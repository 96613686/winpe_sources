# RpcCloseListener

- ea: `0x18000f120`
- end: `0x18000f500`
- name: `RpcCloseListener`
- size: `992`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005ffa0`
- `0x18005ffc0`

## callees

- `0x180009940`
- `0x18000f120`
- `0x18000faf0`
- `0x180012070`
- `0x180012d10`
- `0x1800154a0`
- `0x180033f60`
- `0x180034e64`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000f379`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000f379`
- `ntdll!NtQueryInformationProcess` at `0x18000f357`
- `ntdll!NtQueryInformationProcess` at `0x18000f357`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4cd`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000f309`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000f309`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000f497`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000f4bd`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000f497`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000f4bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f3ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f3ab`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000f2dd`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000f2dd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000f329`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000f329`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000f182`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000f182`

## string_xrefs

- `0x18000f464`: `%s with Trace ID 0x%x Completed`
- `0x18000f1ec`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18000f3dd`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

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
0x18000f120  push    rbp
0x18000f122  push    rbx
0x18000f123  push    rsi
0x18000f124  push    rdi
0x18000f125  push    r12
0x18000f127  push    r13
0x18000f129  push    r14
0x18000f12b  push    r15
0x18000f12d  lea     rbp, [rsp-2B8h]
0x18000f135  sub     rsp, 3B8h
0x18000f13c  mov     rax, cs:__security_cookie
0x18000f143  xor     rax, rsp
0x18000f146  mov     [rbp+2F0h+var_50], rax
0x18000f14d  mov     rdi, rcx
0x18000f150  lea     r15, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000f157  mov     [rsp+3F0h+var_3B0], r15
0x18000f15c  mov     ebx, 1
0x18000f161  mov     [rsp+3F0h+var_394], ebx
0x18000f165  xor     r14d, r14d
0x18000f168  mov     [rsp+3F0h+var_390], r14
0x18000f16d  lea     r13, aRpccloselisten; "RpcCloseListener"
0x18000f174  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r14d; int CTraceBase::g_bEnabled
0x18000f17b  jnz     short loc_18000F1A1
0x18000f17d  lea     rcx, [rsp+3F0h+pguid]; pguid
0x18000f182  call    cs:__imp_CoCreateGuid
0x18000f189  nop     dword ptr [rax+rax+00h]
0x18000f18e  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, ebx; ulong CTraceBase::g_NextShortActivityID
0x18000f196  inc     ebx
0x18000f198  mov     [rsp+3F0h+var_398], ebx
0x18000f19c  jmp     loc_18000F266
0x18000f1a1  test    byte ptr cs:?g_DebugTraceComponent@@3KA, bl; ulong g_DebugTraceComponent
0x18000f1a7  jz      short loc_18000F1C7
0x18000f1a9  mov     [rsp+3F0h+ReturnLength], r13
0x18000f1ae  mov     r9d, ebx
0x18000f1b1  lea     r8, [rsp+3F0h+var_3B0]
0x18000f1b6  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x18000f1bd  mov     ecx, 2; int
0x18000f1c2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f1c7  mov     [rsp+3F0h+var_3C0], r14
0x18000f1cc  lea     rcx, [rsp+3F0h+var_3C0]; struct CTraceBase **
0x18000f1d1  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000f1d6  test    eax, eax
0x18000f1d8  js      short loc_18000F1FD
0x18000f1da  cmp     [rsp+3F0h+var_3C0], r14
0x18000f1df  jz      short loc_18000F1FD
0x18000f1e1  test    byte ptr cs:?g_DebugTraceComponent@@3KA, bl; ulong g_DebugTraceComponent
0x18000f1e7  jz      short loc_18000F1FD
0x18000f1e9  mov     r8d, ebx
0x18000f1ec  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x18000f1f3  mov     ecx, 2; int
0x18000f1f8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f1fd  xor     edx, edx; char *
0x18000f1ff  xor     ecx, ecx; lpTlsValue
0x18000f201  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000f206  lea     rcx, [rsp+3F0h+var_390]; struct CTraceBase **
0x18000f20b  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000f210  test    eax, eax
0x18000f212  js      short loc_18000F24A
0x18000f214  mov     rcx, [rsp+3F0h+var_390]
0x18000f219  test    rcx, rcx
0x18000f21c  jz      short loc_18000F24A
0x18000f21e  mov     rax, [rcx]
0x18000f221  lea     rdx, [rsp+3F0h+pguid]
0x18000f226  mov     rax, [rax+20h]
0x18000f22a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f22f  mov     rcx, [rsp+3F0h+var_390]
0x18000f234  mov     rax, [rcx]
0x18000f237  mov     rax, [rax+18h]
0x18000f23b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f240  mov     [rsp+3F0h+var_398], eax
0x18000f244  mov     [rsp+3F0h+var_388], ebx
0x18000f248  jmp     short loc_18000F26B
0x18000f24a  mov     rdx, r13; char *
0x18000f24d  lea     rcx, [rsp+3F0h+var_3B0]; lpTlsValue
0x18000f252  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000f257  lea     rdx, [rsp+3F0h+var_398]; unsigned int *
0x18000f25c  lea     rcx, [rsp+3F0h+pguid]; struct _GUID *
0x18000f261  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x18000f266  mov     [rsp+3F0h+var_388], r14d
0x18000f26b  lea     r12, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000f272  mov     [rsp+3F0h+var_3B0], r12
0x18000f277  mov     [rsp+3F0h+var_380], r13
0x18000f27c  mov     qword ptr [rsp+3F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000f285  mov     [rbp+2F0h+var_370], r14d
0x18000f289  xor     edx, edx; Val
0x18000f28b  mov     r8d, 208h; Size
0x18000f291  lea     rcx, [rbp+2F0h+var_36C]; void *
0x18000f295  call    memset_0
0x18000f29a  cmp     [rbp+2F0h+var_370], r14d
0x18000f29e  jz      short loc_18000F2C4
0x18000f2a0  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000f2a7  jz      short loc_18000F2C4
0x18000f2a9  mov     r9d, [rsp+3F0h+var_398]
0x18000f2ae  mov     r8, [rsp+3F0h+var_380]
0x18000f2b3  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x18000f2ba  mov     ecx, 2; int
0x18000f2bf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f2c4  mov     esi, cs:?g_DebugTraceComponent@@3KA; ulong g_DebugTraceComponent
0x18000f2ca  and     esi, 1
0x18000f2cd  mov     qword ptr [rsp+3F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000f2d6  lea     rdx, [rsp+3F0h+Pid+4]; Pid
0x18000f2db  xor     ecx, ecx; Binding
0x18000f2dd  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000f2e4  nop     dword ptr [rax+rax+00h]
0x18000f2e9  mov     ebx, eax
0x18000f2eb  test    eax, eax
0x18000f2ed  jle     short loc_18000F2F8
0x18000f2ef  movzx   ebx, ax
0x18000f2f2  or      ebx, 80070000h
0x18000f2f8  test    ebx, ebx
0x18000f2fa  js      loc_18000F3B7
0x18000f300  lea     rdx, [rsp+3F0h+Pid]; pSessionId
0x18000f305  mov     ecx, [rsp+3F0h+Pid+4]; dwProcessId
0x18000f309  call    cs:__imp_ProcessIdToSessionId
0x18000f310  nop     dword ptr [rax+rax+00h]
0x18000f315  test    esi, esi
0x18000f317  jz      loc_18000F3B7
0x18000f31d  mov     r8d, [rsp+3F0h+Pid+4]; dwProcessId
0x18000f322  xor     edx, edx; bInheritHandle
0x18000f324  mov     ecx, 400h; dwDesiredAccess
0x18000f329  call    cs:__imp_OpenProcess
0x18000f330  nop     dword ptr [rax+rax+00h]
0x18000f335  mov     rsi, rax
0x18000f338  test    rax, rax
0x18000f33b  jz      short loc_18000F3B7
0x18000f33d  mov     [rsp+3F0h+ReturnLength], r14; ReturnLength
0x18000f342  mov     r9d, 110h; ProcessInformationLength
0x18000f348  lea     r8, [rbp+2F0h+ProcessInformation]; ProcessInformation
0x18000f34f  mov     edx, 1Bh; ProcessInformationClass
0x18000f354  mov     rcx, rax; ProcessHandle
0x18000f357  call    cs:__imp_NtQueryInformationProcess
0x18000f35e  nop     dword ptr [rax+rax+00h]
0x18000f363  mov     ebx, eax
0x18000f365  or      ebx, 10000000h
0x18000f36b  jl      short loc_18000F3A8
0x18000f36d  mov     edx, 5Ch ; '\'; Ch
0x18000f372  mov     rcx, [rbp+2F0h+Str]; Str
0x18000f379  call    cs:__imp_wcsrchr
0x18000f380  nop     dword ptr [rax+rax+00h]
0x18000f385  test    rax, rax
0x18000f388  jnz     short loc_18000F393
0x18000f38a  mov     rax, [rbp+2F0h+Str]
0x18000f391  jmp     short loc_18000F397
0x18000f393  add     rax, 2
0x18000f397  mov     r8, rax; unsigned __int16 *
0x18000f39a  mov     edx, 104h; unsigned __int64
0x18000f39f  lea     rcx, [rbp+2F0h+var_36C]; unsigned __int16 *
0x18000f3a3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f3a8  mov     rcx, rsi; hObject
0x18000f3ab  call    cs:__imp_CloseHandle
0x18000f3b2  nop     dword ptr [rax+rax+00h]
0x18000f3b7  cmp     [rbp+2F0h+var_370], r14d
0x18000f3bb  jz      short loc_18000F40A
0x18000f3bd  test    ebx, ebx
0x18000f3bf  js      short loc_18000F3F0
0x18000f3c1  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000f3c8  jz      short loc_18000F40A
0x18000f3ca  lea     rax, [rbp+2F0h+var_36C]
0x18000f3ce  mov     [rsp+3F0h+ReturnLength], rax
0x18000f3d3  mov     r9d, [rsp+3F0h+Pid]
0x18000f3d8  mov     r8d, [rsp+3F0h+Pid+4]
0x18000f3dd  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x18000f3e4  mov     ecx, 2; int
0x18000f3e9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f3ee  jmp     short loc_18000F40A
0x18000f3f0  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000f3f7  jz      short loc_18000F40A
0x18000f3f9  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x18000f400  mov     ecx, 2; int
0x18000f405  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f40a  test    rdi, rdi
0x18000f40d  jnz     short loc_18000F431
0x18000f40f  mov     r9, r13
0x18000f412  lea     r8, aPhlistener; "phListener"
0x18000f419  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18000f420  mov     ecx, 8; int
0x18000f425  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f42a  mov     ebx, 80070057h
0x18000f42f  jmp     short loc_18000F446
0x18000f431  mov     rcx, [rdi]
0x18000f434  mov     rax, [rcx]
0x18000f437  mov     rax, [rax+10h]
0x18000f43b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f440  mov     [rdi], r14
0x18000f443  mov     ebx, r14d
0x18000f446  mov     [rsp+3F0h+var_3B0], r12
0x18000f44b  cmp     [rbp+2F0h+var_370], 0
0x18000f44f  jz      short loc_18000F475
0x18000f451  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000f458  jz      short loc_18000F475
0x18000f45a  mov     r9d, [rsp+3F0h+var_398]
0x18000f45f  mov     r8, [rsp+3F0h+var_380]
0x18000f464  lea     rdx, aSWithTraceId0x; "%s with Trace ID 0x%x Completed"
0x18000f46b  mov     ecx, 2; int
0x18000f470  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f475  mov     [rsp+3F0h+var_3B0], r15
0x18000f47a  cmp     cs:?g_bEnabled@CTraceBase@@0HA, 0; int CTraceBase::g_bEnabled
0x18000f481  jz      short loc_18000F4DA
0x18000f483  cmp     [rsp+3F0h+var_388], 0
0x18000f488  jnz     short loc_18000F4DA
0x18000f48a  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x18000f490  cmp     ecx, 0FFFFFFFFh
0x18000f493  jz      short loc_18000F4DA
0x18000f495  xor     edx, edx; lpTlsValue
0x18000f497  call    cs:__imp_TlsSetValue
0x18000f49e  nop     dword ptr [rax+rax+00h]
0x18000f4a3  test    eax, eax
0x18000f4a5  jnz     short loc_18000F4B5
0x18000f4a7  call    cs:__imp_GetLastError
0x18000f4ae  nop     dword ptr [rax+rax+00h]
0x18000f4b3  jmp     short loc_18000F4CD
0x18000f4b5  xor     edx, edx; lpTlsValue
0x18000f4b7  mov     ecx, cs:?g_CreatorFunctionTLSIndex@CTraceBase@@0KA; dwTlsIndex
0x18000f4bd  call    cs:__imp_TlsSetValue
0x18000f4c4  nop     dword ptr [rax+rax+00h]
0x18000f4c9  test    eax, eax
0x18000f4cb  jnz     short loc_18000F4DA
0x18000f4cd  call    cs:__imp_GetLastError
0x18000f4d4  nop     dword ptr [rax+rax+00h]
0x18000f4d9  nop
0x18000f4da  mov     eax, ebx
0x18000f4dc  mov     rcx, [rbp+2F0h+var_50]
0x18000f4e3  xor     rcx, rsp; StackCookie
0x18000f4e6  call    __security_check_cookie
0x18000f4eb  add     rsp, 3B8h
0x18000f4f2  pop     r15
0x18000f4f4  pop     r14
0x18000f4f6  pop     r13
0x18000f4f8  pop     r12
0x18000f4fa  pop     rdi
0x18000f4fb  pop     rsi
0x18000f4fc  pop     rbx
0x18000f4fd  pop     rbp
0x18000f4fe  retn
```
