# dllmain_dispatch

- ea: `0x18000141c`
- end: `0x180001543`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001550`

## callees

- `0x180001220`
- `0x18000141c`
- `0x180001a3c`
- `0x180008888`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180012330 <= 0 )
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
0x18000141c  mov     rax, rsp
0x18000141f  mov     [rax+20h], rbx
0x180001423  mov     [rax+18h], r8
0x180001427  mov     [rax+10h], edx
0x18000142a  mov     [rax+8], rcx
0x18000142e  push    rsi
0x18000142f  push    rdi
0x180001430  push    r14
0x180001432  sub     rsp, 40h
0x180001436  mov     rsi, r8
0x180001439  mov     edi, edx
0x18000143b  mov     r14, rcx
0x18000143e  test    edx, edx
0x180001440  jnz     short loc_180001451
0x180001442  cmp     cs:dword_180012330, edx
0x180001448  jg      short loc_180001451
0x18000144a  xor     eax, eax
0x18000144c  jmp     loc_180001535
0x180001451  lea     eax, [rdx-1]
0x180001454  cmp     eax, 1
0x180001457  ja      short loc_180001498
0x180001459  mov     rax, cs:_pRawDllMain
0x180001460  test    rax, rax
0x180001463  jnz     short loc_18000146A
0x180001465  lea     ebx, [rax+1]
0x180001468  jmp     short loc_180001471
0x18000146a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000146f  mov     ebx, eax
0x180001471  mov     [rsp+58h+var_28], ebx
0x180001475  test    ebx, ebx
0x180001477  jz      loc_18000152B
0x18000147d  mov     r8, rsi
0x180001480  mov     edx, edi
0x180001482  mov     rcx, r14
0x180001485  call    dllmain_crt_dispatch
0x18000148a  mov     ebx, eax
0x18000148c  mov     [rsp+58h+var_28], eax
0x180001490  test    eax, eax
0x180001492  jz      loc_18000152B
0x180001498  mov     r8, rsi; lpvReserved
0x18000149b  mov     edx, edi; fdwReason
0x18000149d  mov     rcx, r14; hinstDLL
0x1800014a0  call    DllMain
0x1800014a5  mov     ebx, eax
0x1800014a7  mov     [rsp+58h+var_28], eax
0x1800014ab  cmp     edi, 1
0x1800014ae  jnz     short loc_1800014E7
0x1800014b0  test    eax, eax
0x1800014b2  jnz     short loc_1800014E7
0x1800014b4  mov     r8, rsi; lpvReserved
0x1800014b7  xor     edx, edx; fdwReason
0x1800014b9  mov     rcx, r14; hinstDLL
0x1800014bc  call    DllMain
0x1800014c1  mov     r8, rsi
0x1800014c4  xor     edx, edx
0x1800014c6  mov     rcx, r14
0x1800014c9  call    dllmain_crt_dispatch
0x1800014ce  mov     rax, cs:_pRawDllMain
0x1800014d5  test    rax, rax
0x1800014d8  jz      short loc_1800014E7
0x1800014da  mov     r8, rsi
0x1800014dd  xor     edx, edx
0x1800014df  mov     rcx, r14
0x1800014e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014e7  test    edi, edi
0x1800014e9  jz      short loc_1800014F0
0x1800014eb  cmp     edi, 3
0x1800014ee  jnz     short loc_18000152B
0x1800014f0  mov     r8, rsi
0x1800014f3  mov     edx, edi
0x1800014f5  mov     rcx, r14
0x1800014f8  call    dllmain_crt_dispatch
0x1800014fd  mov     ebx, eax
0x1800014ff  mov     [rsp+58h+var_28], eax
0x180001503  test    eax, eax
0x180001505  jz      short loc_18000152B
0x180001507  mov     rax, cs:_pRawDllMain
0x18000150e  test    rax, rax
0x180001511  jnz     short loc_180001518
0x180001513  lea     ebx, [rax+1]
0x180001516  jmp     short loc_180001527
0x180001518  mov     r8, rsi
0x18000151b  mov     edx, edi
0x18000151d  mov     rcx, r14
0x180001520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001525  mov     ebx, eax
0x180001527  mov     [rsp+58h+var_28], ebx
0x18000152b  jmp     short loc_180001533
0x18000152d  xor     ebx, ebx
0x18000152f  mov     [rsp+58h+var_28], ebx
0x180001533  mov     eax, ebx
0x180001535  mov     rbx, [rsp+58h+arg_18]
0x18000153a  add     rsp, 40h
0x18000153e  pop     r14
0x180001540  pop     rdi
0x180001541  pop     rsi
0x180001542  retn
0x18000ccec  push    rbp
0x18000ccee  sub     rsp, 30h
0x18000ccf2  mov     rbp, rdx
0x18000ccf5  mov     rax, [rcx]
0x18000ccf8  mov     edx, [rax]
0x18000ccfa  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000ccff  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000cd03  lea     r9, dllmain_crt_dispatch; int
0x18000cd0a  mov     r8, [rbp+70h]; int
0x18000cd0e  mov     edx, [rbp+68h]; int
0x18000cd11  mov     rcx, [rbp+60h]; int
0x18000cd15  call    __scrt_dllmain_exception_filter
0x18000cd1a  nop
0x18000cd1b  add     rsp, 30h
0x18000cd1f  pop     rbp
0x18000cd20  retn
```
