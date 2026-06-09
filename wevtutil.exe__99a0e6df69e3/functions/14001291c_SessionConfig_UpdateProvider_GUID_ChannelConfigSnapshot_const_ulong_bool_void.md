# SessionConfig::UpdateProvider(_GUID,ChannelConfigSnapshot const &,ulong,bool,void *)

- ea: `0x14001291c`
- end: `0x140013652`
- name: `?UpdateProvider@SessionConfig@@CAXU_GUID@@AEBVChannelConfigSnapshot@@K_NPEAX@Z`
- size: `3382`
- prototype: `void __fastcall(struct _GUID *, const struct ChannelConfigSnapshot *, unsigned int, bool, void *)`
- caller_count: `3`
- callee_count: `22`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140013658`
- `0x14002d8e4`
- `0x14002daf0`

## callees

- `0x140003700`
- `0x140004ae0`
- `0x140005600`
- `0x140005a80`
- `0x140006db0`
- `0x140007fd0`
- `0x14000a4d8`
- `0x14000b6d0`
- `0x14000d6e8`
- `0x14001291c`
- `0x140014960`
- `0x14001a9b8`
- `0x14001b5b4`
- `0x14001b668`
- `0x140021b00`
- `0x140022cec`
- `0x14002e8ac`
- `0x14002eae0`
- `0x14002f0d8`
- `0x14002f6c8`
- `0x140031810`
- `0x14003181c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012eeb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012f00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012eeb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012f00`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140012d99`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140012d99`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140012ea2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140012ea2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140013074`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001311e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001327d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140013324`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400133c4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140013473`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140013074`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001311e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001327d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140013324`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400133c4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140013473`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall SessionConfig::UpdateProvider(
        struct _GUID *a1,
        const struct ChannelConfigSnapshot *a2,
        unsigned int a3,
        char a4,
        void *a5)
{
  HKEY v8; // rdi
  __int64 v9; // rbx
  const char *v10; // r8
  const char *v11; // r8
  __int64 v12; // r8
  int v13; // eax
  int v14; // esi
  __int64 v15; // rcx
  int AutoLoggersRegPath; // eax
  int v17; // esi
  const char *v18; // r8
  HKEY *v19; // rax
  unsigned int RegKey; // r15d
  HKEY v21; // rax
  const char *v22; // r8
  HKEY *v23; // rax
  __int64 v24; // r13
  __int64 v25; // rbx
  char v26; // dl
  __int64 v27; // rbx
  unsigned __int64 v28; // rbx
  __int64 v29; // rcx
  unsigned __int8 v30; // si
  HKEY v31; // r10
  int v32; // edx
  int v33; // r8d
  HKEY *v34; // rax
  void *v35; // r15
  unsigned int v36; // eax
  unsigned int v37; // esi
  unsigned int v38; // eax
  unsigned int v39; // esi
  unsigned int v40; // eax
  unsigned int v41; // esi
  unsigned int v42; // eax
  unsigned int v43; // esi
  unsigned int v44; // eax
  unsigned int v45; // esi
  unsigned int v46; // eax
  unsigned int v47; // esi
  unsigned int v48; // eax
  unsigned int v49; // esi
  unsigned int v50; // eax
  unsigned int v51; // esi
  __int16 *pExceptionObject; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v54; // [rsp+50h] [rbp-B0h]
  __int64 v55; // [rsp+58h] [rbp-A8h]
  unsigned int v56; // [rsp+60h] [rbp-A0h]
  __int64 v57; // [rsp+64h] [rbp-9Ch]
  char v58; // [rsp+6Ch] [rbp-94h]
  DWORD pdwType; // [rsp+70h] [rbp-90h] BYREF
  HKEY hkey; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  __int64 v62; // [rsp+88h] [rbp-78h]
  BYTE Data[8]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v64; // [rsp+98h] [rbp-68h]
  void *Buf1; // [rsp+A0h] [rbp-60h]
  __int64 pvData; // [rsp+A8h] [rbp-58h] BYREF
  HKEY v67; // [rsp+B0h] [rbp-50h] BYREF
  DWORD pcbData; // [rsp+B8h] [rbp-48h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v70; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v71; // [rsp+E8h] [rbp-18h]
  wchar_t *v72[4]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v73; // [rsp+120h] [rbp+20h] BYREF
  __int64 v74; // [rsp+128h] [rbp+28h]
  __int128 Buf2; // [rsp+140h] [rbp+40h] BYREF
  _QWORD v76[10]; // [rsp+150h] [rbp+50h] BYREF

  Buf1 = a1;
  *(_QWORD *)Data = a5;
  v8 = (HKEY)*((_QWORD *)a2 + 25);
  v9 = (__int64)(*((_QWORD *)a2 + 26) - (_QWORD)v8) >> 1;
  hKey = v8;
  v62 = v9;
  if ( !(unsigned __int8)IsSecurityChannel(&hKey) )
  {
    if ( a3 > 8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, 13);
      }
      EvtException::EvtException((EvtException *)&pExceptionObject, 0xDu, v10, 1249);
      throw (EvtException *)&pExceptionObject;
    }
    hKey = v8;
    v62 = v9;
    SessionConfig::EtwSessionForChannel::EtwSessionForChannel(
      v76,
      &hKey,
      *((unsigned __int8 *)a2 + 249),
      *((unsigned __int8 *)a2 + 248));
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v70);
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             &v70,
                             v76[0]) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, 14);
      }
      EvtException::EvtException((EvtException *)&pExceptionObject, 0xEu, v11, 1256);
      throw (EvtException *)&pExceptionObject;
    }
    Buf2 = *(_OWORD *)((char *)a2 + 8);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v73);
    LOBYTE(v12) = 1;
    v13 = tlx::assign_guid<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v73, a1, v12);
    v14 = v13;
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          81,
          &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids,
          (unsigned int)v13);
      }
      pExceptionObject = word_14003838A;
      v54 = 0;
      v55 = 0;
      v56 = v14;
      v57 = -1;
      v58 = 0;
      throw (EvtException *)&pExceptionObject;
    }
    hKey = 0;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v72);
    AutoLoggersRegPath = RegistryPaths::GetAutoLoggersRegPath(v15, &hKey, lpSubKey, v72);
    v17 = AutoLoggersRegPath;
    if ( AutoLoggersRegPath < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          82,
          &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids,
          (unsigned int)AutoLoggersRegPath);
      }
      pExceptionObject = word_14003838A;
      v54 = 0;
      v55 = 0;
      v56 = v17;
      v57 = -1;
      v58 = 0;
      throw (EvtException *)&pExceptionObject;
    }
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                             lpSubKey,
                             92)
      || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                             lpSubKey,
                             v70,
                             (v71 - v70) >> 1)
      || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                             lpSubKey,
                             92)
      || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                             lpSubKey,
                             v73,
                             (v74 - v73) >> 1) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, 14);
      }
      EvtException::EvtException((EvtException *)&pExceptionObject, 0xEu, v18, 1276);
      throw (EvtException *)&pExceptionObject;
    }
    hkey = 0;
    v19 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
    RegKey = OpenRegKey(hKey, lpSubKey[0], 0x2001Fu, v19, a5);
    v21 = 0;
    v67 = 0;
    if ( v72[0] != v72[1] )
    {
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                               v72,
                               92)
        || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                               v72,
                               v70,
                               (v71 - v70) >> 1)
        || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                               v72,
                               92)
        || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                               v72,
                               v73,
                               (v74 - v73) >> 1) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, 14);
        }
        EvtException::EvtException((EvtException *)&pExceptionObject, 0xEu, v22, 1290);
        throw (EvtException *)&pExceptionObject;
      }
      v23 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v67);
      RegKey = OpenRegKey(hKey, v72[0], 0x20019u, v23, a5);
      v21 = v67;
    }
    pvData = 0;
    v24 = 0;
    v25 = 1LL << (63 - (unsigned __int8)a3);
    if ( (unsigned __int8)(*((_BYTE *)a2 + 249) - 2) <= 1u || *((_BYTE *)a2 + 248) == 2 )
    {
      v26 = a4;
      if ( !*((_BYTE *)a2 + 251) || !a4 )
        goto LABEL_49;
      v29 = *(_QWORD *)a2;
      v24 = 1LL << (63 - (unsigned __int8)a3);
      v28 = *(_QWORD *)a2;
    }
    else
    {
      pdwType = 0;
      pcbData = 8;
      RegGetValueW(hkey, 0, L"MatchAnyKeyword", 0x48u, &pdwType, &pvData, &pcbData);
      v26 = a4;
      if ( *((_BYTE *)a2 + 251) && a4 )
        v27 = pvData | v25;
      else
        v27 = pvData & ~v25;
      v28 = v27 & 0xFF00000000000000uLL;
      v29 = v28;
      v21 = v67;
    }
    pvData = v29;
    if ( v28 || v24 )
    {
      v30 = 0;
      goto LABEL_50;
    }
LABEL_49:
    v30 = 1;
LABEL_50:
    v31 = hkey;
    if ( !v26 || v30 )
    {
      if ( !v21 && !hkey )
      {
LABEL_54:
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v72);
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v73);
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v70);
        SessionConfig::EtwSessionForChannel::~EtwSessionForChannel((SessionConfig::EtwSessionForChannel *)v76);
        return;
      }
      if ( v30 )
      {
        if ( !hkey )
          goto LABEL_69;
        if ( !v21 )
        {
          if ( !RegDeleteKeyExW(hKey, lpSubKey[0], 0, 0)
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF__guid_S(*((_QWORD *)WPP_GLOBAL_Control + 2), v32, v33, (_DWORD)Buf1, (__int64)lpSubKey[0]);
          }
LABEL_64:
          if ( v67 )
            RegCloseKey(v67);
          if ( hkey )
            RegCloseKey(hkey);
          goto LABEL_54;
        }
      }
    }
    if ( hkey )
    {
LABEL_70:
      if ( RegKey )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, RegKey);
        }
        pExceptionObject = word_14003838A;
        v54 = 0;
        v55 = 0;
        v56 = RegKey;
        v57 = -1;
        v58 = 0;
        throw (EvtException *)&pExceptionObject;
      }
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        v35 = Buf1;
      }
      else
      {
        v35 = Buf1;
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          *(LPCWSTR *)Data = lpSubKey[0];
          v64 = lpSubKey[1] - lpSubKey[0];
          hKey = (HKEY)*((_QWORD *)a2 + 25);
          v62 = (__int64)(*((_QWORD *)a2 + 26) - (_QWORD)hKey) >> 1;
          WPP_SF__guid__utlwsv__utlwsv_(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)&hKey, (__int64)Data);
          v31 = hkey;
        }
      }
      pdwType = v30 ^ 1;
      v36 = RegSetValueExW(v31, L"Enabled", 0, 4u, (const BYTE *)&pdwType, 4u);
      v37 = v36;
      if ( v36 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v36);
        }
        pExceptionObject = word_14003838A;
        v54 = 0;
        v55 = 0;
        v56 = v37;
        v57 = -1;
        v58 = 0;
        throw (EvtException *)&pExceptionObject;
      }
      pdwType = *((unsigned __int8 *)a2 + 50);
      v38 = RegSetValueExW(hkey, L"EnableLevel", 0, 4u, (const BYTE *)&pdwType, 4u);
      v39 = v38;
      if ( v38 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v38);
        }
        pExceptionObject = word_14003838A;
        v54 = 0;
        v55 = 0;
        v56 = v39;
        v57 = -1;
        v58 = 0;
        throw (EvtException *)&pExceptionObject;
      }
      *(_QWORD *)Data = v70;
      v64 = (v71 - v70) >> 1;
      v40 = RegWriteStringValueNoThrow(hkey, L"LoggerName", Data);
      v41 = v40;
      if ( v40 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v40);
        }
        pExceptionObject = word_14003838A;
        v54 = 0;
        v55 = 0;
        v56 = v41;
        v57 = -1;
        v58 = 0;
        throw (EvtException *)&pExceptionObject;
      }
      if ( !memcmp_0(v35, &Buf2, 0x10u) )
      {
        pdwType = *(_DWORD *)a2;
        v42 = RegSetValueExW(hkey, L"EnableFlags", 0, 4u, (const BYTE *)&pdwType, 4u);
        v43 = v42;
        if ( v42 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v42);
          }
          pExceptionObject = word_14003838A;
          v54 = 0;
          v55 = 0;
          v56 = v43;
          v57 = -1;
          v58 = 0;
          throw (EvtException *)&pExceptionObject;
        }
      }
      else
      {
        *(_QWORD *)Data = pvData;
        v44 = RegSetValueExW(hkey, L"MatchAnyKeyword", 0, 0xBu, Data, 8u);
        v45 = v44;
        if ( v44 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v44);
          }
          pExceptionObject = word_14003838A;
          v54 = 0;
          v55 = 0;
          v56 = v45;
          v57 = -1;
          v58 = 0;
          throw (EvtException *)&pExceptionObject;
        }
        *(_QWORD *)Data = v24;
        v46 = RegSetValueExW(hkey, L"MatchAllKeyword", 0, 0xBu, Data, 8u);
        v47 = v46;
        if ( v46 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v46);
          }
          pExceptionObject = word_14003838A;
          v54 = 0;
          v55 = 0;
          v56 = v47;
          v57 = -1;
          v58 = 0;
          throw (EvtException *)&pExceptionObject;
        }
        pdwType = *((_BYTE *)a2 + 49) != 0;
        v48 = RegSetValueExW(hkey, L"EnableProperty", 0, 4u, (const BYTE *)&pdwType, 4u);
        v49 = v48;
        if ( v48 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v48);
          }
          pExceptionObject = word_14003838A;
          v54 = 0;
          v55 = 0;
          v56 = v49;
          v57 = -1;
          v58 = 0;
          throw (EvtException *)&pExceptionObject;
        }
        *(_QWORD *)Data = v70;
        v64 = (v71 - v70) >> 1;
        v50 = RegWriteStringValueNoThrow(hkey, L"LoggerName", Data);
        v51 = v50;
        if ( v50 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v50);
          }
          pExceptionObject = word_14003838A;
          v54 = 0;
          v55 = 0;
          v56 = v51;
          v57 = -1;
          v58 = 0;
          throw (EvtException *)&pExceptionObject;
        }
      }
      goto LABEL_64;
    }
LABEL_69:
    v34 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
    RegKey = CreateRegKey(hKey, lpSubKey[0], 0x2001Fu, 0, v34, 0, *(void **)Data);
    v31 = hkey;
    goto LABEL_70;
  }
}

```

