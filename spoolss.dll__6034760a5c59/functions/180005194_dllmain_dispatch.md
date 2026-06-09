# dllmain_dispatch

- ea: `0x180005194`
- end: `0x1800052bb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800052d0`

## callees

- `0x1800021c0`
- `0x180004fb0`
- `0x180005194`
- `0x18000541c`
- `0x180016010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180021370 <= 0 )
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
0x180005194  mov     rax, rsp
0x180005197  mov     [rax+20h], rbx
0x18000519b  mov     [rax+18h], r8
0x18000519f  mov     [rax+10h], edx
0x1800051a2  mov     [rax+8], rcx
0x1800051a6  push    rsi
0x1800051a7  push    rdi
0x1800051a8  push    r14
0x1800051aa  sub     rsp, 40h
0x1800051ae  mov     rsi, r8
0x1800051b1  mov     edi, edx
0x1800051b3  mov     r14, rcx
0x1800051b6  test    edx, edx
0x1800051b8  jnz     short loc_1800051C9
0x1800051ba  cmp     cs:dword_180021370, edx
0x1800051c0  jg      short loc_1800051C9
0x1800051c2  xor     eax, eax
0x1800051c4  jmp     loc_1800052AD
0x1800051c9  lea     eax, [rdx-1]
0x1800051cc  cmp     eax, 1
0x1800051cf  ja      short loc_180005210
0x1800051d1  mov     rax, cs:_pRawDllMain
0x1800051d8  test    rax, rax
0x1800051db  jnz     short loc_1800051E2
0x1800051dd  lea     ebx, [rax+1]
0x1800051e0  jmp     short loc_1800051E9
0x1800051e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051e7  mov     ebx, eax
0x1800051e9  mov     [rsp+58h+var_28], ebx
0x1800051ed  test    ebx, ebx
0x1800051ef  jz      loc_1800052A3
0x1800051f5  mov     r8, rsi
0x1800051f8  mov     edx, edi
0x1800051fa  mov     rcx, r14
0x1800051fd  call    dllmain_crt_dispatch
0x180005202  mov     ebx, eax
0x180005204  mov     [rsp+58h+var_28], eax
0x180005208  test    eax, eax
0x18000520a  jz      loc_1800052A3
0x180005210  mov     r8, rsi; lpvReserved
0x180005213  mov     edx, edi; fdwReason
0x180005215  mov     rcx, r14; hinstDLL
0x180005218  call    DllMain
0x18000521d  mov     ebx, eax
0x18000521f  mov     [rsp+58h+var_28], eax
0x180005223  cmp     edi, 1
0x180005226  jnz     short loc_18000525F
0x180005228  test    eax, eax
0x18000522a  jnz     short loc_18000525F
0x18000522c  mov     r8, rsi; lpvReserved
0x18000522f  xor     edx, edx; fdwReason
0x180005231  mov     rcx, r14; hinstDLL
0x180005234  call    DllMain
0x180005239  mov     r8, rsi
0x18000523c  xor     edx, edx
0x18000523e  mov     rcx, r14
0x180005241  call    dllmain_crt_dispatch
0x180005246  mov     rax, cs:_pRawDllMain
0x18000524d  test    rax, rax
0x180005250  jz      short loc_18000525F
0x180005252  mov     r8, rsi
0x180005255  xor     edx, edx
0x180005257  mov     rcx, r14
0x18000525a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000525f  test    edi, edi
0x180005261  jz      short loc_180005268
0x180005263  cmp     edi, 3
0x180005266  jnz     short loc_1800052A3
0x180005268  mov     r8, rsi
0x18000526b  mov     edx, edi
0x18000526d  mov     rcx, r14
0x180005270  call    dllmain_crt_dispatch
0x180005275  mov     ebx, eax
0x180005277  mov     [rsp+58h+var_28], eax
0x18000527b  test    eax, eax
0x18000527d  jz      short loc_1800052A3
0x18000527f  mov     rax, cs:_pRawDllMain
0x180005286  test    rax, rax
0x180005289  jnz     short loc_180005290
0x18000528b  lea     ebx, [rax+1]
0x18000528e  jmp     short loc_18000529F
0x180005290  mov     r8, rsi
0x180005293  mov     edx, edi
0x180005295  mov     rcx, r14
0x180005298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000529d  mov     ebx, eax
0x18000529f  mov     [rsp+58h+var_28], ebx
0x1800052a3  jmp     short loc_1800052AB
0x1800052a5  xor     ebx, ebx
0x1800052a7  mov     [rsp+58h+var_28], ebx
0x1800052ab  mov     eax, ebx
0x1800052ad  mov     rbx, [rsp+58h+arg_18]
0x1800052b2  add     rsp, 40h
0x1800052b6  pop     r14
0x1800052b8  pop     rdi
0x1800052b9  pop     rsi
0x1800052ba  retn
0x180015130  push    rbp
0x180015132  sub     rsp, 30h
0x180015136  mov     rbp, rdx
0x180015139  mov     rax, [rcx]
0x18001513c  mov     edx, [rax]
0x18001513e  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180015143  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180015147  lea     r9, dllmain_crt_dispatch; int
0x18001514e  mov     r8, [rbp+70h]; int
0x180015152  mov     edx, [rbp+68h]; int
0x180015155  mov     rcx, [rbp+60h]; int
0x180015159  call    __scrt_dllmain_exception_filter
0x18001515e  nop
0x18001515f  add     rsp, 30h
0x180015163  pop     rbp
0x180015164  retn
```
