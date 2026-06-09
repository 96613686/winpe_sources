# _DllMainCRTStartup

- ea: `0x180001900`
- end: `0x18000193d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001900`
- `0x180001944`
- `0x180001d74`

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
0x180001900  mov     [rsp+arg_0], rbx
0x180001905  mov     [rsp+arg_8], rsi
0x18000190a  push    rdi
0x18000190b  sub     rsp, 20h
0x18000190f  mov     rdi, r8
0x180001912  mov     ebx, edx
0x180001914  mov     rsi, rcx
0x180001917  cmp     edx, 1
0x18000191a  jnz     short loc_180001921
0x18000191c  call    __security_init_cookie
0x180001921  mov     r8, rdi
0x180001924  mov     edx, ebx; fdwReason
0x180001926  mov     rcx, rsi; hinstDLL
0x180001929  mov     rbx, [rsp+28h+arg_0]
0x18000192e  mov     rsi, [rsp+28h+arg_8]
0x180001933  add     rsp, 20h
0x180001937  pop     rdi
0x180001938  jmp     __DllMainCRTStartup
```
