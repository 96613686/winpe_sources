# GetCurrentThreadId_0

- ea: `0x140001662`
- end: `0x140001668`
- name: `GetCurrentThreadId_0`
- size: `6`
- prototype: `DWORD __stdcall()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x14000cfd4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140001662`

## pseudocode

```c
// attributes: thunk
DWORD __stdcall GetCurrentThreadId_0()
{
  return GetCurrentThreadId();
}

```

## disassembly

```asm
0x140001662  jmp     cs:__imp_GetCurrentThreadId
```
