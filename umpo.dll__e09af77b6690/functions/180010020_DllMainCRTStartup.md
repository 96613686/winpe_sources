# _DllMainCRTStartup

- ea: `0x180010020`
- end: `0x18001005d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000fee4`
- `0x180010020`
- `0x1800100c0`

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
0x180010020  mov     [rsp+arg_0], rbx
0x180010025  mov     [rsp+arg_8], rsi
0x18001002a  push    rdi
0x18001002b  sub     rsp, 20h
0x18001002f  mov     rdi, r8
0x180010032  mov     ebx, edx
0x180010034  mov     rsi, rcx
0x180010037  cmp     edx, 1
0x18001003a  jnz     short loc_180010041
0x18001003c  call    __security_init_cookie
0x180010041  mov     r8, rdi; lpvReserved
0x180010044  mov     edx, ebx; fdwReason
0x180010046  mov     rcx, rsi; hinstDLL
0x180010049  mov     rbx, [rsp+28h+arg_0]
0x18001004e  mov     rsi, [rsp+28h+arg_8]
0x180010053  add     rsp, 20h
0x180010057  pop     rdi
0x180010058  jmp     dllmain_dispatch
```
