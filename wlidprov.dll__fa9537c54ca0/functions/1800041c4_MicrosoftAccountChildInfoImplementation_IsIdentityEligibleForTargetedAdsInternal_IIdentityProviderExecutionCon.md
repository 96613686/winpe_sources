# MicrosoftAccountChildInfoImplementation::IsIdentityEligibleForTargetedAdsInternal(IIdentityProviderExecutionContext *,IIdentityStorageFunctions *,ushort const *,int *)

- ea: `0x1800041c4`
- end: `0x18000481d`
- name: `?IsIdentityEligibleForTargetedAdsInternal@MicrosoftAccountChildInfoImplementation@@AEAAJPEAVIIdentityProviderExecutionContext@@PEAVIIdentityStorageFunctions@@PEBGPEAH@Z`
- size: `1625`
- prototype: `__int64 __fastcall(MicrosoftAccountChildInfoImplementation *__hidden this, struct IIdentityProviderExecutionContext *, struct IIdentityStorageFunctions *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003f50`

## callees

- `0x1800034c0`
- `0x1800041c4`
- `0x180004a7c`
- `0x180004b00`
- `0x180004b2c`
- `0x180004b44`
- `0x1800061a8`
- `0x1800090c0`
- `0x180009630`
- `0x18000a300`
- `0x18000a400`
- `0x18000bcc4`
- `0x180058010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__get_errno` at `0x180004489`
- `api-ms-win-crt-private-l1-1-0!_o__get_errno` at `0x180004489`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800045a7`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180004811`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800045a7`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180004811`

## string_xrefs

