# WLIDCEnumerateUserAssociatedDevices(void * const,ulong,ushort *,ulong *,__MIDL_liveidsvc_0003 * *)

- ea: `0x180049268`
- end: `0x1800495cc`
- name: `?WLIDCEnumerateUserAssociatedDevices@@YAJQEAXKPEAGPEAKPEAPEAU__MIDL_liveidsvc_0003@@@Z`
- size: `868`
- prototype: `__int64 __fastcall(void *const, unsigned int, unsigned __int16 *, unsigned int *, struct __MIDL_liveidsvc_0003 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002b600`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x1800455b8`
- `0x180046ce0`
- `0x180049268`
- `0x18004cd04`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180049441`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180049496`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180049441`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180049496`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180049348`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180049348`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004935b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800494a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004935b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800494a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049516`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049516`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004946b`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004946b`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800493b9`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800493b9`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800494cf`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800494cf`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180049301`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180049301`

## string_xrefs

- `0x18004936d`: `RPC failed to create new event, hr = %#x`
- `0x1800494e3`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCEnumerateUserAssociatedDevices(
        void *const a1,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned int *a4,
        struct __MIDL_liveidsvc_0003 **a5)
{
  DWORD v7; // esi
  char v8; // r15
  char v9; // r14
  int LastError; // eax
  const unsigned __int16 *v11; // r9
  unsigned int v12; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v14; // esi
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-118h]
  unsigned int Reply; // [rsp+50h] [rbp-E8h] BYREF
  char v18; // [rsp+54h] [rbp-E4h]
  DWORD dwMilliseconds; // [rsp+58h] [rbp-E0h] BYREF
  DWORD v20; // [rsp+5Ch] [rbp-DCh] BYREF
  struct __MIDL_liveidsvc_0003 **v21; // [rsp+60h] [rbp-D8h]
  unsigned int *v22; // [rsp+68h] [rbp-D0h]
  unsigned __int16 *v23; // [rsp+70h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+78h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+90h] [rbp-A8h] BYREF

  v22 = a4;
  v23 = a3;
  v21 = a5;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v7 = dwMilliseconds;
  v20 = dwMilliseconds;
  v8 = 0;
  v18 = 0;
  v9 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v11 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v12 = 938;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x26u, 0, &pAsync, a1, a2, v23, v22, v21);
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
  v12 = 940;
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
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v8 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[36],unsigned long &>(
      (__int64)"WLIDCEnumerateUserAssociatedDevices",
      (int *)&v20);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x3ACu,
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
      0x3ACu,
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
0x180049268  push    rsi
0x18004926a  push    r12
0x18004926c  push    r13
0x18004926e  push    r14
0x180049270  push    r15
0x180049272  sub     rsp, 110h
0x180049279  mov     rax, cs:__security_cookie
0x180049280  xor     rax, rsp
0x180049283  mov     [rsp+138h+var_38], rax
0x18004928b  mov     [rsp+138h+var_D0], r9
0x180049290  mov     [rsp+138h+var_C8], r8
0x180049295  mov     r13d, edx
0x180049298  mov     r12, rcx
0x18004929b  mov     rax, [rsp+138h+arg_20]
0x1800492a3  mov     [rsp+138h+var_D8], rax
0x1800492a8  mov     [rsp+138h+Reply], 0
0x1800492b0  mov     [rsp+138h+dwMilliseconds], 0
0x1800492b8  lea     r8, [rsp+138h+dwMilliseconds]; unsigned int *
0x1800492bd  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x1800492c2  xor     edx, edx; Val
0x1800492c4  lea     r8d, [rdx+70h]; Size
0x1800492c8  lea     rcx, [rsp+138h+pAsync]; void *
0x1800492d0  call    memset_0
0x1800492d5  mov     esi, [rsp+138h+dwMilliseconds]
0x1800492d9  mov     [rsp+138h+dwMilliseconds], esi
0x1800492dd  mov     [rsp+138h+var_DC], esi
0x1800492e1  xor     r15b, r15b
0x1800492e4  mov     [rsp+138h+var_E4], r15b
0x1800492e9  xor     r14b, r14b
0x1800492ec  xorps   xmm0, xmm0
0x1800492ef  movups  xmmword ptr [rsp+138h+Handles], xmm0
0x1800492f4  mov     edx, 70h ; 'p'; Size
0x1800492f9  lea     rcx, [rsp+138h+pAsync]; pAsync
0x180049301  call    cs:__imp_RpcAsyncInitializeHandle
0x180049307  test    eax, eax
0x180049309  jz      short loc_180049327
0x18004930b  jle     short loc_180049315
0x18004930d  movzx   eax, ax
0x180049310  or      eax, 80070000h
0x180049315  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004931c  mov     r8d, 3AAh
0x180049322  jmp     loc_1800494F0
0x180049327  mov     [rsp+138h+pAsync.UserInfo], 0
0x180049333  mov     [rsp+138h+pAsync.NotificationType], 1
0x18004933e  xor     r9d, r9d; lpName
0x180049341  xor     r8d, r8d; bInitialState
0x180049344  xor     edx, edx; bManualReset
0x180049346  xor     ecx, ecx; lpEventAttributes
0x180049348  call    cs:__imp_CreateEventW
0x18004934e  mov     qword ptr [rsp+138h+pAsync.u], rax
0x180049356  test    rax, rax
0x180049359  jnz     short loc_180049376
0x18004935b  call    cs:__imp_GetLastError
0x180049361  test    eax, eax
0x180049363  jle     short loc_18004936D
0x180049365  movzx   eax, ax
0x180049368  or      eax, 80070000h
0x18004936d  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180049374  jmp     short loc_18004931C
0x180049376  mov     [rsp+138h+Handles], rax
0x18004937b  mov     rax, [rsp+138h+var_D8]
0x180049380  mov     [rsp+138h+var_F8], rax
0x180049385  mov     rax, [rsp+138h+var_D0]
0x18004938a  mov     [rsp+138h+var_100], rax
0x18004938f  mov     rax, [rsp+138h+var_C8]
0x180049394  mov     [rsp+138h+var_108], rax
0x180049399  mov     [rsp+138h+var_110], r13d
0x18004939e  mov     qword ptr [rsp+138h+bAlertable], r12
0x1800493a3  lea     r9, [rsp+138h+pAsync]
0x1800493ab  xor     r8d, r8d; pReturnValue
0x1800493ae  lea     edx, [r8+26h]; nProcNum
0x1800493b2  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800493b9  call    cs:__imp_Ndr64AsyncClientCall
0x1800493bf  mov     eax, [rsp+138h+Reply]
0x1800493c3  jmp     short loc_180049414
0x1800493c5  test    eax, eax
0x1800493c7  jle     short loc_1800493D1
0x1800493c9  movzx   eax, ax
0x1800493cc  or      eax, 80070000h
0x1800493d1  mov     [rsp+138h+Reply], eax
0x1800493d5  mov     [rsp+138h+bAlertable], eax
0x1800493d9  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x1800493e0  mov     r8d, 3ACh; unsigned int
0x1800493e6  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800493ed  mov     ecx, 2; unsigned __int8
0x1800493f2  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800493f7  mov     eax, [rsp+138h+Reply]
0x1800493fb  test    eax, eax
0x1800493fd  js      short loc_180049408
0x1800493ff  mov     eax, 8000FFFFh
0x180049404  mov     [rsp+138h+Reply], eax
0x180049408  mov     esi, [rsp+138h+dwMilliseconds]
0x18004940c  mov     r15b, [rsp+138h+var_E4]
0x180049411  mov     r14b, r15b
0x180049414  test    eax, eax
0x180049416  jns     short loc_18004942A
0x180049418  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004941f  mov     r8d, 3ACh
0x180049425  jmp     loc_1800494F4
0x18004942a  mov     [rsp+138h+bAlertable], 0; bAlertable
0x180049432  mov     r9d, esi; dwMilliseconds
0x180049435  xor     r8d, r8d; bWaitAll
0x180049438  lea     rdx, [rsp+138h+Handles]; lpHandles
0x18004943d  lea     ecx, [r8+1]; nCount
0x180049441  call    cs:__imp_WaitForMultipleObjectsEx
0x180049447  mov     esi, eax
0x180049449  mov     r12d, 102h
0x18004944f  test    r14b, r14b
0x180049452  jnz     short loc_1800494A3
0x180049454  cmp     esi, r12d
0x180049457  jz      short loc_18004945E
0x180049459  cmp     esi, 1
0x18004945c  jnz     short loc_1800494A3
0x18004945e  mov     edx, 1; fAbort
0x180049463  lea     rcx, [rsp+138h+pAsync]; pAsync
0x18004946b  call    cs:__imp_RpcAsyncCancelCall
0x180049471  cmp     esi, r12d
0x180049474  jnz     short loc_18004947B
0x180049476  mov     r15b, 1
0x180049479  jmp     short loc_18004947E
0x18004947b  mov     r14b, 1
0x18004947e  mov     [rsp+138h+bAlertable], 0; bAlertable
0x180049486  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004948a  xor     r8d, r8d; bWaitAll
0x18004948d  lea     rdx, [rsp+138h+Handles]; lpHandles
0x180049492  lea     ecx, [r8+1]; nCount
0x180049496  call    cs:__imp_WaitForMultipleObjectsEx
0x18004949c  mov     esi, eax
0x18004949e  test    r15b, r15b
0x1800494a1  jz      short loc_18004944F
0x1800494a3  test    esi, esi
0x1800494a5  jz      short loc_1800494C2
0x1800494a7  call    cs:__imp_GetLastError
0x1800494ad  test    eax, eax
0x1800494af  jle     short loc_1800494B9
0x1800494b1  movzx   eax, ax
0x1800494b4  or      eax, 80070000h
0x1800494b9  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x1800494c0  jmp     short loc_1800494EA
0x1800494c2  lea     rdx, [rsp+138h+Reply]; Reply
0x1800494c7  lea     rcx, [rsp+138h+pAsync]; pAsync
0x1800494cf  call    cs:__imp_RpcAsyncCompleteCall
0x1800494d5  test    eax, eax
0x1800494d7  jz      short loc_180049509
0x1800494d9  jle     short loc_1800494E3
0x1800494db  movzx   eax, ax
0x1800494de  or      eax, 80070000h
0x1800494e3  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x1800494ea  mov     r8d, 3ACh; unsigned int
0x1800494f0  mov     [rsp+138h+Reply], eax
0x1800494f4  mov     [rsp+138h+bAlertable], eax
0x1800494f8  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800494ff  mov     ecx, 2; unsigned __int8
0x180049504  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180049509  mov     rcx, qword ptr [rsp+138h+pAsync.u]; hObject
0x180049511  test    rcx, rcx
0x180049514  jz      short loc_18004951C
0x180049516  call    cs:__imp_CloseHandle
0x18004951c  test    r15b, r15b
0x18004951f  jz      short loc_180049560
0x180049521  mov     [rsp+138h+Reply], 800705B4h
0x180049529  lea     rdx, [rsp+138h+var_DC]
0x18004952e  lea     rcx, aWlidcenumerate; "WLIDCEnumerateUserAssociatedDevices"
0x180049535  call    ??$RPCCallTimedOut@AEAY0CE@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0CE@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[36],ulong &>(char const (&)[36],ulong &)
0x18004953a  mov     eax, [rsp+138h+Reply]
0x18004953e  mov     [rsp+138h+bAlertable], eax
0x180049542  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180049549  mov     r8d, 3ACh; unsigned int
0x18004954f  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180049556  mov     ecx, 2; unsigned __int8
0x18004955b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180049560  test    r14b, r14b
0x180049563  jz      short loc_180049590
0x180049565  mov     eax, 800704C7h
0x18004956a  mov     [rsp+138h+Reply], eax
0x18004956e  mov     [rsp+138h+bAlertable], eax
0x180049572  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180049579  mov     r8d, 3ACh; unsigned int
0x18004957f  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180049586  mov     ecx, 2; unsigned __int8
0x18004958b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180049590  mov     eax, [rsp+138h+Reply]
0x180049594  cmp     eax, 800706B5h
0x180049599  jz      short loc_1800495A2
0x18004959b  cmp     eax, 800706BAh
0x1800495a0  jnz     short loc_1800495AB
0x1800495a2  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x1800495a7  mov     eax, [rsp+138h+Reply]
0x1800495ab  mov     rcx, [rsp+138h+var_38]
0x1800495b3  xor     rcx, rsp; StackCookie
0x1800495b6  call    __security_check_cookie
0x1800495bb  add     rsp, 110h
0x1800495c2  pop     r15
0x1800495c4  pop     r14
0x1800495c6  pop     r13
0x1800495c8  pop     r12
0x1800495ca  pop     rsi
0x1800495cb  retn
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
