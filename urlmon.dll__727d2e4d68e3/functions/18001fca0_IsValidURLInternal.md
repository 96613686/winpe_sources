# IsValidURLInternal

- ea: `0x18001fca0`
- end: `0x180020edf`
- name: `IsValidURLInternal`
- size: `4671`
- prototype: `__int64 __fastcall(struct IBindCtx *, const WCHAR *, __int64, int)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800f1c30`

## callees

- `0x180018bfc`
- `0x18001c0c0`
- `0x18001db50`
- `0x18001db94`
- `0x18001e580`
- `0x18001fc10`
- `0x18001fca0`
- `0x180020ee8`
- `0x180024e2c`
- `0x18002d6a0`
- `0x180031480`
- `0x1800490d0`
- `0x1800830ec`
- `0x1800a5e20`
- `0x1801285e6`
- `0x180128660`
- `0x180128720`
- `0x180129010`

## import_xrefs

- `msvcrt!wcschr` at `0x1800207fc`
- `msvcrt!wcschr` at `0x1800207fc`
- `iertutil!CreateUri` at `0x18001ff80`
- `iertutil!CreateUri` at `0x1800200d3`
- `iertutil!CreateUri` at `0x18001ff80`
- `iertutil!CreateUri` at `0x1800200d3`
- `iertutil!PrivateCoInternetCombineIUri` at `0x1800201bb`
- `iertutil!PrivateCoInternetCombineIUri` at `0x1800201bb`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180020ad1`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180020b00`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180020ad1`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180020b00`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x18001fe4c`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x18001ffa7`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x18001fe4c`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x18001ffa7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020137`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020468`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020713`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020767`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002092e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020137`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020468`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020713`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020767`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002092e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020106`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020438`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020870`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020106`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020438`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020870`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800204b4`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800204b4`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020a46`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020a46`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001fe9e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001fec7`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001ff06`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001fff1`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002001a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180020058`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001fe9e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001fec7`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001ff06`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001fff1`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002001a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180020058`
- `api-ms-win-core-atoms-l1-1-0!AddAtomW` at `0x180020aa7`
- `api-ms-win-core-atoms-l1-1-0!AddAtomW` at `0x180020aa7`
- `api-ms-win-core-atoms-l1-1-0!FindAtomW` at `0x18002088f`
- `api-ms-win-core-atoms-l1-1-0!FindAtomW` at `0x18002088f`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180020e2c`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180020e2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020c70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020c7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020d67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020c70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020c7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020d67`
- `OLEAUT32!__imp_SysFreeString` at `0x180020ce5`
- `OLEAUT32!__imp_SysFreeString` at `0x180020d45`
- `OLEAUT32!__imp_SysFreeString` at `0x180020ce5`
- `OLEAUT32!__imp_SysFreeString` at `0x180020d45`
- `OLEAUT32!__imp_SysStringLen` at `0x180020d2e`
- `OLEAUT32!__imp_SysStringLen` at `0x180020d2e`

## pseudocode

```c
__int64 __fastcall IsValidURLInternal(struct IBindCtx *a1, const WCHAR *a2, __int64 a3, int a4)
{
  unsigned int v4; // edi
  unsigned int v5; // eax
  struct IBindCtx *v7; // r15
  const WCHAR *v9; // r14
  int v10; // r12d
  UINT v11; // r15d
  bool ShouldUseEdge; // di
  int v13; // esi
  int v14; // ebx
  DWORD v15; // edx
  HRESULT v16; // ebx
  IUri *v17; // r15
  LPVOID v18; // rdi
  bool v19; // bl
  DWORD v20; // edx
  IUri *v21; // rbx
  COInetSession *v22; // rax
  int v23; // r14d
  volatile signed __int32 *v24; // rsi
  int v25; // eax
  __int64 v26; // rcx
  struct IUri *v27; // rsi
  BOOL v28; // edi
  BOOL v29; // r14d
  __int64 v30; // r8
  BSTR v31; // rdx
  WCHAR *v32; // r9
  __int64 v33; // rcx
  WCHAR *v34; // rcx
  BOOL v35; // edi
  unsigned int v36; // ebx
  int v37; // ebx
  __int64 v38; // rax
  int v39; // r14d
  COInetSession *v40; // rax
  int v41; // ebx
  COInetSession *v42; // rsi
  int i; // ebx
  __int64 v44; // rdi
  WCHAR v45; // cx
  int v46; // r8d
  int j; // edx
  __int64 v48; // rax
  struct IUriVtbl *lpVtbl; // rax
  int v50; // ebx
  COInetSession *v51; // rax
  COInetSession *v52; // rax
  WCHAR *v53; // rdx
  wchar_t *v54; // r8
  HRESULT ClassObject; // r13d
  __int64 v56; // rcx
  __int64 v57; // r9
  wchar_t *v58; // rcx
  wchar_t *v59; // rax
  ATOM AtomW; // cx
  __int64 v61; // rax
  IID *v62; // rax
  __int64 v63; // rcx
  unsigned int v64; // ecx
  IID *KnownOInetProtocolClsID; // rax
  unsigned int v66; // ecx
  char *v67; // rbx
  __int64 (__fastcall ***v68)(CEasyClassFactory *__hidden, const struct _GUID *, void **); // rcx
  __int64 k; // r14
  ATOM v70; // ax
  unsigned int v71; // r15d
  unsigned int v72; // r14d
  ATOM m; // r12
  int IsFeatureEnabledInternal; // ecx
  int v75; // ecx
  LPVOID *v76; // rax
  LPVOID *v77; // r14
  unsigned int n; // r14d
  __int64 v79; // rdi
  const void *v80; // rdx
  _QWORD *v81; // rax
  _QWORD *v82; // rcx
  struct _GUID v83; // xmm0
  unsigned int v84; // esi
  struct IUri *v85; // rdx
  __int64 v86; // r8
  const unsigned __int16 *v87; // rbx
  UINT v88; // [rsp+40h] [rbp-C0h]
  IUri *v89; // [rsp+48h] [rbp-B8h] BYREF
  IUri *ppURI; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v91; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR pwzURI; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v93; // [rsp+68h] [rbp-98h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-90h] BYREF
  struct IUri *v95; // [rsp+78h] [rbp-88h] BYREF
  int v96; // [rsp+80h] [rbp-80h]
  struct IBindCtx *v97; // [rsp+88h] [rbp-78h]
  const WCHAR *v98; // [rsp+90h] [rbp-70h]
  IID Buf1; // [rsp+98h] [rbp-68h] BYREF
  struct _GUID v100[64]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t Str[4]; // [rsp+4B0h] [rbp+3B0h] BYREF
  struct IUri *v102; // [rsp+4B8h] [rbp+3B8h]
  unsigned int v103; // [rsp+4C0h] [rbp+3C0h]
  BSTR bstrString[2]; // [rsp+4C8h] [rbp+3C8h] BYREF
  UINT v105[6]; // [rsp+4D8h] [rbp+3D8h] BYREF
  WCHAR pszStr1[2088]; // [rsp+4F0h] [rbp+3F0h] BYREF

  v4 = 0;
  v96 = a4;
  v5 = 0;
  LODWORD(ppURI) = 0;
  v98 = a2;
  v7 = a1;
  v97 = a1;
  if ( a2 )
  {
    v91 = 0;
    v93 = 0;
    pwzURI = 0;
    pszStr1[0] = 0;
    if ( a1 )
    {
      if ( ((unsigned int (__fastcall *)(struct IBindCtx *, const wchar_t *, LPVOID *))a1->lpVtbl->GetObjectParam)(
             a1,
             L"URL Context",
             &v93) )
      {
        v93 = 0;
      }
      else if ( v93 )
      {
        (*(void (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)v93 + 176LL))(v93, &v91);
        if ( v91 == 6 )
          (*(void (__fastcall **)(LPVOID, struct IBindCtx *, _QWORD, LPCWSTR *))(*(_QWORD *)v93 + 160LL))(
            v93,
            v7,
            0,
            &pwzURI);
      }
    }
    v9 = pwzURI;
    v10 = -2147024882;
    if ( !pwzURI )
    {
      LODWORD(ppURI) = 2085;
      v36 = (unsigned int)CoInternetParseUrl(a2, PARSE_CANONICALIZE, 0x10000u, pszStr1, 0x825u, (DWORD *)&ppURI, 0) >> 31;
      v88 = (unsigned int)ppURI;
      goto LABEL_103;
    }
    v102 = 0;
    *(_QWORD *)Str = &CUString::`vftable';
    *(_OWORD *)bstrString = 0;
    v103 = 11;
    v11 = 0;
    v105[0] = 0;
    ppURI = 0;
    v95 = 0;
    v88 = 0;
    ShouldUseEdge = InternalForkingSupport_ShouldUseEdge();
    v13 = 50342821;
    if ( !ShouldUseEdge )
    {
LABEL_17:
      v14 = 33565605;
      if ( !ShouldUseEdge )
        goto LABEL_21;
      goto LABEL_18;
    }
    v14 = 50342821;
    if ( FCK::FEATURE_DISABLE_DATAURI_SUPPORT )
    {
      IsFeatureEnabledInternal = CoInternetIsFeatureEnabledInternal();
      if ( IsFeatureEnabledInternal < 0 )
        goto LABEL_18;
      dword_180166BE8 = IsFeatureEnabledInternal == 0;
      FCK::FEATURE_DISABLE_DATAURI_SUPPORT = 0;
    }
    if ( dword_180166BE8 )
      goto LABEL_17;
LABEL_18:
    InitOnceExecuteOnce(&stru_18016AF28, GlobalInitOnceUrlMon, 0, 0);
    if ( (dword_18016B858 & 1) != 0 )
    {
      InitOnceExecuteOnce(&stru_18016AF28, GlobalInitOnceUrlMon, 0, 0);
      if ( (dword_18016B858 & 2) != 0 || (unsigned int)IsABrowserApp() )
      {
LABEL_22:
        InitOnceExecuteOnce(&stru_18016AF28, GlobalInitOnceUrlMon, 0, 0);
        if ( (dword_18016B858 & 4) != 0 )
        {
LABEL_23:
          if ( (v14 & 0x110) == 0 )
            v14 |= 0x100u;
          v15 = v14 | 0x80;
          if ( (v14 & 0xC0) != 0 )
            v15 = v14;
          if ( (v15 & 0x600) == 0 )
            v15 |= 0x200u;
          if ( (v15 & 0x1800) == 0 )
            v15 |= 0x800u;
          if ( (v15 & 0x6000) == 0 )
            v15 |= 0x2000u;
          if ( (v15 & 0x2000000) == 0 )
            v15 |= 0x2000000u;
          if ( (v15 & 0x1000000) == 0 )
            v15 |= 0x1000000u;
          v16 = CreateUri(v9, v15, 0, &ppURI);
          if ( v16 < 0 )
            goto LABEL_92;
          v17 = ppURI;
          v18 = 0;
          v89 = 0;
          v95 = 0;
          v19 = InternalForkingSupport_ShouldUseEdge();
          if ( !v19 )
            goto LABEL_41;
          if ( FCK::FEATURE_DISABLE_DATAURI_SUPPORT )
          {
            v75 = CoInternetIsFeatureEnabledInternal();
            if ( v75 < 0 )
              goto LABEL_42;
            dword_180166BE8 = v75 == 0;
            FCK::FEATURE_DISABLE_DATAURI_SUPPORT = 0;
          }
          if ( dword_180166BE8 )
          {
LABEL_41:
            v13 = 33565605;
            if ( !v19 )
            {
LABEL_45:
              v13 &= ~0x2000000u;
              if ( !v19 )
              {
LABEL_174:
                v13 &= ~0x8000000u;
LABEL_47:
                if ( (v13 & 0x110) == 0 )
                  v13 |= 0x100u;
                v20 = v13 | 0x80;
                if ( (v13 & 0xC0) != 0 )
                  v20 = v13;
                if ( (v20 & 0x600) == 0 )
                  v20 |= 0x200u;
                if ( (v20 & 0x1800) == 0 )
                  v20 |= 0x800u;
                if ( (v20 & 0x6000) == 0 )
                  v20 |= 0x2000u;
                if ( (v20 & 0x2000000) == 0 )
                  v20 |= 0x2000000u;
                if ( (v20 & 0x1000000) == 0 )
                  v20 |= 0x1000000u;
                v16 = CreateUri(a2, v20, 0, &v89);
                if ( v16 < 0 )
                {
LABEL_73:
                  if ( v89 )
                    ((void (__fastcall *)(IUri *))v89->lpVtbl->Release)(v89);
                  if ( v16 >= 0 )
                  {
                    v27 = v95;
                    v16 = 0;
                    v28 = v95 != v102;
                    v29 = v103 != 0;
                    if ( v95 != v102 || v103 )
                    {
                      if ( bstrString[0] )
                      {
                        SysFreeString(bstrString[0]);
                        bstrString[0] = 0;
                      }
                      bstrString[1] = 0;
                      v105[0] = 0;
                      if ( v28 && v102 )
                      {
                        ((void (__fastcall *)(struct IUri *))v102->lpVtbl->Release)(v102);
                        v102 = 0;
                      }
                    }
                    v103 = 0;
                    if ( !v27 || !v29 && !v28 )
                      goto LABEL_83;
                    lpVtbl = v27->lpVtbl;
                    v89 = 0;
                    if ( ((int (__fastcall *)(struct IUri *, GUID *, IUri **))lpVtbl->QueryInterface)(
                           v27,
                           &GUID_50295b0c_6b79_4935_aed8_05d80ec86a60,
                           &v89) < 0 )
                    {
                      v16 = ((__int64 (__fastcall *)(struct IUri *, _QWORD, BSTR *, _QWORD))v27->lpVtbl->GetPropertyBSTR)(
                              v27,
                              v103,
                              bstrString,
                              0);
                      if ( v16 >= 0 )
                      {
                        bstrString[1] = bstrString[0];
                        v105[0] = SysStringLen(bstrString[0]);
                      }
                    }
                    else
                    {
                      v16 = ((__int64 (__fastcall *)(IUri *, _QWORD, BSTR *, UINT *))v89->lpVtbl[1].QueryInterface)(
                              v89,
                              v103,
                              &bstrString[1],
                              v105);
                      ((void (__fastcall *)(IUri *))v89->lpVtbl->Release)(v89);
                    }
                    if ( v28 && v16 >= 0 )
                    {
                      v102 = v27;
                      ((void (__fastcall *)(struct IUri *))v27->lpVtbl->AddRef)(v27);
                    }
                    if ( v16 == 1 && (v16 = CUString::Set((CUString *)Str, v95, Uri_PROPERTY_RAW_URI), v16 == 1) )
                    {
                      v16 = -2146697214;
                    }
                    else
                    {
LABEL_83:
                      if ( v16 >= 0 )
                      {
                        v11 = v105[0];
                        v30 = 2085;
                        v88 = v105[0];
                        if ( v105[0] >= 0x825 )
                        {
                          v11 = v105[0] + 1;
                          v16 = -2147467261;
                          v88 = v105[0] + 1;
                        }
                        else
                        {
                          v31 = bstrString[1];
                          v32 = pszStr1;
                          v33 = v105[0];
                          do
                          {
                            if ( !v33 )
                              break;
                            if ( !*v31 )
                              break;
                            *v32++ = *v31++;
                            --v33;
                            --v30;
                          }
                          while ( v30 );
                          v34 = v32 - 1;
                          v16 = -2147024774;
                          if ( v30 )
                          {
                            v34 = v32;
                            v16 = 0;
                          }
                          *v34 = 0;
                        }
                        goto LABEL_92;
                      }
                    }
                  }
LABEL_139:
                  v11 = 0;
LABEL_92:
                  if ( ppURI )
                  {
                    ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
                    ppURI = 0;
                  }
                  if ( v95 )
                  {
                    ((void (__fastcall *)(struct IUri *))v95->lpVtbl->Release)(v95);
                    v95 = 0;
                  }
                  *(_QWORD *)Str = &CUString::`vftable';
                  v35 = v102 != 0;
                  if ( v102 || v103 != 11 )
                  {
                    if ( bstrString[0] )
                    {
                      SysFreeString(bstrString[0]);
                      bstrString[0] = 0;
                    }
                    bstrString[1] = 0;
                    v105[0] = 0;
                    if ( v35 && v102 )
                      ((void (__fastcall *)(struct IUri *))v102->lpVtbl->Release)(v102);
                  }
                  v36 = (unsigned int)v16 >> 31;
                  LODWORD(ppURI) = v11;
                  v4 = 0;
                  v7 = v97;
LABEL_103:
                  if ( v36 )
                    goto LABEL_237;
                  v37 = 0;
                  v38 = -1;
                  do
                    ++v38;
                  while ( pszStr1[v38] );
                  if ( !v38 )
LABEL_237:
                    v37 = -2147221020;
                  if ( pwzURI )
                    CoTaskMemFree((LPVOID)pwzURI);
                  if ( v37 )
                    goto LABEL_151;
                  LODWORD(v95) = 0;
                  v89 = 0;
                  v39 = 0;
                  pwzURI = 0;
                  Buf1 = 0;
                  if ( v7
                    && ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, LPCWSTR *))v7->lpVtbl->GetObjectParam)(
                         v7,
                         L"_BSCB_Holder_",
                         &pwzURI) >= 0
                    && (v50 = (**(__int64 (__fastcall ***)(LPCWSTR, GUID *, IUri **))pwzURI)(
                                pwzURI,
                                &IID_IBindStatusCallback,
                                &v89),
                        (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)pwzURI + 16LL))(pwzURI),
                        v50 >= 0) )
                  {
                    pwzURI = 0;
                    if ( ((__int64 (__fastcall *)(IUri *, GUID *, LPCWSTR *))v89->lpVtbl->QueryInterface)(
                           v89,
                           &IID_IServiceProvider,
                           &pwzURI) >= 0 )
                    {
                      ppv = 0;
                      if ( (*(int (__fastcall **)(LPCWSTR, GUID *, GUID *, LPVOID *))(*(_QWORD *)pwzURI + 24LL))(
                             pwzURI,
                             &IID_IInternetProtocol,
                             &IID_IInternetProtocol,
                             &ppv) >= 0
                        && ppv )
                      {
                        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
                        v39 = 1;
                        LODWORD(v95) = 1;
                      }
                      (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)pwzURI + 16LL))(pwzURI);
                    }
                    ((void (__fastcall *)(IUri *))v89->lpVtbl->Release)(v89);
                    if ( v39 )
                      goto LABEL_9;
                  }
                  else
                  {
                    v89 = 0;
                  }
                  EnterCriticalSection(&g_mxsOInet);
                  v40 = g_pCOInetSession;
                  if ( g_pCOInetSession )
                  {
                    v41 = 0;
                  }
                  else
                  {
                    v51 = (COInetSession *)operator new(0x180u);
                    if ( v51 && (v40 = COInetSession::COInetSession(v51)) != 0 )
                    {
                      v41 = 0;
                      g_pCOInetSession = v40;
                    }
                    else
                    {
                      v40 = g_pCOInetSession;
                      v41 = -2147024882;
                    }
                    if ( !v40 )
                    {
                      LeaveCriticalSection(&g_mxsOInet);
                      goto LABEL_151;
                    }
                  }
                  _InterlockedIncrement((volatile signed __int32 *)v40 + 4);
                  v42 = g_pCOInetSession;
                  LeaveCriticalSection(&g_mxsOInet);
                  if ( !v41 )
                  {
                    for ( i = 0; i < 12; ++i )
                    {
                      v44 = 10LL * i;
                      if ( !StrCmpNICW(pszStr1, *(LPCWSTR *)((char *)&off_18012A010 + v44 * 4), dword_18012A030[v44]) )
                      {
                        v45 = pszStr1[dword_18012A030[v44]];
                        if ( v45 == 58 || !v45 )
                        {
                          v46 = dword_18012A020[v44];
                          if ( v46 )
                          {
                            v4 = 0;
                            for ( j = 0; j < 12; ++j )
                            {
                              v48 = 10LL * j;
                              if ( v46 == dword_18012A020[v48] )
                              {
                                Buf1 = **(GUID **)((char *)&off_18012A028 + v48 * 4);
                                goto LABEL_125;
                              }
                            }
                            Buf1 = (IID)MEMORY[0];
                            _InterlockedDecrement((volatile signed __int32 *)v42 + 4);
                            goto LABEL_9;
                          }
                          break;
                        }
                      }
                    }
                    v4 = 0;
                    v53 = pszStr1;
                    v93 = 0;
                    v54 = Str;
                    ClassObject = -2146697203;
                    v56 = 31;
                    v57 = 32;
                    do
                    {
                      if ( !v56 )
                        break;
                      if ( !*v53 )
                        break;
                      *v54++ = *v53++;
                      --v56;
                      --v57;
                    }
                    while ( v57 );
                    v58 = v54 - 1;
                    if ( v57 )
                      v58 = v54;
                    *v58 = 0;
                    v59 = wcschr(Str, 0x3Au);
                    if ( !v59 )
                      goto LABEL_168;
                    *v59 = 0;
                    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v42 + 112));
                    *((_QWORD *)v42 + 20) = 0;
                    if ( *((int *)v42 + 27) > 0 )
                    {
                      AtomW = FindAtomW(Str);
                      if ( AtomW )
                      {
                        v61 = *((_QWORD *)v42 + 19);
                        for ( *((_QWORD *)v42 + 20) = v61; v61; *((_QWORD *)v42 + 20) = v61 )
                        {
                          if ( *(_WORD *)v61 == AtomW )
                            break;
                          v61 = *(_QWORD *)(v61 + 32);
                        }
                      }
                    }
                    if ( !*((_QWORD *)v42 + 20) )
                    {
                      for ( k = *((_QWORD *)v42 + 21); k; k = *(_QWORD *)(k + 8) )
                      {
                        if ( !StrCmpICW(Str, *(LPCWSTR *)k) )
                        {
                          v10 = 1;
                          goto LABEL_202;
                        }
                      }
                      v76 = (LPVOID *)operator new(0x10u);
                      v77 = v76;
                      if ( v76 )
                      {
                        *v76 = 0;
                        v76[1] = 0;
                        if ( CProtocolData::Init((CProtocolData *)v76, Str, *((struct CProtocolData **)v42 + 21)) )
                        {
                          *((_QWORD *)v42 + 21) = v77;
                          v10 = 0;
                        }
                        else
                        {
                          if ( *v77 )
                            CoTaskMemFree(*v77);
                          CoTaskMemFree(v77);
                        }
                      }
LABEL_202:
                      if ( !v10 )
                      {
                        v91 = 64;
                        ClassObject = CProtMgrNameSpace::LookupClsIDFromReg(
                                        (COInetSession *)((char *)v42 + 96),
                                        Str,
                                        v100,
                                        &v91,
                                        0,
                                        0);
                        if ( !ClassObject )
                        {
                          v70 = AddAtomW(Str);
                          v71 = v91;
                          v72 = 0;
                          for ( m = v70; v72 < v71; ++v72 )
                          {
                            v81 = operator new(0x38u);
                            v82 = v81;
                            if ( v81 )
                            {
                              *(_WORD *)v81 = m;
                              v83 = v100[v72];
                              v81[1] = 0;
                              v81[5] = 0;
                              *((struct _GUID *)v81 + 1) = v83;
                              v81[6] = 0;
                              v81[4] = *((_QWORD *)v42 + 19);
                              *((_QWORD *)v42 + 19) = v81;
                              _InterlockedIncrement((volatile signed __int32 *)v42 + 27);
                            }
                            else
                            {
                              v82 = 0;
                            }
                            if ( !*((_QWORD *)v42 + 20) )
                              *((_QWORD *)v42 + 20) = v82;
                          }
                          v7 = v97;
                        }
                      }
                    }
                    v62 = (IID *)*((_QWORD *)v42 + 20);
                    if ( v62 )
                    {
                      Buf1 = v62[1];
                      v63 = *((_QWORD *)v42 + 20);
                      if ( *(_QWORD *)(v63 + 8) )
                      {
                        v93 = *(LPVOID *)(v63 + 8);
                        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v63 + 8) + 8LL))(*(_QWORD *)(v63 + 8));
                        ClassObject = 0;
                      }
                      else
                      {
                        ppv = 0;
                        ClassObject = CoGetClassObject(&Buf1, 1u, 0, &IID_IClassFactory, &ppv);
                        if ( !ClassObject )
                          v93 = ppv;
                      }
                      *((_QWORD *)v42 + 20) = *(_QWORD *)(*((_QWORD *)v42 + 20) + 32LL);
                    }
                    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v42 + 112));
                    if ( !ClassObject )
                      goto LABEL_191;
                    v64 = IsKnownProtocol(Str);
                    if ( v64 )
                    {
                      KnownOInetProtocolClsID = (IID *)GetKnownOInetProtocolClsID(v64);
                      v67 = (char *)v42 + 16 * v66;
                      Buf1 = *KnownOInetProtocolClsID;
                      v68 = (__int64 (__fastcall ***)(CEasyClassFactory *__hidden, const struct _GUID *, void **))*((_QWORD *)v67 + 33);
                      if ( v68 )
                      {
LABEL_190:
                        v93 = v68;
                        ((void (__fastcall *)(__int64 (__fastcall ***)(CEasyClassFactory *__hidden, const struct _GUID *, void **)))(*v68)[1])(v68);
                        v4 = 0;
LABEL_191:
                        ClassObject = 0;
LABEL_193:
                        v39 = (int)v95;
LABEL_168:
                        if ( v93 )
                          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v93 + 16LL))(v93);
                        if ( ClassObject
                          && (ClassObject == -2146697202
                           || (*(unsigned int (__fastcall **)(__int64, WCHAR *, IID *, _QWORD, _QWORD, _DWORD))(*((_QWORD *)v42 + 3) + 16LL))(
                                (__int64)v42 + 24,
                                pszStr1,
                                &Buf1,
                                0,
                                0,
                                0)) )
                        {
                          _InterlockedDecrement((volatile signed __int32 *)v42 + 4);
                          if ( !v39 )
                            goto LABEL_151;
                        }
                        else
                        {
LABEL_125:
                          _InterlockedDecrement((volatile signed __int32 *)v42 + 4);
                        }
                        goto LABEL_9;
                      }
                      if ( !memcmp_0(&GUID_00000001_0000_0000_c000_000000000046, &IID_IClassFactory, 0x10u)
                        || !memcmp_0(&GUID_00000001_0000_0000_c000_000000000046, &IID_IUnknown, 0x10u) )
                      {
                        for ( n = 0; ; ++n )
                        {
                          v79 = 4LL * n;
                          v80 = *(const void **)((char *)&off_18012D4B8 + v79 * 8);
                          if ( !v80 )
                            break;
                          if ( !memcmp_0(&Buf1, v80, 0x10u) )
                          {
                            _InterlockedIncrement((volatile signed __int32 *)&g_cRef);
                            v68 = &(&off_18012D4B0)[v79];
                            if ( !&(&off_18012D4B0)[v79] )
                              break;
                            if ( !_InterlockedCompareExchange64(
                                    (volatile signed __int64 *)v67 + 33,
                                    (signed __int64)v68,
                                    0) )
                            {
                              _InterlockedIncrement(&g_lCOInetSessionDllRefcount);
                              goto LABEL_190;
                            }
                            ((void (__fastcall *)(__int64 (__fastcall ***)(CEasyClassFactory *__hidden, const struct _GUID *, void **)))(*v68)[2])(v68);
                            v68 = (__int64 (__fastcall ***)(CEasyClassFactory *__hidden, const struct _GUID *, void **))*((_QWORD *)v67 + 33);
                            if ( v68 )
                              goto LABEL_190;
                            break;
                          }
                        }
                      }
                    }
                    ClassObject = (**((__int64 (__fastcall ***)(__int64, wchar_t *, LPVOID *, IID *))v42 + 3))(
                                    (__int64)v42 + 24,
                                    Str,
                                    &v93,
                                    &Buf1);
                    v4 = 0;
                    goto LABEL_193;
                  }
