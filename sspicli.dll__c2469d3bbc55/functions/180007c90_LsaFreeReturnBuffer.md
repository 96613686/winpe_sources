# LsaFreeReturnBuffer

- ea: `0x180007c90`
- end: `0x180007d29`
- name: `LsaFreeReturnBuffer`
- size: `153`
- prototype: `NTSTATUS __stdcall(PVOID Buffer)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800069d8`
- `0x18000ab30`
- `0x18000d560`
- `0x1800197b0`
- `0x18001c0a0`
- `0x18001c380`
- `0x18001c530`

## callees

- `0x180007c90`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x180007d1e`
- `ntdll!NtDeviceIoControlFile` at `0x180007d1e`
- `ntdll!NtFreeVirtualMemory` at `0x180007ccb`
- `ntdll!NtFreeVirtualMemory` at `0x180007ccb`

## pseudocode

```c

```
