# IsValidURL

- ea: `0x18001eaa0`
- end: `0x18001fa8d`
- name: `IsValidURL`
- size: `4077`
- prototype: `HRESULT __stdcall(LPBC pBC, LPCWSTR szURL, DWORD dwReserved)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180018bfc`
- `0x18001db50`
- `0x18001db94`
- `0x18001e580`
- `0x18001eaa0`
- `0x18001fc10`
- `0x180020ee8`
- `0x180024e2c`
- `0x18002fee0`
- `0x180031480`
- `0x180037ab0`
- `0x1800490d0`
- `0x1800a5e20`
- `0x1801285e6`
- `0x180128660`
- `0x180128720`
- `0x180129010`

## import_xrefs

- `msvcrt!wcschr` at `0x18001f316`
- `msvcrt!wcschr` at `0x18001f316`
- `iertutil!CreateUri` at `0x18001ec73`
- `iertutil!CreateUri` at `0x18001ed7c`
- `iertutil!CreateUri` at `0x18001ec73`
- `iertutil!CreateUri` at `0x18001ed7c`
- `iertutil!PrivateCoInternetCombineIUri` at `0x18001ee60`
- `iertutil!PrivateCoInternetCombineIUri` at `0x18001ee60`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x18001f7e1`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x18001f80e`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x18001f7e1`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x18001f80e`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x18001eb80`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x18001ec9d`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x18001eb80`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x18001ec9d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ede3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f219`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f43d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ede3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f219`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f43d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001edb2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f1e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f3a2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001edb2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f1e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f3a2`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18001f260`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18001f260`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18001f71d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18001f71d`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001ebd9`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001ec02`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001ec3d`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001ece7`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001ed10`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001ed4b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001ebd9`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001ec02`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001ec3d`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001ece7`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001ed10`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001ed4b`
- `api-ms-win-core-atoms-l1-1-0!AddAtomW` at `0x18001f77d`
- `api-ms-win-core-atoms-l1-1-0!AddAtomW` at `0x18001f77d`
- `api-ms-win-core-atoms-l1-1-0!FindAtomW` at `0x18001f3bf`
- `api-ms-win-core-atoms-l1-1-0!FindAtomW` at `0x18001f3bf`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18001fa67`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18001fa67`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f953`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f9bb`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f953`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f9bb`
- `OLEAUT32!__imp_SysStringLen` at `0x18001f99c`
- `OLEAUT32!__imp_SysStringLen` at `0x18001f99c`

## pseudocode

```c
HRESULT __stdcall IsValidURL(LPBC pBC, LPCWSTR szURL, DWORD dwReserved)
{
  const WCHAR *v5; // rbx
  LPVOID v6; // rcx
  HRESULT v7; // esi
  int v8; // r14d
  bool ShouldUseEdge; // r15
  int v10; // edi
  int v11; // ecx
  DWORD v12; // edx
  signed int v13; // ebx
  bool v14; // bl
  int v15; // ecx
  DWORD v16; // edx
  IUri *v17; // r15
  LPVOID v18; // rdi
  COInetSession *v19; // rax
  int v20; // r14d
  volatile signed __int32 *v21; // rbx
  struct IUri *v22; // rdi
  _BOOL8 v23; // r14
  _BOOL8 v24; // r15
  __int64 v25; // rdx
  __int64 v26; // rcx
  WCHAR *v27; // rax
  BSTR v28; // r8
  WCHAR *v29; // rcx
  _BOOL8 v30; // rdi
  unsigned int v31; // ebx
  int v32; // ebx
  __int64 v33; // rax
  int v34; // r15d
  WCHAR v35; // cx
  int v36; // edx
  int v37; // ecx
  IID *v38; // rax
  COInetSession *v40; // rax
  int v41; // ebx
  COInetSession *v42; // r13
  int i; // ebx
  COInetSession *v44; // rax
  __int64 v45; // rcx
  int ClassObject; // r14d
  WCHAR *v47; // r9
  wchar_t *v48; // rax
  __int64 v49; // r8
  wchar_t *v50; // rcx
  wchar_t *v51; // rax
  char *v52; // rdi
  struct _RTL_CRITICAL_SECTION *v53; // rbx
  ATOM AtomW; // ax
  __int64 j; // rcx
  IID *v56; // rax
  __int64 v57; // rcx
  int v58; // ecx
  IID *KnownOInetProtocolClsID; // rax
  unsigned int v60; // ecx
  __int64 v61; // rbx
  __int64 (__fastcall ***v62)(CEasyClassFactory *__hidden, const struct _GUID *, void **); // rcx
  unsigned int k; // r14d
  __int64 v64; // rdi
  const void *v65; // rdx
  struct IUriVtbl *lpVtbl; // rax
  int v67; // ebx
  COInetSession *v68; // rax
  __int64 m; // r12
  int v70; // ecx
  unsigned int v71; // r12d
  ATOM v72; // ax
  ATOM v73; // bx
  struct _GUID *v74; // rax
  struct _GUID v75; // xmm0
  int IsFeatureEnabledInternal; // eax
  int v77; // eax
  CProtocolData *v78; // rax
  CProtocolData *v79; // r12
  DWORD cchResult[2]; // [rsp+20h] [rbp-E0h]
  int pcchResult; // [rsp+28h] [rbp-D8h]
  IUri *v82; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v83; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v85[2]; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v86; // [rsp+60h] [rbp-A0h] BYREF
  void *v87; // [rsp+68h] [rbp-98h] BYREF
  IUri *ppURI; // [rsp+70h] [rbp-90h] BYREF
  IID Buf1; // [rsp+78h] [rbp-88h] BYREF
  struct _GUID v90[64]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Str[4]; // [rsp+490h] [rbp+390h] BYREF
  struct IUri *v92; // [rsp+498h] [rbp+398h]
  unsigned int v93; // [rsp+4A0h] [rbp+3A0h]
  BSTR bstrString[2]; // [rsp+4A8h] [rbp+3A8h] BYREF
  UINT v95[6]; // [rsp+4B8h] [rbp+3B8h] BYREF
  WCHAR pszStr1[2088]; // [rsp+4D0h] [rbp+3D0h] BYREF

  if ( !szURL )
    return -2147024809;
  v83 = 0;
  v5 = 0;
  v87 = 0;
  v86 = 0;
  pszStr1[0] = 0;
  if ( pBC )
  {
    if ( ((unsigned int (__fastcall *)(LPBC, const wchar_t *, LPVOID *))pBC->lpVtbl->GetObjectParam)(
           pBC,
           L"URL Context",
           &v86) )
    {
      v6 = 0;
      v86 = 0;
    }
    else
    {
      v6 = v86;
    }
    if ( v6 )
    {
      (*(void (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)v6 + 176LL))(v6, &v83);
      if ( v83 == 6 )
        (*(void (__fastcall **)(LPVOID, LPBC, _QWORD, void **))(*(_QWORD *)v86 + 160LL))(v86, pBC, 0, &v87);
    }
    v5 = (const WCHAR *)v87;
  }
  if ( !v5 )
  {
    v85[0] = 2085;
    v7 = 1;
    v31 = (unsigned int)CoInternetParseUrl(szURL, PARSE_CANONICALIZE, 0x10000u, pszStr1, 0x825u, v85, 0) >> 31;
    goto LABEL_78;
  }
  v92 = 0;
  *(_QWORD *)Str = &CUString::`vftable';
  *(_OWORD *)bstrString = 0;
  v93 = 11;
  v95[0] = 0;
  ppURI = 0;
  *(_QWORD *)v85 = 0;
  v7 = 1;
  v8 = 50342821;
  ShouldUseEdge = InternalForkingSupport_ShouldUseEdge();
  if ( !ShouldUseEdge )
  {
LABEL_11:
    v10 = 33565605;
    if ( !ShouldUseEdge )
      goto LABEL_15;
    goto LABEL_12;
  }
  v10 = 50342821;
  if ( FCK::FEATURE_DISABLE_DATAURI_SUPPORT )
  {
    IsFeatureEnabledInternal = CoInternetIsFeatureEnabledInternal();
    if ( IsFeatureEnabledInternal < 0 )
      goto LABEL_12;
    dword_180166BE8 = IsFeatureEnabledInternal == 0;
    FCK::FEATURE_DISABLE_DATAURI_SUPPORT = 0;
  }
  if ( dword_180166BE8 )
    goto LABEL_11;