LABEL_151:
                  v4 = 1;
LABEL_9:
                  v5 = v88;
                  goto LABEL_10;
                }
                v21 = v89;
                if ( !v89 )
                {
                  v16 = -2147418113;
                  goto LABEL_139;
                }
                ppv = 0;
                EnterCriticalSection(&g_mxsOInet);
                v22 = g_pCOInetSession;
                if ( g_pCOInetSession )
                {
                  v23 = 0;
                }
                else
                {
                  v52 = (COInetSession *)operator new(0x180u);
                  if ( v52 && (v22 = COInetSession::COInetSession(v52)) != 0 )
                  {
                    v23 = 0;
                    g_pCOInetSession = v22;
                  }
                  else
                  {
                    v22 = g_pCOInetSession;
                    v23 = -2147024882;
                  }
                  if ( !v22 )
                  {
                    LeaveCriticalSection(&g_mxsOInet);
LABEL_71:
                    v16 = PrivateCoInternetCombineIUri(v17, v21, 0x10000, &v95, 0, v18, 0, 0);
                    if ( v18 )
                      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
                    goto LABEL_73;
                  }
                }
                _InterlockedIncrement((volatile signed __int32 *)v22 + 4);
                v24 = (volatile signed __int32 *)g_pCOInetSession;
                LeaveCriticalSection(&g_mxsOInet);
                if ( !v23 )
                {
                  if ( v24 )
                  {
                    if ( !memcmp_0(&GUID_79eac9ec_baf9_11ce_8c82_00aa004ba90b, &IID_IInternetProtocolInfo, 0x10u) )
                    {
                      v18 = (LPVOID)(v24 + 2);
                      v26 = (__int64)(v24 + 4);
                      _InterlockedIncrement(v24 + 4);
                    }
                    else
                    {
                      v25 = COInetSession::QueryInterface(
                              (COInetSession *)v24,
                              &GUID_79eac9ec_baf9_11ce_8c82_00aa004ba90b,
                              &ppv);
                      v26 = (__int64)(v24 + 4);
                      if ( !v25 )
                        v18 = ppv;
                    }
                  }
                  else
                  {
                    v26 = 16;
                  }
                  _InterlockedDecrement((volatile signed __int32 *)v26);
                }
                goto LABEL_71;
              }
