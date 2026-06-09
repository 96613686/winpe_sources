# dllmain_dispatch

- ea: `0x18000e4b4`
- end: `0x18000e5db`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000e5f0`

## callees

- `0x18000d4e0`
- `0x18000e2d0`
- `0x18000e4b4`
- `0x18000e774`
- `0x18001d010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180029410 <= 0 )
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
0x18000e4b4  mov     rax, rsp
0x18000e4b7  mov     [rax+20h], rbx
0x18000e4bb  mov     [rax+18h], r8
0x18000e4bf  mov     [rax+10h], edx
0x18000e4c2  mov     [rax+8], rcx
0x18000e4c6  push    rsi
0x18000e4c7  push    rdi
0x18000e4c8  push    r14
0x18000e4ca  sub     rsp, 40h
0x18000e4ce  mov     rsi, r8
0x18000e4d1  mov     edi, edx
0x18000e4d3  mov     r14, rcx
0x18000e4d6  test    edx, edx
0x18000e4d8  jnz     short loc_18000E4E9
0x18000e4da  cmp     cs:dword_180029410, edx
0x18000e4e0  jg      short loc_18000E4E9
0x18000e4e2  xor     eax, eax
0x18000e4e4  jmp     loc_18000E5CD
0x18000e4e9  lea     eax, [rdx-1]
0x18000e4ec  cmp     eax, 1
0x18000e4ef  ja      short loc_18000E530
0x18000e4f1  mov     rax, cs:_pRawDllMain
0x18000e4f8  test    rax, rax
0x18000e4fb  jnz     short loc_18000E502
0x18000e4fd  lea     ebx, [rax+1]
0x18000e500  jmp     short loc_18000E509
0x18000e502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e507  mov     ebx, eax
0x18000e509  mov     [rsp+58h+var_28], ebx
0x18000e50d  test    ebx, ebx
0x18000e50f  jz      loc_18000E5C3
0x18000e515  mov     r8, rsi
0x18000e518  mov     edx, edi
0x18000e51a  mov     rcx, r14
0x18000e51d  call    dllmain_crt_dispatch
0x18000e522  mov     ebx, eax
0x18000e524  mov     [rsp+58h+var_28], eax
0x18000e528  test    eax, eax
0x18000e52a  jz      loc_18000E5C3
0x18000e530  mov     r8, rsi; lpvReserved
0x18000e533  mov     edx, edi; fdwReason
0x18000e535  mov     rcx, r14; hinstDLL
0x18000e538  call    DllMain
0x18000e53d  mov     ebx, eax
0x18000e53f  mov     [rsp+58h+var_28], eax
0x18000e543  cmp     edi, 1
0x18000e546  jnz     short loc_18000E57F
0x18000e548  test    eax, eax
0x18000e54a  jnz     short loc_18000E57F
0x18000e54c  mov     r8, rsi; lpvReserved
0x18000e54f  xor     edx, edx; fdwReason
0x18000e551  mov     rcx, r14; hinstDLL
0x18000e554  call    DllMain
0x18000e559  mov     r8, rsi
0x18000e55c  xor     edx, edx
0x18000e55e  mov     rcx, r14
0x18000e561  call    dllmain_crt_dispatch
0x18000e566  mov     rax, cs:_pRawDllMain
0x18000e56d  test    rax, rax
0x18000e570  jz      short loc_18000E57F
0x18000e572  mov     r8, rsi
0x18000e575  xor     edx, edx
0x18000e577  mov     rcx, r14
0x18000e57a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e57f  test    edi, edi
0x18000e581  jz      short loc_18000E588
0x18000e583  cmp     edi, 3
0x18000e586  jnz     short loc_18000E5C3
0x18000e588  mov     r8, rsi
0x18000e58b  mov     edx, edi
0x18000e58d  mov     rcx, r14
0x18000e590  call    dllmain_crt_dispatch
0x18000e595  mov     ebx, eax
0x18000e597  mov     [rsp+58h+var_28], eax
0x18000e59b  test    eax, eax
0x18000e59d  jz      short loc_18000E5C3
0x18000e59f  mov     rax, cs:_pRawDllMain
0x18000e5a6  test    rax, rax
0x18000e5a9  jnz     short loc_18000E5B0
0x18000e5ab  lea     ebx, [rax+1]
0x18000e5ae  jmp     short loc_18000E5BF
0x18000e5b0  mov     r8, rsi
0x18000e5b3  mov     edx, edi
0x18000e5b5  mov     rcx, r14
0x18000e5b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5bd  mov     ebx, eax
0x18000e5bf  mov     [rsp+58h+var_28], ebx
0x18000e5c3  jmp     short loc_18000E5CB
0x18000e5c5  xor     ebx, ebx
0x18000e5c7  mov     [rsp+58h+var_28], ebx
0x18000e5cb  mov     eax, ebx
0x18000e5cd  mov     rbx, [rsp+58h+arg_18]
0x18000e5d2  add     rsp, 40h
0x18000e5d6  pop     r14
0x18000e5d8  pop     rdi
0x18000e5d9  pop     rsi
0x18000e5da  retn
0x18001c9f6  push    rbp
0x18001c9f8  sub     rsp, 30h
0x18001c9fc  mov     rbp, rdx
0x18001c9ff  mov     rax, [rcx]
0x18001ca02  mov     edx, [rax]
0x18001ca04  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001ca09  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18001ca0d  lea     r9, dllmain_crt_dispatch; int
0x18001ca14  mov     r8, [rbp+70h]; int
0x18001ca18  mov     edx, [rbp+68h]; int
0x18001ca1b  mov     rcx, [rbp+60h]; int
0x18001ca1f  call    __scrt_dllmain_exception_filter
0x18001ca24  nop
0x18001ca25  add     rsp, 30h
0x18001ca29  pop     rbp
0x18001ca2a  retn
```
