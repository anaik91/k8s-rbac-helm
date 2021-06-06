# Kubernetes RBAC

## Prerequisites

* `Helm v3`
* `Access to Kubernetes`

## Building Values 

Below are the groups  to update add name , namespaces & permission
```
groups:
- name: admin
  namespaces:
  - '*'
  permission: admin
- name: devops-admin
  namespaces:
  - default
  - shared
  - admission-control
  - monitoring
  permission: admin
- name: devops-readonly
  namespaces:
  - default
  - shared
  - admission-control
  - monitoring
  permission: readonly
```

## Installing Helm Chart
```
helm upgrade --install -f values.yaml roles authz --debug
```