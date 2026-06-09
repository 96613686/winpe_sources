# WLIDCInitializeEx(ushort const *,_WLIDInitialSettings * *)

- ea: `0x18004d78c`
- end: `0x18004daf0`
- name: `?WLIDCInitializeEx@@YAJPEBGPEAPEAU_WLIDInitialSettings@@@Z`
- size: `868`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _WLIDInitialSettings **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180031560`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180044e20`
- `0x180046ce0`
- `0x18004cd04`
- `0x18004d78c`
- `0x180050c84`
- `0x180050e40`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004d956`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004d9a8`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004d956`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004d9a8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004d874`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004d874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d887`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d9b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d887`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d9b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004da25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004da25`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004d97d`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004d97d`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004d8ce`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004d8ce`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004d9de`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004d9de`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004d82d`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004d82d`

## string_xrefs

- `0x18004d899`: `RPC failed to create new event, hr = %#x`
- `0x18004d9f2`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCInitializeEx(const unsigned __int16 *a1, struct _WLIDInitialSettings **a2)
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
    v10 = 562;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x38u, 0, &pAsync, v18, a1, a2);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v9 = L"RPC call failed, hr = %#x";
    v10 = 564;
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
    v10 = 564;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[18],unsigned long &>(
      (__int64)"WLIDCInitializeEx",
      (int *)&v17);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x234u,
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
      0x234u,
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
0x18004d78c  mov     [rsp+arg_10], rsi
0x18004d791  mov     [rsp+arg_18], r12
0x18004d796  push    r13
0x18004d798  push    r14
0x18004d79a  push    r15
0x18004d79c  sub     rsp, 0F0h
0x18004d7a3  mov     rax, cs:__security_cookie
0x18004d7aa  xor     rax, rsp
0x18004d7ad  mov     [rsp+108h+var_28], rax
0x18004d7b5  mov     r13, rdx
0x18004d7b8  mov     r12, rcx
0x18004d7bb  mov     [rsp+108h+dwMilliseconds], 0
0x18004d7c3  lea     r8, [rsp+108h+dwMilliseconds]; unsigned int *
0x18004d7c8  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004d7cd  mov     [rsp+108h+Reply], 0
0x18004d7d5  mov     [rsp+108h+var_B8], 0
0x18004d7de  lea     rcx, [rsp+108h+var_B8]; this
0x18004d7e3  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18004d7e8  mov     [rsp+108h+Reply], eax
0x18004d7ec  test    eax, eax
0x18004d7ee  js      loc_18004DAC6
0x18004d7f4  xor     edx, edx; Val
0x18004d7f6  lea     r8d, [rdx+70h]; Size
0x18004d7fa  lea     rcx, [rsp+108h+pAsync]; void *
0x18004d7ff  call    memset_0
0x18004d804  mov     esi, [rsp+108h+dwMilliseconds]
0x18004d808  mov     [rsp+108h+dwMilliseconds], esi
0x18004d80c  mov     [rsp+108h+var_BC], esi
0x18004d810  xor     r15b, r15b
0x18004d813  mov     [rsp+108h+var_C4], r15b
0x18004d818  xor     r14b, r14b
0x18004d81b  xorps   xmm0, xmm0
0x18004d81e  movups  xmmword ptr [rsp+108h+Handles], xmm0
0x18004d823  mov     edx, 70h ; 'p'; Size
0x18004d828  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004d82d  call    cs:__imp_RpcAsyncInitializeHandle
0x18004d833  test    eax, eax
0x18004d835  jz      short loc_18004D853
0x18004d837  jle     short loc_18004D841
0x18004d839  movzx   eax, ax
0x18004d83c  or      eax, 80070000h
0x18004d841  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004d848  mov     r8d, 232h
0x18004d84e  jmp     loc_18004D9FF
0x18004d853  mov     [rsp+108h+pAsync.UserInfo], 0
0x18004d85f  mov     [rsp+108h+pAsync.NotificationType], 1
0x18004d86a  xor     r9d, r9d; lpName
0x18004d86d  xor     r8d, r8d; bInitialState
0x18004d870  xor     edx, edx; bManualReset
0x18004d872  xor     ecx, ecx; lpEventAttributes
0x18004d874  call    cs:__imp_CreateEventW
0x18004d87a  mov     qword ptr [rsp+108h+pAsync.u], rax
0x18004d882  test    rax, rax
0x18004d885  jnz     short loc_18004D8A2
0x18004d887  call    cs:__imp_GetLastError
0x18004d88d  test    eax, eax
0x18004d88f  jle     short loc_18004D899
0x18004d891  movzx   eax, ax
0x18004d894  or      eax, 80070000h
0x18004d899  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004d8a0  jmp     short loc_18004D848
0x18004d8a2  mov     [rsp+108h+Handles], rax
0x18004d8a7  mov     [rsp+108h+var_D8], r13
0x18004d8ac  mov     [rsp+108h+var_E0], r12
0x18004d8b1  mov     rax, [rsp+108h+var_B8]
0x18004d8b6  mov     qword ptr [rsp+108h+bAlertable], rax
0x18004d8bb  lea     r9, [rsp+108h+pAsync]
0x18004d8c0  xor     r8d, r8d; pReturnValue
0x18004d8c3  lea     edx, [r8+38h]; nProcNum
0x18004d8c7  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004d8ce  call    cs:__imp_Ndr64AsyncClientCall
0x18004d8d4  mov     eax, [rsp+108h+Reply]
0x18004d8d8  jmp     short loc_18004D929
0x18004d8da  test    eax, eax
0x18004d8dc  jle     short loc_18004D8E6
0x18004d8de  movzx   eax, ax
0x18004d8e1  or      eax, 80070000h
0x18004d8e6  mov     [rsp+108h+Reply], eax
0x18004d8ea  mov     [rsp+108h+bAlertable], eax
0x18004d8ee  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004d8f5  mov     r8d, 234h; unsigned int
0x18004d8fb  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004d902  mov     ecx, 2; unsigned __int8
0x18004d907  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004d90c  mov     eax, [rsp+108h+Reply]
0x18004d910  test    eax, eax
0x18004d912  js      short loc_18004D91D
0x18004d914  mov     eax, 8000FFFFh
0x18004d919  mov     [rsp+108h+Reply], eax
0x18004d91d  mov     esi, [rsp+108h+dwMilliseconds]
0x18004d921  mov     r15b, [rsp+108h+var_C4]
0x18004d926  mov     r14b, r15b
0x18004d929  test    eax, eax
0x18004d92b  jns     short loc_18004D93F
0x18004d92d  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004d934  mov     r8d, 234h
0x18004d93a  jmp     loc_18004DA03
0x18004d93f  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18004d947  mov     r9d, esi; dwMilliseconds
0x18004d94a  xor     r8d, r8d; bWaitAll
0x18004d94d  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18004d952  lea     ecx, [r8+1]; nCount
0x18004d956  call    cs:__imp_WaitForMultipleObjectsEx
0x18004d95c  mov     esi, eax
0x18004d95e  mov     r12d, 102h
0x18004d964  test    r14b, r14b
0x18004d967  jnz     short loc_18004D9B5
0x18004d969  cmp     esi, r12d
0x18004d96c  jz      short loc_18004D973
0x18004d96e  cmp     esi, 1
0x18004d971  jnz     short loc_18004D9B5
0x18004d973  mov     edx, 1; fAbort
0x18004d978  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004d97d  call    cs:__imp_RpcAsyncCancelCall
0x18004d983  cmp     esi, r12d
0x18004d986  jnz     short loc_18004D98D
0x18004d988  mov     r15b, 1
0x18004d98b  jmp     short loc_18004D990
0x18004d98d  mov     r14b, 1
0x18004d990  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18004d998  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004d99c  xor     r8d, r8d; bWaitAll
0x18004d99f  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18004d9a4  lea     ecx, [r8+1]; nCount
0x18004d9a8  call    cs:__imp_WaitForMultipleObjectsEx
0x18004d9ae  mov     esi, eax
0x18004d9b0  test    r15b, r15b
0x18004d9b3  jz      short loc_18004D964
0x18004d9b5  test    esi, esi
0x18004d9b7  jz      short loc_18004D9D4
0x18004d9b9  call    cs:__imp_GetLastError
0x18004d9bf  test    eax, eax
0x18004d9c1  jle     short loc_18004D9CB
0x18004d9c3  movzx   eax, ax
0x18004d9c6  or      eax, 80070000h
0x18004d9cb  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004d9d2  jmp     short loc_18004D9F9
0x18004d9d4  lea     rdx, [rsp+108h+Reply]; Reply
0x18004d9d9  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004d9de  call    cs:__imp_RpcAsyncCompleteCall
0x18004d9e4  test    eax, eax
0x18004d9e6  jz      short loc_18004DA18
0x18004d9e8  jle     short loc_18004D9F2
0x18004d9ea  movzx   eax, ax
0x18004d9ed  or      eax, 80070000h
0x18004d9f2  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004d9f9  mov     r8d, 234h; unsigned int
0x18004d9ff  mov     [rsp+108h+Reply], eax
0x18004da03  mov     [rsp+108h+bAlertable], eax
0x18004da07  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004da0e  mov     ecx, 2; unsigned __int8
0x18004da13  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004da18  mov     rcx, qword ptr [rsp+108h+pAsync.u]; hObject
0x18004da20  test    rcx, rcx
0x18004da23  jz      short loc_18004DA2B
0x18004da25  call    cs:__imp_CloseHandle
0x18004da2b  test    r15b, r15b
0x18004da2e  jz      short loc_18004DA6F
0x18004da30  mov     [rsp+108h+Reply], 800705B4h
0x18004da38  lea     rdx, [rsp+108h+var_BC]
0x18004da3d  lea     rcx, aWlidcinitializ; "WLIDCInitializeEx"
0x18004da44  call    ??$RPCCallTimedOut@AEAY0BC@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BC@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[18],ulong &>(char const (&)[18],ulong &)
0x18004da49  mov     eax, [rsp+108h+Reply]
0x18004da4d  mov     [rsp+108h+bAlertable], eax
0x18004da51  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004da58  mov     r8d, 234h; unsigned int
0x18004da5e  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004da65  mov     ecx, 2; unsigned __int8
0x18004da6a  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004da6f  test    r14b, r14b
0x18004da72  jz      short loc_18004DA9F
0x18004da74  mov     eax, 800704C7h
0x18004da79  mov     [rsp+108h+Reply], eax
0x18004da7d  mov     [rsp+108h+bAlertable], eax
0x18004da81  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004da88  mov     r8d, 234h; unsigned int
0x18004da8e  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004da95  mov     ecx, 2; unsigned __int8
0x18004da9a  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004da9f  cmp     [rsp+108h+Reply], 800706B5h
0x18004daa7  jz      short loc_18004DAB3
0x18004daa9  cmp     [rsp+108h+Reply], 800706BAh
0x18004dab1  jnz     short loc_18004DAB8
0x18004dab3  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004dab8  lea     rcx, [rsp+108h+var_B8]; this
0x18004dabd  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18004dac2  mov     eax, [rsp+108h+Reply]
0x18004dac6  mov     rcx, [rsp+108h+var_28]
0x18004dace  xor     rcx, rsp; StackCookie
0x18004dad1  call    __security_check_cookie
0x18004dad6  lea     r11, [rsp+108h+var_18]
0x18004dade  mov     rsi, [r11+30h]
0x18004dae2  mov     r12, [r11+38h]
0x18004dae6  mov     rsp, r11
0x18004dae9  pop     r15
0x18004daeb  pop     r14
0x18004daed  pop     r13
0x18004daef  retn
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
