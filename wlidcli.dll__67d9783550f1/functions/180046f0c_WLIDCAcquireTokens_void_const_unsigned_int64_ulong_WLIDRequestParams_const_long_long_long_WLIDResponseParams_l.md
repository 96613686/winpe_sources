# WLIDCAcquireTokens(void * const,unsigned __int64,ulong,_WLIDRequestParams * const,long *,long *,long *,_WLIDResponseParams * *,long *,void *,int)

- ea: `0x180046f0c`
- end: `0x1800473d8`
- name: `?WLIDCAcquireTokens@@YAJQEAX_KKQEAU_WLIDRequestParams@@PEAJ33PEAPEAU_WLIDResponseParams@@3PEAXH@Z`
- size: `1228`
- prototype: `__int64 __fastcall(void *const, unsigned __int64, unsigned int, struct _WLIDRequestParams *const, int *, int *, int *, struct _WLIDResponseParams **, int *, void *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001ca08`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180044eac`
- `0x180046ce0`
- `0x180046e64`
- `0x180046f0c`
- `0x18004cd04`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180047224`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004727c`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180047224`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004727c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004707b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004707b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004708e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004728d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004708e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004728d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047302`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047302`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004724e`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004724e`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180047181`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180047181`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800472b8`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800472b8`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180047034`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180047034`

## string_xrefs

- `0x1800470a0`: `RPC failed to create new event, hr = %#x`
- `0x1800472cc`: `RPC Async complete call failed, hr = %#x`
- `0x180047320`: `WLIDCAcquireTokens`
- `0x1800473ab`: `WLIDCAcquireTokens`

## pseudocode

```c
__int64 __fastcall WLIDCAcquireTokens(
        void *const a1,
        __int64 a2,
        int a3,
        struct _WLIDRequestParams *const a4,
        int *a5,
        int *a6,
        int *a7,
        struct _WLIDResponseParams **a8,
        int *a9,
        void *a10,
        int a11)
{
  DWORD v12; // r12d
  char v13; // r15
  char v14; // r14
  int LastError; // eax
  const unsigned __int16 *v16; // r9
  unsigned int v17; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v19; // esi
  int v20; // ecx
  BOOL bAlertable[2]; // [rsp+20h] [rbp-188h]
  int Reply; // [rsp+90h] [rbp-118h] BYREF
  char v24; // [rsp+94h] [rbp-114h]
  DWORD dwMilliseconds; // [rsp+98h] [rbp-110h] BYREF
  int v26; // [rsp+9Ch] [rbp-10Ch] BYREF
  int v27; // [rsp+A0h] [rbp-108h]
  int v28; // [rsp+A4h] [rbp-104h]
  DWORD v29; // [rsp+A8h] [rbp-100h] BYREF
  HANDLE Handles[2]; // [rsp+B0h] [rbp-F8h] BYREF
  int *v31; // [rsp+C0h] [rbp-E8h]
  struct _WLIDResponseParams **v32; // [rsp+C8h] [rbp-E0h]
  int *v33; // [rsp+D0h] [rbp-D8h]
  int *v34; // [rsp+D8h] [rbp-D0h]
  int *v35; // [rsp+E0h] [rbp-C8h]
  struct _WLIDRequestParams *v36; // [rsp+E8h] [rbp-C0h]
  __int64 v37; // [rsp+F0h] [rbp-B8h]
  _RPC_ASYNC_STATE pAsync; // [rsp+100h] [rbp-A8h] BYREF

  v36 = a4;
  v27 = a3;
  v37 = a2;
  v35 = a5;
  v34 = a6;
  v33 = a7;
  v32 = a8;
  v31 = a9;
  v26 = 0;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  if ( a11 )
    dwMilliseconds *= 3;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v12 = dwMilliseconds;
  v29 = dwMilliseconds;
  v13 = 0;
  v24 = 0;
  v14 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v16 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_7:
    v17 = 669;
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
    v16 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_7;
  }
  Handles[0] = EventW;
  if ( a10 )
    Handles[1] = a10;
  v28 = (a10 != 0) + 1;
  Ndr64AsyncClientCall(
    (MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo,
    0xFu,
    0,
    &pAsync,
    a1,
    v37,
    v27,
    v36,
    &String,
    0,
    &String,
    v35,
    v34,
    v33,
    &v26,
    v32,
    v31);
  v19 = WaitForMultipleObjectsEx((a10 != 0) + 1, Handles, 0, v12, 0);
  do
  {
    if ( v14 || v19 != 258 && v19 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v19 == 258 )
      v13 = 1;
    else
      v14 = 1;
    v19 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v13 );
  if ( v19 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v16 = L"Encountered error while waiting on RPC call, hr = %#x";
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_32;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v16 = L"RPC Async complete call failed, hr = %#x";
  }
  v17 = 684;
LABEL_31:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(
    2u,
    "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
    v17,
    v16,
    *(_QWORD *)bAlertable);
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v13 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[19],unsigned long &>(
      (__int64)"WLIDCAcquireTokens",
      (int *)&v29);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x2ACu,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v14 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x2ACu,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  v20 = Reply;
  if ( Reply == -2147023179 || Reply == -2147023174 )
  {
    TraceServiceStatus();
    v20 = Reply;
  }
  return TranslateRpcServiceError(v20, "WLIDCAcquireTokens");
}

```

