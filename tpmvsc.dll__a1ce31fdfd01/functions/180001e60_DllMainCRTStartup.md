# _DllMainCRTStartup

- ea: `0x180001e60`
- end: `0x180001e9d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001d24`
- `0x180001e60`
- `0x180002478`

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
0x180001e60  mov     [rsp+arg_0], rbx
0x180001e65  mov     [rsp+arg_8], rsi
0x180001e6a  push    rdi
0x180001e6b  sub     rsp, 20h
0x180001e6f  mov     rdi, r8
0x180001e72  mov     ebx, edx
0x180001e74  mov     rsi, rcx
0x180001e77  cmp     edx, 1
0x180001e7a  jnz     short loc_180001E81
0x180001e7c  call    __security_init_cookie
0x180001e81  mov     r8, rdi; lpvReserved
0x180001e84  mov     edx, ebx; fdwReason
0x180001e86  mov     rcx, rsi; hinstDLL
0x180001e89  mov     rbx, [rsp+28h+arg_0]
0x180001e8e  mov     rsi, [rsp+28h+arg_8]
0x180001e93  add     rsp, 20h
0x180001e97  pop     rdi
0x180001e98  jmp     dllmain_dispatch
```
