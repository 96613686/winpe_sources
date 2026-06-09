# PolicyRefreshCacheHelper::RefreshGPCache(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,bool &,bool &)

- ea: `0x1800236b8`
- end: `0x180024025`
- name: `?RefreshGPCache@PolicyRefreshCacheHelper@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEA_N1@Z`
- size: `2413`
- prototype: `__int64 __fastcall(wchar_t *, _BYTE *, _BYTE *)`
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000cfc0`

## callees

- `0x18000aac0`
- `0x18000aae4`
- `0x18000e7e4`
- `0x18000f8a8`
- `0x18000fb4c`
- `0x18000fcc4`
- `0x180010260`
- `0x1800191d4`
- `0x18001eea4`
- `0x180022634`
- `0x180022788`
- `0x180022a48`
- `0x180022fc4`
- `0x180023288`
- `0x180023468`
- `0x1800236b8`
- `0x18002436c`
- `0x180024464`
- `0x1800246ac`
- `0x180024738`
- `0x180024d24`
- `0x180024dd0`
- `0x1800258bc`
- `0x180026c78`
- `0x180027144`
- `0x180027234`
- `0x18002c554`
- `0x18002d264`
- `0x18002ffd0`
- `0x180030cb4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002386f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002386f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023834`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800238b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023910`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023961`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023834`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800238b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023910`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023961`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002383c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002383c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023829`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023829`
- `USERENV!EnterCriticalPolicySection` at `0x18002373a`
- `USERENV!EnterCriticalPolicySection` at `0x18002373a`
- `USERENV!LeaveCriticalPolicySection` at `0x180023fc3`
- `USERENV!LeaveCriticalPolicySection` at `0x180023fc3`

## string_xrefs

- `0x180023d77`: `WindowsUpdate`
- `0x180023f26`: `WindowsUpdate`
- `0x180023eb9`: `ActiveCache`
- `0x180023d66`: `ActiveCacheHash`
- `0x180023f0f`: `ActiveCacheHash`
- `0x180023f45`: `ActiveCacheHash`
- `0x1800239c5`: `WindowsUpdate|WUServer`
- `0x1800239fb`: `WindowsUpdate|WUStatusServer`
- `0x180023a33`: `WindowsUpdate|UpdateServiceUrlAlternate`
- `0x180023d6d`: `\UpdatePolicy\GPCache`
- `0x180023750`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRefreshCacheHelper.cpp`
- `0x1800237ae`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRefreshCacheHelper.cpp`
- `0x180023fd7`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRefreshCacheHelper.cpp`
- `0x180023f7d`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRegistryHelper.cpp`

## pseudocode

