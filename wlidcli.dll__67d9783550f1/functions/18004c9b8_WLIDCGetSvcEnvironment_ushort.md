# WLIDCGetSvcEnvironment(ushort * *)

- ea: `0x18004c9b8`
- end: `0x18004ccfe`
- name: `?WLIDCGetSvcEnvironment@@YAJPEAPEAG@Z`
- size: `838`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002663c`
- `0x18003bc20`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x1800450dc`
- `0x180046ce0`
- `0x18004c9b8`
- `0x18004cd04`
- `0x180050c84`
- `0x180050e40`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004cb6f`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004cbc1`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004cb6f`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004cbc1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004ca92`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004ca92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004caa5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cbd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004caa5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cbd2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004cc3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004cc3e`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004cb96`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004cb96`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004cae7`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004cae7`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004cbf7`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004cbf7`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004ca4e`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004ca4e`

## string_xrefs

- `0x18004cab7`: `RPC failed to create new event, hr = %#x`
- `0x18004cc0b`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCGetSvcEnvironment(unsigned __int16 **a1, unsigned int a2)
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
  BOOL bAlertable[2]; // [rsp+20h] [rbp-E8h]
  int Reply; // [rsp+30h] [rbp-D8h] BYREF
  char v14; // [rsp+34h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+38h] [rbp-D0h] BYREF
  DWORD v16; // [rsp+3Ch] [rbp-CCh] BYREF
  __int64 v17; // [rsp+40h] [rbp-C8h] BYREF
  HANDLE Handles[3]; // [rsp+48h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+60h] [rbp-A8h] BYREF

  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  v17 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v17);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v4 = dwMilliseconds;
  v16 = dwMilliseconds;
  v5 = 0;
  v14 = 0;
  v6 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v9 = 1063;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x34u, 0, &pAsync, v17, a1);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v8 = L"RPC call failed, hr = %#x";
    v9 = 1065;
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
    v9 = 1065;
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
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v5 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[23],unsigned long &>(
      (__int64)"WLIDCGetSvcEnvironment",
      (int *)&v16);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x429u,
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
      0x429u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v17);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x18004c9b8  push    rsi
