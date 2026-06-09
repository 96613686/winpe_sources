# RpcOpenListener

- ea: `0x18000e240`
- end: `0x18000ea3b`
- name: `RpcOpenListener`
- size: `2043`
- prototype: `__int64 __fastcall(__int64, __int64, char **)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009b90`
- `0x18000a210`
- `0x18000e240`
- `0x18000f790`
- `0x1800119a0`
- `0x1800127b0`
- `0x180014de0`
- `0x1800321f0`
- `0x1800326dc`
- `0x1800330c4`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000e494`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000e494`
- `ntdll!RtlCaptureStackBackTrace` at `0x18000e69d`
- `ntdll!RtlCaptureStackBackTrace` at `0x18000e69d`
- `ntdll!NtQueryInformationProcess` at `0x18000e478`
- `ntdll!NtQueryInformationProcess` at `0x18000e478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e79d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e9ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e79d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e9ab`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000e437`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000e437`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000e987`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000e9a1`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000e987`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000e9a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e4c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e4c0`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000e413`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000e835`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000e413`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000e835`
- `RPCRT4!RpcRevertToSelf` at `0x18000e7e1`
- `RPCRT4!RpcRevertToSelf` at `0x18000e7e1`
- `RPCRT4!RpcImpersonateClient` at `0x18000e732`
- `RPCRT4!RpcImpersonateClient` at `0x18000e732`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18000e701`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18000e701`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000e450`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000e450`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e793`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e793`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000e2b8`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000e2b8`

## string_xrefs

