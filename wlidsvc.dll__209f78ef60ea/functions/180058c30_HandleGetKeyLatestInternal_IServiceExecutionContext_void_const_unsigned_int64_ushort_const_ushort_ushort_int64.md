# HandleGetKeyLatestInternal(IServiceExecutionContext *,void * const,unsigned __int64,ushort const *,ushort * *,ushort * *,__int64 *)

- ea: `0x180058c30`
- end: `0x1800592a3`
- name: `?HandleGetKeyLatestInternal@@YAJPEAVIServiceExecutionContext@@QEAX_KPEBGPEAPEAG4PEA_J@Z`
- size: `1651`
- prototype: `__int64 __fastcall(struct IServiceExecutionContext *, void *const, unsigned __int64, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, __int64 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180028f00`

## callees

- `0x180001724`
- `0x18000c050`
- `0x18000ed04`
- `0x18000fd04`
- `0x1800124c4`
- `0x1800151c4`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18002d36c`
- `0x18002d838`
- `0x180030120`
- `0x180043344`
- `0x180048fd4`
- `0x180058c30`
- `0x18008390c`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180058f0e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180058fa2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180058ff8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005902a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180058f0e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180058fa2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180058ff8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005902a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18005912b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800591ab`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18005912b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800591ab`

## string_xrefs

- `0x180058cfc`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180058d99`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180059107`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180059182`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18005923a`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180058d81`: `hr = pSvcWrapper->Impersonate(&client)`
- `0x18005920d`: `!pIdentityWrapper->IsIdentityNULL(hIdentity) && pIdentityWrapper->HasAuthToken(hIdentity)`
- `0x180058ec6`: `hr = pTokenBagWrapper->GetKeyLatest( hTokenBag, wcszPurpose, requireMaterial, wstrKeyVersion, wstrKeyMaterial)`
- `0x18005915a`: `hr = StringCchCopyW(*pwszKeyVersion, wstrKeyVersion.GetLength() + 1, (LPCWSTR)wstrKeyVersion)`
- `0x1800591d9`: `hr = StringCchCopyW(*pwszKeyMaterial, wstrKeyMaterial.GetLength() + 1, (LPCWSTR)wstrKeyMaterial)`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall HandleGetKeyLatestInternal(
        struct IServiceExecutionContext *a1,
        void *const a2,
        __int64 a3,
        const unsigned __int16 *a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6,
        __int64 *a7)
{
  __int64 v10; // r15
  __int64 v11; // r14
  unsigned __int16 **v12; // r13
  unsigned __int16 **v13; // rax
  __int64 *v14; // r12
  int v15; // eax
  const char *v16; // rcx
  unsigned int v17; // r8d
  int v18; // r9d
  __int64 v19; // rax
  __int64 v20; // rbx
  __int64 v21; // r14
  int v22; // eax
  const char *v23; // rcx
  unsigned int v24; // r8d
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  int v28; // eax
  unsigned int v29; // edi
  unsigned __int64 v30; // r9
  __int64 v31; // rdx
  int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r9
  int *v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // r9
  int v40; // eax
  __int64 v41; // rbx
  unsigned __int16 *v42; // rax
  unsigned __int16 *v43; // rax
  char *v45; // [rsp+20h] [rbp-81h]
  char *v46; // [rsp+20h] [rbp-81h]
  char *v47; // [rsp+20h] [rbp-81h]
  unsigned __int16 *v48; // [rsp+40h] [rbp-61h] BYREF
  unsigned __int16 *v49; // [rsp+48h] [rbp-59h] BYREF
  __int64 v50; // [rsp+50h] [rbp-51h] BYREF
  __int64 v51; // [rsp+58h] [rbp-49h] BYREF
  __int64 v52; // [rsp+60h] [rbp-41h] BYREF
  BOOL v53; // [rsp+68h] [rbp-39h]
  __int64 v54; // [rsp+70h] [rbp-31h]
  __int64 v55; // [rsp+78h] [rbp-29h] BYREF
  __int64 v56; // [rsp+80h] [rbp-21h] BYREF
  __int64 v57; // [rsp+88h] [rbp-19h]
  _QWORD v58[10]; // [rsp+90h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+47h]
  __int64 v60; // [rsp+F0h] [rbp+4Fh] BYREF
  void *v61; // [rsp+F8h] [rbp+57h]
  int v62; // [rsp+100h] [rbp+5Fh] BYREF

  v61 = a2;
  v62 = 0;
  v56 = 0;
  v52 = 0;
  v55 = 0;
  v51 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v48);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v49);
  v10 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 56LL))(a1);
  v54 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 104LL))(a1);
  v11 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 80LL))(a1);
  v57 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 64LL))(a1);
  v58[0] = "HandleGetKeyLatestInternal";
  v58[1] = &v62;
  v58[2] = 0;
  v58[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    "HandleGetKeyLatestInternal",
    (const char *)0x27F4,
    0,
    (const unsigned __int16 *)v45);
  if ( (a3 & 0xFFFFFFFFFFFFFFFCuLL) != 0 || !a4 || !*a4 || (v12 = a5) == 0 || (v13 = a6) == 0 )
  {
    v62 = -2147024809;
    goto LABEL_62;
  }
  *a5 = 0;
  *v13 = 0;
  v14 = a7;
  if ( a7 )
    *a7 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v11 + 32LL))(v11, &v52, 0);
  v62 = v15;
  if ( v15 >= 0 )
  {
    v15 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)v11 + 40LL))(v11, &v52, &v56);
    v62 = v15;
    if ( v15 < 0 )
    {
      v16 = "hr = pSvcWrapper->GetLogonId(&client, logonId)";
      v17 = 10254;
      goto LABEL_10;
    }
    v15 = (*(__int64 (__fastcall **)(__int64, __int64 *, void *, __int64 *))(*(_QWORD *)v11 + 24LL))(
            v11,
            &v56,
            v61,
            &v51);
    v62 = v15;
    if ( v15 < 0 )
    {
      v16 = "hr = pSvcWrapper->GetIdentityHandle(logonId, handle, hIdentity)";
      v17 = 10257;
      goto LABEL_10;
    }
    if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 48LL))(v10, v51)
      || !(*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 24LL))(v10, v51) )
    {
      v18 = -2147186688;
      v62 = -2147186688;
      v47 = "!pIdentityWrapper->IsIdentityNULL(hIdentity) && pIdentityWrapper->HasAuthToken(hIdentity)";
      v17 = 10259;
      goto LABEL_11;
    }
    v19 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 40LL))(v10, v51);
    CAutoRefPtr<CIdentityTokenBag>::operator=(&v55, v19);
    v20 = v55;
    if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v54 + 24LL))(v54, v55) )
    {
      v62 = -2147188685;
      goto LABEL_62;
    }
    v21 = a3 & 1;
    v53 = !(a3 & 1);
    v46 = (char *)&v48;
    v22 = (*(__int64 (__fastcall **)(__int64, __int64, const unsigned __int16 *, bool))(*(_QWORD *)v54 + 8LL))(
            v54,
            v20,
            a4,
            !(a3 & 1));
    v62 = v22;
    if ( v22 < 0 )
    {
      v23 = "hr = pTokenBagWrapper->GetKeyLatest( hTokenBag, wcszPurpose, requireMaterial, wstrKeyVersion, wstrKeyMaterial)";
      v24 = 10275;
      goto LABEL_23;
    }
    if ( !*((_DWORD *)v48 - 4) )
    {
      if ( (unsigned int)dword_1801C2080 > 5 )
      {
        v50 = a3;
        LOBYTE(v60) = (unsigned int)_o__wcsicmp(a4, L"StrongCredentialKey") == 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
          v25,
          (__int64)&byte_180197AD7,
          v26,
          v27,
          (__int64)&v60,
          (__int64)&v50);
      }
      if ( (a3 & 2) == 0 )
        goto LABEL_28;
      goto LABEL_42;
    }
    if ( (a3 & 1) != 0 )
    {
      if ( (unsigned int)dword_1801C2080 <= 5 )
        goto LABEL_47;
      v50 = a3;
      v32 = _o__wcsicmp(a4, L"StrongCredentialKey");
      v36 = (int *)byte_180197A41;
    }
    else
    {
      if ( !*((_DWORD *)v49 - 4) )
      {
        if ( (a3 & 2) == 0 )
        {
LABEL_28:
          v60 = v51;
          if ( v51 )
            _InterlockedIncrement((volatile signed __int32 *)(v51 + 8));
          v28 = RequestKey(a4, &v60, v10, v57);
          v29 = v28;
          v62 = v28;
          if ( v28 < 0 )
          {
            v30 = (unsigned int)v28;
            v31 = 10333;
LABEL_65:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v31,
              (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
              (const char *)v30,
              (int)v46);
            goto LABEL_66;
          }
          v46 = (char *)&v48;
          v40 = (*(__int64 (__fastcall **)(__int64, __int64, const unsigned __int16 *, BOOL))(*(_QWORD *)v54 + 8LL))(
                  v54,
                  v20,
                  a4,
                  v53);
          v29 = v40;
          v62 = v40;
          if ( v40 < 0 )
          {
            v30 = (unsigned int)v40;
            v31 = 10341;
            goto LABEL_65;
          }
          if ( !*((_DWORD *)v48 - 4) || !*((_DWORD *)v49 - 4) )
          {
            v29 = -2147186523;
            v62 = -2147186523;
            v31 = 10346;
LABEL_64:
            v30 = v29;
            goto LABEL_65;
          }
LABEL_47:
          if ( v14 )
          {
            v60 = 0;
            v22 = WlidsvcUtil::ParseDateTimeString(&v48, &v60);
            v62 = v22;
            if ( v22 < 0 )
            {
              v23 = "hr = WlidsvcUtil::ParseDateTimeString(wstrKeyVersion, keyVersionTimeStamp, TRUE)";
              v24 = 10354;
              goto LABEL_23;
            }
            v41 = v60;
            LODWORD(v46) = v60;
            TracePrintW(
              5u,
              "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
              0x2873u,
              L"Key version = %I64d");
            *v14 = v41;
          }
          v42 = (unsigned __int16 *)malloc(2LL * (*((_DWORD *)v48 - 4) + 1));
          *v12 = v42;
          if ( !v42 )
            goto LABEL_58;
          v22 = StringCchCopyW(v42, *((_DWORD *)v48 - 4) + 1, v48);
          v62 = v22;
          if ( v22 < 0 )
          {
            v23 = "hr = StringCchCopyW(*pwszKeyVersion, wstrKeyVersion.GetLength() + 1, (LPCWSTR)wstrKeyVersion)";
            v24 = 10362;
            goto LABEL_23;
          }
          v46 = (char *)*v12;
          TracePrintW(
            5u,
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
            0x287Bu,
            L"KeyVersion: %ls");
          if ( v21 )
            goto LABEL_62;
          v43 = (unsigned __int16 *)malloc(2LL * (*((_DWORD *)v49 - 4) + 1));
          *a6 = v43;
          if ( !v43 )
          {
LABEL_58:
            v62 = -2147024882;
            goto LABEL_62;
          }
          v22 = StringCchCopyW(v43, *((_DWORD *)v49 - 4) + 1, v49);
          v62 = v22;
          if ( v22 >= 0 )
            goto LABEL_62;
          v23 = "hr = StringCchCopyW(*pwszKeyMaterial, wstrKeyMaterial.GetLength() + 1, (LPCWSTR)wstrKeyMaterial)";
          v24 = 10370;
LABEL_23:
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
            "HandleGetKeyLatestInternal",
            v24,
            v22,
            v23);
          goto LABEL_62;
        }
        if ( (unsigned int)dword_1801C2080 > 5 )
        {
          v50 = a3;
          LOBYTE(v60) = (unsigned int)_o__wcsicmp(a4, L"StrongCredentialKey") == 0;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
            v37,
            (__int64)byte_1801979F5,
            v38,
            v39,
            (__int64)&v60,
            (__int64)&v50);
        }
