# WLIDCHasPersistedCredential(void * const,ushort const *,int *)

- ea: `0x18004d454`
- end: `0x18004d783`
- name: `?WLIDCHasPersistedCredential@@YAJQEAXPEBGPEAH@Z`
- size: `815`
- prototype: `__int64 __fastcall(void *const, const unsigned __int16 *, int *)`
- caller_count: `5`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001f980`
- `0x180027dd8`
- `0x180031250`
- `0x180032600`
- `0x180032ab0`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180045308`
- `0x180046ce0`
- `0x18004cd04`
- `0x18004d454`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004d5fe`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004d650`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004d5fe`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004d650`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004d51c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004d51c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d52f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d661`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d52f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d661`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d6cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d6cd`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004d625`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004d625`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004d576`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004d576`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004d686`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004d686`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004d4d5`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004d4d5`

## string_xrefs

- `0x18004d541`: `RPC failed to create new event, hr = %#x`
- `0x18004d69a`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCHasPersistedCredential(void *const a1, const unsigned __int16 *a2, int *a3)
{
  DWORD v5; // esi
  char v6; // r15
  char v7; // r14
  int LastError; // eax
  const unsigned __int16 *v9; // r9
  unsigned int v10; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v12; // esi
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-F8h]
  unsigned int Reply; // [rsp+40h] [rbp-D8h] BYREF
  char v16; // [rsp+44h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-D0h] BYREF
  DWORD v18; // [rsp+4Ch] [rbp-CCh] BYREF
  int *v19; // [rsp+50h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+58h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-A8h] BYREF

  v19 = a3;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v5 = dwMilliseconds;
  v18 = dwMilliseconds;
  v6 = 0;
  v16 = 0;
  v7 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v10 = 823;
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
    v9 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_5;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x1Au, 0, &pAsync, a1, a2, v19);
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
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_28;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = L"RPC Async complete call failed, hr = %#x";
  }
  v10 = 825;
