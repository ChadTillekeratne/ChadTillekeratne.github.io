# Overview
## Methology
- Immutable Infrastructure - Once an artifact is created in a system, does not change ny user modifications
    - Traditional infrastructure is mutable, incremental updates are performed (apt-get)
		- Not represented by one artifact, but rather the current state (configuration management)
 - Declarative Configuration - represents the desired configuration, Kubernetes is responsible to ensure actual states
	- Opposed to imperative config - define by a series of instructions
		- Imperative describe actions actions
		- Declarative defines state
	- Support infrastructure as code - Storing declarative configuration in source control
- Self-healing - continuously takes actions to ensure current state matches desired state
  - EG - when you define 3 replicas, it doesn't just create them, it continually checks and repairts
	- Operator - more advanced logic to maintain, scale, heal, etc. specific software (Eg - mySQL) is encoded into an operator app that runs as a container in the cluster 
		- Think of this as an automated SRE
- Decoupled architectures - each component is seperated, defined by APIs
    - Crisp APIs limit cross team communications, micro services - allows for scaling of an App Dev team.  One pizza teams

## Container Basics
- Containers
	- Application programs are comprised of: language runtime, libraries, and you source code
	    - Shared dependencies of differing versions creates "it works on my machine"
	- Docker - runtime engine
	- Container images - bundle a program and its dependencies into a single artifact under a root file system
	    - Binary package that encapsulates all necessary files
	- Docker Image Format
		- OCI-compliant (Open Container Initiative)
		- Overlay file system - layer files systems
			- Various implementations: aufs, overlay, overlay2
		- Container configuration file - defines how to: network, namespace isolation, resource constraints (cgroups), syscall restrictions
	- Types:
      - System containers - mimic full VMs, fully bootable processes
      - Application containers - contains application logic

- Docker
	- .dockerfile - automates the creation of a docker image
	- .dockerignore - defines files that should be ignored when copying to image 
	- Optimizing size
		- Files that are removed in subsequent layers are still present in the images
		- Every time you change a layer, it changes every layer that comes after it
			- Order from leat likely to change to most likely
		- Don't build an application in the image, can leave unneeded dev/build tools
			- Multistage builds - produces multiple images (build image, deployment image)
		- Store in remote registry (public or private)

## Deploying Kubernetes
- Minicube - sets up a local K8s cluster (single node)
  - Kubectl - administration command line interface, makes calls to the API server
  - Namespaces - organizes objects in a cluster
    -  By default, kubectl uses "default" namespace
    - Change default context in `$HOME/.kube/config`; kubectl configuration file, also stores auth

## Pods
- Groups one or more containers
- Smallest deployable artifact
- All containers in a pod land on the same machine
- Each container in a pod runs its own cgroup, but share some Linux namespaces
  - Share network namespace (IP Address and Port space)
  - Share Hostname (UTS Namespace)
  - Allow for communication over System V IPC or POSIX message queues
  - Accessing a Pod
    - Port forwarding
      - `kubectl port-forward <name> 8080:8080`
  - Healthchecks
    - Process health check - ensures that the main process of an application is always running, restart if not
    - Liveness healthcheck - Runs application specific logic
    -  Defined in the pod manifest
      -  Defined per container
	- Readiness healthcheck probe - container ready to server requests
	  - Failures remove from load balancer
      - Probe types:
	    - `httpGet`
	    - `tcpSocket`
	    - `exec` - execute a script in the container; return 0 for good

## Resource Management
- Utilization metric: CPU, memory, GPU
- Requested per container (not pod)
- Minimum required resources
- Memory over utilization - when system runs out, terminate (restarted) containers over requested
- Maximum - kernel is configured with limits
- Volumes: spec Volumes in pod manifest

## Labels and annotations
- Labels - key-value pair attached to objects, holds identifying information
    - Label selectors - used by user tools and different system objects (replicaSets to Pods)
	  - Kubernetes is a decoupled architecture, labels are used to relate across 
	- Annotations - key-value-pair stores non-identifying information
	  -  Can by leveraged by tools and libraries
	  - Provides extra data; whereas labels are used to identify and groups
	  -  When in doubt, start with annotation, then promote to label when needed

## Service Discovery
-  DNS is default service discovery of the internet
     -  Some clients cache responses (beyond TTL)
   -  Delays in updates
- "Service" object
- Kubernetes provides a DNS service exposed to pods
    - DNS service is installed as a system component
    - `<service-name>.<namespace-name>.svc.<cluster.local> `
		- cluster.local - default basename for the cluter, can be changed
	- Communications from outside the cluster
		- nodePort
		- Cloud providers have "LoadBalancer" type
- Kube-proxy - Network proxy on each node, part of "Service" context
	1. Kube-proxy watches for new services in cluster (via API server)
	1. Programs ipTables rules in the kernel of host to rewrite the desintation of packets
        - If endpoints for a service changes (pods go up/down/fail), ipTables is rewritten by kube-proxy
	- Managing other environment communications
		- Hashicorp's Consul - manage connectivity in/out of cluster
## Http Load-Balancing
- Ingress - name of the kubernetes native http load balancer
- No standard ingress controller, must install your own (pluggable)
  - Sample controllers: Contour, Envoy for load balancer
  - {Contour} translates ingress objects and configures {Envoy}

# Components
- Source: https://kubernetes.io/docs/concepts/overview/components/
## Node Components
-  Kubelet - Runes on each node, ensures containers are running in a pod
  -  Takes PodSpecs, ensures containers meet PodSpecs
- Kube-proxy - Network proxy on each node, part of "Service" context
  -  Maintains network rules on nodes
  -  Uses OS packet filtering if available, otherwise kube-proxy does forward of packets
- Container-runtime - runs containers; sample runtimes: Docker, containerD, CRI-D
  -  Implementation defined by CRI (Container Runtime Interface)
## Control Plane
- Kube-apiserver - frontend for control plane
- Etcd - Highly-available key value store for all cluster data
- Kube-scheduler - watches for newly created pods with no assigned nodes (and assigns nodes)
- Kube-control-manager - runs controller processes
  -  Node controller - notices and respond when nodes go down
  - Replication controller - maintains the correct number of pods
  -  Endpoint controller - populates the endpoint object (joins services and pods)
  -  Service account and token controllers - creates default accounts and API access tokens for new namespaces
  -  Cloud-control-manager - embeds cloud specific control logic
### Add-Ons
  - DNS
  - WebAPI
  - Container Resource Monitoring
  - Cluster Level Monitoring

