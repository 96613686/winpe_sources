# BlbimgFindUsedSpaceInDiffArea(_GUID,__int64 *,ulong *)

- ea: `0x1400b9058`
- end: `0x1400b93da`
- name: `?BlbimgFindUsedSpaceInDiffArea@@YA?AW4_BLBIMG_RESULT_CODE@@U_GUID@@PEA_JPEAK@Z`
- size: `898`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1400b8514`

## callees

- `0x1400063b4`
- `0x140007ad3`
- `0x14000bb24`
- `0x140014200`
- `0x140014260`
- `0x14003c434`
- `0x1400b9058`
- `0x1400c3c80`
- `0x140134d20`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1400b91c2`
- `KERNEL32!CreateFileW` at `0x1400b91c2`
- `KERNEL32!CloseHandle` at `0x1400b9388`
- `KERNEL32!CloseHandle` at `0x1400b9388`
- `KERNEL32!GetLastError` at `0x1400b91f5`
- `KERNEL32!GetLastError` at `0x1400b928a`
- `KERNEL32!GetLastError` at `0x1400b91f5`
- `KERNEL32!GetLastError` at `0x1400b928a`
- `KERNEL32!DeviceIoControl` at `0x1400b925c`
- `KERNEL32!DeviceIoControl` at `0x1400b925c`
- `RPCRT4!UuidToStringW` at `0x1400b9102`
- `RPCRT4!UuidToStringW` at `0x1400b9102`
- `RPCRT4!RpcStringFreeW` at `0x1400b9379`
- `RPCRT4!RpcStringFreeW` at `0x1400b9379`

## string_xrefs

- `0x1400b9153`: `\\?\GLOBALROOT\Device\HarddiskVolumeShadowCopy{`

## pseudocode

```c

```