LABEL_42:
        v62 = -2147186524;
        goto LABEL_62;
      }
      if ( (unsigned int)dword_1801C2080 <= 5 )
        goto LABEL_47;
      v50 = a3;
      v32 = _o__wcsicmp(a4, L"StrongCredentialKey");
      v36 = &dword_180197A8C;
    }
    LOBYTE(v60) = v32 == 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
      v33,
      (__int64)v36,
      v34,
      v35,
      (__int64)&v60,
      (__int64)&v50);
    goto LABEL_47;
  }
  v16 = "hr = pSvcWrapper->Impersonate(&client)";
  v17 = 10253;
LABEL_10:
  v47 = (char *)v16;
  v18 = v15;
LABEL_11:
  Telemetry::IfFailExit(
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    "HandleGetKeyLatestInternal",
    v17,
    v18,
    v47);
LABEL_62:
  v29 = v62;
  if ( v62 < 0 )
  {
    v31 = 10374;
    goto LABEL_64;
  }
LABEL_66:
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v58);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v49);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v48);
  CAutoRefPtr<CSingleIdentity>::Deinit(&v51);
  CAutoRefPtr<IStoredIdentity>::Deinit(&v55);
  CAutoImpersonateClient::~CAutoImpersonateClient((CAutoImpersonateClient *)&v52);
  return v29;
}

