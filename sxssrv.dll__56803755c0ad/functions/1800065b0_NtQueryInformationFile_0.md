# NtQueryInformationFile_0

- ea: `0x1800065b0`
- end: `0x1800065b6`
- name: `NtQueryInformationFile_0`
- size: `6`
- prototype: `NTSTATUS __stdcall(HANDLE FileHandle, PIO_STATUS_BLOCK IoStatusBlock, PVOID FileInformation, ULONG Length, FILE_INFORMATION_CLASS FileInformationClass)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180003e70`
- `0x180005f70`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x1800065b0`

## pseudocode

```c
// attributes: thunk
NTSTATUS __stdcall NtQueryInformationFile_0(
        HANDLE FileHandle,
        PIO_STATUS_BLOCK IoStatusBlock,
        PVOID FileInformation,
        ULONG Length,
        FILE_INFORMATION_CLASS FileInformationClass)
{
  return NtQueryInformationFile(FileHandle, IoStatusBlock, FileInformation, Length, FileInformationClass);
}

```

## disassembly

```asm
0x1800065b0  jmp     cs:__imp_NtQueryInformationFile
```
