# LoadWldpLibrary

- ea: `0x140006c60`
- end: `0x140006cb3`
- name: `LoadWldpLibrary`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140006c60`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140006c73`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140006c73`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006c95`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006c95`

## string_xrefs

- `0x140006c66`: `WLDP.DLL`

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
0x140006c60  sub     rsp, 28h
0x140006c64  xor     edx, edx; hFile
0x140006c66  lea     rcx, LibFileName; "WLDP.DLL"
0x140006c6d  mov     r8d, 800h; dwFlags
0x140006c73  call    cs:__imp_LoadLibraryExW
0x140006c7a  nop     dword ptr [rax+rax+00h]
0x140006c7f  mov     cs:WldpModuleHandle, rax
0x140006c86  test    rax, rax
0x140006c89  jz      short loc_140006CA8
0x140006c8b  lea     rdx, ProcName; "WldpIsAllowedEntryPoint"
0x140006c92  mov     rcx, rax; hModule
0x140006c95  call    cs:__imp_GetProcAddress
0x140006c9c  nop     dword ptr [rax+rax+00h]
0x140006ca1  mov     cs:IsAllowedEntryPoint, rax
0x140006ca8  mov     eax, 1
0x140006cad  add     rsp, 28h
0x140006cb1  retn
```
