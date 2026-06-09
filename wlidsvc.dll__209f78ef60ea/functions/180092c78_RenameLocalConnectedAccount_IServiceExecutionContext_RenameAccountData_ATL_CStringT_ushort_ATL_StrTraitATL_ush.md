# RenameLocalConnectedAccount(IServiceExecutionContext *,RenameAccountData &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x180092c78`
- end: `0x180093052`
- name: `?RenameLocalConnectedAccount@@YAJPEAVIServiceExecutionContext@@AEAURenameAccountData@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `986`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a1f78`

## callees

- `0x18000c050`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001f4d0`
- `0x18001f968`
- `0x180043344`
- `0x18008fe20`
- `0x180092c78`
- `0x180093058`
- `0x180094b4c`
- `0x1800a6280`
- `0x1800a63ec`
- `0x1800b1afc`
- `0x180128010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092e86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092f67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092f9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092fe5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092e86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092f67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092f9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092fe5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180092ee2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180092ee2`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x180092f40`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x180092f40`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x180092e7c`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x180092e7c`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSDisconnectSession` at `0x180092f5d`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSDisconnectSession` at `0x180092fdb`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSDisconnectSession` at `0x180092f5d`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSDisconnectSession` at `0x180092fdb`

## string_xrefs

- `0x180092dae`: `hr = client.ImpersonateClient()`
- `0x180092cda`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\renamemembername.cpp`
- `0x180092d21`: `hr = DeleteIdentityStore(renameAccountData.hOldUser, true, nullptr, cid, isAssociated)`
- `0x180092cab`: `RenameLocalConnectedAccount`
- `0x180092d80`: `hr = HandleConnectIdentity(renameAccountData.hNewUser, &connectFlags, nullptr)`
- `0x180092d55`: `hr = UpdateSamProperties(renameAccountData)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RenameLocalConnectedAccount(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // eax
  int updated; // eax
  int v8; // eax
  int v9; // eax
  const char *v10; // rcx
  unsigned int v11; // r8d
  struct _WTS_SESSION_INFOW *v12; // rax
  signed int LastError; // eax
  const unsigned __int16 *v14; // r9
  unsigned int v15; // r8d
  unsigned __int8 v16; // cl
  DWORD v17; // ebx
  WTS_CONNECTSTATE_CLASS State; // r14d
  __int64 i; // rdi
  signed int v20; // eax
  const unsigned __int16 *v21; // r9
  unsigned int v22; // r8d
  unsigned int v23; // ebx
  DWORD *pCount; // [rsp+20h] [rbp-49h]
  DWORD *pCounta; // [rsp+20h] [rbp-49h]
  DWORD *pCountb; // [rsp+20h] [rbp-49h]
  __int64 v28; // [rsp+30h] [rbp-39h] BYREF
  DWORD v29; // [rsp+38h] [rbp-31h] BYREF
  int v30; // [rsp+3Ch] [rbp-2Dh] BYREF
  PWTS_SESSION_INFOW ppSessionInfo[3]; // [rsp+40h] [rbp-29h] BYREF
  __int128 v32; // [rsp+58h] [rbp-11h] BYREF
  __int128 v33; // [rsp+68h] [rbp-1h]
  _QWORD v34[9]; // [rsp+78h] [rbp+Fh] BYREF
  int v35; // [rsp+D8h] [rbp+6Fh] BYREF
  DWORD SessionId; // [rsp+E8h] [rbp+7Fh] BYREF

  v35 = 0;
  v32 = 0;
  v33 = 0;
  v34[0] = "RenameLocalConnectedAccount";
  v34[1] = &v35;
  v34[2] = 0;
  v34[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\renamemembername.cpp",
    "RenameLocalConnectedAccount",
    (const char *)0xEF,
    0,
    (const unsigned __int16 *)pCount);
  SessionId = 0;
  *(_QWORD *)&v32 = 1;
  DWORD2(v33) = 2;
  v6 = DeleteIdentityStore(*(void **)(a2 + 32), 1, 0, a3, &v28);
  v35 = v6;
  if ( v6 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\renamemembername.cpp",
      "RenameLocalConnectedAccount",
      0xF5u,
      v6,
      "hr = DeleteIdentityStore(renameAccountData.hOldUser, true, nullptr, cid, isAssociated)");
    goto LABEL_46;
  }
  updated = UpdateSamProperties((struct RenameAccountData *)a2);
  v35 = updated;
  if ( updated < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\renamemembername.cpp",
      "RenameLocalConnectedAccount",
      0xF6u,
      updated,
      "hr = UpdateSamProperties(renameAccountData)");
    goto LABEL_46;
  }
  v8 = HandleConnectIdentity(*(void *const *)(a2 + 40), (struct _WLID_CONNECT_PARAM *const)&v32, 0);
  v35 = v8;
  if ( v8 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\renamemembername.cpp",
      "RenameLocalConnectedAccount",
      0xF7u,
      v8,
      "hr = HandleConnectIdentity(renameAccountData.hNewUser, &connectFlags, nullptr)");
    goto LABEL_46;
  }
  v28 = 0;
  v9 = CAutoImpersonateClient::ImpersonateClient((CAutoImpersonateClient *)&v28, 0);
  v35 = v9;
  if ( v9 < 0 )
  {
    v10 = "hr = client.ImpersonateClient()";
    v11 = 252;
LABEL_10:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\renamemembername.cpp",
      "RenameLocalConnectedAccount",
      v11,
      v9,
      v10);
    CAutoImpersonateClient::~CAutoImpersonateClient((CAutoImpersonateClient *)&v28);
    goto LABEL_46;
  }
  v9 = CAutoImpersonateClient::GetSessionId((CAutoImpersonateClient *)&v28, &SessionId);
  v35 = v9;
  if ( v9 < 0 )
  {
    v10 = "hr = client.GetSessionId(currentSessionId)";
    v11 = 253;
    goto LABEL_10;
  }
  CAutoImpersonateClient::~CAutoImpersonateClient((CAutoImpersonateClient *)&v28);
  if ( (unsigned __int8)IsWinStationQueryInformationWPresent()
    && (unsigned __int8)IsWTSFreeMemoryPresent()
    && (unsigned __int8)IsWTSFreeMemoryPresent() )
  {
    v12 = (struct _WTS_SESSION_INFOW *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 72LL))(a1);
    ppSessionInfo[0] = 0;
    ppSessionInfo[2] = v12;
    ppSessionInfo[1] = 0;
    v29 = 0;
    v30 = 0;
    LODWORD(v28) = 0;
    if ( !WTSEnumerateSessionsW(0, 0, 1u, ppSessionInfo, &v29) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v14 = L"WTSEnumerateSessions failed = 0x%x.";
      v15 = 278;
      goto LABEL_20;
    }
    v17 = 0;
    State = WTSActive;
    for ( i = 0; (unsigned int)i < v29; i = (unsigned int)(i + 1) )
    {
      if ( CompareStringOrdinal(L"Console", -1, ppSessionInfo[0][i].pWinStationName, -1, 1) == 2 )
      {
        v17 = ppSessionInfo[0][i].SessionId;
        State = ppSessionInfo[0][i].State;
        LODWORD(pCountb) = v17;
        TracePrintW(
          5u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\renamemembername.cpp",
          0x121u,
          L"Console session id = %d, state = %d.",
          pCountb,
          State);
        break;
      }
    }
    if ( (unsigned __int8)WinStationQueryInformationW(0, SessionId, 28, &v30, 4, &v28) == 1 )
    {
      if ( v30 != 1 )
        goto LABEL_37;
      if ( WTSDisconnectSession(0, SessionId, 0) )
      {
        LODWORD(pCounta) = v17;
        TracePrintW(
          5u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\renamemembername.cpp",
          0x133u,
          L"WTSDisconnectSession succeeded for session id = %d.",
          pCounta);
        goto LABEL_37;
      }
      v20 = GetLastError();
      if ( v20 > 0 )
        v20 = (unsigned __int16)v20 | 0x80070000;
      v21 = L"WTSDisconnectSession failed = 0x%x.";
      v22 = 303;
    }
    else
    {
      v20 = GetLastError();
      if ( v20 > 0 )
        v20 = (unsigned __int16)v20 | 0x80070000;
      v21 = L"WinStationQueryInformationW failed = 0x%x.";
      v22 = 313;
    }
    LODWORD(pCounta) = v20;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\renamemembername.cpp",
      v22,
      v21,
      pCounta);
LABEL_37:
    if ( v17 == SessionId || State == WTSActive )
      goto LABEL_45;
    if ( WTSDisconnectSession(0, v17, 0) )
    {
      LODWORD(pCounta) = v17;
      v14 = L"WTSDisconnectSession succeeded for session id = %d.";
      v15 = 330;
      v16 = 5;
      goto LABEL_44;
    }
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v14 = L"WTSDisconnectSession failed = 0x%x.";
    v15 = 326;
LABEL_20:
    LODWORD(pCounta) = LastError;
    v16 = 2;
LABEL_44:
    TracePrintW(
      v16,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\renamemembername.cpp",
      v15,
      v14,
      pCounta);
LABEL_45:
    Auto<_WTS_SESSION_INFOW *,LocalWTSSessionFunctor,IServiceWinApi>::~Auto<_WTS_SESSION_INFOW *,LocalWTSSessionFunctor,IServiceWinApi>(ppSessionInfo);
  }
LABEL_46:
  v23 = v35;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v34);
  return v23;
}

```

