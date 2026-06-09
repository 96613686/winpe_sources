# WLIDCGetConfigString(ushort const *,ushort * *)

- ea: `0x1800463a0`
- end: `0x180046704`
- name: `?WLIDCGetConfigString@@YAJPEBGPEAPEAG@Z`
- size: `868`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002520c`
- `0x1800416f0`

## callees

- `0x18000a400`
- `0x18000f870`
- `0x180010c68`
- `0x180011588`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180041c80`
- `0x180043240`
- `0x1800463a0`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046488`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046488`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004656a`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800465bc`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004656a`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800465bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004649b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800465cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004649b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800465cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046639`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046639`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180046441`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180046441`
- `RPCRT4!RpcAsyncCancelCall` at `0x180046591`
- `RPCRT4!RpcAsyncCancelCall` at `0x180046591`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800464e2`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800464e2`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800465f2`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800465f2`

## string_xrefs

- `0x1800464ad`: `RPC failed to create new event, hr = %#x`
- `0x180046606`: `RPC Async complete call failed, hr = %#x`
- `0x180046651`: `WLIDCGetConfigString`

## pseudocode

```c
__int64 __fastcall WLIDCGetConfigString(const unsigned __int16 *a1, unsigned __int16 **a2)
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
    v10 = 1226;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x33u, 0, &pAsync, v18, a1, a2);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v9 = L"RPC call failed, hr = %#x";
    v10 = 1228;
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
    v10 = 1228;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],unsigned long &>("WLIDCGetConfigString", &v17);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x4CCu,
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
      0x4CCu,
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
0x1800463a0  mov     [rsp+arg_10], rsi
0x1800463a5  mov     [rsp+arg_18], r12
0x1800463aa  push    r13
0x1800463ac  push    r14
0x1800463ae  push    r15
0x1800463b0  sub     rsp, 0F0h
0x1800463b7  mov     rax, cs:__security_cookie
0x1800463be  xor     rax, rsp
0x1800463c1  mov     [rsp+108h+var_28], rax
0x1800463c9  mov     r13, rdx
0x1800463cc  mov     r12, rcx
0x1800463cf  mov     [rsp+108h+dwMilliseconds], 0
0x1800463d7  lea     r8, [rsp+108h+dwMilliseconds]; unsigned int *
0x1800463dc  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x1800463e1  mov     [rsp+108h+Reply], 0
0x1800463e9  mov     [rsp+108h+var_B8], 0
0x1800463f2  lea     rcx, [rsp+108h+var_B8]; this
0x1800463f7  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x1800463fc  mov     [rsp+108h+Reply], eax
0x180046400  test    eax, eax
0x180046402  js      loc_1800466DA
0x180046408  xor     edx, edx; Val
0x18004640a  lea     r8d, [rdx+70h]; Size
0x18004640e  lea     rcx, [rsp+108h+pAsync]; void *
0x180046413  call    memset_0
0x180046418  mov     esi, [rsp+108h+dwMilliseconds]
0x18004641c  mov     [rsp+108h+dwMilliseconds], esi
0x180046420  mov     [rsp+108h+var_BC], esi
0x180046424  xor     r15b, r15b
0x180046427  mov     [rsp+108h+var_C4], r15b
0x18004642c  xor     r14b, r14b
0x18004642f  xorps   xmm0, xmm0
0x180046432  movups  xmmword ptr [rsp+108h+Handles], xmm0
0x180046437  mov     edx, 70h ; 'p'; Size
0x18004643c  lea     rcx, [rsp+108h+pAsync]; pAsync
0x180046441  call    cs:__imp_RpcAsyncInitializeHandle
0x180046447  test    eax, eax
0x180046449  jz      short loc_180046467
0x18004644b  jle     short loc_180046455
0x18004644d  movzx   eax, ax
0x180046450  or      eax, 80070000h
0x180046455  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004645c  mov     r8d, 4CAh
0x180046462  jmp     loc_180046613
0x180046467  mov     [rsp+108h+pAsync.UserInfo], 0
0x180046473  mov     [rsp+108h+pAsync.NotificationType], 1
0x18004647e  xor     r9d, r9d; lpName
0x180046481  xor     r8d, r8d; bInitialState
0x180046484  xor     edx, edx; bManualReset
0x180046486  xor     ecx, ecx; lpEventAttributes
0x180046488  call    cs:__imp_CreateEventW
0x18004648e  mov     qword ptr [rsp+108h+pAsync.u], rax
0x180046496  test    rax, rax
0x180046499  jnz     short loc_1800464B6
0x18004649b  call    cs:__imp_GetLastError
0x1800464a1  test    eax, eax
0x1800464a3  jle     short loc_1800464AD
0x1800464a5  movzx   eax, ax
0x1800464a8  or      eax, 80070000h
0x1800464ad  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x1800464b4  jmp     short loc_18004645C
0x1800464b6  mov     [rsp+108h+Handles], rax
0x1800464bb  mov     [rsp+108h+var_D8], r13
0x1800464c0  mov     [rsp+108h+var_E0], r12
0x1800464c5  mov     rax, [rsp+108h+var_B8]
0x1800464ca  mov     qword ptr [rsp+108h+bAlertable], rax
0x1800464cf  lea     r9, [rsp+108h+pAsync]
0x1800464d4  xor     r8d, r8d; pReturnValue
0x1800464d7  lea     edx, [r8+33h]; nProcNum
0x1800464db  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800464e2  call    cs:__imp_Ndr64AsyncClientCall
0x1800464e8  mov     eax, [rsp+108h+Reply]
0x1800464ec  jmp     short loc_18004653D
0x1800464ee  test    eax, eax
0x1800464f0  jle     short loc_1800464FA
0x1800464f2  movzx   eax, ax
0x1800464f5  or      eax, 80070000h
0x1800464fa  mov     [rsp+108h+Reply], eax
0x1800464fe  mov     [rsp+108h+bAlertable], eax
0x180046502  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180046509  mov     r8d, 4CCh; unsigned int
0x18004650f  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180046516  mov     ecx, 2; unsigned __int8
0x18004651b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180046520  mov     eax, [rsp+108h+Reply]
0x180046524  test    eax, eax
0x180046526  js      short loc_180046531
0x180046528  mov     eax, 8000FFFFh
0x18004652d  mov     [rsp+108h+Reply], eax
0x180046531  mov     esi, [rsp+108h+dwMilliseconds]
0x180046535  mov     r15b, [rsp+108h+var_C4]
0x18004653a  mov     r14b, r15b
0x18004653d  test    eax, eax
0x18004653f  jns     short loc_180046553
0x180046541  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180046548  mov     r8d, 4CCh
0x18004654e  jmp     loc_180046617
0x180046553  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18004655b  mov     r9d, esi; dwMilliseconds
0x18004655e  xor     r8d, r8d; bWaitAll
0x180046561  lea     rdx, [rsp+108h+Handles]; lpHandles
0x180046566  lea     ecx, [r8+1]; nCount
0x18004656a  call    cs:__imp_WaitForMultipleObjectsEx
0x180046570  mov     esi, eax
0x180046572  mov     r12d, 102h
0x180046578  test    r14b, r14b
0x18004657b  jnz     short loc_1800465C9
0x18004657d  cmp     esi, r12d
0x180046580  jz      short loc_180046587
0x180046582  cmp     esi, 1
0x180046585  jnz     short loc_1800465C9
0x180046587  mov     edx, 1; fAbort
0x18004658c  lea     rcx, [rsp+108h+pAsync]; pAsync
0x180046591  call    cs:__imp_RpcAsyncCancelCall
0x180046597  cmp     esi, r12d
0x18004659a  jnz     short loc_1800465A1
0x18004659c  mov     r15b, 1
0x18004659f  jmp     short loc_1800465A4
0x1800465a1  mov     r14b, 1
0x1800465a4  mov     [rsp+108h+bAlertable], 0; bAlertable
0x1800465ac  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800465b0  xor     r8d, r8d; bWaitAll
0x1800465b3  lea     rdx, [rsp+108h+Handles]; lpHandles
0x1800465b8  lea     ecx, [r8+1]; nCount
0x1800465bc  call    cs:__imp_WaitForMultipleObjectsEx
0x1800465c2  mov     esi, eax
0x1800465c4  test    r15b, r15b
0x1800465c7  jz      short loc_180046578
0x1800465c9  test    esi, esi
0x1800465cb  jz      short loc_1800465E8
0x1800465cd  call    cs:__imp_GetLastError
0x1800465d3  test    eax, eax
0x1800465d5  jle     short loc_1800465DF
0x1800465d7  movzx   eax, ax
0x1800465da  or      eax, 80070000h
0x1800465df  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x1800465e6  jmp     short loc_18004660D
0x1800465e8  lea     rdx, [rsp+108h+Reply]; Reply
0x1800465ed  lea     rcx, [rsp+108h+pAsync]; pAsync
0x1800465f2  call    cs:__imp_RpcAsyncCompleteCall
0x1800465f8  test    eax, eax
0x1800465fa  jz      short loc_18004662C
0x1800465fc  jle     short loc_180046606
0x1800465fe  movzx   eax, ax
0x180046601  or      eax, 80070000h
0x180046606  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004660d  mov     r8d, 4CCh; unsigned int
0x180046613  mov     [rsp+108h+Reply], eax
0x180046617  mov     [rsp+108h+bAlertable], eax
0x18004661b  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180046622  mov     ecx, 2; unsigned __int8
0x180046627  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004662c  mov     rcx, qword ptr [rsp+108h+pAsync.u]; hObject
0x180046634  test    rcx, rcx
0x180046637  jz      short loc_18004663F
0x180046639  call    cs:__imp_CloseHandle
0x18004663f  test    r15b, r15b
0x180046642  jz      short loc_180046683
0x180046644  mov     [rsp+108h+Reply], 800705B4h
0x18004664c  lea     rdx, [rsp+108h+var_BC]
0x180046651  lea     rcx, aWlidcgetconfig; "WLIDCGetConfigString"
0x180046658  call    ??$RPCCallTimedOut@AEAY0BF@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BF@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],ulong &>(char const (&)[21],ulong &)
0x18004665d  mov     eax, [rsp+108h+Reply]
0x180046661  mov     [rsp+108h+bAlertable], eax
0x180046665  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004666c  mov     r8d, 4CCh; unsigned int
0x180046672  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180046679  mov     ecx, 2; unsigned __int8
0x18004667e  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180046683  test    r14b, r14b
0x180046686  jz      short loc_1800466B3
0x180046688  mov     eax, 800704C7h
0x18004668d  mov     [rsp+108h+Reply], eax
0x180046691  mov     [rsp+108h+bAlertable], eax
0x180046695  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004669c  mov     r8d, 4CCh; unsigned int
0x1800466a2  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800466a9  mov     ecx, 2; unsigned __int8
0x1800466ae  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800466b3  cmp     [rsp+108h+Reply], 800706B5h
0x1800466bb  jz      short loc_1800466C7
0x1800466bd  cmp     [rsp+108h+Reply], 800706BAh
0x1800466c5  jnz     short loc_1800466CC
0x1800466c7  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x1800466cc  lea     rcx, [rsp+108h+var_B8]; this
0x1800466d1  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x1800466d6  mov     eax, [rsp+108h+Reply]
0x1800466da  mov     rcx, [rsp+108h+var_28]
0x1800466e2  xor     rcx, rsp; StackCookie
0x1800466e5  call    __security_check_cookie
0x1800466ea  lea     r11, [rsp+108h+var_18]
0x1800466f2  mov     rsi, [r11+30h]
0x1800466f6  mov     r12, [r11+38h]
0x1800466fa  mov     rsp, r11
0x1800466fd  pop     r15
0x1800466ff  pop     r14
0x180046701  pop     r13
0x180046703  retn
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