LABEL_12:
  InitOnceExecuteOnce(&stru_18016AF28, (PINIT_ONCE_FN)GlobalInitOnceUrlMon, 0, 0);
  if ( (dword_18016B858 & 1) != 0 )
  {
    InitOnceExecuteOnce(&stru_18016AF28, (PINIT_ONCE_FN)GlobalInitOnceUrlMon, 0, 0);
    if ( (dword_18016B858 & 2) != 0 || (unsigned int)IsABrowserApp() )
      goto LABEL_16;
  }
LABEL_15:
  v10 &= ~0x2000000u;
  if ( ShouldUseEdge )
LABEL_16:
    InitOnceExecuteOnce(&stru_18016AF28, (PINIT_ONCE_FN)GlobalInitOnceUrlMon, 0, 0);
  v11 = v10 | 0x2000000;
  if ( (v10 & 0x2000000) != 0 )
    v11 = v10;
  v12 = v11 | 0x1000000;
  if ( (v11 & 0x1000000) != 0 )
    v12 = v11;
  v13 = CreateUri(v5, v12, 0, &ppURI);
  if ( v13 < 0 )
    goto LABEL_67;
  *(_QWORD *)&Buf1.Data1 = ppURI;
  v82 = 0;
  *(_QWORD *)v85 = 0;
  v14 = InternalForkingSupport_ShouldUseEdge();
  if ( !v14 )
    goto LABEL_25;
  if ( FCK::FEATURE_DISABLE_DATAURI_SUPPORT )
  {
    v77 = CoInternetIsFeatureEnabledInternal();
    if ( v77 < 0 )
      goto LABEL_26;
    dword_180166BE8 = v77 == 0;
    FCK::FEATURE_DISABLE_DATAURI_SUPPORT = 0;
  }
  if ( dword_180166BE8 )
  {
LABEL_25:
    v8 = 33565605;
    if ( !v14 )
      goto LABEL_29;
  }
LABEL_26:
  InitOnceExecuteOnce(&stru_18016AF28, (PINIT_ONCE_FN)GlobalInitOnceUrlMon, 0, 0);
  if ( (dword_18016B858 & 1) == 0
    || (InitOnceExecuteOnce(&stru_18016AF28, (PINIT_ONCE_FN)GlobalInitOnceUrlMon, 0, 0), (dword_18016B858 & 2) == 0)
    && !(unsigned int)IsABrowserApp() )
  {
LABEL_29:
    v8 &= ~0x2000000u;
    if ( !v14 )
      goto LABEL_31;
  }
  InitOnceExecuteOnce(&stru_18016AF28, (PINIT_ONCE_FN)GlobalInitOnceUrlMon, 0, 0);
