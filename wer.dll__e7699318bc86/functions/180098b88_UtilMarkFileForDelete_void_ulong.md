# UtilMarkFileForDelete(void *,ulong)

- ea: `0x180098b88`
- end: `0x180098c5a`
- name: `?UtilMarkFileForDelete@@YAXPEAXK@Z`
- size: `210`
- prototype: `void __fastcall(HANDLE FileHandle, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003b590`
- `0x18007d2a8`

## callees

- `0x180050db0`
- `0x180098b88`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x180098bd9`
- `ntdll!NtQueryInformationFile` at `0x180098bd9`
- `ntdll!NtSetInformationFile` at `0x180098c14`
- `ntdll!NtSetInformationFile` at `0x180098c37`
- `ntdll!NtSetInformationFile` at `0x180098c14`
- `ntdll!NtSetInformationFile` at `0x180098c37`

## pseudocode

```c

```
