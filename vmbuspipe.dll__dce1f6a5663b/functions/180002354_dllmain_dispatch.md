# dllmain_dispatch

- ea: `0x180002354`
- end: `0x18000247b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002490`

## callees

- `0x180002170`
- `0x180002354`
- `0x18000260c`
- `0x180007558`
- `0x180008010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18000C1F0 <= 0 )
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
0x180002354  mov     rax, rsp
0x180002357  mov     [rax+20h], rbx
0x18000235b  mov     [rax+18h], r8
0x18000235f  mov     [rax+10h], edx
0x180002362  mov     [rax+8], rcx
0x180002366  push    rsi
0x180002367  push    rdi
0x180002368  push    r14
0x18000236a  sub     rsp, 40h
0x18000236e  mov     rsi, r8
0x180002371  mov     edi, edx
0x180002373  mov     r14, rcx
0x180002376  test    edx, edx
0x180002378  jnz     short loc_180002389
0x18000237a  cmp     cs:dword_18000C1F0, edx
0x180002380  jg      short loc_180002389
0x180002382  xor     eax, eax
0x180002384  jmp     loc_18000246D
0x180002389  lea     eax, [rdx-1]
0x18000238c  cmp     eax, 1
0x18000238f  ja      short loc_1800023D0
0x180002391  mov     rax, cs:_pRawDllMain
0x180002398  test    rax, rax
0x18000239b  jnz     short loc_1800023A2
0x18000239d  lea     ebx, [rax+1]
0x1800023a0  jmp     short loc_1800023A9
0x1800023a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023a7  mov     ebx, eax
0x1800023a9  mov     [rsp+58h+var_28], ebx
0x1800023ad  test    ebx, ebx
0x1800023af  jz      loc_180002463
0x1800023b5  mov     r8, rsi
0x1800023b8  mov     edx, edi
0x1800023ba  mov     rcx, r14
0x1800023bd  call    dllmain_crt_dispatch
0x1800023c2  mov     ebx, eax
0x1800023c4  mov     [rsp+58h+var_28], eax
0x1800023c8  test    eax, eax
0x1800023ca  jz      loc_180002463
0x1800023d0  mov     r8, rsi; lpvReserved
0x1800023d3  mov     edx, edi; fdwReason
0x1800023d5  mov     rcx, r14; hinstDLL
0x1800023d8  call    DllMain
0x1800023dd  mov     ebx, eax
0x1800023df  mov     [rsp+58h+var_28], eax
0x1800023e3  cmp     edi, 1
0x1800023e6  jnz     short loc_18000241F
0x1800023e8  test    eax, eax
0x1800023ea  jnz     short loc_18000241F
0x1800023ec  mov     r8, rsi; lpvReserved
0x1800023ef  xor     edx, edx; fdwReason
0x1800023f1  mov     rcx, r14; hinstDLL
0x1800023f4  call    DllMain
0x1800023f9  mov     r8, rsi
0x1800023fc  xor     edx, edx
0x1800023fe  mov     rcx, r14
0x180002401  call    dllmain_crt_dispatch
0x180002406  mov     rax, cs:_pRawDllMain
0x18000240d  test    rax, rax
0x180002410  jz      short loc_18000241F
0x180002412  mov     r8, rsi
0x180002415  xor     edx, edx
0x180002417  mov     rcx, r14
0x18000241a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000241f  test    edi, edi
0x180002421  jz      short loc_180002428
0x180002423  cmp     edi, 3
0x180002426  jnz     short loc_180002463
0x180002428  mov     r8, rsi
0x18000242b  mov     edx, edi
0x18000242d  mov     rcx, r14
0x180002430  call    dllmain_crt_dispatch
0x180002435  mov     ebx, eax
0x180002437  mov     [rsp+58h+var_28], eax
0x18000243b  test    eax, eax
0x18000243d  jz      short loc_180002463
0x18000243f  mov     rax, cs:_pRawDllMain
0x180002446  test    rax, rax
0x180002449  jnz     short loc_180002450
0x18000244b  lea     ebx, [rax+1]
0x18000244e  jmp     short loc_18000245F
0x180002450  mov     r8, rsi
0x180002453  mov     edx, edi
0x180002455  mov     rcx, r14
0x180002458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000245d  mov     ebx, eax
0x18000245f  mov     [rsp+58h+var_28], ebx
0x180002463  jmp     short loc_18000246B
0x180002465  xor     ebx, ebx
0x180002467  mov     [rsp+58h+var_28], ebx
0x18000246b  mov     eax, ebx
0x18000246d  mov     rbx, [rsp+58h+arg_18]
0x180002472  add     rsp, 40h
0x180002476  pop     r14
0x180002478  pop     rdi
0x180002479  pop     rsi
0x18000247a  retn
0x180007a80  push    rbp
0x180007a82  sub     rsp, 30h
0x180007a86  mov     rbp, rdx
0x180007a89  mov     rax, [rcx]
0x180007a8c  mov     edx, [rax]
0x180007a8e  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180007a93  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180007a97  lea     r9, dllmain_crt_dispatch; int
0x180007a9e  mov     r8, [rbp+70h]; int
0x180007aa2  mov     edx, [rbp+68h]; int
0x180007aa5  mov     rcx, [rbp+60h]; int
0x180007aa9  call    __scrt_dllmain_exception_filter
0x180007aae  nop
0x180007aaf  add     rsp, 30h
0x180007ab3  pop     rbp
0x180007ab4  retn
```
