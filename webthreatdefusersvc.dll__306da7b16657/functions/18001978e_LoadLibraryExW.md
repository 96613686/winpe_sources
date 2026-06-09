# LoadLibraryExW

- ea: `0x18001978e`
- end: `0x180019794`
- name: `LoadLibraryExW`
- size: `6`
- prototype: `HMODULE __stdcall(LPCWSTR lpLibFileName, HANDLE hFile, DWORD dwFlags)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180013194`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001978e`

## pseudocode

```c
// attributes: thunk
HMODULE __stdcall LoadLibraryExW(LPCWSTR lpLibFileName, HANDLE hFile, DWORD dwFlags)
{
  return __imp_LoadLibraryExW(lpLibFileName, hFile, dwFlags);
}

```

## disassembly

```asm
0x18001978e  jmp     cs:__imp_LoadLibraryExW
```
