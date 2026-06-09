# UtilMarkFileForDelete(void *,ulong)

- ea: `0x18009d104`
- end: `0x18009d1e9`
- name: `?UtilMarkFileForDelete@@YAXPEAXK@Z`
- size: `229`
- prototype: `void __fastcall(HANDLE FileHandle, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003d4f0`
- `0x180080bc0`

## callees

- `0x180053300`
- `0x18009d104`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x18009d155`
- `ntdll!NtQueryInformationFile` at `0x18009d155`
- `ntdll!NtSetInformationFile` at `0x18009d196`
- `ntdll!NtSetInformationFile` at `0x18009d1bf`
- `ntdll!NtSetInformationFile` at `0x18009d196`
- `ntdll!NtSetInformationFile` at `0x18009d1bf`

## pseudocode

```c

```
