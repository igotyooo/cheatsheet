## Change mode
### By numeric permission codes
#### Numeric permission codes
Read: `4`, write: `2`, execute: `1`.

#### Syntax
`$ chmod [-R] <x><y><z> <target>`</br>
Recursive: `-R`</br>
Sum of the owner permission codes: `x`</br>
Sum of the owner group permission codes: `y`</br>
Sum of the rest user/group permission codes: `z`</br>

### By character permission codes.
#### Character class codes
Owner: `u`</br>
Owner group: `g`</br>
The rest user/group: `o`</br>
All: `a` (default if not specified)</br>

#### Character operation codes
Add the permissions: `+`</br>
Remove the permissions: `-`</br>

#### Character permission code.
Read: `r`, write: `w`, execute: `e`.</br>

#### Syntax
`$ chmod [-R] <classes><operation><permissions>`</br>
Recursive: `-R`</br>

## Change owner.
#### Syntax
`chown [-R] <user>[:<group>] <target1> [<target2> ..]`</br>
Recursive: `-R`</br>
User to be the owner of the target: `user`</br>
Goup to be the owner of the target: `group`</br>
