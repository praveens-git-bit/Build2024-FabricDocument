
### Exercise 3: Power BI Experience
 
### Task 3.1: Create Semantic model and generate insights using Copilot for Power BI  in Microsoft Fabric

With the wide spectrum data sources as well as Litware's data in OneLake, it is now time to get some awesome insights and visualizations from this data. So, let's dive deep into the experience of the Business Analyst, Wendy, for just that. Based on all the gathered data, Wendy is expected to create Power BI reports for other data citizens and stakeholders. Let's step into her shoes to experience the power of Copilot for Power BI in conjunction with Direct Lake Mode.

1. Navigate back to the Microsoft Fabric tab on your browser.

2. Click on Workspaces and select contosoSales…

![Pipeline.](mediaNew/task-1.1-new4.png)

3. In the **contosoSales...** workspace, click on **Filter** and select **Lakehouse**.

   ![Lakehouse.](mediaNew/task-1.3-ext-shortcut1.png)	

3. Click on the **lakehouse...**.

>**Note:** There are 3 options for lakehouse, namely Lakehouse, Dataset (default) and SQL endpoint. Make sure you select the type **Lakehouse** option.

   ![Lakehouse.](mediaNew/task-1.3-ext-shortcut2.png)

>**Note:** In case you do not see the **'website_bounce_rate'** under the **Tables** section of the lakehouse, follow the below steps from **a to c**. If you are able to see it, please continue with step 4.

a. Click on **data**.

![Simulator.](mediaNew/task-new1.png)

b. Click on the **ellipse**(three icons) in front of **website_bounce_rate.csv**, select **Load to Tables** and then select **New Table**.

![Simulator.](mediaNew/task-new2.png)

c. In the pop-up verify the **New table name** and then click on the **Load** button.

![alt text](mediaNew/task-new3.png)


*Once the **website_bounce_rate** delta table is there, we can proceed with the steps ahead*

4. Click on the **New semantic model**.

Note: *wait for new semantic model page to popup.*

   ![Simulator.](mediaNew/task-new4.png)

6. Enter **website_bounce_rate_model** in the Name field.

```BASH
website_bounce_rate_model
```

7. Select workspace as **contosoSales...** and scroll down.

   ![Simulator.](mediaNew/task-new5.png)

8. Select **website_bounce_rate** table and click on the **Confirm** button. 

   ![Simulator.](mediaNew/task-new6.png)

>Wait for the semantic model creation.

8. To create a new report using this semantic model, click on the **New Report** at the top bar.
 
   ![Simulator.](mediaNew/task-new7.png)

Note: Close any pop-up which apears on the screen.

 ![Simulator.](mediaNew/coplitclose.png)

9. Click on the **Get started** button. You will now see how easy it is for the data analyst to create compelling Power BI reports and get deep insights with literally no hands-on coding!

   ![Simulator.](mediaNew/task-new8.png)
	
10. Click on the **Prompt Guide** button.  

11. Select the option **What's in my data?**.
   
      ![Simulator.](mediaNew/task-new9.png)

The first option, 'What’s in my data?' provides an overview of the contents of the dataset. It identifies and describes what the datasets and attributes are all about and provides a concise summary of the content. So, there’s no need to wait for someone to explain the dataset. This improves the efficiency and volume of report creation for Contoso.

16. Enter the below prompt.
 
```BASH
Create a report Bounce Rate analysis, to show the correlation between customer sentiment, particularly among millennials and Gen Z, unsuccessful product searches across different devices, and the website's bounce rate by customer generations.  
```
Note: *Wait for the prompt to populate.*

17. Click on the **Send** button and wait for the results to load. 

      ![Simulator.](mediaNew/task-new12.png)
	
>**Note:** If you see the error message saying, 'Something went wrong.', try refreshing the page and restart the task. Being in a shared environment, the service may be busy at times.

>**Note:** The responses from Copilot may not match the ones in the screenshot but will provide a similar response.

Based on this report, we notice that the website bounce rate for Contoso is especially high amongst the Millennial customer segment. Let’s ask Copilot if it has any recommendations for improving this bounce rate.

We’ll ask Copilot for suggestions based on the results and data in the report.

18. Enter the below prompt in Copilot, and press **Send** button.

```BASH
Based on the data in the report, what can be done to improve the bounce rate of millennials?
```
![Simulator.](mediaNew/task-new13.png)
	
20. Observe the suggestions provided by Copilot. So, you see copilot creates the desired Power BI report and even goes a step further to give powerful insights. How cool is that? Wendy realizes that in order for the website bounce rate to improve, Contoso needs to transform their mobile website experience for millennials. And this helps them reduce their millennial related customer churn too! Now, what if Contoso’s leadership team needed a quick summary of this entire report? All good, let’s see the SmartNarratives feature in action!
	
      ![Simulator.](mediaNew/task-new14.png)
	
21. Expand the **Visualizations** pane and select the **Narratives** visual. 

![Simulator.](mediaNew/visualizations.png)

22. Click on **Copilot (preview)** within the visual.

      ![Simulator.](mediaNew/open-narrative.png)
	
23. Select **Give an executive summary**. 

24. Click on **Update** and observe the generated summary. See how easy it was to get an executive summary? And all this with absolutely no IT resource dependency!
 
      ![Simulator.](mediaNew/task-new16.png)

25. Expand the narrative from the corner to get a better readable view of the result.
    
![Simulator.](mediaNew/expand-arrow.png)

27. Click on close button in the above near **Create a narrative with copilot.**

![Simulator.](mediaNew/close-copilot.png)
     
The summary could also be generated in another language if specified. Additionally, the summary updates if you filter the report on any visual. How cool is that?

---
