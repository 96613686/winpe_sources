# CFSFolder::GetDisplayNameOf(_ITEMID_CHILD const *,ulong,_STRRET *)

- ea: `0x180045c80`
- end: `0x180046669`
- name: `?GetDisplayNameOf@CFSFolder@@UEAAJPEFBU_ITEMID_CHILD@@KPEAU_STRRET@@@Z`
- size: `2537`
- prototype: `int(CFSFolder *__hidden this, const struct _ITEMID_CHILD *, unsigned int, struct _STRRET *)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180009fc0`
- `0x1800304e0`
- `0x180036df0`
- `0x180038f50`
- `0x180038f80`
- `0x18003eca0`
- `0x1800441c0`
- `0x1800442d0`
- `0x180045c80`
- `0x180047190`
- `0x180063050`
- `0x1800630d0`
- `0x180092590`
- `0x180096e60`
- `0x1800c72b0`
- `0x180103290`
- `0x1801e6c80`
- `0x18034591c`
- `0x18036f610`
- `0x1803b1f60`
- `0x1803b29ea`
- `0x1803b2ac0`
- `0x1803b69c5`
- `0x18067d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180046607`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180046607`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800463ec`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800463ec`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180046264`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180046264`
- `OLEAUT32!__imp_SysAllocString` at `0x1800464e1`
- `OLEAUT32!__imp_SysAllocString` at `0x1800464e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046211`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046211`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045f74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800460c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004618c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800461a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800461b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800464d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004657c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045f74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800460c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004618c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800461a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800461b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800464d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004657c`
- `SHCORE!__imp_ualstrcpynW` at `0x1800462d7`
- `SHCORE!__imp_ualstrcpynW` at `0x1800462d7`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180046280`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180046280`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CFSFolder::GetDisplayNameOf(
        CFSFolder *this,
        const struct _ITEMID_CHILD *a2,
        unsigned int a3,
        struct _STRRET *a4)
{
  __int64 v8; // rdi
  __int64 v9; // rax
  HRESULT v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // rcx
  const struct _ITEMID_CHILD *v15; // r14
  char IsEnabled; // al
  unsigned __int16 v17; // r8
  unsigned __int16 *v18; // rdx
  __int64 v19; // r9
  unsigned int v20; // ecx
  unsigned __int16 *v21; // rcx
  _BYTE *v22; // rax
  unsigned __int64 v23; // rcx
  int v24; // edx
  unsigned __int16 *v26; // r8
  _WORD *v27; // rax
  unsigned __int16 *v28; // r9
  _WORD *v29; // rcx
  int v30; // ebx
  int v31; // eax
  unsigned int v32; // r14d
  int NormalDisplayName; // eax
  WCHAR *v34; // rdx
  WCHAR *v35; // rdx
  ITEMIDLIST *v36; // r14
  unsigned __int16 **v37; // rdx
  int LocalizedFolderPath; // eax
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  _BYTE *v42; // rbx
  char *v43; // rax
  size_t v44; // rsi
  size_t v45; // r14
  WCHAR *v46; // rax
  WCHAR *v47; // rdi
  const WCHAR *FileNameW; // rax
  HRESULT v49; // eax
  unsigned int v50; // ebx
  _WORD *CLSIDExtension; // rax
  __int16 v52; // r11
  __int64 (__fastcall *v53)(char *, GUID *, __int64); // rbx
  __int64 v54; // rax
  int v55; // eax
  unsigned int v56; // ebx
  PWSTR v57; // rcx
  unsigned __int16 **v58; // rax
  int UnescapedHttpUri; // eax
  const ITEMIDLIST *v60; // rcx
  HRESULT v61; // eax
  void **v62; // rax
  __int64 v63; // rdx
  __int64 v64; // rcx
  const ITEMIDLIST *v65; // rcx
  int lpWideCharStr; // [rsp+20h] [rbp-E0h]
  int lpWideCharStra; // [rsp+20h] [rbp-E0h]
  LPCITEMIDLIST ppidlLast; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR ppszPath; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID v70[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v71[2]; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v72; // [rsp+60h] [rbp-A0h]
  LPVOID v73; // [rsp+68h] [rbp-98h]
  LPVOID pv; // [rsp+80h] [rbp-80h]
  __int64 v75; // [rsp+88h] [rbp-78h]
  __int64 v76; // [rsp+90h] [rbp-70h]
  __int64 v77; // [rsp+98h] [rbp-68h]
  __int64 v78; // [rsp+A0h] [rbp-60h]
  __int64 v79; // [rsp+A8h] [rbp-58h]
  WCHAR *v80; // [rsp+B8h] [rbp-48h]
  int v81; // [rsp+D0h] [rbp-30h]
  WCHAR WideCharStr[278]; // [rsp+D4h] [rbp-2Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+258h]

  v8 = 0x7FFFFFFF;
  if ( !a2 )
  {
LABEL_2:
    if ( (a3 & 0xC001) == 0x8000 )
    {
      ppszPath = 0;
      v9 = *((_QWORD *)this + 56) - *(_QWORD *)&GUID_NULL.Data1;
      if ( !v9 )
        v9 = *((_QWORD *)this + 57) - *(_QWORD *)GUID_NULL.Data4;
      if ( v9 )
      {
        v10 = SHGetKnownFolderPath((const KNOWNFOLDERID *const)this + 28, 0x4000u, 0, &ppszPath);
        v11 = v10;
        if ( v10 < 0 )
        {
          v12 = 1163;
LABEL_8:
          v13 = (unsigned int)v10;
LABEL_112:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v12,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
            (const char *)v13,
            lpWideCharStr);
LABEL_113:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1431,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
            (const char *)v11,
            lpWideCharStr);
          goto LABEL_74;
        }
      }
      else
      {
        v42 = (_BYTE *)*((_QWORD *)this + 50);
        if ( v42 )
        {
          v43 = (char *)*((_QWORD *)this + 50);
          do
          {
            if ( !*(_WORD *)v43 )
              break;
            v43 += 2;
            --v8;
          }
          while ( v8 );
          v44 = 2 * ((v43 - v42) >> 1);
          v45 = v44 + 2;
          v46 = (WCHAR *)CoTaskMemAlloc(v44 + 2);
          v47 = v46;
          if ( !v46 )
          {
            ppszPath = 0;
            v11 = -2147024882;
            v13 = 2147942414LL;
            v12 = 1171;
            goto LABEL_112;
          }
          if ( v44 )
          {
            if ( v45 < v44 )
            {
              memset_0(v46, 0, v45);
              *(_DWORD *)_o__errno(v64) = 34;
              invalid_parameter_noinfo();
            }
            else
            {
              memcpy_0(v46, v42, v44);
            }
          }
          v47[v44 / 2] = 0;
          goto LABEL_105;
        }
        v60 = (const ITEMIDLIST *)*((_QWORD *)this + 49);
        if ( v60 )
        {
          v61 = SHGetNameFromIDList(v60, SIGDN_DESKTOPABSOLUTEPARSING, &ppszPath);
          v11 = v61;
          if ( v61 < 0 )
          {
            v12 = 1177;
            v13 = (unsigned int)v61;
            goto LABEL_112;
          }
        }
        else
        {
          v65 = (const ITEMIDLIST *)*((_QWORD *)this + 48);
          if ( v65 )
          {
            v10 = SHGetNameFromIDList(v65, SIGDN_DESKTOPABSOLUTEPARSING, &ppszPath);
            v11 = v10;
            if ( v10 < 0 )
            {
              v12 = 1181;
              goto LABEL_8;
            }
          }
        }
        if ( !ppszPath )
        {
          v11 = -2147024893;
          goto LABEL_113;
        }
        *((_QWORD *)this + 50) = SysAllocString(ppszPath);
      }
      v47 = ppszPath;
LABEL_105:
      a4->uType = 0;
      a4->pOleStr = v47;
      return 0;
    }
    if ( *((_QWORD *)this + 49) && !a3 )
      return 2147500033LL;
    v37 = (unsigned __int16 **)((char *)this + 424);
    if ( !*v37 )
    {
      LocalizedFolderPath = CFSFolder::_GetLocalizedFolderPath((CFSFolder *)((char *)this - 48), v37);
      v11 = LocalizedFolderPath;
      if ( LocalizedFolderPath < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1446,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
          (const char *)(unsigned int)LocalizedFolderPath,
          lpWideCharStr);
        return v11;
      }
    }
    FileNameW = PathFindFileNameW(*((LPCWSTR *)this + 53));
    a4->uType = 0;
    v49 = SHStrDupW(FileNameW, &a4->pOleStr);
    v50 = v49;
    if ( v49 >= 0 )
      return 0;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1447,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
      (const char *)(unsigned int)v49,
      lpWideCharStr);
    return v50;
  }
  v14 = *(unsigned __int16 *)a2;
  if ( (unsigned int)v14 <= 0xB )
    goto LABEL_30;
  if ( (*((_BYTE *)a2 + 2) & 0x70) == 0x30 )
  {
    v15 = a2;
    goto LABEL_12;
  }
  if ( *(_DWORD *)((char *)a2 + 6) != 1179862595
    || *((unsigned __int16 *)a2 + 2) > (unsigned __int64)(v14 - 4)
    || (v15 = (const struct _ITEMID_CHILD *)((char *)a2 + 10),
        !IDListContainerIsConsistent((LPCITEMIDLIST)((char *)a2 + 10), *((unsigned __int16 *)a2 + 2)))
    || v52 != *(_WORD *)v15 + 6
    || (unsigned __int16)(*(_WORD *)v15 + 6) < *(_WORD *)v15 )
  {
LABEL_30:
    if ( *(_WORD *)a2 )
      return 2147942487LL;
    goto LABEL_2;
  }
LABEL_12:
  if ( *(_WORD *)v15 < 0xEu )
    goto LABEL_30;
  if ( !*(_WORD *)a2 )
    goto LABEL_38;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl'::`2'::impl);
  v17 = *(_WORD *)a2;
  if ( IsEnabled )
  {
    if ( v17 < 2u )
      goto LABEL_38;
  }
  v18 = 0;
  v19 = *(unsigned __int16 *)((char *)a2 + v17 - 2);
  if ( (_WORD)v19 )
  {
    if ( v19 + 8 < (unsigned __int64)v17 )
    {
      v18 = (unsigned __int16 *)((char *)a2 + v19);
      v20 = *(unsigned __int16 *)((char *)a2 + v19);
      if ( v20 < 8 || HIWORD(*((_DWORD *)v18 + 1)) != 0xBEEF || (unsigned int)v19 + v20 > v17 )
        v18 = 0;
    }
  }
  v21 = (unsigned __int16 *)((char *)a2 + v17);
  if ( v18 )
  {
    while ( *((_DWORD *)v18 + 1) != -1091633148 )
    {
      v26 = 0;
      if ( v18 + 4 <= v21 )
      {
        v28 = (unsigned __int16 *)((char *)v18 + *v18);
        if ( v28 == v21 )
          goto LABEL_38;
        if ( v28 <= v21 )
        {
          if ( v28 + 4 > v21
            || HIWORD(*((_DWORD *)v28 + 1)) != 0xBEEF
            || (unsigned __int16 *)((char *)v28 + *v28) > v21
            || v28 < v18 + 4 )
          {
            goto LABEL_38;
          }
          v26 = (unsigned __int16 *)((char *)v18 + *v18);
        }
      }
      v18 = v26;
      if ( !v26 )
        goto LABEL_38;
    }
  }
  else
  {
LABEL_38:
    if ( (*((_BYTE *)v15 + 2) & 0x34) == 0x34 )
    {
      v27 = (_WORD *)((char *)v15 + 14);
      if ( v15 != (const struct _ITEMID_CHILD *)-14LL )
      {
        v23 = ((unsigned __int64)*(unsigned __int16 *)v15 - 14) >> 1;
        if ( v23 <= 0x7FFFFFFF )
        {
          for ( ; v23; --v23 )
          {
            if ( !*v27 )
              break;
            ++v27;
          }
          goto LABEL_27;
        }
      }
LABEL_139:
      v24 = -2147024809;
      goto LABEL_29;
    }
  }
  v22 = (char *)v15 + 14;
  if ( v15 == (const struct _ITEMID_CHILD *)-14LL )
    goto LABEL_139;
  v23 = *(unsigned __int16 *)v15 - 14LL;
  if ( v23 > 0x7FFFFFFF )
    goto LABEL_139;
  if ( *(_WORD *)v15 != 14 )
  {
    do
    {
      if ( !*v22 )
        break;
      ++v22;
      --v23;
    }
    while ( v23 );
  }
