# ConstructURL

- ea: `0x180013c30`
- end: `0x1800145ee`
- name: `ConstructURL`
- size: `2494`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180017620`
- `0x18004eed0`

## callees

- `0x18001063c`
- `0x180013c30`
- `0x1800150e0`
- `0x18001511c`
- `0x180015fc0`
- `0x18001e160`
- `0x18009f200`
- `0x18011ba26`
- `0x18011c010`

## import_xrefs

- `iertutil!CreateUri` at `0x180014032`
- `iertutil!CreateUri` at `0x1800141a9`
- `iertutil!CreateUri` at `0x180014032`
- `iertutil!CreateUri` at `0x1800141a9`
- `iertutil!PrivateCoInternetCombineIUri` at `0x180014278`
- `iertutil!PrivateCoInternetCombineIUri` at `0x180014278`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x1800144b0`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x1800144db`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x1800144b0`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x1800144db`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x180013f1f`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x180014095`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x180013f1f`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x180014095`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800141ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014450`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800141ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014450`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800141d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800141d7`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180013f63`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180013f86`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180013fbf`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800140d9`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800140fc`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180014135`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180013f63`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180013f86`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180013fbf`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800140d9`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800140fc`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180014135`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800145d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800145d9`
- `OLEAUT32!__imp_SysFreeString` at `0x18001456d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800145c0`
- `OLEAUT32!__imp_SysFreeString` at `0x18001456d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800145c0`
- `OLEAUT32!__imp_SysStringLen` at `0x1800145a4`
- `OLEAUT32!__imp_SysStringLen` at `0x1800145a4`

## pseudocode

```c
__int64 __fastcall ConstructURL(
        __int64 a1,
        struct IUri *a2,
        __int64 a3,
        const WCHAR *a4,
        LPWSTR pszResult,
        unsigned int a6,
        DWORD *a7,
        DWORD pcchResult)
{
  char v8; // bl
  DWORD *v9; // r13
  DWORD v10; // esi
  DWORD v11; // r12d
  const WCHAR *v12; // r10
  WCHAR *v14; // r15
  DWORD cchResult; // r14d
  const WCHAR *v16; // rcx
  HRESULT v17; // ebx
  LPWSTR v18; // rcx
  BOOL v19; // edi
  __int64 v20; // rax
  unsigned int v21; // ebx
  __int64 v23; // rax
  __int64 v24; // rdx
  WCHAR *v25; // rcx
  __int64 v26; // rax
  const WCHAR *v27; // r15
  int v28; // r13d
  int v29; // ecx
  DWORD v30; // ebx
  bool ShouldUseEdge; // di
  DWORD v32; // edx
  int v33; // r15d
  unsigned int v34; // ebx
  bool v35; // di
  DWORD v36; // edx
  IUri *v37; // rbx
  LPCWSTR v38; // rdi
  COInetSession *v39; // rax
  volatile signed __int32 *v40; // rsi
  int Interface; // eax
  __int64 v42; // rcx
  struct IUri *v43; // rsi
  BOOL v44; // edi
  BOOL v45; // r15d
  DWORD v46; // esi
  BSTR v47; // rdx
  __int64 v48; // rax
  __int64 v49; // r8
  LPWSTR v50; // r9
  struct IUriVtbl *lpVtbl; // rax
  COInetSession *v52; // rax
  int IsFeatureEnabledInternal; // eax
  int v54; // eax
  __int64 v55; // [rsp+40h] [rbp-59h] BYREF
  IUri *ppURI; // [rsp+48h] [rbp-51h] BYREF
  IUri *v57; // [rsp+50h] [rbp-49h] BYREF
  LPCWSTR pwzURI; // [rsp+58h] [rbp-41h] BYREF
  IUri *v59; // [rsp+60h] [rbp-39h]
  void **v60; // [rsp+68h] [rbp-31h] BYREF
  struct IUri *v61; // [rsp+70h] [rbp-29h]
  unsigned int v62; // [rsp+78h] [rbp-21h]
  BSTR bstrString[2]; // [rsp+80h] [rbp-19h] BYREF
  UINT v64[16]; // [rsp+90h] [rbp-9h] BYREF
  struct IUri *v65; // [rsp+E8h] [rbp+4Fh] BYREF
  int v66; // [rsp+F0h] [rbp+57h] BYREF
  int v67; // [rsp+F4h] [rbp+5Bh]
  LPCWSTR v68; // [rsp+F8h] [rbp+5Fh] BYREF

  v68 = a4;
  v67 = HIDWORD(a3);
  v65 = a2;
  v8 = pcchResult;
  v9 = a7;
  v10 = pcchResult & 2;
  v66 = 0;
  v11 = 0;
  v55 = 0;
  pwzURI = 0;
  if ( (pcchResult & 2) == 0 )
    v11 = 0x10000;
  *a7 = 0;
  v12 = a4;
  if ( !a4 )
    return 2147942487LL;
  v14 = pszResult;
  if ( !pszResult )
    return 2147942487LL;
  cchResult = a6 >> 1;
  if ( a6 >> 1 < 0x824 )
    return 2147942487LL;
  *pszResult = 0;
  if ( !a1 )
  {
    a6 = 0;
    goto LABEL_8;
  }
  if ( (*(unsigned int (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)a1 + 80LL))(
         a1,
         L"URL Context",
         &v55) )
  {
    v55 = 0;
  }
  else if ( v55 )
  {
    (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v55 + 176LL))(v55, &v66);
    if ( v66 == 6 )
      (*(void (__fastcall **)(__int64, __int64, _QWORD, LPCWSTR *))(*(_QWORD *)v55 + 160LL))(v55, a1, 0, &pwzURI);
  }
  v27 = pwzURI;
  a6 = 0;
  if ( pwzURI )
  {
    v61 = 0;
    v62 = 11;
    v60 = &CUString::`vftable';
    v28 = 50342789;
    v64[0] = 0;
    v29 = 50342789;
    ppURI = 0;
    if ( !v10 )
      v29 = 50342821;
    v65 = 0;
    pcchResult = 0;
    *(_OWORD *)bstrString = 0;
    v30 = v29;
    ShouldUseEdge = InternalForkingSupport_ShouldUseEdge();
    if ( !ShouldUseEdge )
    {
LABEL_52:
      v30 &= ~0x1000000u;
      if ( !ShouldUseEdge )
        goto LABEL_56;
      goto LABEL_53;
    }
    if ( FCK::FEATURE_DISABLE_DATAURI_SUPPORT )
    {
      IsFeatureEnabledInternal = CoInternetIsFeatureEnabledInternal();
      if ( IsFeatureEnabledInternal < 0 )
        goto LABEL_53;
      dword_180159BE8 = IsFeatureEnabledInternal == 0;
      FCK::FEATURE_DISABLE_DATAURI_SUPPORT = 0;
    }
    if ( dword_180159BE8 )
      goto LABEL_52;
LABEL_53:
    InitOnceExecuteOnce(&stru_18015DE28, GlobalInitOnceUrlMon, 0, 0);
    if ( (dword_18015E75C & 1) != 0 )
    {
      InitOnceExecuteOnce(&stru_18015DE28, GlobalInitOnceUrlMon, 0, 0);
      if ( (dword_18015E75C & 2) != 0 || (unsigned int)IsABrowserApp() )
      {
LABEL_57:
        InitOnceExecuteOnce(&stru_18015DE28, GlobalInitOnceUrlMon, 0, 0);
        if ( (dword_18015E75C & 4) != 0 )
        {
LABEL_58:
          if ( (v30 & 0x110) == 0 )
            v30 |= 0x100u;
          v32 = v30 | 0x80;
          if ( (v30 & 0xC0) != 0 )
            v32 = v30;
          if ( (v32 & 0x600) == 0 )
            v32 |= 0x200u;
          if ( (v32 & 0x1800) == 0 )
            v32 |= 0x800u;
          if ( (v32 & 0x6000) == 0 )
            v32 |= 0x2000u;
          if ( (v32 & 0x2000000) == 0 )
            v32 |= 0x2000000u;
          if ( (v32 & 0x1000000) == 0 )
            v32 |= 0x1000000u;
          v17 = CreateUri(v27, v32, 0, &ppURI);
          if ( v17 < 0 )
            goto LABEL_159;
          v33 = 0;
          v59 = ppURI;
          v57 = 0;
          if ( !v10 )
            v28 = 50342821;
          v65 = 0;
          v34 = v28;
          v35 = InternalForkingSupport_ShouldUseEdge();
          if ( !v35 )
            goto LABEL_78;
          if ( FCK::FEATURE_DISABLE_DATAURI_SUPPORT )
          {
            v54 = CoInternetIsFeatureEnabledInternal();
            if ( v54 < 0 )
              goto LABEL_79;
            dword_180159BE8 = v54 == 0;
            FCK::FEATURE_DISABLE_DATAURI_SUPPORT = 0;
          }
          if ( dword_180159BE8 )
          {
LABEL_78:
            v34 = v28 & 0xFEFFFFFF;
            if ( !v35 )
            {
LABEL_82:
              v34 &= ~0x2000000u;
              if ( !v35 )
              {
LABEL_145:
                v34 &= ~0x8000000u;
LABEL_84:
                if ( (v34 & 0x110) == 0 )
                  v34 |= 0x100u;
                v36 = v34 | 0x80;
                if ( (v34 & 0xC0) != 0 )
                  v36 = v34;
                if ( (v36 & 0x600) == 0 )
                  v36 |= 0x200u;
                if ( (v36 & 0x1800) == 0 )
                  v36 |= 0x800u;
                if ( (v36 & 0x6000) == 0 )
                  v36 |= 0x2000u;
                if ( (v36 & 0x2000000) == 0 )
                  v36 |= 0x2000000u;
                if ( (v36 & 0x1000000) == 0 )
                  v36 |= 0x1000000u;
                v17 = CreateUri(v68, v36, 0, &v57);
                if ( v17 >= 0 )
                {
                  v37 = v57;
                  if ( !v57 )
                  {
                    v17 = -2147418113;
                    goto LABEL_159;
                  }
                  v38 = 0;
                  v68 = 0;
                  EnterCriticalSection(&g_mxsOInet);
                  v39 = g_pCOInetSession;
                  if ( g_pCOInetSession
                    || ((v52 = (COInetSession *)operator new(0x180u)) == 0
                     || (v39 = COInetSession::COInetSession(v52)) == 0
                      ? (COInetSession *)(v39 = g_pCOInetSession, v33 = -2147024882)
                      : (g_pCOInetSession = v39),
                        v39) )
                  {
                    _InterlockedIncrement((volatile signed __int32 *)v39 + 4);
                    v40 = (volatile signed __int32 *)g_pCOInetSession;
                    LeaveCriticalSection(&g_mxsOInet);
                    if ( !v33 )
                    {
                      if ( v40 )
                      {
                        if ( !memcmp_0(&GUID_79eac9ec_baf9_11ce_8c82_00aa004ba90b, &IID_IInternetProtocolInfo, 0x10u) )
                        {
                          v38 = (LPCWSTR)(v40 + 2);
                          v42 = (__int64)(v40 + 4);
                          _InterlockedIncrement(v40 + 4);
                        }
                        else
                        {
                          Interface = COInetSession::QueryInterface(
                                        (COInetSession *)v40,
                                        &GUID_79eac9ec_baf9_11ce_8c82_00aa004ba90b,
                                        (void **)&v68);
                          v42 = (__int64)(v40 + 4);
                          if ( !Interface )
                            v38 = v68;
                        }
                      }
                      else
                      {
                        v42 = 16;
                      }
                      _InterlockedDecrement((volatile signed __int32 *)v42);
                    }
                  }
                  else
                  {
                    LeaveCriticalSection(&g_mxsOInet);
                  }
                  v17 = PrivateCoInternetCombineIUri(v59, v37, v11, &v65, 0, v38, 0, 0);
                  if ( v38 )
                    (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)v38 + 16LL))(v38);
                }
                if ( v57 )
                  ((void (__fastcall *)(IUri *))v57->lpVtbl->Release)(v57);
                if ( v17 >= 0 )
                {
                  v43 = v65;
                  v17 = 0;
                  v44 = v65 != v61;
                  v45 = v62 != 0;
                  if ( v65 != v61 || v62 )
                  {
                    if ( bstrString[0] )
                    {
                      SysFreeString(bstrString[0]);
                      bstrString[0] = 0;
                    }
                    bstrString[1] = 0;
                    v64[0] = 0;
                    if ( v44 && v61 )
                    {
                      ((void (__fastcall *)(struct IUri *))v61->lpVtbl->Release)(v61);
                      v61 = 0;
                    }
                  }
                  v62 = 0;
                  if ( !v43 || !v45 && !v44 )
                    goto LABEL_119;
                  lpVtbl = v43->lpVtbl;
                  v68 = 0;
                  if ( ((int (__fastcall *)(struct IUri *, GUID *, LPCWSTR *))lpVtbl->QueryInterface)(
                         v43,
                         &GUID_50295b0c_6b79_4935_aed8_05d80ec86a60,
                         &v68) < 0 )
                  {
                    v17 = ((__int64 (__fastcall *)(struct IUri *, _QWORD, BSTR *, _QWORD))v43->lpVtbl->GetPropertyBSTR)(
                            v43,
                            v62,
                            bstrString,
                            0);
                    if ( v17 >= 0 )
                    {
                      bstrString[1] = bstrString[0];
                      v64[0] = SysStringLen(bstrString[0]);
                    }
                  }
                  else
                  {
                    v17 = (*(__int64 (__fastcall **)(LPCWSTR, _QWORD, BSTR *, UINT *))(*(_QWORD *)v68 + 224LL))(
                            v68,
                            v62,
                            &bstrString[1],
                            v64);
                    (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)v68 + 16LL))(v68);
                  }
                  if ( v44 && v17 >= 0 )
                  {
                    v61 = v43;
                    ((void (__fastcall *)(struct IUri *))v43->lpVtbl->AddRef)(v43);
                  }
                  if ( v17 == 1 && (v17 = CUString::Set((CUString *)&v60, v65, Uri_PROPERTY_RAW_URI), v17 == 1) )
                  {
                    v17 = -2146697214;
                  }
                  else
                  {
LABEL_119:
                    if ( v17 >= 0 )
                    {
                      v46 = v64[0];
                      v14 = pszResult;
                      if ( cchResult <= v64[0] )
                      {
                        v46 = v64[0] + 1;
                        v17 = -2147467261;
                      }
                      else if ( v64[0] > 0x7FFFFFFE )
                      {
                        *pszResult = 0;
                        v17 = -2147024809;
                      }
                      else
                      {
                        v47 = bstrString[1];
                        v48 = v64[0];
                        v49 = cchResult;
                        v50 = pszResult;
                        do
                        {
                          if ( !v48 )
                            break;
                          if ( !*v47 )
                            break;
                          *v50++ = *v47++;
                          --v48;
                          --v49;
                        }
                        while ( v49 );
                        v18 = v50 - 1;
                        v17 = -2147024774;
                        if ( v49 )
                        {
                          v18 = v50;
                          v17 = 0;
                        }
                        *v18 = 0;
                      }
                      goto LABEL_13;
                    }
                  }
                }
LABEL_159:
                v46 = pcchResult;
                v14 = pszResult;
LABEL_13:
                if ( ppURI )
                {
                  ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
                  ppURI = 0;
                }
                if ( v65 )
                {
                  ((void (__fastcall *)(struct IUri *))v65->lpVtbl->Release)(v65);
                  v65 = 0;
                }
                v60 = &CUString::`vftable';
                v19 = v61 != 0;
                if ( v61 || v62 != 11 )
                {
                  if ( bstrString[0] )
                  {
                    SysFreeString(bstrString[0]);
                    bstrString[0] = 0;
                  }
                  bstrString[1] = 0;
                  v64[0] = 0;
                  if ( v19 && v61 )
                    ((void (__fastcall *)(struct IUri *))v61->lpVtbl->Release)(v61);
                }
                *a7 = v46;
                goto LABEL_24;
              }
