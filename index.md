---
layout: default
---
# How did we get here?
A common point of salesforce implementations is the need to document the data model of the current implementation. 
Several different tools have tried, but none was able to achieve my requirements, so I decided to implement a solution myself.

### Requirements:
* The data dictionary should be able to display standard objects and fields.
* The data dictionary should be able to display custom objects and fields.
* The data dictionary should be able to display managed package objects.
* The data dictionary should display Salesforce's data categorization.
* The data dictionary should display help text and description from fields.

Seems simple, but the data required for getting all this information was across multiple metadata.
This added complexity made it challenging to list all objects in a consistent and simple way.

Due to its modular and simple implementation, a SFDX plugin was defined as the development method for the solution. It gave us really good abstraction to have a simple start point. SFDX plugin gave us:
* Authentication abstraction
* Simplified access to metadata
* Org access abstraction

As a baseline for our development, we (I) forked the awesome [data model generator](https://github.com/gavignon/sfdc-generate-data-dictionary) by @gavignon.
Simplifications and security measures were added (no username and password as command parameters etc...), and the missing metadata was added to the data dictionary, such as data category for fields.


## Instalation

```bash
sfdx plugins:install sfdxdatadicgen
```

### Usage
```bash
$ sfdx dataDictionary:generate [-o <string>] [-m] [-s <array>] [-l <array>] [-v <string>] [-u <string>] [--apiversion
<string>] [--json] [--loglevel trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL]
```
### OPTIONS

-l, --includemanagedpackages=includemanagedpackages                               List of namespaces of manage
packages that will be downloaded.+

-m, --includemanaged                                                              boolean that indicates if managed
package files should also be
included

-o, --output=output                                                               destination and file name for xls
dataDictionary

-s, --includestandardsobjects=includestandardsobjects                             Additional standard objects
(Account, Contact and User go by
default)

-u, --targetusername=targetusername                                               username or alias for the target
org; overrides default target org

-v, --targetdevhubusername=targetdevhubusername                                   username or alias for the dev hub
org; overrides default dev hub org

--apiversion=apiversion                                                           override the api version used for
api requests made by this command

--json                                                                            format output as json

--loglevel=(trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL)  [default: warn] logging level for
this command invocation

###EXAMPLES
```bash
$ sfdx dataDictionary:generate --targetusername myOrg@example.com
```
```bash
$ sfdx dataDictionary:generate -u myOrgName -m true -s Case,Opportunity,Product2
```
