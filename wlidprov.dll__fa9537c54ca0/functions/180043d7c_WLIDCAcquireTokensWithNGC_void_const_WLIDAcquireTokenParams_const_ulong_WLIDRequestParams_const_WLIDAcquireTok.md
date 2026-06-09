# WLIDCAcquireTokensWithNGC(void * const,_WLIDAcquireTokenParams * const,ulong,_WLIDRequestParams * const,_WLIDAcquireTokenResults *,_WLIDResponseParams * *,void *,int)

- ea: `0x180043d7c`
- end: `0x1800441f0`
- name: `?WLIDCAcquireTokensWithNGC@@YAJQEAXQEAU_WLIDAcquireTokenParams@@KQEAU_WLIDRequestParams@@PEAU_WLIDAcquireTokenResults@@PEAPEAU_WLIDResponseParams@@PEAXH@Z`
- size: `1140`
- prototype: `__int64 __fastcall(void *const, struct _WLIDAcquireTokenParams *const, unsigned int, struct _WLIDRequestParams *const, struct _WLIDAcquireTokenResults *, struct _WLIDResponseParams **, void *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180041570`

## callees

- `0x18000a400`
- `0x180010c68`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180041f38`
- `0x180043240`
- `0x180043d7c`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180043ead`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180043ead`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004404a`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800440a2`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004404a`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800440a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043ec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800440b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043ec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800440b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044128`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044128`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180043e66`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180043e66`
- `RPCRT4!RpcAsyncCancelCall` at `0x180044074`
- `RPCRT4!RpcAsyncCancelCall` at `0x180044074`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180043fa7`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180043fa7`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800440de`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800440de`

## string_xrefs

- `0x180043ed2`: `RPC failed to create new event, hr = %#x`
- `0x1800440f2`: `RPC Async complete call failed, hr = %#x`
- `0x180044146`: `WLIDCAcquireTokensWithNGC`

## pseudocode

