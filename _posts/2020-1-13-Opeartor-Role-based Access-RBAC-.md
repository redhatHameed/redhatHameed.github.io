---
layout: post
title:  Operator  Role-based Access Control (RBAC)
---


When the Operator SDK generates an Operator project, it creates a number of manifest files for deploying the Operator.
Many of these files grant permissions to the deployed Operator to perform the various tasks it does throughout its lifetime.


The Operator SDK generates three files under deploy directory related to Operator permissions:

-deploy/service_account.yaml

-deploy/role.yaml

-deploy/role_binding.yaml


The serverice account create service account which installs and manages the application.

Role defines the role-based access control restriction or what permissions the service account has 

Role-based access control, which maps the service account to the role and provides authorization of given actions to the service account.


Examples:

**Service Account**:
```
apiVersion: v1
kind: ServiceAccount
metadata:
  name: <application-name>-operator

```

**Role**

The * wildcard allows all actions on the given resources:

```$yaml
apiVersion: rbac.authorization.k8s.io/v1
kind: Role
metadata:
  creationTimestamp: null
  name: <pplication-name>-operator
rules:
- apiGroups:
  - ""
  resources:
  - pods
  - services
  - endpoints
  - persistentvolumeclaims
  - events
  - configmaps
  - secrets
  verbs:
  - '*'
- apiGroups:
  - ""
  resources:
  - namespaces
  verbs:
  - get
- apiGroups:
  - apps
  resources:
  - deployments
  - daemonsets
  - replicasets
  - statefulsets
  verbs:
  - '*'
- apiGroups:
  - monitoring.coreos.com
  resources:
  - servicemonitors
  verbs:
  - get
  - create
- apiGroups:
  - broker.amq.io
  resources:
  - '*'
  - activemqartemisaddresses
  - activemqartemisscaledowns
  - activemqartemis
  verbs:
  - '*'
- apiGroups:
  - route.openshift.io
  resources:
  - routes
  - routes/custom-host
  - routes/status
  verbs:
  - get
  - list
  - watch
  - create
  - delete
- apiGroups:
  - extensions
  resources:
  - ingresses
  verbs:
  - get
  - list
  - watch
  - create
  - delete


```

**RoleBiding**

```
kind: RoleBinding
apiVersion: rbac.authorization.k8s.io/v1
metadata:
  name: application-name-operator
subjects:
- kind: ServiceAccount
  name: application-name-operator
roleRef:
  kind: Role
  name: application-name-operator
  apiGroup: rbac.authorization.k8s.io

```










-- 

   