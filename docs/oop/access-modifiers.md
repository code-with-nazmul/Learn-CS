Access modifiers are the mechanism that enforces encapsulation. 
Encapsulation is the principle - bundle data with the methods that work on it, and hide internal details. Access modifiers are the tool to gain encapsulation.


Access modifiers control who can see and use a class, field, or constructor. 

The 4 levels in short: 

| Access Modifier | Same Class | Same Package | Subclass (Other Package) | Everywhere |
| :--- | :---: | :---: | :---: | :---: |
| `private` | ✅ | ❌ | ❌ | ❌ |
| `default` (no keyword) | ✅ | ✅ | ❌ | ❌ |
| `protected` | ✅ | ✅ | ✅ | ❌ |
| `public` | ✅ | ✅ | ✅ | ✅ |


Example using code (java):
For understanding access modifiers I will use java code. In this example I have two packages: package and bank.
```java
  	package bank;

	public class Account {
		private double balance;          // only inside Account
		String branch = "Dhaka";         // default: same package only
		protected String owner;          // package + subclasses
		public String accountNo;         // anywhere

		public double getBalance() {     // controlled access
			return balance;
		}

		public void deposit(double amount) {
			if (amount > 0) balance += amount;
		}
	}
```

```java
	package app;
	import bank.Account;

	public class Main {
		public static void main(String[] args) {
			Account a = new Account();
			a.accountNo = "123";        // ✅ public
			a.deposit(500);             // ✅ public
			// a.balance = 100;         // ❌ private
			// a.branch;                // ❌ default (different package)
			// a.owner;                 // ❌ protected (not a subclass)
		}
	}
```