- `0x180004210`: `MicrosoftAccountChildInfoImplementation::IsIdentityEligibleForTargetedAdsInternal`
- `0x1800045c7`: `MicrosoftAccountChildInfoImplementation::IsIdentityEligibleForTargetedAdsInternal`
- `0x180004672`: `MicrosoftAccountChildInfoImplementation::IsIdentityEligibleForTargetedAdsInternal`
- `0x1800047c2`: `MicrosoftAccountChildInfoImplementation::IsIdentityEligibleForTargetedAdsInternal`
- `0x1800047e6`: `MicrosoftAccountChildInfoImplementation::IsIdentityEligibleForTargetedAdsInternal`
- `0x1800045b2`: `hr = pIdentityExecutionContext->GetSystemStoreLiteFunctions()->GetStoredIdentityProperty( spUserSid, PPCRL_CREDPROPERTY_CHILDFLAGS, &spPropertyValue, nullptr)`
- `0x180004715`: `Failed to read the user properties from the immersive cache.`
- `0x180004760`: `hr = pIdentityExecutionContext->GetSystemStoreLiteFunctions()->GetCurrentUserSidString(&spUserSid)`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall MicrosoftAccountChildInfoImplementation::IsIdentityEligibleForTargetedAdsInternal(
        MicrosoftAccountChildInfoImplementation *this,
        struct IIdentityProviderExecutionContext *a2,
        struct IIdentityStorageFunctions *a3,
        const unsigned __int16 *a4,
        int *a5)
{
  unsigned __int64 v8; // rsi
  PPTraceStatus *v9; // rcx
  PPTraceStatus *v10; // rcx
  char v11; // al
  int *v12; // rdi
  __int64 (__fastcall *v13)(struct IIdentityStorageFunctions *, _QWORD *, _WORD **, _QWORD, int *, __int64 *); // rbx
  __int64 v14; // rax
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  char v21; // bl
  PPTraceStatus *v22; // rcx
  unsigned int v23; // edi
  unsigned int v24; // ebx
  __int64 v25; // rcx
  unsigned __int64 v26; // rax
  PPTraceStatus *v27; // rcx
  bool v29; // zf
  const char *v30; // rcx
  unsigned int v31; // r8d
  int v32; // r9d
  const char *v33; // rax
  unsigned int v34; // r8d
  PPTraceStatus *v35; // rcx
  char *v36; // [rsp+20h] [rbp-A1h]
  char *v37; // [rsp+20h] [rbp-A1h]
  __int64 v38; // [rsp+28h] [rbp-99h]
  int v39; // [rsp+40h] [rbp-81h] BYREF
  __int64 v40; // [rsp+48h] [rbp-79h] BYREF
  _WORD *v41; // [rsp+50h] [rbp-71h] BYREF
  _QWORD v42[3]; // [rsp+58h] [rbp-69h] BYREF
  _QWORD v43[3]; // [rsp+70h] [rbp-51h] BYREF
  _QWORD v44[2]; // [rsp+88h] [rbp-39h] BYREF
  __int64 v45; // [rsp+98h] [rbp-29h]
  int *v46; // [rsp+A0h] [rbp-21h]
  const char *v47; // [rsp+A8h] [rbp-19h]
  _QWORD v48[12]; // [rsp+B0h] [rbp-11h] BYREF
  int v49; // [rsp+120h] [rbp+5Fh] BYREF
  int v50; // [rsp+124h] [rbp+63h]

  v50 = HIDWORD(this);
  v49 = 0;
  v40 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v48[0] = "MicrosoftAccountChildInfoImplementation::IsIdentityEligibleForTargetedAdsInternal";
  v48[1] = &v49;
  v48[2] = 0;
  v48[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\microsoftaccountchildinfoimplementation.cpp",
    "MicrosoftAccountChildInfoImplementation::IsIdentityEligibleForTargetedAdsInternal",
    (const char *)0x61,
    0,
    (const unsigned __int16 *)v36);
  v44[1] = qword_180062D40;
  v8 = 14;
  v45 = 14;
  v46 = &v49;
  v47 = "MicrosoftAccountChildInfoImplementation::IsIdentityEligibleForTargetedAdsInternal";
  if ( PPTraceStatus::GetAssertFlag(v9) == 1 || (v29 = PPTraceStatus::GetAssertFlag(v10) == 2, v11 = 0, v29) )
    v11 = 1;
  if ( !v11 )
  {
    v8 = -(__int64)((Microsoft_Windows_LiveIdEnableBits & 0x20) != 0) & 0xE;
    v45 = v8;
  }
  v12 = a5;
  if ( !a5 )
  {
    v49 = -2147024809;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\microsoftaccountchildinfoimplementation.cpp",
      "MicrosoftAccountChildInfoImplementation::IsIdentityEligibleForTargetedAdsInternal",
      0x70u,
      -2147024809,
      "hr = E_INVALIDARG");
    goto LABEL_24;
  }
  *a5 = 0;
  if ( a4 && *a4 )
  {
    v39 = 0;
    v13 = *(__int64 (__fastcall **)(struct IIdentityStorageFunctions *, _QWORD *, _WORD **, _QWORD, int *, __int64 *))(*(_QWORD *)a3 + 24LL);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v41,
      L"ChildFlags");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      v44,
      a4);
    v49 = v13(a3, v44, &v41, 0, &v39, &v40);
    ATL::CStringData::Release((ATL::CStringData *)(v44[0] - 24LL));
    ATL::CStringData::Release((ATL::CStringData *)(v41 - 12));
    v14 = v40;
    if ( v49 >= 0 && !*(_DWORD *)(v40 - 16) )
    {
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\microsoftaccountchildinfoimplementation.cpp",
        0x83u,
        L"The saved immersive property for ChildFlags element was empty.");
      v32 = -2147023728;
      v33 = "hr = HRESULT_FROM_WIN32(ERROR_NOT_FOUND)";
      v34 = 132;
LABEL_45:
      v49 = v32;
LABEL_46:
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\microsoftaccountchildinfoimplementation.cpp",
        "MicrosoftAccountChildInfoImplementation::IsIdentityEligibleForTargetedAdsInternal",
        v34,
        v32,
        v33);
      goto LABEL_23;
    }
    if ( v49 == -2147023579 )
    {
      v49 = 0;
      goto LABEL_11;
    }
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\microsoftaccountchildinfoimplementation.cpp",
      0x8Du,
      L"Failed to read the user properties from the immersive cache.");
    v32 = v49;
    if ( v49 < 0 )
    {
      v33 = "hr";
      v34 = 142;
      goto LABEL_46;
    }
  }
  v14 = v40;
