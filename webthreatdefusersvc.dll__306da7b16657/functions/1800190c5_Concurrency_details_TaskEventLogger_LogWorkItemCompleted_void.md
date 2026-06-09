# Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)

- ea: `0x1800190c5`
- end: `0x1800190cb`
- name: `?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ`
- size: `6`
- prototype: `void __fastcall(Concurrency::details::_TaskEventLogger *this)`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007984`
- `0x18000f990`

## import_xrefs

- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800190c5`

## pseudocode

```c
// attributes: thunk
void __fastcall Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(
        Concurrency::details::_TaskEventLogger *this)
{
  __imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ(this);
}

```

## disassembly

```asm
0x1800190c5  jmp     cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ
```
