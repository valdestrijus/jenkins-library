# transportRequestGetTransports

## Description
Gets all open Transport Requests that can be modified for a Change Document on the Solution Manager.

## Prerequisites
* **[Change Management Client 2.0.0 or compatible version](http://central.maven.org/maven2/com/sap/devops/cmclient/dist.cli/)** - available for download on Maven Central.

## Parameters
| parameter        | mandatory | default                                                | possible values    |
| -----------------|-----------|--------------------------------------------------------|--------------------|
| `script`        | yes       |                                                    |                    |
| `changeId`        | yes       |                                                    |                    |
| `cmCredentialsId`  | yes       |                                                    |                    |
| `cmEndpoint`        | yes       |                                                    |                    |

* `script` - The common script environment of the Jenkinsfile running. Typically the reference to the script calling the pipeline step is provided with the `this` parameter, as in `script: this`. This allows the function to access the [`commonPipelineEnvironment`](commonPipelineEnvironment.md) for retrieving, for example, configuration parameters.
* `changeId` - The id of the change document to get the transport requests.
* `cmCredentialsId` - The credentials to connect to the Solution Manager.
* `cmEndpoint` - The address of the Solution Manager.

## Step configuration
The following parameters can also be specified as step parameters using the global configuration file:

* `cmCredentialsId`
* `cmEndpoint`

## Return value
A Map containing the ids of the Transport Requests that are open and can be modified.

## Exceptions
* `AbortException`:
    * If the change id is not provided.
    * If the request to get the transport requests fails.

## Example
```groovy
def transportRequests = transportRequestGetTransports script:this, changeId: '001'
```
