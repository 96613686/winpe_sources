# mmioCreateChunkStub

- ea: `0x18000b880`
- end: `0x18000b887`
- name: `mmioCreateChunkStub`
- size: `7`
- prototype: `MMRESULT __stdcall(HMMIO hmmio, LPMMCKINFO pmmcki, UINT fuCreate)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-mm-misc-l1-1-0!mmioCreateChunk` at `0x18000b880`

## pseudocode

```c
// attributes: thunk
MMRESULT __stdcall mmioCreateChunkStub(HMMIO hmmio, LPMMCKINFO pmmcki, UINT fuCreate)
{
  return mmioCreateChunk(hmmio, pmmcki, fuCreate);
}

```

## disassembly

```asm
0x18000b880  jmp     cs:__imp_mmioCreateChunk
```
