# CoInternetCombineUrlInternal

- ea: `0x18001dc50`
- end: `0x18001e4ca`
- name: `CoInternetCombineUrlInternal`
- size: `2170`
- prototype: `__int64 __fastcall(const WCHAR *, const WCHAR *, unsigned int, _WORD *, unsigned int, IUri *, DWORD_PTR dwReserved)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800ffef0`

## callees

- `0x180018bfc`
- `0x18001db50`
- `0x18001db94`
- `0x18001dc50`
- `0x180031480`
- `0x1800a5e20`
- `0x1801285e6`
- `0x180129010`

## import_xrefs

- `iertutil!CreateUri` at `0x18001dee7`
- `iertutil!CreateUri` at `0x18001e073`
- `iertutil!CreateUri` at `0x18001dee7`
- `iertutil!CreateUri` at `0x18001e073`
- `iertutil!PrivateCoInternetCombineIUri` at `0x18001e15e`
- `iertutil!PrivateCoInternetCombineIUri` at `0x18001e15e`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x18001e3b1`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x18001e3e2`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x18001e3b1`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x18001e3e2`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x18001ddb9`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x18001df40`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x18001ddb9`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x18001df40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e0d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e359`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e0d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e359`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e0a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e0a4`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001de04`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001de2d`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001de6c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001df8a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001dfb3`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001dff2`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001de04`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001de2d`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001de6c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001df8a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001dfb3`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001dff2`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e434`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e4b5`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e434`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e4b5`
- `OLEAUT32!__imp_SysStringLen` at `0x18001e471`
- `OLEAUT32!__imp_SysStringLen` at `0x18001e471`

## pseudocode

```c
__int64 __fastcall CoInternetCombineUrlInternal(
        const WCHAR *a1,
        const WCHAR *a2,
        unsigned int a3,
        _WORD *a4,
        unsigned int a5,
        IUri *a6,
        DWORD_PTR dwReserved)
{
  IUri *v7; // r12
  int v10; // edi
  int v11; // esi
  HRESULT v12; // esi
  _WORD *v13; // rcx
  BOOL v14; // ebx
  bool ShouldUseEdge; // r14
  DWORD v17; // edx
  bool v18; // si
  DWORD v19; // edx
  IUri *v20; // rsi
  void *v21; // rdi
  COInetSession *v22; // rax
  int v23; // r15d
  volatile signed __int32 *v24; // r14
  int v25; // eax
  __int64 v26; // rcx
  struct IUri *v27; // r14
  BOOL v28; // edi
  BOOL v29; // r15d
  __int64 v30; // rcx
  __int64 v31; // r8
  BSTR v32; // rdx
  __int64 v33; // rax
  struct IUriVtbl *lpVtbl; // rax
  COInetSession *v35; // rax
  int IsFeatureEnabledInternal; // eax
  int v37; // eax
  struct IUri *v38; // [rsp+40h] [rbp-49h] BYREF
  IUri *ppURI; // [rsp+48h] [rbp-41h] BYREF
  void *v40; // [rsp+50h] [rbp-39h] BYREF
  IUri *v41; // [rsp+58h] [rbp-31h]
  void **v42; // [rsp+60h] [rbp-29h] BYREF
  struct IUri *v43; // [rsp+68h] [rbp-21h]
  unsigned int v44; // [rsp+70h] [rbp-19h]
  BSTR bstrString[2]; // [rsp+78h] [rbp-11h] BYREF
  UINT v46[14]; // [rsp+88h] [rbp-1h] BYREF

  v7 = a6;
  v42 = &CUString::`vftable';
  v43 = 0;
  v44 = 11;
  v46[0] = 0;
  ppURI = 0;
  v38 = 0;
  *(_OWORD *)bstrString = 0;
  if ( a6 )
    LODWORD(a6->lpVtbl) = 0;
  v10 = (a3 >> 11) & 0x20 | 0x3002B85;
  v11 = v10;
  if ( (a3 & 0x8000000) != 0 )
    v11 = (a3 >> 11) & 0x20 | 0x3002A95;
  if ( (v11 & 0x110) == 0x110 )
  {
    v12 = -2147024809;
    goto LABEL_14;
  }
  ShouldUseEdge = InternalForkingSupport_ShouldUseEdge();
  if ( !ShouldUseEdge )
  {
LABEL_26:
    v11 &= ~0x1000000u;
    if ( !ShouldUseEdge )
      goto LABEL_30;
    goto LABEL_27;
  }
  if ( FCK::FEATURE_DISABLE_DATAURI_SUPPORT )
  {
    IsFeatureEnabledInternal = CoInternetIsFeatureEnabledInternal();
    if ( IsFeatureEnabledInternal < 0 )
      goto LABEL_27;
    dword_180166BE8 = IsFeatureEnabledInternal == 0;
    FCK::FEATURE_DISABLE_DATAURI_SUPPORT = 0;
  }
  if ( dword_180166BE8 )
    goto LABEL_26;
