# CFSFolder::GetNormalDisplayName(_ITEMID_CHILD const *,ulong,FSIS_UINAME_OPTIONS,ushort * *)

- ea: `0x180047190`
- end: `0x180047d1d`
- name: `?GetNormalDisplayName@CFSFolder@@IEAAJPEFBU_ITEMID_CHILD@@KW4FSIS_UINAME_OPTIONS@@PEAPEAG@Z`
- size: `2957`
- prototype: ``
- caller_count: `5`
- callee_count: `22`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800407f0`
- `0x1800429f0`
- `0x180045c80`
- `0x18022d9e0`
- `0x180252a90`

## callees

- `0x180009fc0`
- `0x1800304e0`
- `0x180038f50`
- `0x180038f80`
- `0x1800441c0`
- `0x180047190`
- `0x180048ad0`
- `0x18004a270`
- `0x18004a6f0`
- `0x180063050`
- `0x18008ecb0`
- `0x180096e60`
- `0x1800974c0`
- `0x1800fd500`
- `0x180107000`
- `0x180135090`
- `0x180180ba0`
- `0x18034591c`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x1803b69c5`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180047717`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180047717`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800476f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800476f8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180047ae5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180047b3a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180047c4c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180047ae5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180047b3a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180047c4c`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeW` at `0x180047ce7`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeW` at `0x180047ce7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x18004796a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x18004796a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180047bd3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180047bd3`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180047827`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180047827`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047439`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047439`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047557`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004756d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047583`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004759a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047645`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004765b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047671`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047688`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047709`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047c72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047557`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004756d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047583`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004759a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047645`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004765b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047671`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047688`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047709`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047c72`
- `SHCORE!__imp_StrRetToStrW` at `0x180047b66`
- `SHCORE!__imp_StrRetToStrW` at `0x180047b66`
- `SHCORE!__imp_ualstrcpynW` at `0x18004779c`
- `SHCORE!__imp_ualstrcpynW` at `0x18004795a`
- `SHCORE!__imp_ualstrcpynW` at `0x180047bc0`
- `SHCORE!__imp_ualstrcpynW` at `0x18004779c`
- `SHCORE!__imp_ualstrcpynW` at `0x18004795a`
- `SHCORE!__imp_ualstrcpynW` at `0x180047bc0`
- `SHCORE!__imp_ualstrlenW` at `0x1800477ef`
- `SHCORE!__imp_ualstrlenW` at `0x1800477ef`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x180047cb4`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x180047cb4`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CFSFolder::GetNormalDisplayName(
        struct CFSFolder *a1,
        unsigned __int16 *a2,
        unsigned __int64 *a3,
        unsigned int a4,
        PWSTR *a5)
{
  unsigned int v6; // r14d
  unsigned __int16 *v9; // rdi
  const struct IDFOLDER *v10; // rsi
  char IsEnabled; // al
  unsigned __int64 v12; // r9
  unsigned __int64 *v13; // rdx
  __int64 v14; // r10
  unsigned int v15; // ecx
  unsigned __int64 v16; // rcx
  _BYTE *v17; // rcx
  unsigned __int64 v18; // rdx
  int v19; // r8d
  __int64 v20; // rdx
  __int64 v21; // rcx
  unsigned __int64 v22; // rbx
  __int64 v23; // rsi
  const CHAR *v24; // r8
  __int64 v25; // rax
  __int64 v26; // rax
  struct IDFOLDER *v27; // r9
  WCHAR *v28; // rcx
  WCHAR *v29; // rdx
  WCHAR *v30; // rdi
  unsigned __int64 v31; // r14
  WCHAR *v32; // rax
  WCHAR *v33; // r10
  int v34; // esi
  unsigned __int64 v35; // rdx
  WCHAR *v36; // r8
  __int64 v37; // rcx
  WCHAR v38; // ax
  __int64 v39; // r9
  WCHAR *v40; // rcx
  PWSTR v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  unsigned __int16 *v50; // r9
  int ShouldShowExtension; // eax
  const CHAR *v52; // rdi
  unsigned __int64 v53; // r8
  __int64 v54; // rdi
  __int64 v55; // rcx
  WCHAR *v56; // rdx
  __int64 v57; // r9
  unsigned __int16 *v58; // r8
  WCHAR v59; // ax
  unsigned __int16 *v60; // rcx
  struct IDFOLDER *v61; // r8
  unsigned __int16 *v62; // rcx
  WCHAR *v63; // rdx
  unsigned __int16 v64; // ax
  WCHAR *v65; // rcx
  __int64 v66; // r14
  bool v67; // cf
  const CHAR *v68; // rdx
  void **v69; // rax
  HRESULT v70; // ebx
  int v71; // eax
  __int64 v72; // rbx
  __int64 v73; // rax
  __int64 v74; // rdx
  __int64 v75; // rcx
  __int64 v76; // rcx
  __int16 v77; // r11
  LPWSTR *v78; // rax
  __int64 v79; // rdx
  const CHAR *v80; // rdx
  const unsigned __int16 *ExtensionW; // rax
  HRESULT v82; // eax
  int lpWideCharStr; // [rsp+20h] [rbp-E0h]
  PWSTR pszUrl; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v85; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v86; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v87[2]; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v88; // [rsp+60h] [rbp-A0h]
  LPVOID v89; // [rsp+68h] [rbp-98h]
  LPVOID pv; // [rsp+80h] [rbp-80h]
  __int64 v91; // [rsp+88h] [rbp-78h]
  __int64 v92; // [rsp+90h] [rbp-70h]
  __int64 v93; // [rsp+98h] [rbp-68h]
  struct IDFOLDER *v94; // [rsp+A0h] [rbp-60h]
  const CHAR *v95; // [rsp+A8h] [rbp-58h]
  WCHAR *v96; // [rsp+B8h] [rbp-48h]
  WCHAR *v97; // [rsp+C0h] [rbp-40h]
  int v98; // [rsp+D0h] [rbp-30h]
  WCHAR pszOutBuf[278]; // [rsp+D4h] [rbp-2Ch] BYREF
  STRRET pszSource; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int16 v101[264]; // [rsp+510h] [rbp+410h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+778h] [rbp+678h]

  v6 = (unsigned int)a3;
  *a5 = 0;
  v9 = 0;
  if ( a2 )
  {
    v49 = *a2;
    if ( (unsigned int)v49 > 0xB )
    {
      if ( (a2[1] & 0x70) == 0x30 )
      {
        v9 = a2;
        v10 = 0;
        goto LABEL_3;
      }
      if ( *(_DWORD *)(a2 + 3) == 1179862595 )
      {
        if ( a2[2] > (unsigned __int64)(v49 - 4)
          || (v9 = a2 + 5, !IDListContainerIsConsistent((LPCITEMIDLIST)(a2 + 5), a2[2]))
          || v77 != *v9 + 6
          || (unsigned __int16)(*v9 + 6) < *v9 )
        {
          v10 = 0;
          goto LABEL_23;
        }
      }
    }
  }
  v10 = 0;
  if ( !v9 )
    goto LABEL_23;
LABEL_3:
  if ( *v9 < 0xEu )
    goto LABEL_23;
  if ( a2 )
  {
    if ( *a2 )
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl'::`2'::impl);
      v12 = *a2;
      if ( !IsEnabled || (unsigned int)v12 >= 2 )
      {
        v13 = 0;
        v14 = *(unsigned __int16 *)((char *)a2 + v12 - 2);
        if ( (_WORD)v14 )
        {
          if ( v14 + 8 < v12 )
          {
            v13 = (unsigned __int64 *)((char *)a2 + v14);
            v15 = *(unsigned __int16 *)((char *)a2 + v14);
            if ( v15 < 8 || HIWORD(*((_DWORD *)v13 + 1)) != 0xBEEF || (unsigned int)v14 + v15 > (unsigned int)v12 )
              v13 = 0;
          }
        }
        v16 = (unsigned __int64)a2 + v12;
        if ( v13 )
        {
          while ( *((_DWORD *)v13 + 1) != -1091633148 )
          {
            a3 = 0;
            if ( (unsigned __int64)(v13 + 1) <= v16 )
            {
              v50 = (unsigned __int16 *)((char *)v13 + *(unsigned __int16 *)v13);
              if ( v50 == (unsigned __int16 *)v16 )
                goto LABEL_104;
              if ( (unsigned __int64)v50 <= v16 )
              {
                if ( (unsigned __int64)(v50 + 4) > v16
                  || HIWORD(*((_DWORD *)v50 + 1)) != 0xBEEF
                  || (unsigned __int64)v50 + *v50 > v16
                  || v50 < (unsigned __int16 *)v13 + 4 )
                {
                  goto LABEL_104;
                }
                a3 = (unsigned __int64 *)((char *)v13 + *(unsigned __int16 *)v13);
              }
            }
            v13 = a3;
            if ( !a3 )
              goto LABEL_104;
          }
          goto LABEL_14;
        }
      }
    }
  }
