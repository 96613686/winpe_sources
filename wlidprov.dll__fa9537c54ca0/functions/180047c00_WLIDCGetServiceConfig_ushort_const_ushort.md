# WLIDCGetServiceConfig(ushort const *,ushort * *)

- ea: `0x180047c00`
- end: `0x180047f64`
- name: `?WLIDCGetServiceConfig@@YAJPEBGPEAPEAG@Z`
- size: `868`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180041800`

## callees

- `0x18000a400`
- `0x18000f870`
- `0x180010c68`
- `0x180011588`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180041d0c`
- `0x180043240`
- `0x180047c00`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180047ce8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180047ce8`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180047dca`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180047e1c`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180047dca`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180047e1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047cfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047e2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047cfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047e2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047e99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047e99`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180047ca1`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180047ca1`
- `RPCRT4!RpcAsyncCancelCall` at `0x180047df1`
- `RPCRT4!RpcAsyncCancelCall` at `0x180047df1`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180047d42`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180047d42`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180047e52`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180047e52`

## string_xrefs

- `0x180047d0d`: `RPC failed to create new event, hr = %#x`
- `0x180047e66`: `RPC Async complete call failed, hr = %#x`
- `0x180047eb1`: `WLIDCGetServiceConfig`

## pseudocode

```c
__int64 __fastcall WLIDCGetServiceConfig(const unsigned __int16 *a1, unsigned __int16 **a2)
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
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
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
    v10 = 648;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0xEu, 0, &pAsync, v18, a1, a2);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v9 = L"RPC call failed, hr = %#x";
    v10 = 650;
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
    v10 = 650;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[22],unsigned long &>("WLIDCGetServiceConfig", &v17);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x28Au,
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
      0x28Au,
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
0x180047c00  mov     [rsp+arg_10], rsi
0x180047c05  mov     [rsp+arg_18], r12
0x180047c0a  push    r13
0x180047c0c  push    r14
0x180047c0e  push    r15
0x180047c10  sub     rsp, 0F0h
0x180047c17  mov     rax, cs:__security_cookie
0x180047c1e  xor     rax, rsp
0x180047c21  mov     [rsp+108h+var_28], rax
0x180047c29  mov     r13, rdx
0x180047c2c  mov     r12, rcx
0x180047c2f  mov     [rsp+108h+dwMilliseconds], 0
0x180047c37  lea     r8, [rsp+108h+dwMilliseconds]; unsigned int *
0x180047c3c  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180047c41  mov     [rsp+108h+Reply], 0
0x180047c49  mov     [rsp+108h+var_B8], 0
0x180047c52  lea     rcx, [rsp+108h+var_B8]; this
0x180047c57  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x180047c5c  mov     [rsp+108h+Reply], eax
0x180047c60  test    eax, eax
0x180047c62  js      loc_180047F3A
0x180047c68  xor     edx, edx; Val
0x180047c6a  lea     r8d, [rdx+70h]; Size
0x180047c6e  lea     rcx, [rsp+108h+pAsync]; void *
0x180047c73  call    memset_0
0x180047c78  mov     esi, [rsp+108h+dwMilliseconds]
0x180047c7c  mov     [rsp+108h+dwMilliseconds], esi
0x180047c80  mov     [rsp+108h+var_BC], esi
0x180047c84  xor     r15b, r15b
0x180047c87  mov     [rsp+108h+var_C4], r15b
0x180047c8c  xor     r14b, r14b
0x180047c8f  xorps   xmm0, xmm0
0x180047c92  movups  xmmword ptr [rsp+108h+Handles], xmm0
0x180047c97  mov     edx, 70h ; 'p'; Size
0x180047c9c  lea     rcx, [rsp+108h+pAsync]; pAsync
0x180047ca1  call    cs:__imp_RpcAsyncInitializeHandle
0x180047ca7  test    eax, eax
0x180047ca9  jz      short loc_180047CC7
0x180047cab  jle     short loc_180047CB5
0x180047cad  movzx   eax, ax
0x180047cb0  or      eax, 80070000h
0x180047cb5  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180047cbc  mov     r8d, 288h
0x180047cc2  jmp     loc_180047E73
0x180047cc7  mov     [rsp+108h+pAsync.UserInfo], 0
0x180047cd3  mov     [rsp+108h+pAsync.NotificationType], 1
0x180047cde  xor     r9d, r9d; lpName
0x180047ce1  xor     r8d, r8d; bInitialState
0x180047ce4  xor     edx, edx; bManualReset
0x180047ce6  xor     ecx, ecx; lpEventAttributes
0x180047ce8  call    cs:__imp_CreateEventW
0x180047cee  mov     qword ptr [rsp+108h+pAsync.u], rax
0x180047cf6  test    rax, rax
0x180047cf9  jnz     short loc_180047D16
0x180047cfb  call    cs:__imp_GetLastError
0x180047d01  test    eax, eax
0x180047d03  jle     short loc_180047D0D
0x180047d05  movzx   eax, ax
0x180047d08  or      eax, 80070000h
0x180047d0d  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180047d14  jmp     short loc_180047CBC
0x180047d16  mov     [rsp+108h+Handles], rax
0x180047d1b  mov     [rsp+108h+var_D8], r13
0x180047d20  mov     [rsp+108h+var_E0], r12
0x180047d25  mov     rax, [rsp+108h+var_B8]
0x180047d2a  mov     qword ptr [rsp+108h+bAlertable], rax
0x180047d2f  lea     r9, [rsp+108h+pAsync]
0x180047d34  xor     r8d, r8d; pReturnValue
0x180047d37  lea     edx, [r8+0Eh]; nProcNum
0x180047d3b  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180047d42  call    cs:__imp_Ndr64AsyncClientCall
0x180047d48  mov     eax, [rsp+108h+Reply]
0x180047d4c  jmp     short loc_180047D9D
0x180047d4e  test    eax, eax
0x180047d50  jle     short loc_180047D5A
0x180047d52  movzx   eax, ax
0x180047d55  or      eax, 80070000h
0x180047d5a  mov     [rsp+108h+Reply], eax
0x180047d5e  mov     [rsp+108h+bAlertable], eax
0x180047d62  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180047d69  mov     r8d, 28Ah; unsigned int
0x180047d6f  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180047d76  mov     ecx, 2; unsigned __int8
0x180047d7b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180047d80  mov     eax, [rsp+108h+Reply]
0x180047d84  test    eax, eax
0x180047d86  js      short loc_180047D91
0x180047d88  mov     eax, 8000FFFFh
0x180047d8d  mov     [rsp+108h+Reply], eax
0x180047d91  mov     esi, [rsp+108h+dwMilliseconds]
0x180047d95  mov     r15b, [rsp+108h+var_C4]
0x180047d9a  mov     r14b, r15b
0x180047d9d  test    eax, eax
0x180047d9f  jns     short loc_180047DB3
0x180047da1  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180047da8  mov     r8d, 28Ah
0x180047dae  jmp     loc_180047E77
0x180047db3  mov     [rsp+108h+bAlertable], 0; bAlertable
0x180047dbb  mov     r9d, esi; dwMilliseconds
0x180047dbe  xor     r8d, r8d; bWaitAll
0x180047dc1  lea     rdx, [rsp+108h+Handles]; lpHandles
0x180047dc6  lea     ecx, [r8+1]; nCount
0x180047dca  call    cs:__imp_WaitForMultipleObjectsEx
0x180047dd0  mov     esi, eax
0x180047dd2  mov     r12d, 102h
0x180047dd8  test    r14b, r14b
0x180047ddb  jnz     short loc_180047E29
0x180047ddd  cmp     esi, r12d
0x180047de0  jz      short loc_180047DE7
0x180047de2  cmp     esi, 1
0x180047de5  jnz     short loc_180047E29
0x180047de7  mov     edx, 1; fAbort
0x180047dec  lea     rcx, [rsp+108h+pAsync]; pAsync
0x180047df1  call    cs:__imp_RpcAsyncCancelCall
0x180047df7  cmp     esi, r12d
0x180047dfa  jnz     short loc_180047E01
0x180047dfc  mov     r15b, 1
0x180047dff  jmp     short loc_180047E04
0x180047e01  mov     r14b, 1
0x180047e04  mov     [rsp+108h+bAlertable], 0; bAlertable
0x180047e0c  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180047e10  xor     r8d, r8d; bWaitAll
0x180047e13  lea     rdx, [rsp+108h+Handles]; lpHandles
0x180047e18  lea     ecx, [r8+1]; nCount
0x180047e1c  call    cs:__imp_WaitForMultipleObjectsEx
0x180047e22  mov     esi, eax
0x180047e24  test    r15b, r15b
0x180047e27  jz      short loc_180047DD8
0x180047e29  test    esi, esi
0x180047e2b  jz      short loc_180047E48
0x180047e2d  call    cs:__imp_GetLastError
0x180047e33  test    eax, eax
0x180047e35  jle     short loc_180047E3F
0x180047e37  movzx   eax, ax
0x180047e3a  or      eax, 80070000h
0x180047e3f  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180047e46  jmp     short loc_180047E6D
0x180047e48  lea     rdx, [rsp+108h+Reply]; Reply
0x180047e4d  lea     rcx, [rsp+108h+pAsync]; pAsync
0x180047e52  call    cs:__imp_RpcAsyncCompleteCall
0x180047e58  test    eax, eax
0x180047e5a  jz      short loc_180047E8C
0x180047e5c  jle     short loc_180047E66
0x180047e5e  movzx   eax, ax
0x180047e61  or      eax, 80070000h
0x180047e66  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180047e6d  mov     r8d, 28Ah; unsigned int
0x180047e73  mov     [rsp+108h+Reply], eax
0x180047e77  mov     [rsp+108h+bAlertable], eax
0x180047e7b  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180047e82  mov     ecx, 2; unsigned __int8
0x180047e87  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180047e8c  mov     rcx, qword ptr [rsp+108h+pAsync.u]; hObject
0x180047e94  test    rcx, rcx
0x180047e97  jz      short loc_180047E9F
0x180047e99  call    cs:__imp_CloseHandle
0x180047e9f  test    r15b, r15b
0x180047ea2  jz      short loc_180047EE3
0x180047ea4  mov     [rsp+108h+Reply], 800705B4h
0x180047eac  lea     rdx, [rsp+108h+var_BC]
0x180047eb1  lea     rcx, aWlidcgetservic; "WLIDCGetServiceConfig"
0x180047eb8  call    ??$RPCCallTimedOut@AEAY0BG@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BG@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[22],ulong &>(char const (&)[22],ulong &)
0x180047ebd  mov     eax, [rsp+108h+Reply]
0x180047ec1  mov     [rsp+108h+bAlertable], eax
0x180047ec5  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180047ecc  mov     r8d, 28Ah; unsigned int
0x180047ed2  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180047ed9  mov     ecx, 2; unsigned __int8
0x180047ede  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180047ee3  test    r14b, r14b
0x180047ee6  jz      short loc_180047F13
0x180047ee8  mov     eax, 800704C7h
0x180047eed  mov     [rsp+108h+Reply], eax
0x180047ef1  mov     [rsp+108h+bAlertable], eax
0x180047ef5  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180047efc  mov     r8d, 28Ah; unsigned int
0x180047f02  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180047f09  mov     ecx, 2; unsigned __int8
0x180047f0e  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180047f13  cmp     [rsp+108h+Reply], 800706B5h
0x180047f1b  jz      short loc_180047F27
0x180047f1d  cmp     [rsp+108h+Reply], 800706BAh
0x180047f25  jnz     short loc_180047F2C
0x180047f27  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180047f2c  lea     rcx, [rsp+108h+var_B8]; this
0x180047f31  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x180047f36  mov     eax, [rsp+108h+Reply]
0x180047f3a  mov     rcx, [rsp+108h+var_28]
0x180047f42  xor     rcx, rsp; StackCookie
0x180047f45  call    __security_check_cookie
0x180047f4a  lea     r11, [rsp+108h+var_18]
0x180047f52  mov     rsi, [r11+30h]
0x180047f56  mov     r12, [r11+38h]
0x180047f5a  mov     rsp, r11
0x180047f5d  pop     r15
0x180047f5f  pop     r14
0x180047f61  pop     r13
0x180047f63  retn
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