0x18004c9ba  push    r12
0x18004c9bc  push    r14
0x18004c9be  push    r15
0x18004c9c0  sub     rsp, 0E8h
0x18004c9c7  mov     rax, cs:__security_cookie
0x18004c9ce  xor     rax, rsp
0x18004c9d1  mov     [rsp+108h+var_38], rax
0x18004c9d9  mov     r12, rcx
0x18004c9dc  mov     [rsp+108h+dwMilliseconds], 0
0x18004c9e4  lea     r8, [rsp+108h+dwMilliseconds]; unsigned int *
0x18004c9e9  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004c9ee  mov     [rsp+108h+Reply], 0
0x18004c9f6  mov     [rsp+108h+var_C8], 0
0x18004c9ff  lea     rcx, [rsp+108h+var_C8]; this
0x18004ca04  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18004ca09  mov     [rsp+108h+Reply], eax
0x18004ca0d  test    eax, eax
0x18004ca0f  js      loc_18004CCDF
0x18004ca15  xor     edx, edx; Val
0x18004ca17  lea     r8d, [rdx+70h]; Size
0x18004ca1b  lea     rcx, [rsp+108h+pAsync]; void *
0x18004ca20  call    memset_0
0x18004ca25  mov     esi, [rsp+108h+dwMilliseconds]
0x18004ca29  mov     [rsp+108h+dwMilliseconds], esi
0x18004ca2d  mov     [rsp+108h+var_CC], esi
0x18004ca31  xor     r15b, r15b
0x18004ca34  mov     [rsp+108h+var_D4], r15b
0x18004ca39  xor     r14b, r14b
0x18004ca3c  xorps   xmm0, xmm0
0x18004ca3f  movups  xmmword ptr [rsp+108h+Handles], xmm0
0x18004ca44  mov     edx, 70h ; 'p'; Size
0x18004ca49  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004ca4e  call    cs:__imp_RpcAsyncInitializeHandle
0x18004ca54  test    eax, eax
0x18004ca56  jz      short loc_18004CA74
0x18004ca58  jle     short loc_18004CA62
0x18004ca5a  movzx   eax, ax
0x18004ca5d  or      eax, 80070000h
0x18004ca62  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004ca69  mov     r8d, 427h
0x18004ca6f  jmp     loc_18004CC18
0x18004ca74  mov     [rsp+108h+pAsync.UserInfo], 0
0x18004ca7d  mov     [rsp+108h+pAsync.NotificationType], 1
0x18004ca88  xor     r9d, r9d; lpName
0x18004ca8b  xor     r8d, r8d; bInitialState
0x18004ca8e  xor     edx, edx; bManualReset
0x18004ca90  xor     ecx, ecx; lpEventAttributes
0x18004ca92  call    cs:__imp_CreateEventW
0x18004ca98  mov     qword ptr [rsp+108h+pAsync.u], rax
0x18004caa0  test    rax, rax
0x18004caa3  jnz     short loc_18004CAC0
0x18004caa5  call    cs:__imp_GetLastError
0x18004caab  test    eax, eax
0x18004caad  jle     short loc_18004CAB7
0x18004caaf  movzx   eax, ax
0x18004cab2  or      eax, 80070000h
0x18004cab7  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004cabe  jmp     short loc_18004CA69
0x18004cac0  mov     [rsp+108h+Handles], rax
0x18004cac5  mov     [rsp+108h+var_E0], r12
0x18004caca  mov     rax, [rsp+108h+var_C8]
0x18004cacf  mov     qword ptr [rsp+108h+bAlertable], rax
0x18004cad4  lea     r9, [rsp+108h+pAsync]
0x18004cad9  xor     r8d, r8d; pReturnValue
0x18004cadc  lea     edx, [r8+34h]; nProcNum
0x18004cae0  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004cae7  call    cs:__imp_Ndr64AsyncClientCall
0x18004caed  mov     eax, [rsp+108h+Reply]
0x18004caf1  jmp     short loc_18004CB42
0x18004caf3  test    eax, eax
0x18004caf5  jle     short loc_18004CAFF
0x18004caf7  movzx   eax, ax
0x18004cafa  or      eax, 80070000h
0x18004caff  mov     [rsp+108h+Reply], eax
0x18004cb03  mov     [rsp+108h+bAlertable], eax
0x18004cb07  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004cb0e  mov     r8d, 429h; unsigned int
0x18004cb14  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004cb1b  mov     ecx, 2; unsigned __int8
0x18004cb20  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004cb25  mov     eax, [rsp+108h+Reply]
0x18004cb29  test    eax, eax
0x18004cb2b  js      short loc_18004CB36
0x18004cb2d  mov     eax, 8000FFFFh
0x18004cb32  mov     [rsp+108h+Reply], eax
0x18004cb36  mov     esi, [rsp+108h+dwMilliseconds]
0x18004cb3a  mov     r15b, [rsp+108h+var_D4]
0x18004cb3f  mov     r14b, r15b
0x18004cb42  test    eax, eax
0x18004cb44  jns     short loc_18004CB58
0x18004cb46  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004cb4d  mov     r8d, 429h
0x18004cb53  jmp     loc_18004CC1C
0x18004cb58  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18004cb60  mov     r9d, esi; dwMilliseconds
0x18004cb63  xor     r8d, r8d; bWaitAll
0x18004cb66  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18004cb6b  lea     ecx, [r8+1]; nCount
0x18004cb6f  call    cs:__imp_WaitForMultipleObjectsEx
0x18004cb75  mov     esi, eax
0x18004cb77  mov     r12d, 102h
0x18004cb7d  test    r14b, r14b
0x18004cb80  jnz     short loc_18004CBCE
0x18004cb82  cmp     esi, r12d
0x18004cb85  jz      short loc_18004CB8C
0x18004cb87  cmp     esi, 1
0x18004cb8a  jnz     short loc_18004CBCE
0x18004cb8c  mov     edx, 1; fAbort
0x18004cb91  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004cb96  call    cs:__imp_RpcAsyncCancelCall
0x18004cb9c  cmp     esi, r12d
0x18004cb9f  jnz     short loc_18004CBA6
0x18004cba1  mov     r15b, 1
0x18004cba4  jmp     short loc_18004CBA9
0x18004cba6  mov     r14b, 1
0x18004cba9  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18004cbb1  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004cbb5  xor     r8d, r8d; bWaitAll
0x18004cbb8  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18004cbbd  lea     ecx, [r8+1]; nCount
0x18004cbc1  call    cs:__imp_WaitForMultipleObjectsEx
0x18004cbc7  mov     esi, eax
0x18004cbc9  test    r15b, r15b
0x18004cbcc  jz      short loc_18004CB7D
0x18004cbce  test    esi, esi
0x18004cbd0  jz      short loc_18004CBED
0x18004cbd2  call    cs:__imp_GetLastError
0x18004cbd8  test    eax, eax
0x18004cbda  jle     short loc_18004CBE4
0x18004cbdc  movzx   eax, ax
0x18004cbdf  or      eax, 80070000h
0x18004cbe4  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004cbeb  jmp     short loc_18004CC12
0x18004cbed  lea     rdx, [rsp+108h+Reply]; Reply
0x18004cbf2  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004cbf7  call    cs:__imp_RpcAsyncCompleteCall
0x18004cbfd  test    eax, eax
0x18004cbff  jz      short loc_18004CC31
0x18004cc01  jle     short loc_18004CC0B
0x18004cc03  movzx   eax, ax
0x18004cc06  or      eax, 80070000h
0x18004cc0b  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004cc12  mov     r8d, 429h; unsigned int
0x18004cc18  mov     [rsp+108h+Reply], eax
0x18004cc1c  mov     [rsp+108h+bAlertable], eax
0x18004cc20  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004cc27  mov     ecx, 2; unsigned __int8
0x18004cc2c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004cc31  mov     rcx, qword ptr [rsp+108h+pAsync.u]; hObject
0x18004cc39  test    rcx, rcx
0x18004cc3c  jz      short loc_18004CC44
0x18004cc3e  call    cs:__imp_CloseHandle
0x18004cc44  test    r15b, r15b
0x18004cc47  jz      short loc_18004CC88
0x18004cc49  mov     [rsp+108h+Reply], 800705B4h
0x18004cc51  lea     rdx, [rsp+108h+var_CC]
0x18004cc56  lea     rcx, aWlidcgetsvcenv; "WLIDCGetSvcEnvironment"
0x18004cc5d  call    ??$RPCCallTimedOut@AEAY0BH@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BH@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[23],ulong &>(char const (&)[23],ulong &)
0x18004cc62  mov     eax, [rsp+108h+Reply]
0x18004cc66  mov     [rsp+108h+bAlertable], eax
0x18004cc6a  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004cc71  mov     r8d, 429h; unsigned int
0x18004cc77  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004cc7e  mov     ecx, 2; unsigned __int8
0x18004cc83  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004cc88  test    r14b, r14b
0x18004cc8b  jz      short loc_18004CCB8
0x18004cc8d  mov     eax, 800704C7h
0x18004cc92  mov     [rsp+108h+Reply], eax
0x18004cc96  mov     [rsp+108h+bAlertable], eax
0x18004cc9a  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004cca1  mov     r8d, 429h; unsigned int
0x18004cca7  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004ccae  mov     ecx, 2; unsigned __int8
0x18004ccb3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004ccb8  cmp     [rsp+108h+Reply], 800706B5h
0x18004ccc0  jz      short loc_18004CCCC
0x18004ccc2  cmp     [rsp+108h+Reply], 800706BAh
0x18004ccca  jnz     short loc_18004CCD1
0x18004cccc  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004ccd1  lea     rcx, [rsp+108h+var_C8]; this
0x18004ccd6  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18004ccdb  mov     eax, [rsp+108h+Reply]
0x18004ccdf  mov     rcx, [rsp+108h+var_38]
0x18004cce7  xor     rcx, rsp; StackCookie
0x18004ccea  call    __security_check_cookie
0x18004ccef  add     rsp, 0E8h
0x18004ccf6  pop     r15
0x18004ccf8  pop     r14
0x18004ccfa  pop     r12
0x18004ccfc  pop     rsi
0x18004ccfd  retn
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
