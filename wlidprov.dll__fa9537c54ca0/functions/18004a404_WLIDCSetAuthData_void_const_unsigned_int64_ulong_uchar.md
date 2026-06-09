# WLIDCSetAuthData(void * const,unsigned __int64,ulong,uchar *)

- ea: `0x18004a404`
- end: `0x18004a740`
- name: `?WLIDCSetAuthData@@YAJQEAX_KKPEAE@Z`
- size: `828`
- prototype: `__int64 __fastcall(void *const, unsigned __int64, unsigned int, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180025bbc`
- `0x180041910`

## callees

- `0x18000a400`
- `0x180010c68`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180041a58`
- `0x180043240`
- `0x18004a404`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004a4d1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004a4d1`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004a5bb`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004a60d`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004a5bb`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004a60d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a4e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a61e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a4e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a61e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a68a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a68a`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004a48a`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004a48a`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004a5e2`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004a5e2`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004a533`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004a533`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004a643`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004a643`

## string_xrefs

- `0x18004a4f6`: `RPC failed to create new event, hr = %#x`
- `0x18004a657`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCSetAuthData(void *const a1, __int64 a2, int a3, unsigned __int8 *a4)
{
  DWORD v6; // esi
  char v7; // r15
  char v8; // r14
  int LastError; // eax
  const unsigned __int16 *v10; // r9
  unsigned int v11; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v13; // esi
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-F8h]
  unsigned int Reply; // [rsp+40h] [rbp-D8h] BYREF
  char v17; // [rsp+44h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-D0h] BYREF
  int v19; // [rsp+4Ch] [rbp-CCh]
  DWORD v20; // [rsp+50h] [rbp-C8h] BYREF
  unsigned __int8 *v21; // [rsp+58h] [rbp-C0h]
  HANDLE Handles[2]; // [rsp+60h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-A8h] BYREF

  v21 = a4;
  v19 = a3;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v6 = dwMilliseconds;
  v20 = dwMilliseconds;
  v7 = 0;
  v17 = 0;
  v8 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v11 = 610;
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
    v10 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_5;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0xCu, 0, &pAsync, a1, a2, v19, v21);
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
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_28;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC Async complete call failed, hr = %#x";
  }
  v11 = 612;
LABEL_27:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(
    2u,
    "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
    v11,
    v10,
    *(_QWORD *)bAlertable);
