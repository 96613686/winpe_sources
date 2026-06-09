# AddDataObjectToZipFile(IDataObject *,uint,ushort const *,ushort const *,HWND__ *,_ITEMIDLIST const *,INewMenuClient *,int)

- ea: `0x180015218`
- end: `0x1800153bb`
- name: `?AddDataObjectToZipFile@@YAJPEAUIDataObject@@IPEBG1PEAUHWND__@@PEFBU_ITEMIDLIST@@PEAUINewMenuClient@@H@Z`
- size: `419`
- prototype: `__int64 __fastcall(struct IDataObject *, unsigned int, const unsigned __int16 *, unsigned __int16 *, HWND hWnd, struct _ITEMIDLIST *, struct INewMenuClient *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180015020`
- `0x1800450f0`

## callees

- `0x1800128d0`
- `0x180015218`
- `0x180024a24`
- `0x18002bf78`
- `0x180035394`
- `0x180036f50`
- `0x18003ef3c`
- `0x1800408fc`
- `0x180071010`

## import_xrefs

- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180015389`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180015389`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015343`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015343`
- `KERNEL32!GlobalLock` at `0x1800152bb`
- `KERNEL32!GlobalLock` at `0x1800152bb`
- `ole32!ReleaseStgMedium` at `0x180015393`
- `ole32!ReleaseStgMedium` at `0x180015393`

## pseudocode

```c

```
