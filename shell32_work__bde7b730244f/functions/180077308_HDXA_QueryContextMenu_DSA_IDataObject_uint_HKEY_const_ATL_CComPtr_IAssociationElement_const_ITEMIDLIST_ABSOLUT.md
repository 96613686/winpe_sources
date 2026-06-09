# HDXA_QueryContextMenu(_DSA *,IDataObject *,uint,HKEY__ * * const,ATL::CComPtr<IAssociationElement> * const,_ITEMIDLIST_ABSOLUTE const *,_QCMINFO *,uint,_DCA *,uint * const,IUnknown *,_DCA *)

- ea: `0x180077308`
- end: `0x180077996`
- name: `?HDXA_QueryContextMenu@@YAIPEAU_DSA@@PEAUIDataObject@@IQEAPEAUHKEY__@@QEAV?$CComPtr@UIAssociationElement@@@ATL@@PEBU_ITEMIDLIST_ABSOLUTE@@PEAU_QCMINFO@@IPEAU_DCA@@QEAIPEAUIUnknown@@6@Z`
- size: `1678`
- prototype: `__int64 __usercall@<rax>(HDSA hdsa@<rcx>, __int64, __int64, __int64, int, HDSA, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `21`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005a000`
- `0x180075e58`
- `0x180076824`
- `0x1802e72bc`

## callees

- `0x18000f05c`
- `0x18003eab0`
- `0x1800426e8`
- `0x180043380`
- `0x18006b4d0`
- `0x180077308`
- `0x1800780b4`
- `0x1800ad5e0`
- `0x1800c386c`
- `0x1800f188c`
- `0x1800f3ab0`
- `0x180100ce4`
- `0x18011c20c`
- `0x1801266d0`
- `0x18018ce04`
- `0x18018ce7c`
- `0x1801a83d0`
- `0x180233280`
- `0x1802645f4`
- `0x1802646ec`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800774f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800775a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007763e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180077667`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800777bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800777f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800774f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800775a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007763e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180077667`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800777bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800777f1`
- `USER32!GetMenuItemID` at `0x1800777a2`
- `USER32!GetMenuItemID` at `0x1800777a2`
- `USER32!GetMenuDefaultItem` at `0x1800778c2`
- `USER32!GetMenuDefaultItem` at `0x180077906`
- `USER32!GetMenuDefaultItem` at `0x1800778c2`
- `USER32!GetMenuDefaultItem` at `0x180077906`
- `USER32!GetMenuItemCount` at `0x1800777b4`
- `USER32!GetMenuItemCount` at `0x1800778e7`
- `USER32!GetMenuItemCount` at `0x1800777b4`
- `USER32!GetMenuItemCount` at `0x1800778e7`
- `SHCORE!__imp_SHGetObjectCompatFlags` at `0x1800776d2`
- `SHCORE!__imp_SHGetObjectCompatFlags` at `0x1800776d2`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHStringFromGUIDW` at `0x180077407`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHStringFromGUIDW` at `0x180077407`
- `SHLWAPI!GetMenuPosFromID` at `0x180077775`
- `SHLWAPI!GetMenuPosFromID` at `0x1800778dc`
- `SHLWAPI!GetMenuPosFromID` at `0x180077775`
- `SHLWAPI!GetMenuPosFromID` at `0x1800778dc`

## string_xrefs

- `0x18007769f`: `CLSID\%s`
- `0x180077429`: `CLSID\%s\shellex\MayChangeDefaultMenu`
- `0x18007746c`: `CLSID\%s\shellex\NoAddToRecent`

## pseudocode

```c

```
