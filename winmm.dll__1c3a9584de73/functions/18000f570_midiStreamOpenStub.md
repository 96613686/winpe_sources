# midiStreamOpenStub

- ea: `0x18000f570`
- end: `0x18000f577`
- name: `midiStreamOpenStub`
- size: `7`
- prototype: `MMRESULT __stdcall(LPHMIDISTRM phms, LPUINT puDeviceID, DWORD cMidi, DWORD_PTR dwCallback, DWORD_PTR dwInstance, DWORD fdwOpen)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-mm-mme-l1-1-0!midiStreamOpen` at `0x18000f570`

## pseudocode

```c
// attributes: thunk
MMRESULT __stdcall midiStreamOpenStub(
        LPHMIDISTRM phms,
        LPUINT puDeviceID,
        DWORD cMidi,
        DWORD_PTR dwCallback,
        DWORD_PTR dwInstance,
        DWORD fdwOpen)
{
  return midiStreamOpen(phms, puDeviceID, cMidi, dwCallback, dwInstance, fdwOpen);
}

```

## disassembly

```asm
0x18000f570  jmp     cs:__imp_midiStreamOpen
```
