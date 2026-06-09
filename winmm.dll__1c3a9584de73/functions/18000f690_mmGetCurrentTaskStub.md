# mmGetCurrentTaskStub

- ea: `0x18000f690`
- end: `0x18000f697`
- name: `mmGetCurrentTaskStub`
- size: `7`
- prototype: `DWORD __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `WINMMBASE!mmGetCurrentTask` at `0x18000f690`

## pseudocode

```c
// attributes: thunk
DWORD __stdcall mmGetCurrentTaskStub()
{
  return mmGetCurrentTask();
}

```

## disassembly

```asm
0x18000f690  jmp     cs:__imp_mmGetCurrentTask
```
