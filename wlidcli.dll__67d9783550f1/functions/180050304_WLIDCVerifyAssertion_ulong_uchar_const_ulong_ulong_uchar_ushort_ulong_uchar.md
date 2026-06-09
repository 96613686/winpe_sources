# WLIDCVerifyAssertion(ulong,uchar const *,ulong *,ulong,uchar *,ushort * *,ulong *,uchar * *)

- ea: `0x180050304`
- end: `0x18005071c`
- name: `?WLIDCVerifyAssertion@@YAJKPEBEPEAKKPEAEPEAPEAG1PEAPEAE@Z`
- size: `1048`
- prototype: `__int64 __fastcall(unsigned int, const unsigned __int8 *, unsigned int *, unsigned int, unsigned __int8 *, unsigned __int16 **, unsigned int *, unsigned __int8 **)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180025ec0`
- `0x180034e60`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180044fc4`
- `0x180046ce0`
- `0x18004cd04`
- `0x180050304`
- `0x180050c84`
- `0x180050e40`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18005057c`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800505d4`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18005057c`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800505d4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180050445`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180050445`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050458`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800505e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050458`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800505e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050654`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050654`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800505a6`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800505a6`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800504f1`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800504f1`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18005060d`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18005060d`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800503fe`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800503fe`

## string_xrefs

- `0x18005046a`: `RPC failed to create new event, hr = %#x`
- `0x180050621`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCVerifyAssertion(
        unsigned int a1,
        const unsigned __int8 *a2,
        unsigned int *a3,
        int a4,
        unsigned __int8 *a5,
        unsigned __int16 **a6,
        unsigned int *a7,
        unsigned __int8 **a8)
{
  __int64 result; // rax
  DWORD v11; // esi
  char v12; // r15
  char v13; // r14
  int LastError; // eax
  const unsigned __int16 *v15; // r9
  unsigned int v16; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v18; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-158h]
  int Reply; // [rsp+70h] [rbp-108h] BYREF
  char v21; // [rsp+74h] [rbp-104h]
  DWORD dwMilliseconds; // [rsp+78h] [rbp-100h] BYREF
  int v23; // [rsp+7Ch] [rbp-FCh]
  DWORD v24; // [rsp+80h] [rbp-F8h] BYREF
  __int64 v25; // [rsp+88h] [rbp-F0h] BYREF
  unsigned __int8 **v26; // [rsp+90h] [rbp-E8h]
  unsigned int *v27; // [rsp+98h] [rbp-E0h]
  unsigned __int16 **v28; // [rsp+A0h] [rbp-D8h]
  unsigned __int8 *v29; // [rsp+A8h] [rbp-D0h]
  unsigned int *v30; // [rsp+B0h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+B8h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+D0h] [rbp-A8h] BYREF

  v23 = a4;
  v30 = a3;
  v29 = a5;
  v28 = a6;
  v27 = a7;
  v26 = a8;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue(a1, (unsigned int)a2, &dwMilliseconds);
  v25 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v25);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v11 = dwMilliseconds;
  v24 = dwMilliseconds;
  v12 = 0;
  v21 = 0;
  v13 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v15 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v16 = 872;
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
    v15 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall(
    (MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo,
    0x1Du,
    0,
    &pAsync,
    v25,
    a1,
    a2,
    v30,
    v23,
    v29,
    v28,
    v27,
    v26);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v15 = L"RPC call failed, hr = %#x";
    v16 = 874;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v16,
      v15,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
  v18 = WaitForMultipleObjectsEx(1u, Handles, 0, v11, 0);
  do
  {
    if ( v13 || v18 != 258 && v18 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v18 == 258 )
      v12 = 1;
    else
      v13 = 1;
    v18 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v12 );
  if ( v18 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v15 = L"Encountered error while waiting on RPC call, hr = %#x";
LABEL_29:
    v16 = 874;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v15 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v12 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],unsigned long &>(
      (__int64)"WLIDCVerifyAssertion",
      (int *)&v24);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x36Au,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v13 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x36Au,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v25);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x180050304  push    rsi
