# WLIDCGetProofOfPossessionTokens(ushort const *,ushort const *,_GUID const *,ulong *,ProofOfPossessionCookieInfo * *)

- ea: `0x1800474f8`
- end: `0x180047896`
- name: `?WLIDCGetProofOfPossessionTokens@@YAJPEBG0PEBU_GUID@@PEAKPEAPEAUProofOfPossessionCookieInfo@@@Z`
- size: `926`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, unsigned int *, struct ProofOfPossessionCookieInfo **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800417c0`

## callees

- `0x18000a400`
- `0x18000f870`
- `0x180010c68`
- `0x180011588`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x1800421e8`
- `0x180043240`
- `0x1800474f8`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800475fa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800475fa`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180047703`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004775b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180047703`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004775b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004760d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004776c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004760d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004776c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800477db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800477db`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800475b3`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800475b3`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004772d`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004772d`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180047678`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180047678`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180047794`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180047794`

## string_xrefs

- `0x18004761f`: `RPC failed to create new event, hr = %#x`
- `0x1800477a8`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCGetProofOfPossessionTokens(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        unsigned int *a4,
        struct ProofOfPossessionCookieInfo **a5)
{
  __int64 result; // rax
  DWORD v8; // esi
  char v9; // r15
  char v10; // r14
  int LastError; // eax
  const unsigned __int16 *v12; // r9
  unsigned int v13; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v15; // esi
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  BOOL bAlertable[2]; // [rsp+20h] [rbp-118h]
  int Reply; // [rsp+50h] [rbp-E8h] BYREF
  char v19; // [rsp+54h] [rbp-E4h]
  DWORD dwMilliseconds; // [rsp+58h] [rbp-E0h] BYREF
  DWORD v21; // [rsp+5Ch] [rbp-DCh] BYREF
  __int64 v22; // [rsp+60h] [rbp-D8h] BYREF
  struct ProofOfPossessionCookieInfo **v23; // [rsp+68h] [rbp-D0h]
  unsigned int *v24; // [rsp+70h] [rbp-C8h]
  const struct _GUID *v25; // [rsp+78h] [rbp-C0h]
  HANDLE Handles[2]; // [rsp+80h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+90h] [rbp-A8h] BYREF

  v24 = a4;
  v25 = a3;
  v23 = a5;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  v22 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v22);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v8 = dwMilliseconds;
  v21 = dwMilliseconds;
  v9 = 0;
  v19 = 0;
  v10 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v12 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v13 = 1365;
