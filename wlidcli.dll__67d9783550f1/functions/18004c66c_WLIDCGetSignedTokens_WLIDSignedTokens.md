# WLIDCGetSignedTokens(_WLIDSignedTokens * *)

- ea: `0x18004c66c`
- end: `0x18004c9b2`
- name: `?WLIDCGetSignedTokens@@YAJPEAPEAU_WLIDSignedTokens@@@Z`
- size: `838`
- prototype: `__int64 __fastcall(struct _WLIDSignedTokens **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800306c0`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180044fc4`
- `0x180046ce0`
- `0x18004c66c`
- `0x18004cd04`
- `0x180050c84`
- `0x180050e40`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004c823`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004c875`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004c823`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004c875`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004c746`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004c746`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c759`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c886`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c759`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c886`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c8f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c8f2`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004c84a`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004c84a`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004c79b`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004c79b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004c8ab`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004c8ab`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004c702`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004c702`

## string_xrefs

- `0x18004c76b`: `RPC failed to create new event, hr = %#x`
- `0x18004c8bf`: `RPC Async complete call failed, hr = %#x`
- `0x18004c90a`: `WLIDCGetSignedTokens`

## pseudocode

```c
__int64 __fastcall WLIDCGetSignedTokens(struct _WLIDSignedTokens **a1, unsigned int a2)
{
  __int64 result; // rax
  DWORD v4; // esi
  char v5; // r15
  char v6; // r14
  int LastError; // eax
  const unsigned __int16 *v8; // r9
  unsigned int v9; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v11; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-E8h]
  int Reply; // [rsp+30h] [rbp-D8h] BYREF
  char v14; // [rsp+34h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+38h] [rbp-D0h] BYREF
  DWORD v16; // [rsp+3Ch] [rbp-CCh] BYREF
  __int64 v17; // [rsp+40h] [rbp-C8h] BYREF
  HANDLE Handles[3]; // [rsp+48h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+60h] [rbp-A8h] BYREF

  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  v17 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v17);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v4 = dwMilliseconds;
  v16 = dwMilliseconds;
  v5 = 0;
  v14 = 0;
  v6 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v9 = 1345;
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
    v8 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x3Fu, 0, &pAsync, v17, a1);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v8 = L"RPC call failed, hr = %#x";
    v9 = 1347;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v9,
      v8,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
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
LABEL_29:
    v9 = 1347;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v5 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],unsigned long &>(
      (__int64)"WLIDCGetSignedTokens",
      (int *)&v16);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x543u,
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
      0x543u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v17);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x18004c66c  push    rsi
0x18004c66e  push    r12
0x18004c670  push    r14
0x18004c672  push    r15
0x18004c674  sub     rsp, 0E8h
0x18004c67b  mov     rax, cs:__security_cookie
0x18004c682  xor     rax, rsp
0x18004c685  mov     [rsp+108h+var_38], rax
0x18004c68d  mov     r12, rcx
0x18004c690  mov     [rsp+108h+dwMilliseconds], 0
0x18004c698  lea     r8, [rsp+108h+dwMilliseconds]; unsigned int *
0x18004c69d  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004c6a2  mov     [rsp+108h+Reply], 0
0x18004c6aa  mov     [rsp+108h+var_C8], 0
0x18004c6b3  lea     rcx, [rsp+108h+var_C8]; this
0x18004c6b8  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18004c6bd  mov     [rsp+108h+Reply], eax
0x18004c6c1  test    eax, eax
0x18004c6c3  js      loc_18004C993
0x18004c6c9  xor     edx, edx; Val
0x18004c6cb  lea     r8d, [rdx+70h]; Size
0x18004c6cf  lea     rcx, [rsp+108h+pAsync]; void *
0x18004c6d4  call    memset_0
0x18004c6d9  mov     esi, [rsp+108h+dwMilliseconds]
0x18004c6dd  mov     [rsp+108h+dwMilliseconds], esi
0x18004c6e1  mov     [rsp+108h+var_CC], esi
0x18004c6e5  xor     r15b, r15b
0x18004c6e8  mov     [rsp+108h+var_D4], r15b
0x18004c6ed  xor     r14b, r14b
0x18004c6f0  xorps   xmm0, xmm0
0x18004c6f3  movups  xmmword ptr [rsp+108h+Handles], xmm0
0x18004c6f8  mov     edx, 70h ; 'p'; Size
0x18004c6fd  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004c702  call    cs:__imp_RpcAsyncInitializeHandle
0x18004c708  test    eax, eax
0x18004c70a  jz      short loc_18004C728
0x18004c70c  jle     short loc_18004C716
0x18004c70e  movzx   eax, ax
0x18004c711  or      eax, 80070000h
0x18004c716  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004c71d  mov     r8d, 541h
0x18004c723  jmp     loc_18004C8CC
0x18004c728  mov     [rsp+108h+pAsync.UserInfo], 0
0x18004c731  mov     [rsp+108h+pAsync.NotificationType], 1
0x18004c73c  xor     r9d, r9d; lpName
0x18004c73f  xor     r8d, r8d; bInitialState
0x18004c742  xor     edx, edx; bManualReset
0x18004c744  xor     ecx, ecx; lpEventAttributes
0x18004c746  call    cs:__imp_CreateEventW
0x18004c74c  mov     qword ptr [rsp+108h+pAsync.u], rax
0x18004c754  test    rax, rax
0x18004c757  jnz     short loc_18004C774
0x18004c759  call    cs:__imp_GetLastError
0x18004c75f  test    eax, eax
0x18004c761  jle     short loc_18004C76B
0x18004c763  movzx   eax, ax
0x18004c766  or      eax, 80070000h
0x18004c76b  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004c772  jmp     short loc_18004C71D
0x18004c774  mov     [rsp+108h+Handles], rax
0x18004c779  mov     [rsp+108h+var_E0], r12
0x18004c77e  mov     rax, [rsp+108h+var_C8]
0x18004c783  mov     qword ptr [rsp+108h+bAlertable], rax
0x18004c788  lea     r9, [rsp+108h+pAsync]
0x18004c78d  xor     r8d, r8d; pReturnValue
0x18004c790  lea     edx, [r8+3Fh]; nProcNum
0x18004c794  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004c79b  call    cs:__imp_Ndr64AsyncClientCall
0x18004c7a1  mov     eax, [rsp+108h+Reply]
0x18004c7a5  jmp     short loc_18004C7F6
0x18004c7a7  test    eax, eax
0x18004c7a9  jle     short loc_18004C7B3
0x18004c7ab  movzx   eax, ax
0x18004c7ae  or      eax, 80070000h
0x18004c7b3  mov     [rsp+108h+Reply], eax
0x18004c7b7  mov     [rsp+108h+bAlertable], eax
0x18004c7bb  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004c7c2  mov     r8d, 543h; unsigned int
0x18004c7c8  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004c7cf  mov     ecx, 2; unsigned __int8
0x18004c7d4  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004c7d9  mov     eax, [rsp+108h+Reply]
0x18004c7dd  test    eax, eax
0x18004c7df  js      short loc_18004C7EA
0x18004c7e1  mov     eax, 8000FFFFh
0x18004c7e6  mov     [rsp+108h+Reply], eax
0x18004c7ea  mov     esi, [rsp+108h+dwMilliseconds]
0x18004c7ee  mov     r15b, [rsp+108h+var_D4]
0x18004c7f3  mov     r14b, r15b
0x18004c7f6  test    eax, eax
0x18004c7f8  jns     short loc_18004C80C
0x18004c7fa  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004c801  mov     r8d, 543h
0x18004c807  jmp     loc_18004C8D0
0x18004c80c  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18004c814  mov     r9d, esi; dwMilliseconds
0x18004c817  xor     r8d, r8d; bWaitAll
0x18004c81a  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18004c81f  lea     ecx, [r8+1]; nCount
0x18004c823  call    cs:__imp_WaitForMultipleObjectsEx
0x18004c829  mov     esi, eax
0x18004c82b  mov     r12d, 102h
0x18004c831  test    r14b, r14b
0x18004c834  jnz     short loc_18004C882
0x18004c836  cmp     esi, r12d
0x18004c839  jz      short loc_18004C840
0x18004c83b  cmp     esi, 1
0x18004c83e  jnz     short loc_18004C882
0x18004c840  mov     edx, 1; fAbort
0x18004c845  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004c84a  call    cs:__imp_RpcAsyncCancelCall
0x18004c850  cmp     esi, r12d
0x18004c853  jnz     short loc_18004C85A
0x18004c855  mov     r15b, 1
0x18004c858  jmp     short loc_18004C85D
0x18004c85a  mov     r14b, 1
0x18004c85d  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18004c865  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004c869  xor     r8d, r8d; bWaitAll
0x18004c86c  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18004c871  lea     ecx, [r8+1]; nCount
0x18004c875  call    cs:__imp_WaitForMultipleObjectsEx
0x18004c87b  mov     esi, eax
0x18004c87d  test    r15b, r15b
0x18004c880  jz      short loc_18004C831
0x18004c882  test    esi, esi
0x18004c884  jz      short loc_18004C8A1
0x18004c886  call    cs:__imp_GetLastError
0x18004c88c  test    eax, eax
0x18004c88e  jle     short loc_18004C898
0x18004c890  movzx   eax, ax
0x18004c893  or      eax, 80070000h
0x18004c898  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004c89f  jmp     short loc_18004C8C6
0x18004c8a1  lea     rdx, [rsp+108h+Reply]; Reply
0x18004c8a6  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004c8ab  call    cs:__imp_RpcAsyncCompleteCall
0x18004c8b1  test    eax, eax
0x18004c8b3  jz      short loc_18004C8E5
0x18004c8b5  jle     short loc_18004C8BF
0x18004c8b7  movzx   eax, ax
0x18004c8ba  or      eax, 80070000h
0x18004c8bf  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004c8c6  mov     r8d, 543h; unsigned int
0x18004c8cc  mov     [rsp+108h+Reply], eax
0x18004c8d0  mov     [rsp+108h+bAlertable], eax
0x18004c8d4  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004c8db  mov     ecx, 2; unsigned __int8
0x18004c8e0  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004c8e5  mov     rcx, qword ptr [rsp+108h+pAsync.u]; hObject
0x18004c8ed  test    rcx, rcx
0x18004c8f0  jz      short loc_18004C8F8
0x18004c8f2  call    cs:__imp_CloseHandle
0x18004c8f8  test    r15b, r15b
0x18004c8fb  jz      short loc_18004C93C
0x18004c8fd  mov     [rsp+108h+Reply], 800705B4h
0x18004c905  lea     rdx, [rsp+108h+var_CC]
0x18004c90a  lea     rcx, aWlidcgetsigned_0; "WLIDCGetSignedTokens"
0x18004c911  call    ??$RPCCallTimedOut@AEAY0BF@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BF@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],ulong &>(char const (&)[21],ulong &)
0x18004c916  mov     eax, [rsp+108h+Reply]
0x18004c91a  mov     [rsp+108h+bAlertable], eax
0x18004c91e  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004c925  mov     r8d, 543h; unsigned int
0x18004c92b  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004c932  mov     ecx, 2; unsigned __int8
0x18004c937  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004c93c  test    r14b, r14b
0x18004c93f  jz      short loc_18004C96C
0x18004c941  mov     eax, 800704C7h
0x18004c946  mov     [rsp+108h+Reply], eax
0x18004c94a  mov     [rsp+108h+bAlertable], eax
0x18004c94e  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004c955  mov     r8d, 543h; unsigned int
0x18004c95b  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004c962  mov     ecx, 2; unsigned __int8
0x18004c967  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004c96c  cmp     [rsp+108h+Reply], 800706B5h
0x18004c974  jz      short loc_18004C980
0x18004c976  cmp     [rsp+108h+Reply], 800706BAh
0x18004c97e  jnz     short loc_18004C985
0x18004c980  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004c985  lea     rcx, [rsp+108h+var_C8]; this
0x18004c98a  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18004c98f  mov     eax, [rsp+108h+Reply]
0x18004c993  mov     rcx, [rsp+108h+var_38]
0x18004c99b  xor     rcx, rsp; StackCookie
0x18004c99e  call    __security_check_cookie
0x18004c9a3  add     rsp, 0E8h
0x18004c9aa  pop     r15
0x18004c9ac  pop     r14
0x18004c9ae  pop     r12
0x18004c9b0  pop     rsi
0x18004c9b1  retn
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
