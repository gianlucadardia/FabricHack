## Configuration
[<-Back](./Readme.md)


### Azure Resources configuration
For testing purpose you could create SQL Database loading an  example.

**Through audit setting**

![selectsetting](./images/selectauditing.png)

- Configure database to send audit log to 
  - Storage account
![storageaudit](./images/storageaudit.png)

  - Eventhub
![sendeventhub](./images/sqloneh.png)

**REMEBER TO SAVE**
![sqlsave](./images/sql-saveaudit.png)


To simplify configuration process we could  perform some activity in order to generate some log to gather from eventstream
![generatevent](./images/generateevents.png)



### **Fabric configuration**

- connect eventsream to eventhub
  
- select ADX database as destination 
  
- provide table name as destination
Put in window dialog event name table

- select "Enable preprocess"
Once selected destination, we need to configure eventsream preporcessor.
![es-preprocessor](./images/es-preprocessor.png)
 providing following trasformation

 **Expandrecords** to expand arrary 

 **Manage Fields**  To flatten json and report to one level all fields provided by the audit log
 


- From **ADX** page enable *"visible to lakehouse"* switch
  ![enablelkh](./images/kql-enablelkh.png)

- add shortcut from lakehouse to ADX
  
  ![newshorcut](./images/lkh-newshortcut.png)
  ![newshorcutref](./images/lkh-referenceshortcut.png)


Final evenstream configuration
![esfinalconfiguration](./images/es-finalconfiguration.png)

[<-Back](./Readme.md)