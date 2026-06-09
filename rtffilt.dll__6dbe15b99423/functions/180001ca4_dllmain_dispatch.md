# dllmain_dispatch

- ea: `0x180001ca4`
- end: `0x180001dcb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001de0`

## callees

- `0x180001ac0`
- `0x180001ca4`
- `0x180001fd0`
- `0x180002398`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180023510 <= 0 )
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
0x180001ca4  mov     rax, rsp
0x180001ca7  mov     [rax+20h], rbx
0x180001cab  mov     [rax+18h], r8
0x180001caf  mov     [rax+10h], edx
0x180001cb2  mov     [rax+8], rcx
0x180001cb6  push    rsi
0x180001cb7  push    rdi
0x180001cb8  push    r14
0x180001cba  sub     rsp, 40h
0x180001cbe  mov     rsi, r8
0x180001cc1  mov     edi, edx
0x180001cc3  mov     r14, rcx
0x180001cc6  test    edx, edx
0x180001cc8  jnz     short loc_180001CD9
0x180001cca  cmp     cs:dword_180023510, edx
0x180001cd0  jg      short loc_180001CD9
0x180001cd2  xor     eax, eax
0x180001cd4  jmp     loc_180001DBD
0x180001cd9  lea     eax, [rdx-1]
0x180001cdc  cmp     eax, 1
0x180001cdf  ja      short loc_180001D20
0x180001ce1  mov     rax, cs:_pRawDllMain
0x180001ce8  test    rax, rax
0x180001ceb  jnz     short loc_180001CF2
0x180001ced  lea     ebx, [rax+1]
0x180001cf0  jmp     short loc_180001CF9
0x180001cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cf7  mov     ebx, eax
0x180001cf9  mov     [rsp+58h+var_28], ebx
0x180001cfd  test    ebx, ebx
0x180001cff  jz      loc_180001DB3
0x180001d05  mov     r8, rsi
0x180001d08  mov     edx, edi
0x180001d0a  mov     rcx, r14
0x180001d0d  call    dllmain_crt_dispatch
0x180001d12  mov     ebx, eax
0x180001d14  mov     [rsp+58h+var_28], eax
0x180001d18  test    eax, eax
0x180001d1a  jz      loc_180001DB3
0x180001d20  mov     r8, rsi; lpvReserved
0x180001d23  mov     edx, edi; fdwReason
0x180001d25  mov     rcx, r14; hinstDLL
0x180001d28  call    DllMain
0x180001d2d  mov     ebx, eax
0x180001d2f  mov     [rsp+58h+var_28], eax
0x180001d33  cmp     edi, 1
0x180001d36  jnz     short loc_180001D6F
0x180001d38  test    eax, eax
0x180001d3a  jnz     short loc_180001D6F
0x180001d3c  mov     r8, rsi; lpvReserved
0x180001d3f  xor     edx, edx; fdwReason
0x180001d41  mov     rcx, r14; hinstDLL
0x180001d44  call    DllMain
0x180001d49  mov     r8, rsi
0x180001d4c  xor     edx, edx
0x180001d4e  mov     rcx, r14
0x180001d51  call    dllmain_crt_dispatch
0x180001d56  mov     rax, cs:_pRawDllMain
0x180001d5d  test    rax, rax
0x180001d60  jz      short loc_180001D6F
0x180001d62  mov     r8, rsi
0x180001d65  xor     edx, edx
0x180001d67  mov     rcx, r14
0x180001d6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d6f  test    edi, edi
0x180001d71  jz      short loc_180001D78
0x180001d73  cmp     edi, 3
0x180001d76  jnz     short loc_180001DB3
0x180001d78  mov     r8, rsi
0x180001d7b  mov     edx, edi
0x180001d7d  mov     rcx, r14
0x180001d80  call    dllmain_crt_dispatch
0x180001d85  mov     ebx, eax
0x180001d87  mov     [rsp+58h+var_28], eax
0x180001d8b  test    eax, eax
0x180001d8d  jz      short loc_180001DB3
0x180001d8f  mov     rax, cs:_pRawDllMain
0x180001d96  test    rax, rax
0x180001d99  jnz     short loc_180001DA0
0x180001d9b  lea     ebx, [rax+1]
0x180001d9e  jmp     short loc_180001DAF
0x180001da0  mov     r8, rsi
0x180001da3  mov     edx, edi
0x180001da5  mov     rcx, r14
0x180001da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001dad  mov     ebx, eax
0x180001daf  mov     [rsp+58h+var_28], ebx
0x180001db3  jmp     short loc_180001DBB
0x180001db5  xor     ebx, ebx
0x180001db7  mov     [rsp+58h+var_28], ebx
0x180001dbb  mov     eax, ebx
0x180001dbd  mov     rbx, [rsp+58h+arg_18]
0x180001dc2  add     rsp, 40h
0x180001dc6  pop     r14
0x180001dc8  pop     rdi
0x180001dc9  pop     rsi
0x180001dca  retn
0x18001998c  push    rbp
0x18001998e  sub     rsp, 30h
0x180019992  mov     rbp, rdx
0x180019995  mov     rax, [rcx]
0x180019998  mov     edx, [rax]
0x18001999a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001999f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800199a3  lea     r9, dllmain_crt_dispatch; int
0x1800199aa  mov     r8, [rbp+70h]; int
0x1800199ae  mov     edx, [rbp+68h]; int
0x1800199b1  mov     rcx, [rbp+60h]; int
0x1800199b5  call    __scrt_dllmain_exception_filter
0x1800199ba  nop
0x1800199bb  add     rsp, 30h
0x1800199bf  pop     rbp
0x1800199c0  retn
```
