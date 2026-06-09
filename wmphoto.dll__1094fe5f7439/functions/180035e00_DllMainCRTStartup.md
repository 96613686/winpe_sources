# _DllMainCRTStartup

- ea: `0x180035e00`
- end: `0x180035e3d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180035cc4`
- `0x180035e00`
- `0x18003656c`

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
0x180035e00  mov     [rsp+arg_0], rbx
0x180035e05  mov     [rsp+arg_8], rsi
0x180035e0a  push    rdi
0x180035e0b  sub     rsp, 20h
0x180035e0f  mov     rdi, r8
0x180035e12  mov     ebx, edx
0x180035e14  mov     rsi, rcx
0x180035e17  cmp     edx, 1
0x180035e1a  jnz     short loc_180035E21
0x180035e1c  call    __security_init_cookie
0x180035e21  mov     r8, rdi; lpvReserved
0x180035e24  mov     edx, ebx; fdwReason
0x180035e26  mov     rcx, rsi; hinstDLL
0x180035e29  mov     rbx, [rsp+28h+arg_0]
0x180035e2e  mov     rsi, [rsp+28h+arg_8]
0x180035e33  add     rsp, 20h
0x180035e37  pop     rdi
0x180035e38  jmp     dllmain_dispatch
```
