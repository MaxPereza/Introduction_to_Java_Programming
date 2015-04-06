# Checkpoint Answers Chapter 6 #
## 6.1 ##
Some of the benefits of using methods are:  
- Faster development time by reuse of code  
- Reduces complexity of the code  
- Makes the code easier to maintain  

## 6.2 ##
A number of properties about a given method need to be decided before it can be defined:  
- What modifiers are suitable
- The type of the value, if any, that shall be returned
- The name of the method
- What parameters are needed as data for the method to be able to do its work
- What the method is intended to do and how it shall do it

When all of the above decisions have been made so can the method be defined. An example of a method definition looks like this:  
```Java  
public static int max(int num1, int num2) {  
	if (num1 > num2)  
		return num1;   
	else  
		return num2;  
}  
```  
The keywords public and static are examples of modifiers. The following int indicates that the method will return an int after being executed. The name of the method is max and it takes two int's as data parameters.

The part between the braces is the body of the loop and it this part that does the actual work. In this case so will it be checked which of the parameters that is biggest and the value of this parameter is returned to the caller of the method.  

A method is invoked by using the name of the method combined with the same number and type of actual parameter values as in the definition of the method.  

An invocation of the max method can for example look like this:  
```Java  
int biggestNumber = max(15, 42);  
```  
## 6.3 ##
The body of the max method can be shortened by the use of the conditional operator.  
```Java  
return ( num1 > num2 ) ? num1 : num2;  
```   
## 6.4 ##
A call to a method with a void return type is always a statement itself. A call to a value-returning method can also be a statement by itself.  
## 6.5 ##
The return type of the main method is void.  
## 6.6 ##
Omitting a return statement in a value-returning method will cause a syntax error.  

It is possible to have a return statement in a void function, this will end the execution of the method.  

It is a syntax error to have a void function return a value.  
## 6.7 ##
The term parameter is used to refer to the list of variables in a method declaration.  

The term argument refers to the actual values that are passed in when the method is invoked.  

A method signature is made up of the name and the parameter list of a given method. Note that the return type is not part of the method signature.  
## 6.8 ##
**a**  
```Java  
public static double getCommission(double SalesAmount, double commissionRate)
```  
**b**  
```Java  
public static void displayCalendar(int mont, int year)
```  
**c**  
```Java  
public static double squareRoot(double num)
```  
**d**  
```Java  
public static boolean isEven(int num)
```  
**e**  
```Java  
public static void displayMessage(String message, int count)
```  
**f**  
```Java  
public static double monthlyPayment(double loanAmount, int years, double interestRate)
```  
**g**  
```Java  
public static char toUpperCase(char letter)
```  
## 6.9 ##
```Java  
public class Test {
	public static method1(int n, m) {
		n += m;
		method2(3.4);
	}

	public static int method2(int n) {
		if (n > 0) 
			return 1;
		else if (n == 0) 
			return 0;
		else if (n < 0) 
			return -1;
	}
}
```
There are multiple errors in the above code.  

The return type for method1 is missing, it shall be void.

The type of the second parameter in method1 is missing, it shall most likely be of type int.  

The second method, named method2, is in method1 invoked with a double argument but the parameter of method2 is of typ int. This causes an syntax error, this can be fixed by changing the method signature of method2.  

The compiler will think that it is possible for method2 to not return any value in some situations. Remove the last if to make the code compile without changing the behavior. 

A fully corrected code look like this:
```Java  
public class Test {
	public static void method1(int n, int m) {
		n += m;
		method2(3.4);
	}

	public static int method2(double n) {
		if (n > 0)
			return 1;
		else if (n == 0)
			return 0;
		else
			return -1;
	}
}
```  