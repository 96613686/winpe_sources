# CacheMetadataStorage::GetUrlCacheEntryInfo(RegistryHelper *,CacheEntry &)

- ea: `0x1800307d0`
- end: `0x180030d53`
- name: `?GetUrlCacheEntryInfo@CacheMetadataStorage@@AEAAJPEAVRegistryHelper@@AEAVCacheEntry@@@Z`
- size: `1411`
- prototype: `__int64 __fastcall(CacheMetadataStorage *__hidden this, struct RegistryHelper *, struct CacheEntry *)`
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c5a4`
- `0x18002cfc0`
- `0x18006121c`
- `0x180080548`
- `0x180081048`

## callees

- `0x18002e450`
- `0x18002e730`
- `0x18002ee38`
- `0x1800307d0`
- `0x180030d60`
- `0x1800a0b2c`
- `0x1800b99f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800308c4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003092c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800309ae`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030a03`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030a64`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800308c4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003092c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800309ae`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030a03`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030a64`

## string_xrefs

- `0x180030b01`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\cachemetadatastorage.cpp`
- `0x180030bc4`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\cachemetadatastorage.cpp`
- `0x180030bf5`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\cachemetadatastorage.cpp`
- `0x180030c26`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\cachemetadatastorage.cpp`
- `0x180030c7f`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\cachemetadatastorage.cpp`
- `0x180030c9f`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\cachemetadatastorage.cpp`
- `0x180030cf9`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\cachemetadatastorage.cpp`
- `0x180030d19`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\cachemetadatastorage.cpp`
- `0x180030b34`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\cachemetadatastorage.cpp`
- `0x180030ccc`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\cachemetadatastorage.cpp`
- `0x18003095f`: `LocalPath`
- `0x180030b47`: `CacheMetadataStorage::GetUrlCacheEntryInfo`
- `0x180030cc5`: `CacheMetadataStorage::GetUrlCacheEntryInfo`

## pseudocode

