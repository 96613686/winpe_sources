# _DllMainCRTStartupForGS

- ea: `0x180001010`
- end: `0x18000102e`
- name: `_DllMainCRTStartupForGS`
- size: `30`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001010`
- `0x180001034`

## import_xrefs

- `KERNEL32!DisableThreadLibraryCalls` at `0x180001019`
- `KERNEL32!DisableThreadLibraryCalls` at `0x180001019`

## pseudocode

```c
BOOL __stdcall DllMainCRTStartupForGS(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    _security_init_cookie();
  }
  return 1;
}

```

## disassembly

```asm
0x180001010  sub     rsp, 28h
0x180001014  cmp     edx, 1
0x180001017  jnz     short loc_180001024
0x180001019  call    cs:__imp_DisableThreadLibraryCalls
0x18000101f  call    __security_init_cookie
0x180001024  mov     eax, 1
0x180001029  add     rsp, 28h
0x18000102d  retn
```
