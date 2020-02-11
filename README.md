# explore-restful-booker-api-with-postman

Exploring Service API through Test Automation with Postman

1. API under exploration: <a href="https://github.com/mwinteringham/restful-booker">Restful Booker</a>
   
   Restful Booker API is a NODE application, Please refer the above URL for installation and more details.
Note that the instructions say that you need MongoDB, but you actually do not need to have MongoDB installed and you may see a couple of warnings for packages during installation but don't worry on that.

2. Environments created: Production URL(https://restful-booker.herokuapp.com/) and Local URL(http://localhost:3001/)

3. After you import this postman collection, you can see the pre-requested scripts where the data-driven mechanism is implemented.
Reference:<a href="https://learning.getpostman.com/docs/postman/scripts/postman_sandbox_api_reference">Postman Scripting docs<a/>

4. Please install <a href="https://www.npmjs.com/package/newman">Newman</a>, a tool used to help the postman collections on the command line and also this helps to integrate the collection with Jenkins or other continuous integration solutions.
  
      a. command for installation : npm install -g newman
  
      b. Go to command line shell in the folder where our collection saved
  
      c. command for execution: newman run #collection name# -e #environment#
                  and for our case it would be,      
                                newman run RestfulBookerAPIBuildVerificationTest.postman_collection.json -e Local.postman_environment.json
                                
    This will generate a basic report like below that how many scripts ran and how many assertions there were and how many failed, and it breaks down all the failures. 
    
    ![image](https://drive.google.com/uc?export=view&id=1mgFbrgo6Ct2cU6BaZxfDWMugW8v0c3_T)

  5.   In order to run postman collection on jenkins, referred this site: <a href="https://www.toolsqa.com/postman/run-postman-collection-on-jenkins/"> toolsqa</a> and the jenkins report will be like below:
  ![image2](https://drive.google.com/uc?export=view&id=1--ZWYXQ7Zts1RiviJaCrSLo7-UTB6zcQ)
  
Note:
Configured the jenkins job like below

![image3](https://drive.google.com/uc?export=view&id=1ojzWVrRTXoV2aUx9k0-U4wkBObCjKMue)
   
For reporting, two different reporters are used 1) to the command line 2) junit style and finally display the test results, exportm them as a XML file(result.xml)
