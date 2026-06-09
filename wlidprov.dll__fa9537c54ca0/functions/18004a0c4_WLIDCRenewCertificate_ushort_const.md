# WLIDCRenewCertificate(ushort const *)

- ea: `0x18004a0c4`
- end: `0x18004a3fc`
- name: `?WLIDCRenewCertificate@@YAJPEBG@Z`
- size: `824`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180041900`

## callees

- `0x18000a400`
- `0x18000f870`
- `0x180011588`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180041d0c`
- `0x180043240`
- `0x18004a0c4`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004a18c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004a18c`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004a266`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004a2b8`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004a266`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004a2b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a19f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a2c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a19f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a2c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a335`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a335`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004a148`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004a148`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004a28a`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004a28a`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004a1df`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004a1df`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004a2ee`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004a2ee`

## string_xrefs

- `0x18004a1b1`: `RPC failed to create new event, hr = %#x`
- `0x18004a302`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCRenewCertificate(const unsigned __int16 *a1)
{
  __int64 result; // rax
  char v3; // r15
  char v4; // r14
  int LastError; // eax
  const unsigned __int16 *v6; // r9
  unsigned int v7; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v9; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-C8h]
  int Reply; // [rsp+30h] [rbp-B8h] BYREF
  char v12; // [rsp+34h] [rbp-B4h]
  int v13; // [rsp+38h] [rbp-B0h] BYREF
  __int64 v14; // [rsp+40h] [rbp-A8h] BYREF
  HANDLE Handles[3]; // [rsp+48h] [rbp-A0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+60h] [rbp-88h] BYREF

  v14 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v14);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v13 = 600000;
  v3 = 0;
  v12 = 0;
  v4 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v6 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v7 = 1217;
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
    v6 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&OnlineProviderCertInterface_ProxyInfo, 0, 0, &pAsync, v14, a1);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v6 = L"RPC call failed, hr = %#x";
    v7 = 1219;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v7,
      v6,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
  v9 = WaitForMultipleObjectsEx(1u, Handles, 0, 0x927C0u, 0);
  do
  {
    if ( v4 || v9 != 258 && v9 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v9 == 258 )
      v3 = 1;
    else
      v4 = 1;
    v9 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v3 );
  if ( v9 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v6 = L"Encountered error while waiting on RPC call, hr = %#x";
LABEL_29:
    v7 = 1219;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v6 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v3 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[22],unsigned long &>("WLIDCRenewCertificate", &v13);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x4C3u,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v4 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x4C3u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v14);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x18004a0c4  mov     [rsp+arg_8], rsi
