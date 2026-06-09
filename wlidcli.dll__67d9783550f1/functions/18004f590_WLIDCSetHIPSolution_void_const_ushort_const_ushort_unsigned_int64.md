# WLIDCSetHIPSolution(void * const,ushort const *,ushort *,unsigned __int64)

- ea: `0x18004f590`
- end: `0x18004f8ce`
- name: `?WLIDCSetHIPSolution@@YAJQEAXPEBGPEAG_K@Z`
- size: `830`
- prototype: `__int64 __fastcall(void *const, const unsigned __int16 *, unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002706c`
- `0x180033a20`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180044f38`
- `0x180046ce0`
- `0x18004cd04`
- `0x18004f590`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004f749`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004f79b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004f749`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004f79b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004f65d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004f65d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f670`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f7ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f670`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f7ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f818`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f818`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004f770`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004f770`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004f6c1`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004f6c1`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004f7d1`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004f7d1`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004f616`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004f616`

## string_xrefs

- `0x18004f682`: `RPC failed to create new event, hr = %#x`
- `0x18004f7e5`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCSetHIPSolution(void *const a1, const unsigned __int16 *a2, unsigned __int16 *a3, __int64 a4)
{
  DWORD v6; // esi
  char v7; // r15
  char v8; // r14
  int LastError; // eax
  const unsigned __int16 *v10; // r9
  unsigned int v11; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v13; // esi
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-F8h]
  unsigned int Reply; // [rsp+40h] [rbp-D8h] BYREF
  char v17; // [rsp+44h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-D0h] BYREF
  DWORD v19; // [rsp+4Ch] [rbp-CCh] BYREF
  __int64 v20; // [rsp+50h] [rbp-C8h]
  unsigned __int16 *v21; // [rsp+58h] [rbp-C0h]
  HANDLE Handles[2]; // [rsp+60h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-A8h] BYREF

  v20 = a4;
  v21 = a3;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v6 = dwMilliseconds;
  v19 = dwMilliseconds;
  v7 = 0;
  v17 = 0;
  v8 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v11 = 1035;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x2Fu, 0, &pAsync, a1, a2, v21, v20);
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
  v11 = 1037;
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
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v7 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[20],unsigned long &>(
      (__int64)"WLIDCSetHIPSolution",
      (int *)&v19);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x40Du,
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
      0x40Du,
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
0x18004f590  push    rsi
0x18004f592  push    r12
0x18004f594  push    r13
0x18004f596  push    r14
0x18004f598  push    r15
0x18004f59a  sub     rsp, 0F0h
0x18004f5a1  mov     rax, cs:__security_cookie
0x18004f5a8  xor     rax, rsp
0x18004f5ab  mov     [rsp+118h+var_38], rax
0x18004f5b3  mov     [rsp+118h+var_C8], r9
0x18004f5b8  mov     [rsp+118h+var_C0], r8
0x18004f5bd  mov     r13, rdx
0x18004f5c0  mov     r12, rcx
0x18004f5c3  mov     [rsp+118h+Reply], 0
0x18004f5cb  mov     [rsp+118h+dwMilliseconds], 0
0x18004f5d3  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x18004f5d8  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004f5dd  xor     edx, edx; Val
0x18004f5df  lea     r8d, [rdx+70h]; Size
0x18004f5e3  lea     rcx, [rsp+118h+pAsync]; void *
0x18004f5e8  call    memset_0
0x18004f5ed  mov     esi, [rsp+118h+dwMilliseconds]
0x18004f5f1  mov     [rsp+118h+dwMilliseconds], esi
0x18004f5f5  mov     [rsp+118h+var_CC], esi
0x18004f5f9  xor     r15b, r15b
0x18004f5fc  mov     [rsp+118h+var_D4], r15b
0x18004f601  xor     r14b, r14b
0x18004f604  xorps   xmm0, xmm0
0x18004f607  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x18004f60c  mov     edx, 70h ; 'p'; Size
0x18004f611  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004f616  call    cs:__imp_RpcAsyncInitializeHandle
0x18004f61c  test    eax, eax
0x18004f61e  jz      short loc_18004F63C
0x18004f620  jle     short loc_18004F62A
0x18004f622  movzx   eax, ax
0x18004f625  or      eax, 80070000h
0x18004f62a  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004f631  mov     r8d, 40Bh
0x18004f637  jmp     loc_18004F7F2
0x18004f63c  mov     [rsp+118h+pAsync.UserInfo], 0
0x18004f648  mov     [rsp+118h+pAsync.NotificationType], 1
0x18004f653  xor     r9d, r9d; lpName
0x18004f656  xor     r8d, r8d; bInitialState
0x18004f659  xor     edx, edx; bManualReset
0x18004f65b  xor     ecx, ecx; lpEventAttributes
0x18004f65d  call    cs:__imp_CreateEventW
0x18004f663  mov     qword ptr [rsp+118h+pAsync.u], rax
0x18004f66b  test    rax, rax
0x18004f66e  jnz     short loc_18004F68B
0x18004f670  call    cs:__imp_GetLastError
0x18004f676  test    eax, eax
0x18004f678  jle     short loc_18004F682
0x18004f67a  movzx   eax, ax
0x18004f67d  or      eax, 80070000h
0x18004f682  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004f689  jmp     short loc_18004F631
0x18004f68b  mov     [rsp+118h+Handles], rax
0x18004f690  mov     rax, [rsp+118h+var_C8]
0x18004f695  mov     [rsp+118h+var_E0], rax
0x18004f69a  mov     rax, [rsp+118h+var_C0]
0x18004f69f  mov     [rsp+118h+var_E8], rax
0x18004f6a4  mov     [rsp+118h+var_F0], r13
0x18004f6a9  mov     qword ptr [rsp+118h+bAlertable], r12
0x18004f6ae  lea     r9, [rsp+118h+pAsync]
0x18004f6b3  xor     r8d, r8d; pReturnValue
0x18004f6b6  lea     edx, [r8+2Fh]; nProcNum
0x18004f6ba  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004f6c1  call    cs:__imp_Ndr64AsyncClientCall
0x18004f6c7  mov     eax, [rsp+118h+Reply]
0x18004f6cb  jmp     short loc_18004F71C
0x18004f6cd  test    eax, eax
0x18004f6cf  jle     short loc_18004F6D9
0x18004f6d1  movzx   eax, ax
0x18004f6d4  or      eax, 80070000h
0x18004f6d9  mov     [rsp+118h+Reply], eax
0x18004f6dd  mov     [rsp+118h+bAlertable], eax
0x18004f6e1  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004f6e8  mov     r8d, 40Dh; unsigned int
0x18004f6ee  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004f6f5  mov     ecx, 2; unsigned __int8
0x18004f6fa  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004f6ff  mov     eax, [rsp+118h+Reply]
0x18004f703  test    eax, eax
0x18004f705  js      short loc_18004F710
0x18004f707  mov     eax, 8000FFFFh
0x18004f70c  mov     [rsp+118h+Reply], eax
0x18004f710  mov     esi, [rsp+118h+dwMilliseconds]
0x18004f714  mov     r15b, [rsp+118h+var_D4]
0x18004f719  mov     r14b, r15b
0x18004f71c  test    eax, eax
0x18004f71e  jns     short loc_18004F732
0x18004f720  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004f727  mov     r8d, 40Dh
0x18004f72d  jmp     loc_18004F7F6
0x18004f732  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004f73a  mov     r9d, esi; dwMilliseconds
0x18004f73d  xor     r8d, r8d; bWaitAll
0x18004f740  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004f745  lea     ecx, [r8+1]; nCount
0x18004f749  call    cs:__imp_WaitForMultipleObjectsEx
0x18004f74f  mov     esi, eax
0x18004f751  mov     r12d, 102h
0x18004f757  test    r14b, r14b
0x18004f75a  jnz     short loc_18004F7A8
0x18004f75c  cmp     esi, r12d
0x18004f75f  jz      short loc_18004F766
0x18004f761  cmp     esi, 1
0x18004f764  jnz     short loc_18004F7A8
0x18004f766  mov     edx, 1; fAbort
0x18004f76b  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004f770  call    cs:__imp_RpcAsyncCancelCall
0x18004f776  cmp     esi, r12d
0x18004f779  jnz     short loc_18004F780
0x18004f77b  mov     r15b, 1
0x18004f77e  jmp     short loc_18004F783
0x18004f780  mov     r14b, 1
0x18004f783  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004f78b  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004f78f  xor     r8d, r8d; bWaitAll
0x18004f792  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004f797  lea     ecx, [r8+1]; nCount
0x18004f79b  call    cs:__imp_WaitForMultipleObjectsEx
0x18004f7a1  mov     esi, eax
0x18004f7a3  test    r15b, r15b
0x18004f7a6  jz      short loc_18004F757
0x18004f7a8  test    esi, esi
0x18004f7aa  jz      short loc_18004F7C7
0x18004f7ac  call    cs:__imp_GetLastError
0x18004f7b2  test    eax, eax
0x18004f7b4  jle     short loc_18004F7BE
0x18004f7b6  movzx   eax, ax
0x18004f7b9  or      eax, 80070000h
0x18004f7be  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004f7c5  jmp     short loc_18004F7EC
0x18004f7c7  lea     rdx, [rsp+118h+Reply]; Reply
0x18004f7cc  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004f7d1  call    cs:__imp_RpcAsyncCompleteCall
0x18004f7d7  test    eax, eax
0x18004f7d9  jz      short loc_18004F80B
0x18004f7db  jle     short loc_18004F7E5
0x18004f7dd  movzx   eax, ax
0x18004f7e0  or      eax, 80070000h
0x18004f7e5  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004f7ec  mov     r8d, 40Dh; unsigned int
0x18004f7f2  mov     [rsp+118h+Reply], eax
0x18004f7f6  mov     [rsp+118h+bAlertable], eax
0x18004f7fa  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004f801  mov     ecx, 2; unsigned __int8
0x18004f806  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004f80b  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x18004f813  test    rcx, rcx
0x18004f816  jz      short loc_18004F81E
0x18004f818  call    cs:__imp_CloseHandle
0x18004f81e  test    r15b, r15b
0x18004f821  jz      short loc_18004F862
0x18004f823  mov     [rsp+118h+Reply], 800705B4h
0x18004f82b  lea     rdx, [rsp+118h+var_CC]
0x18004f830  lea     rcx, aWlidcsethipsol; "WLIDCSetHIPSolution"
0x18004f837  call    ??$RPCCallTimedOut@AEAY0BE@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BE@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[20],ulong &>(char const (&)[20],ulong &)
0x18004f83c  mov     eax, [rsp+118h+Reply]
0x18004f840  mov     [rsp+118h+bAlertable], eax
0x18004f844  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004f84b  mov     r8d, 40Dh; unsigned int
0x18004f851  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004f858  mov     ecx, 2; unsigned __int8
0x18004f85d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004f862  test    r14b, r14b
0x18004f865  jz      short loc_18004F892
0x18004f867  mov     eax, 800704C7h
0x18004f86c  mov     [rsp+118h+Reply], eax
0x18004f870  mov     [rsp+118h+bAlertable], eax
0x18004f874  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004f87b  mov     r8d, 40Dh; unsigned int
0x18004f881  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004f888  mov     ecx, 2; unsigned __int8
0x18004f88d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004f892  mov     eax, [rsp+118h+Reply]
0x18004f896  cmp     eax, 800706B5h
0x18004f89b  jz      short loc_18004F8A4
0x18004f89d  cmp     eax, 800706BAh
0x18004f8a2  jnz     short loc_18004F8AD
0x18004f8a4  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004f8a9  mov     eax, [rsp+118h+Reply]
0x18004f8ad  mov     rcx, [rsp+118h+var_38]
0x18004f8b5  xor     rcx, rsp; StackCookie
0x18004f8b8  call    __security_check_cookie
0x18004f8bd  add     rsp, 0F0h
0x18004f8c4  pop     r15
0x18004f8c6  pop     r14
0x18004f8c8  pop     r13
0x18004f8ca  pop     r12
0x18004f8cc  pop     rsi
0x18004f8cd  retn
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
