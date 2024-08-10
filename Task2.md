# Configure FTP/ SFTP server and create a ADF pipeline for data extraction

## Create an SFTP linked service using UI

1. Browse to the Manage tab in your Azure Data Factory or Synapse workspace and select Linked Services, then click New:

![](https://learn.microsoft.com/en-us/azure/data-factory/media/doc-common-process/new-linked-service.png)

2. Search for SFTP and select the SFTP connector.

![](https://learn.microsoft.com/en-us/azure/data-factory/media/connector-sftp/sftp-connector.png)

3. Configure the service details, test the connection, and create the new linked service.

![](https://learn.microsoft.com/en-us/azure/data-factory/media/connector-sftp/configure-sftp-linked-service.png)



## Create a pipeline

1. On the home page, select Orchestrate.

![](https://learn.microsoft.com/en-us/azure/data-factory/media/tutorial-data-flow/orchestrate.png)

2. In the General panel under Properties, specify CopyPipeline for Name. Then collapse the panel by clicking the Properties icon in the top-right corner.

In the Activities tool box, expand the Move and Transform category, and drag and drop the Copy Data activity from the tool box to the pipeline designer surface. Specify CopyFromBlobToSql for Name.

![](https://learn.microsoft.com/en-us/azure/data-factory/media/tutorial-copy-data-portal/drag-drop-copy-activity.png)

3. Go to the Source tab. Select + New to create a source dataset.

In the New Dataset dialog box selected desuired storage to extract data from.

4. Go to the Sink tab, and select + New to create a sink dataset.

In the New Dataset dialog box, input "SQL" in the search box to filter the connectors, select Azure SQL Database, and then select Continue. 


