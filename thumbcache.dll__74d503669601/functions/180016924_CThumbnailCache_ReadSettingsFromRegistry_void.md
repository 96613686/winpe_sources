# CThumbnailCache::_ReadSettingsFromRegistry(void)

- ea: `0x180016924`
- end: `0x180017542`
- name: `?_ReadSettingsFromRegistry@CThumbnailCache@@AEAAXXZ`
- size: `3102`
- prototype: `void __fastcall(CThumbnailCache *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015868`

## callees

- `0x180016924`
- `0x18002f834`
- `0x180035830`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016979`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016979`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017264`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017264`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800169e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016a1f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016a63`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016ad1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016b0f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016b4d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016b8b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016bc9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016c07`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016c45`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016c83`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016cc1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016cff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016d3d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016d7b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016db9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001715a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017198`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800171d6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017214`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017252`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800169e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016a1f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016a63`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016ad1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016b0f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016b4d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016b8b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016bc9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016c07`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016c45`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016c83`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016cc1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016cff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016d3d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016d7b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016db9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001715a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017198`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800171d6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017214`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017252`

## string_xrefs

- `0x18001696b`: `SOFTWARE\Microsoft\Windows\CurrentVersion\ThumbnailCache`
- `0x180016fe6`: `MaxCacheFileSize256`
- `0x1800170d6`: `MaxCacheFileSizeEXIF`
- `0x180016f6b`: `MaxCacheFileSize16`
- `0x180016f8c`: `MaxCacheFileSize32`
- `0x180016f28`: `MinCacheFilesSizesWhenShrinkingEXIF`
- `0x180016e92`: `MinCacheFilesSizesWhenShrinking1280`
- `0x180016dd7`: `MinCacheFilesSizesWhenShrinking16`
- `0x180016fc8`: `MaxCacheFileSize96`
- `0x18001709a`: `MaxCacheFileSizeWide`
- `0x1800170b8`: `MaxCacheFileSizeWideAlternate`
- `0x18001705e`: `MaxCacheFileSize2560`
- `0x180016eec`: `MinCacheFilesSizesWhenShrinkingWide`
- `0x180016f46`: `MinCacheFilesSizesWhenShrinkingCustomStream`
- `0x180017022`: `MaxCacheFileSize1280`
- `0x180016e1a`: `MinCacheFilesSizesWhenShrinking48`
- `0x180016faa`: `MaxCacheFileSize48`
- `0x1800170f4`: `MaxCacheFileSizeCustomStream`
- `0x180017040`: `MaxCacheFileSize1920`
- `0x180016e56`: `MinCacheFilesSizesWhenShrinking256`
- `0x180016dfc`: `MinCacheFilesSizesWhenShrinking32`
- `0x180016eb0`: `MinCacheFilesSizesWhenShrinking1920`
- `0x18001707c`: `MaxCacheFileSize256SlowReclaim`
- `0x180016ece`: `MinCacheFilesSizesWhenShrinking2560`
- `0x180017004`: `MaxCacheFileSize768`
- `0x180016e38`: `MinCacheFilesSizesWhenShrinking96`
- `0x180016f0a`: `MinCacheFilesSizesWhenShrinkingWideAlternate`
- `0x180016e74`: `MinCacheFilesSizesWhenShrinking768`

## pseudocode

