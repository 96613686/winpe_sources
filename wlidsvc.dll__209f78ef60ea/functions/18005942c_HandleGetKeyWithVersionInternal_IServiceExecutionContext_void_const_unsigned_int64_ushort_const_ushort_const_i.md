# HandleGetKeyWithVersionInternal(IServiceExecutionContext *,void * const,unsigned __int64,ushort const *,ushort const *,__int64,ushort * *)

- ea: `0x18005942c`
- end: `0x180059991`
- name: `?HandleGetKeyWithVersionInternal@@YAJPEAVIServiceExecutionContext@@QEAX_KPEBG3_JPEAPEAG@Z`
- size: `1381`
- prototype: `__int64 __fastcall(struct IServiceExecutionContext *, void *const, unsigned __int64, const unsigned __int16 *, const unsigned __int16 *, __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800592ac`

## callees

- `0x180001724`
- `0x18000c050`
- `0x18000ed04`
- `0x18000fd04`
- `0x1800124c4`
- `0x1800151c4`
- `0x180018f80`
- `0x18001925c`
- `0x180019690`
- `0x18001a530`
- `0x18001a9c0`
- `0x18001cf20`
- `0x18002d36c`
- `0x18002d838`
- `0x180030120`
- `0x180043344`
- `0x180048fd4`
- `0x18005942c`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180059787`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800597f5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180059787`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800597f5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800597c0`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800597c0`

## string_xrefs

- `0x180059503`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18005957e`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180059657`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180059865`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x1800595b4`: `hr = pSvcWrapper->Impersonate(&client)`
- `0x180059913`: `!pIdentityWrapper->IsIdentityNULL(hIdentity) && pIdentityWrapper->HasAuthToken(hIdentity)`
- `0x1800598ef`: `hr = StringCchCopyW(*pwszKeyMaterial, wstrKeyMaterial.GetLength() + 1, (LPCWSTR)wstrKeyMaterial)`
- `0x18005974a`: `hr = pTokenBagWrapper->GetKeySpecific( hTokenBag, wcszPurpose, wstrVersion, wstrKeyMaterial)`
- `0x1800598a5`: `hr = pTokenBagWrapper->GetKeySpecific( hTokenBag, wcszPurpose, wstrVersion, wstrKeyMaterial)`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall HandleGetKeyWithVersionInternal(
        struct IServiceExecutionContext *a1,
        void *const a2,
        __time64_t a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        __time64_t a6,
        unsigned __int16 **a7)
{
  const unsigned __int16 *v9; // rbx
  __int64 v10; // r14
  __int64 v11; // r12
  __int64 v12; // r15
  __time64_t v13; // rdi
  unsigned __int16 **v14; // r13
  __time64_t v15; // rbx
  const char *v16; // rax
  int v17; // r9d
  unsigned int v18; // r8d
  int v19; // eax
  int v20; // eax
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rax
  __int64 v24; // rbx
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  unsigned __int16 *v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // r9
  int v33; // eax
  unsigned int v34; // edi
  int v35; // eax
  int v36; // eax
  char *v38; // [rsp+28h] [rbp-81h]
  __int64 v39; // [rsp+48h] [rbp-61h] BYREF
  unsigned __int16 *v40; // [rsp+50h] [rbp-59h] BYREF
  __time64_t v41; // [rsp+58h] [rbp-51h] BYREF
  __time64_t v42; // [rsp+60h] [rbp-49h] BYREF
  __int64 v43; // [rsp+68h] [rbp-41h] BYREF
  __int64 v44; // [rsp+70h] [rbp-39h] BYREF
  __int64 v45; // [rsp+78h] [rbp-31h] BYREF
  __int64 v46; // [rsp+80h] [rbp-29h]
  __int64 v47; // [rsp+88h] [rbp-21h] BYREF
  const char *v48[11]; // [rsp+90h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+47h]
  int v50; // [rsp+F8h] [rbp+4Fh] BYREF
  void *v51; // [rsp+100h] [rbp+57h]
  __time64_t Time; // [rsp+108h] [rbp+5Fh] BYREF

  Time = a3;
  v51 = a2;
  v50 = 0;
  v45 = 0;
  v43 = 0;
  v44 = 0;
  v41 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v40);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v47);
  v9 = a5;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v39,
    a5);
  v10 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 56LL))(a1);
  v11 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 104LL))(a1);
  v12 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 80LL))(a1);
  v46 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 64LL))(a1);
  CTraceFuncW<long>::CTraceFuncW<long>(
    v48,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    10486,
    (const char *)&v50,
    "HandleGetKeyWithVersionInternal",
    (wchar_t *)L"KeyVersion: %ls",
    v9);
  v13 = Time;
  if ( (Time & 0xFFFFFFFFFFFFFFFCuLL) != 0 || !a4 || !*a4 || (v14 = a7) == 0 )
  {
    v50 = -2147024809;
    goto LABEL_45;
  }
  v15 = a6;
  if ( !*(_DWORD *)(v39 - 16) && a6 <= 0 )
  {
    v50 = -2147024809;
    v16 = "(wstrVersion.IsEmpty() == false || versionTimeStamp > 0)";
    v17 = -2147024809;
    v18 = 10496;
LABEL_8:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleGetKeyWithVersionInternal",
      v18,
      v17,
      v16);
    goto LABEL_45;
  }
  *a7 = 0;
  v19 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v12 + 32LL))(v12, &v43, 0);
  v50 = v19;
  if ( v19 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleGetKeyWithVersionInternal",
      0x2905u,
      v19,
      "hr = pSvcWrapper->Impersonate(&client)");
