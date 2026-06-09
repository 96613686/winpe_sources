# WLIDCDeleteContextEx(unsigned __int64,void * *)

- ea: `0x18000e1c0`
- end: `0x18000e4fa`
- name: `?WLIDCDeleteContextEx@@YAJ_KPEAPEAX@Z`
- size: `826`
- prototype: `__int64 __fastcall(unsigned int, void **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180007b00`
- `0x18000a3e8`

## callees

- `0x1800027f0`
- `0x1800033b4`
- `0x18000c47c`
- `0x18000dc00`
- `0x18000e1c0`
- `0x18000e85c`
- `0x18000f4cc`
- `0x18000fe90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000e361`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000e3b3`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000e361`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000e3b3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e280`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e280`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e293`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e3c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e293`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e3c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e430`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e430`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000e3e9`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000e3e9`
- `RPCRT4!RpcAsyncCancelCall` at `0x18000e385`
- `RPCRT4!RpcAsyncCancelCall` at `0x18000e385`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18000e2d4`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18000e2d4`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18000e23c`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18000e23c`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18000e4cc`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18000e4cc`

## string_xrefs

- `0x18000e2a5`: `RPC failed to create new event, hr = %#x`
- `0x18000e3fd`: `RPC Async complete call failed, hr = %#x`
- `0x18000e448`: `WLIDCDeleteContextEx`

## pseudocode

