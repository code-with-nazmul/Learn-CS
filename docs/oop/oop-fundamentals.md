???+ "What is OOP?"
	OOP is a programming paradigm where programs are designed using objects that contain data and methods that operates on data. Its four main principes are encapsulation, abstraction, inheritence and polymorphism.

???+ "What is class?"
	A class is a blueprint or template that defines the data and methods that objects can have.

???+ "What is object"
	Object is an instance of class. It has its own state represented by its instance data and can use methods defined by its class.

???+ "Four principles of OOP in short"
	???+ "Encapsulation"
		Encapsulation is bundling data and the methods that operaton on that data within a class, while controlling access to the data using access modifiers to maintain its integrity.

		External code accesses them through public methods, often referred to as getters and setters. 

		It allows the class to control how data is accessed or modified.

	???+ "Abstraction"
		Abstraction is the process of hiding unnecessary implementation details and exposing only the essential functionality of an object.

	???+ "Inheritence"
		Inheritence is an OOP mechanism that allows the creation of new classes that inherit properties and methods of existing classes. 

		It promotes code reuse and establishes a hierarchical relationship between classes.

	???+ "Polymorphism"
		Polymorphism means many forms. It allows the same method to have different behaviors depending on the object.
		
		There are two types of polymorphism. We will discuss them later.

	???+ "Example of oop in code (java)"
		```java
		class Animal{
			private String name; // Encapsulation
			public Animal(String name){
				this.name = name;
			}
			public String getName(){
				return name;
			}
			
			abstract void makeSound(); // Abstraction
		}

		class Dog extends Animal{ // Inheritence
			public Dog(String name){
				super(name);
			}
			
			@Override // polymorphism
			void makeSound(){
				System.out.println("Dog barks");	
			}
		}

		```