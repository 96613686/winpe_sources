# mmioRenameAStub

- ea: `0x18000f780`
- end: `0x18000f787`
- name: `mmioRenameAStub`
- size: `7`
- prototype: `MMRESULT __stdcall(LPCSTR pszFileName, LPCSTR pszNewFileName, LPCMMIOINFO pmmioinfo, DWORD fdwRename)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-mm-misc-l1-1-0!mmioRenameA` at `0x18000f780`

## pseudocode

```c
// attributes: thunk
MMRESULT __stdcall mmioRenameAStub(LPCSTR pszFileName, LPCSTR pszNewFileName, LPCMMIOINFO pmmioinfo, DWORD fdwRename)
{
  return mmioRenameA(pszFileName, pszNewFileName, pmmioinfo, fdwRename);
}

```

## disassembly

```asm
0x18000f780  jmp     cs:__imp_mmioRenameA
```
