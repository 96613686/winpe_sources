# _DllMainCRTStartup

- ea: `0x1800363d0`
- end: `0x18003640d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180036294`
- `0x1800363d0`
- `0x180036b30`

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
0x1800363d0  mov     [rsp+arg_0], rbx
0x1800363d5  mov     [rsp+arg_8], rsi
0x1800363da  push    rdi
0x1800363db  sub     rsp, 20h
0x1800363df  mov     rdi, r8
0x1800363e2  mov     ebx, edx
0x1800363e4  mov     rsi, rcx
0x1800363e7  cmp     edx, 1
0x1800363ea  jnz     short loc_1800363F1
0x1800363ec  call    __security_init_cookie
0x1800363f1  mov     r8, rdi; lpvReserved
0x1800363f4  mov     edx, ebx; fdwReason
0x1800363f6  mov     rcx, rsi; hinstDLL
0x1800363f9  mov     rbx, [rsp+28h+arg_0]
0x1800363fe  mov     rsi, [rsp+28h+arg_8]
0x180036403  add     rsp, 20h
0x180036407  pop     rdi
0x180036408  jmp     dllmain_dispatch
```
