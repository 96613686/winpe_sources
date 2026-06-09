# DllEntryPoint

- ea: `0x180001010`
- end: `0x18000102e`
- name: `DllEntryPoint`
- size: `30`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180001010`
- `0x180001038`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001019`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001019`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    sub_180001038();
  }
  return 1;
}

```

## disassembly

```asm
0x180001010  sub     rsp, 28h
0x180001014  cmp     edx, 1
0x180001017  jnz     short loc_180001024
0x180001019  call    cs:DisableThreadLibraryCalls
0x18000101f  call    sub_180001038
0x180001024  mov     eax, 1
0x180001029  add     rsp, 28h
0x18000102d  retn
```
