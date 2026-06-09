# WLIDCCreateContextEx(ushort const *,ushort const *,unsigned __int64,void * *)

- ea: `0x18000de3c`
- end: `0x18000e1ba`
- name: `?WLIDCCreateContextEx@@YAJPEBG0_KPEAPEAX@Z`
- size: `894`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, __int64, void **)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180007b00`
- `0x18000a3e8`

## callees

- `0x1800027f0`
- `0x1800033b4`
- `0x18000c47c`
- `0x18000dc00`
- `0x18000dd84`
- `0x18000de3c`
- `0x18000e85c`
- `0x18000ee14`
- `0x18000efd0`
- `0x18000f4cc`
- `0x18000fe90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000e020`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000e075`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000e020`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000e075`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000df1f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000df1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e086`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e086`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e0f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e0f5`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000e0ae`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000e0ae`
- `RPCRT4!RpcAsyncCancelCall` at `0x18000e04a`
- `RPCRT4!RpcAsyncCancelCall` at `0x18000e04a`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18000df98`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18000df98`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18000ded8`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18000ded8`

## string_xrefs

- `0x18000df44`: `RPC failed to create new event, hr = %#x`
- `0x18000e0c2`: `RPC Async complete call failed, hr = %#x`
- `0x18000e10d`: `WLIDCCreateContextEx`

## pseudocode

```c
__int64 __fastcall WLIDCCreateContextEx(const unsigned __int16 *a1, const unsigned __int16 *a2, __int64 a3, void **a4)
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
  const char *v14; // rdx
  BOOL bAlertable[2]; // [rsp+20h] [rbp-108h]
  signed int Reply; // [rsp+50h] [rbp-D8h] BYREF
  char v17; // [rsp+54h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+58h] [rbp-D0h] BYREF
  DWORD v19; // [rsp+5Ch] [rbp-CCh] BYREF
  __int64 v20; // [rsp+60h] [rbp-C8h] BYREF
  HANDLE Handles[3]; // [rsp+68h] [rbp-C0h] BYREF
  _RPC_ASYNC_STATE pAsync; // [rsp+80h] [rbp-A8h] BYREF

  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
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
    v11 = 574;
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
  Ndr64AsyncClientCall(
    (MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo,
    0xAu,
    0,
    &pAsync,
    v20,
    byte_180017D50,
    L"{74e888b9-d499-4e2b-a5fc-031f2407d02e}",
    0x800000,
    a4);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v10 = L"RPC call failed, hr = %#x";
    v11 = 576;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      (PPTraceStatus *)2,
      (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
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
    v11 = 576;
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
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v7 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],unsigned long &>(
      (__int64)"WLIDCCreateContextEx",
      (int *)&v19);
    bAlertable[0] = Reply;
    TracePrintW(
      (PPTraceStatus *)2,
      (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x240u,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v8 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      (PPTraceStatus *)2,
      (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x240u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v20);
  return TranslateRpcServiceError(Reply, v14);
}

```

## disassembly

