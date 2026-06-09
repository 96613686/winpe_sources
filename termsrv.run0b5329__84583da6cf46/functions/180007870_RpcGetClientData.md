# RpcGetClientData

- ea: `0x180007870`
- end: `0x180008045`
- name: `RpcGetClientData`
- size: `2005`
- prototype: `__int64 __fastcall(__int64, unsigned int, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008050`

## callees

- `0x180007870`
- `0x1800092f0`
- `0x18000a210`
- `0x18000f790`
- `0x1800119a0`
- `0x1800127b0`
- `0x180013150`
- `0x180014de0`
- `0x1800321f0`
- `0x1800330c4`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180007ac8`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180007ac8`
- `ntdll!NtQueryInformationProcess` at `0x180007aac`
- `ntdll!NtQueryInformationProcess` at `0x180007aac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007fb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007fcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007fb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007fcc`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180007a6b`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180007a6b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180007fa8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180007fc2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180007fa8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180007fc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007af4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007af4`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180007a47`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180007a47`
- `RPCRT4!RpcRevertToSelf` at `0x180007f1c`
- `RPCRT4!RpcRevertToSelf` at `0x180007f1c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180007a84`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180007a84`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007b90`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007b90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007f0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007f0f`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800078f5`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800078f5`

## string_xrefs

- `0x180007f6f`: `%s with Trace ID 0x%x Completed`
- `0x180007c7b`: `StringCchCopy in RpcGetClientData failed: 0x%x`
- `0x180007963`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x180007b1d`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RpcGetClientData(__int64 a1, unsigned int a2, _QWORD *a3, _DWORD *a4)
{
  struct ITSSession *v7; // rbx
  unsigned int v8; // esi
  RPC_STATUS v9; // eax
  int v10; // edi
  HANDLE v11; // rax
  void *v12; // rsi
  NTSTATUS InformationProcess; // eax
  wchar_t *v14; // rax
  wchar_t *v15; // rax
  const char *v16; // r8
  int v17; // edi
  _DWORD *v18; // rsi
  int v19; // eax
  int v20; // ecx
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // ecx
  int v25; // r14d
  int v26; // eax
  __int64 v27; // rcx
  _BYTE *v28; // rax
  const char *v29; // r8
  int v30; // eax
  bool v31; // sf
  struct CTraceBase *v33; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v34; // [rsp+38h] [rbp-C8h] BYREF
  int TokenHandle; // [rsp+3Ch] [rbp-C4h] BYREF
  struct ITerminal *v36; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v37; // [rsp+48h] [rbp-B8h] BYREF
  struct ITSSession *v38; // [rsp+50h] [rbp-B0h] BYREF
  void **v39; // [rsp+60h] [rbp-A0h] BYREF
  GUID pguid; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v41[2]; // [rsp+78h] [rbp-88h] BYREF
  struct CTraceBase *v42; // [rsp+80h] [rbp-80h] BYREF
  int v43; // [rsp+88h] [rbp-78h]
  const char *v44; // [rsp+90h] [rbp-70h]
  unsigned int Pid[2]; // [rsp+98h] [rbp-68h] BYREF
  int v46; // [rsp+A0h] [rbp-60h]
  unsigned __int16 v47[262]; // [rsp+A4h] [rbp-5Ch] BYREF
  _BYTE ProcessInformation[8]; // [rsp+2B0h] [rbp+1B0h] BYREF
  wchar_t *Str; // [rsp+2B8h] [rbp+1B8h]
  unsigned __int16 v50[264]; // [rsp+3C0h] [rbp+2C0h] BYREF

  v7 = 0;
  v38 = 0;
  v36 = 0;
  v37 = 0;
  TokenHandle = 0;
  v39 = &CTraceBase::`vftable';
  v41[1] = 1;
  v42 = 0;
  if ( !CTraceBase::g_bEnabled )
  {
    CoCreateGuid(&pguid);
    v41[0] = _InterlockedIncrement((volatile signed __int32 *)&CTraceBase::g_NextShortActivityID);
LABEL_13:
    v43 = 0;
    goto LABEL_14;
  }
  if ( (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "Adding trace %p, %d, %s", &v39, 1, "RpcGetClientData");
  v33 = 0;
  if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v33) >= 0 && v33 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(
      2,
      "TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC",
      1);
  CTraceBase::ResetThreadCurrentOperationTrace(0, 0);
  if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v42) < 0 || !v42 )
  {
    CTraceBase::ResetThreadCurrentOperationTrace((struct CTraceBase *)&v39, "RpcGetClientData");
    CTraceBase::GenerateTraceID(&pguid, v41);
    goto LABEL_13;
  }
  (*(void (__fastcall **)(struct CTraceBase *, GUID *))(*(_QWORD *)v42 + 32LL))(v42, &pguid);
  v41[0] = (*(__int64 (__fastcall **)(struct CTraceBase *))(*(_QWORD *)v42 + 24LL))(v42);
  v43 = 1;
LABEL_14:
  v39 = &CRpcCallTrace::`vftable';
  v44 = "RpcGetClientData";
  *(_QWORD *)Pid = -1;
  v46 = 0;
  memset_0(v47, 0, 0x208u);
  if ( v46 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "TRACE RPC %s with Trace ID 0x%x", v44, v41[0]);
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
          StringCchCopyW(v47, 0x104u, v15);
        }
        CloseHandle(v12);
      }
    }
  }
  if ( v46 )
  {
    if ( v10 < 0 )
    {
      if ( (g_DebugTraceComponent & 1) != 0 )
        _DbgPrintMessage(2, "RPC Caller: Unknown");
    }
    else if ( (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(2, "RPC Caller: PID %d, SessID %d, Process Name: <%S>", Pid[1], Pid[0], v47);
    }
  }
  if ( !a3 )
  {
    v16 = "ppClient";
LABEL_36:
    _DbgPrintMessage(8, "Missing paramter %s in %s", v16, "RpcGetClientData");
    v17 = -2147024809;
    goto LABEL_79;
  }
  if ( !a4 )
  {
    v16 = "pOutBuffByteLen";
    goto LABEL_36;
  }
  v18 = LocalAlloc(0x40u, 0x8F8u);
  if ( !v18 )
  {
    v17 = -2147024882;
    goto LABEL_74;
  }
  v19 = RCMRpcPrologueEx(a2, 1u, 1u, &v36, &v38, &TokenHandle);
  v17 = v19;
  v7 = v38;
  if ( v19 < 0 )
  {
    v20 = 1;
    if ( v19 != -2147022646 )
      v20 = 4;
    _DbgPrintMessage(v20, "RCMRpcPrologue failed: 0x%x", v19);
    if ( v17 != -2147022646 || !v7 )
      goto LABEL_73;
    _DbgPrintMessage(1, "getClientData call in non-active state");
    memset_0(v18, 0, 0x8F8u);
    v21 = (*(__int64 (__fastcall **)(struct ITSSession *, unsigned __int16 *))(*(_QWORD *)v7 + 192LL))(v7, v50);
    if ( v21 < 0 )
    {
      _DbgPrintMessage(4, "ptrSession->GetSessionInitialProgram failed: 0x%x", v21);
      goto LABEL_72;
    }
    v22 = StringCchCopyW((unsigned __int16 *)v18 + 334, 0x101u, v50);
    v17 = v22;
    if ( v22 < 0 )
    {
      _DbgPrintMessage(4, "StringCchCopy in RpcGetClientData failed: 0x%x", v22);
LABEL_72:
      v17 = -2147022646;
      goto LABEL_73;
    }
LABEL_67:
    *a3 = v18;
    *a4 = 2296;
    goto LABEL_74;
  }
  v34 = 0;
  v23 = (*(__int64 (__fastcall **)(struct ITSSession *, unsigned int *))(*(_QWORD *)v38 + 88LL))(v38, &v34);
  v17 = v23;
  if ( v23 >= 0 )
  {
    if ( v34 > 0xC || (v24 = 5028, !_bittest(&v24, v34)) || !v36 )
    {
      if ( v34 == -1 )
        v29 = "Invalid";
      else
        v29 = off_1800D4B10[v34];
      _DbgPrintMessage(8, "getClientData call in invalid state %s", v29);
      goto LABEL_72;
    }
    v17 = (**(__int64 (__fastcall ***)(struct ITerminal *, __int64 *, __int64 *))v36)(v36, qword_1800D7370, &v37);
    if ( v17 < 0 )
    {
      v33 = 0;
      if ( v36 )
      {
        v25 = (**(__int64 (__fastcall ***)(struct ITerminal *, __int64 *, struct CTraceBase **))v36)(
                v36,
                qword_1800D7370,
                &v33);
        if ( v33 )
          (*(void (__fastcall **)(struct CTraceBase *))(*(_QWORD *)v33 + 16LL))(v33);
        if ( v25 >= 0 )
        {
          _DbgPrintMessage(8, "Invalid terminal");
          goto LABEL_73;
        }
      }
      else
      {
        SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v33);
      }
      memset_0(v18, 0, 0x8F8u);
      *v18 = 196;
      *((_BYTE *)v18 + 1188) = 3;
      *(_DWORD *)((char *)v18 + 1258) = 31457920;
      *((_WORD *)v18 + 631) = 2;
      *((_OWORD *)v18 + 128) = TS_INVALID_TZ;
      *((_OWORD *)v18 + 129) = xmmword_1800D9FA0;
      *((_OWORD *)v18 + 130) = xmmword_1800D9FB0;
      *((_OWORD *)v18 + 131) = xmmword_1800D9FC0;
      *((_OWORD *)v18 + 132) = xmmword_1800D9FD0;
      *((_OWORD *)v18 + 133) = xmmword_1800D9FE0;
      *((_OWORD *)v18 + 134) = xmmword_1800D9FF0;
      *((_OWORD *)v18 + 135) = xmmword_1800DA000;
      *((_OWORD *)v18 + 136) = xmmword_1800DA010;
      *((_OWORD *)v18 + 137) = xmmword_1800DA020;
      *(_OWORD *)(v18 + 551) = *(__int128 *)((char *)&xmmword_1800DA020 + 12);
      v17 = 0;
      *a3 = v18;
      *a4 = 2296;
      goto LABEL_74;
    }
    v26 = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)v37 + 232LL))(v37, v18, 2296);
    v17 = v26;
    if ( v26 >= 0 )
    {
      v27 = 30;
      v28 = v18 + 31;
      do
      {
        *v28++ = 0;
        --v27;
      }
      while ( v27 );
      goto LABEL_67;
    }
    _DbgPrintMessage(8, "Session->GetClientData failed: 0x%x in %s", v26, "RpcGetClientData");
  }
  else
  {
    _DbgPrintMessage(8, "getState failed: 0x%x in %s", v23, "RpcGetClientData");
  }
