# WLIDCGetIdName(void * const,ushort * *)

- ea: `0x18004b8cc`
- end: `0x18004bbee`
- name: `?WLIDCGetIdName@@YAJQEAXPEAPEAG@Z`
- size: `802`
- prototype: `__int64 __fastcall(void *const, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000bf58`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x1800456cc`
- `0x180046ce0`
- `0x18004b8cc`
- `0x18004cd04`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004ba67`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004bab9`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004ba67`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004bab9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004b98f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004b98f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b9a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004baca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b9a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004baca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004bb36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004bb36`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004ba8e`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004ba8e`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004b9df`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004b9df`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004baef`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004baef`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004b94e`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004b94e`

## string_xrefs

- `0x18004b9b4`: `RPC failed to create new event, hr = %#x`
- `0x18004bb03`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCGetIdName(void *const a1, unsigned __int16 **a2)
{
  DWORD v4; // esi
  char v5; // r15
  char v6; // r14
  int LastError; // eax
  const unsigned __int16 *v8; // r9
  unsigned int v9; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v11; // esi
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-C8h]
  unsigned int Reply; // [rsp+30h] [rbp-B8h] BYREF
  char v16; // [rsp+34h] [rbp-B4h]
  DWORD dwMilliseconds; // [rsp+38h] [rbp-B0h] BYREF
  DWORD v18; // [rsp+3Ch] [rbp-ACh] BYREF
  HANDLE Handles[2]; // [rsp+40h] [rbp-A8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+50h] [rbp-98h] BYREF

  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v4 = dwMilliseconds;
  v18 = dwMilliseconds;
  v5 = 0;
  v16 = 0;
  v6 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v9 = 1072;
    goto LABEL_27;
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
    goto LABEL_5;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x35u, 0, &pAsync, a1, a2);
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
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_28;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = L"RPC Async complete call failed, hr = %#x";
  }
  v9 = 1074;
LABEL_27:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(2u, "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp", v9, v8, *(_QWORD *)bAlertable);
LABEL_28:
  NotificationRoutine = pAsync.u.APC.NotificationRoutine;
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v5 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[15],unsigned long &>(
      (__int64)NotificationRoutine,
      (int *)&v18);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x432u,
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
      0x432u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  result = Reply;
  if ( Reply == -2147023179 || Reply == -2147023174 )
  {
    TraceServiceStatus();
    return Reply;
  }
  return result;
}

