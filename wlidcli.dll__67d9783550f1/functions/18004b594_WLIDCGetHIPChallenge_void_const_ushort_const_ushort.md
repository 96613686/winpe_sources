# WLIDCGetHIPChallenge(void * const,ushort const *,ushort * *)

- ea: `0x18004b594`
- end: `0x18004b8c3`
- name: `?WLIDCGetHIPChallenge@@YAJQEAXPEBGPEAPEAG@Z`
- size: `815`
- prototype: `__int64 __fastcall(void *const, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002f250`
- `0x18003be90`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180044fc4`
- `0x180046ce0`
- `0x18004b594`
- `0x18004cd04`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004b73e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004b790`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004b73e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004b790`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004b65c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004b65c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b66f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b7a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b66f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b7a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b80d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b80d`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004b765`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004b765`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004b6b6`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004b6b6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004b7c6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004b7c6`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004b615`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004b615`

## string_xrefs

- `0x18004b681`: `RPC failed to create new event, hr = %#x`
- `0x18004b7da`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCGetHIPChallenge(void *const a1, const unsigned __int16 *a2, unsigned __int16 **a3)
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
  unsigned __int16 **v19; // [rsp+50h] [rbp-C8h]
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
    v10 = 1024;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x2Eu, 0, &pAsync, a1, a2, v19);
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
  v10 = 1026;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],unsigned long &>(
      (__int64)"WLIDCGetHIPChallenge",
      (int *)&v18);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x402u,
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
      0x402u,
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
0x18004b594  push    rsi
0x18004b596  push    r12
0x18004b598  push    r13
0x18004b59a  push    r14
0x18004b59c  push    r15
0x18004b59e  sub     rsp, 0F0h
0x18004b5a5  mov     rax, cs:__security_cookie
0x18004b5ac  xor     rax, rsp
0x18004b5af  mov     [rsp+118h+var_38], rax
0x18004b5b7  mov     [rsp+118h+var_C8], r8
0x18004b5bc  mov     r13, rdx
0x18004b5bf  mov     r12, rcx
0x18004b5c2  mov     [rsp+118h+Reply], 0
0x18004b5ca  mov     [rsp+118h+dwMilliseconds], 0
0x18004b5d2  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x18004b5d7  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004b5dc  xor     edx, edx; Val
0x18004b5de  lea     r8d, [rdx+70h]; Size
0x18004b5e2  lea     rcx, [rsp+118h+pAsync]; void *
0x18004b5e7  call    memset_0
0x18004b5ec  mov     esi, [rsp+118h+dwMilliseconds]
0x18004b5f0  mov     [rsp+118h+dwMilliseconds], esi
0x18004b5f4  mov     [rsp+118h+var_CC], esi
0x18004b5f8  xor     r15b, r15b
0x18004b5fb  mov     [rsp+118h+var_D4], r15b
0x18004b600  xor     r14b, r14b
0x18004b603  xorps   xmm0, xmm0
0x18004b606  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x18004b60b  mov     edx, 70h ; 'p'; Size
0x18004b610  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004b615  call    cs:__imp_RpcAsyncInitializeHandle
0x18004b61b  test    eax, eax
0x18004b61d  jz      short loc_18004B63B
0x18004b61f  jle     short loc_18004B629
0x18004b621  movzx   eax, ax
0x18004b624  or      eax, 80070000h
0x18004b629  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004b630  mov     r8d, 400h
0x18004b636  jmp     loc_18004B7E7
0x18004b63b  mov     [rsp+118h+pAsync.UserInfo], 0
0x18004b647  mov     [rsp+118h+pAsync.NotificationType], 1
0x18004b652  xor     r9d, r9d; lpName
0x18004b655  xor     r8d, r8d; bInitialState
0x18004b658  xor     edx, edx; bManualReset
0x18004b65a  xor     ecx, ecx; lpEventAttributes
0x18004b65c  call    cs:__imp_CreateEventW
0x18004b662  mov     qword ptr [rsp+118h+pAsync.u], rax
0x18004b66a  test    rax, rax
0x18004b66d  jnz     short loc_18004B68A
0x18004b66f  call    cs:__imp_GetLastError
0x18004b675  test    eax, eax
0x18004b677  jle     short loc_18004B681
0x18004b679  movzx   eax, ax
0x18004b67c  or      eax, 80070000h
0x18004b681  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004b688  jmp     short loc_18004B630
0x18004b68a  mov     [rsp+118h+Handles], rax
0x18004b68f  mov     rax, [rsp+118h+var_C8]
0x18004b694  mov     [rsp+118h+var_E8], rax
0x18004b699  mov     [rsp+118h+var_F0], r13
0x18004b69e  mov     qword ptr [rsp+118h+bAlertable], r12
0x18004b6a3  lea     r9, [rsp+118h+pAsync]
0x18004b6a8  xor     r8d, r8d; pReturnValue
0x18004b6ab  lea     edx, [r8+2Eh]; nProcNum
0x18004b6af  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004b6b6  call    cs:__imp_Ndr64AsyncClientCall
0x18004b6bc  mov     eax, [rsp+118h+Reply]
0x18004b6c0  jmp     short loc_18004B711
0x18004b6c2  test    eax, eax
0x18004b6c4  jle     short loc_18004B6CE
0x18004b6c6  movzx   eax, ax
0x18004b6c9  or      eax, 80070000h
0x18004b6ce  mov     [rsp+118h+Reply], eax
0x18004b6d2  mov     [rsp+118h+bAlertable], eax
0x18004b6d6  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004b6dd  mov     r8d, 402h; unsigned int
0x18004b6e3  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004b6ea  mov     ecx, 2; unsigned __int8
0x18004b6ef  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004b6f4  mov     eax, [rsp+118h+Reply]
0x18004b6f8  test    eax, eax
0x18004b6fa  js      short loc_18004B705
0x18004b6fc  mov     eax, 8000FFFFh
0x18004b701  mov     [rsp+118h+Reply], eax
0x18004b705  mov     esi, [rsp+118h+dwMilliseconds]
0x18004b709  mov     r15b, [rsp+118h+var_D4]
0x18004b70e  mov     r14b, r15b
0x18004b711  test    eax, eax
0x18004b713  jns     short loc_18004B727
0x18004b715  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004b71c  mov     r8d, 402h
0x18004b722  jmp     loc_18004B7EB
0x18004b727  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004b72f  mov     r9d, esi; dwMilliseconds
0x18004b732  xor     r8d, r8d; bWaitAll
0x18004b735  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004b73a  lea     ecx, [r8+1]; nCount
0x18004b73e  call    cs:__imp_WaitForMultipleObjectsEx
0x18004b744  mov     esi, eax
0x18004b746  mov     r12d, 102h
0x18004b74c  test    r14b, r14b
0x18004b74f  jnz     short loc_18004B79D
0x18004b751  cmp     esi, r12d
0x18004b754  jz      short loc_18004B75B
0x18004b756  cmp     esi, 1
0x18004b759  jnz     short loc_18004B79D
0x18004b75b  mov     edx, 1; fAbort
0x18004b760  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004b765  call    cs:__imp_RpcAsyncCancelCall
0x18004b76b  cmp     esi, r12d
0x18004b76e  jnz     short loc_18004B775
0x18004b770  mov     r15b, 1
0x18004b773  jmp     short loc_18004B778
0x18004b775  mov     r14b, 1
0x18004b778  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004b780  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004b784  xor     r8d, r8d; bWaitAll
0x18004b787  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004b78c  lea     ecx, [r8+1]; nCount
0x18004b790  call    cs:__imp_WaitForMultipleObjectsEx
0x18004b796  mov     esi, eax
0x18004b798  test    r15b, r15b
0x18004b79b  jz      short loc_18004B74C
0x18004b79d  test    esi, esi
0x18004b79f  jz      short loc_18004B7BC
0x18004b7a1  call    cs:__imp_GetLastError
0x18004b7a7  test    eax, eax
0x18004b7a9  jle     short loc_18004B7B3
0x18004b7ab  movzx   eax, ax
0x18004b7ae  or      eax, 80070000h
0x18004b7b3  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004b7ba  jmp     short loc_18004B7E1
0x18004b7bc  lea     rdx, [rsp+118h+Reply]; Reply
0x18004b7c1  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004b7c6  call    cs:__imp_RpcAsyncCompleteCall
0x18004b7cc  test    eax, eax
0x18004b7ce  jz      short loc_18004B800
0x18004b7d0  jle     short loc_18004B7DA
0x18004b7d2  movzx   eax, ax
0x18004b7d5  or      eax, 80070000h
0x18004b7da  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004b7e1  mov     r8d, 402h; unsigned int
0x18004b7e7  mov     [rsp+118h+Reply], eax
0x18004b7eb  mov     [rsp+118h+bAlertable], eax
0x18004b7ef  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004b7f6  mov     ecx, 2; unsigned __int8
0x18004b7fb  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004b800  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x18004b808  test    rcx, rcx
0x18004b80b  jz      short loc_18004B813
0x18004b80d  call    cs:__imp_CloseHandle
0x18004b813  test    r15b, r15b
0x18004b816  jz      short loc_18004B857
0x18004b818  mov     [rsp+118h+Reply], 800705B4h
0x18004b820  lea     rdx, [rsp+118h+var_CC]
0x18004b825  lea     rcx, aWlidcgethipcha; "WLIDCGetHIPChallenge"
0x18004b82c  call    ??$RPCCallTimedOut@AEAY0BF@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BF@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],ulong &>(char const (&)[21],ulong &)
0x18004b831  mov     eax, [rsp+118h+Reply]
0x18004b835  mov     [rsp+118h+bAlertable], eax
0x18004b839  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004b840  mov     r8d, 402h; unsigned int
0x18004b846  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004b84d  mov     ecx, 2; unsigned __int8
0x18004b852  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004b857  test    r14b, r14b
0x18004b85a  jz      short loc_18004B887
0x18004b85c  mov     eax, 800704C7h
0x18004b861  mov     [rsp+118h+Reply], eax
0x18004b865  mov     [rsp+118h+bAlertable], eax
0x18004b869  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004b870  mov     r8d, 402h; unsigned int
0x18004b876  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004b87d  mov     ecx, 2; unsigned __int8
0x18004b882  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004b887  mov     eax, [rsp+118h+Reply]
0x18004b88b  cmp     eax, 800706B5h
0x18004b890  jz      short loc_18004B899
0x18004b892  cmp     eax, 800706BAh
0x18004b897  jnz     short loc_18004B8A2
0x18004b899  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004b89e  mov     eax, [rsp+118h+Reply]
0x18004b8a2  mov     rcx, [rsp+118h+var_38]
0x18004b8aa  xor     rcx, rsp; StackCookie
0x18004b8ad  call    __security_check_cookie
0x18004b8b2  add     rsp, 0F0h
0x18004b8b9  pop     r15
0x18004b8bb  pop     r14
0x18004b8bd  pop     r13
0x18004b8bf  pop     r12
0x18004b8c1  pop     rsi
0x18004b8c2  retn
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
