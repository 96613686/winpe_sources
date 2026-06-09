# ZwDeviceIoControlFile_0

- ea: `0x14000db06`
- end: `0x14000db0d`
- name: `ZwDeviceIoControlFile_0`
- size: `7`
- prototype: `NTSTATUS __stdcall(HANDLE FileHandle, HANDLE Event, PIO_APC_ROUTINE ApcRoutine, PVOID ApcContext, PIO_STATUS_BLOCK IoStatusBlock, ULONG IoControlCode, PVOID InputBuffer, ULONG InputBufferLength, PVOID OutputBuffer, ULONG OutputBufferLength)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140030b8c`
- `0x140031380`
- `0x140031550`
- `0x14003186c`
- `0x14003195c`
- `0x140031a90`
- `0x140031ba0`

## import_xrefs

- `ntoskrnl!ZwDeviceIoControlFile` at `0x14000db06`

## pseudocode

```c

```
