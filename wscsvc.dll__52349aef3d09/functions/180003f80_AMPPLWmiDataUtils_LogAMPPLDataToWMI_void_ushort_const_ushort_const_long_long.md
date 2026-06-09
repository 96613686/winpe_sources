# AMPPLWmiDataUtils::LogAMPPLDataToWMI(void *,ushort const *,ushort const *,long,long)

- ea: `0x180003f80`
- end: `0x180005212`
- name: `?LogAMPPLDataToWMI@AMPPLWmiDataUtils@@YAJPEAXPEBG1JJ@Z`
- size: `4754`
- prototype: `__int64 __fastcall(AMPPLWmiDataUtils *this, OLECHAR *, const unsigned __int16 *, const unsigned __int16 *, LONG)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180025520`
- `0x180031cd0`

## callees

- `0x180003f80`
- `0x180005220`
- `0x180005308`
- `0x180005650`
- `0x180005710`
- `0x1800062d0`
- `0x180008e48`
- `0x180018750`
- `0x1800202e8`
- `0x180029e74`
- `0x18002a762`
- `0x18002b1ac`
- `0x18002fbb4`
- `0x18003fc30`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004954`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004bab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004bec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004954`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004bab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004bec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800048a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004945`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800048a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004945`
- `RPCRT4!RpcRevertToSelf` at `0x180004170`
- `RPCRT4!RpcRevertToSelf` at `0x180004170`
- `RPCRT4!RpcImpersonateClient` at `0x180004063`
- `RPCRT4!RpcImpersonateClient` at `0x180004063`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180004111`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180004111`
- `RPCRT4!RpcRaiseException` at `0x180004ba4`
- `RPCRT4!RpcRaiseException` at `0x180004ba4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800040b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800040b0`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000409e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000409e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800048da`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800048da`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180004903`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180004903`
- `OLEAUT32!__imp_SysAllocString` at `0x1800041ef`
- `OLEAUT32!__imp_SysAllocString` at `0x180004295`
- `OLEAUT32!__imp_SysAllocString` at `0x1800042f1`
- `OLEAUT32!__imp_SysAllocString` at `0x180004347`
- `OLEAUT32!__imp_SysAllocString` at `0x18000439d`
- `OLEAUT32!__imp_SysAllocString` at `0x18000442d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800041ef`
- `OLEAUT32!__imp_SysAllocString` at `0x180004295`
- `OLEAUT32!__imp_SysAllocString` at `0x1800042f1`
- `OLEAUT32!__imp_SysAllocString` at `0x180004347`
- `OLEAUT32!__imp_SysAllocString` at `0x18000439d`
- `OLEAUT32!__imp_SysAllocString` at `0x18000442d`
- `OLEAUT32!__imp_SysFreeString` at `0x180004586`
- `OLEAUT32!__imp_SysFreeString` at `0x180004713`
- `OLEAUT32!__imp_SysFreeString` at `0x180004a59`
- `OLEAUT32!__imp_SysFreeString` at `0x180004aae`
- `OLEAUT32!__imp_SysFreeString` at `0x180004586`
- `OLEAUT32!__imp_SysFreeString` at `0x180004713`
- `OLEAUT32!__imp_SysFreeString` at `0x180004a59`
- `OLEAUT32!__imp_SysFreeString` at `0x180004aae`
- `OLEAUT32!__imp_VariantInit` at `0x18000427c`
- `OLEAUT32!__imp_VariantInit` at `0x18000427c`
- `OLEAUT32!__imp_VariantClear` at `0x1800042d5`
- `OLEAUT32!__imp_VariantClear` at `0x180004331`
- `OLEAUT32!__imp_VariantClear` at `0x180004387`
- `OLEAUT32!__imp_VariantClear` at `0x1800043e1`
- `OLEAUT32!__imp_VariantClear` at `0x18000446a`
- `OLEAUT32!__imp_VariantClear` at `0x1800044bb`
- `OLEAUT32!__imp_VariantClear` at `0x18000450f`
- `OLEAUT32!__imp_VariantClear` at `0x1800042d5`
- `OLEAUT32!__imp_VariantClear` at `0x180004331`
- `OLEAUT32!__imp_VariantClear` at `0x180004387`
- `OLEAUT32!__imp_VariantClear` at `0x1800043e1`
- `OLEAUT32!__imp_VariantClear` at `0x18000446a`
- `OLEAUT32!__imp_VariantClear` at `0x1800044bb`
- `OLEAUT32!__imp_VariantClear` at `0x18000450f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180004085`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180004085`

## string_xrefs

- `0x1800043bd`: `pathToSignedProductExe`
- `0x180004314`: `pathToCaller`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AMPPLWmiDataUtils::LogAMPPLDataToWMI(
        AMPPLWmiDataUtils *this,
        OLECHAR *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        LONG a5)
{
  OLECHAR *v5; // r13
  unsigned __int16 *v7; // r15
  void *v8; // r14
  void *v9; // rsi
  void *v10; // rdx
  struct CExternalBase **v11; // r9
  __int64 v12; // rdx
  CThirdPartyManager *v13; // rdi
  CSecurityVerificationManager *v14; // r12
  unsigned int v15; // eax
  int ExternalBaseFromPESettings; // edi
  bool v17; // sf
  signed int v18; // ebx
  unsigned int v19; // eax
  CThirdPartyManager *v20; // r10
  bool v21; // sf
  const OLECHAR *v22; // r12
  __int64 v23; // rcx
  struct CWmiEventManagerAvFw *v24; // rbx
  __int64 v25; // rcx
  __int64 v26; // r15
  OLECHAR *v27; // rdi
  int v28; // eax
  HRESULT v29; // eax
  int v30; // eax
  HRESULT v31; // eax
  int v32; // eax
  HRESULT v33; // eax
  int v34; // eax
  HRESULT v35; // eax
  unsigned __int16 **v36; // r8
  int WscIniConfiguration; // eax
  OLECHAR *v38; // rbx
  const OLECHAR *v39; // rcx
  int v40; // eax
  HRESULT v41; // eax
  int v42; // eax
  HRESULT v43; // eax
  int v44; // eax
  HRESULT v45; // eax
  int v46; // eax
  unsigned int v47; // r12d
  void (__fastcall ***v48)(_QWORD, __int64); // rcx
  _WORD *v50; // rdi
  __int64 v51; // rax
  __int64 v52; // rsi
  size_t v53; // rax
  unsigned __int64 v54; // kr00_8
  void *v55; // rax
  _WORD *v56; // rdi
  __int64 v57; // rax
  __int64 v58; // r15
  size_t v59; // rax
  unsigned __int64 v60; // kr10_8
  void *v61; // rax
  DWORD v62; // eax
  unsigned __int64 v63; // rax
  unsigned __int64 v64; // rbx
  size_t v65; // rax
  unsigned __int16 *v66; // rax
  unsigned __int16 *v67; // r12
  __int64 v68; // rcx
  WCHAR *v69; // rdx
  WCHAR *v70; // r8
  WCHAR v71; // ax
  WCHAR *v72; // rcx
  HANDLE v73; // rax
  void *v74; // r13
  __int64 v75; // rax
  DWORD LastError; // eax
  __int64 v77; // rax
  _SECURITY_PRODUCT_TYPE v78[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v79; // [rsp+48h] [rbp-B8h] BYREF
  WINBOOL IsMember[2]; // [rsp+50h] [rbp-B0h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v82; // [rsp+70h] [rbp-90h] BYREF
  __int64 v83; // [rsp+78h] [rbp-88h] BYREF
  LONG v84; // [rsp+80h] [rbp-80h]
  PSID Sid; // [rsp+88h] [rbp-78h] BYREF
  OLECHAR *v86; // [rsp+90h] [rbp-70h]
  const unsigned __int16 *v87; // [rsp+98h] [rbp-68h]
  void *v88; // [rsp+A0h] [rbp-60h]
  void *v89; // [rsp+A8h] [rbp-58h]
  struct CSecurityVerificationManager *v90; // [rsp+B0h] [rbp-50h]
  int RpcCallAttributes; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v92; // [rsp+C4h] [rbp-3Ch]
  int v93; // [rsp+CCh] [rbp-34h]
  __int128 v94; // [rsp+D0h] [rbp-30h]
  __int128 v95; // [rsp+E0h] [rbp-20h]
  __int128 v96; // [rsp+F0h] [rbp-10h]
  DWORD dwProcessId[4]; // [rsp+100h] [rbp+0h]
  __int128 v98; // [rsp+110h] [rbp+10h]
  __int128 v99; // [rsp+120h] [rbp+20h]
  __int64 v100; // [rsp+130h] [rbp+30h]
  WCHAR ExeName[268]; // [rsp+140h] [rbp+40h] BYREF

  v84 = (int)a4;
  v87 = a3;
  v5 = a2;
  v86 = a2;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::GetImpl'::`2'::impl,
    a2);
  v7 = 0;
  *(_QWORD *)v78 = 0;
  v8 = 0;
  v88 = 0;
  v9 = 0;
  v89 = 0;
  v83 = 0;
  if ( (int)WscServiceUtils::PopulateExternalBaseFromExistingRegistration(
              this,
              v10,
              (enum _SECURITY_PRODUCT_TYPE)v78,
              v11) >= 0 )
  {
    v50 = *(_WORD **)(*(_QWORD *)v78 + 16LL);
    v51 = -1;
    do
      ++v51;
    while ( v50[v51] );
    v52 = v51 + 1;
    v54 = v51 + 1;
    v53 = 2 * (v51 + 1);
    if ( !is_mul_ok(v54, 2u) )
      v53 = -1;
    v55 = operator new[](v53, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v55;
    v88 = v55;
    if ( v55 )
      memmove_0(v55, v50, 2 * v52);
    v56 = *(_WORD **)(*(_QWORD *)v78 + 24LL);
    v57 = -1;
    do
      ++v57;
    while ( v56[v57] );
    v58 = v57 + 1;
    v60 = v57 + 1;
    v59 = 2 * (v57 + 1);
    if ( !is_mul_ok(v60, 2u) )
      v59 = -1;
    v61 = operator new[](v59, (const struct std::nothrow_t *)&std::nothrow);
    v9 = v61;
    v89 = v61;
    if ( v61 )
      memmove_0(v61, v56, 2 * v58);
    v7 = 0;
  }
  if ( *(_QWORD *)v78 )
  {
    (***(void (__fastcall ****)(_QWORD, __int64))v78)(*(_QWORD *)v78, 1);
    *(_QWORD *)v78 = 0;
  }
  LOBYTE(v12) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::GetImpl'::`2'::impl,
    v12);
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids);
  v13 = WscServiceUtils::g_pAntiVirusManager;
  v14 = WscServiceUtils::g_pAntiVirusVerificationManager;
  v90 = WscServiceUtils::g_pAntiVirusVerificationManager;
  v15 = RpcImpersonateClient(this);
  if ( v15 )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, v15);
    }
    RpcRaiseException(5);
  }
  IsMember[0] = 0;
  Sid = 0;
  if ( ConvertStringSidToSidW(L"S-1-5-80-1913148863-3492339771-4165695881-2087618961-4109116736", &Sid) )
  {
    if ( !CheckTokenMembership(0, Sid, IsMember) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, LastError);
      }
      IsMember[0] = 0;
    }
    LocalFree(Sid);
  }
  else
  {
    v62 = GetLastError();
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, v62);
    }
  }
  if ( IsMember[0] )
  {
    v18 = (*(__int64 (__fastcall **)(CThirdPartyManager *, _SECURITY_PRODUCT_TYPE *))(*(_QWORD *)v13 + 8LL))(v13, v78);
    goto LABEL_18;
  }
  if ( !(unsigned int)RunningAsAdministrator() )
  {
    v18 = 5;
    goto LABEL_18;
  }
  if ( !this )
  {
    LOWORD(ExternalBaseFromPESettings) = 87;
LABEL_84:
    v18 = (unsigned __int16)ExternalBaseFromPESettings;
    goto LABEL_18;
  }
  RpcCallAttributes = 2;
  v92 = 16;
  v93 = 0;
  v94 = 0;
  v95 = 0;
  v96 = 0;
  *(_OWORD *)dwProcessId = 0;
  v98 = 0;
  v99 = 0;
  v100 = 0;
  ExternalBaseFromPESettings = RpcServerInqCallAttributesW(this, &RpcCallAttributes);
  if ( !ExternalBaseFromPESettings )
  {
    v73 = OpenProcess(0x1000u, 0, dwProcessId[0]);
    v74 = v73;
    if ( v73 )
    {
      v64 = 260;
      IsMember[0] = 260;
      if ( QueryFullProcessImageNameW(v73, 0, ExeName, (PDWORD)IsMember) )
      {
        if ( !IsMember[0] )
        {
          ExternalBaseFromPESettings = 3;
          CloseHandle(v74);
          v5 = v86;
          goto LABEL_15;
        }
        if ( IsMember[0] > 0x103u )
        {
          ExternalBaseFromPESettings = 111;
        }
        else
        {
          v75 = -1;
          do
            ++v75;
          while ( ExeName[v75] );
          v63 = v75 + 1;
          if ( v63 >= 0x104 )
          {
            if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                10,
                WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids,
                (unsigned int)v63,
                260);
            }
          }
          else
          {
            v64 = v63;
          }
          v65 = 2 * v64;
          if ( !is_mul_ok(v64, 2u) )
            v65 = -1;
          v66 = (unsigned __int16 *)operator new[](v65, (const struct std::nothrow_t *)&std::nothrow);
          v67 = v66;
          if ( v66 )
          {
            if ( v64 )
            {
              v68 = 2147483646;
              v69 = ExeName;
              v70 = v66;
              do
              {
                if ( !v68 )
                  break;
                v71 = *v69;
                if ( !*v69 )
                  break;
                ++v69;
                *v70++ = v71;
                --v68;
                --v64;
              }
              while ( v64 );
              v72 = v70 - 1;
              if ( v64 )
                v72 = v70;
              *v72 = 0;
              v7 = v67;
              LOWORD(ExternalBaseFromPESettings) = 0;
            }
            else
            {
              LOWORD(ExternalBaseFromPESettings) = 87;
              if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  11,
                  WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids,
                  2147942487LL);
              }
              operator delete(v67);
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids);
            }
            LOWORD(ExternalBaseFromPESettings) = 14;
          }
          ExternalBaseFromPESettings = (unsigned __int16)ExternalBaseFromPESettings;
          v14 = v90;
        }
      }
      else
      {
        ExternalBaseFromPESettings = GetLastError();
        if ( !ExternalBaseFromPESettings )
          ExternalBaseFromPESettings = 3;
      }
      CloseHandle(v74);
      v5 = v86;
      goto LABEL_15;
    }
    ExternalBaseFromPESettings = GetLastError();
    v5 = v86;
    if ( !ExternalBaseFromPESettings )
    {
      LOWORD(ExternalBaseFromPESettings) = 110;
      goto LABEL_184;
    }
  }
