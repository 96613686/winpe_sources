# RpcIsListening

- ea: `0x18000b5f0`
- end: `0x18000babf`
- name: `RpcIsListening`
- size: `1231`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a210`
- `0x18000b5f0`
- `0x18000f790`
- `0x1800119a0`
- `0x1800127b0`
- `0x180014de0`
- `0x1800321f0`
- `0x1800330c4`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000b840`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000b840`
- `ntdll!NtQueryInformationProcess` at `0x18000b824`
- `ntdll!NtQueryInformationProcess` at `0x18000b824`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba7a`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000b7e2`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000b7e2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000ba56`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000ba70`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000ba56`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000ba70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b86c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b86c`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000b7bc`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000b7bc`
- `RPCRT4!RpcRevertToSelf` at `0x18000b96c`
- `RPCRT4!RpcRevertToSelf` at `0x18000b96c`
- `RPCRT4!RpcImpersonateClient` at `0x18000b91d`
- `RPCRT4!RpcImpersonateClient` at `0x18000b91d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000b7fc`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000b7fc`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000b657`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000b657`

## string_xrefs

- `0x18000b940`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18000ba23`: `%s with Trace ID 0x%x Completed`
- `0x18000b9ab`: `AccessCheck( QUERY ) failed: 0x%x in %s`
- `0x18000b6c8`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18000b897`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RpcIsListening(__int64 a1, _DWORD *a2)
{
  __int64 v4; // rbx
  unsigned int v5; // esi
  RPC_STATUS v6; // eax
  int v7; // edi
  HANDLE v8; // rax
  void *v9; // rsi
  NTSTATUS InformationProcess; // eax
  wchar_t *v11; // rax
  wchar_t *v12; // rax
  const char *v13; // r8
  signed int v14; // edi
  RPC_STATUS v15; // eax
  int v16; // eax
  bool v17; // sf
  int v18; // eax
  struct CTraceBase *v20; // [rsp+30h] [rbp-D0h] BYREF
  void **v21; // [rsp+40h] [rbp-C0h] BYREF
  GUID pguid; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v23[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct CTraceBase *v24; // [rsp+60h] [rbp-A0h] BYREF
  int v25; // [rsp+68h] [rbp-98h]
  const char *v26; // [rsp+70h] [rbp-90h]
  unsigned int Pid[2]; // [rsp+78h] [rbp-88h] BYREF
  int v28; // [rsp+80h] [rbp-80h]
  unsigned __int16 v29[262]; // [rsp+84h] [rbp-7Ch] BYREF
  _BYTE ProcessInformation[8]; // [rsp+290h] [rbp+190h] BYREF
  wchar_t *Str; // [rsp+298h] [rbp+198h]

  v4 = 0;
  v21 = &CTraceBase::`vftable';
  v23[1] = 1;
  v24 = 0;
  if ( !CTraceBase::g_bEnabled )
  {
    CoCreateGuid(&pguid);
    v23[0] = _InterlockedIncrement((volatile signed __int32 *)&CTraceBase::g_NextShortActivityID);
LABEL_13:
    v25 = 0;
    goto LABEL_14;
  }
  if ( (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "Adding trace %p, %d, %s", &v21, 1, "RpcIsListening");
  v20 = 0;
  if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v20) >= 0 && v20 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(
      2,
      "TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC",
      1);
  CTraceBase::ResetThreadCurrentOperationTrace(0, 0);
  if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v24) < 0 || !v24 )
  {
    CTraceBase::ResetThreadCurrentOperationTrace((struct CTraceBase *)&v21, "RpcIsListening");
    CTraceBase::GenerateTraceID(&pguid, v23);
    goto LABEL_13;
  }
  (*(void (__fastcall **)(struct CTraceBase *, GUID *))(*(_QWORD *)v24 + 32LL))(v24, &pguid);
  v23[0] = (*(__int64 (__fastcall **)(struct CTraceBase *))(*(_QWORD *)v24 + 24LL))(v24);
  v25 = 1;
LABEL_14:
  v21 = &CRpcCallTrace::`vftable';
  v26 = "RpcIsListening";
  *(_QWORD *)Pid = -1;
  v28 = 0;
  memset_0(v29, 0, 0x208u);
  if ( v28 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "TRACE RPC %s with Trace ID 0x%x", v26, v23[0]);
  v5 = g_DebugTraceComponent & 1;
  *(_QWORD *)Pid = -1;
  v6 = I_RpcBindingInqLocalClientPID(0, &Pid[1]);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 >= 0 )
  {
    ProcessIdToSessionId(Pid[1], Pid);
    if ( v5 )
    {
      v8 = OpenProcess(0x400u, 0, Pid[1]);
      v9 = v8;
      if ( v8 )
      {
        InformationProcess = NtQueryInformationProcess(v8, ProcessImageFileName, ProcessInformation, 0x110u, 0);
        v7 = InformationProcess | 0x10000000;
        if ( InformationProcess >= 0 )
        {
          v11 = wcsrchr(Str, 0x5Cu);
          if ( v11 )
            v12 = v11 + 1;
          else
            v12 = Str;
          StringCchCopyW(v29, 0x104u, v12);
        }
        CloseHandle(v9);
      }
    }
  }
  if ( v28 )
  {
    if ( v7 < 0 )
    {
      if ( (g_DebugTraceComponent & 1) != 0 )
        _DbgPrintMessage(2, "RPC Caller: Unknown");
    }
    else if ( (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(2, "RPC Caller: PID %d, SessID %d, Process Name: <%S>", Pid[1], Pid[0], v29);
    }
  }
  if ( !a1 )
  {
    v13 = "hListener";
LABEL_36:
    _DbgPrintMessage(8, "Missing paramter %s in %s", v13, "RpcIsListening");
    v14 = -2147024809;
    goto LABEL_54;
  }
  if ( !a2 )
  {
    v13 = "pbIsListening";
    goto LABEL_36;
  }
  v4 = *(_QWORD *)(a1 + 1592);
  if ( v4 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v4 + 8LL))(*(_QWORD *)(a1 + 1592));
  v15 = RpcImpersonateClient(0);
  v14 = v15;
  if ( v15 > 0 )
    v14 = (unsigned __int16)v15 | 0x80070000;
  if ( v14 >= 0 )
  {
    v14 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 96LL))(v4, 1);
    v16 = RpcRevertToSelf();
    v17 = v16 < 0;
    if ( v16 > 0 )
    {
      v16 = (unsigned __int16)v16 | 0x80070000;
      v17 = v16 < 0;
    }
    if ( v17 )
    {
      v14 = -2147024891;
      _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v16);
    }
    else if ( v14 >= 0 )
    {
      v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 64LL))(v4);
      v14 = v18;
      if ( v18 >= 0 )
      {
        *a2 = v18 == 0;
        v14 = 0;
      }
      else
      {
        _DbgPrintMessage(8, "Listener->isListening failed: 0x%x in %s", v18, "RpcIsListening");
      }
    }
    else
    {
      _DbgPrintMessage(8, "AccessCheck( QUERY ) failed: 0x%x in %s", v14, "RpcIsListening");
    }
  }
  else
  {
    _DbgPrintMessage(8, "RpcImpersonateClient failed: 0x%x in %s", v14, "RpcIsListening");
  }
