MongoDB Connector provides a simple way to connect to MongoDB Atlas via Data APIs hosted using Azure function in your tenant to read and write data to MongoDB Atlas collections. MongoDB connector makes it easy to perform CRUD operations and aggregations on your data in minutes and allows you to query MongoDB to build rich apps and workflows in Power Apps, Power Automate and Logic Apps. 
**Please note that MongoDB deprecated the Atlas Data APIs from September, 2025 and thus please use this connector mechnaism to set up an Azure function and use its url and API keys instead of Atlas' ones in your Apps and Flows.**

## Prerequisites

1. **Configure Atlas Environment**

Register for a new Atlas Account [here](https://www.mongodb.com/docs/atlas/tutorial/create-atlas-account/#register-a-new-service-account). Follow steps from 1 to 4 (Create an Atlas account, Deploy a Free cluster, Add your IP to the IP access list and Create a Database user) to set up the Atlas environment.

2. **Set Up Azure Function as Atlas Data API**

    i. Fork the [MongoDB repo] (https://github.com/mongodb-partners/MongoDB_DataAPI_Azure). Note the new **forked repo url**.
    ii. Click the below **Deploy to Azure** button to have the Azure function created in your tenant.


3. **Create a Data API Key** [**here**](https://www.mongodb.com/docs/atlas/api/data-api/#2.-create-a-data-api-key)

**Note: Save the api key generated as this is the only time you can retrieve the full private key.**

## How to get credentials

Follow the steps in [Create a Data API Key](https://www.mongodb.com/docs/atlas/api/data-api/#2.-create-a-data-api-key) to create API key in Atlas and use it in the API calls

## Get started with your connector

Once the Prerequisites are completed, Go to PowerAutomate-\> Data-\> Connections. Click on "New Connection" and search for MongoDB in the right Search Bar like shown below in the screenshot.

![](RackMultipart20230210-1-bnu4rc_html_73774492813969bd.png)

Click on the MongoDB connection and you would see the below popup which asks to enter the API key and the Base URL.

![](RackMultipart20230210-1-bnu4rc_html_101150465b95d1eb.png)

1: For the "API Key" field, enter the Data API key which you would have set up in the [Step 3](https://docs.google.com/document/d/1C5vDjCxBe_TLi6Q-J2MMK5O9hJQ49zcSU25RB6e6x60/edit#heading=h.i8rsuxkzr1i2)

2: For the "BaseUrl", enter the URL Endpoint you find in the MongoDB Atlas portal-\> [Data API](https://docs.google.com/document/d/1C5vDjCxBe_TLi6Q-J2MMK5O9hJQ49zcSU25RB6e6x60/edit#heading=h.x8ak3uxusfkl).

Use one of the Data APIs for any CRUD operations against MongoDB Atlas. For complex queries, use the "Run an Aggregation Pipeline" API to use aggregation stages to massage the output from one stage to another. The flexibility and dynamism of MongoDB allows you to create rich apps and automate any time consuming processes. You keep enhancing the apps by adding more features and fields to the same collection.

Additionally, check [Appsource](https://appsource.microsoft.com/en-us/product/dynamics-365/mongodb.mongodb_customer_onboarding_app) for a hands-on demo of a Banking Customer Onboarding application built using Power Apps, Power Automate and MongoDB Atlas. The Github link for the same is [here.](https://github.com/mongodb-partners/MongoDB_Atlas_integration_with_Microsoft_Power_Apps_and_Power_Automate)

## Known issues and limitations

As MongoDB does not enforce a schema, the current connector can be used with Power Automate and Logic Apps only, which supports dynamic schema for the API response, which can then be parsed using the "Parse JSON" constructs. It can be used in Power Apps by invoking a Power Automate flow for every MongoDB interaction. You can also continue to use the certified MongoDB connector from the [Microsoft Github repository](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/certified-connectors/MongoDB) as a Custom connector to use it in Power Apps directly to customize the Response schema as per your MongoDB collection schema.

Restrictions applicable to MongoDB Data API does apply to the MongoDB connector also. Please refer to this [link](https://www.mongodb.com/docs/atlas/app-services/mongodb/crud-and-aggregation-apis/#aggregation-pipeline-stage-availability) to know more about the aggregation stages that are not supported under User context of Data APIs.


Please follow this [link](https://www.mongodb.com/docs/atlas/api/data-api/#request-limitations) for the known limitations with the requests

## Common errors and remedies

Please follow this [link](https://www.mongodb.com/docs/atlas/api/data-api-resources/#error-codes) for common error codes and this  [link](https://www.mongodb.com/docs/atlas/api/data-api/#request-traffic) for known failure due to request traffic limitations

