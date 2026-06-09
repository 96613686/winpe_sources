# _DllMainCRTStartup

- ea: `0x180002230`
- end: `0x18000226d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002230`
- `0x180002274`
- `0x1800025b4`

## pseudocode

```c
BOOL __stdcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return _DllMainCRTStartup((PRELOAD_MANAGER *)hinstDLL, fdwReason, (__int64)lpReserved);
}

```

## disassembly

```asm
0x180002230  mov     [rsp+arg_0], rbx
0x180002235  mov     [rsp+arg_8], rsi
0x18000223a  push    rdi
0x18000223b  sub     rsp, 20h
0x18000223f  mov     rdi, r8
0x180002242  mov     ebx, edx
0x180002244  mov     rsi, rcx
0x180002247  cmp     edx, 1
0x18000224a  jnz     short loc_180002251
0x18000224c  call    __security_init_cookie
0x180002251  mov     r8, rdi
0x180002254  mov     edx, ebx
0x180002256  mov     rcx, rsi; this
0x180002259  mov     rbx, [rsp+28h+arg_0]
0x18000225e  mov     rsi, [rsp+28h+arg_8]
0x180002263  add     rsp, 20h
0x180002267  pop     rdi
0x180002268  jmp     __DllMainCRTStartup
```
