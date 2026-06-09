# AsyncGetClassBits2Ex

- ea: `0x18007a694`
- end: `0x18007b26d`
- name: `AsyncGetClassBits2Ex`
- size: `3033`
- prototype: ``
- caller_count: `3`
- callee_count: `35`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007a5ac`
- `0x1800a8b4c`
- `0x1800bbfd0`

## callees

- `0x18001db50`
- `0x18002fee0`
- `0x180033980`
- `0x180033fa4`
- `0x18005d404`
- `0x18007a694`
- `0x18007b274`
- `0x18007b3f8`
- `0x18007b440`
- `0x18007b4b8`
- `0x18007b6e0`
- `0x18007b978`
- `0x18008f6dc`
- `0x1800a4de0`
- `0x1800a5678`
- `0x1800a5f50`
- `0x1800a8570`
- `0x1800bab80`
- `0x1800babd0`
- `0x1800bb22c`
- `0x1800bc798`
- `0x1800c4618`
- `0x1800c7030`
- `0x1800c76e4`
- `0x1800c9300`
- `0x1800ccd74`
- `0x1800cd52c`
- `0x1800d0f9c`
- `0x1800d4c04`
- `0x1800f0230`
- `0x1800f02cc`
- `0x180124dcc`
- `0x1801285e6`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?EDL_GetDomainFromUri@@YAJPEAUIUri@@PEAPEAG@Z` at `0x18007b09b`
- `iertutil!__imp_?EDL_GetDomainFromUri@@YAJPEAUIUri@@PEAPEAG@Z` at `0x18007b09b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18007aaf9`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18007aaf9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIA` at `0x18007aca1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIA` at `0x18007aca1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007ac0c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007ac0c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18007ac48`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18007ac48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007acb8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007acb8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007a75b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007a75b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetShortPathNameA` at `0x18007ac6d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetShortPathNameA` at `0x18007ac8a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetShortPathNameA` at `0x18007ac6d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetShortPathNameA` at `0x18007ac8a`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18007aa65`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18007aa65`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18007ab31`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18007ad93`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18007ab31`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18007ad93`
- `OLEAUT32!__imp_SysFreeString` at `0x18007b0bb`
- `OLEAUT32!__imp_SysFreeString` at `0x18007b0bb`

## string_xrefs

- `0x18007ac3c`: `ActiveXCache`
- `0x18007b040`: `__SZ_MARKUP_URI`
- `0x18007af78`: `__RESTRICT_ACTIVEXINSTALL`
- `0x18007afbc`: `__ACTIVEXINSTALL_MACHINE_SCOPE`
- `0x18007aff6`: `__ACTIVEXINSTALL_USER_SCOPE`

## pseudocode

