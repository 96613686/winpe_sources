# WLIDCAssociateDeviceToUser(ushort const *,void * const,ushort const *,ulong)

- ea: `0x180047748`
- end: `0x180047a7d`
- name: `?WLIDCAssociateDeviceToUser@@YAJPEBGQEAX0K@Z`
- size: `821`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void *const, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180035320`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180045280`
- `0x180046ce0`
- `0x180047748`
- `0x18004cd04`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800478ff`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180047951`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800478ff`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180047951`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180047815`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180047815`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047828`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047828`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047962`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800479ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800479ce`
- `RPCRT4!RpcAsyncCancelCall` at `0x180047926`
- `RPCRT4!RpcAsyncCancelCall` at `0x180047926`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180047877`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180047877`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180047987`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180047987`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800477ce`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800477ce`

## string_xrefs

- `0x18004783a`: `RPC failed to create new event, hr = %#x`
- `0x18004799b`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCAssociateDeviceToUser(
        const unsigned __int16 *a1,
        void *const a2,
        const unsigned __int16 *a3,
        int a4)
{
  DWORD v6; // esi
  char v7; // r15
  char v8; // r14
  int LastError; // eax
  const unsigned __int16 *v10; // r9
  unsigned int v11; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v13; // esi
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-F8h]
  unsigned int Reply; // [rsp+40h] [rbp-D8h] BYREF
  char v18; // [rsp+44h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-D0h] BYREF
  int v20; // [rsp+4Ch] [rbp-CCh]
  DWORD v21; // [rsp+50h] [rbp-C8h] BYREF
  const unsigned __int16 *v22; // [rsp+58h] [rbp-C0h]
  HANDLE Handles[2]; // [rsp+60h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-A8h] BYREF

  v20 = a4;
  v22 = a3;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v6 = dwMilliseconds;
  v21 = dwMilliseconds;
  v7 = 0;
  v18 = 0;
  v8 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v11 = 914;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x24u, 0, &pAsync, a1, a2, v22, v20);
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
  v11 = 916;
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
  NotificationRoutine = pAsync.u.APC.NotificationRoutine;
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v7 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[27],unsigned long &>(
      (__int64)NotificationRoutine,
      (int *)&v21);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x394u,
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
      0x394u,
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
0x180047748  push    rsi
0x18004774a  push    r12
0x18004774c  push    r13
0x18004774e  push    r14
0x180047750  push    r15
0x180047752  sub     rsp, 0F0h
0x180047759  mov     rax, cs:__security_cookie
0x180047760  xor     rax, rsp
0x180047763  mov     [rsp+118h+var_38], rax
0x18004776b  mov     [rsp+118h+var_CC], r9d
0x180047770  mov     [rsp+118h+var_C0], r8
0x180047775  mov     r13, rdx
0x180047778  mov     r12, rcx
0x18004777b  mov     [rsp+118h+Reply], 0
0x180047783  mov     [rsp+118h+dwMilliseconds], 0
0x18004778b  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x180047790  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180047795  xor     edx, edx; Val
0x180047797  lea     r8d, [rdx+70h]; Size
0x18004779b  lea     rcx, [rsp+118h+pAsync]; void *
0x1800477a0  call    memset_0
0x1800477a5  mov     esi, [rsp+118h+dwMilliseconds]
0x1800477a9  mov     [rsp+118h+dwMilliseconds], esi
0x1800477ad  mov     [rsp+118h+var_C8], esi
0x1800477b1  xor     r15b, r15b
0x1800477b4  mov     [rsp+118h+var_D4], r15b
0x1800477b9  xor     r14b, r14b
0x1800477bc  xorps   xmm0, xmm0
0x1800477bf  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x1800477c4  mov     edx, 70h ; 'p'; Size
0x1800477c9  lea     rcx, [rsp+118h+pAsync]; pAsync
0x1800477ce  call    cs:__imp_RpcAsyncInitializeHandle
0x1800477d4  test    eax, eax
0x1800477d6  jz      short loc_1800477F4
0x1800477d8  jle     short loc_1800477E2
0x1800477da  movzx   eax, ax
0x1800477dd  or      eax, 80070000h
0x1800477e2  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x1800477e9  mov     r8d, 392h
0x1800477ef  jmp     loc_1800479A8
0x1800477f4  mov     [rsp+118h+pAsync.UserInfo], 0
0x180047800  mov     [rsp+118h+pAsync.NotificationType], 1
0x18004780b  xor     r9d, r9d; lpName
0x18004780e  xor     r8d, r8d; bInitialState
0x180047811  xor     edx, edx; bManualReset
0x180047813  xor     ecx, ecx; lpEventAttributes
0x180047815  call    cs:__imp_CreateEventW
0x18004781b  mov     qword ptr [rsp+118h+pAsync.u], rax
0x180047823  test    rax, rax
0x180047826  jnz     short loc_180047843
0x180047828  call    cs:__imp_GetLastError
0x18004782e  test    eax, eax
0x180047830  jle     short loc_18004783A
0x180047832  movzx   eax, ax
0x180047835  or      eax, 80070000h
0x18004783a  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180047841  jmp     short loc_1800477E9
0x180047843  mov     [rsp+118h+Handles], rax
0x180047848  mov     eax, [rsp+118h+var_CC]
0x18004784c  mov     [rsp+118h+var_E0], eax
0x180047850  mov     rax, [rsp+118h+var_C0]
0x180047855  mov     [rsp+118h+var_E8], rax
0x18004785a  mov     [rsp+118h+var_F0], r13
0x18004785f  mov     qword ptr [rsp+118h+bAlertable], r12
0x180047864  lea     r9, [rsp+118h+pAsync]
0x180047869  xor     r8d, r8d; pReturnValue
0x18004786c  lea     edx, [r8+24h]; nProcNum
0x180047870  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180047877  call    cs:__imp_Ndr64AsyncClientCall
0x18004787d  mov     eax, [rsp+118h+Reply]
0x180047881  jmp     short loc_1800478D2
0x180047883  test    eax, eax
0x180047885  jle     short loc_18004788F
0x180047887  movzx   eax, ax
0x18004788a  or      eax, 80070000h
0x18004788f  mov     [rsp+118h+Reply], eax
0x180047893  mov     [rsp+118h+bAlertable], eax
0x180047897  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004789e  mov     r8d, 394h; unsigned int
0x1800478a4  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800478ab  mov     ecx, 2; unsigned __int8
0x1800478b0  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800478b5  mov     eax, [rsp+118h+Reply]
0x1800478b9  test    eax, eax
0x1800478bb  js      short loc_1800478C6
0x1800478bd  mov     eax, 8000FFFFh
0x1800478c2  mov     [rsp+118h+Reply], eax
0x1800478c6  mov     esi, [rsp+118h+dwMilliseconds]
0x1800478ca  mov     r15b, [rsp+118h+var_D4]
0x1800478cf  mov     r14b, r15b
0x1800478d2  test    eax, eax
0x1800478d4  jns     short loc_1800478E8
0x1800478d6  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x1800478dd  mov     r8d, 394h
0x1800478e3  jmp     loc_1800479AC
0x1800478e8  mov     [rsp+118h+bAlertable], 0; bAlertable
0x1800478f0  mov     r9d, esi; dwMilliseconds
0x1800478f3  xor     r8d, r8d; bWaitAll
0x1800478f6  lea     rdx, [rsp+118h+Handles]; lpHandles
0x1800478fb  lea     ecx, [r8+1]; nCount
0x1800478ff  call    cs:__imp_WaitForMultipleObjectsEx
0x180047905  mov     esi, eax
0x180047907  mov     r12d, 102h
0x18004790d  test    r14b, r14b
0x180047910  jnz     short loc_18004795E
0x180047912  cmp     esi, r12d
0x180047915  jz      short loc_18004791C
0x180047917  cmp     esi, 1
0x18004791a  jnz     short loc_18004795E
0x18004791c  mov     edx, 1; fAbort
0x180047921  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180047926  call    cs:__imp_RpcAsyncCancelCall
0x18004792c  cmp     esi, r12d
0x18004792f  jnz     short loc_180047936
0x180047931  mov     r15b, 1
0x180047934  jmp     short loc_180047939
0x180047936  mov     r14b, 1
0x180047939  mov     [rsp+118h+bAlertable], 0; bAlertable
0x180047941  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180047945  xor     r8d, r8d; bWaitAll
0x180047948  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004794d  lea     ecx, [r8+1]; nCount
0x180047951  call    cs:__imp_WaitForMultipleObjectsEx
0x180047957  mov     esi, eax
0x180047959  test    r15b, r15b
0x18004795c  jz      short loc_18004790D
0x18004795e  test    esi, esi
0x180047960  jz      short loc_18004797D
0x180047962  call    cs:__imp_GetLastError
0x180047968  test    eax, eax
0x18004796a  jle     short loc_180047974
0x18004796c  movzx   eax, ax
0x18004796f  or      eax, 80070000h
0x180047974  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004797b  jmp     short loc_1800479A2
0x18004797d  lea     rdx, [rsp+118h+Reply]; Reply
0x180047982  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180047987  call    cs:__imp_RpcAsyncCompleteCall
0x18004798d  test    eax, eax
0x18004798f  jz      short loc_1800479C1
0x180047991  jle     short loc_18004799B
0x180047993  movzx   eax, ax
0x180047996  or      eax, 80070000h
0x18004799b  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x1800479a2  mov     r8d, 394h; unsigned int
0x1800479a8  mov     [rsp+118h+Reply], eax
0x1800479ac  mov     [rsp+118h+bAlertable], eax
0x1800479b0  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800479b7  mov     ecx, 2; unsigned __int8
0x1800479bc  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800479c1  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x1800479c9  test    rcx, rcx
0x1800479cc  jz      short loc_1800479D4
0x1800479ce  call    cs:__imp_CloseHandle
0x1800479d4  test    r15b, r15b
0x1800479d7  jz      short loc_180047A11
0x1800479d9  mov     [rsp+118h+Reply], 800705B4h
0x1800479e1  lea     rdx, [rsp+118h+var_C8]
0x1800479e6  call    ??$RPCCallTimedOut@AEAY0BL@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BL@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[27],ulong &>(char const (&)[27],ulong &)
0x1800479eb  mov     eax, [rsp+118h+Reply]
0x1800479ef  mov     [rsp+118h+bAlertable], eax
0x1800479f3  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x1800479fa  mov     r8d, 394h; unsigned int
0x180047a00  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180047a07  mov     ecx, 2; unsigned __int8
0x180047a0c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180047a11  test    r14b, r14b
0x180047a14  jz      short loc_180047A41
0x180047a16  mov     eax, 800704C7h
0x180047a1b  mov     [rsp+118h+Reply], eax
0x180047a1f  mov     [rsp+118h+bAlertable], eax
0x180047a23  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180047a2a  mov     r8d, 394h; unsigned int
0x180047a30  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180047a37  mov     ecx, 2; unsigned __int8
0x180047a3c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180047a41  mov     eax, [rsp+118h+Reply]
0x180047a45  cmp     eax, 800706B5h
0x180047a4a  jz      short loc_180047A53
0x180047a4c  cmp     eax, 800706BAh
0x180047a51  jnz     short loc_180047A5C
0x180047a53  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180047a58  mov     eax, [rsp+118h+Reply]
0x180047a5c  mov     rcx, [rsp+118h+var_38]
0x180047a64  xor     rcx, rsp; StackCookie
0x180047a67  call    __security_check_cookie
0x180047a6c  add     rsp, 0F0h
0x180047a73  pop     r15
0x180047a75  pop     r14
0x180047a77  pop     r13
0x180047a79  pop     r12
0x180047a7b  pop     rsi
0x180047a7c  retn
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
