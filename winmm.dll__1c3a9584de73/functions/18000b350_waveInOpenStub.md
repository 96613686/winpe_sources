# waveInOpenStub

- ea: `0x18000b350`
- end: `0x18000b357`
- name: `waveInOpenStub`
- size: `7`
- prototype: `MMRESULT __stdcall(LPHWAVEIN phwi, UINT uDeviceID, LPCWAVEFORMATEX pwfx, DWORD_PTR dwCallback, DWORD_PTR dwInstance, DWORD fdwOpen)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-mm-mme-l1-1-0!waveInOpen` at `0x18000b350`

## pseudocode

```c
// attributes: thunk
MMRESULT __stdcall waveInOpenStub(
        LPHWAVEIN phwi,
        UINT uDeviceID,
        LPCWAVEFORMATEX pwfx,
        DWORD_PTR dwCallback,
        DWORD_PTR dwInstance,
        DWORD fdwOpen)
{
  return waveInOpen(phwi, uDeviceID, pwfx, dwCallback, dwInstance, fdwOpen);
}

```

## disassembly

```asm
0x18000b350  jmp     cs:__imp_waveInOpen
```
