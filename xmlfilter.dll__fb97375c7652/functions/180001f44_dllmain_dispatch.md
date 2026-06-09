# dllmain_dispatch

- ea: `0x180001f44`
- end: `0x18000206b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002080`

## callees

- `0x180001d60`
- `0x180001f44`
- `0x180002264`
- `0x1800139a0`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800217F0 <= 0 )
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
0x180001f44  mov     rax, rsp
0x180001f47  mov     [rax+20h], rbx
0x180001f4b  mov     [rax+18h], r8
0x180001f4f  mov     [rax+10h], edx
0x180001f52  mov     [rax+8], rcx
0x180001f56  push    rsi
0x180001f57  push    rdi
0x180001f58  push    r14
0x180001f5a  sub     rsp, 40h
0x180001f5e  mov     rsi, r8
0x180001f61  mov     edi, edx
0x180001f63  mov     r14, rcx
0x180001f66  test    edx, edx
0x180001f68  jnz     short loc_180001F79
0x180001f6a  cmp     cs:dword_1800217F0, edx
0x180001f70  jg      short loc_180001F79
0x180001f72  xor     eax, eax
0x180001f74  jmp     loc_18000205D
0x180001f79  lea     eax, [rdx-1]
0x180001f7c  cmp     eax, 1
0x180001f7f  ja      short loc_180001FC0
0x180001f81  mov     rax, cs:_pRawDllMain
0x180001f88  test    rax, rax
0x180001f8b  jnz     short loc_180001F92
0x180001f8d  lea     ebx, [rax+1]
0x180001f90  jmp     short loc_180001F99
0x180001f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f97  mov     ebx, eax
0x180001f99  mov     [rsp+58h+var_28], ebx
0x180001f9d  test    ebx, ebx
0x180001f9f  jz      loc_180002053
0x180001fa5  mov     r8, rsi
0x180001fa8  mov     edx, edi
0x180001faa  mov     rcx, r14
0x180001fad  call    dllmain_crt_dispatch
0x180001fb2  mov     ebx, eax
0x180001fb4  mov     [rsp+58h+var_28], eax
0x180001fb8  test    eax, eax
0x180001fba  jz      loc_180002053
0x180001fc0  mov     r8, rsi; lpvReserved
0x180001fc3  mov     edx, edi; fdwReason
0x180001fc5  mov     rcx, r14; hinstDLL
0x180001fc8  call    DllMain
0x180001fcd  mov     ebx, eax
0x180001fcf  mov     [rsp+58h+var_28], eax
0x180001fd3  cmp     edi, 1
0x180001fd6  jnz     short loc_18000200F
0x180001fd8  test    eax, eax
0x180001fda  jnz     short loc_18000200F
0x180001fdc  mov     r8, rsi; lpvReserved
0x180001fdf  xor     edx, edx; fdwReason
0x180001fe1  mov     rcx, r14; hinstDLL
0x180001fe4  call    DllMain
0x180001fe9  mov     r8, rsi
0x180001fec  xor     edx, edx
0x180001fee  mov     rcx, r14
0x180001ff1  call    dllmain_crt_dispatch
0x180001ff6  mov     rax, cs:_pRawDllMain
0x180001ffd  test    rax, rax
0x180002000  jz      short loc_18000200F
0x180002002  mov     r8, rsi
0x180002005  xor     edx, edx
0x180002007  mov     rcx, r14
0x18000200a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000200f  test    edi, edi
0x180002011  jz      short loc_180002018
0x180002013  cmp     edi, 3
0x180002016  jnz     short loc_180002053
0x180002018  mov     r8, rsi
0x18000201b  mov     edx, edi
0x18000201d  mov     rcx, r14
0x180002020  call    dllmain_crt_dispatch
0x180002025  mov     ebx, eax
0x180002027  mov     [rsp+58h+var_28], eax
0x18000202b  test    eax, eax
0x18000202d  jz      short loc_180002053
0x18000202f  mov     rax, cs:_pRawDllMain
0x180002036  test    rax, rax
0x180002039  jnz     short loc_180002040
0x18000203b  lea     ebx, [rax+1]
0x18000203e  jmp     short loc_18000204F
0x180002040  mov     r8, rsi
0x180002043  mov     edx, edi
0x180002045  mov     rcx, r14
0x180002048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000204d  mov     ebx, eax
0x18000204f  mov     [rsp+58h+var_28], ebx
0x180002053  jmp     short loc_18000205B
0x180002055  xor     ebx, ebx
0x180002057  mov     [rsp+58h+var_28], ebx
0x18000205b  mov     eax, ebx
0x18000205d  mov     rbx, [rsp+58h+arg_18]
0x180002062  add     rsp, 40h
0x180002066  pop     r14
0x180002068  pop     rdi
0x180002069  pop     rsi
0x18000206a  retn
0x18001453c  push    rbp
0x18001453e  sub     rsp, 30h
0x180014542  mov     rbp, rdx
0x180014545  mov     rax, [rcx]
0x180014548  mov     edx, [rax]
0x18001454a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001454f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180014553  lea     r9, dllmain_crt_dispatch; int
0x18001455a  mov     r8, [rbp+70h]; int
0x18001455e  mov     edx, [rbp+68h]; int
0x180014561  mov     rcx, [rbp+60h]; int
0x180014565  call    __scrt_dllmain_exception_filter
0x18001456a  nop
0x18001456b  add     rsp, 30h
0x18001456f  pop     rbp
0x180014570  retn
```
