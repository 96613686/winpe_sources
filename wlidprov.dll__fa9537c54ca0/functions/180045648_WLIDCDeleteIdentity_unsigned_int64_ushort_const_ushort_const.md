# WLIDCDeleteIdentity(unsigned __int64,ushort const *,ushort const *)

- ea: `0x180045648`
- end: `0x1800459b5`
- name: `?WLIDCDeleteIdentity@@YAJ_KPEBG1@Z`
- size: `877`
- prototype: `__int64 __fastcall(unsigned __int64, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180024630`

## callees

- `0x18000a400`
- `0x18000f870`
- `0x180010c68`
- `0x180011588`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180041bf4`
- `0x180043240`
- `0x180045648`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180045730`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180045730`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004581b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004586d`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004581b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004586d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045743`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004587e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045743`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004587e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800458ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800458ea`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800456e9`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800456e9`
- `RPCRT4!RpcAsyncCancelCall` at `0x180045842`
- `RPCRT4!RpcAsyncCancelCall` at `0x180045842`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180045793`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180045793`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800458a3`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800458a3`

## string_xrefs

- `0x180045755`: `RPC failed to create new event, hr = %#x`
- `0x1800458b7`: `RPC Async complete call failed, hr = %#x`
- `0x180045902`: `WLIDCDeleteIdentity`

## pseudocode