```c
__int64 __fastcall WLIDCAcquireTokensWithNGC(
        void *const a1,
        struct _WLIDAcquireTokenParams *const a2,
        int a3,
        struct _WLIDRequestParams *const a4,
        struct _WLIDAcquireTokenResults *a5,
        struct _WLIDResponseParams **a6,
        void *a7,
        int a8)
{
  DWORD v8; // r12d
  char v9; // r15
  char v10; // r14
  int LastError; // eax
  const unsigned __int16 *v12; // r9
  unsigned int v13; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v15; // esi
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-168h]
  unsigned int Reply; // [rsp+90h] [rbp-F8h] BYREF
  char v19; // [rsp+94h] [rbp-F4h]
  DWORD dwMilliseconds; // [rsp+98h] [rbp-F0h] BYREF
  int v21; // [rsp+9Ch] [rbp-ECh]
  int v22; // [rsp+A0h] [rbp-E8h]
  DWORD v23; // [rsp+A4h] [rbp-E4h] BYREF
  HANDLE Handles[2]; // [rsp+A8h] [rbp-E0h] BYREF
  struct _WLIDResponseParams **v25; // [rsp+B8h] [rbp-D0h]
  struct _WLIDAcquireTokenParams *v26; // [rsp+C0h] [rbp-C8h]
  struct _WLIDRequestParams *v27; // [rsp+C8h] [rbp-C0h]
  void *v28; // [rsp+D0h] [rbp-B8h]
  struct _RPC_ASYNC_STATE pAsync; // [rsp+E0h] [rbp-A8h] BYREF

  v27 = a4;
  v21 = a3;
  v26 = a2;
  v28 = a1;
  v25 = a6;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  if ( a8 )
    dwMilliseconds *= 3;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v8 = dwMilliseconds;
  v23 = dwMilliseconds;
  v9 = 0;
  v19 = 0;
  v10 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v12 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_7:
    v13 = 1499;
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
    v12 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_7;
  }
  Handles[0] = EventW;
  if ( a7 )
    Handles[1] = a7;
  v22 = (a7 != 0) + 1;
  Ndr64AsyncClientCall(
    (MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo,
    0x49u,
    0,
    &pAsync,
    v28,
    *(_QWORD *)v26,
    v21,
    v27,
    *((_QWORD *)v26 + 1),
    *((_QWORD *)v26 + 2),
    *((_QWORD *)v26 + 3),
    a5,
    (char *)a5 + 4,
    (char *)a5 + 8,
    (char *)a5 + 16,
    v25,
    (char *)a5 + 12);
  v15 = WaitForMultipleObjectsEx((a7 != 0) + 1, Handles, 0, v8, 0);
  do
  {
    if ( v10 || v15 != 258 && v15 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v15 == 258 )
      v9 = 1;
    else
      v10 = 1;
    v15 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v9 );
  if ( v15 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v12 = L"Encountered error while waiting on RPC call, hr = %#x";
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_32;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v12 = L"RPC Async complete call failed, hr = %#x";
  }
  v13 = 1514;
LABEL_31:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(
    2u,
    "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
    v13,
    v12,
    *(_QWORD *)bAlertable);
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v9 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[26],unsigned long &>("WLIDCAcquireTokensWithNGC", &v23);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x5EAu,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v10 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x5EAu,
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
0x180043d7c  push    rsi
0x180043d7e  push    r12
0x180043d80  push    r13
0x180043d82  push    r14
0x180043d84  push    r15
0x180043d86  sub     rsp, 160h
0x180043d8d  mov     rax, cs:__security_cookie
0x180043d94  xor     rax, rsp
0x180043d97  mov     [rsp+188h+var_38], rax
0x180043d9f  mov     [rsp+188h+var_C0], r9
0x180043da7  mov     [rsp+188h+var_EC], r8d
0x180043daf  mov     [rsp+188h+var_C8], rdx
0x180043db7  mov     [rsp+188h+var_B8], rcx
0x180043dbf  mov     r13, [rsp+188h+arg_20]
0x180043dc7  mov     rax, [rsp+188h+arg_28]
0x180043dcf  mov     [rsp+188h+var_D0], rax
0x180043dd7  mov     [rsp+188h+Reply], 0
0x180043de2  mov     [rsp+188h+dwMilliseconds], 0
0x180043ded  lea     r8, [rsp+188h+dwMilliseconds]; unsigned int *
0x180043df5  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180043dfa  cmp     [rsp+188h+arg_38], 0
0x180043e02  jz      short loc_180043E15
0x180043e04  mov     eax, [rsp+188h+dwMilliseconds]
0x180043e0b  lea     eax, [rax+rax*2]
0x180043e0e  mov     [rsp+188h+dwMilliseconds], eax
0x180043e15  xor     edx, edx; Val
0x180043e17  lea     r8d, [rdx+70h]; Size
0x180043e1b  lea     rcx, [rsp+188h+pAsync]; void *
0x180043e23  call    memset_0
0x180043e28  mov     r12d, [rsp+188h+dwMilliseconds]
0x180043e30  mov     [rsp+188h+dwMilliseconds], r12d
0x180043e38  mov     [rsp+188h+var_E4], r12d
0x180043e40  xor     r15b, r15b
0x180043e43  mov     [rsp+188h+var_F4], r15b
0x180043e4b  xor     r14b, r14b
0x180043e4e  xorps   xmm0, xmm0
0x180043e51  movups  xmmword ptr [rsp+188h+Handles], xmm0
0x180043e59  mov     edx, 70h ; 'p'; Size
0x180043e5e  lea     rcx, [rsp+188h+pAsync]; pAsync
0x180043e66  call    cs:__imp_RpcAsyncInitializeHandle
0x180043e6c  test    eax, eax
0x180043e6e  jz      short loc_180043E8C
0x180043e70  jle     short loc_180043E7A
0x180043e72  movzx   eax, ax
0x180043e75  or      eax, 80070000h
0x180043e7a  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180043e81  mov     r8d, 5DBh
0x180043e87  jmp     loc_1800440FF
0x180043e8c  mov     [rsp+188h+pAsync.UserInfo], 0
0x180043e98  mov     [rsp+188h+pAsync.NotificationType], 1
0x180043ea3  xor     r9d, r9d; lpName
0x180043ea6  xor     r8d, r8d; bInitialState
0x180043ea9  xor     edx, edx; bManualReset
0x180043eab  xor     ecx, ecx; lpEventAttributes
0x180043ead  call    cs:__imp_CreateEventW
0x180043eb3  mov     qword ptr [rsp+188h+pAsync.u], rax
0x180043ebb  test    rax, rax
0x180043ebe  jnz     short loc_180043EDB
0x180043ec0  call    cs:__imp_GetLastError
0x180043ec6  test    eax, eax
0x180043ec8  jle     short loc_180043ED2
0x180043eca  movzx   eax, ax
0x180043ecd  or      eax, 80070000h
0x180043ed2  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180043ed9  jmp     short loc_180043E81
0x180043edb  mov     [rsp+188h+Handles], rax
0x180043ee3  mov     rax, [rsp+188h+arg_30]
0x180043eeb  test    rax, rax
0x180043eee  jz      short loc_180043EF8
0x180043ef0  mov     [rsp+188h+Handles+8], rax
0x180043ef8  neg     rax
0x180043efb  sbb     esi, esi
0x180043efd  neg     esi
0x180043eff  inc     esi
0x180043f01  mov     [rsp+188h+var_E8], esi
0x180043f08  lea     rax, [r13+0Ch]
0x180043f0c  lea     rcx, [r13+10h]
0x180043f10  lea     rdx, [r13+8]
0x180043f14  lea     r8, [r13+4]
0x180043f18  mov     [rsp+188h+var_108], rax
0x180043f20  mov     rax, [rsp+188h+var_D0]
0x180043f28  mov     [rsp+188h+var_110], rax
0x180043f2d  mov     [rsp+188h+var_118], rcx
0x180043f32  mov     [rsp+188h+var_120], rdx
0x180043f37  mov     [rsp+188h+var_128], r8
0x180043f3c  mov     [rsp+188h+var_130], r13
0x180043f41  mov     rcx, [rsp+188h+var_C8]
0x180043f49  mov     rax, [rcx+18h]
0x180043f4d  mov     [rsp+188h+var_138], rax
0x180043f52  mov     rax, [rcx+10h]
0x180043f56  mov     [rsp+188h+var_140], rax
0x180043f5b  mov     rax, [rcx+8]
0x180043f5f  mov     [rsp+188h+var_148], rax
0x180043f64  mov     rax, [rsp+188h+var_C0]
0x180043f6c  mov     [rsp+188h+var_150], rax
0x180043f71  mov     eax, [rsp+188h+var_EC]
0x180043f78  mov     [rsp+188h+var_158], eax
0x180043f7c  mov     rax, [rcx]
0x180043f7f  mov     [rsp+188h+var_160], rax
0x180043f84  mov     rax, [rsp+188h+var_B8]
0x180043f8c  mov     qword ptr [rsp+188h+bAlertable], rax
0x180043f91  lea     r9, [rsp+188h+pAsync]
0x180043f99  xor     r8d, r8d; pReturnValue
0x180043f9c  lea     edx, [r8+49h]; nProcNum
0x180043fa0  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180043fa7  call    cs:__imp_Ndr64AsyncClientCall
0x180043fad  mov     eax, [rsp+188h+Reply]
0x180043fb4  jmp     short loc_18004401C
0x180043fb6  test    eax, eax
0x180043fb8  jle     short loc_180043FC2
0x180043fba  movzx   eax, ax
0x180043fbd  or      eax, 80070000h
0x180043fc2  mov     [rsp+188h+Reply], eax
0x180043fc9  mov     [rsp+188h+bAlertable], eax
0x180043fcd  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180043fd4  mov     r8d, 5EAh; unsigned int
0x180043fda  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180043fe1  mov     ecx, 2; unsigned __int8
0x180043fe6  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180043feb  mov     eax, [rsp+188h+Reply]
0x180043ff2  test    eax, eax
0x180043ff4  js      short loc_180044002
0x180043ff6  mov     eax, 8000FFFFh
0x180043ffb  mov     [rsp+188h+Reply], eax
0x180044002  mov     r12d, [rsp+188h+dwMilliseconds]
0x18004400a  mov     r15b, [rsp+188h+var_F4]
0x180044012  mov     r14b, r15b
0x180044015  mov     esi, [rsp+188h+var_E8]
0x18004401c  test    eax, eax
0x18004401e  jns     short loc_180044032
0x180044020  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180044027  mov     r8d, 5EAh
0x18004402d  jmp     loc_180044106
0x180044032  mov     [rsp+188h+bAlertable], 0; bAlertable
0x18004403a  mov     r9d, r12d; dwMilliseconds
0x18004403d  xor     r8d, r8d; bWaitAll
0x180044040  lea     rdx, [rsp+188h+Handles]; lpHandles
0x180044048  mov     ecx, esi; nCount
0x18004404a  call    cs:__imp_WaitForMultipleObjectsEx
0x180044050  mov     esi, eax
0x180044052  mov     r12d, 102h
0x180044058  test    r14b, r14b
0x18004405b  jnz     short loc_1800440AF
0x18004405d  cmp     esi, r12d
0x180044060  jz      short loc_180044067
0x180044062  cmp     esi, 1
0x180044065  jnz     short loc_1800440AF
0x180044067  mov     edx, 1; fAbort
0x18004406c  lea     rcx, [rsp+188h+pAsync]; pAsync
0x180044074  call    cs:__imp_RpcAsyncCancelCall
0x18004407a  cmp     esi, r12d
0x18004407d  jnz     short loc_180044084
0x18004407f  mov     r15b, 1
0x180044082  jmp     short loc_180044087
0x180044084  mov     r14b, 1
0x180044087  mov     [rsp+188h+bAlertable], 0; bAlertable
0x18004408f  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180044093  xor     r8d, r8d; bWaitAll
0x180044096  lea     rdx, [rsp+188h+Handles]; lpHandles
0x18004409e  lea     ecx, [r8+1]; nCount
0x1800440a2  call    cs:__imp_WaitForMultipleObjectsEx
0x1800440a8  mov     esi, eax
0x1800440aa  test    r15b, r15b
0x1800440ad  jz      short loc_180044058
0x1800440af  test    esi, esi
0x1800440b1  jz      short loc_1800440CE
0x1800440b3  call    cs:__imp_GetLastError
0x1800440b9  test    eax, eax
0x1800440bb  jle     short loc_1800440C5
0x1800440bd  movzx   eax, ax
0x1800440c0  or      eax, 80070000h
0x1800440c5  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x1800440cc  jmp     short loc_1800440F9
0x1800440ce  lea     rdx, [rsp+188h+Reply]; Reply
0x1800440d6  lea     rcx, [rsp+188h+pAsync]; pAsync
0x1800440de  call    cs:__imp_RpcAsyncCompleteCall
0x1800440e4  test    eax, eax
0x1800440e6  jz      short loc_18004411B
0x1800440e8  jle     short loc_1800440F2
0x1800440ea  movzx   eax, ax
0x1800440ed  or      eax, 80070000h
0x1800440f2  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x1800440f9  mov     r8d, 5EAh; unsigned int
0x1800440ff  mov     [rsp+188h+Reply], eax
0x180044106  mov     [rsp+188h+bAlertable], eax
0x18004410a  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180044111  mov     ecx, 2; unsigned __int8
0x180044116  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004411b  mov     rcx, qword ptr [rsp+188h+pAsync.u]; hObject
0x180044123  test    rcx, rcx
0x180044126  jz      short loc_18004412E
0x180044128  call    cs:__imp_CloseHandle
0x18004412e  test    r15b, r15b
0x180044131  jz      short loc_18004417B
0x180044133  mov     [rsp+188h+Reply], 800705B4h
0x18004413e  lea     rdx, [rsp+188h+var_E4]
0x180044146  lea     rcx, aWlidcacquireto_1; "WLIDCAcquireTokensWithNGC"
0x18004414d  call    ??$RPCCallTimedOut@AEAY0BK@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BK@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[26],ulong &>(char const (&)[26],ulong &)
0x180044152  mov     eax, [rsp+188h+Reply]
0x180044159  mov     [rsp+188h+bAlertable], eax
0x18004415d  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180044164  mov     r8d, 5EAh; unsigned int
0x18004416a  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180044171  mov     ecx, 2; unsigned __int8
0x180044176  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004417b  test    r14b, r14b
0x18004417e  jz      short loc_1800441AE
0x180044180  mov     eax, 800704C7h
0x180044185  mov     [rsp+188h+Reply], eax
0x18004418c  mov     [rsp+188h+bAlertable], eax
0x180044190  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180044197  mov     r8d, 5EAh; unsigned int
0x18004419d  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800441a4  mov     ecx, 2; unsigned __int8
0x1800441a9  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800441ae  mov     eax, [rsp+188h+Reply]
0x1800441b5  cmp     eax, 800706B5h
0x1800441ba  jz      short loc_1800441C3
0x1800441bc  cmp     eax, 800706BAh
0x1800441c1  jnz     short loc_1800441CF
0x1800441c3  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x1800441c8  mov     eax, [rsp+188h+Reply]
0x1800441cf  mov     rcx, [rsp+188h+var_38]
0x1800441d7  xor     rcx, rsp; StackCookie
0x1800441da  call    __security_check_cookie
0x1800441df  add     rsp, 160h
0x1800441e6  pop     r15
0x1800441e8  pop     r14
0x1800441ea  pop     r13
0x1800441ec  pop     r12
0x1800441ee  pop     rsi
0x1800441ef  retn
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
