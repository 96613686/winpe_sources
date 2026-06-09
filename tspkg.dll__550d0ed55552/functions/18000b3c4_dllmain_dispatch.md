# dllmain_dispatch

- ea: `0x18000b3c4`
- end: `0x18000b4eb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000b500`

## callees

- `0x18000b1e0`
- `0x18000b3c4`
- `0x18000b64c`
- `0x18000ba1c`
- `0x18001d010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180025410 <= 0 )
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
0x18000b3c4  mov     rax, rsp
0x18000b3c7  mov     [rax+20h], rbx
0x18000b3cb  mov     [rax+18h], r8
0x18000b3cf  mov     [rax+10h], edx
0x18000b3d2  mov     [rax+8], rcx
0x18000b3d6  push    rsi
0x18000b3d7  push    rdi
0x18000b3d8  push    r14
0x18000b3da  sub     rsp, 40h
0x18000b3de  mov     rsi, r8
0x18000b3e1  mov     edi, edx
0x18000b3e3  mov     r14, rcx
0x18000b3e6  test    edx, edx
0x18000b3e8  jnz     short loc_18000B3F9
0x18000b3ea  cmp     cs:dword_180025410, edx
0x18000b3f0  jg      short loc_18000B3F9
0x18000b3f2  xor     eax, eax
0x18000b3f4  jmp     loc_18000B4DD
0x18000b3f9  lea     eax, [rdx-1]
0x18000b3fc  cmp     eax, 1
0x18000b3ff  ja      short loc_18000B440
0x18000b401  mov     rax, cs:_pRawDllMain
0x18000b408  test    rax, rax
0x18000b40b  jnz     short loc_18000B412
0x18000b40d  lea     ebx, [rax+1]
0x18000b410  jmp     short loc_18000B419
0x18000b412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b417  mov     ebx, eax
0x18000b419  mov     [rsp+58h+var_28], ebx
0x18000b41d  test    ebx, ebx
0x18000b41f  jz      loc_18000B4D3
0x18000b425  mov     r8, rsi
0x18000b428  mov     edx, edi
0x18000b42a  mov     rcx, r14
0x18000b42d  call    dllmain_crt_dispatch
0x18000b432  mov     ebx, eax
0x18000b434  mov     [rsp+58h+var_28], eax
0x18000b438  test    eax, eax
0x18000b43a  jz      loc_18000B4D3
0x18000b440  mov     r8, rsi; lpvReserved
0x18000b443  mov     edx, edi; fdwReason
0x18000b445  mov     rcx, r14; hinstDLL
0x18000b448  call    DllMain
0x18000b44d  mov     ebx, eax
0x18000b44f  mov     [rsp+58h+var_28], eax
0x18000b453  cmp     edi, 1
0x18000b456  jnz     short loc_18000B48F
0x18000b458  test    eax, eax
0x18000b45a  jnz     short loc_18000B48F
0x18000b45c  mov     r8, rsi; lpvReserved
0x18000b45f  xor     edx, edx; fdwReason
0x18000b461  mov     rcx, r14; hinstDLL
0x18000b464  call    DllMain
0x18000b469  mov     r8, rsi
0x18000b46c  xor     edx, edx
0x18000b46e  mov     rcx, r14
0x18000b471  call    dllmain_crt_dispatch
0x18000b476  mov     rax, cs:_pRawDllMain
0x18000b47d  test    rax, rax
0x18000b480  jz      short loc_18000B48F
0x18000b482  mov     r8, rsi
0x18000b485  xor     edx, edx
0x18000b487  mov     rcx, r14
0x18000b48a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b48f  test    edi, edi
0x18000b491  jz      short loc_18000B498
0x18000b493  cmp     edi, 3
0x18000b496  jnz     short loc_18000B4D3
0x18000b498  mov     r8, rsi
0x18000b49b  mov     edx, edi
0x18000b49d  mov     rcx, r14
0x18000b4a0  call    dllmain_crt_dispatch
0x18000b4a5  mov     ebx, eax
0x18000b4a7  mov     [rsp+58h+var_28], eax
0x18000b4ab  test    eax, eax
0x18000b4ad  jz      short loc_18000B4D3
0x18000b4af  mov     rax, cs:_pRawDllMain
0x18000b4b6  test    rax, rax
0x18000b4b9  jnz     short loc_18000B4C0
0x18000b4bb  lea     ebx, [rax+1]
0x18000b4be  jmp     short loc_18000B4CF
0x18000b4c0  mov     r8, rsi
0x18000b4c3  mov     edx, edi
0x18000b4c5  mov     rcx, r14
0x18000b4c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4cd  mov     ebx, eax
0x18000b4cf  mov     [rsp+58h+var_28], ebx
0x18000b4d3  jmp     short loc_18000B4DB
0x18000b4d5  xor     ebx, ebx
0x18000b4d7  mov     [rsp+58h+var_28], ebx
0x18000b4db  mov     eax, ebx
0x18000b4dd  mov     rbx, [rsp+58h+arg_18]
0x18000b4e2  add     rsp, 40h
0x18000b4e6  pop     r14
0x18000b4e8  pop     rdi
0x18000b4e9  pop     rsi
0x18000b4ea  retn
0x18001c70c  push    rbp
0x18001c70e  sub     rsp, 30h
0x18001c712  mov     rbp, rdx
0x18001c715  mov     rax, [rcx]
0x18001c718  mov     edx, [rax]
0x18001c71a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001c71f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18001c723  lea     r9, dllmain_crt_dispatch; int
0x18001c72a  mov     r8, [rbp+70h]; int
0x18001c72e  mov     edx, [rbp+68h]; int
0x18001c731  mov     rcx, [rbp+60h]; int
0x18001c735  call    __scrt_dllmain_exception_filter
0x18001c73a  nop
0x18001c73b  add     rsp, 30h
0x18001c73f  pop     rbp
0x18001c740  retn
```
