# Concurrency::details::TaskStack::~TaskStack(void)

- ea: `0x180013db8`
- end: `0x180013dbd`
- name: `j_??1TaskStack@details@Concurrency@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(Concurrency::details::TaskStack *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18001b2ab`
- `0x18001b722`
- `0x18001b746`

## callees

- `0x18001647c`

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
0x180013db8  jmp     ??1TaskStack@details@Concurrency@@QEAA@XZ
```
