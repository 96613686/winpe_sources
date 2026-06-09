# AsyncGetClassBits2Ex

- ea: `0x180074e2c`
- end: `0x1800759ae`
- name: `AsyncGetClassBits2Ex`
- size: `2946`
- prototype: ``
- caller_count: `3`
- callee_count: `35`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180074d4c`
- `0x1800a1d3c`
- `0x1800b4540`

## callees

- `0x1800150e0`
- `0x18002d6f0`
- `0x18002dcd8`
- `0x180030880`
- `0x180057a44`
- `0x180074e2c`
- `0x1800759b4`
- `0x180075b14`
- `0x180075b5c`
- `0x180075bcc`
- `0x180075de0`
- `0x180076078`
- `0x180089aac`
- `0x18009e0dc`
- `0x18009e830`
- `0x18009f084`
- `0x1800a17a0`
- `0x1800b3230`
- `0x1800b3280`
- `0x1800b37fc`
- `0x1800b4ce8`
- `0x1800bc46c`
- `0x1800bee10`
- `0x1800bf484`
- `0x1800c0f48`
- `0x1800c48fc`
- `0x1800c5044`
- `0x1800c8758`
- `0x1800cc144`
- `0x1800e65d0`
- `0x1800e666c`
- `0x1801184d8`
- `0x18011ba26`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_?EDL_GetDomainFromUri@@YAJPEAUIUri@@PEAPEAG@Z` at `0x1800757e8`
- `iertutil!__imp_?EDL_GetDomainFromUri@@YAJPEAUIUri@@PEAPEAG@Z` at `0x1800757e8`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180075280`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180075280`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIA` at `0x180075404`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIA` at `0x180075404`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180075387`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180075387`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800753bd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800753bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075415`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075415`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180074ef3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180074ef3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetShortPathNameA` at `0x1800753dc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetShortPathNameA` at `0x1800753f3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetShortPathNameA` at `0x1800753dc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetShortPathNameA` at `0x1800753f3`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x1800751f6`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x1800751f6`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800752b2`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800754ea`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800752b2`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800754ea`
- `OLEAUT32!__imp_SysFreeString` at `0x180075802`
- `OLEAUT32!__imp_SysFreeString` at `0x180075802`

## string_xrefs

- `0x1800753b1`: `ActiveXCache`
- `0x180075791`: `__SZ_MARKUP_URI`
- `0x1800756c9`: `__RESTRICT_ACTIVEXINSTALL`
- `0x18007570d`: `__ACTIVEXINSTALL_MACHINE_SCOPE`
- `0x180075747`: `__ACTIVEXINSTALL_USER_SCOPE`

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
  CLocalComponentInfo *v17; // rdi
  signed int ClsidFromExtOrMime; // esi
  BOOL v19; // ecx
  const unsigned __int16 *v20; // rcx
  char v21; // al
  GUID *v22; // r12
  CExtensionValidationProxy *v23; // rax
  GUID *p_pclsid; // rdx
  int v26; // r14d
  CExtensionValidationProxy *v27; // rax
  struct IUri *v28; // rsi
  char *v29; // r13
  HRESULT ClassObject; // esi
  unsigned int v31; // r13d
  DWORD v32; // r12d
  GUID *p_Buf1; // rdx
  int v34; // eax
  unsigned int v35; // eax
  struct IInternetHostSecurityManager *HostSecurityManager; // rax
  const unsigned __int16 *v37; // r14
  signed int v38; // eax
  CCodeDownload *v39; // rax
  const unsigned __int16 *v40; // r13
  CCodeDownload *v41; // rax
  CCodeDownload *v42; // r14
  int v43; // eax
  struct IBindCtx v44; // rax
  struct IBindCtx v45; // rax
  struct IBindCtx v46; // rax
  OLECHAR *v47; // rcx
  PCNZWCH v48; // rsi
  int v49; // ecx
  struct IInternetHostSecurityManager *v50; // r12
  int v51; // r15d
  __int64 *v52; // rbx
  __int64 v53; // rax
  unsigned int lpcbData; // [rsp+28h] [rbp-D8h]
  unsigned int v55; // [rsp+30h] [rbp-D0h]
  struct CDLDebugLog *v56; // [rsp+60h] [rbp-A0h]
  DWORD dwFlags; // [rsp+68h] [rbp-98h]
  DWORD cbData; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v59; // [rsp+70h] [rbp-90h]
  unsigned int v60; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD dwClsContext; // [rsp+78h] [rbp-88h]
  struct IBindStatusCallback *v62; // [rsp+80h] [rbp-80h] BYREF
  PCNZWCH lpString1; // [rsp+88h] [rbp-78h] BYREF
  int v64; // [rsp+90h] [rbp-70h] BYREF
  DWORD Type; // [rsp+94h] [rbp-6Ch] BYREF
  LPCWCH v66; // [rsp+98h] [rbp-68h]
  LPCOLESTR v67; // [rsp+A0h] [rbp-60h]
  __int64 v68; // [rsp+A8h] [rbp-58h] BYREF
  CClBinding *v69; // [rsp+B0h] [rbp-50h] BYREF
  LPCWCH v70; // [rsp+B8h] [rbp-48h]
  char *v71; // [rsp+C0h] [rbp-40h] BYREF
  IID *riid; // [rsp+C8h] [rbp-38h]
  LPVOID pvReserved; // [rsp+D0h] [rbp-30h]
  struct IUri *v74; // [rsp+D8h] [rbp-28h] BYREF
  int v75; // [rsp+E0h] [rbp-20h]
  BOOL v76; // [rsp+E4h] [rbp-1Ch]
  __int64 v77; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v78; // [rsp+F0h] [rbp-10h] BYREF
  struct IInternetHostSecurityManager *v79; // [rsp+F8h] [rbp-8h]
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
  v67 = *(LPCOLESTR *)a2;
  v11 = *(const WCHAR **)(a2 + 16);
  dwFlags = *(_DWORD *)(a2 + 56);
  v69 = (CClBinding *)a2;
  v12 = *(const OLECHAR **)(a2 + 8);
  lpString1 = v11;
  v62 = 0;
  v71 = 0;
  v79 = 0;
  cbData = 0;
  v64 = 0;
  v74 = 0;
  dwClsContext = a4;
  lpsz = v12;
  v66 = v7;
  v70 = v8;
  v60 = v9;
  v59 = v10;
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
    v8 = v70;
  }
  DebugLog = CDLDebugLog::GetDebugLog(v67, v7, v8, lpString1);
  v56 = DebugLog;
  v15 = DebugLog;
  if ( DebugLog )
    ++*((_DWORD *)DebugLog + 3112);
  v16 = (CLocalComponentInfo *)operator new(0x140u);
  if ( v16 )
  {
    v17 = CLocalComponentInfo::CLocalComponentInfo(v16);
    if ( v17 )
    {
      if ( lpsz )
        CLSIDFromString(lpsz, &pclsid);
      ClsidFromExtOrMime = GetClsidFromExtOrMime(&pclsid, &Buf1, v8, v66, &v71);
      if ( ClsidFromExtOrMime < 0 )
      {
        if ( v15 )
          CDLDebugLog::DebugOut(v15, 1, 1, 0x2733u, v70, v66);
        goto LABEL_20;
      }
      ClsidFromExtOrMime = 0;
      v75 = dwFlags & 0x200;
      v19 = memcmp_0(&Buf1, &GUID_NULL, 0x10u) == 0;
      v76 = v19;
      if ( !v67 && v19 )
        goto LABEL_11;
      if ( memcmp_0(&Buf1, &CLSID_ActiveXPlugin, 0x10u) )
      {
        v66 = 0;
        v70 = 0;
      }
      p_pclsid = &pclsid;
      if ( !v71 )
        p_pclsid = &Buf1;
      v26 = IsControlLocallyInstalled(v71, p_pclsid, v67, v9, v10, v17, 0, 0, &v64);
      if ( v26 < 0 )
        goto LABEL_19;
      if ( (*((_DWORD *)v69 + 14) & 0x400000) != 0 )
      {
        p_Buf1 = &pclsid;
        if ( !v71 )
          p_Buf1 = &Buf1;
        v34 = IsControlLocallyInstalled(v71, p_Buf1, v67, v9, v10, v17, 0, 1, &v64);
        if ( v34 < 0 )
          goto LABEL_19;
        if ( !v26 )
        {
          v26 = 1;
          if ( v34 != 1 )
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
          if ( *(_BYTE *)v17 )
          {
            GetShortPathNameA((LPCSTR)v17, szShortPath, 0x104u);
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
      ClsidFromExtOrMime = v26;
LABEL_42:
      if ( ClsidFromExtOrMime || (dwFlags & 1) != 0 )
      {
        cbData = v64;
      }
      else
      {
        v35 = *((_DWORD *)v17 + 70);
        if ( *((_DWORD *)v17 + 78) <= v35
          && (*((_DWORD *)v17 + 78) != v35 || *((_DWORD *)v17 + 79) <= *((_DWORD *)v17 + 71)) )
        {
          goto LABEL_19;
        }
        cbData = 1;
        v9 = -1;
        v60 = -1;
        v10 = -1;
        v59 = -1;
      }
LABEL_11:
      if ( (*((_BYTE *)v69 + 60) & 1) != 0 )
      {
        ClsidFromExtOrMime = -2147024891;
        goto LABEL_19;
      }
      GetUriFromBindCtx(a3, &v74);
      v21 = dwFlags;
      if ( (dwFlags & 4) != 0 && !v9 && !v10 )
      {
        v22 = &pclsid;
        phkResult[0] = 0;
        if ( !v71 )
          v22 = &Buf1;
        Type = IsWebBrowserInImmersiveModeAllowed(a3);
        v23 = (CExtensionValidationProxy *)operator new(0x20u);
        if ( !v23 || (v27 = CExtensionValidationProxy::CExtensionValidationProxy(v23, a3)) == 0 )
        {
          ClsidFromExtOrMime = -2147024882;
LABEL_19:
          v15 = v56;
LABEL_20:
          if ( v71 )
            operator delete(v71);
          goto LABEL_22;
        }
        v28 = v74;
        v29 = (char *)v27 + 16;
        if ( CoInternetIsFeatureEnabled(FEATURE_SAFE_BINDTOOBJECT, 2u)
          || (unsigned int)IsActiveXExtensionAllowed(v22, v28, Type) && !IsClsidKillbittedWorker(v22, g_pAxCompatCache) )
        {
          if ( !v29
            || (ClassObject = (*(__int64 (__fastcall **)(char *, GUID *))(*(_QWORD *)v29 + 24LL))(v29, v22),
                ClassObject != -2147024891) )
          {
            ClassObject = CoGetClassObject(v22, dwClsContext, pvReserved, riid, (LPVOID *)phkResult);
          }
        }
        else
        {
          ClassObject = -2147024891;
        }
        (*(void (__fastcall **)(char *))(*(_QWORD *)v29 + 16LL))(v29);
        if ( ClassObject >= 0 )
        {
          (*(void (__fastcall **)(HKEY))(*(_QWORD *)phkResult[0] + 16LL))(phkResult[0]);
          ClsidFromExtOrMime = 0;
          goto LABEL_19;
        }
        if ( ClassObject == -2147024891 )
          goto LABEL_63;
        v21 = dwFlags;
      }
      if ( (v21 & 2) != 0 )
      {
        ClsidFromExtOrMime = 1;
        goto LABEL_19;
      }
      if ( *((_DWORD *)v17 + 77) )
      {
        v31 = -1;
        v59 = -1;
        v32 = 1;
      }
      else
      {
        v31 = v60;
        if ( v60 != -1 && v59 != -1 )
        {
          *(GUID *)phkResult = pclsid;
          ClsidFromExtOrMime = InstallIEFeature(v20, v66, (struct _GUID *)phkResult, a3, v60, v59, v55);
          if ( ClsidFromExtOrMime != 1 )
            goto LABEL_19;
        }
        v32 = cbData;
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
          CLSIDFromString(v67, (LPCLSID)phkResult);
          ClsidFromExtOrMime = WrapCoInstall(
                                 (struct _GUID *)phkResult,
                                 (unsigned __int16 *)v66,
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
                               &v62);
        if ( ClsidFromExtOrMime < 0 )
          goto LABEL_19;
        ((void (__fastcall *)(struct IBindCtx *))a3->lpVtbl->AddRef)(a3);
        HostSecurityManager = GetHostSecurityManager(v62);
        v37 = v66;
        v79 = HostSecurityManager;
        v38 = CCodeDownload::HandleDuplicateCodeDownloads(
                lpString1,
                v66,
                v70,
                &Buf1,
                v67,
                dwClsContext,
                pvReserved,
                riid,
                a3,
                v62,
                dwFlags,
                HostSecurityManager);
        v60 = v38;
        ClsidFromExtOrMime = v38;
        if ( v38 < 0 )
          goto LABEL_99;
        if ( v38 == 262632 )
          goto LABEL_19;
        v39 = (CCodeDownload *)operator new(0x340u);
        if ( v39 )
        {
          lpcbData = v31;
          v40 = lpString1;
          v41 = CCodeDownload::CCodeDownload(
                  v39,
                  v67,
                  lpString1,
                  v37,
                  (unsigned __int16 *)v70,
                  lpcbData,
                  v59,
                  v32,
                  (int *)&v60);
          ClsidFromExtOrMime = v60;
          v42 = v41;
        }
        else
        {
          v40 = lpString1;
          v42 = 0;
        }
        if ( ClsidFromExtOrMime < 0 )
          CCodeDownload::Release(v42);
        v43 = ClsidFromExtOrMime;
        if ( !v42 )
          v43 = -2147024882;
        ClsidFromExtOrMime = v43;
        if ( v43 < 0 )
        {
LABEL_99:
          ((void (__fastcall *)(struct IBindStatusCallback *))v62->lpVtbl->Release)(v62);
          ((void (__fastcall *)(struct IBindCtx *))a3->lpVtbl->Release)(a3);
          goto LABEL_19;
        }
        if ( v56 )
          CCodeDownload::SetDebugLog(v42, v56);
        v44.lpVtbl = a3->lpVtbl;
        v77 = 0;
        if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, __int64 *))v44.lpVtbl->GetObjectParam)(
               a3,
               L"__RESTRICT_ACTIVEXINSTALL",
               &v77) >= 0 )
          *((_DWORD *)v42 + 68) |= 0x1000000u;
        if ( v77 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
          v77 = 0;
        }
        v45.lpVtbl = a3->lpVtbl;
        v68 = 0;
        if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, __int64 *))v45.lpVtbl->GetObjectParam)(
               a3,
               L"__ACTIVEXINSTALL_MACHINE_SCOPE",
               &v68) < 0 )
        {
          if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, __int64 *))a3->lpVtbl->GetObjectParam)(
                 a3,
                 L"__ACTIVEXINSTALL_USER_SCOPE",
                 &v68) < 0 )
            goto LABEL_118;
          *((_DWORD *)v42 + 202) = 2;
          *((_DWORD *)v42 + 201) = 2;
        }
        else
        {
          *((_DWORD *)v42 + 202) = 1;
          *((_DWORD *)v42 + 201) = 1;
        }
        if ( v68 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
          v68 = 0;
        }
LABEL_118:
        v46.lpVtbl = a3->lpVtbl;
        v78 = 0;
        if ( !((unsigned int (__fastcall *)(struct IBindCtx *, const wchar_t *, __int64 *))v46.lpVtbl->GetObjectParam)(
                a3,
                L"__SZ_MARKUP_URI",
                &v78)
          && v78 )
        {
          phkResult[0] = 0;
          if ( !(**(unsigned int (__fastcall ***)(__int64, GUID *, HKEY *))v78)(v78, &IID_IUri, phkResult)
            && phkResult[0] )
          {
            lpString1 = 0;
            if ( !EDL_GetDomainFromUri((struct IUri *)phkResult[0], (unsigned __int16 **)&lpString1) )
            {
              v47 = (OLECHAR *)*((_QWORD *)v42 + 102);
              v48 = lpString1;
              if ( v47 )
                SysFreeString(v47);
              *((_QWORD *)v42 + 102) = v48;
            }
            (*(void (__fastcall **)(HKEY))(*(_QWORD *)phkResult[0] + 16LL))(phkResult[0]);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
        }
        v49 = *((_DWORD *)v69 + 14);
        *((_DWORD *)v42 + 127) = (v49 & 0x400000) != 0;
        if ( (v49 & 0x400000) != 0 )
          *((_DWORD *)v42 + 126) = 1;
        v50 = v79;
        v69 = 0;
        ClsidFromExtOrMime = CCodeDownload::CreateClientBinding(
                               v42,
                               &v69,
                               a3,
                               v62,
                               &pclsid,
                               dwClsContext,
                               pvReserved,
                               riid,
                               1,
                               v79);
        if ( ClsidFromExtOrMime < 0 )
        {
          ((void (__fastcall *)(struct IBindStatusCallback *))v62->lpVtbl->Release)(v62);
          ((void (__fastcall *)(struct IBindCtx *))a3->lpVtbl->Release)(a3);
LABEL_142:
          CCodeDownload::Release(v42);
          goto LABEL_19;
        }
        CClBinding::SetClassString(v69, lpsz);
        v51 = v75;
        if ( v75 || !v76 )
        {
          ClsidFromExtOrMime = CheckActiveXDownloadEnabled(v50, v40, v62);
          if ( ClsidFromExtOrMime < 0 )
            goto LABEL_142;
          *((_DWORD *)v42 + 68) |= v51;
        }
        v52 = (__int64 *)*((_QWORD *)v13 + 2);
        v53 = CList<CCodeBaseHold *,CCodeBaseHold *>::NewNode(v52, 0, *v52);
        if ( v53 )
        {
          *(_QWORD *)(v53 + 16) = v42;
          if ( *v52 )
            *(_QWORD *)(*v52 + 8) = v53;
          else
            v52[1] = v53;
          *v52 = v53;
        }
        *((_QWORD *)v42 + 48) = v53;
        ClsidFromExtOrMime = CCodeDownload::DoCodeDownload(v42, v17, dwFlags);
        v17 = 0;
        goto LABEL_142;
      }
LABEL_63:
      ClsidFromExtOrMime = -2147024891;
      goto LABEL_19;
    }
  }
  else
  {
    v17 = 0;
  }
  ClsidFromExtOrMime = -2147024882;
LABEL_22:
  if ( v15 )
    CDLDebugLog::Release(v15);
  if ( v17 )
    CLocalComponentInfo::`scalar deleting destructor'(v17);