LABEL_30:
    Reply = LastError;
    goto LABEL_31;
  }
  pAsync.UserInfo = 0;
  pAsync.NotificationType = RpcNotificationTypeEvent;
  EventW = (RPCNOTIFICATION_ROUTINE *)CreateEventW(0, 0, 0, 0);
  pAsync.u.APC.NotificationRoutine = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v12 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x41u, 0, &pAsync, v22, a1, a2, v25, v24, v23);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v12 = L"RPC call failed, hr = %#x";
    v13 = 1367;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v13,
      v12,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
  v15 = WaitForMultipleObjectsEx(1u, Handles, 0, v8, 0);
  do
  {
    if ( v10 || v15 != 258 && v15 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v15 == 258 )
      v9 = 1;
    else
      v10 = 1;
    v15 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v9 );
  if ( v15 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v12 = L"Encountered error while waiting on RPC call, hr = %#x";
LABEL_29:
    v13 = 1367;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v12 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  NotificationRoutine = pAsync.u.APC.NotificationRoutine;
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v9 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[32],unsigned long &>(NotificationRoutine, &v21);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x557u,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v10 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x557u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v22);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x1800474f8  push    rsi
0x1800474fa  push    r12
0x1800474fc  push    r13
0x1800474fe  push    r14
0x180047500  push    r15
0x180047502  sub     rsp, 110h
0x180047509  mov     rax, cs:__security_cookie
0x180047510  xor     rax, rsp
0x180047513  mov     [rsp+138h+var_38], rax
0x18004751b  mov     [rsp+138h+var_C8], r9
0x180047520  mov     [rsp+138h+var_C0], r8
0x180047525  mov     r13, rdx
0x180047528  mov     r12, rcx
0x18004752b  mov     rax, [rsp+138h+arg_20]
0x180047533  mov     [rsp+138h+var_D0], rax
0x180047538  mov     [rsp+138h+dwMilliseconds], 0
0x180047540  lea     r8, [rsp+138h+dwMilliseconds]; unsigned int *
0x180047545  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004754a  mov     [rsp+138h+Reply], 0
0x180047552  mov     [rsp+138h+var_D8], 0
0x18004755b  lea     rcx, [rsp+138h+var_D8]; this
0x180047560  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x180047565  mov     [rsp+138h+Reply], eax
0x180047569  test    eax, eax
0x18004756b  js      loc_180047875
0x180047571  xor     edx, edx; Val
0x180047573  lea     r8d, [rdx+70h]; Size
0x180047577  lea     rcx, [rsp+138h+pAsync]; void *
0x18004757f  call    memset_0
0x180047584  mov     esi, [rsp+138h+dwMilliseconds]
0x180047588  mov     [rsp+138h+dwMilliseconds], esi
0x18004758c  mov     [rsp+138h+var_DC], esi
0x180047590  xor     r15b, r15b
0x180047593  mov     [rsp+138h+var_E4], r15b
0x180047598  xor     r14b, r14b
0x18004759b  xorps   xmm0, xmm0
0x18004759e  movups  xmmword ptr [rsp+138h+Handles], xmm0
0x1800475a6  mov     edx, 70h ; 'p'; Size
0x1800475ab  lea     rcx, [rsp+138h+pAsync]; pAsync
0x1800475b3  call    cs:__imp_RpcAsyncInitializeHandle
0x1800475b9  test    eax, eax
0x1800475bb  jz      short loc_1800475D9
0x1800475bd  jle     short loc_1800475C7
0x1800475bf  movzx   eax, ax
0x1800475c2  or      eax, 80070000h
0x1800475c7  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x1800475ce  mov     r8d, 555h
0x1800475d4  jmp     loc_1800477B5
0x1800475d9  mov     [rsp+138h+pAsync.UserInfo], 0
0x1800475e5  mov     [rsp+138h+pAsync.NotificationType], 1
0x1800475f0  xor     r9d, r9d; lpName
0x1800475f3  xor     r8d, r8d; bInitialState
0x1800475f6  xor     edx, edx; bManualReset
0x1800475f8  xor     ecx, ecx; lpEventAttributes
0x1800475fa  call    cs:__imp_CreateEventW
0x180047600  mov     qword ptr [rsp+138h+pAsync.u], rax
0x180047608  test    rax, rax
0x18004760b  jnz     short loc_180047628
0x18004760d  call    cs:__imp_GetLastError
0x180047613  test    eax, eax
0x180047615  jle     short loc_18004761F
0x180047617  movzx   eax, ax
0x18004761a  or      eax, 80070000h
0x18004761f  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180047626  jmp     short loc_1800475CE
0x180047628  mov     [rsp+138h+Handles], rax
0x180047630  mov     rax, [rsp+138h+var_D0]
0x180047635  mov     [rsp+138h+var_F0], rax
0x18004763a  mov     rax, [rsp+138h+var_C8]
0x18004763f  mov     [rsp+138h+var_F8], rax
0x180047644  mov     rax, [rsp+138h+var_C0]
0x180047649  mov     [rsp+138h+var_100], rax
0x18004764e  mov     [rsp+138h+var_108], r13
0x180047653  mov     [rsp+138h+var_110], r12
0x180047658  mov     rax, [rsp+138h+var_D8]
0x18004765d  mov     qword ptr [rsp+138h+bAlertable], rax
0x180047662  lea     r9, [rsp+138h+pAsync]
0x18004766a  xor     r8d, r8d; pReturnValue
0x18004766d  lea     edx, [r8+41h]; nProcNum
0x180047671  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180047678  call    cs:__imp_Ndr64AsyncClientCall
0x18004767e  mov     eax, [rsp+138h+Reply]
0x180047682  jmp     short loc_1800476D3
0x180047684  test    eax, eax
0x180047686  jle     short loc_180047690
0x180047688  movzx   eax, ax
0x18004768b  or      eax, 80070000h
0x180047690  mov     [rsp+138h+Reply], eax
0x180047694  mov     [rsp+138h+bAlertable], eax
0x180047698  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004769f  mov     r8d, 557h; unsigned int
0x1800476a5  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800476ac  mov     ecx, 2; unsigned __int8
0x1800476b1  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800476b6  mov     eax, [rsp+138h+Reply]
0x1800476ba  test    eax, eax
0x1800476bc  js      short loc_1800476C7
0x1800476be  mov     eax, 8000FFFFh
0x1800476c3  mov     [rsp+138h+Reply], eax
0x1800476c7  mov     esi, [rsp+138h+dwMilliseconds]
0x1800476cb  mov     r15b, [rsp+138h+var_E4]
0x1800476d0  mov     r14b, r15b
0x1800476d3  test    eax, eax
0x1800476d5  jns     short loc_1800476E9
0x1800476d7  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x1800476de  mov     r8d, 557h
0x1800476e4  jmp     loc_1800477B9
0x1800476e9  mov     [rsp+138h+bAlertable], 0; bAlertable
0x1800476f1  mov     r9d, esi; dwMilliseconds
0x1800476f4  xor     r8d, r8d; bWaitAll
0x1800476f7  lea     rdx, [rsp+138h+Handles]; lpHandles
0x1800476ff  lea     ecx, [r8+1]; nCount
0x180047703  call    cs:__imp_WaitForMultipleObjectsEx
0x180047709  mov     esi, eax
0x18004770b  mov     r12d, 102h
0x180047711  test    r14b, r14b
0x180047714  jnz     short loc_180047768
0x180047716  cmp     esi, r12d
0x180047719  jz      short loc_180047720
0x18004771b  cmp     esi, 1
0x18004771e  jnz     short loc_180047768
0x180047720  mov     edx, 1; fAbort
0x180047725  lea     rcx, [rsp+138h+pAsync]; pAsync
0x18004772d  call    cs:__imp_RpcAsyncCancelCall
0x180047733  cmp     esi, r12d
0x180047736  jnz     short loc_18004773D
0x180047738  mov     r15b, 1
0x18004773b  jmp     short loc_180047740
0x18004773d  mov     r14b, 1
0x180047740  mov     [rsp+138h+bAlertable], 0; bAlertable
0x180047748  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004774c  xor     r8d, r8d; bWaitAll
0x18004774f  lea     rdx, [rsp+138h+Handles]; lpHandles
0x180047757  lea     ecx, [r8+1]; nCount
0x18004775b  call    cs:__imp_WaitForMultipleObjectsEx
0x180047761  mov     esi, eax
0x180047763  test    r15b, r15b
0x180047766  jz      short loc_180047711
0x180047768  test    esi, esi
0x18004776a  jz      short loc_180047787
0x18004776c  call    cs:__imp_GetLastError
0x180047772  test    eax, eax
0x180047774  jle     short loc_18004777E
0x180047776  movzx   eax, ax
0x180047779  or      eax, 80070000h
0x18004777e  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180047785  jmp     short loc_1800477AF
0x180047787  lea     rdx, [rsp+138h+Reply]; Reply
0x18004778c  lea     rcx, [rsp+138h+pAsync]; pAsync
0x180047794  call    cs:__imp_RpcAsyncCompleteCall
0x18004779a  test    eax, eax
0x18004779c  jz      short loc_1800477CE
0x18004779e  jle     short loc_1800477A8
0x1800477a0  movzx   eax, ax
0x1800477a3  or      eax, 80070000h
0x1800477a8  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x1800477af  mov     r8d, 557h; unsigned int
0x1800477b5  mov     [rsp+138h+Reply], eax
0x1800477b9  mov     [rsp+138h+bAlertable], eax
0x1800477bd  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800477c4  mov     ecx, 2; unsigned __int8
0x1800477c9  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800477ce  mov     rcx, qword ptr [rsp+138h+pAsync.u]; hObject
0x1800477d6  test    rcx, rcx
0x1800477d9  jz      short loc_1800477E1
0x1800477db  call    cs:__imp_CloseHandle
0x1800477e1  test    r15b, r15b
0x1800477e4  jz      short loc_18004781E
0x1800477e6  mov     [rsp+138h+Reply], 800705B4h
0x1800477ee  lea     rdx, [rsp+138h+var_DC]
0x1800477f3  call    ??$RPCCallTimedOut@AEAY0CA@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0CA@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[32],ulong &>(char const (&)[32],ulong &)
0x1800477f8  mov     eax, [rsp+138h+Reply]
0x1800477fc  mov     [rsp+138h+bAlertable], eax
0x180047800  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180047807  mov     r8d, 557h; unsigned int
0x18004780d  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180047814  mov     ecx, 2; unsigned __int8
0x180047819  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004781e  test    r14b, r14b
0x180047821  jz      short loc_18004784E
0x180047823  mov     eax, 800704C7h
0x180047828  mov     [rsp+138h+Reply], eax
0x18004782c  mov     [rsp+138h+bAlertable], eax
0x180047830  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180047837  mov     r8d, 557h; unsigned int
0x18004783d  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180047844  mov     ecx, 2; unsigned __int8
0x180047849  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004784e  cmp     [rsp+138h+Reply], 800706B5h
0x180047856  jz      short loc_180047862
0x180047858  cmp     [rsp+138h+Reply], 800706BAh
0x180047860  jnz     short loc_180047867
0x180047862  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180047867  lea     rcx, [rsp+138h+var_D8]; this
0x18004786c  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x180047871  mov     eax, [rsp+138h+Reply]
0x180047875  mov     rcx, [rsp+138h+var_38]
0x18004787d  xor     rcx, rsp; StackCookie
0x180047880  call    __security_check_cookie
0x180047885  add     rsp, 110h
0x18004788c  pop     r15
0x18004788e  pop     r14
0x180047890  pop     r13
0x180047892  pop     r12
0x180047894  pop     rsi
0x180047895  retn
0x180057620  push    rbp
0x180057622  sub     rsp, 50h
0x180057626  mov     rbp, rdx
0x180057629  mov     rcx, [rcx]
0x18005762c  mov     ecx, [rcx]; unsigned int
0x18005762e  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x180057633  nop
0x180057634  add     rsp, 50h
0x180057638  pop     rbp
0x180057639  retn
```
