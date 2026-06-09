# WLIDCSetOptions(ulong,__MIDL_liveidsvc_0001 *,unsigned __int64)

- ea: `0x18004f8d4`
- end: `0x18004fc31`
- name: `?WLIDCSetOptions@@YAJKPEAU__MIDL_liveidsvc_0001@@_K@Z`
- size: `861`
- prototype: `__int64 __fastcall(unsigned int, struct __MIDL_liveidsvc_0001 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180033c80`
- `0x180034730`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180044d0c`
- `0x180046ce0`
- `0x18004cd04`
- `0x18004f8d4`
- `0x180050c84`
- `0x180050e40`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004faa7`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004faf9`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004faa7`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004faf9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004f9bb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004f9bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f9ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fb0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f9ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fb0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fb76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fb76`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004face`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004face`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004fa1f`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004fa1f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004fb2f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004fb2f`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004f974`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004f974`

## string_xrefs

- `0x18004f9e0`: `RPC failed to create new event, hr = %#x`
- `0x18004fb43`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCSetOptions(unsigned int a1, struct __MIDL_liveidsvc_0001 *a2, __int64 a3)
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
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  BOOL bAlertable[2]; // [rsp+20h] [rbp-F8h]
  int Reply; // [rsp+40h] [rbp-D8h] BYREF
  char v17; // [rsp+44h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-D0h] BYREF
  DWORD v19; // [rsp+4Ch] [rbp-CCh] BYREF
  __int64 v20; // [rsp+50h] [rbp-C8h] BYREF
  __int64 v21; // [rsp+58h] [rbp-C0h]
  HANDLE Handles[2]; // [rsp+60h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-A8h] BYREF

  v21 = a3;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue(a1, (unsigned int)a2, &dwMilliseconds);
  v20 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v20);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v6 = dwMilliseconds;
  v19 = dwMilliseconds;
  v7 = 0;
  v17 = 0;
  v8 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v11 = 798;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x18u, 0, &pAsync, v20, a1, a2, v21);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v10 = L"RPC call failed, hr = %#x";
    v11 = 800;
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
    v11 = 800;
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
  NotificationRoutine = pAsync.u.APC.NotificationRoutine;
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v7 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[16],unsigned long &>(
      (__int64)NotificationRoutine,
      (int *)&v19);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x320u,
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
      0x320u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v20);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x18004f8d4  push    rsi
