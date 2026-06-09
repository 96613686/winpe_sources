# CDesktopWatermark::s_DesktopBuildPaint(HDC__ *,tagRECT const *,HFONT__ *,bool)

- ea: `0x1800307f0`
- end: `0x180031418`
- name: `?s_DesktopBuildPaint@CDesktopWatermark@@CAXPEAUHDC__@@PEBUtagRECT@@PEAUHFONT__@@_N@Z`
- size: `3112`
- prototype: `void __fastcall(HDC hdc, const struct tagRECT *, HFONT, bool)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting`

## callers

- `0x18002f510`

## callees

- `0x180030034`
- `0x180030134`
- `0x180030384`
- `0x18003063c`
- `0x1800307f0`
- `0x180031420`
- `0x180047bb4`
- `0x180047d00`
- `0x180060740`
- `0x1800ed6bc`
- `0x1801c1444`
- `0x180233280`
- `0x1802338fc`
- `0x180233964`
- `0x1802342fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180030a41`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180030af9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180030daf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180030a41`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180030af9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180030daf`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180030fda`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180030fda`
- `USER32!GetSysColor` at `0x180030904`
- `USER32!GetSysColor` at `0x180030904`
- `ntdll!RtlGetNtSystemRoot` at `0x180031117`
- `ntdll!RtlGetNtSystemRoot` at `0x180031179`
- `ntdll!RtlGetNtSystemRoot` at `0x180031117`
- `ntdll!RtlGetNtSystemRoot` at `0x180031179`
- `GDI32!SetTextColor` at `0x18003091f`
- `GDI32!SetTextColor` at `0x180030e3b`
- `GDI32!SetTextColor` at `0x18003091f`
- `GDI32!SetTextColor` at `0x180030e3b`
- `GDI32!SelectObject` at `0x180030937`
- `GDI32!SelectObject` at `0x180030e23`
- `GDI32!SelectObject` at `0x1800310db`
- `GDI32!SelectObject` at `0x1800310f7`
- `GDI32!SelectObject` at `0x180030937`
- `GDI32!SelectObject` at `0x180030e23`
- `GDI32!SelectObject` at `0x1800310db`
- `GDI32!SelectObject` at `0x1800310f7`
- `GDI32!SetBkMode` at `0x180030841`
- `GDI32!SetBkMode` at `0x180030e2f`
- `GDI32!SetBkMode` at `0x180030841`
- `GDI32!SetBkMode` at `0x180030e2f`
- `GDI32!GetTextExtentPoint32W` at `0x180030981`
- `GDI32!GetTextExtentPoint32W` at `0x1800309a7`
- `GDI32!GetTextExtentPoint32W` at `0x1800309d3`
- `GDI32!GetTextExtentPoint32W` at `0x1800309ff`
- `GDI32!GetTextExtentPoint32W` at `0x180031134`
- `GDI32!GetTextExtentPoint32W` at `0x180031270`
- `GDI32!GetTextExtentPoint32W` at `0x180031295`
- `GDI32!GetTextExtentPoint32W` at `0x180030981`
- `GDI32!GetTextExtentPoint32W` at `0x1800309a7`
- `GDI32!GetTextExtentPoint32W` at `0x1800309d3`
- `GDI32!GetTextExtentPoint32W` at `0x1800309ff`
- `GDI32!GetTextExtentPoint32W` at `0x180031134`
- `GDI32!GetTextExtentPoint32W` at `0x180031270`
- `GDI32!GetTextExtentPoint32W` at `0x180031295`
- `GDI32!SetTextAlign` at `0x180030b77`
- `GDI32!SetTextAlign` at `0x180030e47`
- `GDI32!SetTextAlign` at `0x1800312f2`
- `GDI32!SetTextAlign` at `0x180030b77`
- `GDI32!SetTextAlign` at `0x180030e47`
- `GDI32!SetTextAlign` at `0x1800312f2`
- `GDI32!GetTextAlign` at `0x180030830`
- `GDI32!GetTextAlign` at `0x180030830`
- `GDI32!ExtTextOutW` at `0x180030bec`
- `GDI32!ExtTextOutW` at `0x180030c65`
- `GDI32!ExtTextOutW` at `0x180030ce4`
- `GDI32!ExtTextOutW` at `0x180030d63`
- `GDI32!ExtTextOutW` at `0x180030bec`
- `GDI32!ExtTextOutW` at `0x180030c65`
- `GDI32!ExtTextOutW` at `0x180030ce4`
- `GDI32!ExtTextOutW` at `0x180030d63`
- `GDI32!GetLayout` at `0x180030bac`
- `GDI32!GetLayout` at `0x180030c27`
- `GDI32!GetLayout` at `0x180030ca3`
- `GDI32!GetLayout` at `0x180030d22`
- `GDI32!GetLayout` at `0x180030bac`
- `GDI32!GetLayout` at `0x180030c27`
- `GDI32!GetLayout` at `0x180030ca3`
- `GDI32!GetLayout` at `0x180030d22`
- `UxTheme!EndBufferedPaint` at `0x1800310c0`
- `UxTheme!EndBufferedPaint` at `0x1800310c0`
- `UxTheme!BeginBufferedPaint` at `0x180031051`
- `UxTheme!BeginBufferedPaint` at `0x180031051`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x180030ece`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x180030f14`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x180030f87`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x1800310a8`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x1800311f1`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x18003136b`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x1800313f8`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x180030ece`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x180030f14`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x180030f87`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x1800310a8`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x1800311f1`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x18003136b`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x1800313f8`
- `WINBRAND!BrandingLoadStringForEdition` at `0x1800308d5`
- `WINBRAND!BrandingLoadStringForEdition` at `0x1800308d5`
- `Wldp!__imp_?WldpIsProductionConfiguration@@YAJPEAH@Z` at `0x180030fb6`
- `Wldp!__imp_?WldpIsProductionConfiguration@@YAJPEAH@Z` at `0x180030fb6`

## pseudocode

```c

```
