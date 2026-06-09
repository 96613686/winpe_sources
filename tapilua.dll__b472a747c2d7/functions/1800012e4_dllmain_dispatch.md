# dllmain_dispatch

- ea: `0x1800012e4`
- end: `0x18000140b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001420`

## callees

- `0x180001100`
- `0x1800012e4`
- `0x180001680`
- `0x180004994`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18000A1B0 <= 0 )
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
0x1800012e4  mov     rax, rsp
0x1800012e7  mov     [rax+20h], rbx
0x1800012eb  mov     [rax+18h], r8
0x1800012ef  mov     [rax+10h], edx
0x1800012f2  mov     [rax+8], rcx
0x1800012f6  push    rsi
0x1800012f7  push    rdi
0x1800012f8  push    r14
0x1800012fa  sub     rsp, 40h
0x1800012fe  mov     rsi, r8
0x180001301  mov     edi, edx
0x180001303  mov     r14, rcx
0x180001306  test    edx, edx
0x180001308  jnz     short loc_180001319
0x18000130a  cmp     cs:dword_18000A1B0, edx
0x180001310  jg      short loc_180001319
0x180001312  xor     eax, eax
0x180001314  jmp     loc_1800013FD
0x180001319  lea     eax, [rdx-1]
0x18000131c  cmp     eax, 1
0x18000131f  ja      short loc_180001360
0x180001321  mov     rax, cs:_pRawDllMain
0x180001328  test    rax, rax
0x18000132b  jnz     short loc_180001332
0x18000132d  lea     ebx, [rax+1]
0x180001330  jmp     short loc_180001339
0x180001332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001337  mov     ebx, eax
0x180001339  mov     [rsp+58h+var_28], ebx
0x18000133d  test    ebx, ebx
0x18000133f  jz      loc_1800013F3
0x180001345  mov     r8, rsi
0x180001348  mov     edx, edi
0x18000134a  mov     rcx, r14
0x18000134d  call    dllmain_crt_dispatch
0x180001352  mov     ebx, eax
0x180001354  mov     [rsp+58h+var_28], eax
0x180001358  test    eax, eax
0x18000135a  jz      loc_1800013F3
0x180001360  mov     r8, rsi; lpvReserved
0x180001363  mov     edx, edi; fdwReason
0x180001365  mov     rcx, r14; hinstDLL
0x180001368  call    DllMain
0x18000136d  mov     ebx, eax
0x18000136f  mov     [rsp+58h+var_28], eax
0x180001373  cmp     edi, 1
0x180001376  jnz     short loc_1800013AF
0x180001378  test    eax, eax
0x18000137a  jnz     short loc_1800013AF
0x18000137c  mov     r8, rsi; lpvReserved
0x18000137f  xor     edx, edx; fdwReason
0x180001381  mov     rcx, r14; hinstDLL
0x180001384  call    DllMain
0x180001389  mov     r8, rsi
0x18000138c  xor     edx, edx
0x18000138e  mov     rcx, r14
0x180001391  call    dllmain_crt_dispatch
0x180001396  mov     rax, cs:_pRawDllMain
0x18000139d  test    rax, rax
0x1800013a0  jz      short loc_1800013AF
0x1800013a2  mov     r8, rsi
0x1800013a5  xor     edx, edx
0x1800013a7  mov     rcx, r14
0x1800013aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013af  test    edi, edi
0x1800013b1  jz      short loc_1800013B8
0x1800013b3  cmp     edi, 3
0x1800013b6  jnz     short loc_1800013F3
0x1800013b8  mov     r8, rsi
0x1800013bb  mov     edx, edi
0x1800013bd  mov     rcx, r14
0x1800013c0  call    dllmain_crt_dispatch
0x1800013c5  mov     ebx, eax
0x1800013c7  mov     [rsp+58h+var_28], eax
0x1800013cb  test    eax, eax
0x1800013cd  jz      short loc_1800013F3
0x1800013cf  mov     rax, cs:_pRawDllMain
0x1800013d6  test    rax, rax
0x1800013d9  jnz     short loc_1800013E0
0x1800013db  lea     ebx, [rax+1]
0x1800013de  jmp     short loc_1800013EF
0x1800013e0  mov     r8, rsi
0x1800013e3  mov     edx, edi
0x1800013e5  mov     rcx, r14
0x1800013e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013ed  mov     ebx, eax
0x1800013ef  mov     [rsp+58h+var_28], ebx
0x1800013f3  jmp     short loc_1800013FB
0x1800013f5  xor     ebx, ebx
0x1800013f7  mov     [rsp+58h+var_28], ebx
0x1800013fb  mov     eax, ebx
0x1800013fd  mov     rbx, [rsp+58h+arg_18]
0x180001402  add     rsp, 40h
0x180001406  pop     r14
0x180001408  pop     rdi
0x180001409  pop     rsi
0x18000140a  retn
0x18000501c  push    rbp
0x18000501e  sub     rsp, 30h
0x180005022  mov     rbp, rdx
0x180005025  mov     rax, [rcx]
0x180005028  mov     edx, [rax]
0x18000502a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000502f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180005033  lea     r9, dllmain_crt_dispatch; int
0x18000503a  mov     r8, [rbp+70h]; int
0x18000503e  mov     edx, [rbp+68h]; int
0x180005041  mov     rcx, [rbp+60h]; int
0x180005045  call    __scrt_dllmain_exception_filter
0x18000504a  nop
0x18000504b  add     rsp, 30h
0x18000504f  pop     rbp
0x180005050  retn
```
