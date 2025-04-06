# QFApplicationResultsAndReflections
QF Senior Quality Engineer Application - Results and Reflections

Thanks for taking the time to check out my demo projects! 

## Web Testing Demo - Playwright 

A simple Playwright framework was created with almost default configuration 

A test is created making use of only: 

1. Drive a user journey E2E in an e-commerce setting
   * Use the codegen feature to build the basic steps
   * Updated the codegen locators for better stability/better practice
   * Added in verification steps, to ensure that checks were made along the journey to verify the results
3. Organise the code using simple page object model (there are other approaches!)
4. Organise test case with Playwright's Test Steps approach, to build better reports with less information
   * Configured playwright to retain trace on fail, so that reports can be used to troubleshoot
   * Playwright report can be expanded to dig into each test step if need be
  
### Reflections
Given more time to put into this project, I would 
* review locators

If not a smoke test, I would also consider: 
* interacting with the underlying API services, using **APIContext**, to check the service service status before proceeding with steps that may be at risk of failing should an underlying API be down in the environment
  
### Sample Playwright Report captures

Test case overview: 

<img width="1015" alt="image" src="https://github.com/user-attachments/assets/9731ccff-e061-4cdf-9d98-79fb5d11352e" />

Test step detail: 
<img width="960" alt="image" src="https://github.com/user-attachments/assets/797f088c-f937-4219-83cd-3bb536916161" />

## API Testing Demo - Postman/Newman

A basic PostMan demo to interact with the Weatherbit API

Weatherbit specifications were first imported to Postman to view the specifications

TEST CASES: 

Exploratory Data Driven Test Cases

2 x simple tests were created as exploratory approach to seeing the behaviour of the end points: Get Current Weather, using PostalCode and Lat/Long informnation 
  * Tests can be executed in Postman Application (default variables for PostalCode, Lat, Long are pre-defined as Scripts to run before the request is sent)
  * Tests can be executed in Postman Runner or Newman using bulk data files, sourced on the weatherbit site

Regression Test Case - calling a single end point with dynamically built parameters, driven from a CSV file
1 x simple regression case created to demonstrate using a CSV to drive lower level test steps to check the basic system functionality 
  * Boundary value testing 
  * Invalid/Valid inputs etc

## Results 

### Bugs

If working on this project, I would **highlight the risks of sending an API key as a query parameter**
  * This will result in easier detection of secret information (In the case of weatherbit, the API key isn't as sensitive, so there are traces you can find of the API key in my project - even though initially I looked at setting it up in a .env file to protect it)

There were some results where for Get Current Weather by PostalCode, where the **results didn't match the country of the country requested**
  * I would investigate the backend services to see if the backend data handles those inputs, and where the issue is coming from (or if it is the only way it can be handled for some more obscure places)
    







