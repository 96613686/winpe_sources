# WLIDCGetCachedTokens(void * const,ulong,_WLIDRequestParams * const,_WLIDResponseParams * *)

- ea: `0x18004990c`
- end: `0x180049c64`
- name: `?WLIDCGetCachedTokens@@YAJQEAXKQEAU_WLIDRequestParams@@PEAPEAU_WLIDResponseParams@@@Z`
- size: `856`
- prototype: `__int64 __fastcall(void *const, unsigned int, struct _WLIDRequestParams *const, struct _WLIDResponseParams **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001dd50`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180044fc4`
- `0x180046ce0`
- `0x18004990c`
- `0x18004cd04`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180049ad9`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180049b2e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180049ad9`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180049b2e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800499e2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800499e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800499f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049b3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800499f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049b3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049bae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049bae`
- `RPCRT4!RpcAsyncCancelCall` at `0x180049b03`
- `RPCRT4!RpcAsyncCancelCall` at `0x180049b03`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180049a51`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180049a51`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180049b67`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180049b67`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004999b`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004999b`

## string_xrefs

- `0x180049a07`: `RPC failed to create new event, hr = %#x`
- `0x180049b7b`: `RPC Async complete call failed, hr = %#x`
- `0x180049bc6`: `WLIDCGetCachedTokens`

## pseudocode

