# dllmain_dispatch

- ea: `0x180002544`
- end: `0x18000266b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002680`

## callees

- `0x180002360`
- `0x180002544`
- `0x1800027cc`
- `0x18000a880`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180015430 <= 0 )
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
0x180002544  mov     rax, rsp
0x180002547  mov     [rax+20h], rbx
0x18000254b  mov     [rax+18h], r8
0x18000254f  mov     [rax+10h], edx
0x180002552  mov     [rax+8], rcx
0x180002556  push    rsi
0x180002557  push    rdi
0x180002558  push    r14
0x18000255a  sub     rsp, 40h
0x18000255e  mov     rsi, r8
0x180002561  mov     edi, edx
0x180002563  mov     r14, rcx
0x180002566  test    edx, edx
0x180002568  jnz     short loc_180002579
0x18000256a  cmp     cs:dword_180015430, edx
0x180002570  jg      short loc_180002579
0x180002572  xor     eax, eax
0x180002574  jmp     loc_18000265D
0x180002579  lea     eax, [rdx-1]
0x18000257c  cmp     eax, 1
0x18000257f  ja      short loc_1800025C0
0x180002581  mov     rax, cs:_pRawDllMain
0x180002588  test    rax, rax
0x18000258b  jnz     short loc_180002592
0x18000258d  lea     ebx, [rax+1]
0x180002590  jmp     short loc_180002599
0x180002592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002597  mov     ebx, eax
0x180002599  mov     [rsp+58h+var_28], ebx
0x18000259d  test    ebx, ebx
0x18000259f  jz      loc_180002653
0x1800025a5  mov     r8, rsi
0x1800025a8  mov     edx, edi
0x1800025aa  mov     rcx, r14
0x1800025ad  call    dllmain_crt_dispatch
0x1800025b2  mov     ebx, eax
0x1800025b4  mov     [rsp+58h+var_28], eax
0x1800025b8  test    eax, eax
0x1800025ba  jz      loc_180002653
0x1800025c0  mov     r8, rsi; lpvReserved
0x1800025c3  mov     edx, edi; fdwReason
0x1800025c5  mov     rcx, r14; hinstDLL
0x1800025c8  call    DllMain
0x1800025cd  mov     ebx, eax
0x1800025cf  mov     [rsp+58h+var_28], eax
0x1800025d3  cmp     edi, 1
0x1800025d6  jnz     short loc_18000260F
0x1800025d8  test    eax, eax
0x1800025da  jnz     short loc_18000260F
0x1800025dc  mov     r8, rsi; lpvReserved
0x1800025df  xor     edx, edx; fdwReason
0x1800025e1  mov     rcx, r14; hinstDLL
0x1800025e4  call    DllMain
0x1800025e9  mov     r8, rsi
0x1800025ec  xor     edx, edx
0x1800025ee  mov     rcx, r14
0x1800025f1  call    dllmain_crt_dispatch
0x1800025f6  mov     rax, cs:_pRawDllMain
0x1800025fd  test    rax, rax
0x180002600  jz      short loc_18000260F
0x180002602  mov     r8, rsi
0x180002605  xor     edx, edx
0x180002607  mov     rcx, r14
0x18000260a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000260f  test    edi, edi
0x180002611  jz      short loc_180002618
0x180002613  cmp     edi, 3
0x180002616  jnz     short loc_180002653
0x180002618  mov     r8, rsi
0x18000261b  mov     edx, edi
0x18000261d  mov     rcx, r14
0x180002620  call    dllmain_crt_dispatch
0x180002625  mov     ebx, eax
0x180002627  mov     [rsp+58h+var_28], eax
0x18000262b  test    eax, eax
0x18000262d  jz      short loc_180002653
0x18000262f  mov     rax, cs:_pRawDllMain
0x180002636  test    rax, rax
0x180002639  jnz     short loc_180002640
0x18000263b  lea     ebx, [rax+1]
0x18000263e  jmp     short loc_18000264F
0x180002640  mov     r8, rsi
0x180002643  mov     edx, edi
0x180002645  mov     rcx, r14
0x180002648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000264d  mov     ebx, eax
0x18000264f  mov     [rsp+58h+var_28], ebx
0x180002653  jmp     short loc_18000265B
0x180002655  xor     ebx, ebx
0x180002657  mov     [rsp+58h+var_28], ebx
0x18000265b  mov     eax, ebx
0x18000265d  mov     rbx, [rsp+58h+arg_18]
0x180002662  add     rsp, 40h
0x180002666  pop     r14
0x180002668  pop     rdi
0x180002669  pop     rsi
0x18000266a  retn
0x18000e52c  push    rbp
0x18000e52e  sub     rsp, 30h
0x18000e532  mov     rbp, rdx
0x18000e535  mov     rax, [rcx]
0x18000e538  mov     edx, [rax]
0x18000e53a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000e53f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000e543  lea     r9, dllmain_crt_dispatch; int
0x18000e54a  mov     r8, [rbp+70h]; int
0x18000e54e  mov     edx, [rbp+68h]; int
0x18000e551  mov     rcx, [rbp+60h]; int
0x18000e555  call    __scrt_dllmain_exception_filter
0x18000e55a  nop
0x18000e55b  add     rsp, 30h
0x18000e55f  pop     rbp
0x18000e560  retn
```
