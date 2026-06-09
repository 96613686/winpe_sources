# WLIDCDisconnectIdentity(void * const)

- ea: `0x1800459bc`
- end: `0x180045cc3`
- name: `?WLIDCDisconnectIdentity@@YAJQEAX@Z`
- size: `775`
- prototype: `__int64 __fastcall(void *const)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800247c0`
- `0x180041680`

## callees

- `0x18000a400`
- `0x180010c68`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180041e24`
- `0x180043240`
- `0x1800459bc`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180045a74`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180045a74`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180045b47`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180045b99`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180045b47`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180045b99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045a87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045baa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045a87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045baa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045c16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045c16`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180045a33`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180045a33`
- `RPCRT4!RpcAsyncCancelCall` at `0x180045b6e`
- `RPCRT4!RpcAsyncCancelCall` at `0x180045b6e`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180045abf`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180045abf`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180045bcf`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180045bcf`

## string_xrefs

- `0x180045a99`: `RPC failed to create new event, hr = %#x`
- `0x180045be3`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCDisconnectIdentity(void *const a1, unsigned int a2)
{
  DWORD v3; // esi
  char v4; // r15
  char v5; // r14
  int LastError; // eax
  const unsigned __int16 *v7; // r9
  unsigned int v8; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v10; // esi
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-D8h]
  unsigned int Reply; // [rsp+30h] [rbp-C8h] BYREF
  char v15; // [rsp+34h] [rbp-C4h]
  DWORD dwMilliseconds; // [rsp+38h] [rbp-C0h] BYREF
  DWORD v17; // [rsp+3Ch] [rbp-BCh] BYREF
  HANDLE Handles[2]; // [rsp+40h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+50h] [rbp-A8h] BYREF

  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v3 = dwMilliseconds;
  v17 = dwMilliseconds;
  v4 = 0;
  v15 = 0;
  v5 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v8 = 509;
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
    v7 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_5;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 5u, 0, &pAsync, a1);
  v10 = WaitForMultipleObjectsEx(1u, Handles, 0, v3, 0);
  do
  {
    if ( v5 || v10 != 258 && v10 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v10 == 258 )
      v4 = 1;
    else
      v5 = 1;
    v10 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v4 );
  if ( v10 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = L"Encountered error while waiting on RPC call, hr = %#x";
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_28;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = L"RPC Async complete call failed, hr = %#x";
  }
  v8 = 511;