## disassembly

```asm
0x180046f0c  push    rsi
0x180046f0e  push    r12
0x180046f10  push    r13
0x180046f12  push    r14
0x180046f14  push    r15
0x180046f16  sub     rsp, 180h
0x180046f1d  mov     rax, cs:__security_cookie
0x180046f24  xor     rax, rsp
0x180046f27  mov     [rsp+1A8h+var_38], rax
0x180046f2f  mov     [rsp+1A8h+var_C0], r9
0x180046f37  mov     [rsp+1A8h+var_108], r8d
0x180046f3f  mov     [rsp+1A8h+var_B8], rdx
0x180046f47  mov     r13, rcx
0x180046f4a  mov     rax, [rsp+1A8h+arg_20]
0x180046f52  mov     [rsp+1A8h+var_C8], rax
0x180046f5a  mov     rax, [rsp+1A8h+arg_28]
0x180046f62  mov     [rsp+1A8h+var_D0], rax
0x180046f6a  mov     rax, [rsp+1A8h+arg_30]
0x180046f72  mov     [rsp+1A8h+var_D8], rax
0x180046f7a  mov     rax, [rsp+1A8h+arg_38]
0x180046f82  mov     [rsp+1A8h+var_E0], rax
0x180046f8a  mov     rax, [rsp+1A8h+arg_40]
0x180046f92  mov     [rsp+1A8h+var_E8], rax
0x180046f9a  mov     [rsp+1A8h+var_10C], 0
0x180046fa5  mov     [rsp+1A8h+Reply], 0
0x180046fb0  mov     [rsp+1A8h+dwMilliseconds], 0
0x180046fbb  lea     r8, [rsp+1A8h+dwMilliseconds]; unsigned int *
0x180046fc3  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180046fc8  cmp     [rsp+1A8h+arg_50], 0
0x180046fd0  jz      short loc_180046FE3
0x180046fd2  mov     eax, [rsp+1A8h+dwMilliseconds]
0x180046fd9  lea     eax, [rax+rax*2]
0x180046fdc  mov     [rsp+1A8h+dwMilliseconds], eax
0x180046fe3  xor     edx, edx; Val
0x180046fe5  lea     r8d, [rdx+70h]; Size
0x180046fe9  lea     rcx, [rsp+1A8h+pAsync]; void *
0x180046ff1  call    memset_0
0x180046ff6  mov     r12d, [rsp+1A8h+dwMilliseconds]
0x180046ffe  mov     [rsp+1A8h+dwMilliseconds], r12d
0x180047006  mov     [rsp+1A8h+var_100], r12d
0x18004700e  xor     r15b, r15b
0x180047011  mov     [rsp+1A8h+var_114], r15b
0x180047019  xor     r14b, r14b
0x18004701c  xorps   xmm0, xmm0
0x18004701f  movups  xmmword ptr [rsp+1A8h+Handles], xmm0
0x180047027  mov     edx, 70h ; 'p'; Size
0x18004702c  lea     rcx, [rsp+1A8h+pAsync]; pAsync
0x180047034  call    cs:__imp_RpcAsyncInitializeHandle
0x18004703a  test    eax, eax
0x18004703c  jz      short loc_18004705A
0x18004703e  jle     short loc_180047048
0x180047040  movzx   eax, ax
0x180047043  or      eax, 80070000h
0x180047048  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004704f  mov     r8d, 29Dh
0x180047055  jmp     loc_1800472D9
0x18004705a  mov     [rsp+1A8h+pAsync.UserInfo], 0
0x180047066  mov     [rsp+1A8h+pAsync.NotificationType], 1
0x180047071  xor     r9d, r9d; lpName
0x180047074  xor     r8d, r8d; bInitialState
0x180047077  xor     edx, edx; bManualReset
0x180047079  xor     ecx, ecx; lpEventAttributes
0x18004707b  call    cs:__imp_CreateEventW
0x180047081  mov     qword ptr [rsp+1A8h+pAsync.u], rax
0x180047089  test    rax, rax
0x18004708c  jnz     short loc_1800470A9
0x18004708e  call    cs:__imp_GetLastError
0x180047094  test    eax, eax
0x180047096  jle     short loc_1800470A0
0x180047098  movzx   eax, ax
0x18004709b  or      eax, 80070000h
0x1800470a0  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x1800470a7  jmp     short loc_18004704F
0x1800470a9  mov     [rsp+1A8h+Handles], rax
0x1800470b1  mov     rax, [rsp+1A8h+arg_48]
0x1800470b9  test    rax, rax
0x1800470bc  jz      short loc_1800470C6
0x1800470be  mov     [rsp+1A8h+Handles+8], rax
0x1800470c6  neg     rax
0x1800470c9  sbb     esi, esi
0x1800470cb  neg     esi
0x1800470cd  inc     esi
0x1800470cf  mov     [rsp+1A8h+var_104], esi
0x1800470d6  mov     rax, [rsp+1A8h+var_E8]
0x1800470de  mov     [rsp+1A8h+var_128], rax
0x1800470e6  mov     rax, [rsp+1A8h+var_E0]
0x1800470ee  mov     [rsp+1A8h+var_130], rax
0x1800470f3  lea     rax, [rsp+1A8h+var_10C]
0x1800470fb  mov     [rsp+1A8h+var_138], rax
0x180047100  mov     rax, [rsp+1A8h+var_D8]
0x180047108  mov     [rsp+1A8h+var_140], rax
0x18004710d  mov     rax, [rsp+1A8h+var_D0]
0x180047115  mov     [rsp+1A8h+var_148], rax
0x18004711a  mov     rax, [rsp+1A8h+var_C8]
0x180047122  mov     [rsp+1A8h+var_150], rax
0x180047127  lea     rax, String
0x18004712e  mov     [rsp+1A8h+var_158], rax
0x180047133  mov     [rsp+1A8h+var_160], 0
0x18004713c  mov     [rsp+1A8h+var_168], rax
0x180047141  mov     rax, [rsp+1A8h+var_C0]
0x180047149  mov     [rsp+1A8h+var_170], rax
0x18004714e  mov     eax, [rsp+1A8h+var_108]
0x180047155  mov     [rsp+1A8h+var_178], eax
0x180047159  mov     rax, [rsp+1A8h+var_B8]
0x180047161  mov     [rsp+1A8h+var_180], rax
0x180047166  mov     qword ptr [rsp+1A8h+bAlertable], r13
0x18004716b  lea     r9, [rsp+1A8h+pAsync]
0x180047173  xor     r8d, r8d; pReturnValue
0x180047176  lea     edx, [r8+0Fh]; nProcNum
0x18004717a  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180047181  call    cs:__imp_Ndr64AsyncClientCall
0x180047187  mov     eax, [rsp+1A8h+Reply]
0x18004718e  jmp     short loc_1800471F6
0x180047190  test    eax, eax
0x180047192  jle     short loc_18004719C
0x180047194  movzx   eax, ax
0x180047197  or      eax, 80070000h
0x18004719c  mov     [rsp+1A8h+Reply], eax
0x1800471a3  mov     [rsp+1A8h+bAlertable], eax
0x1800471a7  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x1800471ae  mov     r8d, 2ACh; unsigned int
0x1800471b4  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800471bb  mov     ecx, 2; unsigned __int8
0x1800471c0  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800471c5  mov     eax, [rsp+1A8h+Reply]
0x1800471cc  test    eax, eax
0x1800471ce  js      short loc_1800471DC
0x1800471d0  mov     eax, 8000FFFFh
0x1800471d5  mov     [rsp+1A8h+Reply], eax
0x1800471dc  mov     r12d, [rsp+1A8h+dwMilliseconds]
0x1800471e4  mov     r15b, [rsp+1A8h+var_114]
0x1800471ec  mov     r14b, r15b
0x1800471ef  mov     esi, [rsp+1A8h+var_104]
0x1800471f6  test    eax, eax
0x1800471f8  jns     short loc_18004720C
0x1800471fa  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180047201  mov     r8d, 2ACh
0x180047207  jmp     loc_1800472E0
0x18004720c  mov     [rsp+1A8h+bAlertable], 0; bAlertable
0x180047214  mov     r9d, r12d; dwMilliseconds
0x180047217  xor     r8d, r8d; bWaitAll
0x18004721a  lea     rdx, [rsp+1A8h+Handles]; lpHandles
0x180047222  mov     ecx, esi; nCount
0x180047224  call    cs:__imp_WaitForMultipleObjectsEx
0x18004722a  mov     esi, eax
0x18004722c  mov     r12d, 102h
0x180047232  test    r14b, r14b
0x180047235  jnz     short loc_180047289
0x180047237  cmp     esi, r12d
0x18004723a  jz      short loc_180047241
0x18004723c  cmp     esi, 1
0x18004723f  jnz     short loc_180047289
0x180047241  mov     edx, 1; fAbort
0x180047246  lea     rcx, [rsp+1A8h+pAsync]; pAsync
0x18004724e  call    cs:__imp_RpcAsyncCancelCall
0x180047254  cmp     esi, r12d
0x180047257  jnz     short loc_18004725E
0x180047259  mov     r15b, 1
0x18004725c  jmp     short loc_180047261
0x18004725e  mov     r14b, 1
0x180047261  mov     [rsp+1A8h+bAlertable], 0; bAlertable
0x180047269  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004726d  xor     r8d, r8d; bWaitAll
0x180047270  lea     rdx, [rsp+1A8h+Handles]; lpHandles
0x180047278  lea     ecx, [r8+1]; nCount
0x18004727c  call    cs:__imp_WaitForMultipleObjectsEx
0x180047282  mov     esi, eax
0x180047284  test    r15b, r15b
0x180047287  jz      short loc_180047232
0x180047289  test    esi, esi
0x18004728b  jz      short loc_1800472A8
0x18004728d  call    cs:__imp_GetLastError
0x180047293  test    eax, eax
0x180047295  jle     short loc_18004729F
0x180047297  movzx   eax, ax
0x18004729a  or      eax, 80070000h
0x18004729f  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x1800472a6  jmp     short loc_1800472D3
0x1800472a8  lea     rdx, [rsp+1A8h+Reply]; Reply
0x1800472b0  lea     rcx, [rsp+1A8h+pAsync]; pAsync
0x1800472b8  call    cs:__imp_RpcAsyncCompleteCall
0x1800472be  test    eax, eax
0x1800472c0  jz      short loc_1800472F5
0x1800472c2  jle     short loc_1800472CC
0x1800472c4  movzx   eax, ax
0x1800472c7  or      eax, 80070000h
0x1800472cc  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x1800472d3  mov     r8d, 2ACh; unsigned int
0x1800472d9  mov     [rsp+1A8h+Reply], eax
0x1800472e0  mov     [rsp+1A8h+bAlertable], eax
0x1800472e4  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800472eb  mov     ecx, 2; unsigned __int8
0x1800472f0  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800472f5  mov     rcx, qword ptr [rsp+1A8h+pAsync.u]; hObject
0x1800472fd  test    rcx, rcx
0x180047300  jz      short loc_180047308
0x180047302  call    cs:__imp_CloseHandle
0x180047308  test    r15b, r15b
0x18004730b  jz      short loc_180047355
0x18004730d  mov     [rsp+1A8h+Reply], 800705B4h
0x180047318  lea     rdx, [rsp+1A8h+var_100]
0x180047320  lea     rcx, aWlidcacquireto; "WLIDCAcquireTokens"
0x180047327  call    ??$RPCCallTimedOut@AEAY0BD@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BD@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[19],ulong &>(char const (&)[19],ulong &)
0x18004732c  mov     eax, [rsp+1A8h+Reply]
0x180047333  mov     [rsp+1A8h+bAlertable], eax
0x180047337  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004733e  mov     r8d, 2ACh; unsigned int
0x180047344  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004734b  mov     ecx, 2; unsigned __int8
0x180047350  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180047355  test    r14b, r14b
0x180047358  jz      short loc_180047388
0x18004735a  mov     eax, 800704C7h
0x18004735f  mov     [rsp+1A8h+Reply], eax
0x180047366  mov     [rsp+1A8h+bAlertable], eax
0x18004736a  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180047371  mov     r8d, 2ACh; unsigned int
0x180047377  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004737e  mov     ecx, 2; unsigned __int8
0x180047383  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180047388  mov     ecx, [rsp+1A8h+Reply]
0x18004738f  cmp     ecx, 800706B5h
0x180047395  jz      short loc_18004739F
0x180047397  cmp     ecx, 800706BAh
0x18004739d  jnz     short loc_1800473AB
0x18004739f  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x1800473a4  mov     ecx, [rsp+1A8h+Reply]; int
0x1800473ab  lea     rdx, aWlidcacquireto; "WLIDCAcquireTokens"
0x1800473b2  call    ?TranslateRpcServiceError@@YAJJPEBD@Z; TranslateRpcServiceError(long,char const *)
0x1800473b7  mov     rcx, [rsp+1A8h+var_38]
0x1800473bf  xor     rcx, rsp; StackCookie
0x1800473c2  call    __security_check_cookie
0x1800473c7  add     rsp, 180h
0x1800473ce  pop     r15
0x1800473d0  pop     r14
0x1800473d2  pop     r13
0x1800473d4  pop     r12
0x1800473d6  pop     rsi
0x1800473d7  retn
0x18006198c  push    rbp
0x18006198e  sub     rsp, 90h
0x180061995  mov     rbp, rdx
0x180061998  mov     rcx, [rcx]
0x18006199b  mov     ecx, [rcx]; unsigned int
0x18006199d  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x1800619a2  nop
0x1800619a3  add     rsp, 90h
0x1800619aa  pop     rbp
0x1800619ab  retn
```
