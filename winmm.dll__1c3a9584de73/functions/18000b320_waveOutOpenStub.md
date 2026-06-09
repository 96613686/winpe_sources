# waveOutOpenStub

- ea: `0x18000b320`
- end: `0x18000b327`
- name: `waveOutOpenStub`
- size: `7`
- prototype: `MMRESULT __stdcall(LPHWAVEOUT phwo, UINT uDeviceID, LPCWAVEFORMATEX pwfx, DWORD_PTR dwCallback, DWORD_PTR dwInstance, DWORD fdwOpen)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-mm-mme-l1-1-0!waveOutOpen` at `0x18000b320`

## pseudocode

```c
// attributes: thunk
MMRESULT __stdcall waveOutOpenStub(
        LPHWAVEOUT phwo,
        UINT uDeviceID,
        LPCWAVEFORMATEX pwfx,
        DWORD_PTR dwCallback,
        DWORD_PTR dwInstance,
        DWORD fdwOpen)
{
  return waveOutOpen(phwo, uDeviceID, pwfx, dwCallback, dwInstance, fdwOpen);
}

```

## disassembly

```asm
0x18000b320  jmp     cs:__imp_waveOutOpen
```
