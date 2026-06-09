# WLIDCGetScenarioInlineUrlWithContextData(ulong,ushort * *)

- ea: `0x18004789c`
- end: `0x180047bf9`
- name: `?WLIDCGetScenarioInlineUrlWithContextData@@YAJKPEAPEAG@Z`
- size: `861`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800417f0`

## callees

- `0x18000a400`
- `0x18000f870`
- `0x180010c68`
- `0x180011588`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x1800422fc`
- `0x180043240`
- `0x18004789c`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180047984`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180047984`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180047a66`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180047ab8`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180047a66`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180047ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047ac9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047ac9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047b35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047b35`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004793d`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004793d`
- `RPCRT4!RpcAsyncCancelCall` at `0x180047a8d`
- `RPCRT4!RpcAsyncCancelCall` at `0x180047a8d`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800479de`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800479de`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180047aee`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180047aee`

## string_xrefs

- `0x1800479a9`: `RPC failed to create new event, hr = %#x`
- `0x180047b02`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCGetScenarioInlineUrlWithContextData(unsigned int a1, unsigned __int16 **a2)
{
  __int64 result; // rax
  DWORD v5; // esi
  char v6; // r15
  char v7; // r14
  int LastError; // eax
  const unsigned __int16 *v9; // r9
  unsigned int v10; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v12; // esi
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  BOOL bAlertable[2]; // [rsp+20h] [rbp-E8h]
  int Reply; // [rsp+40h] [rbp-C8h] BYREF
  char v16; // [rsp+44h] [rbp-C4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-C0h] BYREF
  DWORD v18; // [rsp+4Ch] [rbp-BCh] BYREF
  __int64 v19; // [rsp+50h] [rbp-B8h] BYREF
  HANDLE Handles[3]; // [rsp+58h] [rbp-B0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-98h] BYREF

  dwMilliseconds = 0;
  WLIDCGetTimeOutValue(a1, (unsigned int)a2, &dwMilliseconds);
  v19 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v19);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v5 = dwMilliseconds;
  v18 = dwMilliseconds;
  v6 = 0;
  v16 = 0;
  v7 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v10 = 1469;
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
    v9 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x47u, 0, &pAsync, v19, a1, a2);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v9 = L"RPC call failed, hr = %#x";
    v10 = 1475;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v10,
      v9,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
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
LABEL_29:
    v10 = 1475;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  NotificationRoutine = pAsync.u.APC.NotificationRoutine;
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v6 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[41],unsigned long &>(NotificationRoutine, &v18);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x5C3u,
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
      0x5C3u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v19);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x18004789c  mov     [rsp+arg_10], rsi
