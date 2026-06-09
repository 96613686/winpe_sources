# WLIDCDeProvisionDeviceId(ushort const *,ulong,unsigned __int64)

- ea: `0x180048158`
- end: `0x1800484bc`
- name: `?WLIDCDeProvisionDeviceId@@YAJPEBGK_K@Z`
- size: `868`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002a320`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180045168`
- `0x180046ce0`
- `0x180048158`
- `0x18004cd04`
- `0x180050c84`
- `0x180050e40`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004832b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004837d`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004832b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004837d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004823f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004823f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004838e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004838e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800483fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800483fa`
- `RPCRT4!RpcAsyncCancelCall` at `0x180048352`
- `RPCRT4!RpcAsyncCancelCall` at `0x180048352`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800482a3`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800482a3`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800483b3`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800483b3`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800481f8`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800481f8`

## string_xrefs

- `0x180048264`: `RPC failed to create new event, hr = %#x`
- `0x1800483c7`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCDeProvisionDeviceId(const unsigned __int16 *a1, unsigned int a2, __int64 a3)
{
  __int64 result; // rax
  DWORD v6; // esi
  char v7; // r15
  char v8; // r14
  int LastError; // eax
  const unsigned __int16 *v10; // r9
  unsigned int v11; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v13; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-F8h]
  int Reply; // [rsp+40h] [rbp-D8h] BYREF
  char v16; // [rsp+44h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-D0h] BYREF
  DWORD v18; // [rsp+4Ch] [rbp-CCh] BYREF
  __int64 v19; // [rsp+50h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+58h] [rbp-C0h]
  HANDLE Handles[2]; // [rsp+60h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-A8h] BYREF

  v20 = a3;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  v19 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v19);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v6 = dwMilliseconds;
  v18 = dwMilliseconds;
  v7 = 0;
  v16 = 0;
  v8 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v11 = 1278;
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
    v10 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x22u, 0, &pAsync, v19, a1, a2, v20);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v10 = L"RPC call failed, hr = %#x";
    v11 = 1280;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v11,
      v10,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
  v13 = WaitForMultipleObjectsEx(1u, Handles, 0, v6, 0);
  do
  {
    if ( v8 || v13 != 258 && v13 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v13 == 258 )
      v7 = 1;
    else
      v8 = 1;
    v13 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v7 );
  if ( v13 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"Encountered error while waiting on RPC call, hr = %#x";
LABEL_29:
    v11 = 1280;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v7 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[25],unsigned long &>(
      (__int64)"WLIDCDeProvisionDeviceId",
      (int *)&v18);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x500u,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v8 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x500u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v19);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x180048158  push    rsi