LABEL_45:
    v34 = v50;
    goto LABEL_46;
  }
  v20 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)v12 + 40LL))(v12, &v43, &v45);
  v50 = v20;
  if ( v20 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleGetKeyWithVersionInternal",
      0x2906u,
      v20,
      "hr = pSvcWrapper->GetLogonId(&client, logonId)");
    goto LABEL_45;
  }
  if ( !*(_DWORD *)(v39 - 16) )
  {
    Time = v15;
    v21 = ATL::CTime::FormatGmt(&Time);
    ATL::CSimpleStringT<unsigned short,0>::operator=(&v39, v21);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v42);
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      0x290Eu,
      L"Key version asked for is %ls, timeStamp=%I64d.",
      v39,
      v15);
  }
  v22 = (*(__int64 (__fastcall **)(__int64, __int64 *, void *, __time64_t *))(*(_QWORD *)v12 + 24LL))(
          v12,
          &v45,
          v51,
          &v41);
  v50 = v22;
  if ( v22 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleGetKeyWithVersionInternal",
      0x2912u,
      v22,
      "hr = pSvcWrapper->GetIdentityHandle(logonId, handle, hIdentity)");
    goto LABEL_45;
  }
  if ( (*(unsigned __int8 (__fastcall **)(__int64, __time64_t))(*(_QWORD *)v10 + 48LL))(v10, v41)
    || !(*(unsigned __int8 (__fastcall **)(__int64, __time64_t))(*(_QWORD *)v10 + 24LL))(v10, v41) )
  {
    v17 = -2147186688;
    v50 = -2147186688;
    v16 = "!pIdentityWrapper->IsIdentityNULL(hIdentity) && pIdentityWrapper->HasAuthToken(hIdentity)";
    v18 = 10516;
    goto LABEL_8;
  }
  v23 = (*(__int64 (__fastcall **)(__int64, __time64_t))(*(_QWORD *)v10 + 40LL))(v10, v41);
  CAutoRefPtr<CIdentityTokenBag>::operator=(&v44, v23);
  v24 = v44;
  if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 24LL))(v11, v44) )
  {
    v50 = -2147188685;
    goto LABEL_45;
  }
  v38 = (char *)&v40;
  v25 = (*(__int64 (__fastcall **)(__int64, __int64, const unsigned __int16 *, __int64))(*(_QWORD *)v11 + 16LL))(
          v11,
          v24,
          a4,
          v39);
  v50 = v25;
  if ( v25 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleGetKeyWithVersionInternal",
      0x2923u,
      v25,
      "hr = pTokenBagWrapper->GetKeySpecific( hTokenBag, wcszPurpose, wstrVersion, wstrKeyMaterial)");
    goto LABEL_45;
  }
  if ( *((_DWORD *)v40 - 4) )
  {
    if ( (unsigned int)dword_1801C2080 > 5 )
    {
      v42 = v13;
      LOBYTE(Time) = (unsigned int)_o__wcsicmp(a4, L"StrongCredentialKey") == 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
        v26,
        (__int64)&unk_1801979A8,
        v27,
        v28,
        (__int64)&Time,
        (__int64)&v42);
    }
    goto LABEL_27;
  }
  if ( (unsigned int)dword_1801C2080 > 5 )
  {
    v42 = v13;
    LOBYTE(Time) = (unsigned int)_o__wcsicmp(a4, L"StrongCredentialKey") == 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
      v30,
      (__int64)&word_180197906,
      v31,
      v32,
      (__int64)&Time,
      (__int64)&v42);
  }
  if ( (v13 & 2) != 0 )
  {
    v50 = -2147186524;
    goto LABEL_45;
  }
  Time = v41;
  if ( v41 )
    _InterlockedIncrement((volatile signed __int32 *)(v41 + 8));
  v33 = RequestKey(a4, &Time, v10, v46);
  v34 = v33;
  v50 = v33;
  if ( v33 >= 0 )
  {
    v35 = (*(__int64 (__fastcall **)(__int64, __int64, const unsigned __int16 *, __int64, unsigned __int16 **))(*(_QWORD *)v11 + 16LL))(
            v11,
            v24,
            a4,
            v39,
            &v40);
    v50 = v35;
    if ( v35 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleGetKeyWithVersionInternal",
        0x2945u,
        v35,
        "hr = pTokenBagWrapper->GetKeySpecific( hTokenBag, wcszPurpose, wstrVersion, wstrKeyMaterial)");
      goto LABEL_45;
    }
    if ( !*((_DWORD *)v40 - 4) )
    {
      v50 = -2147186523;
      goto LABEL_45;
    }
