# SHTaskPoolQueueTask

- ea: `0x180018df5`
- end: `0x180018dfb`
- name: `SHTaskPoolQueueTask`
- size: `6`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x18000538c`
- `0x18000af20`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180018df5`

## pseudocode

```c
// attributes: thunk
__int64 SHTaskPoolQueueTask()
{
  return __imp_SHTaskPoolQueueTask();
}

```

## disassembly

```asm
0x180018df5  jmp     cs:__imp_SHTaskPoolQueueTask
```