## disassembly

```asm
0x180092c78  mov     [rsp-8+arg_0], rbx
0x180092c7d  push    rbp
0x180092c7e  push    rsi
0x180092c7f  push    rdi
0x180092c80  push    r12
0x180092c82  push    r14
0x180092c84  lea     rbp, [rsp-37h]
0x180092c89  sub     rsp, 0A0h
0x180092c90  mov     rbx, r8
0x180092c93  mov     rdi, rdx
0x180092c96  mov     rsi, rcx
0x180092c99  mov     [rbp+57h+arg_8], 0
0x180092ca0  xorps   xmm0, xmm0
0x180092ca3  movups  [rbp+57h+var_68], xmm0
0x180092ca7  movups  [rbp+57h+var_58], xmm0
0x180092cab  lea     r14, aRenamelocalcon; "RenameLocalConnectedAccount"
0x180092cb2  mov     [rbp+57h+var_48], r14
0x180092cb6  lea     rax, [rbp+57h+arg_8]
0x180092cba  mov     [rbp+57h+var_40], rax
0x180092cbe  mov     [rbp+57h+var_38], 0
0x180092cc6  mov     [rbp+57h+var_30], 0
0x180092cce  xor     r9d, r9d; unsigned int
0x180092cd1  mov     r8d, 0EFh; char *
0x180092cd7  mov     rdx, r14; char *
0x180092cda  lea     r12, aOnecoreuapDsEx_99; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180092ce1  mov     rcx, r12; this
0x180092ce4  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180092ce9  nop
0x180092cea  mov     [rbp+57h+SessionId], 0
0x180092cf1  mov     qword ptr [rbp+57h+var_68], 1
0x180092cf9  mov     dword ptr [rbp+57h+var_58+8], 2
0x180092d00  lea     rax, [rbp+57h+var_90]
0x180092d04  mov     [rsp+0C0h+pCount], rax; __int64
0x180092d09  mov     r9, rbx
0x180092d0c  xor     r8d, r8d
0x180092d0f  mov     dl, 1
0x180092d11  mov     rcx, [rdi+20h]; void *
0x180092d15  call    ?DeleteIdentityStore@@YAJPEAX_N0AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAH@Z; DeleteIdentityStore(void *,bool,void *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,int &)
0x180092d1a  mov     [rbp+57h+arg_8], eax
0x180092d1d  test    eax, eax
0x180092d1f  jns     short loc_180092D46
0x180092d21  lea     r8, aHrDeleteidenti_1; "hr = DeleteIdentityStore(renameAccountD"...
0x180092d28  mov     [rsp+0C0h+pCount], r8; char *
0x180092d2d  mov     r8d, 0F5h; unsigned int
0x180092d33  mov     r9d, eax; int
0x180092d36  mov     rdx, r14; char *
0x180092d39  mov     rcx, r12; char *
0x180092d3c  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180092d41  jmp     loc_18009302D
0x180092d46  mov     rcx, rdi; struct RenameAccountData *
0x180092d49  call    ?UpdateSamProperties@@YAJAEAURenameAccountData@@@Z; UpdateSamProperties(RenameAccountData &)
0x180092d4e  mov     [rbp+57h+arg_8], eax
0x180092d51  test    eax, eax
0x180092d53  jns     short loc_180092D69
0x180092d55  lea     rcx, aHrUpdatesampro; "hr = UpdateSamProperties(renameAccountD"...
0x180092d5c  mov     [rsp+0C0h+pCount], rcx
0x180092d61  mov     r8d, 0F6h
0x180092d67  jmp     short loc_180092D33
0x180092d69  xor     r8d, r8d; void *
0x180092d6c  lea     rdx, [rbp+57h+var_68]; struct _WLID_CONNECT_PARAM *
0x180092d70  mov     rcx, [rdi+28h]; void *
0x180092d74  call    ?HandleConnectIdentity@@YAJQEAXQEAU_WLID_CONNECT_PARAM@@PEAX@Z; HandleConnectIdentity(void * const,_WLID_CONNECT_PARAM * const,void *)
0x180092d79  mov     [rbp+57h+arg_8], eax
0x180092d7c  test    eax, eax
0x180092d7e  jns     short loc_180092D94
0x180092d80  lea     rcx, aHrHandleconnec; "hr = HandleConnectIdentity(renameAccoun"...
0x180092d87  mov     [rsp+0C0h+pCount], rcx
0x180092d8c  mov     r8d, 0F7h
0x180092d92  jmp     short loc_180092D33
0x180092d94  mov     [rbp+57h+var_90], 0
0x180092d9c  xor     edx, edx; struct ATL::CAccessToken *
0x180092d9e  lea     rcx, [rbp+57h+var_90]; this
0x180092da2  call    ?ImpersonateClient@CAutoImpersonateClient@@QEAAJPEAVCAccessToken@ATL@@@Z; CAutoImpersonateClient::ImpersonateClient(ATL::CAccessToken *)
0x180092da7  mov     [rbp+57h+arg_8], eax
0x180092daa  test    eax, eax
0x180092dac  jns     short loc_180092DDC
0x180092dae  lea     rcx, aHrClientImpers_1; "hr = client.ImpersonateClient()"
0x180092db5  mov     r8d, 0FCh; unsigned int
0x180092dbb  mov     r9d, eax; int
0x180092dbe  mov     [rsp+0C0h+pCount], rcx; char *
0x180092dc3  mov     rdx, r14; char *
0x180092dc6  mov     rcx, r12; char *
0x180092dc9  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180092dce  lea     rcx, [rbp+57h+var_90]; this
0x180092dd2  call    ??1CAutoImpersonateClient@@QEAA@XZ; CAutoImpersonateClient::~CAutoImpersonateClient(void)
0x180092dd7  jmp     loc_18009302D
0x180092ddc  lea     rdx, [rbp+57h+SessionId]; unsigned int *
0x180092de0  lea     rcx, [rbp+57h+var_90]; this
0x180092de4  call    ?GetSessionId@CAutoImpersonateClient@@QEAAJAEAK@Z; CAutoImpersonateClient::GetSessionId(ulong &)
0x180092de9  mov     [rbp+57h+arg_8], eax
0x180092dec  test    eax, eax
0x180092dee  jns     short loc_180092DFF
0x180092df0  lea     rcx, aHrClientGetses; "hr = client.GetSessionId(currentSession"...
0x180092df7  mov     r8d, 0FDh
0x180092dfd  jmp     short loc_180092DBB
0x180092dff  lea     rcx, [rbp+57h+var_90]; this
0x180092e03  call    ??1CAutoImpersonateClient@@QEAA@XZ; CAutoImpersonateClient::~CAutoImpersonateClient(void)
0x180092e08  call    IsWinStationQueryInformationWPresent
0x180092e0d  test    al, al
0x180092e0f  jz      loc_18009302D
0x180092e15  call    IsWTSFreeMemoryPresent
0x180092e1a  test    al, al
0x180092e1c  jz      loc_18009302D
0x180092e22  call    IsWTSFreeMemoryPresent
0x180092e27  test    al, al
0x180092e29  jz      loc_18009302D
0x180092e2f  mov     rax, [rsi]
0x180092e32  mov     rcx, rsi
0x180092e35  mov     rax, [rax+48h]
0x180092e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092e3e  mov     [rbp+57h+ppSessionInfo], 0
0x180092e46  mov     [rbp+57h+var_70], rax
0x180092e4a  mov     [rbp+57h+var_78], 0
0x180092e52  mov     [rbp+57h+var_88], 0
0x180092e59  mov     [rbp+57h+var_84], 0
0x180092e60  mov     dword ptr [rbp+57h+var_90], 0
0x180092e67  lea     rax, [rbp+57h+var_88]
0x180092e6b  mov     [rsp+0C0h+pCount], rax; pCount
0x180092e70  lea     r9, [rbp+57h+ppSessionInfo]; ppSessionInfo
0x180092e74  xor     edx, edx; Reserved
0x180092e76  xor     ecx, ecx; hServer
0x180092e78  lea     r8d, [rdx+1]; Version
0x180092e7c  call    cs:__imp_WTSEnumerateSessionsW
0x180092e82  test    eax, eax
0x180092e84  jnz     short loc_180092EB3
0x180092e86  call    cs:__imp_GetLastError
0x180092e8c  test    eax, eax
0x180092e8e  jle     short loc_180092E98
0x180092e90  movzx   eax, ax
0x180092e93  or      eax, 80070000h
0x180092e98  lea     r9, aWtsenumeratese_1; "WTSEnumerateSessions failed = 0x%x."
0x180092e9f  mov     r8d, 116h
0x180092ea5  mov     dword ptr [rsp+0C0h+pCount], eax
0x180092ea9  mov     ecx, 2
0x180092eae  jmp     loc_18009301C
0x180092eb3  xor     ebx, ebx
0x180092eb5  xor     r14d, r14d
0x180092eb8  xor     edi, edi
0x180092eba  cmp     edi, [rbp+57h+var_88]
0x180092ebd  jnb     short loc_180092F20
0x180092ebf  lea     rsi, [rdi+rdi*2]
0x180092ec3  mov     dword ptr [rsp+0C0h+pCount], 1; bIgnoreCase
0x180092ecb  or      r9d, 0FFFFFFFFh; cchCount2
0x180092ecf  mov     r8, [rbp+57h+ppSessionInfo]
0x180092ed3  mov     r8, [r8+rsi*8+8]; lpString2
0x180092ed8  or      edx, r9d; cchCount1
0x180092edb  lea     rcx, aConsole; "Console"
0x180092ee2  call    cs:__imp_CompareStringOrdinal
0x180092ee8  cmp     eax, 2
0x180092eeb  jz      short loc_180092EF1
0x180092eed  inc     edi
0x180092eef  jmp     short loc_180092EBA
0x180092ef1  mov     rax, [rbp+57h+ppSessionInfo]
0x180092ef5  mov     ebx, [rax+rsi*8]
0x180092ef8  mov     r14d, [rax+rsi*8+10h]
0x180092efd  mov     dword ptr [rsp+0C0h+var_98], r14d
0x180092f02  mov     dword ptr [rsp+0C0h+pCount], ebx
0x180092f06  lea     r9, aConsoleSession; "Console session id = %d, state = %d."
0x180092f0d  mov     r8d, 121h; unsigned int
0x180092f13  mov     rdx, r12; char *
0x180092f16  mov     ecx, 5; unsigned __int8
0x180092f1b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180092f20  lea     rax, [rbp+57h+var_90]
0x180092f24  mov     [rsp+0C0h+var_98], rax
0x180092f29  mov     dword ptr [rsp+0C0h+pCount], 4
0x180092f31  lea     r9, [rbp+57h+var_84]
0x180092f35  mov     r8d, 1Ch
0x180092f3b  mov     edx, [rbp+57h+SessionId]
0x180092f3e  xor     ecx, ecx
0x180092f40  call    cs:__imp_WinStationQueryInformationW
0x180092f46  mov     edi, 80070000h
0x180092f4b  cmp     al, 1
0x180092f4d  jnz     short loc_180092F9D
0x180092f4f  cmp     [rbp+57h+var_84], 1
0x180092f53  jnz     short loc_180092FCA
0x180092f55  xor     r8d, r8d; bWait
0x180092f58  mov     edx, [rbp+57h+SessionId]; SessionId
0x180092f5b  xor     ecx, ecx; hServer
0x180092f5d  call    cs:__imp_WTSDisconnectSession
0x180092f63  test    eax, eax
0x180092f65  jnz     short loc_180092F85
0x180092f67  call    cs:__imp_GetLastError
0x180092f6d  test    eax, eax
0x180092f6f  jle     short loc_180092F76
0x180092f71  movzx   eax, ax
0x180092f74  or      eax, edi
0x180092f76  lea     r9, aWtsdisconnects_1; "WTSDisconnectSession failed = 0x%x."
0x180092f7d  mov     r8d, 12Fh
0x180092f83  jmp     short loc_180092FB9
0x180092f85  mov     dword ptr [rsp+0C0h+pCount], ebx
0x180092f89  lea     r9, aWtsdisconnects_0; "WTSDisconnectSession succeeded for sess"...
0x180092f90  mov     r8d, 133h
0x180092f96  mov     ecx, 5
0x180092f9b  jmp     short loc_180092FC2
0x180092f9d  call    cs:__imp_GetLastError
0x180092fa3  test    eax, eax
0x180092fa5  jle     short loc_180092FAC
0x180092fa7  movzx   eax, ax
0x180092faa  or      eax, edi
0x180092fac  lea     r9, aWinstationquer_0; "WinStationQueryInformationW failed = 0x"...
0x180092fb3  mov     r8d, 139h; unsigned int
0x180092fb9  mov     dword ptr [rsp+0C0h+pCount], eax
0x180092fbd  mov     ecx, 2; unsigned __int8
0x180092fc2  mov     rdx, r12; char *
0x180092fc5  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180092fca  cmp     ebx, [rbp+57h+SessionId]
0x180092fcd  jz      short loc_180093024
0x180092fcf  test    r14d, r14d
0x180092fd2  jz      short loc_180093024
0x180092fd4  xor     r8d, r8d; bWait
0x180092fd7  mov     edx, ebx; SessionId
0x180092fd9  xor     ecx, ecx; hServer
0x180092fdb  call    cs:__imp_WTSDisconnectSession
0x180092fe1  test    eax, eax
0x180092fe3  jnz     short loc_180093006
0x180092fe5  call    cs:__imp_GetLastError
0x180092feb  test    eax, eax
0x180092fed  jle     short loc_180092FF4
0x180092fef  movzx   eax, ax
0x180092ff2  or      eax, edi
0x180092ff4  lea     r9, aWtsdisconnects_1; "WTSDisconnectSession failed = 0x%x."
0x180092ffb  mov     r8d, 146h
0x180093001  jmp     loc_180092EA5
0x180093006  mov     dword ptr [rsp+0C0h+pCount], ebx
0x18009300a  lea     r9, aWtsdisconnects_0; "WTSDisconnectSession succeeded for sess"...
0x180093011  mov     r8d, 14Ah; unsigned int
0x180093017  mov     ecx, 5; unsigned __int8
0x18009301c  mov     rdx, r12; char *
0x18009301f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180093024  lea     rcx, [rbp+57h+ppSessionInfo]
0x180093028  call    ??1?$Auto@PEAU_WTS_SESSION_INFOW@@VLocalWTSSessionFunctor@@VIServiceWinApi@@@@QEAA@XZ; Auto<_WTS_SESSION_INFOW *,LocalWTSSessionFunctor,IServiceWinApi>::~Auto<_WTS_SESSION_INFOW *,LocalWTSSessionFunctor,IServiceWinApi>(void)
0x18009302d  mov     ebx, [rbp+57h+arg_8]
0x180093030  lea     rcx, [rbp+57h+var_48]
0x180093034  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180093039  mov     eax, ebx
0x18009303b  mov     rbx, [rsp+0C0h+arg_0]
0x180093043  add     rsp, 0A0h
0x18009304a  pop     r14
0x18009304c  pop     r12
0x18009304e  pop     rdi
0x18009304f  pop     rsi
0x180093050  pop     rbp
0x180093051  retn
```
