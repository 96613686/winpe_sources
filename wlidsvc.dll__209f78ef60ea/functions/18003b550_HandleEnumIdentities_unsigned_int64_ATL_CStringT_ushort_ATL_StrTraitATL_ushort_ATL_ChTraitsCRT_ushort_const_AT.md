# HandleEnumIdentities(unsigned __int64,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ulong *,ushort * * *)

- ea: `0x18003b550`
- end: `0x18003b9ff`
- name: `?HandleEnumIdentities@@YAJ_KAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1PEAKPEAPEAPEAG@Z`
- size: `1199`
- prototype: ``
- caller_count: `5`
- callee_count: `24`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003b3e0`
- `0x1800a3338`
- `0x1800b0604`
- `0x1800b0d34`
- `0x1800b57d4`

## callees

- `0x18000c050`
- `0x18000ed3c`
- `0x180015860`
- `0x180015fb0`
- `0x180018f80`
- `0x180019690`
- `0x18001a530`
- `0x18001a9c0`
- `0x18001d050`
- `0x18001dfec`
- `0x18001f4d0`
- `0x18001f968`
- `0x180020b10`
- `0x180021c10`
- `0x180030120`
- `0x18003b550`
- `0x18003bba4`
- `0x180046d7c`
- `0x18005a66c`
- `0x180091528`
- `0x1800a4778`
- `0x1800bc9a0`
- `0x1800e4980`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003b96f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003b981`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003b96f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003b981`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18003b890`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18003b8de`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18003b890`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18003b8de`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003b9b3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003b9b3`

## string_xrefs

