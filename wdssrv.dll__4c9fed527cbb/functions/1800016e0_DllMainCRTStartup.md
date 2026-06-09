# _DllMainCRTStartup

- ea: `0x1800016e0`
- end: `0x18000171d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800016e0`
- `0x180001724`
- `0x180001b44`

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
0x1800016e0  mov     [rsp+arg_0], rbx
0x1800016e5  mov     [rsp+arg_8], rsi
0x1800016ea  push    rdi
0x1800016eb  sub     rsp, 20h
0x1800016ef  mov     rdi, r8
0x1800016f2  mov     ebx, edx
0x1800016f4  mov     rsi, rcx
0x1800016f7  cmp     edx, 1
0x1800016fa  jnz     short loc_180001701
0x1800016fc  call    __security_init_cookie
0x180001701  mov     r8, rdi
0x180001704  mov     edx, ebx; fdwReason
0x180001706  mov     rcx, rsi; hinstDLL
0x180001709  mov     rbx, [rsp+28h+arg_0]
0x18000170e  mov     rsi, [rsp+28h+arg_8]
0x180001713  add     rsp, 20h
0x180001717  pop     rdi
0x180001718  jmp     __DllMainCRTStartup
```
