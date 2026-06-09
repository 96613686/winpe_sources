# CDefView::WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800afc68`
- end: `0x1800b0a25`
- name: `?WndProc@CDefView@@AEAA_JPEAUHWND__@@I_K_J@Z`
- size: `3517`
- prototype: `__int64 __fastcall(CDefView *__hidden this, HWND hWnd, UINT Msg, unsigned int, LPARAM lParam)`
- caller_count: `1`
- callee_count: `55`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800afba0`

## callees

- `0x18000f34c`
- `0x18000f5a4`
- `0x18000f7c0`
- `0x18000fb9c`
- `0x18000fc40`
- `0x180010080`
- `0x18001052c`
- `0x180017aec`
- `0x180017bdc`
- `0x18002eac8`
- `0x180048590`
- `0x180053040`
- `0x18005459c`
- `0x180054f88`
- `0x180056470`
- `0x180076260`
- `0x18009f6c0`
- `0x18009f850`
- `0x18009fa5c`
- `0x1800ac89c`
- `0x1800afc68`
- `0x1800b6030`
- `0x1800b6bd0`
- `0x1800bb328`
- `0x1800bbaa4`
- `0x1800c9e7c`
- `0x1800f7f1c`
- `0x1800fa660`
- `0x18011fc5c`
- `0x18013b6f4`
- `0x18013d1d4`
- `0x18013d640`
- `0x180141550`
- `0x180146c34`
- `0x18015584c`
- `0x18015594c`
- `0x18015bc2c`
- `0x180160ab8`
- `0x1801a83d0`
- `0x1801d7780`
- `0x1801d7d50`
- `0x1801f973c`
- `0x180233280`
- `0x1802c9d68`
- `0x1802ca600`
- `0x1802cd3ac`
- `0x1802cddc0`
- `0x1802d1570`
- `0x1802d8c38`
- `0x1802d8ca8`

## import_xrefs

- `USER32!GetMessageExtraInfo` at `0x1800b0400`
- `USER32!GetMessageExtraInfo` at `0x1800b041c`
- `USER32!GetMessageExtraInfo` at `0x1800b0400`
- `USER32!GetMessageExtraInfo` at `0x1800b041c`
- `USER32!UpdateWindow` at `0x1800afda5`
- `USER32!UpdateWindow` at `0x1800afda5`
- `USER32!SetGestureConfig` at `0x1800b0505`
- `USER32!SetGestureConfig` at `0x1800b0505`
- `USER32!CloseGestureInfoHandle` at `0x1800b0561`
- `USER32!CloseGestureInfoHandle` at `0x1800b0561`
- `USER32!GetGestureInfo` at `0x1800b0546`
- `USER32!GetGestureInfo` at `0x1800b0546`
- `USER32!ChangeClipboardChain` at `0x1800afe13`
- `USER32!ChangeClipboardChain` at `0x1800afe13`
- `USER32!GetSysColorBrush` at `0x1800b0489`
- `USER32!GetSysColorBrush` at `0x1800b0489`
- `USER32!FillRect` at `0x1800b0146`
- `USER32!FillRect` at `0x1800b0146`
- `USER32!DefWindowProcW` at `0x1800afecf`
- `USER32!DefWindowProcW` at `0x1800afecf`
- `USER32!KillTimer` at `0x1800b01fb`
- `USER32!KillTimer` at `0x1800b0271`
- `USER32!KillTimer` at `0x1800b01fb`
- `USER32!KillTimer` at `0x1800b0271`
- `USER32!GetParent` at `0x1800b0709`
- `USER32!GetParent` at `0x1800b0709`
- `USER32!SendMessageW` at `0x1800aff66`
- `USER32!SendMessageW` at `0x1800b0008`
- `USER32!SendMessageW` at `0x1800b0054`
- `USER32!SendMessageW` at `0x1800b0637`
- `USER32!SendMessageW` at `0x1800b066b`
- `USER32!SendMessageW` at `0x1800aff66`
- `USER32!SendMessageW` at `0x1800b0008`
- `USER32!SendMessageW` at `0x1800b0054`
- `USER32!SendMessageW` at `0x1800b0637`
- `USER32!SendMessageW` at `0x1800b066b`
- `USER32!PostMessageW` at `0x1800b0244`
- `USER32!PostMessageW` at `0x1800b0244`
- `USER32!GetSysColor` at `0x1800b010a`
- `USER32!GetSysColor` at `0x1800b0473`
- `USER32!GetSysColor` at `0x1800b010a`
- `USER32!GetSysColor` at `0x1800b0473`
- `USER32!SetWindowLongPtrW` at `0x1800b0311`
- `USER32!SetWindowLongPtrW` at `0x1800b0311`
- `USER32!GetClientRect` at `0x1800b0136`
- `USER32!GetClientRect` at `0x1800b0136`
- `USER32!InvalidateRect` at `0x1800b05e4`
- `USER32!InvalidateRect` at `0x1800b05e4`
- `GDI32!SetBkColor` at `0x1800b047e`
- `GDI32!SetBkColor` at `0x1800b047e`
- `GDI32!DeleteObject` at `0x1800b014f`
- `GDI32!DeleteObject` at `0x1800b014f`
- `GDI32!CreateSolidBrush` at `0x1800b011a`
- `GDI32!CreateSolidBrush` at `0x1800b011a`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x1800afdd8`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x1800afdf2`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x1800afdd8`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x1800afdf2`
- `UxTheme!__imp_ShouldAppsUseDarkMode` at `0x1800affd1`
- `UxTheme!__imp_ShouldAppsUseDarkMode` at `0x1800affec`
- `UxTheme!__imp_ShouldAppsUseDarkMode` at `0x1800affd1`
- `UxTheme!__imp_ShouldAppsUseDarkMode` at `0x1800affec`
- `UxTheme!__imp_SetPreferredAppMode` at `0x1800aff37`
- `UxTheme!__imp_SetPreferredAppMode` at `0x1800aff37`
- `DUI70!FlushThemeHandles` at `0x1800affe6`
- `DUI70!FlushThemeHandles` at `0x1800affe6`
- `Windows.Storage!DrawTransparentBackground` at `0x1800b00fc`
- `Windows.Storage!DrawTransparentBackground` at `0x1800b00fc`

## pseudocode

```c

```
