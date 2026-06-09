# dllmain_dispatch

- ea: `0x180004af4`
- end: `0x180004c1b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180004c30`

## callees

- `0x1800023f0`
- `0x180004910`
- `0x180004af4`
- `0x180004e84`
- `0x180008010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL startup_argv_mode; // eax

  if ( !fdwReason && dword_18000D450 <= 0 )
    return 0;
  if ( fdwReason - 1 > 1
    || (pRawDllMain ? (v7 = ((__int64 (*)(void))pRawDllMain)()) : (v7 = 1),
        v7 && (v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved)) != 0) )
  {
    startup_argv_mode = get_startup_argv_mode(hinstDLL, fdwReason, lpvReserved);
    v7 = startup_argv_mode;
    if ( fdwReason == 1 && !startup_argv_mode )
    {
      get_startup_argv_mode(hinstDLL, 0, lpvReserved);
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
0x180004af4  mov     rax, rsp
0x180004af7  mov     [rax+20h], rbx
0x180004afb  mov     [rax+18h], r8
0x180004aff  mov     [rax+10h], edx
0x180004b02  mov     [rax+8], rcx
0x180004b06  push    rsi
0x180004b07  push    rdi
0x180004b08  push    r14
0x180004b0a  sub     rsp, 40h
0x180004b0e  mov     rsi, r8
0x180004b11  mov     edi, edx
0x180004b13  mov     r14, rcx
0x180004b16  test    edx, edx
0x180004b18  jnz     short loc_180004B29
0x180004b1a  cmp     cs:dword_18000D450, edx
0x180004b20  jg      short loc_180004B29
0x180004b22  xor     eax, eax
0x180004b24  jmp     loc_180004C0D
0x180004b29  lea     eax, [rdx-1]
0x180004b2c  cmp     eax, 1
0x180004b2f  ja      short loc_180004B70
0x180004b31  mov     rax, cs:_pRawDllMain
0x180004b38  test    rax, rax
0x180004b3b  jnz     short loc_180004B42
0x180004b3d  lea     ebx, [rax+1]
0x180004b40  jmp     short loc_180004B49
0x180004b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b47  mov     ebx, eax
0x180004b49  mov     [rsp+58h+var_28], ebx
0x180004b4d  test    ebx, ebx
0x180004b4f  jz      loc_180004C03
0x180004b55  mov     r8, rsi
0x180004b58  mov     edx, edi
0x180004b5a  mov     rcx, r14
0x180004b5d  call    dllmain_crt_dispatch
0x180004b62  mov     ebx, eax
0x180004b64  mov     [rsp+58h+var_28], eax
0x180004b68  test    eax, eax
0x180004b6a  jz      loc_180004C03
0x180004b70  mov     r8, rsi; lpvReserved
0x180004b73  mov     edx, edi; fdwReason
0x180004b75  mov     rcx, r14; hinstDLL
0x180004b78  call    _get_startup_argv_mode
0x180004b7d  mov     ebx, eax
0x180004b7f  mov     [rsp+58h+var_28], eax
0x180004b83  cmp     edi, 1
0x180004b86  jnz     short loc_180004BBF
0x180004b88  test    eax, eax
0x180004b8a  jnz     short loc_180004BBF
0x180004b8c  mov     r8, rsi; lpvReserved
0x180004b8f  xor     edx, edx; fdwReason
0x180004b91  mov     rcx, r14; hinstDLL
0x180004b94  call    _get_startup_argv_mode
0x180004b99  mov     r8, rsi
0x180004b9c  xor     edx, edx
0x180004b9e  mov     rcx, r14
0x180004ba1  call    dllmain_crt_dispatch
0x180004ba6  mov     rax, cs:_pRawDllMain
0x180004bad  test    rax, rax
0x180004bb0  jz      short loc_180004BBF
0x180004bb2  mov     r8, rsi
0x180004bb5  xor     edx, edx
0x180004bb7  mov     rcx, r14
0x180004bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bbf  test    edi, edi
0x180004bc1  jz      short loc_180004BC8
0x180004bc3  cmp     edi, 3
0x180004bc6  jnz     short loc_180004C03
0x180004bc8  mov     r8, rsi
0x180004bcb  mov     edx, edi
0x180004bcd  mov     rcx, r14
0x180004bd0  call    dllmain_crt_dispatch
0x180004bd5  mov     ebx, eax
0x180004bd7  mov     [rsp+58h+var_28], eax
0x180004bdb  test    eax, eax
0x180004bdd  jz      short loc_180004C03
0x180004bdf  mov     rax, cs:_pRawDllMain
0x180004be6  test    rax, rax
0x180004be9  jnz     short loc_180004BF0
0x180004beb  lea     ebx, [rax+1]
0x180004bee  jmp     short loc_180004BFF
0x180004bf0  mov     r8, rsi
0x180004bf3  mov     edx, edi
0x180004bf5  mov     rcx, r14
0x180004bf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bfd  mov     ebx, eax
0x180004bff  mov     [rsp+58h+var_28], ebx
0x180004c03  jmp     short loc_180004C0B
0x180004c05  xor     ebx, ebx
0x180004c07  mov     [rsp+58h+var_28], ebx
0x180004c0b  mov     eax, ebx
0x180004c0d  mov     rbx, [rsp+58h+arg_18]
0x180004c12  add     rsp, 40h
0x180004c16  pop     r14
0x180004c18  pop     rdi
0x180004c19  pop     rsi
0x180004c1a  retn
0x1800078a2  push    rbp
0x1800078a4  sub     rsp, 30h
0x1800078a8  mov     rbp, rdx
0x1800078ab  mov     rax, [rcx]
0x1800078ae  mov     edx, [rax]
0x1800078b0  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800078b5  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800078b9  lea     r9, dllmain_crt_dispatch; int
0x1800078c0  mov     r8, [rbp+70h]; int
0x1800078c4  mov     edx, [rbp+68h]; int
0x1800078c7  mov     rcx, [rbp+60h]; int
0x1800078cb  call    __scrt_dllmain_exception_filter
0x1800078d0  nop
0x1800078d1  add     rsp, 30h
0x1800078d5  pop     rbp
0x1800078d6  retn
```
