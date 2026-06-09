# dllmain_dispatch

- ea: `0x180001404`
- end: `0x18000152b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001540`

## callees

- `0x180001190`
- `0x180001220`
- `0x180001404`
- `0x18000168c`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001A2C8 <= 0 )
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
0x180001404  mov     rax, rsp
0x180001407  mov     [rax+20h], rbx
0x18000140b  mov     [rax+18h], r8
0x18000140f  mov     [rax+10h], edx
0x180001412  mov     [rax+8], rcx
0x180001416  push    rsi
0x180001417  push    rdi
0x180001418  push    r14
0x18000141a  sub     rsp, 40h
0x18000141e  mov     rsi, r8
0x180001421  mov     edi, edx
0x180001423  mov     r14, rcx
0x180001426  test    edx, edx
0x180001428  jnz     short loc_180001439
0x18000142a  cmp     cs:dword_18001A2C8, edx
0x180001430  jg      short loc_180001439
0x180001432  xor     eax, eax
0x180001434  jmp     loc_18000151D
0x180001439  lea     eax, [rdx-1]
0x18000143c  cmp     eax, 1
0x18000143f  ja      short loc_180001480
0x180001441  mov     rax, cs:_pRawDllMain
0x180001448  test    rax, rax
0x18000144b  jnz     short loc_180001452
0x18000144d  lea     ebx, [rax+1]
0x180001450  jmp     short loc_180001459
0x180001452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001457  mov     ebx, eax
0x180001459  mov     [rsp+58h+var_28], ebx
0x18000145d  test    ebx, ebx
0x18000145f  jz      loc_180001513
0x180001465  mov     r8, rsi
0x180001468  mov     edx, edi
0x18000146a  mov     rcx, r14
0x18000146d  call    dllmain_crt_dispatch
0x180001472  mov     ebx, eax
0x180001474  mov     [rsp+58h+var_28], eax
0x180001478  test    eax, eax
0x18000147a  jz      loc_180001513
0x180001480  mov     r8, rsi; lpvReserved
0x180001483  mov     edx, edi; fdwReason
0x180001485  mov     rcx, r14; hinstDLL
0x180001488  call    DllMain
0x18000148d  mov     ebx, eax
0x18000148f  mov     [rsp+58h+var_28], eax
0x180001493  cmp     edi, 1
0x180001496  jnz     short loc_1800014CF
0x180001498  test    eax, eax
0x18000149a  jnz     short loc_1800014CF
0x18000149c  mov     r8, rsi; lpvReserved
0x18000149f  xor     edx, edx; fdwReason
0x1800014a1  mov     rcx, r14; hinstDLL
0x1800014a4  call    DllMain
0x1800014a9  mov     r8, rsi
0x1800014ac  xor     edx, edx
0x1800014ae  mov     rcx, r14
0x1800014b1  call    dllmain_crt_dispatch
0x1800014b6  mov     rax, cs:_pRawDllMain
0x1800014bd  test    rax, rax
0x1800014c0  jz      short loc_1800014CF
0x1800014c2  mov     r8, rsi
0x1800014c5  xor     edx, edx
0x1800014c7  mov     rcx, r14
0x1800014ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014cf  test    edi, edi
0x1800014d1  jz      short loc_1800014D8
0x1800014d3  cmp     edi, 3
0x1800014d6  jnz     short loc_180001513
0x1800014d8  mov     r8, rsi
0x1800014db  mov     edx, edi
0x1800014dd  mov     rcx, r14
0x1800014e0  call    dllmain_crt_dispatch
0x1800014e5  mov     ebx, eax
0x1800014e7  mov     [rsp+58h+var_28], eax
0x1800014eb  test    eax, eax
0x1800014ed  jz      short loc_180001513
0x1800014ef  mov     rax, cs:_pRawDllMain
0x1800014f6  test    rax, rax
0x1800014f9  jnz     short loc_180001500
0x1800014fb  lea     ebx, [rax+1]
0x1800014fe  jmp     short loc_18000150F
0x180001500  mov     r8, rsi
0x180001503  mov     edx, edi
0x180001505  mov     rcx, r14
0x180001508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000150d  mov     ebx, eax
0x18000150f  mov     [rsp+58h+var_28], ebx
0x180001513  jmp     short loc_18000151B
0x180001515  xor     ebx, ebx
0x180001517  mov     [rsp+58h+var_28], ebx
0x18000151b  mov     eax, ebx
0x18000151d  mov     rbx, [rsp+58h+arg_18]
0x180001522  add     rsp, 40h
0x180001526  pop     r14
0x180001528  pop     rdi
0x180001529  pop     rsi
0x18000152a  retn
0x18000c750  push    rbp
0x18000c752  sub     rsp, 30h
0x18000c756  mov     rbp, rdx
0x18000c759  mov     rax, [rcx]
0x18000c75c  mov     edx, [rax]
0x18000c75e  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000c763  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000c767  lea     r9, dllmain_crt_dispatch; int
0x18000c76e  mov     r8, [rbp+70h]; int
0x18000c772  mov     edx, [rbp+68h]; int
0x18000c775  mov     rcx, [rbp+60h]; int
0x18000c779  call    __scrt_dllmain_exception_filter
0x18000c77e  nop
0x18000c77f  add     rsp, 30h
0x18000c783  pop     rbp
0x18000c784  retn
```
