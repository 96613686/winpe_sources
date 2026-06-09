# HandleAcquireTokensWithNGC(IServiceExecutionContext *,void * const,unsigned __int64,ulong,_WLIDRequestParams * const,long *,long *,long *,_WLIDResponseParams * *,ushort const *,unsigned __int64,ushort const *,long *,ulong *)

- ea: `0x18002a57c`
- end: `0x18002acc4`
- name: `?HandleAcquireTokensWithNGC@@YAJPEAVIServiceExecutionContext@@QEAX_KKQEAU_WLIDRequestParams@@PEAJ44PEAPEAU_WLIDResponseParams@@PEBG264PEAK@Z`
- size: `1864`
- prototype: `int(struct IServiceExecutionContext *, void *const, unsigned __int64, unsigned int, struct _WLIDRequestParams *const, int *, int *, int *, struct _WLIDResponseParams **, const unsigned __int16 *, unsigned __int64, const unsigned __int16 *, int *, unsigned int *)`
- caller_count: `1`
- callee_count: `29`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002a390`

## callees

- `0x18000141c`
- `0x18000ed04`
- `0x18000fd04`
- `0x180011e9c`
- `0x1800151c4`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001cf20`
- `0x18001f968`
- `0x180020970`
- `0x180020b10`
- `0x18002783c`
- `0x18002a57c`
- `0x18002d36c`
- `0x180043344`
- `0x18004a878`
- `0x18004d60c`
- `0x18004d8c4`
- `0x180050c20`
- `0x18005538c`
- `0x1800563d0`
- `0x1800768c0`
- `0x1800896b4`
- `0x180089e6c`
- `0x1800a3b60`
- `0x1800ae22c`
- `0x1800bbd14`
- `0x1800bc6c0`
- `0x180128010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002a88b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002a8ac`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002a8d0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002a88b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002a8ac`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002a8d0`

## string_xrefs

