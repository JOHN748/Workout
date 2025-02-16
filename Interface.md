- It is one of the component in java which is similar to class.
- We use interface to achieve 100% of abstraction and multiple inheritance.
#### Note:
- non-static methods along with the body is not allowed in the interface because they'll reduce the abstraction percentage.
##### Example:
```java
// C.T.E

interface Bank{
	public void createAccount(){
	
	}
}
```
- interface is prefixed with abstract at the time of compile time and also the non-static methods without body also prefixed with public abstract.
##### Example:
```java
// Before Compile time

interface Bank{
	void createAccount();
}

// At Compile time

abstract interface Bank{
	public abstract void createAccount();
}
```
- static method along with the body will not reduce the abstraction percentage.
##### Example:
```java
interface Bank{
	public static void main(String[] args){
		System.out.println("Syed Tabrez");
	}
}
```
- If we are having any non-static variable in the interface, at the time of compile time compiler will prefix public static final to the variable.
##### Example:
```java 
// Before Compile time

interface Bank{
	String BNAME = "SBI";
	public static void main(Sreing[] args){
		System.out.println(BNAME);
	}
}

// After Compile time

interface Bank{
	public static final String BNAME = "SBI";
	public static void main(String[] args){
		System.out.println(BNAME);
	}
}
```
- interface will not allow constructor to achieve multiple inheritance.
- We cannot create object for the interface.
##### Example:
```java
// C.T.E
abstract interface Bank{
	public static void main(String[] args){
		Bank b = new Bank();
	}
}
```
- Multi line initializer both static and non-static is not allowed in the interface.
##### Example:
```java
// C.T.E
abstract interface Bank{
	static{}
	{}
}
```
- When it comes to interface final abstract or private abstract is compile time error.
- default methods are allowed in the interface from java8 for some business logics.
##### Example:
```java
// CTS 
interface Bank{
	default void createAccount(){
		
	}
}
```

#### Inheritance with respect to interface:
##### Example:
```java
interface Company{
	String CNAME = "TCS";
	void job();
}

class SoftwareEngineer implements Company{
	@override
	public void job(){
		System.out.println("Software Engineer in : "+CNAME);
	}
}

class MechancicalEngineer implements Company{
	@override
	public void job(){
		System.out.println("Mechanical Engineer in : "+CNAME);
	}
}

public class WBT1{
	public static void main(String[] args){
		Company c1 = new SoftwareEngineer();
		Company c2 = new MechanicalEngineer();

		c1.job();
		c2.job();
	}
} 
```
##### Output:
```
Software Engineer in : TCS
Mechanical Engineer in : TCS
```