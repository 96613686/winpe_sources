# CreateUpgradableProductsList(CWmiEventManager *,CList<ushort *,ushort *> *,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> &,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> &)

- ea: `0x180021128`
- end: `0x180022129`
- name: `?CreateUpgradableProductsList@@YAJPEAVCWmiEventManager@@PEAV?$CList@PEAGPEAG@@AEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@2@Z`
- size: `4097`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001d9e0`

## callees

- `0x180002db0`
- `0x180006c50`
- `0x180008e48`
- `0x180009f40`
- `0x180016ae8`
- `0x180017a48`
- `0x180017b00`
- `0x180018ab0`
- `0x18001b7f0`
- `0x18001c4c0`
- `0x180021128`
- `0x180022130`
- `0x1800287d4`
- `0x180029158`
- `0x180029300`
- `0x180029e74`
- `0x1800310e8`
- `0x180031228`
- `0x1800319bc`
- `0x180031c30`
- `0x180032508`
- `0x180032790`
- `0x18003280c`
- `0x180032adc`
- `0x180032c38`
- `0x180032e48`
- `0x18003fbf2`
- `0x18003fc30`
- `0x180042010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002188c`
- `msvcrt!_wcsicmp` at `0x180021bdd`
- `msvcrt!_wcsicmp` at `0x18002188c`
- `msvcrt!_wcsicmp` at `0x180021bdd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800214aa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021547`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800214aa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021547`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002130e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002130e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800213ff`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180021de4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800213ff`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180021de4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180021254`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180021fff`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180021254`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180021fff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002128c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002128c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002205f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800220b0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002205f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800220b0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800211d3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002184f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800211d3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002184f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800214c7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180021641`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002193e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002197d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800214c7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180021641`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002193e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002197d`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180021bc7`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180021bc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021768`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021768`
- `OLEAUT32!__imp_SysAllocString` at `0x180021687`
- `OLEAUT32!__imp_SysAllocString` at `0x180021687`
- `OLEAUT32!__imp_SysFreeString` at `0x180021d55`
- `OLEAUT32!__imp_SysFreeString` at `0x180021d55`
- `CRYPT32!CryptHashPublicKeyInfo` at `0x180021b7e`
- `CRYPT32!CryptHashPublicKeyInfo` at `0x180021b7e`
- `CRYPT32!CertFreeCertificateContext` at `0x180021755`
- `CRYPT32!CertFreeCertificateContext` at `0x180021755`
- `ADVAPI32!RegDeleteKeyW` at `0x180021e6a`
- `ADVAPI32!RegDeleteKeyW` at `0x180021e6a`

## string_xrefs

- `0x18002181c`: `pathToSignedReportingExe`
- `0x1800211cc`: `%CommonProgramFiles%\AV`
- `0x180021246`: `SOFTWARE\Microsoft\Security Center\ProvidersMigration\WicaUpgradableAVs`
- `0x180021440`: `SOFTWARE\Microsoft\Security Center\ProvidersMigration\WicaUpgradableAVs`
- `0x180021e25`: `SOFTWARE\Microsoft\Security Center\ProvidersMigration\WicaUpgradableAVs`
- `0x180021f93`: `SOFTWARE\Microsoft\Security Center\ProvidersMigration\WicaUpgradableAVs`

## pseudocode

```c
__int64 __fastcall CreateUpgradableProductsList(__int64 a1, __int64 a2)
{
  CWmiEventManager *v3; // r14
  int v4; // r15d
  int WbemServices; // esi
  int PseudoExpiredProductsList; // eax
  unsigned int v7; // eax
  CThirdPartyManager *v8; // rcx
  __int64 v9; // rdx
  DWORD v11; // ebx
  DWORD v12; // eax
  void **v13; // rcx
  void **v14; // rdx
  LSTATUS ValueW; // eax
  void **v16; // rdx
  __int64 v17; // rax
  CThirdPartyManager *v18; // rcx
  int v19; // edx
  int v20; // edx
  OLECHAR *v21; // r12
  int v22; // ebx
  int v23; // ebx
  struct IWbemServices *HeadPosition; // rax
  unsigned __int64 v25; // r8
  const wchar_t *Next; // rax
  __int64 v27; // rax
  DWORD FileAttributesW; // eax
  CThirdPartyManager *v29; // rcx
  __int64 v30; // rdx
  WCHAR *v31; // r9
  __int64 v32; // rcx
  int IsPseudoExpired; // eax
  int ProductState; // eax
  CThirdPartyManager *v35; // rcx
  int v36; // edx
  unsigned __int16 *v37; // r9
  __int64 k; // rcx
  __int64 v39; // rax
  DWORD v40; // ebx
  void **v41; // rcx
  void **v42; // rdx
  LSTATUS v43; // eax
  _QWORD *v44; // rbx
  unsigned __int64 v45; // r8
  _QWORD *v46; // r11
  __int64 v47; // rcx
  _QWORD *i; // rax
  const BYTE *v49; // r14
  const unsigned __int16 *v50; // rcx
  void **v51; // rdx
  LSTATUS v52; // eax
  CThirdPartyManager *v53; // rcx
  int v54; // edx
  DWORD v55; // eax
  const BYTE *v56; // rcx
  DWORD v57; // eax
  __int64 v58; // rcx
  _QWORD *j; // rax
  DWORD pcbData; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cchName; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  __int64 v64; // [rsp+78h] [rbp-88h] BYREF
  struct IWbemServices *v65; // [rsp+80h] [rbp-80h] BYREF
  int v66; // [rsp+88h] [rbp-78h] BYREF
  int v67; // [rsp+8Ch] [rbp-74h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+90h] [rbp-70h] BYREF
  LPVOID pv; // [rsp+98h] [rbp-68h] BYREF
  __int64 v70; // [rsp+A0h] [rbp-60h] BYREF
  LPCWSTR lpSrc[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v72; // [rsp+B8h] [rbp-48h]
  DWORD pcbComputedHash; // [rsp+C0h] [rbp-40h] BYREF
  void *Block[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v75; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v76; // [rsp+E0h] [rbp-20h]
  BYTE pbComputedHash[16]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v78[5]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int16 pvData[264]; // [rsp+120h] [rbp+20h] BYREF
  WCHAR Name[264]; // [rsp+330h] [rbp+230h] BYREF
  unsigned __int16 v81[264]; // [rsp+540h] [rbp+440h] BYREF
  WCHAR String1[264]; // [rsp+750h] [rbp+650h] BYREF
  WCHAR Dst[264]; // [rsp+960h] [rbp+860h] BYREF
  WCHAR FileName[264]; // [rsp+B70h] [rbp+A70h] BYREF

  v3 = g_pWmiEventManagerAvFw;
  v4 = 0;
  WbemServices = 0;
  hKey = 0;
  cSubKeys = 0;
  cchName = 0;
  pcbData = 0;
  v76 = 7;
  v75 = 0;
  LOWORD(Block[0]) = 0;
  v65 = 0;
  v70 = 0;
  v64 = 0;
  v66 = 0;
  v67 = 0;
  *(_OWORD *)lpSrc = 0;
  v72 = 0;
  *(_OWORD *)pbComputedHash = 0;
  pcbComputedHash = 16;
  pCertContext = 0;
  pv = 0;
  if ( !ExpandEnvironmentStringsW(L"%CommonProgramFiles%\\AV", Dst, 0x104u) )
    goto LABEL_11;
  PseudoExpiredProductsList = CreatePseudoExpiredProductsList();
  WbemServices = PseudoExpiredProductsList;
  if ( PseudoExpiredProductsList < 0
    && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
      (unsigned int)PseudoExpiredProductsList);
  }
  v7 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Security Center\\ProvidersMigration\\WicaUpgradableAVs",
         0,
         0,
         0,
         0x2000Fu,
         0,
         &hKey,
         0);
  if ( v7 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_11;
    }
    v9 = 37;
    goto LABEL_10;
  }
  v7 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  if ( v7 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_11;
    }
    v9 = 38;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, v7);
    goto LABEL_11;
  }
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, cSubKeys);
  v11 = 0;
  v12 = cSubKeys;
  if ( cSubKeys )
  {
    while ( 1 )
    {
      cchName = 260;
      pcbData = 520;
      memset_0(Name, 0, 0x208u);
      memset_0(pvData, 0, 0x208u);
      memset_0(v81, 0, 0x208u);
      v13 = Block;
      if ( v76 >= 8 )
        v13 = (void **)Block[0];
      v75 = 0;
      *(_WORD *)v13 = 0;
      if ( RegEnumKeyExW(hKey, v11, Name, &cchName, 0, 0, 0, 0) )
      {
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, v11);
        }
        goto LABEL_51;
      }
      std::wstring::assign(Block, L"SOFTWARE\\Microsoft\\Security Center\\ProvidersMigration\\WicaUpgradableAVs");
      std::wstring::append(Block, L"\\");
      std::wstring::append(Block, Name);
      v14 = Block;
      if ( v76 >= 8 )
        v14 = (void **)Block[0];
      ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, (LPCWSTR)v14, L"RemediationExe", 2u, 0, pvData, &pcbData);
      if ( ValueW || !pvData[0] )
        break;
      if ( GetFileAttributesW(pvData) == -1 )
      {
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, pvData);
        }
        goto LABEL_51;
      }
      v16 = Block;
      if ( v76 >= 8 )
        v16 = (void **)Block[0];
      ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, (LPCWSTR)v16, L"DisplayName", 2u, 0, v81, &pcbData);
      if ( !ValueW && v81[0] )
      {
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            44,
            (unsigned int)WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
            (unsigned int)v81,
            (__int64)pvData);
        }
        std::wstring::wstring(v78, pvData);
        v17 = std::map<std::wstring,std::wstring>::operator[](&g_UpgradableProducts, v78);
        std::wstring::assign(v17, v81);
        std::wstring::_Tidy(v78, 1, 0);
        goto LABEL_51;
      }
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v19 = 43;
LABEL_50:
        WPP_SF_SD(
          *((_QWORD *)v18 + 2),
          v19,
          (unsigned int)WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
          (unsigned int)Name,
          ValueW);
      }
