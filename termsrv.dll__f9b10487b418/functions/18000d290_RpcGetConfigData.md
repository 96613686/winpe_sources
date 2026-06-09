# RpcGetConfigData

- ea: `0x18000d290`
- end: `0x18000d7c8`
- name: `RpcGetConfigData`
- size: `1336`
- prototype: `__int64 __fastcall(__int64, unsigned int, _QWORD *, _DWORD *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800092f0`
- `0x18000a210`
- `0x18000d290`
- `0x18000f790`
- `0x1800119a0`
- `0x1800127b0`
- `0x180014de0`
- `0x1800321f0`
- `0x1800330c4`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000d4de`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000d4de`
- `ntdll!NtQueryInformationProcess` at `0x18000d4c2`
- `ntdll!NtQueryInformationProcess` at `0x18000d4c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d749`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d763`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d749`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d763`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000d481`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000d481`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000d73f`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000d759`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000d73f`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000d759`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d50a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d50a`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000d45d`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000d45d`
- `RPCRT4!RpcRevertToSelf` at `0x18000d6b2`
- `RPCRT4!RpcRevertToSelf` at `0x18000d6b2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000d49a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000d49a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d638`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d638`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d69d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d69d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000d30a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000d30a`

## string_xrefs

- `0x18000d705`: `%s with Trace ID 0x%x Completed`
- `0x18000d2f5`: `RpcGetConfigData`
- `0x18000d56d`: `RpcGetConfigData`
- `0x18000d60c`: `RpcGetConfigData`
- `0x18000d66d`: `RpcGetConfigData`
- `0x18000d566`: `ppConfig`
- `0x18000d677`: `ptrRemoteTerminal->GetConfigData failed: 0x%x in %s`
- `0x18000d372`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18000d534`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
__int64 __fastcall RpcGetConfigData(__int64 a1, unsigned int a2, _QWORD *a3, _DWORD *a4)
{
  int v7; // esi
  unsigned int v8; // edi
  RPC_STATUS v9; // eax
  int v10; // ebx
  HANDLE v11; // rax
  void *v12; // rdi
  NTSTATUS InformationProcess; // eax
  wchar_t *v14; // rax
  wchar_t *v15; // rax
  const char *v16; // r8
  unsigned int v17; // edi
  int v18; // eax
  __int64 v19; // rsi
  _BYTE *v20; // rax
  _BYTE *v21; // rbx
  int v22; // eax
  void *v23; // rcx
  int v24; // eax
  bool v25; // sf
  int TokenHandle; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v28; // [rsp+38h] [rbp-C8h] BYREF
  struct ITerminal *v29; // [rsp+40h] [rbp-C0h] BYREF
  struct CTraceBase *v30; // [rsp+48h] [rbp-B8h] BYREF
  void **v31; // [rsp+50h] [rbp-B0h] BYREF
  GUID pguid; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v33[2]; // [rsp+68h] [rbp-98h] BYREF
  struct CTraceBase *v34; // [rsp+70h] [rbp-90h] BYREF
  int v35; // [rsp+78h] [rbp-88h]
  const char *v36; // [rsp+80h] [rbp-80h]
  unsigned int Pid[2]; // [rsp+88h] [rbp-78h] BYREF
  int v38; // [rsp+90h] [rbp-70h]
  unsigned __int16 v39[262]; // [rsp+94h] [rbp-6Ch] BYREF
  _BYTE ProcessInformation[8]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wchar_t *Str; // [rsp+2A8h] [rbp+1A8h]

  v29 = 0;
  v28 = 0;
  TokenHandle = 0;
  v31 = &CTraceBase::`vftable';
  v7 = 1;
  v33[1] = 1;
  v34 = 0;
  if ( !CTraceBase::g_bEnabled )
  {
    CoCreateGuid(&pguid);
    v33[0] = _InterlockedIncrement((volatile signed __int32 *)&CTraceBase::g_NextShortActivityID);
LABEL_13:
    v35 = 0;
    goto LABEL_14;
  }
  if ( (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "Adding trace %p, %d, %s", &v31, 1, "RpcGetConfigData");
  v30 = 0;
  if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v30) >= 0 && v30 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(
      2,
      "TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC",
      1);
  CTraceBase::ResetThreadCurrentOperationTrace(0, 0);
  if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v34) < 0 || !v34 )
  {
    CTraceBase::ResetThreadCurrentOperationTrace((struct CTraceBase *)&v31, "RpcGetConfigData");
    CTraceBase::GenerateTraceID(&pguid, v33);
    goto LABEL_13;
  }
  (*(void (__fastcall **)(struct CTraceBase *, GUID *))(*(_QWORD *)v34 + 32LL))(v34, &pguid);
  v33[0] = (*(__int64 (__fastcall **)(struct CTraceBase *))(*(_QWORD *)v34 + 24LL))(v34);
  v35 = 1;
