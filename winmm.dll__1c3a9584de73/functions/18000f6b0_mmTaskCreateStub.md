# mmTaskCreateStub

- ea: `0x18000f6b0`
- end: `0x18000f6b7`
- name: `mmTaskCreateStub`
- size: `7`
- prototype: `UINT __stdcall(LPTASKCALLBACK lpfn, HANDLE *lph, DWORD_PTR dwInst)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `WINMMBASE!mmTaskCreate` at `0x18000f6b0`

## pseudocode

```c
// attributes: thunk
UINT __stdcall mmTaskCreateStub(LPTASKCALLBACK lpfn, HANDLE *lph, DWORD_PTR dwInst)
{
  return mmTaskCreate(lpfn, lph, dwInst);
}

```

## disassembly

```asm
0x18000f6b0  jmp     cs:__imp_mmTaskCreate
```
