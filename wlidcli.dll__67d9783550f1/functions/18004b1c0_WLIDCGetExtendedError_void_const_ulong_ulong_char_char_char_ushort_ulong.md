# WLIDCGetExtendedError(void * const,ulong *,ulong *,char * *,char * *,char * *,ushort * *,ulong *)

- ea: `0x18004b1c0`
- end: `0x18004b58d`
- name: `?WLIDCGetExtendedError@@YAJQEAXPEAK1PEAPEAD22PEAPEAG1@Z`
- size: `973`
- prototype: `__int64 __fastcall(void *const, unsigned int *, unsigned int *, char **, char **, char **, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002df40`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180045050`
- `0x180046ce0`
- `0x18004b1c0`
- `0x18004cd04`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004b3ff`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004b457`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004b3ff`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004b457`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004b2d6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004b2d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b2e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b2e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b468`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b4d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b4d7`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004b429`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004b429`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004b374`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004b374`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004b490`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004b490`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004b28f`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004b28f`

## string_xrefs

- `0x18004b2fb`: `RPC failed to create new event, hr = %#x`
- `0x18004b4a4`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCGetExtendedError(
        void *const a1,
        unsigned int *a2,
        unsigned int *a3,
        char **a4,
        char **a5,
        char **a6,
        unsigned __int16 **a7,
        unsigned int *a8)
{
  DWORD v10; // esi
  char v11; // r15
  char v12; // r14
  int LastError; // eax
  const unsigned __int16 *v14; // r9
  unsigned int v15; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v17; // esi
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-138h]
  unsigned int Reply; // [rsp+60h] [rbp-F8h] BYREF
  char v21; // [rsp+64h] [rbp-F4h]
  DWORD dwMilliseconds; // [rsp+68h] [rbp-F0h] BYREF
  DWORD v23; // [rsp+6Ch] [rbp-ECh] BYREF
  unsigned int *v24; // [rsp+70h] [rbp-E8h]
  unsigned __int16 **v25; // [rsp+78h] [rbp-E0h]
  char **v26; // [rsp+80h] [rbp-D8h]
  char **v27; // [rsp+88h] [rbp-D0h]
  char **v28; // [rsp+90h] [rbp-C8h]
  unsigned int *v29; // [rsp+98h] [rbp-C0h]
  HANDLE Handles[2]; // [rsp+A0h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+B0h] [rbp-A8h] BYREF

  v28 = a4;
  v29 = a3;
  v27 = a5;
  v26 = a6;
  v25 = a7;
  v24 = a8;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v10 = dwMilliseconds;
  v23 = dwMilliseconds;
  v11 = 0;
  v21 = 0;
  v12 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v14 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v15 = 741;
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
    v14 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_5;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall(
    (MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo,
    0x13u,
    0,
    &pAsync,
    a1,
    a2,
    v29,
    v28,
    v27,
    v26,
    v25,
    v24);
  v17 = WaitForMultipleObjectsEx(1u, Handles, 0, v10, 0);
  do
  {
    if ( v12 || v17 != 258 && v17 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v17 == 258 )
      v11 = 1;
    else
      v12 = 1;
    v17 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v11 );
  if ( v17 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v14 = L"Encountered error while waiting on RPC call, hr = %#x";
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_28;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v14 = L"RPC Async complete call failed, hr = %#x";
  }
  v15 = 743;
LABEL_27:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(
    2u,
    "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
    v15,
    v14,
    *(_QWORD *)bAlertable);
LABEL_28:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v11 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[22],unsigned long &>(
      (__int64)"WLIDCGetExtendedError",
      (int *)&v23);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x2E7u,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v12 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x2E7u,
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
0x18004b1c0  push    rsi
0x18004b1c2  push    r12
0x18004b1c4  push    r13
0x18004b1c6  push    r14
0x18004b1c8  push    r15
0x18004b1ca  sub     rsp, 130h
0x18004b1d1  mov     rax, cs:__security_cookie
0x18004b1d8  xor     rax, rsp
0x18004b1db  mov     [rsp+158h+var_38], rax
0x18004b1e3  mov     [rsp+158h+var_C8], r9
0x18004b1eb  mov     [rsp+158h+var_C0], r8
0x18004b1f3  mov     r13, rdx
0x18004b1f6  mov     r12, rcx
0x18004b1f9  mov     rax, [rsp+158h+arg_20]
0x18004b201  mov     [rsp+158h+var_D0], rax
0x18004b209  mov     rax, [rsp+158h+arg_28]
0x18004b211  mov     [rsp+158h+var_D8], rax
0x18004b219  mov     rax, [rsp+158h+arg_30]
0x18004b221  mov     [rsp+158h+var_E0], rax
0x18004b226  mov     rax, [rsp+158h+arg_38]
0x18004b22e  mov     [rsp+158h+var_E8], rax
0x18004b233  mov     [rsp+158h+Reply], 0
0x18004b23b  mov     [rsp+158h+dwMilliseconds], 0
0x18004b243  lea     r8, [rsp+158h+dwMilliseconds]; unsigned int *
0x18004b248  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004b24d  xor     edx, edx; Val
0x18004b24f  lea     r8d, [rdx+70h]; Size
0x18004b253  lea     rcx, [rsp+158h+pAsync]; void *
0x18004b25b  call    memset_0
0x18004b260  mov     esi, [rsp+158h+dwMilliseconds]
0x18004b264  mov     [rsp+158h+dwMilliseconds], esi
0x18004b268  mov     [rsp+158h+var_EC], esi
0x18004b26c  xor     r15b, r15b
0x18004b26f  mov     [rsp+158h+var_F4], r15b
0x18004b274  xor     r14b, r14b
0x18004b277  xorps   xmm0, xmm0
0x18004b27a  movups  xmmword ptr [rsp+158h+Handles], xmm0
0x18004b282  mov     edx, 70h ; 'p'; Size
0x18004b287  lea     rcx, [rsp+158h+pAsync]; pAsync
0x18004b28f  call    cs:__imp_RpcAsyncInitializeHandle
0x18004b295  test    eax, eax
0x18004b297  jz      short loc_18004B2B5
0x18004b299  jle     short loc_18004B2A3
0x18004b29b  movzx   eax, ax
0x18004b29e  or      eax, 80070000h
0x18004b2a3  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004b2aa  mov     r8d, 2E5h
0x18004b2b0  jmp     loc_18004B4B1
0x18004b2b5  mov     [rsp+158h+pAsync.UserInfo], 0
0x18004b2c1  mov     [rsp+158h+pAsync.NotificationType], 1
0x18004b2cc  xor     r9d, r9d; lpName
0x18004b2cf  xor     r8d, r8d; bInitialState
0x18004b2d2  xor     edx, edx; bManualReset
0x18004b2d4  xor     ecx, ecx; lpEventAttributes
0x18004b2d6  call    cs:__imp_CreateEventW
0x18004b2dc  mov     qword ptr [rsp+158h+pAsync.u], rax
0x18004b2e4  test    rax, rax
0x18004b2e7  jnz     short loc_18004B304
0x18004b2e9  call    cs:__imp_GetLastError
0x18004b2ef  test    eax, eax
0x18004b2f1  jle     short loc_18004B2FB
0x18004b2f3  movzx   eax, ax
0x18004b2f6  or      eax, 80070000h
0x18004b2fb  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004b302  jmp     short loc_18004B2AA
0x18004b304  mov     [rsp+158h+Handles], rax
0x18004b30c  mov     rax, [rsp+158h+var_E8]
0x18004b311  mov     [rsp+158h+var_100], rax
0x18004b316  mov     rax, [rsp+158h+var_E0]
0x18004b31b  mov     [rsp+158h+var_108], rax
0x18004b320  mov     rax, [rsp+158h+var_D8]
0x18004b328  mov     [rsp+158h+var_110], rax
0x18004b32d  mov     rax, [rsp+158h+var_D0]
0x18004b335  mov     [rsp+158h+var_118], rax
0x18004b33a  mov     rax, [rsp+158h+var_C8]
0x18004b342  mov     [rsp+158h+var_120], rax
0x18004b347  mov     rax, [rsp+158h+var_C0]
0x18004b34f  mov     [rsp+158h+var_128], rax
0x18004b354  mov     [rsp+158h+var_130], r13
0x18004b359  mov     qword ptr [rsp+158h+bAlertable], r12
0x18004b35e  lea     r9, [rsp+158h+pAsync]
0x18004b366  xor     r8d, r8d; pReturnValue
0x18004b369  lea     edx, [r8+13h]; nProcNum
0x18004b36d  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004b374  call    cs:__imp_Ndr64AsyncClientCall
0x18004b37a  mov     eax, [rsp+158h+Reply]
0x18004b37e  jmp     short loc_18004B3CF
0x18004b380  test    eax, eax
0x18004b382  jle     short loc_18004B38C
0x18004b384  movzx   eax, ax
0x18004b387  or      eax, 80070000h
0x18004b38c  mov     [rsp+158h+Reply], eax
0x18004b390  mov     [rsp+158h+bAlertable], eax
0x18004b394  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004b39b  mov     r8d, 2E7h; unsigned int
0x18004b3a1  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004b3a8  mov     ecx, 2; unsigned __int8
0x18004b3ad  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004b3b2  mov     eax, [rsp+158h+Reply]
0x18004b3b6  test    eax, eax
0x18004b3b8  js      short loc_18004B3C3
0x18004b3ba  mov     eax, 8000FFFFh
0x18004b3bf  mov     [rsp+158h+Reply], eax
0x18004b3c3  mov     esi, [rsp+158h+dwMilliseconds]
0x18004b3c7  mov     r15b, [rsp+158h+var_F4]
0x18004b3cc  mov     r14b, r15b
0x18004b3cf  test    eax, eax
0x18004b3d1  jns     short loc_18004B3E5
0x18004b3d3  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004b3da  mov     r8d, 2E7h
0x18004b3e0  jmp     loc_18004B4B5
0x18004b3e5  mov     [rsp+158h+bAlertable], 0; bAlertable
0x18004b3ed  mov     r9d, esi; dwMilliseconds
0x18004b3f0  xor     r8d, r8d; bWaitAll
0x18004b3f3  lea     rdx, [rsp+158h+Handles]; lpHandles
0x18004b3fb  lea     ecx, [r8+1]; nCount
0x18004b3ff  call    cs:__imp_WaitForMultipleObjectsEx
0x18004b405  mov     esi, eax
0x18004b407  mov     r12d, 102h
0x18004b40d  test    r14b, r14b
0x18004b410  jnz     short loc_18004B464
0x18004b412  cmp     esi, r12d
0x18004b415  jz      short loc_18004B41C
0x18004b417  cmp     esi, 1
0x18004b41a  jnz     short loc_18004B464
0x18004b41c  mov     edx, 1; fAbort
0x18004b421  lea     rcx, [rsp+158h+pAsync]; pAsync
0x18004b429  call    cs:__imp_RpcAsyncCancelCall
0x18004b42f  cmp     esi, r12d
0x18004b432  jnz     short loc_18004B439
0x18004b434  mov     r15b, 1
0x18004b437  jmp     short loc_18004B43C
0x18004b439  mov     r14b, 1
0x18004b43c  mov     [rsp+158h+bAlertable], 0; bAlertable
0x18004b444  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004b448  xor     r8d, r8d; bWaitAll
0x18004b44b  lea     rdx, [rsp+158h+Handles]; lpHandles
0x18004b453  lea     ecx, [r8+1]; nCount
0x18004b457  call    cs:__imp_WaitForMultipleObjectsEx
0x18004b45d  mov     esi, eax
0x18004b45f  test    r15b, r15b
0x18004b462  jz      short loc_18004B40D
0x18004b464  test    esi, esi
0x18004b466  jz      short loc_18004B483
0x18004b468  call    cs:__imp_GetLastError
0x18004b46e  test    eax, eax
0x18004b470  jle     short loc_18004B47A
0x18004b472  movzx   eax, ax
0x18004b475  or      eax, 80070000h
0x18004b47a  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004b481  jmp     short loc_18004B4AB
0x18004b483  lea     rdx, [rsp+158h+Reply]; Reply
0x18004b488  lea     rcx, [rsp+158h+pAsync]; pAsync
0x18004b490  call    cs:__imp_RpcAsyncCompleteCall
0x18004b496  test    eax, eax
0x18004b498  jz      short loc_18004B4CA
0x18004b49a  jle     short loc_18004B4A4
0x18004b49c  movzx   eax, ax
0x18004b49f  or      eax, 80070000h
0x18004b4a4  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004b4ab  mov     r8d, 2E7h; unsigned int
0x18004b4b1  mov     [rsp+158h+Reply], eax
0x18004b4b5  mov     [rsp+158h+bAlertable], eax
0x18004b4b9  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004b4c0  mov     ecx, 2; unsigned __int8
0x18004b4c5  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004b4ca  mov     rcx, qword ptr [rsp+158h+pAsync.u]; hObject
0x18004b4d2  test    rcx, rcx
0x18004b4d5  jz      short loc_18004B4DD
0x18004b4d7  call    cs:__imp_CloseHandle
0x18004b4dd  test    r15b, r15b
0x18004b4e0  jz      short loc_18004B521
0x18004b4e2  mov     [rsp+158h+Reply], 800705B4h
0x18004b4ea  lea     rdx, [rsp+158h+var_EC]
0x18004b4ef  lea     rcx, aWlidcgetextend; "WLIDCGetExtendedError"
0x18004b4f6  call    ??$RPCCallTimedOut@AEAY0BG@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BG@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[22],ulong &>(char const (&)[22],ulong &)
0x18004b4fb  mov     eax, [rsp+158h+Reply]
0x18004b4ff  mov     [rsp+158h+bAlertable], eax
0x18004b503  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004b50a  mov     r8d, 2E7h; unsigned int
0x18004b510  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004b517  mov     ecx, 2; unsigned __int8
0x18004b51c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004b521  test    r14b, r14b
0x18004b524  jz      short loc_18004B551
0x18004b526  mov     eax, 800704C7h
0x18004b52b  mov     [rsp+158h+Reply], eax
0x18004b52f  mov     [rsp+158h+bAlertable], eax
0x18004b533  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004b53a  mov     r8d, 2E7h; unsigned int
0x18004b540  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004b547  mov     ecx, 2; unsigned __int8
0x18004b54c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004b551  mov     eax, [rsp+158h+Reply]
0x18004b555  cmp     eax, 800706B5h
0x18004b55a  jz      short loc_18004B563
0x18004b55c  cmp     eax, 800706BAh
0x18004b561  jnz     short loc_18004B56C
0x18004b563  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004b568  mov     eax, [rsp+158h+Reply]
0x18004b56c  mov     rcx, [rsp+158h+var_38]
0x18004b574  xor     rcx, rsp; StackCookie
0x18004b577  call    __security_check_cookie
0x18004b57c  add     rsp, 130h
0x18004b583  pop     r15
0x18004b585  pop     r14
0x18004b587  pop     r13
0x18004b589  pop     r12
0x18004b58b  pop     rsi
0x18004b58c  retn
0x180061a16  push    rbp
0x180061a18  sub     rsp, 60h
0x180061a1c  mov     rbp, rdx
0x180061a1f  mov     rcx, [rcx]
0x180061a22  mov     ecx, [rcx]; unsigned int
0x180061a24  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x180061a29  nop
0x180061a2a  add     rsp, 60h
0x180061a2e  pop     rbp
0x180061a2f  retn
```
