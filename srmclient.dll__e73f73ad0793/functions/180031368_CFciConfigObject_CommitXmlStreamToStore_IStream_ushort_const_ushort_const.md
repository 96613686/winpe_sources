# CFciConfigObject::CommitXmlStreamToStore(IStream *,ushort const *,ushort const *)

- ea: `0x180031368`
- end: `0x1800315db`
- name: `?CommitXmlStreamToStore@CFciConfigObject@@SAXPEAUIStream@@PEBG1@Z`
- size: `627`
- prototype: `void __fastcall(LPSTREAM pstm, WCHAR *, WCHAR *Src)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003354c`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x1800106e0`
- `0x180031368`
- `0x18006febc`
- `0x1800700b8`
- `0x180072a80`
- `0x180073a80`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `ole32!GetHGlobalFromStream` at `0x18003146f`
- `ole32!GetHGlobalFromStream` at `0x18003146f`
- `KERNEL32!GlobalLock` at `0x180031490`
- `KERNEL32!GlobalLock` at `0x180031490`
- `KERNEL32!GlobalUnlock` at `0x1800314af`
- `KERNEL32!GlobalUnlock` at `0x1800314af`

## string_xrefs

- `0x180031393`: `base\fs\fsrm\service\globalstore\fciconfigobject.cpp`
- `0x18003139f`: `CFciConfigObject::CommitXmlStreamToStore`

## pseudocode

```c

```
