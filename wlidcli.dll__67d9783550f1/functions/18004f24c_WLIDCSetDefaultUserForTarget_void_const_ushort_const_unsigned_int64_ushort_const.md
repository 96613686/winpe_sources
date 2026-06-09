# WLIDCSetDefaultUserForTarget(void * const,ushort const *,unsigned __int64,ushort const *)

- ea: `0x18004f24c`
- end: `0x18004f58a`
- name: `?WLIDCSetDefaultUserForTarget@@YAJQEAXPEBG_K1@Z`
- size: `830`
- prototype: `__int64 __fastcall(void *const, const unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180033720`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180045394`
- `0x180046ce0`
- `0x18004cd04`
- `0x18004f24c`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004f405`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004f457`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004f405`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004f457`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004f319`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004f319`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f32c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f32c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f468`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f4d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f4d4`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004f42c`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004f42c`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004f37d`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004f37d`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004f48d`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004f48d`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004f2d2`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004f2d2`

## string_xrefs

- `0x18004f33e`: `RPC failed to create new event, hr = %#x`
- `0x18004f4a1`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCSetDefaultUserForTarget(
        void *const a1,
        const unsigned __int16 *a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  DWORD v6; // esi
  char v7; // r15
  char v8; // r14
  int LastError; // eax
  const unsigned __int16 *v10; // r9
  unsigned int v11; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v13; // esi
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-F8h]
  unsigned int Reply; // [rsp+40h] [rbp-D8h] BYREF
  char v17; // [rsp+44h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-D0h] BYREF
  DWORD v19; // [rsp+4Ch] [rbp-CCh] BYREF
  const unsigned __int16 *v20; // [rsp+50h] [rbp-C8h]
  __int64 v21; // [rsp+58h] [rbp-C0h]
  HANDLE Handles[2]; // [rsp+60h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-A8h] BYREF

  v20 = a4;
  v21 = a3;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
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
LABEL_5:
    v11 = 1046;
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
    v10 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_5;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x30u, 0, &pAsync, a1, a2, v21, v20);
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
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_28;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC Async complete call failed, hr = %#x";
  }
  v11 = 1048;
LABEL_27:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(
    2u,
    "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
    v11,
    v10,
    *(_QWORD *)bAlertable);
