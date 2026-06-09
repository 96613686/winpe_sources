# DllMain

- ea: `0x180001a8c`
- end: `0x180001aa5`
- name: `DllMain`
- size: `25`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001314`

## callees

- `0x180001a8c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001a95`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001a95`

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
0x180001a8c  sub     rsp, 28h
0x180001a90  cmp     edx, 1
0x180001a93  jnz     short loc_180001A9B
0x180001a95  call    cs:__imp_DisableThreadLibraryCalls
0x180001a9b  mov     eax, 1
0x180001aa0  add     rsp, 28h
0x180001aa4  retn
```
