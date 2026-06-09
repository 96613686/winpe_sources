# midiInOpenStub

- ea: `0x18000f450`
- end: `0x18000f457`
- name: `midiInOpenStub`
- size: `7`
- prototype: `MMRESULT __stdcall(LPHMIDIIN phmi, UINT uDeviceID, DWORD_PTR dwCallback, DWORD_PTR dwInstance, DWORD fdwOpen)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-mm-mme-l1-1-0!midiInOpen` at `0x18000f450`

## pseudocode

```c
// attributes: thunk
MMRESULT __stdcall midiInOpenStub(
        LPHMIDIIN phmi,
        UINT uDeviceID,
        DWORD_PTR dwCallback,
        DWORD_PTR dwInstance,
        DWORD fdwOpen)
{
  return midiInOpen(phmi, uDeviceID, dwCallback, dwInstance, fdwOpen);
}

```

## disassembly

```asm
0x18000f450  jmp     cs:__imp_midiInOpen
```
