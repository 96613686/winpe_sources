# SetUserPropertiesToSystemStore(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x18003e73c`
- end: `0x18003eb4c`
- name: `?SetUserPropertiesToSystemStore@@YAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V32@@2@AEBV12@@Z`
- size: `1040`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800efc0c`

## callees

- `0x18000c050`
- `0x18000e8dc`
- `0x18000ed3c`
- `0x1800133c8`
- `0x180014824`
- `0x1800151c4`
- `0x180015fb0`
- `0x180018f80`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001dfec`
- `0x18001f968`
- `0x180020b10`
- `0x18003e73c`
- `0x18003eb54`
- `0x18003ec18`
- `0x1800801dc`
- `0x180081cac`
- `0x180084e88`
- `0x1800a716c`
- `0x180128010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003e8e3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003e8e3`
- `ntdll!RtlAcquireResourceShared` at `0x18003e823`
- `ntdll!RtlAcquireResourceShared` at `0x18003e823`
- `ntdll!RtlReleaseResource` at `0x18003e896`
- `ntdll!RtlReleaseResource` at `0x18003e896`

## string_xrefs

- `0x18003e7ff`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\tokenbag.cpp`
- `0x18003e883`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\tokenbag.cpp`
- `0x18003eaf0`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\tokenbag.cpp`
- `0x18003eb2c`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\tokenbag.cpp`
- `0x18003ea80`: `hr = client.ImpersonateClient()`
- `0x18003eab1`: `hr = client.GetTokenUser(pszSid)`
- `0x18003eb10`: `hr = Transaction.Commit()`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SetUserPropertiesToSystemStore(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v5; // r12
  volatile signed __int32 *v6; // rbx
  unsigned __int16 *v7; // rdi
  unsigned __int16 *v8; // rsi
  struct _RTL_RESOURCE *v9; // r14
  int v10; // eax
  int LogonId; // eax
  unsigned int v12; // r15d
  void *v14; // r15
  int v15; // ebx
  int v16; // eax
  int v17; // eax
  __int64 i; // r15
  __int64 v19; // r12
  __int64 v20; // rdx
  int v21; // eax
  int TokenUser; // eax
  const char *v23; // rcx
  unsigned int v24; // r8d
  char *v25; // [rsp+20h] [rbp-A9h]
  __int64 v26; // [rsp+30h] [rbp-99h] BYREF
  struct _LUID v27; // [rsp+38h] [rbp-91h] BYREF
  __int64 v28; // [rsp+40h] [rbp-89h] BYREF
  unsigned __int16 *v29; // [rsp+48h] [rbp-81h] BYREF
  unsigned __int16 *v30; // [rsp+50h] [rbp-79h] BYREF
  _BYTE v31[8]; // [rsp+58h] [rbp-71h] BYREF
  _BYTE v32[8]; // [rsp+60h] [rbp-69h] BYREF
  volatile signed __int32 *v33; // [rsp+68h] [rbp-61h]
  _QWORD v34[7]; // [rsp+78h] [rbp-51h] BYREF
  _BYTE v35[112]; // [rsp+B0h] [rbp-19h] BYREF
  int v37; // [rsp+148h] [rbp+7Fh] BYREF

  v5 = a1;
  v37 = 0;
  v26 = 0;
  v6 = 0;
  v33 = 0;
  v28 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v27 = 0;
  v7 = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v30 = v7;
  v8 = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v29 = v8;
  v34[0] = "SetUserPropertiesToSystemStore";
  v34[1] = &v37;
  v34[2] = 0;
  v34[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\tokenbag.cpp",
    "SetUserPropertiesToSystemStore",
    (const char *)0x1F5,
    0,
    (const unsigned __int16 *)v25);
  v9 = (struct _RTL_RESOURCE *)((char *)g_pPPCRL + 2136);
  v34[4] = (char *)g_pPPCRL + 2136;
  RtlAcquireResourceShared((PRTL_RESOURCE)((char *)g_pPPCRL + 2136), 1u);
  v10 = CAutoImpersonateClient::ImpersonateClient((CAutoImpersonateClient *)&v26, 0);
  v37 = v10;
  if ( v10 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\tokenbag.cpp",
      "SetUserPropertiesToSystemStore",
      0x1F8u,
      v10,
      "hr = client.ImpersonateClient()");
    goto LABEL_5;
  }
  if ( *(_DWORD *)(*a3 - 16LL) )
  {
    ATL::CSimpleStringT<unsigned short,0>::operator=(&v28, a3);
  }
  else
  {
    LogonId = CAutoImpersonateClient::GetLogonId((CAutoImpersonateClient *)&v26, &v27);
    v37 = LogonId;
    if ( LogonId < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\tokenbag.cpp",
        "SetUserPropertiesToSystemStore",
        0x203u,
        LogonId,
        "hr = client.GetLogonId(logonId)");
      goto LABEL_5;
    }
    TokenUser = CAutoImpersonateClient::GetTokenUser((CAutoImpersonateClient *)&v26, &v28);
    v37 = TokenUser;
    if ( TokenUser < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\tokenbag.cpp",
        "SetUserPropertiesToSystemStore",
        0x204u,
        TokenUser,
        "hr = client.GetTokenUser(pszSid)");
      goto LABEL_5;
    }
  }
  v14 = operator new(0x120u, (const struct std::nothrow_t *)std::nothrow);
  v34[5] = v14;
  if ( v14 )
  {
    v34[6] = v31;
    v15 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            v31,
            &v28);
    v16 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            v32,
            v5);
    v6 = (volatile signed __int32 *)CStoredIdentity::CStoredIdentity((_DWORD)v14, v16, v15, (unsigned int)&v27, 0);
  }
  else
  {
    v6 = 0;
  }
  v33 = v6;
  if ( !v6 )
  {
    v37 = -2147024882;
    goto LABEL_5;
  }
  v27 = (struct _LUID)v6;
  _InterlockedIncrement(v6 + 2);
  CStoredIdentityTransaction::CStoredIdentityTransaction(v35, &v27);
  v17 = CStoredIdentityTransaction::Start((CStoredIdentityTransaction *)v35);
  v37 = v17;
  if ( v17 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\tokenbag.cpp",
      "SetUserPropertiesToSystemStore",
      0x20Cu,
      v17,
      "hr = Transaction.Start()");
    goto LABEL_26;
  }
  if ( !(*(unsigned int (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 24LL))(v6) )
  {
LABEL_26:
    CStoredIdentityTransaction::~CStoredIdentityTransaction((CStoredIdentityTransaction *)v35);
    goto LABEL_5;
  }
  for ( i = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::GetStartPosition(a2);
        i;
        i = v19 )
  {
    v19 = *(_QWORD *)(i + 16);
    if ( !v19 )
    {
      LODWORD(v20) = *(_DWORD *)(i + 24) % *(_DWORD *)(a2 + 16);
      do
      {
        v20 = (unsigned int)(v20 + 1);
        v19 = 0;
        if ( (unsigned int)v20 >= *(_DWORD *)(a2 + 16) )
          break;
        v19 = *(_QWORD *)(*(_QWORD *)a2 + 8 * v20);
      }
      while ( !v19 );
    }
    ATL::CSimpleStringT<unsigned short,0>::operator=(&v30, i);
    ATL::CSimpleStringT<unsigned short,0>::operator=(&v29, i + 8);
    v8 = v29;
    v7 = v30;
    v21 = CStoredIdentity::SetProperty((CStoredIdentity *)v6, v30, v29);
    v37 = v21;
    if ( v21 < 0 )
    {
      v23 = "hr = pStoredId->SetProperty(propertyName, propertyValue)";
      v24 = 532;
      goto LABEL_35;
    }
  }
  v21 = CStoredIdentityTransaction::Commit((CStoredIdentityTransaction *)v35, 0, 0);
  v37 = v21;
  if ( v21 >= 0 )
  {
    v5 = a1;
    goto LABEL_26;
  }
  v23 = "hr = Transaction.Commit()";
  v24 = 535;
LABEL_35:
  Telemetry::IfFailExit(
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\tokenbag.cpp",
    "SetUserPropertiesToSystemStore",
    v24,
    v21,
    v23);
  CStoredIdentityTransaction::~CStoredIdentityTransaction((CStoredIdentityTransaction *)v35);
  v5 = a1;
LABEL_5:
  v12 = v37;
  RtlReleaseResource(v9);
  CTraceFuncW<long>::~CTraceFuncW<long>(v34);
  ATL::CStringData::Release((ATL::CStringData *)(v8 - 12));
  ATL::CStringData::Release((ATL::CStringData *)(v7 - 12));
  ATL::CStringData::Release((ATL::CStringData *)(v28 - 24));
  if ( v6 )
    CRefCounted::Release((CRefCounted *)v6);
  if ( (_DWORD)v26 )
    SetThreadToken(0, 0);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v5);
  return v12;
}

