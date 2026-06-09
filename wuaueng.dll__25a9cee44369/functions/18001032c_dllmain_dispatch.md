# dllmain_dispatch

- ea: `0x18001032c`
- end: `0x180010453`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180010460`

## callees

- `0x1800064e0`
- `0x18000fd98`
- `0x180010130`
- `0x18001032c`
- `0x1800159b0`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180021824 <= 0 )
    return 0;
  if ( fdwReason - 1 > 1
    || (pRawDllMain ? (v7 = ((__int64 (*)(void))pRawDllMain)()) : (v7 = 1),
        v7 && (v7 = dllmain_crt_dispatch((__int64)hinstDLL, fdwReason, (__int64)lpvReserved)) != 0) )
  {
    v8 = DllMain(hinstDLL, fdwReason, lpvReserved);
    v7 = v8;
    if ( fdwReason == 1 && !v8 )
    {
      DllMain(hinstDLL, 0, lpvReserved);
      dllmain_crt_dispatch((__int64)hinstDLL, 0, (__int64)lpvReserved);
      if ( pRawDllMain )
        pRawDllMain(hinstDLL, 0, lpvReserved);
    }
    if ( !fdwReason || fdwReason == 3 )
    {
      v7 = dllmain_crt_dispatch((__int64)hinstDLL, fdwReason, (__int64)lpvReserved);
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
0x18001032c  mov     rax, rsp
0x18001032f  mov     [rax+20h], rbx
0x180010333  mov     [rax+18h], r8
0x180010337  mov     [rax+10h], edx
0x18001033a  mov     [rax+8], rcx
0x18001033e  push    rsi
0x18001033f  push    rdi
0x180010340  push    r14
0x180010342  sub     rsp, 40h
0x180010346  mov     rsi, r8
0x180010349  mov     edi, edx
0x18001034b  mov     r14, rcx
0x18001034e  test    edx, edx
0x180010350  jnz     short loc_180010361
0x180010352  cmp     cs:dword_180021824, edx
0x180010358  jg      short loc_180010361
0x18001035a  xor     eax, eax
0x18001035c  jmp     loc_180010445
0x180010361  lea     eax, [rdx-1]
0x180010364  cmp     eax, 1
0x180010367  ja      short loc_1800103A8
0x180010369  mov     rax, cs:_pRawDllMain
0x180010370  test    rax, rax
0x180010373  jnz     short loc_18001037A
0x180010375  lea     ebx, [rax+1]
0x180010378  jmp     short loc_180010381
0x18001037a  call    _guard_dispatch_icall
0x18001037f  mov     ebx, eax
0x180010381  mov     [rsp+58h+var_28], ebx
0x180010385  test    ebx, ebx
0x180010387  jz      loc_18001043B
0x18001038d  mov     r8, rsi
0x180010390  mov     edx, edi
0x180010392  mov     rcx, r14
0x180010395  call    dllmain_crt_dispatch
0x18001039a  mov     ebx, eax
0x18001039c  mov     [rsp+58h+var_28], eax
0x1800103a0  test    eax, eax
0x1800103a2  jz      loc_18001043B
0x1800103a8  mov     r8, rsi; lpvReserved
0x1800103ab  mov     edx, edi; fdwReason
0x1800103ad  mov     rcx, r14; hinstDLL
0x1800103b0  call    DllMain
0x1800103b5  mov     ebx, eax
0x1800103b7  mov     [rsp+58h+var_28], eax
0x1800103bb  cmp     edi, 1
0x1800103be  jnz     short loc_1800103F7
0x1800103c0  test    eax, eax
0x1800103c2  jnz     short loc_1800103F7
0x1800103c4  mov     r8, rsi; lpvReserved
0x1800103c7  xor     edx, edx; fdwReason
0x1800103c9  mov     rcx, r14; hinstDLL
0x1800103cc  call    DllMain
0x1800103d1  mov     r8, rsi
0x1800103d4  xor     edx, edx
0x1800103d6  mov     rcx, r14
0x1800103d9  call    dllmain_crt_dispatch
0x1800103de  mov     rax, cs:_pRawDllMain
0x1800103e5  test    rax, rax
0x1800103e8  jz      short loc_1800103F7
0x1800103ea  mov     r8, rsi
0x1800103ed  xor     edx, edx
0x1800103ef  mov     rcx, r14
0x1800103f2  call    _guard_dispatch_icall
0x1800103f7  test    edi, edi
0x1800103f9  jz      short loc_180010400
0x1800103fb  cmp     edi, 3
0x1800103fe  jnz     short loc_18001043B
0x180010400  mov     r8, rsi
0x180010403  mov     edx, edi
0x180010405  mov     rcx, r14
0x180010408  call    dllmain_crt_dispatch
0x18001040d  mov     ebx, eax
0x18001040f  mov     [rsp+58h+var_28], eax
0x180010413  test    eax, eax
0x180010415  jz      short loc_18001043B
0x180010417  mov     rax, cs:_pRawDllMain
0x18001041e  test    rax, rax
0x180010421  jnz     short loc_180010428
0x180010423  lea     ebx, [rax+1]
0x180010426  jmp     short loc_180010437
0x180010428  mov     r8, rsi
0x18001042b  mov     edx, edi
0x18001042d  mov     rcx, r14
0x180010430  call    _guard_dispatch_icall
0x180010435  mov     ebx, eax
0x180010437  mov     [rsp+58h+var_28], ebx
0x18001043b  jmp     short loc_180010443
0x18001043d  xor     ebx, ebx
0x18001043f  mov     [rsp+58h+var_28], ebx
0x180010443  mov     eax, ebx
0x180010445  mov     rbx, [rsp+58h+arg_18]
0x18001044a  add     rsp, 40h
0x18001044e  pop     r14
0x180010450  pop     rdi
0x180010451  pop     rsi
0x180010452  retn
0x180016c4f  push    rbp
0x180016c51  sub     rsp, 30h
0x180016c55  mov     rbp, rdx
0x180016c58  mov     rax, [rcx]
0x180016c5b  mov     edx, [rax]
0x180016c5d  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180016c62  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180016c66  lea     r9, dllmain_crt_dispatch; int
0x180016c6d  mov     r8, [rbp+70h]; int
0x180016c71  mov     edx, [rbp+68h]; int
0x180016c74  mov     rcx, [rbp+60h]; int
0x180016c78  call    __scrt_dllmain_exception_filter
0x180016c7d  nop
0x180016c7e  add     rsp, 30h
0x180016c82  pop     rbp
0x180016c83  retn
```
