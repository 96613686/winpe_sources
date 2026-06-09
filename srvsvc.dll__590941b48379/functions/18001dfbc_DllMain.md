# DllMain

- ea: `0x18001dfbc`
- end: `0x18001dfdf`
- name: `DllMain`
- size: `35`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001dd24`

## callees

- `0x18001dfbc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001dfcf`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001dfcf`

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
0x18001dfbc  sub     rsp, 28h
0x18001dfc0  cmp     edx, 1
0x18001dfc3  jnz     short loc_18001DFD5
0x18001dfc5  cmp     cs:_pRawDllMain, 0
0x18001dfcd  jnz     short loc_18001DFD5
0x18001dfcf  call    cs:__imp_DisableThreadLibraryCalls
0x18001dfd5  mov     eax, 1
0x18001dfda  add     rsp, 28h
0x18001dfde  retn
```
