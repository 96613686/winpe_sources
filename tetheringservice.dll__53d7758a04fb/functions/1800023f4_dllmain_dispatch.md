# dllmain_dispatch

- ea: `0x1800023f4`
- end: `0x18000251b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002530`

## callees

- `0x180002210`
- `0x1800023f4`
- `0x18000268c`
- `0x180002ac0`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180041A30 <= 0 )
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
0x1800023f4  mov     rax, rsp
0x1800023f7  mov     [rax+20h], rbx
0x1800023fb  mov     [rax+18h], r8
0x1800023ff  mov     [rax+10h], edx
0x180002402  mov     [rax+8], rcx
0x180002406  push    rsi
0x180002407  push    rdi
0x180002408  push    r14
0x18000240a  sub     rsp, 40h
0x18000240e  mov     rsi, r8
0x180002411  mov     edi, edx
0x180002413  mov     r14, rcx
0x180002416  test    edx, edx
0x180002418  jnz     short loc_180002429
0x18000241a  cmp     cs:dword_180041A30, edx
0x180002420  jg      short loc_180002429
0x180002422  xor     eax, eax
0x180002424  jmp     loc_18000250D
0x180002429  lea     eax, [rdx-1]
0x18000242c  cmp     eax, 1
0x18000242f  ja      short loc_180002470
0x180002431  mov     rax, cs:_pRawDllMain
0x180002438  test    rax, rax
0x18000243b  jnz     short loc_180002442
0x18000243d  lea     ebx, [rax+1]
0x180002440  jmp     short loc_180002449
0x180002442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002447  mov     ebx, eax
0x180002449  mov     [rsp+58h+var_28], ebx
0x18000244d  test    ebx, ebx
0x18000244f  jz      loc_180002503
0x180002455  mov     r8, rsi
0x180002458  mov     edx, edi
0x18000245a  mov     rcx, r14
0x18000245d  call    dllmain_crt_dispatch
0x180002462  mov     ebx, eax
0x180002464  mov     [rsp+58h+var_28], eax
0x180002468  test    eax, eax
0x18000246a  jz      loc_180002503
0x180002470  mov     r8, rsi; lpvReserved
0x180002473  mov     edx, edi; fdwReason
0x180002475  mov     rcx, r14; hinstDLL
0x180002478  call    DllMain
0x18000247d  mov     ebx, eax
0x18000247f  mov     [rsp+58h+var_28], eax
0x180002483  cmp     edi, 1
0x180002486  jnz     short loc_1800024BF
0x180002488  test    eax, eax
0x18000248a  jnz     short loc_1800024BF
0x18000248c  mov     r8, rsi; lpvReserved
0x18000248f  xor     edx, edx; fdwReason
0x180002491  mov     rcx, r14; hinstDLL
0x180002494  call    DllMain
0x180002499  mov     r8, rsi
0x18000249c  xor     edx, edx
0x18000249e  mov     rcx, r14
0x1800024a1  call    dllmain_crt_dispatch
0x1800024a6  mov     rax, cs:_pRawDllMain
0x1800024ad  test    rax, rax
0x1800024b0  jz      short loc_1800024BF
0x1800024b2  mov     r8, rsi
0x1800024b5  xor     edx, edx
0x1800024b7  mov     rcx, r14
0x1800024ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024bf  test    edi, edi
0x1800024c1  jz      short loc_1800024C8
0x1800024c3  cmp     edi, 3
0x1800024c6  jnz     short loc_180002503
0x1800024c8  mov     r8, rsi
0x1800024cb  mov     edx, edi
0x1800024cd  mov     rcx, r14
0x1800024d0  call    dllmain_crt_dispatch
0x1800024d5  mov     ebx, eax
0x1800024d7  mov     [rsp+58h+var_28], eax
0x1800024db  test    eax, eax
0x1800024dd  jz      short loc_180002503
0x1800024df  mov     rax, cs:_pRawDllMain
0x1800024e6  test    rax, rax
0x1800024e9  jnz     short loc_1800024F0
0x1800024eb  lea     ebx, [rax+1]
0x1800024ee  jmp     short loc_1800024FF
0x1800024f0  mov     r8, rsi
0x1800024f3  mov     edx, edi
0x1800024f5  mov     rcx, r14
0x1800024f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024fd  mov     ebx, eax
0x1800024ff  mov     [rsp+58h+var_28], ebx
0x180002503  jmp     short loc_18000250B
0x180002505  xor     ebx, ebx
0x180002507  mov     [rsp+58h+var_28], ebx
0x18000250b  mov     eax, ebx
0x18000250d  mov     rbx, [rsp+58h+arg_18]
0x180002512  add     rsp, 40h
0x180002516  pop     r14
0x180002518  pop     rdi
0x180002519  pop     rsi
0x18000251a  retn
0x1800316cc  push    rbp
0x1800316ce  sub     rsp, 30h
0x1800316d2  mov     rbp, rdx
0x1800316d5  mov     rax, [rcx]
0x1800316d8  mov     edx, [rax]
0x1800316da  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800316df  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800316e3  lea     r9, dllmain_crt_dispatch; int
0x1800316ea  mov     r8, [rbp+70h]; int
0x1800316ee  mov     edx, [rbp+68h]; int
0x1800316f1  mov     rcx, [rbp+60h]; int
0x1800316f5  call    __scrt_dllmain_exception_filter
0x1800316fa  nop
0x1800316fb  add     rsp, 30h
0x1800316ff  pop     rbp
0x180031700  retn
```
