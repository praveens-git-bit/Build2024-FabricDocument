
### Exercise 1: Data Engineering experience - Data ingestion from a spectrum of analytical data sources into OneLake

*Before we start executing the steps, we will trigger the simulator app to start streaming data to eventhub.*

1. Copy the below URL and paste it in the browser to get the streaming started.
```BASH
   <inject key= "WebAppBrowse" enableCopy="true"/>
```
2. **Wait** for the page to load. The following page will appear.

![Simulator.](mediaNew/task-1.3.png)

---

### Task 1.1: Use the Data Pipelines/Data Flow ‘No Code-Low Code experience’

In this exercise, you will act as the Data Engineer and transfer Contoso's data from Azure SQL Database into the Lakehouse. 

1. Open **PowerBI** in a new tab by going to 

```BASH
https://app.powerbi.com
```

*Close* the top bar for a better view.

   ![Create Power BI Workspace.](mediaNew/task-1.1-new1.png)

2. In Power BI service, click on **Workspaces**.

3. Click the **+ New workspace** button.

	![Create Power BI Workspace.](mediaNew/task-1.1.2.png)

4. Copy paste the name of the **Workspace** in the name field and click **Apply**.

```BASH
   <inject key= "WorkspaceName" enableCopy="true"/>
```
   ![Create Power BI Workspace.](mediaNew/task-1.1.3.png)


5. Click on **Workspaces** to verify if the workspace with the given name was created, if not perform the steps above again.

**NOTE:** If the workspace you created is not visible, perform **steps 3 to 5** again.

   ![Create Power BI Workspace.](mediaNew/task-1.1-new4.png)

6. In Power BI service, click **+ New** and then select **More options**.

   ![Close the browser.](mediaNew/task-1.2.1.png)

7. In the new window, under the Data Engineering section, click on **Lakehouse**.

    ![Close the browser.](mediaNew/task-1.2.2.png)

*Wait for the New lakehouse pop-up box to appear*

9. Enter the name **lakehouse**.

```BASH
   <inject key= "lakehouseName" enableCopy="true"/>
```

10. Click the **Create** button.

    ![Close the browser.](mediaNew/task-1.2.3.png)

11. Open a new tab on your browser and navigate to Microsoft Fabric at 
```BASH
https://app.fabric.microsoft.com
```
**Note**: If you are seeing "Enter your email, we'll check if you need to create a new account" please provide the email ID you provided to signin into Azure.

```BASH
<inject key= "AzureAdUserEmail" enableCopy="true"/>
```

12. On the Microsoft Fabric landing page, click on the **Data Factory** experience.

![Pipeline.](mediaNew/task-1.3.01.png)

13. Click on **Workspaces** and select the **contosoSales...** workspace.

![Create Power BI Workspace.](mediaNew/task-1.1-new4.png)

14. Click the **Data Factory** icon in the bottom left corner of the screen to select **Data Factory**.

![Pipeline.](mediaNew/task-1.3.1.png)

15. Click on **Data pipeline**.

![Pipeline.](mediaNew/task-1.3.2.png)

*Wait for the New pipeline pop-up box to appear*

16. In the pop-up, type the pipeline name **Azure SQL DB Pipeline** and click on the **Create** button.

```BASH
Azure SQL DB Pipeline
```

![Pipeline.](mediaNew/task-1.3.3.png)

17. In the Data pipeline window, click on **Copy data assistant**.

![Pipeline.](mediaNew/task-1.3.4.png)

18. In the pop-up, scroll down through the resources, click on **Azure SQL Database** and then click on the **Next** button.

>**Note** You may not see the **Azure SQL Database** in the same location as shown in the screenshot.

![Pipeline.](mediaNew/task-1.3.5.png)

19. Select the **Create new connection** radio button.

>**Note:** To fill in the details for required fields, we need to fetch the data from the SQL Database resource deployed in the Azure Portal, due to the time constrain we have provided the details below.

![Pipeline.](mediaNew/task-1.3.6.png)


20. In the **Server** field, paste the value from the below.
```BASH
 <inject key= "MssqlServer" enableCopy="true"/>
```

21. Enter **SalesDb** in the **Database** field.

```BASH
SalesDb
```
![Datawarehouse.](mediaNew/task-1.3.15.png)

22. Scroll down and select **Basic** for Authentication kind, enter **labsqladmin** as the Username, **Smoothie@2024** as the Password and click on the **Next** button.

```BASH
labsqladmin
```
```BASH
Smoothie@2024
```
![Datawarehouse.](mediaNew/task-1.3.16.png)

>**Note:** Close any pop-up that you see throughout the lab.
   
![Datawarehouse.](mediaNew/task-1.3.16.1.png)


23. Click on the **checkbox** for **Select all** and then click on the **Next** button.

![Datawarehouse.](mediaNew/task-1.3.17.png)

Note: *Wait for the source to be appeared.*