```

## disassembly

```asm
0x180058c30  mov     [rsp-8+arg_18], rbx
0x180058c35  mov     [rsp-8+arg_8], rdx
0x180058c3a  push    rbp
0x180058c3b  push    rsi
0x180058c3c  push    rdi
0x180058c3d  push    r12
0x180058c3f  push    r13
0x180058c41  push    r14
0x180058c43  push    r15
0x180058c45  lea     rbp, [rsp-0Fh]
0x180058c4a  sub     rsp, 0B0h
0x180058c51  mov     rsi, r9
0x180058c54  mov     rdi, r8
0x180058c57  mov     rbx, rcx
0x180058c5a  xor     eax, eax
0x180058c5c  mov     [rbp+3Fh+arg_10], eax
0x180058c5f  mov     [rbp+3Fh+var_60], rax
0x180058c63  mov     [rbp+3Fh+var_80], rax
0x180058c67  mov     [rbp+3Fh+var_68], rax
0x180058c6b  mov     [rbp+3Fh+var_88], rax
0x180058c6f  lea     rcx, [rbp+3Fh+var_A0]
0x180058c73  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180058c78  nop
0x180058c79  lea     rcx, [rbp+3Fh+var_98]
0x180058c7d  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180058c82  nop
0x180058c83  mov     rax, [rbx]
0x180058c86  mov     rcx, rbx
0x180058c89  mov     rax, [rax+38h]
0x180058c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058c92  mov     r15, rax
0x180058c95  mov     rcx, [rbx]
0x180058c98  mov     rax, [rcx+68h]
0x180058c9c  mov     rcx, rbx
0x180058c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058ca4  mov     [rbp+3Fh+var_70], rax
0x180058ca8  mov     rcx, [rbx]
0x180058cab  mov     rax, [rcx+50h]
0x180058caf  mov     rcx, rbx
0x180058cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058cb7  mov     r14, rax
0x180058cba  mov     rcx, [rbx]
0x180058cbd  mov     rax, [rcx+40h]
0x180058cc1  mov     rcx, rbx
0x180058cc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058cc9  mov     [rbp+3Fh+var_58], rax
0x180058ccd  lea     rbx, aHandlegetkeyla; "HandleGetKeyLatestInternal"
0x180058cd4  mov     [rbp+3Fh+var_50], rbx
0x180058cd8  lea     rax, [rbp+3Fh+arg_10]
0x180058cdc  mov     [rbp+3Fh+var_48], rax
0x180058ce0  mov     [rbp+3Fh+var_40], 0
0x180058ce8  mov     [rbp+3Fh+var_38], 0
0x180058cf0  xor     r9d, r9d; unsigned int
0x180058cf3  mov     r8d, 27F4h; char *
0x180058cf9  mov     rdx, rbx; char *
0x180058cfc  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180058d03  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180058d08  nop
0x180058d09  test    rdi, 0FFFFFFFFFFFFFFFCh
0x180058d10  jnz     loc_180059224
0x180058d16  test    rsi, rsi
0x180058d19  jz      loc_180059224
0x180058d1f  xor     eax, eax
0x180058d21  cmp     ax, [rsi]
0x180058d24  jz      loc_180059224
0x180058d2a  mov     r13, [rbp+3Fh+arg_20]
0x180058d2e  test    r13, r13
0x180058d31  jz      loc_180059224
0x180058d37  mov     rax, [rbp+3Fh+arg_28]
0x180058d3b  test    rax, rax
0x180058d3e  jz      loc_180059224
0x180058d44  mov     qword ptr [r13+0], 0
0x180058d4c  mov     qword ptr [rax], 0
0x180058d53  mov     r12, [rbp+3Fh+arg_30]
0x180058d57  test    r12, r12
0x180058d5a  jz      short loc_180058D64
0x180058d5c  mov     qword ptr [r12], 0
0x180058d64  mov     rax, [r14]
0x180058d67  xor     r8d, r8d
0x180058d6a  lea     rdx, [rbp+3Fh+var_80]
0x180058d6e  mov     rcx, r14
0x180058d71  mov     rax, [rax+20h]
0x180058d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058d7a  mov     [rbp+3Fh+arg_10], eax
0x180058d7d  test    eax, eax
0x180058d7f  jns     short loc_180058DAA
0x180058d81  lea     rcx, aHrPsvcwrapperI; "hr = pSvcWrapper->Impersonate(&client)"
0x180058d88  mov     r8d, 280Dh; unsigned int
0x180058d8e  mov     [rsp+0E0h+var_C0], rcx; char *
0x180058d93  mov     r9d, eax; int
0x180058d96  mov     rdx, rbx; char *
0x180058d99  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180058da0  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180058da5  jmp     loc_18005922B
0x180058daa  mov     rax, [r14]
0x180058dad  lea     r8, [rbp+3Fh+var_60]
0x180058db1  lea     rdx, [rbp+3Fh+var_80]
0x180058db5  mov     rcx, r14
0x180058db8  mov     rax, [rax+28h]
0x180058dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058dc1  mov     [rbp+3Fh+arg_10], eax
0x180058dc4  test    eax, eax
0x180058dc6  jns     short loc_180058DD7
0x180058dc8  lea     rcx, aHrPsvcwrapperG_2; "hr = pSvcWrapper->GetLogonId(&client, l"...
0x180058dcf  mov     r8d, 280Eh
0x180058dd5  jmp     short loc_180058D8E
0x180058dd7  mov     rax, [r14]
0x180058dda  lea     r9, [rbp+3Fh+var_88]
0x180058dde  mov     r8, [rbp+3Fh+arg_8]
0x180058de2  lea     rdx, [rbp+3Fh+var_60]
0x180058de6  mov     rcx, r14
0x180058de9  mov     rax, [rax+18h]
0x180058ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058df2  mov     [rbp+3Fh+arg_10], eax
0x180058df5  test    eax, eax
0x180058df7  jns     short loc_180058E08
0x180058df9  lea     rcx, aHrPsvcwrapperG_3; "hr = pSvcWrapper->GetIdentityHandle(log"...
0x180058e00  mov     r8d, 2811h
0x180058e06  jmp     short loc_180058D8E
0x180058e08  mov     rax, [r15]
0x180058e0b  mov     rdx, [rbp+3Fh+var_88]
0x180058e0f  mov     rcx, r15
0x180058e12  mov     rax, [rax+30h]
0x180058e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058e1b  test    al, al
0x180058e1d  jnz     loc_180059203
0x180058e23  mov     rax, [r15]
0x180058e26  mov     rdx, [rbp+3Fh+var_88]
0x180058e2a  mov     rcx, r15
0x180058e2d  mov     rax, [rax+18h]
0x180058e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058e36  test    al, al
0x180058e38  jz      loc_180059203
0x180058e3e  mov     rax, [r15]
0x180058e41  mov     rdx, [rbp+3Fh+var_88]
0x180058e45  mov     rcx, r15
0x180058e48  mov     rax, [rax+28h]
0x180058e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058e51  mov     rdx, rax
0x180058e54  lea     rcx, [rbp+3Fh+var_68]
0x180058e58  call    ??4?$CAutoRefPtr@VCIdentityTokenBag@@@@QEAAAEAV0@PEAVCIdentityTokenBag@@@Z; CAutoRefPtr<CIdentityTokenBag>::operator=(CIdentityTokenBag *)
0x180058e5d  mov     rcx, [rbp+3Fh+var_70]
0x180058e61  mov     rax, [rcx]
0x180058e64  mov     rbx, [rbp+3Fh+var_68]
0x180058e68  mov     rdx, rbx
0x180058e6b  mov     rax, [rax+18h]
0x180058e6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058e74  test    al, al
0x180058e76  jz      short loc_180058E84
0x180058e78  mov     [rbp+3Fh+arg_10], 80048033h
0x180058e7f  jmp     loc_18005922B
0x180058e84  mov     r14, rdi
0x180058e87  and     r14d, 1
0x180058e8b  mov     edx, r14d
0x180058e8e  xor     edx, 1
0x180058e91  mov     [rbp+3Fh+var_78], edx
0x180058e94  mov     rcx, [rbp+3Fh+var_70]
0x180058e98  mov     rax, [rcx]
0x180058e9b  lea     r8, [rbp+3Fh+var_98]
0x180058e9f  mov     [rsp+0E0h+var_B8], r8
0x180058ea4  lea     r8, [rbp+3Fh+var_A0]
0x180058ea8  mov     [rsp+0E0h+var_C0], r8
0x180058ead  mov     r9d, edx
0x180058eb0  mov     r8, rsi
0x180058eb3  mov     rdx, rbx
0x180058eb6  mov     rax, [rax+8]
0x180058eba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058ebf  mov     [rbp+3Fh+arg_10], eax
0x180058ec2  test    eax, eax
0x180058ec4  jns     short loc_180058EE7
0x180058ec6  lea     rcx, aHrPtokenbagwra_1; "hr = pTokenBagWrapper->GetKeyLatest( hT"...
0x180058ecd  mov     r8d, 2823h
0x180058ed3  mov     r9d, eax
0x180058ed6  mov     [rsp+0E0h+var_C0], rcx
0x180058edb  lea     rdx, aHandlegetkeyla; "HandleGetKeyLatestInternal"
0x180058ee2  jmp     loc_180058D99
0x180058ee7  mov     rax, [rbp+3Fh+var_A0]
0x180058eeb  cmp     dword ptr [rax-10h], 0
0x180058eef  jnz     loc_180058F80
0x180058ef5  mov     eax, cs:dword_1801C2080
0x180058efb  cmp     eax, 5
0x180058efe  jbe     short loc_180058F38
0x180058f00  mov     [rbp+3Fh+var_90], rdi
0x180058f04  lea     rdx, aStrongcredenti_0; "StrongCredentialKey"
0x180058f0b  mov     rcx, rsi
0x180058f0e  call    cs:__imp__o__wcsicmp
0x180058f14  test    eax, eax
0x180058f16  setz    byte ptr [rbp+3Fh+arg_0]
0x180058f1a  lea     rax, [rbp+3Fh+var_90]
0x180058f1e  mov     [rsp+0E0h+var_B8], rax
0x180058f23  lea     rax, [rbp+3Fh+arg_0]
0x180058f27  mov     [rsp+0E0h+var_C0], rax
0x180058f2c  lea     rdx, byte_180197AD7
0x180058f33  call    ??$Write@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)
0x180058f38  test    dil, 2
0x180058f3c  jnz     loc_180059054
0x180058f42  mov     rax, [rbp+3Fh+var_88]
0x180058f46  mov     [rbp+3Fh+arg_0], rax
0x180058f4a  test    rax, rax
0x180058f4d  jz      short loc_180058F53
0x180058f4f  lock inc dword ptr [rax+8]
0x180058f53  mov     r9, [rbp+3Fh+var_58]
0x180058f57  mov     r8, r15
0x180058f5a  lea     rdx, [rbp+3Fh+arg_0]
0x180058f5e  mov     rcx, rsi
0x180058f61  call    ?RequestKey@@YAJPEBGV?$CAutoRefPtr@VCSingleIdentity@@@@PEBVIIdentityWrapper@@PEBVIRequestWrapper@@@Z; RequestKey(ushort const *,CAutoRefPtr<CSingleIdentity>,IIdentityWrapper const *,IRequestWrapper const *)
0x180058f66  mov     edi, eax
0x180058f68  mov     [rbp+3Fh+arg_10], eax
0x180058f6b  test    eax, eax
0x180058f6d  jns     loc_180059060
0x180058f73  mov     r9d, eax
0x180058f76  mov     edx, 285Dh
0x180058f7b  jmp     loc_18005923A
0x180058f80  test    r14, r14
0x180058f83  jz      short loc_180058FD1
0x180058f85  mov     eax, cs:dword_1801C2080
0x180058f8b  cmp     eax, 5
0x180058f8e  jbe     loc_1800590BE
0x180058f94  mov     [rbp+3Fh+var_90], rdi
0x180058f98  lea     rdx, aStrongcredenti_0; "StrongCredentialKey"
0x180058f9f  mov     rcx, rsi
0x180058fa2  call    cs:__imp__o__wcsicmp
0x180058fa8  lea     rdx, byte_180197A41
0x180058faf  test    eax, eax
0x180058fb1  lea     rax, [rbp+3Fh+var_90]
0x180058fb5  mov     [rsp+0E0h+var_B8], rax
0x180058fba  lea     rax, [rbp+3Fh+arg_0]
0x180058fbe  mov     [rsp+0E0h+var_C0], rax
0x180058fc3  setz    byte ptr [rbp+3Fh+arg_0]
0x180058fc7  call    ??$Write@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)
0x180058fcc  jmp     loc_1800590BE
0x180058fd1  mov     rax, [rbp+3Fh+var_98]
0x180058fd5  cmp     dword ptr [rax-10h], 0
0x180058fd9  jz      short loc_180059007
0x180058fdb  mov     eax, cs:dword_1801C2080
0x180058fe1  cmp     eax, 5
0x180058fe4  jbe     loc_1800590BE
0x180058fea  mov     [rbp+3Fh+var_90], rdi
0x180058fee  lea     rdx, aStrongcredenti_0; "StrongCredentialKey"
0x180058ff5  mov     rcx, rsi
0x180058ff8  call    cs:__imp__o__wcsicmp
0x180058ffe  lea     rdx, dword_180197A8C
0x180059005  jmp     short loc_180058FAF
0x180059007  test    dil, 2
0x18005900b  jz      loc_180058F42
0x180059011  mov     eax, cs:dword_1801C2080
0x180059017  cmp     eax, 5
0x18005901a  jbe     short loc_180059054
0x18005901c  mov     [rbp+3Fh+var_90], rdi
0x180059020  lea     rdx, aStrongcredenti_0; "StrongCredentialKey"
0x180059027  mov     rcx, rsi
0x18005902a  call    cs:__imp__o__wcsicmp
0x180059030  test    eax, eax
0x180059032  setz    byte ptr [rbp+3Fh+arg_0]
0x180059036  lea     rax, [rbp+3Fh+var_90]
0x18005903a  mov     [rsp+0E0h+var_B8], rax
0x18005903f  lea     rax, [rbp+3Fh+arg_0]
0x180059043  mov     [rsp+0E0h+var_C0], rax
0x180059048  lea     rdx, byte_1801979F5
0x18005904f  call    ??$Write@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)
0x180059054  mov     [rbp+3Fh+arg_10], 800488A4h
0x18005905b  jmp     loc_18005922B
0x180059060  mov     rcx, [rbp+3Fh+var_70]
0x180059064  mov     rax, [rcx]
0x180059067  lea     rdx, [rbp+3Fh+var_98]
0x18005906b  mov     [rsp+0E0h+var_B8], rdx
0x180059070  lea     rdx, [rbp+3Fh+var_A0]
0x180059074  mov     [rsp+0E0h+var_C0], rdx
0x180059079  mov     r9d, [rbp+3Fh+var_78]
0x18005907d  mov     r8, rsi
0x180059080  mov     rdx, rbx
0x180059083  mov     rax, [rax+8]
0x180059087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005908c  mov     edi, eax
0x18005908e  mov     [rbp+3Fh+arg_10], eax
0x180059091  test    eax, eax
0x180059093  jns     short loc_1800590A2
0x180059095  mov     r9d, eax
0x180059098  mov     edx, 2865h
0x18005909d  jmp     loc_18005923A
0x1800590a2  mov     rax, [rbp+3Fh+var_A0]
0x1800590a6  cmp     dword ptr [rax-10h], 0
0x1800590aa  jz      loc_1800591F4
0x1800590b0  mov     rax, [rbp+3Fh+var_98]
0x1800590b4  cmp     dword ptr [rax-10h], 0
0x1800590b8  jz      loc_1800591F4
0x1800590be  test    r12, r12
0x1800590c1  jz      short loc_18005911C
0x1800590c3  mov     [rbp+3Fh+arg_0], 0
0x1800590cb  lea     rdx, [rbp+3Fh+arg_0]
0x1800590cf  lea     rcx, [rbp+3Fh+var_A0]
0x1800590d3  call    ?ParseDateTimeString@WlidsvcUtil@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEA_JH@Z; WlidsvcUtil::ParseDateTimeString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,__int64 &,int)
0x1800590d8  mov     [rbp+3Fh+arg_10], eax
0x1800590db  test    eax, eax
0x1800590dd  jns     short loc_1800590F1
0x1800590df  lea     rcx, aHrWlidsvcutilP; "hr = WlidsvcUtil::ParseDateTimeString(w"...
0x1800590e6  mov     r8d, 2872h
0x1800590ec  jmp     loc_180058ED3
0x1800590f1  mov     rbx, [rbp+3Fh+arg_0]
0x1800590f5  mov     [rsp+0E0h+var_C0], rbx
  ... truncated ...
```
