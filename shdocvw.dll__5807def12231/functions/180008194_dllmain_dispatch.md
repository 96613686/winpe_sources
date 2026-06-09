# dllmain_dispatch

- ea: `0x180008194`
- end: `0x1800082bb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800082d0`

## callees

- `0x1800020e0`
- `0x180007fb0`
- `0x180008194`
- `0x18000841c`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800385D0 <= 0 )
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
0x180008194  mov     rax, rsp
0x180008197  mov     [rax+20h], rbx
0x18000819b  mov     [rax+18h], r8
0x18000819f  mov     [rax+10h], edx
0x1800081a2  mov     [rax+8], rcx
0x1800081a6  push    rsi
0x1800081a7  push    rdi
0x1800081a8  push    r14
0x1800081aa  sub     rsp, 40h
0x1800081ae  mov     rsi, r8
0x1800081b1  mov     edi, edx
0x1800081b3  mov     r14, rcx
0x1800081b6  test    edx, edx
0x1800081b8  jnz     short loc_1800081C9
0x1800081ba  cmp     cs:dword_1800385D0, edx
0x1800081c0  jg      short loc_1800081C9
0x1800081c2  xor     eax, eax
0x1800081c4  jmp     loc_1800082AD
0x1800081c9  lea     eax, [rdx-1]
0x1800081cc  cmp     eax, 1
0x1800081cf  ja      short loc_180008210
0x1800081d1  mov     rax, cs:_pRawDllMain
0x1800081d8  test    rax, rax
0x1800081db  jnz     short loc_1800081E2
0x1800081dd  lea     ebx, [rax+1]
0x1800081e0  jmp     short loc_1800081E9
0x1800081e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081e7  mov     ebx, eax
0x1800081e9  mov     [rsp+58h+var_28], ebx
0x1800081ed  test    ebx, ebx
0x1800081ef  jz      loc_1800082A3
0x1800081f5  mov     r8, rsi
0x1800081f8  mov     edx, edi
0x1800081fa  mov     rcx, r14
0x1800081fd  call    dllmain_crt_dispatch
0x180008202  mov     ebx, eax
0x180008204  mov     [rsp+58h+var_28], eax
0x180008208  test    eax, eax
0x18000820a  jz      loc_1800082A3
0x180008210  mov     r8, rsi; lpvReserved
0x180008213  mov     edx, edi; fdwReason
0x180008215  mov     rcx, r14; hinstDLL
0x180008218  call    DllMain
0x18000821d  mov     ebx, eax
0x18000821f  mov     [rsp+58h+var_28], eax
0x180008223  cmp     edi, 1
0x180008226  jnz     short loc_18000825F
0x180008228  test    eax, eax
0x18000822a  jnz     short loc_18000825F
0x18000822c  mov     r8, rsi; lpvReserved
0x18000822f  xor     edx, edx; fdwReason
0x180008231  mov     rcx, r14; hinstDLL
0x180008234  call    DllMain
0x180008239  mov     r8, rsi
0x18000823c  xor     edx, edx
0x18000823e  mov     rcx, r14
0x180008241  call    dllmain_crt_dispatch
0x180008246  mov     rax, cs:_pRawDllMain
0x18000824d  test    rax, rax
0x180008250  jz      short loc_18000825F
0x180008252  mov     r8, rsi
0x180008255  xor     edx, edx
0x180008257  mov     rcx, r14
0x18000825a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000825f  test    edi, edi
0x180008261  jz      short loc_180008268
0x180008263  cmp     edi, 3
0x180008266  jnz     short loc_1800082A3
0x180008268  mov     r8, rsi
0x18000826b  mov     edx, edi
0x18000826d  mov     rcx, r14
0x180008270  call    dllmain_crt_dispatch
0x180008275  mov     ebx, eax
0x180008277  mov     [rsp+58h+var_28], eax
0x18000827b  test    eax, eax
0x18000827d  jz      short loc_1800082A3
0x18000827f  mov     rax, cs:_pRawDllMain
0x180008286  test    rax, rax
0x180008289  jnz     short loc_180008290
0x18000828b  lea     ebx, [rax+1]
0x18000828e  jmp     short loc_18000829F
0x180008290  mov     r8, rsi
0x180008293  mov     edx, edi
0x180008295  mov     rcx, r14
0x180008298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000829d  mov     ebx, eax
0x18000829f  mov     [rsp+58h+var_28], ebx
0x1800082a3  jmp     short loc_1800082AB
0x1800082a5  xor     ebx, ebx
0x1800082a7  mov     [rsp+58h+var_28], ebx
0x1800082ab  mov     eax, ebx
0x1800082ad  mov     rbx, [rsp+58h+arg_18]
0x1800082b2  add     rsp, 40h
0x1800082b6  pop     r14
0x1800082b8  pop     rdi
0x1800082b9  pop     rsi
0x1800082ba  retn
0x180027ffe  push    rbp
0x180028000  sub     rsp, 30h
0x180028004  mov     rbp, rdx
0x180028007  mov     rax, [rcx]
0x18002800a  mov     edx, [rax]
0x18002800c  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180028011  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180028015  lea     r9, dllmain_crt_dispatch; int
0x18002801c  mov     r8, [rbp+70h]; int
0x180028020  mov     edx, [rbp+68h]; int
0x180028023  mov     rcx, [rbp+60h]; int
0x180028027  call    __scrt_dllmain_exception_filter
0x18002802c  nop
0x18002802d  add     rsp, 30h
0x180028031  pop     rbp
0x180028032  retn
```
