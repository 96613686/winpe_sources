# DllMain

- ea: `0x18000ba1c`
- end: `0x18000ba3f`
- name: `DllMain`
- size: `35`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000b3c4`

## callees

- `0x18000ba1c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000ba2f`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000ba2f`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason == 1 && !pRawDllMain )
    DisableThreadLibraryCalls(hinstDLL);
  return 1;
}

```

## disassembly

```asm
0x18000ba1c  sub     rsp, 28h
0x18000ba20  cmp     edx, 1
0x18000ba23  jnz     short loc_18000BA35
0x18000ba25  cmp     cs:_pRawDllMain, 0
0x18000ba2d  jnz     short loc_18000BA35
0x18000ba2f  call    cs:__imp_DisableThreadLibraryCalls
0x18000ba35  mov     eax, 1
0x18000ba3a  add     rsp, 28h
0x18000ba3e  retn
```
