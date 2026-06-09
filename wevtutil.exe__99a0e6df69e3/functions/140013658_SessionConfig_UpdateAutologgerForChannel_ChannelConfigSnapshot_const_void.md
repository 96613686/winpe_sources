# SessionConfig::UpdateAutologgerForChannel(ChannelConfigSnapshot const &,void *)

- ea: `0x140013658`
- end: `0x14001495a`
- name: `?UpdateAutologgerForChannel@SessionConfig@@SAXAEBVChannelConfigSnapshot@@PEAX@Z`
- size: `4866`
- prototype: `void __fastcall(const struct ChannelConfigSnapshot *, void *)`
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14002e018`

## callees

- `0x140003700`
- `0x140004ae0`
- `0x140005600`
- `0x140006db0`
- `0x140007310`
- `0x140007fd0`
- `0x140008870`
- `0x14000a4d8`
- `0x14000b6d0`
- `0x14000d314`
- `0x14000d62c`
- `0x14000d6e8`
- `0x14001291c`
- `0x140013658`
- `0x140014960`
- `0x140014988`
- `0x1400151ec`
- `0x140019348`
- `0x14001b5b4`
- `0x14001b668`
- `0x140021b00`
- `0x140022510`
- `0x140022cec`
- `0x14002ba80`
- `0x14002c664`
- `0x14002dc00`
- `0x14002e0cc`
- `0x14002efbc`
- `0x14002f198`
- `0x14002f6c8`
- `0x140031810`
- `0x14003181c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140014439`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140014439`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140014914`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140014925`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140014914`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140014925`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140013ad5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140013ddf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140013e7d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140013f1b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140013fb9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140014057`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140014103`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400142cb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140014364`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140014475`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400144fc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001459b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140013ad5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140013ddf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140013e7d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140013f1b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140013fb9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140014057`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140014103`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400142cb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140014364`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140014475`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400144fc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001459b`

## string_xrefs

- `0x1400143f4`: `Security`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall SessionConfig::UpdateAutologgerForChannel(const struct ChannelConfigSnapshot *a1, void *a2)
{
  __int64 v4; // rax
  unsigned int PersistedAutoLoggerRegPath; // eax
  int v6; // r12d
  HKEY *v7; // rax
  int v8; // eax
  int v9; // r12d
  __int64 v10; // rcx
  unsigned int WinevtRegPath; // eax
  unsigned int v12; // r12d
  const char *v13; // r8
  HKEY *v14; // rax
  int v15; // eax
  const wchar_t *v16; // rdx
  int v17; // r14d
  const wchar_t *v18; // rdx
  unsigned int v19; // eax
  unsigned int v20; // r14d
  char v21; // r13
  struct _GUID v22; // xmm6
  HKEY *v23; // rax
  int v24; // eax
  int v25; // r12d
  const wchar_t *v26; // r9
  unsigned int v27; // eax
  unsigned int v28; // r12d
  unsigned int v29; // eax
  unsigned int v30; // r12d
  unsigned int v31; // eax
  unsigned int v32; // r12d
  unsigned int v33; // eax
  unsigned int v34; // r12d
  unsigned int v35; // eax
  unsigned int v36; // r12d
  unsigned int v37; // eax
  unsigned int v38; // r12d
  const char *v39; // r8
  unsigned int v40; // eax
  unsigned int v41; // r12d
  int v42; // r13d
  unsigned int v43; // eax
  unsigned int v44; // r12d
  unsigned int v45; // eax
  unsigned int v46; // r12d
  unsigned int v47; // eax
  unsigned int v48; // r12d
  unsigned int v49; // eax
  unsigned int v50; // r12d
  unsigned int v51; // eax
  unsigned int v52; // r12d
  const char *v53; // r8
  unsigned int v54; // eax
  unsigned int v55; // r12d
  const char *v56; // r8
  unsigned int v57; // eax
  unsigned int v58; // r12d
  __int16 *v59; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v60; // [rsp+50h] [rbp-B8h]
  __int64 v61; // [rsp+58h] [rbp-B0h]
  unsigned int v62; // [rsp+60h] [rbp-A8h]
  __int64 v63; // [rsp+64h] [rbp-A4h]
  char v64; // [rsp+6Ch] [rbp-9Ch]
  HKEY Data; // [rsp+70h] [rbp-98h] BYREF
  BYTE Data_8[16]; // [rsp+78h] [rbp-90h] BYREF
  struct _GUID v67; // [rsp+88h] [rbp-80h] BYREF
  unsigned int v68; // [rsp+98h] [rbp-70h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp-68h] BYREF
  unsigned int v70; // [rsp+A8h] [rbp-60h] BYREF
  unsigned int v71; // [rsp+ACh] [rbp-5Ch] BYREF
  __int16 *pExceptionObject; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v73; // [rsp+B8h] [rbp-50h]
  __int64 v74; // [rsp+C0h] [rbp-48h]
  int v75; // [rsp+C8h] [rbp-40h]
  int v76; // [rsp+CCh] [rbp-3Ch]
  int v77; // [rsp+D0h] [rbp-38h]
  char v78; // [rsp+D4h] [rbp-34h]
  struct _GUID Buf1[2]; // [rsp+D8h] [rbp-30h] BYREF
  wchar_t *v80[4]; // [rsp+F8h] [rbp-10h] BYREF
  _QWORD v81[4]; // [rsp+118h] [rbp+10h] BYREF
  _QWORD v82[4]; // [rsp+138h] [rbp+30h] BYREF
  LPCWCH lpString2[4]; // [rsp+158h] [rbp+50h] BYREF
  _EVENT_TRACE_PROPERTIES v84; // [rsp+178h] [rbp+70h] BYREF
  LPCWCH lpString1[8]; // [rsp+1F8h] [rbp+F0h] BYREF
  struct _GUID v86; // [rsp+238h] [rbp+130h]
  const struct ChannelConfigSnapshot *v87; // [rsp+248h] [rbp+140h] BYREF
  _BYTE v88[88]; // [rsp+250h] [rbp+148h] BYREF

  if ( !ChannelConfigSnapshot::IsOwnerOfEtwSession(a1) )
  {
    SessionConfig::UpdateProvidersForChannel(a1, 1, a2);
    return;
  }
  Data = 0;
  hKey = 0;
  *(_QWORD *)Data_8 = *((_QWORD *)a1 + 25);
  *(_QWORD *)&Data_8[8] = (__int64)(*((_QWORD *)a1 + 26) - *(_QWORD *)Data_8) >> 1;
  SessionConfig::EtwSessionForChannel::EtwSessionForChannel(
    lpString1,
    Data_8,
    *((unsigned __int8 *)a1 + 249),
    *((unsigned __int8 *)a1 + 248));
  *(_QWORD *)Data_8 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v80);
  v4 = -1;
  do
    ++v4;
  while ( lpString1[0][v4] );
  *(LPCWCH *)&v67.Data1 = lpString1[0];
  *(_QWORD *)v67.Data4 = v4;
  PersistedAutoLoggerRegPath = RegistryPaths::GetPersistedAutoLoggerRegPath(lpString1[0], &v67, Data_8, v80);
  v6 = PersistedAutoLoggerRegPath;
  if ( PersistedAutoLoggerRegPath )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids,
        PersistedAutoLoggerRegPath);
    }
    pExceptionObject = word_14003838A;
    v73 = 0;
    v74 = 0;
    v75 = v6;
    v76 = -1;
    v77 = -1;
    v78 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  if ( *((_BYTE *)a1 + 251) )
  {
    v87 = a1;
    *(_QWORD *)&v67.Data1 = *((_QWORD *)a1 + 25);
    *(_QWORD *)v67.Data4 = (__int64)(*((_QWORD *)a1 + 26) - *(_QWORD *)&v67.Data1) >> 1;
    SessionConfig::EtwSessionForChannel::EtwSessionForChannel(
      v88,
      &v67,
      *((unsigned __int8 *)a1 + 249),
      *((unsigned __int8 *)a1 + 248));
    memset_0(&v84, 0, sizeof(v84));
    SessionConfig::BuildTracePropsFromChannelRegistryConfig_Impl((SessionConfig *)&v87, &v84);
    v21 = *((_BYTE *)a1 + 249);
    v22 = *(struct _GUID *)((char *)a1 + 8);
    Buf1[0] = v22;
    v68 = 0;
    v23 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&Data);
    v24 = CreateRegKey(*(HKEY *)Data_8, v80[0], 0x2001Fu, 0, v23, &v68, a2);
    v25 = v24;
    if ( v24 )
    {
      if ( v24 != 5
        || (*(_QWORD *)&v67.Data1 = *((_QWORD *)a1 + 25),
            *(_QWORD *)v67.Data4 = (__int64)(*((_QWORD *)a1 + 26) - *(_QWORD *)&v67.Data1) >> 1,
            !(unsigned __int8)IsSecurityChannel(&v67)) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_DS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            27,
            (unsigned int)&WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids,
            v25,
            (__int64)v80[0]);
        }
        v59 = word_14003838A;
        v60 = 0;
        v61 = 0;
        v62 = v25;
        v63 = -1;
        v64 = 0;
        throw (EvtException *)&v59;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v26 = L"Modifying";
        if ( v68 != 2 )
          v26 = L"Creating";
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          (unsigned int)&WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids,
          (_DWORD)v26,
          (__int64)v80[0]);
      }
      *(_DWORD *)Data_8 = 1;
      v27 = RegSetValueExW(Data, L"Start", 0, 4u, Data_8, 4u);
      v28 = v27;
      if ( v27 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v27);
        }
        v59 = word_14003838A;
        v60 = 0;
        v61 = 0;
        v62 = v28;
        v63 = -1;
        v64 = 0;
        throw (EvtException *)&v59;
      }
      *(_DWORD *)Data_8 = v84.BufferSize;
      v29 = RegSetValueExW(Data, L"BufferSize", 0, 4u, Data_8, 4u);
      v30 = v29;
      if ( v29 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v29);
        }
        v59 = word_14003838A;
        v60 = 0;
        v61 = 0;
        v62 = v30;
        v63 = -1;
        v64 = 0;
        throw (EvtException *)&v59;
      }
      *(_DWORD *)Data_8 = v84.MinimumBuffers;
      v31 = RegSetValueExW(Data, L"MinimumBuffers", 0, 4u, Data_8, 4u);
      v32 = v31;
      if ( v31 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v31);
        }
        v59 = word_14003838A;
        v60 = 0;
        v61 = 0;
        v62 = v32;
        v63 = -1;
        v64 = 0;
        throw (EvtException *)&v59;
      }
      *(_DWORD *)Data_8 = v84.MaximumBuffers;
      v33 = RegSetValueExW(Data, L"MaximumBuffers", 0, 4u, Data_8, 4u);
      v34 = v33;
      if ( v33 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v33);
        }
        v59 = word_14003838A;
        v60 = 0;
        v61 = 0;
        v62 = v34;
        v63 = -1;
        v64 = 0;
        throw (EvtException *)&v59;
      }
      *(_DWORD *)Data_8 = v84.FlushTimer;
      v35 = RegSetValueExW(Data, L"FlushTimer", 0, 4u, Data_8, 4u);
      v36 = v35;
      if ( v35 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v35);
        }
        v59 = word_14003838A;
        v60 = 0;
        v61 = 0;
        v62 = v36;
        v63 = -1;
        v64 = 0;
        throw (EvtException *)&v59;
      }
      if ( (unsigned __int8)(v21 - 2) <= 1u )
      {
        *(_DWORD *)Data_8 = v84.MaximumFileSize;
        v37 = RegSetValueExW(Data, L"MaxFileSize", 0, 4u, Data_8, 4u);
        v38 = v37;
        if ( v37 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v37);
          }
          v59 = word_14003838A;
          v60 = 0;
          v61 = 0;
          v62 = v38;
          v63 = -1;
          v64 = 0;
          throw (EvtException *)&v59;
        }
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&pExceptionObject);
        *(_QWORD *)&v67.Data1 = *((_QWORD *)a1 + 7);
        *(_QWORD *)v67.Data4 = (__int64)(*((_QWORD *)a1 + 8) - *(_QWORD *)&v67.Data1) >> 1;
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                 &pExceptionObject,
                                 &v67) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, 14);
          }
          EvtException::EvtException((EvtException *)&v59, 0xEu, v39, 459);
          throw (EvtException *)&v59;
        }
        *(_QWORD *)&v67.Data1 = pExceptionObject;
        *(_QWORD *)v67.Data4 = (v73 - (__int64)pExceptionObject) >> 1;
        v40 = RegWriteStringValueNoThrow(Data, L"FileName", &v67);
        v41 = v40;
        if ( v40 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v40);
          }
          v59 = word_14003838A;
          v60 = 0;
          v61 = 0;
          v62 = v41;
          v63 = -1;
          v64 = 0;
          throw (EvtException *)&v59;
        }
        if ( *((_DWORD *)a1 + 10) > 1u )
        {
          v42 = *((_DWORD *)a1 + 11);
          *(_DWORD *)Data_8 = *((_DWORD *)a1 + 10);
          v43 = RegSetValueExW(Data, L"FileMax", 0, 4u, Data_8, 4u);
          v44 = v43;
          if ( v43 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v43);
            }
            v59 = word_14003838A;
            v60 = 0;
            v61 = 0;
            v62 = v44;
            v63 = -1;
            v64 = 0;
            throw (EvtException *)&v59;
          }
          *(_DWORD *)Data_8 = v42;
          v45 = RegSetValueExW(Data, L"FileCounter", 0, 4u, Data_8, 4u);
          v46 = v45;
          if ( v45 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v45);
            }
            v59 = word_14003838A;
            v60 = 0;
            v61 = 0;
            v62 = v46;
            v63 = -1;
            v64 = 0;
            throw (EvtException *)&v59;
          }
        }
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&pExceptionObject);
      }
      *(_OWORD *)Data_8 = 0;
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpString2);
      *(_QWORD *)&v67.Data1 = L"Security";
      *(_QWORD *)v67.Data4 = 8;
      SessionConfig::EtwSessionForChannel::GetSessionNameAndGuid(&v67, lpString2, Data_8);
      if ( CompareStringOrdinal(lpString1[0], -1, lpString2[0], lpString2[1] - lpString2[0], 1) == 2 )
      {
        *(_DWORD *)Data_8 = v84.LogFileMode | 0x40;
        v47 = RegSetValueExW(Data, L"LogFileMode", 0, 4u, Data_8, 4u);
        v48 = v47;
        if ( v47 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v47);
          }
          v59 = word_14003838A;
          v60 = 0;
          v61 = 0;
          v62 = v48;
          v63 = -1;
          v64 = 0;
          throw (EvtException *)&v59;
        }
      }
      else
      {
        *(_DWORD *)Data_8 = v84.LogFileMode;
        v49 = RegSetValueExW(Data, L"LogFileMode", 0, 4u, Data_8, 4u);
        v50 = v49;
        if ( v49 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v49);
          }
          v59 = word_14003838A;
          v60 = 0;
          v61 = 0;
          v62 = v50;
          v63 = -1;
          v64 = 0;
          throw (EvtException *)&v59;
        }
      }
      *(_DWORD *)Data_8 = v84.Wnode.ClientContext;
      v51 = RegSetValueExW(Data, L"ClockType", 0, 4u, Data_8, 4u);
      v52 = v51;
      if ( v51 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v51);
        }
        v59 = word_14003838A;
        v60 = 0;
        v61 = 0;
        v62 = v52;
        v63 = -1;
        v64 = 0;
        throw (EvtException *)&v59;
      }
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v82);
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               v82,
                               lpString1[4]) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, 14);
        }
        EvtException::EvtException((EvtException *)&v59, 0xEu, v53, 499);
        throw (EvtException *)&v59;
      }
      *(_QWORD *)&v67.Data1 = v82[0];
      *(_QWORD *)v67.Data4 = (__int64)(v82[1] - v82[0]) >> 1;
      v54 = RegWriteStringValueNoThrow(Data, L"Guid", &v67);
      v55 = v54;
      if ( v54 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v54);
        }
        v59 = word_14003838A;
        v60 = 0;
        v61 = 0;
        v62 = v55;
        v63 = -1;
        v64 = 0;
        throw (EvtException *)&v59;
      }
      if ( memcmp_0(Buf1, &GUID_NULL, 0x10u) )
      {
        Buf1[0] = v22;
        SessionConfig::UpdateProvider(Buf1, a1, 0, 1, a2);
      }
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v81);
      *(_QWORD *)&v67.Data1 = *((_QWORD *)a1 + 25);
      *(_QWORD *)v67.Data4 = (__int64)(*((_QWORD *)a1 + 26) - *(_QWORD *)&v67.Data1) >> 1;
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               v81,
                               &v67) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, 14);
        }
        EvtException::EvtException((EvtException *)&v59, 0xEu, v56, 514);
        throw (EvtException *)&v59;
      }
      *(_QWORD *)&v67.Data1 = v81[0];
      *(_QWORD *)v67.Data4 = (__int64)(v81[1] - v81[0]) >> 1;
      v57 = RegWriteStringValueNoThrow(Data, L"OwningChannel", &v67);
      v58 = v57;
      if ( v57 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v57);
        }
        v59 = word_14003838A;
        v60 = 0;
        v61 = 0;
        v62 = v58;
        v63 = -1;
        v64 = 0;
        throw (EvtException *)&v59;
      }
      if ( v68 != 2
        || (*(_QWORD *)&v67.Data1 = *((_QWORD *)a1 + 25),
            *(_QWORD *)v67.Data4 = (__int64)(*((_QWORD *)a1 + 26) - *(_QWORD *)&v67.Data1) >> 1,
            !(unsigned __int8)IsCoreChannel(&v67)) )
      {
        SessionConfig::UpdateProvidersForChannel(a1, 1, a2);
      }
      SessionConfig::SetSessionSecurity(a1, 0, a2);
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v81);
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v82);
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpString2);
    }
    SessionConfig::EtwSessionForChannel::~EtwSessionForChannel((SessionConfig::EtwSessionForChannel *)v88);
    goto LABEL_178;
  }
  v71 = 0;
  v70 = 0;
  v7 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&Data);
  v8 = OpenRegKey(*(HKEY *)Data_8, v80[0], 0x20019u, v7, a2);
  v9 = v8;
  if ( v8 )
  {
    if ( v8 != 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          (unsigned int)&WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids,
          v8,
          (__int64)v80[0]);
      }
      pExceptionObject = word_14003838A;
      v73 = 0;
      v74 = 0;
      v75 = v9;
      v76 = -1;
      v77 = -1;
      v78 = 0;
      throw (EvtException *)&pExceptionObject;
    }
  }
  else
  {
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(Buf1);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&pExceptionObject);
    WinevtRegPath = RegistryPaths::GetWinevtRegPath(v10, Data_8, Buf1, &pExceptionObject);
    v12 = WinevtRegPath;
    if ( WinevtRegPath )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids,
          WinevtRegPath);
      }
      v59 = word_14003838A;
      v60 = 0;
      v61 = 0;
      v62 = v12;
      v63 = -1;
      v64 = 0;
      throw (EvtException *)&v59;
    }
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                             Buf1,
                             L"\\Channels\\",
                             10)
      || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                             Buf1,
                             *((_QWORD *)a1 + 25),
                             (__int64)(*((_QWORD *)a1 + 26) - *((_QWORD *)a1 + 25)) >> 1) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, 14);
      }
      EvtException::EvtException((EvtException *)&v59, 0xEu, v13, 375);
      throw (EvtException *)&v59;
    }
    v14 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    v15 = OpenRegKey(*(HKEY *)Data_8, *(const wchar_t **)&Buf1[0].Data1, 0x2001Fu, v14, a2);
    v17 = v15;
    if ( v15 )
    {
      if ( v15 != 2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_DS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            (unsigned int)&WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids,
            v15,
            *(__int64 *)&Buf1[0].Data1);
        }
        v59 = word_14003838A;
        v60 = 0;
        v61 = 0;
        v62 = v17;
        v63 = -1;
        v64 = 0;
        throw (EvtException *)&v59;
      }
      v67 = v86;
      SessionConfig::DeleteSession(lpString1[0], &v67, a2);
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&pExceptionObject);
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(Buf1);
      goto LABEL_178;
    }
    if ( !RegReadDWORDValueNoThrow(Data, v16, L"FileCounter", &v70)
      && !RegReadDWORDValueNoThrow(hKey, v18, L"FileCounter", &v71)
      && v70 != v71 )
    {
      *(_DWORD *)Data_8 = v70;
      v19 = RegSetValueExW(hKey, L"FileCounter", 0, 4u, Data_8, 4u);
      v20 = v19;
      if ( v19 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v19);
        }
        v59 = word_14003838A;
        v60 = 0;
        v61 = 0;
        v62 = v20;
        v63 = -1;
        v64 = 0;
        throw (EvtException *)&v59;
      }
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&pExceptionObject);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(Buf1);
  }
  v67 = v86;
  SessionConfig::DeleteSession(lpString1[0], &v67, a2);
LABEL_178:
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v80);
  SessionConfig::EtwSessionForChannel::~EtwSessionForChannel((SessionConfig::EtwSessionForChannel *)lpString1);
  if ( hKey )
    RegCloseKey(hKey);
  if ( Data )
    RegCloseKey(Data);
}

```

