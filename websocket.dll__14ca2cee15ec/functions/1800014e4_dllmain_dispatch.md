# dllmain_dispatch

- ea: `0x1800014e4`
- end: `0x18000160b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001620`

## callees

- `0x180001300`
- `0x1800014e4`
- `0x180001834`
- `0x180002010`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180012350 <= 0 )
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
0x1800014e4  mov     rax, rsp
0x1800014e7  mov     [rax+20h], rbx
0x1800014eb  mov     [rax+18h], r8
0x1800014ef  mov     [rax+10h], edx
0x1800014f2  mov     [rax+8], rcx
0x1800014f6  push    rsi
0x1800014f7  push    rdi
0x1800014f8  push    r14
0x1800014fa  sub     rsp, 40h
0x1800014fe  mov     rsi, r8
0x180001501  mov     edi, edx
0x180001503  mov     r14, rcx
0x180001506  test    edx, edx
0x180001508  jnz     short loc_180001519
0x18000150a  cmp     cs:dword_180012350, edx
0x180001510  jg      short loc_180001519
0x180001512  xor     eax, eax
0x180001514  jmp     loc_1800015FD
0x180001519  lea     eax, [rdx-1]
0x18000151c  cmp     eax, 1
0x18000151f  ja      short loc_180001560
0x180001521  mov     rax, cs:_pRawDllMain
0x180001528  test    rax, rax
0x18000152b  jnz     short loc_180001532
0x18000152d  lea     ebx, [rax+1]
0x180001530  jmp     short loc_180001539
0x180001532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001537  mov     ebx, eax
0x180001539  mov     [rsp+58h+var_28], ebx
0x18000153d  test    ebx, ebx
0x18000153f  jz      loc_1800015F3
0x180001545  mov     r8, rsi
0x180001548  mov     edx, edi
0x18000154a  mov     rcx, r14
0x18000154d  call    dllmain_crt_dispatch
0x180001552  mov     ebx, eax
0x180001554  mov     [rsp+58h+var_28], eax
0x180001558  test    eax, eax
0x18000155a  jz      loc_1800015F3
0x180001560  mov     r8, rsi; lpvReserved
0x180001563  mov     edx, edi; fdwReason
0x180001565  mov     rcx, r14; hinstDLL
0x180001568  call    DllMain
0x18000156d  mov     ebx, eax
0x18000156f  mov     [rsp+58h+var_28], eax
0x180001573  cmp     edi, 1
0x180001576  jnz     short loc_1800015AF
0x180001578  test    eax, eax
0x18000157a  jnz     short loc_1800015AF
0x18000157c  mov     r8, rsi; lpvReserved
0x18000157f  xor     edx, edx; fdwReason
0x180001581  mov     rcx, r14; hinstDLL
0x180001584  call    DllMain
0x180001589  mov     r8, rsi
0x18000158c  xor     edx, edx
0x18000158e  mov     rcx, r14
0x180001591  call    dllmain_crt_dispatch
0x180001596  mov     rax, cs:_pRawDllMain
0x18000159d  test    rax, rax
0x1800015a0  jz      short loc_1800015AF
0x1800015a2  mov     r8, rsi
0x1800015a5  xor     edx, edx
0x1800015a7  mov     rcx, r14
0x1800015aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015af  test    edi, edi
0x1800015b1  jz      short loc_1800015B8
0x1800015b3  cmp     edi, 3
0x1800015b6  jnz     short loc_1800015F3
0x1800015b8  mov     r8, rsi
0x1800015bb  mov     edx, edi
0x1800015bd  mov     rcx, r14
0x1800015c0  call    dllmain_crt_dispatch
0x1800015c5  mov     ebx, eax
0x1800015c7  mov     [rsp+58h+var_28], eax
0x1800015cb  test    eax, eax
0x1800015cd  jz      short loc_1800015F3
0x1800015cf  mov     rax, cs:_pRawDllMain
0x1800015d6  test    rax, rax
0x1800015d9  jnz     short loc_1800015E0
0x1800015db  lea     ebx, [rax+1]
0x1800015de  jmp     short loc_1800015EF
0x1800015e0  mov     r8, rsi
0x1800015e3  mov     edx, edi
0x1800015e5  mov     rcx, r14
0x1800015e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015ed  mov     ebx, eax
0x1800015ef  mov     [rsp+58h+var_28], ebx
0x1800015f3  jmp     short loc_1800015FB
0x1800015f5  xor     ebx, ebx
0x1800015f7  mov     [rsp+58h+var_28], ebx
0x1800015fb  mov     eax, ebx
0x1800015fd  mov     rbx, [rsp+58h+arg_18]
0x180001602  add     rsp, 40h
0x180001606  pop     r14
0x180001608  pop     rdi
0x180001609  pop     rsi
0x18000160a  retn
0x18000dcdc  push    rbp
0x18000dcde  sub     rsp, 30h
0x18000dce2  mov     rbp, rdx
0x18000dce5  mov     rax, [rcx]
0x18000dce8  mov     edx, [rax]
0x18000dcea  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000dcef  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000dcf3  lea     r9, dllmain_crt_dispatch; int
0x18000dcfa  mov     r8, [rbp+70h]; int
0x18000dcfe  mov     edx, [rbp+68h]; int
0x18000dd01  mov     rcx, [rbp+60h]; int
0x18000dd05  call    __scrt_dllmain_exception_filter
0x18000dd0a  nop
0x18000dd0b  add     rsp, 30h
0x18000dd0f  pop     rbp
0x18000dd10  retn
```
