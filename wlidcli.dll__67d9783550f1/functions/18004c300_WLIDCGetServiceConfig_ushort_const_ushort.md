# WLIDCGetServiceConfig(ushort const *,ushort * *)

- ea: `0x18004c300`
- end: `0x18004c664`
- name: `?WLIDCGetServiceConfig@@YAJPEBGPEAPEAG@Z`
- size: `868`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001db9c`
- `0x180030310`
- `0x18003799c`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180045050`
- `0x180046ce0`
- `0x18004c300`
- `0x18004cd04`
- `0x180050c84`
- `0x180050e40`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004c4ca`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004c51c`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004c4ca`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004c51c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004c3e8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004c3e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c3fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c52d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c3fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c52d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c599`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c599`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004c4f1`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004c4f1`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004c442`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004c442`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004c552`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004c552`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004c3a1`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004c3a1`

## string_xrefs

- `0x18004c40d`: `RPC failed to create new event, hr = %#x`
- `0x18004c566`: `RPC Async complete call failed, hr = %#x`
- `0x18004c5b1`: `WLIDCGetServiceConfig`

## pseudocode

```c
__int64 __fastcall WLIDCGetServiceConfig(const unsigned __int16 *a1, unsigned __int16 **a2)
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
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
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
    v10 = 648;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0xEu, 0, &pAsync, v18, a1, a2);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v9 = L"RPC call failed, hr = %#x";
    v10 = 650;
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
    v10 = 650;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[22],unsigned long &>(
      (__int64)"WLIDCGetServiceConfig",
      (int *)&v17);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x28Au,
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
      0x28Au,
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
0x18004c300  mov     [rsp+arg_10], rsi
0x18004c305  mov     [rsp+arg_18], r12
0x18004c30a  push    r13
0x18004c30c  push    r14
0x18004c30e  push    r15
0x18004c310  sub     rsp, 0F0h
0x18004c317  mov     rax, cs:__security_cookie
0x18004c31e  xor     rax, rsp
0x18004c321  mov     [rsp+108h+var_28], rax
0x18004c329  mov     r13, rdx
0x18004c32c  mov     r12, rcx
0x18004c32f  mov     [rsp+108h+dwMilliseconds], 0
0x18004c337  lea     r8, [rsp+108h+dwMilliseconds]; unsigned int *
0x18004c33c  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004c341  mov     [rsp+108h+Reply], 0
0x18004c349  mov     [rsp+108h+var_B8], 0
0x18004c352  lea     rcx, [rsp+108h+var_B8]; this
0x18004c357  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18004c35c  mov     [rsp+108h+Reply], eax
0x18004c360  test    eax, eax
0x18004c362  js      loc_18004C63A
0x18004c368  xor     edx, edx; Val
0x18004c36a  lea     r8d, [rdx+70h]; Size
0x18004c36e  lea     rcx, [rsp+108h+pAsync]; void *
0x18004c373  call    memset_0
0x18004c378  mov     esi, [rsp+108h+dwMilliseconds]
0x18004c37c  mov     [rsp+108h+dwMilliseconds], esi
0x18004c380  mov     [rsp+108h+var_BC], esi
0x18004c384  xor     r15b, r15b
0x18004c387  mov     [rsp+108h+var_C4], r15b
0x18004c38c  xor     r14b, r14b
0x18004c38f  xorps   xmm0, xmm0
0x18004c392  movups  xmmword ptr [rsp+108h+Handles], xmm0
0x18004c397  mov     edx, 70h ; 'p'; Size
0x18004c39c  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004c3a1  call    cs:__imp_RpcAsyncInitializeHandle
0x18004c3a7  test    eax, eax
0x18004c3a9  jz      short loc_18004C3C7
0x18004c3ab  jle     short loc_18004C3B5
0x18004c3ad  movzx   eax, ax
0x18004c3b0  or      eax, 80070000h
0x18004c3b5  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004c3bc  mov     r8d, 288h
0x18004c3c2  jmp     loc_18004C573
0x18004c3c7  mov     [rsp+108h+pAsync.UserInfo], 0
0x18004c3d3  mov     [rsp+108h+pAsync.NotificationType], 1
0x18004c3de  xor     r9d, r9d; lpName
0x18004c3e1  xor     r8d, r8d; bInitialState
0x18004c3e4  xor     edx, edx; bManualReset
0x18004c3e6  xor     ecx, ecx; lpEventAttributes
0x18004c3e8  call    cs:__imp_CreateEventW
0x18004c3ee  mov     qword ptr [rsp+108h+pAsync.u], rax
0x18004c3f6  test    rax, rax
0x18004c3f9  jnz     short loc_18004C416
0x18004c3fb  call    cs:__imp_GetLastError
0x18004c401  test    eax, eax
0x18004c403  jle     short loc_18004C40D
0x18004c405  movzx   eax, ax
0x18004c408  or      eax, 80070000h
0x18004c40d  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004c414  jmp     short loc_18004C3BC
0x18004c416  mov     [rsp+108h+Handles], rax
0x18004c41b  mov     [rsp+108h+var_D8], r13
0x18004c420  mov     [rsp+108h+var_E0], r12
0x18004c425  mov     rax, [rsp+108h+var_B8]
0x18004c42a  mov     qword ptr [rsp+108h+bAlertable], rax
0x18004c42f  lea     r9, [rsp+108h+pAsync]
0x18004c434  xor     r8d, r8d; pReturnValue
0x18004c437  lea     edx, [r8+0Eh]; nProcNum
0x18004c43b  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004c442  call    cs:__imp_Ndr64AsyncClientCall
0x18004c448  mov     eax, [rsp+108h+Reply]
0x18004c44c  jmp     short loc_18004C49D
0x18004c44e  test    eax, eax
0x18004c450  jle     short loc_18004C45A
0x18004c452  movzx   eax, ax
0x18004c455  or      eax, 80070000h
0x18004c45a  mov     [rsp+108h+Reply], eax
0x18004c45e  mov     [rsp+108h+bAlertable], eax
0x18004c462  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004c469  mov     r8d, 28Ah; unsigned int
0x18004c46f  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004c476  mov     ecx, 2; unsigned __int8
0x18004c47b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004c480  mov     eax, [rsp+108h+Reply]
0x18004c484  test    eax, eax
0x18004c486  js      short loc_18004C491
0x18004c488  mov     eax, 8000FFFFh
0x18004c48d  mov     [rsp+108h+Reply], eax
0x18004c491  mov     esi, [rsp+108h+dwMilliseconds]
0x18004c495  mov     r15b, [rsp+108h+var_C4]
0x18004c49a  mov     r14b, r15b
0x18004c49d  test    eax, eax
0x18004c49f  jns     short loc_18004C4B3
0x18004c4a1  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004c4a8  mov     r8d, 28Ah
0x18004c4ae  jmp     loc_18004C577
0x18004c4b3  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18004c4bb  mov     r9d, esi; dwMilliseconds
0x18004c4be  xor     r8d, r8d; bWaitAll
0x18004c4c1  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18004c4c6  lea     ecx, [r8+1]; nCount
0x18004c4ca  call    cs:__imp_WaitForMultipleObjectsEx
0x18004c4d0  mov     esi, eax
0x18004c4d2  mov     r12d, 102h
0x18004c4d8  test    r14b, r14b
0x18004c4db  jnz     short loc_18004C529
0x18004c4dd  cmp     esi, r12d
0x18004c4e0  jz      short loc_18004C4E7
0x18004c4e2  cmp     esi, 1
0x18004c4e5  jnz     short loc_18004C529
0x18004c4e7  mov     edx, 1; fAbort
0x18004c4ec  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004c4f1  call    cs:__imp_RpcAsyncCancelCall
0x18004c4f7  cmp     esi, r12d
0x18004c4fa  jnz     short loc_18004C501
0x18004c4fc  mov     r15b, 1
0x18004c4ff  jmp     short loc_18004C504
0x18004c501  mov     r14b, 1
0x18004c504  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18004c50c  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004c510  xor     r8d, r8d; bWaitAll
0x18004c513  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18004c518  lea     ecx, [r8+1]; nCount
0x18004c51c  call    cs:__imp_WaitForMultipleObjectsEx
0x18004c522  mov     esi, eax
0x18004c524  test    r15b, r15b
0x18004c527  jz      short loc_18004C4D8
0x18004c529  test    esi, esi
0x18004c52b  jz      short loc_18004C548
0x18004c52d  call    cs:__imp_GetLastError
0x18004c533  test    eax, eax
0x18004c535  jle     short loc_18004C53F
0x18004c537  movzx   eax, ax
0x18004c53a  or      eax, 80070000h
0x18004c53f  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004c546  jmp     short loc_18004C56D
0x18004c548  lea     rdx, [rsp+108h+Reply]; Reply
0x18004c54d  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004c552  call    cs:__imp_RpcAsyncCompleteCall
0x18004c558  test    eax, eax
0x18004c55a  jz      short loc_18004C58C
0x18004c55c  jle     short loc_18004C566
0x18004c55e  movzx   eax, ax
0x18004c561  or      eax, 80070000h
0x18004c566  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004c56d  mov     r8d, 28Ah; unsigned int
0x18004c573  mov     [rsp+108h+Reply], eax
0x18004c577  mov     [rsp+108h+bAlertable], eax
0x18004c57b  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004c582  mov     ecx, 2; unsigned __int8
0x18004c587  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004c58c  mov     rcx, qword ptr [rsp+108h+pAsync.u]; hObject
0x18004c594  test    rcx, rcx
0x18004c597  jz      short loc_18004C59F
0x18004c599  call    cs:__imp_CloseHandle
0x18004c59f  test    r15b, r15b
0x18004c5a2  jz      short loc_18004C5E3
0x18004c5a4  mov     [rsp+108h+Reply], 800705B4h
0x18004c5ac  lea     rdx, [rsp+108h+var_BC]
0x18004c5b1  lea     rcx, aWlidcgetservic; "WLIDCGetServiceConfig"
0x18004c5b8  call    ??$RPCCallTimedOut@AEAY0BG@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BG@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[22],ulong &>(char const (&)[22],ulong &)
0x18004c5bd  mov     eax, [rsp+108h+Reply]
0x18004c5c1  mov     [rsp+108h+bAlertable], eax
0x18004c5c5  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004c5cc  mov     r8d, 28Ah; unsigned int
0x18004c5d2  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004c5d9  mov     ecx, 2; unsigned __int8
0x18004c5de  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004c5e3  test    r14b, r14b
0x18004c5e6  jz      short loc_18004C613
0x18004c5e8  mov     eax, 800704C7h
0x18004c5ed  mov     [rsp+108h+Reply], eax
0x18004c5f1  mov     [rsp+108h+bAlertable], eax
0x18004c5f5  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004c5fc  mov     r8d, 28Ah; unsigned int
0x18004c602  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004c609  mov     ecx, 2; unsigned __int8
0x18004c60e  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004c613  cmp     [rsp+108h+Reply], 800706B5h
0x18004c61b  jz      short loc_18004C627
0x18004c61d  cmp     [rsp+108h+Reply], 800706BAh
0x18004c625  jnz     short loc_18004C62C
0x18004c627  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004c62c  lea     rcx, [rsp+108h+var_B8]; this
0x18004c631  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18004c636  mov     eax, [rsp+108h+Reply]
0x18004c63a  mov     rcx, [rsp+108h+var_28]
0x18004c642  xor     rcx, rsp; StackCookie
0x18004c645  call    __security_check_cookie
0x18004c64a  lea     r11, [rsp+108h+var_18]
0x18004c652  mov     rsi, [r11+30h]
0x18004c656  mov     r12, [r11+38h]
0x18004c65a  mov     rsp, r11
0x18004c65d  pop     r15
0x18004c65f  pop     r14
0x18004c661  pop     r13
0x18004c663  retn
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
