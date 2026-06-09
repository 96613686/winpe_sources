# _DllMainCRTStartup

- ea: `0x180001d60`
- end: `0x180001d9d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001d60`
- `0x180001da4`
- `0x180002294`

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
0x180001d60  mov     [rsp+arg_0], rbx
0x180001d65  mov     [rsp+arg_8], rsi
0x180001d6a  push    rdi
0x180001d6b  sub     rsp, 20h
0x180001d6f  mov     rdi, r8
0x180001d72  mov     ebx, edx
0x180001d74  mov     rsi, rcx
0x180001d77  cmp     edx, 1
0x180001d7a  jnz     short loc_180001D81
0x180001d7c  call    __security_init_cookie
0x180001d81  mov     r8, rdi
0x180001d84  mov     edx, ebx; fdwReason
0x180001d86  mov     rcx, rsi; hinstDLL
0x180001d89  mov     rbx, [rsp+28h+arg_0]
0x180001d8e  mov     rsi, [rsp+28h+arg_8]
0x180001d93  add     rsp, 20h
0x180001d97  pop     rdi
0x180001d98  jmp     __DllMainCRTStartup
```
