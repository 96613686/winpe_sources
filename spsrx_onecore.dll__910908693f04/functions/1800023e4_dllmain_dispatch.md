# dllmain_dispatch

- ea: `0x1800023e4`
- end: `0x18000250b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002520`

## callees

- `0x180002200`
- `0x1800023e4`
- `0x1800026c8`
- `0x180002f78`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180015190 <= 0 )
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
0x1800023e4  mov     rax, rsp
0x1800023e7  mov     [rax+20h], rbx
0x1800023eb  mov     [rax+18h], r8
0x1800023ef  mov     [rax+10h], edx
0x1800023f2  mov     [rax+8], rcx
0x1800023f6  push    rsi
0x1800023f7  push    rdi
0x1800023f8  push    r14
0x1800023fa  sub     rsp, 40h
0x1800023fe  mov     rsi, r8
0x180002401  mov     edi, edx
0x180002403  mov     r14, rcx
0x180002406  test    edx, edx
0x180002408  jnz     short loc_180002419
0x18000240a  cmp     cs:dword_180015190, edx
0x180002410  jg      short loc_180002419
0x180002412  xor     eax, eax
0x180002414  jmp     loc_1800024FD
0x180002419  lea     eax, [rdx-1]
0x18000241c  cmp     eax, 1
0x18000241f  ja      short loc_180002460
0x180002421  mov     rax, cs:_pRawDllMain
0x180002428  test    rax, rax
0x18000242b  jnz     short loc_180002432
0x18000242d  lea     ebx, [rax+1]
0x180002430  jmp     short loc_180002439
0x180002432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002437  mov     ebx, eax
0x180002439  mov     [rsp+58h+var_28], ebx
0x18000243d  test    ebx, ebx
0x18000243f  jz      loc_1800024F3
0x180002445  mov     r8, rsi
0x180002448  mov     edx, edi
0x18000244a  mov     rcx, r14
0x18000244d  call    dllmain_crt_dispatch
0x180002452  mov     ebx, eax
0x180002454  mov     [rsp+58h+var_28], eax
0x180002458  test    eax, eax
0x18000245a  jz      loc_1800024F3
0x180002460  mov     r8, rsi; lpvReserved
0x180002463  mov     edx, edi; fdwReason
0x180002465  mov     rcx, r14; hinstDLL
0x180002468  call    DllMain
0x18000246d  mov     ebx, eax
0x18000246f  mov     [rsp+58h+var_28], eax
0x180002473  cmp     edi, 1
0x180002476  jnz     short loc_1800024AF
0x180002478  test    eax, eax
0x18000247a  jnz     short loc_1800024AF
0x18000247c  mov     r8, rsi; lpvReserved
0x18000247f  xor     edx, edx; fdwReason
0x180002481  mov     rcx, r14; hinstDLL
0x180002484  call    DllMain
0x180002489  mov     r8, rsi
0x18000248c  xor     edx, edx
0x18000248e  mov     rcx, r14
0x180002491  call    dllmain_crt_dispatch
0x180002496  mov     rax, cs:_pRawDllMain
0x18000249d  test    rax, rax
0x1800024a0  jz      short loc_1800024AF
0x1800024a2  mov     r8, rsi
0x1800024a5  xor     edx, edx
0x1800024a7  mov     rcx, r14
0x1800024aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024af  test    edi, edi
0x1800024b1  jz      short loc_1800024B8
0x1800024b3  cmp     edi, 3
0x1800024b6  jnz     short loc_1800024F3
0x1800024b8  mov     r8, rsi
0x1800024bb  mov     edx, edi
0x1800024bd  mov     rcx, r14
0x1800024c0  call    dllmain_crt_dispatch
0x1800024c5  mov     ebx, eax
0x1800024c7  mov     [rsp+58h+var_28], eax
0x1800024cb  test    eax, eax
0x1800024cd  jz      short loc_1800024F3
0x1800024cf  mov     rax, cs:_pRawDllMain
0x1800024d6  test    rax, rax
0x1800024d9  jnz     short loc_1800024E0
0x1800024db  lea     ebx, [rax+1]
0x1800024de  jmp     short loc_1800024EF
0x1800024e0  mov     r8, rsi
0x1800024e3  mov     edx, edi
0x1800024e5  mov     rcx, r14
0x1800024e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024ed  mov     ebx, eax
0x1800024ef  mov     [rsp+58h+var_28], ebx
0x1800024f3  jmp     short loc_1800024FB
0x1800024f5  xor     ebx, ebx
0x1800024f7  mov     [rsp+58h+var_28], ebx
0x1800024fb  mov     eax, ebx
0x1800024fd  mov     rbx, [rsp+58h+arg_18]
0x180002502  add     rsp, 40h
0x180002506  pop     r14
0x180002508  pop     rdi
0x180002509  pop     rsi
0x18000250a  retn
0x1800035b6  push    rbp
0x1800035b8  sub     rsp, 30h
0x1800035bc  mov     rbp, rdx
0x1800035bf  mov     rax, [rcx]
0x1800035c2  mov     edx, [rax]
0x1800035c4  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800035c9  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800035cd  lea     r9, dllmain_crt_dispatch; int
0x1800035d4  mov     r8, [rbp+70h]; int
0x1800035d8  mov     edx, [rbp+68h]; int
0x1800035db  mov     rcx, [rbp+60h]; int
0x1800035df  call    __scrt_dllmain_exception_filter
0x1800035e4  nop
0x1800035e5  add     rsp, 30h
0x1800035e9  pop     rbp
0x1800035ea  retn
```