LABEL_28:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v7 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[17],unsigned long &>("WLIDCSetAuthData", &v20);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x264u,
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
      0x264u,
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
0x18004a404  push    rsi
0x18004a406  push    r12
0x18004a408  push    r13
0x18004a40a  push    r14
0x18004a40c  push    r15
0x18004a40e  sub     rsp, 0F0h
0x18004a415  mov     rax, cs:__security_cookie
0x18004a41c  xor     rax, rsp
0x18004a41f  mov     [rsp+118h+var_38], rax
0x18004a427  mov     [rsp+118h+var_C0], r9
0x18004a42c  mov     [rsp+118h+var_CC], r8d
0x18004a431  mov     r13, rdx
0x18004a434  mov     r12, rcx
0x18004a437  mov     [rsp+118h+Reply], 0
0x18004a43f  mov     [rsp+118h+dwMilliseconds], 0
0x18004a447  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x18004a44c  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004a451  xor     edx, edx; Val
0x18004a453  lea     r8d, [rdx+70h]; Size
0x18004a457  lea     rcx, [rsp+118h+pAsync]; void *
0x18004a45c  call    memset_0
0x18004a461  mov     esi, [rsp+118h+dwMilliseconds]
0x18004a465  mov     [rsp+118h+dwMilliseconds], esi
0x18004a469  mov     [rsp+118h+var_C8], esi
0x18004a46d  xor     r15b, r15b
0x18004a470  mov     [rsp+118h+var_D4], r15b
0x18004a475  xor     r14b, r14b
0x18004a478  xorps   xmm0, xmm0
0x18004a47b  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x18004a480  mov     edx, 70h ; 'p'; Size
0x18004a485  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004a48a  call    cs:__imp_RpcAsyncInitializeHandle
0x18004a490  test    eax, eax
0x18004a492  jz      short loc_18004A4B0
0x18004a494  jle     short loc_18004A49E
0x18004a496  movzx   eax, ax
0x18004a499  or      eax, 80070000h
0x18004a49e  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004a4a5  mov     r8d, 262h
0x18004a4ab  jmp     loc_18004A664
0x18004a4b0  mov     [rsp+118h+pAsync.UserInfo], 0
0x18004a4bc  mov     [rsp+118h+pAsync.NotificationType], 1
0x18004a4c7  xor     r9d, r9d; lpName
0x18004a4ca  xor     r8d, r8d; bInitialState
0x18004a4cd  xor     edx, edx; bManualReset
0x18004a4cf  xor     ecx, ecx; lpEventAttributes
0x18004a4d1  call    cs:__imp_CreateEventW
0x18004a4d7  mov     qword ptr [rsp+118h+pAsync.u], rax
0x18004a4df  test    rax, rax
0x18004a4e2  jnz     short loc_18004A4FF
0x18004a4e4  call    cs:__imp_GetLastError
0x18004a4ea  test    eax, eax
0x18004a4ec  jle     short loc_18004A4F6
0x18004a4ee  movzx   eax, ax
0x18004a4f1  or      eax, 80070000h
0x18004a4f6  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004a4fd  jmp     short loc_18004A4A5
0x18004a4ff  mov     [rsp+118h+Handles], rax
0x18004a504  mov     rax, [rsp+118h+var_C0]
0x18004a509  mov     [rsp+118h+var_E0], rax
0x18004a50e  mov     eax, [rsp+118h+var_CC]
0x18004a512  mov     [rsp+118h+var_E8], eax
0x18004a516  mov     [rsp+118h+var_F0], r13
0x18004a51b  mov     qword ptr [rsp+118h+bAlertable], r12
0x18004a520  lea     r9, [rsp+118h+pAsync]
0x18004a525  xor     r8d, r8d; pReturnValue
0x18004a528  lea     edx, [r8+0Ch]; nProcNum
0x18004a52c  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004a533  call    cs:__imp_Ndr64AsyncClientCall
0x18004a539  mov     eax, [rsp+118h+Reply]
0x18004a53d  jmp     short loc_18004A58E
0x18004a53f  test    eax, eax
0x18004a541  jle     short loc_18004A54B
0x18004a543  movzx   eax, ax
0x18004a546  or      eax, 80070000h
0x18004a54b  mov     [rsp+118h+Reply], eax
0x18004a54f  mov     [rsp+118h+bAlertable], eax
0x18004a553  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004a55a  mov     r8d, 264h; unsigned int
0x18004a560  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004a567  mov     ecx, 2; unsigned __int8
0x18004a56c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004a571  mov     eax, [rsp+118h+Reply]
0x18004a575  test    eax, eax
0x18004a577  js      short loc_18004A582
0x18004a579  mov     eax, 8000FFFFh
0x18004a57e  mov     [rsp+118h+Reply], eax
0x18004a582  mov     esi, [rsp+118h+dwMilliseconds]
0x18004a586  mov     r15b, [rsp+118h+var_D4]
0x18004a58b  mov     r14b, r15b
0x18004a58e  test    eax, eax
0x18004a590  jns     short loc_18004A5A4
0x18004a592  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004a599  mov     r8d, 264h
0x18004a59f  jmp     loc_18004A668
0x18004a5a4  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004a5ac  mov     r9d, esi; dwMilliseconds
0x18004a5af  xor     r8d, r8d; bWaitAll
0x18004a5b2  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004a5b7  lea     ecx, [r8+1]; nCount
0x18004a5bb  call    cs:__imp_WaitForMultipleObjectsEx
0x18004a5c1  mov     esi, eax
0x18004a5c3  mov     r12d, 102h
0x18004a5c9  test    r14b, r14b
0x18004a5cc  jnz     short loc_18004A61A
0x18004a5ce  cmp     esi, r12d
0x18004a5d1  jz      short loc_18004A5D8
0x18004a5d3  cmp     esi, 1
0x18004a5d6  jnz     short loc_18004A61A
0x18004a5d8  mov     edx, 1; fAbort
0x18004a5dd  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004a5e2  call    cs:__imp_RpcAsyncCancelCall
0x18004a5e8  cmp     esi, r12d
0x18004a5eb  jnz     short loc_18004A5F2
0x18004a5ed  mov     r15b, 1
0x18004a5f0  jmp     short loc_18004A5F5
0x18004a5f2  mov     r14b, 1
0x18004a5f5  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004a5fd  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004a601  xor     r8d, r8d; bWaitAll
0x18004a604  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004a609  lea     ecx, [r8+1]; nCount
0x18004a60d  call    cs:__imp_WaitForMultipleObjectsEx
0x18004a613  mov     esi, eax
0x18004a615  test    r15b, r15b
0x18004a618  jz      short loc_18004A5C9
0x18004a61a  test    esi, esi
0x18004a61c  jz      short loc_18004A639
0x18004a61e  call    cs:__imp_GetLastError
0x18004a624  test    eax, eax
0x18004a626  jle     short loc_18004A630
0x18004a628  movzx   eax, ax
0x18004a62b  or      eax, 80070000h
0x18004a630  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004a637  jmp     short loc_18004A65E
0x18004a639  lea     rdx, [rsp+118h+Reply]; Reply
0x18004a63e  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004a643  call    cs:__imp_RpcAsyncCompleteCall
0x18004a649  test    eax, eax
0x18004a64b  jz      short loc_18004A67D
0x18004a64d  jle     short loc_18004A657
0x18004a64f  movzx   eax, ax
0x18004a652  or      eax, 80070000h
0x18004a657  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004a65e  mov     r8d, 264h; unsigned int
0x18004a664  mov     [rsp+118h+Reply], eax
0x18004a668  mov     [rsp+118h+bAlertable], eax
0x18004a66c  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004a673  mov     ecx, 2; unsigned __int8
0x18004a678  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004a67d  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x18004a685  test    rcx, rcx
0x18004a688  jz      short loc_18004A690
0x18004a68a  call    cs:__imp_CloseHandle
0x18004a690  test    r15b, r15b
0x18004a693  jz      short loc_18004A6D4
0x18004a695  mov     [rsp+118h+Reply], 800705B4h
0x18004a69d  lea     rdx, [rsp+118h+var_C8]
0x18004a6a2  lea     rcx, aWlidcsetauthda_0; "WLIDCSetAuthData"
0x18004a6a9  call    ??$RPCCallTimedOut@AEAY0BB@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BB@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[17],ulong &>(char const (&)[17],ulong &)
0x18004a6ae  mov     eax, [rsp+118h+Reply]
0x18004a6b2  mov     [rsp+118h+bAlertable], eax
0x18004a6b6  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004a6bd  mov     r8d, 264h; unsigned int
0x18004a6c3  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004a6ca  mov     ecx, 2; unsigned __int8
0x18004a6cf  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004a6d4  test    r14b, r14b
0x18004a6d7  jz      short loc_18004A704
0x18004a6d9  mov     eax, 800704C7h
0x18004a6de  mov     [rsp+118h+Reply], eax
0x18004a6e2  mov     [rsp+118h+bAlertable], eax
0x18004a6e6  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004a6ed  mov     r8d, 264h; unsigned int
0x18004a6f3  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004a6fa  mov     ecx, 2; unsigned __int8
0x18004a6ff  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004a704  mov     eax, [rsp+118h+Reply]
0x18004a708  cmp     eax, 800706B5h
0x18004a70d  jz      short loc_18004A716
0x18004a70f  cmp     eax, 800706BAh
0x18004a714  jnz     short loc_18004A71F
0x18004a716  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004a71b  mov     eax, [rsp+118h+Reply]
0x18004a71f  mov     rcx, [rsp+118h+var_38]
0x18004a727  xor     rcx, rsp; StackCookie
0x18004a72a  call    __security_check_cookie
0x18004a72f  add     rsp, 0F0h
0x18004a736  pop     r15
0x18004a738  pop     r14
0x18004a73a  pop     r13
0x18004a73c  pop     r12
0x18004a73e  pop     rsi
0x18004a73f  retn
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