LABEL_104:
  if ( (v9[1] & 0x34) != 0x34 )
  {
LABEL_14:
    v17 = v9 + 7;
    if ( v9 == (unsigned __int16 *)-14LL || (v18 = *v9 - 14LL, v18 > 0x7FFFFFFF) )
    {
      v19 = -2147024809;
    }
    else
    {
      if ( *v9 != 14 )
      {
        do
        {
          if ( !*v17 )
            break;
          ++v17;
          --v18;
        }
        while ( v18 );
      }
      v19 = -2147024809;
      if ( v18 )
        v19 = 0;
    }
    goto LABEL_21;
  }
  v19 = UnalignedStringCbLengthW(v9 + 7, *v9 - 14LL, a3);
LABEL_21:
  if ( v19 >= 0 )
    v10 = (const struct IDFOLDER *)v9;
LABEL_23:
  pszUrl = 0;
  CFileSysItemString::CFileSysItemString((CFileSysItemString *)v87, a1, (const struct _ITEMIDLIST_RELATIVE *)a2, v10);
  v86 = 0;
  if ( (unsigned int)CFileSysItemString::GetJunctionClsid(v87, 3, &v86)
    && (unsigned int)CCLSIDInfoCache::GetFolderValue(v21, &v86, 1) )
  {
    v85 = 0;
    v69 = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>(&v85);
    v70 = CFSFolder::_Bind(
            a1,
            0,
            (const struct _ITEMIDLIST_RELATIVE *)a2,
            &GUID_000214e6_0000_0000_c000_000000000046,
            v69);
    if ( v70 < 0 )
    {
      v79 = 5069;
      goto LABEL_199;
    }
    memset_0(&pszSource, 0, sizeof(pszSource));
    v71 = (*(__int64 (__fastcall **)(__int64, const ITEMIDLIST *, _QWORD, STRRET *))(*(_QWORD *)v85 + 88LL))(
            v85,
            &c_idlDesktop,
            v6,
            &pszSource);
    v70 = v71;
    if ( v71 )
    {
      if ( v71 == -2147467263 )
      {
        v72 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pszUrl);
        v73 = CFileSysItemString::UIName(v87, a4);
        v70 = _AllocString<CTCoAllocPolicy>(v75, v74, v73, v72);
        if ( v70 >= 0 )
          goto LABEL_153;
        v79 = 5079;
LABEL_199:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v79,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
          (const char *)(unsigned int)v70,
          lpWideCharStr);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
        goto LABEL_187;
      }
      if ( v71 < 0 )
      {
        v79 = 5083;
        goto LABEL_199;
      }
    }
    else
    {
      v78 = (LPWSTR *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pszUrl);
      v70 = StrRetToStrW(&pszSource, &c_idlDesktop, v78);
      if ( v70 < 0 )
      {
        v79 = 5075;
        goto LABEL_199;
      }
    }