LABEL_27:
    v29 = (unsigned __int16 *)malloc(2LL * (*((_DWORD *)v40 - 4) + 1));
    *v14 = v29;
    if ( v29 )
    {
      v36 = StringCchCopyW(v29, *((_DWORD *)v40 - 4) + 1, v40);
      v50 = v36;
      if ( v36 < 0 )
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          "HandleGetKeyWithVersionInternal",
          0x2953u,
          v36,
          "hr = StringCchCopyW(*pwszKeyMaterial, wstrKeyMaterial.GetLength() + 1, (LPCWSTR)wstrKeyMaterial)");
    }
    else
    {
      v50 = -2147024882;
    }
    goto LABEL_45;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x293E,
    (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    (const char *)(unsigned int)v33,
    (int)v38);
LABEL_46:
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v48);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v39);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v47);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v40);
  CAutoRefPtr<CSingleIdentity>::Deinit(&v41);
  CAutoRefPtr<IStoredIdentity>::Deinit(&v44);
  CAutoImpersonateClient::~CAutoImpersonateClient((CAutoImpersonateClient *)&v43);
  return v34;
}

```

## disassembly

```asm
0x18005942c  mov     rax, rsp
0x18005942f  mov     [rax+20h], rbx
0x180059433  mov     [rax+18h], r8
0x180059437  mov     [rax+10h], rdx
0x18005943b  push    rbp
0x18005943c  push    rsi
0x18005943d  push    rdi
0x18005943e  push    r12
0x180059440  push    r13
0x180059442  push    r14
0x180059444  push    r15
0x180059446  lea     rbp, [rax-47h]
0x18005944a  sub     rsp, 0B0h
0x180059451  mov     rsi, r9
0x180059454  mov     rdi, rcx
0x180059457  xor     r13d, r13d
0x18005945a  mov     [rbp+3Fh+arg_0], r13d
0x18005945e  mov     [rbp+3Fh+var_70], r13
0x180059462  mov     [rbp+3Fh+var_80], r13
0x180059466  mov     [rbp+3Fh+var_78], r13
0x18005946a  mov     [rbp+3Fh+var_90], r13
0x18005946e  lea     rcx, [rbp+3Fh+var_98]
0x180059472  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180059477  nop
0x180059478  lea     rcx, [rbp+3Fh+var_60]
0x18005947c  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180059481  nop
0x180059482  mov     rbx, [rbp+3Fh+arg_20]
0x180059486  mov     rdx, rbx
0x180059489  lea     rcx, [rbp+3Fh+var_A0]
0x18005948d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180059492  nop
0x180059493  mov     rax, [rdi]
0x180059496  mov     rcx, rdi
0x180059499  mov     rax, [rax+38h]
0x18005949d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800594a2  mov     r14, rax
0x1800594a5  mov     rcx, [rdi]
0x1800594a8  mov     rax, [rcx+68h]
0x1800594ac  mov     rcx, rdi
0x1800594af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800594b4  mov     r12, rax
0x1800594b7  mov     rcx, [rdi]
0x1800594ba  mov     rax, [rcx+50h]
0x1800594be  mov     rcx, rdi
0x1800594c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800594c6  mov     r15, rax
0x1800594c9  mov     rcx, [rdi]
0x1800594cc  mov     rax, [rcx+40h]
0x1800594d0  mov     rcx, rdi
0x1800594d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800594d8  mov     [rbp+3Fh+var_68], rax
0x1800594dc  mov     [rsp+30h], rbx
0x1800594e1  lea     rax, aKeyversionLs; "KeyVersion: %ls"
0x1800594e8  mov     [rsp+0E0h+var_B8], rax
0x1800594ed  lea     rax, aHandlegetkeywi; "HandleGetKeyWithVersionInternal"
0x1800594f4  mov     [rsp+0E0h+var_C0], rax
0x1800594f9  lea     r9, [rbp+3Fh+arg_0]
0x1800594fd  mov     r8d, 28F6h
0x180059503  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18005950a  lea     rcx, [rbp+3Fh+var_58]
0x18005950e  call    ??0?$CTraceFuncW@J@@QEAA@PEBDKAEAJ0PEBGZZ; CTraceFuncW<long>::CTraceFuncW<long>(char const *,ulong,long &,char const *,ushort const *,...)
0x180059513  nop
0x180059514  mov     rdi, [rbp+3Fh+Time]
0x180059518  test    rdi, 0FFFFFFFFFFFFFFFCh
0x18005951f  jnz     loc_180059925
0x180059525  test    rsi, rsi
0x180059528  jz      loc_180059925
0x18005952e  cmp     r13w, [rsi]
0x180059532  jz      loc_180059925
0x180059538  mov     r13, [rbp+3Fh+arg_30]
0x18005953c  test    r13, r13
0x18005953f  jz      loc_180059925
0x180059545  mov     rbx, [rbp+3Fh+arg_28]
0x180059549  mov     rax, [rbp+3Fh+var_A0]
0x18005954d  cmp     dword ptr [rax-10h], 0
0x180059551  jnz     short loc_18005958F
0x180059553  test    rbx, rbx
0x180059556  jg      short loc_18005958F
0x180059558  mov     [rbp+3Fh+arg_0], 80070057h
0x18005955f  lea     rax, aWstrversionIse; "(wstrVersion.IsEmpty() == false || vers"...
0x180059566  mov     r9d, 80070057h; int
0x18005956c  mov     r8d, 2900h; unsigned int
0x180059572  mov     [rsp+0E0h+var_C0], rax; char *
0x180059577  lea     rdx, aHandlegetkeywi; "HandleGetKeyWithVersionInternal"
0x18005957e  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180059585  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18005958a  jmp     loc_18005992C
0x18005958f  mov     qword ptr [r13+0], 0
0x180059597  mov     rax, [r15]
0x18005959a  xor     r8d, r8d
0x18005959d  lea     rdx, [rbp+3Fh+var_80]
0x1800595a1  mov     rcx, r15
0x1800595a4  mov     rax, [rax+20h]
0x1800595a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800595ad  mov     [rbp+3Fh+arg_0], eax
0x1800595b0  test    eax, eax
0x1800595b2  jns     short loc_1800595CB
0x1800595b4  lea     rcx, aHrPsvcwrapperI; "hr = pSvcWrapper->Impersonate(&client)"
0x1800595bb  mov     [rsp+0E0h+var_C0], rcx
0x1800595c0  mov     r9d, eax
0x1800595c3  mov     r8d, 2905h
0x1800595c9  jmp     short loc_180059577
0x1800595cb  mov     rax, [r15]
0x1800595ce  lea     r8, [rbp+3Fh+var_70]
0x1800595d2  lea     rdx, [rbp+3Fh+var_80]
0x1800595d6  mov     rcx, r15
0x1800595d9  mov     rax, [rax+28h]
0x1800595dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800595e2  mov     [rbp+3Fh+arg_0], eax
0x1800595e5  test    eax, eax
0x1800595e7  jns     short loc_180059603
0x1800595e9  lea     rcx, aHrPsvcwrapperG_2; "hr = pSvcWrapper->GetLogonId(&client, l"...
0x1800595f0  mov     [rsp+0E0h+var_C0], rcx
0x1800595f5  mov     r9d, eax
0x1800595f8  mov     r8d, 2906h
0x1800595fe  jmp     loc_180059577
0x180059603  mov     rax, [rbp+3Fh+var_A0]
0x180059607  cmp     dword ptr [rax-10h], 0
0x18005960b  jnz     short loc_180059668
0x18005960d  mov     [rbp+3Fh+Time], rbx
0x180059611  lea     r8, aYMDtHMSz; "%Y-%m-%dT%H:%M:%SZ"
0x180059618  lea     rdx, [rbp+3Fh+var_88]
0x18005961c  lea     rcx, [rbp+3Fh+Time]; Time
0x180059620  call    ?FormatGmt@CTime@ATL@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@PEBG@Z; ATL::CTime::FormatGmt(ushort const *)
0x180059625  nop
0x180059626  mov     rdx, rax
0x180059629  lea     rcx, [rbp+3Fh+var_A0]
0x18005962d  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x180059632  nop
0x180059633  lea     rcx, [rbp+3Fh+var_88]
0x180059637  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18005963c  mov     [rsp+0E0h+var_B8], rbx
0x180059641  mov     rax, [rbp+3Fh+var_A0]
0x180059645  mov     [rsp+0E0h+var_C0], rax
0x18005964a  lea     r9, aKeyVersionAske; "Key version asked for is %ls, timeStamp"...
0x180059651  mov     r8d, 290Eh; unsigned int
0x180059657  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18005965e  mov     ecx, 5; unsigned __int8
0x180059663  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180059668  mov     rax, [r15]
0x18005966b  lea     r9, [rbp+3Fh+var_90]
0x18005966f  mov     r8, [rbp+3Fh+arg_8]
0x180059673  lea     rdx, [rbp+3Fh+var_70]
0x180059677  mov     rcx, r15
0x18005967a  mov     rax, [rax+18h]
0x18005967e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059683  mov     [rbp+3Fh+arg_0], eax
0x180059686  test    eax, eax
0x180059688  jns     short loc_1800596A4
0x18005968a  lea     rcx, aHrPsvcwrapperG_3; "hr = pSvcWrapper->GetIdentityHandle(log"...
0x180059691  mov     [rsp+0E0h+var_C0], rcx
0x180059696  mov     r9d, eax
0x180059699  mov     r8d, 2912h
0x18005969f  jmp     loc_180059577
0x1800596a4  mov     rax, [r14]
0x1800596a7  mov     rdx, [rbp+3Fh+var_90]
0x1800596ab  mov     rcx, r14
0x1800596ae  mov     rax, [rax+30h]
0x1800596b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800596b7  test    al, al
0x1800596b9  jnz     loc_180059909
0x1800596bf  mov     rax, [r14]
0x1800596c2  mov     rdx, [rbp+3Fh+var_90]
0x1800596c6  mov     rcx, r14
0x1800596c9  mov     rax, [rax+18h]
0x1800596cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800596d2  test    al, al
0x1800596d4  jz      loc_180059909
0x1800596da  mov     rax, [r14]
0x1800596dd  mov     rdx, [rbp+3Fh+var_90]
0x1800596e1  mov     rcx, r14
0x1800596e4  mov     rax, [rax+28h]
0x1800596e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800596ed  mov     rdx, rax
0x1800596f0  lea     rcx, [rbp+3Fh+var_78]
0x1800596f4  call    ??4?$CAutoRefPtr@VCIdentityTokenBag@@@@QEAAAEAV0@PEAVCIdentityTokenBag@@@Z; CAutoRefPtr<CIdentityTokenBag>::operator=(CIdentityTokenBag *)
0x1800596f9  mov     rax, [r12]
0x1800596fd  mov     rbx, [rbp+3Fh+var_78]
0x180059701  mov     rdx, rbx
0x180059704  mov     rcx, r12
0x180059707  mov     rax, [rax+18h]
0x18005970b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059710  test    al, al
0x180059712  jz      short loc_180059720
0x180059714  mov     [rbp+3Fh+arg_0], 80048033h
0x18005971b  jmp     loc_18005992C
0x180059720  mov     rax, [r12]
0x180059724  lea     rcx, [rbp+3Fh+var_98]
0x180059728  mov     [rsp+0E0h+var_C0], rcx
0x18005972d  mov     r9, [rbp+3Fh+var_A0]
0x180059731  mov     r8, rsi
0x180059734  mov     rdx, rbx
0x180059737  mov     rcx, r12
0x18005973a  mov     rax, [rax+10h]
0x18005973e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059743  mov     [rbp+3Fh+arg_0], eax
0x180059746  test    eax, eax
0x180059748  jns     short loc_180059764
0x18005974a  lea     rcx, aHrPtokenbagwra; "hr = pTokenBagWrapper->GetKeySpecific( "...
0x180059751  mov     [rsp+0E0h+var_C0], rcx
0x180059756  mov     r9d, eax
0x180059759  mov     r8d, 2923h
0x18005975f  jmp     loc_180059577
0x180059764  mov     rax, [rbp+3Fh+var_98]
0x180059768  cmp     dword ptr [rax-10h], 0
0x18005976c  mov     eax, cs:dword_1801C2080
0x180059772  jz      short loc_1800597E2
0x180059774  cmp     eax, 5
0x180059777  jbe     short loc_1800597B1
0x180059779  mov     [rbp+3Fh+var_88], rdi
0x18005977d  lea     rdx, aStrongcredenti_0; "StrongCredentialKey"
0x180059784  mov     rcx, rsi
0x180059787  call    cs:__imp__o__wcsicmp
0x18005978d  test    eax, eax
0x18005978f  setz    byte ptr [rbp+3Fh+Time]
0x180059793  lea     rax, [rbp+3Fh+var_88]
0x180059797  mov     [rsp+0E0h+var_B8], rax
0x18005979c  lea     rax, [rbp+3Fh+Time]
0x1800597a0  mov     [rsp+0E0h+var_C0], rax
0x1800597a5  lea     rdx, unk_1801979A8
0x1800597ac  call    ??$Write@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)
0x1800597b1  mov     rax, [rbp+3Fh+var_98]
0x1800597b5  mov     ecx, [rax-10h]
0x1800597b8  inc     ecx
0x1800597ba  movsxd  rcx, ecx
0x1800597bd  add     rcx, rcx; Size
0x1800597c0  call    cs:__imp_malloc
0x1800597c6  mov     rcx, rax; unsigned __int16 *
0x1800597c9  mov     [r13+0], rax
0x1800597cd  test    rax, rax
0x1800597d0  jnz     loc_1800598D6
0x1800597d6  mov     [rbp+3Fh+arg_0], 8007000Eh
0x1800597dd  jmp     loc_18005992C
0x1800597e2  cmp     eax, 5
0x1800597e5  jbe     short loc_18005981F
0x1800597e7  mov     [rbp+3Fh+var_88], rdi
0x1800597eb  lea     rdx, aStrongcredenti_0; "StrongCredentialKey"
0x1800597f2  mov     rcx, rsi
0x1800597f5  call    cs:__imp__o__wcsicmp
0x1800597fb  test    eax, eax
0x1800597fd  setz    byte ptr [rbp+3Fh+Time]
0x180059801  lea     rax, [rbp+3Fh+var_88]
0x180059805  mov     [rsp+0E0h+var_B8], rax
0x18005980a  lea     rax, [rbp+3Fh+Time]
0x18005980e  mov     [rsp+0E0h+var_C0], rax; int
0x180059813  lea     rdx, word_180197906
0x18005981a  call    ??$Write@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)
0x18005981f  test    dil, 2
0x180059823  jz      short loc_180059831
0x180059825  mov     [rbp+3Fh+arg_0], 800488A4h
0x18005982c  jmp     loc_18005992C
0x180059831  mov     rax, [rbp+3Fh+var_90]
0x180059835  mov     [rbp+3Fh+Time], rax
0x180059839  test    rax, rax
0x18005983c  jz      short loc_180059842
0x18005983e  lock inc dword ptr [rax+8]
0x180059842  mov     r9, [rbp+3Fh+var_68]
0x180059846  mov     r8, r14
0x180059849  lea     rdx, [rbp+3Fh+Time]
0x18005984d  mov     rcx, rsi
0x180059850  call    ?RequestKey@@YAJPEBGV?$CAutoRefPtr@VCSingleIdentity@@@@PEBVIIdentityWrapper@@PEBVIRequestWrapper@@@Z; RequestKey(ushort const *,CAutoRefPtr<CSingleIdentity>,IIdentityWrapper const *,IRequestWrapper const *)
0x180059855  mov     edi, eax
0x180059857  mov     [rbp+3Fh+arg_0], eax
0x18005985a  test    eax, eax
0x18005985c  jns     short loc_18005987B
0x18005985e  mov     rcx, [rbp+47h]; this
0x180059862  mov     r9d, eax; char *
0x180059865  lea     r8, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18005986c  mov     edx, 293Eh; void *
0x180059871  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059876  jmp     loc_18005992F
0x18005987b  mov     rax, [r12]
0x18005987f  lea     rcx, [rbp+3Fh+var_98]
0x180059883  mov     [rsp+0E0h+var_C0], rcx
0x180059888  mov     r9, [rbp+3Fh+var_A0]
0x18005988c  mov     r8, rsi
0x18005988f  mov     rdx, rbx
0x180059892  mov     rcx, r12
0x180059895  mov     rax, [rax+10h]
0x180059899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005989e  mov     [rbp+3Fh+arg_0], eax
0x1800598a1  test    eax, eax
0x1800598a3  jns     short loc_1800598BF
0x1800598a5  lea     rcx, aHrPtokenbagwra; "hr = pTokenBagWrapper->GetKeySpecific( "...
0x1800598ac  mov     [rsp+0E0h+var_C0], rcx
0x1800598b1  mov     r9d, eax
0x1800598b4  mov     r8d, 2945h
0x1800598ba  jmp     loc_180059577
0x1800598bf  mov     rax, [rbp+3Fh+var_98]
0x1800598c3  cmp     dword ptr [rax-10h], 0
0x1800598c7  jnz     loc_1800597B1
0x1800598cd  mov     [rbp+3Fh+arg_0], 800488A5h
0x1800598d4  jmp     short loc_18005992C
0x1800598d6  mov     r8, [rbp+3Fh+var_98]; unsigned __int16 *
0x1800598da  mov     eax, [r8-10h]
0x1800598de  inc     eax
0x1800598e0  movsxd  rdx, eax; unsigned __int64
0x1800598e3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800598e8  mov     [rbp+3Fh+arg_0], eax
  ... truncated ...
```