LABEL_51:
      ++v11;
      v12 = cSubKeys;
      if ( v11 >= cSubKeys )
        goto LABEL_52;
    }
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_51;
    }
    v19 = 41;
    goto LABEL_50;
  }
LABEL_52:
  if ( !a2 || *(int *)(a2 + 48) <= 0 )
  {
LABEL_145:
    v40 = 0;
    if ( v12 )
    {
      do
      {
        cchName = 260;
        pcbData = 520;
        memset_0(Name, 0, 0x208u);
        v41 = Block;
        if ( v76 >= 8 )
          v41 = (void **)Block[0];
        v75 = 0;
        *(_WORD *)v41 = 0;
        if ( RegEnumKeyExW(hKey, v40, Name, &cchName, 0, 0, 0, 0) )
        {
          if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, v40);
          }
        }
        else
        {
          std::wstring::assign(Block, L"SOFTWARE\\Microsoft\\Security Center\\ProvidersMigration\\WicaUpgradableAVs");
          std::wstring::append(Block, L"\\");
          std::wstring::append(Block, Name);
          v42 = Block;
          if ( v76 >= 8 )
            v42 = (void **)Block[0];
          v43 = RegDeleteKeyW(HKEY_LOCAL_MACHINE, (LPCWSTR)v42);
          if ( ((v43 & 0xFFFFFFFC) != 0 || v43 == 1)
            && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              58,
              (unsigned int)WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
              (unsigned int)Name,
              v43);
          }
        }
        ++v40;
      }
      while ( v40 < cSubKeys );
    }
    v44 = *(_QWORD **)g_UpgradableProducts;
    while ( 1 )
    {
      if ( v44 == (_QWORD *)g_UpgradableProducts )
        goto LABEL_11;
      cchName = 260;
      pcbData = 520;
      memset_0(Name, 0, 0x208u);
      v46 = *(_QWORD **)g_RemovedButNotUpgradableProducts;
      while ( v46 != (_QWORD *)g_RemovedButNotUpgradableProducts )
      {
        if ( !(unsigned int)std::wstring::compare(v44 + 8, (__int64)(v46 + 8)) )
        {
          std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::erase(
            &g_RemovedButNotUpgradableProducts,
            &v65,
            v46);
          break;
        }
        if ( !*((_BYTE *)v46 + 25) )
        {
          v47 = v46[2];
          if ( *(_BYTE *)(v47 + 25) )
          {
            for ( i = (_QWORD *)v46[1]; !*((_BYTE *)i + 25) && v46 == (_QWORD *)i[2]; i = (_QWORD *)i[1] )
              v46 = i;
          }
          else
          {
            i = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Min((_QWORD *)v47);
          }
          v46 = i;
        }
      }
      v49 = (const BYTE *)(v44 + 8);
      if ( v44[11] < 8u )
        v50 = (const unsigned __int16 *)(v44 + 8);
      else
        v50 = *(const unsigned __int16 **)v49;
      WbemServices = StripInvalidPathCharsFromString(v50, Name, v45);
      if ( WbemServices >= 0 )
      {
        std::wstring::assign(Block, L"SOFTWARE\\Microsoft\\Security Center\\ProvidersMigration\\WicaUpgradableAVs");
        std::wstring::append(Block, L"\\");
        std::wstring::append(Block, Name);
        v51 = Block;
        if ( v76 >= 8 )
          v51 = (void **)Block[0];
        v52 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)v51, 0, 0, 0, 0x20007u, 0, &hKey, 0);
        if ( v52 )
        {
          v53 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          {
            goto LABEL_197;
          }
          v54 = 59;
          goto LABEL_196;
        }
        v55 = 2 * *((_DWORD *)v44 + 12);
        pcbData = v55;
        v56 = (const BYTE *)(v44 + 4);
        if ( v44[7] >= 8u )
          v56 = *(const BYTE **)v56;
        v52 = RegSetValueExW(hKey, L"RemediationExe", 0, 1u, v56, v55);
        if ( v52 )
        {
          v53 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          {
            goto LABEL_197;
          }
          v54 = 60;
          goto LABEL_196;
        }
        v57 = 2 * *((_DWORD *)v44 + 20);
        pcbData = v57;
        if ( v44[11] >= 8u )
          v49 = *(const BYTE **)v49;
        v52 = RegSetValueExW(hKey, L"DisplayName", 0, 1u, v49, v57);
        if ( v52 )
        {
          v53 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v54 = 61;
LABEL_196:
            WPP_SF_SD(
              *((_QWORD *)v53 + 2),
              v54,
              (unsigned int)WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
              (unsigned int)Name,
              v52);
          }
        }
      }