```asm
0x18000de3c  push    rsi
0x18000de3e  push    r12
0x18000de40  push    r14
0x18000de42  push    r15
0x18000de44  sub     rsp, 108h
0x18000de4b  mov     rax, cs:__security_cookie
0x18000de52  xor     rax, rsp
0x18000de55  mov     [rsp+128h+var_38], rax
0x18000de5d  mov     r12, r9
0x18000de60  mov     [rsp+128h+dwMilliseconds], 0
0x18000de68  lea     r8, [rsp+128h+dwMilliseconds]; unsigned int *
0x18000de6d  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18000de72  mov     [rsp+128h+Reply], 0
0x18000de7a  mov     [rsp+128h+var_C8], 0
0x18000de83  lea     rcx, [rsp+128h+var_C8]; this
0x18000de88  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18000de8d  mov     [rsp+128h+Reply], eax
0x18000de91  test    eax, eax
0x18000de93  js      loc_18000E19B
0x18000de99  xor     edx, edx; Val
0x18000de9b  lea     r8d, [rdx+70h]; Size
0x18000de9f  lea     rcx, [rsp+128h+pAsync]; void *
0x18000dea7  call    memset_0
0x18000deac  mov     esi, [rsp+128h+dwMilliseconds]
0x18000deb0  mov     [rsp+128h+dwMilliseconds], esi
0x18000deb4  mov     [rsp+128h+var_CC], esi
0x18000deb8  xor     r15b, r15b
0x18000debb  mov     [rsp+128h+var_D4], r15b
0x18000dec0  xor     r14b, r14b
0x18000dec3  xorps   xmm0, xmm0
0x18000dec6  movups  xmmword ptr [rsp+128h+Handles], xmm0
0x18000decb  mov     edx, 70h ; 'p'; Size
0x18000ded0  lea     rcx, [rsp+128h+pAsync]; pAsync
0x18000ded8  call    cs:__imp_RpcAsyncInitializeHandle
0x18000dede  test    eax, eax
0x18000dee0  jz      short loc_18000DEFE
0x18000dee2  jle     short loc_18000DEEC
0x18000dee4  movzx   eax, ax
0x18000dee7  or      eax, 80070000h
0x18000deec  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18000def3  mov     r8d, 23Eh
0x18000def9  jmp     loc_18000E0CF
0x18000defe  mov     [rsp+128h+pAsync.UserInfo], 0
0x18000df0a  mov     [rsp+128h+pAsync.NotificationType], 1
0x18000df15  xor     r9d, r9d; lpName
0x18000df18  xor     r8d, r8d; bInitialState
0x18000df1b  xor     edx, edx; bManualReset
0x18000df1d  xor     ecx, ecx; lpEventAttributes
0x18000df1f  call    cs:__imp_CreateEventW
0x18000df25  mov     qword ptr [rsp+128h+pAsync.u], rax
0x18000df2d  test    rax, rax
0x18000df30  jnz     short loc_18000DF4D
0x18000df32  call    cs:__imp_GetLastError
0x18000df38  test    eax, eax
0x18000df3a  jle     short loc_18000DF44
0x18000df3c  movzx   eax, ax
0x18000df3f  or      eax, 80070000h
0x18000df44  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18000df4b  jmp     short loc_18000DEF3
0x18000df4d  mov     [rsp+128h+Handles], rax
0x18000df52  mov     [rsp+128h+var_E8], r12
0x18000df57  mov     [rsp+128h+var_F0], 800000h
0x18000df60  lea     rax, a74e888b9D4994e; "{74e888b9-d499-4e2b-a5fc-031f2407d02e}"
0x18000df67  mov     [rsp+128h+var_F8], rax
0x18000df6c  lea     rax, byte_180017D50
0x18000df73  mov     [rsp+128h+var_100], rax
0x18000df78  mov     rax, [rsp+128h+var_C8]
0x18000df7d  mov     qword ptr [rsp+128h+bAlertable], rax
0x18000df82  lea     r9, [rsp+128h+pAsync]
0x18000df8a  xor     r8d, r8d; pReturnValue
0x18000df8d  lea     edx, [r8+0Ah]; nProcNum
0x18000df91  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000df98  call    cs:__imp_Ndr64AsyncClientCall
0x18000df9e  mov     eax, [rsp+128h+Reply]
0x18000dfa2  jmp     short loc_18000DFF3
0x18000dfa4  test    eax, eax
0x18000dfa6  jle     short loc_18000DFB0
0x18000dfa8  movzx   eax, ax
0x18000dfab  or      eax, 80070000h
0x18000dfb0  mov     [rsp+128h+Reply], eax
0x18000dfb4  mov     [rsp+128h+bAlertable], eax
0x18000dfb8  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18000dfbf  mov     r8d, 240h; unsigned int
0x18000dfc5  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000dfcc  mov     ecx, 2; unsigned __int8
0x18000dfd1  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000dfd6  mov     eax, [rsp+128h+Reply]
0x18000dfda  test    eax, eax
0x18000dfdc  js      short loc_18000DFE7
0x18000dfde  mov     eax, 8000FFFFh
0x18000dfe3  mov     [rsp+128h+Reply], eax
0x18000dfe7  mov     esi, [rsp+128h+dwMilliseconds]
0x18000dfeb  mov     r15b, [rsp+128h+var_D4]
0x18000dff0  mov     r14b, r15b
0x18000dff3  test    eax, eax
0x18000dff5  jns     short loc_18000E009
0x18000dff7  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18000dffe  mov     r8d, 240h
0x18000e004  jmp     loc_18000E0D3
0x18000e009  mov     [rsp+128h+bAlertable], 0; bAlertable
0x18000e011  mov     r9d, esi; dwMilliseconds
0x18000e014  xor     r8d, r8d; bWaitAll
0x18000e017  lea     rdx, [rsp+128h+Handles]; lpHandles
0x18000e01c  lea     ecx, [r8+1]; nCount
0x18000e020  call    cs:__imp_WaitForMultipleObjectsEx
0x18000e026  mov     esi, eax
0x18000e028  mov     r12d, 102h
0x18000e02e  test    r14b, r14b
0x18000e031  jnz     short loc_18000E082
0x18000e033  cmp     esi, r12d
0x18000e036  jz      short loc_18000E03D
0x18000e038  cmp     esi, 1
0x18000e03b  jnz     short loc_18000E082
0x18000e03d  mov     edx, 1; fAbort
0x18000e042  lea     rcx, [rsp+128h+pAsync]; pAsync
0x18000e04a  call    cs:__imp_RpcAsyncCancelCall
0x18000e050  cmp     esi, r12d
0x18000e053  jnz     short loc_18000E05A
0x18000e055  mov     r15b, 1
0x18000e058  jmp     short loc_18000E05D
0x18000e05a  mov     r14b, 1
0x18000e05d  mov     [rsp+128h+bAlertable], 0; bAlertable
0x18000e065  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18000e069  xor     r8d, r8d; bWaitAll
0x18000e06c  lea     rdx, [rsp+128h+Handles]; lpHandles
0x18000e071  lea     ecx, [r8+1]; nCount
0x18000e075  call    cs:__imp_WaitForMultipleObjectsEx
0x18000e07b  mov     esi, eax
0x18000e07d  test    r15b, r15b
0x18000e080  jz      short loc_18000E02E
0x18000e082  test    esi, esi
0x18000e084  jz      short loc_18000E0A1
0x18000e086  call    cs:__imp_GetLastError
0x18000e08c  test    eax, eax
0x18000e08e  jle     short loc_18000E098
0x18000e090  movzx   eax, ax
0x18000e093  or      eax, 80070000h
0x18000e098  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18000e09f  jmp     short loc_18000E0C9
0x18000e0a1  lea     rdx, [rsp+128h+Reply]; Reply
0x18000e0a6  lea     rcx, [rsp+128h+pAsync]; pAsync
0x18000e0ae  call    cs:__imp_RpcAsyncCompleteCall
0x18000e0b4  test    eax, eax
0x18000e0b6  jz      short loc_18000E0E8
0x18000e0b8  jle     short loc_18000E0C2
0x18000e0ba  movzx   eax, ax
0x18000e0bd  or      eax, 80070000h
0x18000e0c2  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18000e0c9  mov     r8d, 240h; unsigned int
0x18000e0cf  mov     [rsp+128h+Reply], eax
0x18000e0d3  mov     [rsp+128h+bAlertable], eax
0x18000e0d7  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000e0de  mov     ecx, 2; unsigned __int8
0x18000e0e3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000e0e8  mov     rcx, qword ptr [rsp+128h+pAsync.u]; hObject
0x18000e0f0  test    rcx, rcx
0x18000e0f3  jz      short loc_18000E0FB
0x18000e0f5  call    cs:__imp_CloseHandle
0x18000e0fb  test    r15b, r15b
0x18000e0fe  jz      short loc_18000E13F
0x18000e100  mov     [rsp+128h+Reply], 800705B4h
0x18000e108  lea     rdx, [rsp+128h+var_CC]
0x18000e10d  lea     rcx, aWlidccreatecon; "WLIDCCreateContextEx"
0x18000e114  call    ??$RPCCallTimedOut@AEAY0BF@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BF@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],ulong &>(char const (&)[21],ulong &)
0x18000e119  mov     eax, [rsp+128h+Reply]
0x18000e11d  mov     [rsp+128h+bAlertable], eax
0x18000e121  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18000e128  mov     r8d, 240h; unsigned int
0x18000e12e  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000e135  mov     ecx, 2; unsigned __int8
0x18000e13a  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000e13f  test    r14b, r14b
0x18000e142  jz      short loc_18000E16F
0x18000e144  mov     eax, 800704C7h
0x18000e149  mov     [rsp+128h+Reply], eax
0x18000e14d  mov     [rsp+128h+bAlertable], eax
0x18000e151  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18000e158  mov     r8d, 240h; unsigned int
0x18000e15e  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000e165  mov     ecx, 2; unsigned __int8
0x18000e16a  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000e16f  cmp     [rsp+128h+Reply], 800706B5h
0x18000e177  jz      short loc_18000E183
0x18000e179  cmp     [rsp+128h+Reply], 800706BAh
0x18000e181  jnz     short loc_18000E188
0x18000e183  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18000e188  lea     rcx, [rsp+128h+var_C8]; this
0x18000e18d  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18000e192  mov     ecx, [rsp+128h+Reply]; int
0x18000e196  call    ?TranslateRpcServiceError@@YAJJPEBD@Z; TranslateRpcServiceError(long,char const *)
0x18000e19b  mov     rcx, [rsp+128h+var_38]
0x18000e1a3  xor     rcx, rsp; StackCookie
0x18000e1a6  call    __security_check_cookie
0x18000e1ab  add     rsp, 108h
0x18000e1b2  pop     r15
0x18000e1b4  pop     r14
0x18000e1b6  pop     r12
0x18000e1b8  pop     rsi
0x18000e1b9  retn
0x180011321  push    rbp
0x180011323  sub     rsp, 50h
0x180011327  mov     rbp, rdx
0x18001132a  mov     rcx, [rcx]
0x18001132d  mov     ecx, [rcx]; unsigned int
0x18001132f  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x180011334  nop
0x180011335  add     rsp, 50h
0x180011339  pop     rbp
0x18001133a  retn
```
