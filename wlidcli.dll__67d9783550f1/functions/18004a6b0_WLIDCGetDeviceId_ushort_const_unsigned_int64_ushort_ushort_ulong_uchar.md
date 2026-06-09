# WLIDCGetDeviceId(ushort const *,unsigned __int64,ushort * *,ushort * *,ulong *,uchar * *)

- ea: `0x18004a6b0`
- end: `0x18004aa7e`
- name: `?WLIDCGetDeviceId@@YAJPEBG_KPEAPEAG2PEAKPEAPEAE@Z`
- size: `974`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64, unsigned __int16 **, unsigned __int16 **, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002d8a0`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180044d94`
- `0x180046ce0`
- `0x18004a6b0`
- `0x18004cd04`
- `0x180050c84`
- `0x180050e40`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004a8e4`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004a93c`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004a8e4`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004a93c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004a7c8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004a7c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a7db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a94d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a7db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a94d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a9bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a9bc`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004a90e`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004a90e`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004a859`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004a859`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004a975`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004a975`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004a781`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004a781`

## string_xrefs

- `0x18004a7ed`: `RPC failed to create new event, hr = %#x`
- `0x18004a989`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCGetDeviceId(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4,
        unsigned int *a5,
        unsigned __int8 **a6)
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
  BOOL bAlertable[2]; // [rsp+20h] [rbp-138h]
  int Reply; // [rsp+60h] [rbp-F8h] BYREF
  char v19; // [rsp+64h] [rbp-F4h]
  DWORD dwMilliseconds; // [rsp+68h] [rbp-F0h] BYREF
  DWORD v21; // [rsp+6Ch] [rbp-ECh] BYREF
  __int64 v22; // [rsp+70h] [rbp-E8h] BYREF
  unsigned __int8 **v23; // [rsp+78h] [rbp-E0h]
  unsigned int *v24; // [rsp+80h] [rbp-D8h]
  unsigned __int16 **v25; // [rsp+88h] [rbp-D0h]
  unsigned __int16 **v26; // [rsp+90h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+98h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+B0h] [rbp-A8h] BYREF

  v25 = a4;
  v26 = a3;
  v24 = a5;
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
    v14 = 886;
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
  Ndr64AsyncClientCall(
    (MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo,
    0x1Eu,
    0,
    &pAsync,
    v22,
    a1,
    a2,
    v26,
    v25,
    v24,
    v23);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v13 = L"RPC call failed, hr = %#x";
    v14 = 888;
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
    v14 = 888;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[17],unsigned long &>(
      (__int64)"WLIDCGetDeviceId",
      (int *)&v21);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x378u,
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
      0x378u,
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
0x18004a6b0  push    rsi
0x18004a6b2  push    r12
0x18004a6b4  push    r13
0x18004a6b6  push    r14
0x18004a6b8  push    r15
0x18004a6ba  sub     rsp, 130h
0x18004a6c1  mov     rax, cs:__security_cookie
0x18004a6c8  xor     rax, rsp
0x18004a6cb  mov     [rsp+158h+var_38], rax
0x18004a6d3  mov     [rsp+158h+var_D0], r9
0x18004a6db  mov     [rsp+158h+var_C8], r8
0x18004a6e3  mov     r13, rdx
0x18004a6e6  mov     r12, rcx
0x18004a6e9  mov     rax, [rsp+158h+arg_20]
0x18004a6f1  mov     [rsp+158h+var_D8], rax
0x18004a6f9  mov     rax, [rsp+158h+arg_28]
0x18004a701  mov     [rsp+158h+var_E0], rax
0x18004a706  mov     [rsp+158h+dwMilliseconds], 0
0x18004a70e  lea     r8, [rsp+158h+dwMilliseconds]; unsigned int *
0x18004a713  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004a718  mov     [rsp+158h+Reply], 0
0x18004a720  mov     [rsp+158h+var_E8], 0
0x18004a729  lea     rcx, [rsp+158h+var_E8]; this
0x18004a72e  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18004a733  mov     [rsp+158h+Reply], eax
0x18004a737  test    eax, eax
0x18004a739  js      loc_18004AA5D
0x18004a73f  xor     edx, edx; Val
0x18004a741  lea     r8d, [rdx+70h]; Size
0x18004a745  lea     rcx, [rsp+158h+pAsync]; void *
0x18004a74d  call    memset_0
0x18004a752  mov     esi, [rsp+158h+dwMilliseconds]
0x18004a756  mov     [rsp+158h+dwMilliseconds], esi
0x18004a75a  mov     [rsp+158h+var_EC], esi
0x18004a75e  xor     r15b, r15b
0x18004a761  mov     [rsp+158h+var_F4], r15b
0x18004a766  xor     r14b, r14b
0x18004a769  xorps   xmm0, xmm0
0x18004a76c  movups  xmmword ptr [rsp+158h+Handles], xmm0
0x18004a774  mov     edx, 70h ; 'p'; Size
0x18004a779  lea     rcx, [rsp+158h+pAsync]; pAsync
0x18004a781  call    cs:__imp_RpcAsyncInitializeHandle
0x18004a787  test    eax, eax
0x18004a789  jz      short loc_18004A7A7
0x18004a78b  jle     short loc_18004A795
0x18004a78d  movzx   eax, ax
0x18004a790  or      eax, 80070000h
0x18004a795  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004a79c  mov     r8d, 376h
0x18004a7a2  jmp     loc_18004A996
0x18004a7a7  mov     [rsp+158h+pAsync.UserInfo], 0
0x18004a7b3  mov     [rsp+158h+pAsync.NotificationType], 1
0x18004a7be  xor     r9d, r9d; lpName
0x18004a7c1  xor     r8d, r8d; bInitialState
0x18004a7c4  xor     edx, edx; bManualReset
0x18004a7c6  xor     ecx, ecx; lpEventAttributes
0x18004a7c8  call    cs:__imp_CreateEventW
0x18004a7ce  mov     qword ptr [rsp+158h+pAsync.u], rax
0x18004a7d6  test    rax, rax
0x18004a7d9  jnz     short loc_18004A7F6
0x18004a7db  call    cs:__imp_GetLastError
0x18004a7e1  test    eax, eax
0x18004a7e3  jle     short loc_18004A7ED
0x18004a7e5  movzx   eax, ax
0x18004a7e8  or      eax, 80070000h
0x18004a7ed  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004a7f4  jmp     short loc_18004A79C
0x18004a7f6  mov     [rsp+158h+Handles], rax
0x18004a7fe  mov     rax, [rsp+158h+var_E0]
0x18004a803  mov     [rsp+158h+var_108], rax
0x18004a808  mov     rax, [rsp+158h+var_D8]
0x18004a810  mov     [rsp+158h+var_110], rax
0x18004a815  mov     rax, [rsp+158h+var_D0]
0x18004a81d  mov     [rsp+158h+var_118], rax
0x18004a822  mov     rax, [rsp+158h+var_C8]
0x18004a82a  mov     [rsp+158h+var_120], rax
0x18004a82f  mov     [rsp+158h+var_128], r13
0x18004a834  mov     [rsp+158h+var_130], r12
0x18004a839  mov     rax, [rsp+158h+var_E8]
0x18004a83e  mov     qword ptr [rsp+158h+bAlertable], rax
0x18004a843  lea     r9, [rsp+158h+pAsync]
0x18004a84b  xor     r8d, r8d; pReturnValue
0x18004a84e  lea     edx, [r8+1Eh]; nProcNum
0x18004a852  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004a859  call    cs:__imp_Ndr64AsyncClientCall
0x18004a85f  mov     eax, [rsp+158h+Reply]
0x18004a863  jmp     short loc_18004A8B4
0x18004a865  test    eax, eax
0x18004a867  jle     short loc_18004A871
0x18004a869  movzx   eax, ax
0x18004a86c  or      eax, 80070000h
0x18004a871  mov     [rsp+158h+Reply], eax
0x18004a875  mov     [rsp+158h+bAlertable], eax
0x18004a879  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004a880  mov     r8d, 378h; unsigned int
0x18004a886  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004a88d  mov     ecx, 2; unsigned __int8
0x18004a892  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004a897  mov     eax, [rsp+158h+Reply]
0x18004a89b  test    eax, eax
0x18004a89d  js      short loc_18004A8A8
0x18004a89f  mov     eax, 8000FFFFh
0x18004a8a4  mov     [rsp+158h+Reply], eax
0x18004a8a8  mov     esi, [rsp+158h+dwMilliseconds]
0x18004a8ac  mov     r15b, [rsp+158h+var_F4]
0x18004a8b1  mov     r14b, r15b
0x18004a8b4  test    eax, eax
0x18004a8b6  jns     short loc_18004A8CA
0x18004a8b8  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004a8bf  mov     r8d, 378h
0x18004a8c5  jmp     loc_18004A99A
0x18004a8ca  mov     [rsp+158h+bAlertable], 0; bAlertable
0x18004a8d2  mov     r9d, esi; dwMilliseconds
0x18004a8d5  xor     r8d, r8d; bWaitAll
0x18004a8d8  lea     rdx, [rsp+158h+Handles]; lpHandles
0x18004a8e0  lea     ecx, [r8+1]; nCount
0x18004a8e4  call    cs:__imp_WaitForMultipleObjectsEx
0x18004a8ea  mov     esi, eax
0x18004a8ec  mov     r12d, 102h
0x18004a8f2  test    r14b, r14b
0x18004a8f5  jnz     short loc_18004A949
0x18004a8f7  cmp     esi, r12d
0x18004a8fa  jz      short loc_18004A901
0x18004a8fc  cmp     esi, 1
0x18004a8ff  jnz     short loc_18004A949
0x18004a901  mov     edx, 1; fAbort
0x18004a906  lea     rcx, [rsp+158h+pAsync]; pAsync
0x18004a90e  call    cs:__imp_RpcAsyncCancelCall
0x18004a914  cmp     esi, r12d
0x18004a917  jnz     short loc_18004A91E
0x18004a919  mov     r15b, 1
0x18004a91c  jmp     short loc_18004A921
0x18004a91e  mov     r14b, 1
0x18004a921  mov     [rsp+158h+bAlertable], 0; bAlertable
0x18004a929  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004a92d  xor     r8d, r8d; bWaitAll
0x18004a930  lea     rdx, [rsp+158h+Handles]; lpHandles
0x18004a938  lea     ecx, [r8+1]; nCount
0x18004a93c  call    cs:__imp_WaitForMultipleObjectsEx
0x18004a942  mov     esi, eax
0x18004a944  test    r15b, r15b
0x18004a947  jz      short loc_18004A8F2
0x18004a949  test    esi, esi
0x18004a94b  jz      short loc_18004A968
0x18004a94d  call    cs:__imp_GetLastError
0x18004a953  test    eax, eax
0x18004a955  jle     short loc_18004A95F
0x18004a957  movzx   eax, ax
0x18004a95a  or      eax, 80070000h
0x18004a95f  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004a966  jmp     short loc_18004A990
0x18004a968  lea     rdx, [rsp+158h+Reply]; Reply
0x18004a96d  lea     rcx, [rsp+158h+pAsync]; pAsync
0x18004a975  call    cs:__imp_RpcAsyncCompleteCall
0x18004a97b  test    eax, eax
0x18004a97d  jz      short loc_18004A9AF
0x18004a97f  jle     short loc_18004A989
0x18004a981  movzx   eax, ax
0x18004a984  or      eax, 80070000h
0x18004a989  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004a990  mov     r8d, 378h; unsigned int
0x18004a996  mov     [rsp+158h+Reply], eax
0x18004a99a  mov     [rsp+158h+bAlertable], eax
0x18004a99e  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004a9a5  mov     ecx, 2; unsigned __int8
0x18004a9aa  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004a9af  mov     rcx, qword ptr [rsp+158h+pAsync.u]; hObject
0x18004a9b7  test    rcx, rcx
0x18004a9ba  jz      short loc_18004A9C2
0x18004a9bc  call    cs:__imp_CloseHandle
0x18004a9c2  test    r15b, r15b
0x18004a9c5  jz      short loc_18004AA06
0x18004a9c7  mov     [rsp+158h+Reply], 800705B4h
0x18004a9cf  lea     rdx, [rsp+158h+var_EC]
0x18004a9d4  lea     rcx, aWlidcgetdevice_0; "WLIDCGetDeviceId"
0x18004a9db  call    ??$RPCCallTimedOut@AEAY0BB@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BB@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[17],ulong &>(char const (&)[17],ulong &)
0x18004a9e0  mov     eax, [rsp+158h+Reply]
0x18004a9e4  mov     [rsp+158h+bAlertable], eax
0x18004a9e8  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004a9ef  mov     r8d, 378h; unsigned int
0x18004a9f5  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004a9fc  mov     ecx, 2; unsigned __int8
0x18004aa01  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004aa06  test    r14b, r14b
0x18004aa09  jz      short loc_18004AA36
0x18004aa0b  mov     eax, 800704C7h
0x18004aa10  mov     [rsp+158h+Reply], eax
0x18004aa14  mov     [rsp+158h+bAlertable], eax
0x18004aa18  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004aa1f  mov     r8d, 378h; unsigned int
0x18004aa25  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004aa2c  mov     ecx, 2; unsigned __int8
0x18004aa31  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004aa36  cmp     [rsp+158h+Reply], 800706B5h
0x18004aa3e  jz      short loc_18004AA4A
0x18004aa40  cmp     [rsp+158h+Reply], 800706BAh
0x18004aa48  jnz     short loc_18004AA4F
0x18004aa4a  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004aa4f  lea     rcx, [rsp+158h+var_E8]; this
0x18004aa54  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18004aa59  mov     eax, [rsp+158h+Reply]
0x18004aa5d  mov     rcx, [rsp+158h+var_38]
0x18004aa65  xor     rcx, rsp; StackCookie
0x18004aa68  call    __security_check_cookie
0x18004aa6d  add     rsp, 130h
0x18004aa74  pop     r15
0x18004aa76  pop     r14
0x18004aa78  pop     r13
0x18004aa7a  pop     r12
0x18004aa7c  pop     rsi
0x18004aa7d  retn
0x180061a16  push    rbp
0x180061a18  sub     rsp, 60h
0x180061a1c  mov     rbp, rdx
0x180061a1f  mov     rcx, [rcx]
0x180061a22  mov     ecx, [rcx]; unsigned int
0x180061a24  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x180061a29  nop
0x180061a2a  add     rsp, 60h
0x180061a2e  pop     rbp
0x180061a2f  retn
```
