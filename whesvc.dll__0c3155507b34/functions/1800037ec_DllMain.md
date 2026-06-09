# DllMain

- ea: `0x1800037ec`
- end: `0x18000380f`
- name: `DllMain`
- size: `35`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003154`

## callees

- `0x1800037ec`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800037ff`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800037ff`

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
0x1800037ec  sub     rsp, 28h
0x1800037f0  cmp     edx, 1
0x1800037f3  jnz     short loc_180003805
0x1800037f5  cmp     cs:_pRawDllMain, 0
0x1800037fd  jnz     short loc_180003805
0x1800037ff  call    cs:__imp_DisableThreadLibraryCalls
0x180003805  mov     eax, 1
0x18000380a  add     rsp, 28h
0x18000380e  retn
```
