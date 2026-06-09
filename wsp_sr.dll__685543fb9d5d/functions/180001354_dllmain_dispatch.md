# dllmain_dispatch

- ea: `0x180001354`
- end: `0x18000147b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001490`

## callees

- `0x180001170`
- `0x180001354`
- `0x180001700`
- `0x180003690`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800C7230 <= 0 )
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
0x180001354  mov     rax, rsp
0x180001357  mov     [rax+20h], rbx
0x18000135b  mov     [rax+18h], r8
0x18000135f  mov     [rax+10h], edx
0x180001362  mov     [rax+8], rcx
0x180001366  push    rsi
0x180001367  push    rdi
0x180001368  push    r14
0x18000136a  sub     rsp, 40h
0x18000136e  mov     rsi, r8
0x180001371  mov     edi, edx
0x180001373  mov     r14, rcx
0x180001376  test    edx, edx
0x180001378  jnz     short loc_180001389
0x18000137a  cmp     cs:dword_1800C7230, edx
0x180001380  jg      short loc_180001389
0x180001382  xor     eax, eax
0x180001384  jmp     loc_18000146D
0x180001389  lea     eax, [rdx-1]
0x18000138c  cmp     eax, 1
0x18000138f  ja      short loc_1800013D0
0x180001391  mov     rax, cs:_pRawDllMain
0x180001398  test    rax, rax
0x18000139b  jnz     short loc_1800013A2
0x18000139d  lea     ebx, [rax+1]
0x1800013a0  jmp     short loc_1800013A9
0x1800013a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013a7  mov     ebx, eax
0x1800013a9  mov     [rsp+58h+var_28], ebx
0x1800013ad  test    ebx, ebx
0x1800013af  jz      loc_180001463
0x1800013b5  mov     r8, rsi
0x1800013b8  mov     edx, edi
0x1800013ba  mov     rcx, r14
0x1800013bd  call    dllmain_crt_dispatch
0x1800013c2  mov     ebx, eax
0x1800013c4  mov     [rsp+58h+var_28], eax
0x1800013c8  test    eax, eax
0x1800013ca  jz      loc_180001463
0x1800013d0  mov     r8, rsi; lpvReserved
0x1800013d3  mov     edx, edi; fdwReason
0x1800013d5  mov     rcx, r14; hinstDLL
0x1800013d8  call    DllMain
0x1800013dd  mov     ebx, eax
0x1800013df  mov     [rsp+58h+var_28], eax
0x1800013e3  cmp     edi, 1
0x1800013e6  jnz     short loc_18000141F
0x1800013e8  test    eax, eax
0x1800013ea  jnz     short loc_18000141F
0x1800013ec  mov     r8, rsi; lpvReserved
0x1800013ef  xor     edx, edx; fdwReason
0x1800013f1  mov     rcx, r14; hinstDLL
0x1800013f4  call    DllMain
0x1800013f9  mov     r8, rsi
0x1800013fc  xor     edx, edx
0x1800013fe  mov     rcx, r14
0x180001401  call    dllmain_crt_dispatch
0x180001406  mov     rax, cs:_pRawDllMain
0x18000140d  test    rax, rax
0x180001410  jz      short loc_18000141F
0x180001412  mov     r8, rsi
0x180001415  xor     edx, edx
0x180001417  mov     rcx, r14
0x18000141a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000141f  test    edi, edi
0x180001421  jz      short loc_180001428
0x180001423  cmp     edi, 3
0x180001426  jnz     short loc_180001463
0x180001428  mov     r8, rsi
0x18000142b  mov     edx, edi
0x18000142d  mov     rcx, r14
0x180001430  call    dllmain_crt_dispatch
0x180001435  mov     ebx, eax
0x180001437  mov     [rsp+58h+var_28], eax
0x18000143b  test    eax, eax
0x18000143d  jz      short loc_180001463
0x18000143f  mov     rax, cs:_pRawDllMain
0x180001446  test    rax, rax
0x180001449  jnz     short loc_180001450
0x18000144b  lea     ebx, [rax+1]
0x18000144e  jmp     short loc_18000145F
0x180001450  mov     r8, rsi
0x180001453  mov     edx, edi
0x180001455  mov     rcx, r14
0x180001458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000145d  mov     ebx, eax
0x18000145f  mov     [rsp+58h+var_28], ebx
0x180001463  jmp     short loc_18000146B
0x180001465  xor     ebx, ebx
0x180001467  mov     [rsp+58h+var_28], ebx
0x18000146b  mov     eax, ebx
0x18000146d  mov     rbx, [rsp+58h+arg_18]
0x180001472  add     rsp, 40h
0x180001476  pop     r14
0x180001478  pop     rdi
0x180001479  pop     rsi
0x18000147a  retn
0x18002a31c  push    rbp
0x18002a31e  sub     rsp, 30h
0x18002a322  mov     rbp, rdx
0x18002a325  mov     rax, [rcx]
0x18002a328  mov     edx, [rax]
0x18002a32a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18002a32f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18002a333  lea     r9, dllmain_crt_dispatch; int
0x18002a33a  mov     r8, [rbp+70h]; int
0x18002a33e  mov     edx, [rbp+68h]; int
0x18002a341  mov     rcx, [rbp+60h]; int
0x18002a345  call    __scrt_dllmain_exception_filter
0x18002a34a  nop
0x18002a34b  add     rsp, 30h
0x18002a34f  pop     rbp
0x18002a350  retn
```