LABEL_11:
  if ( *(_DWORD *)(v14 - 16) )
    goto LABEL_18;
  v39 = 0;
  memset(v43, 0, sizeof(v43));
  memset(v42, 0, sizeof(v42));
  v15 = (*(__int64 (__fastcall **)(struct IIdentityProviderExecutionContext *))(*(_QWORD *)a2 + 48LL))(a2);
  v16 = (*(__int64 (__fastcall **)(__int64, int *, _QWORD))(*(_QWORD *)v15 + 8LL))(v15, &v39, 0);
  v49 = v16;
  if ( v16 < 0 )
  {
    v30 = "hr = pIdentityExecutionContext->GetSystemStoreLiteFunctions()->IsConnected(&connected, nullptr)";
    v31 = 153;
    goto LABEL_40;
  }
  if ( !v39 )
  {
    v49 = -2147023579;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\microsoftaccountchildinfoimplementation.cpp",
      "MicrosoftAccountChildInfoImplementation::IsIdentityEligibleForTargetedAdsInternal",
      0x9Du,
      -2147023579,
      "hr = HRESULT_FROM_WIN32(ERROR_NO_SUCH_USER)");
    goto LABEL_41;
  }
  v17 = (*(__int64 (__fastcall **)(struct IIdentityProviderExecutionContext *))(*(_QWORD *)a2 + 48LL))(a2);
  v16 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v17 + 32LL))(v17, v43);
  v49 = v16;
  if ( v16 < 0 )
  {
    v30 = "hr = pIdentityExecutionContext->GetSystemStoreLiteFunctions()->GetCurrentUserSidString(&spUserSid)";
    v31 = 160;
    goto LABEL_40;
  }
  v18 = (*(__int64 (__fastcall **)(struct IIdentityProviderExecutionContext *))(*(_QWORD *)a2 + 48LL))(a2);
  v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, _QWORD *, _QWORD))(*(_QWORD *)v18 + 24LL))(
          v18,
          v43[0],
          L"ChildFlags",
          v42,
          0);
  v49 = v16;
  if ( v16 < 0 )
  {
    v30 = "hr = pIdentityExecutionContext->GetSystemStoreLiteFunctions()->GetStoredIdentityProperty( spUserSid, PPCRL_CRE"
          "DPROPERTY_CHILDFLAGS, &spPropertyValue, nullptr)";
    v31 = 165;
LABEL_40:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\microsoftaccountchildinfoimplementation.cpp",
      "MicrosoftAccountChildInfoImplementation::IsIdentityEligibleForTargetedAdsInternal",
      v31,
      v16,
      v30);
    goto LABEL_41;
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(&v40, v42[0]);
  if ( *(_DWORD *)(v40 - 16) )
  {
    Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(v42);
    Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(v43);
LABEL_18:
    v39 = 0;
    v41 = 0;
    v19 = (*(__int64 (__fastcall **)(struct IIdentityProviderExecutionContext *))(*(_QWORD *)a2 + 8LL))(a2);
    v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 40LL))(v19);
    v21 = (*(__int64 (__fastcall **)(__int64, __int64, _WORD **, __int64))(*(_QWORD *)v20 + 24LL))(v20, v40, &v41, 16);
    _o__get_errno(&v39);
    if ( !v39 && (!v41 || !*v41) )
    {
      if ( (v21 & 1) != 0 )
        *v12 = 1;
      goto LABEL_23;
    }
    LODWORD(v38) = v39;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\microsoftaccountchildinfoimplementation.cpp",
      0xBAu,
      L"The saved child flags value is malformed. flags = %ls, errno = %d",
      v40,
      v38);
    v32 = -2147024883;
    v33 = "hr = HRESULT_FROM_WIN32(ERROR_INVALID_DATA)";
    v34 = 187;
    goto LABEL_45;
  }
  TracePrintW(
    2u,
    "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\microsoftaccountchildinfoimplementation.cpp",
    0xABu,
    L"The saved system store properties are missing the ChildFlags element.");
  v49 = -2147023728;
  Telemetry::IfFailExit(
    "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\microsoftaccountchildinfoimplementation.cpp",
    "MicrosoftAccountChildInfoImplementation::IsIdentityEligibleForTargetedAdsInternal",
    0xACu,
    -2147023728,
    "hr = HRESULT_FROM_WIN32(ERROR_NOT_FOUND)");
LABEL_41:
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(v42);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(v43);
LABEL_23:
  LODWORD(v37) = *v12;
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\microsoftaccountchildinfoimplementation.cpp",
    0xCAu,
    L"Returning value, *pIsEligible=%d",
    v37);