LABEL_14:
  v31 = &CRpcCallTrace::`vftable';
  v36 = "RpcGetConfigData";
  *(_QWORD *)Pid = -1;
  v38 = 0;
  memset_0(v39, 0, 0x208u);
  if ( v38 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "TRACE RPC %s with Trace ID 0x%x", v36, v33[0]);
  v8 = g_DebugTraceComponent & 1;
  *(_QWORD *)Pid = -1;
  v9 = I_RpcBindingInqLocalClientPID(0, &Pid[1]);
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  if ( v10 >= 0 )
  {
    ProcessIdToSessionId(Pid[1], Pid);
    if ( v8 )
    {
      v11 = OpenProcess(0x400u, 0, Pid[1]);
      v12 = v11;
      if ( v11 )
      {
        InformationProcess = NtQueryInformationProcess(v11, ProcessImageFileName, ProcessInformation, 0x110u, 0);
        v10 = InformationProcess | 0x10000000;
        if ( InformationProcess >= 0 )
        {
          v14 = wcsrchr(Str, 0x5Cu);
          if ( v14 )
            v15 = v14 + 1;
          else
            v15 = Str;
          StringCchCopyW(v39, 0x104u, v15);
        }
        CloseHandle(v12);
      }
    }
  }
  if ( v38 )
  {
    if ( v10 < 0 )
    {
      if ( (g_DebugTraceComponent & 1) != 0 )
        _DbgPrintMessage(2, "RPC Caller: Unknown");
    }
    else if ( (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(2, "RPC Caller: PID %d, SessID %d, Process Name: <%S>", Pid[1], Pid[0], v39);
    }
  }
  if ( !a3 )
  {
    v16 = "ppConfig";
LABEL_36:
    _DbgPrintMessage(8, "Missing paramter %s in %s", v16, "RpcGetConfigData");
    v17 = -2147024809;
    goto LABEL_57;
  }
  if ( !a4 )
  {
    v16 = "pOutBuffByteLen";
    goto LABEL_36;
  }
  v18 = RCMRpcPrologueEx(a2, 1u, 1u, &v29, 0, &TokenHandle);
  v17 = v18;
  if ( v18 >= 0 )
  {
    if ( (**(int (__fastcall ***)(struct ITerminal *, __int64 *, __int64 *))v29)(v29, qword_1800D7370, &v28) >= 0 )
    {
      v19 = 2664;
      v20 = LocalAlloc(0x40u, 0xA68u);
      v21 = v20;
      if ( v20 )
      {
        v22 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)v28 + 240LL))(v28, v20, 2664);
        v17 = v22;
        if ( v22 >= 0 )
        {
          *a3 = v21;
          *a4 = 2664;
        }
        else
        {
          _DbgPrintMessage(8, "ptrRemoteTerminal->GetConfigData failed: 0x%x in %s", v22, "RpcGetConfigData");
          v23 = v21;
          do
          {
            *v21++ = 0;
            --v19;
          }
          while ( v19 );
          LocalFree(v23);
        }
      }
      else
      {
        v17 = -2147024882;
      }
    }
    else
    {
      v17 = -2147022646;
      _DbgPrintMessage(4, "QI on IID_IRemoteTerminal failed: 0x%x in %s", -2147022646, "RpcGetConfigData");
    }
  }
  else
  {
    if ( v18 != -2147022646 )
      v7 = 4;
    _DbgPrintMessage(v7, "RCMRpcPrologue failed: 0x%x", v18);
  }
  if ( TokenHandle )
  {
    v24 = RpcRevertToSelf();
    v25 = v24 < 0;
    if ( v24 > 0 )
    {
      v24 = (unsigned __int16)v24 | 0x80070000;
      v25 = v24 < 0;
    }
    if ( v25 )
    {
      _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v24);
      v17 = -2147024891;
    }
  }
LABEL_57:
  v31 = &CRpcCallTrace::`vftable';
  if ( v38 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "%s with Trace ID 0x%x Completed", v36, v33[0]);
  v31 = &CTraceBase::`vftable';
  if ( !v35 && CTraceBase::g_bEnabled && CTraceBase::g_TLSIndex != -1 )
  {
    if ( TlsSetValue(CTraceBase::g_TLSIndex, 0) )
    {
      if ( TlsSetValue(CTraceBase::g_CreatorFunctionTLSIndex, 0) )
        goto LABEL_67;
    }
    else
    {
      GetLastError();
    }
    GetLastError();
  }
LABEL_67:
  v34 = 0;
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  if ( v29 )
    (*(void (__fastcall **)(struct ITerminal *))(*(_QWORD *)v29 + 16LL))(v29);
  return v17;
}

```

