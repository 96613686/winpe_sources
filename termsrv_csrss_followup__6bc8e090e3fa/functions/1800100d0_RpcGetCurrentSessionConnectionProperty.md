# RpcGetCurrentSessionConnectionProperty

- ea: `0x1800100d0`
- end: `0x18001076d`
- name: `RpcGetCurrentSessionConnectionProperty`
- size: `1693`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009940`
- `0x18000faf0`
- `0x1800100d0`
- `0x180010780`
- `0x180012070`
- `0x180012d10`
- `0x1800154a0`
- `0x180033f60`
- `0x180034e64`
- `0x1800caed0`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001033c`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001033c`
- `ntdll!NtQueryInformationProcess` at `0x18001031a`
- `ntdll!NtQueryInformationProcess` at `0x18001031a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001048a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001057f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800105ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800106f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001071b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001048a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001057f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800105ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800106f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001071b`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800102cd`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800102cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001045b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010550`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001045b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010550`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001047a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001056f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001047a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001056f`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800106e5`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001070b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800106e5`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001070b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001036e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001050d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010639`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010734`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001036e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001050d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010639`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010734`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800102a3`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800102a3`
- `RPCRT4!RpcRevertToSelf` at `0x1800104aa`
- `RPCRT4!RpcRevertToSelf` at `0x1800104aa`
- `RPCRT4!RpcImpersonateClient` at `0x180010430`
- `RPCRT4!RpcImpersonateClient` at `0x180010430`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800102ec`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800102ec`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800105df`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800105df`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001013d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001013d`

## string_xrefs