```c
__int64 __fastcall WLIDCDeleteContextEx(unsigned int a1, void **a2)
{
  DWORD v3; // esi
  char v4; // r12
  char v5; // r14
  int LastError; // eax
  const unsigned __int16 *v7; // r9
  unsigned int v8; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v10; // esi
  int v11; // eax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-E8h]
  int Reply; // [rsp+30h] [rbp-D8h] BYREF
  char v15; // [rsp+34h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+38h] [rbp-D0h] BYREF
  DWORD v17; // [rsp+3Ch] [rbp-CCh] BYREF
  void **v18; // [rsp+40h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+48h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+60h] [rbp-A8h] BYREF

  v18 = a2;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue(a1, (unsigned int)a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v3 = dwMilliseconds;
  v17 = dwMilliseconds;
  v4 = 0;
  v15 = 0;
  v5 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v8 = 621;
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
    v7 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_5;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0xDu, 0, &pAsync, 0, a2);
  v10 = WaitForMultipleObjectsEx(1u, Handles, 0, v3, 0);
  do
  {
    if ( v5 || v10 != 258 && v10 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v10 == 258 )
      v4 = 1;
    else
      v5 = 1;
    v10 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v4 );
  if ( v10 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = L"Encountered error while waiting on RPC call, hr = %#x";
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_28;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = L"RPC Async complete call failed, hr = %#x";
  }
  v8 = 623;
LABEL_27:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(
    (PPTraceStatus *)2,
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
    v8,
    v7,
    *(_QWORD *)bAlertable);
LABEL_28:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v4 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],unsigned long &>(
      (__int64)"WLIDCDeleteContextEx",
      (int *)&v17);
    bAlertable[0] = Reply;
    TracePrintW(
      (PPTraceStatus *)2,
      (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x26Fu,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v5 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      (PPTraceStatus *)2,
      (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x26Fu,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  v11 = Reply;
  if ( Reply == -2147023179 || Reply == -2147023174 )
  {
    TraceServiceStatus();
    v11 = Reply;
  }
  if ( v11 < 0 )
  {
    RpcSsDestroyClientContext(a2);
    *a2 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18000e1c0  push    rsi
0x18000e1c2  push    r12
0x18000e1c4  push    r14
0x18000e1c6  push    r15
0x18000e1c8  sub     rsp, 0E8h
0x18000e1cf  mov     rax, cs:__security_cookie
0x18000e1d6  xor     rax, rsp
0x18000e1d9  mov     [rsp+108h+var_38], rax
0x18000e1e1  mov     r15, rdx
0x18000e1e4  mov     [rsp+108h+var_C8], rdx
0x18000e1e9  mov     [rsp+108h+Reply], 0
0x18000e1f1  mov     [rsp+108h+dwMilliseconds], 0
0x18000e1f9  lea     r8, [rsp+108h+dwMilliseconds]; unsigned int *
0x18000e1fe  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18000e203  xor     edx, edx; Val
0x18000e205  lea     r8d, [rdx+70h]; Size
0x18000e209  lea     rcx, [rsp+108h+pAsync]; void *
0x18000e20e  call    memset_0
0x18000e213  mov     esi, [rsp+108h+dwMilliseconds]
0x18000e217  mov     [rsp+108h+dwMilliseconds], esi
0x18000e21b  mov     [rsp+108h+var_CC], esi
0x18000e21f  xor     r12b, r12b
0x18000e222  mov     [rsp+108h+var_D4], r12b
0x18000e227  xor     r14b, r14b
0x18000e22a  xorps   xmm0, xmm0
0x18000e22d  movups  xmmword ptr [rsp+108h+Handles], xmm0
0x18000e232  mov     edx, 70h ; 'p'; Size
0x18000e237  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18000e23c  call    cs:__imp_RpcAsyncInitializeHandle
0x18000e242  test    eax, eax
0x18000e244  jz      short loc_18000E262
0x18000e246  jle     short loc_18000E250
0x18000e248  movzx   eax, ax
0x18000e24b  or      eax, 80070000h
0x18000e250  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18000e257  mov     r8d, 26Dh
0x18000e25d  jmp     loc_18000E40A
0x18000e262  mov     [rsp+108h+pAsync.UserInfo], 0
0x18000e26b  mov     [rsp+108h+pAsync.NotificationType], 1
0x18000e276  xor     r9d, r9d; lpName
0x18000e279  xor     r8d, r8d; bInitialState
0x18000e27c  xor     edx, edx; bManualReset
0x18000e27e  xor     ecx, ecx; lpEventAttributes
0x18000e280  call    cs:__imp_CreateEventW
0x18000e286  mov     qword ptr [rsp+108h+pAsync.u], rax
0x18000e28e  test    rax, rax
0x18000e291  jnz     short loc_18000E2AE
0x18000e293  call    cs:__imp_GetLastError
0x18000e299  test    eax, eax
0x18000e29b  jle     short loc_18000E2A5
0x18000e29d  movzx   eax, ax
0x18000e2a0  or      eax, 80070000h
0x18000e2a5  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18000e2ac  jmp     short loc_18000E257
0x18000e2ae  mov     [rsp+108h+Handles], rax
0x18000e2b3  mov     [rsp+108h+var_E0], r15
0x18000e2b8  mov     qword ptr [rsp+108h+bAlertable], 0
0x18000e2c1  lea     r9, [rsp+108h+pAsync]
0x18000e2c6  xor     r8d, r8d; pReturnValue
0x18000e2c9  lea     edx, [r8+0Dh]; nProcNum
0x18000e2cd  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000e2d4  call    cs:__imp_Ndr64AsyncClientCall
0x18000e2da  mov     eax, [rsp+108h+Reply]
0x18000e2de  jmp     short loc_18000E334
0x18000e2e0  test    eax, eax
0x18000e2e2  jle     short loc_18000E2EC
0x18000e2e4  movzx   eax, ax
0x18000e2e7  or      eax, 80070000h
0x18000e2ec  mov     [rsp+108h+Reply], eax
0x18000e2f0  mov     [rsp+108h+bAlertable], eax
0x18000e2f4  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18000e2fb  mov     r8d, 26Fh; unsigned int
0x18000e301  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000e308  mov     ecx, 2; unsigned __int8
0x18000e30d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000e312  mov     eax, [rsp+108h+Reply]
0x18000e316  test    eax, eax
0x18000e318  js      short loc_18000E323
0x18000e31a  mov     eax, 8000FFFFh
0x18000e31f  mov     [rsp+108h+Reply], eax
0x18000e323  mov     esi, [rsp+108h+dwMilliseconds]
0x18000e327  mov     r12b, [rsp+108h+var_D4]
0x18000e32c  mov     r14b, r12b
0x18000e32f  mov     r15, [rsp+108h+var_C8]
0x18000e334  test    eax, eax
0x18000e336  jns     short loc_18000E34A
0x18000e338  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18000e33f  mov     r8d, 26Fh
0x18000e345  jmp     loc_18000E40E
0x18000e34a  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18000e352  mov     r9d, esi; dwMilliseconds
0x18000e355  xor     r8d, r8d; bWaitAll
0x18000e358  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18000e35d  lea     ecx, [r8+1]; nCount
0x18000e361  call    cs:__imp_WaitForMultipleObjectsEx
0x18000e367  mov     esi, eax
0x18000e369  test    r14b, r14b
0x18000e36c  jnz     short loc_18000E3C0
0x18000e36e  cmp     esi, 102h
0x18000e374  jz      short loc_18000E37B
0x18000e376  cmp     esi, 1
0x18000e379  jnz     short loc_18000E3C0
0x18000e37b  mov     edx, 1; fAbort
0x18000e380  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18000e385  call    cs:__imp_RpcAsyncCancelCall
0x18000e38b  cmp     esi, 102h
0x18000e391  jnz     short loc_18000E398
0x18000e393  mov     r12b, 1
0x18000e396  jmp     short loc_18000E39B
0x18000e398  mov     r14b, 1
0x18000e39b  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18000e3a3  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18000e3a7  xor     r8d, r8d; bWaitAll
0x18000e3aa  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18000e3af  lea     ecx, [r8+1]; nCount
0x18000e3b3  call    cs:__imp_WaitForMultipleObjectsEx
0x18000e3b9  mov     esi, eax
0x18000e3bb  test    r12b, r12b
0x18000e3be  jz      short loc_18000E369
0x18000e3c0  test    esi, esi
0x18000e3c2  jz      short loc_18000E3DF
0x18000e3c4  call    cs:__imp_GetLastError
0x18000e3ca  test    eax, eax
0x18000e3cc  jle     short loc_18000E3D6
0x18000e3ce  movzx   eax, ax
0x18000e3d1  or      eax, 80070000h
0x18000e3d6  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18000e3dd  jmp     short loc_18000E404
0x18000e3df  lea     rdx, [rsp+108h+Reply]; Reply
0x18000e3e4  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18000e3e9  call    cs:__imp_RpcAsyncCompleteCall
0x18000e3ef  test    eax, eax
0x18000e3f1  jz      short loc_18000E423
0x18000e3f3  jle     short loc_18000E3FD
0x18000e3f5  movzx   eax, ax
0x18000e3f8  or      eax, 80070000h
0x18000e3fd  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18000e404  mov     r8d, 26Fh; unsigned int
0x18000e40a  mov     [rsp+108h+Reply], eax
0x18000e40e  mov     [rsp+108h+bAlertable], eax
0x18000e412  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000e419  mov     ecx, 2; unsigned __int8
0x18000e41e  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000e423  mov     rcx, qword ptr [rsp+108h+pAsync.u]; hObject
0x18000e42b  test    rcx, rcx
0x18000e42e  jz      short loc_18000E436
0x18000e430  call    cs:__imp_CloseHandle
0x18000e436  test    r12b, r12b
0x18000e439  jz      short loc_18000E47A
0x18000e43b  mov     [rsp+108h+Reply], 800705B4h
0x18000e443  lea     rdx, [rsp+108h+var_CC]
0x18000e448  lea     rcx, aWlidcdeletecon; "WLIDCDeleteContextEx"
0x18000e44f  call    ??$RPCCallTimedOut@AEAY0BF@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BF@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],ulong &>(char const (&)[21],ulong &)
0x18000e454  mov     eax, [rsp+108h+Reply]
0x18000e458  mov     [rsp+108h+bAlertable], eax
0x18000e45c  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18000e463  mov     r8d, 26Fh; unsigned int
0x18000e469  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000e470  mov     ecx, 2; unsigned __int8
0x18000e475  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000e47a  test    r14b, r14b
0x18000e47d  jz      short loc_18000E4AA
0x18000e47f  mov     eax, 800704C7h
0x18000e484  mov     [rsp+108h+Reply], eax
0x18000e488  mov     [rsp+108h+bAlertable], eax
0x18000e48c  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18000e493  mov     r8d, 26Fh; unsigned int
0x18000e499  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000e4a0  mov     ecx, 2; unsigned __int8
0x18000e4a5  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000e4aa  mov     eax, [rsp+108h+Reply]
0x18000e4ae  cmp     eax, 800706B5h
0x18000e4b3  jz      short loc_18000E4BC
0x18000e4b5  cmp     eax, 800706BAh
0x18000e4ba  jnz     short loc_18000E4C5
0x18000e4bc  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18000e4c1  mov     eax, [rsp+108h+Reply]
0x18000e4c5  test    eax, eax
0x18000e4c7  jns     short loc_18000E4D9
0x18000e4c9  mov     rcx, r15; ContextHandle
0x18000e4cc  call    cs:__imp_RpcSsDestroyClientContext
0x18000e4d2  mov     qword ptr [r15], 0
0x18000e4d9  xor     eax, eax
0x18000e4db  mov     rcx, [rsp+108h+var_38]
0x18000e4e3  xor     rcx, rsp; StackCookie
0x18000e4e6  call    __security_check_cookie
0x18000e4eb  add     rsp, 0E8h
0x18000e4f2  pop     r15
0x18000e4f4  pop     r14
0x18000e4f6  pop     r12
0x18000e4f8  pop     rsi
0x18000e4f9  retn
0x180011342  push    rbp
0x180011344  sub     rsp, 30h
0x180011348  mov     rbp, rdx
0x18001134b  mov     rcx, [rcx]
0x18001134e  mov     ecx, [rcx]; unsigned int
0x180011350  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x180011355  nop
0x180011356  add     rsp, 30h
0x18001135a  pop     rbp
0x18001135b  retn
```
