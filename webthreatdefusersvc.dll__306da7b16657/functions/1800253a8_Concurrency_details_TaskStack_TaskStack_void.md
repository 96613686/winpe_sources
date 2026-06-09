# Concurrency::details::TaskStack::~TaskStack(void)

- ea: `0x1800253a8`
- end: `0x1800253ad`
- name: `j_??1TaskStack@details@Concurrency@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(Concurrency::details::TaskStack *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18002b505`
- `0x18002b55f`

## callees

- `0x1800253b4`

## pseudocode

```c
// attributes: thunk
void __fastcall Concurrency::details::TaskStack::~TaskStack(Concurrency::details::TaskStack *this)
{
  ??1TaskStack@details@Concurrency@@QEAA@XZ(this);
}

```

## disassembly

```asm
0x1800253a8  jmp     ??1TaskStack@details@Concurrency@@QEAA@XZ
```