- `0x18000e2a3`: `RpcOpenListener`
- `0x18000e522`: `RpcOpenListener`
- `0x18000e58d`: `RpcOpenListener`
- `0x18000e5e0`: `RpcOpenListener`
- `0x18000e911`: `RpcOpenListener`
- `0x18000e8e6`: `new CAccessTracker failed: 0x%x in %s`
- `0x18000e8dc`: `CObjectAccessTracker<class IListener,5000>::GetInstanceOfObject`
- `0x18000e75c`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18000e94e`: `%s with Trace ID 0x%x Completed`
- `0x18000e889`: `CObjectAccessTracker<class IListener,5000>::CObjectAccessTracker`
- `0x18000e752`: `CObjectAccessTracker<class IListener,5000>::GetCallerSessionId`
- `0x18000e7ba`: `CObjectAccessTracker<class IListener,5000>::GetCallerSessionId`
- `0x18000e7c4`: `GetTokenInformation failed: 0x%x in %s`
- `0x18000e329`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18000e4e9`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
__int64 __fastcall RpcOpenListener(__int64 a1, __int64 a2, char **a3)
{
  __int64 v5; // rbx
  unsigned int v6; // esi
  RPC_STATUS v7; // eax
  int v8; // edi
  HANDLE v9; // rax
  void *v10; // rsi
  NTSTATUS InformationProcess; // eax
  wchar_t *v12; // rax
  wchar_t *v13; // rax
  const char *v14; // r8
  signed int v15; // edi
  int v16; // eax
  int v17; // eax
  __int64 v18; // r14
  __int64 v19; // rdi
  char *v20; // rax
  char *v21; // rsi
  char v22; // al
  RPC_STATUS IsClientLocal; // eax
  bool v24; // sf
  RPC_STATUS v25; // eax
  signed int v26; // r14d
  signed int LastError; // eax
  signed int v28; // eax
  bool v29; // sf
  RPC_STATUS v30; // eax
  int v31; // eax
  char *v32; // r14
  DWORD ReturnLength; // [rsp+30h] [rbp-D0h] BYREF
  ULONG BackTraceHash[2]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int ClientLocalFlag; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v37; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v38; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v39; // [rsp+58h] [rbp-A8h] BYREF
  void **v40; // [rsp+60h] [rbp-A0h] BYREF
  GUID pguid; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v42[2]; // [rsp+78h] [rbp-88h] BYREF
  struct CTraceBase *v43; // [rsp+80h] [rbp-80h] BYREF
  int v44; // [rsp+88h] [rbp-78h]
  const char *v45; // [rsp+90h] [rbp-70h]
  unsigned int Pid[2]; // [rsp+98h] [rbp-68h] BYREF
  int v47; // [rsp+A0h] [rbp-60h]
  unsigned __int16 v48[262]; // [rsp+A4h] [rbp-5Ch] BYREF
  char ProcessInformation[8]; // [rsp+2B0h] [rbp+1B0h] BYREF
  wchar_t *Str; // [rsp+2B8h] [rbp+1B8h]

  v5 = 0;
  v39 = 0;
  v38 = 0;
  v37 = 0;
  v40 = &CTraceBase::`vftable';
  v42[1] = 1;
  v43 = 0;
  if ( !CTraceBase::g_bEnabled )
  {
    CoCreateGuid(&pguid);
    v42[0] = _InterlockedIncrement((volatile signed __int32 *)&CTraceBase::g_NextShortActivityID);
LABEL_13:
    v44 = 0;
    goto LABEL_14;
  }
  if ( (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "Adding trace %p, %d, %s", &v40, 1, "RpcOpenListener");
  *(_QWORD *)BackTraceHash = 0;
  if ( (int)CTraceBase::GetThreadCurrentOperationTrace((struct CTraceBase **)BackTraceHash) >= 0
    && *(_QWORD *)BackTraceHash
    && (g_DebugTraceComponent & 1) != 0 )
  {
    _DbgPrintMessage(
      2,
      "TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC",
      1);
  }
  CTraceBase::ResetThreadCurrentOperationTrace(0, 0);
  if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v43) < 0 || !v43 )
  {
    CTraceBase::ResetThreadCurrentOperationTrace((struct CTraceBase *)&v40, "RpcOpenListener");
    CTraceBase::GenerateTraceID(&pguid, v42);
    goto LABEL_13;
  }
  (*(void (__fastcall **)(struct CTraceBase *, GUID *))(*(_QWORD *)v43 + 32LL))(v43, &pguid);
  v42[0] = (*(__int64 (__fastcall **)(struct CTraceBase *))(*(_QWORD *)v43 + 24LL))(v43);
  v44 = 1;
LABEL_14:
  v40 = &CRpcCallTrace::`vftable';
  v45 = "RpcOpenListener";
  *(_QWORD *)Pid = -1;
  v47 = 0;
  memset_0(v48, 0, 0x208u);
  if ( v47 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "TRACE RPC %s with Trace ID 0x%x", v45, v42[0]);
  v6 = g_DebugTraceComponent & 1;
  *(_QWORD *)Pid = -1;
  v7 = I_RpcBindingInqLocalClientPID(0, &Pid[1]);
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  if ( v8 >= 0 )
  {
    ProcessIdToSessionId(Pid[1], Pid);
    if ( v6 )
    {
      v9 = OpenProcess(0x400u, 0, Pid[1]);
      v10 = v9;
      if ( v9 )
      {
        InformationProcess = NtQueryInformationProcess(v9, ProcessImageFileName, ProcessInformation, 0x110u, 0);
        v8 = InformationProcess | 0x10000000;
        if ( InformationProcess >= 0 )
        {
          v12 = wcsrchr(Str, 0x5Cu);
          if ( v12 )
            v13 = v12 + 1;
          else
            v13 = Str;
          StringCchCopyW(v48, 0x104u, v13);
        }
        CloseHandle(v10);
      }
    }
  }
  if ( v47 )
  {
    if ( v8 < 0 )
    {
      if ( (g_DebugTraceComponent & 1) != 0 )
        _DbgPrintMessage(2, "RPC Caller: Unknown");
    }
    else if ( (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(2, "RPC Caller: PID %d, SessID %d, Process Name: <%S>", Pid[1], Pid[0], v48);
    }
  }
  if ( !a3 )
  {
    v14 = "phListener";
LABEL_36:
    _DbgPrintMessage(8, "Missing paramter %s in %s", v14, "RpcOpenListener");
    v15 = -2147024809;
    goto LABEL_88;
  }
  if ( !a2 )
  {
    v14 = "szListenerName";
    goto LABEL_36;
  }
  if ( qword_180128DF0 )
  {
    v5 = qword_180128DF0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_180128DF0 + 8LL))(qword_180128DF0);
  }
  v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 216LL))(v5, &v37);
  v15 = v16;
  if ( v16 < 0 )
  {
    _DbgPrintMessage(8, "GetSessionCallCounter failed: 0x%x in %s", v16, "RpcOpenListener");
    goto LABEL_88;
  }
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 120LL))(v5, &v39);
  v17 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v39 + 48LL))(v39, a2, &v38);
  v15 = v17;
  if ( v17 < 0 )
  {
    _DbgPrintMessage(8, "List->GetListenerByName failed: 0x%x in %s", v17, "RpcOpenListener");
    goto LABEL_88;
  }
  v18 = v37;
  v19 = v38;
  v20 = (char *)operator new(0x658u, (const struct std::nothrow_t *)std::nothrow);
  v21 = v20;
  if ( !v20 )
  {
    v15 = -2147024882;
    v21 = 0;
    goto LABEL_82;
  }
  *(_QWORD *)v20 = &CTSPrivateObject<IUnknown>::`vftable';
  *((_QWORD *)v20 + 2) = "LISTENERTRACKER";
  *((_DWORD *)v20 + 2) = 0;
  *((_DWORD *)v20 + 3) = 1;
  *((_QWORD *)v20 + 198) = v20 + 1576;
  *((_QWORD *)v20 + 197) = v20 + 1576;
  AddTrackingObject((struct _LIST_ENTRY *)(v20 + 1576));
  *((_QWORD *)v21 + 3) = 0;
  *((_DWORD *)v21 + 8) = 0;
  BackTraceHash[0] = 0;
  v22 = _InterlockedIncrement((volatile signed __int32 *)v21 + 8);
  if ( g_bCaptureObjectStackTrace == 1 )
    RtlCaptureStackBackTrace(1u, 6u, (PVOID *)&v21[48 * (v22 & 0x1F) + 40], BackTraceHash);
  *(_QWORD *)v21 = &CObjectAccessTracker<IListener,5000>::`vftable';
  *((_QWORD *)v21 + 199) = v19;
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
  *((_QWORD *)v21 + 200) = -1;
  *((_QWORD *)v21 + 201) = v18;
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
  *((_QWORD *)v21 + 202) = 0;
  ClientLocalFlag = 0;
  IsClientLocal = I_RpcBindingIsClientLocal(0, &ClientLocalFlag);
  v24 = IsClientLocal < 0;
  if ( IsClientLocal > 0 )
    v24 = 1;
  if ( v24 || !ClientLocalFlag )
  {
LABEL_77:
    v31 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)v21 + 201) + 24LL))(
            *((_QWORD *)v21 + 201),
            5000,
            v21 + 1616);
    v15 = v31;
    if ( v31 < 0 )
      _DbgPrintMessage(
        8,
        "m_pCientTracker->TrackCaller failed: 0x%x in %s",
        (unsigned int)v31,
        "CObjectAccessTracker<class IListener,5000>::CObjectAccessTracker");
    goto LABEL_79;
  }
  BackTraceHash[0] = 0;
  v25 = RpcImpersonateClient(0);
  v15 = v25;
  ReturnLength = v25;
  if ( v25 > 0 )
    v15 = (unsigned __int16)v25 | 0x80070000;
  v26 = v15;
  if ( v15 < 0 )
  {
    _DbgPrintMessage(
      8,
      "RpcImpersonateClient failed: 0x%x in %s",
      v15,
      "CObjectAccessTracker<class IListener,5000>::GetCallerSessionId");
LABEL_71:
    _DbgPrintMessage(
      8,
      "GetCallerSessionId failed: 0x%x in %s",
      (unsigned int)v26,
      "CObjectAccessTracker<class IListener,5000>::CObjectAccessTracker");
    goto LABEL_79;
  }
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFBLL, TokenSessionId, BackTraceHash, 4u, &ReturnLength) )
    goto LABEL_65;
  LastError = GetLastError();
  v26 = LastError;
  if ( LastError > 0 )
    v26 = (unsigned __int16)LastError | 0x80070000;
  if ( v26 >= 0 )
