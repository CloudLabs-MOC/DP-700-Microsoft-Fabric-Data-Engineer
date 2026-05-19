# Lab 01: Monitor Fabric activity in the monitoring hub

### Estimated Duration: 45 Minutes

The *monitoring hub* in Microsoft Fabric provides a central place where you can monitor activity. You can use the monitoring hub to review events related to items you have permission to view.

In this hands-on lab, you will explore how to monitor activities in Microsoft Fabric using the monitoring hub. You will create and run different Fabric artifacts like lakehouses, dataflows, and notebooks, and learn how to track and review their execution history. Additionally, you will practice customizing views in the monitoring hub to effectively manage large volumes of activity logs.

## Lab Objectives

In this lab, you will complete the following tasks:

- Task 1: Create a lakehouse

- Task 2: Create and monitor a Dataflow

- Task 3: Create and monitor a Spark notebook

- Task 4: Monitor history for an item

- Task 5: Customize monitoring hub views

## Task 1: Create a lakehouse

In this task, you will create a lakehouse in your Microsoft Fabric workspace. 

1. Return to your workspace and click the **+ New item (1)** icon.  

1. On the **All items** page, scroll down to the **Store data** section and select **Lakehouse (2)**.  

   ![Screenshot of uploaded files in a lakehouse.](./Images/l4-05-l6.png)  

1. Provide the following details to create a **Lakehouse**:  

    - **Name:** Enter **lakehouse<inject key="DeploymentID" enableCopy="false"/> (1)**  

    - Make sure the **Lakehouse schemas** option is **disabled (2)**. 

    - Click **Create (3)** to proceed.

      ![Screenshot of uploaded files in a lakehouse.](./Images/l4-05-l7.png)     

1. View the new lakehouse, and note that the **Lakehouse explorer** pane on the left enables you to browse tables and files in the lakehouse:

    - The **Tables** folder contains tables that you can query using SQL semantics. Tables in a Microsoft Fabric lakehouse are based on the open source *Delta Lake* file format, commonly used in Apache Spark.

    - The **Files** folder contains data files in the OneLake storage for the lakehouse that aren't associated with managed delta tables. You can also create *shortcuts* in this folder to reference data that is stored externally.

      ![Screenshot of uploaded files in a lakehouse.](./Images/l4-05-l8.png)

      >**Note**: Currently, there are no tables or files in the lakehouse.

## Task 2: Create and monitor a Dataflow

In Microsoft Fabric, you can use a Dataflow (Gen2) to ingest data from a wide range of sources. In this exercise, you'll use a dataflow to get data from a CSV file and load it into a table in your lakehouse.

In this task, you will create a Dataflow Gen2 to ingest data from a CSV file into the lakehouse. You will publish the dataflow and monitor its execution status using the monitoring hub.

1. On the **Home** page for your lakehouse, in the **Get data in your lakehouse** menu, select **New Dataflow Gen2**.

   ![](./Images/l5-05-l1.png)

1. Enter **Get Product Data** **(1)** in the **Name** field, and then click **Create** **(2)**.

    ![Screenshot of a new dataflow.](./Images/l5-05-l2.png)

1. In the dataflow designer, select **Import from a Text/CSV file**.

   ![](./Images/l5-05-l3.png)

1. Then complete the Get Data wizard to create a data connection by linking to `https://raw.githubusercontent.com/MicrosoftLearning/dp-data/main/products.csv` **(1)** using anonymous authentication and then click **Next (2)**.

    ![Screenshot of a new dataflow.](./Images/lab5u2.png)

1. When you have completed the wizard, a preview of the data will be shown in the dataflow designer like below and click on **Create**.

    ![Screenshot of a new dataflow.](./Images/mod5-p3t1p1(2).png)

1. Click on dorp-down arrow **(1)** then **Save and run (2)** option to save and run the dataflow, then close it.

    ![](./Images/dpm9.png)

1. In the navigation bar on the left, select **Monitor** to view the monitoring hub and observe that your dataflow is in-progress (if not, refresh the view until you see it).

    ![Screenshot of the monitoring hub with a dataflow in-progress.](./Images/lab5u5.png)

1. Wait for a few seconds, and then **refresh** the page until the status of the dataflow is **Succeeded**.

    ![](./Images/dpm10.png)

