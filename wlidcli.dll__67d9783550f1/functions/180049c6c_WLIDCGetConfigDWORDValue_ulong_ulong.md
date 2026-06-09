# WLIDCGetConfigDWORDValue(ulong,ulong *)

- ea: `0x180049c6c`
- end: `0x180049fd0`
- name: `?WLIDCGetConfigDWORDValue@@YAJKPEAK@Z`
- size: `868`
- prototype: `__int64 __fastcall(unsigned int, unsigned int *)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180011178`
- `0x180016c74`
- `0x18002d490`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180045168`
- `0x180046ce0`
- `0x180049c6c`
- `0x18004cd04`
- `0x180050c84`
- `0x180050e40`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180049e36`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180049e88`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180049e36`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180049e88`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180049d54`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180049d54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049d67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049e99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049d67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049e99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049f05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049f05`
- `RPCRT4!RpcAsyncCancelCall` at `0x180049e5d`
- `RPCRT4!RpcAsyncCancelCall` at `0x180049e5d`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180049dae`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180049dae`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180049ebe`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180049ebe`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180049d0d`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180049d0d`

## string_xrefs

- `0x180049d79`: `RPC failed to create new event, hr = %#x`
- `0x180049ed2`: `RPC Async complete call failed, hr = %#x`
- `0x180049f1d`: `WLIDCGetConfigDWORDValue`

## pseudocode