- `0x18003b5a4`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18003b663`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18003b745`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18003b947`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18003b800`: `hr = client.GetTokenUser(pszSid)`
- `0x18003b647`: `hr = client.ImpersonateClient(&ContextToken)`
- `0x18003b7cd`: `hr = GetCachedIdentities(wszCachedCredType, arrMemberNames)`
- `0x18003b86a`: `hr = CSystemStore::EnumIdentities(pszSid, logonId, enumFlags, wszFilterPropertyName, wszFilterPropertyValue, arrMemberNames )`
- `0x18003b92b`: `hr = StringCchCopyW(rgwszMemberNames[i], arrMemberNames[i].GetLength() + 1, (LPCWSTR)arrMemberNames[i])`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall HandleEnumIdentities(int a1, const void **a2, __int64 a3, _DWORD *a4, _QWORD *a5)
{
  unsigned __int64 v9; // rsi
  _QWORD *v10; // r13
  int v11; // eax
  int LogonId; // eax
  int SessionId; // eax
  const wchar_t *v14; // rdx
  int v15; // ebx
  unsigned int v16; // eax
  int SignedInUsernames; // eax
  int CachedIdentities; // eax
  const char *v19; // rcx
  unsigned int v20; // r8d
  int TokenUser; // eax
  int v22; // eax
  _QWORD *v23; // rax
  _QWORD *v24; // rdi
  unsigned __int64 i; // r14
  _QWORD *v26; // rax
  void *v27; // rax
  const unsigned __int16 *v28; // rbx
  _QWORD *v29; // rax
  int v30; // eax
  __int64 j; // rbx
  void *v32; // rcx
  unsigned int v33; // ebx
  char *v35; // [rsp+20h] [rbp-A1h]
  unsigned int v36; // [rsp+40h] [rbp-81h] BYREF
  __int64 v37; // [rsp+48h] [rbp-79h] BYREF
  __int64 v38; // [rsp+50h] [rbp-71h] BYREF
  struct _LUID v39; // [rsp+58h] [rbp-69h] BYREF
  __int64 v40; // [rsp+60h] [rbp-61h] BYREF
  __int64 v41; // [rsp+68h] [rbp-59h] BYREF
  unsigned __int64 v42; // [rsp+70h] [rbp-51h]
  __int64 v43; // [rsp+78h] [rbp-49h]
  int v44; // [rsp+80h] [rbp-41h]
  __int64 v45; // [rsp+88h] [rbp-39h] BYREF
  void **v46; // [rsp+90h] [rbp-31h] BYREF
  __int128 v47; // [rsp+98h] [rbp-29h]
  __int64 v48; // [rsp+A8h] [rbp-19h]
  const char *v49[12]; // [rsp+B0h] [rbp-11h] BYREF
  int v50; // [rsp+128h] [rbp+67h] BYREF

  v50 = 0;
  CTraceFuncW<long>::CTraceFuncW<long>(
    v49,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    5635,
    (const char *)&v50,
    "HandleEnumIdentities",
    L"wszFilterPropertyNAme='%ls'",
    *a2);
  v38 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v41 = 0;
  v9 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v40 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *a4 = 0;
  v10 = a5;
  *a5 = 0;
  v37 = 0;
  v39 = 0;
  v36 = 0;
  v46 = &ATL::CAccessToken::`vftable';
  v47 = 0;
  v48 = 0;
  v11 = CAutoImpersonateClient::ImpersonateClient((CAutoImpersonateClient *)&v37, (struct ATL::CAccessToken *)&v46);
  v50 = v11;
  if ( v11 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleEnumIdentities",
      0x1614u,
      v11,
      "hr = client.ImpersonateClient(&ContextToken)");
    goto LABEL_48;
  }
  LogonId = CAutoImpersonateClient::GetLogonId((CAutoImpersonateClient *)&v37, &v39);
  v50 = LogonId;
  if ( LogonId < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleEnumIdentities",
      0x1615u,
      LogonId,
      "hr = client.GetLogonId(logonId)");
    goto LABEL_48;
  }
  SessionId = CAutoImpersonateClient::GetSessionId((CAutoImpersonateClient *)&v37, &v36);
  v50 = SessionId;
  if ( SessionId < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleEnumIdentities",
      0x1616u,
      SessionId,
      "hr = client.GetSessionId(dwSessionId)");
    goto LABEL_48;
  }
  if ( (a1 & 1) != 0 )
  {
    if ( (a1 & 0x10) != 0 )
    {
      ATL::CSimpleStringT<unsigned short,0>::Empty(&v38);
      goto LABEL_17;
    }
    v14 = L"ps:password";
    goto LABEL_14;
  }
  if ( (a1 & 0x10) != 0 )
  {
    v14 = L"ps:membernameonly";
LABEL_14:
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v38, v14);
    goto LABEL_17;
  }
  if ( (a1 & 0x100) != 0 )
    ATL::CSimpleStringT<unsigned short,0>::operator=(&v38, a2);
LABEL_17:
  if ( (a1 & 0x1000000) != 0 )
  {
    v50 = SignInAssociatedUser(0, v36, &v39, 0);
    LODWORD(v35) = v50;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      0x1634u,
      L"SignInAssociatedUser. (0x%x)",
      v35);
    v15 = (int)g_pPPCRL;
    v16 = (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                          &v45,
                          a2);
    SignedInUsernames = CIdentityStore::GetSignedInUsernames(v15 + 496, (unsigned int)&v39, v36, v16, (__int64)&v41);
    v50 = SignedInUsernames;
    if ( SignedInUsernames < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleEnumIdentities",
        0x1637u,
        SignedInUsernames,
        "hr = g_pPPCRL->GetIdentityStore()->GetSignedInUsernames(logonId, dwSessionId, wszFilterPropertyName, arrMemberNames)");
      goto LABEL_48;
    }
    v9 = v42;
  }
  if ( (a1 & 0x111) != 0 )
  {
    CachedIdentities = GetCachedIdentities(v38, &v41);
    v50 = CachedIdentities;
    if ( CachedIdentities < 0 )
    {
      v19 = "hr = GetCachedIdentities(wszCachedCredType, arrMemberNames)";
      v20 = 5693;
LABEL_31:
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleEnumIdentities",
        v20,
        CachedIdentities,
        v19);
      goto LABEL_48;
    }
  }
  else
  {
    if ( (*(_QWORD *)&a1 & 0x111000LL) == 0 )
      goto LABEL_33;
    TokenUser = CAutoImpersonateClient::GetTokenUser((CAutoImpersonateClient *)&v37, &v40);
    v50 = TokenUser;
    if ( TokenUser < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleEnumIdentities",
        0x1647u,
        TokenUser,
        "hr = client.GetTokenUser(pszSid)");
      goto LABEL_48;
    }
    v22 = CAutoImpersonateClient::GetLogonId((CAutoImpersonateClient *)&v37, &v39);
    v50 = v22;
    if ( v22 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleEnumIdentities",
        0x1648u,
        v22,
        "hr = client.GetLogonId(logonId)");
      goto LABEL_48;
    }
    CachedIdentities = CSystemStore::EnumIdentities(
                         (unsigned int)&v40,
                         (unsigned int)&v39,
                         a1,
                         (_DWORD)a2,
                         a3,
                         (__int64)&v41);
    v50 = CachedIdentities;
    if ( CachedIdentities < 0 )
    {
      v19 = "hr = CSystemStore::EnumIdentities(pszSid, logonId, enumFlags, wszFilterPropertyName, wszFilterPropertyValue,"
            " arrMemberNames )";
      v20 = 5711;
      goto LABEL_31;
    }
  }
  v9 = v42;
LABEL_33:
  v23 = malloc(8 * v9);
  v24 = v23;
  if ( v23 )
  {
    memset_0(v23, 0, 8 * v9);
    for ( i = 0; ; ++i )
    {
      if ( i >= v9 )
      {
        *a4 = v9;
        *v10 = v24;
        goto LABEL_48;
      }
      v26 = (_QWORD *)ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::operator[](
                        &v41,
                        i);
      v27 = malloc(2LL * *(int *)(*v26 - 16LL) + 2);
      v24[i] = v27;
      if ( !v27 )
        break;
      v28 = *(const unsigned __int16 **)ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::operator[](
                                          &v41,
                                          i);
      v29 = (_QWORD *)ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::operator[](
                        &v41,
                        i);
      v30 = StringCchCopyW((unsigned __int16 *)v24[i], *(_DWORD *)(*v29 - 16LL) + 1, v28);
      v50 = v30;
      if ( v30 < 0 )
      {
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          "HandleEnumIdentities",
          0x165Du,
          v30,
          "hr = StringCchCopyW(rgwszMemberNames[i], arrMemberNames[i].GetLength() + 1, (LPCWSTR)arrMemberNames[i])");
        goto LABEL_42;
      }
    }
    v50 = -2147024882;
LABEL_42:
    for ( j = 0; (unsigned int)j < v9; j = (unsigned int)(j + 1) )
    {
      v32 = (void *)v24[j];
      if ( v32 )
        free(v32);
    }
    free(v24);
  }
  else
  {
    v50 = -2147024882;
  }
LABEL_48:
  v33 = v50;
  v46 = &ATL::CAccessToken::`vftable';
  ATL::CAccessToken::Clear((ATL::CAccessToken *)&v46);
  if ( (_DWORD)v37 )
    SetThreadToken(0, 0);
  ATL::CStringData::Release((ATL::CStringData *)(v40 - 24));
  ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>(&v41);
  ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v49);
  return v33;
}

