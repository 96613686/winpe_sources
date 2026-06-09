# WLIDCCreateContextWithLogonId(ushort const *,ushort const *,ulong,long,unsigned __int64,void * *)

- ea: `0x180044c08`
- end: `0x180044fb5`
- name: `?WLIDCCreateContextWithLogonId@@YAJPEBG0KJ_KPEAPEAX@Z`
- size: `941`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int, int, unsigned __int64, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180041630`

## callees

- `0x18000a400`
- `0x18000f870`
- `0x180010c68`
- `0x180011588`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x1800420d8`
- `0x180043240`
- `0x180044c08`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180044d0d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180044d0d`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180044e22`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180044e7a`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180044e22`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180044e7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044d20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044e8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044d20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044e8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044efa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044efa`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180044cc6`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180044cc6`
- `RPCRT4!RpcAsyncCancelCall` at `0x180044e4c`
- `RPCRT4!RpcAsyncCancelCall` at `0x180044e4c`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180044d97`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180044d97`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180044eb3`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180044eb3`

## string_xrefs

- `0x180044d32`: `RPC failed to create new event, hr = %#x`
- `0x180044ec7`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCCreateContextWithLogonId(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        int a3,
        int a4,
        unsigned __int64 a5,
        void **a6)
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
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  BOOL bAlertable[2]; // [rsp+20h] [rbp-128h]
  int Reply; // [rsp+60h] [rbp-E8h] BYREF
  char v20; // [rsp+64h] [rbp-E4h]
  DWORD dwMilliseconds; // [rsp+68h] [rbp-E0h] BYREF
  int v22; // [rsp+6Ch] [rbp-DCh]
  int v23; // [rsp+70h] [rbp-D8h]
  DWORD v24; // [rsp+74h] [rbp-D4h] BYREF
  __int64 v25; // [rsp+78h] [rbp-D0h] BYREF
  void **v26; // [rsp+80h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+88h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+A0h] [rbp-A8h] BYREF

  v22 = a4;
  v23 = a3;
  v26 = a6;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  v25 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v25);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v9 = dwMilliseconds;
  v24 = dwMilliseconds;
  v10 = 0;
  v20 = 0;
  v11 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v13 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v14 = 598;
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
    0xBu,
    0,
    &pAsync,
    v25,
    a1,
    a2,
    v23,
    v22,
    a5,
    v26);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v13 = L"RPC call failed, hr = %#x";
    v14 = 600;
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
    v14 = 600;
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
  NotificationRoutine = pAsync.u.APC.NotificationRoutine;
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v10 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[30],unsigned long &>(NotificationRoutine, &v24);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x258u,
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
      0x258u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v25);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x180044c08  push    rsi
