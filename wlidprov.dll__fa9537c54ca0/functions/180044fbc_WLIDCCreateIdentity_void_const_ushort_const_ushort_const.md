# WLIDCCreateIdentity(void * const,ushort const *,ushort const *)

- ea: `0x180044fbc`
- end: `0x1800452eb`
- name: `?WLIDCCreateIdentity@@YAJQEAXPEBG1@Z`
- size: `815`
- prototype: `__int64 __fastcall(void *const, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800243c0`

## callees

- `0x18000a400`
- `0x180010c68`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180041bf4`
- `0x180043240`
- `0x180044fbc`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180045084`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180045084`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180045166`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800451b8`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180045166`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800451b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045097`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800451c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045097`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800451c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045235`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045235`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004503d`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004503d`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004518d`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004518d`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800450de`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800450de`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800451ee`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800451ee`

## string_xrefs

- `0x1800450a9`: `RPC failed to create new event, hr = %#x`
- `0x180045202`: `RPC Async complete call failed, hr = %#x`
- `0x18004524d`: `WLIDCCreateIdentity`

## pseudocode

```c
__int64 __fastcall WLIDCCreateIdentity(void *const a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
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
  const unsigned __int16 *v19; // [rsp+50h] [rbp-C8h]
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
    v10 = 521;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 6u, 0, &pAsync, a1, a2, v19);
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
  v10 = 523;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[20],unsigned long &>("WLIDCCreateIdentity", &v18);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x20Bu,
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
      0x20Bu,
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
0x180044fbc  push    rsi
0x180044fbe  push    r12
0x180044fc0  push    r13
0x180044fc2  push    r14
0x180044fc4  push    r15
0x180044fc6  sub     rsp, 0F0h
0x180044fcd  mov     rax, cs:__security_cookie
0x180044fd4  xor     rax, rsp
0x180044fd7  mov     [rsp+118h+var_38], rax
0x180044fdf  mov     [rsp+118h+var_C8], r8
0x180044fe4  mov     r13, rdx
0x180044fe7  mov     r12, rcx
0x180044fea  mov     [rsp+118h+Reply], 0
0x180044ff2  mov     [rsp+118h+dwMilliseconds], 0
0x180044ffa  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x180044fff  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180045004  xor     edx, edx; Val
0x180045006  lea     r8d, [rdx+70h]; Size
0x18004500a  lea     rcx, [rsp+118h+pAsync]; void *
0x18004500f  call    memset_0
0x180045014  mov     esi, [rsp+118h+dwMilliseconds]
0x180045018  mov     [rsp+118h+dwMilliseconds], esi
0x18004501c  mov     [rsp+118h+var_CC], esi
0x180045020  xor     r15b, r15b
0x180045023  mov     [rsp+118h+var_D4], r15b
0x180045028  xor     r14b, r14b
0x18004502b  xorps   xmm0, xmm0
0x18004502e  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x180045033  mov     edx, 70h ; 'p'; Size
0x180045038  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004503d  call    cs:__imp_RpcAsyncInitializeHandle
0x180045043  test    eax, eax
0x180045045  jz      short loc_180045063
0x180045047  jle     short loc_180045051
0x180045049  movzx   eax, ax
0x18004504c  or      eax, 80070000h
0x180045051  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180045058  mov     r8d, 209h
0x18004505e  jmp     loc_18004520F
0x180045063  mov     [rsp+118h+pAsync.UserInfo], 0
0x18004506f  mov     [rsp+118h+pAsync.NotificationType], 1
0x18004507a  xor     r9d, r9d; lpName
0x18004507d  xor     r8d, r8d; bInitialState
0x180045080  xor     edx, edx; bManualReset
0x180045082  xor     ecx, ecx; lpEventAttributes
0x180045084  call    cs:__imp_CreateEventW
0x18004508a  mov     qword ptr [rsp+118h+pAsync.u], rax
0x180045092  test    rax, rax
0x180045095  jnz     short loc_1800450B2
0x180045097  call    cs:__imp_GetLastError
0x18004509d  test    eax, eax
0x18004509f  jle     short loc_1800450A9
0x1800450a1  movzx   eax, ax
0x1800450a4  or      eax, 80070000h
0x1800450a9  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x1800450b0  jmp     short loc_180045058
0x1800450b2  mov     [rsp+118h+Handles], rax
0x1800450b7  mov     rax, [rsp+118h+var_C8]
0x1800450bc  mov     [rsp+118h+var_E8], rax
0x1800450c1  mov     [rsp+118h+var_F0], r13
0x1800450c6  mov     qword ptr [rsp+118h+bAlertable], r12
0x1800450cb  lea     r9, [rsp+118h+pAsync]
0x1800450d0  xor     r8d, r8d; pReturnValue
0x1800450d3  lea     edx, [r8+6]; nProcNum
0x1800450d7  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800450de  call    cs:__imp_Ndr64AsyncClientCall
0x1800450e4  mov     eax, [rsp+118h+Reply]
0x1800450e8  jmp     short loc_180045139
0x1800450ea  test    eax, eax
0x1800450ec  jle     short loc_1800450F6
0x1800450ee  movzx   eax, ax
0x1800450f1  or      eax, 80070000h
0x1800450f6  mov     [rsp+118h+Reply], eax
0x1800450fa  mov     [rsp+118h+bAlertable], eax
0x1800450fe  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180045105  mov     r8d, 20Bh; unsigned int
0x18004510b  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180045112  mov     ecx, 2; unsigned __int8
0x180045117  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004511c  mov     eax, [rsp+118h+Reply]
0x180045120  test    eax, eax
0x180045122  js      short loc_18004512D
0x180045124  mov     eax, 8000FFFFh
0x180045129  mov     [rsp+118h+Reply], eax
0x18004512d  mov     esi, [rsp+118h+dwMilliseconds]
0x180045131  mov     r15b, [rsp+118h+var_D4]
0x180045136  mov     r14b, r15b
0x180045139  test    eax, eax
0x18004513b  jns     short loc_18004514F
0x18004513d  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180045144  mov     r8d, 20Bh
0x18004514a  jmp     loc_180045213
0x18004514f  mov     [rsp+118h+bAlertable], 0; bAlertable
0x180045157  mov     r9d, esi; dwMilliseconds
0x18004515a  xor     r8d, r8d; bWaitAll
0x18004515d  lea     rdx, [rsp+118h+Handles]; lpHandles
0x180045162  lea     ecx, [r8+1]; nCount
0x180045166  call    cs:__imp_WaitForMultipleObjectsEx
0x18004516c  mov     esi, eax
0x18004516e  mov     r12d, 102h
0x180045174  test    r14b, r14b
0x180045177  jnz     short loc_1800451C5
0x180045179  cmp     esi, r12d
0x18004517c  jz      short loc_180045183
0x18004517e  cmp     esi, 1
0x180045181  jnz     short loc_1800451C5
0x180045183  mov     edx, 1; fAbort
0x180045188  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004518d  call    cs:__imp_RpcAsyncCancelCall
0x180045193  cmp     esi, r12d
0x180045196  jnz     short loc_18004519D
0x180045198  mov     r15b, 1
0x18004519b  jmp     short loc_1800451A0
0x18004519d  mov     r14b, 1
0x1800451a0  mov     [rsp+118h+bAlertable], 0; bAlertable
0x1800451a8  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800451ac  xor     r8d, r8d; bWaitAll
0x1800451af  lea     rdx, [rsp+118h+Handles]; lpHandles
0x1800451b4  lea     ecx, [r8+1]; nCount
0x1800451b8  call    cs:__imp_WaitForMultipleObjectsEx
0x1800451be  mov     esi, eax
0x1800451c0  test    r15b, r15b
0x1800451c3  jz      short loc_180045174
0x1800451c5  test    esi, esi
0x1800451c7  jz      short loc_1800451E4
0x1800451c9  call    cs:__imp_GetLastError
0x1800451cf  test    eax, eax
0x1800451d1  jle     short loc_1800451DB
0x1800451d3  movzx   eax, ax
0x1800451d6  or      eax, 80070000h
0x1800451db  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x1800451e2  jmp     short loc_180045209
0x1800451e4  lea     rdx, [rsp+118h+Reply]; Reply
0x1800451e9  lea     rcx, [rsp+118h+pAsync]; pAsync
0x1800451ee  call    cs:__imp_RpcAsyncCompleteCall
0x1800451f4  test    eax, eax
0x1800451f6  jz      short loc_180045228
0x1800451f8  jle     short loc_180045202
0x1800451fa  movzx   eax, ax
0x1800451fd  or      eax, 80070000h
0x180045202  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180045209  mov     r8d, 20Bh; unsigned int
0x18004520f  mov     [rsp+118h+Reply], eax
0x180045213  mov     [rsp+118h+bAlertable], eax
0x180045217  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004521e  mov     ecx, 2; unsigned __int8
0x180045223  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180045228  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x180045230  test    rcx, rcx
0x180045233  jz      short loc_18004523B
0x180045235  call    cs:__imp_CloseHandle
0x18004523b  test    r15b, r15b
0x18004523e  jz      short loc_18004527F
0x180045240  mov     [rsp+118h+Reply], 800705B4h
0x180045248  lea     rdx, [rsp+118h+var_CC]
0x18004524d  lea     rcx, aWlidccreateide; "WLIDCCreateIdentity"
0x180045254  call    ??$RPCCallTimedOut@AEAY0BE@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BE@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[20],ulong &>(char const (&)[20],ulong &)
0x180045259  mov     eax, [rsp+118h+Reply]
0x18004525d  mov     [rsp+118h+bAlertable], eax
0x180045261  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180045268  mov     r8d, 20Bh; unsigned int
0x18004526e  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180045275  mov     ecx, 2; unsigned __int8
0x18004527a  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004527f  test    r14b, r14b
0x180045282  jz      short loc_1800452AF
0x180045284  mov     eax, 800704C7h
0x180045289  mov     [rsp+118h+Reply], eax
0x18004528d  mov     [rsp+118h+bAlertable], eax
0x180045291  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180045298  mov     r8d, 20Bh; unsigned int
0x18004529e  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800452a5  mov     ecx, 2; unsigned __int8
0x1800452aa  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800452af  mov     eax, [rsp+118h+Reply]
0x1800452b3  cmp     eax, 800706B5h
0x1800452b8  jz      short loc_1800452C1
0x1800452ba  cmp     eax, 800706BAh
0x1800452bf  jnz     short loc_1800452CA
0x1800452c1  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x1800452c6  mov     eax, [rsp+118h+Reply]
0x1800452ca  mov     rcx, [rsp+118h+var_38]
0x1800452d2  xor     rcx, rsp; StackCookie
0x1800452d5  call    __security_check_cookie
0x1800452da  add     rsp, 0F0h
0x1800452e1  pop     r15
0x1800452e3  pop     r14
0x1800452e5  pop     r13
0x1800452e7  pop     r12
0x1800452e9  pop     rsi
0x1800452ea  retn
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
