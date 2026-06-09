# WLIDCCreateContextForLinkedIdentity(void * const,ushort const *,void * *)

- ea: `0x180047e20`
- end: `0x18004814f`
- name: `?WLIDCCreateContextForLinkedIdentity@@YAJQEAXPEBGPEAPEAX@Z`
- size: `815`
- prototype: `__int64 __fastcall(void *const, const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180029d90`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x1800455b8`
- `0x180046ce0`
- `0x180047e20`
- `0x18004cd04`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180047fca`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004801c`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180047fca`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004801c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180047ee8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180047ee8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047efb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004802d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047efb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004802d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048099`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048099`
- `RPCRT4!RpcAsyncCancelCall` at `0x180047ff1`
- `RPCRT4!RpcAsyncCancelCall` at `0x180047ff1`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180047f42`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180047f42`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180048052`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180048052`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180047ea1`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180047ea1`

## string_xrefs

- `0x180047f0d`: `RPC failed to create new event, hr = %#x`
- `0x180048066`: `RPC Async complete call failed, hr = %#x`
- `0x1800480b1`: `WLIDCCreateContextForLinkedIdentity`

## pseudocode

```c
__int64 __fastcall WLIDCCreateContextForLinkedIdentity(void *const a1, const unsigned __int16 *a2, void **a3)
{
  DWORD v5; // esi
  char v6; // r15
  char v7; // r14
  int LastError; // eax
  const unsigned __int16 *v9; // r9
  unsigned int v10; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v12; // esi
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-F8h]
  unsigned int Reply; // [rsp+40h] [rbp-D8h] BYREF
  char v16; // [rsp+44h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-D0h] BYREF
  DWORD v18; // [rsp+4Ch] [rbp-CCh] BYREF
  void **v19; // [rsp+50h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+58h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-A8h] BYREF

  v19 = a3;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v5 = dwMilliseconds;
  v18 = dwMilliseconds;
  v6 = 0;
  v16 = 0;
  v7 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v10 = 964;
    goto LABEL_27;
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
    goto LABEL_5;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x28u, 0, &pAsync, a1, a2, v19);
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
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_28;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = L"RPC Async complete call failed, hr = %#x";
  }
  v10 = 966;
LABEL_27:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(2u, "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp", v10, v9, *(_QWORD *)bAlertable);
LABEL_28:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v6 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[36],unsigned long &>(
      (__int64)"WLIDCCreateContextForLinkedIdentity",
      (int *)&v18);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x3C6u,
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
      0x3C6u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  result = Reply;
  if ( Reply == -2147023179 || Reply == -2147023174 )
  {
    TraceServiceStatus();
    return Reply;
  }
  return result;
}

```

## disassembly

