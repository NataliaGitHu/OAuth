# How to register the OAuth apps
*Credentials should be different for GitCloud and DevInfo applications./

##  GitHub.com


1.	Sign in to your <a href="https://github.com/" target="_blank">Github</a> account;
2.	Click "Settings"; ![Settings](images/Settings-GitHub%20.png)
3.	Click "Developer Settings"; ![Developer Settings](images/Developer-settings.png)
4.	Switch to OAuth apps;
5.	Click "New OAuth app"; ![New OAuth app](images/New-OAuth-App%20.png)
6.	Fill in all required text-field;  
*Authorization callback URL = <YOUR_APP_BASE_URL> +/api/1/oauth/github/*;
7.	Click "Register application";
8.	Copy a Client ID and a Client Secret;
9.	Open the `/jiragitcloud/docs/server-specific-conf/sourcesGithub.yaml`;
10.	Put a Client ID and a Client Secret into this file;
11.	Change a callback URL to <YOUR_APP_BASE_URL> +/api/1/oauth/github/;
     
```
---
pullRequestsEnabledInstallId: .+
apps:
  GitCloud:
    oauthClientId: 58493e73d12ed864e01b
    oauthSecret: a68bb445bc5511441bf98df85301b74de2f90ab0
    callbackUrl: https://ntalalova.ngrok.bigbrassband.tk/api/1/oauth/github/
    scope: repo
  DevInfo:
    oauthClientId: 9208b286cc3272e34adf
    oauthSecret: fdaa3e1b5e4f7244b3ae888739d74937b2839bc9
    callbackUrl: https://devinfo.bigbrassband.com/api/1/oauth/github/
    scope: repo
 ```
  
12.	Save the changes.


##  Bitbucket


1.	Sign in to your <a href="https://bitbucket.org/" target="_blank">Bitbucket</a> account;
2.	Сlick one of the workspaces;    
3.	Click "Settings";  	![Add-consumer](images/Settings-Bitbucket.png)  
4.	Click "OAuth consumers";	![Add-consumer](images/OAuth-consumers.png)  
5.	Click "Add consumer";  ![Add-consumer](images/Add%20consumer.png)  
6.	Fill in all required text fields:  
*Callback URL = <YOUR_APP_BASE_URL> + /api/1/oauth/bitbucketorg/*  
*The required permissions:*  
* *Projects: Read*  
* *Repositories: Write* 
* *Pull requests: Write*  
* *Webhooks: Read and write*
* *Pipelines: Read*
7.	Click "Save";
8.	Open the `/jiragitcloud/docs/server-specific-conf/sourcesBitbucket.yaml`;
9.	Сopy a Key and a Secret and put it into this file;
         
```
---
pullRequestsEnabledInstallId: .+
apps:
  GitCloud:
    noApp: repoRead
    currentApp: repoWritePullWrite
    apps:
      repoRead:
        oauthClientId: SJ9LbSYYpGHTvfNeB6
        oauthSecret: GGEt2p38bafS5ApGWm8Qq5LpF7EByDPq
      repoWritePullWrite:
        oauthClientId: ruEPpuKYhRVncsRNGY
        oauthSecret: JsyH7CBpFCGpZeqe6ZV5W5JNKLyj9Fkj
      pipelinesRead :
        oauthClientId: ruEPpuKYhRVncsRNGY
        oauthSecret: JsyH7CBpFCGpZeqe6ZV5W5JNKLyj9Fkj
  
  DevInfo:
    noApp: repoWritePullWrite
    currentApp: repoWritePullWrite
    apps:
      repoWritePullWrite:
        oauthClientId: Qgt5rjpY3NarMEmq24
        oauthSecret: M5jeq25uCMEjDsvSsZGAAPTtenpxsTKW
  ```    

10.	Save the changes.


##  Microsoft

1.	Sign in to your <a href="https://azure.microsoft.com/en-us/services/devops/" target="_blank">VSTS</a> account;
2.	Go to <a href="https://aex.dev.azure.com/me?mkt=en-US&campaign=o~msft~old~vsts~profile" target="_blank">VSTS profile</a> page;
3.	Сlick "Create new application"; ![Azure-CreateNewApplication](images/Azure-CreateNewApplication.png)
4.	Fill in all required text-fields:  
*Authorization callback URL = <YOUR_APP_BASE_URL> + /api/1/oauth/vsts*  
*Authorized scopes:*  
  * *Build (read)*
  * *Code (read and write)*  
  * *Release (read)*
5.	Click "Create application";
6.	Open the `/jiragitcloud/docs/server-specific-conf/sourcesVSTS.yaml`;
7.	Copy an App ID and a Client Secret and put it into this file;
8.	Change a callback URL to <YOUR_APP_BASE_URL> +/api/1/oauth/vsts/;  
  
 ```
---
pullRequestsEnabledInstallId: .+
apps:
  GitCloud:
    oauthClientId: 3A22ACAF-BDF3-40F3-9354-FAE55434CE63
    oauthSecret: eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIng1dCI6Im9PdmN6NU1fN3AtSGpJS2xGWHo5M3VfVjBabyJ9.eyJjaWQiOiIzYTIyYWNhZi1iZGYzLTQwZjMtOTM1NC1mYWU1NTQzNGNlNjMiLCJjc2kiOiIxZWJkYjA4MC04MjI4LTRiYTQtYTRjZC01YzNmMjIxZTFmNzAiLCJuYW1laWQiOiI0MjRiMmVmOS0xMWJhLTYxODAtYWRhYi0zOGY3MzQwMDg0MDQiLCJpc3MiOiJhcHAudnN0b2tlbi52aXN1YWxzdHVkaW8uY29tIiwiYXVkIjoiYXBwLnZzdG9rZW4udmlzdWFsc3R1ZGlvLmNvbSIsIm5iZiI6MTY0NjgwNDg0NywiZXhwIjoxODA0NTcxMjQ3fQ.HqGtmbo_2cXaLKVukhpwgClciCeTv9--I_EgpHXoJS4m_rN-4egssNJMrXvKmlDUGpOnlJufFoPxit3kuNYcKg3EycQ0U027yvzVVMeCDcd3S2rrfo-E6fPIcQ65sqe2RE3hkZOqCwViTzYVdvxCv-o5zsjVi3gv1zk-V8HdrtEg2gpXVw1l7aR9m1sU-jMzPnKVEOZey3rkbSTSuxsc7AC30WTgbJuU3v1qLaHVKKFraEGOig06Uqq5nj4pIeSNoHmMkGUiqwD72tUnfUZnQM5gSRUaxLGNkgwurehml_YN35oYNLQZTtcb0WfN_4sT8ayZvZu_V6JAh00NNhO1rw 
    callbackUrl: https://ntalalova.ngrok.bigbrassband.tk/api/1/oauth/vsts/
    scope: vso.build vso.code_write vso.release
  DevInfo:
    oauthClientId: SJ9LbSYYpGHTvfNeB6
    oauthSecret: GGEt2p38bafS5ApGWm8Qq5LpF7EByDPq
    callbackUrl: https://devinfo.bigbrassband.com/api/1/oauth/vsts/
    scope: vso.build%20vso.code_write%20vso.release
  ```  
 
9.	Save the changes.
