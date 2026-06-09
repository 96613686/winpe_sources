# dllmain_dispatch

- ea: `0x18000fee4`
- end: `0x18001000b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180010020`

## callees

- `0x18000fd00`
- `0x18000fee4`
- `0x18001017c`
- `0x1800102cc`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180024470 <= 0 )
    return 0;
  if ( fdwReason - 1 > 1
    || (pRawDllMain ? (v7 = ((__int64 (*)(void))pRawDllMain)()) : (v7 = 1),
        v7 && (v7 = dllmain_crt_dispatch((__int64)hinstDLL, fdwReason, (__int64)lpvReserved)) != 0) )
  {
    v8 = DllMain(hinstDLL, fdwReason, lpvReserved);
    v7 = v8;
    if ( fdwReason == 1 && !v8 )
    {
      DllMain(hinstDLL, 0, lpvReserved);
      dllmain_crt_dispatch((__int64)hinstDLL, 0, (__int64)lpvReserved);
      if ( pRawDllMain )
        pRawDllMain(hinstDLL, 0, lpvReserved);
    }
    if ( !fdwReason || fdwReason == 3 )
    {
      v7 = dllmain_crt_dispatch((__int64)hinstDLL, fdwReason, (__int64)lpvReserved);
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
0x18000fee4  mov     rax, rsp
0x18000fee7  mov     [rax+20h], rbx
0x18000feeb  mov     [rax+18h], r8
0x18000feef  mov     [rax+10h], edx
0x18000fef2  mov     [rax+8], rcx
0x18000fef6  push    rsi
0x18000fef7  push    rdi
0x18000fef8  push    r14
0x18000fefa  sub     rsp, 40h
0x18000fefe  mov     rsi, r8
0x18000ff01  mov     edi, edx
0x18000ff03  mov     r14, rcx
0x18000ff06  test    edx, edx
0x18000ff08  jnz     short loc_18000FF19
0x18000ff0a  cmp     cs:dword_180024470, edx
0x18000ff10  jg      short loc_18000FF19
0x18000ff12  xor     eax, eax
0x18000ff14  jmp     loc_18000FFFD
0x18000ff19  lea     eax, [rdx-1]
0x18000ff1c  cmp     eax, 1
0x18000ff1f  ja      short loc_18000FF60
0x18000ff21  mov     rax, cs:_pRawDllMain
0x18000ff28  test    rax, rax
0x18000ff2b  jnz     short loc_18000FF32
0x18000ff2d  lea     ebx, [rax+1]
0x18000ff30  jmp     short loc_18000FF39
0x18000ff32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff37  mov     ebx, eax
0x18000ff39  mov     [rsp+58h+var_28], ebx
0x18000ff3d  test    ebx, ebx
0x18000ff3f  jz      loc_18000FFF3
0x18000ff45  mov     r8, rsi
0x18000ff48  mov     edx, edi
0x18000ff4a  mov     rcx, r14
0x18000ff4d  call    dllmain_crt_dispatch
0x18000ff52  mov     ebx, eax
0x18000ff54  mov     [rsp+58h+var_28], eax
0x18000ff58  test    eax, eax
0x18000ff5a  jz      loc_18000FFF3
0x18000ff60  mov     r8, rsi; lpvReserved
0x18000ff63  mov     edx, edi; fdwReason
0x18000ff65  mov     rcx, r14; hinstDLL
0x18000ff68  call    DllMain
0x18000ff6d  mov     ebx, eax
0x18000ff6f  mov     [rsp+58h+var_28], eax
0x18000ff73  cmp     edi, 1
0x18000ff76  jnz     short loc_18000FFAF
0x18000ff78  test    eax, eax
0x18000ff7a  jnz     short loc_18000FFAF
0x18000ff7c  mov     r8, rsi; lpvReserved
0x18000ff7f  xor     edx, edx; fdwReason
0x18000ff81  mov     rcx, r14; hinstDLL
0x18000ff84  call    DllMain
0x18000ff89  mov     r8, rsi
0x18000ff8c  xor     edx, edx
0x18000ff8e  mov     rcx, r14
0x18000ff91  call    dllmain_crt_dispatch
0x18000ff96  mov     rax, cs:_pRawDllMain
0x18000ff9d  test    rax, rax
0x18000ffa0  jz      short loc_18000FFAF
0x18000ffa2  mov     r8, rsi
0x18000ffa5  xor     edx, edx
0x18000ffa7  mov     rcx, r14
0x18000ffaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffaf  test    edi, edi
0x18000ffb1  jz      short loc_18000FFB8
0x18000ffb3  cmp     edi, 3
0x18000ffb6  jnz     short loc_18000FFF3
0x18000ffb8  mov     r8, rsi
0x18000ffbb  mov     edx, edi
0x18000ffbd  mov     rcx, r14
0x18000ffc0  call    dllmain_crt_dispatch
0x18000ffc5  mov     ebx, eax
0x18000ffc7  mov     [rsp+58h+var_28], eax
0x18000ffcb  test    eax, eax
0x18000ffcd  jz      short loc_18000FFF3
0x18000ffcf  mov     rax, cs:_pRawDllMain
0x18000ffd6  test    rax, rax
0x18000ffd9  jnz     short loc_18000FFE0
0x18000ffdb  lea     ebx, [rax+1]
0x18000ffde  jmp     short loc_18000FFEF
0x18000ffe0  mov     r8, rsi
0x18000ffe3  mov     edx, edi
0x18000ffe5  mov     rcx, r14
0x18000ffe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffed  mov     ebx, eax
0x18000ffef  mov     [rsp+58h+var_28], ebx
0x18000fff3  jmp     short loc_18000FFFB
0x18000fff5  xor     ebx, ebx
0x18000fff7  mov     [rsp+58h+var_28], ebx
0x18000fffb  mov     eax, ebx
0x18000fffd  mov     rbx, [rsp+58h+arg_18]
0x180010002  add     rsp, 40h
0x180010006  pop     r14
0x180010008  pop     rdi
0x180010009  pop     rsi
0x18001000a  retn
0x18001898c  push    rbp
0x18001898e  sub     rsp, 30h
0x180018992  mov     rbp, rdx
0x180018995  mov     rax, [rcx]
0x180018998  mov     edx, [rax]
0x18001899a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001899f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800189a3  lea     r9, dllmain_crt_dispatch; int
0x1800189aa  mov     r8, [rbp+70h]; int
0x1800189ae  mov     edx, [rbp+68h]; int
0x1800189b1  mov     rcx, [rbp+60h]; int
0x1800189b5  call    __scrt_dllmain_exception_filter
0x1800189ba  nop
0x1800189bb  add     rsp, 30h
0x1800189bf  pop     rbp
0x1800189c0  retn
```
