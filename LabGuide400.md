![](images/400/Picture400-lab.png)  
Updated: April 13, 2017
Please direct comments to: Cam Crockett

## Introduction

Welcome to lab 400. In this lab we will be completing our application architecture by deploying a Golang microservice on Docker. The service will be responsible to translating currencies on our UI. Our target Architecture for the end of the lab will look like this:
![](images/400/targeted-architecture.png) 

## Objectives

- Setup your docker host on Container Cloud Service
- Deploy the microservices from it's Docker Hub build location

## Required Artifacts
- The following lab requires an Oracle Public Cloud account that will be supplied by your instructor.
- SSHKey: Download zip from [https://github.com/c-rocket/TTC-CurrencyMicroservice](https://github.com/c-rocket/TTC-CurrencyMicroservice) and extract labkey.pub

## Optional Artifacts

- The Code Base for Docker Hub Build is located here: [https://github.com/c-rocket/TTC-CurrencyMicroservice](https://github.com/c-rocket/TTC-CurrencyMicroservice)
- Google's Go Programming Language is described here: [https://golang.org/](https://golang.org/)
- Docker informaiton can be found here: [https://www.docker.com/](https://www.docker.com/)
- Oracle's Container Cloud Service is deatiled here: [https://cloud.oracle.com/en_US/container](https://cloud.oracle.com/en_US/container)

## Prerequisites

- Expected that labs 100, 200 and 300 have been completed already
- Expected that your storage policy has been set as described in the [prerequisite guide](PreReqGuide.md)

# Setup and Deploy a Golang Microservice on Docker

## Setup your Docker Host

### **STEP 1**: Login with your Oracle Cloud Account

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


### **STEP 2**: Create a Container Cloud Service Instance

- From the Cloud UI dashboard click on the **Container** Cloud Service menu (not to be confused with Application Container) and select Open Service Console

![](images/400/step02.png)

- You will now be on the landing page for Oracl'e Container Cloud Service

![](images/400/step03.png)

- Click Create a service to start the wizard process of setting up your Docker host

![](images/400/step04.png)

- Fill in the form and click Next

```
Service Name: TouchTheCloudDemo
SSH Public Key: Use the one provided (or select new key to have on generated for you)
Admin Username: admin
Admin Password: Oracle123
```

![](images/400/step05.png)

- Confirm your setup

![](images/400/step06.png)

- Wait for a few minutes while your host provisions

![](images/400/step07.png)

### **STEP 3**: Create a new container service

- Once your Container Service instance is provisioned, click on the menu to open the Container Console

![](images/400/step09.png)

- Use the admin username and password you setup in the instance configuration to login


```
Username: admin
Password: Oracle123
```

![](images/400/step10.png)

- Once logged in, you will be presented with the main dashboard

![](images/400/step11.png)

- Select Services from the left hand menu, here you will find a listing of out-of-the-box containers available to be deployed
    - A new deployment is as easy as hitting deploy.

![](images/400/step12.png)

- We are now going to create a new service based off a Docker image built on Docker Hub (by default, Docker hub is linked to Oracle's Container Cloud service via the Registries Menu). Select New Service

![](images/400/step13.png)

- Fill out the New Service Form


```
Service Name: Currency Microservice
Image: camcrockett/ttc-currencymicroservice

```

![](images/400/step14.png)

- Select Ports from the Available Options and Add a new TCP port mapping for port 8090 and Save

![](images/400/step15.png)

- Now Save your new service

![](images/400/step16.png)

- verify your new service is in the list by filtering for Currency

![](images/400/step17.png)


### **STEP 4**: Deploy the container

- find the Currency Microservice in the list of services and select Deploy

![](images/400/step17.png)

- Use the default values for the deployment and hit Deploy

![](images/400/step18.png)

- Your container should start deploying

![](images/400/step19.png)

- Once sucessfully deployed the status should update

![](images/400/step20.png)


### **STEP 5**: Verify your Microservice

- Select Containers on the left menu to see a listing of your containers

![](images/400/step21.png)

- Click on hostname to view host details. **Make a note of the public IP**

![](images/400/step22.png)

- To Verify the microservice, open a new web browser tab and use the public IP to hit the following URL:


```
http://<Public_IP>:8090/currencies/v1/usd
```

![](images/400/step23.png)

### **STEP 6**: Bind your Microservice

- Return to your main service dashboard

![](images/400/step01.png)

- Select Application Container Cloud Service to view your previously deployed Applications from Labs 100 and 200

![](images/200/step.png)

- From the applicaiton dashbaord step into your Ui application

![](images/400/step.png)

- Select the <somthing> tab on the left

![](images/400/step.png)

- Add in a binding for the new Currency microservice

![](images/400/step.png)

- Save and apply your biding

![](images/400/step.png)

- You should now be able to open your UI where the Lab 400 achievement is unlocked and a currency selector is now enabled on screen.

![](images/400/step.png)

