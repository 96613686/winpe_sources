# mmioRenameWStub

- ea: `0x18000f790`
- end: `0x18000f797`
- name: `mmioRenameWStub`
- size: `7`
- prototype: `MMRESULT __stdcall(LPCWSTR pszFileName, LPCWSTR pszNewFileName, LPCMMIOINFO pmmioinfo, DWORD fdwRename)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-mm-misc-l1-1-0!mmioRenameW` at `0x18000f790`

## pseudocode

```c
// attributes: thunk
MMRESULT __stdcall mmioRenameWStub(LPCWSTR pszFileName, LPCWSTR pszNewFileName, LPCMMIOINFO pmmioinfo, DWORD fdwRename)
{
  return mmioRenameW(pszFileName, pszNewFileName, pmmioinfo, fdwRename);
}

```

## disassembly

```asm
0x18000f790  jmp     cs:__imp_mmioRenameW
```
