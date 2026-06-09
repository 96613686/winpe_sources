# Concurrency::details::_TaskEventLogger::_LogCancelTask(void)

- ea: `0x180019095`
- end: `0x18001909b`
- name: `?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ`
- size: `6`
- prototype: `void __fastcall(Concurrency::details::_TaskEventLogger *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x18000d120`

## import_xrefs

- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180019095`

## pseudocode

```c
// attributes: thunk
void __fastcall Concurrency::details::_TaskEventLogger::_LogCancelTask(Concurrency::details::_TaskEventLogger *this)
{
  __imp_?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ(this);
}

```

## disassembly

```asm
0x180019095  jmp     cs:__imp_?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ
```