```c
__int64 __fastcall CacheMetadataStorage::GetUrlCacheEntryInfo(
        CacheMetadataStorage *this,
        HKEY *a2,
        struct CacheEntry *a3)
{
  struct CacheEntry *v5; // rcx
  _WORD *v6; // rcx
  BYTE *v7; // r13
  BYTE *v8; // r15
  BYTE *v9; // r12
  int StringValue; // eax
  unsigned int v11; // ebx
  int v12; // eax
  HKEY v13; // rcx
  LSTATUS v14; // eax
  __int64 v15; // rcx
  HKEY v16; // rcx
  LSTATUS v17; // eax
  int v18; // eax
  __int64 v19; // rcx
  LSTATUS v20; // eax
  __int64 v21; // rcx
  HKEY v22; // rcx
  LSTATUS v23; // eax
  __int64 v24; // rcx
  LSTATUS v25; // eax
  __int64 v26; // rcx
  unsigned int v28; // ecx
  int v29; // r9d
  int lpData; // [rsp+20h] [rbp-69h]
  int lpDataa; // [rsp+20h] [rbp-69h]
  int lpDatab; // [rsp+20h] [rbp-69h]
  int lpDatac; // [rsp+20h] [rbp-69h]
  int lpDatad; // [rsp+20h] [rbp-69h]
  int lpDatae; // [rsp+20h] [rbp-69h]
  DWORD cbData; // [rsp+30h] [rbp-59h] BYREF
  DWORD Type; // [rsp+38h] [rbp-51h] BYREF
  const unsigned __int16 *v38; // [rsp+50h] [rbp-39h]
  __int64 v39; // [rsp+58h] [rbp-31h]
  const unsigned __int16 *v40; // [rsp+60h] [rbp-29h]
  __int64 v41; // [rsp+68h] [rbp-21h]
  DWORD *p_Type; // [rsp+70h] [rbp-19h]
  __int64 v43; // [rsp+78h] [rbp-11h]
  DWORD *p_cbData; // [rsp+80h] [rbp-9h]
  __int64 v45; // [rsp+88h] [rbp-1h]
  const WCHAR *v46; // [rsp+90h] [rbp+7h]
  __int64 v47; // [rsp+98h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  *((_QWORD *)a3 + 2) = 0;
  if ( *((_QWORD *)a3 + 3) <= 7u )
    v5 = a3;
  else
    v5 = *(struct CacheEntry **)a3;
  *(_WORD *)v5 = 0;
  *((_QWORD *)a3 + 6) = 0;
  if ( *((_QWORD *)a3 + 7) <= 7u )
    v6 = (_WORD *)((char *)a3 + 32);
  else
    v6 = (_WORD *)*((_QWORD *)a3 + 4);
  *v6 = 0;
  v7 = (BYTE *)a3 + 116;
  *((_DWORD *)a3 + 28) = 0;
  v8 = (BYTE *)a3 + 104;
  *((_DWORD *)a3 + 26) = 0;
  v9 = (BYTE *)a3 + 108;
  *((_DWORD *)a3 + 27) = 0;
  *(_OWORD *)((char *)a3 + 116) = 0;
  *(_QWORD *)((char *)a3 + 132) = 0;
  StringValue = RegistryHelper::ReadStringValue(a2, L"Url", (char *)a3 + 64);
  v11 = StringValue;
  if ( StringValue < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x13E,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\cachemetadatastorage.cpp",
      (const char *)(unsigned int)StringValue,
      lpData);
    if ( (Microsoft_Windows_PushNotifications_PlatformEnableBits & 1) == 0 )
      return v11;
    Type = 318;
    goto LABEL_47;
  }
  v12 = RegistryHelper::ReadStringValue(a2, L"Aumid", a3);
  v11 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x141,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\cachemetadatastorage.cpp",
      (const char *)(unsigned int)v12,
      lpData);
    if ( (Microsoft_Windows_PushNotifications_PlatformEnableBits & 1) == 0 )
      return v11;
    Type = 321;
    goto LABEL_47;
  }
  Type = 0;
  cbData = 0;
  if ( !a2[1] )
    MicrosoftTelemetryAssertTriggeredNoArgs(0);
  v13 = a2[1];
  cbData = 4;
  v14 = RegQueryValueExW(v13, L"FileSize", 0, &Type, v8, &cbData);
  v11 = v14;
  if ( v14 )
  {
    if ( v14 <= 0 )
      goto LABEL_12;
    goto LABEL_42;
  }
  if ( Type != 4 || cbData != 4 )
  {
    LOWORD(v11) = 1012;
LABEL_42:
    v11 = (unsigned __int16)v11 | 0x80070000;
  }
LABEL_12:
  if ( (v11 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x144,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\cachemetadatastorage.cpp",
      (const char *)v11,
      lpDataa);
    v29 = 324;
LABEL_59:
    WpnDebugTrace(
      v28,
      L"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\cachemetadatastorage.cpp",
      L"CacheMetadataStorage::GetUrlCacheEntryInfo",
      v29,
      v11,
      &word_180124798);
    return v11;
  }
  Type = 0;
  cbData = 0;
  if ( !a2[1] )
    MicrosoftTelemetryAssertTriggeredNoArgs(v15);
  v16 = a2[1];
  cbData = 4;
  v17 = RegQueryValueExW(v16, L"Flag", 0, &Type, v9, &cbData);
  v11 = v17;
  if ( v17 )
  {
    if ( v17 <= 0 )
      goto LABEL_18;
    goto LABEL_44;
  }
  if ( Type != 4 || cbData != 4 )
  {
    LOWORD(v11) = 1012;
LABEL_44:
    v11 = (unsigned __int16)v11 | 0x80070000;
  }
LABEL_18:
  if ( (v11 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x147,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\cachemetadatastorage.cpp",
      (const char *)v11,
      lpDatab);
    v29 = 327;
    goto LABEL_59;
  }
  v18 = RegistryHelper::ReadStringValue(a2, L"LocalPath", (char *)a3 + 32);
  v11 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x14A,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\cachemetadatastorage.cpp",
      (const char *)(unsigned int)v18,
      lpDatab);
    if ( (Microsoft_Windows_PushNotifications_PlatformEnableBits & 1) == 0 )
      return v11;
    Type = 330;
LABEL_47:
    cbData = v11;
    p_Type = &Type;
    v38 = L"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\cachemetadatastorage.cpp";
    p_cbData = &cbData;
    v39 = 172;
    v46 = &word_180124798;
    v40 = L"CacheMetadataStorage::GetUrlCacheEntryInfo";
    v41 = 86;
    v43 = 4;
    v45 = 4;
    v47 = 2;
    McGenEventWrite_EventWriteTransfer(
      &WPNCORE_PROVIDER_GUID_Context,
      WPNCORE_EVENT_DEBUG,
      L"CacheMetadataStorage::GetUrlCacheEntryInfo",
      6);
    return v11;
  }
  Type = 8;
  cbData = 0;
  if ( !a2[1] )
    MicrosoftTelemetryAssertTriggeredNoArgs(v19);
  v20 = RegQueryValueExW(a2[1], L"Expiration", 0, &cbData, (LPBYTE)a3 + 96, &Type);
  v11 = v20;
  if ( v20 > 0 )
    v11 = (unsigned __int16)v20 | 0x80070000;
  if ( (v11 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x14D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\cachemetadatastorage.cpp",
      (const char *)v11,
      lpDatac);
    v29 = 333;
    goto LABEL_59;
  }
  Type = 0;
  cbData = 0;
  if ( !a2[1] )
    MicrosoftTelemetryAssertTriggeredNoArgs(v21);
  v22 = a2[1];
  cbData = 4;
  v23 = RegQueryValueExW(v22, L"NotificationsCount", 0, &Type, (LPBYTE)a3 + 112, &cbData);
  v11 = v23;
  if ( v23 )
  {
    if ( v23 <= 0 )
      goto LABEL_30;
    goto LABEL_49;
  }
  if ( Type != 4 || cbData != 4 )
  {
    LOWORD(v11) = 1012;
LABEL_49:
    v11 = (unsigned __int16)v11 | 0x80070000;
  }
LABEL_30:
  if ( (v11 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x150,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\cachemetadatastorage.cpp",
      (const char *)v11,
      lpDatad);
    if ( (Microsoft_Windows_PushNotifications_PlatformEnableBits & 1) == 0 )
      return v11;
    Type = 336;
    goto LABEL_47;
  }
  Type = 24;
  cbData = 0;
  if ( !a2[1] )
    MicrosoftTelemetryAssertTriggeredNoArgs(v24);
  v25 = RegQueryValueExW(a2[1], L"Notifications", 0, &cbData, v7, &Type);
  v11 = v25;
  if ( v25 > 0 )
    v11 = (unsigned __int16)v25 | 0x80070000;
  if ( (v11 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x158,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\cachemetadatastorage.cpp",
      (const char *)v11,
      lpDatae);
    v29 = 344;
    goto LABEL_59;
  }
  if ( Type != 24 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v26);
  return v11;
}

```

