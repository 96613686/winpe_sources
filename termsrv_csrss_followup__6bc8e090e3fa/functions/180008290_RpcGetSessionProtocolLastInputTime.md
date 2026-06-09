# RpcGetSessionProtocolLastInputTime

- ea: `0x180008290`
- end: `0x180008918`
- name: `RpcGetSessionProtocolLastInputTime`
- size: `1672`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008290`
- `0x180008920`
- `0x180009940`
- `0x18000faf0`
- `0x180012070`
- `0x180012d10`
- `0x1800154a0`
- `0x180033f60`
- `0x180034e64`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000879c`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000879c`
- `ntdll!NtQueryInformationProcess` at `0x18000877a`
- `ntdll!NtQueryInformationProcess` at `0x18000877a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000859c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008906`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000859c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008906`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800083a9`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800083a9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180008588`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800088f2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180008588`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800088f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800087ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800087ce`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180008383`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180008383`
- `RPCRT4!RpcRevertToSelf` at `0x180008517`
- `RPCRT4!RpcRevertToSelf` at `0x180008517`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008744`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008744`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800085b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800085b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000855c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000855c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180008319`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180008319`

## string_xrefs

- `0x180008301`: `RpcGetSessionProtocolLastInputTime`
- `0x1800084f5`: `RpcGetSessionProtocolLastInputTime`
- `0x180008622`: `RpcGetSessionProtocolLastInputTime`
- `0x180008857`: `RpcGetSessionProtocolLastInputTime`
- `0x1800088d4`: `%s with Trace ID 0x%x Completed`
- `0x1800088a8`: `RemoteTerminal->GetProtocolStatus failed: 0x%x`
- `0x18000868f`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x180008801`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RpcGetSessionProtocolLastInputTime(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        _QWORD *a4,
        _DWORD *a5,
        __int64 a6)
{
  int v8; // esi
  unsigned int v9; // edi
  RPC_STATUS v10; // eax
  int v11; // ebx
  void *v12; // rdi
  int v13; // ebx
  const char *v15; // r8
  int v16; // eax
  bool v17; // sf
  HLOCAL v18; // rax
  int v19; // eax
  int v20; // eax
  HANDLE v21; // rax
  void *v22; // rdi
  NTSTATUS InformationProcess; // eax
  wchar_t *v24; // rax
  wchar_t *v25; // rax
  int TokenHandle; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v28; // [rsp+40h] [rbp-C0h]
  struct ITerminal *v29; // [rsp+48h] [rbp-B8h] BYREF
  struct CTraceBase *v30; // [rsp+50h] [rbp-B0h] BYREF
  void **v31; // [rsp+60h] [rbp-A0h] BYREF
  GUID pguid; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v33[2]; // [rsp+78h] [rbp-88h] BYREF
  struct CTraceBase *v34; // [rsp+80h] [rbp-80h] BYREF
  int v35; // [rsp+88h] [rbp-78h]
  const char *v36; // [rsp+90h] [rbp-70h]
  unsigned int Pid[2]; // [rsp+98h] [rbp-68h] BYREF
  int v38; // [rsp+A0h] [rbp-60h]
  unsigned __int16 v39[262]; // [rsp+A4h] [rbp-5Ch] BYREF
  _BYTE ProcessInformation[8]; // [rsp+2B0h] [rbp+1B0h] BYREF
  wchar_t *Str; // [rsp+2B8h] [rbp+1B8h]

  v28 = a2;
  TokenHandle = 0;
  v29 = 0;
  v27 = 0;
  v31 = &CTraceBase::`vftable';
  v8 = 1;
  v33[1] = 1;
  v34 = 0;
  if ( CTraceBase::g_bEnabled )
  {
    if ( (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(2, "Adding trace %p, %d, %s", &v31, 1, "RpcGetSessionProtocolLastInputTime");
    v30 = 0;
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v30) >= 0 && v30 && (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(
        2,
        "TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC",
        1);
    CTraceBase::ResetThreadCurrentOperationTrace(0, 0);
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v34) >= 0 && v34 )
    {
      (*(void (__fastcall **)(struct CTraceBase *, GUID *))(*(_QWORD *)v34 + 32LL))(v34, &pguid);
      v33[0] = (*(__int64 (__fastcall **)(struct CTraceBase *))(*(_QWORD *)v34 + 24LL))(v34);
      v35 = 1;
      goto LABEL_4;
    }
    CTraceBase::ResetThreadCurrentOperationTrace((struct CTraceBase *)&v31, "RpcGetSessionProtocolLastInputTime");
    CTraceBase::GenerateTraceID(&pguid, v33);
  }
  else
  {
    CoCreateGuid(&pguid);
    v33[0] = _InterlockedIncrement((volatile signed __int32 *)&CTraceBase::g_NextShortActivityID);
  }
  v35 = 0;