LABEL_27:
  v24 = -2147024809;
  if ( v23 )
    v24 = 0;
LABEL_29:
  if ( v24 < 0 )
    goto LABEL_30;
  v29 = (_WORD *)((char *)a2 + *(unsigned __int16 *)a2);
  if ( !v29 || !*v29 )
  {
    ppszPath = 0;
    if ( (a3 & 0x8000) == 0 )
    {
      ppszPath = 0;
      NormalDisplayName = CFSFolder::GetNormalDisplayName(
                            (CFSFolder *)((char *)this - 48),
                            (unsigned __int16 *)a2,
                            (unsigned __int64 *)a3,
                            0,
                            &ppszPath);
      v11 = NormalDisplayName;
      if ( NormalDisplayName < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1406,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
          (const char *)(unsigned int)NormalDisplayName,
          lpWideCharStr);
LABEL_74:
        if ( ppszPath )
          CoTaskMemFree(ppszPath);
        return v11;
      }
      v30 = a3 & 1;
      goto LABEL_59;
    }
    v30 = a3 & 1;
    if ( (a3 & 1) == 0 )
    {
      ppszPath = 0;
      v31 = (*(__int64 (__fastcall **)(char *, const struct _ITEMID_CHILD *, PWSTR *))(*((_QWORD *)this + 33) + 128LL))(
              (char *)this + 264,
              a2,
              &ppszPath);
      v32 = v31;
      if ( v31 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1401,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
          (const char *)(unsigned int)v31,
          lpWideCharStr);
        if ( ppszPath )
          CoTaskMemFree(ppszPath);
        return v32;
      }
