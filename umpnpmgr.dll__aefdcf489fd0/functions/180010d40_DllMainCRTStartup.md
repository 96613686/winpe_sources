# _DllMainCRTStartup

- ea: `0x180010d40`
- end: `0x180010d7d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180010d40`
- `0x180010d84`
- `0x1800113b4`

## pseudocode

```c
BOOL __stdcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return _DllMainCRTStartup(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x180010d40  mov     [rsp+arg_0], rbx
0x180010d45  mov     [rsp+arg_8], rsi
0x180010d4a  push    rdi
0x180010d4b  sub     rsp, 20h
0x180010d4f  mov     rdi, r8
0x180010d52  mov     ebx, edx
0x180010d54  mov     rsi, rcx
0x180010d57  cmp     edx, 1
0x180010d5a  jnz     short loc_180010D61
0x180010d5c  call    __security_init_cookie
0x180010d61  mov     r8, rdi
0x180010d64  mov     edx, ebx; fdwReason
0x180010d66  mov     rcx, rsi; hinstDLL
0x180010d69  mov     rbx, [rsp+28h+arg_0]
0x180010d6e  mov     rsi, [rsp+28h+arg_8]
0x180010d73  add     rsp, 20h
0x180010d77  pop     rdi
0x180010d78  jmp     __DllMainCRTStartup
```