```c
__int64 __fastcall WLIDCGetCachedTokens(
        void *const a1,
        unsigned int a2,
        struct _WLIDRequestParams *const a3,
        struct _WLIDResponseParams **a4)
{
  DWORD v6; // esi
  char v7; // r15
  char v8; // r14
  int LastError; // eax
  const unsigned __int16 *v10; // r9
  unsigned int v11; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v13; // esi
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-108h]
  unsigned int Reply; // [rsp+50h] [rbp-D8h] BYREF
  char v17; // [rsp+54h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+58h] [rbp-D0h] BYREF
  int v19; // [rsp+5Ch] [rbp-CCh] BYREF
  DWORD v20; // [rsp+60h] [rbp-C8h] BYREF
  struct _WLIDResponseParams **v21; // [rsp+68h] [rbp-C0h]
  HANDLE Handles[2]; // [rsp+70h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+80h] [rbp-A8h] BYREF

  v21 = a4;
  v19 = 0;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v6 = dwMilliseconds;
  v20 = dwMilliseconds;
  v7 = 0;
  v17 = 0;
  v8 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v11 = 725;
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
    v10 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_5;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x12u, 0, &pAsync, a1, 1, a3, &v19, v21);
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
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_28;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC Async complete call failed, hr = %#x";
  }
  v11 = 727;
LABEL_27:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(
    2u,
    "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
    v11,
    v10,
    *(_QWORD *)bAlertable);
LABEL_28:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v7 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],unsigned long &>(
      (__int64)"WLIDCGetCachedTokens",
      (int *)&v20);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x2D7u,
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
      0x2D7u,
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
0x18004990c  push    rsi
0x18004990e  push    r12
0x180049910  push    r13
0x180049912  push    r14
0x180049914  push    r15
0x180049916  sub     rsp, 100h
0x18004991d  mov     rax, cs:__security_cookie
0x180049924  xor     rax, rsp
0x180049927  mov     [rsp+128h+var_38], rax
0x18004992f  mov     [rsp+128h+var_C0], r9
0x180049934  mov     r13, r8
0x180049937  mov     r12, rcx
0x18004993a  mov     [rsp+128h+var_CC], 0
0x180049942  mov     [rsp+128h+Reply], 0
0x18004994a  mov     [rsp+128h+dwMilliseconds], 0
0x180049952  lea     r8, [rsp+128h+dwMilliseconds]; unsigned int *
0x180049957  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004995c  xor     edx, edx; Val
0x18004995e  lea     r8d, [rdx+70h]; Size
0x180049962  lea     rcx, [rsp+128h+pAsync]; void *
0x18004996a  call    memset_0
0x18004996f  mov     esi, [rsp+128h+dwMilliseconds]
0x180049973  mov     [rsp+128h+dwMilliseconds], esi
0x180049977  mov     [rsp+128h+var_C8], esi
0x18004997b  xor     r15b, r15b
0x18004997e  mov     [rsp+128h+var_D4], r15b
0x180049983  xor     r14b, r14b
0x180049986  xorps   xmm0, xmm0
0x180049989  movups  xmmword ptr [rsp+128h+Handles], xmm0
0x18004998e  mov     edx, 70h ; 'p'; Size
0x180049993  lea     rcx, [rsp+128h+pAsync]; pAsync
0x18004999b  call    cs:__imp_RpcAsyncInitializeHandle
0x1800499a1  test    eax, eax
0x1800499a3  jz      short loc_1800499C1
0x1800499a5  jle     short loc_1800499AF
0x1800499a7  movzx   eax, ax
0x1800499aa  or      eax, 80070000h
0x1800499af  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x1800499b6  mov     r8d, 2D5h
0x1800499bc  jmp     loc_180049B88
0x1800499c1  mov     [rsp+128h+pAsync.UserInfo], 0
0x1800499cd  mov     [rsp+128h+pAsync.NotificationType], 1
0x1800499d8  xor     r9d, r9d; lpName
0x1800499db  xor     r8d, r8d; bInitialState
0x1800499de  xor     edx, edx; bManualReset
0x1800499e0  xor     ecx, ecx; lpEventAttributes
0x1800499e2  call    cs:__imp_CreateEventW
0x1800499e8  mov     qword ptr [rsp+128h+pAsync.u], rax
0x1800499f0  test    rax, rax
0x1800499f3  jnz     short loc_180049A10
0x1800499f5  call    cs:__imp_GetLastError
0x1800499fb  test    eax, eax
0x1800499fd  jle     short loc_180049A07
0x1800499ff  movzx   eax, ax
0x180049a02  or      eax, 80070000h
0x180049a07  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180049a0e  jmp     short loc_1800499B6
0x180049a10  mov     [rsp+128h+Handles], rax
0x180049a15  mov     rax, [rsp+128h+var_C0]
0x180049a1a  mov     [rsp+128h+var_E8], rax
0x180049a1f  lea     rax, [rsp+128h+var_CC]
0x180049a24  mov     [rsp+128h+var_F0], rax
0x180049a29  mov     [rsp+128h+var_F8], r13
0x180049a2e  mov     [rsp+128h+var_100], 1
0x180049a36  mov     qword ptr [rsp+128h+bAlertable], r12
0x180049a3b  lea     r9, [rsp+128h+pAsync]
0x180049a43  xor     r8d, r8d; pReturnValue
0x180049a46  lea     edx, [r8+12h]; nProcNum
0x180049a4a  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180049a51  call    cs:__imp_Ndr64AsyncClientCall
0x180049a57  mov     eax, [rsp+128h+Reply]
0x180049a5b  jmp     short loc_180049AAC
0x180049a5d  test    eax, eax
0x180049a5f  jle     short loc_180049A69
0x180049a61  movzx   eax, ax
0x180049a64  or      eax, 80070000h
0x180049a69  mov     [rsp+128h+Reply], eax
0x180049a6d  mov     [rsp+128h+bAlertable], eax
0x180049a71  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180049a78  mov     r8d, 2D7h; unsigned int
0x180049a7e  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180049a85  mov     ecx, 2; unsigned __int8
0x180049a8a  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180049a8f  mov     eax, [rsp+128h+Reply]
0x180049a93  test    eax, eax
0x180049a95  js      short loc_180049AA0
0x180049a97  mov     eax, 8000FFFFh
0x180049a9c  mov     [rsp+128h+Reply], eax
0x180049aa0  mov     esi, [rsp+128h+dwMilliseconds]
0x180049aa4  mov     r15b, [rsp+128h+var_D4]
0x180049aa9  mov     r14b, r15b
0x180049aac  test    eax, eax
0x180049aae  jns     short loc_180049AC2
0x180049ab0  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180049ab7  mov     r8d, 2D7h
0x180049abd  jmp     loc_180049B8C
0x180049ac2  mov     [rsp+128h+bAlertable], 0; bAlertable
0x180049aca  mov     r9d, esi; dwMilliseconds
0x180049acd  xor     r8d, r8d; bWaitAll
0x180049ad0  lea     rdx, [rsp+128h+Handles]; lpHandles
0x180049ad5  lea     ecx, [r8+1]; nCount
0x180049ad9  call    cs:__imp_WaitForMultipleObjectsEx
0x180049adf  mov     esi, eax
0x180049ae1  mov     r12d, 102h
0x180049ae7  test    r14b, r14b
0x180049aea  jnz     short loc_180049B3B
0x180049aec  cmp     esi, r12d
0x180049aef  jz      short loc_180049AF6
0x180049af1  cmp     esi, 1
0x180049af4  jnz     short loc_180049B3B
0x180049af6  mov     edx, 1; fAbort
0x180049afb  lea     rcx, [rsp+128h+pAsync]; pAsync
0x180049b03  call    cs:__imp_RpcAsyncCancelCall
0x180049b09  cmp     esi, r12d
0x180049b0c  jnz     short loc_180049B13
0x180049b0e  mov     r15b, 1
0x180049b11  jmp     short loc_180049B16
0x180049b13  mov     r14b, 1
0x180049b16  mov     [rsp+128h+bAlertable], 0; bAlertable
0x180049b1e  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180049b22  xor     r8d, r8d; bWaitAll
0x180049b25  lea     rdx, [rsp+128h+Handles]; lpHandles
0x180049b2a  lea     ecx, [r8+1]; nCount
0x180049b2e  call    cs:__imp_WaitForMultipleObjectsEx
0x180049b34  mov     esi, eax
0x180049b36  test    r15b, r15b
0x180049b39  jz      short loc_180049AE7
0x180049b3b  test    esi, esi
0x180049b3d  jz      short loc_180049B5A
0x180049b3f  call    cs:__imp_GetLastError
0x180049b45  test    eax, eax
0x180049b47  jle     short loc_180049B51
0x180049b49  movzx   eax, ax
0x180049b4c  or      eax, 80070000h
0x180049b51  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180049b58  jmp     short loc_180049B82
0x180049b5a  lea     rdx, [rsp+128h+Reply]; Reply
0x180049b5f  lea     rcx, [rsp+128h+pAsync]; pAsync
0x180049b67  call    cs:__imp_RpcAsyncCompleteCall
0x180049b6d  test    eax, eax
0x180049b6f  jz      short loc_180049BA1
0x180049b71  jle     short loc_180049B7B
0x180049b73  movzx   eax, ax
0x180049b76  or      eax, 80070000h
0x180049b7b  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180049b82  mov     r8d, 2D7h; unsigned int
0x180049b88  mov     [rsp+128h+Reply], eax
0x180049b8c  mov     [rsp+128h+bAlertable], eax
0x180049b90  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180049b97  mov     ecx, 2; unsigned __int8
0x180049b9c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180049ba1  mov     rcx, qword ptr [rsp+128h+pAsync.u]; hObject
0x180049ba9  test    rcx, rcx
0x180049bac  jz      short loc_180049BB4
0x180049bae  call    cs:__imp_CloseHandle
0x180049bb4  test    r15b, r15b
0x180049bb7  jz      short loc_180049BF8
0x180049bb9  mov     [rsp+128h+Reply], 800705B4h
0x180049bc1  lea     rdx, [rsp+128h+var_C8]
0x180049bc6  lea     rcx, aWlidcgetcached; "WLIDCGetCachedTokens"
0x180049bcd  call    ??$RPCCallTimedOut@AEAY0BF@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BF@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],ulong &>(char const (&)[21],ulong &)
0x180049bd2  mov     eax, [rsp+128h+Reply]
0x180049bd6  mov     [rsp+128h+bAlertable], eax
0x180049bda  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180049be1  mov     r8d, 2D7h; unsigned int
0x180049be7  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180049bee  mov     ecx, 2; unsigned __int8
0x180049bf3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180049bf8  test    r14b, r14b
0x180049bfb  jz      short loc_180049C28
0x180049bfd  mov     eax, 800704C7h
0x180049c02  mov     [rsp+128h+Reply], eax
0x180049c06  mov     [rsp+128h+bAlertable], eax
0x180049c0a  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180049c11  mov     r8d, 2D7h; unsigned int
0x180049c17  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180049c1e  mov     ecx, 2; unsigned __int8
0x180049c23  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180049c28  mov     eax, [rsp+128h+Reply]
0x180049c2c  cmp     eax, 800706B5h
0x180049c31  jz      short loc_180049C3A
0x180049c33  cmp     eax, 800706BAh
0x180049c38  jnz     short loc_180049C43
0x180049c3a  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180049c3f  mov     eax, [rsp+128h+Reply]
0x180049c43  mov     rcx, [rsp+128h+var_38]
0x180049c4b  xor     rcx, rsp; StackCookie
0x180049c4e  call    __security_check_cookie
0x180049c53  add     rsp, 100h
0x180049c5a  pop     r15
0x180049c5c  pop     r14
0x180049c5e  pop     r13
0x180049c60  pop     r12
0x180049c62  pop     rsi
0x180049c63  retn
0x1800619d4  push    rbp
0x1800619d6  sub     rsp, 50h
0x1800619da  mov     rbp, rdx
0x1800619dd  mov     rcx, [rcx]
0x1800619e0  mov     ecx, [rcx]; unsigned int
0x1800619e2  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x1800619e7  nop
0x1800619e8  add     rsp, 50h
0x1800619ec  pop     rbp
0x1800619ed  retn
```