LABEL_46:
              InitOnceExecuteOnce(&stru_18016AF28, GlobalInitOnceUrlMon, 0, 0);
              if ( (dword_18016B858 & 4) != 0 )
                goto LABEL_47;
              goto LABEL_174;
            }
          }
LABEL_42:
          InitOnceExecuteOnce(&stru_18016AF28, GlobalInitOnceUrlMon, 0, 0);
          if ( (dword_18016B858 & 1) != 0 )
          {
            InitOnceExecuteOnce(&stru_18016AF28, GlobalInitOnceUrlMon, 0, 0);
            if ( (dword_18016B858 & 2) != 0 || (unsigned int)IsABrowserApp() )
              goto LABEL_46;
          }
          goto LABEL_45;
        }
LABEL_173:
        v14 &= ~0x8000000u;
        goto LABEL_23;
      }
    }
LABEL_21:
    v14 &= ~0x2000000u;
    if ( !ShouldUseEdge )
      goto LABEL_173;
    goto LABEL_22;
  }
  v4 = -2147024809;
LABEL_10:
  if ( (v96 & 1) != 0 && v4 == 1 && v5 > 0x824 )
  {
    v84 = 2 * v5 + 2;
    ppv = operator new(saturated_mul(v84, 2u));
    v87 = (const unsigned __int16 *)ppv;
    if ( ppv && !(unsigned int)ConstructURL((__int64)v7, v85, v86, v98, (LPWSTR)ppv, v84, (DWORD *)&ppURI, 1u) )
      v4 = IsOInetProtocol(v7, v87) != 0;
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&ppv);
  }
  return v4;
}

