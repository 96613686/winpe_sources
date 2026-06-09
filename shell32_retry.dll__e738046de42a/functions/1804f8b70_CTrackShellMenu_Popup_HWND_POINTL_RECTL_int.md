# CTrackShellMenu::Popup(HWND__ *,_POINTL *,_RECTL *,int)

- ea: `0x1804f8b70`
- end: `0x1804f8f7d`
- name: `?Popup@CTrackShellMenu@@UEAAJPEAUHWND__@@PEAU_POINTL@@PEAU_RECTL@@H@Z`
- size: `1037`
- prototype: `__int64 __usercall@<rax>(CTrackShellMenu *__hidden this@<rcx>, HWND@<rdx>, struct _POINTL *@<r8>, struct _RECTL *@<r9>, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1800221ec`
- `0x1800257d0`
- `0x180154f6c`
- `0x180233280`
- `0x1802332d0`
- `0x1804f88c0`
- `0x1804f8b70`
- `0x1804f90d0`
- `0x180571010`

## import_xrefs

- `USER32!GetWindowThreadProcessId` at `0x1804f8c1e`
- `USER32!GetWindowThreadProcessId` at `0x1804f8c31`
- `USER32!GetWindowThreadProcessId` at `0x1804f8c1e`
- `USER32!GetWindowThreadProcessId` at `0x1804f8c31`
- `USER32!GetPropW` at `0x1804f8d85`
- `USER32!GetPropW` at `0x1804f8ea9`
- `USER32!GetPropW` at `0x1804f8d85`
- `USER32!GetPropW` at `0x1804f8ea9`
- `USER32!SetPropW` at `0x1804f8dca`
- `USER32!SetPropW` at `0x1804f8ed3`
- `USER32!SetPropW` at `0x1804f8dca`
- `USER32!SetPropW` at `0x1804f8ed3`
- `USER32!GetAncestor` at `0x1804f8be4`
- `USER32!GetAncestor` at `0x1804f8c10`
- `USER32!GetAncestor` at `0x1804f8c47`
- `USER32!GetAncestor` at `0x1804f8be4`
- `USER32!GetAncestor` at `0x1804f8c10`
- `USER32!GetAncestor` at `0x1804f8c47`
- `USER32!SetForegroundWindow` at `0x1804f8c6c`
- `USER32!SetForegroundWindow` at `0x1804f8c6c`
- `USER32!PostMessageW` at `0x1804f8e93`
- `USER32!PostMessageW` at `0x1804f8e93`
- `USER32!DispatchMessageW` at `0x1804f8e7c`
- `USER32!DispatchMessageW` at `0x1804f8e7c`
- `USER32!TranslateMessage` at `0x1804f8e72`
- `USER32!TranslateMessage` at `0x1804f8e72`
- `USER32!GetMessageW` at `0x1804f8e48`
- `USER32!GetMessageW` at `0x1804f8e48`
- `USER32!GetWindowLongPtrW` at `0x1804f8db0`
- `USER32!GetWindowLongPtrW` at `0x1804f8db0`
- `USER32!SetWindowLongPtrW` at `0x1804f8ddf`
- `USER32!SetWindowLongPtrW` at `0x1804f8ec0`
- `USER32!SetWindowLongPtrW` at `0x1804f8ddf`
- `USER32!SetWindowLongPtrW` at `0x1804f8ec0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1804f8c93`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1804f8cc4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1804f8c93`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1804f8cc4`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x1804f8d51`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x1804f8f45`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x1804f8d51`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x1804f8f45`
- `api-ms-win-shlwapi-ie-l1-1-0!IUnknown_Exec` at `0x1804f8f39`
- `api-ms-win-shlwapi-ie-l1-1-0!IUnknown_Exec` at `0x1804f8f39`

## pseudocode

```c

```
