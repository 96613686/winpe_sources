# WLIDCHasPersistedCredential(void * const,ushort const *,int *)

- ea: `0x18004895c`
- end: `0x180048c84`
- name: `?WLIDCHasPersistedCredential@@YAJQEAXPEBGPEAH@Z`
- size: `808`
- prototype: `__int64 __fastcall(void *const, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180041870`

## callees

- `0x18000a400`
- `0x180010c68`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180041fc4`
- `0x180043240`
- `0x18004895c`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180048a24`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180048a24`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180048b06`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180048b58`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180048b06`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180048b58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048a37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048b69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048a37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048b69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048bd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048bd5`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800489dd`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800489dd`
- `RPCRT4!RpcAsyncCancelCall` at `0x180048b2d`
- `RPCRT4!RpcAsyncCancelCall` at `0x180048b2d`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180048a7e`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180048a7e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180048b8e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180048b8e`

## string_xrefs

- `0x180048a49`: `RPC failed to create new event, hr = %#x`
- `0x180048ba2`: `RPC Async complete call failed, hr = %#x`

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
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-F8h]
  unsigned int Reply; // [rsp+40h] [rbp-D8h] BYREF
  char v17; // [rsp+44h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-D0h] BYREF
  DWORD v19; // [rsp+4Ch] [rbp-CCh] BYREF
  int *v20; // [rsp+50h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+58h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-A8h] BYREF

  v20 = a3;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v5 = dwMilliseconds;
  v19 = dwMilliseconds;
  v6 = 0;
  v17 = 0;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x1Au, 0, &pAsync, a1, a2, v20);
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
  NotificationRoutine = pAsync.u.APC.NotificationRoutine;
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v6 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[28],unsigned long &>(NotificationRoutine, &v19);
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
0x18004895c  push    rsi
0x18004895e  push    r12
0x180048960  push    r13
0x180048962  push    r14
0x180048964  push    r15
0x180048966  sub     rsp, 0F0h
0x18004896d  mov     rax, cs:__security_cookie
0x180048974  xor     rax, rsp
0x180048977  mov     [rsp+118h+var_38], rax
0x18004897f  mov     [rsp+118h+var_C8], r8
0x180048984  mov     r13, rdx
0x180048987  mov     r12, rcx
0x18004898a  mov     [rsp+118h+Reply], 0
0x180048992  mov     [rsp+118h+dwMilliseconds], 0
0x18004899a  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x18004899f  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x1800489a4  xor     edx, edx; Val
0x1800489a6  lea     r8d, [rdx+70h]; Size
0x1800489aa  lea     rcx, [rsp+118h+pAsync]; void *
0x1800489af  call    memset_0
0x1800489b4  mov     esi, [rsp+118h+dwMilliseconds]
0x1800489b8  mov     [rsp+118h+dwMilliseconds], esi
0x1800489bc  mov     [rsp+118h+var_CC], esi
0x1800489c0  xor     r15b, r15b
0x1800489c3  mov     [rsp+118h+var_D4], r15b
0x1800489c8  xor     r14b, r14b
0x1800489cb  xorps   xmm0, xmm0
0x1800489ce  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x1800489d3  mov     edx, 70h ; 'p'; Size
0x1800489d8  lea     rcx, [rsp+118h+pAsync]; pAsync
0x1800489dd  call    cs:__imp_RpcAsyncInitializeHandle
0x1800489e3  test    eax, eax
0x1800489e5  jz      short loc_180048A03
0x1800489e7  jle     short loc_1800489F1
0x1800489e9  movzx   eax, ax
0x1800489ec  or      eax, 80070000h
0x1800489f1  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x1800489f8  mov     r8d, 337h
0x1800489fe  jmp     loc_180048BAF
0x180048a03  mov     [rsp+118h+pAsync.UserInfo], 0
0x180048a0f  mov     [rsp+118h+pAsync.NotificationType], 1
0x180048a1a  xor     r9d, r9d; lpName
0x180048a1d  xor     r8d, r8d; bInitialState
0x180048a20  xor     edx, edx; bManualReset
0x180048a22  xor     ecx, ecx; lpEventAttributes
0x180048a24  call    cs:__imp_CreateEventW
0x180048a2a  mov     qword ptr [rsp+118h+pAsync.u], rax
0x180048a32  test    rax, rax
0x180048a35  jnz     short loc_180048A52
0x180048a37  call    cs:__imp_GetLastError
0x180048a3d  test    eax, eax
0x180048a3f  jle     short loc_180048A49
0x180048a41  movzx   eax, ax
0x180048a44  or      eax, 80070000h
0x180048a49  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180048a50  jmp     short loc_1800489F8
0x180048a52  mov     [rsp+118h+Handles], rax
0x180048a57  mov     rax, [rsp+118h+var_C8]
0x180048a5c  mov     [rsp+118h+var_E8], rax
0x180048a61  mov     [rsp+118h+var_F0], r13
0x180048a66  mov     qword ptr [rsp+118h+bAlertable], r12
0x180048a6b  lea     r9, [rsp+118h+pAsync]
0x180048a70  xor     r8d, r8d; pReturnValue
0x180048a73  lea     edx, [r8+1Ah]; nProcNum
0x180048a77  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180048a7e  call    cs:__imp_Ndr64AsyncClientCall
0x180048a84  mov     eax, [rsp+118h+Reply]
0x180048a88  jmp     short loc_180048AD9
0x180048a8a  test    eax, eax
0x180048a8c  jle     short loc_180048A96
0x180048a8e  movzx   eax, ax
0x180048a91  or      eax, 80070000h
0x180048a96  mov     [rsp+118h+Reply], eax
0x180048a9a  mov     [rsp+118h+bAlertable], eax
0x180048a9e  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180048aa5  mov     r8d, 339h; unsigned int
0x180048aab  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180048ab2  mov     ecx, 2; unsigned __int8
0x180048ab7  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180048abc  mov     eax, [rsp+118h+Reply]
0x180048ac0  test    eax, eax
0x180048ac2  js      short loc_180048ACD
0x180048ac4  mov     eax, 8000FFFFh
0x180048ac9  mov     [rsp+118h+Reply], eax
0x180048acd  mov     esi, [rsp+118h+dwMilliseconds]
0x180048ad1  mov     r15b, [rsp+118h+var_D4]
0x180048ad6  mov     r14b, r15b
0x180048ad9  test    eax, eax
0x180048adb  jns     short loc_180048AEF
0x180048add  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180048ae4  mov     r8d, 339h
0x180048aea  jmp     loc_180048BB3
0x180048aef  mov     [rsp+118h+bAlertable], 0; bAlertable
0x180048af7  mov     r9d, esi; dwMilliseconds
0x180048afa  xor     r8d, r8d; bWaitAll
0x180048afd  lea     rdx, [rsp+118h+Handles]; lpHandles
0x180048b02  lea     ecx, [r8+1]; nCount
0x180048b06  call    cs:__imp_WaitForMultipleObjectsEx
0x180048b0c  mov     esi, eax
0x180048b0e  mov     r12d, 102h
0x180048b14  test    r14b, r14b
0x180048b17  jnz     short loc_180048B65
0x180048b19  cmp     esi, r12d
0x180048b1c  jz      short loc_180048B23
0x180048b1e  cmp     esi, 1
0x180048b21  jnz     short loc_180048B65
0x180048b23  mov     edx, 1; fAbort
0x180048b28  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180048b2d  call    cs:__imp_RpcAsyncCancelCall
0x180048b33  cmp     esi, r12d
0x180048b36  jnz     short loc_180048B3D
0x180048b38  mov     r15b, 1
0x180048b3b  jmp     short loc_180048B40
0x180048b3d  mov     r14b, 1
0x180048b40  mov     [rsp+118h+bAlertable], 0; bAlertable
0x180048b48  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180048b4c  xor     r8d, r8d; bWaitAll
0x180048b4f  lea     rdx, [rsp+118h+Handles]; lpHandles
0x180048b54  lea     ecx, [r8+1]; nCount
0x180048b58  call    cs:__imp_WaitForMultipleObjectsEx
0x180048b5e  mov     esi, eax
0x180048b60  test    r15b, r15b
0x180048b63  jz      short loc_180048B14
0x180048b65  test    esi, esi
0x180048b67  jz      short loc_180048B84
0x180048b69  call    cs:__imp_GetLastError
0x180048b6f  test    eax, eax
0x180048b71  jle     short loc_180048B7B
0x180048b73  movzx   eax, ax
0x180048b76  or      eax, 80070000h
0x180048b7b  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180048b82  jmp     short loc_180048BA9
0x180048b84  lea     rdx, [rsp+118h+Reply]; Reply
0x180048b89  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180048b8e  call    cs:__imp_RpcAsyncCompleteCall
0x180048b94  test    eax, eax
0x180048b96  jz      short loc_180048BC8
0x180048b98  jle     short loc_180048BA2
0x180048b9a  movzx   eax, ax
0x180048b9d  or      eax, 80070000h
0x180048ba2  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180048ba9  mov     r8d, 339h; unsigned int
0x180048baf  mov     [rsp+118h+Reply], eax
0x180048bb3  mov     [rsp+118h+bAlertable], eax
0x180048bb7  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180048bbe  mov     ecx, 2; unsigned __int8
0x180048bc3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180048bc8  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x180048bd0  test    rcx, rcx
0x180048bd3  jz      short loc_180048BDB
0x180048bd5  call    cs:__imp_CloseHandle
0x180048bdb  test    r15b, r15b
0x180048bde  jz      short loc_180048C18
0x180048be0  mov     [rsp+118h+Reply], 800705B4h
0x180048be8  lea     rdx, [rsp+118h+var_CC]
0x180048bed  call    ??$RPCCallTimedOut@AEAY0BM@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BM@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[28],ulong &>(char const (&)[28],ulong &)
0x180048bf2  mov     eax, [rsp+118h+Reply]
0x180048bf6  mov     [rsp+118h+bAlertable], eax
0x180048bfa  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180048c01  mov     r8d, 339h; unsigned int
0x180048c07  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180048c0e  mov     ecx, 2; unsigned __int8
0x180048c13  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180048c18  test    r14b, r14b
0x180048c1b  jz      short loc_180048C48
0x180048c1d  mov     eax, 800704C7h
0x180048c22  mov     [rsp+118h+Reply], eax
0x180048c26  mov     [rsp+118h+bAlertable], eax
0x180048c2a  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180048c31  mov     r8d, 339h; unsigned int
0x180048c37  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180048c3e  mov     ecx, 2; unsigned __int8
0x180048c43  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180048c48  mov     eax, [rsp+118h+Reply]
0x180048c4c  cmp     eax, 800706B5h
0x180048c51  jz      short loc_180048C5A
0x180048c53  cmp     eax, 800706BAh
0x180048c58  jnz     short loc_180048C63
0x180048c5a  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180048c5f  mov     eax, [rsp+118h+Reply]
0x180048c63  mov     rcx, [rsp+118h+var_38]
0x180048c6b  xor     rcx, rsp; StackCookie
0x180048c6e  call    __security_check_cookie
0x180048c73  add     rsp, 0F0h
0x180048c7a  pop     r15
0x180048c7c  pop     r14
0x180048c7e  pop     r13
0x180048c80  pop     r12
0x180048c82  pop     rsi
0x180048c83  retn
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
