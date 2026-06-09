# WLIDCAcquireTokensEx(void * const,_WLIDAcquireTokenParams * const,ulong,_WLIDRequestParams * const,_WLIDAcquireTokenResults *,_WLIDResponseParams * *)

- ea: `0x180043944`
- end: `0x180043d75`
- name: `?WLIDCAcquireTokensEx@@YAJQEAXQEAU_WLIDAcquireTokenParams@@KQEAU_WLIDRequestParams@@PEAU_WLIDAcquireTokenResults@@PEAPEAU_WLIDResponseParams@@@Z`
- size: `1073`
- prototype: `__int64 __fastcall(void *const, struct _WLIDAcquireTokenParams *const, unsigned int, struct _WLIDRequestParams *const, struct _WLIDAcquireTokenResults *, struct _WLIDResponseParams **)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002520c`
- `0x180041530`

## callees

- `0x18000a400`
- `0x180010c68`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180041c80`
- `0x180043240`
- `0x1800433c4`
- `0x180043944`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180043a55`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180043a55`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180043bc1`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180043c19`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180043bc1`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180043c19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043a68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043c2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043a68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043c2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043c9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043c9f`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180043a0e`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180043a0e`
- `RPCRT4!RpcAsyncCancelCall` at `0x180043beb`
- `RPCRT4!RpcAsyncCancelCall` at `0x180043beb`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180043b23`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180043b23`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180043c55`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180043c55`

## string_xrefs

- `0x180043a7a`: `RPC failed to create new event, hr = %#x`
- `0x180043c69`: `RPC Async complete call failed, hr = %#x`
- `0x180043cbd`: `WLIDCAcquireTokensEx`
- `0x180043d48`: `WLIDCAcquireTokensEx`

## pseudocode

```c
__int64 __fastcall WLIDCAcquireTokensEx(
        void *const a1,
        struct _WLIDAcquireTokenParams *const a2,
        int a3,
        struct _WLIDRequestParams *const a4,
        struct _WLIDAcquireTokenResults *a5,
        struct _WLIDResponseParams **a6)
{
  DWORD v7; // r12d
  char v8; // r15
  char v9; // r14
  int LastError; // eax
  const unsigned __int16 *v11; // r9
  unsigned int v12; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v14; // esi
  int v15; // ecx
  BOOL bAlertable[2]; // [rsp+20h] [rbp-158h]
  int Reply; // [rsp+90h] [rbp-E8h] BYREF
  char v19; // [rsp+94h] [rbp-E4h]
  DWORD dwMilliseconds; // [rsp+98h] [rbp-E0h] BYREF
  int v21; // [rsp+9Ch] [rbp-DCh]
  DWORD v22; // [rsp+A0h] [rbp-D8h] BYREF
  struct _WLIDResponseParams **v23; // [rsp+A8h] [rbp-D0h]
  struct _WLIDRequestParams *v24; // [rsp+B0h] [rbp-C8h]
  void *v25; // [rsp+B8h] [rbp-C0h]
  HANDLE Handles[2]; // [rsp+C0h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+D0h] [rbp-A8h] BYREF

  v24 = a4;
  v21 = a3;
  v25 = a1;
  v23 = a6;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v7 = dwMilliseconds;
  v22 = dwMilliseconds;
  v8 = 0;
  v19 = 0;
  v9 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v11 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v12 = 699;
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
    v11 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_5;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall(
    (MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo,
    0xFu,
    0,
    &pAsync,
    v25,
    *(_QWORD *)a2,
    v21,
    v24,
    *((_QWORD *)a2 + 1),
    *((_QWORD *)a2 + 2),
    *((_QWORD *)a2 + 3),
    a5,
    (char *)a5 + 4,
    (char *)a5 + 8,
    (char *)a5 + 16,
    v23,
    (char *)a5 + 12);
  v14 = WaitForMultipleObjectsEx(1u, Handles, 0, v7, 0);
  do
  {
    if ( v9 || v14 != 258 && v14 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v14 == 258 )
      v8 = 1;
    else
      v9 = 1;
    v14 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v8 );
  if ( v14 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v11 = L"Encountered error while waiting on RPC call, hr = %#x";
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_28;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v11 = L"RPC Async complete call failed, hr = %#x";
  }
  v12 = 714;
LABEL_27:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(
    2u,
    "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
    v12,
    v11,
    *(_QWORD *)bAlertable);
LABEL_28:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v8 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],unsigned long &>("WLIDCAcquireTokensEx", &v22);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x2CAu,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v9 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x2CAu,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  v15 = Reply;
  if ( Reply == -2147023179 || Reply == -2147023174 )
  {
    TraceServiceStatus();
    v15 = Reply;
  }
  return TranslateRpcServiceError(v15, "WLIDCAcquireTokensEx");
}

```

