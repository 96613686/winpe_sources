# dllmain_dispatch

- ea: `0x180001444`
- end: `0x18000156b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001580`

## callees

- `0x180001260`
- `0x180001444`
- `0x1800016cc`
- `0x180001f54`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18004A5D0 <= 0 )
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
0x180001444  mov     rax, rsp
0x180001447  mov     [rax+20h], rbx
0x18000144b  mov     [rax+18h], r8
0x18000144f  mov     [rax+10h], edx
0x180001452  mov     [rax+8], rcx
0x180001456  push    rsi
0x180001457  push    rdi
0x180001458  push    r14
0x18000145a  sub     rsp, 40h
0x18000145e  mov     rsi, r8
0x180001461  mov     edi, edx
0x180001463  mov     r14, rcx
0x180001466  test    edx, edx
0x180001468  jnz     short loc_180001479
0x18000146a  cmp     cs:dword_18004A5D0, edx
0x180001470  jg      short loc_180001479
0x180001472  xor     eax, eax
0x180001474  jmp     loc_18000155D
0x180001479  lea     eax, [rdx-1]
0x18000147c  cmp     eax, 1
0x18000147f  ja      short loc_1800014C0
0x180001481  mov     rax, cs:_pRawDllMain
0x180001488  test    rax, rax
0x18000148b  jnz     short loc_180001492
0x18000148d  lea     ebx, [rax+1]
0x180001490  jmp     short loc_180001499
0x180001492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001497  mov     ebx, eax
0x180001499  mov     [rsp+58h+var_28], ebx
0x18000149d  test    ebx, ebx
0x18000149f  jz      loc_180001553
0x1800014a5  mov     r8, rsi
0x1800014a8  mov     edx, edi
0x1800014aa  mov     rcx, r14
0x1800014ad  call    dllmain_crt_dispatch
0x1800014b2  mov     ebx, eax
0x1800014b4  mov     [rsp+58h+var_28], eax
0x1800014b8  test    eax, eax
0x1800014ba  jz      loc_180001553
0x1800014c0  mov     r8, rsi; lpvReserved
0x1800014c3  mov     edx, edi; fdwReason
0x1800014c5  mov     rcx, r14; hinstDLL
0x1800014c8  call    DllMain
0x1800014cd  mov     ebx, eax
0x1800014cf  mov     [rsp+58h+var_28], eax
0x1800014d3  cmp     edi, 1
0x1800014d6  jnz     short loc_18000150F
0x1800014d8  test    eax, eax
0x1800014da  jnz     short loc_18000150F
0x1800014dc  mov     r8, rsi; lpvReserved
0x1800014df  xor     edx, edx; fdwReason
0x1800014e1  mov     rcx, r14; hinstDLL
0x1800014e4  call    DllMain
0x1800014e9  mov     r8, rsi
0x1800014ec  xor     edx, edx
0x1800014ee  mov     rcx, r14
0x1800014f1  call    dllmain_crt_dispatch
0x1800014f6  mov     rax, cs:_pRawDllMain
0x1800014fd  test    rax, rax
0x180001500  jz      short loc_18000150F
0x180001502  mov     r8, rsi
0x180001505  xor     edx, edx
0x180001507  mov     rcx, r14
0x18000150a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000150f  test    edi, edi
0x180001511  jz      short loc_180001518
0x180001513  cmp     edi, 3
0x180001516  jnz     short loc_180001553
0x180001518  mov     r8, rsi
0x18000151b  mov     edx, edi
0x18000151d  mov     rcx, r14
0x180001520  call    dllmain_crt_dispatch
0x180001525  mov     ebx, eax
0x180001527  mov     [rsp+58h+var_28], eax
0x18000152b  test    eax, eax
0x18000152d  jz      short loc_180001553
0x18000152f  mov     rax, cs:_pRawDllMain
0x180001536  test    rax, rax
0x180001539  jnz     short loc_180001540
0x18000153b  lea     ebx, [rax+1]
0x18000153e  jmp     short loc_18000154F
0x180001540  mov     r8, rsi
0x180001543  mov     edx, edi
0x180001545  mov     rcx, r14
0x180001548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000154d  mov     ebx, eax
0x18000154f  mov     [rsp+58h+var_28], ebx
0x180001553  jmp     short loc_18000155B
0x180001555  xor     ebx, ebx
0x180001557  mov     [rsp+58h+var_28], ebx
0x18000155b  mov     eax, ebx
0x18000155d  mov     rbx, [rsp+58h+arg_18]
0x180001562  add     rsp, 40h
0x180001566  pop     r14
0x180001568  pop     rdi
0x180001569  pop     rsi
0x18000156a  retn
0x18003f37c  push    rbp
0x18003f37e  sub     rsp, 30h
0x18003f382  mov     rbp, rdx
0x18003f385  mov     rax, [rcx]
0x18003f388  mov     edx, [rax]
0x18003f38a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18003f38f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18003f393  lea     r9, dllmain_crt_dispatch; int
0x18003f39a  mov     r8, [rbp+70h]; int
0x18003f39e  mov     edx, [rbp+68h]; int
0x18003f3a1  mov     rcx, [rbp+60h]; int
0x18003f3a5  call    __scrt_dllmain_exception_filter
0x18003f3aa  nop
0x18003f3ab  add     rsp, 30h
0x18003f3af  pop     rbp
0x18003f3b0  retn
```