```

## disassembly

```asm
0x18001fca0  push    rbp
0x18001fca2  push    rbx
0x18001fca3  push    rsi
0x18001fca4  push    rdi
0x18001fca5  push    r15
0x18001fca7  lea     rbp, [rsp-1460h]
0x18001fcaf  mov     eax, 1560h
0x18001fcb4  call    _alloca_probe
0x18001fcb9  sub     rsp, rax
0x18001fcbc  mov     rax, cs:__security_cookie
0x18001fcc3  xor     rax, rsp
0x18001fcc6  mov     [rbp+1480h+var_40], rax
0x18001fccd  xor     edi, edi
0x18001fccf  mov     [rsp+1580h+var_28], r13
0x18001fcd7  mov     [rbp+1480h+var_1500], r9d
0x18001fcdb  mov     eax, edi
0x18001fcdd  mov     dword ptr [rsp+1580h+ppURI], eax
0x18001fce1  mov     r13, rdx
0x18001fce4  mov     [rbp+1480h+var_14F0], rdx
0x18001fce8  mov     r15, rcx
0x18001fceb  mov     [rbp+1480h+var_14F8], rcx
0x18001fcef  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18001fcf6  test    rdx, rdx
0x18001fcf9  jz      short loc_18001FD53
0x18001fcfb  mov     [rsp+1580h+arg_10], r12
0x18001fd03  mov     [rsp+1580h+var_30], r14
0x18001fd0b  mov     [rsp+1580h+var_1528], edi
0x18001fd0f  mov     [rsp+1580h+var_1518], rdi
0x18001fd14  mov     [rsp+1580h+pwzURI], rdi
0x18001fd19  mov     [rbp+1480h+pszStr1], di
0x18001fd20  test    rcx, rcx
0x18001fd23  jz      loc_18001FDF7
0x18001fd29  mov     rax, [rcx]
0x18001fd2c  lea     r8, [rsp+1580h+var_1518]
0x18001fd31  lea     rdx, aUrlContext; "URL Context"
0x18001fd38  mov     rax, [rax+50h]
0x18001fd3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd41  test    eax, eax
0x18001fd43  jz      loc_18001FDE9
0x18001fd49  mov     [rsp+1580h+var_1518], rdi
0x18001fd4e  jmp     loc_18001FDF7
0x18001fd53  mov     edi, 80070057h
0x18001fd58  jmp     short loc_18001FDB7
0x18001fd5a  cmp     r13d, 800C000Eh
0x18001fd61  jz      short loc_18001FD96
0x18001fd63  mov     rax, [rsi+18h]
0x18001fd67  lea     rcx, [rsi+18h]
0x18001fd6b  mov     dword ptr [rsp+1580h+pcchResult], edi
0x18001fd6f  lea     r8, [rbp+1480h+Buf1]
0x18001fd73  xor     r9d, r9d
0x18001fd76  mov     qword ptr [rsp+1580h+cchResult], rdi
0x18001fd7b  lea     rdx, [rbp+1480h+pszStr1]
0x18001fd82  mov     rax, [rax+10h]
0x18001fd86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd8b  mov     r13d, eax
0x18001fd8e  test    eax, eax
0x18001fd90  jz      loc_180020528
0x18001fd96  lock dec dword ptr [rsi+10h]
0x18001fd9a  test    r14d, r14d
0x18001fd9d  jz      loc_18002071F
0x18001fda3  mov     eax, [rsp+1580h+var_1540]
0x18001fda7  mov     r12, [rsp+1580h+arg_10]
0x18001fdaf  mov     r14, [rsp+1580h+var_30]
0x18001fdb7  test    byte ptr [rbp+1480h+var_1500], 1
0x18001fdbb  mov     r13, [rsp+1580h+var_28]
0x18001fdc3  jnz     loc_180020E52
0x18001fdc9  mov     eax, edi
0x18001fdcb  mov     rcx, [rbp+1480h+var_40]
0x18001fdd2  xor     rcx, rsp; StackCookie
0x18001fdd5  call    __security_check_cookie
0x18001fdda  add     rsp, 1560h
0x18001fde1  pop     r15
0x18001fde3  pop     rdi
0x18001fde4  pop     rsi
0x18001fde5  pop     rbx
0x18001fde6  pop     rbp
0x18001fde7  retn
0x18001fde9  mov     rcx, [rsp+1580h+var_1518]
0x18001fdee  test    rcx, rcx
0x18001fdf1  jnz     loc_180020C90
0x18001fdf7  mov     r14, [rsp+1580h+pwzURI]
0x18001fdfc  mov     r12d, 8007000Eh
0x18001fe02  test    r14, r14
0x18001fe05  jz      loc_1800209BD
0x18001fe0b  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x18001fe12  mov     [rbp+1480h+var_10C8], rdi
0x18001fe19  xorps   xmm0, xmm0
0x18001fe1c  mov     qword ptr [rbp+1480h+Str], rax
0x18001fe23  movdqu  xmmword ptr [rbp+1480h+bstrString], xmm0
0x18001fe2b  mov     [rbp+1480h+var_10C0], 0Bh
0x18001fe35  mov     r15d, edi
0x18001fe38  mov     [rbp+1480h+var_10A8], edi
0x18001fe3e  mov     [rsp+1580h+ppURI], rdi
0x18001fe43  mov     [rsp+1580h+var_1508], rdi
0x18001fe48  mov     [rsp+1580h+var_1540], edi
0x18001fe4c  call    cs:__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ; InternalForkingSupport_ShouldUseEdge(void)
0x18001fe53  nop     dword ptr [rax+rax+00h]
0x18001fe58  movzx   edi, al
0x18001fe5b  mov     esi, 3002BA5h
0x18001fe60  test    al, al
0x18001fe62  jz      short loc_18001FE80
0x18001fe64  mov     rcx, cs:?FEATURE_DISABLE_DATAURI_SUPPORT@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_DISABLE_DATAURI_SUPPORT
0x18001fe6b  mov     ebx, esi
0x18001fe6d  test    rcx, rcx
0x18001fe70  jnz     loc_180020AD1
0x18001fe76  mov     eax, cs:dword_180166BE8
0x18001fe7c  test    eax, eax
0x18001fe7e  jz      short loc_18001FE8A
0x18001fe80  mov     ebx, 2002BA5h
0x18001fe85  test    dil, dil
0x18001fe88  jz      short loc_18001FEE5
0x18001fe8a  xor     r9d, r9d; Context
0x18001fe8d  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001fe94  xor     r8d, r8d; Parameter
0x18001fe97  lea     rcx, stru_18016AF28; InitOnce
0x18001fe9e  call    cs:__imp_InitOnceExecuteOnce
0x18001fea5  nop     dword ptr [rax+rax+00h]
0x18001feaa  test    byte ptr cs:dword_18016B858, 1
0x18001feb1  jz      short loc_18001FEE5
0x18001feb3  xor     r9d, r9d; Context
0x18001feb6  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001febd  xor     r8d, r8d; Parameter
0x18001fec0  lea     rcx, stru_18016AF28; InitOnce
0x18001fec7  call    cs:__imp_InitOnceExecuteOnce
0x18001fece  nop     dword ptr [rax+rax+00h]
0x18001fed3  test    byte ptr cs:dword_18016B858, 2
0x18001feda  jnz     short loc_18001FEF2
0x18001fedc  call    ?IsABrowserApp@@YAHXZ; IsABrowserApp(void)
0x18001fee1  test    eax, eax
0x18001fee3  jnz     short loc_18001FEF2
0x18001fee5  btr     ebx, 19h
0x18001fee9  test    dil, dil
0x18001feec  jz      loc_180020839
0x18001fef2  xor     r9d, r9d; Context
0x18001fef5  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001fefc  xor     r8d, r8d; Parameter
0x18001feff  lea     rcx, stru_18016AF28; InitOnce
0x18001ff06  call    cs:__imp_InitOnceExecuteOnce
0x18001ff0d  nop     dword ptr [rax+rax+00h]
0x18001ff12  test    byte ptr cs:dword_18016B858, 4
0x18001ff19  jz      loc_180020839
0x18001ff1f  mov     eax, ebx
0x18001ff21  bts     eax, 8
0x18001ff25  test    ebx, 110h
0x18001ff2b  cmovz   ebx, eax
0x18001ff2e  mov     edx, ebx
0x18001ff30  bts     edx, 7
0x18001ff34  test    bl, 0C0h
0x18001ff37  cmovnz  edx, ebx
0x18001ff3a  mov     eax, edx
0x18001ff3c  bts     eax, 9
0x18001ff40  test    edx, 600h
0x18001ff46  cmovz   edx, eax
0x18001ff49  test    edx, 1800h
0x18001ff4f  jnz     short loc_18001FF55
0x18001ff51  bts     edx, 0Bh
0x18001ff55  test    edx, 6000h
0x18001ff5b  jnz     short loc_18001FF61
0x18001ff5d  bts     edx, 0Dh
0x18001ff61  bt      edx, 19h
0x18001ff65  jb      short loc_18001FF6B
0x18001ff67  bts     edx, 19h
0x18001ff6b  bt      edx, 18h
0x18001ff6f  jb      short loc_18001FF75
0x18001ff71  bts     edx, 18h; dwFlags
0x18001ff75  lea     r9, [rsp+1580h+ppURI]; ppURI
0x18001ff7a  xor     r8d, r8d; dwReserved
0x18001ff7d  mov     rcx, r14; pwzURI
0x18001ff80  call    cs:__imp_CreateUri
0x18001ff87  nop     dword ptr [rax+rax+00h]
0x18001ff8c  mov     ebx, eax
0x18001ff8e  test    eax, eax
0x18001ff90  js      loc_1800202EA
0x18001ff96  mov     r15, [rsp+1580h+ppURI]
0x18001ff9b  xor     edi, edi
0x18001ff9d  mov     [rsp+1580h+var_1538], rdi
0x18001ffa2  mov     [rsp+1580h+var_1508], rdi
0x18001ffa7  call    cs:__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ; InternalForkingSupport_ShouldUseEdge(void)
0x18001ffae  nop     dword ptr [rax+rax+00h]
0x18001ffb3  movzx   ebx, al
0x18001ffb6  test    al, al
0x18001ffb8  jz      short loc_18001FFD4
0x18001ffba  mov     rcx, cs:?FEATURE_DISABLE_DATAURI_SUPPORT@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_DISABLE_DATAURI_SUPPORT
0x18001ffc1  test    rcx, rcx
0x18001ffc4  jnz     loc_180020B00
0x18001ffca  mov     eax, cs:dword_180166BE8
0x18001ffd0  test    eax, eax
0x18001ffd2  jz      short loc_18001FFDD
0x18001ffd4  mov     esi, 2002BA5h
0x18001ffd9  test    bl, bl
0x18001ffdb  jz      short loc_180020038
0x18001ffdd  xor     r9d, r9d; Context
0x18001ffe0  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001ffe7  xor     r8d, r8d; Parameter
0x18001ffea  lea     rcx, stru_18016AF28; InitOnce
0x18001fff1  call    cs:__imp_InitOnceExecuteOnce
0x18001fff8  nop     dword ptr [rax+rax+00h]
0x18001fffd  test    byte ptr cs:dword_18016B858, 1
0x180020004  jz      short loc_180020038
0x180020006  xor     r9d, r9d; Context
0x180020009  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180020010  xor     r8d, r8d; Parameter
0x180020013  lea     rcx, stru_18016AF28; InitOnce
0x18002001a  call    cs:__imp_InitOnceExecuteOnce
0x180020021  nop     dword ptr [rax+rax+00h]
0x180020026  test    byte ptr cs:dword_18016B858, 2
0x18002002d  jnz     short loc_180020044
0x18002002f  call    ?IsABrowserApp@@YAHXZ; IsABrowserApp(void)
0x180020034  test    eax, eax
0x180020036  jnz     short loc_180020044
0x180020038  btr     esi, 19h
0x18002003c  test    bl, bl
0x18002003e  jz      loc_180020842
0x180020044  xor     r9d, r9d; Context
0x180020047  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18002004e  xor     r8d, r8d; Parameter
0x180020051  lea     rcx, stru_18016AF28; InitOnce
0x180020058  call    cs:__imp_InitOnceExecuteOnce
0x18002005f  nop     dword ptr [rax+rax+00h]
0x180020064  test    byte ptr cs:dword_18016B858, 4
0x18002006b  jz      loc_180020842
0x180020071  mov     eax, esi
0x180020073  bts     eax, 8
0x180020077  test    esi, 110h
0x18002007d  cmovz   esi, eax
0x180020080  mov     edx, esi
0x180020082  bts     edx, 7
0x180020086  test    sil, 0C0h
0x18002008a  cmovnz  edx, esi
0x18002008d  mov     eax, edx
0x18002008f  bts     eax, 9
0x180020093  test    edx, 600h
0x180020099  cmovz   edx, eax
0x18002009c  test    edx, 1800h
0x1800200a2  jnz     short loc_1800200A8
0x1800200a4  bts     edx, 0Bh
0x1800200a8  test    edx, 6000h
0x1800200ae  jnz     short loc_1800200B4
0x1800200b0  bts     edx, 0Dh
0x1800200b4  bt      edx, 19h
0x1800200b8  jb      short loc_1800200BE
0x1800200ba  bts     edx, 19h
0x1800200be  bt      edx, 18h
0x1800200c2  jb      short loc_1800200C8
0x1800200c4  bts     edx, 18h; dwFlags
0x1800200c8  lea     r9, [rsp+1580h+var_1538]; ppURI
0x1800200cd  xor     r8d, r8d; dwReserved
0x1800200d0  mov     rcx, r13; pwzURI
0x1800200d3  call    cs:__imp_CreateUri
0x1800200da  nop     dword ptr [rax+rax+00h]
0x1800200df  mov     ebx, eax
0x1800200e1  test    eax, eax
0x1800200e3  js      loc_180020CDD
0x1800200e9  mov     rbx, [rsp+1580h+var_1538]
0x1800200ee  test    rbx, rbx
0x1800200f1  jz      loc_180020CD3
0x1800200f7  xor     r13d, r13d
0x1800200fa  lea     rcx, ?g_mxsOInet@@3VCMutexSem@@A; lpCriticalSection
0x180020101  mov     [rsp+1580h+ppv], r13
0x180020106  call    cs:__imp_EnterCriticalSection
0x18002010d  nop     dword ptr [rax+rax+00h]
0x180020112  mov     rax, cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA; COInetSession * g_pCOInetSession
0x180020119  test    rax, rax
0x18002011c  jz      loc_180020729
0x180020122  mov     r14d, r13d
0x180020125  lock inc dword ptr [rax+10h]
0x180020129  mov     rsi, cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA; COInetSession * g_pCOInetSession
0x180020130  lea     rcx, ?g_mxsOInet@@3VCMutexSem@@A; lpCriticalSection
0x180020137  call    cs:__imp_LeaveCriticalSection
0x18002013e  nop     dword ptr [rax+rax+00h]
0x180020143  test    r14d, r14d
0x180020146  jnz     short loc_180020196
0x180020148  test    rsi, rsi
0x18002014b  jz      loc_180020A1C
0x180020151  mov     r8d, 10h; Size
0x180020157  lea     rdx, IID_IInternetProtocolInfo; Buf2
0x18002015e  lea     rcx, _GUID_79eac9ec_baf9_11ce_8c82_00aa004ba90b; Buf1
0x180020165  call    memcmp_0
0x18002016a  test    eax, eax
0x18002016c  jz      loc_180020829
0x180020172  lea     r8, [rsp+1580h+ppv]; void **
0x180020177  mov     rcx, rsi; this
0x18002017a  lea     rdx, _GUID_79eac9ec_baf9_11ce_8c82_00aa004ba90b; struct _GUID *
0x180020181  call    ?QueryInterface@COInetSession@@UEAAJAEBU_GUID@@PEAPEAX@Z; COInetSession::QueryInterface(_GUID const &,void * *)
0x180020186  lea     rcx, [rsi+10h]
0x18002018a  test    eax, eax
0x18002018c  jnz     short loc_180020193
0x18002018e  mov     rdi, [rsp+1580h+ppv]
0x180020193  lock dec dword ptr [rcx]
0x180020196  mov     [rsp+1580h+var_1548], r13d
0x18002019b  lea     r9, [rsp+1580h+var_1508]
0x1800201a0  mov     [rsp+1580h+dwReserved], r13d
0x1800201a5  mov     r8d, 10000h
0x1800201ab  mov     [rsp+1580h+pcchResult], rdi
0x1800201b0  mov     rdx, rbx
0x1800201b3  mov     rcx, r15
0x1800201b6  mov     qword ptr [rsp+1580h+cchResult], r13
0x1800201bb  call    cs:__imp_PrivateCoInternetCombineIUri
0x1800201c2  nop     dword ptr [rax+rax+00h]
0x1800201c7  mov     ebx, eax
  ... truncated ...
```
