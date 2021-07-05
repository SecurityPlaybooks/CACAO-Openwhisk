# CACAO-Openwhisk
An initiative to enable to invocation of an Openwhisk-based action as a part of a CACAO Playbook. Either using attack-cmd or defining a new command type for CACAO means we can then enable an integration framework for running 'serverless' workloads in any cloud provider of your choice.
## Overview 

Cyber Security response is performed differently by many organisations and a given organisation can have many tools they use to achieve tasks. 
One offered solution over the years by security vendors is to provide bespoke integration frameworks and BPMN modeled graphical flows to orchestrate them. The problem that has emerged from this is there are now hundreds of 'apps'/'integrations'/'functions' that don't work with each other and in many cases overlap and compete with one another. 

The goal of this project is to try and squash some of that by providing a gateway to serverless computing using Openwhisk. Using an open-source event based framework like Openwhisk is done with the hopes that each vendor can eventually leverage each others contributions to the security space as its developer mindshare grows. Instead of building a bespoke response that only serves to lock you in to that security vendor you can build on open technologies that you can take anywhere.

Security vendors will unfortunately always compete on their products solutions but we as security professionals should instead collaborate on the solving of problems.

## Specification 
In this repository we made an in-code specification definition of the `openwhisk` command using [pydantic](). This provides a quick method of validating your `openwhisk` command adheres to the specification defined below. This spec is a work in progress and will evolve over time.

```python
class OpenwhiskSpec(BaseModel):
    """OpenwhiskSpec is a definition of parameters
    needed for the openwhisk command to be considered valid.
    The spec supports both the running of modules and playbooks
    """
    name: str = "openwhisk"
    id: UUID

```

## Usage
In its current state this package is usable within another python package for either:
+ The running of openwhisk actions against a specified API Host.
+ The validation of a OpenwhiskSpec command

## Installation
You can choose to install this package from Pypi which will grab the last released version: 
```
pip install cacao-openwhisk
```
..Or you can install this package directly from the source code:
```
python setup.py install
```


### What is CACAO? 
CACAO is a specification standard cultivated by OASIS. This specification defines the schema and taxonomy for collaborative automated course of action operations (CACAO) security playbooks and how these playbooks can be created, documented, and shared in a structured and standardized way across organizational boundaries and technological solutions. [source](https://docs.google.com/document/d/144kgoCnZbxc0CXms3EeACf4Sz84lmEt88JoVr4FnmSc/edit#)

### What is Openwhisk?
Apache OpenWhisk is an open source, distributed Serverless platform that executes functions (fx) in response to events at any scale. OpenWhisk manages the infrastructure, servers and scaling using Docker containers so you can focus on building amazing and efficient applications.


### Use Case Demonstrated by Ryan Gordon
Demonstrates how CACAO Security Playbooks can integrate open source standard frameworks like Openwhisk to enable the creation of vendor agnostic "functions" for the Open Security Community.