LABEL_31:
  v15 = v8 | 0x2000000;
  if ( (v8 & 0x2000000) != 0 )
    v15 = v8;
  v16 = v15 | 0x1000000;
  if ( (v15 & 0x1000000) != 0 )
    v16 = v15;
  v13 = CreateUri(szURL, v16, 0, &v82);
  if ( v13 < 0 )
    goto LABEL_48;
  v17 = v82;
  if ( v82 )
  {
    ppv = 0;
    v18 = 0;
    EnterCriticalSection(&g_mxsOInet);
    v19 = g_pCOInetSession;
    if ( g_pCOInetSession )
    {
      v20 = 0;
    }
    else
    {
      v68 = (COInetSession *)operator new(0x180u);
      if ( v68 && (v19 = COInetSession::COInetSession(v68)) != 0 )
      {
        v20 = 0;
        g_pCOInetSession = v19;
      }
      else
      {
        v19 = g_pCOInetSession;
        v20 = -2147024882;
      }
      if ( !v19 )
      {
        v21 = 0;
        v20 = -2147024882;
        goto LABEL_40;
      }
    }
    _InterlockedAdd((volatile signed __int32 *)v19 + 4, 1u);
    v21 = (volatile signed __int32 *)g_pCOInetSession;
LABEL_40:
    LeaveCriticalSection(&g_mxsOInet);
    if ( !v20 )
    {
      if ( v21 )
      {
        if ( !memcmp_0(&GUID_79eac9ec_baf9_11ce_8c82_00aa004ba90b, &IID_IInternetProtocolInfo, 0x10u) )
        {
          v18 = (LPVOID)(v21 + 2);
          _InterlockedAdd(v21 + 4, 1u);
        }
        else if ( !(unsigned int)COInetSession::QueryInterface(
                                   (COInetSession *)v21,
                                   &GUID_79eac9ec_baf9_11ce_8c82_00aa004ba90b,
                                   &ppv) )
        {
          v18 = ppv;
        }
      }
      _InterlockedDecrement(v21 + 4);
    }
    v13 = PrivateCoInternetCombineIUri(*(_QWORD *)&Buf1.Data1, v17, 0x10000, v85, 0, v18, 0, 0);
    if ( v18 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
LABEL_48:
    if ( v82 )
      ((void (__fastcall *)(IUri *))v82->lpVtbl->Release)(v82);
    if ( v13 >= 0 )
    {
      v22 = *(struct IUri **)v85;
      v13 = 0;
      v23 = *(_QWORD *)v85 != (_QWORD)v92;
      v24 = v93 != 0;
      if ( *(struct IUri **)v85 != v92 || v93 )
      {
        if ( bstrString[0] )
        {
          SysFreeString(bstrString[0]);
          bstrString[0] = 0;
        }
        bstrString[1] = 0;
        v95[0] = 0;
        if ( v23 && v92 )
        {
          ((void (__fastcall *)(struct IUri *))v92->lpVtbl->Release)(v92);
          v92 = 0;
        }
      }
      v93 = 0;
      if ( !v22 || !v24 && !v23 )
        goto LABEL_58;
      lpVtbl = v22->lpVtbl;
      v82 = 0;
      if ( ((int (__fastcall *)(struct IUri *, GUID *, IUri **))lpVtbl->QueryInterface)(
             v22,
             &GUID_50295b0c_6b79_4935_aed8_05d80ec86a60,
             &v82) < 0 )
      {
        v13 = ((__int64 (__fastcall *)(struct IUri *, _QWORD, BSTR *, _QWORD))v22->lpVtbl->GetPropertyBSTR)(
                v22,
                v93,
                bstrString,
                0);
        if ( v13 >= 0 )
        {
          bstrString[1] = bstrString[0];
          v95[0] = SysStringLen(bstrString[0]);
        }
      }
      else
      {
        v13 = ((__int64 (__fastcall *)(IUri *, _QWORD, BSTR *, UINT *))v82->lpVtbl[1].QueryInterface)(
                v82,
                v93,
                &bstrString[1],
                v95);
        ((void (__fastcall *)(IUri *))v82->lpVtbl->Release)(v82);
      }
      if ( v23 && v13 >= 0 )
      {
        v92 = v22;
        ((void (__fastcall *)(struct IUri *))v22->lpVtbl->AddRef)(v22);
      }
      if ( v13 == 1 && (v13 = CUString::Set((CUString *)Str, *(struct IUri **)v85, 0xBu), v13 == 1) )
      {
        v13 = -2146697214;
      }
      else
      {
LABEL_58:
        if ( v13 >= 0 )
        {
          v25 = 2085;
          if ( v95[0] >= 0x825 )
          {
            v13 = -2147467261;
          }
          else
          {
            v26 = v95[0];
            v27 = pszStr1;
            v28 = bstrString[1];
            do
            {
              if ( !v26 )
                break;
              if ( !*v28 )
                break;
              *v27++ = *v28++;
              --v26;
              --v25;
            }
            while ( v25 );
            v29 = v27 - 1;
            if ( v25 )
              v29 = v27;
            v13 = v25 == 0 ? 0x8007007A : 0;
            *v29 = 0;
          }
        }
      }
    }
    goto LABEL_67;
  }
  v13 = -2147418113;
LABEL_67:
  if ( ppURI )
  {
    ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
    ppURI = 0;
  }
  if ( *(_QWORD *)v85 )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v85 + 16LL))(*(_QWORD *)v85);
    *(_QWORD *)v85 = 0;
  }
  *(_QWORD *)Str = &CUString::`vftable';
  v30 = v92 != 0;
  if ( v92 || v93 != 11 )
  {
    if ( bstrString[0] )
    {
      SysFreeString(bstrString[0]);
      bstrString[0] = 0;
    }
    bstrString[1] = 0;
    v95[0] = 0;
    if ( v30 && v92 )
      ((void (__fastcall *)(struct IUri *))v92->lpVtbl->Release)(v92);
  }
  v31 = (unsigned int)v13 >> 31;
LABEL_78:
  if ( v31 )
    goto LABEL_213;
  v32 = 0;
  v33 = -1;
  do
    ++v33;
  while ( pszStr1[v33] );
  if ( !v33 )
LABEL_213:
    v32 = -2147221020;
  if ( v87 )
    operator delete(v87);
  if ( v32 )
    return v7;
  v87 = 0;
  v82 = 0;
  v34 = 0;
  Buf1 = 0;
  if ( pBC
    && ((int (__fastcall *)(LPBC, const wchar_t *, IUri **))pBC->lpVtbl->GetObjectParam)(pBC, L"_BSCB_Holder_", &v82) >= 0
    && (v67 = ((__int64 (__fastcall *)(IUri *, GUID *, void **))v82->lpVtbl->QueryInterface)(
                v82,
                &IID_IBindStatusCallback,
                &v87),
        ((void (__fastcall *)(IUri *))v82->lpVtbl->Release)(v82),
        v67 >= 0) )
  {
    v82 = 0;
    if ( (**(int (__fastcall ***)(void *, GUID *, IUri **))v87)(v87, &IID_IServiceProvider, &v82) >= 0 )
    {
      ppv = 0;
      if ( ((int (__fastcall *)(IUri *, GUID *, GUID *, LPVOID *))v82->lpVtbl->GetPropertyBSTR)(
             v82,
             &IID_IInternetProtocol,
             &IID_IInternetProtocol,
             &ppv) >= 0
        && ppv )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        v34 = 1;
      }
      ((void (__fastcall *)(IUri *))v82->lpVtbl->Release)(v82);
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v87 + 16LL))(v87);
    if ( v34 )
      return 0;
  }
  else
  {
    v87 = 0;
  }
  EnterCriticalSection(&g_mxsOInet);
  v40 = g_pCOInetSession;
  if ( g_pCOInetSession )
  {
    v41 = 0;
LABEL_109:
    _InterlockedAdd((volatile signed __int32 *)v40 + 4, 1u);
    v42 = g_pCOInetSession;
    goto LABEL_110;
  }
  v44 = (COInetSession *)operator new(0x180u);
  if ( v44 && (v40 = COInetSession::COInetSession(v44)) != 0 )
  {
    v41 = 0;
    g_pCOInetSession = v40;
  }
  else
  {
    v40 = g_pCOInetSession;
    v41 = -2147024882;
  }
  if ( v40 )
    goto LABEL_109;
  v42 = 0;
  v41 = -2147024882;
LABEL_110:
  ppv = v42;
  LeaveCriticalSection(&g_mxsOInet);
  if ( v41 )
    return v7;
  for ( i = 0; ; ++i )
  {
    if ( i >= 12 )
      goto LABEL_120;
    if ( !StrCmpNICW(pszStr1, (LPCWSTR)*(&off_18012A010 + 5 * i), dword_18012A030[10 * i]) )
    {
      v35 = pszStr1[dword_18012A030[10 * i]];
      if ( v35 == 58 || !v35 )
        break;
    }
  }
  v36 = dword_18012A020[10 * i];
  if ( v36 )
  {
    v37 = 0;
    while ( v36 != dword_18012A020[10 * v37] )
    {
      ++v37;
      v38 = 0;
      if ( v37 >= 12 )
        goto LABEL_94;
    }
    v38 = *(&off_18012A028 + 5 * v37);
LABEL_94:
    Buf1 = *v38;
    goto LABEL_95;
  }
LABEL_120:
  v45 = 31;
  v86 = 0;
  ClassObject = -2146697203;
  v47 = pszStr1;
  v48 = Str;
  v49 = 32;
  do
  {
    if ( !v45 )
      break;
    if ( !*v47 )
      break;
    *v48++ = *v47++;
    --v45;
    --v49;
  }
  while ( v49 );
  v50 = v48 - 1;
  if ( v49 )
    v50 = v48;
  *v50 = 0;
  v51 = wcschr(Str, 0x3Au);
  if ( v51 )
  {
    v52 = (char *)v42 + 96;
    *v51 = 0;
    v53 = (struct _RTL_CRITICAL_SECTION *)((char *)v42 + 112);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v42 + 112));
    *((_QWORD *)v42 + 20) = 0;
    if ( *((int *)v42 + 27) > 0 )
    {
      AtomW = FindAtomW(Str);
      if ( AtomW )
      {
        for ( j = *((_QWORD *)v42 + 19); ; j = *(_QWORD *)(j + 32) )
        {
          *((_QWORD *)v42 + 20) = j;
          if ( !j || *(_WORD *)j == AtomW )
            break;
        }
      }
    }
    if ( *((_QWORD *)v42 + 20) )
    {
LABEL_141:
      v56 = (IID *)*((_QWORD *)v52 + 8);
      if ( v56 )
      {
        Buf1 = v56[1];
        v57 = *((_QWORD *)v52 + 8);
        if ( *(_QWORD *)(v57 + 8) )
        {
          v86 = *(LPVOID *)(v57 + 8);
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v57 + 8) + 8LL))(*(_QWORD *)(v57 + 8));
          ClassObject = 0;
        }
        else
        {
          ppv = 0;
          ClassObject = CoGetClassObject(&Buf1, 1u, 0, &IID_IClassFactory, &ppv);
          if ( !ClassObject )
            v86 = ppv;
        }
        *((_QWORD *)v52 + 8) = *(_QWORD *)(*((_QWORD *)v52 + 8) + 32LL);
      }
      LeaveCriticalSection(v53);
      if ( ClassObject )
      {
        v58 = IsKnownProtocol(Str);
        if ( !v58 )
        {
LABEL_156:
          ClassObject = (**((__int64 (__fastcall ***)(__int64, wchar_t *, LPVOID *, IID *, DWORD *, int))v42 + 3))(
                          (__int64)v42 + 24,
                          Str,
                          &v86,
                          &Buf1,
                          *(DWORD **)cchResult,
                          pcchResult);
          goto LABEL_127;
        }
        KnownOInetProtocolClsID = (IID *)GetKnownOInetProtocolClsID(v58);
        v61 = 16LL * v60;
        Buf1 = *KnownOInetProtocolClsID;
        v62 = *(__int64 (__fastcall ****)(CEasyClassFactory *__hidden, const struct _GUID *, void **))((char *)v42 + v61 + 264);
        if ( !v62 )
        {
          if ( !memcmp_0(&GUID_00000001_0000_0000_c000_000000000046, &IID_IClassFactory, 0x10u)
            || !memcmp_0(&GUID_00000001_0000_0000_c000_000000000046, &IID_IUnknown, 0x10u) )
          {
            for ( k = 0; ; ++k )
            {
              v64 = 4LL * k;
              v65 = *(const void **)((char *)&off_18012D4B8 + v64 * 8);
              if ( !v65 )
                break;
              if ( !memcmp_0(&Buf1, v65, 0x10u) )
              {
                _InterlockedAdd((volatile signed __int32 *)&g_cRef, 1u);
                v62 = &(&off_18012D4B0)[v64];
                if ( !&(&off_18012D4B0)[v64] )
                  goto LABEL_156;
                if ( _InterlockedCompareExchange64(
                       (volatile signed __int64 *)((char *)v42 + v61 + 264),
                       (signed __int64)v62,
                       0) )
                {
                  ((void (__fastcall *)(__int64 (__fastcall ***)(CEasyClassFactory *__hidden, const struct _GUID *, void **)))(*v62)[2])(v62);
                  v62 = *(__int64 (__fastcall ****)(CEasyClassFactory *__hidden, const struct _GUID *, void **))((char *)v42 + v61 + 264);
                  if ( !v62 )
                    goto LABEL_156;
                }
                else
                {
                  _InterlockedAdd(&g_lCOInetSessionDllRefcount, 1u);
                }
                goto LABEL_154;
              }
            }
          }
          goto LABEL_156;
        }
LABEL_154:
        v86 = v62;
        ((void (__fastcall *)(__int64 (__fastcall ***)(CEasyClassFactory *__hidden, const struct _GUID *, void **)))(*v62)[1])(v62);
      }
      ClassObject = 0;
      goto LABEL_127;
    }
    for ( m = *((_QWORD *)v42 + 21); m; m = *(_QWORD *)(m + 8) )
    {
      if ( !StrCmpICW(Str, *(LPCWSTR *)m) )
      {
        v70 = 1;
        goto LABEL_185;
      }
    }
    v78 = (CProtocolData *)operator new(0x10u);
    v79 = v78;
    if ( v78 )
    {
      *(_QWORD *)v78 = 0;
      *((_QWORD *)v78 + 1) = 0;
      if ( (unsigned int)CProtocolData::Init(v78, Str, *((struct CProtocolData **)v42 + 21)) )
      {
        *((_QWORD *)v42 + 21) = v79;
        v70 = 0;
LABEL_185:
        v71 = 0;
        if ( !v70 )
        {
          pcchResult = 0;
          *(_QWORD *)cchResult = 0;
          v83 = 64;
          ClassObject = CProtMgrNameSpace::LookupClsIDFromReg((COInetSession *)((char *)v42 + 96), Str, v90, &v83);
          if ( !ClassObject )
          {
            v72 = AddAtomW(Str);
            if ( v83 )
            {
              v73 = v72;
              do
              {
                v74 = (struct _GUID *)operator new(0x38u);
                if ( v74 )
                {
                  LOWORD(v74->Data1) = v73;
                  v75 = v90[v71];
                  *(_QWORD *)v74->Data4 = 0;
                  *(_QWORD *)v74[2].Data4 = 0;
                  v74[1] = v75;
                  *(_QWORD *)&v74[3].Data1 = 0;
                  *(_QWORD *)&v74[2].Data1 = *((_QWORD *)v42 + 19);
                  *((_QWORD *)v42 + 19) = v74;
                  _InterlockedAdd((volatile signed __int32 *)v42 + 27, 1u);
                }
                else
                {
                  v74 = 0;
                }
                if ( !*((_QWORD *)v42 + 20) )
                  *((_QWORD *)v42 + 20) = v74;
                ++v71;
              }
              while ( v71 < v83 );
              v42 = (COInetSession *)ppv;
              v53 = (struct _RTL_CRITICAL_SECTION *)(v52 + 16);
            }
          }
        }
        goto LABEL_141;
      }
      CProtocolData::`scalar deleting destructor'(v79);
    }
    v70 = -2147024882;
    goto LABEL_185;
  }
