# DllMain

- ea: `0x1800047bc`
- end: `0x1800047d5`
- name: `DllMain`
- size: `25`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002474`

## callees

- `0x1800047bc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800047c5`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800047c5`

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
0x1800047bc  sub     rsp, 28h
0x1800047c0  cmp     edx, 1
0x1800047c3  jnz     short loc_1800047CB
0x1800047c5  call    cs:__imp_DisableThreadLibraryCalls
0x1800047cb  mov     eax, 1
0x1800047d0  add     rsp, 28h
0x1800047d4  retn
```
