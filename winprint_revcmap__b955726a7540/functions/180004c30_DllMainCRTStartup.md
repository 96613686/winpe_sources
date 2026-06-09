# _DllMainCRTStartup

- ea: `0x180004c30`
- end: `0x180004c6d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180004af4`
- `0x180004c30`
- `0x180004ca4`

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
0x180004c30  mov     [rsp+arg_0], rbx
0x180004c35  mov     [rsp+arg_8], rsi
0x180004c3a  push    rdi
0x180004c3b  sub     rsp, 20h
0x180004c3f  mov     rdi, r8
0x180004c42  mov     ebx, edx
0x180004c44  mov     rsi, rcx
0x180004c47  cmp     edx, 1
0x180004c4a  jnz     short loc_180004C51
0x180004c4c  call    __security_init_cookie
0x180004c51  mov     r8, rdi; lpvReserved
0x180004c54  mov     edx, ebx; fdwReason
0x180004c56  mov     rcx, rsi; hinstDLL
0x180004c59  mov     rbx, [rsp+28h+arg_0]
0x180004c5e  mov     rsi, [rsp+28h+arg_8]
0x180004c63  add     rsp, 20h
0x180004c67  pop     rdi
0x180004c68  jmp     dllmain_dispatch
```