LABEL_127:
  if ( v86 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v86 + 16LL))(v86);
  if ( !ClassObject
    || ClassObject != -2146697202
    && !(*(unsigned int (__fastcall **)(__int64, WCHAR *, IID *, _QWORD, _QWORD, _DWORD))(*((_QWORD *)v42 + 3) + 16LL))(
          (__int64)v42 + 24,
          pszStr1,
          &Buf1,
          0,
          0,
          0) )
  {
LABEL_95:
    v34 = 1;
  }
  _InterlockedDecrement((volatile signed __int32 *)v42 + 4);
  if ( v34 )
    return 0;
  return v7;
}

```

## disassembly

```asm
0x18001eaa0  mov     [rsp-8+arg_10], rbx
0x18001eaa5  push    rbp
0x18001eaa6  push    rsi
0x18001eaa7  push    rdi
0x18001eaa8  push    r12
0x18001eaaa  push    r13
0x18001eaac  push    r14
0x18001eaae  push    r15
0x18001eab0  lea     rbp, [rsp-1430h]
0x18001eab8  mov     eax, 1530h
0x18001eabd  call    _alloca_probe
0x18001eac2  sub     rsp, rax
0x18001eac5  mov     rax, cs:__security_cookie
0x18001eacc  xor     rax, rsp
0x18001eacf  mov     [rbp+1460h+var_40], rax
0x18001ead6  xor     esi, esi
0x18001ead8  mov     r12, rdx
0x18001eadb  mov     r13, rcx
0x18001eade  test    rdx, rdx
0x18001eae1  jz      loc_18001F0BA
0x18001eae7  mov     [rsp+1560h+var_1518], esi
0x18001eaeb  mov     ebx, esi
0x18001eaed  mov     [rsp+1560h+var_14F8], rbx
0x18001eaf2  mov     [rsp+1560h+var_1500], rsi
0x18001eaf7  mov     [rbp+1460h+pszStr1], si
0x18001eafe  test    rcx, rcx
0x18001eb01  jz      short loc_18001EB38
0x18001eb03  mov     rax, [rcx]
0x18001eb06  lea     r8, [rsp+1560h+var_1500]
0x18001eb0b  lea     rdx, aUrlContext; "URL Context"
0x18001eb12  mov     rax, [rax+50h]
0x18001eb16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb1b  test    eax, eax
0x18001eb1d  jz      loc_18001F8FC
0x18001eb23  mov     ecx, esi
0x18001eb25  mov     [rsp+1560h+var_1500], rcx
0x18001eb2a  test    rcx, rcx
0x18001eb2d  jnz     loc_18001F906
0x18001eb33  mov     rbx, [rsp+1560h+var_14F8]
0x18001eb38  mov     edi, 8007000Eh
0x18001eb3d  test    rbx, rbx
0x18001eb40  jz      loc_18001F6C1
0x18001eb46  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x18001eb4d  mov     [rbp+1460h+var_10C8], rsi
0x18001eb54  xorps   xmm0, xmm0
0x18001eb57  mov     qword ptr [rbp+1460h+Str], rax
0x18001eb5e  movdqu  xmmword ptr [rbp+1460h+bstrString], xmm0
0x18001eb66  mov     [rbp+1460h+var_10C0], 0Bh
0x18001eb70  mov     [rbp+1460h+var_10A8], esi
0x18001eb76  mov     [rsp+1560h+ppURI], rsi
0x18001eb7b  mov     qword ptr [rsp+1560h+var_1508], rsi
0x18001eb80  call    cs:__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ; InternalForkingSupport_ShouldUseEdge(void)
0x18001eb87  nop     dword ptr [rax+rax+00h]
0x18001eb8c  mov     esi, 1
0x18001eb91  mov     r14d, 3002BA5h
0x18001eb97  mov     r15b, al
0x18001eb9a  test    al, al
0x18001eb9c  jz      short loc_18001EBBB
0x18001eb9e  mov     rcx, cs:?FEATURE_DISABLE_DATAURI_SUPPORT@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_DISABLE_DATAURI_SUPPORT
0x18001eba5  mov     edi, r14d
0x18001eba8  test    rcx, rcx
0x18001ebab  jnz     loc_18001F7E1
0x18001ebb1  mov     eax, cs:dword_180166BE8
0x18001ebb7  test    eax, eax
0x18001ebb9  jz      short loc_18001EBC5
0x18001ebbb  mov     edi, 2002BA5h
0x18001ebc0  test    r15b, r15b
0x18001ebc3  jz      short loc_18001EC20
0x18001ebc5  xor     r9d, r9d; Context
0x18001ebc8  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001ebcf  xor     r8d, r8d; Parameter
0x18001ebd2  lea     rcx, stru_18016AF28; InitOnce
0x18001ebd9  call    cs:__imp_InitOnceExecuteOnce
0x18001ebe0  nop     dword ptr [rax+rax+00h]
0x18001ebe5  test    byte ptr cs:dword_18016B858, sil
0x18001ebec  jz      short loc_18001EC20
0x18001ebee  xor     r9d, r9d; Context
0x18001ebf1  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001ebf8  xor     r8d, r8d; Parameter
0x18001ebfb  lea     rcx, stru_18016AF28; InitOnce
0x18001ec02  call    cs:__imp_InitOnceExecuteOnce
0x18001ec09  nop     dword ptr [rax+rax+00h]
0x18001ec0e  test    byte ptr cs:dword_18016B858, 2
0x18001ec15  jnz     short loc_18001EC29
0x18001ec17  call    ?IsABrowserApp@@YAHXZ; IsABrowserApp(void)
0x18001ec1c  test    eax, eax
0x18001ec1e  jnz     short loc_18001EC29
0x18001ec20  btr     edi, 19h
0x18001ec24  test    r15b, r15b
0x18001ec27  jz      short loc_18001EC49
0x18001ec29  xor     r9d, r9d; Context
0x18001ec2c  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001ec33  xor     r8d, r8d; Parameter
0x18001ec36  lea     rcx, stru_18016AF28; InitOnce
0x18001ec3d  call    cs:__imp_InitOnceExecuteOnce
0x18001ec44  nop     dword ptr [rax+rax+00h]
0x18001ec49  mov     edx, 2000000h
0x18001ec4e  lea     r9, [rsp+1560h+ppURI]; ppURI
0x18001ec53  mov     ecx, edi
0x18001ec55  xor     r15d, r15d
0x18001ec58  or      ecx, edx
0x18001ec5a  test    edx, edi
0x18001ec5c  cmovnz  ecx, edi
0x18001ec5f  mov     edi, 1000000h
0x18001ec64  mov     edx, ecx
0x18001ec66  or      edx, edi
0x18001ec68  test    edi, ecx
0x18001ec6a  cmovnz  edx, ecx; dwFlags
0x18001ec6d  xor     r8d, r8d; dwReserved
0x18001ec70  mov     rcx, rbx; pwzURI
0x18001ec73  call    cs:__imp_CreateUri
0x18001ec7a  nop     dword ptr [rax+rax+00h]
0x18001ec7f  mov     ebx, eax
0x18001ec81  test    eax, eax
0x18001ec83  js      loc_18001F9B3
0x18001ec89  mov     rax, [rsp+1560h+ppURI]
0x18001ec8e  mov     qword ptr [rsp+1560h+Buf1.Data1], rax
0x18001ec93  mov     [rsp+1560h+var_1520], r15
0x18001ec98  mov     qword ptr [rsp+1560h+var_1508], r15
0x18001ec9d  call    cs:__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ; InternalForkingSupport_ShouldUseEdge(void)
0x18001eca4  nop     dword ptr [rax+rax+00h]
0x18001eca9  mov     bl, al
0x18001ecab  test    al, al
0x18001ecad  jz      short loc_18001ECC9
0x18001ecaf  mov     rcx, cs:?FEATURE_DISABLE_DATAURI_SUPPORT@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_DISABLE_DATAURI_SUPPORT
0x18001ecb6  test    rcx, rcx
0x18001ecb9  jnz     loc_18001F80E
0x18001ecbf  mov     eax, cs:dword_180166BE8
0x18001ecc5  test    eax, eax
0x18001ecc7  jz      short loc_18001ECD3
0x18001ecc9  mov     r14d, 2002BA5h
0x18001eccf  test    bl, bl
0x18001ecd1  jz      short loc_18001ED2E
0x18001ecd3  xor     r9d, r9d; Context
0x18001ecd6  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001ecdd  xor     r8d, r8d; Parameter
0x18001ece0  lea     rcx, stru_18016AF28; InitOnce
0x18001ece7  call    cs:__imp_InitOnceExecuteOnce
0x18001ecee  nop     dword ptr [rax+rax+00h]
0x18001ecf3  test    byte ptr cs:dword_18016B858, sil
0x18001ecfa  jz      short loc_18001ED2E
0x18001ecfc  xor     r9d, r9d; Context
0x18001ecff  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001ed06  xor     r8d, r8d; Parameter
0x18001ed09  lea     rcx, stru_18016AF28; InitOnce
0x18001ed10  call    cs:__imp_InitOnceExecuteOnce
0x18001ed17  nop     dword ptr [rax+rax+00h]
0x18001ed1c  test    byte ptr cs:dword_18016B858, 2
0x18001ed23  jnz     short loc_18001ED37
0x18001ed25  call    ?IsABrowserApp@@YAHXZ; IsABrowserApp(void)
0x18001ed2a  test    eax, eax
0x18001ed2c  jnz     short loc_18001ED37
0x18001ed2e  btr     r14d, 19h
0x18001ed33  test    bl, bl
0x18001ed35  jz      short loc_18001ED57
0x18001ed37  xor     r9d, r9d; Context
0x18001ed3a  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001ed41  xor     r8d, r8d; Parameter
0x18001ed44  lea     rcx, stru_18016AF28; InitOnce
0x18001ed4b  call    cs:__imp_InitOnceExecuteOnce
0x18001ed52  nop     dword ptr [rax+rax+00h]
0x18001ed57  mov     edx, 2000000h
0x18001ed5c  lea     r9, [rsp+1560h+var_1520]; ppURI
0x18001ed61  mov     ecx, r14d
0x18001ed64  or      ecx, edx
0x18001ed66  test    edx, r14d
0x18001ed69  cmovnz  ecx, r14d
0x18001ed6d  mov     edx, ecx
0x18001ed6f  or      edx, edi
0x18001ed71  test    edi, ecx
0x18001ed73  cmovnz  edx, ecx; dwFlags
0x18001ed76  xor     r8d, r8d; dwReserved
0x18001ed79  mov     rcx, r12; pwzURI
0x18001ed7c  call    cs:__imp_CreateUri
0x18001ed83  nop     dword ptr [rax+rax+00h]
0x18001ed88  xor     r12d, r12d
0x18001ed8b  mov     ebx, eax
0x18001ed8d  test    eax, eax
0x18001ed8f  js      loc_18001EE82
0x18001ed95  mov     r15, [rsp+1560h+var_1520]
0x18001ed9a  test    r15, r15
0x18001ed9d  jz      loc_18001F949
0x18001eda3  lea     rcx, ?g_mxsOInet@@3VCMutexSem@@A; lpCriticalSection
0x18001edaa  mov     [rsp+1560h+ppv], r12
0x18001edaf  mov     edi, r12d
0x18001edb2  call    cs:__imp_EnterCriticalSection
0x18001edb9  nop     dword ptr [rax+rax+00h]
0x18001edbe  mov     rax, cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA; COInetSession * g_pCOInetSession
0x18001edc5  test    rax, rax
0x18001edc8  jz      loc_18001F649
0x18001edce  mov     r14d, r12d
0x18001edd1  lock add [rax+10h], esi
0x18001edd5  mov     rbx, cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA; COInetSession * g_pCOInetSession
0x18001eddc  lea     rcx, ?g_mxsOInet@@3VCMutexSem@@A; lpCriticalSection
0x18001ede3  call    cs:__imp_LeaveCriticalSection
0x18001edea  nop     dword ptr [rax+rax+00h]
0x18001edef  test    r14d, r14d
0x18001edf2  jnz     short loc_18001EE39
0x18001edf4  test    rbx, rbx
0x18001edf7  jz      short loc_18001EE35
0x18001edf9  lea     r8d, [r14+10h]; Size
0x18001edfd  lea     rdx, IID_IInternetProtocolInfo; Buf2
0x18001ee04  lea     rcx, _GUID_79eac9ec_baf9_11ce_8c82_00aa004ba90b; Buf1
0x18001ee0b  call    memcmp_0
0x18001ee10  test    eax, eax
0x18001ee12  jz      loc_18001F6A3
0x18001ee18  lea     r8, [rsp+1560h+ppv]; void **
0x18001ee1d  mov     rcx, rbx; this
0x18001ee20  lea     rdx, _GUID_79eac9ec_baf9_11ce_8c82_00aa004ba90b; struct _GUID *
0x18001ee27  call    ?QueryInterface@COInetSession@@UEAAJAEBU_GUID@@PEAPEAX@Z; COInetSession::QueryInterface(_GUID const &,void * *)
0x18001ee2c  test    eax, eax
0x18001ee2e  jnz     short loc_18001EE35
0x18001ee30  mov     rdi, [rsp+1560h+ppv]
0x18001ee35  lock dec dword ptr [rbx+10h]
0x18001ee39  mov     rcx, qword ptr [rsp+1560h+Buf1.Data1]
0x18001ee3e  lea     r9, [rsp+1560h+var_1508]
0x18001ee43  mov     [rsp+1560h+var_1528], r12d
0x18001ee48  mov     r8d, 10000h
0x18001ee4e  mov     [rsp+1560h+dwReserved], r12d
0x18001ee53  mov     rdx, r15
0x18001ee56  mov     [rsp+1560h+pcchResult], rdi
0x18001ee5b  mov     qword ptr [rsp+1560h+cchResult], r12
0x18001ee60  call    cs:__imp_PrivateCoInternetCombineIUri
0x18001ee67  nop     dword ptr [rax+rax+00h]
0x18001ee6c  mov     ebx, eax
0x18001ee6e  test    rdi, rdi
0x18001ee71  jz      short loc_18001EE82
0x18001ee73  mov     rax, [rdi]
0x18001ee76  mov     rcx, rdi
0x18001ee79  mov     rax, [rax+10h]
0x18001ee7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee82  mov     rcx, [rsp+1560h+var_1520]
0x18001ee87  test    rcx, rcx
0x18001ee8a  jz      short loc_18001EE98
0x18001ee8c  mov     rax, [rcx]
0x18001ee8f  mov     rax, [rax+10h]
0x18001ee93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee98  test    ebx, ebx
0x18001ee9a  js      loc_18001EF87
0x18001eea0  mov     rdi, qword ptr [rsp+1560h+var_1508]
0x18001eea5  mov     r14d, r12d
0x18001eea8  cmp     rdi, [rbp+1460h+var_10C8]
0x18001eeaf  mov     r15d, r12d
0x18001eeb2  mov     ebx, r12d
0x18001eeb5  setnz   r14b
0x18001eeb9  cmp     [rbp+1460h+var_10C0], r12d
0x18001eec0  setnz   r15b
0x18001eec4  test    r14d, r14d
0x18001eec7  jz      loc_18001F688
0x18001eecd  mov     rcx, [rbp+1460h+bstrString]; bstrString
0x18001eed4  test    rcx, rcx
0x18001eed7  jnz     loc_18001F953
0x18001eedd  mov     [rbp+1460h+bstrString+8], r12
0x18001eee4  mov     [rbp+1460h+var_10A8], r12d
0x18001eeeb  test    r14d, r14d
0x18001eeee  jz      short loc_18001EF0F
0x18001eef0  mov     rcx, [rbp+1460h+var_10C8]
0x18001eef7  test    rcx, rcx
0x18001eefa  jz      short loc_18001EF0F
0x18001eefc  mov     rax, [rcx]
0x18001eeff  mov     rax, [rax+10h]
0x18001ef03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef08  mov     [rbp+1460h+var_10C8], r12
0x18001ef0f  mov     [rbp+1460h+var_10C0], r12d
0x18001ef16  test    rdi, rdi
0x18001ef19  jnz     loc_18001F550
0x18001ef1f  test    ebx, ebx
0x18001ef21  js      short loc_18001EF87
0x18001ef23  mov     edx, 825h
0x18001ef28  cmp     [rbp+1460h+var_10A8], edx
0x18001ef2e  jnb     loc_18001F83A
0x18001ef34  mov     ecx, [rbp+1460h+var_10A8]
0x18001ef3a  lea     rax, [rbp+1460h+pszStr1]
0x18001ef41  mov     r8, [rbp+1460h+bstrString+8]
0x18001ef48  test    rcx, rcx
0x18001ef4b  jz      short loc_18001EF6B
0x18001ef4d  movzx   r9d, word ptr [r8]
0x18001ef51  test    r9w, r9w
0x18001ef55  jz      short loc_18001EF6B
0x18001ef57  mov     [rax], r9w
0x18001ef5b  add     r8, 2
0x18001ef5f  add     rax, 2
0x18001ef63  sub     rcx, rsi
0x18001ef66  sub     rdx, rsi
0x18001ef69  jnz     short loc_18001EF48
0x18001ef6b  test    rdx, rdx
0x18001ef6e  lea     rcx, [rax-2]
0x18001ef72  cmovnz  rcx, rax
0x18001ef76  neg     rdx
0x18001ef79  sbb     ebx, ebx
0x18001ef7b  not     ebx
0x18001ef7d  and     ebx, 8007007Ah
0x18001ef83  mov     [rcx], r12w
0x18001ef87  mov     rcx, [rsp+1560h+ppURI]
0x18001ef8c  test    rcx, rcx
0x18001ef8f  jz      short loc_18001EFA2
0x18001ef91  mov     rax, [rcx]
0x18001ef94  mov     rax, [rax+10h]
0x18001ef98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef9d  mov     [rsp+1560h+ppURI], r12
  ... truncated ...
```
