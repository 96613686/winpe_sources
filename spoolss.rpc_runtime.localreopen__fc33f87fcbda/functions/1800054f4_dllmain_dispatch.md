# dllmain_dispatch

- ea: `0x1800054f4`
- end: `0x18000561b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180005630`

## callees

- `0x180002290`
- `0x180005310`
- `0x1800054f4`
- `0x18000577c`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180022370 <= 0 )
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
0x1800054f4  mov     rax, rsp
0x1800054f7  mov     [rax+20h], rbx
0x1800054fb  mov     [rax+18h], r8
0x1800054ff  mov     [rax+10h], edx
0x180005502  mov     [rax+8], rcx
0x180005506  push    rsi
0x180005507  push    rdi
0x180005508  push    r14
0x18000550a  sub     rsp, 40h
0x18000550e  mov     rsi, r8
0x180005511  mov     edi, edx
0x180005513  mov     r14, rcx
0x180005516  test    edx, edx
0x180005518  jnz     short loc_180005529
0x18000551a  cmp     cs:dword_180022370, edx
0x180005520  jg      short loc_180005529
0x180005522  xor     eax, eax
0x180005524  jmp     loc_18000560D
0x180005529  lea     eax, [rdx-1]
0x18000552c  cmp     eax, 1
0x18000552f  ja      short loc_180005570
0x180005531  mov     rax, cs:_pRawDllMain
0x180005538  test    rax, rax
0x18000553b  jnz     short loc_180005542
0x18000553d  lea     ebx, [rax+1]
0x180005540  jmp     short loc_180005549
0x180005542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005547  mov     ebx, eax
0x180005549  mov     [rsp+58h+var_28], ebx
0x18000554d  test    ebx, ebx
0x18000554f  jz      loc_180005603
0x180005555  mov     r8, rsi
0x180005558  mov     edx, edi
0x18000555a  mov     rcx, r14
0x18000555d  call    dllmain_crt_dispatch
0x180005562  mov     ebx, eax
0x180005564  mov     [rsp+58h+var_28], eax
0x180005568  test    eax, eax
0x18000556a  jz      loc_180005603
0x180005570  mov     r8, rsi; lpvReserved
0x180005573  mov     edx, edi; fdwReason
0x180005575  mov     rcx, r14; hinstDLL
0x180005578  call    DllMain
0x18000557d  mov     ebx, eax
0x18000557f  mov     [rsp+58h+var_28], eax
0x180005583  cmp     edi, 1
0x180005586  jnz     short loc_1800055BF
0x180005588  test    eax, eax
0x18000558a  jnz     short loc_1800055BF
0x18000558c  mov     r8, rsi; lpvReserved
0x18000558f  xor     edx, edx; fdwReason
0x180005591  mov     rcx, r14; hinstDLL
0x180005594  call    DllMain
0x180005599  mov     r8, rsi
0x18000559c  xor     edx, edx
0x18000559e  mov     rcx, r14
0x1800055a1  call    dllmain_crt_dispatch
0x1800055a6  mov     rax, cs:_pRawDllMain
0x1800055ad  test    rax, rax
0x1800055b0  jz      short loc_1800055BF
0x1800055b2  mov     r8, rsi
0x1800055b5  xor     edx, edx
0x1800055b7  mov     rcx, r14
0x1800055ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055bf  test    edi, edi
0x1800055c1  jz      short loc_1800055C8
0x1800055c3  cmp     edi, 3
0x1800055c6  jnz     short loc_180005603
0x1800055c8  mov     r8, rsi
0x1800055cb  mov     edx, edi
0x1800055cd  mov     rcx, r14
0x1800055d0  call    dllmain_crt_dispatch
0x1800055d5  mov     ebx, eax
0x1800055d7  mov     [rsp+58h+var_28], eax
0x1800055db  test    eax, eax
0x1800055dd  jz      short loc_180005603
0x1800055df  mov     rax, cs:_pRawDllMain
0x1800055e6  test    rax, rax
0x1800055e9  jnz     short loc_1800055F0
0x1800055eb  lea     ebx, [rax+1]
0x1800055ee  jmp     short loc_1800055FF
0x1800055f0  mov     r8, rsi
0x1800055f3  mov     edx, edi
0x1800055f5  mov     rcx, r14
0x1800055f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055fd  mov     ebx, eax
0x1800055ff  mov     [rsp+58h+var_28], ebx
0x180005603  jmp     short loc_18000560B
0x180005605  xor     ebx, ebx
0x180005607  mov     [rsp+58h+var_28], ebx
0x18000560b  mov     eax, ebx
0x18000560d  mov     rbx, [rsp+58h+arg_18]
0x180005612  add     rsp, 40h
0x180005616  pop     r14
0x180005618  pop     rdi
0x180005619  pop     rsi
0x18000561a  retn
0x180016b30  push    rbp
0x180016b32  sub     rsp, 30h
0x180016b36  mov     rbp, rdx
0x180016b39  mov     rax, [rcx]
0x180016b3c  mov     edx, [rax]
0x180016b3e  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180016b43  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180016b47  lea     r9, dllmain_crt_dispatch; int
0x180016b4e  mov     r8, [rbp+70h]; int
0x180016b52  mov     edx, [rbp+68h]; int
0x180016b55  mov     rcx, [rbp+60h]; int
0x180016b59  call    __scrt_dllmain_exception_filter
0x180016b5e  nop
0x180016b5f  add     rsp, 30h
0x180016b63  pop     rbp
0x180016b64  retn
```
