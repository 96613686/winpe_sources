# WLIDCGetAuthError(void * const,ushort const *,ushort * *)

- ea: `0x1800495d4`
- end: `0x180049903`
- name: `?WLIDCGetAuthError@@YAJQEAXPEBGPEAPEAG@Z`
- size: `815`
- prototype: `__int64 __fastcall(void *const, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002935c`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180044e20`
- `0x180046ce0`
- `0x1800495d4`
- `0x18004cd04`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004977e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800497d0`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004977e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800497d0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004969c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004969c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800496af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800497e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800496af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800497e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004984d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004984d`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800497a5`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800497a5`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800496f6`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800496f6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180049806`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180049806`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180049655`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180049655`

## string_xrefs

- `0x1800496c1`: `RPC failed to create new event, hr = %#x`
- `0x18004981a`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCGetAuthError(void *const a1, const unsigned __int16 *a2, unsigned __int16 **a3)
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
  unsigned __int16 **v19; // [rsp+50h] [rbp-C8h]
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
    v10 = 1005;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x2Cu, 0, &pAsync, a1, a2, v19);
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
  v10 = 1007;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[18],unsigned long &>(
      (__int64)"WLIDCGetAuthError",
      (int *)&v18);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x3EFu,
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
      0x3EFu,
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
0x1800495d4  push    rsi
0x1800495d6  push    r12
0x1800495d8  push    r13
0x1800495da  push    r14
0x1800495dc  push    r15
0x1800495de  sub     rsp, 0F0h
0x1800495e5  mov     rax, cs:__security_cookie
0x1800495ec  xor     rax, rsp
0x1800495ef  mov     [rsp+118h+var_38], rax
0x1800495f7  mov     [rsp+118h+var_C8], r8
0x1800495fc  mov     r13, rdx
0x1800495ff  mov     r12, rcx
0x180049602  mov     [rsp+118h+Reply], 0
0x18004960a  mov     [rsp+118h+dwMilliseconds], 0
0x180049612  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x180049617  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004961c  xor     edx, edx; Val
0x18004961e  lea     r8d, [rdx+70h]; Size
0x180049622  lea     rcx, [rsp+118h+pAsync]; void *
0x180049627  call    memset_0
0x18004962c  mov     esi, [rsp+118h+dwMilliseconds]
0x180049630  mov     [rsp+118h+dwMilliseconds], esi
0x180049634  mov     [rsp+118h+var_CC], esi
0x180049638  xor     r15b, r15b
0x18004963b  mov     [rsp+118h+var_D4], r15b
0x180049640  xor     r14b, r14b
0x180049643  xorps   xmm0, xmm0
0x180049646  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x18004964b  mov     edx, 70h ; 'p'; Size
0x180049650  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180049655  call    cs:__imp_RpcAsyncInitializeHandle
0x18004965b  test    eax, eax
0x18004965d  jz      short loc_18004967B
0x18004965f  jle     short loc_180049669
0x180049661  movzx   eax, ax
0x180049664  or      eax, 80070000h
0x180049669  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180049670  mov     r8d, 3EDh
0x180049676  jmp     loc_180049827
0x18004967b  mov     [rsp+118h+pAsync.UserInfo], 0
0x180049687  mov     [rsp+118h+pAsync.NotificationType], 1
0x180049692  xor     r9d, r9d; lpName
0x180049695  xor     r8d, r8d; bInitialState
0x180049698  xor     edx, edx; bManualReset
0x18004969a  xor     ecx, ecx; lpEventAttributes
0x18004969c  call    cs:__imp_CreateEventW
0x1800496a2  mov     qword ptr [rsp+118h+pAsync.u], rax
0x1800496aa  test    rax, rax
0x1800496ad  jnz     short loc_1800496CA
0x1800496af  call    cs:__imp_GetLastError
0x1800496b5  test    eax, eax
0x1800496b7  jle     short loc_1800496C1
0x1800496b9  movzx   eax, ax
0x1800496bc  or      eax, 80070000h
0x1800496c1  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x1800496c8  jmp     short loc_180049670
0x1800496ca  mov     [rsp+118h+Handles], rax
0x1800496cf  mov     rax, [rsp+118h+var_C8]
0x1800496d4  mov     [rsp+118h+var_E8], rax
0x1800496d9  mov     [rsp+118h+var_F0], r13
0x1800496de  mov     qword ptr [rsp+118h+bAlertable], r12
0x1800496e3  lea     r9, [rsp+118h+pAsync]
0x1800496e8  xor     r8d, r8d; pReturnValue
0x1800496eb  lea     edx, [r8+2Ch]; nProcNum
0x1800496ef  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800496f6  call    cs:__imp_Ndr64AsyncClientCall
0x1800496fc  mov     eax, [rsp+118h+Reply]
0x180049700  jmp     short loc_180049751
0x180049702  test    eax, eax
0x180049704  jle     short loc_18004970E
0x180049706  movzx   eax, ax
0x180049709  or      eax, 80070000h
0x18004970e  mov     [rsp+118h+Reply], eax
0x180049712  mov     [rsp+118h+bAlertable], eax
0x180049716  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004971d  mov     r8d, 3EFh; unsigned int
0x180049723  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004972a  mov     ecx, 2; unsigned __int8
0x18004972f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180049734  mov     eax, [rsp+118h+Reply]
0x180049738  test    eax, eax
0x18004973a  js      short loc_180049745
0x18004973c  mov     eax, 8000FFFFh
0x180049741  mov     [rsp+118h+Reply], eax
0x180049745  mov     esi, [rsp+118h+dwMilliseconds]
0x180049749  mov     r15b, [rsp+118h+var_D4]
0x18004974e  mov     r14b, r15b
0x180049751  test    eax, eax
0x180049753  jns     short loc_180049767
0x180049755  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004975c  mov     r8d, 3EFh
0x180049762  jmp     loc_18004982B
0x180049767  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004976f  mov     r9d, esi; dwMilliseconds
0x180049772  xor     r8d, r8d; bWaitAll
0x180049775  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004977a  lea     ecx, [r8+1]; nCount
0x18004977e  call    cs:__imp_WaitForMultipleObjectsEx
0x180049784  mov     esi, eax
0x180049786  mov     r12d, 102h
0x18004978c  test    r14b, r14b
0x18004978f  jnz     short loc_1800497DD
0x180049791  cmp     esi, r12d
0x180049794  jz      short loc_18004979B
0x180049796  cmp     esi, 1
0x180049799  jnz     short loc_1800497DD
0x18004979b  mov     edx, 1; fAbort
0x1800497a0  lea     rcx, [rsp+118h+pAsync]; pAsync
0x1800497a5  call    cs:__imp_RpcAsyncCancelCall
0x1800497ab  cmp     esi, r12d
0x1800497ae  jnz     short loc_1800497B5
0x1800497b0  mov     r15b, 1
0x1800497b3  jmp     short loc_1800497B8
0x1800497b5  mov     r14b, 1
0x1800497b8  mov     [rsp+118h+bAlertable], 0; bAlertable
0x1800497c0  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800497c4  xor     r8d, r8d; bWaitAll
0x1800497c7  lea     rdx, [rsp+118h+Handles]; lpHandles
0x1800497cc  lea     ecx, [r8+1]; nCount
0x1800497d0  call    cs:__imp_WaitForMultipleObjectsEx
0x1800497d6  mov     esi, eax
0x1800497d8  test    r15b, r15b
0x1800497db  jz      short loc_18004978C
0x1800497dd  test    esi, esi
0x1800497df  jz      short loc_1800497FC
0x1800497e1  call    cs:__imp_GetLastError
0x1800497e7  test    eax, eax
0x1800497e9  jle     short loc_1800497F3
0x1800497eb  movzx   eax, ax
0x1800497ee  or      eax, 80070000h
0x1800497f3  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x1800497fa  jmp     short loc_180049821
0x1800497fc  lea     rdx, [rsp+118h+Reply]; Reply
0x180049801  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180049806  call    cs:__imp_RpcAsyncCompleteCall
0x18004980c  test    eax, eax
0x18004980e  jz      short loc_180049840
0x180049810  jle     short loc_18004981A
0x180049812  movzx   eax, ax
0x180049815  or      eax, 80070000h
0x18004981a  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180049821  mov     r8d, 3EFh; unsigned int
0x180049827  mov     [rsp+118h+Reply], eax
0x18004982b  mov     [rsp+118h+bAlertable], eax
0x18004982f  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180049836  mov     ecx, 2; unsigned __int8
0x18004983b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180049840  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x180049848  test    rcx, rcx
0x18004984b  jz      short loc_180049853
0x18004984d  call    cs:__imp_CloseHandle
0x180049853  test    r15b, r15b
0x180049856  jz      short loc_180049897
0x180049858  mov     [rsp+118h+Reply], 800705B4h
0x180049860  lea     rdx, [rsp+118h+var_CC]
0x180049865  lea     rcx, aWlidcgetauther; "WLIDCGetAuthError"
0x18004986c  call    ??$RPCCallTimedOut@AEAY0BC@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BC@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[18],ulong &>(char const (&)[18],ulong &)
0x180049871  mov     eax, [rsp+118h+Reply]
0x180049875  mov     [rsp+118h+bAlertable], eax
0x180049879  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180049880  mov     r8d, 3EFh; unsigned int
0x180049886  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004988d  mov     ecx, 2; unsigned __int8
0x180049892  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180049897  test    r14b, r14b
0x18004989a  jz      short loc_1800498C7
0x18004989c  mov     eax, 800704C7h
0x1800498a1  mov     [rsp+118h+Reply], eax
0x1800498a5  mov     [rsp+118h+bAlertable], eax
0x1800498a9  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x1800498b0  mov     r8d, 3EFh; unsigned int
0x1800498b6  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800498bd  mov     ecx, 2; unsigned __int8
0x1800498c2  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800498c7  mov     eax, [rsp+118h+Reply]
0x1800498cb  cmp     eax, 800706B5h
0x1800498d0  jz      short loc_1800498D9
0x1800498d2  cmp     eax, 800706BAh
0x1800498d7  jnz     short loc_1800498E2
0x1800498d9  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x1800498de  mov     eax, [rsp+118h+Reply]
0x1800498e2  mov     rcx, [rsp+118h+var_38]
0x1800498ea  xor     rcx, rsp; StackCookie
0x1800498ed  call    __security_check_cookie
0x1800498f2  add     rsp, 0F0h
0x1800498f9  pop     r15
0x1800498fb  pop     r14
0x1800498fd  pop     r13
0x1800498ff  pop     r12
0x180049901  pop     rsi
0x180049902  retn
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
