# WLIDCCleanupIdentity(ushort const *)

- ea: `0x1800441f8`
- end: `0x18004453e`
- name: `?WLIDCCleanupIdentity@@YAJPEBG@Z`
- size: `838`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800415d0`

## callees

- `0x18000a400`
- `0x18000f870`
- `0x180010c68`
- `0x180011588`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180041c80`
- `0x180043240`
- `0x1800441f8`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800442d2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800442d2`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800443af`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180044401`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800443af`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180044401`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800442e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044412`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800442e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044412`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004447e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004447e`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004428e`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004428e`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800443d6`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800443d6`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180044327`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180044327`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180044437`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180044437`

## string_xrefs

- `0x1800442f7`: `RPC failed to create new event, hr = %#x`
- `0x18004444b`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCCleanupIdentity(const unsigned __int16 *a1, unsigned int a2)
{
  __int64 result; // rax
  DWORD v4; // esi
  char v5; // r15
  char v6; // r14
  int LastError; // eax
  const unsigned __int16 *v8; // r9
  unsigned int v9; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v11; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-E8h]
  int Reply; // [rsp+30h] [rbp-D8h] BYREF
  char v14; // [rsp+34h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+38h] [rbp-D0h] BYREF
  DWORD v16; // [rsp+3Ch] [rbp-CCh] BYREF
  __int64 v17; // [rsp+40h] [rbp-C8h] BYREF
  HANDLE Handles[3]; // [rsp+48h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+60h] [rbp-A8h] BYREF

  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  v17 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v17);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v4 = dwMilliseconds;
  v16 = dwMilliseconds;
  v5 = 0;
  v14 = 0;
  v6 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v9 = 1540;
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
    v8 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x4Bu, 0, &pAsync, v17, a1);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v8 = L"RPC call failed, hr = %#x";
    v9 = 1542;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v9,
      v8,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
  v11 = WaitForMultipleObjectsEx(1u, Handles, 0, v4, 0);
  do
  {
    if ( v6 || v11 != 258 && v11 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v11 == 258 )
      v5 = 1;
    else
      v6 = 1;
    v11 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v5 );
  if ( v11 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = L"Encountered error while waiting on RPC call, hr = %#x";
LABEL_29:
    v9 = 1542;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v5 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],unsigned long &>("WLIDCCleanupIdentity", &v16);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x606u,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v6 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x606u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v17);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x1800441f8  push    rsi
