---
title: "Consume an OData Service and use External Entities"
category: "Integration"
menu_order: 8.5
tags: ["integration", "OData service", "data hub", "consume", "external entity", "OData service URL"]
description: "Describes the development workflow for working with oData and external entities using Odata service URL."
---

## 1 Introduction

Licensed users of Mendix Data Hub can also directly consume published OData Services during app development without using the functionality of the [Data Hub Catalog](/data-hub/data-hub-catalog) through the [Data Hub pane](/refguide/data-hub-pane). This can save time when, for example, developing and testing [published OData services](/refguide/published-odata-services) which can be deployed locally and consumed without having to register them in the Data Hub Catalog.

You can create a [Consumed OData Service](/refguide/consumed-odata-service)  document in your app model and specify the OData service contract URL or a (local) metadata.  A mapping of the service will be created and listed in the **Data Hub Project** pane (displayed when no search term is specified) and  the exposed entities can be dragged into the domain model as [External Entities](/refguide/external-entities).  

This document also describes how you can connect to the *same service* which is published in the Data Hub Catalog when you have finished your offline development.

**This how-to will teach you how to do the following:**

* Add a consumed OData Service document to your project model
* Specify a published OData service using the service metadata contract URL or the file path
* Use the **Data Hub Project** pane to view and use the exposed entities in your app development
* Connect to the same service registered in the Data Hub Catalog

{{% alert type="info" %}}
A Data Hub license is required to consume OData services and use the **Data Hub pane**.
{{% /alert %}}


## 2 Prerequisites

Before starting this how-to you will need the following:

* Be familiar with app modeling using [external entities](/refguide/external-entities)

