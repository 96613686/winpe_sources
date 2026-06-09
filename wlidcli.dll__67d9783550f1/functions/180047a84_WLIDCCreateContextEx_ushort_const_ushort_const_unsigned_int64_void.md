# WLIDCCreateContextEx(ushort const *,ushort const *,unsigned __int64,void * *)

- ea: `0x180047a84`
- end: `0x180047e18`
- name: `?WLIDCCreateContextEx@@YAJPEBG0_KPEAPEAX@Z`
- size: `916`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int64, void **)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000bf58`
- `0x18001f6a0`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180044fc4`
- `0x180046ce0`
- `0x180046e64`
- `0x180047a84`
- `0x18004cd04`
- `0x180050c84`
- `0x180050e40`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180047c6c`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180047cc1`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180047c6c`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180047cc1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180047b72`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180047b72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047b85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047cd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047b85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047cd2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047d41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047d41`
- `RPCRT4!RpcAsyncCancelCall` at `0x180047c96`
- `RPCRT4!RpcAsyncCancelCall` at `0x180047c96`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180047be4`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180047be4`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180047cfa`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180047cfa`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180047b2b`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180047b2b`

## string_xrefs

- `0x180047b97`: `RPC failed to create new event, hr = %#x`
- `0x180047d0e`: `RPC Async complete call failed, hr = %#x`
- `0x180047d59`: `WLIDCCreateContextEx`
- `0x180047dde`: `WLIDCCreateContextEx`

## pseudocode

```c
__int64 __fastcall WLIDCCreateContextEx(const unsigned __int16 *a1, const unsigned __int16 *a2, __int64 a3, void **a4)
{
  __int64 result; // rax
  DWORD v7; // esi
  char v8; // r15
  char v9; // r14
  int LastError; // eax
  const unsigned __int16 *v11; // r9
  unsigned int v12; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v14; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-F8h]
  int Reply; // [rsp+50h] [rbp-C8h] BYREF
  char v17; // [rsp+54h] [rbp-C4h]
  DWORD dwMilliseconds; // [rsp+58h] [rbp-C0h] BYREF
  DWORD v19; // [rsp+5Ch] [rbp-BCh] BYREF
  __int64 v20; // [rsp+60h] [rbp-B8h] BYREF
  HANDLE Handles[3]; // [rsp+68h] [rbp-B0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+80h] [rbp-98h] BYREF

  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  v20 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v20);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v7 = dwMilliseconds;
  v19 = dwMilliseconds;
  v8 = 0;
  v17 = 0;
  v9 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v11 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v12 = 574;
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
    v11 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall(
    (MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo,
    0xAu,
    0,
    &pAsync,
    v20,
    a1,
    L"{5d3e8ebb-54a3-442f-a42f-ffa310573928}",
    8421376,
    a4);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v11 = L"RPC call failed, hr = %#x";
    v12 = 576;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v12,
      v11,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
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
LABEL_29:
    v12 = 576;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v11 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v8 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],unsigned long &>(
      (__int64)"WLIDCCreateContextEx",
      (int *)&v19);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x240u,
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
      0x240u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v20);
  return TranslateRpcServiceError(Reply, "WLIDCCreateContextEx");
}

```

## disassembly

