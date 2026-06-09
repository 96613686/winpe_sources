# _DllMainCRTStartup

- ea: `0x180010a70`
- end: `0x180010aad`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001093c`
- `0x180010a70`
- `0x1800110b8`

## pseudocode

```c
BOOL __stdcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return dllmain_dispatch(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x180010a70  mov     [rsp+arg_0], rbx
0x180010a75  mov     [rsp+arg_8], rsi
0x180010a7a  push    rdi
0x180010a7b  sub     rsp, 20h
0x180010a7f  mov     rdi, r8
0x180010a82  mov     ebx, edx
0x180010a84  mov     rsi, rcx
0x180010a87  cmp     edx, 1
0x180010a8a  jnz     short loc_180010A91
0x180010a8c  call    __security_init_cookie
0x180010a91  mov     r8, rdi; lpvReserved
0x180010a94  mov     edx, ebx; fdwReason
0x180010a96  mov     rcx, rsi; hinstDLL
0x180010a99  mov     rbx, [rsp+28h+arg_0]
0x180010a9e  mov     rsi, [rsp+28h+arg_8]
0x180010aa3  add     rsp, 20h
0x180010aa7  pop     rdi
0x180010aa8  jmp     dllmain_dispatch
```
