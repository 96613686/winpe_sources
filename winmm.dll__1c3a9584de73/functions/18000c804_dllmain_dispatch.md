# dllmain_dispatch

- ea: `0x18000c804`
- end: `0x18000c92b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000c940`

## callees

- `0x180004774`
- `0x18000c620`
- `0x18000c804`
- `0x18000cb78`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180025A70 <= 0 )
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
0x18000c804  mov     rax, rsp
0x18000c807  mov     [rax+20h], rbx
0x18000c80b  mov     [rax+18h], r8
0x18000c80f  mov     [rax+10h], edx
0x18000c812  mov     [rax+8], rcx
0x18000c816  push    rsi
0x18000c817  push    rdi
0x18000c818  push    r14
0x18000c81a  sub     rsp, 40h
0x18000c81e  mov     rsi, r8
0x18000c821  mov     edi, edx
0x18000c823  mov     r14, rcx
0x18000c826  test    edx, edx
0x18000c828  jnz     short loc_18000C839
0x18000c82a  cmp     cs:dword_180025A70, edx
0x18000c830  jg      short loc_18000C839
0x18000c832  xor     eax, eax
0x18000c834  jmp     loc_18000C91D
0x18000c839  lea     eax, [rdx-1]
0x18000c83c  cmp     eax, 1
0x18000c83f  ja      short loc_18000C880
0x18000c841  mov     rax, cs:_pRawDllMain
0x18000c848  test    rax, rax
0x18000c84b  jnz     short loc_18000C852
0x18000c84d  lea     ebx, [rax+1]
0x18000c850  jmp     short loc_18000C859
0x18000c852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c857  mov     ebx, eax
0x18000c859  mov     [rsp+58h+var_28], ebx
0x18000c85d  test    ebx, ebx
0x18000c85f  jz      loc_18000C913
0x18000c865  mov     r8, rsi
0x18000c868  mov     edx, edi
0x18000c86a  mov     rcx, r14
0x18000c86d  call    dllmain_crt_dispatch
0x18000c872  mov     ebx, eax
0x18000c874  mov     [rsp+58h+var_28], eax
0x18000c878  test    eax, eax
0x18000c87a  jz      loc_18000C913
0x18000c880  mov     r8, rsi; lpvReserved
0x18000c883  mov     edx, edi; fdwReason
0x18000c885  mov     rcx, r14; hinstDLL
0x18000c888  call    DllMain
0x18000c88d  mov     ebx, eax
0x18000c88f  mov     [rsp+58h+var_28], eax
0x18000c893  cmp     edi, 1
0x18000c896  jnz     short loc_18000C8CF
0x18000c898  test    eax, eax
0x18000c89a  jnz     short loc_18000C8CF
0x18000c89c  mov     r8, rsi; lpvReserved
0x18000c89f  xor     edx, edx; fdwReason
0x18000c8a1  mov     rcx, r14; hinstDLL
0x18000c8a4  call    DllMain
0x18000c8a9  mov     r8, rsi
0x18000c8ac  xor     edx, edx
0x18000c8ae  mov     rcx, r14
0x18000c8b1  call    dllmain_crt_dispatch
0x18000c8b6  mov     rax, cs:_pRawDllMain
0x18000c8bd  test    rax, rax
0x18000c8c0  jz      short loc_18000C8CF
0x18000c8c2  mov     r8, rsi
0x18000c8c5  xor     edx, edx
0x18000c8c7  mov     rcx, r14
0x18000c8ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8cf  test    edi, edi
0x18000c8d1  jz      short loc_18000C8D8
0x18000c8d3  cmp     edi, 3
0x18000c8d6  jnz     short loc_18000C913
0x18000c8d8  mov     r8, rsi
0x18000c8db  mov     edx, edi
0x18000c8dd  mov     rcx, r14
0x18000c8e0  call    dllmain_crt_dispatch
0x18000c8e5  mov     ebx, eax
0x18000c8e7  mov     [rsp+58h+var_28], eax
0x18000c8eb  test    eax, eax
0x18000c8ed  jz      short loc_18000C913
0x18000c8ef  mov     rax, cs:_pRawDllMain
0x18000c8f6  test    rax, rax
0x18000c8f9  jnz     short loc_18000C900
0x18000c8fb  lea     ebx, [rax+1]
0x18000c8fe  jmp     short loc_18000C90F
0x18000c900  mov     r8, rsi
0x18000c903  mov     edx, edi
0x18000c905  mov     rcx, r14
0x18000c908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c90d  mov     ebx, eax
0x18000c90f  mov     [rsp+58h+var_28], ebx
0x18000c913  jmp     short loc_18000C91B
0x18000c915  xor     ebx, ebx
0x18000c917  mov     [rsp+58h+var_28], ebx
0x18000c91b  mov     eax, ebx
0x18000c91d  mov     rbx, [rsp+58h+arg_18]
0x18000c922  add     rsp, 40h
0x18000c926  pop     r14
0x18000c928  pop     rdi
0x18000c929  pop     rsi
0x18000c92a  retn
0x18001aac1  push    rbp
0x18001aac3  sub     rsp, 30h
0x18001aac7  mov     rbp, rdx
0x18001aaca  mov     rax, [rcx]
0x18001aacd  mov     edx, [rax]
0x18001aacf  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001aad4  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18001aad8  lea     r9, dllmain_crt_dispatch; int
0x18001aadf  mov     r8, [rbp+70h]; int
0x18001aae3  mov     edx, [rbp+68h]; int
0x18001aae6  mov     rcx, [rbp+60h]; int
0x18001aaea  call    __scrt_dllmain_exception_filter
0x18001aaef  nop
0x18001aaf0  add     rsp, 30h
0x18001aaf4  pop     rbp
0x18001aaf5  retn
```
