# Concurrency::details::_TaskEventLogger::_LogScheduleTask(bool)

- ea: `0x180019089`
- end: `0x18001908f`
- name: `?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z`
- size: `6`
- prototype: `void __fastcall(Concurrency::details::_TaskEventLogger *this, bool)`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x1800043d8`
- `0x18000ef04`

## import_xrefs

- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x180019089`

## pseudocode

```c
// attributes: thunk
void __fastcall Concurrency::details::_TaskEventLogger::_LogScheduleTask(
        Concurrency::details::_TaskEventLogger *this,
        bool a2)
{
  __imp_?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z(this, a2);
}

```

## disassembly

```asm
0x180019089  jmp     cs:__imp_?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z
```
