# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x18001dc60`
- end: `0x18001dc65`
- name: `j_??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_0`
- size: `5`
- prototype: `void __fastcall(RTL_SRWLOCK **this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002c0b8`
- `0x18002c0ca`

## callees

- `0x18001dd34`

## pseudocode

```c
// attributes: thunk
void __fastcall Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(
        RTL_SRWLOCK **this)
{
  ??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_0(this);
}

```

## disassembly

```asm
0x18001dc60  jmp     ??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_0
```
