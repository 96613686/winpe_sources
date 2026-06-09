# _DllMainCRTStartup

- ea: `0x1800021e0`
- end: `0x18000221d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800020a4`
- `0x1800021e0`
- `0x180002630`

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
0x1800021e0  mov     [rsp+arg_0], rbx
0x1800021e5  mov     [rsp+arg_8], rsi
0x1800021ea  push    rdi
0x1800021eb  sub     rsp, 20h
0x1800021ef  mov     rdi, r8
0x1800021f2  mov     ebx, edx
0x1800021f4  mov     rsi, rcx
0x1800021f7  cmp     edx, 1
0x1800021fa  jnz     short loc_180002201
0x1800021fc  call    __security_init_cookie
0x180002201  mov     r8, rdi; lpvReserved
0x180002204  mov     edx, ebx; fdwReason
0x180002206  mov     rcx, rsi; hinstDLL
0x180002209  mov     rbx, [rsp+28h+arg_0]
0x18000220e  mov     rsi, [rsp+28h+arg_8]
0x180002213  add     rsp, 20h
0x180002217  pop     rdi
0x180002218  jmp     dllmain_dispatch
```
