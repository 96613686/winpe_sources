# _DllMainCRTStartup

- ea: `0x180002680`
- end: `0x1800026bd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002544`
- `0x180002680`
- `0x180002bb0`

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
0x180002680  mov     [rsp+arg_0], rbx
0x180002685  mov     [rsp+arg_8], rsi
0x18000268a  push    rdi
0x18000268b  sub     rsp, 20h
0x18000268f  mov     rdi, r8
0x180002692  mov     ebx, edx
0x180002694  mov     rsi, rcx
0x180002697  cmp     edx, 1
0x18000269a  jnz     short loc_1800026A1
0x18000269c  call    __security_init_cookie
0x1800026a1  mov     r8, rdi; lpvReserved
0x1800026a4  mov     edx, ebx; fdwReason
0x1800026a6  mov     rcx, rsi; hinstDLL
0x1800026a9  mov     rbx, [rsp+28h+arg_0]
0x1800026ae  mov     rsi, [rsp+28h+arg_8]
0x1800026b3  add     rsp, 20h
0x1800026b7  pop     rdi
0x1800026b8  jmp     dllmain_dispatch
```
