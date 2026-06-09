# DataTypeEnumToString(_DATA_TYPE_NODE)

- ea: `0x1800185b8`
- end: `0x180018782`
- name: `?DataTypeEnumToString@@YAPEAGW4_DATA_TYPE_NODE@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18001b870`

## callees

- `0x1800185b8`

## string_xrefs

- `0x180018690`: `DATA_TYPE_TEMP`
- `0x180018772`: `DATA_TYPE_TEMP_PREV_INSTALLATION`
- `0x180018762`: `DATA_TYPE_STAGED_UPDATES`
- `0x18001874a`: `DATA_TYPE_SR_UPDATESCRATCH`

## pseudocode

```c
const wchar_t *__fastcall DataTypeEnumToString(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx

  if ( a1 <= 16 )
  {
    if ( a1 == 16 )
      return L"DATA_TYPE_DOWNLOADS";
    if ( a1 > 8 )
    {
      v8 = a1 - 9;
      if ( !v8 )
        return L"DATA_TYPE_DOCS";
      v9 = v8 - 1;
      if ( !v9 )
        return L"DATA_TYPE_TEMP";
      v10 = v9 - 1;
      if ( !v10 )
        return L"DATA_TYPE_TELEMETRY";
      v11 = v10 - 1;
      if ( !v11 )
        return L"DATA_TYPE_PIM";
      v12 = v11 - 1;
      if ( !v12 )
        return L"DATA_TYPE_BUILTINAPPS";
      v13 = v12 - 1;
      if ( !v13 )
        return L"DATA_TYPE_SYSTEMSEMIPERM";
      if ( v13 == 1 )
        return L"DATA_TYPE_TEST";
    }
    else
    {
      if ( a1 == 8 )
        return L"DATA_TYPE_MAPS";
      if ( !a1 )
        return L"DATA_TYPE_ROOT";
      v1 = a1 - 1;
      if ( !v1 )
        return L"DATA_TYPE_SYSTEMANDRESERVED";
      v2 = v1 - 1;
      if ( !v2 )
        return L"DATA_TYPE_MUSIC";
      v3 = v2 - 1;
      if ( !v3 )
        return L"DATA_TYPE_PICTURES";
      v4 = v3 - 1;
      if ( !v4 )
        return L"DATA_TYPE_VIDEOS";
      v5 = v4 - 1;
      if ( !v5 )
        return L"DATA_TYPE_PODCASTS";
      v6 = v5 - 1;
      if ( !v6 )
        return L"DATA_TYPE_RINGTONES";
      if ( v6 == 1 )
        return L"DATA_TYPE_APPS";
    }
    return L"Unknown";
  }
  if ( a1 <= 25 )
  {
    if ( a1 == 25 )
      return L"DATA_TYPE_SYSTEM_HIBERFILE";
    v14 = a1 - 17;
    if ( !v14 )
      return L"DATA_TYPE_ONEDRIVE";
    v15 = v14 - 1;
    if ( !v15 )
      return L"DATA_TYPE_CLASSIC_APPS";
    v16 = v15 - 1;
    if ( !v16 )
      return L"DATA_TYPE_ALLMEDIA";
    v17 = v16 - 1;
    if ( !v17 )
      return L"DATA_TYPE_CURRENT_USER_PROFILE";
    v18 = v17 - 1;
    if ( !v18 )
      return L"DATA_TYPE_OTHER_USER_PROFILES";
    v19 = v18 - 1;
    if ( !v19 )
      return L"DATA_TYPE_RECYCLE_BIN";
    v20 = v19 - 1;
    if ( !v20 )
      return L"DATA_TYPE_OTHER";
    if ( v20 == 1 )
      return L"DATA_TYPE_SYSTEM_PAGEFILE";
    return L"Unknown";
  }
  v21 = a1 - 26;
  if ( !v21 )
    return L"DATA_TYPE_SYSTEM_RESTORE";
  v22 = v21 - 1;
  if ( !v22 )
    return L"DATA_TYPE_TEMP_PREV_INSTALLATION";
  v23 = v22 - 1;
  if ( !v23 )
    return L"DATA_TYPE_DESKTOP";
  v24 = v23 - 1;
  if ( !v24 )
    return L"DATA_TYPE_STAGED_UPDATES";
  v25 = v24 - 1;
  if ( !v25 )
    return L"DATA_TYPE_SR_HARD";
  v26 = v25 - 1;
  if ( !v26 )
    return L"DATA_TYPE_SR_SOFT";
  if ( v26 != 1 )
    return L"Unknown";
  return L"DATA_TYPE_SR_UPDATESCRATCH";
}

```

