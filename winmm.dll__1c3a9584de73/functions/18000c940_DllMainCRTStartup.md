# _DllMainCRTStartup

- ea: `0x18000c940`
- end: `0x18000c97d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000c804`
- `0x18000c940`
- `0x18000cf00`

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
0x18000c940  mov     [rsp+arg_0], rbx
0x18000c945  mov     [rsp+arg_8], rsi
0x18000c94a  push    rdi
0x18000c94b  sub     rsp, 20h
0x18000c94f  mov     rdi, r8
0x18000c952  mov     ebx, edx
0x18000c954  mov     rsi, rcx
0x18000c957  cmp     edx, 1
0x18000c95a  jnz     short loc_18000C961
0x18000c95c  call    __security_init_cookie
0x18000c961  mov     r8, rdi; lpvReserved
0x18000c964  mov     edx, ebx; fdwReason
0x18000c966  mov     rcx, rsi; hinstDLL
0x18000c969  mov     rbx, [rsp+28h+arg_0]
0x18000c96e  mov     rsi, [rsp+28h+arg_8]
0x18000c973  add     rsp, 20h
0x18000c977  pop     rdi
0x18000c978  jmp     dllmain_dispatch
```
