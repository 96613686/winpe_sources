# WLIDCAddUserToSsoGroup(ushort const *,unsigned __int64,ulong)

- ea: `0x1800473e0`
- end: `0x180047742`
- name: `?WLIDCAddUserToSsoGroup@@YAJPEBG_KK@Z`
- size: `866`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002706c`
- `0x1800350b0`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x1800450dc`
- `0x180046ce0`
- `0x1800473e0`
- `0x18004cd04`
- `0x180050c84`
- `0x180050e40`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800475b1`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180047603`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800475b1`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180047603`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800474c7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800474c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800474da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047614`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800474da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047614`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047680`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047680`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800475d8`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800475d8`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180047529`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180047529`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180047639`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180047639`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180047480`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180047480`

## string_xrefs

- `0x1800474ec`: `RPC failed to create new event, hr = %#x`
- `0x18004764d`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCAddUserToSsoGroup(const unsigned __int16 *a1, __int64 a2, int a3)
{
  __int64 result; // rax
  DWORD v6; // esi
  char v7; // r15
  char v8; // r14
  int LastError; // eax
  const unsigned __int16 *v10; // r9
  unsigned int v11; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v13; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-F8h]
  int Reply; // [rsp+40h] [rbp-D8h] BYREF
  char v16; // [rsp+44h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-D0h] BYREF
  int v18; // [rsp+4Ch] [rbp-CCh]
  DWORD v19; // [rsp+50h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+58h] [rbp-C0h] BYREF
  HANDLE Handles[2]; // [rsp+60h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-A8h] BYREF

  v18 = a3;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  v20 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v20);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v6 = dwMilliseconds;
  v19 = dwMilliseconds;
  v7 = 0;
  v16 = 0;
  v8 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v11 = 974;
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
    v10 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x29u, 0, &pAsync, v20, a1, a2, v18);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v10 = L"RPC call failed, hr = %#x";
    v11 = 976;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v11,
      v10,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
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
LABEL_29:
    v11 = 976;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v7 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[23],unsigned long &>(
      (__int64)"WLIDCAddUserToSsoGroup",
      (int *)&v19);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x3D0u,
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
      0x3D0u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v20);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x1800473e0  push    rsi
