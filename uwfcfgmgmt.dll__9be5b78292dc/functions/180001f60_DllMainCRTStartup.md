# _DllMainCRTStartup

- ea: `0x180001f60`
- end: `0x180001f9d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001f60`
- `0x180001fa4`
- `0x1800027c4`

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
0x180001f60  mov     [rsp+arg_0], rbx
0x180001f65  mov     [rsp+arg_8], rsi
0x180001f6a  push    rdi
0x180001f6b  sub     rsp, 20h
0x180001f6f  mov     rdi, r8
0x180001f72  mov     ebx, edx
0x180001f74  mov     rsi, rcx
0x180001f77  cmp     edx, 1
0x180001f7a  jnz     short loc_180001F81
0x180001f7c  call    __security_init_cookie
0x180001f81  mov     r8, rdi
0x180001f84  mov     edx, ebx; fdwReason
0x180001f86  mov     rcx, rsi; hinstDLL
0x180001f89  mov     rbx, [rsp+28h+arg_0]
0x180001f8e  mov     rsi, [rsp+28h+arg_8]
0x180001f93  add     rsp, 20h
0x180001f97  pop     rdi
0x180001f98  jmp     __DllMainCRTStartup
```