LABEL_83:
              InitOnceExecuteOnce(&stru_18015DE28, GlobalInitOnceUrlMon, 0, 0);
              if ( (dword_18015E75C & 4) != 0 )
                goto LABEL_84;
              goto LABEL_145;
            }
          }
LABEL_79:
          InitOnceExecuteOnce(&stru_18015DE28, GlobalInitOnceUrlMon, 0, 0);
          if ( (dword_18015E75C & 1) != 0 )
          {
            InitOnceExecuteOnce(&stru_18015DE28, GlobalInitOnceUrlMon, 0, 0);
            if ( (dword_18015E75C & 2) != 0 || (unsigned int)IsABrowserApp() )
              goto LABEL_83;
          }
          goto LABEL_82;
        }
LABEL_144:
        v30 &= ~0x8000000u;
        goto LABEL_58;
      }
    }
LABEL_56:
    v30 &= ~0x2000000u;
    if ( !ShouldUseEdge )
      goto LABEL_144;
    goto LABEL_57;
  }
  v12 = v68;
  v14 = pszResult;
LABEL_8:
  v16 = v12;
  if ( (v8 & 1) != 0 )
  {
    pcchResult = cchResult;
    v17 = CoInternetParseUrl(v12, PARSE_CANONICALIZE, v11, v14, cchResult, &pcchResult, 0);
    *v9 = pcchResult;
LABEL_24:
    if ( v17 < 0 )
      goto LABEL_163;
    v20 = -1;
    do
      ++v20;
    while ( v14[v20] );
    if ( v20 )
      v21 = a6;
    else
LABEL_163:
      v21 = -2147221020;
    if ( pwzURI )
      CoTaskMemFree((LPVOID)pwzURI);
    return v21;
  }
  v23 = 2147483646;
  v24 = cchResult;
  do
  {
    if ( !v23 )
      break;
    if ( !*v16 )
      break;
    *v14++ = *v16++;
    --v23;
    --v24;
  }
  while ( v24 );
  v25 = v14 - 1;
  v26 = -1;
  if ( v24 )
    v25 = v14;
  *v25 = 0;
  do
    ++v26;
  while ( v12[v26] );
  *v9 = v26;
  return 0;
}

