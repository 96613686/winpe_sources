# dllmain_dispatch

- ea: `0x180006494`
- end: `0x1800065bb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800065d0`

## callees

- `0x1800062b0`
- `0x180006494`
- `0x180006824`
- `0x1800075d4`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180027110 <= 0 )
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
0x180006494  mov     rax, rsp
0x180006497  mov     [rax+20h], rbx
0x18000649b  mov     [rax+18h], r8
0x18000649f  mov     [rax+10h], edx
0x1800064a2  mov     [rax+8], rcx
0x1800064a6  push    rsi
0x1800064a7  push    rdi
0x1800064a8  push    r14
0x1800064aa  sub     rsp, 40h
0x1800064ae  mov     rsi, r8
0x1800064b1  mov     edi, edx
0x1800064b3  mov     r14, rcx
0x1800064b6  test    edx, edx
0x1800064b8  jnz     short loc_1800064C9
0x1800064ba  cmp     cs:dword_180027110, edx
0x1800064c0  jg      short loc_1800064C9
0x1800064c2  xor     eax, eax
0x1800064c4  jmp     loc_1800065AD
0x1800064c9  lea     eax, [rdx-1]
0x1800064cc  cmp     eax, 1
0x1800064cf  ja      short loc_180006510
0x1800064d1  mov     rax, cs:_pRawDllMain
0x1800064d8  test    rax, rax
0x1800064db  jnz     short loc_1800064E2
0x1800064dd  lea     ebx, [rax+1]
0x1800064e0  jmp     short loc_1800064E9
0x1800064e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064e7  mov     ebx, eax
0x1800064e9  mov     [rsp+58h+var_28], ebx
0x1800064ed  test    ebx, ebx
0x1800064ef  jz      loc_1800065A3
0x1800064f5  mov     r8, rsi
0x1800064f8  mov     edx, edi
0x1800064fa  mov     rcx, r14
0x1800064fd  call    dllmain_crt_dispatch
0x180006502  mov     ebx, eax
0x180006504  mov     [rsp+58h+var_28], eax
0x180006508  test    eax, eax
0x18000650a  jz      loc_1800065A3
0x180006510  mov     r8, rsi; lpvReserved
0x180006513  mov     edx, edi; fdwReason
0x180006515  mov     rcx, r14; hinstDLL
0x180006518  call    DllMain
0x18000651d  mov     ebx, eax
0x18000651f  mov     [rsp+58h+var_28], eax
0x180006523  cmp     edi, 1
0x180006526  jnz     short loc_18000655F
0x180006528  test    eax, eax
0x18000652a  jnz     short loc_18000655F
0x18000652c  mov     r8, rsi; lpvReserved
0x18000652f  xor     edx, edx; fdwReason
0x180006531  mov     rcx, r14; hinstDLL
0x180006534  call    DllMain
0x180006539  mov     r8, rsi
0x18000653c  xor     edx, edx
0x18000653e  mov     rcx, r14
0x180006541  call    dllmain_crt_dispatch
0x180006546  mov     rax, cs:_pRawDllMain
0x18000654d  test    rax, rax
0x180006550  jz      short loc_18000655F
0x180006552  mov     r8, rsi
0x180006555  xor     edx, edx
0x180006557  mov     rcx, r14
0x18000655a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000655f  test    edi, edi
0x180006561  jz      short loc_180006568
0x180006563  cmp     edi, 3
0x180006566  jnz     short loc_1800065A3
0x180006568  mov     r8, rsi
0x18000656b  mov     edx, edi
0x18000656d  mov     rcx, r14
0x180006570  call    dllmain_crt_dispatch
0x180006575  mov     ebx, eax
0x180006577  mov     [rsp+58h+var_28], eax
0x18000657b  test    eax, eax
0x18000657d  jz      short loc_1800065A3
0x18000657f  mov     rax, cs:_pRawDllMain
0x180006586  test    rax, rax
0x180006589  jnz     short loc_180006590
0x18000658b  lea     ebx, [rax+1]
0x18000658e  jmp     short loc_18000659F
0x180006590  mov     r8, rsi
0x180006593  mov     edx, edi
0x180006595  mov     rcx, r14
0x180006598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000659d  mov     ebx, eax
0x18000659f  mov     [rsp+58h+var_28], ebx
0x1800065a3  jmp     short loc_1800065AB
0x1800065a5  xor     ebx, ebx
0x1800065a7  mov     [rsp+58h+var_28], ebx
0x1800065ab  mov     eax, ebx
0x1800065ad  mov     rbx, [rsp+58h+arg_18]
0x1800065b2  add     rsp, 40h
0x1800065b6  pop     r14
0x1800065b8  pop     rdi
0x1800065b9  pop     rsi
0x1800065ba  retn
0x180017d62  push    rbp
0x180017d64  sub     rsp, 30h
0x180017d68  mov     rbp, rdx
0x180017d6b  mov     rax, [rcx]
0x180017d6e  mov     edx, [rax]
0x180017d70  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180017d75  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180017d79  lea     r9, dllmain_crt_dispatch; int
0x180017d80  mov     r8, [rbp+70h]; int
0x180017d84  mov     edx, [rbp+68h]; int
0x180017d87  mov     rcx, [rbp+60h]; int
0x180017d8b  call    __scrt_dllmain_exception_filter
0x180017d90  nop
0x180017d91  add     rsp, 30h
0x180017d95  pop     rbp
0x180017d96  retn
```
