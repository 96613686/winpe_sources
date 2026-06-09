# WLIDCpGetConfigDWORDValue(ulong,ulong *)

- ea: `0x180050724`
- end: `0x180050a69`
- name: `?WLIDCpGetConfigDWORDValue@@YAJKPEAK@Z`
- size: `837`
- prototype: `__int64 __fastcall(unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18004cd04`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x1800451f4`
- `0x180046ce0`
- `0x180050724`
- `0x180050c84`
- `0x180050e40`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800508d3`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180050925`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800508d3`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180050925`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800507ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800507ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050802`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050936`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050802`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050936`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800509a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800509a2`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800508f7`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800508f7`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18005084c`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18005084c`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18005095b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18005095b`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800507a8`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800507a8`

## string_xrefs

- `0x180050814`: `RPC failed to create new event, hr = %#x`
- `0x18005096f`: `RPC Async complete call failed, hr = %#x`
- `0x1800509ba`: `WLIDCpGetConfigDWORDValue`

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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[26],unsigned long &>(
      (__int64)"WLIDCpGetConfigDWORDValue",
      &v14);
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
0x180050724  mov     [rsp+arg_0], rsi
0x180050729  mov     [rsp+arg_10], r14
0x18005072e  push    r15
0x180050730  sub     rsp, 0F0h
0x180050737  mov     rax, cs:__security_cookie
0x18005073e  xor     rax, rsp
0x180050741  mov     [rsp+0F8h+var_18], rax
0x180050749  mov     rsi, rdx
0x18005074c  mov     [rsp+0F8h+Reply], 0
0x180050754  mov     [rsp+0F8h+var_A8], 0
0x18005075d  lea     rcx, [rsp+0F8h+var_A8]; this
0x180050762  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x180050767  mov     [rsp+0F8h+Reply], eax
0x18005076b  test    eax, eax
0x18005076d  js      loc_180050A43
0x180050773  xor     edx, edx; Val
0x180050775  lea     r8d, [rdx+70h]; Size
0x180050779  lea     rcx, [rsp+0F8h+pAsync]; void *
0x18005077e  call    memset_0
0x180050783  mov     [rsp+0F8h+var_B0], 1388h
0x18005078b  xor     r15b, r15b
0x18005078e  mov     [rsp+0F8h+var_B4], r15b
0x180050793  xor     r14b, r14b
0x180050796  xorps   xmm0, xmm0
0x180050799  movups  xmmword ptr [rsp+0F8h+Handles], xmm0
0x18005079e  mov     edx, 70h ; 'p'; Size
0x1800507a3  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x1800507a8  call    cs:__imp_RpcAsyncInitializeHandle
0x1800507ae  test    eax, eax
0x1800507b0  jz      short loc_1800507CE
0x1800507b2  jle     short loc_1800507BC
0x1800507b4  movzx   eax, ax
0x1800507b7  or      eax, 80070000h
0x1800507bc  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x1800507c3  mov     r8d, 16Ah
0x1800507c9  jmp     loc_18005097C
0x1800507ce  mov     [rsp+0F8h+pAsync.UserInfo], 0
0x1800507da  mov     [rsp+0F8h+pAsync.NotificationType], 1
0x1800507e5  xor     r9d, r9d; lpName
0x1800507e8  xor     r8d, r8d; bInitialState
0x1800507eb  xor     edx, edx; bManualReset
0x1800507ed  xor     ecx, ecx; lpEventAttributes
0x1800507ef  call    cs:__imp_CreateEventW
0x1800507f5  mov     qword ptr [rsp+0F8h+pAsync.u], rax
0x1800507fd  test    rax, rax
0x180050800  jnz     short loc_18005081D
0x180050802  call    cs:__imp_GetLastError
0x180050808  test    eax, eax
0x18005080a  jle     short loc_180050814
0x18005080c  movzx   eax, ax
0x18005080f  or      eax, 80070000h
0x180050814  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18005081b  jmp     short loc_1800507C3
0x18005081d  mov     [rsp+0F8h+Handles], rax
0x180050822  mov     [rsp+0F8h+var_C8], rsi
0x180050827  mov     [rsp+0F8h+var_D0], 3
0x18005082f  mov     rax, [rsp+0F8h+var_A8]
0x180050834  mov     qword ptr [rsp+0F8h+bAlertable], rax
0x180050839  lea     r9, [rsp+0F8h+pAsync]
0x18005083e  xor     r8d, r8d; pReturnValue
0x180050841  lea     edx, [r8+36h]; nProcNum
0x180050845  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18005084c  call    cs:__imp_Ndr64AsyncClientCall
0x180050852  mov     eax, [rsp+0F8h+Reply]
0x180050856  jmp     short loc_1800508A3
0x180050858  test    eax, eax
0x18005085a  jle     short loc_180050864
0x18005085c  movzx   eax, ax
0x18005085f  or      eax, 80070000h
0x180050864  mov     [rsp+0F8h+Reply], eax
0x180050868  mov     [rsp+0F8h+bAlertable], eax
0x18005086c  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180050873  mov     r8d, 16Ch; unsigned int
0x180050879  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180050880  mov     ecx, 2; unsigned __int8
0x180050885  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18005088a  mov     eax, [rsp+0F8h+Reply]
0x18005088e  test    eax, eax
0x180050890  js      short loc_18005089B
0x180050892  mov     eax, 8000FFFFh
0x180050897  mov     [rsp+0F8h+Reply], eax
0x18005089b  mov     r15b, [rsp+0F8h+var_B4]
0x1800508a0  mov     r14b, r15b
0x1800508a3  test    eax, eax
0x1800508a5  jns     short loc_1800508B9
0x1800508a7  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x1800508ae  mov     r8d, 16Ch
0x1800508b4  jmp     loc_180050980
0x1800508b9  mov     [rsp+0F8h+bAlertable], 0; bAlertable
0x1800508c1  mov     r9d, 1388h; dwMilliseconds
0x1800508c7  xor     r8d, r8d; bWaitAll
0x1800508ca  lea     rdx, [rsp+0F8h+Handles]; lpHandles
0x1800508cf  lea     ecx, [r8+1]; nCount
0x1800508d3  call    cs:__imp_WaitForMultipleObjectsEx
0x1800508d9  mov     esi, eax
0x1800508db  test    r14b, r14b
0x1800508de  jnz     short loc_180050932
0x1800508e0  cmp     esi, 102h
0x1800508e6  jz      short loc_1800508ED
0x1800508e8  cmp     esi, 1
0x1800508eb  jnz     short loc_180050932
0x1800508ed  mov     edx, 1; fAbort
0x1800508f2  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x1800508f7  call    cs:__imp_RpcAsyncCancelCall
0x1800508fd  cmp     esi, 102h
0x180050903  jnz     short loc_18005090A
0x180050905  mov     r15b, 1
0x180050908  jmp     short loc_18005090D
0x18005090a  mov     r14b, 1
0x18005090d  mov     [rsp+0F8h+bAlertable], 0; bAlertable
0x180050915  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180050919  xor     r8d, r8d; bWaitAll
0x18005091c  lea     rdx, [rsp+0F8h+Handles]; lpHandles
0x180050921  lea     ecx, [r8+1]; nCount
0x180050925  call    cs:__imp_WaitForMultipleObjectsEx
0x18005092b  mov     esi, eax
0x18005092d  test    r15b, r15b
0x180050930  jz      short loc_1800508DB
0x180050932  test    esi, esi
0x180050934  jz      short loc_180050951
0x180050936  call    cs:__imp_GetLastError
0x18005093c  test    eax, eax
0x18005093e  jle     short loc_180050948
0x180050940  movzx   eax, ax
0x180050943  or      eax, 80070000h
0x180050948  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18005094f  jmp     short loc_180050976
0x180050951  lea     rdx, [rsp+0F8h+Reply]; Reply
0x180050956  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x18005095b  call    cs:__imp_RpcAsyncCompleteCall
0x180050961  test    eax, eax
0x180050963  jz      short loc_180050995
0x180050965  jle     short loc_18005096F
0x180050967  movzx   eax, ax
0x18005096a  or      eax, 80070000h
0x18005096f  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180050976  mov     r8d, 16Ch; unsigned int
0x18005097c  mov     [rsp+0F8h+Reply], eax
0x180050980  mov     [rsp+0F8h+bAlertable], eax
0x180050984  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18005098b  mov     ecx, 2; unsigned __int8
0x180050990  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180050995  mov     rcx, qword ptr [rsp+0F8h+pAsync.u]; hObject
0x18005099d  test    rcx, rcx
0x1800509a0  jz      short loc_1800509A8
0x1800509a2  call    cs:__imp_CloseHandle
0x1800509a8  test    r15b, r15b
0x1800509ab  jz      short loc_1800509EC
0x1800509ad  mov     [rsp+0F8h+Reply], 800705B4h
0x1800509b5  lea     rdx, [rsp+0F8h+var_B0]
0x1800509ba  lea     rcx, aWlidcpgetconfi; "WLIDCpGetConfigDWORDValue"
0x1800509c1  call    ??$RPCCallTimedOut@AEAY0BK@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BK@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[26],ulong &>(char const (&)[26],ulong &)
0x1800509c6  mov     eax, [rsp+0F8h+Reply]
0x1800509ca  mov     [rsp+0F8h+bAlertable], eax
0x1800509ce  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x1800509d5  mov     r8d, 16Ch; unsigned int
0x1800509db  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800509e2  mov     ecx, 2; unsigned __int8
0x1800509e7  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800509ec  test    r14b, r14b
0x1800509ef  jz      short loc_180050A1C
0x1800509f1  mov     eax, 800704C7h
0x1800509f6  mov     [rsp+0F8h+Reply], eax
0x1800509fa  mov     [rsp+0F8h+bAlertable], eax
0x1800509fe  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180050a05  mov     r8d, 16Ch; unsigned int
0x180050a0b  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180050a12  mov     ecx, 2; unsigned __int8
0x180050a17  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180050a1c  cmp     [rsp+0F8h+Reply], 800706B5h
0x180050a24  jz      short loc_180050A30
0x180050a26  cmp     [rsp+0F8h+Reply], 800706BAh
0x180050a2e  jnz     short loc_180050A35
0x180050a30  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180050a35  lea     rcx, [rsp+0F8h+var_A8]; this
0x180050a3a  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x180050a3f  mov     eax, [rsp+0F8h+Reply]
0x180050a43  mov     rcx, [rsp+0F8h+var_18]
0x180050a4b  xor     rcx, rsp; StackCookie
0x180050a4e  call    __security_check_cookie
0x180050a53  lea     r11, [rsp+0F8h+var_8]
0x180050a5b  mov     rsi, [r11+10h]
0x180050a5f  mov     r14, [r11+20h]
0x180050a63  mov     rsp, r11
0x180050a66  pop     r15
0x180050a68  retn
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
