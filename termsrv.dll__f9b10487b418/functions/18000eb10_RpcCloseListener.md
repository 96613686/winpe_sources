# RpcCloseListener

- ea: `0x18000eb10`
- end: `0x18000eead`
- name: `RpcCloseListener`
- size: `925`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005d0d0`
- `0x18005d0f0`

## callees

- `0x18000a210`
- `0x18000eb10`
- `0x18000f790`
- `0x1800119a0`
- `0x1800127b0`
- `0x180014de0`
- `0x1800321f0`
- `0x1800330c4`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000ed4b`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000ed4b`
- `ntdll!NtQueryInformationProcess` at `0x18000ed2f`
- `ntdll!NtQueryInformationProcess` at `0x18000ed2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee81`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000eced`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000eced`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000ee5d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000ee77`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000ee5d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000ee77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ed77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ed77`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000ecc7`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000ecc7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000ed07`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000ed07`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000eb72`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000eb72`

## string_xrefs

- `0x18000ee2a`: `%s with Trace ID 0x%x Completed`
- `0x18000ebd6`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18000eda3`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RpcCloseListener(_QWORD *a1)
{
  unsigned int v2; // esi
  RPC_STATUS v3; // eax
  int v4; // ebx
  HANDLE v5; // rax
  void *v6; // rsi
  NTSTATUS InformationProcess; // eax
  wchar_t *v8; // rax
  wchar_t *v9; // rax
  unsigned int v10; // ebx
  struct CTraceBase *v12; // [rsp+30h] [rbp-D0h] BYREF
  void **v13; // [rsp+40h] [rbp-C0h] BYREF
  GUID pguid; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v15[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct CTraceBase *v16; // [rsp+60h] [rbp-A0h] BYREF
  int v17; // [rsp+68h] [rbp-98h]
  const char *v18; // [rsp+70h] [rbp-90h]
  unsigned int Pid[2]; // [rsp+78h] [rbp-88h] BYREF
  int v20; // [rsp+80h] [rbp-80h]
  unsigned __int16 v21[262]; // [rsp+84h] [rbp-7Ch] BYREF
  _BYTE ProcessInformation[8]; // [rsp+290h] [rbp+190h] BYREF
  wchar_t *Str; // [rsp+298h] [rbp+198h]

  v13 = &CTraceBase::`vftable';
  v15[1] = 1;
  v16 = 0;
  if ( !CTraceBase::g_bEnabled )
  {
    CoCreateGuid(&pguid);
    v15[0] = _InterlockedIncrement((volatile signed __int32 *)&CTraceBase::g_NextShortActivityID);
LABEL_13:
    v17 = 0;
    goto LABEL_14;
  }
  if ( (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "Adding trace %p, %d, %s", &v13, 1, "RpcCloseListener");
  v12 = 0;
  if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v12) >= 0 && v12 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(
      2,
      "TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC",
      1);
  CTraceBase::ResetThreadCurrentOperationTrace(0, 0);
  if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v16) < 0 || !v16 )
  {
    CTraceBase::ResetThreadCurrentOperationTrace((struct CTraceBase *)&v13, "RpcCloseListener");
    CTraceBase::GenerateTraceID(&pguid, v15);
    goto LABEL_13;
  }
  (*(void (__fastcall **)(struct CTraceBase *, GUID *))(*(_QWORD *)v16 + 32LL))(v16, &pguid);
  v15[0] = (*(__int64 (__fastcall **)(struct CTraceBase *))(*(_QWORD *)v16 + 24LL))(v16);
  v17 = 1;