LABEL_27:
  InitOnceExecuteOnce(&stru_18016AF28, GlobalInitOnceUrlMon, 0, 0);
  if ( (dword_18016B858 & 1) != 0 )
  {
    InitOnceExecuteOnce(&stru_18016AF28, GlobalInitOnceUrlMon, 0, 0);
    if ( (dword_18016B858 & 2) != 0 || (unsigned int)IsABrowserApp() )
    {
LABEL_31:
      InitOnceExecuteOnce(&stru_18016AF28, GlobalInitOnceUrlMon, 0, 0);
      if ( (dword_18016B858 & 4) != 0 )
        goto LABEL_32;
      goto LABEL_51;
    }
  }
LABEL_30:
  v11 &= ~0x2000000u;
  if ( ShouldUseEdge )
    goto LABEL_31;
LABEL_51:
  v11 &= ~0x8000000u;
LABEL_32:
  if ( (v11 & 0x110) == 0 )
    v11 |= 0x100u;
  v17 = v11 | 0x80;
  if ( (v11 & 0xC0) != 0 )
    v17 = v11;
  if ( (v17 & 0x600) == 0 )
    v17 |= 0x200u;
  if ( (v17 & 0x1800) == 0 )
    v17 |= 0x800u;
  if ( (v17 & 0x6000) == 0 )
    v17 |= 0x2000u;
  if ( (v17 & 0x2000000) == 0 )
    v17 |= 0x2000000u;
  if ( (v17 & 0x1000000) == 0 )
    v17 |= 0x1000000u;
  v12 = CreateUri(a1, v17, 0, &ppURI);
  if ( v12 < 0 )
    goto LABEL_10;
  v41 = ppURI;
  a6 = 0;
  v38 = 0;
  if ( (a3 & 0x8000000) != 0 )
    v10 = (a3 >> 11) & 0x20 | 0x3002A95;
  if ( (v10 & 0x110) == 0x110 )
  {
LABEL_50:
    v12 = -2147024809;
    goto LABEL_10;
  }
  v18 = InternalForkingSupport_ShouldUseEdge();
  if ( v18 )
  {
    if ( FCK::FEATURE_DISABLE_DATAURI_SUPPORT )
    {
      v37 = CoInternetIsFeatureEnabledInternal();
      if ( v37 < 0 )
        goto LABEL_56;
      dword_180166BE8 = v37 == 0;
      FCK::FEATURE_DISABLE_DATAURI_SUPPORT = 0;
    }
    if ( !dword_180166BE8 )
      goto LABEL_56;
  }
  v10 &= ~0x1000000u;
  if ( v18 )
  {
LABEL_56:
    InitOnceExecuteOnce(&stru_18016AF28, GlobalInitOnceUrlMon, 0, 0);
    if ( (dword_18016B858 & 1) != 0 )
    {
      InitOnceExecuteOnce(&stru_18016AF28, GlobalInitOnceUrlMon, 0, 0);
      if ( (dword_18016B858 & 2) != 0 || (unsigned int)IsABrowserApp() )
        goto LABEL_60;
    }
  }
  v10 &= ~0x2000000u;
  if ( !v18 )
  {
LABEL_127:
    v10 &= ~0x8000000u;
    goto LABEL_61;
  }