0x180044c0a  push    r12
0x180044c0c  push    r13
0x180044c0e  push    r14
0x180044c10  push    r15
0x180044c12  sub     rsp, 120h
0x180044c19  mov     rax, cs:__security_cookie
0x180044c20  xor     rax, rsp
0x180044c23  mov     [rsp+148h+var_38], rax
0x180044c2b  mov     [rsp+148h+var_DC], r9d
0x180044c30  mov     [rsp+148h+var_D8], r8d
0x180044c35  mov     r13, rdx
0x180044c38  mov     r12, rcx
0x180044c3b  mov     rax, [rsp+148h+arg_28]
0x180044c43  mov     [rsp+148h+var_C8], rax
0x180044c4b  mov     [rsp+148h+dwMilliseconds], 0
0x180044c53  lea     r8, [rsp+148h+dwMilliseconds]; unsigned int *
0x180044c58  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180044c5d  mov     [rsp+148h+Reply], 0
0x180044c65  mov     [rsp+148h+var_D0], 0
0x180044c6e  lea     rcx, [rsp+148h+var_D0]; this
0x180044c73  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x180044c78  mov     [rsp+148h+Reply], eax
0x180044c7c  test    eax, eax
0x180044c7e  js      loc_180044F94
0x180044c84  xor     edx, edx; Val
0x180044c86  lea     r8d, [rdx+70h]; Size
0x180044c8a  lea     rcx, [rsp+148h+pAsync]; void *
0x180044c92  call    memset_0
0x180044c97  mov     esi, [rsp+148h+dwMilliseconds]
0x180044c9b  mov     [rsp+148h+dwMilliseconds], esi
0x180044c9f  mov     [rsp+148h+var_D4], esi
0x180044ca3  xor     r15b, r15b
0x180044ca6  mov     [rsp+148h+var_E4], r15b
0x180044cab  xor     r14b, r14b
0x180044cae  xorps   xmm0, xmm0
0x180044cb1  movups  xmmword ptr [rsp+148h+Handles], xmm0
0x180044cb9  mov     edx, 70h ; 'p'; Size
0x180044cbe  lea     rcx, [rsp+148h+pAsync]; pAsync
0x180044cc6  call    cs:__imp_RpcAsyncInitializeHandle
0x180044ccc  test    eax, eax
0x180044cce  jz      short loc_180044CEC
0x180044cd0  jle     short loc_180044CDA
0x180044cd2  movzx   eax, ax
0x180044cd5  or      eax, 80070000h
0x180044cda  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180044ce1  mov     r8d, 256h
0x180044ce7  jmp     loc_180044ED4
0x180044cec  mov     [rsp+148h+pAsync.UserInfo], 0
0x180044cf8  mov     [rsp+148h+pAsync.NotificationType], 1
0x180044d03  xor     r9d, r9d; lpName
0x180044d06  xor     r8d, r8d; bInitialState
0x180044d09  xor     edx, edx; bManualReset
0x180044d0b  xor     ecx, ecx; lpEventAttributes
0x180044d0d  call    cs:__imp_CreateEventW
0x180044d13  mov     qword ptr [rsp+148h+pAsync.u], rax
0x180044d1b  test    rax, rax
0x180044d1e  jnz     short loc_180044D3B
0x180044d20  call    cs:__imp_GetLastError
0x180044d26  test    eax, eax
0x180044d28  jle     short loc_180044D32
0x180044d2a  movzx   eax, ax
0x180044d2d  or      eax, 80070000h
0x180044d32  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180044d39  jmp     short loc_180044CE1
0x180044d3b  mov     [rsp+148h+Handles], rax
0x180044d43  mov     rax, [rsp+148h+var_C8]
0x180044d4b  mov     [rsp+148h+var_F8], rax
0x180044d50  mov     rax, [rsp+148h+arg_20]
0x180044d58  mov     [rsp+148h+var_100], rax
0x180044d5d  mov     eax, [rsp+148h+var_DC]
0x180044d61  mov     [rsp+148h+var_108], eax
0x180044d65  mov     eax, [rsp+148h+var_D8]
0x180044d69  mov     [rsp+148h+var_110], eax
0x180044d6d  mov     [rsp+148h+var_118], r13
0x180044d72  mov     [rsp+148h+var_120], r12
0x180044d77  mov     rax, [rsp+148h+var_D0]
0x180044d7c  mov     qword ptr [rsp+148h+bAlertable], rax
0x180044d81  lea     r9, [rsp+148h+pAsync]
0x180044d89  xor     r8d, r8d; pReturnValue
0x180044d8c  lea     edx, [r8+0Bh]; nProcNum
0x180044d90  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180044d97  call    cs:__imp_Ndr64AsyncClientCall
0x180044d9d  mov     eax, [rsp+148h+Reply]
0x180044da1  jmp     short loc_180044DF2
0x180044da3  test    eax, eax
0x180044da5  jle     short loc_180044DAF
0x180044da7  movzx   eax, ax
0x180044daa  or      eax, 80070000h
0x180044daf  mov     [rsp+148h+Reply], eax
0x180044db3  mov     [rsp+148h+bAlertable], eax
0x180044db7  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180044dbe  mov     r8d, 258h; unsigned int
0x180044dc4  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180044dcb  mov     ecx, 2; unsigned __int8
0x180044dd0  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180044dd5  mov     eax, [rsp+148h+Reply]
0x180044dd9  test    eax, eax
0x180044ddb  js      short loc_180044DE6
0x180044ddd  mov     eax, 8000FFFFh
0x180044de2  mov     [rsp+148h+Reply], eax
0x180044de6  mov     esi, [rsp+148h+dwMilliseconds]
0x180044dea  mov     r15b, [rsp+148h+var_E4]
0x180044def  mov     r14b, r15b
0x180044df2  test    eax, eax
0x180044df4  jns     short loc_180044E08
0x180044df6  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180044dfd  mov     r8d, 258h
0x180044e03  jmp     loc_180044ED8
0x180044e08  mov     [rsp+148h+bAlertable], 0; bAlertable
0x180044e10  mov     r9d, esi; dwMilliseconds
0x180044e13  xor     r8d, r8d; bWaitAll
0x180044e16  lea     rdx, [rsp+148h+Handles]; lpHandles
0x180044e1e  lea     ecx, [r8+1]; nCount
0x180044e22  call    cs:__imp_WaitForMultipleObjectsEx
0x180044e28  mov     esi, eax
0x180044e2a  mov     r12d, 102h
0x180044e30  test    r14b, r14b
0x180044e33  jnz     short loc_180044E87
0x180044e35  cmp     esi, r12d
0x180044e38  jz      short loc_180044E3F
0x180044e3a  cmp     esi, 1
0x180044e3d  jnz     short loc_180044E87
0x180044e3f  mov     edx, 1; fAbort
0x180044e44  lea     rcx, [rsp+148h+pAsync]; pAsync
0x180044e4c  call    cs:__imp_RpcAsyncCancelCall
0x180044e52  cmp     esi, r12d
0x180044e55  jnz     short loc_180044E5C
0x180044e57  mov     r15b, 1
0x180044e5a  jmp     short loc_180044E5F
0x180044e5c  mov     r14b, 1
0x180044e5f  mov     [rsp+148h+bAlertable], 0; bAlertable
0x180044e67  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180044e6b  xor     r8d, r8d; bWaitAll
0x180044e6e  lea     rdx, [rsp+148h+Handles]; lpHandles
0x180044e76  lea     ecx, [r8+1]; nCount
0x180044e7a  call    cs:__imp_WaitForMultipleObjectsEx
0x180044e80  mov     esi, eax
0x180044e82  test    r15b, r15b
0x180044e85  jz      short loc_180044E30
0x180044e87  test    esi, esi
0x180044e89  jz      short loc_180044EA6
0x180044e8b  call    cs:__imp_GetLastError
0x180044e91  test    eax, eax
0x180044e93  jle     short loc_180044E9D
0x180044e95  movzx   eax, ax
0x180044e98  or      eax, 80070000h
0x180044e9d  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180044ea4  jmp     short loc_180044ECE
0x180044ea6  lea     rdx, [rsp+148h+Reply]; Reply
0x180044eab  lea     rcx, [rsp+148h+pAsync]; pAsync
0x180044eb3  call    cs:__imp_RpcAsyncCompleteCall
0x180044eb9  test    eax, eax
0x180044ebb  jz      short loc_180044EED
0x180044ebd  jle     short loc_180044EC7
0x180044ebf  movzx   eax, ax
0x180044ec2  or      eax, 80070000h
0x180044ec7  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180044ece  mov     r8d, 258h; unsigned int
0x180044ed4  mov     [rsp+148h+Reply], eax
0x180044ed8  mov     [rsp+148h+bAlertable], eax
0x180044edc  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180044ee3  mov     ecx, 2; unsigned __int8
0x180044ee8  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180044eed  mov     rcx, qword ptr [rsp+148h+pAsync.u]; hObject
0x180044ef5  test    rcx, rcx
0x180044ef8  jz      short loc_180044F00
0x180044efa  call    cs:__imp_CloseHandle
0x180044f00  test    r15b, r15b
0x180044f03  jz      short loc_180044F3D
0x180044f05  mov     [rsp+148h+Reply], 800705B4h
0x180044f0d  lea     rdx, [rsp+148h+var_D4]
0x180044f12  call    ??$RPCCallTimedOut@AEAY0BO@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BO@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[30],ulong &>(char const (&)[30],ulong &)
0x180044f17  mov     eax, [rsp+148h+Reply]
0x180044f1b  mov     [rsp+148h+bAlertable], eax
0x180044f1f  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180044f26  mov     r8d, 258h; unsigned int
0x180044f2c  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180044f33  mov     ecx, 2; unsigned __int8
0x180044f38  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180044f3d  test    r14b, r14b
0x180044f40  jz      short loc_180044F6D
0x180044f42  mov     eax, 800704C7h
0x180044f47  mov     [rsp+148h+Reply], eax
0x180044f4b  mov     [rsp+148h+bAlertable], eax
0x180044f4f  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180044f56  mov     r8d, 258h; unsigned int
0x180044f5c  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180044f63  mov     ecx, 2; unsigned __int8
0x180044f68  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180044f6d  cmp     [rsp+148h+Reply], 800706B5h
0x180044f75  jz      short loc_180044F81
0x180044f77  cmp     [rsp+148h+Reply], 800706BAh
0x180044f7f  jnz     short loc_180044F86
0x180044f81  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180044f86  lea     rcx, [rsp+148h+var_D0]; this
0x180044f8b  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x180044f90  mov     eax, [rsp+148h+Reply]
0x180044f94  mov     rcx, [rsp+148h+var_38]
0x180044f9c  xor     rcx, rsp; StackCookie
0x180044f9f  call    __security_check_cookie
0x180044fa4  add     rsp, 120h
0x180044fab  pop     r15
0x180044fad  pop     r14
0x180044faf  pop     r13
0x180044fb1  pop     r12
0x180044fb3  pop     rsi
0x180044fb4  retn
0x180057641  push    rbp
0x180057643  sub     rsp, 60h
0x180057647  mov     rbp, rdx
0x18005764a  mov     rcx, [rcx]
0x18005764d  mov     ecx, [rcx]; unsigned int
0x18005764f  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x180057654  nop
0x180057655  add     rsp, 60h
0x180057659  pop     rbp
0x18005765a  retn
```
