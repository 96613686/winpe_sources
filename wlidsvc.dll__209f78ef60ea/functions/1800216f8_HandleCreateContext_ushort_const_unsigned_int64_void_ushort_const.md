# HandleCreateContext(ushort const *,unsigned __int64,void * *,ushort const *)

- ea: `0x1800216f8`
- end: `0x180021b22`
- name: `?HandleCreateContext@@YAJPEBG_KPEAPEAX0@Z`
- size: `1066`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, void **, const unsigned __int16 *)`
- caller_count: `8`
- callee_count: `22`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180021550`
- `0x18006da60`
- `0x1800a9960`
- `0x1800b57d4`
- `0x1800b6310`
- `0x1800bc9a0`
- `0x1800be5d0`
- `0x1800e4580`

## callees

- `0x18000c050`
- `0x18000fd04`
- `0x1800133c8`
- `0x180015860`
- `0x180015fb0`
- `0x180019690`
- `0x180019780`
- `0x18001a530`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001cf20`
- `0x18001dfec`
- `0x18001f968`
- `0x180020970`
- `0x180020b10`
- `0x1800216f8`
- `0x180021b28`
- `0x180021bbc`
- `0x180021c10`
- `0x180021df0`
- `0x180040084`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800217b0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180021955`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800217b0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180021955`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800219f7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800219f7`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18002187d`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18002187d`

## string_xrefs