* Have the URL of a published OData v3 or v4 metadata contract or a locally stored file—the  following are examples that you can use in this how-to:  

	* Use the **Copy Data Source URI** button in the [Data Hub Catalog](/data-hub/data-hub-catalog/search#search-details) to copy the location of the metadata file to your clipboard:

    ![published Odata service URL](attachments/consume-an-odata-service/dh-copy-url.png)

	* The OData.org website at https://www.odata.org/odata-services/ publish example files for the different versions of OData. A example that you can use is the [Northwind read only](https://services.odata.org/V3/Northwind/Northwind.svc) service which is rich in exposed datasets.   
	
		{{% alert type="info" %}}This sample OData file does not connect to any datasets, therefore the resulting app will not display any data for the external entities that you may use in your app .{{% /alert %}}
		
	* 


## 3 Using Published OData Services {#published-service}

This section describes how you can obtain the URL or file of an OData service that can that you can use in this how to. You can use the URL or download the contract of a data source that is registered in the Data Hub catalog. You can also use an example of a typical OData service that is publicly available.Thirdly the 

### 3.1 Sample file from OData.org {#sampleODataservice}

The OData.org website publish example files for the different versions of OData at https://www.odata.org/odata-services/.  The following steps describe the example file that is used in this how-to which has a rich assortment of exposed entities.  



1. Go to  https://www.odata.org/odata-services/ Under the **OData v3** tab you will use the sample OData v3 example, [Northwind read only](https://services.odata.org/V3/Northwind/Northwind.svc) service. Click the link for this file or any other file that is listed for OData v3 to open the metadata file for this service.

2. The file that you will see displayed is stored under the name `$metadata` at the web URL.

3. Therefore, the full URL of the file is `https://services.odata.org/V3/Northwind/Northwind.svc/$metadata`.

You can also download the file to your computer if you want to try the process for consuming a locally stored file. 

### 3.2 URL or Contract from a Data Source Registered in Data Hub 

You can obtain the URL of a service or **Data Source**  (as it is known in the Catalog) that is registered in the [Data Hub Catalog](/data-hub/data-hub-catalog/search#search-details). On the data source details page, there is a You can use the **Download** functionality from the same screen to download the metadata contract to your computer and use that to consume from a file as described in [Using a Locally Stored OData Metadata File](#consumefile).

### 3.3 Mendix Published OData Service Deployed Locally {#how-to-file}

This is the most common use for consuming an OData service described in this how to, for local service development and testing the service before it is registered in the Data Hub Catalog.  This means that you only need to deploy the publishing app and service locally.

 In the Data Hub how-to [Share Data Between Apps](/data-hub/share-data/index) a simple published OData service is created in [Section 3: Creating an App](/data-hub/share-data/index#createapp) and [Section 4: Publishing to the Data Hub Catalog](/data-hub/share-data/index#publishing). You can choose to deploy this app locally (to your computer)  by selecting **Run Locally** and create local test data for the app which you will be able to use in the consuming app.  

#### 3.3.1 Published OData Service URL {#publishedservice}
For a locally deployed app in Studio Pro the, URL is displayed under the **Settings** tab of the **Published OData Service** document. The OData metadata contract is the file  `$metadata` file and the **Service feed** provides the location of locally stored datasets that you create for the app:

![published Odata service URL](attachments/consume-an-odata-service/metadata-contract-url.png) 

#### 3.3.2 Export the Published OData Service file to your Computer
If you are working locally and creating published OData services and creating data that you want to test, you can **Export** the **Metadata** file locally from the **Settings** tab of the **Published OData Service** document:

![published Odata service URL](attachments/consume-an-odata-service/metadata-contract-file.png) 

You can consume the locally stored OData service by specifying the file as described in [Consuming an OData Service from a local file](#consumefile). 

You can use locally stored datasets whose location will be specified by the **Service feed** value.

## 4 Consuming an OData Service using the URL{#consumeurl}

When you search for a data source in the [Data Hub](/refguide/data-hub-pane) pane you will be presented with all the registered assets in the [Data Hub Catalog](/data-hub/data-hub-catalog/search) that satisfy your search criteria. These assets are exposed in, and registered as, published OData services in the **Data Hub Catlog**. When you drag an entity from the **Data Hub** pane into your domain model, the asset metadata contract is accessed at the service endpoint and a **Consumed OData Service** document is added to your app project model with the details of metadata file. In addition, the **Location** document that accompanies all **Consumed OData Services**is also added providing **Constant** information.

If you want to model using an OData service that is not registered in the Data Hub Catalog, or you are developing services that are not ready to register in the **Data Hub Catalog**, you can use the procedure given in this how-to. By specifying the URL of your OData service you can consume the service directly into your model and see the exposed entities in the **Data Hub** project panel and easily drag them into your domain model. 

During app development and testing phases this means that you can deploy your app locally and without taking up a cloud slot which can speed up the process that may involve several iterations.

Follow these steps to consume a published Odata service directly using the URL:

1. First you must add a **Consumed OData service** document to your model: in the project explorer, right-click over the model name and select **Add other** > **Consumed OData Service**.
     {{% alert type="info" %}}You must have a Data Hub license to see this menu item.
     {{% /alert %}}
     
2. In the **Add Consumed OData Service** dialog box, enter a name for the Consumed OData Service document. In this case, accept the default **Consumed_OData_Service**  and click **OK**.

3. A blank consumed OData document is added to the model and the **Metadata Editor** dialog is displayed asking you to specify the metadata file.

4. By default the **Import from** is set to **URL**; click **Edit**.

5. Copy the full URL of the OData service you want to consume . For the example in described in [Sample file from OData.org](#sampleODataservice) this is: `https://services.odata.org/V3/Northwind/Northwind.svc/$metadata`.
     Alternatively, you can copy the URL of a published OData service created in your Mendix app as described in [Published OData Service URL](#publishedservice).

6.  Paste the URL in the **Metadata URL** and click **OK**:
     ![use data hub pane](attachments/consume-an-odata-service/metadata-URL-box.png)
    
7. The **Metadata Editor** will show the **URL** of the file that you have specified. Click **OK**: 

     ![metadata editor URL](attachments/consume-an-odata-service/metadata-editor-url.png)

8. You will be informed of the following:

     ![use data hub pane](attachments/consume-an-odata-service/data-hub-pane-dialog-box.png)

9. Click **OK**. The **Consumed_OData_Service** document is added to the model in the project explorer and displayed:

   ![consumed odata service doc](attachments/consume-an-odata-service/consumed-odata-document.png)

10. In Studio Pro, the URL of the service must be provided so that it can use this when locating further information for the service and the datasets it connects to. Under the **Connection** tab, this is specified in the **Service URL**. This information is stored in the **Constant** document that accompanies a **Consumed OData service**. Click **Select** and for the **Select Constant** click **New** to create a new constant. 

11. Click **OK**  to accept the default **Name**: *Consumed_OData_Service_Location*:

![constant doc](attachments/consume-an-odata-service/location-constant-document.png)
11. For the **Default value** enter the service URL  `https://services.odata.org/V3/Northwind/Northwind.svc/` and click **OK**. You will notice that the "Location" or **Constant** definition document is added to the module: 

    {{% image_container width="300" %}}![location doc](attachments/consume-an-odata-service/location-constant-url.png){{% /image_container %}}

12. In the **Data Hub** pane, the new service is listed in the **Project** panel. The green tick indicates that this contract is loaded and being consumed.  For more details about the information displayed in the **Data Hub** pane and the **Project** panel see the [Data Hub Project](/refguide/data-hub-pane#projectpanel) panel.

13. Take a few moments to explore the entities that are available in the service, and the attributes for the entities (click **+** to expand the entity and display the attributes). The **Northwind** example has many entities: 

    {{% image_container width="300" %}}![use data hub pane](attachments/consume-an-odata-service/data-hub-project-pane.png){{% /image_container %}}

14. You can now drag and drop entities from the service into your domain model. 

    {{% alert type="info" %}}As this is a sample public OData Service, there is no associated dataset available that you will be able to use in your app. You can use the example given in [Mendix Published OData Service Deployed Locally](#how-to-file) for which you can create you own set of data and view it in the consuming app.

    {{% /alert %}}

## 5 Consuming an OData Service Using a Locally Stored OData Metadata File {#consumefile}
If you want to consume from a metadata file stored locally, follow up to step 3 of [Consuming an OData Service using the URL](#consumeurl) and then proceed with the following:

1. In the **Metadata Editor** dialog, select **File** and then click **Browse** to select a locally stored OData contract.

2. Select the saved `$metadata` and click **Open** in the finder. 

3. You will be informed of the following:

     ![use data hub pane](attachments/consume-an-odata-service/data-hub-pane-dialog-box.png)

4. Click **OK**. The **Consumed_OData_Service** document is added to the model in the project explorer and under the **Metadata** tab you will see the metadata file with the local pathname. 
   ![consumed odata service doc](attachments/consume-an-odata-service/consumed-odata-document-file.png)
   
5.  The consumed service is added to the **Project**  panel in the **Data Hub** pane and the green tick indicates that it is being consumed.  For further detail see the [Data Hub Project](/refguide/data-hub-pane#projectpanel) panel.
	
6. Continue with Step 10 and 11 of [Consuming an OData Service using the URL](#consumeurl) and for the **Constant** add the local service URL to specify the data that the service connects to.

Your resulting app, which you can also deploy locally, will show the consumed entities and display the specified data in the resulting consuming app.


## 7 Connecting to a Service in Data Hub 

When you have been developing an app using the method described in this how-to and you want to connect to *the same service* registered in the Data Hub Catalog, the method described in this section which will enable you to use the advantages of consuming through the Data Hub Catalog which includes notifications of updates to the consumed registered services.

{{% alert type="warning" %}}This method can only be used if the service contract that you want to connect to is the same as the one that you consumed as a URL or file. This means that there should be no signficant differences in the metadata contract that is registered in the Catalog otherwise this will result in errors.{{% /alert %}}

To connect from your locally consumed OData service to a service in the Data Hub Catalog follow these steps: 

1. In the project exlporer delete the consumed service doc in project explorer. In the following example the **...
2. Search for the service in the Data Hub pane
3. Drag an entity from the service into the domain model
4. Rename the newly consumed doc to the name of the one consumed in your model
5. Delete the entity that you consumed to create the link to the catalog.

In this way, you can also ensure that when new versions of the published OData services that you have consumed in your project are made available you will be notified and can **Update** or **Switch** to the newer versions.

## 8 Updating Consumed Services without Using the Data Hub Pane

If the contract is different - then will get a consistency error. 

Remove this section

Non breaking changes 

Check out the story about the removal of the Update button??? 

As described in [Updating or Switching a Consumed OData Service](/refguide/consumed-odata-service#updating) if a different metadata contract is detected by Studio Pro at the service URL to the one that is currently being consumed by the project, you will be presented with the option to **Update** to the new contract. 

## 4 Read More
* [Consumed OData Service](/refguide/consumed-odata-service) 
*  [Data Hub pane](/refguide/data-hub-pane)
* [External Entities](/refguide/external-entities)
* [Data Hub Catalog](/data-hub/data-hub-catalog)