LABEL_59:
      if ( (a3 & 0x4000) != 0 )
      {
        if ( !v30 && (*((_BYTE *)this + 488) & 0x20) != 0 )
        {
          v70[0] = 0;
          v58 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(v70);
          UnescapedHttpUri = CFSFolder::GetUnescapedHttpUri((CFSFolder *)((char *)this - 48), a2, v58);
          v11 = UnescapedHttpUri;
          if ( UnescapedHttpUri < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x140F,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
              (const char *)(unsigned int)UnescapedHttpUri,
              lpWideCharStr);
            if ( v70[0] )
              CoTaskMemFree(v70[0]);
            goto LABEL_74;
          }
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            &ppszPath,
            v70);
          if ( v70[0] )
            CoTaskMemFree(v70[0]);
        }
        else
        {
          CLSIDExtension = (_WORD *)PathFindCLSIDExtension(ppszPath, 0);
          if ( CLSIDExtension )
            *CLSIDExtension = 0;
        }
      }
      a4->uType = 0;
      a4->pOleStr = ppszPath;
      return 0;
    }
    CFileSysItemString::CFileSysItemString((CFileSysItemString *)v71, (CFSFolder *)((char *)this - 48), a2, v15);
    if ( v80 )
      goto LABEL_95;
    if ( (v81 & 1) != 0 )
    {
LABEL_69:
      v35 = WideCharStr;
LABEL_70:
      wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &ppidlLast,
        v35,
        -1);
      v36 = (ITEMIDLIST *)ppidlLast;
      if ( ppszPath )
        wil::details::close_invoke_helper<1,void (*)(void *),&void CoTaskMemFree(void *),unsigned short *>::close_reset(ppszPath);
      ppszPath = &v36->mkid.cb;
      if ( !v36 )
      {
        v11 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x13FD,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
          (const char *)0x8007000ELL,
          lpWideCharStr);
        CFileSysItemString::~CFileSysItemString((CFileSysItemString *)v71);
        goto LABEL_74;
      }
      v71[0] = &CFileSysItemString::`vftable';
      v39 = v77;
      v77 = 0;
      if ( v39 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      v40 = v75;
      v75 = 0;
      if ( v40 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      v41 = v76;
      v76 = 0;
      if ( v41 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      if ( pv )
        CoTaskMemFree(pv);
      if ( v73 )
        CoTaskMemFree(v73);
      if ( v72 )
        CoTaskMemFree(v72);
      goto LABEL_59;
    }
    if ( v79 )
    {
      v34 = (WCHAR *)(v79 + *(unsigned __int16 *)(v79 + 16));
      if ( ((unsigned __int8)v34 & 1) == 0 )
      {
        if ( v34 != WideCharStr )
        {
          v80 = (WCHAR *)(v79 + *(unsigned __int16 *)(v79 + 16));
          goto LABEL_68;
        }
LABEL_110:
        v81 = 1;
LABEL_68:
        if ( !v80 )
          goto LABEL_69;
LABEL_95:
        v35 = v80;
        goto LABEL_70;
      }
    }
    else
    {
      if ( (*(_BYTE *)(v78 + 2) & 0x34) != 0x34 )
      {
        MultiByteToWideChar(0, 0, (LPCCH)(v78 + 14), -1, WideCharStr, 260);
        goto LABEL_110;
      }
      v34 = (WCHAR *)(v78 + 14);
    }
    ualstrcpynW(WideCharStr, v34, 260);
    goto LABEL_110;
  }
  ppszPath = 0;
  v53 = (__int64 (__fastcall *)(char *, GUID *, __int64))**((_QWORD **)this - 6);
  v54 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>(&ppszPath);
  v55 = v53((char *)this - 48, &GUID_000214e6_0000_0000_c000_000000000046, v54);
  v56 = v55;
  if ( v55 >= 0 )
  {
    v70[0] = 0;
    ppidlLast = 0;
    v62 = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>(v70);
    v11 = SHBindToFolderIDListParentEx(
            (IShellFolder *)ppszPath,
            (LPCITEMIDLIST)a2,
            0,
            &GUID_000214e6_0000_0000_c000_000000000046,
            v62,
            &ppidlLast);
    if ( (v11 & 0x80000000) == 0 )
    {
      v11 = (*(__int64 (__fastcall **)(LPVOID, LPCITEMIDLIST, _QWORD, struct _STRRET *))(*(_QWORD *)v70[0] + 88LL))(
              v70[0],
              ppidlLast,
              a3,
              a4);
      if ( (v11 & 0x80000000) == 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v70);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppszPath);
        return 0;
      }
      v63 = 5159;
    }
    else
    {
      v63 = 5158;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v63,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
      (const char *)v11,
      lpWideCharStra);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v70);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppszPath);
    return v11;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1422,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
    (const char *)(unsigned int)v55,
    lpWideCharStr);
  v57 = ppszPath;
  if ( ppszPath )
  {
    ppszPath = 0;
    (*(void (__fastcall **)(PWSTR))(*(_QWORD *)v57 + 16LL))(v57);
  }
  return v56;
}

```

