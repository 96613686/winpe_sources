# dllmain_dispatch

- ea: `0x180036294`
- end: `0x1800363bb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800363d0`

## callees

- `0x18002f510`
- `0x1800360b0`
- `0x180036294`
- `0x180036560`
- `0x180045010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800512D0 <= 0 )
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
0x180036294  mov     rax, rsp
0x180036297  mov     [rax+20h], rbx
0x18003629b  mov     [rax+18h], r8
0x18003629f  mov     [rax+10h], edx
0x1800362a2  mov     [rax+8], rcx
0x1800362a6  push    rsi
0x1800362a7  push    rdi
0x1800362a8  push    r14
0x1800362aa  sub     rsp, 40h
0x1800362ae  mov     rsi, r8
0x1800362b1  mov     edi, edx
0x1800362b3  mov     r14, rcx
0x1800362b6  test    edx, edx
0x1800362b8  jnz     short loc_1800362C9
0x1800362ba  cmp     cs:dword_1800512D0, edx
0x1800362c0  jg      short loc_1800362C9
0x1800362c2  xor     eax, eax
0x1800362c4  jmp     loc_1800363AD
0x1800362c9  lea     eax, [rdx-1]
0x1800362cc  cmp     eax, 1
0x1800362cf  ja      short loc_180036310
0x1800362d1  mov     rax, cs:_pRawDllMain
0x1800362d8  test    rax, rax
0x1800362db  jnz     short loc_1800362E2
0x1800362dd  lea     ebx, [rax+1]
0x1800362e0  jmp     short loc_1800362E9
0x1800362e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800362e7  mov     ebx, eax
0x1800362e9  mov     [rsp+58h+var_28], ebx
0x1800362ed  test    ebx, ebx
0x1800362ef  jz      loc_1800363A3
0x1800362f5  mov     r8, rsi
0x1800362f8  mov     edx, edi
0x1800362fa  mov     rcx, r14
0x1800362fd  call    dllmain_crt_dispatch
0x180036302  mov     ebx, eax
0x180036304  mov     [rsp+58h+var_28], eax
0x180036308  test    eax, eax
0x18003630a  jz      loc_1800363A3
0x180036310  mov     r8, rsi; lpvReserved
0x180036313  mov     edx, edi; fdwReason
0x180036315  mov     rcx, r14; hinstDLL
0x180036318  call    DllMain
0x18003631d  mov     ebx, eax
0x18003631f  mov     [rsp+58h+var_28], eax
0x180036323  cmp     edi, 1
0x180036326  jnz     short loc_18003635F
0x180036328  test    eax, eax
0x18003632a  jnz     short loc_18003635F
0x18003632c  mov     r8, rsi; lpvReserved
0x18003632f  xor     edx, edx; fdwReason
0x180036331  mov     rcx, r14; hinstDLL
0x180036334  call    DllMain
0x180036339  mov     r8, rsi
0x18003633c  xor     edx, edx
0x18003633e  mov     rcx, r14
0x180036341  call    dllmain_crt_dispatch
0x180036346  mov     rax, cs:_pRawDllMain
0x18003634d  test    rax, rax
0x180036350  jz      short loc_18003635F
0x180036352  mov     r8, rsi
0x180036355  xor     edx, edx
0x180036357  mov     rcx, r14
0x18003635a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003635f  test    edi, edi
0x180036361  jz      short loc_180036368
0x180036363  cmp     edi, 3
0x180036366  jnz     short loc_1800363A3
0x180036368  mov     r8, rsi
0x18003636b  mov     edx, edi
0x18003636d  mov     rcx, r14
0x180036370  call    dllmain_crt_dispatch
0x180036375  mov     ebx, eax
0x180036377  mov     [rsp+58h+var_28], eax
0x18003637b  test    eax, eax
0x18003637d  jz      short loc_1800363A3
0x18003637f  mov     rax, cs:_pRawDllMain
0x180036386  test    rax, rax
0x180036389  jnz     short loc_180036390
0x18003638b  lea     ebx, [rax+1]
0x18003638e  jmp     short loc_18003639F
0x180036390  mov     r8, rsi
0x180036393  mov     edx, edi
0x180036395  mov     rcx, r14
0x180036398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003639d  mov     ebx, eax
0x18003639f  mov     [rsp+58h+var_28], ebx
0x1800363a3  jmp     short loc_1800363AB
0x1800363a5  xor     ebx, ebx
0x1800363a7  mov     [rsp+58h+var_28], ebx
0x1800363ab  mov     eax, ebx
0x1800363ad  mov     rbx, [rsp+58h+arg_18]
0x1800363b2  add     rsp, 40h
0x1800363b6  pop     r14
0x1800363b8  pop     rdi
0x1800363b9  pop     rsi
0x1800363ba  retn
0x1800440e2  push    rbp
0x1800440e4  sub     rsp, 30h
0x1800440e8  mov     rbp, rdx
0x1800440eb  mov     rax, [rcx]
0x1800440ee  mov     edx, [rax]
0x1800440f0  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800440f5  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800440f9  lea     r9, dllmain_crt_dispatch; int
0x180044100  mov     r8, [rbp+70h]; int
0x180044104  mov     edx, [rbp+68h]; int
0x180044107  mov     rcx, [rbp+60h]; int
0x18004410b  call    __scrt_dllmain_exception_filter
0x180044110  nop
0x180044111  add     rsp, 30h
0x180044115  pop     rbp
0x180044116  retn
```
