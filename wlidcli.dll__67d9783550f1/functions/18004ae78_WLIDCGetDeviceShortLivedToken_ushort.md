# WLIDCGetDeviceShortLivedToken(ushort * *)

- ea: `0x18004ae78`
- end: `0x18004b1b7`
- name: `?WLIDCGetDeviceShortLivedToken@@YAJPEAPEAG@Z`
- size: `831`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180025fc0`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180045420`
- `0x180046ce0`
- `0x18004ae78`
- `0x18004cd04`
- `0x180050c84`
- `0x180050e40`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004b02f`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004b081`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004b02f`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004b081`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004af52`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004af52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004af65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b092`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004af65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b092`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b0fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b0fe`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004b056`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004b056`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004afa7`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004afa7`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004b0b7`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004b0b7`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004af0e`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004af0e`

## string_xrefs

- `0x18004af77`: `RPC failed to create new event, hr = %#x`
- `0x18004b0cb`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCGetDeviceShortLivedToken(unsigned __int16 **a1, unsigned int a2)
{
  __int64 result; // rax
  DWORD v4; // esi
  char v5; // r15
  char v6; // r14
  int LastError; // eax
  const unsigned __int16 *v8; // r9
  unsigned int v9; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v11; // esi
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  BOOL bAlertable[2]; // [rsp+20h] [rbp-E8h]
  int Reply; // [rsp+30h] [rbp-D8h] BYREF
  char v15; // [rsp+34h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+38h] [rbp-D0h] BYREF
  DWORD v17; // [rsp+3Ch] [rbp-CCh] BYREF
  __int64 v18; // [rsp+40h] [rbp-C8h] BYREF
  HANDLE Handles[3]; // [rsp+48h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+60h] [rbp-A8h] BYREF

  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  v18 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v18);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v4 = dwMilliseconds;
  v17 = dwMilliseconds;
  v5 = 0;
  v15 = 0;
  v6 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v9 = 1014;
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
    v8 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x2Du, 0, &pAsync, v18, a1);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v8 = L"RPC call failed, hr = %#x";
    v9 = 1016;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v9,
      v8,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
  v11 = WaitForMultipleObjectsEx(1u, Handles, 0, v4, 0);
  do
  {
    if ( v6 || v11 != 258 && v11 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v11 == 258 )
      v5 = 1;
    else
      v6 = 1;
    v11 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v5 );
  if ( v11 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = L"Encountered error while waiting on RPC call, hr = %#x";
LABEL_29:
    v9 = 1016;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  NotificationRoutine = pAsync.u.APC.NotificationRoutine;
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v5 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[30],unsigned long &>(
      (__int64)NotificationRoutine,
      (int *)&v17);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x3F8u,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v6 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x3F8u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v18);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x18004ae78  push    rsi