LABEL_15:
  v17 = ExternalBaseFromPESettings < 0;
  if ( ExternalBaseFromPESettings > 0 )
  {
LABEL_184:
    ExternalBaseFromPESettings = (unsigned __int16)ExternalBaseFromPESettings | 0x80070000;
    v17 = ExternalBaseFromPESettings < 0;
  }
  if ( v17 )
    goto LABEL_84;
  v18 = 0;
  ExternalBaseFromPESettings = CSecurityVerificationManager::CreateExternalBaseFromPESettings(
                                 v14,
                                 v7,
                                 (struct CExternalBase **)v78);
  operator delete(v7);
  if ( ExternalBaseFromPESettings < 0 )
    goto LABEL_84;
LABEL_18:
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids,
      (unsigned int)v18);
  v19 = RpcRevertToSelf();
  if ( !v19 )
    goto LABEL_22;
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, v19);
LABEL_22:
    v20 = WPP_GLOBAL_Control;
  }
  v21 = v18 < 0;
  if ( v18 > 0 )
  {
    v18 = (unsigned __int16)v18 | 0x80070000;
    v21 = v18 < 0;
  }
  if ( v21 )
  {
    if ( v20 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)v20 + 2), 10, WPP_93277130f4d6304520323beb48801075_Traceguids, (unsigned int)v18);
    CommonUtil::AutoRef<IEnumWbemClassObject>::~AutoRef<IEnumWbemClassObject>(&v83);
    if ( v9 )
      operator delete(v9);
    if ( v8 )
      operator delete(v8);
    if ( *(_QWORD *)v78 )
      (***(void (__fastcall ****)(_QWORD, __int64))v78)(*(_QWORD *)v78, 1);
    return (unsigned int)v18;
  }
  v22 = v87;
  v23 = -1;
  if ( !v87 )
    goto LABEL_27;
  v77 = -1;
  do
    ++v77;
  while ( v87[v77] );
  if ( !v77 )
