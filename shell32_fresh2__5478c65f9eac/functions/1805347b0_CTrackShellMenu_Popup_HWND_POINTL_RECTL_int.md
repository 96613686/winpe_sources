# CTrackShellMenu::Popup(HWND__ *,_POINTL *,_RECTL *,int)

- ea: `0x1805347b0`
- end: `0x180534b7d`
- name: `?Popup@CTrackShellMenu@@UEAAJPEAUHWND__@@PEAU_POINTL@@PEAU_RECTL@@H@Z`
- size: `973`
- prototype: `__int64 __usercall@<rax>(CTrackShellMenu *__hidden this@<rcx>, HWND hWnd@<rdx>, struct _POINTL *@<r8>, struct _RECTL *@<r9>, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18006271c`
- `0x180164198`
- `0x180249490`
- `0x1802494e0`
- `0x180534460`
- `0x1805345ac`
- `0x1805347b0`
- `0x180534cd0`
- `0x180535224`
- `0x1805b2010`

## import_xrefs

- `USER32!GetPropW` at `0x180534a8e`
- `USER32!GetPropW` at `0x180534a8e`
- `USER32!SetPropW` at `0x180534ac4`
- `USER32!SetPropW` at `0x180534ac4`
- `USER32!GetAncestor` at `0x180534822`
- `USER32!GetAncestor` at `0x180534822`
- `USER32!SetForegroundWindow` at `0x180534870`
- `USER32!SetForegroundWindow` at `0x180534870`
- `USER32!PostMessageW` at `0x180534a72`
- `USER32!PostMessageW` at `0x180534a72`
- `USER32!DispatchMessageW` at `0x180534a55`
- `USER32!DispatchMessageW` at `0x180534a55`
- `USER32!TranslateMessage` at `0x180534a45`
- `USER32!TranslateMessage` at `0x180534a45`
- `USER32!GetMessageW` at `0x180534a12`
- `USER32!GetMessageW` at `0x180534a12`
- `USER32!SetWindowLongPtrW` at `0x180534aab`
- `USER32!SetWindowLongPtrW` at `0x180534aab`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1805348a5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1805348df`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1805348a5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1805348df`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x180534976`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x180534b40`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x180534976`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x180534b40`
- `api-ms-win-shlwapi-ie-l1-1-0!IUnknown_Exec` at `0x180534b2e`
- `api-ms-win-shlwapi-ie-l1-1-0!IUnknown_Exec` at `0x180534b2e`

## pseudocode

```c

```
