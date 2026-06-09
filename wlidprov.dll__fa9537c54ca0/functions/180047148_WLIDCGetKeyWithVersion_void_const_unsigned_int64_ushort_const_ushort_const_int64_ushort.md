# WLIDCGetKeyWithVersion(void * const,unsigned __int64,ushort const *,ushort const *,__int64,ushort * *)

- ea: `0x180047148`
- end: `0x1800474f0`
- name: `?WLIDCGetKeyWithVersion@@YAJQEAX_KPEBG2_JPEAPEAG@Z`
- size: `936`
- prototype: `__int64 __fastcall(void *const, unsigned __int64, const unsigned __int16 *, const unsigned __int16 *, __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180041780`

## callees

- `0x18000a400`
- `0x18000f870`
- `0x180010c68`
- `0x180011588`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180041d98`
- `0x180043240`
- `0x180047148`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004724a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004724a`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180047356`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800473ae`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180047356`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800473ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004725d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800473bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004725d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800473bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004742e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004742e`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180047203`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180047203`
- `RPCRT4!RpcAsyncCancelCall` at `0x180047380`
- `RPCRT4!RpcAsyncCancelCall` at `0x180047380`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800472cb`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800472cb`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800473e7`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800473e7`

## string_xrefs

- `0x18004726f`: `RPC failed to create new event, hr = %#x`
- `0x1800473fb`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCGetKeyWithVersion(
        void *const a1,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        __int64 a5,
        unsigned __int16 **a6)
{
  __int64 result; // rax
  DWORD v9; // esi
  char v10; // r15
  char v11; // r14
  int LastError; // eax
  const unsigned __int16 *v13; // r9
  unsigned int v14; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v16; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-118h]
  int Reply; // [rsp+50h] [rbp-E8h] BYREF
  char v19; // [rsp+54h] [rbp-E4h]
  DWORD dwMilliseconds; // [rsp+58h] [rbp-E0h] BYREF
  DWORD v21; // [rsp+5Ch] [rbp-DCh] BYREF
  __int64 v22; // [rsp+60h] [rbp-D8h] BYREF
  unsigned __int16 **v23; // [rsp+68h] [rbp-D0h]
  const unsigned __int16 *v24; // [rsp+70h] [rbp-C8h]
  const unsigned __int16 *v25; // [rsp+78h] [rbp-C0h]
  HANDLE Handles[2]; // [rsp+80h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+90h] [rbp-A8h] BYREF

  v24 = a4;
  v25 = a3;
  v23 = a6;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  v22 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v22);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v9 = dwMilliseconds;
  v21 = dwMilliseconds;
  v10 = 0;
  v19 = 0;
  v11 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v13 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v14 = 1306;
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
    v13 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x3Du, 0, &pAsync, a1, a2, v25, v24, a5, v23);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v13 = L"RPC call failed, hr = %#x";
    v14 = 1308;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v14,
      v13,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
  v16 = WaitForMultipleObjectsEx(1u, Handles, 0, v9, 0);
  do
  {
    if ( v11 || v16 != 258 && v16 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v16 == 258 )
      v10 = 1;
    else
      v11 = 1;
    v16 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v10 );
  if ( v16 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v13 = L"Encountered error while waiting on RPC call, hr = %#x";
LABEL_29:
    v14 = 1308;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v13 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v10 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[23],unsigned long &>("WLIDCGetKeyWithVersion", &v21);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x51Cu,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v11 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x51Cu,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v22);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x180047148  push    rsi
