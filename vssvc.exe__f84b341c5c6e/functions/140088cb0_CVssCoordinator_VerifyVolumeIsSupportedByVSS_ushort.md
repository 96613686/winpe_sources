# CVssCoordinator::VerifyVolumeIsSupportedByVSS(ushort *)

- ea: `0x140088cb0`
- end: `0x140089153`
- name: `?VerifyVolumeIsSupportedByVSS@CVssCoordinator@@AEAAXPEAG@Z`
- size: `1187`
- prototype: `void(CVssCoordinator *__hidden this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, loader_planting`

## callers

- `0x1400844c0`
- `0x140085360`

## callees

- `0x1400137c0`
- `0x140013b00`
- `0x140015e38`
- `0x140025b00`
- `0x140028b48`
- `0x14003c174`
- `0x140049ec4`
- `0x14004ce80`
- `0x140088cb0`
- `0x140091560`
- `0x1400916f0`
- `0x1400919a0`
- `0x1400921dc`

## import_xrefs

- `ntdll!NtQueryVolumeInformationFile` at `0x140088f6c`
- `ntdll!NtQueryVolumeInformationFile` at `0x140088f6c`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x140088f7f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x140088f7f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140088e4f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140088e4f`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x140088d4d`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x140088d4d`

## string_xrefs

- `0x140088ead`: `Error calling CreateFile on volume '%s'`
- `0x140089081`: `Volume '%s' not found or not ready : NTSTATUS 0x%08lx`
- `0x1400890f6`: `Encountered a read-only volume (%s), not supported by VSS`

## pseudocode

```c

```
