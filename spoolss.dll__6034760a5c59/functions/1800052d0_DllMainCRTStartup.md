# _DllMainCRTStartup

- ea: `0x1800052d0`
- end: `0x18000530d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180005194`
- `0x1800052d0`
- `0x18000571c`

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
0x1800052d0  mov     [rsp+arg_0], rbx
0x1800052d5  mov     [rsp+arg_8], rsi
0x1800052da  push    rdi
0x1800052db  sub     rsp, 20h
0x1800052df  mov     rdi, r8
0x1800052e2  mov     ebx, edx
0x1800052e4  mov     rsi, rcx
0x1800052e7  cmp     edx, 1
0x1800052ea  jnz     short loc_1800052F1
0x1800052ec  call    __security_init_cookie
0x1800052f1  mov     r8, rdi; lpvReserved
0x1800052f4  mov     edx, ebx; fdwReason
0x1800052f6  mov     rcx, rsi; hinstDLL
0x1800052f9  mov     rbx, [rsp+28h+arg_0]
0x1800052fe  mov     rsi, [rsp+28h+arg_8]
0x180005303  add     rsp, 20h
0x180005307  pop     rdi
0x180005308  jmp     dllmain_dispatch
```
