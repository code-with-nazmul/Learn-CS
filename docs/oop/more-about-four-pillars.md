???+ "Polymorphism + Inheritence"
	```java
		class Animal{
			void sound(){
				System.out.println("Some sound");
			}
		}

		class Dog extends Animal{
			@Override
			void sound(){
				System.out.println("Bark");
			}
		}

		class Cat extends Animal{
			@Override
			void sound(){
				System.out.println("Meow");
			}
		}

		Animal a1 =       new Dog();
		// ^                    ^
		// |                    |
		// reference type      object type
		Animal a2 = new Cat();

		a1.sound(); // bark
		a2.sound(); // meow
	```

	Here runtime polymorphism happens. And I can write Animal a1 = new Dog() because Dog IS-A Animal. But when calling the sound() method, java goes to sound() method of child class because, object type is what matters here.

???+ "Abstract VS Interface"
	Read details about Abstract and Interface in [here](./four-pillars-oop.md) under abstraction section:

	| Feature | Interface | Abstract Class |
	| :--- | :--- | :--- |
	| **Keyword** | `implements` | `extends` |
	| **Inheritance** | A class can implement many | A class can extend only one |
	| **State (instance fields)** | No (only constants) | Yes |
	| **Constructors** | No | Yes |
	| **Method types** | Abstract, default, static | Abstract and concrete |
	| **Access modifiers** | Methods are public | Any (private, protected, etc.) |