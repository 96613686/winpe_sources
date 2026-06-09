# CVssCoordinator::DeleteExposure(ushort *,long,ushort *)

- ea: `0x14009f210`
- end: `0x14009f4a3`
- name: `?DeleteExposure@CVssCoordinator@@AEAAXPEAGJ0@Z`
- size: `659`
- prototype: `void(CVssCoordinator *__hidden this, unsigned __int16 *, int, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, reparse_path`

## callers

- `0x140036788`
- `0x14009c970`
- `0x14009f4ac`
- `0x14009f678`

## callees

- `0x1400137c0`
- `0x140013b00`
- `0x1400921dc`
- `0x14009f210`
- `0x1400cda78`
- `0x1400da2f0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteVolumeMountPointW` at `0x14009f477`
- `api-ms-win-core-file-l1-1-0!DeleteVolumeMountPointW` at `0x14009f477`
- `srvcli!NetShareGetInfo` at `0x14009f2c6`
- `srvcli!NetShareGetInfo` at `0x14009f2c6`
- `srvcli!NetShareDel` at `0x14009f3f1`
- `srvcli!NetShareDel` at `0x14009f3f1`
- `netutils!NetApiBufferFree` at `0x14009f466`
- `netutils!NetApiBufferFree` at `0x14009f466`

## string_xrefs

- `0x14009f23b`: `base\stor\vss\modules\coord\src\delete.cxx`
- `0x14009f247`: `CVssCoordinator::DeleteExposure`

## pseudocode

```c

```
