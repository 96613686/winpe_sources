# WLIDCCreateContextEx(ushort const *,ushort const *,unsigned __int64,void * *)

- ea: `0x180044874`
- end: `0x180044c02`
- name: `?WLIDCCreateContextEx@@YAJPEBG0_KPEAPEAX@Z`
- size: `910`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int64, void **)`
- caller_count: `5`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800243c0`
- `0x1800247c0`
- `0x180025bbc`
- `0x180041600`
- `0x180041610`

## callees

- `0x18000a400`
- `0x18000f870`
- `0x180010c68`
- `0x180011588`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180041c80`
- `0x180043240`
- `0x1800433c4`
- `0x180044874`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180044966`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180044966`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180044a5f`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180044ab4`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180044a5f`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180044ab4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044ac5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044ac5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044b34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044b34`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004491f`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004491f`
- `RPCRT4!RpcAsyncCancelCall` at `0x180044a89`
- `RPCRT4!RpcAsyncCancelCall` at `0x180044a89`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800449d7`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800449d7`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180044aed`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180044aed`

## string_xrefs

- `0x18004498b`: `RPC failed to create new event, hr = %#x`
- `0x180044b01`: `RPC Async complete call failed, hr = %#x`
- `0x180044b4c`: `WLIDCCreateContextEx`
- `0x180044bd1`: `WLIDCCreateContextEx`

## pseudocode

```c
__int64 __fastcall WLIDCCreateContextEx(const unsigned __int16 *a1, const unsigned __int16 *a2, __int64 a3, void **a4)
{
  __int64 result; // rax
  DWORD v7; // esi
  char v8; // r15
  char v9; // r14
  int LastError; // eax
  const unsigned __int16 *v11; // r9
  unsigned int v12; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v14; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-118h]
  int Reply; // [rsp+50h] [rbp-E8h] BYREF
  char v17; // [rsp+54h] [rbp-E4h]
  DWORD dwMilliseconds; // [rsp+58h] [rbp-E0h] BYREF
  DWORD v19; // [rsp+5Ch] [rbp-DCh] BYREF
  __int64 v20; // [rsp+60h] [rbp-D8h] BYREF
  void **v21; // [rsp+68h] [rbp-D0h]
  __int64 v22; // [rsp+70h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+78h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+90h] [rbp-A8h] BYREF

  v21 = a4;
  v22 = a3;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  v20 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v20);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v7 = dwMilliseconds;
  v19 = dwMilliseconds;
  v8 = 0;
  v17 = 0;
  v9 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v11 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v12 = 574;
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
    v11 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0xAu, 0, &pAsync, v20, a1, a2, v22, v21);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v11 = L"RPC call failed, hr = %#x";
    v12 = 576;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v12,
      v11,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
  v14 = WaitForMultipleObjectsEx(1u, Handles, 0, v7, 0);
  do
  {
    if ( v9 || v14 != 258 && v14 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v14 == 258 )
      v8 = 1;
    else
      v9 = 1;
    v14 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v8 );
  if ( v14 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v11 = L"Encountered error while waiting on RPC call, hr = %#x";
LABEL_29:
    v12 = 576;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v11 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v8 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],unsigned long &>("WLIDCCreateContextEx", &v19);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x240u,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v9 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x240u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v20);
  return TranslateRpcServiceError(Reply, "WLIDCCreateContextEx");
}

```

## disassembly

