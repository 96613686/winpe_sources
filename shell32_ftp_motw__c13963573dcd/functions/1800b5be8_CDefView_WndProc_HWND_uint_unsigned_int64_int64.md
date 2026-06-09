# CDefView::WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800b5be8`
- end: `0x1800b69eb`
- name: `?WndProc@CDefView@@AEAA_JPEAUHWND__@@I_K_J@Z`
- size: `3587`
- prototype: `__int64 __usercall@<rax>(CDefView *__hidden this@<rcx>, HWND@<rdx>, unsigned int@<r8d>, unsigned __int64@<r9>, __int64)`
- caller_count: `1`
- callee_count: `54`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800b5b10`

## callees

- `0x18000eab4`
- `0x18000f9c4`
- `0x18000fc30`
- `0x18000fe58`
- `0x18001024c`
- `0x1800102f0`
- `0x180010730`
- `0x180010c0c`
- `0x1800443c4`
- `0x18004e1b8`
- `0x180055afc`
- `0x1800577f0`
- `0x18005e810`
- `0x18005fd00`
- `0x18006134c`
- `0x18009e194`
- `0x18009e29c`
- `0x1800ad140`
- `0x1800ad2dc`
- `0x1800ad4f0`
- `0x1800b4b18`
- `0x1800b5be8`
- `0x1800b8bc8`
- `0x1800b9790`
- `0x1800ff9f0`
- `0x180101f20`
- `0x18011d298`
- `0x18012d338`
- `0x18014c4cc`
- `0x18014d74c`
- `0x18014dd74`
- `0x18014fe1c`
- `0x180156728`
- `0x18016476c`
- `0x18016bd68`
- `0x180170898`
- `0x1801bcd70`
- `0x1801ee978`
- `0x1801ef1b8`
- `0x180210a40`
- `0x180249490`
- `0x1802dd610`
- `0x1802e7478`
- `0x1802e7d70`
- `0x1802eabbc`
- `0x1802eb620`
- `0x1802ef150`
- `0x1802f70ec`
- `0x1802f7160`
- `0x1802f74dc`

## import_xrefs

- `USER32!GetMessageExtraInfo` at `0x1800b634f`
- `USER32!GetMessageExtraInfo` at `0x1800b6371`
- `USER32!GetMessageExtraInfo` at `0x1800b634f`
- `USER32!GetMessageExtraInfo` at `0x1800b6371`
- `USER32!UpdateWindow` at `0x1800b5ce1`
- `USER32!UpdateWindow` at `0x1800b5ce1`
- `USER32!SetGestureConfig` at `0x1800b6456`
- `USER32!SetGestureConfig` at `0x1800b6456`
- `USER32!CloseGestureInfoHandle` at `0x1800b64be`
- `USER32!CloseGestureInfoHandle` at `0x1800b64be`
- `USER32!GetGestureInfo` at `0x1800b649d`
- `USER32!GetGestureInfo` at `0x1800b649d`
- `USER32!ChangeClipboardChain` at `0x1800b5d6c`
- `USER32!ChangeClipboardChain` at `0x1800b5d6c`
- `USER32!GetSysColorBrush` at `0x1800b63ed`
- `USER32!GetSysColorBrush` at `0x1800b63ed`
- `USER32!FillRect` at `0x1800b606f`
- `USER32!FillRect` at `0x1800b606f`
- `USER32!DefWindowProcW` at `0x1800b68fd`
- `USER32!DefWindowProcW` at `0x1800b68fd`
- `USER32!KillTimer` at `0x1800b6131`
- `USER32!KillTimer` at `0x1800b61b3`
- `USER32!KillTimer` at `0x1800b6131`
- `USER32!KillTimer` at `0x1800b61b3`
- `USER32!GetParent` at `0x1800b6675`
- `USER32!GetParent` at `0x1800b6675`
- `USER32!PostMessageW` at `0x1800b6180`
- `USER32!PostMessageW` at `0x1800b6180`
- `USER32!GetSysColor` at `0x1800b6020`
- `USER32!GetSysColor` at `0x1800b63cb`
- `USER32!GetSysColor` at `0x1800b6020`
- `USER32!GetSysColor` at `0x1800b63cb`
- `USER32!SetWindowLongPtrW` at `0x1800b6256`
- `USER32!SetWindowLongPtrW` at `0x1800b6256`
- `USER32!GetClientRect` at `0x1800b6059`
- `USER32!GetClientRect` at `0x1800b6059`
- `USER32!InvalidateRect` at `0x1800b654c`
- `USER32!InvalidateRect` at `0x1800b654c`
- `USER32!SendMessageW` at `0x1800b5e92`
- `USER32!SendMessageW` at `0x1800b5f6a`
- `USER32!SendMessageW` at `0x1800b659d`
- `USER32!SendMessageW` at `0x1800b65d7`
- `USER32!SendMessageW` at `0x1800b5e92`
- `USER32!SendMessageW` at `0x1800b5f6a`
- `USER32!SendMessageW` at `0x1800b659d`
- `USER32!SendMessageW` at `0x1800b65d7`
- `GDI32!SetBkColor` at `0x1800b63dc`
- `GDI32!SetBkColor` at `0x1800b63dc`
- `GDI32!DeleteObject` at `0x1800b607e`
- `GDI32!DeleteObject` at `0x1800b607e`
- `GDI32!CreateSolidBrush` at `0x1800b6036`
- `GDI32!CreateSolidBrush` at `0x1800b6036`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x1800b5d24`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x1800b5d44`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x1800b5d24`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x1800b5d44`
- `UxTheme!__imp_SetPreferredAppMode` at `0x1800b5e5d`
- `UxTheme!__imp_SetPreferredAppMode` at `0x1800b5e5d`
- `Windows.Storage!DrawTransparentBackground` at `0x1800b600c`
- `Windows.Storage!DrawTransparentBackground` at `0x1800b600c`

## pseudocode

```c

```