LABEL_27:
    v22 = (const OLECHAR *)v8;
  if ( !v5 )
    goto LABEL_29;
  do
    ++v23;
  while ( v5[v23] );
  if ( !v23 )
LABEL_29:
    v5 = (OLECHAR *)v9;
  v24 = g_pWmiEventManagerAvFw;
  if ( !g_pWmiEventManagerAvFw )
  {
    if ( v20 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)v20 + 2), 11, WPP_93277130f4d6304520323beb48801075_Traceguids);
    CommonUtil::AutoRef<IEnumWbemClassObject>::~AutoRef<IEnumWbemClassObject>(&v83);
    if ( v9 )
      operator delete(v9);
    if ( v8 )
      operator delete(v8);
    if ( *(_QWORD *)v78 )
    {
      (***(void (__fastcall ****)(_QWORD, __int64))v78)(*(_QWORD *)v78, 1);
      return 2147500037LL;
    }
    return 2147500037LL;
  }
  v25 = *((_QWORD *)g_pWmiEventManagerAvFw + 8);
  if ( !v25 )
  {
    if ( v20 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)v20 + 2), 12, WPP_93277130f4d6304520323beb48801075_Traceguids, 2147500037LL);
    if ( v9 )
      operator delete(v9);
    if ( v8 )
      operator delete(v8);
    if ( *(_QWORD *)v78 )
      (***(void (__fastcall ****)(_QWORD, __int64))v78)(*(_QWORD *)v78, 1);
    return 2147500037LL;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(v25);
  v26 = *((_QWORD *)v24 + 8);
  v83 = v26;
  v27 = SysAllocString(L"WSC_CallerAMPPLData");
  v87 = v27;
  if ( v27 )
  {
    v82 = 0;
    v18 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD, _QWORD, __int64 *, _QWORD))(*(_QWORD *)v26 + 48LL))(
            v26,
            v27,
            0,
            0,
            &v82,
            0);
    if ( v18 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_93277130f4d6304520323beb48801075_Traceguids,
          (unsigned int)v18);
      }
      CommonUtil::AutoRef<IEnumWbemClassObject>::~AutoRef<IEnumWbemClassObject>(&v82);
      SysFreeString(v27);
      CommonUtil::AutoRef<IEnumWbemClassObject>::~AutoRef<IEnumWbemClassObject>(&v83);
      if ( v9 )
        operator delete(v9);
      if ( v8 )