LABEL_73:
  LocalFree(v18);
LABEL_74:
  if ( TokenHandle )
  {
    v30 = RpcRevertToSelf();
    v31 = v30 < 0;
    if ( v30 > 0 )
    {
      v30 = (unsigned __int16)v30 | 0x80070000;
      v31 = v30 < 0;
    }
    if ( v31 )
    {
      _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v30);
      v17 = -2147024891;
    }
  }
LABEL_79:
  v39 = &CRpcCallTrace::`vftable';
  if ( v46 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "%s with Trace ID 0x%x Completed", v44, v41[0]);
  v39 = &CTraceBase::`vftable';
  if ( !v43 && CTraceBase::g_bEnabled && CTraceBase::g_TLSIndex != -1 )
  {
    if ( TlsSetValue(CTraceBase::g_TLSIndex, 0) )
    {
      if ( TlsSetValue(CTraceBase::g_CreatorFunctionTLSIndex, 0) )
        goto LABEL_89;
    }
    else
    {
      GetLastError();
    }
    GetLastError();
  }
LABEL_89:
  v42 = 0;
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  if ( v36 )
    (*(void (__fastcall **)(struct ITerminal *))(*(_QWORD *)v36 + 16LL))(v36);
  if ( v7 )
    (*(void (__fastcall **)(struct ITSSession *))(*(_QWORD *)v7 + 16LL))(v7);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180007870  mov     [rsp-8+arg_0], rbx
