#Style Guide  

## Style and Documentation  

### Comments  
* State intentions  
```
// Function accepts an integer and calculate's the n'th fibonacci value in the fibonacci sequence.  
// Returns  calculated integer.  
int fibonacci(int n);    
```
* State input, output and high-level functionality  
```
// Function inserts a new node with templated data into the list before the node referred to by loc.  
// Returns iterator to the newly inserted node.  
// Receives constant reference to node data, iterator to the insertion location.  
// loc is permitted to be start() or end().  
iterator insertNode(iterator loc, const T& data);  
```
* Identify unstated details not included in name; e.g. unit of measurement  
``` double rectangleHeight;     // the height of the rectangle in cm  ```
* Avoid redundant comments.
    - It is not necessary to comment every operation in the code.  
    - Focus on the unstated and high-level intention and avoid commenting straightforward behaviour.   
```
// Example of redundant comments
for(int i=0;i<10;i++){       //this is a for loop, it runs 10 times  
    x = x+1;        //add 1 to x  
    y = y-1;        //subtract 1 from y  
}
```  
    
### Naming conventions   
#### Functions and Variables   
- Use camelCase (e.g. int thisIsAVariable = 0; ).  
- Use detailed and fully descriptive names.  
  void verifyUserName(string receivedUserName);  
- Avoid single letter variable names with the exception of loop counters or variables representing a known algorithm or equation ( e.g. the nth integer in a sequence).  
- Avoid generic variable names such as flag or file, add detail to describe the explicit purpose( e.g. bool isConnected = true; ).

#### Classes   
- Use UpperCase letter to mark each word in a class name.  
``` class CacheList {…} ```  
  
###### Member Variables  
- Use the underscore suffix format to declare class member variables.  
``` int dataMember_; ```    
  
### indentation    
##### Tabs and spacing
  - Tabs should consistently be represented by 4 spaces.   
  - Each block of code requires a tabbed indentation.  
```
void function (....){  
    for(....){  
      if(....){  
        switch(...){  
            ...
        }  
      }  
    }  
}
```
  
### Brackets  
- Use end of line style brackets for bracketed blocks.
```
for(...){   
    newNumber += 1;   
}  
```    
- Exceptions can be made for arrow notation of functions and brief function notation but should be avoided in order to maintain code readability.  
  
## Code Structure and Organization  
-	Use meaningful and descriptive file names for source code files.  
-	Group related functions and classes in the same file.  
-	Separate code blocks with blank lines to improve readability.  
-	Limit the length of lines to 80 characters to prevent horizontal scrolling.  
-	Avoid excessively long functions; break them up into smaller, more manageable functions.  
  
### Error Handling  
-	Use exceptions to handle errors and avoid using error codes.  
-	Clearly document what exceptions can be thrown and under what circumstances.  
-	Use descriptive error messages that provide context and guidance for resolving the issue.  
  
### Testing  
-	Write unit tests for all functions and classes. 
-	Use a consistent naming convention for test functions and test files.  
-	Write test cases for both valid and invalid input to ensure full code coverage.   
-	Document test results and ensure all tests pass before releasing code to production.  
  
### Version Control  
- Use version control software to track changes to the codebase.  
  
**GitHub**  
- Create working branches to make any changes to main branch code.  
- Once changes are committed to working branch create Pull Request to be reviewed prior to merging to main.  
  
### Best Practices for Design  
- Follow the SOLID principles of software development.  
- Use design patterns where appropriate.  
- Favor composition over inheritance where possible.  
- Write code that is maintainable and easy to modify.  
- Continuously refactor code to improve its quality and maintainability.  
  
#### SOLID Principles  
**Single Responsibility Principle (SRP):** A class should have only one responsibility. If a class has more than one responsibility, it becomes harder to change and maintain, and it can also lead to dependencies between different parts of the code.
**Open-Closed Principle (OCP):** A class should be open for extension but closed for modification. You should be able to extend the behavior of a class without modifying its code. Achieved by using inheritance, composition, or other techniques to add new functionality without changing existing code.  
  
**Liskov Substitution Principle (LSP):** Subtypes must be substitutable for their base types. This means that any subclass or derived class should be able to be used in place of its parent class without causing errors or unexpected behavior. Closely related to inheritance and polymorphism principles.  
  
**Interface Segregation Principle (ISP):** Clients should not be forced to depend on interfaces they do not use. Interfaces should be tailored to the specific needs of the client, rather than being overloaded with unnecessary methods or properties. Particularly important in large-scale software development, where interfaces can become complex and difficult to manage.  
  
**Dependency Inversion Principle (DIP):** Depend on abstractions, not concrete implementations. This means that high-level modules should not depend on low-level modules, but both should depend on abstractions. Abstractions should not depend on details; details should depend on abstractions. Often achieved through dependency injection, which allows for loose coupling between different parts of the code.  
