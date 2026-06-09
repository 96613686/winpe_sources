# WLIDCGetKeyLatest(void * const,unsigned __int64,ushort const *,ushort * *,ushort * *,__int64 *)

- ea: `0x180046d90`
- end: `0x180047141`
- name: `?WLIDCGetKeyLatest@@YAJQEAX_KPEBGPEAPEAG3PEA_J@Z`
- size: `945`
- prototype: `__int64 __fastcall(void *const, unsigned __int64, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180041740`

## callees

- `0x18000a400`
- `0x18000f870`
- `0x180010c68`
- `0x180011588`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180041ae4`
- `0x180043240`
- `0x180046d90`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046ea2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046ea2`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180046fae`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180047006`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180046fae`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180047006`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046eb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047017`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046eb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047017`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047086`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047086`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180046e5b`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180046e5b`
- `RPCRT4!RpcAsyncCancelCall` at `0x180046fd8`
- `RPCRT4!RpcAsyncCancelCall` at `0x180046fd8`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180046f23`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180046f23`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004703f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004703f`

## string_xrefs

- `0x180046ec7`: `RPC failed to create new event, hr = %#x`
- `0x180047053`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCGetKeyLatest(
        void *const a1,
        __int64 a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5,
        __int64 *a6)
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
  int Reply; // [rsp+50h] [rbp-F8h] BYREF
  char v20; // [rsp+54h] [rbp-F4h]
  DWORD dwMilliseconds; // [rsp+58h] [rbp-F0h] BYREF
  DWORD v22; // [rsp+5Ch] [rbp-ECh] BYREF
  __int64 v23; // [rsp+60h] [rbp-E8h] BYREF
  __int64 *v24; // [rsp+68h] [rbp-E0h]
  unsigned __int16 **v25; // [rsp+70h] [rbp-D8h]
  unsigned __int16 **v26; // [rsp+78h] [rbp-D0h]
  const unsigned __int16 *v27; // [rsp+80h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+88h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+A0h] [rbp-A8h] BYREF

  v26 = a4;
  v27 = a3;
  v25 = a5;
  v24 = a6;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  v23 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v23);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v9 = dwMilliseconds;
  v22 = dwMilliseconds;
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
    v14 = 1292;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x3Cu, 0, &pAsync, a1, a2, v27, v26, v25, v24);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v13 = L"RPC call failed, hr = %#x";
    v14 = 1294;
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
    v14 = 1294;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[18],unsigned long &>(NotificationRoutine, &v22);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x50Eu,
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
      0x50Eu,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v23);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x180046d90  push    rsi
