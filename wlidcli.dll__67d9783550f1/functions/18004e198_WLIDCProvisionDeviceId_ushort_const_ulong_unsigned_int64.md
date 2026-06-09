# WLIDCProvisionDeviceId(ushort const *,ulong,unsigned __int64)

- ea: `0x18004e198`
- end: `0x18004e4fc`
- name: `?WLIDCProvisionDeviceId@@YAJPEBGK_K@Z`
- size: `868`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800329b0`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x1800450dc`
- `0x180046ce0`
- `0x18004cd04`
- `0x18004e198`
- `0x180050c84`
- `0x180050e40`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004e36b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004e3bd`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004e36b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004e3bd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004e27f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004e27f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e292`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e3ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e292`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e3ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e43a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e43a`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004e392`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004e392`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004e2e3`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004e2e3`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004e3f3`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004e3f3`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004e238`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004e238`

## string_xrefs

- `0x18004e2a4`: `RPC failed to create new event, hr = %#x`
- `0x18004e407`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCProvisionDeviceId(const unsigned __int16 *a1, unsigned int a2, __int64 a3)
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
    v11 = 1238;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x1Fu, 0, &pAsync, v19, a1, a2, v20);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v10 = L"RPC call failed, hr = %#x";
    v11 = 1240;
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
    v11 = 1240;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[23],unsigned long &>(
      (__int64)"WLIDCProvisionDeviceId",
      (int *)&v18);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x4D8u,
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
      0x4D8u,
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
0x18004e198  push    rsi
0x18004e19a  push    r12
0x18004e19c  push    r13
0x18004e19e  push    r14
0x18004e1a0  push    r15
0x18004e1a2  sub     rsp, 0F0h
0x18004e1a9  mov     rax, cs:__security_cookie
0x18004e1b0  xor     rax, rsp
0x18004e1b3  mov     [rsp+118h+var_38], rax
0x18004e1bb  mov     [rsp+118h+var_C0], r8
0x18004e1c0  mov     r13d, edx
0x18004e1c3  mov     r12, rcx
0x18004e1c6  mov     [rsp+118h+dwMilliseconds], 0
0x18004e1ce  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x18004e1d3  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004e1d8  mov     [rsp+118h+Reply], 0
0x18004e1e0  mov     [rsp+118h+var_C8], 0
0x18004e1e9  lea     rcx, [rsp+118h+var_C8]; this
0x18004e1ee  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18004e1f3  mov     [rsp+118h+Reply], eax
0x18004e1f7  test    eax, eax
0x18004e1f9  js      loc_18004E4DB
0x18004e1ff  xor     edx, edx; Val
0x18004e201  lea     r8d, [rdx+70h]; Size
0x18004e205  lea     rcx, [rsp+118h+pAsync]; void *
0x18004e20a  call    memset_0
0x18004e20f  mov     esi, [rsp+118h+dwMilliseconds]
0x18004e213  mov     [rsp+118h+dwMilliseconds], esi
0x18004e217  mov     [rsp+118h+var_CC], esi
0x18004e21b  xor     r15b, r15b
0x18004e21e  mov     [rsp+118h+var_D4], r15b
0x18004e223  xor     r14b, r14b
0x18004e226  xorps   xmm0, xmm0
0x18004e229  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x18004e22e  mov     edx, 70h ; 'p'; Size
0x18004e233  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004e238  call    cs:__imp_RpcAsyncInitializeHandle
0x18004e23e  test    eax, eax
0x18004e240  jz      short loc_18004E25E
0x18004e242  jle     short loc_18004E24C
0x18004e244  movzx   eax, ax
0x18004e247  or      eax, 80070000h
0x18004e24c  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004e253  mov     r8d, 4D6h
0x18004e259  jmp     loc_18004E414
0x18004e25e  mov     [rsp+118h+pAsync.UserInfo], 0
0x18004e26a  mov     [rsp+118h+pAsync.NotificationType], 1
0x18004e275  xor     r9d, r9d; lpName
0x18004e278  xor     r8d, r8d; bInitialState
0x18004e27b  xor     edx, edx; bManualReset
0x18004e27d  xor     ecx, ecx; lpEventAttributes
0x18004e27f  call    cs:__imp_CreateEventW
0x18004e285  mov     qword ptr [rsp+118h+pAsync.u], rax
0x18004e28d  test    rax, rax
0x18004e290  jnz     short loc_18004E2AD
0x18004e292  call    cs:__imp_GetLastError
0x18004e298  test    eax, eax
0x18004e29a  jle     short loc_18004E2A4
0x18004e29c  movzx   eax, ax
0x18004e29f  or      eax, 80070000h
0x18004e2a4  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004e2ab  jmp     short loc_18004E253
0x18004e2ad  mov     [rsp+118h+Handles], rax
0x18004e2b2  mov     rax, [rsp+118h+var_C0]
0x18004e2b7  mov     [rsp+118h+var_E0], rax
0x18004e2bc  mov     [rsp+118h+var_E8], r13d
0x18004e2c1  mov     [rsp+118h+var_F0], r12
0x18004e2c6  mov     rax, [rsp+118h+var_C8]
0x18004e2cb  mov     qword ptr [rsp+118h+bAlertable], rax
0x18004e2d0  lea     r9, [rsp+118h+pAsync]
0x18004e2d5  xor     r8d, r8d; pReturnValue
0x18004e2d8  lea     edx, [r8+1Fh]; nProcNum
0x18004e2dc  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004e2e3  call    cs:__imp_Ndr64AsyncClientCall
0x18004e2e9  mov     eax, [rsp+118h+Reply]
0x18004e2ed  jmp     short loc_18004E33E
0x18004e2ef  test    eax, eax
0x18004e2f1  jle     short loc_18004E2FB
0x18004e2f3  movzx   eax, ax
0x18004e2f6  or      eax, 80070000h
0x18004e2fb  mov     [rsp+118h+Reply], eax
0x18004e2ff  mov     [rsp+118h+bAlertable], eax
0x18004e303  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004e30a  mov     r8d, 4D8h; unsigned int
0x18004e310  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004e317  mov     ecx, 2; unsigned __int8
0x18004e31c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004e321  mov     eax, [rsp+118h+Reply]
0x18004e325  test    eax, eax
0x18004e327  js      short loc_18004E332
0x18004e329  mov     eax, 8000FFFFh
0x18004e32e  mov     [rsp+118h+Reply], eax
0x18004e332  mov     esi, [rsp+118h+dwMilliseconds]
0x18004e336  mov     r15b, [rsp+118h+var_D4]
0x18004e33b  mov     r14b, r15b
0x18004e33e  test    eax, eax
0x18004e340  jns     short loc_18004E354
0x18004e342  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004e349  mov     r8d, 4D8h
0x18004e34f  jmp     loc_18004E418
0x18004e354  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004e35c  mov     r9d, esi; dwMilliseconds
0x18004e35f  xor     r8d, r8d; bWaitAll
0x18004e362  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004e367  lea     ecx, [r8+1]; nCount
0x18004e36b  call    cs:__imp_WaitForMultipleObjectsEx
0x18004e371  mov     esi, eax
0x18004e373  mov     r12d, 102h
0x18004e379  test    r14b, r14b
0x18004e37c  jnz     short loc_18004E3CA
0x18004e37e  cmp     esi, r12d
0x18004e381  jz      short loc_18004E388
0x18004e383  cmp     esi, 1
0x18004e386  jnz     short loc_18004E3CA
0x18004e388  mov     edx, 1; fAbort
0x18004e38d  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004e392  call    cs:__imp_RpcAsyncCancelCall
0x18004e398  cmp     esi, r12d
0x18004e39b  jnz     short loc_18004E3A2
0x18004e39d  mov     r15b, 1
0x18004e3a0  jmp     short loc_18004E3A5
0x18004e3a2  mov     r14b, 1
0x18004e3a5  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004e3ad  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004e3b1  xor     r8d, r8d; bWaitAll
0x18004e3b4  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004e3b9  lea     ecx, [r8+1]; nCount
0x18004e3bd  call    cs:__imp_WaitForMultipleObjectsEx
0x18004e3c3  mov     esi, eax
0x18004e3c5  test    r15b, r15b
0x18004e3c8  jz      short loc_18004E379
0x18004e3ca  test    esi, esi
0x18004e3cc  jz      short loc_18004E3E9
0x18004e3ce  call    cs:__imp_GetLastError
0x18004e3d4  test    eax, eax
0x18004e3d6  jle     short loc_18004E3E0
0x18004e3d8  movzx   eax, ax
0x18004e3db  or      eax, 80070000h
0x18004e3e0  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004e3e7  jmp     short loc_18004E40E
0x18004e3e9  lea     rdx, [rsp+118h+Reply]; Reply
0x18004e3ee  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004e3f3  call    cs:__imp_RpcAsyncCompleteCall
0x18004e3f9  test    eax, eax
0x18004e3fb  jz      short loc_18004E42D
0x18004e3fd  jle     short loc_18004E407
0x18004e3ff  movzx   eax, ax
0x18004e402  or      eax, 80070000h
0x18004e407  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004e40e  mov     r8d, 4D8h; unsigned int
0x18004e414  mov     [rsp+118h+Reply], eax
0x18004e418  mov     [rsp+118h+bAlertable], eax
0x18004e41c  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004e423  mov     ecx, 2; unsigned __int8
0x18004e428  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004e42d  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x18004e435  test    rcx, rcx
0x18004e438  jz      short loc_18004E440
0x18004e43a  call    cs:__imp_CloseHandle
0x18004e440  test    r15b, r15b
0x18004e443  jz      short loc_18004E484
0x18004e445  mov     [rsp+118h+Reply], 800705B4h
0x18004e44d  lea     rdx, [rsp+118h+var_CC]
0x18004e452  lea     rcx, aWlidcprovision; "WLIDCProvisionDeviceId"
0x18004e459  call    ??$RPCCallTimedOut@AEAY0BH@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BH@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[23],ulong &>(char const (&)[23],ulong &)
0x18004e45e  mov     eax, [rsp+118h+Reply]
0x18004e462  mov     [rsp+118h+bAlertable], eax
0x18004e466  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004e46d  mov     r8d, 4D8h; unsigned int
0x18004e473  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004e47a  mov     ecx, 2; unsigned __int8
0x18004e47f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004e484  test    r14b, r14b
0x18004e487  jz      short loc_18004E4B4
0x18004e489  mov     eax, 800704C7h
0x18004e48e  mov     [rsp+118h+Reply], eax
0x18004e492  mov     [rsp+118h+bAlertable], eax
0x18004e496  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004e49d  mov     r8d, 4D8h; unsigned int
0x18004e4a3  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004e4aa  mov     ecx, 2; unsigned __int8
0x18004e4af  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004e4b4  cmp     [rsp+118h+Reply], 800706B5h
0x18004e4bc  jz      short loc_18004E4C8
0x18004e4be  cmp     [rsp+118h+Reply], 800706BAh
0x18004e4c6  jnz     short loc_18004E4CD
0x18004e4c8  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004e4cd  lea     rcx, [rsp+118h+var_C8]; this
0x18004e4d2  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18004e4d7  mov     eax, [rsp+118h+Reply]
0x18004e4db  mov     rcx, [rsp+118h+var_38]
0x18004e4e3  xor     rcx, rsp; StackCookie
0x18004e4e6  call    __security_check_cookie
0x18004e4eb  add     rsp, 0F0h
0x18004e4f2  pop     r15
0x18004e4f4  pop     r14
0x18004e4f6  pop     r13
0x18004e4f8  pop     r12
0x18004e4fa  pop     rsi
0x18004e4fb  retn
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
