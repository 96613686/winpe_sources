# dllmain_dispatch

- ea: `0x180001d24`
- end: `0x180001e4b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001e60`

## callees

- `0x180001b40`
- `0x180001d24`
- `0x18000208c`
- `0x18001c400`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800485D0 <= 0 )
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
0x180001d24  mov     rax, rsp
0x180001d27  mov     [rax+20h], rbx
0x180001d2b  mov     [rax+18h], r8
0x180001d2f  mov     [rax+10h], edx
0x180001d32  mov     [rax+8], rcx
0x180001d36  push    rsi
0x180001d37  push    rdi
0x180001d38  push    r14
0x180001d3a  sub     rsp, 40h
0x180001d3e  mov     rsi, r8
0x180001d41  mov     edi, edx
0x180001d43  mov     r14, rcx
0x180001d46  test    edx, edx
0x180001d48  jnz     short loc_180001D59
0x180001d4a  cmp     cs:dword_1800485D0, edx
0x180001d50  jg      short loc_180001D59
0x180001d52  xor     eax, eax
0x180001d54  jmp     loc_180001E3D
0x180001d59  lea     eax, [rdx-1]
0x180001d5c  cmp     eax, 1
0x180001d5f  ja      short loc_180001DA0
0x180001d61  mov     rax, cs:_pRawDllMain
0x180001d68  test    rax, rax
0x180001d6b  jnz     short loc_180001D72
0x180001d6d  lea     ebx, [rax+1]
0x180001d70  jmp     short loc_180001D79
0x180001d72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d77  mov     ebx, eax
0x180001d79  mov     [rsp+58h+var_28], ebx
0x180001d7d  test    ebx, ebx
0x180001d7f  jz      loc_180001E33
0x180001d85  mov     r8, rsi
0x180001d88  mov     edx, edi
0x180001d8a  mov     rcx, r14
0x180001d8d  call    dllmain_crt_dispatch
0x180001d92  mov     ebx, eax
0x180001d94  mov     [rsp+58h+var_28], eax
0x180001d98  test    eax, eax
0x180001d9a  jz      loc_180001E33
0x180001da0  mov     r8, rsi; lpvReserved
0x180001da3  mov     edx, edi; fdwReason
0x180001da5  mov     rcx, r14; hinstDLL
0x180001da8  call    DllMain
0x180001dad  mov     ebx, eax
0x180001daf  mov     [rsp+58h+var_28], eax
0x180001db3  cmp     edi, 1
0x180001db6  jnz     short loc_180001DEF
0x180001db8  test    eax, eax
0x180001dba  jnz     short loc_180001DEF
0x180001dbc  mov     r8, rsi; lpvReserved
0x180001dbf  xor     edx, edx; fdwReason
0x180001dc1  mov     rcx, r14; hinstDLL
0x180001dc4  call    DllMain
0x180001dc9  mov     r8, rsi
0x180001dcc  xor     edx, edx
0x180001dce  mov     rcx, r14
0x180001dd1  call    dllmain_crt_dispatch
0x180001dd6  mov     rax, cs:_pRawDllMain
0x180001ddd  test    rax, rax
0x180001de0  jz      short loc_180001DEF
0x180001de2  mov     r8, rsi
0x180001de5  xor     edx, edx
0x180001de7  mov     rcx, r14
0x180001dea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001def  test    edi, edi
0x180001df1  jz      short loc_180001DF8
0x180001df3  cmp     edi, 3
0x180001df6  jnz     short loc_180001E33
0x180001df8  mov     r8, rsi
0x180001dfb  mov     edx, edi
0x180001dfd  mov     rcx, r14
0x180001e00  call    dllmain_crt_dispatch
0x180001e05  mov     ebx, eax
0x180001e07  mov     [rsp+58h+var_28], eax
0x180001e0b  test    eax, eax
0x180001e0d  jz      short loc_180001E33
0x180001e0f  mov     rax, cs:_pRawDllMain
0x180001e16  test    rax, rax
0x180001e19  jnz     short loc_180001E20
0x180001e1b  lea     ebx, [rax+1]
0x180001e1e  jmp     short loc_180001E2F
0x180001e20  mov     r8, rsi
0x180001e23  mov     edx, edi
0x180001e25  mov     rcx, r14
0x180001e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e2d  mov     ebx, eax
0x180001e2f  mov     [rsp+58h+var_28], ebx
0x180001e33  jmp     short loc_180001E3B
0x180001e35  xor     ebx, ebx
0x180001e37  mov     [rsp+58h+var_28], ebx
0x180001e3b  mov     eax, ebx
0x180001e3d  mov     rbx, [rsp+58h+arg_18]
0x180001e42  add     rsp, 40h
0x180001e46  pop     r14
0x180001e48  pop     rdi
0x180001e49  pop     rsi
0x180001e4a  retn
0x180034bec  push    rbp
0x180034bee  sub     rsp, 30h
0x180034bf2  mov     rbp, rdx
0x180034bf5  mov     rax, [rcx]
0x180034bf8  mov     edx, [rax]
0x180034bfa  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180034bff  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180034c03  lea     r9, dllmain_crt_dispatch; int
0x180034c0a  mov     r8, [rbp+70h]; int
0x180034c0e  mov     edx, [rbp+68h]; int
0x180034c11  mov     rcx, [rbp+60h]; int
0x180034c15  call    __scrt_dllmain_exception_filter
0x180034c1a  nop
0x180034c1b  add     rsp, 30h
0x180034c1f  pop     rbp
0x180034c20  retn
```