```c
void __fastcall CThumbnailCache::_ReadSettingsFromRegistry(CThumbnailCache *this)
{
  DWORD v2; // eax
  unsigned int v3; // ecx
  unsigned int i; // eax
  __int64 v5; // rdx
  DWORD v6; // eax
  DWORD v7; // eax
  DWORD v8; // eax
  DWORD v9; // eax
  DWORD v10; // eax
  DWORD v11; // eax
  DWORD v12; // eax
  DWORD v13; // eax
  DWORD v14; // eax
  DWORD v15; // eax
  DWORD v16; // eax
  DWORD v17; // eax
  DWORD v18; // eax
  DWORD v19; // eax
  DWORD v20; // eax
  DWORD v21; // eax
  DWORD v22; // eax
  DWORD v23; // eax
  DWORD v24; // eax
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  DWORD Type; // [rsp+38h] [rbp-20h] BYREF
  BYTE Data[4]; // [rsp+3Ch] [rbp-1Ch] BYREF
  DWORD cbData; // [rsp+40h] [rbp-18h] BYREF

  if ( !*((_DWORD *)this + 190) )
  {
    hKey = 0;
    if ( RegOpenKeyExW(
           HKEY_CURRENT_USER,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ThumbnailCache",
           0,
           0x20019u,
           &hKey) )
    {
LABEL_3:
      *((_DWORD *)this + 190) = 1;
      return;
    }
    *(_DWORD *)Data = 0;
    Type = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"MinFreeSpace", 0, &Type, Data, &cbData) && Type == 4 )
    {
      if ( *(_DWORD *)Data >= 0xC8u )
      {
        if ( *(_DWORD *)Data <= 0xFFFu )
          dword_1800623EC = *(_DWORD *)Data << 20;
        else
          dword_1800623EC = -1048576;
      }
      else
      {
        dword_1800623EC = 209715200;
      }
    }
    Type = 0;
    *(_DWORD *)Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"MaxPercentageOfFreeSpaceForRebalancing", 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData)
      && *(_DWORD *)Data == 4 )
    {
      v6 = Type;
      if ( Type > 0x64 )
        v6 = 100;
      dword_1800623F0 = v6;
    }
    Type = 0;
    *(_DWORD *)Data = 0;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"ShrinkIfGreaterThanPercentageOfFreeSpace", 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData)
      || *(_DWORD *)Data != 4 )
    {
      v2 = dword_1800623E8;
    }
    else
    {
      v2 = Type;
      if ( Type > 0x64 )
      {
        v2 = 100;
        goto LABEL_11;
      }
      dword_1800623E8 = Type;
    }
    if ( v2 )
    {
LABEL_12:
      v3 = dword_1800623F0;
      if ( !dword_1800623F0 )
      {
        v3 = 1;
        dword_1800623F0 = 1;
      }
      if ( v2 < v3 )
        dword_1800623F0 = v2;
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"BalancedPercentage16", 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData)
        && *(_DWORD *)Data == 4 )
      {
        v7 = Type;
        if ( Type > 0x64 )
          v7 = 100;
        dword_1800623B0 = v7;
      }
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"BalancedPercentage32", 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData)
        && *(_DWORD *)Data == 4 )
      {
        v8 = Type;
        if ( Type > 0x64 )
          v8 = 100;
        dword_1800623B4 = v8;
      }
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"BalancedPercentage48", 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData)
        && *(_DWORD *)Data == 4 )
      {
        v9 = Type;
        if ( Type > 0x64 )
          v9 = 100;
        dword_1800623B8 = v9;
      }
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"BalancedPercentage96", 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData)
        && *(_DWORD *)Data == 4 )
      {
        v10 = Type;
        if ( Type > 0x64 )
          v10 = 100;
        dword_1800623BC = v10;
      }
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"BalancedPercentage256", 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData)
        && *(_DWORD *)Data == 4 )
      {
        v11 = Type;
        if ( Type > 0x64 )
          v11 = 100;
        dword_1800623C0 = v11;
      }
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"BalancedPercentage768", 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData)
        && *(_DWORD *)Data == 4 )
      {
        v12 = Type;
        if ( Type > 0x64 )
          v12 = 100;
        dword_1800623C4 = v12;
      }
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"BalancedPercentage1280", 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData)
        && *(_DWORD *)Data == 4 )
      {
        v13 = Type;
        if ( Type > 0x64 )
          v13 = 100;
        dword_1800623C8 = v13;
      }
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"BalancedPercentage1920", 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData)
        && *(_DWORD *)Data == 4 )
      {
        v14 = Type;
        if ( Type > 0x64 )
          v14 = 100;
        dword_1800623CC = v14;
      }
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"BalancedPercentage2560", 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData)
        && *(_DWORD *)Data == 4 )
      {
        v15 = Type;
        if ( Type > 0x64 )
          v15 = 100;
        dword_1800623D0 = v15;
      }
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"BalancedPercentageWide", 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData)
        && *(_DWORD *)Data == 4 )
      {
        v16 = Type;
        if ( Type > 0x64 )
          v16 = 100;
        dword_1800623D8 = v16;
      }
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"BalancedPercentageWideAlternate", 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData)
        && *(_DWORD *)Data == 4 )
      {
        v17 = Type;
        if ( Type > 0x64 )
          v17 = 100;
        dword_1800623E0 = v17;
      }
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"BalancedPercentageEXIF", 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData)
        && *(_DWORD *)Data == 4 )
      {
        v18 = Type;
        if ( Type > 0x64 )
          v18 = 100;
        dword_1800623DC = v18;
      }
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"BalancedPercentageCustomStream", 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData)
        && *(_DWORD *)Data == 4 )
      {
        v19 = Type;
        if ( Type > 0x64 )
          v19 = 100;
        dword_1800623E4 = v19;
      }
      ReadDWORDRegValue<__int64>(
        (_DWORD)hKey,
        (unsigned int)L"MinCacheFilesSizesWhenShrinking16",
        (unsigned int)qword_1800622D0,
        1,
        1000);
      ReadDWORDRegValue<__int64>(
        (_DWORD)hKey,
        (unsigned int)L"MinCacheFilesSizesWhenShrinking32",
        (unsigned int)&unk_1800622D8,
        1,
        1000);
      ReadDWORDRegValue<__int64>(
        (_DWORD)hKey,
        (unsigned int)L"MinCacheFilesSizesWhenShrinking48",
        (unsigned int)&unk_1800622E0,
        1,
        1000);
      ReadDWORDRegValue<__int64>(
        (_DWORD)hKey,
        (unsigned int)L"MinCacheFilesSizesWhenShrinking96",
        (unsigned int)&unk_1800622E8,
        1,
        1000);
      ReadDWORDRegValue<__int64>(
        (_DWORD)hKey,
        (unsigned int)L"MinCacheFilesSizesWhenShrinking256",
        (unsigned int)&unk_1800622F0,
        1,
        1000);
      ReadDWORDRegValue<__int64>(
        (_DWORD)hKey,
        (unsigned int)L"MinCacheFilesSizesWhenShrinking768",
        (unsigned int)&unk_1800622F8,
        1,
        1000);
      ReadDWORDRegValue<__int64>(
        (_DWORD)hKey,
        (unsigned int)L"MinCacheFilesSizesWhenShrinking1280",
        (unsigned int)&unk_180062300,
        1,
        1000);
      ReadDWORDRegValue<__int64>(
        (_DWORD)hKey,
        (unsigned int)L"MinCacheFilesSizesWhenShrinking1920",
        (unsigned int)&unk_180062308,
        1,
        1000);
      ReadDWORDRegValue<__int64>(
        (_DWORD)hKey,
        (unsigned int)L"MinCacheFilesSizesWhenShrinking2560",
        (unsigned int)&unk_180062310,
        1,
        1000);
      ReadDWORDRegValue<__int64>(
        (_DWORD)hKey,
        (unsigned int)L"MinCacheFilesSizesWhenShrinkingWide",
        (unsigned int)&unk_180062320,
        1,
        1000);
      ReadDWORDRegValue<__int64>(
        (_DWORD)hKey,
        (unsigned int)L"MinCacheFilesSizesWhenShrinkingWideAlternate",
        (unsigned int)&unk_180062330,
        1,
        1000);
      ReadDWORDRegValue<__int64>(
        (_DWORD)hKey,
        (unsigned int)L"MinCacheFilesSizesWhenShrinkingEXIF",
        (unsigned int)&unk_180062328,
        1,
        1000);
      ReadDWORDRegValue<__int64>(
        (_DWORD)hKey,
        (unsigned int)L"MinCacheFilesSizesWhenShrinkingCustomStream",
        (unsigned int)&unk_180062338,
        1,
        1000);
      ReadDWORDRegValue<__int64>(
        (_DWORD)hKey,
        (unsigned int)L"MaxCacheFileSize16",
        (unsigned int)qword_180062340,
        50,
        3995);
      ReadDWORDRegValue<__int64>(
        (_DWORD)hKey,
        (unsigned int)L"MaxCacheFileSize32",
        (unsigned int)&unk_180062348,
        50,
        3995);
      ReadDWORDRegValue<__int64>(
        (_DWORD)hKey,
        (unsigned int)L"MaxCacheFileSize48",
        (unsigned int)&unk_180062350,
        50,
        3995);
      ReadDWORDRegValue<__int64>(
        (_DWORD)hKey,
        (unsigned int)L"MaxCacheFileSize96",
        (unsigned int)&unk_180062358,
        50,
        3995);
      ReadDWORDRegValue<__int64>(
        (_DWORD)hKey,
        (unsigned int)L"MaxCacheFileSize256",
        (unsigned int)&unk_180062360,
        50,
        3995);
      ReadDWORDRegValue<__int64>(
        (_DWORD)hKey,
        (unsigned int)L"MaxCacheFileSize768",
        (unsigned int)&unk_180062368,
        50,
        3995);
      ReadDWORDRegValue<__int64>(
        (_DWORD)hKey,
        (unsigned int)L"MaxCacheFileSize1280",
        (unsigned int)&unk_180062370,
        50,
        3995);
      ReadDWORDRegValue<__int64>(
        (_DWORD)hKey,
        (unsigned int)L"MaxCacheFileSize1920",
        (unsigned int)&unk_180062378,
        50,
        3995);
      ReadDWORDRegValue<__int64>(
        (_DWORD)hKey,
        (unsigned int)L"MaxCacheFileSize2560",
        (unsigned int)&unk_180062380,
        50,
        3995);
      ReadDWORDRegValue<__int64>(
        (_DWORD)hKey,
        (unsigned int)L"MaxCacheFileSize256SlowReclaim",
        (unsigned int)&unk_180062388,
        50,
        3995);
      ReadDWORDRegValue<__int64>(
        (_DWORD)hKey,
        (unsigned int)L"MaxCacheFileSizeWide",
        (unsigned int)&unk_180062390,
        50,
        3995);
      ReadDWORDRegValue<__int64>(
        (_DWORD)hKey,
        (unsigned int)L"MaxCacheFileSizeWideAlternate",
        (unsigned int)&unk_1800623A0,
        50,
        3995);
      ReadDWORDRegValue<__int64>(
        (_DWORD)hKey,
        (unsigned int)L"MaxCacheFileSizeEXIF",
        (unsigned int)&unk_180062398,
        50,
        3995);
      ReadDWORDRegValue<__int64>(
        (_DWORD)hKey,
        (unsigned int)L"MaxCacheFileSizeCustomStream",
        (unsigned int)&unk_1800623A8,
        50,
        3995);
      for ( i = 0; i < 0xE; ++i )
      {
        v5 = qword_1800622D0[i];
        if ( qword_180062340[i] < v5 )
          qword_180062340[i] = v5;
      }
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"MaxUnbalancedPercentage", 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData)
        && *(_DWORD *)Data == 4 )
      {
        v20 = Type;
        if ( Type > 0x64 )
          v20 = 100;
        dword_1800622C4 = v20;
      }
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(
              hKey,
              L"SlowReclaimMaxPercentageOfFreeSpaceForRebalancing",
              0,
              (LPDWORD)Data,
              (LPBYTE)&Type,
              &cbData)
        && *(_DWORD *)Data == 4 )
      {
        v21 = Type;
        if ( Type > 0x64 )
          v21 = 100;
        dword_1800622C8 = v21;
      }
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(
              hKey,
              L"SlowReclaimShrinkIfGreaterThanPercentageOfFreeSpace",
              0,
              (LPDWORD)Data,
              (LPBYTE)&Type,
              &cbData)
        && *(_DWORD *)Data == 4 )
      {
        v22 = Type;
        if ( Type > 0x64 )
          v22 = 100;
        dword_1800622C0 = v22;
      }
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"FastExtractThresholdInMS", 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData)
        && *(_DWORD *)Data == 4 )
      {
        v23 = Type;
        if ( Type > 0x3A98 )
          v23 = 15000;
        dword_180062AD0 = v23;
      }
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"ExtractionTimeoutInMS", 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData)
        && *(_DWORD *)Data == 4 )
      {
        v24 = Type;
        if ( Type >= 0x7530 )
        {
          if ( Type > 0x927C0 )
            v24 = 600000;
          dwMilliseconds = v24;
        }
        else
        {
          dwMilliseconds = 30000;
        }
      }
      RegCloseKey(hKey);
      goto LABEL_3;
    }
    v2 = 1;
LABEL_11:
    dword_1800623E8 = v2;
    goto LABEL_12;
  }
}

```

