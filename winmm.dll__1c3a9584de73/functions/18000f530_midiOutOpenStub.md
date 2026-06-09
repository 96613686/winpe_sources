# midiOutOpenStub

- ea: `0x18000f530`
- end: `0x18000f537`
- name: `midiOutOpenStub`
- size: `7`
- prototype: `MMRESULT __stdcall(LPHMIDIOUT phmo, UINT uDeviceID, DWORD_PTR dwCallback, DWORD_PTR dwInstance, DWORD fdwOpen)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-mm-mme-l1-1-0!midiOutOpen` at `0x18000f530`

## pseudocode

```c
// attributes: thunk
MMRESULT __stdcall midiOutOpenStub(
        LPHMIDIOUT phmo,
        UINT uDeviceID,
        DWORD_PTR dwCallback,
        DWORD_PTR dwInstance,
        DWORD fdwOpen)
{
  return midiOutOpen(phmo, uDeviceID, dwCallback, dwInstance, fdwOpen);
}

```

## disassembly

```asm
0x18000f530  jmp     cs:__imp_midiOutOpen
```
