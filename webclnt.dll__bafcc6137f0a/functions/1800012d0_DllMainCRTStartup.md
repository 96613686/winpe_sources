# _DllMainCRTStartup

- ea: `0x1800012d0`
- end: `0x18000130d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800012d0`
- `0x180001314`
- `0x180001964`

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
0x1800012d0  mov     [rsp+arg_0], rbx
0x1800012d5  mov     [rsp+arg_8], rsi
0x1800012da  push    rdi
0x1800012db  sub     rsp, 20h
0x1800012df  mov     rdi, r8
0x1800012e2  mov     ebx, edx
0x1800012e4  mov     rsi, rcx
0x1800012e7  cmp     edx, 1
0x1800012ea  jnz     short loc_1800012F1
0x1800012ec  call    __security_init_cookie
0x1800012f1  mov     r8, rdi
0x1800012f4  mov     edx, ebx; fdwReason
0x1800012f6  mov     rcx, rsi; hinstDLL
0x1800012f9  mov     rbx, [rsp+28h+arg_0]
0x1800012fe  mov     rsi, [rsp+28h+arg_8]
0x180001303  add     rsp, 20h
0x180001307  pop     rdi
0x180001308  jmp     __DllMainCRTStartup
```
