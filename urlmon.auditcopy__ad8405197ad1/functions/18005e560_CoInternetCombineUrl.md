# CoInternetCombineUrl

- ea: `0x18005e560`
- end: `0x18005ed6c`
- name: `CoInternetCombineUrl`
- size: `2060`
- prototype: `HRESULT __stdcall(LPCWSTR pwzBaseUrl, LPCWSTR pwzRelativeUrl, DWORD dwCombineFlags, LPWSTR pszResult, DWORD cchResult, DWORD *pcchResult, DWORD dwReserved)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180018bfc`
- `0x18001db50`
- `0x18001db94`
- `0x180031480`
- `0x18005e560`
- `0x1800a5e20`
- `0x1801285e6`
- `0x180129010`

## import_xrefs

- `iertutil!CreateUri` at `0x18005e7b8`
- `iertutil!CreateUri` at `0x18005eb44`
- `iertutil!CreateUri` at `0x18005e7b8`
- `iertutil!CreateUri` at `0x18005eb44`
- `iertutil!PrivateCoInternetCombineIUri` at `0x18005e82f`
- `iertutil!PrivateCoInternetCombineIUri` at `0x18005e82f`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x18005ec5a`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x18005ec8b`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x18005ec5a`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x18005ec8b`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x18005e6c1`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x18005ea0e`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x18005e6c1`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x18005ea0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005eb9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005eb9f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005eb75`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005eb75`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005e70b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005e734`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005e76f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005ea56`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005ea7f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005eab9`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005e70b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005e734`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005e76f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005ea56`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005ea7f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005eab9`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ece3`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ed57`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ece3`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ed57`
- `OLEAUT32!__imp_SysStringLen` at `0x18005ed22`
- `OLEAUT32!__imp_SysStringLen` at `0x18005ed22`

## pseudocode

```c
HRESULT __stdcall CoInternetCombineUrl(
        LPCWSTR pwzBaseUrl,
        LPCWSTR pwzRelativeUrl,
        DWORD dwCombineFlags,
        LPWSTR pszResult,
        DWORD cchResult,
        DWORD *pcchResult,
        DWORD dwReserved)
{
  DWORD *v7; // r13
  DWORD v10; // edi
  DWORD v11; // ebx
  DWORD v12; // r14d
  HRESULT Uri; // ebx
  LPWSTR v14; // rcx
  _BOOL8 v15; // rdi
  bool ShouldUseEdge; // si
  int v18; // esi
  int v19; // edx
  int v20; // ecx
  DWORD v21; // edx
  DWORD *v22; // rcx
  void *v23; // rdi
  struct IUri *v24; // rdi
  _BOOL8 v25; // r12
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rax
  BSTR v29; // rcx
  bool v30; // bl
  int v31; // ecx
  int v32; // edx
  int v33; // ecx
  int v34; // edx
  int v35; // ecx
  int v36; // r9d
  DWORD v37; // edx
  DWORD *v38; // r12
  COInetSession *v39; // rax
  volatile signed __int32 *v40; // rbx
  COInetSession *v41; // rax
  int IsFeatureEnabledInternal; // eax
  int v43; // eax
  struct IUri *v44; // [rsp+48h] [rbp-41h] BYREF
  IUri *ppURI; // [rsp+50h] [rbp-39h] BYREF
  void *v46; // [rsp+58h] [rbp-31h] BYREF
  IUri *v47; // [rsp+60h] [rbp-29h]
  void **v48; // [rsp+68h] [rbp-21h] BYREF
  struct IUri *v49; // [rsp+70h] [rbp-19h]
  unsigned int v50; // [rsp+78h] [rbp-11h]
  BSTR bstrString[2]; // [rsp+80h] [rbp-9h] BYREF
  UINT v52[14]; // [rsp+90h] [rbp+7h] BYREF

  v7 = pcchResult;
  v49 = 0;
  v50 = 11;
  v48 = &CUString::`vftable';
  v52[0] = 0;
  ppURI = 0;
  v44 = 0;
  *(_OWORD *)bstrString = 0;
  if ( pcchResult )
    *pcchResult = 0;
  v10 = (dwCombineFlags >> 11) & 0x20 | 0x3002B85;
  v11 = v10;
  v12 = dwCombineFlags & 0x8000000;
  if ( (dwCombineFlags & 0x8000000) != 0 )
    v11 = (dwCombineFlags >> 11) & 0x20 | 0x3002A95;
  if ( (v11 & 0x110) == 0x110 )
  {
    Uri = -2147024809;
    goto LABEL_14;
  }
  ShouldUseEdge = InternalForkingSupport_ShouldUseEdge();
  if ( !ShouldUseEdge )
    goto LABEL_26;
  if ( FCK::FEATURE_DISABLE_DATAURI_SUPPORT )
  {
    IsFeatureEnabledInternal = CoInternetIsFeatureEnabledInternal();
    if ( IsFeatureEnabledInternal < 0 )
      goto LABEL_27;
    dword_180166BE8 = IsFeatureEnabledInternal == 0;
    FCK::FEATURE_DISABLE_DATAURI_SUPPORT = 0;
  }
  if ( dword_180166BE8 )
  {
LABEL_26:
    v11 &= ~0x1000000u;
    if ( !ShouldUseEdge )
      goto LABEL_30;
  }
LABEL_27:
  InitOnceExecuteOnce(&stru_18016AF28, (PINIT_ONCE_FN)GlobalInitOnceUrlMon, 0, 0);
  if ( (dword_18016B858 & 1) == 0
    || (InitOnceExecuteOnce(&stru_18016AF28, (PINIT_ONCE_FN)GlobalInitOnceUrlMon, 0, 0), (dword_18016B858 & 2) == 0)
    && !(unsigned int)IsABrowserApp() )
  {
LABEL_30:
    v11 &= ~0x2000000u;
    if ( !ShouldUseEdge )
      goto LABEL_32;
  }
  InitOnceExecuteOnce(&stru_18016AF28, (PINIT_ONCE_FN)GlobalInitOnceUrlMon, 0, 0);
LABEL_32:
  v18 = 0;
  v19 = v11 | 0x100;
  if ( (v11 & 0x110) != 0 )
    v19 = v11;
  v20 = v19 | 0x2000000;
  if ( (v19 & 0x2000000) != 0 )
    v20 = v19;
  v21 = v20 | 0x1000000;
  if ( (v20 & 0x1000000) != 0 )
    v21 = v20;
  Uri = CreateUri(pwzBaseUrl, v21, 0, &ppURI);
  if ( Uri < 0 )
    goto LABEL_10;
  v44 = 0;
  v22 = 0;
  pcchResult = 0;
  if ( v12 )
    v10 = v10 & 0xFFFFFEEF | 0x10;
  if ( (v10 & 0x110) == 0x110 )
  {
    Uri = -2147024809;
LABEL_48:
    if ( v22 )
      (*(void (__fastcall **)(DWORD *))(*(_QWORD *)v22 + 16LL))(v22);
    if ( Uri >= 0 )
    {
      v24 = v44;
      Uri = 0;
      LOBYTE(v18) = v44 != v49;
      v25 = v50 != 0;
      if ( v18 || v50 )
      {
        if ( bstrString[0] )
        {
          SysFreeString(bstrString[0]);
          bstrString[0] = 0;
        }
        bstrString[1] = 0;
        v52[0] = 0;
        if ( v18 && v49 )
        {
          ((void (__fastcall *)(struct IUri *))v49->lpVtbl->Release)(v49);
          v49 = 0;
        }
      }
      v50 = 0;
      if ( !v24 || !v25 && !v18 )
        goto LABEL_58;
      pcchResult = 0;
      if ( ((__int64 (__fastcall *)(struct IUri *, GUID *, DWORD **))v24->lpVtbl->QueryInterface)(
             v24,
             &GUID_50295b0c_6b79_4935_aed8_05d80ec86a60,
             &pcchResult) < 0 )
      {
        Uri = ((__int64 (__fastcall *)(struct IUri *, _QWORD, BSTR *, _QWORD))v24->lpVtbl->GetPropertyBSTR)(
                v24,
                v50,
                bstrString,
                0);
        if ( Uri >= 0 )
        {
          bstrString[1] = bstrString[0];
          v52[0] = SysStringLen(bstrString[0]);
        }
      }
      else
      {
        Uri = (*(__int64 (__fastcall **)(DWORD *, _QWORD, BSTR *, UINT *))(*(_QWORD *)pcchResult + 224LL))(
                pcchResult,
                v50,
                &bstrString[1],
                v52);
        (*(void (__fastcall **)(DWORD *))(*(_QWORD *)pcchResult + 16LL))(pcchResult);
      }
      if ( v18 && Uri >= 0 )
      {
        v49 = v24;
        ((void (__fastcall *)(struct IUri *))v24->lpVtbl->AddRef)(v24);
      }
      if ( Uri == 1 && (Uri = CUString::Set((CUString *)&v48, v44, 0xBu), Uri == 1) )
      {
        Uri = -2146697214;
      }
      else
      {
LABEL_58:
        if ( Uri >= 0 )
        {
          v26 = v52[0];
          if ( cchResult <= v52[0] )
          {
            if ( v7 )
              *v7 = v52[0] + 1;
            Uri = -2147467261;
          }
          else
          {
            if ( v7 )
              *v7 = v52[0];
            v27 = cchResult;
            if ( cchResult - 1 > 0x7FFFFFFE )
            {
              Uri = -2147024809;
              if ( cchResult )
                *pszResult = 0;
            }
            else if ( (unsigned int)v26 > 0x7FFFFFFE )
            {
              *pszResult = 0;
              Uri = -2147024809;
            }
            else
            {
              v28 = v26;
              v29 = bstrString[1];
              do
              {
                if ( !v28 )
                  break;
                if ( !*v29 )
                  break;
                *pszResult++ = *v29++;
                --v28;
                --v27;
              }
              while ( v27 );
              v14 = pszResult - 1;
              if ( v27 )
                v14 = pszResult;
              Uri = v27 == 0 ? 0x8007007A : 0;
              *v14 = 0;
            }
          }
        }
      }
    }
    goto LABEL_10;
  }
  v47 = ppURI;
  v30 = InternalForkingSupport_ShouldUseEdge();
  if ( !v30 )
  {
LABEL_83:
    v10 &= ~0x1000000u;
    if ( !v30 )
      goto LABEL_87;
    goto LABEL_84;
  }
  if ( FCK::FEATURE_DISABLE_DATAURI_SUPPORT )
  {
    v43 = CoInternetIsFeatureEnabledInternal();
    if ( v43 < 0 )
      goto LABEL_84;
    dword_180166BE8 = v43 == 0;
    FCK::FEATURE_DISABLE_DATAURI_SUPPORT = 0;
  }
  if ( dword_180166BE8 )
    goto LABEL_83;
LABEL_84:
  InitOnceExecuteOnce(&stru_18016AF28, (PINIT_ONCE_FN)GlobalInitOnceUrlMon, 0, 0);
  if ( (dword_18016B858 & 1) != 0 )
  {
    InitOnceExecuteOnce(&stru_18016AF28, (PINIT_ONCE_FN)GlobalInitOnceUrlMon, 0, 0);
    if ( (dword_18016B858 & 2) != 0 || (unsigned int)IsABrowserApp() )
      goto LABEL_88;
  }
LABEL_87:
  v10 &= ~0x2000000u;
  if ( v30 )
LABEL_88:
    InitOnceExecuteOnce(&stru_18016AF28, (PINIT_ONCE_FN)GlobalInitOnceUrlMon, 0, 0);
  if ( pwzRelativeUrl )
  {
    v31 = v10 | 0x100;
    if ( (v10 & 0x110) != 0 )
      v31 = v10;
    v32 = v31 | 0x80;
    if ( (v31 & 0xC0) != 0 )
      v32 = v31;
    v33 = v32 | 0x200;
    if ( (v32 & 0x600) != 0 )
      v33 = v32;
    v34 = v33 | 0x800;
    if ( (v33 & 0x1800) != 0 )
      v34 = v33;
    v35 = v34 | 0x2000;
    if ( (v34 & 0x6000) != 0 )
      v35 = v34;
    v36 = v35 | 0x2000000;
    if ( (v35 & 0x2000000) != 0 )
      v36 = v35;
    v37 = v36 | 0x1000000;
    if ( (v36 & 0x1000000) != 0 )
      v37 = v36;
    Uri = CreateUri(pwzRelativeUrl, v37, dwReserved, (IUri **)&pcchResult);
    if ( Uri < 0 )
      goto LABEL_47;
  }
  v38 = pcchResult;
  if ( pcchResult )
  {
    v46 = 0;
    v23 = 0;
    EnterCriticalSection(&g_mxsOInet);
    v39 = g_pCOInetSession;
    if ( g_pCOInetSession
      || ((v41 = (COInetSession *)operator new(0x180u)) != 0 && (v39 = COInetSession::COInetSession(v41)) != 0
        ? (g_pCOInetSession = v39)
        : (COInetSession *)(v39 = g_pCOInetSession, v18 = -2147024882),
          v39) )
    {
      _InterlockedIncrement((volatile signed __int32 *)v39 + 4);
      v40 = (volatile signed __int32 *)g_pCOInetSession;
    }
    else
    {
      v40 = 0;
      v18 = -2147024882;
    }
    LeaveCriticalSection(&g_mxsOInet);
    if ( v18 )
    {
      v18 = 0;
    }
    else
    {
      v18 = 0;
      if ( v40 )
      {
        if ( !memcmp_0(&GUID_79eac9ec_baf9_11ce_8c82_00aa004ba90b, &IID_IInternetProtocolInfo, 0x10u) )
        {
          v23 = (void *)(v40 + 2);
          _InterlockedIncrement(v40 + 4);
        }
        else if ( !(unsigned int)COInetSession::QueryInterface(
                                   (COInetSession *)v40,
                                   &GUID_79eac9ec_baf9_11ce_8c82_00aa004ba90b,
                                   &v46) )
        {
          v23 = v46;
        }
      }
      _InterlockedDecrement(v40 + 4);
    }
    Uri = PrivateCoInternetCombineIUri(v47, v38, dwCombineFlags, &v44, dwReserved, v23, 0, 0);
    if ( v23 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v23 + 16LL))(v23);
LABEL_47:
    v22 = pcchResult;
    goto LABEL_48;
  }
  Uri = -2147418113;
LABEL_10:
  if ( ppURI )
  {
    ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
    ppURI = 0;
  }
  if ( v44 )
  {
    ((void (__fastcall *)(struct IUri *))v44->lpVtbl->Release)(v44);
    v44 = 0;
  }
LABEL_14:
  v48 = &CUString::`vftable';
  v15 = v49 != 0;
  if ( v49 || v50 != 11 )
  {
    if ( bstrString[0] )
    {
      SysFreeString(bstrString[0]);
      bstrString[0] = 0;
    }
    bstrString[1] = 0;
    v52[0] = 0;
    if ( v15 && v49 )
      ((void (__fastcall *)(struct IUri *))v49->lpVtbl->Release)(v49);
  }
  return Uri;
}

