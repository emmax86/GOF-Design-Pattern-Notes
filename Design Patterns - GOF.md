# Major Paradigms
* Program to an interface, not an implementation
	* Prefer interfaces defined by language Interfaces and Abstract Classes
		* Language should have little to no defined behavior in an abstract class
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
		* New functionality is obtained by assembling or _composing_ objects
