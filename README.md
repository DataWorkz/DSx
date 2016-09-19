#Hands-On-Lab: Data Scientist
Analyze sales data in dashDB from IBM Data Science Experience using Spark based IPython Notebooks

#Introduction
IBM Data Science Experience is an interactive, collaborative, cloud-based environment where data scientists can use multiple tools to drive analytics and derive insights. Data Scientists can use Python, R, or Scala in Jupyter Notebooks already connected to Spark or RStudio for open source R computing environment.

<img src="DSX1.png">

This lab exercise uses an IPython Notebook in Data Science Experience to connect with dashDB, explores sales, product data and analyze sales performance for a specific product line. Pixiedust, a Python based visualization package is used to visualize the results.

##Steps for the Lab

###Provision dashDB <br>
1.	Login to IBM Bluemix <br>
a.	For existing accounts use  https://console.ng.bluemix.net/login <br>
b.	Sign-up for a free trial account at https://console.ng.bluemix.net/registration/ <br>
2.	Provision dashDB  <br>
a.	From the Bluemix catalog menu search for “dashdb” <br>
b.	Click on the dashDB Icon   <br>
c.	Accept the default values and rename “Service name:” to ‘DS_Sales_DataStore’ <br>
d.	Select “Entry Pricing Plan” (default) and click “Create” on the right hand panel. <br>
The lab exercise uses a sample database provisioned by dashDB service. <br>

###Data Science Experience
Provision Spark Service in Data Science Experience <br>

1.	Login to IBM Data Science Experience @ http://datascience.ibm.com/ <br>
2.	Create a new Notebook <br>
a.	Click on ‘Start a Notebook” <br> 
b.	If this is your first Notebook, you will see a message that you need Spark service. Click on ‘Create a Spark Service here’ link in the message to provision Spark Service. <br>
c.	Type ‘IA_Lab_Spark’ as the Spark service name and accept defaults (Personal plan for Spark service, New Object Storage with free plan).  <br>
d.	Click ‘Create Instance’ to create Spark Service. <br>
###Create Notebook in Data Science Experience <br>
1.	On next screen, click on ‘New Notebook’ to create a notebook. <br>
2.	Type ‘IA_Lab_Notebook’ as Notebook name, click on ‘from URL’ link and specify  <br>
https://github.com/ibmdataworks/sigmo-demos/tree/master/data-scientist/interactive-analytics/DSX_IA_Lab.ipynb <br>
 
e.	 Select ‘Trust this Notebook to run with your Privileges’ and click on ‘Create Notebook’  <br>
 
3.	Once notebook is created, add connection details to access data sources. <br>
a.	On top left menu, click Menu -> Connections -> Create Connection <br>
b.	Key in ‘dashDB’ as connection name <br>
c.	From drop down list of ‘Target Service Instance’ select ‘DS_Sales_DataStore’, the dashDb service you provisioned in Bluemix. <br>
d.	Select ‘Database’ as ‘BLUDB’.  <br>
e.	Click ‘Create’. <br>
4.	Open your Notebook and add the data source<br>
a.	Navigate to home with a click on ‘IBM Data Science Experience’ (top left) and open ‘DS Lab Notebook’ <br>
b.	Click on ‘Data Sources’ and ‘Add Source’<br>
 
c.	Click on Connections, select the connection named ‘dashDB’<br>
d.	Click ‘Add Data Source’<br>
 
5.	From the Notebook, connect to the sample sales database in dashDB<br>
a.	Place the cursor in the first cell. This should be empty, if not clear the contents. <br>
b.	Click on ‘Insert Code’  to insert credentials for the data source ‘dashDB’ <br>
 
c.	Rename the inserted array variable ‘credentials_1’  to ‘credentials’<br>
 
d.	To execute code in any notebook cell, place cursor in cell and click the arrow icon in toolbar<br>
 
e.	Place cursor in cell1, execute code to capture dashDB database credentials<br>
f.	Place cursor in cell2, execute code to connect, load tables from dashDB<br>
6.	Query, join and group data using SparkSQL Data frame API to build aggregated sales for the product line ‘Outdoor Protection’. <br>
a.	Place cursor in cell3 and execute code to build aggregated sales data frame<br>
b.	Place cursor in cell4 and execute code to install or update Pixiedust package<br>
c.	Place cursor in cell5 and execute code to  visualize SparkSQL Data frame<br>
 
7.	You can move the mouse over the visual to see data points on each bar. The chart shows a steady decline in sales for ‘Outdoor Protection’ product line.<br>
8.	Pixiedust is an open source visualization package developed by IBM labs. You can visualize SparkSQL data frames with a single API call and interactively access raw data, pick visual options and stow data away to files or IBM Cloudant or Object Storage. <br>

###End of Lab
Next Steps: Build your next Spark Analytics project using IBM Data Science Experience.

CLEANUP: Delete dashDB service ‘DS_Sales_DataStore’ from Bluemix, delete ‘IA_Lab_Notebook’ and ‘IA_Lab_Spark’ Spark service from Data Science Experience
