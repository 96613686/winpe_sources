# WLIDCRemovePersistedCredential(void * const,ushort const *,unsigned __int64)

- ea: `0x18004e504`
- end: `0x18004e832`
- name: `?WLIDCRemovePersistedCredential@@YAJQEAXPEBG_K@Z`
- size: `814`
- prototype: `__int64 __fastcall(void *const, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180032ab0`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x1800454a8`
- `0x180046ce0`
- `0x18004cd04`
- `0x18004e504`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004e6ab`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004e6fd`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004e6ab`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004e6fd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004e5ca`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004e5ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e5dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e70e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e5dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e70e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e77a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e77a`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004e6d2`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004e6d2`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004e623`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004e623`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004e733`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004e733`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004e586`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004e586`

## string_xrefs

- `0x18004e5ef`: `RPC failed to create new event, hr = %#x`
- `0x18004e747`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCRemovePersistedCredential(void *const a1, const unsigned __int16 *a2)
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
  BOOL bAlertable[2]; // [rsp+20h] [rbp-D8h]
  unsigned int Reply; // [rsp+40h] [rbp-B8h] BYREF
  char v16; // [rsp+44h] [rbp-B4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-B0h] BYREF
  DWORD v18; // [rsp+4Ch] [rbp-ACh] BYREF
  HANDLE Handles[2]; // [rsp+50h] [rbp-A8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+60h] [rbp-98h] BYREF

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
    v9 = 856;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x1Cu, 0, &pAsync, a1, a2, 0);
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
  v9 = 858;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[31],unsigned long &>(
      (__int64)NotificationRoutine,
      (int *)&v18);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x35Au,
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
      0x35Au,
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
0x18004e504  mov     [rsp+arg_10], rsi
0x18004e509  mov     [rsp+arg_18], r12
0x18004e50e  push    r13
0x18004e510  push    r14
0x18004e512  push    r15
0x18004e514  sub     rsp, 0E0h
0x18004e51b  mov     rax, cs:__security_cookie
0x18004e522  xor     rax, rsp
0x18004e525  mov     [rsp+0F8h+var_28], rax
0x18004e52d  mov     r13, rdx
0x18004e530  mov     r12, rcx
0x18004e533  mov     [rsp+0F8h+Reply], 0
0x18004e53b  mov     [rsp+0F8h+dwMilliseconds], 0
0x18004e543  lea     r8, [rsp+0F8h+dwMilliseconds]; unsigned int *
0x18004e548  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004e54d  xor     edx, edx; Val
0x18004e54f  lea     r8d, [rdx+70h]; Size
0x18004e553  lea     rcx, [rsp+0F8h+pAsync]; void *
0x18004e558  call    memset_0
0x18004e55d  mov     esi, [rsp+0F8h+dwMilliseconds]
0x18004e561  mov     [rsp+0F8h+dwMilliseconds], esi
0x18004e565  mov     [rsp+0F8h+var_AC], esi
0x18004e569  xor     r15b, r15b
0x18004e56c  mov     [rsp+0F8h+var_B4], r15b
0x18004e571  xor     r14b, r14b
0x18004e574  xorps   xmm0, xmm0
0x18004e577  movups  xmmword ptr [rsp+0F8h+Handles], xmm0
0x18004e57c  mov     edx, 70h ; 'p'; Size
0x18004e581  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x18004e586  call    cs:__imp_RpcAsyncInitializeHandle
0x18004e58c  test    eax, eax
0x18004e58e  jz      short loc_18004E5AC
0x18004e590  jle     short loc_18004E59A
0x18004e592  movzx   eax, ax
0x18004e595  or      eax, 80070000h
0x18004e59a  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004e5a1  mov     r8d, 358h
0x18004e5a7  jmp     loc_18004E754
0x18004e5ac  mov     [rsp+0F8h+pAsync.UserInfo], 0
0x18004e5b5  mov     [rsp+0F8h+pAsync.NotificationType], 1
0x18004e5c0  xor     r9d, r9d; lpName
0x18004e5c3  xor     r8d, r8d; bInitialState
0x18004e5c6  xor     edx, edx; bManualReset
0x18004e5c8  xor     ecx, ecx; lpEventAttributes
0x18004e5ca  call    cs:__imp_CreateEventW
0x18004e5d0  mov     qword ptr [rsp+0F8h+pAsync.u], rax
0x18004e5d8  test    rax, rax
0x18004e5db  jnz     short loc_18004E5F8
0x18004e5dd  call    cs:__imp_GetLastError
0x18004e5e3  test    eax, eax
0x18004e5e5  jle     short loc_18004E5EF
0x18004e5e7  movzx   eax, ax
0x18004e5ea  or      eax, 80070000h
0x18004e5ef  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004e5f6  jmp     short loc_18004E5A1
0x18004e5f8  mov     [rsp+0F8h+Handles], rax
0x18004e5fd  mov     [rsp+0F8h+var_C8], 0
0x18004e606  mov     [rsp+0F8h+var_D0], r13
0x18004e60b  mov     qword ptr [rsp+0F8h+bAlertable], r12
0x18004e610  lea     r9, [rsp+0F8h+pAsync]
0x18004e615  xor     r8d, r8d; pReturnValue
0x18004e618  lea     edx, [r8+1Ch]; nProcNum
0x18004e61c  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004e623  call    cs:__imp_Ndr64AsyncClientCall
0x18004e629  mov     eax, [rsp+0F8h+Reply]
0x18004e62d  jmp     short loc_18004E67E
0x18004e62f  test    eax, eax
0x18004e631  jle     short loc_18004E63B
0x18004e633  movzx   eax, ax
0x18004e636  or      eax, 80070000h
0x18004e63b  mov     [rsp+0F8h+Reply], eax
0x18004e63f  mov     [rsp+0F8h+bAlertable], eax
0x18004e643  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004e64a  mov     r8d, 35Ah; unsigned int
0x18004e650  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004e657  mov     ecx, 2; unsigned __int8
0x18004e65c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004e661  mov     eax, [rsp+0F8h+Reply]
0x18004e665  test    eax, eax
0x18004e667  js      short loc_18004E672
0x18004e669  mov     eax, 8000FFFFh
0x18004e66e  mov     [rsp+0F8h+Reply], eax
0x18004e672  mov     esi, [rsp+0F8h+dwMilliseconds]
0x18004e676  mov     r15b, [rsp+0F8h+var_B4]
0x18004e67b  mov     r14b, r15b
0x18004e67e  test    eax, eax
0x18004e680  jns     short loc_18004E694
0x18004e682  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004e689  mov     r8d, 35Ah
0x18004e68f  jmp     loc_18004E758
0x18004e694  mov     [rsp+0F8h+bAlertable], 0; bAlertable
0x18004e69c  mov     r9d, esi; dwMilliseconds
0x18004e69f  xor     r8d, r8d; bWaitAll
0x18004e6a2  lea     rdx, [rsp+0F8h+Handles]; lpHandles
0x18004e6a7  lea     ecx, [r8+1]; nCount
0x18004e6ab  call    cs:__imp_WaitForMultipleObjectsEx
0x18004e6b1  mov     esi, eax
0x18004e6b3  mov     r12d, 102h
0x18004e6b9  test    r14b, r14b
0x18004e6bc  jnz     short loc_18004E70A
0x18004e6be  cmp     esi, r12d
0x18004e6c1  jz      short loc_18004E6C8
0x18004e6c3  cmp     esi, 1
0x18004e6c6  jnz     short loc_18004E70A
0x18004e6c8  mov     edx, 1; fAbort
0x18004e6cd  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x18004e6d2  call    cs:__imp_RpcAsyncCancelCall
0x18004e6d8  cmp     esi, r12d
0x18004e6db  jnz     short loc_18004E6E2
0x18004e6dd  mov     r15b, 1
0x18004e6e0  jmp     short loc_18004E6E5
0x18004e6e2  mov     r14b, 1
0x18004e6e5  mov     [rsp+0F8h+bAlertable], 0; bAlertable
0x18004e6ed  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004e6f1  xor     r8d, r8d; bWaitAll
0x18004e6f4  lea     rdx, [rsp+0F8h+Handles]; lpHandles
0x18004e6f9  lea     ecx, [r8+1]; nCount
0x18004e6fd  call    cs:__imp_WaitForMultipleObjectsEx
0x18004e703  mov     esi, eax
0x18004e705  test    r15b, r15b
0x18004e708  jz      short loc_18004E6B9
0x18004e70a  test    esi, esi
0x18004e70c  jz      short loc_18004E729
0x18004e70e  call    cs:__imp_GetLastError
0x18004e714  test    eax, eax
0x18004e716  jle     short loc_18004E720
0x18004e718  movzx   eax, ax
0x18004e71b  or      eax, 80070000h
0x18004e720  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004e727  jmp     short loc_18004E74E
0x18004e729  lea     rdx, [rsp+0F8h+Reply]; Reply
0x18004e72e  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x18004e733  call    cs:__imp_RpcAsyncCompleteCall
0x18004e739  test    eax, eax
0x18004e73b  jz      short loc_18004E76D
0x18004e73d  jle     short loc_18004E747
0x18004e73f  movzx   eax, ax
0x18004e742  or      eax, 80070000h
0x18004e747  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004e74e  mov     r8d, 35Ah; unsigned int
0x18004e754  mov     [rsp+0F8h+Reply], eax
0x18004e758  mov     [rsp+0F8h+bAlertable], eax
0x18004e75c  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004e763  mov     ecx, 2; unsigned __int8
0x18004e768  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004e76d  mov     rcx, qword ptr [rsp+0F8h+pAsync.u]; hObject
0x18004e775  test    rcx, rcx
0x18004e778  jz      short loc_18004E780
0x18004e77a  call    cs:__imp_CloseHandle
0x18004e780  test    r15b, r15b
0x18004e783  jz      short loc_18004E7BD
0x18004e785  mov     [rsp+0F8h+Reply], 800705B4h
0x18004e78d  lea     rdx, [rsp+0F8h+var_AC]
0x18004e792  call    ??$RPCCallTimedOut@AEAY0BP@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BP@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[31],ulong &>(char const (&)[31],ulong &)
0x18004e797  mov     eax, [rsp+0F8h+Reply]
0x18004e79b  mov     [rsp+0F8h+bAlertable], eax
0x18004e79f  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004e7a6  mov     r8d, 35Ah; unsigned int
0x18004e7ac  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004e7b3  mov     ecx, 2; unsigned __int8
0x18004e7b8  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004e7bd  test    r14b, r14b
0x18004e7c0  jz      short loc_18004E7ED
0x18004e7c2  mov     eax, 800704C7h
0x18004e7c7  mov     [rsp+0F8h+Reply], eax
0x18004e7cb  mov     [rsp+0F8h+bAlertable], eax
0x18004e7cf  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004e7d6  mov     r8d, 35Ah; unsigned int
0x18004e7dc  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004e7e3  mov     ecx, 2; unsigned __int8
0x18004e7e8  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004e7ed  mov     eax, [rsp+0F8h+Reply]
0x18004e7f1  cmp     eax, 800706B5h
0x18004e7f6  jz      short loc_18004E7FF
0x18004e7f8  cmp     eax, 800706BAh
0x18004e7fd  jnz     short loc_18004E808
0x18004e7ff  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004e804  mov     eax, [rsp+0F8h+Reply]
0x18004e808  mov     rcx, [rsp+0F8h+var_28]
0x18004e810  xor     rcx, rsp; StackCookie
0x18004e813  call    __security_check_cookie
0x18004e818  lea     r11, [rsp+0F8h+var_18]
0x18004e820  mov     rsi, [r11+30h]
0x18004e824  mov     r12, [r11+38h]
0x18004e828  mov     rsp, r11
0x18004e82b  pop     r15
0x18004e82d  pop     r14
0x18004e82f  pop     r13
0x18004e831  retn
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
