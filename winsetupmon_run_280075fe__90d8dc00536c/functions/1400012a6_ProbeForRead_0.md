# ProbeForRead_0

- ea: `0x1400012a6`
- end: `0x1400012ad`
- name: `ProbeForRead_0`
- size: `7`
- prototype: `void __stdcall(volatile void *Address, SIZE_T Length, ULONG Alignment)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140001220`
- `0x14001e008`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400012a6`

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
0x1400012a6  jmp     cs:__imp_ProbeForRead
```
