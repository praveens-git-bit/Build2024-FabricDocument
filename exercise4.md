## **OPTIONAL EXERCISE**


### Exercise 4: Real-Time Intelligence experience, explore Streaming data using Copilot for KQL DB

Imagine it is 6 am on the day of Contoso's big Thanksgiving sale. Customers are flocking to their stores in large numbers. We are about to witness the very culmination of Contoso's phenomenal transformation with Microsoft Fabric and ADB. Specifically, we will see how near real-time data is used to make decisions for the next moment in Contoso's stores to ensure optimal temperatures are maintained for their customers while they shop at the big sale!

### Task 4.1: Ingest real-time/historical data into KQL DB using Eventstream

1. Click on **Workspaces** and select the **contosoSales...** workspace.

![Create Power BI Workspace.](mediaNew/task-1.1-new4.png)

Note: *If you see any pop up click on* **Don't Save.**

![Create Power BI Workspace.](mediaNew/donotsave.png)

1. While you are in the Fabric workspace homepage, click on the **experience** button on the **bottom left** of the screen and then select **Real-Time Intelligence**.

	![Close the browser.](mediaNew/Realtime-Intelligence.png)

2. On Real-Time Intelligence experience screen, click on **Eventhouse.**

Note: *Wait for the new Eventhouse to popup.*

![Close the browser.](mediaNew/eventhouse1.png)

4. Enter the name **Contoso-Eventhouse**, click on the **Create** button and wait for the database to be created.

```BASH
Contoso-Eventhouse
```
![Close the browser.](mediaNew/eventhouse2.png)

**Note:** If you see a pop-up like the one in the screenshot below, ignore it and proceed with the next step.

![Close the browser.](mediaNew/eventhouse16.png)

6. Click on **Real-Time Intelligence** at the bottom left corner of the screen and select **Real-Time Intelligence**.

   ![Close the browser.](mediaNew/Realtime-Intelligence.png)

7. Scroll down and search for **Eventstream** under **Real-Time Intelligence.**

   ![Close the browser.](mediaNew/eventhouse4.png)

9. Enter the name as **RealtimeDataTo-KQL-DB** and and tick a checkbox 'Enhanced Capabilities(preview)' click on **Create** button.

```BASH
RealtimeDataTo-KQL-DB
```

   ![Close the browser.](mediaNew/Eventst-name1.png)

10. Click on the **Add External Source** button.

   ![Close the browser.](mediaNew/task-5.2.1new1.0.3.png)

11. Click on the **Azure Event Hub** button.

   ![Close the browser.](mediaNew/task-5.2.1new1.0.4.png)

12. Under Connection Click on **New connection**.

![Close the browser.](mediaNew/eventhouse13.png)

12. To fill in the fields below we need to navigate to Azure Portal.

   ![Close the browser.](mediaNew/task-5.2.1new1.0.5.png)

13. Navigate to the **Azure Portal**. In the **rg-fabric...** resource group, search for the **event hubs namespace** and click on the **Event Hubs Namespace** resource.

   ![Close the browser.](mediaNew/task-5.2.1new1.0.6.png)

14. In the left navigation pane expand the **Entities** section, click on **Event Hubs**, and then click on the **thermostat** event hub.

   ![Close the browser.](mediaNew/task-5.2.4-2.png)

15. In the left pane expand **Settings**, click on **Shared access policies** and then click on **thermostat**.

   ![Close the browser.](mediaNew/task-5.2.4-3.png)

16. Copy the **Primary key** and paste it in a notepad for further use. 

   ![Close the browser.](mediaNew/task-5.2.5.png)

17. Go back to the **Fabric tab** on your browser.

19. Make sure you are in the **Create new connection** section, paste the below value for **Event Hub namespace** and enter the **Event Hub** value as **thermostat**.

```BASH
<inject key= "eventhubNamespace" enableCopy="true"/>
```
```BASH
thermostat
```
   ![Close the browser.](mediaNew/task-5.2.5-2.png)

20. Scroll down and select **Shared Access Key** for Authentication kind, enter **thermostat** as the Shared Access Key Name and then paste the value copied in **step 16** in the **Shared Access Key**.

```BASH
thermostat
```
![Close the browser.](mediaNew/eventhouse14.png)

21. Select Data format as **JSON** and then click on the **Next** button.

   ![Close the browser.](mediaNew/eventhouse15.png)

