# CThirdPartyManager::LoadDatastoreInstances(CList<ushort *,ushort *> *)

- ea: `0x180016d50`
- end: `0x180017a41`
- name: `?LoadDatastoreInstances@CThirdPartyManager@@QEAAJPEAV?$CList@PEAGPEAG@@@Z`
- size: `3313`
- prototype: `__int64 __fastcall(CThirdPartyManager *, __int64)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001d9e0`

## callees

- `0x180008e48`
- `0x180008e88`
- `0x180016b94`
- `0x180016d50`
- `0x180017c30`
- `0x180018774`
- `0x180018970`
- `0x180018ab0`
- `0x180018b60`
- `0x18001f97c`
- `0x18002027c`
- `0x1800202e8`
- `0x18002698c`
- `0x180027b94`
- `0x1800287b0`
- `0x180029158`
- `0x180029e74`
- `0x180029fd0`
- `0x180029ffc`
- `0x18003fbf2`
- `0x18003fc30`
- `0x18003fcf0`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017548`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001793d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017548`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001793d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800174c3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800175c2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001763a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800176a1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017732`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800174c3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800175c2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001763a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800176a1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017732`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180016f1e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180016f1e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180017052`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180017052`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016e7b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016e7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016ec8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800179ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016ec8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800179ab`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180017507`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180017507`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001751c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001751c`

## pseudocode

