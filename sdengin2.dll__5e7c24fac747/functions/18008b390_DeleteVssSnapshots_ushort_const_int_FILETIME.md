# DeleteVssSnapshots(ushort const *,int,_FILETIME *)

- ea: `0x18008b390`
- end: `0x18008b6ca`
- name: `?DeleteVssSnapshots@@YAJPEBGHPEAU_FILETIME@@@Z`
- size: `826`
- prototype: `__int64 __fastcall(wchar_t *String1, int, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18008b108`

## callees

- `0x180003430`
- `0x180008200`
- `0x1800323f0`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180079e1c`
- `0x18008b390`
- `0x180091e04`
- `0x1800c97da`
- `0x1800c9830`
- `0x1800cb010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18008b5a9`
- `msvcrt!_wcsicmp` at `0x18008b5a9`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x18008b454`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x18008b454`
- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x18008b544`
- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x18008b673`
- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x18008b544`
- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x18008b673`

## string_xrefs

- `0x18008b3c2`: `DeleteVssSnapshots`

## pseudocode

```c

```
