# HandleGetUserPropertiesFromSystemStore(ushort const *,ulong *,_WLIDIdentityProperty * *)

- ea: `0x180010290`
- end: `0x18001087f`
- name: `?HandleGetUserPropertiesFromSystemStore@@YAJPEBGPEAKPEAPEAU_WLIDIdentityProperty@@@Z`
- size: `1519`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *, struct _WLIDIdentityProperty **)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180010180`

## callees

- `0x18000c050`
- `0x18000e8dc`
- `0x18000ed3c`
- `0x180010290`
- `0x180010888`
- `0x1800133c8`
- `0x180014824`
- `0x180015860`
- `0x180015fb0`
- `0x180018f80`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001cf20`
- `0x18001dfec`
- `0x18001f968`
- `0x180020b10`
- `0x1800801dc`
- `0x180081cac`
- `0x180084e88`
- `0x1800a4778`
- `0x1800a716c`
- `0x1800af474`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001047b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001052f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180010559`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001047b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001052f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180010559`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180010726`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180010726`

## string_xrefs

- `0x180010364`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x1800107a6`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180010769`: `hr = client.ImpersonateClient()`
- `0x1800107c1`: `hr = client.GetTokenUser(pszSid)`
- `0x18001081a`: `hr = StringCchCopyW(apIdentityProperty[dwIndex].pszProperty, pszProp.GetLength() + 1, (LPCWSTR)pszProp)`
- `0x180010853`: `hr = StringCchCopyW(apIdentityProperty[dwIndex].pszValue, pszPropValue.GetLength() + 1, (LPCWSTR)pszPropValue)`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall HandleGetUserPropertiesFromSystemStore(
        unsigned __int16 *a1,
        unsigned int *a2,
        struct _WLIDIdentityProperty **a3)
{
  struct _LUID v4; // rbx
  struct _WLIDIdentityProperty *v5; // r12
  unsigned int v6; // r13d
  int v7; // eax
  int TokenUser; // eax
  int LogonId; // eax
  void *v10; // rax
  int v11; // edi
  unsigned int v12; // ebx
  unsigned int v13; // eax
  int v14; // eax
  unsigned int v15; // r14d
  struct _WLIDIdentityProperty *v16; // rax
  struct _WLIDIdentityProperty *v17; // rdi
  unsigned int v18; // r14d
  bool v19; // zf
  void *v20; // rax
  void *v21; // rax
  __int16 *v22; // rcx
  int v23; // eax
  int v24; // eax
  __int64 v25; // rdx
  _WORD *v26; // r8
  __int64 v27; // rax
  __int16 v28; // r9
  _WORD *v29; // rcx
  int v30; // r9d
  __int16 *v31; // rcx
  int v32; // eax
  int v33; // eax
  __int64 v34; // rdx
  _WORD *v35; // r8
  __int64 v36; // rax
  __int16 v37; // r9
  _WORD *v38; // rcx
  int v39; // eax
  unsigned int v40; // edi
  __int64 v41; // rcx
  const char *v43; // rax
  unsigned int v44; // r8d
  const unsigned __int16 *v45; // [rsp+28h] [rbp-B9h]
  __int64 v46; // [rsp+38h] [rbp-A9h] BYREF
  __int64 v47; // [rsp+40h] [rbp-A1h] BYREF
  __int64 v48; // [rsp+48h] [rbp-99h] BYREF
  struct _LUID v49; // [rsp+50h] [rbp-91h] BYREF
  __int64 v50; // [rsp+58h] [rbp-89h] BYREF
  char *v51; // [rsp+60h] [rbp-81h] BYREF
  __int64 v52; // [rsp+68h] [rbp-79h] BYREF
  struct _LUID v53; // [rsp+70h] [rbp-71h]
  struct _WLIDIdentityProperty *v54; // [rsp+80h] [rbp-61h]
  unsigned int v55; // [rsp+88h] [rbp-59h]
  __int64 v56; // [rsp+90h] [rbp-51h]
  _BYTE v57[64]; // [rsp+98h] [rbp-49h] BYREF
  _QWORD v58[12]; // [rsp+D8h] [rbp-9h] BYREF
  int v61; // [rsp+160h] [rbp+7Fh] BYREF

