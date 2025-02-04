# nfspoc
A POC for NFS large file retrieval.  
  
## Entry point
http://localhost:8090/demo/start

## Enviro Variables
The following environmental variable must be present when the application is run.
| Name  | Example Value |
| ------------- | ------------- |
| POC_ORDS_ENDPOINT  | http://myendpoint  |
| POC_ORDS_APP_ID  | 12345  |
| POC_ORDS_APP_PWD | 12345  |
| POC_ORDS_TICKET_LIFETIME  | 120  |
| POC_WRAPPER_BASEPATH | http://myendpoint |

## Installation
Once repo is cloned and environmental variables set, then run the following:
```
mvn clean
mvn install
mvn spring-boot:run
``` 
## Usage
It's expected the Chrome browser will be used for this application. 

 1. Start at http://localhost:8080/demo/start
 2. Select one or more documents from the list at the top left of the
    screen.
 3. A green progress bar will indicate the underlying ORDS calls for
    each thread; first the initialize call followed by the getPOCFile
    call. The total timing  of each call will be written on the progress
    bar.
 4. During a failure condition the progress bar will be red. The reason
    for the failure may be found by opening the developer tools (F12) ad inspecting the response object for the failed thread id. Look for the 'errorMessage' attribute. 
 5. Once the file is available on the NFS drive (when the progress bar
    hits 100%), the file will automatically begin to download. 


 
