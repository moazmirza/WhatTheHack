# Challenge 5: Build Mobile Application around SAP. 

[< Previous Challenge](./04-BCDR-with-ANF.md) - **[Home](../README.md)** - [Next Challenge >](./06-Start-Stop-Automation.md)

## Introduction

Mango Inc has established SAP landscape for several years. Now Mango Inc wants to enable users with simplified mobile user interface that requires data from multiple sources and one of the data source is S/4 Hana system. Assume that production workers on site want to know material information on their mobile devices. How do you build mobile application using No/Low code platform that can interact with SAP system seemlessly? In this challenge, we'll find that out.

## Description

Build a simple power application for Tablet that can  fetch available materials from the user sales organization and plant. Application should also allow user to select material from the list and display complete details for that material upon selection. High level architecture for this application may look like as shown below. 

![](Images/Challenge5-SampleArchiteture.png)

This challenge requires you to build foundational infrastructure along with power application. 

## Success Criteria

1. Setup working ERP connection in the power automate (or flow).
2. Run the power application and display selected material information. 

## Hints

- BAPI Names to fetch data from **SAP S/4 Hana system**.
	- Materials list can be fetched from SAP system using BAPI named "BAPI_MATERIAL_GETLIST".
		- You can use below selection criteria to fetch materials using above BAPI.
		- Material selection: I CP * (like MATNRSELECTION SIGN as I, MATNRSELECTION OPTION as CP, and MATNRSELECTION MATNR LOW as *)
		- Plant selection: I EQ 1010
		- Sales organization selection: I EQ 1010
		- You can leave rest of the selection criteria empty. 
		- MATNRLIST in the received outfrom SAP system has list of materials. 
	- Material information can be fetched from SAP system using BAPI named "BAPI_MTERIAL_GET_DETAIL"

- Power Automate is very useful to connect SAP system and fetch data. 
- Request & Response step can be used to pass information from power automate (flow) to power application. 
- Sample end application may look like below: (It is only to give an idea but can be much better than this).
![](Images/Challenge5-SampleApplicationScreen.png)

## References

1. SAP ERP Connector in power applications: https://powerapps.microsoft.com/en-us/blog/introducing-the-sap-erp-connector/
2. Power Apps canvas applications: https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/ 
3. Create collection object in power apps: https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/create-update-collection 
4. Using power (flows) Automate in power apps: https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/using-logic-flows
5. Access URL for power application: https://make.powerapps.com/
6. Access Azure portal: https://portal.azure.com/ 




