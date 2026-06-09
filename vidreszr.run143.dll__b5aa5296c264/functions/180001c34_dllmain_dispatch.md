# dllmain_dispatch

- ea: `0x180001c34`
- end: `0x180001d5b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001d70`

## callees

- `0x180001a50`
- `0x180001c34`
- `0x180001fc4`
- `0x1800145ec`
- `0x180016010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001BB90 <= 0 )
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
0x180001c34  mov     rax, rsp
0x180001c37  mov     [rax+20h], rbx
0x180001c3b  mov     [rax+18h], r8
0x180001c3f  mov     [rax+10h], edx
0x180001c42  mov     [rax+8], rcx
0x180001c46  push    rsi
0x180001c47  push    rdi
0x180001c48  push    r14
0x180001c4a  sub     rsp, 40h
0x180001c4e  mov     rsi, r8
0x180001c51  mov     edi, edx
0x180001c53  mov     r14, rcx
0x180001c56  test    edx, edx
0x180001c58  jnz     short loc_180001C69
0x180001c5a  cmp     cs:dword_18001BB90, edx
0x180001c60  jg      short loc_180001C69
0x180001c62  xor     eax, eax
0x180001c64  jmp     loc_180001D4D
0x180001c69  lea     eax, [rdx-1]
0x180001c6c  cmp     eax, 1
0x180001c6f  ja      short loc_180001CB0
0x180001c71  mov     rax, cs:_pRawDllMain
0x180001c78  test    rax, rax
0x180001c7b  jnz     short loc_180001C82
0x180001c7d  lea     ebx, [rax+1]
0x180001c80  jmp     short loc_180001C89
0x180001c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c87  mov     ebx, eax
0x180001c89  mov     [rsp+58h+var_28], ebx
0x180001c8d  test    ebx, ebx
0x180001c8f  jz      loc_180001D43
0x180001c95  mov     r8, rsi
0x180001c98  mov     edx, edi
0x180001c9a  mov     rcx, r14
0x180001c9d  call    dllmain_crt_dispatch
0x180001ca2  mov     ebx, eax
0x180001ca4  mov     [rsp+58h+var_28], eax
0x180001ca8  test    eax, eax
0x180001caa  jz      loc_180001D43
0x180001cb0  mov     r8, rsi; lpvReserved
0x180001cb3  mov     edx, edi; fdwReason
0x180001cb5  mov     rcx, r14; hinstDLL
0x180001cb8  call    DllMain
0x180001cbd  mov     ebx, eax
0x180001cbf  mov     [rsp+58h+var_28], eax
0x180001cc3  cmp     edi, 1
0x180001cc6  jnz     short loc_180001CFF
0x180001cc8  test    eax, eax
0x180001cca  jnz     short loc_180001CFF
0x180001ccc  mov     r8, rsi; lpvReserved
0x180001ccf  xor     edx, edx; fdwReason
0x180001cd1  mov     rcx, r14; hinstDLL
0x180001cd4  call    DllMain
0x180001cd9  mov     r8, rsi
0x180001cdc  xor     edx, edx
0x180001cde  mov     rcx, r14
0x180001ce1  call    dllmain_crt_dispatch
0x180001ce6  mov     rax, cs:_pRawDllMain
0x180001ced  test    rax, rax
0x180001cf0  jz      short loc_180001CFF
0x180001cf2  mov     r8, rsi
0x180001cf5  xor     edx, edx
0x180001cf7  mov     rcx, r14
0x180001cfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cff  test    edi, edi
0x180001d01  jz      short loc_180001D08
0x180001d03  cmp     edi, 3
0x180001d06  jnz     short loc_180001D43
0x180001d08  mov     r8, rsi
0x180001d0b  mov     edx, edi
0x180001d0d  mov     rcx, r14
0x180001d10  call    dllmain_crt_dispatch
0x180001d15  mov     ebx, eax
0x180001d17  mov     [rsp+58h+var_28], eax
0x180001d1b  test    eax, eax
0x180001d1d  jz      short loc_180001D43
0x180001d1f  mov     rax, cs:_pRawDllMain
0x180001d26  test    rax, rax
0x180001d29  jnz     short loc_180001D30
0x180001d2b  lea     ebx, [rax+1]
0x180001d2e  jmp     short loc_180001D3F
0x180001d30  mov     r8, rsi
0x180001d33  mov     edx, edi
0x180001d35  mov     rcx, r14
0x180001d38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d3d  mov     ebx, eax
0x180001d3f  mov     [rsp+58h+var_28], ebx
0x180001d43  jmp     short loc_180001D4B
0x180001d45  xor     ebx, ebx
0x180001d47  mov     [rsp+58h+var_28], ebx
0x180001d4b  mov     eax, ebx
0x180001d4d  mov     rbx, [rsp+58h+arg_18]
0x180001d52  add     rsp, 40h
0x180001d56  pop     r14
0x180001d58  pop     rdi
0x180001d59  pop     rsi
0x180001d5a  retn
0x1800159cc  push    rbp
0x1800159ce  sub     rsp, 30h
0x1800159d2  mov     rbp, rdx
0x1800159d5  mov     rax, [rcx]
0x1800159d8  mov     edx, [rax]
0x1800159da  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800159df  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800159e3  lea     r9, dllmain_crt_dispatch; int
0x1800159ea  mov     r8, [rbp+70h]; int
0x1800159ee  mov     edx, [rbp+68h]; int
0x1800159f1  mov     rcx, [rbp+60h]; int
0x1800159f5  call    __scrt_dllmain_exception_filter
0x1800159fa  nop
0x1800159fb  add     rsp, 30h
0x1800159ff  pop     rbp
0x180015a00  retn
```
