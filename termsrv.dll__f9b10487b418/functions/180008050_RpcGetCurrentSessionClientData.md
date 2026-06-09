# RpcGetCurrentSessionClientData

- ea: `0x180008050`
- end: `0x18000860c`
- name: `RpcGetCurrentSessionClientData`
- size: `1468`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _DWORD *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007870`
- `0x180008050`
- `0x18000a210`
- `0x18000f790`
- `0x1800119a0`
- `0x1800127b0`
- `0x180014de0`
- `0x1800321f0`
- `0x1800330c4`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000829c`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000829c`
- `ntdll!NtQueryInformationProcess` at `0x180008280`
- `ntdll!NtQueryInformationProcess` at `0x180008280`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000836b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008456`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000836b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008456`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085c7`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000823f`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000823f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008348`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008433`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008348`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008433`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008361`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000844c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008361`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000844c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800085a3`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800085bd`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800085a3`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800085bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800082c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800083e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800084fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800085da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800082c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800083e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800084fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800085da`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000821b`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000821b`
- `RPCRT4!RpcRevertToSelf` at `0x180008385`
- `RPCRT4!RpcRevertToSelf` at `0x180008385`
- `RPCRT4!RpcImpersonateClient` at `0x180008326`
- `RPCRT4!RpcImpersonateClient` at `0x180008326`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008258`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008258`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800084b0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800084b0`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800080ba`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800080ba`

## string_xrefs

- `0x180008403`: `CRpcUtils::GetClientToken failed: 0x%x in %s`
- `0x18000833f`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x1800083c1`: `CRpcUtils::GetClientToken`
- `0x180008570`: `%s with Trace ID 0x%x Completed`
- `0x1800084dd`: `GetTokenInformation failed: 0x%x in %s`
- `0x1800083ba`: `OpenThreadToken failed: 0x%x in %s`
- `0x180008479`: `OpenThreadToken failed: 0x%x in %s`
- `0x18000812b`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x1800082f2`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RpcGetCurrentSessionClientData(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  unsigned int v6; // edi
  RPC_STATUS v7; // eax
  int v8; // ebx
  HANDLE v9; // rax
  void *v10; // rdi
  NTSTATUS InformationProcess; // eax
  wchar_t *v12; // rax
  wchar_t *v13; // rax
  RPC_STATUS v14; // eax
  signed int v15; // edi
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  int v18; // eax
  bool v19; // sf
  void *v20; // rax
  void *v21; // rbx
  unsigned int v22; // esi
  HANDLE v23; // rax
  signed int v24; // eax
  HANDLE v25; // rcx
  signed int v26; // eax
  int ClientData; // eax
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
    _DbgPrintMessage(2, "Adding trace %p, %d, %s", &v33, 1, "RpcGetCurrentSessionClientData");
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
    CTraceBase::ResetThreadCurrentOperationTrace((struct CTraceBase *)&v33, "RpcGetCurrentSessionClientData");
    CTraceBase::GenerateTraceID(&pguid, v35);
    goto LABEL_13;
  }
  (*(void (__fastcall **)(struct CTraceBase *, GUID *))(*(_QWORD *)v36 + 32LL))(v36, &pguid);
  v35[0] = (*(__int64 (__fastcall **)(struct CTraceBase *))(*(_QWORD *)v36 + 24LL))(v36);
  v37 = 1;
