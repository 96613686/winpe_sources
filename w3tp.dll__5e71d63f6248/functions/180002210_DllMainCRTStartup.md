# _DllMainCRTStartup

- ea: `0x180002210`
- end: `0x18000224d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002210`
- `0x180002254`
- `0x180002584`

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
0x180002210  mov     [rsp+arg_0], rbx
0x180002215  mov     [rsp+arg_8], rsi
0x18000221a  push    rdi
0x18000221b  sub     rsp, 20h
0x18000221f  mov     rdi, r8
0x180002222  mov     ebx, edx
0x180002224  mov     rsi, rcx
0x180002227  cmp     edx, 1
0x18000222a  jnz     short loc_180002231
0x18000222c  call    __security_init_cookie
0x180002231  mov     r8, rdi
0x180002234  mov     edx, ebx; fdwReason
0x180002236  mov     rcx, rsi; hinstDLL
0x180002239  mov     rbx, [rsp+28h+arg_0]
0x18000223e  mov     rsi, [rsp+28h+arg_8]
0x180002243  add     rsp, 20h
0x180002247  pop     rdi
0x180002248  jmp     __DllMainCRTStartup
```