```asm
0x180044874  push    rsi
0x180044876  push    r12
0x180044878  push    r13
0x18004487a  push    r14
0x18004487c  push    r15
0x18004487e  sub     rsp, 110h
0x180044885  mov     rax, cs:__security_cookie
0x18004488c  xor     rax, rsp
0x18004488f  mov     [rsp+138h+var_38], rax
0x180044897  mov     [rsp+138h+var_D0], r9
0x18004489c  mov     [rsp+138h+var_C8], r8
0x1800448a1  mov     r13, rdx
0x1800448a4  mov     r12, rcx
0x1800448a7  mov     [rsp+138h+dwMilliseconds], 0
0x1800448af  lea     r8, [rsp+138h+dwMilliseconds]; unsigned int *
0x1800448b4  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x1800448b9  mov     [rsp+138h+Reply], 0
0x1800448c1  mov     [rsp+138h+var_D8], 0
0x1800448ca  lea     rcx, [rsp+138h+var_D8]; this
0x1800448cf  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x1800448d4  mov     [rsp+138h+Reply], eax
0x1800448d8  test    eax, eax
0x1800448da  js      loc_180044BE1
0x1800448e0  xor     edx, edx; Val
0x1800448e2  lea     r8d, [rdx+70h]; Size
0x1800448e6  lea     rcx, [rsp+138h+pAsync]; void *
0x1800448ee  call    memset_0
0x1800448f3  mov     esi, [rsp+138h+dwMilliseconds]
0x1800448f7  mov     [rsp+138h+dwMilliseconds], esi
0x1800448fb  mov     [rsp+138h+var_DC], esi
0x1800448ff  xor     r15b, r15b
0x180044902  mov     [rsp+138h+var_E4], r15b
0x180044907  xor     r14b, r14b
0x18004490a  xorps   xmm0, xmm0
0x18004490d  movups  xmmword ptr [rsp+138h+Handles], xmm0
0x180044912  mov     edx, 70h ; 'p'; Size
0x180044917  lea     rcx, [rsp+138h+pAsync]; pAsync
0x18004491f  call    cs:__imp_RpcAsyncInitializeHandle
0x180044925  test    eax, eax
0x180044927  jz      short loc_180044945
0x180044929  jle     short loc_180044933
0x18004492b  movzx   eax, ax
0x18004492e  or      eax, 80070000h
0x180044933  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004493a  mov     r8d, 23Eh
0x180044940  jmp     loc_180044B0E
0x180044945  mov     [rsp+138h+pAsync.UserInfo], 0
0x180044951  mov     [rsp+138h+pAsync.NotificationType], 1
0x18004495c  xor     r9d, r9d; lpName
0x18004495f  xor     r8d, r8d; bInitialState
0x180044962  xor     edx, edx; bManualReset
0x180044964  xor     ecx, ecx; lpEventAttributes
0x180044966  call    cs:__imp_CreateEventW
0x18004496c  mov     qword ptr [rsp+138h+pAsync.u], rax
0x180044974  test    rax, rax
0x180044977  jnz     short loc_180044994
0x180044979  call    cs:__imp_GetLastError
0x18004497f  test    eax, eax
0x180044981  jle     short loc_18004498B
0x180044983  movzx   eax, ax
0x180044986  or      eax, 80070000h
0x18004498b  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180044992  jmp     short loc_18004493A
0x180044994  mov     [rsp+138h+Handles], rax
0x180044999  mov     rax, [rsp+138h+var_D0]
0x18004499e  mov     [rsp+138h+var_F8], rax
0x1800449a3  mov     rax, [rsp+138h+var_C8]
0x1800449a8  mov     [rsp+138h+var_100], rax
0x1800449ad  mov     [rsp+138h+var_108], r13
0x1800449b2  mov     [rsp+138h+var_110], r12
0x1800449b7  mov     rax, [rsp+138h+var_D8]
0x1800449bc  mov     qword ptr [rsp+138h+bAlertable], rax
0x1800449c1  lea     r9, [rsp+138h+pAsync]
0x1800449c9  xor     r8d, r8d; pReturnValue
0x1800449cc  lea     edx, [r8+0Ah]; nProcNum
0x1800449d0  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800449d7  call    cs:__imp_Ndr64AsyncClientCall
0x1800449dd  mov     eax, [rsp+138h+Reply]
0x1800449e1  jmp     short loc_180044A32
0x1800449e3  test    eax, eax
0x1800449e5  jle     short loc_1800449EF
0x1800449e7  movzx   eax, ax
0x1800449ea  or      eax, 80070000h
0x1800449ef  mov     [rsp+138h+Reply], eax
0x1800449f3  mov     [rsp+138h+bAlertable], eax
0x1800449f7  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x1800449fe  mov     r8d, 240h; unsigned int
0x180044a04  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180044a0b  mov     ecx, 2; unsigned __int8
0x180044a10  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180044a15  mov     eax, [rsp+138h+Reply]
0x180044a19  test    eax, eax
0x180044a1b  js      short loc_180044A26
0x180044a1d  mov     eax, 8000FFFFh
0x180044a22  mov     [rsp+138h+Reply], eax
0x180044a26  mov     esi, [rsp+138h+dwMilliseconds]
0x180044a2a  mov     r15b, [rsp+138h+var_E4]
0x180044a2f  mov     r14b, r15b
0x180044a32  test    eax, eax
0x180044a34  jns     short loc_180044A48
0x180044a36  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180044a3d  mov     r8d, 240h
0x180044a43  jmp     loc_180044B12
0x180044a48  mov     [rsp+138h+bAlertable], 0; bAlertable
0x180044a50  mov     r9d, esi; dwMilliseconds
0x180044a53  xor     r8d, r8d; bWaitAll
0x180044a56  lea     rdx, [rsp+138h+Handles]; lpHandles
0x180044a5b  lea     ecx, [r8+1]; nCount
0x180044a5f  call    cs:__imp_WaitForMultipleObjectsEx
0x180044a65  mov     esi, eax
0x180044a67  mov     r12d, 102h
0x180044a6d  test    r14b, r14b
0x180044a70  jnz     short loc_180044AC1
0x180044a72  cmp     esi, r12d
0x180044a75  jz      short loc_180044A7C
0x180044a77  cmp     esi, 1
0x180044a7a  jnz     short loc_180044AC1
0x180044a7c  mov     edx, 1; fAbort
0x180044a81  lea     rcx, [rsp+138h+pAsync]; pAsync
0x180044a89  call    cs:__imp_RpcAsyncCancelCall
0x180044a8f  cmp     esi, r12d
0x180044a92  jnz     short loc_180044A99
0x180044a94  mov     r15b, 1
0x180044a97  jmp     short loc_180044A9C
0x180044a99  mov     r14b, 1
0x180044a9c  mov     [rsp+138h+bAlertable], 0; bAlertable
0x180044aa4  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180044aa8  xor     r8d, r8d; bWaitAll
0x180044aab  lea     rdx, [rsp+138h+Handles]; lpHandles
0x180044ab0  lea     ecx, [r8+1]; nCount
0x180044ab4  call    cs:__imp_WaitForMultipleObjectsEx
0x180044aba  mov     esi, eax
0x180044abc  test    r15b, r15b
0x180044abf  jz      short loc_180044A6D
0x180044ac1  test    esi, esi
0x180044ac3  jz      short loc_180044AE0
0x180044ac5  call    cs:__imp_GetLastError
0x180044acb  test    eax, eax
0x180044acd  jle     short loc_180044AD7
0x180044acf  movzx   eax, ax
0x180044ad2  or      eax, 80070000h
0x180044ad7  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180044ade  jmp     short loc_180044B08
0x180044ae0  lea     rdx, [rsp+138h+Reply]; Reply
0x180044ae5  lea     rcx, [rsp+138h+pAsync]; pAsync
0x180044aed  call    cs:__imp_RpcAsyncCompleteCall
0x180044af3  test    eax, eax
0x180044af5  jz      short loc_180044B27
0x180044af7  jle     short loc_180044B01
0x180044af9  movzx   eax, ax
0x180044afc  or      eax, 80070000h
0x180044b01  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180044b08  mov     r8d, 240h; unsigned int
0x180044b0e  mov     [rsp+138h+Reply], eax
0x180044b12  mov     [rsp+138h+bAlertable], eax
0x180044b16  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180044b1d  mov     ecx, 2; unsigned __int8
0x180044b22  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180044b27  mov     rcx, qword ptr [rsp+138h+pAsync.u]; hObject
0x180044b2f  test    rcx, rcx
0x180044b32  jz      short loc_180044B3A
0x180044b34  call    cs:__imp_CloseHandle
0x180044b3a  test    r15b, r15b
0x180044b3d  jz      short loc_180044B7E
0x180044b3f  mov     [rsp+138h+Reply], 800705B4h
0x180044b47  lea     rdx, [rsp+138h+var_DC]
0x180044b4c  lea     rcx, aWlidccreatecon; "WLIDCCreateContextEx"
0x180044b53  call    ??$RPCCallTimedOut@AEAY0BF@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BF@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],ulong &>(char const (&)[21],ulong &)
0x180044b58  mov     eax, [rsp+138h+Reply]
0x180044b5c  mov     [rsp+138h+bAlertable], eax
0x180044b60  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180044b67  mov     r8d, 240h; unsigned int
0x180044b6d  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180044b74  mov     ecx, 2; unsigned __int8
0x180044b79  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180044b7e  test    r14b, r14b
0x180044b81  jz      short loc_180044BAE
0x180044b83  mov     eax, 800704C7h
0x180044b88  mov     [rsp+138h+Reply], eax
0x180044b8c  mov     [rsp+138h+bAlertable], eax
0x180044b90  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180044b97  mov     r8d, 240h; unsigned int
0x180044b9d  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180044ba4  mov     ecx, 2; unsigned __int8
0x180044ba9  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180044bae  cmp     [rsp+138h+Reply], 800706B5h
0x180044bb6  jz      short loc_180044BC2
0x180044bb8  cmp     [rsp+138h+Reply], 800706BAh
0x180044bc0  jnz     short loc_180044BC7
0x180044bc2  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180044bc7  lea     rcx, [rsp+138h+var_D8]; this
0x180044bcc  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x180044bd1  lea     rdx, aWlidccreatecon; "WLIDCCreateContextEx"
0x180044bd8  mov     ecx, [rsp+138h+Reply]; int
0x180044bdc  call    ?TranslateRpcServiceError@@YAJJPEBD@Z; TranslateRpcServiceError(long,char const *)
0x180044be1  mov     rcx, [rsp+138h+var_38]
0x180044be9  xor     rcx, rsp; StackCookie
0x180044bec  call    __security_check_cookie
0x180044bf1  add     rsp, 110h
0x180044bf8  pop     r15
0x180044bfa  pop     r14
0x180044bfc  pop     r13
0x180044bfe  pop     r12
0x180044c00  pop     rsi
0x180044c01  retn
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
