# WLIDCUpdateUserAssociatedDeviceProperties(ushort const *,void * const,ulong,ulong,__MIDL_liveidsvc_0003 *)

- ea: `0x18004ffa4`
- end: `0x1800502fd`
- name: `?WLIDCUpdateUserAssociatedDeviceProperties@@YAJPEBGQEAXKKPEAU__MIDL_liveidsvc_0003@@@Z`
- size: `857`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void *const, unsigned int, unsigned int, struct __MIDL_liveidsvc_0003 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180034930`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180045644`
- `0x180046ce0`
- `0x18004cd04`
- `0x18004ffa4`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180050179`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800501ce`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180050179`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800501ce`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180050084`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180050084`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050097`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800501df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050097`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800501df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005024e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005024e`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800501a3`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800501a3`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800500f1`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800500f1`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180050207`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180050207`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18005003d`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18005003d`

## string_xrefs

- `0x1800500a9`: `RPC failed to create new event, hr = %#x`
- `0x18005021b`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCUpdateUserAssociatedDeviceProperties(
        const unsigned __int16 *a1,
        void *const a2,
        int a3,
        int a4,
        struct __MIDL_liveidsvc_0003 *a5)
{
  DWORD v7; // esi
  char v8; // r15
  char v9; // r14
  int LastError; // eax
  const unsigned __int16 *v11; // r9
  unsigned int v12; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v14; // esi
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-108h]
  unsigned int Reply; // [rsp+50h] [rbp-D8h] BYREF
  char v19; // [rsp+54h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+58h] [rbp-D0h] BYREF
  int v21; // [rsp+5Ch] [rbp-CCh]
  int v22; // [rsp+60h] [rbp-C8h]
  DWORD v23; // [rsp+64h] [rbp-C4h] BYREF
  struct __MIDL_liveidsvc_0003 *v24; // [rsp+68h] [rbp-C0h]
  HANDLE Handles[2]; // [rsp+70h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+80h] [rbp-A8h] BYREF

  v21 = a4;
  v22 = a3;
  v24 = a5;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v7 = dwMilliseconds;
  v23 = dwMilliseconds;
  v8 = 0;
  v19 = 0;
  v9 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v11 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v12 = 951;
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
    v11 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_5;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x27u, 0, &pAsync, a1, a2, v22, v21, v24);
  v14 = WaitForMultipleObjectsEx(1u, Handles, 0, v7, 0);
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
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_28;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v11 = L"RPC Async complete call failed, hr = %#x";
  }
  v12 = 953;
LABEL_27:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(
    2u,
    "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
    v12,
    v11,
    *(_QWORD *)bAlertable);