```

## disassembly

```asm
0x18004b8cc  mov     [rsp+arg_10], rsi
0x18004b8d1  mov     [rsp+arg_18], r12
0x18004b8d6  push    r13
0x18004b8d8  push    r14
0x18004b8da  push    r15
0x18004b8dc  sub     rsp, 0D0h
0x18004b8e3  mov     rax, cs:__security_cookie
0x18004b8ea  xor     rax, rsp
0x18004b8ed  mov     [rsp+0E8h+var_28], rax
0x18004b8f5  mov     r13, rdx
0x18004b8f8  mov     r12, rcx
0x18004b8fb  mov     [rsp+0E8h+Reply], 0
0x18004b903  mov     [rsp+0E8h+dwMilliseconds], 0
0x18004b90b  lea     r8, [rsp+0E8h+dwMilliseconds]; unsigned int *
0x18004b910  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004b915  xor     edx, edx; Val
0x18004b917  lea     r8d, [rdx+70h]; Size
0x18004b91b  lea     rcx, [rsp+0E8h+pAsync]; void *
0x18004b920  call    memset_0
0x18004b925  mov     esi, [rsp+0E8h+dwMilliseconds]
0x18004b929  mov     [rsp+0E8h+dwMilliseconds], esi
0x18004b92d  mov     [rsp+0E8h+var_AC], esi
0x18004b931  xor     r15b, r15b
0x18004b934  mov     [rsp+0E8h+var_B4], r15b
0x18004b939  xor     r14b, r14b
0x18004b93c  xorps   xmm0, xmm0
0x18004b93f  movups  xmmword ptr [rsp+0E8h+Handles], xmm0
0x18004b944  mov     edx, 70h ; 'p'; Size
0x18004b949  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x18004b94e  call    cs:__imp_RpcAsyncInitializeHandle
0x18004b954  test    eax, eax
0x18004b956  jz      short loc_18004B974
0x18004b958  jle     short loc_18004B962
0x18004b95a  movzx   eax, ax
0x18004b95d  or      eax, 80070000h
0x18004b962  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004b969  mov     r8d, 430h
0x18004b96f  jmp     loc_18004BB10
0x18004b974  mov     [rsp+0E8h+pAsync.UserInfo], 0
0x18004b97d  mov     [rsp+0E8h+pAsync.NotificationType], 1
0x18004b985  xor     r9d, r9d; lpName
0x18004b988  xor     r8d, r8d; bInitialState
0x18004b98b  xor     edx, edx; bManualReset
0x18004b98d  xor     ecx, ecx; lpEventAttributes
0x18004b98f  call    cs:__imp_CreateEventW
0x18004b995  mov     qword ptr [rsp+0E8h+pAsync.u], rax
0x18004b99d  test    rax, rax
0x18004b9a0  jnz     short loc_18004B9BD
0x18004b9a2  call    cs:__imp_GetLastError
0x18004b9a8  test    eax, eax
0x18004b9aa  jle     short loc_18004B9B4
0x18004b9ac  movzx   eax, ax
0x18004b9af  or      eax, 80070000h
0x18004b9b4  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004b9bb  jmp     short loc_18004B969
0x18004b9bd  mov     [rsp+0E8h+Handles], rax
0x18004b9c2  mov     [rsp+0E8h+var_C0], r13
0x18004b9c7  mov     qword ptr [rsp+0E8h+bAlertable], r12
0x18004b9cc  lea     r9, [rsp+0E8h+pAsync]
0x18004b9d1  xor     r8d, r8d; pReturnValue
0x18004b9d4  lea     edx, [r8+35h]; nProcNum
0x18004b9d8  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004b9df  call    cs:__imp_Ndr64AsyncClientCall
0x18004b9e5  mov     eax, [rsp+0E8h+Reply]
0x18004b9e9  jmp     short loc_18004BA3A
0x18004b9eb  test    eax, eax
0x18004b9ed  jle     short loc_18004B9F7
0x18004b9ef  movzx   eax, ax
0x18004b9f2  or      eax, 80070000h
0x18004b9f7  mov     [rsp+0E8h+Reply], eax
0x18004b9fb  mov     [rsp+0E8h+bAlertable], eax
0x18004b9ff  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004ba06  mov     r8d, 432h; unsigned int
0x18004ba0c  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004ba13  mov     ecx, 2; unsigned __int8
0x18004ba18  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004ba1d  mov     eax, [rsp+0E8h+Reply]
0x18004ba21  test    eax, eax
0x18004ba23  js      short loc_18004BA2E
0x18004ba25  mov     eax, 8000FFFFh
0x18004ba2a  mov     [rsp+0E8h+Reply], eax
0x18004ba2e  mov     esi, [rsp+0E8h+dwMilliseconds]
0x18004ba32  mov     r15b, [rsp+0E8h+var_B4]
0x18004ba37  mov     r14b, r15b
0x18004ba3a  test    eax, eax
0x18004ba3c  jns     short loc_18004BA50
0x18004ba3e  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004ba45  mov     r8d, 432h
0x18004ba4b  jmp     loc_18004BB14
0x18004ba50  mov     [rsp+0E8h+bAlertable], 0; bAlertable
0x18004ba58  mov     r9d, esi; dwMilliseconds
0x18004ba5b  xor     r8d, r8d; bWaitAll
0x18004ba5e  lea     rdx, [rsp+0E8h+Handles]; lpHandles
0x18004ba63  lea     ecx, [r8+1]; nCount
0x18004ba67  call    cs:__imp_WaitForMultipleObjectsEx
0x18004ba6d  mov     esi, eax
0x18004ba6f  mov     r12d, 102h
0x18004ba75  test    r14b, r14b
0x18004ba78  jnz     short loc_18004BAC6
0x18004ba7a  cmp     esi, r12d
0x18004ba7d  jz      short loc_18004BA84
0x18004ba7f  cmp     esi, 1
0x18004ba82  jnz     short loc_18004BAC6
0x18004ba84  mov     edx, 1; fAbort
0x18004ba89  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x18004ba8e  call    cs:__imp_RpcAsyncCancelCall
0x18004ba94  cmp     esi, r12d
0x18004ba97  jnz     short loc_18004BA9E
0x18004ba99  mov     r15b, 1
0x18004ba9c  jmp     short loc_18004BAA1
0x18004ba9e  mov     r14b, 1
0x18004baa1  mov     [rsp+0E8h+bAlertable], 0; bAlertable
0x18004baa9  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004baad  xor     r8d, r8d; bWaitAll
0x18004bab0  lea     rdx, [rsp+0E8h+Handles]; lpHandles
0x18004bab5  lea     ecx, [r8+1]; nCount
0x18004bab9  call    cs:__imp_WaitForMultipleObjectsEx
0x18004babf  mov     esi, eax
0x18004bac1  test    r15b, r15b
0x18004bac4  jz      short loc_18004BA75
0x18004bac6  test    esi, esi
0x18004bac8  jz      short loc_18004BAE5
0x18004baca  call    cs:__imp_GetLastError
0x18004bad0  test    eax, eax
0x18004bad2  jle     short loc_18004BADC
0x18004bad4  movzx   eax, ax
0x18004bad7  or      eax, 80070000h
0x18004badc  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004bae3  jmp     short loc_18004BB0A
0x18004bae5  lea     rdx, [rsp+0E8h+Reply]; Reply
0x18004baea  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x18004baef  call    cs:__imp_RpcAsyncCompleteCall
0x18004baf5  test    eax, eax
0x18004baf7  jz      short loc_18004BB29
0x18004baf9  jle     short loc_18004BB03
0x18004bafb  movzx   eax, ax
0x18004bafe  or      eax, 80070000h
0x18004bb03  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004bb0a  mov     r8d, 432h; unsigned int
0x18004bb10  mov     [rsp+0E8h+Reply], eax
0x18004bb14  mov     [rsp+0E8h+bAlertable], eax
0x18004bb18  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004bb1f  mov     ecx, 2; unsigned __int8
0x18004bb24  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004bb29  mov     rcx, qword ptr [rsp+0E8h+pAsync.u]; hObject
0x18004bb31  test    rcx, rcx
0x18004bb34  jz      short loc_18004BB3C
0x18004bb36  call    cs:__imp_CloseHandle
0x18004bb3c  test    r15b, r15b
0x18004bb3f  jz      short loc_18004BB79
0x18004bb41  mov     [rsp+0E8h+Reply], 800705B4h
0x18004bb49  lea     rdx, [rsp+0E8h+var_AC]
0x18004bb4e  call    ??$RPCCallTimedOut@AEAY0P@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0P@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[15],ulong &>(char const (&)[15],ulong &)
0x18004bb53  mov     eax, [rsp+0E8h+Reply]
0x18004bb57  mov     [rsp+0E8h+bAlertable], eax
0x18004bb5b  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004bb62  mov     r8d, 432h; unsigned int
0x18004bb68  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004bb6f  mov     ecx, 2; unsigned __int8
0x18004bb74  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004bb79  test    r14b, r14b
0x18004bb7c  jz      short loc_18004BBA9
0x18004bb7e  mov     eax, 800704C7h
0x18004bb83  mov     [rsp+0E8h+Reply], eax
0x18004bb87  mov     [rsp+0E8h+bAlertable], eax
0x18004bb8b  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004bb92  mov     r8d, 432h; unsigned int
0x18004bb98  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004bb9f  mov     ecx, 2; unsigned __int8
0x18004bba4  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004bba9  mov     eax, [rsp+0E8h+Reply]
0x18004bbad  cmp     eax, 800706B5h
0x18004bbb2  jz      short loc_18004BBBB
0x18004bbb4  cmp     eax, 800706BAh
0x18004bbb9  jnz     short loc_18004BBC4
0x18004bbbb  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004bbc0  mov     eax, [rsp+0E8h+Reply]
0x18004bbc4  mov     rcx, [rsp+0E8h+var_28]
0x18004bbcc  xor     rcx, rsp; StackCookie
0x18004bbcf  call    __security_check_cookie
0x18004bbd4  lea     r11, [rsp+0E8h+var_18]
0x18004bbdc  mov     rsi, [r11+30h]
0x18004bbe0  mov     r12, [r11+38h]
0x18004bbe4  mov     rsp, r11
0x18004bbe7  pop     r15
0x18004bbe9  pop     r14
0x18004bbeb  pop     r13
0x18004bbed  retn
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
