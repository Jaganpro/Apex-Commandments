# Apex-Commandments
Curated Information about Apex Best Practices from Tech Sessions and Personal experience

## Apex Best Practices

### Don't use SOQL queries inside For-Loops
 
  * Queries in For Loops can break governer limits
  * Total Query limit per execution context is 100.
  
  ![image](https://user-images.githubusercontent.com/2145211/39098748-44d46406-463d-11e8-9295-165925257fe1.png)
  
  * Take SOQL queries out of For-Loop. Here in this case, we are using relationship queries.
  
  ![image](https://user-images.githubusercontent.com/2145211/39098763-7baa3cb2-463d-11e8-98f4-14dfd255110b.png)
  
### Don't use DML Operations inside For-Loops

  * Using DML Operations inside for loops can break governer limits. 
  * DML Operation Limit per execution context is 150.
  
  ![image](https://user-images.githubusercontent.com/2145211/39098785-e2667830-463d-11e8-8b79-eff95ff00318.png)
  
  * Add the instance variable to a list and then perform DML operation outside of For-loop
  
  ![image](https://user-images.githubusercontent.com/2145211/39098802-3d1f4252-463e-11e8-9669-761f2c29e9a5.png)

### 