- `0x18002a66f`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18002a744`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18002a7f7`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18002a97d`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18002abda`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18002ac45`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18002a616`: `AcquireTokens`
- `0x18002a64a`: `HandleAcquireTokensWithNGC`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall HandleAcquireTokensWithNGC(
        struct IServiceExecutionContext *a1,
        void *const a2,
        __int64 a3,
        unsigned int a4,
        struct _WLIDRequestParams *const a5,
        int *a6,
        int *a7,
        int *a8,
        struct _WLIDResponseParams **a9,
        unsigned __int16 *a10,
        unsigned __int64 a11,
        unsigned __int16 *a12,
        int *a13,
        unsigned int *a14)
{
  __int64 v16; // rdi
  __int64 v17; // r14
  int LogonId; // eax
  unsigned int v19; // ebx
  __int64 v20; // rdx
  unsigned __int64 v21; // r9
  struct CSingleIdentity *v22; // rbx
  int v23; // edi
  __int64 v24; // rdx
  unsigned __int64 v25; // rdi
  char v26; // r14
  char v27; // r15
  CAutoFreeWLIDResponse *v28; // rcx
  unsigned int v29; // r8d
  int v30; // eax
  struct _WLIDResponseParams *v31; // rcx
  __int64 v32; // rdi
  __int64 *v33; // rax
  __int64 v34; // rdi
  __int64 *v35; // rax
  int v36; // eax
  unsigned int v37; // edi
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // r9
  const unsigned __int16 *bIgnoreCase; // [rsp+20h] [rbp-E0h]
  unsigned int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  signed int v44; // [rsp+70h] [rbp-90h] BYREF
  LPCWCH v45; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v46; // [rsp+80h] [rbp-80h] BYREF
  struct CSingleIdentity *v47; // [rsp+88h] [rbp-78h] BYREF
  __int64 v48; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v49; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v50; // [rsp+A0h] [rbp-60h] BYREF
  LPCWCH lpString1; // [rsp+A8h] [rbp-58h] BYREF
  int v52; // [rsp+B0h] [rbp-50h]
  void *v53; // [rsp+B8h] [rbp-48h]
  int *v54; // [rsp+C0h] [rbp-40h]
  struct IServiceExecutionContext *v55; // [rsp+C8h] [rbp-38h]
  int *v56; // [rsp+D0h] [rbp-30h]
  unsigned __int16 *v57; // [rsp+D8h] [rbp-28h]
  unsigned __int16 *v58; // [rsp+E0h] [rbp-20h]
  int *v59; // [rsp+E8h] [rbp-18h]
  int *v60; // [rsp+F0h] [rbp-10h]
  struct _WLIDRequestParams *v61; // [rsp+F8h] [rbp-8h]
  __int64 v62; // [rsp+100h] [rbp+0h] BYREF
  __int64 v63[3]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v64[4]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v65[14]; // [rsp+140h] [rbp+40h] BYREF
  _QWORD v66[42]; // [rsp+1B0h] [rbp+B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+258h]

  v46 = a4;
  v53 = a2;
  v55 = a1;
  v61 = a5;
  v60 = a6;
  v59 = a7;
  v54 = a8;
  v58 = a10;
  v57 = a12;
  v56 = a13;
  wil::ActivityBase<MSAClientTraceTelemetry,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MSAClientTraceTelemetry,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v66,
    (__int64)"AcquireTokens");
  v66[0] = &MSAClientTraceTelemetry::AcquireTokens::`vftable';
  MSAClientTraceTelemetry::AcquireTokens::StartActivity((MSAClientTraceTelemetry::AcquireTokens *)v66);
  v44 = 0;
  v64[0] = "HandleAcquireTokensWithNGC";
  v64[1] = &v44;
  v64[2] = 0;
  v64[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    "HandleAcquireTokensWithNGC",
    (const char *)0x1399,
    0,
    bIgnoreCase);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v50);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v49);
  v45 = 0;
  v48 = 0;
  v47 = 0;
  v16 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 80LL))(a1);
  v17 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 56LL))(a1);
  if ( a9 )
    *a9 = 0;
  if ( a14 )
    *a14 = 0;
  SmartTelemetryJson::SmartTelemetryJson((SmartTelemetryJson *)v65, 0x2000000000LL, a3, L"wl");
  v65[0] = &SmartAcquireTokensTelemetryJson::`vftable';
  v65[12] = a9;
  v65[13] = a14;
  LogonId = CAutoImpersonateClient::ImpersonateClient((CAutoImpersonateClient *)&v48, 0);
  v19 = LogonId;
  if ( LogonId < 0 )
  {
    v20 = 5047;
LABEL_9:
    v21 = (unsigned int)LogonId;
    goto LABEL_10;
  }
  LogonId = CAutoImpersonateClient::GetLogonId((CAutoImpersonateClient *)&v48, (struct _LUID *)&v45);
  v19 = LogonId;
  if ( LogonId < 0 )
  {
    v20 = 5048;
    goto LABEL_9;
  }
  LogonId = CIdentityStore::GetSingleIdentity((__int64)g_pPPCRL + 496, &v45, (__int64)v53, &v47);
  v19 = LogonId;
  if ( LogonId < 0 )
  {
    v20 = 5049;
    goto LABEL_9;
  }
  LogonId = (*(__int64 (__fastcall **)(__int64, __int64 *, unsigned __int16 **))(*(_QWORD *)v16 + 72LL))(
              v16,
              &v48,
              &v49);
  v19 = LogonId;
  if ( LogonId < 0 )
  {
    v20 = 5050;
    goto LABEL_9;
  }
  v22 = v47;
  v23 = (*(__int64 (__fastcall **)(__int64, struct CSingleIdentity *, const wchar_t *, unsigned __int16 **))(*(_QWORD *)v17 + 112LL))(
          v17,
          v47,
          L"CID",
          &v50);
  if ( v23 < 0 )
  {
    v24 = 5051;
LABEL_69:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      (const char *)(unsigned int)v23,
      bIgnoreCasea);
    v19 = v23;
    goto LABEL_70;
  }
  v25 = a11;
  if ( (a3 & 0x80000000) != 0 )
  {
    if ( !a11 )
    {
      v19 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x13C1,
              (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
              (const char *)0x578,
              bIgnoreCasea);
      goto LABEL_70;
    }
    if ( *((_DWORD *)v50 - 4) && (int)SetNgcKeyName(a1, &v47, v50, v49) >= 0 )
      a3 &= ~0x80000000uLL;
  }
  v26 = 0;
  v52 = 0;
  (*(void (__fastcall **)(struct CSingleIdentity *, LPCWCH *))(*(_QWORD *)v22 + 16LL))(v22, &lpString1);
  (*(void (__fastcall **)(struct CSingleIdentity *, LPCWCH *))(*(_QWORD *)v22 + 24LL))(v22, &v45);
  v27 = 1;
  if ( CompareStringOrdinal(lpString1, -1, L"{CC553C39-4B1C-43DB-94A0-3B78F751ACEF}", -1, 1) == 2
    || CompareStringOrdinal(lpString1, -1, L"{7D629E2E-CC4C-4CC4-95B7-25C48B11C53D}", -1, 1) == 2
    || CompareStringOrdinal(
         v45,
         -1,
         L"S-1-15-2-278586202-1783374767-3755652818-1001658646-1865713925-2047498344-1799408599",
         -1,
         1) == 2
    || (a3 & 0x8000) != 0 )
  {
    v27 = 0;
  }
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v45);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&lpString1);
  while ( 1 )
  {
    if ( v26 )
    {
      v29 = *a14;
      *a14 = 0;
      CAutoFreeWLIDResponse::FreeWLIDResponseParams(v28, a9, v29);
    }
    v30 = HandleAcquireTokens(v53, (unsigned __int16 *)a3, v46, v61, v60, v59, v54, a9, v58, v25, v57, v56, a14);
    v44 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x13F7,
        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        (const char *)(unsigned int)v30,
        bIgnoreCasea);
      v30 = v44;
    }
    v26 = 0;
    if ( *v54 == -2147186517 || (v31 = *a9) != 0 && *((_DWORD *)v31 + 1) == -2147186517 )
    {
      v34 = (*(__int64 (__fastcall **)(struct CSingleIdentity *))(*(_QWORD *)v22 + 8LL))(v22);
      v63[2] = (__int64)&v45;
      v45 = 0;
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v45);
      v35 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              v63,
              L"ps:ngckn");
      v36 = CIdentityCredentialBag::StoreCredential(v34, v35, &v45);
      v37 = v36;
      if ( v36 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1403,
          (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          (const char *)(unsigned int)v36,
          bIgnoreCasea);
        SmartAcquireTokensTelemetryJson::~SmartAcquireTokensTelemetryJson((SmartAcquireTokensTelemetryJson *)v65);
        CAutoRefPtr<CSingleIdentity>::Deinit(&v47);
        CAutoImpersonateClient::~CAutoImpersonateClient((CAutoImpersonateClient *)&v48);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v49);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v50);
        CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v64);
        MSAClientTraceTelemetry::AcquireTokens::~AcquireTokens((MSAClientTraceTelemetry::AcquireTokens *)v66);
        return v37;
      }
      v27 = 0;
      v23 = RemoveMSAIDPKeyIfSecondaryOrAssociated(v55, v22, v50, v49, 1);
      if ( v23 < 0 )
      {
        v24 = 5131;
        goto LABEL_69;
      }
      goto LABEL_55;
    }
    if ( v30 == -2146893778 )
    {
      v32 = (*(__int64 (__fastcall **)(struct CSingleIdentity *))(*(_QWORD *)v22 + 8LL))(v22);
      v63[1] = (__int64)&lpString1;
      lpString1 = 0;
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&lpString1);
      v33 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              &v62,
              L"ps:ngckn");
      v23 = CIdentityCredentialBag::StoreCredential(v32, v33, &lpString1);
      if ( v23 < 0 )
      {
        v24 = 5140;
        goto LABEL_69;
      }
      v27 = 0;
      a3 |= 0x80000000uLL;
      v26 = 1;
