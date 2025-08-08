# Lab 3: Implement deployment pipelines in Microsoft Fabric

## Estimated Duration : 45 minutes

Deployment pipelines in Microsoft Fabric let you automate the process of copying   changes made to the content in Fabric items between environments like development, test, and production. You can use deployment pipelines to develop and test content before it reaches end users. In this exercise, you create a deployment pipeline, and assign stages to the pipeline. Then you create some content in a development workspace and use deployment pipelines to deploy it between the Development, Test and Production pipeline stages.

In this hands-on lab, you will implement deployment pipelines in Microsoft Fabric to automate the promotion of content across different environments such as Development, Test, and Production. You will create workspaces, configure a deployment pipeline, generate content in the Development workspace, and use deployment pipelines to deploy the content across stages. This exercise demonstrates how to streamline content management and validation before it reaches end users.

## Lab Objectives

In this lab, you will complete the following tasks:

- **Task 1**: Create workspaces

- **Task 2**: Create a deployment pipeline

- **Task 3**: Assign workspaces to stages of a deployment pipeline

- **Task 4**: Create content

- **Task 5**: Deploy content between stages

### Task 1: Create workspaces

In this task, you will create three workspaces in Microsoft Fabric — Development, Test, and Production — with Fabric capacity enabled.

1. In the menu bar on the left, select **Workspaces** (the icon looks similar to &#128455;).
   
1. Create a **new workspace** named **Development<inject key="DeploymentID" enableCopy="false"/> (1)**, and under **License mode**, select the **Trial (2)** and click on **Apply (3)**.

    ![](./Images/dpm41.png)
   
1. Repeat **steps 1 & 2**, for creating **two** more workspaces named **Test<inject key="DeploymentID" enableCopy="false"/>**, and **Production<inject key="DeploymentID" enableCopy="false"/>**.
   
1. Select the **Workspaces (1)** icon on the menu bar on the left and confirm that there are three workspaces named:  **Development<inject key="DeploymentID" enableCopy="false"/>**, **Test<inject key="DeploymentID" enableCopy="false"/>**, and **Production<inject key="DeploymentID" enableCopy="false"/>** **(2)**.

    ![](./Images/dpm42.png)

### Task 2: Create a deployment pipeline

In this task, you will create a new deployment pipeline that will manage the movement of content across the Development, Test, and Production stages.

1. In the menu bar on the left, select **Workspaces (1)**.
   
1. Select **Deployment Pipelines (2)**, then **New pipeline**.

    ![](./Images/dpm43.png)
   
1. In the **Add a new deployment pipeline** window, click on **New pipeline** from bottom and enter **pipeline<inject key="DeploymentID" enableCopy="false"/> (1)** as the pipeline name, then click **Next (2)** to continue.

   ![Screenshot of pipeline stages.](./Images/lab5u18.png)
   
1. Accept the defaults on the **Customize your stages** window.

1. Select **Create and Continue**.

   ![Screenshot of pipeline stages.](./Images/lab5u19.png)

### Task 3: Assign workspaces to stages of a deployment pipeline

In this task, you will assign the previously created workspaces to their respective stages in the deployment pipeline.

1. On the left menu bar, select the **pipeline** you created.
   
3. In the window that appears, select the **dropdown** under the **Add content to this stage** for each deployment stage and select the name of the **workspace** that matches the name of the stage and click on **correct** symbol next to the dropdown to assign the workspace.

   ![.](./Images/deployment-pipeline12.png)

   ![.](./Images/dpm44.png)   

### Task 4: Create content

In this task, you will create a lakehouse named LabLakehouse in the Development workspace and populate it with sample data.

1. In the menu bar on the left, select **Workspaces**.
   
1. Select the **Development<inject key="DeploymentID" enableCopy="false"/>** workspace.
   
1. Select **New Item**.
   
1. In the window that appears, Under the **Store data** select **Lakehouse** and if prompt to **Upgrade to a free Microsoft Fabric trial** click on **Upgrade**.

1. In the **New lakehouse window**, name the lakehouse as, **LabLakehouse<inject key="DeploymentID" enableCopy="false"/>**.
   
1. Select **Create**.
    
1. Select the **Start with sample data** tile.

1. Then on the **Use a Sample** page, choose the **Public holidays** tile to populate the workspace with sample data.

    ![Screenshot of a new lakehouse in Fabric.](./Images/lab5u14.png)

1. In the menu bar on the left, select the **pipeline<inject key="DeploymentID" enableCopy="false"/> (1)** you created, then **toggle off (1)** **New Deployment Pipelines** to disable the feature **(2)**.

    ![Screenshot of a new lakehouse in Fabric.](./Images/dpm45.png)
    
1. In the **Development** stage, select the **>** until you see **Lakehouses**. The lakehouse shows up as new content in the Development stage. Between the **Development** and **Test** stages, there's an orange **X** within a circle. The orange **X** indicates that the Development and Test stages aren't synchronized.
    
1. Select the downward arrow below the orange **X** to compare the content in the Development **(1)** and Test environments. Select **Compare (2)**.The LabLakehouse only exists in the Development stage.  

    ![](./Images/dpm46.png)

### Task 5: Deploy content between stages

In this task, you will use the deployment pipeline to move the lakehouse content from Development to Test, and then to Production, verifying the synchronization at each stage.

Deploy the lakehouse from the **Development** stage to the **Test** and **Production** stages.

1. Select the **Deploy** button in the **Development** stage of the pipeline to copy the lakehouse in its current state to the text stage.

    ![](./Images/dpm47.png)

1. If a pop-up appears stating **"Workspace includes unsupported items"**, click **Continue** to proceed. 

   ![](./Images/lab5u201.png)

1. In the **Deploy to next stage** window, select **Deploy** to initiate the deployment.   

    ![](./Images/dpm48.png)
   
1. There is an **orange X** between the Test and Production stages. Select the **downward facing arrow (1)** below the orange X. The lakehouse exists in the Development and Test stages but not yet in the Production stage.
   
   - In the **Test** stage, select **Deploy (2)**.

     ![](./Images/dpm49.png)   
   
1. In the **Deploy to next stage** window, select **Deploy**. The green check mark between the stages indicates that all stages in sync and contain the same content.

    ![](./Images/dpm50.png)
    
1. Using deployment pipelines to deploy between stages also updates the content in the workspaces corresponding to the deployment stage. Let's confirm.
    
1. In the menu bar on the left, select **Workspaces**.
    
1. Select the **Test<inject key="DeploymentID" enableCopy="false"/> (1)** workspace. The lakehouse was copied there **(2)**.

    ![](./Images/dpm51.png)
    
1. Open the **Production<inject key="DeploymentID" enableCopy="false"/> (1)** workspace from the **Workspaces** icon on the left menu. The lakehouse was copied to the Production workspace too **(2)**.

    ![](./Images/dpm52.png)

## Review

In this lab, you learned how to:

- Created workspaces

- Created a deployment pipeline

- Assigned workspaces to stages of a deployment pipeline

- Created content

- Deployed content between stages

## You have successfully completed the lab
