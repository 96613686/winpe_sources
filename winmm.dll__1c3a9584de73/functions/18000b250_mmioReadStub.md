# mmioReadStub

- ea: `0x18000b250`
- end: `0x18000b257`
- name: `mmioReadStub`
- size: `7`
- prototype: `LONG __stdcall(HMMIO hmmio, HPSTR pch, LONG cch)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-mm-misc-l1-1-0!mmioRead` at `0x18000b250`

## pseudocode

```c
// attributes: thunk
LONG __stdcall mmioReadStub(HMMIO hmmio, HPSTR pch, LONG cch)
{
  return mmioRead(hmmio, pch, cch);
}

```

## disassembly

```asm
0x18000b250  jmp     cs:__imp_mmioRead
```
