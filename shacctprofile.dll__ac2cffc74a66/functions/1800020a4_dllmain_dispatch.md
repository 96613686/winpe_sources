# dllmain_dispatch

- ea: `0x1800020a4`
- end: `0x1800021cb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800021e0`

## callees

- `0x180001ec0`
- `0x1800020a4`
- `0x18000232c`
- `0x180006038`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18000FA10 <= 0 )
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
0x1800020a4  mov     rax, rsp
0x1800020a7  mov     [rax+20h], rbx
0x1800020ab  mov     [rax+18h], r8
0x1800020af  mov     [rax+10h], edx
0x1800020b2  mov     [rax+8], rcx
0x1800020b6  push    rsi
0x1800020b7  push    rdi
0x1800020b8  push    r14
0x1800020ba  sub     rsp, 40h
0x1800020be  mov     rsi, r8
0x1800020c1  mov     edi, edx
0x1800020c3  mov     r14, rcx
0x1800020c6  test    edx, edx
0x1800020c8  jnz     short loc_1800020D9
0x1800020ca  cmp     cs:dword_18000FA10, edx
0x1800020d0  jg      short loc_1800020D9
0x1800020d2  xor     eax, eax
0x1800020d4  jmp     loc_1800021BD
0x1800020d9  lea     eax, [rdx-1]
0x1800020dc  cmp     eax, 1
0x1800020df  ja      short loc_180002120
0x1800020e1  mov     rax, cs:_pRawDllMain
0x1800020e8  test    rax, rax
0x1800020eb  jnz     short loc_1800020F2
0x1800020ed  lea     ebx, [rax+1]
0x1800020f0  jmp     short loc_1800020F9
0x1800020f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020f7  mov     ebx, eax
0x1800020f9  mov     [rsp+58h+var_28], ebx
0x1800020fd  test    ebx, ebx
0x1800020ff  jz      loc_1800021B3
0x180002105  mov     r8, rsi
0x180002108  mov     edx, edi
0x18000210a  mov     rcx, r14
0x18000210d  call    dllmain_crt_dispatch
0x180002112  mov     ebx, eax
0x180002114  mov     [rsp+58h+var_28], eax
0x180002118  test    eax, eax
0x18000211a  jz      loc_1800021B3
0x180002120  mov     r8, rsi; lpvReserved
0x180002123  mov     edx, edi; fdwReason
0x180002125  mov     rcx, r14; hinstDLL
0x180002128  call    DllMain
0x18000212d  mov     ebx, eax
0x18000212f  mov     [rsp+58h+var_28], eax
0x180002133  cmp     edi, 1
0x180002136  jnz     short loc_18000216F
0x180002138  test    eax, eax
0x18000213a  jnz     short loc_18000216F
0x18000213c  mov     r8, rsi; lpvReserved
0x18000213f  xor     edx, edx; fdwReason
0x180002141  mov     rcx, r14; hinstDLL
0x180002144  call    DllMain
0x180002149  mov     r8, rsi
0x18000214c  xor     edx, edx
0x18000214e  mov     rcx, r14
0x180002151  call    dllmain_crt_dispatch
0x180002156  mov     rax, cs:_pRawDllMain
0x18000215d  test    rax, rax
0x180002160  jz      short loc_18000216F
0x180002162  mov     r8, rsi
0x180002165  xor     edx, edx
0x180002167  mov     rcx, r14
0x18000216a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000216f  test    edi, edi
0x180002171  jz      short loc_180002178
0x180002173  cmp     edi, 3
0x180002176  jnz     short loc_1800021B3
0x180002178  mov     r8, rsi
0x18000217b  mov     edx, edi
0x18000217d  mov     rcx, r14
0x180002180  call    dllmain_crt_dispatch
0x180002185  mov     ebx, eax
0x180002187  mov     [rsp+58h+var_28], eax
0x18000218b  test    eax, eax
0x18000218d  jz      short loc_1800021B3
0x18000218f  mov     rax, cs:_pRawDllMain
0x180002196  test    rax, rax
0x180002199  jnz     short loc_1800021A0
0x18000219b  lea     ebx, [rax+1]
0x18000219e  jmp     short loc_1800021AF
0x1800021a0  mov     r8, rsi
0x1800021a3  mov     edx, edi
0x1800021a5  mov     rcx, r14
0x1800021a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021ad  mov     ebx, eax
0x1800021af  mov     [rsp+58h+var_28], ebx
0x1800021b3  jmp     short loc_1800021BB
0x1800021b5  xor     ebx, ebx
0x1800021b7  mov     [rsp+58h+var_28], ebx
0x1800021bb  mov     eax, ebx
0x1800021bd  mov     rbx, [rsp+58h+arg_18]
0x1800021c2  add     rsp, 40h
0x1800021c6  pop     r14
0x1800021c8  pop     rdi
0x1800021c9  pop     rsi
0x1800021ca  retn
0x18000980c  push    rbp
0x18000980e  sub     rsp, 30h
0x180009812  mov     rbp, rdx
0x180009815  mov     rax, [rcx]
0x180009818  mov     edx, [rax]
0x18000981a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000981f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180009823  lea     r9, dllmain_crt_dispatch; int
0x18000982a  mov     r8, [rbp+70h]; int
0x18000982e  mov     edx, [rbp+68h]; int
0x180009831  mov     rcx, [rbp+60h]; int
0x180009835  call    __scrt_dllmain_exception_filter
0x18000983a  nop
0x18000983b  add     rsp, 30h
0x18000983f  pop     rbp
0x180009840  retn
```