LABEL_65:
    *((_DWORD *)v21 + 401) = BackTraceHash[0];
  else
    _DbgPrintMessage(
      8,
      "GetTokenInformation failed: 0x%x in %s",
      v26,
      "CObjectAccessTracker<class IListener,5000>::GetCallerSessionId");
  v28 = RpcRevertToSelf();
  ReturnLength = v28;
  v29 = v28 < 0;
  if ( v28 > 0 )
  {
    v28 = (unsigned __int16)v28 | 0x80070000;
    v29 = v28 < 0;
  }
  if ( v29 )
    _DbgPrintMessage(8, "RpcRevertToSelf failed 0x%08x", v28);
  v15 = v26;
  if ( v26 < 0 )
    goto LABEL_71;
  if ( *((_DWORD *)v21 + 401) )
  {
    v30 = I_RpcBindingInqLocalClientPID(0, (unsigned int *)v21 + 400);
    v15 = v30;
    if ( v30 > 0 )
      v15 = (unsigned __int16)v30 | 0x80070000;
    if ( v15 < 0 )
    {
      _DbgPrintMessage(
        8,
        "I_RpcBindingInqLocalClientPID failed: 0x%x in %s",
        (unsigned int)v15,
        "CObjectAccessTracker<class IListener,5000>::CObjectAccessTracker");
      goto LABEL_79;
    }
    goto LABEL_77;
  }
