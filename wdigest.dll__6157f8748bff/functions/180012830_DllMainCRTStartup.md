# _DllMainCRTStartup

- ea: `0x180012830`
- end: `0x18001286d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800126f4`
- `0x180012830`
- `0x180012cd0`

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
0x180012830  mov     [rsp+arg_0], rbx
0x180012835  mov     [rsp+arg_8], rsi
0x18001283a  push    rdi
0x18001283b  sub     rsp, 20h
0x18001283f  mov     rdi, r8
0x180012842  mov     ebx, edx
0x180012844  mov     rsi, rcx
0x180012847  cmp     edx, 1
0x18001284a  jnz     short loc_180012851
0x18001284c  call    __security_init_cookie
0x180012851  mov     r8, rdi; lpvReserved
0x180012854  mov     edx, ebx; fdwReason
0x180012856  mov     rcx, rsi; hinstDLL
0x180012859  mov     rbx, [rsp+28h+arg_0]
0x18001285e  mov     rsi, [rsp+28h+arg_8]
0x180012863  add     rsp, 20h
0x180012867  pop     rdi
0x180012868  jmp     dllmain_dispatch
```
