# RpcGetConfigData

- ea: `0x18000da10`
- end: `0x18000df03`
- name: `RpcGetConfigData`
- size: `1267`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180008920`
- `0x180009940`
- `0x18000da10`
- `0x18000f760`
- `0x18000faf0`
- `0x180012070`
- `0x180012d10`
- `0x1800154a0`
- `0x180033f60`
- `0x180034e64`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000dc7c`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000dc7c`
- `ntdll!NtQueryInformationProcess` at `0x18000dc5a`
- `ntdll!NtQueryInformationProcess` at `0x18000dc5a`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000dc0d`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000dc0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dcae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dcae`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000dbe3`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000dbe3`
- `RPCRT4!RpcRevertToSelf` at `0x18000de68`
- `RPCRT4!RpcRevertToSelf` at `0x18000de68`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000dc2c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000dc2c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000dde2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000dde2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000de4d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000de4d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000da8a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000da8a`

## string_xrefs

- `0x18000da75`: `RpcGetConfigData`
- `0x18000dd17`: `RpcGetConfigData`
- `0x18000ddb6`: `RpcGetConfigData`
- `0x18000de1d`: `RpcGetConfigData`
- `0x18000dd10`: `ppConfig`
- `0x18000de27`: `ptrRemoteTerminal->GetConfigData failed: 0x%x in %s`
- `0x18000daf8`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18000dcde`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
    if ( (**(int (__fastcall ***)(struct ITerminal *, __int64 *, __int64 *))v29)(v29, qword_1800DD390, &v28) >= 0 )
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
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)&v31);
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  if ( v29 )
    (*(void (__fastcall **)(struct ITerminal *))(*(_QWORD *)v29 + 16LL))(v29);
  return v17;
}

```

## disassembly

