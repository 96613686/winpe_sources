# dllmain_dispatch

- ea: `0x180002274`
- end: `0x18000239b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800023b0`

## callees

- `0x180002090`
- `0x180002274`
- `0x180002690`
- `0x180003c24`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001C3B0 <= 0 )
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
0x180002274  mov     rax, rsp
0x180002277  mov     [rax+20h], rbx
0x18000227b  mov     [rax+18h], r8
0x18000227f  mov     [rax+10h], edx
0x180002282  mov     [rax+8], rcx
0x180002286  push    rsi
0x180002287  push    rdi
0x180002288  push    r14
0x18000228a  sub     rsp, 40h
0x18000228e  mov     rsi, r8
0x180002291  mov     edi, edx
0x180002293  mov     r14, rcx
0x180002296  test    edx, edx
0x180002298  jnz     short loc_1800022A9
0x18000229a  cmp     cs:dword_18001C3B0, edx
0x1800022a0  jg      short loc_1800022A9
0x1800022a2  xor     eax, eax
0x1800022a4  jmp     loc_18000238D
0x1800022a9  lea     eax, [rdx-1]
0x1800022ac  cmp     eax, 1
0x1800022af  ja      short loc_1800022F0
0x1800022b1  mov     rax, cs:_pRawDllMain
0x1800022b8  test    rax, rax
0x1800022bb  jnz     short loc_1800022C2
0x1800022bd  lea     ebx, [rax+1]
0x1800022c0  jmp     short loc_1800022C9
0x1800022c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022c7  mov     ebx, eax
0x1800022c9  mov     [rsp+58h+var_28], ebx
0x1800022cd  test    ebx, ebx
0x1800022cf  jz      loc_180002383
0x1800022d5  mov     r8, rsi
0x1800022d8  mov     edx, edi
0x1800022da  mov     rcx, r14
0x1800022dd  call    dllmain_crt_dispatch
0x1800022e2  mov     ebx, eax
0x1800022e4  mov     [rsp+58h+var_28], eax
0x1800022e8  test    eax, eax
0x1800022ea  jz      loc_180002383
0x1800022f0  mov     r8, rsi; lpvReserved
0x1800022f3  mov     edx, edi; fdwReason
0x1800022f5  mov     rcx, r14; hinstDLL
0x1800022f8  call    DllMain
0x1800022fd  mov     ebx, eax
0x1800022ff  mov     [rsp+58h+var_28], eax
0x180002303  cmp     edi, 1
0x180002306  jnz     short loc_18000233F
0x180002308  test    eax, eax
0x18000230a  jnz     short loc_18000233F
0x18000230c  mov     r8, rsi; lpvReserved
0x18000230f  xor     edx, edx; fdwReason
0x180002311  mov     rcx, r14; hinstDLL
0x180002314  call    DllMain
0x180002319  mov     r8, rsi
0x18000231c  xor     edx, edx
0x18000231e  mov     rcx, r14
0x180002321  call    dllmain_crt_dispatch
0x180002326  mov     rax, cs:_pRawDllMain
0x18000232d  test    rax, rax
0x180002330  jz      short loc_18000233F
0x180002332  mov     r8, rsi
0x180002335  xor     edx, edx
0x180002337  mov     rcx, r14
0x18000233a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000233f  test    edi, edi
0x180002341  jz      short loc_180002348
0x180002343  cmp     edi, 3
0x180002346  jnz     short loc_180002383
0x180002348  mov     r8, rsi
0x18000234b  mov     edx, edi
0x18000234d  mov     rcx, r14
0x180002350  call    dllmain_crt_dispatch
0x180002355  mov     ebx, eax
0x180002357  mov     [rsp+58h+var_28], eax
0x18000235b  test    eax, eax
0x18000235d  jz      short loc_180002383
0x18000235f  mov     rax, cs:_pRawDllMain
0x180002366  test    rax, rax
0x180002369  jnz     short loc_180002370
0x18000236b  lea     ebx, [rax+1]
0x18000236e  jmp     short loc_18000237F
0x180002370  mov     r8, rsi
0x180002373  mov     edx, edi
0x180002375  mov     rcx, r14
0x180002378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000237d  mov     ebx, eax
0x18000237f  mov     [rsp+58h+var_28], ebx
0x180002383  jmp     short loc_18000238B
0x180002385  xor     ebx, ebx
0x180002387  mov     [rsp+58h+var_28], ebx
0x18000238b  mov     eax, ebx
0x18000238d  mov     rbx, [rsp+58h+arg_18]
0x180002392  add     rsp, 40h
0x180002396  pop     r14
0x180002398  pop     rdi
0x180002399  pop     rsi
0x18000239a  retn
0x18000ff7c  push    rbp
0x18000ff7e  sub     rsp, 30h
0x18000ff82  mov     rbp, rdx
0x18000ff85  mov     rax, [rcx]
0x18000ff88  mov     edx, [rax]
0x18000ff8a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000ff8f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000ff93  lea     r9, dllmain_crt_dispatch; int
0x18000ff9a  mov     r8, [rbp+70h]; int
0x18000ff9e  mov     edx, [rbp+68h]; int
0x18000ffa1  mov     rcx, [rbp+60h]; int
0x18000ffa5  call    __scrt_dllmain_exception_filter
0x18000ffaa  nop
0x18000ffab  add     rsp, 30h
0x18000ffaf  pop     rbp
0x18000ffb0  retn
```