LABEL_79:
  (*(void (__fastcall **)(char *))(*(_QWORD *)v21 + 8LL))(v21);
  if ( v15 < 0 )
  {
LABEL_82:
    v32 = 0;
    _DbgPrintMessage(
      8,
      "new CAccessTracker failed: 0x%x in %s",
      v15,
      "CObjectAccessTracker<class IListener,5000>::GetInstanceOfObject");
    goto LABEL_83;
  }
  v32 = v21;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v21 + 8LL))(v21);
LABEL_83:
  if ( v21 )
    (*(void (__fastcall **)(char *))(*(_QWORD *)v21 + 16LL))(v21);
  if ( v15 >= 0 )
    *a3 = v32;
  else
    _DbgPrintMessage(8, "LISTENERTRACKER::GetInstanceOfObject failed: 0x%x in %s", v15, "RpcOpenListener");
LABEL_88:
  v40 = &CRpcCallTrace::`vftable';
  if ( v47 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "%s with Trace ID 0x%x Completed", v45, v42[0]);
  v40 = &CTraceBase::`vftable';
  if ( CTraceBase::g_bEnabled && !v44 && CTraceBase::g_TLSIndex != -1 )
  {
    if ( TlsSetValue(CTraceBase::g_TLSIndex, 0) )
    {
      if ( TlsSetValue(CTraceBase::g_CreatorFunctionTLSIndex, 0) )
        goto LABEL_98;
    }
    else
    {
      GetLastError();
    }
    GetLastError();
  }
