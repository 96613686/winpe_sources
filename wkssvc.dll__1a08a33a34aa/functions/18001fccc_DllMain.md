# DllMain

- ea: `0x18001fccc`
- end: `0x18001fcef`
- name: `DllMain`
- size: `35`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001fa44`

## callees

- `0x18001fccc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001fcdf`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001fcdf`

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
0x18001fccc  sub     rsp, 28h
0x18001fcd0  cmp     edx, 1
0x18001fcd3  jnz     short loc_18001FCE5
0x18001fcd5  cmp     cs:_pRawDllMain, 0
0x18001fcdd  jnz     short loc_18001FCE5
0x18001fcdf  call    cs:__imp_DisableThreadLibraryCalls
0x18001fce5  mov     eax, 1
0x18001fcea  add     rsp, 28h
0x18001fcee  retn
```