- `0x18002186b`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x180021788`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18002192f`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180021a6f`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180021ae9`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180021772`: `HandleCreateContext`
- `0x180021a35`: `HandleCreateContext`
- `0x180021ae2`: `HandleCreateContext`
- `0x180021922`: `Created Context 0x%p for '%ls'`
- `0x180021a1d`: `hr = client.ImpersonateClient(&hContextToken)`
- `0x180021a5d`: `hr = g_pPPCRL->GetIdentityStore()->GetNewIdentityHandle(logonId, pszSid, hContextToken, dwPID, CStringW(wszMemberName), flags, pHandle)`
- `0x180021847`: `CAutoImpersonateClient::GetCallerProcessID`
- `0x180021ab6`: `hr = client.GetTokenUser(pszSid)`

## pseudocode

```c
__int64 __fastcall HandleCreateContext(const unsigned __int16 *a1, __int64 a2, void **a3, const unsigned __int16 *a4)
{
  unsigned int v8; // r15d
  unsigned __int8 v9; // dl
  PPTraceStatus *v10; // rcx
  char v11; // di
  bool v12; // zf
  char v13; // al
  int LogonId; // eax
  int v15; // eax
  CPassportClientLibrary *v16; // rbx
  __int64 v17; // rax
  int NewIdentityHandle; // eax
  unsigned __int8 v19; // dl
  PPTraceStatus *v20; // rcx
  const unsigned __int16 *String; // rax
  int SingleIdentity; // eax
  CRefCounted *v23; // rbx
  __int64 v24; // rcx
  unsigned int v25; // ebx
  unsigned int v27; // r8d
  char *v28; // [rsp+20h] [rbp-99h]
  char *v29; // [rsp+20h] [rbp-99h]
  unsigned int Pid[2]; // [rsp+40h] [rbp-79h] BYREF
  int v31; // [rsp+48h] [rbp-71h] BYREF
  __int64 v32; // [rsp+50h] [rbp-69h] BYREF
  void **v33; // [rsp+58h] [rbp-61h] BYREF
  const unsigned __int16 *v34; // [rsp+60h] [rbp-59h]
  void *Block; // [rsp+68h] [rbp-51h]
  __int64 v36; // [rsp+70h] [rbp-49h]
  struct _LUID v37; // [rsp+78h] [rbp-41h] BYREF
  __int64 v38; // [rsp+80h] [rbp-39h] BYREF
  _BYTE v39[8]; // [rsp+88h] [rbp-31h] BYREF
  void **v40; // [rsp+90h] [rbp-29h] BYREF
  __int128 v41; // [rsp+98h] [rbp-21h]
  __int64 v42; // [rsp+A8h] [rbp-11h]
  _BYTE v43[96]; // [rsp+B0h] [rbp-9h] BYREF
  int v44; // [rsp+120h] [rbp+67h] BYREF

  v8 = 0;
  v44 = 0;
  v11 = 1;
  if ( !PPTraceShouldRedact() || (LOBYTE(v10) = 1, v12 = !PPTraceStatus::TraceOnFlag(v10, v9), v13 = 1, v12) )
    v13 = 0;
  v34 = a1;
  Block = 0;
  LOBYTE(v36) = v13;
  v33 = &PPRedactedStringW::`vftable';
  PPRedactedStringW::GetString((PPRedactedStringW *)&v33);
  CTraceFuncW<long>::CTraceFuncW<long>(
    v43,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    1108,
    &v44,
    "HandleCreateContext",
    L"wszMemberName='%ls'");
  v33 = &PPRedactedStringW::`vftable';
  if ( Block )
    free(Block);
  v37 = 0;
  v32 = 0;
  v38 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v40 = &ATL::CAccessToken::`vftable';
  v41 = 0;
  v42 = 0;
  *a3 = 0;
  LogonId = CAutoImpersonateClient::ImpersonateClient((CAutoImpersonateClient *)&v32, (struct ATL::CAccessToken *)&v40);
  v44 = LogonId;
  if ( LogonId < 0 )
  {
    v29 = "hr = client.ImpersonateClient(&hContextToken)";
    v27 = 1119;
LABEL_28:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleCreateContext",
      v27,
      LogonId,
      v29);
    goto LABEL_23;
  }
  LogonId = CAutoImpersonateClient::GetLogonId((CAutoImpersonateClient *)&v32, &v37);
  v44 = LogonId;
  if ( LogonId < 0 )
  {
    v29 = "hr = client.GetLogonId(logonId)";
    v27 = 1120;
    goto LABEL_28;
  }
  LogonId = CAutoImpersonateClient::GetTokenUser((CAutoImpersonateClient *)&v32, &v38);
  v44 = LogonId;
  if ( LogonId < 0 )
  {
    v29 = "hr = client.GetTokenUser(pszSid)";
    v27 = 1121;
    goto LABEL_28;
  }
  v31 = 0;
  Pid[0] = 0;
  v33 = (void **)"CAutoImpersonateClient::GetCallerProcessID";
  v34 = (const unsigned __int16 *)&v31;
  Block = 0;
  v36 = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h",
    "CAutoImpersonateClient::GetCallerProcessID",
    (const char *)0x1BD,
    0,
    (const unsigned __int16 *)v28);
  v15 = I_RpcBindingInqLocalClientPID(0, Pid);
  if ( v15 )
  {
    if ( v15 > 0 )
      v15 = (unsigned __int16)v15 | 0x80070000;
    v31 = v15;
  }
  else
  {
    v8 = Pid[0];
  }
  CTraceFuncW<long>::~CTraceFuncW<long>(&v33);
  v16 = g_pPPCRL;
  v17 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          v39,
          a1);
  NewIdentityHandle = CIdentityStore::GetNewIdentityHandle((char *)v16 + 496, &v37, &v38, &v40, v8, v17, a2, a3);
  v44 = NewIdentityHandle;
  if ( NewIdentityHandle < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleCreateContext",
      0x468u,
      NewIdentityHandle,
      "hr = g_pPPCRL->GetIdentityStore()->GetNewIdentityHandle(logonId, pszSid, hContextToken, dwPID, CStringW(wszMemberN"
      "ame), flags, pHandle)");
    goto LABEL_23;
  }
  if ( !PPTraceShouldRedact() || (LOBYTE(v20) = 1, !PPTraceStatus::TraceOnFlag(v20, v19)) )
    v11 = 0;
  v34 = a1;
  Block = 0;
  LOBYTE(v36) = v11;
  v33 = &PPRedactedStringW::`vftable';
  String = PPRedactedStringW::GetString((PPRedactedStringW *)&v33);
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    0x46Au,
    L"Created Context 0x%p for '%ls'",
    *a3,
    String);
  v33 = &PPRedactedStringW::`vftable';
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  if ( a4 )
  {
    *(_QWORD *)Pid = 0;
    SingleIdentity = CIdentityStore::GetSingleIdentity((char *)g_pPPCRL + 496, &v37, *a3, Pid);
    v44 = SingleIdentity;
    if ( SingleIdentity < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleCreateContext",
        0x46Fu,
        SingleIdentity,
        "hr = g_pPPCRL->GetIdentityStore()->GetSingleIdentity(logonId, *pHandle, pIdentity)");
      CAutoRefPtr<CSingleIdentity>::Deinit(Pid);
      goto LABEL_23;
    }
    v23 = *(CRefCounted **)Pid;
    if ( (a2 & 0x200000) != 0 )
    {
      v24 = *(_QWORD *)Pid + 712LL;
    }
    else
    {
      if ( (a2 & 0x800000) == 0 )
      {
LABEL_21:
        if ( v23 )
          CRefCounted::Release(v23);
        goto LABEL_23;
      }
      v24 = *(_QWORD *)Pid + 720LL;
    }
    ATL::CSimpleStringT<unsigned short,0>::SetString(v24, a4);
    goto LABEL_21;
  }
LABEL_23:
  if ( v44 < 0 && *a3 )
  {
    HandleDeleteContextEx(0, 0, *a3);
    *a3 = 0;
  }
  v25 = v44;
  v40 = &ATL::CAccessToken::`vftable';
  ATL::CAccessToken::Clear((ATL::CAccessToken *)&v40);
  ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
  if ( (_DWORD)v32 )
    SetThreadToken(0, 0);
  CTraceFuncW<long>::~CTraceFuncW<long>(v43);
  return v25;
}

