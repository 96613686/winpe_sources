# _SetDlgIcon(HWND__ *,CArchiveItemDataObject *)

- ea: `0x180044d04`
- end: `0x180044ddd`
- name: `?_SetDlgIcon@@YAXPEAUHWND__@@PEAVCArchiveItemDataObject@@@Z`
- size: `217`
- prototype: `void __fastcall(HWND, struct IDataObject *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800448a0`

## callees

- `0x1800123c0`
- `0x180036f50`
- `0x180037958`
- `0x180044afc`
- `0x180044d04`

## import_xrefs

- `SHELL32!ExtractIconExW` at `0x180044dad`
- `SHELL32!ExtractIconExW` at `0x180044dad`
- `SHELL32!SHGetFileInfoW` at `0x180044d71`
- `SHELL32!SHGetFileInfoW` at `0x180044d71`
- `SHELL32!__imp_ILFree` at `0x180044d8e`
- `SHELL32!__imp_ILFree` at `0x180044d8e`

## string_xrefs

- `0x180044da6`: `shell32.dll`

## pseudocode

```c

```
