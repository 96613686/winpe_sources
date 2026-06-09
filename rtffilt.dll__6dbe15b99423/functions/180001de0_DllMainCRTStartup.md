# _DllMainCRTStartup

- ea: `0x180001de0`
- end: `0x180001e1d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001ca4`
- `0x180001de0`
- `0x1800022dc`

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
0x180001de0  mov     [rsp+arg_0], rbx
0x180001de5  mov     [rsp+arg_8], rsi
0x180001dea  push    rdi
0x180001deb  sub     rsp, 20h
0x180001def  mov     rdi, r8
0x180001df2  mov     ebx, edx
0x180001df4  mov     rsi, rcx
0x180001df7  cmp     edx, 1
0x180001dfa  jnz     short loc_180001E01
0x180001dfc  call    __security_init_cookie
0x180001e01  mov     r8, rdi; lpvReserved
0x180001e04  mov     edx, ebx; fdwReason
0x180001e06  mov     rcx, rsi; hinstDLL
0x180001e09  mov     rbx, [rsp+28h+arg_0]
0x180001e0e  mov     rsi, [rsp+28h+arg_8]
0x180001e13  add     rsp, 20h
0x180001e17  pop     rdi
0x180001e18  jmp     dllmain_dispatch
```
