# Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)

- ea: `0x1800190ad`
- end: `0x1800190b3`
- name: `?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ`
- size: `6`
- prototype: `void __fastcall(Concurrency::details::_TaskEventLogger *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f990`

## import_xrefs

- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800190ad`

## pseudocode

```c
// attributes: thunk
void __fastcall Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(
        Concurrency::details::_TaskEventLogger *this)
{
  __imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ(this);
}

```

## disassembly

```asm
0x1800190ad  jmp     cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ
```