LABEL_27:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(2u, "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp", v10, v9, *(_QWORD *)bAlertable);
LABEL_28:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v6 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[28],unsigned long &>(
      (__int64)"WLIDCHasPersistedCredential",
      (int *)&v18);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x339u,
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
      0x339u,
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
0x18004d454  push    rsi
0x18004d456  push    r12
0x18004d458  push    r13
0x18004d45a  push    r14
0x18004d45c  push    r15
0x18004d45e  sub     rsp, 0F0h
0x18004d465  mov     rax, cs:__security_cookie
0x18004d46c  xor     rax, rsp
0x18004d46f  mov     [rsp+118h+var_38], rax
0x18004d477  mov     [rsp+118h+var_C8], r8
0x18004d47c  mov     r13, rdx
0x18004d47f  mov     r12, rcx
0x18004d482  mov     [rsp+118h+Reply], 0
0x18004d48a  mov     [rsp+118h+dwMilliseconds], 0
0x18004d492  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x18004d497  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004d49c  xor     edx, edx; Val
0x18004d49e  lea     r8d, [rdx+70h]; Size
0x18004d4a2  lea     rcx, [rsp+118h+pAsync]; void *
0x18004d4a7  call    memset_0
0x18004d4ac  mov     esi, [rsp+118h+dwMilliseconds]
0x18004d4b0  mov     [rsp+118h+dwMilliseconds], esi
0x18004d4b4  mov     [rsp+118h+var_CC], esi
0x18004d4b8  xor     r15b, r15b
0x18004d4bb  mov     [rsp+118h+var_D4], r15b
0x18004d4c0  xor     r14b, r14b
0x18004d4c3  xorps   xmm0, xmm0
0x18004d4c6  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x18004d4cb  mov     edx, 70h ; 'p'; Size
0x18004d4d0  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004d4d5  call    cs:__imp_RpcAsyncInitializeHandle
0x18004d4db  test    eax, eax
0x18004d4dd  jz      short loc_18004D4FB
0x18004d4df  jle     short loc_18004D4E9
0x18004d4e1  movzx   eax, ax
0x18004d4e4  or      eax, 80070000h
0x18004d4e9  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004d4f0  mov     r8d, 337h
0x18004d4f6  jmp     loc_18004D6A7
0x18004d4fb  mov     [rsp+118h+pAsync.UserInfo], 0
0x18004d507  mov     [rsp+118h+pAsync.NotificationType], 1
0x18004d512  xor     r9d, r9d; lpName
0x18004d515  xor     r8d, r8d; bInitialState
0x18004d518  xor     edx, edx; bManualReset
0x18004d51a  xor     ecx, ecx; lpEventAttributes
0x18004d51c  call    cs:__imp_CreateEventW
0x18004d522  mov     qword ptr [rsp+118h+pAsync.u], rax
0x18004d52a  test    rax, rax
0x18004d52d  jnz     short loc_18004D54A
0x18004d52f  call    cs:__imp_GetLastError
0x18004d535  test    eax, eax
0x18004d537  jle     short loc_18004D541
0x18004d539  movzx   eax, ax
0x18004d53c  or      eax, 80070000h
0x18004d541  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004d548  jmp     short loc_18004D4F0
0x18004d54a  mov     [rsp+118h+Handles], rax
0x18004d54f  mov     rax, [rsp+118h+var_C8]
0x18004d554  mov     [rsp+118h+var_E8], rax
0x18004d559  mov     [rsp+118h+var_F0], r13
0x18004d55e  mov     qword ptr [rsp+118h+bAlertable], r12
0x18004d563  lea     r9, [rsp+118h+pAsync]
0x18004d568  xor     r8d, r8d; pReturnValue
0x18004d56b  lea     edx, [r8+1Ah]; nProcNum
0x18004d56f  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004d576  call    cs:__imp_Ndr64AsyncClientCall
0x18004d57c  mov     eax, [rsp+118h+Reply]
0x18004d580  jmp     short loc_18004D5D1
0x18004d582  test    eax, eax
0x18004d584  jle     short loc_18004D58E
0x18004d586  movzx   eax, ax
0x18004d589  or      eax, 80070000h
0x18004d58e  mov     [rsp+118h+Reply], eax
0x18004d592  mov     [rsp+118h+bAlertable], eax
0x18004d596  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004d59d  mov     r8d, 339h; unsigned int
0x18004d5a3  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004d5aa  mov     ecx, 2; unsigned __int8
0x18004d5af  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004d5b4  mov     eax, [rsp+118h+Reply]
0x18004d5b8  test    eax, eax
0x18004d5ba  js      short loc_18004D5C5
0x18004d5bc  mov     eax, 8000FFFFh
0x18004d5c1  mov     [rsp+118h+Reply], eax
0x18004d5c5  mov     esi, [rsp+118h+dwMilliseconds]
0x18004d5c9  mov     r15b, [rsp+118h+var_D4]
0x18004d5ce  mov     r14b, r15b
0x18004d5d1  test    eax, eax
0x18004d5d3  jns     short loc_18004D5E7
0x18004d5d5  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004d5dc  mov     r8d, 339h
0x18004d5e2  jmp     loc_18004D6AB
0x18004d5e7  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004d5ef  mov     r9d, esi; dwMilliseconds
0x18004d5f2  xor     r8d, r8d; bWaitAll
0x18004d5f5  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004d5fa  lea     ecx, [r8+1]; nCount
0x18004d5fe  call    cs:__imp_WaitForMultipleObjectsEx
0x18004d604  mov     esi, eax
0x18004d606  mov     r12d, 102h
0x18004d60c  test    r14b, r14b
0x18004d60f  jnz     short loc_18004D65D
0x18004d611  cmp     esi, r12d
0x18004d614  jz      short loc_18004D61B
0x18004d616  cmp     esi, 1
0x18004d619  jnz     short loc_18004D65D
0x18004d61b  mov     edx, 1; fAbort
0x18004d620  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004d625  call    cs:__imp_RpcAsyncCancelCall
0x18004d62b  cmp     esi, r12d
0x18004d62e  jnz     short loc_18004D635
0x18004d630  mov     r15b, 1
0x18004d633  jmp     short loc_18004D638
0x18004d635  mov     r14b, 1
0x18004d638  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004d640  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004d644  xor     r8d, r8d; bWaitAll
0x18004d647  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004d64c  lea     ecx, [r8+1]; nCount
0x18004d650  call    cs:__imp_WaitForMultipleObjectsEx
0x18004d656  mov     esi, eax
0x18004d658  test    r15b, r15b
0x18004d65b  jz      short loc_18004D60C
0x18004d65d  test    esi, esi
0x18004d65f  jz      short loc_18004D67C
0x18004d661  call    cs:__imp_GetLastError
0x18004d667  test    eax, eax
0x18004d669  jle     short loc_18004D673
0x18004d66b  movzx   eax, ax
0x18004d66e  or      eax, 80070000h
0x18004d673  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004d67a  jmp     short loc_18004D6A1
0x18004d67c  lea     rdx, [rsp+118h+Reply]; Reply
0x18004d681  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004d686  call    cs:__imp_RpcAsyncCompleteCall
0x18004d68c  test    eax, eax
0x18004d68e  jz      short loc_18004D6C0
0x18004d690  jle     short loc_18004D69A
0x18004d692  movzx   eax, ax
0x18004d695  or      eax, 80070000h
0x18004d69a  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004d6a1  mov     r8d, 339h; unsigned int
0x18004d6a7  mov     [rsp+118h+Reply], eax
0x18004d6ab  mov     [rsp+118h+bAlertable], eax
0x18004d6af  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004d6b6  mov     ecx, 2; unsigned __int8
0x18004d6bb  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004d6c0  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x18004d6c8  test    rcx, rcx
0x18004d6cb  jz      short loc_18004D6D3
0x18004d6cd  call    cs:__imp_CloseHandle
0x18004d6d3  test    r15b, r15b
0x18004d6d6  jz      short loc_18004D717
0x18004d6d8  mov     [rsp+118h+Reply], 800705B4h
0x18004d6e0  lea     rdx, [rsp+118h+var_CC]
0x18004d6e5  lea     rcx, aWlidchaspersis; "WLIDCHasPersistedCredential"
0x18004d6ec  call    ??$RPCCallTimedOut@AEAY0BM@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BM@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[28],ulong &>(char const (&)[28],ulong &)
0x18004d6f1  mov     eax, [rsp+118h+Reply]
0x18004d6f5  mov     [rsp+118h+bAlertable], eax
0x18004d6f9  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004d700  mov     r8d, 339h; unsigned int
0x18004d706  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004d70d  mov     ecx, 2; unsigned __int8
0x18004d712  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004d717  test    r14b, r14b
0x18004d71a  jz      short loc_18004D747
0x18004d71c  mov     eax, 800704C7h
0x18004d721  mov     [rsp+118h+Reply], eax
0x18004d725  mov     [rsp+118h+bAlertable], eax
0x18004d729  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004d730  mov     r8d, 339h; unsigned int
0x18004d736  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004d73d  mov     ecx, 2; unsigned __int8
0x18004d742  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004d747  mov     eax, [rsp+118h+Reply]
0x18004d74b  cmp     eax, 800706B5h
0x18004d750  jz      short loc_18004D759
0x18004d752  cmp     eax, 800706BAh
0x18004d757  jnz     short loc_18004D762
0x18004d759  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004d75e  mov     eax, [rsp+118h+Reply]
0x18004d762  mov     rcx, [rsp+118h+var_38]
0x18004d76a  xor     rcx, rsp; StackCookie
0x18004d76d  call    __security_check_cookie
0x18004d772  add     rsp, 0F0h
0x18004d779  pop     r15
0x18004d77b  pop     r14
0x18004d77d  pop     r13
0x18004d77f  pop     r12
0x18004d781  pop     rsi
0x18004d782  retn
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
