# DllMain

- ea: `0x180002ac0`
- end: `0x180002ae3`
- name: `DllMain`
- size: `35`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800023f4`

## callees

- `0x180002ac0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180002ad3`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180002ad3`

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
0x180002ac0  sub     rsp, 28h
0x180002ac4  cmp     edx, 1
0x180002ac7  jnz     short loc_180002AD9
0x180002ac9  cmp     cs:_pRawDllMain, 0
0x180002ad1  jnz     short loc_180002AD9
0x180002ad3  call    cs:__imp_DisableThreadLibraryCalls
0x180002ad9  mov     eax, 1
0x180002ade  add     rsp, 28h
0x180002ae2  retn
```
