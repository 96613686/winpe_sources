# DeleteVssSnapshots(ushort const *,int,_FILETIME *)

- ea: `0x18008f118`
- end: `0x18008f46f`
- name: `?DeleteVssSnapshots@@YAJPEBGHPEAU_FILETIME@@@Z`
- size: `855`
- prototype: `__int64 __fastcall(wchar_t *String1, int, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18008ee80`

## callees

- `0x180003520`
- `0x1800083a0`
- `0x180033754`
- `0x180072e08`
- `0x180072f14`
- `0x18007d000`
- `0x18008f118`
- `0x180095fd4`
- `0x1800cf56a`
- `0x1800cf5c0`
- `0x1800d1010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18008f33d`
- `msvcrt!_wcsicmp` at `0x18008f33d`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x18008f1dc`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x18008f1dc`
- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x18008f2d2`
- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x18008f411`
- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x18008f2d2`
- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x18008f411`

## string_xrefs

- `0x18008f14a`: `DeleteVssSnapshots`

## pseudocode

```c

```
