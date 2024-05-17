
# **Modern Analytics with Microsoft Fabric, Copilot and Azure Databricks DREAM Lab (Lab332)**

**The estimated time to complete this lab is 45-60 minutes.**

**DISCLAIMER**

This presentation, demonstration, and demonstration model are for informational purposes only and (1) are not subject to SOC 1 and SOC 2 compliance audits, and (2) are not designed, intended or made available as a medical device(s) or as a substitute for professional medical advice, diagnosis, treatment or judgment. Microsoft makes no warranties, express or implied, in this presentation, demonstration, and demonstration model. Nothing in this presentation, demonstration, or demonstration model modifies any of the terms and conditions of Microsoft’s written and signed agreements. This is not an offer and applicable terms and the information provided are subject to revision and may be changed at any time by Microsoft.

This presentation, demonstration, and demonstration model do not give you or your organization any license to any patents, trademarks, copyrights, or other intellectual property covering the subject matter in this presentation, demonstration, and demonstration model.

The information contained in this presentation, demonstration and demonstration model represents the current view of Microsoft on the issues discussed as of the date of presentation and/or demonstration, for the duration of your access to the demonstration model. Because Microsoft must respond to changing market conditions, it should not be interpreted to be a commitment on the part of Microsoft, and Microsoft cannot guarantee the accuracy of any information presented after the date of presentation and/or demonstration and for the duration of your access to the demonstration model.

No Microsoft technology, nor any of its component technologies, including the demonstration model, is intended or made available as a substitute for the professional advice, opinion, or judgment of (1) a certified financial services professional, or (2) a certified medical professional. Partners or customers are responsible for ensuring the regulatory compliance of any solution they build using Microsoft technologies.

**Copyright**

© 2024 Microsoft Corporation. All rights reserved. 

By using this demo/lab, you agree to the following terms:

The technology/functionality described in this demo/lab is provided by Microsoft Corporation for purposes of obtaining your feedback and to provide you with a learning experience. You may only use the demo/lab to evaluate such technology features and functionality and provide feedback to Microsoft. You may not use it for any other purpose. You may not modify, copy, distribute, transmit, display, perform, reproduce, publish, license, create derivative works from, transfer, or sell this demo/lab or any portion thereof.

COPYING OR REPRODUCTION OF THE DEMO/LAB (OR ANY PORTION OF IT) TO ANY OTHER SERVER OR LOCATION FOR FURTHER REPRODUCTION OR REDISTRIBUTION IS EXPRESSLY PROHIBITED.

THIS DEMO/LAB PROVIDES CERTAIN SOFTWARE TECHNOLOGY/PRODUCT FEATURES AND FUNCTIONALITY, INCLUDING POTENTIAL NEW FEATURES AND CONCEPTS, IN A SIMULATED ENVIRONMENT WITHOUT COMPLEX SET-UP OR INSTALLATION FOR THE PURPOSE DESCRIBED ABOVE. THE TECHNOLOGY/CONCEPTS REPRESENTED IN THIS DEMO/LAB MAY NOT REPRESENT FULL FEATURE FUNCTIONALITY AND MAY NOT WORK THE WAY A FINAL VERSION MAY WORK. WE ALSO MAY NOT RELEASE A FINAL VERSION OF SUCH FEATURES OR CONCEPTS. YOUR EXPERIENCE WITH USING SUCH FEATURES AND FUNCITONALITY IN A PHYSICAL ENVIRONMENT MAY ALSO BE DIFFERENT.

## **Table of Contents**
 
### Exercise 1: Data Engineering experience, Data ingestion from a spectrum of analytical data sources into OneLake.
 
 - Task 1.1: Use the Data Pipelines/Data Flow ‘No Code-Low Code experience’

 - Task 1.2: Use the ‘New Shortcut’ option from external data sources

 - Task 1.3: Transform data using Dataflow Gen2 ‘No Code-Low Code experience’ Copilot
 

### Exercise 2: DLT Pipelines, Unity Catalog (Data governance), Metastore experience, Retrieval Augmented Generation (RAG) and Machine Learning (ML)
 
 - Task 2.1: Explore Delta Live Table pipeline (Data Transformation)
 
 - Task 2.2: Explore the data in the Azure Databricks environment with Unity Catalog (unified governance solution for data and AI)
	
 - (Optional) Task 2.3 Deploy LLM Chatbots With the Data Intelligence Platform 

 
### Exercise 3: Power BI Experience
 
- Task 3.1: Create a Semantic model and generate insights using Copilot for Power BI

**OPTIONAL EXERCISES**

### Exercise 4: Real-time Analytics experience - Explore Streaming data using Copilot for KQL DB (optional)
 
- Task 4.1: Ingest real-time/historical data into KQL DB using Eventstream
 
- Task 4.2: Analyze/discover patterns, identify anomalies and outliers using Copilot


### Exercise 5: Data Science experience - Explore Machine Learning and Business Intelligence scenarios in ADB (read only)
 
- Task 5.1: Build ML models, experiments, and log ML model in the built-in model registry using MLflow and batch scoring


### OVERVIEW

---
 ![Simulator.](mediaNew/buildarch.png)

This lab showcases Modern Analytics with Microsoft Fabric and Azure Databricks, featuring a cost-effective, performance-optimized, and cloud-native Analytics solution pattern. This architecture unifies our customers' data estate to accelerate data value creation. The visual illustrates the real-world example for Contoso, a fictitious company. Contoso is a retailer with thousands of brick-and-mortar stores across the world. They also have an online store. Contoso is acquiring Litware Inc. Litware Inc. has curated marketing data and sales data processed by Azure Databricks and stored in the gold layer in ADLS Gen 2. Contoso too has it's customer churn data stored in the gold layer in ADLS Gen 2. In the following exercises, you will see how the Contoso team leveraged the power of Microsoft Fabric to ingest data from disparate sources, combine Litware's data with their existing data from ADLS Gen2, and derive meaningful insights. You will witness how the team used a shortcut to reference the existing Litware Inc. data from ADLS Gen2. Finally, you will see the advantages of Unity Catalog for Contoso data architects to quickly get up to speed on the acquired company Litware's data. You will also see the power of creating LLM Chatbots with the Data Intelligence Platform to achieve unprecedented Market Sentiment for Contoso.

The lab scenario starts on January 30th. The company's new CEO, April, recently noticed negative trends in their KPIs, including:

- High customer churn

- Declining sales revenue

- High bounce rate on their website

- High operating expense

- Poor customer experience

- And most importantly, a low Market Sentiment

To address the high customer churn, April and the Contoso team have already decided to acquire Litware Inc. which carries products popular with millennials. April asks Rupesh, the Chief Data Officer how they could create a data driven organization and reverse these adverse KPI trends. Rupesh talks to his technical team, including Eva, the data engineer, Miguel, the data scientist and Wendy, the business analyst. Rupesh tasks them with designing and implementing a solution pattern to realize this dream of a data driven organization. Our story centers around Rupesh and his team. They recognize that the existence of data silos within Contoso's various departments presents a significant integration challenge. This challenge is further worsened by the need to combine it's subsidiary data and data from Litware Inc.

During this lab you will execute some of these steps as a part of this team to reverse these adverse KPI trends. As a first step, you will ingest data from a spectrum of data sources into OneLake for Contoso. Let's get started.
