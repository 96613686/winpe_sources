# DllMain

- ea: `0x18000c1d8`
- end: `0x18000c1f8`
- name: `DllMain`
- size: `32`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800015d4`

## callees

- `0x18000c1d8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000c1e8`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000c1e8`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason == 1 )
  {
    g_hInstance = hinstDLL;
    DisableThreadLibraryCalls(hinstDLL);
  }
  return 1;
}

```

## disassembly

```asm
0x18000c1d8  sub     rsp, 28h
0x18000c1dc  cmp     edx, 1
0x18000c1df  jnz     short loc_18000C1EE
0x18000c1e1  mov     cs:?g_hInstance@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hInstance
0x18000c1e8  call    cs:__imp_DisableThreadLibraryCalls
0x18000c1ee  mov     eax, 1
0x18000c1f3  add     rsp, 28h
0x18000c1f7  retn
```
