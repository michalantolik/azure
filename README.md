# Azure - Personal Learning Notes

## COMPUTE SERVICES

### Compute Services
- Services used to run cloud-based applications

### Virtualization
- Emulation of physical machines
- Physical machine (server) has OS installed
- OS has virtualization software installed
- Virtualization software creates virtual machines

### Virtual Machine (VM) - IaaS
- Emulation of a physical machine (server) --> from ready images or your own
- Has its own OS installed --> VM emulates hardware

### Virtual Machine Scale Sets (VM Scale Sets) - IaaS
- Set of identical VMs with auto-scaling feature

### Azure Container Instances (AKI) – PaaS
- Service which runs containers inside container groups
- Physical machine (server) has OS installed
- OS has container runtime installed
- Container runtime creates containers from container images --> from container repo
- Container does not have its own OS installed --> Container emulates OS

### Azure Kubernetes Service (AKS) – PaaS
- Platform which orchestrates a set of containers (nodes)

### App Services - PaaS
- Service for hosting webapps --> websites or webservices
- Supports multiple programming languages and containers

### Azure Function (Function Apps) - PaaS
- Service for running small pieces of code --> small webservices
- Serverless in that sense that infrastructure is abstracted away
- Two pricing models: consumption-based plan, dedicated plan
- Good for micro and nano services
