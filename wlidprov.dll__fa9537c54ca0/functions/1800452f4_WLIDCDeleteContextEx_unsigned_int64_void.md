# WLIDCDeleteContextEx(unsigned __int64,void * *)

- ea: `0x1800452f4`
- end: `0x180045640`
- name: `?WLIDCDeleteContextEx@@YAJ_KPEAPEAX@Z`
- size: `844`
- prototype: `int(unsigned __int64, void **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180013330`
- `0x180041670`

## callees

- `0x18000a400`
- `0x180010c68`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180041c80`
- `0x180043240`
- `0x1800452f4`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800453bf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800453bf`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004549c`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800454ee`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004549c`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800454ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800453d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800454ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800453d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800454ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004556b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004556b`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004537b`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004537b`
- `RPCRT4!RpcSsDestroyClientContext` at `0x180045607`
- `RPCRT4!RpcSsDestroyClientContext` at `0x180045607`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800454c3`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800454c3`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004540f`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004540f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180045524`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180045524`

## string_xrefs

- `0x1800453e4`: `RPC failed to create new event, hr = %#x`
- `0x180045538`: `RPC Async complete call failed, hr = %#x`
- `0x180045583`: `WLIDCDeleteContextEx`

## pseudocode

```c
__int64 __fastcall WLIDCDeleteContextEx(__int64 a1, void **a2)
{
  DWORD v4; // esi
  char v5; // r12
  char v6; // r14
  int LastError; // eax
  const unsigned __int16 *v8; // r9
  unsigned int v9; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v11; // esi
  int v12; // eax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-D8h]
  int Reply; // [rsp+30h] [rbp-C8h] BYREF
  char v16; // [rsp+34h] [rbp-C4h]
  DWORD dwMilliseconds; // [rsp+38h] [rbp-C0h] BYREF
  DWORD v18; // [rsp+3Ch] [rbp-BCh] BYREF
  void **v19; // [rsp+40h] [rbp-B8h]
  HANDLE Handles[3]; // [rsp+48h] [rbp-B0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+60h] [rbp-98h] BYREF

  v19 = a2;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue(a1, (unsigned int)a2, &dwMilliseconds);
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
    v9 = 621;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0xDu, 0, &pAsync, a1, a2);
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
  v9 = 623;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],unsigned long &>("WLIDCDeleteContextEx", &v18);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x26Fu,
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
      0x26Fu,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  v12 = Reply;
  if ( Reply == -2147023179 || Reply == -2147023174 )
  {
    TraceServiceStatus();
    v12 = Reply;
  }
  if ( v12 < 0 )
  {
    RpcSsDestroyClientContext(a2);
    *a2 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800452f4  mov     [rsp+arg_10], rsi
0x1800452f9  mov     [rsp+arg_18], r12
0x1800452fe  push    r13
0x180045300  push    r14
0x180045302  push    r15
0x180045304  sub     rsp, 0E0h
0x18004530b  mov     rax, cs:__security_cookie
0x180045312  xor     rax, rsp
0x180045315  mov     [rsp+0F8h+var_28], rax
0x18004531d  mov     r15, rdx
0x180045320  mov     r13, rcx
0x180045323  mov     [rsp+0F8h+var_B8], rdx
0x180045328  mov     [rsp+0F8h+Reply], 0
0x180045330  mov     [rsp+0F8h+dwMilliseconds], 0
0x180045338  lea     r8, [rsp+0F8h+dwMilliseconds]; unsigned int *
0x18004533d  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180045342  xor     edx, edx; Val
0x180045344  lea     r8d, [rdx+70h]; Size
0x180045348  lea     rcx, [rsp+0F8h+pAsync]; void *
0x18004534d  call    memset_0
0x180045352  mov     esi, [rsp+0F8h+dwMilliseconds]
0x180045356  mov     [rsp+0F8h+dwMilliseconds], esi
0x18004535a  mov     [rsp+0F8h+var_BC], esi
0x18004535e  xor     r12b, r12b
0x180045361  mov     [rsp+0F8h+var_C4], r12b
0x180045366  xor     r14b, r14b
0x180045369  xorps   xmm0, xmm0
0x18004536c  movups  xmmword ptr [rsp+0F8h+Handles], xmm0
0x180045371  mov     edx, 70h ; 'p'; Size
0x180045376  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x18004537b  call    cs:__imp_RpcAsyncInitializeHandle
0x180045381  test    eax, eax
0x180045383  jz      short loc_1800453A1
0x180045385  jle     short loc_18004538F
0x180045387  movzx   eax, ax
0x18004538a  or      eax, 80070000h
0x18004538f  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180045396  mov     r8d, 26Dh
0x18004539c  jmp     loc_180045545
0x1800453a1  mov     [rsp+0F8h+pAsync.UserInfo], 0
0x1800453aa  mov     [rsp+0F8h+pAsync.NotificationType], 1
0x1800453b5  xor     r9d, r9d; lpName
0x1800453b8  xor     r8d, r8d; bInitialState
0x1800453bb  xor     edx, edx; bManualReset
0x1800453bd  xor     ecx, ecx; lpEventAttributes
0x1800453bf  call    cs:__imp_CreateEventW
0x1800453c5  mov     qword ptr [rsp+0F8h+pAsync.u], rax
0x1800453cd  test    rax, rax
0x1800453d0  jnz     short loc_1800453ED
0x1800453d2  call    cs:__imp_GetLastError
0x1800453d8  test    eax, eax
0x1800453da  jle     short loc_1800453E4
0x1800453dc  movzx   eax, ax
0x1800453df  or      eax, 80070000h
0x1800453e4  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x1800453eb  jmp     short loc_180045396
0x1800453ed  mov     [rsp+0F8h+Handles], rax
0x1800453f2  mov     [rsp+0F8h+var_D0], r15
0x1800453f7  mov     qword ptr [rsp+0F8h+bAlertable], r13
0x1800453fc  lea     r9, [rsp+0F8h+pAsync]
0x180045401  xor     r8d, r8d; pReturnValue
0x180045404  lea     edx, [r8+0Dh]; nProcNum
0x180045408  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004540f  call    cs:__imp_Ndr64AsyncClientCall
0x180045415  mov     eax, [rsp+0F8h+Reply]
0x180045419  jmp     short loc_18004546F
0x18004541b  test    eax, eax
0x18004541d  jle     short loc_180045427
0x18004541f  movzx   eax, ax
0x180045422  or      eax, 80070000h
0x180045427  mov     [rsp+0F8h+Reply], eax
0x18004542b  mov     [rsp+0F8h+bAlertable], eax
0x18004542f  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180045436  mov     r8d, 26Fh; unsigned int
0x18004543c  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180045443  mov     ecx, 2; unsigned __int8
0x180045448  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004544d  mov     eax, [rsp+0F8h+Reply]
0x180045451  test    eax, eax
0x180045453  js      short loc_18004545E
0x180045455  mov     eax, 8000FFFFh
0x18004545a  mov     [rsp+0F8h+Reply], eax
0x18004545e  mov     esi, [rsp+0F8h+dwMilliseconds]
0x180045462  mov     r12b, [rsp+0F8h+var_C4]
0x180045467  mov     r14b, r12b
0x18004546a  mov     r15, [rsp+0F8h+var_B8]
0x18004546f  test    eax, eax
0x180045471  jns     short loc_180045485
0x180045473  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004547a  mov     r8d, 26Fh
0x180045480  jmp     loc_180045549
0x180045485  mov     [rsp+0F8h+bAlertable], 0; bAlertable
0x18004548d  mov     r9d, esi; dwMilliseconds
0x180045490  xor     r8d, r8d; bWaitAll
0x180045493  lea     rdx, [rsp+0F8h+Handles]; lpHandles
0x180045498  lea     ecx, [r8+1]; nCount
0x18004549c  call    cs:__imp_WaitForMultipleObjectsEx
0x1800454a2  mov     esi, eax
0x1800454a4  mov     r13d, 102h
0x1800454aa  test    r14b, r14b
0x1800454ad  jnz     short loc_1800454FB
0x1800454af  cmp     esi, r13d
0x1800454b2  jz      short loc_1800454B9
0x1800454b4  cmp     esi, 1
0x1800454b7  jnz     short loc_1800454FB
0x1800454b9  mov     edx, 1; fAbort
0x1800454be  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x1800454c3  call    cs:__imp_RpcAsyncCancelCall
0x1800454c9  cmp     esi, r13d
0x1800454cc  jnz     short loc_1800454D3
0x1800454ce  mov     r12b, 1
0x1800454d1  jmp     short loc_1800454D6
0x1800454d3  mov     r14b, 1
0x1800454d6  mov     [rsp+0F8h+bAlertable], 0; bAlertable
0x1800454de  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800454e2  xor     r8d, r8d; bWaitAll
0x1800454e5  lea     rdx, [rsp+0F8h+Handles]; lpHandles
0x1800454ea  lea     ecx, [r8+1]; nCount
0x1800454ee  call    cs:__imp_WaitForMultipleObjectsEx
0x1800454f4  mov     esi, eax
0x1800454f6  test    r12b, r12b
0x1800454f9  jz      short loc_1800454AA
0x1800454fb  test    esi, esi
0x1800454fd  jz      short loc_18004551A
0x1800454ff  call    cs:__imp_GetLastError
0x180045505  test    eax, eax
0x180045507  jle     short loc_180045511
0x180045509  movzx   eax, ax
0x18004550c  or      eax, 80070000h
0x180045511  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180045518  jmp     short loc_18004553F
0x18004551a  lea     rdx, [rsp+0F8h+Reply]; Reply
0x18004551f  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x180045524  call    cs:__imp_RpcAsyncCompleteCall
0x18004552a  test    eax, eax
0x18004552c  jz      short loc_18004555E
0x18004552e  jle     short loc_180045538
0x180045530  movzx   eax, ax
0x180045533  or      eax, 80070000h
0x180045538  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004553f  mov     r8d, 26Fh; unsigned int
0x180045545  mov     [rsp+0F8h+Reply], eax
0x180045549  mov     [rsp+0F8h+bAlertable], eax
0x18004554d  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180045554  mov     ecx, 2; unsigned __int8
0x180045559  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004555e  mov     rcx, qword ptr [rsp+0F8h+pAsync.u]; hObject
0x180045566  test    rcx, rcx
0x180045569  jz      short loc_180045571
0x18004556b  call    cs:__imp_CloseHandle
0x180045571  test    r12b, r12b
0x180045574  jz      short loc_1800455B5
0x180045576  mov     [rsp+0F8h+Reply], 800705B4h
0x18004557e  lea     rdx, [rsp+0F8h+var_BC]
0x180045583  lea     rcx, aWlidcdeletecon; "WLIDCDeleteContextEx"
0x18004558a  call    ??$RPCCallTimedOut@AEAY0BF@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BF@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],ulong &>(char const (&)[21],ulong &)
0x18004558f  mov     eax, [rsp+0F8h+Reply]
0x180045593  mov     [rsp+0F8h+bAlertable], eax
0x180045597  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004559e  mov     r8d, 26Fh; unsigned int
0x1800455a4  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800455ab  mov     ecx, 2; unsigned __int8
0x1800455b0  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800455b5  test    r14b, r14b
0x1800455b8  jz      short loc_1800455E5
0x1800455ba  mov     eax, 800704C7h
0x1800455bf  mov     [rsp+0F8h+Reply], eax
0x1800455c3  mov     [rsp+0F8h+bAlertable], eax
0x1800455c7  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x1800455ce  mov     r8d, 26Fh; unsigned int
0x1800455d4  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800455db  mov     ecx, 2; unsigned __int8
0x1800455e0  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800455e5  mov     eax, [rsp+0F8h+Reply]
0x1800455e9  cmp     eax, 800706B5h
0x1800455ee  jz      short loc_1800455F7
0x1800455f0  cmp     eax, 800706BAh
0x1800455f5  jnz     short loc_180045600
0x1800455f7  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x1800455fc  mov     eax, [rsp+0F8h+Reply]
0x180045600  test    eax, eax
0x180045602  jns     short loc_180045614
0x180045604  mov     rcx, r15; ContextHandle
0x180045607  call    cs:__imp_RpcSsDestroyClientContext
0x18004560d  mov     qword ptr [r15], 0
0x180045614  xor     eax, eax
0x180045616  mov     rcx, [rsp+0F8h+var_28]
0x18004561e  xor     rcx, rsp; StackCookie
0x180045621  call    __security_check_cookie
0x180045626  lea     r11, [rsp+0F8h+var_18]
0x18004562e  mov     rsi, [r11+30h]
0x180045632  mov     r12, [r11+38h]
0x180045636  mov     rsp, r11
0x180045639  pop     r15
0x18004563b  pop     r14
0x18004563d  pop     r13
0x18004563f  retn
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
