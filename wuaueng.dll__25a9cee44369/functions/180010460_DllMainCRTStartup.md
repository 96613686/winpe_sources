# _DllMainCRTStartup

- ea: `0x180010460`
- end: `0x18001049d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001032c`
- `0x180010460`
- `0x180010acc`

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
0x180010460  mov     [rsp+arg_0], rbx
0x180010465  mov     [rsp+arg_8], rsi
0x18001046a  push    rdi
0x18001046b  sub     rsp, 20h
0x18001046f  mov     rdi, r8
0x180010472  mov     ebx, edx
0x180010474  mov     rsi, rcx
0x180010477  cmp     edx, 1
0x18001047a  jnz     short loc_180010481
0x18001047c  call    __security_init_cookie
0x180010481  mov     r8, rdi; lpvReserved
0x180010484  mov     edx, ebx; fdwReason
0x180010486  mov     rcx, rsi; hinstDLL
0x180010489  mov     rbx, [rsp+28h+arg_0]
0x18001048e  mov     rsi, [rsp+28h+arg_8]
0x180010493  add     rsp, 20h
0x180010497  pop     rdi
0x180010498  jmp     dllmain_dispatch
```
