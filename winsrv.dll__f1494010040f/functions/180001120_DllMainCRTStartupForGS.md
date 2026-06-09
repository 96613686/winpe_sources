# _DllMainCRTStartupForGS

- ea: `0x180001120`
- end: `0x18000113e`
- name: `_DllMainCRTStartupForGS`
- size: `30`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001120`
- `0x180001148`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001129`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001129`

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
0x180001120  sub     rsp, 28h
0x180001124  cmp     edx, 1
0x180001127  jnz     short loc_180001134
0x180001129  call    cs:__imp_DisableThreadLibraryCalls
0x18000112f  call    __security_init_cookie
0x180001134  mov     eax, 1
0x180001139  add     rsp, 28h
0x18000113d  retn
```
