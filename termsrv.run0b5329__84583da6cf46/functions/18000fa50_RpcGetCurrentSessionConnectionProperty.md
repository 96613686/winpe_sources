# RpcGetCurrentSessionConnectionProperty

- ea: `0x18000fa50`
- end: `0x180010059`
- name: `RpcGetCurrentSessionConnectionProperty`
- size: `1545`
- prototype: `__int64 __fastcall(__int64, void *, char **)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a210`
- `0x18000f790`
- `0x18000fa50`
- `0x180010060`
- `0x1800119a0`
- `0x1800127b0`
- `0x180014de0`
- `0x1800321f0`
- `0x1800330c4`
- `0x1800c4e00`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000fc9e`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000fc9e`
- `ntdll!NtQueryInformationProcess` at `0x18000fc82`
- `ntdll!NtQueryInformationProcess` at `0x18000fc82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fdcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fffa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010014`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fdcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fffa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010014`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000fc41`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000fc41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000fda8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000fe7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000fda8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000fe7f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000fdc1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000fe98`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000fdc1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000fe98`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000fff0`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001000a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000fff0`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001000a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fcca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fe42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ff4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010027`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fcca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fe42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ff4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010027`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000fc1d`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000fc1d`
- `RPCRT4!RpcRevertToSelf` at `0x18000fde5`
- `RPCRT4!RpcRevertToSelf` at `0x18000fde5`
- `RPCRT4!RpcImpersonateClient` at `0x18000fd86`
- `RPCRT4!RpcImpersonateClient` at `0x18000fd86`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000fc5a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000fc5a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000fefc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000fefc`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000fabd`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000fabd`

## string_xrefs

- `0x18000fe59`: `CRpcUtils::GetClientToken failed: 0x%x in %s`
- `0x18000fd9f`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18000fe21`: `CRpcUtils::GetClientToken`
- `0x18000ffb6`: `%s with Trace ID 0x%x Completed`
- `0x18000ff29`: `GetTokenInformation failed: 0x%x in %s`
- `0x18000fe1a`: `OpenThreadToken failed: 0x%x in %s`
- `0x18000fec5`: `OpenThreadToken failed: 0x%x in %s`
- `0x18000fb2e`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18000fcf3`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RpcGetCurrentSessionConnectionProperty(__int64 a1, void *a2, char **a3)
{
  void *v6; // rbx
  unsigned int v7; // esi
  RPC_STATUS v8; // eax
  int v9; // edi
  HANDLE v10; // rax
  void *v11; // rsi
  NTSTATUS InformationProcess; // eax
  wchar_t *v13; // rax
  wchar_t *v14; // rax
  signed int v15; // edi
  RPC_STATUS v16; // eax
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  int v19; // eax
  bool v20; // sf
  void *v21; // rax
  unsigned int v22; // esi
  HANDLE v23; // rax
  signed int v24; // eax
  HANDLE v25; // rcx
  signed int v26; // eax
  int ConnectionProperty; // eax
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int TokenInformation; // [rsp+38h] [rbp-C8h] BYREF
  DWORD ReturnLength; // [rsp+3Ch] [rbp-C4h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  void **v33; // [rsp+50h] [rbp-B0h] BYREF
  GUID pguid; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v35[2]; // [rsp+68h] [rbp-98h] BYREF
  struct CTraceBase *v36; // [rsp+70h] [rbp-90h] BYREF
  int v37; // [rsp+78h] [rbp-88h]
  const char *v38; // [rsp+80h] [rbp-80h]
  unsigned int Pid[2]; // [rsp+88h] [rbp-78h] BYREF
  int v40; // [rsp+90h] [rbp-70h]
  unsigned __int16 v41[262]; // [rsp+94h] [rbp-6Ch] BYREF
  _BYTE ProcessInformation[8]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wchar_t *Str; // [rsp+2A8h] [rbp+1A8h]

  v6 = 0;
  v33 = &CTraceBase::`vftable';
  v35[1] = 1;
  v36 = 0;
  if ( !CTraceBase::g_bEnabled )
  {
    CoCreateGuid(&pguid);
    v35[0] = _InterlockedIncrement((volatile signed __int32 *)&CTraceBase::g_NextShortActivityID);
LABEL_13:
    v37 = 0;
    goto LABEL_14;
  }
  if ( (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "Adding trace %p, %d, %s", &v33, 1, "RpcGetCurrentSessionConnectionProperty");
  hObject = 0;
  if ( (int)CTraceBase::GetThreadCurrentOperationTrace((struct CTraceBase **)&hObject) >= 0
    && hObject
    && (g_DebugTraceComponent & 1) != 0 )
  {
    _DbgPrintMessage(
      2,
      "TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC",
      1);
  }
  CTraceBase::ResetThreadCurrentOperationTrace(0, 0);
  if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v36) < 0 || !v36 )
  {
    CTraceBase::ResetThreadCurrentOperationTrace((struct CTraceBase *)&v33, "RpcGetCurrentSessionConnectionProperty");
    CTraceBase::GenerateTraceID(&pguid, v35);
    goto LABEL_13;
  }
  (*(void (__fastcall **)(struct CTraceBase *, GUID *))(*(_QWORD *)v36 + 32LL))(v36, &pguid);
  v35[0] = (*(__int64 (__fastcall **)(struct CTraceBase *))(*(_QWORD *)v36 + 24LL))(v36);
  v37 = 1;