```

## disassembly

```asm
0x180013c30  mov     [rsp-8+arg_0], rbx
0x180013c35  mov     [rsp-8+arg_18], r9
0x180013c3a  mov     [rsp-8+arg_10], r8
0x180013c3f  mov     [rsp-8+arg_8], rdx
0x180013c44  push    rbp
0x180013c45  push    rsi
0x180013c46  push    rdi
0x180013c47  push    r12
0x180013c49  push    r13
0x180013c4b  push    r14
0x180013c4d  push    r15
0x180013c4f  lea     rbp, [rsp-7]
0x180013c54  sub     rsp, 0A0h
0x180013c5b  mov     ebx, [rbp+37h+arg_38]
0x180013c5e  xor     r11d, r11d
0x180013c61  mov     r13, [rbp+37h+arg_30]
0x180013c65  mov     esi, ebx
0x180013c67  and     esi, 2
0x180013c6a  mov     dword ptr [rbp+37h+arg_10], r11d
0x180013c6e  mov     r12d, r11d
0x180013c71  mov     [rbp+37h+var_90], r11
0x180013c75  mov     eax, 10000h
0x180013c7a  mov     [rbp+37h+pwzURI], r11
0x180013c7e  cmovz   r12d, eax
0x180013c82  mov     [r13+0], r11d
0x180013c86  mov     r10, r9
0x180013c89  mov     rdi, rcx
0x180013c8c  test    r9, r9
0x180013c8f  jz      loc_1800145E4
0x180013c95  mov     r15, [rbp+37h+pszResult]
0x180013c99  test    r15, r15
0x180013c9c  jz      loc_1800145E4
0x180013ca2  mov     r14d, [rbp+37h+arg_28]
0x180013ca6  shr     r14d, 1
0x180013ca9  cmp     r14d, 824h
0x180013cb0  jb      loc_1800145E4
0x180013cb6  mov     [r15], r11w
0x180013cba  test    rcx, rcx
0x180013cbd  jnz     loc_180013E64
0x180013cc3  mov     r9d, r11d
0x180013cc6  mov     [rbp+37h+arg_28], r11d
0x180013cca  mov     rcx, r10; pwzUrl
0x180013ccd  test    bl, 1
0x180013cd0  jz      loc_180013E0E
0x180013cd6  mov     [rsp+0D0h+dwReserved], r11d; dwReserved
0x180013cdb  lea     rax, [rbp+37h+arg_38]
0x180013cdf  mov     [rsp+0D0h+pcchResult], rax; pcchResult
0x180013ce4  mov     r9, r15; pszResult
0x180013ce7  mov     r8d, r12d; dwFlags
0x180013cea  mov     [rsp+0D0h+cchResult], r14d; cchResult
0x180013cef  mov     edx, 1; ParseAction
0x180013cf4  mov     [rbp+37h+arg_38], r14d
0x180013cf8  call    CoInternetParseUrl
0x180013cfd  mov     ebx, eax
0x180013cff  mov     eax, [rbp+37h+arg_38]
0x180013d02  mov     [r13+0], eax
0x180013d06  jmp     loc_180013DB2
0x180013d0b  test    r8, r8
0x180013d0e  lea     rcx, [r9-2]
0x180013d12  mov     ebx, 8007007Ah
0x180013d17  cmovnz  rcx, r9
0x180013d1b  cmovnz  ebx, r12d
0x180013d1f  mov     [rcx], r12w
0x180013d23  mov     rcx, [rbp+37h+ppURI]
0x180013d27  test    rcx, rcx
0x180013d2a  jz      short loc_180013D3C
0x180013d2c  mov     rax, [rcx]
0x180013d2f  mov     rax, [rax+10h]
0x180013d33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d38  mov     [rbp+37h+ppURI], r12
0x180013d3c  mov     rcx, [rbp+37h+arg_8]
0x180013d40  test    rcx, rcx
0x180013d43  jz      short loc_180013D55
0x180013d45  mov     rax, [rcx]
0x180013d48  mov     rax, [rax+10h]
0x180013d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d51  mov     [rbp+37h+arg_8], r12
0x180013d55  cmp     [rbp+37h+var_60], 0
0x180013d5a  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x180013d61  mov     edi, r12d
0x180013d64  mov     [rbp+37h+var_68], rax
0x180013d68  setnz   dil
0x180013d6c  mov     eax, r12d
0x180013d6f  cmp     [rbp+37h+var_58], 0Bh
0x180013d73  setnz   al
0x180013d76  test    edi, edi
0x180013d78  jz      loc_180013E05
0x180013d7e  mov     rcx, [rbp+37h+bstrString]; bstrString
0x180013d82  test    rcx, rcx
0x180013d85  jnz     loc_1800145C0
0x180013d8b  mov     [rbp+37h+bstrString+8], r12
0x180013d8f  mov     [rbp+37h+var_40], r12d
0x180013d93  test    edi, edi
0x180013d95  jz      short loc_180013DAC
0x180013d97  mov     rcx, [rbp+37h+var_60]
0x180013d9b  test    rcx, rcx
0x180013d9e  jz      short loc_180013DAC
0x180013da0  mov     rax, [rcx]
0x180013da3  mov     rax, [rax+10h]
0x180013da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013dac  mov     rax, [rbp+37h+arg_30]
0x180013db0  mov     [rax], esi
0x180013db2  shr     ebx, 1Fh
0x180013db5  test    ebx, ebx
0x180013db7  jnz     loc_1800145CF
0x180013dbd  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180013dc4  inc     rax
0x180013dc7  cmp     word ptr [r15+rax*2], 0
0x180013dcd  jnz     short loc_180013DC4
0x180013dcf  test    rax, rax
0x180013dd2  jz      loc_1800145CF
0x180013dd8  mov     ebx, [rbp+37h+arg_28]
0x180013ddb  mov     rcx, [rbp+37h+pwzURI]; pv
0x180013ddf  test    rcx, rcx
0x180013de2  jnz     loc_1800145D9
0x180013de8  mov     eax, ebx
0x180013dea  mov     rbx, [rsp+0D0h+arg_0]
0x180013df2  add     rsp, 0A0h
0x180013df9  pop     r15
0x180013dfb  pop     r14
0x180013dfd  pop     r13
0x180013dff  pop     r12
0x180013e01  pop     rdi
0x180013e02  pop     rsi
0x180013e03  pop     rbp
0x180013e04  retn
0x180013e05  test    eax, eax
0x180013e07  jz      short loc_180013DAC
0x180013e09  jmp     loc_180013D7E
0x180013e0e  mov     eax, 7FFFFFFEh
0x180013e13  mov     edx, r14d
0x180013e16  test    rax, rax
0x180013e19  jz      short loc_180013E3A
0x180013e1b  movzx   r8d, word ptr [rcx]
0x180013e1f  test    r8w, r8w
0x180013e23  jz      short loc_180013E3A
0x180013e25  mov     [r15], r8w
0x180013e29  add     rcx, 2
0x180013e2d  add     r15, 2
0x180013e31  dec     rax
0x180013e34  sub     rdx, 1
0x180013e38  jnz     short loc_180013E16
0x180013e3a  test    rdx, rdx
0x180013e3d  lea     rcx, [r15-2]
0x180013e41  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180013e48  cmovnz  rcx, r15
0x180013e4c  mov     [rcx], r11w
0x180013e50  inc     rax
0x180013e53  cmp     word ptr [r10+rax*2], 0
0x180013e59  jnz     short loc_180013E50
0x180013e5b  mov     [r13+0], eax
0x180013e5f  mov     eax, r9d
0x180013e62  jmp     short loc_180013DEA
0x180013e64  mov     rax, [rcx]
0x180013e67  lea     r8, [rbp+37h+var_90]
0x180013e6b  lea     rdx, aUrlContext; "URL Context"
0x180013e72  mov     rax, [rax+50h]
0x180013e76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e7b  test    eax, eax
0x180013e7d  jz      short loc_180013E88
0x180013e7f  xor     r11d, r11d
0x180013e82  mov     [rbp+37h+var_90], r11
0x180013e86  jmp     short loc_180013E98
0x180013e88  mov     rcx, [rbp+37h+var_90]
0x180013e8c  test    rcx, rcx
0x180013e8f  jnz     loc_18001451A
0x180013e95  xor     r11d, r11d
0x180013e98  mov     r15, [rbp+37h+pwzURI]
0x180013e9c  mov     r9d, r11d
0x180013e9f  mov     [rbp+37h+arg_28], r11d
0x180013ea3  test    r15, r15
0x180013ea6  jz      loc_1800144A3
0x180013eac  test    esi, esi
0x180013eae  mov     [rbp+37h+var_60], r11
0x180013eb2  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x180013eb9  mov     [rbp+37h+var_58], 0Bh
0x180013ec0  mov     [rbp+37h+var_68], rax
0x180013ec4  mov     r13d, 3002B85h
0x180013eca  mov     eax, 3002BA5h
0x180013ecf  mov     [rbp+37h+var_40], r11d
0x180013ed3  mov     ecx, r13d
0x180013ed6  mov     [rbp+37h+ppURI], r11
0x180013eda  cmovz   ecx, eax
0x180013edd  mov     [rbp+37h+arg_8], r11
0x180013ee1  mov     ebx, ecx
0x180013ee3  mov     [rbp+37h+arg_38], r11d
0x180013ee7  or      ebx, 40h
0x180013eea  xorps   xmm0, xmm0
0x180013eed  test    cl, 0C0h
0x180013ef0  movdqu  xmmword ptr [rbp+37h+bstrString], xmm0
0x180013ef5  cmovnz  ebx, ecx
0x180013ef8  mov     eax, ebx
0x180013efa  bts     eax, 9
0x180013efe  test    ebx, 600h
0x180013f04  cmovz   ebx, eax
0x180013f07  test    ebx, 1800h
0x180013f0d  jnz     short loc_180013F13
0x180013f0f  bts     ebx, 0Bh
0x180013f13  test    ebx, 6000h
0x180013f19  jnz     short loc_180013F1F
0x180013f1b  bts     ebx, 0Eh
0x180013f1f  call    cs:__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ; InternalForkingSupport_ShouldUseEdge(void)
0x180013f25  movzx   edi, al
0x180013f28  test    al, al
0x180013f2a  jz      short loc_180013F46
0x180013f2c  mov     rcx, cs:?FEATURE_DISABLE_DATAURI_SUPPORT@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_DISABLE_DATAURI_SUPPORT
0x180013f33  test    rcx, rcx
0x180013f36  jnz     loc_1800144B0
0x180013f3c  mov     eax, cs:dword_180159BE8
0x180013f42  test    eax, eax
0x180013f44  jz      short loc_180013F4F
0x180013f46  btr     ebx, 18h
0x180013f4a  test    dil, dil
0x180013f4d  jz      short loc_180013F9E
0x180013f4f  xor     r9d, r9d; Context
0x180013f52  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180013f59  xor     r8d, r8d; Parameter
0x180013f5c  lea     rcx, stru_18015DE28; InitOnce
0x180013f63  call    cs:__imp_InitOnceExecuteOnce
0x180013f69  test    byte ptr cs:dword_18015E75C, 1
0x180013f70  jz      short loc_180013F9E
0x180013f72  xor     r9d, r9d; Context
0x180013f75  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180013f7c  xor     r8d, r8d; Parameter
0x180013f7f  lea     rcx, stru_18015DE28; InitOnce
0x180013f86  call    cs:__imp_InitOnceExecuteOnce
0x180013f8c  test    byte ptr cs:dword_18015E75C, 2
0x180013f93  jnz     short loc_180013FAB
0x180013f95  call    ?IsABrowserApp@@YAHXZ; IsABrowserApp(void)
0x180013f9a  test    eax, eax
0x180013f9c  jnz     short loc_180013FAB
0x180013f9e  btr     ebx, 19h
0x180013fa2  test    dil, dil
0x180013fa5  jz      loc_180014479
0x180013fab  xor     r9d, r9d; Context
0x180013fae  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180013fb5  xor     r8d, r8d; Parameter
0x180013fb8  lea     rcx, stru_18015DE28; InitOnce
0x180013fbf  call    cs:__imp_InitOnceExecuteOnce
0x180013fc5  test    byte ptr cs:dword_18015E75C, 4
0x180013fcc  jz      loc_180014479
0x180013fd2  mov     eax, ebx
0x180013fd4  bts     eax, 8
0x180013fd8  test    ebx, 110h
0x180013fde  cmovz   ebx, eax
0x180013fe1  mov     edx, ebx
0x180013fe3  bts     edx, 7
0x180013fe7  test    bl, 0C0h
0x180013fea  cmovnz  edx, ebx
0x180013fed  mov     eax, edx
0x180013fef  bts     eax, 9
0x180013ff3  test    edx, 600h
0x180013ff9  cmovz   edx, eax
0x180013ffc  test    edx, 1800h
0x180014002  jnz     short loc_180014008
0x180014004  bts     edx, 0Bh
0x180014008  test    edx, 6000h
0x18001400e  jnz     short loc_180014014
0x180014010  bts     edx, 0Dh
0x180014014  bt      edx, 19h
0x180014018  jb      short loc_18001401E
0x18001401a  bts     edx, 19h
0x18001401e  bt      edx, 18h
0x180014022  jb      short loc_180014028
0x180014024  bts     edx, 18h; dwFlags
0x180014028  lea     r9, [rbp+37h+ppURI]; ppURI
0x18001402c  xor     r8d, r8d; dwReserved
0x18001402f  mov     rcx, r15; pwzURI
0x180014032  call    cs:__imp_CreateUri
0x180014038  mov     ebx, eax
0x18001403a  test    eax, eax
0x18001403c  js      loc_18001455E
0x180014042  mov     rax, [rbp+37h+ppURI]
0x180014046  xor     r15d, r15d
0x180014049  test    esi, esi
0x18001404b  mov     [rbp+37h+var_70], rax
0x18001404f  mov     eax, 3002BA5h
0x180014054  mov     [rbp+37h+var_80], r15
0x180014058  cmovz   r13d, eax
0x18001405c  mov     [rbp+37h+arg_8], r15
0x180014060  mov     ebx, r13d
0x180014063  or      ebx, 40h
0x180014066  test    r13b, 0C0h
0x18001406a  cmovnz  ebx, r13d
0x18001406e  mov     eax, ebx
0x180014070  bts     eax, 9
0x180014074  test    ebx, 600h
0x18001407a  cmovz   ebx, eax
0x18001407d  test    ebx, 1800h
0x180014083  jnz     short loc_180014089
0x180014085  bts     ebx, 0Bh
0x180014089  test    ebx, 6000h
0x18001408f  jnz     short loc_180014095
0x180014091  bts     ebx, 0Eh
0x180014095  call    cs:__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ; InternalForkingSupport_ShouldUseEdge(void)
0x18001409b  movzx   edi, al
0x18001409e  test    al, al
0x1800140a0  jz      short loc_1800140BC
0x1800140a2  mov     rcx, cs:?FEATURE_DISABLE_DATAURI_SUPPORT@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_DISABLE_DATAURI_SUPPORT
0x1800140a9  test    rcx, rcx
  ... truncated ...
```
