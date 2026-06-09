# _DllMainCRTStartup

- ea: `0x180008210`
- end: `0x18000824d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008210`
- `0x180008254`
- `0x180008584`

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
0x180008210  mov     [rsp+arg_0], rbx
0x180008215  mov     [rsp+arg_8], rsi
0x18000821a  push    rdi
0x18000821b  sub     rsp, 20h
0x18000821f  mov     rdi, r8
0x180008222  mov     ebx, edx
0x180008224  mov     rsi, rcx
0x180008227  cmp     edx, 1
0x18000822a  jnz     short loc_180008231
0x18000822c  call    __security_init_cookie
0x180008231  mov     r8, rdi
0x180008234  mov     edx, ebx; fdwReason
0x180008236  mov     rcx, rsi; hinstDLL
0x180008239  mov     rbx, [rsp+28h+arg_0]
0x18000823e  mov     rsi, [rsp+28h+arg_8]
0x180008243  add     rsp, 20h
0x180008247  pop     rdi
0x180008248  jmp     __DllMainCRTStartup
```