0x180050306  push    r12
0x180050308  push    r13
0x18005030a  push    r14
0x18005030c  push    r15
0x18005030e  sub     rsp, 150h
0x180050315  mov     rax, cs:__security_cookie
0x18005031c  xor     rax, rsp
0x18005031f  mov     [rsp+178h+var_38], rax
0x180050327  mov     [rsp+178h+var_FC], r9d
0x18005032c  mov     [rsp+178h+var_C8], r8
0x180050334  mov     r13, rdx
0x180050337  mov     r12d, ecx
0x18005033a  mov     rax, [rsp+178h+arg_20]
0x180050342  mov     [rsp+178h+var_D0], rax
0x18005034a  mov     rax, [rsp+178h+arg_28]
0x180050352  mov     [rsp+178h+var_D8], rax
0x18005035a  mov     rax, [rsp+178h+arg_30]
0x180050362  mov     [rsp+178h+var_E0], rax
0x18005036a  mov     rax, [rsp+178h+arg_38]
0x180050372  mov     [rsp+178h+var_E8], rax
0x18005037a  mov     [rsp+178h+dwMilliseconds], 0
0x180050382  lea     r8, [rsp+178h+dwMilliseconds]; unsigned int *
0x180050387  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18005038c  mov     [rsp+178h+Reply], 0
0x180050394  mov     [rsp+178h+var_F0], 0
0x1800503a0  lea     rcx, [rsp+178h+var_F0]; this
0x1800503a8  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x1800503ad  mov     [rsp+178h+Reply], eax
0x1800503b1  test    eax, eax
0x1800503b3  js      loc_1800506FB
0x1800503b9  xor     edx, edx; Val
0x1800503bb  lea     r8d, [rdx+70h]; Size
0x1800503bf  lea     rcx, [rsp+178h+pAsync]; void *
0x1800503c7  call    memset_0
0x1800503cc  mov     esi, [rsp+178h+dwMilliseconds]
0x1800503d0  mov     [rsp+178h+dwMilliseconds], esi
0x1800503d4  mov     [rsp+178h+var_F8], esi
0x1800503db  xor     r15b, r15b
0x1800503de  mov     [rsp+178h+var_104], r15b
0x1800503e3  xor     r14b, r14b
0x1800503e6  xorps   xmm0, xmm0
0x1800503e9  movups  xmmword ptr [rsp+178h+Handles], xmm0
0x1800503f1  mov     edx, 70h ; 'p'; Size
0x1800503f6  lea     rcx, [rsp+178h+pAsync]; pAsync
0x1800503fe  call    cs:__imp_RpcAsyncInitializeHandle
0x180050404  test    eax, eax
0x180050406  jz      short loc_180050424
0x180050408  jle     short loc_180050412
0x18005040a  movzx   eax, ax
0x18005040d  or      eax, 80070000h
0x180050412  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180050419  mov     r8d, 368h
0x18005041f  jmp     loc_18005062E
0x180050424  mov     [rsp+178h+pAsync.UserInfo], 0
0x180050430  mov     [rsp+178h+pAsync.NotificationType], 1
0x18005043b  xor     r9d, r9d; lpName
0x18005043e  xor     r8d, r8d; bInitialState
0x180050441  xor     edx, edx; bManualReset
0x180050443  xor     ecx, ecx; lpEventAttributes
0x180050445  call    cs:__imp_CreateEventW
0x18005044b  mov     qword ptr [rsp+178h+pAsync.u], rax
0x180050453  test    rax, rax
0x180050456  jnz     short loc_180050473
0x180050458  call    cs:__imp_GetLastError
0x18005045e  test    eax, eax
0x180050460  jle     short loc_18005046A
0x180050462  movzx   eax, ax
0x180050465  or      eax, 80070000h
0x18005046a  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180050471  jmp     short loc_180050419
0x180050473  mov     [rsp+178h+Handles], rax
0x18005047b  mov     rax, [rsp+178h+var_E8]
0x180050483  mov     [rsp+178h+var_118], rax
0x180050488  mov     rax, [rsp+178h+var_E0]
0x180050490  mov     [rsp+178h+var_120], rax
0x180050495  mov     rax, [rsp+178h+var_D8]
0x18005049d  mov     [rsp+178h+var_128], rax
0x1800504a2  mov     rax, [rsp+178h+var_D0]
0x1800504aa  mov     [rsp+178h+var_130], rax
0x1800504af  mov     eax, [rsp+178h+var_FC]
0x1800504b3  mov     [rsp+178h+var_138], eax
0x1800504b7  mov     rax, [rsp+178h+var_C8]
0x1800504bf  mov     [rsp+178h+var_140], rax
0x1800504c4  mov     [rsp+178h+var_148], r13
0x1800504c9  mov     [rsp+178h+var_150], r12d
0x1800504ce  mov     rax, [rsp+178h+var_F0]
0x1800504d6  mov     qword ptr [rsp+178h+bAlertable], rax
0x1800504db  lea     r9, [rsp+178h+pAsync]
0x1800504e3  xor     r8d, r8d; pReturnValue
0x1800504e6  lea     edx, [r8+1Dh]; nProcNum
0x1800504ea  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800504f1  call    cs:__imp_Ndr64AsyncClientCall
0x1800504f7  mov     eax, [rsp+178h+Reply]
0x1800504fb  jmp     short loc_18005054C
0x1800504fd  test    eax, eax
0x1800504ff  jle     short loc_180050509
0x180050501  movzx   eax, ax
0x180050504  or      eax, 80070000h
0x180050509  mov     [rsp+178h+Reply], eax
0x18005050d  mov     [rsp+178h+bAlertable], eax
0x180050511  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180050518  mov     r8d, 36Ah; unsigned int
0x18005051e  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180050525  mov     ecx, 2; unsigned __int8
0x18005052a  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18005052f  mov     eax, [rsp+178h+Reply]
0x180050533  test    eax, eax
0x180050535  js      short loc_180050540
0x180050537  mov     eax, 8000FFFFh
0x18005053c  mov     [rsp+178h+Reply], eax
0x180050540  mov     esi, [rsp+178h+dwMilliseconds]
0x180050544  mov     r15b, [rsp+178h+var_104]
0x180050549  mov     r14b, r15b
0x18005054c  test    eax, eax
0x18005054e  jns     short loc_180050562
0x180050550  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180050557  mov     r8d, 36Ah
0x18005055d  jmp     loc_180050632
0x180050562  mov     [rsp+178h+bAlertable], 0; bAlertable
0x18005056a  mov     r9d, esi; dwMilliseconds
0x18005056d  xor     r8d, r8d; bWaitAll
0x180050570  lea     rdx, [rsp+178h+Handles]; lpHandles
0x180050578  lea     ecx, [r8+1]; nCount
0x18005057c  call    cs:__imp_WaitForMultipleObjectsEx
0x180050582  mov     esi, eax
0x180050584  mov     r12d, 102h
0x18005058a  test    r14b, r14b
0x18005058d  jnz     short loc_1800505E1
0x18005058f  cmp     esi, r12d
0x180050592  jz      short loc_180050599
0x180050594  cmp     esi, 1
0x180050597  jnz     short loc_1800505E1
0x180050599  mov     edx, 1; fAbort
0x18005059e  lea     rcx, [rsp+178h+pAsync]; pAsync
0x1800505a6  call    cs:__imp_RpcAsyncCancelCall
0x1800505ac  cmp     esi, r12d
0x1800505af  jnz     short loc_1800505B6
0x1800505b1  mov     r15b, 1
0x1800505b4  jmp     short loc_1800505B9
0x1800505b6  mov     r14b, 1
0x1800505b9  mov     [rsp+178h+bAlertable], 0; bAlertable
0x1800505c1  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800505c5  xor     r8d, r8d; bWaitAll
0x1800505c8  lea     rdx, [rsp+178h+Handles]; lpHandles
0x1800505d0  lea     ecx, [r8+1]; nCount
0x1800505d4  call    cs:__imp_WaitForMultipleObjectsEx
0x1800505da  mov     esi, eax
0x1800505dc  test    r15b, r15b
0x1800505df  jz      short loc_18005058A
0x1800505e1  test    esi, esi
0x1800505e3  jz      short loc_180050600
0x1800505e5  call    cs:__imp_GetLastError
0x1800505eb  test    eax, eax
0x1800505ed  jle     short loc_1800505F7
0x1800505ef  movzx   eax, ax
0x1800505f2  or      eax, 80070000h
0x1800505f7  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x1800505fe  jmp     short loc_180050628
0x180050600  lea     rdx, [rsp+178h+Reply]; Reply
0x180050605  lea     rcx, [rsp+178h+pAsync]; pAsync
0x18005060d  call    cs:__imp_RpcAsyncCompleteCall
0x180050613  test    eax, eax
0x180050615  jz      short loc_180050647
0x180050617  jle     short loc_180050621
0x180050619  movzx   eax, ax
0x18005061c  or      eax, 80070000h
0x180050621  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180050628  mov     r8d, 36Ah; unsigned int
0x18005062e  mov     [rsp+178h+Reply], eax
0x180050632  mov     [rsp+178h+bAlertable], eax
0x180050636  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18005063d  mov     ecx, 2; unsigned __int8
0x180050642  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180050647  mov     rcx, qword ptr [rsp+178h+pAsync.u]; hObject
0x18005064f  test    rcx, rcx
0x180050652  jz      short loc_18005065A
0x180050654  call    cs:__imp_CloseHandle
0x18005065a  test    r15b, r15b
0x18005065d  jz      short loc_1800506A1
0x18005065f  mov     [rsp+178h+Reply], 800705B4h
0x180050667  lea     rdx, [rsp+178h+var_F8]
0x18005066f  lea     rcx, aWlidcverifyass; "WLIDCVerifyAssertion"
0x180050676  call    ??$RPCCallTimedOut@AEAY0BF@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BF@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],ulong &>(char const (&)[21],ulong &)
0x18005067b  mov     eax, [rsp+178h+Reply]
0x18005067f  mov     [rsp+178h+bAlertable], eax
0x180050683  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18005068a  mov     r8d, 36Ah; unsigned int
0x180050690  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180050697  mov     ecx, 2; unsigned __int8
0x18005069c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800506a1  test    r14b, r14b
0x1800506a4  jz      short loc_1800506D1
0x1800506a6  mov     eax, 800704C7h
0x1800506ab  mov     [rsp+178h+Reply], eax
0x1800506af  mov     [rsp+178h+bAlertable], eax
0x1800506b3  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x1800506ba  mov     r8d, 36Ah; unsigned int
0x1800506c0  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800506c7  mov     ecx, 2; unsigned __int8
0x1800506cc  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800506d1  cmp     [rsp+178h+Reply], 800706B5h
0x1800506d9  jz      short loc_1800506E5
0x1800506db  cmp     [rsp+178h+Reply], 800706BAh
0x1800506e3  jnz     short loc_1800506EA
0x1800506e5  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x1800506ea  lea     rcx, [rsp+178h+var_F0]; this
0x1800506f2  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x1800506f7  mov     eax, [rsp+178h+Reply]
0x1800506fb  mov     rcx, [rsp+178h+var_38]
0x180050703  xor     rcx, rsp; StackCookie
0x180050706  call    __security_check_cookie
0x18005070b  add     rsp, 150h
0x180050712  pop     r15
0x180050714  pop     r14
0x180050716  pop     r13
0x180050718  pop     r12
0x18005071a  pop     rsi
0x18005071b  retn
0x180061a37  push    rbp
0x180061a39  sub     rsp, 70h
0x180061a3d  mov     rbp, rdx
0x180061a40  mov     rcx, [rcx]
0x180061a43  mov     ecx, [rcx]; unsigned int
0x180061a45  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x180061a4a  nop
0x180061a4b  add     rsp, 70h
0x180061a4f  pop     rbp
0x180061a50  retn
```