LABEL_95:
        operator delete(v8);
    }
    else
    {
      v79 = 0;
      v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v82 + 120LL))(v82, 0, &v79);
      if ( v18 >= 0 )
      {
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        pvarg.vt = 8;
        pvarg.llVal = (LONGLONG)SysAllocString(*(const OLECHAR **)(*(_QWORD *)v78 + 8LL));
        v28 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v79 + 40LL))(
                v79,
                L"instanceGuid",
                0,
                &pvarg,
                0);
        if ( v28 < 0
          && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            16,
            WPP_93277130f4d6304520323beb48801075_Traceguids,
            (unsigned int)v28);
        }
        v29 = VariantClear(&pvarg);
        if ( v29 < 0
          && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            WPP_93277130f4d6304520323beb48801075_Traceguids,
            (unsigned int)v29);
        }
        pvarg.vt = 8;
        pvarg.llVal = (LONGLONG)SysAllocString(*(const OLECHAR **)(*(_QWORD *)v78 + 32LL));
        v30 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v79 + 40LL))(
                v79,
                L"pathToCaller",
                0,
                &pvarg,
                0);
        if ( v30 < 0
          && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            WPP_93277130f4d6304520323beb48801075_Traceguids,
            (unsigned int)v30);
        }
        v31 = VariantClear(&pvarg);
        if ( v31 < 0
          && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            WPP_93277130f4d6304520323beb48801075_Traceguids,
            (unsigned int)v31);
        }
        pvarg.vt = 8;
        pvarg.llVal = (LONGLONG)SysAllocString(v22);
        v32 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v79 + 40LL))(
                v79,
                L"displayName",
                0,
                &pvarg,
                0);
        if ( v32 < 0
          && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            WPP_93277130f4d6304520323beb48801075_Traceguids,
            (unsigned int)v32);
        }
        v33 = VariantClear(&pvarg);
        if ( v33 < 0
          && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            WPP_93277130f4d6304520323beb48801075_Traceguids,
            (unsigned int)v33);
        }
        pvarg.vt = 8;
        pvarg.llVal = (LONGLONG)SysAllocString(v5);
        v34 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v79 + 40LL))(
                v79,
                L"pathToSignedProductExe",
                0,
                &pvarg,
                0);
        if ( v34 < 0
          && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            WPP_93277130f4d6304520323beb48801075_Traceguids,
            (unsigned int)v34);
        }
        v35 = VariantClear(&pvarg);
        if ( v35 < 0
          && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            23,
            WPP_93277130f4d6304520323beb48801075_Traceguids,
            (unsigned int)v35);
        }
        *(_QWORD *)IsMember = 0;
        WscIniConfiguration = WscServiceUtils::GetWscIniConfiguration(
                                (WscServiceUtils *)v5,
                                (unsigned __int16 *)IsMember,
                                v36);
        if ( WscIniConfiguration < 0 )
        {
          if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              24,
              WPP_93277130f4d6304520323beb48801075_Traceguids,
              (unsigned int)WscIniConfiguration);
          }
          v38 = *(OLECHAR **)IsMember;
          if ( *(_QWORD *)IsMember )
          {
            operator delete(*(void **)IsMember);
            v38 = 0;
            *(_QWORD *)IsMember = 0;
          }
        }
        else
        {
          v38 = *(OLECHAR **)IsMember;
        }
        pvarg.vt = 8;
        v39 = (const OLECHAR *)&qword_180045B70;
        if ( v38 )
          v39 = v38;
        pvarg.llVal = (LONGLONG)SysAllocString(v39);
        v40 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v79 + 40LL))(
                v79,
                L"iniString",
                0,
                &pvarg,
                0);
        if ( v40 < 0
          && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            WPP_93277130f4d6304520323beb48801075_Traceguids,
            (unsigned int)v40);
        }
        v41 = VariantClear(&pvarg);
        if ( v41 < 0
          && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            WPP_93277130f4d6304520323beb48801075_Traceguids,
            (unsigned int)v41);
        }
        pvarg.vt = 3;
        pvarg.lVal = v84;
        v42 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v79 + 40LL))(
                v79,
                L"hresultCode",
                0,
                &pvarg,
                0);
        if ( v42 < 0
          && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            27,
            WPP_93277130f4d6304520323beb48801075_Traceguids,
            (unsigned int)v42);
        }
        v43 = VariantClear(&pvarg);
        if ( v43 < 0
          && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            28,
            WPP_93277130f4d6304520323beb48801075_Traceguids,
            (unsigned int)v43);
        }
        pvarg.vt = 3;
        pvarg.lVal = a5;
        v44 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v79 + 40LL))(
                v79,
                L"statusCode",
                0,
                &pvarg,
                0);
        if ( v44 < 0
          && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            29,
            WPP_93277130f4d6304520323beb48801075_Traceguids,
            (unsigned int)v44);
        }
        v45 = VariantClear(&pvarg);
        if ( v45 < 0
          && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            30,
            WPP_93277130f4d6304520323beb48801075_Traceguids,
            (unsigned int)v45);
        }
        v46 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v26 + 112LL))(
                v26,
                v79,
                0,
                0,
                0);
        v47 = v46;
        if ( v46 < 0 )
        {
          if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              31,
              WPP_93277130f4d6304520323beb48801075_Traceguids,
              (unsigned int)v46);
          }
          if ( v38 )
            operator delete(v38);
          CommonUtil::AutoRef<IEnumWbemClassObject>::~AutoRef<IEnumWbemClassObject>(&v79);
          CommonUtil::AutoRef<IEnumWbemClassObject>::~AutoRef<IEnumWbemClassObject>(&v82);
          SysFreeString(v27);
          CommonUtil::AutoRef<IEnumWbemClassObject>::~AutoRef<IEnumWbemClassObject>(&v83);
          if ( v9 )
            operator delete(v9);
          if ( v8 )
            operator delete(v8);
          v48 = *(void (__fastcall ****)(_QWORD, __int64))v78;
        }
        else
        {
          if ( v38 )
            operator delete(v38);
          if ( v79 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
          if ( v82 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
          SysFreeString(v27);
          if ( v26 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          if ( v9 )
            operator delete(v9);
          if ( v8 )
            operator delete(v8);
          v48 = *(void (__fastcall ****)(_QWORD, __int64))v78;
          if ( !*(_QWORD *)v78 )
            return v47;
        }
        if ( v48 )
          (**v48)(v48, 1);
        return v47;
      }
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          WPP_93277130f4d6304520323beb48801075_Traceguids,
          (unsigned int)v18);
      }
      if ( v79 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
      if ( v82 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
      SysFreeString(v27);
      if ( v26 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      if ( v9 )
        operator delete(v9);
      if ( v8 )
        goto LABEL_95;
    }
    if ( *(_QWORD *)v78 )
    {
      (***(void (__fastcall ****)(_QWORD, __int64))v78)(*(_QWORD *)v78, 1);
      return (unsigned int)v18;
    }
    return (unsigned int)v18;
  }
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_93277130f4d6304520323beb48801075_Traceguids, 2147942414LL);
  CommonUtil::AutoRef<IEnumWbemClassObject>::~AutoRef<IEnumWbemClassObject>(&v83);
  if ( v9 )
    operator delete(v9);
  if ( v8 )
    operator delete(v8);
  if ( *(_QWORD *)v78 )
    (***(void (__fastcall ****)(_QWORD, __int64))v78)(*(_QWORD *)v78, 1);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180003f80  push    rbp
