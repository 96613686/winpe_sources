# CDesktopWatermark::s_DesktopBuildPaint(HDC__ *,tagRECT const *,HFONT__ *,bool)

- ea: `0x1800706a4`
- end: `0x1800713db`
- name: `?s_DesktopBuildPaint@CDesktopWatermark@@CAXPEAUHDC__@@PEBUtagRECT@@PEAUHFONT__@@_N@Z`
- size: `3383`
- prototype: `void __fastcall(HDC hdc, const struct tagRECT *, HFONT, bool)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting`

## callers

- `0x18006f2f4`

## callees

- `0x180043964`
- `0x180043ac0`
- `0x18006fe84`
- `0x18006ff98`
- `0x1800701e8`
- `0x1800704dc`
- `0x1800706a4`
- `0x1800713e4`
- `0x1800cecf4`
- `0x1800f0484`
- `0x1801d76f8`
- `0x180249490`
- `0x180249b0c`
- `0x180249b74`
- `0x18024a53c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180070931`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800709ef`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180070ce1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180070931`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800709ef`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180070ce1`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180070f43`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180070f43`
- `USER32!GetSysColor` at `0x1800707ca`
- `USER32!GetSysColor` at `0x1800707ca`
- `ntdll!RtlGetNtSystemRoot` at `0x1800710a4`
- `ntdll!RtlGetNtSystemRoot` at `0x180071112`
- `ntdll!RtlGetNtSystemRoot` at `0x1800710a4`
- `ntdll!RtlGetNtSystemRoot` at `0x180071112`
- `GDI32!SetTextColor` at `0x1800707eb`
- `GDI32!SetTextColor` at `0x180070d7f`
- `GDI32!SetTextColor` at `0x1800707eb`
- `GDI32!SetTextColor` at `0x180070d7f`
- `GDI32!SelectObject` at `0x180070809`
- `GDI32!SelectObject` at `0x180070d5b`
- `GDI32!SelectObject` at `0x18007105c`
- `GDI32!SelectObject` at `0x18007107e`
- `GDI32!SelectObject` at `0x180070809`
- `GDI32!SelectObject` at `0x180070d5b`
- `GDI32!SelectObject` at `0x18007105c`
- `GDI32!SelectObject` at `0x18007107e`
- `GDI32!SetBkMode` at `0x1800706fb`
- `GDI32!SetBkMode` at `0x180070d6d`
- `GDI32!SetBkMode` at `0x1800706fb`
- `GDI32!SetBkMode` at `0x180070d6d`
- `GDI32!GetTextExtentPoint32W` at `0x180070859`
- `GDI32!GetTextExtentPoint32W` at `0x180070885`
- `GDI32!GetTextExtentPoint32W` at `0x1800708b7`
- `GDI32!GetTextExtentPoint32W` at `0x1800708e9`
- `GDI32!GetTextExtentPoint32W` at `0x1800710c7`
- `GDI32!GetTextExtentPoint32W` at `0x180071215`
- `GDI32!GetTextExtentPoint32W` at `0x180071240`
- `GDI32!GetTextExtentPoint32W` at `0x180070859`
- `GDI32!GetTextExtentPoint32W` at `0x180070885`
- `GDI32!GetTextExtentPoint32W` at `0x1800708b7`
- `GDI32!GetTextExtentPoint32W` at `0x1800708e9`
- `GDI32!GetTextExtentPoint32W` at `0x1800710c7`
- `GDI32!GetTextExtentPoint32W` at `0x180071215`
- `GDI32!GetTextExtentPoint32W` at `0x180071240`
- `GDI32!SetTextAlign` at `0x180070a73`
- `GDI32!SetTextAlign` at `0x180070d91`
- `GDI32!SetTextAlign` at `0x1800712a3`
- `GDI32!SetTextAlign` at `0x180070a73`
- `GDI32!SetTextAlign` at `0x180070d91`
- `GDI32!SetTextAlign` at `0x1800712a3`
- `GDI32!GetTextAlign` at `0x1800706e4`
- `GDI32!GetTextAlign` at `0x1800706e4`
- `GDI32!ExtTextOutW` at `0x180070af4`
- `GDI32!ExtTextOutW` at `0x180070b79`
- `GDI32!ExtTextOutW` at `0x180070c04`
- `GDI32!ExtTextOutW` at `0x180070c8f`
- `GDI32!ExtTextOutW` at `0x180070af4`
- `GDI32!ExtTextOutW` at `0x180070b79`
- `GDI32!ExtTextOutW` at `0x180070c04`
- `GDI32!ExtTextOutW` at `0x180070c8f`
- `GDI32!GetLayout` at `0x180070aae`
- `GDI32!GetLayout` at `0x180070b35`
- `GDI32!GetLayout` at `0x180070bbd`
- `GDI32!GetLayout` at `0x180070c48`
- `GDI32!GetLayout` at `0x180070aae`
- `GDI32!GetLayout` at `0x180070b35`
- `GDI32!GetLayout` at `0x180070bbd`
- `GDI32!GetLayout` at `0x180070c48`
- `UxTheme!EndBufferedPaint` at `0x18007103b`
- `UxTheme!EndBufferedPaint` at `0x18007103b`
- `UxTheme!BeginBufferedPaint` at `0x180070fc0`
- `UxTheme!BeginBufferedPaint` at `0x180070fc0`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x180070e1f`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x180070e6b`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x180070ee4`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x18007101d`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x180071190`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x180071322`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x1800713b5`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x180070e1f`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x180070e6b`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x180070ee4`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x18007101d`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x180071190`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x180071322`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x1800713b5`
- `WINBRAND!BrandingLoadStringForEdition` at `0x180070795`
- `WINBRAND!BrandingLoadStringForEdition` at `0x180070795`
- `Wldp!__imp_?WldpIsProductionConfiguration@@YAJPEAH@Z` at `0x180070f19`
- `Wldp!__imp_?WldpIsProductionConfiguration@@YAJPEAH@Z` at `0x180070f19`

## pseudocode

```c

```
