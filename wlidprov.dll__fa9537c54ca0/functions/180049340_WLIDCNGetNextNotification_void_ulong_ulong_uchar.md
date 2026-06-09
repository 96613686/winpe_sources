# WLIDCNGetNextNotification(void *,ulong *,ulong *,uchar * *)

- ea: `0x180049340`
- end: `0x180049692`
- name: `?WLIDCNGetNextNotification@@YAJPEAXPEAK1PEAPEAE@Z`
- size: `850`
- prototype: `__int64 __fastcall(void *, unsigned int *, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800027e0`

## callees

- `0x18000a400`
- `0x18000f870`
- `0x180011588`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180041f38`
- `0x180043240`
- `0x180049340`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180049419`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180049419`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180049506`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004955a`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180049506`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004955a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004942c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004956d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004942c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004956d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800495d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800495d6`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800493cd`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800493cd`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004952f`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004952f`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004947a`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004947a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180049592`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180049592`

## string_xrefs

- `0x18004943e`: `RPC failed to create new event, hr = %#x`
- `0x1800495a6`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCNGetNextNotification(void *a1, unsigned int *a2, unsigned int *a3, unsigned __int8 **a4)
{
  __int64 result; // rax
  char v8; // r12
  char v9; // r15
  int LastError; // eax
  const unsigned __int16 *v11; // r9
  unsigned int v12; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v14; // r14d
  BOOL bAlertable[2]; // [rsp+20h] [rbp-F8h]
  int Reply; // [rsp+40h] [rbp-D8h] BYREF
  char v17; // [rsp+44h] [rbp-D4h]
  int v18; // [rsp+48h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+50h] [rbp-C8h] BYREF
  unsigned __int8 **v20; // [rsp+58h] [rbp-C0h]
  HANDLE Handles[2]; // [rsp+60h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-A8h] BYREF

  v20 = a4;
  v19 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v19);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v18 = 600000;
  v8 = 0;
  v17 = 0;
  v9 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v11 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v12 = 1192;
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
    v11 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvcnotify_ProxyInfo, 2u, 0, &pAsync, a1, a2, a3, v20);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v11 = L"RPC call failed, hr = %#x";
    v12 = 1194;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v12,
      v11,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
  v14 = WaitForMultipleObjectsEx(1u, Handles, 0, 0x927C0u, 0);
  do
  {
    if ( v9 || v14 != 258 && v14 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v14 == 258 )
      v8 = 1;
    else
      v9 = 1;
    v14 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v8 );
  if ( v14 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v11 = L"Encountered error while waiting on RPC call, hr = %#x";
LABEL_29:
    v12 = 1194;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v11 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v8 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[26],unsigned long &>("WLIDCNGetNextNotification", &v18);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x4AAu,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v9 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x4AAu,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v19);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x180049340  push    rdi