LABEL_54:
  v21 = &CRpcCallTrace::`vftable';
  if ( v28 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "%s with Trace ID 0x%x Completed", v26, v23[0]);
  v21 = &CTraceBase::`vftable';
  if ( CTraceBase::g_bEnabled && !v25 && CTraceBase::g_TLSIndex != -1 )
  {
    if ( TlsSetValue(CTraceBase::g_TLSIndex, 0) )
    {
      if ( TlsSetValue(CTraceBase::g_CreatorFunctionTLSIndex, 0) )
        goto LABEL_64;
    }
    else
    {
      GetLastError();
    }
    GetLastError();
  }
LABEL_64:
  v24 = 0;
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18000b5f0  push    rbp
0x18000b5f2  push    rbx
0x18000b5f3  push    rsi
0x18000b5f4  push    rdi
0x18000b5f5  push    r12
0x18000b5f7  push    r13
0x18000b5f9  push    r14
0x18000b5fb  push    r15
0x18000b5fd  lea     rbp, [rsp-2B8h]
0x18000b605  sub     rsp, 3B8h
0x18000b60c  mov     rax, cs:__security_cookie
0x18000b613  xor     rax, rsp
0x18000b616  mov     [rbp+2F0h+var_50], rax
0x18000b61d  mov     r15, rdx
0x18000b620  mov     r14, rcx
0x18000b623  xor     r12d, r12d
0x18000b626  mov     ebx, r12d
0x18000b629  lea     r13, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000b630  mov     [rsp+3F0h+var_3B0], r13
0x18000b635  mov     [rsp+3F0h+var_394], 1
0x18000b63d  mov     [rsp+3F0h+var_390], r12
0x18000b642  lea     rdi, aRpcislistening; "RpcIsListening"
0x18000b649  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r12d; int CTraceBase::g_bEnabled
0x18000b650  jnz     short loc_18000B675
0x18000b652  lea     rcx, [rsp+3F0h+pguid]; pguid
0x18000b657  call    cs:__imp_CoCreateGuid
0x18000b65d  mov     eax, 1
0x18000b662  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x18000b66a  inc     eax
0x18000b66c  mov     [rsp+3F0h+var_398], eax
0x18000b670  jmp     loc_18000B746
0x18000b675  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000b67c  jz      short loc_18000B69F
0x18000b67e  mov     [rsp+3F0h+ReturnLength], rdi
0x18000b683  mov     r9d, 1
0x18000b689  lea     r8, [rsp+3F0h+var_3B0]
0x18000b68e  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x18000b695  mov     ecx, 2; int
0x18000b69a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b69f  mov     [rsp+3F0h+var_3C0], r12
0x18000b6a4  lea     rcx, [rsp+3F0h+var_3C0]; struct CTraceBase **
0x18000b6a9  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000b6ae  test    eax, eax
0x18000b6b0  js      short loc_18000B6D9
0x18000b6b2  cmp     [rsp+3F0h+var_3C0], rbx
0x18000b6b7  jz      short loc_18000B6D9
0x18000b6b9  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000b6c0  jz      short loc_18000B6D9
0x18000b6c2  mov     r8d, 1
0x18000b6c8  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x18000b6cf  mov     ecx, 2; int
0x18000b6d4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b6d9  xor     edx, edx; char *
0x18000b6db  xor     ecx, ecx; lpTlsValue
0x18000b6dd  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000b6e2  lea     rcx, [rsp+3F0h+var_390]; struct CTraceBase **
0x18000b6e7  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000b6ec  test    eax, eax
0x18000b6ee  js      short loc_18000B72A
0x18000b6f0  mov     rcx, [rsp+3F0h+var_390]
0x18000b6f5  test    rcx, rcx
0x18000b6f8  jz      short loc_18000B72A
0x18000b6fa  mov     rax, [rcx]
0x18000b6fd  lea     rdx, [rsp+3F0h+pguid]
0x18000b702  mov     rax, [rax+20h]
0x18000b706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b70b  mov     rcx, [rsp+3F0h+var_390]
0x18000b710  mov     rax, [rcx]
0x18000b713  mov     rax, [rax+18h]
0x18000b717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b71c  mov     [rsp+3F0h+var_398], eax
0x18000b720  mov     [rsp+3F0h+var_388], 1
0x18000b728  jmp     short loc_18000B74B
0x18000b72a  mov     rdx, rdi; char *
0x18000b72d  lea     rcx, [rsp+3F0h+var_3B0]; lpTlsValue
0x18000b732  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000b737  lea     rdx, [rsp+3F0h+var_398]; unsigned int *
0x18000b73c  lea     rcx, [rsp+3F0h+pguid]; struct _GUID *
0x18000b741  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x18000b746  mov     [rsp+3F0h+var_388], r12d
0x18000b74b  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000b752  mov     [rsp+3F0h+var_3B0], rax
0x18000b757  mov     [rsp+3F0h+var_380], rdi
0x18000b75c  mov     qword ptr [rsp+3F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000b765  mov     [rbp+2F0h+var_370], r12d
0x18000b769  xor     edx, edx; Val
0x18000b76b  mov     r8d, 208h; Size
0x18000b771  lea     rcx, [rbp+2F0h+var_36C]; void *
0x18000b775  call    memset_0
0x18000b77a  cmp     [rbp+2F0h+var_370], ebx
0x18000b77d  jz      short loc_18000B7A3
0x18000b77f  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000b786  jz      short loc_18000B7A3
0x18000b788  mov     r9d, [rsp+3F0h+var_398]
0x18000b78d  mov     r8, [rsp+3F0h+var_380]
0x18000b792  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x18000b799  mov     ecx, 2; int
0x18000b79e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b7a3  mov     esi, cs:?g_DebugTraceComponent@@3KA; ulong g_DebugTraceComponent
0x18000b7a9  and     esi, 1
0x18000b7ac  mov     qword ptr [rsp+3F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000b7b5  lea     rdx, [rsp+3F0h+Pid+4]; Pid
0x18000b7ba  xor     ecx, ecx; Binding
0x18000b7bc  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000b7c2  mov     edi, eax
0x18000b7c4  test    eax, eax
0x18000b7c6  jle     short loc_18000B7D1
0x18000b7c8  movzx   edi, ax
0x18000b7cb  or      edi, 80070000h
0x18000b7d1  test    edi, edi
0x18000b7d3  js      loc_18000B872
0x18000b7d9  lea     rdx, [rsp+3F0h+Pid]; pSessionId
0x18000b7de  mov     ecx, [rsp+3F0h+Pid+4]; dwProcessId
0x18000b7e2  call    cs:__imp_ProcessIdToSessionId
0x18000b7e8  test    esi, esi
0x18000b7ea  jz      loc_18000B872
0x18000b7f0  mov     r8d, [rsp+3F0h+Pid+4]; dwProcessId
0x18000b7f5  xor     edx, edx; bInheritHandle
0x18000b7f7  mov     ecx, 400h; dwDesiredAccess
0x18000b7fc  call    cs:__imp_OpenProcess
0x18000b802  mov     rsi, rax
0x18000b805  test    rax, rax
0x18000b808  jz      short loc_18000B872
0x18000b80a  mov     [rsp+3F0h+ReturnLength], r12; ReturnLength
0x18000b80f  mov     r9d, 110h; ProcessInformationLength
0x18000b815  lea     r8, [rbp+2F0h+ProcessInformation]; ProcessInformation
0x18000b81c  mov     edx, 1Bh; ProcessInformationClass
0x18000b821  mov     rcx, rax; ProcessHandle
0x18000b824  call    cs:__imp_NtQueryInformationProcess
0x18000b82a  mov     edi, eax
0x18000b82c  or      edi, 10000000h
0x18000b832  jl      short loc_18000B869
0x18000b834  mov     edx, 5Ch ; '\'; Ch
0x18000b839  mov     rcx, [rbp+2F0h+Str]; Str
0x18000b840  call    cs:__imp_wcsrchr
0x18000b846  test    rax, rax
0x18000b849  jnz     short loc_18000B854
0x18000b84b  mov     rax, [rbp+2F0h+Str]
0x18000b852  jmp     short loc_18000B858
0x18000b854  add     rax, 2
0x18000b858  mov     r8, rax; unsigned __int16 *
0x18000b85b  mov     edx, 104h; unsigned __int64
0x18000b860  lea     rcx, [rbp+2F0h+var_36C]; unsigned __int16 *
0x18000b864  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b869  mov     rcx, rsi; hObject
0x18000b86c  call    cs:__imp_CloseHandle
0x18000b872  cmp     [rbp+2F0h+var_370], ebx
0x18000b875  jz      short loc_18000B8C4
0x18000b877  test    edi, edi
0x18000b879  js      short loc_18000B8AA
0x18000b87b  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000b882  jz      short loc_18000B8C4
0x18000b884  lea     rax, [rbp+2F0h+var_36C]
0x18000b888  mov     [rsp+3F0h+ReturnLength], rax
0x18000b88d  mov     r9d, [rsp+3F0h+Pid]
0x18000b892  mov     r8d, [rsp+3F0h+Pid+4]
0x18000b897  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x18000b89e  mov     ecx, 2; int
0x18000b8a3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b8a8  jmp     short loc_18000B8C4
0x18000b8aa  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000b8b1  jz      short loc_18000B8C4
0x18000b8b3  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x18000b8ba  mov     ecx, 2; int
0x18000b8bf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b8c4  test    r14, r14
0x18000b8c7  jnz     short loc_18000B8F2
0x18000b8c9  lea     r8, aHlistener; "hListener"
0x18000b8d0  lea     r9, aRpcislistening; "RpcIsListening"
0x18000b8d7  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18000b8de  mov     ecx, 8; int
0x18000b8e3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b8e8  mov     edi, 80070057h
0x18000b8ed  jmp     loc_18000B9FE
0x18000b8f2  test    r15, r15
0x18000b8f5  jnz     short loc_18000B900
0x18000b8f7  lea     r8, aPbislistening; "pbIsListening"
0x18000b8fe  jmp     short loc_18000B8D0
0x18000b900  mov     rbx, [r14+638h]
0x18000b907  test    rbx, rbx
0x18000b90a  jz      short loc_18000B91B
0x18000b90c  mov     rax, [rbx]
0x18000b90f  mov     rcx, rbx
0x18000b912  mov     rax, [rax+8]
0x18000b916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b91b  xor     ecx, ecx; BindingHandle
0x18000b91d  call    cs:__imp_RpcImpersonateClient
0x18000b923  mov     edi, eax
0x18000b925  test    eax, eax
0x18000b927  jle     short loc_18000B932
0x18000b929  movzx   edi, ax
0x18000b92c  or      edi, 80070000h
0x18000b932  test    edi, edi
0x18000b934  jns     short loc_18000B956
0x18000b936  lea     r9, aRpcislistening; "RpcIsListening"
0x18000b93d  mov     r8d, edi
0x18000b940  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x18000b947  mov     ecx, 8; int
0x18000b94c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b951  jmp     loc_18000B9FE
0x18000b956  mov     rax, [rbx]
0x18000b959  mov     edx, 1
0x18000b95e  mov     rcx, rbx
0x18000b961  mov     rax, [rax+60h]
0x18000b965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b96a  mov     edi, eax
0x18000b96c  call    cs:__imp_RpcRevertToSelf
0x18000b972  test    eax, eax
0x18000b974  jle     short loc_18000B980
0x18000b976  movzx   eax, ax
0x18000b979  or      eax, 80070000h
0x18000b97e  test    eax, eax
0x18000b980  jns     short loc_18000B99D
0x18000b982  mov     edi, 80070005h
0x18000b987  mov     r8d, eax
0x18000b98a  lea     rdx, aRpcreverttosel_1; "RpcRevertToSelf failed: 0x%x"
0x18000b991  mov     ecx, 8; int
0x18000b996  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b99b  jmp     short loc_18000B9FE
0x18000b99d  test    edi, edi
0x18000b99f  jns     short loc_18000B9BE
0x18000b9a1  lea     r9, aRpcislistening; "RpcIsListening"
0x18000b9a8  mov     r8d, edi
0x18000b9ab  lea     rdx, aAccesscheckQue; "AccessCheck( QUERY ) failed: 0x%x in %s"
0x18000b9b2  mov     ecx, 8; int
0x18000b9b7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b9bc  jmp     short loc_18000B9FE
0x18000b9be  mov     rax, [rbx]
0x18000b9c1  mov     rcx, rbx
0x18000b9c4  mov     rax, [rax+40h]
0x18000b9c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9cd  mov     edi, eax
0x18000b9cf  test    eax, eax
0x18000b9d1  jns     short loc_18000B9F0
0x18000b9d3  lea     r9, aRpcislistening; "RpcIsListening"
0x18000b9da  mov     r8d, eax
0x18000b9dd  lea     rdx, aListenerIslist; "Listener->isListening failed: 0x%x in %"...
0x18000b9e4  mov     ecx, 8; int
0x18000b9e9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b9ee  jmp     short loc_18000B9FE
0x18000b9f0  mov     eax, r12d
0x18000b9f3  test    edi, edi
0x18000b9f5  setz    al
0x18000b9f8  mov     [r15], eax
0x18000b9fb  mov     edi, r12d
0x18000b9fe  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000ba05  mov     [rsp+3F0h+var_3B0], rax
0x18000ba0a  cmp     [rbp+2F0h+var_370], 0
0x18000ba0e  jz      short loc_18000BA34
0x18000ba10  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000ba17  jz      short loc_18000BA34
0x18000ba19  mov     r9d, [rsp+3F0h+var_398]
0x18000ba1e  mov     r8, [rsp+3F0h+var_380]
0x18000ba23  lea     rdx, aSWithTraceId0x; "%s with Trace ID 0x%x Completed"
0x18000ba2a  mov     ecx, 2; int
0x18000ba2f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ba34  mov     [rsp+3F0h+var_3B0], r13
0x18000ba39  cmp     cs:?g_bEnabled@CTraceBase@@0HA, 0; int CTraceBase::g_bEnabled
0x18000ba40  jz      short loc_18000BA80
0x18000ba42  cmp     [rsp+3F0h+var_388], 0
0x18000ba47  jnz     short loc_18000BA80
0x18000ba49  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x18000ba4f  cmp     ecx, 0FFFFFFFFh
0x18000ba52  jz      short loc_18000BA80
0x18000ba54  xor     edx, edx; lpTlsValue
0x18000ba56  call    cs:__imp_TlsSetValue
0x18000ba5c  test    eax, eax
0x18000ba5e  jnz     short loc_18000BA68
0x18000ba60  call    cs:__imp_GetLastError
0x18000ba66  jmp     short loc_18000BA7A
0x18000ba68  xor     edx, edx; lpTlsValue
0x18000ba6a  mov     ecx, cs:?g_CreatorFunctionTLSIndex@CTraceBase@@0KA; dwTlsIndex
0x18000ba70  call    cs:__imp_TlsSetValue
0x18000ba76  test    eax, eax
0x18000ba78  jnz     short loc_18000BA80
0x18000ba7a  call    cs:__imp_GetLastError
0x18000ba80  mov     [rsp+3F0h+var_390], r12
0x18000ba85  test    rbx, rbx
0x18000ba88  jz      short loc_18000BA9A
0x18000ba8a  mov     rax, [rbx]
0x18000ba8d  mov     rcx, rbx
0x18000ba90  mov     rax, [rax+10h]
0x18000ba94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba99  nop
0x18000ba9a  mov     eax, edi
0x18000ba9c  mov     rcx, [rbp+2F0h+var_50]
0x18000baa3  xor     rcx, rsp; StackCookie
0x18000baa6  call    __security_check_cookie
0x18000baab  add     rsp, 3B8h
0x18000bab2  pop     r15
0x18000bab4  pop     r14
0x18000bab6  pop     r13
0x18000bab8  pop     r12
0x18000baba  pop     rdi
0x18000babb  pop     rsi
0x18000babc  pop     rbx
0x18000babd  pop     rbp
0x18000babe  retn
```
