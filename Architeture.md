# Tips for Workshop Developers
    
## Steps for creating a new workshop

- To start a new workshop, use git to create a branch from this (workshop-template) branch.
- Rename the workshop-template folder in your new branch to the title of your new workshop, observing the naming convention of the rest of the folders in the repository
- Rename the lab guide md files to be more specific to your workshop, if desired.
- Update manifest.json with the titles and descriptions of your labs (and md filenames if you changed them).
- Use LabGuide100.md as an example of how to format and structure your lab's markdown.
- Preview your lab guides by loading index.html in your favorite editor's live view (Brackets - Live Preview, Atom - atom-live-server)

## Supporting Files

- README
    - The README.md file (this file) should give a clear step-by-step overview of what the student should do to complete the workshop, beginning with any prerequisite checks or software installation (detailed in the Student Guide)
    - **Do not include this 'Tips for Workshop Developers' section in the final workshop readme**
    - An example readme follows these tips, it can be modified for your workshop
- Student Guide
    - An example student guide has been provided, but it should be modified for the requirements of this workshop.
    - It should document where to get and how to install any required software
    - Any networking settings likely to need attention should be discussed in the guide
- Images
    - Store lab images under the images/x00 folder corresponding to the lab number they belong to. 
    - Images that are used in multiple lab guides can be stored directly in the images/ folder.

# Example Readme:
## IMPORTANT: How to prepare for this workshop

**First**, ***Get an Oracle Cloud Account*** 
- Oracle provides several methods for gaining access to Oracle Cloud Accounts used to complete the Labs in this Hands-on-Workshop. 
    - For some workshop events, cloud environments will be provided. 
    - For others events (e.g. **Oracle Code**), or when completing this workshop in a self-service model, you must gain access to your own Trial account. Trial accounts can be obtained at [Try It](http://cloud.oracle.com/tryit) 
    - If you are attending an Oracle sponsored event, please **review your Event invitation** for more instruction on how to gain access to your Workshop Account.
        
**Second**, ***Configure your Client Environment***
- Your client enviroment **must be configured prior** to attempting the Hands-on-Workshop labs. 
- You have two options for configuring your workshop client environment. 
     - ***Option 1:*** You can install Virtual Box and download and run a pre-configured **Virtual Box Image**.
     - ***Option 2:*** You can **install and configure** Eclipse, Brackets and Git on your laptop. 
- Both **Option 1 and 2 are documented** in the [Prerequisite Guide](PreReqGuide.md). ***Please follow the instruction in the Student Guide*** prior to attempting the Labs. 
      
## How to View the Lab Guides

- The Labguides are best viewed using the Workshop's [GitHub Pages Website URL](https://c-rocket.github.io/TouchTheCloudDevOpsLab/) 

- Once you are viewing the Workshop's GitHub Pages website, you can see a list of Lab Guides at any time by clicking on the **Menu Icon**

    ![](images/WorkshopMenu.png)  

- To log issues and view the Lab Guide source, go to the [github oracle](https://github.com/c-rocket/TouchTheCloudDevOpsLab) repository.


## DevOps and Cloud Native Microservices Workshop

This Oracle Public Cloud DevOps workshop will guide participants through the main AppDev Services in their Oracle Trial Account. There will be a combination of presentation and hands-on work for this workshop focusing on automating the build out of a microservices application.

## Workshop Details

**Reference the following Lab Guides by opening their Documentation Files:**

