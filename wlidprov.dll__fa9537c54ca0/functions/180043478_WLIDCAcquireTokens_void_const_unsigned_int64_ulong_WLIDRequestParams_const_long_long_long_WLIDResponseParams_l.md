# WLIDCAcquireTokens(void * const,unsigned __int64,ulong,_WLIDRequestParams * const,long *,long *,long *,_WLIDResponseParams * *,long *,void *,int)

- ea: `0x180043478`
- end: `0x18004393d`
- name: `?WLIDCAcquireTokens@@YAJQEAX_KKQEAU_WLIDRequestParams@@PEAJ33PEAPEAU_WLIDResponseParams@@3PEAXH@Z`
- size: `1221`
- prototype: `__int64 __fastcall(void *const, unsigned __int64, unsigned int, struct _WLIDRequestParams *const, int *, int *, int *, struct _WLIDResponseParams **, int *, void *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180041420`
- `0x1800414a0`

## callees

- `0x18000a400`
- `0x180010c68`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180041b6c`
- `0x180043240`
- `0x1800433c4`
- `0x180043478`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800435e7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800435e7`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180043790`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800437e8`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180043790`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800437e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800435fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800437f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800435fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800437f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004386e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004386e`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800435a0`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800435a0`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800437ba`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800437ba`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800436ed`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800436ed`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180043824`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180043824`

## string_xrefs

- `0x18004360c`: `RPC failed to create new event, hr = %#x`
- `0x180043838`: `RPC Async complete call failed, hr = %#x`
- `0x180043910`: `WLIDCAcquireTokens`

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
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  int v21; // ecx
  BOOL bAlertable[2]; // [rsp+20h] [rbp-188h]
  int Reply; // [rsp+90h] [rbp-118h] BYREF
  char v25; // [rsp+94h] [rbp-114h]
  DWORD dwMilliseconds; // [rsp+98h] [rbp-110h] BYREF
  int v27; // [rsp+9Ch] [rbp-10Ch] BYREF
  int v28; // [rsp+A0h] [rbp-108h]
  int v29; // [rsp+A4h] [rbp-104h]
  DWORD v30; // [rsp+A8h] [rbp-100h] BYREF
  HANDLE Handles[2]; // [rsp+B0h] [rbp-F8h] BYREF
  int *v32; // [rsp+C0h] [rbp-E8h]
  struct _WLIDResponseParams **v33; // [rsp+C8h] [rbp-E0h]
  int *v34; // [rsp+D0h] [rbp-D8h]
  int *v35; // [rsp+D8h] [rbp-D0h]
  int *v36; // [rsp+E0h] [rbp-C8h]
  struct _WLIDRequestParams *v37; // [rsp+E8h] [rbp-C0h]
  __int64 v38; // [rsp+F0h] [rbp-B8h]
  struct _RPC_ASYNC_STATE pAsync; // [rsp+100h] [rbp-A8h] BYREF

  v37 = a4;
  v28 = a3;
  v38 = a2;
  v36 = a5;
  v35 = a6;
  v34 = a7;
  v33 = a8;
  v32 = a9;
  v27 = 0;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  if ( a11 )
    dwMilliseconds *= 3;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v12 = dwMilliseconds;
  v30 = dwMilliseconds;
  v13 = 0;
  v25 = 0;
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
  v29 = (a10 != 0) + 1;
  Ndr64AsyncClientCall(
    (MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo,
    0xFu,
    0,
    &pAsync,
    a1,
    v38,
    v28,
    v37,
    &qword_180063440,
    0,
    &qword_180063440,
    v36,
    v35,
    v34,
    &v27,
    v33,
    v32);
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
  NotificationRoutine = pAsync.u.APC.NotificationRoutine;
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v13 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[19],unsigned long &>(NotificationRoutine, &v30);
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
  v21 = Reply;
  if ( Reply == -2147023179 || Reply == -2147023174 )
  {
    TraceServiceStatus();
    v21 = Reply;
  }
  return TranslateRpcServiceError(v21, "WLIDCAcquireTokens");
}

