# # mulesoft-chargeback : This repository is created as Proof of Concept to prove out the chargeback model for MuleSoft Platform 
## # Table of Contents 
###   1. Use Case for the Prototype
###   2. Source files to import in Anypoint Studio
###   3. Closer look at Splunk Log4 Appender configuration for MuleSoft flows to ingest data in Splunk
###   4. Splunk set up on your system 
###   5. Splunk configuration and index creation
###   6. Import MuleSoft POC Flows app cores JSON files in Splunk
###   7. Configure Splunk Dashboards for application level counts and chargeback for clients
  
  Let's get Started !!!!

### Step 1: Use Case for Prototype 
  Let's take a fictitious use where we have two clients or groups in a company, Ecommerce and Mobile calling building apps to submit/get an order to/from a common backend system (eg. SAP or OMS) . Mobile App calls Mobile Order EAPI ( Experience API ) and Ecommerce App calls Ecom Order EAPI (Experience API) to submit/get or perform crud operations. Each of experience API in turn calls common Order SAPI (system API) to perform respective crud operation 

![](https://github.com/nikhilgauba/mulesoft-chargeback/blob/main/UseCase.png)


### Step 2: Source files to import in Anypoint Studio 

In our prototype app we used the mule4 correlation ID configuration to pass the correlation ID down with a prefix of the calling group (e.g, mobile or ecom). This ID is logged with the standard JSON Logger to Splunk. An OOB platform API can pull the full set of application and core configurations to compute the bills

![](https://github.com/nikhilgauba/mulesoft-chargeback/blob/main/APILayers.png)
