# Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)

- ea: `0x1800190b9`
- end: `0x1800190bf`
- name: `?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ`
- size: `6`
- prototype: `void __fastcall(Concurrency::details::_TaskEventLogger *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x18000f990`

## import_xrefs

- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800190b9`

## pseudocode

```c
// attributes: thunk
void __fastcall Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(
        Concurrency::details::_TaskEventLogger *this)
{
  __imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ(this);
}

```

## disassembly

```asm
0x1800190b9  jmp     cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ
```
