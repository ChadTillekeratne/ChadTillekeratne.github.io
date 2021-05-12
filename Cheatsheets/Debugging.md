# Common Failure Scenarios

## Failed Service Call

|Failure/Fault| Error / Exception (Linux) |Windows|Troubleshooting Commands (Linux)|Windows|
|--|--|--|--|--|
|Failed service location (DNS)|`nodename nor servname provided, or not known (<host>:<port>)`||`nslookup`, `dig`
|Port not listening|||`nc -z -v <host> <port>` |`telnet <host> <port>`
|SSL negociation failure
|SSL trust failure (client validation)
|Connection Timeout (client, server)
|Failued authentication (401,403, close connection)
|Request timeout
|Remote service close connection
|Error response

## In Process Faults

|Category|Failure/Fault|Error / Exception|Troubleshooting Commands
|--|--|--|--|
|Logic Bug|Null variable reference|
||Bad input validation
||Off by one
||Bad comparison
||Infinite loop
||Race condition
|Locks
||.Net Garbage Collection (GC)
||State variable content

## Server/System Faults

|Category|Failure/Fault|Error / Exception|Troubleshooting Commands
|--|--|--|--|
|Resource Exhaustion|Processor/memory/disk/network

# Operating System

|Scenario | Sub-Scenario | Windows | Linux
|--|--|--|--|
|Process|List|`tasklist`|`top`, `htop`|
||Activity|[[SysInternals] Process Monitor](https://docs.microsoft.com/en-us/sysinternals/downloads/procmon)|`strace`
|Network|Trace||`netsh trace start persistent=yes capture=yes tracefile=c:\temp\my-trace.etl`|`tcpdump`
||Open connections|
||Listening Ports|`netstat -aof `|`netstat -plnt` 
|Disk IO Trace

# Framework 

|Scenario | Sub-Scenario | .NET Framework | dotnet core | GO | Node.JS
|--|--|--|--|--|--|--|
|Profiling|CPU Usage|||[pprof](https://golang.org/pkg/net/http/pprof/)|`node --prof app.js`
|Memory|Taking a memory dump

## Framework Details

### dotnet

#### Log all exceptions

`logman create trace -n dotnetexceptions -o c:\dotnetexceptions.etl
logman update trace -n dotnetexceptions -p Microsoft-Windows-DotNETRuntime (ExceptionKeyword)
logman start -n dotnetexceptions
  [...]
logman stop -n dotnetexceptions`

Trace Viewer:
-  https://github.com/Microsoft/perfview/blob/master/documentation/Downloading.md

#### Record all HTTP Traffic

<pre>
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
    <system.diagnostics>
        <trace autoflush="true" />
        <sources>
            <source name="System.Net" maxdatasize="1024">
                <listeners>
                    <add name="MyTraceFile"/>
                    <add name="MyConsole"/>
                </listeners>
            </source>
        </sources>
        <sharedListeners>
            <add
              name="MyTraceFile"
              type="System.Diagnostics.TextWriterTraceListener"
              initializeData="System.Net.trace.log"
                />
            <add name="MyConsole" type="System.Diagnostics.ConsoleTraceListener" />
        </sharedListeners>
        <switches>
            <add name="System.Net" value="Information" />
            <!-- <add name="System.Net" value="Verbose" />-->
        </switches>
    </system.diagnostics>
</configuration>
</pre>
