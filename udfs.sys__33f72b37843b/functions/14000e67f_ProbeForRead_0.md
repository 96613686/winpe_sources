# ProbeForRead_0

- ea: `0x14000e67f`
- end: `0x14000e686`
- name: `ProbeForRead_0`
- size: `7`
- prototype: `void __stdcall(volatile void *Address, SIZE_T Length, ULONG Alignment)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x14002fe54`
- `0x14002feb8`
- `0x14002ff18`
- `0x14002ff60`
- `0x14002ffa8`
- `0x14002ffec`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14000e67f`

## pseudocode

```c
// attributes: thunk
void __stdcall ProbeForRead_0(volatile void *Address, SIZE_T Length, ULONG Alignment)
{
  ProbeForRead(Address, Length, Alignment);
}

```

## disassembly

```asm
0x14000e67f  jmp     cs:__imp_ProbeForRead
```
