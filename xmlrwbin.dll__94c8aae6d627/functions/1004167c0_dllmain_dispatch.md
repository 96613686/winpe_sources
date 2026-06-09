# dllmain_dispatch

- ea: `0x1004167c0`
- end: `0x1004168f1`
- name: `dllmain_dispatch`
- size: `305`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1004168f8`

## callees

- `0x100401140`
- `0x1004165c0`
- `0x100416734`
- `0x1004167c0`
- `0x100416e08`
- `0x100424580`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_100434CD4 <= 0 )
    return 0;
  if ( fdwReason - 1 > 1
    || (!pRawDllMain || (v7 = ((__int64 (*)(void))pRawDllMain)()) != 0)
    && (v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved)) != 0 )
  {
    v8 = DllMain(hinstDLL, fdwReason, lpvReserved);
    v7 = v8;
    if ( fdwReason == 1 && !v8 )
    {
      DllMain(hinstDLL, 0, lpvReserved);
      dllmain_crt_process_detach(lpvReserved != 0);
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
0x1004167c0  mov     rax, rsp
0x1004167c3  mov     [rax+20h], rbx
0x1004167c7  mov     [rax+18h], r8
0x1004167cb  mov     [rax+10h], edx
0x1004167ce  mov     [rax+8], rcx
0x1004167d2  push    rsi
0x1004167d3  push    rdi
0x1004167d4  push    r14
0x1004167d6  sub     rsp, 40h
0x1004167da  mov     rsi, r8
0x1004167dd  mov     edi, edx
0x1004167df  mov     r14, rcx
0x1004167e2  test    edx, edx
0x1004167e4  jnz     short loc_1004167F5
0x1004167e6  cmp     cs:dword_100434CD4, edx
0x1004167ec  jg      short loc_1004167F5
0x1004167ee  xor     eax, eax
0x1004167f0  jmp     loc_1004168E3
0x1004167f5  lea     eax, [rdx-1]
0x1004167f8  cmp     eax, 1
0x1004167fb  ja      short loc_100416842
0x1004167fd  mov     rax, cs:_pRawDllMain
0x100416804  test    rax, rax
0x100416807  jnz     short loc_100416813
0x100416809  mov     [rsp+58h+var_28], 1
0x100416811  jmp     short loc_100416827
0x100416813  call    cs:__guard_dispatch_icall_fptr
0x100416819  mov     ebx, eax
0x10041681b  mov     [rsp+58h+var_28], eax
0x10041681f  test    eax, eax
0x100416821  jz      loc_1004168D9
0x100416827  mov     r8, rsi
0x10041682a  mov     edx, edi
0x10041682c  mov     rcx, r14
0x10041682f  call    dllmain_crt_dispatch
0x100416834  mov     ebx, eax
0x100416836  mov     [rsp+58h+var_28], eax
0x10041683a  test    eax, eax
0x10041683c  jz      loc_1004168D9
0x100416842  mov     r8, rsi; lpvReserved
0x100416845  mov     edx, edi; fdwReason
0x100416847  mov     rcx, r14; hinstDLL
0x10041684a  call    DllMain
0x10041684f  mov     ebx, eax
0x100416851  mov     [rsp+58h+var_28], eax
0x100416855  cmp     edi, 1
0x100416858  jnz     short loc_100416890
0x10041685a  test    eax, eax
0x10041685c  jnz     short loc_100416890
0x10041685e  mov     r8, rsi; lpvReserved
0x100416861  xor     edx, edx; fdwReason
0x100416863  mov     rcx, r14; hinstDLL
0x100416866  call    DllMain
0x10041686b  test    rsi, rsi
0x10041686e  setnz   cl
0x100416871  call    dllmain_crt_process_detach
0x100416876  mov     rax, cs:_pRawDllMain
0x10041687d  test    rax, rax
0x100416880  jz      short loc_100416890
0x100416882  mov     r8, rsi
0x100416885  xor     edx, edx
0x100416887  mov     rcx, r14
0x10041688a  call    cs:__guard_dispatch_icall_fptr
0x100416890  test    edi, edi
0x100416892  jz      short loc_100416899
0x100416894  cmp     edi, 3
0x100416897  jnz     short loc_1004168D9
0x100416899  mov     r8, rsi
0x10041689c  mov     edx, edi
0x10041689e  mov     rcx, r14
0x1004168a1  call    dllmain_crt_dispatch
0x1004168a6  mov     ebx, eax
0x1004168a8  mov     [rsp+58h+var_28], eax
0x1004168ac  test    eax, eax
0x1004168ae  jz      short loc_1004168D9
0x1004168b0  mov     rax, cs:_pRawDllMain
0x1004168b7  test    rax, rax
0x1004168ba  jnz     short loc_1004168C5
0x1004168bc  lea     ebx, [rax+1]
0x1004168bf  mov     [rsp+58h+var_28], ebx
0x1004168c3  jmp     short loc_1004168D9
0x1004168c5  mov     r8, rsi
0x1004168c8  mov     edx, edi
0x1004168ca  mov     rcx, r14
0x1004168cd  call    cs:__guard_dispatch_icall_fptr
0x1004168d3  mov     ebx, eax
0x1004168d5  mov     [rsp+58h+var_28], eax
0x1004168d9  jmp     short loc_1004168E1
0x1004168db  xor     ebx, ebx
0x1004168dd  mov     [rsp+58h+var_28], ebx
0x1004168e1  mov     eax, ebx
0x1004168e3  mov     rbx, [rsp+58h+arg_18]
0x1004168e8  add     rsp, 40h
0x1004168ec  pop     r14
0x1004168ee  pop     rdi
0x1004168ef  pop     rsi
0x1004168f0  retn
0x1004250c0  push    rbp
0x1004250c2  sub     rsp, 30h
0x1004250c6  mov     rbp, rdx
0x1004250c9  mov     rax, [rcx]
0x1004250cc  mov     edx, [rax]
0x1004250ce  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1004250d3  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1004250d7  lea     r9, dllmain_crt_dispatch; int
0x1004250de  mov     r8, [rbp+70h]; int
0x1004250e2  mov     edx, [rbp+68h]; int
0x1004250e5  mov     rcx, [rbp+60h]; int
0x1004250e9  call    __scrt_dllmain_exception_filter
0x1004250ee  nop
0x1004250ef  add     rsp, 30h
0x1004250f3  pop     rbp
0x1004250f4  retn
```