## disassembly

```asm
0x180045c80  push    rbp
0x180045c82  push    rbx
0x180045c83  push    rsi
0x180045c84  push    rdi
0x180045c85  push    r12
0x180045c87  push    r13
0x180045c89  push    r14
0x180045c8b  push    r15
0x180045c8d  lea     rbp, [rsp-218h]
0x180045c95  sub     rsp, 318h
0x180045c9c  mov     rax, cs:__security_cookie
0x180045ca3  xor     rax, rsp
0x180045ca6  mov     [rbp+250h+var_50], rax
0x180045cad  mov     r12, r9
0x180045cb0  mov     r15d, r8d
0x180045cb3  mov     rsi, rdx
0x180045cb6  mov     r13, rcx
0x180045cb9  mov     edi, 7FFFFFFFh
0x180045cbe  test    rdx, rdx
0x180045cc1  jnz     short loc_180045D2F
0x180045cc3  mov     eax, r15d
0x180045cc6  and     eax, 0C001h
0x180045ccb  cmp     eax, 8000h
0x180045cd0  jnz     loc_1800460D6
0x180045cd6  mov     [rsp+350h+ppszPath], 0
0x180045cdf  lea     rcx, [r13+1C0h]; rfid
0x180045ce6  mov     rax, [rcx]
0x180045ce9  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180045cf0  jnz     short loc_180045CFD
0x180045cf2  mov     rax, [rcx+8]
0x180045cf6  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180045cfd  test    rax, rax
0x180045d00  jz      loc_1800461DD
0x180045d06  lea     r9, [rsp+350h+ppszPath]; ppszPath
0x180045d0b  xor     r8d, r8d; hToken
0x180045d0e  mov     edx, 4000h; dwFlags
0x180045d13  call    SHGetKnownFolderPath
0x180045d18  mov     ebx, eax
0x180045d1a  test    eax, eax
0x180045d1c  jns     loc_1800464F4
0x180045d22  mov     edx, 48Bh
0x180045d27  mov     r9d, eax
0x180045d2a  jmp     loc_180046301
0x180045d2f  movzx   ecx, word ptr [rdx]
0x180045d32  cmp     ecx, 0Bh
0x180045d35  jbe     loc_180045E33
0x180045d3b  movzx   eax, byte ptr [rdx+2]
0x180045d3f  and     al, 70h
0x180045d41  cmp     al, 30h ; '0'
0x180045d43  jnz     loc_180046365
0x180045d49  mov     r14, rsi
0x180045d4c  cmp     word ptr [r14], 0Eh
0x180045d51  jb      loc_180045E33
0x180045d57  cmp     word ptr [rsi], 0
0x180045d5b  jz      loc_180045E7D
0x180045d61  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow> `wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl(void)'::`2'::impl
0x180045d68  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(void)
0x180045d6d  movzx   r8d, word ptr [rsi]
0x180045d71  test    al, al
0x180045d73  jnz     loc_18004654E
0x180045d79  movzx   r10d, r8w
0x180045d7d  xor     edx, edx
0x180045d7f  movzx   ecx, r8w
0x180045d83  movzx   r9d, word ptr [rcx+rsi-2]
0x180045d89  mov     ebx, 0BEEFh
0x180045d8e  test    r9w, r9w
0x180045d92  jz      short loc_180045DCC
0x180045d94  lea     rax, [r9+8]
0x180045d98  cmp     rax, rcx
0x180045d9b  jnb     short loc_180045DCC
0x180045d9d  lea     rdx, [r9+rsi]
0x180045da1  movzx   ecx, word ptr [rdx]
0x180045da4  cmp     ecx, 8
0x180045da7  jb      loc_18004612A
0x180045dad  mov     eax, [rdx+4]
0x180045db0  shr     rax, 10h
0x180045db4  cmp     ax, bx
0x180045db7  jnz     loc_18004612A
0x180045dbd  add     ecx, r9d
0x180045dc0  movzx   eax, r8w
0x180045dc4  cmp     ecx, eax
0x180045dc6  ja      loc_18004612A
0x180045dcc  movzx   ecx, r10w
0x180045dd0  add     rcx, rsi
0x180045dd3  test    rdx, rdx
0x180045dd6  jz      loc_180045E7D
0x180045ddc  cmp     dword ptr [rdx+4], 0BEEF0004h
0x180045de3  jnz     loc_180045ECF
0x180045de9  lea     rax, [r14+0Eh]
0x180045ded  test    rax, rax
0x180045df0  jz      loc_180046537
0x180045df6  movzx   ecx, word ptr [r14]
0x180045dfa  add     rcx, 0FFFFFFFFFFFFFFF2h
0x180045dfe  cmp     rcx, rdi
0x180045e01  ja      loc_180046537
0x180045e07  test    rcx, rcx
0x180045e0a  jz      short loc_180045E1E
0x180045e0c  nop     dword ptr [rax+00h]
0x180045e10  cmp     byte ptr [rax], 0
0x180045e13  jz      short loc_180045E1E
0x180045e15  inc     rax
0x180045e18  sub     rcx, 1
0x180045e1c  jnz     short loc_180045E10
0x180045e1e  xor     eax, eax
0x180045e20  mov     edx, 80070057h
0x180045e25  test    rcx, rcx
0x180045e28  cmovnz  edx, eax
0x180045e2b  test    edx, edx
0x180045e2d  jns     loc_180045EEE
0x180045e33  cmp     word ptr [rsi], 0
0x180045e37  jz      loc_180045CC3
0x180045e3d  mov     eax, 80070057h
0x180045e42  jmp     loc_180045FD9
0x180045e47  lea     rax, [r9+8]
0x180045e4b  cmp     rax, rcx
0x180045e4e  ja      short loc_180045E7D
0x180045e50  mov     eax, [r9+4]
0x180045e54  shr     rax, 10h
0x180045e58  cmp     ax, bx
0x180045e5b  jnz     short loc_180045E7D
0x180045e5d  movzx   eax, word ptr [r9]
0x180045e61  add     rax, r9
0x180045e64  cmp     rax, rcx
0x180045e67  ja      short loc_180045E7D
0x180045e69  cmp     r9, r10
0x180045e6c  jb      short loc_180045E7D
0x180045e6e  mov     r8, r9
0x180045e71  mov     rdx, r8
0x180045e74  test    r8, r8
0x180045e77  jnz     loc_180045DDC
0x180045e7d  movzx   eax, byte ptr [r14+2]
0x180045e82  and     al, 34h
0x180045e84  cmp     al, 34h ; '4'
0x180045e86  jnz     loc_180045DE9
0x180045e8c  lea     rax, [r14+0Eh]
0x180045e90  test    rax, rax
0x180045e93  jz      loc_180046537
0x180045e99  movzx   ecx, word ptr [r14]
0x180045e9d  sub     rcx, 0Eh
0x180045ea1  shr     rcx, 1
0x180045ea4  cmp     rcx, rdi
0x180045ea7  ja      loc_180046537
0x180045ead  test    rcx, rcx
0x180045eb0  jz      loc_180045E1E
0x180045eb6  cmp     word ptr [rax], 0
0x180045eba  jz      loc_180045E1E
0x180045ec0  add     rax, 2
0x180045ec4  sub     rcx, 1
0x180045ec8  jnz     short loc_180045EB6
0x180045eca  jmp     loc_180045E1E
0x180045ecf  xor     r8d, r8d
0x180045ed2  lea     r10, [rdx+8]
0x180045ed6  cmp     r10, rcx
0x180045ed9  ja      short loc_180045E71
0x180045edb  movzx   r9d, word ptr [rdx]
0x180045edf  add     r9, rdx
0x180045ee2  cmp     r9, rcx
0x180045ee5  jz      short loc_180045E7D
0x180045ee7  ja      short loc_180045E71
0x180045ee9  jmp     loc_180045E47
0x180045eee  movzx   ecx, word ptr [rsi]
0x180045ef1  add     rcx, rsi
0x180045ef4  jz      short loc_180045F00
0x180045ef6  cmp     word ptr [rcx], 0
0x180045efa  jnz     loc_1800463FD
0x180045f00  mov     [rsp+350h+ppszPath], 0
0x180045f09  bt      r15d, 0Fh
0x180045f0e  jnb     short loc_180045F85
0x180045f10  mov     ebx, r15d
0x180045f13  and     ebx, 1
0x180045f16  jnz     loc_180045FFD
0x180045f1c  mov     [rsp+350h+ppszPath], 0
0x180045f25  mov     rax, [r13+108h]
0x180045f2c  lea     rcx, [r13+108h]
0x180045f33  lea     r8, [rsp+350h+ppszPath]
0x180045f38  mov     rdx, rsi
0x180045f3b  mov     rax, [rax+80h]
0x180045f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045f47  mov     r14d, eax
0x180045f4a  test    eax, eax
0x180045f4c  jns     short loc_180045FBA
0x180045f4e  mov     rcx, [rbp+258h]; this
0x180045f55  mov     r9d, eax; char *
0x180045f58  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x180045f5f  mov     edx, 1401h; void *
0x180045f64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045f69  nop
0x180045f6a  mov     rcx, [rsp+350h+ppszPath]; pv
0x180045f6f  test    rcx, rcx
0x180045f72  jz      short loc_180045F80
0x180045f74  call    cs:__imp_CoTaskMemFree
0x180045f7b  nop     dword ptr [rax+rax+00h]
0x180045f80  mov     eax, r14d
0x180045f83  jmp     short loc_180045FD9
0x180045f85  mov     [rsp+350h+ppszPath], 0
0x180045f8e  lea     rax, [rsp+350h+ppszPath]
0x180045f93  mov     [rsp+350h+lpWideCharStr], rax; int
0x180045f98  xor     r9d, r9d
0x180045f9b  mov     r8d, r15d
0x180045f9e  mov     rdx, rsi
0x180045fa1  lea     rcx, [r13-30h]
0x180045fa5  call    ?GetNormalDisplayName@CFSFolder@@IEAAJPEFBU_ITEMID_CHILD@@KW4FSIS_UINAME_OPTIONS@@PEAPEAG@Z; CFSFolder::GetNormalDisplayName(_ITEMID_CHILD const *,ulong,FSIS_UINAME_OPTIONS,ushort * *)
0x180045faa  mov     ebx, eax
0x180045fac  test    eax, eax
0x180045fae  js      loc_1800465DD
0x180045fb4  mov     ebx, r15d
0x180045fb7  and     ebx, 1
0x180045fba  bt      r15d, 0Eh
0x180045fbf  jb      loc_180046334
0x180045fc5  mov     dword ptr [r12], 0
0x180045fcd  mov     rax, [rsp+350h+ppszPath]
0x180045fd2  mov     [r12+8], rax
0x180045fd7  xor     eax, eax
0x180045fd9  mov     rcx, [rbp+250h+var_50]
0x180045fe0  xor     rcx, rsp; StackCookie
0x180045fe3  call    __security_check_cookie
0x180045fe8  add     rsp, 318h
0x180045fef  pop     r15
0x180045ff1  pop     r14
0x180045ff3  pop     r13
0x180045ff5  pop     r12
0x180045ff7  pop     rdi
0x180045ff8  pop     rsi
0x180045ff9  pop     rbx
0x180045ffa  pop     rbp
0x180045ffb  retn
0x180045ffd  mov     r9, r14; struct IDFOLDER *
0x180046000  mov     r8, rsi; struct _ITEMIDLIST_RELATIVE *
0x180046003  lea     rdx, [r13-30h]; struct CFSFolder *
0x180046007  lea     rcx, [rsp+350h+var_300]; this
0x18004600c  call    ??0CFileSysItemString@@QEAA@PEAVCFSFolder@@PEFBU_ITEMIDLIST_RELATIVE@@PEFBUIDFOLDER@@@Z; CFileSysItemString::CFileSysItemString(CFSFolder *,_ITEMIDLIST_RELATIVE const *,IDFOLDER const *)
0x180046011  nop
0x180046012  cmp     [rbp+250h+var_298], 0
0x180046017  jnz     loc_1800461CA
0x18004601d  test    byte ptr [rbp+250h+var_280], 1
0x180046021  jnz     short loc_18004605C
0x180046023  mov     rcx, [rbp+250h+var_2A8]
0x180046027  test    rcx, rcx
0x18004602a  jz      loc_1800463BA
0x180046030  movzx   edx, word ptr [rcx+10h]
0x180046034  add     rdx, rcx
0x180046037  test    dl, 1
0x18004603a  jnz     loc_1800462CD
0x180046040  lea     rax, [rbp+250h+WideCharStr]
0x180046044  cmp     rdx, rax
0x180046047  jz      loc_1800462E3
0x18004604d  mov     [rbp+250h+var_298], rdx
0x180046051  cmp     [rbp+250h+var_298], 0
0x180046056  jnz     loc_1800461CA
0x18004605c  lea     rdx, [rbp+250h+WideCharStr]
0x180046060  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180046067  lea     rcx, [rsp+350h+ppidlLast]
0x18004606c  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180046071  mov     r14, [rsp+350h+ppidlLast]
0x180046076  mov     rcx, [rsp+350h+ppszPath]; pv
0x18004607b  test    rcx, rcx
0x18004607e  jnz     loc_1800461D3
0x180046084  mov     [rsp+350h+ppszPath], r14
0x180046089  test    r14, r14
0x18004608c  jnz     loc_180046131
0x180046092  mov     rcx, [rbp+258h]; this
0x180046099  mov     ebx, 8007000Eh
0x18004609e  mov     r9d, ebx; char *
0x1800460a1  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x1800460a8  mov     edx, 13FDh; void *
0x1800460ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800460b2  nop
0x1800460b3  lea     rcx, [rsp+350h+var_300]; this
0x1800460b8  call    ??1CFileSysItemString@@UEAA@XZ; CFileSysItemString::~CFileSysItemString(void)
0x1800460bd  nop
0x1800460be  mov     rcx, [rsp+350h+ppszPath]; pv
0x1800460c3  test    rcx, rcx
0x1800460c6  jz      short loc_180046123
0x1800460c8  call    cs:__imp_CoTaskMemFree
0x1800460cf  nop     dword ptr [rax+rax+00h]
0x1800460d4  jmp     short loc_180046123
0x1800460d6  cmp     qword ptr [r13+188h], 0
0x1800460de  jnz     loc_180046656
0x1800460e4  lea     rcx, [r13-30h]; this
0x1800460e8  lea     rdx, [rcx+1D8h]; unsigned __int16 **
0x1800460ef  cmp     qword ptr [rdx], 0
0x1800460f3  jnz     loc_18004625D
0x1800460f9  call    ?_GetLocalizedFolderPath@CFSFolder@@IEAAJPEAPEAG@Z; CFSFolder::_GetLocalizedFolderPath(ushort * *)
0x1800460fe  mov     ebx, eax
0x180046100  test    eax, eax
0x180046102  jns     loc_18004625D
0x180046108  mov     rcx, [rbp+258h]; this
0x18004610f  mov     r9d, eax; char *
0x180046112  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x180046119  mov     edx, 1446h; void *
0x18004611e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046123  mov     eax, ebx
0x180046125  jmp     loc_180045FD9
0x18004612a  xor     edx, edx
0x18004612c  jmp     loc_180045DCC
0x180046131  lea     rax, ??_7CFileSysItemString@@6B@; const CFileSysItemString::`vftable'
0x180046138  mov     [rsp+350h+var_300], rax
0x18004613d  mov     rcx, [rbp+250h+var_2B8]
0x180046141  xor     r14d, r14d
0x180046144  mov     [rbp+250h+var_2B8], r14
  ... truncated ...
```
