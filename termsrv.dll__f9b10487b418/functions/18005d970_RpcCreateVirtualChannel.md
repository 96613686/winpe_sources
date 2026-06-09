# RpcCreateVirtualChannel

- ea: `0x18005d970`
- end: `0x18005de87`
- name: `RpcCreateVirtualChannel`
- size: `1303`
- prototype: `__int64 __fastcall(__int64, unsigned int, const char *, int, void **)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005de90`

## callees

- `0x1800092f0`
- `0x18000a210`
- `0x18000bad0`
- `0x18000f1a0`
- `0x1800130d8`
- `0x180013150`
- `0x1800148d0`
- `0x180027d54`
- `0x18002aa5c`
- `0x1800321f0`
- `0x18005bebc`
- `0x18005d970`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18005dae4`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18005dae4`
- `ntdll!EtwEventActivityIdControl` at `0x18005da1c`
- `ntdll!EtwEventActivityIdControl` at `0x18005de1a`
- `ntdll!EtwEventActivityIdControl` at `0x18005da1c`
- `ntdll!EtwEventActivityIdControl` at `0x18005de1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005dd9e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005dd9e`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18005dca6`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18005dca6`
- `RPCRT4!RpcRevertToSelf` at `0x18005dbba`
- `RPCRT4!RpcRevertToSelf` at `0x18005dcd8`
- `RPCRT4!RpcRevertToSelf` at `0x18005dde4`
- `RPCRT4!RpcRevertToSelf` at `0x18005dbba`
- `RPCRT4!RpcRevertToSelf` at `0x18005dcd8`
- `RPCRT4!RpcRevertToSelf` at `0x18005dde4`
- `RPCRT4!RpcImpersonateClient` at `0x18005dc42`
- `RPCRT4!RpcImpersonateClient` at `0x18005dd2e`
- `RPCRT4!RpcImpersonateClient` at `0x18005dc42`
- `RPCRT4!RpcImpersonateClient` at `0x18005dd2e`

## string_xrefs

