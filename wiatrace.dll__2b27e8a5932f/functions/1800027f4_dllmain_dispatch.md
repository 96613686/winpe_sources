# dllmain_dispatch

- ea: `0x1800027f4`
- end: `0x18000291b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002930`

## callees

- `0x1800023e4`
- `0x180002610`
- `0x1800027f4`
- `0x180002b84`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180007090 <= 0 )
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
0x1800027f4  mov     rax, rsp
0x1800027f7  mov     [rax+20h], rbx
0x1800027fb  mov     [rax+18h], r8
0x1800027ff  mov     [rax+10h], edx
0x180002802  mov     [rax+8], rcx
0x180002806  push    rsi
0x180002807  push    rdi
0x180002808  push    r14
0x18000280a  sub     rsp, 40h
0x18000280e  mov     rsi, r8
0x180002811  mov     edi, edx
0x180002813  mov     r14, rcx
0x180002816  test    edx, edx
0x180002818  jnz     short loc_180002829
0x18000281a  cmp     cs:dword_180007090, edx
0x180002820  jg      short loc_180002829
0x180002822  xor     eax, eax
0x180002824  jmp     loc_18000290D
0x180002829  lea     eax, [rdx-1]
0x18000282c  cmp     eax, 1
0x18000282f  ja      short loc_180002870
0x180002831  mov     rax, cs:_pRawDllMain
0x180002838  test    rax, rax
0x18000283b  jnz     short loc_180002842
0x18000283d  lea     ebx, [rax+1]
0x180002840  jmp     short loc_180002849
0x180002842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002847  mov     ebx, eax
0x180002849  mov     [rsp+58h+var_28], ebx
0x18000284d  test    ebx, ebx
0x18000284f  jz      loc_180002903
0x180002855  mov     r8, rsi
0x180002858  mov     edx, edi
0x18000285a  mov     rcx, r14
0x18000285d  call    dllmain_crt_dispatch
0x180002862  mov     ebx, eax
0x180002864  mov     [rsp+58h+var_28], eax
0x180002868  test    eax, eax
0x18000286a  jz      loc_180002903
0x180002870  mov     r8, rsi; lpvReserved
0x180002873  mov     edx, edi; fdwReason
0x180002875  mov     rcx, r14; hinstDLL
0x180002878  call    DllMain
0x18000287d  mov     ebx, eax
0x18000287f  mov     [rsp+58h+var_28], eax
0x180002883  cmp     edi, 1
0x180002886  jnz     short loc_1800028BF
0x180002888  test    eax, eax
0x18000288a  jnz     short loc_1800028BF
0x18000288c  mov     r8, rsi; lpvReserved
0x18000288f  xor     edx, edx; fdwReason
0x180002891  mov     rcx, r14; hinstDLL
0x180002894  call    DllMain
0x180002899  mov     r8, rsi
0x18000289c  xor     edx, edx
0x18000289e  mov     rcx, r14
0x1800028a1  call    dllmain_crt_dispatch
0x1800028a6  mov     rax, cs:_pRawDllMain
0x1800028ad  test    rax, rax
0x1800028b0  jz      short loc_1800028BF
0x1800028b2  mov     r8, rsi
0x1800028b5  xor     edx, edx
0x1800028b7  mov     rcx, r14
0x1800028ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028bf  test    edi, edi
0x1800028c1  jz      short loc_1800028C8
0x1800028c3  cmp     edi, 3
0x1800028c6  jnz     short loc_180002903
0x1800028c8  mov     r8, rsi
0x1800028cb  mov     edx, edi
0x1800028cd  mov     rcx, r14
0x1800028d0  call    dllmain_crt_dispatch
0x1800028d5  mov     ebx, eax
0x1800028d7  mov     [rsp+58h+var_28], eax
0x1800028db  test    eax, eax
0x1800028dd  jz      short loc_180002903
0x1800028df  mov     rax, cs:_pRawDllMain
0x1800028e6  test    rax, rax
0x1800028e9  jnz     short loc_1800028F0
0x1800028eb  lea     ebx, [rax+1]
0x1800028ee  jmp     short loc_1800028FF
0x1800028f0  mov     r8, rsi
0x1800028f3  mov     edx, edi
0x1800028f5  mov     rcx, r14
0x1800028f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028fd  mov     ebx, eax
0x1800028ff  mov     [rsp+58h+var_28], ebx
0x180002903  jmp     short loc_18000290B
0x180002905  xor     ebx, ebx
0x180002907  mov     [rsp+58h+var_28], ebx
0x18000290b  mov     eax, ebx
0x18000290d  mov     rbx, [rsp+58h+arg_18]
0x180002912  add     rsp, 40h
0x180002916  pop     r14
0x180002918  pop     rdi
0x180002919  pop     rsi
0x18000291a  retn
0x18000349c  push    rbp
0x18000349e  sub     rsp, 30h
0x1800034a2  mov     rbp, rdx
0x1800034a5  mov     rax, [rcx]
0x1800034a8  mov     edx, [rax]
0x1800034aa  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800034af  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800034b3  lea     r9, dllmain_crt_dispatch; int
0x1800034ba  mov     r8, [rbp+70h]; int
0x1800034be  mov     edx, [rbp+68h]; int
0x1800034c1  mov     rcx, [rbp+60h]; int
0x1800034c5  call    __scrt_dllmain_exception_filter
0x1800034ca  nop
0x1800034cb  add     rsp, 30h
0x1800034cf  pop     rbp
0x1800034d0  retn
```
