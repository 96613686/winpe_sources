# _DllMainCRTStartup

- ea: `0x180002520`
- end: `0x18000255d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800023e4`
- `0x180002520`
- `0x18000299c`

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
0x180002520  mov     [rsp+arg_0], rbx
0x180002525  mov     [rsp+arg_8], rsi
0x18000252a  push    rdi
0x18000252b  sub     rsp, 20h
0x18000252f  mov     rdi, r8
0x180002532  mov     ebx, edx
0x180002534  mov     rsi, rcx
0x180002537  cmp     edx, 1
0x18000253a  jnz     short loc_180002541
0x18000253c  call    __security_init_cookie
0x180002541  mov     r8, rdi; lpvReserved
0x180002544  mov     edx, ebx; fdwReason
0x180002546  mov     rcx, rsi; hinstDLL
0x180002549  mov     rbx, [rsp+28h+arg_0]
0x18000254e  mov     rsi, [rsp+28h+arg_8]
0x180002553  add     rsp, 20h
0x180002557  pop     rdi
0x180002558  jmp     dllmain_dispatch
```
