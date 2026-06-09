# WLIDCUpdateConnectedIdentity(void * const,unsigned __int64)

- ea: `0x18004aa80`
- end: `0x18004ada9`
- name: `?WLIDCUpdateConnectedIdentity@@YAJQEAX_K@Z`
- size: `809`
- prototype: `__int64 __fastcall(void *const, unsigned __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800238ec`
- `0x180041950`

## callees

- `0x18000a400`
- `0x180010c68`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x18004204c`
- `0x180043240`
- `0x18004aa80`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004ab43`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004ab43`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004ac1b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004ac6d`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004ac1b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004ac6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ab56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ac7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ab56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ac7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004acea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004acea`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004ab02`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004ab02`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004ac42`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004ac42`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004ab93`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004ab93`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004aca3`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004aca3`

## string_xrefs

- `0x18004ab68`: `RPC failed to create new event, hr = %#x`
- `0x18004acb7`: `RPC Async complete call failed, hr = %#x`
- `0x18004ad02`: `WLIDCUpdateConnectedIdentity`

## pseudocode

```c
__int64 __fastcall WLIDCUpdateConnectedIdentity(void *const a1, __int64 a2)
{
  DWORD v4; // esi
  char v5; // r15
  char v6; // r14
  int LastError; // eax
  const unsigned __int16 *v8; // r9
  unsigned int v9; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v11; // esi
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-C8h]
  unsigned int Reply; // [rsp+30h] [rbp-B8h] BYREF
  char v15; // [rsp+34h] [rbp-B4h]
  DWORD dwMilliseconds; // [rsp+38h] [rbp-B0h] BYREF
  DWORD v17; // [rsp+3Ch] [rbp-ACh] BYREF
  HANDLE Handles[2]; // [rsp+40h] [rbp-A8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+50h] [rbp-98h] BYREF

  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v4 = dwMilliseconds;
  v17 = dwMilliseconds;
  v5 = 0;
  v15 = 0;
  v6 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v9 = 500;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 4u, 0, &pAsync, a1, a2);
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
  v9 = 502;
LABEL_27:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(2u, "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp", v9, v8, *(_QWORD *)bAlertable);
LABEL_28:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v5 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[29],unsigned long &>("WLIDCUpdateConnectedIdentity", &v17);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x1F6u,
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
      0x1F6u,
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
0x18004aa80  mov     [rsp+arg_10], rsi
0x18004aa85  mov     [rsp+arg_18], r12
0x18004aa8a  push    r13
0x18004aa8c  push    r14
0x18004aa8e  push    r15
0x18004aa90  sub     rsp, 0D0h
0x18004aa97  mov     rax, cs:__security_cookie
0x18004aa9e  xor     rax, rsp
0x18004aaa1  mov     [rsp+0E8h+var_28], rax
0x18004aaa9  mov     r13, rdx
0x18004aaac  mov     r12, rcx
0x18004aaaf  mov     [rsp+0E8h+Reply], 0
0x18004aab7  mov     [rsp+0E8h+dwMilliseconds], 0
0x18004aabf  lea     r8, [rsp+0E8h+dwMilliseconds]; unsigned int *
0x18004aac4  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004aac9  xor     edx, edx; Val
0x18004aacb  lea     r8d, [rdx+70h]; Size
0x18004aacf  lea     rcx, [rsp+0E8h+pAsync]; void *
0x18004aad4  call    memset_0
0x18004aad9  mov     esi, [rsp+0E8h+dwMilliseconds]
0x18004aadd  mov     [rsp+0E8h+dwMilliseconds], esi
0x18004aae1  mov     [rsp+0E8h+var_AC], esi
0x18004aae5  xor     r15b, r15b
0x18004aae8  mov     [rsp+0E8h+var_B4], r15b
0x18004aaed  xor     r14b, r14b
0x18004aaf0  xorps   xmm0, xmm0
0x18004aaf3  movups  xmmword ptr [rsp+0E8h+Handles], xmm0
0x18004aaf8  mov     edx, 70h ; 'p'; Size
0x18004aafd  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x18004ab02  call    cs:__imp_RpcAsyncInitializeHandle
0x18004ab08  test    eax, eax
0x18004ab0a  jz      short loc_18004AB28
0x18004ab0c  jle     short loc_18004AB16
0x18004ab0e  movzx   eax, ax
0x18004ab11  or      eax, 80070000h
0x18004ab16  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004ab1d  mov     r8d, 1F4h
0x18004ab23  jmp     loc_18004ACC4
0x18004ab28  mov     [rsp+0E8h+pAsync.UserInfo], 0
0x18004ab31  mov     [rsp+0E8h+pAsync.NotificationType], 1
0x18004ab39  xor     r9d, r9d; lpName
0x18004ab3c  xor     r8d, r8d; bInitialState
0x18004ab3f  xor     edx, edx; bManualReset
0x18004ab41  xor     ecx, ecx; lpEventAttributes
0x18004ab43  call    cs:__imp_CreateEventW
0x18004ab49  mov     qword ptr [rsp+0E8h+pAsync.u], rax
0x18004ab51  test    rax, rax
0x18004ab54  jnz     short loc_18004AB71
0x18004ab56  call    cs:__imp_GetLastError
0x18004ab5c  test    eax, eax
0x18004ab5e  jle     short loc_18004AB68
0x18004ab60  movzx   eax, ax
0x18004ab63  or      eax, 80070000h
0x18004ab68  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004ab6f  jmp     short loc_18004AB1D
0x18004ab71  mov     [rsp+0E8h+Handles], rax
0x18004ab76  mov     [rsp+0E8h+var_C0], r13
0x18004ab7b  mov     qword ptr [rsp+0E8h+bAlertable], r12
0x18004ab80  lea     r9, [rsp+0E8h+pAsync]
0x18004ab85  xor     r8d, r8d; pReturnValue
0x18004ab88  lea     edx, [r8+4]; nProcNum
0x18004ab8c  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004ab93  call    cs:__imp_Ndr64AsyncClientCall
0x18004ab99  mov     eax, [rsp+0E8h+Reply]
0x18004ab9d  jmp     short loc_18004ABEE
0x18004ab9f  test    eax, eax
0x18004aba1  jle     short loc_18004ABAB
0x18004aba3  movzx   eax, ax
0x18004aba6  or      eax, 80070000h
0x18004abab  mov     [rsp+0E8h+Reply], eax
0x18004abaf  mov     [rsp+0E8h+bAlertable], eax
0x18004abb3  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004abba  mov     r8d, 1F6h; unsigned int
0x18004abc0  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004abc7  mov     ecx, 2; unsigned __int8
0x18004abcc  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004abd1  mov     eax, [rsp+0E8h+Reply]
0x18004abd5  test    eax, eax
0x18004abd7  js      short loc_18004ABE2
0x18004abd9  mov     eax, 8000FFFFh
0x18004abde  mov     [rsp+0E8h+Reply], eax
0x18004abe2  mov     esi, [rsp+0E8h+dwMilliseconds]
0x18004abe6  mov     r15b, [rsp+0E8h+var_B4]
0x18004abeb  mov     r14b, r15b
0x18004abee  test    eax, eax
0x18004abf0  jns     short loc_18004AC04
0x18004abf2  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004abf9  mov     r8d, 1F6h
0x18004abff  jmp     loc_18004ACC8
0x18004ac04  mov     [rsp+0E8h+bAlertable], 0; bAlertable
0x18004ac0c  mov     r9d, esi; dwMilliseconds
0x18004ac0f  xor     r8d, r8d; bWaitAll
0x18004ac12  lea     rdx, [rsp+0E8h+Handles]; lpHandles
0x18004ac17  lea     ecx, [r8+1]; nCount
0x18004ac1b  call    cs:__imp_WaitForMultipleObjectsEx
0x18004ac21  mov     esi, eax
0x18004ac23  mov     r12d, 102h
0x18004ac29  test    r14b, r14b
0x18004ac2c  jnz     short loc_18004AC7A
0x18004ac2e  cmp     esi, r12d
0x18004ac31  jz      short loc_18004AC38
0x18004ac33  cmp     esi, 1
0x18004ac36  jnz     short loc_18004AC7A
0x18004ac38  mov     edx, 1; fAbort
0x18004ac3d  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x18004ac42  call    cs:__imp_RpcAsyncCancelCall
0x18004ac48  cmp     esi, r12d
0x18004ac4b  jnz     short loc_18004AC52
0x18004ac4d  mov     r15b, 1
0x18004ac50  jmp     short loc_18004AC55
0x18004ac52  mov     r14b, 1
0x18004ac55  mov     [rsp+0E8h+bAlertable], 0; bAlertable
0x18004ac5d  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004ac61  xor     r8d, r8d; bWaitAll
0x18004ac64  lea     rdx, [rsp+0E8h+Handles]; lpHandles
0x18004ac69  lea     ecx, [r8+1]; nCount
0x18004ac6d  call    cs:__imp_WaitForMultipleObjectsEx
0x18004ac73  mov     esi, eax
0x18004ac75  test    r15b, r15b
0x18004ac78  jz      short loc_18004AC29
0x18004ac7a  test    esi, esi
0x18004ac7c  jz      short loc_18004AC99
0x18004ac7e  call    cs:__imp_GetLastError
0x18004ac84  test    eax, eax
0x18004ac86  jle     short loc_18004AC90
0x18004ac88  movzx   eax, ax
0x18004ac8b  or      eax, 80070000h
0x18004ac90  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004ac97  jmp     short loc_18004ACBE
0x18004ac99  lea     rdx, [rsp+0E8h+Reply]; Reply
0x18004ac9e  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x18004aca3  call    cs:__imp_RpcAsyncCompleteCall
0x18004aca9  test    eax, eax
0x18004acab  jz      short loc_18004ACDD
0x18004acad  jle     short loc_18004ACB7
0x18004acaf  movzx   eax, ax
0x18004acb2  or      eax, 80070000h
0x18004acb7  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004acbe  mov     r8d, 1F6h; unsigned int
0x18004acc4  mov     [rsp+0E8h+Reply], eax
0x18004acc8  mov     [rsp+0E8h+bAlertable], eax
0x18004accc  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004acd3  mov     ecx, 2; unsigned __int8
0x18004acd8  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004acdd  mov     rcx, qword ptr [rsp+0E8h+pAsync.u]; hObject
0x18004ace5  test    rcx, rcx
0x18004ace8  jz      short loc_18004ACF0
0x18004acea  call    cs:__imp_CloseHandle
0x18004acf0  test    r15b, r15b
0x18004acf3  jz      short loc_18004AD34
0x18004acf5  mov     [rsp+0E8h+Reply], 800705B4h
0x18004acfd  lea     rdx, [rsp+0E8h+var_AC]
0x18004ad02  lea     rcx, aWlidcupdatecon; "WLIDCUpdateConnectedIdentity"
0x18004ad09  call    ??$RPCCallTimedOut@AEAY0BN@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BN@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[29],ulong &>(char const (&)[29],ulong &)
0x18004ad0e  mov     eax, [rsp+0E8h+Reply]
0x18004ad12  mov     [rsp+0E8h+bAlertable], eax
0x18004ad16  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004ad1d  mov     r8d, 1F6h; unsigned int
0x18004ad23  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004ad2a  mov     ecx, 2; unsigned __int8
0x18004ad2f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004ad34  test    r14b, r14b
0x18004ad37  jz      short loc_18004AD64
0x18004ad39  mov     eax, 800704C7h
0x18004ad3e  mov     [rsp+0E8h+Reply], eax
0x18004ad42  mov     [rsp+0E8h+bAlertable], eax
0x18004ad46  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004ad4d  mov     r8d, 1F6h; unsigned int
0x18004ad53  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004ad5a  mov     ecx, 2; unsigned __int8
0x18004ad5f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004ad64  mov     eax, [rsp+0E8h+Reply]
0x18004ad68  cmp     eax, 800706B5h
0x18004ad6d  jz      short loc_18004AD76
0x18004ad6f  cmp     eax, 800706BAh
0x18004ad74  jnz     short loc_18004AD7F
0x18004ad76  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004ad7b  mov     eax, [rsp+0E8h+Reply]
0x18004ad7f  mov     rcx, [rsp+0E8h+var_28]
0x18004ad87  xor     rcx, rsp; StackCookie
0x18004ad8a  call    __security_check_cookie
0x18004ad8f  lea     r11, [rsp+0E8h+var_18]
0x18004ad97  mov     rsi, [r11+30h]
0x18004ad9b  mov     r12, [r11+38h]
0x18004ad9f  mov     rsp, r11
0x18004ada2  pop     r15
0x18004ada4  pop     r14
0x18004ada6  pop     r13
0x18004ada8  retn
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
