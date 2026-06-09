# WLIDCRemoveUserFromSsoGroup(ushort const *,unsigned __int64,ulong)

- ea: `0x18004e838`
- end: `0x18004eb9a`
- name: `?WLIDCRemoveUserFromSsoGroup@@YAJPEBG_KK@Z`
- size: `866`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800368a0`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180045308`
- `0x180046ce0`
- `0x18004cd04`
- `0x18004e838`
- `0x180050c84`
- `0x180050e40`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004ea09`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004ea5b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004ea09`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004ea5b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004e91f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004e91f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e932`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ea6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e932`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ea6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ead8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ead8`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004ea30`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004ea30`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004e981`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004e981`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004ea91`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004ea91`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004e8d8`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004e8d8`

## string_xrefs

- `0x18004e944`: `RPC failed to create new event, hr = %#x`
- `0x18004eaa5`: `RPC Async complete call failed, hr = %#x`
- `0x18004eaf0`: `WLIDCRemoveUserFromSsoGroup`

## pseudocode

```c
__int64 __fastcall WLIDCRemoveUserFromSsoGroup(const unsigned __int16 *a1, __int64 a2, int a3)
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
  int v18; // [rsp+4Ch] [rbp-CCh]
  DWORD v19; // [rsp+50h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+58h] [rbp-C0h] BYREF
  HANDLE Handles[2]; // [rsp+60h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-A8h] BYREF

  v18 = a3;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  v20 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v20);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v6 = dwMilliseconds;
  v19 = dwMilliseconds;
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
    v11 = 995;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x2Bu, 0, &pAsync, v20, a1, a2, v18);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v10 = L"RPC call failed, hr = %#x";
    v11 = 997;
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
    v11 = 997;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[28],unsigned long &>(
      (__int64)"WLIDCRemoveUserFromSsoGroup",
      (int *)&v19);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x3E5u,
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
      0x3E5u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v20);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x18004e838  push    rsi
0x18004e83a  push    r12
0x18004e83c  push    r13
0x18004e83e  push    r14
0x18004e840  push    r15
0x18004e842  sub     rsp, 0F0h
0x18004e849  mov     rax, cs:__security_cookie
0x18004e850  xor     rax, rsp
0x18004e853  mov     [rsp+118h+var_38], rax
0x18004e85b  mov     [rsp+118h+var_CC], r8d
0x18004e860  mov     r13, rdx
0x18004e863  mov     r12, rcx
0x18004e866  mov     [rsp+118h+dwMilliseconds], 0
0x18004e86e  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x18004e873  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004e878  mov     [rsp+118h+Reply], 0
0x18004e880  mov     [rsp+118h+var_C0], 0
0x18004e889  lea     rcx, [rsp+118h+var_C0]; this
0x18004e88e  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18004e893  mov     [rsp+118h+Reply], eax
0x18004e897  test    eax, eax
0x18004e899  js      loc_18004EB79
0x18004e89f  xor     edx, edx; Val
0x18004e8a1  lea     r8d, [rdx+70h]; Size
0x18004e8a5  lea     rcx, [rsp+118h+pAsync]; void *
0x18004e8aa  call    memset_0
0x18004e8af  mov     esi, [rsp+118h+dwMilliseconds]
0x18004e8b3  mov     [rsp+118h+dwMilliseconds], esi
0x18004e8b7  mov     [rsp+118h+var_C8], esi
0x18004e8bb  xor     r15b, r15b
0x18004e8be  mov     [rsp+118h+var_D4], r15b
0x18004e8c3  xor     r14b, r14b
0x18004e8c6  xorps   xmm0, xmm0
0x18004e8c9  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x18004e8ce  mov     edx, 70h ; 'p'; Size
0x18004e8d3  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004e8d8  call    cs:__imp_RpcAsyncInitializeHandle
0x18004e8de  test    eax, eax
0x18004e8e0  jz      short loc_18004E8FE
0x18004e8e2  jle     short loc_18004E8EC
0x18004e8e4  movzx   eax, ax
0x18004e8e7  or      eax, 80070000h
0x18004e8ec  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004e8f3  mov     r8d, 3E3h
0x18004e8f9  jmp     loc_18004EAB2
0x18004e8fe  mov     [rsp+118h+pAsync.UserInfo], 0
0x18004e90a  mov     [rsp+118h+pAsync.NotificationType], 1
0x18004e915  xor     r9d, r9d; lpName
0x18004e918  xor     r8d, r8d; bInitialState
0x18004e91b  xor     edx, edx; bManualReset
0x18004e91d  xor     ecx, ecx; lpEventAttributes
0x18004e91f  call    cs:__imp_CreateEventW
0x18004e925  mov     qword ptr [rsp+118h+pAsync.u], rax
0x18004e92d  test    rax, rax
0x18004e930  jnz     short loc_18004E94D
0x18004e932  call    cs:__imp_GetLastError
0x18004e938  test    eax, eax
0x18004e93a  jle     short loc_18004E944
0x18004e93c  movzx   eax, ax
0x18004e93f  or      eax, 80070000h
0x18004e944  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004e94b  jmp     short loc_18004E8F3
0x18004e94d  mov     [rsp+118h+Handles], rax
0x18004e952  mov     eax, [rsp+118h+var_CC]
0x18004e956  mov     [rsp+118h+var_E0], eax
0x18004e95a  mov     [rsp+118h+var_E8], r13
0x18004e95f  mov     [rsp+118h+var_F0], r12
0x18004e964  mov     rax, [rsp+118h+var_C0]
0x18004e969  mov     qword ptr [rsp+118h+bAlertable], rax
0x18004e96e  lea     r9, [rsp+118h+pAsync]
0x18004e973  xor     r8d, r8d; pReturnValue
0x18004e976  lea     edx, [r8+2Bh]; nProcNum
0x18004e97a  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004e981  call    cs:__imp_Ndr64AsyncClientCall
0x18004e987  mov     eax, [rsp+118h+Reply]
0x18004e98b  jmp     short loc_18004E9DC
0x18004e98d  test    eax, eax
0x18004e98f  jle     short loc_18004E999
0x18004e991  movzx   eax, ax
0x18004e994  or      eax, 80070000h
0x18004e999  mov     [rsp+118h+Reply], eax
0x18004e99d  mov     [rsp+118h+bAlertable], eax
0x18004e9a1  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004e9a8  mov     r8d, 3E5h; unsigned int
0x18004e9ae  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004e9b5  mov     ecx, 2; unsigned __int8
0x18004e9ba  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004e9bf  mov     eax, [rsp+118h+Reply]
0x18004e9c3  test    eax, eax
0x18004e9c5  js      short loc_18004E9D0
0x18004e9c7  mov     eax, 8000FFFFh
0x18004e9cc  mov     [rsp+118h+Reply], eax
0x18004e9d0  mov     esi, [rsp+118h+dwMilliseconds]
0x18004e9d4  mov     r15b, [rsp+118h+var_D4]
0x18004e9d9  mov     r14b, r15b
0x18004e9dc  test    eax, eax
0x18004e9de  jns     short loc_18004E9F2
0x18004e9e0  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004e9e7  mov     r8d, 3E5h
0x18004e9ed  jmp     loc_18004EAB6
0x18004e9f2  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004e9fa  mov     r9d, esi; dwMilliseconds
0x18004e9fd  xor     r8d, r8d; bWaitAll
0x18004ea00  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004ea05  lea     ecx, [r8+1]; nCount
0x18004ea09  call    cs:__imp_WaitForMultipleObjectsEx
0x18004ea0f  mov     esi, eax
0x18004ea11  mov     r12d, 102h
0x18004ea17  test    r14b, r14b
0x18004ea1a  jnz     short loc_18004EA68
0x18004ea1c  cmp     esi, r12d
0x18004ea1f  jz      short loc_18004EA26
0x18004ea21  cmp     esi, 1
0x18004ea24  jnz     short loc_18004EA68
0x18004ea26  mov     edx, 1; fAbort
0x18004ea2b  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004ea30  call    cs:__imp_RpcAsyncCancelCall
0x18004ea36  cmp     esi, r12d
0x18004ea39  jnz     short loc_18004EA40
0x18004ea3b  mov     r15b, 1
0x18004ea3e  jmp     short loc_18004EA43
0x18004ea40  mov     r14b, 1
0x18004ea43  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004ea4b  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004ea4f  xor     r8d, r8d; bWaitAll
0x18004ea52  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004ea57  lea     ecx, [r8+1]; nCount
0x18004ea5b  call    cs:__imp_WaitForMultipleObjectsEx
0x18004ea61  mov     esi, eax
0x18004ea63  test    r15b, r15b
0x18004ea66  jz      short loc_18004EA17
0x18004ea68  test    esi, esi
0x18004ea6a  jz      short loc_18004EA87
0x18004ea6c  call    cs:__imp_GetLastError
0x18004ea72  test    eax, eax
0x18004ea74  jle     short loc_18004EA7E
0x18004ea76  movzx   eax, ax
0x18004ea79  or      eax, 80070000h
0x18004ea7e  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004ea85  jmp     short loc_18004EAAC
0x18004ea87  lea     rdx, [rsp+118h+Reply]; Reply
0x18004ea8c  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004ea91  call    cs:__imp_RpcAsyncCompleteCall
0x18004ea97  test    eax, eax
0x18004ea99  jz      short loc_18004EACB
0x18004ea9b  jle     short loc_18004EAA5
0x18004ea9d  movzx   eax, ax
0x18004eaa0  or      eax, 80070000h
0x18004eaa5  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004eaac  mov     r8d, 3E5h; unsigned int
0x18004eab2  mov     [rsp+118h+Reply], eax
0x18004eab6  mov     [rsp+118h+bAlertable], eax
0x18004eaba  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004eac1  mov     ecx, 2; unsigned __int8
0x18004eac6  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004eacb  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x18004ead3  test    rcx, rcx
0x18004ead6  jz      short loc_18004EADE
0x18004ead8  call    cs:__imp_CloseHandle
0x18004eade  test    r15b, r15b
0x18004eae1  jz      short loc_18004EB22
0x18004eae3  mov     [rsp+118h+Reply], 800705B4h
0x18004eaeb  lea     rdx, [rsp+118h+var_C8]
0x18004eaf0  lea     rcx, aWlidcremoveuse; "WLIDCRemoveUserFromSsoGroup"
0x18004eaf7  call    ??$RPCCallTimedOut@AEAY0BM@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BM@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[28],ulong &>(char const (&)[28],ulong &)
0x18004eafc  mov     eax, [rsp+118h+Reply]
0x18004eb00  mov     [rsp+118h+bAlertable], eax
0x18004eb04  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004eb0b  mov     r8d, 3E5h; unsigned int
0x18004eb11  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004eb18  mov     ecx, 2; unsigned __int8
0x18004eb1d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004eb22  test    r14b, r14b
0x18004eb25  jz      short loc_18004EB52
0x18004eb27  mov     eax, 800704C7h
0x18004eb2c  mov     [rsp+118h+Reply], eax
0x18004eb30  mov     [rsp+118h+bAlertable], eax
0x18004eb34  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004eb3b  mov     r8d, 3E5h; unsigned int
0x18004eb41  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004eb48  mov     ecx, 2; unsigned __int8
0x18004eb4d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004eb52  cmp     [rsp+118h+Reply], 800706B5h
0x18004eb5a  jz      short loc_18004EB66
0x18004eb5c  cmp     [rsp+118h+Reply], 800706BAh
0x18004eb64  jnz     short loc_18004EB6B
0x18004eb66  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004eb6b  lea     rcx, [rsp+118h+var_C0]; this
0x18004eb70  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18004eb75  mov     eax, [rsp+118h+Reply]
0x18004eb79  mov     rcx, [rsp+118h+var_38]
0x18004eb81  xor     rcx, rsp; StackCookie
0x18004eb84  call    __security_check_cookie
0x18004eb89  add     rsp, 0F0h
0x18004eb90  pop     r15
0x18004eb92  pop     r14
0x18004eb94  pop     r13
0x18004eb96  pop     r12
0x18004eb98  pop     rsi
0x18004eb99  retn
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