>**Note:** Wait for the connection to be established.

22. Click on the **Next** button.

   ![Close the browser.](mediaNew/task-5.2.1new7.png)

23. Click on the **Add** button.

   ![Close the browser.](mediaNew/task-5.2.1new8.png)

24. In the Eventstream canvas, click on the **New destination** dropdown and select **KQL Database**.

   ![Close the browser.](mediaNew/task-5.2.1new9.png)

25. Select the **Event processing before ingestion** radio button, enter **RealTimeData** as the Destination name.

```BASH
RealTimeData
```

26. Select **contosoSales...** and **Contoso-Eventhouse** from the respective 'Workspace' and 'KQL Database' dropdowns.

27. Finally click on the **Create new** button.

   ![Close the browser.](mediaNew/task-5.2.13.png)

28. Enter the table name as **thermostat** and then click on the **Done** button.

```BASH
thermostat
```
   ![Close the browser.](mediaNew/eventhouse6.png)

29. Enter the Input data format as **Json**.

Note: *Zoom-out on your screen if the Input data format field is not visible.*

   ![Close the browser.](mediaNew/eventhouse7.png)

30. Drag Arrow from 'RealtimeDataTo-KQL' and connect it to 'RealTimeData'.

![Close the browser.](mediaNew/realtimedata.png)

Note: *Wait for the data ingestion from EventHub to KQL DB.*

31. Now, click on the **Publish** button.
    
   ![Close the browser.](mediaNew/task-5.2.15.png)

Note: *Wait for the data ingestion from EventHub to KQL DB.*

32. Once you see that the streaming has started, click on Refresh and wait for the data to preview.

    ![Close the browser.](mediaNew/eventhouse17.png)

Real-time data from the event hub has been ingested successfully into the KQL Database. Next, as customers walk in aisles and the temperatures fluctuate, let us see how KQL queries proactively identify anomalies and help maintain an optimal shopping experience!

---

### Task 4.2: Analyze/discover patterns, identify anomalies and outliers using Copilot

Kusto Query Language is a powerful tool. In this scenario KQL is used to explore Contoso’s data, discover patterns, identify anomalies and outliers, create statistical modeling, and more.

We use KQL to query the thermostat data that’s streaming in near real-time from the devices installed in Contoso’s stores.

1. Click on the **Workspaces** and select **contosoSales...** workspace from left navigation pane.

![Close the browser.](mediaNew/task-5.3.1.png)

2. Click on the **Real-Time Intelligence** at the bottom left corner of the screen and select **Real-Time Intelligence**.
		
![Close the browser.](mediaNew/Realtime-Intelligence.png)

3. Select **KQL Queryset**.

![Close the browser.](mediaNew/eventhouse9.png)

4. Enter **Query Thermostat Data in Near Real-time using KQL Script** as the name and click on the **Create** button.

```BASH
Query Thermostat Data in Near Real-time using KQL Script
```

![Close the browser.](mediaNew/task-5.3.3.png)

5. **Wait** for the query set creation and a new screen will display. In this screen, click on **Contoso-Eventhouse**, verify the workspace name and then click on the **Connect** button.

![Close the browser.](mediaNew/eventhouse10.png)

6. Place your cursor inside the query field, select all using Ctrl + A and delete the pre-written query

![Close the browser.](mediaNew/task-5.3.5.png)

7. Click on the **Copilot** button.

![Close the browser.](mediaNew/task-5.3.6.png)

6. **Paste** the query provided below in the query section.

```BASH
Create a query to find average temperature every 1 min
```

7. Click on the **send** icon.

8. Click on the **Insert** button.

![Close the browser.](mediaNew/task-5.3.7.png)

9. Select the **script**, click on the **Run** button and you get the desired result.

![Close the browser.](mediaNew/task-5.3.8.png)

So, imagine if one of the aisles had a sudden rise in temperature. Customers start leaving that aisle and the wait times in the checkout lines start to increase. But thanks to the KQL Queries, those anomalies would be tracked and immediate notifications would be generated to bring the aisle temperature back to optimal levels! Now, after all these amazing data transformations in OneLake in a healthy ecosystem with Azure Databricks, can we actually predict customer churn for the future? Absolutely! In fact, in the next exercise, let’s see the power of Microsoft Fabric and Azure Databricks to do just that!

---
