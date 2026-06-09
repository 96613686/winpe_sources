# WLIDCSetIdentityExtendedProperty(void * const,ushort const *,ushort const *)

- ea: `0x18004a748`
- end: `0x18004aa77`
- name: `?WLIDCSetIdentityExtendedProperty@@YAJQEAXPEBG1@Z`
- size: `815`
- prototype: `__int64 __fastcall(void *const, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180041930`

## callees

- `0x18000a400`
- `0x180010c68`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180042270`
- `0x180043240`
- `0x18004a748`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004a810`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004a810`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004a8f2`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004a944`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004a8f2`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004a944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a823`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a955`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a823`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a955`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a9c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a9c1`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004a7c9`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004a7c9`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004a919`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004a919`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004a86a`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004a86a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004a97a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004a97a`

## string_xrefs

- `0x18004a835`: `RPC failed to create new event, hr = %#x`
- `0x18004a98e`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCSetIdentityExtendedProperty(
        void *const a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
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
  const unsigned __int16 *v19; // [rsp+50h] [rbp-C8h]
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
    v10 = 775;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x17u, 0, &pAsync, a1, a2, v19);
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
  v10 = 777;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[33],unsigned long &>(
      "WLIDCSetIdentityExtendedProperty",
      &v18);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x309u,
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
      0x309u,
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
0x18004a748  push    rsi
0x18004a74a  push    r12
0x18004a74c  push    r13
0x18004a74e  push    r14
0x18004a750  push    r15
0x18004a752  sub     rsp, 0F0h
0x18004a759  mov     rax, cs:__security_cookie
0x18004a760  xor     rax, rsp
0x18004a763  mov     [rsp+118h+var_38], rax
0x18004a76b  mov     [rsp+118h+var_C8], r8
0x18004a770  mov     r13, rdx
0x18004a773  mov     r12, rcx
0x18004a776  mov     [rsp+118h+Reply], 0
0x18004a77e  mov     [rsp+118h+dwMilliseconds], 0
0x18004a786  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x18004a78b  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004a790  xor     edx, edx; Val
0x18004a792  lea     r8d, [rdx+70h]; Size
0x18004a796  lea     rcx, [rsp+118h+pAsync]; void *
0x18004a79b  call    memset_0
0x18004a7a0  mov     esi, [rsp+118h+dwMilliseconds]
0x18004a7a4  mov     [rsp+118h+dwMilliseconds], esi
0x18004a7a8  mov     [rsp+118h+var_CC], esi
0x18004a7ac  xor     r15b, r15b
0x18004a7af  mov     [rsp+118h+var_D4], r15b
0x18004a7b4  xor     r14b, r14b
0x18004a7b7  xorps   xmm0, xmm0
0x18004a7ba  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x18004a7bf  mov     edx, 70h ; 'p'; Size
0x18004a7c4  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004a7c9  call    cs:__imp_RpcAsyncInitializeHandle
0x18004a7cf  test    eax, eax
0x18004a7d1  jz      short loc_18004A7EF
0x18004a7d3  jle     short loc_18004A7DD
0x18004a7d5  movzx   eax, ax
0x18004a7d8  or      eax, 80070000h
0x18004a7dd  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004a7e4  mov     r8d, 307h
0x18004a7ea  jmp     loc_18004A99B
0x18004a7ef  mov     [rsp+118h+pAsync.UserInfo], 0
0x18004a7fb  mov     [rsp+118h+pAsync.NotificationType], 1
0x18004a806  xor     r9d, r9d; lpName
0x18004a809  xor     r8d, r8d; bInitialState
0x18004a80c  xor     edx, edx; bManualReset
0x18004a80e  xor     ecx, ecx; lpEventAttributes
0x18004a810  call    cs:__imp_CreateEventW
0x18004a816  mov     qword ptr [rsp+118h+pAsync.u], rax
0x18004a81e  test    rax, rax
0x18004a821  jnz     short loc_18004A83E
0x18004a823  call    cs:__imp_GetLastError
0x18004a829  test    eax, eax
0x18004a82b  jle     short loc_18004A835
0x18004a82d  movzx   eax, ax
0x18004a830  or      eax, 80070000h
0x18004a835  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004a83c  jmp     short loc_18004A7E4
0x18004a83e  mov     [rsp+118h+Handles], rax
0x18004a843  mov     rax, [rsp+118h+var_C8]
0x18004a848  mov     [rsp+118h+var_E8], rax
0x18004a84d  mov     [rsp+118h+var_F0], r13
0x18004a852  mov     qword ptr [rsp+118h+bAlertable], r12
0x18004a857  lea     r9, [rsp+118h+pAsync]
0x18004a85c  xor     r8d, r8d; pReturnValue
0x18004a85f  lea     edx, [r8+17h]; nProcNum
0x18004a863  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004a86a  call    cs:__imp_Ndr64AsyncClientCall
0x18004a870  mov     eax, [rsp+118h+Reply]
0x18004a874  jmp     short loc_18004A8C5
0x18004a876  test    eax, eax
0x18004a878  jle     short loc_18004A882
0x18004a87a  movzx   eax, ax
0x18004a87d  or      eax, 80070000h
0x18004a882  mov     [rsp+118h+Reply], eax
0x18004a886  mov     [rsp+118h+bAlertable], eax
0x18004a88a  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004a891  mov     r8d, 309h; unsigned int
0x18004a897  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004a89e  mov     ecx, 2; unsigned __int8
0x18004a8a3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004a8a8  mov     eax, [rsp+118h+Reply]
0x18004a8ac  test    eax, eax
0x18004a8ae  js      short loc_18004A8B9
0x18004a8b0  mov     eax, 8000FFFFh
0x18004a8b5  mov     [rsp+118h+Reply], eax
0x18004a8b9  mov     esi, [rsp+118h+dwMilliseconds]
0x18004a8bd  mov     r15b, [rsp+118h+var_D4]
0x18004a8c2  mov     r14b, r15b
0x18004a8c5  test    eax, eax
0x18004a8c7  jns     short loc_18004A8DB
0x18004a8c9  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004a8d0  mov     r8d, 309h
0x18004a8d6  jmp     loc_18004A99F
0x18004a8db  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004a8e3  mov     r9d, esi; dwMilliseconds
0x18004a8e6  xor     r8d, r8d; bWaitAll
0x18004a8e9  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004a8ee  lea     ecx, [r8+1]; nCount
0x18004a8f2  call    cs:__imp_WaitForMultipleObjectsEx
0x18004a8f8  mov     esi, eax
0x18004a8fa  mov     r12d, 102h
0x18004a900  test    r14b, r14b
0x18004a903  jnz     short loc_18004A951
0x18004a905  cmp     esi, r12d
0x18004a908  jz      short loc_18004A90F
0x18004a90a  cmp     esi, 1
0x18004a90d  jnz     short loc_18004A951
0x18004a90f  mov     edx, 1; fAbort
0x18004a914  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004a919  call    cs:__imp_RpcAsyncCancelCall
0x18004a91f  cmp     esi, r12d
0x18004a922  jnz     short loc_18004A929
0x18004a924  mov     r15b, 1
0x18004a927  jmp     short loc_18004A92C
0x18004a929  mov     r14b, 1
0x18004a92c  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004a934  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004a938  xor     r8d, r8d; bWaitAll
0x18004a93b  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004a940  lea     ecx, [r8+1]; nCount
0x18004a944  call    cs:__imp_WaitForMultipleObjectsEx
0x18004a94a  mov     esi, eax
0x18004a94c  test    r15b, r15b
0x18004a94f  jz      short loc_18004A900
0x18004a951  test    esi, esi
0x18004a953  jz      short loc_18004A970
0x18004a955  call    cs:__imp_GetLastError
0x18004a95b  test    eax, eax
0x18004a95d  jle     short loc_18004A967
0x18004a95f  movzx   eax, ax
0x18004a962  or      eax, 80070000h
0x18004a967  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004a96e  jmp     short loc_18004A995
0x18004a970  lea     rdx, [rsp+118h+Reply]; Reply
0x18004a975  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004a97a  call    cs:__imp_RpcAsyncCompleteCall
0x18004a980  test    eax, eax
0x18004a982  jz      short loc_18004A9B4
0x18004a984  jle     short loc_18004A98E
0x18004a986  movzx   eax, ax
0x18004a989  or      eax, 80070000h
0x18004a98e  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004a995  mov     r8d, 309h; unsigned int
0x18004a99b  mov     [rsp+118h+Reply], eax
0x18004a99f  mov     [rsp+118h+bAlertable], eax
0x18004a9a3  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004a9aa  mov     ecx, 2; unsigned __int8
0x18004a9af  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004a9b4  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x18004a9bc  test    rcx, rcx
0x18004a9bf  jz      short loc_18004A9C7
0x18004a9c1  call    cs:__imp_CloseHandle
0x18004a9c7  test    r15b, r15b
0x18004a9ca  jz      short loc_18004AA0B
0x18004a9cc  mov     [rsp+118h+Reply], 800705B4h
0x18004a9d4  lea     rdx, [rsp+118h+var_CC]
0x18004a9d9  lea     rcx, aWlidcsetidenti; "WLIDCSetIdentityExtendedProperty"
0x18004a9e0  call    ??$RPCCallTimedOut@AEAY0CB@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0CB@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[33],ulong &>(char const (&)[33],ulong &)
0x18004a9e5  mov     eax, [rsp+118h+Reply]
0x18004a9e9  mov     [rsp+118h+bAlertable], eax
0x18004a9ed  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004a9f4  mov     r8d, 309h; unsigned int
0x18004a9fa  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004aa01  mov     ecx, 2; unsigned __int8
0x18004aa06  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004aa0b  test    r14b, r14b
0x18004aa0e  jz      short loc_18004AA3B
0x18004aa10  mov     eax, 800704C7h
0x18004aa15  mov     [rsp+118h+Reply], eax
0x18004aa19  mov     [rsp+118h+bAlertable], eax
0x18004aa1d  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004aa24  mov     r8d, 309h; unsigned int
0x18004aa2a  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004aa31  mov     ecx, 2; unsigned __int8
0x18004aa36  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004aa3b  mov     eax, [rsp+118h+Reply]
0x18004aa3f  cmp     eax, 800706B5h
0x18004aa44  jz      short loc_18004AA4D
0x18004aa46  cmp     eax, 800706BAh
0x18004aa4b  jnz     short loc_18004AA56
0x18004aa4d  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004aa52  mov     eax, [rsp+118h+Reply]
0x18004aa56  mov     rcx, [rsp+118h+var_38]
0x18004aa5e  xor     rcx, rsp; StackCookie
0x18004aa61  call    __security_check_cookie
0x18004aa66  add     rsp, 0F0h
0x18004aa6d  pop     r15
0x18004aa6f  pop     r14
0x18004aa71  pop     r13
0x18004aa73  pop     r12
0x18004aa75  pop     rsi
0x18004aa76  retn
0x180057062  push    rbp
0x180057064  sub     rsp, 40h
0x180057068  mov     rbp, rdx
0x18005706b  mov     rcx, [rcx]
0x18005706e  mov     ecx, [rcx]; unsigned int
0x180057070  call    ?WLIDpExceptionFilter@@YAHK@Z
0x180057075  nop
0x180057076  add     rsp, 40h
0x18005707a  pop     rbp
0x18005707b  retn
```
