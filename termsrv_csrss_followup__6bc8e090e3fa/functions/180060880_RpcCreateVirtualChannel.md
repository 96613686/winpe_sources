# RpcCreateVirtualChannel

- ea: `0x180060880`
- end: `0x180060de1`
- name: `RpcCreateVirtualChannel`
- size: `1377`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180060df0`

## callees

- `0x180008920`
- `0x180009940`
- `0x18000ba50`
- `0x18000f760`
- `0x180013948`
- `0x1800139c0`
- `0x180015020`
- `0x180015d48`
- `0x180029420`
- `0x18002c17c`
- `0x180033f60`
- `0x18005ec90`
- `0x180060880`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180060a02`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180060a02`
- `ntdll!EtwEventActivityIdControl` at `0x180060d6d`
- `ntdll!EtwEventActivityIdControl` at `0x180060d6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180060ce5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180060ce5`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180060bda`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180060bda`
- `RPCRT4!RpcRevertToSelf` at `0x180060ad9`
- `RPCRT4!RpcRevertToSelf` at `0x180060c17`
- `RPCRT4!RpcRevertToSelf` at `0x180060d31`
- `RPCRT4!RpcRevertToSelf` at `0x180060ad9`
- `RPCRT4!RpcRevertToSelf` at `0x180060c17`
- `RPCRT4!RpcRevertToSelf` at `0x180060d31`
- `RPCRT4!RpcImpersonateClient` at `0x180060b69`
- `RPCRT4!RpcImpersonateClient` at `0x180060c72`
- `RPCRT4!RpcImpersonateClient` at `0x180060b69`
- `RPCRT4!RpcImpersonateClient` at `0x180060c72`

## string_xrefs

- `0x180060b85`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x1800608b7`: `RpcCreateVirtualChannel`
- `0x180060bb8`: `RpcCreateVirtualChannel`
- `0x180060d1d`: `RpcCreateVirtualChannel`
- `0x180060a23`: `AccessCheckForRailEncVC failed: 0x%x in %s`
- `0x180060af5`: `RpcRevertToSelf before ptrRemoteTerminal->CreateDynamicVirtualChannel failed: 0x%x in %s`
- `0x180060b56`: `ptrRemoteTerminal->CreateDynamicVirtualChannel failed: 0x%x in %s`
- `0x180060bc2`: `ptrRemoteTerminal->CreateStaticVirtualChannel failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall RpcCreateVirtualChannel(__int64 a1, unsigned int a2, const char *a3, int a4, void **a5)
{
  signed int v8; // ebx
  const char *v9; // r8
  int v10; // edi
  unsigned __int64 v11; // rax
  int v12; // eax
  int v13; // eax
  int v14; // r15d
  int v15; // eax
  int v16; // r12d
  int InstanceOfSessionManager; // eax
  bool v18; // sf
  const char *v19; // rdx
  bool v20; // sf
  int v21; // eax
  RPC_STATUS v22; // eax
  bool v23; // sf
  bool v24; // sf
  __int64 v25; // rsi
  unsigned int v26; // ebx
  __int64 (__fastcall *v27)(__int64, void *, _QWORD, void **, unsigned int); // rdi
  DWORD CurrentProcessId; // eax
  int v29; // eax
  bool v30; // sf
  int TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int Pid; // [rsp+44h] [rbp-BCh] BYREF
  void *v34; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v36; // [rsp+58h] [rbp-A8h]
  __int64 v37; // [rsp+60h] [rbp-A0h] BYREF
  struct ISessionManager *v38; // [rsp+68h] [rbp-98h] BYREF
  struct ITerminal *v39; // [rsp+70h] [rbp-90h] BYREF
  void **v40; // [rsp+78h] [rbp-88h]
  GUID pguid; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v42[16]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v43[592]; // [rsp+A0h] [rbp-60h] BYREF

  v36 = a4;
  v40 = a5;
  TokenHandle = 0;
  v39 = 0;
  v35 = 0;
  v34 = 0;
  Pid = 0;
  v38 = 0;
  v37 = 0;
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v43, 0, "RpcCreateVirtualChannel");
  pguid = 0;
  v8 = GenerateConstrainedGuid(&pguid, 0xF4600000);
  CAutoSetThreadActivityId::CAutoSetThreadActivityId((CAutoSetThreadActivityId *)v42, &pguid);
  if ( v8 < 0 )
  {
    _DbgPrintMessage(8, "GenerateConstrainedGuid failed: 0x%x in %s", (unsigned int)v8, "RpcCreateVirtualChannel");
    goto LABEL_75;
  }
  if ( !a3 )
  {
    v9 = "EndpointName";
LABEL_6:
    _DbgPrintMessage(8, "Missing paramter %s in %s", v9, "RpcCreateVirtualChannel");
    v8 = -2147024809;
    goto LABEL_75;
  }
  if ( !a5 )
  {
    v9 = "phChannel";
    goto LABEL_6;
  }
  v10 = 1;
  if ( (a4 & 1) == 0 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a3[v11] );
    if ( v11 > 7 )
    {
      v8 = -2147024809;
      _DbgPrintMessage(8, "Static channel name too long");
      goto LABEL_75;
    }
  }
  if ( (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "Creating virtual channel %s on session %d options 0x%08x", a3, a2, a4);
  if ( !(unsigned int)_o__stricmp(a3, "railenc") )
  {
    v12 = AccessCheckForRailEncVC(a2);
    v8 = v12;
    if ( v12 < 0 )
    {
      _DbgPrintMessage(8, "AccessCheckForRailEncVC failed: 0x%x in %s", (unsigned int)v12, "RpcCreateVirtualChannel");
      goto LABEL_75;
    }
  }
  v13 = RCMRpcPrologueEx(a2, 8u, 1u, &v39, 0, &TokenHandle);
  v8 = v13;
  if ( v13 < 0 )
  {
    if ( v13 != -2147022646 )
      v10 = 4;
    _DbgPrintMessage(v10, "RCMRpcPrologue failed: 0x%x", (unsigned int)v13);
    goto LABEL_23;
  }
  v15 = (**(__int64 (__fastcall ***)(struct ITerminal *, __int64 *, __int64 *))v39)(v39, qword_1800DD390, &v35);
  v8 = v15;
  if ( v15 < 0 )
  {
    _DbgPrintMessage(4, "QI( IRemoteTerminal ) failed: 0x%x in %s", (unsigned int)v15, "RpcCreateVirtualChannel");
    goto LABEL_23;
  }
  v16 = 0;
  if ( (a4 & 1) != 0 )
  {
    v14 = TokenHandle;
    if ( TokenHandle )
    {
      InstanceOfSessionManager = RpcRevertToSelf();
      v18 = InstanceOfSessionManager < 0;
      if ( InstanceOfSessionManager > 0 )
      {
        InstanceOfSessionManager = (unsigned __int16)InstanceOfSessionManager | 0x80070000;
        v18 = InstanceOfSessionManager < 0;
      }
      if ( v18 )
      {
        v19 = "RpcRevertToSelf before ptrRemoteTerminal->CreateDynamicVirtualChannel failed: 0x%x in %s";
        goto LABEL_69;
      }
      v14 = 0;
      v16 = 1;
    }
    InstanceOfSessionManager = (*(__int64 (__fastcall **)(__int64, const char *, _QWORD, _QWORD, unsigned int, void **))(*(_QWORD *)v35 + 280LL))(
                                 v35,
                                 a3,
                                 (v36 >> 1) & 3,
                                 (v36 >> 3) & 1,
                                 (v36 >> 1) & 0xFFF8,
                                 &v34);
    v8 = InstanceOfSessionManager;
    if ( InstanceOfSessionManager < 0 )
    {
      v19 = "ptrRemoteTerminal->CreateDynamicVirtualChannel failed: 0x%x in %s";
      goto LABEL_69;
    }
    if ( v16 )
    {
      InstanceOfSessionManager = RpcImpersonateClient(0);
      v20 = InstanceOfSessionManager < 0;
      if ( InstanceOfSessionManager > 0 )
      {
        InstanceOfSessionManager = (unsigned __int16)InstanceOfSessionManager | 0x80070000;
        v20 = InstanceOfSessionManager < 0;
      }
      if ( v20 )
      {
LABEL_40:
        v19 = "RpcImpersonateClient failed: 0x%x in %s";
        goto LABEL_69;
      }
      v14 = 1;
    }
  }
  else
  {
    v21 = (*(__int64 (__fastcall **)(__int64, const char *, void **))(*(_QWORD *)v35 + 272LL))(v35, a3, &v34);
    v8 = v21;
    if ( v21 < 0 )
    {
      _DbgPrintMessage(
        8,
        "ptrRemoteTerminal->CreateStaticVirtualChannel failed: 0x%x in %s",
        (unsigned int)v21,
        "RpcCreateVirtualChannel");
LABEL_23:
      v14 = TokenHandle;
      goto LABEL_70;
    }
    v14 = TokenHandle;
  }
  v22 = I_RpcBindingInqLocalClientPID(0, &Pid);
  v8 = v22;
  if ( v22 > 0 )
    v8 = (unsigned __int16)v22 | 0x80070000;
  if ( v8 < 0 )
  {
    _DbgPrintMessage(8, "I_RpcBindingInqLocalClientPID failed: 0x%x in %s", (unsigned int)v8, "RpcCreateVirtualChannel");
    goto LABEL_70;
  }
  if ( (a4 & 1) != 0 )
  {
    if ( v14 )
    {
      InstanceOfSessionManager = RpcRevertToSelf();
      v23 = InstanceOfSessionManager < 0;
      if ( InstanceOfSessionManager > 0 )
      {
        InstanceOfSessionManager = (unsigned __int16)InstanceOfSessionManager | 0x80070000;
        v23 = InstanceOfSessionManager < 0;
      }
      if ( v23 )
      {
        v19 = "RpcRevertToSelf before DuplicateHandleInPidKMode failed: 0x%x in %s";
        goto LABEL_69;
      }
      v14 = 0;
      v16 = 1;
    }
    InstanceOfSessionManager = DuplicateHandleInPidKMode(v34, Pid, v40);
    v8 = InstanceOfSessionManager;
    if ( InstanceOfSessionManager < 0 )
    {
      v19 = "DuplicateHandleInPidKMode failed: 0x%x in %s";
      goto LABEL_69;
    }
    if ( !v16 )
      goto LABEL_70;
    InstanceOfSessionManager = RpcImpersonateClient(0);
    v24 = InstanceOfSessionManager < 0;
    if ( InstanceOfSessionManager > 0 )
    {
      InstanceOfSessionManager = (unsigned __int16)InstanceOfSessionManager | 0x80070000;
      v24 = InstanceOfSessionManager < 0;
    }
    if ( !v24 )
    {
      v14 = 1;
      goto LABEL_70;
    }
    goto LABEL_40;
  }
  InstanceOfSessionManager = CUtils::GetInstanceOfSessionManager(&v38);
  v8 = InstanceOfSessionManager;
  if ( InstanceOfSessionManager >= 0 )
  {
    InstanceOfSessionManager = (*(__int64 (__fastcall **)(struct ISessionManager *, __int64 *))(*(_QWORD *)v38 + 48LL))(
                                 v38,
                                 &v37);
    v8 = InstanceOfSessionManager;
    if ( InstanceOfSessionManager >= 0 )
    {
      v25 = v37;
      v26 = Pid;
      v27 = *(__int64 (__fastcall **)(__int64, void *, _QWORD, void **, unsigned int))(*(_QWORD *)v37 + 24LL);
      CurrentProcessId = GetCurrentProcessId();
      InstanceOfSessionManager = v27(v25, v34, CurrentProcessId, v40, v26);
      v8 = InstanceOfSessionManager;
      if ( InstanceOfSessionManager >= 0 )
        goto LABEL_70;
      v19 = "Mgr->DuplicateHandleInPid failed: 0x%x in %s";
    }
    else
    {
      v19 = "GetInstanceOfRestrictedCalls failed: 0x%x in %s";
    }
  }
  else
  {
    v19 = "GetInstanceOfSessionManager failed: 0x%x in %s";
  }
LABEL_69:
  _DbgPrintMessage(8, v19, (unsigned int)InstanceOfSessionManager, "RpcCreateVirtualChannel");
LABEL_70:
  if ( v14 )
  {
    v29 = RpcRevertToSelf();
    v30 = v29 < 0;
    if ( v29 > 0 )
    {
      v29 = (unsigned __int16)v29 | 0x80070000;
      v30 = v29 < 0;
    }
    if ( v30 )
    {
      _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v29);
      v8 = -2147024891;
    }
  }
LABEL_75:
  EtwEventActivityIdControl(2, v42);
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v43);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v37);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v38);
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&v34);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v35);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v39);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180060880  mov     [rsp-8+arg_0], rbx
0x180060885  push    rbp
0x180060886  push    rsi
0x180060887  push    rdi
0x180060888  push    r12
0x18006088a  push    r13
0x18006088c  push    r14
0x18006088e  push    r15
0x180060890  lea     rbp, [rsp-200h]
0x180060898  sub     rsp, 300h
0x18006089f  mov     rax, cs:__security_cookie
0x1800608a6  xor     rax, rsp
0x1800608a9  mov     [rbp+230h+var_40], rax
0x1800608b0  mov     rdi, [rbp+230h+arg_20]
0x1800608b7  lea     r12, aRpccreatevirtu; "RpcCreateVirtualChannel"
0x1800608be  mov     rsi, r8
0x1800608c1  mov     [rsp+330h+var_2D8], r9d
0x1800608c6  mov     r15d, edx
0x1800608c9  mov     [rsp+330h+var_2B8], rdi
0x1800608ce  mov     r8, r12; char *
0x1800608d1  mov     [rsp+330h+var_2F0], 0
0x1800608d9  xor     edx, edx; int
0x1800608db  mov     [rsp+330h+var_2C0], 0
0x1800608e4  lea     rcx, [rbp+230h+var_290]; this
0x1800608e8  mov     [rsp+330h+var_2E0], 0
0x1800608f1  mov     r14d, r9d
0x1800608f4  mov     [rsp+330h+var_2E8], 0
0x1800608fd  mov     [rsp+330h+Pid], 0
0x180060905  mov     [rsp+330h+var_2C8], 0
0x18006090e  mov     [rsp+330h+var_2D0], 0
0x180060917  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18006091c  xorps   xmm0, xmm0
0x18006091f  lea     rcx, [rbp+230h+pguid]; pguid
0x180060923  mov     edx, 0F4600000h; unsigned int
0x180060928  movups  xmmword ptr [rbp+230h+pguid.Data1], xmm0
0x18006092c  call    ?GenerateConstrainedGuid@@YAJPEAU_GUID@@K@Z; GenerateConstrainedGuid(_GUID *,ulong)
0x180060931  lea     rdx, [rbp+230h+pguid]; struct _GUID *
0x180060935  mov     ebx, eax
0x180060937  lea     rcx, [rbp+230h+var_2A0]; this
0x18006093b  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x180060940  test    ebx, ebx
0x180060942  jns     short loc_180060960
0x180060944  mov     r8d, ebx
0x180060947  lea     rdx, aGenerateconstr; "GenerateConstrainedGuid failed: 0x%x in"...
0x18006094e  mov     r9, r12
0x180060951  mov     ecx, 8; int
0x180060956  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006095b  jmp     loc_180060D64
0x180060960  test    rsi, rsi
0x180060963  jnz     short loc_18006098A
0x180060965  lea     r8, aEndpointname; "EndpointName"
0x18006096c  mov     r9, r12
0x18006096f  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180060976  mov     ecx, 8; int
0x18006097b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180060980  mov     ebx, 80070057h
0x180060985  jmp     loc_180060D64
0x18006098a  test    rdi, rdi
0x18006098d  jnz     short loc_180060998
0x18006098f  lea     r8, aPhchannel; "phChannel"
0x180060996  jmp     short loc_18006096C
0x180060998  mov     r13d, r14d
0x18006099b  mov     edi, 1
0x1800609a0  and     r13d, edi
0x1800609a3  jnz     short loc_1800609D3
0x1800609a5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800609a9  inc     rax
0x1800609ac  cmp     byte ptr [rsi+rax], 0
0x1800609b0  jnz     short loc_1800609A9
0x1800609b2  cmp     rax, 7
0x1800609b6  jbe     short loc_1800609D3
0x1800609b8  lea     rdx, aStaticChannelN; "Static channel name too long"
0x1800609bf  mov     ecx, 8; int
0x1800609c4  mov     ebx, 80070057h
0x1800609c9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800609ce  jmp     loc_180060D64
0x1800609d3  test    byte ptr cs:?g_DebugTraceComponent@@3KA, dil; ulong g_DebugTraceComponent
0x1800609da  jz      short loc_1800609F8
0x1800609dc  mov     r9d, r15d
0x1800609df  mov     dword ptr [rsp+330h+var_310], r14d
0x1800609e4  mov     r8, rsi
0x1800609e7  lea     rdx, aCreatingVirtua; "Creating virtual channel %s on session "...
0x1800609ee  mov     ecx, 2; int
0x1800609f3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800609f8  lea     rdx, aRailenc; "railenc"
0x1800609ff  mov     rcx, rsi
0x180060a02  call    cs:__imp__o__stricmp
0x180060a09  nop     dword ptr [rax+rax+00h]
0x180060a0e  test    eax, eax
0x180060a10  jnz     short loc_180060A2F
0x180060a12  mov     ecx, r15d; unsigned int
0x180060a15  call    ?AccessCheckForRailEncVC@@YAJK@Z; AccessCheckForRailEncVC(ulong)
0x180060a1a  mov     ebx, eax
0x180060a1c  test    eax, eax
0x180060a1e  jns     short loc_180060A2F
0x180060a20  mov     r8d, eax
0x180060a23  lea     rdx, aAccesscheckfor; "AccessCheckForRailEncVC failed: 0x%x in"...
0x180060a2a  jmp     loc_18006094E
0x180060a2f  lea     rax, [rsp+330h+var_2F0]
0x180060a34  mov     r14d, 8
0x180060a3a  mov     [rsp+330h+TokenHandle], rax; TokenHandle
0x180060a3f  lea     r9, [rsp+330h+var_2C0]; struct ITerminal **
0x180060a44  mov     edx, r14d; unsigned int
0x180060a47  mov     [rsp+330h+var_310], 0; struct ITSSession **
0x180060a50  mov     r8d, edi; int
0x180060a53  mov     ecx, r15d; unsigned int
0x180060a56  call    ?RCMRpcPrologueEx@@YAJKKHPEAPEAUITerminal@@PEAPEAUITSSession@@PEAH@Z; RCMRpcPrologueEx(ulong,ulong,int,ITerminal * *,ITSSession * *,int *)
0x180060a5b  mov     ebx, eax
0x180060a5d  test    eax, eax
0x180060a5f  jns     short loc_180060A88
0x180060a61  lea     ecx, [r14-4]
0x180060a65  cmp     eax, 800708CAh
0x180060a6a  mov     r8d, eax
0x180060a6d  lea     rdx, aRcmrpcprologue; "RCMRpcPrologue failed: 0x%x"
0x180060a74  cmovnz  edi, ecx
0x180060a77  mov     ecx, edi; int
0x180060a79  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180060a7e  mov     r15d, [rsp+330h+var_2F0]
0x180060a83  jmp     loc_180060D2C
0x180060a88  mov     rcx, [rsp+330h+var_2C0]
0x180060a8d  lea     r8, [rsp+330h+var_2E0]
0x180060a92  lea     rdx, qword_1800DD390
0x180060a99  mov     rax, [rcx]
0x180060a9c  mov     rax, [rax]
0x180060a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060aa4  mov     ebx, eax
0x180060aa6  test    eax, eax
0x180060aa8  jns     short loc_180060AC3
0x180060aaa  mov     r9, r12
0x180060aad  lea     rdx, aQiIremotetermi_0; "QI( IRemoteTerminal ) failed: 0x%x in %"...
0x180060ab4  mov     ecx, 4; int
0x180060ab9  mov     r8d, eax
0x180060abc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180060ac1  jmp     short loc_180060A7E
0x180060ac3  xor     r12d, r12d
0x180060ac6  test    r13d, r13d
0x180060ac9  jz      loc_180060B96
0x180060acf  mov     r15d, [rsp+330h+var_2F0]
0x180060ad4  test    r15d, r15d
0x180060ad7  jz      short loc_180060B07
0x180060ad9  call    cs:__imp_RpcRevertToSelf
0x180060ae0  nop     dword ptr [rax+rax+00h]
0x180060ae5  test    eax, eax
0x180060ae7  jle     short loc_180060AF3
0x180060ae9  movzx   eax, ax
0x180060aec  or      eax, 80070000h
0x180060af1  test    eax, eax
0x180060af3  jns     short loc_180060B01
0x180060af5  lea     rdx, aRpcreverttosel; "RpcRevertToSelf before ptrRemoteTermina"...
0x180060afc  jmp     loc_180060D1A
0x180060b01  xor     r15d, r15d
0x180060b04  mov     r12d, edi
0x180060b07  mov     edx, [rsp+330h+var_2D8]
0x180060b0b  lea     r9, [rsp+330h+var_2E8]
0x180060b10  mov     rcx, [rsp+330h+var_2E0]
0x180060b15  mov     r10d, edx
0x180060b18  shr     r10d, 1
0x180060b1b  mov     r8d, r10d
0x180060b1e  shr     edx, 3
0x180060b21  and     r8d, 0FFF8h
0x180060b28  mov     [rsp+330h+TokenHandle], r9
0x180060b2d  mov     rax, [rcx]
0x180060b30  and     edx, edi
0x180060b32  and     r10d, 3
0x180060b36  mov     dword ptr [rsp+330h+var_310], r8d
0x180060b3b  mov     r9d, edx
0x180060b3e  mov     r8d, r10d
0x180060b41  mov     rdx, rsi
0x180060b44  mov     rax, [rax+118h]
0x180060b4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060b50  mov     ebx, eax
0x180060b52  test    eax, eax
0x180060b54  jns     short loc_180060B62
0x180060b56  lea     rdx, aPtrremotetermi_3; "ptrRemoteTerminal->CreateDynamicVirtual"...
0x180060b5d  jmp     loc_180060D1A
0x180060b62  test    r12d, r12d
0x180060b65  jz      short loc_180060BD3
0x180060b67  xor     ecx, ecx; BindingHandle
0x180060b69  call    cs:__imp_RpcImpersonateClient
0x180060b70  nop     dword ptr [rax+rax+00h]
0x180060b75  test    eax, eax
0x180060b77  jle     short loc_180060B83
0x180060b79  movzx   eax, ax
0x180060b7c  or      eax, 80070000h
0x180060b81  test    eax, eax
0x180060b83  jns     short loc_180060B91
0x180060b85  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x180060b8c  jmp     loc_180060D1A
0x180060b91  mov     r15d, edi
0x180060b94  jmp     short loc_180060BD3
0x180060b96  mov     rcx, [rsp+330h+var_2E0]
0x180060b9b  lea     r8, [rsp+330h+var_2E8]
0x180060ba0  mov     rdx, rsi
0x180060ba3  mov     rax, [rcx]
0x180060ba6  mov     rax, [rax+110h]
0x180060bad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060bb2  mov     ebx, eax
0x180060bb4  test    eax, eax
0x180060bb6  jns     short loc_180060BCE
0x180060bb8  lea     r9, aRpccreatevirtu; "RpcCreateVirtualChannel"
0x180060bbf  mov     ecx, r14d
0x180060bc2  lea     rdx, aPtrremotetermi_11; "ptrRemoteTerminal->CreateStaticVirtualC"...
0x180060bc9  jmp     loc_180060AB9
0x180060bce  mov     r15d, [rsp+330h+var_2F0]
0x180060bd3  lea     rdx, [rsp+330h+Pid]; Pid
0x180060bd8  xor     ecx, ecx; Binding
0x180060bda  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180060be1  nop     dword ptr [rax+rax+00h]
0x180060be6  mov     ebx, eax
0x180060be8  mov     esi, 80070000h
0x180060bed  test    eax, eax
0x180060bef  jle     short loc_180060BF6
0x180060bf1  movzx   ebx, ax
0x180060bf4  or      ebx, esi
0x180060bf6  test    ebx, ebx
0x180060bf8  jns     short loc_180060C09
0x180060bfa  mov     r8d, ebx
0x180060bfd  lea     rdx, aIRpcbindinginq; "I_RpcBindingInqLocalClientPID failed: 0"...
0x180060c04  jmp     loc_180060D1D
0x180060c09  test    r13d, r13d
0x180060c0c  jz      loc_180060C97
0x180060c12  test    r15d, r15d
0x180060c15  jz      short loc_180060C42
0x180060c17  call    cs:__imp_RpcRevertToSelf
0x180060c1e  nop     dword ptr [rax+rax+00h]
0x180060c23  test    eax, eax
0x180060c25  jle     short loc_180060C2E
0x180060c27  movzx   eax, ax
0x180060c2a  or      eax, esi
0x180060c2c  test    eax, eax
0x180060c2e  jns     short loc_180060C3C
0x180060c30  lea     rdx, aRpcreverttosel_4; "RpcRevertToSelf before DuplicateHandleI"...
0x180060c37  jmp     loc_180060D1A
0x180060c3c  xor     r15d, r15d
0x180060c3f  mov     r12d, edi
0x180060c42  mov     r8, [rsp+330h+var_2B8]; void **
0x180060c47  mov     edx, [rsp+330h+Pid]; unsigned int
0x180060c4b  mov     rcx, [rsp+330h+var_2E8]; void *
0x180060c50  call    ?DuplicateHandleInPidKMode@@YAJPEAXKPEAPEAX@Z; DuplicateHandleInPidKMode(void *,ulong,void * *)
0x180060c55  mov     ebx, eax
0x180060c57  test    eax, eax
0x180060c59  jns     short loc_180060C67
0x180060c5b  lea     rdx, aDuplicatehandl_0; "DuplicateHandleInPidKMode failed: 0x%x "...
0x180060c62  jmp     loc_180060D1A
0x180060c67  test    r12d, r12d
0x180060c6a  jz      loc_180060D2C
0x180060c70  xor     ecx, ecx; BindingHandle
0x180060c72  call    cs:__imp_RpcImpersonateClient
0x180060c79  nop     dword ptr [rax+rax+00h]
0x180060c7e  test    eax, eax
0x180060c80  jle     short loc_180060C89
0x180060c82  movzx   eax, ax
0x180060c85  or      eax, esi
0x180060c87  test    eax, eax
0x180060c89  js      loc_180060B85
0x180060c8f  mov     r15d, edi
0x180060c92  jmp     loc_180060D2C
0x180060c97  lea     rcx, [rsp+330h+var_2C8]; struct ISessionManager **
0x180060c9c  call    ?GetInstanceOfSessionManager@CUtils@@SAJPEAPEAUISessionManager@@@Z; CUtils::GetInstanceOfSessionManager(ISessionManager * *)
0x180060ca1  mov     ebx, eax
0x180060ca3  test    eax, eax
0x180060ca5  jns     short loc_180060CB0
0x180060ca7  lea     rdx, aGetinstanceofs; "GetInstanceOfSessionManager failed: 0x%"...
0x180060cae  jmp     short loc_180060D1A
0x180060cb0  mov     rcx, [rsp+330h+var_2C8]
0x180060cb5  lea     rdx, [rsp+330h+var_2D0]
0x180060cba  mov     rax, [rcx]
0x180060cbd  mov     rax, [rax+30h]
0x180060cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060cc6  mov     ebx, eax
0x180060cc8  test    eax, eax
0x180060cca  jns     short loc_180060CD5
0x180060ccc  lea     rdx, aGetinstanceofr_4; "GetInstanceOfRestrictedCalls failed: 0x"...
0x180060cd3  jmp     short loc_180060D1A
0x180060cd5  mov     rsi, [rsp+330h+var_2D0]
0x180060cda  mov     ebx, [rsp+330h+Pid]
0x180060cde  mov     rax, [rsi]
0x180060ce1  mov     rdi, [rax+18h]
0x180060ce5  call    cs:__imp_GetCurrentProcessId
0x180060cec  nop     dword ptr [rax+rax+00h]
0x180060cf1  mov     r9, [rsp+330h+var_2B8]
0x180060cf6  mov     rcx, rsi
0x180060cf9  mov     rdx, [rsp+330h+var_2E8]
0x180060cfe  mov     r8d, eax
0x180060d01  mov     rax, rdi
0x180060d04  mov     dword ptr [rsp+330h+var_310], ebx
0x180060d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060d0d  mov     ebx, eax
0x180060d0f  test    eax, eax
0x180060d11  jns     short loc_180060D2C
0x180060d13  lea     rdx, aMgrDuplicateha; "Mgr->DuplicateHandleInPid failed: 0x%x "...
0x180060d1a  mov     r8d, eax
0x180060d1d  lea     r9, aRpccreatevirtu; "RpcCreateVirtualChannel"
0x180060d24  mov     ecx, r14d; int
0x180060d27  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180060d2c  test    r15d, r15d
0x180060d2f  jz      short loc_180060D64
0x180060d31  call    cs:__imp_RpcRevertToSelf
0x180060d38  nop     dword ptr [rax+rax+00h]
0x180060d3d  test    eax, eax
  ... truncated ...
```