```

## disassembly

```asm
0x1800216f8  push    rbp
0x1800216fa  push    rbx
0x1800216fb  push    rsi
0x1800216fc  push    rdi
0x1800216fd  push    r12
0x1800216ff  push    r13
0x180021701  push    r14
0x180021703  push    r15
0x180021705  lea     rbp, [rsp-1Fh]
0x18002170a  sub     rsp, 0D8h
0x180021711  mov     r14, r9
0x180021714  mov     rsi, r8
0x180021717  mov     r12, rdx
0x18002171a  mov     r13, rcx
0x18002171d  xor     r15d, r15d
0x180021720  mov     [rbp+57h+arg_0], r15d
0x180021724  call    ?PPTraceShouldRedact@@YA_NXZ; PPTraceShouldRedact(void)
0x180021729  mov     dil, 1
0x18002172c  test    al, al
0x18002172e  jz      short loc_18002173F
0x180021730  mov     cl, dil; this
0x180021733  call    ?TraceOnFlag@PPTraceStatus@@YA_NE@Z; PPTraceStatus::TraceOnFlag(uchar)
0x180021738  test    al, al
0x18002173a  mov     al, dil
0x18002173d  jnz     short loc_180021742
0x18002173f  mov     al, r15b
0x180021742  mov     [rbp+57h+var_B0], r13
0x180021746  mov     [rbp+57h+Block], r15
0x18002174a  mov     byte ptr [rbp+57h+var_A0], al
0x18002174d  lea     rax, ??_7PPRedactedStringW@@6B@; const PPRedactedStringW::`vftable'
0x180021754  mov     [rbp+57h+var_B8], rax
0x180021758  lea     rcx, [rbp+57h+var_B8]; this
0x18002175c  call    ?GetString@PPRedactedStringW@@QEAAPEBGXZ; PPRedactedStringW::GetString(void)
0x180021761  mov     [rsp+110h+var_E0], rax
0x180021766  lea     rax, aWszmembernameL_0; "wszMemberName='%ls'"
0x18002176d  mov     [rsp+110h+var_E8], rax
0x180021772  lea     rax, aHandlecreateco; "HandleCreateContext"
0x180021779  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x18002177e  lea     r9, [rbp+57h+arg_0]
0x180021782  mov     r8d, 454h
0x180021788  lea     rbx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18002178f  mov     rdx, rbx
0x180021792  lea     rcx, [rbp+57h+var_60]
0x180021796  call    ??0?$CTraceFuncW@J@@QEAA@PEBDKAEAJ0PEBGZZ; CTraceFuncW<long>::CTraceFuncW<long>(char const *,ulong,long &,char const *,ushort const *,...)
0x18002179b  nop
0x18002179c  lea     rax, ??_7PPRedactedStringW@@6B@; const PPRedactedStringW::`vftable'
0x1800217a3  mov     [rbp+57h+var_B8], rax
0x1800217a7  mov     rcx, [rbp+57h+Block]; Block
0x1800217ab  test    rcx, rcx
0x1800217ae  jz      short loc_1800217B6
0x1800217b0  call    cs:__imp_free
0x1800217b6  mov     qword ptr [rbp+57h+var_98.LowPart], r15
0x1800217ba  mov     [rbp+57h+var_C0], r15
0x1800217be  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800217c5  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800217cc  mov     rax, [rax+18h]
0x1800217d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217d5  add     rax, 18h
0x1800217d9  mov     [rbp+57h+var_90], rax
0x1800217dd  lea     rax, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x1800217e4  mov     [rbp+57h+var_80], rax
0x1800217e8  xorps   xmm0, xmm0
0x1800217eb  movdqu  [rbp+57h+var_78], xmm0
0x1800217f0  mov     [rbp+57h+var_68], r15
0x1800217f4  mov     [rsi], r15
0x1800217f7  lea     rdx, [rbp+57h+var_80]; struct ATL::CAccessToken *
0x1800217fb  lea     rcx, [rbp+57h+var_C0]; this
0x1800217ff  call    ?ImpersonateClient@CAutoImpersonateClient@@QEAAJPEAVCAccessToken@ATL@@@Z; CAutoImpersonateClient::ImpersonateClient(ATL::CAccessToken *)
0x180021804  mov     [rbp+57h+arg_0], eax
0x180021807  test    eax, eax
0x180021809  js      loc_180021A1D
0x18002180f  lea     rdx, [rbp+57h+var_98]; struct _LUID *
0x180021813  lea     rcx, [rbp+57h+var_C0]; this
0x180021817  call    ?GetLogonId@CAutoImpersonateClient@@QEAAJAEAU_LUID@@@Z; CAutoImpersonateClient::GetLogonId(_LUID &)
0x18002181c  mov     [rbp+57h+arg_0], eax
0x18002181f  test    eax, eax
0x180021821  js      loc_180021A9F
0x180021827  lea     rdx, [rbp+57h+var_90]
0x18002182b  lea     rcx, [rbp+57h+var_C0]; this
0x18002182f  call    ?GetTokenUser@CAutoImpersonateClient@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CAutoImpersonateClient::GetTokenUser(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180021834  mov     [rbp+57h+arg_0], eax
0x180021837  test    eax, eax
0x180021839  js      loc_180021AB6
0x18002183f  mov     [rbp+57h+var_C8], r15d
0x180021843  mov     [rbp+57h+Pid], r15d
0x180021847  lea     rdx, aCautoimpersona_2; "CAutoImpersonateClient::GetCallerProces"...
0x18002184e  mov     [rbp+57h+var_B8], rdx
0x180021852  lea     rax, [rbp+57h+var_C8]
0x180021856  mov     [rbp+57h+var_B0], rax
0x18002185a  mov     [rbp+57h+Block], r15
0x18002185e  mov     [rbp+57h+var_A0], r15
0x180021862  xor     r9d, r9d; unsigned int
0x180021865  mov     r8d, 1BDh; char *
0x18002186b  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180021872  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180021877  lea     rdx, [rbp+57h+Pid]; Pid
0x18002187b  xor     ecx, ecx; Binding
0x18002187d  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180021883  test    eax, eax
0x180021885  jnz     loc_180021A8D
0x18002188b  mov     r15d, [rbp+57h+Pid]
0x18002188f  lea     rcx, [rbp+57h+var_B8]
0x180021893  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180021898  mov     rbx, cs:?g_pPPCRL@@3PEAVCPassportClientLibrary@@EA; CPassportClientLibrary * g_pPPCRL
0x18002189f  mov     rdx, r13
0x1800218a2  lea     rcx, [rbp+57h+var_88]
0x1800218a6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800218ab  mov     [rsp+110h+var_D8], rsi
0x1800218b0  mov     [rsp+110h+var_E0], r12
0x1800218b5  mov     [rsp+110h+var_E8], rax
0x1800218ba  mov     dword ptr [rsp+110h+var_F0], r15d
0x1800218bf  lea     r9, [rbp+57h+var_80]
0x1800218c3  lea     r8, [rbp+57h+var_90]
0x1800218c7  lea     rdx, [rbp+57h+var_98]
0x1800218cb  lea     rcx, [rbx+1F0h]
0x1800218d2  call    ?GetNewIdentityHandle@CIdentityStore@@QEAAJAEAU_LUID@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAVCAccessToken@4@KV34@_KPEAPEAX@Z; CIdentityStore::GetNewIdentityHandle(_LUID &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAccessToken &,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,unsigned __int64,void * *)
0x1800218d7  mov     [rbp+57h+arg_0], eax
0x1800218da  xor     r15d, r15d
0x1800218dd  test    eax, eax
0x1800218df  js      loc_180021A5D
0x1800218e5  call    ?PPTraceShouldRedact@@YA_NXZ; PPTraceShouldRedact(void)
0x1800218ea  test    al, al
0x1800218ec  jnz     loc_180021A78
0x1800218f2  mov     dil, r15b
0x1800218f5  mov     [rbp+57h+var_B0], r13
0x1800218f9  mov     [rbp+57h+Block], r15
0x1800218fd  mov     byte ptr [rbp+57h+var_A0], dil
0x180021901  lea     rax, ??_7PPRedactedStringW@@6B@; const PPRedactedStringW::`vftable'
0x180021908  mov     [rbp+57h+var_B8], rax
0x18002190c  lea     rcx, [rbp+57h+var_B8]; this
0x180021910  call    ?GetString@PPRedactedStringW@@QEAAPEBGXZ; PPRedactedStringW::GetString(void)
0x180021915  mov     [rsp+110h+var_E8], rax
0x18002191a  mov     rax, [rsi]
0x18002191d  mov     [rsp+110h+var_F0], rax
0x180021922  lea     r9, aCreatedContext; "Created Context 0x%p for '%ls'"
0x180021929  mov     r8d, 46Ah; unsigned int
0x18002192f  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180021936  mov     ecx, 5; unsigned __int8
0x18002193b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180021940  nop
0x180021941  lea     rax, ??_7PPRedactedStringW@@6B@; const PPRedactedStringW::`vftable'
0x180021948  mov     [rbp+57h+var_B8], rax
0x18002194c  mov     rcx, [rbp+57h+Block]; Block
0x180021950  test    rcx, rcx
0x180021953  jz      short loc_18002195F
0x180021955  call    cs:__imp_free
0x18002195b  mov     [rbp+57h+Block], r15
0x18002195f  test    r14, r14
0x180021962  jz      short loc_1800219BD
0x180021964  mov     qword ptr [rbp+57h+Pid], r15
0x180021968  mov     rcx, cs:?g_pPPCRL@@3PEAVCPassportClientLibrary@@EA; CPassportClientLibrary * g_pPPCRL
0x18002196f  add     rcx, 1F0h
0x180021976  lea     r9, [rbp+57h+Pid]
0x18002197a  mov     r8, [rsi]
0x18002197d  lea     rdx, [rbp+57h+var_98]
0x180021981  call    ?GetSingleIdentity@CIdentityStore@@QEAAJAEAU_LUID@@PEAXAEAV?$CAutoRefPtr@VCSingleIdentity@@@@@Z; CIdentityStore::GetSingleIdentity(_LUID &,void *,CAutoRefPtr<CSingleIdentity> &)
0x180021986  mov     [rbp+57h+arg_0], eax
0x180021989  test    eax, eax
0x18002198b  js      loc_180021ACD
0x180021991  mov     rbx, qword ptr [rbp+57h+Pid]
0x180021995  bt      r12, 15h
0x18002199a  jnb     loc_180021A46
0x1800219a0  lea     rcx, [rbx+2C8h]
0x1800219a7  mov     rdx, r14
0x1800219aa  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1800219af  nop
0x1800219b0  test    rbx, rbx
0x1800219b3  jz      short loc_1800219BD
0x1800219b5  mov     rcx, rbx; this
0x1800219b8  call    ?Release@CRefCounted@@QEAAXXZ; CRefCounted::Release(void)
0x1800219bd  cmp     [rbp+57h+arg_0], r15d
0x1800219c1  jl      loc_180021B04
0x1800219c7  mov     ebx, [rbp+57h+arg_0]
0x1800219ca  lea     rax, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x1800219d1  mov     [rbp+57h+var_80], rax
0x1800219d5  lea     rcx, [rbp+57h+var_80]; this
0x1800219d9  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x1800219de  nop
0x1800219df  mov     rcx, [rbp+57h+var_90]
0x1800219e3  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800219e7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800219ec  nop
0x1800219ed  cmp     dword ptr [rbp+57h+var_C0], r15d
0x1800219f1  jz      short loc_1800219FE
0x1800219f3  xor     edx, edx; Token
0x1800219f5  xor     ecx, ecx; Thread
0x1800219f7  call    cs:__imp_SetThreadToken
0x1800219fd  nop
0x1800219fe  lea     rcx, [rbp+57h+var_60]
0x180021a02  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180021a07  mov     eax, ebx
0x180021a09  add     rsp, 0D8h
0x180021a10  pop     r15
0x180021a12  pop     r14
0x180021a14  pop     r13
0x180021a16  pop     r12
0x180021a18  pop     rdi
0x180021a19  pop     rsi
0x180021a1a  pop     rbx
0x180021a1b  pop     rbp
0x180021a1c  retn
0x180021a1d  lea     r8, aHrClientImpers_0; "hr = client.ImpersonateClient(&hContext"...
0x180021a24  mov     [rsp+110h+var_F0], r8; char *
0x180021a29  mov     r8d, 45Fh; unsigned int
0x180021a2f  mov     rcx, rbx; char *
0x180021a32  mov     r9d, eax; int
0x180021a35  lea     rdx, aHandlecreateco; "HandleCreateContext"
0x180021a3c  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180021a41  jmp     loc_1800219BD
0x180021a46  bt      r12, 17h
0x180021a4b  jnb     loc_1800219B0
0x180021a51  lea     rcx, [rbx+2D0h]
0x180021a58  jmp     loc_1800219A7
0x180021a5d  lea     rcx, aHrGPppcrlGetid_26; "hr = g_pPPCRL->GetIdentityStore()->GetN"...
0x180021a64  mov     [rsp+110h+var_F0], rcx
0x180021a69  mov     r8d, 468h
0x180021a6f  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180021a76  jmp     short loc_180021A32
0x180021a78  mov     cl, dil; this
0x180021a7b  call    ?TraceOnFlag@PPTraceStatus@@YA_NE@Z; PPTraceStatus::TraceOnFlag(uchar)
0x180021a80  test    al, al
0x180021a82  jnz     loc_1800218F5
0x180021a88  jmp     loc_1800218F2
0x180021a8d  jle     short loc_180021A97
0x180021a8f  movzx   eax, ax
0x180021a92  or      eax, 80070000h
0x180021a97  mov     [rbp+57h+var_C8], eax
0x180021a9a  jmp     loc_18002188F
0x180021a9f  lea     rcx, aHrClientGetlog; "hr = client.GetLogonId(logonId)"
0x180021aa6  mov     [rsp+110h+var_F0], rcx
0x180021aab  mov     r8d, 460h
0x180021ab1  jmp     loc_180021A2F
0x180021ab6  lea     rcx, aHrClientGettok_1; "hr = client.GetTokenUser(pszSid)"
0x180021abd  mov     [rsp+110h+var_F0], rcx
0x180021ac2  mov     r8d, 461h
0x180021ac8  jmp     loc_180021A2F
0x180021acd  lea     rcx, aHrGPppcrlGetid_15; "hr = g_pPPCRL->GetIdentityStore()->GetS"...
0x180021ad4  mov     [rsp+110h+var_F0], rcx; char *
0x180021ad9  mov     r9d, eax; int
0x180021adc  mov     r8d, 46Fh; unsigned int
0x180021ae2  lea     rdx, aHandlecreateco; "HandleCreateContext"
0x180021ae9  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180021af0  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180021af5  nop
0x180021af6  lea     rcx, [rbp+57h+Pid]
0x180021afa  call    ?Deinit@?$CAutoRefPtr@VCSingleIdentity@@@@IEAAXXZ; CAutoRefPtr<CSingleIdentity>::Deinit(void)
0x180021aff  jmp     loc_1800219BD
0x180021b04  mov     r8, [rsi]; void *
0x180021b07  test    r8, r8
0x180021b0a  jz      loc_1800219C7
0x180021b10  xor     edx, edx; unsigned __int8
0x180021b12  xor     ecx, ecx; unsigned __int64
0x180021b14  call    ?HandleDeleteContextEx@@YAJ_KEQEAX@Z; HandleDeleteContextEx(unsigned __int64,uchar,void * const)
0x180021b19  mov     [rsi], r15
0x180021b1c  jmp     loc_1800219C7
```