0x18004714a  push    r12
0x18004714c  push    r13
0x18004714e  push    r14
0x180047150  push    r15
0x180047152  sub     rsp, 110h
0x180047159  mov     rax, cs:__security_cookie
0x180047160  xor     rax, rsp
0x180047163  mov     [rsp+138h+var_38], rax
0x18004716b  mov     [rsp+138h+var_C8], r9
0x180047170  mov     [rsp+138h+var_C0], r8
0x180047175  mov     r13, rdx
0x180047178  mov     r12, rcx
0x18004717b  mov     rax, [rsp+138h+arg_28]
0x180047183  mov     [rsp+138h+var_D0], rax
0x180047188  mov     [rsp+138h+dwMilliseconds], 0
0x180047190  lea     r8, [rsp+138h+dwMilliseconds]; unsigned int *
0x180047195  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004719a  mov     [rsp+138h+Reply], 0
0x1800471a2  mov     [rsp+138h+var_D8], 0
0x1800471ab  lea     rcx, [rsp+138h+var_D8]; this
0x1800471b0  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x1800471b5  mov     [rsp+138h+Reply], eax
0x1800471b9  test    eax, eax
0x1800471bb  js      loc_1800474CF
0x1800471c1  xor     edx, edx; Val
0x1800471c3  lea     r8d, [rdx+70h]; Size
0x1800471c7  lea     rcx, [rsp+138h+pAsync]; void *
0x1800471cf  call    memset_0
0x1800471d4  mov     esi, [rsp+138h+dwMilliseconds]
0x1800471d8  mov     [rsp+138h+dwMilliseconds], esi
0x1800471dc  mov     [rsp+138h+var_DC], esi
0x1800471e0  xor     r15b, r15b
0x1800471e3  mov     [rsp+138h+var_E4], r15b
0x1800471e8  xor     r14b, r14b
0x1800471eb  xorps   xmm0, xmm0
0x1800471ee  movups  xmmword ptr [rsp+138h+Handles], xmm0
0x1800471f6  mov     edx, 70h ; 'p'; Size
0x1800471fb  lea     rcx, [rsp+138h+pAsync]; pAsync
0x180047203  call    cs:__imp_RpcAsyncInitializeHandle
0x180047209  test    eax, eax
0x18004720b  jz      short loc_180047229
0x18004720d  jle     short loc_180047217
0x18004720f  movzx   eax, ax
0x180047212  or      eax, 80070000h
0x180047217  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004721e  mov     r8d, 51Ah
0x180047224  jmp     loc_180047408
0x180047229  mov     [rsp+138h+pAsync.UserInfo], 0
0x180047235  mov     [rsp+138h+pAsync.NotificationType], 1
0x180047240  xor     r9d, r9d; lpName
0x180047243  xor     r8d, r8d; bInitialState
0x180047246  xor     edx, edx; bManualReset
0x180047248  xor     ecx, ecx; lpEventAttributes
0x18004724a  call    cs:__imp_CreateEventW
0x180047250  mov     qword ptr [rsp+138h+pAsync.u], rax
0x180047258  test    rax, rax
0x18004725b  jnz     short loc_180047278
0x18004725d  call    cs:__imp_GetLastError
0x180047263  test    eax, eax
0x180047265  jle     short loc_18004726F
0x180047267  movzx   eax, ax
0x18004726a  or      eax, 80070000h
0x18004726f  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180047276  jmp     short loc_18004721E
0x180047278  mov     [rsp+138h+Handles], rax
0x180047280  mov     rax, [rsp+138h+var_D0]
0x180047285  mov     [rsp+138h+var_F0], rax
0x18004728a  mov     rax, [rsp+138h+arg_20]
0x180047292  mov     [rsp+138h+var_F8], rax
0x180047297  mov     rax, [rsp+138h+var_C8]
0x18004729c  mov     [rsp+138h+var_100], rax
0x1800472a1  mov     rax, [rsp+138h+var_C0]
0x1800472a6  mov     [rsp+138h+var_108], rax
0x1800472ab  mov     [rsp+138h+var_110], r13
0x1800472b0  mov     qword ptr [rsp+138h+bAlertable], r12
0x1800472b5  lea     r9, [rsp+138h+pAsync]
0x1800472bd  xor     r8d, r8d; pReturnValue
0x1800472c0  lea     edx, [r8+3Dh]; nProcNum
0x1800472c4  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800472cb  call    cs:__imp_Ndr64AsyncClientCall
0x1800472d1  mov     eax, [rsp+138h+Reply]
0x1800472d5  jmp     short loc_180047326
0x1800472d7  test    eax, eax
0x1800472d9  jle     short loc_1800472E3
0x1800472db  movzx   eax, ax
0x1800472de  or      eax, 80070000h
0x1800472e3  mov     [rsp+138h+Reply], eax
0x1800472e7  mov     [rsp+138h+bAlertable], eax
0x1800472eb  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x1800472f2  mov     r8d, 51Ch; unsigned int
0x1800472f8  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800472ff  mov     ecx, 2; unsigned __int8
0x180047304  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180047309  mov     eax, [rsp+138h+Reply]
0x18004730d  test    eax, eax
0x18004730f  js      short loc_18004731A
0x180047311  mov     eax, 8000FFFFh
0x180047316  mov     [rsp+138h+Reply], eax
0x18004731a  mov     esi, [rsp+138h+dwMilliseconds]
0x18004731e  mov     r15b, [rsp+138h+var_E4]
0x180047323  mov     r14b, r15b
0x180047326  test    eax, eax
0x180047328  jns     short loc_18004733C
0x18004732a  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180047331  mov     r8d, 51Ch
0x180047337  jmp     loc_18004740C
0x18004733c  mov     [rsp+138h+bAlertable], 0; bAlertable
0x180047344  mov     r9d, esi; dwMilliseconds
0x180047347  xor     r8d, r8d; bWaitAll
0x18004734a  lea     rdx, [rsp+138h+Handles]; lpHandles
0x180047352  lea     ecx, [r8+1]; nCount
0x180047356  call    cs:__imp_WaitForMultipleObjectsEx
0x18004735c  mov     esi, eax
0x18004735e  mov     r12d, 102h
0x180047364  test    r14b, r14b
0x180047367  jnz     short loc_1800473BB
0x180047369  cmp     esi, r12d
0x18004736c  jz      short loc_180047373
0x18004736e  cmp     esi, 1
0x180047371  jnz     short loc_1800473BB
0x180047373  mov     edx, 1; fAbort
0x180047378  lea     rcx, [rsp+138h+pAsync]; pAsync
0x180047380  call    cs:__imp_RpcAsyncCancelCall
0x180047386  cmp     esi, r12d
0x180047389  jnz     short loc_180047390
0x18004738b  mov     r15b, 1
0x18004738e  jmp     short loc_180047393
0x180047390  mov     r14b, 1
0x180047393  mov     [rsp+138h+bAlertable], 0; bAlertable
0x18004739b  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004739f  xor     r8d, r8d; bWaitAll
0x1800473a2  lea     rdx, [rsp+138h+Handles]; lpHandles
0x1800473aa  lea     ecx, [r8+1]; nCount
0x1800473ae  call    cs:__imp_WaitForMultipleObjectsEx
0x1800473b4  mov     esi, eax
0x1800473b6  test    r15b, r15b
0x1800473b9  jz      short loc_180047364
0x1800473bb  test    esi, esi
0x1800473bd  jz      short loc_1800473DA
0x1800473bf  call    cs:__imp_GetLastError
0x1800473c5  test    eax, eax
0x1800473c7  jle     short loc_1800473D1
0x1800473c9  movzx   eax, ax
0x1800473cc  or      eax, 80070000h
0x1800473d1  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x1800473d8  jmp     short loc_180047402
0x1800473da  lea     rdx, [rsp+138h+Reply]; Reply
0x1800473df  lea     rcx, [rsp+138h+pAsync]; pAsync
0x1800473e7  call    cs:__imp_RpcAsyncCompleteCall
0x1800473ed  test    eax, eax
0x1800473ef  jz      short loc_180047421
0x1800473f1  jle     short loc_1800473FB
0x1800473f3  movzx   eax, ax
0x1800473f6  or      eax, 80070000h
0x1800473fb  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180047402  mov     r8d, 51Ch; unsigned int
0x180047408  mov     [rsp+138h+Reply], eax
0x18004740c  mov     [rsp+138h+bAlertable], eax
0x180047410  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180047417  mov     ecx, 2; unsigned __int8
0x18004741c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180047421  mov     rcx, qword ptr [rsp+138h+pAsync.u]; hObject
0x180047429  test    rcx, rcx
0x18004742c  jz      short loc_180047434
0x18004742e  call    cs:__imp_CloseHandle
0x180047434  test    r15b, r15b
0x180047437  jz      short loc_180047478
0x180047439  mov     [rsp+138h+Reply], 800705B4h
0x180047441  lea     rdx, [rsp+138h+var_DC]
0x180047446  lea     rcx, aWlidcgetkeywit; "WLIDCGetKeyWithVersion"
0x18004744d  call    ??$RPCCallTimedOut@AEAY0BH@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BH@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[23],ulong &>(char const (&)[23],ulong &)
0x180047452  mov     eax, [rsp+138h+Reply]
0x180047456  mov     [rsp+138h+bAlertable], eax
0x18004745a  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180047461  mov     r8d, 51Ch; unsigned int
0x180047467  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004746e  mov     ecx, 2; unsigned __int8
0x180047473  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180047478  test    r14b, r14b
0x18004747b  jz      short loc_1800474A8
0x18004747d  mov     eax, 800704C7h
0x180047482  mov     [rsp+138h+Reply], eax
0x180047486  mov     [rsp+138h+bAlertable], eax
0x18004748a  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180047491  mov     r8d, 51Ch; unsigned int
0x180047497  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004749e  mov     ecx, 2; unsigned __int8
0x1800474a3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800474a8  cmp     [rsp+138h+Reply], 800706B5h
0x1800474b0  jz      short loc_1800474BC
0x1800474b2  cmp     [rsp+138h+Reply], 800706BAh
0x1800474ba  jnz     short loc_1800474C1
0x1800474bc  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x1800474c1  lea     rcx, [rsp+138h+var_D8]; this
0x1800474c6  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x1800474cb  mov     eax, [rsp+138h+Reply]
0x1800474cf  mov     rcx, [rsp+138h+var_38]
0x1800474d7  xor     rcx, rsp; StackCookie
0x1800474da  call    __security_check_cookie
0x1800474df  add     rsp, 110h
0x1800474e6  pop     r15
0x1800474e8  pop     r14
0x1800474ea  pop     r13
0x1800474ec  pop     r12
0x1800474ee  pop     rsi
0x1800474ef  retn
0x180057620  push    rbp
0x180057622  sub     rsp, 50h
0x180057626  mov     rbp, rdx
0x180057629  mov     rcx, [rcx]
0x18005762c  mov     ecx, [rcx]; unsigned int
0x18005762e  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x180057633  nop
0x180057634  add     rsp, 50h
0x180057638  pop     rbp
0x180057639  retn
```
