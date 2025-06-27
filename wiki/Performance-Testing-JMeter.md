 **JMeter Setup and Usage V1.0** 

 **What is JMeter?** 

JMeter is an open-source testing tool that analyzes and measures the performance of software and products.

It is used to execute performance testing, load testing, and functional testing of web applications.

JMeter can also simulate a heavy load on a server by creating tons of virtual concurrent users to the web server.

 **How does JMeter perform testing?** 

Let's have a look at the different steps performed by JMeter during testing:


1. It creates a request and sends it to the server.


1. It receives the response from servers, collects them, and visualizes those details in a chart or graph.


1. It processes the response from the server.


1. It generates the test result in several formats such as text, XML, JSON so that the tester can analyze data.



 **Prerequisites** 

JMeter is a pure Java desktop application. It requires a fully compliant JVM 6 or higher. You need to download and install the latest version of Java SE Development Kit.

The operating systems compatible with JMeter are:


* Linux


* Windows


* Mac OS


* Ubuntu




1.  **Check if Java is installed** 




* Open the command prompt


* Put the command java -version



Example:


```
C:\Users\Ashley>java -version
java version "18.0.2.1" 2022-08-18
Java(TM) SE Runtime Environment (build 18.0.2.1+1-18)
Java HotSpot(TM) 64-Bit Server VM (build 18.0.2.1+1-18, mixed mode, sharing)

```
If you have Java installed in your system, the command will show the version of Java installed. Otherwise, before going forward with the installation of JMeter, you must install Java.

You can download and install the latest version of Java SE Development Kit. Download Java Platform (JDK).


1.  **Download JMeter** 




* To download JMeter, go to the Apache JMeter website.


* On the website, go to the binaries section and download the zip file.


* Wait for the zip folder to be downloaded.



 **Apache JMeter 5.4.1 (Requires Java 8+)** 

Binaries


* apache-jmeter-5.4.1.zip (pgp, md5, sha1)


* apache-jmeter-5.4.1.tgz (pgp, md5, sha1)




1.  **Install JMeter** 



Installation of JMeter is extremely easy and simple. You simply unzip the zip/tar file into the directory where you want JMeter to be installed. There is no tedious installation screen to deal with.


* Once the zip folder is downloaded, go to the folder location, and then extract the zip folder.


* Once the folder is extracted, go inside that folder and then go inside the bin folder.


* If you are using Windows, just run the file /bin/jmeter.bat to start JMeter in GUI mode.


* If you are using Linux/Mac, navigate to the folder and run the file /bin/jmeter.sh to start JMeter in GUI mode.




1.  **Install Plugin Manager** 



Plugins Manager enables users to automatically install various plugins, eliminating the need for manual installations. The manager saves users from dealing with JAR files manually.

The steps to install Plugins Manager are as follows:


