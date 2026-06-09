# WLIDCUpdateToken(void * const,_WLIDTokenParams const *,ushort * *)

- ea: `0x18004b100`
- end: `0x18004b47e`
- name: `?WLIDCUpdateToken@@YAJQEAXPEBU_WLIDTokenParams@@PEAPEAG@Z`
- size: `894`
- prototype: `__int64 __fastcall(void *const, const struct _WLIDTokenParams *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180025bbc`
- `0x180041970`

## callees

- `0x18000a400`
- `0x18000f870`
- `0x180010c68`
- `0x180011588`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180041a58`
- `0x180043240`
- `0x18004b100`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004b1f6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004b1f6`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004b2e7`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004b33c`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004b2e7`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004b33c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b209`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b34d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b209`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b34d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b3bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b3bc`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004b1af`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004b1af`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004b311`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004b311`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004b25f`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004b25f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004b375`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004b375`

## string_xrefs

- `0x18004b21b`: `RPC failed to create new event, hr = %#x`
- `0x18004b389`: `RPC Async complete call failed, hr = %#x`
- `0x18004b3d4`: `WLIDCUpdateToken`

## pseudocode

```c
__int64 __fastcall WLIDCUpdateToken(void *const a1, const struct _WLIDTokenParams *a2, unsigned __int16 **a3)
{
  __int64 result; // rax
  DWORD v6; // esi
  char v7; // r15
  char v8; // r14
  int LastError; // eax
  const unsigned __int16 *v10; // r9
  unsigned int v11; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  unsigned __int16 **v13; // rax
  DWORD v14; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-108h]
  int Reply; // [rsp+40h] [rbp-E8h] BYREF
  char v17; // [rsp+44h] [rbp-E4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-E0h] BYREF
  DWORD v19; // [rsp+4Ch] [rbp-DCh] BYREF
  __int64 v20; // [rsp+50h] [rbp-D8h] BYREF
  __int64 v21; // [rsp+58h] [rbp-D0h] BYREF
  const struct _WLIDTokenParams *v22; // [rsp+60h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+68h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+80h] [rbp-A8h] BYREF

  v22 = a2;
  v21 = 0;
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
    v11 = 1322;
LABEL_32:
    Reply = LastError;
    goto LABEL_33;
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
  v13 = (unsigned __int16 **)&v21;
  if ( a3 )
    v13 = a3;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x10u, 0, &pAsync, a1, v22, v13);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v10 = L"RPC call failed, hr = %#x";
    v11 = 1328;
LABEL_33:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v11,
      v10,
      *(_QWORD *)bAlertable);
    goto LABEL_34;
  }
  v14 = WaitForMultipleObjectsEx(1u, Handles, 0, v6, 0);
  do
  {
    if ( v8 || v14 != 258 && v14 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v14 == 258 )
      v7 = 1;
    else
      v8 = 1;
    v14 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v7 );
  if ( v14 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"Encountered error while waiting on RPC call, hr = %#x";
LABEL_31:
    v11 = 1328;
    goto LABEL_32;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_31;
  }
LABEL_34:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v7 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[17],unsigned long &>("WLIDCUpdateToken", &v19);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x530u,
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
      0x530u,
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
0x18004b100  push    rsi
0x18004b102  push    r12
0x18004b104  push    r13
0x18004b106  push    r14
0x18004b108  push    r15
0x18004b10a  sub     rsp, 100h
0x18004b111  mov     rax, cs:__security_cookie
0x18004b118  xor     rax, rsp
0x18004b11b  mov     [rsp+128h+var_38], rax
0x18004b123  mov     r12, r8
0x18004b126  mov     [rsp+128h+var_C8], rdx
0x18004b12b  mov     r13, rcx
0x18004b12e  mov     [rsp+128h+var_D0], 0
0x18004b137  mov     [rsp+128h+dwMilliseconds], 0
0x18004b13f  lea     r8, [rsp+128h+dwMilliseconds]; unsigned int *
0x18004b144  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004b149  mov     [rsp+128h+Reply], 0
0x18004b151  mov     [rsp+128h+var_D8], 0
0x18004b15a  lea     rcx, [rsp+128h+var_D8]; this
0x18004b15f  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18004b164  mov     [rsp+128h+Reply], eax
0x18004b168  test    eax, eax
0x18004b16a  js      loc_18004B45D
0x18004b170  xor     edx, edx; Val
0x18004b172  lea     r8d, [rdx+70h]; Size
0x18004b176  lea     rcx, [rsp+128h+pAsync]; void *
0x18004b17e  call    memset_0
0x18004b183  mov     esi, [rsp+128h+dwMilliseconds]
0x18004b187  mov     [rsp+128h+dwMilliseconds], esi
0x18004b18b  mov     [rsp+128h+var_DC], esi
0x18004b18f  xor     r15b, r15b
0x18004b192  mov     [rsp+128h+var_E4], r15b
0x18004b197  xor     r14b, r14b
0x18004b19a  xorps   xmm0, xmm0
0x18004b19d  movups  xmmword ptr [rsp+128h+Handles], xmm0
0x18004b1a2  mov     edx, 70h ; 'p'; Size
0x18004b1a7  lea     rcx, [rsp+128h+pAsync]; pAsync
0x18004b1af  call    cs:__imp_RpcAsyncInitializeHandle
0x18004b1b5  test    eax, eax
0x18004b1b7  jz      short loc_18004B1D5
0x18004b1b9  jle     short loc_18004B1C3
0x18004b1bb  movzx   eax, ax
0x18004b1be  or      eax, 80070000h
0x18004b1c3  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004b1ca  mov     r8d, 52Ah
0x18004b1d0  jmp     loc_18004B396
0x18004b1d5  mov     [rsp+128h+pAsync.UserInfo], 0
0x18004b1e1  mov     [rsp+128h+pAsync.NotificationType], 1
0x18004b1ec  xor     r9d, r9d; lpName
0x18004b1ef  xor     r8d, r8d; bInitialState
0x18004b1f2  xor     edx, edx; bManualReset
0x18004b1f4  xor     ecx, ecx; lpEventAttributes
0x18004b1f6  call    cs:__imp_CreateEventW
0x18004b1fc  mov     qword ptr [rsp+128h+pAsync.u], rax
0x18004b204  test    rax, rax
0x18004b207  jnz     short loc_18004B224
0x18004b209  call    cs:__imp_GetLastError
0x18004b20f  test    eax, eax
0x18004b211  jle     short loc_18004B21B
0x18004b213  movzx   eax, ax
0x18004b216  or      eax, 80070000h
0x18004b21b  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004b222  jmp     short loc_18004B1CA
0x18004b224  mov     [rsp+128h+Handles], rax
0x18004b229  lea     rax, [rsp+128h+var_D0]
0x18004b22e  test    r12, r12
0x18004b231  cmovnz  rax, r12
0x18004b235  mov     [rsp+128h+var_F8], rax
0x18004b23a  mov     rax, [rsp+128h+var_C8]
0x18004b23f  mov     [rsp+128h+var_100], rax
0x18004b244  mov     qword ptr [rsp+128h+bAlertable], r13
0x18004b249  lea     r9, [rsp+128h+pAsync]
0x18004b251  xor     r8d, r8d; pReturnValue
0x18004b254  lea     edx, [r8+10h]; nProcNum
0x18004b258  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004b25f  call    cs:__imp_Ndr64AsyncClientCall
0x18004b265  mov     eax, [rsp+128h+Reply]
0x18004b269  jmp     short loc_18004B2BA
0x18004b26b  test    eax, eax
0x18004b26d  jle     short loc_18004B277
0x18004b26f  movzx   eax, ax
0x18004b272  or      eax, 80070000h
0x18004b277  mov     [rsp+128h+Reply], eax
0x18004b27b  mov     [rsp+128h+bAlertable], eax
0x18004b27f  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004b286  mov     r8d, 530h; unsigned int
0x18004b28c  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004b293  mov     ecx, 2; unsigned __int8
0x18004b298  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004b29d  mov     eax, [rsp+128h+Reply]
0x18004b2a1  test    eax, eax
0x18004b2a3  js      short loc_18004B2AE
0x18004b2a5  mov     eax, 8000FFFFh
0x18004b2aa  mov     [rsp+128h+Reply], eax
0x18004b2ae  mov     esi, [rsp+128h+dwMilliseconds]
0x18004b2b2  mov     r15b, [rsp+128h+var_E4]
0x18004b2b7  mov     r14b, r15b
0x18004b2ba  test    eax, eax
0x18004b2bc  jns     short loc_18004B2D0
0x18004b2be  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004b2c5  mov     r8d, 530h
0x18004b2cb  jmp     loc_18004B39A
0x18004b2d0  mov     [rsp+128h+bAlertable], 0; bAlertable
0x18004b2d8  mov     r9d, esi; dwMilliseconds
0x18004b2db  xor     r8d, r8d; bWaitAll
0x18004b2de  lea     rdx, [rsp+128h+Handles]; lpHandles
0x18004b2e3  lea     ecx, [r8+1]; nCount
0x18004b2e7  call    cs:__imp_WaitForMultipleObjectsEx
0x18004b2ed  mov     esi, eax
0x18004b2ef  mov     r12d, 102h
0x18004b2f5  test    r14b, r14b
0x18004b2f8  jnz     short loc_18004B349
0x18004b2fa  cmp     esi, r12d
0x18004b2fd  jz      short loc_18004B304
0x18004b2ff  cmp     esi, 1
0x18004b302  jnz     short loc_18004B349
0x18004b304  mov     edx, 1; fAbort
0x18004b309  lea     rcx, [rsp+128h+pAsync]; pAsync
0x18004b311  call    cs:__imp_RpcAsyncCancelCall
0x18004b317  cmp     esi, r12d
0x18004b31a  jnz     short loc_18004B321
0x18004b31c  mov     r15b, 1
0x18004b31f  jmp     short loc_18004B324
0x18004b321  mov     r14b, 1
0x18004b324  mov     [rsp+128h+bAlertable], 0; bAlertable
0x18004b32c  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004b330  xor     r8d, r8d; bWaitAll
0x18004b333  lea     rdx, [rsp+128h+Handles]; lpHandles
0x18004b338  lea     ecx, [r8+1]; nCount
0x18004b33c  call    cs:__imp_WaitForMultipleObjectsEx
0x18004b342  mov     esi, eax
0x18004b344  test    r15b, r15b
0x18004b347  jz      short loc_18004B2F5
0x18004b349  test    esi, esi
0x18004b34b  jz      short loc_18004B368
0x18004b34d  call    cs:__imp_GetLastError
0x18004b353  test    eax, eax
0x18004b355  jle     short loc_18004B35F
0x18004b357  movzx   eax, ax
0x18004b35a  or      eax, 80070000h
0x18004b35f  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004b366  jmp     short loc_18004B390
0x18004b368  lea     rdx, [rsp+128h+Reply]; Reply
0x18004b36d  lea     rcx, [rsp+128h+pAsync]; pAsync
0x18004b375  call    cs:__imp_RpcAsyncCompleteCall
0x18004b37b  test    eax, eax
0x18004b37d  jz      short loc_18004B3AF
0x18004b37f  jle     short loc_18004B389
0x18004b381  movzx   eax, ax
0x18004b384  or      eax, 80070000h
0x18004b389  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004b390  mov     r8d, 530h; unsigned int
0x18004b396  mov     [rsp+128h+Reply], eax
0x18004b39a  mov     [rsp+128h+bAlertable], eax
0x18004b39e  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004b3a5  mov     ecx, 2; unsigned __int8
0x18004b3aa  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004b3af  mov     rcx, qword ptr [rsp+128h+pAsync.u]; hObject
0x18004b3b7  test    rcx, rcx
0x18004b3ba  jz      short loc_18004B3C2
0x18004b3bc  call    cs:__imp_CloseHandle
0x18004b3c2  test    r15b, r15b
0x18004b3c5  jz      short loc_18004B406
0x18004b3c7  mov     [rsp+128h+Reply], 800705B4h
0x18004b3cf  lea     rdx, [rsp+128h+var_DC]
0x18004b3d4  lea     rcx, aWlidcupdatetok; "WLIDCUpdateToken"
0x18004b3db  call    ??$RPCCallTimedOut@AEAY0BB@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BB@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[17],ulong &>(char const (&)[17],ulong &)
0x18004b3e0  mov     eax, [rsp+128h+Reply]
0x18004b3e4  mov     [rsp+128h+bAlertable], eax
0x18004b3e8  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004b3ef  mov     r8d, 530h; unsigned int
0x18004b3f5  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004b3fc  mov     ecx, 2; unsigned __int8
0x18004b401  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004b406  test    r14b, r14b
0x18004b409  jz      short loc_18004B436
0x18004b40b  mov     eax, 800704C7h
0x18004b410  mov     [rsp+128h+Reply], eax
0x18004b414  mov     [rsp+128h+bAlertable], eax
0x18004b418  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004b41f  mov     r8d, 530h; unsigned int
0x18004b425  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004b42c  mov     ecx, 2; unsigned __int8
0x18004b431  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004b436  cmp     [rsp+128h+Reply], 800706B5h
0x18004b43e  jz      short loc_18004B44A
0x18004b440  cmp     [rsp+128h+Reply], 800706BAh
0x18004b448  jnz     short loc_18004B44F
0x18004b44a  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004b44f  lea     rcx, [rsp+128h+var_D8]; this
0x18004b454  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18004b459  mov     eax, [rsp+128h+Reply]
0x18004b45d  mov     rcx, [rsp+128h+var_38]
0x18004b465  xor     rcx, rsp; StackCookie
0x18004b468  call    __security_check_cookie
0x18004b46d  add     rsp, 100h
0x18004b474  pop     r15
0x18004b476  pop     r14
0x18004b478  pop     r13
0x18004b47a  pop     r12
0x18004b47c  pop     rsi
0x18004b47d  retn
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
