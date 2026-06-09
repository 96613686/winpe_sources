# _DllMainCRTStartup

- ea: `0x180005630`
- end: `0x18000566d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800054f4`
- `0x180005630`
- `0x180005a7c`

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
0x180005630  mov     [rsp+arg_0], rbx
0x180005635  mov     [rsp+arg_8], rsi
0x18000563a  push    rdi
0x18000563b  sub     rsp, 20h
0x18000563f  mov     rdi, r8
0x180005642  mov     ebx, edx
0x180005644  mov     rsi, rcx
0x180005647  cmp     edx, 1
0x18000564a  jnz     short loc_180005651
0x18000564c  call    __security_init_cookie
0x180005651  mov     r8, rdi; lpvReserved
0x180005654  mov     edx, ebx; fdwReason
0x180005656  mov     rcx, rsi; hinstDLL
0x180005659  mov     rbx, [rsp+28h+arg_0]
0x18000565e  mov     rsi, [rsp+28h+arg_8]
0x180005663  add     rsp, 20h
0x180005667  pop     rdi
0x180005668  jmp     dllmain_dispatch
```