LABEL_55:
      v25 = a11;
      goto LABEL_56;
    }
    if ( v25
      && v27 == 1
      && (v30 == -2147186612
       || v30 == -2147186642
       || v30 == -2147186500
       || v30 == -2147186552
       || v30 >= 0 && (*v54 == -2147186459 || *v54 >= 0 && v31 && *((_DWORD *)v31 + 1) == -2147186459))
      && *((_DWORD *)v50 - 4) )
    {
      break;
    }
LABEL_57:
    v28 = (CAutoFreeWLIDResponse *)(unsigned int)(v52 + 1);
    v52 = (int)v28;
    if ( (int)v28 > 10 )
    {
      if ( (unsigned int)dword_1801C2080 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_1801C2080, 0x400000000000LL) )
        {
          v46 = v44;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            v38,
            (__int64)&byte_180197D7F,
            v39,
            v40,
            (__int64)&v46);
        }
      }
      v30 = v44;
LABEL_67:
      wil::ActivityBase<MSAClientTraceTelemetry,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        v66,
        (unsigned int)v30);
      v19 = v44;
      goto LABEL_70;
    }
    if ( v26 != 1 )
      goto LABEL_67;
  }
  if ( (int)SetNgcKeyName(v55, &v47, v50, v49) >= 0 )
  {
    v26 = 1;
LABEL_56:
    v30 = v44;
    goto LABEL_57;
  }
  v19 = v44;
  if ( v44 >= 0 )
    goto LABEL_70;
  v21 = (unsigned int)v44;
  v20 = 5160;
