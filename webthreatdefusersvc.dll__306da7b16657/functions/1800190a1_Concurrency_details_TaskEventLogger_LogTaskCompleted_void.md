# Concurrency::details::_TaskEventLogger::_LogTaskCompleted(void)

- ea: `0x1800190a1`
- end: `0x1800190a7`
- name: `?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ`
- size: `6`
- prototype: `void __fastcall(Concurrency::details::_TaskEventLogger *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007368`

## import_xrefs

- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800190a1`

## pseudocode

```c
// attributes: thunk
void __fastcall Concurrency::details::_TaskEventLogger::_LogTaskCompleted(Concurrency::details::_TaskEventLogger *this)
{
  __imp_?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ(this);
}

```

## disassembly

```asm
0x1800190a1  jmp     cs:__imp_?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ
```
