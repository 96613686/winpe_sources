# _DllMainCRTStartup(x,x,x)

- ea: `0x10003bf0`
- end: `0x10003c15`
- name: `__DllMainCRTStartup@12`
- size: `37`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x10003aa8`
- `0x10003bf0`
- `0x10003cdc`

## pseudocode

```c
BOOL __stdcall _DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    __security_init_cookie();
  return dllmain_dispatch(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x10003bf0  mov     edi, edi
0x10003bf2  push    ebp
0x10003bf3  mov     ebp, esp
0x10003bf5  cmp     [ebp+fdwReason], 1
0x10003bf9  jnz     short loc_10003C00
0x10003bfb  call    ___security_init_cookie
0x10003c00  push    [ebp+lpReserved]; lpvReserved
0x10003c03  push    [ebp+fdwReason]; fdwReason
0x10003c06  push    [ebp+hinstDLL]; hinstDLL
0x10003c09  call    dllmain_dispatch
0x10003c0e  add     esp, 0Ch
0x10003c11  pop     ebp
0x10003c12  retn    0Ch
```