```

## disassembly

```asm
0x180043478  push    rsi
0x18004347a  push    r12
0x18004347c  push    r13
0x18004347e  push    r14
0x180043480  push    r15
0x180043482  sub     rsp, 180h
0x180043489  mov     rax, cs:__security_cookie
0x180043490  xor     rax, rsp
0x180043493  mov     [rsp+1A8h+var_38], rax
0x18004349b  mov     [rsp+1A8h+var_C0], r9
0x1800434a3  mov     [rsp+1A8h+var_108], r8d
0x1800434ab  mov     [rsp+1A8h+var_B8], rdx
0x1800434b3  mov     r13, rcx
0x1800434b6  mov     rax, [rsp+1A8h+arg_20]
0x1800434be  mov     [rsp+1A8h+var_C8], rax
0x1800434c6  mov     rax, [rsp+1A8h+arg_28]
0x1800434ce  mov     [rsp+1A8h+var_D0], rax
0x1800434d6  mov     rax, [rsp+1A8h+arg_30]
0x1800434de  mov     [rsp+1A8h+var_D8], rax
0x1800434e6  mov     rax, [rsp+1A8h+arg_38]
0x1800434ee  mov     [rsp+1A8h+var_E0], rax
0x1800434f6  mov     rax, [rsp+1A8h+arg_40]
0x1800434fe  mov     [rsp+1A8h+var_E8], rax
0x180043506  mov     [rsp+1A8h+var_10C], 0
0x180043511  mov     [rsp+1A8h+Reply], 0
0x18004351c  mov     [rsp+1A8h+dwMilliseconds], 0
0x180043527  lea     r8, [rsp+1A8h+dwMilliseconds]; unsigned int *
0x18004352f  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180043534  cmp     [rsp+1A8h+arg_50], 0
0x18004353c  jz      short loc_18004354F
0x18004353e  mov     eax, [rsp+1A8h+dwMilliseconds]
0x180043545  lea     eax, [rax+rax*2]
0x180043548  mov     [rsp+1A8h+dwMilliseconds], eax
0x18004354f  xor     edx, edx; Val
0x180043551  lea     r8d, [rdx+70h]; Size
0x180043555  lea     rcx, [rsp+1A8h+pAsync]; void *
0x18004355d  call    memset_0
0x180043562  mov     r12d, [rsp+1A8h+dwMilliseconds]
0x18004356a  mov     [rsp+1A8h+dwMilliseconds], r12d
0x180043572  mov     [rsp+1A8h+var_100], r12d
0x18004357a  xor     r15b, r15b
0x18004357d  mov     [rsp+1A8h+var_114], r15b
0x180043585  xor     r14b, r14b
0x180043588  xorps   xmm0, xmm0
0x18004358b  movups  xmmword ptr [rsp+1A8h+Handles], xmm0
0x180043593  mov     edx, 70h ; 'p'; Size
0x180043598  lea     rcx, [rsp+1A8h+pAsync]; pAsync
0x1800435a0  call    cs:__imp_RpcAsyncInitializeHandle
0x1800435a6  test    eax, eax
0x1800435a8  jz      short loc_1800435C6
0x1800435aa  jle     short loc_1800435B4
0x1800435ac  movzx   eax, ax
0x1800435af  or      eax, 80070000h
0x1800435b4  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x1800435bb  mov     r8d, 29Dh
0x1800435c1  jmp     loc_180043845
0x1800435c6  mov     [rsp+1A8h+pAsync.UserInfo], 0
0x1800435d2  mov     [rsp+1A8h+pAsync.NotificationType], 1
0x1800435dd  xor     r9d, r9d; lpName
0x1800435e0  xor     r8d, r8d; bInitialState
0x1800435e3  xor     edx, edx; bManualReset
0x1800435e5  xor     ecx, ecx; lpEventAttributes
0x1800435e7  call    cs:__imp_CreateEventW
0x1800435ed  mov     qword ptr [rsp+1A8h+pAsync.u], rax
0x1800435f5  test    rax, rax
0x1800435f8  jnz     short loc_180043615
0x1800435fa  call    cs:__imp_GetLastError
0x180043600  test    eax, eax
0x180043602  jle     short loc_18004360C
0x180043604  movzx   eax, ax
0x180043607  or      eax, 80070000h
0x18004360c  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180043613  jmp     short loc_1800435BB
0x180043615  mov     [rsp+1A8h+Handles], rax
0x18004361d  mov     rax, [rsp+1A8h+arg_48]
0x180043625  test    rax, rax
0x180043628  jz      short loc_180043632
0x18004362a  mov     [rsp+1A8h+Handles+8], rax
0x180043632  neg     rax
0x180043635  sbb     esi, esi
0x180043637  neg     esi
0x180043639  inc     esi
0x18004363b  mov     [rsp+1A8h+var_104], esi
0x180043642  mov     rax, [rsp+1A8h+var_E8]
0x18004364a  mov     [rsp+1A8h+var_128], rax
0x180043652  mov     rax, [rsp+1A8h+var_E0]
0x18004365a  mov     [rsp+1A8h+var_130], rax
0x18004365f  lea     rax, [rsp+1A8h+var_10C]
0x180043667  mov     [rsp+1A8h+var_138], rax
0x18004366c  mov     rax, [rsp+1A8h+var_D8]
0x180043674  mov     [rsp+1A8h+var_140], rax
0x180043679  mov     rax, [rsp+1A8h+var_D0]
0x180043681  mov     [rsp+1A8h+var_148], rax
0x180043686  mov     rax, [rsp+1A8h+var_C8]
0x18004368e  mov     [rsp+1A8h+var_150], rax
0x180043693  lea     rax, qword_180063440
0x18004369a  mov     [rsp+1A8h+var_158], rax
0x18004369f  mov     [rsp+1A8h+var_160], 0
0x1800436a8  mov     [rsp+1A8h+var_168], rax
0x1800436ad  mov     rax, [rsp+1A8h+var_C0]
0x1800436b5  mov     [rsp+1A8h+var_170], rax
0x1800436ba  mov     eax, [rsp+1A8h+var_108]
0x1800436c1  mov     [rsp+1A8h+var_178], eax
0x1800436c5  mov     rax, [rsp+1A8h+var_B8]
0x1800436cd  mov     [rsp+1A8h+var_180], rax
0x1800436d2  mov     qword ptr [rsp+1A8h+bAlertable], r13
0x1800436d7  lea     r9, [rsp+1A8h+pAsync]
0x1800436df  xor     r8d, r8d; pReturnValue
0x1800436e2  lea     edx, [r8+0Fh]; nProcNum
0x1800436e6  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800436ed  call    cs:__imp_Ndr64AsyncClientCall
0x1800436f3  mov     eax, [rsp+1A8h+Reply]
0x1800436fa  jmp     short loc_180043762
0x1800436fc  test    eax, eax
0x1800436fe  jle     short loc_180043708
0x180043700  movzx   eax, ax
0x180043703  or      eax, 80070000h
0x180043708  mov     [rsp+1A8h+Reply], eax
0x18004370f  mov     [rsp+1A8h+bAlertable], eax
0x180043713  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004371a  mov     r8d, 2ACh; unsigned int
0x180043720  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180043727  mov     ecx, 2; unsigned __int8
0x18004372c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180043731  mov     eax, [rsp+1A8h+Reply]
0x180043738  test    eax, eax
0x18004373a  js      short loc_180043748
0x18004373c  mov     eax, 8000FFFFh
0x180043741  mov     [rsp+1A8h+Reply], eax
0x180043748  mov     r12d, [rsp+1A8h+dwMilliseconds]
0x180043750  mov     r15b, [rsp+1A8h+var_114]
0x180043758  mov     r14b, r15b
0x18004375b  mov     esi, [rsp+1A8h+var_104]
0x180043762  test    eax, eax
0x180043764  jns     short loc_180043778
0x180043766  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004376d  mov     r8d, 2ACh
0x180043773  jmp     loc_18004384C
0x180043778  mov     [rsp+1A8h+bAlertable], 0; bAlertable
0x180043780  mov     r9d, r12d; dwMilliseconds
0x180043783  xor     r8d, r8d; bWaitAll
0x180043786  lea     rdx, [rsp+1A8h+Handles]; lpHandles
0x18004378e  mov     ecx, esi; nCount
0x180043790  call    cs:__imp_WaitForMultipleObjectsEx
0x180043796  mov     esi, eax
0x180043798  mov     r12d, 102h
0x18004379e  test    r14b, r14b
0x1800437a1  jnz     short loc_1800437F5
0x1800437a3  cmp     esi, r12d
0x1800437a6  jz      short loc_1800437AD
0x1800437a8  cmp     esi, 1
0x1800437ab  jnz     short loc_1800437F5
0x1800437ad  mov     edx, 1; fAbort
0x1800437b2  lea     rcx, [rsp+1A8h+pAsync]; pAsync
0x1800437ba  call    cs:__imp_RpcAsyncCancelCall
0x1800437c0  cmp     esi, r12d
0x1800437c3  jnz     short loc_1800437CA
0x1800437c5  mov     r15b, 1
0x1800437c8  jmp     short loc_1800437CD
0x1800437ca  mov     r14b, 1
0x1800437cd  mov     [rsp+1A8h+bAlertable], 0; bAlertable
0x1800437d5  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800437d9  xor     r8d, r8d; bWaitAll
0x1800437dc  lea     rdx, [rsp+1A8h+Handles]; lpHandles
0x1800437e4  lea     ecx, [r8+1]; nCount
0x1800437e8  call    cs:__imp_WaitForMultipleObjectsEx
0x1800437ee  mov     esi, eax
0x1800437f0  test    r15b, r15b
0x1800437f3  jz      short loc_18004379E
0x1800437f5  test    esi, esi
0x1800437f7  jz      short loc_180043814
0x1800437f9  call    cs:__imp_GetLastError
0x1800437ff  test    eax, eax
0x180043801  jle     short loc_18004380B
0x180043803  movzx   eax, ax
0x180043806  or      eax, 80070000h
0x18004380b  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180043812  jmp     short loc_18004383F
0x180043814  lea     rdx, [rsp+1A8h+Reply]; Reply
0x18004381c  lea     rcx, [rsp+1A8h+pAsync]; pAsync
0x180043824  call    cs:__imp_RpcAsyncCompleteCall
0x18004382a  test    eax, eax
0x18004382c  jz      short loc_180043861
0x18004382e  jle     short loc_180043838
0x180043830  movzx   eax, ax
0x180043833  or      eax, 80070000h
0x180043838  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004383f  mov     r8d, 2ACh; unsigned int
0x180043845  mov     [rsp+1A8h+Reply], eax
0x18004384c  mov     [rsp+1A8h+bAlertable], eax
0x180043850  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180043857  mov     ecx, 2; unsigned __int8
0x18004385c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180043861  mov     rcx, qword ptr [rsp+1A8h+pAsync.u]; hObject
0x180043869  test    rcx, rcx
0x18004386c  jz      short loc_180043874
0x18004386e  call    cs:__imp_CloseHandle
0x180043874  test    r15b, r15b
0x180043877  jz      short loc_1800438BA
0x180043879  mov     [rsp+1A8h+Reply], 800705B4h
0x180043884  lea     rdx, [rsp+1A8h+var_100]
0x18004388c  call    ??$RPCCallTimedOut@AEAY0BD@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BD@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[19],ulong &>(char const (&)[19],ulong &)
0x180043891  mov     eax, [rsp+1A8h+Reply]
0x180043898  mov     [rsp+1A8h+bAlertable], eax
0x18004389c  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x1800438a3  mov     r8d, 2ACh; unsigned int
0x1800438a9  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800438b0  mov     ecx, 2; unsigned __int8
0x1800438b5  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800438ba  test    r14b, r14b
0x1800438bd  jz      short loc_1800438ED
0x1800438bf  mov     eax, 800704C7h
0x1800438c4  mov     [rsp+1A8h+Reply], eax
0x1800438cb  mov     [rsp+1A8h+bAlertable], eax
0x1800438cf  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x1800438d6  mov     r8d, 2ACh; unsigned int
0x1800438dc  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800438e3  mov     ecx, 2; unsigned __int8
0x1800438e8  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800438ed  mov     ecx, [rsp+1A8h+Reply]
0x1800438f4  cmp     ecx, 800706B5h
0x1800438fa  jz      short loc_180043904
0x1800438fc  cmp     ecx, 800706BAh
0x180043902  jnz     short loc_180043910
0x180043904  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180043909  mov     ecx, [rsp+1A8h+Reply]; int
0x180043910  lea     rdx, aWlidcacquireto_2; "WLIDCAcquireTokens"
0x180043917  call    ?TranslateRpcServiceError@@YAJJPEBD@Z; TranslateRpcServiceError(long,char const *)
0x18004391c  mov     rcx, [rsp+1A8h+var_38]
0x180043924  xor     rcx, rsp; StackCookie
0x180043927  call    __security_check_cookie
0x18004392c  add     rsp, 180h
0x180043933  pop     r15
0x180043935  pop     r14
0x180043937  pop     r13
0x180043939  pop     r12
0x18004393b  pop     rsi
0x18004393c  retn
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
