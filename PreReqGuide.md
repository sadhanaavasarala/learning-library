Update: April 10, 2017

# Prerequisites Guide

This Guide will provide you with the instructions nessesary to ensure you have the proper tools and configuration done to execute ont he workshop. This Workshop will allow you to gain exposure to Oracle Developer Cloud Service, Oracle Application Container Cloud Service, Oracle Container Cloud Service, Oracle MySQL Cloud Service and Oracle's open source front end framework Oracle JET.

## Client Enviroment Options

Your client enviroment **must be configured prior** to attempting the Hands on Workshop, or you will not be able to complete the Workshop labs.

### Check/Set Storage Replication Policy
Depending on the state of your Cloud Account, you may need to set the replication policy, if it has not been previously set. In this step you will got to the Storage Cloud Service to check on the status of the Replicaton Policy

- From any browser, go to the URL:
    `https://cloud.oracle.com`

- click **Sign In** in the upper right hand corner of the browser

    ![](images/100/Picture100-1.png)

- **IMPORTANT** - Under my services, select from the drop down list the correct data center and click on **My Services**. If you are unsure of the data center you should select, and this is an in-person training event, ***ask your instructor*** which **Region** to select from the drop down list. If you received your account through an Oracle Trial, your Trial confirmation email should provide a URL that will pre-select the region for you.

    ![](images/100/Picture100-2.png)

- Enter your identity domain and click **Go**.

    **NOTE:** The **Identity Domain, User Name** and **Password** values will be given to you by the instructor or Trial confirmation email.

    ![](images/100/Picture100-3.png)

- Once your Identity Domain is set, enter your User Name and Password and click **Sign In**


    ![](images/100/Picture100-3.5.png)

- You will be presented with a Dashboard displaying the various cloud services available to this account.

    ![](images/100/Picture100-4.png). 

- Click on the **Storage** Cloud Service

    ![](images/100/Picture-01.png)

- If you see a message requesting that you **Set Replication Policy** as is shown below, click on the message. If the message is not displayed, your replication policy has already been set and you can continue to the next step by clicking on the **Dashboard** icon in the top right corner of the page.

    ![](images/100/Picture-02.png)

- Care must be taking when setting your replication policy, because it cannot be changed. With Trial accounts, the first option available will generatlly set the replication policy sufficient for this workshop, so we will take the Default, and click on the **Set** button. 

    ![](images/100/Picture-03.png)

- Click on the **Dashboard** button

    ![](images/100/Picture-04.png)

You have two options for configuring your workshop client environment. 

- ***Option 1***: You can install Virtual Box and download and run a pre-configured **Virtual Box Image**. 
    - Refer to the ***Virtual Box Client Installation*** section of this document to use this option
    - **This option is best**, if you don't want to worry about installing and configuring multiple Open Source Software tools on your laptop. 
- ***Option 2***: You can **install and configure** Eclipse, Brackets and Git on your laptop.
    - Refer to the ***Configure Client Tools Locally*** section of this document to use this option.
    - **This option is best** if you want to install and configure the opensource software on your laptop, or your corporate standards will not let you install a hypervisor, or your laptop's resorces are not adequate to run virtual images. 

### Hardware Requirements

- You will need a machine capable of connecting to the internet and downloading files
