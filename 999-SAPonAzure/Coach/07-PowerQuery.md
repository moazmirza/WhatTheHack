# Challenge 7: Coach's Guide

[< Previous Challenge](./06-deploymongo.md) - **[Home](README.md)** - [Next Challenge >](./08-storage.md)

## Notes & Guidance

There are few  actvities for the PowerBI APp intergation with SAP HANA DB ..
at theigh level we can summerize the actvities in three sections ...

Activity 1:  

Make sure that   SAP S/4 appliance is installed and have access details in right SAP client. 

Activity 2:   

Now download  and install  the Power BI client  and SAP HANA studio on SAP   windows jump box to configure the DB connection and create the direct query using power BI desktop, 
 
Activity 3:  

Now  configure the poweBI app connection to SAP HANA DB using Azure  and SAP documenations steps using  HANA studio and power BI desktop clients.
steps include --
   1. Create the additiona SAP schema and user , Assign appropriate previleges and roles to newly created users in HANA stusion to conenct SAP S/4 schema.
   2. IN power BI clinet GUI add the user name / password of HANA db users and connection strings with tables name to poulate the data
   3. Once the data populate in power BI client, use appropariate colume , row and filter criteria to create the quesry to show vistulaization using PIE or nbar char.
   4. publish the power BI app for the end user so they can use on their desktop for future use.


Login in SAP HANA Database using HANA Studio: 



 
![Image1](Images/Challege7_image1.png)
 

Or  



![Image2](Images/Challenge7_image2.png)

Following pop up will appear  - 

 

![Image3](Images/Challenge7_image3.png)

 

Select  "Launch" Button ... 

 

After selecting launch ... 


![Image4](Images/Challenge7_image4.png)


 

Select "Apply and Close " 


![Image5](Images/Challenge7_image5.png)


 

Select description "Open Hack ID"  - apply and close 

  

  

  
![Image6](Images/Challenge7_image6.png)

 

 

It will create  "OpenhackID" entry in the SAP studio 

 

 
![Image7](Images/Challenge7_image7.png)
  


Initial screen of SAP HANA studio will pop up  

  

![Image8](Images/Challenge7_image8.png)
 

 

Right click on the left space under systems and select “Add System” 

  
![Image9](Images/Challenge7_image9.png)
  


 

Enter  the system information as below  

![Image10](Images/Challenge7_image10.png)
 

Enter system user ID and  password for SAP HANA DB  

 

![Image11](Images/Challenge7_image11png)
 

 

Add SAP system S4P 

 

![Image12](Images/Challenge7_image12png)
 

 

Enter the "SYSTEM" DB user and password  

 


 
![Image13](Images/Challenge7_image13.png)
 

 

Setup new User ID in SAP HANA Database: 

Create a new user ID SAPOPENHACK in SAP HANA, this user will be used to connect Power BI to SAP HANA Database 

 

 

![Image14](Images/Challenge7_image14.png)
 

 

Create new user  SAPOPENHACK 

 
![Image15](Images/Challenge7_image15.png)
 

Enter  "SAPOPENHACK" ID and Password -- 



Add " ABAP admin" "content admin" public" roles  

 

 
![Image16](Images/Challenge7_image16.png)
 

Add "catalog read",  "data admin" and "export" system privileges .. 

 ![Image17](Images/Challenge7_image17.png)


 
Add following object privileges ---  create and select 

 
![Image18](Images/Challenge7_image18.png)
 
![Image19](Images/Challenge7_image19.png)

Save the configuration  

![Image20](Images/Challenge7_image20.png)


 

 

When we update the “Object Privileges” with TBTCO and granter is SYSTEM it won’t save it and gives an error. So remove that object and login into S4P with SAPHANADB  ( User ID) and then goto securityàUsers-àSAPOPENHACK and add the object privileges with TBTCO. 

 


![Image21](Images/Challenge7_image21.png)

 

HANA configuration is complete … now Let's work on Power BI connection and report... 

Setup the connection in Power BI desktop to SAP HANA Database: 

Install Power BI Desktop 

![Image22](Images/Challenge7_image22.png)



 

Open Power BI desktop 


 ![Image23](Images/Challenge7_image23.png)

Click on “Get data from another source” and select “ Connect” 

 

 
On following screen, type SAP Keyword 

 

![Image24](Images/Challenge7_image24.png)
 

Enter SAP DB information on following screen  

 ![Image25](Images/Challenge7_image25.png)


Enter port information as follows  

 
![Image26](Images/Challenge7_image26.png) 

Select custom and SQL query as follows  

 
![Image27](Images/Challenge7_image27.png)

Will pop up with information about SAP table TBTCO as follows  

![Image28](Images/Challenge7_image28.png)

 


Select “Load” after the screen appears 

 
![Image29](Images/Challenge7_image29.png)
 


 

Select "transform data " on opo up screen as shwon in following screen  

![Image30](Images/Challenge7_image30.png)

![Image31](Images/Challenge7_image31.png)

![Image32](Images/Challenge7_image32.png)

Creating visualization in Power BI using the SAP table TBTCO 

Create a Matrix. 


![Image33](Images/Challenge7_image33.png)

 

 

Add fields “JOBNAME” and “AUTHCKMAN” in Rows 


Add field “STATUS” in Columns 

Add “EVENTID” in Values 

![Image34](Images/Challenge7_image34.png)


 

 

Create a new Table in the visualization 

  

Drag and drop fields "JOBNAME", "JOBCLASS", "JOBLOG", "REAXSERVER" and "ENDDATE" under values 

 

![Image35](Images/Challenge7_image35.png)

Create a Pie chart: 

  

Drag and drop field “AUTHCKMAN” under Legend and  field “JOBCOUNT” under Values ( with count). 


![Image36](Images/Challenge7_image36.png)
 

Create a Filter or Slicer 

Drag and drop field “AUTHCKMAN” under Field. 

![Image37](Images/Challenge7_image37.png)
 
![Image38](Images/Challenge7_image38.png)

![Image39](Images/Challenge7_image39.png)


Save the report 

![Image40](Images/Challenge7_image40.png)
 

Once the report is saved need to publish to Power Apps 
