# _DllMainCRTStartup

- ea: `0x1800015b0`
- end: `0x1800015ed`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800015b0`
- `0x1800015f4`
- `0x1800019f4`

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
0x1800015b0  mov     [rsp+arg_0], rbx
0x1800015b5  mov     [rsp+arg_8], rsi
0x1800015ba  push    rdi
0x1800015bb  sub     rsp, 20h
0x1800015bf  mov     rdi, r8
0x1800015c2  mov     ebx, edx
0x1800015c4  mov     rsi, rcx
0x1800015c7  cmp     edx, 1
0x1800015ca  jnz     short loc_1800015D1
0x1800015cc  call    __security_init_cookie
0x1800015d1  mov     r8, rdi
0x1800015d4  mov     edx, ebx; fdwReason
0x1800015d6  mov     rcx, rsi; hinstDLL
0x1800015d9  mov     rbx, [rsp+28h+arg_0]
0x1800015de  mov     rsi, [rsp+28h+arg_8]
0x1800015e3  add     rsp, 20h
0x1800015e7  pop     rdi
0x1800015e8  jmp     __DllMainCRTStartup
```
