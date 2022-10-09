# Walk through srcSAXEventDispatch
## Elijah Strayer, Roy Rojas Gutierrez (Shared roles because of group size)

### Faults
- ```srcSAXEventDispatchUtilities.hpp``` const char* URI is capitalized in parameter but lowercase is 
used in the function body
- ```srcSAXEventDispatchUtilities.hpp``` function Nand and Nor use the same exact code just differnt
function name, breaks don't repeat yourself
- ```srcSAXEventDispatch.hpp``` line 67 srcSAXHandler class does not exist anywhere 


### Inconsistencies
- ```srcSAXEventDispatchUtilities.hpp``` As the code progresses, the amount of comments deminishes
- ```srcSAXSingleEventDispatcher.hpp``` line 39, 43 and 50, 54 method names are confusing, no dispatch 
 make me think dispatched would be set to false. 
- ```srcSAXEventDispatchUtilities.hpp``` line 88 all the strings and line 111 num_numspaces and namespaces
 are declared but not used anywhere
- ```srcSAXEventDispatchUtilities.hpp``` members that the constructor sets up should be private data members
- ```srcSAXEventDispatchUtilities.hpp``` line 229 should use setDispatched method
- ```srcSAXEventDispatchUtilities.hpp``` line 38 not all declared ParserStates are used and line 53 
not all srcDiff states are used
- ```srcSAXEventDispatchUtilities.hpp``` line 438 have only one for loop and call both functions in one loop
- ```srcSAXEventDispatch.hpp``` delete line 49 and just use line 57 CreateListenerHelper same thing with
CreateListenersImpl
- ```srcSAXEventDispatch.hpp``` CreateListenerImpl calls CreateListenerHelper which then calls CreateListenerImpl, its circular
- ```srcSAXEventDispatch.hpp``` line 89 there are two for loops when only one can be used to call both functions
- ```srcSAXEventDispatch.hpp``` AddEvents and RemoveEvents not used anywhere
- ```srcSAXEventDispatch.hpp``` make a function to handle setting up process_map and process_map2. a lot of repeated code
that is the same
- ```srcSAXEventDispatch.hpp``` Refactor to put document stuff (line 746-EOF) into its own class
- ```srcSAXEventDispatch.hpp``` xml functions do not have error handling for the file
- No valaidation for xml file, unless the xml library does this itself
 
### Requirements Violations
- Software is not easy to use

### Possible Improvements
- Alphabetize imports and variables so they are easier to find and makes the code look cleaner
- ```srcSAXEventDispatcher.hpp``` line 541, 550 have comments with problems to fix
- ```srcSAXEventDispatcher.hpp``` Delete commented out deprecated code on lines 849-857, 312
- It would be helpful if all files had a description at the top as to what its purpose is
- ```srcSAXEventDispatchUtilities.hpp``` There is a TODO comment in line 437
- Put classes in there own separate files, having some in the same file can get confusing
- Different variable names for data member and constructor parameters
- Methids/functions are big and some do more than one responsiblity
- ```srcSAXEventDispatchUtilities.hpp``` line 438 delete commented out const in parameters
- import ```srcSAXHandler.hpp``` is used but no file exist
- ```srcSAXEventDispatch.hpp``` line 38-65 are very confusing
- Confusion between dispatching and dipatched variables hard to keep track of
- ```srcSAXEventDispatch.hpp``` better name than process_map and process_map2
- ```srcSAXEventDispatch.hpp``` better name for AddEvent and AddEvents same with remove
- ```srcSAXEventDispatch.hpp``` line 830 start element has too much that it is doing should make separate functions
- ```srcSAXEventDispatch.hpp``` line 940-945 and 963-966 make code into a function for reuse
- ```srcSAXEventDispatch.hpp``` endRoot and endUnit are basically the same exact function make into one
- ```srcSAXEventDispatcher.hpp``` Extract method from the process_map and process_map2 since many of the statments seem to have similar logic
- ```srcSAXEventDispatcher.hpp``` line 775 and 967 is_archive is used but never declared anywhere
- ```srcSAXEventDispatcher.hpp``` endRoot and endUnit take arguments that are never used in their respective methods, same with endElement, URI is never used in the method