## disassembly

```asm
0x1800307d0  mov     [rsp-8+arg_0], rbx
0x1800307d5  push    rbp
0x1800307d6  push    rsi
0x1800307d7  push    rdi
0x1800307d8  push    r12
0x1800307da  push    r13
0x1800307dc  push    r14
0x1800307de  push    r15
0x1800307e0  lea     rbp, [rsp-27h]
0x1800307e5  sub     rsp, 0B0h
0x1800307ec  mov     rax, cs:__security_cookie
0x1800307f3  xor     rax, rsp
0x1800307f6  mov     [rbp+57h+var_40], rax
0x1800307fa  mov     rsi, rdx
0x1800307fd  mov     rdi, r8
0x180030800  xor     edx, edx
0x180030802  mov     [r8+10h], rdx
0x180030806  cmp     qword ptr [r8+18h], 7
0x18003080b  jbe     loc_180030AAB
0x180030811  mov     rcx, [r8]
0x180030814  mov     [rcx], dx
0x180030817  mov     [r8+30h], rdx
0x18003081b  cmp     qword ptr [r8+38h], 7
0x180030820  jbe     loc_180030AB3
0x180030826  mov     rcx, [r8+20h]
0x18003082a  mov     [rcx], dx
0x18003082d  lea     r13, [r8+74h]
0x180030831  mov     [r8+70h], edx
0x180030835  lea     r15, [r8+68h]
0x180030839  mov     [r15], edx
0x18003083c  lea     r12, [r8+6Ch]
0x180030840  mov     [r12], edx
0x180030844  xorps   xmm0, xmm0
0x180030847  xor     eax, eax
0x180030849  lea     rdx, aUrl; "Url"
0x180030850  movups  xmmword ptr [r13+0], xmm0
0x180030855  add     r8, 40h ; '@'
0x180030859  mov     [r13+10h], rax
0x18003085d  mov     rcx, rsi
0x180030860  call    ?ReadStringValue@RegistryHelper@@QEAAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegistryHelper::ReadStringValue(ushort const *,std::wstring &)
0x180030865  mov     ebx, eax
0x180030867  test    eax, eax
0x180030869  js      loc_180030BC0
0x18003086f  mov     r8, rdi
0x180030872  lea     rdx, aAumid; "Aumid"
0x180030879  mov     rcx, rsi
0x18003087c  call    ?ReadStringValue@RegistryHelper@@QEAAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegistryHelper::ReadStringValue(ushort const *,std::wstring &)
0x180030881  mov     ebx, eax
0x180030883  test    eax, eax
0x180030885  js      loc_180030BF1
0x18003088b  xor     ecx, ecx
0x18003088d  mov     [rbp+57h+Type], ecx
0x180030890  mov     [rbp+57h+cbData], ecx
0x180030893  cmp     [rsi+8], rcx
0x180030897  jz      loc_180030C67
0x18003089d  mov     rcx, [rsi+8]; hKey
0x1800308a1  lea     rax, [rbp+57h+cbData]
0x1800308a5  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x1800308aa  lea     r9, [rbp+57h+Type]; lpType
0x1800308ae  xor     r8d, r8d; lpReserved
0x1800308b1  mov     [rsp+0E0h+lpData], r15; int
0x1800308b6  lea     rdx, aFilesize; "FileSize"
0x1800308bd  mov     [rbp+57h+cbData], 4
0x1800308c4  call    cs:__imp_RegQueryValueExW
0x1800308ca  mov     ebx, eax
0x1800308cc  test    eax, eax
0x1800308ce  jnz     loc_180030AD5
0x1800308d4  cmp     [rbp+57h+Type], 4
0x1800308d8  jnz     loc_180030C71
0x1800308de  cmp     [rbp+57h+cbData], 4
0x1800308e2  jnz     loc_180030C71
0x1800308e8  test    ebx, ebx
0x1800308ea  js      loc_180030C7B
0x1800308f0  xor     r15d, r15d
0x1800308f3  mov     [rbp+57h+Type], r15d
0x1800308f7  mov     [rbp+57h+cbData], r15d
0x1800308fb  cmp     [rsi+8], r15
0x1800308ff  jz      loc_180030CE1
0x180030905  mov     rcx, [rsi+8]; hKey
0x180030909  lea     rax, [rbp+57h+cbData]
0x18003090d  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x180030912  lea     r9, [rbp+57h+Type]; lpType
0x180030916  xor     r8d, r8d; lpReserved
0x180030919  mov     [rsp+0E0h+lpData], r12; int
0x18003091e  lea     rdx, aFlag; "Flag"
0x180030925  mov     [rbp+57h+cbData], 4
0x18003092c  call    cs:__imp_RegQueryValueExW
0x180030932  mov     ebx, eax
0x180030934  test    eax, eax
0x180030936  jnz     loc_180030AE9
0x18003093c  cmp     [rbp+57h+Type], 4
0x180030940  jnz     loc_180030CEB
0x180030946  cmp     [rbp+57h+cbData], 4
0x18003094a  jnz     loc_180030CEB
0x180030950  test    ebx, ebx
0x180030952  js      loc_180030CF5
0x180030958  lea     r8, [rdi+20h]
0x18003095c  mov     rcx, rsi
0x18003095f  lea     rdx, aLocalpath; "LocalPath"
0x180030966  call    ?ReadStringValue@RegistryHelper@@QEAAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegistryHelper::ReadStringValue(ushort const *,std::wstring &)
0x18003096b  mov     ebx, eax
0x18003096d  test    eax, eax
0x18003096f  js      loc_180030AFD
0x180030975  mov     [rbp+57h+Type], 8
0x18003097c  mov     [rbp+57h+cbData], r15d
0x180030980  cmp     [rsi+8], r15
0x180030984  jz      loc_180030C53
0x18003098a  lea     rcx, [rbp+57h+Type]
0x18003098e  xor     r8d, r8d; lpReserved
0x180030991  mov     [rsp+0E0h+lpcbData], rcx; lpcbData
0x180030996  lea     rax, [rdi+60h]
0x18003099a  mov     rcx, [rsi+8]; hKey
0x18003099e  lea     r9, [rbp+57h+cbData]; lpType
0x1800309a2  lea     rdx, aExpiration; "Expiration"
0x1800309a9  mov     [rsp+0E0h+lpData], rax; int
0x1800309ae  call    cs:__imp_RegQueryValueExW
0x1800309b4  mov     ebx, eax
0x1800309b6  test    eax, eax
0x1800309b8  jg      loc_180030ABC
0x1800309be  test    ebx, ebx
0x1800309c0  js      loc_180030D15
0x1800309c6  mov     [rbp+57h+Type], r15d
0x1800309ca  mov     [rbp+57h+cbData], r15d
0x1800309ce  cmp     [rsi+8], r15
0x1800309d2  jz      loc_180030D35
0x1800309d8  mov     rcx, [rsi+8]; hKey
0x1800309dc  lea     rax, [rbp+57h+cbData]
0x1800309e0  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x1800309e5  lea     r9, [rbp+57h+Type]; lpType
0x1800309e9  lea     rax, [rdi+70h]
0x1800309ed  mov     [rbp+57h+cbData], 4
0x1800309f4  xor     r8d, r8d; lpReserved
0x1800309f7  mov     [rsp+0E0h+lpData], rax; int
0x1800309fc  lea     rdx, aNotificationsc; "NotificationsCount"
0x180030a03  call    cs:__imp_RegQueryValueExW
0x180030a09  mov     ebx, eax
0x180030a0b  test    eax, eax
0x180030a0d  jnz     loc_180030BAC
0x180030a13  cmp     [rbp+57h+Type], 4
0x180030a17  jnz     loc_180030D3F
0x180030a1d  cmp     [rbp+57h+cbData], 4
0x180030a21  jnz     loc_180030D3F
0x180030a27  test    ebx, ebx
0x180030a29  js      loc_180030C22
0x180030a2f  mov     [rbp+57h+Type], 18h
0x180030a36  mov     [rbp+57h+cbData], r15d
0x180030a3a  cmp     [rsi+8], r15
0x180030a3e  jz      loc_180030C5D
0x180030a44  mov     rcx, [rsi+8]; hKey
0x180030a48  lea     rax, [rbp+57h+Type]
0x180030a4c  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x180030a51  lea     r9, [rbp+57h+cbData]; lpType
0x180030a55  xor     r8d, r8d; lpReserved
0x180030a58  mov     [rsp+0E0h+lpData], r13; int
0x180030a5d  lea     rdx, aNotifications; "Notifications"
0x180030a64  call    cs:__imp_RegQueryValueExW
0x180030a6a  mov     ebx, eax
0x180030a6c  test    eax, eax
0x180030a6e  jg      short loc_180030ACA
0x180030a70  test    ebx, ebx
0x180030a72  js      loc_180030C9B
0x180030a78  cmp     [rbp+57h+Type], 18h
0x180030a7c  jnz     loc_180030D49
0x180030a82  mov     eax, ebx
0x180030a84  mov     rcx, [rbp+57h+var_40]
0x180030a88  xor     rcx, rsp; StackCookie
0x180030a8b  call    __security_check_cookie
0x180030a90  mov     rbx, [rsp+0E0h+arg_0]
0x180030a98  add     rsp, 0B0h
0x180030a9f  pop     r15
0x180030aa1  pop     r14
0x180030aa3  pop     r13
0x180030aa5  pop     r12
0x180030aa7  pop     rdi
0x180030aa8  pop     rsi
0x180030aa9  pop     rbp
0x180030aaa  retn
0x180030aab  mov     rcx, rdi
0x180030aae  jmp     loc_180030814
0x180030ab3  lea     rcx, [r8+20h]
0x180030ab7  jmp     loc_18003082A
0x180030abc  movzx   ebx, ax
0x180030abf  or      ebx, 80070000h
0x180030ac5  jmp     loc_1800309BE
0x180030aca  movzx   ebx, ax
0x180030acd  or      ebx, 80070000h
0x180030ad3  jmp     short loc_180030A70
0x180030ad5  jle     loc_1800308E8
0x180030adb  movzx   ebx, bx
0x180030ade  or      ebx, 80070000h
0x180030ae4  jmp     loc_1800308E8
0x180030ae9  jle     loc_180030950
0x180030aef  movzx   ebx, bx
0x180030af2  or      ebx, 80070000h
0x180030af8  jmp     loc_180030950
0x180030afd  mov     rcx, [rbp+5Fh]; this
0x180030b01  lea     r8, aOnecoreuapBase_76; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180030b08  mov     r9d, ebx; char *
0x180030b0b  mov     edx, 14Ah; void *
0x180030b10  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180030b15  test    cs:Microsoft_Windows_PushNotifications_PlatformEnableBits, 1
0x180030b1c  jz      loc_180030A82
0x180030b22  mov     [rbp+57h+Type], 14Ah
0x180030b29  lea     rax, [rbp+57h+Type]
0x180030b2d  mov     [rbp+57h+cbData], ebx
0x180030b30  mov     [rbp+57h+var_70], rax
0x180030b34  lea     rdx, aOnecoreuapBase_95; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180030b3b  lea     rax, [rbp+57h+cbData]
0x180030b3f  mov     [rbp+57h+var_90], rdx
0x180030b43  mov     [rbp+57h+var_60], rax
0x180030b47  lea     r8, aCachemetadatas_5; "CacheMetadataStorage::GetUrlCacheEntryI"...
0x180030b4e  lea     rax, word_180124798
0x180030b55  mov     [rbp+57h+var_88], 0ACh
0x180030b5d  mov     [rbp+57h+var_50], rax
0x180030b61  lea     rdx, WPNCORE_EVENT_DEBUG
0x180030b68  lea     rax, [rbp+57h+var_A0]
0x180030b6c  mov     [rbp+57h+var_80], r8
0x180030b70  mov     r9d, 6
0x180030b76  mov     [rsp+0E0h+lpData], rax
0x180030b7b  lea     rcx, WPNCORE_PROVIDER_GUID_Context
0x180030b82  mov     [rbp+57h+var_78], 56h ; 'V'
0x180030b8a  mov     [rbp+57h+var_68], 4
0x180030b92  mov     [rbp+57h+var_58], 4
0x180030b9a  mov     [rbp+57h+var_48], 2
0x180030ba2  call    McGenEventWrite_EventWriteTransfer
0x180030ba7  jmp     loc_180030A82
0x180030bac  jle     loc_180030A27
0x180030bb2  movzx   ebx, bx
0x180030bb5  or      ebx, 80070000h
0x180030bbb  jmp     loc_180030A27
0x180030bc0  mov     rcx, [rbp+5Fh]; this
0x180030bc4  lea     r8, aOnecoreuapBase_76; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180030bcb  mov     r9d, ebx; char *
0x180030bce  mov     edx, 13Eh; void *
0x180030bd3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180030bd8  test    cs:Microsoft_Windows_PushNotifications_PlatformEnableBits, 1
0x180030bdf  jz      loc_180030A82
0x180030be5  mov     [rbp+57h+Type], 13Eh
0x180030bec  jmp     loc_180030B29
0x180030bf1  mov     rcx, [rbp+5Fh]; this
0x180030bf5  lea     r8, aOnecoreuapBase_76; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180030bfc  mov     r9d, ebx; char *
0x180030bff  mov     edx, 141h; void *
0x180030c04  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180030c09  test    cs:Microsoft_Windows_PushNotifications_PlatformEnableBits, 1
0x180030c10  jz      loc_180030A82
0x180030c16  mov     [rbp+57h+Type], 141h
0x180030c1d  jmp     loc_180030B29
0x180030c22  mov     rcx, [rbp+5Fh]; this
0x180030c26  lea     r8, aOnecoreuapBase_76; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180030c2d  mov     r9d, ebx; char *
0x180030c30  mov     edx, 150h; void *
0x180030c35  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180030c3a  test    cs:Microsoft_Windows_PushNotifications_PlatformEnableBits, 1
0x180030c41  jz      loc_180030A82
0x180030c47  mov     [rbp+57h+Type], 150h
0x180030c4e  jmp     loc_180030B29
0x180030c53  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "this->m_key != nullptr")
0x180030c58  jmp     loc_18003098A
0x180030c5d  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "this->m_key != nullptr")
0x180030c62  jmp     loc_180030A44
0x180030c67  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "this->m_key != nullptr")
0x180030c6c  jmp     loc_18003089D
0x180030c71  mov     ebx, 3F4h
0x180030c76  jmp     loc_180030ADB
0x180030c7b  mov     rcx, [rbp+5Fh]; this
0x180030c7f  lea     r8, aOnecoreuapBase_76; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180030c86  mov     r9d, ebx; char *
0x180030c89  mov     edx, 144h; void *
0x180030c8e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180030c93  mov     r9d, 144h
0x180030c99  jmp     short loc_180030CB9
0x180030c9b  mov     rcx, [rbp+5Fh]; this
0x180030c9f  lea     r8, aOnecoreuapBase_76; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180030ca6  mov     r9d, ebx; char *
0x180030ca9  mov     edx, 158h; void *
0x180030cae  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180030cb3  mov     r9d, 158h; int
0x180030cb9  lea     rax, word_180124798
0x180030cc0  mov     [rsp+0E0h+lpcbData], rax; unsigned __int16 *
0x180030cc5  lea     r8, aCachemetadatas_5; "CacheMetadataStorage::GetUrlCacheEntryI"...
0x180030ccc  lea     rdx, aOnecoreuapBase_95; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180030cd3  mov     dword ptr [rsp+0E0h+lpData], ebx; int
0x180030cd7  call    ?WpnDebugTrace@@YAXKPEBG0HJ0@Z; WpnDebugTrace(ulong,ushort const *,ushort const *,int,long,ushort const *)
0x180030cdc  jmp     loc_180030A82
0x180030ce1  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "this->m_key != nullptr")
0x180030ce6  jmp     loc_180030905
0x180030ceb  mov     ebx, 3F4h
0x180030cf0  jmp     loc_180030AEF
0x180030cf5  mov     rcx, [rbp+5Fh]; this
0x180030cf9  lea     r8, aOnecoreuapBase_76; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180030d00  mov     r9d, ebx; char *
0x180030d03  mov     edx, 147h; void *
0x180030d08  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180030d0d  mov     r9d, 147h
0x180030d13  jmp     short loc_180030CB9
0x180030d15  mov     rcx, [rbp+5Fh]; this
0x180030d19  lea     r8, aOnecoreuapBase_76; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180030d20  mov     r9d, ebx; char *
0x180030d23  mov     edx, 14Dh; void *
  ... truncated ...
```