## disassembly

```asm
0x180043944  push    rsi
0x180043946  push    r12
0x180043948  push    r13
0x18004394a  push    r14
0x18004394c  push    r15
0x18004394e  sub     rsp, 150h
0x180043955  mov     rax, cs:__security_cookie
0x18004395c  xor     rax, rsp
0x18004395f  mov     [rsp+178h+var_38], rax
0x180043967  mov     [rsp+178h+var_C8], r9
0x18004396f  mov     [rsp+178h+var_DC], r8d
0x180043977  mov     r13, rdx
0x18004397a  mov     [rsp+178h+var_C0], rcx
0x180043982  mov     rsi, [rsp+178h+arg_20]
0x18004398a  mov     rax, [rsp+178h+arg_28]
0x180043992  mov     [rsp+178h+var_D0], rax
0x18004399a  mov     [rsp+178h+Reply], 0
0x1800439a5  mov     [rsp+178h+dwMilliseconds], 0
0x1800439b0  lea     r8, [rsp+178h+dwMilliseconds]; unsigned int *
0x1800439b8  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x1800439bd  xor     edx, edx; Val
0x1800439bf  lea     r8d, [rdx+70h]; Size
0x1800439c3  lea     rcx, [rsp+178h+pAsync]; void *
0x1800439cb  call    memset_0
0x1800439d0  mov     r12d, [rsp+178h+dwMilliseconds]
0x1800439d8  mov     [rsp+178h+dwMilliseconds], r12d
0x1800439e0  mov     [rsp+178h+var_D8], r12d
0x1800439e8  xor     r15b, r15b
0x1800439eb  mov     [rsp+178h+var_E4], r15b
0x1800439f3  xor     r14b, r14b
0x1800439f6  xorps   xmm0, xmm0
0x1800439f9  movups  xmmword ptr [rsp+178h+Handles], xmm0
0x180043a01  mov     edx, 70h ; 'p'; Size
0x180043a06  lea     rcx, [rsp+178h+pAsync]; pAsync
0x180043a0e  call    cs:__imp_RpcAsyncInitializeHandle
0x180043a14  test    eax, eax
0x180043a16  jz      short loc_180043A34
0x180043a18  jle     short loc_180043A22
0x180043a1a  movzx   eax, ax
0x180043a1d  or      eax, 80070000h
0x180043a22  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180043a29  mov     r8d, 2BBh
0x180043a2f  jmp     loc_180043C76
0x180043a34  mov     [rsp+178h+pAsync.UserInfo], 0
0x180043a40  mov     [rsp+178h+pAsync.NotificationType], 1
0x180043a4b  xor     r9d, r9d; lpName
0x180043a4e  xor     r8d, r8d; bInitialState
0x180043a51  xor     edx, edx; bManualReset
0x180043a53  xor     ecx, ecx; lpEventAttributes
0x180043a55  call    cs:__imp_CreateEventW
0x180043a5b  mov     qword ptr [rsp+178h+pAsync.u], rax
0x180043a63  test    rax, rax
0x180043a66  jnz     short loc_180043A83
0x180043a68  call    cs:__imp_GetLastError
0x180043a6e  test    eax, eax
0x180043a70  jle     short loc_180043A7A
0x180043a72  movzx   eax, ax
0x180043a75  or      eax, 80070000h
0x180043a7a  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180043a81  jmp     short loc_180043A29
0x180043a83  mov     [rsp+178h+Handles], rax
0x180043a8b  lea     rax, [rsi+0Ch]
0x180043a8f  lea     rcx, [rsi+10h]
0x180043a93  lea     rdx, [rsi+8]
0x180043a97  lea     r8, [rsi+4]
0x180043a9b  mov     [rsp+178h+var_F8], rax
0x180043aa3  mov     rax, [rsp+178h+var_D0]
0x180043aab  mov     [rsp+178h+var_100], rax
0x180043ab0  mov     [rsp+178h+var_108], rcx
0x180043ab5  mov     [rsp+178h+var_110], rdx
0x180043aba  mov     [rsp+178h+var_118], r8
0x180043abf  mov     [rsp+178h+var_120], rsi
0x180043ac4  mov     rax, [r13+18h]
0x180043ac8  mov     [rsp+178h+var_128], rax
0x180043acd  mov     rax, [r13+10h]
0x180043ad1  mov     [rsp+178h+var_130], rax
0x180043ad6  mov     rax, [r13+8]
0x180043ada  mov     [rsp+178h+var_138], rax
0x180043adf  mov     rax, [rsp+178h+var_C8]
0x180043ae7  mov     [rsp+178h+var_140], rax
0x180043aec  mov     eax, [rsp+178h+var_DC]
0x180043af3  mov     [rsp+178h+var_148], eax
0x180043af7  mov     rax, [r13+0]
0x180043afb  mov     [rsp+178h+var_150], rax
0x180043b00  mov     rax, [rsp+178h+var_C0]
0x180043b08  mov     qword ptr [rsp+178h+bAlertable], rax
0x180043b0d  lea     r9, [rsp+178h+pAsync]
0x180043b15  xor     r8d, r8d; pReturnValue
0x180043b18  lea     edx, [r8+0Fh]; nProcNum
0x180043b1c  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180043b23  call    cs:__imp_Ndr64AsyncClientCall
0x180043b29  mov     eax, [rsp+178h+Reply]
0x180043b30  jmp     short loc_180043B91
0x180043b32  test    eax, eax
0x180043b34  jle     short loc_180043B3E
0x180043b36  movzx   eax, ax
0x180043b39  or      eax, 80070000h
0x180043b3e  mov     [rsp+178h+Reply], eax
0x180043b45  mov     [rsp+178h+bAlertable], eax
0x180043b49  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180043b50  mov     r8d, 2CAh; unsigned int
0x180043b56  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180043b5d  mov     ecx, 2; unsigned __int8
0x180043b62  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180043b67  mov     eax, [rsp+178h+Reply]
0x180043b6e  test    eax, eax
0x180043b70  js      short loc_180043B7E
0x180043b72  mov     eax, 8000FFFFh
0x180043b77  mov     [rsp+178h+Reply], eax
0x180043b7e  mov     r12d, [rsp+178h+dwMilliseconds]
0x180043b86  mov     r15b, [rsp+178h+var_E4]
0x180043b8e  mov     r14b, r15b
0x180043b91  test    eax, eax
0x180043b93  jns     short loc_180043BA7
0x180043b95  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180043b9c  mov     r8d, 2CAh
0x180043ba2  jmp     loc_180043C7D
0x180043ba7  mov     [rsp+178h+bAlertable], 0; bAlertable
0x180043baf  mov     r9d, r12d; dwMilliseconds
0x180043bb2  xor     r8d, r8d; bWaitAll
0x180043bb5  lea     rdx, [rsp+178h+Handles]; lpHandles
0x180043bbd  lea     ecx, [r8+1]; nCount
0x180043bc1  call    cs:__imp_WaitForMultipleObjectsEx
0x180043bc7  mov     esi, eax
0x180043bc9  mov     r12d, 102h
0x180043bcf  test    r14b, r14b
0x180043bd2  jnz     short loc_180043C26
0x180043bd4  cmp     esi, r12d
0x180043bd7  jz      short loc_180043BDE
0x180043bd9  cmp     esi, 1
0x180043bdc  jnz     short loc_180043C26
0x180043bde  mov     edx, 1; fAbort
0x180043be3  lea     rcx, [rsp+178h+pAsync]; pAsync
0x180043beb  call    cs:__imp_RpcAsyncCancelCall
0x180043bf1  cmp     esi, r12d
0x180043bf4  jnz     short loc_180043BFB
0x180043bf6  mov     r15b, 1
0x180043bf9  jmp     short loc_180043BFE
0x180043bfb  mov     r14b, 1
0x180043bfe  mov     [rsp+178h+bAlertable], 0; bAlertable
0x180043c06  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180043c0a  xor     r8d, r8d; bWaitAll
0x180043c0d  lea     rdx, [rsp+178h+Handles]; lpHandles
0x180043c15  lea     ecx, [r8+1]; nCount
0x180043c19  call    cs:__imp_WaitForMultipleObjectsEx
0x180043c1f  mov     esi, eax
0x180043c21  test    r15b, r15b
0x180043c24  jz      short loc_180043BCF
0x180043c26  test    esi, esi
0x180043c28  jz      short loc_180043C45
0x180043c2a  call    cs:__imp_GetLastError
0x180043c30  test    eax, eax
0x180043c32  jle     short loc_180043C3C
0x180043c34  movzx   eax, ax
0x180043c37  or      eax, 80070000h
0x180043c3c  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180043c43  jmp     short loc_180043C70
0x180043c45  lea     rdx, [rsp+178h+Reply]; Reply
0x180043c4d  lea     rcx, [rsp+178h+pAsync]; pAsync
0x180043c55  call    cs:__imp_RpcAsyncCompleteCall
0x180043c5b  test    eax, eax
0x180043c5d  jz      short loc_180043C92
0x180043c5f  jle     short loc_180043C69
0x180043c61  movzx   eax, ax
0x180043c64  or      eax, 80070000h
0x180043c69  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180043c70  mov     r8d, 2CAh; unsigned int
0x180043c76  mov     [rsp+178h+Reply], eax
0x180043c7d  mov     [rsp+178h+bAlertable], eax
0x180043c81  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180043c88  mov     ecx, 2; unsigned __int8
0x180043c8d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180043c92  mov     rcx, qword ptr [rsp+178h+pAsync.u]; hObject
0x180043c9a  test    rcx, rcx
0x180043c9d  jz      short loc_180043CA5
0x180043c9f  call    cs:__imp_CloseHandle
0x180043ca5  test    r15b, r15b
0x180043ca8  jz      short loc_180043CF2
0x180043caa  mov     [rsp+178h+Reply], 800705B4h
0x180043cb5  lea     rdx, [rsp+178h+var_D8]
0x180043cbd  lea     rcx, aWlidcacquireto_3; "WLIDCAcquireTokensEx"
0x180043cc4  call    ??$RPCCallTimedOut@AEAY0BF@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BF@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],ulong &>(char const (&)[21],ulong &)
0x180043cc9  mov     eax, [rsp+178h+Reply]
0x180043cd0  mov     [rsp+178h+bAlertable], eax
0x180043cd4  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180043cdb  mov     r8d, 2CAh; unsigned int
0x180043ce1  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180043ce8  mov     ecx, 2; unsigned __int8
0x180043ced  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180043cf2  test    r14b, r14b
0x180043cf5  jz      short loc_180043D25
0x180043cf7  mov     eax, 800704C7h
0x180043cfc  mov     [rsp+178h+Reply], eax
0x180043d03  mov     [rsp+178h+bAlertable], eax
0x180043d07  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180043d0e  mov     r8d, 2CAh; unsigned int
0x180043d14  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180043d1b  mov     ecx, 2; unsigned __int8
0x180043d20  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180043d25  mov     ecx, [rsp+178h+Reply]
0x180043d2c  cmp     ecx, 800706B5h
0x180043d32  jz      short loc_180043D3C
0x180043d34  cmp     ecx, 800706BAh
0x180043d3a  jnz     short loc_180043D48
0x180043d3c  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180043d41  mov     ecx, [rsp+178h+Reply]; int
0x180043d48  lea     rdx, aWlidcacquireto_3; "WLIDCAcquireTokensEx"
0x180043d4f  call    ?TranslateRpcServiceError@@YAJJPEBD@Z; TranslateRpcServiceError(long,char const *)
0x180043d54  mov     rcx, [rsp+178h+var_38]
0x180043d5c  xor     rcx, rsp; StackCookie
0x180043d5f  call    __security_check_cookie
0x180043d64  add     rsp, 150h
0x180043d6b  pop     r15
0x180043d6d  pop     r14
0x180043d6f  pop     r13
0x180043d71  pop     r12
0x180043d73  pop     rsi
0x180043d74  retn
0x1800575f9  push    rbp
0x1800575fb  sub     rsp, 90h
0x180057602  mov     rbp, rdx
0x180057605  mov     rcx, [rcx]
0x180057608  mov     ecx, [rcx]; unsigned int
0x18005760a  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x18005760f  nop
0x180057610  add     rsp, 90h
0x180057617  pop     rbp
0x180057618  retn
```
