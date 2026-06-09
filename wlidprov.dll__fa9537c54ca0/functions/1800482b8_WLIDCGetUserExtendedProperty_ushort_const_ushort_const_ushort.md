# WLIDCGetUserExtendedProperty(ushort const *,ushort const *,ushort * *)

- ea: `0x1800482b8`
- end: `0x18004861c`
- name: `?WLIDCGetUserExtendedProperty@@YAJPEBG0PEAPEAG@Z`
- size: `868`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180041830`

## callees

- `0x18000a400`
- `0x18000f870`
- `0x180010c68`
- `0x180011588`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x18004204c`
- `0x180043240`
- `0x1800482b8`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004839f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004839f`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004848b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800484dd`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004848b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800484dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800483b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800484ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800483b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800484ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004855a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004855a`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180048358`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180048358`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800484b2`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800484b2`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180048403`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180048403`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180048513`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180048513`

## string_xrefs

- `0x1800483c4`: `RPC failed to create new event, hr = %#x`
- `0x180048527`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCGetUserExtendedProperty(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  __int64 result; // rax
  DWORD v6; // esi
  char v7; // r15
  char v8; // r14
  int LastError; // eax
  const unsigned __int16 *v10; // r9
  unsigned int v11; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v13; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-F8h]
  int Reply; // [rsp+40h] [rbp-D8h] BYREF
  char v16; // [rsp+44h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-D0h] BYREF
  DWORD v18; // [rsp+4Ch] [rbp-CCh] BYREF
  __int64 v19; // [rsp+50h] [rbp-C8h] BYREF
  unsigned __int16 **v20; // [rsp+58h] [rbp-C0h]
  HANDLE Handles[2]; // [rsp+60h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-A8h] BYREF

  v20 = a3;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  v19 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v19);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v6 = dwMilliseconds;
  v18 = dwMilliseconds;
  v7 = 0;
  v16 = 0;
  v8 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v11 = 753;
LABEL_30:
    Reply = LastError;
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
    v10 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x14u, 0, &pAsync, v19, a1, a2, v20);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v10 = L"RPC call failed, hr = %#x";
    v11 = 755;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v11,
      v10,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
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
LABEL_29:
    v11 = 755;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v7 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[29],unsigned long &>("WLIDCGetUserExtendedProperty", &v18);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x2F3u,
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
      0x2F3u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v19);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x1800482b8  push    rsi
