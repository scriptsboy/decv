DeCV 1.0b 
---------

- What is it
- Usage
- Possible problems

About
-----
DeCV is a decompiler for files protected with Code Virtualizer v1.3.8.0 by 
Oreans Technologies (www.oreans.com).

It's able to devirtualize macro-protected code back to a stack language used
by CV. If anyone is interested enough to write a CVL -> x86 converter, take
a look at recover_x86.py -- it it's not hard to extend this code to handle
more opcodes, but it's quite a bit of work. 

Usage
-----
DeCV was tested on IDA 6.2.x with IDAPython.

To use, open the file you want to deprotect and load decv.py script and wait.
DeCV will automatically perform all tasks.

Possible problems
-----------------
DeCV relies on IDA to correctly disassemble code. If you encounter problems 
during the handler parsing (basic block creation), manifested in errors like:
- outside handler: *address*
- Problem with getting mnemonic @ *address*
they are most likely caused by incorrect disasm generated by IDA. 

To fix, go to the address you see in the error message. If you see garbage
instructions or data mixed with code (DB xxh), undefine whole block by 
pressing 'u', and then directly convert to code, by pressing 'c'. Resulting
code should be cleaner and should not have garbage instructions, or DB xxh
stuff in it.

p_k
gdtr.wordpress.com
twitter.com/pa_kt

