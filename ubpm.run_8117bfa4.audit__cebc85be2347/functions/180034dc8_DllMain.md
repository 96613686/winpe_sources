# DllMain

- ea: `0x180034dc8`
- end: `0x180034e00`
- name: `DllMain`
- size: `56`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180033ae4`

## callees

- `0x180034dc8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180034ddc`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180034ddc`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      g_hUbpmModule = (__int64)hinstDLL;
      DisableThreadLibraryCalls(hinstDLL);
    }
  }
  else
  {
    g_hUbpmModule = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180034dc8  sub     rsp, 28h
0x180034dcc  test    edx, edx
0x180034dce  jz      short loc_180034DEA
0x180034dd0  cmp     edx, 1
0x180034dd3  jnz     short loc_180034DF5
0x180034dd5  mov     cs:g_hUbpmModule, rcx
0x180034ddc  call    cs:__imp_DisableThreadLibraryCalls
0x180034de3  nop     dword ptr [rax+rax+00h]
0x180034de8  jmp     short loc_180034DF5
0x180034dea  mov     cs:g_hUbpmModule, 0
0x180034df5  mov     eax, 1
0x180034dfa  add     rsp, 28h
0x180034dfe  retn
```