LABEL_153:
    v76 = v85;
    if ( v85 )
    {
      v85 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
    }
    goto LABEL_66;
  }
  pszUrl = 0;
  v22 = -1;
  if ( v97 )
    goto LABEL_44;
  if ( (v98 & 2) == 0 )
  {
    LOWORD(pszSource.uType) = 0;
    v23 = 260;
    v24 = v95;
    if ( !v95 )
      goto LABEL_30;
    if ( *((_WORD *)v95 + 1) >= 7u && (v25 = *((unsigned __int16 *)v95 + 18), (_WORD)v25) )
    {
      v52 = &v95[v25];
      v53 = ualstrlenW(&v95[v25], v20, v95) + 1;
      if ( v53 > 0x104 )
      {
LABEL_123:
        v24 = v95;
LABEL_30:
        if ( a4 == 2 )
        {
          if ( !(unsigned int)IsFolder(v94) )
            goto LABEL_143;
        }
        else
        {
          if ( a4 )
          {
            v27 = v94;
            goto LABEL_33;
          }
          ShouldShowExtension = CFileSysItemString::ShouldShowExtension((CFileSysItemString *)v87);
          v24 = v95;
          v27 = v94;
          if ( !ShouldShowExtension )
          {
LABEL_143:
            if ( (v98 & 1) == 0 )
            {
              if ( v24 )
              {
                v68 = &v24[*((unsigned __int16 *)v24 + 8)];
              }
              else
              {
                if ( (*((_BYTE *)v27 + 2) & 0x34) != 0x34 )
                {
                  MultiByteToWideChar(0, 0, (LPCCH)v27 + 14, -1, pszOutBuf, 260);
                  goto LABEL_147;
                }
                v68 = (char *)v27 + 14;
              }
              ualstrcpynW(pszOutBuf, v68, 260);
            }
LABEL_147:
            PathRemoveExtensionW(pszOutBuf);
            v98 = 2;
            goto LABEL_43;
          }
        }
LABEL_33:
        v28 = v96;
        if ( v96 )
        {
LABEL_41:
          if ( pszOutBuf == v28 )
            goto LABEL_40;
          v97 = v28;
LABEL_43:
          if ( v97 )
          {
LABEL_44:
            v30 = v97;
            goto LABEL_45;
          }
          goto LABEL_109;
        }
        if ( (v98 & 1) != 0 )
        {
LABEL_40:
          v98 = 3;
          goto LABEL_43;
        }
        if ( v24 )
        {
          v29 = (WCHAR *)&v24[*((unsigned __int16 *)v24 + 8)];
          if ( ((unsigned __int8)v29 & 1) == 0 )
          {
            if ( v29 != pszOutBuf )
            {
              v28 = (WCHAR *)&v24[*((unsigned __int16 *)v24 + 8)];
              v96 = v28;
              goto LABEL_39;
            }
LABEL_117:
            v98 = 1;
LABEL_39:
            if ( !v28 )
              goto LABEL_40;
            goto LABEL_41;
          }
        }
        else
        {
          if ( (*((_BYTE *)v27 + 2) & 0x34) != 0x34 )
          {
            MultiByteToWideChar(0, 0, (LPCCH)v27 + 14, -1, pszOutBuf, 260);
            goto LABEL_116;
          }
          v29 = (WCHAR *)((char *)v27 + 14);
        }
        ualstrcpynW(pszOutBuf, v29, 260);
LABEL_116:
        v28 = v96;
        goto LABEL_117;
      }
      memcpy_0(&pszSource, v52, 2 * v53);
    }
    else
    {
      v26 = *((unsigned __int16 *)v95 + 9);
      if ( !(_WORD)v26 )
        goto LABEL_30;
      SHAnsiToUnicode(&v95[v26], (PWSTR)&pszSource, 260);
    }
    if ( SHLoadIndirectString((PCWSTR)&pszSource, pszOutBuf, 0x104u, 0) < 0 )
      goto LABEL_123;
    v98 = 2;
    v54 = 2147483646;
    v55 = 2147483646;
    v56 = pszOutBuf;
    v57 = 260;
    v58 = v101;
    do
    {
      if ( !v55 )
        break;
      v59 = *v56;
      if ( !*v56 )
        break;
      ++v56;
      *v58++ = v59;
      --v55;
      --v57;
    }
    while ( v57 );
    v60 = v58 - 1;
    if ( v57 )
      v60 = v58;
    *v60 = 0;
    v61 = v94;
    if ( (((*((_BYTE *)v94 + 2) & 0x37) - 49) & 0xFB) == 0 )
    {
LABEL_131:
      v62 = v101;
      v63 = pszOutBuf;
      do
      {
        if ( !v54 )
          break;
        v64 = *v62;
        if ( !*v62 )
          break;
        ++v62;
        *v63++ = v64;
        --v54;
        --v23;
      }
      while ( v23 );
      v65 = v63 - 1;
      if ( v23 )
        v65 = v63;
      *v65 = 0;
      v98 = 2;
      goto LABEL_43;
    }
    if ( a4 != 1 )
    {
      if ( a4 || !(unsigned int)CFileSysItemString::ShouldShowExtension((CFileSysItemString *)v87) )
        goto LABEL_131;
      v61 = v94;
    }
    if ( v95 )
    {
      v80 = &v95[*((unsigned __int16 *)v95 + 8)];
    }
    else
    {
      if ( (*((_BYTE *)v61 + 2) & 0x34) != 0x34 )
      {
        MultiByteToWideChar(0, 0, (LPCCH)v61 + 14, -1, (LPWSTR)&pszSource, 260);
LABEL_179:
        ExtensionW = PathFindExtensionW((LPCWSTR)&pszSource);
        if ( ExtensionW )
          StringCchCatW(v101, 0x104u, ExtensionW);
        goto LABEL_131;
      }
      v80 = (char *)v61 + 14;
    }
    ualstrcpynW(&pszSource, v80, 260);
    goto LABEL_179;
  }
