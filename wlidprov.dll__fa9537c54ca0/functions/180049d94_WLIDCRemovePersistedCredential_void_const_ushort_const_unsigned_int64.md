# WLIDCRemovePersistedCredential(void * const,ushort const *,unsigned __int64)

- ea: `0x180049d94`
- end: `0x18004a0bc`
- name: `?WLIDCRemovePersistedCredential@@YAJQEAXPEBG_K@Z`
- size: `808`
- prototype: `__int64 __fastcall(void *const, const unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800238ec`
- `0x1800418e0`

## callees

- `0x18000a400`
- `0x180010c68`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180042160`
- `0x180043240`
- `0x180049d94`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180049e5c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180049e5c`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180049f3e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180049f90`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180049f3e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180049f90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049e6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049fa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049e6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049fa1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a00d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a00d`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180049e15`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180049e15`
- `RPCRT4!RpcAsyncCancelCall` at `0x180049f65`
- `RPCRT4!RpcAsyncCancelCall` at `0x180049f65`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180049eb6`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180049eb6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180049fc6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180049fc6`

## string_xrefs

- `0x180049e81`: `RPC failed to create new event, hr = %#x`
- `0x180049fda`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCRemovePersistedCredential(void *const a1, const unsigned __int16 *a2, __int64 a3)
{
  DWORD v5; // esi
  char v6; // r15
  char v7; // r14
  int LastError; // eax
  const unsigned __int16 *v9; // r9
  unsigned int v10; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v12; // esi
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-F8h]
  unsigned int Reply; // [rsp+40h] [rbp-D8h] BYREF
  char v17; // [rsp+44h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-D0h] BYREF
  DWORD v19; // [rsp+4Ch] [rbp-CCh] BYREF
  __int64 v20; // [rsp+50h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+58h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-A8h] BYREF

  v20 = a3;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v5 = dwMilliseconds;
  v19 = dwMilliseconds;
  v6 = 0;
  v17 = 0;
  v7 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v10 = 856;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x1Cu, 0, &pAsync, a1, a2, v20);
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
  v10 = 858;
