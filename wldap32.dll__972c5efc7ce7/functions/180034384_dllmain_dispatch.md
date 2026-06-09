# dllmain_dispatch

- ea: `0x180034384`
- end: `0x1800344ab`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800344c0`

## callees

- `0x180024a60`
- `0x1800341a0`
- `0x180034384`
- `0x18003460c`
- `0x18004d010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800655B0 <= 0 )
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
0x180034384  mov     rax, rsp
0x180034387  mov     [rax+20h], rbx
0x18003438b  mov     [rax+18h], r8
0x18003438f  mov     [rax+10h], edx
0x180034392  mov     [rax+8], rcx
0x180034396  push    rsi
0x180034397  push    rdi
0x180034398  push    r14
0x18003439a  sub     rsp, 40h
0x18003439e  mov     rsi, r8
0x1800343a1  mov     edi, edx
0x1800343a3  mov     r14, rcx
0x1800343a6  test    edx, edx
0x1800343a8  jnz     short loc_1800343B9
0x1800343aa  cmp     cs:dword_1800655B0, edx
0x1800343b0  jg      short loc_1800343B9
0x1800343b2  xor     eax, eax
0x1800343b4  jmp     loc_18003449D
0x1800343b9  lea     eax, [rdx-1]
0x1800343bc  cmp     eax, 1
0x1800343bf  ja      short loc_180034400
0x1800343c1  mov     rax, cs:_pRawDllMain
0x1800343c8  test    rax, rax
0x1800343cb  jnz     short loc_1800343D2
0x1800343cd  lea     ebx, [rax+1]
0x1800343d0  jmp     short loc_1800343D9
0x1800343d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800343d7  mov     ebx, eax
0x1800343d9  mov     [rsp+58h+var_28], ebx
0x1800343dd  test    ebx, ebx
0x1800343df  jz      loc_180034493
0x1800343e5  mov     r8, rsi
0x1800343e8  mov     edx, edi
0x1800343ea  mov     rcx, r14
0x1800343ed  call    dllmain_crt_dispatch
0x1800343f2  mov     ebx, eax
0x1800343f4  mov     [rsp+58h+var_28], eax
0x1800343f8  test    eax, eax
0x1800343fa  jz      loc_180034493
0x180034400  mov     r8, rsi; lpvReserved
0x180034403  mov     edx, edi; fdwReason
0x180034405  mov     rcx, r14; hinstDLL
0x180034408  call    DllMain
0x18003440d  mov     ebx, eax
0x18003440f  mov     [rsp+58h+var_28], eax
0x180034413  cmp     edi, 1
0x180034416  jnz     short loc_18003444F
0x180034418  test    eax, eax
0x18003441a  jnz     short loc_18003444F
0x18003441c  mov     r8, rsi; lpvReserved
0x18003441f  xor     edx, edx; fdwReason
0x180034421  mov     rcx, r14; hinstDLL
0x180034424  call    DllMain
0x180034429  mov     r8, rsi
0x18003442c  xor     edx, edx
0x18003442e  mov     rcx, r14
0x180034431  call    dllmain_crt_dispatch
0x180034436  mov     rax, cs:_pRawDllMain
0x18003443d  test    rax, rax
0x180034440  jz      short loc_18003444F
0x180034442  mov     r8, rsi
0x180034445  xor     edx, edx
0x180034447  mov     rcx, r14
0x18003444a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003444f  test    edi, edi
0x180034451  jz      short loc_180034458
0x180034453  cmp     edi, 3
0x180034456  jnz     short loc_180034493
0x180034458  mov     r8, rsi
0x18003445b  mov     edx, edi
0x18003445d  mov     rcx, r14
0x180034460  call    dllmain_crt_dispatch
0x180034465  mov     ebx, eax
0x180034467  mov     [rsp+58h+var_28], eax
0x18003446b  test    eax, eax
0x18003446d  jz      short loc_180034493
0x18003446f  mov     rax, cs:_pRawDllMain
0x180034476  test    rax, rax
0x180034479  jnz     short loc_180034480
0x18003447b  lea     ebx, [rax+1]
0x18003447e  jmp     short loc_18003448F
0x180034480  mov     r8, rsi
0x180034483  mov     edx, edi
0x180034485  mov     rcx, r14
0x180034488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003448d  mov     ebx, eax
0x18003448f  mov     [rsp+58h+var_28], ebx
0x180034493  jmp     short loc_18003449B
0x180034495  xor     ebx, ebx
0x180034497  mov     [rsp+58h+var_28], ebx
0x18003449b  mov     eax, ebx
0x18003449d  mov     rbx, [rsp+58h+arg_18]
0x1800344a2  add     rsp, 40h
0x1800344a6  pop     r14
0x1800344a8  pop     rdi
0x1800344a9  pop     rsi
0x1800344aa  retn
0x18004c90d  push    rbp
0x18004c90f  sub     rsp, 30h
0x18004c913  mov     rbp, rdx
0x18004c916  mov     rax, [rcx]
0x18004c919  mov     edx, [rax]
0x18004c91b  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18004c920  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18004c924  lea     r9, dllmain_crt_dispatch; int
0x18004c92b  mov     r8, [rbp+70h]; int
0x18004c92f  mov     edx, [rbp+68h]; int
0x18004c932  mov     rcx, [rbp+60h]; int
0x18004c936  call    __scrt_dllmain_exception_filter
0x18004c93b  nop
0x18004c93c  add     rsp, 30h
0x18004c940  pop     rbp
0x18004c941  retn
```
