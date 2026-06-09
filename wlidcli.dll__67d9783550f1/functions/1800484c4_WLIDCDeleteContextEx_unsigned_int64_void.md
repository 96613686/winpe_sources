# WLIDCDeleteContextEx(unsigned __int64,void * *)

- ea: `0x1800484c4`
- end: `0x180048810`
- name: `?WLIDCDeleteContextEx@@YAJ_KPEAPEAX@Z`
- size: `844`
- prototype: `int(unsigned __int64, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000b2b0`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180044fc4`
- `0x180046ce0`
- `0x1800484c4`
- `0x18004cd04`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004866c`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800486be`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004866c`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800486be`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004858f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004858f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800485a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800486cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800485a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800486cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004873b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004873b`
- `RPCRT4!RpcAsyncCancelCall` at `0x180048693`
- `RPCRT4!RpcAsyncCancelCall` at `0x180048693`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800485df`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800485df`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800486f4`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800486f4`
- `RPCRT4!RpcSsDestroyClientContext` at `0x1800487d7`
- `RPCRT4!RpcSsDestroyClientContext` at `0x1800487d7`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004854b`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004854b`

## string_xrefs

- `0x1800485b4`: `RPC failed to create new event, hr = %#x`
- `0x180048708`: `RPC Async complete call failed, hr = %#x`
- `0x180048753`: `WLIDCDeleteContextEx`

## pseudocode

