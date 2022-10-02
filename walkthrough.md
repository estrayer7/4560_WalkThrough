# Walk through srcSAXEventDispatch
## Elijah Strayer, Roy Rojas Gutierrez

### Faults
- ```srcSAXEventDispatcher.hpp``` line 775 and 967 is_archive is used but never declared anywhere
- - ```srcSAXEventDispatchUtilities.hpp``` const char* URI is capitalized in parameter but lowercase is used in the function body

### Inconsistencies
- ```srcSAXEventDispatchUtilities.hpp``` As the code progresses, the amount of comments deminishes
- ```srcSAXSingleEventDispatcher.hpp``` line 39, 43 and 50, 54 method names are confusing, no dispatch 
 make me think dispatched would be set to false. 
- ```srcSAXEventDispatchUtilities.hpp``` dipatcher, elementStack, depth, currentLineNumber are only 
used in the constructor and for nothing else get ride of them
- ```srcSAXEventDispatchUtilities.hpp``` line 88 all the strings are declared but not used anywhere
- ```srcSAXEventDispatchUtilities.hpp``` members that the constructor sets up should be private data members
 
### Requirements Violations

### Possible Improvements
- Alphabetize imports and variables so they are easier to find and makes the code look cleaner
- ```srcSAXEventDispatcher.hpp``` line 541, 550 have comments with problems to fix
- ```srcSAXEventDispatcher.hpp``` Delete commented out deprecated code on lines 849-857, 312
- It would be helpful if all files had a description at the top as to what its purpose is
- ```srcSAXEventDispatchUtilities.hpp``` There is a TODO comment in line 437
- Put classes in there own separate files, having some in the same file can get confusing
- Different variable names for data member and constructor parameters