```c
__int64 __fastcall CThirdPartyManager::LoadDatastoreInstances(CThirdPartyManager *a1, __int64 a2)
{
  __int64 v3; // r13
  enum _SECURITY_PRODUCT_TYPE v4; // eax
  const WCHAR *DatastoreRegKey; // r14
  HKEY *phkResult; // rax
  int v8; // ebx
  HKEY v9; // rcx
  unsigned int v10; // eax
  unsigned __int64 v11; // rbx
  DWORD v12; // eax
  LPCWSTR *v13; // rcx
  unsigned __int64 v14; // rbx
  const WCHAR *v15; // r12
  unsigned __int64 v16; // r15
  LPCWSTR *v17; // rax
  LPCWSTR *v18; // rax
  unsigned __int64 v19; // rcx
  LPCWSTR *v20; // rcx
  LPCWSTR *v21; // rcx
  unsigned __int64 v22; // rsi
  LPCWSTR *v23; // rax
  LPCWSTR *v24; // rax
  LPCWSTR *v25; // rax
  unsigned __int64 v26; // rdi
  unsigned __int64 v27; // rbx
  unsigned __int64 v28; // rsi
  LPCWSTR *v29; // r9
  LPCWSTR *v30; // rcx
  LPCWSTR *v31; // rcx
  unsigned __int64 v32; // rbx
  LPCWSTR *v33; // rcx
  LPCWSTR *v34; // rcx
  unsigned __int64 v35; // rbx
  LPCWSTR *v36; // rax
  LPCWSTR *v37; // rax
  LPCWSTR *v38; // rax
  unsigned __int64 v39; // rsi
  unsigned __int64 v40; // rdi
  unsigned __int64 v41; // rbx
  LPCWSTR *v42; // r9
  LPCWSTR *v43; // rcx
  LPCWSTR *v44; // rcx
  unsigned __int64 v45; // rdi
  LPCWSTR *v46; // rcx
  LPCWSTR *v47; // rcx
  LSTATUS ValueW; // eax
  int v49; // edx
  WCHAR *v50; // r9
  CThirdPartyManager *v51; // rcx
  const WCHAR *v52; // rdx
  const WCHAR *v53; // rdx
  const WCHAR *v54; // rdx
  const WCHAR *v55; // rdx
  CThirdPartyManager *v56; // rdi
  struct CExternalBase *v57; // rbx
  signed int LastError; // eax
  __int64 v59; // rdx
  DWORD pcbData; // [rsp+60h] [rbp-A0h] BYREF
  int v61; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD dwIndex; // [rsp+68h] [rbp-98h]
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  DWORD cSubKeys; // [rsp+78h] [rbp-88h] BYREF
  int v65; // [rsp+7Ch] [rbp-84h]
  __int64 v66; // [rsp+80h] [rbp-80h] BYREF
  DWORD cchName; // [rsp+88h] [rbp-78h] BYREF
  __int64 v68; // [rsp+90h] [rbp-70h] BYREF
  struct CExternalBase *v69; // [rsp+98h] [rbp-68h] BYREF
  __int64 v70; // [rsp+A0h] [rbp-60h]
  CThirdPartyManager *v71; // [rsp+A8h] [rbp-58h]
  LPCWSTR lpSubKey[2]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v73; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v74; // [rsp+C8h] [rbp-38h]
  WCHAR Name[520]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR pvData[520]; // [rsp+4E0h] [rbp+3E0h] BYREF
  _WORD v77[520]; // [rsp+8F0h] [rbp+7F0h] BYREF
  _WORD v78[520]; // [rsp+D00h] [rbp+C00h] BYREF
  _WORD v79[520]; // [rsp+1110h] [rbp+1010h] BYREF
  WCHAR Dst[520]; // [rsp+1520h] [rbp+1420h] BYREF

  v70 = a2;
  v71 = a1;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids);
  v68 = 0;
  v65 = (*(__int64 (__fastcall **)(CThirdPartyManager *, __int64 *))(*(_QWORD *)a1 + 40LL))(a1, &v68);
  v3 = v68;
  v66 = v68;
  v68 = 0;
  if ( v65 < 0 || !v3 )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids);
    }
    if ( v3 )
      (**(void (__fastcall ***)(__int64, __int64))v3)(v3, 1);
    return 2147500037LL;
  }
  v4 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v3 + 24LL))(v3);
  DatastoreRegKey = WscGetDatastoreRegKey(v4);
  if ( !DatastoreRegKey )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids);
    }
    CommonUtil::CAutoUniquePtr<CExternalBase,void>::~CAutoUniquePtr<CExternalBase,void>(&v66);
    return 2147942487LL;
  }
  hKey = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, DatastoreRegKey, 0, 0x30019u, phkResult);
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        WPP_945edad5fd7435d1f807bc12083ac763_Traceguids,
        DatastoreRegKey);
    }
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    v9 = hKey;
    if ( hKey )
      goto LABEL_18;
    goto LABEL_19;
  }
  cSubKeys = 0;
  v10 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  v8 = v10;
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids, v10);
    }
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    v9 = hKey;
    if ( hKey )
      goto LABEL_18;
    goto LABEL_19;
  }
  v11 = 7;
  v74 = 7;
  v73 = 0;
  LOWORD(lpSubKey[0]) = 0;
  memset_0(v79, 0, sizeof(v79));
  memset_0(v78, 0, sizeof(v78));
  v61 = 0;
  memset_0(pvData, 0, sizeof(pvData));
  memset_0(v77, 0, sizeof(v77));
  v12 = 0;
  while ( 1 )
  {
    dwIndex = v12;
    if ( v12 >= cSubKeys )
    {
      if ( v11 >= 8 )
        operator delete((void *)lpSubKey[0]);
      v74 = 7;
      v73 = 0;
      LOWORD(lpSubKey[0]) = 0;
      if ( hKey )
        RegCloseKey(hKey);
      (**(void (__fastcall ***)(__int64, __int64))v3)(v3, 1);
      return (unsigned int)v65;
    }
    if ( v11 < 8 )
      v13 = lpSubKey;
    else
      v13 = (LPCWSTR *)lpSubKey[0];
    v73 = 0;
    *(_WORD *)v13 = 0;
    memset_0(Name, 0, sizeof(Name));
    cchName = 520;
    if ( RegEnumKeyExW(hKey, dwIndex, Name, &cchName, 0, 0, 0, 0) )
    {
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          45,
          WPP_945edad5fd7435d1f807bc12083ac763_Traceguids,
          DatastoreRegKey);
      }
      goto LABEL_190;
    }
    if ( *DatastoreRegKey )
    {
      v14 = -1;
      do
        ++v14;
      while ( DatastoreRegKey[v14] );
    }
    else
    {
      v14 = 0;
    }
    v15 = lpSubKey[0];
    v16 = v74;
    v17 = v74 < 8 ? lpSubKey : (LPCWSTR *)lpSubKey[0];
    if ( DatastoreRegKey < (const WCHAR *)v17
      || (v74 < 8 ? (v18 = lpSubKey) : (v18 = (LPCWSTR *)lpSubKey[0]), (char *)v18 + 2 * v73 <= (char *)DatastoreRegKey) )
    {
      if ( v14 > 0x7FFFFFFFFFFFFFFELL )
        goto LABEL_199;
      if ( v74 >= v14 )
      {
        if ( !v14 )
        {
          v21 = lpSubKey;
          if ( v74 >= 8 )
            v21 = (LPCWSTR *)lpSubKey[0];
          v73 = 0;
          *(_WORD *)v21 = 0;
          goto LABEL_65;
        }
      }
      else
      {
        std::wstring::_Copy(lpSubKey, v14, v73);
        v16 = v74;
        v19 = v73;
        v15 = lpSubKey[0];
        if ( !v14 )
          goto LABEL_66;
      }
      if ( v16 < 8 )
        v15 = (const WCHAR *)lpSubKey;
      std::char_traits<unsigned short>::copy(v15, DatastoreRegKey, v14);
      v20 = v74 < 8 ? lpSubKey : (LPCWSTR *)lpSubKey[0];
      v73 = v14;
      *((_WORD *)v20 + v14) = 0;
    }
    else
    {
      if ( v74 < 8 )
        v15 = (const WCHAR *)lpSubKey;
      std::wstring::assign(lpSubKey, lpSubKey, DatastoreRegKey - v15, v14);
    }
LABEL_65:
    v16 = v74;
    v19 = v73;
    v15 = lpSubKey[0];
LABEL_66:
    v22 = asc_1800465F0[0] != 0;
    v23 = v16 < 8 ? lpSubKey : (LPCWSTR *)v15;
    if ( L"\\" < (const unsigned __int16 *)v23
      || (v16 < 8 ? (v24 = lpSubKey) : (v24 = (LPCWSTR *)v15), (char *)v24 + 2 * v19 <= (char *)L"\\") )
    {
      if ( -1LL - v19 <= v22 )
        goto LABEL_199;
      if ( asc_1800465F0[0] )
      {
        v32 = v19 + v22;
        if ( (unsigned __int8)std::wstring::_Grow(lpSubKey, v19 + v22) )
        {
          v33 = lpSubKey;
          if ( v74 >= 8 )
            v33 = (LPCWSTR *)lpSubKey[0];
          std::char_traits<unsigned short>::copy((char *)v33 + 2 * v73, L"\\", v22);
          v34 = lpSubKey;
          if ( v74 >= 8 )
            v34 = (LPCWSTR *)lpSubKey[0];
          v73 = v32;
          *((_WORD *)v34 + v32) = 0;
        }
        goto LABEL_98;
      }
    }
    else
    {
      if ( v16 < 8 )
        v25 = lpSubKey;
      else
        v25 = (LPCWSTR *)v15;
      v26 = ((char *)L"\\" - (char *)v25) >> 1;
      if ( v19 < v26 )
LABEL_191:
        std::_Xout_of_range("invalid string position");
      v27 = v19 - v26;
      if ( v19 - v26 >= v22 )
        v27 = asc_1800465F0[0] != 0;
      if ( ~v19 <= v27 )
LABEL_199:
        std::_Xlength_error("string too long");
      if ( v27 )
      {
        v28 = v27 + v19;
        if ( (unsigned __int8)std::wstring::_Grow(lpSubKey, v27 + v19) )
        {
          v29 = lpSubKey;
          if ( v74 >= 8 )
            v29 = (LPCWSTR *)lpSubKey[0];
          v30 = lpSubKey;
          if ( v74 >= 8 )
            v30 = (LPCWSTR *)lpSubKey[0];
          std::char_traits<unsigned short>::copy((char *)v30 + 2 * v73, (char *)v29 + 2 * v26, v27);
          v31 = lpSubKey;
          if ( v74 >= 8 )
            v31 = (LPCWSTR *)lpSubKey[0];
          v73 = v28;
          *((_WORD *)v31 + v28) = 0;
        }
LABEL_98:
        v16 = v74;
        v19 = v73;
        v15 = lpSubKey[0];
      }
    }
    if ( Name[0] )
    {
      v35 = -1;
      do
        ++v35;
      while ( Name[v35] );
    }
    else
    {
      v35 = 0;
    }
    v36 = v16 < 8 ? lpSubKey : (LPCWSTR *)v15;
    if ( Name < (WCHAR *)v36
      || (v16 < 8 ? (v37 = lpSubKey) : (v37 = (LPCWSTR *)v15), (char *)v37 + 2 * v19 <= (char *)Name) )
    {
      if ( -1LL - v19 <= v35 )
        goto LABEL_199;
      if ( v35 )
      {
        v45 = v19 + v35;
        if ( (unsigned __int8)std::wstring::_Grow(lpSubKey, v19 + v35) )
        {
          v46 = lpSubKey;
          if ( v74 >= 8 )
            v46 = (LPCWSTR *)lpSubKey[0];
          std::char_traits<unsigned short>::copy((char *)v46 + 2 * v73, Name, v35);
          v47 = lpSubKey;
          if ( v74 >= 8 )
            v47 = (LPCWSTR *)lpSubKey[0];
          v73 = v45;
          *((_WORD *)v47 + v45) = 0;
        }
        goto LABEL_135;
      }
    }
    else
    {
      if ( v16 < 8 )
        v38 = lpSubKey;
      else
        v38 = (LPCWSTR *)v15;
      v39 = ((char *)Name - (char *)v38) >> 1;
      if ( v19 < v39 )
        goto LABEL_191;
      v40 = v19 - v39;
      if ( v19 - v39 >= v35 )
        v40 = v35;
      if ( ~v19 <= v40 )
        goto LABEL_199;
      if ( v40 )
      {
        v41 = v40 + v19;
        if ( (unsigned __int8)std::wstring::_Grow(lpSubKey, v40 + v19) )
        {
          v42 = lpSubKey;
          if ( v74 >= 8 )
            v42 = (LPCWSTR *)lpSubKey[0];
          v43 = lpSubKey;
          if ( v74 >= 8 )
            v43 = (LPCWSTR *)lpSubKey[0];
          std::char_traits<unsigned short>::copy((char *)v43 + 2 * v73, (char *)v42 + 2 * v39, v40);
          v44 = lpSubKey;
          if ( v74 >= 8 )
            v44 = (LPCWSTR *)lpSubKey[0];
          v73 = v41;
          *((_WORD *)v44 + v41) = 0;
        }
LABEL_135:
        v16 = v74;
        v15 = lpSubKey[0];
      }
    }
    memset_0(pvData, 0, sizeof(pvData));
    pcbData = 1040;
    if ( v16 < 8 )
      v15 = (const WCHAR *)lpSubKey;
    ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v15, L"REPORTINGEXE", 2u, 0, pvData, &pcbData);
    if ( !ValueW )
    {
      if ( pvData[0] )
        break;
    }
    v51 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v49 = 46;
LABEL_188:
      v50 = Name;
LABEL_189:
      WPP_SF_Sd(
        *((_QWORD *)v51 + 2),
        v49,
        (unsigned int)WPP_945edad5fd7435d1f807bc12083ac763_Traceguids,
        (_DWORD)v50,
        ValueW);
    }
LABEL_190:
    v12 = dwIndex + 1;
    v11 = v74;
  }
  memset_0(Dst, 0, sizeof(Dst));
  if ( ExpandEnvironmentStringsW(pvData, Dst, 0x208u) )
  {
    if ( GetFileAttributesW(Dst) == -1 )
    {
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LOBYTE(ValueW) = GetLastError();
        v49 = 48;
        v50 = Dst;
        v51 = WPP_GLOBAL_Control;
        goto LABEL_189;
      }
    }
    else
    {
      memset_0(v79, 0, sizeof(v79));
      pcbData = 1040;
      if ( v74 < 8 )
        v52 = (const WCHAR *)lpSubKey;
      else
        v52 = lpSubKey[0];
      ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v52, L"GUID", 2u, 0, v79, &pcbData);
      if ( ValueW || !v79[0] )
      {
        v51 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v49 = 49;
          goto LABEL_188;
        }
      }
      else
      {
        memset_0(v78, 0, sizeof(v78));
        pcbData = 1040;
        if ( v74 < 8 )
          v53 = (const WCHAR *)lpSubKey;
        else
          v53 = lpSubKey[0];
        ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v53, L"DISPLAYNAME", 2u, 0, v78, &pcbData);
        if ( ValueW || !v78[0] )
        {
          v51 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v49 = 50;
            goto LABEL_188;
          }
        }
        else
        {
          v61 = 0;
          pcbData = 4;
          if ( v74 < 8 )
            v54 = (const WCHAR *)lpSubKey;
          else
            v54 = lpSubKey[0];
          ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v54, L"STATE", 0x18u, 0, &v61, &pcbData);
          if ( ValueW )
          {
            v51 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v49 = 51;
              goto LABEL_188;
            }
          }
          else
          {
            memset_0(v77, 0, sizeof(v77));
            pcbData = 1040;
            if ( v74 < 8 )
              v55 = (const WCHAR *)lpSubKey;
            else
              v55 = lpSubKey[0];
            ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v55, L"PRODUCTEXE", 2u, 0, v77, &pcbData);
            if ( ValueW || !v77[0] )
            {
              v51 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v49 = 52;
                goto LABEL_188;
              }
            }
            else
            {
              v69 = 0;
              v56 = v71;
              v65 = CThirdPartyManager::CreateExternalBaseFromRegistry(v71, &v69, v79, v78, v61, pvData, v77, v70);
              if ( v65 < 0 )
              {
                if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    54,
                    (unsigned int)WPP_945edad5fd7435d1f807bc12083ac763_Traceguids,
                    (unsigned int)Name,
                    0);
                }
              }
              else
              {
                if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                {
                  WPP_SF_S(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    53,
                    WPP_945edad5fd7435d1f807bc12083ac763_Traceguids,
                    Name);
                }
                v57 = v69;
                CThirdPartyManager::UpdateExternalProduct(v56, v69);
                WscTelemetryEventWriteProductLoad(v57, 1);
                if ( v57 )
                  (**(void (__fastcall ***)(struct CExternalBase *, __int64))v57)(v57, 1);
              }
            }
          }
        }
      }
    }
    goto LABEL_190;
  }
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids, pvData);
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError > 0 )
    v8 = (unsigned __int16)LastError | 0x80070000;
  LOBYTE(v59) = 1;
  std::wstring::_Tidy(lpSubKey, v59, 0);
  v9 = hKey;
  if ( !hKey )
    goto LABEL_19;
LABEL_18:
  RegCloseKey(v9);
LABEL_19:
  CommonUtil::CAutoUniquePtr<CExternalBase,void>::~CAutoUniquePtr<CExternalBase,void>(&v66);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180016d50  mov     [rsp-8+arg_10], rbx
0x180016d55  push    rbp
0x180016d56  push    rsi
0x180016d57  push    rdi
0x180016d58  push    r12
0x180016d5a  push    r13
0x180016d5c  push    r14
0x180016d5e  push    r15
0x180016d60  lea     rbp, [rsp-1840h]
0x180016d68  mov     eax, 1940h
0x180016d6d  call    _alloca_probe
0x180016d72  sub     rsp, rax
0x180016d75  mov     rax, cs:__security_cookie
0x180016d7c  xor     rax, rsp
0x180016d7f  mov     [rbp+1870h+var_40], rax
0x180016d86  mov     [rbp+1870h+var_18D0], rdx
0x180016d8a  mov     rdi, rcx
0x180016d8d  mov     [rbp+1870h+var_18C8], rcx
0x180016d91  lea     r12, WPP_GLOBAL_Control
0x180016d98  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d9f  cmp     rcx, r12
0x180016da2  jz      short loc_180016DBF
0x180016da4  test    byte ptr [rcx+1Ch], 4
0x180016da8  jz      short loc_180016DBF
0x180016daa  mov     edx, 28h ; '('
0x180016daf  lea     r8, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids
0x180016db6  mov     rcx, [rcx+10h]
0x180016dba  call    WPP_SF_
0x180016dbf  xor     r15d, r15d
0x180016dc2  mov     [rbp+1870h+var_18E0], r15
0x180016dc6  mov     rax, [rdi]
0x180016dc9  lea     rdx, [rbp+1870h+var_18E0]
0x180016dcd  mov     rcx, rdi
0x180016dd0  mov     rax, [rax+28h]
0x180016dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016dd9  mov     [rsp+1970h+var_18F4], eax
0x180016ddd  mov     r13, [rbp+1870h+var_18E0]
0x180016de1  mov     [rbp+1870h+var_18F0], r13
0x180016de5  mov     [rbp+1870h+var_18E0], r15
0x180016de9  test    eax, eax
0x180016deb  js      loc_1800179D1
0x180016df1  test    r13, r13
0x180016df4  jz      loc_1800179D1
0x180016dfa  mov     rcx, [r13+0]
0x180016dfe  mov     rax, [rcx+18h]
0x180016e02  mov     rcx, r13
0x180016e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e0a  mov     ecx, eax; enum _SECURITY_PRODUCT_TYPE
0x180016e0c  call    ?WscGetDatastoreRegKey@@YAPEBGW4_SECURITY_PRODUCT_TYPE@@@Z; WscGetDatastoreRegKey(_SECURITY_PRODUCT_TYPE)
0x180016e11  mov     r14, rax
0x180016e14  test    rax, rax
0x180016e17  jnz     short loc_180016E54
0x180016e19  mov     rcx, cs:WPP_GLOBAL_Control
0x180016e20  cmp     rcx, r12
0x180016e23  jz      short loc_180016E41
0x180016e25  test    byte ptr [rcx+1Ch], 1
0x180016e29  jz      short loc_180016E41
0x180016e2b  mov     edx, 2Ah ; '*'
0x180016e30  lea     r8, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids
0x180016e37  mov     rcx, [rcx+10h]
0x180016e3b  call    WPP_SF_
0x180016e40  nop
0x180016e41  lea     rcx, [rbp+1870h+var_18F0]
0x180016e45  call    ??1?$CAutoUniquePtr@VCExternalBase@@X@CommonUtil@@QEAA@XZ; CommonUtil::CAutoUniquePtr<CExternalBase,void>::~CAutoUniquePtr<CExternalBase,void>(void)
0x180016e4a  mov     eax, 80070057h
0x180016e4f  jmp     loc_180017A17
0x180016e54  mov     [rsp+1970h+hKey], r15
0x180016e59  lea     rcx, [rsp+1970h+hKey]
0x180016e5e  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180016e63  mov     [rsp+1970h+phkResult], rax; phkResult
0x180016e68  mov     r9d, 30019h; samDesired
0x180016e6e  xor     r8d, r8d; ulOptions
0x180016e71  mov     rdx, r14; lpSubKey
0x180016e74  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016e7b  call    cs:__imp_RegOpenKeyExW
0x180016e81  mov     ebx, eax
0x180016e83  test    eax, eax
0x180016e85  jz      short loc_180016EDF
0x180016e87  mov     rcx, cs:WPP_GLOBAL_Control
0x180016e8e  cmp     rcx, r12
0x180016e91  jz      short loc_180016EB1
0x180016e93  test    byte ptr [rcx+1Ch], 1
0x180016e97  jz      short loc_180016EB1
0x180016e99  mov     edx, 2Bh ; '+'
0x180016e9e  mov     r9, r14
0x180016ea1  lea     r8, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids
0x180016ea8  mov     rcx, [rcx+10h]
0x180016eac  call    WPP_SF_S
0x180016eb1  test    ebx, ebx
0x180016eb3  jle     short loc_180016EBE
0x180016eb5  movzx   ebx, bx
0x180016eb8  or      ebx, 80070000h
0x180016ebe  mov     rcx, [rsp+1970h+hKey]; hKey
0x180016ec3  test    rcx, rcx
0x180016ec6  jz      short loc_180016ECF
0x180016ec8  call    cs:__imp_RegCloseKey
0x180016ece  nop
0x180016ecf  lea     rcx, [rbp+1870h+var_18F0]
0x180016ed3  call    ??1?$CAutoUniquePtr@VCExternalBase@@X@CommonUtil@@QEAA@XZ; CommonUtil::CAutoUniquePtr<CExternalBase,void>::~CAutoUniquePtr<CExternalBase,void>(void)
0x180016ed8  mov     eax, ebx
0x180016eda  jmp     loc_180017A17
0x180016edf  mov     [rsp+1970h+cSubKeys], r15d
0x180016ee4  mov     [rsp+1970h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180016ee9  mov     [rsp+1970h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180016eee  mov     [rsp+1970h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180016ef3  mov     [rsp+1970h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180016ef8  mov     [rsp+1970h+lpcValues], r15; lpcValues
0x180016efd  mov     [rsp+1970h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180016f02  mov     [rsp+1970h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180016f07  lea     rax, [rsp+1970h+cSubKeys]
0x180016f0c  mov     [rsp+1970h+phkResult], rax; lpcSubKeys
0x180016f11  xor     r9d, r9d; lpReserved
0x180016f14  xor     r8d, r8d; lpcchClass
0x180016f17  xor     edx, edx; lpClass
0x180016f19  mov     rcx, [rsp+1970h+hKey]; hKey
0x180016f1e  call    cs:__imp_RegQueryInfoKeyW
0x180016f24  mov     ebx, eax
0x180016f26  test    eax, eax
0x180016f28  jz      short loc_180016F74
0x180016f2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180016f31  cmp     rcx, r12
0x180016f34  jz      short loc_180016F54
0x180016f36  test    byte ptr [rcx+1Ch], 1
0x180016f3a  jz      short loc_180016F54
0x180016f3c  mov     edx, 2Ch ; ','
0x180016f41  mov     r9d, eax
0x180016f44  lea     r8, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids
0x180016f4b  mov     rcx, [rcx+10h]
0x180016f4f  call    WPP_SF_d
0x180016f54  test    ebx, ebx
0x180016f56  jle     short loc_180016F61
0x180016f58  movzx   ebx, bx
0x180016f5b  or      ebx, 80070000h
0x180016f61  mov     rcx, [rsp+1970h+hKey]
0x180016f66  test    rcx, rcx
0x180016f69  jz      loc_180016ECF
0x180016f6f  jmp     loc_180016EC8
0x180016f74  mov     ebx, 7
0x180016f79  mov     [rbp+1870h+var_18A8], rbx
0x180016f7d  mov     [rbp+1870h+var_18B0], r15
0x180016f81  mov     word ptr [rbp+1870h+lpSubKey], r15w
0x180016f86  xor     edx, edx; Val
0x180016f88  mov     r8d, 410h; Size
0x180016f8e  lea     rcx, [rbp+1870h+var_860]; void *
0x180016f95  call    memset_0
0x180016f9a  xor     edx, edx; Val
0x180016f9c  mov     r8d, 410h; Size
0x180016fa2  lea     rcx, [rbp+1870h+var_C70]; void *
0x180016fa9  call    memset_0
0x180016fae  mov     [rsp+1970h+var_190C], r15d
0x180016fb3  xor     edx, edx; Val
0x180016fb5  mov     r8d, 410h; Size
0x180016fbb  lea     rcx, [rbp+1870h+pvData]; void *
0x180016fc2  call    memset_0
0x180016fc7  xor     edx, edx; Val
0x180016fc9  mov     r8d, 410h; Size
0x180016fcf  lea     rcx, [rbp+1870h+var_1080]; void *
0x180016fd6  call    memset_0
0x180016fdb  mov     eax, r15d
0x180016fde  mov     rsi, 7FFFFFFFFFFFFFFEh
0x180016fe8  lea     rdi, asc_1800465F0; "\\"
0x180016fef  mov     [rsp+1970h+dwIndex], eax
0x180016ff3  cmp     eax, [rsp+1970h+cSubKeys]
0x180016ff7  jnb     loc_180017981
0x180016ffd  cmp     rbx, 8
0x180017001  jb      short loc_180017009
0x180017003  mov     rcx, [rbp+1870h+lpSubKey]
0x180017007  jmp     short loc_18001700D
0x180017009  lea     rcx, [rbp+1870h+lpSubKey]
0x18001700d  mov     [rbp+1870h+var_18B0], r15
0x180017011  mov     [rcx], r15w
0x180017015  xor     edx, edx; Val
0x180017017  mov     r8d, 410h; Size
0x18001701d  lea     rcx, [rbp+1870h+Name]; void *
0x180017021  call    memset_0
0x180017026  mov     [rbp+1870h+cchName], 208h
0x18001702d  mov     [rsp+1970h+lpcValues], r15; lpftLastWriteTime
0x180017032  mov     [rsp+1970h+lpcbMaxClassLen], r15; lpcchClass
0x180017037  mov     [rsp+1970h+lpcbMaxSubKeyLen], r15; lpClass
0x18001703c  mov     [rsp+1970h+phkResult], r15; lpReserved
0x180017041  lea     r9, [rbp+1870h+cchName]; lpcchName
0x180017045  lea     r8, [rbp+1870h+Name]; lpName
0x180017049  mov     edx, [rsp+1970h+dwIndex]; dwIndex
0x18001704d  mov     rcx, [rsp+1970h+hKey]; hKey
0x180017052  call    cs:__imp_RegEnumKeyExW
0x180017058  test    eax, eax
0x18001705a  jz      short loc_180017093
0x18001705c  mov     rcx, cs:WPP_GLOBAL_Control
0x180017063  cmp     rcx, r12
0x180017066  jz      loc_1800178EC
0x18001706c  test    byte ptr [rcx+1Ch], 1
0x180017070  jz      loc_1800178EC
0x180017076  mov     edx, 2Dh ; '-'
0x18001707b  mov     r9, r14
0x18001707e  lea     r8, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids
0x180017085  mov     rcx, [rcx+10h]
0x180017089  call    WPP_SF_S
0x18001708e  jmp     loc_1800178EC
0x180017093  cmp     word ptr [r14], 0
0x180017098  jnz     short loc_18001709F
0x18001709a  mov     rbx, r15
0x18001709d  jmp     short loc_1800170BB
0x18001709f  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800170a6  nop     word ptr [rax+rax+00000000h]
0x1800170b0  inc     rbx
0x1800170b3  cmp     word ptr [r14+rbx*2], 0
0x1800170b9  jnz     short loc_1800170B0
0x1800170bb  mov     r12, [rbp+1870h+lpSubKey]
0x1800170bf  mov     r15, [rbp+1870h+var_18A8]
0x1800170c3  cmp     r15, 8
0x1800170c7  jb      short loc_1800170CE
0x1800170c9  mov     rax, r12
0x1800170cc  jmp     short loc_1800170D2
0x1800170ce  lea     rax, [rbp+1870h+lpSubKey]
0x1800170d2  mov     rcx, [rbp+1870h+var_18B0]
0x1800170d6  cmp     r14, rax
0x1800170d9  jb      short loc_180017118
0x1800170db  cmp     r15, 8
0x1800170df  jb      short loc_1800170E6
0x1800170e1  mov     rax, r12
0x1800170e4  jmp     short loc_1800170EA
0x1800170e6  lea     rax, [rbp+1870h+lpSubKey]
0x1800170ea  lea     rax, [rax+rcx*2]
0x1800170ee  cmp     rax, r14
0x1800170f1  jbe     short loc_180017118
0x1800170f3  cmp     r15, 8
0x1800170f7  jnb     short loc_1800170FD
0x1800170f9  lea     r12, [rbp+1870h+lpSubKey]
0x1800170fd  mov     r8, r14
0x180017100  sub     r8, r12
0x180017103  sar     r8, 1
0x180017106  mov     r9, rbx
0x180017109  lea     rdx, [rbp+1870h+lpSubKey]
0x18001710d  lea     rcx, [rbp+1870h+lpSubKey]
0x180017111  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180017116  jmp     short loc_180017195
0x180017118  cmp     rbx, rsi
0x18001711b  ja      loc_180017974
0x180017121  cmp     r15, rbx
0x180017124  jnb     short loc_18001716B
0x180017126  mov     r8, rcx
0x180017129  mov     rdx, rbx
0x18001712c  lea     rcx, [rbp+1870h+lpSubKey]
0x180017130  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x180017135  mov     r15, [rbp+1870h+var_18A8]
0x180017139  mov     rcx, [rbp+1870h+var_18B0]
0x18001713d  mov     r12, [rbp+1870h+lpSubKey]
0x180017141  test    rbx, rbx
0x180017144  jz      short loc_1800171A1
0x180017146  cmp     r15, 8
0x18001714a  jnb     short loc_180017150
0x18001714c  lea     r12, [rbp+1870h+lpSubKey]
0x180017150  mov     r8, rbx
0x180017153  mov     rdx, r14
0x180017156  mov     rcx, r12
0x180017159  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x18001715e  cmp     [rbp+1870h+var_18A8], 8
0x180017163  jb      short loc_180017187
0x180017165  mov     rcx, [rbp+1870h+lpSubKey]
0x180017169  jmp     short loc_18001718B
0x18001716b  test    rbx, rbx
0x18001716e  jnz     short loc_180017146
0x180017170  lea     rcx, [rbp+1870h+lpSubKey]
0x180017174  cmp     r15, 8
0x180017178  cmovnb  rcx, r12
0x18001717c  mov     [rbp+1870h+var_18B0], rbx
0x180017180  xor     eax, eax
0x180017182  mov     [rcx], ax
0x180017185  jmp     short loc_180017195
0x180017187  lea     rcx, [rbp+1870h+lpSubKey]
0x18001718b  mov     [rbp+1870h+var_18B0], rbx
0x18001718f  xor     eax, eax
0x180017191  mov     [rcx+rbx*2], ax
0x180017195  mov     r15, [rbp+1870h+var_18A8]
0x180017199  mov     rcx, [rbp+1870h+var_18B0]
0x18001719d  mov     r12, [rbp+1870h+lpSubKey]
0x1800171a1  cmp     word ptr cs:asc_1800465F0, 0; "\\"
0x1800171a9  jnz     short loc_1800171AF
0x1800171ab  xor     esi, esi
0x1800171ad  jmp     short loc_1800171B4
0x1800171af  mov     esi, 1
0x1800171b4  cmp     r15, 8
0x1800171b8  jb      short loc_1800171BF
0x1800171ba  mov     rax, r12
0x1800171bd  jmp     short loc_1800171C3
0x1800171bf  lea     rax, [rbp+1870h+lpSubKey]
0x1800171c3  cmp     rdi, rax
0x1800171c6  jb      loc_180017288
0x1800171cc  cmp     r15, 8
0x1800171d0  jb      short loc_1800171D7
0x1800171d2  mov     rax, r12
0x1800171d5  jmp     short loc_1800171DB
0x1800171d7  lea     rax, [rbp+1870h+lpSubKey]
0x1800171db  lea     rax, [rax+rcx*2]
0x1800171df  cmp     rax, rdi
0x1800171e2  jbe     loc_180017288
0x1800171e8  cmp     r15, 8
0x1800171ec  jb      short loc_1800171F3
0x1800171ee  mov     rax, r12
0x1800171f1  jmp     short loc_1800171F7
  ... truncated ...
```
