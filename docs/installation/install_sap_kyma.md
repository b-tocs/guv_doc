# Installation for SAP BTP Kyma and HANA Cloud

The Graph Universe (GUV) can be installed on the SAP Business Technology Platform (BTP). The SAP Kyma environment is a Kubernetes (K8S) environment within the SAP BTP. As a persistence layer the SAP HANA Cloud database can be used. 

The required installation steps are described here.

## Prerequisites

The following components are required:

1. SAP BTP account
2. SAP Kyma Cluster
3. SAP HANA Cloud Instance

You can get a trial acess for free. See the [SAP Developer Tutorials](https://developers.sap.com/tutorial-navigator.html) and search for "Kyma" and "HANA".

## Check the HANA database

Login to your SAP BTP subaccount and select "Instances and Subscriptions". You should find an installed "SAP HANA Cloud" Application. 

![SAP BTP Instances](res/sap_btp_instances.png)

Enter the "HANA Cloud Central" Cockpit by selecting the "SAP HANA Cloud" application.

![SAP HANA Cloud Central Cockpit](res/sap_hana_cloud_central.png).

Enter the context menu via "Action" and select "Copy SQL Endpoint". 

Your copied endpoint should be like this:

`0cf183xx-xxxa-xx71-83xx-5ff37xxx324.hana.trial-us10.hanacloud.ondemand.com:443`

Check the DB user and password to access this instance.  


## Prepare the Kyma cluster

Go to your SAP BTP subaccount "Overview" and check the "Kyma Environment". 

![SAP BTP Kyma](res/sap_btp_kyma.png)

Select the "Link to dashboard".

![SAP Kyma Dashboard](res/sap_btp_kyma_dashboard.png)

### Create a namespace

Select `Namespaces` and `Create`. 

![SAP Kyma Namespaces](res/sap_btp_kyma_namespace.png)

Switch to the "Form" view. Enter a valid name: e.g. `guv-demo` and confirm with `Create`. 

![SAP Kyma Namespace creation](res/sap_btp_kyma_namespace_form.png)

A new Kyma namespace is visible and You will see an empty dashboard.

![SAP Kyma Namespace dashboard](res/sap_btp_kyma_namespace_dashboard.png)

### Create the secrets for HANA

In this step You will create a secret for storing the secret connection information to the HANA Cloud database.




