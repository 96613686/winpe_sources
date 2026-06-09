# _DllMainCRTStartup

- ea: `0x180003b60`
- end: `0x180003b9d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003a24`
- `0x180003b60`
- `0x180003c00`

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
0x180003b60  mov     [rsp+arg_0], rbx
0x180003b65  mov     [rsp+arg_8], rsi
0x180003b6a  push    rdi
0x180003b6b  sub     rsp, 20h
0x180003b6f  mov     rdi, r8
0x180003b72  mov     ebx, edx
0x180003b74  mov     rsi, rcx
0x180003b77  cmp     edx, 1
0x180003b7a  jnz     short loc_180003B81
0x180003b7c  call    __security_init_cookie
0x180003b81  mov     r8, rdi; lpvReserved
0x180003b84  mov     edx, ebx; fdwReason
0x180003b86  mov     rcx, rsi; hinstDLL
0x180003b89  mov     rbx, [rsp+28h+arg_0]
0x180003b8e  mov     rsi, [rsp+28h+arg_8]
0x180003b93  add     rsp, 20h
0x180003b97  pop     rdi
0x180003b98  jmp     dllmain_dispatch
```
