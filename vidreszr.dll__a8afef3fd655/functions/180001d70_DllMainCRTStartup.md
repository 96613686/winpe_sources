# _DllMainCRTStartup

- ea: `0x180001d70`
- end: `0x180001dad`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001c34`
- `0x180001d70`
- `0x180001de4`

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
0x180001d70  mov     [rsp+arg_0], rbx
0x180001d75  mov     [rsp+arg_8], rsi
0x180001d7a  push    rdi
0x180001d7b  sub     rsp, 20h
0x180001d7f  mov     rdi, r8
0x180001d82  mov     ebx, edx
0x180001d84  mov     rsi, rcx
0x180001d87  cmp     edx, 1
0x180001d8a  jnz     short loc_180001D91
0x180001d8c  call    __security_init_cookie
0x180001d91  mov     r8, rdi; lpvReserved
0x180001d94  mov     edx, ebx; fdwReason
0x180001d96  mov     rcx, rsi; hinstDLL
0x180001d99  mov     rbx, [rsp+28h+arg_0]
0x180001d9e  mov     rsi, [rsp+28h+arg_8]
0x180001da3  add     rsp, 20h
0x180001da7  pop     rdi
0x180001da8  jmp     dllmain_dispatch
```
