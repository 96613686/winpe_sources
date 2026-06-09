# dllmain_dispatch

- ea: `0x180002654`
- end: `0x18000277b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002790`

## callees

- `0x180002470`
- `0x180002654`
- `0x180002924`
- `0x180004574`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180020490 <= 0 )
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
0x180002654  mov     rax, rsp
0x180002657  mov     [rax+20h], rbx
0x18000265b  mov     [rax+18h], r8
0x18000265f  mov     [rax+10h], edx
0x180002662  mov     [rax+8], rcx
0x180002666  push    rsi
0x180002667  push    rdi
0x180002668  push    r14
0x18000266a  sub     rsp, 40h
0x18000266e  mov     rsi, r8
0x180002671  mov     edi, edx
0x180002673  mov     r14, rcx
0x180002676  test    edx, edx
0x180002678  jnz     short loc_180002689
0x18000267a  cmp     cs:dword_180020490, edx
0x180002680  jg      short loc_180002689
0x180002682  xor     eax, eax
0x180002684  jmp     loc_18000276D
0x180002689  lea     eax, [rdx-1]
0x18000268c  cmp     eax, 1
0x18000268f  ja      short loc_1800026D0
0x180002691  mov     rax, cs:_pRawDllMain
0x180002698  test    rax, rax
0x18000269b  jnz     short loc_1800026A2
0x18000269d  lea     ebx, [rax+1]
0x1800026a0  jmp     short loc_1800026A9
0x1800026a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026a7  mov     ebx, eax
0x1800026a9  mov     [rsp+58h+var_28], ebx
0x1800026ad  test    ebx, ebx
0x1800026af  jz      loc_180002763
0x1800026b5  mov     r8, rsi
0x1800026b8  mov     edx, edi
0x1800026ba  mov     rcx, r14
0x1800026bd  call    dllmain_crt_dispatch
0x1800026c2  mov     ebx, eax
0x1800026c4  mov     [rsp+58h+var_28], eax
0x1800026c8  test    eax, eax
0x1800026ca  jz      loc_180002763
0x1800026d0  mov     r8, rsi; lpvReserved
0x1800026d3  mov     edx, edi; fdwReason
0x1800026d5  mov     rcx, r14; hinstDLL
0x1800026d8  call    DllMain
0x1800026dd  mov     ebx, eax
0x1800026df  mov     [rsp+58h+var_28], eax
0x1800026e3  cmp     edi, 1
0x1800026e6  jnz     short loc_18000271F
0x1800026e8  test    eax, eax
0x1800026ea  jnz     short loc_18000271F
0x1800026ec  mov     r8, rsi; lpvReserved
0x1800026ef  xor     edx, edx; fdwReason
0x1800026f1  mov     rcx, r14; hinstDLL
0x1800026f4  call    DllMain
0x1800026f9  mov     r8, rsi
0x1800026fc  xor     edx, edx
0x1800026fe  mov     rcx, r14
0x180002701  call    dllmain_crt_dispatch
0x180002706  mov     rax, cs:_pRawDllMain
0x18000270d  test    rax, rax
0x180002710  jz      short loc_18000271F
0x180002712  mov     r8, rsi
0x180002715  xor     edx, edx
0x180002717  mov     rcx, r14
0x18000271a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000271f  test    edi, edi
0x180002721  jz      short loc_180002728
0x180002723  cmp     edi, 3
0x180002726  jnz     short loc_180002763
0x180002728  mov     r8, rsi
0x18000272b  mov     edx, edi
0x18000272d  mov     rcx, r14
0x180002730  call    dllmain_crt_dispatch
0x180002735  mov     ebx, eax
0x180002737  mov     [rsp+58h+var_28], eax
0x18000273b  test    eax, eax
0x18000273d  jz      short loc_180002763
0x18000273f  mov     rax, cs:_pRawDllMain
0x180002746  test    rax, rax
0x180002749  jnz     short loc_180002750
0x18000274b  lea     ebx, [rax+1]
0x18000274e  jmp     short loc_18000275F
0x180002750  mov     r8, rsi
0x180002753  mov     edx, edi
0x180002755  mov     rcx, r14
0x180002758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000275d  mov     ebx, eax
0x18000275f  mov     [rsp+58h+var_28], ebx
0x180002763  jmp     short loc_18000276B
0x180002765  xor     ebx, ebx
0x180002767  mov     [rsp+58h+var_28], ebx
0x18000276b  mov     eax, ebx
0x18000276d  mov     rbx, [rsp+58h+arg_18]
0x180002772  add     rsp, 40h
0x180002776  pop     r14
0x180002778  pop     rdi
0x180002779  pop     rsi
0x18000277a  retn
0x18001071c  push    rbp
0x18001071e  sub     rsp, 30h
0x180010722  mov     rbp, rdx
0x180010725  mov     rax, [rcx]
0x180010728  mov     edx, [rax]
0x18001072a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001072f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180010733  lea     r9, dllmain_crt_dispatch; int
0x18001073a  mov     r8, [rbp+70h]; int
0x18001073e  mov     edx, [rbp+68h]; int
0x180010741  mov     rcx, [rbp+60h]; int
0x180010745  call    __scrt_dllmain_exception_filter
0x18001074a  nop
0x18001074b  add     rsp, 30h
0x18001074f  pop     rbp
0x180010750  retn
```