LABEL_10:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v20,
    (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    (const char *)v21,
    bIgnoreCasea);
LABEL_70:
  SmartAcquireTokensTelemetryJson::~SmartAcquireTokensTelemetryJson((SmartAcquireTokensTelemetryJson *)v65);
  CAutoRefPtr<CSingleIdentity>::Deinit(&v47);
  CAutoImpersonateClient::~CAutoImpersonateClient((CAutoImpersonateClient *)&v48);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v49);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v50);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v64);
  MSAClientTraceTelemetry::AcquireTokens::~AcquireTokens((MSAClientTraceTelemetry::AcquireTokens *)v66);
  return v19;
}

```

## disassembly

```asm
0x18002a57c  push    rbp
0x18002a57e  push    rbx
0x18002a57f  push    rsi
0x18002a580  push    rdi
0x18002a581  push    r12
0x18002a583  push    r13
0x18002a585  push    r14
0x18002a587  push    r15
0x18002a589  lea     rbp, [rsp-218h]
0x18002a591  sub     rsp, 318h
0x18002a598  mov     rax, cs:__security_cookie
0x18002a59f  xor     rax, rsp
0x18002a5a2  mov     [rbp+250h+var_50], rax
0x18002a5a9  mov     [rbp+250h+var_2D0], r9d
0x18002a5ad  mov     rsi, r8
0x18002a5b0  mov     [rbp+250h+var_298], rdx
0x18002a5b4  mov     r15, rcx
0x18002a5b7  mov     [rbp+250h+var_288], rcx
0x18002a5bb  mov     rax, [rbp+250h+arg_20]
0x18002a5c2  mov     [rbp+250h+var_258], rax
0x18002a5c6  mov     rax, [rbp+250h+arg_28]
0x18002a5cd  mov     [rbp+250h+var_260], rax
0x18002a5d1  mov     rax, [rbp+250h+arg_30]
0x18002a5d8  mov     [rbp+250h+var_268], rax
0x18002a5dc  mov     rax, [rbp+250h+arg_38]
0x18002a5e3  mov     [rbp+250h+var_290], rax
0x18002a5e7  mov     r13, [rbp+250h+arg_40]
0x18002a5ee  mov     rax, [rbp+250h+arg_48]
0x18002a5f5  mov     [rbp+250h+var_270], rax
0x18002a5f9  mov     rax, [rbp+250h+arg_58]
0x18002a600  mov     [rbp+250h+var_278], rax
0x18002a604  mov     rax, [rbp+250h+arg_60]
0x18002a60b  mov     [rbp+250h+var_280], rax
0x18002a60f  mov     r12, [rbp+250h+arg_68]
0x18002a616  lea     rdx, aAcquiretokens; "AcquireTokens"
0x18002a61d  lea     rcx, [rbp+250h+var_1A0]
0x18002a624  call    ??0?$ActivityBase@VMSAClientTraceTelemetry@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<MSAClientTraceTelemetry,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MSAClientTraceTelemetry,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002a629  lea     rax, ??_7AcquireTokens@MSAClientTraceTelemetry@@6B@; const MSAClientTraceTelemetry::AcquireTokens::`vftable'
0x18002a630  mov     [rbp+250h+var_1A0], rax
0x18002a637  lea     rcx, [rbp+250h+var_1A0]; this
0x18002a63e  call    ?StartActivity@AcquireTokens@MSAClientTraceTelemetry@@QEAAXXZ; MSAClientTraceTelemetry::AcquireTokens::StartActivity(void)
0x18002a643  nop
0x18002a644  xor     ebx, ebx
0x18002a646  mov     [rsp+350h+var_2E0], ebx
0x18002a64a  lea     rdx, aHandleacquiret; "HandleAcquireTokensWithNGC"
0x18002a651  mov     [rbp+250h+var_230], rdx
0x18002a655  lea     rax, [rsp+350h+var_2E0]
0x18002a65a  mov     [rbp+250h+var_228], rax
0x18002a65e  mov     [rbp+250h+var_220], rbx
0x18002a662  mov     [rbp+250h+var_218], rbx
0x18002a666  xor     r9d, r9d; unsigned int
0x18002a669  mov     r8d, 1399h; char *
0x18002a66f  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18002a676  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18002a67b  nop
0x18002a67c  lea     rcx, [rbp+250h+var_2B0]
0x18002a680  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002a685  nop
0x18002a686  lea     rcx, [rbp+250h+var_2B8]
0x18002a68a  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002a68f  nop
0x18002a690  mov     [rsp+350h+var_2D8], rbx
0x18002a695  mov     [rbp+250h+var_2C0], rbx
0x18002a699  mov     [rbp+250h+var_2C8], rbx
0x18002a69d  mov     rax, [r15]
0x18002a6a0  mov     rcx, r15
0x18002a6a3  mov     rax, [rax+50h]
0x18002a6a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a6ac  mov     rdi, rax
0x18002a6af  mov     rcx, [r15]
0x18002a6b2  mov     rax, [rcx+38h]
0x18002a6b6  mov     rcx, r15
0x18002a6b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a6be  mov     r14, rax
0x18002a6c1  test    r13, r13
0x18002a6c4  jz      short loc_18002A6CA
0x18002a6c6  mov     [r13+0], rbx
0x18002a6ca  test    r12, r12
0x18002a6cd  jz      short loc_18002A6D3
0x18002a6cf  mov     [r12], ebx
0x18002a6d3  lea     r9, aWl; "wl"
0x18002a6da  mov     r8, rsi; unsigned __int64
0x18002a6dd  mov     rdx, 2000000000h; unsigned __int64
0x18002a6e7  lea     rcx, [rbp+250h+var_210]; this
0x18002a6eb  call    ??0SmartTelemetryJson@@QEAA@_K0PEBG@Z; SmartTelemetryJson::SmartTelemetryJson(unsigned __int64,unsigned __int64,ushort const *)
0x18002a6f0  lea     rax, ??_7SmartAcquireTokensTelemetryJson@@6B@; const SmartAcquireTokensTelemetryJson::`vftable'
0x18002a6f7  mov     [rbp+250h+var_210], rax
0x18002a6fb  mov     [rbp+250h+var_1B0], r13
0x18002a702  mov     [rbp+250h+var_1A8], r12
0x18002a709  xor     edx, edx; struct ATL::CAccessToken *
0x18002a70b  lea     rcx, [rbp+250h+var_2C0]; this
0x18002a70f  call    ?ImpersonateClient@CAutoImpersonateClient@@QEAAJPEAVCAccessToken@ATL@@@Z; CAutoImpersonateClient::ImpersonateClient(ATL::CAccessToken *)
0x18002a714  mov     ebx, eax
0x18002a716  test    eax, eax
0x18002a718  jns     short loc_18002A721
0x18002a71a  mov     edx, 13B7h
0x18002a71f  jmp     short loc_18002A73A
0x18002a721  lea     rdx, [rsp+350h+var_2D8]; struct _LUID *
0x18002a726  lea     rcx, [rbp+250h+var_2C0]; this
0x18002a72a  call    ?GetLogonId@CAutoImpersonateClient@@QEAAJAEAU_LUID@@@Z; CAutoImpersonateClient::GetLogonId(_LUID &)
0x18002a72f  mov     ebx, eax
0x18002a731  test    eax, eax
0x18002a733  jns     short loc_18002A755
0x18002a735  mov     edx, 13B8h; void *
0x18002a73a  mov     r9d, eax; char *
0x18002a73d  mov     rcx, [rbp+258h]; this
0x18002a744  lea     r8, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18002a74b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a750  jmp     loc_18002ABEF
0x18002a755  mov     rcx, cs:?g_pPPCRL@@3PEAVCPassportClientLibrary@@EA; CPassportClientLibrary * g_pPPCRL
0x18002a75c  add     rcx, 1F0h
0x18002a763  lea     r9, [rbp+250h+var_2C8]
0x18002a767  mov     r8, [rbp+250h+var_298]
0x18002a76b  lea     rdx, [rsp+350h+var_2D8]
0x18002a770  call    ?GetSingleIdentity@CIdentityStore@@QEAAJAEAU_LUID@@PEAXAEAV?$CAutoRefPtr@VCSingleIdentity@@@@@Z; CIdentityStore::GetSingleIdentity(_LUID &,void *,CAutoRefPtr<CSingleIdentity> &)
0x18002a775  mov     ebx, eax
0x18002a777  test    eax, eax
0x18002a779  jns     short loc_18002A782
0x18002a77b  mov     edx, 13B9h
0x18002a780  jmp     short loc_18002A73A
0x18002a782  mov     rax, [rdi]
0x18002a785  lea     r8, [rbp+250h+var_2B8]
0x18002a789  lea     rdx, [rbp+250h+var_2C0]
0x18002a78d  mov     rcx, rdi
0x18002a790  mov     rax, [rax+48h]
0x18002a794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a799  mov     ebx, eax
0x18002a79b  test    eax, eax
0x18002a79d  jns     short loc_18002A7A6
0x18002a79f  mov     edx, 13BAh
0x18002a7a4  jmp     short loc_18002A73A
0x18002a7a6  mov     rax, [r14]
0x18002a7a9  lea     r9, [rbp+250h+var_2B0]
0x18002a7ad  lea     r8, aCid; "CID"
0x18002a7b4  mov     rbx, [rbp+250h+var_2C8]
0x18002a7b8  mov     rdx, rbx
0x18002a7bb  mov     rcx, r14
0x18002a7be  mov     rax, [rax+70h]
0x18002a7c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a7c7  mov     edi, eax
0x18002a7c9  test    eax, eax
0x18002a7cb  jns     short loc_18002A7D7
0x18002a7cd  mov     edx, 13BBh
0x18002a7d2  jmp     loc_18002ABD7
0x18002a7d7  mov     rdi, [rbp+250h+arg_50]
0x18002a7de  bt      rsi, 1Fh
0x18002a7e3  jnb     short loc_18002A83B
0x18002a7e5  test    rdi, rdi
0x18002a7e8  jnz     short loc_18002A80F
0x18002a7ea  mov     rcx, [rbp+258h]; this
0x18002a7f1  mov     r9d, 578h; char *
0x18002a7f7  lea     r8, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18002a7fe  mov     edx, 13C1h; void *
0x18002a803  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002a808  mov     ebx, eax
0x18002a80a  jmp     loc_18002ABEF
0x18002a80f  mov     r8, [rbp+250h+var_2B0]
0x18002a813  cmp     dword ptr [r8-10h], 0
0x18002a818  jz      short loc_18002A83B
0x18002a81a  mov     r9, [rbp+250h+var_2B8]
0x18002a81e  lea     rdx, [rbp+250h+var_2C8]
0x18002a822  mov     rcx, r15
0x18002a825  call    ?SetNgcKeyName@@YAJPEAVIServiceExecutionContext@@AEAV?$CAutoRefPtr@VCSingleIdentity@@@@PEBG2@Z; SetNgcKeyName(IServiceExecutionContext *,CAutoRefPtr<CSingleIdentity> &,ushort const *,ushort const *)
0x18002a82a  test    eax, eax
0x18002a82c  js      short loc_18002A83B
0x18002a82e  mov     rax, 0FFFFFFFF7FFFFFFFh
0x18002a838  and     rsi, rax
0x18002a83b  xor     r14b, r14b
0x18002a83e  mov     [rbp+250h+var_2A0], 0
0x18002a845  mov     rax, [rbx]
0x18002a848  lea     rdx, [rbp+250h+lpString1]
0x18002a84c  mov     rcx, rbx
0x18002a84f  mov     rax, [rax+10h]
0x18002a853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a858  nop
0x18002a859  mov     rax, [rbx]
0x18002a85c  lea     rdx, [rsp+350h+var_2D8]
0x18002a861  mov     rcx, rbx
0x18002a864  mov     rax, [rax+18h]
0x18002a868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a86d  mov     r15d, 1
0x18002a873  mov     [rsp+350h+bIgnoreCase], r15d; bIgnoreCase
0x18002a878  or      eax, 0FFFFFFFFh
0x18002a87b  mov     r9d, eax; cchCount2
0x18002a87e  lea     r8, aCc553c394b1c43; "{CC553C39-4B1C-43DB-94A0-3B78F751ACEF}"
0x18002a885  mov     edx, eax; cchCount1
0x18002a887  mov     rcx, [rbp+250h+lpString1]; lpString1
0x18002a88b  call    cs:__imp_CompareStringOrdinal
0x18002a891  cmp     eax, 2
0x18002a894  jz      short loc_18002A8E2
0x18002a896  mov     [rsp+350h+bIgnoreCase], r15d; bIgnoreCase
0x18002a89b  or      edx, 0FFFFFFFFh; cchCount1
0x18002a89e  mov     r9d, edx; cchCount2
0x18002a8a1  lea     r8, a7d629e2eCc4c4c; "{7D629E2E-CC4C-4CC4-95B7-25C48B11C53D}"
0x18002a8a8  mov     rcx, [rbp+250h+lpString1]; lpString1
0x18002a8ac  call    cs:__imp_CompareStringOrdinal
0x18002a8b2  cmp     eax, 2
0x18002a8b5  jz      short loc_18002A8E2
0x18002a8b7  mov     [rsp+350h+bIgnoreCase], r15d; bIgnoreCase
0x18002a8bc  or      eax, 0FFFFFFFFh
0x18002a8bf  mov     r9d, eax; cchCount2
0x18002a8c2  lea     r8, aS1152278586202; "S-1-15-2-278586202-1783374767-375565281"...
0x18002a8c9  mov     edx, eax; cchCount1
0x18002a8cb  mov     rcx, [rsp+350h+var_2D8]; lpString1
0x18002a8d0  call    cs:__imp_CompareStringOrdinal
0x18002a8d6  cmp     eax, 2
0x18002a8d9  jz      short loc_18002A8E2
0x18002a8db  bt      rsi, 0Fh
0x18002a8e0  jnb     short loc_18002A8E5
0x18002a8e2  xor     r15b, r15b
0x18002a8e5  lea     rcx, [rsp+350h+var_2D8]
0x18002a8ea  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002a8ef  nop
0x18002a8f0  lea     rcx, [rbp+250h+lpString1]
0x18002a8f4  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002a8f9  test    r14b, r14b
0x18002a8fc  jz      short loc_18002A912
0x18002a8fe  mov     r8d, [r12]; unsigned int
0x18002a902  mov     dword ptr [r12], 0
0x18002a90a  mov     rdx, r13; struct _WLIDResponseParams **
0x18002a90d  call    ?FreeWLIDResponseParams@CAutoFreeWLIDResponse@@AEAAXPEAPEAU_WLIDResponseParams@@K@Z; CAutoFreeWLIDResponse::FreeWLIDResponseParams(_WLIDResponseParams * *,ulong)
0x18002a912  mov     [rsp+350h+var_2F0], r12; unsigned int *
0x18002a917  mov     rax, [rbp+250h+var_280]
0x18002a91b  mov     [rsp+350h+var_2F8], rax; int *
0x18002a920  mov     rax, [rbp+250h+var_278]
0x18002a924  mov     [rsp+350h+var_300], rax; unsigned __int16 *
0x18002a929  mov     [rsp+350h+var_308], rdi; unsigned __int64
0x18002a92e  mov     rax, [rbp+250h+var_270]
0x18002a932  mov     [rsp+350h+var_310], rax; unsigned __int16 *
0x18002a937  mov     [rsp+350h+var_318], r13; struct _WLIDResponseParams **
0x18002a93c  mov     rax, [rbp+250h+var_290]
0x18002a940  mov     [rsp+350h+var_320], rax; int *
0x18002a945  mov     rax, [rbp+250h+var_268]
0x18002a949  mov     [rsp+350h+var_328], rax; int *
0x18002a94e  mov     rax, [rbp+250h+var_260]
0x18002a952  mov     qword ptr [rsp+350h+bIgnoreCase], rax; int
0x18002a957  mov     r9, [rbp+250h+var_258]; struct _WLIDRequestParams *
0x18002a95b  mov     r8d, [rbp+250h+var_2D0]; unsigned int
0x18002a95f  mov     rdx, rsi; unsigned __int64
0x18002a962  mov     rcx, [rbp+250h+var_298]; void *
0x18002a966  call    ?HandleAcquireTokens@@YAJQEAX_KKQEAU_WLIDRequestParams@@PEAJ33PEAPEAU_WLIDResponseParams@@PEBG_K53PEAK@Z; HandleAcquireTokens(void * const,unsigned __int64,ulong,_WLIDRequestParams * const,long *,long *,long *,_WLIDResponseParams * *,ushort const *,unsigned __int64,ushort const *,long *,ulong *)
0x18002a96b  mov     [rsp+350h+var_2E0], eax
0x18002a96f  mov     rcx, [rbp+258h]; this
0x18002a976  test    eax, eax
0x18002a978  jns     short loc_18002A992
0x18002a97a  mov     r9d, eax; char *
0x18002a97d  lea     r8, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18002a984  mov     edx, 13F7h; void *
0x18002a989  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002a98e  mov     eax, [rsp+350h+var_2E0]
0x18002a992  xor     r14b, r14b
0x18002a995  mov     rdx, [rbp+250h+var_290]
0x18002a999  cmp     dword ptr [rdx], 800488ABh
0x18002a99f  jz      loc_18002AAB7
0x18002a9a5  mov     rcx, [r13+0]
0x18002a9a9  test    rcx, rcx
0x18002a9ac  jz      short loc_18002A9BB
0x18002a9ae  cmp     dword ptr [rcx+4], 800488ABh
0x18002a9b5  jz      loc_18002AAB7
0x18002a9bb  cmp     eax, 8009002Eh
0x18002a9c0  jnz     short loc_18002AA29
0x18002a9c2  mov     rax, [rbx]
0x18002a9c5  mov     rcx, rbx
0x18002a9c8  mov     rax, [rax+8]
0x18002a9cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a9d1  mov     rdi, rax
0x18002a9d4  lea     rax, [rbp+250h+lpString1]
0x18002a9d8  mov     [rbp+250h+var_240], rax
0x18002a9dc  xor     eax, eax
0x18002a9de  mov     [rbp+250h+lpString1], rax
0x18002a9e2  lea     rcx, [rbp+250h+lpString1]
0x18002a9e6  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002a9eb  nop
0x18002a9ec  lea     rdx, aPsNgckn; "ps:ngckn"
0x18002a9f3  lea     rcx, [rbp+250h+var_250]
0x18002a9f7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002a9fc  nop
0x18002a9fd  lea     r8, [rbp+250h+lpString1]
0x18002aa01  mov     rdx, rax
0x18002aa04  mov     rcx, rdi
0x18002aa07  call    ?StoreCredential@CIdentityCredentialBag@@QEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CAutoZeroMemoryStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@@@Z; CIdentityCredentialBag::StoreCredential(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CAutoZeroMemoryStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x18002aa0c  mov     edi, eax
0x18002aa0e  test    eax, eax
0x18002aa10  js      loc_18002AB59
0x18002aa16  xor     r15b, r15b
0x18002aa19  mov     eax, 80000000h
0x18002aa1e  or      rsi, rax
0x18002aa21  mov     r14b, 1
0x18002aa24  jmp     loc_18002AB35
0x18002aa29  test    rdi, rdi
0x18002aa2c  jz      loc_18002AB40
0x18002aa32  cmp     r15b, 1
0x18002aa36  jnz     loc_18002AB40
0x18002aa3c  cmp     eax, 8004884Ch
0x18002aa41  jz      short loc_18002AA87
0x18002aa43  cmp     eax, 8004882Eh
0x18002aa48  jz      short loc_18002AA87
0x18002aa4a  cmp     eax, 800488BCh
0x18002aa4f  jz      short loc_18002AA87
0x18002aa51  cmp     eax, 80048888h
  ... truncated ...
```
