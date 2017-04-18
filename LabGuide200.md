
![](images/200/Picture200-lab.png)  
Updated: February 10, 2017

## Introduction

In Lab 200 we will be building and deploying our first microservice, this microservice will provide a RESTFul interface for our catalog database. The microservice is built using Java and leverages lightweight libraries Jax-ws and Grizzly IO to create RESTful endpoints. In Lab 300 we will be wiring up a MySQL Database to the microservice.

Please direct comments to: Cam Crockett (cam.crockett@oracle.com)

## Objectives
- Import microservice from GitHub
- Setup automated build to create application artifacts
- Setup an automated deployment to provisiona dn deploy your applciation into the Oracle Cloud

## Required Artifacts
- We will be leveraging a preparred application found on [GitHub: https://github.com/c-rocket/TTC-MySQLMicroservice.git](https://github.com/c-rocket/TTC-MySQLMicroservice.git)

## Technologies Involved
- Oracle Cloud Serivce:
    - Developer Coud Service
    - Application Container Cloud Service
- Application Technologies
    - Written in Java
    - Leverages Jax-ws and Grizzly IO to provide a RESTful inerface
    - Uses MySQL drivers for DB interface
    - Uses Maven for build scripting and library management

## Architecture
You will be building out the first component of your Microservices Application

![](images/200/targeted-architecture.png)

# Create Your Project

## Create Developer Cloud Service Project

### **STEP 1**: Login to your Oracle Cloud Account
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

    ![](images/100/Picture100-4.png)

- If all your services are not visible, **click** on the **Customize Dashboard**, you can add services to the dashboard by clicking **Show.** For this workshop, you will want to ensure that you are showing at least the **Application Container, Developer and Storage** cloud services. If you do not want to see a specific service, click **Hide**

    ![](images/100/Picture100-5.png)

### **STEP 2**: Check/Set Storage Replication Policy

- If you have not already done so please set your replication policy as described in the [Pre-requisite guide](PreReqGuide.md).

### **STEP 3**: Login to Developer Cloud Service

Oracle Developer Cloud Service provides a complete development platform that streamlines team development processes and automates software delivery. The integrated platform includes an issue tracking system, agile development dashboards, code versioning and review platform, continuous integration and delivery automation, as well as team collaboration features such as wikis and live activity stream. With a rich web based dashboard and integration with popular development tools, Oracle Developer Cloud Service helps deliver better applications faster.

- From the Cloud UI dashboard click on the **Developer** service. In our example, the Developer Cloud Service is named **developer99019**.

    ![](images/100/Picture100-6.png)

- The Service Details page gives you a quick glance of the service status overview.

    ![](images/100/Picture100-7.png)

- Click **Open Service Console** for the Oracle Developer Cloud Service. The Service Console will then list all projects for which you are currently a member.

    ![](images/100/Picture100-7.5.png)

### **STEP 4**: Create Developer Cloud Service Project

- Click **New Project** to start the project create wizard.

    ![](images/100/step02.png)

- On Details screen enter the following data and click on **Next**.


```
    Name: Touch The Cloud Demo
```

> **Note:** A Private project will only be seen by you or users added to the project. A Shared project will be seen by all Developer Cloud users.

![](images/100/step03.png)

- Leave default template set to **Empty Project** and click **Next**

    ![](images/100/step04.png)

- Select your **Wiki Markup** preference to **MARKDOWN** and click **Finish**.

    ![](images/100/step05.png)

- The Project Creation on average will take about 1-2 minutes.

    ![](images/100/step06.png)

- You now have a new project, in which you can manage your software development.

    ![](images/100/step07.png)


# Setup your Application

## Import the Catalog Application

### **STEP 5**: Create a New Repository

In this step we will be importing the NodeJS and Oracle JET application from GitHub directly into our Developer cloud isntance

- From the main page click **New Repository**.

![](images/100/step07.png)

- Fill out the form and hit **create**


```
Name: CatalogUI
Select Import from Existing Repository:
https://github.com/c-rocket/TTC-CatalogApp.git
```


![](images/100/step08.png)

- Your code is now being imported into a new Git repository in Developer Cloud Service

![](images/100/step09.png)

- Once finished the code in the repository will be available to browse through

![](images/100/step10.png)


### **STEP 6**: Create Deployment Articfacts through an Automated Build

- Click **Build** on the left menu

![](images/100/step11.png)

- Create a **New Job**. Fill out the form and click **Save**

> Name: CatalogUIBuild

![](images/100/step12.png)

- You will now be able to configure your build.

![](images/100/step13.png)

- Select the **Source Control** tab and select **Git**, followed by the catalog repository. Add the **Master branch**.

![](images/100/step14.png)

- Select the **Build Step** Add a Shell Build

![](images/100/step15.png)

- Enter the command:


```shell
npm install
```

![](images/100/step16.png)

- Select the **Post Build** step and Archive the Artifactat by adding `**/target/*`

![](images/100/step17.png)

- **Save** and **Build Now**

![](images/100/step19.png)

### **STEP 7**: Create an Application Deployment for the Build

- Click **Deploy** from the left menu

![](images/100/step20.png)

- Select Create **New Configuration** and fill out the form and select Application Cotnainer from the Deployment Target


```
ConfigurationName: CatalogUIDeploy
```

![](images/100/step21.png)

- Enter in your domain credentials and Test the Connection. Once successfully tested, select connection.

![](images/100/step23.png)

- Select the following options:

```
Runtime: Node
Billing: Hourly
Type: Automatic
Deploy Stable Builds Only
Job: CatalogUIBuild
Artifact: TTC-CatalogApp.zip
```

![](images/100/step24.png)

- Save and Start the Deployment

![](images/100/step25.png)

- The deployment should execute successfully

![](images/100/step26.png)

### **STEP 8**: Verify Deployment

- Open your main Dashboard Console. Select Application Container and open the service console

![](images/100/step27.png)

- You will now see the Deployed Aplication Running

![](images/100/step28.png)

- Open the link provided to view the Deployed Application

![](images/100/step29.png)

**You have now completed lab 100**