```c
__int64 __fastcall WLIDCGetConfigDWORDValue(unsigned int a1, unsigned int *a2)
{
  __int64 result; // rax
  DWORD v5; // esi
  char v6; // r15
  char v7; // r14
  int LastError; // eax
  const unsigned __int16 *v9; // r9
  unsigned int v10; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v12; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-E8h]
  int Reply; // [rsp+40h] [rbp-C8h] BYREF
  char v15; // [rsp+44h] [rbp-C4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-C0h] BYREF
  DWORD v17; // [rsp+4Ch] [rbp-BCh] BYREF
  __int64 v18; // [rsp+50h] [rbp-B8h] BYREF
  HANDLE Handles[3]; // [rsp+58h] [rbp-B0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-98h] BYREF

  dwMilliseconds = 0;
  WLIDCGetTimeOutValue(a1, (unsigned int)a2, &dwMilliseconds);
  v18 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v18);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v5 = dwMilliseconds;
  v17 = dwMilliseconds;
  v6 = 0;
  v15 = 0;
  v7 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v10 = 1091;
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
    v9 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x36u, 0, &pAsync, v18, a1, a2);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v9 = L"RPC call failed, hr = %#x";
    v10 = 1093;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v10,
      v9,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
  v12 = WaitForMultipleObjectsEx(1u, Handles, 0, v5, 0);
  do
  {
    if ( v7 || v12 != 258 && v12 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v12 == 258 )
      v6 = 1;
    else
      v7 = 1;
    v12 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v6 );
  if ( v12 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = L"Encountered error while waiting on RPC call, hr = %#x";
LABEL_29:
    v10 = 1093;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v6 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[25],unsigned long &>(
      (__int64)"WLIDCGetConfigDWORDValue",
      (int *)&v17);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x445u,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v7 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x445u,
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
0x180049c6c  mov     [rsp+arg_10], rsi
0x180049c71  mov     [rsp+arg_18], r12
0x180049c76  push    r13
0x180049c78  push    r14
0x180049c7a  push    r15
0x180049c7c  sub     rsp, 0F0h
0x180049c83  mov     rax, cs:__security_cookie
0x180049c8a  xor     rax, rsp
0x180049c8d  mov     [rsp+108h+var_28], rax
0x180049c95  mov     r13, rdx
0x180049c98  mov     r12d, ecx
0x180049c9b  mov     [rsp+108h+dwMilliseconds], 0
0x180049ca3  lea     r8, [rsp+108h+dwMilliseconds]; unsigned int *
0x180049ca8  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180049cad  mov     [rsp+108h+Reply], 0
0x180049cb5  mov     [rsp+108h+var_B8], 0
0x180049cbe  lea     rcx, [rsp+108h+var_B8]; this
0x180049cc3  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x180049cc8  mov     [rsp+108h+Reply], eax
0x180049ccc  test    eax, eax
0x180049cce  js      loc_180049FA6
0x180049cd4  xor     edx, edx; Val
0x180049cd6  lea     r8d, [rdx+70h]; Size
0x180049cda  lea     rcx, [rsp+108h+pAsync]; void *
0x180049cdf  call    memset_0
0x180049ce4  mov     esi, [rsp+108h+dwMilliseconds]
0x180049ce8  mov     [rsp+108h+dwMilliseconds], esi
0x180049cec  mov     [rsp+108h+var_BC], esi
0x180049cf0  xor     r15b, r15b
0x180049cf3  mov     [rsp+108h+var_C4], r15b
0x180049cf8  xor     r14b, r14b
0x180049cfb  xorps   xmm0, xmm0
0x180049cfe  movups  xmmword ptr [rsp+108h+Handles], xmm0
0x180049d03  mov     edx, 70h ; 'p'; Size
0x180049d08  lea     rcx, [rsp+108h+pAsync]; pAsync
0x180049d0d  call    cs:__imp_RpcAsyncInitializeHandle
0x180049d13  test    eax, eax
0x180049d15  jz      short loc_180049D33
0x180049d17  jle     short loc_180049D21
0x180049d19  movzx   eax, ax
0x180049d1c  or      eax, 80070000h
0x180049d21  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180049d28  mov     r8d, 443h
0x180049d2e  jmp     loc_180049EDF
0x180049d33  mov     [rsp+108h+pAsync.UserInfo], 0
0x180049d3f  mov     [rsp+108h+pAsync.NotificationType], 1
0x180049d4a  xor     r9d, r9d; lpName
0x180049d4d  xor     r8d, r8d; bInitialState
0x180049d50  xor     edx, edx; bManualReset
0x180049d52  xor     ecx, ecx; lpEventAttributes
0x180049d54  call    cs:__imp_CreateEventW
0x180049d5a  mov     qword ptr [rsp+108h+pAsync.u], rax
0x180049d62  test    rax, rax
0x180049d65  jnz     short loc_180049D82
0x180049d67  call    cs:__imp_GetLastError
0x180049d6d  test    eax, eax
0x180049d6f  jle     short loc_180049D79
0x180049d71  movzx   eax, ax
0x180049d74  or      eax, 80070000h
0x180049d79  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180049d80  jmp     short loc_180049D28
0x180049d82  mov     [rsp+108h+Handles], rax
0x180049d87  mov     [rsp+108h+var_D8], r13
0x180049d8c  mov     [rsp+108h+var_E0], r12d
0x180049d91  mov     rax, [rsp+108h+var_B8]
0x180049d96  mov     qword ptr [rsp+108h+bAlertable], rax
0x180049d9b  lea     r9, [rsp+108h+pAsync]
0x180049da0  xor     r8d, r8d; pReturnValue
0x180049da3  lea     edx, [r8+36h]; nProcNum
0x180049da7  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180049dae  call    cs:__imp_Ndr64AsyncClientCall
0x180049db4  mov     eax, [rsp+108h+Reply]
0x180049db8  jmp     short loc_180049E09
0x180049dba  test    eax, eax
0x180049dbc  jle     short loc_180049DC6
0x180049dbe  movzx   eax, ax
0x180049dc1  or      eax, 80070000h
0x180049dc6  mov     [rsp+108h+Reply], eax
0x180049dca  mov     [rsp+108h+bAlertable], eax
0x180049dce  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180049dd5  mov     r8d, 445h; unsigned int
0x180049ddb  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180049de2  mov     ecx, 2; unsigned __int8
0x180049de7  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180049dec  mov     eax, [rsp+108h+Reply]
0x180049df0  test    eax, eax
0x180049df2  js      short loc_180049DFD
0x180049df4  mov     eax, 8000FFFFh
0x180049df9  mov     [rsp+108h+Reply], eax
0x180049dfd  mov     esi, [rsp+108h+dwMilliseconds]
0x180049e01  mov     r15b, [rsp+108h+var_C4]
0x180049e06  mov     r14b, r15b
0x180049e09  test    eax, eax
0x180049e0b  jns     short loc_180049E1F
0x180049e0d  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180049e14  mov     r8d, 445h
0x180049e1a  jmp     loc_180049EE3
0x180049e1f  mov     [rsp+108h+bAlertable], 0; bAlertable
0x180049e27  mov     r9d, esi; dwMilliseconds
0x180049e2a  xor     r8d, r8d; bWaitAll
0x180049e2d  lea     rdx, [rsp+108h+Handles]; lpHandles
0x180049e32  lea     ecx, [r8+1]; nCount
0x180049e36  call    cs:__imp_WaitForMultipleObjectsEx
0x180049e3c  mov     esi, eax
0x180049e3e  mov     r12d, 102h
0x180049e44  test    r14b, r14b
0x180049e47  jnz     short loc_180049E95
0x180049e49  cmp     esi, r12d
0x180049e4c  jz      short loc_180049E53
0x180049e4e  cmp     esi, 1
0x180049e51  jnz     short loc_180049E95
0x180049e53  mov     edx, 1; fAbort
0x180049e58  lea     rcx, [rsp+108h+pAsync]; pAsync
0x180049e5d  call    cs:__imp_RpcAsyncCancelCall
0x180049e63  cmp     esi, r12d
0x180049e66  jnz     short loc_180049E6D
0x180049e68  mov     r15b, 1
0x180049e6b  jmp     short loc_180049E70
0x180049e6d  mov     r14b, 1
0x180049e70  mov     [rsp+108h+bAlertable], 0; bAlertable
0x180049e78  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180049e7c  xor     r8d, r8d; bWaitAll
0x180049e7f  lea     rdx, [rsp+108h+Handles]; lpHandles
0x180049e84  lea     ecx, [r8+1]; nCount
0x180049e88  call    cs:__imp_WaitForMultipleObjectsEx
0x180049e8e  mov     esi, eax
0x180049e90  test    r15b, r15b
0x180049e93  jz      short loc_180049E44
0x180049e95  test    esi, esi
0x180049e97  jz      short loc_180049EB4
0x180049e99  call    cs:__imp_GetLastError
0x180049e9f  test    eax, eax
0x180049ea1  jle     short loc_180049EAB
0x180049ea3  movzx   eax, ax
0x180049ea6  or      eax, 80070000h
0x180049eab  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180049eb2  jmp     short loc_180049ED9
0x180049eb4  lea     rdx, [rsp+108h+Reply]; Reply
0x180049eb9  lea     rcx, [rsp+108h+pAsync]; pAsync
0x180049ebe  call    cs:__imp_RpcAsyncCompleteCall
0x180049ec4  test    eax, eax
0x180049ec6  jz      short loc_180049EF8
0x180049ec8  jle     short loc_180049ED2
0x180049eca  movzx   eax, ax
0x180049ecd  or      eax, 80070000h
0x180049ed2  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180049ed9  mov     r8d, 445h; unsigned int
0x180049edf  mov     [rsp+108h+Reply], eax
0x180049ee3  mov     [rsp+108h+bAlertable], eax
0x180049ee7  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180049eee  mov     ecx, 2; unsigned __int8
0x180049ef3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180049ef8  mov     rcx, qword ptr [rsp+108h+pAsync.u]; hObject
0x180049f00  test    rcx, rcx
0x180049f03  jz      short loc_180049F0B
0x180049f05  call    cs:__imp_CloseHandle
0x180049f0b  test    r15b, r15b
0x180049f0e  jz      short loc_180049F4F
0x180049f10  mov     [rsp+108h+Reply], 800705B4h
0x180049f18  lea     rdx, [rsp+108h+var_BC]
0x180049f1d  lea     rcx, aWlidcgetconfig_0; "WLIDCGetConfigDWORDValue"
0x180049f24  call    ??$RPCCallTimedOut@AEAY0BJ@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BJ@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[25],ulong &>(char const (&)[25],ulong &)
0x180049f29  mov     eax, [rsp+108h+Reply]
0x180049f2d  mov     [rsp+108h+bAlertable], eax
0x180049f31  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180049f38  mov     r8d, 445h; unsigned int
0x180049f3e  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180049f45  mov     ecx, 2; unsigned __int8
0x180049f4a  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180049f4f  test    r14b, r14b
0x180049f52  jz      short loc_180049F7F
0x180049f54  mov     eax, 800704C7h
0x180049f59  mov     [rsp+108h+Reply], eax
0x180049f5d  mov     [rsp+108h+bAlertable], eax
0x180049f61  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180049f68  mov     r8d, 445h; unsigned int
0x180049f6e  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180049f75  mov     ecx, 2; unsigned __int8
0x180049f7a  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180049f7f  cmp     [rsp+108h+Reply], 800706B5h
0x180049f87  jz      short loc_180049F93
0x180049f89  cmp     [rsp+108h+Reply], 800706BAh
0x180049f91  jnz     short loc_180049F98
0x180049f93  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180049f98  lea     rcx, [rsp+108h+var_B8]; this
0x180049f9d  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x180049fa2  mov     eax, [rsp+108h+Reply]
0x180049fa6  mov     rcx, [rsp+108h+var_28]
0x180049fae  xor     rcx, rsp; StackCookie
0x180049fb1  call    __security_check_cookie
0x180049fb6  lea     r11, [rsp+108h+var_18]
0x180049fbe  mov     rsi, [r11+30h]
0x180049fc2  mov     r12, [r11+38h]
0x180049fc6  mov     rsp, r11
0x180049fc9  pop     r15
0x180049fcb  pop     r14
0x180049fcd  pop     r13
0x180049fcf  retn
0x1800619b3  push    rbp
0x1800619b5  sub     rsp, 40h
0x1800619b9  mov     rbp, rdx
0x1800619bc  mov     rcx, [rcx]
0x1800619bf  mov     ecx, [rcx]; unsigned int
0x1800619c1  call    ?WLIDpExceptionFilter@@YAHK@Z
0x1800619c6  nop
0x1800619c7  add     rsp, 40h
0x1800619cb  pop     rbp
0x1800619cc  retn
```