```c
__int64 __fastcall WLIDCDeleteIdentity(unsigned int a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  __int64 result; // rax
  DWORD v6; // esi
  char v7; // r15
  char v8; // r14
  int LastError; // eax
  const unsigned __int16 *v10; // r9
  unsigned int v11; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v13; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-E8h]
  int Reply; // [rsp+40h] [rbp-C8h] BYREF
  char v16; // [rsp+44h] [rbp-C4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-C0h] BYREF
  DWORD v18; // [rsp+4Ch] [rbp-BCh] BYREF
  __int64 v19; // [rsp+50h] [rbp-B8h] BYREF
  HANDLE Handles[3]; // [rsp+58h] [rbp-B0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-98h] BYREF

  dwMilliseconds = 0;
  WLIDCGetTimeOutValue(a1, (unsigned int)a2, &dwMilliseconds);
  v19 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v19);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v6 = dwMilliseconds;
  v18 = dwMilliseconds;
  v7 = 0;
  v16 = 0;
  v8 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v11 = 532;
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
    v10 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 7u, 0, &pAsync, v19, 1, a2, a3);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v10 = L"RPC call failed, hr = %#x";
    v11 = 534;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v11,
      v10,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
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
LABEL_29:
    v11 = 534;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v7 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[20],unsigned long &>("WLIDCDeleteIdentity", &v18);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x216u,
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
      0x216u,
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
0x180045648  mov     [rsp+arg_0], rsi
0x18004564d  mov     [rsp+arg_18], r12
0x180045652  push    r13
0x180045654  push    r14
0x180045656  push    r15
0x180045658  sub     rsp, 0F0h
0x18004565f  mov     rax, cs:__security_cookie
0x180045666  xor     rax, rsp
0x180045669  mov     [rsp+108h+var_28], rax
0x180045671  mov     r13, r8
0x180045674  mov     r12, rdx
0x180045677  mov     [rsp+108h+dwMilliseconds], 0
0x18004567f  lea     r8, [rsp+108h+dwMilliseconds]; unsigned int *
0x180045684  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180045689  mov     [rsp+108h+Reply], 0
0x180045691  mov     [rsp+108h+var_B8], 0
0x18004569a  lea     rcx, [rsp+108h+var_B8]; this
0x18004569f  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x1800456a4  mov     [rsp+108h+Reply], eax
0x1800456a8  test    eax, eax
0x1800456aa  js      loc_18004598B
0x1800456b0  xor     edx, edx; Val
0x1800456b2  lea     r8d, [rdx+70h]; Size
0x1800456b6  lea     rcx, [rsp+108h+pAsync]; void *
0x1800456bb  call    memset_0
0x1800456c0  mov     esi, [rsp+108h+dwMilliseconds]
0x1800456c4  mov     [rsp+108h+dwMilliseconds], esi
0x1800456c8  mov     [rsp+108h+var_BC], esi
0x1800456cc  xor     r15b, r15b
0x1800456cf  mov     [rsp+108h+var_C4], r15b
0x1800456d4  xor     r14b, r14b
0x1800456d7  xorps   xmm0, xmm0
0x1800456da  movups  xmmword ptr [rsp+108h+Handles], xmm0
0x1800456df  mov     edx, 70h ; 'p'; Size
0x1800456e4  lea     rcx, [rsp+108h+pAsync]; pAsync
0x1800456e9  call    cs:__imp_RpcAsyncInitializeHandle
0x1800456ef  test    eax, eax
0x1800456f1  jz      short loc_18004570F
0x1800456f3  jle     short loc_1800456FD
0x1800456f5  movzx   eax, ax
0x1800456f8  or      eax, 80070000h
0x1800456fd  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180045704  mov     r8d, 214h
0x18004570a  jmp     loc_1800458C4
0x18004570f  mov     [rsp+108h+pAsync.UserInfo], 0
0x18004571b  mov     [rsp+108h+pAsync.NotificationType], 1
0x180045726  xor     r9d, r9d; lpName
0x180045729  xor     r8d, r8d; bInitialState
0x18004572c  xor     edx, edx; bManualReset
0x18004572e  xor     ecx, ecx; lpEventAttributes
0x180045730  call    cs:__imp_CreateEventW
0x180045736  mov     qword ptr [rsp+108h+pAsync.u], rax
0x18004573e  test    rax, rax
0x180045741  jnz     short loc_18004575E
0x180045743  call    cs:__imp_GetLastError
0x180045749  test    eax, eax
0x18004574b  jle     short loc_180045755
0x18004574d  movzx   eax, ax
0x180045750  or      eax, 80070000h
0x180045755  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004575c  jmp     short loc_180045704
0x18004575e  mov     [rsp+108h+Handles], rax
0x180045763  mov     [rsp+108h+var_D0], r13
0x180045768  mov     [rsp+108h+var_D8], r12
0x18004576d  mov     [rsp+108h+var_E0], 1
0x180045776  mov     rax, [rsp+108h+var_B8]
0x18004577b  mov     qword ptr [rsp+108h+bAlertable], rax
0x180045780  lea     r9, [rsp+108h+pAsync]
0x180045785  xor     r8d, r8d; pReturnValue
0x180045788  lea     edx, [r8+7]; nProcNum
0x18004578c  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180045793  call    cs:__imp_Ndr64AsyncClientCall
0x180045799  mov     eax, [rsp+108h+Reply]
0x18004579d  jmp     short loc_1800457EE
0x18004579f  test    eax, eax
0x1800457a1  jle     short loc_1800457AB
0x1800457a3  movzx   eax, ax
0x1800457a6  or      eax, 80070000h
0x1800457ab  mov     [rsp+108h+Reply], eax
0x1800457af  mov     [rsp+108h+bAlertable], eax
0x1800457b3  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x1800457ba  mov     r8d, 216h; unsigned int
0x1800457c0  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800457c7  mov     ecx, 2; unsigned __int8
0x1800457cc  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800457d1  mov     eax, [rsp+108h+Reply]
0x1800457d5  test    eax, eax
0x1800457d7  js      short loc_1800457E2
0x1800457d9  mov     eax, 8000FFFFh
0x1800457de  mov     [rsp+108h+Reply], eax
0x1800457e2  mov     esi, [rsp+108h+dwMilliseconds]
0x1800457e6  mov     r15b, [rsp+108h+var_C4]
0x1800457eb  mov     r14b, r15b
0x1800457ee  test    eax, eax
0x1800457f0  jns     short loc_180045804
0x1800457f2  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x1800457f9  mov     r8d, 216h
0x1800457ff  jmp     loc_1800458C8
0x180045804  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18004580c  mov     r9d, esi; dwMilliseconds
0x18004580f  xor     r8d, r8d; bWaitAll
0x180045812  lea     rdx, [rsp+108h+Handles]; lpHandles
0x180045817  lea     ecx, [r8+1]; nCount
0x18004581b  call    cs:__imp_WaitForMultipleObjectsEx
0x180045821  mov     esi, eax
0x180045823  mov     r12d, 102h
0x180045829  test    r14b, r14b
0x18004582c  jnz     short loc_18004587A
0x18004582e  cmp     esi, r12d
0x180045831  jz      short loc_180045838
0x180045833  cmp     esi, 1
0x180045836  jnz     short loc_18004587A
0x180045838  mov     edx, 1; fAbort
0x18004583d  lea     rcx, [rsp+108h+pAsync]; pAsync
0x180045842  call    cs:__imp_RpcAsyncCancelCall
0x180045848  cmp     esi, r12d
0x18004584b  jnz     short loc_180045852
0x18004584d  mov     r15b, 1
0x180045850  jmp     short loc_180045855
0x180045852  mov     r14b, 1
0x180045855  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18004585d  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180045861  xor     r8d, r8d; bWaitAll
0x180045864  lea     rdx, [rsp+108h+Handles]; lpHandles
0x180045869  lea     ecx, [r8+1]; nCount
0x18004586d  call    cs:__imp_WaitForMultipleObjectsEx
0x180045873  mov     esi, eax
0x180045875  test    r15b, r15b
0x180045878  jz      short loc_180045829
0x18004587a  test    esi, esi
0x18004587c  jz      short loc_180045899
0x18004587e  call    cs:__imp_GetLastError
0x180045884  test    eax, eax
0x180045886  jle     short loc_180045890
0x180045888  movzx   eax, ax
0x18004588b  or      eax, 80070000h
0x180045890  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180045897  jmp     short loc_1800458BE
0x180045899  lea     rdx, [rsp+108h+Reply]; Reply
0x18004589e  lea     rcx, [rsp+108h+pAsync]; pAsync
0x1800458a3  call    cs:__imp_RpcAsyncCompleteCall
0x1800458a9  test    eax, eax
0x1800458ab  jz      short loc_1800458DD
0x1800458ad  jle     short loc_1800458B7
0x1800458af  movzx   eax, ax
0x1800458b2  or      eax, 80070000h
0x1800458b7  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x1800458be  mov     r8d, 216h; unsigned int
0x1800458c4  mov     [rsp+108h+Reply], eax
0x1800458c8  mov     [rsp+108h+bAlertable], eax
0x1800458cc  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800458d3  mov     ecx, 2; unsigned __int8
0x1800458d8  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800458dd  mov     rcx, qword ptr [rsp+108h+pAsync.u]; hObject
0x1800458e5  test    rcx, rcx
0x1800458e8  jz      short loc_1800458F0
0x1800458ea  call    cs:__imp_CloseHandle
0x1800458f0  test    r15b, r15b
0x1800458f3  jz      short loc_180045934
0x1800458f5  mov     [rsp+108h+Reply], 800705B4h
0x1800458fd  lea     rdx, [rsp+108h+var_BC]
0x180045902  lea     rcx, aWlidcdeleteide; "WLIDCDeleteIdentity"
0x180045909  call    ??$RPCCallTimedOut@AEAY0BE@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BE@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[20],ulong &>(char const (&)[20],ulong &)
0x18004590e  mov     eax, [rsp+108h+Reply]
0x180045912  mov     [rsp+108h+bAlertable], eax
0x180045916  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004591d  mov     r8d, 216h; unsigned int
0x180045923  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004592a  mov     ecx, 2; unsigned __int8
0x18004592f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180045934  test    r14b, r14b
0x180045937  jz      short loc_180045964
0x180045939  mov     eax, 800704C7h
0x18004593e  mov     [rsp+108h+Reply], eax
0x180045942  mov     [rsp+108h+bAlertable], eax
0x180045946  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004594d  mov     r8d, 216h; unsigned int
0x180045953  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004595a  mov     ecx, 2; unsigned __int8
0x18004595f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180045964  cmp     [rsp+108h+Reply], 800706B5h
0x18004596c  jz      short loc_180045978
0x18004596e  cmp     [rsp+108h+Reply], 800706BAh
0x180045976  jnz     short loc_18004597D
0x180045978  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004597d  lea     rcx, [rsp+108h+var_B8]; this
0x180045982  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x180045987  mov     eax, [rsp+108h+Reply]
0x18004598b  mov     rcx, [rsp+108h+var_28]
0x180045993  xor     rcx, rsp; StackCookie
0x180045996  call    __security_check_cookie
0x18004599b  lea     r11, [rsp+108h+var_18]
0x1800459a3  mov     rsi, [r11+20h]
0x1800459a7  mov     r12, [r11+38h]
0x1800459ab  mov     rsp, r11
0x1800459ae  pop     r15
0x1800459b0  pop     r14
0x1800459b2  pop     r13
0x1800459b4  retn
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
