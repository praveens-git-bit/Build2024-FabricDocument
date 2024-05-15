# Modern Analytics with Microsoft Fabric, Copilot and Azure Databricks DREAM Lab (Lab332)
 
**The estimated time to complete this lab is 45-60 minutes.**
 
## Table of Contents
 
## Exercise 1: Data Engineering experience, Data ingestion from a spectrum of analytical data sources into OneLake
 
 - Task 1.1: Use the Data Pipelines/Data Flow ‘No Code-Low Code experience’

 - Task 1.2: Use the ‘New Shortcut’ option from external data sources

 - Task 1.3: Transform data using Dataflow Gen2 ‘No Code-Low Code experience’ Copilot
 


## Exercise 2: DLT Pipelines, Unity Catalog (Data governance), Metastore experience, Retrieval Augmented Generation (RAG) and Machine Learning (ML)
 
 - Task 2.1: Explore Delta Live Table pipeline (Data Transformation)
 
 - Task 2.2: Explore the data in the Azure Databricks environment with Unity Catalog (unified governance solution for data and AI)
	
 - Task 2.3 Deploy LLM Chatbots With the Data Intelligence Platform 

 
## Exercise 3: Power BI Experience
 
- Task 3.1: Create a Semantic model and generate insights using Copilot for Power BI


## Exercise 4: Real-time Analytics experience - Explore Streaming data using Copilot for KQL DB (optional)
 
- Task 4.1: Ingest real-time/historical data into KQL DB using Eventstream
 
- Task 4.2: Analyze/discover patterns, identify anomalies and outliers using Copilot


## Exercise 5: Data Science experience - Explore Machine Learning and Business Intelligence scenarios in ADB (read only)
 
- Task 5.1: Build ML models, experiments, and log ML model in the built-in model registry using MLflow and batch scoring


## OVERVIEW

---
 ![Simulator.](mediaNew/buildarch.png)

This lab showcases Modern Analytics with Microsoft Fabric and Azure Databricks, featuring a cost-effective, performance-optimized, and cloud-native Analytics solution pattern. This architecture unifies our customers' data estate to accelerate data value creation. The visual illustrates the real-world example for Contoso, a fictitious company. Contoso is a retailer with thousands of brick-and-mortar stores across the world. They also have an online store. Contoso is acquiring Litware Inc. Litware Inc. has curated marketing data and sales data processed by Azure Databricks and stored in the gold layer in ADLS Gen 2. In the following exercises, you will see how the Contoso team leveraged the power of Microsoft Fabric to ingest data from disparate sources, combine data with their existing data from ADLS Gen2, and derive meaningful insights. You will witness how the team used a shortcut to reference the existing Litware Inc. data from ADLS Gen2. Finally, you will see the advantages of Unity Catalog and creating LLM Chatbots with the Data Intelligence Platform.

The lab scenario starts on January 30th. The company's new CEO, April, recently noticed negative trends in their KPIs, including:

- High customer churn

- Declining sales revenue

- High bounce rate on their website

- High operating expense

- Poor customer experience

April asks Rupesh, the Chief Data Officer how they could create a data driven organization and reverse these adverse KPI trends. Rupesh talks to his technical team, including Eva, the data engineer, Miguel, the data scientist and Wendy, the business analyst. Rupesh tasks them with designing and implementing a solution pattern to realize this dream of a data driven organization. Our story centers around Rupesh and his team. They recognize that the existence of data silos within Contoso's various departments presents a significant integration challenge.

During this lab you will execute some of these steps as a part of this team to reverse these adverse KPI trends.

### Exercise 1: Data Engineering experience - Data ingestion from a spectrum of analytical data sources into OneLake

*Before we start executing the steps, we will trigger the simulator app to start streaming data to eventhub.*

1. Open a Microsoft Edge browser in **InPrivate** mode. 