0x180007875  push    rbp
0x180007876  push    rsi
0x180007877  push    rdi
0x180007878  push    r12
0x18000787a  push    r13
0x18000787c  push    r14
0x18000787e  push    r15
0x180007880  lea     rbp, [rsp-4E0h]
0x180007888  sub     rsp, 5E0h
0x18000788f  mov     rax, cs:__security_cookie
0x180007896  xor     rax, rsp
0x180007899  mov     [rbp+510h+var_40], rax
0x1800078a0  mov     r12, r9
0x1800078a3  mov     r15, r8
0x1800078a6  mov     r14d, edx
0x1800078a9  xor     r13d, r13d
0x1800078ac  mov     ebx, r13d
0x1800078af  mov     [rsp+610h+var_5C0], rbx
0x1800078b4  mov     [rsp+610h+var_5D0], r13
0x1800078b9  mov     [rsp+610h+var_5C8], r13
0x1800078be  mov     [rsp+610h+var_5D4], r13d
0x1800078c3  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x1800078ca  mov     [rsp+610h+var_5B0], rax
0x1800078cf  mov     [rsp+610h+var_594], 1
0x1800078d7  mov     [rbp+510h+var_590], r13
0x1800078db  lea     rdi, aRpcgetclientda_0; "RpcGetClientData"
0x1800078e2  mov     esi, 2
0x1800078e7  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r13d; int CTraceBase::g_bEnabled
0x1800078ee  jnz     short loc_180007913
0x1800078f0  lea     rcx, [rsp+610h+pguid]; pguid
0x1800078f5  call    cs:__imp_CoCreateGuid
0x1800078fb  mov     eax, 1
0x180007900  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x180007908  inc     eax
0x18000790a  mov     [rsp+610h+var_598], eax
0x18000790e  jmp     loc_1800079DA
0x180007913  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000791a  jz      short loc_18000793A
0x18000791c  mov     [rsp+610h+ReturnLength], rdi
0x180007921  mov     r9d, 1
0x180007927  lea     r8, [rsp+610h+var_5B0]
0x18000792c  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x180007933  mov     ecx, esi; int
0x180007935  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000793a  mov     [rsp+610h+var_5E0], r13
0x18000793f  lea     rcx, [rsp+610h+var_5E0]; struct CTraceBase **
0x180007944  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x180007949  test    eax, eax
0x18000794b  js      short loc_180007971
0x18000794d  cmp     [rsp+610h+var_5E0], rbx
0x180007952  jz      short loc_180007971
0x180007954  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000795b  jz      short loc_180007971
0x18000795d  mov     r8d, 1
0x180007963  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x18000796a  mov     ecx, esi; int
0x18000796c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007971  xor     edx, edx; char *
0x180007973  xor     ecx, ecx; lpTlsValue
0x180007975  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000797a  lea     rcx, [rbp+510h+var_590]; struct CTraceBase **
0x18000797e  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x180007983  test    eax, eax
0x180007985  js      short loc_1800079BE
0x180007987  mov     rcx, [rbp+510h+var_590]
0x18000798b  test    rcx, rcx
0x18000798e  jz      short loc_1800079BE
0x180007990  mov     rax, [rcx]
0x180007993  lea     rdx, [rsp+610h+pguid]
0x180007998  mov     rax, [rax+20h]
0x18000799c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079a1  mov     rcx, [rbp+510h+var_590]
0x1800079a5  mov     rax, [rcx]
0x1800079a8  mov     rax, [rax+18h]
0x1800079ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079b1  mov     [rsp+610h+var_598], eax
0x1800079b5  mov     [rbp+510h+var_588], 1
0x1800079bc  jmp     short loc_1800079DE
0x1800079be  mov     rdx, rdi; char *
0x1800079c1  lea     rcx, [rsp+610h+var_5B0]; lpTlsValue
0x1800079c6  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x1800079cb  lea     rdx, [rsp+610h+var_598]; unsigned int *
0x1800079d0  lea     rcx, [rsp+610h+pguid]; struct _GUID *
0x1800079d5  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x1800079da  mov     [rbp+510h+var_588], r13d
0x1800079de  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x1800079e5  mov     [rsp+610h+var_5B0], rax
0x1800079ea  mov     [rbp+510h+var_580], rdi
0x1800079ee  mov     qword ptr [rbp+510h+Pid], 0FFFFFFFFFFFFFFFFh
0x1800079f6  mov     [rbp+510h+var_570], r13d
0x1800079fa  xor     edx, edx; Val
0x1800079fc  mov     r8d, 208h; Size
0x180007a02  lea     rcx, [rbp+510h+var_56C]; void *
0x180007a06  call    memset_0
0x180007a0b  cmp     [rbp+510h+var_570], ebx
0x180007a0e  jz      short loc_180007A30
0x180007a10  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180007a17  jz      short loc_180007A30
0x180007a19  mov     r9d, [rsp+610h+var_598]
0x180007a1e  mov     r8, [rbp+510h+var_580]
0x180007a22  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x180007a29  mov     ecx, esi; int
0x180007a2b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007a30  mov     esi, cs:?g_DebugTraceComponent@@3KA; ulong g_DebugTraceComponent
0x180007a36  and     esi, 1
0x180007a39  mov     qword ptr [rbp+510h+Pid], 0FFFFFFFFFFFFFFFFh
0x180007a41  lea     rdx, [rbp+510h+Pid+4]; Pid
0x180007a45  xor     ecx, ecx; Binding
0x180007a47  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180007a4d  mov     edi, eax
0x180007a4f  test    eax, eax
0x180007a51  jle     short loc_180007A5C
0x180007a53  movzx   edi, ax
0x180007a56  or      edi, 80070000h
0x180007a5c  test    edi, edi
0x180007a5e  js      loc_180007AFA
0x180007a64  lea     rdx, [rbp+510h+Pid]; pSessionId
0x180007a68  mov     ecx, [rbp+510h+Pid+4]; dwProcessId
0x180007a6b  call    cs:__imp_ProcessIdToSessionId
0x180007a71  test    esi, esi
0x180007a73  jz      loc_180007AFA
0x180007a79  mov     r8d, [rbp+510h+Pid+4]; dwProcessId
0x180007a7d  xor     edx, edx; bInheritHandle
0x180007a7f  mov     ecx, 400h; dwDesiredAccess
0x180007a84  call    cs:__imp_OpenProcess
0x180007a8a  mov     rsi, rax
0x180007a8d  test    rax, rax
0x180007a90  jz      short loc_180007AFA
0x180007a92  mov     [rsp+610h+ReturnLength], r13; ReturnLength
0x180007a97  mov     r9d, 110h; ProcessInformationLength
0x180007a9d  lea     r8, [rbp+510h+ProcessInformation]; ProcessInformation
0x180007aa4  mov     edx, 1Bh; ProcessInformationClass
0x180007aa9  mov     rcx, rax; ProcessHandle
0x180007aac  call    cs:__imp_NtQueryInformationProcess
0x180007ab2  mov     edi, eax
0x180007ab4  or      edi, 10000000h
0x180007aba  jl      short loc_180007AF1
0x180007abc  mov     edx, 5Ch ; '\'; Ch
0x180007ac1  mov     rcx, [rbp+510h+Str]; Str
0x180007ac8  call    cs:__imp_wcsrchr
0x180007ace  test    rax, rax
0x180007ad1  jnz     short loc_180007ADC
0x180007ad3  mov     rax, [rbp+510h+Str]
0x180007ada  jmp     short loc_180007AE0
0x180007adc  add     rax, 2
0x180007ae0  mov     r8, rax; unsigned __int16 *
0x180007ae3  mov     edx, 104h; unsigned __int64
0x180007ae8  lea     rcx, [rbp+510h+var_56C]; unsigned __int16 *
0x180007aec  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007af1  mov     rcx, rsi; hObject
0x180007af4  call    cs:__imp_CloseHandle
0x180007afa  cmp     [rbp+510h+var_570], ebx
0x180007afd  jz      short loc_180007B4A
0x180007aff  test    edi, edi
0x180007b01  js      short loc_180007B30
0x180007b03  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180007b0a  jz      short loc_180007B4A
0x180007b0c  lea     rax, [rbp+510h+var_56C]
0x180007b10  mov     [rsp+610h+ReturnLength], rax
0x180007b15  mov     r9d, [rbp+510h+Pid]
0x180007b19  mov     r8d, [rbp+510h+Pid+4]
0x180007b1d  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x180007b24  mov     ecx, 2; int
0x180007b29  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007b2e  jmp     short loc_180007B4A
0x180007b30  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180007b37  jz      short loc_180007B4A
0x180007b39  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x180007b40  mov     ecx, 2; int
0x180007b45  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007b4a  test    r15, r15
0x180007b4d  jnz     short loc_180007B78
0x180007b4f  lea     r8, aPpclient; "ppClient"
0x180007b56  lea     r9, aRpcgetclientda_0; "RpcGetClientData"
0x180007b5d  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180007b64  mov     ecx, 8; int
0x180007b69  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007b6e  mov     edi, 80070057h
0x180007b73  jmp     loc_180007F4B
0x180007b78  test    r12, r12
0x180007b7b  jnz     short loc_180007B86
0x180007b7d  lea     r8, aPoutbuffbytele; "pOutBuffByteLen"
0x180007b84  jmp     short loc_180007B56
0x180007b86  mov     edx, 8F8h; uBytes
0x180007b8b  mov     ecx, 40h ; '@'; uFlags
0x180007b90  call    cs:__imp_LocalAlloc
0x180007b96  mov     rsi, rax
0x180007b99  test    rax, rax
0x180007b9c  jnz     short loc_180007BA8
0x180007b9e  mov     edi, 8007000Eh
0x180007ba3  jmp     loc_180007F15
0x180007ba8  lea     rax, [rsp+610h+var_5D4]
0x180007bad  mov     [rsp+610h+TokenHandle], rax; TokenHandle
0x180007bb2  lea     rax, [rsp+610h+var_5C0]
0x180007bb7  mov     [rsp+610h+ReturnLength], rax; struct ITSSession **
0x180007bbc  lea     r9, [rsp+610h+var_5D0]; struct ITerminal **
0x180007bc1  mov     edx, 1; unsigned int
0x180007bc6  mov     r8d, edx; int
0x180007bc9  mov     ecx, r14d; unsigned int
0x180007bcc  call    ?RCMRpcPrologueEx@@YAJKKHPEAPEAUITerminal@@PEAPEAUITSSession@@PEAH@Z; RCMRpcPrologueEx(ulong,ulong,int,ITerminal * *,ITSSession * *,int *)
0x180007bd1  mov     edi, eax
0x180007bd3  mov     rbx, [rsp+610h+var_5C0]
0x180007bd8  test    eax, eax
0x180007bda  jns     loc_180007CA6
0x180007be0  mov     ecx, 1
0x180007be5  mov     r14d, 4
0x180007beb  cmp     eax, 800708CAh
0x180007bf0  cmovnz  ecx, r14d; int
0x180007bf4  mov     r8d, eax
0x180007bf7  lea     rdx, aRcmrpcprologue; "RCMRpcPrologue failed: 0x%x"
0x180007bfe  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007c03  cmp     edi, 800708CAh
0x180007c09  jnz     loc_180007F0C
0x180007c0f  test    rbx, rbx
0x180007c12  jz      loc_180007F0C
0x180007c18  lea     rdx, aGetclientdataC; "getClientData call in non-active state"
0x180007c1f  mov     ecx, 1; int
0x180007c24  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007c29  xor     edx, edx; Val
0x180007c2b  mov     r8d, 8F8h; Size
0x180007c31  mov     rcx, rsi; void *
0x180007c34  call    memset_0
0x180007c39  mov     rax, [rbx]
0x180007c3c  lea     rdx, [rbp+510h+var_250]
0x180007c43  mov     rcx, rbx
0x180007c46  mov     rax, [rax+0C0h]
0x180007c4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c52  test    eax, eax
0x180007c54  js      short loc_180007C8F
0x180007c56  lea     rcx, [rsi+29Ch]; unsigned __int16 *
0x180007c5d  lea     r8, [rbp+510h+var_250]; unsigned __int16 *
0x180007c64  mov     edx, 101h; unsigned __int64
0x180007c69  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007c6e  mov     edi, eax
0x180007c70  test    eax, eax
0x180007c72  jns     loc_180007ED0
0x180007c78  mov     r8d, eax
0x180007c7b  lea     rdx, aStringcchcopyI; "StringCchCopy in RpcGetClientData faile"...
0x180007c82  mov     ecx, r14d; int
0x180007c85  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007c8a  jmp     loc_180007F07
0x180007c8f  mov     r8d, eax
0x180007c92  lea     rdx, aPtrsessionGets_1; "ptrSession->GetSessionInitialProgram fa"...
0x180007c99  mov     ecx, r14d; int
0x180007c9c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007ca1  jmp     loc_180007F07
0x180007ca6  mov     [rsp+610h+var_5D8], r13d
0x180007cab  mov     rax, [rbx]
0x180007cae  lea     rdx, [rsp+610h+var_5D8]
0x180007cb3  mov     rcx, rbx
0x180007cb6  mov     rax, [rax+58h]
0x180007cba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cbf  mov     edi, eax
0x180007cc1  test    eax, eax
0x180007cc3  jns     short loc_180007CE5
0x180007cc5  lea     r9, aRpcgetclientda_0; "RpcGetClientData"
0x180007ccc  mov     r8d, eax
0x180007ccf  lea     rdx, aGetstateFailed; "getState failed: 0x%x in %s"
0x180007cd6  mov     ecx, 8; int
0x180007cdb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007ce0  jmp     loc_180007F0C
0x180007ce5  movsxd  rax, [rsp+610h+var_5D8]
0x180007cea  cmp     eax, 0Ch
0x180007ced  ja      loc_180007EDD
0x180007cf3  mov     ecx, 13A4h
0x180007cf8  bt      ecx, eax
0x180007cfb  jnb     loc_180007EDD
0x180007d01  mov     rcx, [rsp+610h+var_5D0]
0x180007d06  test    rcx, rcx
0x180007d09  jz      loc_180007EDD
0x180007d0f  mov     rax, [rcx]
0x180007d12  lea     r8, [rsp+610h+var_5C8]
0x180007d17  lea     rdx, qword_1800D7370
0x180007d1e  mov     rax, [rax]
0x180007d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d26  mov     edi, eax
0x180007d28  test    eax, eax
0x180007d2a  jns     loc_180007E7A
0x180007d30  mov     rcx, [rsp+610h+var_5D0]
0x180007d35  mov     [rsp+610h+var_5E0], r13
0x180007d3a  test    rcx, rcx
0x180007d3d  jnz     loc_180007E2A
0x180007d43  lea     rcx, [rsp+610h+var_5E0]; void *
0x180007d48  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180007d4d  xor     edx, edx; Val
0x180007d4f  mov     r8d, 8F8h; Size
0x180007d55  mov     rcx, rsi; void *
0x180007d58  call    memset_0
0x180007d5d  mov     dword ptr [rsi], 0C4h
0x180007d63  mov     byte ptr [rsi+4A4h], 3
0x180007d6a  mov     dword ptr [rsi+4EAh], 1E00280h
0x180007d74  mov     word ptr [rsi+4EEh], 2
0x180007d7d  movaps  xmm0, cs:TS_INVALID_TZ
0x180007d84  movups  xmmword ptr [rsi+800h], xmm0
0x180007d8b  movaps  xmm1, cs:xmmword_1800D9FA0
0x180007d92  movups  xmmword ptr [rsi+810h], xmm1
0x180007d99  movaps  xmm0, cs:xmmword_1800D9FB0
0x180007da0  movups  xmmword ptr [rsi+820h], xmm0
0x180007da7  movaps  xmm1, cs:xmmword_1800D9FC0
  ... truncated ...
```
