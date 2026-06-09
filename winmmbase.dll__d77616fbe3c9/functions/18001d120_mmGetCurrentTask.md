# mmGetCurrentTask

- ea: `0x18001d120`
- end: `0x18001d127`
- name: `mmGetCurrentTask`
- size: `7`
- prototype: `DWORD __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d120`

## pseudocode

```c
// attributes: thunk
DWORD __stdcall mmGetCurrentTask()
{
  return GetCurrentThreadId();
}

```

## disassembly

```asm
0x18001d120  jmp     cs:__imp_GetCurrentThreadId
```
