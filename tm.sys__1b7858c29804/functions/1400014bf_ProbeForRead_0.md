# ProbeForRead_0

- ea: `0x1400014bf`
- end: `0x1400014c6`
- name: `ProbeForRead_0`
- size: `7`
- prototype: `void __stdcall(volatile void *Address, SIZE_T Length, ULONG Alignment)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1400014d4`
- `0x14000d198`
- `0x14000d1fc`
- `0x14000d238`
- `0x14000d274`
- `0x14000d2bc`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400014bf`

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
0x1400014bf  jmp     cs:__imp_ProbeForRead
```