LABEL_4:
  v31 = &CRpcCallTrace::`vftable';
  v36 = "RpcGetSessionProtocolLastInputTime";
  *(_QWORD *)Pid = -1;
  v38 = 0;
  memset_0(v39, 0, 0x208u);
  if ( v38 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "TRACE RPC %s with Trace ID 0x%x", v36, v33[0]);
  v9 = g_DebugTraceComponent & 1;
  *(_QWORD *)Pid = -1;
  v10 = I_RpcBindingInqLocalClientPID(0, &Pid[1]);
  v11 = v10;
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x80070000;
  if ( v11 >= 0 )
  {
    ProcessIdToSessionId(Pid[1], Pid);
    if ( v9 )
    {
      v21 = OpenProcess(0x400u, 0, Pid[1]);
      v22 = v21;
      if ( v21 )
      {
        InformationProcess = NtQueryInformationProcess(v21, ProcessImageFileName, ProcessInformation, 0x110u, 0);
        v11 = InformationProcess | 0x10000000;
        if ( InformationProcess >= 0 )
        {
          v24 = wcsrchr(Str, 0x5Cu);
          if ( v24 )
            v25 = v24 + 1;
          else
            v25 = Str;
          StringCchCopyW(v39, 0x104u, v25);
        }
        CloseHandle(v22);
      }
    }
  }
  if ( v38 )
  {
    if ( v11 < 0 )
    {
      if ( (g_DebugTraceComponent & 1) != 0 )
        _DbgPrintMessage(2, "RPC Caller: Unknown");
    }
    else if ( (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(2, "RPC Caller: PID %d, SessID %d, Process Name: <%S>", Pid[1], Pid[0], v39);
    }
  }
  if ( !a4 )
  {
    v15 = "ppProtoStatus";
LABEL_27:
    _DbgPrintMessage(8, "Missing paramter %s in %s", v15, "RpcGetSessionProtocolLastInputTime");
    v13 = -2147024809;
    goto LABEL_19;
  }
  if ( !a5 )
  {
    v15 = "pcbProtoStatus";
    goto LABEL_27;
  }
  if ( !a6 )
  {
    v15 = "pLastInputTime";
    goto LABEL_27;
  }
  if ( a3 > 1 )
  {
    v13 = -2147024809;
    _DbgPrintMessage(8, "Invalid InfoType failed: 0x%x in %s", -2147024809, "RpcGetSessionProtocolLastInputTime");
    goto LABEL_19;
  }
  v12 = 0;
  v13 = RCMRpcPrologueEx(v28, 1u, 1u, &v29, 0, &TokenHandle);
  if ( v13 < 0 )
  {
    if ( v13 != -2147022646 )
      v8 = 4;
    _DbgPrintMessage(v8, "RCMRpcPrologue failed: 0x%x", v13);
  }
  else
  {
    v13 = (**(__int64 (__fastcall ***)(struct ITerminal *, __int64 *, __int64 *))v29)(v29, qword_1800DD390, &v27);
    if ( v13 >= 0 )
    {
      v18 = LocalAlloc(0x40u, 0x718u);
      v12 = v18;
      if ( v18 )
      {
        memset_0(v18, 0, 0x718u);
        v19 = (*(__int64 (__fastcall **)(__int64, _QWORD, void *))(*(_QWORD *)v27 + 248LL))(v27, a3, v12);
        if ( v19 < 0 )
          _DbgPrintMessage(8, "RemoteTerminal->GetProtocolStatus failed: 0x%x", v19);
        v20 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v27 + 256LL))(v27, a6);
        v13 = v20;
        if ( v20 < 0 )
          _DbgPrintMessage(
            8,
            "RemoteTerminal->GetLastInputTime failed: 0x%x in %s",
            v20,
            "RpcGetSessionProtocolLastInputTime");
      }
      else
      {
        v13 = -2147024882;
      }
    }
  }
  if ( !TokenHandle )
    goto LABEL_17;
  v16 = RpcRevertToSelf();
  v17 = v16 < 0;
  if ( v16 > 0 )
  {
    v16 = (unsigned __int16)v16 | 0x80070000;
    v17 = v16 < 0;
  }
  if ( v17 )
  {
    _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v16);
    v13 = -2147024891;
  }
  else
  {
LABEL_17:
    if ( v13 >= 0 )
    {
      *a4 = v12;
      *a5 = 1816;
      goto LABEL_19;
    }
  }
  if ( v12 )
    LocalFree(v12);
LABEL_19:
  v31 = &CRpcCallTrace::`vftable';
  if ( v38 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "%s with Trace ID 0x%x Completed", v36, v33[0]);
  v31 = &CTraceBase::`vftable';
  if ( CTraceBase::g_bEnabled && !v35 && CTraceBase::g_TLSIndex != -1 )
  {
    if ( TlsSetValue(CTraceBase::g_TLSIndex, 0) )
    {
      if ( TlsSetValue(CTraceBase::g_CreatorFunctionTLSIndex, 0) )
        goto LABEL_21;
    }
    else
    {
      GetLastError();
    }
    GetLastError();
  }
LABEL_21:
  v34 = 0;
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v29 )
    (*(void (__fastcall **)(struct ITerminal *))(*(_QWORD *)v29 + 16LL))(v29);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180008290  mov     [rsp-8+arg_0], rbx
0x180008295  push    rbp
0x180008296  push    rsi
0x180008297  push    rdi
0x180008298  push    r12
0x18000829a  push    r13
0x18000829c  push    r14
0x18000829e  push    r15
0x1800082a0  lea     rbp, [rsp-2D0h]
0x1800082a8  sub     rsp, 3D0h
0x1800082af  mov     rax, cs:__security_cookie
0x1800082b6  xor     rax, rsp
0x1800082b9  mov     [rbp+300h+var_40], rax
0x1800082c0  mov     r14, r9
0x1800082c3  mov     r13d, r8d
0x1800082c6  mov     [rsp+400h+var_3C0], edx
0x1800082ca  mov     r15, [rbp+300h+arg_20]
0x1800082d1  mov     r12, [rbp+300h+arg_28]
0x1800082d8  xor     ebx, ebx
0x1800082da  mov     [rsp+400h+var_3D0], ebx
0x1800082de  mov     [rsp+400h+var_3B8], rbx
0x1800082e3  mov     [rsp+400h+var_3C8], rbx
0x1800082e8  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x1800082ef  mov     [rsp+400h+var_3A0], rax
0x1800082f4  mov     esi, 1
0x1800082f9  mov     [rsp+400h+var_384], esi
0x1800082fd  mov     [rbp+300h+var_380], rbx
0x180008301  lea     rdi, aRpcgetsessionp_0; "RpcGetSessionProtocolLastInputTime"
0x180008308  cmp     cs:?g_bEnabled@CTraceBase@@0HA, ebx; int CTraceBase::g_bEnabled
0x18000830e  jnz     loc_180008642
0x180008314  lea     rcx, [rsp+400h+pguid]; pguid
0x180008319  call    cs:__imp_CoCreateGuid
0x180008320  nop     dword ptr [rax+rax+00h]
0x180008325  mov     eax, esi
0x180008327  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x18000832f  inc     eax
0x180008331  mov     [rsp+400h+var_388], eax
0x180008335  mov     [rbp+300h+var_378], ebx
0x180008338  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18000833f  mov     [rsp+400h+var_3A0], rax
0x180008344  mov     [rbp+300h+var_370], rdi
0x180008348  mov     qword ptr [rbp+300h+Pid], 0FFFFFFFFFFFFFFFFh
0x180008350  mov     [rbp+300h+var_360], ebx
0x180008353  xor     edx, edx; Val
0x180008355  mov     r8d, 208h; Size
0x18000835b  lea     rcx, [rbp+300h+var_35C]; void *
0x18000835f  call    memset_0
0x180008364  cmp     [rbp+300h+var_360], ebx
0x180008367  jnz     loc_18000870D
0x18000836d  mov     edi, cs:?g_DebugTraceComponent@@3KA; ulong g_DebugTraceComponent
0x180008373  and     edi, esi
0x180008375  mov     qword ptr [rbp+300h+Pid], 0FFFFFFFFFFFFFFFFh
0x18000837d  lea     rdx, [rbp+300h+Pid+4]; Pid
0x180008381  xor     ecx, ecx; Binding
0x180008383  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000838a  nop     dword ptr [rax+rax+00h]
0x18000838f  mov     ebx, eax
0x180008391  test    eax, eax
0x180008393  jle     short loc_18000839E
0x180008395  movzx   ebx, ax
0x180008398  or      ebx, 80070000h
0x18000839e  test    ebx, ebx
0x1800083a0  js      short loc_1800083BD
0x1800083a2  lea     rdx, [rbp+300h+Pid]; pSessionId
0x1800083a6  mov     ecx, [rbp+300h+Pid+4]; dwProcessId
0x1800083a9  call    cs:__imp_ProcessIdToSessionId
0x1800083b0  nop     dword ptr [rax+rax+00h]
0x1800083b5  test    edi, edi
0x1800083b7  jnz     loc_180008739
0x1800083bd  cmp     [rbp+300h+var_360], 0
0x1800083c1  jnz     loc_1800087DF
0x1800083c7  test    r14, r14
0x1800083ca  jz      loc_1800084EE
0x1800083d0  test    r15, r15
0x1800083d3  jz      loc_18000883A
0x1800083d9  test    r12, r12
0x1800083dc  jz      loc_180008846
0x1800083e2  cmp     r13d, esi
0x1800083e5  ja      loc_180008852
0x1800083eb  xor     edi, edi
0x1800083ed  lea     rax, [rsp+400h+var_3D0]
0x1800083f2  mov     [rsp+400h+TokenHandle], rax; TokenHandle
0x1800083f7  mov     [rsp+400h+ReturnLength], rdi; struct ITSSession **
0x1800083fc  lea     r9, [rsp+400h+var_3B8]; struct ITerminal **
0x180008401  mov     r8d, esi; int
0x180008404  mov     edx, esi; unsigned int
0x180008406  mov     ecx, [rsp+400h+var_3C0]; unsigned int
0x18000840a  call    ?RCMRpcPrologueEx@@YAJKKHPEAPEAUITerminal@@PEAPEAUITSSession@@PEAH@Z; RCMRpcPrologueEx(ulong,ulong,int,ITerminal * *,ITSSession * *,int *)
0x18000840f  mov     ebx, eax
0x180008411  test    eax, eax
0x180008413  js      loc_180008877
0x180008419  mov     rcx, [rsp+400h+var_3B8]
0x18000841e  mov     rax, [rcx]
0x180008421  lea     r8, [rsp+400h+var_3C8]
0x180008426  lea     rdx, qword_1800DD390
0x18000842d  mov     rax, [rax]
0x180008430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008435  mov     ebx, eax
0x180008437  test    eax, eax
0x180008439  jns     loc_1800085AD
0x18000843f  cmp     [rsp+400h+var_3D0], 0
0x180008444  jnz     loc_180008517
0x18000844a  test    ebx, ebx
0x18000844c  js      loc_180008550
0x180008452  mov     [r14], rdi
0x180008455  mov     dword ptr [r15], 718h
0x18000845c  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x180008463  mov     [rsp+400h+var_3A0], rax
0x180008468  cmp     [rbp+300h+var_360], 0
0x18000846c  jnz     loc_1800088BE
0x180008472  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x180008479  mov     [rsp+400h+var_3A0], rax
0x18000847e  cmp     cs:?g_bEnabled@CTraceBase@@0HA, 0; int CTraceBase::g_bEnabled
0x180008485  jnz     loc_18000856D
0x18000848b  mov     [rbp+300h+var_380], 0
0x180008493  mov     rcx, [rsp+400h+var_3C8]
0x180008498  test    rcx, rcx
0x18000849b  jz      short loc_1800084AA
0x18000849d  mov     rax, [rcx]
0x1800084a0  mov     rax, [rax+10h]
0x1800084a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084a9  nop
0x1800084aa  mov     rcx, [rsp+400h+var_3B8]
0x1800084af  test    rcx, rcx
0x1800084b2  jz      short loc_1800084C1
0x1800084b4  mov     rax, [rcx]
0x1800084b7  mov     rax, [rax+10h]
0x1800084bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084c0  nop
0x1800084c1  mov     eax, ebx
0x1800084c3  mov     rcx, [rbp+300h+var_40]
0x1800084ca  xor     rcx, rsp; StackCookie
0x1800084cd  call    __security_check_cookie
0x1800084d2  mov     rbx, [rsp+400h+arg_0]
0x1800084da  add     rsp, 3D0h
0x1800084e1  pop     r15
0x1800084e3  pop     r14
0x1800084e5  pop     r13
0x1800084e7  pop     r12
0x1800084e9  pop     rdi
0x1800084ea  pop     rsi
0x1800084eb  pop     rbp
0x1800084ec  retn
0x1800084ee  lea     r8, aPpprotostatus; "ppProtoStatus"
0x1800084f5  lea     r9, aRpcgetsessionp_0; "RpcGetSessionProtocolLastInputTime"
0x1800084fc  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180008503  mov     ecx, 8; int
0x180008508  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000850d  mov     ebx, 80070057h
0x180008512  jmp     loc_18000845C
0x180008517  call    cs:__imp_RpcRevertToSelf
0x18000851e  nop     dword ptr [rax+rax+00h]
0x180008523  test    eax, eax
0x180008525  jle     short loc_180008531
0x180008527  movzx   eax, ax
0x18000852a  or      eax, 80070000h
0x18000852f  test    eax, eax
0x180008531  jns     loc_18000844A
0x180008537  mov     r8d, eax
0x18000853a  lea     rdx, aRpcreverttosel_1; "RpcRevertToSelf failed: 0x%x"
0x180008541  mov     ecx, 8; int
0x180008546  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000854b  mov     ebx, 80070005h
0x180008550  test    rdi, rdi
0x180008553  jz      loc_18000845C
0x180008559  mov     rcx, rdi; hMem
0x18000855c  call    cs:__imp_LocalFree
0x180008563  nop     dword ptr [rax+rax+00h]
0x180008568  jmp     loc_18000845C
0x18000856d  cmp     [rbp+300h+var_378], 0
0x180008571  jnz     loc_18000848B
0x180008577  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x18000857d  cmp     ecx, 0FFFFFFFFh
0x180008580  jz      loc_18000848B
0x180008586  xor     edx, edx; lpTlsValue
0x180008588  call    cs:__imp_TlsSetValue
0x18000858f  nop     dword ptr [rax+rax+00h]
0x180008594  test    eax, eax
0x180008596  jnz     loc_1800088EA
0x18000859c  call    cs:__imp_GetLastError
0x1800085a3  nop     dword ptr [rax+rax+00h]
0x1800085a8  jmp     loc_180008906
0x1800085ad  mov     edx, 718h; uBytes
0x1800085b2  mov     ecx, 40h ; '@'; uFlags
0x1800085b7  call    cs:__imp_LocalAlloc
0x1800085be  nop     dword ptr [rax+rax+00h]
0x1800085c3  mov     rdi, rax
0x1800085c6  test    rax, rax
0x1800085c9  jz      loc_18000889B
0x1800085cf  xor     edx, edx; Val
0x1800085d1  mov     r8d, 718h; Size
0x1800085d7  mov     rcx, rax; void *
0x1800085da  call    memset_0
0x1800085df  mov     rcx, [rsp+400h+var_3C8]
0x1800085e4  mov     rax, [rcx]
0x1800085e7  mov     r8, rdi
0x1800085ea  mov     edx, r13d
0x1800085ed  mov     rax, [rax+0F8h]
0x1800085f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085f9  test    eax, eax
0x1800085fb  js      loc_1800088A5
0x180008601  mov     rcx, [rsp+400h+var_3C8]
0x180008606  mov     rax, [rcx]
0x180008609  mov     rdx, r12
0x18000860c  mov     rax, [rax+100h]
0x180008613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008618  mov     ebx, eax
0x18000861a  test    eax, eax
0x18000861c  jns     loc_18000843F
0x180008622  lea     r9, aRpcgetsessionp_0; "RpcGetSessionProtocolLastInputTime"
0x180008629  mov     r8d, eax
0x18000862c  lea     rdx, aRemoteterminal_1; "RemoteTerminal->GetLastInputTime failed"...
0x180008633  mov     ecx, 8; int
0x180008638  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000863d  jmp     loc_18000843F
0x180008642  test    byte ptr cs:?g_DebugTraceComponent@@3KA, sil; ulong g_DebugTraceComponent
0x180008649  jz      short loc_180008669
0x18000864b  mov     [rsp+400h+ReturnLength], rdi
0x180008650  mov     r9d, esi
0x180008653  lea     r8, [rsp+400h+var_3A0]
0x180008658  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x18000865f  mov     ecx, 2; int
0x180008664  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008669  mov     [rsp+400h+var_3B0], rbx
0x18000866e  lea     rcx, [rsp+400h+var_3B0]; struct CTraceBase **
0x180008673  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x180008678  test    eax, eax
0x18000867a  js      short loc_1800086A0
0x18000867c  cmp     [rsp+400h+var_3B0], rbx
0x180008681  jz      short loc_1800086A0
0x180008683  test    byte ptr cs:?g_DebugTraceComponent@@3KA, sil; ulong g_DebugTraceComponent
0x18000868a  jz      short loc_1800086A0
0x18000868c  mov     r8d, esi
0x18000868f  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x180008696  mov     ecx, 2; int
0x18000869b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800086a0  xor     edx, edx; char *
0x1800086a2  xor     ecx, ecx; lpTlsValue
0x1800086a4  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x1800086a9  lea     rcx, [rbp+300h+var_380]; struct CTraceBase **
0x1800086ad  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x1800086b2  test    eax, eax
0x1800086b4  js      short loc_1800086EC
0x1800086b6  mov     rcx, [rbp+300h+var_380]
0x1800086ba  test    rcx, rcx
0x1800086bd  jz      short loc_1800086EC
0x1800086bf  mov     rax, [rcx]
0x1800086c2  lea     rdx, [rsp+400h+pguid]
0x1800086c7  mov     rax, [rax+20h]
0x1800086cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086d0  mov     rcx, [rbp+300h+var_380]
0x1800086d4  mov     rax, [rcx]
0x1800086d7  mov     rax, [rax+18h]
0x1800086db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086e0  mov     [rsp+400h+var_388], eax
0x1800086e4  mov     [rbp+300h+var_378], esi
0x1800086e7  jmp     loc_180008338
0x1800086ec  mov     rdx, rdi; char *
0x1800086ef  lea     rcx, [rsp+400h+var_3A0]; lpTlsValue
0x1800086f4  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x1800086f9  lea     rdx, [rsp+400h+var_388]; unsigned int *
0x1800086fe  lea     rcx, [rsp+400h+pguid]; struct _GUID *
0x180008703  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x180008708  jmp     loc_180008335
0x18000870d  test    byte ptr cs:?g_DebugTraceComponent@@3KA, sil; ulong g_DebugTraceComponent
0x180008714  jz      loc_18000836D
0x18000871a  mov     r9d, [rsp+400h+var_388]
0x18000871f  mov     r8, [rbp+300h+var_370]
0x180008723  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x18000872a  mov     ecx, 2; int
0x18000872f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008734  jmp     loc_18000836D
0x180008739  mov     r8d, [rbp+300h+Pid+4]; dwProcessId
0x18000873d  xor     edx, edx; bInheritHandle
0x18000873f  mov     ecx, 400h; dwDesiredAccess
0x180008744  call    cs:__imp_OpenProcess
0x18000874b  nop     dword ptr [rax+rax+00h]
0x180008750  mov     rdi, rax
0x180008753  test    rax, rax
0x180008756  jz      loc_1800083BD
0x18000875c  mov     [rsp+400h+ReturnLength], 0; ReturnLength
0x180008765  mov     r9d, 110h; ProcessInformationLength
0x18000876b  lea     r8, [rbp+300h+ProcessInformation]; ProcessInformation
0x180008772  mov     edx, 1Bh; ProcessInformationClass
0x180008777  mov     rcx, rax; ProcessHandle
0x18000877a  call    cs:__imp_NtQueryInformationProcess
0x180008781  nop     dword ptr [rax+rax+00h]
0x180008786  mov     ebx, eax
0x180008788  or      ebx, 10000000h
0x18000878e  jl      short loc_1800087CB
0x180008790  mov     edx, 5Ch ; '\'; Ch
0x180008795  mov     rcx, [rbp+300h+Str]; Str
0x18000879c  call    cs:__imp_wcsrchr
0x1800087a3  nop     dword ptr [rax+rax+00h]
0x1800087a8  test    rax, rax
0x1800087ab  jnz     short loc_1800087B6
0x1800087ad  mov     rax, [rbp+300h+Str]
0x1800087b4  jmp     short loc_1800087BA
0x1800087b6  add     rax, 2
0x1800087ba  mov     r8, rax; unsigned __int16 *
  ... truncated ...
```