LABEL_24:
  v23 = ErrorHandlingUtilities::MapInternalErrorToExternal(v49, 0, 0);
  v24 = v49;
  if ( v49 && v8 )
  {
    if ( PPTraceStatus::GetAssertFlag(v22) == 2
      && (v24 == -2147024890
       || v24 == -2147023834
       || v24 == -2147023179
       || v24 == -2147023174
       || v24 == -2147023173
       || v24 == -2147023170
       || v24 == -2147023143) )
    {
      if ( (Microsoft_Windows_LiveIdEnableBits & 0x20) != 0 )
        McTemplateU0sd_EventWriteTransfer(
          v25,
          Telemetry_ErrorVerifier,
          "MicrosoftAccountChildInfoImplementation::IsIdentityEligibleForTargetedAdsInternal",
          v24);
      DebugBreak();
    }
    v26 = 0;
    v27 = (PPTraceStatus *)qword_180062D40;
    while ( v26 < v8 )
    {
      if ( v24 == *((_DWORD *)qword_180062D40 + v26) )
        goto LABEL_31;
      ++v26;
    }
    if ( (Microsoft_Windows_LiveIdEnableBits & 0x20) != 0 )
      McTemplateU0sd_EventWriteTransfer(
        qword_180062D40,
        Telemetry_ErrorVerifier,
        "MicrosoftAccountChildInfoImplementation::IsIdentityEligibleForTargetedAdsInternal",
        v24);
    if ( PPTraceStatus::GetAssertFlag(v27) == 1 || PPTraceStatus::GetAssertFlag(v35) == 2 )
      DebugBreak();
  }
LABEL_31:
  CTraceFuncW<long>::~CTraceFuncW<long>(v48);
  ATL::CStringData::Release((ATL::CStringData *)(v40 - 24));
  return v23;
}

