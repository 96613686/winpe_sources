# dllmain_dispatch

- ea: `0x180003a24`
- end: `0x180003b4b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180003b60`

## callees

- `0x180002dd0`
- `0x180003840`
- `0x180003a24`
- `0x180003de0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180010110 <= 0 )
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
0x180003a24  mov     rax, rsp
0x180003a27  mov     [rax+20h], rbx
0x180003a2b  mov     [rax+18h], r8
0x180003a2f  mov     [rax+10h], edx
0x180003a32  mov     [rax+8], rcx
0x180003a36  push    rsi
0x180003a37  push    rdi
0x180003a38  push    r14
0x180003a3a  sub     rsp, 40h
0x180003a3e  mov     rsi, r8
0x180003a41  mov     edi, edx
0x180003a43  mov     r14, rcx
0x180003a46  test    edx, edx
0x180003a48  jnz     short loc_180003A59
0x180003a4a  cmp     cs:dword_180010110, edx
0x180003a50  jg      short loc_180003A59
0x180003a52  xor     eax, eax
0x180003a54  jmp     loc_180003B3D
0x180003a59  lea     eax, [rdx-1]
0x180003a5c  cmp     eax, 1
0x180003a5f  ja      short loc_180003AA0
0x180003a61  mov     rax, cs:_pRawDllMain
0x180003a68  test    rax, rax
0x180003a6b  jnz     short loc_180003A72
0x180003a6d  lea     ebx, [rax+1]
0x180003a70  jmp     short loc_180003A79
0x180003a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a77  mov     ebx, eax
0x180003a79  mov     [rsp+58h+var_28], ebx
0x180003a7d  test    ebx, ebx
0x180003a7f  jz      loc_180003B33
0x180003a85  mov     r8, rsi
0x180003a88  mov     edx, edi
0x180003a8a  mov     rcx, r14
0x180003a8d  call    dllmain_crt_dispatch
0x180003a92  mov     ebx, eax
0x180003a94  mov     [rsp+58h+var_28], eax
0x180003a98  test    eax, eax
0x180003a9a  jz      loc_180003B33
0x180003aa0  mov     r8, rsi; lpvReserved
0x180003aa3  mov     edx, edi; fdwReason
0x180003aa5  mov     rcx, r14; hinstDLL
0x180003aa8  call    DllMain
0x180003aad  mov     ebx, eax
0x180003aaf  mov     [rsp+58h+var_28], eax
0x180003ab3  cmp     edi, 1
0x180003ab6  jnz     short loc_180003AEF
0x180003ab8  test    eax, eax
0x180003aba  jnz     short loc_180003AEF
0x180003abc  mov     r8, rsi; lpvReserved
0x180003abf  xor     edx, edx; fdwReason
0x180003ac1  mov     rcx, r14; hinstDLL
0x180003ac4  call    DllMain
0x180003ac9  mov     r8, rsi
0x180003acc  xor     edx, edx
0x180003ace  mov     rcx, r14
0x180003ad1  call    dllmain_crt_dispatch
0x180003ad6  mov     rax, cs:_pRawDllMain
0x180003add  test    rax, rax
0x180003ae0  jz      short loc_180003AEF
0x180003ae2  mov     r8, rsi
0x180003ae5  xor     edx, edx
0x180003ae7  mov     rcx, r14
0x180003aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003aef  test    edi, edi
0x180003af1  jz      short loc_180003AF8
0x180003af3  cmp     edi, 3
0x180003af6  jnz     short loc_180003B33
0x180003af8  mov     r8, rsi
0x180003afb  mov     edx, edi
0x180003afd  mov     rcx, r14
0x180003b00  call    dllmain_crt_dispatch
0x180003b05  mov     ebx, eax
0x180003b07  mov     [rsp+58h+var_28], eax
0x180003b0b  test    eax, eax
0x180003b0d  jz      short loc_180003B33
0x180003b0f  mov     rax, cs:_pRawDllMain
0x180003b16  test    rax, rax
0x180003b19  jnz     short loc_180003B20
0x180003b1b  lea     ebx, [rax+1]
0x180003b1e  jmp     short loc_180003B2F
0x180003b20  mov     r8, rsi
0x180003b23  mov     edx, edi
0x180003b25  mov     rcx, r14
0x180003b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b2d  mov     ebx, eax
0x180003b2f  mov     [rsp+58h+var_28], ebx
0x180003b33  jmp     short loc_180003B3B
0x180003b35  xor     ebx, ebx
0x180003b37  mov     [rsp+58h+var_28], ebx
0x180003b3b  mov     eax, ebx
0x180003b3d  mov     rbx, [rsp+58h+arg_18]
0x180003b42  add     rsp, 40h
0x180003b46  pop     r14
0x180003b48  pop     rdi
0x180003b49  pop     rsi
0x180003b4a  retn
0x18000a82c  push    rbp
0x18000a82e  sub     rsp, 30h
0x18000a832  mov     rbp, rdx
0x18000a835  mov     rax, [rcx]
0x18000a838  mov     edx, [rax]
0x18000a83a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000a83f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000a843  lea     r9, dllmain_crt_dispatch; int
0x18000a84a  mov     r8, [rbp+70h]; int
0x18000a84e  mov     edx, [rbp+68h]; int
0x18000a851  mov     rcx, [rbp+60h]; int
0x18000a855  call    __scrt_dllmain_exception_filter
0x18000a85a  nop
0x18000a85b  add     rsp, 30h
0x18000a85f  pop     rbp
0x18000a860  retn
```