## disassembly

```asm
0x140013658  mov     rax, rsp
0x14001365b  mov     [rax+18h], rbx
0x14001365f  push    rbp
0x140013660  push    rsi
0x140013661  push    rdi
0x140013662  push    r12
0x140013664  push    r13
0x140013666  push    r14
0x140013668  push    r15
0x14001366a  lea     rbp, [rax-1F8h]
0x140013671  sub     rsp, 2C0h
0x140013678  movaps  xmmword ptr [rax-48h], xmm6
0x14001367c  mov     rax, cs:__security_cookie
0x140013683  xor     rax, rsp
0x140013686  mov     [rbp+1F0h+var_50], rax
0x14001368d  mov     r15, rdx
0x140013690  mov     r14, rcx
0x140013693  call    ?IsOwnerOfEtwSession@ChannelConfigSnapshot@@QEBA_NXZ; ChannelConfigSnapshot::IsOwnerOfEtwSession(void)
0x140013698  xor     esi, esi
0x14001369a  test    al, al
0x14001369c  jnz     short loc_1400136B0
0x14001369e  mov     r8, r15; void *
0x1400136a1  mov     dl, 1; bool
0x1400136a3  mov     rcx, r14; struct ChannelConfigSnapshot *
0x1400136a6  call    ?UpdateProvidersForChannel@SessionConfig@@CAXAEBVChannelConfigSnapshot@@_NPEAX@Z; SessionConfig::UpdateProvidersForChannel(ChannelConfigSnapshot const &,bool,void *)
0x1400136ab  jmp     loc_14001492B
0x1400136b0  mov     qword ptr [rsp+2F0h+Data], rsi
0x1400136b5  mov     [rbp+1F0h+hKey], rsi
0x1400136b9  mov     rax, [r14+0C8h]
0x1400136c0  mov     qword ptr [rsp+2F0h+Data+8], rax
0x1400136c5  mov     rcx, [r14+0D0h]
0x1400136cc  sub     rcx, rax
0x1400136cf  sar     rcx, 1
0x1400136d2  mov     [rsp+2F0h+var_278], rcx
0x1400136d7  movzx   r9d, byte ptr [r14+0F8h]
0x1400136df  movzx   r8d, byte ptr [r14+0F9h]
0x1400136e7  lea     rdx, [rsp+2F0h+Data+8]
0x1400136ec  lea     rcx, [rbp+1F0h+lpString1]
0x1400136f3  call    ??0EtwSessionForChannel@SessionConfig@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@W4_EVT_CHANNEL_TYPE@@W4_EVT_CHANNEL_ISOLATION_TYPE@@@Z; SessionConfig::EtwSessionForChannel::EtwSessionForChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,_EVT_CHANNEL_TYPE,_EVT_CHANNEL_ISOLATION_TYPE)
0x1400136f8  nop
0x1400136f9  mov     qword ptr [rsp+2F0h+Data+8], rsi
0x1400136fe  lea     rcx, [rbp+1F0h+var_200]
0x140013702  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140013707  nop
0x140013708  mov     rcx, [rbp+1F0h+lpString1]
0x14001370f  or      r13, 0FFFFFFFFFFFFFFFFh
0x140013713  mov     rax, r13
0x140013716  inc     rax
0x140013719  cmp     [rcx+rax*2], si
0x14001371d  jnz     short loc_140013716
0x14001371f  mov     qword ptr [rbp+1F0h+var_270.Data1], rcx
0x140013723  mov     qword ptr [rbp+1F0h+var_270.Data4], rax
0x140013727  lea     r9, [rbp+1F0h+var_200]
0x14001372b  lea     r8, [rsp+2F0h+Data+8]
0x140013730  lea     rdx, [rbp+1F0h+var_270]
0x140013734  call    ?GetPersistedAutoLoggerRegPath@RegistryPaths@@QEBAKV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@AEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@3@@Z; RegistryPaths::GetPersistedAutoLoggerRegPath(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x140013739  mov     r12d, eax
0x14001373c  test    eax, eax
0x14001373e  jz      short loc_1400137B6
0x140013740  lea     rdi, WPP_GLOBAL_Control
0x140013747  mov     rcx, cs:WPP_GLOBAL_Control
0x14001374e  cmp     rcx, rdi
0x140013751  jz      short loc_14001377B
0x140013753  mov     ebx, 4
0x140013758  test    [rcx+1Ch], bl
0x14001375b  jz      short loc_14001377B
0x14001375d  cmp     byte ptr [rcx+19h], 2
0x140013761  jb      short loc_14001377B
0x140013763  lea     edx, [rbx+11h]
0x140013766  mov     r9d, eax
0x140013769  lea     r8, WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids
0x140013770  mov     rcx, [rcx+10h]
0x140013774  call    WPP_SF_d
0x140013779  xor     esi, esi
0x14001377b  lea     rax, word_14003838A
0x140013782  mov     [rbp+1F0h+pExceptionObject], rax
0x140013786  mov     [rbp+1F0h+var_240], rsi
0x14001378a  mov     [rbp+1F0h+var_238], 0
0x140013792  mov     [rbp+1F0h+var_230], r12d
0x140013796  mov     [rbp+1F0h+var_22C], 0FFFFFFFFh
0x14001379d  mov     [rbp+1F0h+var_228], r13d
0x1400137a1  mov     [rbp+1F0h+var_224], sil
0x1400137a5  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400137ac  lea     rcx, [rbp+1F0h+pExceptionObject]; pExceptionObject
0x1400137b0  call    _CxxThrowException_0
0x1400137b6  cmp     [r14+0FBh], sil
0x1400137bd  jnz     loc_140013BF5
0x1400137c3  mov     [rbp+1F0h+var_24C], esi
0x1400137c6  mov     [rbp+1F0h+var_250], esi
0x1400137c9  lea     rcx, [rsp+2F0h+Data]
0x1400137ce  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1400137d3  mov     [rsp+2F0h+lpData], r15; void *
0x1400137d8  mov     r9, rax; HKEY *
0x1400137db  mov     r8d, 20019h; unsigned int
0x1400137e1  mov     rdx, [rbp+1F0h+var_200]; wchar_t *
0x1400137e5  mov     rcx, qword ptr [rsp+2F0h+Data+8]; HKEY
0x1400137ea  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x1400137ef  mov     r12d, eax
0x1400137f2  test    eax, eax
0x1400137f4  jz      loc_140013882
0x1400137fa  cmp     eax, 2
0x1400137fd  jz      loc_140013B6E
0x140013803  lea     rdi, WPP_GLOBAL_Control
0x14001380a  mov     rcx, cs:WPP_GLOBAL_Control
0x140013811  cmp     rcx, rdi
0x140013814  jz      short loc_140013847
0x140013816  mov     ebx, 4
0x14001381b  test    [rcx+1Ch], bl
0x14001381e  jz      short loc_140013847
0x140013820  cmp     byte ptr [rcx+19h], 2
0x140013824  jb      short loc_140013847
0x140013826  lea     edx, [rbx+12h]
0x140013829  mov     rax, [rbp+1F0h+var_200]
0x14001382d  mov     [rsp+2F0h+lpData], rax
0x140013832  mov     r9d, r12d
0x140013835  lea     r8, WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids
0x14001383c  mov     rcx, [rcx+10h]
0x140013840  call    WPP_SF_DS
0x140013845  xor     esi, esi
0x140013847  lea     rax, word_14003838A
0x14001384e  mov     [rbp+1F0h+pExceptionObject], rax
0x140013852  mov     [rbp+1F0h+var_240], rsi
0x140013856  mov     [rbp+1F0h+var_238], 0
0x14001385e  mov     [rbp+1F0h+var_230], r12d
0x140013862  mov     [rbp+1F0h+var_22C], 0FFFFFFFFh
0x140013869  mov     [rbp+1F0h+var_228], r13d
0x14001386d  mov     [rbp+1F0h+var_224], sil
0x140013871  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140013878  lea     rcx, [rbp+1F0h+pExceptionObject]; pExceptionObject
0x14001387c  call    _CxxThrowException_0
0x140013882  lea     rcx, [rbp+1F0h+Buf1]
0x140013886  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14001388b  nop
0x14001388c  lea     rcx, [rbp+1F0h+pExceptionObject]
0x140013890  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140013895  nop
0x140013896  lea     r9, [rbp+1F0h+pExceptionObject]
0x14001389a  lea     r8, [rbp+1F0h+Buf1]
0x14001389e  lea     rdx, [rsp+2F0h+Data+8]
0x1400138a3  call    ?GetWinevtRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; RegistryPaths::GetWinevtRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1400138a8  mov     r12d, eax
0x1400138ab  test    eax, eax
0x1400138ad  jz      short loc_14001392D
0x1400138af  lea     rdi, WPP_GLOBAL_Control
0x1400138b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400138bd  cmp     rcx, rdi
0x1400138c0  jz      short loc_1400138EA
0x1400138c2  mov     ebx, 4
0x1400138c7  test    [rcx+1Ch], bl
0x1400138ca  jz      short loc_1400138EA
0x1400138cc  cmp     byte ptr [rcx+19h], 2
0x1400138d0  jb      short loc_1400138EA
0x1400138d2  lea     edx, [rbx+13h]
0x1400138d5  mov     r9d, eax
0x1400138d8  lea     r8, WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids
0x1400138df  mov     rcx, [rcx+10h]
0x1400138e3  call    WPP_SF_d
0x1400138e8  xor     esi, esi
0x1400138ea  lea     rax, word_14003838A
0x1400138f1  mov     [rsp+2F0h+var_2B0], rax
0x1400138f6  mov     [rsp+2F0h+var_2A8], rsi
0x1400138fb  mov     qword ptr [rsp+2F0h+var_2A0], 0
0x140013904  mov     dword ptr [rsp+2F0h+var_29C+4], r12d
0x140013909  mov     dword ptr [rsp+2F0h+var_294], 0FFFFFFFFh
0x140013911  mov     dword ptr [rsp+2F0h+var_290], r13d
0x140013916  mov     byte ptr [rsp+2F0h+var_290+4], sil
0x14001391b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140013922  lea     rcx, [rsp+2F0h+var_2B0]; pExceptionObject
0x140013927  call    _CxxThrowException_0
0x14001392d  mov     r8d, 0Ah
0x140013933  lea     rdx, aChannels_1; "\\Channels\\"
0x14001393a  lea     rcx, [rbp+1F0h+Buf1]
0x14001393e  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x140013943  test    al, al
0x140013945  jz      loc_140013B92
0x14001394b  mov     rdx, [r14+0C8h]
0x140013952  mov     r8, [r14+0D0h]
0x140013959  sub     r8, rdx
0x14001395c  sar     r8, 1
0x14001395f  lea     rcx, [rbp+1F0h+Buf1]
0x140013963  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x140013968  test    al, al
0x14001396a  jz      loc_140013B92
0x140013970  lea     rcx, [rbp+1F0h+hKey]
0x140013974  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140013979  mov     [rsp+2F0h+lpData], r15; void *
0x14001397e  mov     r9, rax; HKEY *
0x140013981  mov     r8d, 2001Fh; unsigned int
0x140013987  mov     rdx, qword ptr [rbp+1F0h+Buf1]; wchar_t *
0x14001398b  mov     rcx, qword ptr [rsp+2F0h+Data+8]; HKEY
0x140013990  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x140013995  mov     r14d, eax
0x140013998  test    eax, eax
0x14001399a  jz      loc_140013A68
0x1400139a0  cmp     eax, 2
0x1400139a3  jz      loc_140013A30
0x1400139a9  lea     rdi, WPP_GLOBAL_Control
0x1400139b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400139b7  cmp     rcx, rdi
0x1400139ba  jz      short loc_1400139ED
0x1400139bc  mov     ebx, 4
0x1400139c1  test    [rcx+1Ch], bl
0x1400139c4  jz      short loc_1400139ED
0x1400139c6  cmp     byte ptr [rcx+19h], 2
0x1400139ca  jb      short loc_1400139ED
0x1400139cc  lea     edx, [rbx+15h]
0x1400139cf  mov     rax, qword ptr [rbp+1F0h+Buf1]
0x1400139d3  mov     [rsp+2F0h+lpData], rax
0x1400139d8  mov     r9d, r14d
0x1400139db  lea     r8, WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids
0x1400139e2  mov     rcx, [rcx+10h]
0x1400139e6  call    WPP_SF_DS
0x1400139eb  xor     esi, esi
0x1400139ed  lea     rax, word_14003838A
0x1400139f4  mov     [rsp+2F0h+var_2B0], rax
0x1400139f9  mov     [rsp+2F0h+var_2A8], rsi
0x1400139fe  mov     qword ptr [rsp+2F0h+var_2A0], 0
0x140013a07  mov     dword ptr [rsp+2F0h+var_29C+4], r14d
0x140013a0c  mov     dword ptr [rsp+2F0h+var_294], 0FFFFFFFFh
0x140013a14  mov     dword ptr [rsp+2F0h+var_290], r13d
0x140013a19  mov     byte ptr [rsp+2F0h+var_290+4], sil
0x140013a1e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140013a25  lea     rcx, [rsp+2F0h+var_2B0]; pExceptionObject
0x140013a2a  call    _CxxThrowException_0
0x140013a30  movaps  xmm0, [rbp+1F0h+var_C0]
0x140013a37  movdqu  xmmword ptr [rbp+1F0h+var_270.Data1], xmm0
0x140013a3c  mov     r8, r15; void *
0x140013a3f  lea     rdx, [rbp+1F0h+var_270]; struct _GUID
0x140013a43  mov     rcx, [rbp+1F0h+lpString1]; wchar_t *
0x140013a4a  call    ?DeleteSession@SessionConfig@@CAXPEB_WU_GUID@@PEAX@Z; SessionConfig::DeleteSession(wchar_t const *,_GUID,void *)
0x140013a4f  nop
0x140013a50  lea     rcx, [rbp+1F0h+pExceptionObject]
0x140013a54  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140013a59  nop
0x140013a5a  lea     rcx, [rbp+1F0h+Buf1]
0x140013a5e  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140013a63  jmp     loc_1400148F4
0x140013a68  lea     r9, [rbp+1F0h+var_250]; unsigned int *
0x140013a6c  lea     r8, aFilecounter; "FileCounter"
0x140013a73  mov     rcx, qword ptr [rsp+2F0h+Data]; HKEY
0x140013a78  call    ?RegReadDWORDValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAK@Z; RegReadDWORDValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &)
0x140013a7d  test    eax, eax
0x140013a7f  jnz     loc_140013B5B
0x140013a85  lea     r9, [rbp+1F0h+var_24C]; unsigned int *
0x140013a89  lea     r8, aFilecounter; "FileCounter"
0x140013a90  mov     rcx, [rbp+1F0h+hKey]; HKEY
0x140013a94  call    ?RegReadDWORDValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAK@Z; RegReadDWORDValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &)
0x140013a99  test    eax, eax
0x140013a9b  jnz     loc_140013B5B
0x140013aa1  mov     eax, [rbp+1F0h+var_250]
0x140013aa4  cmp     eax, [rbp+1F0h+var_24C]
0x140013aa7  jz      loc_140013B5B
0x140013aad  mov     dword ptr [rsp+2F0h+Data+8], eax
0x140013ab1  mov     ebx, 4
0x140013ab6  mov     [rsp+2F0h+cbData], ebx; cbData
0x140013aba  lea     rax, [rsp+2F0h+Data+8]
0x140013abf  mov     [rsp+2F0h+lpData], rax; lpData
0x140013ac4  mov     r9d, ebx; dwType
0x140013ac7  xor     r8d, r8d; Reserved
0x140013aca  lea     rdx, aFilecounter; "FileCounter"
0x140013ad1  mov     rcx, [rbp+1F0h+hKey]; hKey
0x140013ad5  call    cs:__imp_RegSetValueExW
0x140013adb  mov     r14d, eax
0x140013ade  test    eax, eax
0x140013ae0  jz      short loc_140013B5B
0x140013ae2  lea     rdi, WPP_GLOBAL_Control
0x140013ae9  mov     rcx, cs:WPP_GLOBAL_Control
0x140013af0  cmp     rcx, rdi
0x140013af3  jz      short loc_140013B18
0x140013af5  test    [rcx+1Ch], bl
0x140013af8  jz      short loc_140013B18
0x140013afa  cmp     byte ptr [rcx+19h], 2
0x140013afe  jb      short loc_140013B18
0x140013b00  lea     edx, [rbx+16h]
0x140013b03  mov     r9d, eax
0x140013b06  lea     r8, WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids
0x140013b0d  mov     rcx, [rcx+10h]
0x140013b11  call    WPP_SF_d
0x140013b16  xor     esi, esi
0x140013b18  lea     rax, word_14003838A
0x140013b1f  mov     [rsp+2F0h+var_2B0], rax
0x140013b24  mov     [rsp+2F0h+var_2A8], rsi
0x140013b29  mov     qword ptr [rsp+2F0h+var_2A0], 0
0x140013b32  mov     dword ptr [rsp+2F0h+var_29C+4], r14d
0x140013b37  mov     dword ptr [rsp+2F0h+var_294], 0FFFFFFFFh
0x140013b3f  mov     dword ptr [rsp+2F0h+var_290], r13d
0x140013b44  mov     byte ptr [rsp+2F0h+var_290+4], sil
0x140013b49  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140013b50  lea     rcx, [rsp+2F0h+var_2B0]; pExceptionObject
0x140013b55  call    _CxxThrowException_0
0x140013b5b  lea     rcx, [rbp+1F0h+pExceptionObject]
0x140013b5f  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140013b64  nop
0x140013b65  lea     rcx, [rbp+1F0h+Buf1]
0x140013b69  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140013b6e  movaps  xmm0, [rbp+1F0h+var_C0]
0x140013b75  movdqu  xmmword ptr [rbp+1F0h+var_270.Data1], xmm0
0x140013b7a  mov     r8, r15; void *
0x140013b7d  lea     rdx, [rbp+1F0h+var_270]; struct _GUID
0x140013b81  mov     rcx, [rbp+1F0h+lpString1]; wchar_t *
  ... truncated ...
```
