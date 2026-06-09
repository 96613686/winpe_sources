# _DllMainCRTStartup

- ea: `0x180009340`
- end: `0x18000937d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009340`
- `0x180009384`
- `0x180009944`

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
0x180009340  mov     [rsp+arg_0], rbx
0x180009345  mov     [rsp+arg_8], rsi
0x18000934a  push    rdi
0x18000934b  sub     rsp, 20h
0x18000934f  mov     rdi, r8
0x180009352  mov     ebx, edx
0x180009354  mov     rsi, rcx
0x180009357  cmp     edx, 1
0x18000935a  jnz     short loc_180009361
0x18000935c  call    __security_init_cookie
0x180009361  mov     r8, rdi
0x180009364  mov     edx, ebx; fdwReason
0x180009366  mov     rcx, rsi; hinstDLL
0x180009369  mov     rbx, [rsp+28h+arg_0]
0x18000936e  mov     rsi, [rsp+28h+arg_8]
0x180009373  add     rsp, 20h
0x180009377  pop     rdi
0x180009378  jmp     __DllMainCRTStartup
```
