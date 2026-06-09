# dllmain_dispatch

- ea: `0x1800126f4`
- end: `0x18001281b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180012830`

## callees

- `0x18000c260`
- `0x180012510`
- `0x1800126f4`
- `0x18001297c`
- `0x180038010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800453B0 <= 0 )
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
0x1800126f4  mov     rax, rsp
0x1800126f7  mov     [rax+20h], rbx
0x1800126fb  mov     [rax+18h], r8
0x1800126ff  mov     [rax+10h], edx
0x180012702  mov     [rax+8], rcx
0x180012706  push    rsi
0x180012707  push    rdi
0x180012708  push    r14
0x18001270a  sub     rsp, 40h
0x18001270e  mov     rsi, r8
0x180012711  mov     edi, edx
0x180012713  mov     r14, rcx
0x180012716  test    edx, edx
0x180012718  jnz     short loc_180012729
0x18001271a  cmp     cs:dword_1800453B0, edx
0x180012720  jg      short loc_180012729
0x180012722  xor     eax, eax
0x180012724  jmp     loc_18001280D
0x180012729  lea     eax, [rdx-1]
0x18001272c  cmp     eax, 1
0x18001272f  ja      short loc_180012770
0x180012731  mov     rax, cs:_pRawDllMain
0x180012738  test    rax, rax
0x18001273b  jnz     short loc_180012742
0x18001273d  lea     ebx, [rax+1]
0x180012740  jmp     short loc_180012749
0x180012742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012747  mov     ebx, eax
0x180012749  mov     [rsp+58h+var_28], ebx
0x18001274d  test    ebx, ebx
0x18001274f  jz      loc_180012803
0x180012755  mov     r8, rsi
0x180012758  mov     edx, edi
0x18001275a  mov     rcx, r14
0x18001275d  call    dllmain_crt_dispatch
0x180012762  mov     ebx, eax
0x180012764  mov     [rsp+58h+var_28], eax
0x180012768  test    eax, eax
0x18001276a  jz      loc_180012803
0x180012770  mov     r8, rsi; lpvReserved
0x180012773  mov     edx, edi; fdwReason
0x180012775  mov     rcx, r14; hinstDLL
0x180012778  call    DllMain
0x18001277d  mov     ebx, eax
0x18001277f  mov     [rsp+58h+var_28], eax
0x180012783  cmp     edi, 1
0x180012786  jnz     short loc_1800127BF
0x180012788  test    eax, eax
0x18001278a  jnz     short loc_1800127BF
0x18001278c  mov     r8, rsi; lpvReserved
0x18001278f  xor     edx, edx; fdwReason
0x180012791  mov     rcx, r14; hinstDLL
0x180012794  call    DllMain
0x180012799  mov     r8, rsi
0x18001279c  xor     edx, edx
0x18001279e  mov     rcx, r14
0x1800127a1  call    dllmain_crt_dispatch
0x1800127a6  mov     rax, cs:_pRawDllMain
0x1800127ad  test    rax, rax
0x1800127b0  jz      short loc_1800127BF
0x1800127b2  mov     r8, rsi
0x1800127b5  xor     edx, edx
0x1800127b7  mov     rcx, r14
0x1800127ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127bf  test    edi, edi
0x1800127c1  jz      short loc_1800127C8
0x1800127c3  cmp     edi, 3
0x1800127c6  jnz     short loc_180012803
0x1800127c8  mov     r8, rsi
0x1800127cb  mov     edx, edi
0x1800127cd  mov     rcx, r14
0x1800127d0  call    dllmain_crt_dispatch
0x1800127d5  mov     ebx, eax
0x1800127d7  mov     [rsp+58h+var_28], eax
0x1800127db  test    eax, eax
0x1800127dd  jz      short loc_180012803
0x1800127df  mov     rax, cs:_pRawDllMain
0x1800127e6  test    rax, rax
0x1800127e9  jnz     short loc_1800127F0
0x1800127eb  lea     ebx, [rax+1]
0x1800127ee  jmp     short loc_1800127FF
0x1800127f0  mov     r8, rsi
0x1800127f3  mov     edx, edi
0x1800127f5  mov     rcx, r14
0x1800127f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127fd  mov     ebx, eax
0x1800127ff  mov     [rsp+58h+var_28], ebx
0x180012803  jmp     short loc_18001280B
0x180012805  xor     ebx, ebx
0x180012807  mov     [rsp+58h+var_28], ebx
0x18001280b  mov     eax, ebx
0x18001280d  mov     rbx, [rsp+58h+arg_18]
0x180012812  add     rsp, 40h
0x180012816  pop     r14
0x180012818  pop     rdi
0x180012819  pop     rsi
0x18001281a  retn
0x1800378b2  push    rbp
0x1800378b4  sub     rsp, 30h
0x1800378b8  mov     rbp, rdx
0x1800378bb  mov     rax, [rcx]
0x1800378be  mov     edx, [rax]
0x1800378c0  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800378c5  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800378c9  lea     r9, dllmain_crt_dispatch; int
0x1800378d0  mov     r8, [rbp+70h]; int
0x1800378d4  mov     edx, [rbp+68h]; int
0x1800378d7  mov     rcx, [rbp+60h]; int
0x1800378db  call    __scrt_dllmain_exception_filter
0x1800378e0  nop
0x1800378e1  add     rsp, 30h
0x1800378e5  pop     rbp
0x1800378e6  retn
```