```

## disassembly

```asm
0x18003b550  push    rbp
0x18003b552  push    rbx
0x18003b553  push    rsi
0x18003b554  push    rdi
0x18003b555  push    r12
0x18003b557  push    r13
0x18003b559  push    r14
0x18003b55b  push    r15
0x18003b55d  lea     rbp, [rsp-17h]
0x18003b562  sub     rsp, 0D8h
0x18003b569  mov     r12, r9
0x18003b56c  mov     r15, r8
0x18003b56f  mov     r14, rdx
0x18003b572  mov     rdi, rcx
0x18003b575  xor     ebx, ebx
0x18003b577  mov     [rbp+4Fh+arg_8], ebx
0x18003b57a  mov     rax, [rdx]
0x18003b57d  mov     [rsp+110h+var_E0], rax
0x18003b582  lea     rax, aWszfilterprope; "wszFilterPropertyNAme='%ls'"
0x18003b589  mov     [rsp+110h+var_E8], rax
0x18003b58e  lea     rax, aHandleenumiden; "HandleEnumIdentities"
0x18003b595  mov     [rsp+110h+var_F0], rax
0x18003b59a  lea     r9, [rbp+4Fh+arg_8]
0x18003b59e  mov     r8d, 1603h
0x18003b5a4  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18003b5ab  lea     rcx, [rbp+4Fh+var_60]
0x18003b5af  call    ??0?$CTraceFuncW@J@@QEAA@PEBDKAEAJ0PEBGZZ; CTraceFuncW<long>::CTraceFuncW<long>(char const *,ulong,long &,char const *,ushort const *,...)
0x18003b5b4  nop
0x18003b5b5  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18003b5bc  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18003b5c3  mov     rax, [rax+18h]
0x18003b5c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b5cc  add     rax, 18h
0x18003b5d0  mov     [rbp+4Fh+var_C0], rax
0x18003b5d4  mov     [rbp+4Fh+var_A8], rbx
0x18003b5d8  mov     esi, ebx
0x18003b5da  mov     [rbp+4Fh+var_A0], rbx
0x18003b5de  mov     [rbp+4Fh+var_98], rbx
0x18003b5e2  mov     [rbp+4Fh+var_90], ebx
0x18003b5e5  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18003b5ec  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18003b5f3  mov     rax, [rax+18h]
0x18003b5f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b5fc  add     rax, 18h
0x18003b600  mov     [rbp+4Fh+var_B0], rax
0x18003b604  mov     [r12], ebx
0x18003b608  mov     r13, [rbp+4Fh+arg_20]
0x18003b60c  mov     [r13+0], rbx
0x18003b610  mov     [rbp+4Fh+var_C8], rbx
0x18003b614  mov     qword ptr [rbp+4Fh+var_B8.LowPart], rbx
0x18003b618  mov     [rsp+110h+var_D0], ebx
0x18003b61c  lea     rax, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x18003b623  mov     [rbp+4Fh+var_80], rax
0x18003b627  xorps   xmm0, xmm0
0x18003b62a  movdqu  [rbp+4Fh+var_78], xmm0
0x18003b62f  mov     [rbp+4Fh+var_68], rbx
0x18003b633  lea     rdx, [rbp+4Fh+var_80]; struct ATL::CAccessToken *
0x18003b637  lea     rcx, [rbp+4Fh+var_C8]; this
0x18003b63b  call    ?ImpersonateClient@CAutoImpersonateClient@@QEAAJPEAVCAccessToken@ATL@@@Z; CAutoImpersonateClient::ImpersonateClient(ATL::CAccessToken *)
0x18003b640  mov     [rbp+4Fh+arg_8], eax
0x18003b643  test    eax, eax
0x18003b645  jns     short loc_18003B674
0x18003b647  lea     r8, aHrClientImpers; "hr = client.ImpersonateClient(&ContextT"...
0x18003b64e  mov     [rsp+110h+var_F0], r8; char *
0x18003b653  mov     r8d, 1614h; unsigned int
0x18003b659  mov     r9d, eax; int
0x18003b65c  lea     rdx, aHandleenumiden; "HandleEnumIdentities"
0x18003b663  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18003b66a  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18003b66f  jmp     loc_18003B991
0x18003b674  lea     rdx, [rbp+4Fh+var_B8]; struct _LUID *
0x18003b678  lea     rcx, [rbp+4Fh+var_C8]; this
0x18003b67c  call    ?GetLogonId@CAutoImpersonateClient@@QEAAJAEAU_LUID@@@Z; CAutoImpersonateClient::GetLogonId(_LUID &)
0x18003b681  mov     [rbp+4Fh+arg_8], eax
0x18003b684  test    eax, eax
0x18003b686  jns     short loc_18003B69C
0x18003b688  lea     rcx, aHrClientGetlog; "hr = client.GetLogonId(logonId)"
0x18003b68f  mov     [rsp+110h+var_F0], rcx
0x18003b694  mov     r8d, 1615h
0x18003b69a  jmp     short loc_18003B659
0x18003b69c  lea     rdx, [rsp+110h+var_D0]; unsigned int *
0x18003b6a1  lea     rcx, [rbp+4Fh+var_C8]; this
0x18003b6a5  call    ?GetSessionId@CAutoImpersonateClient@@QEAAJAEAK@Z; CAutoImpersonateClient::GetSessionId(ulong &)
0x18003b6aa  mov     [rbp+4Fh+arg_8], eax
0x18003b6ad  test    eax, eax
0x18003b6af  jns     short loc_18003B6C5
0x18003b6b1  lea     rcx, aHrClientGetses_2; "hr = client.GetSessionId(dwSessionId)"
0x18003b6b8  mov     [rsp+110h+var_F0], rcx
0x18003b6bd  mov     r8d, 1616h
0x18003b6c3  jmp     short loc_18003B659
0x18003b6c5  mov     rax, rdi
0x18003b6c8  and     eax, 10h
0x18003b6cb  test    dil, 1
0x18003b6cf  jz      short loc_18003B6EA
0x18003b6d1  lea     rcx, [rbp+4Fh+var_C0]
0x18003b6d5  test    rax, rax
0x18003b6d8  jz      short loc_18003B6E1
0x18003b6da  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18003b6df  jmp     short loc_18003B714
0x18003b6e1  lea     rdx, aPsPassword_0; "ps:password"
0x18003b6e8  jmp     short loc_18003B6FA
0x18003b6ea  test    rax, rax
0x18003b6ed  jz      short loc_18003B701
0x18003b6ef  lea     rdx, aPsMembernameon; "ps:membernameonly"
0x18003b6f6  lea     rcx, [rbp+4Fh+var_C0]
0x18003b6fa  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18003b6ff  jmp     short loc_18003B714
0x18003b701  bt      rdi, 8
0x18003b706  jnb     short loc_18003B714
0x18003b708  mov     rdx, r14
0x18003b70b  lea     rcx, [rbp+4Fh+var_C0]
0x18003b70f  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x18003b714  bt      rdi, 18h
0x18003b719  jnb     loc_18003B7AC
0x18003b71f  xor     r9d, r9d; int *
0x18003b722  lea     r8, [rbp+4Fh+var_B8]; struct _LUID *
0x18003b726  mov     edx, [rsp+110h+var_D0]; unsigned int
0x18003b72a  xor     ecx, ecx; unsigned int
0x18003b72c  call    ?SignInAssociatedUser@@YAJKKAEAU_LUID@@PEAH@Z; SignInAssociatedUser(ulong,ulong,_LUID &,int *)
0x18003b731  mov     [rbp+4Fh+arg_8], eax
0x18003b734  mov     dword ptr [rsp+110h+var_F0], eax
0x18003b738  lea     r9, aSigninassociat; "SignInAssociatedUser. (0x%x)"
0x18003b73f  mov     r8d, 1634h; unsigned int
0x18003b745  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18003b74c  mov     ecx, 2; unsigned __int8
0x18003b751  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18003b756  mov     rbx, cs:?g_pPPCRL@@3PEAVCPassportClientLibrary@@EA; CPassportClientLibrary * g_pPPCRL
0x18003b75d  mov     rdx, r14
0x18003b760  lea     rcx, [rbp+4Fh+var_88]
0x18003b764  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18003b769  lea     rcx, [rbp+4Fh+var_A8]
0x18003b76d  mov     [rsp+110h+var_F0], rcx
0x18003b772  mov     r9, rax
0x18003b775  mov     r8d, [rsp+110h+var_D0]
0x18003b77a  lea     rdx, [rbp+4Fh+var_B8]
0x18003b77e  lea     rcx, [rbx+1F0h]
0x18003b785  call    ?GetSignedInUsernames@CIdentityStore@@QEAAJAEAU_LUID@@KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@4@@Z; CIdentityStore::GetSignedInUsernames(_LUID &,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x18003b78a  mov     [rbp+4Fh+arg_8], eax
0x18003b78d  test    eax, eax
0x18003b78f  jns     short loc_18003B7A8
0x18003b791  lea     rcx, aHrGPppcrlGetid_24; "hr = g_pPPCRL->GetIdentityStore()->GetS"...
0x18003b798  mov     [rsp+110h+var_F0], rcx
0x18003b79d  mov     r8d, 1637h
0x18003b7a3  jmp     loc_18003B659
0x18003b7a8  mov     rsi, [rbp+4Fh+var_A0]
0x18003b7ac  test    rdi, 111h
0x18003b7b3  jz      short loc_18003B7DF
0x18003b7b5  lea     rdx, [rbp+4Fh+var_A8]
0x18003b7b9  mov     rcx, [rbp+4Fh+var_C0]
0x18003b7bd  call    ?GetCachedIdentities@@YAJPEBGAEAV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z; GetCachedIdentities(ushort const *,ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x18003b7c2  mov     [rbp+4Fh+arg_8], eax
0x18003b7c5  test    eax, eax
0x18003b7c7  jns     loc_18003B881
0x18003b7cd  lea     rcx, aHrGetcachedide; "hr = GetCachedIdentities(wszCachedCredT"...
0x18003b7d4  mov     r8d, 163Dh
0x18003b7da  jmp     loc_18003B877
0x18003b7df  test    rdi, 111000h
0x18003b7e6  jz      loc_18003B885
0x18003b7ec  lea     rdx, [rbp+4Fh+var_B0]
0x18003b7f0  lea     rcx, [rbp+4Fh+var_C8]; this
0x18003b7f4  call    ?GetTokenUser@CAutoImpersonateClient@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CAutoImpersonateClient::GetTokenUser(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18003b7f9  mov     [rbp+4Fh+arg_8], eax
0x18003b7fc  test    eax, eax
0x18003b7fe  jns     short loc_18003B817
0x18003b800  lea     rcx, aHrClientGettok_1; "hr = client.GetTokenUser(pszSid)"
0x18003b807  mov     [rsp+110h+var_F0], rcx
0x18003b80c  mov     r8d, 1647h
0x18003b812  jmp     loc_18003B659
0x18003b817  lea     rdx, [rbp+4Fh+var_B8]; struct _LUID *
0x18003b81b  lea     rcx, [rbp+4Fh+var_C8]; this
0x18003b81f  call    ?GetLogonId@CAutoImpersonateClient@@QEAAJAEAU_LUID@@@Z; CAutoImpersonateClient::GetLogonId(_LUID &)
0x18003b824  mov     [rbp+4Fh+arg_8], eax
0x18003b827  test    eax, eax
0x18003b829  jns     short loc_18003B842
0x18003b82b  lea     rcx, aHrClientGetlog; "hr = client.GetLogonId(logonId)"
0x18003b832  mov     [rsp+110h+var_F0], rcx
0x18003b837  mov     r8d, 1648h
0x18003b83d  jmp     loc_18003B659
0x18003b842  lea     rax, [rbp+4Fh+var_A8]
0x18003b846  mov     [rsp+110h+var_E8], rax
0x18003b84b  mov     [rsp+110h+var_F0], r15
0x18003b850  mov     r9, r14
0x18003b853  mov     r8, rdi
0x18003b856  lea     rdx, [rbp+4Fh+var_B8]
0x18003b85a  lea     rcx, [rbp+4Fh+var_B0]
0x18003b85e  call    ?EnumIdentities@CSystemStore@@SAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAU_LUID@@_KAEBV23@3AEAV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; CSystemStore::EnumIdentities(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,_LUID &,unsigned __int64,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x18003b863  mov     [rbp+4Fh+arg_8], eax
0x18003b866  test    eax, eax
0x18003b868  jns     short loc_18003B881
0x18003b86a  lea     rcx, aHrCsystemstore_0; "hr = CSystemStore::EnumIdentities(pszSi"...
0x18003b871  mov     r8d, 164Fh
0x18003b877  mov     [rsp+110h+var_F0], rcx
0x18003b87c  jmp     loc_18003B659
0x18003b881  mov     rsi, [rbp+4Fh+var_A0]
0x18003b885  lea     rbx, ds:0[rsi*8]
0x18003b88d  mov     rcx, rbx; Size
0x18003b890  call    cs:__imp_malloc
0x18003b896  mov     rdi, rax
0x18003b899  test    rax, rax
0x18003b89c  jnz     short loc_18003B8AA
0x18003b89e  mov     [rbp+4Fh+arg_8], 8007000Eh
0x18003b8a5  jmp     loc_18003B991
0x18003b8aa  mov     r8, rbx; Size
0x18003b8ad  xor     edx, edx; Val
0x18003b8af  mov     rcx, rdi; void *
0x18003b8b2  call    memset_0
0x18003b8b7  xor     r14d, r14d
0x18003b8ba  cmp     r14, rsi
0x18003b8bd  jnb     loc_18003B989
0x18003b8c3  mov     rdx, r14
0x18003b8c6  lea     rcx, [rbp+4Fh+var_A8]
0x18003b8ca  call    ??A?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@1@_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::operator[](unsigned __int64)
0x18003b8cf  mov     rcx, [rax]
0x18003b8d2  movsxd  rcx, dword ptr [rcx-10h]
0x18003b8d6  lea     rcx, ds:2[rcx*2]; Size
0x18003b8de  call    cs:__imp_malloc
0x18003b8e4  mov     [rdi+r14*8], rax
0x18003b8e8  test    rax, rax
0x18003b8eb  jz      short loc_18003B955
0x18003b8ed  mov     rdx, r14
0x18003b8f0  lea     rcx, [rbp+4Fh+var_A8]
0x18003b8f4  call    ??A?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@1@_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::operator[](unsigned __int64)
0x18003b8f9  mov     rbx, [rax]
0x18003b8fc  mov     rdx, r14
0x18003b8ff  lea     rcx, [rbp+4Fh+var_A8]
0x18003b903  call    ??A?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@1@_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::operator[](unsigned __int64)
0x18003b908  mov     rcx, [rax]
0x18003b90b  mov     eax, [rcx-10h]
0x18003b90e  inc     eax
0x18003b910  movsxd  rdx, eax; unsigned __int64
0x18003b913  mov     r8, rbx; unsigned __int16 *
0x18003b916  mov     rcx, [rdi+r14*8]; unsigned __int16 *
0x18003b91a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003b91f  mov     [rbp+4Fh+arg_8], eax
0x18003b922  test    eax, eax
0x18003b924  js      short loc_18003B92B
0x18003b926  inc     r14
0x18003b929  jmp     short loc_18003B8BA
0x18003b92b  lea     rcx, aHrStringcchcop_0; "hr = StringCchCopyW(rgwszMemberNames[i]"...
0x18003b932  mov     [rsp+110h+var_F0], rcx; char *
0x18003b937  mov     r9d, eax; int
0x18003b93a  mov     r8d, 165Dh; unsigned int
0x18003b940  lea     rdx, aHandleenumiden; "HandleEnumIdentities"
0x18003b947  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18003b94e  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18003b953  jmp     short loc_18003B95C
0x18003b955  mov     [rbp+4Fh+arg_8], 8007000Eh
0x18003b95c  mov     r14, rdi
0x18003b95f  xor     ebx, ebx
0x18003b961  test    rsi, rsi
0x18003b964  jz      short loc_18003B97E
0x18003b966  mov     rcx, [r14+rbx*8]; Block
0x18003b96a  test    rcx, rcx
0x18003b96d  jz      short loc_18003B975
0x18003b96f  call    cs:__imp_free
0x18003b975  inc     ebx
0x18003b977  mov     eax, ebx
0x18003b979  cmp     rax, rsi
0x18003b97c  jb      short loc_18003B966
0x18003b97e  mov     rcx, rdi; Block
0x18003b981  call    cs:__imp_free
0x18003b987  jmp     short loc_18003B991
0x18003b989  mov     [r12], esi
0x18003b98d  mov     [r13+0], rdi
0x18003b991  mov     ebx, [rbp+4Fh+arg_8]
0x18003b994  lea     rax, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x18003b99b  mov     [rbp+4Fh+var_80], rax
0x18003b99f  lea     rcx, [rbp+4Fh+var_80]; this
0x18003b9a3  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x18003b9a8  nop
0x18003b9a9  cmp     dword ptr [rbp+4Fh+var_C8], 0
0x18003b9ad  jz      short loc_18003B9BA
0x18003b9af  xor     edx, edx; Token
0x18003b9b1  xor     ecx, ecx; Thread
0x18003b9b3  call    cs:__imp_SetThreadToken
0x18003b9b9  nop
0x18003b9ba  mov     rcx, [rbp+4Fh+var_B0]
0x18003b9be  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18003b9c2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003b9c7  nop
0x18003b9c8  lea     rcx, [rbp+4Fh+var_A8]
0x18003b9cc  call    ??1?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::~CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>(void)
0x18003b9d1  nop
0x18003b9d2  mov     rcx, [rbp+4Fh+var_C0]
0x18003b9d6  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18003b9da  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003b9df  nop
0x18003b9e0  lea     rcx, [rbp+4Fh+var_60]
0x18003b9e4  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18003b9e9  mov     eax, ebx
0x18003b9eb  add     rsp, 0D8h
0x18003b9f2  pop     r15
0x18003b9f4  pop     r14
0x18003b9f6  pop     r13
0x18003b9f8  pop     r12
0x18003b9fa  pop     rdi
0x18003b9fb  pop     rsi
0x18003b9fc  pop     rbx
0x18003b9fd  pop     rbp
0x18003b9fe  retn
  ... truncated ...
```
