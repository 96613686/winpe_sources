# dllmain_dispatch

- ea: `0x1004267b0`
- end: `0x1004268e1`
- name: `dllmain_dispatch`
- size: `305`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1004268e8`

## callees

- `0x1004012a0`
- `0x1004265b0`
- `0x100426724`
- `0x1004267b0`
- `0x100426de8`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_100450C54 <= 0 )
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
0x1004267b0  mov     rax, rsp
0x1004267b3  mov     [rax+20h], rbx
0x1004267b7  mov     [rax+18h], r8
0x1004267bb  mov     [rax+10h], edx
0x1004267be  mov     [rax+8], rcx
0x1004267c2  push    rsi
0x1004267c3  push    rdi
0x1004267c4  push    r14
0x1004267c6  sub     rsp, 40h
0x1004267ca  mov     rsi, r8
0x1004267cd  mov     edi, edx
0x1004267cf  mov     r14, rcx
0x1004267d2  test    edx, edx
0x1004267d4  jnz     short loc_1004267E5
0x1004267d6  cmp     cs:dword_100450C54, edx
0x1004267dc  jg      short loc_1004267E5
0x1004267de  xor     eax, eax
0x1004267e0  jmp     loc_1004268D3
0x1004267e5  lea     eax, [rdx-1]
0x1004267e8  cmp     eax, 1
0x1004267eb  ja      short loc_100426832
0x1004267ed  mov     rax, cs:_pRawDllMain
0x1004267f4  test    rax, rax
0x1004267f7  jnz     short loc_100426803
0x1004267f9  mov     [rsp+58h+var_28], 1
0x100426801  jmp     short loc_100426817
0x100426803  call    cs:__guard_dispatch_icall_fptr
0x100426809  mov     ebx, eax
0x10042680b  mov     [rsp+58h+var_28], eax
0x10042680f  test    eax, eax
0x100426811  jz      loc_1004268C9
0x100426817  mov     r8, rsi
0x10042681a  mov     edx, edi
0x10042681c  mov     rcx, r14
0x10042681f  call    dllmain_crt_dispatch
0x100426824  mov     ebx, eax
0x100426826  mov     [rsp+58h+var_28], eax
0x10042682a  test    eax, eax
0x10042682c  jz      loc_1004268C9
0x100426832  mov     r8, rsi; lpvReserved
0x100426835  mov     edx, edi; fdwReason
0x100426837  mov     rcx, r14; hinstDLL
0x10042683a  call    DllMain
0x10042683f  mov     ebx, eax
0x100426841  mov     [rsp+58h+var_28], eax
0x100426845  cmp     edi, 1
0x100426848  jnz     short loc_100426880
0x10042684a  test    eax, eax
0x10042684c  jnz     short loc_100426880
0x10042684e  mov     r8, rsi; lpvReserved
0x100426851  xor     edx, edx; fdwReason
0x100426853  mov     rcx, r14; hinstDLL
0x100426856  call    DllMain
0x10042685b  test    rsi, rsi
0x10042685e  setnz   cl
0x100426861  call    dllmain_crt_process_detach
0x100426866  mov     rax, cs:_pRawDllMain
0x10042686d  test    rax, rax
0x100426870  jz      short loc_100426880
0x100426872  mov     r8, rsi
0x100426875  xor     edx, edx
0x100426877  mov     rcx, r14
0x10042687a  call    cs:__guard_dispatch_icall_fptr
0x100426880  test    edi, edi
0x100426882  jz      short loc_100426889
0x100426884  cmp     edi, 3
0x100426887  jnz     short loc_1004268C9
0x100426889  mov     r8, rsi
0x10042688c  mov     edx, edi
0x10042688e  mov     rcx, r14
0x100426891  call    dllmain_crt_dispatch
0x100426896  mov     ebx, eax
0x100426898  mov     [rsp+58h+var_28], eax
0x10042689c  test    eax, eax
0x10042689e  jz      short loc_1004268C9
0x1004268a0  mov     rax, cs:_pRawDllMain
0x1004268a7  test    rax, rax
0x1004268aa  jnz     short loc_1004268B5
0x1004268ac  lea     ebx, [rax+1]
0x1004268af  mov     [rsp+58h+var_28], ebx
0x1004268b3  jmp     short loc_1004268C9
0x1004268b5  mov     r8, rsi
0x1004268b8  mov     edx, edi
0x1004268ba  mov     rcx, r14
0x1004268bd  call    cs:__guard_dispatch_icall_fptr
0x1004268c3  mov     ebx, eax
0x1004268c5  mov     [rsp+58h+var_28], eax
0x1004268c9  jmp     short loc_1004268D1
0x1004268cb  xor     ebx, ebx
0x1004268cd  mov     [rsp+58h+var_28], ebx
0x1004268d1  mov     eax, ebx
0x1004268d3  mov     rbx, [rsp+58h+arg_18]
0x1004268d8  add     rsp, 40h
0x1004268dc  pop     r14
0x1004268de  pop     rdi
0x1004268df  pop     rsi
0x1004268e0  retn
0x10043a8b0  push    rbp
0x10043a8b2  sub     rsp, 30h
0x10043a8b6  mov     rbp, rdx
0x10043a8b9  mov     rax, [rcx]
0x10043a8bc  mov     edx, [rax]
0x10043a8be  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x10043a8c3  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x10043a8c7  lea     r9, dllmain_crt_dispatch; int
0x10043a8ce  mov     r8, [rbp+70h]; int
0x10043a8d2  mov     edx, [rbp+68h]; int
0x10043a8d5  mov     rcx, [rbp+60h]; int
0x10043a8d9  call    __scrt_dllmain_exception_filter
0x10043a8de  nop
0x10043a8df  add     rsp, 30h
0x10043a8e3  pop     rbp
0x10043a8e4  retn
```