0x1800473e2  push    r12
0x1800473e4  push    r13
0x1800473e6  push    r14
0x1800473e8  push    r15
0x1800473ea  sub     rsp, 0F0h
0x1800473f1  mov     rax, cs:__security_cookie
0x1800473f8  xor     rax, rsp
0x1800473fb  mov     [rsp+118h+var_38], rax
0x180047403  mov     [rsp+118h+var_CC], r8d
0x180047408  mov     r13, rdx
0x18004740b  mov     r12, rcx
0x18004740e  mov     [rsp+118h+dwMilliseconds], 0
0x180047416  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x18004741b  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180047420  mov     [rsp+118h+Reply], 0
0x180047428  mov     [rsp+118h+var_C0], 0
0x180047431  lea     rcx, [rsp+118h+var_C0]; this
0x180047436  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18004743b  mov     [rsp+118h+Reply], eax
0x18004743f  test    eax, eax
0x180047441  js      loc_180047721
0x180047447  xor     edx, edx; Val
0x180047449  lea     r8d, [rdx+70h]; Size
0x18004744d  lea     rcx, [rsp+118h+pAsync]; void *
0x180047452  call    memset_0
0x180047457  mov     esi, [rsp+118h+dwMilliseconds]
0x18004745b  mov     [rsp+118h+dwMilliseconds], esi
0x18004745f  mov     [rsp+118h+var_C8], esi
0x180047463  xor     r15b, r15b
0x180047466  mov     [rsp+118h+var_D4], r15b
0x18004746b  xor     r14b, r14b
0x18004746e  xorps   xmm0, xmm0
0x180047471  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x180047476  mov     edx, 70h ; 'p'; Size
0x18004747b  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180047480  call    cs:__imp_RpcAsyncInitializeHandle
0x180047486  test    eax, eax
0x180047488  jz      short loc_1800474A6
0x18004748a  jle     short loc_180047494
0x18004748c  movzx   eax, ax
0x18004748f  or      eax, 80070000h
0x180047494  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004749b  mov     r8d, 3CEh
0x1800474a1  jmp     loc_18004765A
0x1800474a6  mov     [rsp+118h+pAsync.UserInfo], 0
0x1800474b2  mov     [rsp+118h+pAsync.NotificationType], 1
0x1800474bd  xor     r9d, r9d; lpName
0x1800474c0  xor     r8d, r8d; bInitialState
0x1800474c3  xor     edx, edx; bManualReset
0x1800474c5  xor     ecx, ecx; lpEventAttributes
0x1800474c7  call    cs:__imp_CreateEventW
0x1800474cd  mov     qword ptr [rsp+118h+pAsync.u], rax
0x1800474d5  test    rax, rax
0x1800474d8  jnz     short loc_1800474F5
0x1800474da  call    cs:__imp_GetLastError
0x1800474e0  test    eax, eax
0x1800474e2  jle     short loc_1800474EC
0x1800474e4  movzx   eax, ax
0x1800474e7  or      eax, 80070000h
0x1800474ec  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x1800474f3  jmp     short loc_18004749B
0x1800474f5  mov     [rsp+118h+Handles], rax
0x1800474fa  mov     eax, [rsp+118h+var_CC]
0x1800474fe  mov     [rsp+118h+var_E0], eax
0x180047502  mov     [rsp+118h+var_E8], r13
0x180047507  mov     [rsp+118h+var_F0], r12
0x18004750c  mov     rax, [rsp+118h+var_C0]
0x180047511  mov     qword ptr [rsp+118h+bAlertable], rax
0x180047516  lea     r9, [rsp+118h+pAsync]
0x18004751b  xor     r8d, r8d; pReturnValue
0x18004751e  lea     edx, [r8+29h]; nProcNum
0x180047522  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180047529  call    cs:__imp_Ndr64AsyncClientCall
0x18004752f  mov     eax, [rsp+118h+Reply]
0x180047533  jmp     short loc_180047584
0x180047535  test    eax, eax
0x180047537  jle     short loc_180047541
0x180047539  movzx   eax, ax
0x18004753c  or      eax, 80070000h
0x180047541  mov     [rsp+118h+Reply], eax
0x180047545  mov     [rsp+118h+bAlertable], eax
0x180047549  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180047550  mov     r8d, 3D0h; unsigned int
0x180047556  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004755d  mov     ecx, 2; unsigned __int8
0x180047562  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180047567  mov     eax, [rsp+118h+Reply]
0x18004756b  test    eax, eax
0x18004756d  js      short loc_180047578
0x18004756f  mov     eax, 8000FFFFh
0x180047574  mov     [rsp+118h+Reply], eax
0x180047578  mov     esi, [rsp+118h+dwMilliseconds]
0x18004757c  mov     r15b, [rsp+118h+var_D4]
0x180047581  mov     r14b, r15b
0x180047584  test    eax, eax
0x180047586  jns     short loc_18004759A
0x180047588  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004758f  mov     r8d, 3D0h
0x180047595  jmp     loc_18004765E
0x18004759a  mov     [rsp+118h+bAlertable], 0; bAlertable
0x1800475a2  mov     r9d, esi; dwMilliseconds
0x1800475a5  xor     r8d, r8d; bWaitAll
0x1800475a8  lea     rdx, [rsp+118h+Handles]; lpHandles
0x1800475ad  lea     ecx, [r8+1]; nCount
0x1800475b1  call    cs:__imp_WaitForMultipleObjectsEx
0x1800475b7  mov     esi, eax
0x1800475b9  mov     r12d, 102h
0x1800475bf  test    r14b, r14b
0x1800475c2  jnz     short loc_180047610
0x1800475c4  cmp     esi, r12d
0x1800475c7  jz      short loc_1800475CE
0x1800475c9  cmp     esi, 1
0x1800475cc  jnz     short loc_180047610
0x1800475ce  mov     edx, 1; fAbort
0x1800475d3  lea     rcx, [rsp+118h+pAsync]; pAsync
0x1800475d8  call    cs:__imp_RpcAsyncCancelCall
0x1800475de  cmp     esi, r12d
0x1800475e1  jnz     short loc_1800475E8
0x1800475e3  mov     r15b, 1
0x1800475e6  jmp     short loc_1800475EB
0x1800475e8  mov     r14b, 1
0x1800475eb  mov     [rsp+118h+bAlertable], 0; bAlertable
0x1800475f3  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800475f7  xor     r8d, r8d; bWaitAll
0x1800475fa  lea     rdx, [rsp+118h+Handles]; lpHandles
0x1800475ff  lea     ecx, [r8+1]; nCount
0x180047603  call    cs:__imp_WaitForMultipleObjectsEx
0x180047609  mov     esi, eax
0x18004760b  test    r15b, r15b
0x18004760e  jz      short loc_1800475BF
0x180047610  test    esi, esi
0x180047612  jz      short loc_18004762F
0x180047614  call    cs:__imp_GetLastError
0x18004761a  test    eax, eax
0x18004761c  jle     short loc_180047626
0x18004761e  movzx   eax, ax
0x180047621  or      eax, 80070000h
0x180047626  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004762d  jmp     short loc_180047654
0x18004762f  lea     rdx, [rsp+118h+Reply]; Reply
0x180047634  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180047639  call    cs:__imp_RpcAsyncCompleteCall
0x18004763f  test    eax, eax
0x180047641  jz      short loc_180047673
0x180047643  jle     short loc_18004764D
0x180047645  movzx   eax, ax
0x180047648  or      eax, 80070000h
0x18004764d  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180047654  mov     r8d, 3D0h; unsigned int
0x18004765a  mov     [rsp+118h+Reply], eax
0x18004765e  mov     [rsp+118h+bAlertable], eax
0x180047662  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180047669  mov     ecx, 2; unsigned __int8
0x18004766e  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180047673  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x18004767b  test    rcx, rcx
0x18004767e  jz      short loc_180047686
0x180047680  call    cs:__imp_CloseHandle
0x180047686  test    r15b, r15b
0x180047689  jz      short loc_1800476CA
0x18004768b  mov     [rsp+118h+Reply], 800705B4h
0x180047693  lea     rdx, [rsp+118h+var_C8]
0x180047698  lea     rcx, aWlidcadduserto; "WLIDCAddUserToSsoGroup"
0x18004769f  call    ??$RPCCallTimedOut@AEAY0BH@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BH@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[23],ulong &>(char const (&)[23],ulong &)
0x1800476a4  mov     eax, [rsp+118h+Reply]
0x1800476a8  mov     [rsp+118h+bAlertable], eax
0x1800476ac  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x1800476b3  mov     r8d, 3D0h; unsigned int
0x1800476b9  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800476c0  mov     ecx, 2; unsigned __int8
0x1800476c5  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800476ca  test    r14b, r14b
0x1800476cd  jz      short loc_1800476FA
0x1800476cf  mov     eax, 800704C7h
0x1800476d4  mov     [rsp+118h+Reply], eax
0x1800476d8  mov     [rsp+118h+bAlertable], eax
0x1800476dc  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x1800476e3  mov     r8d, 3D0h; unsigned int
0x1800476e9  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800476f0  mov     ecx, 2; unsigned __int8
0x1800476f5  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800476fa  cmp     [rsp+118h+Reply], 800706B5h
0x180047702  jz      short loc_18004770E
0x180047704  cmp     [rsp+118h+Reply], 800706BAh
0x18004770c  jnz     short loc_180047713
0x18004770e  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180047713  lea     rcx, [rsp+118h+var_C0]; this
0x180047718  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18004771d  mov     eax, [rsp+118h+Reply]
0x180047721  mov     rcx, [rsp+118h+var_38]
0x180047729  xor     rcx, rsp; StackCookie
0x18004772c  call    __security_check_cookie
0x180047731  add     rsp, 0F0h
0x180047738  pop     r15
0x18004773a  pop     r14
0x18004773c  pop     r13
0x18004773e  pop     r12
0x180047740  pop     rsi
0x180047741  retn
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
