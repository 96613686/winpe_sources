# WLIDCpGetConfigDWORDValue(ulong,ulong *)

- ea: `0x180010cc4`
- end: `0x180011009`
- name: `?WLIDCpGetConfigDWORDValue@@YAJKPEAK@Z`
- size: `837`
- prototype: `__int64 __fastcall(unsigned int, unsigned int *)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180006c70`
- `0x18000ceb0`
- `0x180010c68`

## callees

- `0x18000a400`
- `0x18000f870`
- `0x180010cc4`
- `0x180011588`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180041f38`
- `0x180043240`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010d8f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010d8f`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180010e73`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180010ec5`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180010e73`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180010ec5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010da2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ed6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010da2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ed6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010f42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010f42`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180010d48`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180010d48`
- `RPCRT4!RpcAsyncCancelCall` at `0x180010e97`
- `RPCRT4!RpcAsyncCancelCall` at `0x180010e97`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180010dec`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180010dec`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180010efb`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180010efb`

## string_xrefs

- `0x180010db4`: `RPC failed to create new event, hr = %#x`
- `0x180010f0f`: `RPC Async complete call failed, hr = %#x`
- `0x180010f5a`: `WLIDCpGetConfigDWORDValue`

## pseudocode

```c
__int64 __fastcall WLIDCpGetConfigDWORDValue(__int64 a1, unsigned int *a2)
{
  __int64 result; // rax
  char v4; // r15
  char v5; // r14
  int LastError; // eax
  const unsigned __int16 *v7; // r9
  unsigned int v8; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v10; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-D8h]
  int Reply; // [rsp+40h] [rbp-B8h] BYREF
  char v13; // [rsp+44h] [rbp-B4h]
  int v14; // [rsp+48h] [rbp-B0h] BYREF
  __int64 v15; // [rsp+50h] [rbp-A8h] BYREF
  HANDLE Handles[3]; // [rsp+58h] [rbp-A0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-88h] BYREF

  v15 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v15);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v14 = 5000;
  v4 = 0;
  v13 = 0;
  v5 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v8 = 362;
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
    v7 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x36u, 0, &pAsync, v15, 3, a2);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v7 = L"RPC call failed, hr = %#x";
    v8 = 364;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v8,
      v7,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
  v10 = WaitForMultipleObjectsEx(1u, Handles, 0, 0x1388u, 0);
  do
  {
    if ( v5 || v10 != 258 && v10 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v10 == 258 )
      v4 = 1;
    else
      v5 = 1;
    v10 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v4 );
  if ( v10 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = L"Encountered error while waiting on RPC call, hr = %#x";
LABEL_29:
    v8 = 364;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v4 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[26],unsigned long &>("WLIDCpGetConfigDWORDValue", &v14);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x16Cu,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v5 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x16Cu,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v15);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x180010cc4  mov     [rsp+arg_0], rsi
0x180010cc9  mov     [rsp+arg_10], r14
0x180010cce  push    r15
0x180010cd0  sub     rsp, 0F0h
0x180010cd7  mov     rax, cs:__security_cookie
0x180010cde  xor     rax, rsp
0x180010ce1  mov     [rsp+0F8h+var_18], rax
0x180010ce9  mov     rsi, rdx
0x180010cec  mov     [rsp+0F8h+Reply], 0
0x180010cf4  mov     [rsp+0F8h+var_A8], 0
0x180010cfd  lea     rcx, [rsp+0F8h+var_A8]; this
0x180010d02  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x180010d07  mov     [rsp+0F8h+Reply], eax
0x180010d0b  test    eax, eax
0x180010d0d  js      loc_180010FE3
0x180010d13  xor     edx, edx; Val
0x180010d15  lea     r8d, [rdx+70h]; Size
0x180010d19  lea     rcx, [rsp+0F8h+pAsync]; void *
0x180010d1e  call    memset_0
0x180010d23  mov     [rsp+0F8h+var_B0], 1388h
0x180010d2b  xor     r15b, r15b
0x180010d2e  mov     [rsp+0F8h+var_B4], r15b
0x180010d33  xor     r14b, r14b
0x180010d36  xorps   xmm0, xmm0
0x180010d39  movups  xmmword ptr [rsp+0F8h+Handles], xmm0
0x180010d3e  mov     edx, 70h ; 'p'; Size
0x180010d43  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x180010d48  call    cs:__imp_RpcAsyncInitializeHandle
0x180010d4e  test    eax, eax
0x180010d50  jz      short loc_180010D6E
0x180010d52  jle     short loc_180010D5C
0x180010d54  movzx   eax, ax
0x180010d57  or      eax, 80070000h
0x180010d5c  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180010d63  mov     r8d, 16Ah
0x180010d69  jmp     loc_180010F1C
0x180010d6e  mov     [rsp+0F8h+pAsync.UserInfo], 0
0x180010d7a  mov     [rsp+0F8h+pAsync.NotificationType], 1
0x180010d85  xor     r9d, r9d; lpName
0x180010d88  xor     r8d, r8d; bInitialState
0x180010d8b  xor     edx, edx; bManualReset
0x180010d8d  xor     ecx, ecx; lpEventAttributes
0x180010d8f  call    cs:__imp_CreateEventW
0x180010d95  mov     qword ptr [rsp+0F8h+pAsync.u], rax
0x180010d9d  test    rax, rax
0x180010da0  jnz     short loc_180010DBD
0x180010da2  call    cs:__imp_GetLastError
0x180010da8  test    eax, eax
0x180010daa  jle     short loc_180010DB4
0x180010dac  movzx   eax, ax
0x180010daf  or      eax, 80070000h
0x180010db4  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180010dbb  jmp     short loc_180010D63
0x180010dbd  mov     [rsp+0F8h+Handles], rax
0x180010dc2  mov     [rsp+0F8h+var_C8], rsi
0x180010dc7  mov     [rsp+0F8h+var_D0], 3
0x180010dcf  mov     rax, [rsp+0F8h+var_A8]
0x180010dd4  mov     qword ptr [rsp+0F8h+bAlertable], rax
0x180010dd9  lea     r9, [rsp+0F8h+pAsync]
0x180010dde  xor     r8d, r8d; pReturnValue
0x180010de1  lea     edx, [r8+36h]; nProcNum
0x180010de5  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180010dec  call    cs:__imp_Ndr64AsyncClientCall
0x180010df2  mov     eax, [rsp+0F8h+Reply]
0x180010df6  jmp     short loc_180010E43
0x180010df8  test    eax, eax
0x180010dfa  jle     short loc_180010E04
0x180010dfc  movzx   eax, ax
0x180010dff  or      eax, 80070000h
0x180010e04  mov     [rsp+0F8h+Reply], eax
0x180010e08  mov     [rsp+0F8h+bAlertable], eax
0x180010e0c  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180010e13  mov     r8d, 16Ch; unsigned int
0x180010e19  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180010e20  mov     ecx, 2; unsigned __int8
0x180010e25  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180010e2a  mov     eax, [rsp+0F8h+Reply]
0x180010e2e  test    eax, eax
0x180010e30  js      short loc_180010E3B
0x180010e32  mov     eax, 8000FFFFh
0x180010e37  mov     [rsp+0F8h+Reply], eax
0x180010e3b  mov     r15b, [rsp+0F8h+var_B4]
0x180010e40  mov     r14b, r15b
0x180010e43  test    eax, eax
0x180010e45  jns     short loc_180010E59
0x180010e47  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180010e4e  mov     r8d, 16Ch
0x180010e54  jmp     loc_180010F20
0x180010e59  mov     [rsp+0F8h+bAlertable], 0; bAlertable
0x180010e61  mov     r9d, 1388h; dwMilliseconds
0x180010e67  xor     r8d, r8d; bWaitAll
0x180010e6a  lea     rdx, [rsp+0F8h+Handles]; lpHandles
0x180010e6f  lea     ecx, [r8+1]; nCount
0x180010e73  call    cs:__imp_WaitForMultipleObjectsEx
0x180010e79  mov     esi, eax
0x180010e7b  test    r14b, r14b
0x180010e7e  jnz     short loc_180010ED2
0x180010e80  cmp     esi, 102h
0x180010e86  jz      short loc_180010E8D
0x180010e88  cmp     esi, 1
0x180010e8b  jnz     short loc_180010ED2
0x180010e8d  mov     edx, 1; fAbort
0x180010e92  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x180010e97  call    cs:__imp_RpcAsyncCancelCall
0x180010e9d  cmp     esi, 102h
0x180010ea3  jnz     short loc_180010EAA
0x180010ea5  mov     r15b, 1
0x180010ea8  jmp     short loc_180010EAD
0x180010eaa  mov     r14b, 1
0x180010ead  mov     [rsp+0F8h+bAlertable], 0; bAlertable
0x180010eb5  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180010eb9  xor     r8d, r8d; bWaitAll
0x180010ebc  lea     rdx, [rsp+0F8h+Handles]; lpHandles
0x180010ec1  lea     ecx, [r8+1]; nCount
0x180010ec5  call    cs:__imp_WaitForMultipleObjectsEx
0x180010ecb  mov     esi, eax
0x180010ecd  test    r15b, r15b
0x180010ed0  jz      short loc_180010E7B
0x180010ed2  test    esi, esi
0x180010ed4  jz      short loc_180010EF1
0x180010ed6  call    cs:__imp_GetLastError
0x180010edc  test    eax, eax
0x180010ede  jle     short loc_180010EE8
0x180010ee0  movzx   eax, ax
0x180010ee3  or      eax, 80070000h
0x180010ee8  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180010eef  jmp     short loc_180010F16
0x180010ef1  lea     rdx, [rsp+0F8h+Reply]; Reply
0x180010ef6  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x180010efb  call    cs:__imp_RpcAsyncCompleteCall
0x180010f01  test    eax, eax
0x180010f03  jz      short loc_180010F35
0x180010f05  jle     short loc_180010F0F
0x180010f07  movzx   eax, ax
0x180010f0a  or      eax, 80070000h
0x180010f0f  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180010f16  mov     r8d, 16Ch; unsigned int
0x180010f1c  mov     [rsp+0F8h+Reply], eax
0x180010f20  mov     [rsp+0F8h+bAlertable], eax
0x180010f24  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180010f2b  mov     ecx, 2; unsigned __int8
0x180010f30  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180010f35  mov     rcx, qword ptr [rsp+0F8h+pAsync.u]; hObject
0x180010f3d  test    rcx, rcx
0x180010f40  jz      short loc_180010F48
0x180010f42  call    cs:__imp_CloseHandle
0x180010f48  test    r15b, r15b
0x180010f4b  jz      short loc_180010F8C
0x180010f4d  mov     [rsp+0F8h+Reply], 800705B4h
0x180010f55  lea     rdx, [rsp+0F8h+var_B0]
0x180010f5a  lea     rcx, aWlidcpgetconfi; "WLIDCpGetConfigDWORDValue"
0x180010f61  call    ??$RPCCallTimedOut@AEAY0BK@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BK@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[26],ulong &>(char const (&)[26],ulong &)
0x180010f66  mov     eax, [rsp+0F8h+Reply]
0x180010f6a  mov     [rsp+0F8h+bAlertable], eax
0x180010f6e  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180010f75  mov     r8d, 16Ch; unsigned int
0x180010f7b  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180010f82  mov     ecx, 2; unsigned __int8
0x180010f87  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180010f8c  test    r14b, r14b
0x180010f8f  jz      short loc_180010FBC
0x180010f91  mov     eax, 800704C7h
0x180010f96  mov     [rsp+0F8h+Reply], eax
0x180010f9a  mov     [rsp+0F8h+bAlertable], eax
0x180010f9e  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180010fa5  mov     r8d, 16Ch; unsigned int
0x180010fab  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180010fb2  mov     ecx, 2; unsigned __int8
0x180010fb7  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180010fbc  cmp     [rsp+0F8h+Reply], 800706B5h
0x180010fc4  jz      short loc_180010FD0
0x180010fc6  cmp     [rsp+0F8h+Reply], 800706BAh
0x180010fce  jnz     short loc_180010FD5
0x180010fd0  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180010fd5  lea     rcx, [rsp+0F8h+var_A8]; this
0x180010fda  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x180010fdf  mov     eax, [rsp+0F8h+Reply]
0x180010fe3  mov     rcx, [rsp+0F8h+var_18]
0x180010feb  xor     rcx, rsp; StackCookie
0x180010fee  call    __security_check_cookie
0x180010ff3  lea     r11, [rsp+0F8h+var_8]
0x180010ffb  mov     rsi, [r11+10h]
0x180010fff  mov     r14, [r11+20h]
0x180011003  mov     rsp, r11
0x180011006  pop     r15
0x180011008  retn
0x180054b44  push    rbp
0x180054b46  sub     rsp, 40h
0x180054b4a  mov     rbp, rdx
0x180054b4d  mov     rcx, [rcx]
0x180054b50  mov     ecx, [rcx]; unsigned int
0x180054b52  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x180054b57  nop
0x180054b58  add     rsp, 40h
0x180054b5c  pop     rbp
0x180054b5d  retn
```
