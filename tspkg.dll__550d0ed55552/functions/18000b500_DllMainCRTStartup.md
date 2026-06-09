# _DllMainCRTStartup

- ea: `0x18000b500`
- end: `0x18000b53d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000b3c4`
- `0x18000b500`
- `0x18000b960`

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
0x18000b500  mov     [rsp+arg_0], rbx
0x18000b505  mov     [rsp+arg_8], rsi
0x18000b50a  push    rdi
0x18000b50b  sub     rsp, 20h
0x18000b50f  mov     rdi, r8
0x18000b512  mov     ebx, edx
0x18000b514  mov     rsi, rcx
0x18000b517  cmp     edx, 1
0x18000b51a  jnz     short loc_18000B521
0x18000b51c  call    __security_init_cookie
0x18000b521  mov     r8, rdi; lpvReserved
0x18000b524  mov     edx, ebx; fdwReason
0x18000b526  mov     rcx, rsi; hinstDLL
0x18000b529  mov     rbx, [rsp+28h+arg_0]
0x18000b52e  mov     rsi, [rsp+28h+arg_8]
0x18000b533  add     rsp, 20h
0x18000b537  pop     rdi
0x18000b538  jmp     dllmain_dispatch
```
