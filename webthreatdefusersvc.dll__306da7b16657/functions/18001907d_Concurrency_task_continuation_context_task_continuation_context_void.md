# Concurrency::task_continuation_context::task_continuation_context(void)

- ea: `0x18001907d`
- end: `0x180019083`
- name: `??0task_continuation_context@Concurrency@@AEAA@XZ`
- size: `6`
- prototype: `__int64 __fastcall(Concurrency::task_continuation_context *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x180006e34`

## import_xrefs

- `msvcp_win!??0task_continuation_context@Concurrency@@AEAA@XZ` at `0x18001907d`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Concurrency::task_continuation_context::task_continuation_context(
        Concurrency::task_continuation_context *this)
{
  return __imp_??0task_continuation_context@Concurrency@@AEAA@XZ(this);
}

```

## disassembly

```asm
0x18001907d  jmp     cs:__imp_??0task_continuation_context@Concurrency@@AEAA@XZ
```