0x18004815a  push    r12
0x18004815c  push    r13
0x18004815e  push    r14
0x180048160  push    r15
0x180048162  sub     rsp, 0F0h
0x180048169  mov     rax, cs:__security_cookie
0x180048170  xor     rax, rsp
0x180048173  mov     [rsp+118h+var_38], rax
0x18004817b  mov     [rsp+118h+var_C0], r8
0x180048180  mov     r13d, edx
0x180048183  mov     r12, rcx
0x180048186  mov     [rsp+118h+dwMilliseconds], 0
0x18004818e  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x180048193  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180048198  mov     [rsp+118h+Reply], 0
0x1800481a0  mov     [rsp+118h+var_C8], 0
0x1800481a9  lea     rcx, [rsp+118h+var_C8]; this
0x1800481ae  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x1800481b3  mov     [rsp+118h+Reply], eax
0x1800481b7  test    eax, eax
0x1800481b9  js      loc_18004849B
0x1800481bf  xor     edx, edx; Val
0x1800481c1  lea     r8d, [rdx+70h]; Size
0x1800481c5  lea     rcx, [rsp+118h+pAsync]; void *
0x1800481ca  call    memset_0
0x1800481cf  mov     esi, [rsp+118h+dwMilliseconds]
0x1800481d3  mov     [rsp+118h+dwMilliseconds], esi
0x1800481d7  mov     [rsp+118h+var_CC], esi
0x1800481db  xor     r15b, r15b
0x1800481de  mov     [rsp+118h+var_D4], r15b
0x1800481e3  xor     r14b, r14b
0x1800481e6  xorps   xmm0, xmm0
0x1800481e9  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x1800481ee  mov     edx, 70h ; 'p'; Size
0x1800481f3  lea     rcx, [rsp+118h+pAsync]; pAsync
0x1800481f8  call    cs:__imp_RpcAsyncInitializeHandle
0x1800481fe  test    eax, eax
0x180048200  jz      short loc_18004821E
0x180048202  jle     short loc_18004820C
0x180048204  movzx   eax, ax
0x180048207  or      eax, 80070000h
0x18004820c  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180048213  mov     r8d, 4FEh
0x180048219  jmp     loc_1800483D4
0x18004821e  mov     [rsp+118h+pAsync.UserInfo], 0
0x18004822a  mov     [rsp+118h+pAsync.NotificationType], 1
0x180048235  xor     r9d, r9d; lpName
0x180048238  xor     r8d, r8d; bInitialState
0x18004823b  xor     edx, edx; bManualReset
0x18004823d  xor     ecx, ecx; lpEventAttributes
0x18004823f  call    cs:__imp_CreateEventW
0x180048245  mov     qword ptr [rsp+118h+pAsync.u], rax
0x18004824d  test    rax, rax
0x180048250  jnz     short loc_18004826D
0x180048252  call    cs:__imp_GetLastError
0x180048258  test    eax, eax
0x18004825a  jle     short loc_180048264
0x18004825c  movzx   eax, ax
0x18004825f  or      eax, 80070000h
0x180048264  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004826b  jmp     short loc_180048213
0x18004826d  mov     [rsp+118h+Handles], rax
0x180048272  mov     rax, [rsp+118h+var_C0]
0x180048277  mov     [rsp+118h+var_E0], rax
0x18004827c  mov     [rsp+118h+var_E8], r13d
0x180048281  mov     [rsp+118h+var_F0], r12
0x180048286  mov     rax, [rsp+118h+var_C8]
0x18004828b  mov     qword ptr [rsp+118h+bAlertable], rax
0x180048290  lea     r9, [rsp+118h+pAsync]
0x180048295  xor     r8d, r8d; pReturnValue
0x180048298  lea     edx, [r8+22h]; nProcNum
0x18004829c  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800482a3  call    cs:__imp_Ndr64AsyncClientCall
0x1800482a9  mov     eax, [rsp+118h+Reply]
0x1800482ad  jmp     short loc_1800482FE
0x1800482af  test    eax, eax
0x1800482b1  jle     short loc_1800482BB
0x1800482b3  movzx   eax, ax
0x1800482b6  or      eax, 80070000h
0x1800482bb  mov     [rsp+118h+Reply], eax
0x1800482bf  mov     [rsp+118h+bAlertable], eax
0x1800482c3  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x1800482ca  mov     r8d, 500h; unsigned int
0x1800482d0  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800482d7  mov     ecx, 2; unsigned __int8
0x1800482dc  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800482e1  mov     eax, [rsp+118h+Reply]
0x1800482e5  test    eax, eax
0x1800482e7  js      short loc_1800482F2
0x1800482e9  mov     eax, 8000FFFFh
0x1800482ee  mov     [rsp+118h+Reply], eax
0x1800482f2  mov     esi, [rsp+118h+dwMilliseconds]
0x1800482f6  mov     r15b, [rsp+118h+var_D4]
0x1800482fb  mov     r14b, r15b
0x1800482fe  test    eax, eax
0x180048300  jns     short loc_180048314
0x180048302  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180048309  mov     r8d, 500h
0x18004830f  jmp     loc_1800483D8
0x180048314  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004831c  mov     r9d, esi; dwMilliseconds
0x18004831f  xor     r8d, r8d; bWaitAll
0x180048322  lea     rdx, [rsp+118h+Handles]; lpHandles
0x180048327  lea     ecx, [r8+1]; nCount
0x18004832b  call    cs:__imp_WaitForMultipleObjectsEx
0x180048331  mov     esi, eax
0x180048333  mov     r12d, 102h
0x180048339  test    r14b, r14b
0x18004833c  jnz     short loc_18004838A
0x18004833e  cmp     esi, r12d
0x180048341  jz      short loc_180048348
0x180048343  cmp     esi, 1
0x180048346  jnz     short loc_18004838A
0x180048348  mov     edx, 1; fAbort
0x18004834d  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180048352  call    cs:__imp_RpcAsyncCancelCall
0x180048358  cmp     esi, r12d
0x18004835b  jnz     short loc_180048362
0x18004835d  mov     r15b, 1
0x180048360  jmp     short loc_180048365
0x180048362  mov     r14b, 1
0x180048365  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004836d  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180048371  xor     r8d, r8d; bWaitAll
0x180048374  lea     rdx, [rsp+118h+Handles]; lpHandles
0x180048379  lea     ecx, [r8+1]; nCount
0x18004837d  call    cs:__imp_WaitForMultipleObjectsEx
0x180048383  mov     esi, eax
0x180048385  test    r15b, r15b
0x180048388  jz      short loc_180048339
0x18004838a  test    esi, esi
0x18004838c  jz      short loc_1800483A9
0x18004838e  call    cs:__imp_GetLastError
0x180048394  test    eax, eax
0x180048396  jle     short loc_1800483A0
0x180048398  movzx   eax, ax
0x18004839b  or      eax, 80070000h
0x1800483a0  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x1800483a7  jmp     short loc_1800483CE
0x1800483a9  lea     rdx, [rsp+118h+Reply]; Reply
0x1800483ae  lea     rcx, [rsp+118h+pAsync]; pAsync
0x1800483b3  call    cs:__imp_RpcAsyncCompleteCall
0x1800483b9  test    eax, eax
0x1800483bb  jz      short loc_1800483ED
0x1800483bd  jle     short loc_1800483C7
0x1800483bf  movzx   eax, ax
0x1800483c2  or      eax, 80070000h
0x1800483c7  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x1800483ce  mov     r8d, 500h; unsigned int
0x1800483d4  mov     [rsp+118h+Reply], eax
0x1800483d8  mov     [rsp+118h+bAlertable], eax
0x1800483dc  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800483e3  mov     ecx, 2; unsigned __int8
0x1800483e8  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800483ed  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x1800483f5  test    rcx, rcx
0x1800483f8  jz      short loc_180048400
0x1800483fa  call    cs:__imp_CloseHandle
0x180048400  test    r15b, r15b
0x180048403  jz      short loc_180048444
0x180048405  mov     [rsp+118h+Reply], 800705B4h
0x18004840d  lea     rdx, [rsp+118h+var_CC]
0x180048412  lea     rcx, aWlidcdeprovisi; "WLIDCDeProvisionDeviceId"
0x180048419  call    ??$RPCCallTimedOut@AEAY0BJ@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BJ@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[25],ulong &>(char const (&)[25],ulong &)
0x18004841e  mov     eax, [rsp+118h+Reply]
0x180048422  mov     [rsp+118h+bAlertable], eax
0x180048426  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004842d  mov     r8d, 500h; unsigned int
0x180048433  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004843a  mov     ecx, 2; unsigned __int8
0x18004843f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180048444  test    r14b, r14b
0x180048447  jz      short loc_180048474
0x180048449  mov     eax, 800704C7h
0x18004844e  mov     [rsp+118h+Reply], eax
0x180048452  mov     [rsp+118h+bAlertable], eax
0x180048456  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004845d  mov     r8d, 500h; unsigned int
0x180048463  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004846a  mov     ecx, 2; unsigned __int8
0x18004846f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180048474  cmp     [rsp+118h+Reply], 800706B5h
0x18004847c  jz      short loc_180048488
0x18004847e  cmp     [rsp+118h+Reply], 800706BAh
0x180048486  jnz     short loc_18004848D
0x180048488  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004848d  lea     rcx, [rsp+118h+var_C8]; this
0x180048492  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x180048497  mov     eax, [rsp+118h+Reply]
0x18004849b  mov     rcx, [rsp+118h+var_38]
0x1800484a3  xor     rcx, rsp; StackCookie
0x1800484a6  call    __security_check_cookie
0x1800484ab  add     rsp, 0F0h
0x1800484b2  pop     r15
0x1800484b4  pop     r14
0x1800484b6  pop     r13
0x1800484b8  pop     r12
0x1800484ba  pop     rsi
0x1800484bb  retn
0x1800619b3  push    rbp
0x1800619b5  sub     rsp, 40h
0x1800619b9  mov     rbp, rdx
0x1800619bc  mov     rcx, [rcx]
0x1800619bf  mov     ecx, [rcx]; unsigned int
0x1800619c1  call    ?WLIDpExceptionFilter@@YAHK@Z
0x1800619c6  nop
0x1800619c7  add     rsp, 40h
0x1800619cb  pop     rbp
0x1800619cc  retn
```
