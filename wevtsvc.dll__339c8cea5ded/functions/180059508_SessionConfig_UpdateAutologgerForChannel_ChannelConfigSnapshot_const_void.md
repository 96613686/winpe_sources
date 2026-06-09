# SessionConfig::UpdateAutologgerForChannel(ChannelConfigSnapshot const &,void *)

- ea: `0x180059508`
- end: `0x18005a7de`
- name: `?UpdateAutologgerForChannel@SessionConfig@@SAXAEBVChannelConfigSnapshot@@PEAX@Z`
- size: `4822`
- prototype: `void __fastcall(const struct ChannelConfigSnapshot *, void *)`
- caller_count: `3`
- callee_count: `33`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180004f2c`
- `0x180057f1c`
- `0x1800840c8`

## callees

- `0x180006600`
- `0x180006770`
- `0x180009200`
- `0x180009260`
- `0x180014bd0`
- `0x18001722c`
- `0x180017b60`
- `0x180017b98`
- `0x180017e28`
- `0x18002a2cc`
- `0x18002d1dc`
- `0x18002d6dc`
- `0x180059508`
- `0x18005a814`
- `0x18005c2d4`
- `0x18005c600`
- `0x18006c144`
- `0x18006ea40`
- `0x18006ea98`
- `0x1800778a4`
- `0x180077ad0`
- `0x180077ddc`
- `0x180083b84`
- `0x180092008`
- `0x18009642c`
- `0x18009aee0`
- `0x18009bb88`
- `0x18009e770`
- `0x1800be3ac`
- `0x1800bf644`
- `0x1800bff1c`
- `0x1800d334c`
- `0x1800d3364`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005996c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180059c48`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180059ce5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180059d82`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180059e1f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180059ebc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180059f67`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005a13d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005a1d5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005a2e8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005a371`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005a412`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005996c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180059c48`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180059ce5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180059d82`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180059e1f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180059ebc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180059f67`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005a13d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005a1d5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005a2e8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005a371`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005a412`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005a2ac`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005a2ac`

## string_xrefs

- `0x18005a263`: `Security`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall SessionConfig::UpdateAutologgerForChannel(const struct ChannelConfigSnapshot *a1, void *a2)
{
  void *v3; // r8
  __int64 v4; // rax
  unsigned int PersistedAutoLoggerRegPath; // eax
  LSTATUS v6; // r15d
  HKEY *v7; // rax
  LSTATUS v8; // eax
  LSTATUS v9; // r15d
  __int64 v10; // rcx
  unsigned int WinevtRegPath; // eax
  int v12; // r15d
  HKEY *v13; // rax
  LSTATUS v14; // eax
  LSTATUS v15; // r14d
  unsigned int v16; // eax
  unsigned int v17; // r14d
  char v18; // r12
  struct _GUID v19; // xmm6
  HKEY *v20; // rax
  struct _SECURITY_ATTRIBUTES *const v21; // r9
  int v22; // eax
  int v23; // r15d
  const wchar_t *v24; // r9
  unsigned int v25; // eax
  unsigned int v26; // r15d
  unsigned int v27; // eax
  unsigned int v28; // r15d
  unsigned int v29; // eax
  unsigned int v30; // r15d
  unsigned int v31; // eax
  unsigned int v32; // r15d
  unsigned int v33; // eax
  unsigned int v34; // r15d
  unsigned int v35; // eax
  unsigned int v36; // r15d
  unsigned int v37; // eax
  int v38; // r15d
  int v39; // r12d
  unsigned int v40; // eax
  unsigned int v41; // r15d
  unsigned int v42; // eax
  unsigned int v43; // r15d
  unsigned int v44; // eax
  unsigned int v45; // r15d
  unsigned int v46; // eax
  unsigned int v47; // r15d
  unsigned int v48; // eax
  unsigned int v49; // r15d
  unsigned int v50; // eax
  int v51; // r15d
  unsigned int v52; // eax
  void *v53; // r8
  int v54; // r15d
  __int128 v55; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v56; // [rsp+58h] [rbp-B0h]
  int v57; // [rsp+60h] [rbp-A8h]
  __int64 v58; // [rsp+64h] [rbp-A4h]
  char v59; // [rsp+6Ch] [rbp-9Ch]
  HKEY Data[3]; // [rsp+70h] [rbp-98h] BYREF
  struct _GUID v61; // [rsp+88h] [rbp-80h] BYREF
  unsigned int v62; // [rsp+98h] [rbp-70h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp-68h] BYREF
  unsigned int v64; // [rsp+A8h] [rbp-60h] BYREF
  unsigned int v65; // [rsp+ACh] [rbp-5Ch] BYREF
  const wchar_t *pExceptionObject; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v67; // [rsp+B8h] [rbp-50h]
  __int64 v68; // [rsp+C0h] [rbp-48h]
  LSTATUS v69; // [rsp+C8h] [rbp-40h]
  int v70; // [rsp+CCh] [rbp-3Ch]
  int v71; // [rsp+D0h] [rbp-38h]
  char v72; // [rsp+D4h] [rbp-34h]
  struct _GUID Buf1[2]; // [rsp+D8h] [rbp-30h] BYREF
  wchar_t *v74[4]; // [rsp+F8h] [rbp-10h] BYREF
  _QWORD v75[4]; // [rsp+118h] [rbp+10h] BYREF
  _QWORD v76[4]; // [rsp+138h] [rbp+30h] BYREF
  LPCWCH lpString2[4]; // [rsp+158h] [rbp+50h] BYREF
  struct _EVENT_TRACE_PROPERTIES v78; // [rsp+178h] [rbp+70h] BYREF
  LPCWCH lpString1[8]; // [rsp+1F8h] [rbp+F0h] BYREF
  struct _GUID v80; // [rsp+238h] [rbp+130h]
  char v81[8]; // [rsp+248h] [rbp+140h] BYREF
  char v82[88]; // [rsp+250h] [rbp+148h] BYREF

  if ( !ChannelConfigSnapshot::IsOwnerOfEtwSession(a1) )
  {
    SessionConfig::UpdateProvidersForChannel(a1, 1, v3);
    return;
  }
  Data[0] = 0;
  hKey = 0;
  Data[1] = *((HKEY *)a1 + 25);
  Data[2] = (HKEY)((__int64)(*((_QWORD *)a1 + 26) - (unsigned __int64)Data[1]) >> 1);
  SessionConfig::EtwSessionForChannel::EtwSessionForChannel(
    lpString1,
    &Data[1],
    *((unsigned __int8 *)a1 + 249),
    *((unsigned __int8 *)a1 + 248));
  Data[1] = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v74);
  v4 = -1;
  do
    ++v4;
  while ( lpString1[0][v4] );
  *(LPCWCH *)&v61.Data1 = lpString1[0];
  *(_QWORD *)v61.Data4 = v4;
  PersistedAutoLoggerRegPath = RegistryPaths::GetPersistedAutoLoggerRegPath(lpString1[0], &v61, &Data[1], v74);
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
        &WPP_b172996960853cbcad4882dc20a972f5_Traceguids,
        PersistedAutoLoggerRegPath);
    }
    pExceptionObject = &byte_1800EC961;
    v67 = 0;
    v68 = 0;
    v69 = v6;
    v70 = -1;
    v71 = -1;
    v72 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  if ( *((_BYTE *)a1 + 251) )
  {
    SessionConfig::SessionConfig((SessionConfig *)v81, a1);
    memset_0(&v78, 0, sizeof(v78));
    SessionConfig::BuildTracePropsFromChannelRegistryConfig_Impl((SessionConfig *)v81, &v78);
    v18 = *((_BYTE *)a1 + 249);
    v19 = *(struct _GUID *)((char *)a1 + 8);
    Buf1[0] = v19;
    v62 = 0;
    v20 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(Data);
    v22 = CreateRegKey(Data[1], v74[0], 0x2001Fu, v21, v20, &v62, (void *)0xFFFFFFFFFFFFFFFFLL);
    v23 = v22;
    if ( v22 )
    {
      if ( v22 != 5
        || (*(_QWORD *)&v61.Data1 = *((_QWORD *)a1 + 25),
            *(_QWORD *)v61.Data4 = (__int64)(*((_QWORD *)a1 + 26) - *(_QWORD *)&v61.Data1) >> 1,
            !(unsigned __int8)IsSecurityChannel(&v61)) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_dS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            27,
            (unsigned int)&WPP_b172996960853cbcad4882dc20a972f5_Traceguids,
            v23,
            (__int64)v74[0]);
        }
        *(_QWORD *)&v55 = &byte_1800EC961;
        *((_QWORD *)&v55 + 1) = 0;
        v56 = 0;
        v57 = v23;
        v58 = -1;
        v59 = 0;
        throw (EvtException *)&v55;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v24 = L"Modifying";
        if ( v62 != 2 )
          v24 = L"Creating";
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          (unsigned int)&WPP_b172996960853cbcad4882dc20a972f5_Traceguids,
          (_DWORD)v24,
          (__int64)v74[0]);
      }
      LODWORD(Data[1]) = 1;
      v25 = RegSetValueExW(Data[0], L"Start", 0, 4u, (const BYTE *)&Data[1], 4u);
      v26 = v25;
      if ( v25 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v25);
        }
        *(_QWORD *)&v55 = &byte_1800EC961;
        *((_QWORD *)&v55 + 1) = 0;
        v56 = 0;
        v57 = v26;
        v58 = -1;
        v59 = 0;
        throw (EvtException *)&v55;
      }
      LODWORD(Data[1]) = v78.BufferSize;
      v27 = RegSetValueExW(Data[0], L"BufferSize", 0, 4u, (const BYTE *)&Data[1], 4u);
      v28 = v27;
      if ( v27 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v27);
        }
        *(_QWORD *)&v55 = &byte_1800EC961;
        *((_QWORD *)&v55 + 1) = 0;
        v56 = 0;
        v57 = v28;
        v58 = -1;
        v59 = 0;
        throw (EvtException *)&v55;
      }
      LODWORD(Data[1]) = v78.MinimumBuffers;
      v29 = RegSetValueExW(Data[0], L"MinimumBuffers", 0, 4u, (const BYTE *)&Data[1], 4u);
      v30 = v29;
      if ( v29 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v29);
        }
        *(_QWORD *)&v55 = &byte_1800EC961;
        *((_QWORD *)&v55 + 1) = 0;
        v56 = 0;
        v57 = v30;
        v58 = -1;
        v59 = 0;
        throw (EvtException *)&v55;
      }
      LODWORD(Data[1]) = v78.MaximumBuffers;
      v31 = RegSetValueExW(Data[0], L"MaximumBuffers", 0, 4u, (const BYTE *)&Data[1], 4u);
      v32 = v31;
      if ( v31 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v31);
        }
        *(_QWORD *)&v55 = &byte_1800EC961;
        *((_QWORD *)&v55 + 1) = 0;
        v56 = 0;
        v57 = v32;
        v58 = -1;
        v59 = 0;
        throw (EvtException *)&v55;
      }
      LODWORD(Data[1]) = v78.FlushTimer;
      v33 = RegSetValueExW(Data[0], L"FlushTimer", 0, 4u, (const BYTE *)&Data[1], 4u);
      v34 = v33;
      if ( v33 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v33);
        }
        *(_QWORD *)&v55 = &byte_1800EC961;
        *((_QWORD *)&v55 + 1) = 0;
        v56 = 0;
        v57 = v34;
        v58 = -1;
        v59 = 0;
        throw (EvtException *)&v55;
      }
      if ( (unsigned __int8)(v18 - 2) <= 1u )
      {
        LODWORD(Data[1]) = v78.MaximumFileSize;
        v35 = RegSetValueExW(Data[0], L"MaxFileSize", 0, 4u, (const BYTE *)&Data[1], 4u);
        v36 = v35;
        if ( v35 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v35);
          }
          *(_QWORD *)&v55 = &byte_1800EC961;
          *((_QWORD *)&v55 + 1) = 0;
          v56 = 0;
          v57 = v36;
          v58 = -1;
          v59 = 0;
          throw (EvtException *)&v55;
        }
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&pExceptionObject);
        *(_QWORD *)&v61.Data1 = *((_QWORD *)a1 + 7);
        *(_QWORD *)v61.Data4 = (__int64)(*((_QWORD *)a1 + 8) - *(_QWORD *)&v61.Data1) >> 1;
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(&pExceptionObject) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, 14);
          }
          v55 = 0;
          v56 = 0;
          v57 = 14;
          v58 = 0x1CBFFFFFFFFLL;
          throw (EvtException *)&v55;
        }
        *(_QWORD *)&v61.Data1 = pExceptionObject;
        *(_QWORD *)v61.Data4 = (v67 - (__int64)pExceptionObject) >> 1;
        v37 = RegWriteStringValueNoThrow(Data[0], L"FileName", &v61);
        v38 = v37;
        if ( v37 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v37);
          }
          *(_QWORD *)&v55 = &byte_1800EC961;
          *((_QWORD *)&v55 + 1) = 0;
          v56 = 0;
          v57 = v38;
          v58 = -1;
          v59 = 0;
          throw (EvtException *)&v55;
        }
        if ( *((_DWORD *)a1 + 10) > 1u )
        {
          v39 = *((_DWORD *)a1 + 11);
          LODWORD(Data[1]) = *((_DWORD *)a1 + 10);
          v40 = RegSetValueExW(Data[0], L"FileMax", 0, 4u, (const BYTE *)&Data[1], 4u);
          v41 = v40;
          if ( v40 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v40);
            }
            *(_QWORD *)&v55 = &byte_1800EC961;
            *((_QWORD *)&v55 + 1) = 0;
            v56 = 0;
            v57 = v41;
            v58 = -1;
            v59 = 0;
            throw (EvtException *)&v55;
          }
          LODWORD(Data[1]) = v39;
          v42 = RegSetValueExW(Data[0], L"FileCounter", 0, 4u, (const BYTE *)&Data[1], 4u);
          v43 = v42;
          if ( v42 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v42);
            }
            *(_QWORD *)&v55 = &byte_1800EC961;
            *((_QWORD *)&v55 + 1) = 0;
            v56 = 0;
            v57 = v43;
            v58 = -1;
            v59 = 0;
            throw (EvtException *)&v55;
          }
        }
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&pExceptionObject);
      }
      *(_OWORD *)&Data[1] = 0;
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpString2);
      *(_QWORD *)&v61.Data1 = L"Security";
      *(_QWORD *)v61.Data4 = 8;
      SessionConfig::EtwSessionForChannel::GetSessionNameAndGuid(&v61, lpString2, &Data[1]);
      if ( CompareStringOrdinal(lpString1[0], -1, lpString2[0], lpString2[1] - lpString2[0], 1) == 2 )
      {
        LODWORD(Data[1]) = v78.LogFileMode | 0x40;
        v44 = RegSetValueExW(Data[0], L"LogFileMode", 0, 4u, (const BYTE *)&Data[1], 4u);
        v45 = v44;
        if ( v44 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v44);
          }
          *(_QWORD *)&v55 = &byte_1800EC961;
          *((_QWORD *)&v55 + 1) = 0;
          v56 = 0;
          v57 = v45;
          v58 = -1;
          v59 = 0;
          throw (EvtException *)&v55;
        }
      }
      else
      {
        LODWORD(Data[1]) = v78.LogFileMode;
        v46 = RegSetValueExW(Data[0], L"LogFileMode", 0, 4u, (const BYTE *)&Data[1], 4u);
        v47 = v46;
        if ( v46 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v46);
          }
          *(_QWORD *)&v55 = &byte_1800EC961;
          *((_QWORD *)&v55 + 1) = 0;
          v56 = 0;
          v57 = v47;
          v58 = -1;
          v59 = 0;
          throw (EvtException *)&v55;
        }
      }
      LODWORD(Data[1]) = v78.Wnode.ClientContext;
      v48 = RegSetValueExW(Data[0], L"ClockType", 0, 4u, (const BYTE *)&Data[1], 4u);
      v49 = v48;
      if ( v48 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v48);
        }
        *(_QWORD *)&v55 = &byte_1800EC961;
        *((_QWORD *)&v55 + 1) = 0;
        v56 = 0;
        v57 = v49;
        v58 = -1;
        v59 = 0;
        throw (EvtException *)&v55;
      }
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v76);
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               v76,
                               lpString1[4]) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, 14);
        }
        v55 = 0;
        v56 = 0;
        v57 = 14;
        v58 = 0x1F3FFFFFFFFLL;
        throw (EvtException *)&v55;
      }
      *(_QWORD *)&v61.Data1 = v76[0];
      *(_QWORD *)v61.Data4 = (__int64)(v76[1] - v76[0]) >> 1;
      v50 = RegWriteStringValueNoThrow(Data[0], L"Guid", &v61);
      v51 = v50;
      if ( v50 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v50);
        }
        *(_QWORD *)&v55 = &byte_1800EC961;
        *((_QWORD *)&v55 + 1) = 0;
        v56 = 0;
        v57 = v51;
        v58 = -1;
        v59 = 0;
        throw (EvtException *)&v55;
      }
      if ( memcmp_0(Buf1, &GUID_NULL, 0x10u) )
      {
        Buf1[0] = v19;
        SessionConfig::UpdateProvider(Buf1, a1, 0, 1, (void *)0xFFFFFFFFFFFFFFFFLL);
      }
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v75);
      *(_QWORD *)&v61.Data1 = *((_QWORD *)a1 + 25);
      *(_QWORD *)v61.Data4 = (__int64)(*((_QWORD *)a1 + 26) - *(_QWORD *)&v61.Data1) >> 1;
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v75) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, 14);
        }
        v55 = 0;
        v56 = 0;
        v57 = 14;
        v58 = 0x202FFFFFFFFLL;
        throw (EvtException *)&v55;
      }
      *(_QWORD *)&v61.Data1 = v75[0];
      *(_QWORD *)v61.Data4 = (__int64)(v75[1] - v75[0]) >> 1;
      v52 = RegWriteStringValueNoThrow(Data[0], L"OwningChannel", &v61);
      v54 = v52;
      if ( v52 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v52);
        }
        *(_QWORD *)&v55 = &byte_1800EC961;
        *((_QWORD *)&v55 + 1) = 0;
        v56 = 0;
        v57 = v54;
        v58 = -1;
        v59 = 0;
        throw (EvtException *)&v55;
      }
      if ( v62 != 2
        || (*(_QWORD *)&v61.Data1 = *((_QWORD *)a1 + 25),
            *(_QWORD *)v61.Data4 = (__int64)(*((_QWORD *)a1 + 26) - *(_QWORD *)&v61.Data1) >> 1,
            !(unsigned __int8)IsCoreChannel(&v61)) )
      {
        SessionConfig::UpdateProvidersForChannel(a1, 1, v53);
      }
      SessionConfig::SetSessionSecurity(a1, 0, (void *)0xFFFFFFFFFFFFFFFFLL);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v75);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v76);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpString2);
    }
    utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>::~pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(v82);
    goto LABEL_178;
  }
  v65 = 0;
  v64 = 0;
  v7 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(Data);
  v8 = OpenRegKey(Data[1], v74[0], 0x20019u, v7, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  v9 = v8;
  if ( v8 )
  {
    if ( v8 != 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_dS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          (unsigned int)&WPP_b172996960853cbcad4882dc20a972f5_Traceguids,
          v8,
          (__int64)v74[0]);
      }
      pExceptionObject = &byte_1800EC961;
      v67 = 0;
      v68 = 0;
      v69 = v9;
      v70 = -1;
      v71 = -1;
      v72 = 0;
      throw (EvtException *)&pExceptionObject;
    }
  }
  else
  {
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(Buf1);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&pExceptionObject);
    WinevtRegPath = RegistryPaths::GetWinevtRegPath(v10, &Data[1], (__int64 *)Buf1, (__int64)&pExceptionObject);
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
          &WPP_b172996960853cbcad4882dc20a972f5_Traceguids,
          WinevtRegPath);
      }
      *(_QWORD *)&v55 = &byte_1800EC961;
      *((_QWORD *)&v55 + 1) = 0;
      v56 = 0;
      v57 = v12;
      v58 = -1;
      v59 = 0;
      throw (EvtException *)&v55;
    }
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(Buf1)
      || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(Buf1) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, 14);
      }
      v55 = 0;
      v56 = 0;
      v57 = 14;
      v58 = 0x177FFFFFFFFLL;
      throw (EvtException *)&v55;
    }
    v13 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    v14 = OpenRegKey(Data[1], *(const wchar_t **)&Buf1[0].Data1, 0x2001Fu, v13, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    v15 = v14;
    if ( v14 )
    {
      if ( v14 != 2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_dS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            (unsigned int)&WPP_b172996960853cbcad4882dc20a972f5_Traceguids,
            v14,
            *(__int64 *)&Buf1[0].Data1);
        }
        *(_QWORD *)&v55 = &byte_1800EC961;
        *((_QWORD *)&v55 + 1) = 0;
        v56 = 0;
        v57 = v15;
        v58 = -1;
        v59 = 0;
        throw (EvtException *)&v55;
      }
      v61 = v80;
      SessionConfig::DeleteSession(lpString1[0], &v61, (void *)0xFFFFFFFFFFFFFFFFLL);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&pExceptionObject);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(Buf1);
      goto LABEL_178;
    }
    if ( !(unsigned int)RegReadDWORDValueNoThrow(Data[0], 0, L"FileCounter", &v64)
      && !(unsigned int)RegReadDWORDValueNoThrow(hKey, 0, L"FileCounter", &v65)
      && v64 != v65 )
    {
      LODWORD(Data[1]) = v64;
      v16 = RegSetValueExW(hKey, L"FileCounter", 0, 4u, (const BYTE *)&Data[1], 4u);
      v17 = v16;
      if ( v16 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v16);
        }
        *(_QWORD *)&v55 = &byte_1800EC961;
        *((_QWORD *)&v55 + 1) = 0;
        v56 = 0;
        v57 = v17;
        v58 = -1;
        v59 = 0;
        throw (EvtException *)&v55;
      }
    }
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&pExceptionObject);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(Buf1);
  }
  v61 = v80;
  SessionConfig::DeleteSession(lpString1[0], &v61, (void *)0xFFFFFFFFFFFFFFFFLL);
LABEL_178:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v74);
  utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>::~pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(lpString1);
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(Data);
}

```

