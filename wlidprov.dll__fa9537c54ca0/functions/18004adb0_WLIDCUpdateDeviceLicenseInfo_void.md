# WLIDCUpdateDeviceLicenseInfo(void)

- ea: `0x18004adb0`
- end: `0x18004b0f9`
- name: `?WLIDCUpdateDeviceLicenseInfo@@YAJXZ`
- size: `841`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180035830`

## callees

- `0x18000a400`
- `0x18000f870`
- `0x180010c68`
- `0x180011588`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x18004204c`
- `0x180043240`
- `0x18004adb0`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004ae8b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004ae8b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004af63`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004afb5`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004af63`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004afb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ae9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004afc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ae9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004afc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b032`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b032`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004ae47`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004ae47`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004af87`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004af87`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004aedb`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004aedb`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004afeb`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004afeb`

## string_xrefs

- `0x18004aeb0`: `RPC failed to create new event, hr = %#x`
- `0x18004afff`: `RPC Async complete call failed, hr = %#x`
- `0x18004b04a`: `WLIDCUpdateDeviceLicenseInfo`

## pseudocode

```c
__int64 __fastcall WLIDCUpdateDeviceLicenseInfo(unsigned int a1, unsigned int a2)
{
  __int64 result; // rax
  DWORD v3; // esi
  char v4; // r15
  char v5; // r14
  int LastError; // eax
  const unsigned __int16 *v7; // r9
  unsigned int v8; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v10; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-C8h]
  int Reply; // [rsp+30h] [rbp-B8h] BYREF
  char v13; // [rsp+34h] [rbp-B4h]
  DWORD dwMilliseconds; // [rsp+38h] [rbp-B0h] BYREF
  DWORD v15; // [rsp+3Ch] [rbp-ACh] BYREF
  __int64 v16; // [rsp+40h] [rbp-A8h] BYREF
  HANDLE Handles[3]; // [rsp+48h] [rbp-A0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+60h] [rbp-88h] BYREF

  dwMilliseconds = 0;
  WLIDCGetTimeOutValue(a1, a2, &dwMilliseconds);
  v16 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v16);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v3 = dwMilliseconds;
  v15 = dwMilliseconds;
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
    v8 = 1391;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x43u, 0, &pAsync, v16);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v7 = L"RPC call failed, hr = %#x";
    v8 = 1393;
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
  v10 = WaitForMultipleObjectsEx(1u, Handles, 0, v3, 0);
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
    v8 = 1393;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[29],unsigned long &>("WLIDCUpdateDeviceLicenseInfo", &v15);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x571u,
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
      0x571u,
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
0x18004adb0  mov     [rsp+arg_0], rsi
0x18004adb5  mov     [rsp+arg_8], r14
0x18004adba  push    r15
0x18004adbc  sub     rsp, 0E0h
0x18004adc3  mov     rax, cs:__security_cookie
0x18004adca  xor     rax, rsp
0x18004adcd  mov     [rsp+0E8h+var_18], rax
0x18004add5  mov     [rsp+0E8h+dwMilliseconds], 0
0x18004addd  lea     r8, [rsp+0E8h+dwMilliseconds]; unsigned int *
0x18004ade2  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004ade7  mov     [rsp+0E8h+Reply], 0
0x18004adef  mov     [rsp+0E8h+var_A8], 0
0x18004adf8  lea     rcx, [rsp+0E8h+var_A8]; this
0x18004adfd  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18004ae02  mov     [rsp+0E8h+Reply], eax
0x18004ae06  test    eax, eax
0x18004ae08  js      loc_18004B0D3
0x18004ae0e  xor     edx, edx; Val
0x18004ae10  lea     r8d, [rdx+70h]; Size
0x18004ae14  lea     rcx, [rsp+0E8h+pAsync]; void *
0x18004ae19  call    memset_0
0x18004ae1e  mov     esi, [rsp+0E8h+dwMilliseconds]
0x18004ae22  mov     [rsp+0E8h+dwMilliseconds], esi
0x18004ae26  mov     [rsp+0E8h+var_AC], esi
0x18004ae2a  xor     r15b, r15b
0x18004ae2d  mov     [rsp+0E8h+var_B4], r15b
0x18004ae32  xor     r14b, r14b
0x18004ae35  xorps   xmm0, xmm0
0x18004ae38  movups  xmmword ptr [rsp+0E8h+Handles], xmm0
0x18004ae3d  mov     edx, 70h ; 'p'; Size
0x18004ae42  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x18004ae47  call    cs:__imp_RpcAsyncInitializeHandle
0x18004ae4d  test    eax, eax
0x18004ae4f  jz      short loc_18004AE6D
0x18004ae51  jle     short loc_18004AE5B
0x18004ae53  movzx   eax, ax
0x18004ae56  or      eax, 80070000h
0x18004ae5b  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004ae62  mov     r8d, 56Fh
0x18004ae68  jmp     loc_18004B00C
0x18004ae6d  mov     [rsp+0E8h+pAsync.UserInfo], 0
0x18004ae76  mov     [rsp+0E8h+pAsync.NotificationType], 1
0x18004ae81  xor     r9d, r9d; lpName
0x18004ae84  xor     r8d, r8d; bInitialState
0x18004ae87  xor     edx, edx; bManualReset
0x18004ae89  xor     ecx, ecx; lpEventAttributes
0x18004ae8b  call    cs:__imp_CreateEventW
0x18004ae91  mov     qword ptr [rsp+0E8h+pAsync.u], rax
0x18004ae99  test    rax, rax
0x18004ae9c  jnz     short loc_18004AEB9
0x18004ae9e  call    cs:__imp_GetLastError
0x18004aea4  test    eax, eax
0x18004aea6  jle     short loc_18004AEB0
0x18004aea8  movzx   eax, ax
0x18004aeab  or      eax, 80070000h
0x18004aeb0  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004aeb7  jmp     short loc_18004AE62
0x18004aeb9  mov     [rsp+0E8h+Handles], rax
0x18004aebe  mov     rax, [rsp+0E8h+var_A8]
0x18004aec3  mov     qword ptr [rsp+0E8h+bAlertable], rax
0x18004aec8  lea     r9, [rsp+0E8h+pAsync]
0x18004aecd  xor     r8d, r8d; pReturnValue
0x18004aed0  lea     edx, [r8+43h]; nProcNum
0x18004aed4  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004aedb  call    cs:__imp_Ndr64AsyncClientCall
0x18004aee1  mov     eax, [rsp+0E8h+Reply]
0x18004aee5  jmp     short loc_18004AF36
0x18004aee7  test    eax, eax
0x18004aee9  jle     short loc_18004AEF3
0x18004aeeb  movzx   eax, ax
0x18004aeee  or      eax, 80070000h
0x18004aef3  mov     [rsp+0E8h+Reply], eax
0x18004aef7  mov     [rsp+0E8h+bAlertable], eax
0x18004aefb  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004af02  mov     r8d, 571h; unsigned int
0x18004af08  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004af0f  mov     ecx, 2; unsigned __int8
0x18004af14  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004af19  mov     eax, [rsp+0E8h+Reply]
0x18004af1d  test    eax, eax
0x18004af1f  js      short loc_18004AF2A
0x18004af21  mov     eax, 8000FFFFh
0x18004af26  mov     [rsp+0E8h+Reply], eax
0x18004af2a  mov     esi, [rsp+0E8h+dwMilliseconds]
0x18004af2e  mov     r15b, [rsp+0E8h+var_B4]
0x18004af33  mov     r14b, r15b
0x18004af36  test    eax, eax
0x18004af38  jns     short loc_18004AF4C
0x18004af3a  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004af41  mov     r8d, 571h
0x18004af47  jmp     loc_18004B010
0x18004af4c  mov     [rsp+0E8h+bAlertable], 0; bAlertable
0x18004af54  mov     r9d, esi; dwMilliseconds
0x18004af57  xor     r8d, r8d; bWaitAll
0x18004af5a  lea     rdx, [rsp+0E8h+Handles]; lpHandles
0x18004af5f  lea     ecx, [r8+1]; nCount
0x18004af63  call    cs:__imp_WaitForMultipleObjectsEx
0x18004af69  mov     esi, eax
0x18004af6b  test    r14b, r14b
0x18004af6e  jnz     short loc_18004AFC2
0x18004af70  cmp     esi, 102h
0x18004af76  jz      short loc_18004AF7D
0x18004af78  cmp     esi, 1
0x18004af7b  jnz     short loc_18004AFC2
0x18004af7d  mov     edx, 1; fAbort
0x18004af82  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x18004af87  call    cs:__imp_RpcAsyncCancelCall
0x18004af8d  cmp     esi, 102h
0x18004af93  jnz     short loc_18004AF9A
0x18004af95  mov     r15b, 1
0x18004af98  jmp     short loc_18004AF9D
0x18004af9a  mov     r14b, 1
0x18004af9d  mov     [rsp+0E8h+bAlertable], 0; bAlertable
0x18004afa5  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004afa9  xor     r8d, r8d; bWaitAll
0x18004afac  lea     rdx, [rsp+0E8h+Handles]; lpHandles
0x18004afb1  lea     ecx, [r8+1]; nCount
0x18004afb5  call    cs:__imp_WaitForMultipleObjectsEx
0x18004afbb  mov     esi, eax
0x18004afbd  test    r15b, r15b
0x18004afc0  jz      short loc_18004AF6B
0x18004afc2  test    esi, esi
0x18004afc4  jz      short loc_18004AFE1
0x18004afc6  call    cs:__imp_GetLastError
0x18004afcc  test    eax, eax
0x18004afce  jle     short loc_18004AFD8
0x18004afd0  movzx   eax, ax
0x18004afd3  or      eax, 80070000h
0x18004afd8  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004afdf  jmp     short loc_18004B006
0x18004afe1  lea     rdx, [rsp+0E8h+Reply]; Reply
0x18004afe6  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x18004afeb  call    cs:__imp_RpcAsyncCompleteCall
0x18004aff1  test    eax, eax
0x18004aff3  jz      short loc_18004B025
0x18004aff5  jle     short loc_18004AFFF
0x18004aff7  movzx   eax, ax
0x18004affa  or      eax, 80070000h
0x18004afff  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004b006  mov     r8d, 571h; unsigned int
0x18004b00c  mov     [rsp+0E8h+Reply], eax
0x18004b010  mov     [rsp+0E8h+bAlertable], eax
0x18004b014  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004b01b  mov     ecx, 2; unsigned __int8
0x18004b020  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004b025  mov     rcx, qword ptr [rsp+0E8h+pAsync.u]; hObject
0x18004b02d  test    rcx, rcx
0x18004b030  jz      short loc_18004B038
0x18004b032  call    cs:__imp_CloseHandle
0x18004b038  test    r15b, r15b
0x18004b03b  jz      short loc_18004B07C
0x18004b03d  mov     [rsp+0E8h+Reply], 800705B4h
0x18004b045  lea     rdx, [rsp+0E8h+var_AC]
0x18004b04a  lea     rcx, aWlidcupdatedev; "WLIDCUpdateDeviceLicenseInfo"
0x18004b051  call    ??$RPCCallTimedOut@AEAY0BN@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BN@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[29],ulong &>(char const (&)[29],ulong &)
0x18004b056  mov     eax, [rsp+0E8h+Reply]
0x18004b05a  mov     [rsp+0E8h+bAlertable], eax
0x18004b05e  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004b065  mov     r8d, 571h; unsigned int
0x18004b06b  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004b072  mov     ecx, 2; unsigned __int8
0x18004b077  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004b07c  test    r14b, r14b
0x18004b07f  jz      short loc_18004B0AC
0x18004b081  mov     eax, 800704C7h
0x18004b086  mov     [rsp+0E8h+Reply], eax
0x18004b08a  mov     [rsp+0E8h+bAlertable], eax
0x18004b08e  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004b095  mov     r8d, 571h; unsigned int
0x18004b09b  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004b0a2  mov     ecx, 2; unsigned __int8
0x18004b0a7  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004b0ac  cmp     [rsp+0E8h+Reply], 800706B5h
0x18004b0b4  jz      short loc_18004B0C0
0x18004b0b6  cmp     [rsp+0E8h+Reply], 800706BAh
0x18004b0be  jnz     short loc_18004B0C5
0x18004b0c0  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004b0c5  lea     rcx, [rsp+0E8h+var_A8]; this
0x18004b0ca  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18004b0cf  mov     eax, [rsp+0E8h+Reply]
0x18004b0d3  mov     rcx, [rsp+0E8h+var_18]
0x18004b0db  xor     rcx, rsp; StackCookie
0x18004b0de  call    __security_check_cookie
0x18004b0e3  lea     r11, [rsp+0E8h+var_8]
0x18004b0eb  mov     rsi, [r11+10h]
0x18004b0ef  mov     r14, [r11+18h]
0x18004b0f3  mov     rsp, r11
0x18004b0f6  pop     r15
0x18004b0f8  retn
0x180057041  push    rbp
0x180057043  sub     rsp, 30h
0x180057047  mov     rbp, rdx
0x18005704a  mov     rcx, [rcx]
0x18005704d  mov     ecx, [rcx]; unsigned int
0x18005704f  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x180057054  nop
0x180057055  add     rsp, 30h
0x180057059  pop     rbp
0x18005705a  retn
```
