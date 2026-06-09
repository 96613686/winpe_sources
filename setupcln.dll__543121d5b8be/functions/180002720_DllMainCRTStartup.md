# _DllMainCRTStartup

- ea: `0x180002720`
- end: `0x18000275d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002720`
- `0x180002764`
- `0x180002c74`

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
0x180002720  mov     [rsp+arg_0], rbx
0x180002725  mov     [rsp+arg_8], rsi
0x18000272a  push    rdi
0x18000272b  sub     rsp, 20h
0x18000272f  mov     rdi, r8
0x180002732  mov     ebx, edx
0x180002734  mov     rsi, rcx
0x180002737  cmp     edx, 1
0x18000273a  jnz     short loc_180002741
0x18000273c  call    __security_init_cookie
0x180002741  mov     r8, rdi
0x180002744  mov     edx, ebx; fdwReason
0x180002746  mov     rcx, rsi; hinstDLL
0x180002749  mov     rbx, [rsp+28h+arg_0]
0x18000274e  mov     rsi, [rsp+28h+arg_8]
0x180002753  add     rsp, 20h
0x180002757  pop     rdi
0x180002758  jmp     __DllMainCRTStartup
```