```asm
0x180047a84  mov     [rsp+arg_8], rsi
0x180047a89  mov     [rsp+arg_10], r12
0x180047a8e  push    r13
0x180047a90  push    r14
0x180047a92  push    r15
0x180047a94  sub     rsp, 100h
0x180047a9b  mov     rax, cs:__security_cookie
0x180047aa2  xor     rax, rsp
0x180047aa5  mov     [rsp+118h+var_28], rax
0x180047aad  mov     r13, r9
0x180047ab0  mov     r12, rcx
0x180047ab3  mov     [rsp+118h+dwMilliseconds], 0
0x180047abb  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x180047ac0  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180047ac5  mov     [rsp+118h+Reply], 0
0x180047acd  mov     [rsp+118h+var_B8], 0
0x180047ad6  lea     rcx, [rsp+118h+var_B8]; this
0x180047adb  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x180047ae0  mov     [rsp+118h+Reply], eax
0x180047ae4  test    eax, eax
0x180047ae6  js      loc_180047DEE
0x180047aec  xor     edx, edx; Val
0x180047aee  lea     r8d, [rdx+70h]; Size
0x180047af2  lea     rcx, [rsp+118h+pAsync]; void *
0x180047afa  call    memset_0
0x180047aff  mov     esi, [rsp+118h+dwMilliseconds]
0x180047b03  mov     [rsp+118h+dwMilliseconds], esi
0x180047b07  mov     [rsp+118h+var_BC], esi
0x180047b0b  xor     r15b, r15b
0x180047b0e  mov     [rsp+118h+var_C4], r15b
0x180047b13  xor     r14b, r14b
0x180047b16  xorps   xmm0, xmm0
0x180047b19  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x180047b1e  mov     edx, 70h ; 'p'; Size
0x180047b23  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180047b2b  call    cs:__imp_RpcAsyncInitializeHandle
0x180047b31  test    eax, eax
0x180047b33  jz      short loc_180047B51
0x180047b35  jle     short loc_180047B3F
0x180047b37  movzx   eax, ax
0x180047b3a  or      eax, 80070000h
0x180047b3f  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180047b46  mov     r8d, 23Eh
0x180047b4c  jmp     loc_180047D1B
0x180047b51  mov     [rsp+118h+pAsync.UserInfo], 0
0x180047b5d  mov     [rsp+118h+pAsync.NotificationType], 1
0x180047b68  xor     r9d, r9d; lpName
0x180047b6b  xor     r8d, r8d; bInitialState
0x180047b6e  xor     edx, edx; bManualReset
0x180047b70  xor     ecx, ecx; lpEventAttributes
0x180047b72  call    cs:__imp_CreateEventW
0x180047b78  mov     qword ptr [rsp+118h+pAsync.u], rax
0x180047b80  test    rax, rax
0x180047b83  jnz     short loc_180047BA0
0x180047b85  call    cs:__imp_GetLastError
0x180047b8b  test    eax, eax
0x180047b8d  jle     short loc_180047B97
0x180047b8f  movzx   eax, ax
0x180047b92  or      eax, 80070000h
0x180047b97  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180047b9e  jmp     short loc_180047B46
0x180047ba0  mov     [rsp+118h+Handles], rax
0x180047ba5  mov     [rsp+118h+var_D8], r13
0x180047baa  mov     [rsp+118h+var_E0], 808000h
0x180047bb3  lea     rax, a5d3e8ebb54a344; "{5d3e8ebb-54a3-442f-a42f-ffa310573928}"
0x180047bba  mov     [rsp+118h+var_E8], rax
0x180047bbf  mov     [rsp+118h+var_F0], r12
0x180047bc4  mov     rax, [rsp+118h+var_B8]
0x180047bc9  mov     qword ptr [rsp+118h+bAlertable], rax
0x180047bce  lea     r9, [rsp+118h+pAsync]
0x180047bd6  xor     r8d, r8d; pReturnValue
0x180047bd9  lea     edx, [r8+0Ah]; nProcNum
0x180047bdd  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180047be4  call    cs:__imp_Ndr64AsyncClientCall
0x180047bea  mov     eax, [rsp+118h+Reply]
0x180047bee  jmp     short loc_180047C3F
0x180047bf0  test    eax, eax
0x180047bf2  jle     short loc_180047BFC
0x180047bf4  movzx   eax, ax
0x180047bf7  or      eax, 80070000h
0x180047bfc  mov     [rsp+118h+Reply], eax
0x180047c00  mov     [rsp+118h+bAlertable], eax
0x180047c04  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180047c0b  mov     r8d, 240h; unsigned int
0x180047c11  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180047c18  mov     ecx, 2; unsigned __int8
0x180047c1d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180047c22  mov     eax, [rsp+118h+Reply]
0x180047c26  test    eax, eax
0x180047c28  js      short loc_180047C33
0x180047c2a  mov     eax, 8000FFFFh
0x180047c2f  mov     [rsp+118h+Reply], eax
0x180047c33  mov     esi, [rsp+118h+dwMilliseconds]
0x180047c37  mov     r15b, [rsp+118h+var_C4]
0x180047c3c  mov     r14b, r15b
0x180047c3f  test    eax, eax
0x180047c41  jns     short loc_180047C55
0x180047c43  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180047c4a  mov     r8d, 240h
0x180047c50  jmp     loc_180047D1F
0x180047c55  mov     [rsp+118h+bAlertable], 0; bAlertable
0x180047c5d  mov     r9d, esi; dwMilliseconds
0x180047c60  xor     r8d, r8d; bWaitAll
0x180047c63  lea     rdx, [rsp+118h+Handles]; lpHandles
0x180047c68  lea     ecx, [r8+1]; nCount
0x180047c6c  call    cs:__imp_WaitForMultipleObjectsEx
0x180047c72  mov     esi, eax
0x180047c74  mov     r12d, 102h
0x180047c7a  test    r14b, r14b
0x180047c7d  jnz     short loc_180047CCE
0x180047c7f  cmp     esi, r12d
0x180047c82  jz      short loc_180047C89
0x180047c84  cmp     esi, 1
0x180047c87  jnz     short loc_180047CCE
0x180047c89  mov     edx, 1; fAbort
0x180047c8e  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180047c96  call    cs:__imp_RpcAsyncCancelCall
0x180047c9c  cmp     esi, r12d
0x180047c9f  jnz     short loc_180047CA6
0x180047ca1  mov     r15b, 1
0x180047ca4  jmp     short loc_180047CA9
0x180047ca6  mov     r14b, 1
0x180047ca9  mov     [rsp+118h+bAlertable], 0; bAlertable
0x180047cb1  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180047cb5  xor     r8d, r8d; bWaitAll
0x180047cb8  lea     rdx, [rsp+118h+Handles]; lpHandles
0x180047cbd  lea     ecx, [r8+1]; nCount
0x180047cc1  call    cs:__imp_WaitForMultipleObjectsEx
0x180047cc7  mov     esi, eax
0x180047cc9  test    r15b, r15b
0x180047ccc  jz      short loc_180047C7A
0x180047cce  test    esi, esi
0x180047cd0  jz      short loc_180047CED
0x180047cd2  call    cs:__imp_GetLastError
0x180047cd8  test    eax, eax
0x180047cda  jle     short loc_180047CE4
0x180047cdc  movzx   eax, ax
0x180047cdf  or      eax, 80070000h
0x180047ce4  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180047ceb  jmp     short loc_180047D15
0x180047ced  lea     rdx, [rsp+118h+Reply]; Reply
0x180047cf2  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180047cfa  call    cs:__imp_RpcAsyncCompleteCall
0x180047d00  test    eax, eax
0x180047d02  jz      short loc_180047D34
0x180047d04  jle     short loc_180047D0E
0x180047d06  movzx   eax, ax
0x180047d09  or      eax, 80070000h
0x180047d0e  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180047d15  mov     r8d, 240h; unsigned int
0x180047d1b  mov     [rsp+118h+Reply], eax
0x180047d1f  mov     [rsp+118h+bAlertable], eax
0x180047d23  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180047d2a  mov     ecx, 2; unsigned __int8
0x180047d2f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180047d34  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x180047d3c  test    rcx, rcx
0x180047d3f  jz      short loc_180047D47
0x180047d41  call    cs:__imp_CloseHandle
0x180047d47  test    r15b, r15b
0x180047d4a  jz      short loc_180047D8B
0x180047d4c  mov     [rsp+118h+Reply], 800705B4h
0x180047d54  lea     rdx, [rsp+118h+var_BC]
0x180047d59  lea     rcx, aWlidccreatecon; "WLIDCCreateContextEx"
0x180047d60  call    ??$RPCCallTimedOut@AEAY0BF@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BF@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],ulong &>(char const (&)[21],ulong &)
0x180047d65  mov     eax, [rsp+118h+Reply]
0x180047d69  mov     [rsp+118h+bAlertable], eax
0x180047d6d  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180047d74  mov     r8d, 240h; unsigned int
0x180047d7a  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180047d81  mov     ecx, 2; unsigned __int8
0x180047d86  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180047d8b  test    r14b, r14b
0x180047d8e  jz      short loc_180047DBB
0x180047d90  mov     eax, 800704C7h
0x180047d95  mov     [rsp+118h+Reply], eax
0x180047d99  mov     [rsp+118h+bAlertable], eax
0x180047d9d  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180047da4  mov     r8d, 240h; unsigned int
0x180047daa  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180047db1  mov     ecx, 2; unsigned __int8
0x180047db6  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180047dbb  cmp     [rsp+118h+Reply], 800706B5h
0x180047dc3  jz      short loc_180047DCF
0x180047dc5  cmp     [rsp+118h+Reply], 800706BAh
0x180047dcd  jnz     short loc_180047DD4
0x180047dcf  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180047dd4  lea     rcx, [rsp+118h+var_B8]; this
0x180047dd9  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x180047dde  lea     rdx, aWlidccreatecon; "WLIDCCreateContextEx"
0x180047de5  mov     ecx, [rsp+118h+Reply]; int
0x180047de9  call    ?TranslateRpcServiceError@@YAJJPEBD@Z; TranslateRpcServiceError(long,char const *)
0x180047dee  mov     rcx, [rsp+118h+var_28]
0x180047df6  xor     rcx, rsp; StackCookie
0x180047df9  call    __security_check_cookie
0x180047dfe  lea     r11, [rsp+118h+var_18]
0x180047e06  mov     rsi, [r11+28h]
0x180047e0a  mov     r12, [r11+30h]
0x180047e0e  mov     rsp, r11
0x180047e11  pop     r15
0x180047e13  pop     r14
0x180047e15  pop     r13
0x180047e17  retn
0x1800619d4  push    rbp
0x1800619d6  sub     rsp, 50h
0x1800619da  mov     rbp, rdx
0x1800619dd  mov     rcx, [rcx]
0x1800619e0  mov     ecx, [rcx]; unsigned int
0x1800619e2  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x1800619e7  nop
0x1800619e8  add     rsp, 50h
0x1800619ec  pop     rbp
0x1800619ed  retn
```
