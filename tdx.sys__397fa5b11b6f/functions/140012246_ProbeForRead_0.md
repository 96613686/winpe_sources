# ProbeForRead_0

- ea: `0x140012246`
- end: `0x14001224d`
- name: `ProbeForRead_0`
- size: `7`
- prototype: `void __stdcall(volatile void *Address, SIZE_T Length, ULONG Alignment)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1400121d8`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140012246`

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
0x140012246  jmp     cs:__imp_ProbeForRead
```
