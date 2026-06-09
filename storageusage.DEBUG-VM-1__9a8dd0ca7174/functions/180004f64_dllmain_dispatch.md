# dllmain_dispatch

- ea: `0x180004f64`
- end: `0x18000508b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800050a0`

## callees

- `0x180004d80`
- `0x180004f64`
- `0x180005324`
- `0x180025654`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800404D0 <= 0 )
    return 0;
  if ( fdwReason - 1 > 1
    || (pRawDllMain ? (v7 = ((__int64 (*)(void))pRawDllMain)()) : (v7 = 1),
        v7 && (v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved)) != 0) )
  {
    v8 = DllMain(hinstDLL, fdwReason, lpvReserved);
    v7 = v8;
    if ( fdwReason == 1 && !v8 )
    {
      DllMain(hinstDLL, 0, lpvReserved);
      dllmain_crt_dispatch(hinstDLL, 0, lpvReserved);
      if ( pRawDllMain )
        pRawDllMain(hinstDLL, 0, lpvReserved);
    }
    if ( !fdwReason || fdwReason == 3 )
    {
      v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved);
      if ( v7 )
      {
        if ( pRawDllMain )
          return (unsigned int)pRawDllMain(hinstDLL, fdwReason, lpvReserved);
        else
          return 1;
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180004f64  mov     rax, rsp
0x180004f67  mov     [rax+20h], rbx
0x180004f6b  mov     [rax+18h], r8
0x180004f6f  mov     [rax+10h], edx
0x180004f72  mov     [rax+8], rcx
0x180004f76  push    rsi
0x180004f77  push    rdi
0x180004f78  push    r14
0x180004f7a  sub     rsp, 40h
0x180004f7e  mov     rsi, r8
0x180004f81  mov     edi, edx
0x180004f83  mov     r14, rcx
0x180004f86  test    edx, edx
0x180004f88  jnz     short loc_180004F99
0x180004f8a  cmp     cs:dword_1800404D0, edx
0x180004f90  jg      short loc_180004F99
0x180004f92  xor     eax, eax
0x180004f94  jmp     loc_18000507D
0x180004f99  lea     eax, [rdx-1]
0x180004f9c  cmp     eax, 1
0x180004f9f  ja      short loc_180004FE0
0x180004fa1  mov     rax, cs:_pRawDllMain
0x180004fa8  test    rax, rax
0x180004fab  jnz     short loc_180004FB2
0x180004fad  lea     ebx, [rax+1]
0x180004fb0  jmp     short loc_180004FB9
0x180004fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fb7  mov     ebx, eax
0x180004fb9  mov     [rsp+58h+var_28], ebx
0x180004fbd  test    ebx, ebx
0x180004fbf  jz      loc_180005073
0x180004fc5  mov     r8, rsi
0x180004fc8  mov     edx, edi
0x180004fca  mov     rcx, r14
0x180004fcd  call    dllmain_crt_dispatch
0x180004fd2  mov     ebx, eax
0x180004fd4  mov     [rsp+58h+var_28], eax
0x180004fd8  test    eax, eax
0x180004fda  jz      loc_180005073
0x180004fe0  mov     r8, rsi; lpvReserved
0x180004fe3  mov     edx, edi; fdwReason
0x180004fe5  mov     rcx, r14; hinstDLL
0x180004fe8  call    DllMain
0x180004fed  mov     ebx, eax
0x180004fef  mov     [rsp+58h+var_28], eax
0x180004ff3  cmp     edi, 1
0x180004ff6  jnz     short loc_18000502F
0x180004ff8  test    eax, eax
0x180004ffa  jnz     short loc_18000502F
0x180004ffc  mov     r8, rsi; lpvReserved
0x180004fff  xor     edx, edx; fdwReason
0x180005001  mov     rcx, r14; hinstDLL
0x180005004  call    DllMain
0x180005009  mov     r8, rsi
0x18000500c  xor     edx, edx
0x18000500e  mov     rcx, r14
0x180005011  call    dllmain_crt_dispatch
0x180005016  mov     rax, cs:_pRawDllMain
0x18000501d  test    rax, rax
0x180005020  jz      short loc_18000502F
0x180005022  mov     r8, rsi
0x180005025  xor     edx, edx
0x180005027  mov     rcx, r14
0x18000502a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000502f  test    edi, edi
0x180005031  jz      short loc_180005038
0x180005033  cmp     edi, 3
0x180005036  jnz     short loc_180005073
0x180005038  mov     r8, rsi
0x18000503b  mov     edx, edi
0x18000503d  mov     rcx, r14
0x180005040  call    dllmain_crt_dispatch
0x180005045  mov     ebx, eax
0x180005047  mov     [rsp+58h+var_28], eax
0x18000504b  test    eax, eax
0x18000504d  jz      short loc_180005073
0x18000504f  mov     rax, cs:_pRawDllMain
0x180005056  test    rax, rax
0x180005059  jnz     short loc_180005060
0x18000505b  lea     ebx, [rax+1]
0x18000505e  jmp     short loc_18000506F
0x180005060  mov     r8, rsi
0x180005063  mov     edx, edi
0x180005065  mov     rcx, r14
0x180005068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000506d  mov     ebx, eax
0x18000506f  mov     [rsp+58h+var_28], ebx
0x180005073  jmp     short loc_18000507B
0x180005075  xor     ebx, ebx
0x180005077  mov     [rsp+58h+var_28], ebx
0x18000507b  mov     eax, ebx
0x18000507d  mov     rbx, [rsp+58h+arg_18]
0x180005082  add     rsp, 40h
0x180005086  pop     r14
0x180005088  pop     rdi
0x180005089  pop     rsi
0x18000508a  retn
0x18002b06c  push    rbp
0x18002b06e  sub     rsp, 30h
0x18002b072  mov     rbp, rdx
0x18002b075  mov     rax, [rcx]
0x18002b078  mov     edx, [rax]
0x18002b07a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18002b07f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18002b083  lea     r9, dllmain_crt_dispatch; int
0x18002b08a  mov     r8, [rbp+70h]; int
0x18002b08e  mov     edx, [rbp+68h]; int
0x18002b091  mov     rcx, [rbp+60h]; int
0x18002b095  call    __scrt_dllmain_exception_filter
0x18002b09a  nop
0x18002b09b  add     rsp, 30h
0x18002b09f  pop     rbp
0x18002b0a0  retn
```