## disassembly

```asm
0x14001291c  mov     [rsp-8+arg_18], rbx
0x140012921  push    rbp
0x140012922  push    rsi
0x140012923  push    rdi
0x140012924  push    r12
0x140012926  push    r13
0x140012928  push    r14
0x14001292a  push    r15
0x14001292c  lea     rbp, [rsp-0B0h]
0x140012934  sub     rsp, 1B0h
0x14001293b  mov     rax, cs:__security_cookie
0x140012942  xor     rax, rsp
0x140012945  mov     [rbp+0E0h+var_40], rax
0x14001294c  mov     [rsp+1E0h+var_1A0], r9b
0x140012951  mov     r12d, r8d
0x140012954  mov     r14, rdx
0x140012957  mov     rsi, rcx
0x14001295a  mov     [rbp+0E0h+Buf1], rcx
0x14001295e  mov     r13, [rbp+0E0h+arg_20]
0x140012965  mov     qword ptr [rbp+0E0h+Data], r13
0x140012969  mov     rdi, [rdx+0C8h]
0x140012970  mov     rbx, [rdx+0D0h]
0x140012977  sub     rbx, rdi
0x14001297a  sar     rbx, 1
0x14001297d  mov     [rbp+0E0h+hKey], rdi
0x140012981  mov     [rbp+0E0h+var_158], rbx
0x140012985  lea     rcx, [rbp+0E0h+hKey]
0x140012989  call    ?IsSecurityChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsSecurityChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x14001298e  test    al, al
0x140012990  jnz     loc_140012E53
0x140012996  cmp     r12d, 8
0x14001299a  jbe     short loc_1400129FD
0x14001299c  lea     rbx, WPP_GLOBAL_Control
0x1400129a3  mov     esi, 0Dh
0x1400129a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400129af  cmp     rcx, rbx
0x1400129b2  jz      short loc_1400129D9
0x1400129b4  test    byte ptr [rcx+1Ch], 4
0x1400129b8  jz      short loc_1400129D9
0x1400129ba  mov     dil, 2
0x1400129bd  cmp     [rcx+19h], dil
0x1400129c1  jb      short loc_1400129D9
0x1400129c3  lea     edx, [rsi+42h]
0x1400129c6  mov     r9d, esi
0x1400129c9  lea     r8, WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids
0x1400129d0  mov     rcx, [rcx+10h]
0x1400129d4  call    WPP_SF_d
0x1400129d9  mov     r9d, 4E1h; int
0x1400129df  mov     edx, esi; unsigned int
0x1400129e1  lea     rcx, [rsp+1E0h+pExceptionObject]; this
0x1400129e6  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x1400129eb  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400129f2  lea     rcx, [rsp+1E0h+pExceptionObject]; pExceptionObject
0x1400129f7  call    _CxxThrowException_0
0x1400129fd  mov     [rbp+0E0h+hKey], rdi
0x140012a01  mov     [rbp+0E0h+var_158], rbx
0x140012a05  movzx   r9d, byte ptr [r14+0F8h]
0x140012a0d  movzx   r8d, byte ptr [r14+0F9h]
0x140012a15  lea     rdx, [rbp+0E0h+hKey]
0x140012a19  lea     rcx, [rbp+0E0h+var_90]
0x140012a1d  call    ??0EtwSessionForChannel@SessionConfig@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@W4_EVT_CHANNEL_TYPE@@W4_EVT_CHANNEL_ISOLATION_TYPE@@@Z; SessionConfig::EtwSessionForChannel::EtwSessionForChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,_EVT_CHANNEL_TYPE,_EVT_CHANNEL_ISOLATION_TYPE)
0x140012a22  nop
0x140012a23  lea     rcx, [rbp+0E0h+var_100]
0x140012a27  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140012a2c  nop
0x140012a2d  mov     rdx, [rbp+0E0h+var_90]
0x140012a31  lea     rcx, [rbp+0E0h+var_100]
0x140012a35  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x140012a3a  xor     edi, edi
0x140012a3c  test    al, al
0x140012a3e  jnz     short loc_140012A9F
0x140012a40  lea     rbx, WPP_GLOBAL_Control
0x140012a47  lea     esi, [rdi+0Eh]
0x140012a4a  mov     rcx, cs:WPP_GLOBAL_Control
0x140012a51  cmp     rcx, rbx
0x140012a54  jz      short loc_140012A7B
0x140012a56  test    byte ptr [rcx+1Ch], 4
0x140012a5a  jz      short loc_140012A7B
0x140012a5c  mov     dil, 2
0x140012a5f  cmp     [rcx+19h], dil
0x140012a63  jb      short loc_140012A7B
0x140012a65  lea     edx, [rsi+42h]
0x140012a68  mov     r9d, esi
0x140012a6b  lea     r8, WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids
0x140012a72  mov     rcx, [rcx+10h]
0x140012a76  call    WPP_SF_d
0x140012a7b  mov     r9d, 4E8h; int
0x140012a81  mov     edx, esi; unsigned int
0x140012a83  lea     rcx, [rsp+1E0h+pExceptionObject]; this
0x140012a88  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140012a8d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140012a94  lea     rcx, [rsp+1E0h+pExceptionObject]; pExceptionObject
0x140012a99  call    _CxxThrowException_0
0x140012a9f  movups  xmm0, xmmword ptr [r14+8]
0x140012aa4  movdqu  [rbp+0E0h+Buf2], xmm0
0x140012aa9  lea     rcx, [rbp+0E0h+var_C0]
0x140012aad  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140012ab2  nop
0x140012ab3  mov     r8b, 1
0x140012ab6  mov     rdx, rsi
0x140012ab9  lea     rcx, [rbp+0E0h+var_C0]
0x140012abd  call    ??$assign_guid@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEBU_GUID@@_N@Z; tlx::assign_guid<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,_GUID const &,bool)
0x140012ac2  mov     esi, eax
0x140012ac4  test    eax, eax
0x140012ac6  jns     short loc_140012B42
0x140012ac8  lea     rbx, WPP_GLOBAL_Control
0x140012acf  mov     rcx, cs:WPP_GLOBAL_Control
0x140012ad6  cmp     rcx, rbx
0x140012ad9  jz      short loc_140012B04
0x140012adb  test    byte ptr [rcx+1Ch], 4
0x140012adf  jz      short loc_140012B04
0x140012ae1  mov     dil, 2
0x140012ae4  cmp     [rcx+19h], dil
0x140012ae8  jb      short loc_140012B02
0x140012aea  mov     edx, 51h ; 'Q'
0x140012aef  mov     r9d, eax
0x140012af2  lea     r8, WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids
0x140012af9  mov     rcx, [rcx+10h]
0x140012afd  call    WPP_SF_d
0x140012b02  xor     edi, edi
0x140012b04  lea     rax, word_14003838A
0x140012b0b  mov     [rsp+1E0h+pExceptionObject], rax
0x140012b10  mov     [rsp+1E0h+var_190], rdi
0x140012b15  mov     [rsp+1E0h+var_188], 0
0x140012b1e  mov     [rsp+1E0h+var_180], esi
0x140012b22  mov     [rsp+1E0h+var_17C], 0FFFFFFFFFFFFFFFFh
0x140012b2b  mov     [rsp+1E0h+var_174], dil
0x140012b30  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140012b37  lea     rcx, [rsp+1E0h+pExceptionObject]; pExceptionObject
0x140012b3c  call    _CxxThrowException_0
0x140012b42  mov     [rbp+0E0h+hKey], rdi
0x140012b46  lea     rcx, [rbp+0E0h+lpSubKey]
0x140012b4a  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140012b4f  nop
0x140012b50  lea     rcx, [rbp+0E0h+var_E0]
0x140012b54  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140012b59  nop
0x140012b5a  lea     r9, [rbp+0E0h+var_E0]
0x140012b5e  lea     r8, [rbp+0E0h+lpSubKey]
0x140012b62  lea     rdx, [rbp+0E0h+hKey]
0x140012b66  call    ?GetAutoLoggersRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; RegistryPaths::GetAutoLoggersRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x140012b6b  mov     esi, eax
0x140012b6d  test    eax, eax
0x140012b6f  jns     short loc_140012BEB
0x140012b71  lea     rbx, WPP_GLOBAL_Control
0x140012b78  mov     rcx, cs:WPP_GLOBAL_Control
0x140012b7f  cmp     rcx, rbx
0x140012b82  jz      short loc_140012BAD
0x140012b84  test    byte ptr [rcx+1Ch], 4
0x140012b88  jz      short loc_140012BAD
0x140012b8a  mov     dil, 2
0x140012b8d  cmp     [rcx+19h], dil
0x140012b91  jb      short loc_140012BAB
0x140012b93  mov     edx, 52h ; 'R'
0x140012b98  mov     r9d, eax
0x140012b9b  lea     r8, WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids
0x140012ba2  mov     rcx, [rcx+10h]
0x140012ba6  call    WPP_SF_d
0x140012bab  xor     edi, edi
0x140012bad  lea     rax, word_14003838A
0x140012bb4  mov     [rsp+1E0h+pExceptionObject], rax
0x140012bb9  mov     [rsp+1E0h+var_190], rdi
0x140012bbe  mov     [rsp+1E0h+var_188], 0
0x140012bc7  mov     [rsp+1E0h+var_180], esi
0x140012bcb  mov     [rsp+1E0h+var_17C], 0FFFFFFFFFFFFFFFFh
0x140012bd4  mov     [rsp+1E0h+var_174], dil
0x140012bd9  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140012be0  lea     rcx, [rsp+1E0h+pExceptionObject]; pExceptionObject
0x140012be5  call    _CxxThrowException_0
0x140012beb  mov     ebx, 5Ch ; '\'
0x140012bf0  mov     edx, ebx
0x140012bf2  lea     rcx, [rbp+0E0h+lpSubKey]
0x140012bf6  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x140012bfb  test    al, al
0x140012bfd  jz      loc_1400135F1
0x140012c03  mov     r8, [rbp+0E0h+var_F8]
0x140012c07  mov     rdx, [rbp+0E0h+var_100]
0x140012c0b  sub     r8, rdx
0x140012c0e  sar     r8, 1
0x140012c11  lea     rcx, [rbp+0E0h+lpSubKey]
0x140012c15  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x140012c1a  test    al, al
0x140012c1c  jz      loc_1400135F1
0x140012c22  mov     edx, ebx
0x140012c24  lea     rcx, [rbp+0E0h+lpSubKey]
0x140012c28  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x140012c2d  test    al, al
0x140012c2f  jz      loc_1400135F1
0x140012c35  mov     r8, [rbp+0E0h+var_B8]
0x140012c39  mov     rdx, [rbp+0E0h+var_C0]
0x140012c3d  sub     r8, rdx
0x140012c40  sar     r8, 1
0x140012c43  lea     rcx, [rbp+0E0h+lpSubKey]
0x140012c47  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x140012c4c  test    al, al
0x140012c4e  jz      loc_1400135F1
0x140012c54  mov     [rsp+1E0h+hkey], rdi
0x140012c59  lea     rcx, [rsp+1E0h+hkey]
0x140012c5e  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140012c63  mov     [rsp+1E0h+pdwType], r13; void *
0x140012c68  mov     r9, rax; HKEY *
0x140012c6b  mov     r8d, 2001Fh; unsigned int
0x140012c71  mov     rdx, [rbp+0E0h+lpSubKey]; wchar_t *
0x140012c75  mov     rcx, [rbp+0E0h+hKey]; HKEY
0x140012c79  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x140012c7e  mov     r15d, eax
0x140012c81  mov     rax, rdi
0x140012c84  mov     [rbp+0E0h+var_130], rax
0x140012c88  mov     rcx, [rbp+0E0h+var_D8]
0x140012c8c  cmp     [rbp+0E0h+var_E0], rcx
0x140012c90  jz      loc_140012D25
0x140012c96  mov     edx, ebx
0x140012c98  lea     rcx, [rbp+0E0h+var_E0]
0x140012c9c  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x140012ca1  test    al, al
0x140012ca3  jz      loc_140013590
0x140012ca9  mov     r8, [rbp+0E0h+var_F8]
0x140012cad  mov     rdx, [rbp+0E0h+var_100]
0x140012cb1  sub     r8, rdx
0x140012cb4  sar     r8, 1
0x140012cb7  lea     rcx, [rbp+0E0h+var_E0]
0x140012cbb  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x140012cc0  test    al, al
0x140012cc2  jz      loc_140013590
0x140012cc8  mov     edx, ebx
0x140012cca  lea     rcx, [rbp+0E0h+var_E0]
0x140012cce  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x140012cd3  test    al, al
0x140012cd5  jz      loc_140013590
0x140012cdb  mov     r8, [rbp+0E0h+var_B8]
0x140012cdf  mov     rdx, [rbp+0E0h+var_C0]
0x140012ce3  sub     r8, rdx
0x140012ce6  sar     r8, 1
0x140012ce9  lea     rcx, [rbp+0E0h+var_E0]
0x140012ced  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x140012cf2  test    al, al
0x140012cf4  jz      loc_140013590
0x140012cfa  lea     rcx, [rbp+0E0h+var_130]
0x140012cfe  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140012d03  mov     [rsp+1E0h+pdwType], r13; void *
0x140012d08  mov     r9, rax; HKEY *
0x140012d0b  mov     r8d, 20019h; unsigned int
0x140012d11  mov     rdx, [rbp+0E0h+var_E0]; wchar_t *
0x140012d15  mov     rcx, [rbp+0E0h+hKey]; HKEY
0x140012d19  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x140012d1e  mov     r15d, eax
0x140012d21  mov     rax, [rbp+0E0h+var_130]
0x140012d25  mov     [rbp+0E0h+var_138], rdi
0x140012d29  mov     r13, rdi
0x140012d2c  mov     ecx, 3Fh ; '?'
0x140012d31  sub     ecx, r12d
0x140012d34  mov     ebx, 1
0x140012d39  shl     rbx, cl
0x140012d3c  mov     cl, [r14+0F9h]
0x140012d43  mov     dil, 2
0x140012d46  sub     cl, dil
0x140012d49  cmp     cl, 1
0x140012d4c  jbe     loc_140012DD3
0x140012d52  cmp     [r14+0F8h], dil
0x140012d59  jz      short loc_140012DD3
0x140012d5b  xor     r12d, r12d
0x140012d5e  mov     [rsp+1E0h+var_170], r12d
0x140012d63  mov     [rbp+0E0h+var_128], 8
0x140012d6a  lea     rax, [rbp+0E0h+var_128]
0x140012d6e  mov     [rsp+1E0h+pcbData], rax; pcbData
0x140012d73  lea     rax, [rbp+0E0h+var_138]
0x140012d77  mov     [rsp+1E0h+pvData], rax; pvData
0x140012d7c  lea     rax, [rsp+1E0h+var_170]
0x140012d81  mov     [rsp+1E0h+pdwType], rax; pdwType
0x140012d86  lea     r9d, [r12+48h]; dwFlags
0x140012d8b  lea     r8, aMatchanykeywor; "MatchAnyKeyword"
0x140012d92  xor     edx, edx; lpSubKey
0x140012d94  mov     rcx, [rsp+1E0h+hkey]; hkey
0x140012d99  call    cs:__imp_RegGetValueW
0x140012d9f  mov     dl, [rsp+1E0h+var_1A0]
0x140012da3  cmp     [r14+0FBh], r12b
0x140012daa  jz      short loc_140012DB6
0x140012dac  test    dl, dl
0x140012dae  jz      short loc_140012DB6
0x140012db0  or      rbx, [rbp+0E0h+var_138]
0x140012db4  jmp     short loc_140012DBD
0x140012db6  not     rbx
0x140012db9  and     rbx, [rbp+0E0h+var_138]
0x140012dbd  mov     rax, 0FF00000000000000h
0x140012dc7  and     rbx, rax
0x140012dca  mov     rcx, rbx
0x140012dcd  mov     rax, [rbp+0E0h+var_130]
0x140012dd1  jmp     short loc_140012DF0
0x140012dd3  xor     r12d, r12d
0x140012dd6  mov     dl, [rsp+1E0h+var_1A0]
0x140012dda  cmp     [r14+0FBh], r12b
0x140012de1  jz      short loc_140012E03
0x140012de3  test    dl, dl
0x140012de5  jz      short loc_140012E03
0x140012de7  mov     rcx, [r14]
0x140012dea  mov     r13, rbx
0x140012ded  mov     rbx, rcx
0x140012df0  mov     [rbp+0E0h+var_138], rcx
0x140012df4  test    rbx, rbx
0x140012df7  jnz     short loc_140012DFE
  ... truncated ...
```
