# _DllMainCRTStartup

- ea: `0x180003700`
- end: `0x18000373d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003700`
- `0x180003744`
- `0x180003878`

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
0x180003700  mov     [rsp+arg_0], rbx
0x180003705  mov     [rsp+arg_8], rsi
0x18000370a  push    rdi
0x18000370b  sub     rsp, 20h
0x18000370f  mov     rdi, r8
0x180003712  mov     ebx, edx
0x180003714  mov     rsi, rcx
0x180003717  cmp     edx, 1
0x18000371a  jnz     short loc_180003721
0x18000371c  call    __security_init_cookie
0x180003721  mov     r8, rdi
0x180003724  mov     edx, ebx; fdwReason
0x180003726  mov     rcx, rsi; hinstDLL
0x180003729  mov     rbx, [rsp+28h+arg_0]
0x18000372e  mov     rsi, [rsp+28h+arg_8]
0x180003733  add     rsp, 20h
0x180003737  pop     rdi
0x180003738  jmp     __DllMainCRTStartup
```
