# CoInternetCombineUrl

- ea: `0x180058a30`
- end: `0x1800591cf`
- name: `CoInternetCombineUrl`
- size: `1951`
- prototype: `HRESULT __stdcall(LPCWSTR pwzBaseUrl, LPCWSTR pwzRelativeUrl, DWORD dwCombineFlags, LPWSTR pszResult, DWORD cchResult, DWORD *pcchResult, DWORD dwReserved)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18001063c`
- `0x1800150e0`
- `0x18001511c`
- `0x18001e160`
- `0x180058a30`
- `0x18009f200`
- `0x18011ba26`
- `0x18011c010`

## import_xrefs

- `iertutil!CreateUri` at `0x180058c6f`
- `iertutil!CreateUri` at `0x180058fd7`
- `iertutil!CreateUri` at `0x180058c6f`
- `iertutil!CreateUri` at `0x180058fd7`
- `iertutil!PrivateCoInternetCombineIUri` at `0x180058ce0`
- `iertutil!PrivateCoInternetCombineIUri` at `0x180058ce0`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x1800590db`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180059106`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x1800590db`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180059106`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x180058b90`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x180058eb9`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x180058b90`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x180058eb9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059026`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059026`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059002`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059002`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180058bd4`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180058bf7`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180058c2c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180058efb`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180058f1e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180058f52`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180058bd4`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180058bf7`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180058c2c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180058efb`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180058f1e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180058f52`
- `OLEAUT32!__imp_SysFreeString` at `0x180059158`
- `OLEAUT32!__imp_SysFreeString` at `0x1800591c0`
- `OLEAUT32!__imp_SysFreeString` at `0x180059158`
- `OLEAUT32!__imp_SysFreeString` at `0x1800591c0`
- `OLEAUT32!__imp_SysStringLen` at `0x180059191`
- `OLEAUT32!__imp_SysStringLen` at `0x180059191`

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
  signed int Uri; // ebx
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
    dword_180159BE8 = IsFeatureEnabledInternal == 0;
    FCK::FEATURE_DISABLE_DATAURI_SUPPORT = 0;
  }
  if ( dword_180159BE8 )
  {
LABEL_26:
    v11 &= ~0x1000000u;
    if ( !ShouldUseEdge )
      goto LABEL_30;
  }
LABEL_27:
  InitOnceExecuteOnce(&stru_18015DE28, GlobalInitOnceUrlMon, 0, 0);
  if ( (dword_18015E75C & 1) == 0
    || (InitOnceExecuteOnce(&stru_18015DE28, GlobalInitOnceUrlMon, 0, 0), (dword_18015E75C & 2) == 0)
    && !(unsigned int)IsABrowserApp() )
  {
LABEL_30:
    v11 &= ~0x2000000u;
    if ( !ShouldUseEdge )
      goto LABEL_32;
  }
  InitOnceExecuteOnce(&stru_18015DE28, GlobalInitOnceUrlMon, 0, 0);
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
      if ( Uri == 1 && (Uri = CUString::Set((CUString *)&v48, v44, Uri_PROPERTY_RAW_URI), Uri == 1) )
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
    dword_180159BE8 = v43 == 0;
    FCK::FEATURE_DISABLE_DATAURI_SUPPORT = 0;
  }
  if ( dword_180159BE8 )
    goto LABEL_83;
LABEL_84:
  InitOnceExecuteOnce(&stru_18015DE28, GlobalInitOnceUrlMon, 0, 0);
  if ( (dword_18015E75C & 1) != 0 )
  {
    InitOnceExecuteOnce(&stru_18015DE28, GlobalInitOnceUrlMon, 0, 0);
    if ( (dword_18015E75C & 2) != 0 || (unsigned int)IsABrowserApp() )
      goto LABEL_88;
  }
LABEL_87:
  v10 &= ~0x2000000u;
  if ( v30 )
LABEL_88:
    InitOnceExecuteOnce(&stru_18015DE28, GlobalInitOnceUrlMon, 0, 0);
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
0x180058a30  mov     rax, rsp
0x180058a33  mov     [rax+8], rbx
0x180058a37  mov     [rax+18h], r8d
0x180058a3b  mov     [rax+10h], rdx
0x180058a3f  push    rbp
0x180058a40  push    rsi
0x180058a41  push    rdi
0x180058a42  push    r12
0x180058a44  push    r13
0x180058a46  push    r14
0x180058a48  push    r15
0x180058a4a  lea     rbp, [rax-47h]
0x180058a4e  sub     rsp, 90h
0x180058a55  mov     r13, [rbp+3Fh+pcchResult]
0x180058a59  xor     esi, esi
0x180058a5b  mov     [rbp+3Fh+var_58], rsi
0x180058a5f  mov     r12, rcx
0x180058a62  mov     [rbp+3Fh+var_50], 0Bh
0x180058a69  lea     rcx, ??_7CUString@@6B@; const CUString::`vftable'
0x180058a70  mov     [rbp+3Fh+var_60], rcx
0x180058a74  xorps   xmm0, xmm0
0x180058a77  mov     [rbp+3Fh+var_38], esi
0x180058a7a  mov     r15, r9
0x180058a7d  mov     [rbp+3Fh+ppURI], rsi
0x180058a81  mov     eax, r8d
0x180058a84  mov     [rbp+3Fh+var_80], rsi
0x180058a88  movdqu  xmmword ptr [rbp+3Fh+bstrString], xmm0
0x180058a8d  test    r13, r13
0x180058a90  jz      short loc_180058A96
0x180058a92  mov     [r13+0], esi
0x180058a96  mov     edi, eax
0x180058a98  mov     r14d, eax
0x180058a9b  shr     edi, 0Bh
0x180058a9e  and     edi, 20h
0x180058aa1  or      edi, 3002B85h
0x180058aa7  mov     ebx, edi
0x180058aa9  and     r14d, 8000000h
0x180058ab0  jz      short loc_180058AB9
0x180058ab2  btr     ebx, 8
0x180058ab6  or      ebx, 10h
0x180058ab9  mov     ecx, 110h
0x180058abe  mov     eax, ebx
0x180058ac0  and     eax, ecx
0x180058ac2  cmp     eax, ecx
0x180058ac4  jnz     loc_180058B90
0x180058aca  mov     ebx, 80070057h
0x180058acf  jmp     short loc_180058B1E
0x180058ad1  test    rdx, rdx
0x180058ad4  lea     rcx, [r15-2]
0x180058ad8  cmovnz  rcx, r15
0x180058adc  neg     rdx
0x180058adf  sbb     ebx, ebx
0x180058ae1  not     ebx
0x180058ae3  and     ebx, 8007007Ah
0x180058ae9  mov     [rcx], si
0x180058aec  mov     rcx, [rbp+3Fh+ppURI]
0x180058af0  test    rcx, rcx
0x180058af3  jz      short loc_180058B05
0x180058af5  mov     rax, [rcx]
0x180058af8  mov     rax, [rax+10h]
0x180058afc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058b01  mov     [rbp+3Fh+ppURI], rsi
0x180058b05  mov     rcx, [rbp+3Fh+var_80]
0x180058b09  test    rcx, rcx
0x180058b0c  jz      short loc_180058B1E
0x180058b0e  mov     rax, [rcx]
0x180058b11  mov     rax, [rax+10h]
0x180058b15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058b1a  mov     [rbp+3Fh+var_80], rsi
0x180058b1e  cmp     [rbp+3Fh+var_58], rsi
0x180058b22  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x180058b29  mov     edi, esi
0x180058b2b  mov     [rbp+3Fh+var_60], rax
0x180058b2f  setnz   dil
0x180058b33  mov     eax, esi
0x180058b35  cmp     [rbp+3Fh+var_50], 0Bh
0x180058b39  setnz   al
0x180058b3c  test    edi, edi
0x180058b3e  jz      short loc_180058B8A
0x180058b40  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x180058b44  test    rcx, rcx
0x180058b47  jnz     loc_1800591C0
0x180058b4d  mov     [rbp+3Fh+bstrString+8], rsi
0x180058b51  mov     [rbp+3Fh+var_38], esi
0x180058b54  test    edi, edi
0x180058b56  jz      short loc_180058B6D
0x180058b58  mov     rcx, [rbp+3Fh+var_58]
0x180058b5c  test    rcx, rcx
0x180058b5f  jz      short loc_180058B6D
0x180058b61  mov     rax, [rcx]
0x180058b64  mov     rax, [rax+10h]
0x180058b68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058b6d  mov     eax, ebx
0x180058b6f  mov     rbx, [rsp+0C0h+arg_0]
0x180058b77  add     rsp, 90h
0x180058b7e  pop     r15
0x180058b80  pop     r14
0x180058b82  pop     r13
0x180058b84  pop     r12
0x180058b86  pop     rdi
0x180058b87  pop     rsi
0x180058b88  pop     rbp
0x180058b89  retn
0x180058b8a  test    eax, eax
0x180058b8c  jz      short loc_180058B6D
0x180058b8e  jmp     short loc_180058B40
0x180058b90  call    cs:__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ; InternalForkingSupport_ShouldUseEdge(void)
0x180058b96  mov     sil, al
0x180058b99  test    al, al
0x180058b9b  jz      short loc_180058BB7
0x180058b9d  mov     rcx, cs:?FEATURE_DISABLE_DATAURI_SUPPORT@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_DISABLE_DATAURI_SUPPORT
0x180058ba4  test    rcx, rcx
0x180058ba7  jnz     loc_1800590DB
0x180058bad  mov     eax, cs:dword_180159BE8
0x180058bb3  test    eax, eax
0x180058bb5  jz      short loc_180058BC0
0x180058bb7  btr     ebx, 18h
0x180058bbb  test    sil, sil
0x180058bbe  jz      short loc_180058C0F
0x180058bc0  xor     r9d, r9d; Context
0x180058bc3  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180058bca  xor     r8d, r8d; Parameter
0x180058bcd  lea     rcx, stru_18015DE28; InitOnce
0x180058bd4  call    cs:__imp_InitOnceExecuteOnce
0x180058bda  test    byte ptr cs:dword_18015E75C, 1
0x180058be1  jz      short loc_180058C0F
0x180058be3  xor     r9d, r9d; Context
0x180058be6  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180058bed  xor     r8d, r8d; Parameter
0x180058bf0  lea     rcx, stru_18015DE28; InitOnce
0x180058bf7  call    cs:__imp_InitOnceExecuteOnce
0x180058bfd  test    byte ptr cs:dword_18015E75C, 2
0x180058c04  jnz     short loc_180058C18
0x180058c06  call    ?IsABrowserApp@@YAHXZ; IsABrowserApp(void)
0x180058c0b  test    eax, eax
0x180058c0d  jnz     short loc_180058C18
0x180058c0f  btr     ebx, 19h
0x180058c13  test    sil, sil
0x180058c16  jz      short loc_180058C32
0x180058c18  xor     r9d, r9d; Context
0x180058c1b  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180058c22  xor     r8d, r8d; Parameter
0x180058c25  lea     rcx, stru_18015DE28; InitOnce
0x180058c2c  call    cs:__imp_InitOnceExecuteOnce
0x180058c32  mov     r8d, 2000000h
0x180058c38  lea     r9, [rbp+3Fh+ppURI]; ppURI
0x180058c3c  xor     esi, esi
0x180058c3e  mov     edx, ebx
0x180058c40  bts     edx, 8
0x180058c44  test    ebx, 110h
0x180058c4a  cmovnz  edx, ebx
0x180058c4d  mov     ecx, edx
0x180058c4f  or      ecx, r8d
0x180058c52  test    r8d, edx
0x180058c55  mov     r8d, 1000000h
0x180058c5b  cmovnz  ecx, edx
0x180058c5e  mov     edx, ecx
0x180058c60  or      edx, r8d
0x180058c63  test    r8d, ecx
0x180058c66  cmovnz  edx, ecx; dwFlags
0x180058c69  xor     r8d, r8d; dwReserved
0x180058c6c  mov     rcx, r12; pwzURI
0x180058c6f  call    cs:__imp_CreateUri
0x180058c75  mov     ebx, eax
0x180058c77  test    eax, eax
0x180058c79  js      loc_180058AEC
0x180058c7f  mov     [rbp+3Fh+var_80], rsi
0x180058c83  mov     ecx, esi
0x180058c85  mov     [rbp+3Fh+pcchResult], rcx
0x180058c89  test    r14d, r14d
0x180058c8c  jz      short loc_180058C95
0x180058c8e  btr     edi, 8
0x180058c92  or      edi, 10h
0x180058c95  mov     r12d, 110h
0x180058c9b  mov     eax, edi
0x180058c9d  and     eax, r12d
0x180058ca0  mov     r14d, 80070057h
0x180058ca6  cmp     eax, r12d
0x180058ca9  jnz     loc_180058EB1
0x180058caf  mov     ebx, r14d
0x180058cb2  jmp     short loc_180058D00
0x180058cb4  mov     rdi, [rbp+3Fh+var_70]
0x180058cb8  lock dec dword ptr [rbx+10h]
0x180058cbc  mov     eax, [rbp+3Fh+dwReserved]
0x180058cbf  lea     r9, [rbp+3Fh+var_80]
0x180058cc3  mov     r8d, [rbp+3Fh+arg_10]
0x180058cc7  mov     rdx, r12
0x180058cca  mov     rcx, [rbp+3Fh+var_68]
0x180058cce  mov     [rsp+38h], esi
0x180058cd2  mov     [rsp+0C0h+var_90], esi
0x180058cd6  mov     qword ptr [rsp+0C0h+var_98], rdi
0x180058cdb  mov     [rsp+0C0h+var_A0], rax
0x180058ce0  call    cs:__imp_PrivateCoInternetCombineIUri
0x180058ce6  mov     ebx, eax
0x180058ce8  test    rdi, rdi
0x180058ceb  jz      short loc_180058CFC
0x180058ced  mov     rax, [rdi]
0x180058cf0  mov     rcx, rdi
0x180058cf3  mov     rax, [rax+10h]
0x180058cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058cfc  mov     rcx, [rbp+3Fh+pcchResult]
0x180058d00  test    rcx, rcx
0x180058d03  jz      short loc_180058D11
0x180058d05  mov     rax, [rcx]
0x180058d08  mov     rax, [rax+10h]
0x180058d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058d11  test    ebx, ebx
0x180058d13  js      loc_180058AEC
0x180058d19  mov     rdi, [rbp+3Fh+var_80]
0x180058d1d  mov     ebx, esi
0x180058d1f  cmp     rdi, [rbp+3Fh+var_58]
0x180058d23  setnz   sil
0x180058d27  xor     eax, eax
0x180058d29  cmp     [rbp+3Fh+var_50], eax
0x180058d2c  mov     r12d, eax
0x180058d2f  setnz   r12b
0x180058d33  test    esi, esi
0x180058d35  jz      loc_180058EA3
0x180058d3b  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x180058d3f  test    rcx, rcx
0x180058d42  jnz     loc_180059158
0x180058d48  mov     [rbp+3Fh+bstrString+8], rax
0x180058d4c  mov     [rbp+3Fh+var_38], eax
0x180058d4f  test    esi, esi
0x180058d51  jz      short loc_180058D6E
0x180058d53  mov     rcx, [rbp+3Fh+var_58]
0x180058d57  test    rcx, rcx
0x180058d5a  jz      short loc_180058D6E
0x180058d5c  mov     rax, [rcx]
0x180058d5f  mov     rax, [rax+10h]
0x180058d63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058d68  xor     eax, eax
0x180058d6a  mov     [rbp+3Fh+var_58], rax
0x180058d6e  mov     [rbp+3Fh+var_50], eax
0x180058d71  test    rdi, rdi
0x180058d74  jnz     short loc_180058DEC
0x180058d76  xor     esi, esi
0x180058d78  test    ebx, ebx
0x180058d7a  js      loc_180058AEC
0x180058d80  mov     ecx, [rbp+3Fh+var_38]
0x180058d83  mov     eax, [rbp+3Fh+cchResult]
0x180058d86  cmp     eax, ecx
0x180058d88  jbe     loc_18005912B
0x180058d8e  test    r13, r13
0x180058d91  jnz     loc_180058E9A
0x180058d97  mov     rdx, rax
0x180058d9a  mov     r8d, 7FFFFFFEh
0x180058da0  dec     eax
0x180058da2  cmp     eax, r8d
0x180058da5  ja      loc_1800591AB
0x180058dab  cmp     ecx, r8d
0x180058dae  ja      loc_18005919F
0x180058db4  mov     rax, rcx
0x180058db7  mov     rcx, [rbp+3Fh+bstrString+8]
0x180058dbb  test    rax, rax
0x180058dbe  jz      loc_180058AD1
0x180058dc4  movzx   r8d, word ptr [rcx]
0x180058dc8  test    r8w, r8w
0x180058dcc  jz      loc_180058AD1
0x180058dd2  mov     [r15], r8w
0x180058dd6  add     rcx, 2
0x180058dda  add     r15, 2
0x180058dde  dec     rax
0x180058de1  sub     rdx, 1
0x180058de5  jnz     short loc_180058DBB
0x180058de7  jmp     loc_180058AD1
0x180058dec  test    r12d, r12d
0x180058def  jz      loc_180059141
0x180058df5  mov     [rbp+3Fh+pcchResult], rax
0x180058df9  lea     r8, [rbp+3Fh+pcchResult]
0x180058dfd  mov     rax, [rdi]
0x180058e00  lea     rdx, _GUID_50295b0c_6b79_4935_aed8_05d80ec86a60
0x180058e07  mov     rcx, rdi
0x180058e0a  mov     rax, [rax]
0x180058e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058e12  mov     edx, [rbp+3Fh+var_50]
0x180058e15  test    eax, eax
0x180058e17  js      loc_180059169
0x180058e1d  mov     rcx, [rbp+3Fh+pcchResult]
0x180058e21  lea     r9, [rbp+3Fh+var_38]
0x180058e25  lea     r8, [rbp+3Fh+bstrString+8]
0x180058e29  mov     rax, [rcx]
0x180058e2c  mov     rax, [rax+0E0h]
0x180058e33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058e38  mov     rcx, [rbp+3Fh+pcchResult]
0x180058e3c  mov     ebx, eax
0x180058e3e  mov     rax, [rcx]
0x180058e41  mov     rax, [rax+10h]
0x180058e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058e4a  test    esi, esi
0x180058e4c  jz      loc_1800590D4
0x180058e52  xor     esi, esi
0x180058e54  test    ebx, ebx
0x180058e56  js      short loc_180058E6B
0x180058e58  mov     [rbp+3Fh+var_58], rdi
0x180058e5c  mov     rcx, rdi
0x180058e5f  mov     rax, [rdi]
0x180058e62  mov     rax, [rax+8]
0x180058e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058e6b  cmp     ebx, 1
  ... truncated ...
```
