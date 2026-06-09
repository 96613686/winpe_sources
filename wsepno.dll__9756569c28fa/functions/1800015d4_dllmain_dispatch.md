# dllmain_dispatch

- ea: `0x1800015d4`
- end: `0x1800016fb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001710`

## callees

- `0x1800013f0`
- `0x1800015d4`
- `0x1800018a4`
- `0x18000c1d8`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800158D0 <= 0 )
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
0x1800015d4  mov     rax, rsp
0x1800015d7  mov     [rax+20h], rbx
0x1800015db  mov     [rax+18h], r8
0x1800015df  mov     [rax+10h], edx
0x1800015e2  mov     [rax+8], rcx
0x1800015e6  push    rsi
0x1800015e7  push    rdi
0x1800015e8  push    r14
0x1800015ea  sub     rsp, 40h
0x1800015ee  mov     rsi, r8
0x1800015f1  mov     edi, edx
0x1800015f3  mov     r14, rcx
0x1800015f6  test    edx, edx
0x1800015f8  jnz     short loc_180001609
0x1800015fa  cmp     cs:dword_1800158D0, edx
0x180001600  jg      short loc_180001609
0x180001602  xor     eax, eax
0x180001604  jmp     loc_1800016ED
0x180001609  lea     eax, [rdx-1]
0x18000160c  cmp     eax, 1
0x18000160f  ja      short loc_180001650
0x180001611  mov     rax, cs:_pRawDllMain
0x180001618  test    rax, rax
0x18000161b  jnz     short loc_180001622
0x18000161d  lea     ebx, [rax+1]
0x180001620  jmp     short loc_180001629
0x180001622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001627  mov     ebx, eax
0x180001629  mov     [rsp+58h+var_28], ebx
0x18000162d  test    ebx, ebx
0x18000162f  jz      loc_1800016E3
0x180001635  mov     r8, rsi
0x180001638  mov     edx, edi
0x18000163a  mov     rcx, r14
0x18000163d  call    dllmain_crt_dispatch
0x180001642  mov     ebx, eax
0x180001644  mov     [rsp+58h+var_28], eax
0x180001648  test    eax, eax
0x18000164a  jz      loc_1800016E3
0x180001650  mov     r8, rsi; lpvReserved
0x180001653  mov     edx, edi; fdwReason
0x180001655  mov     rcx, r14; hinstDLL
0x180001658  call    DllMain
0x18000165d  mov     ebx, eax
0x18000165f  mov     [rsp+58h+var_28], eax
0x180001663  cmp     edi, 1
0x180001666  jnz     short loc_18000169F
0x180001668  test    eax, eax
0x18000166a  jnz     short loc_18000169F
0x18000166c  mov     r8, rsi; lpvReserved
0x18000166f  xor     edx, edx; fdwReason
0x180001671  mov     rcx, r14; hinstDLL
0x180001674  call    DllMain
0x180001679  mov     r8, rsi
0x18000167c  xor     edx, edx
0x18000167e  mov     rcx, r14
0x180001681  call    dllmain_crt_dispatch
0x180001686  mov     rax, cs:_pRawDllMain
0x18000168d  test    rax, rax
0x180001690  jz      short loc_18000169F
0x180001692  mov     r8, rsi
0x180001695  xor     edx, edx
0x180001697  mov     rcx, r14
0x18000169a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000169f  test    edi, edi
0x1800016a1  jz      short loc_1800016A8
0x1800016a3  cmp     edi, 3
0x1800016a6  jnz     short loc_1800016E3
0x1800016a8  mov     r8, rsi
0x1800016ab  mov     edx, edi
0x1800016ad  mov     rcx, r14
0x1800016b0  call    dllmain_crt_dispatch
0x1800016b5  mov     ebx, eax
0x1800016b7  mov     [rsp+58h+var_28], eax
0x1800016bb  test    eax, eax
0x1800016bd  jz      short loc_1800016E3
0x1800016bf  mov     rax, cs:_pRawDllMain
0x1800016c6  test    rax, rax
0x1800016c9  jnz     short loc_1800016D0
0x1800016cb  lea     ebx, [rax+1]
0x1800016ce  jmp     short loc_1800016DF
0x1800016d0  mov     r8, rsi
0x1800016d3  mov     edx, edi
0x1800016d5  mov     rcx, r14
0x1800016d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016dd  mov     ebx, eax
0x1800016df  mov     [rsp+58h+var_28], ebx
0x1800016e3  jmp     short loc_1800016EB
0x1800016e5  xor     ebx, ebx
0x1800016e7  mov     [rsp+58h+var_28], ebx
0x1800016eb  mov     eax, ebx
0x1800016ed  mov     rbx, [rsp+58h+arg_18]
0x1800016f2  add     rsp, 40h
0x1800016f6  pop     r14
0x1800016f8  pop     rdi
0x1800016f9  pop     rsi
0x1800016fa  retn
0x18000d87c  push    rbp
0x18000d87e  sub     rsp, 30h
0x18000d882  mov     rbp, rdx
0x18000d885  mov     rax, [rcx]
0x18000d888  mov     edx, [rax]
0x18000d88a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000d88f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000d893  lea     r9, dllmain_crt_dispatch; int
0x18000d89a  mov     r8, [rbp+70h]; int
0x18000d89e  mov     edx, [rbp+68h]; int
0x18000d8a1  mov     rcx, [rbp+60h]; int
0x18000d8a5  call    __scrt_dllmain_exception_filter
0x18000d8aa  nop
0x18000d8ab  add     rsp, 30h
0x18000d8af  pop     rbp
0x18000d8b0  retn
```
