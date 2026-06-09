# _DllMainCRTStartup

- ea: `0x1800023b0`
- end: `0x1800023ed`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002274`
- `0x1800023b0`
- `0x1800024b0`

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
0x1800023b0  mov     [rsp+arg_0], rbx
0x1800023b5  mov     [rsp+arg_8], rsi
0x1800023ba  push    rdi
0x1800023bb  sub     rsp, 20h
0x1800023bf  mov     rdi, r8
0x1800023c2  mov     ebx, edx
0x1800023c4  mov     rsi, rcx
0x1800023c7  cmp     edx, 1
0x1800023ca  jnz     short loc_1800023D1
0x1800023cc  call    __security_init_cookie
0x1800023d1  mov     r8, rdi; lpvReserved
0x1800023d4  mov     edx, ebx; fdwReason
0x1800023d6  mov     rcx, rsi; hinstDLL
0x1800023d9  mov     rbx, [rsp+28h+arg_0]
0x1800023de  mov     rsi, [rsp+28h+arg_8]
0x1800023e3  add     rsp, 20h
0x1800023e7  pop     rdi
0x1800023e8  jmp     dllmain_dispatch
```