2. Navigate to the Azure Portal at [https://portal.azure.com/]

3. Log into the VM with the password provided in the **Resources** tab located on the right side of the screen.

4. Use these credentials to log into the Azure Portal.

>**Note:** Close the Save password pop-up box.

![Simulator.](mediaNew/task-1.1-new7.png)

5. If prompted to stay signed in, select **Yes**.

![Simulator.](mediaNew/task-1.1-new8.png)

>**Note:** If prompted to take a tour, select **Maybe later**.

![Simulator.](mediaNew/task-1.1-new9.png)

6. Search for **resource group** in the search bar at the top of the page and click on the **Resource groups** option.

![Simulator.](mediaNew/task-1.1-new.png)

7. Search for **rg-fabric** in the searchbox and click on the **resource group**. 

![Simulator.](mediaNew/task-1.1-new5.png)

8. Search for **app service** and select the app service labeled **app-realtime-simulator...**

![Simulator.](mediaNew/task-1.1.png)

9. Click on the **Browse** button and a new tab will open.

![Simulator.](mediaNew/task-1.2.png)

10. **Wait** for the page to load. The following page will appear.

![Simulator.](mediaNew/task-1.3.png)

---

### Task 1.1: Use the Data Pipelines/Data Flow ‘No Code-Low Code experience’

In this exercise, you will act as the Data Engineer and transfer Contoso's data from Azure SQL Database into the Lakehouse. 

1. Open **PowerBI** in a new tab by going to [https://app.powerbi.com].

*Click on the **Continue** button.*

   ![Sign in to Power BI.](mediaNew/task-1.1.0-new1.png)

*Type in a 10 digit number in the box.*

   ![Sign in to Power BI.](mediaNew/task-1.1.0-new2.png)

*Click on the **Get Started** button.*

   ![Sign in to Power BI.](mediaNew/task-1.1.0-new3.png)

*Again click on the **Get Started** button.*

   ![Sign in to Power BI.](mediaNew/task-1.1.0-new4.png)

*Wait for the PowerBI Workspace to load*

![Sign in to Power BI.](mediaNew/task-1.1.0-new5.png)

*Close* the top bar for a better view.

   ![Create Power BI Workspace.](mediaNew/task-1.1-new1.png)

2. In Power BI service, click on **Workspaces**.

3. Click the **+ New workspace** button.

	![Create Power BI Workspace.](mediaNew/task-1.1.2.png)

4. Type the name **contosoSales**, and append the **6 character suffix** at the end of your resource group and click **Apply**.

>**Note:** Do not include spaces in the workspace name.

   ![Create Power BI Workspace.](mediaNew/task-1.1.3.png)

*Click on the **Try free** button.*

   ![Create Power BI Workspace.](mediaNew/task-1.1-new2.png)

*Click on the **Got it** button to continue.*

   ![Create Power BI Workspace.](mediaNew/task-1.1-new3.png)

5. Click on **Workspaces** to verify if the workspace with the given name was created, if not perform the steps above again.

**NOTE:** If the workspace you created is not visible, perform **steps 3 to 5** again.

   ![Create Power BI Workspace.](mediaNew/task-1.1-new4.png)

6. In Power BI service, click **+ New** and then select **More options**.

   ![Close the browser.](mediaNew/task-1.2.1.png)

7. In the new window, under the Data Engineering section, click on **Lakehouse**.

    ![Close the browser.](mediaNew/task-1.2.2.png)

8. **Wait** for the Microsoft Fabric capacity to upgrade and then click on **OK**.

   ![Create Power BI Workspace.](mediaNew/task-1.2-new5.png)

*Wait for the New lakehouse pop-up box to appear*

9. Enter the name **lakehouse**.

10. Click the **Create** button.

    ![Close the browser.](mediaNew/task-1.2.3.png)

11. Click on **Workspaces** in the left navigation pane and select **contosoSales...**.

	![Give the name and description for the new workspace.](mediaNew/task-1.2.4.png)


12. Open a new tab on your browser and navigate to Microsoft Fabric at [https://app.fabric.microsoft.com].

13. On the Microsoft Fabric landing page, click on the **Data Factory** experience.

![Pipeline.](mediaNew/task-1.3.01.png)

14. Click on **Workspaces** and select the **contosoSales...** workspace.

![Pipeline.](mediaNew/task-1.3.02.png)

15. Click the **Data Factory** icon in the bottom left corner of the screen to select **Data Factory**.

![Pipeline.](mediaNew/task-1.3.1.png)

16. Click on **Data pipeline**.

![Pipeline.](mediaNew/task-1.3.2.png)

17. In the pop-up, type the pipeline name **Azure SQL DB Pipeline** and click on the **Create** button.

![Pipeline.](mediaNew/task-1.3.3.png)

18. In the Data pipeline window, click on **Copy data assistant**.

![Pipeline.](mediaNew/task-1.3.4.png)

19. In the pop-up, scroll down through the resources, click on **Azure SQL Database** and then click on the **Next** button.

>**Note** You may not see the **Azure SQL Database** in the same location as shown in the screenshot.

![Pipeline.](mediaNew/task-1.3.5.png)

20. Select the **Create new connection** radio button.

>**Note:** To fill in the details for required fileds, we need to fetch the data from the SQL Database resource deployed in the Azure Portal.

*Steps from here are optional. You may move to Task 1.2*

![Pipeline.](mediaNew/task-1.3.6.png)

21. Navigate to the **Azure Portal**, in the resource group **rg-fabric...**, search for **sql server** in the resource group window and click on the **mssql...** resource.

![Pipeline.](mediaNew/task-1.3.12.png)

22. Copy the **Server name**.

![Pipeline.](mediaNew/task-1.3.13.png)

23. Navigate back to the **Fabric** tab on your browser.

<todo  Do we need screenshot here to show Fabric Tab>

24. In the **Server** field, paste the value you copied in step number **11* and type **SalesDb** in the **Database** field.

![Datawarehouse.](mediaNew/task-1.3.15.png)

25. Scroll down and select **Basic** for Authentication kind, enter **labsqladmin** as the Username, **@@##$$** as the Password and click on the **Next** button.

![Datawarehouse.](mediaNew/task-1.3.16.png)

>**Note:** Close any pop-up that you see throughout the lab.
   
![Datawarehouse.](mediaNew/task-1.3.16.1.png)

>**Note:** Wait for the connection to be created.

26. Click on the **checkbox** for **Select all** and then click on the **Next** button.

![Datawarehouse.](mediaNew/task-1.3.17.png)

27. Scroll down and click on **Lakehouse**, then click on the **Next** button.

![Datawarehouse.](mediaNew/task-1.3.18.png)

28. Click on the **Existing Lakehouse** radio button, click on the **dropdown**, select **lakehouse...** and then click on the **Next** button.

![Datawarehouse.](mediaNew/task-1.3.19.png)

29. Select the **Load to new table** radio button, click on the **checkbox** beside **Source** and then click on **Next**.

![Datawarehouse.](mediaNew/task-1.3.20.png)

30. Click on **Save + Run**.

![Datawarehouse.](mediaNew/task-1.3.21.png)

31. Click on the **OK** button in the Pipeline run window.

![Datawarehouse.](mediaNew/task-1.3.21.0.png)

>**Note:** Wait for the pipeline to execute.

32. Click on the bell icon at the top right of the screen to verify the **Running status** of the pipeline.

![Datawarehouse.](mediaNew/task-1.3.22.png)

33. Your data has been transfered from Azure SQL Database to Lakehouse.

34. Similarly, you can get data into the Lakehouses using pipelines from various other sources like Snowflake, Dataverse, etc.

---

### Task 1.2: Use ‘New Shortcut’ option from external data sources

Now this is something exciting! This section shows how easy it is to create shortcuts without actually moving data. That is the power of OneLake! In this exercise, you will ingest the curated marketing and product reviews data from ADLS Gen2. 

1. In the contosoSales... workspace, click on **Filter** and select **Lakehouse**.

![Lakehouse.](mediaNew/task-1.3-ext-shortcut1.png)	

2. Click on the **lakehouse...**.

>**Note:** There are 3 options for lakehouseBronze, namely Lakehouse, Dataset (default) and SQL endpoint. Make sure you select the **Lakehouse** option.

![Lakehouse.](mediaNew/task-1.3-ext-shortcut2.png)

3. Click on the **three dots (Elipse)** on the right side of Files.

4. Click on **New shortcut**.

![Lakehouse.](mediaNew/task-1.3-ext-shortcut3.png)

5. In the pop-up window, under **External sources**, select the **Azure Data Lake Storage Gen2** source.

![Lakehouse.](mediaNew/task-1.3-ext-shortcut4.png)

>**Note:** Wait for the screen to load.

6. In the screen below, we need to enter the connection details for the ADLS Gen2 shortcut. For this, we need to get the details from the Storage Account resource.

![Lakehouse.](mediaNew/task-1.3-ext-shortcut11.png)

7. Navigate to the **Azure Portal**, in the **rg-fabric...** resource group search for **storage account** and click on the storage account resource.

![Lakehouse.](mediaNew/task-1.3-ext-shortcut5.png)

8. Expand the **Security + networking** section and click on **Access keys**.

![Lakehouse.](mediaNew/task-1.3-ext-shortcut5.2.png)

9. Click on the **Show** button under **key1**.

![Lakehouse.](mediaNew/task-1.3-ext-shortcut6.png)

10. Click on the **Copy to clickboard** button.

11. Save this information in a notepad for further use.

![Lakehouse.](mediaNew/task-1.3-ext-shortcut7.png)

12. In the left pane, expand the **Settings** section and click on **Endpoints**.

![Lakehouse.](mediaNew/task-1.3-ext-shortcut7.1.png)

13. Scroll down to copy the **Data Lake Storage** endpoint in the **Data Lake Storage** section.

14. Save the information in a notepad for further use.

>**Note:** You may see different endpoints in addtion to the ones shown in the following screen. Make sure to select **only** the **Data Lake Storage** endpoint.

![Lakehouse.](mediaNew/task-1.3-ext-shortcut8.png)

15. Navigate back to the **Fabric** tab.

16. Paste the endpoint copied in **step 13** under the **URL** field.

17. In the **Authentiation kind** dropdown, select **Account Key**.

18. Paste the **account key** copied in **step number 10**.

19. Click on **Next**.

![Lakehouse.](mediaNew/task-1.3-ext-shortcut9.png)

20. Select the **data** checkbox and click on the **Next** button.

![Lakehouse.](mediaNew/task-1.3-ext-shortcut9.1.png)

21. Click on the **Create** button.

![Lakehouse.](mediaNew/task-1.3-ext-shortcut10.png)


---

### Task 1.3: Transform data using Dataflow Gen2 ‘No Code-Low Code experience’ Copilot

In this exercise, you will experience how easy it is to use Copilot to transform sales data. 

1. Click on the **Data Factory** icon on the bottom left corner of the screen and select **Data Factory**.

![Datawarehouse.](mediaNew/task-1.3.1.png)

2. Click on **Dataflow Gen2**.

![Datawarehouse.](mediaNew/task-1.2.02.png)

3. Click on the **Get data** button.

![Datawarehouse.](mediaNew/task-1.2.03.png)

4. In the pop-up window, click on the **View more** button.

![Datawarehouse.](mediaNew/task-1.2.04.png)

5. Select **Microsoft Fabric** and then click on **Lakehouse**.

![Datawarehouse.](mediaNew/task-1.2.05.png)

6. Click on the **Next** button.

![Datawarehouse.](mediaNew/task-1.2.05.1.png)

7. Expand **Lakehouse**, **contosoSales...**, **Files** and check the **sales_data.csv** checkbox, then **click** on the **Create** button.

![Datawarehouse.](mediaNew/task-1.2.06.png)

8. Click on the **Copilot** button, paste the **prompt** provided below in the text box and click on the **send** icon.

```
Use first row as header
```

![Datawarehouse.](mediaNew/task-1.2.07.png)

9. Similarly, you can paste the following prompts in Copilot for data transformation.

```
Remove empty rows from GrossRevenue and NetRevenue column
```

>**Note:** Due to time constraints, we will not be publishing and running the Dataflow from the Pipeline.

10. Click on the **close** icon at top right of the **Dataflow** window.

![Datawarehouse.](mediaNew/task-1.2.08.png)

10. Click on **Yes**.

![Datawarehouse.](mediaNew/task-1.2.09.png)

---

### Exercise 2: Unity Catalog (data governance), Metastore experience, RAG and ML

### Task 2.1: Delta Live Table pipeline (Interactive)

1. Navigate to the **Azure Portal**, in the **rg-fabric...** resource group, search for **databricks** and click on the databricks resource with the name **adb-fabric...**.

![Databricks.](mediaNew/task-2.2.0new.png)

2. Click on the **Launch Workspace** button.

![Databricks.](mediaNew/task-2.2.1new.png)

3.	In the left navigation pane click on **Delta Live Table** 

![Databricks.](mediaNew/task-2.2.2new.png)

4. Click on the **Create pipeline** button.

![Databricks.](mediaNew/task-2.2.3.1new.png)

5. Enter the name of the pipeline as **DLT_Pipeline** and click on the file icon to browse the notebook.

![Databricks.](mediaNew/task-2.2.3new.png)

6. Click on **Shared**.

7. Click on **Analytics with ADB**.

8. Click on the **01 DLT Notebook**.

9. Click on the **Select** button.

![Databricks.](mediaNew/task-2.2.4new.png)

10. Click on the **Create** button.

![Databricks.](mediaNew/task-2.2.5new.png)

>**Note**: Due to time constraints we have pre-loaded the output tables in your Databricks. We will not be executing this pipeline.

14. The result would look similar to the following screen.

![Databricks.](mediaNew/task-2.2.7.png)

---

### Task 2.2: Explore the data in Azure Databricks environment with Unity Catalog (unified governance solution for data and AI).
	
With the acquisition of Litware Inc., Contoso had a lot of data integration and interoperability challenges. Contoso wanted to make sure that the transition was smooth and data engineers and scientists from Contoso could easily assimilate the data processed by Databricks. Thankfully, they had the help from a slew of Gen AI features right within Azure Databricks to understand and derieve insights from this data. Let's see how!
	
1.	Click on **Catalog**.

2.	Expand **litware_unity_catalog db**.

3.	Expand the **rag** schema.

4.	Click on **silver_customerChurn** table.

![Databricks.](mediaNew/task-2.1new.png)

5.	Click on **Accept** in 'AI Suggested Comment' box and Click on **AI Generate**.

![Databricks.](mediaNew/task-2.1.1new.png)
	
We can see that Databricks has autogenerated the description for the table and its columns. Users can choose to accept the descriptions or edit them further. This improves the ease of governance on this new data for Contoso. Next, let's see how easy it is to query this data.

![Databricks.](mediaNew/task-2.2new.png)
	
6.	Select the dropdown on **Create**.

7.	Click on **Query**.

![Databricks.](mediaNew/task-2.3new.png)
	
8.	Select the **Assistant** tab.

9.	Type following query in the query box: **Retrieve the average total amount of transactions for each store contract. Additionally, calculate the average total amount for customers who have churned and for those who have not churned. Ensure that all average values are rounded to the nearest whole number.**
	
![Databricks.](mediaNew/task-2.4new.png)
	
By simply using a natural language query, databricks generates an equivalet SQL query.
	
10. Click on the **Arrow** to replace the current code.

![Databricks.](mediaNew/task-2.4.1new.png)

11.	**Run** the query.

12.	Check the output.

>**Note:** Make sure Warehouse is in ready mode

![Databricks.](mediaNew/task-2.5new.png)

Users also have the capability to fix errors in queries with the AI assistant. 
	
13.	In the query, **delete** the last 2/3 letters to introduce an error.

14.	Click on **Run** to see the error.

15.	Click on **Diagnose error** to fix the query issue. 

![Databricks.](mediaNew/task-2.6new.png)
	
Data discovery is also made simple within Azure Databricks. Users can simply search for table names or the information they are looking for in the global search and all the relevant items are returned.
	
16.	Click on **Search*.

17.	Click on **Open search in a full page**.

18. Search for **campaigns** and press enter.

![Databricks.](mediaNew/task-2.7new.png)
	
---

### Task 2.3 (OPTIONAL)Deploy LLM Chatbots With the Data Intelligence Platform 

Contoso also wanted to improve their efficientcy with analyzing hundreds of documents about their big merger and their company policies. Azure Databricks provides just the solution with its Delta Lake architecture supporting unstructured data, like PDF documents, with Lang chain models leveraging Databricks Foundation Model for creating custom chatbots. Let's see how this was done.

![Databricks.](mediaNew/task-2.3.1.png)

First, let's ingest our PDFs as a Delta Lake table with path URLs and content in binary format.

1.	Go to **Unity Catalog Volumes**.

2.	Click on **documents_store**.

![Databricks.](mediaNew/task-2.3.1.a.new.png)

3.	Click on **pdf_documents**.

4.	Review the Knowledge Base (pdfs).

![Databricks.](mediaNew/task-2.3.2new.png)

We'll use Databricks Autoloader to incrementally ingeset new files, making it easy to incrementally consume large volume of files from the data lake in various data formats. Autoloader easily ingests our unstructured PDF data in binary format.

5. Click on **Workspaces**

![Databricks.](mediaNew/task-2.3.3new.png)

6. Open the notebook from the path shown in the screenshot below.

![Databricks.](mediaNew/task-2.3.3.a.new.png)

This notebook is used to convert the ingested document into delta tables. Lets look at the output tables.

7. Click on **Catalog** and under **rag** database, click on the **documents_raw** table.

![Databricks.](mediaNew/task-2.3.3.b.new.png)

8.	Click on **Sample Data**.

9.	Review the delta table.

![Databricks.](mediaNew/task-2.3.4new.png)

Next we convert the PDF documents bytes to text, extract chunks from their content, and create a vector search index for retreival.

10.	Go to table: **documents_embedding**.

![Databricks.](mediaNew/task-2.3.4.a.new.png)

11.	Click **Sample Data**.

12.	Review the Delta Table.

![Databricks.](mediaNew/task-2.3.4.b.new.png)

13.	In the upper-right corner, click on the dropdown for **Create**.

14.	Select **Vector search index**. Click on **Cancel** after reviewing the fields.

![Databricks.](mediaNew/task-2.3.6new.png)

We've just seen how Databricks Lakehouse AI makes it easy to ingest and prepare your documents and deploy a Self-Managed Vector Search index on top of it with just a few lines of code and configuration.

15. Click on **Workspace**.

16. Click on **Shared**.

17. Click on **RetrievalAugmentedGeneration**.

![Databricks.](mediaNew/task-2.3.7.a.new.png)

18. Click on notebook **3. Register and Deploy RAG model as Endpoint**.

![Databricks.](mediaNew/task-2.3.7.new.png)

With this model, we will be able to serve and accept questions based on the documents uploaded.
Everytime we send a question to the chatbot, the following steps occur:
•	The model receiv  es the question
•	The retriever automatically fetches related chunks from our documents
•	A prompt is crafted with the chunks and the question
•	The prompt is sent to the Databricks Foundation Model and Llama 2 serves an accurate answer based on the chunk information!

You will witness this in action [here](https://app-ms-build-2024-demo.azurewebsites.net/#/enterprise-chatbot).

---

### Exercise 3: Power BI Experience
 
### Task 3.1: Create Semantic model and generate insights using Copilot for Power BI

Let us dive deep into the experience of the Business analyst, Wendy. Based on all the gathered data Wendy is expected to create Power BI reports for other data citizens and stakeholders. Let us see the power of Power BI copilot in conjuction with the Direct Lake Mode.

1. Navigate to the Fabric Workspace. 

   ![Pipeline.](mediaNew/task-1.3.02.png)

2. In the **contosoSales...** workspace, click on **Filter** and select **Lakehouse**.

   ![Lakehouse.](mediaNew/task-1.3-ext-shortcut1.png)	

3. Click on the **lakehouse...**.

>**Note:** There are 3 options for lakehouseBronze, namely Lakehouse, Dataset (default) and SQL endpoint. Make sure you select the **Lakehouse** option.

   ![Lakehouse.](mediaNew/task-1.3-ext-shortcut2.png)

>**Note:** In case you do not see the 'website_bounce_rate' under the Tables section of the lakehouse, follow the below steps.

   -  Click on **data**.

      ![Simulator.](mediaNew/task-new1.png)

   - Click on the **ellipse**(three icons) in front of **website_bounce_rate.csv**, select **Load to Tables** and then select **New Table**.

      ![Simulator.](mediaNew/task-new2.png)

   - In the pop-up verify the **New table name** and then click on the **Load** button.

      ![alt text](mediaNew/task-new3.png)


*Once the **website_bounce_rate** delta table is there, we can proceed with the steps ahead*

4. Click on the **New semantic model**. 

   ![Simulator.](mediaNew/task-new4.png)

5. Enter **website_bounce_rate_model** in the Name field. 

6. Select workspace as **contosoSales...** and scroll down.

   ![Simulator.](mediaNew/task-new5.png)

7. Select **website_bounce_rate** table and click on the **Confirm** button. 

   ![Simulator.](mediaNew/task-new6.png)

>Wait for the semantic model creation.

8. To create a new report using this semantic model, click on the **New Report** at the top bar.
 
   ![Simulator.](mediaNew/task-new7.png)

9. Click on the **Copilot** icon, collapse all the other three panes and then click on the **Get started** button.

   ![Simulator.](mediaNew/task-new8.png)
	
10. Click on the **Prompt Guide** button.  

11. Select the option **What's in my dataset?**.
   
      ![Simulator.](mediaNew/task-new9.png)

The first option, “What’s in my dataset?’ provides an overview of the contents of the dataset. It identifies and describes what the datasets and attributes are all about and provides a concise detail of the content. The business analyst does not need to wait for someone to explain the dataset to her. This improves the efficiency and volume of report creation for Contoso.

12. Click on the **Prompt Guide** button. 

13. Select the option **Suggest content for this page**. 

      ![Simulator.](mediaNew/task-new10.png)
	
The copilot can not only describe the dataset, but it can also recomment the kind of reports that could be created using this data.

14. Click on the **Customer** related suggested insight as shown in step 1 of the screenshot **Customer Behavior Insights** 

>The Customer insight for you might differ from the screenshot.

15. Click on the **Edit** button as shown in step 2 of the screenshot.  

   ![Simulator.](mediaNew/task-new11.png)

16. Replace the prompt with following: **Create a report Bounce Rate analysis, to show the correlation between customer sentiment, particularly among millennials and Gen Z, unsuccessful product searches across different devices, and the website's bounce rate by customer generations**.  

17. Click on the **Send** button and wait for the results to load. 

      ![Simulator.](mediaNew/task-new12.png)
	
>**Note:** If you see the error message saying, 'Something went wrong.', try refreshing the page and restart the task. Being in a shared environment, the service may be busy at times.

Based on this report, we notice that the website bounce rate for Contoso is especially high amongst the Millenial customer segment. How about we ask Copilot if it has any recommendations for improving this bounce rate.

Let's ask Copilot for suggestions based on the results and data in the report. 

18. Enter the following prompt in Copilot, **Based on the data in the report, what can be done to improve the bounce rate of millennials?** and press **Send** button.
	
      ![Simulator.](mediaNew/task-new13.png)
	
19. Observe the suggestions provided by Copilot. 
	
      ![Simulator.](mediaNew/task-new14.png)
	
20. Expand the **Visualizations** pane and select the **Narratives** visual. 

21. Click on **Copilot (preview)** within the visual.

      ![Simulator.](mediaNew/task-new15.png)
	
22. Select **Give an executive summary**. 

23. Click on **Update** and observe the generated summary. 
 
      ![Simulator.](mediaNew/task-new16.png)
	
The summary could also be generated in another language if specified. The summary is also updated if you filter the report on any particular visual. How cool is that!

---

### Exercise 4: Real-time Analytics experience, explore Streaming data using Copilot for KQL DB

Imagine it is 6 am on the day of Contoso's big Thanksgiving sale. Customers are flocking to their stores in large numbers. We are about to witness the very culmination of Contoso's phonomenal transformation with Microsoft Fabric and ADB. Specifically, we will see how near real-time data is used to make decisions for the next moment in Contoso's stores to ensure optimal temperatures are maintained for their customers while they shop at the big sale! Let's see how! 

### Task 4.1: Ingest real-time/historical data into KQL DB using Eventstream

1. While you are in the Fabric workspace homepage, click on **+ New** and then click on **More options**.

	![Close the browser.](mediaNew/task-1.2.1.png)

2. In the new window, scroll down to the **Real-Time Analytics** section and click on **KQL Database**.

	![Close the browser.](mediaNew/task-5.1.3.png)

3. Enter the name **Contoso-KQL-DB**, click on the **Create** button and wait for the database to be created.

	![Close the browser.](mediaNew/task-5.1.4.png)

4. Click on the **contosoSales** workspace from left navigation pane.

   ![Close the browser.](mediaNew/task-5.2.1new1.png)

5. Click on the **+ New** button.

   ![Close the browser.](mediaNew/task-5.2.1new1.0.png)

6. Select **Eventstream**.

   ![Close the browser.](mediaNew/task-5.2.1new1.0.1.png)

7. Enter the name as **RealtimeDataTo-KQL-DB** and click on **Create** button.

   ![Close the browser.](mediaNew/task-5.2.1new1.0.2.png)

8. Click on the **Add Source** button.

   ![Close the browser.](mediaNew/task-5.2.1new1.0.3.png)

9. Click on the **Azure Event Hub** button.

   ![Close the browser.](mediaNew/task-5.2.1new1.0.4.png)

10. To fill in the fields below we need to navigate to Azure Portal.

   ![Close the browser.](mediaNew/task-5.2.1new1.0.5.png)

11. Navigate to the **Azure Portal**. In the **rg-fabric...** resource group, search for the **event hubs namespace** and click on the **Event Hubs Namespace** resource.

   ![Close the browser.](mediaNew/task-5.2.1new1.0.6.png)

12. Copy the name of the **Event Hub namespace** and paste it in a notepad for further use.

   ![Close the browser.](mediaNew/task-5.2.1new1.0.7.png)

13. In the left navigation pane expand the **Entities** section, click on **Event Hubs**, and then click on the **thermostat** event hub.

   ![Close the browser.](mediaNew/task-5.2.4-2.png)

14. In the left pane expand **Settings**, click on **Shared access policies** and then click on **thermostat**.

   ![Close the browser.](mediaNew/task-5.2.4-3.png)

15. Copy the **Primary key** and paste it in a notepad for further use. 

   ![Close the browser.](mediaNew/task-5.2.5.png)

16. Go back to the **Fabric tab** on your browser.

17. Make sure you are in the **Create new connection** section, paste the value for **Event Hub namespace** from **step 9** and enter the **Event Hub** value as **thermostat**.

   ![Close the browser.](mediaNew/task-5.2.5-2.png)

18. Scroll down and select **Shared Access Key** for Authentication kind, enter **thermostat** as the Shared Access Key Name and then paste the value copied in **step 12** in the **Shared Access Key**.

19. Select Data format as **JSON** and then click on the **Connect** button.

   ![Close the browser.](mediaNew/task-5.2.5-3.png)

>**Note:** Wait for the connection to be established.

20. Click on the **Next** button.

   ![Close the browser.](mediaNew/task-5.2.1new7.png)

21. Click on the **Add** button.

   ![Close the browser.](mediaNew/task-5.2.1new8.png)

22. In the Eventstream canvas, click on the **New destination** dropdown and select **KQL Database**.

   ![Close the browser.](mediaNew/task-5.2.1new9.png)

23. Select the **Event processing before ingestion** radio button, enter **RealTimeData** as the Destination name.

24. Select **contosoSales...** and **Contoso-KQL-DB** from the respective 'Workspace' and 'KQL Database' dropdowns.

25. Finally click on the **Create new** button.

   ![Close the browser.](mediaNew/task-5.2.12.png)

26. Enter the table name as **thermostat** and then click on the **Done** button.

   ![Close the browser.](mediaNew/task-5.2.13.png)

27. Enter the Input data format as **Json**.

   ![Close the browser.](mediaNew/task-5.2.14.png)

28. Click on the **Publish** button.

   ![Close the browser.](mediaNew/task-5.2.15.png)

Real-time data from the event hub has been ingested successfully into the KQL Database.

---

### Task 4.2: Analyze/discover patterns, identify anomalies and outliers using Copilot

Kusto Query Language is a powerful tool. In this scenario KQL is used to explore Contoso’s data, discover patterns, identify anomalies and outliers, create statistical modeling, and more.

We use KQL to query the thermostat data that’s streaming in near real-time from the devices installed in Contoso’s stores.

1. Click on the **Workspaces** and select **contosoSales...** workspace from left navigation pane.

![Close the browser.](mediaNew/task-5.3.1.png)

2. Click on the **+ New** button.
		
![Close the browser.](mediaNew/task-5.3.2.png)

3. Select **KQL Queryset**.

![Close the browser.](mediaNew/task-5.3.2.png)

4. Enter **Query Thermostat Data in Near Real-time using KQL Script** as the name and click on the **Create** button.

![Close the browser.](mediaNew/task-5.3.3.png)

5. **Wait** for the query set creation and a new screen will display. In this screen, click on **Contoso-KQL-DB**, verify the workspace name and then click on the **Select** button.

![Close the browser.](mediaNew/task-5.3.4.png)

6. Select all using **Ctrl + A** and **delete** the pre-written query.

![Close the browser.](mediaNew/task-5.3.5.png)

7. Click on the **Copilot** button.

![Close the browser.](mediaNew/task-5.3.6.png)

6. **Paste** the query provided below in the query section.

```
What is the average temperature every 1 min?
```

7. Click on the **send** icon.

8. Click on the **Insert** button.

![Close the browser.](mediaNew/task-5.3.7.png)

9. Select the **script**, click on the **Run** button and you get the desired result.

![Close the browser.](mediaNew/task-5.3.8.png)

*Similarly you can use the below prompts*

```
Are there any anomalies for this device?
```

---

### Exercise 5: Data Science experience, explore Machine Learning and Business Intelligence scenarios in ADB (read only)
 
So, we saw how Contoso combined historical gold layer data from ADLS Gen2 with all OneLake data via shortcuts. Additionally, we saw how all that data could be easily accessed in Azure Databricks (thanks to the standard delta parquet format). Delta live tables were created in Azure Databricks for further curation of data. Contoso can now leverage the power of machine learning models in ADB on that data to gain meaningful insights and predict customer churn. Let's explore the Data Science Experience in Azure Databricks as Data Scientists!

### Task 5.1: Build ML models, experiments, and log ML model in the built-in model registry using MLflow and batch scoring

The architecture diagram shown here illustrates the end-to-end MLOps pipeline using the Azure Databricks managed MLflow.

After multiple iterations with various hyperparameters, the best performing model is registered in the Databricks MLflow model registry. Then it is set up as the model serving in the Azure Databricks Workspace for low latency requests.
	
![Close the browser.](mediaNew/task-3.1.1.png)

1. Navigate back to the **Databricks workspace** we started for the previous exercise.

2. In the left navigation pane, select **Workspace** and click **Workspace** again. Select **Shared**, click on **Analytics with ADB** and finally click on the **03 ML Solutions in a Box.ipynb** notebook.

![Close the browser.](mediaNew/task-3.1.2.png)

Now that we've ingested and processed our customer data, we want to understand what makes one customer more likely to churn than another, so we want to see if we can produce a machine learning model that can accurately predict if a particular customer will churn.

Ultimately, we would like to understand our customers' sentiment so we can create targeted campaigns to improve our sales.

3. Navigate to **cmd 10**.

With the data prepared, we can begin exploring the patterns it contains. 

Let's start by examining the customer churn outcome based on factors like a customer's tenure in months and their total amount spent at Contoso. As a result, we can see a high churn rate is seen if the customer's tenure is low, and they have a lower spend amount.

![Close the browser.](mediaNew/task-3.1.4.png)

4. Navigate to **cmd 20**.

5. Navigate to **cmd 21**. 

![Close the browser.](mediaNew/task-3.1.5.png)

By registering this model in Model Registry, we can easily reference the model from anywhere within Databricks.    

6. Review the **cmd 29** cell.

Let’s look at the comparison of multiple runs in the UI.

You can visualize the different runs using a parallel coordinates plot, which shows the impact of different parameter values on a metric.

The best ML model for Customer Churn is selected and registered with Databricks model registry.

![Close the browser.](mediaNew/task-3.1.6.png)

7. Navigate to **cmd 38**.

For low-latency use cases, you can use MLflow to deploy the model for online serving. The serving system loads the Production model version from the Model Registry. 

![Close the browser.](mediaNew/task-3.1.7.png)

8. Navigate to **cmd 40**.

It is then used to predict the probability of Customer Churn using the deployed model and this model endpoint is ready for production.

![Close the browser.](mediaNew/task-3.1.8.png)

9. Navigate to **cmd 41**. 

Once we have the predicted data, it is stored back in delta tables in the gold layer back in OneLake.

![Close the browser.](mediaNew/task-3.1.9.png)	

---

Congratulations! You as Data Engineers have helped Contoso gain actionable insights from its disparate data sources, thereby contributing to future growth, customer satisfaction, and a competitive advantage.

In this lab we experienced the creation of a simple integrated, open and governed Data Lakehouse foundation using Modern Analytics with Microsoft Fabric and Azure Databricks.

In this lab we covered the following:

First, we explored the Data Engineering experience and learned how to create a Microsoft Fabric enabled workspace, build a Lakehouse, and ingest data into OneLake along with other data engineering operations with dataflow copilot.

Second, we explored an analytics pipeline using open Delta format and Azure Databricks Delta Live Tables to build a simple Lakehouse and integrate with OneLake with shortcuts.

Third, we explored data governance and generative AI features in Azure Databricks with Unity Catalog. We also explored ML and BI scenarios on the Lakehouse. Here we reviewed MLOps pipeline using the Azure Databricks managed MLflow with Azure ML.

Fourth, we the Power BI experience in Fabric with copilot and direct lake mode.

Fifth, we explored Streaming data using KQL DB for a Real-time Analytics experience. Here, we created a KQL Database, ingested real-time and historical data into KQL DB, analyzed patterns to uncover anomalies and outliers with the help of copilot.

Finally, we leveraged Power BI to derive actionable insights from data in the Lakehouse using Direct Lake mode.