0x18004f8d6  push    r12
0x18004f8d8  push    r13
0x18004f8da  push    r14
0x18004f8dc  push    r15
0x18004f8de  sub     rsp, 0F0h
0x18004f8e5  mov     rax, cs:__security_cookie
0x18004f8ec  xor     rax, rsp
0x18004f8ef  mov     [rsp+118h+var_38], rax
0x18004f8f7  mov     [rsp+118h+var_C0], r8
0x18004f8fc  mov     r13, rdx
0x18004f8ff  mov     r12d, ecx
0x18004f902  mov     [rsp+118h+dwMilliseconds], 0
0x18004f90a  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x18004f90f  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004f914  mov     [rsp+118h+Reply], 0
0x18004f91c  mov     [rsp+118h+var_C8], 0
0x18004f925  lea     rcx, [rsp+118h+var_C8]; this
0x18004f92a  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18004f92f  mov     [rsp+118h+Reply], eax
0x18004f933  test    eax, eax
0x18004f935  js      loc_18004FC10
0x18004f93b  xor     edx, edx; Val
0x18004f93d  lea     r8d, [rdx+70h]; Size
0x18004f941  lea     rcx, [rsp+118h+pAsync]; void *
0x18004f946  call    memset_0
0x18004f94b  mov     esi, [rsp+118h+dwMilliseconds]
0x18004f94f  mov     [rsp+118h+dwMilliseconds], esi
0x18004f953  mov     [rsp+118h+var_CC], esi
0x18004f957  xor     r15b, r15b
0x18004f95a  mov     [rsp+118h+var_D4], r15b
0x18004f95f  xor     r14b, r14b
0x18004f962  xorps   xmm0, xmm0
0x18004f965  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x18004f96a  mov     edx, 70h ; 'p'; Size
0x18004f96f  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004f974  call    cs:__imp_RpcAsyncInitializeHandle
0x18004f97a  test    eax, eax
0x18004f97c  jz      short loc_18004F99A
0x18004f97e  jle     short loc_18004F988
0x18004f980  movzx   eax, ax
0x18004f983  or      eax, 80070000h
0x18004f988  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004f98f  mov     r8d, 31Eh
0x18004f995  jmp     loc_18004FB50
0x18004f99a  mov     [rsp+118h+pAsync.UserInfo], 0
0x18004f9a6  mov     [rsp+118h+pAsync.NotificationType], 1
0x18004f9b1  xor     r9d, r9d; lpName
0x18004f9b4  xor     r8d, r8d; bInitialState
0x18004f9b7  xor     edx, edx; bManualReset
0x18004f9b9  xor     ecx, ecx; lpEventAttributes
0x18004f9bb  call    cs:__imp_CreateEventW
0x18004f9c1  mov     qword ptr [rsp+118h+pAsync.u], rax
0x18004f9c9  test    rax, rax
0x18004f9cc  jnz     short loc_18004F9E9
0x18004f9ce  call    cs:__imp_GetLastError
0x18004f9d4  test    eax, eax
0x18004f9d6  jle     short loc_18004F9E0
0x18004f9d8  movzx   eax, ax
0x18004f9db  or      eax, 80070000h
0x18004f9e0  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004f9e7  jmp     short loc_18004F98F
0x18004f9e9  mov     [rsp+118h+Handles], rax
0x18004f9ee  mov     rax, [rsp+118h+var_C0]
0x18004f9f3  mov     [rsp+118h+var_E0], rax
0x18004f9f8  mov     [rsp+118h+var_E8], r13
0x18004f9fd  mov     [rsp+118h+var_F0], r12d
0x18004fa02  mov     rax, [rsp+118h+var_C8]
0x18004fa07  mov     qword ptr [rsp+118h+bAlertable], rax
0x18004fa0c  lea     r9, [rsp+118h+pAsync]
0x18004fa11  xor     r8d, r8d; pReturnValue
0x18004fa14  lea     edx, [r8+18h]; nProcNum
0x18004fa18  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004fa1f  call    cs:__imp_Ndr64AsyncClientCall
0x18004fa25  mov     eax, [rsp+118h+Reply]
0x18004fa29  jmp     short loc_18004FA7A
0x18004fa2b  test    eax, eax
0x18004fa2d  jle     short loc_18004FA37
0x18004fa2f  movzx   eax, ax
0x18004fa32  or      eax, 80070000h
0x18004fa37  mov     [rsp+118h+Reply], eax
0x18004fa3b  mov     [rsp+118h+bAlertable], eax
0x18004fa3f  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004fa46  mov     r8d, 320h; unsigned int
0x18004fa4c  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004fa53  mov     ecx, 2; unsigned __int8
0x18004fa58  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004fa5d  mov     eax, [rsp+118h+Reply]
0x18004fa61  test    eax, eax
0x18004fa63  js      short loc_18004FA6E
0x18004fa65  mov     eax, 8000FFFFh
0x18004fa6a  mov     [rsp+118h+Reply], eax
0x18004fa6e  mov     esi, [rsp+118h+dwMilliseconds]
0x18004fa72  mov     r15b, [rsp+118h+var_D4]
0x18004fa77  mov     r14b, r15b
0x18004fa7a  test    eax, eax
0x18004fa7c  jns     short loc_18004FA90
0x18004fa7e  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004fa85  mov     r8d, 320h
0x18004fa8b  jmp     loc_18004FB54
0x18004fa90  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004fa98  mov     r9d, esi; dwMilliseconds
0x18004fa9b  xor     r8d, r8d; bWaitAll
0x18004fa9e  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004faa3  lea     ecx, [r8+1]; nCount
0x18004faa7  call    cs:__imp_WaitForMultipleObjectsEx
0x18004faad  mov     esi, eax
0x18004faaf  mov     r12d, 102h
0x18004fab5  test    r14b, r14b
0x18004fab8  jnz     short loc_18004FB06
0x18004faba  cmp     esi, r12d
0x18004fabd  jz      short loc_18004FAC4
0x18004fabf  cmp     esi, 1
0x18004fac2  jnz     short loc_18004FB06
0x18004fac4  mov     edx, 1; fAbort
0x18004fac9  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004face  call    cs:__imp_RpcAsyncCancelCall
0x18004fad4  cmp     esi, r12d
0x18004fad7  jnz     short loc_18004FADE
0x18004fad9  mov     r15b, 1
0x18004fadc  jmp     short loc_18004FAE1
0x18004fade  mov     r14b, 1
0x18004fae1  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004fae9  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004faed  xor     r8d, r8d; bWaitAll
0x18004faf0  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004faf5  lea     ecx, [r8+1]; nCount
0x18004faf9  call    cs:__imp_WaitForMultipleObjectsEx
0x18004faff  mov     esi, eax
0x18004fb01  test    r15b, r15b
0x18004fb04  jz      short loc_18004FAB5
0x18004fb06  test    esi, esi
0x18004fb08  jz      short loc_18004FB25
0x18004fb0a  call    cs:__imp_GetLastError
0x18004fb10  test    eax, eax
0x18004fb12  jle     short loc_18004FB1C
0x18004fb14  movzx   eax, ax
0x18004fb17  or      eax, 80070000h
0x18004fb1c  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004fb23  jmp     short loc_18004FB4A
0x18004fb25  lea     rdx, [rsp+118h+Reply]; Reply
0x18004fb2a  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004fb2f  call    cs:__imp_RpcAsyncCompleteCall
0x18004fb35  test    eax, eax
0x18004fb37  jz      short loc_18004FB69
0x18004fb39  jle     short loc_18004FB43
0x18004fb3b  movzx   eax, ax
0x18004fb3e  or      eax, 80070000h
0x18004fb43  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004fb4a  mov     r8d, 320h; unsigned int
0x18004fb50  mov     [rsp+118h+Reply], eax
0x18004fb54  mov     [rsp+118h+bAlertable], eax
0x18004fb58  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004fb5f  mov     ecx, 2; unsigned __int8
0x18004fb64  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004fb69  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x18004fb71  test    rcx, rcx
0x18004fb74  jz      short loc_18004FB7C
0x18004fb76  call    cs:__imp_CloseHandle
0x18004fb7c  test    r15b, r15b
0x18004fb7f  jz      short loc_18004FBB9
0x18004fb81  mov     [rsp+118h+Reply], 800705B4h
0x18004fb89  lea     rdx, [rsp+118h+var_CC]
0x18004fb8e  call    ??$RPCCallTimedOut@AEAY0BA@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BA@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[16],ulong &>(char const (&)[16],ulong &)
0x18004fb93  mov     eax, [rsp+118h+Reply]
0x18004fb97  mov     [rsp+118h+bAlertable], eax
0x18004fb9b  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004fba2  mov     r8d, 320h; unsigned int
0x18004fba8  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004fbaf  mov     ecx, 2; unsigned __int8
0x18004fbb4  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004fbb9  test    r14b, r14b
0x18004fbbc  jz      short loc_18004FBE9
0x18004fbbe  mov     eax, 800704C7h
0x18004fbc3  mov     [rsp+118h+Reply], eax
0x18004fbc7  mov     [rsp+118h+bAlertable], eax
0x18004fbcb  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004fbd2  mov     r8d, 320h; unsigned int
0x18004fbd8  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004fbdf  mov     ecx, 2; unsigned __int8
0x18004fbe4  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004fbe9  cmp     [rsp+118h+Reply], 800706B5h
0x18004fbf1  jz      short loc_18004FBFD
0x18004fbf3  cmp     [rsp+118h+Reply], 800706BAh
0x18004fbfb  jnz     short loc_18004FC02
0x18004fbfd  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004fc02  lea     rcx, [rsp+118h+var_C8]; this
0x18004fc07  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18004fc0c  mov     eax, [rsp+118h+Reply]
0x18004fc10  mov     rcx, [rsp+118h+var_38]
0x18004fc18  xor     rcx, rsp; StackCookie
0x18004fc1b  call    __security_check_cookie
0x18004fc20  add     rsp, 0F0h
0x18004fc27  pop     r15
0x18004fc29  pop     r14
0x18004fc2b  pop     r13
0x18004fc2d  pop     r12
0x18004fc2f  pop     rsi
0x18004fc30  retn
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
