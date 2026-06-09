# RtlImageDirectoryEntryToData

- ea: `0x14001622a`
- end: `0x140016231`
- name: `RtlImageDirectoryEntryToData`
- size: `7`
- prototype: `PVOID __stdcall(PVOID BaseAddress, BOOLEAN MappedAsImage, USHORT Directory, PULONG Size)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140010ba0`

## import_xrefs

- `ntoskrnl!RtlImageDirectoryEntryToData` at `0x14001622a`

## pseudocode

```c
// attributes: thunk
PVOID __stdcall RtlImageDirectoryEntryToData(PVOID BaseAddress, BOOLEAN MappedAsImage, USHORT Directory, PULONG Size)
{
  return __imp_RtlImageDirectoryEntryToData(BaseAddress, MappedAsImage, Directory, Size);
}

```

## disassembly

```asm
0x14001622a  jmp     cs:__imp_RtlImageDirectoryEntryToData
```
