# dllmain_dispatch

- ea: `0x18000c0b4`
- end: `0x18000c1db`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000c1f0`

## callees

- `0x1800089c0`
- `0x18000bed0`
- `0x18000c0b4`
- `0x18000c450`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800203D0 <= 0 )
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
0x18000c0b4  mov     rax, rsp
0x18000c0b7  mov     [rax+20h], rbx
0x18000c0bb  mov     [rax+18h], r8
0x18000c0bf  mov     [rax+10h], edx
0x18000c0c2  mov     [rax+8], rcx
0x18000c0c6  push    rsi
0x18000c0c7  push    rdi
0x18000c0c8  push    r14
0x18000c0ca  sub     rsp, 40h
0x18000c0ce  mov     rsi, r8
0x18000c0d1  mov     edi, edx
0x18000c0d3  mov     r14, rcx
0x18000c0d6  test    edx, edx
0x18000c0d8  jnz     short loc_18000C0E9
0x18000c0da  cmp     cs:dword_1800203D0, edx
0x18000c0e0  jg      short loc_18000C0E9
0x18000c0e2  xor     eax, eax
0x18000c0e4  jmp     loc_18000C1CD
0x18000c0e9  lea     eax, [rdx-1]
0x18000c0ec  cmp     eax, 1
0x18000c0ef  ja      short loc_18000C130
0x18000c0f1  mov     rax, cs:_pRawDllMain
0x18000c0f8  test    rax, rax
0x18000c0fb  jnz     short loc_18000C102
0x18000c0fd  lea     ebx, [rax+1]
0x18000c100  jmp     short loc_18000C109
0x18000c102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c107  mov     ebx, eax
0x18000c109  mov     [rsp+58h+var_28], ebx
0x18000c10d  test    ebx, ebx
0x18000c10f  jz      loc_18000C1C3
0x18000c115  mov     r8, rsi
0x18000c118  mov     edx, edi
0x18000c11a  mov     rcx, r14
0x18000c11d  call    dllmain_crt_dispatch
0x18000c122  mov     ebx, eax
0x18000c124  mov     [rsp+58h+var_28], eax
0x18000c128  test    eax, eax
0x18000c12a  jz      loc_18000C1C3
0x18000c130  mov     r8, rsi; lpvReserved
0x18000c133  mov     edx, edi; fdwReason
0x18000c135  mov     rcx, r14; hinstDLL
0x18000c138  call    DllMain
0x18000c13d  mov     ebx, eax
0x18000c13f  mov     [rsp+58h+var_28], eax
0x18000c143  cmp     edi, 1
0x18000c146  jnz     short loc_18000C17F
0x18000c148  test    eax, eax
0x18000c14a  jnz     short loc_18000C17F
0x18000c14c  mov     r8, rsi; lpvReserved
0x18000c14f  xor     edx, edx; fdwReason
0x18000c151  mov     rcx, r14; hinstDLL
0x18000c154  call    DllMain
0x18000c159  mov     r8, rsi
0x18000c15c  xor     edx, edx
0x18000c15e  mov     rcx, r14
0x18000c161  call    dllmain_crt_dispatch
0x18000c166  mov     rax, cs:_pRawDllMain
0x18000c16d  test    rax, rax
0x18000c170  jz      short loc_18000C17F
0x18000c172  mov     r8, rsi
0x18000c175  xor     edx, edx
0x18000c177  mov     rcx, r14
0x18000c17a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c17f  test    edi, edi
0x18000c181  jz      short loc_18000C188
0x18000c183  cmp     edi, 3
0x18000c186  jnz     short loc_18000C1C3
0x18000c188  mov     r8, rsi
0x18000c18b  mov     edx, edi
0x18000c18d  mov     rcx, r14
0x18000c190  call    dllmain_crt_dispatch
0x18000c195  mov     ebx, eax
0x18000c197  mov     [rsp+58h+var_28], eax
0x18000c19b  test    eax, eax
0x18000c19d  jz      short loc_18000C1C3
0x18000c19f  mov     rax, cs:_pRawDllMain
0x18000c1a6  test    rax, rax
0x18000c1a9  jnz     short loc_18000C1B0
0x18000c1ab  lea     ebx, [rax+1]
0x18000c1ae  jmp     short loc_18000C1BF
0x18000c1b0  mov     r8, rsi
0x18000c1b3  mov     edx, edi
0x18000c1b5  mov     rcx, r14
0x18000c1b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1bd  mov     ebx, eax
0x18000c1bf  mov     [rsp+58h+var_28], ebx
0x18000c1c3  jmp     short loc_18000C1CB
0x18000c1c5  xor     ebx, ebx
0x18000c1c7  mov     [rsp+58h+var_28], ebx
0x18000c1cb  mov     eax, ebx
0x18000c1cd  mov     rbx, [rsp+58h+arg_18]
0x18000c1d2  add     rsp, 40h
0x18000c1d6  pop     r14
0x18000c1d8  pop     rdi
0x18000c1d9  pop     rsi
0x18000c1da  retn
0x180016dbc  push    rbp
0x180016dbe  sub     rsp, 30h
0x180016dc2  mov     rbp, rdx
0x180016dc5  mov     rax, [rcx]
0x180016dc8  mov     edx, [rax]
0x180016dca  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180016dcf  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180016dd3  lea     r9, dllmain_crt_dispatch; int
0x180016dda  mov     r8, [rbp+70h]; int
0x180016dde  mov     edx, [rbp+68h]; int
0x180016de1  mov     rcx, [rbp+60h]; int
0x180016de5  call    __scrt_dllmain_exception_filter
0x180016dea  nop
0x180016deb  add     rsp, 30h
0x180016def  pop     rbp
0x180016df0  retn
```
