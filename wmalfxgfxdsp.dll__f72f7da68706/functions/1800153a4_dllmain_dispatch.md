# dllmain_dispatch

- ea: `0x1800153a4`
- end: `0x1800154cb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800154d4`

## callees

- `0x18000fa84`
- `0x1800151c0`
- `0x1800153a4`
- `0x180015710`
- `0x180086010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1801B9510 <= 0 )
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
0x1800153a4  mov     rax, rsp
0x1800153a7  mov     [rax+20h], rbx
0x1800153ab  mov     [rax+18h], r8
0x1800153af  mov     [rax+10h], edx
0x1800153b2  mov     [rax+8], rcx
0x1800153b6  push    rsi
0x1800153b7  push    rdi
0x1800153b8  push    r14
0x1800153ba  sub     rsp, 40h
0x1800153be  mov     rsi, r8
0x1800153c1  mov     edi, edx
0x1800153c3  mov     r14, rcx
0x1800153c6  test    edx, edx
0x1800153c8  jnz     short loc_1800153D9
0x1800153ca  cmp     cs:dword_1801B9510, edx
0x1800153d0  jg      short loc_1800153D9
0x1800153d2  xor     eax, eax
0x1800153d4  jmp     loc_1800154BD
0x1800153d9  lea     eax, [rdx-1]
0x1800153dc  cmp     eax, 1
0x1800153df  ja      short loc_180015420
0x1800153e1  mov     rax, cs:_pRawDllMain
0x1800153e8  test    rax, rax
0x1800153eb  jnz     short loc_1800153F2
0x1800153ed  lea     ebx, [rax+1]
0x1800153f0  jmp     short loc_1800153F9
0x1800153f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153f7  mov     ebx, eax
0x1800153f9  mov     [rsp+58h+var_28], ebx
0x1800153fd  test    ebx, ebx
0x1800153ff  jz      loc_1800154B3
0x180015405  mov     r8, rsi
0x180015408  mov     edx, edi
0x18001540a  mov     rcx, r14
0x18001540d  call    dllmain_crt_dispatch
0x180015412  mov     ebx, eax
0x180015414  mov     [rsp+58h+var_28], eax
0x180015418  test    eax, eax
0x18001541a  jz      loc_1800154B3
0x180015420  mov     r8, rsi; lpvReserved
0x180015423  mov     edx, edi; fdwReason
0x180015425  mov     rcx, r14; hinstDLL
0x180015428  call    DllMain
0x18001542d  mov     ebx, eax
0x18001542f  mov     [rsp+58h+var_28], eax
0x180015433  cmp     edi, 1
0x180015436  jnz     short loc_18001546F
0x180015438  test    eax, eax
0x18001543a  jnz     short loc_18001546F
0x18001543c  mov     r8, rsi; lpvReserved
0x18001543f  xor     edx, edx; fdwReason
0x180015441  mov     rcx, r14; hinstDLL
0x180015444  call    DllMain
0x180015449  mov     r8, rsi
0x18001544c  xor     edx, edx
0x18001544e  mov     rcx, r14
0x180015451  call    dllmain_crt_dispatch
0x180015456  mov     rax, cs:_pRawDllMain
0x18001545d  test    rax, rax
0x180015460  jz      short loc_18001546F
0x180015462  mov     r8, rsi
0x180015465  xor     edx, edx
0x180015467  mov     rcx, r14
0x18001546a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001546f  test    edi, edi
0x180015471  jz      short loc_180015478
0x180015473  cmp     edi, 3
0x180015476  jnz     short loc_1800154B3
0x180015478  mov     r8, rsi
0x18001547b  mov     edx, edi
0x18001547d  mov     rcx, r14
0x180015480  call    dllmain_crt_dispatch
0x180015485  mov     ebx, eax
0x180015487  mov     [rsp+58h+var_28], eax
0x18001548b  test    eax, eax
0x18001548d  jz      short loc_1800154B3
0x18001548f  mov     rax, cs:_pRawDllMain
0x180015496  test    rax, rax
0x180015499  jnz     short loc_1800154A0
0x18001549b  lea     ebx, [rax+1]
0x18001549e  jmp     short loc_1800154AF
0x1800154a0  mov     r8, rsi
0x1800154a3  mov     edx, edi
0x1800154a5  mov     rcx, r14
0x1800154a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154ad  mov     ebx, eax
0x1800154af  mov     [rsp+58h+var_28], ebx
0x1800154b3  jmp     short loc_1800154BB
0x1800154b5  xor     ebx, ebx
0x1800154b7  mov     [rsp+58h+var_28], ebx
0x1800154bb  mov     eax, ebx
0x1800154bd  mov     rbx, [rsp+58h+arg_18]
0x1800154c2  add     rsp, 40h
0x1800154c6  pop     r14
0x1800154c8  pop     rdi
0x1800154c9  pop     rsi
0x1800154ca  retn
0x180085b0c  push    rbp
0x180085b0e  sub     rsp, 30h
0x180085b12  mov     rbp, rdx
0x180085b15  mov     rax, [rcx]
0x180085b18  mov     edx, [rax]
0x180085b1a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180085b1f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180085b23  lea     r9, dllmain_crt_dispatch; int
0x180085b2a  mov     r8, [rbp+70h]; int
0x180085b2e  mov     edx, [rbp+68h]; int
0x180085b31  mov     rcx, [rbp+60h]; int
0x180085b35  call    __scrt_dllmain_exception_filter
0x180085b3a  nop
0x180085b3b  add     rsp, 30h
0x180085b3f  pop     rbp
0x180085b40  retn
```
