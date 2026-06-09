# WLIDCGetDeviceIdEx(ushort const *,ulong,unsigned __int64,ushort * *,ushort * *,ulong *,uchar * *)

- ea: `0x18004aa84`
- end: `0x18004ae6f`
- name: `?WLIDCGetDeviceIdEx@@YAJPEBGK_KPEAPEAG2PEAKPEAPEAE@Z`
- size: `1003`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, unsigned __int64, unsigned __int16 **, unsigned __int16 **, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002dc10`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180044eac`
- `0x180046ce0`
- `0x18004aa84`
- `0x18004cd04`
- `0x180050c84`
- `0x180050e40`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004acd5`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004ad2d`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004acd5`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004ad2d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004abac`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004abac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004abbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ad3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004abbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ad3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004adad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004adad`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004acff`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004acff`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004ac4a`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004ac4a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004ad66`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004ad66`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004ab65`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004ab65`

## string_xrefs

- `0x18004abd1`: `RPC failed to create new event, hr = %#x`
- `0x18004ad7a`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCGetDeviceIdEx(
        const unsigned __int16 *a1,
        unsigned int a2,
        __int64 a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5,
        unsigned int *a6,
        unsigned __int8 **a7)
{
  __int64 result; // rax
  DWORD v10; // esi
  char v11; // r15
  char v12; // r14
  int LastError; // eax
  const unsigned __int16 *v14; // r9
  unsigned int v15; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v17; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-138h]
  int Reply; // [rsp+60h] [rbp-F8h] BYREF
  char v20; // [rsp+64h] [rbp-F4h]
  DWORD dwMilliseconds; // [rsp+68h] [rbp-F0h] BYREF
  DWORD v22; // [rsp+6Ch] [rbp-ECh] BYREF
  __int64 v23; // [rsp+70h] [rbp-E8h] BYREF
  unsigned __int8 **v24; // [rsp+78h] [rbp-E0h]
  unsigned int *v25; // [rsp+80h] [rbp-D8h]
  unsigned __int16 **v26; // [rsp+88h] [rbp-D0h]
  unsigned __int16 **v27; // [rsp+90h] [rbp-C8h]
  __int64 v28; // [rsp+98h] [rbp-C0h]
  HANDLE Handles[2]; // [rsp+A0h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+B0h] [rbp-A8h] BYREF

  v27 = a4;
  v28 = a3;
  v26 = a5;
  v25 = a6;
  v24 = a7;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  v23 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v23);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v10 = dwMilliseconds;
  v22 = dwMilliseconds;
  v11 = 0;
  v20 = 0;
  v12 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v14 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v15 = 1255;
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
    v14 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall(
    (MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo,
    0x20u,
    0,
    &pAsync,
    v23,
    a1,
    a2,
    v28,
    v27,
    v26,
    v25,
    v24);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v14 = L"RPC call failed, hr = %#x";
    v15 = 1257;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v15,
      v14,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
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
LABEL_29:
    v15 = 1257;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v14 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v11 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[19],unsigned long &>(
      (__int64)"WLIDCGetDeviceIdEx",
      (int *)&v22);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x4E9u,
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
      0x4E9u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v23);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x18004aa84  push    rsi