LABEL_27:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(2u, "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp", v10, v9, *(_QWORD *)bAlertable);
LABEL_28:
  NotificationRoutine = pAsync.u.APC.NotificationRoutine;
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v6 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[31],unsigned long &>(NotificationRoutine, &v19);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x35Au,
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
      0x35Au,
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
0x180049d94  push    rsi
0x180049d96  push    r12
0x180049d98  push    r13
0x180049d9a  push    r14
0x180049d9c  push    r15
0x180049d9e  sub     rsp, 0F0h
0x180049da5  mov     rax, cs:__security_cookie
0x180049dac  xor     rax, rsp
0x180049daf  mov     [rsp+118h+var_38], rax
0x180049db7  mov     [rsp+118h+var_C8], r8
0x180049dbc  mov     r13, rdx
0x180049dbf  mov     r12, rcx
0x180049dc2  mov     [rsp+118h+Reply], 0
0x180049dca  mov     [rsp+118h+dwMilliseconds], 0
0x180049dd2  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x180049dd7  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180049ddc  xor     edx, edx; Val
0x180049dde  lea     r8d, [rdx+70h]; Size
0x180049de2  lea     rcx, [rsp+118h+pAsync]; void *
0x180049de7  call    memset_0
0x180049dec  mov     esi, [rsp+118h+dwMilliseconds]
0x180049df0  mov     [rsp+118h+dwMilliseconds], esi
0x180049df4  mov     [rsp+118h+var_CC], esi
0x180049df8  xor     r15b, r15b
0x180049dfb  mov     [rsp+118h+var_D4], r15b
0x180049e00  xor     r14b, r14b
0x180049e03  xorps   xmm0, xmm0
0x180049e06  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x180049e0b  mov     edx, 70h ; 'p'; Size
0x180049e10  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180049e15  call    cs:__imp_RpcAsyncInitializeHandle
0x180049e1b  test    eax, eax
0x180049e1d  jz      short loc_180049E3B
0x180049e1f  jle     short loc_180049E29
0x180049e21  movzx   eax, ax
0x180049e24  or      eax, 80070000h
0x180049e29  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180049e30  mov     r8d, 358h
0x180049e36  jmp     loc_180049FE7
0x180049e3b  mov     [rsp+118h+pAsync.UserInfo], 0
0x180049e47  mov     [rsp+118h+pAsync.NotificationType], 1
0x180049e52  xor     r9d, r9d; lpName
0x180049e55  xor     r8d, r8d; bInitialState
0x180049e58  xor     edx, edx; bManualReset
0x180049e5a  xor     ecx, ecx; lpEventAttributes
0x180049e5c  call    cs:__imp_CreateEventW
0x180049e62  mov     qword ptr [rsp+118h+pAsync.u], rax
0x180049e6a  test    rax, rax
0x180049e6d  jnz     short loc_180049E8A
0x180049e6f  call    cs:__imp_GetLastError
0x180049e75  test    eax, eax
0x180049e77  jle     short loc_180049E81
0x180049e79  movzx   eax, ax
0x180049e7c  or      eax, 80070000h
0x180049e81  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180049e88  jmp     short loc_180049E30
0x180049e8a  mov     [rsp+118h+Handles], rax
0x180049e8f  mov     rax, [rsp+118h+var_C8]
0x180049e94  mov     [rsp+118h+var_E8], rax
0x180049e99  mov     [rsp+118h+var_F0], r13
0x180049e9e  mov     qword ptr [rsp+118h+bAlertable], r12
0x180049ea3  lea     r9, [rsp+118h+pAsync]
0x180049ea8  xor     r8d, r8d; pReturnValue
0x180049eab  lea     edx, [r8+1Ch]; nProcNum
0x180049eaf  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180049eb6  call    cs:__imp_Ndr64AsyncClientCall
0x180049ebc  mov     eax, [rsp+118h+Reply]
0x180049ec0  jmp     short loc_180049F11
0x180049ec2  test    eax, eax
0x180049ec4  jle     short loc_180049ECE
0x180049ec6  movzx   eax, ax
0x180049ec9  or      eax, 80070000h
0x180049ece  mov     [rsp+118h+Reply], eax
0x180049ed2  mov     [rsp+118h+bAlertable], eax
0x180049ed6  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180049edd  mov     r8d, 35Ah; unsigned int
0x180049ee3  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180049eea  mov     ecx, 2; unsigned __int8
0x180049eef  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180049ef4  mov     eax, [rsp+118h+Reply]
0x180049ef8  test    eax, eax
0x180049efa  js      short loc_180049F05
0x180049efc  mov     eax, 8000FFFFh
0x180049f01  mov     [rsp+118h+Reply], eax
0x180049f05  mov     esi, [rsp+118h+dwMilliseconds]
0x180049f09  mov     r15b, [rsp+118h+var_D4]
0x180049f0e  mov     r14b, r15b
0x180049f11  test    eax, eax
0x180049f13  jns     short loc_180049F27
0x180049f15  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180049f1c  mov     r8d, 35Ah
0x180049f22  jmp     loc_180049FEB
0x180049f27  mov     [rsp+118h+bAlertable], 0; bAlertable
0x180049f2f  mov     r9d, esi; dwMilliseconds
0x180049f32  xor     r8d, r8d; bWaitAll
0x180049f35  lea     rdx, [rsp+118h+Handles]; lpHandles
0x180049f3a  lea     ecx, [r8+1]; nCount
0x180049f3e  call    cs:__imp_WaitForMultipleObjectsEx
0x180049f44  mov     esi, eax
0x180049f46  mov     r12d, 102h
0x180049f4c  test    r14b, r14b
0x180049f4f  jnz     short loc_180049F9D
0x180049f51  cmp     esi, r12d
0x180049f54  jz      short loc_180049F5B
0x180049f56  cmp     esi, 1
0x180049f59  jnz     short loc_180049F9D
0x180049f5b  mov     edx, 1; fAbort
0x180049f60  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180049f65  call    cs:__imp_RpcAsyncCancelCall
0x180049f6b  cmp     esi, r12d
0x180049f6e  jnz     short loc_180049F75
0x180049f70  mov     r15b, 1
0x180049f73  jmp     short loc_180049F78
0x180049f75  mov     r14b, 1
0x180049f78  mov     [rsp+118h+bAlertable], 0; bAlertable
0x180049f80  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180049f84  xor     r8d, r8d; bWaitAll
0x180049f87  lea     rdx, [rsp+118h+Handles]; lpHandles
0x180049f8c  lea     ecx, [r8+1]; nCount
0x180049f90  call    cs:__imp_WaitForMultipleObjectsEx
0x180049f96  mov     esi, eax
0x180049f98  test    r15b, r15b
0x180049f9b  jz      short loc_180049F4C
0x180049f9d  test    esi, esi
0x180049f9f  jz      short loc_180049FBC
0x180049fa1  call    cs:__imp_GetLastError
0x180049fa7  test    eax, eax
0x180049fa9  jle     short loc_180049FB3
0x180049fab  movzx   eax, ax
0x180049fae  or      eax, 80070000h
0x180049fb3  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180049fba  jmp     short loc_180049FE1
0x180049fbc  lea     rdx, [rsp+118h+Reply]; Reply
0x180049fc1  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180049fc6  call    cs:__imp_RpcAsyncCompleteCall
0x180049fcc  test    eax, eax
0x180049fce  jz      short loc_18004A000
0x180049fd0  jle     short loc_180049FDA
0x180049fd2  movzx   eax, ax
0x180049fd5  or      eax, 80070000h
0x180049fda  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180049fe1  mov     r8d, 35Ah; unsigned int
0x180049fe7  mov     [rsp+118h+Reply], eax
0x180049feb  mov     [rsp+118h+bAlertable], eax
0x180049fef  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180049ff6  mov     ecx, 2; unsigned __int8
0x180049ffb  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004a000  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x18004a008  test    rcx, rcx
0x18004a00b  jz      short loc_18004A013
0x18004a00d  call    cs:__imp_CloseHandle
0x18004a013  test    r15b, r15b
0x18004a016  jz      short loc_18004A050
0x18004a018  mov     [rsp+118h+Reply], 800705B4h
0x18004a020  lea     rdx, [rsp+118h+var_CC]
0x18004a025  call    ??$RPCCallTimedOut@AEAY0BP@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BP@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[31],ulong &>(char const (&)[31],ulong &)
0x18004a02a  mov     eax, [rsp+118h+Reply]
0x18004a02e  mov     [rsp+118h+bAlertable], eax
0x18004a032  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004a039  mov     r8d, 35Ah; unsigned int
0x18004a03f  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004a046  mov     ecx, 2; unsigned __int8
0x18004a04b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004a050  test    r14b, r14b
0x18004a053  jz      short loc_18004A080
0x18004a055  mov     eax, 800704C7h
0x18004a05a  mov     [rsp+118h+Reply], eax
0x18004a05e  mov     [rsp+118h+bAlertable], eax
0x18004a062  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004a069  mov     r8d, 35Ah; unsigned int
0x18004a06f  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004a076  mov     ecx, 2; unsigned __int8
0x18004a07b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004a080  mov     eax, [rsp+118h+Reply]
0x18004a084  cmp     eax, 800706B5h
0x18004a089  jz      short loc_18004A092
0x18004a08b  cmp     eax, 800706BAh
0x18004a090  jnz     short loc_18004A09B
0x18004a092  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004a097  mov     eax, [rsp+118h+Reply]
0x18004a09b  mov     rcx, [rsp+118h+var_38]
0x18004a0a3  xor     rcx, rsp; StackCookie
0x18004a0a6  call    __security_check_cookie
0x18004a0ab  add     rsp, 0F0h
0x18004a0b2  pop     r15
0x18004a0b4  pop     r14
0x18004a0b6  pop     r13
0x18004a0b8  pop     r12
0x18004a0ba  pop     rsi
0x18004a0bb  retn
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