## disassembly

```asm
0x180059508  mov     rax, rsp
0x18005950b  push    rbp
0x18005950c  push    rbx
0x18005950d  push    rsi
0x18005950e  push    rdi
0x18005950f  push    r12
0x180059511  push    r13
0x180059513  push    r14
0x180059515  push    r15
0x180059517  lea     rbp, [rax-208h]
0x18005951e  sub     rsp, 2C8h
0x180059525  movaps  xmmword ptr [rax-58h], xmm6
0x180059529  mov     rax, cs:__security_cookie
0x180059530  xor     rax, rsp
0x180059533  mov     [rbp+200h+var_60], rax
0x18005953a  mov     r14, rcx
0x18005953d  call    ?IsOwnerOfEtwSession@ChannelConfigSnapshot@@QEBA_NXZ; ChannelConfigSnapshot::IsOwnerOfEtwSession(void)
0x180059542  xor     r13d, r13d
0x180059545  test    al, al
0x180059547  jnz     short loc_180059558
0x180059549  mov     dl, 1; bool
0x18005954b  mov     rcx, r14; struct ChannelConfigSnapshot *
0x18005954e  call    ?UpdateProvidersForChannel@SessionConfig@@CAXAEBVChannelConfigSnapshot@@_NPEAX@Z; SessionConfig::UpdateProvidersForChannel(ChannelConfigSnapshot const &,bool,void *)
0x180059553  jmp     loc_18005A7B3
0x180059558  mov     qword ptr [rsp+300h+Data], r13
0x18005955d  mov     [rbp+200h+hKey], r13
0x180059561  mov     rax, [r14+0C8h]
0x180059568  mov     qword ptr [rsp+300h+Data+8], rax
0x18005956d  mov     rcx, [r14+0D0h]
0x180059574  sub     rcx, rax
0x180059577  sar     rcx, 1
0x18005957a  mov     qword ptr [rsp+300h+Data+10h], rcx
0x18005957f  movzx   r9d, byte ptr [r14+0F8h]
0x180059587  movzx   r8d, byte ptr [r14+0F9h]
0x18005958f  lea     rdx, [rsp+300h+Data+8]
0x180059594  lea     rcx, [rbp+200h+lpString1]
0x18005959b  call    ??0EtwSessionForChannel@SessionConfig@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@W4_EVT_CHANNEL_TYPE@@W4_EVT_CHANNEL_ISOLATION_TYPE@@@Z; SessionConfig::EtwSessionForChannel::EtwSessionForChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,_EVT_CHANNEL_TYPE,_EVT_CHANNEL_ISOLATION_TYPE)
0x1800595a0  nop
0x1800595a1  mov     qword ptr [rsp+300h+Data+8], r13
0x1800595a6  lea     rcx, [rbp+200h+var_210]; void *
0x1800595aa  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800595af  nop
0x1800595b0  mov     rcx, [rbp+200h+lpString1]
0x1800595b7  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800595bb  mov     rax, r12
0x1800595be  inc     rax
0x1800595c1  cmp     [rcx+rax*2], r13w
0x1800595c6  jnz     short loc_1800595BE
0x1800595c8  mov     qword ptr [rbp+200h+var_280.Data1], rcx
0x1800595cc  mov     qword ptr [rbp+200h+var_280.Data4], rax
0x1800595d0  lea     r9, [rbp+200h+var_210]
0x1800595d4  lea     r8, [rsp+300h+Data+8]
0x1800595d9  lea     rdx, [rbp+200h+var_280]
0x1800595dd  call    ?GetPersistedAutoLoggerRegPath@RegistryPaths@@QEBAKV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@AEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@3@@Z; RegistryPaths::GetPersistedAutoLoggerRegPath(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1800595e2  mov     r15d, eax
0x1800595e5  test    eax, eax
0x1800595e7  jz      short loc_180059659
0x1800595e9  lea     rdi, WPP_GLOBAL_Control
0x1800595f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800595f7  cmp     rcx, rdi
0x1800595fa  jz      short loc_180059622
0x1800595fc  mov     ebx, 4
0x180059601  test    [rcx+1Ch], bl
0x180059604  jz      short loc_180059622
0x180059606  cmp     byte ptr [rcx+19h], 2
0x18005960a  jb      short loc_180059622
0x18005960c  lea     edx, [rbx+11h]
0x18005960f  mov     r9d, eax
0x180059612  lea     r8, WPP_b172996960853cbcad4882dc20a972f5_Traceguids
0x180059619  mov     rcx, [rcx+10h]
0x18005961d  call    WPP_SF_d
0x180059622  lea     rax, byte_1800EC961
0x180059629  mov     [rbp+200h+pExceptionObject], rax
0x18005962d  mov     [rbp+200h+var_250], r13
0x180059631  mov     [rbp+200h+var_248], r13
0x180059635  mov     [rbp+200h+var_240], r15d
0x180059639  mov     [rbp+200h+var_23C], 0FFFFFFFFh
0x180059640  mov     [rbp+200h+var_238], r12d
0x180059644  mov     [rbp+200h+var_234], r13b
0x180059648  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18005964f  lea     rcx, [rbp+200h+pExceptionObject]; pExceptionObject
0x180059653  call    _CxxThrowException_0
0x180059659  cmp     [r14+0FBh], r13b
0x180059660  jnz     loc_180059A96
0x180059666  mov     [rbp+200h+var_25C], r13d
0x18005966a  mov     [rbp+200h+var_260], r13d
0x18005966e  lea     rcx, [rsp+300h+Data]
0x180059673  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180059678  mov     [rsp+300h+lpData], r12; void *
0x18005967d  mov     r9, rax; HKEY *
0x180059680  mov     r8d, 20019h; unsigned int
0x180059686  mov     rdx, [rbp+200h+var_210]; wchar_t *
0x18005968a  mov     rcx, qword ptr [rsp+300h+Data+8]; HKEY
0x18005968f  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x180059694  mov     r15d, eax
0x180059697  test    eax, eax
0x180059699  jz      loc_180059721
0x18005969f  cmp     eax, 2
0x1800596a2  jz      loc_1800599FF
0x1800596a8  lea     rdi, WPP_GLOBAL_Control
0x1800596af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800596b6  cmp     rcx, rdi
0x1800596b9  jz      short loc_1800596EA
0x1800596bb  mov     ebx, 4
0x1800596c0  test    [rcx+1Ch], bl
0x1800596c3  jz      short loc_1800596EA
0x1800596c5  cmp     byte ptr [rcx+19h], 2
0x1800596c9  jb      short loc_1800596EA
0x1800596cb  lea     edx, [rbx+12h]
0x1800596ce  mov     rax, [rbp+200h+var_210]
0x1800596d2  mov     [rsp+300h+lpData], rax
0x1800596d7  mov     r9d, r15d
0x1800596da  lea     r8, WPP_b172996960853cbcad4882dc20a972f5_Traceguids
0x1800596e1  mov     rcx, [rcx+10h]
0x1800596e5  call    WPP_SF_dS
0x1800596ea  lea     rax, byte_1800EC961
0x1800596f1  mov     [rbp+200h+pExceptionObject], rax
0x1800596f5  mov     [rbp+200h+var_250], r13
0x1800596f9  mov     [rbp+200h+var_248], r13
0x1800596fd  mov     [rbp+200h+var_240], r15d
0x180059701  mov     [rbp+200h+var_23C], 0FFFFFFFFh
0x180059708  mov     [rbp+200h+var_238], r12d
0x18005970c  mov     [rbp+200h+var_234], r13b
0x180059710  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180059717  lea     rcx, [rbp+200h+pExceptionObject]; pExceptionObject
0x18005971b  call    _CxxThrowException_0
0x180059721  lea     rcx, [rbp+200h+Buf1]; void *
0x180059725  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18005972a  nop
0x18005972b  lea     rcx, [rbp+200h+pExceptionObject]; void *
0x18005972f  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180059734  nop
0x180059735  lea     r9, [rbp+200h+pExceptionObject]
0x180059739  lea     r8, [rbp+200h+Buf1]
0x18005973d  lea     rdx, [rsp+300h+Data+8]
0x180059742  call    ?GetWinevtRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; RegistryPaths::GetWinevtRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x180059747  mov     r15d, eax
0x18005974a  test    eax, eax
0x18005974c  jz      short loc_1800597C6
0x18005974e  lea     rdi, WPP_GLOBAL_Control
0x180059755  mov     rcx, cs:WPP_GLOBAL_Control
0x18005975c  cmp     rcx, rdi
0x18005975f  jz      short loc_180059787
0x180059761  mov     ebx, 4
0x180059766  test    [rcx+1Ch], bl
0x180059769  jz      short loc_180059787
0x18005976b  cmp     byte ptr [rcx+19h], 2
0x18005976f  jb      short loc_180059787
0x180059771  lea     edx, [rbx+13h]
0x180059774  mov     r9d, eax
0x180059777  lea     r8, WPP_b172996960853cbcad4882dc20a972f5_Traceguids
0x18005977e  mov     rcx, [rcx+10h]
0x180059782  call    WPP_SF_d
0x180059787  lea     rax, byte_1800EC961
0x18005978e  mov     qword ptr [rsp+300h+var_2C8+8], rax
0x180059793  mov     [rsp+300h+var_2B8], r13
0x180059798  mov     qword ptr [rsp+300h+var_2B0], r13
0x18005979d  mov     dword ptr [rsp+300h+var_2AC+4], r15d
0x1800597a2  mov     dword ptr [rsp+300h+var_2A4], 0FFFFFFFFh
0x1800597aa  mov     dword ptr [rsp+300h+var_2A0], r12d
0x1800597af  mov     byte ptr [rsp+300h+var_2A0+4], r13b
0x1800597b4  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800597bb  lea     rcx, [rsp+300h+var_2C8+8]; pExceptionObject
0x1800597c0  call    _CxxThrowException_0
0x1800597c6  mov     r8d, 0Ah
0x1800597cc  lea     rdx, aChannels_1; "\\Channels\\"
0x1800597d3  lea     rcx, [rbp+200h+Buf1]
0x1800597d7  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x1800597dc  test    al, al
0x1800597de  jz      loc_180059A23
0x1800597e4  mov     rdx, [r14+0C8h]
0x1800597eb  mov     r8, [r14+0D0h]
0x1800597f2  sub     r8, rdx
0x1800597f5  sar     r8, 1
0x1800597f8  lea     rcx, [rbp+200h+Buf1]
0x1800597fc  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x180059801  test    al, al
0x180059803  jz      loc_180059A23
0x180059809  lea     rcx, [rbp+200h+hKey]
0x18005980d  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180059812  mov     [rsp+300h+lpData], r12; void *
0x180059817  mov     r9, rax; HKEY *
0x18005981a  mov     r8d, 2001Fh; unsigned int
0x180059820  mov     rdx, qword ptr [rbp+200h+Buf1]; wchar_t *
0x180059824  mov     rcx, qword ptr [rsp+300h+Data+8]; HKEY
0x180059829  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x18005982e  mov     r14d, eax
0x180059831  test    eax, eax
0x180059833  jz      loc_1800598FB
0x180059839  cmp     eax, 2
0x18005983c  jz      loc_1800598C3
0x180059842  lea     rdi, WPP_GLOBAL_Control
0x180059849  mov     rcx, cs:WPP_GLOBAL_Control
0x180059850  cmp     rcx, rdi
0x180059853  jz      short loc_180059884
0x180059855  mov     ebx, 4
0x18005985a  test    [rcx+1Ch], bl
0x18005985d  jz      short loc_180059884
0x18005985f  cmp     byte ptr [rcx+19h], 2
0x180059863  jb      short loc_180059884
0x180059865  lea     edx, [rbx+15h]
0x180059868  mov     rax, qword ptr [rbp+200h+Buf1]
0x18005986c  mov     [rsp+300h+lpData], rax
0x180059871  mov     r9d, r14d
0x180059874  lea     r8, WPP_b172996960853cbcad4882dc20a972f5_Traceguids
0x18005987b  mov     rcx, [rcx+10h]
0x18005987f  call    WPP_SF_dS
0x180059884  lea     rax, byte_1800EC961
0x18005988b  mov     qword ptr [rsp+300h+var_2C8+8], rax
0x180059890  mov     [rsp+300h+var_2B8], r13
0x180059895  mov     qword ptr [rsp+300h+var_2B0], r13
0x18005989a  mov     dword ptr [rsp+300h+var_2AC+4], r14d
0x18005989f  mov     dword ptr [rsp+300h+var_2A4], 0FFFFFFFFh
0x1800598a7  mov     dword ptr [rsp+300h+var_2A0], r12d
0x1800598ac  mov     byte ptr [rsp+300h+var_2A0+4], r13b
0x1800598b1  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800598b8  lea     rcx, [rsp+300h+var_2C8+8]; pExceptionObject
0x1800598bd  call    _CxxThrowException_0
0x1800598c3  movaps  xmm0, [rbp+200h+var_D0]
0x1800598ca  movdqu  xmmword ptr [rbp+200h+var_280.Data1], xmm0
0x1800598cf  mov     r8, r12; void *
0x1800598d2  lea     rdx, [rbp+200h+var_280]; struct _GUID
0x1800598d6  mov     rcx, [rbp+200h+lpString1]; wchar_t *
0x1800598dd  call    ?DeleteSession@SessionConfig@@CAXPEB_WU_GUID@@PEAX@Z; SessionConfig::DeleteSession(wchar_t const *,_GUID,void *)
0x1800598e2  nop
0x1800598e3  lea     rcx, [rbp+200h+pExceptionObject]; void *
0x1800598e7  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800598ec  nop
0x1800598ed  lea     rcx, [rbp+200h+Buf1]; void *
0x1800598f1  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800598f6  jmp     loc_18005A788
0x1800598fb  lea     r9, [rbp+200h+var_260]; unsigned int *
0x1800598ff  lea     r8, aFilecounter; "FileCounter"
0x180059906  xor     edx, edx; wchar_t *
0x180059908  mov     rcx, qword ptr [rsp+300h+Data]; HKEY
0x18005990d  call    ?RegReadDWORDValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAK@Z; RegReadDWORDValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &)
0x180059912  test    eax, eax
0x180059914  jnz     loc_1800599EC
0x18005991a  lea     r9, [rbp+200h+var_25C]; unsigned int *
0x18005991e  lea     r8, aFilecounter; "FileCounter"
0x180059925  xor     edx, edx; wchar_t *
0x180059927  mov     rcx, [rbp+200h+hKey]; HKEY
0x18005992b  call    ?RegReadDWORDValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAK@Z; RegReadDWORDValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &)
0x180059930  test    eax, eax
0x180059932  jnz     loc_1800599EC
0x180059938  mov     eax, [rbp+200h+var_260]
0x18005993b  cmp     eax, [rbp+200h+var_25C]
0x18005993e  jz      loc_1800599EC
0x180059944  mov     dword ptr [rsp+300h+Data+8], eax
0x180059948  mov     ebx, 4
0x18005994d  mov     [rsp+300h+cbData], ebx; cbData
0x180059951  lea     rax, [rsp+300h+Data+8]
0x180059956  mov     [rsp+300h+lpData], rax; lpData
0x18005995b  mov     r9d, ebx; dwType
0x18005995e  xor     r8d, r8d; Reserved
0x180059961  lea     rdx, aFilecounter; "FileCounter"
0x180059968  mov     rcx, [rbp+200h+hKey]; hKey
0x18005996c  call    cs:__imp_RegSetValueExW
0x180059972  mov     r14d, eax
0x180059975  test    eax, eax
0x180059977  jz      short loc_1800599EC
0x180059979  lea     rdi, WPP_GLOBAL_Control
0x180059980  mov     rcx, cs:WPP_GLOBAL_Control
0x180059987  cmp     rcx, rdi
0x18005998a  jz      short loc_1800599AD
0x18005998c  test    [rcx+1Ch], bl
0x18005998f  jz      short loc_1800599AD
0x180059991  cmp     byte ptr [rcx+19h], 2
0x180059995  jb      short loc_1800599AD
0x180059997  lea     edx, [rbx+16h]
0x18005999a  mov     r9d, eax
0x18005999d  lea     r8, WPP_b172996960853cbcad4882dc20a972f5_Traceguids
0x1800599a4  mov     rcx, [rcx+10h]
0x1800599a8  call    WPP_SF_d
0x1800599ad  lea     rax, byte_1800EC961
0x1800599b4  mov     qword ptr [rsp+300h+var_2C8+8], rax
0x1800599b9  mov     [rsp+300h+var_2B8], r13
0x1800599be  mov     qword ptr [rsp+300h+var_2B0], r13
0x1800599c3  mov     dword ptr [rsp+300h+var_2AC+4], r14d
0x1800599c8  mov     dword ptr [rsp+300h+var_2A4], 0FFFFFFFFh
0x1800599d0  mov     dword ptr [rsp+300h+var_2A0], r12d
0x1800599d5  mov     byte ptr [rsp+300h+var_2A0+4], r13b
0x1800599da  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800599e1  lea     rcx, [rsp+300h+var_2C8+8]; pExceptionObject
0x1800599e6  call    _CxxThrowException_0
0x1800599ec  lea     rcx, [rbp+200h+pExceptionObject]; void *
0x1800599f0  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800599f5  nop
0x1800599f6  lea     rcx, [rbp+200h+Buf1]; void *
0x1800599fa  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800599ff  movaps  xmm0, [rbp+200h+var_D0]
0x180059a06  movdqu  xmmword ptr [rbp+200h+var_280.Data1], xmm0
0x180059a0b  mov     r8, r12; void *
0x180059a0e  lea     rdx, [rbp+200h+var_280]; struct _GUID
0x180059a12  mov     rcx, [rbp+200h+lpString1]; wchar_t *
0x180059a19  call    ?DeleteSession@SessionConfig@@CAXPEB_WU_GUID@@PEAX@Z; SessionConfig::DeleteSession(wchar_t const *,_GUID,void *)
0x180059a1e  jmp     loc_18005A788
0x180059a23  lea     rdi, WPP_GLOBAL_Control
0x180059a2a  mov     r14d, 0Eh
0x180059a30  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