```c
__int64 __fastcall AsyncGetClassBits2Ex(__int64 a1, __int64 a2, struct IBindCtx *a3, DWORD a4, void *a5, IID *a6)
{
  const WCHAR *v7; // rdi
  const WCHAR *v8; // rsi
  unsigned int v9; // r12d
  unsigned int v10; // r13d
  const WCHAR *v11; // rcx
  const OLECHAR *v12; // rdx
  HKEY v13; // rbx
  struct CDLDebugLog *DebugLog; // rax
  CDLDebugLog *v15; // r14
  CLocalComponentInfo *v16; // rax
  unsigned int v17; // edx
  CLocalComponentInfo *v18; // rdi
  signed int ClsidFromExtOrMime; // esi
  BOOL v20; // ecx
  const unsigned __int16 *v21; // rcx
  char v22; // al
  GUID *v23; // r12
  CExtensionValidationProxy *v24; // rax
  GUID *p_pclsid; // rdx
  int v27; // r14d
  CExtensionValidationProxy *v28; // rax
  struct IUri *v29; // rsi
  char *v30; // r13
  HRESULT ClassObject; // esi
  unsigned int v32; // r13d
  DWORD v33; // r12d
  GUID *p_Buf1; // rdx
  int v35; // eax
  unsigned int v36; // eax
  struct IInternetHostSecurityManager *HostSecurityManager; // rax
  const unsigned __int16 *v38; // r14
  signed int v39; // eax
  CCodeDownload *v40; // rax
  const unsigned __int16 *v41; // r13
  CCodeDownload *v42; // rax
  CCodeDownload *v43; // r14
  int v44; // eax
  struct IBindCtx v45; // rax
  struct IBindCtx v46; // rax
  struct IBindCtx v47; // rax
  OLECHAR *v48; // rcx
  PCNZWCH v49; // rsi
  int v50; // ecx
  struct IInternetHostSecurityManager *v51; // r12
  int v52; // r15d
  __int64 *v53; // rbx
  __int64 v54; // rax
  unsigned int lpcbData; // [rsp+28h] [rbp-D8h]
  unsigned int v56; // [rsp+30h] [rbp-D0h]
  struct CDLDebugLog *v57; // [rsp+60h] [rbp-A0h]
  DWORD dwFlags; // [rsp+68h] [rbp-98h]
  DWORD cbData; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v60; // [rsp+70h] [rbp-90h]
  unsigned int v61; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD dwClsContext; // [rsp+78h] [rbp-88h]
  struct IBindStatusCallback *v63; // [rsp+80h] [rbp-80h] BYREF
  PCNZWCH lpString1; // [rsp+88h] [rbp-78h] BYREF
  int v65; // [rsp+90h] [rbp-70h] BYREF
  DWORD Type; // [rsp+94h] [rbp-6Ch] BYREF
  LPCWCH v67; // [rsp+98h] [rbp-68h]
  LPCOLESTR v68; // [rsp+A0h] [rbp-60h]
  __int64 v69; // [rsp+A8h] [rbp-58h] BYREF
  CClBinding *v70; // [rsp+B0h] [rbp-50h] BYREF
  LPCWCH v71; // [rsp+B8h] [rbp-48h]
  char *v72; // [rsp+C0h] [rbp-40h] BYREF
  IID *riid; // [rsp+C8h] [rbp-38h]
  LPVOID pvReserved; // [rsp+D0h] [rbp-30h]
  struct IUri *v75; // [rsp+D8h] [rbp-28h] BYREF
  int v76; // [rsp+E0h] [rbp-20h]
  BOOL v77; // [rsp+E4h] [rbp-1Ch]
  __int64 v78; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v79; // [rsp+F0h] [rbp-10h] BYREF
  struct IInternetHostSecurityManager *v80; // [rsp+F8h] [rbp-8h]
  LPCOLESTR lpsz; // [rsp+100h] [rbp+0h]
  HKEY phkResult[2]; // [rsp+110h] [rbp+10h] BYREF
  GUID Buf1; // [rsp+120h] [rbp+20h] BYREF
  GUID pclsid; // [rsp+130h] [rbp+30h] BYREF
  CHAR pszSrch[272]; // [rsp+140h] [rbp+40h] BYREF
  CHAR szShortPath[272]; // [rsp+250h] [rbp+150h] BYREF

  pvReserved = a5;
  v7 = *(const WCHAR **)(a2 + 24);
  v8 = *(const WCHAR **)(a2 + 32);
  v9 = *(_DWORD *)(a2 + 48);
  v10 = *(_DWORD *)(a2 + 52);
  riid = a6;
  v68 = *(LPCOLESTR *)a2;
  v11 = *(const WCHAR **)(a2 + 16);
  dwFlags = *(_DWORD *)(a2 + 56);
  v70 = (CClBinding *)a2;
  v12 = *(const OLECHAR **)(a2 + 8);
  lpString1 = v11;
  v63 = 0;
  v72 = 0;
  v80 = 0;
  cbData = 0;
  v65 = 0;
  v75 = 0;
  dwClsContext = a4;
  lpsz = v12;
  v67 = v7;
  v71 = v8;
  v61 = v9;
  v60 = v10;
  Buf1 = 0;
  pclsid = GUID_NULL;
  phkResult[0] = (HKEY)TlsGetValue(gTlsIndex);
  v13 = phkResult[0];
  if ( !phkResult[0] )
  {
    ClsidFromExtOrMime = CUrlMkTls::TLSAllocData((CUrlMkTls *)phkResult);
    if ( ClsidFromExtOrMime < 0 )
      goto LABEL_26;
    v13 = phkResult[0];
    v8 = v71;
  }
  DebugLog = CDLDebugLog::GetDebugLog(v68, v7, v8, lpString1);
  v57 = DebugLog;
  v15 = DebugLog;
  if ( DebugLog )
    ++*((_DWORD *)DebugLog + 3112);
  v16 = (CLocalComponentInfo *)operator new(0x140u);
  if ( v16 )
  {
    v18 = CLocalComponentInfo::CLocalComponentInfo(v16);
    if ( v18 )
    {
      if ( lpsz )
        CLSIDFromString(lpsz, &pclsid);
      ClsidFromExtOrMime = GetClsidFromExtOrMime(&pclsid, &Buf1, v8, v67, &v72);
      if ( ClsidFromExtOrMime < 0 )
      {
        if ( v15 )
          CDLDebugLog::DebugOut(v15, 1, 1, 0x2733u, v71, v67);
        goto LABEL_20;
      }
      ClsidFromExtOrMime = 0;
      v76 = dwFlags & 0x200;
      v20 = memcmp_0(&Buf1, &GUID_NULL, 0x10u) == 0;
      v77 = v20;
      if ( !v68 && v20 )
        goto LABEL_11;
      if ( memcmp_0(&Buf1, &CLSID_ActiveXPlugin, 0x10u) )
      {
        v67 = 0;
        v71 = 0;
      }
      p_pclsid = &pclsid;
      if ( !v72 )
        p_pclsid = &Buf1;
      v27 = IsControlLocallyInstalled(v72, p_pclsid, v68, v9, v10, v18, 0, 0, &v65);
      if ( v27 < 0 )
        goto LABEL_19;
      if ( (*((_DWORD *)v70 + 14) & 0x400000) != 0 )
      {
        p_Buf1 = &pclsid;
        if ( !v72 )
          p_Buf1 = &Buf1;
        v35 = IsControlLocallyInstalled(v72, p_Buf1, v68, v9, v10, v18, 0, 1, &v65);
        if ( v35 < 0 )
          goto LABEL_19;
        if ( !v27 )
        {
          v27 = 1;
          if ( v35 != 1 )
            goto LABEL_42;
          phkResult[0] = 0;
          cbData = 260;
          Type = 1;
          if ( RegOpenKeyExA(
                 HKEY_LOCAL_MACHINE,
                 "Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings",
                 0,
                 0x20019u,
                 phkResult) < 0
            || RegQueryValueExA(phkResult[0], "ActiveXCache", 0, &Type, (LPBYTE)&g_szOCXCacheDirMachineScope, &cbData) < 0 )
          {
            goto LABEL_77;
          }
          if ( *(_BYTE *)v18 )
          {
            GetShortPathNameA((LPCSTR)v18, szShortPath, 0x104u);
            GetShortPathNameA(&g_szOCXCacheDirMachineScope, pszSrch, 0x104u);
            if ( StrStrIA(szShortPath, pszSrch) )
              ClsidFromExtOrMime = 1;
          }
          RegCloseKey(phkResult[0]);
          if ( !ClsidFromExtOrMime )
          {
LABEL_77:
            ClsidFromExtOrMime = 0;
            goto LABEL_42;
          }
        }
      }
      ClsidFromExtOrMime = v27;
LABEL_42:
      if ( ClsidFromExtOrMime || (v17 = 1, (dwFlags & 1) != 0) )
      {
        cbData = v65;
      }
      else
      {
        v36 = *((_DWORD *)v18 + 70);
        if ( *((_DWORD *)v18 + 78) <= v36
          && (*((_DWORD *)v18 + 78) != v36 || *((_DWORD *)v18 + 79) <= *((_DWORD *)v18 + 71)) )
        {
          goto LABEL_19;
        }
        cbData = 1;
        v9 = -1;
        v61 = -1;
        v10 = -1;
        v60 = -1;
      }
LABEL_11:
      if ( (*((_BYTE *)v70 + 60) & 1) != 0 )
      {
        ClsidFromExtOrMime = -2147024891;
        goto LABEL_19;
      }
      GetUriFromBindCtx(a3, &v75);
      v22 = dwFlags;
      if ( (dwFlags & 4) != 0 && !v9 && !v10 )
      {
        v23 = &pclsid;
        phkResult[0] = 0;
        if ( !v72 )
          v23 = &Buf1;
        Type = IsWebBrowserInImmersiveModeAllowed(a3);
        v24 = (CExtensionValidationProxy *)operator new(0x20u);
        if ( !v24 || (v28 = CExtensionValidationProxy::CExtensionValidationProxy(v24, a3)) == 0 )
        {
          ClsidFromExtOrMime = -2147024882;
LABEL_19:
          v15 = v57;
LABEL_20:
          if ( v72 )
            operator delete(v72);
          goto LABEL_22;
        }
        v29 = v75;
        v30 = (char *)v28 + 16;
        if ( CoInternetIsFeatureEnabled(FEATURE_SAFE_BINDTOOBJECT, 2u)
          || (unsigned int)IsActiveXExtensionAllowed(v23, v29, Type) && !IsClsidKillbittedWorker(v23, g_pAxCompatCache) )
        {
          if ( !v30
            || (ClassObject = (*(__int64 (__fastcall **)(char *, GUID *))(*(_QWORD *)v30 + 24LL))(v30, v23),
                ClassObject != -2147024891) )
          {
            ClassObject = CoGetClassObject(v23, dwClsContext, pvReserved, riid, (LPVOID *)phkResult);
          }
        }
        else
        {
          ClassObject = -2147024891;
        }
        (*(void (__fastcall **)(char *))(*(_QWORD *)v30 + 16LL))(v30);
        if ( ClassObject >= 0 )
        {
          (*(void (__fastcall **)(HKEY))(*(_QWORD *)phkResult[0] + 16LL))(phkResult[0]);
          ClsidFromExtOrMime = 0;
          goto LABEL_19;
        }
        if ( ClassObject == -2147024891 )
          goto LABEL_63;
        v22 = dwFlags;
      }
      if ( (v22 & 2) != 0 )
      {
        ClsidFromExtOrMime = 1;
        goto LABEL_19;
      }
      if ( *((_DWORD *)v18 + 77) )
      {
        v32 = -1;
        v60 = -1;
        v33 = 1;
      }
      else
      {
        v32 = v61;
        if ( v61 != -1 && v60 != -1 )
        {
          *(GUID *)phkResult = pclsid;
          ClsidFromExtOrMime = InstallIEFeature(v21, v67, (struct _GUID *)phkResult, a3, v61, v60, v56);
          if ( ClsidFromExtOrMime != 1 )
            goto LABEL_19;
        }
        v33 = cbData;
      }
      if ( (unsigned __int8)IEConfiguration_GetBool(268435481) )
      {
        ClsidFromExtOrMime = -2146695934;
        goto LABEL_19;
      }
      ClsidFromExtOrMime = SetCoInstall();
      if ( ClsidFromExtOrMime < 0 )
        goto LABEL_19;
      if ( g_bUseOLECoInstall )
      {
        if ( (dwFlags & 0x400) == 0 )
        {
          *(_OWORD *)phkResult = 0;
          CLSIDFromString(v68, (LPCLSID)phkResult);
          ClsidFromExtOrMime = WrapCoInstall(
                                 (struct _GUID *)phkResult,
                                 (unsigned __int16 *)v67,
                                 a3,
                                 dwClsContext,
                                 (__int64)pvReserved,
                                 (__int64)riid,
                                 dwFlags);
          if ( ClsidFromExtOrMime >= 0 )
            goto LABEL_19;
        }
      }
      ClsidFromExtOrMime = SetCodeDownloadTLSVars();
      if ( ClsidFromExtOrMime < 0 )
        goto LABEL_19;
      ClsidFromExtOrMime = SetGlobals();
      if ( ClsidFromExtOrMime < 0 )
        goto LABEL_19;
      if ( !g_bLockedDown )
      {
        ClsidFromExtOrMime = ((__int64 (__fastcall *)(struct IBindCtx *, const wchar_t *, struct IBindStatusCallback **))a3->lpVtbl->GetObjectParam)(
                               a3,
                               L"_BSCB_Holder_",
                               &v63);
        if ( ClsidFromExtOrMime < 0 )
          goto LABEL_19;
        ((void (__fastcall *)(struct IBindCtx *))a3->lpVtbl->AddRef)(a3);
        HostSecurityManager = GetHostSecurityManager(v63);
        v38 = v67;
        v80 = HostSecurityManager;
        v39 = CCodeDownload::HandleDuplicateCodeDownloads(
                lpString1,
                v67,
                v71,
                &Buf1,
                v68,
                dwClsContext,
                pvReserved,
                riid,
                a3,
                v63,
                dwFlags,
                HostSecurityManager);
        v61 = v39;
        ClsidFromExtOrMime = v39;
        if ( v39 < 0 )
          goto LABEL_99;
        if ( v39 == 262632 )
          goto LABEL_19;
        v40 = (CCodeDownload *)operator new(0x340u);
        if ( v40 )
        {
          lpcbData = v32;
          v41 = lpString1;
          v42 = CCodeDownload::CCodeDownload(v40, v68, lpString1, v38, v71, lpcbData, v60, v33, (int *)&v61);
          ClsidFromExtOrMime = v61;
          v43 = v42;
        }
        else
        {
          v41 = lpString1;
          v43 = 0;
        }
        if ( ClsidFromExtOrMime < 0 )
          CCodeDownload::Release(v43);
        v44 = ClsidFromExtOrMime;
        if ( !v43 )
          v44 = -2147024882;
        ClsidFromExtOrMime = v44;
        if ( v44 < 0 )
        {
LABEL_99:
          ((void (__fastcall *)(struct IBindStatusCallback *))v63->lpVtbl->Release)(v63);
          ((void (__fastcall *)(struct IBindCtx *))a3->lpVtbl->Release)(a3);
          goto LABEL_19;
        }
        if ( v57 )
          CCodeDownload::SetDebugLog(v43, v57);
        v45.lpVtbl = a3->lpVtbl;
        v78 = 0;
        if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, __int64 *))v45.lpVtbl->GetObjectParam)(
               a3,
               L"__RESTRICT_ACTIVEXINSTALL",
               &v78) >= 0 )
          *((_DWORD *)v43 + 68) |= 0x1000000u;
        if ( v78 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
          v78 = 0;
        }
        v46.lpVtbl = a3->lpVtbl;
        v69 = 0;
        if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, __int64 *))v46.lpVtbl->GetObjectParam)(
               a3,
               L"__ACTIVEXINSTALL_MACHINE_SCOPE",
               &v69) < 0 )
        {
          if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, __int64 *))a3->lpVtbl->GetObjectParam)(
                 a3,
                 L"__ACTIVEXINSTALL_USER_SCOPE",
                 &v69) < 0 )
            goto LABEL_118;
          *((_DWORD *)v43 + 202) = 2;
          *((_DWORD *)v43 + 201) = 2;
        }
        else
        {
          *((_DWORD *)v43 + 202) = 1;
          *((_DWORD *)v43 + 201) = 1;
        }
        if ( v69 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
          v69 = 0;
        }
LABEL_118:
        v47.lpVtbl = a3->lpVtbl;
        v79 = 0;
        if ( !((unsigned int (__fastcall *)(struct IBindCtx *, const wchar_t *, __int64 *))v47.lpVtbl->GetObjectParam)(
                a3,
                L"__SZ_MARKUP_URI",
                &v79)
          && v79 )
        {
          phkResult[0] = 0;
          if ( !(**(unsigned int (__fastcall ***)(__int64, GUID *, HKEY *))v79)(v79, &IID_IUri, phkResult)
            && phkResult[0] )
          {
            lpString1 = 0;
            if ( !EDL_GetDomainFromUri((struct IUri *)phkResult[0], (unsigned __int16 **)&lpString1) )
            {
              v48 = (OLECHAR *)*((_QWORD *)v43 + 102);
              v49 = lpString1;
              if ( v48 )
                SysFreeString(v48);
              *((_QWORD *)v43 + 102) = v49;
            }
            (*(void (__fastcall **)(HKEY))(*(_QWORD *)phkResult[0] + 16LL))(phkResult[0]);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
        }
        v50 = *((_DWORD *)v70 + 14);
        *((_DWORD *)v43 + 127) = (v50 & 0x400000) != 0;
        if ( (v50 & 0x400000) != 0 )
          *((_DWORD *)v43 + 126) = 1;
        v51 = v80;
        v70 = 0;
        ClsidFromExtOrMime = CCodeDownload::CreateClientBinding(
                               v43,
                               &v70,
                               a3,
                               v63,
                               &pclsid,
                               dwClsContext,
                               pvReserved,
                               riid,
                               1,
                               v80);
        if ( ClsidFromExtOrMime < 0 )
        {
          ((void (__fastcall *)(struct IBindStatusCallback *))v63->lpVtbl->Release)(v63);
          ((void (__fastcall *)(struct IBindCtx *))a3->lpVtbl->Release)(a3);
LABEL_142:
          CCodeDownload::Release(v43);
          goto LABEL_19;
        }
        CClBinding::SetClassString(v70, lpsz);
        v52 = v76;
        if ( v76 || !v77 )
        {
          ClsidFromExtOrMime = CheckActiveXDownloadEnabled(v51, v41, v63);
          if ( ClsidFromExtOrMime < 0 )
            goto LABEL_142;
          *((_DWORD *)v43 + 68) |= v52;
        }
        v53 = (__int64 *)*((_QWORD *)v13 + 2);
        v54 = CList<CCodeBaseHold *,CCodeBaseHold *>::NewNode(v53, 0, *v53);
        if ( v54 )
        {
          *(_QWORD *)(v54 + 16) = v43;
          if ( *v53 )
            *(_QWORD *)(*v53 + 8) = v54;
          else
            v53[1] = v54;
          *v53 = v54;
        }
        *((_QWORD *)v43 + 48) = v54;
        ClsidFromExtOrMime = CCodeDownload::DoCodeDownload(v43, v18, dwFlags);
        v18 = 0;
        goto LABEL_142;
      }
LABEL_63:
      ClsidFromExtOrMime = -2147024891;
      goto LABEL_19;
    }
  }
  else
  {
    v18 = 0;
  }
  ClsidFromExtOrMime = -2147024882;
LABEL_22:
  if ( v15 )
    CDLDebugLog::Release(v15);
  if ( v18 )
    CLocalComponentInfo::`scalar deleting destructor'(v18, v17);