LABEL_109:
  v30 = pszOutBuf;
  do
LABEL_45:
    ++v22;
  while ( v30[v22] );
  pszUrl = 0;
  v31 = v22 + 1;
  if ( v22 + 1 < v22 || (pszUrl = 0, !is_mul_ok(v31, 2u)) )
  {
    v34 = -2147024362;
LABEL_83:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13E0,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
      (const char *)(unsigned int)v34,
      lpWideCharStr);
    v87[0] = &CFileSysItemString::`vftable';
    v46 = v93;
    v93 = 0;
    if ( v46 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    v47 = v91;
    v91 = 0;
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    v48 = v92;
    v92 = 0;
    if ( v48 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v89 )
      CoTaskMemFree(v89);
    if ( v88 )
      CoTaskMemFree(v88);
    if ( pszUrl )
      CoTaskMemFree(pszUrl);
    return (unsigned int)v34;
  }
  v32 = (WCHAR *)CoTaskMemAlloc(2 * v31);
  v33 = v32;
  pszUrl = v32;
  v34 = -2147024882;
  if ( v32 )
    v34 = 0;
  if ( v34 < 0 )
    goto LABEL_83;
  if ( !v32 && v22 != -1 || v31 > 0x7FFFFFFF )
    goto LABEL_196;
  if ( v22 < 0x7FFFFFFF )
  {
    if ( !v30 )
    {
      v30 = (WCHAR *)&WindowName;
      v22 = 0;
    }
    if ( v31 )
    {
      v35 = v31;
      v36 = v32;
      v37 = 0;
      do
      {
        if ( !v22 )
          break;
        v38 = *v30;
        if ( !*v30 )
          break;
        ++v30;
        *v36++ = v38;
        --v22;
        ++v37;
        --v35;
      }
      while ( v35 );
      v39 = v37 - 1;
      if ( v35 )
        v39 = v37;
      v40 = v36 - 1;
      if ( v35 )
        v40 = v36;
      *v40 = 0;
      if ( v35 )
      {
        v67 = v31 == v39;
        v66 = v31 - v39;
        if ( !v67 && v66 != 1 && (unsigned __int64)(2 * v66) > 2 )
          memset_0(&v33[v39 + 1], 0, 2 * v66 - 2);
      }
    }
    goto LABEL_66;
  }
  if ( v22 != -1 )
LABEL_196:
    *v32 = 0;
LABEL_66:
  if ( (*((_BYTE *)a1 + 536) & 0x20) != 0 )
  {
    v82 = UrlUnescapeW(pszUrl, 0, 0, 0x100000u);
    v70 = v82;
    if ( v82 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13E5,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
        (const char *)(unsigned int)v82,
        lpWideCharStr);
LABEL_187:
      CFileSysItemString::~CFileSysItemString((CFileSysItemString *)v87);
      if ( pszUrl )
        CoTaskMemFree(pszUrl);
      return (unsigned int)v70;
    }
  }
  v41 = pszUrl;
  pszUrl = 0;
  *a5 = v41;
  v87[0] = &CFileSysItemString::`vftable';
  v42 = v93;
  v93 = 0;
  if ( v42 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  v43 = v91;
  v91 = 0;
  if ( v43 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  v44 = v92;
  v92 = 0;
  if ( v44 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v89 )
    CoTaskMemFree(v89);
  if ( v88 )
    CoTaskMemFree(v88);
  if ( pszUrl )
    CoTaskMemFree(pszUrl);
  return 0;
}

```

## disassembly

```asm
0x180047190  push    rbp
0x180047192  push    rbx
0x180047193  push    rsi
0x180047194  push    rdi
0x180047195  push    r12
0x180047197  push    r13
0x180047199  push    r14
0x18004719b  push    r15
0x18004719d  lea     rbp, [rsp-638h]
0x1800471a5  sub     rsp, 738h
0x1800471ac  mov     rax, cs:__security_cookie
0x1800471b3  xor     rax, rsp
0x1800471b6  mov     [rbp+670h+var_50], rax
0x1800471bd  mov     r15d, r9d
0x1800471c0  mov     r14d, r8d
0x1800471c3  mov     rbx, rdx
0x1800471c6  mov     r12, rcx
0x1800471c9  mov     r13, [rbp+670h+arg_20]
0x1800471d0  mov     qword ptr [r13+0], 0
0x1800471d8  xor     edi, edi
0x1800471da  test    rdx, rdx
0x1800471dd  jnz     loc_180047728
0x1800471e3  xor     esi, esi
0x1800471e5  test    rdi, rdi
0x1800471e8  jz      loc_1800472D4
0x1800471ee  cmp     word ptr [rdi], 0Eh
0x1800471f2  jb      loc_1800472D4
0x1800471f8  test    rbx, rbx
0x1800471fb  jz      loc_1800476D2
0x180047201  cmp     word ptr [rbx], 0
0x180047205  jz      loc_1800476D2
0x18004720b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow> `wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl(void)'::`2'::impl
0x180047212  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(void)
0x180047217  movzx   r9d, word ptr [rbx]
0x18004721b  test    al, al
0x18004721d  jnz     loc_180047B91
0x180047223  xor     edx, edx
0x180047225  movzx   r10d, word ptr [rbx+r9-2]
0x18004722b  mov     r11d, 0BEEFh
0x180047231  test    r10w, r10w
0x180047235  jz      short loc_18004726D
0x180047237  lea     rax, [r10+8]
0x18004723b  cmp     rax, r9
0x18004723e  jnb     short loc_18004726D
0x180047240  lea     rdx, [rbx+r10]
0x180047244  movzx   ecx, word ptr [rdx]
0x180047247  cmp     ecx, 8
0x18004724a  jb      loc_1800478EF
0x180047250  mov     eax, [rdx+4]
0x180047253  shr     rax, 10h
0x180047257  cmp     ax, r11w
0x18004725b  jnz     loc_1800478EF
0x180047261  add     ecx, r10d
0x180047264  cmp     ecx, r9d
0x180047267  ja      loc_1800478EF
0x18004726d  lea     rcx, [rbx+r9]
0x180047271  test    rdx, rdx
0x180047274  jz      loc_1800476D2
0x18004727a  cmp     dword ptr [rdx+4], 0BEEF0004h
0x180047281  jnz     loc_180047766
0x180047287  lea     rcx, [rdi+0Eh]
0x18004728b  test    rcx, rcx
0x18004728e  jz      loc_180047B86
0x180047294  movzx   edx, word ptr [rdi]
0x180047297  add     rdx, 0FFFFFFFFFFFFFFF2h
0x18004729b  cmp     rdx, 7FFFFFFFh
0x1800472a2  ja      loc_180047B86
0x1800472a8  test    rdx, rdx
0x1800472ab  jz      short loc_1800472BE
0x1800472ad  nop     dword ptr [rax]
0x1800472b0  cmp     byte ptr [rcx], 0
0x1800472b3  jz      short loc_1800472BE
0x1800472b5  inc     rcx
0x1800472b8  sub     rdx, 1
0x1800472bc  jnz     short loc_1800472B0
0x1800472be  xor     eax, eax
0x1800472c0  mov     r8d, 80070057h
0x1800472c6  test    rdx, rdx
0x1800472c9  cmovnz  r8d, eax
0x1800472cd  test    r8d, r8d
0x1800472d0  cmovns  rsi, rdi
0x1800472d4  mov     [rsp+770h+pszUrl], 0
0x1800472dd  mov     r9, rsi; struct IDFOLDER *
0x1800472e0  mov     r8, rbx; struct _ITEMIDLIST_RELATIVE *
0x1800472e3  mov     rdx, r12; struct CFSFolder *
0x1800472e6  lea     rcx, [rsp+770h+var_720]; this
0x1800472eb  call    ??0CFileSysItemString@@QEAA@PEAVCFSFolder@@PEFBU_ITEMIDLIST_RELATIVE@@PEFBUIDFOLDER@@@Z; CFileSysItemString::CFileSysItemString(CFSFolder *,_ITEMIDLIST_RELATIVE const *,IDFOLDER const *)
0x1800472f0  nop
0x1800472f1  xorps   xmm0, xmm0
0x1800472f4  movups  [rsp+770h+var_730], xmm0
0x1800472f9  lea     r8, [rsp+770h+var_730]
0x1800472fe  mov     edx, 3
0x180047303  lea     rcx, [rsp+770h+var_720]
0x180047308  call    ?GetJunctionClsid@CFileSysItemString@@QEAAHW4FSIS_JUNCTION_FLAGS@@PEAU_GUID@@@Z; CFileSysItemString::GetJunctionClsid(FSIS_JUNCTION_FLAGS,_GUID *)
0x18004730d  test    eax, eax
0x18004730f  jnz     loc_180047991
0x180047315  mov     rdi, [rsp+770h+pszUrl]
0x18004731a  test    rdi, rdi
0x18004731d  jnz     loc_1800476F8
0x180047323  mov     [rsp+770h+pszUrl], 0
0x18004732c  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180047333  cmp     [rbp+670h+var_6B0], 0
0x180047338  jnz     loc_1800473FD
0x18004733e  test    byte ptr [rbp+670h+var_6A0], 2
0x180047342  jnz     loc_18004775D
0x180047348  xor     eax, eax
0x18004734a  mov     word ptr [rbp+670h+pszSource.uType], ax
0x180047351  mov     esi, 104h
0x180047356  mov     r8, [rbp+670h+var_6C8]
0x18004735a  test    r8, r8
0x18004735d  jz      short loc_180047383
0x18004735f  cmp     word ptr [r8+2], 7
0x180047365  jb      short loc_180047375
0x180047367  movzx   eax, word ptr [r8+24h]
0x18004736c  test    ax, ax
0x18004736f  jnz     loc_1800477E8
0x180047375  movzx   eax, word ptr [r8+12h]
0x18004737a  test    ax, ax
0x18004737d  jnz     loc_180047CA6
0x180047383  cmp     r15d, 2
0x180047387  jz      loc_180047928
0x18004738d  test    r15d, r15d
0x180047390  jz      loc_1800477B8
0x180047396  mov     r9, [rbp+670h+var_6D0]
0x18004739a  mov     rcx, [rbp+670h+var_6B8]
0x18004739e  test    rcx, rcx
0x1800473a1  jnz     short loc_1800473E5
0x1800473a3  test    byte ptr [rbp+670h+var_6A0], 1
0x1800473a7  jnz     short loc_1800473DC
0x1800473a9  test    r8, r8
0x1800473ac  jz      loc_180047ABE
0x1800473b2  movzx   edx, word ptr [r8+10h]
0x1800473b7  add     rdx, r8
0x1800473ba  test    dl, 1
0x1800473bd  jnz     loc_180047795
0x1800473c3  lea     rax, [rbp+670h+pszOutBuf]
0x1800473c7  cmp     rdx, rax
0x1800473ca  jz      loc_1800477AC
0x1800473d0  mov     rcx, rdx
0x1800473d3  mov     [rbp+670h+var_6B8], rdx
0x1800473d7  test    rcx, rcx
0x1800473da  jnz     short loc_1800473E5
0x1800473dc  mov     [rbp+670h+var_6A0], 3
0x1800473e3  jmp     short loc_1800473F2
0x1800473e5  lea     rax, [rbp+670h+pszOutBuf]
0x1800473e9  cmp     rax, rcx
0x1800473ec  jz      short loc_1800473DC
0x1800473ee  mov     [rbp+670h+var_6B0], rcx
0x1800473f2  cmp     [rbp+670h+var_6B0], 0
0x1800473f7  jz      loc_18004775D
0x1800473fd  mov     rdi, [rbp+670h+var_6B0]
0x180047401  inc     rbx
0x180047404  cmp     word ptr [rdi+rbx*2], 0
0x180047409  jnz     short loc_180047401
0x18004740b  xor     r15d, r15d
0x18004740e  mov     [rsp+770h+pszUrl], r15
0x180047413  lea     r14, [rbx+1]
0x180047417  cmp     r14, rbx
0x18004741a  jb      loc_1800475CC
0x180047420  mov     [rsp+770h+pszUrl], r15
0x180047425  mov     eax, 2
0x18004742a  mul     r14
0x18004742d  test    rdx, rdx
0x180047430  jnz     loc_1800475CC
0x180047436  mov     rcx, rax; cb
0x180047439  call    cs:__imp_CoTaskMemAlloc
0x180047440  nop     dword ptr [rax+rax+00h]
0x180047445  mov     r10, rax
0x180047448  mov     [rsp+770h+pszUrl], rax
0x18004744d  mov     esi, 8007000Eh
0x180047452  test    rax, rax
0x180047455  cmovnz  esi, r15d
0x180047459  test    esi, esi
0x18004745b  js      loc_1800475D1
0x180047461  test    rax, rax
0x180047464  jz      loc_180047B00
0x18004746a  cmp     r14, 7FFFFFFFh
0x180047471  ja      loc_180047CCE
0x180047477  cmp     rbx, 7FFFFFFFh
0x18004747e  jnb     loc_180047CC5
0x180047484  test    rdi, rdi
0x180047487  jz      loc_180047982
0x18004748d  test    r14, r14
0x180047490  jz      short loc_1800474E2
0x180047492  mov     rdx, r14
0x180047495  mov     r8, r10
0x180047498  mov     rcx, r15
0x18004749b  nop     dword ptr [rax+rax+00h]
0x1800474a0  test    rbx, rbx
0x1800474a3  jz      short loc_1800474C5
0x1800474a5  movzx   eax, word ptr [rdi]
0x1800474a8  test    ax, ax
0x1800474ab  jz      short loc_1800474C5
0x1800474ad  add     rdi, 2
0x1800474b1  mov     [r8], ax
0x1800474b5  add     r8, 2
0x1800474b9  dec     rbx
0x1800474bc  inc     rcx
0x1800474bf  sub     rdx, 1
0x1800474c3  jnz     short loc_1800474A0
0x1800474c5  lea     r9, [rcx-1]
0x1800474c9  test    rdx, rdx
0x1800474cc  cmovnz  r9, rcx
0x1800474d0  lea     rcx, [r8-2]
0x1800474d4  cmovnz  rcx, r8
0x1800474d8  mov     [rcx], r15w
0x1800474dc  jnz     loc_1800478F6
0x1800474e2  test    byte ptr [r12+218h], 20h
0x1800474eb  jnz     loc_180047CD7
0x1800474f1  mov     rax, [rsp+770h+pszUrl]
0x1800474f6  mov     [rsp+770h+pszUrl], r15
0x1800474fb  mov     [r13+0], rax
0x1800474ff  lea     rax, ??_7CFileSysItemString@@6B@; const CFileSysItemString::`vftable'
0x180047506  mov     [rsp+770h+var_720], rax
0x18004750b  mov     rcx, [rbp+670h+var_6D8]
0x18004750f  mov     [rbp+670h+var_6D8], r15
0x180047513  test    rcx, rcx
0x180047516  jz      short loc_180047524
0x180047518  mov     rax, [rcx]
0x18004751b  mov     rax, [rax+10h]
0x18004751f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047524  mov     rcx, [rbp+670h+var_6E8]
0x180047528  mov     [rbp+670h+var_6E8], r15
0x18004752c  test    rcx, rcx
0x18004752f  jnz     loc_18004774C
0x180047535  mov     rcx, [rbp+670h+var_6E0]
0x180047539  mov     [rbp+670h+var_6E0], r15
0x18004753d  test    rcx, rcx
0x180047540  jz      short loc_18004754E
0x180047542  mov     rax, [rcx]
0x180047545  mov     rax, [rax+10h]
0x180047549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004754e  mov     rcx, [rbp+670h+pv]; pv
0x180047552  test    rcx, rcx
0x180047555  jz      short loc_180047563
0x180047557  call    cs:__imp_CoTaskMemFree
0x18004755e  nop     dword ptr [rax+rax+00h]
0x180047563  mov     rcx, [rsp+770h+var_708]; pv
0x180047568  test    rcx, rcx
0x18004756b  jz      short loc_180047579
0x18004756d  call    cs:__imp_CoTaskMemFree
0x180047574  nop     dword ptr [rax+rax+00h]
0x180047579  mov     rcx, [rsp+770h+var_710]; pv
0x18004757e  test    rcx, rcx
0x180047581  jz      short loc_180047590
0x180047583  call    cs:__imp_CoTaskMemFree
0x18004758a  nop     dword ptr [rax+rax+00h]
0x18004758f  nop
0x180047590  mov     rcx, [rsp+770h+pszUrl]; pv
0x180047595  test    rcx, rcx
0x180047598  jz      short loc_1800475A6
0x18004759a  call    cs:__imp_CoTaskMemFree
0x1800475a1  nop     dword ptr [rax+rax+00h]
0x1800475a6  xor     eax, eax
0x1800475a8  mov     rcx, [rbp+670h+var_50]
0x1800475af  xor     rcx, rsp; StackCookie
0x1800475b2  call    __security_check_cookie
0x1800475b7  add     rsp, 738h
0x1800475be  pop     r15
0x1800475c0  pop     r14
0x1800475c2  pop     r13
0x1800475c4  pop     r12
0x1800475c6  pop     rdi
0x1800475c7  pop     rsi
0x1800475c8  pop     rbx
0x1800475c9  pop     rbp
0x1800475ca  retn
0x1800475cc  mov     esi, 80070216h
0x1800475d1  mov     rcx, [rbp+678h]; this
0x1800475d8  mov     r9d, esi; char *
0x1800475db  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x1800475e2  mov     edx, 13E0h; void *
0x1800475e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800475ec  nop
0x1800475ed  lea     rax, ??_7CFileSysItemString@@6B@; const CFileSysItemString::`vftable'
0x1800475f4  mov     [rsp+770h+var_720], rax
0x1800475f9  mov     rcx, [rbp+670h+var_6D8]
0x1800475fd  mov     [rbp+670h+var_6D8], r15
0x180047601  test    rcx, rcx
0x180047604  jz      short loc_180047612
0x180047606  mov     rax, [rcx]
0x180047609  mov     rax, [rax+10h]
0x18004760d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047612  mov     rcx, [rbp+670h+var_6E8]
0x180047616  mov     [rbp+670h+var_6E8], r15
0x18004761a  test    rcx, rcx
0x18004761d  jnz     loc_1800477D7
0x180047623  mov     rcx, [rbp+670h+var_6E0]
0x180047627  mov     [rbp+670h+var_6E0], r15
0x18004762b  test    rcx, rcx
0x18004762e  jz      short loc_18004763C
0x180047630  mov     rax, [rcx]
0x180047633  mov     rax, [rax+10h]
0x180047637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004763c  mov     rcx, [rbp+670h+pv]; pv
0x180047640  test    rcx, rcx
0x180047643  jz      short loc_180047651
0x180047645  call    cs:__imp_CoTaskMemFree
0x18004764c  nop     dword ptr [rax+rax+00h]
0x180047651  mov     rcx, [rsp+770h+var_708]; pv
  ... truncated ...
```
