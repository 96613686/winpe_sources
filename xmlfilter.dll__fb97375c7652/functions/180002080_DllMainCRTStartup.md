# _DllMainCRTStartup

- ea: `0x180002080`
- end: `0x1800020bd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001f44`
- `0x180002080`
- `0x180002590`

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
0x180002080  mov     [rsp+arg_0], rbx
0x180002085  mov     [rsp+arg_8], rsi
0x18000208a  push    rdi
0x18000208b  sub     rsp, 20h
0x18000208f  mov     rdi, r8
0x180002092  mov     ebx, edx
0x180002094  mov     rsi, rcx
0x180002097  cmp     edx, 1
0x18000209a  jnz     short loc_1800020A1
0x18000209c  call    __security_init_cookie
0x1800020a1  mov     r8, rdi; lpvReserved
0x1800020a4  mov     edx, ebx; fdwReason
0x1800020a6  mov     rcx, rsi; hinstDLL
0x1800020a9  mov     rbx, [rsp+28h+arg_0]
0x1800020ae  mov     rsi, [rsp+28h+arg_8]
0x1800020b3  add     rsp, 20h
0x1800020b7  pop     rdi
0x1800020b8  jmp     dllmain_dispatch
```