* Go to this link: [https://jmeter-plugins.org/wiki/PluginsManager/](https://jmeter-plugins.org/wiki/PluginsManager/)


* Download the Plugins Manager JAR file.


* Place the JAR file in JMeter’s lib/ext directory.




1.  **Install PerfMon Servers Performance Monitoring Plugin** 



There are two setups needed to monitor server performance in JMeter:


1.  **Server Agent Setup** 


1.  **PerfMon Metrics Collector Setup** 



 **Server Agent Setup** 

JMeter does not collect server health metrics by default (except Tomcat). However, users can leverage the open-source SIGAR library, which should run on each server being monitored.

Steps:


* Download the PerfMon Server Agent from GitHub.


* Extract it and place it on each server that requires metric gathering (no administrator/root access needed).


* Navigate to the extracted folder and run:


    *  **Windows:** startAgent.bat


    *  **Mac/Linux:** startAgent.sh



    

This will start the agent on the default port 4444, displaying logs similar to:


```
INFO 2021-02-06 11:33:00.186 RMI TCP Accept-0: Binding to port 4444  
INFO 2021-02-06 11:33:00.186 RMI TCP Accept-0: Bound to port 4444  
INFO 2021-02-06 11:33:00.186 RMI TCP Accept-0: JP@GC Agent v2.2.3 started  

```
To change the port, use the command:


```
startAgent.bat --tcp-port 3450

```

1.  **Install PerfMon Metrics Collector Setup** 




* Open the JMeter test plan.


* Open Plugins Manager.


* Click  **Available Plugins**  and search for PerfMon.


* Install the plugin and restart JMeter.



After installation:


* Add the  **jp@gc - PerfMon Metrics Collector**  by navigating:


    *  **Right-click Thread Group**  →  **Add**  →  **Listener**  →  **jp@gc - PerfMon Metrics Collector** .



    

 **Configuring PerfMon Metrics Collector** 


* Click  **Add Row**  to specify host, port, and the metrics to collect.


* Multiple metrics can be added by clicking  **Add Row**  again.



Here’s the exact extracted text from your image:

 **JMeter PerfMon Plugin Configuration Guide** 

 **Testing the Server Agent** 

After adding the PerfMon Metrics Collector listener, you can validate whether the Server Agent is receiving commands.

Steps:


1.  **Open JMeter.** 


1.  **Right-click Thread Group**  →  **Validate**  → Click  **Validate** .


1. This will send a single test request.


1. Check the  **Server Agent Terminal**  where it is running. If configured correctly, you should see:




```
INFO 2021-06-02 11:55:12 JVM-8PC-B Received test command  
INFO 2021-06-02 11:55:12 JVM-8PC-B Sending acknowledgment  

```
This output confirms that the Server Agent is receiving commands successfully.

 **Understanding JMeter Components** 

JMeter consists of various  **Elements**  designed for different purposes. Some key components include:


*  **Thread Group**  – Defines the number of threads (users) that simulate concurrent requests.


*  **Samplers**  – Send requests to a server and receive responses.


*  **Listeners**  – Capture test results, metrics, and graphs.


*  **Configuration Elements**  – Manage default settings for Samplers, such as HTTP headers.




1.  **Thread Group Overview** 



A  **Thread Group**  is a collection of  **threads** , where each thread represents a virtual user making requests to the application under test.

Key properties:


*  **Number of Threads**  – Simulated users sending requests.


*  **Ramp-Up Period**  – Time taken to start all threads gradually.


*  **Loop Count**  – Defines how many times the requests should be executed per thread.



Here’s the exact extracted text from your image:

 **JMeter Plugin Components Guide** 

 **Samplers Overview** 

Samplers are components that send requests to a server and process responses. JMeter supports testing various protocols, such as HTTP, FTP, JDBC, and more.


*  **FTP Request:**  Used for performance testing an FTP server, allowing file downloads and uploads.


*  **HTTP Request:**  Sends HTTP/HTTPS requests to web servers, simulating browser or API interactions.


*  **JDBC Request:**  Executes database performance testing using SQL queries.


*  **BSF Sampler:**  Allows writing custom samplers using a Bean Scripting Framework language.


*  **Access Log Sampler:**  Reads access logs and generates corresponding HTTP requests.


*  **SMTP Sampler:**  Sends email messages via the SMTP protocol for performance verification.



 **Listeners Overview** 

Listeners capture and display the results of test executions in various formats, such as graphs, tables, and logs.


*  **Graph Results:**  Visualizes server response times in a graph format.


*  **View Results Tree:**  Displays raw request-response data for analysis.


*  **Table Results:**  Summarizes test results in a structured table.


*  **Log Results:**  Records test summaries in a text file for further examination.



 **Configuration Elements Overview** 

Configuration Elements provide default settings and reusable variables for samplers.


*  **User Defined Variables:**  Enables parameterization of requests using predefined variables.


*  **HTTP Header Manager:**  Defines HTTP headers for requests.


*  **CSV Data Set Config:**  Reads external CSV files for dynamic test data.


*  **DNS Cache Manager:**  Controls DNS resolution behavior during testing.


*  **Java Request Defaults:**  Specifies default settings for Java-based samplers.



Here’s the exact extracted text from your image:


1.  **CREATE TEST PLAN** 



Now that you have understood the elements, you can create your own test plan in JMeter.

The first step in creating the test plan is:

 **ADDING A THREAD GROUP** 


* Open the JMeter window


* The window is divided into two parts. The left side has all the added elements, while the right side has all the elements' configurations.


* Right-click on the test plan.


* Go to  **Add → Threads (Users) → Thread Group** 



Now, once you click on the  **Thread Group** , there are three things on the screen that are important concerning the load test:


*  **Number of Threads (Users):** 

    This is the number of threads or users JMeter will simulate.

    Let's make it  **100** .


*  **Ramp-Up Period (in seconds):** 

    This is the time that JMeter takes before starting the thread over.

    Let's keep this as  **12** .


*  **Loop Count:** 

    This is the number of times the test will be executed.

    And this one, let's leave it to be  **1** .



 **Thread Group** 


*  **Name:**  Thread Group


*  **Comments:** 


*  **Action to be taken after a Sampler error:** 


    * Continue


    * Start Next Thread Loop


    * Stop Thread


    * Stop Test


    * Stop Test Now



    

 **Thread Properties** 


*  **Number of Threads (Users):**  100


*  **Ramp-up Period (Seconds):**  12


*  **Loop Count:**  1


    * Same user on each iteration


    * Specify Thread creation until needed



    
*  **Duration (Seconds):** 


*  **Startup delay (Seconds):** 



The next step is to:

 **ADD AN HTTP REQUEST** 


* Right-click on  **Test Plan**  and again go to  **Add** 


* In the drop-down, select  **Samplers** 



These are all the types of requests that JMeter can work on.


* For now, choose the simplest of them all, the  **HTTP Request** .



Here you will have to give the address to some home pages or websites.

Here’s the exact extracted text from your image:

Here, you will have to specify the target website or API:


*  **Server Name or IP:**  Enter the domain name or IP address of the server.


*  **Protocol:**  Specify HTTP or HTTPS based on the request type.


*  **Port Number:**  Define the port on which the server listens.


*  **Path:**  Provide the request path relative to the server.



Once the HTTP request setup is complete, the next step is executing a test:

 **JMeter HTTP Test Execution Guide** 


1.  **Run Test Plan** 



Now that the HTTP test setup is complete, the next step is to execute the test and analyze the results.

 **Add Listeners** 

To determine the results of the test, you need to add listeners.


*  **Right-click on FirstJMeter** 


* Navigate to the  **Listener**  options



JMeter provides various report types for test result visualization.

For now, select  **View Results Tree** .


1.  **Execute the Test Plan** 




* Click the  **green run button**  to start the test.


* Observe the test execution and navigate to  **View Results in Table** .



If the test was successful, you should see a  **green status indicator** , confirming proper request execution.


* Then, verify results in  **View Results in Tree**  for detailed request-response analysis.



 **JMeter Test Results & Monitoring** 

You can see the  **green status**  that shows that the test was successful.


* Then check  **View Results in Tree** 



The  **green status**  or success indicator can be seen here as well.

The test execution considers the  **number of users** ,  **ramp-up period** , and  **loop count**  set up in the first step.

As seen on the screen, the test is  **still running** .


* The execution time, number of requests performed, and the success status of each hit to the API are displayed.



For  **demonstration purposes** , the test is being executed in  **GUI mode** .


* In this example, CPU and  **memory metrics**  are being monitored.



Once the test  **runs for a few seconds** , the  **listener will plot graphs**  based on data collected from the  **server agent** .

 **Additional Documentation** 


* L&P Inner Sourcing Handover Documentation


* Load & Performance Sample Test Plan



 **Troubleshooting** 


*  **JMeter PerfMon: EXCEPTION_ACCESS_VIOLATION** 


* [https://stackoverflow.com/questions/55928198/jmeter-perfmon-exception-access-violation](https://stackoverflow.com/questions/55928198/jmeter-perfmon-exception-access-violation)


*  **Solution:**  Download the  **sigar-amd64-winnt.dll**  file and replace it in the  **lib**  folder.











*****

[[category.storage-team]] 
[[category.confluence]] 