## disassembly

```asm
0x18000d290  mov     [rsp-8+arg_0], rbx
0x18000d295  push    rbp
0x18000d296  push    rsi
0x18000d297  push    rdi
0x18000d298  push    r12
0x18000d29a  push    r13
0x18000d29c  push    r14
0x18000d29e  push    r15
0x18000d2a0  lea     rbp, [rsp-2C0h]
0x18000d2a8  sub     rsp, 3C0h
0x18000d2af  mov     rax, cs:__security_cookie
0x18000d2b6  xor     rax, rsp
0x18000d2b9  mov     [rbp+2F0h+var_40], rax
0x18000d2c0  mov     r15, r9
0x18000d2c3  mov     r14, r8
0x18000d2c6  mov     r12d, edx
0x18000d2c9  xor     r13d, r13d
0x18000d2cc  mov     [rsp+3F0h+var_3B0], r13
0x18000d2d1  mov     [rsp+3F0h+var_3B8], r13
0x18000d2d6  mov     [rsp+3F0h+var_3C0], r13d
0x18000d2db  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000d2e2  mov     [rsp+3F0h+var_3A0], rax
0x18000d2e7  mov     esi, 1
0x18000d2ec  mov     [rsp+3F0h+var_384], esi
0x18000d2f0  mov     [rsp+3F0h+var_380], r13
0x18000d2f5  lea     rbx, aRpcgetconfigda; "RpcGetConfigData"
0x18000d2fc  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r13d; int CTraceBase::g_bEnabled
0x18000d303  jnz     short loc_18000D325
0x18000d305  lea     rcx, [rsp+3F0h+pguid]; pguid
0x18000d30a  call    cs:__imp_CoCreateGuid
0x18000d310  mov     eax, esi
0x18000d312  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x18000d31a  inc     eax
0x18000d31c  mov     [rsp+3F0h+var_388], eax
0x18000d320  jmp     loc_18000D3EC
0x18000d325  test    byte ptr cs:?g_DebugTraceComponent@@3KA, sil; ulong g_DebugTraceComponent
0x18000d32c  jz      short loc_18000D34C
0x18000d32e  mov     [rsp+3F0h+ReturnLength], rbx
0x18000d333  mov     r9d, esi
0x18000d336  lea     r8, [rsp+3F0h+var_3A0]
0x18000d33b  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x18000d342  mov     ecx, 2; int
0x18000d347  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d34c  mov     [rsp+3F0h+var_3A8], r13
0x18000d351  lea     rcx, [rsp+3F0h+var_3A8]; struct CTraceBase **
0x18000d356  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000d35b  test    eax, eax
0x18000d35d  js      short loc_18000D383
0x18000d35f  cmp     [rsp+3F0h+var_3A8], r13
0x18000d364  jz      short loc_18000D383
0x18000d366  test    byte ptr cs:?g_DebugTraceComponent@@3KA, sil; ulong g_DebugTraceComponent
0x18000d36d  jz      short loc_18000D383
0x18000d36f  mov     r8d, esi
0x18000d372  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x18000d379  mov     ecx, 2; int
0x18000d37e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d383  xor     edx, edx; char *
0x18000d385  xor     ecx, ecx; lpTlsValue
0x18000d387  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000d38c  lea     rcx, [rsp+3F0h+var_380]; struct CTraceBase **
0x18000d391  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000d396  test    eax, eax
0x18000d398  js      short loc_18000D3D0
0x18000d39a  mov     rcx, [rsp+3F0h+var_380]
0x18000d39f  test    rcx, rcx
0x18000d3a2  jz      short loc_18000D3D0
0x18000d3a4  mov     rax, [rcx]
0x18000d3a7  lea     rdx, [rsp+3F0h+pguid]
0x18000d3ac  mov     rax, [rax+20h]
0x18000d3b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3b5  mov     rcx, [rsp+3F0h+var_380]
0x18000d3ba  mov     rax, [rcx]
0x18000d3bd  mov     rax, [rax+18h]
0x18000d3c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3c6  mov     [rsp+3F0h+var_388], eax
0x18000d3ca  mov     [rsp+3F0h+var_378], esi
0x18000d3ce  jmp     short loc_18000D3F1
0x18000d3d0  mov     rdx, rbx; char *
0x18000d3d3  lea     rcx, [rsp+3F0h+var_3A0]; lpTlsValue
0x18000d3d8  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000d3dd  lea     rdx, [rsp+3F0h+var_388]; unsigned int *
0x18000d3e2  lea     rcx, [rsp+3F0h+pguid]; struct _GUID *
0x18000d3e7  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x18000d3ec  mov     [rsp+3F0h+var_378], r13d
0x18000d3f1  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000d3f8  mov     [rsp+3F0h+var_3A0], rax
0x18000d3fd  mov     [rbp+2F0h+var_370], rbx
0x18000d401  mov     qword ptr [rbp+2F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000d409  mov     [rbp+2F0h+var_360], r13d
0x18000d40d  xor     edx, edx; Val
0x18000d40f  mov     r8d, 208h; Size
0x18000d415  lea     rcx, [rbp+2F0h+var_35C]; void *
0x18000d419  call    memset_0
0x18000d41e  cmp     [rbp+2F0h+var_360], r13d
0x18000d422  jz      short loc_18000D447
0x18000d424  test    byte ptr cs:?g_DebugTraceComponent@@3KA, sil; ulong g_DebugTraceComponent
0x18000d42b  jz      short loc_18000D447
0x18000d42d  mov     r9d, [rsp+3F0h+var_388]
0x18000d432  mov     r8, [rbp+2F0h+var_370]
0x18000d436  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x18000d43d  mov     ecx, 2; int
0x18000d442  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d447  mov     edi, cs:?g_DebugTraceComponent@@3KA; ulong g_DebugTraceComponent
0x18000d44d  and     edi, esi
0x18000d44f  mov     qword ptr [rbp+2F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000d457  lea     rdx, [rbp+2F0h+Pid+4]; Pid
0x18000d45b  xor     ecx, ecx; Binding
0x18000d45d  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000d463  mov     ebx, eax
0x18000d465  test    eax, eax
0x18000d467  jle     short loc_18000D472
0x18000d469  movzx   ebx, ax
0x18000d46c  or      ebx, 80070000h
0x18000d472  test    ebx, ebx
0x18000d474  js      loc_18000D510
0x18000d47a  lea     rdx, [rbp+2F0h+Pid]; pSessionId
0x18000d47e  mov     ecx, [rbp+2F0h+Pid+4]; dwProcessId
0x18000d481  call    cs:__imp_ProcessIdToSessionId
0x18000d487  test    edi, edi
0x18000d489  jz      loc_18000D510
0x18000d48f  mov     r8d, [rbp+2F0h+Pid+4]; dwProcessId
0x18000d493  xor     edx, edx; bInheritHandle
0x18000d495  mov     ecx, 400h; dwDesiredAccess
0x18000d49a  call    cs:__imp_OpenProcess
0x18000d4a0  mov     rdi, rax
0x18000d4a3  test    rax, rax
0x18000d4a6  jz      short loc_18000D510
0x18000d4a8  mov     [rsp+3F0h+ReturnLength], r13; ReturnLength
0x18000d4ad  mov     r9d, 110h; ProcessInformationLength
0x18000d4b3  lea     r8, [rbp+2F0h+ProcessInformation]; ProcessInformation
0x18000d4ba  mov     edx, 1Bh; ProcessInformationClass
0x18000d4bf  mov     rcx, rax; ProcessHandle
0x18000d4c2  call    cs:__imp_NtQueryInformationProcess
0x18000d4c8  mov     ebx, eax
0x18000d4ca  or      ebx, 10000000h
0x18000d4d0  jl      short loc_18000D507
0x18000d4d2  mov     edx, 5Ch ; '\'; Ch
0x18000d4d7  mov     rcx, [rbp+2F0h+Str]; Str
0x18000d4de  call    cs:__imp_wcsrchr
0x18000d4e4  test    rax, rax
0x18000d4e7  jnz     short loc_18000D4F2
0x18000d4e9  mov     rax, [rbp+2F0h+Str]
0x18000d4f0  jmp     short loc_18000D4F6
0x18000d4f2  add     rax, 2
0x18000d4f6  mov     r8, rax; unsigned __int16 *
0x18000d4f9  mov     edx, 104h; unsigned __int64
0x18000d4fe  lea     rcx, [rbp+2F0h+var_35C]; unsigned __int16 *
0x18000d502  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d507  mov     rcx, rdi; hObject
0x18000d50a  call    cs:__imp_CloseHandle
0x18000d510  cmp     [rbp+2F0h+var_360], r13d
0x18000d514  jz      short loc_18000D561
0x18000d516  test    ebx, ebx
0x18000d518  js      short loc_18000D547
0x18000d51a  test    byte ptr cs:?g_DebugTraceComponent@@3KA, sil; ulong g_DebugTraceComponent
0x18000d521  jz      short loc_18000D561
0x18000d523  lea     rax, [rbp+2F0h+var_35C]
0x18000d527  mov     [rsp+3F0h+ReturnLength], rax
0x18000d52c  mov     r9d, [rbp+2F0h+Pid]
0x18000d530  mov     r8d, [rbp+2F0h+Pid+4]
0x18000d534  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x18000d53b  mov     ecx, 2; int
0x18000d540  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d545  jmp     short loc_18000D561
0x18000d547  test    byte ptr cs:?g_DebugTraceComponent@@3KA, sil; ulong g_DebugTraceComponent
0x18000d54e  jz      short loc_18000D561
0x18000d550  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x18000d557  mov     ecx, 2; int
0x18000d55c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d561  test    r14, r14
0x18000d564  jnz     short loc_18000D58F
0x18000d566  lea     r8, aPpconfig; "ppConfig"
0x18000d56d  lea     r9, aRpcgetconfigda; "RpcGetConfigData"
0x18000d574  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18000d57b  mov     ecx, 8; int
0x18000d580  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d585  mov     edi, 80070057h
0x18000d58a  jmp     loc_18000D6E1
0x18000d58f  test    r15, r15
0x18000d592  jnz     short loc_18000D59D
0x18000d594  lea     r8, aPoutbuffbytele; "pOutBuffByteLen"
0x18000d59b  jmp     short loc_18000D56D
0x18000d59d  lea     rax, [rsp+3F0h+var_3C0]
0x18000d5a2  mov     [rsp+3F0h+TokenHandle], rax; TokenHandle
0x18000d5a7  mov     [rsp+3F0h+ReturnLength], r13; struct ITSSession **
0x18000d5ac  lea     r9, [rsp+3F0h+var_3B0]; struct ITerminal **
0x18000d5b1  mov     r8d, esi; int
0x18000d5b4  mov     edx, esi; unsigned int
0x18000d5b6  mov     ecx, r12d; unsigned int
0x18000d5b9  call    ?RCMRpcPrologueEx@@YAJKKHPEAPEAUITerminal@@PEAPEAUITSSession@@PEAH@Z; RCMRpcPrologueEx(ulong,ulong,int,ITerminal * *,ITSSession * *,int *)
0x18000d5be  mov     edi, eax
0x18000d5c0  test    eax, eax
0x18000d5c2  jns     short loc_18000D5E7
0x18000d5c4  mov     ecx, 4
0x18000d5c9  cmp     eax, 800708CAh
0x18000d5ce  cmovnz  esi, ecx
0x18000d5d1  mov     r8d, eax
0x18000d5d4  lea     rdx, aRcmrpcprologue; "RCMRpcPrologue failed: 0x%x"
0x18000d5db  mov     ecx, esi; int
0x18000d5dd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d5e2  jmp     loc_18000D6AB
0x18000d5e7  mov     rcx, [rsp+3F0h+var_3B0]
0x18000d5ec  mov     rax, [rcx]
0x18000d5ef  lea     r8, [rsp+3F0h+var_3B8]
0x18000d5f4  lea     rdx, qword_1800D7370
0x18000d5fb  mov     rax, [rax]
0x18000d5fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d603  test    eax, eax
0x18000d605  jns     short loc_18000D62C
0x18000d607  mov     edi, 800708CAh
0x18000d60c  lea     r9, aRpcgetconfigda; "RpcGetConfigData"
0x18000d613  mov     r8d, edi
0x18000d616  lea     rdx, aQiOnIidIremote; "QI on IID_IRemoteTerminal failed: 0x%x "...
0x18000d61d  mov     ecx, 4; int
0x18000d622  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d627  jmp     loc_18000D6AB
0x18000d62c  mov     esi, 0A68h
0x18000d631  mov     edx, esi; uBytes
0x18000d633  mov     ecx, 40h ; '@'; uFlags
0x18000d638  call    cs:__imp_LocalAlloc
0x18000d63e  mov     rbx, rax
0x18000d641  test    rax, rax
0x18000d644  jnz     short loc_18000D64D
0x18000d646  mov     edi, 8007000Eh
0x18000d64b  jmp     short loc_18000D6AB
0x18000d64d  mov     rcx, [rsp+3F0h+var_3B8]
0x18000d652  mov     rax, [rcx]
0x18000d655  mov     r8d, esi
0x18000d658  mov     rdx, rbx
0x18000d65b  mov     rax, [rax+0F0h]
0x18000d662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d667  mov     edi, eax
0x18000d669  test    eax, eax
0x18000d66b  jns     short loc_18000D6A5
0x18000d66d  lea     r9, aRpcgetconfigda; "RpcGetConfigData"
0x18000d674  mov     r8d, eax
0x18000d677  lea     rdx, aPtrremotetermi_7; "ptrRemoteTerminal->GetConfigData failed"...
0x18000d67e  mov     ecx, 8; int
0x18000d683  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d688  mov     rcx, rbx; hMem
0x18000d68b  nop     dword ptr [rax+rax+00h]
0x18000d690  mov     [rbx], r13b
0x18000d693  lea     rbx, [rbx+1]
0x18000d697  sub     rsi, 1
0x18000d69b  jnz     short loc_18000D690
0x18000d69d  call    cs:__imp_LocalFree
0x18000d6a3  jmp     short loc_18000D6AB
0x18000d6a5  mov     [r14], rbx
0x18000d6a8  mov     [r15], esi
0x18000d6ab  cmp     [rsp+3F0h+var_3C0], r13d
0x18000d6b0  jz      short loc_18000D6E1
0x18000d6b2  call    cs:__imp_RpcRevertToSelf
0x18000d6b8  test    eax, eax
0x18000d6ba  jle     short loc_18000D6C6
0x18000d6bc  movzx   eax, ax
0x18000d6bf  or      eax, 80070000h
0x18000d6c4  test    eax, eax
0x18000d6c6  jns     short loc_18000D6E1
0x18000d6c8  mov     r8d, eax
0x18000d6cb  lea     rdx, aRpcreverttosel_1; "RpcRevertToSelf failed: 0x%x"
0x18000d6d2  mov     ecx, 8; int
0x18000d6d7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d6dc  mov     edi, 80070005h
0x18000d6e1  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000d6e8  mov     [rsp+3F0h+var_3A0], rax
0x18000d6ed  cmp     [rbp+2F0h+var_360], 0
0x18000d6f1  jz      short loc_18000D716
0x18000d6f3  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000d6fa  jz      short loc_18000D716
0x18000d6fc  mov     r9d, [rsp+3F0h+var_388]
0x18000d701  mov     r8, [rbp+2F0h+var_370]
0x18000d705  lea     rdx, aSWithTraceId0x; "%s with Trace ID 0x%x Completed"
0x18000d70c  mov     ecx, 2; int
0x18000d711  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d716  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000d71d  mov     [rsp+3F0h+var_3A0], rax
0x18000d722  cmp     [rsp+3F0h+var_378], 0
0x18000d727  jnz     short loc_18000D769
0x18000d729  cmp     cs:?g_bEnabled@CTraceBase@@0HA, 0; int CTraceBase::g_bEnabled
0x18000d730  jz      short loc_18000D769
0x18000d732  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x18000d738  cmp     ecx, 0FFFFFFFFh
0x18000d73b  jz      short loc_18000D769
0x18000d73d  xor     edx, edx; lpTlsValue
0x18000d73f  call    cs:__imp_TlsSetValue
0x18000d745  test    eax, eax
0x18000d747  jnz     short loc_18000D751
0x18000d749  call    cs:__imp_GetLastError
0x18000d74f  jmp     short loc_18000D763
0x18000d751  xor     edx, edx; lpTlsValue
0x18000d753  mov     ecx, cs:?g_CreatorFunctionTLSIndex@CTraceBase@@0KA; dwTlsIndex
0x18000d759  call    cs:__imp_TlsSetValue
0x18000d75f  test    eax, eax
0x18000d761  jnz     short loc_18000D769
0x18000d763  call    cs:__imp_GetLastError
0x18000d769  mov     [rsp+3F0h+var_380], r13
0x18000d76e  mov     rcx, [rsp+3F0h+var_3B8]
0x18000d773  test    rcx, rcx
0x18000d776  jz      short loc_18000D785
0x18000d778  mov     rax, [rcx]
  ... truncated ...
```