0x18004aa86  push    r12
0x18004aa88  push    r13
0x18004aa8a  push    r14
0x18004aa8c  push    r15
0x18004aa8e  sub     rsp, 130h
0x18004aa95  mov     rax, cs:__security_cookie
0x18004aa9c  xor     rax, rsp
0x18004aa9f  mov     [rsp+158h+var_38], rax
0x18004aaa7  mov     [rsp+158h+var_C8], r9
0x18004aaaf  mov     [rsp+158h+var_C0], r8
0x18004aab7  mov     r13d, edx
0x18004aaba  mov     r12, rcx
0x18004aabd  mov     rax, [rsp+158h+arg_20]
0x18004aac5  mov     [rsp+158h+var_D0], rax
0x18004aacd  mov     rax, [rsp+158h+arg_28]
0x18004aad5  mov     [rsp+158h+var_D8], rax
0x18004aadd  mov     rax, [rsp+158h+arg_30]
0x18004aae5  mov     [rsp+158h+var_E0], rax
0x18004aaea  mov     [rsp+158h+dwMilliseconds], 0
0x18004aaf2  lea     r8, [rsp+158h+dwMilliseconds]; unsigned int *
0x18004aaf7  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004aafc  mov     [rsp+158h+Reply], 0
0x18004ab04  mov     [rsp+158h+var_E8], 0
0x18004ab0d  lea     rcx, [rsp+158h+var_E8]; this
0x18004ab12  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18004ab17  mov     [rsp+158h+Reply], eax
0x18004ab1b  test    eax, eax
0x18004ab1d  js      loc_18004AE4E
0x18004ab23  xor     edx, edx; Val
0x18004ab25  lea     r8d, [rdx+70h]; Size
0x18004ab29  lea     rcx, [rsp+158h+pAsync]; void *
0x18004ab31  call    memset_0
0x18004ab36  mov     esi, [rsp+158h+dwMilliseconds]
0x18004ab3a  mov     [rsp+158h+dwMilliseconds], esi
0x18004ab3e  mov     [rsp+158h+var_EC], esi
0x18004ab42  xor     r15b, r15b
0x18004ab45  mov     [rsp+158h+var_F4], r15b
0x18004ab4a  xor     r14b, r14b
0x18004ab4d  xorps   xmm0, xmm0
0x18004ab50  movups  xmmword ptr [rsp+158h+Handles], xmm0
0x18004ab58  mov     edx, 70h ; 'p'; Size
0x18004ab5d  lea     rcx, [rsp+158h+pAsync]; pAsync
0x18004ab65  call    cs:__imp_RpcAsyncInitializeHandle
0x18004ab6b  test    eax, eax
0x18004ab6d  jz      short loc_18004AB8B
0x18004ab6f  jle     short loc_18004AB79
0x18004ab71  movzx   eax, ax
0x18004ab74  or      eax, 80070000h
0x18004ab79  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004ab80  mov     r8d, 4E7h
0x18004ab86  jmp     loc_18004AD87
0x18004ab8b  mov     [rsp+158h+pAsync.UserInfo], 0
0x18004ab97  mov     [rsp+158h+pAsync.NotificationType], 1
0x18004aba2  xor     r9d, r9d; lpName
0x18004aba5  xor     r8d, r8d; bInitialState
0x18004aba8  xor     edx, edx; bManualReset
0x18004abaa  xor     ecx, ecx; lpEventAttributes
0x18004abac  call    cs:__imp_CreateEventW
0x18004abb2  mov     qword ptr [rsp+158h+pAsync.u], rax
0x18004abba  test    rax, rax
0x18004abbd  jnz     short loc_18004ABDA
0x18004abbf  call    cs:__imp_GetLastError
0x18004abc5  test    eax, eax
0x18004abc7  jle     short loc_18004ABD1
0x18004abc9  movzx   eax, ax
0x18004abcc  or      eax, 80070000h
0x18004abd1  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004abd8  jmp     short loc_18004AB80
0x18004abda  mov     [rsp+158h+Handles], rax
0x18004abe2  mov     rax, [rsp+158h+var_E0]
0x18004abe7  mov     [rsp+158h+var_100], rax
0x18004abec  mov     rax, [rsp+158h+var_D8]
0x18004abf4  mov     [rsp+158h+var_108], rax
0x18004abf9  mov     rax, [rsp+158h+var_D0]
0x18004ac01  mov     [rsp+158h+var_110], rax
0x18004ac06  mov     rax, [rsp+158h+var_C8]
0x18004ac0e  mov     [rsp+158h+var_118], rax
0x18004ac13  mov     rax, [rsp+158h+var_C0]
0x18004ac1b  mov     [rsp+158h+var_120], rax
0x18004ac20  mov     [rsp+158h+var_128], r13d
0x18004ac25  mov     [rsp+158h+var_130], r12
0x18004ac2a  mov     rax, [rsp+158h+var_E8]
0x18004ac2f  mov     qword ptr [rsp+158h+bAlertable], rax
0x18004ac34  lea     r9, [rsp+158h+pAsync]
0x18004ac3c  xor     r8d, r8d; pReturnValue
0x18004ac3f  lea     edx, [r8+20h]; nProcNum
0x18004ac43  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004ac4a  call    cs:__imp_Ndr64AsyncClientCall
0x18004ac50  mov     eax, [rsp+158h+Reply]
0x18004ac54  jmp     short loc_18004ACA5
0x18004ac56  test    eax, eax
0x18004ac58  jle     short loc_18004AC62
0x18004ac5a  movzx   eax, ax
0x18004ac5d  or      eax, 80070000h
0x18004ac62  mov     [rsp+158h+Reply], eax
0x18004ac66  mov     [rsp+158h+bAlertable], eax
0x18004ac6a  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004ac71  mov     r8d, 4E9h; unsigned int
0x18004ac77  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004ac7e  mov     ecx, 2; unsigned __int8
0x18004ac83  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004ac88  mov     eax, [rsp+158h+Reply]
0x18004ac8c  test    eax, eax
0x18004ac8e  js      short loc_18004AC99
0x18004ac90  mov     eax, 8000FFFFh
0x18004ac95  mov     [rsp+158h+Reply], eax
0x18004ac99  mov     esi, [rsp+158h+dwMilliseconds]
0x18004ac9d  mov     r15b, [rsp+158h+var_F4]
0x18004aca2  mov     r14b, r15b
0x18004aca5  test    eax, eax
0x18004aca7  jns     short loc_18004ACBB
0x18004aca9  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004acb0  mov     r8d, 4E9h
0x18004acb6  jmp     loc_18004AD8B
0x18004acbb  mov     [rsp+158h+bAlertable], 0; bAlertable
0x18004acc3  mov     r9d, esi; dwMilliseconds
0x18004acc6  xor     r8d, r8d; bWaitAll
0x18004acc9  lea     rdx, [rsp+158h+Handles]; lpHandles
0x18004acd1  lea     ecx, [r8+1]; nCount
0x18004acd5  call    cs:__imp_WaitForMultipleObjectsEx
0x18004acdb  mov     esi, eax
0x18004acdd  mov     r12d, 102h
0x18004ace3  test    r14b, r14b
0x18004ace6  jnz     short loc_18004AD3A
0x18004ace8  cmp     esi, r12d
0x18004aceb  jz      short loc_18004ACF2
0x18004aced  cmp     esi, 1
0x18004acf0  jnz     short loc_18004AD3A
0x18004acf2  mov     edx, 1; fAbort
0x18004acf7  lea     rcx, [rsp+158h+pAsync]; pAsync
0x18004acff  call    cs:__imp_RpcAsyncCancelCall
0x18004ad05  cmp     esi, r12d
0x18004ad08  jnz     short loc_18004AD0F
0x18004ad0a  mov     r15b, 1
0x18004ad0d  jmp     short loc_18004AD12
0x18004ad0f  mov     r14b, 1
0x18004ad12  mov     [rsp+158h+bAlertable], 0; bAlertable
0x18004ad1a  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004ad1e  xor     r8d, r8d; bWaitAll
0x18004ad21  lea     rdx, [rsp+158h+Handles]; lpHandles
0x18004ad29  lea     ecx, [r8+1]; nCount
0x18004ad2d  call    cs:__imp_WaitForMultipleObjectsEx
0x18004ad33  mov     esi, eax
0x18004ad35  test    r15b, r15b
0x18004ad38  jz      short loc_18004ACE3
0x18004ad3a  test    esi, esi
0x18004ad3c  jz      short loc_18004AD59
0x18004ad3e  call    cs:__imp_GetLastError
0x18004ad44  test    eax, eax
0x18004ad46  jle     short loc_18004AD50
0x18004ad48  movzx   eax, ax
0x18004ad4b  or      eax, 80070000h
0x18004ad50  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004ad57  jmp     short loc_18004AD81
0x18004ad59  lea     rdx, [rsp+158h+Reply]; Reply
0x18004ad5e  lea     rcx, [rsp+158h+pAsync]; pAsync
0x18004ad66  call    cs:__imp_RpcAsyncCompleteCall
0x18004ad6c  test    eax, eax
0x18004ad6e  jz      short loc_18004ADA0
0x18004ad70  jle     short loc_18004AD7A
0x18004ad72  movzx   eax, ax
0x18004ad75  or      eax, 80070000h
0x18004ad7a  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004ad81  mov     r8d, 4E9h; unsigned int
0x18004ad87  mov     [rsp+158h+Reply], eax
0x18004ad8b  mov     [rsp+158h+bAlertable], eax
0x18004ad8f  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004ad96  mov     ecx, 2; unsigned __int8
0x18004ad9b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004ada0  mov     rcx, qword ptr [rsp+158h+pAsync.u]; hObject
0x18004ada8  test    rcx, rcx
0x18004adab  jz      short loc_18004ADB3
0x18004adad  call    cs:__imp_CloseHandle
0x18004adb3  test    r15b, r15b
0x18004adb6  jz      short loc_18004ADF7
0x18004adb8  mov     [rsp+158h+Reply], 800705B4h
0x18004adc0  lea     rdx, [rsp+158h+var_EC]
0x18004adc5  lea     rcx, aWlidcgetdevice; "WLIDCGetDeviceIdEx"
0x18004adcc  call    ??$RPCCallTimedOut@AEAY0BD@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BD@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[19],ulong &>(char const (&)[19],ulong &)
0x18004add1  mov     eax, [rsp+158h+Reply]
0x18004add5  mov     [rsp+158h+bAlertable], eax
0x18004add9  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004ade0  mov     r8d, 4E9h; unsigned int
0x18004ade6  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004aded  mov     ecx, 2; unsigned __int8
0x18004adf2  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004adf7  test    r14b, r14b
0x18004adfa  jz      short loc_18004AE27
0x18004adfc  mov     eax, 800704C7h
0x18004ae01  mov     [rsp+158h+Reply], eax
0x18004ae05  mov     [rsp+158h+bAlertable], eax
0x18004ae09  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004ae10  mov     r8d, 4E9h; unsigned int
0x18004ae16  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004ae1d  mov     ecx, 2; unsigned __int8
0x18004ae22  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004ae27  cmp     [rsp+158h+Reply], 800706B5h
0x18004ae2f  jz      short loc_18004AE3B
0x18004ae31  cmp     [rsp+158h+Reply], 800706BAh
0x18004ae39  jnz     short loc_18004AE40
0x18004ae3b  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004ae40  lea     rcx, [rsp+158h+var_E8]; this
0x18004ae45  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18004ae4a  mov     eax, [rsp+158h+Reply]
0x18004ae4e  mov     rcx, [rsp+158h+var_38]
0x18004ae56  xor     rcx, rsp; StackCookie
0x18004ae59  call    __security_check_cookie
0x18004ae5e  add     rsp, 130h
0x18004ae65  pop     r15
0x18004ae67  pop     r14
0x18004ae69  pop     r13
0x18004ae6b  pop     r12
0x18004ae6d  pop     rsi
0x18004ae6e  retn
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
