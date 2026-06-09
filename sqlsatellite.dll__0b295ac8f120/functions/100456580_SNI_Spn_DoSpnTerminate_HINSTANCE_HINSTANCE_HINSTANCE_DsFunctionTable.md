# SNI_Spn::DoSpnTerminate(HINSTANCE__ * *,HINSTANCE__ * *,HINSTANCE__ * *,_DsFunctionTable *)

- ea: `0x100456580`
- end: `0x100456720`
- name: `?DoSpnTerminate@SNI_Spn@@CAXPEAPEAUHINSTANCE__@@00PEAU_DsFunctionTable@@@Z`
- size: `416`
- prototype: `void __fastcall(HINSTANCE *, HINSTANCE *, HINSTANCE *, struct _DsFunctionTable *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x10042a070`
- `0x100456020`

## callees

- `0x10042c270`
- `0x10042c430`
- `0x100456580`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1004566bd`
- `KERNEL32!FreeLibrary` at `0x1004566ce`
- `KERNEL32!FreeLibrary` at `0x1004566df`
- `KERNEL32!FreeLibrary` at `0x1004566bd`
- `KERNEL32!FreeLibrary` at `0x1004566ce`
- `KERNEL32!FreeLibrary` at `0x1004566df`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100456685`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100456685`

## string_xrefs

- `0x100456600`: `sql\common\dk\sni\src\util.cpp`
- `0x1004565b0`: `sql\common\dk\sni\src\sni_spn.cpp`

## pseudocode

```c

```