  v61 = 0;
  v48 = 0;
  v4 = 0;
  v53 = 0;
  v51 = (char *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v5 = 0;
  v54 = 0;
  v56 = 0;
  v6 = 0;
  v55 = 0;
  v47 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v46 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v49 = 0;
  v58[0] = "HandleGetUserPropertiesFromSystemStore";
  v58[1] = &v61;
  v58[2] = 0;
  v58[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    "HandleGetUserPropertiesFromSystemStore",
    (const char *)0x2399,
    0,
    v45);
  v7 = CAutoImpersonateClient::ImpersonateClient((CAutoImpersonateClient *)&v48, 0);
  v61 = v7;
  if ( v7 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleGetUserPropertiesFromSystemStore",
      0x239Bu,
      v7,
      "hr = client.ImpersonateClient()");
    goto LABEL_39;
  }
  TokenUser = CAutoImpersonateClient::GetTokenUser((CAutoImpersonateClient *)&v48, &v51);
  v61 = TokenUser;
  if ( TokenUser < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleGetUserPropertiesFromSystemStore",
      0x239Cu,
      TokenUser,
      "hr = client.GetTokenUser(pszSid)");
    goto LABEL_39;
  }
  LogonId = CAutoImpersonateClient::GetLogonId((CAutoImpersonateClient *)&v48, &v49);
  v61 = LogonId;
  if ( LogonId < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleGetUserPropertiesFromSystemStore",
      0x239Du,
      LogonId,
      "hr = client.GetLogonId(logonId)");
    goto LABEL_39;
  }
  v10 = operator new(0x120u, (const struct std::nothrow_t *)std::nothrow);
  v11 = (int)v10;
  v58[4] = v10;
  if ( v10 )
  {
    v58[5] = &v50;
    v12 = (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                          &v50,
                          (const void **)&v51);
    v13 = (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                          &v52,
                          a1);
    v4 = (struct _LUID)CStoredIdentity::CStoredIdentity(v11, v13, v12, (unsigned int)&v49, 0);
  }
  else
  {
    v4 = 0;
  }
  v53 = v4;
  if ( !*(_QWORD *)&v4 )
  {
    v61 = -2147024882;
    goto LABEL_39;
  }
  v49 = v4;
  _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)&v4 + 8LL));
  CStoredIdentityTransaction::CStoredIdentityTransaction(v57, &v49);
  v14 = CStoredIdentityTransaction::Start((CStoredIdentityTransaction *)v57);
  v61 = v14;
  if ( v14 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleGetUserPropertiesFromSystemStore",
      0x23A7u,
      v14,
      "hr = Transaction.Start()");
    goto LABEL_51;
  }
  v15 = *(_DWORD *)(*(_QWORD *)&v4 + 224LL) + 5;
  if ( *(_DWORD *)(*(_QWORD *)&v4 + 224LL) == -5 )
  {
    v61 = -2147418113;
    goto LABEL_48;
  }
  v16 = (struct _WLIDIdentityProperty *)malloc(16LL * v15);
  v17 = v16;
  if ( !v16 )
  {
    v61 = -2147024882;
LABEL_48:
    CStoredIdentityTransaction::~CStoredIdentityTransaction((CStoredIdentityTransaction *)v57);
    goto LABEL_39;
  }
  memset_0(v16, 0, 16LL * v15);
  v5 = v17;
  v54 = v17;
  v6 = v15;
  v55 = v15;
  ATL::CSimpleStringT<unsigned short,0>::SetString(&v47, L"CID");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v50,
    (const void **)(*(_QWORD *)&v4 + 24LL));
  ATL::CSimpleStringT<unsigned short,0>::operator=(&v46, &v50);
  ATL::CStringData::Release((ATL::CStringData *)(v50 - 24));
  *(_QWORD *)(*(_QWORD *)&v4 + 56LL) = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::GetStartPosition(*(_QWORD *)&v4 + 216LL);
  *(_QWORD *)(*(_QWORD *)&v4 + 64LL) = 0;
  *(_DWORD *)(*(_QWORD *)&v4 + 72LL) = 0;
  v61 = 0;
  v18 = 0;
  v19 = 1;
  while ( 1 )
  {
    if ( !v19 )
    {
      v61 = 0;
      CStoredIdentityTransaction::~CStoredIdentityTransaction((CStoredIdentityTransaction *)v57);
      *a2 = v18;
      v5 = 0;
      v6 = 0;
      *a3 = v17;
      goto LABEL_39;
    }
    if ( !*(_DWORD *)(v46 - 16) )
      goto LABEL_36;
    v20 = malloc(2LL * *(int *)(v47 - 16) + 2);
    *((_QWORD *)v17 + 2 * v18) = v20;
    if ( !v20 )
      break;
    v21 = malloc(2LL * *(int *)(v46 - 16) + 2);
    *((_QWORD *)v17 + 2 * v18 + 1) = v21;
    if ( !v21 )
      break;
    v22 = (__int16 *)v47;
    v23 = *(_DWORD *)(v47 - 16);
    v19 = v23 == -1;
    v24 = v23 + 1;
    v25 = v24;
    v26 = (_WORD *)*((_QWORD *)v17 + 2 * v18);
    if ( v19 )
    {
      v30 = -2147024809;
      if ( v24 )
        goto LABEL_57;
    }
    else
    {
      if ( (unsigned __int64)v24 > 0x7FFFFFFF )
      {
        v30 = -2147024809;
LABEL_57:
        *v26 = 0;
        v61 = -2147024809;
LABEL_58:
        v43 = "hr = StringCchCopyW(apIdentityProperty[dwIndex].pszProperty, pszProp.GetLength() + 1, (LPCWSTR)pszProp)";
        v44 = 9159;
        goto LABEL_59;
      }
      v27 = 2147483646;
      do
      {
        if ( !v27 )
          break;
        v28 = *v22;
        if ( !*v22 )
          break;
        ++v22;
        *v26++ = v28;
        --v27;
        --v25;
      }
      while ( v25 );
      v29 = v26 - 1;
      if ( v25 )
        v29 = v26;
      *v29 = 0;
      v30 = v25 == 0 ? 0x8007007A : 0;
    }
    v61 = v30;
    if ( v30 < 0 )
      goto LABEL_58;
    v31 = (__int16 *)v46;
    v32 = *(_DWORD *)(v46 - 16);
    v19 = v32 == -1;
    v33 = v32 + 1;
    v34 = v33;
    v35 = (_WORD *)*((_QWORD *)v17 + 2 * v18 + 1);
    if ( v19 )
    {
      v30 = -2147024809;
      if ( v33 )
        goto LABEL_64;
    }
    else
    {
      if ( (unsigned __int64)v33 > 0x7FFFFFFF )
      {
        v30 = -2147024809;
LABEL_64:
        *v35 = 0;
        v61 = -2147024809;
LABEL_65:
        v43 = "hr = StringCchCopyW(apIdentityProperty[dwIndex].pszValue, pszPropValue.GetLength() + 1, (LPCWSTR)pszPropValue)";
        v44 = 9161;
LABEL_59:
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          "HandleGetUserPropertiesFromSystemStore",
          v44,
          v30,
          v43);
        goto LABEL_51;
      }
      v36 = 2147483646;
      do
      {
        if ( !v36 )
          break;
        v37 = *v31;
        if ( !*v31 )
          break;
        ++v31;
        *v35++ = v37;
        --v36;
        --v34;
      }
      while ( v34 );
      v38 = v35 - 1;
      if ( v34 )
        v38 = v35;
      *v38 = 0;
      v30 = v34 == 0 ? 0x8007007A : 0;
    }
    v61 = v30;
    if ( v30 < 0 )
      goto LABEL_65;
    ++v18;
