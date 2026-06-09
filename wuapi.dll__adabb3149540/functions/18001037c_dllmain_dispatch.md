# dllmain_dispatch

- ea: `0x18001037c`
- end: `0x1800104a3`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800104b0`

## callees

- `0x180007d00`
- `0x18000fde8`
- `0x180010180`
- `0x18001037c`
- `0x180015a00`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180021824 <= 0 )
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
0x18001037c  mov     rax, rsp
0x18001037f  mov     [rax+20h], rbx
0x180010383  mov     [rax+18h], r8
0x180010387  mov     [rax+10h], edx
0x18001038a  mov     [rax+8], rcx
0x18001038e  push    rsi
0x18001038f  push    rdi
0x180010390  push    r14
0x180010392  sub     rsp, 40h
0x180010396  mov     rsi, r8
0x180010399  mov     edi, edx
0x18001039b  mov     r14, rcx
0x18001039e  test    edx, edx
0x1800103a0  jnz     short loc_1800103B1
0x1800103a2  cmp     cs:dword_180021824, edx
0x1800103a8  jg      short loc_1800103B1
0x1800103aa  xor     eax, eax
0x1800103ac  jmp     loc_180010495
0x1800103b1  lea     eax, [rdx-1]
0x1800103b4  cmp     eax, 1
0x1800103b7  ja      short loc_1800103F8
0x1800103b9  mov     rax, cs:_pRawDllMain
0x1800103c0  test    rax, rax
0x1800103c3  jnz     short loc_1800103CA
0x1800103c5  lea     ebx, [rax+1]
0x1800103c8  jmp     short loc_1800103D1
0x1800103ca  call    _guard_dispatch_icall
0x1800103cf  mov     ebx, eax
0x1800103d1  mov     [rsp+58h+var_28], ebx
0x1800103d5  test    ebx, ebx
0x1800103d7  jz      loc_18001048B
0x1800103dd  mov     r8, rsi
0x1800103e0  mov     edx, edi
0x1800103e2  mov     rcx, r14
0x1800103e5  call    dllmain_crt_dispatch
0x1800103ea  mov     ebx, eax
0x1800103ec  mov     [rsp+58h+var_28], eax
0x1800103f0  test    eax, eax
0x1800103f2  jz      loc_18001048B
0x1800103f8  mov     r8, rsi; lpvReserved
0x1800103fb  mov     edx, edi; fdwReason
0x1800103fd  mov     rcx, r14; hinstDLL
0x180010400  call    DllMain
0x180010405  mov     ebx, eax
0x180010407  mov     [rsp+58h+var_28], eax
0x18001040b  cmp     edi, 1
0x18001040e  jnz     short loc_180010447
0x180010410  test    eax, eax
0x180010412  jnz     short loc_180010447
0x180010414  mov     r8, rsi; lpvReserved
0x180010417  xor     edx, edx; fdwReason
0x180010419  mov     rcx, r14; hinstDLL
0x18001041c  call    DllMain
0x180010421  mov     r8, rsi
0x180010424  xor     edx, edx
0x180010426  mov     rcx, r14
0x180010429  call    dllmain_crt_dispatch
0x18001042e  mov     rax, cs:_pRawDllMain
0x180010435  test    rax, rax
0x180010438  jz      short loc_180010447
0x18001043a  mov     r8, rsi
0x18001043d  xor     edx, edx
0x18001043f  mov     rcx, r14
0x180010442  call    _guard_dispatch_icall
0x180010447  test    edi, edi
0x180010449  jz      short loc_180010450
0x18001044b  cmp     edi, 3
0x18001044e  jnz     short loc_18001048B
0x180010450  mov     r8, rsi
0x180010453  mov     edx, edi
0x180010455  mov     rcx, r14
0x180010458  call    dllmain_crt_dispatch
0x18001045d  mov     ebx, eax
0x18001045f  mov     [rsp+58h+var_28], eax
0x180010463  test    eax, eax
0x180010465  jz      short loc_18001048B
0x180010467  mov     rax, cs:_pRawDllMain
0x18001046e  test    rax, rax
0x180010471  jnz     short loc_180010478
0x180010473  lea     ebx, [rax+1]
0x180010476  jmp     short loc_180010487
0x180010478  mov     r8, rsi
0x18001047b  mov     edx, edi
0x18001047d  mov     rcx, r14
0x180010480  call    _guard_dispatch_icall
0x180010485  mov     ebx, eax
0x180010487  mov     [rsp+58h+var_28], ebx
0x18001048b  jmp     short loc_180010493
0x18001048d  xor     ebx, ebx
0x18001048f  mov     [rsp+58h+var_28], ebx
0x180010493  mov     eax, ebx
0x180010495  mov     rbx, [rsp+58h+arg_18]
0x18001049a  add     rsp, 40h
0x18001049e  pop     r14
0x1800104a0  pop     rdi
0x1800104a1  pop     rsi
0x1800104a2  retn
0x180016c9f  push    rbp
0x180016ca1  sub     rsp, 30h
0x180016ca5  mov     rbp, rdx
0x180016ca8  mov     rax, [rcx]
0x180016cab  mov     edx, [rax]
0x180016cad  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180016cb2  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180016cb6  lea     r9, dllmain_crt_dispatch; int
0x180016cbd  mov     r8, [rbp+70h]; int
0x180016cc1  mov     edx, [rbp+68h]; int
0x180016cc4  mov     rcx, [rbp+60h]; int
0x180016cc8  call    __scrt_dllmain_exception_filter
0x180016ccd  nop
0x180016cce  add     rsp, 30h
0x180016cd2  pop     rbp
0x180016cd3  retn
```
