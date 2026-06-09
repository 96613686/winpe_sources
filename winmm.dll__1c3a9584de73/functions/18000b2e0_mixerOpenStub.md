# mixerOpenStub

- ea: `0x18000b2e0`
- end: `0x18000b2e7`
- name: `mixerOpenStub`
- size: `7`
- prototype: `MMRESULT __stdcall(LPHMIXER phmx, UINT uMxId, DWORD_PTR dwCallback, DWORD_PTR dwInstance, DWORD fdwOpen)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-mm-mme-l1-1-0!mixerOpen` at `0x18000b2e0`

## pseudocode

```c
// attributes: thunk
MMRESULT __stdcall mixerOpenStub(LPHMIXER phmx, UINT uMxId, DWORD_PTR dwCallback, DWORD_PTR dwInstance, DWORD fdwOpen)
{
  return mixerOpen(phmx, uMxId, dwCallback, dwInstance, fdwOpen);
}

```

## disassembly

```asm
0x18000b2e0  jmp     cs:__imp_mixerOpen
```
