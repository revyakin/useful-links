# Useful Links

## Linux и ELF
- Линковка, сегменты и секции в ELF binary   
  [Injection of code into executable - Size question](https://security.stackexchange.com/a/157962)

- Linux x86 и x86_64 ABI    
  [What are the calling conventions for UNIX & Linux system calls on i386 and x86-64](https://stackoverflow.com/a/2538212/8496869)


## Windows и PE
- Хедер в котором описана структура PE  
  [wine/include/winnt.h](https://source.winehq.org/source/include/winnt.h)
  
  ### Windows x86_64 ABI
  - The arguments are passed in registers `RCX`, `RDX`, `R8`, and `R9`. 
  - If the arguments are **float**/**double**, they are passed in `XMM0L`, `XMM1L`, `XMM2L`, and `XMM3L`. 
  - 16 byte arguments are passed by reference. 
  
   The parameter area is always at the bottom of the stack (even if alloca is used),
   so that it will always be adjacent to the return address during any function call.
   It contains at least four entries, but always enough space to hold all the parameters
   needed by any function that may be called. **Note that space is always allocated for the
   register parameters, even if the parameters themselves are never homed to the stack;
   a callee is guaranteed that space has been allocated for all its parameters.**
   Home addresses are required for the register arguments so a contiguous area is available
   in case the called function needs to take the address of the argument list (va_list)
   or an individual argument. This area also provides a convenient place to save register
   arguments during thunk execution and as a debugging option (for example, it makes
   the arguments easy to find during debugging if they are stored at their home
   addresses in the prolog code). **Even if the called function has fewer than 4 parameters,
   these 4 stack locations are effectively owned by the called function, and may be used by
   the called function for other purposes besides saving parameter register values.**
   Thus the caller may not save information in this region of stack across a function call.