```asm
0x180047e20  push    rsi
0x180047e22  push    r12
0x180047e24  push    r13
0x180047e26  push    r14
0x180047e28  push    r15
0x180047e2a  sub     rsp, 0F0h
0x180047e31  mov     rax, cs:__security_cookie
0x180047e38  xor     rax, rsp
0x180047e3b  mov     [rsp+118h+var_38], rax
0x180047e43  mov     [rsp+118h+var_C8], r8
0x180047e48  mov     r13, rdx
0x180047e4b  mov     r12, rcx
0x180047e4e  mov     [rsp+118h+Reply], 0
0x180047e56  mov     [rsp+118h+dwMilliseconds], 0
0x180047e5e  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x180047e63  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180047e68  xor     edx, edx; Val
0x180047e6a  lea     r8d, [rdx+70h]; Size
0x180047e6e  lea     rcx, [rsp+118h+pAsync]; void *
0x180047e73  call    memset_0
0x180047e78  mov     esi, [rsp+118h+dwMilliseconds]
0x180047e7c  mov     [rsp+118h+dwMilliseconds], esi
0x180047e80  mov     [rsp+118h+var_CC], esi
0x180047e84  xor     r15b, r15b
0x180047e87  mov     [rsp+118h+var_D4], r15b
0x180047e8c  xor     r14b, r14b
0x180047e8f  xorps   xmm0, xmm0
0x180047e92  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x180047e97  mov     edx, 70h ; 'p'; Size
0x180047e9c  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180047ea1  call    cs:__imp_RpcAsyncInitializeHandle
0x180047ea7  test    eax, eax
0x180047ea9  jz      short loc_180047EC7
0x180047eab  jle     short loc_180047EB5
0x180047ead  movzx   eax, ax
0x180047eb0  or      eax, 80070000h
0x180047eb5  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180047ebc  mov     r8d, 3C4h
0x180047ec2  jmp     loc_180048073
0x180047ec7  mov     [rsp+118h+pAsync.UserInfo], 0
0x180047ed3  mov     [rsp+118h+pAsync.NotificationType], 1
0x180047ede  xor     r9d, r9d; lpName
0x180047ee1  xor     r8d, r8d; bInitialState
0x180047ee4  xor     edx, edx; bManualReset
0x180047ee6  xor     ecx, ecx; lpEventAttributes
0x180047ee8  call    cs:__imp_CreateEventW
0x180047eee  mov     qword ptr [rsp+118h+pAsync.u], rax
0x180047ef6  test    rax, rax
0x180047ef9  jnz     short loc_180047F16
0x180047efb  call    cs:__imp_GetLastError
0x180047f01  test    eax, eax
0x180047f03  jle     short loc_180047F0D
0x180047f05  movzx   eax, ax
0x180047f08  or      eax, 80070000h
0x180047f0d  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180047f14  jmp     short loc_180047EBC
0x180047f16  mov     [rsp+118h+Handles], rax
0x180047f1b  mov     rax, [rsp+118h+var_C8]
0x180047f20  mov     [rsp+118h+var_E8], rax
0x180047f25  mov     [rsp+118h+var_F0], r13
0x180047f2a  mov     qword ptr [rsp+118h+bAlertable], r12
0x180047f2f  lea     r9, [rsp+118h+pAsync]
0x180047f34  xor     r8d, r8d; pReturnValue
0x180047f37  lea     edx, [r8+28h]; nProcNum
0x180047f3b  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180047f42  call    cs:__imp_Ndr64AsyncClientCall
0x180047f48  mov     eax, [rsp+118h+Reply]
0x180047f4c  jmp     short loc_180047F9D
0x180047f4e  test    eax, eax
0x180047f50  jle     short loc_180047F5A
0x180047f52  movzx   eax, ax
0x180047f55  or      eax, 80070000h
0x180047f5a  mov     [rsp+118h+Reply], eax
0x180047f5e  mov     [rsp+118h+bAlertable], eax
0x180047f62  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180047f69  mov     r8d, 3C6h; unsigned int
0x180047f6f  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180047f76  mov     ecx, 2; unsigned __int8
0x180047f7b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180047f80  mov     eax, [rsp+118h+Reply]
0x180047f84  test    eax, eax
0x180047f86  js      short loc_180047F91
0x180047f88  mov     eax, 8000FFFFh
0x180047f8d  mov     [rsp+118h+Reply], eax
0x180047f91  mov     esi, [rsp+118h+dwMilliseconds]
0x180047f95  mov     r15b, [rsp+118h+var_D4]
0x180047f9a  mov     r14b, r15b
0x180047f9d  test    eax, eax
0x180047f9f  jns     short loc_180047FB3
0x180047fa1  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180047fa8  mov     r8d, 3C6h
0x180047fae  jmp     loc_180048077
0x180047fb3  mov     [rsp+118h+bAlertable], 0; bAlertable
0x180047fbb  mov     r9d, esi; dwMilliseconds
0x180047fbe  xor     r8d, r8d; bWaitAll
0x180047fc1  lea     rdx, [rsp+118h+Handles]; lpHandles
0x180047fc6  lea     ecx, [r8+1]; nCount
0x180047fca  call    cs:__imp_WaitForMultipleObjectsEx
0x180047fd0  mov     esi, eax
0x180047fd2  mov     r12d, 102h
0x180047fd8  test    r14b, r14b
0x180047fdb  jnz     short loc_180048029
0x180047fdd  cmp     esi, r12d
0x180047fe0  jz      short loc_180047FE7
0x180047fe2  cmp     esi, 1
0x180047fe5  jnz     short loc_180048029
0x180047fe7  mov     edx, 1; fAbort
0x180047fec  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180047ff1  call    cs:__imp_RpcAsyncCancelCall
0x180047ff7  cmp     esi, r12d
0x180047ffa  jnz     short loc_180048001
0x180047ffc  mov     r15b, 1
0x180047fff  jmp     short loc_180048004
0x180048001  mov     r14b, 1
0x180048004  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004800c  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180048010  xor     r8d, r8d; bWaitAll
0x180048013  lea     rdx, [rsp+118h+Handles]; lpHandles
0x180048018  lea     ecx, [r8+1]; nCount
0x18004801c  call    cs:__imp_WaitForMultipleObjectsEx
0x180048022  mov     esi, eax
0x180048024  test    r15b, r15b
0x180048027  jz      short loc_180047FD8
0x180048029  test    esi, esi
0x18004802b  jz      short loc_180048048
0x18004802d  call    cs:__imp_GetLastError
0x180048033  test    eax, eax
0x180048035  jle     short loc_18004803F
0x180048037  movzx   eax, ax
0x18004803a  or      eax, 80070000h
0x18004803f  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180048046  jmp     short loc_18004806D
0x180048048  lea     rdx, [rsp+118h+Reply]; Reply
0x18004804d  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180048052  call    cs:__imp_RpcAsyncCompleteCall
0x180048058  test    eax, eax
0x18004805a  jz      short loc_18004808C
0x18004805c  jle     short loc_180048066
0x18004805e  movzx   eax, ax
0x180048061  or      eax, 80070000h
0x180048066  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004806d  mov     r8d, 3C6h; unsigned int
0x180048073  mov     [rsp+118h+Reply], eax
0x180048077  mov     [rsp+118h+bAlertable], eax
0x18004807b  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180048082  mov     ecx, 2; unsigned __int8
0x180048087  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004808c  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x180048094  test    rcx, rcx
0x180048097  jz      short loc_18004809F
0x180048099  call    cs:__imp_CloseHandle
0x18004809f  test    r15b, r15b
0x1800480a2  jz      short loc_1800480E3
0x1800480a4  mov     [rsp+118h+Reply], 800705B4h
0x1800480ac  lea     rdx, [rsp+118h+var_CC]
0x1800480b1  lea     rcx, aWlidccreatecon_0; "WLIDCCreateContextForLinkedIdentity"
0x1800480b8  call    ??$RPCCallTimedOut@AEAY0CE@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0CE@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[36],ulong &>(char const (&)[36],ulong &)
0x1800480bd  mov     eax, [rsp+118h+Reply]
0x1800480c1  mov     [rsp+118h+bAlertable], eax
0x1800480c5  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x1800480cc  mov     r8d, 3C6h; unsigned int
0x1800480d2  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800480d9  mov     ecx, 2; unsigned __int8
0x1800480de  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800480e3  test    r14b, r14b
0x1800480e6  jz      short loc_180048113
0x1800480e8  mov     eax, 800704C7h
0x1800480ed  mov     [rsp+118h+Reply], eax
0x1800480f1  mov     [rsp+118h+bAlertable], eax
0x1800480f5  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x1800480fc  mov     r8d, 3C6h; unsigned int
0x180048102  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180048109  mov     ecx, 2; unsigned __int8
0x18004810e  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180048113  mov     eax, [rsp+118h+Reply]
0x180048117  cmp     eax, 800706B5h
0x18004811c  jz      short loc_180048125
0x18004811e  cmp     eax, 800706BAh
0x180048123  jnz     short loc_18004812E
0x180048125  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004812a  mov     eax, [rsp+118h+Reply]
0x18004812e  mov     rcx, [rsp+118h+var_38]
0x180048136  xor     rcx, rsp; StackCookie
0x180048139  call    __security_check_cookie
0x18004813e  add     rsp, 0F0h
0x180048145  pop     r15
0x180048147  pop     r14
0x180048149  pop     r13
0x18004814b  pop     r12
0x18004814d  pop     rsi
0x18004814e  retn
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