0x1800441fa  push    r12
0x1800441fc  push    r14
0x1800441fe  push    r15
0x180044200  sub     rsp, 0E8h
0x180044207  mov     rax, cs:__security_cookie
0x18004420e  xor     rax, rsp
0x180044211  mov     [rsp+108h+var_38], rax
0x180044219  mov     r12, rcx
0x18004421c  mov     [rsp+108h+dwMilliseconds], 0
0x180044224  lea     r8, [rsp+108h+dwMilliseconds]; unsigned int *
0x180044229  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004422e  mov     [rsp+108h+Reply], 0
0x180044236  mov     [rsp+108h+var_C8], 0
0x18004423f  lea     rcx, [rsp+108h+var_C8]; this
0x180044244  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x180044249  mov     [rsp+108h+Reply], eax
0x18004424d  test    eax, eax
0x18004424f  js      loc_18004451F
0x180044255  xor     edx, edx; Val
0x180044257  lea     r8d, [rdx+70h]; Size
0x18004425b  lea     rcx, [rsp+108h+pAsync]; void *
0x180044260  call    memset_0
0x180044265  mov     esi, [rsp+108h+dwMilliseconds]
0x180044269  mov     [rsp+108h+dwMilliseconds], esi
0x18004426d  mov     [rsp+108h+var_CC], esi
0x180044271  xor     r15b, r15b
0x180044274  mov     [rsp+108h+var_D4], r15b
0x180044279  xor     r14b, r14b
0x18004427c  xorps   xmm0, xmm0
0x18004427f  movups  xmmword ptr [rsp+108h+Handles], xmm0
0x180044284  mov     edx, 70h ; 'p'; Size
0x180044289  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004428e  call    cs:__imp_RpcAsyncInitializeHandle
0x180044294  test    eax, eax
0x180044296  jz      short loc_1800442B4
0x180044298  jle     short loc_1800442A2
0x18004429a  movzx   eax, ax
0x18004429d  or      eax, 80070000h
0x1800442a2  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x1800442a9  mov     r8d, 604h
0x1800442af  jmp     loc_180044458
0x1800442b4  mov     [rsp+108h+pAsync.UserInfo], 0
0x1800442bd  mov     [rsp+108h+pAsync.NotificationType], 1
0x1800442c8  xor     r9d, r9d; lpName
0x1800442cb  xor     r8d, r8d; bInitialState
0x1800442ce  xor     edx, edx; bManualReset
0x1800442d0  xor     ecx, ecx; lpEventAttributes
0x1800442d2  call    cs:__imp_CreateEventW
0x1800442d8  mov     qword ptr [rsp+108h+pAsync.u], rax
0x1800442e0  test    rax, rax
0x1800442e3  jnz     short loc_180044300
0x1800442e5  call    cs:__imp_GetLastError
0x1800442eb  test    eax, eax
0x1800442ed  jle     short loc_1800442F7
0x1800442ef  movzx   eax, ax
0x1800442f2  or      eax, 80070000h
0x1800442f7  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x1800442fe  jmp     short loc_1800442A9
0x180044300  mov     [rsp+108h+Handles], rax
0x180044305  mov     [rsp+108h+var_E0], r12
0x18004430a  mov     rax, [rsp+108h+var_C8]
0x18004430f  mov     qword ptr [rsp+108h+bAlertable], rax
0x180044314  lea     r9, [rsp+108h+pAsync]
0x180044319  xor     r8d, r8d; pReturnValue
0x18004431c  lea     edx, [r8+4Bh]; nProcNum
0x180044320  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180044327  call    cs:__imp_Ndr64AsyncClientCall
0x18004432d  mov     eax, [rsp+108h+Reply]
0x180044331  jmp     short loc_180044382
0x180044333  test    eax, eax
0x180044335  jle     short loc_18004433F
0x180044337  movzx   eax, ax
0x18004433a  or      eax, 80070000h
0x18004433f  mov     [rsp+108h+Reply], eax
0x180044343  mov     [rsp+108h+bAlertable], eax
0x180044347  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004434e  mov     r8d, 606h; unsigned int
0x180044354  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004435b  mov     ecx, 2; unsigned __int8
0x180044360  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180044365  mov     eax, [rsp+108h+Reply]
0x180044369  test    eax, eax
0x18004436b  js      short loc_180044376
0x18004436d  mov     eax, 8000FFFFh
0x180044372  mov     [rsp+108h+Reply], eax
0x180044376  mov     esi, [rsp+108h+dwMilliseconds]
0x18004437a  mov     r15b, [rsp+108h+var_D4]
0x18004437f  mov     r14b, r15b
0x180044382  test    eax, eax
0x180044384  jns     short loc_180044398
0x180044386  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004438d  mov     r8d, 606h
0x180044393  jmp     loc_18004445C
0x180044398  mov     [rsp+108h+bAlertable], 0; bAlertable
0x1800443a0  mov     r9d, esi; dwMilliseconds
0x1800443a3  xor     r8d, r8d; bWaitAll
0x1800443a6  lea     rdx, [rsp+108h+Handles]; lpHandles
0x1800443ab  lea     ecx, [r8+1]; nCount
0x1800443af  call    cs:__imp_WaitForMultipleObjectsEx
0x1800443b5  mov     esi, eax
0x1800443b7  mov     r12d, 102h
0x1800443bd  test    r14b, r14b
0x1800443c0  jnz     short loc_18004440E
0x1800443c2  cmp     esi, r12d
0x1800443c5  jz      short loc_1800443CC
0x1800443c7  cmp     esi, 1
0x1800443ca  jnz     short loc_18004440E
0x1800443cc  mov     edx, 1; fAbort
0x1800443d1  lea     rcx, [rsp+108h+pAsync]; pAsync
0x1800443d6  call    cs:__imp_RpcAsyncCancelCall
0x1800443dc  cmp     esi, r12d
0x1800443df  jnz     short loc_1800443E6
0x1800443e1  mov     r15b, 1
0x1800443e4  jmp     short loc_1800443E9
0x1800443e6  mov     r14b, 1
0x1800443e9  mov     [rsp+108h+bAlertable], 0; bAlertable
0x1800443f1  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800443f5  xor     r8d, r8d; bWaitAll
0x1800443f8  lea     rdx, [rsp+108h+Handles]; lpHandles
0x1800443fd  lea     ecx, [r8+1]; nCount
0x180044401  call    cs:__imp_WaitForMultipleObjectsEx
0x180044407  mov     esi, eax
0x180044409  test    r15b, r15b
0x18004440c  jz      short loc_1800443BD
0x18004440e  test    esi, esi
0x180044410  jz      short loc_18004442D
0x180044412  call    cs:__imp_GetLastError
0x180044418  test    eax, eax
0x18004441a  jle     short loc_180044424
0x18004441c  movzx   eax, ax
0x18004441f  or      eax, 80070000h
0x180044424  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004442b  jmp     short loc_180044452
0x18004442d  lea     rdx, [rsp+108h+Reply]; Reply
0x180044432  lea     rcx, [rsp+108h+pAsync]; pAsync
0x180044437  call    cs:__imp_RpcAsyncCompleteCall
0x18004443d  test    eax, eax
0x18004443f  jz      short loc_180044471
0x180044441  jle     short loc_18004444B
0x180044443  movzx   eax, ax
0x180044446  or      eax, 80070000h
0x18004444b  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180044452  mov     r8d, 606h; unsigned int
0x180044458  mov     [rsp+108h+Reply], eax
0x18004445c  mov     [rsp+108h+bAlertable], eax
0x180044460  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180044467  mov     ecx, 2; unsigned __int8
0x18004446c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180044471  mov     rcx, qword ptr [rsp+108h+pAsync.u]; hObject
0x180044479  test    rcx, rcx
0x18004447c  jz      short loc_180044484
0x18004447e  call    cs:__imp_CloseHandle
0x180044484  test    r15b, r15b
0x180044487  jz      short loc_1800444C8
0x180044489  mov     [rsp+108h+Reply], 800705B4h
0x180044491  lea     rdx, [rsp+108h+var_CC]
0x180044496  lea     rcx, aWlidccleanupid; "WLIDCCleanupIdentity"
0x18004449d  call    ??$RPCCallTimedOut@AEAY0BF@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BF@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],ulong &>(char const (&)[21],ulong &)
0x1800444a2  mov     eax, [rsp+108h+Reply]
0x1800444a6  mov     [rsp+108h+bAlertable], eax
0x1800444aa  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x1800444b1  mov     r8d, 606h; unsigned int
0x1800444b7  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800444be  mov     ecx, 2; unsigned __int8
0x1800444c3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800444c8  test    r14b, r14b
0x1800444cb  jz      short loc_1800444F8
0x1800444cd  mov     eax, 800704C7h
0x1800444d2  mov     [rsp+108h+Reply], eax
0x1800444d6  mov     [rsp+108h+bAlertable], eax
0x1800444da  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x1800444e1  mov     r8d, 606h; unsigned int
0x1800444e7  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800444ee  mov     ecx, 2; unsigned __int8
0x1800444f3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800444f8  cmp     [rsp+108h+Reply], 800706B5h
0x180044500  jz      short loc_18004450C
0x180044502  cmp     [rsp+108h+Reply], 800706BAh
0x18004450a  jnz     short loc_180044511
0x18004450c  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180044511  lea     rcx, [rsp+108h+var_C8]; this
0x180044516  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18004451b  mov     eax, [rsp+108h+Reply]
0x18004451f  mov     rcx, [rsp+108h+var_38]
0x180044527  xor     rcx, rsp; StackCookie
0x18004452a  call    __security_check_cookie
0x18004452f  add     rsp, 0E8h
0x180044536  pop     r15
0x180044538  pop     r14
0x18004453a  pop     r12
0x18004453c  pop     rsi
0x18004453d  retn
0x180057041  push    rbp
0x180057043  sub     rsp, 30h
0x180057047  mov     rbp, rdx
0x18005704a  mov     rcx, [rcx]
0x18005704d  mov     ecx, [rcx]; unsigned int
0x18005704f  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x180057054  nop
0x180057055  add     rsp, 30h
0x180057059  pop     rbp
0x18005705a  retn
```
