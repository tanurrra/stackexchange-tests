# stackexchange-tests

## Postman tests for (some) API endpoints of stackexchange.com 

* For CI integration command will look like:
```
newman run stackexchange.postman_collection.json -e stackexchange_com.postman_environment.json
```
It should be added to the build step in Jenkins. 

* Reports: run tests with additional command: 
``` 
--reporters cli,json --reporter-json-export outputfile.json
```
 
* To get reports in teamcity the following command should be added: 
```
-r teamcity
```

* or with option `--bail` to stop on a test case error with a status code of 1, which can then be picked up by a CI tool or build system:
```
newman run stackexchange.postman_collection.json -e stackexchange_com.postman_environment.json --bail newman
```

Docs: https://api.stackexchange.com/docs/
