# _DllMainCRTStartup

- ea: `0x18001e250`
- end: `0x18001e28d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001e250`
- `0x18001e294`
- `0x18001e9bc`

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
0x18001e250  mov     [rsp+arg_0], rbx
0x18001e255  mov     [rsp+arg_8], rsi
0x18001e25a  push    rdi
0x18001e25b  sub     rsp, 20h
0x18001e25f  mov     rdi, r8
0x18001e262  mov     ebx, edx
0x18001e264  mov     rsi, rcx
0x18001e267  cmp     edx, 1
0x18001e26a  jnz     short loc_18001E271
0x18001e26c  call    __security_init_cookie
0x18001e271  mov     r8, rdi
0x18001e274  mov     edx, ebx; fdwReason
0x18001e276  mov     rcx, rsi; hinstDLL
0x18001e279  mov     rbx, [rsp+28h+arg_0]
0x18001e27e  mov     rsi, [rsp+28h+arg_8]
0x18001e283  add     rsp, 20h
0x18001e287  pop     rdi
0x18001e288  jmp     __DllMainCRTStartup
```
