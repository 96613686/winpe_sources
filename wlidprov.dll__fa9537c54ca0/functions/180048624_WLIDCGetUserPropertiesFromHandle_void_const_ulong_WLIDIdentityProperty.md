# WLIDCGetUserPropertiesFromHandle(void * const,ulong *,_WLIDIdentityProperty * *)

- ea: `0x180048624`
- end: `0x180048953`
- name: `?WLIDCGetUserPropertiesFromHandle@@YAJQEAXPEAKPEAPEAU_WLIDIdentityProperty@@@Z`
- size: `815`
- prototype: `__int64 __fastcall(void *const, unsigned int *, struct _WLIDIdentityProperty **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180026d88`

## callees

- `0x18000a400`
- `0x180010c68`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180042270`
- `0x180043240`
- `0x180048624`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800486ec`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800486ec`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800487ce`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180048820`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800487ce`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180048820`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800486ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048831`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800486ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048831`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004889d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004889d`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800486a5`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800486a5`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800487f5`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800487f5`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180048746`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180048746`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180048856`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180048856`

## string_xrefs

- `0x180048711`: `RPC failed to create new event, hr = %#x`
- `0x18004886a`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCGetUserPropertiesFromHandle(
        void *const a1,
        unsigned int *a2,
        struct _WLIDIdentityProperty **a3)
{
  DWORD v5; // esi
  char v6; // r15
  char v7; // r14
  int LastError; // eax
  const unsigned __int16 *v9; // r9
  unsigned int v10; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v12; // esi
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-F8h]
  unsigned int Reply; // [rsp+40h] [rbp-D8h] BYREF
  char v16; // [rsp+44h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-D0h] BYREF
  DWORD v18; // [rsp+4Ch] [rbp-CCh] BYREF
  struct _WLIDIdentityProperty **v19; // [rsp+50h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+58h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-A8h] BYREF

  v19 = a3;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v5 = dwMilliseconds;
  v18 = dwMilliseconds;
  v6 = 0;
  v16 = 0;
  v7 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v10 = 1112;
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
    v9 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_5;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x3Bu, 0, &pAsync, a1, a2, v19);
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
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_28;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = L"RPC Async complete call failed, hr = %#x";
  }
  v10 = 1114;
