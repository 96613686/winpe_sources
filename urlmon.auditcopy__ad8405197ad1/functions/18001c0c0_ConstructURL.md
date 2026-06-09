# ConstructURL

- ea: `0x18001c0c0`
- end: `0x18001caf7`
- name: `ConstructURL`
- size: `2615`
- prototype: `__int64 __fastcall(__int64, struct IUri *, __int64, const WCHAR *, LPWSTR pszResult, unsigned int, DWORD *, DWORD pcchResult)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001fca0`
- `0x18002fb10`

## callees

- `0x180018bfc`
- `0x18001c0c0`
- `0x18001db50`
- `0x18001db94`
- `0x18001e580`
- `0x180031480`
- `0x1800a5e20`
- `0x1801285e6`
- `0x180129010`

## import_xrefs

- `iertutil!CreateUri` at `0x18001c4db`
- `iertutil!CreateUri` at `0x18001c670`
- `iertutil!CreateUri` at `0x18001c4db`
- `iertutil!CreateUri` at `0x18001c670`
- `iertutil!PrivateCoInternetCombineIUri` at `0x18001c751`
- `iertutil!PrivateCoInternetCombineIUri` at `0x18001c751`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x18001c995`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x18001c9c6`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x18001c995`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x18001c9c6`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x18001c3b0`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x18001c544`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x18001c3b0`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x18001c544`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c6d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c92f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c6d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c92f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c6a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c6a4`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001c3fa`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001c423`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001c462`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001c58e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001c5b7`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001c5f6`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001c3fa`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001c423`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001c462`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001c58e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001c5b7`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001c5f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cadc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cadc`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ca5e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cabd`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ca5e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cabd`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ca9b`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ca9b`

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
  int v17; // ebx
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
  UINT v46; // esi
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
      dword_180166BE8 = IsFeatureEnabledInternal == 0;
      FCK::FEATURE_DISABLE_DATAURI_SUPPORT = 0;
    }
    if ( dword_180166BE8 )
      goto LABEL_52;
LABEL_53:
    InitOnceExecuteOnce(&stru_18016AF28, (PINIT_ONCE_FN)GlobalInitOnceUrlMon, 0, 0);
    if ( (dword_18016B858 & 1) != 0 )
    {
      InitOnceExecuteOnce(&stru_18016AF28, (PINIT_ONCE_FN)GlobalInitOnceUrlMon, 0, 0);
      if ( (dword_18016B858 & 2) != 0 || (unsigned int)IsABrowserApp() )
      {
LABEL_57:
        InitOnceExecuteOnce(&stru_18016AF28, (PINIT_ONCE_FN)GlobalInitOnceUrlMon, 0, 0);
        if ( (dword_18016B858 & 4) != 0 )
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
            dword_180166BE8 = v54 == 0;
            FCK::FEATURE_DISABLE_DATAURI_SUPPORT = 0;
          }
          if ( dword_180166BE8 )
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
                  if ( v17 == 1 && (v17 = CUString::Set((CUString *)&v60, v65, 0xBu), v17 == 1) )
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
              InitOnceExecuteOnce(&stru_18016AF28, (PINIT_ONCE_FN)GlobalInitOnceUrlMon, 0, 0);
              if ( (dword_18016B858 & 4) != 0 )
                goto LABEL_84;
              goto LABEL_145;
            }
          }
LABEL_79:
          InitOnceExecuteOnce(&stru_18016AF28, (PINIT_ONCE_FN)GlobalInitOnceUrlMon, 0, 0);
          if ( (dword_18016B858 & 1) != 0 )
          {
            InitOnceExecuteOnce(&stru_18016AF28, (PINIT_ONCE_FN)GlobalInitOnceUrlMon, 0, 0);
            if ( (dword_18016B858 & 2) != 0 || (unsigned int)IsABrowserApp() )
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
0x18001c0c0  mov     [rsp-8+arg_0], rbx
0x18001c0c5  mov     [rsp-8+arg_18], r9
0x18001c0ca  mov     [rsp-8+arg_10], r8
0x18001c0cf  mov     [rsp-8+arg_8], rdx
0x18001c0d4  push    rbp
0x18001c0d5  push    rsi
0x18001c0d6  push    rdi
0x18001c0d7  push    r12
0x18001c0d9  push    r13
0x18001c0db  push    r14
0x18001c0dd  push    r15
0x18001c0df  lea     rbp, [rsp-7]
0x18001c0e4  sub     rsp, 0A0h
0x18001c0eb  mov     ebx, [rbp+37h+arg_38]
0x18001c0ee  xor     r11d, r11d
0x18001c0f1  mov     r13, [rbp+37h+arg_30]
0x18001c0f5  mov     esi, ebx
0x18001c0f7  and     esi, 2
0x18001c0fa  mov     dword ptr [rbp+37h+arg_10], r11d
0x18001c0fe  mov     r12d, r11d
0x18001c101  mov     [rbp+37h+var_90], r11
0x18001c105  mov     eax, 10000h
0x18001c10a  mov     [rbp+37h+pwzURI], r11
0x18001c10e  cmovz   r12d, eax
0x18001c112  mov     [r13+0], r11d
0x18001c116  mov     r10, r9
0x18001c119  mov     rdi, rcx
0x18001c11c  test    r9, r9
0x18001c11f  jz      loc_18001CAED
0x18001c125  mov     r15, [rbp+37h+pszResult]
0x18001c129  test    r15, r15
0x18001c12c  jz      loc_18001CAED
0x18001c132  mov     r14d, [rbp+37h+arg_28]
0x18001c136  shr     r14d, 1
0x18001c139  cmp     r14d, 824h
0x18001c140  jb      loc_18001CAED
0x18001c146  mov     [r15], r11w
0x18001c14a  test    rcx, rcx
0x18001c14d  jnz     loc_18001C2F5
0x18001c153  mov     r9d, r11d
0x18001c156  mov     [rbp+37h+arg_28], r11d
0x18001c15a  mov     rcx, r10; pwzUrl
0x18001c15d  test    bl, 1
0x18001c160  jz      loc_18001C29F
0x18001c166  mov     [rsp+0D0h+dwReserved], r11d; dwReserved
0x18001c16b  lea     rax, [rbp+37h+arg_38]
0x18001c16f  mov     [rsp+0D0h+pcchResult], rax; pcchResult
0x18001c174  mov     r9, r15; pszResult
0x18001c177  mov     r8d, r12d; dwFlags
0x18001c17a  mov     [rsp+0D0h+cchResult], r14d; cchResult
0x18001c17f  mov     edx, 1; ParseAction
0x18001c184  mov     [rbp+37h+arg_38], r14d
0x18001c188  call    CoInternetParseUrl
0x18001c18d  mov     ebx, eax
0x18001c18f  mov     eax, [rbp+37h+arg_38]
0x18001c192  mov     [r13+0], eax
0x18001c196  jmp     loc_18001C242
0x18001c19b  test    r8, r8
0x18001c19e  lea     rcx, [r9-2]
0x18001c1a2  mov     ebx, 8007007Ah
0x18001c1a7  cmovnz  rcx, r9
0x18001c1ab  cmovnz  ebx, r12d
0x18001c1af  mov     [rcx], r12w
0x18001c1b3  mov     rcx, [rbp+37h+ppURI]
0x18001c1b7  test    rcx, rcx
0x18001c1ba  jz      short loc_18001C1CC
0x18001c1bc  mov     rax, [rcx]
0x18001c1bf  mov     rax, [rax+10h]
0x18001c1c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c1c8  mov     [rbp+37h+ppURI], r12
0x18001c1cc  mov     rcx, [rbp+37h+arg_8]
0x18001c1d0  test    rcx, rcx
0x18001c1d3  jz      short loc_18001C1E5
0x18001c1d5  mov     rax, [rcx]
0x18001c1d8  mov     rax, [rax+10h]
0x18001c1dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c1e1  mov     [rbp+37h+arg_8], r12
0x18001c1e5  cmp     [rbp+37h+var_60], 0
0x18001c1ea  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x18001c1f1  mov     edi, r12d
0x18001c1f4  mov     [rbp+37h+var_68], rax
0x18001c1f8  setnz   dil
0x18001c1fc  mov     eax, r12d
0x18001c1ff  cmp     [rbp+37h+var_58], 0Bh
0x18001c203  setnz   al
0x18001c206  test    edi, edi
0x18001c208  jz      loc_18001C296
0x18001c20e  mov     rcx, [rbp+37h+bstrString]; bstrString
0x18001c212  test    rcx, rcx
0x18001c215  jnz     loc_18001CABD
0x18001c21b  mov     [rbp+37h+bstrString+8], r12
0x18001c21f  mov     [rbp+37h+var_40], r12d
0x18001c223  test    edi, edi
0x18001c225  jz      short loc_18001C23C
0x18001c227  mov     rcx, [rbp+37h+var_60]
0x18001c22b  test    rcx, rcx
0x18001c22e  jz      short loc_18001C23C
0x18001c230  mov     rax, [rcx]
0x18001c233  mov     rax, [rax+10h]
0x18001c237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c23c  mov     rax, [rbp+37h+arg_30]
0x18001c240  mov     [rax], esi
0x18001c242  shr     ebx, 1Fh
0x18001c245  test    ebx, ebx
0x18001c247  jnz     loc_18001CAD2
0x18001c24d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001c254  inc     rax
0x18001c257  cmp     word ptr [r15+rax*2], 0
0x18001c25d  jnz     short loc_18001C254
0x18001c25f  test    rax, rax
0x18001c262  jz      loc_18001CAD2
0x18001c268  mov     ebx, [rbp+37h+arg_28]
0x18001c26b  mov     rcx, [rbp+37h+pwzURI]; pv
0x18001c26f  test    rcx, rcx
0x18001c272  jnz     loc_18001CADC
0x18001c278  mov     eax, ebx
0x18001c27a  mov     rbx, [rsp+0D0h+arg_0]
0x18001c282  add     rsp, 0A0h
0x18001c289  pop     r15
0x18001c28b  pop     r14
0x18001c28d  pop     r13
0x18001c28f  pop     r12
0x18001c291  pop     rdi
0x18001c292  pop     rsi
0x18001c293  pop     rbp
0x18001c294  retn
0x18001c296  test    eax, eax
0x18001c298  jz      short loc_18001C23C
0x18001c29a  jmp     loc_18001C20E
0x18001c29f  mov     eax, 7FFFFFFEh
0x18001c2a4  mov     edx, r14d
0x18001c2a7  test    rax, rax
0x18001c2aa  jz      short loc_18001C2CB
0x18001c2ac  movzx   r8d, word ptr [rcx]
0x18001c2b0  test    r8w, r8w
0x18001c2b4  jz      short loc_18001C2CB
0x18001c2b6  mov     [r15], r8w
0x18001c2ba  add     rcx, 2
0x18001c2be  add     r15, 2
0x18001c2c2  dec     rax
0x18001c2c5  sub     rdx, 1
0x18001c2c9  jnz     short loc_18001C2A7
0x18001c2cb  test    rdx, rdx
0x18001c2ce  lea     rcx, [r15-2]
0x18001c2d2  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001c2d9  cmovnz  rcx, r15
0x18001c2dd  mov     [rcx], r11w
0x18001c2e1  inc     rax
0x18001c2e4  cmp     word ptr [r10+rax*2], 0
0x18001c2ea  jnz     short loc_18001C2E1
0x18001c2ec  mov     [r13+0], eax
0x18001c2f0  mov     eax, r9d
0x18001c2f3  jmp     short loc_18001C27A
0x18001c2f5  mov     rax, [rcx]
0x18001c2f8  lea     r8, [rbp+37h+var_90]
0x18001c2fc  lea     rdx, aUrlContext; "URL Context"
0x18001c303  mov     rax, [rax+50h]
0x18001c307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c30c  test    eax, eax
0x18001c30e  jz      short loc_18001C319
0x18001c310  xor     r11d, r11d
0x18001c313  mov     [rbp+37h+var_90], r11
0x18001c317  jmp     short loc_18001C329
0x18001c319  mov     rcx, [rbp+37h+var_90]
0x18001c31d  test    rcx, rcx
0x18001c320  jnz     loc_18001CA0B
0x18001c326  xor     r11d, r11d
0x18001c329  mov     r15, [rbp+37h+pwzURI]
0x18001c32d  mov     r9d, r11d
0x18001c330  mov     [rbp+37h+arg_28], r11d
0x18001c334  test    r15, r15
0x18001c337  jz      loc_18001C988
0x18001c33d  test    esi, esi
0x18001c33f  mov     [rbp+37h+var_60], r11
0x18001c343  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x18001c34a  mov     [rbp+37h+var_58], 0Bh
0x18001c351  mov     [rbp+37h+var_68], rax
0x18001c355  mov     r13d, 3002B85h
0x18001c35b  mov     eax, 3002BA5h
0x18001c360  mov     [rbp+37h+var_40], r11d
0x18001c364  mov     ecx, r13d
0x18001c367  mov     [rbp+37h+ppURI], r11
0x18001c36b  cmovz   ecx, eax
0x18001c36e  mov     [rbp+37h+arg_8], r11
0x18001c372  mov     ebx, ecx
0x18001c374  mov     [rbp+37h+arg_38], r11d
0x18001c378  or      ebx, 40h
0x18001c37b  xorps   xmm0, xmm0
0x18001c37e  test    cl, 0C0h
0x18001c381  movdqu  xmmword ptr [rbp+37h+bstrString], xmm0
0x18001c386  cmovnz  ebx, ecx
0x18001c389  mov     eax, ebx
0x18001c38b  bts     eax, 9
0x18001c38f  test    ebx, 600h
0x18001c395  cmovz   ebx, eax
0x18001c398  test    ebx, 1800h
0x18001c39e  jnz     short loc_18001C3A4
0x18001c3a0  bts     ebx, 0Bh
0x18001c3a4  test    ebx, 6000h
0x18001c3aa  jnz     short loc_18001C3B0
0x18001c3ac  bts     ebx, 0Eh
0x18001c3b0  call    cs:__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ; InternalForkingSupport_ShouldUseEdge(void)
0x18001c3b7  nop     dword ptr [rax+rax+00h]
0x18001c3bc  movzx   edi, al
0x18001c3bf  test    al, al
0x18001c3c1  jz      short loc_18001C3DD
0x18001c3c3  mov     rcx, cs:?FEATURE_DISABLE_DATAURI_SUPPORT@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_DISABLE_DATAURI_SUPPORT
0x18001c3ca  test    rcx, rcx
0x18001c3cd  jnz     loc_18001C995
0x18001c3d3  mov     eax, cs:dword_180166BE8
0x18001c3d9  test    eax, eax
0x18001c3db  jz      short loc_18001C3E6
0x18001c3dd  btr     ebx, 18h
0x18001c3e1  test    dil, dil
0x18001c3e4  jz      short loc_18001C441
0x18001c3e6  xor     r9d, r9d; Context
0x18001c3e9  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001c3f0  xor     r8d, r8d; Parameter
0x18001c3f3  lea     rcx, stru_18016AF28; InitOnce
0x18001c3fa  call    cs:__imp_InitOnceExecuteOnce
0x18001c401  nop     dword ptr [rax+rax+00h]
0x18001c406  test    byte ptr cs:dword_18016B858, 1
0x18001c40d  jz      short loc_18001C441
0x18001c40f  xor     r9d, r9d; Context
0x18001c412  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001c419  xor     r8d, r8d; Parameter
0x18001c41c  lea     rcx, stru_18016AF28; InitOnce
0x18001c423  call    cs:__imp_InitOnceExecuteOnce
0x18001c42a  nop     dword ptr [rax+rax+00h]
0x18001c42f  test    byte ptr cs:dword_18016B858, 2
0x18001c436  jnz     short loc_18001C44E
0x18001c438  call    ?IsABrowserApp@@YAHXZ; IsABrowserApp(void)
0x18001c43d  test    eax, eax
0x18001c43f  jnz     short loc_18001C44E
0x18001c441  btr     ebx, 19h
0x18001c445  test    dil, dil
0x18001c448  jz      loc_18001C95E
0x18001c44e  xor     r9d, r9d; Context
0x18001c451  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001c458  xor     r8d, r8d; Parameter
0x18001c45b  lea     rcx, stru_18016AF28; InitOnce
0x18001c462  call    cs:__imp_InitOnceExecuteOnce
0x18001c469  nop     dword ptr [rax+rax+00h]
0x18001c46e  test    byte ptr cs:dword_18016B858, 4
0x18001c475  jz      loc_18001C95E
0x18001c47b  mov     eax, ebx
0x18001c47d  bts     eax, 8
0x18001c481  test    ebx, 110h
0x18001c487  cmovz   ebx, eax
0x18001c48a  mov     edx, ebx
0x18001c48c  bts     edx, 7
0x18001c490  test    bl, 0C0h
0x18001c493  cmovnz  edx, ebx
0x18001c496  mov     eax, edx
0x18001c498  bts     eax, 9
0x18001c49c  test    edx, 600h
0x18001c4a2  cmovz   edx, eax
0x18001c4a5  test    edx, 1800h
0x18001c4ab  jnz     short loc_18001C4B1
0x18001c4ad  bts     edx, 0Bh
0x18001c4b1  test    edx, 6000h
0x18001c4b7  jnz     short loc_18001C4BD
0x18001c4b9  bts     edx, 0Dh
0x18001c4bd  bt      edx, 19h
0x18001c4c1  jb      short loc_18001C4C7
0x18001c4c3  bts     edx, 19h
0x18001c4c7  bt      edx, 18h
0x18001c4cb  jb      short loc_18001C4D1
0x18001c4cd  bts     edx, 18h; dwFlags
0x18001c4d1  lea     r9, [rbp+37h+ppURI]; ppURI
0x18001c4d5  xor     r8d, r8d; dwReserved
0x18001c4d8  mov     rcx, r15; pwzURI
0x18001c4db  call    cs:__imp_CreateUri
0x18001c4e2  nop     dword ptr [rax+rax+00h]
0x18001c4e7  mov     ebx, eax
0x18001c4e9  test    eax, eax
0x18001c4eb  js      loc_18001CA4F
0x18001c4f1  mov     rax, [rbp+37h+ppURI]
0x18001c4f5  xor     r15d, r15d
0x18001c4f8  test    esi, esi
0x18001c4fa  mov     [rbp+37h+var_70], rax
0x18001c4fe  mov     eax, 3002BA5h
0x18001c503  mov     [rbp+37h+var_80], r15
0x18001c507  cmovz   r13d, eax
0x18001c50b  mov     [rbp+37h+arg_8], r15
0x18001c50f  mov     ebx, r13d
0x18001c512  or      ebx, 40h
0x18001c515  test    r13b, 0C0h
0x18001c519  cmovnz  ebx, r13d
0x18001c51d  mov     eax, ebx
0x18001c51f  bts     eax, 9
0x18001c523  test    ebx, 600h
0x18001c529  cmovz   ebx, eax
0x18001c52c  test    ebx, 1800h
0x18001c532  jnz     short loc_18001C538
0x18001c534  bts     ebx, 0Bh
0x18001c538  test    ebx, 6000h
0x18001c53e  jnz     short loc_18001C544
0x18001c540  bts     ebx, 0Eh
0x18001c544  call    cs:__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ; InternalForkingSupport_ShouldUseEdge(void)
  ... truncated ...
```
