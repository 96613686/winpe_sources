# LoadWldpLibrary

- ea: `0x140006790`
- end: `0x1400067d6`
- name: `LoadWldpLibrary`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140006790`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400067a3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400067a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400067bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400067bf`

## string_xrefs

- `0x140006796`: `WLDP.DLL`

## pseudocode

```c
__int64 LoadWldpLibrary()
{
  HMODULE Library; // rax

  Library = LoadLibraryExW(L"WLDP.DLL", 0, 0x800u);
  WldpModuleHandle = (__int64)Library;
  if ( Library )
    IsAllowedEntryPoint = (__int64)GetProcAddress(Library, "WldpIsAllowedEntryPoint");
  return 1;
}

```

## disassembly

```asm
0x140006790  sub     rsp, 28h
0x140006794  xor     edx, edx; hFile
0x140006796  lea     rcx, LibFileName; "WLDP.DLL"
0x14000679d  mov     r8d, 800h; dwFlags
0x1400067a3  call    cs:__imp_LoadLibraryExW
0x1400067a9  mov     cs:WldpModuleHandle, rax
0x1400067b0  test    rax, rax
0x1400067b3  jz      short loc_1400067CC
0x1400067b5  lea     rdx, ProcName; "WldpIsAllowedEntryPoint"
0x1400067bc  mov     rcx, rax; hModule
0x1400067bf  call    cs:__imp_GetProcAddress
0x1400067c5  mov     cs:IsAllowedEntryPoint, rax
0x1400067cc  mov     eax, 1
0x1400067d1  add     rsp, 28h
0x1400067d5  retn
```