0x180046d92  push    r12
0x180046d94  push    r13
0x180046d96  push    r14
0x180046d98  push    r15
0x180046d9a  sub     rsp, 120h
0x180046da1  mov     rax, cs:__security_cookie
0x180046da8  xor     rax, rsp
0x180046dab  mov     [rsp+148h+var_38], rax
0x180046db3  mov     [rsp+148h+var_D0], r9
0x180046db8  mov     [rsp+148h+var_C8], r8
0x180046dc0  mov     r13, rdx
0x180046dc3  mov     r12, rcx
0x180046dc6  mov     rax, [rsp+148h+arg_20]
0x180046dce  mov     [rsp+148h+var_D8], rax
0x180046dd3  mov     rax, [rsp+148h+arg_28]
0x180046ddb  mov     [rsp+148h+var_E0], rax
0x180046de0  mov     [rsp+148h+dwMilliseconds], 0
0x180046de8  lea     r8, [rsp+148h+dwMilliseconds]; unsigned int *
0x180046ded  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180046df2  mov     [rsp+148h+Reply], 0
0x180046dfa  mov     [rsp+148h+var_E8], 0
0x180046e03  lea     rcx, [rsp+148h+var_E8]; this
0x180046e08  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x180046e0d  mov     [rsp+148h+Reply], eax
0x180046e11  test    eax, eax
0x180046e13  js      loc_180047120
0x180046e19  xor     edx, edx; Val
0x180046e1b  lea     r8d, [rdx+70h]; Size
0x180046e1f  lea     rcx, [rsp+148h+pAsync]; void *
0x180046e27  call    memset_0
0x180046e2c  mov     esi, [rsp+148h+dwMilliseconds]
0x180046e30  mov     [rsp+148h+dwMilliseconds], esi
0x180046e34  mov     [rsp+148h+var_EC], esi
0x180046e38  xor     r15b, r15b
0x180046e3b  mov     [rsp+148h+var_F4], r15b
0x180046e40  xor     r14b, r14b
0x180046e43  xorps   xmm0, xmm0
0x180046e46  movups  xmmword ptr [rsp+148h+Handles], xmm0
0x180046e4e  mov     edx, 70h ; 'p'; Size
0x180046e53  lea     rcx, [rsp+148h+pAsync]; pAsync
0x180046e5b  call    cs:__imp_RpcAsyncInitializeHandle
0x180046e61  test    eax, eax
0x180046e63  jz      short loc_180046E81
0x180046e65  jle     short loc_180046E6F
0x180046e67  movzx   eax, ax
0x180046e6a  or      eax, 80070000h
0x180046e6f  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180046e76  mov     r8d, 50Ch
0x180046e7c  jmp     loc_180047060
0x180046e81  mov     [rsp+148h+pAsync.UserInfo], 0
0x180046e8d  mov     [rsp+148h+pAsync.NotificationType], 1
0x180046e98  xor     r9d, r9d; lpName
0x180046e9b  xor     r8d, r8d; bInitialState
0x180046e9e  xor     edx, edx; bManualReset
0x180046ea0  xor     ecx, ecx; lpEventAttributes
0x180046ea2  call    cs:__imp_CreateEventW
0x180046ea8  mov     qword ptr [rsp+148h+pAsync.u], rax
0x180046eb0  test    rax, rax
0x180046eb3  jnz     short loc_180046ED0
0x180046eb5  call    cs:__imp_GetLastError
0x180046ebb  test    eax, eax
0x180046ebd  jle     short loc_180046EC7
0x180046ebf  movzx   eax, ax
0x180046ec2  or      eax, 80070000h
0x180046ec7  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180046ece  jmp     short loc_180046E76
0x180046ed0  mov     [rsp+148h+Handles], rax
0x180046ed8  mov     rax, [rsp+148h+var_E0]
0x180046edd  mov     [rsp+148h+var_100], rax
0x180046ee2  mov     rax, [rsp+148h+var_D8]
0x180046ee7  mov     [rsp+148h+var_108], rax
0x180046eec  mov     rax, [rsp+148h+var_D0]
0x180046ef1  mov     [rsp+148h+var_110], rax
0x180046ef6  mov     rax, [rsp+148h+var_C8]
0x180046efe  mov     [rsp+148h+var_118], rax
0x180046f03  mov     [rsp+148h+var_120], r13
0x180046f08  mov     qword ptr [rsp+148h+bAlertable], r12
0x180046f0d  lea     r9, [rsp+148h+pAsync]
0x180046f15  xor     r8d, r8d; pReturnValue
0x180046f18  lea     edx, [r8+3Ch]; nProcNum
0x180046f1c  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180046f23  call    cs:__imp_Ndr64AsyncClientCall
0x180046f29  mov     eax, [rsp+148h+Reply]
0x180046f2d  jmp     short loc_180046F7E
0x180046f2f  test    eax, eax
0x180046f31  jle     short loc_180046F3B
0x180046f33  movzx   eax, ax
0x180046f36  or      eax, 80070000h
0x180046f3b  mov     [rsp+148h+Reply], eax
0x180046f3f  mov     [rsp+148h+bAlertable], eax
0x180046f43  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180046f4a  mov     r8d, 50Eh; unsigned int
0x180046f50  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180046f57  mov     ecx, 2; unsigned __int8
0x180046f5c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180046f61  mov     eax, [rsp+148h+Reply]
0x180046f65  test    eax, eax
0x180046f67  js      short loc_180046F72
0x180046f69  mov     eax, 8000FFFFh
0x180046f6e  mov     [rsp+148h+Reply], eax
0x180046f72  mov     esi, [rsp+148h+dwMilliseconds]
0x180046f76  mov     r15b, [rsp+148h+var_F4]
0x180046f7b  mov     r14b, r15b
0x180046f7e  test    eax, eax
0x180046f80  jns     short loc_180046F94
0x180046f82  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180046f89  mov     r8d, 50Eh
0x180046f8f  jmp     loc_180047064
0x180046f94  mov     [rsp+148h+bAlertable], 0; bAlertable
0x180046f9c  mov     r9d, esi; dwMilliseconds
0x180046f9f  xor     r8d, r8d; bWaitAll
0x180046fa2  lea     rdx, [rsp+148h+Handles]; lpHandles
0x180046faa  lea     ecx, [r8+1]; nCount
0x180046fae  call    cs:__imp_WaitForMultipleObjectsEx
0x180046fb4  mov     esi, eax
0x180046fb6  mov     r12d, 102h
0x180046fbc  test    r14b, r14b
0x180046fbf  jnz     short loc_180047013
0x180046fc1  cmp     esi, r12d
0x180046fc4  jz      short loc_180046FCB
0x180046fc6  cmp     esi, 1
0x180046fc9  jnz     short loc_180047013
0x180046fcb  mov     edx, 1; fAbort
0x180046fd0  lea     rcx, [rsp+148h+pAsync]; pAsync
0x180046fd8  call    cs:__imp_RpcAsyncCancelCall
0x180046fde  cmp     esi, r12d
0x180046fe1  jnz     short loc_180046FE8
0x180046fe3  mov     r15b, 1
0x180046fe6  jmp     short loc_180046FEB
0x180046fe8  mov     r14b, 1
0x180046feb  mov     [rsp+148h+bAlertable], 0; bAlertable
0x180046ff3  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180046ff7  xor     r8d, r8d; bWaitAll
0x180046ffa  lea     rdx, [rsp+148h+Handles]; lpHandles
0x180047002  lea     ecx, [r8+1]; nCount
0x180047006  call    cs:__imp_WaitForMultipleObjectsEx
0x18004700c  mov     esi, eax
0x18004700e  test    r15b, r15b
0x180047011  jz      short loc_180046FBC
0x180047013  test    esi, esi
0x180047015  jz      short loc_180047032
0x180047017  call    cs:__imp_GetLastError
0x18004701d  test    eax, eax
0x18004701f  jle     short loc_180047029
0x180047021  movzx   eax, ax
0x180047024  or      eax, 80070000h
0x180047029  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180047030  jmp     short loc_18004705A
0x180047032  lea     rdx, [rsp+148h+Reply]; Reply
0x180047037  lea     rcx, [rsp+148h+pAsync]; pAsync
0x18004703f  call    cs:__imp_RpcAsyncCompleteCall
0x180047045  test    eax, eax
0x180047047  jz      short loc_180047079
0x180047049  jle     short loc_180047053
0x18004704b  movzx   eax, ax
0x18004704e  or      eax, 80070000h
0x180047053  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004705a  mov     r8d, 50Eh; unsigned int
0x180047060  mov     [rsp+148h+Reply], eax
0x180047064  mov     [rsp+148h+bAlertable], eax
0x180047068  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004706f  mov     ecx, 2; unsigned __int8
0x180047074  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180047079  mov     rcx, qword ptr [rsp+148h+pAsync.u]; hObject
0x180047081  test    rcx, rcx
0x180047084  jz      short loc_18004708C
0x180047086  call    cs:__imp_CloseHandle
0x18004708c  test    r15b, r15b
0x18004708f  jz      short loc_1800470C9
0x180047091  mov     [rsp+148h+Reply], 800705B4h
0x180047099  lea     rdx, [rsp+148h+var_EC]
0x18004709e  call    ??$RPCCallTimedOut@AEAY0BC@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BC@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[18],ulong &>(char const (&)[18],ulong &)
0x1800470a3  mov     eax, [rsp+148h+Reply]
0x1800470a7  mov     [rsp+148h+bAlertable], eax
0x1800470ab  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x1800470b2  mov     r8d, 50Eh; unsigned int
0x1800470b8  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800470bf  mov     ecx, 2; unsigned __int8
0x1800470c4  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800470c9  test    r14b, r14b
0x1800470cc  jz      short loc_1800470F9
0x1800470ce  mov     eax, 800704C7h
0x1800470d3  mov     [rsp+148h+Reply], eax
0x1800470d7  mov     [rsp+148h+bAlertable], eax
0x1800470db  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x1800470e2  mov     r8d, 50Eh; unsigned int
0x1800470e8  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800470ef  mov     ecx, 2; unsigned __int8
0x1800470f4  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800470f9  cmp     [rsp+148h+Reply], 800706B5h
0x180047101  jz      short loc_18004710D
0x180047103  cmp     [rsp+148h+Reply], 800706BAh
0x18004710b  jnz     short loc_180047112
0x18004710d  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180047112  lea     rcx, [rsp+148h+var_E8]; this
0x180047117  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18004711c  mov     eax, [rsp+148h+Reply]
0x180047120  mov     rcx, [rsp+148h+var_38]
0x180047128  xor     rcx, rsp; StackCookie
0x18004712b  call    __security_check_cookie
0x180047130  add     rsp, 120h
0x180047137  pop     r15
0x180047139  pop     r14
0x18004713b  pop     r13
0x18004713d  pop     r12
0x18004713f  pop     rsi
0x180047140  retn
0x180057620  push    rbp
0x180057622  sub     rsp, 50h
0x180057626  mov     rbp, rdx
0x180057629  mov     rcx, [rcx]
0x18005762c  mov     ecx, [rcx]; unsigned int
0x18005762e  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x180057633  nop
0x180057634  add     rsp, 50h
0x180057638  pop     rbp
0x180057639  retn
```