LABEL_98:
  v43 = 0;
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18000e240  mov     [rsp-8+arg_0], rbx
0x18000e245  push    rbp
0x18000e246  push    rsi
0x18000e247  push    rdi
0x18000e248  push    r12
0x18000e24a  push    r13
0x18000e24c  push    r14
0x18000e24e  push    r15
0x18000e250  lea     rbp, [rsp-2D0h]
0x18000e258  sub     rsp, 3D0h
0x18000e25f  mov     rax, cs:__security_cookie
0x18000e266  xor     rax, rsp
0x18000e269  mov     [rbp+300h+var_40], rax
0x18000e270  mov     r15, r8
0x18000e273  mov     r14, rdx
0x18000e276  xor     r12d, r12d
0x18000e279  mov     ebx, r12d
0x18000e27c  mov     [rsp+400h+var_3A8], r12
0x18000e281  mov     [rsp+400h+var_3B0], r12
0x18000e286  mov     [rsp+400h+var_3B8], r12
0x18000e28b  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000e292  mov     [rsp+400h+var_3A0], rax
0x18000e297  mov     [rsp+400h+var_384], 1
0x18000e29f  mov     [rbp+300h+var_380], r12
0x18000e2a3  lea     rdi, aRpcopenlistene; "RpcOpenListener"
0x18000e2aa  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r12d; int CTraceBase::g_bEnabled
0x18000e2b1  jnz     short loc_18000E2D6
0x18000e2b3  lea     rcx, [rsp+400h+pguid]; pguid
0x18000e2b8  call    cs:__imp_CoCreateGuid
0x18000e2be  mov     eax, 1
0x18000e2c3  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x18000e2cb  inc     eax
0x18000e2cd  mov     [rsp+400h+var_388], eax
0x18000e2d1  jmp     loc_18000E3A3
0x18000e2d6  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000e2dd  jz      short loc_18000E300
0x18000e2df  mov     [rsp+400h+ReturnLength], rdi
0x18000e2e4  mov     r9d, 1
0x18000e2ea  lea     r8, [rsp+400h+var_3A0]
0x18000e2ef  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x18000e2f6  mov     ecx, 2; int
0x18000e2fb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e300  mov     qword ptr [rsp+400h+BackTraceHash], r12
0x18000e305  lea     rcx, [rsp+400h+BackTraceHash]; struct CTraceBase **
0x18000e30a  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000e30f  test    eax, eax
0x18000e311  js      short loc_18000E33A
0x18000e313  cmp     qword ptr [rsp+400h+BackTraceHash], rbx
0x18000e318  jz      short loc_18000E33A
0x18000e31a  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000e321  jz      short loc_18000E33A
0x18000e323  mov     r8d, 1
0x18000e329  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x18000e330  mov     ecx, 2; int
0x18000e335  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e33a  xor     edx, edx; char *
0x18000e33c  xor     ecx, ecx; lpTlsValue
0x18000e33e  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000e343  lea     rcx, [rbp+300h+var_380]; struct CTraceBase **
0x18000e347  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000e34c  test    eax, eax
0x18000e34e  js      short loc_18000E387
0x18000e350  mov     rcx, [rbp+300h+var_380]
0x18000e354  test    rcx, rcx
0x18000e357  jz      short loc_18000E387
0x18000e359  mov     rax, [rcx]
0x18000e35c  lea     rdx, [rsp+400h+pguid]
0x18000e361  mov     rax, [rax+20h]
0x18000e365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e36a  mov     rcx, [rbp+300h+var_380]
0x18000e36e  mov     rax, [rcx]
0x18000e371  mov     rax, [rax+18h]
0x18000e375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e37a  mov     [rsp+400h+var_388], eax
0x18000e37e  mov     [rbp+300h+var_378], 1
0x18000e385  jmp     short loc_18000E3A7
0x18000e387  mov     rdx, rdi; char *
0x18000e38a  lea     rcx, [rsp+400h+var_3A0]; lpTlsValue
0x18000e38f  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000e394  lea     rdx, [rsp+400h+var_388]; unsigned int *
0x18000e399  lea     rcx, [rsp+400h+pguid]; struct _GUID *
0x18000e39e  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x18000e3a3  mov     [rbp+300h+var_378], r12d
0x18000e3a7  lea     r13, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000e3ae  mov     [rsp+400h+var_3A0], r13
0x18000e3b3  mov     [rbp+300h+var_370], rdi
0x18000e3b7  mov     qword ptr [rbp+300h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000e3bf  mov     [rbp+300h+var_360], r12d
0x18000e3c3  xor     edx, edx; Val
0x18000e3c5  mov     r8d, 208h; Size
0x18000e3cb  lea     rcx, [rbp+300h+var_35C]; void *
0x18000e3cf  call    memset_0
0x18000e3d4  cmp     [rbp+300h+var_360], ebx
0x18000e3d7  jz      short loc_18000E3FC
0x18000e3d9  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000e3e0  jz      short loc_18000E3FC
0x18000e3e2  mov     r9d, [rsp+400h+var_388]
0x18000e3e7  mov     r8, [rbp+300h+var_370]
0x18000e3eb  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x18000e3f2  mov     ecx, 2; int
0x18000e3f7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e3fc  mov     esi, cs:?g_DebugTraceComponent@@3KA; ulong g_DebugTraceComponent
0x18000e402  and     esi, 1
0x18000e405  mov     qword ptr [rbp+300h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000e40d  lea     rdx, [rbp+300h+Pid+4]; Pid
0x18000e411  xor     ecx, ecx; Binding
0x18000e413  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000e419  mov     edi, eax
0x18000e41b  test    eax, eax
0x18000e41d  jle     short loc_18000E428
0x18000e41f  movzx   edi, ax
0x18000e422  or      edi, 80070000h
0x18000e428  test    edi, edi
0x18000e42a  js      loc_18000E4C6
0x18000e430  lea     rdx, [rbp+300h+Pid]; pSessionId
0x18000e434  mov     ecx, [rbp+300h+Pid+4]; dwProcessId
0x18000e437  call    cs:__imp_ProcessIdToSessionId
0x18000e43d  test    esi, esi
0x18000e43f  jz      loc_18000E4C6
0x18000e445  mov     r8d, [rbp+300h+Pid+4]; dwProcessId
0x18000e449  xor     edx, edx; bInheritHandle
0x18000e44b  mov     ecx, 400h; dwDesiredAccess
0x18000e450  call    cs:__imp_OpenProcess
0x18000e456  mov     rsi, rax
0x18000e459  test    rax, rax
0x18000e45c  jz      short loc_18000E4C6
0x18000e45e  mov     [rsp+400h+ReturnLength], r12; ReturnLength
0x18000e463  mov     r9d, 110h; ProcessInformationLength
0x18000e469  lea     r8, [rbp+300h+ProcessInformation]; ProcessInformation
0x18000e470  mov     edx, 1Bh; ProcessInformationClass
0x18000e475  mov     rcx, rax; ProcessHandle
0x18000e478  call    cs:__imp_NtQueryInformationProcess
0x18000e47e  mov     edi, eax
0x18000e480  or      edi, 10000000h
0x18000e486  jl      short loc_18000E4BD
0x18000e488  mov     edx, 5Ch ; '\'; Ch
0x18000e48d  mov     rcx, [rbp+300h+Str]; Str
0x18000e494  call    cs:__imp_wcsrchr
0x18000e49a  test    rax, rax
0x18000e49d  jnz     short loc_18000E4A8
0x18000e49f  mov     rax, [rbp+300h+Str]
0x18000e4a6  jmp     short loc_18000E4AC
0x18000e4a8  add     rax, 2
0x18000e4ac  mov     r8, rax; unsigned __int16 *
0x18000e4af  mov     edx, 104h; unsigned __int64
0x18000e4b4  lea     rcx, [rbp+300h+var_35C]; unsigned __int16 *
0x18000e4b8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e4bd  mov     rcx, rsi; hObject
0x18000e4c0  call    cs:__imp_CloseHandle
0x18000e4c6  cmp     [rbp+300h+var_360], ebx
0x18000e4c9  jz      short loc_18000E516
0x18000e4cb  test    edi, edi
0x18000e4cd  js      short loc_18000E4FC
0x18000e4cf  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000e4d6  jz      short loc_18000E516
0x18000e4d8  lea     rax, [rbp+300h+var_35C]
0x18000e4dc  mov     [rsp+400h+ReturnLength], rax
0x18000e4e1  mov     r9d, [rbp+300h+Pid]
0x18000e4e5  mov     r8d, [rbp+300h+Pid+4]
0x18000e4e9  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x18000e4f0  mov     ecx, 2; int
0x18000e4f5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e4fa  jmp     short loc_18000E516
0x18000e4fc  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000e503  jz      short loc_18000E516
0x18000e505  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x18000e50c  mov     ecx, 2; int
0x18000e511  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e516  test    r15, r15
0x18000e519  jnz     short loc_18000E544
0x18000e51b  lea     r8, aPhlistener; "phListener"
0x18000e522  lea     r9, aRpcopenlistene; "RpcOpenListener"
0x18000e529  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18000e530  mov     ecx, 8; int
0x18000e535  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e53a  mov     edi, 80070057h
0x18000e53f  jmp     loc_18000E931
0x18000e544  test    r14, r14
0x18000e547  jnz     short loc_18000E552
0x18000e549  lea     r8, aSzlistenername; "szListenerName"
0x18000e550  jmp     short loc_18000E522
0x18000e552  mov     rax, cs:qword_180128DF0
0x18000e559  test    rax, rax
0x18000e55c  jz      short loc_18000E570
0x18000e55e  mov     rbx, rax
0x18000e561  mov     rax, [rax]
0x18000e564  mov     rcx, rbx
0x18000e567  mov     rax, [rax+8]
0x18000e56b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e570  mov     rax, [rbx]
0x18000e573  lea     rdx, [rsp+400h+var_3B8]
0x18000e578  mov     rcx, rbx
0x18000e57b  mov     rax, [rax+0D8h]
0x18000e582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e587  mov     edi, eax
0x18000e589  test    eax, eax
0x18000e58b  jns     short loc_18000E5AD
0x18000e58d  lea     r9, aRpcopenlistene; "RpcOpenListener"
0x18000e594  mov     r8d, eax
0x18000e597  lea     rdx, aGetsessioncall; "GetSessionCallCounter failed: 0x%x in %"...
0x18000e59e  mov     ecx, 8; int
0x18000e5a3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e5a8  jmp     loc_18000E931
0x18000e5ad  mov     rax, [rbx]
0x18000e5b0  lea     rdx, [rsp+400h+var_3A8]
0x18000e5b5  mov     rcx, rbx
0x18000e5b8  mov     rax, [rax+78h]
0x18000e5bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5c1  mov     rcx, [rsp+400h+var_3A8]
0x18000e5c6  mov     rax, [rcx]
0x18000e5c9  lea     r8, [rsp+400h+var_3B0]
0x18000e5ce  mov     rdx, r14
0x18000e5d1  mov     rax, [rax+30h]
0x18000e5d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5da  mov     edi, eax
0x18000e5dc  test    eax, eax
0x18000e5de  jns     short loc_18000E600
0x18000e5e0  lea     r9, aRpcopenlistene; "RpcOpenListener"
0x18000e5e7  mov     r8d, eax
0x18000e5ea  lea     rdx, aListGetlistene; "List->GetListenerByName failed: 0x%x in"...
0x18000e5f1  mov     ecx, 8; int
0x18000e5f6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e5fb  jmp     loc_18000E931
0x18000e600  mov     r14, [rsp+400h+var_3B8]
0x18000e605  mov     rdi, [rsp+400h+var_3B0]
0x18000e60a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e611  mov     ecx, 658h; unsigned __int64
0x18000e616  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e61b  mov     rsi, rax
0x18000e61e  test    rax, rax
0x18000e621  jz      loc_18000E8D1
0x18000e627  lea     rax, ??_7?$CTSPrivateObject@UIUnknown@@@@6B@; const CTSPrivateObject<IUnknown>::`vftable'
0x18000e62e  mov     [rsi], rax
0x18000e631  lea     rax, aListenertracke; "LISTENERTRACKER"
0x18000e638  mov     [rsi+10h], rax
0x18000e63c  mov     [rsi+8], r12d
0x18000e640  mov     dword ptr [rsi+0Ch], 1
0x18000e647  lea     rcx, [rsi+628h]; struct _LIST_ENTRY *
0x18000e64e  mov     [rcx+8], rcx
0x18000e652  mov     [rcx], rcx
0x18000e655  call    ?AddTrackingObject@@YAXPEAU_LIST_ENTRY@@@Z; AddTrackingObject(_LIST_ENTRY *)
0x18000e65a  mov     [rsi+18h], r12
0x18000e65e  mov     [rsi+20h], r12d
0x18000e662  mov     [rsp+400h+BackTraceHash], r12d
0x18000e667  mov     eax, 1
0x18000e66c  lock xadd [rsi+20h], eax
0x18000e671  inc     eax
0x18000e673  cmp     cs:?g_bCaptureObjectStackTrace@@3HA, 1; int g_bCaptureObjectStackTrace
0x18000e67a  jnz     short loc_18000E6A3
0x18000e67c  and     eax, 1Fh
0x18000e67f  lea     r8, [rax+rax*2]
0x18000e683  shl     r8, 4
0x18000e687  add     r8, 28h ; '('
0x18000e68b  add     r8, rsi; BackTrace
0x18000e68e  lea     r9, [rsp+400h+BackTraceHash]; BackTraceHash
0x18000e693  mov     edx, 6; FramesToCapture
0x18000e698  mov     ecx, 1; FramesToSkip
0x18000e69d  call    cs:__imp_RtlCaptureStackBackTrace
0x18000e6a3  lea     rax, ??_7?$CObjectAccessTracker@VIListener@@$0BDII@@@6B@; const CObjectAccessTracker<IListener,5000>::`vftable'
0x18000e6aa  mov     [rsi], rax
0x18000e6ad  mov     [rsi+638h], rdi
0x18000e6b4  test    rdi, rdi
0x18000e6b7  jz      short loc_18000E6C8
0x18000e6b9  mov     rax, [rdi]
0x18000e6bc  mov     rcx, rdi
0x18000e6bf  mov     rax, [rax+8]
0x18000e6c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6c8  mov     qword ptr [rsi+640h], 0FFFFFFFFFFFFFFFFh
0x18000e6d3  mov     [rsi+648h], r14
0x18000e6da  test    r14, r14
0x18000e6dd  jz      short loc_18000E6EE
0x18000e6df  mov     rax, [r14]
0x18000e6e2  mov     rcx, r14
0x18000e6e5  mov     rax, [rax+8]
0x18000e6e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6ee  mov     [rsi+650h], r12
0x18000e6f5  mov     [rsp+400h+ClientLocalFlag], r12d
0x18000e6fa  lea     rdx, [rsp+400h+ClientLocalFlag]; ClientLocalFlag
0x18000e6ff  xor     ecx, ecx; BindingHandle
0x18000e701  call    cs:__imp_I_RpcBindingIsClientLocal
0x18000e707  test    eax, eax
0x18000e709  jle     short loc_18000E715
0x18000e70b  movzx   eax, ax
0x18000e70e  or      eax, 80070000h
0x18000e713  test    eax, eax
0x18000e715  js      loc_18000E85A
0x18000e71b  cmp     [rsp+400h+ClientLocalFlag], r12d
0x18000e720  jz      loc_18000E85A
0x18000e726  mov     [rsp+400h+var_3D0], r12d
0x18000e72b  mov     [rsp+400h+BackTraceHash], r12d
0x18000e730  xor     ecx, ecx; BindingHandle
0x18000e732  call    cs:__imp_RpcImpersonateClient
0x18000e738  mov     edi, eax
0x18000e73a  mov     [rsp+400h+var_3D0], eax
0x18000e73e  test    eax, eax
0x18000e740  jle     short loc_18000E74B
0x18000e742  movzx   edi, ax
0x18000e745  or      edi, 80070000h
0x18000e74b  mov     r14d, edi
0x18000e74e  test    edi, edi
  ... truncated ...
```