```

## disassembly

```asm
0x1800041c4  mov     qword ptr [rsp-8+arg_0], rcx
0x1800041c9  push    rbp
0x1800041ca  push    rbx
0x1800041cb  push    rsi
0x1800041cc  push    rdi
0x1800041cd  push    r12
0x1800041cf  push    r13
0x1800041d1  push    r14
0x1800041d3  push    r15
0x1800041d5  lea     rbp, [rsp-17h]
0x1800041da  sub     rsp, 0D8h
0x1800041e1  mov     r15, r9
0x1800041e4  mov     r12, r8
0x1800041e7  mov     r14, rdx
0x1800041ea  xor     r13d, r13d
0x1800041ed  mov     [rbp+4Fh+arg_0], r13d
0x1800041f1  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800041f8  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800041ff  mov     rax, [rax+18h]
0x180004203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004208  add     rax, 18h
0x18000420c  mov     [rbp+4Fh+var_C8], rax
0x180004210  lea     rbx, aMicrosoftaccou_1; "MicrosoftAccountChildInfoImplementation"...
0x180004217  mov     [rbp+4Fh+var_60], rbx
0x18000421b  lea     rax, [rbp+4Fh+arg_0]
0x18000421f  mov     [rbp+4Fh+var_58], rax
0x180004223  mov     [rbp+4Fh+var_50], r13
0x180004227  mov     [rbp+4Fh+var_48], r13
0x18000422b  xor     r9d, r9d; unsigned int
0x18000422e  lea     r8d, [r13+61h]; char *
0x180004232  mov     rdx, rbx; char *
0x180004235  lea     rcx, aOnecoreuapDsEx_27; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x18000423c  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180004241  nop
0x180004242  lea     rax, qword_180062D40
0x180004249  mov     [rbp+4Fh+var_80], rax
0x18000424d  lea     esi, [r13+0Eh]
0x180004251  mov     [rbp+4Fh+var_78], rsi
0x180004255  lea     rax, [rbp+4Fh+arg_0]
0x180004259  mov     [rbp+4Fh+var_70], rax
0x18000425d  mov     [rbp+4Fh+var_68], rbx
0x180004261  call    ?GetAssertFlag@PPTraceStatus@@YAKXZ; PPTraceStatus::GetAssertFlag(void)
0x180004266  cmp     eax, 1
0x180004269  jnz     loc_180004568
0x18000426f  mov     al, 1
0x180004271  test    al, al
0x180004273  jz      loc_18000454C
0x180004279  mov     rdi, [rbp+4Fh+arg_20]
0x18000427d  test    rdi, rdi
0x180004280  jz      loc_1800046AA
0x180004286  mov     [rdi], r13d
0x180004289  test    r15, r15
0x18000428c  jz      loc_18000457E
0x180004292  cmp     [r15], r13w
0x180004296  jz      loc_18000457E
0x18000429c  mov     [rsp+110h+var_D0], r13d
0x1800042a1  mov     rax, [r12]
0x1800042a5  mov     rbx, [rax+18h]
0x1800042a9  lea     rdx, aChildflags; "ChildFlags"
0x1800042b0  lea     rcx, [rbp+4Fh+var_C0]
0x1800042b4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800042b9  nop
0x1800042ba  mov     rdx, r15
0x1800042bd  lea     rcx, [rbp+4Fh+var_88]
0x1800042c1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800042c6  nop
0x1800042c7  lea     rax, [rbp+4Fh+var_C8]
0x1800042cb  mov     [rsp+110h+var_E8], rax
0x1800042d0  lea     rax, [rsp+110h+var_D0]
0x1800042d5  mov     [rsp+110h+var_F0], rax
0x1800042da  xor     r9d, r9d
0x1800042dd  lea     r8, [rbp+4Fh+var_C0]
0x1800042e1  lea     rdx, [rbp+4Fh+var_88]
0x1800042e5  mov     rcx, r12
0x1800042e8  mov     rax, rbx
0x1800042eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042f0  mov     [rbp+4Fh+arg_0], eax
0x1800042f3  mov     rcx, [rbp+4Fh+var_88]
0x1800042f7  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800042fb  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180004300  nop
0x180004301  mov     rcx, [rbp+4Fh+var_C0]
0x180004305  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180004309  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000430e  mov     rax, [rbp+4Fh+var_C8]
0x180004312  mov     ecx, [rbp+4Fh+arg_0]
0x180004315  test    ecx, ecx
0x180004317  jns     loc_1800045EF
0x18000431d  lea     r15, aOnecoreuapDsEx_27; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180004324  cmp     ecx, 80070525h
0x18000432a  jnz     loc_180004715
0x180004330  mov     [rbp+4Fh+arg_0], r13d
0x180004334  cmp     [rax-10h], r13d
0x180004338  jnz     loc_180004438
0x18000433e  mov     [rsp+110h+var_D0], r13d
0x180004343  mov     [rbp+4Fh+var_A0], r13
0x180004347  mov     [rbp+4Fh+var_90], r13
0x18000434b  mov     [rbp+4Fh+var_98], r13
0x18000434f  mov     [rbp+4Fh+var_B8], r13
0x180004353  mov     [rbp+4Fh+var_A8], r13
0x180004357  mov     [rbp+4Fh+var_B0], r13
0x18000435b  mov     rax, [r14]
0x18000435e  mov     rcx, r14
0x180004361  mov     rax, [rax+30h]
0x180004365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000436a  mov     r9, rax
0x18000436d  mov     rcx, [rax]
0x180004370  mov     rax, [rcx+8]
0x180004374  xor     r8d, r8d
0x180004377  lea     rdx, [rsp+110h+var_D0]
0x18000437c  mov     rcx, r9
0x18000437f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004384  mov     [rbp+4Fh+arg_0], eax
0x180004387  test    eax, eax
0x180004389  js      loc_18000474E
0x18000438f  cmp     [rsp+110h+var_D0], r13d
0x180004394  jz      loc_180004686
0x18000439a  mov     rax, [r14]
0x18000439d  mov     rcx, r14
0x1800043a0  mov     rax, [rax+30h]
0x1800043a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043a9  mov     r8, rax
0x1800043ac  mov     rcx, [rax]
0x1800043af  mov     rax, [rcx+20h]
0x1800043b3  lea     rdx, [rbp+4Fh+var_A0]
0x1800043b7  mov     rcx, r8
0x1800043ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043bf  mov     [rbp+4Fh+arg_0], eax
0x1800043c2  test    eax, eax
0x1800043c4  js      loc_180004760
0x1800043ca  mov     rax, [r14]
0x1800043cd  mov     rcx, r14
0x1800043d0  mov     rax, [rax+30h]
0x1800043d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043d9  mov     r10, rax
0x1800043dc  mov     rcx, [rax]
0x1800043df  mov     rax, [rcx+18h]
0x1800043e3  mov     [rsp+110h+var_F0], r13
0x1800043e8  lea     r9, [rbp+4Fh+var_B8]
0x1800043ec  lea     r8, aChildflags; "ChildFlags"
0x1800043f3  mov     rdx, [rbp+4Fh+var_A0]
0x1800043f7  mov     rcx, r10
0x1800043fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043ff  mov     [rbp+4Fh+arg_0], eax
0x180004402  test    eax, eax
0x180004404  js      loc_1800045B2
0x18000440a  mov     rdx, [rbp+4Fh+var_B8]
0x18000440e  lea     rcx, [rbp+4Fh+var_C8]
0x180004412  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180004417  mov     rax, [rbp+4Fh+var_C8]
0x18000441b  cmp     [rax-10h], r13d
0x18000441f  jz      loc_1800046DA
0x180004425  lea     rcx, [rbp+4Fh+var_B8]
0x180004429  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x18000442e  nop
0x18000442f  lea     rcx, [rbp+4Fh+var_A0]
0x180004433  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x180004438  mov     [rsp+110h+var_D0], r13d
0x18000443d  mov     [rbp+4Fh+var_C0], r13
0x180004441  mov     rax, [r14]
0x180004444  mov     rcx, r14
0x180004447  mov     rax, [rax+8]
0x18000444b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004450  mov     rdx, rax
0x180004453  mov     rcx, [rax]
0x180004456  mov     rax, [rcx+28h]
0x18000445a  mov     rcx, rdx
0x18000445d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004462  mov     r10, rax
0x180004465  mov     rcx, [rax]
0x180004468  mov     rax, [rcx+18h]
0x18000446c  mov     r9d, 10h
0x180004472  lea     r8, [rbp+4Fh+var_C0]
0x180004476  mov     rdx, [rbp+4Fh+var_C8]
0x18000447a  mov     rcx, r10
0x18000447d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004482  mov     ebx, eax
0x180004484  lea     rcx, [rsp+110h+var_D0]
0x180004489  call    cs:__imp__o__get_errno
0x18000448f  mov     eax, [rsp+110h+var_D0]
0x180004493  test    eax, eax
0x180004495  jnz     loc_18000462F
0x18000449b  mov     rcx, [rbp+4Fh+var_C0]
0x18000449f  test    rcx, rcx
0x1800044a2  jz      short loc_1800044AE
0x1800044a4  cmp     [rcx], r13w
0x1800044a8  jnz     loc_18000462F
0x1800044ae  test    bl, 1
0x1800044b1  jz      short loc_1800044B9
0x1800044b3  mov     dword ptr [rdi], 1
0x1800044b9  mov     eax, [rdi]
0x1800044bb  mov     dword ptr [rsp+110h+var_F0], eax
0x1800044bf  lea     r9, aReturningValue; "Returning value, *pIsEligible=%d"
0x1800044c6  mov     r8d, 0CAh; unsigned int
0x1800044cc  mov     rdx, r15; char *
0x1800044cf  mov     ecx, 5; unsigned __int8
0x1800044d4  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800044d9  xor     r8d, r8d; bool *
0x1800044dc  xor     edx, edx; bool
0x1800044de  mov     ecx, [rbp+4Fh+arg_0]; int
0x1800044e1  call    ?MapInternalErrorToExternal@ErrorHandlingUtilities@@SAJJ_NPEA_N@Z; ErrorHandlingUtilities::MapInternalErrorToExternal(long,bool,bool *)
0x1800044e6  mov     edi, eax
0x1800044e8  mov     ebx, [rbp+4Fh+arg_0]
0x1800044eb  test    ebx, ebx
0x1800044ed  jz      short loc_18000451F
0x1800044ef  test    rsi, rsi
0x1800044f2  jz      short loc_18000451F
0x1800044f4  call    ?GetAssertFlag@PPTraceStatus@@YAKXZ; PPTraceStatus::GetAssertFlag(void)
0x1800044f9  cmp     eax, 2
0x1800044fc  jz      loc_18000458E
0x180004502  mov     rax, r13
0x180004505  lea     rcx, qword_180062D40
0x18000450c  cmp     rax, rsi
0x18000450f  jnb     loc_1800047DA
0x180004515  cmp     ebx, [rcx+rax*4]
0x180004518  jz      short loc_18000451F
0x18000451a  inc     rax
0x18000451d  jmp     short loc_18000450C
0x18000451f  lea     rcx, [rbp+4Fh+var_60]
0x180004523  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180004528  nop
0x180004529  mov     rcx, [rbp+4Fh+var_C8]
0x18000452d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180004531  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180004536  mov     eax, edi
0x180004538  add     rsp, 0D8h
0x18000453f  pop     r15
0x180004541  pop     r14
0x180004543  pop     r13
0x180004545  pop     r12
0x180004547  pop     rdi
0x180004548  pop     rsi
0x180004549  pop     rbx
0x18000454a  pop     rbp
0x18000454b  retn
0x18000454c  mov     al, cs:Microsoft_Windows_LiveIdEnableBits
0x180004552  and     al, 20h
0x180004554  neg     al
0x180004556  sbb     rax, rax
0x180004559  and     rax, rsi
0x18000455c  mov     rsi, rax
0x18000455f  mov     [rbp+4Fh+var_78], rax
0x180004563  jmp     loc_180004279
0x180004568  call    ?GetAssertFlag@PPTraceStatus@@YAKXZ; PPTraceStatus::GetAssertFlag(void)
0x18000456d  cmp     eax, 2
0x180004570  mov     al, r13b
0x180004573  jnz     loc_180004271
0x180004579  jmp     loc_18000426F
0x18000457e  lea     r15, aOnecoreuapDsEx_27; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180004585  mov     rax, [rbp+4Fh+var_C8]
0x180004589  jmp     loc_180004334
0x18000458e  cmp     ebx, 80070006h
0x180004594  jnz     loc_180004772
0x18000459a  test    cs:Microsoft_Windows_LiveIdEnableBits, 20h
0x1800045a1  jnz     loc_1800047BF
0x1800045a7  call    cs:__imp_DebugBreak
0x1800045ad  jmp     loc_180004502
0x1800045b2  lea     rcx, aHrPidentityexe_0; "hr = pIdentityExecutionContext->GetSyst"...
0x1800045b9  mov     r8d, 0A5h; unsigned int
0x1800045bf  mov     [rsp+110h+var_F0], rcx; char *
0x1800045c4  mov     r9d, eax; int
0x1800045c7  lea     rdx, aMicrosoftaccou_1; "MicrosoftAccountChildInfoImplementation"...
0x1800045ce  mov     rcx, r15; char *
0x1800045d1  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800045d6  nop
0x1800045d7  lea     rcx, [rbp+4Fh+var_B8]
0x1800045db  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x1800045e0  nop
0x1800045e1  lea     rcx, [rbp+4Fh+var_A0]
0x1800045e5  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x1800045ea  jmp     loc_1800044B9
0x1800045ef  cmp     [rax-10h], r13d
0x1800045f3  jnz     loc_18000431D
0x1800045f9  lea     r9, aTheSavedImmers; "The saved immersive property for ChildF"...
0x180004600  mov     r8d, 83h; unsigned int
0x180004606  lea     r15, aOnecoreuapDsEx_27; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x18000460d  mov     rdx, r15; char *
0x180004610  mov     ecx, 2; unsigned __int8
0x180004615  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000461a  mov     r9d, 80070490h
0x180004620  lea     rax, aHrHresultFromW_1; "hr = HRESULT_FROM_WIN32(ERROR_NOT_FOUND"...
0x180004627  mov     r8d, 84h
0x18000462d  jmp     short loc_180004669
0x18000462f  mov     dword ptr [rsp+110h+var_E8], eax
0x180004633  mov     rax, [rbp+4Fh+var_C8]
0x180004637  mov     [rsp+110h+var_F0], rax
0x18000463c  lea     r9, aTheSavedChildF; "The saved child flags value is malforme"...
0x180004643  mov     r8d, 0BAh; unsigned int
0x180004649  mov     rdx, r15; char *
0x18000464c  mov     ecx, 2; unsigned __int8
0x180004651  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180004656  mov     r9d, 8007000Dh; int
0x18000465c  lea     rax, aHrHresultFromW_6; "hr = HRESULT_FROM_WIN32(ERROR_INVALID_D"...
0x180004663  mov     r8d, 0BBh; unsigned int
0x180004669  mov     [rbp+4Fh+arg_0], r9d
0x18000466d  mov     [rsp+110h+var_F0], rax; char *
0x180004672  lea     rdx, aMicrosoftaccou_1; "MicrosoftAccountChildInfoImplementation"...
0x180004679  mov     rcx, r15; char *
0x18000467c  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180004681  jmp     loc_1800044B9
  ... truncated ...
```
