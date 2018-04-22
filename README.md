# Apex-Commandments
Curated list of Apex Best Practices from Tech Sessions and from my Personal experience

## Apex Best Practices

### Rule 1: Don't use SOQL queries inside For-Loops
 
  * Queries in For Loops can break governer limits
  * Total Query limit per execution context is 100.
  
  ![image](https://user-images.githubusercontent.com/2145211/39098748-44d46406-463d-11e8-9295-165925257fe1.png)
  
  * Take SOQL queries out of For-Loop. Here in this case, we are using relationship queries.
  
  ![image](https://user-images.githubusercontent.com/2145211/39098763-7baa3cb2-463d-11e8-98f4-14dfd255110b.png)
  
### Rule 2: Don't use DML Operations inside For-Loops

  * Using DML Operations inside for loops can break governer limits. 
  * DML Operation Limit per execution context is 150.
  
  ![image](https://user-images.githubusercontent.com/2145211/39098785-e2667830-463d-11e8-8b79-eff95ff00318.png)
  
  * Add the instance variable to a list and then perform DML operation outside of For-loop
  
  ![image](https://user-images.githubusercontent.com/2145211/39098802-3d1f4252-463e-11e8-9669-761f2c29e9a5.png)

### Rule 3: Define only 1 trigger per Object

  * This is because, if we have multiple triggers per Object, salesforce does not guarentee the order of execution.
  
  ![image](https://user-images.githubusercontent.com/2145211/39098834-b5560d1e-463e-11e8-82c4-a7ea17ea1839.png)
  
### Rule 4: Don't add code directly to Triggers other than reference to other classes or methods

  * As best practice, always create an Handler Classes
  
  ![image](https://user-images.githubusercontent.com/2145211/39098850-1184bb12-463f-11e8-9fd4-6ea147371984.png)
  
### Rule 5: Use Maps for Queries whenever possible

  * By using Map, we can always retrieve a specific record using ID.
  
  ![image](https://user-images.githubusercontent.com/2145211/39098891-7a8e4826-463f-11e8-9ec6-5f375b7ae480.png)
  
### Rule 6: Use Relationships in SOQL to reduce Queries

  * Parent-child and Child-Parent Relationships in Salesforce are useful to reduce number of Queries, so that the risk of breaking governer limits are reduced
  
  * When we go from Child-Parent, we can go upto 5 levels up in the hierarchy.
  * When we go from Parent-Child, it is limited to 1 level down.
  
  ![image](https://user-images.githubusercontent.com/2145211/39098924-be281530-463f-11e8-96e0-3a5b8f0c58ba.png)
  
### Rule 7: Aim for 100% Test Coverage

  * Atleast 3 scenarios should be tested:
    * Positive Test Case
    * Negative Test Case
    * User/Profile/Role based Case
    
  * Example of a Positive Test Case
  
  ![image](https://user-images.githubusercontent.com/2145211/39098973-7796d9b6-4640-11e8-9ee2-16e654e7e9a1.png)

  * Example of a Negative Test Case
  * We are forcing an error and we are checking the error which was thrown was the error which we are expecting.
  
  ![image](https://user-images.githubusercontent.com/2145211/39098978-9c2df8f4-4640-11e8-9cbb-ad179bf97c1b.png)
  
  * Example of User/Role/Profile based Test Case
  * Use System.runAs() method for this type of test cases.
  
  ![image](https://user-images.githubusercontent.com/2145211/39099010-f6537b38-4640-11e8-87f2-03ce7bbdacc2.png)
  
### Rule 8: Write Useful Test Cases

  * Every test needs to use assertions
    * Assert(A==B,"Reason why Assert Failed")
    * AssertEquals(A==B, "Reason why Assert Failed")
    * AssertNotEquals(A==B, "Reason why Assert Failed")
    
### Rule 9: Test One thing at a time

  * Unit Test - Test Driven Development (TDD)
  
  ![image](https://user-images.githubusercontent.com/2145211/39099034-79e9c236-4641-11e8-9db0-4f9d96ec47e9.png)

## Credits

  * Apex 10 Commandments - https://www.youtube.com/watch?v=yqJZDmW1yLI
