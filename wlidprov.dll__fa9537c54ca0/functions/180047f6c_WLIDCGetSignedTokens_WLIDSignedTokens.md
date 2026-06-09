# WLIDCGetSignedTokens(_WLIDSignedTokens * *)

- ea: `0x180047f6c`
- end: `0x1800482b2`
- name: `?WLIDCGetSignedTokens@@YAJPEAPEAU_WLIDSignedTokens@@@Z`
- size: `838`
- prototype: `__int64 __fastcall(struct _WLIDSignedTokens **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180041820`

## callees

- `0x18000a400`
- `0x18000f870`
- `0x180010c68`
- `0x180011588`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180041c80`
- `0x180043240`
- `0x180047f6c`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180048046`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180048046`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180048123`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180048175`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180048123`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180048175`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048059`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048186`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048059`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048186`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800481f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800481f2`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180048002`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180048002`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004814a`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004814a`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004809b`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004809b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800481ab`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800481ab`

## string_xrefs

- `0x18004806b`: `RPC failed to create new event, hr = %#x`
- `0x1800481bf`: `RPC Async complete call failed, hr = %#x`
- `0x18004820a`: `WLIDCGetSignedTokens`

## pseudocode

```c
__int64 __fastcall WLIDCGetSignedTokens(struct _WLIDSignedTokens **a1, unsigned int a2)
{
  __int64 result; // rax
  DWORD v4; // esi
  char v5; // r15
  char v6; // r14
  int LastError; // eax
  const unsigned __int16 *v8; // r9
  unsigned int v9; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v11; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-E8h]
  int Reply; // [rsp+30h] [rbp-D8h] BYREF
  char v14; // [rsp+34h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+38h] [rbp-D0h] BYREF
  DWORD v16; // [rsp+3Ch] [rbp-CCh] BYREF
  __int64 v17; // [rsp+40h] [rbp-C8h] BYREF
  HANDLE Handles[3]; // [rsp+48h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+60h] [rbp-A8h] BYREF

  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  v17 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v17);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v4 = dwMilliseconds;
  v16 = dwMilliseconds;
  v5 = 0;
  v14 = 0;
  v6 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v9 = 1345;
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
    v8 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x3Fu, 0, &pAsync, v17, a1);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v8 = L"RPC call failed, hr = %#x";
    v9 = 1347;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v9,
      v8,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
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
LABEL_29:
    v9 = 1347;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v5 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],unsigned long &>("WLIDCGetSignedTokens", &v16);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x543u,
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
      0x543u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v17);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x180047f6c  push    rsi
0x180047f6e  push    r12
0x180047f70  push    r14
0x180047f72  push    r15
0x180047f74  sub     rsp, 0E8h
0x180047f7b  mov     rax, cs:__security_cookie
0x180047f82  xor     rax, rsp
0x180047f85  mov     [rsp+108h+var_38], rax
0x180047f8d  mov     r12, rcx
0x180047f90  mov     [rsp+108h+dwMilliseconds], 0
0x180047f98  lea     r8, [rsp+108h+dwMilliseconds]; unsigned int *
0x180047f9d  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180047fa2  mov     [rsp+108h+Reply], 0
0x180047faa  mov     [rsp+108h+var_C8], 0
0x180047fb3  lea     rcx, [rsp+108h+var_C8]; this
0x180047fb8  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x180047fbd  mov     [rsp+108h+Reply], eax
0x180047fc1  test    eax, eax
0x180047fc3  js      loc_180048293
0x180047fc9  xor     edx, edx; Val
0x180047fcb  lea     r8d, [rdx+70h]; Size
0x180047fcf  lea     rcx, [rsp+108h+pAsync]; void *
0x180047fd4  call    memset_0
0x180047fd9  mov     esi, [rsp+108h+dwMilliseconds]
0x180047fdd  mov     [rsp+108h+dwMilliseconds], esi
0x180047fe1  mov     [rsp+108h+var_CC], esi
0x180047fe5  xor     r15b, r15b
0x180047fe8  mov     [rsp+108h+var_D4], r15b
0x180047fed  xor     r14b, r14b
0x180047ff0  xorps   xmm0, xmm0
0x180047ff3  movups  xmmword ptr [rsp+108h+Handles], xmm0
0x180047ff8  mov     edx, 70h ; 'p'; Size
0x180047ffd  lea     rcx, [rsp+108h+pAsync]; pAsync
0x180048002  call    cs:__imp_RpcAsyncInitializeHandle
0x180048008  test    eax, eax
0x18004800a  jz      short loc_180048028
0x18004800c  jle     short loc_180048016
0x18004800e  movzx   eax, ax
0x180048011  or      eax, 80070000h
0x180048016  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004801d  mov     r8d, 541h
0x180048023  jmp     loc_1800481CC
0x180048028  mov     [rsp+108h+pAsync.UserInfo], 0
0x180048031  mov     [rsp+108h+pAsync.NotificationType], 1
0x18004803c  xor     r9d, r9d; lpName
0x18004803f  xor     r8d, r8d; bInitialState
0x180048042  xor     edx, edx; bManualReset
0x180048044  xor     ecx, ecx; lpEventAttributes
0x180048046  call    cs:__imp_CreateEventW
0x18004804c  mov     qword ptr [rsp+108h+pAsync.u], rax
0x180048054  test    rax, rax
0x180048057  jnz     short loc_180048074
0x180048059  call    cs:__imp_GetLastError
0x18004805f  test    eax, eax
0x180048061  jle     short loc_18004806B
0x180048063  movzx   eax, ax
0x180048066  or      eax, 80070000h
0x18004806b  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180048072  jmp     short loc_18004801D
0x180048074  mov     [rsp+108h+Handles], rax
0x180048079  mov     [rsp+108h+var_E0], r12
0x18004807e  mov     rax, [rsp+108h+var_C8]
0x180048083  mov     qword ptr [rsp+108h+bAlertable], rax
0x180048088  lea     r9, [rsp+108h+pAsync]
0x18004808d  xor     r8d, r8d; pReturnValue
0x180048090  lea     edx, [r8+3Fh]; nProcNum
0x180048094  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004809b  call    cs:__imp_Ndr64AsyncClientCall
0x1800480a1  mov     eax, [rsp+108h+Reply]
0x1800480a5  jmp     short loc_1800480F6
0x1800480a7  test    eax, eax
0x1800480a9  jle     short loc_1800480B3
0x1800480ab  movzx   eax, ax
0x1800480ae  or      eax, 80070000h
0x1800480b3  mov     [rsp+108h+Reply], eax
0x1800480b7  mov     [rsp+108h+bAlertable], eax
0x1800480bb  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x1800480c2  mov     r8d, 543h; unsigned int
0x1800480c8  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800480cf  mov     ecx, 2; unsigned __int8
0x1800480d4  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800480d9  mov     eax, [rsp+108h+Reply]
0x1800480dd  test    eax, eax
0x1800480df  js      short loc_1800480EA
0x1800480e1  mov     eax, 8000FFFFh
0x1800480e6  mov     [rsp+108h+Reply], eax
0x1800480ea  mov     esi, [rsp+108h+dwMilliseconds]
0x1800480ee  mov     r15b, [rsp+108h+var_D4]
0x1800480f3  mov     r14b, r15b
0x1800480f6  test    eax, eax
0x1800480f8  jns     short loc_18004810C
0x1800480fa  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180048101  mov     r8d, 543h
0x180048107  jmp     loc_1800481D0
0x18004810c  mov     [rsp+108h+bAlertable], 0; bAlertable
0x180048114  mov     r9d, esi; dwMilliseconds
0x180048117  xor     r8d, r8d; bWaitAll
0x18004811a  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18004811f  lea     ecx, [r8+1]; nCount
0x180048123  call    cs:__imp_WaitForMultipleObjectsEx
0x180048129  mov     esi, eax
0x18004812b  mov     r12d, 102h
0x180048131  test    r14b, r14b
0x180048134  jnz     short loc_180048182
0x180048136  cmp     esi, r12d
0x180048139  jz      short loc_180048140
0x18004813b  cmp     esi, 1
0x18004813e  jnz     short loc_180048182
0x180048140  mov     edx, 1; fAbort
0x180048145  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004814a  call    cs:__imp_RpcAsyncCancelCall
0x180048150  cmp     esi, r12d
0x180048153  jnz     short loc_18004815A
0x180048155  mov     r15b, 1
0x180048158  jmp     short loc_18004815D
0x18004815a  mov     r14b, 1
0x18004815d  mov     [rsp+108h+bAlertable], 0; bAlertable
0x180048165  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180048169  xor     r8d, r8d; bWaitAll
0x18004816c  lea     rdx, [rsp+108h+Handles]; lpHandles
0x180048171  lea     ecx, [r8+1]; nCount
0x180048175  call    cs:__imp_WaitForMultipleObjectsEx
0x18004817b  mov     esi, eax
0x18004817d  test    r15b, r15b
0x180048180  jz      short loc_180048131
0x180048182  test    esi, esi
0x180048184  jz      short loc_1800481A1
0x180048186  call    cs:__imp_GetLastError
0x18004818c  test    eax, eax
0x18004818e  jle     short loc_180048198
0x180048190  movzx   eax, ax
0x180048193  or      eax, 80070000h
0x180048198  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004819f  jmp     short loc_1800481C6
0x1800481a1  lea     rdx, [rsp+108h+Reply]; Reply
0x1800481a6  lea     rcx, [rsp+108h+pAsync]; pAsync
0x1800481ab  call    cs:__imp_RpcAsyncCompleteCall
0x1800481b1  test    eax, eax
0x1800481b3  jz      short loc_1800481E5
0x1800481b5  jle     short loc_1800481BF
0x1800481b7  movzx   eax, ax
0x1800481ba  or      eax, 80070000h
0x1800481bf  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x1800481c6  mov     r8d, 543h; unsigned int
0x1800481cc  mov     [rsp+108h+Reply], eax
0x1800481d0  mov     [rsp+108h+bAlertable], eax
0x1800481d4  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800481db  mov     ecx, 2; unsigned __int8
0x1800481e0  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800481e5  mov     rcx, qword ptr [rsp+108h+pAsync.u]; hObject
0x1800481ed  test    rcx, rcx
0x1800481f0  jz      short loc_1800481F8
0x1800481f2  call    cs:__imp_CloseHandle
0x1800481f8  test    r15b, r15b
0x1800481fb  jz      short loc_18004823C
0x1800481fd  mov     [rsp+108h+Reply], 800705B4h
0x180048205  lea     rdx, [rsp+108h+var_CC]
0x18004820a  lea     rcx, aWlidcgetsigned_0; "WLIDCGetSignedTokens"
0x180048211  call    ??$RPCCallTimedOut@AEAY0BF@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BF@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],ulong &>(char const (&)[21],ulong &)
0x180048216  mov     eax, [rsp+108h+Reply]
0x18004821a  mov     [rsp+108h+bAlertable], eax
0x18004821e  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180048225  mov     r8d, 543h; unsigned int
0x18004822b  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180048232  mov     ecx, 2; unsigned __int8
0x180048237  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004823c  test    r14b, r14b
0x18004823f  jz      short loc_18004826C
0x180048241  mov     eax, 800704C7h
0x180048246  mov     [rsp+108h+Reply], eax
0x18004824a  mov     [rsp+108h+bAlertable], eax
0x18004824e  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180048255  mov     r8d, 543h; unsigned int
0x18004825b  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180048262  mov     ecx, 2; unsigned __int8
0x180048267  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004826c  cmp     [rsp+108h+Reply], 800706B5h
0x180048274  jz      short loc_180048280
0x180048276  cmp     [rsp+108h+Reply], 800706BAh
0x18004827e  jnz     short loc_180048285
0x180048280  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180048285  lea     rcx, [rsp+108h+var_C8]; this
0x18004828a  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18004828f  mov     eax, [rsp+108h+Reply]
0x180048293  mov     rcx, [rsp+108h+var_38]
0x18004829b  xor     rcx, rsp; StackCookie
0x18004829e  call    __security_check_cookie
0x1800482a3  add     rsp, 0E8h
0x1800482aa  pop     r15
0x1800482ac  pop     r14
0x1800482ae  pop     r12
0x1800482b0  pop     rsi
0x1800482b1  retn
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