LABEL_27:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(2u, "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp", v8, v7, *(_QWORD *)bAlertable);
LABEL_28:
  NotificationRoutine = pAsync.u.APC.NotificationRoutine;
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v4 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[24],unsigned long &>(NotificationRoutine, &v17);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x1FFu,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v5 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x1FFu,
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
0x1800459bc  push    rsi
0x1800459be  push    r12
0x1800459c0  push    r14
0x1800459c2  push    r15
0x1800459c4  sub     rsp, 0D8h
0x1800459cb  mov     rax, cs:__security_cookie
0x1800459d2  xor     rax, rsp
0x1800459d5  mov     [rsp+0F8h+var_38], rax
0x1800459dd  mov     r12, rcx
0x1800459e0  mov     [rsp+0F8h+Reply], 0
0x1800459e8  mov     [rsp+0F8h+dwMilliseconds], 0
0x1800459f0  lea     r8, [rsp+0F8h+dwMilliseconds]; unsigned int *
0x1800459f5  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x1800459fa  xor     edx, edx; Val
0x1800459fc  lea     r8d, [rdx+70h]; Size
0x180045a00  lea     rcx, [rsp+0F8h+pAsync]; void *
0x180045a05  call    memset_0
0x180045a0a  mov     esi, [rsp+0F8h+dwMilliseconds]
0x180045a0e  mov     [rsp+0F8h+dwMilliseconds], esi
0x180045a12  mov     [rsp+0F8h+var_BC], esi
0x180045a16  xor     r15b, r15b
0x180045a19  mov     [rsp+0F8h+var_C4], r15b
0x180045a1e  xor     r14b, r14b
0x180045a21  xorps   xmm0, xmm0
0x180045a24  movups  xmmword ptr [rsp+0F8h+Handles], xmm0
0x180045a29  mov     edx, 70h ; 'p'; Size
0x180045a2e  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x180045a33  call    cs:__imp_RpcAsyncInitializeHandle
0x180045a39  test    eax, eax
0x180045a3b  jz      short loc_180045A59
0x180045a3d  jle     short loc_180045A47
0x180045a3f  movzx   eax, ax
0x180045a42  or      eax, 80070000h
0x180045a47  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180045a4e  mov     r8d, 1FDh
0x180045a54  jmp     loc_180045BF0
0x180045a59  mov     [rsp+0F8h+pAsync.UserInfo], 0
0x180045a62  mov     [rsp+0F8h+pAsync.NotificationType], 1
0x180045a6a  xor     r9d, r9d; lpName
0x180045a6d  xor     r8d, r8d; bInitialState
0x180045a70  xor     edx, edx; bManualReset
0x180045a72  xor     ecx, ecx; lpEventAttributes
0x180045a74  call    cs:__imp_CreateEventW
0x180045a7a  mov     qword ptr [rsp+0F8h+pAsync.u], rax
0x180045a82  test    rax, rax
0x180045a85  jnz     short loc_180045AA2
0x180045a87  call    cs:__imp_GetLastError
0x180045a8d  test    eax, eax
0x180045a8f  jle     short loc_180045A99
0x180045a91  movzx   eax, ax
0x180045a94  or      eax, 80070000h
0x180045a99  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180045aa0  jmp     short loc_180045A4E
0x180045aa2  mov     [rsp+0F8h+Handles], rax
0x180045aa7  mov     qword ptr [rsp+0F8h+bAlertable], r12
0x180045aac  lea     r9, [rsp+0F8h+pAsync]
0x180045ab1  xor     r8d, r8d; pReturnValue
0x180045ab4  lea     edx, [r8+5]; nProcNum
0x180045ab8  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180045abf  call    cs:__imp_Ndr64AsyncClientCall
0x180045ac5  mov     eax, [rsp+0F8h+Reply]
0x180045ac9  jmp     short loc_180045B1A
0x180045acb  test    eax, eax
0x180045acd  jle     short loc_180045AD7
0x180045acf  movzx   eax, ax
0x180045ad2  or      eax, 80070000h
0x180045ad7  mov     [rsp+0F8h+Reply], eax
0x180045adb  mov     [rsp+0F8h+bAlertable], eax
0x180045adf  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180045ae6  mov     r8d, 1FFh; unsigned int
0x180045aec  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180045af3  mov     ecx, 2; unsigned __int8
0x180045af8  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180045afd  mov     eax, [rsp+0F8h+Reply]
0x180045b01  test    eax, eax
0x180045b03  js      short loc_180045B0E
0x180045b05  mov     eax, 8000FFFFh
0x180045b0a  mov     [rsp+0F8h+Reply], eax
0x180045b0e  mov     esi, [rsp+0F8h+dwMilliseconds]
0x180045b12  mov     r15b, [rsp+0F8h+var_C4]
0x180045b17  mov     r14b, r15b
0x180045b1a  test    eax, eax
0x180045b1c  jns     short loc_180045B30
0x180045b1e  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180045b25  mov     r8d, 1FFh
0x180045b2b  jmp     loc_180045BF4
0x180045b30  mov     [rsp+0F8h+bAlertable], 0; bAlertable
0x180045b38  mov     r9d, esi; dwMilliseconds
0x180045b3b  xor     r8d, r8d; bWaitAll
0x180045b3e  lea     rdx, [rsp+0F8h+Handles]; lpHandles
0x180045b43  lea     ecx, [r8+1]; nCount
0x180045b47  call    cs:__imp_WaitForMultipleObjectsEx
0x180045b4d  mov     esi, eax
0x180045b4f  mov     r12d, 102h
0x180045b55  test    r14b, r14b
0x180045b58  jnz     short loc_180045BA6
0x180045b5a  cmp     esi, r12d
0x180045b5d  jz      short loc_180045B64
0x180045b5f  cmp     esi, 1
0x180045b62  jnz     short loc_180045BA6
0x180045b64  mov     edx, 1; fAbort
0x180045b69  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x180045b6e  call    cs:__imp_RpcAsyncCancelCall
0x180045b74  cmp     esi, r12d
0x180045b77  jnz     short loc_180045B7E
0x180045b79  mov     r15b, 1
0x180045b7c  jmp     short loc_180045B81
0x180045b7e  mov     r14b, 1
0x180045b81  mov     [rsp+0F8h+bAlertable], 0; bAlertable
0x180045b89  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180045b8d  xor     r8d, r8d; bWaitAll
0x180045b90  lea     rdx, [rsp+0F8h+Handles]; lpHandles
0x180045b95  lea     ecx, [r8+1]; nCount
0x180045b99  call    cs:__imp_WaitForMultipleObjectsEx
0x180045b9f  mov     esi, eax
0x180045ba1  test    r15b, r15b
0x180045ba4  jz      short loc_180045B55
0x180045ba6  test    esi, esi
0x180045ba8  jz      short loc_180045BC5
0x180045baa  call    cs:__imp_GetLastError
0x180045bb0  test    eax, eax
0x180045bb2  jle     short loc_180045BBC
0x180045bb4  movzx   eax, ax
0x180045bb7  or      eax, 80070000h
0x180045bbc  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180045bc3  jmp     short loc_180045BEA
0x180045bc5  lea     rdx, [rsp+0F8h+Reply]; Reply
0x180045bca  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x180045bcf  call    cs:__imp_RpcAsyncCompleteCall
0x180045bd5  test    eax, eax
0x180045bd7  jz      short loc_180045C09
0x180045bd9  jle     short loc_180045BE3
0x180045bdb  movzx   eax, ax
0x180045bde  or      eax, 80070000h
0x180045be3  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180045bea  mov     r8d, 1FFh; unsigned int
0x180045bf0  mov     [rsp+0F8h+Reply], eax
0x180045bf4  mov     [rsp+0F8h+bAlertable], eax
0x180045bf8  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180045bff  mov     ecx, 2; unsigned __int8
0x180045c04  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180045c09  mov     rcx, qword ptr [rsp+0F8h+pAsync.u]; hObject
0x180045c11  test    rcx, rcx
0x180045c14  jz      short loc_180045C1C
0x180045c16  call    cs:__imp_CloseHandle
0x180045c1c  test    r15b, r15b
0x180045c1f  jz      short loc_180045C59
0x180045c21  mov     [rsp+0F8h+Reply], 800705B4h
0x180045c29  lea     rdx, [rsp+0F8h+var_BC]
0x180045c2e  call    ??$RPCCallTimedOut@AEAY0BI@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BI@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[24],ulong &>(char const (&)[24],ulong &)
0x180045c33  mov     eax, [rsp+0F8h+Reply]
0x180045c37  mov     [rsp+0F8h+bAlertable], eax
0x180045c3b  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180045c42  mov     r8d, 1FFh; unsigned int
0x180045c48  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180045c4f  mov     ecx, 2; unsigned __int8
0x180045c54  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180045c59  test    r14b, r14b
0x180045c5c  jz      short loc_180045C89
0x180045c5e  mov     eax, 800704C7h
0x180045c63  mov     [rsp+0F8h+Reply], eax
0x180045c67  mov     [rsp+0F8h+bAlertable], eax
0x180045c6b  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180045c72  mov     r8d, 1FFh; unsigned int
0x180045c78  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180045c7f  mov     ecx, 2; unsigned __int8
0x180045c84  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180045c89  mov     eax, [rsp+0F8h+Reply]
0x180045c8d  cmp     eax, 800706B5h
0x180045c92  jz      short loc_180045C9B
0x180045c94  cmp     eax, 800706BAh
0x180045c99  jnz     short loc_180045CA4
0x180045c9b  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180045ca0  mov     eax, [rsp+0F8h+Reply]
0x180045ca4  mov     rcx, [rsp+0F8h+var_38]
0x180045cac  xor     rcx, rsp; StackCookie
0x180045caf  call    __security_check_cookie
0x180045cb4  add     rsp, 0D8h
0x180045cbb  pop     r15
0x180045cbd  pop     r14
0x180045cbf  pop     r12
0x180045cc1  pop     rsi
0x180045cc2  retn
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
