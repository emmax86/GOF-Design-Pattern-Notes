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
* Favor object composition to class inheritance
	* Class Inheritence
		* Define a class's implementation in terms of another's
		* White box: most components of the parent are visible to the child
		* Changes in the design of the parent result in a necessity for changes in child
		* Advantages:
			* Straightforward
			* Determined statically during compile-time
			* Easy to modify the implementation being reused
			* When a subclass overrides some (but not all) operations, it can affect the operations it inherits as well, assuming they call overriden operations
		* Disadvantages:
			* Cannot change behaviors or implementations inherited from parent class during runtime
				* inheritance is determined compile-time
				* (Anecdote: Unless you have some kind of instrumentation library?)
			* Exposes child class to details of parent's implementation
				* If parent's implementation changes, it may be necessary to change child's implementation
				* _"Should any aspect of the inherited implementation not be appropriate for new problem domains, the parent class must be rewritten or replaced by something more appropriate."_
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
		* Advantages:
			* Defined dynamically during runtime through objects acquiring references to one another
			* Does not stop you from using any other objects you want
			* Does not break encapsulation; a composer's operations are fundamentally separate from the object it composes
			* Keeps objects focused on one task
			* Objects can be replaced during runtime as long as they have the same type
		* Disadvantages
			* Set of available components is rarely rich enough to accomplish everything you need in practice
	* Composition and inheritance complement each other, however
		* Reuse by inheritence allows us to make new components that are compatible with those used by composers
			* E.g. Extending a Button class to become a ToggleButton class which can still be used wherever a Button component is expected
	* The key is to avoid _overuse_ of inheritance. Where possible and (semantically appropriate), designs are made more _reusable_ and _simpler_ by preferring object composition.
