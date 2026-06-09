# DllMain

- ea: `0x180001d1c`
- end: `0x180001d35`
- name: `DllMain`
- size: `25`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001274`

## callees

- `0x180001d1c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001d25`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001d25`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason == 1 )
    DisableThreadLibraryCalls(hinstDLL);
  return 1;
}

```

## disassembly

```asm
0x180001d1c  sub     rsp, 28h
0x180001d20  cmp     edx, 1
0x180001d23  jnz     short loc_180001D2B
0x180001d25  call    cs:__imp_DisableThreadLibraryCalls
0x180001d2b  mov     eax, 1
0x180001d30  add     rsp, 28h
0x180001d34  retn
```
