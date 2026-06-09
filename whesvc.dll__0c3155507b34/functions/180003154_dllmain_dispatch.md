# dllmain_dispatch

- ea: `0x180003154`
- end: `0x18000327b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180003290`

## callees

- `0x180002f70`
- `0x180003154`
- `0x180003414`
- `0x1800037ec`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180034790 <= 0 )
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
0x180003154  mov     rax, rsp
0x180003157  mov     [rax+20h], rbx
0x18000315b  mov     [rax+18h], r8
0x18000315f  mov     [rax+10h], edx
0x180003162  mov     [rax+8], rcx
0x180003166  push    rsi
0x180003167  push    rdi
0x180003168  push    r14
0x18000316a  sub     rsp, 40h
0x18000316e  mov     rsi, r8
0x180003171  mov     edi, edx
0x180003173  mov     r14, rcx
0x180003176  test    edx, edx
0x180003178  jnz     short loc_180003189
0x18000317a  cmp     cs:dword_180034790, edx
0x180003180  jg      short loc_180003189
0x180003182  xor     eax, eax
0x180003184  jmp     loc_18000326D
0x180003189  lea     eax, [rdx-1]
0x18000318c  cmp     eax, 1
0x18000318f  ja      short loc_1800031D0
0x180003191  mov     rax, cs:_pRawDllMain
0x180003198  test    rax, rax
0x18000319b  jnz     short loc_1800031A2
0x18000319d  lea     ebx, [rax+1]
0x1800031a0  jmp     short loc_1800031A9
0x1800031a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031a7  mov     ebx, eax
0x1800031a9  mov     [rsp+58h+var_28], ebx
0x1800031ad  test    ebx, ebx
0x1800031af  jz      loc_180003263
0x1800031b5  mov     r8, rsi
0x1800031b8  mov     edx, edi
0x1800031ba  mov     rcx, r14
0x1800031bd  call    dllmain_crt_dispatch
0x1800031c2  mov     ebx, eax
0x1800031c4  mov     [rsp+58h+var_28], eax
0x1800031c8  test    eax, eax
0x1800031ca  jz      loc_180003263
0x1800031d0  mov     r8, rsi; lpvReserved
0x1800031d3  mov     edx, edi; fdwReason
0x1800031d5  mov     rcx, r14; hinstDLL
0x1800031d8  call    DllMain
0x1800031dd  mov     ebx, eax
0x1800031df  mov     [rsp+58h+var_28], eax
0x1800031e3  cmp     edi, 1
0x1800031e6  jnz     short loc_18000321F
0x1800031e8  test    eax, eax
0x1800031ea  jnz     short loc_18000321F
0x1800031ec  mov     r8, rsi; lpvReserved
0x1800031ef  xor     edx, edx; fdwReason
0x1800031f1  mov     rcx, r14; hinstDLL
0x1800031f4  call    DllMain
0x1800031f9  mov     r8, rsi
0x1800031fc  xor     edx, edx
0x1800031fe  mov     rcx, r14
0x180003201  call    dllmain_crt_dispatch
0x180003206  mov     rax, cs:_pRawDllMain
0x18000320d  test    rax, rax
0x180003210  jz      short loc_18000321F
0x180003212  mov     r8, rsi
0x180003215  xor     edx, edx
0x180003217  mov     rcx, r14
0x18000321a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000321f  test    edi, edi
0x180003221  jz      short loc_180003228
0x180003223  cmp     edi, 3
0x180003226  jnz     short loc_180003263
0x180003228  mov     r8, rsi
0x18000322b  mov     edx, edi
0x18000322d  mov     rcx, r14
0x180003230  call    dllmain_crt_dispatch
0x180003235  mov     ebx, eax
0x180003237  mov     [rsp+58h+var_28], eax
0x18000323b  test    eax, eax
0x18000323d  jz      short loc_180003263
0x18000323f  mov     rax, cs:_pRawDllMain
0x180003246  test    rax, rax
0x180003249  jnz     short loc_180003250
0x18000324b  lea     ebx, [rax+1]
0x18000324e  jmp     short loc_18000325F
0x180003250  mov     r8, rsi
0x180003253  mov     edx, edi
0x180003255  mov     rcx, r14
0x180003258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000325d  mov     ebx, eax
0x18000325f  mov     [rsp+58h+var_28], ebx
0x180003263  jmp     short loc_18000326B
0x180003265  xor     ebx, ebx
0x180003267  mov     [rsp+58h+var_28], ebx
0x18000326b  mov     eax, ebx
0x18000326d  mov     rbx, [rsp+58h+arg_18]
0x180003272  add     rsp, 40h
0x180003276  pop     r14
0x180003278  pop     rdi
0x180003279  pop     rsi
0x18000327a  retn
0x1800266ec  push    rbp
0x1800266ee  sub     rsp, 30h
0x1800266f2  mov     rbp, rdx
0x1800266f5  mov     rax, [rcx]
0x1800266f8  mov     edx, [rax]
0x1800266fa  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800266ff  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180026703  lea     r9, dllmain_crt_dispatch; int
0x18002670a  mov     r8, [rbp+70h]; int
0x18002670e  mov     edx, [rbp+68h]; int
0x180026711  mov     rcx, [rbp+60h]; int
0x180026715  call    __scrt_dllmain_exception_filter
0x18002671a  nop
0x18002671b  add     rsp, 30h
0x18002671f  pop     rbp
0x180026720  retn
```
