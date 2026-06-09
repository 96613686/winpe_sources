# WLIDCGetOneTimeCredential(void * const,unsigned __int64,ushort const *,ushort const *,ushort const *,ushort const *,ushort * *,ushort * *)

- ea: `0x18004bf2c`
- end: `0x18004c2f9`
- name: `?WLIDCGetOneTimeCredential@@YAJQEAX_KPEBG222PEAPEAG3@Z`
- size: `973`
- prototype: `__int64 __fastcall(void *const, unsigned __int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800306c0`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x1800451f4`
- `0x180046ce0`
- `0x18004bf2c`
- `0x18004cd04`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004c16b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004c1c3`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004c16b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004c1c3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004c042`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004c042`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c055`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c1d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c055`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c1d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c243`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c243`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004c195`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004c195`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004c0e0`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004c0e0`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004c1fc`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004c1fc`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004bffb`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004bffb`

## string_xrefs

- `0x18004c067`: `RPC failed to create new event, hr = %#x`
- `0x18004c210`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCGetOneTimeCredential(
        void *const a1,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        unsigned __int16 **a7,
        unsigned __int16 **a8)
{
  DWORD v10; // esi
  char v11; // r15
  char v12; // r14
  int LastError; // eax
  const unsigned __int16 *v14; // r9
  unsigned int v15; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v17; // esi
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-138h]
  unsigned int Reply; // [rsp+60h] [rbp-F8h] BYREF
  char v21; // [rsp+64h] [rbp-F4h]
  DWORD dwMilliseconds; // [rsp+68h] [rbp-F0h] BYREF
  DWORD v23; // [rsp+6Ch] [rbp-ECh] BYREF
  unsigned __int16 **v24; // [rsp+70h] [rbp-E8h]
  unsigned __int16 **v25; // [rsp+78h] [rbp-E0h]
  const unsigned __int16 *v26; // [rsp+80h] [rbp-D8h]
  const unsigned __int16 *v27; // [rsp+88h] [rbp-D0h]
  const unsigned __int16 *v28; // [rsp+90h] [rbp-C8h]
  const unsigned __int16 *v29; // [rsp+98h] [rbp-C0h]
  HANDLE Handles[2]; // [rsp+A0h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+B0h] [rbp-A8h] BYREF

  v28 = a4;
  v29 = a3;
  v27 = a5;
  v26 = a6;
  v25 = a7;
  v24 = a8;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v10 = dwMilliseconds;
  v23 = dwMilliseconds;
  v11 = 0;
  v21 = 0;
  v12 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v14 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v15 = 1128;
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
    v14 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_5;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall(
    (MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo,
    0x39u,
    0,
    &pAsync,
    a1,
    a2,
    v29,
    v28,
    v27,
    v26,
    v25,
    v24);
  v17 = WaitForMultipleObjectsEx(1u, Handles, 0, v10, 0);
  do
  {
    if ( v12 || v17 != 258 && v17 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v17 == 258 )
      v11 = 1;
    else
      v12 = 1;
    v17 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v11 );
  if ( v17 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v14 = L"Encountered error while waiting on RPC call, hr = %#x";
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_28;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v14 = L"RPC Async complete call failed, hr = %#x";
  }
  v15 = 1130;
LABEL_27:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(
    2u,
    "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
    v15,
    v14,
    *(_QWORD *)bAlertable);
LABEL_28:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v11 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[26],unsigned long &>(
      (__int64)"WLIDCGetOneTimeCredential",
      (int *)&v23);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x46Au,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v12 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x46Au,
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
0x18004bf2c  push    rsi
0x18004bf2e  push    r12
0x18004bf30  push    r13
0x18004bf32  push    r14
0x18004bf34  push    r15
0x18004bf36  sub     rsp, 130h
0x18004bf3d  mov     rax, cs:__security_cookie
0x18004bf44  xor     rax, rsp
0x18004bf47  mov     [rsp+158h+var_38], rax
0x18004bf4f  mov     [rsp+158h+var_C8], r9
0x18004bf57  mov     [rsp+158h+var_C0], r8
0x18004bf5f  mov     r13, rdx
0x18004bf62  mov     r12, rcx
0x18004bf65  mov     rax, [rsp+158h+arg_20]
0x18004bf6d  mov     [rsp+158h+var_D0], rax
0x18004bf75  mov     rax, [rsp+158h+arg_28]
0x18004bf7d  mov     [rsp+158h+var_D8], rax
0x18004bf85  mov     rax, [rsp+158h+arg_30]
0x18004bf8d  mov     [rsp+158h+var_E0], rax
0x18004bf92  mov     rax, [rsp+158h+arg_38]
0x18004bf9a  mov     [rsp+158h+var_E8], rax
0x18004bf9f  mov     [rsp+158h+Reply], 0
0x18004bfa7  mov     [rsp+158h+dwMilliseconds], 0
0x18004bfaf  lea     r8, [rsp+158h+dwMilliseconds]; unsigned int *
0x18004bfb4  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004bfb9  xor     edx, edx; Val
0x18004bfbb  lea     r8d, [rdx+70h]; Size
0x18004bfbf  lea     rcx, [rsp+158h+pAsync]; void *
0x18004bfc7  call    memset_0
0x18004bfcc  mov     esi, [rsp+158h+dwMilliseconds]
0x18004bfd0  mov     [rsp+158h+dwMilliseconds], esi
0x18004bfd4  mov     [rsp+158h+var_EC], esi
0x18004bfd8  xor     r15b, r15b
0x18004bfdb  mov     [rsp+158h+var_F4], r15b
0x18004bfe0  xor     r14b, r14b
0x18004bfe3  xorps   xmm0, xmm0
0x18004bfe6  movups  xmmword ptr [rsp+158h+Handles], xmm0
0x18004bfee  mov     edx, 70h ; 'p'; Size
0x18004bff3  lea     rcx, [rsp+158h+pAsync]; pAsync
0x18004bffb  call    cs:__imp_RpcAsyncInitializeHandle
0x18004c001  test    eax, eax
0x18004c003  jz      short loc_18004C021
0x18004c005  jle     short loc_18004C00F
0x18004c007  movzx   eax, ax
0x18004c00a  or      eax, 80070000h
0x18004c00f  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004c016  mov     r8d, 468h
0x18004c01c  jmp     loc_18004C21D
0x18004c021  mov     [rsp+158h+pAsync.UserInfo], 0
0x18004c02d  mov     [rsp+158h+pAsync.NotificationType], 1
0x18004c038  xor     r9d, r9d; lpName
0x18004c03b  xor     r8d, r8d; bInitialState
0x18004c03e  xor     edx, edx; bManualReset
0x18004c040  xor     ecx, ecx; lpEventAttributes
0x18004c042  call    cs:__imp_CreateEventW
0x18004c048  mov     qword ptr [rsp+158h+pAsync.u], rax
0x18004c050  test    rax, rax
0x18004c053  jnz     short loc_18004C070
0x18004c055  call    cs:__imp_GetLastError
0x18004c05b  test    eax, eax
0x18004c05d  jle     short loc_18004C067
0x18004c05f  movzx   eax, ax
0x18004c062  or      eax, 80070000h
0x18004c067  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004c06e  jmp     short loc_18004C016
0x18004c070  mov     [rsp+158h+Handles], rax
0x18004c078  mov     rax, [rsp+158h+var_E8]
0x18004c07d  mov     [rsp+158h+var_100], rax
0x18004c082  mov     rax, [rsp+158h+var_E0]
0x18004c087  mov     [rsp+158h+var_108], rax
0x18004c08c  mov     rax, [rsp+158h+var_D8]
0x18004c094  mov     [rsp+158h+var_110], rax
0x18004c099  mov     rax, [rsp+158h+var_D0]
0x18004c0a1  mov     [rsp+158h+var_118], rax
0x18004c0a6  mov     rax, [rsp+158h+var_C8]
0x18004c0ae  mov     [rsp+158h+var_120], rax
0x18004c0b3  mov     rax, [rsp+158h+var_C0]
0x18004c0bb  mov     [rsp+158h+var_128], rax
0x18004c0c0  mov     [rsp+158h+var_130], r13
0x18004c0c5  mov     qword ptr [rsp+158h+bAlertable], r12
0x18004c0ca  lea     r9, [rsp+158h+pAsync]
0x18004c0d2  xor     r8d, r8d; pReturnValue
0x18004c0d5  lea     edx, [r8+39h]; nProcNum
0x18004c0d9  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004c0e0  call    cs:__imp_Ndr64AsyncClientCall
0x18004c0e6  mov     eax, [rsp+158h+Reply]
0x18004c0ea  jmp     short loc_18004C13B
0x18004c0ec  test    eax, eax
0x18004c0ee  jle     short loc_18004C0F8
0x18004c0f0  movzx   eax, ax
0x18004c0f3  or      eax, 80070000h
0x18004c0f8  mov     [rsp+158h+Reply], eax
0x18004c0fc  mov     [rsp+158h+bAlertable], eax
0x18004c100  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004c107  mov     r8d, 46Ah; unsigned int
0x18004c10d  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004c114  mov     ecx, 2; unsigned __int8
0x18004c119  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004c11e  mov     eax, [rsp+158h+Reply]
0x18004c122  test    eax, eax
0x18004c124  js      short loc_18004C12F
0x18004c126  mov     eax, 8000FFFFh
0x18004c12b  mov     [rsp+158h+Reply], eax
0x18004c12f  mov     esi, [rsp+158h+dwMilliseconds]
0x18004c133  mov     r15b, [rsp+158h+var_F4]
0x18004c138  mov     r14b, r15b
0x18004c13b  test    eax, eax
0x18004c13d  jns     short loc_18004C151
0x18004c13f  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004c146  mov     r8d, 46Ah
0x18004c14c  jmp     loc_18004C221
0x18004c151  mov     [rsp+158h+bAlertable], 0; bAlertable
0x18004c159  mov     r9d, esi; dwMilliseconds
0x18004c15c  xor     r8d, r8d; bWaitAll
0x18004c15f  lea     rdx, [rsp+158h+Handles]; lpHandles
0x18004c167  lea     ecx, [r8+1]; nCount
0x18004c16b  call    cs:__imp_WaitForMultipleObjectsEx
0x18004c171  mov     esi, eax
0x18004c173  mov     r12d, 102h
0x18004c179  test    r14b, r14b
0x18004c17c  jnz     short loc_18004C1D0
0x18004c17e  cmp     esi, r12d
0x18004c181  jz      short loc_18004C188
0x18004c183  cmp     esi, 1
0x18004c186  jnz     short loc_18004C1D0
0x18004c188  mov     edx, 1; fAbort
0x18004c18d  lea     rcx, [rsp+158h+pAsync]; pAsync
0x18004c195  call    cs:__imp_RpcAsyncCancelCall
0x18004c19b  cmp     esi, r12d
0x18004c19e  jnz     short loc_18004C1A5
0x18004c1a0  mov     r15b, 1
0x18004c1a3  jmp     short loc_18004C1A8
0x18004c1a5  mov     r14b, 1
0x18004c1a8  mov     [rsp+158h+bAlertable], 0; bAlertable
0x18004c1b0  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004c1b4  xor     r8d, r8d; bWaitAll
0x18004c1b7  lea     rdx, [rsp+158h+Handles]; lpHandles
0x18004c1bf  lea     ecx, [r8+1]; nCount
0x18004c1c3  call    cs:__imp_WaitForMultipleObjectsEx
0x18004c1c9  mov     esi, eax
0x18004c1cb  test    r15b, r15b
0x18004c1ce  jz      short loc_18004C179
0x18004c1d0  test    esi, esi
0x18004c1d2  jz      short loc_18004C1EF
0x18004c1d4  call    cs:__imp_GetLastError
0x18004c1da  test    eax, eax
0x18004c1dc  jle     short loc_18004C1E6
0x18004c1de  movzx   eax, ax
0x18004c1e1  or      eax, 80070000h
0x18004c1e6  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004c1ed  jmp     short loc_18004C217
0x18004c1ef  lea     rdx, [rsp+158h+Reply]; Reply
0x18004c1f4  lea     rcx, [rsp+158h+pAsync]; pAsync
0x18004c1fc  call    cs:__imp_RpcAsyncCompleteCall
0x18004c202  test    eax, eax
0x18004c204  jz      short loc_18004C236
0x18004c206  jle     short loc_18004C210
0x18004c208  movzx   eax, ax
0x18004c20b  or      eax, 80070000h
0x18004c210  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004c217  mov     r8d, 46Ah; unsigned int
0x18004c21d  mov     [rsp+158h+Reply], eax
0x18004c221  mov     [rsp+158h+bAlertable], eax
0x18004c225  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004c22c  mov     ecx, 2; unsigned __int8
0x18004c231  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004c236  mov     rcx, qword ptr [rsp+158h+pAsync.u]; hObject
0x18004c23e  test    rcx, rcx
0x18004c241  jz      short loc_18004C249
0x18004c243  call    cs:__imp_CloseHandle
0x18004c249  test    r15b, r15b
0x18004c24c  jz      short loc_18004C28D
0x18004c24e  mov     [rsp+158h+Reply], 800705B4h
0x18004c256  lea     rdx, [rsp+158h+var_EC]
0x18004c25b  lea     rcx, aWlidcgetonetim; "WLIDCGetOneTimeCredential"
0x18004c262  call    ??$RPCCallTimedOut@AEAY0BK@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BK@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[26],ulong &>(char const (&)[26],ulong &)
0x18004c267  mov     eax, [rsp+158h+Reply]
0x18004c26b  mov     [rsp+158h+bAlertable], eax
0x18004c26f  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004c276  mov     r8d, 46Ah; unsigned int
0x18004c27c  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004c283  mov     ecx, 2; unsigned __int8
0x18004c288  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004c28d  test    r14b, r14b
0x18004c290  jz      short loc_18004C2BD
0x18004c292  mov     eax, 800704C7h
0x18004c297  mov     [rsp+158h+Reply], eax
0x18004c29b  mov     [rsp+158h+bAlertable], eax
0x18004c29f  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004c2a6  mov     r8d, 46Ah; unsigned int
0x18004c2ac  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004c2b3  mov     ecx, 2; unsigned __int8
0x18004c2b8  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004c2bd  mov     eax, [rsp+158h+Reply]
0x18004c2c1  cmp     eax, 800706B5h
0x18004c2c6  jz      short loc_18004C2CF
0x18004c2c8  cmp     eax, 800706BAh
0x18004c2cd  jnz     short loc_18004C2D8
0x18004c2cf  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004c2d4  mov     eax, [rsp+158h+Reply]
0x18004c2d8  mov     rcx, [rsp+158h+var_38]
0x18004c2e0  xor     rcx, rsp; StackCookie
0x18004c2e3  call    __security_check_cookie
0x18004c2e8  add     rsp, 130h
0x18004c2ef  pop     r15
0x18004c2f1  pop     r14
0x18004c2f3  pop     r13
0x18004c2f5  pop     r12
0x18004c2f7  pop     rsi
0x18004c2f8  retn
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
