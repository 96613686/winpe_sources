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

- `0x1400306fc`
- `0x140030b3c`
- `0x140030e14`
- `0x14003101c`
- `0x140031500`
- `0x140031670`
- `0x14003190c`
- `0x140031a40`

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
