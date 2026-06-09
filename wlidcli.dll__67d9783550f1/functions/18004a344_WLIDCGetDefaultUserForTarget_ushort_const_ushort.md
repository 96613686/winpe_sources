# WLIDCGetDefaultUserForTarget(ushort const *,ushort * *)

- ea: `0x18004a344`
- end: `0x18004a6a8`
- name: `?WLIDCGetDefaultUserForTarget@@YAJPEBGPEAPEAG@Z`
- size: `868`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002d740`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180045394`
- `0x180046ce0`
- `0x18004a344`
- `0x18004cd04`
- `0x180050c84`
- `0x180050e40`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004a50e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004a560`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004a50e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004a560`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004a42c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004a42c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a43f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a571`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a43f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a571`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a5dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a5dd`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004a535`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004a535`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004a486`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004a486`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004a596`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004a596`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004a3e5`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004a3e5`

## string_xrefs

- `0x18004a451`: `RPC failed to create new event, hr = %#x`
- `0x18004a5aa`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCGetDefaultUserForTarget(const unsigned __int16 *a1, unsigned __int16 **a2)
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
    v10 = 1055;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x31u, 0, &pAsync, v18, a1, a2);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v9 = L"RPC call failed, hr = %#x";
    v10 = 1057;
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
    v10 = 1057;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[29],unsigned long &>(
      (__int64)"WLIDCGetDefaultUserForTarget",
      (int *)&v17);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x421u,
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
      0x421u,
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
0x18004a344  mov     [rsp+arg_10], rsi
0x18004a349  mov     [rsp+arg_18], r12
0x18004a34e  push    r13
0x18004a350  push    r14
0x18004a352  push    r15
0x18004a354  sub     rsp, 0F0h
0x18004a35b  mov     rax, cs:__security_cookie
0x18004a362  xor     rax, rsp
0x18004a365  mov     [rsp+108h+var_28], rax
0x18004a36d  mov     r13, rdx
0x18004a370  mov     r12, rcx
0x18004a373  mov     [rsp+108h+dwMilliseconds], 0
0x18004a37b  lea     r8, [rsp+108h+dwMilliseconds]; unsigned int *
0x18004a380  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004a385  mov     [rsp+108h+Reply], 0
0x18004a38d  mov     [rsp+108h+var_B8], 0
0x18004a396  lea     rcx, [rsp+108h+var_B8]; this
0x18004a39b  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18004a3a0  mov     [rsp+108h+Reply], eax
0x18004a3a4  test    eax, eax
0x18004a3a6  js      loc_18004A67E
0x18004a3ac  xor     edx, edx; Val
0x18004a3ae  lea     r8d, [rdx+70h]; Size
0x18004a3b2  lea     rcx, [rsp+108h+pAsync]; void *
0x18004a3b7  call    memset_0
0x18004a3bc  mov     esi, [rsp+108h+dwMilliseconds]
0x18004a3c0  mov     [rsp+108h+dwMilliseconds], esi
0x18004a3c4  mov     [rsp+108h+var_BC], esi
0x18004a3c8  xor     r15b, r15b
0x18004a3cb  mov     [rsp+108h+var_C4], r15b
0x18004a3d0  xor     r14b, r14b
0x18004a3d3  xorps   xmm0, xmm0
0x18004a3d6  movups  xmmword ptr [rsp+108h+Handles], xmm0
0x18004a3db  mov     edx, 70h ; 'p'; Size
0x18004a3e0  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004a3e5  call    cs:__imp_RpcAsyncInitializeHandle
0x18004a3eb  test    eax, eax
0x18004a3ed  jz      short loc_18004A40B
0x18004a3ef  jle     short loc_18004A3F9
0x18004a3f1  movzx   eax, ax
0x18004a3f4  or      eax, 80070000h
0x18004a3f9  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004a400  mov     r8d, 41Fh
0x18004a406  jmp     loc_18004A5B7
0x18004a40b  mov     [rsp+108h+pAsync.UserInfo], 0
0x18004a417  mov     [rsp+108h+pAsync.NotificationType], 1
0x18004a422  xor     r9d, r9d; lpName
0x18004a425  xor     r8d, r8d; bInitialState
0x18004a428  xor     edx, edx; bManualReset
0x18004a42a  xor     ecx, ecx; lpEventAttributes
0x18004a42c  call    cs:__imp_CreateEventW
0x18004a432  mov     qword ptr [rsp+108h+pAsync.u], rax
0x18004a43a  test    rax, rax
0x18004a43d  jnz     short loc_18004A45A
0x18004a43f  call    cs:__imp_GetLastError
0x18004a445  test    eax, eax
0x18004a447  jle     short loc_18004A451
0x18004a449  movzx   eax, ax
0x18004a44c  or      eax, 80070000h
0x18004a451  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004a458  jmp     short loc_18004A400
0x18004a45a  mov     [rsp+108h+Handles], rax
0x18004a45f  mov     [rsp+108h+var_D8], r13
0x18004a464  mov     [rsp+108h+var_E0], r12
0x18004a469  mov     rax, [rsp+108h+var_B8]
0x18004a46e  mov     qword ptr [rsp+108h+bAlertable], rax
0x18004a473  lea     r9, [rsp+108h+pAsync]
0x18004a478  xor     r8d, r8d; pReturnValue
0x18004a47b  lea     edx, [r8+31h]; nProcNum
0x18004a47f  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004a486  call    cs:__imp_Ndr64AsyncClientCall
0x18004a48c  mov     eax, [rsp+108h+Reply]
0x18004a490  jmp     short loc_18004A4E1
0x18004a492  test    eax, eax
0x18004a494  jle     short loc_18004A49E
0x18004a496  movzx   eax, ax
0x18004a499  or      eax, 80070000h
0x18004a49e  mov     [rsp+108h+Reply], eax
0x18004a4a2  mov     [rsp+108h+bAlertable], eax
0x18004a4a6  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004a4ad  mov     r8d, 421h; unsigned int
0x18004a4b3  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004a4ba  mov     ecx, 2; unsigned __int8
0x18004a4bf  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004a4c4  mov     eax, [rsp+108h+Reply]
0x18004a4c8  test    eax, eax
0x18004a4ca  js      short loc_18004A4D5
0x18004a4cc  mov     eax, 8000FFFFh
0x18004a4d1  mov     [rsp+108h+Reply], eax
0x18004a4d5  mov     esi, [rsp+108h+dwMilliseconds]
0x18004a4d9  mov     r15b, [rsp+108h+var_C4]
0x18004a4de  mov     r14b, r15b
0x18004a4e1  test    eax, eax
0x18004a4e3  jns     short loc_18004A4F7
0x18004a4e5  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004a4ec  mov     r8d, 421h
0x18004a4f2  jmp     loc_18004A5BB
0x18004a4f7  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18004a4ff  mov     r9d, esi; dwMilliseconds
0x18004a502  xor     r8d, r8d; bWaitAll
0x18004a505  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18004a50a  lea     ecx, [r8+1]; nCount
0x18004a50e  call    cs:__imp_WaitForMultipleObjectsEx
0x18004a514  mov     esi, eax
0x18004a516  mov     r12d, 102h
0x18004a51c  test    r14b, r14b
0x18004a51f  jnz     short loc_18004A56D
0x18004a521  cmp     esi, r12d
0x18004a524  jz      short loc_18004A52B
0x18004a526  cmp     esi, 1
0x18004a529  jnz     short loc_18004A56D
0x18004a52b  mov     edx, 1; fAbort
0x18004a530  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004a535  call    cs:__imp_RpcAsyncCancelCall
0x18004a53b  cmp     esi, r12d
0x18004a53e  jnz     short loc_18004A545
0x18004a540  mov     r15b, 1
0x18004a543  jmp     short loc_18004A548
0x18004a545  mov     r14b, 1
0x18004a548  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18004a550  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004a554  xor     r8d, r8d; bWaitAll
0x18004a557  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18004a55c  lea     ecx, [r8+1]; nCount
0x18004a560  call    cs:__imp_WaitForMultipleObjectsEx
0x18004a566  mov     esi, eax
0x18004a568  test    r15b, r15b
0x18004a56b  jz      short loc_18004A51C
0x18004a56d  test    esi, esi
0x18004a56f  jz      short loc_18004A58C
0x18004a571  call    cs:__imp_GetLastError
0x18004a577  test    eax, eax
0x18004a579  jle     short loc_18004A583
0x18004a57b  movzx   eax, ax
0x18004a57e  or      eax, 80070000h
0x18004a583  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004a58a  jmp     short loc_18004A5B1
0x18004a58c  lea     rdx, [rsp+108h+Reply]; Reply
0x18004a591  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004a596  call    cs:__imp_RpcAsyncCompleteCall
0x18004a59c  test    eax, eax
0x18004a59e  jz      short loc_18004A5D0
0x18004a5a0  jle     short loc_18004A5AA
0x18004a5a2  movzx   eax, ax
0x18004a5a5  or      eax, 80070000h
0x18004a5aa  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004a5b1  mov     r8d, 421h; unsigned int
0x18004a5b7  mov     [rsp+108h+Reply], eax
0x18004a5bb  mov     [rsp+108h+bAlertable], eax
0x18004a5bf  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004a5c6  mov     ecx, 2; unsigned __int8
0x18004a5cb  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004a5d0  mov     rcx, qword ptr [rsp+108h+pAsync.u]; hObject
0x18004a5d8  test    rcx, rcx
0x18004a5db  jz      short loc_18004A5E3
0x18004a5dd  call    cs:__imp_CloseHandle
0x18004a5e3  test    r15b, r15b
0x18004a5e6  jz      short loc_18004A627
0x18004a5e8  mov     [rsp+108h+Reply], 800705B4h
0x18004a5f0  lea     rdx, [rsp+108h+var_BC]
0x18004a5f5  lea     rcx, aWlidcgetdefaul; "WLIDCGetDefaultUserForTarget"
0x18004a5fc  call    ??$RPCCallTimedOut@AEAY0BN@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BN@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[29],ulong &>(char const (&)[29],ulong &)
0x18004a601  mov     eax, [rsp+108h+Reply]
0x18004a605  mov     [rsp+108h+bAlertable], eax
0x18004a609  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004a610  mov     r8d, 421h; unsigned int
0x18004a616  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004a61d  mov     ecx, 2; unsigned __int8
0x18004a622  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004a627  test    r14b, r14b
0x18004a62a  jz      short loc_18004A657
0x18004a62c  mov     eax, 800704C7h
0x18004a631  mov     [rsp+108h+Reply], eax
0x18004a635  mov     [rsp+108h+bAlertable], eax
0x18004a639  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004a640  mov     r8d, 421h; unsigned int
0x18004a646  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004a64d  mov     ecx, 2; unsigned __int8
0x18004a652  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004a657  cmp     [rsp+108h+Reply], 800706B5h
0x18004a65f  jz      short loc_18004A66B
0x18004a661  cmp     [rsp+108h+Reply], 800706BAh
0x18004a669  jnz     short loc_18004A670
0x18004a66b  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004a670  lea     rcx, [rsp+108h+var_B8]; this
0x18004a675  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18004a67a  mov     eax, [rsp+108h+Reply]
0x18004a67e  mov     rcx, [rsp+108h+var_28]
0x18004a686  xor     rcx, rsp; StackCookie
0x18004a689  call    __security_check_cookie
0x18004a68e  lea     r11, [rsp+108h+var_18]
0x18004a696  mov     rsi, [r11+30h]
0x18004a69a  mov     r12, [r11+38h]
0x18004a69e  mov     rsp, r11
0x18004a6a1  pop     r15
0x18004a6a3  pop     r14
0x18004a6a5  pop     r13
0x18004a6a7  retn
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