```

## disassembly

```asm
0x18003e73c  mov     [rsp-8+arg_8], rbx
0x18003e741  mov     [rsp-8+arg_0], rcx
0x18003e746  push    rbp
0x18003e747  push    rsi
0x18003e748  push    rdi
0x18003e749  push    r12
0x18003e74b  push    r13
0x18003e74d  push    r14
0x18003e74f  push    r15
0x18003e751  lea     rbp, [rsp-27h]
0x18003e756  sub     rsp, 0F0h
0x18003e75d  mov     r15, r8
0x18003e760  mov     r13, rdx
0x18003e763  mov     r12, rcx
0x18003e766  xor     r14d, r14d
0x18003e769  mov     [rbp+57h+arg_18], r14d
0x18003e76d  mov     [rsp+120h+var_F0], r14
0x18003e772  mov     ebx, r14d
0x18003e775  mov     [rbp+57h+var_B8], rbx
0x18003e779  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18003e780  lea     rsi, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18003e787  mov     rcx, rsi
0x18003e78a  mov     rax, [rax+18h]
0x18003e78e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e793  add     rax, 18h
0x18003e797  mov     [rsp+120h+var_E0], rax
0x18003e79c  mov     qword ptr [rsp+120h+var_E8.LowPart], r14
0x18003e7a1  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18003e7a8  mov     rcx, rsi
0x18003e7ab  mov     rax, [rax+18h]
0x18003e7af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e7b4  lea     rdi, [rax+18h]
0x18003e7b8  mov     [rbp+57h+var_D0], rdi
0x18003e7bc  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18003e7c3  mov     rcx, rsi
0x18003e7c6  mov     rax, [rax+18h]
0x18003e7ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e7cf  lea     rsi, [rax+18h]
0x18003e7d3  mov     [rsp+120h+var_D8], rsi
0x18003e7d8  lea     rcx, aSetuserpropert; "SetUserPropertiesToSystemStore"
0x18003e7df  mov     [rbp+57h+var_A8], rcx
0x18003e7e3  lea     rax, [rbp+57h+arg_18]
0x18003e7e7  mov     [rbp+57h+var_A0], rax
0x18003e7eb  mov     [rbp+57h+var_98], r14
0x18003e7ef  mov     [rbp+57h+var_90], r14
0x18003e7f3  xor     r9d, r9d; unsigned int
0x18003e7f6  mov     r8d, 1F5h; char *
0x18003e7fc  mov     rdx, rcx; char *
0x18003e7ff  lea     rcx, aOnecoreuapDsEx_2; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18003e806  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18003e80b  nop
0x18003e80c  mov     r14, cs:?g_pPPCRL@@3PEAVCPassportClientLibrary@@EA; CPassportClientLibrary * g_pPPCRL
0x18003e813  add     r14, 858h
0x18003e81a  mov     [rbp+57h+var_88], r14
0x18003e81e  mov     dl, 1; Wait
0x18003e820  mov     rcx, r14; Resource
0x18003e823  call    cs:__imp_RtlAcquireResourceShared
0x18003e829  nop
0x18003e82a  xor     edx, edx; struct ATL::CAccessToken *
0x18003e82c  lea     rcx, [rsp+120h+var_F0]; this
0x18003e831  call    ?ImpersonateClient@CAutoImpersonateClient@@QEAAJPEAVCAccessToken@ATL@@@Z; CAutoImpersonateClient::ImpersonateClient(ATL::CAccessToken *)
0x18003e836  mov     [rbp+57h+arg_18], eax
0x18003e839  test    eax, eax
0x18003e83b  js      loc_18003EA80
0x18003e841  mov     rax, [r15]
0x18003e844  cmp     [rax-10h], ebx
0x18003e847  jnz     loc_18003E910
0x18003e84d  lea     rdx, [rsp+120h+var_E8]; struct _LUID *
0x18003e852  lea     rcx, [rsp+120h+var_F0]; this
0x18003e857  call    ?GetLogonId@CAutoImpersonateClient@@QEAAJAEAU_LUID@@@Z; CAutoImpersonateClient::GetLogonId(_LUID &)
0x18003e85c  mov     [rbp+57h+arg_18], eax
0x18003e85f  test    eax, eax
0x18003e861  jns     loc_18003EA97
0x18003e867  lea     rcx, aHrClientGetlog; "hr = client.GetLogonId(logonId)"
0x18003e86e  mov     [rsp+120h+var_100], rcx; char *
0x18003e873  mov     r8d, 203h; unsigned int
0x18003e879  mov     r9d, eax; int
0x18003e87c  lea     rdx, aSetuserpropert; "SetUserPropertiesToSystemStore"
0x18003e883  lea     rcx, aOnecoreuapDsEx_2; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18003e88a  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18003e88f  mov     r15d, [rbp+57h+arg_18]
0x18003e893  mov     rcx, r14; Resource
0x18003e896  call    cs:__imp_RtlReleaseResource
0x18003e89c  nop
0x18003e89d  lea     rcx, [rbp+57h+var_A8]
0x18003e8a1  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18003e8a6  nop
0x18003e8a7  lea     rcx, [rsi-18h]; this
0x18003e8ab  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003e8b0  nop
0x18003e8b1  lea     rcx, [rdi-18h]; this
0x18003e8b5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003e8ba  nop
0x18003e8bb  mov     rcx, [rsp+120h+var_E0]
0x18003e8c0  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18003e8c4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003e8c9  nop
0x18003e8ca  test    rbx, rbx
0x18003e8cd  jz      short loc_18003E8D8
0x18003e8cf  mov     rcx, rbx; this
0x18003e8d2  call    ?Release@CRefCounted@@QEAAXXZ; CRefCounted::Release(void)
0x18003e8d7  nop
0x18003e8d8  cmp     dword ptr [rsp+120h+var_F0], 0
0x18003e8dd  jz      short loc_18003E8EA
0x18003e8df  xor     edx, edx; Token
0x18003e8e1  xor     ecx, ecx; Thread
0x18003e8e3  call    cs:__imp_SetThreadToken
0x18003e8e9  nop
0x18003e8ea  mov     rcx, r12
0x18003e8ed  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003e8f2  mov     eax, r15d
0x18003e8f5  mov     rbx, [rsp+120h+arg_8]
0x18003e8fd  add     rsp, 0F0h
0x18003e904  pop     r15
0x18003e906  pop     r14
0x18003e908  pop     r13
0x18003e90a  pop     r12
0x18003e90c  pop     rdi
0x18003e90d  pop     rsi
0x18003e90e  pop     rbp
0x18003e90f  retn
0x18003e910  mov     rdx, r15
0x18003e913  lea     rcx, [rsp+120h+var_E0]
0x18003e918  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x18003e91d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003e924  mov     ecx, 120h; unsigned __int64
0x18003e929  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003e92e  mov     r15, rax
0x18003e931  mov     [rbp+57h+var_80], rax
0x18003e935  test    rax, rax
0x18003e938  jz      loc_18003EA79
0x18003e93e  lea     rax, [rbp+57h+var_C8]
0x18003e942  mov     [rbp+57h+var_78], rax
0x18003e946  lea     rdx, [rsp+120h+var_E0]
0x18003e94b  lea     rcx, [rbp+57h+var_C8]
0x18003e94f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18003e954  mov     rbx, rax
0x18003e957  mov     rdx, r12
0x18003e95a  lea     rcx, [rbp+57h+var_C0]
0x18003e95e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18003e963  nop
0x18003e964  mov     dword ptr [rsp+120h+var_100], 0
0x18003e96c  lea     r9, [rsp+120h+var_E8]
0x18003e971  mov     r8, rbx
0x18003e974  mov     rdx, rax
0x18003e977  mov     rcx, r15
0x18003e97a  call    ??0CStoredIdentity@@QEAA@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0AEAU_LUID@@H@Z; CStoredIdentity::CStoredIdentity(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,_LUID &,int)
0x18003e97f  mov     rbx, rax
0x18003e982  mov     [rbp+57h+var_B8], rbx
0x18003e986  test    rbx, rbx
0x18003e989  jz      loc_18003EAC8
0x18003e98f  mov     qword ptr [rsp+120h+var_E8.LowPart], rbx
0x18003e994  lock inc dword ptr [rbx+8]
0x18003e998  lea     rdx, [rsp+120h+var_E8]
0x18003e99d  lea     rcx, [rbp+57h+var_70]
0x18003e9a1  call    ??0CStoredIdentityTransaction@@QEAA@V?$CAutoRefPtr@VCStoredIdentity@@@@@Z; CStoredIdentityTransaction::CStoredIdentityTransaction(CAutoRefPtr<CStoredIdentity>)
0x18003e9a6  nop
0x18003e9a7  lea     rcx, [rbp+57h+var_70]; this
0x18003e9ab  call    ?Start@CStoredIdentityTransaction@@QEAAJXZ; CStoredIdentityTransaction::Start(void)
0x18003e9b0  mov     [rbp+57h+arg_18], eax
0x18003e9b3  test    eax, eax
0x18003e9b5  js      loc_18003EAD4
0x18003e9bb  mov     rax, [rbx]
0x18003e9be  mov     rcx, rbx
0x18003e9c1  mov     rax, [rax+18h]
0x18003e9c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e9ca  test    eax, eax
0x18003e9cc  jz      loc_18003EA6B
0x18003e9d2  mov     rcx, r13
0x18003e9d5  call    ?GetStartPosition@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::GetStartPosition(void)
0x18003e9da  mov     r15, rax
0x18003e9dd  test    r15, r15
0x18003e9e0  jz      short loc_18003EA4E
0x18003e9e2  mov     r12, [r15+10h]
0x18003e9e6  test    r12, r12
0x18003e9e9  jnz     short loc_18003EA0D
0x18003e9eb  xor     edx, edx
0x18003e9ed  mov     eax, [r15+18h]
0x18003e9f1  div     dword ptr [r13+10h]
0x18003e9f5  inc     edx
0x18003e9f7  xor     r12d, r12d
0x18003e9fa  cmp     edx, [r13+10h]
0x18003e9fe  jnb     short loc_18003EA0D
0x18003ea00  mov     rax, [r13+0]
0x18003ea04  mov     r12, [rax+rdx*8]
0x18003ea08  test    r12, r12
0x18003ea0b  jz      short loc_18003E9F5
0x18003ea0d  mov     rdx, r15
0x18003ea10  lea     rcx, [rbp+57h+var_D0]
0x18003ea14  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x18003ea19  lea     rdx, [r15+8]
0x18003ea1d  lea     rcx, [rsp+120h+var_D8]
0x18003ea22  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x18003ea27  mov     rsi, [rsp+120h+var_D8]
0x18003ea2c  mov     r8, rsi; unsigned __int16 *
0x18003ea2f  mov     rdi, [rbp+57h+var_D0]
0x18003ea33  mov     rdx, rdi; unsigned __int16 *
0x18003ea36  mov     rcx, rbx; this
0x18003ea39  call    ?SetProperty@CStoredIdentity@@QEAAJPEBG0@Z; CStoredIdentity::SetProperty(ushort const *,ushort const *)
0x18003ea3e  mov     [rbp+57h+arg_18], eax
0x18003ea41  test    eax, eax
0x18003ea43  js      loc_18003EB01
0x18003ea49  mov     r15, r12
0x18003ea4c  jmp     short loc_18003E9DD
0x18003ea4e  xor     r8d, r8d; bool
0x18003ea51  xor     edx, edx; void *
0x18003ea53  lea     rcx, [rbp+57h+var_70]; this
0x18003ea57  call    ?Commit@CStoredIdentityTransaction@@QEAAJPEAX_N@Z; CStoredIdentityTransaction::Commit(void *,bool)
0x18003ea5c  mov     [rbp+57h+arg_18], eax
0x18003ea5f  test    eax, eax
0x18003ea61  js      loc_18003EB10
0x18003ea67  mov     r12, [rbp+57h+arg_0]
0x18003ea6b  lea     rcx, [rbp+57h+var_70]; this
0x18003ea6f  call    ??1CStoredIdentityTransaction@@QEAA@XZ; CStoredIdentityTransaction::~CStoredIdentityTransaction(void)
0x18003ea74  jmp     loc_18003E88F
0x18003ea79  xor     ebx, ebx
0x18003ea7b  jmp     loc_18003E982
0x18003ea80  lea     r8, aHrClientImpers_1; "hr = client.ImpersonateClient()"
0x18003ea87  mov     [rsp+120h+var_100], r8
0x18003ea8c  mov     r8d, 1F8h
0x18003ea92  jmp     loc_18003E879
0x18003ea97  lea     rdx, [rsp+120h+var_E0]
0x18003ea9c  lea     rcx, [rsp+120h+var_F0]; this
0x18003eaa1  call    ?GetTokenUser@CAutoImpersonateClient@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CAutoImpersonateClient::GetTokenUser(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18003eaa6  mov     [rbp+57h+arg_18], eax
0x18003eaa9  test    eax, eax
0x18003eaab  jns     loc_18003E91D
0x18003eab1  lea     rcx, aHrClientGettok_1; "hr = client.GetTokenUser(pszSid)"
0x18003eab8  mov     [rsp+120h+var_100], rcx
0x18003eabd  mov     r8d, 204h
0x18003eac3  jmp     loc_18003E879
0x18003eac8  mov     [rbp+57h+arg_18], 8007000Eh
0x18003eacf  jmp     loc_18003E88F
0x18003ead4  lea     rcx, aHrTransactionS; "hr = Transaction.Start()"
0x18003eadb  mov     [rsp+120h+var_100], rcx; char *
0x18003eae0  mov     r9d, eax; int
0x18003eae3  mov     r8d, 20Ch; unsigned int
0x18003eae9  lea     rdx, aSetuserpropert; "SetUserPropertiesToSystemStore"
0x18003eaf0  lea     rcx, aOnecoreuapDsEx_2; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18003eaf7  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18003eafc  jmp     loc_18003EA6B
0x18003eb01  lea     rcx, aHrPstoredidSet_3; "hr = pStoredId->SetProperty(propertyNam"...
0x18003eb08  mov     r8d, 214h
0x18003eb0e  jmp     short loc_18003EB1D
0x18003eb10  lea     rcx, aHrTransactionC; "hr = Transaction.Commit()"
0x18003eb17  mov     r8d, 217h; unsigned int
0x18003eb1d  mov     r9d, eax; int
0x18003eb20  mov     [rsp+120h+var_100], rcx; char *
0x18003eb25  lea     rdx, aSetuserpropert; "SetUserPropertiesToSystemStore"
0x18003eb2c  lea     rcx, aOnecoreuapDsEx_2; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18003eb33  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18003eb38  nop
0x18003eb39  lea     rcx, [rbp+57h+var_70]; this
0x18003eb3d  call    ??1CStoredIdentityTransaction@@QEAA@XZ; CStoredIdentityTransaction::~CStoredIdentityTransaction(void)
0x18003eb42  mov     r12, [rbp+57h+arg_0]
0x18003eb46  jmp     loc_18003E88F
```
