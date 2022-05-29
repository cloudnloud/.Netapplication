# Deployment-Dotnet application
## Step-1: Pre-requisites
- You must have activated aws.amazon.com account or Azure account.
- you must create Windows server 
- Connect to the Windows server using RDP client 
## Step-2: 
 - Go in to server manager (server_manager)
 ![image](https://github.com/cloudnloud/.Netapplication/blob/master/images/server_manager.png)
 - In the server manager go to the local manager and make sure IE enhanced security configuration is off 
 ![image](https://github.com/cloudnloud/.Netapplication/blob/master/images/IE_configuration.png)
- Install Necessary software using the below link 
(https://ninite.com/)
## Step-3: Install Necessary Software In VM
 -  select the bundle depending on your .net application
 (https://dotnet.microsoft.com/en-us/download/dotnet/3.1)
 ![image](https://github.com/cloudnloud/.Netapplication/blob/master/images/windows_hostingbundle.png)
 
 - now install web deployment (select appropriate version depending upon VM)
 (https://www.microsoft.com/en-us/download/details.aspx?id=43717)
  ![image](https://github.com/cloudnloud/.Netapplication/blob/master/images/webdeployment_64.png)
 -  Install IIS (with Management Console)
 
 ````
 # Install IIS (with Management Console)
Install-WindowsFeature -name Web-Server -IncludeManagementTools

# Install Web Management Service
Install-WindowsFeature -Name Web-Mgmt-Service
`````
 - download the JDK 8 and install it in VM
  (https://www.oracle.com/java/technologies/downloads/#java8-windows8)
 - configure environmental variables for JDK 8 
environmental variables > system variables > go with browse and select the file location of JDK
 ![image](https://github.com/cloudnloud/.Netapplication/blob/master/images/Environmental_variables2.png)
 ## Other tools required are :
 - Install Visual studio 2019
 (https://visualstudio.microsoft.com/vs/community/)
 
- Git for Windows
Jenkins will need Git to be able to pull the code from repositories. You can download it from here.
 (https://git-scm.com/download/win)
- Install choclatey in powershell
```
choco install nuget.commandline
```
- Install Nuget  (please follow below link )
(https://community.chocolatey.org/packages?q=nuget)


 ## Step-4: Download Jenkins 
- Download Jenkins and install jenkins
 (https://www.jenkins.io/download/#downloading-jenkins)
- Once the download is complete, run the jenkins.msi installation file.
- The setup wizard starts. Click Next to proceed.
-  Select the install destination folder and click Next to continue.
- Under the Run service as a local or domain user option, enter the domain username and password for the user account you want to run Jenkins with. Click Test Credentials to verify the login data, then click Next to proceed.
- Using the Run service as LocalSystem option doesn’t require you to enter user login data. Instead, it grants Jenkins full access to your system and services. Note that this is a less secure option and is thusnot recommended.
-  Enter the port number you want Jenkins to run on. Click Test Port to check if the selected port is available, then click Next to continue.
- Select the directory where Java is installed on your system and click Next to proceed.
-  Select the features you want to install with Jenkins and click Next to continue.
- Click Install to staOnce the installation is complete, click Finish to exit the install wizard.rt the installation process.

## Step-5: Unblock Jenkins
- In your web browser, navigate to the port number you selected during the installation using the following address
```
http://localhost:[port number]
```
- Navigate to the location on your system specified by the Unblock Jenkins page.
 ![image](https://github.com/cloudnloud/.Netapplication/blob/master/images/Unlock_jenkins.png)

- Open the initialAdminPassword file using a text editor such as Notepad.
- Copy the password from the initialAdminPassword file.
- Paste the password in the Administrator password field on the Unblock Jenkins page and click Continue to proceed.
 
## Step-6: Customize Jenkins
- Click the Install suggested plugins button to have Jenkins automatically install the most frequently used plugins.
![image](https://github.com/cloudnloud/.Netapplication/blob/master/images/Install_suggestPlugin.png)
-  After Jenkins finishes installing the plugins, enter the required information on the Create First Admin User page. Click Save and Continue to proceed.
- On the Instance Configuration page, confirm the port number you want Jenkins to use and click Save and Finish to finish the initial customization.
- Click the Start using Jenkins button to move to the Jenkins dashboard
## Step-7: Install Plugins
- go to manage Jenkins > manage plugins > under Available go with MSBUILD
- go with install without restart

## Step-8: Configure Global tool configuration
- configuring Git 
![image](https://github.com/cloudnloud/.Netapplication/blob/master/images/git_configure.png)

- Configuring Build tool MSBUILD
![image](https://github.com/cloudnloud/.Netapplication/blob/master/images/msbuild_configure.png)

## Step-9: Create New Item
- Enter the name of the item you want to create. We shall use the “.netapplication” for this demo.
- Select Freestyle project
- Click Okay
## Step-10:  Enter Project details
## step-9:  Enter repository URL
![image](https://github.com/cloudnloud/.Netapplication/blob/master/images/git_scm.png)
## step-11:  Under build trigger 
! [image](https://github.com/cloudnloud/.Netapplication/blob/master/images/buildtrigger_image.png)
## step-12: Under build,
- Click on “Add build step”
- Click on “Execute Windows batch command” and add the commands you want to execute during the build process.
![image] (https://github.com/cloudnloud/.Netapplication/blob/master/images/nugget_image.png)
- click on Msbuild and give this following command 
![image](https://github.com/cloudnloud/.Netapplication/blob/master/images/msbuild_file.png)
![image](https://github.com/cloudnloud/.Netapplication/blob/master/images/executecommand.png)
- click on Apply and save
## step -13: Now click on Build 
![image(https://github.com/cloudnloud/.Netapplication/blob/master/Deployment-Dotnetapplication-jenkins-images/build_success.png)




     






