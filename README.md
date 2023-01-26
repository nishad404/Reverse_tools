                                       "ltrace" 
                                       
ltrace is a tools used in reverse engineering.ltrace is a debugging utility in Linux, used to display the calls a userspace application makes to shared libraries.This tools used for malware analysis when execute the malware.
   
   usage:: ltrace ./file_name
                                        
                                        
                                        
                                            "radare2"
                                        
 radare2 is a reverse engineering tools.I have solved many problem in tryhackem.It is a linux tools.It works in command.
 Installed size: 2.20 MB
 How to install: sudo apt install radare2
 usage::
 
 >>aaa
 >>>alf
 >>>pdf @main
  137: int main (char **argv);
│           ; var int32_t var_4h @ ebp-0x4
│           ; arg char **argv @ esp+0x24
│           0x0804849b      8d4c2404       lea ecx, [argv]
│           0x0804849f      83e4f0         and esp, 0xfffffff0
│           0x080484a2      ff71fc         push dword [ecx - 4]
│           0x080484a5      55             push ebp
│           0x080484a6      89e5           mov ebp, esp
│           0x080484a8      51             push ecx
│           0x080484a9      83ec04         sub esp, 4
│           0x080484ac      89c8           mov eax, ecx
│           0x080484ae      833802         cmp dword [eax], 2
│       ┌─< 0x080484b1      741d           je 0x80484d0
│       │   0x080484b3      8b4004         mov eax, dword [eax + 4]
│       │   0x080484b6      8b00           mov eax, dword [eax]
│       │   0x080484b8      83ec08         sub esp, 8
│       │   0x080484bb      50             push eax
│       │   0x080484bc      6860860408     push str.Usage:__s_password_n ; 0x8048660 ; "Usage: %s password\n"                                       
│       │   0x080484c1      e87afeffff     call sym.imp.printf         ; int printf(const char *format)                                             
│       │   0x080484c6      83c410         add esp, 0x10
│       │   0x080484c9      b801000000     mov eax, 1
│      ┌──< 0x080484ce      eb4c           jmp 0x804851c
│      │└─> 0x080484d0      8b4004         mov eax, dword [eax + 4]
│      │    0x080484d3      83c004         add eax, 4
│      │    0x080484d6      8b00           mov eax, dword [eax]
│      │    0x080484d8      83ec0c         sub esp, 0xc
│      │    0x080484db      50             push eax
│      │    0x080484dc      e89ffeffff     call sym.imp.atoi           ; int atoi(const char *str)                                                  
│      │    0x080484e1      83c410         add esp, 0x10
│      │    0x080484e4      3d0df0feca     cmp eax, 0xcafef00d
│      │┌─< 0x080484e9      7417           je 0x8048502
│      ││   0x080484eb      83ec0c         sub esp, 0xc
│      ││   0x080484ee      6874860408     push str.Access_denied.     ; 0x8048674 ; "Access denied."                                               
│      ││   0x080484f3      e858feffff     call sym.imp.puts           ; int puts(const char *s)                                                    
│      ││   0x080484f8      83c410         add esp, 0x10
│      ││   0x080484fb      b801000000     mov eax, 1
│     ┌───< 0x08048500      eb1a           jmp 0x804851c
│     ││└─> 0x08048502      83ec0c         sub esp, 0xc
│     ││    0x08048505      6883860408     push str.Access_granted.    ; 0x8048683 ; "Access granted."                                              
│     ││    0x0804850a      e841feffff     call sym.imp.puts           ; int puts(const char *s)                                                    
│     ││    0x0804850f      83c410         add esp, 0x10
│     ││    0x08048512      e80d000000     call sym.giveFlag
│     ││    0x08048517      b800000000     mov eax, 0
│     ││    ; CODE XREFS from main @ 0x80484ce, 0x8048500
│     └└──> 0x0804851c      8b4dfc         mov ecx, dword [var_4h]
│           0x0804851f      c9             leave
│           0x08048520      8d61fc         lea esp, [ecx - 4]
└           0x08048523      c3             ret
