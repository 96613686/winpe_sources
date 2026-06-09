# WLIDCConnectIdentity(void * const,_WLID_CONNECT_PARAM * const)

- ea: `0x180044544`
- end: `0x18004486d`
- name: `?WLIDCConnectIdentity@@YAJQEAXQEAU_WLID_CONNECT_PARAM@@@Z`
- size: `809`
- prototype: `__int64 __fastcall(void *const, struct _WLID_CONNECT_PARAM *const)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800238ec`
- `0x1800415e0`

## callees

- `0x18000a400`
- `0x180010c68`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180041c80`
- `0x180043240`
- `0x180044544`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180044607`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180044607`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800446df`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180044731`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800446df`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180044731`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004461a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044742`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004461a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044742`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800447ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800447ae`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800445c6`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800445c6`
- `RPCRT4!RpcAsyncCancelCall` at `0x180044706`
- `RPCRT4!RpcAsyncCancelCall` at `0x180044706`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180044657`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180044657`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180044767`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180044767`

## string_xrefs

- `0x18004462c`: `RPC failed to create new event, hr = %#x`
- `0x18004477b`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCConnectIdentity(void *const a1, struct _WLID_CONNECT_PARAM *const a2)
{
  DWORD v4; // esi
  char v5; // r15
  char v6; // r14
  int LastError; // eax
  const unsigned __int16 *v8; // r9
  unsigned int v9; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v11; // esi
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-C8h]
  unsigned int Reply; // [rsp+30h] [rbp-B8h] BYREF
  char v15; // [rsp+34h] [rbp-B4h]
  DWORD dwMilliseconds; // [rsp+38h] [rbp-B0h] BYREF
  DWORD v17; // [rsp+3Ch] [rbp-ACh] BYREF
  HANDLE Handles[2]; // [rsp+40h] [rbp-A8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+50h] [rbp-98h] BYREF

  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v4 = dwMilliseconds;
  v17 = dwMilliseconds;
  v5 = 0;
  v15 = 0;
  v6 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v9 = 488;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 3u, 0, &pAsync, a1, a2);
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
  v9 = 490;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],unsigned long &>("WLIDCConnectIdentity", &v17);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x1EAu,
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
      0x1EAu,
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
0x180044544  mov     [rsp+arg_10], rsi
0x180044549  mov     [rsp+arg_18], r12
0x18004454e  push    r13
0x180044550  push    r14
0x180044552  push    r15
0x180044554  sub     rsp, 0D0h
0x18004455b  mov     rax, cs:__security_cookie
0x180044562  xor     rax, rsp
0x180044565  mov     [rsp+0E8h+var_28], rax
0x18004456d  mov     r13, rdx
0x180044570  mov     r12, rcx
0x180044573  mov     [rsp+0E8h+Reply], 0
0x18004457b  mov     [rsp+0E8h+dwMilliseconds], 0
0x180044583  lea     r8, [rsp+0E8h+dwMilliseconds]; unsigned int *
0x180044588  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004458d  xor     edx, edx; Val
0x18004458f  lea     r8d, [rdx+70h]; Size
0x180044593  lea     rcx, [rsp+0E8h+pAsync]; void *
0x180044598  call    memset_0
0x18004459d  mov     esi, [rsp+0E8h+dwMilliseconds]
0x1800445a1  mov     [rsp+0E8h+dwMilliseconds], esi
0x1800445a5  mov     [rsp+0E8h+var_AC], esi
0x1800445a9  xor     r15b, r15b
0x1800445ac  mov     [rsp+0E8h+var_B4], r15b
0x1800445b1  xor     r14b, r14b
0x1800445b4  xorps   xmm0, xmm0
0x1800445b7  movups  xmmword ptr [rsp+0E8h+Handles], xmm0
0x1800445bc  mov     edx, 70h ; 'p'; Size
0x1800445c1  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x1800445c6  call    cs:__imp_RpcAsyncInitializeHandle
0x1800445cc  test    eax, eax
0x1800445ce  jz      short loc_1800445EC
0x1800445d0  jle     short loc_1800445DA
0x1800445d2  movzx   eax, ax
0x1800445d5  or      eax, 80070000h
0x1800445da  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x1800445e1  mov     r8d, 1E8h
0x1800445e7  jmp     loc_180044788
0x1800445ec  mov     [rsp+0E8h+pAsync.UserInfo], 0
0x1800445f5  mov     [rsp+0E8h+pAsync.NotificationType], 1
0x1800445fd  xor     r9d, r9d; lpName
0x180044600  xor     r8d, r8d; bInitialState
0x180044603  xor     edx, edx; bManualReset
0x180044605  xor     ecx, ecx; lpEventAttributes
0x180044607  call    cs:__imp_CreateEventW
0x18004460d  mov     qword ptr [rsp+0E8h+pAsync.u], rax
0x180044615  test    rax, rax
0x180044618  jnz     short loc_180044635
0x18004461a  call    cs:__imp_GetLastError
0x180044620  test    eax, eax
0x180044622  jle     short loc_18004462C
0x180044624  movzx   eax, ax
0x180044627  or      eax, 80070000h
0x18004462c  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180044633  jmp     short loc_1800445E1
0x180044635  mov     [rsp+0E8h+Handles], rax
0x18004463a  mov     [rsp+0E8h+var_C0], r13
0x18004463f  mov     qword ptr [rsp+0E8h+bAlertable], r12
0x180044644  lea     r9, [rsp+0E8h+pAsync]
0x180044649  xor     r8d, r8d; pReturnValue
0x18004464c  lea     edx, [r8+3]; nProcNum
0x180044650  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180044657  call    cs:__imp_Ndr64AsyncClientCall
0x18004465d  mov     eax, [rsp+0E8h+Reply]
0x180044661  jmp     short loc_1800446B2
0x180044663  test    eax, eax
0x180044665  jle     short loc_18004466F
0x180044667  movzx   eax, ax
0x18004466a  or      eax, 80070000h
0x18004466f  mov     [rsp+0E8h+Reply], eax
0x180044673  mov     [rsp+0E8h+bAlertable], eax
0x180044677  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004467e  mov     r8d, 1EAh; unsigned int
0x180044684  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004468b  mov     ecx, 2; unsigned __int8
0x180044690  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180044695  mov     eax, [rsp+0E8h+Reply]
0x180044699  test    eax, eax
0x18004469b  js      short loc_1800446A6
0x18004469d  mov     eax, 8000FFFFh
0x1800446a2  mov     [rsp+0E8h+Reply], eax
0x1800446a6  mov     esi, [rsp+0E8h+dwMilliseconds]
0x1800446aa  mov     r15b, [rsp+0E8h+var_B4]
0x1800446af  mov     r14b, r15b
0x1800446b2  test    eax, eax
0x1800446b4  jns     short loc_1800446C8
0x1800446b6  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x1800446bd  mov     r8d, 1EAh
0x1800446c3  jmp     loc_18004478C
0x1800446c8  mov     [rsp+0E8h+bAlertable], 0; bAlertable
0x1800446d0  mov     r9d, esi; dwMilliseconds
0x1800446d3  xor     r8d, r8d; bWaitAll
0x1800446d6  lea     rdx, [rsp+0E8h+Handles]; lpHandles
0x1800446db  lea     ecx, [r8+1]; nCount
0x1800446df  call    cs:__imp_WaitForMultipleObjectsEx
0x1800446e5  mov     esi, eax
0x1800446e7  mov     r12d, 102h
0x1800446ed  test    r14b, r14b
0x1800446f0  jnz     short loc_18004473E
0x1800446f2  cmp     esi, r12d
0x1800446f5  jz      short loc_1800446FC
0x1800446f7  cmp     esi, 1
0x1800446fa  jnz     short loc_18004473E
0x1800446fc  mov     edx, 1; fAbort
0x180044701  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x180044706  call    cs:__imp_RpcAsyncCancelCall
0x18004470c  cmp     esi, r12d
0x18004470f  jnz     short loc_180044716
0x180044711  mov     r15b, 1
0x180044714  jmp     short loc_180044719
0x180044716  mov     r14b, 1
0x180044719  mov     [rsp+0E8h+bAlertable], 0; bAlertable
0x180044721  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180044725  xor     r8d, r8d; bWaitAll
0x180044728  lea     rdx, [rsp+0E8h+Handles]; lpHandles
0x18004472d  lea     ecx, [r8+1]; nCount
0x180044731  call    cs:__imp_WaitForMultipleObjectsEx
0x180044737  mov     esi, eax
0x180044739  test    r15b, r15b
0x18004473c  jz      short loc_1800446ED
0x18004473e  test    esi, esi
0x180044740  jz      short loc_18004475D
0x180044742  call    cs:__imp_GetLastError
0x180044748  test    eax, eax
0x18004474a  jle     short loc_180044754
0x18004474c  movzx   eax, ax
0x18004474f  or      eax, 80070000h
0x180044754  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004475b  jmp     short loc_180044782
0x18004475d  lea     rdx, [rsp+0E8h+Reply]; Reply
0x180044762  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x180044767  call    cs:__imp_RpcAsyncCompleteCall
0x18004476d  test    eax, eax
0x18004476f  jz      short loc_1800447A1
0x180044771  jle     short loc_18004477B
0x180044773  movzx   eax, ax
0x180044776  or      eax, 80070000h
0x18004477b  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180044782  mov     r8d, 1EAh; unsigned int
0x180044788  mov     [rsp+0E8h+Reply], eax
0x18004478c  mov     [rsp+0E8h+bAlertable], eax
0x180044790  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180044797  mov     ecx, 2; unsigned __int8
0x18004479c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800447a1  mov     rcx, qword ptr [rsp+0E8h+pAsync.u]; hObject
0x1800447a9  test    rcx, rcx
0x1800447ac  jz      short loc_1800447B4
0x1800447ae  call    cs:__imp_CloseHandle
0x1800447b4  test    r15b, r15b
0x1800447b7  jz      short loc_1800447F8
0x1800447b9  mov     [rsp+0E8h+Reply], 800705B4h
0x1800447c1  lea     rdx, [rsp+0E8h+var_AC]
0x1800447c6  lea     rcx, aWlidcconnectid_0; "WLIDCConnectIdentity"
0x1800447cd  call    ??$RPCCallTimedOut@AEAY0BF@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BF@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],ulong &>(char const (&)[21],ulong &)
0x1800447d2  mov     eax, [rsp+0E8h+Reply]
0x1800447d6  mov     [rsp+0E8h+bAlertable], eax
0x1800447da  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x1800447e1  mov     r8d, 1EAh; unsigned int
0x1800447e7  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800447ee  mov     ecx, 2; unsigned __int8
0x1800447f3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800447f8  test    r14b, r14b
0x1800447fb  jz      short loc_180044828
0x1800447fd  mov     eax, 800704C7h
0x180044802  mov     [rsp+0E8h+Reply], eax
0x180044806  mov     [rsp+0E8h+bAlertable], eax
0x18004480a  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180044811  mov     r8d, 1EAh; unsigned int
0x180044817  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004481e  mov     ecx, 2; unsigned __int8
0x180044823  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180044828  mov     eax, [rsp+0E8h+Reply]
0x18004482c  cmp     eax, 800706B5h
0x180044831  jz      short loc_18004483A
0x180044833  cmp     eax, 800706BAh
0x180044838  jnz     short loc_180044843
0x18004483a  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004483f  mov     eax, [rsp+0E8h+Reply]
0x180044843  mov     rcx, [rsp+0E8h+var_28]
0x18004484b  xor     rcx, rsp; StackCookie
0x18004484e  call    __security_check_cookie
0x180044853  lea     r11, [rsp+0E8h+var_18]
0x18004485b  mov     rsi, [r11+30h]
0x18004485f  mov     r12, [r11+38h]
0x180044863  mov     rsp, r11
0x180044866  pop     r15
0x180044868  pop     r14
0x18004486a  pop     r13
0x18004486c  retn
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
