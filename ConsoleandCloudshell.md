# **Console and Cloud shell**

##Objectives
   Get access to Google Cloud.
   Create a Cloud Storage bucket using the Cloud Console.
   Create a Cloud Storage bucket using Cloud Shell.
   Become familiar with Cloud Shell features.
   
##Steps
 1. Create a bucket using Console.
    >>> gsutil mb gs://qwiklabs-gcp-00-0a0163005b72
 2. Become familiar with Cloud Shell features.
 -Copy the file into one of the buckets you created earlier in the lab
    >>>gsutil cp my file.txt gs://qwiklabs-gcp-00-0a0163005b72
 3. Create a persistent state in Cloud Shell
 3.1 Identify available regions
 -List available regions
    >>>gcloud compute regions list
 3.2 Create and verify an environment variable
 -Create an environment variable and replace [YOUR_REGION] with the region you selected in the previous step.
    >>>INFRACLASS_REGION=us-central1
 -Verify it with echo
    >>> echo $INFRACLASS_REGION
 -Exit
  >>>exit
 3.4 Create a subdirectory for materials used in this class
 -Create a subdirectory for materials used in this class
    >>>mkdir infraclass
 -Create a file called config in the infraclass directory
 	>>>touch infraclass/config
 -Append the value of your Region environment variable to the config file
 	>>>echo INFRACLASS_REGION=$INFRACLASS_REGION >> ~/infraclass/config
 -Create a second environment variable for your Project ID
 	>>>INFRACLASS_PROJECT_ID=qwiklabs-gcp-00-0a0163005b72
 -Append the value of your Project ID environment variable to the config file
 	>>>echo INFRACLASS_PROJECT_ID=$INFRACLASS_PROJECT_ID >> ~/infraclass/config
 -Use the source command to set the environment variables, and use the echo command to verify that the project variable was set
 	>>>source infraclass/config
	>>>echo $INFRACLASS_PROJECT_ID
 -Close and re-open Cloud Shell. Then issue the echo command again
 	>>>echo $INFRACLASS_PROJECT_ID
 		<No Output>
 3.5 Modify the bash profile and create persistence
 -Edit the shell profile with the following command
  	>>>nano .profile
 -Add the following line to the end of the file
  	>>>source infraclass/config
 -Press Ctrl+O, ENTER to save the file, and then press Ctrl+X to exit nano.
 -Close and then re-open Cloud Shell to cycle the VM.
 -Use the echo command to verify that the variable is still set
  	>>>echo $INFRACLASS_PROJECT_ID
  