LABEL_60:
  InitOnceExecuteOnce(&stru_18016AF28, GlobalInitOnceUrlMon, 0, 0);
  if ( (dword_18016B858 & 4) == 0 )
    goto LABEL_127;
LABEL_61:
  if ( !a2 )
    goto LABEL_77;
  if ( (v10 & 0x110) == 0 )
    v10 |= 0x100u;
  v19 = v10 | 0x80;
  if ( (v10 & 0xC0) != 0 )
    v19 = v10;
  if ( (v19 & 0x600) == 0 )
    v19 |= 0x200u;
  if ( (v19 & 0x1800) == 0 )
    v19 |= 0x800u;
  if ( (v19 & 0x6000) == 0 )
    v19 |= 0x2000u;
  if ( (v19 & 0x2000000) == 0 )
    v19 |= 0x2000000u;
  if ( (v19 & 0x1000000) == 0 )
    v19 |= 0x1000000u;
  v12 = CreateUri(a2, v19, (unsigned int)dwReserved, &a6);
  if ( v12 >= 0 )
  {
LABEL_77:
    v20 = a6;
    if ( !a6 )
    {
      v12 = -2147418113;
      goto LABEL_10;
    }
    v40 = 0;
    v21 = 0;
    EnterCriticalSection(&g_mxsOInet);
    v22 = g_pCOInetSession;
    v23 = 0;
    if ( g_pCOInetSession
      || ((v35 = (COInetSession *)operator new(0x180u)) == 0 || (v22 = COInetSession::COInetSession(v35)) == 0
        ? (COInetSession *)(v22 = g_pCOInetSession, v23 = -2147024882)
        : (g_pCOInetSession = v22),
          v22) )
    {
      _InterlockedIncrement((volatile signed __int32 *)v22 + 4);
      v24 = (volatile signed __int32 *)g_pCOInetSession;
      LeaveCriticalSection(&g_mxsOInet);
      if ( !v23 )
      {
        if ( v24 )
        {
          if ( !memcmp_0(&GUID_79eac9ec_baf9_11ce_8c82_00aa004ba90b, &IID_IInternetProtocolInfo, 0x10u) )
          {
            v21 = (void *)(v24 + 2);
            v26 = (__int64)(v24 + 4);
            _InterlockedIncrement(v24 + 4);
          }
          else
          {
            v25 = COInetSession::QueryInterface((COInetSession *)v24, &GUID_79eac9ec_baf9_11ce_8c82_00aa004ba90b, &v40);
            v26 = (__int64)(v24 + 4);
            if ( !v25 )
              v21 = v40;
          }
        }
        else
        {
          v26 = 16;
        }
        _InterlockedDecrement((volatile signed __int32 *)v26);
      }
    }
    else
    {
      LeaveCriticalSection(&g_mxsOInet);
    }
    v12 = PrivateCoInternetCombineIUri(v41, v20, a3, &v38, (unsigned int)dwReserved, v21, 0, 0);
    if ( v21 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v21 + 16LL))(v21);
  }
  if ( a6 )
    ((void (__fastcall *)(IUri *))a6->lpVtbl->Release)(a6);
  if ( v12 < 0 )
    goto LABEL_10;
  v27 = v38;
  v12 = 0;
  v28 = v38 != v43;
  v29 = v44 != 0;
  if ( v38 != v43 || v44 )
  {
    if ( bstrString[0] )
    {
      SysFreeString(bstrString[0]);
      bstrString[0] = 0;
    }
    bstrString[1] = 0;
    v46[0] = 0;
    if ( v28 && v43 )
    {
      ((void (__fastcall *)(struct IUri *))v43->lpVtbl->Release)(v43);
      v43 = 0;
    }
  }
  v44 = 0;
  if ( v27 && (v29 || v28) )
  {
    lpVtbl = v27->lpVtbl;
    a6 = 0;
    if ( ((int (__fastcall *)(struct IUri *, GUID *, IUri **))lpVtbl->QueryInterface)(
           v27,
           &GUID_50295b0c_6b79_4935_aed8_05d80ec86a60,
           &a6) < 0 )
    {
      v12 = ((__int64 (__fastcall *)(struct IUri *, _QWORD, BSTR *, _QWORD))v27->lpVtbl->GetPropertyBSTR)(
              v27,
              v44,
              bstrString,
              0);
      if ( v12 >= 0 )
      {
        bstrString[1] = bstrString[0];
        v46[0] = SysStringLen(bstrString[0]);
      }
    }
    else
    {
      v12 = ((__int64 (__fastcall *)(IUri *, _QWORD, BSTR *, UINT *))a6->lpVtbl[1].QueryInterface)(
              a6,
              v44,
              &bstrString[1],
              v46);
      ((void (__fastcall *)(IUri *))a6->lpVtbl->Release)(a6);
    }
    if ( v28 && v12 >= 0 )
    {
      v43 = v27;
      ((void (__fastcall *)(struct IUri *))v27->lpVtbl->AddRef)(v27);
    }
    if ( v12 == 1 )
    {
      v12 = CUString::Set((CUString *)&v42, v38, Uri_PROPERTY_RAW_URI);
      if ( v12 == 1 )
      {
        v12 = -2146697214;
        goto LABEL_10;
      }
    }
  }
  if ( v12 >= 0 )
  {
    v30 = v46[0];
    if ( a5 <= v46[0] )
    {
      if ( v7 )
        LODWORD(v7->lpVtbl) = v46[0] + 1;
      v12 = -2147467261;
      goto LABEL_10;
    }
    if ( v7 )
      LODWORD(v7->lpVtbl) = v46[0];
    v31 = a5;
    if ( a5 - 1 > 0x7FFFFFFE )
    {
      v12 = -2147024809;
      if ( a5 )
        *a4 = 0;
      goto LABEL_10;
    }
    if ( (unsigned int)v30 <= 0x7FFFFFFE )
    {
      v32 = bstrString[1];
      v33 = v30;
      do
      {
        if ( !v33 )
          break;
        if ( !*v32 )
          break;
        *a4++ = *v32++;
        --v33;
        --v31;
      }
      while ( v31 );
      v13 = a4 - 1;
      v12 = -2147024774;
      if ( v31 )
      {
        v13 = a4;
        v12 = 0;
      }
      *v13 = 0;
      goto LABEL_10;
    }
    *a4 = 0;
    goto LABEL_50;
  }
