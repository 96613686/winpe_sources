# CFspCloudFileSystemOperations::SetReadOnly(void *)

- ea: `0x18009ac24`
- end: `0x18009adc1`
- name: `?SetReadOnly@CFspCloudFileSystemOperations@@SAJPEAX@Z`
- size: `413`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800942b0`

## callees

- `0x180002ab0`
- `0x180007e10`
- `0x180008080`
- `0x180011314`
- `0x18009ac24`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x18009ad1e`
- `ntdll!NtQueryInformationFile` at `0x18009ad1e`
- `ntdll!NtSetInformationFile` at `0x18009ad6f`
- `ntdll!NtSetInformationFile` at `0x18009ad6f`

## string_xrefs

- `0x18009acad`: `CFspCloudFileSystemOperations::SetReadOnly`

## pseudocode

```c

```