LABEL_26:
  if ( v74 )
  {
    ((void (__fastcall *)(struct IUri *))v74->lpVtbl->Release)(v74);
    v74 = 0;
  }
  if ( v79 )
    ((void (__fastcall *)(struct IInternetHostSecurityManager *))v79->lpVtbl->Release)(v79);
  return (unsigned int)ClsidFromExtOrMime;
}

```

## disassembly

```asm
0x180074e2c  mov     [rsp-8+arg_0], rbx
0x180074e31  push    rbp
0x180074e32  push    rsi
0x180074e33  push    rdi
0x180074e34  push    r12
0x180074e36  push    r13
0x180074e38  push    r14
0x180074e3a  push    r15
0x180074e3c  lea     rbp, [rsp-270h]
0x180074e44  sub     rsp, 370h
0x180074e4b  mov     rax, cs:__security_cookie
0x180074e52  xor     rax, rsp
0x180074e55  mov     [rbp+2A0h+var_40], rax
0x180074e5c  mov     rcx, [rbp+2A0h+arg_20]
0x180074e63  mov     rax, rdx
0x180074e66  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x180074e6d  mov     [rbp+2A0h+pvReserved], rcx
0x180074e71  mov     r15, r8
0x180074e74  mov     rcx, [rbp+2A0h+arg_28]
0x180074e7b  xorps   xmm0, xmm0
0x180074e7e  mov     rdi, [rax+18h]
0x180074e82  mov     rsi, [rax+20h]
0x180074e86  mov     r12d, [rax+30h]
0x180074e8a  mov     r13d, [rax+34h]
0x180074e8e  mov     [rbp+2A0h+riid], rcx
0x180074e92  mov     rcx, [rdx]
0x180074e95  mov     [rbp+2A0h+var_300], rcx
0x180074e99  mov     rcx, [rax+10h]
0x180074e9d  mov     eax, [rax+38h]
0x180074ea0  mov     [rsp+3A0h+var_338], eax
0x180074ea4  xor     eax, eax
0x180074ea6  mov     [rbp+2A0h+var_2F0], rdx
0x180074eaa  mov     rdx, [rdx+8]
0x180074eae  mov     [rbp+2A0h+lpString1], rcx
0x180074eb2  mov     ecx, cs:?gTlsIndex@@3KA; dwTlsIndex
0x180074eb8  mov     [rbp+2A0h+var_320], rax
0x180074ebc  mov     [rbp+2A0h+var_2E0], rax
0x180074ec0  mov     [rbp+2A0h+var_2A8], rax
0x180074ec4  mov     [rsp+3A0h+cbData], eax
0x180074ec8  mov     [rbp+2A0h+var_310], eax
0x180074ecb  mov     [rbp+2A0h+var_2C8], rax
0x180074ecf  mov     [rsp+3A0h+dwClsContext], r9d
0x180074ed4  mov     [rbp+2A0h+lpsz], rdx
0x180074ed8  mov     [rbp+2A0h+var_308], rdi
0x180074edc  mov     [rbp+2A0h+var_2E8], rsi
0x180074ee0  mov     [rsp+3A0h+var_32C], r12d
0x180074ee5  mov     [rsp+3A0h+var_330], r13d
0x180074eea  movups  [rbp+2A0h+Buf1], xmm0
0x180074eee  movdqu  xmmword ptr [rbp+2A0h+pclsid.Data1], xmm1
0x180074ef3  call    cs:__imp_TlsGetValue
0x180074ef9  mov     [rbp+2A0h+phkResult], rax
0x180074efd  mov     rbx, rax
0x180074f00  test    rax, rax
0x180074f03  jz      loc_1800750B5
0x180074f09  mov     r9, [rbp+2A0h+lpString1]; unsigned __int16 *
0x180074f0d  mov     r8, rsi; unsigned __int16 *
0x180074f10  mov     rcx, [rbp+2A0h+var_300]; unsigned __int16 *
0x180074f14  mov     rdx, rdi; unsigned __int16 *
0x180074f17  call    ?GetDebugLog@CDLDebugLog@@SAPEAV1@PEBG000@Z; CDLDebugLog::GetDebugLog(ushort const *,ushort const *,ushort const *,ushort const *)
0x180074f1c  mov     [rsp+3A0h+var_340], rax
0x180074f21  mov     r14, rax
0x180074f24  test    rax, rax
0x180074f27  jnz     loc_1800752A0
0x180074f2d  mov     ecx, 140h; Size
0x180074f32  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180074f37  test    rax, rax
0x180074f3a  jz      loc_1800750AC
0x180074f40  mov     rcx, rax; this
0x180074f43  call    ??0CLocalComponentInfo@@QEAA@XZ; CLocalComponentInfo::CLocalComponentInfo(void)
0x180074f48  mov     rdi, rax
0x180074f4b  test    rax, rax
0x180074f4e  jz      loc_1800750AE
0x180074f54  mov     rax, [rbp+2A0h+lpsz]
0x180074f58  test    rax, rax
0x180074f5b  jnz     loc_1800752AB
0x180074f61  mov     r9, [rbp+2A0h+var_308]; unsigned __int16 *
0x180074f65  lea     rax, [rbp+2A0h+var_2E0]
0x180074f69  mov     r8, rsi; unsigned __int16 *
0x180074f6c  mov     [rsp+3A0h+ppv], rax; char **
0x180074f71  lea     rdx, [rbp+2A0h+Buf1]; pclsid
0x180074f75  lea     rcx, [rbp+2A0h+pclsid]; Source
0x180074f79  call    ?GetClsidFromExtOrMime@@YAJAEBU_GUID@@AEAU1@PEBG2PEAPEAD@Z; GetClsidFromExtOrMime(_GUID const &,_GUID &,ushort const *,ushort const *,char * *)
0x180074f7e  mov     esi, eax
0x180074f80  test    eax, eax
0x180074f82  js      loc_1800752BD
0x180074f88  mov     eax, [rsp+3A0h+var_338]
0x180074f8c  lea     rdx, GUID_NULL; Buf2
0x180074f93  and     eax, 200h
0x180074f98  lea     rcx, [rbp+2A0h+Buf1]; Buf1
0x180074f9c  xor     esi, esi
0x180074f9e  mov     [rbp+2A0h+var_2C0], eax
0x180074fa1  lea     r8d, [rsi+10h]; Size
0x180074fa5  call    memcmp_0
0x180074faa  mov     r14, [rbp+2A0h+var_300]
0x180074fae  xor     ecx, ecx
0x180074fb0  test    eax, eax
0x180074fb2  setz    cl
0x180074fb5  mov     [rbp+2A0h+var_2BC], ecx
0x180074fb8  test    r14, r14
0x180074fbb  jnz     loc_1800750D1
0x180074fc1  test    ecx, ecx
0x180074fc3  jz      loc_1800750D1
0x180074fc9  mov     rax, [rbp+2A0h+var_2F0]
0x180074fcd  test    byte ptr [rax+3Ch], 1
0x180074fd1  jnz     loc_18007547C
0x180074fd7  lea     rdx, [rbp+2A0h+var_2C8]; struct IUri **
0x180074fdb  mov     rcx, r15; struct IBindCtx *
0x180074fde  call    ?GetUriFromBindCtx@@YAJPEAUIBindCtx@@PEAPEAUIUri@@@Z; GetUriFromBindCtx(IBindCtx *,IUri * *)
0x180074fe3  mov     eax, [rsp+3A0h+var_338]
0x180074fe7  mov     r14d, 80070005h
0x180074fed  test    al, 4
0x180074fef  jz      loc_18007521F
0x180074ff5  test    r12d, r12d
0x180074ff8  jnz     loc_18007521F
0x180074ffe  test    r13d, r13d
0x180075001  jnz     loc_18007521F
0x180075007  cmp     [rbp+2A0h+var_2E0], 0
0x18007500c  lea     rax, [rbp+2A0h+Buf1]
0x180075010  lea     r12, [rbp+2A0h+pclsid]
0x180075014  mov     [rbp+2A0h+phkResult], 0
0x18007501c  mov     rcx, r15; struct IBindCtx *
0x18007501f  cmovz   r12, rax
0x180075023  call    ?IsWebBrowserInImmersiveModeAllowed@@YAHPEAUIBindCtx@@@Z; IsWebBrowserInImmersiveModeAllowed(IBindCtx *)
0x180075028  lea     ecx, [r13+20h]; Size
0x18007502c  mov     [rbp+2A0h+Type], eax
0x18007502f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180075034  test    rax, rax
0x180075037  jnz     loc_180075167
0x18007503d  mov     esi, 8007000Eh
0x180075042  mov     r14, [rsp+3A0h+var_340]
0x180075047  mov     rax, [rbp+2A0h+var_2E0]
0x18007504b  test    rax, rax
0x18007504e  jnz     loc_18007595D
0x180075054  test    r14, r14
0x180075057  jnz     loc_18007596A
0x18007505d  test    rdi, rdi
0x180075060  jnz     loc_180075977
0x180075066  mov     rcx, [rbp+2A0h+var_2C8]
0x18007506a  test    rcx, rcx
0x18007506d  jnz     loc_180075984
0x180075073  mov     rcx, [rbp+2A0h+var_2A8]
0x180075077  test    rcx, rcx
0x18007507a  jnz     loc_18007599D
0x180075080  mov     eax, esi
0x180075082  mov     rcx, [rbp+2A0h+var_40]
0x180075089  xor     rcx, rsp; StackCookie
0x18007508c  call    __security_check_cookie
0x180075091  mov     rbx, [rsp+3A0h+arg_0]
0x180075099  add     rsp, 370h
0x1800750a0  pop     r15
0x1800750a2  pop     r14
0x1800750a4  pop     r13
0x1800750a6  pop     r12
0x1800750a8  pop     rdi
0x1800750a9  pop     rsi
0x1800750aa  pop     rbp
0x1800750ab  retn
0x1800750ac  xor     edi, edi
0x1800750ae  mov     esi, 8007000Eh
0x1800750b3  jmp     short loc_180075054
0x1800750b5  lea     rcx, [rbp+2A0h+phkResult]; this
0x1800750b9  call    ?TLSAllocData@CUrlMkTls@@AEAAJXZ; CUrlMkTls::TLSAllocData(void)
0x1800750be  mov     esi, eax
0x1800750c0  test    eax, eax
0x1800750c2  js      short loc_180075066
0x1800750c4  mov     rbx, [rbp+2A0h+phkResult]
0x1800750c8  mov     rsi, [rbp+2A0h+var_2E8]
0x1800750cc  jmp     loc_180074F09
0x1800750d1  mov     r8d, 10h; Size
0x1800750d7  lea     rdx, CLSID_ActiveXPlugin; Buf2
0x1800750de  lea     rcx, [rbp+2A0h+Buf1]; Buf1
0x1800750e2  call    memcmp_0
0x1800750e7  xor     r8d, r8d
0x1800750ea  test    eax, eax
0x1800750ec  jz      short loc_1800750F6
0x1800750ee  mov     [rbp+2A0h+var_308], r8
0x1800750f2  mov     [rbp+2A0h+var_2E8], r8
0x1800750f6  mov     rax, [rbp+2A0h+var_2E0]
0x1800750fa  lea     rcx, [rbp+2A0h+Buf1]
0x1800750fe  test    rax, rax
0x180075101  lea     rdx, [rbp+2A0h+pclsid]
0x180075105  mov     r9d, r12d; unsigned int
0x180075108  cmovz   rdx, rcx; struct _GUID *
0x18007510c  lea     rcx, [rbp+2A0h+var_310]
0x180075110  mov     [rsp+3A0h+var_360], rcx; int *
0x180075115  mov     rcx, rax; char *
0x180075118  mov     dword ptr [rsp+3A0h+var_368], r8d; int
0x18007511d  mov     [rsp+3A0h+var_370], r8; char *
0x180075122  mov     r8, r14; unsigned __int16 *
0x180075125  mov     [rsp+3A0h+lpcbData], rdi; struct CLocalComponentInfo *
0x18007512a  mov     dword ptr [rsp+3A0h+ppv], r13d; unsigned int
0x18007512f  call    ?IsControlLocallyInstalled@@YAJPEADQEAU_GUID@@PEBGKKPEAVCLocalComponentInfo@@0HPEAH@Z; IsControlLocallyInstalled(char *,_GUID * const,ushort const *,ulong,ulong,CLocalComponentInfo *,char *,int,int *)
0x180075134  mov     r14d, eax
0x180075137  test    eax, eax
0x180075139  js      loc_180075042
0x18007513f  mov     rax, [rbp+2A0h+var_2F0]
0x180075143  test    dword ptr [rax+38h], 400000h
0x18007514a  jnz     loc_1800752F5
0x180075150  mov     esi, r14d
0x180075153  test    esi, esi
0x180075155  jz      loc_18007542A
0x18007515b  mov     eax, [rbp+2A0h+var_310]
0x18007515e  mov     [rsp+3A0h+cbData], eax
0x180075162  jmp     loc_180074FC9
0x180075167  mov     rdx, r15; struct IBindCtx *
0x18007516a  mov     rcx, rax; this
0x18007516d  call    ??0CExtensionValidationProxy@@QEAA@PEAUIBindCtx@@@Z; CExtensionValidationProxy::CExtensionValidationProxy(IBindCtx *)
0x180075172  test    rax, rax
0x180075175  jz      loc_18007503D
0x18007517b  mov     rsi, [rbp+2A0h+var_2C8]
0x18007517f  lea     r13, [rax+10h]
0x180075183  mov     edx, 2; dwFlags
0x180075188  lea     ecx, [rdx+0Eh]; FeatureEntry
0x18007518b  call    CoInternetIsFeatureEnabled
0x180075190  test    eax, eax
0x180075192  jnz     short loc_1800751BF
0x180075194  mov     r8d, [rbp+2A0h+Type]; int
0x180075198  mov     rdx, rsi; struct IUri *
0x18007519b  mov     rcx, r12; struct _GUID *
0x18007519e  call    ?IsActiveXExtensionAllowed@@YAHAEBU_GUID@@PEAUIUri@@H@Z; IsActiveXExtensionAllowed(_GUID const &,IUri *,int)
0x1800751a3  test    eax, eax
0x1800751a5  jz      short loc_1800751BA
0x1800751a7  mov     rdx, cs:?g_pAxCompatCache@@3PEAVCCompatCacheList@@EA; struct CCompatCacheList *
0x1800751ae  mov     rcx, r12; struct _GUID *
0x1800751b1  call    ?IsClsidKillbittedWorker@@YA_NPEBU_GUID@@PEAVCCompatCacheList@@@Z; IsClsidKillbittedWorker(_GUID const *,CCompatCacheList *)
0x1800751b6  test    al, al
0x1800751b8  jz      short loc_1800751BF
0x1800751ba  mov     esi, r14d
0x1800751bd  jmp     short loc_1800751FE
0x1800751bf  test    r13, r13
0x1800751c2  jz      short loc_1800751DE
0x1800751c4  mov     rax, [r13+0]
0x1800751c8  mov     rdx, r12
0x1800751cb  mov     rcx, r13
0x1800751ce  mov     rax, [rax+18h]
0x1800751d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800751d7  mov     esi, eax
0x1800751d9  cmp     eax, r14d
0x1800751dc  jz      short loc_1800751FE
0x1800751de  mov     r9, [rbp+2A0h+riid]; riid
0x1800751e2  lea     rax, [rbp+2A0h+phkResult]
0x1800751e6  mov     r8, [rbp+2A0h+pvReserved]; pvReserved
0x1800751ea  mov     rcx, r12; rclsid
0x1800751ed  mov     edx, [rsp+3A0h+dwClsContext]; dwClsContext
0x1800751f1  mov     [rsp+3A0h+ppv], rax; ppv
0x1800751f6  call    cs:__imp_CoGetClassObject
0x1800751fc  mov     esi, eax
0x1800751fe  mov     rax, [r13+0]
0x180075202  mov     rcx, r13
0x180075205  mov     rax, [rax+10h]
0x180075209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007520e  test    esi, esi
0x180075210  jns     loc_180075486
0x180075216  cmp     esi, r14d
0x180075219  jz      short loc_180075298
0x18007521b  mov     eax, [rsp+3A0h+var_338]
0x18007521f  test    al, 2
0x180075221  jnz     loc_18007549D
0x180075227  or      eax, 0FFFFFFFFh
0x18007522a  cmp     dword ptr [rdi+134h], 0
0x180075231  jnz     loc_1800754A7
0x180075237  mov     r13d, [rsp+3A0h+var_32C]
0x18007523c  cmp     r13d, eax
0x18007523f  jz      short loc_180075276
0x180075241  mov     esi, [rsp+3A0h+var_330]
0x180075245  cmp     esi, eax
0x180075247  jz      short loc_180075276
0x180075249  movaps  xmm0, xmmword ptr [rbp+2A0h+pclsid.Data1]
0x18007524d  lea     r8, [rbp+2A0h+phkResult]; struct _GUID
0x180075251  mov     rdx, [rbp+2A0h+var_308]; unsigned __int16 *
0x180075255  mov     r9, r15; struct IBindCtx *
0x180075258  mov     dword ptr [rsp+3A0h+lpcbData], esi; unsigned int
0x18007525c  movdqa  xmmword ptr [rbp+2A0h+phkResult], xmm0
0x180075261  mov     dword ptr [rsp+3A0h+ppv], r13d; unsigned int
0x180075266  call    ?InstallIEFeature@@YAJPEBG0U_GUID@@PEAUIBindCtx@@KKK@Z; InstallIEFeature(ushort const *,ushort const *,_GUID,IBindCtx *,ulong,ulong,ulong)
0x18007526b  mov     esi, eax
0x18007526d  cmp     eax, 1
0x180075270  jnz     loc_180075042
0x180075276  mov     r12d, [rsp+3A0h+cbData]
0x18007527b  mov     ecx, 10000019h
0x180075280  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180075286  test    al, al
0x180075288  jz      loc_1800754B9
0x18007528e  mov     esi, 800C0502h
0x180075293  jmp     loc_180075042
0x180075298  mov     esi, r14d
0x18007529b  jmp     loc_180075042
0x1800752a0  inc     dword ptr [rax+30A0h]
0x1800752a6  jmp     loc_180074F2D
0x1800752ab  lea     rdx, [rbp+2A0h+pclsid]; pclsid
0x1800752af  mov     rcx, rax; lpsz
0x1800752b2  call    cs:__imp_CLSIDFromString
0x1800752b8  jmp     loc_180074F61
0x1800752bd  test    r14, r14
0x1800752c0  jz      loc_180075047
0x1800752c6  mov     rax, [rbp+2A0h+var_308]
0x1800752ca  mov     r9d, 2733h; unsigned int
0x1800752d0  mov     rcx, [rbp+2A0h+var_2E8]
0x1800752d4  mov     [rsp+3A0h+lpcbData], rax
0x1800752d9  mov     eax, 1
  ... truncated ...
```