- `0x18005dc58`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18005d9a7`: `RpcCreateVirtualChannel`
- `0x18005dafb`: `RpcCreateVirtualChannel`
- `0x18005db96`: `RpcCreateVirtualChannel`
- `0x18005ddd0`: `RpcCreateVirtualChannel`
- `0x18005db05`: `AccessCheckForRailEncVC failed: 0x%x in %s`
- `0x18005dbd0`: `RpcRevertToSelf before ptrRemoteTerminal->CreateDynamicVirtualChannel failed: 0x%x in %s`
- `0x18005dc30`: `ptrRemoteTerminal->CreateDynamicVirtualChannel failed: 0x%x in %s`
- `0x18005dc8b`: `ptrRemoteTerminal->CreateStaticVirtualChannel failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RpcCreateVirtualChannel(__int64 a1, unsigned int a2, const char *a3, int a4, void **a5)
{
  signed int v8; // eax
  signed int v9; // ebx
  const char *v10; // r8
  int v11; // edi
  unsigned __int64 v12; // rax
  int v13; // eax
  int v14; // eax
  int v15; // r15d
  int v16; // eax
  int v17; // esi
  int InstanceOfSessionManager; // eax
  bool v19; // sf
  const char *v20; // rdx
  bool v21; // sf
  int v22; // eax
  RPC_STATUS v23; // eax
  bool v24; // sf
  bool v25; // sf
  __int64 v26; // rsi
  unsigned int v27; // ebx
  __int64 (__fastcall *v28)(__int64, void *, _QWORD, void **, unsigned int); // rdi
  DWORD CurrentProcessId; // eax
  int v30; // eax
  bool v31; // sf
  int TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int Pid; // [rsp+44h] [rbp-BCh] BYREF
  void *v35; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v36; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v37; // [rsp+58h] [rbp-A8h]
  __int64 v38; // [rsp+60h] [rbp-A0h] BYREF
  struct ISessionManager *v39; // [rsp+68h] [rbp-98h] BYREF
  struct ITerminal *v40; // [rsp+70h] [rbp-90h] BYREF
  void **v41; // [rsp+78h] [rbp-88h]
  GUID pguid; // [rsp+80h] [rbp-80h] BYREF
  GUID v43; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v44[592]; // [rsp+A0h] [rbp-60h] BYREF

  v37 = a4;
  v41 = a5;
  TokenHandle = 0;
  v40 = 0;
  v36 = 0;
  v35 = 0;
  Pid = 0;
  v39 = 0;
  v38 = 0;
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v44, 0, "RpcCreateVirtualChannel");
  pguid = 0;
  v8 = GenerateConstrainedGuid(&pguid, 0xF4600000);
  v43 = pguid;
  v9 = v8;
  EtwEventActivityIdControl(4, &v43);
  if ( v9 < 0 )
  {
    _DbgPrintMessage(8, "GenerateConstrainedGuid failed: 0x%x in %s", (unsigned int)v9, "RpcCreateVirtualChannel");
    goto LABEL_75;
  }
  if ( !a3 )
  {
    v10 = "EndpointName";
LABEL_6:
    _DbgPrintMessage(8, "Missing paramter %s in %s", v10, "RpcCreateVirtualChannel");
    v9 = -2147024809;
    goto LABEL_75;
  }
  if ( !a5 )
  {
    v10 = "phChannel";
    goto LABEL_6;
  }
  v11 = 1;
  if ( (a4 & 1) == 0 )
  {
    v12 = -1;
    do
      ++v12;
    while ( a3[v12] );
    if ( v12 > 7 )
    {
      v9 = -2147024809;
      _DbgPrintMessage(8, "Static channel name too long");
      goto LABEL_75;
    }
  }
  if ( (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "Creating virtual channel %s on session %d options 0x%08x", a3, a2, a4);
  if ( !(unsigned int)_o__stricmp(a3, "railenc") )
  {
    v13 = AccessCheckForRailEncVC(a2);
    v9 = v13;
    if ( v13 < 0 )
    {
      _DbgPrintMessage(8, "AccessCheckForRailEncVC failed: 0x%x in %s", (unsigned int)v13, "RpcCreateVirtualChannel");
      goto LABEL_75;
    }
  }
  v14 = RCMRpcPrologueEx(a2, 8u, 1u, &v40, 0, &TokenHandle);
  v9 = v14;
  if ( v14 < 0 )
  {
    if ( v14 != -2147022646 )
      v11 = 4;
    _DbgPrintMessage(v11, "RCMRpcPrologue failed: 0x%x", (unsigned int)v14);
    goto LABEL_23;
  }
  v16 = (**(__int64 (__fastcall ***)(struct ITerminal *, __int64 *, __int64 *))v40)(v40, qword_1800D7370, &v36);
  v9 = v16;
  if ( v16 < 0 )
  {
    _DbgPrintMessage(4, "QI( IRemoteTerminal ) failed: 0x%x in %s", (unsigned int)v16, "RpcCreateVirtualChannel");
    goto LABEL_23;
  }
  v17 = 0;
  if ( (a4 & 1) != 0 )
  {
    v15 = TokenHandle;
    if ( TokenHandle )
    {
      InstanceOfSessionManager = RpcRevertToSelf();
      v19 = InstanceOfSessionManager < 0;
      if ( InstanceOfSessionManager > 0 )
      {
        InstanceOfSessionManager = (unsigned __int16)InstanceOfSessionManager | 0x80070000;
        v19 = InstanceOfSessionManager < 0;
      }
      if ( v19 )
      {
        v20 = "RpcRevertToSelf before ptrRemoteTerminal->CreateDynamicVirtualChannel failed: 0x%x in %s";
        goto LABEL_69;
      }
      v15 = 0;
      v17 = 1;
    }
    InstanceOfSessionManager = (*(__int64 (__fastcall **)(__int64, const char *, _QWORD, _QWORD, unsigned int, void **))(*(_QWORD *)v36 + 280LL))(
                                 v36,
                                 a3,
                                 (v37 >> 1) & 3,
                                 (v37 >> 3) & 1,
                                 (v37 >> 1) & 0xFFF8,
                                 &v35);
    v9 = InstanceOfSessionManager;
    if ( InstanceOfSessionManager < 0 )
    {
      v20 = "ptrRemoteTerminal->CreateDynamicVirtualChannel failed: 0x%x in %s";
      goto LABEL_69;
    }
    if ( v17 )
    {
      InstanceOfSessionManager = RpcImpersonateClient(0);
      v21 = InstanceOfSessionManager < 0;
      if ( InstanceOfSessionManager > 0 )
      {
        InstanceOfSessionManager = (unsigned __int16)InstanceOfSessionManager | 0x80070000;
        v21 = InstanceOfSessionManager < 0;
      }
      if ( v21 )
      {
LABEL_40:
        v20 = "RpcImpersonateClient failed: 0x%x in %s";
        goto LABEL_69;
      }
      v15 = 1;
    }
  }
  else
  {
    v22 = (*(__int64 (__fastcall **)(__int64, const char *, void **))(*(_QWORD *)v36 + 272LL))(v36, a3, &v35);
    v9 = v22;
    if ( v22 < 0 )
    {
      _DbgPrintMessage(
        8,
        "ptrRemoteTerminal->CreateStaticVirtualChannel failed: 0x%x in %s",
        (unsigned int)v22,
        "RpcCreateVirtualChannel");
LABEL_23:
      v15 = TokenHandle;
      goto LABEL_70;
    }
    v15 = TokenHandle;
  }
  v23 = I_RpcBindingInqLocalClientPID(0, &Pid);
  v9 = v23;
  if ( v23 > 0 )
    v9 = (unsigned __int16)v23 | 0x80070000;
  if ( v9 < 0 )
  {
    _DbgPrintMessage(8, "I_RpcBindingInqLocalClientPID failed: 0x%x in %s", (unsigned int)v9, "RpcCreateVirtualChannel");
    goto LABEL_70;
  }
  if ( (a4 & 1) != 0 )
  {
    if ( v15 )
    {
      InstanceOfSessionManager = RpcRevertToSelf();
      v24 = InstanceOfSessionManager < 0;
      if ( InstanceOfSessionManager > 0 )
      {
        InstanceOfSessionManager = (unsigned __int16)InstanceOfSessionManager | 0x80070000;
        v24 = InstanceOfSessionManager < 0;
      }
      if ( v24 )
      {
        v20 = "RpcRevertToSelf before DuplicateHandleInPidKMode failed: 0x%x in %s";
        goto LABEL_69;
      }
      v15 = 0;
      v17 = 1;
    }
    InstanceOfSessionManager = DuplicateHandleInPidKMode(v35, Pid, v41);
    v9 = InstanceOfSessionManager;
    if ( InstanceOfSessionManager < 0 )
    {
      v20 = "DuplicateHandleInPidKMode failed: 0x%x in %s";
      goto LABEL_69;
    }
    if ( !v17 )
      goto LABEL_70;
    InstanceOfSessionManager = RpcImpersonateClient(0);
    v25 = InstanceOfSessionManager < 0;
    if ( InstanceOfSessionManager > 0 )
    {
      InstanceOfSessionManager = (unsigned __int16)InstanceOfSessionManager | 0x80070000;
      v25 = InstanceOfSessionManager < 0;
    }
    if ( !v25 )
    {
      v15 = 1;
      goto LABEL_70;
    }
    goto LABEL_40;
  }
  InstanceOfSessionManager = CUtils::GetInstanceOfSessionManager(&v39);
  v9 = InstanceOfSessionManager;
  if ( InstanceOfSessionManager >= 0 )
  {
    InstanceOfSessionManager = (*(__int64 (__fastcall **)(struct ISessionManager *, __int64 *))(*(_QWORD *)v39 + 48LL))(
                                 v39,
                                 &v38);
    v9 = InstanceOfSessionManager;
    if ( InstanceOfSessionManager >= 0 )
    {
      v26 = v38;
      v27 = Pid;
      v28 = *(__int64 (__fastcall **)(__int64, void *, _QWORD, void **, unsigned int))(*(_QWORD *)v38 + 24LL);
      CurrentProcessId = GetCurrentProcessId();
      InstanceOfSessionManager = v28(v26, v35, CurrentProcessId, v41, v27);
      v9 = InstanceOfSessionManager;
      if ( InstanceOfSessionManager >= 0 )
        goto LABEL_70;
      v20 = "Mgr->DuplicateHandleInPid failed: 0x%x in %s";
    }
    else
    {
      v20 = "GetInstanceOfRestrictedCalls failed: 0x%x in %s";
    }
  }
  else
  {
    v20 = "GetInstanceOfSessionManager failed: 0x%x in %s";
  }
LABEL_69:
  _DbgPrintMessage(8, v20, (unsigned int)InstanceOfSessionManager, "RpcCreateVirtualChannel");
LABEL_70:
  if ( v15 )
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
      v9 = -2147024891;
    }
  }