27. Scroll down and click on **Lakehouse**, then click on the **Next** button.

![Datawarehouse.](mediaNew/task-1.3.18.png)

28. Click on the **Existing Lakehouse** radio button, click on the **dropdown**, select **lakehouse...** and then click on the **Next** button.

![Datawarehouse.](mediaNew/task-1.3.19.png)

Note: *Wait for the source to be appeared.*

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

>**Note:** There are 3 options for lakehouse, namely Lakehouse, Dataset (default) and SQL endpoint. Make sure you select the **Lakehouse** option.

![Lakehouse.](mediaNew/task-1.3-ext-shortcut2.png)

>**Note:** When you enter into the lakehouse, if you are seeing the folder called undefined under tables refresh by clicking on the **three dot (Elipse)** 

![Lakehouse.](mediaNew/task-1note.png)

3. Click on the **three dots (Elipse)** on the right side of Files.

4. Click on **New shortcut**.

![Lakehouse.](mediaNew/task-1.3-ext-shortcut3.png)

5. In the pop-up window, under **External sources**, select the **Azure Data Lake Storage Gen2** source.

![Lakehouse.](mediaNew/task-1.3-ext-shortcut4.png)

>**Note:** Wait for the screen to load.

6. In the screen below, we need to enter the connection details for the ADLS Gen2 shortcut. For this, we need to get the details from the Storage Account resource.

![Lakehouse.](mediaNew/task-1.3-ext-shortcut11.png)

7. Navigate to the **Azure Portal** search for **resource group** in the search bar at the top of the page and click on the **Resource groups** option.

![Simulator.](mediaNew/task-1.1-new.png)

7. Search for **rg-fabric** in the searchbox and click on the **resource group**. 

![Simulator.](mediaNew/task-1.1-new5.png)

7. In the **rg-fabric...** resource group search for **storage account** and click on the storage account resource.

![Lakehouse.](mediaNew/task-1.3-ext-shortcut5.png)

**Note**: Due the the screen size of VM, user will not able to see left navigation bar, please click on the "Hamburger sign* from the above to navigate to the **Security + Networking** and click on the expand button.

8. Expand the **Security + networking** section and click on **Access keys**.

![Lakehouse.](mediaNew/task-1.3-ext-shortcut5.2.png)

9. Click on the **Show** button under **key1**.

![Lakehouse.](mediaNew/task-1.3-ext-shortcut6.png)

10. Click on the **Copy to clickboard** button.

11. Save this information in a notepad for further use.

![Lakehouse.](mediaNew/task-1.3-ext-shortcut7.png)


15. Navigate back to the **Fabric** tab.

16. Enter the endpoint provided below under the **URL** field.
```BASH
 <inject key= "StorageEndpoint" enableCopy="true"/>
```
17. In the **Authentiation kind** dropdown, select **Account Key**.

18. Paste the **account key** copied in **step number 10**.

19. Click on **Next**.

![Lakehouse.](mediaNew/task-1.3-ext-shortcut9.png)

20. Select the **data** checkbox and click on the **Next** button.

![Lakehouse.](mediaNew/task-1.3-ext-shortcut9.1.png)

21. Click on the **Create** button.

![Lakehouse.](mediaNew/task-1.3-ext-shortcut10.png)

22. Click on the newly created shortcut named data.

![Lakehouse.](mediaNew/task-wb7.png)

23. Scroll down in the **middle of the screen**, click on the **three dots (Elipse)** on the right side of **website_bounce_rate.csv**.

24. Click on **Load to Tables** and select **New table**.

![Lakehouse.](mediaNew/task-wb8.png)

25. In the pop-up verify the **New table name** and then click on the **Load** button.

![alt text](mediaNew/task-new3.png)

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

**Note**: User might see a popup page of datasource to select, and might not able to see any option, please click on next to continue with the lakehouse connection.

6. Click on the **Next** button.

![Datawarehouse.](mediaNew/task-1.2.05.1.png)

7. Expand **Lakehouse** > **contosoSales...** > **Lakehouse...** > **Files** > **data** and check the **sales_data.csv** checkbox, then **click** on the **Create** button.

![Datawarehouse.](mediaNew/task-1.2.06.png)

8. Click on the **Copilot** button, paste the **prompt** provided below in the text box and click on the **send** icon.

```BASH
Use first row as header in sales_data table
```

![Datawarehouse.](mediaNew/task-1.2.07.png)

9. Similarly, you can paste the following prompts in Copilot for data transformation.

```BASH
Remove empty rows from GrossRevenue and NetRevenue column from sales_data table
```

>**Note:** Due to time constraints, we will not be publishing and running the Dataflow from the Pipeline.

10. Click on the **close** icon at top right of the **Dataflow** window.

![Datawarehouse.](mediaNew/task-1.2.08.png)

10. Click on **Yes**.

![Datawarehouse.](mediaNew/task-1.2.09.png)

---