```c
__int64 __fastcall PolicyRefreshCacheHelper::RefreshGPCache(wchar_t *a1, _BYTE *a2, _BYTE *a3)
{
  int GPActiveCache; // eax
  unsigned int v5; // ebx
  unsigned int v6; // r13d
  const char *v7; // r9
  _QWORD *v9; // rax
  __int64 v10; // rsi
  __int64 v11; // r15
  __m128i si128; // xmm6
  int GPCacheRegKeyPath; // eax
  int v14; // edi
  __int64 v15; // rdx
  HKEY v16; // rdi
  DWORD LastError; // ebx
  const WCHAR *v18; // rdx
  unsigned int v19; // eax
  void *v20; // rcx
  __int64 *v21; // rbx
  wchar_t *v22; // r12
  const wchar_t **v23; // rsi
  unsigned __int64 v24; // rdi
  const wchar_t *v25; // rcx
  size_t v26; // r8
  unsigned __int64 v27; // rdi
  const wchar_t *v28; // rcx
  size_t v29; // r8
  unsigned __int64 v30; // rdi
  const wchar_t *v31; // rcx
  size_t v32; // r8
  void *v33; // rax
  int Hash; // eax
  __int64 v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rax
  __int64 **v39; // rcx
  __int64 *m; // rax
  __int64 *n; // rcx
  _QWORD *v42; // rax
  __int64 v43; // rax
  __int64 **v44; // rdx
  __int64 *i; // rcx
  __int64 v46; // rcx
  __int64 j; // rax
  int GPSourceHash; // eax
  int HKLMValue; // eax
  __int64 v50; // rdx
  HKEY v51; // rbx
  __int64 v52; // r8
  const wchar_t *v53; // rdx
  const wchar_t *v54; // rcx
  __int64 k; // rbx
  __int64 v56; // rsi
  int refreshed; // eax
  int v58; // eax
  unsigned __int64 v59; // r9
  wchar_t **v60; // rbx
  int RedirectedRegistryKeyName; // eax
  __int64 v62; // rcx
  __int64 v63; // rdx
  __int64 v64; // r9
  int phkResult; // [rsp+28h] [rbp-E0h]
  _OWORD v66[2]; // [rsp+48h] [rbp-C0h] BYREF
  _OWORD v67[2]; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE *v68; // [rsp+88h] [rbp-80h]
  HANDLE *p_hSection; // [rsp+90h] [rbp-78h]
  char v70; // [rsp+98h] [rbp-70h]
  HANDLE hSection; // [rsp+A0h] [rbp-68h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp-60h] BYREF
  wchar_t **v73; // [rsp+B0h] [rbp-58h]
  wchar_t *S1[2]; // [rsp+B8h] [rbp-50h] BYREF
  size_t N; // [rsp+C8h] [rbp-40h]
  unsigned __int64 v76; // [rsp+D0h] [rbp-38h]
  LPCWSTR lpSubKey[2]; // [rsp+D8h] [rbp-30h] BYREF
  __m128i v78; // [rsp+E8h] [rbp-20h]
  __int128 v79; // [rsp+F8h] [rbp-10h] BYREF
  wchar_t *S2[2]; // [rsp+108h] [rbp+0h] BYREF
  __int64 v81; // [rsp+118h] [rbp+10h]
  unsigned __int64 v82; // [rsp+120h] [rbp+18h]
  wchar_t v83[256]; // [rsp+128h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+380h] [rbp+278h]

  v68 = a3;
  S1[0] = a1;
  LODWORD(hKey) = 1;
  GPActiveCache = PolicyRefreshCacheHelper::GetGPActiveCache((unsigned int *)&hKey);
  v5 = GPActiveCache;
  if ( GPActiveCache <= -2147024895 || (unsigned int)(GPActiveCache + 2147024892) <= 0x7FF8FFFB )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x155,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRefreshCacheHelper.cpp",
      (const char *)(unsigned int)GPActiveCache,
      phkResult);
    return v5;
  }
  v6 = ((_DWORD)hKey == 1) + 1;
  hSection = EnterCriticalPolicySection(1);
  if ( !hSection )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x15C,
             (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRefreshCacheHelper.cpp",
             v7);
  p_hSection = &hSection;
  v70 = 1;
  v79 = 0u;
  v9 = operator new(0x60u);
  *v9 = v9;
  v9[1] = v9;
  v9[2] = v9;
  *((_WORD *)v9 + 12) = 257;
  *(_QWORD *)&v79 = v9;
  v11 = *((_QWORD *)&UpdatePolicyReader::c_vszPolicy_GPCache_Regkeys + 1);
  v10 = UpdatePolicyReader::c_vszPolicy_GPCache_Regkeys;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  if ( (_QWORD)UpdatePolicyReader::c_vszPolicy_GPCache_Regkeys != *((_QWORD *)&UpdatePolicyReader::c_vszPolicy_GPCache_Regkeys
                                                                  + 1) )
  {
    while ( 1 )
    {
      std::wstring::wstring(lpSubKey, v10);
      hKey = 0;
      v66[0] = 0;
      v66[1] = si128;
      LOWORD(v66[0]) = 0;
      v67[0] = 0;
      v67[1] = si128;
      LOWORD(v67[0]) = 0;
      GPCacheRegKeyPath = PolicyRefreshCacheHelper::GetGPCacheRegKeyPath(lpSubKey);
      v14 = GPCacheRegKeyPath;
      if ( GPCacheRegKeyPath < 0 )
        break;
      v16 = hKey;
      if ( hKey )
      {
        LastError = GetLastError();
        RegCloseKey(v16);
        SetLastError(LastError);
      }
      hKey = 0;
      v18 = (const WCHAR *)lpSubKey;
      if ( v78.m128i_i64[1] > 7uLL )
        v18 = lpSubKey[0];
      v19 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v18, 0, 0x20019u, &hKey);
      if ( v19 )
      {
        v14 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x100,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRefreshCacheHelper.cpp",
                (const char *)v19,
                phkResult);
        std::wstring::~wstring(v67);
        std::wstring::~wstring(v66);
        if ( hKey )
          RegCloseKey(hKey);
        if ( v14 < 0 )
          goto LABEL_21;
      }
      else
      {
        GPCacheRegKeyPath = PolicyRefreshCacheHelper::ReadPolicyRegValue(hKey);
        v14 = GPCacheRegKeyPath;
        if ( GPCacheRegKeyPath < 0 )
        {
          v15 = 259;
LABEL_19:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v15,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRefreshCacheHelper.cpp",
            (const char *)(unsigned int)GPCacheRegKeyPath,
            phkResult);
          std::wstring::~wstring(v67);
          std::wstring::~wstring(v66);
          if ( hKey )
            RegCloseKey(hKey);
LABEL_21:
          if ( (unsigned int)(v14 + 2147024894) > 1 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x168,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRefreshCacheHelper.cpp",
              (const char *)(unsigned int)v14,
              phkResult);
            goto LABEL_23;
          }
          goto LABEL_26;
        }
        std::wstring::~wstring(v67);
        std::wstring::~wstring(v66);
        if ( hKey )
          RegCloseKey(hKey);
      }
LABEL_26:
      std::wstring::~wstring(lpSubKey);
      v10 += 32;
      if ( v10 == v11 )
      {
        v9 = (_QWORD *)v79;
        goto LABEL_28;
      }
    }
    v15 = 253;
    goto LABEL_19;
  }
LABEL_28:
  if ( *((_QWORD *)&v79 + 1) )
    *a2 = 1;
  v21 = (__int64 *)*v9;
  if ( *(_BYTE *)(*v9 + 25LL) )
  {
LABEL_64:
    *(_OWORD *)S2 = 0;
    v81 = 0;
    v82 = 7;
    LOWORD(S2[0]) = 0;
    S1[0] = 0;
    S1[1] = 0;
    hKey = (HKEY)S1;
    v73 = S1;
    v42 = operator new(0x60u);
    *v42 = v42;
    v42[1] = v42;
    v42[2] = v42;
    *((_WORD *)v42 + 12) = 257;
    S1[0] = (wchar_t *)v42;
    v43 = std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Copy_nodes<0>(
            S1,
            *(_QWORD *)(v79 + 8),
            v42);
    *((_QWORD *)S1[0] + 1) = v43;
    S1[1] = *((wchar_t **)&v79 + 1);
    v44 = (__int64 **)*((_QWORD *)S1[0] + 1);
    if ( *((_BYTE *)v44 + 25) )
    {
      *(_QWORD *)S1[0] = S1[0];
      *((wchar_t **)S1[0] + 2) = S1[0];
    }
    else
    {
      for ( i = *v44; !*((_BYTE *)i + 25); i = (__int64 *)*i )
        v44 = (__int64 **)i;
      *(_QWORD *)S1[0] = v44;
      v46 = *((_QWORD *)S1[0] + 1);
      for ( j = *(_QWORD *)(v46 + 16); !*(_BYTE *)(j + 25); j = *(_QWORD *)(j + 16) )
        v46 = j;
      *((_QWORD *)S1[0] + 2) = v46;
    }
    v73 = 0;
    std::_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>>::~_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>>(&hKey);
    GPSourceHash = PolicyRefreshCacheHelper::GenerateGPSourceHash(S1, S2);
    v14 = GPSourceHash;
    if ( GPSourceHash < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18B,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRefreshCacheHelper.cpp",
        (const char *)(unsigned int)GPSourceHash,
        phkResult);
LABEL_115:
      v20 = S2;
      goto LABEL_116;
    }
    *(_OWORD *)S1 = 0;
    N = 0;
    v76 = 7;
    LOWORD(S1[0]) = 0;
    hKey = 0;
    HKLMValue = PolicyRegistryHelper::GetHKLMValue(
                  L"WindowsUpdate",
                  L"\\UpdatePolicy\\GPCache",
                  L"ActiveCacheHash",
                  (wchar_t **)&hKey);
    v14 = HKLMValue;
    if ( HKLMValue >= 0 )
    {
      *(_OWORD *)lpSubKey = 0;
      v78 = 0;
      v51 = hKey;
      v52 = -1;
      do
        ++v52;
      while ( *((_WORD *)hKey + v52) );
      std::wstring::_Construct<1,wchar_t const *>(lpSubKey);
      std::wstring::operator=(S1, lpSubKey);
      std::wstring::~wstring(lpSubKey);
      if ( v51 )
        SusFree(v51);
    }
    else
    {
      if ( (unsigned int)(HKLMValue + 2147024894) > 1 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x37,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRefreshCacheHelper.cpp",
          (const char *)(unsigned int)HKLMValue,
          phkResult);
        if ( hKey )
          SusFree(hKey);
LABEL_83:
        v50 = 402;
        goto LABEL_112;
      }
      if ( hKey )
        SusFree(hKey);
      if ( v14 != -2147024894 && v14 != -2147024893 )
        goto LABEL_83;
    }
    v53 = (const wchar_t *)S2;
    if ( v82 > 7 )
      v53 = S2[0];
    v54 = (const wchar_t *)S1;
    if ( v76 > 7 )
      v54 = S1[0];
    if ( N == v81 && (!N || !wmemcmp(v54, v53, N)) )
    {
LABEL_95:
      v14 = 0;
LABEL_114:
      std::wstring::~wstring(S1);
      goto LABEL_115;
    }
    *v68 = 1;
    v56 = *((_QWORD *)&UpdatePolicyReader::c_vszPolicy_GPCache_Regkeys + 1);
    for ( k = UpdatePolicyReader::c_vszPolicy_GPCache_Regkeys; k != v56; k += 32 )
    {
      std::wstring::wstring(lpSubKey, k);
      refreshed = PolicyRefreshCacheHelper::RefreshGPCacheForEachNode((LPCWSTR)lpSubKey);
      v14 = refreshed;
      if ( refreshed < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x19B,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRefreshCacheHelper.cpp",
          (const char *)(unsigned int)refreshed,
          phkResult);
        std::wstring::~wstring(lpSubKey);
        goto LABEL_114;
      }
      std::wstring::~wstring(lpSubKey);
    }
    v58 = PolicyRegistryHelper::SetHKLMValue(v54, L"\\UpdatePolicy\\GPCache", L"ActiveCache", v6);
    v14 = v58;
    if ( v58 < 0 )
    {
      v59 = (unsigned int)v58;
      v50 = 418;
      goto LABEL_113;
    }
    v60 = S2;
    if ( v82 > 7 )
      v60 = (wchar_t **)S2[0];
    if ( aActivecachehas[0] )
    {
      RedirectedRegistryKeyName = PolicyRegistryHelper::GetRedirectedRegistryKeyName(
                                    L"WindowsUpdate",
                                    L"\\UpdatePolicy\\GPCache",
                                    v83,
                                    0x100u);
      v14 = RedirectedRegistryKeyName;
      if ( RedirectedRegistryKeyName >= 0 )
      {
        v14 = RegSetStringValue(v62, v83, L"ActiveCacheHash", v60);
        v64 = (unsigned int)v14;
        if ( v14 >= 0 )
          goto LABEL_95;
        v63 = 236;
      }
      else
      {
        v63 = 234;
        v64 = (unsigned int)RedirectedRegistryKeyName;
      }
    }
    else
    {
      v14 = -2147024809;
      v63 = 231;
      v64 = 2147942487LL;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v63,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRegistryHelper.cpp",
      (const char *)v64,
      phkResult);
    v50 = 424;
LABEL_112:
    v59 = (unsigned int)v14;
LABEL_113:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v50,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRefreshCacheHelper.cpp",
      (const char *)v59,
      phkResult);
    goto LABEL_114;
  }
  v22 = S1[0];
  while ( 1 )
  {
    v23 = (const wchar_t **)(v21 + 4);
    v24 = v21[6];
    v25 = (const wchar_t *)(v21 + 4);
    if ( (unsigned __int64)v21[7] > 7 )
      v25 = *v23;
    v26 = v21[6];
    if ( v24 > 0x16 )
      v26 = 22;
    if ( wmemcmp(v25, L"WindowsUpdate|WUServer", v26) || v24 != 22 )
    {
      v27 = v21[6];
      v28 = (const wchar_t *)(v21 + 4);
      if ( (unsigned __int64)v21[7] > 7 )
        v28 = *v23;
      v29 = v21[6];
      if ( v27 > 0x1C )
        v29 = 28;
      if ( wmemcmp(v28, L"WindowsUpdate|WUStatusServer", v29) || v27 != 28 )
      {
        v30 = v21[6];
        v31 = (const wchar_t *)(v21 + 4);
        if ( (unsigned __int64)v21[7] > 7 )
          v31 = *v23;
        v32 = v21[6];
        if ( v30 > 0x27 )
          v32 = 39;
        if ( wmemcmp(v31, L"WindowsUpdate|UpdateServiceUrlAlternate", v32) || v30 != 39 )
        {
          v37 = v21[6];
          if ( v37 == 0x7FFFFFFFFFFFFFFELL )
            std::_Xlen_string();
          std::wstring::wstring(lpSubKey, v37, L"=", 1);
          v38 = std::operator+<wchar_t>(v67, lpSubKey, v21 + 8);
          std::operator+<wchar_t>(v66, v38, L";");
          std::wstring::operator+=(v22);
          std::wstring::~wstring(v66);
          std::wstring::~wstring(v67);
          std::wstring::~wstring(lpSubKey);
          goto LABEL_55;
        }
      }
    }
    *(_OWORD *)lpSubKey = 0;
    v78 = si128;
    LOWORD(lpSubKey[0]) = 0;
    v33 = (void *)std::wstring::wstring(v66, v21 + 8);
    Hash = PolicyRefreshCacheHelper::GenerateHash(v33);
    v14 = Hash;
    if ( Hash < 0 )
      break;
    v35 = v21[6];
    if ( v35 == 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    std::wstring::wstring(v66, v35, L"=", 1);
    v36 = std::operator+<wchar_t>(S1, v66, lpSubKey);
    std::operator+<wchar_t>(v67, v36, L";");
    std::wstring::operator+=(v22);
    std::wstring::~wstring(v67);
    std::wstring::~wstring(S1);
    std::wstring::~wstring(v66);
    std::wstring::~wstring(lpSubKey);
LABEL_55:
    v39 = (__int64 **)v21[2];
    if ( *((_BYTE *)v39 + 25) )
    {
      for ( m = (__int64 *)v21[1]; !*((_BYTE *)m + 25) && v21 == (__int64 *)m[2]; m = (__int64 *)m[1] )
        v21 = m;
      v21 = m;
    }
    else
    {
      v21 = (__int64 *)v21[2];
      for ( n = *v39; !*((_BYTE *)n + 25); n = (__int64 *)*n )
        v21 = n;
    }
    if ( *((_BYTE *)v21 + 25) )
      goto LABEL_64;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x17D,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRefreshCacheHelper.cpp",
    (const char *)(unsigned int)Hash,
    phkResult);
LABEL_23:
  v20 = lpSubKey;
LABEL_116:
  std::wstring::~wstring(v20);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v79);
  LeaveCriticalPolicySection(hSection);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800236b8  mov     rax, rsp
0x1800236bb  mov     [rax+20h], rbx
0x1800236bf  push    rbp
0x1800236c0  push    rsi
0x1800236c1  push    rdi
0x1800236c2  push    r12
0x1800236c4  push    r13
0x1800236c6  push    r14
0x1800236c8  push    r15
0x1800236ca  lea     rbp, [rax-278h]
0x1800236d1  sub     rsp, 340h
0x1800236d8  movaps  xmmword ptr [rax-48h], xmm6
0x1800236dc  mov     rax, cs:__security_cookie
0x1800236e3  xor     rax, rsp
0x1800236e6  mov     [rbp+270h+var_50], rax
0x1800236ed  mov     [rbp+270h+var_2F0], r8
0x1800236f1  mov     r12, rdx
0x1800236f4  mov     [rbp+270h+S1], rcx
0x1800236f8  mov     dword ptr [rbp+270h+hKey], 1
0x1800236ff  lea     rcx, [rbp+270h+hKey]; unsigned int *
0x180023703  call    ?GetGPActiveCache@PolicyRefreshCacheHelper@@CAJAEAK@Z; PolicyRefreshCacheHelper::GetGPActiveCache(ulong &)
0x180023708  mov     ebx, eax
0x18002370a  cmp     eax, 80070001h
0x18002370f  jle     loc_180023FCD
0x180023715  lea     ecx, [rax+7FF8FFFCh]
0x18002371b  cmp     ecx, 7FF8FFFBh
0x180023721  jbe     loc_180023FCD
0x180023727  xor     ebx, ebx
0x180023729  mov     r13d, ebx
0x18002372c  cmp     dword ptr [rbp+270h+hKey], 1
0x180023730  setz    r13b
0x180023734  inc     r13d
0x180023737  lea     ecx, [rbx+1]; bMachine
0x18002373a  call    cs:__imp_EnterCriticalPolicySection
0x180023740  mov     [rbp+270h+hSection], rax
0x180023744  test    rax, rax
0x180023747  jnz     short loc_180023766
0x180023749  mov     rcx, [rbp+278h]; this
0x180023750  lea     r8, aCW1SSrcClientP_1; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180023757  mov     edx, 15Ch; void *
0x18002375c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023761  jmp     loc_180023FEA
0x180023766  lea     rax, [rbp+270h+hSection]
0x18002376a  mov     [rbp+270h+var_2E8], rax
0x18002376e  mov     [rbp+270h+var_2E0], 1
0x180023772  xorps   xmm0, xmm0
0x180023775  movups  [rbp+270h+var_280], xmm0
0x180023779  mov     qword ptr [rbp+270h+var_280], rbx
0x18002377d  mov     qword ptr [rbp+270h+var_280+8], rbx
0x180023781  mov     ecx, 60h ; '`'; Size
0x180023786  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002378b  mov     [rax], rax
0x18002378e  mov     [rax+8], rax
0x180023792  mov     [rax+10h], rax
0x180023796  mov     word ptr [rax+18h], 101h
0x18002379c  mov     qword ptr [rbp+270h+var_280], rax
0x1800237a0  mov     rsi, qword ptr cs:?c_vszPolicy_GPCache_Regkeys@UpdatePolicyReader@@2V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@B; std::vector<std::wstring> const UpdatePolicyReader::c_vszPolicy_GPCache_Regkeys
0x1800237a7  mov     r15, qword ptr cs:?c_vszPolicy_GPCache_Regkeys@UpdatePolicyReader@@2V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@B+8; std::vector<std::wstring> const UpdatePolicyReader::c_vszPolicy_GPCache_Regkeys
0x1800237ae  lea     r14, aCW1SSrcClientP_1; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x1800237b5  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800237bd  cmp     rsi, r15
0x1800237c0  jz      loc_180023982
0x1800237c6  mov     rdx, rsi
0x1800237c9  lea     rcx, [rbp+270h+lpSubKey]
0x1800237cd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800237d2  nop
0x1800237d3  mov     [rbp+270h+hKey], rbx
0x1800237d7  xorps   xmm0, xmm0
0x1800237da  movups  [rsp+370h+var_338+8], xmm0
0x1800237df  movdqu  [rsp+370h+var_328+8], xmm6
0x1800237e5  mov     word ptr [rsp+370h+var_338+8], bx
0x1800237ea  movups  [rsp+370h+var_318+8], xmm0
0x1800237ef  movdqu  [rsp+370h+var_308+8], xmm6
0x1800237f5  mov     word ptr [rsp+370h+var_318+8], bx
0x1800237fa  lea     r9, [rsp+370h+var_318+8]
0x1800237ff  lea     r8, [rsp+370h+var_338+8]
0x180023804  mov     edx, r13d
0x180023807  lea     rcx, [rbp+270h+lpSubKey]; Src
0x18002380b  call    ?GetGPCacheRegKeyPath@PolicyRefreshCacheHelper@@CAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KAEAV23@1@Z; PolicyRefreshCacheHelper::GetGPCacheRegKeyPath(std::wstring const &,ulong,std::wstring &,std::wstring &)
0x180023810  mov     edi, eax
0x180023812  test    eax, eax
0x180023814  jns     short loc_180023820
0x180023816  mov     edx, 0FDh
0x18002381b  jmp     loc_1800238DE
0x180023820  mov     rdi, [rbp+270h+hKey]
0x180023824  test    rdi, rdi
0x180023827  jz      short loc_180023844
0x180023829  call    cs:__imp_GetLastError
0x18002382f  mov     ebx, eax
0x180023831  mov     rcx, rdi; hKey
0x180023834  call    cs:__imp_RegCloseKey
0x18002383a  mov     ecx, ebx; dwErrCode
0x18002383c  call    cs:__imp_SetLastError
0x180023842  xor     ebx, ebx
0x180023844  mov     [rbp+270h+hKey], rbx
0x180023848  lea     rdx, [rbp+270h+lpSubKey]
0x18002384c  cmp     [rbp+270h+var_288], 7
0x180023851  cmova   rdx, [rbp+270h+lpSubKey]; lpSubKey
0x180023856  lea     rax, [rbp+270h+hKey]
0x18002385a  mov     [rsp+370h+phkResult], rax; int
0x18002385f  mov     r9d, 20019h; samDesired
0x180023865  xor     r8d, r8d; ulOptions
0x180023868  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002386f  call    cs:__imp_RegOpenKeyExW
0x180023875  test    eax, eax
0x180023877  jz      short loc_1800238C1
0x180023879  mov     rcx, [rbp+278h]; this
0x180023880  mov     r9d, eax; char *
0x180023883  mov     r8, r14; unsigned int
0x180023886  mov     edx, 100h; void *
0x18002388b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180023890  mov     edi, eax
0x180023892  lea     rcx, [rsp+370h+var_318+8]; void *
0x180023897  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002389c  nop
0x18002389d  lea     rcx, [rsp+370h+var_338+8]; void *
0x1800238a2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800238a7  nop
0x1800238a8  mov     rcx, [rbp+270h+hKey]; hKey
0x1800238ac  test    rcx, rcx
0x1800238af  jz      short loc_1800238B7
0x1800238b1  call    cs:__imp_RegCloseKey
0x1800238b7  test    edi, edi
0x1800238b9  jns     loc_180023968
0x1800238bf  jmp     short loc_180023916
0x1800238c1  lea     r8, [rbp+270h+var_280]
0x1800238c5  lea     rdx, [rsp+370h+var_318+8]
0x1800238ca  mov     rcx, [rbp+270h+hKey]; hKey
0x1800238ce  call    ?ReadPolicyRegValue@PolicyRefreshCacheHelper@@CAJPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@4@@Z; PolicyRefreshCacheHelper::ReadPolicyRegValue(HKEY__ *,std::wstring &,std::map<std::wstring,std::wstring> &)
0x1800238d3  mov     edi, eax
0x1800238d5  test    eax, eax
0x1800238d7  jns     short loc_180023942
0x1800238d9  mov     edx, 103h; void *
0x1800238de  mov     r9d, eax; char *
0x1800238e1  mov     r8, r14; unsigned int
0x1800238e4  mov     rcx, [rbp+278h]; this
0x1800238eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800238f0  nop
0x1800238f1  lea     rcx, [rsp+370h+var_318+8]; void *
0x1800238f6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800238fb  nop
0x1800238fc  lea     rcx, [rsp+370h+var_338+8]; void *
0x180023901  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023906  nop
0x180023907  mov     rcx, [rbp+270h+hKey]; hKey
0x18002390b  test    rcx, rcx
0x18002390e  jz      short loc_180023916
0x180023910  call    cs:__imp_RegCloseKey
0x180023916  lea     eax, [rdi+7FF8FFFEh]
0x18002391c  cmp     eax, 1
0x18002391f  jbe     short loc_180023968
0x180023921  mov     rcx, [rbp+278h]; this
0x180023928  mov     r9d, edi; char *
0x18002392b  mov     r8, r14; unsigned int
0x18002392e  mov     edx, 168h; void *
0x180023933  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023938  nop
0x180023939  lea     rcx, [rbp+270h+lpSubKey]
0x18002393d  jmp     loc_180023FAF
0x180023942  lea     rcx, [rsp+370h+var_318+8]; void *
0x180023947  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002394c  nop
0x18002394d  lea     rcx, [rsp+370h+var_338+8]; void *
0x180023952  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023957  nop
0x180023958  mov     rcx, [rbp+270h+hKey]; hKey
0x18002395c  test    rcx, rcx
0x18002395f  jz      short loc_180023968
0x180023961  call    cs:__imp_RegCloseKey
0x180023967  nop
0x180023968  lea     rcx, [rbp+270h+lpSubKey]; void *
0x18002396c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023971  add     rsi, 20h ; ' '
0x180023975  cmp     rsi, r15
0x180023978  jnz     loc_1800237C6
0x18002397e  mov     rax, qword ptr [rbp+270h+var_280]
0x180023982  xor     r15d, r15d
0x180023985  cmp     qword ptr [rbp+270h+var_280+8], r15
0x180023989  jz      short loc_180023990
0x18002398b  mov     byte ptr [r12], 1
0x180023990  mov     rbx, [rax]
0x180023993  cmp     [rbx+19h], r15b
0x180023997  jnz     loc_180023C2A
0x18002399d  mov     r12, [rbp+270h+S1]
0x1800239a1  mov     eax, 16h
0x1800239a6  lea     rsi, [rbx+20h]
0x1800239aa  mov     rdi, [rbx+30h]
0x1800239ae  mov     rcx, rsi
0x1800239b1  cmp     qword ptr [rsi+18h], 7
0x1800239b6  jbe     short loc_1800239BB
0x1800239b8  mov     rcx, [rsi]; S1
0x1800239bb  mov     r8, rdi
0x1800239be  cmp     rdi, rax
0x1800239c1  cmova   r8, rax; N
0x1800239c5  lea     rdx, aWindowsupdateW_0; "WindowsUpdate|WUServer"
0x1800239cc  call    wmemcmp
0x1800239d1  test    eax, eax
0x1800239d3  jnz     short loc_1800239DB
0x1800239d5  cmp     rdi, 16h
0x1800239d9  jz      short loc_180023A53
0x1800239db  mov     rdi, [rsi+10h]
0x1800239df  mov     rcx, rsi
0x1800239e2  cmp     qword ptr [rsi+18h], 7
0x1800239e7  jbe     short loc_1800239EC
0x1800239e9  mov     rcx, [rsi]; S1
0x1800239ec  mov     r8, rdi
0x1800239ef  mov     eax, 1Ch
0x1800239f4  cmp     rdi, rax
0x1800239f7  cmova   r8, rax; N
0x1800239fb  lea     rdx, aWindowsupdateW; "WindowsUpdate|WUStatusServer"
0x180023a02  call    wmemcmp
0x180023a07  test    eax, eax
0x180023a09  jnz     short loc_180023A13
0x180023a0b  lea     ecx, [rax+1Ch]
0x180023a0e  cmp     rdi, rcx
0x180023a11  jz      short loc_180023A53
0x180023a13  mov     rdi, [rsi+10h]
0x180023a17  mov     rcx, rsi
0x180023a1a  cmp     qword ptr [rsi+18h], 7
0x180023a1f  jbe     short loc_180023A24
0x180023a21  mov     rcx, [rsi]; S1
0x180023a24  mov     r8, rdi
0x180023a27  mov     eax, 27h ; '''
0x180023a2c  cmp     rdi, rax
0x180023a2f  cmova   r8, rax; N
0x180023a33  lea     rdx, aWindowsupdateU; "WindowsUpdate|UpdateServiceUrlAlternate"
0x180023a3a  call    wmemcmp
0x180023a3f  test    eax, eax
0x180023a41  jnz     loc_180023B3B
0x180023a47  lea     edx, [rax+27h]
0x180023a4a  cmp     rdi, rdx
0x180023a4d  jnz     loc_180023B3B
0x180023a53  xorps   xmm0, xmm0
0x180023a56  movups  xmmword ptr [rbp+270h+lpSubKey], xmm0
0x180023a5a  movdqu  xmmword ptr [rbp-20h], xmm6
0x180023a5f  xor     eax, eax
0x180023a61  mov     word ptr [rbp+270h+lpSubKey], ax
0x180023a65  lea     rdx, [rbx+40h]
0x180023a69  lea     rcx, [rsp+370h+var_338+8]
0x180023a6e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180023a73  lea     rdx, [rbp+270h+lpSubKey]
0x180023a77  mov     rcx, rax; void *
0x180023a7a  call    ?GenerateHash@PolicyRefreshCacheHelper@@CAJV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV23@@Z; PolicyRefreshCacheHelper::GenerateHash(std::wstring,std::wstring &)
0x180023a7f  mov     edi, eax
0x180023a81  xor     r15d, r15d
0x180023a84  test    eax, eax
0x180023a86  js      loc_180023CD3
0x180023a8c  mov     rcx, [rsi+10h]
0x180023a90  mov     rax, 7FFFFFFFFFFFFFFEh
0x180023a9a  sub     rax, rcx
0x180023a9d  cmp     rax, 1
0x180023aa1  jb      loc_18002401F
0x180023aa7  cmp     qword ptr [rsi+18h], 7
0x180023aac  jbe     short loc_180023AB1
0x180023aae  mov     rsi, [rsi]
0x180023ab1  mov     [rsp+370h+var_340], 1; __int64
0x180023aba  lea     rax, asc_18003F434; "="
0x180023ac1  mov     [rsp+370h+Src], rax; Src
0x180023ac6  mov     [rsp+370h+phkResult], rcx; __int64
0x180023acb  mov     r9, rsi
0x180023ace  lea     rcx, [rsp+370h+var_338+8]; void *
0x180023ad3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180023ad8  nop
0x180023ad9  lea     r8, [rbp+270h+lpSubKey]
0x180023add  lea     rdx, [rsp+370h+var_338+8]
0x180023ae2  lea     rcx, [rbp+270h+S1]
0x180023ae6  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x180023aeb  nop
0x180023aec  lea     r8, asc_18003F430; ";"
0x180023af3  mov     rdx, rax
0x180023af6  lea     rcx, [rsp+370h+var_318+8]
0x180023afb  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x180023b00  nop
0x180023b01  mov     rdx, rax
0x180023b04  mov     rcx, r12; Src
0x180023b07  call    ??Y?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator+=(std::wstring const &)
0x180023b0c  nop
0x180023b0d  lea     rcx, [rsp+370h+var_318+8]; void *
0x180023b12  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023b17  nop
0x180023b18  lea     rcx, [rbp+270h+S1]; void *
0x180023b1c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023b21  nop
0x180023b22  lea     rcx, [rsp+370h+var_338+8]; void *
0x180023b27  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023b2c  nop
0x180023b2d  lea     rcx, [rbp+270h+lpSubKey]; void *
0x180023b31  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023b36  jmp     loc_180023BDD
0x180023b3b  mov     rcx, [rsi+10h]
0x180023b3f  mov     rax, 7FFFFFFFFFFFFFFEh
0x180023b49  sub     rax, rcx
0x180023b4c  cmp     rax, 1
0x180023b50  jb      loc_180024019
0x180023b56  cmp     qword ptr [rsi+18h], 7
0x180023b5b  jbe     short loc_180023B60
0x180023b5d  mov     rsi, [rsi]
0x180023b60  mov     [rsp+370h+var_340], 1; __int64
0x180023b69  lea     rax, asc_18003F434; "="
0x180023b70  mov     [rsp+370h+Src], rax; Src
  ... truncated ...
```
