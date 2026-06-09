# _DllMainCRTStartup

- ea: `0x180001d20`
- end: `0x180001d5d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001d20`
- `0x180001d64`
- `0x18000207c`

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
0x180001d20  mov     [rsp+arg_0], rbx
0x180001d25  mov     [rsp+arg_8], rsi
0x180001d2a  push    rdi
0x180001d2b  sub     rsp, 20h
0x180001d2f  mov     rdi, r8
0x180001d32  mov     ebx, edx
0x180001d34  mov     rsi, rcx
0x180001d37  cmp     edx, 1
0x180001d3a  jnz     short loc_180001D41
0x180001d3c  call    __security_init_cookie
0x180001d41  mov     r8, rdi
0x180001d44  mov     edx, ebx; fdwReason
0x180001d46  mov     rcx, rsi; hinstDLL
0x180001d49  mov     rbx, [rsp+28h+arg_0]
0x180001d4e  mov     rsi, [rsp+28h+arg_8]
0x180001d53  add     rsp, 20h
0x180001d57  pop     rdi
0x180001d58  jmp     __DllMainCRTStartup
```