0x180003f82  push    rbx
0x180003f83  push    rsi
0x180003f84  push    rdi
0x180003f85  push    r12
0x180003f87  push    r13
0x180003f89  push    r14
0x180003f8b  push    r15
0x180003f8d  lea     rbp, [rsp-268h]
0x180003f95  sub     rsp, 368h
0x180003f9c  mov     rax, cs:__security_cookie
0x180003fa3  xor     rax, rsp
0x180003fa6  mov     [rbp+2A0h+var_48], rax
0x180003fad  mov     [rbp+2A0h+var_320], r9d
0x180003fb1  mov     [rbp+2A0h+var_308], r8
0x180003fb5  mov     r13, rdx
0x180003fb8  mov     [rbp+2A0h+var_310], rdx
0x180003fbc  mov     rbx, rcx
0x180003fbf  mov     dl, 1
0x180003fc1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::GetImpl(void)'::`2'::impl
0x180003fc8  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180003fcd  xor     r15d, r15d
0x180003fd0  mov     qword ptr [rsp+3A0h+var_360], r15
0x180003fd5  mov     r14d, r15d
0x180003fd8  mov     [rbp+2A0h+var_300], r15
0x180003fdc  mov     esi, r15d
0x180003fdf  mov     [rbp+2A0h+var_2F8], r15
0x180003fe3  mov     [rsp+3A0h+var_328], r15
0x180003fe8  lea     r8, [rsp+3A0h+var_360]; enum _SECURITY_PRODUCT_TYPE
0x180003fed  mov     rcx, rbx; this
0x180003ff0  call    ?PopulateExternalBaseFromExistingRegistration@WscServiceUtils@@YAJPEAXW4_SECURITY_PRODUCT_TYPE@@PEAPEAVCExternalBase@@@Z; WscServiceUtils::PopulateExternalBaseFromExistingRegistration(void *,_SECURITY_PRODUCT_TYPE,CExternalBase * *)
0x180003ff5  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180003ffc  test    eax, eax
0x180003ffe  jns     loc_180004613
0x180004004  mov     rcx, qword ptr [rsp+3A0h+var_360]
0x180004009  test    rcx, rcx
0x18000400c  jz      short loc_180004023
0x18000400e  mov     rax, [rcx]
0x180004011  mov     edx, 1
0x180004016  mov     rax, [rax]
0x180004019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000401e  mov     qword ptr [rsp+3A0h+var_360], r15
0x180004023  mov     dl, 1
0x180004025  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::GetImpl(void)'::`2'::impl
0x18000402c  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180004031  lea     rax, WPP_GLOBAL_Control
0x180004038  mov     rcx, cs:WPP_GLOBAL_Control
0x18000403f  cmp     rcx, rax
0x180004042  jz      short loc_18000404E
0x180004044  test    byte ptr [rcx+1Ch], 8
0x180004048  jnz     loc_180004B54
0x18000404e  mov     rdi, cs:?g_pAntiVirusManager@WscServiceUtils@@3PEAVCAntiVirusManager@@EA; CAntiVirusManager * WscServiceUtils::g_pAntiVirusManager
0x180004055  mov     r12, cs:?g_pAntiVirusVerificationManager@WscServiceUtils@@3PEAVCSecurityVerificationManagerAv@@EA; CSecurityVerificationManagerAv * WscServiceUtils::g_pAntiVirusVerificationManager
0x18000405c  mov     [rbp+2A0h+var_2F0], r12
0x180004060  mov     rcx, rbx; BindingHandle
0x180004063  call    cs:__imp_RpcImpersonateClient
0x180004069  test    eax, eax
0x18000406b  jnz     loc_180004B6E
0x180004071  mov     [rsp+3A0h+IsMember], r15d
0x180004076  mov     [rbp+2A0h+Sid], r15
0x18000407a  lea     rdx, [rbp+2A0h+Sid]; Sid
0x18000407e  lea     rcx, StringSid; "S-1-5-80-1913148863-3492339771-41656958"...
0x180004085  call    cs:__imp_ConvertStringSidToSidW
0x18000408b  test    eax, eax
0x18000408d  jz      loc_1800047C9
0x180004093  lea     r8, [rsp+3A0h+IsMember]; IsMember
0x180004098  mov     rdx, [rbp+2A0h+Sid]; SidToCheck
0x18000409c  xor     ecx, ecx; TokenHandle
0x18000409e  call    cs:__imp_CheckTokenMembership
0x1800040a4  test    eax, eax
0x1800040a6  jz      loc_180004BAB
0x1800040ac  mov     rcx, [rbp+2A0h+Sid]; hMem
0x1800040b0  call    cs:__imp_LocalFree
0x1800040b6  cmp     [rsp+3A0h+IsMember], 0
0x1800040bb  jnz     loc_1800047AE
0x1800040c1  call    RunningAsAdministrator
0x1800040c6  test    eax, eax
0x1800040c8  jz      loc_180004CE2
0x1800040ce  test    rbx, rbx
0x1800040d1  jz      loc_1800046BE
0x1800040d7  mov     [rbp+2A0h+RpcCallAttributes], 2
0x1800040de  mov     [rbp+2A0h+var_2DC], 10h
0x1800040e6  xor     eax, eax
0x1800040e8  mov     [rbp+2A0h+var_2D4], eax
0x1800040eb  xorps   xmm0, xmm0
0x1800040ee  movups  [rbp+2A0h+var_2D0], xmm0
0x1800040f2  movups  [rbp+2A0h+var_2C0], xmm0
0x1800040f6  movups  [rbp+2A0h+var_2B0], xmm0
0x1800040fa  movups  xmmword ptr [rbp+2A0h+dwProcessId], xmm0
0x1800040fe  movups  [rbp+2A0h+var_290], xmm0
0x180004102  movups  [rbp+2A0h+var_280], xmm0
0x180004106  mov     [rbp+2A0h+var_270], rax
0x18000410a  lea     rdx, [rbp+2A0h+RpcCallAttributes]; RpcCallAttributes
0x18000410e  mov     rcx, rbx; ClientBinding
0x180004111  call    cs:__imp_RpcServerInqCallAttributesW
0x180004117  mov     edi, eax
0x180004119  test    eax, eax
0x18000411b  jz      loc_1800048CF
0x180004121  test    edi, edi
0x180004123  jg      loc_180004C05
0x180004129  js      loc_1800046C3
0x18000412f  xor     ebx, ebx
0x180004131  lea     r8, [rsp+3A0h+var_360]; struct CExternalBase **
0x180004136  mov     rdx, r15; unsigned __int16 *
0x180004139  mov     rcx, r12; this
0x18000413c  call    ?CreateExternalBaseFromPESettings@CSecurityVerificationManager@@QEAAJPEAGPEAPEAVCExternalBase@@@Z; CSecurityVerificationManager::CreateExternalBaseFromPESettings(ushort *,CExternalBase * *)
0x180004141  mov     edi, eax
0x180004143  mov     rcx, r15; Block
0x180004146  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000414b  test    edi, edi
0x18000414d  js      loc_1800046C3
0x180004153  mov     rcx, cs:WPP_GLOBAL_Control
0x18000415a  lea     rdi, WPP_GLOBAL_Control
0x180004161  cmp     rcx, rdi
0x180004164  jz      short loc_180004170
0x180004166  test    byte ptr [rcx+1Ch], 8
0x18000416a  jnz     loc_180004CEC
0x180004170  call    cs:__imp_RpcRevertToSelf
0x180004176  test    eax, eax
0x180004178  jnz     loc_180004D09
0x18000417e  mov     r10, cs:WPP_GLOBAL_Control
0x180004185  test    ebx, ebx
0x180004187  jg      loc_180004603
0x18000418d  js      loc_180004D41
0x180004193  mov     r12, [rbp+2A0h+var_308]
0x180004197  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000419e  test    r12, r12
0x1800041a1  jnz     loc_180004D72
0x1800041a7  mov     r12, r14
0x1800041aa  test    r13, r13
0x1800041ad  jnz     loc_180004D8E
0x1800041b3  mov     r13, rsi
0x1800041b6  mov     rbx, cs:?g_pWmiEventManagerAvFw@@3PEAVCWmiEventManagerAvFw@@EA; CWmiEventManagerAvFw * g_pWmiEventManagerAvFw
0x1800041bd  test    rbx, rbx
0x1800041c0  jz      loc_180004DA8
0x1800041c6  mov     rcx, [rbx+40h]
0x1800041ca  test    rcx, rcx
0x1800041cd  jz      loc_18000496B
0x1800041d3  mov     rax, [rcx]
0x1800041d6  mov     rax, [rax+8]
0x1800041da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041df  mov     r15, [rbx+40h]
0x1800041e3  mov     [rsp+3A0h+var_328], r15
0x1800041e8  lea     rcx, psz; "WSC_CallerAMPPLData"
0x1800041ef  call    cs:__imp_SysAllocString
0x1800041f5  mov     rdi, rax
0x1800041f8  mov     [rbp+2A0h+var_308], rax
0x1800041fc  test    rax, rax
0x1800041ff  jz      loc_1800051D0
0x180004205  xor     ecx, ecx
0x180004207  mov     [rsp+3A0h+var_330], rcx
0x18000420c  mov     rax, [r15]
0x18000420f  mov     [rsp+3A0h+var_378], rcx
0x180004214  lea     rcx, [rsp+3A0h+var_330]
0x180004219  mov     [rsp+3A0h+var_380], rcx
0x18000421e  xor     r9d, r9d
0x180004221  xor     r8d, r8d
0x180004224  mov     rdx, rdi
0x180004227  mov     rcx, r15
0x18000422a  mov     rax, [rax+30h]
0x18000422e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004233  mov     ebx, eax
0x180004235  test    eax, eax
0x180004237  js      loc_180004E01
0x18000423d  mov     [rsp+3A0h+var_358], 0
0x180004246  mov     rcx, [rsp+3A0h+var_330]
0x18000424b  mov     rax, [rcx]
0x18000424e  lea     r8, [rsp+3A0h+var_358]
0x180004253  xor     edx, edx
0x180004255  mov     rax, [rax+78h]
0x180004259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000425e  mov     ebx, eax
0x180004260  test    eax, eax
0x180004262  js      loc_1800046CB
0x180004268  xorps   xmm0, xmm0
0x18000426b  xor     eax, eax
0x18000426d  movups  xmmword ptr [rsp+3A0h+pvarg], xmm0
0x180004272  mov     qword ptr [rsp+3A0h+pvarg+10h], rax
0x180004277  lea     rcx, [rsp+3A0h+pvarg]; pvarg
0x18000427c  call    cs:__imp_VariantInit
0x180004282  mov     ebx, 8
0x180004287  mov     word ptr [rsp+3A0h+pvarg], bx
0x18000428c  mov     rcx, qword ptr [rsp+3A0h+var_360]
0x180004291  mov     rcx, [rcx+8]; psz
0x180004295  call    cs:__imp_SysAllocString
0x18000429b  mov     qword ptr [rsp+3A0h+pvarg+8], rax
0x1800042a0  mov     rcx, [rsp+3A0h+var_358]
0x1800042a5  mov     rax, [rcx]
0x1800042a8  mov     dword ptr [rsp+3A0h+var_380], 0
0x1800042b0  lea     r9, [rsp+3A0h+pvarg]
0x1800042b5  xor     r8d, r8d
0x1800042b8  lea     rdx, aInstanceguid; "instanceGuid"
0x1800042bf  mov     rax, [rax+28h]
0x1800042c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042c8  test    eax, eax
0x1800042ca  js      loc_180004E66
0x1800042d0  lea     rcx, [rsp+3A0h+pvarg]; pvarg
0x1800042d5  call    cs:__imp_VariantClear
0x1800042db  test    eax, eax
0x1800042dd  js      loc_180004EA4
0x1800042e3  mov     word ptr [rsp+3A0h+pvarg], bx
0x1800042e8  mov     rcx, qword ptr [rsp+3A0h+var_360]
0x1800042ed  mov     rcx, [rcx+20h]; psz
0x1800042f1  call    cs:__imp_SysAllocString
0x1800042f7  mov     qword ptr [rsp+3A0h+pvarg+8], rax
0x1800042fc  mov     rcx, [rsp+3A0h+var_358]
0x180004301  mov     rax, [rcx]
0x180004304  mov     dword ptr [rsp+3A0h+var_380], 0
0x18000430c  lea     r9, [rsp+3A0h+pvarg]
0x180004311  xor     r8d, r8d
0x180004314  lea     rdx, aPathtocaller; "pathToCaller"
0x18000431b  mov     rax, [rax+28h]
0x18000431f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004324  test    eax, eax
0x180004326  js      loc_180004EE2
0x18000432c  lea     rcx, [rsp+3A0h+pvarg]; pvarg
0x180004331  call    cs:__imp_VariantClear
0x180004337  test    eax, eax
0x180004339  js      loc_180004F20
0x18000433f  mov     word ptr [rsp+3A0h+pvarg], bx
0x180004344  mov     rcx, r12; psz
0x180004347  call    cs:__imp_SysAllocString
0x18000434d  mov     qword ptr [rsp+3A0h+pvarg+8], rax
0x180004352  mov     rcx, [rsp+3A0h+var_358]
0x180004357  mov     rax, [rcx]
0x18000435a  xor     r12d, r12d
0x18000435d  mov     dword ptr [rsp+3A0h+var_380], r12d
0x180004362  lea     r9, [rsp+3A0h+pvarg]
0x180004367  xor     r8d, r8d
0x18000436a  lea     rdx, aDisplayname_0; "displayName"
0x180004371  mov     rax, [rax+28h]
0x180004375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000437a  test    eax, eax
0x18000437c  js      loc_180004770
0x180004382  lea     rcx, [rsp+3A0h+pvarg]; pvarg
0x180004387  call    cs:__imp_VariantClear
0x18000438d  test    eax, eax
0x18000438f  js      loc_180004F5E
0x180004395  mov     word ptr [rsp+3A0h+pvarg], bx
0x18000439a  mov     rcx, r13; psz
0x18000439d  call    cs:__imp_SysAllocString
0x1800043a3  mov     qword ptr [rsp+3A0h+pvarg+8], rax
0x1800043a8  mov     rcx, [rsp+3A0h+var_358]
0x1800043ad  mov     rax, [rcx]
0x1800043b0  mov     dword ptr [rsp+3A0h+var_380], r12d
0x1800043b5  lea     r9, [rsp+3A0h+pvarg]
0x1800043ba  xor     r8d, r8d
0x1800043bd  lea     rdx, aPathtosignedpr; "pathToSignedProductExe"
0x1800043c4  mov     rax, [rax+28h]
0x1800043c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043cd  test    eax, eax
0x1800043cf  js      loc_180004F9C
0x1800043d5  lea     rbx, WPP_GLOBAL_Control
0x1800043dc  lea     rcx, [rsp+3A0h+pvarg]; pvarg
0x1800043e1  call    cs:__imp_VariantClear
0x1800043e7  test    eax, eax
0x1800043e9  js      loc_180004FDA
0x1800043ef  mov     qword ptr [rsp+3A0h+IsMember], r12
0x1800043f4  lea     rdx, [rsp+3A0h+IsMember]; unsigned __int16 *
0x1800043f9  mov     rcx, r13; this
0x1800043fc  call    ?GetWscIniConfiguration@WscServiceUtils@@YAJPEBGPEAPEAG@Z; WscServiceUtils::GetWscIniConfiguration(ushort const *,ushort * *)
0x180004401  test    eax, eax
0x180004403  js      loc_180005011
0x180004409  mov     rbx, qword ptr [rsp+3A0h+IsMember]
0x18000440e  lea     r13, WPP_GLOBAL_Control
0x180004415  mov     eax, 8
0x18000441a  mov     word ptr [rsp+3A0h+pvarg], ax
0x18000441f  lea     rcx, qword_180045B70
0x180004426  test    rbx, rbx
0x180004429  cmovnz  rcx, rbx; psz
0x18000442d  call    cs:__imp_SysAllocString
0x180004433  mov     qword ptr [rsp+3A0h+pvarg+8], rax
0x180004438  mov     rcx, [rsp+3A0h+var_358]
0x18000443d  mov     rax, [rcx]
0x180004440  mov     dword ptr [rsp+3A0h+var_380], r12d
0x180004445  lea     r9, [rsp+3A0h+pvarg]
0x18000444a  xor     r8d, r8d
0x18000444d  lea     rdx, aInistring; "iniString"
0x180004454  mov     rax, [rax+28h]
0x180004458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000445d  test    eax, eax
0x18000445f  js      loc_18000504F
0x180004465  lea     rcx, [rsp+3A0h+pvarg]; pvarg
0x18000446a  call    cs:__imp_VariantClear
0x180004470  test    eax, eax
0x180004472  js      loc_180005086
0x180004478  mov     eax, 3
0x18000447d  mov     word ptr [rsp+3A0h+pvarg], ax
0x180004482  mov     eax, [rbp+2A0h+var_320]
0x180004485  mov     dword ptr [rsp+3A0h+pvarg+8], eax
0x180004489  mov     rcx, [rsp+3A0h+var_358]
0x18000448e  mov     rax, [rcx]
0x180004491  mov     dword ptr [rsp+3A0h+var_380], r12d
0x180004496  lea     r9, [rsp+3A0h+pvarg]
0x18000449b  xor     r8d, r8d
0x18000449e  lea     rdx, aHresultcode; "hresultCode"
0x1800044a5  mov     rax, [rax+28h]
0x1800044a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044ae  test    eax, eax
0x1800044b0  js      loc_1800050BD
  ... truncated ...
```