```c
__int64 __fastcall WLIDCDeleteContextEx(__int64 a1, void **a2)
{
  DWORD v4; // esi
  char v5; // r12
  char v6; // r14
  int LastError; // eax
  const unsigned __int16 *v8; // r9
  unsigned int v9; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v11; // esi
  int v12; // eax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-D8h]
  int Reply; // [rsp+30h] [rbp-C8h] BYREF
  char v16; // [rsp+34h] [rbp-C4h]
  DWORD dwMilliseconds; // [rsp+38h] [rbp-C0h] BYREF
  DWORD v18; // [rsp+3Ch] [rbp-BCh] BYREF
  void **v19; // [rsp+40h] [rbp-B8h]
  HANDLE Handles[3]; // [rsp+48h] [rbp-B0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+60h] [rbp-98h] BYREF

  v19 = a2;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue(a1, (unsigned int)a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v4 = dwMilliseconds;
  v18 = dwMilliseconds;
  v5 = 0;
  v16 = 0;
  v6 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v9 = 621;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0xDu, 0, &pAsync, a1, a2);
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
  v9 = 623;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],unsigned long &>(
      (__int64)"WLIDCDeleteContextEx",
      (int *)&v18);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x26Fu,
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
      0x26Fu,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  v12 = Reply;
  if ( Reply == -2147023179 || Reply == -2147023174 )
  {
    TraceServiceStatus();
    v12 = Reply;
  }
  if ( v12 < 0 )
  {
    RpcSsDestroyClientContext(a2);
    *a2 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800484c4  mov     [rsp+arg_10], rsi
0x1800484c9  mov     [rsp+arg_18], r12
0x1800484ce  push    r13
0x1800484d0  push    r14
0x1800484d2  push    r15
0x1800484d4  sub     rsp, 0E0h
0x1800484db  mov     rax, cs:__security_cookie
0x1800484e2  xor     rax, rsp
0x1800484e5  mov     [rsp+0F8h+var_28], rax
0x1800484ed  mov     r15, rdx
0x1800484f0  mov     r13, rcx
0x1800484f3  mov     [rsp+0F8h+var_B8], rdx
0x1800484f8  mov     [rsp+0F8h+Reply], 0
0x180048500  mov     [rsp+0F8h+dwMilliseconds], 0
0x180048508  lea     r8, [rsp+0F8h+dwMilliseconds]; unsigned int *
0x18004850d  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180048512  xor     edx, edx; Val
0x180048514  lea     r8d, [rdx+70h]; Size
0x180048518  lea     rcx, [rsp+0F8h+pAsync]; void *
0x18004851d  call    memset_0
0x180048522  mov     esi, [rsp+0F8h+dwMilliseconds]
0x180048526  mov     [rsp+0F8h+dwMilliseconds], esi
0x18004852a  mov     [rsp+0F8h+var_BC], esi
0x18004852e  xor     r12b, r12b
0x180048531  mov     [rsp+0F8h+var_C4], r12b
0x180048536  xor     r14b, r14b
0x180048539  xorps   xmm0, xmm0
0x18004853c  movups  xmmword ptr [rsp+0F8h+Handles], xmm0
0x180048541  mov     edx, 70h ; 'p'; Size
0x180048546  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x18004854b  call    cs:__imp_RpcAsyncInitializeHandle
0x180048551  test    eax, eax
0x180048553  jz      short loc_180048571
0x180048555  jle     short loc_18004855F
0x180048557  movzx   eax, ax
0x18004855a  or      eax, 80070000h
0x18004855f  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180048566  mov     r8d, 26Dh
0x18004856c  jmp     loc_180048715
0x180048571  mov     [rsp+0F8h+pAsync.UserInfo], 0
0x18004857a  mov     [rsp+0F8h+pAsync.NotificationType], 1
0x180048585  xor     r9d, r9d; lpName
0x180048588  xor     r8d, r8d; bInitialState
0x18004858b  xor     edx, edx; bManualReset
0x18004858d  xor     ecx, ecx; lpEventAttributes
0x18004858f  call    cs:__imp_CreateEventW
0x180048595  mov     qword ptr [rsp+0F8h+pAsync.u], rax
0x18004859d  test    rax, rax
0x1800485a0  jnz     short loc_1800485BD
0x1800485a2  call    cs:__imp_GetLastError
0x1800485a8  test    eax, eax
0x1800485aa  jle     short loc_1800485B4
0x1800485ac  movzx   eax, ax
0x1800485af  or      eax, 80070000h
0x1800485b4  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x1800485bb  jmp     short loc_180048566
0x1800485bd  mov     [rsp+0F8h+Handles], rax
0x1800485c2  mov     [rsp+0F8h+var_D0], r15
0x1800485c7  mov     qword ptr [rsp+0F8h+bAlertable], r13
0x1800485cc  lea     r9, [rsp+0F8h+pAsync]
0x1800485d1  xor     r8d, r8d; pReturnValue
0x1800485d4  lea     edx, [r8+0Dh]; nProcNum
0x1800485d8  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800485df  call    cs:__imp_Ndr64AsyncClientCall
0x1800485e5  mov     eax, [rsp+0F8h+Reply]
0x1800485e9  jmp     short loc_18004863F
0x1800485eb  test    eax, eax
0x1800485ed  jle     short loc_1800485F7
0x1800485ef  movzx   eax, ax
0x1800485f2  or      eax, 80070000h
0x1800485f7  mov     [rsp+0F8h+Reply], eax
0x1800485fb  mov     [rsp+0F8h+bAlertable], eax
0x1800485ff  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180048606  mov     r8d, 26Fh; unsigned int
0x18004860c  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180048613  mov     ecx, 2; unsigned __int8
0x180048618  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004861d  mov     eax, [rsp+0F8h+Reply]
0x180048621  test    eax, eax
0x180048623  js      short loc_18004862E
0x180048625  mov     eax, 8000FFFFh
0x18004862a  mov     [rsp+0F8h+Reply], eax
0x18004862e  mov     esi, [rsp+0F8h+dwMilliseconds]
0x180048632  mov     r12b, [rsp+0F8h+var_C4]
0x180048637  mov     r14b, r12b
0x18004863a  mov     r15, [rsp+0F8h+var_B8]
0x18004863f  test    eax, eax
0x180048641  jns     short loc_180048655
0x180048643  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004864a  mov     r8d, 26Fh
0x180048650  jmp     loc_180048719
0x180048655  mov     [rsp+0F8h+bAlertable], 0; bAlertable
0x18004865d  mov     r9d, esi; dwMilliseconds
0x180048660  xor     r8d, r8d; bWaitAll
0x180048663  lea     rdx, [rsp+0F8h+Handles]; lpHandles
0x180048668  lea     ecx, [r8+1]; nCount
0x18004866c  call    cs:__imp_WaitForMultipleObjectsEx
0x180048672  mov     esi, eax
0x180048674  mov     r13d, 102h
0x18004867a  test    r14b, r14b
0x18004867d  jnz     short loc_1800486CB
0x18004867f  cmp     esi, r13d
0x180048682  jz      short loc_180048689
0x180048684  cmp     esi, 1
0x180048687  jnz     short loc_1800486CB
0x180048689  mov     edx, 1; fAbort
0x18004868e  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x180048693  call    cs:__imp_RpcAsyncCancelCall
0x180048699  cmp     esi, r13d
0x18004869c  jnz     short loc_1800486A3
0x18004869e  mov     r12b, 1
0x1800486a1  jmp     short loc_1800486A6
0x1800486a3  mov     r14b, 1
0x1800486a6  mov     [rsp+0F8h+bAlertable], 0; bAlertable
0x1800486ae  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800486b2  xor     r8d, r8d; bWaitAll
0x1800486b5  lea     rdx, [rsp+0F8h+Handles]; lpHandles
0x1800486ba  lea     ecx, [r8+1]; nCount
0x1800486be  call    cs:__imp_WaitForMultipleObjectsEx
0x1800486c4  mov     esi, eax
0x1800486c6  test    r12b, r12b
0x1800486c9  jz      short loc_18004867A
0x1800486cb  test    esi, esi
0x1800486cd  jz      short loc_1800486EA
0x1800486cf  call    cs:__imp_GetLastError
0x1800486d5  test    eax, eax
0x1800486d7  jle     short loc_1800486E1
0x1800486d9  movzx   eax, ax
0x1800486dc  or      eax, 80070000h
0x1800486e1  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x1800486e8  jmp     short loc_18004870F
0x1800486ea  lea     rdx, [rsp+0F8h+Reply]; Reply
0x1800486ef  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x1800486f4  call    cs:__imp_RpcAsyncCompleteCall
0x1800486fa  test    eax, eax
0x1800486fc  jz      short loc_18004872E
0x1800486fe  jle     short loc_180048708
0x180048700  movzx   eax, ax
0x180048703  or      eax, 80070000h
0x180048708  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004870f  mov     r8d, 26Fh; unsigned int
0x180048715  mov     [rsp+0F8h+Reply], eax
0x180048719  mov     [rsp+0F8h+bAlertable], eax
0x18004871d  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180048724  mov     ecx, 2; unsigned __int8
0x180048729  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004872e  mov     rcx, qword ptr [rsp+0F8h+pAsync.u]; hObject
0x180048736  test    rcx, rcx
0x180048739  jz      short loc_180048741
0x18004873b  call    cs:__imp_CloseHandle
0x180048741  test    r12b, r12b
0x180048744  jz      short loc_180048785
0x180048746  mov     [rsp+0F8h+Reply], 800705B4h
0x18004874e  lea     rdx, [rsp+0F8h+var_BC]
0x180048753  lea     rcx, aWlidcdeletecon; "WLIDCDeleteContextEx"
0x18004875a  call    ??$RPCCallTimedOut@AEAY0BF@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BF@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],ulong &>(char const (&)[21],ulong &)
0x18004875f  mov     eax, [rsp+0F8h+Reply]
0x180048763  mov     [rsp+0F8h+bAlertable], eax
0x180048767  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004876e  mov     r8d, 26Fh; unsigned int
0x180048774  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004877b  mov     ecx, 2; unsigned __int8
0x180048780  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180048785  test    r14b, r14b
0x180048788  jz      short loc_1800487B5
0x18004878a  mov     eax, 800704C7h
0x18004878f  mov     [rsp+0F8h+Reply], eax
0x180048793  mov     [rsp+0F8h+bAlertable], eax
0x180048797  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004879e  mov     r8d, 26Fh; unsigned int
0x1800487a4  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800487ab  mov     ecx, 2; unsigned __int8
0x1800487b0  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800487b5  mov     eax, [rsp+0F8h+Reply]
0x1800487b9  cmp     eax, 800706B5h
0x1800487be  jz      short loc_1800487C7
0x1800487c0  cmp     eax, 800706BAh
0x1800487c5  jnz     short loc_1800487D0
0x1800487c7  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x1800487cc  mov     eax, [rsp+0F8h+Reply]
0x1800487d0  test    eax, eax
0x1800487d2  jns     short loc_1800487E4
0x1800487d4  mov     rcx, r15; ContextHandle
0x1800487d7  call    cs:__imp_RpcSsDestroyClientContext
0x1800487dd  mov     qword ptr [r15], 0
0x1800487e4  xor     eax, eax
0x1800487e6  mov     rcx, [rsp+0F8h+var_28]
0x1800487ee  xor     rcx, rsp; StackCookie
0x1800487f1  call    __security_check_cookie
0x1800487f6  lea     r11, [rsp+0F8h+var_18]
0x1800487fe  mov     rsi, [r11+30h]
0x180048802  mov     r12, [r11+38h]
0x180048806  mov     rsp, r11
0x180048809  pop     r15
0x18004880b  pop     r14
0x18004880d  pop     r13
0x18004880f  retn
0x1800619f5  push    rbp
0x1800619f7  sub     rsp, 30h
0x1800619fb  mov     rbp, rdx
0x1800619fe  mov     rcx, [rcx]
0x180061a01  mov     ecx, [rcx]; unsigned int
0x180061a03  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x180061a08  nop
0x180061a09  add     rsp, 30h
0x180061a0d  pop     rbp
0x180061a0e  retn
```
