# dllmain_dispatch

- ea: `0x180035cc4`
- end: `0x180035deb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180035e00`

## callees

- `0x18002f310`
- `0x180035ae0`
- `0x180035cc4`
- `0x180035f90`
- `0x180044010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800502D0 <= 0 )
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
0x180035cc4  mov     rax, rsp
0x180035cc7  mov     [rax+20h], rbx
0x180035ccb  mov     [rax+18h], r8
0x180035ccf  mov     [rax+10h], edx
0x180035cd2  mov     [rax+8], rcx
0x180035cd6  push    rsi
0x180035cd7  push    rdi
0x180035cd8  push    r14
0x180035cda  sub     rsp, 40h
0x180035cde  mov     rsi, r8
0x180035ce1  mov     edi, edx
0x180035ce3  mov     r14, rcx
0x180035ce6  test    edx, edx
0x180035ce8  jnz     short loc_180035CF9
0x180035cea  cmp     cs:dword_1800502D0, edx
0x180035cf0  jg      short loc_180035CF9
0x180035cf2  xor     eax, eax
0x180035cf4  jmp     loc_180035DDD
0x180035cf9  lea     eax, [rdx-1]
0x180035cfc  cmp     eax, 1
0x180035cff  ja      short loc_180035D40
0x180035d01  mov     rax, cs:_pRawDllMain
0x180035d08  test    rax, rax
0x180035d0b  jnz     short loc_180035D12
0x180035d0d  lea     ebx, [rax+1]
0x180035d10  jmp     short loc_180035D19
0x180035d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d17  mov     ebx, eax
0x180035d19  mov     [rsp+58h+var_28], ebx
0x180035d1d  test    ebx, ebx
0x180035d1f  jz      loc_180035DD3
0x180035d25  mov     r8, rsi
0x180035d28  mov     edx, edi
0x180035d2a  mov     rcx, r14
0x180035d2d  call    dllmain_crt_dispatch
0x180035d32  mov     ebx, eax
0x180035d34  mov     [rsp+58h+var_28], eax
0x180035d38  test    eax, eax
0x180035d3a  jz      loc_180035DD3
0x180035d40  mov     r8, rsi; lpvReserved
0x180035d43  mov     edx, edi; fdwReason
0x180035d45  mov     rcx, r14; hinstDLL
0x180035d48  call    DllMain
0x180035d4d  mov     ebx, eax
0x180035d4f  mov     [rsp+58h+var_28], eax
0x180035d53  cmp     edi, 1
0x180035d56  jnz     short loc_180035D8F
0x180035d58  test    eax, eax
0x180035d5a  jnz     short loc_180035D8F
0x180035d5c  mov     r8, rsi; lpvReserved
0x180035d5f  xor     edx, edx; fdwReason
0x180035d61  mov     rcx, r14; hinstDLL
0x180035d64  call    DllMain
0x180035d69  mov     r8, rsi
0x180035d6c  xor     edx, edx
0x180035d6e  mov     rcx, r14
0x180035d71  call    dllmain_crt_dispatch
0x180035d76  mov     rax, cs:_pRawDllMain
0x180035d7d  test    rax, rax
0x180035d80  jz      short loc_180035D8F
0x180035d82  mov     r8, rsi
0x180035d85  xor     edx, edx
0x180035d87  mov     rcx, r14
0x180035d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d8f  test    edi, edi
0x180035d91  jz      short loc_180035D98
0x180035d93  cmp     edi, 3
0x180035d96  jnz     short loc_180035DD3
0x180035d98  mov     r8, rsi
0x180035d9b  mov     edx, edi
0x180035d9d  mov     rcx, r14
0x180035da0  call    dllmain_crt_dispatch
0x180035da5  mov     ebx, eax
0x180035da7  mov     [rsp+58h+var_28], eax
0x180035dab  test    eax, eax
0x180035dad  jz      short loc_180035DD3
0x180035daf  mov     rax, cs:_pRawDllMain
0x180035db6  test    rax, rax
0x180035db9  jnz     short loc_180035DC0
0x180035dbb  lea     ebx, [rax+1]
0x180035dbe  jmp     short loc_180035DCF
0x180035dc0  mov     r8, rsi
0x180035dc3  mov     edx, edi
0x180035dc5  mov     rcx, r14
0x180035dc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035dcd  mov     ebx, eax
0x180035dcf  mov     [rsp+58h+var_28], ebx
0x180035dd3  jmp     short loc_180035DDB
0x180035dd5  xor     ebx, ebx
0x180035dd7  mov     [rsp+58h+var_28], ebx
0x180035ddb  mov     eax, ebx
0x180035ddd  mov     rbx, [rsp+58h+arg_18]
0x180035de2  add     rsp, 40h
0x180035de6  pop     r14
0x180035de8  pop     rdi
0x180035de9  pop     rsi
0x180035dea  retn
0x1800438d2  push    rbp
0x1800438d4  sub     rsp, 30h
0x1800438d8  mov     rbp, rdx
0x1800438db  mov     rax, [rcx]
0x1800438de  mov     edx, [rax]
0x1800438e0  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800438e5  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800438e9  lea     r9, dllmain_crt_dispatch; int
0x1800438f0  mov     r8, [rbp+70h]; int
0x1800438f4  mov     edx, [rbp+68h]; int
0x1800438f7  mov     rcx, [rbp+60h]; int
0x1800438fb  call    __scrt_dllmain_exception_filter
0x180043900  nop
0x180043901  add     rsp, 30h
0x180043905  pop     rbp
0x180043906  retn
```
