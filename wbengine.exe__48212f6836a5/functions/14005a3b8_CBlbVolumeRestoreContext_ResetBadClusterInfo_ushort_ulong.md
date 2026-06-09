# CBlbVolumeRestoreContext::ResetBadClusterInfo(ushort *,ulong)

- ea: `0x14005a3b8`
- end: `0x14005a623`
- name: `?ResetBadClusterInfo@CBlbVolumeRestoreContext@@AEAAJPEAGK@Z`
- size: `619`
- prototype: `__int64 __fastcall(CBlbVolumeRestoreContext *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x14005a62c`

## callees

- `0x140006ca8`
- `0x14000bb4c`
- `0x14003c54c`
- `0x14003c9cc`
- `0x14005a3b8`
- `0x14005b944`
- `0x140092184`
- `0x140137010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x14005a54b`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14005a581`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14005a54b`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14005a581`
- `KERNEL32!FreeLibrary` at `0x14005a4aa`
- `KERNEL32!FreeLibrary` at `0x14005a607`
- `KERNEL32!FreeLibrary` at `0x14005a4aa`
- `KERNEL32!FreeLibrary` at `0x14005a607`
- `KERNEL32!GetProcAddress` at `0x14005a499`
- `KERNEL32!GetProcAddress` at `0x14005a499`
- `KERNEL32!GetLastError` at `0x14005a433`
- `KERNEL32!GetLastError` at `0x14005a4b0`
- `KERNEL32!GetLastError` at `0x14005a433`
- `KERNEL32!GetLastError` at `0x14005a4b0`

## string_xrefs

- `0x14005a41f`: `fmifs.dll`
- `0x14005a410`: `base\stor\blb\engine\service\restore.cpp`

## pseudocode

```c

```
