# Walk through srcSAXEventDispatch
## Elijah Strayer, Roy Rojas Gutierrez

### Faults
- ```srcSAXEventDispatcher.hpp``` line 775 and 967 is_archive is used but never declared anywhere

### Inconsistencies

### Requirements Violations

### Possible Improvements
- Alphabetize imports and variables so they are easier to find and makes the code look cleaner
- ```srcSAXEventDispatcher.hpp``` line 541, 550 have comments with problems to fix
- ```srcSAXEventDispatcher.hpp``` Delete commented out deprecated code on lines 849-857, 312