LABEL_14:
  v33 = &CRpcCallTrace::`vftable';
  v38 = "RpcGetCurrentSessionConnectionProperty";
  *(_QWORD *)Pid = -1;
  v40 = 0;
  memset_0(v41, 0, 0x208u);
  if ( v40 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "TRACE RPC %s with Trace ID 0x%x", v38, v35[0]);
  v7 = g_DebugTraceComponent & 1;
  *(_QWORD *)Pid = -1;
  v8 = I_RpcBindingInqLocalClientPID(0, &Pid[1]);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v9 >= 0 )
  {
    ProcessIdToSessionId(Pid[1], Pid);
    if ( v7 )
    {
      v10 = OpenProcess(0x400u, 0, Pid[1]);
      v11 = v10;
      if ( v10 )
      {
        InformationProcess = NtQueryInformationProcess(v10, ProcessImageFileName, ProcessInformation, 0x110u, 0);
        v9 = InformationProcess | 0x10000000;
        if ( InformationProcess >= 0 )
        {
          v13 = wcsrchr(Str, 0x5Cu);
          if ( v13 )
            v14 = v13 + 1;
          else
            v14 = Str;
          StringCchCopyW(v41, 0x104u, v14);
        }
        CloseHandle(v11);
      }
    }
  }
  if ( v40 )
  {
    if ( v9 < 0 )
    {
      if ( (g_DebugTraceComponent & 1) != 0 )
        _DbgPrintMessage(2, "RPC Caller: Unknown");
    }
    else if ( (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(2, "RPC Caller: PID %d, SessID %d, Process Name: <%S>", Pid[1], Pid[0], v41);
    }
  }
  if ( memcmp_0(PROPERTY_TYPE_AUDIOENUM_DLL, a2, 0x10u)
    && memcmp_0(&PROPERTY_TYPE_TS_LICENSETYPE_GUID, a2, 0x10u)
    && memcmp_0(PROPERTY_TYPE_CLIENT_ALLOWS_AUDIO_CAPTURE_CLSID, a2, 0x10u) )
  {
    v15 = -2147024891;
    _DbgPrintMessage(
      8,
      "Invalid Property Type failed: 0x%x in %s",
      2147942405LL,
      "RpcGetCurrentSessionConnectionProperty");
    goto LABEL_78;
  }
  TokenHandle = 0;
  v16 = RpcImpersonateClient(0);
  v15 = v16;
  if ( v16 > 0 )
    v15 = (unsigned __int16)v16 | 0x80070000;
  if ( v15 >= 0 )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
    {
      v15 = 0;
    }
    else
    {
      LastError = GetLastError();
      v15 = LastError;
      if ( LastError > 0 )
        v15 = (unsigned __int16)LastError | 0x80070000;
    }
    v19 = RpcRevertToSelf();
    v20 = v19 < 0;
    if ( v19 > 0 )
    {
      v19 = (unsigned __int16)v19 | 0x80070000;
      v20 = v19 < 0;
    }
    if ( v20 )
    {
      _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v19);
      v15 = -2147024891;
    }
    else
    {
      if ( v15 >= 0 )
      {
        v21 = TokenHandle;
        goto LABEL_55;
      }
      _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x in %s", (unsigned int)v15, "CRpcUtils::GetClientToken");
    }
  }
  else
  {
    _DbgPrintMessage(8, "RpcImpersonateClient failed: 0x%x in %s", (unsigned int)v15, "CRpcUtils::GetClientToken");
  }
  v21 = TokenHandle;
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    goto LABEL_56;
  }
LABEL_55:
  v6 = v21;
LABEL_56:
  if ( v15 < 0 )
  {
    _DbgPrintMessage(
      8,
      "CRpcUtils::GetClientToken failed: 0x%x in %s",
      (unsigned int)v15,
      "RpcGetCurrentSessionConnectionProperty");
    goto LABEL_78;
  }
  v22 = 0;
  hObject = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  v15 = 0;
  if ( v6 )
  {
    v25 = v6;
    goto LABEL_66;
  }
  v23 = GetCurrentThread();
  if ( OpenThreadToken(v23, 8u, 1, &hObject) )
    goto LABEL_64;
  v24 = GetLastError();
  v15 = v24;
  if ( v24 > 0 )
    v15 = (unsigned __int16)v24 | 0x80070000;
  if ( v15 >= 0 )
  {
LABEL_64:
    v25 = hObject;
LABEL_66:
    if ( GetTokenInformation(v25, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
      goto LABEL_71;
    v26 = GetLastError();
    v15 = v26;
    if ( v26 > 0 )
      v15 = (unsigned __int16)v26 | 0x80070000;
    if ( v15 >= 0 )
LABEL_71:
      v22 = TokenInformation;
    else
      _DbgPrintMessage(8, "GetTokenInformation failed: 0x%x in %s", v15, "CUtils::GetUserSessionId");
    goto LABEL_72;
  }
  _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x in %s", v15, "CUtils::GetUserSessionId");
LABEL_72:
  if ( hObject )
    CloseHandle(hObject);
  if ( v15 >= 0 )
  {
    ConnectionProperty = RpcGetConnectionProperty(a1, v22, (char *)a2, a3);
    v15 = ConnectionProperty;
    if ( ConnectionProperty < 0 )
      _DbgPrintMessage(
        8,
        "RpcGetConnectionProperty failed: 0x%x in %s",
        (unsigned int)ConnectionProperty,
        "RpcGetCurrentSessionConnectionProperty");
  }
  else
  {
    _DbgPrintMessage(
      8,
      "CUtils::GetUserSessionId() failed: 0x%x in %s",
      (unsigned int)v15,
      "RpcGetCurrentSessionConnectionProperty");
  }
LABEL_78:
  v33 = &CRpcCallTrace::`vftable';
  if ( v40 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "%s with Trace ID 0x%x Completed", v38, v35[0]);
  v33 = &CTraceBase::`vftable';
  if ( CTraceBase::g_bEnabled && !v37 && CTraceBase::g_TLSIndex != -1 )
  {
    if ( TlsSetValue(CTraceBase::g_TLSIndex, 0) )
    {
      if ( TlsSetValue(CTraceBase::g_CreatorFunctionTLSIndex, 0) )
        goto LABEL_88;
    }
    else
    {
      GetLastError();
    }
    GetLastError();
  }
LABEL_88:
  v36 = 0;
  if ( v6 )
    CloseHandle(v6);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18000fa50  mov     [rsp-8+arg_18], rbx
0x18000fa55  push    rbp
0x18000fa56  push    rsi
0x18000fa57  push    rdi
0x18000fa58  push    r12
0x18000fa5a  push    r13
0x18000fa5c  push    r14
0x18000fa5e  push    r15
0x18000fa60  lea     rbp, [rsp-2C0h]
0x18000fa68  sub     rsp, 3C0h
0x18000fa6f  mov     rax, cs:__security_cookie
0x18000fa76  xor     rax, rsp
0x18000fa79  mov     [rbp+2F0h+var_40], rax
0x18000fa80  mov     r12, r8
0x18000fa83  mov     r14, rdx
0x18000fa86  mov     r15, rcx
0x18000fa89  xor     r13d, r13d
0x18000fa8c  mov     ebx, r13d
0x18000fa8f  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000fa96  mov     [rsp+3F0h+var_3A0], rax
0x18000fa9b  mov     [rsp+3F0h+var_384], 1
0x18000faa3  mov     [rsp+3F0h+var_380], r13
0x18000faa8  lea     rdi, aRpcgetcurrents_1; "RpcGetCurrentSessionConnectionProperty"
0x18000faaf  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r13d; int CTraceBase::g_bEnabled
0x18000fab6  jnz     short loc_18000FADB
0x18000fab8  lea     rcx, [rsp+3F0h+pguid]; pguid
0x18000fabd  call    cs:__imp_CoCreateGuid
0x18000fac3  mov     eax, 1
0x18000fac8  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x18000fad0  inc     eax
0x18000fad2  mov     [rsp+3F0h+var_388], eax
0x18000fad6  jmp     loc_18000FBAC
0x18000fadb  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000fae2  jz      short loc_18000FB05
0x18000fae4  mov     [rsp+3F0h+ReturnLength], rdi
0x18000fae9  mov     r9d, 1
0x18000faef  lea     r8, [rsp+3F0h+var_3A0]
0x18000faf4  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x18000fafb  mov     ecx, 2; int
0x18000fb00  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000fb05  mov     [rsp+3F0h+hObject], r13
0x18000fb0a  lea     rcx, [rsp+3F0h+hObject]; struct CTraceBase **
0x18000fb0f  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000fb14  test    eax, eax
0x18000fb16  js      short loc_18000FB3F
0x18000fb18  cmp     [rsp+3F0h+hObject], rbx
0x18000fb1d  jz      short loc_18000FB3F
0x18000fb1f  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000fb26  jz      short loc_18000FB3F
0x18000fb28  mov     r8d, 1
0x18000fb2e  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x18000fb35  mov     ecx, 2; int
0x18000fb3a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000fb3f  xor     edx, edx; char *
0x18000fb41  xor     ecx, ecx; lpTlsValue
0x18000fb43  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000fb48  lea     rcx, [rsp+3F0h+var_380]; struct CTraceBase **
0x18000fb4d  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000fb52  test    eax, eax
0x18000fb54  js      short loc_18000FB90
0x18000fb56  mov     rcx, [rsp+3F0h+var_380]
0x18000fb5b  test    rcx, rcx
0x18000fb5e  jz      short loc_18000FB90
0x18000fb60  mov     rax, [rcx]
0x18000fb63  lea     rdx, [rsp+3F0h+pguid]
0x18000fb68  mov     rax, [rax+20h]
0x18000fb6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb71  mov     rcx, [rsp+3F0h+var_380]
0x18000fb76  mov     rax, [rcx]
0x18000fb79  mov     rax, [rax+18h]
0x18000fb7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb82  mov     [rsp+3F0h+var_388], eax
0x18000fb86  mov     [rsp+3F0h+var_378], 1
0x18000fb8e  jmp     short loc_18000FBB1
0x18000fb90  mov     rdx, rdi; char *
0x18000fb93  lea     rcx, [rsp+3F0h+var_3A0]; lpTlsValue
0x18000fb98  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000fb9d  lea     rdx, [rsp+3F0h+var_388]; unsigned int *
0x18000fba2  lea     rcx, [rsp+3F0h+pguid]; struct _GUID *
0x18000fba7  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x18000fbac  mov     [rsp+3F0h+var_378], r13d
0x18000fbb1  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000fbb8  mov     [rsp+3F0h+var_3A0], rax
0x18000fbbd  mov     [rbp+2F0h+var_370], rdi
0x18000fbc1  mov     qword ptr [rbp+2F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000fbc9  mov     [rbp+2F0h+var_360], r13d
0x18000fbcd  xor     edx, edx; Val
0x18000fbcf  mov     r8d, 208h; Size
0x18000fbd5  lea     rcx, [rbp+2F0h+var_35C]; void *
0x18000fbd9  call    memset_0
0x18000fbde  cmp     [rbp+2F0h+var_360], ebx
0x18000fbe1  jz      short loc_18000FC06
0x18000fbe3  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000fbea  jz      short loc_18000FC06
0x18000fbec  mov     r9d, [rsp+3F0h+var_388]
0x18000fbf1  mov     r8, [rbp+2F0h+var_370]
0x18000fbf5  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x18000fbfc  mov     ecx, 2; int
0x18000fc01  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000fc06  mov     esi, cs:?g_DebugTraceComponent@@3KA; ulong g_DebugTraceComponent
0x18000fc0c  and     esi, 1
0x18000fc0f  mov     qword ptr [rbp+2F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000fc17  lea     rdx, [rbp+2F0h+Pid+4]; Pid
0x18000fc1b  xor     ecx, ecx; Binding
0x18000fc1d  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000fc23  mov     edi, eax
0x18000fc25  test    eax, eax
0x18000fc27  jle     short loc_18000FC32
0x18000fc29  movzx   edi, ax
0x18000fc2c  or      edi, 80070000h
0x18000fc32  test    edi, edi
0x18000fc34  js      loc_18000FCD0
0x18000fc3a  lea     rdx, [rbp+2F0h+Pid]; pSessionId
0x18000fc3e  mov     ecx, [rbp+2F0h+Pid+4]; dwProcessId
0x18000fc41  call    cs:__imp_ProcessIdToSessionId
0x18000fc47  test    esi, esi
0x18000fc49  jz      loc_18000FCD0
0x18000fc4f  mov     r8d, [rbp+2F0h+Pid+4]; dwProcessId
0x18000fc53  xor     edx, edx; bInheritHandle
0x18000fc55  mov     ecx, 400h; dwDesiredAccess
0x18000fc5a  call    cs:__imp_OpenProcess
0x18000fc60  mov     rsi, rax
0x18000fc63  test    rax, rax
0x18000fc66  jz      short loc_18000FCD0
0x18000fc68  mov     [rsp+3F0h+ReturnLength], r13; ReturnLength
0x18000fc6d  mov     r9d, 110h; ProcessInformationLength
0x18000fc73  lea     r8, [rbp+2F0h+ProcessInformation]; ProcessInformation
0x18000fc7a  mov     edx, 1Bh; ProcessInformationClass
0x18000fc7f  mov     rcx, rax; ProcessHandle
0x18000fc82  call    cs:__imp_NtQueryInformationProcess
0x18000fc88  mov     edi, eax
0x18000fc8a  or      edi, 10000000h
0x18000fc90  jl      short loc_18000FCC7
0x18000fc92  mov     edx, 5Ch ; '\'; Ch
0x18000fc97  mov     rcx, [rbp+2F0h+Str]; Str
0x18000fc9e  call    cs:__imp_wcsrchr
0x18000fca4  test    rax, rax
0x18000fca7  jnz     short loc_18000FCB2
0x18000fca9  mov     rax, [rbp+2F0h+Str]
0x18000fcb0  jmp     short loc_18000FCB6
0x18000fcb2  add     rax, 2
0x18000fcb6  mov     r8, rax; unsigned __int16 *
0x18000fcb9  mov     edx, 104h; unsigned __int64
0x18000fcbe  lea     rcx, [rbp+2F0h+var_35C]; unsigned __int16 *
0x18000fcc2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fcc7  mov     rcx, rsi; hObject
0x18000fcca  call    cs:__imp_CloseHandle
0x18000fcd0  cmp     [rbp+2F0h+var_360], ebx
0x18000fcd3  jz      short loc_18000FD20
0x18000fcd5  test    edi, edi
0x18000fcd7  js      short loc_18000FD06
0x18000fcd9  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000fce0  jz      short loc_18000FD20
0x18000fce2  lea     rax, [rbp+2F0h+var_35C]
0x18000fce6  mov     [rsp+3F0h+ReturnLength], rax
0x18000fceb  mov     r9d, [rbp+2F0h+Pid]
0x18000fcef  mov     r8d, [rbp+2F0h+Pid+4]
0x18000fcf3  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x18000fcfa  mov     ecx, 2; int
0x18000fcff  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000fd04  jmp     short loc_18000FD20
0x18000fd06  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000fd0d  jz      short loc_18000FD20
0x18000fd0f  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x18000fd16  mov     ecx, 2; int
0x18000fd1b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000fd20  mov     r8d, 10h; Size
0x18000fd26  mov     rdx, r14; Buf2
0x18000fd29  lea     rcx, PROPERTY_TYPE_AUDIOENUM_DLL; Buf1
0x18000fd30  call    memcmp_0
0x18000fd35  test    eax, eax
0x18000fd37  jz      short loc_18000FD7F
0x18000fd39  mov     r8d, 10h; Size
0x18000fd3f  mov     rdx, r14; Buf2
0x18000fd42  lea     rcx, PROPERTY_TYPE_TS_LICENSETYPE_GUID; Buf1
0x18000fd49  call    memcmp_0
0x18000fd4e  test    eax, eax
0x18000fd50  jz      short loc_18000FD7F
0x18000fd52  mov     r8d, 10h; Size
0x18000fd58  mov     rdx, r14; Buf2
0x18000fd5b  lea     rcx, PROPERTY_TYPE_CLIENT_ALLOWS_AUDIO_CAPTURE_CLSID; Buf1
0x18000fd62  call    memcmp_0
0x18000fd67  test    eax, eax
0x18000fd69  jz      short loc_18000FD7F
0x18000fd6b  mov     edi, 80070005h
0x18000fd70  mov     r8d, edi
0x18000fd73  lea     rdx, aInvalidPropert; "Invalid Property Type failed: 0x%x in %"...
0x18000fd7a  jmp     loc_18000FF80
0x18000fd7f  mov     [rsp+3F0h+TokenHandle], r13
0x18000fd84  xor     ecx, ecx; BindingHandle
0x18000fd86  call    cs:__imp_RpcImpersonateClient
0x18000fd8c  mov     edi, eax
0x18000fd8e  test    eax, eax
0x18000fd90  jle     short loc_18000FD9B
0x18000fd92  movzx   edi, ax
0x18000fd95  or      edi, 80070000h
0x18000fd9b  test    edi, edi
0x18000fd9d  jns     short loc_18000FDA8
0x18000fd9f  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x18000fda6  jmp     short loc_18000FE21
0x18000fda8  call    cs:__imp_GetCurrentThread
0x18000fdae  mov     rcx, rax; ThreadHandle
0x18000fdb1  lea     r9, [rsp+3F0h+TokenHandle]; TokenHandle
0x18000fdb6  mov     edx, 0Eh; DesiredAccess
0x18000fdbb  mov     r8d, 1; OpenAsSelf
0x18000fdc1  call    cs:__imp_OpenThreadToken
0x18000fdc7  test    eax, eax
0x18000fdc9  jnz     short loc_18000FDE2
0x18000fdcb  call    cs:__imp_GetLastError
0x18000fdd1  mov     edi, eax
0x18000fdd3  test    eax, eax
0x18000fdd5  jle     short loc_18000FDE5
0x18000fdd7  movzx   edi, ax
0x18000fdda  or      edi, 80070000h
0x18000fde0  jmp     short loc_18000FDE5
0x18000fde2  mov     edi, r13d
0x18000fde5  call    cs:__imp_RpcRevertToSelf
0x18000fdeb  test    eax, eax
0x18000fded  jle     short loc_18000FDF9
0x18000fdef  movzx   eax, ax
0x18000fdf2  or      eax, 80070000h
0x18000fdf7  test    eax, eax
0x18000fdf9  jns     short loc_18000FE16
0x18000fdfb  mov     r8d, eax
0x18000fdfe  lea     rdx, aRpcreverttosel_1; "RpcRevertToSelf failed: 0x%x"
0x18000fe05  mov     ecx, 8; int
0x18000fe0a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000fe0f  mov     edi, 80070005h
0x18000fe14  jmp     short loc_18000FE35
0x18000fe16  test    edi, edi
0x18000fe18  jns     short loc_18000FE4A
0x18000fe1a  lea     rdx, aOpenthreadtoke; "OpenThreadToken failed: 0x%x in %s"
0x18000fe21  lea     r9, aCrpcutilsGetcl; "CRpcUtils::GetClientToken"
0x18000fe28  mov     r8d, edi
0x18000fe2b  mov     ecx, 8; int
0x18000fe30  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000fe35  mov     rax, [rsp+3F0h+TokenHandle]
0x18000fe3a  test    rax, rax
0x18000fe3d  jz      short loc_18000FE4F
0x18000fe3f  mov     rcx, rax; hObject
0x18000fe42  call    cs:__imp_CloseHandle
0x18000fe48  jmp     short loc_18000FE52
0x18000fe4a  mov     rax, [rsp+3F0h+TokenHandle]
0x18000fe4f  mov     rbx, rax
0x18000fe52  test    edi, edi
0x18000fe54  jns     short loc_18000FE65
0x18000fe56  mov     r8d, edi
0x18000fe59  lea     rdx, aCrpcutilsGetcl_0; "CRpcUtils::GetClientToken failed: 0x%x "...
0x18000fe60  jmp     loc_18000FF80
0x18000fe65  mov     esi, r13d
0x18000fe68  mov     [rsp+3F0h+hObject], r13
0x18000fe6d  mov     [rsp+3F0h+TokenInformation], r13d
0x18000fe72  mov     [rsp+3F0h+var_3B4], r13d
0x18000fe77  mov     edi, r13d
0x18000fe7a  test    rbx, rbx
0x18000fe7d  jnz     short loc_18000FEDF
0x18000fe7f  call    cs:__imp_GetCurrentThread
0x18000fe85  lea     r9, [rsp+3F0h+hObject]; TokenHandle
0x18000fe8a  mov     edx, 8; DesiredAccess
0x18000fe8f  mov     r8d, 1; OpenAsSelf
0x18000fe95  mov     rcx, rax; ThreadHandle
0x18000fe98  call    cs:__imp_OpenThreadToken
0x18000fe9e  test    eax, eax
0x18000fea0  jnz     short loc_18000FED8
0x18000fea2  call    cs:__imp_GetLastError
0x18000fea8  mov     edi, eax
0x18000feaa  test    eax, eax
0x18000feac  jle     short loc_18000FEB7
0x18000feae  movzx   edi, ax
0x18000feb1  or      edi, 80070000h
0x18000feb7  test    edi, edi
0x18000feb9  jns     short loc_18000FED8
0x18000febb  lea     r9, aCutilsGetusers_1; "CUtils::GetUserSessionId"
0x18000fec2  mov     r8d, edi
0x18000fec5  lea     rdx, aOpenthreadtoke; "OpenThreadToken failed: 0x%x in %s"
0x18000fecc  mov     ecx, 8; int
0x18000fed1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000fed6  jmp     short loc_18000FF40
0x18000fed8  mov     rcx, [rsp+3F0h+hObject]
0x18000fedd  jmp     short loc_18000FEE2
0x18000fedf  mov     rcx, rbx; TokenHandle
0x18000fee2  lea     rax, [rsp+3F0h+var_3B4]
0x18000fee7  mov     [rsp+3F0h+ReturnLength], rax; ReturnLength
0x18000feec  mov     r9d, 4; TokenInformationLength
0x18000fef2  lea     r8, [rsp+3F0h+TokenInformation]; TokenInformation
0x18000fef7  mov     edx, 0Ch; TokenInformationClass
0x18000fefc  call    cs:__imp_GetTokenInformation
0x18000ff02  test    eax, eax
0x18000ff04  jnz     short loc_18000FF3C
0x18000ff06  call    cs:__imp_GetLastError
0x18000ff0c  mov     edi, eax
0x18000ff0e  test    eax, eax
0x18000ff10  jle     short loc_18000FF1B
0x18000ff12  movzx   edi, ax
0x18000ff15  or      edi, 80070000h
0x18000ff1b  test    edi, edi
0x18000ff1d  jns     short loc_18000FF3C
0x18000ff1f  lea     r9, aCutilsGetusers_1; "CUtils::GetUserSessionId"
0x18000ff26  mov     r8d, edi
0x18000ff29  lea     rdx, aGettokeninform_3; "GetTokenInformation failed: 0x%x in %s"
  ... truncated ...
```