```asm
0x18000da10  mov     [rsp-8+arg_0], rbx
0x18000da15  push    rbp
0x18000da16  push    rsi
0x18000da17  push    rdi
0x18000da18  push    r12
0x18000da1a  push    r13
0x18000da1c  push    r14
0x18000da1e  push    r15
0x18000da20  lea     rbp, [rsp-2C0h]
0x18000da28  sub     rsp, 3C0h
0x18000da2f  mov     rax, cs:__security_cookie
0x18000da36  xor     rax, rsp
0x18000da39  mov     [rbp+2F0h+var_40], rax
0x18000da40  mov     r15, r9
0x18000da43  mov     r14, r8
0x18000da46  mov     r12d, edx
0x18000da49  xor     r13d, r13d
0x18000da4c  mov     [rsp+3F0h+var_3B0], r13
0x18000da51  mov     [rsp+3F0h+var_3B8], r13
0x18000da56  mov     [rsp+3F0h+var_3C0], r13d
0x18000da5b  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000da62  mov     [rsp+3F0h+var_3A0], rax
0x18000da67  mov     esi, 1
0x18000da6c  mov     [rsp+3F0h+var_384], esi
0x18000da70  mov     [rsp+3F0h+var_380], r13
0x18000da75  lea     rbx, aRpcgetconfigda; "RpcGetConfigData"
0x18000da7c  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r13d; int CTraceBase::g_bEnabled
0x18000da83  jnz     short loc_18000DAAB
0x18000da85  lea     rcx, [rsp+3F0h+pguid]; pguid
0x18000da8a  call    cs:__imp_CoCreateGuid
0x18000da91  nop     dword ptr [rax+rax+00h]
0x18000da96  mov     eax, esi
0x18000da98  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x18000daa0  inc     eax
0x18000daa2  mov     [rsp+3F0h+var_388], eax
0x18000daa6  jmp     loc_18000DB72
0x18000daab  test    byte ptr cs:?g_DebugTraceComponent@@3KA, sil; ulong g_DebugTraceComponent
0x18000dab2  jz      short loc_18000DAD2
0x18000dab4  mov     [rsp+3F0h+ReturnLength], rbx
0x18000dab9  mov     r9d, esi
0x18000dabc  lea     r8, [rsp+3F0h+var_3A0]
0x18000dac1  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x18000dac8  mov     ecx, 2; int
0x18000dacd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000dad2  mov     [rsp+3F0h+var_3A8], r13
0x18000dad7  lea     rcx, [rsp+3F0h+var_3A8]; struct CTraceBase **
0x18000dadc  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000dae1  test    eax, eax
0x18000dae3  js      short loc_18000DB09
0x18000dae5  cmp     [rsp+3F0h+var_3A8], r13
0x18000daea  jz      short loc_18000DB09
0x18000daec  test    byte ptr cs:?g_DebugTraceComponent@@3KA, sil; ulong g_DebugTraceComponent
0x18000daf3  jz      short loc_18000DB09
0x18000daf5  mov     r8d, esi
0x18000daf8  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x18000daff  mov     ecx, 2; int
0x18000db04  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000db09  xor     edx, edx; char *
0x18000db0b  xor     ecx, ecx; lpTlsValue
0x18000db0d  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000db12  lea     rcx, [rsp+3F0h+var_380]; struct CTraceBase **
0x18000db17  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000db1c  test    eax, eax
0x18000db1e  js      short loc_18000DB56
0x18000db20  mov     rcx, [rsp+3F0h+var_380]
0x18000db25  test    rcx, rcx
0x18000db28  jz      short loc_18000DB56
0x18000db2a  mov     rax, [rcx]
0x18000db2d  lea     rdx, [rsp+3F0h+pguid]
0x18000db32  mov     rax, [rax+20h]
0x18000db36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db3b  mov     rcx, [rsp+3F0h+var_380]
0x18000db40  mov     rax, [rcx]
0x18000db43  mov     rax, [rax+18h]
0x18000db47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db4c  mov     [rsp+3F0h+var_388], eax
0x18000db50  mov     [rsp+3F0h+var_378], esi
0x18000db54  jmp     short loc_18000DB77
0x18000db56  mov     rdx, rbx; char *
0x18000db59  lea     rcx, [rsp+3F0h+var_3A0]; lpTlsValue
0x18000db5e  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000db63  lea     rdx, [rsp+3F0h+var_388]; unsigned int *
0x18000db68  lea     rcx, [rsp+3F0h+pguid]; struct _GUID *
0x18000db6d  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x18000db72  mov     [rsp+3F0h+var_378], r13d
0x18000db77  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000db7e  mov     [rsp+3F0h+var_3A0], rax
0x18000db83  mov     [rbp+2F0h+var_370], rbx
0x18000db87  mov     qword ptr [rbp+2F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000db8f  mov     [rbp+2F0h+var_360], r13d
0x18000db93  xor     edx, edx; Val
0x18000db95  mov     r8d, 208h; Size
0x18000db9b  lea     rcx, [rbp+2F0h+var_35C]; void *
0x18000db9f  call    memset_0
0x18000dba4  cmp     [rbp+2F0h+var_360], r13d
0x18000dba8  jz      short loc_18000DBCD
0x18000dbaa  test    byte ptr cs:?g_DebugTraceComponent@@3KA, sil; ulong g_DebugTraceComponent
0x18000dbb1  jz      short loc_18000DBCD
0x18000dbb3  mov     r9d, [rsp+3F0h+var_388]
0x18000dbb8  mov     r8, [rbp+2F0h+var_370]
0x18000dbbc  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x18000dbc3  mov     ecx, 2; int
0x18000dbc8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000dbcd  mov     edi, cs:?g_DebugTraceComponent@@3KA; ulong g_DebugTraceComponent
0x18000dbd3  and     edi, esi
0x18000dbd5  mov     qword ptr [rbp+2F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000dbdd  lea     rdx, [rbp+2F0h+Pid+4]; Pid
0x18000dbe1  xor     ecx, ecx; Binding
0x18000dbe3  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000dbea  nop     dword ptr [rax+rax+00h]
0x18000dbef  mov     ebx, eax
0x18000dbf1  test    eax, eax
0x18000dbf3  jle     short loc_18000DBFE
0x18000dbf5  movzx   ebx, ax
0x18000dbf8  or      ebx, 80070000h
0x18000dbfe  test    ebx, ebx
0x18000dc00  js      loc_18000DCBA
0x18000dc06  lea     rdx, [rbp+2F0h+Pid]; pSessionId
0x18000dc0a  mov     ecx, [rbp+2F0h+Pid+4]; dwProcessId
0x18000dc0d  call    cs:__imp_ProcessIdToSessionId
0x18000dc14  nop     dword ptr [rax+rax+00h]
0x18000dc19  test    edi, edi
0x18000dc1b  jz      loc_18000DCBA
0x18000dc21  mov     r8d, [rbp+2F0h+Pid+4]; dwProcessId
0x18000dc25  xor     edx, edx; bInheritHandle
0x18000dc27  mov     ecx, 400h; dwDesiredAccess
0x18000dc2c  call    cs:__imp_OpenProcess
0x18000dc33  nop     dword ptr [rax+rax+00h]
0x18000dc38  mov     rdi, rax
0x18000dc3b  test    rax, rax
0x18000dc3e  jz      short loc_18000DCBA
0x18000dc40  mov     [rsp+3F0h+ReturnLength], r13; ReturnLength
0x18000dc45  mov     r9d, 110h; ProcessInformationLength
0x18000dc4b  lea     r8, [rbp+2F0h+ProcessInformation]; ProcessInformation
0x18000dc52  mov     edx, 1Bh; ProcessInformationClass
0x18000dc57  mov     rcx, rax; ProcessHandle
0x18000dc5a  call    cs:__imp_NtQueryInformationProcess
0x18000dc61  nop     dword ptr [rax+rax+00h]
0x18000dc66  mov     ebx, eax
0x18000dc68  or      ebx, 10000000h
0x18000dc6e  jl      short loc_18000DCAB
0x18000dc70  mov     edx, 5Ch ; '\'; Ch
0x18000dc75  mov     rcx, [rbp+2F0h+Str]; Str
0x18000dc7c  call    cs:__imp_wcsrchr
0x18000dc83  nop     dword ptr [rax+rax+00h]
0x18000dc88  test    rax, rax
0x18000dc8b  jnz     short loc_18000DC96
0x18000dc8d  mov     rax, [rbp+2F0h+Str]
0x18000dc94  jmp     short loc_18000DC9A
0x18000dc96  add     rax, 2
0x18000dc9a  mov     r8, rax; unsigned __int16 *
0x18000dc9d  mov     edx, 104h; unsigned __int64
0x18000dca2  lea     rcx, [rbp+2F0h+var_35C]; unsigned __int16 *
0x18000dca6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000dcab  mov     rcx, rdi; hObject
0x18000dcae  call    cs:__imp_CloseHandle
0x18000dcb5  nop     dword ptr [rax+rax+00h]
0x18000dcba  cmp     [rbp+2F0h+var_360], r13d
0x18000dcbe  jz      short loc_18000DD0B
0x18000dcc0  test    ebx, ebx
0x18000dcc2  js      short loc_18000DCF1
0x18000dcc4  test    byte ptr cs:?g_DebugTraceComponent@@3KA, sil; ulong g_DebugTraceComponent
0x18000dccb  jz      short loc_18000DD0B
0x18000dccd  lea     rax, [rbp+2F0h+var_35C]
0x18000dcd1  mov     [rsp+3F0h+ReturnLength], rax
0x18000dcd6  mov     r9d, [rbp+2F0h+Pid]
0x18000dcda  mov     r8d, [rbp+2F0h+Pid+4]
0x18000dcde  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x18000dce5  mov     ecx, 2; int
0x18000dcea  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000dcef  jmp     short loc_18000DD0B
0x18000dcf1  test    byte ptr cs:?g_DebugTraceComponent@@3KA, sil; ulong g_DebugTraceComponent
0x18000dcf8  jz      short loc_18000DD0B
0x18000dcfa  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x18000dd01  mov     ecx, 2; int
0x18000dd06  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000dd0b  test    r14, r14
0x18000dd0e  jnz     short loc_18000DD39
0x18000dd10  lea     r8, aPpconfig; "ppConfig"
0x18000dd17  lea     r9, aRpcgetconfigda; "RpcGetConfigData"
0x18000dd1e  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18000dd25  mov     ecx, 8; int
0x18000dd2a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000dd2f  mov     edi, 80070057h
0x18000dd34  jmp     loc_18000DE9D
0x18000dd39  test    r15, r15
0x18000dd3c  jnz     short loc_18000DD47
0x18000dd3e  lea     r8, aPoutbuffbytele; "pOutBuffByteLen"
0x18000dd45  jmp     short loc_18000DD17
0x18000dd47  lea     rax, [rsp+3F0h+var_3C0]
0x18000dd4c  mov     [rsp+3F0h+TokenHandle], rax; TokenHandle
0x18000dd51  mov     [rsp+3F0h+ReturnLength], r13; struct ITSSession **
0x18000dd56  lea     r9, [rsp+3F0h+var_3B0]; struct ITerminal **
0x18000dd5b  mov     r8d, esi; int
0x18000dd5e  mov     edx, esi; unsigned int
0x18000dd60  mov     ecx, r12d; unsigned int
0x18000dd63  call    ?RCMRpcPrologueEx@@YAJKKHPEAPEAUITerminal@@PEAPEAUITSSession@@PEAH@Z; RCMRpcPrologueEx(ulong,ulong,int,ITerminal * *,ITSSession * *,int *)
0x18000dd68  mov     edi, eax
0x18000dd6a  test    eax, eax
0x18000dd6c  jns     short loc_18000DD91
0x18000dd6e  mov     ecx, 4
0x18000dd73  cmp     eax, 800708CAh
0x18000dd78  cmovnz  esi, ecx
0x18000dd7b  mov     r8d, eax
0x18000dd7e  lea     rdx, aRcmrpcprologue; "RCMRpcPrologue failed: 0x%x"
0x18000dd85  mov     ecx, esi; int
0x18000dd87  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000dd8c  jmp     loc_18000DE61
0x18000dd91  mov     rcx, [rsp+3F0h+var_3B0]
0x18000dd96  mov     rax, [rcx]
0x18000dd99  lea     r8, [rsp+3F0h+var_3B8]
0x18000dd9e  lea     rdx, qword_1800DD390
0x18000dda5  mov     rax, [rax]
0x18000dda8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddad  test    eax, eax
0x18000ddaf  jns     short loc_18000DDD6
0x18000ddb1  mov     edi, 800708CAh
0x18000ddb6  lea     r9, aRpcgetconfigda; "RpcGetConfigData"
0x18000ddbd  mov     r8d, edi
0x18000ddc0  lea     rdx, aQiOnIidIremote; "QI on IID_IRemoteTerminal failed: 0x%x "...
0x18000ddc7  mov     ecx, 4; int
0x18000ddcc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ddd1  jmp     loc_18000DE61
0x18000ddd6  mov     esi, 0A68h
0x18000dddb  mov     edx, esi; uBytes
0x18000dddd  mov     ecx, 40h ; '@'; uFlags
0x18000dde2  call    cs:__imp_LocalAlloc
0x18000dde9  nop     dword ptr [rax+rax+00h]
0x18000ddee  mov     rbx, rax
0x18000ddf1  test    rax, rax
0x18000ddf4  jnz     short loc_18000DDFD
0x18000ddf6  mov     edi, 8007000Eh
0x18000ddfb  jmp     short loc_18000DE61
0x18000ddfd  mov     rcx, [rsp+3F0h+var_3B8]
0x18000de02  mov     rax, [rcx]
0x18000de05  mov     r8d, esi
0x18000de08  mov     rdx, rbx
0x18000de0b  mov     rax, [rax+0F0h]
0x18000de12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de17  mov     edi, eax
0x18000de19  test    eax, eax
0x18000de1b  jns     short loc_18000DE5B
0x18000de1d  lea     r9, aRpcgetconfigda; "RpcGetConfigData"
0x18000de24  mov     r8d, eax
0x18000de27  lea     rdx, aPtrremotetermi_7; "ptrRemoteTerminal->GetConfigData failed"...
0x18000de2e  mov     ecx, 8; int
0x18000de33  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000de38  mov     rcx, rbx; hMem
0x18000de3b  nop     dword ptr [rax+rax+00h]
0x18000de40  mov     [rbx], r13b
0x18000de43  lea     rbx, [rbx+1]
0x18000de47  sub     rsi, 1
0x18000de4b  jnz     short loc_18000DE40
0x18000de4d  call    cs:__imp_LocalFree
0x18000de54  nop     dword ptr [rax+rax+00h]
0x18000de59  jmp     short loc_18000DE61
0x18000de5b  mov     [r14], rbx
0x18000de5e  mov     [r15], esi
0x18000de61  cmp     [rsp+3F0h+var_3C0], r13d
0x18000de66  jz      short loc_18000DE9D
0x18000de68  call    cs:__imp_RpcRevertToSelf
0x18000de6f  nop     dword ptr [rax+rax+00h]
0x18000de74  test    eax, eax
0x18000de76  jle     short loc_18000DE82
0x18000de78  movzx   eax, ax
0x18000de7b  or      eax, 80070000h
0x18000de80  test    eax, eax
0x18000de82  jns     short loc_18000DE9D
0x18000de84  mov     r8d, eax
0x18000de87  lea     rdx, aRpcreverttosel_1; "RpcRevertToSelf failed: 0x%x"
0x18000de8e  mov     ecx, 8; int
0x18000de93  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000de98  mov     edi, 80070005h
0x18000de9d  lea     rcx, [rsp+3F0h+var_3A0]; this
0x18000dea2  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x18000dea7  nop
0x18000dea8  mov     rcx, [rsp+3F0h+var_3B8]
0x18000dead  test    rcx, rcx
0x18000deb0  jz      short loc_18000DEBF
0x18000deb2  mov     rax, [rcx]
0x18000deb5  mov     rax, [rax+10h]
0x18000deb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000debe  nop
0x18000debf  mov     rcx, [rsp+3F0h+var_3B0]
0x18000dec4  test    rcx, rcx
0x18000dec7  jz      short loc_18000DED6
0x18000dec9  mov     rax, [rcx]
0x18000decc  mov     rax, [rax+10h]
0x18000ded0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ded5  nop
0x18000ded6  mov     eax, edi
0x18000ded8  mov     rcx, [rbp+2F0h+var_40]
0x18000dedf  xor     rcx, rsp; StackCookie
0x18000dee2  call    __security_check_cookie
0x18000dee7  mov     rbx, [rsp+3F0h+arg_0]
0x18000deef  add     rsp, 3C0h
0x18000def6  pop     r15
0x18000def8  pop     r14
0x18000defa  pop     r13
0x18000defc  pop     r12
  ... truncated ...
```