LABEL_28:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v7 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[29],unsigned long &>(
      (__int64)"WLIDCSetDefaultUserForTarget",
      (int *)&v19);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x418u,
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
      0x418u,
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
0x18004f24c  push    rsi
0x18004f24e  push    r12
0x18004f250  push    r13
0x18004f252  push    r14
0x18004f254  push    r15
0x18004f256  sub     rsp, 0F0h
0x18004f25d  mov     rax, cs:__security_cookie
0x18004f264  xor     rax, rsp
0x18004f267  mov     [rsp+118h+var_38], rax
0x18004f26f  mov     [rsp+118h+var_C8], r9
0x18004f274  mov     [rsp+118h+var_C0], r8
0x18004f279  mov     r13, rdx
0x18004f27c  mov     r12, rcx
0x18004f27f  mov     [rsp+118h+Reply], 0
0x18004f287  mov     [rsp+118h+dwMilliseconds], 0
0x18004f28f  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x18004f294  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004f299  xor     edx, edx; Val
0x18004f29b  lea     r8d, [rdx+70h]; Size
0x18004f29f  lea     rcx, [rsp+118h+pAsync]; void *
0x18004f2a4  call    memset_0
0x18004f2a9  mov     esi, [rsp+118h+dwMilliseconds]
0x18004f2ad  mov     [rsp+118h+dwMilliseconds], esi
0x18004f2b1  mov     [rsp+118h+var_CC], esi
0x18004f2b5  xor     r15b, r15b
0x18004f2b8  mov     [rsp+118h+var_D4], r15b
0x18004f2bd  xor     r14b, r14b
0x18004f2c0  xorps   xmm0, xmm0
0x18004f2c3  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x18004f2c8  mov     edx, 70h ; 'p'; Size
0x18004f2cd  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004f2d2  call    cs:__imp_RpcAsyncInitializeHandle
0x18004f2d8  test    eax, eax
0x18004f2da  jz      short loc_18004F2F8
0x18004f2dc  jle     short loc_18004F2E6
0x18004f2de  movzx   eax, ax
0x18004f2e1  or      eax, 80070000h
0x18004f2e6  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004f2ed  mov     r8d, 416h
0x18004f2f3  jmp     loc_18004F4AE
0x18004f2f8  mov     [rsp+118h+pAsync.UserInfo], 0
0x18004f304  mov     [rsp+118h+pAsync.NotificationType], 1
0x18004f30f  xor     r9d, r9d; lpName
0x18004f312  xor     r8d, r8d; bInitialState
0x18004f315  xor     edx, edx; bManualReset
0x18004f317  xor     ecx, ecx; lpEventAttributes
0x18004f319  call    cs:__imp_CreateEventW
0x18004f31f  mov     qword ptr [rsp+118h+pAsync.u], rax
0x18004f327  test    rax, rax
0x18004f32a  jnz     short loc_18004F347
0x18004f32c  call    cs:__imp_GetLastError
0x18004f332  test    eax, eax
0x18004f334  jle     short loc_18004F33E
0x18004f336  movzx   eax, ax
0x18004f339  or      eax, 80070000h
0x18004f33e  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004f345  jmp     short loc_18004F2ED
0x18004f347  mov     [rsp+118h+Handles], rax
0x18004f34c  mov     rax, [rsp+118h+var_C8]
0x18004f351  mov     [rsp+118h+var_E0], rax
0x18004f356  mov     rax, [rsp+118h+var_C0]
0x18004f35b  mov     [rsp+118h+var_E8], rax
0x18004f360  mov     [rsp+118h+var_F0], r13
0x18004f365  mov     qword ptr [rsp+118h+bAlertable], r12
0x18004f36a  lea     r9, [rsp+118h+pAsync]
0x18004f36f  xor     r8d, r8d; pReturnValue
0x18004f372  lea     edx, [r8+30h]; nProcNum
0x18004f376  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004f37d  call    cs:__imp_Ndr64AsyncClientCall
0x18004f383  mov     eax, [rsp+118h+Reply]
0x18004f387  jmp     short loc_18004F3D8
0x18004f389  test    eax, eax
0x18004f38b  jle     short loc_18004F395
0x18004f38d  movzx   eax, ax
0x18004f390  or      eax, 80070000h
0x18004f395  mov     [rsp+118h+Reply], eax
0x18004f399  mov     [rsp+118h+bAlertable], eax
0x18004f39d  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004f3a4  mov     r8d, 418h; unsigned int
0x18004f3aa  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004f3b1  mov     ecx, 2; unsigned __int8
0x18004f3b6  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004f3bb  mov     eax, [rsp+118h+Reply]
0x18004f3bf  test    eax, eax
0x18004f3c1  js      short loc_18004F3CC
0x18004f3c3  mov     eax, 8000FFFFh
0x18004f3c8  mov     [rsp+118h+Reply], eax
0x18004f3cc  mov     esi, [rsp+118h+dwMilliseconds]
0x18004f3d0  mov     r15b, [rsp+118h+var_D4]
0x18004f3d5  mov     r14b, r15b
0x18004f3d8  test    eax, eax
0x18004f3da  jns     short loc_18004F3EE
0x18004f3dc  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004f3e3  mov     r8d, 418h
0x18004f3e9  jmp     loc_18004F4B2
0x18004f3ee  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004f3f6  mov     r9d, esi; dwMilliseconds
0x18004f3f9  xor     r8d, r8d; bWaitAll
0x18004f3fc  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004f401  lea     ecx, [r8+1]; nCount
0x18004f405  call    cs:__imp_WaitForMultipleObjectsEx
0x18004f40b  mov     esi, eax
0x18004f40d  mov     r12d, 102h
0x18004f413  test    r14b, r14b
0x18004f416  jnz     short loc_18004F464
0x18004f418  cmp     esi, r12d
0x18004f41b  jz      short loc_18004F422
0x18004f41d  cmp     esi, 1
0x18004f420  jnz     short loc_18004F464
0x18004f422  mov     edx, 1; fAbort
0x18004f427  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004f42c  call    cs:__imp_RpcAsyncCancelCall
0x18004f432  cmp     esi, r12d
0x18004f435  jnz     short loc_18004F43C
0x18004f437  mov     r15b, 1
0x18004f43a  jmp     short loc_18004F43F
0x18004f43c  mov     r14b, 1
0x18004f43f  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004f447  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004f44b  xor     r8d, r8d; bWaitAll
0x18004f44e  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004f453  lea     ecx, [r8+1]; nCount
0x18004f457  call    cs:__imp_WaitForMultipleObjectsEx
0x18004f45d  mov     esi, eax
0x18004f45f  test    r15b, r15b
0x18004f462  jz      short loc_18004F413
0x18004f464  test    esi, esi
0x18004f466  jz      short loc_18004F483
0x18004f468  call    cs:__imp_GetLastError
0x18004f46e  test    eax, eax
0x18004f470  jle     short loc_18004F47A
0x18004f472  movzx   eax, ax
0x18004f475  or      eax, 80070000h
0x18004f47a  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004f481  jmp     short loc_18004F4A8
0x18004f483  lea     rdx, [rsp+118h+Reply]; Reply
0x18004f488  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004f48d  call    cs:__imp_RpcAsyncCompleteCall
0x18004f493  test    eax, eax
0x18004f495  jz      short loc_18004F4C7
0x18004f497  jle     short loc_18004F4A1
0x18004f499  movzx   eax, ax
0x18004f49c  or      eax, 80070000h
0x18004f4a1  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004f4a8  mov     r8d, 418h; unsigned int
0x18004f4ae  mov     [rsp+118h+Reply], eax
0x18004f4b2  mov     [rsp+118h+bAlertable], eax
0x18004f4b6  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004f4bd  mov     ecx, 2; unsigned __int8
0x18004f4c2  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004f4c7  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x18004f4cf  test    rcx, rcx
0x18004f4d2  jz      short loc_18004F4DA
0x18004f4d4  call    cs:__imp_CloseHandle
0x18004f4da  test    r15b, r15b
0x18004f4dd  jz      short loc_18004F51E
0x18004f4df  mov     [rsp+118h+Reply], 800705B4h
0x18004f4e7  lea     rdx, [rsp+118h+var_CC]
0x18004f4ec  lea     rcx, aWlidcsetdefaul; "WLIDCSetDefaultUserForTarget"
0x18004f4f3  call    ??$RPCCallTimedOut@AEAY0BN@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BN@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[29],ulong &>(char const (&)[29],ulong &)
0x18004f4f8  mov     eax, [rsp+118h+Reply]
0x18004f4fc  mov     [rsp+118h+bAlertable], eax
0x18004f500  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004f507  mov     r8d, 418h; unsigned int
0x18004f50d  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004f514  mov     ecx, 2; unsigned __int8
0x18004f519  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004f51e  test    r14b, r14b
0x18004f521  jz      short loc_18004F54E
0x18004f523  mov     eax, 800704C7h
0x18004f528  mov     [rsp+118h+Reply], eax
0x18004f52c  mov     [rsp+118h+bAlertable], eax
0x18004f530  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004f537  mov     r8d, 418h; unsigned int
0x18004f53d  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004f544  mov     ecx, 2; unsigned __int8
0x18004f549  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004f54e  mov     eax, [rsp+118h+Reply]
0x18004f552  cmp     eax, 800706B5h
0x18004f557  jz      short loc_18004F560
0x18004f559  cmp     eax, 800706BAh
0x18004f55e  jnz     short loc_18004F569
0x18004f560  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004f565  mov     eax, [rsp+118h+Reply]
0x18004f569  mov     rcx, [rsp+118h+var_38]
0x18004f571  xor     rcx, rsp; StackCookie
0x18004f574  call    __security_check_cookie
0x18004f579  add     rsp, 0F0h
0x18004f580  pop     r15
0x18004f582  pop     r14
0x18004f584  pop     r13
0x18004f586  pop     r12
0x18004f588  pop     rsi
0x18004f589  retn
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
