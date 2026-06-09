# WLIDCGetIdentityProperty(void * const,ushort const *,ushort * *)

- ea: `0x180046a58`
- end: `0x180046d87`
- name: `?WLIDCGetIdentityProperty@@YAJQEAXPEBGPEAPEAG@Z`
- size: `815`
- prototype: `__int64 __fastcall(void *const, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800238ec`
- `0x1800247c0`
- `0x18002520c`
- `0x180041720`

## callees

- `0x18000a400`
- `0x180010c68`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180041eac`
- `0x180043240`
- `0x180046a58`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046b20`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046b20`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180046c02`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180046c54`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180046c02`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180046c54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046b33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046c65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046b33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046c65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046cd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046cd1`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180046ad9`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180046ad9`
- `RPCRT4!RpcAsyncCancelCall` at `0x180046c29`
- `RPCRT4!RpcAsyncCancelCall` at `0x180046c29`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180046b7a`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180046b7a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180046c8a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180046c8a`

## string_xrefs

- `0x180046b45`: `RPC failed to create new event, hr = %#x`
- `0x180046c9e`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCGetIdentityProperty(void *const a1, const unsigned __int16 *a2, unsigned __int16 **a3)
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
  unsigned __int16 **v19; // [rsp+50h] [rbp-C8h]
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
    v10 = 786;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x16u, 0, &pAsync, a1, a2, v19);
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
  v10 = 788;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[25],unsigned long &>("WLIDCGetIdentityProperty", &v18);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x314u,
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
      0x314u,
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
0x180046a58  push    rsi
0x180046a5a  push    r12
0x180046a5c  push    r13
0x180046a5e  push    r14
0x180046a60  push    r15
0x180046a62  sub     rsp, 0F0h
0x180046a69  mov     rax, cs:__security_cookie
0x180046a70  xor     rax, rsp
0x180046a73  mov     [rsp+118h+var_38], rax
0x180046a7b  mov     [rsp+118h+var_C8], r8
0x180046a80  mov     r13, rdx
0x180046a83  mov     r12, rcx
0x180046a86  mov     [rsp+118h+Reply], 0
0x180046a8e  mov     [rsp+118h+dwMilliseconds], 0
0x180046a96  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x180046a9b  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180046aa0  xor     edx, edx; Val
0x180046aa2  lea     r8d, [rdx+70h]; Size
0x180046aa6  lea     rcx, [rsp+118h+pAsync]; void *
0x180046aab  call    memset_0
0x180046ab0  mov     esi, [rsp+118h+dwMilliseconds]
0x180046ab4  mov     [rsp+118h+dwMilliseconds], esi
0x180046ab8  mov     [rsp+118h+var_CC], esi
0x180046abc  xor     r15b, r15b
0x180046abf  mov     [rsp+118h+var_D4], r15b
0x180046ac4  xor     r14b, r14b
0x180046ac7  xorps   xmm0, xmm0
0x180046aca  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x180046acf  mov     edx, 70h ; 'p'; Size
0x180046ad4  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180046ad9  call    cs:__imp_RpcAsyncInitializeHandle
0x180046adf  test    eax, eax
0x180046ae1  jz      short loc_180046AFF
0x180046ae3  jle     short loc_180046AED
0x180046ae5  movzx   eax, ax
0x180046ae8  or      eax, 80070000h
0x180046aed  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180046af4  mov     r8d, 312h
0x180046afa  jmp     loc_180046CAB
0x180046aff  mov     [rsp+118h+pAsync.UserInfo], 0
0x180046b0b  mov     [rsp+118h+pAsync.NotificationType], 1
0x180046b16  xor     r9d, r9d; lpName
0x180046b19  xor     r8d, r8d; bInitialState
0x180046b1c  xor     edx, edx; bManualReset
0x180046b1e  xor     ecx, ecx; lpEventAttributes
0x180046b20  call    cs:__imp_CreateEventW
0x180046b26  mov     qword ptr [rsp+118h+pAsync.u], rax
0x180046b2e  test    rax, rax
0x180046b31  jnz     short loc_180046B4E
0x180046b33  call    cs:__imp_GetLastError
0x180046b39  test    eax, eax
0x180046b3b  jle     short loc_180046B45
0x180046b3d  movzx   eax, ax
0x180046b40  or      eax, 80070000h
0x180046b45  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180046b4c  jmp     short loc_180046AF4
0x180046b4e  mov     [rsp+118h+Handles], rax
0x180046b53  mov     rax, [rsp+118h+var_C8]
0x180046b58  mov     [rsp+118h+var_E8], rax
0x180046b5d  mov     [rsp+118h+var_F0], r13
0x180046b62  mov     qword ptr [rsp+118h+bAlertable], r12
0x180046b67  lea     r9, [rsp+118h+pAsync]
0x180046b6c  xor     r8d, r8d; pReturnValue
0x180046b6f  lea     edx, [r8+16h]; nProcNum
0x180046b73  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180046b7a  call    cs:__imp_Ndr64AsyncClientCall
0x180046b80  mov     eax, [rsp+118h+Reply]
0x180046b84  jmp     short loc_180046BD5
0x180046b86  test    eax, eax
0x180046b88  jle     short loc_180046B92
0x180046b8a  movzx   eax, ax
0x180046b8d  or      eax, 80070000h
0x180046b92  mov     [rsp+118h+Reply], eax
0x180046b96  mov     [rsp+118h+bAlertable], eax
0x180046b9a  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180046ba1  mov     r8d, 314h; unsigned int
0x180046ba7  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180046bae  mov     ecx, 2; unsigned __int8
0x180046bb3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180046bb8  mov     eax, [rsp+118h+Reply]
0x180046bbc  test    eax, eax
0x180046bbe  js      short loc_180046BC9
0x180046bc0  mov     eax, 8000FFFFh
0x180046bc5  mov     [rsp+118h+Reply], eax
0x180046bc9  mov     esi, [rsp+118h+dwMilliseconds]
0x180046bcd  mov     r15b, [rsp+118h+var_D4]
0x180046bd2  mov     r14b, r15b
0x180046bd5  test    eax, eax
0x180046bd7  jns     short loc_180046BEB
0x180046bd9  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180046be0  mov     r8d, 314h
0x180046be6  jmp     loc_180046CAF
0x180046beb  mov     [rsp+118h+bAlertable], 0; bAlertable
0x180046bf3  mov     r9d, esi; dwMilliseconds
0x180046bf6  xor     r8d, r8d; bWaitAll
0x180046bf9  lea     rdx, [rsp+118h+Handles]; lpHandles
0x180046bfe  lea     ecx, [r8+1]; nCount
0x180046c02  call    cs:__imp_WaitForMultipleObjectsEx
0x180046c08  mov     esi, eax
0x180046c0a  mov     r12d, 102h
0x180046c10  test    r14b, r14b
0x180046c13  jnz     short loc_180046C61
0x180046c15  cmp     esi, r12d
0x180046c18  jz      short loc_180046C1F
0x180046c1a  cmp     esi, 1
0x180046c1d  jnz     short loc_180046C61
0x180046c1f  mov     edx, 1; fAbort
0x180046c24  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180046c29  call    cs:__imp_RpcAsyncCancelCall
0x180046c2f  cmp     esi, r12d
0x180046c32  jnz     short loc_180046C39
0x180046c34  mov     r15b, 1
0x180046c37  jmp     short loc_180046C3C
0x180046c39  mov     r14b, 1
0x180046c3c  mov     [rsp+118h+bAlertable], 0; bAlertable
0x180046c44  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180046c48  xor     r8d, r8d; bWaitAll
0x180046c4b  lea     rdx, [rsp+118h+Handles]; lpHandles
0x180046c50  lea     ecx, [r8+1]; nCount
0x180046c54  call    cs:__imp_WaitForMultipleObjectsEx
0x180046c5a  mov     esi, eax
0x180046c5c  test    r15b, r15b
0x180046c5f  jz      short loc_180046C10
0x180046c61  test    esi, esi
0x180046c63  jz      short loc_180046C80
0x180046c65  call    cs:__imp_GetLastError
0x180046c6b  test    eax, eax
0x180046c6d  jle     short loc_180046C77
0x180046c6f  movzx   eax, ax
0x180046c72  or      eax, 80070000h
0x180046c77  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180046c7e  jmp     short loc_180046CA5
0x180046c80  lea     rdx, [rsp+118h+Reply]; Reply
0x180046c85  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180046c8a  call    cs:__imp_RpcAsyncCompleteCall
0x180046c90  test    eax, eax
0x180046c92  jz      short loc_180046CC4
0x180046c94  jle     short loc_180046C9E
0x180046c96  movzx   eax, ax
0x180046c99  or      eax, 80070000h
0x180046c9e  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180046ca5  mov     r8d, 314h; unsigned int
0x180046cab  mov     [rsp+118h+Reply], eax
0x180046caf  mov     [rsp+118h+bAlertable], eax
0x180046cb3  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180046cba  mov     ecx, 2; unsigned __int8
0x180046cbf  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180046cc4  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x180046ccc  test    rcx, rcx
0x180046ccf  jz      short loc_180046CD7
0x180046cd1  call    cs:__imp_CloseHandle
0x180046cd7  test    r15b, r15b
0x180046cda  jz      short loc_180046D1B
0x180046cdc  mov     [rsp+118h+Reply], 800705B4h
0x180046ce4  lea     rdx, [rsp+118h+var_CC]
0x180046ce9  lea     rcx, aWlidcgetidenti; "WLIDCGetIdentityProperty"
0x180046cf0  call    ??$RPCCallTimedOut@AEAY0BJ@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BJ@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[25],ulong &>(char const (&)[25],ulong &)
0x180046cf5  mov     eax, [rsp+118h+Reply]
0x180046cf9  mov     [rsp+118h+bAlertable], eax
0x180046cfd  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180046d04  mov     r8d, 314h; unsigned int
0x180046d0a  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180046d11  mov     ecx, 2; unsigned __int8
0x180046d16  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180046d1b  test    r14b, r14b
0x180046d1e  jz      short loc_180046D4B
0x180046d20  mov     eax, 800704C7h
0x180046d25  mov     [rsp+118h+Reply], eax
0x180046d29  mov     [rsp+118h+bAlertable], eax
0x180046d2d  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180046d34  mov     r8d, 314h; unsigned int
0x180046d3a  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180046d41  mov     ecx, 2; unsigned __int8
0x180046d46  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180046d4b  mov     eax, [rsp+118h+Reply]
0x180046d4f  cmp     eax, 800706B5h
0x180046d54  jz      short loc_180046D5D
0x180046d56  cmp     eax, 800706BAh
0x180046d5b  jnz     short loc_180046D66
0x180046d5d  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180046d62  mov     eax, [rsp+118h+Reply]
0x180046d66  mov     rcx, [rsp+118h+var_38]
0x180046d6e  xor     rcx, rsp; StackCookie
0x180046d71  call    __security_check_cookie
0x180046d76  add     rsp, 0F0h
0x180046d7d  pop     r15
0x180046d7f  pop     r14
0x180046d81  pop     r13
0x180046d83  pop     r12
0x180046d85  pop     rsi
0x180046d86  retn
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
