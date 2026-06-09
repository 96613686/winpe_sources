# dllmain_dispatch

- ea: `0x1800055a4`
- end: `0x1800056cb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800056e0`

## callees

- `0x1800022c0`
- `0x1800053c0`
- `0x1800055a4`
- `0x180005960`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180010110 <= 0 )
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
0x1800055a4  mov     rax, rsp
0x1800055a7  mov     [rax+20h], rbx
0x1800055ab  mov     [rax+18h], r8
0x1800055af  mov     [rax+10h], edx
0x1800055b2  mov     [rax+8], rcx
0x1800055b6  push    rsi
0x1800055b7  push    rdi
0x1800055b8  push    r14
0x1800055ba  sub     rsp, 40h
0x1800055be  mov     rsi, r8
0x1800055c1  mov     edi, edx
0x1800055c3  mov     r14, rcx
0x1800055c6  test    edx, edx
0x1800055c8  jnz     short loc_1800055D9
0x1800055ca  cmp     cs:dword_180010110, edx
0x1800055d0  jg      short loc_1800055D9
0x1800055d2  xor     eax, eax
0x1800055d4  jmp     loc_1800056BD
0x1800055d9  lea     eax, [rdx-1]
0x1800055dc  cmp     eax, 1
0x1800055df  ja      short loc_180005620
0x1800055e1  mov     rax, cs:_pRawDllMain
0x1800055e8  test    rax, rax
0x1800055eb  jnz     short loc_1800055F2
0x1800055ed  lea     ebx, [rax+1]
0x1800055f0  jmp     short loc_1800055F9
0x1800055f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055f7  mov     ebx, eax
0x1800055f9  mov     [rsp+58h+var_28], ebx
0x1800055fd  test    ebx, ebx
0x1800055ff  jz      loc_1800056B3
0x180005605  mov     r8, rsi
0x180005608  mov     edx, edi
0x18000560a  mov     rcx, r14
0x18000560d  call    dllmain_crt_dispatch
0x180005612  mov     ebx, eax
0x180005614  mov     [rsp+58h+var_28], eax
0x180005618  test    eax, eax
0x18000561a  jz      loc_1800056B3
0x180005620  mov     r8, rsi; lpvReserved
0x180005623  mov     edx, edi; fdwReason
0x180005625  mov     rcx, r14; hinstDLL
0x180005628  call    DllMain
0x18000562d  mov     ebx, eax
0x18000562f  mov     [rsp+58h+var_28], eax
0x180005633  cmp     edi, 1
0x180005636  jnz     short loc_18000566F
0x180005638  test    eax, eax
0x18000563a  jnz     short loc_18000566F
0x18000563c  mov     r8, rsi; lpvReserved
0x18000563f  xor     edx, edx; fdwReason
0x180005641  mov     rcx, r14; hinstDLL
0x180005644  call    DllMain
0x180005649  mov     r8, rsi
0x18000564c  xor     edx, edx
0x18000564e  mov     rcx, r14
0x180005651  call    dllmain_crt_dispatch
0x180005656  mov     rax, cs:_pRawDllMain
0x18000565d  test    rax, rax
0x180005660  jz      short loc_18000566F
0x180005662  mov     r8, rsi
0x180005665  xor     edx, edx
0x180005667  mov     rcx, r14
0x18000566a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000566f  test    edi, edi
0x180005671  jz      short loc_180005678
0x180005673  cmp     edi, 3
0x180005676  jnz     short loc_1800056B3
0x180005678  mov     r8, rsi
0x18000567b  mov     edx, edi
0x18000567d  mov     rcx, r14
0x180005680  call    dllmain_crt_dispatch
0x180005685  mov     ebx, eax
0x180005687  mov     [rsp+58h+var_28], eax
0x18000568b  test    eax, eax
0x18000568d  jz      short loc_1800056B3
0x18000568f  mov     rax, cs:_pRawDllMain
0x180005696  test    rax, rax
0x180005699  jnz     short loc_1800056A0
0x18000569b  lea     ebx, [rax+1]
0x18000569e  jmp     short loc_1800056AF
0x1800056a0  mov     r8, rsi
0x1800056a3  mov     edx, edi
0x1800056a5  mov     rcx, r14
0x1800056a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056ad  mov     ebx, eax
0x1800056af  mov     [rsp+58h+var_28], ebx
0x1800056b3  jmp     short loc_1800056BB
0x1800056b5  xor     ebx, ebx
0x1800056b7  mov     [rsp+58h+var_28], ebx
0x1800056bb  mov     eax, ebx
0x1800056bd  mov     rbx, [rsp+58h+arg_18]
0x1800056c2  add     rsp, 40h
0x1800056c6  pop     r14
0x1800056c8  pop     rdi
0x1800056c9  pop     rsi
0x1800056ca  retn
0x18000badc  push    rbp
0x18000bade  sub     rsp, 30h
0x18000bae2  mov     rbp, rdx
0x18000bae5  mov     rax, [rcx]
0x18000bae8  mov     edx, [rax]
0x18000baea  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000baef  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000baf3  lea     r9, dllmain_crt_dispatch; int
0x18000bafa  mov     r8, [rbp+70h]; int
0x18000bafe  mov     edx, [rbp+68h]; int
0x18000bb01  mov     rcx, [rbp+60h]; int
0x18000bb05  call    __scrt_dllmain_exception_filter
0x18000bb0a  nop
0x18000bb0b  add     rsp, 30h
0x18000bb0f  pop     rbp
0x18000bb10  retn
```