0x1800478a1  mov     [rsp+arg_18], r12
0x1800478a6  push    r13
0x1800478a8  push    r14
0x1800478aa  push    r15
0x1800478ac  sub     rsp, 0F0h
0x1800478b3  mov     rax, cs:__security_cookie
0x1800478ba  xor     rax, rsp
0x1800478bd  mov     [rsp+108h+var_28], rax
0x1800478c5  mov     r13, rdx
0x1800478c8  mov     r12d, ecx
0x1800478cb  mov     [rsp+108h+dwMilliseconds], 0
0x1800478d3  lea     r8, [rsp+108h+dwMilliseconds]; unsigned int *
0x1800478d8  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x1800478dd  mov     [rsp+108h+Reply], 0
0x1800478e5  mov     [rsp+108h+var_B8], 0
0x1800478ee  lea     rcx, [rsp+108h+var_B8]; this
0x1800478f3  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x1800478f8  mov     [rsp+108h+Reply], eax
0x1800478fc  test    eax, eax
0x1800478fe  js      loc_180047BCF
0x180047904  xor     edx, edx; Val
0x180047906  lea     r8d, [rdx+70h]; Size
0x18004790a  lea     rcx, [rsp+108h+pAsync]; void *
0x18004790f  call    memset_0
0x180047914  mov     esi, [rsp+108h+dwMilliseconds]
0x180047918  mov     [rsp+108h+dwMilliseconds], esi
0x18004791c  mov     [rsp+108h+var_BC], esi
0x180047920  xor     r15b, r15b
0x180047923  mov     [rsp+108h+var_C4], r15b
0x180047928  xor     r14b, r14b
0x18004792b  xorps   xmm0, xmm0
0x18004792e  movups  xmmword ptr [rsp+108h+Handles], xmm0
0x180047933  mov     edx, 70h ; 'p'; Size
0x180047938  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004793d  call    cs:__imp_RpcAsyncInitializeHandle
0x180047943  test    eax, eax
0x180047945  jz      short loc_180047963
0x180047947  jle     short loc_180047951
0x180047949  movzx   eax, ax
0x18004794c  or      eax, 80070000h
0x180047951  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180047958  mov     r8d, 5BDh
0x18004795e  jmp     loc_180047B0F
0x180047963  mov     [rsp+108h+pAsync.UserInfo], 0
0x18004796f  mov     [rsp+108h+pAsync.NotificationType], 1
0x18004797a  xor     r9d, r9d; lpName
0x18004797d  xor     r8d, r8d; bInitialState
0x180047980  xor     edx, edx; bManualReset
0x180047982  xor     ecx, ecx; lpEventAttributes
0x180047984  call    cs:__imp_CreateEventW
0x18004798a  mov     qword ptr [rsp+108h+pAsync.u], rax
0x180047992  test    rax, rax
0x180047995  jnz     short loc_1800479B2
0x180047997  call    cs:__imp_GetLastError
0x18004799d  test    eax, eax
0x18004799f  jle     short loc_1800479A9
0x1800479a1  movzx   eax, ax
0x1800479a4  or      eax, 80070000h
0x1800479a9  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x1800479b0  jmp     short loc_180047958
0x1800479b2  mov     [rsp+108h+Handles], rax
0x1800479b7  mov     [rsp+108h+var_D8], r13
0x1800479bc  mov     [rsp+108h+var_E0], r12d
0x1800479c1  mov     rax, [rsp+108h+var_B8]
0x1800479c6  mov     qword ptr [rsp+108h+bAlertable], rax
0x1800479cb  lea     r9, [rsp+108h+pAsync]
0x1800479d0  xor     r8d, r8d; pReturnValue
0x1800479d3  lea     edx, [r8+47h]; nProcNum
0x1800479d7  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800479de  call    cs:__imp_Ndr64AsyncClientCall
0x1800479e4  mov     eax, [rsp+108h+Reply]
0x1800479e8  jmp     short loc_180047A39
0x1800479ea  test    eax, eax
0x1800479ec  jle     short loc_1800479F6
0x1800479ee  movzx   eax, ax
0x1800479f1  or      eax, 80070000h
0x1800479f6  mov     [rsp+108h+Reply], eax
0x1800479fa  mov     [rsp+108h+bAlertable], eax
0x1800479fe  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180047a05  mov     r8d, 5C3h; unsigned int
0x180047a0b  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180047a12  mov     ecx, 2; unsigned __int8
0x180047a17  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180047a1c  mov     eax, [rsp+108h+Reply]
0x180047a20  test    eax, eax
0x180047a22  js      short loc_180047A2D
0x180047a24  mov     eax, 8000FFFFh
0x180047a29  mov     [rsp+108h+Reply], eax
0x180047a2d  mov     esi, [rsp+108h+dwMilliseconds]
0x180047a31  mov     r15b, [rsp+108h+var_C4]
0x180047a36  mov     r14b, r15b
0x180047a39  test    eax, eax
0x180047a3b  jns     short loc_180047A4F
0x180047a3d  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180047a44  mov     r8d, 5C3h
0x180047a4a  jmp     loc_180047B13
0x180047a4f  mov     [rsp+108h+bAlertable], 0; bAlertable
0x180047a57  mov     r9d, esi; dwMilliseconds
0x180047a5a  xor     r8d, r8d; bWaitAll
0x180047a5d  lea     rdx, [rsp+108h+Handles]; lpHandles
0x180047a62  lea     ecx, [r8+1]; nCount
0x180047a66  call    cs:__imp_WaitForMultipleObjectsEx
0x180047a6c  mov     esi, eax
0x180047a6e  mov     r12d, 102h
0x180047a74  test    r14b, r14b
0x180047a77  jnz     short loc_180047AC5
0x180047a79  cmp     esi, r12d
0x180047a7c  jz      short loc_180047A83
0x180047a7e  cmp     esi, 1
0x180047a81  jnz     short loc_180047AC5
0x180047a83  mov     edx, 1; fAbort
0x180047a88  lea     rcx, [rsp+108h+pAsync]; pAsync
0x180047a8d  call    cs:__imp_RpcAsyncCancelCall
0x180047a93  cmp     esi, r12d
0x180047a96  jnz     short loc_180047A9D
0x180047a98  mov     r15b, 1
0x180047a9b  jmp     short loc_180047AA0
0x180047a9d  mov     r14b, 1
0x180047aa0  mov     [rsp+108h+bAlertable], 0; bAlertable
0x180047aa8  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180047aac  xor     r8d, r8d; bWaitAll
0x180047aaf  lea     rdx, [rsp+108h+Handles]; lpHandles
0x180047ab4  lea     ecx, [r8+1]; nCount
0x180047ab8  call    cs:__imp_WaitForMultipleObjectsEx
0x180047abe  mov     esi, eax
0x180047ac0  test    r15b, r15b
0x180047ac3  jz      short loc_180047A74
0x180047ac5  test    esi, esi
0x180047ac7  jz      short loc_180047AE4
0x180047ac9  call    cs:__imp_GetLastError
0x180047acf  test    eax, eax
0x180047ad1  jle     short loc_180047ADB
0x180047ad3  movzx   eax, ax
0x180047ad6  or      eax, 80070000h
0x180047adb  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180047ae2  jmp     short loc_180047B09
0x180047ae4  lea     rdx, [rsp+108h+Reply]; Reply
0x180047ae9  lea     rcx, [rsp+108h+pAsync]; pAsync
0x180047aee  call    cs:__imp_RpcAsyncCompleteCall
0x180047af4  test    eax, eax
0x180047af6  jz      short loc_180047B28
0x180047af8  jle     short loc_180047B02
0x180047afa  movzx   eax, ax
0x180047afd  or      eax, 80070000h
0x180047b02  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180047b09  mov     r8d, 5C3h; unsigned int
0x180047b0f  mov     [rsp+108h+Reply], eax
0x180047b13  mov     [rsp+108h+bAlertable], eax
0x180047b17  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180047b1e  mov     ecx, 2; unsigned __int8
0x180047b23  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180047b28  mov     rcx, qword ptr [rsp+108h+pAsync.u]; hObject
0x180047b30  test    rcx, rcx
0x180047b33  jz      short loc_180047B3B
0x180047b35  call    cs:__imp_CloseHandle
0x180047b3b  test    r15b, r15b
0x180047b3e  jz      short loc_180047B78
0x180047b40  mov     [rsp+108h+Reply], 800705B4h
0x180047b48  lea     rdx, [rsp+108h+var_BC]
0x180047b4d  call    ??$RPCCallTimedOut@AEAY0CJ@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0CJ@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[41],ulong &>(char const (&)[41],ulong &)
0x180047b52  mov     eax, [rsp+108h+Reply]
0x180047b56  mov     [rsp+108h+bAlertable], eax
0x180047b5a  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180047b61  mov     r8d, 5C3h; unsigned int
0x180047b67  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180047b6e  mov     ecx, 2; unsigned __int8
0x180047b73  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180047b78  test    r14b, r14b
0x180047b7b  jz      short loc_180047BA8
0x180047b7d  mov     eax, 800704C7h
0x180047b82  mov     [rsp+108h+Reply], eax
0x180047b86  mov     [rsp+108h+bAlertable], eax
0x180047b8a  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180047b91  mov     r8d, 5C3h; unsigned int
0x180047b97  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180047b9e  mov     ecx, 2; unsigned __int8
0x180047ba3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180047ba8  cmp     [rsp+108h+Reply], 800706B5h
0x180047bb0  jz      short loc_180047BBC
0x180047bb2  cmp     [rsp+108h+Reply], 800706BAh
0x180047bba  jnz     short loc_180047BC1
0x180047bbc  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180047bc1  lea     rcx, [rsp+108h+var_B8]; this
0x180047bc6  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x180047bcb  mov     eax, [rsp+108h+Reply]
0x180047bcf  mov     rcx, [rsp+108h+var_28]
0x180047bd7  xor     rcx, rsp; StackCookie
0x180047bda  call    __security_check_cookie
0x180047bdf  lea     r11, [rsp+108h+var_18]
0x180047be7  mov     rsi, [r11+30h]
0x180047beb  mov     r12, [r11+38h]
0x180047bef  mov     rsp, r11
0x180047bf2  pop     r15
0x180047bf4  pop     r14
0x180047bf6  pop     r13
0x180047bf8  retn
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
