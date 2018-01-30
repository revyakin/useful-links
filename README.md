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

