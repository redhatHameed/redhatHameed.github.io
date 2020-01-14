---
layout: post
title:  Operator Life Cycle Manager(OLM) UI component Information
---

OLM UI convert the Custom Resource (CR) into a user interface. The main idea behind for desinging UI for easy use for non technical user can easily install any product by selecting or inserting the value through UI.

As OLM uses the ClusterServiceVersion is the primary metadata resource that describes an Operator and this file contain different section, for UI setting we need to add The **specDescriptors** and **statusDescriptors** fields provide additional metadata around the spec and status fields that will be present on the custom resource. 
Compatible UIs can use this additional information to render an interface for users.


For each field in the custom resource’s spec, add an entry to the specDescriptors field. 

Each entry should contain the following:


- displayName - user-friendly name of the field
- description - information about what the field represents
- path - dot-delimited path of the field on the CRD or types.go object
- x-descriptors - UI component information on the field’s capabilities, x-descriptors field contain two section, the fieldGroup and field-type


 
 As below list contains different field type of x-descriptors that are commonly supported by compatible UIs:
 
 
 

**Boolean Switch**: urn:alm:descriptor:com.tectonic.ui:booleanSwitch

**Checkbox**:  urn:alm:descriptor:com.tectonic.ui:checkbox

**Endpoint List**: urn:alm:descriptor:com.tectonic.ui:endpointList

**Image Pull Policy**: urn:alm:descriptor:com.tectonic.ui:imagePullPolicy

**Label**: urn:alm:descriptor:com.tectonic.ui:label

**Namespace Selector**: urn:alm:descriptor:com.tectonic.ui:namespaceSelector

**Node Affinity**: urn:alm:descriptor:com.tectonic.ui:nodeAffinity

**Number**:  urn:alm:descriptor:com.tectonic.ui:number

**Password**:  urn:alm:descriptor:com.tectonic.ui:password

**Pod Affinity**: urn:alm:descriptor:com.tectonic.ui:podAffinity

**Pod AntiAffinity**:  urn:alm:descriptor:com.tectonic.ui:podAntiAffinity

**Resource Requirements**: urn:alm:descriptor:com.tectonic.ui:resourceRequirements

**Selector**: urn:alm:descriptor:com.tectonic.ui:selector:

**Text**:  urn:alm:descriptor:com.tectonic.ui:text

**Update Strategy**: urn:alm:descriptor:com.tectonic.ui:updateStrategy

---
The structure of the **statusDescriptors** field also similar, including the same fields you need to specify



**Conditions**: urn:alm:descriptor:io.kubernetes.conditions

**k8s phase reason**: urn:alm:descriptor:io.kubernetes.phase:reason

**k8s phase**: urn:alm:descriptor:io.kubernetes.phase

**Pod count**: urn:alm:descriptor:com.tectonic.ui:podCount

**Pod statuses**: urn:alm:descriptor:com.tectonic.ui:podStatuses

**Prometheus endpoint**: urn:alm:descriptor:prometheusEndpoint

**Text**: urn:alm:descriptor:text

**W3 link**: urn:alm:descriptor:org.w3:link

--- 


   