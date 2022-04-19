# How to register the OAuth apps
*Credentials should be different for GitCloud and DevInfo applications.

##  GitHub.com


1.	Sign in to your <a href="https://github.com/" target="_blank">Github</a> account;
2.	Click "Settings";
3.	Click "Developer Settings";
4.	Switch to OAuth apps;
5.	Click "New OAuth app";
6.	Fill in all required text-field  
*Authorization callback URL = <your URL> +/api/1/oauth/github/*;
7.	Click "Register application";
8.	Copy a Client ID and a Client Secret;
9.	Open the `/jiragitcloud/docs/server-specific-conf/sourcesGithub.yaml`;
10.	Put a Client ID and a Client Secret into this file;
11.	Change a callback URL to <your URL> +/api/1/oauth/github/;
12.	Save the changes.


##  Bitbucket


1.	Sign in to your <a href="https://bitbucket.org/" target="_blank">Bitbucket</a> account;
2.	Сlick one of the workspaces;
3.	Click "Settings";
4.	Click "OAuth consumers";
5.	Click "Add consumer";
6.	Fill in all required text fields:  
*Callback URL = <your URL> + /api/1/oauth/bitbucketorg/*  
*The required permissions:*  
* *Projects Read*  
* *Repositories Write* 
* *Pull requests Write*  
* *Webhooks Read and write*
7.	Click "Save";
8.	Open the `/jiragitcloud/docs/server-specific-conf/sourcesBitbucket.yaml`;
9.	Сopy a Key and a Secret and put it into this file;
10.	Save the changes.


##  Microsoft

1.	Sign in to your <a href="https://azure.microsoft.com/en-us/services/devops/" target="_blank">VSTS</a> account;
2.	Go to <a href="https://aex.dev.azure.com/me?mkt=en-US&campaign=o~msft~old~vsts~profile" target="_blank">VSTS profile</a> page.
3.	Сlick "Create new application";
4.	Fill in all required text-fields:  
*Authorization callback URL = <your URL> + /api/1/oauth/vsts*  
*Authorized scopes: Code (read and write)*
5.	Click "Create application";
6.	Open the `/jiragitcloud/docs/server-specific-conf/sourcesVSTS.yaml`;
7.	Copy an App ID and a Client Secret and put it into this file;
8.	Change a callback URL to <your URL> +/api/1/oauth/vsts/;
9.	Save the changes.