LABEL_14:
  v33 = &CRpcCallTrace::`vftable';
  v38 = "RpcGetCurrentSessionClientData";
  *(_QWORD *)Pid = -1;
  v40 = 0;
  memset_0(v41, 0, 0x208u);
  if ( v40 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "TRACE RPC %s with Trace ID 0x%x", v38, v35[0]);
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
          StringCchCopyW(v41, 0x104u, v13);
        }
        CloseHandle(v10);
      }
    }
  }
  if ( v40 )
  {
    if ( v8 < 0 )
    {
      if ( (g_DebugTraceComponent & 1) != 0 )
        _DbgPrintMessage(2, "RPC Caller: Unknown");
    }
    else if ( (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(2, "RPC Caller: PID %d, SessID %d, Process Name: <%S>", Pid[1], Pid[0], v41);
    }
  }
  TokenHandle = 0;
  v14 = RpcImpersonateClient(0);
  v15 = v14;
  if ( v14 > 0 )
    v15 = (unsigned __int16)v14 | 0x80070000;
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
    v18 = RpcRevertToSelf();
    v19 = v18 < 0;
    if ( v18 > 0 )
    {
      v18 = (unsigned __int16)v18 | 0x80070000;
      v19 = v18 < 0;
    }
    if ( v19 )
    {
      _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v18);
      v15 = -2147024891;
    }
    else
    {
      if ( v15 >= 0 )
      {
        v20 = TokenHandle;
        goto LABEL_51;
      }
      _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x in %s", (unsigned int)v15, "CRpcUtils::GetClientToken");
    }
  }
  else
  {
    _DbgPrintMessage(8, "RpcImpersonateClient failed: 0x%x in %s", (unsigned int)v15, "CRpcUtils::GetClientToken");
  }
  v20 = TokenHandle;
  if ( TokenHandle )
  {
    v21 = 0;
    CloseHandle(TokenHandle);
    goto LABEL_52;
  }
LABEL_51:
  v21 = v20;
LABEL_52:
  if ( v15 < 0 )
  {
    _DbgPrintMessage(8, "CRpcUtils::GetClientToken failed: 0x%x in %s", v15, "RpcGetCurrentSessionClientData");
    goto LABEL_74;
  }
  v22 = 0;
  hObject = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  v15 = 0;
  if ( v21 )
  {
    v25 = v21;
    goto LABEL_62;
  }
  v23 = GetCurrentThread();
  if ( OpenThreadToken(v23, 8u, 1, &hObject) )
    goto LABEL_60;
  v24 = GetLastError();
  v15 = v24;
  if ( v24 > 0 )
    v15 = (unsigned __int16)v24 | 0x80070000;
  if ( v15 >= 0 )
  {
LABEL_60:
    v25 = hObject;
LABEL_62:
    if ( GetTokenInformation(v25, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
      goto LABEL_67;
    v26 = GetLastError();
    v15 = v26;
    if ( v26 > 0 )
      v15 = (unsigned __int16)v26 | 0x80070000;
    if ( v15 >= 0 )
LABEL_67:
      v22 = TokenInformation;
    else
      _DbgPrintMessage(8, "GetTokenInformation failed: 0x%x in %s", v15, "CUtils::GetUserSessionId");
    goto LABEL_68;
  }
  _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x in %s", v15, "CUtils::GetUserSessionId");
LABEL_68:
  if ( hObject )
    CloseHandle(hObject);
  if ( v15 >= 0 )
  {
    ClientData = RpcGetClientData(a1, v22, a2, a3);
    v15 = ClientData;
    if ( ClientData < 0 )
      _DbgPrintMessage(
        8,
        "RpcGetClientData failed: 0x%x in %s",
        (unsigned int)ClientData,
        "RpcGetCurrentSessionClientData");
  }
  else
  {
    _DbgPrintMessage(
      8,
      "CUtils::GetUserSessionId failed: 0x%x in %s",
      (unsigned int)v15,
      "RpcGetCurrentSessionClientData");
  }
LABEL_74:
  v33 = &CRpcCallTrace::`vftable';
  if ( v40 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "%s with Trace ID 0x%x Completed", v38, v35[0]);
  v33 = &CTraceBase::`vftable';
  if ( CTraceBase::g_bEnabled && !v37 && CTraceBase::g_TLSIndex != -1 )
  {
    if ( TlsSetValue(CTraceBase::g_TLSIndex, 0) )
    {
      if ( TlsSetValue(CTraceBase::g_CreatorFunctionTLSIndex, 0) )
        goto LABEL_84;
    }
    else
    {
      GetLastError();
    }
    GetLastError();
  }
LABEL_84:
  v36 = 0;
  if ( v21 )
    CloseHandle(v21);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180008050  mov     [rsp-8+arg_18], rbx
0x180008055  push    rbp
0x180008056  push    rsi
0x180008057  push    rdi
0x180008058  push    r12
0x18000805a  push    r13
0x18000805c  push    r14
0x18000805e  push    r15
0x180008060  lea     rbp, [rsp-2C0h]
0x180008068  sub     rsp, 3C0h
0x18000806f  mov     rax, cs:__security_cookie
0x180008076  xor     rax, rsp
0x180008079  mov     [rbp+2F0h+var_40], rax
0x180008080  mov     r12, r8
0x180008083  mov     r15, rdx
0x180008086  mov     r14, rcx
0x180008089  lea     rsi, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x180008090  mov     [rsp+3F0h+var_3A0], rsi
0x180008095  mov     [rsp+3F0h+var_384], 1
0x18000809d  xor     r13d, r13d
0x1800080a0  mov     [rsp+3F0h+var_380], r13
0x1800080a5  lea     rbx, aRpcgetcurrents_2; "RpcGetCurrentSessionClientData"
0x1800080ac  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r13d; int CTraceBase::g_bEnabled
0x1800080b3  jnz     short loc_1800080D8
0x1800080b5  lea     rcx, [rsp+3F0h+pguid]; pguid
0x1800080ba  call    cs:__imp_CoCreateGuid
0x1800080c0  mov     eax, 1
0x1800080c5  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x1800080cd  inc     eax
0x1800080cf  mov     [rsp+3F0h+var_388], eax
0x1800080d3  jmp     loc_1800081A9
0x1800080d8  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x1800080df  jz      short loc_180008102
0x1800080e1  mov     [rsp+3F0h+ReturnLength], rbx
0x1800080e6  mov     r9d, 1
0x1800080ec  lea     r8, [rsp+3F0h+var_3A0]
0x1800080f1  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x1800080f8  mov     ecx, 2; int
0x1800080fd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008102  mov     [rsp+3F0h+hObject], r13
0x180008107  lea     rcx, [rsp+3F0h+hObject]; struct CTraceBase **
0x18000810c  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x180008111  test    eax, eax
0x180008113  js      short loc_18000813C
0x180008115  cmp     [rsp+3F0h+hObject], r13
0x18000811a  jz      short loc_18000813C
0x18000811c  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180008123  jz      short loc_18000813C
0x180008125  mov     r8d, 1
0x18000812b  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x180008132  mov     ecx, 2; int
0x180008137  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000813c  xor     edx, edx; char *
0x18000813e  xor     ecx, ecx; lpTlsValue
0x180008140  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x180008145  lea     rcx, [rsp+3F0h+var_380]; struct CTraceBase **
0x18000814a  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000814f  test    eax, eax
0x180008151  js      short loc_18000818D
0x180008153  mov     rcx, [rsp+3F0h+var_380]
0x180008158  test    rcx, rcx
0x18000815b  jz      short loc_18000818D
0x18000815d  mov     rax, [rcx]
0x180008160  lea     rdx, [rsp+3F0h+pguid]
0x180008165  mov     rax, [rax+20h]
0x180008169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000816e  mov     rcx, [rsp+3F0h+var_380]
0x180008173  mov     rax, [rcx]
0x180008176  mov     rax, [rax+18h]
0x18000817a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000817f  mov     [rsp+3F0h+var_388], eax
0x180008183  mov     [rsp+3F0h+var_378], 1
0x18000818b  jmp     short loc_1800081AE
0x18000818d  mov     rdx, rbx; char *
0x180008190  lea     rcx, [rsp+3F0h+var_3A0]; lpTlsValue
0x180008195  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000819a  lea     rdx, [rsp+3F0h+var_388]; unsigned int *
0x18000819f  lea     rcx, [rsp+3F0h+pguid]; struct _GUID *
0x1800081a4  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x1800081a9  mov     [rsp+3F0h+var_378], r13d
0x1800081ae  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x1800081b5  mov     [rsp+3F0h+var_3A0], rax
0x1800081ba  mov     [rbp+2F0h+var_370], rbx
0x1800081be  mov     qword ptr [rbp+2F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x1800081c6  mov     [rbp+2F0h+var_360], r13d
0x1800081ca  xor     edx, edx; Val
0x1800081cc  mov     r8d, 208h; Size
0x1800081d2  lea     rcx, [rbp+2F0h+var_35C]; void *
0x1800081d6  call    memset_0
0x1800081db  cmp     [rbp+2F0h+var_360], r13d
0x1800081df  jz      short loc_180008204
0x1800081e1  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x1800081e8  jz      short loc_180008204
0x1800081ea  mov     r9d, [rsp+3F0h+var_388]
0x1800081ef  mov     r8, [rbp+2F0h+var_370]
0x1800081f3  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x1800081fa  mov     ecx, 2; int
0x1800081ff  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008204  mov     edi, cs:?g_DebugTraceComponent@@3KA; ulong g_DebugTraceComponent
0x18000820a  and     edi, 1
0x18000820d  mov     qword ptr [rbp+2F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x180008215  lea     rdx, [rbp+2F0h+Pid+4]; Pid
0x180008219  xor     ecx, ecx; Binding
0x18000821b  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180008221  mov     ebx, eax
0x180008223  test    eax, eax
0x180008225  jle     short loc_180008230
0x180008227  movzx   ebx, ax
0x18000822a  or      ebx, 80070000h
0x180008230  test    ebx, ebx
0x180008232  js      loc_1800082CE
0x180008238  lea     rdx, [rbp+2F0h+Pid]; pSessionId
0x18000823c  mov     ecx, [rbp+2F0h+Pid+4]; dwProcessId
0x18000823f  call    cs:__imp_ProcessIdToSessionId
0x180008245  test    edi, edi
0x180008247  jz      loc_1800082CE
0x18000824d  mov     r8d, [rbp+2F0h+Pid+4]; dwProcessId
0x180008251  xor     edx, edx; bInheritHandle
0x180008253  mov     ecx, 400h; dwDesiredAccess
0x180008258  call    cs:__imp_OpenProcess
0x18000825e  mov     rdi, rax
0x180008261  test    rax, rax
0x180008264  jz      short loc_1800082CE
0x180008266  mov     [rsp+3F0h+ReturnLength], r13; ReturnLength
0x18000826b  mov     r9d, 110h; ProcessInformationLength
0x180008271  lea     r8, [rbp+2F0h+ProcessInformation]; ProcessInformation
0x180008278  mov     edx, 1Bh; ProcessInformationClass
0x18000827d  mov     rcx, rax; ProcessHandle
0x180008280  call    cs:__imp_NtQueryInformationProcess
0x180008286  mov     ebx, eax
0x180008288  or      ebx, 10000000h
0x18000828e  jl      short loc_1800082C5
0x180008290  mov     edx, 5Ch ; '\'; Ch
0x180008295  mov     rcx, [rbp+2F0h+Str]; Str
0x18000829c  call    cs:__imp_wcsrchr
0x1800082a2  test    rax, rax
0x1800082a5  jnz     short loc_1800082B0
0x1800082a7  mov     rax, [rbp+2F0h+Str]
0x1800082ae  jmp     short loc_1800082B4
0x1800082b0  add     rax, 2
0x1800082b4  mov     r8, rax; unsigned __int16 *
0x1800082b7  mov     edx, 104h; unsigned __int64
0x1800082bc  lea     rcx, [rbp+2F0h+var_35C]; unsigned __int16 *
0x1800082c0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800082c5  mov     rcx, rdi; hObject
0x1800082c8  call    cs:__imp_CloseHandle
0x1800082ce  cmp     [rbp+2F0h+var_360], r13d
0x1800082d2  jz      short loc_18000831F
0x1800082d4  test    ebx, ebx
0x1800082d6  js      short loc_180008305
0x1800082d8  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x1800082df  jz      short loc_18000831F
0x1800082e1  lea     rax, [rbp+2F0h+var_35C]
0x1800082e5  mov     [rsp+3F0h+ReturnLength], rax
0x1800082ea  mov     r9d, [rbp+2F0h+Pid]
0x1800082ee  mov     r8d, [rbp+2F0h+Pid+4]
0x1800082f2  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x1800082f9  mov     ecx, 2; int
0x1800082fe  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008303  jmp     short loc_18000831F
0x180008305  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000830c  jz      short loc_18000831F
0x18000830e  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x180008315  mov     ecx, 2; int
0x18000831a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000831f  mov     [rsp+3F0h+TokenHandle], r13
0x180008324  xor     ecx, ecx; BindingHandle
0x180008326  call    cs:__imp_RpcImpersonateClient
0x18000832c  mov     edi, eax
0x18000832e  test    eax, eax
0x180008330  jle     short loc_18000833B
0x180008332  movzx   edi, ax
0x180008335  or      edi, 80070000h
0x18000833b  test    edi, edi
0x18000833d  jns     short loc_180008348
0x18000833f  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x180008346  jmp     short loc_1800083C1
0x180008348  call    cs:__imp_GetCurrentThread
0x18000834e  mov     rcx, rax; ThreadHandle
0x180008351  lea     r9, [rsp+3F0h+TokenHandle]; TokenHandle
0x180008356  mov     edx, 0Eh; DesiredAccess
0x18000835b  mov     r8d, 1; OpenAsSelf
0x180008361  call    cs:__imp_OpenThreadToken
0x180008367  test    eax, eax
0x180008369  jnz     short loc_180008382
0x18000836b  call    cs:__imp_GetLastError
0x180008371  mov     edi, eax
0x180008373  test    eax, eax
0x180008375  jle     short loc_180008385
0x180008377  movzx   edi, ax
0x18000837a  or      edi, 80070000h
0x180008380  jmp     short loc_180008385
0x180008382  mov     edi, r13d
0x180008385  call    cs:__imp_RpcRevertToSelf
0x18000838b  test    eax, eax
0x18000838d  jle     short loc_180008399
0x18000838f  movzx   eax, ax
0x180008392  or      eax, 80070000h
0x180008397  test    eax, eax
0x180008399  jns     short loc_1800083B6
0x18000839b  mov     r8d, eax
0x18000839e  lea     rdx, aRpcreverttosel_1; "RpcRevertToSelf failed: 0x%x"
0x1800083a5  mov     ecx, 8; int
0x1800083aa  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800083af  mov     edi, 80070005h
0x1800083b4  jmp     short loc_1800083D5
0x1800083b6  test    edi, edi
0x1800083b8  jns     short loc_1800083ED
0x1800083ba  lea     rdx, aOpenthreadtoke; "OpenThreadToken failed: 0x%x in %s"
0x1800083c1  lea     r9, aCrpcutilsGetcl; "CRpcUtils::GetClientToken"
0x1800083c8  mov     r8d, edi
0x1800083cb  mov     ecx, 8; int
0x1800083d0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800083d5  mov     rax, [rsp+3F0h+TokenHandle]
0x1800083da  test    rax, rax
0x1800083dd  jz      short loc_1800083F2
0x1800083df  mov     rbx, r13
0x1800083e2  mov     rcx, rax; hObject
0x1800083e5  call    cs:__imp_CloseHandle
0x1800083eb  jmp     short loc_1800083F5
0x1800083ed  mov     rax, [rsp+3F0h+TokenHandle]
0x1800083f2  mov     rbx, rax
0x1800083f5  test    edi, edi
0x1800083f7  jns     short loc_180008419
0x1800083f9  lea     r9, aRpcgetcurrents_2; "RpcGetCurrentSessionClientData"
0x180008400  mov     r8d, edi
0x180008403  lea     rdx, aCrpcutilsGetcl_0; "CRpcUtils::GetClientToken failed: 0x%x "...
0x18000840a  mov     ecx, 8; int
0x18000840f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008414  jmp     loc_18000854C
0x180008419  mov     esi, r13d
0x18000841c  mov     [rsp+3F0h+hObject], r13
0x180008421  mov     [rsp+3F0h+TokenInformation], r13d
0x180008426  mov     [rsp+3F0h+var_3B4], r13d
0x18000842b  mov     edi, r13d
0x18000842e  test    rbx, rbx
0x180008431  jnz     short loc_180008493
0x180008433  call    cs:__imp_GetCurrentThread
0x180008439  lea     r9, [rsp+3F0h+hObject]; TokenHandle
0x18000843e  mov     edx, 8; DesiredAccess
0x180008443  mov     r8d, 1; OpenAsSelf
0x180008449  mov     rcx, rax; ThreadHandle
0x18000844c  call    cs:__imp_OpenThreadToken
0x180008452  test    eax, eax
0x180008454  jnz     short loc_18000848C
0x180008456  call    cs:__imp_GetLastError
0x18000845c  mov     edi, eax
0x18000845e  test    eax, eax
0x180008460  jle     short loc_18000846B
0x180008462  movzx   edi, ax
0x180008465  or      edi, 80070000h
0x18000846b  test    edi, edi
0x18000846d  jns     short loc_18000848C
0x18000846f  lea     r9, aCutilsGetusers_1; "CUtils::GetUserSessionId"
0x180008476  mov     r8d, edi
0x180008479  lea     rdx, aOpenthreadtoke; "OpenThreadToken failed: 0x%x in %s"
0x180008480  mov     ecx, 8; int
0x180008485  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000848a  jmp     short loc_1800084F4
0x18000848c  mov     rcx, [rsp+3F0h+hObject]
0x180008491  jmp     short loc_180008496
0x180008493  mov     rcx, rbx; TokenHandle
0x180008496  lea     rax, [rsp+3F0h+var_3B4]
0x18000849b  mov     [rsp+3F0h+ReturnLength], rax; ReturnLength
0x1800084a0  mov     r9d, 4; TokenInformationLength
0x1800084a6  lea     r8, [rsp+3F0h+TokenInformation]; TokenInformation
0x1800084ab  mov     edx, 0Ch; TokenInformationClass
0x1800084b0  call    cs:__imp_GetTokenInformation
0x1800084b6  test    eax, eax
0x1800084b8  jnz     short loc_1800084F0
0x1800084ba  call    cs:__imp_GetLastError
0x1800084c0  mov     edi, eax
0x1800084c2  test    eax, eax
0x1800084c4  jle     short loc_1800084CF
0x1800084c6  movzx   edi, ax
0x1800084c9  or      edi, 80070000h
0x1800084cf  test    edi, edi
0x1800084d1  jns     short loc_1800084F0
0x1800084d3  lea     r9, aCutilsGetusers_1; "CUtils::GetUserSessionId"
0x1800084da  mov     r8d, edi
0x1800084dd  lea     rdx, aGettokeninform_3; "GetTokenInformation failed: 0x%x in %s"
0x1800084e4  mov     ecx, 8; int
0x1800084e9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800084ee  jmp     short loc_1800084F4
0x1800084f0  mov     esi, [rsp+3F0h+TokenInformation]
0x1800084f4  mov     rcx, [rsp+3F0h+hObject]; hObject
0x1800084f9  test    rcx, rcx
0x1800084fc  jz      short loc_180008504
0x1800084fe  call    cs:__imp_CloseHandle
0x180008504  test    edi, edi
0x180008506  jns     short loc_180008514
0x180008508  mov     r8d, edi
0x18000850b  lea     rdx, aCutilsGetusers_0; "CUtils::GetUserSessionId failed: 0x%x i"...
0x180008512  jmp     short loc_180008534
0x180008514  mov     r9, r12
0x180008517  mov     r8, r15
0x18000851a  mov     edx, esi
0x18000851c  mov     rcx, r14
0x18000851f  call    RpcGetClientData
0x180008524  mov     edi, eax
  ... truncated ...
```
