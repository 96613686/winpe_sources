# dllmain_dispatch

- ea: `0x1800248c4`
- end: `0x1800249eb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180024a00`

## callees

- `0x18001ac20`
- `0x1800246e0`
- `0x1800248c4`
- `0x180024b84`
- `0x18003c010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18004B290 <= 0 )
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
0x1800248c4  mov     rax, rsp
0x1800248c7  mov     [rax+20h], rbx
0x1800248cb  mov     [rax+18h], r8
0x1800248cf  mov     [rax+10h], edx
0x1800248d2  mov     [rax+8], rcx
0x1800248d6  push    rsi
0x1800248d7  push    rdi
0x1800248d8  push    r14
0x1800248da  sub     rsp, 40h
0x1800248de  mov     rsi, r8
0x1800248e1  mov     edi, edx
0x1800248e3  mov     r14, rcx
0x1800248e6  test    edx, edx
0x1800248e8  jnz     short loc_1800248F9
0x1800248ea  cmp     cs:dword_18004B290, edx
0x1800248f0  jg      short loc_1800248F9
0x1800248f2  xor     eax, eax
0x1800248f4  jmp     loc_1800249DD
0x1800248f9  lea     eax, [rdx-1]
0x1800248fc  cmp     eax, 1
0x1800248ff  ja      short loc_180024940
0x180024901  mov     rax, cs:_pRawDllMain
0x180024908  test    rax, rax
0x18002490b  jnz     short loc_180024912
0x18002490d  lea     ebx, [rax+1]
0x180024910  jmp     short loc_180024919
0x180024912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024917  mov     ebx, eax
0x180024919  mov     [rsp+58h+var_28], ebx
0x18002491d  test    ebx, ebx
0x18002491f  jz      loc_1800249D3
0x180024925  mov     r8, rsi
0x180024928  mov     edx, edi
0x18002492a  mov     rcx, r14
0x18002492d  call    dllmain_crt_dispatch
0x180024932  mov     ebx, eax
0x180024934  mov     [rsp+58h+var_28], eax
0x180024938  test    eax, eax
0x18002493a  jz      loc_1800249D3
0x180024940  mov     r8, rsi; lpvReserved
0x180024943  mov     edx, edi; fdwReason
0x180024945  mov     rcx, r14; hinstDLL
0x180024948  call    DllMain
0x18002494d  mov     ebx, eax
0x18002494f  mov     [rsp+58h+var_28], eax
0x180024953  cmp     edi, 1
0x180024956  jnz     short loc_18002498F
0x180024958  test    eax, eax
0x18002495a  jnz     short loc_18002498F
0x18002495c  mov     r8, rsi; lpvReserved
0x18002495f  xor     edx, edx; fdwReason
0x180024961  mov     rcx, r14; hinstDLL
0x180024964  call    DllMain
0x180024969  mov     r8, rsi
0x18002496c  xor     edx, edx
0x18002496e  mov     rcx, r14
0x180024971  call    dllmain_crt_dispatch
0x180024976  mov     rax, cs:_pRawDllMain
0x18002497d  test    rax, rax
0x180024980  jz      short loc_18002498F
0x180024982  mov     r8, rsi
0x180024985  xor     edx, edx
0x180024987  mov     rcx, r14
0x18002498a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002498f  test    edi, edi
0x180024991  jz      short loc_180024998
0x180024993  cmp     edi, 3
0x180024996  jnz     short loc_1800249D3
0x180024998  mov     r8, rsi
0x18002499b  mov     edx, edi
0x18002499d  mov     rcx, r14
0x1800249a0  call    dllmain_crt_dispatch
0x1800249a5  mov     ebx, eax
0x1800249a7  mov     [rsp+58h+var_28], eax
0x1800249ab  test    eax, eax
0x1800249ad  jz      short loc_1800249D3
0x1800249af  mov     rax, cs:_pRawDllMain
0x1800249b6  test    rax, rax
0x1800249b9  jnz     short loc_1800249C0
0x1800249bb  lea     ebx, [rax+1]
0x1800249be  jmp     short loc_1800249CF
0x1800249c0  mov     r8, rsi
0x1800249c3  mov     edx, edi
0x1800249c5  mov     rcx, r14
0x1800249c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249cd  mov     ebx, eax
0x1800249cf  mov     [rsp+58h+var_28], ebx
0x1800249d3  jmp     short loc_1800249DB
0x1800249d5  xor     ebx, ebx
0x1800249d7  mov     [rsp+58h+var_28], ebx
0x1800249db  mov     eax, ebx
0x1800249dd  mov     rbx, [rsp+58h+arg_18]
0x1800249e2  add     rsp, 40h
0x1800249e6  pop     r14
0x1800249e8  pop     rdi
0x1800249e9  pop     rsi
0x1800249ea  retn
0x18003a857  push    rbp
0x18003a859  sub     rsp, 30h
0x18003a85d  mov     rbp, rdx
0x18003a860  mov     rax, [rcx]
0x18003a863  mov     edx, [rax]
0x18003a865  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18003a86a  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18003a86e  lea     r9, dllmain_crt_dispatch; int
0x18003a875  mov     r8, [rbp+70h]; int
0x18003a879  mov     edx, [rbp+68h]; int
0x18003a87c  mov     rcx, [rbp+60h]; int
0x18003a880  call    __scrt_dllmain_exception_filter
0x18003a885  nop
0x18003a886  add     rsp, 30h
0x18003a88a  pop     rbp
0x18003a88b  retn
```
