# dllmain_dispatch

- ea: `0x18001fd74`
- end: `0x18001fe9b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18001feb0`

## callees

- `0x18000ee40`
- `0x18001fb90`
- `0x18001fd74`
- `0x18001fffc`
- `0x180032010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800443F0 <= 0 )
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
0x18001fd74  mov     rax, rsp
0x18001fd77  mov     [rax+20h], rbx
0x18001fd7b  mov     [rax+18h], r8
0x18001fd7f  mov     [rax+10h], edx
0x18001fd82  mov     [rax+8], rcx
0x18001fd86  push    rsi
0x18001fd87  push    rdi
0x18001fd88  push    r14
0x18001fd8a  sub     rsp, 40h
0x18001fd8e  mov     rsi, r8
0x18001fd91  mov     edi, edx
0x18001fd93  mov     r14, rcx
0x18001fd96  test    edx, edx
0x18001fd98  jnz     short loc_18001FDA9
0x18001fd9a  cmp     cs:dword_1800443F0, edx
0x18001fda0  jg      short loc_18001FDA9
0x18001fda2  xor     eax, eax
0x18001fda4  jmp     loc_18001FE8D
0x18001fda9  lea     eax, [rdx-1]
0x18001fdac  cmp     eax, 1
0x18001fdaf  ja      short loc_18001FDF0
0x18001fdb1  mov     rax, cs:_pRawDllMain
0x18001fdb8  test    rax, rax
0x18001fdbb  jnz     short loc_18001FDC2
0x18001fdbd  lea     ebx, [rax+1]
0x18001fdc0  jmp     short loc_18001FDC9
0x18001fdc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fdc7  mov     ebx, eax
0x18001fdc9  mov     [rsp+58h+var_28], ebx
0x18001fdcd  test    ebx, ebx
0x18001fdcf  jz      loc_18001FE83
0x18001fdd5  mov     r8, rsi
0x18001fdd8  mov     edx, edi
0x18001fdda  mov     rcx, r14
0x18001fddd  call    dllmain_crt_dispatch
0x18001fde2  mov     ebx, eax
0x18001fde4  mov     [rsp+58h+var_28], eax
0x18001fde8  test    eax, eax
0x18001fdea  jz      loc_18001FE83
0x18001fdf0  mov     r8, rsi; lpvReserved
0x18001fdf3  mov     edx, edi; fdwReason
0x18001fdf5  mov     rcx, r14; hinstDLL
0x18001fdf8  call    DllMain
0x18001fdfd  mov     ebx, eax
0x18001fdff  mov     [rsp+58h+var_28], eax
0x18001fe03  cmp     edi, 1
0x18001fe06  jnz     short loc_18001FE3F
0x18001fe08  test    eax, eax
0x18001fe0a  jnz     short loc_18001FE3F
0x18001fe0c  mov     r8, rsi; lpvReserved
0x18001fe0f  xor     edx, edx; fdwReason
0x18001fe11  mov     rcx, r14; hinstDLL
0x18001fe14  call    DllMain
0x18001fe19  mov     r8, rsi
0x18001fe1c  xor     edx, edx
0x18001fe1e  mov     rcx, r14
0x18001fe21  call    dllmain_crt_dispatch
0x18001fe26  mov     rax, cs:_pRawDllMain
0x18001fe2d  test    rax, rax
0x18001fe30  jz      short loc_18001FE3F
0x18001fe32  mov     r8, rsi
0x18001fe35  xor     edx, edx
0x18001fe37  mov     rcx, r14
0x18001fe3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe3f  test    edi, edi
0x18001fe41  jz      short loc_18001FE48
0x18001fe43  cmp     edi, 3
0x18001fe46  jnz     short loc_18001FE83
0x18001fe48  mov     r8, rsi
0x18001fe4b  mov     edx, edi
0x18001fe4d  mov     rcx, r14
0x18001fe50  call    dllmain_crt_dispatch
0x18001fe55  mov     ebx, eax
0x18001fe57  mov     [rsp+58h+var_28], eax
0x18001fe5b  test    eax, eax
0x18001fe5d  jz      short loc_18001FE83
0x18001fe5f  mov     rax, cs:_pRawDllMain
0x18001fe66  test    rax, rax
0x18001fe69  jnz     short loc_18001FE70
0x18001fe6b  lea     ebx, [rax+1]
0x18001fe6e  jmp     short loc_18001FE7F
0x18001fe70  mov     r8, rsi
0x18001fe73  mov     edx, edi
0x18001fe75  mov     rcx, r14
0x18001fe78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe7d  mov     ebx, eax
0x18001fe7f  mov     [rsp+58h+var_28], ebx
0x18001fe83  jmp     short loc_18001FE8B
0x18001fe85  xor     ebx, ebx
0x18001fe87  mov     [rsp+58h+var_28], ebx
0x18001fe8b  mov     eax, ebx
0x18001fe8d  mov     rbx, [rsp+58h+arg_18]
0x18001fe92  add     rsp, 40h
0x18001fe96  pop     r14
0x18001fe98  pop     rdi
0x18001fe99  pop     rsi
0x18001fe9a  retn
0x1800317ec  push    rbp
0x1800317ee  sub     rsp, 30h
0x1800317f2  mov     rbp, rdx
0x1800317f5  mov     rax, [rcx]
0x1800317f8  mov     edx, [rax]
0x1800317fa  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800317ff  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180031803  lea     r9, dllmain_crt_dispatch; int
0x18003180a  mov     r8, [rbp+70h]; int
0x18003180e  mov     edx, [rbp+68h]; int
0x180031811  mov     rcx, [rbp+60h]; int
0x180031815  call    __scrt_dllmain_exception_filter
0x18003181a  nop
0x18003181b  add     rsp, 30h
0x18003181f  pop     rbp
0x180031820  retn
```
