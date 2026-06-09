# WLIDCGetConfigDWORDValue(ulong,ulong *)

- ea: `0x180046034`
- end: `0x180046398`
- name: `?WLIDCGetConfigDWORDValue@@YAJKPEAK@Z`
- size: `868`
- prototype: `__int64 __fastcall(unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800416e0`

## callees

- `0x18000a400`
- `0x18000f870`
- `0x180010c68`
- `0x180011588`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180041eac`
- `0x180043240`
- `0x180046034`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004611c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004611c`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800461fe`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180046250`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800461fe`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180046250`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004612f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046261`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004612f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046261`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800462cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800462cd`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800460d5`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800460d5`
- `RPCRT4!RpcAsyncCancelCall` at `0x180046225`
- `RPCRT4!RpcAsyncCancelCall` at `0x180046225`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180046176`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180046176`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180046286`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180046286`

## string_xrefs

- `0x180046141`: `RPC failed to create new event, hr = %#x`
- `0x18004629a`: `RPC Async complete call failed, hr = %#x`
- `0x1800462e5`: `WLIDCGetConfigDWORDValue`

## pseudocode

```c
__int64 __fastcall WLIDCGetConfigDWORDValue(unsigned int a1, unsigned int *a2)
{
  __int64 result; // rax
  DWORD v5; // esi
  char v6; // r15
  char v7; // r14
  int LastError; // eax
  const unsigned __int16 *v9; // r9
  unsigned int v10; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v12; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-E8h]
  int Reply; // [rsp+40h] [rbp-C8h] BYREF
  char v15; // [rsp+44h] [rbp-C4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-C0h] BYREF
  DWORD v17; // [rsp+4Ch] [rbp-BCh] BYREF
  __int64 v18; // [rsp+50h] [rbp-B8h] BYREF
  HANDLE Handles[3]; // [rsp+58h] [rbp-B0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-98h] BYREF

  dwMilliseconds = 0;
  WLIDCGetTimeOutValue(a1, (unsigned int)a2, &dwMilliseconds);
  v18 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v18);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v5 = dwMilliseconds;
  v17 = dwMilliseconds;
  v6 = 0;
  v15 = 0;
  v7 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v10 = 1091;
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
    v9 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x36u, 0, &pAsync, v18, a1, a2);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v9 = L"RPC call failed, hr = %#x";
    v10 = 1093;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v10,
      v9,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
  v12 = WaitForMultipleObjectsEx(1u, Handles, 0, v5, 0);
  do
  {
    if ( v7 || v12 != 258 && v12 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v12 == 258 )
      v6 = 1;
    else
      v7 = 1;
    v12 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v6 );
  if ( v12 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = L"Encountered error while waiting on RPC call, hr = %#x";
LABEL_29:
    v10 = 1093;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v6 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[25],unsigned long &>("WLIDCGetConfigDWORDValue", &v17);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x445u,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v7 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x445u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v18);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x180046034  mov     [rsp+arg_10], rsi
0x180046039  mov     [rsp+arg_18], r12
0x18004603e  push    r13
0x180046040  push    r14
0x180046042  push    r15
0x180046044  sub     rsp, 0F0h
0x18004604b  mov     rax, cs:__security_cookie
0x180046052  xor     rax, rsp
0x180046055  mov     [rsp+108h+var_28], rax
0x18004605d  mov     r13, rdx
0x180046060  mov     r12d, ecx
0x180046063  mov     [rsp+108h+dwMilliseconds], 0
0x18004606b  lea     r8, [rsp+108h+dwMilliseconds]; unsigned int *
0x180046070  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180046075  mov     [rsp+108h+Reply], 0
0x18004607d  mov     [rsp+108h+var_B8], 0
0x180046086  lea     rcx, [rsp+108h+var_B8]; this
0x18004608b  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x180046090  mov     [rsp+108h+Reply], eax
0x180046094  test    eax, eax
0x180046096  js      loc_18004636E
0x18004609c  xor     edx, edx; Val
0x18004609e  lea     r8d, [rdx+70h]; Size
0x1800460a2  lea     rcx, [rsp+108h+pAsync]; void *
0x1800460a7  call    memset_0
0x1800460ac  mov     esi, [rsp+108h+dwMilliseconds]
0x1800460b0  mov     [rsp+108h+dwMilliseconds], esi
0x1800460b4  mov     [rsp+108h+var_BC], esi
0x1800460b8  xor     r15b, r15b
0x1800460bb  mov     [rsp+108h+var_C4], r15b
0x1800460c0  xor     r14b, r14b
0x1800460c3  xorps   xmm0, xmm0
0x1800460c6  movups  xmmword ptr [rsp+108h+Handles], xmm0
0x1800460cb  mov     edx, 70h ; 'p'; Size
0x1800460d0  lea     rcx, [rsp+108h+pAsync]; pAsync
0x1800460d5  call    cs:__imp_RpcAsyncInitializeHandle
0x1800460db  test    eax, eax
0x1800460dd  jz      short loc_1800460FB
0x1800460df  jle     short loc_1800460E9
0x1800460e1  movzx   eax, ax
0x1800460e4  or      eax, 80070000h
0x1800460e9  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x1800460f0  mov     r8d, 443h
0x1800460f6  jmp     loc_1800462A7
0x1800460fb  mov     [rsp+108h+pAsync.UserInfo], 0
0x180046107  mov     [rsp+108h+pAsync.NotificationType], 1
0x180046112  xor     r9d, r9d; lpName
0x180046115  xor     r8d, r8d; bInitialState
0x180046118  xor     edx, edx; bManualReset
0x18004611a  xor     ecx, ecx; lpEventAttributes
0x18004611c  call    cs:__imp_CreateEventW
0x180046122  mov     qword ptr [rsp+108h+pAsync.u], rax
0x18004612a  test    rax, rax
0x18004612d  jnz     short loc_18004614A
0x18004612f  call    cs:__imp_GetLastError
0x180046135  test    eax, eax
0x180046137  jle     short loc_180046141
0x180046139  movzx   eax, ax
0x18004613c  or      eax, 80070000h
0x180046141  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180046148  jmp     short loc_1800460F0
0x18004614a  mov     [rsp+108h+Handles], rax
0x18004614f  mov     [rsp+108h+var_D8], r13
0x180046154  mov     [rsp+108h+var_E0], r12d
0x180046159  mov     rax, [rsp+108h+var_B8]
0x18004615e  mov     qword ptr [rsp+108h+bAlertable], rax
0x180046163  lea     r9, [rsp+108h+pAsync]
0x180046168  xor     r8d, r8d; pReturnValue
0x18004616b  lea     edx, [r8+36h]; nProcNum
0x18004616f  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180046176  call    cs:__imp_Ndr64AsyncClientCall
0x18004617c  mov     eax, [rsp+108h+Reply]
0x180046180  jmp     short loc_1800461D1
0x180046182  test    eax, eax
0x180046184  jle     short loc_18004618E
0x180046186  movzx   eax, ax
0x180046189  or      eax, 80070000h
0x18004618e  mov     [rsp+108h+Reply], eax
0x180046192  mov     [rsp+108h+bAlertable], eax
0x180046196  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004619d  mov     r8d, 445h; unsigned int
0x1800461a3  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800461aa  mov     ecx, 2; unsigned __int8
0x1800461af  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800461b4  mov     eax, [rsp+108h+Reply]
0x1800461b8  test    eax, eax
0x1800461ba  js      short loc_1800461C5
0x1800461bc  mov     eax, 8000FFFFh
0x1800461c1  mov     [rsp+108h+Reply], eax
0x1800461c5  mov     esi, [rsp+108h+dwMilliseconds]
0x1800461c9  mov     r15b, [rsp+108h+var_C4]
0x1800461ce  mov     r14b, r15b
0x1800461d1  test    eax, eax
0x1800461d3  jns     short loc_1800461E7
0x1800461d5  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x1800461dc  mov     r8d, 445h
0x1800461e2  jmp     loc_1800462AB
0x1800461e7  mov     [rsp+108h+bAlertable], 0; bAlertable
0x1800461ef  mov     r9d, esi; dwMilliseconds
0x1800461f2  xor     r8d, r8d; bWaitAll
0x1800461f5  lea     rdx, [rsp+108h+Handles]; lpHandles
0x1800461fa  lea     ecx, [r8+1]; nCount
0x1800461fe  call    cs:__imp_WaitForMultipleObjectsEx
0x180046204  mov     esi, eax
0x180046206  mov     r12d, 102h
0x18004620c  test    r14b, r14b
0x18004620f  jnz     short loc_18004625D
0x180046211  cmp     esi, r12d
0x180046214  jz      short loc_18004621B
0x180046216  cmp     esi, 1
0x180046219  jnz     short loc_18004625D
0x18004621b  mov     edx, 1; fAbort
0x180046220  lea     rcx, [rsp+108h+pAsync]; pAsync
0x180046225  call    cs:__imp_RpcAsyncCancelCall
0x18004622b  cmp     esi, r12d
0x18004622e  jnz     short loc_180046235
0x180046230  mov     r15b, 1
0x180046233  jmp     short loc_180046238
0x180046235  mov     r14b, 1
0x180046238  mov     [rsp+108h+bAlertable], 0; bAlertable
0x180046240  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180046244  xor     r8d, r8d; bWaitAll
0x180046247  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18004624c  lea     ecx, [r8+1]; nCount
0x180046250  call    cs:__imp_WaitForMultipleObjectsEx
0x180046256  mov     esi, eax
0x180046258  test    r15b, r15b
0x18004625b  jz      short loc_18004620C
0x18004625d  test    esi, esi
0x18004625f  jz      short loc_18004627C
0x180046261  call    cs:__imp_GetLastError
0x180046267  test    eax, eax
0x180046269  jle     short loc_180046273
0x18004626b  movzx   eax, ax
0x18004626e  or      eax, 80070000h
0x180046273  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004627a  jmp     short loc_1800462A1
0x18004627c  lea     rdx, [rsp+108h+Reply]; Reply
0x180046281  lea     rcx, [rsp+108h+pAsync]; pAsync
0x180046286  call    cs:__imp_RpcAsyncCompleteCall
0x18004628c  test    eax, eax
0x18004628e  jz      short loc_1800462C0
0x180046290  jle     short loc_18004629A
0x180046292  movzx   eax, ax
0x180046295  or      eax, 80070000h
0x18004629a  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x1800462a1  mov     r8d, 445h; unsigned int
0x1800462a7  mov     [rsp+108h+Reply], eax
0x1800462ab  mov     [rsp+108h+bAlertable], eax
0x1800462af  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800462b6  mov     ecx, 2; unsigned __int8
0x1800462bb  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800462c0  mov     rcx, qword ptr [rsp+108h+pAsync.u]; hObject
0x1800462c8  test    rcx, rcx
0x1800462cb  jz      short loc_1800462D3
0x1800462cd  call    cs:__imp_CloseHandle
0x1800462d3  test    r15b, r15b
0x1800462d6  jz      short loc_180046317
0x1800462d8  mov     [rsp+108h+Reply], 800705B4h
0x1800462e0  lea     rdx, [rsp+108h+var_BC]
0x1800462e5  lea     rcx, aWlidcgetconfig_0; "WLIDCGetConfigDWORDValue"
0x1800462ec  call    ??$RPCCallTimedOut@AEAY0BJ@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BJ@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[25],ulong &>(char const (&)[25],ulong &)
0x1800462f1  mov     eax, [rsp+108h+Reply]
0x1800462f5  mov     [rsp+108h+bAlertable], eax
0x1800462f9  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180046300  mov     r8d, 445h; unsigned int
0x180046306  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004630d  mov     ecx, 2; unsigned __int8
0x180046312  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180046317  test    r14b, r14b
0x18004631a  jz      short loc_180046347
0x18004631c  mov     eax, 800704C7h
0x180046321  mov     [rsp+108h+Reply], eax
0x180046325  mov     [rsp+108h+bAlertable], eax
0x180046329  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180046330  mov     r8d, 445h; unsigned int
0x180046336  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004633d  mov     ecx, 2; unsigned __int8
0x180046342  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180046347  cmp     [rsp+108h+Reply], 800706B5h
0x18004634f  jz      short loc_18004635B
0x180046351  cmp     [rsp+108h+Reply], 800706BAh
0x180046359  jnz     short loc_180046360
0x18004635b  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180046360  lea     rcx, [rsp+108h+var_B8]; this
0x180046365  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18004636a  mov     eax, [rsp+108h+Reply]
0x18004636e  mov     rcx, [rsp+108h+var_28]
0x180046376  xor     rcx, rsp; StackCookie
0x180046379  call    __security_check_cookie
0x18004637e  lea     r11, [rsp+108h+var_18]
0x180046386  mov     rsi, [r11+30h]
0x18004638a  mov     r12, [r11+38h]
0x18004638e  mov     rsp, r11
0x180046391  pop     r15
0x180046393  pop     r14
0x180046395  pop     r13
0x180046397  retn
0x180057062  push    rbp
0x180057064  sub     rsp, 40h
0x180057068  mov     rbp, rdx
0x18005706b  mov     rcx, [rcx]
0x18005706e  mov     ecx, [rcx]; unsigned int
0x180057070  call    ?WLIDpExceptionFilter@@YAHK@Z
0x180057075  nop
0x180057076  add     rsp, 40h
0x18005707a  pop     rbp
0x18005707b  retn
```