```

## disassembly

```asm
0x18005e560  mov     rax, rsp
0x18005e563  mov     [rax+8], rbx
0x18005e567  mov     [rax+18h], r8d
0x18005e56b  mov     [rax+10h], rdx
0x18005e56f  push    rbp
0x18005e570  push    rsi
0x18005e571  push    rdi
0x18005e572  push    r12
0x18005e574  push    r13
0x18005e576  push    r14
0x18005e578  push    r15
0x18005e57a  lea     rbp, [rax-47h]
0x18005e57e  sub     rsp, 90h
0x18005e585  mov     r13, [rbp+3Fh+pcchResult]
0x18005e589  xor     esi, esi
0x18005e58b  mov     [rbp+3Fh+var_58], rsi
0x18005e58f  mov     r12, rcx
0x18005e592  mov     [rbp+3Fh+var_50], 0Bh
0x18005e599  lea     rcx, ??_7CUString@@6B@; const CUString::`vftable'
0x18005e5a0  mov     [rbp+3Fh+var_60], rcx
0x18005e5a4  xorps   xmm0, xmm0
0x18005e5a7  mov     [rbp+3Fh+var_38], esi
0x18005e5aa  mov     r15, r9
0x18005e5ad  mov     [rbp+3Fh+ppURI], rsi
0x18005e5b1  mov     eax, r8d
0x18005e5b4  mov     [rbp+3Fh+var_80], rsi
0x18005e5b8  movdqu  xmmword ptr [rbp+3Fh+bstrString], xmm0
0x18005e5bd  test    r13, r13
0x18005e5c0  jz      short loc_18005E5C6
0x18005e5c2  mov     [r13+0], esi
0x18005e5c6  mov     edi, eax
0x18005e5c8  mov     r14d, eax
0x18005e5cb  shr     edi, 0Bh
0x18005e5ce  and     edi, 20h
0x18005e5d1  or      edi, 3002B85h
0x18005e5d7  mov     ebx, edi
0x18005e5d9  and     r14d, 8000000h
0x18005e5e0  jz      short loc_18005E5E9
0x18005e5e2  btr     ebx, 8
0x18005e5e6  or      ebx, 10h
0x18005e5e9  mov     ecx, 110h
0x18005e5ee  mov     eax, ebx
0x18005e5f0  and     eax, ecx
0x18005e5f2  cmp     eax, ecx
0x18005e5f4  jnz     loc_18005E6C1
0x18005e5fa  mov     ebx, 80070057h
0x18005e5ff  jmp     short loc_18005E64E
0x18005e601  test    rdx, rdx
0x18005e604  lea     rcx, [r15-2]
0x18005e608  cmovnz  rcx, r15
0x18005e60c  neg     rdx
0x18005e60f  sbb     ebx, ebx
0x18005e611  not     ebx
0x18005e613  and     ebx, 8007007Ah
0x18005e619  mov     [rcx], si
0x18005e61c  mov     rcx, [rbp+3Fh+ppURI]
0x18005e620  test    rcx, rcx
0x18005e623  jz      short loc_18005E635
0x18005e625  mov     rax, [rcx]
0x18005e628  mov     rax, [rax+10h]
0x18005e62c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e631  mov     [rbp+3Fh+ppURI], rsi
0x18005e635  mov     rcx, [rbp+3Fh+var_80]
0x18005e639  test    rcx, rcx
0x18005e63c  jz      short loc_18005E64E
0x18005e63e  mov     rax, [rcx]
0x18005e641  mov     rax, [rax+10h]
0x18005e645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e64a  mov     [rbp+3Fh+var_80], rsi
0x18005e64e  cmp     [rbp+3Fh+var_58], rsi
0x18005e652  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x18005e659  mov     edi, esi
0x18005e65b  mov     [rbp+3Fh+var_60], rax
0x18005e65f  setnz   dil
0x18005e663  mov     eax, esi
0x18005e665  cmp     [rbp+3Fh+var_50], 0Bh
0x18005e669  setnz   al
0x18005e66c  test    edi, edi
0x18005e66e  jz      short loc_18005E6BB
0x18005e670  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x18005e674  test    rcx, rcx
0x18005e677  jnz     loc_18005ED57
0x18005e67d  mov     [rbp+3Fh+bstrString+8], rsi
0x18005e681  mov     [rbp+3Fh+var_38], esi
0x18005e684  test    edi, edi
0x18005e686  jz      short loc_18005E69D
0x18005e688  mov     rcx, [rbp+3Fh+var_58]
0x18005e68c  test    rcx, rcx
0x18005e68f  jz      short loc_18005E69D
0x18005e691  mov     rax, [rcx]
0x18005e694  mov     rax, [rax+10h]
0x18005e698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e69d  mov     eax, ebx
0x18005e69f  mov     rbx, [rsp+0C0h+arg_0]
0x18005e6a7  add     rsp, 90h
0x18005e6ae  pop     r15
0x18005e6b0  pop     r14
0x18005e6b2  pop     r13
0x18005e6b4  pop     r12
0x18005e6b6  pop     rdi
0x18005e6b7  pop     rsi
0x18005e6b8  pop     rbp
0x18005e6b9  retn
0x18005e6bb  test    eax, eax
0x18005e6bd  jz      short loc_18005E69D
0x18005e6bf  jmp     short loc_18005E670
0x18005e6c1  call    cs:__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ; InternalForkingSupport_ShouldUseEdge(void)
0x18005e6c8  nop     dword ptr [rax+rax+00h]
0x18005e6cd  mov     sil, al
0x18005e6d0  test    al, al
0x18005e6d2  jz      short loc_18005E6EE
0x18005e6d4  mov     rcx, cs:?FEATURE_DISABLE_DATAURI_SUPPORT@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_DISABLE_DATAURI_SUPPORT
0x18005e6db  test    rcx, rcx
0x18005e6de  jnz     loc_18005EC5A
0x18005e6e4  mov     eax, cs:dword_180166BE8
0x18005e6ea  test    eax, eax
0x18005e6ec  jz      short loc_18005E6F7
0x18005e6ee  btr     ebx, 18h
0x18005e6f2  test    sil, sil
0x18005e6f5  jz      short loc_18005E752
0x18005e6f7  xor     r9d, r9d; Context
0x18005e6fa  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18005e701  xor     r8d, r8d; Parameter
0x18005e704  lea     rcx, stru_18016AF28; InitOnce
0x18005e70b  call    cs:__imp_InitOnceExecuteOnce
0x18005e712  nop     dword ptr [rax+rax+00h]
0x18005e717  test    byte ptr cs:dword_18016B858, 1
0x18005e71e  jz      short loc_18005E752
0x18005e720  xor     r9d, r9d; Context
0x18005e723  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18005e72a  xor     r8d, r8d; Parameter
0x18005e72d  lea     rcx, stru_18016AF28; InitOnce
0x18005e734  call    cs:__imp_InitOnceExecuteOnce
0x18005e73b  nop     dword ptr [rax+rax+00h]
0x18005e740  test    byte ptr cs:dword_18016B858, 2
0x18005e747  jnz     short loc_18005E75B
0x18005e749  call    ?IsABrowserApp@@YAHXZ; IsABrowserApp(void)
0x18005e74e  test    eax, eax
0x18005e750  jnz     short loc_18005E75B
0x18005e752  btr     ebx, 19h
0x18005e756  test    sil, sil
0x18005e759  jz      short loc_18005E77B
0x18005e75b  xor     r9d, r9d; Context
0x18005e75e  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18005e765  xor     r8d, r8d; Parameter
0x18005e768  lea     rcx, stru_18016AF28; InitOnce
0x18005e76f  call    cs:__imp_InitOnceExecuteOnce
0x18005e776  nop     dword ptr [rax+rax+00h]
0x18005e77b  mov     r8d, 2000000h
0x18005e781  lea     r9, [rbp+3Fh+ppURI]; ppURI
0x18005e785  xor     esi, esi
0x18005e787  mov     edx, ebx
0x18005e789  bts     edx, 8
0x18005e78d  test    ebx, 110h
0x18005e793  cmovnz  edx, ebx
0x18005e796  mov     ecx, edx
0x18005e798  or      ecx, r8d
0x18005e79b  test    r8d, edx
0x18005e79e  mov     r8d, 1000000h
0x18005e7a4  cmovnz  ecx, edx
0x18005e7a7  mov     edx, ecx
0x18005e7a9  or      edx, r8d
0x18005e7ac  test    r8d, ecx
0x18005e7af  cmovnz  edx, ecx; dwFlags
0x18005e7b2  xor     r8d, r8d; dwReserved
0x18005e7b5  mov     rcx, r12; pwzURI
0x18005e7b8  call    cs:__imp_CreateUri
0x18005e7bf  nop     dword ptr [rax+rax+00h]
0x18005e7c4  mov     ebx, eax
0x18005e7c6  test    eax, eax
0x18005e7c8  js      loc_18005E61C
0x18005e7ce  mov     [rbp+3Fh+var_80], rsi
0x18005e7d2  mov     ecx, esi
0x18005e7d4  mov     [rbp+3Fh+pcchResult], rcx
0x18005e7d8  test    r14d, r14d
0x18005e7db  jz      short loc_18005E7E4
0x18005e7dd  btr     edi, 8
0x18005e7e1  or      edi, 10h
0x18005e7e4  mov     r12d, 110h
0x18005e7ea  mov     eax, edi
0x18005e7ec  and     eax, r12d
0x18005e7ef  mov     r14d, 80070057h
0x18005e7f5  cmp     eax, r12d
0x18005e7f8  jnz     loc_18005EA06
0x18005e7fe  mov     ebx, r14d
0x18005e801  jmp     short loc_18005E855
0x18005e803  mov     rdi, [rbp+3Fh+var_70]
0x18005e807  lock dec dword ptr [rbx+10h]
0x18005e80b  mov     eax, [rbp+3Fh+dwReserved]
0x18005e80e  lea     r9, [rbp+3Fh+var_80]
0x18005e812  mov     r8d, [rbp+3Fh+arg_10]
0x18005e816  mov     rdx, r12
0x18005e819  mov     rcx, [rbp+3Fh+var_68]
0x18005e81d  mov     [rsp+38h], esi
0x18005e821  mov     [rsp+0C0h+var_90], esi
0x18005e825  mov     qword ptr [rsp+0C0h+var_98], rdi
0x18005e82a  mov     [rsp+0C0h+var_A0], rax
0x18005e82f  call    cs:__imp_PrivateCoInternetCombineIUri
0x18005e836  nop     dword ptr [rax+rax+00h]
0x18005e83b  mov     ebx, eax
0x18005e83d  test    rdi, rdi
0x18005e840  jz      short loc_18005E851
0x18005e842  mov     rax, [rdi]
0x18005e845  mov     rcx, rdi
0x18005e848  mov     rax, [rax+10h]
0x18005e84c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e851  mov     rcx, [rbp+3Fh+pcchResult]
0x18005e855  test    rcx, rcx
0x18005e858  jz      short loc_18005E866
0x18005e85a  mov     rax, [rcx]
0x18005e85d  mov     rax, [rax+10h]
0x18005e861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e866  test    ebx, ebx
0x18005e868  js      loc_18005E61C
0x18005e86e  mov     rdi, [rbp+3Fh+var_80]
0x18005e872  mov     ebx, esi
0x18005e874  cmp     rdi, [rbp+3Fh+var_58]
0x18005e878  setnz   sil
0x18005e87c  xor     eax, eax
0x18005e87e  cmp     [rbp+3Fh+var_50], eax
0x18005e881  mov     r12d, eax
0x18005e884  setnz   r12b
0x18005e888  test    esi, esi
0x18005e88a  jz      loc_18005E9F8
0x18005e890  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x18005e894  test    rcx, rcx
0x18005e897  jnz     loc_18005ECE3
0x18005e89d  mov     [rbp+3Fh+bstrString+8], rax
0x18005e8a1  mov     [rbp+3Fh+var_38], eax
0x18005e8a4  test    esi, esi
0x18005e8a6  jz      short loc_18005E8C3
0x18005e8a8  mov     rcx, [rbp+3Fh+var_58]
0x18005e8ac  test    rcx, rcx
0x18005e8af  jz      short loc_18005E8C3
0x18005e8b1  mov     rax, [rcx]
0x18005e8b4  mov     rax, [rax+10h]
0x18005e8b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e8bd  xor     eax, eax
0x18005e8bf  mov     [rbp+3Fh+var_58], rax
0x18005e8c3  mov     [rbp+3Fh+var_50], eax
0x18005e8c6  test    rdi, rdi
0x18005e8c9  jnz     short loc_18005E941
0x18005e8cb  xor     esi, esi
0x18005e8cd  test    ebx, ebx
0x18005e8cf  js      loc_18005E61C
0x18005e8d5  mov     ecx, [rbp+3Fh+var_38]
0x18005e8d8  mov     eax, [rbp+3Fh+cchResult]
0x18005e8db  cmp     eax, ecx
0x18005e8dd  jbe     loc_18005ECB6
0x18005e8e3  test    r13, r13
0x18005e8e6  jnz     loc_18005E9EF
0x18005e8ec  mov     rdx, rax
0x18005e8ef  mov     r8d, 7FFFFFFEh
0x18005e8f5  dec     eax
0x18005e8f7  cmp     eax, r8d
0x18005e8fa  ja      loc_18005ED42
0x18005e900  cmp     ecx, r8d
0x18005e903  ja      loc_18005ED36
0x18005e909  mov     rax, rcx
0x18005e90c  mov     rcx, [rbp+3Fh+bstrString+8]
0x18005e910  test    rax, rax
0x18005e913  jz      loc_18005E601
0x18005e919  movzx   r8d, word ptr [rcx]
0x18005e91d  test    r8w, r8w
0x18005e921  jz      loc_18005E601
0x18005e927  mov     [r15], r8w
0x18005e92b  add     rcx, 2
0x18005e92f  add     r15, 2
0x18005e933  dec     rax
0x18005e936  sub     rdx, 1
0x18005e93a  jnz     short loc_18005E910
0x18005e93c  jmp     loc_18005E601
0x18005e941  test    r12d, r12d
0x18005e944  jz      loc_18005ECCC
0x18005e94a  mov     [rbp+3Fh+pcchResult], rax
0x18005e94e  lea     r8, [rbp+3Fh+pcchResult]
0x18005e952  mov     rax, [rdi]
0x18005e955  lea     rdx, _GUID_50295b0c_6b79_4935_aed8_05d80ec86a60
0x18005e95c  mov     rcx, rdi
0x18005e95f  mov     rax, [rax]
0x18005e962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e967  mov     edx, [rbp+3Fh+var_50]
0x18005e96a  test    eax, eax
0x18005e96c  js      loc_18005ECFA
0x18005e972  mov     rcx, [rbp+3Fh+pcchResult]
0x18005e976  lea     r9, [rbp+3Fh+var_38]
0x18005e97a  lea     r8, [rbp+3Fh+bstrString+8]
0x18005e97e  mov     rax, [rcx]
0x18005e981  mov     rax, [rax+0E0h]
0x18005e988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e98d  mov     rcx, [rbp+3Fh+pcchResult]
0x18005e991  mov     ebx, eax
0x18005e993  mov     rax, [rcx]
0x18005e996  mov     rax, [rax+10h]
0x18005e99a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e99f  test    esi, esi
0x18005e9a1  jz      loc_18005EC53
0x18005e9a7  xor     esi, esi
0x18005e9a9  test    ebx, ebx
0x18005e9ab  js      short loc_18005E9C0
  ... truncated ...
```