LABEL_14:
  v13 = &CRpcCallTrace::`vftable';
  v18 = "RpcCloseListener";
  *(_QWORD *)Pid = -1;
  v20 = 0;
  memset_0(v21, 0, 0x208u);
  if ( v20 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "TRACE RPC %s with Trace ID 0x%x", v18, v15[0]);
  v2 = g_DebugTraceComponent & 1;
  *(_QWORD *)Pid = -1;
  v3 = I_RpcBindingInqLocalClientPID(0, &Pid[1]);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 >= 0 )
  {
    ProcessIdToSessionId(Pid[1], Pid);
    if ( v2 )
    {
      v5 = OpenProcess(0x400u, 0, Pid[1]);
      v6 = v5;
      if ( v5 )
      {
        InformationProcess = NtQueryInformationProcess(v5, ProcessImageFileName, ProcessInformation, 0x110u, 0);
        v4 = InformationProcess | 0x10000000;
        if ( InformationProcess >= 0 )
        {
          v8 = wcsrchr(Str, 0x5Cu);
          if ( v8 )
            v9 = v8 + 1;
          else
            v9 = Str;
          StringCchCopyW(v21, 0x104u, v9);
        }
        CloseHandle(v6);
      }
    }
  }
  if ( v20 )
  {
    if ( v4 < 0 )
    {
      if ( (g_DebugTraceComponent & 1) != 0 )
        _DbgPrintMessage(2, "RPC Caller: Unknown");
    }
    else if ( (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(2, "RPC Caller: PID %d, SessID %d, Process Name: <%S>", Pid[1], Pid[0], v21);
    }
  }
  if ( a1 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
    *a1 = 0;
    v10 = 0;
  }
  else
  {
    _DbgPrintMessage(8, "Missing paramter %s in %s", "phListener", "RpcCloseListener");
    v10 = -2147024809;
  }
  v13 = &CRpcCallTrace::`vftable';
  if ( v20 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "%s with Trace ID 0x%x Completed", v18, v15[0]);
  v13 = &CTraceBase::`vftable';
  if ( CTraceBase::g_bEnabled && !v17 && CTraceBase::g_TLSIndex != -1 )
  {
    if ( !TlsSetValue(CTraceBase::g_TLSIndex, 0) )
    {
      GetLastError();
LABEL_46:
      GetLastError();
      return v10;
    }
    if ( !TlsSetValue(CTraceBase::g_CreatorFunctionTLSIndex, 0) )
      goto LABEL_46;
  }
  return v10;
}

```

## disassembly