0x180049342  push    r12
0x180049344  push    r13
0x180049346  push    r14
0x180049348  push    r15
0x18004934a  sub     rsp, 0F0h
0x180049351  mov     rax, cs:__security_cookie
0x180049358  xor     rax, rsp
0x18004935b  mov     [rsp+118h+var_38], rax
0x180049363  mov     [rsp+118h+var_C0], r9
0x180049368  mov     r13, r8
0x18004936b  mov     r14, rdx
0x18004936e  mov     rdi, rcx
0x180049371  mov     [rsp+118h+Reply], 0
0x180049379  mov     [rsp+118h+var_C8], 0
0x180049382  lea     rcx, [rsp+118h+var_C8]; this
0x180049387  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18004938c  mov     [rsp+118h+Reply], eax
0x180049390  test    eax, eax
0x180049392  js      loc_180049671
0x180049398  xor     edx, edx; Val
0x18004939a  lea     r8d, [rdx+70h]; Size
0x18004939e  lea     rcx, [rsp+118h+pAsync]; void *
0x1800493a3  call    memset_0
0x1800493a8  mov     [rsp+118h+var_D0], 927C0h
0x1800493b0  xor     r12b, r12b
0x1800493b3  mov     [rsp+118h+var_D4], r12b
0x1800493b8  xor     r15b, r15b
0x1800493bb  xorps   xmm0, xmm0
0x1800493be  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x1800493c3  mov     edx, 70h ; 'p'; Size
0x1800493c8  lea     rcx, [rsp+118h+pAsync]; pAsync
0x1800493cd  call    cs:__imp_RpcAsyncInitializeHandle
0x1800493d3  test    eax, eax
0x1800493d5  jz      short loc_1800493F8
0x1800493d7  jle     short loc_1800493E1
0x1800493d9  movzx   eax, ax
0x1800493dc  or      eax, 80070000h
0x1800493e1  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x1800493e8  mov     r8d, 4A8h
0x1800493ee  mov     edi, 2
0x1800493f3  jmp     loc_1800495B3
0x1800493f8  mov     [rsp+118h+pAsync.UserInfo], 0
0x180049404  mov     [rsp+118h+pAsync.NotificationType], 1
0x18004940f  xor     r9d, r9d; lpName
0x180049412  xor     r8d, r8d; bInitialState
0x180049415  xor     edx, edx; bManualReset
0x180049417  xor     ecx, ecx; lpEventAttributes
0x180049419  call    cs:__imp_CreateEventW
0x18004941f  mov     qword ptr [rsp+118h+pAsync.u], rax
0x180049427  test    rax, rax
0x18004942a  jnz     short loc_180049447
0x18004942c  call    cs:__imp_GetLastError
0x180049432  test    eax, eax
0x180049434  jle     short loc_18004943E
0x180049436  movzx   eax, ax
0x180049439  or      eax, 80070000h
0x18004943e  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180049445  jmp     short loc_1800493E8
0x180049447  mov     [rsp+118h+Handles], rax
0x18004944c  mov     rax, [rsp+118h+var_C0]
0x180049451  mov     [rsp+118h+var_E0], rax
0x180049456  mov     [rsp+118h+var_E8], r13
0x18004945b  mov     [rsp+118h+var_F0], r14
0x180049460  mov     qword ptr [rsp+118h+bAlertable], rdi
0x180049465  lea     r9, [rsp+118h+pAsync]
0x18004946a  xor     r8d, r8d; pReturnValue
0x18004946d  lea     edi, [r8+2]
0x180049471  mov     edx, edi; nProcNum
0x180049473  lea     rcx, ?liveidsvcnotify_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004947a  call    cs:__imp_Ndr64AsyncClientCall
0x180049480  mov     eax, [rsp+118h+Reply]
0x180049484  jmp     short loc_1800494D6
0x180049486  test    eax, eax
0x180049488  jle     short loc_180049492
0x18004948a  movzx   eax, ax
0x18004948d  or      eax, 80070000h
0x180049492  mov     [rsp+118h+Reply], eax
0x180049496  mov     [rsp+118h+bAlertable], eax
0x18004949a  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x1800494a1  mov     r8d, 4AAh; unsigned int
0x1800494a7  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800494ae  mov     ecx, 2; unsigned __int8
0x1800494b3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800494b8  mov     eax, [rsp+118h+Reply]
0x1800494bc  test    eax, eax
0x1800494be  js      short loc_1800494C9
0x1800494c0  mov     eax, 8000FFFFh
0x1800494c5  mov     [rsp+118h+Reply], eax
0x1800494c9  mov     edi, 2
0x1800494ce  mov     r12b, [rsp+118h+var_D4]
0x1800494d3  mov     r15b, r12b
0x1800494d6  test    eax, eax
0x1800494d8  jns     short loc_1800494EC
0x1800494da  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x1800494e1  mov     r8d, 4AAh
0x1800494e7  jmp     loc_1800495B7
0x1800494ec  mov     [rsp+118h+bAlertable], 0; bAlertable
0x1800494f4  mov     r9d, 927C0h; dwMilliseconds
0x1800494fa  xor     r8d, r8d; bWaitAll
0x1800494fd  lea     rdx, [rsp+118h+Handles]; lpHandles
0x180049502  lea     ecx, [r8+1]; nCount
0x180049506  call    cs:__imp_WaitForMultipleObjectsEx
0x18004950c  mov     r14d, eax
0x18004950f  mov     r13d, 102h
0x180049515  test    r15b, r15b
0x180049518  jnz     short loc_180049568
0x18004951a  cmp     r14d, r13d
0x18004951d  jz      short loc_180049525
0x18004951f  cmp     r14d, 1
0x180049523  jnz     short loc_180049568
0x180049525  mov     edx, 1; fAbort
0x18004952a  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004952f  call    cs:__imp_RpcAsyncCancelCall
0x180049535  cmp     r14d, r13d
0x180049538  jnz     short loc_18004953F
0x18004953a  mov     r12b, 1
0x18004953d  jmp     short loc_180049542
0x18004953f  mov     r15b, 1
0x180049542  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004954a  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004954e  xor     r8d, r8d; bWaitAll
0x180049551  lea     rdx, [rsp+118h+Handles]; lpHandles
0x180049556  lea     ecx, [r8+1]; nCount
0x18004955a  call    cs:__imp_WaitForMultipleObjectsEx
0x180049560  mov     r14d, eax
0x180049563  test    r12b, r12b
0x180049566  jz      short loc_180049515
0x180049568  test    r14d, r14d
0x18004956b  jz      short loc_180049588
0x18004956d  call    cs:__imp_GetLastError
0x180049573  test    eax, eax
0x180049575  jle     short loc_18004957F
0x180049577  movzx   eax, ax
0x18004957a  or      eax, 80070000h
0x18004957f  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180049586  jmp     short loc_1800495AD
0x180049588  lea     rdx, [rsp+118h+Reply]; Reply
0x18004958d  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180049592  call    cs:__imp_RpcAsyncCompleteCall
0x180049598  test    eax, eax
0x18004959a  jz      short loc_1800495C9
0x18004959c  jle     short loc_1800495A6
0x18004959e  movzx   eax, ax
0x1800495a1  or      eax, 80070000h
0x1800495a6  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x1800495ad  mov     r8d, 4AAh; unsigned int
0x1800495b3  mov     [rsp+118h+Reply], eax
0x1800495b7  mov     [rsp+118h+bAlertable], eax
0x1800495bb  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800495c2  mov     ecx, edi; unsigned __int8
0x1800495c4  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800495c9  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x1800495d1  test    rcx, rcx
0x1800495d4  jz      short loc_1800495DC
0x1800495d6  call    cs:__imp_CloseHandle
0x1800495dc  test    r12b, r12b
0x1800495df  jz      short loc_18004961D
0x1800495e1  mov     [rsp+118h+Reply], 800705B4h
0x1800495e9  lea     rdx, [rsp+118h+var_D0]
0x1800495ee  lea     rcx, aWlidcngetnextn_1; "WLIDCNGetNextNotification"
0x1800495f5  call    ??$RPCCallTimedOut@AEAY0BK@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BK@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[26],ulong &>(char const (&)[26],ulong &)
0x1800495fa  mov     eax, [rsp+118h+Reply]
0x1800495fe  mov     [rsp+118h+bAlertable], eax
0x180049602  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180049609  mov     r8d, 4AAh; unsigned int
0x18004960f  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180049616  mov     ecx, edi; unsigned __int8
0x180049618  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004961d  test    r15b, r15b
0x180049620  jz      short loc_18004964A
0x180049622  mov     eax, 800704C7h
0x180049627  mov     [rsp+118h+Reply], eax
0x18004962b  mov     [rsp+118h+bAlertable], eax
0x18004962f  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180049636  mov     r8d, 4AAh; unsigned int
0x18004963c  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180049643  mov     ecx, edi; unsigned __int8
0x180049645  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004964a  cmp     [rsp+118h+Reply], 800706B5h
0x180049652  jz      short loc_18004965E
0x180049654  cmp     [rsp+118h+Reply], 800706BAh
0x18004965c  jnz     short loc_180049663
0x18004965e  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180049663  lea     rcx, [rsp+118h+var_C8]; this
0x180049668  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18004966d  mov     eax, [rsp+118h+Reply]
0x180049671  mov     rcx, [rsp+118h+var_38]
0x180049679  xor     rcx, rsp; StackCookie
0x18004967c  call    __security_check_cookie
0x180049681  add     rsp, 0F0h
0x180049688  pop     r15
0x18004968a  pop     r14
0x18004968c  pop     r13
0x18004968e  pop     r12
0x180049690  pop     rdi
0x180049691  retn
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
