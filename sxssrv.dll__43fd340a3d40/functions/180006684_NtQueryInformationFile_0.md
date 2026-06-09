# NtQueryInformationFile_0

- ea: `0x180006684`
- end: `0x18000668a`
- name: `NtQueryInformationFile_0`
- size: `6`
- prototype: `NTSTATUS __stdcall(HANDLE FileHandle, PIO_STATUS_BLOCK IoStatusBlock, PVOID FileInformation, ULONG Length, FILE_INFORMATION_CLASS FileInformationClass)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180004020`
- `0x180006030`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x180006684`

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
0x180006684  jmp     cs:__imp_NtQueryInformationFile
```
