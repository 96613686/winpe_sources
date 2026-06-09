# LoadLibraryExW_0

- ea: `0x1400032f8`
- end: `0x1400032fe`
- name: `LoadLibraryExW_0`
- size: `6`
- prototype: `HMODULE __stdcall(LPCWSTR lpLibFileName, HANDLE hFile, DWORD dwFlags)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x14001e86c`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1400032f8`

## pseudocode

```c
// attributes: thunk
HMODULE __stdcall LoadLibraryExW_0(LPCWSTR lpLibFileName, HANDLE hFile, DWORD dwFlags)
{
  return LoadLibraryExW(lpLibFileName, hFile, dwFlags);
}

```

## disassembly

```asm
0x1400032f8  jmp     cs:__imp_LoadLibraryExW
```
