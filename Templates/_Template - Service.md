# Service Metadata
|||
|--|--|
|Description|
|Source Code Repository|
|Owner(s)|
|Questions|Teams/Slack/etc. Channels
|API Documentation|{}


# Architecture
[Service Architecture Diagram]

## Components
|Component Name|Protocol|Authentication|Description|
|--|--|--|--|
|ChadFrontdoorWeb|HTTPS|JWT|Main web server
|Elasticsearch|HTTPS|Service Identity|Main data store for customer data
|Weather Web Service|HTTPS|Service Identity|Third-Party Service for getting weather data

# Deployments

