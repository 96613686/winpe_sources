# dllmain_dispatch

- ea: `0x1800088f4`
- end: `0x180008a1b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180008a30`

## callees

- `0x1800061b0`
- `0x180008710`
- `0x1800088f4`
- `0x180008be8`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18002A430 <= 0 )
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
0x1800088f4  mov     rax, rsp
0x1800088f7  mov     [rax+20h], rbx
0x1800088fb  mov     [rax+18h], r8
0x1800088ff  mov     [rax+10h], edx
0x180008902  mov     [rax+8], rcx
0x180008906  push    rsi
0x180008907  push    rdi
0x180008908  push    r14
0x18000890a  sub     rsp, 40h
0x18000890e  mov     rsi, r8
0x180008911  mov     edi, edx
0x180008913  mov     r14, rcx
0x180008916  test    edx, edx
0x180008918  jnz     short loc_180008929
0x18000891a  cmp     cs:dword_18002A430, edx
0x180008920  jg      short loc_180008929
0x180008922  xor     eax, eax
0x180008924  jmp     loc_180008A0D
0x180008929  lea     eax, [rdx-1]
0x18000892c  cmp     eax, 1
0x18000892f  ja      short loc_180008970
0x180008931  mov     rax, cs:_pRawDllMain
0x180008938  test    rax, rax
0x18000893b  jnz     short loc_180008942
0x18000893d  lea     ebx, [rax+1]
0x180008940  jmp     short loc_180008949
0x180008942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008947  mov     ebx, eax
0x180008949  mov     [rsp+58h+var_28], ebx
0x18000894d  test    ebx, ebx
0x18000894f  jz      loc_180008A03
0x180008955  mov     r8, rsi
0x180008958  mov     edx, edi
0x18000895a  mov     rcx, r14
0x18000895d  call    dllmain_crt_dispatch
0x180008962  mov     ebx, eax
0x180008964  mov     [rsp+58h+var_28], eax
0x180008968  test    eax, eax
0x18000896a  jz      loc_180008A03
0x180008970  mov     r8, rsi; lpvReserved
0x180008973  mov     edx, edi; fdwReason
0x180008975  mov     rcx, r14; hinstDLL
0x180008978  call    DllMain
0x18000897d  mov     ebx, eax
0x18000897f  mov     [rsp+58h+var_28], eax
0x180008983  cmp     edi, 1
0x180008986  jnz     short loc_1800089BF
0x180008988  test    eax, eax
0x18000898a  jnz     short loc_1800089BF
0x18000898c  mov     r8, rsi; lpvReserved
0x18000898f  xor     edx, edx; fdwReason
0x180008991  mov     rcx, r14; hinstDLL
0x180008994  call    DllMain
0x180008999  mov     r8, rsi
0x18000899c  xor     edx, edx
0x18000899e  mov     rcx, r14
0x1800089a1  call    dllmain_crt_dispatch
0x1800089a6  mov     rax, cs:_pRawDllMain
0x1800089ad  test    rax, rax
0x1800089b0  jz      short loc_1800089BF
0x1800089b2  mov     r8, rsi
0x1800089b5  xor     edx, edx
0x1800089b7  mov     rcx, r14
0x1800089ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089bf  test    edi, edi
0x1800089c1  jz      short loc_1800089C8
0x1800089c3  cmp     edi, 3
0x1800089c6  jnz     short loc_180008A03
0x1800089c8  mov     r8, rsi
0x1800089cb  mov     edx, edi
0x1800089cd  mov     rcx, r14
0x1800089d0  call    dllmain_crt_dispatch
0x1800089d5  mov     ebx, eax
0x1800089d7  mov     [rsp+58h+var_28], eax
0x1800089db  test    eax, eax
0x1800089dd  jz      short loc_180008A03
0x1800089df  mov     rax, cs:_pRawDllMain
0x1800089e6  test    rax, rax
0x1800089e9  jnz     short loc_1800089F0
0x1800089eb  lea     ebx, [rax+1]
0x1800089ee  jmp     short loc_1800089FF
0x1800089f0  mov     r8, rsi
0x1800089f3  mov     edx, edi
0x1800089f5  mov     rcx, r14
0x1800089f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089fd  mov     ebx, eax
0x1800089ff  mov     [rsp+58h+var_28], ebx
0x180008a03  jmp     short loc_180008A0B
0x180008a05  xor     ebx, ebx
0x180008a07  mov     [rsp+58h+var_28], ebx
0x180008a0b  mov     eax, ebx
0x180008a0d  mov     rbx, [rsp+58h+arg_18]
0x180008a12  add     rsp, 40h
0x180008a16  pop     r14
0x180008a18  pop     rdi
0x180008a19  pop     rsi
0x180008a1a  retn
0x18001cdb1  push    rbp
0x18001cdb3  sub     rsp, 30h
0x18001cdb7  mov     rbp, rdx
0x18001cdba  mov     rax, [rcx]
0x18001cdbd  mov     edx, [rax]
0x18001cdbf  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001cdc4  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18001cdc8  lea     r9, dllmain_crt_dispatch; int
0x18001cdcf  mov     r8, [rbp+70h]; int
0x18001cdd3  mov     edx, [rbp+68h]; int
0x18001cdd6  mov     rcx, [rbp+60h]; int
0x18001cdda  call    __scrt_dllmain_exception_filter
0x18001cddf  nop
0x18001cde0  add     rsp, 30h
0x18001cde4  pop     rbp
0x18001cde5  retn
```
