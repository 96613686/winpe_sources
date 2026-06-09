# RpcIsListening

- ea: `0x18000eb30`
- end: `0x18000f04e`
- name: `RpcIsListening`
- size: `1310`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009940`
- `0x18000eb30`
- `0x18000faf0`
- `0x180012070`
- `0x180012d10`
- `0x1800154a0`
- `0x180033f60`
- `0x180034e64`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000ed9e`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000ed9e`
- `ntdll!NtQueryInformationProcess` at `0x18000ed7c`
- `ntdll!NtQueryInformationProcess` at `0x18000ed7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000efdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f002`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000efdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f002`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000ed2e`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000ed2e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000efcc`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000eff2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000efcc`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000eff2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000edd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000edd0`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000ed02`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000ed02`
- `RPCRT4!RpcRevertToSelf` at `0x18000eedc`
- `RPCRT4!RpcRevertToSelf` at `0x18000eedc`
- `RPCRT4!RpcImpersonateClient` at `0x18000ee87`
- `RPCRT4!RpcImpersonateClient` at `0x18000ee87`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000ed4e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000ed4e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000eb97`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000eb97`

## string_xrefs

- `0x18000eeb0`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18000ef99`: `%s with Trace ID 0x%x Completed`
- `0x18000ef21`: `AccessCheck( QUERY ) failed: 0x%x in %s`
- `0x18000ec0e`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18000ee01`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

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
0x18000eb30  push    rbp
0x18000eb32  push    rbx
0x18000eb33  push    rsi
0x18000eb34  push    rdi
0x18000eb35  push    r12
0x18000eb37  push    r13
0x18000eb39  push    r14
0x18000eb3b  push    r15
0x18000eb3d  lea     rbp, [rsp-2B8h]
0x18000eb45  sub     rsp, 3B8h
0x18000eb4c  mov     rax, cs:__security_cookie
0x18000eb53  xor     rax, rsp
0x18000eb56  mov     [rbp+2F0h+var_50], rax
0x18000eb5d  mov     r15, rdx
0x18000eb60  mov     r14, rcx
0x18000eb63  xor     r12d, r12d
0x18000eb66  mov     ebx, r12d
0x18000eb69  lea     r13, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000eb70  mov     [rsp+3F0h+var_3B0], r13
0x18000eb75  mov     [rsp+3F0h+var_394], 1
0x18000eb7d  mov     [rsp+3F0h+var_390], r12
0x18000eb82  lea     rdi, aRpcislistening; "RpcIsListening"
0x18000eb89  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r12d; int CTraceBase::g_bEnabled
0x18000eb90  jnz     short loc_18000EBBB
0x18000eb92  lea     rcx, [rsp+3F0h+pguid]; pguid
0x18000eb97  call    cs:__imp_CoCreateGuid
0x18000eb9e  nop     dword ptr [rax+rax+00h]
0x18000eba3  mov     eax, 1
0x18000eba8  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x18000ebb0  inc     eax
0x18000ebb2  mov     [rsp+3F0h+var_398], eax
0x18000ebb6  jmp     loc_18000EC8C
0x18000ebbb  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000ebc2  jz      short loc_18000EBE5
0x18000ebc4  mov     [rsp+3F0h+ReturnLength], rdi
0x18000ebc9  mov     r9d, 1
0x18000ebcf  lea     r8, [rsp+3F0h+var_3B0]
0x18000ebd4  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x18000ebdb  mov     ecx, 2; int
0x18000ebe0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ebe5  mov     [rsp+3F0h+var_3C0], r12
0x18000ebea  lea     rcx, [rsp+3F0h+var_3C0]; struct CTraceBase **
0x18000ebef  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000ebf4  test    eax, eax
0x18000ebf6  js      short loc_18000EC1F
0x18000ebf8  cmp     [rsp+3F0h+var_3C0], rbx
0x18000ebfd  jz      short loc_18000EC1F
0x18000ebff  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000ec06  jz      short loc_18000EC1F
0x18000ec08  mov     r8d, 1
0x18000ec0e  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x18000ec15  mov     ecx, 2; int
0x18000ec1a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ec1f  xor     edx, edx; char *
0x18000ec21  xor     ecx, ecx; lpTlsValue
0x18000ec23  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000ec28  lea     rcx, [rsp+3F0h+var_390]; struct CTraceBase **
0x18000ec2d  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000ec32  test    eax, eax
0x18000ec34  js      short loc_18000EC70
0x18000ec36  mov     rcx, [rsp+3F0h+var_390]
0x18000ec3b  test    rcx, rcx
0x18000ec3e  jz      short loc_18000EC70
0x18000ec40  mov     rax, [rcx]
0x18000ec43  lea     rdx, [rsp+3F0h+pguid]
0x18000ec48  mov     rax, [rax+20h]
0x18000ec4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec51  mov     rcx, [rsp+3F0h+var_390]
0x18000ec56  mov     rax, [rcx]
0x18000ec59  mov     rax, [rax+18h]
0x18000ec5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec62  mov     [rsp+3F0h+var_398], eax
0x18000ec66  mov     [rsp+3F0h+var_388], 1
0x18000ec6e  jmp     short loc_18000EC91
0x18000ec70  mov     rdx, rdi; char *
0x18000ec73  lea     rcx, [rsp+3F0h+var_3B0]; lpTlsValue
0x18000ec78  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000ec7d  lea     rdx, [rsp+3F0h+var_398]; unsigned int *
0x18000ec82  lea     rcx, [rsp+3F0h+pguid]; struct _GUID *
0x18000ec87  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x18000ec8c  mov     [rsp+3F0h+var_388], r12d
0x18000ec91  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000ec98  mov     [rsp+3F0h+var_3B0], rax
0x18000ec9d  mov     [rsp+3F0h+var_380], rdi
0x18000eca2  mov     qword ptr [rsp+3F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000ecab  mov     [rbp+2F0h+var_370], r12d
0x18000ecaf  xor     edx, edx; Val
0x18000ecb1  mov     r8d, 208h; Size
0x18000ecb7  lea     rcx, [rbp+2F0h+var_36C]; void *
0x18000ecbb  call    memset_0
0x18000ecc0  cmp     [rbp+2F0h+var_370], ebx
0x18000ecc3  jz      short loc_18000ECE9
0x18000ecc5  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000eccc  jz      short loc_18000ECE9
0x18000ecce  mov     r9d, [rsp+3F0h+var_398]
0x18000ecd3  mov     r8, [rsp+3F0h+var_380]
0x18000ecd8  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x18000ecdf  mov     ecx, 2; int
0x18000ece4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ece9  mov     esi, cs:?g_DebugTraceComponent@@3KA; ulong g_DebugTraceComponent
0x18000ecef  and     esi, 1
0x18000ecf2  mov     qword ptr [rsp+3F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000ecfb  lea     rdx, [rsp+3F0h+Pid+4]; Pid
0x18000ed00  xor     ecx, ecx; Binding
0x18000ed02  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000ed09  nop     dword ptr [rax+rax+00h]
0x18000ed0e  mov     edi, eax
0x18000ed10  test    eax, eax
0x18000ed12  jle     short loc_18000ED1D
0x18000ed14  movzx   edi, ax
0x18000ed17  or      edi, 80070000h
0x18000ed1d  test    edi, edi
0x18000ed1f  js      loc_18000EDDC
0x18000ed25  lea     rdx, [rsp+3F0h+Pid]; pSessionId
0x18000ed2a  mov     ecx, [rsp+3F0h+Pid+4]; dwProcessId
0x18000ed2e  call    cs:__imp_ProcessIdToSessionId
0x18000ed35  nop     dword ptr [rax+rax+00h]
0x18000ed3a  test    esi, esi
0x18000ed3c  jz      loc_18000EDDC
0x18000ed42  mov     r8d, [rsp+3F0h+Pid+4]; dwProcessId
0x18000ed47  xor     edx, edx; bInheritHandle
0x18000ed49  mov     ecx, 400h; dwDesiredAccess
0x18000ed4e  call    cs:__imp_OpenProcess
0x18000ed55  nop     dword ptr [rax+rax+00h]
0x18000ed5a  mov     rsi, rax
0x18000ed5d  test    rax, rax
0x18000ed60  jz      short loc_18000EDDC
0x18000ed62  mov     [rsp+3F0h+ReturnLength], r12; ReturnLength
0x18000ed67  mov     r9d, 110h; ProcessInformationLength
0x18000ed6d  lea     r8, [rbp+2F0h+ProcessInformation]; ProcessInformation
0x18000ed74  mov     edx, 1Bh; ProcessInformationClass
0x18000ed79  mov     rcx, rax; ProcessHandle
0x18000ed7c  call    cs:__imp_NtQueryInformationProcess
0x18000ed83  nop     dword ptr [rax+rax+00h]
0x18000ed88  mov     edi, eax
0x18000ed8a  or      edi, 10000000h
0x18000ed90  jl      short loc_18000EDCD
0x18000ed92  mov     edx, 5Ch ; '\'; Ch
0x18000ed97  mov     rcx, [rbp+2F0h+Str]; Str
0x18000ed9e  call    cs:__imp_wcsrchr
0x18000eda5  nop     dword ptr [rax+rax+00h]
0x18000edaa  test    rax, rax
0x18000edad  jnz     short loc_18000EDB8
0x18000edaf  mov     rax, [rbp+2F0h+Str]
0x18000edb6  jmp     short loc_18000EDBC
0x18000edb8  add     rax, 2
0x18000edbc  mov     r8, rax; unsigned __int16 *
0x18000edbf  mov     edx, 104h; unsigned __int64
0x18000edc4  lea     rcx, [rbp+2F0h+var_36C]; unsigned __int16 *
0x18000edc8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000edcd  mov     rcx, rsi; hObject
0x18000edd0  call    cs:__imp_CloseHandle
0x18000edd7  nop     dword ptr [rax+rax+00h]
0x18000eddc  cmp     [rbp+2F0h+var_370], ebx
0x18000eddf  jz      short loc_18000EE2E
0x18000ede1  test    edi, edi
0x18000ede3  js      short loc_18000EE14
0x18000ede5  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000edec  jz      short loc_18000EE2E
0x18000edee  lea     rax, [rbp+2F0h+var_36C]
0x18000edf2  mov     [rsp+3F0h+ReturnLength], rax
0x18000edf7  mov     r9d, [rsp+3F0h+Pid]
0x18000edfc  mov     r8d, [rsp+3F0h+Pid+4]
0x18000ee01  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x18000ee08  mov     ecx, 2; int
0x18000ee0d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ee12  jmp     short loc_18000EE2E
0x18000ee14  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000ee1b  jz      short loc_18000EE2E
0x18000ee1d  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x18000ee24  mov     ecx, 2; int
0x18000ee29  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ee2e  test    r14, r14
0x18000ee31  jnz     short loc_18000EE5C
0x18000ee33  lea     r8, aHlistener; "hListener"
0x18000ee3a  lea     r9, aRpcislistening; "RpcIsListening"
0x18000ee41  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18000ee48  mov     ecx, 8; int
0x18000ee4d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ee52  mov     edi, 80070057h
0x18000ee57  jmp     loc_18000EF74
0x18000ee5c  test    r15, r15
0x18000ee5f  jnz     short loc_18000EE6A
0x18000ee61  lea     r8, aPbislistening; "pbIsListening"
0x18000ee68  jmp     short loc_18000EE3A
0x18000ee6a  mov     rbx, [r14+638h]
0x18000ee71  test    rbx, rbx
0x18000ee74  jz      short loc_18000EE85
0x18000ee76  mov     rax, [rbx]
0x18000ee79  mov     rcx, rbx
0x18000ee7c  mov     rax, [rax+8]
0x18000ee80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee85  xor     ecx, ecx; BindingHandle
0x18000ee87  call    cs:__imp_RpcImpersonateClient
0x18000ee8e  nop     dword ptr [rax+rax+00h]
0x18000ee93  mov     edi, eax
0x18000ee95  test    eax, eax
0x18000ee97  jle     short loc_18000EEA2
0x18000ee99  movzx   edi, ax
0x18000ee9c  or      edi, 80070000h
0x18000eea2  test    edi, edi
0x18000eea4  jns     short loc_18000EEC6
0x18000eea6  lea     r9, aRpcislistening; "RpcIsListening"
0x18000eead  mov     r8d, edi
0x18000eeb0  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x18000eeb7  mov     ecx, 8; int
0x18000eebc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000eec1  jmp     loc_18000EF74
0x18000eec6  mov     rax, [rbx]
0x18000eec9  mov     edx, 1
0x18000eece  mov     rcx, rbx
0x18000eed1  mov     rax, [rax+60h]
0x18000eed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eeda  mov     edi, eax
0x18000eedc  call    cs:__imp_RpcRevertToSelf
0x18000eee3  nop     dword ptr [rax+rax+00h]
0x18000eee8  test    eax, eax
0x18000eeea  jle     short loc_18000EEF6
0x18000eeec  movzx   eax, ax
0x18000eeef  or      eax, 80070000h
0x18000eef4  test    eax, eax
0x18000eef6  jns     short loc_18000EF13
0x18000eef8  mov     edi, 80070005h
0x18000eefd  mov     r8d, eax
0x18000ef00  lea     rdx, aRpcreverttosel_1; "RpcRevertToSelf failed: 0x%x"
0x18000ef07  mov     ecx, 8; int
0x18000ef0c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ef11  jmp     short loc_18000EF74
0x18000ef13  test    edi, edi
0x18000ef15  jns     short loc_18000EF34
0x18000ef17  lea     r9, aRpcislistening; "RpcIsListening"
0x18000ef1e  mov     r8d, edi
0x18000ef21  lea     rdx, aAccesscheckQue; "AccessCheck( QUERY ) failed: 0x%x in %s"
0x18000ef28  mov     ecx, 8; int
0x18000ef2d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ef32  jmp     short loc_18000EF74
0x18000ef34  mov     rax, [rbx]
0x18000ef37  mov     rcx, rbx
0x18000ef3a  mov     rax, [rax+40h]
0x18000ef3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef43  mov     edi, eax
0x18000ef45  test    eax, eax
0x18000ef47  jns     short loc_18000EF66
0x18000ef49  lea     r9, aRpcislistening; "RpcIsListening"
0x18000ef50  mov     r8d, eax
0x18000ef53  lea     rdx, aListenerIslist; "Listener->isListening failed: 0x%x in %"...
0x18000ef5a  mov     ecx, 8; int
0x18000ef5f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ef64  jmp     short loc_18000EF74
0x18000ef66  mov     eax, r12d
0x18000ef69  test    edi, edi
0x18000ef6b  setz    al
0x18000ef6e  mov     [r15], eax
0x18000ef71  mov     edi, r12d
0x18000ef74  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000ef7b  mov     [rsp+3F0h+var_3B0], rax
0x18000ef80  cmp     [rbp+2F0h+var_370], 0
0x18000ef84  jz      short loc_18000EFAA
0x18000ef86  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000ef8d  jz      short loc_18000EFAA
0x18000ef8f  mov     r9d, [rsp+3F0h+var_398]
0x18000ef94  mov     r8, [rsp+3F0h+var_380]
0x18000ef99  lea     rdx, aSWithTraceId0x; "%s with Trace ID 0x%x Completed"
0x18000efa0  mov     ecx, 2; int
0x18000efa5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000efaa  mov     [rsp+3F0h+var_3B0], r13
0x18000efaf  cmp     cs:?g_bEnabled@CTraceBase@@0HA, 0; int CTraceBase::g_bEnabled
0x18000efb6  jz      short loc_18000F00E
0x18000efb8  cmp     [rsp+3F0h+var_388], 0
0x18000efbd  jnz     short loc_18000F00E
0x18000efbf  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x18000efc5  cmp     ecx, 0FFFFFFFFh
0x18000efc8  jz      short loc_18000F00E
0x18000efca  xor     edx, edx; lpTlsValue
0x18000efcc  call    cs:__imp_TlsSetValue
0x18000efd3  nop     dword ptr [rax+rax+00h]
0x18000efd8  test    eax, eax
0x18000efda  jnz     short loc_18000EFEA
0x18000efdc  call    cs:__imp_GetLastError
0x18000efe3  nop     dword ptr [rax+rax+00h]
0x18000efe8  jmp     short loc_18000F002
0x18000efea  xor     edx, edx; lpTlsValue
0x18000efec  mov     ecx, cs:?g_CreatorFunctionTLSIndex@CTraceBase@@0KA; dwTlsIndex
0x18000eff2  call    cs:__imp_TlsSetValue
0x18000eff9  nop     dword ptr [rax+rax+00h]
0x18000effe  test    eax, eax
0x18000f000  jnz     short loc_18000F00E
0x18000f002  call    cs:__imp_GetLastError
0x18000f009  nop     dword ptr [rax+rax+00h]
0x18000f00e  mov     [rsp+3F0h+var_390], r12
0x18000f013  test    rbx, rbx
0x18000f016  jz      short loc_18000F028
0x18000f018  mov     rax, [rbx]
0x18000f01b  mov     rcx, rbx
0x18000f01e  mov     rax, [rax+10h]
0x18000f022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f027  nop
0x18000f028  mov     eax, edi
0x18000f02a  mov     rcx, [rbp+2F0h+var_50]
0x18000f031  xor     rcx, rsp; StackCookie
  ... truncated ...
```
