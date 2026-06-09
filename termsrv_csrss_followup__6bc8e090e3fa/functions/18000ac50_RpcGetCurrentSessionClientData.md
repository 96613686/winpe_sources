# RpcGetCurrentSessionClientData

- ea: `0x18000ac50`
- end: `0x18000b2a0`
- name: `RpcGetCurrentSessionClientData`
- size: `1616`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009940`
- `0x18000ac50`
- `0x18000b2b0`
- `0x18000faf0`
- `0x180012070`
- `0x180012d10`
- `0x1800154a0`
- `0x180033f60`
- `0x180034e64`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000aeba`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000aeba`
- `ntdll!NtQueryInformationProcess` at `0x18000ae98`
- `ntdll!NtQueryInformationProcess` at `0x18000ae98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000afaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b123`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b24e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000afaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b123`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b24e`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000ae4b`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000ae4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000af7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b084`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000af7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b084`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000af9a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000b0a3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000af9a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000b0a3`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000b218`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000b23e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000b218`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000b23e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aeec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b030`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b16d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b267`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aeec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b030`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b16d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b267`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000ae21`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000ae21`
- `RPCRT4!RpcRevertToSelf` at `0x18000afca`
- `RPCRT4!RpcRevertToSelf` at `0x18000afca`
- `RPCRT4!RpcImpersonateClient` at `0x18000af50`
- `RPCRT4!RpcImpersonateClient` at `0x18000af50`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000ae6a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000ae6a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b113`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b113`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000acba`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000acba`

## string_xrefs

- `0x18000b054`: `CRpcUtils::GetClientToken failed: 0x%x in %s`
- `0x18000af6f`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18000b00c`: `CRpcUtils::GetClientToken`
- `0x18000b1e5`: `%s with Trace ID 0x%x Completed`
- `0x18000b14c`: `GetTokenInformation failed: 0x%x in %s`
- `0x18000b005`: `OpenThreadToken failed: 0x%x in %s`
- `0x18000b0dc`: `OpenThreadToken failed: 0x%x in %s`
- `0x18000ad31`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18000af1c`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RpcGetCurrentSessionClientData(__int64 a1, __int64 a2, __int64 a3)
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
0x18000ac50  mov     [rsp-8+arg_18], rbx
0x18000ac55  push    rbp
0x18000ac56  push    rsi
0x18000ac57  push    rdi
0x18000ac58  push    r12
0x18000ac5a  push    r13
0x18000ac5c  push    r14
0x18000ac5e  push    r15
0x18000ac60  lea     rbp, [rsp-2C0h]
0x18000ac68  sub     rsp, 3C0h
0x18000ac6f  mov     rax, cs:__security_cookie
0x18000ac76  xor     rax, rsp
0x18000ac79  mov     [rbp+2F0h+var_40], rax
0x18000ac80  mov     r12, r8
0x18000ac83  mov     r15, rdx
0x18000ac86  mov     r14, rcx
0x18000ac89  lea     rsi, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000ac90  mov     [rsp+3F0h+var_3A0], rsi
0x18000ac95  mov     [rsp+3F0h+var_384], 1
0x18000ac9d  xor     r13d, r13d
0x18000aca0  mov     [rsp+3F0h+var_380], r13
0x18000aca5  lea     rbx, aRpcgetcurrents_2; "RpcGetCurrentSessionClientData"
0x18000acac  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r13d; int CTraceBase::g_bEnabled
0x18000acb3  jnz     short loc_18000ACDE
0x18000acb5  lea     rcx, [rsp+3F0h+pguid]; pguid
0x18000acba  call    cs:__imp_CoCreateGuid
0x18000acc1  nop     dword ptr [rax+rax+00h]
0x18000acc6  mov     eax, 1
0x18000accb  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x18000acd3  inc     eax
0x18000acd5  mov     [rsp+3F0h+var_388], eax
0x18000acd9  jmp     loc_18000ADAF
0x18000acde  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000ace5  jz      short loc_18000AD08
0x18000ace7  mov     [rsp+3F0h+ReturnLength], rbx
0x18000acec  mov     r9d, 1
0x18000acf2  lea     r8, [rsp+3F0h+var_3A0]
0x18000acf7  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x18000acfe  mov     ecx, 2; int
0x18000ad03  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ad08  mov     [rsp+3F0h+hObject], r13
0x18000ad0d  lea     rcx, [rsp+3F0h+hObject]; struct CTraceBase **
0x18000ad12  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000ad17  test    eax, eax
0x18000ad19  js      short loc_18000AD42
0x18000ad1b  cmp     [rsp+3F0h+hObject], r13
0x18000ad20  jz      short loc_18000AD42
0x18000ad22  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000ad29  jz      short loc_18000AD42
0x18000ad2b  mov     r8d, 1
0x18000ad31  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x18000ad38  mov     ecx, 2; int
0x18000ad3d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ad42  xor     edx, edx; char *
0x18000ad44  xor     ecx, ecx; lpTlsValue
0x18000ad46  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000ad4b  lea     rcx, [rsp+3F0h+var_380]; struct CTraceBase **
0x18000ad50  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000ad55  test    eax, eax
0x18000ad57  js      short loc_18000AD93
0x18000ad59  mov     rcx, [rsp+3F0h+var_380]
0x18000ad5e  test    rcx, rcx
0x18000ad61  jz      short loc_18000AD93
0x18000ad63  mov     rax, [rcx]
0x18000ad66  lea     rdx, [rsp+3F0h+pguid]
0x18000ad6b  mov     rax, [rax+20h]
0x18000ad6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad74  mov     rcx, [rsp+3F0h+var_380]
0x18000ad79  mov     rax, [rcx]
0x18000ad7c  mov     rax, [rax+18h]
0x18000ad80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad85  mov     [rsp+3F0h+var_388], eax
0x18000ad89  mov     [rsp+3F0h+var_378], 1
0x18000ad91  jmp     short loc_18000ADB4
0x18000ad93  mov     rdx, rbx; char *
0x18000ad96  lea     rcx, [rsp+3F0h+var_3A0]; lpTlsValue
0x18000ad9b  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000ada0  lea     rdx, [rsp+3F0h+var_388]; unsigned int *
0x18000ada5  lea     rcx, [rsp+3F0h+pguid]; struct _GUID *
0x18000adaa  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x18000adaf  mov     [rsp+3F0h+var_378], r13d
0x18000adb4  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000adbb  mov     [rsp+3F0h+var_3A0], rax
0x18000adc0  mov     [rbp+2F0h+var_370], rbx
0x18000adc4  mov     qword ptr [rbp+2F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000adcc  mov     [rbp+2F0h+var_360], r13d
0x18000add0  xor     edx, edx; Val
0x18000add2  mov     r8d, 208h; Size
0x18000add8  lea     rcx, [rbp+2F0h+var_35C]; void *
0x18000addc  call    memset_0
0x18000ade1  cmp     [rbp+2F0h+var_360], r13d
0x18000ade5  jz      short loc_18000AE0A
0x18000ade7  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000adee  jz      short loc_18000AE0A
0x18000adf0  mov     r9d, [rsp+3F0h+var_388]
0x18000adf5  mov     r8, [rbp+2F0h+var_370]
0x18000adf9  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x18000ae00  mov     ecx, 2; int
0x18000ae05  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ae0a  mov     edi, cs:?g_DebugTraceComponent@@3KA; ulong g_DebugTraceComponent
0x18000ae10  and     edi, 1
0x18000ae13  mov     qword ptr [rbp+2F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000ae1b  lea     rdx, [rbp+2F0h+Pid+4]; Pid
0x18000ae1f  xor     ecx, ecx; Binding
0x18000ae21  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000ae28  nop     dword ptr [rax+rax+00h]
0x18000ae2d  mov     ebx, eax
0x18000ae2f  test    eax, eax
0x18000ae31  jle     short loc_18000AE3C
0x18000ae33  movzx   ebx, ax
0x18000ae36  or      ebx, 80070000h
0x18000ae3c  test    ebx, ebx
0x18000ae3e  js      loc_18000AEF8
0x18000ae44  lea     rdx, [rbp+2F0h+Pid]; pSessionId
0x18000ae48  mov     ecx, [rbp+2F0h+Pid+4]; dwProcessId
0x18000ae4b  call    cs:__imp_ProcessIdToSessionId
0x18000ae52  nop     dword ptr [rax+rax+00h]
0x18000ae57  test    edi, edi
0x18000ae59  jz      loc_18000AEF8
0x18000ae5f  mov     r8d, [rbp+2F0h+Pid+4]; dwProcessId
0x18000ae63  xor     edx, edx; bInheritHandle
0x18000ae65  mov     ecx, 400h; dwDesiredAccess
0x18000ae6a  call    cs:__imp_OpenProcess
0x18000ae71  nop     dword ptr [rax+rax+00h]
0x18000ae76  mov     rdi, rax
0x18000ae79  test    rax, rax
0x18000ae7c  jz      short loc_18000AEF8
0x18000ae7e  mov     [rsp+3F0h+ReturnLength], r13; ReturnLength
0x18000ae83  mov     r9d, 110h; ProcessInformationLength
0x18000ae89  lea     r8, [rbp+2F0h+ProcessInformation]; ProcessInformation
0x18000ae90  mov     edx, 1Bh; ProcessInformationClass
0x18000ae95  mov     rcx, rax; ProcessHandle
0x18000ae98  call    cs:__imp_NtQueryInformationProcess
0x18000ae9f  nop     dword ptr [rax+rax+00h]
0x18000aea4  mov     ebx, eax
0x18000aea6  or      ebx, 10000000h
0x18000aeac  jl      short loc_18000AEE9
0x18000aeae  mov     edx, 5Ch ; '\'; Ch
0x18000aeb3  mov     rcx, [rbp+2F0h+Str]; Str
0x18000aeba  call    cs:__imp_wcsrchr
0x18000aec1  nop     dword ptr [rax+rax+00h]
0x18000aec6  test    rax, rax
0x18000aec9  jnz     short loc_18000AED4
0x18000aecb  mov     rax, [rbp+2F0h+Str]
0x18000aed2  jmp     short loc_18000AED8
0x18000aed4  add     rax, 2
0x18000aed8  mov     r8, rax; unsigned __int16 *
0x18000aedb  mov     edx, 104h; unsigned __int64
0x18000aee0  lea     rcx, [rbp+2F0h+var_35C]; unsigned __int16 *
0x18000aee4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000aee9  mov     rcx, rdi; hObject
0x18000aeec  call    cs:__imp_CloseHandle
0x18000aef3  nop     dword ptr [rax+rax+00h]
0x18000aef8  cmp     [rbp+2F0h+var_360], r13d
0x18000aefc  jz      short loc_18000AF49
0x18000aefe  test    ebx, ebx
0x18000af00  js      short loc_18000AF2F
0x18000af02  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000af09  jz      short loc_18000AF49
0x18000af0b  lea     rax, [rbp+2F0h+var_35C]
0x18000af0f  mov     [rsp+3F0h+ReturnLength], rax
0x18000af14  mov     r9d, [rbp+2F0h+Pid]
0x18000af18  mov     r8d, [rbp+2F0h+Pid+4]
0x18000af1c  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x18000af23  mov     ecx, 2; int
0x18000af28  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000af2d  jmp     short loc_18000AF49
0x18000af2f  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000af36  jz      short loc_18000AF49
0x18000af38  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x18000af3f  mov     ecx, 2; int
0x18000af44  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000af49  mov     [rsp+3F0h+TokenHandle], r13
0x18000af4e  xor     ecx, ecx; BindingHandle
0x18000af50  call    cs:__imp_RpcImpersonateClient
0x18000af57  nop     dword ptr [rax+rax+00h]
0x18000af5c  mov     edi, eax
0x18000af5e  test    eax, eax
0x18000af60  jle     short loc_18000AF6B
0x18000af62  movzx   edi, ax
0x18000af65  or      edi, 80070000h
0x18000af6b  test    edi, edi
0x18000af6d  jns     short loc_18000AF7B
0x18000af6f  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x18000af76  jmp     loc_18000B00C
0x18000af7b  call    cs:__imp_GetCurrentThread
0x18000af82  nop     dword ptr [rax+rax+00h]
0x18000af87  mov     rcx, rax; ThreadHandle
0x18000af8a  lea     r9, [rsp+3F0h+TokenHandle]; TokenHandle
0x18000af8f  mov     edx, 0Eh; DesiredAccess
0x18000af94  mov     r8d, 1; OpenAsSelf
0x18000af9a  call    cs:__imp_OpenThreadToken
0x18000afa1  nop     dword ptr [rax+rax+00h]
0x18000afa6  test    eax, eax
0x18000afa8  jnz     short loc_18000AFC7
0x18000afaa  call    cs:__imp_GetLastError
0x18000afb1  nop     dword ptr [rax+rax+00h]
0x18000afb6  mov     edi, eax
0x18000afb8  test    eax, eax
0x18000afba  jle     short loc_18000AFCA
0x18000afbc  movzx   edi, ax
0x18000afbf  or      edi, 80070000h
0x18000afc5  jmp     short loc_18000AFCA
0x18000afc7  mov     edi, r13d
0x18000afca  call    cs:__imp_RpcRevertToSelf
0x18000afd1  nop     dword ptr [rax+rax+00h]
0x18000afd6  test    eax, eax
0x18000afd8  jle     short loc_18000AFE4
0x18000afda  movzx   eax, ax
0x18000afdd  or      eax, 80070000h
0x18000afe2  test    eax, eax
0x18000afe4  jns     short loc_18000B001
0x18000afe6  mov     r8d, eax
0x18000afe9  lea     rdx, aRpcreverttosel_1; "RpcRevertToSelf failed: 0x%x"
0x18000aff0  mov     ecx, 8; int
0x18000aff5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000affa  mov     edi, 80070005h
0x18000afff  jmp     short loc_18000B020
0x18000b001  test    edi, edi
0x18000b003  jns     short loc_18000B03E
0x18000b005  lea     rdx, aOpenthreadtoke; "OpenThreadToken failed: 0x%x in %s"
0x18000b00c  lea     r9, aCrpcutilsGetcl; "CRpcUtils::GetClientToken"
0x18000b013  mov     r8d, edi
0x18000b016  mov     ecx, 8; int
0x18000b01b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b020  mov     rax, [rsp+3F0h+TokenHandle]
0x18000b025  test    rax, rax
0x18000b028  jz      short loc_18000B043
0x18000b02a  mov     rbx, r13
0x18000b02d  mov     rcx, rax; hObject
0x18000b030  call    cs:__imp_CloseHandle
0x18000b037  nop     dword ptr [rax+rax+00h]
0x18000b03c  jmp     short loc_18000B046
0x18000b03e  mov     rax, [rsp+3F0h+TokenHandle]
0x18000b043  mov     rbx, rax
0x18000b046  test    edi, edi
0x18000b048  jns     short loc_18000B06A
0x18000b04a  lea     r9, aRpcgetcurrents_2; "RpcGetCurrentSessionClientData"
0x18000b051  mov     r8d, edi
0x18000b054  lea     rdx, aCrpcutilsGetcl_0; "CRpcUtils::GetClientToken failed: 0x%x "...
0x18000b05b  mov     ecx, 8; int
0x18000b060  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b065  jmp     loc_18000B1C1
0x18000b06a  mov     esi, r13d
0x18000b06d  mov     [rsp+3F0h+hObject], r13
0x18000b072  mov     [rsp+3F0h+TokenInformation], r13d
0x18000b077  mov     [rsp+3F0h+var_3B4], r13d
0x18000b07c  mov     edi, r13d
0x18000b07f  test    rbx, rbx
0x18000b082  jnz     short loc_18000B0F6
0x18000b084  call    cs:__imp_GetCurrentThread
0x18000b08b  nop     dword ptr [rax+rax+00h]
0x18000b090  lea     r9, [rsp+3F0h+hObject]; TokenHandle
0x18000b095  mov     edx, 8; DesiredAccess
0x18000b09a  mov     r8d, 1; OpenAsSelf
0x18000b0a0  mov     rcx, rax; ThreadHandle
0x18000b0a3  call    cs:__imp_OpenThreadToken
0x18000b0aa  nop     dword ptr [rax+rax+00h]
0x18000b0af  test    eax, eax
0x18000b0b1  jnz     short loc_18000B0EF
0x18000b0b3  call    cs:__imp_GetLastError
0x18000b0ba  nop     dword ptr [rax+rax+00h]
0x18000b0bf  mov     edi, eax
0x18000b0c1  test    eax, eax
0x18000b0c3  jle     short loc_18000B0CE
0x18000b0c5  movzx   edi, ax
0x18000b0c8  or      edi, 80070000h
0x18000b0ce  test    edi, edi
0x18000b0d0  jns     short loc_18000B0EF
0x18000b0d2  lea     r9, aCutilsGetusers_1; "CUtils::GetUserSessionId"
0x18000b0d9  mov     r8d, edi
0x18000b0dc  lea     rdx, aOpenthreadtoke; "OpenThreadToken failed: 0x%x in %s"
0x18000b0e3  mov     ecx, 8; int
0x18000b0e8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b0ed  jmp     short loc_18000B163
0x18000b0ef  mov     rcx, [rsp+3F0h+hObject]
0x18000b0f4  jmp     short loc_18000B0F9
0x18000b0f6  mov     rcx, rbx; TokenHandle
0x18000b0f9  lea     rax, [rsp+3F0h+var_3B4]
0x18000b0fe  mov     [rsp+3F0h+ReturnLength], rax; ReturnLength
0x18000b103  mov     r9d, 4; TokenInformationLength
0x18000b109  lea     r8, [rsp+3F0h+TokenInformation]; TokenInformation
0x18000b10e  mov     edx, 0Ch; TokenInformationClass
0x18000b113  call    cs:__imp_GetTokenInformation
0x18000b11a  nop     dword ptr [rax+rax+00h]
0x18000b11f  test    eax, eax
0x18000b121  jnz     short loc_18000B15F
0x18000b123  call    cs:__imp_GetLastError
0x18000b12a  nop     dword ptr [rax+rax+00h]
0x18000b12f  mov     edi, eax
0x18000b131  test    eax, eax
0x18000b133  jle     short loc_18000B13E
0x18000b135  movzx   edi, ax
0x18000b138  or      edi, 80070000h
0x18000b13e  test    edi, edi
0x18000b140  jns     short loc_18000B15F
0x18000b142  lea     r9, aCutilsGetusers_1; "CUtils::GetUserSessionId"
0x18000b149  mov     r8d, edi
0x18000b14c  lea     rdx, aGettokeninform_3; "GetTokenInformation failed: 0x%x in %s"
0x18000b153  mov     ecx, 8; int
  ... truncated ...
```
