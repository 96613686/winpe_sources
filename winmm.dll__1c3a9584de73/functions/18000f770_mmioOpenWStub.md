# mmioOpenWStub

- ea: `0x18000f770`
- end: `0x18000f777`
- name: `mmioOpenWStub`
- size: `7`
- prototype: `HMMIO __stdcall(LPWSTR pszFileName, LPMMIOINFO pmmioinfo, DWORD fdwOpen)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-mm-misc-l1-1-0!mmioOpenW` at `0x18000f770`

## pseudocode

```c
// attributes: thunk
HMMIO __stdcall mmioOpenWStub(LPWSTR pszFileName, LPMMIOINFO pmmioinfo, DWORD fdwOpen)
{
  return mmioOpenW(pszFileName, pmmioinfo, fdwOpen);
}

```

## disassembly

```asm
0x18000f770  jmp     cs:__imp_mmioOpenW
```
