# dllmain_dispatch

- ea: `0x18000d824`
- end: `0x18000d94b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000d960`

## callees

- `0x18000c8c0`
- `0x18000d640`
- `0x18000d824`
- `0x18000dae4`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180028310 <= 0 )
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
0x18000d824  mov     rax, rsp
0x18000d827  mov     [rax+20h], rbx
0x18000d82b  mov     [rax+18h], r8
0x18000d82f  mov     [rax+10h], edx
0x18000d832  mov     [rax+8], rcx
0x18000d836  push    rsi
0x18000d837  push    rdi
0x18000d838  push    r14
0x18000d83a  sub     rsp, 40h
0x18000d83e  mov     rsi, r8
0x18000d841  mov     edi, edx
0x18000d843  mov     r14, rcx
0x18000d846  test    edx, edx
0x18000d848  jnz     short loc_18000D859
0x18000d84a  cmp     cs:dword_180028310, edx
0x18000d850  jg      short loc_18000D859
0x18000d852  xor     eax, eax
0x18000d854  jmp     loc_18000D93D
0x18000d859  lea     eax, [rdx-1]
0x18000d85c  cmp     eax, 1
0x18000d85f  ja      short loc_18000D8A0
0x18000d861  mov     rax, cs:_pRawDllMain
0x18000d868  test    rax, rax
0x18000d86b  jnz     short loc_18000D872
0x18000d86d  lea     ebx, [rax+1]
0x18000d870  jmp     short loc_18000D879
0x18000d872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d877  mov     ebx, eax
0x18000d879  mov     [rsp+58h+var_28], ebx
0x18000d87d  test    ebx, ebx
0x18000d87f  jz      loc_18000D933
0x18000d885  mov     r8, rsi
0x18000d888  mov     edx, edi
0x18000d88a  mov     rcx, r14
0x18000d88d  call    dllmain_crt_dispatch
0x18000d892  mov     ebx, eax
0x18000d894  mov     [rsp+58h+var_28], eax
0x18000d898  test    eax, eax
0x18000d89a  jz      loc_18000D933
0x18000d8a0  mov     r8, rsi; lpvReserved
0x18000d8a3  mov     edx, edi; fdwReason
0x18000d8a5  mov     rcx, r14; hinstDLL
0x18000d8a8  call    DllMain
0x18000d8ad  mov     ebx, eax
0x18000d8af  mov     [rsp+58h+var_28], eax
0x18000d8b3  cmp     edi, 1
0x18000d8b6  jnz     short loc_18000D8EF
0x18000d8b8  test    eax, eax
0x18000d8ba  jnz     short loc_18000D8EF
0x18000d8bc  mov     r8, rsi; lpvReserved
0x18000d8bf  xor     edx, edx; fdwReason
0x18000d8c1  mov     rcx, r14; hinstDLL
0x18000d8c4  call    DllMain
0x18000d8c9  mov     r8, rsi
0x18000d8cc  xor     edx, edx
0x18000d8ce  mov     rcx, r14
0x18000d8d1  call    dllmain_crt_dispatch
0x18000d8d6  mov     rax, cs:_pRawDllMain
0x18000d8dd  test    rax, rax
0x18000d8e0  jz      short loc_18000D8EF
0x18000d8e2  mov     r8, rsi
0x18000d8e5  xor     edx, edx
0x18000d8e7  mov     rcx, r14
0x18000d8ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8ef  test    edi, edi
0x18000d8f1  jz      short loc_18000D8F8
0x18000d8f3  cmp     edi, 3
0x18000d8f6  jnz     short loc_18000D933
0x18000d8f8  mov     r8, rsi
0x18000d8fb  mov     edx, edi
0x18000d8fd  mov     rcx, r14
0x18000d900  call    dllmain_crt_dispatch
0x18000d905  mov     ebx, eax
0x18000d907  mov     [rsp+58h+var_28], eax
0x18000d90b  test    eax, eax
0x18000d90d  jz      short loc_18000D933
0x18000d90f  mov     rax, cs:_pRawDllMain
0x18000d916  test    rax, rax
0x18000d919  jnz     short loc_18000D920
0x18000d91b  lea     ebx, [rax+1]
0x18000d91e  jmp     short loc_18000D92F
0x18000d920  mov     r8, rsi
0x18000d923  mov     edx, edi
0x18000d925  mov     rcx, r14
0x18000d928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d92d  mov     ebx, eax
0x18000d92f  mov     [rsp+58h+var_28], ebx
0x18000d933  jmp     short loc_18000D93B
0x18000d935  xor     ebx, ebx
0x18000d937  mov     [rsp+58h+var_28], ebx
0x18000d93b  mov     eax, ebx
0x18000d93d  mov     rbx, [rsp+58h+arg_18]
0x18000d942  add     rsp, 40h
0x18000d946  pop     r14
0x18000d948  pop     rdi
0x18000d949  pop     rsi
0x18000d94a  retn
0x18001ae94  push    rbp
0x18001ae96  sub     rsp, 30h
0x18001ae9a  mov     rbp, rdx
0x18001ae9d  mov     rax, [rcx]
0x18001aea0  mov     edx, [rax]
0x18001aea2  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001aea7  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18001aeab  lea     r9, dllmain_crt_dispatch; int
0x18001aeb2  mov     r8, [rbp+70h]; int
0x18001aeb6  mov     edx, [rbp+68h]; int
0x18001aeb9  mov     rcx, [rbp+60h]; int
0x18001aebd  call    __scrt_dllmain_exception_filter
0x18001aec2  nop
0x18001aec3  add     rsp, 30h
0x18001aec7  pop     rbp
0x18001aec8  retn
```
