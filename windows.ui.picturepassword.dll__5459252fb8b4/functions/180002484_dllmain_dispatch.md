# dllmain_dispatch

- ea: `0x180002484`
- end: `0x1800025ab`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800025c0`

## callees

- `0x1800022a0`
- `0x180002484`
- `0x180002718`
- `0x180004990`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18002D2D0 <= 0 )
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
0x180002484  mov     rax, rsp
0x180002487  mov     [rax+20h], rbx
0x18000248b  mov     [rax+18h], r8
0x18000248f  mov     [rax+10h], edx
0x180002492  mov     [rax+8], rcx
0x180002496  push    rsi
0x180002497  push    rdi
0x180002498  push    r14
0x18000249a  sub     rsp, 40h
0x18000249e  mov     rsi, r8
0x1800024a1  mov     edi, edx
0x1800024a3  mov     r14, rcx
0x1800024a6  test    edx, edx
0x1800024a8  jnz     short loc_1800024B9
0x1800024aa  cmp     cs:dword_18002D2D0, edx
0x1800024b0  jg      short loc_1800024B9
0x1800024b2  xor     eax, eax
0x1800024b4  jmp     loc_18000259D
0x1800024b9  lea     eax, [rdx-1]
0x1800024bc  cmp     eax, 1
0x1800024bf  ja      short loc_180002500
0x1800024c1  mov     rax, cs:_pRawDllMain
0x1800024c8  test    rax, rax
0x1800024cb  jnz     short loc_1800024D2
0x1800024cd  lea     ebx, [rax+1]
0x1800024d0  jmp     short loc_1800024D9
0x1800024d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024d7  mov     ebx, eax
0x1800024d9  mov     [rsp+58h+var_28], ebx
0x1800024dd  test    ebx, ebx
0x1800024df  jz      loc_180002593
0x1800024e5  mov     r8, rsi
0x1800024e8  mov     edx, edi
0x1800024ea  mov     rcx, r14
0x1800024ed  call    dllmain_crt_dispatch
0x1800024f2  mov     ebx, eax
0x1800024f4  mov     [rsp+58h+var_28], eax
0x1800024f8  test    eax, eax
0x1800024fa  jz      loc_180002593
0x180002500  mov     r8, rsi; lpvReserved
0x180002503  mov     edx, edi; fdwReason
0x180002505  mov     rcx, r14; hinstDLL
0x180002508  call    DllMain
0x18000250d  mov     ebx, eax
0x18000250f  mov     [rsp+58h+var_28], eax
0x180002513  cmp     edi, 1
0x180002516  jnz     short loc_18000254F
0x180002518  test    eax, eax
0x18000251a  jnz     short loc_18000254F
0x18000251c  mov     r8, rsi; lpvReserved
0x18000251f  xor     edx, edx; fdwReason
0x180002521  mov     rcx, r14; hinstDLL
0x180002524  call    DllMain
0x180002529  mov     r8, rsi
0x18000252c  xor     edx, edx
0x18000252e  mov     rcx, r14
0x180002531  call    dllmain_crt_dispatch
0x180002536  mov     rax, cs:_pRawDllMain
0x18000253d  test    rax, rax
0x180002540  jz      short loc_18000254F
0x180002542  mov     r8, rsi
0x180002545  xor     edx, edx
0x180002547  mov     rcx, r14
0x18000254a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000254f  test    edi, edi
0x180002551  jz      short loc_180002558
0x180002553  cmp     edi, 3
0x180002556  jnz     short loc_180002593
0x180002558  mov     r8, rsi
0x18000255b  mov     edx, edi
0x18000255d  mov     rcx, r14
0x180002560  call    dllmain_crt_dispatch
0x180002565  mov     ebx, eax
0x180002567  mov     [rsp+58h+var_28], eax
0x18000256b  test    eax, eax
0x18000256d  jz      short loc_180002593
0x18000256f  mov     rax, cs:_pRawDllMain
0x180002576  test    rax, rax
0x180002579  jnz     short loc_180002580
0x18000257b  lea     ebx, [rax+1]
0x18000257e  jmp     short loc_18000258F
0x180002580  mov     r8, rsi
0x180002583  mov     edx, edi
0x180002585  mov     rcx, r14
0x180002588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000258d  mov     ebx, eax
0x18000258f  mov     [rsp+58h+var_28], ebx
0x180002593  jmp     short loc_18000259B
0x180002595  xor     ebx, ebx
0x180002597  mov     [rsp+58h+var_28], ebx
0x18000259b  mov     eax, ebx
0x18000259d  mov     rbx, [rsp+58h+arg_18]
0x1800025a2  add     rsp, 40h
0x1800025a6  pop     r14
0x1800025a8  pop     rdi
0x1800025a9  pop     rsi
0x1800025aa  retn
0x18001e47c  push    rbp
0x18001e47e  sub     rsp, 30h
0x18001e482  mov     rbp, rdx
0x18001e485  mov     rax, [rcx]
0x18001e488  mov     edx, [rax]
0x18001e48a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001e48f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18001e493  lea     r9, dllmain_crt_dispatch; int
0x18001e49a  mov     r8, [rbp+70h]; int
0x18001e49e  mov     edx, [rbp+68h]; int
0x18001e4a1  mov     rcx, [rbp+60h]; int
0x18001e4a5  call    __scrt_dllmain_exception_filter
0x18001e4aa  nop
0x18001e4ab  add     rsp, 30h
0x18001e4af  pop     rbp
0x18001e4b0  retn
```
