# ZwOpenFile_0

- ea: `0x14000db18`
- end: `0x14000db1f`
- name: `ZwOpenFile_0`
- size: `7`
- prototype: `NTSTATUS __stdcall(PHANDLE FileHandle, ACCESS_MASK DesiredAccess, POBJECT_ATTRIBUTES ObjectAttributes, PIO_STATUS_BLOCK IoStatusBlock, ULONG ShareAccess, ULONG OpenOptions)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x14003074c`
- `0x140030b8c`
- `0x140030e64`
- `0x14003106c`
- `0x140031550`
- `0x1400316c0`
- `0x14003195c`
- `0x140031a90`

## import_xrefs

- `ntoskrnl!ZwOpenFile` at `0x14000db18`

## pseudocode

```c
// attributes: thunk
NTSTATUS __stdcall ZwOpenFile_0(
        PHANDLE FileHandle,
        ACCESS_MASK DesiredAccess,
        POBJECT_ATTRIBUTES ObjectAttributes,
        PIO_STATUS_BLOCK IoStatusBlock,
        ULONG ShareAccess,
        ULONG OpenOptions)
{
  return ZwOpenFile(FileHandle, DesiredAccess, ObjectAttributes, IoStatusBlock, ShareAccess, OpenOptions);
}

```

## disassembly

```asm
0x14000db18  jmp     cs:__imp_ZwOpenFile
```
