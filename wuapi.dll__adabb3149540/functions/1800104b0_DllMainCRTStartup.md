# _DllMainCRTStartup

- ea: `0x1800104b0`
- end: `0x1800104ed`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001037c`
- `0x1800104b0`
- `0x180010b1c`

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
0x1800104b0  mov     [rsp+arg_0], rbx
0x1800104b5  mov     [rsp+arg_8], rsi
0x1800104ba  push    rdi
0x1800104bb  sub     rsp, 20h
0x1800104bf  mov     rdi, r8
0x1800104c2  mov     ebx, edx
0x1800104c4  mov     rsi, rcx
0x1800104c7  cmp     edx, 1
0x1800104ca  jnz     short loc_1800104D1
0x1800104cc  call    __security_init_cookie
0x1800104d1  mov     r8, rdi; lpvReserved
0x1800104d4  mov     edx, ebx; fdwReason
0x1800104d6  mov     rcx, rsi; hinstDLL
0x1800104d9  mov     rbx, [rsp+28h+arg_0]
0x1800104de  mov     rsi, [rsp+28h+arg_8]
0x1800104e3  add     rsp, 20h
0x1800104e7  pop     rdi
0x1800104e8  jmp     dllmain_dispatch
```
