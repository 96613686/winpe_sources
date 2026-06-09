# _DllMainCRTStartup

- ea: `0x1800034b0`
- end: `0x1800034ed`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800034b0`
- `0x1800034f4`
- `0x180003b34`

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
0x1800034b0  mov     [rsp+arg_0], rbx
0x1800034b5  mov     [rsp+arg_8], rsi
0x1800034ba  push    rdi
0x1800034bb  sub     rsp, 20h
0x1800034bf  mov     rdi, r8
0x1800034c2  mov     ebx, edx
0x1800034c4  mov     rsi, rcx
0x1800034c7  cmp     edx, 1
0x1800034ca  jnz     short loc_1800034D1
0x1800034cc  call    __security_init_cookie
0x1800034d1  mov     r8, rdi
0x1800034d4  mov     edx, ebx; fdwReason
0x1800034d6  mov     rcx, rsi; hinstDLL
0x1800034d9  mov     rbx, [rsp+28h+arg_0]
0x1800034de  mov     rsi, [rsp+28h+arg_8]
0x1800034e3  add     rsp, 20h
0x1800034e7  pop     rdi
0x1800034e8  jmp     __DllMainCRTStartup
```