0x18004ae7a  push    r12
0x18004ae7c  push    r14
0x18004ae7e  push    r15
0x18004ae80  sub     rsp, 0E8h
0x18004ae87  mov     rax, cs:__security_cookie
0x18004ae8e  xor     rax, rsp
0x18004ae91  mov     [rsp+108h+var_38], rax
0x18004ae99  mov     r12, rcx
0x18004ae9c  mov     [rsp+108h+dwMilliseconds], 0
0x18004aea4  lea     r8, [rsp+108h+dwMilliseconds]; unsigned int *
0x18004aea9  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004aeae  mov     [rsp+108h+Reply], 0
0x18004aeb6  mov     [rsp+108h+var_C8], 0
0x18004aebf  lea     rcx, [rsp+108h+var_C8]; this
0x18004aec4  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18004aec9  mov     [rsp+108h+Reply], eax
0x18004aecd  test    eax, eax
0x18004aecf  js      loc_18004B198
0x18004aed5  xor     edx, edx; Val
0x18004aed7  lea     r8d, [rdx+70h]; Size
0x18004aedb  lea     rcx, [rsp+108h+pAsync]; void *
0x18004aee0  call    memset_0
0x18004aee5  mov     esi, [rsp+108h+dwMilliseconds]
0x18004aee9  mov     [rsp+108h+dwMilliseconds], esi
0x18004aeed  mov     [rsp+108h+var_CC], esi
0x18004aef1  xor     r15b, r15b
0x18004aef4  mov     [rsp+108h+var_D4], r15b
0x18004aef9  xor     r14b, r14b
0x18004aefc  xorps   xmm0, xmm0
0x18004aeff  movups  xmmword ptr [rsp+108h+Handles], xmm0
0x18004af04  mov     edx, 70h ; 'p'; Size
0x18004af09  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004af0e  call    cs:__imp_RpcAsyncInitializeHandle
0x18004af14  test    eax, eax
0x18004af16  jz      short loc_18004AF34
0x18004af18  jle     short loc_18004AF22
0x18004af1a  movzx   eax, ax
0x18004af1d  or      eax, 80070000h
0x18004af22  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004af29  mov     r8d, 3F6h
0x18004af2f  jmp     loc_18004B0D8
0x18004af34  mov     [rsp+108h+pAsync.UserInfo], 0
0x18004af3d  mov     [rsp+108h+pAsync.NotificationType], 1
0x18004af48  xor     r9d, r9d; lpName
0x18004af4b  xor     r8d, r8d; bInitialState
0x18004af4e  xor     edx, edx; bManualReset
0x18004af50  xor     ecx, ecx; lpEventAttributes
0x18004af52  call    cs:__imp_CreateEventW
0x18004af58  mov     qword ptr [rsp+108h+pAsync.u], rax
0x18004af60  test    rax, rax
0x18004af63  jnz     short loc_18004AF80
0x18004af65  call    cs:__imp_GetLastError
0x18004af6b  test    eax, eax
0x18004af6d  jle     short loc_18004AF77
0x18004af6f  movzx   eax, ax
0x18004af72  or      eax, 80070000h
0x18004af77  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004af7e  jmp     short loc_18004AF29
0x18004af80  mov     [rsp+108h+Handles], rax
0x18004af85  mov     [rsp+108h+var_E0], r12
0x18004af8a  mov     rax, [rsp+108h+var_C8]
0x18004af8f  mov     qword ptr [rsp+108h+bAlertable], rax
0x18004af94  lea     r9, [rsp+108h+pAsync]
0x18004af99  xor     r8d, r8d; pReturnValue
0x18004af9c  lea     edx, [r8+2Dh]; nProcNum
0x18004afa0  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004afa7  call    cs:__imp_Ndr64AsyncClientCall
0x18004afad  mov     eax, [rsp+108h+Reply]
0x18004afb1  jmp     short loc_18004B002
0x18004afb3  test    eax, eax
0x18004afb5  jle     short loc_18004AFBF
0x18004afb7  movzx   eax, ax
0x18004afba  or      eax, 80070000h
0x18004afbf  mov     [rsp+108h+Reply], eax
0x18004afc3  mov     [rsp+108h+bAlertable], eax
0x18004afc7  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004afce  mov     r8d, 3F8h; unsigned int
0x18004afd4  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004afdb  mov     ecx, 2; unsigned __int8
0x18004afe0  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004afe5  mov     eax, [rsp+108h+Reply]
0x18004afe9  test    eax, eax
0x18004afeb  js      short loc_18004AFF6
0x18004afed  mov     eax, 8000FFFFh
0x18004aff2  mov     [rsp+108h+Reply], eax
0x18004aff6  mov     esi, [rsp+108h+dwMilliseconds]
0x18004affa  mov     r15b, [rsp+108h+var_D4]
0x18004afff  mov     r14b, r15b
0x18004b002  test    eax, eax
0x18004b004  jns     short loc_18004B018
0x18004b006  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004b00d  mov     r8d, 3F8h
0x18004b013  jmp     loc_18004B0DC
0x18004b018  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18004b020  mov     r9d, esi; dwMilliseconds
0x18004b023  xor     r8d, r8d; bWaitAll
0x18004b026  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18004b02b  lea     ecx, [r8+1]; nCount
0x18004b02f  call    cs:__imp_WaitForMultipleObjectsEx
0x18004b035  mov     esi, eax
0x18004b037  mov     r12d, 102h
0x18004b03d  test    r14b, r14b
0x18004b040  jnz     short loc_18004B08E
0x18004b042  cmp     esi, r12d
0x18004b045  jz      short loc_18004B04C
0x18004b047  cmp     esi, 1
0x18004b04a  jnz     short loc_18004B08E
0x18004b04c  mov     edx, 1; fAbort
0x18004b051  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004b056  call    cs:__imp_RpcAsyncCancelCall
0x18004b05c  cmp     esi, r12d
0x18004b05f  jnz     short loc_18004B066
0x18004b061  mov     r15b, 1
0x18004b064  jmp     short loc_18004B069
0x18004b066  mov     r14b, 1
0x18004b069  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18004b071  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004b075  xor     r8d, r8d; bWaitAll
0x18004b078  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18004b07d  lea     ecx, [r8+1]; nCount
0x18004b081  call    cs:__imp_WaitForMultipleObjectsEx
0x18004b087  mov     esi, eax
0x18004b089  test    r15b, r15b
0x18004b08c  jz      short loc_18004B03D
0x18004b08e  test    esi, esi
0x18004b090  jz      short loc_18004B0AD
0x18004b092  call    cs:__imp_GetLastError
0x18004b098  test    eax, eax
0x18004b09a  jle     short loc_18004B0A4
0x18004b09c  movzx   eax, ax
0x18004b09f  or      eax, 80070000h
0x18004b0a4  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004b0ab  jmp     short loc_18004B0D2
0x18004b0ad  lea     rdx, [rsp+108h+Reply]; Reply
0x18004b0b2  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004b0b7  call    cs:__imp_RpcAsyncCompleteCall
0x18004b0bd  test    eax, eax
0x18004b0bf  jz      short loc_18004B0F1
0x18004b0c1  jle     short loc_18004B0CB
0x18004b0c3  movzx   eax, ax
0x18004b0c6  or      eax, 80070000h
0x18004b0cb  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004b0d2  mov     r8d, 3F8h; unsigned int
0x18004b0d8  mov     [rsp+108h+Reply], eax
0x18004b0dc  mov     [rsp+108h+bAlertable], eax
0x18004b0e0  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004b0e7  mov     ecx, 2; unsigned __int8
0x18004b0ec  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004b0f1  mov     rcx, qword ptr [rsp+108h+pAsync.u]; hObject
0x18004b0f9  test    rcx, rcx
0x18004b0fc  jz      short loc_18004B104
0x18004b0fe  call    cs:__imp_CloseHandle
0x18004b104  test    r15b, r15b
0x18004b107  jz      short loc_18004B141
0x18004b109  mov     [rsp+108h+Reply], 800705B4h
0x18004b111  lea     rdx, [rsp+108h+var_CC]
0x18004b116  call    ??$RPCCallTimedOut@AEAY0BO@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BO@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[30],ulong &>(char const (&)[30],ulong &)
0x18004b11b  mov     eax, [rsp+108h+Reply]
0x18004b11f  mov     [rsp+108h+bAlertable], eax
0x18004b123  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004b12a  mov     r8d, 3F8h; unsigned int
0x18004b130  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004b137  mov     ecx, 2; unsigned __int8
0x18004b13c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004b141  test    r14b, r14b
0x18004b144  jz      short loc_18004B171
0x18004b146  mov     eax, 800704C7h
0x18004b14b  mov     [rsp+108h+Reply], eax
0x18004b14f  mov     [rsp+108h+bAlertable], eax
0x18004b153  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004b15a  mov     r8d, 3F8h; unsigned int
0x18004b160  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004b167  mov     ecx, 2; unsigned __int8
0x18004b16c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004b171  cmp     [rsp+108h+Reply], 800706B5h
0x18004b179  jz      short loc_18004B185
0x18004b17b  cmp     [rsp+108h+Reply], 800706BAh
0x18004b183  jnz     short loc_18004B18A
0x18004b185  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004b18a  lea     rcx, [rsp+108h+var_C8]; this
0x18004b18f  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18004b194  mov     eax, [rsp+108h+Reply]
0x18004b198  mov     rcx, [rsp+108h+var_38]
0x18004b1a0  xor     rcx, rsp; StackCookie
0x18004b1a3  call    __security_check_cookie
0x18004b1a8  add     rsp, 0E8h
0x18004b1af  pop     r15
0x18004b1b1  pop     r14
0x18004b1b3  pop     r12
0x18004b1b5  pop     rsi
0x18004b1b6  retn
0x1800619f5  push    rbp
0x1800619f7  sub     rsp, 30h
0x1800619fb  mov     rbp, rdx
0x1800619fe  mov     rcx, [rcx]
0x180061a01  mov     ecx, [rcx]; unsigned int
0x180061a03  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x180061a08  nop
0x180061a09  add     rsp, 30h
0x180061a0d  pop     rbp
0x180061a0e  retn
```
