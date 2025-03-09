# Exercise 1: Create a Fabric workspace

### Estimated Duration: 15 minutes

In this exercise, you will go through the process of signing up for the Microsoft Fabric Trial and setting up a workspace. This serves as the initial step in familiarizing yourself with the Microsoft Fabric platform. By creating a workspace, you will establish a dedicated environment where you can explore and interact with the wide range of tools and services Microsoft Fabric offers, including data integration, analytics, and visualization. This foundational setup is essential for understanding how to manage and organize resources within Fabric, as well as how to collaborate effectively across teams and projects within the platform.

## Lab objectives

In this lab, you will be able to complete the following tasks:

- Task 1: Sign up for Microsoft Fabric Trial
- Task 2: Create a workspace

### Task 1: Sign up for Microsoft Fabric Trial

In this task, you will initiate your 60-day free trial of Microsoft Fabric by signing up through the Fabric app, providing access to its comprehensive suite of data integration, analytics, and visualization tools

1. Open the **Microsoft Edge** browser in the LabVM, navigate to the following URL, and click **Try for Free**:  

   ```
   https://www.microsoft.com/en-in/microsoft-fabric/getting-started
   ```

1. You'll see the **Sign into Microsoft Azure** tab. Here, enter your credentials:
 
   - **Email/Username:** <inject key="AzureAdUserEmail"></inject>
 
     ![Enter Your Username](./Images/md1.png)
 
1. Next, provide your password:
 
   - **Password:** <inject key="AzureAdUserPassword"></inject>
 
     ![Enter Your Username](./Images/md2.png)

1. If **Action required** pop-up window appears, click on **Ask later**.

#### Steps to Proceed with MFA Setup if "Ask Later" Option is Not Visible

1. At the **"More information required"** prompt, select **Next**.

1. On the **"Keep your account secure"** page, select **Next** twice.

1. **Note:** If you don’t have the Microsoft Authenticator app installed on your mobile device:

   - Open **Google Play Store** (Android) or **App Store** (iOS).
   - Search for **Microsoft Authenticator** and tap **Install**.
   - Open the **Microsoft Authenticator** app, select **Add account**, then choose **Work or school account**.

1. A **QR code** will be displayed on your computer screen.

1. In the Authenticator app, select **Scan a QR code** and scan the code displayed on your screen.

1. After scanning, click **Next** to proceed.

1. On your phone, enter the number shown on your computer screen in the Authenticator app and select **Next**.
       
1. If prompted to stay signed in, you can click **No**

#### Activate the Microsoft Fabric Free Trial  

1. In the Fabric portal, click on **Account Manager (1)** and then select **Free trial (2)**.

    ![Account-manager-start](./Images/md3.png)  

2. In the prompt that appears, click **Activate** to start your **60-day free Fabric trial**.  

   ![Account-manager-start](./Images/md4.png)  

3. Once the trial is successfully activated, click **Got it** on the confirmation prompt.  

   ![Account-manager-start](./Images/md5.png)  

### Task 2: Create a workspace

In this task, you will create a Fabric workspace. The workspace contains all the items needed for this tutorial, which includes lakehouse, dataflows, Data Factory pipelines, notebooks, Power BI datasets, and reports.

1. From the left menu bar, select **Workspaces (1)** and click on **+ New workspace (2)**.

    ![New Workspace](./Images/md6.png)

1. On **Create a workspace** window, enter the below name and expand the **Advanced (2)** setttings

   - **Name:** Enter **fabric-<inject key="DeploymentID" enableCopy="false"/>** (1)

    ![New Workspace](./Images/md7.png)

1. Under **License mode**, select the **Trial (1)** and click on **Apply (2)**

    ![New Workspace](./Images/md8.png)

### Summary

In this exercise, you have signed up for Microsoft Fabric Trial and created a workspace.

### Review 
In this lab, you have completed:

 + Signed up for Microsoft Fabric Trial
 + Created a workspace

### You have successfully completed the lab. Click on Next >> to procced with next Lab.
