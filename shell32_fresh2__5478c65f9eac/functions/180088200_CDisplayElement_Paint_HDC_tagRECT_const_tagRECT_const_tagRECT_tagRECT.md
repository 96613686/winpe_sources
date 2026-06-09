# CDisplayElement::Paint(HDC__ *,tagRECT const *,tagRECT const *,tagRECT *,tagRECT *)

- ea: `0x180088200`
- end: `0x180088441`
- name: `?Paint@CDisplayElement@@UEAAXPEAUHDC__@@PEBUtagRECT@@1PEAU3@2@Z`
- size: `577`
- prototype: `void __usercall(CDisplayElement *__hidden this@<rcx>, HDC hdc@<rdx>, const struct tagRECT *@<r8>, const struct tagRECT *@<r9>, struct tagRECT *, struct tagRECT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x180087f34`
- `0x180088200`
- `0x180088448`
- `0x1800884bc`
- `0x180088558`
- `0x18018cb54`
- `0x180249490`
- `0x1805b2010`

## import_xrefs

- `USER32!DrawTextW` at `0x1800883e8`
- `USER32!DrawTextW` at `0x1800883e8`
- `GDI32!SelectObject` at `0x180088272`
- `GDI32!SelectObject` at `0x180088409`
- `GDI32!SelectObject` at `0x180088272`
- `GDI32!SelectObject` at `0x180088409`
- `GDI32!GetTextColor` at `0x180088384`
- `GDI32!GetTextColor` at `0x180088384`
- `DUI70!?GetFontStyle@Element@DirectUI@@QEAAHXZ` at `0x180088371`
- `DUI70!?GetFontStyle@Element@DirectUI@@QEAAHXZ` at `0x180088371`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18008831a`
- `DUI70!?GetType@Value@DirectUI@@QEBAHXZ` at `0x18008833d`
- `DUI70!?GetType@Value@DirectUI@@QEBAHXZ` at `0x18008833d`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180088395`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x1800883c9`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180088395`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x1800883c9`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800883f7`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800883f7`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18008832b`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18008832b`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x1800882c3`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x1800882c3`
- `DUI70!?Paint@Element@DirectUI@@UEAAXPEAUHDC__@@PEBUtagRECT@@1PEAU4@2@Z` at `0x180088242`
- `DUI70!?Paint@Element@DirectUI@@UEAAXPEAUHDC__@@PEBUtagRECT@@1PEAU4@2@Z` at `0x180088242`
- `DUI70!DUIDrawShadowText` at `0x1800883b8`
- `DUI70!DUIDrawShadowText` at `0x1800883b8`
- `DUI70!?GetMouseFocused@Element@DirectUI@@QEAA_NXZ` at `0x18008829c`
- `DUI70!?GetMouseFocused@Element@DirectUI@@QEAA_NXZ` at `0x18008829c`

## pseudocode

```c

```
