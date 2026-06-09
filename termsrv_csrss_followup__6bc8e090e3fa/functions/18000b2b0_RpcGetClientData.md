# RpcGetClientData

- ea: `0x18000b2b0`
- end: `0x18000ba42`
- name: `RpcGetClientData`
- size: `1938`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000ac50`

## callees

- `0x180008920`
- `0x180009940`
- `0x18000b2b0`
- `0x18000f760`
- `0x18000faf0`
- `0x180012070`
- `0x180012d10`
- `0x1800139c0`
- `0x1800154a0`
- `0x180033f60`
- `0x180034e64`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000b526`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000b526`
- `ntdll!NtQueryInformationProcess` at `0x18000b504`
- `ntdll!NtQueryInformationProcess` at `0x18000b504`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000b4b7`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000b4b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b558`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b558`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000b48d`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000b48d`
- `RPCRT4!RpcRevertToSelf` at `0x18000b992`
- `RPCRT4!RpcRevertToSelf` at `0x18000b992`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000b4d6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000b4d6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b5fa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b5fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b97f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b97f`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000b335`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000b335`

## string_xrefs

- `0x18000b6eb`: `StringCchCopy in RpcGetClientData failed: 0x%x`
- `0x18000b3a9`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18000b587`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

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
        v29 = off_1800DAB50[v34];
      _DbgPrintMessage(8, "getClientData call in invalid state %s", v29);
      goto LABEL_72;
    }
    v17 = (**(__int64 (__fastcall ***)(struct ITerminal *, __int64 *, __int64 *))v36)(v36, qword_1800DD390, &v37);
    if ( v17 < 0 )
    {
      v33 = 0;
      if ( v36 )
      {
        v25 = (**(__int64 (__fastcall ***)(struct ITerminal *, __int64 *, struct CTraceBase **))v36)(
                v36,
                qword_1800DD390,
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
      *((_OWORD *)v18 + 129) = xmmword_1800DFFF0;
      *((_OWORD *)v18 + 130) = xmmword_1800E0000;
      *((_OWORD *)v18 + 131) = xmmword_1800E0010;
      *((_OWORD *)v18 + 132) = xmmword_1800E0020;
      *((_OWORD *)v18 + 133) = xmmword_1800E0030;
      *((_OWORD *)v18 + 134) = xmmword_1800E0040;
      *((_OWORD *)v18 + 135) = xmmword_1800E0050;
      *((_OWORD *)v18 + 136) = xmmword_1800E0060;
      *((_OWORD *)v18 + 137) = xmmword_1800E0070;
      *(_OWORD *)(v18 + 551) = *(__int128 *)((char *)&xmmword_1800E0070 + 12);
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
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)&v39);
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
0x18000b2b0  mov     [rsp-8+arg_0], rbx
0x18000b2b5  push    rbp
0x18000b2b6  push    rsi
0x18000b2b7  push    rdi
0x18000b2b8  push    r12
0x18000b2ba  push    r13
0x18000b2bc  push    r14
0x18000b2be  push    r15
0x18000b2c0  lea     rbp, [rsp-4E0h]
0x18000b2c8  sub     rsp, 5E0h
0x18000b2cf  mov     rax, cs:__security_cookie
0x18000b2d6  xor     rax, rsp
0x18000b2d9  mov     [rbp+510h+var_40], rax
0x18000b2e0  mov     r12, r9
0x18000b2e3  mov     r15, r8
0x18000b2e6  mov     r14d, edx
0x18000b2e9  xor     r13d, r13d
0x18000b2ec  mov     ebx, r13d
0x18000b2ef  mov     [rsp+610h+var_5C0], rbx
0x18000b2f4  mov     [rsp+610h+var_5D0], r13
0x18000b2f9  mov     [rsp+610h+var_5C8], r13
0x18000b2fe  mov     [rsp+610h+var_5D4], r13d
0x18000b303  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18000b30a  mov     [rsp+610h+var_5B0], rax
0x18000b30f  mov     [rsp+610h+var_594], 1
0x18000b317  mov     [rbp+510h+var_590], r13
0x18000b31b  lea     rdi, aRpcgetclientda_0; "RpcGetClientData"
0x18000b322  mov     esi, 2
0x18000b327  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r13d; int CTraceBase::g_bEnabled
0x18000b32e  jnz     short loc_18000B359
0x18000b330  lea     rcx, [rsp+610h+pguid]; pguid
0x18000b335  call    cs:__imp_CoCreateGuid
0x18000b33c  nop     dword ptr [rax+rax+00h]
0x18000b341  mov     eax, 1
0x18000b346  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x18000b34e  inc     eax
0x18000b350  mov     [rsp+610h+var_598], eax
0x18000b354  jmp     loc_18000B420
0x18000b359  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000b360  jz      short loc_18000B380
0x18000b362  mov     [rsp+610h+ReturnLength], rdi
0x18000b367  mov     r9d, 1
0x18000b36d  lea     r8, [rsp+610h+var_5B0]
0x18000b372  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x18000b379  mov     ecx, esi; int
0x18000b37b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b380  mov     [rsp+610h+var_5E0], r13
0x18000b385  lea     rcx, [rsp+610h+var_5E0]; struct CTraceBase **
0x18000b38a  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000b38f  test    eax, eax
0x18000b391  js      short loc_18000B3B7
0x18000b393  cmp     [rsp+610h+var_5E0], rbx
0x18000b398  jz      short loc_18000B3B7
0x18000b39a  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000b3a1  jz      short loc_18000B3B7
0x18000b3a3  mov     r8d, 1
0x18000b3a9  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x18000b3b0  mov     ecx, esi; int
0x18000b3b2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b3b7  xor     edx, edx; char *
0x18000b3b9  xor     ecx, ecx; lpTlsValue
0x18000b3bb  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000b3c0  lea     rcx, [rbp+510h+var_590]; struct CTraceBase **
0x18000b3c4  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18000b3c9  test    eax, eax
0x18000b3cb  js      short loc_18000B404
0x18000b3cd  mov     rcx, [rbp+510h+var_590]
0x18000b3d1  test    rcx, rcx
0x18000b3d4  jz      short loc_18000B404
0x18000b3d6  mov     rax, [rcx]
0x18000b3d9  lea     rdx, [rsp+610h+pguid]
0x18000b3de  mov     rax, [rax+20h]
0x18000b3e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3e7  mov     rcx, [rbp+510h+var_590]
0x18000b3eb  mov     rax, [rcx]
0x18000b3ee  mov     rax, [rax+18h]
0x18000b3f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3f7  mov     [rsp+610h+var_598], eax
0x18000b3fb  mov     [rbp+510h+var_588], 1
0x18000b402  jmp     short loc_18000B424
0x18000b404  mov     rdx, rdi; char *
0x18000b407  lea     rcx, [rsp+610h+var_5B0]; lpTlsValue
0x18000b40c  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18000b411  lea     rdx, [rsp+610h+var_598]; unsigned int *
0x18000b416  lea     rcx, [rsp+610h+pguid]; struct _GUID *
0x18000b41b  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x18000b420  mov     [rbp+510h+var_588], r13d
0x18000b424  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000b42b  mov     [rsp+610h+var_5B0], rax
0x18000b430  mov     [rbp+510h+var_580], rdi
0x18000b434  mov     qword ptr [rbp+510h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000b43c  mov     [rbp+510h+var_570], r13d
0x18000b440  xor     edx, edx; Val
0x18000b442  mov     r8d, 208h; Size
0x18000b448  lea     rcx, [rbp+510h+var_56C]; void *
0x18000b44c  call    memset_0
0x18000b451  cmp     [rbp+510h+var_570], ebx
0x18000b454  jz      short loc_18000B476
0x18000b456  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000b45d  jz      short loc_18000B476
0x18000b45f  mov     r9d, [rsp+610h+var_598]
0x18000b464  mov     r8, [rbp+510h+var_580]
0x18000b468  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x18000b46f  mov     ecx, esi; int
0x18000b471  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b476  mov     esi, cs:?g_DebugTraceComponent@@3KA; ulong g_DebugTraceComponent
0x18000b47c  and     esi, 1
0x18000b47f  mov     qword ptr [rbp+510h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000b487  lea     rdx, [rbp+510h+Pid+4]; Pid
0x18000b48b  xor     ecx, ecx; Binding
0x18000b48d  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000b494  nop     dword ptr [rax+rax+00h]
0x18000b499  mov     edi, eax
0x18000b49b  test    eax, eax
0x18000b49d  jle     short loc_18000B4A8
0x18000b49f  movzx   edi, ax
0x18000b4a2  or      edi, 80070000h
0x18000b4a8  test    edi, edi
0x18000b4aa  js      loc_18000B564
0x18000b4b0  lea     rdx, [rbp+510h+Pid]; pSessionId
0x18000b4b4  mov     ecx, [rbp+510h+Pid+4]; dwProcessId
0x18000b4b7  call    cs:__imp_ProcessIdToSessionId
0x18000b4be  nop     dword ptr [rax+rax+00h]
0x18000b4c3  test    esi, esi
0x18000b4c5  jz      loc_18000B564
0x18000b4cb  mov     r8d, [rbp+510h+Pid+4]; dwProcessId
0x18000b4cf  xor     edx, edx; bInheritHandle
0x18000b4d1  mov     ecx, 400h; dwDesiredAccess
0x18000b4d6  call    cs:__imp_OpenProcess
0x18000b4dd  nop     dword ptr [rax+rax+00h]
0x18000b4e2  mov     rsi, rax
0x18000b4e5  test    rax, rax
0x18000b4e8  jz      short loc_18000B564
0x18000b4ea  mov     [rsp+610h+ReturnLength], r13; ReturnLength
0x18000b4ef  mov     r9d, 110h; ProcessInformationLength
0x18000b4f5  lea     r8, [rbp+510h+ProcessInformation]; ProcessInformation
0x18000b4fc  mov     edx, 1Bh; ProcessInformationClass
0x18000b501  mov     rcx, rax; ProcessHandle
0x18000b504  call    cs:__imp_NtQueryInformationProcess
0x18000b50b  nop     dword ptr [rax+rax+00h]
0x18000b510  mov     edi, eax
0x18000b512  or      edi, 10000000h
0x18000b518  jl      short loc_18000B555
0x18000b51a  mov     edx, 5Ch ; '\'; Ch
0x18000b51f  mov     rcx, [rbp+510h+Str]; Str
0x18000b526  call    cs:__imp_wcsrchr
0x18000b52d  nop     dword ptr [rax+rax+00h]
0x18000b532  test    rax, rax
0x18000b535  jnz     short loc_18000B540
0x18000b537  mov     rax, [rbp+510h+Str]
0x18000b53e  jmp     short loc_18000B544
0x18000b540  add     rax, 2
0x18000b544  mov     r8, rax; unsigned __int16 *
0x18000b547  mov     edx, 104h; unsigned __int64
0x18000b54c  lea     rcx, [rbp+510h+var_56C]; unsigned __int16 *
0x18000b550  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b555  mov     rcx, rsi; hObject
0x18000b558  call    cs:__imp_CloseHandle
0x18000b55f  nop     dword ptr [rax+rax+00h]
0x18000b564  cmp     [rbp+510h+var_570], ebx
0x18000b567  jz      short loc_18000B5B4
0x18000b569  test    edi, edi
0x18000b56b  js      short loc_18000B59A
0x18000b56d  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000b574  jz      short loc_18000B5B4
0x18000b576  lea     rax, [rbp+510h+var_56C]
0x18000b57a  mov     [rsp+610h+ReturnLength], rax
0x18000b57f  mov     r9d, [rbp+510h+Pid]
0x18000b583  mov     r8d, [rbp+510h+Pid+4]
0x18000b587  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x18000b58e  mov     ecx, 2; int
0x18000b593  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b598  jmp     short loc_18000B5B4
0x18000b59a  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18000b5a1  jz      short loc_18000B5B4
0x18000b5a3  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x18000b5aa  mov     ecx, 2; int
0x18000b5af  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b5b4  test    r15, r15
0x18000b5b7  jnz     short loc_18000B5E2
0x18000b5b9  lea     r8, aPpclient; "ppClient"
0x18000b5c0  lea     r9, aRpcgetclientda_0; "RpcGetClientData"
0x18000b5c7  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18000b5ce  mov     ecx, 8; int
0x18000b5d3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b5d8  mov     edi, 80070057h
0x18000b5dd  jmp     loc_18000B9C7
0x18000b5e2  test    r12, r12
0x18000b5e5  jnz     short loc_18000B5F0
0x18000b5e7  lea     r8, aPoutbuffbytele; "pOutBuffByteLen"
0x18000b5ee  jmp     short loc_18000B5C0
0x18000b5f0  mov     edx, 8F8h; uBytes
0x18000b5f5  mov     ecx, 40h ; '@'; uFlags
0x18000b5fa  call    cs:__imp_LocalAlloc
0x18000b601  nop     dword ptr [rax+rax+00h]
0x18000b606  mov     rsi, rax
0x18000b609  test    rax, rax
0x18000b60c  jnz     short loc_18000B618
0x18000b60e  mov     edi, 8007000Eh
0x18000b613  jmp     loc_18000B98B
0x18000b618  lea     rax, [rsp+610h+var_5D4]
0x18000b61d  mov     [rsp+610h+TokenHandle], rax; TokenHandle
0x18000b622  lea     rax, [rsp+610h+var_5C0]
0x18000b627  mov     [rsp+610h+ReturnLength], rax; struct ITSSession **
0x18000b62c  lea     r9, [rsp+610h+var_5D0]; struct ITerminal **
0x18000b631  mov     edx, 1; unsigned int
0x18000b636  mov     r8d, edx; int
0x18000b639  mov     ecx, r14d; unsigned int
0x18000b63c  call    ?RCMRpcPrologueEx@@YAJKKHPEAPEAUITerminal@@PEAPEAUITSSession@@PEAH@Z; RCMRpcPrologueEx(ulong,ulong,int,ITerminal * *,ITSSession * *,int *)
0x18000b641  mov     edi, eax
0x18000b643  mov     rbx, [rsp+610h+var_5C0]
0x18000b648  test    eax, eax
0x18000b64a  jns     loc_18000B716
0x18000b650  mov     ecx, 1
0x18000b655  mov     r14d, 4
0x18000b65b  cmp     eax, 800708CAh
0x18000b660  cmovnz  ecx, r14d; int
0x18000b664  mov     r8d, eax
0x18000b667  lea     rdx, aRcmrpcprologue; "RCMRpcPrologue failed: 0x%x"
0x18000b66e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b673  cmp     edi, 800708CAh
0x18000b679  jnz     loc_18000B97C
0x18000b67f  test    rbx, rbx
0x18000b682  jz      loc_18000B97C
0x18000b688  lea     rdx, aGetclientdataC; "getClientData call in non-active state"
0x18000b68f  mov     ecx, 1; int
0x18000b694  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b699  xor     edx, edx; Val
0x18000b69b  mov     r8d, 8F8h; Size
0x18000b6a1  mov     rcx, rsi; void *
0x18000b6a4  call    memset_0
0x18000b6a9  mov     rax, [rbx]
0x18000b6ac  lea     rdx, [rbp+510h+var_250]
0x18000b6b3  mov     rcx, rbx
0x18000b6b6  mov     rax, [rax+0C0h]
0x18000b6bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6c2  test    eax, eax
0x18000b6c4  js      short loc_18000B6FF
0x18000b6c6  lea     rcx, [rsi+29Ch]; unsigned __int16 *
0x18000b6cd  lea     r8, [rbp+510h+var_250]; unsigned __int16 *
0x18000b6d4  mov     edx, 101h; unsigned __int64
0x18000b6d9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b6de  mov     edi, eax
0x18000b6e0  test    eax, eax
0x18000b6e2  jns     loc_18000B940
0x18000b6e8  mov     r8d, eax
0x18000b6eb  lea     rdx, aStringcchcopyI; "StringCchCopy in RpcGetClientData faile"...
0x18000b6f2  mov     ecx, r14d; int
0x18000b6f5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b6fa  jmp     loc_18000B977
0x18000b6ff  mov     r8d, eax
0x18000b702  lea     rdx, aPtrsessionGets_1; "ptrSession->GetSessionInitialProgram fa"...
0x18000b709  mov     ecx, r14d; int
0x18000b70c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b711  jmp     loc_18000B977
0x18000b716  mov     [rsp+610h+var_5D8], r13d
0x18000b71b  mov     rax, [rbx]
0x18000b71e  lea     rdx, [rsp+610h+var_5D8]
0x18000b723  mov     rcx, rbx
0x18000b726  mov     rax, [rax+58h]
0x18000b72a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b72f  mov     edi, eax
0x18000b731  test    eax, eax
0x18000b733  jns     short loc_18000B755
0x18000b735  lea     r9, aRpcgetclientda_0; "RpcGetClientData"
0x18000b73c  mov     r8d, eax
0x18000b73f  lea     rdx, aGetstateFailed; "getState failed: 0x%x in %s"
0x18000b746  mov     ecx, 8; int
0x18000b74b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b750  jmp     loc_18000B97C
0x18000b755  movsxd  rax, [rsp+610h+var_5D8]
0x18000b75a  cmp     eax, 0Ch
0x18000b75d  ja      loc_18000B94D
0x18000b763  mov     ecx, 13A4h
0x18000b768  bt      ecx, eax
0x18000b76b  jnb     loc_18000B94D
0x18000b771  mov     rcx, [rsp+610h+var_5D0]
0x18000b776  test    rcx, rcx
0x18000b779  jz      loc_18000B94D
0x18000b77f  mov     rax, [rcx]
0x18000b782  lea     r8, [rsp+610h+var_5C8]
0x18000b787  lea     rdx, qword_1800DD390
0x18000b78e  mov     rax, [rax]
0x18000b791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b796  mov     edi, eax
0x18000b798  test    eax, eax
0x18000b79a  jns     loc_18000B8EA
0x18000b7a0  mov     rcx, [rsp+610h+var_5D0]
0x18000b7a5  mov     [rsp+610h+var_5E0], r13
0x18000b7aa  test    rcx, rcx
0x18000b7ad  jnz     loc_18000B89A
0x18000b7b3  lea     rcx, [rsp+610h+var_5E0]; void *
0x18000b7b8  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18000b7bd  xor     edx, edx; Val
0x18000b7bf  mov     r8d, 8F8h; Size
0x18000b7c5  mov     rcx, rsi; void *
0x18000b7c8  call    memset_0
0x18000b7cd  mov     dword ptr [rsi], 0C4h
0x18000b7d3  mov     byte ptr [rsi+4A4h], 3
0x18000b7da  mov     dword ptr [rsi+4EAh], 1E00280h
  ... truncated ...
```
