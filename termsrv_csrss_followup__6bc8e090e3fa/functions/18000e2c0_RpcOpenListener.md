# RpcOpenListener

- ea: `0x18000e2c0`
- end: `0x18000eb28`
- name: `RpcOpenListener`
- size: `2152`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009220`
- `0x180009940`
- `0x18000e2c0`
- `0x18000faf0`
- `0x180012070`
- `0x180012d10`
- `0x1800154a0`
- `0x180033f60`
- `0x18003444c`
- `0x180034e64`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000e532`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000e532`
- `ntdll!RtlCaptureStackBackTrace` at `0x18000e747`
- `ntdll!RtlCaptureStackBackTrace` at `0x18000e747`
- `ntdll!NtQueryInformationProcess` at `0x18000e510`
- `ntdll!NtQueryInformationProcess` at `0x18000e510`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e85f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e85f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea91`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000e4c3`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000e4c3`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000ea5b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000ea81`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000ea5b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000ea81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e564`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e564`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000e499`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000e903`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000e499`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000e903`
- `RPCRT4!RpcRevertToSelf` at `0x18000e8a9`
- `RPCRT4!RpcRevertToSelf` at `0x18000e8a9`
- `RPCRT4!RpcImpersonateClient` at `0x18000e7e8`
- `RPCRT4!RpcImpersonateClient` at `0x18000e7e8`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18000e7b1`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18000e7b1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000e4e2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000e4e2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e84f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e84f`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000e338`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000e338`

## string_xrefs

- `0x18000e323`: `RpcOpenListener`
- `0x18000e5cc`: `RpcOpenListener`
- `0x18000e637`: `RpcOpenListener`
- `0x18000e68a`: `RpcOpenListener`
- `0x18000e9e5`: `RpcOpenListener`
- `0x18000e9ba`: `new CAccessTracker failed: 0x%x in %s`
- `0x18000e9b0`: `CObjectAccessTracker<class IListener,5000>::GetInstanceOfObject`
- `0x18000e818`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18000ea22`: `%s with Trace ID 0x%x Completed`
- `0x18000e95d`: `CObjectAccessTracker<class IListener,5000>::CObjectAccessTracker`
- `0x18000e80e`: `CObjectAccessTracker<class IListener,5000>::GetCallerSessionId`
- `0x18000e882`: `CObjectAccessTracker<class IListener,5000>::GetCallerSessionId`
- `0x18000e88c`: `GetTokenInformation failed: 0x%x in %s`
- `0x18000e3af`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18000e593`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  if ( qword_18012EDF8 )
  {
    v5 = qword_18012EDF8;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_18012EDF8 + 8LL))(qword_18012EDF8);
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
0x18000e2c0  mov     [rsp-8+arg_0], rbx
0x18000e2c5  push    rbp
0x18000e2c6  push    rsi
0x18000e2c7  push    rdi
0x18000e2c8  push    r12
0x18000e2ca  push    r13
0x18000e2cc  push    r14
0x18000e2ce  push    r15
0x18000e2d0  lea     rbp, [rsp-2D0h]
0x18000e2d8  sub     rsp, 3D0h
0x18000e2df  mov     rax, cs:__security_cookie
0x18000e2e6  xor     rax, rsp
0x18000e2e9  mov     [rbp+300h+var_40], rax
0x18000e2f0  mov     r15, r8
0x18000e2f3  mov     r14, rdx
0x18000e2f6  xor     r12d, r12d
0x18000e2f9  mov     ebx, r12d
0x18000e2fc  mov     [rsp+400h+var_3A8], r12
0x18000e301  mov     [rsp+400h+var_3B0], r12
0x18000e306  mov     [rsp+400h+var_3B8], r12
0x18000e30b  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000e312  mov     [rsp+400h+var_3A0], rax
0x18000e317  mov     [rsp+400h+var_384], 1
0x18000e31f  mov     [rbp+300h+var_380], r12
0x18000e323  lea     rdi, aRpcopenlistene; "RpcOpenListener"
0x18000e32a  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r12d; int CTraceBase::g_bEnabled
0x18000e331  jnz     short loc_18000E35C
0x18000e333  lea     rcx, [rsp+400h+pguid]; pguid
0x18000e338  call    cs:__imp_CoCreateGuid
0x18000e33f  nop     dword ptr [rax+rax+00h]
0x18000e344  mov     eax, 1
0x18000e349  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x18000e351  inc     eax
0x18000e353  mov     [rsp+400h+var_388], eax
0x18000e357  jmp     loc_18000E429
0x18000e35c  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000e363  jz      short loc_18000E386
0x18000e365  mov     [rsp+400h+ReturnLength], rdi
0x18000e36a  mov     r9d, 1
0x18000e370  lea     r8, [rsp+400h+var_3A0]
0x18000e375  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x18000e37c  mov     ecx, 2; int
0x18000e381  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e386  mov     qword ptr [rsp+400h+BackTraceHash], r12
0x18000e38b  lea     rcx, [rsp+400h+BackTraceHash]; struct CTraceBase **
0x18000e390  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000e395  test    eax, eax
0x18000e397  js      short loc_18000E3C0
0x18000e399  cmp     qword ptr [rsp+400h+BackTraceHash], rbx
0x18000e39e  jz      short loc_18000E3C0
0x18000e3a0  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000e3a7  jz      short loc_18000E3C0
0x18000e3a9  mov     r8d, 1
0x18000e3af  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x18000e3b6  mov     ecx, 2; int
0x18000e3bb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e3c0  xor     edx, edx; char *
0x18000e3c2  xor     ecx, ecx; lpTlsValue
0x18000e3c4  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000e3c9  lea     rcx, [rbp+300h+var_380]; struct CTraceBase **
0x18000e3cd  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000e3d2  test    eax, eax
0x18000e3d4  js      short loc_18000E40D
0x18000e3d6  mov     rcx, [rbp+300h+var_380]
0x18000e3da  test    rcx, rcx
0x18000e3dd  jz      short loc_18000E40D
0x18000e3df  mov     rax, [rcx]
0x18000e3e2  lea     rdx, [rsp+400h+pguid]
0x18000e3e7  mov     rax, [rax+20h]
0x18000e3eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3f0  mov     rcx, [rbp+300h+var_380]
0x18000e3f4  mov     rax, [rcx]
0x18000e3f7  mov     rax, [rax+18h]
0x18000e3fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e400  mov     [rsp+400h+var_388], eax
0x18000e404  mov     [rbp+300h+var_378], 1
0x18000e40b  jmp     short loc_18000E42D
0x18000e40d  mov     rdx, rdi; char *
0x18000e410  lea     rcx, [rsp+400h+var_3A0]; lpTlsValue
0x18000e415  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000e41a  lea     rdx, [rsp+400h+var_388]; unsigned int *
0x18000e41f  lea     rcx, [rsp+400h+pguid]; struct _GUID *
0x18000e424  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x18000e429  mov     [rbp+300h+var_378], r12d
0x18000e42d  lea     r13, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000e434  mov     [rsp+400h+var_3A0], r13
0x18000e439  mov     [rbp+300h+var_370], rdi
0x18000e43d  mov     qword ptr [rbp+300h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000e445  mov     [rbp+300h+var_360], r12d
0x18000e449  xor     edx, edx; Val
0x18000e44b  mov     r8d, 208h; Size
0x18000e451  lea     rcx, [rbp+300h+var_35C]; void *
0x18000e455  call    memset_0
0x18000e45a  cmp     [rbp+300h+var_360], ebx
0x18000e45d  jz      short loc_18000E482
0x18000e45f  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000e466  jz      short loc_18000E482
0x18000e468  mov     r9d, [rsp+400h+var_388]
0x18000e46d  mov     r8, [rbp+300h+var_370]
0x18000e471  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x18000e478  mov     ecx, 2; int
0x18000e47d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e482  mov     esi, cs:?g_DebugTraceComponent@@3KA; ulong g_DebugTraceComponent
0x18000e488  and     esi, 1
0x18000e48b  mov     qword ptr [rbp+300h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000e493  lea     rdx, [rbp+300h+Pid+4]; Pid
0x18000e497  xor     ecx, ecx; Binding
0x18000e499  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000e4a0  nop     dword ptr [rax+rax+00h]
0x18000e4a5  mov     edi, eax
0x18000e4a7  test    eax, eax
0x18000e4a9  jle     short loc_18000E4B4
0x18000e4ab  movzx   edi, ax
0x18000e4ae  or      edi, 80070000h
0x18000e4b4  test    edi, edi
0x18000e4b6  js      loc_18000E570
0x18000e4bc  lea     rdx, [rbp+300h+Pid]; pSessionId
0x18000e4c0  mov     ecx, [rbp+300h+Pid+4]; dwProcessId
0x18000e4c3  call    cs:__imp_ProcessIdToSessionId
0x18000e4ca  nop     dword ptr [rax+rax+00h]
0x18000e4cf  test    esi, esi
0x18000e4d1  jz      loc_18000E570
0x18000e4d7  mov     r8d, [rbp+300h+Pid+4]; dwProcessId
0x18000e4db  xor     edx, edx; bInheritHandle
0x18000e4dd  mov     ecx, 400h; dwDesiredAccess
0x18000e4e2  call    cs:__imp_OpenProcess
0x18000e4e9  nop     dword ptr [rax+rax+00h]
0x18000e4ee  mov     rsi, rax
0x18000e4f1  test    rax, rax
0x18000e4f4  jz      short loc_18000E570
0x18000e4f6  mov     [rsp+400h+ReturnLength], r12; ReturnLength
0x18000e4fb  mov     r9d, 110h; ProcessInformationLength
0x18000e501  lea     r8, [rbp+300h+ProcessInformation]; ProcessInformation
0x18000e508  mov     edx, 1Bh; ProcessInformationClass
0x18000e50d  mov     rcx, rax; ProcessHandle
0x18000e510  call    cs:__imp_NtQueryInformationProcess
0x18000e517  nop     dword ptr [rax+rax+00h]
0x18000e51c  mov     edi, eax
0x18000e51e  or      edi, 10000000h
0x18000e524  jl      short loc_18000E561
0x18000e526  mov     edx, 5Ch ; '\'; Ch
0x18000e52b  mov     rcx, [rbp+300h+Str]; Str
0x18000e532  call    cs:__imp_wcsrchr
0x18000e539  nop     dword ptr [rax+rax+00h]
0x18000e53e  test    rax, rax
0x18000e541  jnz     short loc_18000E54C
0x18000e543  mov     rax, [rbp+300h+Str]
0x18000e54a  jmp     short loc_18000E550
0x18000e54c  add     rax, 2
0x18000e550  mov     r8, rax; unsigned __int16 *
0x18000e553  mov     edx, 104h; unsigned __int64
0x18000e558  lea     rcx, [rbp+300h+var_35C]; unsigned __int16 *
0x18000e55c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e561  mov     rcx, rsi; hObject
0x18000e564  call    cs:__imp_CloseHandle
0x18000e56b  nop     dword ptr [rax+rax+00h]
0x18000e570  cmp     [rbp+300h+var_360], ebx
0x18000e573  jz      short loc_18000E5C0
0x18000e575  test    edi, edi
0x18000e577  js      short loc_18000E5A6
0x18000e579  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000e580  jz      short loc_18000E5C0
0x18000e582  lea     rax, [rbp+300h+var_35C]
0x18000e586  mov     [rsp+400h+ReturnLength], rax
0x18000e58b  mov     r9d, [rbp+300h+Pid]
0x18000e58f  mov     r8d, [rbp+300h+Pid+4]
0x18000e593  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x18000e59a  mov     ecx, 2; int
0x18000e59f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e5a4  jmp     short loc_18000E5C0
0x18000e5a6  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000e5ad  jz      short loc_18000E5C0
0x18000e5af  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x18000e5b6  mov     ecx, 2; int
0x18000e5bb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e5c0  test    r15, r15
0x18000e5c3  jnz     short loc_18000E5EE
0x18000e5c5  lea     r8, aPhlistener; "phListener"
0x18000e5cc  lea     r9, aRpcopenlistene; "RpcOpenListener"
0x18000e5d3  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18000e5da  mov     ecx, 8; int
0x18000e5df  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e5e4  mov     edi, 80070057h
0x18000e5e9  jmp     loc_18000EA05
0x18000e5ee  test    r14, r14
0x18000e5f1  jnz     short loc_18000E5FC
0x18000e5f3  lea     r8, aSzlistenername; "szListenerName"
0x18000e5fa  jmp     short loc_18000E5CC
0x18000e5fc  mov     rax, cs:qword_18012EDF8
0x18000e603  test    rax, rax
0x18000e606  jz      short loc_18000E61A
0x18000e608  mov     rbx, rax
0x18000e60b  mov     rax, [rax]
0x18000e60e  mov     rcx, rbx
0x18000e611  mov     rax, [rax+8]
0x18000e615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e61a  mov     rax, [rbx]
0x18000e61d  lea     rdx, [rsp+400h+var_3B8]
0x18000e622  mov     rcx, rbx
0x18000e625  mov     rax, [rax+0D8h]
0x18000e62c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e631  mov     edi, eax
0x18000e633  test    eax, eax
0x18000e635  jns     short loc_18000E657
0x18000e637  lea     r9, aRpcopenlistene; "RpcOpenListener"
0x18000e63e  mov     r8d, eax
0x18000e641  lea     rdx, aGetsessioncall; "GetSessionCallCounter failed: 0x%x in %"...
0x18000e648  mov     ecx, 8; int
0x18000e64d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e652  jmp     loc_18000EA05
0x18000e657  mov     rax, [rbx]
0x18000e65a  lea     rdx, [rsp+400h+var_3A8]
0x18000e65f  mov     rcx, rbx
0x18000e662  mov     rax, [rax+78h]
0x18000e666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e66b  mov     rcx, [rsp+400h+var_3A8]
0x18000e670  mov     rax, [rcx]
0x18000e673  lea     r8, [rsp+400h+var_3B0]
0x18000e678  mov     rdx, r14
0x18000e67b  mov     rax, [rax+30h]
0x18000e67f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e684  mov     edi, eax
0x18000e686  test    eax, eax
0x18000e688  jns     short loc_18000E6AA
0x18000e68a  lea     r9, aRpcopenlistene; "RpcOpenListener"
0x18000e691  mov     r8d, eax
0x18000e694  lea     rdx, aListGetlistene; "List->GetListenerByName failed: 0x%x in"...
0x18000e69b  mov     ecx, 8; int
0x18000e6a0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e6a5  jmp     loc_18000EA05
0x18000e6aa  mov     r14, [rsp+400h+var_3B8]
0x18000e6af  mov     rdi, [rsp+400h+var_3B0]
0x18000e6b4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e6bb  mov     ecx, 658h; unsigned __int64
0x18000e6c0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e6c5  mov     rsi, rax
0x18000e6c8  test    rax, rax
0x18000e6cb  jz      loc_18000E9A5
0x18000e6d1  lea     rax, ??_7?$CTSPrivateObject@UIUnknown@@@@6B@; const CTSPrivateObject<IUnknown>::`vftable'
0x18000e6d8  mov     [rsi], rax
0x18000e6db  lea     rax, aListenertracke; "LISTENERTRACKER"
0x18000e6e2  mov     [rsi+10h], rax
0x18000e6e6  mov     [rsi+8], r12d
0x18000e6ea  mov     dword ptr [rsi+0Ch], 1
0x18000e6f1  lea     rcx, [rsi+628h]; struct _LIST_ENTRY *
0x18000e6f8  mov     [rcx+8], rcx
0x18000e6fc  mov     [rcx], rcx
0x18000e6ff  call    ?AddTrackingObject@@YAXPEAU_LIST_ENTRY@@@Z; AddTrackingObject(_LIST_ENTRY *)
0x18000e704  mov     [rsi+18h], r12
0x18000e708  mov     [rsi+20h], r12d
0x18000e70c  mov     [rsp+400h+BackTraceHash], r12d
0x18000e711  mov     eax, 1
0x18000e716  lock xadd [rsi+20h], eax
0x18000e71b  inc     eax
0x18000e71d  cmp     cs:?g_bCaptureObjectStackTrace@@3HA, 1; int g_bCaptureObjectStackTrace
0x18000e724  jnz     short loc_18000E753
0x18000e726  and     eax, 1Fh
0x18000e729  lea     r8, [rax+rax*2]
0x18000e72d  shl     r8, 4
0x18000e731  add     r8, 28h ; '('
0x18000e735  add     r8, rsi; BackTrace
0x18000e738  lea     r9, [rsp+400h+BackTraceHash]; BackTraceHash
0x18000e73d  mov     edx, 6; FramesToCapture
0x18000e742  mov     ecx, 1; FramesToSkip
0x18000e747  call    cs:__imp_RtlCaptureStackBackTrace
0x18000e74e  nop     dword ptr [rax+rax+00h]
0x18000e753  lea     rax, ??_7?$CObjectAccessTracker@VIListener@@$0BDII@@@6B@; const CObjectAccessTracker<IListener,5000>::`vftable'
0x18000e75a  mov     [rsi], rax
0x18000e75d  mov     [rsi+638h], rdi
0x18000e764  test    rdi, rdi
0x18000e767  jz      short loc_18000E778
0x18000e769  mov     rax, [rdi]
0x18000e76c  mov     rcx, rdi
0x18000e76f  mov     rax, [rax+8]
0x18000e773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e778  mov     qword ptr [rsi+640h], 0FFFFFFFFFFFFFFFFh
0x18000e783  mov     [rsi+648h], r14
0x18000e78a  test    r14, r14
0x18000e78d  jz      short loc_18000E79E
0x18000e78f  mov     rax, [r14]
0x18000e792  mov     rcx, r14
0x18000e795  mov     rax, [rax+8]
0x18000e799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e79e  mov     [rsi+650h], r12
0x18000e7a5  mov     [rsp+400h+ClientLocalFlag], r12d
0x18000e7aa  lea     rdx, [rsp+400h+ClientLocalFlag]; ClientLocalFlag
0x18000e7af  xor     ecx, ecx; BindingHandle
0x18000e7b1  call    cs:__imp_I_RpcBindingIsClientLocal
0x18000e7b8  nop     dword ptr [rax+rax+00h]
0x18000e7bd  test    eax, eax
0x18000e7bf  jle     short loc_18000E7CB
0x18000e7c1  movzx   eax, ax
0x18000e7c4  or      eax, 80070000h
0x18000e7c9  test    eax, eax
0x18000e7cb  js      loc_18000E92E
0x18000e7d1  cmp     [rsp+400h+ClientLocalFlag], r12d
0x18000e7d6  jz      loc_18000E92E
0x18000e7dc  mov     [rsp+400h+var_3D0], r12d
0x18000e7e1  mov     [rsp+400h+BackTraceHash], r12d
0x18000e7e6  xor     ecx, ecx; BindingHandle
  ... truncated ...
```
