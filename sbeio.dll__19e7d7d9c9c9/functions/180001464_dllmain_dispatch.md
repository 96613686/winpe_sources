# dllmain_dispatch

- ea: `0x180001464`
- end: `0x18000158b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800015a0`

## callees

- `0x180001280`
- `0x180001464`
- `0x1800017f4`
- `0x1800078a0`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180032290 <= 0 )
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
0x180001464  mov     rax, rsp
0x180001467  mov     [rax+20h], rbx
0x18000146b  mov     [rax+18h], r8
0x18000146f  mov     [rax+10h], edx
0x180001472  mov     [rax+8], rcx
0x180001476  push    rsi
0x180001477  push    rdi
0x180001478  push    r14
0x18000147a  sub     rsp, 40h
0x18000147e  mov     rsi, r8
0x180001481  mov     edi, edx
0x180001483  mov     r14, rcx
0x180001486  test    edx, edx
0x180001488  jnz     short loc_180001499
0x18000148a  cmp     cs:dword_180032290, edx
0x180001490  jg      short loc_180001499
0x180001492  xor     eax, eax
0x180001494  jmp     loc_18000157D
0x180001499  lea     eax, [rdx-1]
0x18000149c  cmp     eax, 1
0x18000149f  ja      short loc_1800014E0
0x1800014a1  mov     rax, cs:_pRawDllMain
0x1800014a8  test    rax, rax
0x1800014ab  jnz     short loc_1800014B2
0x1800014ad  lea     ebx, [rax+1]
0x1800014b0  jmp     short loc_1800014B9
0x1800014b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014b7  mov     ebx, eax
0x1800014b9  mov     [rsp+58h+var_28], ebx
0x1800014bd  test    ebx, ebx
0x1800014bf  jz      loc_180001573
0x1800014c5  mov     r8, rsi
0x1800014c8  mov     edx, edi
0x1800014ca  mov     rcx, r14
0x1800014cd  call    dllmain_crt_dispatch
0x1800014d2  mov     ebx, eax
0x1800014d4  mov     [rsp+58h+var_28], eax
0x1800014d8  test    eax, eax
0x1800014da  jz      loc_180001573
0x1800014e0  mov     r8, rsi; lpvReserved
0x1800014e3  mov     edx, edi; fdwReason
0x1800014e5  mov     rcx, r14; hinstDLL
0x1800014e8  call    DllMain
0x1800014ed  mov     ebx, eax
0x1800014ef  mov     [rsp+58h+var_28], eax
0x1800014f3  cmp     edi, 1
0x1800014f6  jnz     short loc_18000152F
0x1800014f8  test    eax, eax
0x1800014fa  jnz     short loc_18000152F
0x1800014fc  mov     r8, rsi; lpvReserved
0x1800014ff  xor     edx, edx; fdwReason
0x180001501  mov     rcx, r14; hinstDLL
0x180001504  call    DllMain
0x180001509  mov     r8, rsi
0x18000150c  xor     edx, edx
0x18000150e  mov     rcx, r14
0x180001511  call    dllmain_crt_dispatch
0x180001516  mov     rax, cs:_pRawDllMain
0x18000151d  test    rax, rax
0x180001520  jz      short loc_18000152F
0x180001522  mov     r8, rsi
0x180001525  xor     edx, edx
0x180001527  mov     rcx, r14
0x18000152a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000152f  test    edi, edi
0x180001531  jz      short loc_180001538
0x180001533  cmp     edi, 3
0x180001536  jnz     short loc_180001573
0x180001538  mov     r8, rsi
0x18000153b  mov     edx, edi
0x18000153d  mov     rcx, r14
0x180001540  call    dllmain_crt_dispatch
0x180001545  mov     ebx, eax
0x180001547  mov     [rsp+58h+var_28], eax
0x18000154b  test    eax, eax
0x18000154d  jz      short loc_180001573
0x18000154f  mov     rax, cs:_pRawDllMain
0x180001556  test    rax, rax
0x180001559  jnz     short loc_180001560
0x18000155b  lea     ebx, [rax+1]
0x18000155e  jmp     short loc_18000156F
0x180001560  mov     r8, rsi
0x180001563  mov     edx, edi
0x180001565  mov     rcx, r14
0x180001568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000156d  mov     ebx, eax
0x18000156f  mov     [rsp+58h+var_28], ebx
0x180001573  jmp     short loc_18000157B
0x180001575  xor     ebx, ebx
0x180001577  mov     [rsp+58h+var_28], ebx
0x18000157b  mov     eax, ebx
0x18000157d  mov     rbx, [rsp+58h+arg_18]
0x180001582  add     rsp, 40h
0x180001586  pop     r14
0x180001588  pop     rdi
0x180001589  pop     rsi
0x18000158a  retn
0x18002a14c  push    rbp
0x18002a14e  sub     rsp, 30h
0x18002a152  mov     rbp, rdx
0x18002a155  mov     rax, [rcx]
0x18002a158  mov     edx, [rax]
0x18002a15a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18002a15f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18002a163  lea     r9, dllmain_crt_dispatch; int
0x18002a16a  mov     r8, [rbp+70h]; int
0x18002a16e  mov     edx, [rbp+68h]; int
0x18002a171  mov     rcx, [rbp+60h]; int
0x18002a175  call    __scrt_dllmain_exception_filter
0x18002a17a  nop
0x18002a17b  add     rsp, 30h
0x18002a17f  pop     rbp
0x18002a180  retn
```
