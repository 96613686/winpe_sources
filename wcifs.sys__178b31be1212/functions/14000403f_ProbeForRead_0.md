# ProbeForRead_0

- ea: `0x14000403f`
- end: `0x140004046`
- name: `ProbeForRead_0`
- size: `7`
- prototype: `void __stdcall(volatile void *Address, SIZE_T Length, ULONG Alignment)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140004058`
- `0x14001439c`
- `0x140014400`
- `0x14001443c`
- `0x14001449c`
- `0x1400144e4`
- `0x14001452c`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14000403f`

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
0x14000403f  jmp     cs:__imp_ProbeForRead
```