LABEL_10:
  if ( ppURI )
  {
    ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
    ppURI = 0;
  }
  if ( v38 )
  {
    ((void (__fastcall *)(struct IUri *))v38->lpVtbl->Release)(v38);
    v38 = 0;
  }
LABEL_14:
  v42 = &CUString::`vftable';
  v14 = v43 != 0;
  if ( v43 || v44 != 11 )
  {
    if ( bstrString[0] )
    {
      SysFreeString(bstrString[0]);
      bstrString[0] = 0;
    }
    bstrString[1] = 0;
    v46[0] = 0;
    if ( v14 && v43 )
      ((void (__fastcall *)(struct IUri *))v43->lpVtbl->Release)(v43);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001dc50  mov     [rsp-8+arg_10], rbx
0x18001dc55  mov     [rsp-8+arg_8], rdx
0x18001dc5a  mov     [rsp-8+pwzURI], rcx
0x18001dc5f  push    rbp
0x18001dc60  push    rsi
0x18001dc61  push    rdi
0x18001dc62  push    r12
0x18001dc64  push    r13
0x18001dc66  push    r14
0x18001dc68  push    r15
0x18001dc6a  lea     rbp, [rsp-7]
0x18001dc6f  sub     rsp, 90h
0x18001dc76  mov     r12, [rbp+37h+arg_28]
0x18001dc7a  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x18001dc81  xor     r14d, r14d
0x18001dc84  mov     [rbp+37h+var_60], rax
0x18001dc88  mov     [rbp+37h+var_58], r14
0x18001dc8c  xorps   xmm0, xmm0
0x18001dc8f  mov     [rbp+37h+var_50], 0Bh
0x18001dc96  mov     rbx, r9
0x18001dc99  mov     [rbp+37h+var_38], r14d
0x18001dc9d  mov     r13d, r8d
0x18001dca0  mov     [rbp+37h+ppURI], r14
0x18001dca4  mov     [rbp+37h+var_80], r14
0x18001dca8  movdqu  xmmword ptr [rbp+37h+bstrString], xmm0
0x18001dcad  test    r12, r12
0x18001dcb0  jz      short loc_18001DCB6
0x18001dcb2  mov     [r12], r14d
0x18001dcb6  mov     edi, r13d
0x18001dcb9  mov     r15d, r13d
0x18001dcbc  shr     edi, 0Bh
0x18001dcbf  and     edi, 20h
0x18001dcc2  or      edi, 3002B85h
0x18001dcc8  mov     esi, edi
0x18001dcca  and     r15d, 8000000h
0x18001dcd1  jz      short loc_18001DCDA
0x18001dcd3  btr     esi, 8
0x18001dcd7  or      esi, 10h
0x18001dcda  mov     eax, esi
0x18001dcdc  and     eax, 110h
0x18001dce1  cmp     eax, 110h
0x18001dce6  jnz     loc_18001DDB9
0x18001dcec  mov     esi, 80070057h
0x18001dcf1  jmp     short loc_18001DD43
0x18001dcf3  test    r8, r8
0x18001dcf6  lea     rcx, [rbx-2]
0x18001dcfa  mov     esi, 8007007Ah
0x18001dcff  cmovnz  rcx, rbx
0x18001dd03  xor     r14d, r14d
0x18001dd06  test    r8, r8
0x18001dd09  cmovnz  esi, r14d
0x18001dd0d  mov     [rcx], r14w
0x18001dd11  mov     rcx, [rbp+37h+ppURI]
0x18001dd15  test    rcx, rcx
0x18001dd18  jz      short loc_18001DD2A
0x18001dd1a  mov     rax, [rcx]
0x18001dd1d  mov     rax, [rax+10h]
0x18001dd21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd26  mov     [rbp+37h+ppURI], r14
0x18001dd2a  mov     rcx, [rbp+37h+var_80]
0x18001dd2e  test    rcx, rcx
0x18001dd31  jz      short loc_18001DD43
0x18001dd33  mov     rax, [rcx]
0x18001dd36  mov     rax, [rax+10h]
0x18001dd3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd3f  mov     [rbp+37h+var_80], r14
0x18001dd43  cmp     [rbp+37h+var_58], 0
0x18001dd48  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x18001dd4f  mov     ebx, r14d
0x18001dd52  mov     [rbp+37h+var_60], rax
0x18001dd56  setnz   bl
0x18001dd59  mov     eax, r14d
0x18001dd5c  cmp     [rbp+37h+var_50], 0Bh
0x18001dd60  setnz   al
0x18001dd63  test    ebx, ebx
0x18001dd65  jz      short loc_18001DDB3
0x18001dd67  mov     rcx, [rbp+37h+bstrString]; bstrString
0x18001dd6b  test    rcx, rcx
0x18001dd6e  jnz     loc_18001E4B5
0x18001dd74  mov     [rbp+37h+bstrString+8], r14
0x18001dd78  mov     [rbp+37h+var_38], r14d
0x18001dd7c  test    ebx, ebx
0x18001dd7e  jz      short loc_18001DD95
0x18001dd80  mov     rcx, [rbp+37h+var_58]
0x18001dd84  test    rcx, rcx
0x18001dd87  jz      short loc_18001DD95
0x18001dd89  mov     rax, [rcx]
0x18001dd8c  mov     rax, [rax+10h]
0x18001dd90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd95  mov     rbx, [rsp+0C0h+arg_10]
0x18001dd9d  mov     eax, esi
0x18001dd9f  add     rsp, 90h
0x18001dda6  pop     r15
0x18001dda8  pop     r14
0x18001ddaa  pop     r13
0x18001ddac  pop     r12
0x18001ddae  pop     rdi
0x18001ddaf  pop     rsi
0x18001ddb0  pop     rbp
0x18001ddb1  retn
0x18001ddb3  test    eax, eax
0x18001ddb5  jz      short loc_18001DD95
0x18001ddb7  jmp     short loc_18001DD67
0x18001ddb9  call    cs:__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ; InternalForkingSupport_ShouldUseEdge(void)
0x18001ddc0  nop     dword ptr [rax+rax+00h]
0x18001ddc5  movzx   r14d, al
0x18001ddc9  test    al, al
0x18001ddcb  jz      short loc_18001DDE7
0x18001ddcd  mov     rcx, cs:?FEATURE_DISABLE_DATAURI_SUPPORT@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_DISABLE_DATAURI_SUPPORT
0x18001ddd4  test    rcx, rcx
0x18001ddd7  jnz     loc_18001E3B1
0x18001dddd  mov     eax, cs:dword_180166BE8
0x18001dde3  test    eax, eax
0x18001dde5  jz      short loc_18001DDF0
0x18001dde7  btr     esi, 18h
0x18001ddeb  test    r14b, r14b
0x18001ddee  jz      short loc_18001DE4B
0x18001ddf0  xor     r9d, r9d; Context
0x18001ddf3  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001ddfa  xor     r8d, r8d; Parameter
0x18001ddfd  lea     rcx, stru_18016AF28; InitOnce
0x18001de04  call    cs:__imp_InitOnceExecuteOnce
0x18001de0b  nop     dword ptr [rax+rax+00h]
0x18001de10  test    byte ptr cs:dword_18016B858, 1
0x18001de17  jz      short loc_18001DE4B
0x18001de19  xor     r9d, r9d; Context
0x18001de1c  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001de23  xor     r8d, r8d; Parameter
0x18001de26  lea     rcx, stru_18016AF28; InitOnce
0x18001de2d  call    cs:__imp_InitOnceExecuteOnce
0x18001de34  nop     dword ptr [rax+rax+00h]
0x18001de39  test    byte ptr cs:dword_18016B858, 2
0x18001de40  jnz     short loc_18001DE58
0x18001de42  call    ?IsABrowserApp@@YAHXZ; IsABrowserApp(void)
0x18001de47  test    eax, eax
0x18001de49  jnz     short loc_18001DE58
0x18001de4b  btr     esi, 19h
0x18001de4f  test    r14b, r14b
0x18001de52  jz      loc_18001DF37
0x18001de58  xor     r9d, r9d; Context
0x18001de5b  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001de62  xor     r8d, r8d; Parameter
0x18001de65  lea     rcx, stru_18016AF28; InitOnce
0x18001de6c  call    cs:__imp_InitOnceExecuteOnce
0x18001de73  nop     dword ptr [rax+rax+00h]
0x18001de78  test    byte ptr cs:dword_18016B858, 4
0x18001de7f  jz      loc_18001DF37
0x18001de85  mov     eax, esi
0x18001de87  bts     eax, 8
0x18001de8b  test    esi, 110h
0x18001de91  cmovz   esi, eax
0x18001de94  mov     edx, esi
0x18001de96  bts     edx, 7
0x18001de9a  test    sil, 0C0h
0x18001de9e  cmovnz  edx, esi
0x18001dea1  mov     eax, edx
0x18001dea3  bts     eax, 9
0x18001dea7  test    edx, 600h
0x18001dead  cmovz   edx, eax
0x18001deb0  test    edx, 1800h
0x18001deb6  jnz     short loc_18001DEBC
0x18001deb8  bts     edx, 0Bh
0x18001debc  test    edx, 6000h
0x18001dec2  jnz     short loc_18001DEC8
0x18001dec4  bts     edx, 0Dh
0x18001dec8  bt      edx, 19h
0x18001decc  jb      short loc_18001DED2
0x18001dece  bts     edx, 19h
0x18001ded2  bt      edx, 18h
0x18001ded6  jb      short loc_18001DEDC
0x18001ded8  bts     edx, 18h; dwFlags
0x18001dedc  mov     rcx, [rbp+37h+pwzURI]; pwzURI
0x18001dee0  lea     r9, [rbp+37h+ppURI]; ppURI
0x18001dee4  xor     r8d, r8d; dwReserved
0x18001dee7  call    cs:__imp_CreateUri
0x18001deee  nop     dword ptr [rax+rax+00h]
0x18001def3  xor     r14d, r14d
0x18001def6  mov     esi, eax
0x18001def8  test    eax, eax
0x18001defa  js      loc_18001DD11
0x18001df00  mov     rax, [rbp+37h+ppURI]
0x18001df04  mov     [rbp+37h+var_68], rax
0x18001df08  mov     eax, edi
0x18001df0a  btr     eax, 8
0x18001df0e  mov     [rbp+37h+arg_28], r14
0x18001df12  or      eax, 10h
0x18001df15  mov     [rbp+37h+var_80], r14
0x18001df19  test    r15d, r15d
0x18001df1c  cmovnz  edi, eax
0x18001df1f  mov     eax, edi
0x18001df21  and     eax, 110h
0x18001df26  cmp     eax, 110h
0x18001df2b  jnz     short loc_18001DF40
0x18001df2d  mov     esi, 80070057h
0x18001df32  jmp     loc_18001DD11
0x18001df37  btr     esi, 1Bh
0x18001df3b  jmp     loc_18001DE85
0x18001df40  call    cs:__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ; InternalForkingSupport_ShouldUseEdge(void)
0x18001df47  nop     dword ptr [rax+rax+00h]
0x18001df4c  movzx   esi, al
0x18001df4f  test    al, al
0x18001df51  jz      short loc_18001DF6D
0x18001df53  mov     rcx, cs:?FEATURE_DISABLE_DATAURI_SUPPORT@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_DISABLE_DATAURI_SUPPORT
0x18001df5a  test    rcx, rcx
0x18001df5d  jnz     loc_18001E3E2
0x18001df63  mov     eax, cs:dword_180166BE8
0x18001df69  test    eax, eax
0x18001df6b  jz      short loc_18001DF76
0x18001df6d  btr     edi, 18h
0x18001df71  test    sil, sil
0x18001df74  jz      short loc_18001DFD1
0x18001df76  xor     r9d, r9d; Context
0x18001df79  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001df80  xor     r8d, r8d; Parameter
0x18001df83  lea     rcx, stru_18016AF28; InitOnce
0x18001df8a  call    cs:__imp_InitOnceExecuteOnce
0x18001df91  nop     dword ptr [rax+rax+00h]
0x18001df96  test    byte ptr cs:dword_18016B858, 1
0x18001df9d  jz      short loc_18001DFD1
0x18001df9f  xor     r9d, r9d; Context
0x18001dfa2  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001dfa9  xor     r8d, r8d; Parameter
0x18001dfac  lea     rcx, stru_18016AF28; InitOnce
0x18001dfb3  call    cs:__imp_InitOnceExecuteOnce
0x18001dfba  nop     dword ptr [rax+rax+00h]
0x18001dfbf  test    byte ptr cs:dword_18016B858, 2
0x18001dfc6  jnz     short loc_18001DFDE
0x18001dfc8  call    ?IsABrowserApp@@YAHXZ; IsABrowserApp(void)
0x18001dfcd  test    eax, eax
0x18001dfcf  jnz     short loc_18001DFDE
0x18001dfd1  btr     edi, 19h
0x18001dfd5  test    sil, sil
0x18001dfd8  jz      loc_18001E390
0x18001dfde  xor     r9d, r9d; Context
0x18001dfe1  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001dfe8  xor     r8d, r8d; Parameter
0x18001dfeb  lea     rcx, stru_18016AF28; InitOnce
0x18001dff2  call    cs:__imp_InitOnceExecuteOnce
0x18001dff9  nop     dword ptr [rax+rax+00h]
0x18001dffe  test    byte ptr cs:dword_18016B858, 4
0x18001e005  jz      loc_18001E390
0x18001e00b  mov     rcx, [rbp+37h+arg_8]; pwzURI
0x18001e00f  test    rcx, rcx
0x18001e012  jz      short loc_18001E089
0x18001e014  mov     eax, edi
0x18001e016  bts     eax, 8
0x18001e01a  test    edi, 110h
0x18001e020  cmovz   edi, eax
0x18001e023  mov     edx, edi
0x18001e025  bts     edx, 7
0x18001e029  test    dil, 0C0h
0x18001e02d  cmovnz  edx, edi
0x18001e030  mov     eax, edx
0x18001e032  bts     eax, 9
0x18001e036  test    edx, 600h
0x18001e03c  cmovz   edx, eax
0x18001e03f  test    edx, 1800h
0x18001e045  jnz     short loc_18001E04B
0x18001e047  bts     edx, 0Bh
0x18001e04b  test    edx, 6000h
0x18001e051  jnz     short loc_18001E057
0x18001e053  bts     edx, 0Dh
0x18001e057  bt      edx, 19h
0x18001e05b  jb      short loc_18001E061
0x18001e05d  bts     edx, 19h
0x18001e061  bt      edx, 18h
0x18001e065  jb      short loc_18001E06B
0x18001e067  bts     edx, 18h; dwFlags
0x18001e06b  mov     r8d, dword ptr [rbp+37h+dwReserved]; dwReserved
0x18001e06f  lea     r9, [rbp+37h+arg_28]; ppURI
0x18001e073  call    cs:__imp_CreateUri
0x18001e07a  nop     dword ptr [rax+rax+00h]
0x18001e07f  mov     esi, eax
0x18001e081  test    eax, eax
0x18001e083  js      loc_18001E180
0x18001e089  mov     rsi, [rbp+37h+arg_28]
0x18001e08d  test    rsi, rsi
0x18001e090  jz      loc_18001E4AB
0x18001e096  lea     rcx, ?g_mxsOInet@@3VCMutexSem@@A; lpCriticalSection
0x18001e09d  mov     [rbp+37h+var_70], r14
0x18001e0a1  mov     rdi, r14
0x18001e0a4  call    cs:__imp_EnterCriticalSection
0x18001e0ab  nop     dword ptr [rax+rax+00h]
0x18001e0b0  mov     rax, cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA; COInetSession * g_pCOInetSession
0x18001e0b7  mov     r15d, r14d
0x18001e0ba  test    rax, rax
0x18001e0bd  jz      loc_18001E326
0x18001e0c3  lock inc dword ptr [rax+10h]
0x18001e0c7  mov     r14, cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA; COInetSession * g_pCOInetSession
0x18001e0ce  lea     rcx, ?g_mxsOInet@@3VCMutexSem@@A; lpCriticalSection
0x18001e0d5  call    cs:__imp_LeaveCriticalSection
0x18001e0dc  nop     dword ptr [rax+rax+00h]
0x18001e0e1  test    r15d, r15d
0x18001e0e4  jnz     loc_18001E36A
0x18001e0ea  test    r14, r14
0x18001e0ed  jz      loc_18001E3A8
0x18001e0f3  mov     r8d, 10h; Size
0x18001e0f9  lea     rdx, IID_IInternetProtocolInfo; Buf2
0x18001e100  lea     rcx, _GUID_79eac9ec_baf9_11ce_8c82_00aa004ba90b; Buf1
0x18001e107  call    memcmp_0
  ... truncated ...
```
