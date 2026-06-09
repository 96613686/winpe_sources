# _DllMainCRTStartup

- ea: `0x180001540`
- end: `0x18000157d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001404`
- `0x180001540`
- `0x1800019f4`

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
0x180001540  mov     [rsp+arg_0], rbx
0x180001545  mov     [rsp+arg_8], rsi
0x18000154a  push    rdi
0x18000154b  sub     rsp, 20h
0x18000154f  mov     rdi, r8
0x180001552  mov     ebx, edx
0x180001554  mov     rsi, rcx
0x180001557  cmp     edx, 1
0x18000155a  jnz     short loc_180001561
0x18000155c  call    __security_init_cookie
0x180001561  mov     r8, rdi; lpvReserved
0x180001564  mov     edx, ebx; fdwReason
0x180001566  mov     rcx, rsi; hinstDLL
0x180001569  mov     rbx, [rsp+28h+arg_0]
0x18000156e  mov     rsi, [rsp+28h+arg_8]
0x180001573  add     rsp, 20h
0x180001577  pop     rdi
0x180001578  jmp     dllmain_dispatch
```
