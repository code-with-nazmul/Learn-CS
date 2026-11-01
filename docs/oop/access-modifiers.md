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