## disassembly

```asm
0x1800185b8  cmp     ecx, 10h
0x1800185bb  jg      loc_1800186A8
0x1800185c1  jz      loc_1800186A0
0x1800185c7  cmp     ecx, 8
0x1800185ca  jg      short loc_180018641
0x1800185cc  jz      short loc_180018639
0x1800185ce  test    ecx, ecx
0x1800185d0  jz      short loc_180018631
0x1800185d2  sub     ecx, 1
0x1800185d5  jz      short loc_180018629
0x1800185d7  sub     ecx, 1
0x1800185da  jz      short loc_180018621
0x1800185dc  sub     ecx, 1
0x1800185df  jz      short loc_180018619
0x1800185e1  sub     ecx, 1
0x1800185e4  jz      short loc_180018611
0x1800185e6  sub     ecx, 1
0x1800185e9  jz      short loc_180018609
0x1800185eb  sub     ecx, 1
0x1800185ee  jz      short loc_180018601
0x1800185f0  cmp     ecx, 1
0x1800185f3  jnz     loc_180018742
0x1800185f9  lea     rax, aDataTypeApps; "DATA_TYPE_APPS"
0x180018600  retn
0x180018601  lea     rax, aDataTypeRingto; "DATA_TYPE_RINGTONES"
0x180018608  retn
0x180018609  lea     rax, aDataTypePodcas; "DATA_TYPE_PODCASTS"
0x180018610  retn
0x180018611  lea     rax, aDataTypeVideos; "DATA_TYPE_VIDEOS"
0x180018618  retn
0x180018619  lea     rax, aDataTypePictur; "DATA_TYPE_PICTURES"
0x180018620  retn
0x180018621  lea     rax, aDataTypeMusic; "DATA_TYPE_MUSIC"
0x180018628  retn
0x180018629  lea     rax, aDataTypeSystem_0; "DATA_TYPE_SYSTEMANDRESERVED"
0x180018630  retn
0x180018631  lea     rax, aDataTypeRoot; "DATA_TYPE_ROOT"
0x180018638  retn
0x180018639  lea     rax, aDataTypeMaps; "DATA_TYPE_MAPS"
0x180018640  retn
0x180018641  sub     ecx, 9
0x180018644  jz      short loc_180018698
0x180018646  sub     ecx, 1
0x180018649  jz      short loc_180018690
0x18001864b  sub     ecx, 1
0x18001864e  jz      short loc_180018688
0x180018650  sub     ecx, 1
0x180018653  jz      short loc_180018680
0x180018655  sub     ecx, 1
0x180018658  jz      short loc_180018678
0x18001865a  sub     ecx, 1
0x18001865d  jz      short loc_180018670
0x18001865f  cmp     ecx, 1
0x180018662  jnz     loc_180018742
0x180018668  lea     rax, aDataTypeTest; "DATA_TYPE_TEST"
0x18001866f  retn
0x180018670  lea     rax, aDataTypeSystem_1; "DATA_TYPE_SYSTEMSEMIPERM"
0x180018677  retn
0x180018678  lea     rax, aDataTypeBuilti; "DATA_TYPE_BUILTINAPPS"
0x18001867f  retn
0x180018680  lea     rax, aDataTypePim; "DATA_TYPE_PIM"
0x180018687  retn
0x180018688  lea     rax, aDataTypeTeleme; "DATA_TYPE_TELEMETRY"
0x18001868f  retn
0x180018690  lea     rax, aDataTypeTemp; "DATA_TYPE_TEMP"
0x180018697  retn
0x180018698  lea     rax, aDataTypeDocs; "DATA_TYPE_DOCS"
0x18001869f  retn
0x1800186a0  lea     rax, aDataTypeDownlo; "DATA_TYPE_DOWNLOADS"
0x1800186a7  retn
0x1800186a8  cmp     ecx, 19h
0x1800186ab  jg      short loc_18001871F
0x1800186ad  jz      short loc_180018717
0x1800186af  sub     ecx, 11h
0x1800186b2  jz      short loc_18001870F
0x1800186b4  sub     ecx, 1
0x1800186b7  jz      short loc_180018707
0x1800186b9  sub     ecx, 1
0x1800186bc  jz      short loc_1800186FF
0x1800186be  sub     ecx, 1
0x1800186c1  jz      short loc_1800186F7
0x1800186c3  sub     ecx, 1
0x1800186c6  jz      short loc_1800186EF
0x1800186c8  sub     ecx, 1
0x1800186cb  jz      short loc_1800186E7
0x1800186cd  sub     ecx, 1
0x1800186d0  jz      short loc_1800186DF
0x1800186d2  cmp     ecx, 1
0x1800186d5  jnz     short loc_180018742
0x1800186d7  lea     rax, aDataTypeSystem_3; "DATA_TYPE_SYSTEM_PAGEFILE"
0x1800186de  retn
0x1800186df  lea     rax, aDataTypeOther; "DATA_TYPE_OTHER"
0x1800186e6  retn
0x1800186e7  lea     rax, aDataTypeRecycl; "DATA_TYPE_RECYCLE_BIN"
0x1800186ee  retn
0x1800186ef  lea     rax, aDataTypeOtherU; "DATA_TYPE_OTHER_USER_PROFILES"
0x1800186f6  retn
0x1800186f7  lea     rax, aDataTypeCurren; "DATA_TYPE_CURRENT_USER_PROFILE"
0x1800186fe  retn
0x1800186ff  lea     rax, aDataTypeAllmed; "DATA_TYPE_ALLMEDIA"
0x180018706  retn
0x180018707  lea     rax, aDataTypeClassi; "DATA_TYPE_CLASSIC_APPS"
0x18001870e  retn
0x18001870f  lea     rax, aDataTypeOnedri; "DATA_TYPE_ONEDRIVE"
0x180018716  retn
0x180018717  lea     rax, aDataTypeSystem; "DATA_TYPE_SYSTEM_HIBERFILE"
0x18001871e  retn
0x18001871f  sub     ecx, 1Ah
0x180018722  jz      short loc_18001877A
0x180018724  sub     ecx, 1
0x180018727  jz      short loc_180018772
0x180018729  sub     ecx, 1
0x18001872c  jz      short loc_18001876A
0x18001872e  sub     ecx, 1
0x180018731  jz      short loc_180018762
0x180018733  sub     ecx, 1
0x180018736  jz      short loc_18001875A
0x180018738  sub     ecx, 1
0x18001873b  jz      short loc_180018752
0x18001873d  cmp     ecx, 1
0x180018740  jz      short loc_18001874A
0x180018742  lea     rax, aUnknown; "Unknown"
0x180018749  retn
0x18001874a  lea     rax, aDataTypeSrUpda; "DATA_TYPE_SR_UPDATESCRATCH"
0x180018751  retn
0x180018752  lea     rax, aDataTypeSrSoft; "DATA_TYPE_SR_SOFT"
0x180018759  retn
0x18001875a  lea     rax, aDataTypeSrHard; "DATA_TYPE_SR_HARD"
0x180018761  retn
0x180018762  lea     rax, aDataTypeStaged; "DATA_TYPE_STAGED_UPDATES"
0x180018769  retn
0x18001876a  lea     rax, aDataTypeDeskto; "DATA_TYPE_DESKTOP"
0x180018771  retn
0x180018772  lea     rax, aDataTypeTempPr; "DATA_TYPE_TEMP_PREV_INSTALLATION"
0x180018779  retn
0x18001877a  lea     rax, aDataTypeSystem_2; "DATA_TYPE_SYSTEM_RESTORE"
0x180018781  retn
```
