# Major Paradigms
* Program to an interface, not an implementation
	* Prefer interfaces defined by language Interfaces and Abstract Classes
		* Type should have little to no defined behavior in an abstract class
		* Rather, use abstract classes much like interface classes: define mechanisms for interacting with object
	* Why:
		* Clients remain unaware of types used, and do not need to be aware. They ought only to know the interface to interact with the type
		* Clients remain unaware of classes that implement these objects, only the behaviors and interfaces of the abstract class
		* Leads to agnostic, reusable elements of software and reduces dependencies between components
		* _"Don't declare variables to be instances of particular concrete classes. Instead, commit only to an interface defined by an abstract class. You will find this to be a common theme of the design patterns in this book."_
* Favor object composition to class inheritence
	* Class Inheritence
		* Define a class's implementation in terms of another's
		* White box: most components of the parent are visible to the child
		* Changes in the design of the parent result in a necessity for changes in child
	* Object Composition
		* New functionality is obtained by assembling or _composing_ objects to get more complex functionality
		* Instead of extending from a class to add additional functionality, incorporate it into a new class
		* Objects must have well-defined interfaces for composer to interact with
		* From a Has-A vs. Is-A perspective, this is a Has-A relationship
			* In terms of functionality, a composer need not extend an object to augment or manipulate its behavior
			* Rather, the composer need only interface with the object
		* Black box: components of the object are hidden to the composer
			* Because the object has a well-defined interface, the object's implementation need not matter to the composer
		* Changes the the object's internal structure do not facilitate a necessity to change the composer, so long as the interface remains the same
