# dllmain_dispatch

- ea: `0x18001093c`
- end: `0x180010a63`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180010a70`

## callees

- `0x180003b6c`
- `0x180010424`
- `0x180010740`
- `0x18001093c`
- `0x1800148e0`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001F884 <= 0 )
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
0x18001093c  mov     rax, rsp
0x18001093f  mov     [rax+20h], rbx
0x180010943  mov     [rax+18h], r8
0x180010947  mov     [rax+10h], edx
0x18001094a  mov     [rax+8], rcx
0x18001094e  push    rsi
0x18001094f  push    rdi
0x180010950  push    r14
0x180010952  sub     rsp, 40h
0x180010956  mov     rsi, r8
0x180010959  mov     edi, edx
0x18001095b  mov     r14, rcx
0x18001095e  test    edx, edx
0x180010960  jnz     short loc_180010971
0x180010962  cmp     cs:dword_18001F884, edx
0x180010968  jg      short loc_180010971
0x18001096a  xor     eax, eax
0x18001096c  jmp     loc_180010A55
0x180010971  lea     eax, [rdx-1]
0x180010974  cmp     eax, 1
0x180010977  ja      short loc_1800109B8
0x180010979  mov     rax, cs:_pRawDllMain
0x180010980  test    rax, rax
0x180010983  jnz     short loc_18001098A
0x180010985  lea     ebx, [rax+1]
0x180010988  jmp     short loc_180010991
0x18001098a  call    _guard_dispatch_icall
0x18001098f  mov     ebx, eax
0x180010991  mov     [rsp+58h+var_28], ebx
0x180010995  test    ebx, ebx
0x180010997  jz      loc_180010A4B
0x18001099d  mov     r8, rsi
0x1800109a0  mov     edx, edi
0x1800109a2  mov     rcx, r14
0x1800109a5  call    dllmain_crt_dispatch
0x1800109aa  mov     ebx, eax
0x1800109ac  mov     [rsp+58h+var_28], eax
0x1800109b0  test    eax, eax
0x1800109b2  jz      loc_180010A4B
0x1800109b8  mov     r8, rsi; lpvReserved
0x1800109bb  mov     edx, edi; fdwReason
0x1800109bd  mov     rcx, r14; hinstDLL
0x1800109c0  call    DllMain
0x1800109c5  mov     ebx, eax
0x1800109c7  mov     [rsp+58h+var_28], eax
0x1800109cb  cmp     edi, 1
0x1800109ce  jnz     short loc_180010A07
0x1800109d0  test    eax, eax
0x1800109d2  jnz     short loc_180010A07
0x1800109d4  mov     r8, rsi; lpvReserved
0x1800109d7  xor     edx, edx; fdwReason
0x1800109d9  mov     rcx, r14; hinstDLL
0x1800109dc  call    DllMain
0x1800109e1  mov     r8, rsi
0x1800109e4  xor     edx, edx
0x1800109e6  mov     rcx, r14
0x1800109e9  call    dllmain_crt_dispatch
0x1800109ee  mov     rax, cs:_pRawDllMain
0x1800109f5  test    rax, rax
0x1800109f8  jz      short loc_180010A07
0x1800109fa  mov     r8, rsi
0x1800109fd  xor     edx, edx
0x1800109ff  mov     rcx, r14
0x180010a02  call    _guard_dispatch_icall
0x180010a07  test    edi, edi
0x180010a09  jz      short loc_180010A10
0x180010a0b  cmp     edi, 3
0x180010a0e  jnz     short loc_180010A4B
0x180010a10  mov     r8, rsi
0x180010a13  mov     edx, edi
0x180010a15  mov     rcx, r14
0x180010a18  call    dllmain_crt_dispatch
0x180010a1d  mov     ebx, eax
0x180010a1f  mov     [rsp+58h+var_28], eax
0x180010a23  test    eax, eax
0x180010a25  jz      short loc_180010A4B
0x180010a27  mov     rax, cs:_pRawDllMain
0x180010a2e  test    rax, rax
0x180010a31  jnz     short loc_180010A38
0x180010a33  lea     ebx, [rax+1]
0x180010a36  jmp     short loc_180010A47
0x180010a38  mov     r8, rsi
0x180010a3b  mov     edx, edi
0x180010a3d  mov     rcx, r14
0x180010a40  call    _guard_dispatch_icall
0x180010a45  mov     ebx, eax
0x180010a47  mov     [rsp+58h+var_28], ebx
0x180010a4b  jmp     short loc_180010A53
0x180010a4d  xor     ebx, ebx
0x180010a4f  mov     [rsp+58h+var_28], ebx
0x180010a53  mov     eax, ebx
0x180010a55  mov     rbx, [rsp+58h+arg_18]
0x180010a5a  add     rsp, 40h
0x180010a5e  pop     r14
0x180010a60  pop     rdi
0x180010a61  pop     rsi
0x180010a62  retn
0x180015eef  push    rbp
0x180015ef1  sub     rsp, 30h
0x180015ef5  mov     rbp, rdx
0x180015ef8  mov     rax, [rcx]
0x180015efb  mov     edx, [rax]
0x180015efd  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180015f02  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180015f06  lea     r9, dllmain_crt_dispatch; int
0x180015f0d  mov     r8, [rbp+70h]; int
0x180015f11  mov     edx, [rbp+68h]; int
0x180015f14  mov     rcx, [rbp+60h]; int
0x180015f18  call    __scrt_dllmain_exception_filter
0x180015f1d  nop
0x180015f1e  add     rsp, 30h
0x180015f22  pop     rbp
0x180015f23  retn
```