LABEL_28:
  NotificationRoutine = pAsync.u.APC.NotificationRoutine;
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v8 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[42],unsigned long &>(
      (__int64)NotificationRoutine,
      (int *)&v23);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x3B9u,
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
      0x3B9u,
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
0x18004ffa4  push    rsi
0x18004ffa6  push    r12
0x18004ffa8  push    r13
0x18004ffaa  push    r14
0x18004ffac  push    r15
0x18004ffae  sub     rsp, 100h
0x18004ffb5  mov     rax, cs:__security_cookie
0x18004ffbc  xor     rax, rsp
0x18004ffbf  mov     [rsp+128h+var_38], rax
0x18004ffc7  mov     [rsp+128h+var_CC], r9d
0x18004ffcc  mov     [rsp+128h+var_C8], r8d
0x18004ffd1  mov     r13, rdx
0x18004ffd4  mov     r12, rcx
0x18004ffd7  mov     rax, [rsp+128h+arg_20]
0x18004ffdf  mov     [rsp+128h+var_C0], rax
0x18004ffe4  mov     [rsp+128h+Reply], 0
0x18004ffec  mov     [rsp+128h+dwMilliseconds], 0
0x18004fff4  lea     r8, [rsp+128h+dwMilliseconds]; unsigned int *
0x18004fff9  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004fffe  xor     edx, edx; Val
0x180050000  lea     r8d, [rdx+70h]; Size
0x180050004  lea     rcx, [rsp+128h+pAsync]; void *
0x18005000c  call    memset_0
0x180050011  mov     esi, [rsp+128h+dwMilliseconds]
0x180050015  mov     [rsp+128h+dwMilliseconds], esi
0x180050019  mov     [rsp+128h+var_C4], esi
0x18005001d  xor     r15b, r15b
0x180050020  mov     [rsp+128h+var_D4], r15b
0x180050025  xor     r14b, r14b
0x180050028  xorps   xmm0, xmm0
0x18005002b  movups  xmmword ptr [rsp+128h+Handles], xmm0
0x180050030  mov     edx, 70h ; 'p'; Size
0x180050035  lea     rcx, [rsp+128h+pAsync]; pAsync
0x18005003d  call    cs:__imp_RpcAsyncInitializeHandle
0x180050043  test    eax, eax
0x180050045  jz      short loc_180050063
0x180050047  jle     short loc_180050051
0x180050049  movzx   eax, ax
0x18005004c  or      eax, 80070000h
0x180050051  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180050058  mov     r8d, 3B7h
0x18005005e  jmp     loc_180050228
0x180050063  mov     [rsp+128h+pAsync.UserInfo], 0
0x18005006f  mov     [rsp+128h+pAsync.NotificationType], 1
0x18005007a  xor     r9d, r9d; lpName
0x18005007d  xor     r8d, r8d; bInitialState
0x180050080  xor     edx, edx; bManualReset
0x180050082  xor     ecx, ecx; lpEventAttributes
0x180050084  call    cs:__imp_CreateEventW
0x18005008a  mov     qword ptr [rsp+128h+pAsync.u], rax
0x180050092  test    rax, rax
0x180050095  jnz     short loc_1800500B2
0x180050097  call    cs:__imp_GetLastError
0x18005009d  test    eax, eax
0x18005009f  jle     short loc_1800500A9
0x1800500a1  movzx   eax, ax
0x1800500a4  or      eax, 80070000h
0x1800500a9  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x1800500b0  jmp     short loc_180050058
0x1800500b2  mov     [rsp+128h+Handles], rax
0x1800500b7  mov     rax, [rsp+128h+var_C0]
0x1800500bc  mov     [rsp+128h+var_E8], rax
0x1800500c1  mov     eax, [rsp+128h+var_CC]
0x1800500c5  mov     [rsp+128h+var_F0], eax
0x1800500c9  mov     eax, [rsp+128h+var_C8]
0x1800500cd  mov     [rsp+128h+var_F8], eax
0x1800500d1  mov     [rsp+128h+var_100], r13
0x1800500d6  mov     qword ptr [rsp+128h+bAlertable], r12
0x1800500db  lea     r9, [rsp+128h+pAsync]
0x1800500e3  xor     r8d, r8d; pReturnValue
0x1800500e6  lea     edx, [r8+27h]; nProcNum
0x1800500ea  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800500f1  call    cs:__imp_Ndr64AsyncClientCall
0x1800500f7  mov     eax, [rsp+128h+Reply]
0x1800500fb  jmp     short loc_18005014C
0x1800500fd  test    eax, eax
0x1800500ff  jle     short loc_180050109
0x180050101  movzx   eax, ax
0x180050104  or      eax, 80070000h
0x180050109  mov     [rsp+128h+Reply], eax
0x18005010d  mov     [rsp+128h+bAlertable], eax
0x180050111  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180050118  mov     r8d, 3B9h; unsigned int
0x18005011e  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180050125  mov     ecx, 2; unsigned __int8
0x18005012a  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18005012f  mov     eax, [rsp+128h+Reply]
0x180050133  test    eax, eax
0x180050135  js      short loc_180050140
0x180050137  mov     eax, 8000FFFFh
0x18005013c  mov     [rsp+128h+Reply], eax
0x180050140  mov     esi, [rsp+128h+dwMilliseconds]
0x180050144  mov     r15b, [rsp+128h+var_D4]
0x180050149  mov     r14b, r15b
0x18005014c  test    eax, eax
0x18005014e  jns     short loc_180050162
0x180050150  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180050157  mov     r8d, 3B9h
0x18005015d  jmp     loc_18005022C
0x180050162  mov     [rsp+128h+bAlertable], 0; bAlertable
0x18005016a  mov     r9d, esi; dwMilliseconds
0x18005016d  xor     r8d, r8d; bWaitAll
0x180050170  lea     rdx, [rsp+128h+Handles]; lpHandles
0x180050175  lea     ecx, [r8+1]; nCount
0x180050179  call    cs:__imp_WaitForMultipleObjectsEx
0x18005017f  mov     esi, eax
0x180050181  mov     r12d, 102h
0x180050187  test    r14b, r14b
0x18005018a  jnz     short loc_1800501DB
0x18005018c  cmp     esi, r12d
0x18005018f  jz      short loc_180050196
0x180050191  cmp     esi, 1
0x180050194  jnz     short loc_1800501DB
0x180050196  mov     edx, 1; fAbort
0x18005019b  lea     rcx, [rsp+128h+pAsync]; pAsync
0x1800501a3  call    cs:__imp_RpcAsyncCancelCall
0x1800501a9  cmp     esi, r12d
0x1800501ac  jnz     short loc_1800501B3
0x1800501ae  mov     r15b, 1
0x1800501b1  jmp     short loc_1800501B6
0x1800501b3  mov     r14b, 1
0x1800501b6  mov     [rsp+128h+bAlertable], 0; bAlertable
0x1800501be  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800501c2  xor     r8d, r8d; bWaitAll
0x1800501c5  lea     rdx, [rsp+128h+Handles]; lpHandles
0x1800501ca  lea     ecx, [r8+1]; nCount
0x1800501ce  call    cs:__imp_WaitForMultipleObjectsEx
0x1800501d4  mov     esi, eax
0x1800501d6  test    r15b, r15b
0x1800501d9  jz      short loc_180050187
0x1800501db  test    esi, esi
0x1800501dd  jz      short loc_1800501FA
0x1800501df  call    cs:__imp_GetLastError
0x1800501e5  test    eax, eax
0x1800501e7  jle     short loc_1800501F1
0x1800501e9  movzx   eax, ax
0x1800501ec  or      eax, 80070000h
0x1800501f1  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x1800501f8  jmp     short loc_180050222
0x1800501fa  lea     rdx, [rsp+128h+Reply]; Reply
0x1800501ff  lea     rcx, [rsp+128h+pAsync]; pAsync
0x180050207  call    cs:__imp_RpcAsyncCompleteCall
0x18005020d  test    eax, eax
0x18005020f  jz      short loc_180050241
0x180050211  jle     short loc_18005021B
0x180050213  movzx   eax, ax
0x180050216  or      eax, 80070000h
0x18005021b  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180050222  mov     r8d, 3B9h; unsigned int
0x180050228  mov     [rsp+128h+Reply], eax
0x18005022c  mov     [rsp+128h+bAlertable], eax
0x180050230  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180050237  mov     ecx, 2; unsigned __int8
0x18005023c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180050241  mov     rcx, qword ptr [rsp+128h+pAsync.u]; hObject
0x180050249  test    rcx, rcx
0x18005024c  jz      short loc_180050254
0x18005024e  call    cs:__imp_CloseHandle
0x180050254  test    r15b, r15b
0x180050257  jz      short loc_180050291
0x180050259  mov     [rsp+128h+Reply], 800705B4h
0x180050261  lea     rdx, [rsp+128h+var_C4]
0x180050266  call    ??$RPCCallTimedOut@AEAY0CK@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0CK@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[42],ulong &>(char const (&)[42],ulong &)
0x18005026b  mov     eax, [rsp+128h+Reply]
0x18005026f  mov     [rsp+128h+bAlertable], eax
0x180050273  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18005027a  mov     r8d, 3B9h; unsigned int
0x180050280  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180050287  mov     ecx, 2; unsigned __int8
0x18005028c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180050291  test    r14b, r14b
0x180050294  jz      short loc_1800502C1
0x180050296  mov     eax, 800704C7h
0x18005029b  mov     [rsp+128h+Reply], eax
0x18005029f  mov     [rsp+128h+bAlertable], eax
0x1800502a3  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x1800502aa  mov     r8d, 3B9h; unsigned int
0x1800502b0  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800502b7  mov     ecx, 2; unsigned __int8
0x1800502bc  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800502c1  mov     eax, [rsp+128h+Reply]
0x1800502c5  cmp     eax, 800706B5h
0x1800502ca  jz      short loc_1800502D3
0x1800502cc  cmp     eax, 800706BAh
0x1800502d1  jnz     short loc_1800502DC
0x1800502d3  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x1800502d8  mov     eax, [rsp+128h+Reply]
0x1800502dc  mov     rcx, [rsp+128h+var_38]
0x1800502e4  xor     rcx, rsp; StackCookie
0x1800502e7  call    __security_check_cookie
0x1800502ec  add     rsp, 100h
0x1800502f3  pop     r15
0x1800502f5  pop     r14
0x1800502f7  pop     r13
0x1800502f9  pop     r12
0x1800502fb  pop     rsi
0x1800502fc  retn
0x1800619d4  push    rbp
0x1800619d6  sub     rsp, 50h
0x1800619da  mov     rbp, rdx
0x1800619dd  mov     rcx, [rcx]
0x1800619e0  mov     ecx, [rcx]; unsigned int
0x1800619e2  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x1800619e7  nop
0x1800619e8  add     rsp, 50h
0x1800619ec  pop     rbp
0x1800619ed  retn
```