LABEL_36:
    v39 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))CStoredIdentity::GetNextProperty)(v4, &v47, &v46);
    v61 = v39;
    v19 = v39 == 0;
    if ( v39 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleGetUserPropertiesFromSystemStore",
        0x23CEu,
        v39,
        "hr = pStoredId->GetNextProperty(pszProp, pszPropValue)");
      goto LABEL_51;
    }
  }
  v61 = -2147024882;
LABEL_51:
  CStoredIdentityTransaction::~CStoredIdentityTransaction((CStoredIdentityTransaction *)v57);
LABEL_39:
  v40 = v61;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v58);
  ATL::CStringData::Release((ATL::CStringData *)(v46 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v47 - 24));
  if ( v5 )
    WLIDIdentityPropertyFunctor::operator()(v41, v5, v6);
  ATL::CStringData::Release((ATL::CStringData *)(v51 - 24));
  if ( v4 )
    CRefCounted::Release(*(CRefCounted **)&v4);
  if ( (_DWORD)v48 )
    SetThreadToken(0, 0);
  return v40;
}

```

## disassembly

```asm
0x180010290  mov     rax, rsp
0x180010293  mov     [rax+8], rbx
0x180010297  mov     [rax+18h], r8
0x18001029b  mov     [rax+10h], rdx
0x18001029f  push    rbp
0x1800102a0  push    rsi
0x1800102a1  push    rdi
0x1800102a2  push    r12
0x1800102a4  push    r13
0x1800102a6  push    r14
0x1800102a8  push    r15
0x1800102aa  lea     rbp, [rax-5Fh]
0x1800102ae  sub     rsp, 100h
0x1800102b5  mov     rsi, rcx
0x1800102b8  xor     r15d, r15d
0x1800102bb  mov     [rbp+57h+arg_18], r15d
0x1800102bf  mov     [rsp+130h+var_F0], r15
0x1800102c4  mov     ebx, r15d
0x1800102c7  mov     [rbp+57h+var_C8], rbx
0x1800102cb  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800102d2  lea     rdi, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800102d9  mov     rcx, rdi
0x1800102dc  mov     rax, [rax+18h]
0x1800102e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102e5  add     rax, 18h
0x1800102e9  mov     [rsp+130h+var_D8], rax
0x1800102ee  mov     r12d, r15d
0x1800102f1  mov     [rbp+57h+var_B8], r15
0x1800102f5  mov     [rbp+57h+var_A8], r15
0x1800102f9  mov     r13d, r15d
0x1800102fc  mov     [rbp+57h+var_B0], r15d
0x180010300  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180010307  mov     rcx, rdi
0x18001030a  mov     rax, [rax+18h]
0x18001030e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010313  add     rax, 18h
0x180010317  mov     [rsp+130h+var_F8], rax
0x18001031c  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180010323  mov     rcx, rdi
0x180010326  mov     rax, [rax+18h]
0x18001032a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001032f  add     rax, 18h
0x180010333  mov     [rsp+130h+var_100], rax
0x180010338  mov     qword ptr [rsp+130h+var_E8.LowPart], r15
0x18001033d  lea     r14, aHandlegetuserp; "HandleGetUserPropertiesFromSystemStore"
0x180010344  mov     [rbp+57h+var_60], r14
0x180010348  lea     rax, [rbp+57h+arg_18]
0x18001034c  mov     [rbp+57h+var_58], rax
0x180010350  mov     [rbp+57h+var_50], r15
0x180010354  mov     [rbp+57h+var_48], r15
0x180010358  xor     r9d, r9d; unsigned int
0x18001035b  mov     r8d, 2399h; char *
0x180010361  mov     rdx, r14; char *
0x180010364  lea     rdi, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18001036b  mov     rcx, rdi; this
0x18001036e  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180010373  nop
0x180010374  xor     edx, edx; struct ATL::CAccessToken *
0x180010376  lea     rcx, [rsp+130h+var_F0]; this
0x18001037b  call    ?ImpersonateClient@CAutoImpersonateClient@@QEAAJPEAVCAccessToken@ATL@@@Z; CAutoImpersonateClient::ImpersonateClient(ATL::CAccessToken *)
0x180010380  mov     [rbp+57h+arg_18], eax
0x180010383  test    eax, eax
0x180010385  js      loc_180010769
0x18001038b  lea     rdx, [rsp+130h+var_D8]
0x180010390  lea     rcx, [rsp+130h+var_F0]; this
0x180010395  call    ?GetTokenUser@CAutoImpersonateClient@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CAutoImpersonateClient::GetTokenUser(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18001039a  mov     [rbp+57h+arg_18], eax
0x18001039d  test    eax, eax
0x18001039f  js      loc_1800107C1
0x1800103a5  lea     rdx, [rsp+130h+var_E8]; struct _LUID *
0x1800103aa  lea     rcx, [rsp+130h+var_F0]; this
0x1800103af  call    ?GetLogonId@CAutoImpersonateClient@@QEAAJAEAU_LUID@@@Z; CAutoImpersonateClient::GetLogonId(_LUID &)
0x1800103b4  mov     [rbp+57h+arg_18], eax
0x1800103b7  test    eax, eax
0x1800103b9  js      loc_1800107D5
0x1800103bf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800103c6  mov     ecx, 120h; unsigned __int64
0x1800103cb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800103d0  mov     rdi, rax
0x1800103d3  mov     [rbp+57h+var_40], rax
0x1800103d7  test    rax, rax
0x1800103da  jz      loc_180010749
0x1800103e0  lea     rax, [rsp+130h+var_E0]
0x1800103e5  mov     [rbp+57h+var_38], rax
0x1800103e9  lea     rdx, [rsp+130h+var_D8]
0x1800103ee  lea     rcx, [rsp+130h+var_E0]
0x1800103f3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800103f8  mov     rbx, rax
0x1800103fb  mov     rdx, rsi
0x1800103fe  lea     rcx, [rbp+57h+var_D0]
0x180010402  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180010407  nop
0x180010408  mov     [rsp+20h], r15d
0x18001040d  lea     r9, [rsp+130h+var_E8]
0x180010412  mov     r8, rbx
0x180010415  mov     rdx, rax
0x180010418  mov     rcx, rdi
0x18001041b  call    ??0CStoredIdentity@@QEAA@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0AEAU_LUID@@H@Z; CStoredIdentity::CStoredIdentity(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,_LUID &,int)
0x180010420  mov     rbx, rax
0x180010423  mov     [rbp+57h+var_C8], rbx
0x180010427  test    rbx, rbx
0x18001042a  jz      loc_1800107E9
0x180010430  mov     qword ptr [rsp+130h+var_E8.LowPart], rbx
0x180010435  lock inc dword ptr [rbx+8]
0x180010439  lea     rdx, [rsp+130h+var_E8]
0x18001043e  lea     rcx, [rbp+57h+var_A0]
0x180010442  call    ??0CStoredIdentityTransaction@@QEAA@V?$CAutoRefPtr@VCStoredIdentity@@@@@Z; CStoredIdentityTransaction::CStoredIdentityTransaction(CAutoRefPtr<CStoredIdentity>)
0x180010447  nop
0x180010448  lea     rcx, [rbp+57h+var_A0]; this
0x18001044c  call    ?Start@CStoredIdentityTransaction@@QEAAJXZ; CStoredIdentityTransaction::Start(void)
0x180010451  mov     [rbp+57h+arg_18], eax
0x180010454  test    eax, eax
0x180010456  js      loc_18001078E
0x18001045c  lea     r15, [rbx+0D8h]
0x180010463  mov     r14d, [r15+8]
0x180010467  add     r14d, 5
0x18001046b  jz      loc_1800107F5
0x180010471  mov     esi, r14d
0x180010474  shl     rsi, 4
0x180010478  mov     rcx, rsi; Size
0x18001047b  call    cs:__imp_malloc
0x180010481  mov     rdi, rax
0x180010484  test    rax, rax
0x180010487  jz      loc_180010751
0x18001048d  mov     r8, rsi; Size
0x180010490  xor     edx, edx; Val
0x180010492  mov     rcx, rax; void *
0x180010495  call    memset_0
0x18001049a  mov     r12, rdi
0x18001049d  mov     [rbp+57h+var_B8], rdi
0x1800104a1  mov     r13d, r14d
0x1800104a4  mov     [rbp+57h+var_B0], r14d
0x1800104a8  lea     rdx, aCid; "CID"
0x1800104af  lea     rcx, [rsp+130h+var_F8]
0x1800104b4  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1800104b9  lea     rdx, [rbx+18h]
0x1800104bd  lea     rcx, [rsp+130h+var_E0]
0x1800104c2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800104c7  nop
0x1800104c8  lea     rdx, [rsp+130h+var_E0]
0x1800104cd  lea     rcx, [rsp+130h+var_100]
0x1800104d2  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1800104d7  nop
0x1800104d8  mov     rcx, [rsp+130h+var_E0]
0x1800104dd  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800104e1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800104e6  mov     rcx, r15
0x1800104e9  call    ?GetStartPosition@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::GetStartPosition(void)
0x1800104ee  mov     [rbx+38h], rax
0x1800104f2  xor     r15d, r15d
0x1800104f5  mov     [rbx+40h], r15
0x1800104f9  mov     [rbx+48h], r15d
0x1800104fd  mov     [rbp+57h+arg_18], r15d
0x180010501  mov     r14d, r15d
0x180010504  mov     eax, r15d
0x180010507  test    eax, eax
0x180010509  jnz     loc_1800106A9
0x18001050f  mov     rax, [rsp+130h+var_100]
0x180010514  cmp     [rax-10h], r15d
0x180010518  jz      loc_18001066B
0x18001051e  mov     rax, [rsp+130h+var_F8]
0x180010523  movsxd  rcx, dword ptr [rax-10h]
0x180010527  lea     rcx, ds:2[rcx*2]; Size
0x18001052f  call    cs:__imp_malloc
0x180010535  mov     esi, r14d
0x180010538  add     rsi, rsi
0x18001053b  mov     [rdi+rsi*8], rax
0x18001053f  test    rax, rax
0x180010542  jz      loc_180010862
0x180010548  mov     rax, [rsp+130h+var_100]
0x18001054d  movsxd  rcx, dword ptr [rax-10h]
0x180010551  lea     rcx, ds:2[rcx*2]; Size
0x180010559  call    cs:__imp_malloc
0x18001055f  mov     [rdi+rsi*8+8], rax
0x180010564  test    rax, rax
0x180010567  jz      loc_180010862
0x18001056d  mov     rcx, [rsp+130h+var_F8]
0x180010572  mov     eax, [rcx-10h]
0x180010575  add     eax, 1
0x180010578  movsxd  rdx, eax
0x18001057b  mov     r8, [rdi+rsi*8]
0x18001057f  jz      loc_180010801
0x180010585  cmp     rdx, 7FFFFFFFh
0x18001058c  ja      loc_18001083D
0x180010592  mov     eax, 7FFFFFFEh
0x180010597  test    rax, rax
0x18001059a  jz      short loc_1800105BB
0x18001059c  movzx   r9d, word ptr [rcx]
0x1800105a0  test    r9w, r9w
0x1800105a4  jz      short loc_1800105BB
0x1800105a6  add     rcx, 2
0x1800105aa  mov     [r8], r9w
0x1800105ae  add     r8, 2
0x1800105b2  dec     rax
0x1800105b5  sub     rdx, 1
0x1800105b9  jnz     short loc_180010597
0x1800105bb  lea     rcx, [r8-2]
0x1800105bf  test    rdx, rdx
0x1800105c2  cmovnz  rcx, r8
0x1800105c6  mov     [rcx], r15w
0x1800105ca  neg     rdx
0x1800105cd  sbb     r9d, r9d
0x1800105d0  not     r9d
0x1800105d3  and     r9d, 8007007Ah
0x1800105da  mov     r10d, 80070057h
0x1800105e0  mov     [rbp+57h+arg_18], r9d
0x1800105e4  test    r9d, r9d
0x1800105e7  js      loc_18001081A
0x1800105ed  mov     rcx, [rsp+130h+var_100]
0x1800105f2  mov     eax, [rcx-10h]
0x1800105f5  add     eax, 1
0x1800105f8  movsxd  rdx, eax
0x1800105fb  mov     r8, [rdi+rsi*8+8]
0x180010600  jz      loc_180010831
0x180010606  cmp     rdx, 7FFFFFFFh
0x18001060d  ja      loc_180010848
0x180010613  mov     eax, 7FFFFFFEh
0x180010618  test    rax, rax
0x18001061b  jz      short loc_18001063C
0x18001061d  movzx   r9d, word ptr [rcx]
0x180010621  test    r9w, r9w
0x180010625  jz      short loc_18001063C
0x180010627  add     rcx, 2
0x18001062b  mov     [r8], r9w
0x18001062f  add     r8, 2
0x180010633  dec     rax
0x180010636  sub     rdx, 1
0x18001063a  jnz     short loc_180010618
0x18001063c  lea     rcx, [r8-2]
0x180010640  test    rdx, rdx
0x180010643  cmovnz  rcx, r8
0x180010647  mov     [rcx], r15w
0x18001064b  neg     rdx
0x18001064e  sbb     r9d, r9d
0x180010651  not     r9d
0x180010654  and     r9d, 8007007Ah
0x18001065b  mov     [rbp+57h+arg_18], r9d
0x18001065f  test    r9d, r9d
0x180010662  js      loc_180010853
0x180010668  inc     r14d
0x18001066b  lea     r8, [rsp+130h+var_100]
0x180010670  lea     rdx, [rsp+130h+var_F8]
0x180010675  mov     rcx, rbx
0x180010678  call    ?GetNextProperty@CStoredIdentity@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; CStoredIdentity::GetNextProperty(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18001067d  mov     [rbp+57h+arg_18], eax
0x180010680  test    eax, eax
0x180010682  jns     loc_180010509
0x180010688  lea     rcx, aHrPstoredidGet; "hr = pStoredId->GetNextProperty(pszProp"...
0x18001068f  mov     [rsp+20h], rcx
0x180010694  mov     r9d, eax
0x180010697  mov     r8d, 23CEh
0x18001069d  lea     rdx, aHandlegetuserp; "HandleGetUserPropertiesFromSystemStore"
0x1800106a4  jmp     loc_1800107A6
0x1800106a9  mov     [rbp+57h+arg_18], r15d
0x1800106ad  lea     rcx, [rbp+57h+var_A0]; this
0x1800106b1  call    ??1CStoredIdentityTransaction@@QEAA@XZ; CStoredIdentityTransaction::~CStoredIdentityTransaction(void)
0x1800106b6  mov     rax, [rbp+57h+arg_8]
0x1800106ba  mov     [rax], r14d
0x1800106bd  mov     r12, r15
0x1800106c0  mov     r13d, r15d
0x1800106c3  mov     rax, [rbp+57h+arg_10]
0x1800106c7  mov     [rax], rdi
0x1800106ca  mov     edi, [rbp+57h+arg_18]
0x1800106cd  lea     rcx, [rbp+57h+var_60]
0x1800106d1  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800106d6  nop
0x1800106d7  mov     rcx, [rsp+130h+var_100]
0x1800106dc  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800106e0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800106e5  nop
0x1800106e6  mov     rcx, [rsp+130h+var_F8]
0x1800106eb  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800106ef  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800106f4  nop
0x1800106f5  test    r12, r12
0x1800106f8  jnz     loc_18001086E
0x1800106fe  mov     rcx, [rsp+130h+var_D8]
0x180010703  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180010707  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001070c  nop
0x18001070d  test    rbx, rbx
0x180010710  jz      short loc_18001071B
0x180010712  mov     rcx, rbx; this
0x180010715  call    ?Release@CRefCounted@@QEAAXXZ; CRefCounted::Release(void)
0x18001071a  nop
0x18001071b  cmp     dword ptr [rsp+130h+var_F0], r15d
0x180010720  jz      short loc_18001072C
0x180010722  xor     edx, edx; Token
0x180010724  xor     ecx, ecx; Thread
0x180010726  call    cs:__imp_SetThreadToken
0x18001072c  mov     eax, edi
0x18001072e  mov     rbx, [rsp+130h+arg_0]
0x180010736  add     rsp, 100h
0x18001073d  pop     r15
0x18001073f  pop     r14
0x180010741  pop     r13
0x180010743  pop     r12
0x180010745  pop     rdi
0x180010746  pop     rsi
0x180010747  pop     rbp
  ... truncated ...
```
