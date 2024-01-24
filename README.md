[comment]: # "Auto-generated SOAR connector documentation"
# Spur Context

Publisher: Splunk Community  
Connector Version: 1.1.0  
Product Vendor: Spur  
Product Name: Context  
Product Version Supported (regex): ".\*"  
Minimum Product Version: 6.1.1  

The Spur Context API provides REST API access for IP Context data. Visit our website for more information on use-cases, integrations, and client successes

[comment]: # " File: README.md"
[comment]: # " Copyright (c) 2024 Splunk Inc."
[comment]: # ""
[comment]: # "  Licensed under Apache 2.0 (https://www.apache.org/licenses/LICENSE-2.0.txt)"
[comment]: # ""
# Splunk> Phantom

Welcome to the open-source repository for Splunk> Phantom's spur_context App.

Please have a look at our [Contributing Guide](https://github.com/Splunk-SOAR-Apps/.github/blob/main/.github/CONTRIBUTING.md) if you are interested in contributing, raising issues, or learning more about open-source Phantom apps.

## Legal and License

This Phantom App is licensed under the Apache 2.0 license. Please see our [Contributing Guide](https://github.com/Splunk-SOAR-Apps/.github/blob/main/.github/CONTRIBUTING.md#legal-notice) for further details.

### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a PassiveTotal asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**base_url** |  required  | string | URL to connect to Spur
**api_token** |  required  | password | API token

### Supported Actions  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity   
[lookup ip](#action-lookup-ip) - Get IP information/reputation

# action: 'test connectivity'
Validate the asset configuration for connectivity

Type: **test**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output  

## action: 'lookup ip'
Get ip information/reputation

Type: **investigate**  
Read only: **True**

The Spur Context API provides REST API access for IP Context data. Visit our website for more information on use-cases, integrations, and client successes.

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**ip** |  required  | IP to query | string |  `ip`

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.as\.number | numeric | 
action\_result\.data\.\*\.as\.organization | string | 
action\_result\.data\.\*\.ip | string | 
action\_result\.data\.\*\.client\.count | numeric | 
action\_result\.data\.\*\.client\.spread | numeric | 
action\_result\.data\.\*\.client\.behaviors | string | 
action\_result\.data\.\*\.client\.countries | string |
action\_result\.data\.\*\.client\.concentration\.city | string | 
action\_result\.data\.\*\.client\.concentration\.skew | numeric | 
action\_result\.data\.\*\.client\.concentration\.state | string | 
action\_result\.data\.\*\.client\.concentration\.country | string | 
action\_result\.data\.\*\.client\.concentration\.density | numeric | 
action\_result\.data\.\*\.client\.concentration\.geohash | string | 
action\_result\.data\.\*\.location\.city | string | 
action\_result\.data\.\*\.location\.state | string | 
action\_result\.data\.\*\.location\.country | string | 
action\_result\.data\.\*\.organization | string |
action\_result\.data\.\*\.infrastructure | string | 
action\_result\.data\.\*\.risks | string | 
action\_result\.data\.\*\.client\.types | string | 
action\_result\.data\.\*\.tunnels\.\*\.type | string | 
action\_result\.data\.\*\.tunnels\.\*\.entries | string | 
action\_result\.data\.\*\.tunnels\.\*\.operator | string | 
action\_result\.data\.\*\.tunnels\.\*\.anonymous | string | 


### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a Context asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**base_url** |  required  | string | URL to connect to
**api_token** |  required  | password | API Token to authenticate with
**verify_server_cert** |  optional  | boolean | Verify server certificate

### Supported Actions  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity using supplied configuration  
[lookup ip](#action-lookup-ip) - Check for the presence of an IP in a threat intelligence feed  

## action: 'test connectivity'
Validate the asset configuration for connectivity using supplied configuration

Type: **test**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output  

## action: 'lookup ip'
Check for the presence of an IP in a threat intelligence feed

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**ip** |  required  | IP to lookup | string |  `ip` 

#### Action Output
DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------------
action_result.parameter.ip | string |  `ip`  |  
action_result.status | string |  |   success  failed 
action_result.message | string |  |  
summary.total_objects | numeric |  |   1 
summary.total_objects_successful | numeric |  |   1 
action_result.data.\*.as.number | numeric |  |  
action_result.data.\*.as.organization | string |  |  
action_result.data.\*.ip | string |  `ip`  |  
action_result.data.\*.client.count | numeric |  |  
action_result.data.\*.client.spread | numeric |  |  
action_result.data.\*.client.behaviors | string |  |  
action_result.data.\*.client.countries | numeric |  |  
action_result.data.\*.client.concentration.city | string |  |  
action_result.data.\*.client.concentration.skew | numeric |  |  
action_result.data.\*.client.concentration.state | string |  |  
action_result.data.\*.client.concentration.country | string |  |  
action_result.data.\*.client.concentration.density | numeric |  |  
action_result.data.\*.client.concentration.geohash | string |  |  
action_result.data.\*.location.city | string |  |  
action_result.data.\*.location.state | string |  |  
action_result.data.\*.location.country | string |  |  
action_result.data.\*.organization | string |  |  
action_result.data.\*.infrastructure | string |  |  
action_result.data.\*.risks | string |  |  
action_result.data.\*.client.types | string |  |  
action_result.data.\*.tunnels.\*.type | string |  |  
action_result.data.\*.tunnels.\*.entries | string |  `ip`  |  
action_result.data.\*.tunnels.\*.operator | string |  |  
action_result.data.\*.tunnels.\*.anonymous | string |  |  
action_result.summary | string |  |  