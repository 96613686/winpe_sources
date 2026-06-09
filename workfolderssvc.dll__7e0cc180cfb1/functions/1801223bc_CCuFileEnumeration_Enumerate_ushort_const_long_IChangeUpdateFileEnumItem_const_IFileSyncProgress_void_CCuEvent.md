# CCuFileEnumeration::Enumerate(ushort const *,long (*)(IChangeUpdateFileEnumItem const *,IFileSyncProgress *,void *,CCuEventLogger *,ISyncFileSystemInterface *),IFileSyncProgress *,void *,CCuEventLogger *)

- ea: `0x1801223bc`
- end: `0x180122834`
- name: `?Enumerate@CCuFileEnumeration@@QEBAJPEBGP6AJPEBUIChangeUpdateFileEnumItem@@PEAUIFileSyncProgress@@PEAXPEAVCCuEventLogger@@PEAUISyncFileSystemInterface@@@Z234@Z`
- size: `1144`
- prototype: `__int64 __fastcall(CCuFileEnumeration *__hidden this, const unsigned __int16 *, int (*)(const struct IChangeUpdateFileEnumItem *, struct IFileSyncProgress *, void *, struct CCuEventLogger *, struct ISyncFileSystemInterface *), struct IFileSyncProgress *, void *, struct CCuEventLogger *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x18011dce4`

## callees

- `0x180001290`
- `0x180001ad4`
- `0x180002ab0`
- `0x180007e10`
- `0x1800091ac`
- `0x18000a6ec`
- `0x180011314`
- `0x180090c60`
- `0x1800984c8`
- `0x1801223bc`
- `0x18012283c`
- `0x180123ad8`
- `0x18013e010`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x180122489`
- `KERNEL32!GetTickCount64` at `0x1801225f2`
- `KERNEL32!GetTickCount64` at `0x180122489`
- `KERNEL32!GetTickCount64` at `0x1801225f2`
- `KERNEL32!LocalFree` at `0x1801227f0`
- `KERNEL32!LocalFree` at `0x1801227f0`

## pseudocode

```c

```
