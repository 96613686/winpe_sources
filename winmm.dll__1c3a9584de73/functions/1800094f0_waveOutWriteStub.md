# waveOutWriteStub

- ea: `0x1800094f0`
- end: `0x1800094f7`
- name: `waveOutWriteStub`
- size: `7`
- prototype: `MMRESULT __stdcall(HWAVEOUT hwo, LPWAVEHDR pwh, UINT cbwh)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-mm-mme-l1-1-0!waveOutWrite` at `0x1800094f0`

## pseudocode

```c
// attributes: thunk
MMRESULT __stdcall waveOutWriteStub(HWAVEOUT hwo, LPWAVEHDR pwh, UINT cbwh)
{
  return waveOutWrite(hwo, pwh, cbwh);
}

```

## disassembly

```asm
0x1800094f0  jmp     cs:__imp_waveOutWrite
```