LABEL_75:
  EtwEventActivityIdControl(2, &v43);
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v44);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v38);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v39);
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&v35);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v36);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v40);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18005d970  mov     [rsp-8+arg_0], rbx
0x18005d975  push    rbp
0x18005d976  push    rsi
0x18005d977  push    rdi
0x18005d978  push    r12
0x18005d97a  push    r13
0x18005d97c  push    r14
0x18005d97e  push    r15
0x18005d980  lea     rbp, [rsp-200h]
0x18005d988  sub     rsp, 300h
0x18005d98f  mov     rax, cs:__security_cookie
0x18005d996  xor     rax, rsp
0x18005d999  mov     [rbp+230h+var_40], rax
0x18005d9a0  mov     rdi, [rbp+230h+arg_20]
0x18005d9a7  lea     r13, aRpccreatevirtu; "RpcCreateVirtualChannel"
0x18005d9ae  xor     r15d, r15d
0x18005d9b1  mov     [rsp+330h+var_2D8], r9d
0x18005d9b6  mov     r12, r8
0x18005d9b9  mov     [rsp+330h+var_2B8], rdi
0x18005d9be  mov     esi, edx
0x18005d9c0  mov     [rsp+330h+var_2F0], r15d
0x18005d9c5  mov     r8, r13; char *
0x18005d9c8  mov     [rsp+330h+var_2C0], r15
0x18005d9cd  xor     edx, edx; int
0x18005d9cf  mov     [rsp+330h+var_2E0], r15
0x18005d9d4  lea     rcx, [rbp+230h+var_290]; this
0x18005d9d8  mov     [rsp+330h+var_2E8], r15
0x18005d9dd  mov     r14d, r9d
0x18005d9e0  mov     [rsp+330h+Pid], r15d
0x18005d9e5  mov     [rsp+330h+var_2C8], r15
0x18005d9ea  mov     [rsp+330h+var_2D0], r15
0x18005d9ef  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18005d9f4  xorps   xmm0, xmm0
0x18005d9f7  lea     rcx, [rbp+230h+pguid]; pguid
0x18005d9fb  mov     edx, 0F4600000h; unsigned int
0x18005da00  movups  xmmword ptr [rbp+230h+pguid.Data1], xmm0
0x18005da04  call    ?GenerateConstrainedGuid@@YAJPEAU_GUID@@K@Z; GenerateConstrainedGuid(_GUID *,ulong)
0x18005da09  movaps  xmm0, xmmword ptr [rbp+230h+pguid.Data1]
0x18005da0d  lea     rdx, [rbp+230h+var_2A0]
0x18005da11  lea     ecx, [r15+4]
0x18005da15  movdqa  [rbp+230h+var_2A0], xmm0
0x18005da1a  mov     ebx, eax
0x18005da1c  call    cs:__imp_EtwEventActivityIdControl
0x18005da22  test    ebx, ebx
0x18005da24  jns     short loc_18005DA42
0x18005da26  mov     r9, r13
0x18005da29  lea     rdx, aGenerateconstr; "GenerateConstrainedGuid failed: 0x%x in"...
0x18005da30  mov     r8d, ebx
0x18005da33  mov     ecx, 8; int
0x18005da38  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005da3d  jmp     loc_18005DE11
0x18005da42  test    r12, r12
0x18005da45  jnz     short loc_18005DA6C
0x18005da47  lea     r8, aEndpointname; "EndpointName"
0x18005da4e  mov     r9, r13
0x18005da51  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18005da58  mov     ecx, 8; int
0x18005da5d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005da62  mov     ebx, 80070057h
0x18005da67  jmp     loc_18005DE11
0x18005da6c  test    rdi, rdi
0x18005da6f  jnz     short loc_18005DA7A
0x18005da71  lea     r8, aPhchannel; "phChannel"
0x18005da78  jmp     short loc_18005DA4E
0x18005da7a  mov     r13d, r14d
0x18005da7d  mov     edi, 1
0x18005da82  and     r13d, edi
0x18005da85  jnz     short loc_18005DAB5
0x18005da87  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005da8b  inc     rax
0x18005da8e  cmp     [r12+rax], r15b
0x18005da92  jnz     short loc_18005DA8B
0x18005da94  cmp     rax, 7
0x18005da98  jbe     short loc_18005DAB5
0x18005da9a  lea     rdx, aStaticChannelN; "Static channel name too long"
0x18005daa1  mov     ecx, 8; int
0x18005daa6  mov     ebx, 80070057h
0x18005daab  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005dab0  jmp     loc_18005DE11
0x18005dab5  test    byte ptr cs:?g_DebugTraceComponent@@3KA, dil; ulong g_DebugTraceComponent
0x18005dabc  jz      short loc_18005DADA
0x18005dabe  mov     r9d, esi
0x18005dac1  mov     dword ptr [rsp+330h+var_310], r14d
0x18005dac6  mov     r8, r12
0x18005dac9  lea     rdx, aCreatingVirtua; "Creating virtual channel %s on session "...
0x18005dad0  mov     ecx, 2; int
0x18005dad5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005dada  lea     rdx, aRailenc; "railenc"
0x18005dae1  mov     rcx, r12
0x18005dae4  call    cs:__imp__o__stricmp
0x18005daea  test    eax, eax
0x18005daec  jnz     short loc_18005DB11
0x18005daee  mov     ecx, esi; unsigned int
0x18005daf0  call    ?AccessCheckForRailEncVC@@YAJK@Z; AccessCheckForRailEncVC(ulong)
0x18005daf5  mov     ebx, eax
0x18005daf7  test    eax, eax
0x18005daf9  jns     short loc_18005DB11
0x18005dafb  lea     r9, aRpccreatevirtu; "RpcCreateVirtualChannel"
0x18005db02  mov     r8d, eax
0x18005db05  lea     rdx, aAccesscheckfor; "AccessCheckForRailEncVC failed: 0x%x in"...
0x18005db0c  jmp     loc_18005DA33
0x18005db11  lea     rax, [rsp+330h+var_2F0]
0x18005db16  mov     r14d, 8
0x18005db1c  mov     [rsp+330h+TokenHandle], rax; TokenHandle
0x18005db21  lea     r9, [rsp+330h+var_2C0]; struct ITerminal **
0x18005db26  mov     edx, r14d; unsigned int
0x18005db29  mov     [rsp+330h+var_310], r15; struct ITSSession **
0x18005db2e  mov     r8d, edi; int
0x18005db31  mov     ecx, esi; unsigned int
0x18005db33  call    ?RCMRpcPrologueEx@@YAJKKHPEAPEAUITerminal@@PEAPEAUITSSession@@PEAH@Z; RCMRpcPrologueEx(ulong,ulong,int,ITerminal * *,ITSSession * *,int *)
0x18005db38  mov     ebx, eax
0x18005db3a  test    eax, eax
0x18005db3c  jns     short loc_18005DB65
0x18005db3e  lea     ecx, [r14-4]
0x18005db42  cmp     eax, 800708CAh
0x18005db47  mov     r8d, eax
0x18005db4a  lea     rdx, aRcmrpcprologue; "RCMRpcPrologue failed: 0x%x"
0x18005db51  cmovnz  edi, ecx
0x18005db54  mov     ecx, edi; int
0x18005db56  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005db5b  mov     r15d, [rsp+330h+var_2F0]
0x18005db60  jmp     loc_18005DDDF
0x18005db65  mov     rcx, [rsp+330h+var_2C0]
0x18005db6a  lea     r8, [rsp+330h+var_2E0]
0x18005db6f  lea     rdx, qword_1800D7370
0x18005db76  mov     rax, [rcx]
0x18005db79  mov     rax, [rax]
0x18005db7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005db81  mov     ebx, eax
0x18005db83  test    eax, eax
0x18005db85  jns     short loc_18005DBA4
0x18005db87  lea     rdx, aQiIremotetermi_0; "QI( IRemoteTerminal ) failed: 0x%x in %"...
0x18005db8e  mov     ecx, 4; int
0x18005db93  mov     r8d, eax
0x18005db96  lea     r9, aRpccreatevirtu; "RpcCreateVirtualChannel"
0x18005db9d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005dba2  jmp     short loc_18005DB5B
0x18005dba4  mov     esi, r15d
0x18005dba7  test    r13d, r13d
0x18005dbaa  jz      loc_18005DC69
0x18005dbb0  mov     r15d, [rsp+330h+var_2F0]
0x18005dbb5  test    r15d, r15d
0x18005dbb8  jz      short loc_18005DBE1
0x18005dbba  call    cs:__imp_RpcRevertToSelf
0x18005dbc0  test    eax, eax
0x18005dbc2  jle     short loc_18005DBCE
0x18005dbc4  movzx   eax, ax
0x18005dbc7  or      eax, 80070000h
0x18005dbcc  test    eax, eax
0x18005dbce  jns     short loc_18005DBDC
0x18005dbd0  lea     rdx, aRpcreverttosel; "RpcRevertToSelf before ptrRemoteTermina"...
0x18005dbd7  jmp     loc_18005DDCD
0x18005dbdc  xor     r15d, r15d
0x18005dbdf  mov     esi, edi
0x18005dbe1  mov     edx, [rsp+330h+var_2D8]
0x18005dbe5  lea     r9, [rsp+330h+var_2E8]
0x18005dbea  mov     rcx, [rsp+330h+var_2E0]
0x18005dbef  mov     r10d, edx
0x18005dbf2  shr     r10d, 1
0x18005dbf5  mov     r8d, r10d
0x18005dbf8  shr     edx, 3
0x18005dbfb  and     r8d, 0FFF8h
0x18005dc02  mov     [rsp+330h+TokenHandle], r9
0x18005dc07  mov     rax, [rcx]
0x18005dc0a  and     edx, edi
0x18005dc0c  and     r10d, 3
0x18005dc10  mov     dword ptr [rsp+330h+var_310], r8d
0x18005dc15  mov     r9d, edx
0x18005dc18  mov     r8d, r10d
0x18005dc1b  mov     rdx, r12
0x18005dc1e  mov     rax, [rax+118h]
0x18005dc25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dc2a  mov     ebx, eax
0x18005dc2c  test    eax, eax
0x18005dc2e  jns     short loc_18005DC3C
0x18005dc30  lea     rdx, aPtrremotetermi_3; "ptrRemoteTerminal->CreateDynamicVirtual"...
0x18005dc37  jmp     loc_18005DDCD
0x18005dc3c  test    esi, esi
0x18005dc3e  jz      short loc_18005DC9F
0x18005dc40  xor     ecx, ecx; BindingHandle
0x18005dc42  call    cs:__imp_RpcImpersonateClient
0x18005dc48  test    eax, eax
0x18005dc4a  jle     short loc_18005DC56
0x18005dc4c  movzx   eax, ax
0x18005dc4f  or      eax, 80070000h
0x18005dc54  test    eax, eax
0x18005dc56  jns     short loc_18005DC64
0x18005dc58  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x18005dc5f  jmp     loc_18005DDCD
0x18005dc64  mov     r15d, edi
0x18005dc67  jmp     short loc_18005DC9F
0x18005dc69  mov     rcx, [rsp+330h+var_2E0]
0x18005dc6e  lea     r8, [rsp+330h+var_2E8]
0x18005dc73  mov     rdx, r12
0x18005dc76  mov     rax, [rcx]
0x18005dc79  mov     rax, [rax+110h]
0x18005dc80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dc85  mov     ebx, eax
0x18005dc87  test    eax, eax
0x18005dc89  jns     short loc_18005DC9A
0x18005dc8b  lea     rdx, aPtrremotetermi_11; "ptrRemoteTerminal->CreateStaticVirtualC"...
0x18005dc92  mov     ecx, r14d
0x18005dc95  jmp     loc_18005DB93
0x18005dc9a  mov     r15d, [rsp+330h+var_2F0]
0x18005dc9f  lea     rdx, [rsp+330h+Pid]; Pid
0x18005dca4  xor     ecx, ecx; Binding
0x18005dca6  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18005dcac  mov     ebx, eax
0x18005dcae  test    eax, eax
0x18005dcb0  jle     short loc_18005DCBB
0x18005dcb2  movzx   ebx, ax
0x18005dcb5  or      ebx, 80070000h
0x18005dcbb  test    ebx, ebx
0x18005dcbd  jns     short loc_18005DCCE
0x18005dcbf  mov     r8d, ebx
0x18005dcc2  lea     rdx, aIRpcbindinginq; "I_RpcBindingInqLocalClientPID failed: 0"...
0x18005dcc9  jmp     loc_18005DDD0
0x18005dcce  test    r13d, r13d
0x18005dcd1  jz      short loc_18005DD50
0x18005dcd3  test    r15d, r15d
0x18005dcd6  jz      short loc_18005DCFF
0x18005dcd8  call    cs:__imp_RpcRevertToSelf
0x18005dcde  test    eax, eax
0x18005dce0  jle     short loc_18005DCEC
0x18005dce2  movzx   eax, ax
0x18005dce5  or      eax, 80070000h
0x18005dcea  test    eax, eax
0x18005dcec  jns     short loc_18005DCFA
0x18005dcee  lea     rdx, aRpcreverttosel_4; "RpcRevertToSelf before DuplicateHandleI"...
0x18005dcf5  jmp     loc_18005DDCD
0x18005dcfa  xor     r15d, r15d
0x18005dcfd  mov     esi, edi
0x18005dcff  mov     r8, [rsp+330h+var_2B8]; void **
0x18005dd04  mov     edx, [rsp+330h+Pid]; unsigned int
0x18005dd08  mov     rcx, [rsp+330h+var_2E8]; void *
0x18005dd0d  call    ?DuplicateHandleInPidKMode@@YAJPEAXKPEAPEAX@Z; DuplicateHandleInPidKMode(void *,ulong,void * *)
0x18005dd12  mov     ebx, eax
0x18005dd14  test    eax, eax
0x18005dd16  jns     short loc_18005DD24
0x18005dd18  lea     rdx, aDuplicatehandl_0; "DuplicateHandleInPidKMode failed: 0x%x "...
0x18005dd1f  jmp     loc_18005DDCD
0x18005dd24  test    esi, esi
0x18005dd26  jz      loc_18005DDDF
0x18005dd2c  xor     ecx, ecx; BindingHandle
0x18005dd2e  call    cs:__imp_RpcImpersonateClient
0x18005dd34  test    eax, eax
0x18005dd36  jle     short loc_18005DD42
0x18005dd38  movzx   eax, ax
0x18005dd3b  or      eax, 80070000h
0x18005dd40  test    eax, eax
0x18005dd42  js      loc_18005DC58
0x18005dd48  mov     r15d, edi
0x18005dd4b  jmp     loc_18005DDDF
0x18005dd50  lea     rcx, [rsp+330h+var_2C8]; struct ISessionManager **
0x18005dd55  call    ?GetInstanceOfSessionManager@CUtils@@SAJPEAPEAUISessionManager@@@Z; CUtils::GetInstanceOfSessionManager(ISessionManager * *)
0x18005dd5a  mov     ebx, eax
0x18005dd5c  test    eax, eax
0x18005dd5e  jns     short loc_18005DD69
0x18005dd60  lea     rdx, aGetinstanceofs; "GetInstanceOfSessionManager failed: 0x%"...
0x18005dd67  jmp     short loc_18005DDCD
0x18005dd69  mov     rcx, [rsp+330h+var_2C8]
0x18005dd6e  lea     rdx, [rsp+330h+var_2D0]
0x18005dd73  mov     rax, [rcx]
0x18005dd76  mov     rax, [rax+30h]
0x18005dd7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dd7f  mov     ebx, eax
0x18005dd81  test    eax, eax
0x18005dd83  jns     short loc_18005DD8E
0x18005dd85  lea     rdx, aGetinstanceofr_4; "GetInstanceOfRestrictedCalls failed: 0x"...
0x18005dd8c  jmp     short loc_18005DDCD
0x18005dd8e  mov     rsi, [rsp+330h+var_2D0]
0x18005dd93  mov     ebx, [rsp+330h+Pid]
0x18005dd97  mov     rax, [rsi]
0x18005dd9a  mov     rdi, [rax+18h]
0x18005dd9e  call    cs:__imp_GetCurrentProcessId
0x18005dda4  mov     r9, [rsp+330h+var_2B8]
0x18005dda9  mov     rcx, rsi
0x18005ddac  mov     rdx, [rsp+330h+var_2E8]
0x18005ddb1  mov     r8d, eax
0x18005ddb4  mov     rax, rdi
0x18005ddb7  mov     dword ptr [rsp+330h+var_310], ebx
0x18005ddbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ddc0  mov     ebx, eax
0x18005ddc2  test    eax, eax
0x18005ddc4  jns     short loc_18005DDDF
0x18005ddc6  lea     rdx, aMgrDuplicateha; "Mgr->DuplicateHandleInPid failed: 0x%x "...
0x18005ddcd  mov     r8d, eax
0x18005ddd0  lea     r9, aRpccreatevirtu; "RpcCreateVirtualChannel"
0x18005ddd7  mov     ecx, r14d; int
0x18005ddda  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005dddf  test    r15d, r15d
0x18005dde2  jz      short loc_18005DE11
0x18005dde4  call    cs:__imp_RpcRevertToSelf
0x18005ddea  test    eax, eax
0x18005ddec  jle     short loc_18005DDF8
0x18005ddee  movzx   eax, ax
0x18005ddf1  or      eax, 80070000h
0x18005ddf6  test    eax, eax
0x18005ddf8  jns     short loc_18005DE11
0x18005ddfa  mov     r8d, eax
  ... truncated ...
```
