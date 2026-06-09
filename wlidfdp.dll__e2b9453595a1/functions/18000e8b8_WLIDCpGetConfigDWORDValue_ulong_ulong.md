# WLIDCpGetConfigDWORDValue(ulong,ulong *)

- ea: `0x18000e8b8`
- end: `0x18000ebf6`
- name: `?WLIDCpGetConfigDWORDValue@@YAJKPEAK@Z`
- size: `830`
- prototype: `__int64 __fastcall(__int64, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000e85c`

## callees

- `0x1800027f0`
- `0x1800033b4`
- `0x18000c508`
- `0x18000dc00`
- `0x18000e8b8`
- `0x18000ee14`
- `0x18000efd0`
- `0x18000f4cc`
- `0x18000fe90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000ea67`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000eab9`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000ea67`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000eab9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e983`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e983`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e996`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eaca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e996`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eaca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eb36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eb36`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000eaef`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000eaef`
- `RPCRT4!RpcAsyncCancelCall` at `0x18000ea8b`
- `RPCRT4!RpcAsyncCancelCall` at `0x18000ea8b`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18000e9e0`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18000e9e0`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18000e93c`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18000e93c`

## string_xrefs

- `0x18000e9a8`: `RPC failed to create new event, hr = %#x`
- `0x18000eb03`: `RPC Async complete call failed, hr = %#x`

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
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  BOOL bAlertable[2]; // [rsp+20h] [rbp-D8h]
  int Reply; // [rsp+40h] [rbp-B8h] BYREF
  char v14; // [rsp+44h] [rbp-B4h]
  int v15; // [rsp+48h] [rbp-B0h] BYREF
  __int64 v16; // [rsp+50h] [rbp-A8h] BYREF
  HANDLE Handles[3]; // [rsp+58h] [rbp-A0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-88h] BYREF

  v16 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v16);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v15 = 5000;
  v4 = 0;
  v14 = 0;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x36u, 0, &pAsync, v16, 3, a2);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v7 = L"RPC call failed, hr = %#x";
    v8 = 364;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      (PPTraceStatus *)2,
      (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
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
  NotificationRoutine = pAsync.u.APC.NotificationRoutine;
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v4 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[26],unsigned long &>((__int64)NotificationRoutine, &v15);
    bAlertable[0] = Reply;
    TracePrintW(
      (PPTraceStatus *)2,
      (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x16Cu,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v5 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      (PPTraceStatus *)2,
      (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x16Cu,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v16);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x18000e8b8  mov     [rsp+arg_0], rsi
0x18000e8bd  mov     [rsp+arg_10], r14
0x18000e8c2  push    r15
0x18000e8c4  sub     rsp, 0F0h
0x18000e8cb  mov     rax, cs:__security_cookie
0x18000e8d2  xor     rax, rsp
0x18000e8d5  mov     [rsp+0F8h+var_18], rax
0x18000e8dd  mov     rsi, rdx
0x18000e8e0  mov     [rsp+0F8h+Reply], 0
0x18000e8e8  mov     [rsp+0F8h+var_A8], 0
0x18000e8f1  lea     rcx, [rsp+0F8h+var_A8]; this
0x18000e8f6  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18000e8fb  mov     [rsp+0F8h+Reply], eax
0x18000e8ff  test    eax, eax
0x18000e901  js      loc_18000EBD0
0x18000e907  xor     edx, edx; Val
0x18000e909  lea     r8d, [rdx+70h]; Size
0x18000e90d  lea     rcx, [rsp+0F8h+pAsync]; void *
0x18000e912  call    memset_0
0x18000e917  mov     [rsp+0F8h+var_B0], 1388h
0x18000e91f  xor     r15b, r15b
0x18000e922  mov     [rsp+0F8h+var_B4], r15b
0x18000e927  xor     r14b, r14b
0x18000e92a  xorps   xmm0, xmm0
0x18000e92d  movups  xmmword ptr [rsp+0F8h+Handles], xmm0
0x18000e932  mov     edx, 70h ; 'p'; Size
0x18000e937  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x18000e93c  call    cs:__imp_RpcAsyncInitializeHandle
0x18000e942  test    eax, eax
0x18000e944  jz      short loc_18000E962
0x18000e946  jle     short loc_18000E950
0x18000e948  movzx   eax, ax
0x18000e94b  or      eax, 80070000h
0x18000e950  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18000e957  mov     r8d, 16Ah
0x18000e95d  jmp     loc_18000EB10
0x18000e962  mov     [rsp+0F8h+pAsync.UserInfo], 0
0x18000e96e  mov     [rsp+0F8h+pAsync.NotificationType], 1
0x18000e979  xor     r9d, r9d; lpName
0x18000e97c  xor     r8d, r8d; bInitialState
0x18000e97f  xor     edx, edx; bManualReset
0x18000e981  xor     ecx, ecx; lpEventAttributes
0x18000e983  call    cs:__imp_CreateEventW
0x18000e989  mov     qword ptr [rsp+0F8h+pAsync.u], rax
0x18000e991  test    rax, rax
0x18000e994  jnz     short loc_18000E9B1
0x18000e996  call    cs:__imp_GetLastError
0x18000e99c  test    eax, eax
0x18000e99e  jle     short loc_18000E9A8
0x18000e9a0  movzx   eax, ax
0x18000e9a3  or      eax, 80070000h
0x18000e9a8  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18000e9af  jmp     short loc_18000E957
0x18000e9b1  mov     [rsp+0F8h+Handles], rax
0x18000e9b6  mov     [rsp+0F8h+var_C8], rsi
0x18000e9bb  mov     [rsp+0F8h+var_D0], 3
0x18000e9c3  mov     rax, [rsp+0F8h+var_A8]
0x18000e9c8  mov     qword ptr [rsp+0F8h+bAlertable], rax
0x18000e9cd  lea     r9, [rsp+0F8h+pAsync]
0x18000e9d2  xor     r8d, r8d; pReturnValue
0x18000e9d5  lea     edx, [r8+36h]; nProcNum
0x18000e9d9  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000e9e0  call    cs:__imp_Ndr64AsyncClientCall
0x18000e9e6  mov     eax, [rsp+0F8h+Reply]
0x18000e9ea  jmp     short loc_18000EA37
0x18000e9ec  test    eax, eax
0x18000e9ee  jle     short loc_18000E9F8
0x18000e9f0  movzx   eax, ax
0x18000e9f3  or      eax, 80070000h
0x18000e9f8  mov     [rsp+0F8h+Reply], eax
0x18000e9fc  mov     [rsp+0F8h+bAlertable], eax
0x18000ea00  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18000ea07  mov     r8d, 16Ch; unsigned int
0x18000ea0d  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000ea14  mov     ecx, 2; unsigned __int8
0x18000ea19  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000ea1e  mov     eax, [rsp+0F8h+Reply]
0x18000ea22  test    eax, eax
0x18000ea24  js      short loc_18000EA2F
0x18000ea26  mov     eax, 8000FFFFh
0x18000ea2b  mov     [rsp+0F8h+Reply], eax
0x18000ea2f  mov     r15b, [rsp+0F8h+var_B4]
0x18000ea34  mov     r14b, r15b
0x18000ea37  test    eax, eax
0x18000ea39  jns     short loc_18000EA4D
0x18000ea3b  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18000ea42  mov     r8d, 16Ch
0x18000ea48  jmp     loc_18000EB14
0x18000ea4d  mov     [rsp+0F8h+bAlertable], 0; bAlertable
0x18000ea55  mov     r9d, 1388h; dwMilliseconds
0x18000ea5b  xor     r8d, r8d; bWaitAll
0x18000ea5e  lea     rdx, [rsp+0F8h+Handles]; lpHandles
0x18000ea63  lea     ecx, [r8+1]; nCount
0x18000ea67  call    cs:__imp_WaitForMultipleObjectsEx
0x18000ea6d  mov     esi, eax
0x18000ea6f  test    r14b, r14b
0x18000ea72  jnz     short loc_18000EAC6
0x18000ea74  cmp     esi, 102h
0x18000ea7a  jz      short loc_18000EA81
0x18000ea7c  cmp     esi, 1
0x18000ea7f  jnz     short loc_18000EAC6
0x18000ea81  mov     edx, 1; fAbort
0x18000ea86  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x18000ea8b  call    cs:__imp_RpcAsyncCancelCall
0x18000ea91  cmp     esi, 102h
0x18000ea97  jnz     short loc_18000EA9E
0x18000ea99  mov     r15b, 1
0x18000ea9c  jmp     short loc_18000EAA1
0x18000ea9e  mov     r14b, 1
0x18000eaa1  mov     [rsp+0F8h+bAlertable], 0; bAlertable
0x18000eaa9  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18000eaad  xor     r8d, r8d; bWaitAll
0x18000eab0  lea     rdx, [rsp+0F8h+Handles]; lpHandles
0x18000eab5  lea     ecx, [r8+1]; nCount
0x18000eab9  call    cs:__imp_WaitForMultipleObjectsEx
0x18000eabf  mov     esi, eax
0x18000eac1  test    r15b, r15b
0x18000eac4  jz      short loc_18000EA6F
0x18000eac6  test    esi, esi
0x18000eac8  jz      short loc_18000EAE5
0x18000eaca  call    cs:__imp_GetLastError
0x18000ead0  test    eax, eax
0x18000ead2  jle     short loc_18000EADC
0x18000ead4  movzx   eax, ax
0x18000ead7  or      eax, 80070000h
0x18000eadc  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18000eae3  jmp     short loc_18000EB0A
0x18000eae5  lea     rdx, [rsp+0F8h+Reply]; Reply
0x18000eaea  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x18000eaef  call    cs:__imp_RpcAsyncCompleteCall
0x18000eaf5  test    eax, eax
0x18000eaf7  jz      short loc_18000EB29
0x18000eaf9  jle     short loc_18000EB03
0x18000eafb  movzx   eax, ax
0x18000eafe  or      eax, 80070000h
0x18000eb03  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18000eb0a  mov     r8d, 16Ch; unsigned int
0x18000eb10  mov     [rsp+0F8h+Reply], eax
0x18000eb14  mov     [rsp+0F8h+bAlertable], eax
0x18000eb18  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000eb1f  mov     ecx, 2; unsigned __int8
0x18000eb24  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000eb29  mov     rcx, qword ptr [rsp+0F8h+pAsync.u]; hObject
0x18000eb31  test    rcx, rcx
0x18000eb34  jz      short loc_18000EB3C
0x18000eb36  call    cs:__imp_CloseHandle
0x18000eb3c  test    r15b, r15b
0x18000eb3f  jz      short loc_18000EB79
0x18000eb41  mov     [rsp+0F8h+Reply], 800705B4h
0x18000eb49  lea     rdx, [rsp+0F8h+var_B0]
0x18000eb4e  call    ??$RPCCallTimedOut@AEAY0BK@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BK@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[26],ulong &>(char const (&)[26],ulong &)
0x18000eb53  mov     eax, [rsp+0F8h+Reply]
0x18000eb57  mov     [rsp+0F8h+bAlertable], eax
0x18000eb5b  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18000eb62  mov     r8d, 16Ch; unsigned int
0x18000eb68  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000eb6f  mov     ecx, 2; unsigned __int8
0x18000eb74  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000eb79  test    r14b, r14b
0x18000eb7c  jz      short loc_18000EBA9
0x18000eb7e  mov     eax, 800704C7h
0x18000eb83  mov     [rsp+0F8h+Reply], eax
0x18000eb87  mov     [rsp+0F8h+bAlertable], eax
0x18000eb8b  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18000eb92  mov     r8d, 16Ch; unsigned int
0x18000eb98  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000eb9f  mov     ecx, 2; unsigned __int8
0x18000eba4  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000eba9  cmp     [rsp+0F8h+Reply], 800706B5h
0x18000ebb1  jz      short loc_18000EBBD
0x18000ebb3  cmp     [rsp+0F8h+Reply], 800706BAh
0x18000ebbb  jnz     short loc_18000EBC2
0x18000ebbd  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18000ebc2  lea     rcx, [rsp+0F8h+var_A8]; this
0x18000ebc7  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18000ebcc  mov     eax, [rsp+0F8h+Reply]
0x18000ebd0  mov     rcx, [rsp+0F8h+var_18]
0x18000ebd8  xor     rcx, rsp; StackCookie
0x18000ebdb  call    __security_check_cookie
0x18000ebe0  lea     r11, [rsp+0F8h+var_8]
0x18000ebe8  mov     rsi, [r11+10h]
0x18000ebec  mov     r14, [r11+20h]
0x18000ebf0  mov     rsp, r11
0x18000ebf3  pop     r15
0x18000ebf5  retn
0x180011363  push    rbp
0x180011365  sub     rsp, 40h
0x180011369  mov     rbp, rdx
0x18001136c  mov     rcx, [rcx]
0x18001136f  mov     ecx, [rcx]; unsigned int
0x180011371  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x180011376  nop
0x180011377  add     rsp, 40h
0x18001137b  pop     rbp
0x18001137c  retn
```
