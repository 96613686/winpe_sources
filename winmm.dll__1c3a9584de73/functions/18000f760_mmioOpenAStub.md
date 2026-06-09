# mmioOpenAStub

- ea: `0x18000f760`
- end: `0x18000f767`
- name: `mmioOpenAStub`
- size: `7`
- prototype: `HMMIO __stdcall(LPSTR pszFileName, LPMMIOINFO pmmioinfo, DWORD fdwOpen)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-mm-misc-l1-1-0!mmioOpenA` at `0x18000f760`

## pseudocode

```c
// attributes: thunk
HMMIO __stdcall mmioOpenAStub(LPSTR pszFileName, LPMMIOINFO pmmioinfo, DWORD fdwOpen)
{
  return mmioOpenA(pszFileName, pmmioinfo, fdwOpen);
}

```

## disassembly

```asm
0x18000f760  jmp     cs:__imp_mmioOpenA
```
