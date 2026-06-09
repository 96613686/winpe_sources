# mmTaskSignalStub

- ea: `0x18000f6c0`
- end: `0x18000f6c7`
- name: `mmTaskSignalStub`
- size: `7`
- prototype: `BOOL __stdcall(DWORD h)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `WINMMBASE!mmTaskSignal` at `0x18000f6c0`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall mmTaskSignalStub(DWORD h)
{
  return mmTaskSignal(h);
}

```

## disassembly

```asm
0x18000f6c0  jmp     cs:__imp_mmTaskSignal
```