LABEL_197:
      if ( !*((_BYTE *)v44 + 25) )
      {
        v58 = v44[2];
        if ( *(_BYTE *)(v58 + 25) )
        {
          for ( j = (_QWORD *)v44[1]; !*((_BYTE *)j + 25) && v44 == (_QWORD *)j[2]; j = (_QWORD *)j[1] )
            v44 = j;
        }
        else
        {
          j = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Min((_QWORD *)v58);
        }
        v44 = j;
      }
    }
  }
  if ( GetFileAttributesW(Dst) == -1 )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, Dst);
    }
    v4 = 1;
  }
  v21 = SysAllocString(L"AntiVirusProduct");
  if ( !v21 )
  {
    WbemServices = -2147024882;
    goto LABEL_11;
  }
  WbemServices = CWmiEventManager::GetWbemServices(v3, v20, &v65);
  if ( WbemServices < 0 )
    goto LABEL_143;
  v70 = 0;
  WbemServices = ((__int64 (__fastcall *)(struct IWbemServices *, OLECHAR *, __int64, _QWORD, __int64 *))v65->lpVtbl->CreateInstanceEnum)(
                   v65,
                   v21,
                   32,
                   0,
                   &v70);
  if ( WbemServices < 0 )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        46,
        WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
        (unsigned int)WbemServices);
    }
    goto LABEL_143;
  }
  while ( 1 )
  {
    if ( v64 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
      v64 = 0;
    }
    if ( pCertContext )
    {
      CertFreeCertificateContext(pCertContext);
      pCertContext = 0;
    }
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v66 = 0;
    v22 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, int *))(*(_QWORD *)v70 + 32LL))(
            v70,
            1000,
            1,
            &v64,
            &v66);
    if ( v22 )
      break;
    if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, LPCWSTR *, _QWORD, _QWORD))(*(_QWORD *)v64 + 32LL))(
           v64,
           L"displayName",
           0,
           lpSrc,
           0,
           0) >= 0
      && LOWORD(lpSrc[0]) != 1
      && (int)StringCchCopyW(v81, 0x104u, lpSrc[1]) >= 0
      && (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, LPCWSTR *, _QWORD, _QWORD))(*(_QWORD *)v64 + 32LL))(
           v64,
           L"pathToSignedReportingExe",
           0,
           lpSrc,
           0,
           0) >= 0
      && LOWORD(lpSrc[0]) != 1 )
    {
      if ( ExpandEnvironmentStringsW(lpSrc[1], String1, 0x104u) - 1 > 0x103 )
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v30 = 47;
          v31 = String1;
LABEL_140:
          WPP_SF_S(*((_QWORD *)v29 + 2), v30, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, v31);
        }
      }
      else
      {
        v23 = 0;
        HeadPosition = (struct IWbemServices *)CList<unsigned short *,unsigned short *>::GetHeadPosition(a2);
        v65 = HeadPosition;
        while ( HeadPosition )
        {
          Next = (const wchar_t *)CList<unsigned short *,unsigned short *>::GetNext(a2, &v65);
          if ( !_wcsicmp(String1, Next) )
          {
            v23 = 1;
            std::wstring::wstring(v78, String1);
            v27 = std::map<std::wstring,std::wstring>::operator[](&g_RemovedButNotUpgradableProducts, v78);
            std::wstring::assign(v27, v81);
            std::wstring::_Tidy(v78, 1, 0);
            break;
          }
          HeadPosition = v65;
        }
        if ( !v4
          && (int)StripInvalidPathCharsFromString(v81, Name, v25) >= 0
          && (int)StringCchPrintfW(FileName, 0x104u, L"%ls\\%ls", Dst, Name) >= 0 )
        {
          FileAttributesW = GetFileAttributesW(FileName);
          if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
          {
            v29 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              v30 = 48;
              v31 = FileName;
              goto LABEL_140;
            }
          }
          else if ( (int)StringCchPrintfW(pvData, 0x104u, L"%ls\\upgrade.exe", FileName) >= 0 )
          {
            if ( GetFileAttributesW(pvData) == -1 )
            {
              v29 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                v30 = 49;
LABEL_94:
                v31 = pvData;
                goto LABEL_140;
              }
            }
            else
            {
              if ( !v23 )
              {
                if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                {
                  WPP_SF_S(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    50,
                    WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
                    pvData);
                }
                std::wstring::wstring(v78, pvData);
                std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::erase(
                  v32,
                  v78);
                goto LABEL_100;
              }
              IsPseudoExpired = GetIsPseudoExpired(String1, &v67);
              if ( IsPseudoExpired >= 0 )
              {
                if ( v67 )
                {
                  v29 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                  {
                    v30 = 52;
                    goto LABEL_94;
                  }
                }
                else if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, LPCWSTR *, _QWORD, _QWORD))(*(_QWORD *)v64 + 32LL))(
                            v64,
                            L"productState",
                            0,
                            lpSrc,
                            0,
                            0) >= 0
                       && LOWORD(lpSrc[0]) != 1 )
                {
                  ProductState = ExtractProductState(LODWORD(lpSrc[1]));
                  if ( (ProductState & 0xFFFFBFFF) != 0 )
                  {
                    if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, LPCWSTR *, _QWORD, _QWORD))(*(_QWORD *)v64 + 32LL))(
                           v64,
                           L"instanceGuid",
                           0,
                           lpSrc,
                           0,
                           0) >= 0
                      && LOWORD(lpSrc[0]) != 1 )
                    {
                      ProductState = GetCertContext(pvData, &pCertContext);
                      if ( ProductState >= 0 )
                      {
                        if ( CryptHashPublicKeyInfo(
                               0,
                               0x8003u,
                               0,
                               1u,
                               &pCertContext->pCertInfo->SubjectPublicKeyInfo,
                               pbComputedHash,
                               &pcbComputedHash) )
                        {
                          *(_DWORD *)pbComputedHash ^= 0x7C15780Fu;
                          *(_WORD *)&pbComputedHash[4] ^= 0x298Du;
                          *(_WORD *)&pbComputedHash[6] ^= 0x46CFu;
                          for ( k = 0; k != 8; ++k )
                            pbComputedHash[k + 8] ^= *((_BYTE *)&qword_1800487D8 + k);
                          if ( StringFromCLSID((const IID *const)pbComputedHash, (LPOLESTR *)&pv) >= 0 )
                          {
                            if ( _wcsicmp(lpSrc[1], (const wchar_t *)pv) )
                            {
                              if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
                                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                              {
                                WPP_SF_SS(
                                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                                  55,
                                  (unsigned int)WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
                                  (unsigned int)v81,
                                  (__int64)pvData);
                              }
                            }
                            else
                            {
                              if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
                                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                              {
                                WPP_SF_SS(
                                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                                  56,
                                  (unsigned int)WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
                                  (unsigned int)v81,
                                  (__int64)pvData);
                              }
                              std::wstring::wstring(v78, pvData);
                              v39 = std::map<std::wstring,std::wstring>::operator[](&g_UpgradableProducts, v78);
                              std::wstring::assign(v39, v81);
LABEL_100:
                              std::wstring::_Tidy(v78, 1, 0);
                            }
                          }
                        }
                      }
                      else
                      {
                        v35 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                        {
                          v36 = 54;
                          v37 = pvData;
                          goto LABEL_133;
                        }
                      }
                    }
                  }
                  else
                  {
                    v35 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                    {
                      v36 = 53;
                      v37 = v81;
LABEL_133:
                      WPP_SF_SD(
                        *((_QWORD *)v35 + 2),
                        v36,
                        (unsigned int)WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
                        (_DWORD)v37,
                        ProductState);
                    }
                  }
                }
              }
              else if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
                     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  51,
                  WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
                  (unsigned int)IsPseudoExpired);
              }
            }
          }
        }
      }
    }
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
  WbemServices = 0;
  if ( v22 != 1 )
    WbemServices = v22;