```asm
0x18000eb10  push    rbp
0x18000eb12  push    rbx
0x18000eb13  push    rsi
0x18000eb14  push    rdi
0x18000eb15  push    r12
0x18000eb17  push    r13
0x18000eb19  push    r14
0x18000eb1b  push    r15
0x18000eb1d  lea     rbp, [rsp-2B8h]
0x18000eb25  sub     rsp, 3B8h
0x18000eb2c  mov     rax, cs:__security_cookie
0x18000eb33  xor     rax, rsp
0x18000eb36  mov     [rbp+2F0h+var_50], rax
0x18000eb3d  mov     rdi, rcx
0x18000eb40  lea     r15, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000eb47  mov     [rsp+3F0h+var_3B0], r15
0x18000eb4c  mov     ebx, 1
0x18000eb51  mov     [rsp+3F0h+var_394], ebx
0x18000eb55  xor     r14d, r14d
0x18000eb58  mov     [rsp+3F0h+var_390], r14
0x18000eb5d  lea     r13, aRpccloselisten; "RpcCloseListener"
0x18000eb64  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r14d; int CTraceBase::g_bEnabled
0x18000eb6b  jnz     short loc_18000EB8B
0x18000eb6d  lea     rcx, [rsp+3F0h+pguid]; pguid
0x18000eb72  call    cs:__imp_CoCreateGuid
0x18000eb78  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, ebx; ulong CTraceBase::g_NextShortActivityID
0x18000eb80  inc     ebx
0x18000eb82  mov     [rsp+3F0h+var_398], ebx
0x18000eb86  jmp     loc_18000EC50
0x18000eb8b  test    byte ptr cs:?g_DebugTraceComponent@@3KA, bl; ulong g_DebugTraceComponent
0x18000eb91  jz      short loc_18000EBB1
0x18000eb93  mov     [rsp+3F0h+ReturnLength], r13
0x18000eb98  mov     r9d, ebx
0x18000eb9b  lea     r8, [rsp+3F0h+var_3B0]
0x18000eba0  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x18000eba7  mov     ecx, 2; int
0x18000ebac  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ebb1  mov     [rsp+3F0h+var_3C0], r14
0x18000ebb6  lea     rcx, [rsp+3F0h+var_3C0]; struct CTraceBase **
0x18000ebbb  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000ebc0  test    eax, eax
0x18000ebc2  js      short loc_18000EBE7
0x18000ebc4  cmp     [rsp+3F0h+var_3C0], r14
0x18000ebc9  jz      short loc_18000EBE7
0x18000ebcb  test    byte ptr cs:?g_DebugTraceComponent@@3KA, bl; ulong g_DebugTraceComponent
0x18000ebd1  jz      short loc_18000EBE7
0x18000ebd3  mov     r8d, ebx
0x18000ebd6  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x18000ebdd  mov     ecx, 2; int
0x18000ebe2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ebe7  xor     edx, edx; char *
0x18000ebe9  xor     ecx, ecx; lpTlsValue
0x18000ebeb  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000ebf0  lea     rcx, [rsp+3F0h+var_390]; struct CTraceBase **
0x18000ebf5  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000ebfa  test    eax, eax
0x18000ebfc  js      short loc_18000EC34
0x18000ebfe  mov     rcx, [rsp+3F0h+var_390]
0x18000ec03  test    rcx, rcx
0x18000ec06  jz      short loc_18000EC34
0x18000ec08  mov     rax, [rcx]
0x18000ec0b  lea     rdx, [rsp+3F0h+pguid]
0x18000ec10  mov     rax, [rax+20h]
0x18000ec14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec19  mov     rcx, [rsp+3F0h+var_390]
0x18000ec1e  mov     rax, [rcx]
0x18000ec21  mov     rax, [rax+18h]
0x18000ec25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec2a  mov     [rsp+3F0h+var_398], eax
0x18000ec2e  mov     [rsp+3F0h+var_388], ebx
0x18000ec32  jmp     short loc_18000EC55
0x18000ec34  mov     rdx, r13; char *
0x18000ec37  lea     rcx, [rsp+3F0h+var_3B0]; lpTlsValue
0x18000ec3c  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000ec41  lea     rdx, [rsp+3F0h+var_398]; unsigned int *
0x18000ec46  lea     rcx, [rsp+3F0h+pguid]; struct _GUID *
0x18000ec4b  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x18000ec50  mov     [rsp+3F0h+var_388], r14d
0x18000ec55  lea     r12, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000ec5c  mov     [rsp+3F0h+var_3B0], r12
0x18000ec61  mov     [rsp+3F0h+var_380], r13
0x18000ec66  mov     qword ptr [rsp+3F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000ec6f  mov     [rbp+2F0h+var_370], r14d
0x18000ec73  xor     edx, edx; Val
0x18000ec75  mov     r8d, 208h; Size
0x18000ec7b  lea     rcx, [rbp+2F0h+var_36C]; void *
0x18000ec7f  call    memset_0
0x18000ec84  cmp     [rbp+2F0h+var_370], r14d
0x18000ec88  jz      short loc_18000ECAE
0x18000ec8a  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000ec91  jz      short loc_18000ECAE
0x18000ec93  mov     r9d, [rsp+3F0h+var_398]
0x18000ec98  mov     r8, [rsp+3F0h+var_380]
0x18000ec9d  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x18000eca4  mov     ecx, 2; int
0x18000eca9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ecae  mov     esi, cs:?g_DebugTraceComponent@@3KA; ulong g_DebugTraceComponent
0x18000ecb4  and     esi, 1
0x18000ecb7  mov     qword ptr [rsp+3F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000ecc0  lea     rdx, [rsp+3F0h+Pid+4]; Pid
0x18000ecc5  xor     ecx, ecx; Binding
0x18000ecc7  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000eccd  mov     ebx, eax
0x18000eccf  test    eax, eax
0x18000ecd1  jle     short loc_18000ECDC
0x18000ecd3  movzx   ebx, ax
0x18000ecd6  or      ebx, 80070000h
0x18000ecdc  test    ebx, ebx
0x18000ecde  js      loc_18000ED7D
0x18000ece4  lea     rdx, [rsp+3F0h+Pid]; pSessionId
0x18000ece9  mov     ecx, [rsp+3F0h+Pid+4]; dwProcessId
0x18000eced  call    cs:__imp_ProcessIdToSessionId
0x18000ecf3  test    esi, esi
0x18000ecf5  jz      loc_18000ED7D
0x18000ecfb  mov     r8d, [rsp+3F0h+Pid+4]; dwProcessId
0x18000ed00  xor     edx, edx; bInheritHandle
0x18000ed02  mov     ecx, 400h; dwDesiredAccess
0x18000ed07  call    cs:__imp_OpenProcess
0x18000ed0d  mov     rsi, rax
0x18000ed10  test    rax, rax
0x18000ed13  jz      short loc_18000ED7D
0x18000ed15  mov     [rsp+3F0h+ReturnLength], r14; ReturnLength
0x18000ed1a  mov     r9d, 110h; ProcessInformationLength
0x18000ed20  lea     r8, [rbp+2F0h+ProcessInformation]; ProcessInformation
0x18000ed27  mov     edx, 1Bh; ProcessInformationClass
0x18000ed2c  mov     rcx, rax; ProcessHandle
0x18000ed2f  call    cs:__imp_NtQueryInformationProcess
0x18000ed35  mov     ebx, eax
0x18000ed37  or      ebx, 10000000h
0x18000ed3d  jl      short loc_18000ED74
0x18000ed3f  mov     edx, 5Ch ; '\'; Ch
0x18000ed44  mov     rcx, [rbp+2F0h+Str]; Str
0x18000ed4b  call    cs:__imp_wcsrchr
0x18000ed51  test    rax, rax
0x18000ed54  jnz     short loc_18000ED5F
0x18000ed56  mov     rax, [rbp+2F0h+Str]
0x18000ed5d  jmp     short loc_18000ED63
0x18000ed5f  add     rax, 2
0x18000ed63  mov     r8, rax; unsigned __int16 *
0x18000ed66  mov     edx, 104h; unsigned __int64
0x18000ed6b  lea     rcx, [rbp+2F0h+var_36C]; unsigned __int16 *
0x18000ed6f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ed74  mov     rcx, rsi; hObject
0x18000ed77  call    cs:__imp_CloseHandle
0x18000ed7d  cmp     [rbp+2F0h+var_370], r14d
0x18000ed81  jz      short loc_18000EDD0
0x18000ed83  test    ebx, ebx
0x18000ed85  js      short loc_18000EDB6
0x18000ed87  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000ed8e  jz      short loc_18000EDD0
0x18000ed90  lea     rax, [rbp+2F0h+var_36C]
0x18000ed94  mov     [rsp+3F0h+ReturnLength], rax
0x18000ed99  mov     r9d, [rsp+3F0h+Pid]
0x18000ed9e  mov     r8d, [rsp+3F0h+Pid+4]
0x18000eda3  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x18000edaa  mov     ecx, 2; int
0x18000edaf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000edb4  jmp     short loc_18000EDD0
0x18000edb6  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000edbd  jz      short loc_18000EDD0
0x18000edbf  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x18000edc6  mov     ecx, 2; int
0x18000edcb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000edd0  test    rdi, rdi
0x18000edd3  jnz     short loc_18000EDF7
0x18000edd5  mov     r9, r13
0x18000edd8  lea     r8, aPhlistener; "phListener"
0x18000eddf  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18000ede6  mov     ecx, 8; int
0x18000edeb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000edf0  mov     ebx, 80070057h
0x18000edf5  jmp     short loc_18000EE0C
0x18000edf7  mov     rcx, [rdi]
0x18000edfa  mov     rax, [rcx]
0x18000edfd  mov     rax, [rax+10h]
0x18000ee01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee06  mov     [rdi], r14
0x18000ee09  mov     ebx, r14d
0x18000ee0c  mov     [rsp+3F0h+var_3B0], r12
0x18000ee11  cmp     [rbp+2F0h+var_370], 0
0x18000ee15  jz      short loc_18000EE3B
0x18000ee17  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000ee1e  jz      short loc_18000EE3B
0x18000ee20  mov     r9d, [rsp+3F0h+var_398]
0x18000ee25  mov     r8, [rsp+3F0h+var_380]
0x18000ee2a  lea     rdx, aSWithTraceId0x; "%s with Trace ID 0x%x Completed"
0x18000ee31  mov     ecx, 2; int
0x18000ee36  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ee3b  mov     [rsp+3F0h+var_3B0], r15
0x18000ee40  cmp     cs:?g_bEnabled@CTraceBase@@0HA, 0; int CTraceBase::g_bEnabled
0x18000ee47  jz      short loc_18000EE88
0x18000ee49  cmp     [rsp+3F0h+var_388], 0
0x18000ee4e  jnz     short loc_18000EE88
0x18000ee50  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x18000ee56  cmp     ecx, 0FFFFFFFFh
0x18000ee59  jz      short loc_18000EE88
0x18000ee5b  xor     edx, edx; lpTlsValue
0x18000ee5d  call    cs:__imp_TlsSetValue
0x18000ee63  test    eax, eax
0x18000ee65  jnz     short loc_18000EE6F
0x18000ee67  call    cs:__imp_GetLastError
0x18000ee6d  jmp     short loc_18000EE81
0x18000ee6f  xor     edx, edx; lpTlsValue
0x18000ee71  mov     ecx, cs:?g_CreatorFunctionTLSIndex@CTraceBase@@0KA; dwTlsIndex
0x18000ee77  call    cs:__imp_TlsSetValue
0x18000ee7d  test    eax, eax
0x18000ee7f  jnz     short loc_18000EE88
0x18000ee81  call    cs:__imp_GetLastError
0x18000ee87  nop
0x18000ee88  mov     eax, ebx
0x18000ee8a  mov     rcx, [rbp+2F0h+var_50]
0x18000ee91  xor     rcx, rsp; StackCookie
0x18000ee94  call    __security_check_cookie
0x18000ee99  add     rsp, 3B8h
0x18000eea0  pop     r15
0x18000eea2  pop     r14
0x18000eea4  pop     r13
0x18000eea6  pop     r12
0x18000eea8  pop     rdi
0x18000eea9  pop     rsi
0x18000eeaa  pop     rbx
0x18000eeab  pop     rbp
0x18000eeac  retn
```