LABEL_27:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(2u, "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp", v10, v9, *(_QWORD *)bAlertable);
LABEL_28:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v6 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[33],unsigned long &>(
      "WLIDCGetUserPropertiesFromHandle",
      &v18);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x45Au,
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
      0x45Au,
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
0x180048624  push    rsi
0x180048626  push    r12
0x180048628  push    r13
0x18004862a  push    r14
0x18004862c  push    r15
0x18004862e  sub     rsp, 0F0h
0x180048635  mov     rax, cs:__security_cookie
0x18004863c  xor     rax, rsp
0x18004863f  mov     [rsp+118h+var_38], rax
0x180048647  mov     [rsp+118h+var_C8], r8
0x18004864c  mov     r13, rdx
0x18004864f  mov     r12, rcx
0x180048652  mov     [rsp+118h+Reply], 0
0x18004865a  mov     [rsp+118h+dwMilliseconds], 0
0x180048662  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x180048667  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004866c  xor     edx, edx; Val
0x18004866e  lea     r8d, [rdx+70h]; Size
0x180048672  lea     rcx, [rsp+118h+pAsync]; void *
0x180048677  call    memset_0
0x18004867c  mov     esi, [rsp+118h+dwMilliseconds]
0x180048680  mov     [rsp+118h+dwMilliseconds], esi
0x180048684  mov     [rsp+118h+var_CC], esi
0x180048688  xor     r15b, r15b
0x18004868b  mov     [rsp+118h+var_D4], r15b
0x180048690  xor     r14b, r14b
0x180048693  xorps   xmm0, xmm0
0x180048696  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x18004869b  mov     edx, 70h ; 'p'; Size
0x1800486a0  lea     rcx, [rsp+118h+pAsync]; pAsync
0x1800486a5  call    cs:__imp_RpcAsyncInitializeHandle
0x1800486ab  test    eax, eax
0x1800486ad  jz      short loc_1800486CB
0x1800486af  jle     short loc_1800486B9
0x1800486b1  movzx   eax, ax
0x1800486b4  or      eax, 80070000h
0x1800486b9  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x1800486c0  mov     r8d, 458h
0x1800486c6  jmp     loc_180048877
0x1800486cb  mov     [rsp+118h+pAsync.UserInfo], 0
0x1800486d7  mov     [rsp+118h+pAsync.NotificationType], 1
0x1800486e2  xor     r9d, r9d; lpName
0x1800486e5  xor     r8d, r8d; bInitialState
0x1800486e8  xor     edx, edx; bManualReset
0x1800486ea  xor     ecx, ecx; lpEventAttributes
0x1800486ec  call    cs:__imp_CreateEventW
0x1800486f2  mov     qword ptr [rsp+118h+pAsync.u], rax
0x1800486fa  test    rax, rax
0x1800486fd  jnz     short loc_18004871A
0x1800486ff  call    cs:__imp_GetLastError
0x180048705  test    eax, eax
0x180048707  jle     short loc_180048711
0x180048709  movzx   eax, ax
0x18004870c  or      eax, 80070000h
0x180048711  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180048718  jmp     short loc_1800486C0
0x18004871a  mov     [rsp+118h+Handles], rax
0x18004871f  mov     rax, [rsp+118h+var_C8]
0x180048724  mov     [rsp+118h+var_E8], rax
0x180048729  mov     [rsp+118h+var_F0], r13
0x18004872e  mov     qword ptr [rsp+118h+bAlertable], r12
0x180048733  lea     r9, [rsp+118h+pAsync]
0x180048738  xor     r8d, r8d; pReturnValue
0x18004873b  lea     edx, [r8+3Bh]; nProcNum
0x18004873f  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180048746  call    cs:__imp_Ndr64AsyncClientCall
0x18004874c  mov     eax, [rsp+118h+Reply]
0x180048750  jmp     short loc_1800487A1
0x180048752  test    eax, eax
0x180048754  jle     short loc_18004875E
0x180048756  movzx   eax, ax
0x180048759  or      eax, 80070000h
0x18004875e  mov     [rsp+118h+Reply], eax
0x180048762  mov     [rsp+118h+bAlertable], eax
0x180048766  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004876d  mov     r8d, 45Ah; unsigned int
0x180048773  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004877a  mov     ecx, 2; unsigned __int8
0x18004877f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180048784  mov     eax, [rsp+118h+Reply]
0x180048788  test    eax, eax
0x18004878a  js      short loc_180048795
0x18004878c  mov     eax, 8000FFFFh
0x180048791  mov     [rsp+118h+Reply], eax
0x180048795  mov     esi, [rsp+118h+dwMilliseconds]
0x180048799  mov     r15b, [rsp+118h+var_D4]
0x18004879e  mov     r14b, r15b
0x1800487a1  test    eax, eax
0x1800487a3  jns     short loc_1800487B7
0x1800487a5  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x1800487ac  mov     r8d, 45Ah
0x1800487b2  jmp     loc_18004887B
0x1800487b7  mov     [rsp+118h+bAlertable], 0; bAlertable
0x1800487bf  mov     r9d, esi; dwMilliseconds
0x1800487c2  xor     r8d, r8d; bWaitAll
0x1800487c5  lea     rdx, [rsp+118h+Handles]; lpHandles
0x1800487ca  lea     ecx, [r8+1]; nCount
0x1800487ce  call    cs:__imp_WaitForMultipleObjectsEx
0x1800487d4  mov     esi, eax
0x1800487d6  mov     r12d, 102h
0x1800487dc  test    r14b, r14b
0x1800487df  jnz     short loc_18004882D
0x1800487e1  cmp     esi, r12d
0x1800487e4  jz      short loc_1800487EB
0x1800487e6  cmp     esi, 1
0x1800487e9  jnz     short loc_18004882D
0x1800487eb  mov     edx, 1; fAbort
0x1800487f0  lea     rcx, [rsp+118h+pAsync]; pAsync
0x1800487f5  call    cs:__imp_RpcAsyncCancelCall
0x1800487fb  cmp     esi, r12d
0x1800487fe  jnz     short loc_180048805
0x180048800  mov     r15b, 1
0x180048803  jmp     short loc_180048808
0x180048805  mov     r14b, 1
0x180048808  mov     [rsp+118h+bAlertable], 0; bAlertable
0x180048810  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180048814  xor     r8d, r8d; bWaitAll
0x180048817  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004881c  lea     ecx, [r8+1]; nCount
0x180048820  call    cs:__imp_WaitForMultipleObjectsEx
0x180048826  mov     esi, eax
0x180048828  test    r15b, r15b
0x18004882b  jz      short loc_1800487DC
0x18004882d  test    esi, esi
0x18004882f  jz      short loc_18004884C
0x180048831  call    cs:__imp_GetLastError
0x180048837  test    eax, eax
0x180048839  jle     short loc_180048843
0x18004883b  movzx   eax, ax
0x18004883e  or      eax, 80070000h
0x180048843  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004884a  jmp     short loc_180048871
0x18004884c  lea     rdx, [rsp+118h+Reply]; Reply
0x180048851  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180048856  call    cs:__imp_RpcAsyncCompleteCall
0x18004885c  test    eax, eax
0x18004885e  jz      short loc_180048890
0x180048860  jle     short loc_18004886A
0x180048862  movzx   eax, ax
0x180048865  or      eax, 80070000h
0x18004886a  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180048871  mov     r8d, 45Ah; unsigned int
0x180048877  mov     [rsp+118h+Reply], eax
0x18004887b  mov     [rsp+118h+bAlertable], eax
0x18004887f  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180048886  mov     ecx, 2; unsigned __int8
0x18004888b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180048890  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x180048898  test    rcx, rcx
0x18004889b  jz      short loc_1800488A3
0x18004889d  call    cs:__imp_CloseHandle
0x1800488a3  test    r15b, r15b
0x1800488a6  jz      short loc_1800488E7
0x1800488a8  mov     [rsp+118h+Reply], 800705B4h
0x1800488b0  lea     rdx, [rsp+118h+var_CC]
0x1800488b5  lea     rcx, aWlidcgetuserpr; "WLIDCGetUserPropertiesFromHandle"
0x1800488bc  call    ??$RPCCallTimedOut@AEAY0CB@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0CB@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[33],ulong &>(char const (&)[33],ulong &)
0x1800488c1  mov     eax, [rsp+118h+Reply]
0x1800488c5  mov     [rsp+118h+bAlertable], eax
0x1800488c9  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x1800488d0  mov     r8d, 45Ah; unsigned int
0x1800488d6  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800488dd  mov     ecx, 2; unsigned __int8
0x1800488e2  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800488e7  test    r14b, r14b
0x1800488ea  jz      short loc_180048917
0x1800488ec  mov     eax, 800704C7h
0x1800488f1  mov     [rsp+118h+Reply], eax
0x1800488f5  mov     [rsp+118h+bAlertable], eax
0x1800488f9  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180048900  mov     r8d, 45Ah; unsigned int
0x180048906  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004890d  mov     ecx, 2; unsigned __int8
0x180048912  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180048917  mov     eax, [rsp+118h+Reply]
0x18004891b  cmp     eax, 800706B5h
0x180048920  jz      short loc_180048929
0x180048922  cmp     eax, 800706BAh
0x180048927  jnz     short loc_180048932
0x180048929  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004892e  mov     eax, [rsp+118h+Reply]
0x180048932  mov     rcx, [rsp+118h+var_38]
0x18004893a  xor     rcx, rsp; StackCookie
0x18004893d  call    __security_check_cookie
0x180048942  add     rsp, 0F0h
0x180048949  pop     r15
0x18004894b  pop     r14
0x18004894d  pop     r13
0x18004894f  pop     r12
0x180048951  pop     rsi
0x180048952  retn
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
