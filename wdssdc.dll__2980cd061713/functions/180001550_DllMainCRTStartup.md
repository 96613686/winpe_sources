# _DllMainCRTStartup

- ea: `0x180001550`
- end: `0x18000158d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000141c`
- `0x180001550`
- `0x180001d28`

## pseudocode

```c
BOOL __stdcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return dllmain_dispatch(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x180001550  mov     [rsp+arg_0], rbx
0x180001555  mov     [rsp+arg_8], rsi
0x18000155a  push    rdi
0x18000155b  sub     rsp, 20h
0x18000155f  mov     rdi, r8
0x180001562  mov     ebx, edx
0x180001564  mov     rsi, rcx
0x180001567  cmp     edx, 1
0x18000156a  jnz     short loc_180001571
0x18000156c  call    __security_init_cookie
0x180001571  mov     r8, rdi; lpvReserved
0x180001574  mov     edx, ebx; fdwReason
0x180001576  mov     rcx, rsi; hinstDLL
0x180001579  mov     rbx, [rsp+28h+arg_0]
0x18000157e  mov     rsi, [rsp+28h+arg_8]
0x180001583  add     rsp, 20h
0x180001587  pop     rdi
0x180001588  jmp     dllmain_dispatch
```
