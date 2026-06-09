# _DllMainCRTStartup

- ea: `0x1800263d0`
- end: `0x18002640d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800263d0`
- `0x180026414`
- `0x180026884`

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
0x1800263d0  mov     [rsp+arg_0], rbx
0x1800263d5  mov     [rsp+arg_8], rsi
0x1800263da  push    rdi
0x1800263db  sub     rsp, 20h
0x1800263df  mov     rdi, r8
0x1800263e2  mov     ebx, edx
0x1800263e4  mov     rsi, rcx
0x1800263e7  cmp     edx, 1
0x1800263ea  jnz     short loc_1800263F1
0x1800263ec  call    __security_init_cookie
0x1800263f1  mov     r8, rdi
0x1800263f4  mov     edx, ebx; fdwReason
0x1800263f6  mov     rcx, rsi; hinstDLL
0x1800263f9  mov     rbx, [rsp+28h+arg_0]
0x1800263fe  mov     rsi, [rsp+28h+arg_8]
0x180026403  add     rsp, 20h
0x180026407  pop     rdi
0x180026408  jmp     __DllMainCRTStartup
```
