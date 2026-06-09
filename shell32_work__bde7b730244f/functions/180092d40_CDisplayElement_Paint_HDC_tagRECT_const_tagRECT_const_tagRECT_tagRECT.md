# CDisplayElement::Paint(HDC__ *,tagRECT const *,tagRECT const *,tagRECT *,tagRECT *)

- ea: `0x180092d40`
- end: `0x180092f28`
- name: `?Paint@CDisplayElement@@UEAAXPEAUHDC__@@PEBUtagRECT@@1PEAU3@2@Z`
- size: `488`
- prototype: `void __usercall(CDisplayElement *__hidden this@<rcx>, HDC hdc@<rdx>, const struct tagRECT *@<r8>, const struct tagRECT *@<r9>, struct tagRECT *, struct tagRECT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x180092abc`
- `0x180092d40`
- `0x180092f30`
- `0x180092fa4`
- `0x180093034`
- `0x18017aaac`
- `0x180233280`
- `0x180571010`

## import_xrefs

- `USER32!DrawTextW` at `0x180092ee2`
- `USER32!DrawTextW` at `0x180092ee2`
- `GDI32!SelectObject` at `0x180092dac`
- `GDI32!SelectObject` at `0x180092ef7`
- `GDI32!SelectObject` at `0x180092dac`
- `GDI32!SelectObject` at `0x180092ef7`
- `GDI32!GetTextColor` at `0x180092e96`
- `GDI32!GetTextColor` at `0x180092e96`
- `DUI70!?GetFontStyle@Element@DirectUI@@QEAAHXZ` at `0x180092e89`
- `DUI70!?GetFontStyle@Element@DirectUI@@QEAAHXZ` at `0x180092e89`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180092e42`
- `DUI70!?GetType@Value@DirectUI@@QEBAHXZ` at `0x180092e5f`
- `DUI70!?GetType@Value@DirectUI@@QEBAHXZ` at `0x180092e5f`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180092ea1`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180092ec9`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180092ea1`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180092ec9`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180092eeb`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180092eeb`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180092e53`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180092e53`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x180092df1`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x180092df1`
- `DUI70!?Paint@Element@DirectUI@@UEAAXPEAUHDC__@@PEBUtagRECT@@1PEAU4@2@Z` at `0x180092d82`
- `DUI70!?Paint@Element@DirectUI@@UEAAXPEAUHDC__@@PEBUtagRECT@@1PEAU4@2@Z` at `0x180092d82`
- `DUI70!DUIDrawShadowText` at `0x180092ebe`
- `DUI70!DUIDrawShadowText` at `0x180092ebe`
- `DUI70!?GetMouseFocused@Element@DirectUI@@QEAA_NXZ` at `0x180092dd0`
- `DUI70!?GetMouseFocused@Element@DirectUI@@QEAA_NXZ` at `0x180092dd0`

## pseudocode

```c

```
