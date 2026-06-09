# mmioWriteStub

- ea: `0x18000b840`
- end: `0x18000b847`
- name: `mmioWriteStub`
- size: `7`
- prototype: `LONG __stdcall(HMMIO hmmio, const char *pch, LONG cch)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-mm-misc-l1-1-0!mmioWrite` at `0x18000b840`

## pseudocode

```c
// attributes: thunk
LONG __stdcall mmioWriteStub(HMMIO hmmio, const char *pch, LONG cch)
{
  return mmioWrite(hmmio, pch, cch);
}

```

## disassembly

```asm
0x18000b840  jmp     cs:__imp_mmioWrite
```