0x1800482ba  push    r12
0x1800482bc  push    r13
0x1800482be  push    r14
0x1800482c0  push    r15
0x1800482c2  sub     rsp, 0F0h
0x1800482c9  mov     rax, cs:__security_cookie
0x1800482d0  xor     rax, rsp
0x1800482d3  mov     [rsp+118h+var_38], rax
0x1800482db  mov     [rsp+118h+var_C0], r8
0x1800482e0  mov     r13, rdx
0x1800482e3  mov     r12, rcx
0x1800482e6  mov     [rsp+118h+dwMilliseconds], 0
0x1800482ee  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x1800482f3  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x1800482f8  mov     [rsp+118h+Reply], 0
0x180048300  mov     [rsp+118h+var_C8], 0
0x180048309  lea     rcx, [rsp+118h+var_C8]; this
0x18004830e  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x180048313  mov     [rsp+118h+Reply], eax
0x180048317  test    eax, eax
0x180048319  js      loc_1800485FB
0x18004831f  xor     edx, edx; Val
0x180048321  lea     r8d, [rdx+70h]; Size
0x180048325  lea     rcx, [rsp+118h+pAsync]; void *
0x18004832a  call    memset_0
0x18004832f  mov     esi, [rsp+118h+dwMilliseconds]
0x180048333  mov     [rsp+118h+dwMilliseconds], esi
0x180048337  mov     [rsp+118h+var_CC], esi
0x18004833b  xor     r15b, r15b
0x18004833e  mov     [rsp+118h+var_D4], r15b
0x180048343  xor     r14b, r14b
0x180048346  xorps   xmm0, xmm0
0x180048349  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x18004834e  mov     edx, 70h ; 'p'; Size
0x180048353  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180048358  call    cs:__imp_RpcAsyncInitializeHandle
0x18004835e  test    eax, eax
0x180048360  jz      short loc_18004837E
0x180048362  jle     short loc_18004836C
0x180048364  movzx   eax, ax
0x180048367  or      eax, 80070000h
0x18004836c  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180048373  mov     r8d, 2F1h
0x180048379  jmp     loc_180048534
0x18004837e  mov     [rsp+118h+pAsync.UserInfo], 0
0x18004838a  mov     [rsp+118h+pAsync.NotificationType], 1
0x180048395  xor     r9d, r9d; lpName
0x180048398  xor     r8d, r8d; bInitialState
0x18004839b  xor     edx, edx; bManualReset
0x18004839d  xor     ecx, ecx; lpEventAttributes
0x18004839f  call    cs:__imp_CreateEventW
0x1800483a5  mov     qword ptr [rsp+118h+pAsync.u], rax
0x1800483ad  test    rax, rax
0x1800483b0  jnz     short loc_1800483CD
0x1800483b2  call    cs:__imp_GetLastError
0x1800483b8  test    eax, eax
0x1800483ba  jle     short loc_1800483C4
0x1800483bc  movzx   eax, ax
0x1800483bf  or      eax, 80070000h
0x1800483c4  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x1800483cb  jmp     short loc_180048373
0x1800483cd  mov     [rsp+118h+Handles], rax
0x1800483d2  mov     rax, [rsp+118h+var_C0]
0x1800483d7  mov     [rsp+118h+var_E0], rax
0x1800483dc  mov     [rsp+118h+var_E8], r13
0x1800483e1  mov     [rsp+118h+var_F0], r12
0x1800483e6  mov     rax, [rsp+118h+var_C8]
0x1800483eb  mov     qword ptr [rsp+118h+bAlertable], rax
0x1800483f0  lea     r9, [rsp+118h+pAsync]
0x1800483f5  xor     r8d, r8d; pReturnValue
0x1800483f8  lea     edx, [r8+14h]; nProcNum
0x1800483fc  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180048403  call    cs:__imp_Ndr64AsyncClientCall
0x180048409  mov     eax, [rsp+118h+Reply]
0x18004840d  jmp     short loc_18004845E
0x18004840f  test    eax, eax
0x180048411  jle     short loc_18004841B
0x180048413  movzx   eax, ax
0x180048416  or      eax, 80070000h
0x18004841b  mov     [rsp+118h+Reply], eax
0x18004841f  mov     [rsp+118h+bAlertable], eax
0x180048423  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004842a  mov     r8d, 2F3h; unsigned int
0x180048430  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180048437  mov     ecx, 2; unsigned __int8
0x18004843c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180048441  mov     eax, [rsp+118h+Reply]
0x180048445  test    eax, eax
0x180048447  js      short loc_180048452
0x180048449  mov     eax, 8000FFFFh
0x18004844e  mov     [rsp+118h+Reply], eax
0x180048452  mov     esi, [rsp+118h+dwMilliseconds]
0x180048456  mov     r15b, [rsp+118h+var_D4]
0x18004845b  mov     r14b, r15b
0x18004845e  test    eax, eax
0x180048460  jns     short loc_180048474
0x180048462  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180048469  mov     r8d, 2F3h
0x18004846f  jmp     loc_180048538
0x180048474  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004847c  mov     r9d, esi; dwMilliseconds
0x18004847f  xor     r8d, r8d; bWaitAll
0x180048482  lea     rdx, [rsp+118h+Handles]; lpHandles
0x180048487  lea     ecx, [r8+1]; nCount
0x18004848b  call    cs:__imp_WaitForMultipleObjectsEx
0x180048491  mov     esi, eax
0x180048493  mov     r12d, 102h
0x180048499  test    r14b, r14b
0x18004849c  jnz     short loc_1800484EA
0x18004849e  cmp     esi, r12d
0x1800484a1  jz      short loc_1800484A8
0x1800484a3  cmp     esi, 1
0x1800484a6  jnz     short loc_1800484EA
0x1800484a8  mov     edx, 1; fAbort
0x1800484ad  lea     rcx, [rsp+118h+pAsync]; pAsync
0x1800484b2  call    cs:__imp_RpcAsyncCancelCall
0x1800484b8  cmp     esi, r12d
0x1800484bb  jnz     short loc_1800484C2
0x1800484bd  mov     r15b, 1
0x1800484c0  jmp     short loc_1800484C5
0x1800484c2  mov     r14b, 1
0x1800484c5  mov     [rsp+118h+bAlertable], 0; bAlertable
0x1800484cd  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800484d1  xor     r8d, r8d; bWaitAll
0x1800484d4  lea     rdx, [rsp+118h+Handles]; lpHandles
0x1800484d9  lea     ecx, [r8+1]; nCount
0x1800484dd  call    cs:__imp_WaitForMultipleObjectsEx
0x1800484e3  mov     esi, eax
0x1800484e5  test    r15b, r15b
0x1800484e8  jz      short loc_180048499
0x1800484ea  test    esi, esi
0x1800484ec  jz      short loc_180048509
0x1800484ee  call    cs:__imp_GetLastError
0x1800484f4  test    eax, eax
0x1800484f6  jle     short loc_180048500
0x1800484f8  movzx   eax, ax
0x1800484fb  or      eax, 80070000h
0x180048500  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180048507  jmp     short loc_18004852E
0x180048509  lea     rdx, [rsp+118h+Reply]; Reply
0x18004850e  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180048513  call    cs:__imp_RpcAsyncCompleteCall
0x180048519  test    eax, eax
0x18004851b  jz      short loc_18004854D
0x18004851d  jle     short loc_180048527
0x18004851f  movzx   eax, ax
0x180048522  or      eax, 80070000h
0x180048527  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004852e  mov     r8d, 2F3h; unsigned int
0x180048534  mov     [rsp+118h+Reply], eax
0x180048538  mov     [rsp+118h+bAlertable], eax
0x18004853c  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180048543  mov     ecx, 2; unsigned __int8
0x180048548  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004854d  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x180048555  test    rcx, rcx
0x180048558  jz      short loc_180048560
0x18004855a  call    cs:__imp_CloseHandle
0x180048560  test    r15b, r15b
0x180048563  jz      short loc_1800485A4
0x180048565  mov     [rsp+118h+Reply], 800705B4h
0x18004856d  lea     rdx, [rsp+118h+var_CC]
0x180048572  lea     rcx, aWlidcgetuserex; "WLIDCGetUserExtendedProperty"
0x180048579  call    ??$RPCCallTimedOut@AEAY0BN@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BN@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[29],ulong &>(char const (&)[29],ulong &)
0x18004857e  mov     eax, [rsp+118h+Reply]
0x180048582  mov     [rsp+118h+bAlertable], eax
0x180048586  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004858d  mov     r8d, 2F3h; unsigned int
0x180048593  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004859a  mov     ecx, 2; unsigned __int8
0x18004859f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800485a4  test    r14b, r14b
0x1800485a7  jz      short loc_1800485D4
0x1800485a9  mov     eax, 800704C7h
0x1800485ae  mov     [rsp+118h+Reply], eax
0x1800485b2  mov     [rsp+118h+bAlertable], eax
0x1800485b6  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x1800485bd  mov     r8d, 2F3h; unsigned int
0x1800485c3  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800485ca  mov     ecx, 2; unsigned __int8
0x1800485cf  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800485d4  cmp     [rsp+118h+Reply], 800706B5h
0x1800485dc  jz      short loc_1800485E8
0x1800485de  cmp     [rsp+118h+Reply], 800706BAh
0x1800485e6  jnz     short loc_1800485ED
0x1800485e8  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x1800485ed  lea     rcx, [rsp+118h+var_C8]; this
0x1800485f2  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x1800485f7  mov     eax, [rsp+118h+Reply]
0x1800485fb  mov     rcx, [rsp+118h+var_38]
0x180048603  xor     rcx, rsp; StackCookie
0x180048606  call    __security_check_cookie
0x18004860b  add     rsp, 0F0h
0x180048612  pop     r15
0x180048614  pop     r14
0x180048616  pop     r13
0x180048618  pop     r12
0x18004861a  pop     rsi
0x18004861b  retn
0x180057062  push    rbp
0x180057064  sub     rsp, 40h
0x180057068  mov     rbp, rdx
0x18005706b  mov     rcx, [rcx]
0x18005706e  mov     ecx, [rcx]; unsigned int
0x180057070  call    ?WLIDpExceptionFilter@@YAHK@Z
0x180057075  nop
0x180057076  add     rsp, 40h
0x18005707a  pop     rbp
0x18005707b  retn
```
