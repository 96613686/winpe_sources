# WLIDCRenewDeviceId(ushort const *,ulong,unsigned __int64)

- ea: `0x18004eba0`
- end: `0x18004ef04`
- name: `?WLIDCRenewDeviceId@@YAJPEBGK_K@Z`
- size: `868`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180032e20`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180044eac`
- `0x180046ce0`
- `0x18004cd04`
- `0x18004eba0`
- `0x180050c84`
- `0x180050e40`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004ed73`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004edc5`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004ed73`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004edc5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004ec87`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004ec87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ec9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004edd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ec9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004edd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ee42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ee42`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004ed9a`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004ed9a`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004eceb`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004eceb`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004edfb`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004edfb`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004ec40`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004ec40`

## string_xrefs

- `0x18004ecac`: `RPC failed to create new event, hr = %#x`
- `0x18004ee0f`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCRenewDeviceId(const unsigned __int16 *a1, unsigned int a2, __int64 a3)
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
  __int64 v20; // [rsp+58h] [rbp-C0h]
  HANDLE Handles[2]; // [rsp+60h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-A8h] BYREF

  v20 = a3;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
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
    v11 = 1267;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x21u, 0, &pAsync, v19, a1, a2, v20);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v10 = L"RPC call failed, hr = %#x";
    v11 = 1269;
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
    v11 = 1269;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[19],unsigned long &>(
      (__int64)"WLIDCRenewDeviceId",
      (int *)&v18);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x4F5u,
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
      0x4F5u,
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
0x18004eba0  push    rsi
0x18004eba2  push    r12
0x18004eba4  push    r13
0x18004eba6  push    r14
0x18004eba8  push    r15
0x18004ebaa  sub     rsp, 0F0h
0x18004ebb1  mov     rax, cs:__security_cookie
0x18004ebb8  xor     rax, rsp
0x18004ebbb  mov     [rsp+118h+var_38], rax
0x18004ebc3  mov     [rsp+118h+var_C0], r8
0x18004ebc8  mov     r13d, edx
0x18004ebcb  mov     r12, rcx
0x18004ebce  mov     [rsp+118h+dwMilliseconds], 0
0x18004ebd6  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x18004ebdb  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004ebe0  mov     [rsp+118h+Reply], 0
0x18004ebe8  mov     [rsp+118h+var_C8], 0
0x18004ebf1  lea     rcx, [rsp+118h+var_C8]; this
0x18004ebf6  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18004ebfb  mov     [rsp+118h+Reply], eax
0x18004ebff  test    eax, eax
0x18004ec01  js      loc_18004EEE3
0x18004ec07  xor     edx, edx; Val
0x18004ec09  lea     r8d, [rdx+70h]; Size
0x18004ec0d  lea     rcx, [rsp+118h+pAsync]; void *
0x18004ec12  call    memset_0
0x18004ec17  mov     esi, [rsp+118h+dwMilliseconds]
0x18004ec1b  mov     [rsp+118h+dwMilliseconds], esi
0x18004ec1f  mov     [rsp+118h+var_CC], esi
0x18004ec23  xor     r15b, r15b
0x18004ec26  mov     [rsp+118h+var_D4], r15b
0x18004ec2b  xor     r14b, r14b
0x18004ec2e  xorps   xmm0, xmm0
0x18004ec31  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x18004ec36  mov     edx, 70h ; 'p'; Size
0x18004ec3b  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004ec40  call    cs:__imp_RpcAsyncInitializeHandle
0x18004ec46  test    eax, eax
0x18004ec48  jz      short loc_18004EC66
0x18004ec4a  jle     short loc_18004EC54
0x18004ec4c  movzx   eax, ax
0x18004ec4f  or      eax, 80070000h
0x18004ec54  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004ec5b  mov     r8d, 4F3h
0x18004ec61  jmp     loc_18004EE1C
0x18004ec66  mov     [rsp+118h+pAsync.UserInfo], 0
0x18004ec72  mov     [rsp+118h+pAsync.NotificationType], 1
0x18004ec7d  xor     r9d, r9d; lpName
0x18004ec80  xor     r8d, r8d; bInitialState
0x18004ec83  xor     edx, edx; bManualReset
0x18004ec85  xor     ecx, ecx; lpEventAttributes
0x18004ec87  call    cs:__imp_CreateEventW
0x18004ec8d  mov     qword ptr [rsp+118h+pAsync.u], rax
0x18004ec95  test    rax, rax
0x18004ec98  jnz     short loc_18004ECB5
0x18004ec9a  call    cs:__imp_GetLastError
0x18004eca0  test    eax, eax
0x18004eca2  jle     short loc_18004ECAC
0x18004eca4  movzx   eax, ax
0x18004eca7  or      eax, 80070000h
0x18004ecac  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004ecb3  jmp     short loc_18004EC5B
0x18004ecb5  mov     [rsp+118h+Handles], rax
0x18004ecba  mov     rax, [rsp+118h+var_C0]
0x18004ecbf  mov     [rsp+118h+var_E0], rax
0x18004ecc4  mov     [rsp+118h+var_E8], r13d
0x18004ecc9  mov     [rsp+118h+var_F0], r12
0x18004ecce  mov     rax, [rsp+118h+var_C8]
0x18004ecd3  mov     qword ptr [rsp+118h+bAlertable], rax
0x18004ecd8  lea     r9, [rsp+118h+pAsync]
0x18004ecdd  xor     r8d, r8d; pReturnValue
0x18004ece0  lea     edx, [r8+21h]; nProcNum
0x18004ece4  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004eceb  call    cs:__imp_Ndr64AsyncClientCall
0x18004ecf1  mov     eax, [rsp+118h+Reply]
0x18004ecf5  jmp     short loc_18004ED46
0x18004ecf7  test    eax, eax
0x18004ecf9  jle     short loc_18004ED03
0x18004ecfb  movzx   eax, ax
0x18004ecfe  or      eax, 80070000h
0x18004ed03  mov     [rsp+118h+Reply], eax
0x18004ed07  mov     [rsp+118h+bAlertable], eax
0x18004ed0b  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004ed12  mov     r8d, 4F5h; unsigned int
0x18004ed18  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004ed1f  mov     ecx, 2; unsigned __int8
0x18004ed24  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004ed29  mov     eax, [rsp+118h+Reply]
0x18004ed2d  test    eax, eax
0x18004ed2f  js      short loc_18004ED3A
0x18004ed31  mov     eax, 8000FFFFh
0x18004ed36  mov     [rsp+118h+Reply], eax
0x18004ed3a  mov     esi, [rsp+118h+dwMilliseconds]
0x18004ed3e  mov     r15b, [rsp+118h+var_D4]
0x18004ed43  mov     r14b, r15b
0x18004ed46  test    eax, eax
0x18004ed48  jns     short loc_18004ED5C
0x18004ed4a  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004ed51  mov     r8d, 4F5h
0x18004ed57  jmp     loc_18004EE20
0x18004ed5c  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004ed64  mov     r9d, esi; dwMilliseconds
0x18004ed67  xor     r8d, r8d; bWaitAll
0x18004ed6a  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004ed6f  lea     ecx, [r8+1]; nCount
0x18004ed73  call    cs:__imp_WaitForMultipleObjectsEx
0x18004ed79  mov     esi, eax
0x18004ed7b  mov     r12d, 102h
0x18004ed81  test    r14b, r14b
0x18004ed84  jnz     short loc_18004EDD2
0x18004ed86  cmp     esi, r12d
0x18004ed89  jz      short loc_18004ED90
0x18004ed8b  cmp     esi, 1
0x18004ed8e  jnz     short loc_18004EDD2
0x18004ed90  mov     edx, 1; fAbort
0x18004ed95  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004ed9a  call    cs:__imp_RpcAsyncCancelCall
0x18004eda0  cmp     esi, r12d
0x18004eda3  jnz     short loc_18004EDAA
0x18004eda5  mov     r15b, 1
0x18004eda8  jmp     short loc_18004EDAD
0x18004edaa  mov     r14b, 1
0x18004edad  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004edb5  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004edb9  xor     r8d, r8d; bWaitAll
0x18004edbc  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004edc1  lea     ecx, [r8+1]; nCount
0x18004edc5  call    cs:__imp_WaitForMultipleObjectsEx
0x18004edcb  mov     esi, eax
0x18004edcd  test    r15b, r15b
0x18004edd0  jz      short loc_18004ED81
0x18004edd2  test    esi, esi
0x18004edd4  jz      short loc_18004EDF1
0x18004edd6  call    cs:__imp_GetLastError
0x18004eddc  test    eax, eax
0x18004edde  jle     short loc_18004EDE8
0x18004ede0  movzx   eax, ax
0x18004ede3  or      eax, 80070000h
0x18004ede8  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004edef  jmp     short loc_18004EE16
0x18004edf1  lea     rdx, [rsp+118h+Reply]; Reply
0x18004edf6  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004edfb  call    cs:__imp_RpcAsyncCompleteCall
0x18004ee01  test    eax, eax
0x18004ee03  jz      short loc_18004EE35
0x18004ee05  jle     short loc_18004EE0F
0x18004ee07  movzx   eax, ax
0x18004ee0a  or      eax, 80070000h
0x18004ee0f  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004ee16  mov     r8d, 4F5h; unsigned int
0x18004ee1c  mov     [rsp+118h+Reply], eax
0x18004ee20  mov     [rsp+118h+bAlertable], eax
0x18004ee24  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004ee2b  mov     ecx, 2; unsigned __int8
0x18004ee30  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004ee35  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x18004ee3d  test    rcx, rcx
0x18004ee40  jz      short loc_18004EE48
0x18004ee42  call    cs:__imp_CloseHandle
0x18004ee48  test    r15b, r15b
0x18004ee4b  jz      short loc_18004EE8C
0x18004ee4d  mov     [rsp+118h+Reply], 800705B4h
0x18004ee55  lea     rdx, [rsp+118h+var_CC]
0x18004ee5a  lea     rcx, aWlidcrenewdevi; "WLIDCRenewDeviceId"
0x18004ee61  call    ??$RPCCallTimedOut@AEAY0BD@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BD@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[19],ulong &>(char const (&)[19],ulong &)
0x18004ee66  mov     eax, [rsp+118h+Reply]
0x18004ee6a  mov     [rsp+118h+bAlertable], eax
0x18004ee6e  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004ee75  mov     r8d, 4F5h; unsigned int
0x18004ee7b  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004ee82  mov     ecx, 2; unsigned __int8
0x18004ee87  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004ee8c  test    r14b, r14b
0x18004ee8f  jz      short loc_18004EEBC
0x18004ee91  mov     eax, 800704C7h
0x18004ee96  mov     [rsp+118h+Reply], eax
0x18004ee9a  mov     [rsp+118h+bAlertable], eax
0x18004ee9e  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004eea5  mov     r8d, 4F5h; unsigned int
0x18004eeab  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004eeb2  mov     ecx, 2; unsigned __int8
0x18004eeb7  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004eebc  cmp     [rsp+118h+Reply], 800706B5h
0x18004eec4  jz      short loc_18004EED0
0x18004eec6  cmp     [rsp+118h+Reply], 800706BAh
0x18004eece  jnz     short loc_18004EED5
0x18004eed0  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004eed5  lea     rcx, [rsp+118h+var_C8]; this
0x18004eeda  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18004eedf  mov     eax, [rsp+118h+Reply]
0x18004eee3  mov     rcx, [rsp+118h+var_38]
0x18004eeeb  xor     rcx, rsp; StackCookie
0x18004eeee  call    __security_check_cookie
0x18004eef3  add     rsp, 0F0h
0x18004eefa  pop     r15
0x18004eefc  pop     r14
0x18004eefe  pop     r13
0x18004ef00  pop     r12
0x18004ef02  pop     rsi
0x18004ef03  retn
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
