# WLIDCGetCachedTokens(void * const,ulong,_WLIDRequestParams * const,_WLIDResponseParams * *)

- ea: `0x180045ccc`
- end: `0x18004602b`
- name: `?WLIDCGetCachedTokens@@YAJQEAXKQEAU_WLIDRequestParams@@PEAPEAU_WLIDResponseParams@@@Z`
- size: `863`
- prototype: `__int64 __fastcall(void *const, unsigned int, struct _WLIDRequestParams *const, struct _WLIDResponseParams **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800416c0`

## callees

- `0x18000a400`
- `0x180010c68`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180041c80`
- `0x180043240`
- `0x180045ccc`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180045da7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180045da7`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180045ea0`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180045ef5`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180045ea0`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180045ef5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045dba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045f06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045dba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045f06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045f75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045f75`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180045d60`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180045d60`
- `RPCRT4!RpcAsyncCancelCall` at `0x180045eca`
- `RPCRT4!RpcAsyncCancelCall` at `0x180045eca`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180045e18`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180045e18`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180045f2e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180045f2e`

## string_xrefs

- `0x180045dcc`: `RPC failed to create new event, hr = %#x`
- `0x180045f42`: `RPC Async complete call failed, hr = %#x`
- `0x180045f8d`: `WLIDCGetCachedTokens`

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
  BOOL bAlertable[2]; // [rsp+20h] [rbp-118h]
  unsigned int Reply; // [rsp+50h] [rbp-E8h] BYREF
  char v17; // [rsp+54h] [rbp-E4h]
  DWORD dwMilliseconds; // [rsp+58h] [rbp-E0h] BYREF
  int v19; // [rsp+5Ch] [rbp-DCh] BYREF
  DWORD v20; // [rsp+60h] [rbp-D8h] BYREF
  struct _WLIDResponseParams **v21; // [rsp+68h] [rbp-D0h]
  struct _WLIDRequestParams *v22; // [rsp+70h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+78h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+90h] [rbp-A8h] BYREF

  v21 = a4;
  v22 = a3;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x12u, 0, &pAsync, a1, a2, v22, &v19, v21);
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],unsigned long &>("WLIDCGetCachedTokens", &v20);
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
0x180045ccc  push    rsi
0x180045cce  push    r12
0x180045cd0  push    r13
0x180045cd2  push    r14
0x180045cd4  push    r15
0x180045cd6  sub     rsp, 110h
0x180045cdd  mov     rax, cs:__security_cookie
0x180045ce4  xor     rax, rsp
0x180045ce7  mov     [rsp+138h+var_38], rax
0x180045cef  mov     [rsp+138h+var_D0], r9
0x180045cf4  mov     [rsp+138h+var_C8], r8
0x180045cf9  mov     r13d, edx
0x180045cfc  mov     r12, rcx
0x180045cff  mov     [rsp+138h+var_DC], 0
0x180045d07  mov     [rsp+138h+Reply], 0
0x180045d0f  mov     [rsp+138h+dwMilliseconds], 0
0x180045d17  lea     r8, [rsp+138h+dwMilliseconds]; unsigned int *
0x180045d1c  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180045d21  xor     edx, edx; Val
0x180045d23  lea     r8d, [rdx+70h]; Size
0x180045d27  lea     rcx, [rsp+138h+pAsync]; void *
0x180045d2f  call    memset_0
0x180045d34  mov     esi, [rsp+138h+dwMilliseconds]
0x180045d38  mov     [rsp+138h+dwMilliseconds], esi
0x180045d3c  mov     [rsp+138h+var_D8], esi
0x180045d40  xor     r15b, r15b
0x180045d43  mov     [rsp+138h+var_E4], r15b
0x180045d48  xor     r14b, r14b
0x180045d4b  xorps   xmm0, xmm0
0x180045d4e  movups  xmmword ptr [rsp+138h+Handles], xmm0
0x180045d53  mov     edx, 70h ; 'p'; Size
0x180045d58  lea     rcx, [rsp+138h+pAsync]; pAsync
0x180045d60  call    cs:__imp_RpcAsyncInitializeHandle
0x180045d66  test    eax, eax
0x180045d68  jz      short loc_180045D86
0x180045d6a  jle     short loc_180045D74
0x180045d6c  movzx   eax, ax
0x180045d6f  or      eax, 80070000h
0x180045d74  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180045d7b  mov     r8d, 2D5h
0x180045d81  jmp     loc_180045F4F
0x180045d86  mov     [rsp+138h+pAsync.UserInfo], 0
0x180045d92  mov     [rsp+138h+pAsync.NotificationType], 1
0x180045d9d  xor     r9d, r9d; lpName
0x180045da0  xor     r8d, r8d; bInitialState
0x180045da3  xor     edx, edx; bManualReset
0x180045da5  xor     ecx, ecx; lpEventAttributes
0x180045da7  call    cs:__imp_CreateEventW
0x180045dad  mov     qword ptr [rsp+138h+pAsync.u], rax
0x180045db5  test    rax, rax
0x180045db8  jnz     short loc_180045DD5
0x180045dba  call    cs:__imp_GetLastError
0x180045dc0  test    eax, eax
0x180045dc2  jle     short loc_180045DCC
0x180045dc4  movzx   eax, ax
0x180045dc7  or      eax, 80070000h
0x180045dcc  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180045dd3  jmp     short loc_180045D7B
0x180045dd5  mov     [rsp+138h+Handles], rax
0x180045dda  mov     rax, [rsp+138h+var_D0]
0x180045ddf  mov     [rsp+138h+var_F8], rax
0x180045de4  lea     rax, [rsp+138h+var_DC]
0x180045de9  mov     [rsp+138h+var_100], rax
0x180045dee  mov     rax, [rsp+138h+var_C8]
0x180045df3  mov     [rsp+138h+var_108], rax
0x180045df8  mov     [rsp+138h+var_110], r13d
0x180045dfd  mov     qword ptr [rsp+138h+bAlertable], r12
0x180045e02  lea     r9, [rsp+138h+pAsync]
0x180045e0a  xor     r8d, r8d; pReturnValue
0x180045e0d  lea     edx, [r8+12h]; nProcNum
0x180045e11  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180045e18  call    cs:__imp_Ndr64AsyncClientCall
0x180045e1e  mov     eax, [rsp+138h+Reply]
0x180045e22  jmp     short loc_180045E73
0x180045e24  test    eax, eax
0x180045e26  jle     short loc_180045E30
0x180045e28  movzx   eax, ax
0x180045e2b  or      eax, 80070000h
0x180045e30  mov     [rsp+138h+Reply], eax
0x180045e34  mov     [rsp+138h+bAlertable], eax
0x180045e38  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180045e3f  mov     r8d, 2D7h; unsigned int
0x180045e45  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180045e4c  mov     ecx, 2; unsigned __int8
0x180045e51  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180045e56  mov     eax, [rsp+138h+Reply]
0x180045e5a  test    eax, eax
0x180045e5c  js      short loc_180045E67
0x180045e5e  mov     eax, 8000FFFFh
0x180045e63  mov     [rsp+138h+Reply], eax
0x180045e67  mov     esi, [rsp+138h+dwMilliseconds]
0x180045e6b  mov     r15b, [rsp+138h+var_E4]
0x180045e70  mov     r14b, r15b
0x180045e73  test    eax, eax
0x180045e75  jns     short loc_180045E89
0x180045e77  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180045e7e  mov     r8d, 2D7h
0x180045e84  jmp     loc_180045F53
0x180045e89  mov     [rsp+138h+bAlertable], 0; bAlertable
0x180045e91  mov     r9d, esi; dwMilliseconds
0x180045e94  xor     r8d, r8d; bWaitAll
0x180045e97  lea     rdx, [rsp+138h+Handles]; lpHandles
0x180045e9c  lea     ecx, [r8+1]; nCount
0x180045ea0  call    cs:__imp_WaitForMultipleObjectsEx
0x180045ea6  mov     esi, eax
0x180045ea8  mov     r12d, 102h
0x180045eae  test    r14b, r14b
0x180045eb1  jnz     short loc_180045F02
0x180045eb3  cmp     esi, r12d
0x180045eb6  jz      short loc_180045EBD
0x180045eb8  cmp     esi, 1
0x180045ebb  jnz     short loc_180045F02
0x180045ebd  mov     edx, 1; fAbort
0x180045ec2  lea     rcx, [rsp+138h+pAsync]; pAsync
0x180045eca  call    cs:__imp_RpcAsyncCancelCall
0x180045ed0  cmp     esi, r12d
0x180045ed3  jnz     short loc_180045EDA
0x180045ed5  mov     r15b, 1
0x180045ed8  jmp     short loc_180045EDD
0x180045eda  mov     r14b, 1
0x180045edd  mov     [rsp+138h+bAlertable], 0; bAlertable
0x180045ee5  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180045ee9  xor     r8d, r8d; bWaitAll
0x180045eec  lea     rdx, [rsp+138h+Handles]; lpHandles
0x180045ef1  lea     ecx, [r8+1]; nCount
0x180045ef5  call    cs:__imp_WaitForMultipleObjectsEx
0x180045efb  mov     esi, eax
0x180045efd  test    r15b, r15b
0x180045f00  jz      short loc_180045EAE
0x180045f02  test    esi, esi
0x180045f04  jz      short loc_180045F21
0x180045f06  call    cs:__imp_GetLastError
0x180045f0c  test    eax, eax
0x180045f0e  jle     short loc_180045F18
0x180045f10  movzx   eax, ax
0x180045f13  or      eax, 80070000h
0x180045f18  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180045f1f  jmp     short loc_180045F49
0x180045f21  lea     rdx, [rsp+138h+Reply]; Reply
0x180045f26  lea     rcx, [rsp+138h+pAsync]; pAsync
0x180045f2e  call    cs:__imp_RpcAsyncCompleteCall
0x180045f34  test    eax, eax
0x180045f36  jz      short loc_180045F68
0x180045f38  jle     short loc_180045F42
0x180045f3a  movzx   eax, ax
0x180045f3d  or      eax, 80070000h
0x180045f42  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180045f49  mov     r8d, 2D7h; unsigned int
0x180045f4f  mov     [rsp+138h+Reply], eax
0x180045f53  mov     [rsp+138h+bAlertable], eax
0x180045f57  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180045f5e  mov     ecx, 2; unsigned __int8
0x180045f63  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180045f68  mov     rcx, qword ptr [rsp+138h+pAsync.u]; hObject
0x180045f70  test    rcx, rcx
0x180045f73  jz      short loc_180045F7B
0x180045f75  call    cs:__imp_CloseHandle
0x180045f7b  test    r15b, r15b
0x180045f7e  jz      short loc_180045FBF
0x180045f80  mov     [rsp+138h+Reply], 800705B4h
0x180045f88  lea     rdx, [rsp+138h+var_D8]
0x180045f8d  lea     rcx, aWlidcgetcached; "WLIDCGetCachedTokens"
0x180045f94  call    ??$RPCCallTimedOut@AEAY0BF@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BF@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],ulong &>(char const (&)[21],ulong &)
0x180045f99  mov     eax, [rsp+138h+Reply]
0x180045f9d  mov     [rsp+138h+bAlertable], eax
0x180045fa1  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180045fa8  mov     r8d, 2D7h; unsigned int
0x180045fae  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180045fb5  mov     ecx, 2; unsigned __int8
0x180045fba  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180045fbf  test    r14b, r14b
0x180045fc2  jz      short loc_180045FEF
0x180045fc4  mov     eax, 800704C7h
0x180045fc9  mov     [rsp+138h+Reply], eax
0x180045fcd  mov     [rsp+138h+bAlertable], eax
0x180045fd1  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180045fd8  mov     r8d, 2D7h; unsigned int
0x180045fde  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180045fe5  mov     ecx, 2; unsigned __int8
0x180045fea  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180045fef  mov     eax, [rsp+138h+Reply]
0x180045ff3  cmp     eax, 800706B5h
0x180045ff8  jz      short loc_180046001
0x180045ffa  cmp     eax, 800706BAh
0x180045fff  jnz     short loc_18004600A
0x180046001  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180046006  mov     eax, [rsp+138h+Reply]
0x18004600a  mov     rcx, [rsp+138h+var_38]
0x180046012  xor     rcx, rsp; StackCookie
0x180046015  call    __security_check_cookie
0x18004601a  add     rsp, 110h
0x180046021  pop     r15
0x180046023  pop     r14
0x180046025  pop     r13
0x180046027  pop     r12
0x180046029  pop     rsi
0x18004602a  retn
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