- `0x18001052a`: `CRpcUtils::GetClientToken failed: 0x%x in %s`
- `0x18001044f`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x1800104ec`: `CRpcUtils::GetClientToken`
- `0x1800106ab`: `%s with Trace ID 0x%x Completed`
- `0x180010618`: `GetTokenInformation failed: 0x%x in %s`
- `0x1800104e5`: `OpenThreadToken failed: 0x%x in %s`
- `0x1800105a8`: `OpenThreadToken failed: 0x%x in %s`
- `0x1800101b4`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18001039d`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RpcGetCurrentSessionConnectionProperty(__int64 a1, const void *a2, __int64 a3)
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
    ConnectionProperty = RpcGetConnectionProperty(a1, v22, a2, a3);
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
0x1800100d0  mov     [rsp-8+arg_18], rbx
0x1800100d5  push    rbp
0x1800100d6  push    rsi
0x1800100d7  push    rdi
0x1800100d8  push    r12
0x1800100da  push    r13
0x1800100dc  push    r14
0x1800100de  push    r15
0x1800100e0  lea     rbp, [rsp-2C0h]
0x1800100e8  sub     rsp, 3C0h
0x1800100ef  mov     rax, cs:__security_cookie
0x1800100f6  xor     rax, rsp
0x1800100f9  mov     [rbp+2F0h+var_40], rax
0x180010100  mov     r12, r8
0x180010103  mov     r14, rdx
0x180010106  mov     r15, rcx
0x180010109  xor     r13d, r13d
0x18001010c  mov     ebx, r13d
0x18001010f  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x180010116  mov     [rsp+3F0h+var_3A0], rax
0x18001011b  mov     [rsp+3F0h+var_384], 1
0x180010123  mov     [rsp+3F0h+var_380], r13
0x180010128  lea     rdi, aRpcgetcurrents_1; "RpcGetCurrentSessionConnectionProperty"
0x18001012f  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r13d; int CTraceBase::g_bEnabled
0x180010136  jnz     short loc_180010161
0x180010138  lea     rcx, [rsp+3F0h+pguid]; pguid
0x18001013d  call    cs:__imp_CoCreateGuid
0x180010144  nop     dword ptr [rax+rax+00h]
0x180010149  mov     eax, 1
0x18001014e  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x180010156  inc     eax
0x180010158  mov     [rsp+3F0h+var_388], eax
0x18001015c  jmp     loc_180010232
0x180010161  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180010168  jz      short loc_18001018B
0x18001016a  mov     [rsp+3F0h+ReturnLength], rdi
0x18001016f  mov     r9d, 1
0x180010175  lea     r8, [rsp+3F0h+var_3A0]
0x18001017a  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x180010181  mov     ecx, 2; int
0x180010186  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001018b  mov     [rsp+3F0h+hObject], r13
0x180010190  lea     rcx, [rsp+3F0h+hObject]; struct CTraceBase **
0x180010195  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18001019a  test    eax, eax
0x18001019c  js      short loc_1800101C5
0x18001019e  cmp     [rsp+3F0h+hObject], rbx
0x1800101a3  jz      short loc_1800101C5
0x1800101a5  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x1800101ac  jz      short loc_1800101C5
0x1800101ae  mov     r8d, 1
0x1800101b4  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x1800101bb  mov     ecx, 2; int
0x1800101c0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800101c5  xor     edx, edx; char *
0x1800101c7  xor     ecx, ecx; lpTlsValue
0x1800101c9  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x1800101ce  lea     rcx, [rsp+3F0h+var_380]; struct CTraceBase **
0x1800101d3  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x1800101d8  test    eax, eax
0x1800101da  js      short loc_180010216
0x1800101dc  mov     rcx, [rsp+3F0h+var_380]
0x1800101e1  test    rcx, rcx
0x1800101e4  jz      short loc_180010216
0x1800101e6  mov     rax, [rcx]
0x1800101e9  lea     rdx, [rsp+3F0h+pguid]
0x1800101ee  mov     rax, [rax+20h]
0x1800101f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101f7  mov     rcx, [rsp+3F0h+var_380]
0x1800101fc  mov     rax, [rcx]
0x1800101ff  mov     rax, [rax+18h]
0x180010203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010208  mov     [rsp+3F0h+var_388], eax
0x18001020c  mov     [rsp+3F0h+var_378], 1
0x180010214  jmp     short loc_180010237
0x180010216  mov     rdx, rdi; char *
0x180010219  lea     rcx, [rsp+3F0h+var_3A0]; lpTlsValue
0x18001021e  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x180010223  lea     rdx, [rsp+3F0h+var_388]; unsigned int *
0x180010228  lea     rcx, [rsp+3F0h+pguid]; struct _GUID *
0x18001022d  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x180010232  mov     [rsp+3F0h+var_378], r13d
0x180010237  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18001023e  mov     [rsp+3F0h+var_3A0], rax
0x180010243  mov     [rbp+2F0h+var_370], rdi
0x180010247  mov     qword ptr [rbp+2F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18001024f  mov     [rbp+2F0h+var_360], r13d
0x180010253  xor     edx, edx; Val
0x180010255  mov     r8d, 208h; Size
0x18001025b  lea     rcx, [rbp+2F0h+var_35C]; void *
0x18001025f  call    memset_0
0x180010264  cmp     [rbp+2F0h+var_360], ebx
0x180010267  jz      short loc_18001028C
0x180010269  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180010270  jz      short loc_18001028C
0x180010272  mov     r9d, [rsp+3F0h+var_388]
0x180010277  mov     r8, [rbp+2F0h+var_370]
0x18001027b  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x180010282  mov     ecx, 2; int
0x180010287  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001028c  mov     esi, cs:?g_DebugTraceComponent@@3KA; ulong g_DebugTraceComponent
0x180010292  and     esi, 1
0x180010295  mov     qword ptr [rbp+2F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18001029d  lea     rdx, [rbp+2F0h+Pid+4]; Pid
0x1800102a1  xor     ecx, ecx; Binding
0x1800102a3  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x1800102aa  nop     dword ptr [rax+rax+00h]
0x1800102af  mov     edi, eax
0x1800102b1  test    eax, eax
0x1800102b3  jle     short loc_1800102BE
0x1800102b5  movzx   edi, ax
0x1800102b8  or      edi, 80070000h
0x1800102be  test    edi, edi
0x1800102c0  js      loc_18001037A
0x1800102c6  lea     rdx, [rbp+2F0h+Pid]; pSessionId
0x1800102ca  mov     ecx, [rbp+2F0h+Pid+4]; dwProcessId
0x1800102cd  call    cs:__imp_ProcessIdToSessionId
0x1800102d4  nop     dword ptr [rax+rax+00h]
0x1800102d9  test    esi, esi
0x1800102db  jz      loc_18001037A
0x1800102e1  mov     r8d, [rbp+2F0h+Pid+4]; dwProcessId
0x1800102e5  xor     edx, edx; bInheritHandle
0x1800102e7  mov     ecx, 400h; dwDesiredAccess
0x1800102ec  call    cs:__imp_OpenProcess
0x1800102f3  nop     dword ptr [rax+rax+00h]
0x1800102f8  mov     rsi, rax
0x1800102fb  test    rax, rax
0x1800102fe  jz      short loc_18001037A
0x180010300  mov     [rsp+3F0h+ReturnLength], r13; ReturnLength
0x180010305  mov     r9d, 110h; ProcessInformationLength
0x18001030b  lea     r8, [rbp+2F0h+ProcessInformation]; ProcessInformation
0x180010312  mov     edx, 1Bh; ProcessInformationClass
0x180010317  mov     rcx, rax; ProcessHandle
0x18001031a  call    cs:__imp_NtQueryInformationProcess
0x180010321  nop     dword ptr [rax+rax+00h]
0x180010326  mov     edi, eax
0x180010328  or      edi, 10000000h
0x18001032e  jl      short loc_18001036B
0x180010330  mov     edx, 5Ch ; '\'; Ch
0x180010335  mov     rcx, [rbp+2F0h+Str]; Str
0x18001033c  call    cs:__imp_wcsrchr
0x180010343  nop     dword ptr [rax+rax+00h]
0x180010348  test    rax, rax
0x18001034b  jnz     short loc_180010356
0x18001034d  mov     rax, [rbp+2F0h+Str]
0x180010354  jmp     short loc_18001035A
0x180010356  add     rax, 2
0x18001035a  mov     r8, rax; unsigned __int16 *
0x18001035d  mov     edx, 104h; unsigned __int64
0x180010362  lea     rcx, [rbp+2F0h+var_35C]; unsigned __int16 *
0x180010366  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001036b  mov     rcx, rsi; hObject
0x18001036e  call    cs:__imp_CloseHandle
0x180010375  nop     dword ptr [rax+rax+00h]
0x18001037a  cmp     [rbp+2F0h+var_360], ebx
0x18001037d  jz      short loc_1800103CA
0x18001037f  test    edi, edi
0x180010381  js      short loc_1800103B0
0x180010383  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18001038a  jz      short loc_1800103CA
0x18001038c  lea     rax, [rbp+2F0h+var_35C]
0x180010390  mov     [rsp+3F0h+ReturnLength], rax
0x180010395  mov     r9d, [rbp+2F0h+Pid]
0x180010399  mov     r8d, [rbp+2F0h+Pid+4]
0x18001039d  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x1800103a4  mov     ecx, 2; int
0x1800103a9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800103ae  jmp     short loc_1800103CA
0x1800103b0  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x1800103b7  jz      short loc_1800103CA
0x1800103b9  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x1800103c0  mov     ecx, 2; int
0x1800103c5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800103ca  mov     r8d, 10h; Size
0x1800103d0  mov     rdx, r14; Buf2
0x1800103d3  lea     rcx, PROPERTY_TYPE_AUDIOENUM_DLL; Buf1
0x1800103da  call    memcmp_0
0x1800103df  test    eax, eax
0x1800103e1  jz      short loc_180010429
0x1800103e3  mov     r8d, 10h; Size
0x1800103e9  mov     rdx, r14; Buf2
0x1800103ec  lea     rcx, PROPERTY_TYPE_TS_LICENSETYPE_GUID; Buf1
0x1800103f3  call    memcmp_0
0x1800103f8  test    eax, eax
0x1800103fa  jz      short loc_180010429
0x1800103fc  mov     r8d, 10h; Size
0x180010402  mov     rdx, r14; Buf2
0x180010405  lea     rcx, PROPERTY_TYPE_CLIENT_ALLOWS_AUDIO_CAPTURE_CLSID; Buf1
0x18001040c  call    memcmp_0
0x180010411  test    eax, eax
0x180010413  jz      short loc_180010429
0x180010415  mov     edi, 80070005h
0x18001041a  mov     r8d, edi
0x18001041d  lea     rdx, aInvalidPropert; "Invalid Property Type failed: 0x%x in %"...
0x180010424  jmp     loc_180010675
0x180010429  mov     [rsp+3F0h+TokenHandle], r13
0x18001042e  xor     ecx, ecx; BindingHandle
0x180010430  call    cs:__imp_RpcImpersonateClient
0x180010437  nop     dword ptr [rax+rax+00h]
0x18001043c  mov     edi, eax
0x18001043e  test    eax, eax
0x180010440  jle     short loc_18001044B
0x180010442  movzx   edi, ax
0x180010445  or      edi, 80070000h
0x18001044b  test    edi, edi
0x18001044d  jns     short loc_18001045B
0x18001044f  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x180010456  jmp     loc_1800104EC
0x18001045b  call    cs:__imp_GetCurrentThread
0x180010462  nop     dword ptr [rax+rax+00h]
0x180010467  mov     rcx, rax; ThreadHandle
0x18001046a  lea     r9, [rsp+3F0h+TokenHandle]; TokenHandle
0x18001046f  mov     edx, 0Eh; DesiredAccess
0x180010474  mov     r8d, 1; OpenAsSelf
0x18001047a  call    cs:__imp_OpenThreadToken
0x180010481  nop     dword ptr [rax+rax+00h]
0x180010486  test    eax, eax
0x180010488  jnz     short loc_1800104A7
0x18001048a  call    cs:__imp_GetLastError
0x180010491  nop     dword ptr [rax+rax+00h]
0x180010496  mov     edi, eax
0x180010498  test    eax, eax
0x18001049a  jle     short loc_1800104AA
0x18001049c  movzx   edi, ax
0x18001049f  or      edi, 80070000h
0x1800104a5  jmp     short loc_1800104AA
0x1800104a7  mov     edi, r13d
0x1800104aa  call    cs:__imp_RpcRevertToSelf
0x1800104b1  nop     dword ptr [rax+rax+00h]
0x1800104b6  test    eax, eax
0x1800104b8  jle     short loc_1800104C4
0x1800104ba  movzx   eax, ax
0x1800104bd  or      eax, 80070000h
0x1800104c2  test    eax, eax
0x1800104c4  jns     short loc_1800104E1
0x1800104c6  mov     r8d, eax
0x1800104c9  lea     rdx, aRpcreverttosel_1; "RpcRevertToSelf failed: 0x%x"
0x1800104d0  mov     ecx, 8; int
0x1800104d5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800104da  mov     edi, 80070005h
0x1800104df  jmp     short loc_180010500
0x1800104e1  test    edi, edi
0x1800104e3  jns     short loc_18001051B
0x1800104e5  lea     rdx, aOpenthreadtoke; "OpenThreadToken failed: 0x%x in %s"
0x1800104ec  lea     r9, aCrpcutilsGetcl; "CRpcUtils::GetClientToken"
0x1800104f3  mov     r8d, edi
0x1800104f6  mov     ecx, 8; int
0x1800104fb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180010500  mov     rax, [rsp+3F0h+TokenHandle]
0x180010505  test    rax, rax
0x180010508  jz      short loc_180010520
0x18001050a  mov     rcx, rax; hObject
0x18001050d  call    cs:__imp_CloseHandle
0x180010514  nop     dword ptr [rax+rax+00h]
0x180010519  jmp     short loc_180010523
0x18001051b  mov     rax, [rsp+3F0h+TokenHandle]
0x180010520  mov     rbx, rax
0x180010523  test    edi, edi
0x180010525  jns     short loc_180010536
0x180010527  mov     r8d, edi
0x18001052a  lea     rdx, aCrpcutilsGetcl_0; "CRpcUtils::GetClientToken failed: 0x%x "...
0x180010531  jmp     loc_180010675
0x180010536  mov     esi, r13d
0x180010539  mov     [rsp+3F0h+hObject], r13
0x18001053e  mov     [rsp+3F0h+TokenInformation], r13d
0x180010543  mov     [rsp+3F0h+var_3B4], r13d
0x180010548  mov     edi, r13d
0x18001054b  test    rbx, rbx
0x18001054e  jnz     short loc_1800105C2
0x180010550  call    cs:__imp_GetCurrentThread
0x180010557  nop     dword ptr [rax+rax+00h]
0x18001055c  lea     r9, [rsp+3F0h+hObject]; TokenHandle
0x180010561  mov     edx, 8; DesiredAccess
0x180010566  mov     r8d, 1; OpenAsSelf
0x18001056c  mov     rcx, rax; ThreadHandle
0x18001056f  call    cs:__imp_OpenThreadToken
0x180010576  nop     dword ptr [rax+rax+00h]
0x18001057b  test    eax, eax
0x18001057d  jnz     short loc_1800105BB
0x18001057f  call    cs:__imp_GetLastError
0x180010586  nop     dword ptr [rax+rax+00h]
0x18001058b  mov     edi, eax
0x18001058d  test    eax, eax
0x18001058f  jle     short loc_18001059A
0x180010591  movzx   edi, ax
0x180010594  or      edi, 80070000h
0x18001059a  test    edi, edi
0x18001059c  jns     short loc_1800105BB
0x18001059e  lea     r9, aCutilsGetusers_1; "CUtils::GetUserSessionId"
0x1800105a5  mov     r8d, edi
0x1800105a8  lea     rdx, aOpenthreadtoke; "OpenThreadToken failed: 0x%x in %s"
0x1800105af  mov     ecx, 8; int
0x1800105b4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800105b9  jmp     short loc_18001062F
0x1800105bb  mov     rcx, [rsp+3F0h+hObject]
0x1800105c0  jmp     short loc_1800105C5
0x1800105c2  mov     rcx, rbx; TokenHandle
0x1800105c5  lea     rax, [rsp+3F0h+var_3B4]
0x1800105ca  mov     [rsp+3F0h+ReturnLength], rax; ReturnLength
0x1800105cf  mov     r9d, 4; TokenInformationLength
  ... truncated ...
```