LABEL_26:
  if ( v75 )
  {
    ((void (__fastcall *)(struct IUri *))v75->lpVtbl->Release)(v75);
    v75 = 0;
  }
  if ( v80 )
    ((void (__fastcall *)(struct IInternetHostSecurityManager *))v80->lpVtbl->Release)(v80);
  return (unsigned int)ClsidFromExtOrMime;
}

```

## disassembly

```asm
0x18007a694  mov     [rsp-8+arg_0], rbx
0x18007a699  push    rbp
0x18007a69a  push    rsi
0x18007a69b  push    rdi
0x18007a69c  push    r12
0x18007a69e  push    r13
0x18007a6a0  push    r14
0x18007a6a2  push    r15
0x18007a6a4  lea     rbp, [rsp-270h]
0x18007a6ac  sub     rsp, 370h
0x18007a6b3  mov     rax, cs:__security_cookie
0x18007a6ba  xor     rax, rsp
0x18007a6bd  mov     [rbp+2A0h+var_40], rax
0x18007a6c4  mov     rcx, [rbp+2A0h+arg_20]
0x18007a6cb  mov     rax, rdx
0x18007a6ce  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x18007a6d5  mov     [rbp+2A0h+pvReserved], rcx
0x18007a6d9  mov     r15, r8
0x18007a6dc  mov     rcx, [rbp+2A0h+arg_28]
0x18007a6e3  xorps   xmm0, xmm0
0x18007a6e6  mov     rdi, [rax+18h]
0x18007a6ea  mov     rsi, [rax+20h]
0x18007a6ee  mov     r12d, [rax+30h]
0x18007a6f2  mov     r13d, [rax+34h]
0x18007a6f6  mov     [rbp+2A0h+riid], rcx
0x18007a6fa  mov     rcx, [rdx]
0x18007a6fd  mov     [rbp+2A0h+var_300], rcx
0x18007a701  mov     rcx, [rax+10h]
0x18007a705  mov     eax, [rax+38h]
0x18007a708  mov     [rsp+3A0h+var_338], eax
0x18007a70c  xor     eax, eax
0x18007a70e  mov     [rbp+2A0h+var_2F0], rdx
0x18007a712  mov     rdx, [rdx+8]
0x18007a716  mov     [rbp+2A0h+lpString1], rcx
0x18007a71a  mov     ecx, cs:?gTlsIndex@@3KA; dwTlsIndex
0x18007a720  mov     [rbp+2A0h+var_320], rax
0x18007a724  mov     [rbp+2A0h+var_2E0], rax
0x18007a728  mov     [rbp+2A0h+var_2A8], rax
0x18007a72c  mov     [rsp+3A0h+cbData], eax
0x18007a730  mov     [rbp+2A0h+var_310], eax
0x18007a733  mov     [rbp+2A0h+var_2C8], rax
0x18007a737  mov     [rsp+3A0h+dwClsContext], r9d
0x18007a73c  mov     [rbp+2A0h+lpsz], rdx
0x18007a740  mov     [rbp+2A0h+var_308], rdi
0x18007a744  mov     [rbp+2A0h+var_2E8], rsi
0x18007a748  mov     [rsp+3A0h+var_32C], r12d
0x18007a74d  mov     [rsp+3A0h+var_330], r13d
0x18007a752  movups  [rbp+2A0h+Buf1], xmm0
0x18007a756  movdqu  xmmword ptr [rbp+2A0h+pclsid.Data1], xmm1
0x18007a75b  call    cs:__imp_TlsGetValue
0x18007a762  nop     dword ptr [rax+rax+00h]
0x18007a767  mov     [rbp+2A0h+phkResult], rax
0x18007a76b  mov     rbx, rax
0x18007a76e  test    rax, rax
0x18007a771  jz      loc_18007A924
0x18007a777  mov     r9, [rbp+2A0h+lpString1]; unsigned __int16 *
0x18007a77b  mov     r8, rsi; unsigned __int16 *
0x18007a77e  mov     rcx, [rbp+2A0h+var_300]; unsigned __int16 *
0x18007a782  mov     rdx, rdi; unsigned __int16 *
0x18007a785  call    ?GetDebugLog@CDLDebugLog@@SAPEAV1@PEBG000@Z; CDLDebugLog::GetDebugLog(ushort const *,ushort const *,ushort const *,ushort const *)
0x18007a78a  mov     [rsp+3A0h+var_340], rax
0x18007a78f  mov     r14, rax
0x18007a792  test    rax, rax
0x18007a795  jnz     loc_18007AB1F
0x18007a79b  mov     ecx, 140h; Size
0x18007a7a0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007a7a5  test    rax, rax
0x18007a7a8  jz      loc_18007A91B
0x18007a7ae  mov     rcx, rax; this
0x18007a7b1  call    ??0CLocalComponentInfo@@QEAA@XZ; CLocalComponentInfo::CLocalComponentInfo(void)
0x18007a7b6  mov     rdi, rax
0x18007a7b9  test    rax, rax
0x18007a7bc  jz      loc_18007A91D
0x18007a7c2  mov     rax, [rbp+2A0h+lpsz]
0x18007a7c6  test    rax, rax
0x18007a7c9  jnz     loc_18007AB2A
0x18007a7cf  mov     r9, [rbp+2A0h+var_308]; unsigned __int16 *
0x18007a7d3  lea     rax, [rbp+2A0h+var_2E0]
0x18007a7d7  mov     r8, rsi; unsigned __int16 *
0x18007a7da  mov     [rsp+3A0h+ppv], rax; char **
0x18007a7df  lea     rdx, [rbp+2A0h+Buf1]; pclsid
0x18007a7e3  lea     rcx, [rbp+2A0h+pclsid]; Source
0x18007a7e7  call    ?GetClsidFromExtOrMime@@YAJAEBU_GUID@@AEAU1@PEBG2PEAPEAD@Z; GetClsidFromExtOrMime(_GUID const &,_GUID &,ushort const *,ushort const *,char * *)
0x18007a7ec  mov     esi, eax
0x18007a7ee  test    eax, eax
0x18007a7f0  js      loc_18007AB42
0x18007a7f6  mov     eax, [rsp+3A0h+var_338]
0x18007a7fa  lea     rdx, GUID_NULL; Buf2
0x18007a801  and     eax, 200h
0x18007a806  lea     rcx, [rbp+2A0h+Buf1]; Buf1
0x18007a80a  xor     esi, esi
0x18007a80c  mov     [rbp+2A0h+var_2C0], eax
0x18007a80f  lea     r8d, [rsi+10h]; Size
0x18007a813  call    memcmp_0
0x18007a818  mov     r14, [rbp+2A0h+var_300]
0x18007a81c  xor     ecx, ecx
0x18007a81e  test    eax, eax
0x18007a820  setz    cl
0x18007a823  mov     [rbp+2A0h+var_2BC], ecx
0x18007a826  test    r14, r14
0x18007a829  jnz     loc_18007A940
0x18007a82f  test    ecx, ecx
0x18007a831  jz      loc_18007A940
0x18007a837  mov     rax, [rbp+2A0h+var_2F0]
0x18007a83b  test    byte ptr [rax+3Ch], 1
0x18007a83f  jnz     loc_18007AD25
0x18007a845  lea     rdx, [rbp+2A0h+var_2C8]; struct IUri **
0x18007a849  mov     rcx, r15; struct IBindCtx *
0x18007a84c  call    ?GetUriFromBindCtx@@YAJPEAUIBindCtx@@PEAPEAUIUri@@@Z; GetUriFromBindCtx(IBindCtx *,IUri * *)
0x18007a851  mov     eax, [rsp+3A0h+var_338]
0x18007a855  mov     r14d, 80070005h
0x18007a85b  test    al, 4
0x18007a85d  jz      loc_18007AA98
0x18007a863  test    r12d, r12d
0x18007a866  jnz     loc_18007AA98
0x18007a86c  test    r13d, r13d
0x18007a86f  jnz     loc_18007AA98
0x18007a875  cmp     [rbp+2A0h+var_2E0], 0
0x18007a87a  lea     rax, [rbp+2A0h+Buf1]
0x18007a87e  lea     r12, [rbp+2A0h+pclsid]
0x18007a882  mov     [rbp+2A0h+phkResult], 0
0x18007a88a  mov     rcx, r15; struct IBindCtx *
0x18007a88d  cmovz   r12, rax
0x18007a891  call    ?IsWebBrowserInImmersiveModeAllowed@@YAHPEAUIBindCtx@@@Z; IsWebBrowserInImmersiveModeAllowed(IBindCtx *)
0x18007a896  lea     ecx, [r13+20h]; Size
0x18007a89a  mov     [rbp+2A0h+Type], eax
0x18007a89d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007a8a2  test    rax, rax
0x18007a8a5  jnz     loc_18007A9D6
0x18007a8ab  mov     esi, 8007000Eh
0x18007a8b0  mov     r14, [rsp+3A0h+var_340]
0x18007a8b5  mov     rax, [rbp+2A0h+var_2E0]
0x18007a8b9  test    rax, rax
0x18007a8bc  jnz     loc_18007B21C
0x18007a8c2  test    r14, r14
0x18007a8c5  jnz     loc_18007B229
0x18007a8cb  test    rdi, rdi
0x18007a8ce  jnz     loc_18007B236
0x18007a8d4  mov     rcx, [rbp+2A0h+var_2C8]
0x18007a8d8  test    rcx, rcx
0x18007a8db  jnz     loc_18007B243
0x18007a8e1  mov     rcx, [rbp+2A0h+var_2A8]
0x18007a8e5  test    rcx, rcx
0x18007a8e8  jnz     loc_18007B25C
0x18007a8ee  mov     eax, esi
0x18007a8f0  mov     rcx, [rbp+2A0h+var_40]
0x18007a8f7  xor     rcx, rsp; StackCookie
0x18007a8fa  call    __security_check_cookie
0x18007a8ff  mov     rbx, [rsp+3A0h+arg_0]
0x18007a907  add     rsp, 370h
0x18007a90e  pop     r15
0x18007a910  pop     r14
0x18007a912  pop     r13
0x18007a914  pop     r12
0x18007a916  pop     rdi
0x18007a917  pop     rsi
0x18007a918  pop     rbp
0x18007a919  retn
0x18007a91b  xor     edi, edi
0x18007a91d  mov     esi, 8007000Eh
0x18007a922  jmp     short loc_18007A8C2
0x18007a924  lea     rcx, [rbp+2A0h+phkResult]; this
0x18007a928  call    ?TLSAllocData@CUrlMkTls@@AEAAJXZ; CUrlMkTls::TLSAllocData(void)
0x18007a92d  mov     esi, eax
0x18007a92f  test    eax, eax
0x18007a931  js      short loc_18007A8D4
0x18007a933  mov     rbx, [rbp+2A0h+phkResult]
0x18007a937  mov     rsi, [rbp+2A0h+var_2E8]
0x18007a93b  jmp     loc_18007A777
0x18007a940  mov     r8d, 10h; Size
0x18007a946  lea     rdx, CLSID_ActiveXPlugin; Buf2
0x18007a94d  lea     rcx, [rbp+2A0h+Buf1]; Buf1
0x18007a951  call    memcmp_0
0x18007a956  xor     r8d, r8d
0x18007a959  test    eax, eax
0x18007a95b  jz      short loc_18007A965
0x18007a95d  mov     [rbp+2A0h+var_308], r8
0x18007a961  mov     [rbp+2A0h+var_2E8], r8
0x18007a965  mov     rax, [rbp+2A0h+var_2E0]
0x18007a969  lea     rcx, [rbp+2A0h+Buf1]
0x18007a96d  test    rax, rax
0x18007a970  lea     rdx, [rbp+2A0h+pclsid]
0x18007a974  mov     r9d, r12d; unsigned int
0x18007a977  cmovz   rdx, rcx; struct _GUID *
0x18007a97b  lea     rcx, [rbp+2A0h+var_310]
0x18007a97f  mov     [rsp+3A0h+var_360], rcx; int *
0x18007a984  mov     rcx, rax; char *
0x18007a987  mov     dword ptr [rsp+3A0h+var_368], r8d; int
0x18007a98c  mov     [rsp+3A0h+var_370], r8; char *
0x18007a991  mov     r8, r14; unsigned __int16 *
0x18007a994  mov     [rsp+3A0h+lpcbData], rdi; struct CLocalComponentInfo *
0x18007a999  mov     dword ptr [rsp+3A0h+ppv], r13d; unsigned int
0x18007a99e  call    ?IsControlLocallyInstalled@@YAJPEADQEAU_GUID@@PEBGKKPEAVCLocalComponentInfo@@0HPEAH@Z; IsControlLocallyInstalled(char *,_GUID * const,ushort const *,ulong,ulong,CLocalComponentInfo *,char *,int,int *)
0x18007a9a3  mov     r14d, eax
0x18007a9a6  test    eax, eax
0x18007a9a8  js      loc_18007A8B0
0x18007a9ae  mov     rax, [rbp+2A0h+var_2F0]
0x18007a9b2  test    dword ptr [rax+38h], 400000h
0x18007a9b9  jnz     loc_18007AB7A
0x18007a9bf  mov     esi, r14d
0x18007a9c2  test    esi, esi
0x18007a9c4  jz      loc_18007ACD3
0x18007a9ca  mov     eax, [rbp+2A0h+var_310]
0x18007a9cd  mov     [rsp+3A0h+cbData], eax
0x18007a9d1  jmp     loc_18007A837
0x18007a9d6  mov     rdx, r15; struct IBindCtx *
0x18007a9d9  mov     rcx, rax; this
0x18007a9dc  call    ??0CExtensionValidationProxy@@QEAA@PEAUIBindCtx@@@Z; CExtensionValidationProxy::CExtensionValidationProxy(IBindCtx *)
0x18007a9e1  test    rax, rax
0x18007a9e4  jz      loc_18007A8AB
0x18007a9ea  mov     rsi, [rbp+2A0h+var_2C8]
0x18007a9ee  lea     r13, [rax+10h]
0x18007a9f2  mov     edx, 2; dwFlags
0x18007a9f7  lea     ecx, [rdx+0Eh]; FeatureEntry
0x18007a9fa  call    CoInternetIsFeatureEnabled
0x18007a9ff  test    eax, eax
0x18007aa01  jnz     short loc_18007AA2E
0x18007aa03  mov     r8d, [rbp+2A0h+Type]; int
0x18007aa07  mov     rdx, rsi; struct IUri *
0x18007aa0a  mov     rcx, r12; struct _GUID *
0x18007aa0d  call    ?IsActiveXExtensionAllowed@@YAHAEBU_GUID@@PEAUIUri@@H@Z; IsActiveXExtensionAllowed(_GUID const &,IUri *,int)
0x18007aa12  test    eax, eax
0x18007aa14  jz      short loc_18007AA29
0x18007aa16  mov     rdx, cs:?g_pAxCompatCache@@3PEAVCCompatCacheList@@EA; struct CCompatCacheList *
0x18007aa1d  mov     rcx, r12; struct _GUID *
0x18007aa20  call    ?IsClsidKillbittedWorker@@YA_NPEBU_GUID@@PEAVCCompatCacheList@@@Z; IsClsidKillbittedWorker(_GUID const *,CCompatCacheList *)
0x18007aa25  test    al, al
0x18007aa27  jz      short loc_18007AA2E
0x18007aa29  mov     esi, r14d
0x18007aa2c  jmp     short loc_18007AA73
0x18007aa2e  test    r13, r13
0x18007aa31  jz      short loc_18007AA4D
0x18007aa33  mov     rax, [r13+0]
0x18007aa37  mov     rdx, r12
0x18007aa3a  mov     rcx, r13
0x18007aa3d  mov     rax, [rax+18h]
0x18007aa41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aa46  mov     esi, eax
0x18007aa48  cmp     eax, r14d
0x18007aa4b  jz      short loc_18007AA73
0x18007aa4d  mov     r9, [rbp+2A0h+riid]; riid
0x18007aa51  lea     rax, [rbp+2A0h+phkResult]
0x18007aa55  mov     r8, [rbp+2A0h+pvReserved]; pvReserved
0x18007aa59  mov     rcx, r12; rclsid
0x18007aa5c  mov     edx, [rsp+3A0h+dwClsContext]; dwClsContext
0x18007aa60  mov     [rsp+3A0h+ppv], rax; ppv
0x18007aa65  call    cs:__imp_CoGetClassObject
0x18007aa6c  nop     dword ptr [rax+rax+00h]
0x18007aa71  mov     esi, eax
0x18007aa73  mov     rax, [r13+0]
0x18007aa77  mov     rcx, r13
0x18007aa7a  mov     rax, [rax+10h]
0x18007aa7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aa83  test    esi, esi
0x18007aa85  jns     loc_18007AD2F
0x18007aa8b  cmp     esi, r14d
0x18007aa8e  jz      loc_18007AB17
0x18007aa94  mov     eax, [rsp+3A0h+var_338]
0x18007aa98  test    al, 2
0x18007aa9a  jnz     loc_18007AD46
0x18007aaa0  or      eax, 0FFFFFFFFh
0x18007aaa3  cmp     dword ptr [rdi+134h], 0
0x18007aaaa  jnz     loc_18007AD50
0x18007aab0  mov     r13d, [rsp+3A0h+var_32C]
0x18007aab5  cmp     r13d, eax
0x18007aab8  jz      short loc_18007AAEF
0x18007aaba  mov     esi, [rsp+3A0h+var_330]
0x18007aabe  cmp     esi, eax
0x18007aac0  jz      short loc_18007AAEF
0x18007aac2  movaps  xmm0, xmmword ptr [rbp+2A0h+pclsid.Data1]
0x18007aac6  lea     r8, [rbp+2A0h+phkResult]; struct _GUID
0x18007aaca  mov     rdx, [rbp+2A0h+var_308]; unsigned __int16 *
0x18007aace  mov     r9, r15; struct IBindCtx *
0x18007aad1  mov     dword ptr [rsp+3A0h+lpcbData], esi; unsigned int
0x18007aad5  movdqa  xmmword ptr [rbp+2A0h+phkResult], xmm0
0x18007aada  mov     dword ptr [rsp+3A0h+ppv], r13d; unsigned int
0x18007aadf  call    ?InstallIEFeature@@YAJPEBG0U_GUID@@PEAUIBindCtx@@KKK@Z; InstallIEFeature(ushort const *,ushort const *,_GUID,IBindCtx *,ulong,ulong,ulong)
0x18007aae4  mov     esi, eax
0x18007aae6  cmp     eax, 1
0x18007aae9  jnz     loc_18007A8B0
0x18007aaef  mov     r12d, [rsp+3A0h+cbData]
0x18007aaf4  mov     ecx, 10000019h
0x18007aaf9  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18007ab00  nop     dword ptr [rax+rax+00h]
0x18007ab05  test    al, al
0x18007ab07  jz      loc_18007AD62
0x18007ab0d  mov     esi, 800C0502h
0x18007ab12  jmp     loc_18007A8B0
0x18007ab17  mov     esi, r14d
0x18007ab1a  jmp     loc_18007A8B0
0x18007ab1f  inc     dword ptr [rax+30A0h]
0x18007ab25  jmp     loc_18007A79B
0x18007ab2a  lea     rdx, [rbp+2A0h+pclsid]; pclsid
0x18007ab2e  mov     rcx, rax; lpsz
0x18007ab31  call    cs:__imp_CLSIDFromString
0x18007ab38  nop     dword ptr [rax+rax+00h]
0x18007ab3d  jmp     loc_18007A7CF
0x18007ab42  test    r14, r14
0x18007ab45  jz      loc_18007A8B5
0x18007ab4b  mov     rax, [rbp+2A0h+var_308]
  ... truncated ...
```