1. In the navigation pane, select your **lakehouse**. Then expand the **Tables** folder to verify that a table named **products** has been created and loaded by the dataflow (you may need to refresh the **Tables** folder).

    ![Screenshot of the products table in the lakehouse page.](./Images/lab5u6.png)

    >**Note:** It may take few minutes for the products table to get reflected inside Tables.

## Task 3: Create and monitor a Spark notebook

In this task, you will use a Spark notebook to query the ingested data from the lakehouse. You will run Spark code, stop the session, and monitor the notebook’s execution through the monitoring hub.

1. In the lakehouse interface, Select **Open notebook (1)**, then choose **New notebook (2)** to create a new one.

    ![Screenshot of the products table in the lakehouse page.](./Images/lab5u7.png)

1. A new notebook named **Notebook 1** is created and opened.

1. From the toolbar ribbon, click on **Settings (1)** icon, and change notebook name to **Query Products (2)**.

    ![](./Images/dpmh1.png)
    
    ![](./Images/mod5-p3t1p3.png)

1. In the notebook editor, in the **Explorer** pane, expand the **lakehouse<inject key="DeploymentID" enableCopy="false"/>**

1. In the **ellipsis (...) (1)** menu for the **Products** table, select **Load data (2)** > **Spark (3)**. This adds a new code cell to the notebook as shown here:

    ![Screenshot of a notebook with code to query a table.](./Images/lab5u8.png)

1. Use the **&#9655; Run all (1)** button to run all cells in the notebook. It will take a moment or so to start the Spark session, and then the results of the query will be shown under the code cell **(2)**.

    ![Screenshot of a notebook with query results.](./Images/lab5u9.png)

1. On the toolbar, use the **&#9723;** (*Stop session*) button to stop the Spark session.

    ![](./Images/mod5-p3t1p3(1).png)

1. In the navigation bar, select **Monitor** to view the monitoring hub, and note that the notebook activity is listed.

    ![Screenshot of the monitoring hub with a notebook activity.](./Images/lab5u10.png)

## Task 4: Monitor history for an item

Some items in a workspace might be run multiple times. You can use the monitoring hub to view their run history.

In this task, you will rerun the dataflow and view the historical run history in the monitoring hub. You will also explore detailed run information for each execution instance.

1. In the navigation bar, click on **Workspaces** **(1)** and select the **fabric-<inject key="DeploymentID" enableCopy="false"/> (2)** workspace. Then use the **&#8635; (3)** (*Refresh now*) button for your **Get Product Data** dataflow to re-run it.

    ![Screenshot of the monitoring hub with a notebook activity.](./Images/mod5-p3t4p1.png)

    ![Screenshot of the monitoring hub with a notebook activity.](./Images/mod5-p3t4p1(1).png)

1. In the navigation pane, select the **Monitor** page to view the monitoring hub and verify that the dataflow is in-progress.

    ![Screenshot of the monitoring hub historical runs view.](./Images/lab5u12.png)

1. In the ... menu for any of the historical runs select **View detail** to see details of the run.

    ![Screenshot of the monitoring hub with a notebook activity.](./Images/mod5-p3t4p1(2).png)

1. Close the Details pane and use the **Back to main view** button to return to the main monitoring hub page.

## Task 5: Customize monitoring hub views

In this task, you will learn how to apply filters and adjust columns to customize your monitoring hub view, making it easier to locate and analyze specific activities in environments with a large number of events.

1. In the monitoring hub, use the **Filter (1)** button to apply the following filter:

    - **Status**: **Succeeeded (2)**
    - **Item type**: **Dataflow Gen2 (CI/CD) (3)**

      ![](./Images/dpm13.png)

      ![](./Images/dpm15.png)

    - With the filter applied, only successful runs of dataflows are listed.

        ![](./Images/mod5-p3t5p1.png)

1. Use the **Column Options (1)** button to include the following columns **(2)** in the view (use the **Apply (3)** button to apply the changes):

    - Activity name
    - Status
    - Item type
    - Start time
    - Submitted by
    - Location
    - End time
    - Duration
    - Refresh type
    
      ![](./Images/monitor-filter01.png)

        >**Note:** You may need to scroll horizontally to see all of the columns.

## Review

In this lab, you learned how to:

- Created a lakehouse

- Created and monitored a Dataflow

- Created and monitor a Spark notebook

- Monitored history for an item

- Customized monitoring hub views


### You have successfully completed the lab. Click on Next >> to procced with next Lab.

![](./Images/nextpage-mod5.png)

