# testData

# Planning
Think of data in the application vs Test Case Data vs config data
  Test Case Data includes Test Case Values, Product Data used and Test Config data
	
There are no universal or perfect solutions, but there are multiple strategies

Static Data Prep - set up data before the test to ensure tests pass  
Dynamic Data Prep - set up data during test execution  
*	Avoids brittleness of static data  
*	Main downside is execution time  
*	Secondary issue is data cleanup  
	
	
# Best Practices
* Create as much data as possible during test execution  
* Use configs to define specifications, like what browser to use.  
*	Generally speaking test data should not be hard coded  

Config metadata: specifications like URL  
	Typically use flat text file  
Test Case Values (Scenario data): literal values: name, address, amount, maturity  
	Input values: product data, such as "home mortgage", "business mortgage", …  
	Discovery Data: Search web app config for particular values; we use something similar for localization. We look up the values for certain fields, buttons, …  
Potential Collisions  
	Automated tests running in parallel, manual testers sharing test data  
	Best practices:  
		a. Isolate the test environment: run in off hours, use containers  
		b. Treat any shared data as immutable; any tests that alter data should be run serially  
		c. Use dynamic data as much as possible  
![image](https://user-images.githubusercontent.com/12154513/130531136-2c1eeb7b-7392-4127-bcac-25bcd708a45f.png)
