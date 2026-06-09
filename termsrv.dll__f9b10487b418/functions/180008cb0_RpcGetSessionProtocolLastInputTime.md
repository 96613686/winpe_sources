# RpcGetSessionProtocolLastInputTime

- ea: `0x180008cb0`
- end: `0x1800092e3`
- name: `RpcGetSessionProtocolLastInputTime`
- size: `1587`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008cb0`
- `0x1800092f0`
- `0x18000a210`
- `0x18000f790`
- `0x1800119a0`
- `0x1800127b0`
- `0x180014de0`
- `0x1800321f0`
- `0x1800330c4`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000917f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000917f`
- `ntdll!NtQueryInformationProcess` at `0x180009163`
- `ntdll!NtQueryInformationProcess` at `0x180009163`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800092d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800092d7`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180008dbd`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180008dbd`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180008f89`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800092c9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180008f89`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800092c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091ab`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180008d9d`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180008d9d`
- `RPCRT4!RpcRevertToSelf` at `0x180008f24`
- `RPCRT4!RpcRevertToSelf` at `0x180008f24`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180009133`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180009133`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008fac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008fac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008f63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008f63`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180008d39`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180008d39`

## string_xrefs

- `0x180008d21`: `RpcGetSessionProtocolLastInputTime`
- `0x180008f02`: `RpcGetSessionProtocolLastInputTime`
- `0x180009011`: `RpcGetSessionProtocolLastInputTime`
- `0x18000922e`: `RpcGetSessionProtocolLastInputTime`
- `0x1800092ab`: `%s with Trace ID 0x%x Completed`
- `0x18000927f`: `RemoteTerminal->GetProtocolStatus failed: 0x%x`
- `0x18000907e`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x1800091d8`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

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
    v13 = (**(__int64 (__fastcall ***)(struct ITerminal *, __int64 *, __int64 *))v29)(v29, qword_1800D7370, &v27);
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
0x180008cb0  mov     [rsp-8+arg_0], rbx
0x180008cb5  push    rbp
0x180008cb6  push    rsi
0x180008cb7  push    rdi
0x180008cb8  push    r12
0x180008cba  push    r13
0x180008cbc  push    r14
0x180008cbe  push    r15
0x180008cc0  lea     rbp, [rsp-2D0h]
0x180008cc8  sub     rsp, 3D0h
0x180008ccf  mov     rax, cs:__security_cookie
0x180008cd6  xor     rax, rsp
0x180008cd9  mov     [rbp+300h+var_40], rax
0x180008ce0  mov     r14, r9
0x180008ce3  mov     r13d, r8d
0x180008ce6  mov     [rsp+400h+var_3C0], edx
0x180008cea  mov     r15, [rbp+300h+arg_20]
0x180008cf1  mov     r12, [rbp+300h+arg_28]
0x180008cf8  xor     ebx, ebx
0x180008cfa  mov     [rsp+400h+var_3D0], ebx
0x180008cfe  mov     [rsp+400h+var_3B8], rbx
0x180008d03  mov     [rsp+400h+var_3C8], rbx
0x180008d08  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x180008d0f  mov     [rsp+400h+var_3A0], rax
0x180008d14  mov     esi, 1
0x180008d19  mov     [rsp+400h+var_384], esi
0x180008d1d  mov     [rbp+300h+var_380], rbx
0x180008d21  lea     rdi, aRpcgetsessionp_0; "RpcGetSessionProtocolLastInputTime"
0x180008d28  cmp     cs:?g_bEnabled@CTraceBase@@0HA, ebx; int CTraceBase::g_bEnabled
0x180008d2e  jnz     loc_180009031
0x180008d34  lea     rcx, [rsp+400h+pguid]; pguid
0x180008d39  call    cs:__imp_CoCreateGuid
0x180008d3f  mov     eax, esi
0x180008d41  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x180008d49  inc     eax
0x180008d4b  mov     [rsp+400h+var_388], eax
0x180008d4f  mov     [rbp+300h+var_378], ebx
0x180008d52  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x180008d59  mov     [rsp+400h+var_3A0], rax
0x180008d5e  mov     [rbp+300h+var_370], rdi
0x180008d62  mov     qword ptr [rbp+300h+Pid], 0FFFFFFFFFFFFFFFFh
0x180008d6a  mov     [rbp+300h+var_360], ebx
0x180008d6d  xor     edx, edx; Val
0x180008d6f  mov     r8d, 208h; Size
0x180008d75  lea     rcx, [rbp+300h+var_35C]; void *
0x180008d79  call    memset_0
0x180008d7e  cmp     [rbp+300h+var_360], ebx
0x180008d81  jnz     loc_1800090FC
0x180008d87  mov     edi, cs:?g_DebugTraceComponent@@3KA; ulong g_DebugTraceComponent
0x180008d8d  and     edi, esi
0x180008d8f  mov     qword ptr [rbp+300h+Pid], 0FFFFFFFFFFFFFFFFh
0x180008d97  lea     rdx, [rbp+300h+Pid+4]; Pid
0x180008d9b  xor     ecx, ecx; Binding
0x180008d9d  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180008da3  mov     ebx, eax
0x180008da5  test    eax, eax
0x180008da7  jle     short loc_180008DB2
0x180008da9  movzx   ebx, ax
0x180008dac  or      ebx, 80070000h
0x180008db2  test    ebx, ebx
0x180008db4  js      short loc_180008DCB
0x180008db6  lea     rdx, [rbp+300h+Pid]; pSessionId
0x180008dba  mov     ecx, [rbp+300h+Pid+4]; dwProcessId
0x180008dbd  call    cs:__imp_ProcessIdToSessionId
0x180008dc3  test    edi, edi
0x180008dc5  jnz     loc_180009128
0x180008dcb  cmp     [rbp+300h+var_360], 0
0x180008dcf  jnz     loc_1800091B6
0x180008dd5  test    r14, r14
0x180008dd8  jz      loc_180008EFB
0x180008dde  test    r15, r15
0x180008de1  jz      loc_180009211
0x180008de7  test    r12, r12
0x180008dea  jz      loc_18000921D
0x180008df0  cmp     r13d, esi
0x180008df3  ja      loc_180009229
0x180008df9  xor     edi, edi
0x180008dfb  lea     rax, [rsp+400h+var_3D0]
0x180008e00  mov     [rsp+400h+TokenHandle], rax; TokenHandle
0x180008e05  mov     [rsp+400h+ReturnLength], rdi; struct ITSSession **
0x180008e0a  lea     r9, [rsp+400h+var_3B8]; struct ITerminal **
0x180008e0f  mov     r8d, esi; int
0x180008e12  mov     edx, esi; unsigned int
0x180008e14  mov     ecx, [rsp+400h+var_3C0]; unsigned int
0x180008e18  call    ?RCMRpcPrologueEx@@YAJKKHPEAPEAUITerminal@@PEAPEAUITSSession@@PEAH@Z; RCMRpcPrologueEx(ulong,ulong,int,ITerminal * *,ITSSession * *,int *)
0x180008e1d  mov     ebx, eax
0x180008e1f  test    eax, eax
0x180008e21  js      loc_18000924E
0x180008e27  mov     rcx, [rsp+400h+var_3B8]
0x180008e2c  mov     rax, [rcx]
0x180008e2f  lea     r8, [rsp+400h+var_3C8]
0x180008e34  lea     rdx, qword_1800D7370
0x180008e3b  mov     rax, [rax]
0x180008e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e43  mov     ebx, eax
0x180008e45  test    eax, eax
0x180008e47  jns     loc_180008FA2
0x180008e4d  cmp     [rsp+400h+var_3D0], 0
0x180008e52  jnz     loc_180008F24
0x180008e58  test    ebx, ebx
0x180008e5a  js      loc_180008F57
0x180008e60  mov     [r14], rdi
0x180008e63  mov     dword ptr [r15], 718h
0x180008e6a  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x180008e71  mov     [rsp+400h+var_3A0], rax
0x180008e76  cmp     [rbp+300h+var_360], 0
0x180008e7a  jnz     loc_180009295
0x180008e80  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x180008e87  mov     [rsp+400h+var_3A0], rax
0x180008e8c  cmp     cs:?g_bEnabled@CTraceBase@@0HA, 0; int CTraceBase::g_bEnabled
0x180008e93  jnz     loc_180008F6E
0x180008e99  mov     [rbp+300h+var_380], 0
0x180008ea1  mov     rcx, [rsp+400h+var_3C8]
0x180008ea6  test    rcx, rcx
0x180008ea9  jz      short loc_180008EB8
0x180008eab  mov     rax, [rcx]
0x180008eae  mov     rax, [rax+10h]
0x180008eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008eb7  nop
0x180008eb8  mov     rcx, [rsp+400h+var_3B8]
0x180008ebd  test    rcx, rcx
0x180008ec0  jz      short loc_180008ECF
0x180008ec2  mov     rax, [rcx]
0x180008ec5  mov     rax, [rax+10h]
0x180008ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ece  nop
0x180008ecf  mov     eax, ebx
0x180008ed1  mov     rcx, [rbp+300h+var_40]
0x180008ed8  xor     rcx, rsp; StackCookie
0x180008edb  call    __security_check_cookie
0x180008ee0  mov     rbx, [rsp+400h+arg_0]
0x180008ee8  add     rsp, 3D0h
0x180008eef  pop     r15
0x180008ef1  pop     r14
0x180008ef3  pop     r13
0x180008ef5  pop     r12
0x180008ef7  pop     rdi
0x180008ef8  pop     rsi
0x180008ef9  pop     rbp
0x180008efa  retn
0x180008efb  lea     r8, aPpprotostatus; "ppProtoStatus"
0x180008f02  lea     r9, aRpcgetsessionp_0; "RpcGetSessionProtocolLastInputTime"
0x180008f09  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180008f10  mov     ecx, 8; int
0x180008f15  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008f1a  mov     ebx, 80070057h
0x180008f1f  jmp     loc_180008E6A
0x180008f24  call    cs:__imp_RpcRevertToSelf
0x180008f2a  test    eax, eax
0x180008f2c  jle     short loc_180008F38
0x180008f2e  movzx   eax, ax
0x180008f31  or      eax, 80070000h
0x180008f36  test    eax, eax
0x180008f38  jns     loc_180008E58
0x180008f3e  mov     r8d, eax
0x180008f41  lea     rdx, aRpcreverttosel_1; "RpcRevertToSelf failed: 0x%x"
0x180008f48  mov     ecx, 8; int
0x180008f4d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008f52  mov     ebx, 80070005h
0x180008f57  test    rdi, rdi
0x180008f5a  jz      loc_180008E6A
0x180008f60  mov     rcx, rdi; hMem
0x180008f63  call    cs:__imp_LocalFree
0x180008f69  jmp     loc_180008E6A
0x180008f6e  cmp     [rbp+300h+var_378], 0
0x180008f72  jnz     loc_180008E99
0x180008f78  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x180008f7e  cmp     ecx, 0FFFFFFFFh
0x180008f81  jz      loc_180008E99
0x180008f87  xor     edx, edx; lpTlsValue
0x180008f89  call    cs:__imp_TlsSetValue
0x180008f8f  test    eax, eax
0x180008f91  jnz     loc_1800092C1
0x180008f97  call    cs:__imp_GetLastError
0x180008f9d  jmp     loc_1800092D7
0x180008fa2  mov     edx, 718h; uBytes
0x180008fa7  mov     ecx, 40h ; '@'; uFlags
0x180008fac  call    cs:__imp_LocalAlloc
0x180008fb2  mov     rdi, rax
0x180008fb5  test    rax, rax
0x180008fb8  jz      loc_180009272
0x180008fbe  xor     edx, edx; Val
0x180008fc0  mov     r8d, 718h; Size
0x180008fc6  mov     rcx, rax; void *
0x180008fc9  call    memset_0
0x180008fce  mov     rcx, [rsp+400h+var_3C8]
0x180008fd3  mov     rax, [rcx]
0x180008fd6  mov     r8, rdi
0x180008fd9  mov     edx, r13d
0x180008fdc  mov     rax, [rax+0F8h]
0x180008fe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fe8  test    eax, eax
0x180008fea  js      loc_18000927C
0x180008ff0  mov     rcx, [rsp+400h+var_3C8]
0x180008ff5  mov     rax, [rcx]
0x180008ff8  mov     rdx, r12
0x180008ffb  mov     rax, [rax+100h]
0x180009002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009007  mov     ebx, eax
0x180009009  test    eax, eax
0x18000900b  jns     loc_180008E4D
0x180009011  lea     r9, aRpcgetsessionp_0; "RpcGetSessionProtocolLastInputTime"
0x180009018  mov     r8d, eax
0x18000901b  lea     rdx, aRemoteterminal_1; "RemoteTerminal->GetLastInputTime failed"...
0x180009022  mov     ecx, 8; int
0x180009027  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000902c  jmp     loc_180008E4D
0x180009031  test    byte ptr cs:?g_DebugTraceComponent@@3KA, sil; ulong g_DebugTraceComponent
0x180009038  jz      short loc_180009058
0x18000903a  mov     [rsp+400h+ReturnLength], rdi
0x18000903f  mov     r9d, esi
0x180009042  lea     r8, [rsp+400h+var_3A0]
0x180009047  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x18000904e  mov     ecx, 2; int
0x180009053  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009058  mov     [rsp+400h+var_3B0], rbx
0x18000905d  lea     rcx, [rsp+400h+var_3B0]; struct CTraceBase **
0x180009062  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x180009067  test    eax, eax
0x180009069  js      short loc_18000908F
0x18000906b  cmp     [rsp+400h+var_3B0], rbx
0x180009070  jz      short loc_18000908F
0x180009072  test    byte ptr cs:?g_DebugTraceComponent@@3KA, sil; ulong g_DebugTraceComponent
0x180009079  jz      short loc_18000908F
0x18000907b  mov     r8d, esi
0x18000907e  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x180009085  mov     ecx, 2; int
0x18000908a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000908f  xor     edx, edx; char *
0x180009091  xor     ecx, ecx; lpTlsValue
0x180009093  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x180009098  lea     rcx, [rbp+300h+var_380]; struct CTraceBase **
0x18000909c  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x1800090a1  test    eax, eax
0x1800090a3  js      short loc_1800090DB
0x1800090a5  mov     rcx, [rbp+300h+var_380]
0x1800090a9  test    rcx, rcx
0x1800090ac  jz      short loc_1800090DB
0x1800090ae  mov     rax, [rcx]
0x1800090b1  lea     rdx, [rsp+400h+pguid]
0x1800090b6  mov     rax, [rax+20h]
0x1800090ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090bf  mov     rcx, [rbp+300h+var_380]
0x1800090c3  mov     rax, [rcx]
0x1800090c6  mov     rax, [rax+18h]
0x1800090ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090cf  mov     [rsp+400h+var_388], eax
0x1800090d3  mov     [rbp+300h+var_378], esi
0x1800090d6  jmp     loc_180008D52
0x1800090db  mov     rdx, rdi; char *
0x1800090de  lea     rcx, [rsp+400h+var_3A0]; lpTlsValue
0x1800090e3  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x1800090e8  lea     rdx, [rsp+400h+var_388]; unsigned int *
0x1800090ed  lea     rcx, [rsp+400h+pguid]; struct _GUID *
0x1800090f2  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x1800090f7  jmp     loc_180008D4F
0x1800090fc  test    byte ptr cs:?g_DebugTraceComponent@@3KA, sil; ulong g_DebugTraceComponent
0x180009103  jz      loc_180008D87
0x180009109  mov     r9d, [rsp+400h+var_388]
0x18000910e  mov     r8, [rbp+300h+var_370]
0x180009112  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x180009119  mov     ecx, 2; int
0x18000911e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009123  jmp     loc_180008D87
0x180009128  mov     r8d, [rbp+300h+Pid+4]; dwProcessId
0x18000912c  xor     edx, edx; bInheritHandle
0x18000912e  mov     ecx, 400h; dwDesiredAccess
0x180009133  call    cs:__imp_OpenProcess
0x180009139  mov     rdi, rax
0x18000913c  test    rax, rax
0x18000913f  jz      loc_180008DCB
0x180009145  mov     [rsp+400h+ReturnLength], 0; ReturnLength
0x18000914e  mov     r9d, 110h; ProcessInformationLength
0x180009154  lea     r8, [rbp+300h+ProcessInformation]; ProcessInformation
0x18000915b  mov     edx, 1Bh; ProcessInformationClass
0x180009160  mov     rcx, rax; ProcessHandle
0x180009163  call    cs:__imp_NtQueryInformationProcess
0x180009169  mov     ebx, eax
0x18000916b  or      ebx, 10000000h
0x180009171  jl      short loc_1800091A8
0x180009173  mov     edx, 5Ch ; '\'; Ch
0x180009178  mov     rcx, [rbp+300h+Str]; Str
0x18000917f  call    cs:__imp_wcsrchr
0x180009185  test    rax, rax
0x180009188  jnz     short loc_180009193
0x18000918a  mov     rax, [rbp+300h+Str]
0x180009191  jmp     short loc_180009197
0x180009193  add     rax, 2
0x180009197  mov     r8, rax; unsigned __int16 *
0x18000919a  mov     edx, 104h; unsigned __int64
0x18000919f  lea     rcx, [rbp+300h+var_35C]; unsigned __int16 *
0x1800091a3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800091a8  mov     rcx, rdi; hObject
0x1800091ab  call    cs:__imp_CloseHandle
0x1800091b1  jmp     loc_180008DCB
0x1800091b6  test    ebx, ebx
0x1800091b8  js      short loc_1800091EE
0x1800091ba  test    byte ptr cs:?g_DebugTraceComponent@@3KA, sil; ulong g_DebugTraceComponent
0x1800091c1  jz      loc_180008DD5
0x1800091c7  lea     rax, [rbp+300h+var_35C]
  ... truncated ...
```