## disassembly

```asm
0x180016924  push    rbp
0x180016926  push    rbx
0x180016927  push    rsi
0x180016928  push    rdi
0x180016929  push    r12
0x18001692b  push    r13
0x18001692d  push    r14
0x18001692f  push    r15
0x180016931  mov     rbp, rsp
0x180016934  sub     rsp, 58h
0x180016938  mov     rax, cs:__security_cookie
0x18001693f  xor     rax, rsp
0x180016942  mov     [rbp+var_10], rax
0x180016946  xor     r14d, r14d
0x180016949  mov     rbx, rcx
0x18001694c  cmp     [rcx+2F8h], r14d
0x180016953  jnz     short loc_18001698E
0x180016955  lea     rax, [rbp+hKey]
0x180016959  mov     [rbp+hKey], r14
0x18001695d  mov     r9d, 20019h; samDesired
0x180016963  mov     [rsp+58h+phkResult], rax; phkResult
0x180016968  xor     r8d, r8d; ulOptions
0x18001696b  lea     rdx, pszSubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180016972  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180016979  call    cs:__imp_RegOpenKeyExW
0x18001697f  lea     r13d, [r14+1]
0x180016983  test    eax, eax
0x180016985  jz      short loc_1800169AB
0x180016987  mov     [rbx+2F8h], r13d
0x18001698e  mov     rcx, [rbp+var_10]
0x180016992  xor     rcx, rsp; StackCookie
0x180016995  call    __security_check_cookie
0x18001699a  add     rsp, 58h
0x18001699e  pop     r15
0x1800169a0  pop     r14
0x1800169a2  pop     r13
0x1800169a4  pop     r12
0x1800169a6  pop     rdi
0x1800169a7  pop     rsi
0x1800169a8  pop     rbx
0x1800169a9  pop     rbp
0x1800169aa  retn
0x1800169ab  mov     rcx, [rbp+hKey]; hKey
0x1800169af  lea     rax, [rbp+cbData]
0x1800169b3  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800169b8  lea     r9, [rbp+Type]; lpType
0x1800169bc  lea     rax, [rbp+Data]
0x1800169c0  mov     dword ptr [rbp+Data], r14d
0x1800169c4  mov     r15d, 4
0x1800169ca  mov     [rsp+58h+phkResult], rax; lpData
0x1800169cf  xor     r8d, r8d; lpReserved
0x1800169d2  mov     [rbp+Type], r14d
0x1800169d6  lea     rdx, ValueName; "MinFreeSpace"
0x1800169dd  mov     [rbp+cbData], r15d
0x1800169e1  call    cs:__imp_RegQueryValueExW
0x1800169e7  test    eax, eax
0x1800169e9  jz      loc_18001726F
0x1800169ef  mov     rcx, [rbp+hKey]; hKey
0x1800169f3  lea     rax, [rbp+cbData]
0x1800169f7  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800169fc  lea     r9, [rbp+Data]; lpType
0x180016a00  lea     rax, [rbp+Type]
0x180016a04  mov     [rbp+Type], r14d
0x180016a08  xor     r8d, r8d; lpReserved
0x180016a0b  mov     [rsp+58h+phkResult], rax; lpData
0x180016a10  lea     rdx, aMaxpercentageo; "MaxPercentageOfFreeSpaceForRebalancing"
0x180016a17  mov     dword ptr [rbp+Data], r14d
0x180016a1b  mov     [rbp+cbData], r15d
0x180016a1f  call    cs:__imp_RegQueryValueExW
0x180016a25  mov     r12d, 64h ; 'd'
0x180016a2b  test    eax, eax
0x180016a2d  jz      loc_1800172B6
0x180016a33  mov     rcx, [rbp+hKey]; hKey
0x180016a37  lea     rax, [rbp+cbData]
0x180016a3b  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180016a40  lea     r9, [rbp+Data]; lpType
0x180016a44  lea     rax, [rbp+Type]
0x180016a48  mov     [rbp+Type], r14d
0x180016a4c  xor     r8d, r8d; lpReserved
0x180016a4f  mov     [rsp+58h+phkResult], rax; lpData
0x180016a54  lea     rdx, aShrinkifgreate; "ShrinkIfGreaterThanPercentageOfFreeSpac"...
0x180016a5b  mov     dword ptr [rbp+Data], r14d
0x180016a5f  mov     [rbp+cbData], r15d
0x180016a63  call    cs:__imp_RegQueryValueExW
0x180016a69  test    eax, eax
0x180016a6b  jz      loc_1800172D5
0x180016a71  mov     eax, cs:dword_1800623E8
0x180016a77  test    eax, eax
0x180016a79  jnz     short loc_180016A84
0x180016a7b  mov     eax, r13d
0x180016a7e  mov     cs:dword_1800623E8, eax
0x180016a84  mov     ecx, cs:dword_1800623F0
0x180016a8a  test    ecx, ecx
0x180016a8c  jnz     short loc_180016A97
0x180016a8e  mov     ecx, r13d
0x180016a91  mov     cs:dword_1800623F0, ecx
0x180016a97  cmp     eax, ecx
0x180016a99  jnb     short loc_180016AA1
0x180016a9b  mov     cs:dword_1800623F0, eax
0x180016aa1  mov     rcx, [rbp+hKey]; hKey
0x180016aa5  lea     rax, [rbp+cbData]
0x180016aa9  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180016aae  lea     r9, [rbp+Data]; lpType
0x180016ab2  lea     rax, [rbp+Type]
0x180016ab6  mov     [rbp+Type], r14d
0x180016aba  xor     r8d, r8d; lpReserved
0x180016abd  mov     [rsp+58h+phkResult], rax; lpData
0x180016ac2  lea     rdx, aBalancedpercen_8; "BalancedPercentage16"
0x180016ac9  mov     dword ptr [rbp+Data], r14d
0x180016acd  mov     [rbp+cbData], r15d
0x180016ad1  call    cs:__imp_RegQueryValueExW
0x180016ad7  test    eax, eax
0x180016ad9  jz      loc_1800172FA
0x180016adf  mov     rcx, [rbp+hKey]; hKey
0x180016ae3  lea     rax, [rbp+cbData]
0x180016ae7  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180016aec  lea     r9, [rbp+Data]; lpType
0x180016af0  lea     rax, [rbp+Type]
0x180016af4  mov     [rbp+Type], r14d
0x180016af8  xor     r8d, r8d; lpReserved
0x180016afb  mov     [rsp+58h+phkResult], rax; lpData
0x180016b00  lea     rdx, aBalancedpercen_7; "BalancedPercentage32"
0x180016b07  mov     dword ptr [rbp+Data], r14d
0x180016b0b  mov     [rbp+cbData], r15d
0x180016b0f  call    cs:__imp_RegQueryValueExW
0x180016b15  test    eax, eax
0x180016b17  jz      loc_180017319
0x180016b1d  mov     rcx, [rbp+hKey]; hKey
0x180016b21  lea     rax, [rbp+cbData]
0x180016b25  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180016b2a  lea     r9, [rbp+Data]; lpType
0x180016b2e  lea     rax, [rbp+Type]
0x180016b32  mov     [rbp+Type], r14d
0x180016b36  xor     r8d, r8d; lpReserved
0x180016b39  mov     [rsp+58h+phkResult], rax; lpData
0x180016b3e  lea     rdx, aBalancedpercen_9; "BalancedPercentage48"
0x180016b45  mov     dword ptr [rbp+Data], r14d
0x180016b49  mov     [rbp+cbData], r15d
0x180016b4d  call    cs:__imp_RegQueryValueExW
0x180016b53  test    eax, eax
0x180016b55  jz      loc_180017338
0x180016b5b  mov     rcx, [rbp+hKey]; hKey
0x180016b5f  lea     rax, [rbp+cbData]
0x180016b63  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180016b68  lea     r9, [rbp+Data]; lpType
0x180016b6c  lea     rax, [rbp+Type]
0x180016b70  mov     [rbp+Type], r14d
0x180016b74  xor     r8d, r8d; lpReserved
0x180016b77  mov     [rsp+58h+phkResult], rax; lpData
0x180016b7c  lea     rdx, aBalancedpercen_1; "BalancedPercentage96"
0x180016b83  mov     dword ptr [rbp+Data], r14d
0x180016b87  mov     [rbp+cbData], r15d
0x180016b8b  call    cs:__imp_RegQueryValueExW
0x180016b91  test    eax, eax
0x180016b93  jz      loc_180017357
0x180016b99  mov     rcx, [rbp+hKey]; hKey
0x180016b9d  lea     rax, [rbp+cbData]
0x180016ba1  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180016ba6  lea     r9, [rbp+Data]; lpType
0x180016baa  lea     rax, [rbp+Type]
0x180016bae  mov     [rbp+Type], r14d
0x180016bb2  xor     r8d, r8d; lpReserved
0x180016bb5  mov     [rsp+58h+phkResult], rax; lpData
0x180016bba  lea     rdx, aBalancedpercen; "BalancedPercentage256"
0x180016bc1  mov     dword ptr [rbp+Data], r14d
0x180016bc5  mov     [rbp+cbData], r15d
0x180016bc9  call    cs:__imp_RegQueryValueExW
0x180016bcf  test    eax, eax
0x180016bd1  jz      loc_180017376
0x180016bd7  mov     rcx, [rbp+hKey]; hKey
0x180016bdb  lea     rax, [rbp+cbData]
0x180016bdf  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180016be4  lea     r9, [rbp+Data]; lpType
0x180016be8  lea     rax, [rbp+Type]
0x180016bec  mov     [rbp+Type], r14d
0x180016bf0  xor     r8d, r8d; lpReserved
0x180016bf3  mov     [rsp+58h+phkResult], rax; lpData
0x180016bf8  lea     rdx, aBalancedpercen_0; "BalancedPercentage768"
0x180016bff  mov     dword ptr [rbp+Data], r14d
0x180016c03  mov     [rbp+cbData], r15d
0x180016c07  call    cs:__imp_RegQueryValueExW
0x180016c0d  test    eax, eax
0x180016c0f  jz      loc_180017395
0x180016c15  mov     rcx, [rbp+hKey]; hKey
0x180016c19  lea     rax, [rbp+cbData]
0x180016c1d  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180016c22  lea     r9, [rbp+Data]; lpType
0x180016c26  lea     rax, [rbp+Type]
0x180016c2a  mov     [rbp+Type], r14d
0x180016c2e  xor     r8d, r8d; lpReserved
0x180016c31  mov     [rsp+58h+phkResult], rax; lpData
0x180016c36  lea     rdx, aBalancedpercen_6; "BalancedPercentage1280"
0x180016c3d  mov     dword ptr [rbp+Data], r14d
0x180016c41  mov     [rbp+cbData], r15d
0x180016c45  call    cs:__imp_RegQueryValueExW
0x180016c4b  test    eax, eax
0x180016c4d  jz      loc_1800173B4
0x180016c53  mov     rcx, [rbp+hKey]; hKey
0x180016c57  lea     rax, [rbp+cbData]
0x180016c5b  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180016c60  lea     r9, [rbp+Data]; lpType
0x180016c64  lea     rax, [rbp+Type]
0x180016c68  mov     [rbp+Type], r14d
0x180016c6c  xor     r8d, r8d; lpReserved
0x180016c6f  mov     [rsp+58h+phkResult], rax; lpData
0x180016c74  lea     rdx, aBalancedpercen_3; "BalancedPercentage1920"
0x180016c7b  mov     dword ptr [rbp+Data], r14d
0x180016c7f  mov     [rbp+cbData], r15d
0x180016c83  call    cs:__imp_RegQueryValueExW
0x180016c89  test    eax, eax
0x180016c8b  jz      loc_1800173D3
0x180016c91  mov     rcx, [rbp+hKey]; hKey
0x180016c95  lea     rax, [rbp+cbData]
0x180016c99  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180016c9e  lea     r9, [rbp+Data]; lpType
0x180016ca2  lea     rax, [rbp+Type]
0x180016ca6  mov     [rbp+Type], r14d
0x180016caa  xor     r8d, r8d; lpReserved
0x180016cad  mov     [rsp+58h+phkResult], rax; lpData
0x180016cb2  lea     rdx, aBalancedpercen_10; "BalancedPercentage2560"
0x180016cb9  mov     dword ptr [rbp+Data], r14d
0x180016cbd  mov     [rbp+cbData], r15d
0x180016cc1  call    cs:__imp_RegQueryValueExW
0x180016cc7  test    eax, eax
0x180016cc9  jz      loc_1800173F2
0x180016ccf  mov     rcx, [rbp+hKey]; hKey
0x180016cd3  lea     rax, [rbp+cbData]
0x180016cd7  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180016cdc  lea     r9, [rbp+Data]; lpType
0x180016ce0  lea     rax, [rbp+Type]
0x180016ce4  mov     [rbp+Type], r14d
0x180016ce8  xor     r8d, r8d; lpReserved
0x180016ceb  mov     [rsp+58h+phkResult], rax; lpData
0x180016cf0  lea     rdx, aBalancedpercen_4; "BalancedPercentageWide"
0x180016cf7  mov     dword ptr [rbp+Data], r14d
0x180016cfb  mov     [rbp+cbData], r15d
0x180016cff  call    cs:__imp_RegQueryValueExW
0x180016d05  test    eax, eax
0x180016d07  jz      loc_180017411
0x180016d0d  mov     rcx, [rbp+hKey]; hKey
0x180016d11  lea     rax, [rbp+cbData]
0x180016d15  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180016d1a  lea     r9, [rbp+Data]; lpType
0x180016d1e  lea     rax, [rbp+Type]
0x180016d22  mov     [rbp+Type], r14d
0x180016d26  xor     r8d, r8d; lpReserved
0x180016d29  mov     [rsp+58h+phkResult], rax; lpData
0x180016d2e  lea     rdx, aBalancedpercen_11; "BalancedPercentageWideAlternate"
0x180016d35  mov     dword ptr [rbp+Data], r14d
0x180016d39  mov     [rbp+cbData], r15d
0x180016d3d  call    cs:__imp_RegQueryValueExW
0x180016d43  test    eax, eax
0x180016d45  jz      loc_180017430
0x180016d4b  mov     rcx, [rbp+hKey]; hKey
0x180016d4f  lea     rax, [rbp+cbData]
0x180016d53  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180016d58  lea     r9, [rbp+Data]; lpType
0x180016d5c  lea     rax, [rbp+Type]
0x180016d60  mov     [rbp+Type], r14d
0x180016d64  xor     r8d, r8d; lpReserved
0x180016d67  mov     [rsp+58h+phkResult], rax; lpData
0x180016d6c  lea     rdx, aBalancedpercen_2; "BalancedPercentageEXIF"
0x180016d73  mov     dword ptr [rbp+Data], r14d
0x180016d77  mov     [rbp+cbData], r15d
0x180016d7b  call    cs:__imp_RegQueryValueExW
0x180016d81  test    eax, eax
0x180016d83  jz      loc_18001744F
0x180016d89  mov     rcx, [rbp+hKey]; hKey
0x180016d8d  lea     rax, [rbp+cbData]
0x180016d91  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180016d96  lea     r9, [rbp+Data]; lpType
0x180016d9a  lea     rax, [rbp+Type]
0x180016d9e  mov     [rbp+Type], r14d
0x180016da2  xor     r8d, r8d; lpReserved
0x180016da5  mov     [rsp+58h+phkResult], rax; lpData
0x180016daa  lea     rdx, aBalancedpercen_5; "BalancedPercentageCustomStream"
0x180016db1  mov     dword ptr [rbp+Data], r14d
0x180016db5  mov     [rbp+cbData], r15d
0x180016db9  call    cs:__imp_RegQueryValueExW
0x180016dbf  test    eax, eax
0x180016dc1  jz      loc_18001746E
0x180016dc7  mov     rcx, [rbp+hKey]
0x180016dcb  lea     r8, qword_1800622D0
0x180016dd2  mov     edi, 3E8h
0x180016dd7  lea     rdx, aMincachefiless_3; "MinCacheFilesSizesWhenShrinking16"
0x180016dde  mov     r9d, r13d
0x180016de1  mov     dword ptr [rsp+58h+phkResult], edi
0x180016de5  call    ??$ReadDWORDRegValue@_J@@YAXPEAUHKEY__@@PEBGPEA_JKKH@Z; ReadDWORDRegValue<__int64>(HKEY__ *,ushort const *,__int64 *,ulong,ulong,int)
0x180016dea  mov     rcx, [rbp+hKey]
0x180016dee  lea     r8, unk_1800622D8
0x180016df5  mov     r9d, r13d
0x180016df8  mov     dword ptr [rsp+58h+phkResult], edi
0x180016dfc  lea     rdx, aMincachefiless_11; "MinCacheFilesSizesWhenShrinking32"
0x180016e03  call    ??$ReadDWORDRegValue@_J@@YAXPEAUHKEY__@@PEBGPEA_JKKH@Z; ReadDWORDRegValue<__int64>(HKEY__ *,ushort const *,__int64 *,ulong,ulong,int)
0x180016e08  mov     rcx, [rbp+hKey]
0x180016e0c  lea     r8, unk_1800622E0
0x180016e13  mov     r9d, r13d
0x180016e16  mov     dword ptr [rsp+58h+phkResult], edi
0x180016e1a  lea     rdx, aMincachefiless; "MinCacheFilesSizesWhenShrinking48"
0x180016e21  call    ??$ReadDWORDRegValue@_J@@YAXPEAUHKEY__@@PEBGPEA_JKKH@Z; ReadDWORDRegValue<__int64>(HKEY__ *,ushort const *,__int64 *,ulong,ulong,int)
  ... truncated ...
```