0x18004a0c9  mov     [rsp+arg_10], r14
0x18004a0ce  push    r15
0x18004a0d0  sub     rsp, 0E0h
0x18004a0d7  mov     rax, cs:__security_cookie
0x18004a0de  xor     rax, rsp
0x18004a0e1  mov     [rsp+0E8h+var_18], rax
0x18004a0e9  mov     rsi, rcx
0x18004a0ec  mov     [rsp+0E8h+Reply], 0
0x18004a0f4  mov     [rsp+0E8h+var_A8], 0
0x18004a0fd  lea     rcx, [rsp+0E8h+var_A8]; this
0x18004a102  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18004a107  mov     [rsp+0E8h+Reply], eax
0x18004a10b  test    eax, eax
0x18004a10d  js      loc_18004A3D6
0x18004a113  xor     edx, edx; Val
0x18004a115  lea     r8d, [rdx+70h]; Size
0x18004a119  lea     rcx, [rsp+0E8h+pAsync]; void *
0x18004a11e  call    memset_0
0x18004a123  mov     [rsp+0E8h+var_B0], 927C0h
0x18004a12b  xor     r15b, r15b
0x18004a12e  mov     [rsp+0E8h+var_B4], r15b
0x18004a133  xor     r14b, r14b
0x18004a136  xorps   xmm0, xmm0
0x18004a139  movups  xmmword ptr [rsp+0E8h+Handles], xmm0
0x18004a13e  mov     edx, 70h ; 'p'; Size
0x18004a143  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x18004a148  call    cs:__imp_RpcAsyncInitializeHandle
0x18004a14e  test    eax, eax
0x18004a150  jz      short loc_18004A16E
0x18004a152  jle     short loc_18004A15C
0x18004a154  movzx   eax, ax
0x18004a157  or      eax, 80070000h
0x18004a15c  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004a163  mov     r8d, 4C1h
0x18004a169  jmp     loc_18004A30F
0x18004a16e  mov     [rsp+0E8h+pAsync.UserInfo], 0
0x18004a177  mov     [rsp+0E8h+pAsync.NotificationType], 1
0x18004a182  xor     r9d, r9d; lpName
0x18004a185  xor     r8d, r8d; bInitialState
0x18004a188  xor     edx, edx; bManualReset
0x18004a18a  xor     ecx, ecx; lpEventAttributes
0x18004a18c  call    cs:__imp_CreateEventW
0x18004a192  mov     qword ptr [rsp+0E8h+pAsync.u], rax
0x18004a19a  test    rax, rax
0x18004a19d  jnz     short loc_18004A1BA
0x18004a19f  call    cs:__imp_GetLastError
0x18004a1a5  test    eax, eax
0x18004a1a7  jle     short loc_18004A1B1
0x18004a1a9  movzx   eax, ax
0x18004a1ac  or      eax, 80070000h
0x18004a1b1  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004a1b8  jmp     short loc_18004A163
0x18004a1ba  mov     [rsp+0E8h+Handles], rax
0x18004a1bf  mov     [rsp+0E8h+var_C0], rsi
0x18004a1c4  mov     rax, [rsp+0E8h+var_A8]
0x18004a1c9  mov     qword ptr [rsp+0E8h+bAlertable], rax
0x18004a1ce  lea     r9, [rsp+0E8h+pAsync]
0x18004a1d3  xor     r8d, r8d; pReturnValue
0x18004a1d6  xor     edx, edx; nProcNum
0x18004a1d8  lea     rcx, ?OnlineProviderCertInterface_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004a1df  call    cs:__imp_Ndr64AsyncClientCall
0x18004a1e5  mov     eax, [rsp+0E8h+Reply]
0x18004a1e9  jmp     short loc_18004A236
0x18004a1eb  test    eax, eax
0x18004a1ed  jle     short loc_18004A1F7
0x18004a1ef  movzx   eax, ax
0x18004a1f2  or      eax, 80070000h
0x18004a1f7  mov     [rsp+0E8h+Reply], eax
0x18004a1fb  mov     [rsp+0E8h+bAlertable], eax
0x18004a1ff  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004a206  mov     r8d, 4C3h; unsigned int
0x18004a20c  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004a213  mov     ecx, 2; unsigned __int8
0x18004a218  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004a21d  mov     eax, [rsp+0E8h+Reply]
0x18004a221  test    eax, eax
0x18004a223  js      short loc_18004A22E
0x18004a225  mov     eax, 8000FFFFh
0x18004a22a  mov     [rsp+0E8h+Reply], eax
0x18004a22e  mov     r15b, [rsp+0E8h+var_B4]
0x18004a233  mov     r14b, r15b
0x18004a236  test    eax, eax
0x18004a238  jns     short loc_18004A24C
0x18004a23a  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004a241  mov     r8d, 4C3h
0x18004a247  jmp     loc_18004A313
0x18004a24c  mov     [rsp+0E8h+bAlertable], 0; bAlertable
0x18004a254  mov     r9d, 927C0h; dwMilliseconds
0x18004a25a  xor     r8d, r8d; bWaitAll
0x18004a25d  lea     rdx, [rsp+0E8h+Handles]; lpHandles
0x18004a262  lea     ecx, [r8+1]; nCount
0x18004a266  call    cs:__imp_WaitForMultipleObjectsEx
0x18004a26c  mov     esi, eax
0x18004a26e  test    r14b, r14b
0x18004a271  jnz     short loc_18004A2C5
0x18004a273  cmp     esi, 102h
0x18004a279  jz      short loc_18004A280
0x18004a27b  cmp     esi, 1
0x18004a27e  jnz     short loc_18004A2C5
0x18004a280  mov     edx, 1; fAbort
0x18004a285  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x18004a28a  call    cs:__imp_RpcAsyncCancelCall
0x18004a290  cmp     esi, 102h
0x18004a296  jnz     short loc_18004A29D
0x18004a298  mov     r15b, 1
0x18004a29b  jmp     short loc_18004A2A0
0x18004a29d  mov     r14b, 1
0x18004a2a0  mov     [rsp+0E8h+bAlertable], 0; bAlertable
0x18004a2a8  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004a2ac  xor     r8d, r8d; bWaitAll
0x18004a2af  lea     rdx, [rsp+0E8h+Handles]; lpHandles
0x18004a2b4  lea     ecx, [r8+1]; nCount
0x18004a2b8  call    cs:__imp_WaitForMultipleObjectsEx
0x18004a2be  mov     esi, eax
0x18004a2c0  test    r15b, r15b
0x18004a2c3  jz      short loc_18004A26E
0x18004a2c5  test    esi, esi
0x18004a2c7  jz      short loc_18004A2E4
0x18004a2c9  call    cs:__imp_GetLastError
0x18004a2cf  test    eax, eax
0x18004a2d1  jle     short loc_18004A2DB
0x18004a2d3  movzx   eax, ax
0x18004a2d6  or      eax, 80070000h
0x18004a2db  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004a2e2  jmp     short loc_18004A309
0x18004a2e4  lea     rdx, [rsp+0E8h+Reply]; Reply
0x18004a2e9  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x18004a2ee  call    cs:__imp_RpcAsyncCompleteCall
0x18004a2f4  test    eax, eax
0x18004a2f6  jz      short loc_18004A328
0x18004a2f8  jle     short loc_18004A302
0x18004a2fa  movzx   eax, ax
0x18004a2fd  or      eax, 80070000h
0x18004a302  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004a309  mov     r8d, 4C3h; unsigned int
0x18004a30f  mov     [rsp+0E8h+Reply], eax
0x18004a313  mov     [rsp+0E8h+bAlertable], eax
0x18004a317  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004a31e  mov     ecx, 2; unsigned __int8
0x18004a323  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004a328  mov     rcx, qword ptr [rsp+0E8h+pAsync.u]; hObject
0x18004a330  test    rcx, rcx
0x18004a333  jz      short loc_18004A33B
0x18004a335  call    cs:__imp_CloseHandle
0x18004a33b  test    r15b, r15b
0x18004a33e  jz      short loc_18004A37F
0x18004a340  mov     [rsp+0E8h+Reply], 800705B4h
0x18004a348  lea     rdx, [rsp+0E8h+var_B0]
0x18004a34d  lea     rcx, aWlidcrenewcert; "WLIDCRenewCertificate"
0x18004a354  call    ??$RPCCallTimedOut@AEAY0BG@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BG@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[22],ulong &>(char const (&)[22],ulong &)
0x18004a359  mov     eax, [rsp+0E8h+Reply]
0x18004a35d  mov     [rsp+0E8h+bAlertable], eax
0x18004a361  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004a368  mov     r8d, 4C3h; unsigned int
0x18004a36e  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004a375  mov     ecx, 2; unsigned __int8
0x18004a37a  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004a37f  test    r14b, r14b
0x18004a382  jz      short loc_18004A3AF
0x18004a384  mov     eax, 800704C7h
0x18004a389  mov     [rsp+0E8h+Reply], eax
0x18004a38d  mov     [rsp+0E8h+bAlertable], eax
0x18004a391  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004a398  mov     r8d, 4C3h; unsigned int
0x18004a39e  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004a3a5  mov     ecx, 2; unsigned __int8
0x18004a3aa  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004a3af  cmp     [rsp+0E8h+Reply], 800706B5h
0x18004a3b7  jz      short loc_18004A3C3
0x18004a3b9  cmp     [rsp+0E8h+Reply], 800706BAh
0x18004a3c1  jnz     short loc_18004A3C8
0x18004a3c3  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004a3c8  lea     rcx, [rsp+0E8h+var_A8]; this
0x18004a3cd  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18004a3d2  mov     eax, [rsp+0E8h+Reply]
0x18004a3d6  mov     rcx, [rsp+0E8h+var_18]
0x18004a3de  xor     rcx, rsp; StackCookie
0x18004a3e1  call    __security_check_cookie
0x18004a3e6  lea     r11, [rsp+0E8h+var_8]
0x18004a3ee  mov     rsi, [r11+18h]
0x18004a3f2  mov     r14, [r11+20h]
0x18004a3f6  mov     rsp, r11
0x18004a3f9  pop     r15
0x18004a3fb  retn
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
