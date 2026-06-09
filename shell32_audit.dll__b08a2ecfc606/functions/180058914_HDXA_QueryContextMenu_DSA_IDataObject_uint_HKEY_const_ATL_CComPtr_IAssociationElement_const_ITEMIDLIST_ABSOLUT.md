# HDXA_QueryContextMenu(_DSA *,IDataObject *,uint,HKEY__ * * const,ATL::CComPtr<IAssociationElement> * const,_ITEMIDLIST_ABSOLUTE const *,_QCMINFO *,uint,_DCA *,uint * const,IUnknown *,_DCA *)

- ea: `0x180058914`
- end: `0x180059004`
- name: `?HDXA_QueryContextMenu@@YAIPEAU_DSA@@PEAUIDataObject@@IQEAPEAUHKEY__@@QEAV?$CComPtr@UIAssociationElement@@@ATL@@PEBU_ITEMIDLIST_ABSOLUTE@@PEAU_QCMINFO@@IPEAU_DCA@@QEAIPEAUIUnknown@@6@Z`
- size: `1776`
- prototype: `__int64 __usercall@<rax>(HDSA hdsa@<rcx>, __int64, __int64, __int64, int, HDSA, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `21`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180029f90`
- `0x1800573a8`
- `0x180057e00`
- `0x180305f68`

## callees

- `0x18000f6cc`
- `0x180022f00`
- `0x18003a3e0`
- `0x18003e1e8`
- `0x18003ef10`
- `0x180058914`
- `0x1800597b4`
- `0x180059c58`
- `0x1800a3fec`
- `0x1800f5920`
- `0x1800f8700`
- `0x180108a6c`
- `0x1801277fc`
- `0x180136a48`
- `0x18019fab4`
- `0x18019fb30`
- `0x1801bcd70`
- `0x180249490`
- `0x18027cd40`
- `0x18027ce40`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180058b0a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180058bc4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180058c69`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180058c99`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180058e0f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180058e4b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180058b0a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180058bc4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180058c69`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180058c99`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180058e0f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180058e4b`
- `USER32!GetMenuItemID` at `0x180058de8`
- `USER32!GetMenuItemID` at `0x180058de8`
- `USER32!GetMenuDefaultItem` at `0x180058f21`
- `USER32!GetMenuDefaultItem` at `0x180058f73`
- `USER32!GetMenuDefaultItem` at `0x180058f21`
- `USER32!GetMenuDefaultItem` at `0x180058f73`
- `USER32!GetMenuItemCount` at `0x180058e00`
- `USER32!GetMenuItemCount` at `0x180058f52`
- `USER32!GetMenuItemCount` at `0x180058e00`
- `USER32!GetMenuItemCount` at `0x180058f52`
- `SHCORE!__imp_SHGetObjectCompatFlags` at `0x180058d0a`
- `SHCORE!__imp_SHGetObjectCompatFlags` at `0x180058d0a`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHStringFromGUIDW` at `0x180058a10`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHStringFromGUIDW` at `0x180058a10`
- `SHLWAPI!GetMenuPosFromID` at `0x180058db5`
- `SHLWAPI!GetMenuPosFromID` at `0x180058f41`
- `SHLWAPI!GetMenuPosFromID` at `0x180058db5`
- `SHLWAPI!GetMenuPosFromID` at `0x180058f41`

## string_xrefs

- `0x180058cd7`: `CLSID\%s`
- `0x180058a38`: `CLSID\%s\shellex\MayChangeDefaultMenu`
- `0x180058a81`: `CLSID\%s\shellex\NoAddToRecent`

## pseudocode

```c

```