LABEL_143:
  SysFreeString(v21);
  if ( !v4 )
  {
    v12 = cSubKeys;
    goto LABEL_145;
  }
LABEL_11:
  RegCloseKey(hKey);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::clear(&g_ExpiredProducts);
  if ( v76 >= 8 )
    operator delete(Block[0]);
  return (unsigned int)WbemServices;
}

```

## disassembly

```asm
0x180021128  push    rbp
0x18002112a  push    rbx
0x18002112b  push    rsi
0x18002112c  push    rdi
0x18002112d  push    r12
0x18002112f  push    r13
0x180021131  push    r14
0x180021133  push    r15
0x180021135  lea     rbp, [rsp-0C98h]
0x18002113d  sub     rsp, 0D98h
0x180021144  mov     rax, cs:__security_cookie
0x18002114b  xor     rax, rsp
0x18002114e  mov     [rbp+0CD0h+var_50], rax
0x180021155  mov     r13, rdx
0x180021158  mov     r14, cs:?g_pWmiEventManagerAvFw@@3PEAVCWmiEventManagerAvFw@@EA; CWmiEventManagerAvFw * g_pWmiEventManagerAvFw
0x18002115f  xor     r15d, r15d
0x180021162  mov     esi, r15d
0x180021165  mov     [rsp+0DD0h+hKey], r15
0x18002116a  mov     [rsp+0DD0h+cSubKeys], r15d
0x18002116f  mov     [rsp+0DD0h+cchName], r15d
0x180021174  mov     [rsp+0DD0h+pcbData], r15d
0x180021179  mov     [rbp+0CD0h+var_CF0], 7
0x180021181  mov     [rbp+0CD0h+var_CF8], r15
0x180021185  mov     word ptr [rbp+0CD0h+Block], r15w
0x18002118a  mov     [rbp+0CD0h+var_D50], r15
0x18002118e  mov     [rbp+0CD0h+var_D30], r15
0x180021192  mov     [rsp+0DD0h+var_D58], r15
0x180021197  mov     [rbp+0CD0h+var_D48], r15d
0x18002119b  mov     [rbp+0CD0h+var_D44], r15d
0x18002119f  xorps   xmm0, xmm0
0x1800211a2  xor     eax, eax
0x1800211a4  movups  xmmword ptr [rbp+0CD0h+lpSrc], xmm0
0x1800211a8  mov     [rbp+0CD0h+var_D18], rax
0x1800211ac  movups  xmmword ptr [rbp+0CD0h+pbComputedHash], xmm0
0x1800211b0  mov     [rbp+0CD0h+pcbComputedHash], 10h
0x1800211b7  mov     [rbp+0CD0h+pCertContext], r15
0x1800211bb  mov     [rbp+0CD0h+pv], r15
0x1800211bf  mov     r8d, 104h; nSize
0x1800211c5  lea     rdx, [rbp+0CD0h+Dst]; lpDst
0x1800211cc  lea     rcx, Src; "%CommonProgramFiles%\\AV"
0x1800211d3  call    cs:__imp_ExpandEnvironmentStringsW
0x1800211d9  test    eax, eax
0x1800211db  jz      loc_180021287
0x1800211e1  call    ?CreatePseudoExpiredProductsList@@YAJXZ; CreatePseudoExpiredProductsList(void)
0x1800211e6  mov     esi, eax
0x1800211e8  lea     rbx, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x1800211ef  lea     r12, WPP_GLOBAL_Control
0x1800211f6  test    eax, eax
0x1800211f8  jns     short loc_18002121F
0x1800211fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180021201  cmp     rcx, r12
0x180021204  jz      short loc_18002121F
0x180021206  test    byte ptr [rcx+1Ch], 1
0x18002120a  jz      short loc_18002121F
0x18002120c  lea     edx, [r15+24h]
0x180021210  mov     r9d, eax
0x180021213  mov     r8, rbx
0x180021216  mov     rcx, [rcx+10h]
0x18002121a  call    WPP_SF_d
0x18002121f  mov     [rsp+0DD0h+lpdwDisposition], r15; lpdwDisposition
0x180021224  lea     rax, [rsp+0DD0h+hKey]
0x180021229  mov     [rsp+0DD0h+phkResult], rax; phkResult
0x18002122e  mov     [rsp+0DD0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180021233  mov     [rsp+0DD0h+samDesired], 2000Fh; samDesired
0x18002123b  mov     [rsp+0DD0h+dwOptions], r15d; dwOptions
0x180021240  xor     r9d, r9d; lpClass
0x180021243  xor     r8d, r8d; Reserved
0x180021246  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Security Center\\P"...
0x18002124d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180021254  call    cs:__imp_RegCreateKeyExW
0x18002125a  test    eax, eax
0x18002125c  jz      short loc_1800212D4
0x18002125e  mov     rcx, cs:WPP_GLOBAL_Control
0x180021265  cmp     rcx, r12
0x180021268  jz      short loc_180021287
0x18002126a  mov     dil, 4
0x18002126d  test    [rcx+1Ch], dil
0x180021271  jz      short loc_180021287
0x180021273  mov     edx, 25h ; '%'
0x180021278  mov     r9d, eax
0x18002127b  mov     r8, rbx
0x18002127e  mov     rcx, [rcx+10h]
0x180021282  call    WPP_SF_d
0x180021287  mov     rcx, [rsp+0DD0h+hKey]; hKey
0x18002128c  call    cs:__imp_RegCloseKey
0x180021292  lea     rcx, ?g_ExpiredProducts@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@A; std::map<std::wstring,std::wstring> g_ExpiredProducts
0x180021299  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::clear(void)
0x18002129e  nop
0x18002129f  cmp     [rbp+0CD0h+var_CF0], 8
0x1800212a4  jb      short loc_1800212AF
0x1800212a6  mov     rcx, [rbp+0CD0h+Block]; Block
0x1800212aa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800212af  mov     eax, esi
0x1800212b1  mov     rcx, [rbp+0CD0h+var_50]
0x1800212b8  xor     rcx, rsp; StackCookie
0x1800212bb  call    __security_check_cookie
0x1800212c0  add     rsp, 0D98h
0x1800212c7  pop     r15
0x1800212c9  pop     r14
0x1800212cb  pop     r13
0x1800212cd  pop     r12
0x1800212cf  pop     rdi
0x1800212d0  pop     rsi
0x1800212d1  pop     rbx
0x1800212d2  pop     rbp
0x1800212d3  retn
0x1800212d4  mov     [rsp+0DD0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800212d9  mov     [rsp+0DD0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800212de  mov     [rsp+0DD0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800212e3  mov     [rsp+0DD0h+lpdwDisposition], r15; lpcbMaxValueNameLen
0x1800212e8  mov     [rsp+0DD0h+phkResult], r15; lpcValues
0x1800212ed  mov     [rsp+0DD0h+lpSecurityAttributes], r15; lpcbMaxClassLen
0x1800212f2  mov     qword ptr [rsp+0DD0h+samDesired], r15; lpcbMaxSubKeyLen
0x1800212f7  lea     rax, [rsp+0DD0h+cSubKeys]
0x1800212fc  mov     qword ptr [rsp+0DD0h+dwOptions], rax; lpcSubKeys
0x180021301  xor     r9d, r9d; lpReserved
0x180021304  xor     r8d, r8d; lpcchClass
0x180021307  xor     edx, edx; lpClass
0x180021309  mov     rcx, [rsp+0DD0h+hKey]; hKey
0x18002130e  call    cs:__imp_RegQueryInfoKeyW
0x180021314  test    eax, eax
0x180021316  jz      short loc_18002133F
0x180021318  mov     rcx, cs:WPP_GLOBAL_Control
0x18002131f  cmp     rcx, r12
0x180021322  jz      loc_180021287
0x180021328  mov     dil, 4
0x18002132b  test    [rcx+1Ch], dil
0x18002132f  jz      loc_180021287
0x180021335  mov     edx, 26h ; '&'
0x18002133a  jmp     loc_180021278
0x18002133f  mov     dil, 4
0x180021342  mov     rcx, cs:WPP_GLOBAL_Control
0x180021349  cmp     rcx, r12
0x18002134c  jz      short loc_18002136A
0x18002134e  test    [rcx+1Ch], dil
0x180021352  jz      short loc_18002136A
0x180021354  mov     edx, 27h ; '''
0x180021359  mov     r9d, [rsp+0DD0h+cSubKeys]
0x18002135e  mov     r8, rbx
0x180021361  mov     rcx, [rcx+10h]
0x180021365  call    WPP_SF_d
0x18002136a  mov     ebx, r15d
0x18002136d  mov     eax, [rsp+0DD0h+cSubKeys]
0x180021371  test    eax, eax
0x180021373  jz      loc_180021627
0x180021379  mov     [rsp+0DD0h+cchName], 104h
0x180021381  mov     [rsp+0DD0h+pcbData], 208h
0x180021389  xor     edx, edx; Val
0x18002138b  mov     r8d, 208h; Size
0x180021391  lea     rcx, [rbp+0CD0h+Name]; void *
0x180021398  call    memset_0
0x18002139d  xor     edx, edx; Val
0x18002139f  mov     r8d, 208h; Size
0x1800213a5  lea     rcx, [rbp+0CD0h+pvData]; void *
0x1800213a9  call    memset_0
0x1800213ae  xor     edx, edx; Val
0x1800213b0  mov     r8d, 208h; Size
0x1800213b6  lea     rcx, [rbp+0CD0h+var_890]; void *
0x1800213bd  call    memset_0
0x1800213c2  lea     rcx, [rbp+0CD0h+Block]
0x1800213c6  cmp     [rbp+0CD0h+var_CF0], 8
0x1800213cb  cmovnb  rcx, [rbp+0CD0h+Block]
0x1800213d0  mov     [rbp+0CD0h+var_CF8], r15
0x1800213d4  mov     [rcx], r15w
0x1800213d8  mov     [rsp+0DD0h+phkResult], r15; lpftLastWriteTime
0x1800213dd  mov     [rsp+0DD0h+lpSecurityAttributes], r15; lpcchClass
0x1800213e2  mov     qword ptr [rsp+0DD0h+samDesired], r15; lpClass
0x1800213e7  mov     qword ptr [rsp+0DD0h+dwOptions], r15; lpReserved
0x1800213ec  lea     r9, [rsp+0DD0h+cchName]; lpcchName
0x1800213f1  lea     r8, [rbp+0CD0h+Name]; lpName
0x1800213f8  mov     edx, ebx; dwIndex
0x1800213fa  mov     rcx, [rsp+0DD0h+hKey]; hKey
0x1800213ff  call    cs:__imp_RegEnumKeyExW
0x180021405  test    eax, eax
0x180021407  jz      short loc_180021440
0x180021409  mov     rcx, cs:WPP_GLOBAL_Control
0x180021410  cmp     rcx, r12
0x180021413  jz      loc_180021619
0x180021419  test    [rcx+1Ch], dil
0x18002141d  jz      loc_180021619
0x180021423  mov     edx, 28h ; '('
0x180021428  mov     r9d, ebx
0x18002142b  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x180021432  mov     rcx, [rcx+10h]
0x180021436  call    WPP_SF_d
0x18002143b  jmp     loc_180021619
0x180021440  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Security Center\\P"...
0x180021447  lea     rcx, [rbp+0CD0h+Block]
0x18002144b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180021450  lea     rdx, asc_1800465F0; "\\"
0x180021457  lea     rcx, [rbp+0CD0h+Block]
0x18002145b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180021460  lea     rdx, [rbp+0CD0h+Name]
0x180021467  lea     rcx, [rbp+0CD0h+Block]
0x18002146b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180021470  lea     rdx, [rbp+0CD0h+Block]
0x180021474  cmp     [rbp+0CD0h+var_CF0], 8
0x180021479  cmovnb  rdx, [rbp+0CD0h+Block]; lpSubKey
0x18002147e  lea     rax, [rsp+0DD0h+pcbData]
0x180021483  mov     [rsp+0DD0h+lpSecurityAttributes], rax; pcbData
0x180021488  lea     rax, [rbp+0CD0h+pvData]
0x18002148c  mov     qword ptr [rsp+0DD0h+samDesired], rax; pvData
0x180021491  mov     qword ptr [rsp+0DD0h+dwOptions], r15; pdwType
0x180021496  mov     r9d, 2; dwFlags
0x18002149c  lea     r8, aRemediationexe; "RemediationExe"
0x1800214a3  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800214aa  call    cs:__imp_RegGetValueW
0x1800214b0  test    eax, eax
0x1800214b2  jnz     loc_1800215E7
0x1800214b8  cmp     [rbp+0CD0h+pvData], r15w
0x1800214bd  jz      loc_1800215E7
0x1800214c3  lea     rcx, [rbp+0CD0h+pvData]; lpFileName
0x1800214c7  call    cs:__imp_GetFileAttributesW
0x1800214cd  cmp     eax, 0FFFFFFFFh
0x1800214d0  jnz     short loc_18002150A
0x1800214d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800214d9  cmp     rcx, r12
0x1800214dc  jz      loc_180021619
0x1800214e2  test    [rcx+1Ch], dil
0x1800214e6  jz      loc_180021619
0x1800214ec  mov     edx, 2Ah ; '*'
0x1800214f1  lea     r9, [rbp+0CD0h+pvData]
0x1800214f5  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x1800214fc  mov     rcx, [rcx+10h]
0x180021500  call    WPP_SF_S
0x180021505  jmp     loc_180021619
0x18002150a  lea     rdx, [rbp+0CD0h+Block]
0x18002150e  cmp     [rbp+0CD0h+var_CF0], 8
0x180021513  cmovnb  rdx, [rbp+0CD0h+Block]; lpSubKey
0x180021518  lea     rax, [rsp+0DD0h+pcbData]
0x18002151d  mov     [rsp+0DD0h+lpSecurityAttributes], rax; pcbData
0x180021522  lea     rax, [rbp+0CD0h+var_890]
0x180021529  mov     qword ptr [rsp+0DD0h+samDesired], rax; pvData
0x18002152e  mov     qword ptr [rsp+0DD0h+dwOptions], r15; pdwType
0x180021533  mov     r9d, 2; dwFlags
0x180021539  lea     r8, aDisplayname; "DisplayName"
0x180021540  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180021547  call    cs:__imp_RegGetValueW
0x18002154d  test    eax, eax
0x18002154f  jnz     short loc_1800215CE
0x180021551  cmp     [rbp+0CD0h+var_890], r15w
0x180021559  jz      short loc_1800215CE
0x18002155b  mov     rcx, cs:WPP_GLOBAL_Control
0x180021562  cmp     rcx, r12
0x180021565  jz      short loc_180021590
0x180021567  test    [rcx+1Ch], dil
0x18002156b  jz      short loc_180021590
0x18002156d  lea     edx, [rax+2Ch]
0x180021570  lea     rax, [rbp+0CD0h+pvData]
0x180021574  mov     qword ptr [rsp+0DD0h+dwOptions], rax
0x180021579  lea     r9, [rbp+0CD0h+var_890]
0x180021580  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x180021587  mov     rcx, [rcx+10h]
0x18002158b  call    WPP_SF_SS
0x180021590  lea     rdx, [rbp+0CD0h+pvData]
0x180021594  lea     rcx, [rbp+0CD0h+var_CD8]
0x180021598  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18002159d  nop
0x18002159e  lea     rdx, [rbp+0CD0h+var_CD8]
0x1800215a2  lea     rcx, ?g_UpgradableProducts@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@A; std::map<std::wstring,std::wstring> g_UpgradableProducts
0x1800215a9  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x1800215ae  lea     rdx, [rbp+0CD0h+var_890]
0x1800215b5  mov     rcx, rax
0x1800215b8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800215bd  nop
0x1800215be  xor     r8d, r8d
0x1800215c1  mov     dl, 1
0x1800215c3  lea     rcx, [rbp+0CD0h+var_CD8]
0x1800215c7  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800215cc  jmp     short loc_180021619
0x1800215ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800215d5  cmp     rcx, r12
0x1800215d8  jz      short loc_180021619
0x1800215da  test    [rcx+1Ch], dil
0x1800215de  jz      short loc_180021619
0x1800215e0  mov     edx, 2Bh ; '+'
0x1800215e5  jmp     short loc_1800215FE
0x1800215e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800215ee  cmp     rcx, r12
0x1800215f1  jz      short loc_180021619
0x1800215f3  test    [rcx+1Ch], dil
0x1800215f7  jz      short loc_180021619
0x1800215f9  mov     edx, 29h ; ')'
0x1800215fe  mov     [rsp+0DD0h+dwOptions], eax
0x180021602  lea     r9, [rbp+0CD0h+Name]
0x180021609  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x180021610  mov     rcx, [rcx+10h]
0x180021614  call    WPP_SF_SD
0x180021619  inc     ebx
0x18002161b  mov     eax, [rsp+0DD0h+cSubKeys]
0x18002161f  cmp     ebx, eax
0x180021621  jb      loc_180021379
0x180021627  test    r13, r13
0x18002162a  jz      loc_180021D72
0x180021630  cmp     [r13+30h], r15d
0x180021634  jle     loc_180021D72
0x18002163a  lea     rcx, [rbp+0CD0h+Dst]; lpFileName
0x180021641  call    cs:__imp_GetFileAttributesW
0x180021647  cmp     eax, 0FFFFFFFFh
0x18002164a  jnz     short loc_180021680
  ... truncated ...
```
