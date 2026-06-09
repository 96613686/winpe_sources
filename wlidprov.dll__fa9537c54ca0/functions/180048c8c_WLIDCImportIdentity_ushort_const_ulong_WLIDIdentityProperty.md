# WLIDCImportIdentity(ushort const *,ulong,_WLIDIdentityProperty *)

- ea: `0x180048c8c`
- end: `0x180048ff0`
- name: `?WLIDCImportIdentity@@YAJPEBGKPEAU_WLIDIdentityProperty@@@Z`
- size: `868`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, struct _WLIDIdentityProperty *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180016d68`

## callees

- `0x18000a400`
- `0x18000f870`
- `0x180010c68`
- `0x180011588`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180041bf4`
- `0x180043240`
- `0x180048c8c`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180048d73`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180048d73`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180048e5f`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180048eb1`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180048e5f`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180048eb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048d86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048ec2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048d86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048ec2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048f2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048f2e`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180048d2c`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180048d2c`
- `RPCRT4!RpcAsyncCancelCall` at `0x180048e86`
- `RPCRT4!RpcAsyncCancelCall` at `0x180048e86`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180048dd7`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180048dd7`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180048ee7`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180048ee7`

## string_xrefs

- `0x180048d98`: `RPC failed to create new event, hr = %#x`
- `0x180048efb`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCImportIdentity(const unsigned __int16 *a1, unsigned int a2, struct _WLIDIdentityProperty *a3)
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
  BOOL bAlertable[2]; // [rsp+20h] [rbp-F8h]
  int Reply; // [rsp+40h] [rbp-D8h] BYREF
  char v16; // [rsp+44h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-D0h] BYREF
  DWORD v18; // [rsp+4Ch] [rbp-CCh] BYREF
  __int64 v19; // [rsp+50h] [rbp-C8h] BYREF
  struct _WLIDIdentityProperty *v20; // [rsp+58h] [rbp-C0h]
  HANDLE Handles[2]; // [rsp+60h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-A8h] BYREF

  v20 = a3;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  v19 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v19);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v6 = dwMilliseconds;
  v18 = dwMilliseconds;
  v7 = 0;
  v16 = 0;
  v8 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v11 = 544;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 8u, 0, &pAsync, v19, a1, a2, v20);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v10 = L"RPC call failed, hr = %#x";
    v11 = 546;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
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
    v11 = 546;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[20],unsigned long &>("WLIDCImportIdentity", &v18);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x222u,
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
      0x222u,
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
0x180048c8c  push    rsi
0x180048c8e  push    r12
0x180048c90  push    r13
0x180048c92  push    r14
0x180048c94  push    r15
0x180048c96  sub     rsp, 0F0h
0x180048c9d  mov     rax, cs:__security_cookie
0x180048ca4  xor     rax, rsp
0x180048ca7  mov     [rsp+118h+var_38], rax
0x180048caf  mov     [rsp+118h+var_C0], r8
0x180048cb4  mov     r13d, edx
0x180048cb7  mov     r12, rcx
0x180048cba  mov     [rsp+118h+dwMilliseconds], 0
0x180048cc2  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x180048cc7  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180048ccc  mov     [rsp+118h+Reply], 0
0x180048cd4  mov     [rsp+118h+var_C8], 0
0x180048cdd  lea     rcx, [rsp+118h+var_C8]; this
0x180048ce2  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x180048ce7  mov     [rsp+118h+Reply], eax
0x180048ceb  test    eax, eax
0x180048ced  js      loc_180048FCF
0x180048cf3  xor     edx, edx; Val
0x180048cf5  lea     r8d, [rdx+70h]; Size
0x180048cf9  lea     rcx, [rsp+118h+pAsync]; void *
0x180048cfe  call    memset_0
0x180048d03  mov     esi, [rsp+118h+dwMilliseconds]
0x180048d07  mov     [rsp+118h+dwMilliseconds], esi
0x180048d0b  mov     [rsp+118h+var_CC], esi
0x180048d0f  xor     r15b, r15b
0x180048d12  mov     [rsp+118h+var_D4], r15b
0x180048d17  xor     r14b, r14b
0x180048d1a  xorps   xmm0, xmm0
0x180048d1d  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x180048d22  mov     edx, 70h ; 'p'; Size
0x180048d27  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180048d2c  call    cs:__imp_RpcAsyncInitializeHandle
0x180048d32  test    eax, eax
0x180048d34  jz      short loc_180048D52
0x180048d36  jle     short loc_180048D40
0x180048d38  movzx   eax, ax
0x180048d3b  or      eax, 80070000h
0x180048d40  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180048d47  mov     r8d, 220h
0x180048d4d  jmp     loc_180048F08
0x180048d52  mov     [rsp+118h+pAsync.UserInfo], 0
0x180048d5e  mov     [rsp+118h+pAsync.NotificationType], 1
0x180048d69  xor     r9d, r9d; lpName
0x180048d6c  xor     r8d, r8d; bInitialState
0x180048d6f  xor     edx, edx; bManualReset
0x180048d71  xor     ecx, ecx; lpEventAttributes
0x180048d73  call    cs:__imp_CreateEventW
0x180048d79  mov     qword ptr [rsp+118h+pAsync.u], rax
0x180048d81  test    rax, rax
0x180048d84  jnz     short loc_180048DA1
0x180048d86  call    cs:__imp_GetLastError
0x180048d8c  test    eax, eax
0x180048d8e  jle     short loc_180048D98
0x180048d90  movzx   eax, ax
0x180048d93  or      eax, 80070000h
0x180048d98  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180048d9f  jmp     short loc_180048D47
0x180048da1  mov     [rsp+118h+Handles], rax
0x180048da6  mov     rax, [rsp+118h+var_C0]
0x180048dab  mov     [rsp+118h+var_E0], rax
0x180048db0  mov     [rsp+118h+var_E8], r13d
0x180048db5  mov     [rsp+118h+var_F0], r12
0x180048dba  mov     rax, [rsp+118h+var_C8]
0x180048dbf  mov     qword ptr [rsp+118h+bAlertable], rax
0x180048dc4  lea     r9, [rsp+118h+pAsync]
0x180048dc9  xor     r8d, r8d; pReturnValue
0x180048dcc  lea     edx, [r8+8]; nProcNum
0x180048dd0  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180048dd7  call    cs:__imp_Ndr64AsyncClientCall
0x180048ddd  mov     eax, [rsp+118h+Reply]
0x180048de1  jmp     short loc_180048E32
0x180048de3  test    eax, eax
0x180048de5  jle     short loc_180048DEF
0x180048de7  movzx   eax, ax
0x180048dea  or      eax, 80070000h
0x180048def  mov     [rsp+118h+Reply], eax
0x180048df3  mov     [rsp+118h+bAlertable], eax
0x180048df7  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180048dfe  mov     r8d, 222h; unsigned int
0x180048e04  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180048e0b  mov     ecx, 2; unsigned __int8
0x180048e10  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180048e15  mov     eax, [rsp+118h+Reply]
0x180048e19  test    eax, eax
0x180048e1b  js      short loc_180048E26
0x180048e1d  mov     eax, 8000FFFFh
0x180048e22  mov     [rsp+118h+Reply], eax
0x180048e26  mov     esi, [rsp+118h+dwMilliseconds]
0x180048e2a  mov     r15b, [rsp+118h+var_D4]
0x180048e2f  mov     r14b, r15b
0x180048e32  test    eax, eax
0x180048e34  jns     short loc_180048E48
0x180048e36  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180048e3d  mov     r8d, 222h
0x180048e43  jmp     loc_180048F0C
0x180048e48  mov     [rsp+118h+bAlertable], 0; bAlertable
0x180048e50  mov     r9d, esi; dwMilliseconds
0x180048e53  xor     r8d, r8d; bWaitAll
0x180048e56  lea     rdx, [rsp+118h+Handles]; lpHandles
0x180048e5b  lea     ecx, [r8+1]; nCount
0x180048e5f  call    cs:__imp_WaitForMultipleObjectsEx
0x180048e65  mov     esi, eax
0x180048e67  mov     r12d, 102h
0x180048e6d  test    r14b, r14b
0x180048e70  jnz     short loc_180048EBE
0x180048e72  cmp     esi, r12d
0x180048e75  jz      short loc_180048E7C
0x180048e77  cmp     esi, 1
0x180048e7a  jnz     short loc_180048EBE
0x180048e7c  mov     edx, 1; fAbort
0x180048e81  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180048e86  call    cs:__imp_RpcAsyncCancelCall
0x180048e8c  cmp     esi, r12d
0x180048e8f  jnz     short loc_180048E96
0x180048e91  mov     r15b, 1
0x180048e94  jmp     short loc_180048E99
0x180048e96  mov     r14b, 1
0x180048e99  mov     [rsp+118h+bAlertable], 0; bAlertable
0x180048ea1  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180048ea5  xor     r8d, r8d; bWaitAll
0x180048ea8  lea     rdx, [rsp+118h+Handles]; lpHandles
0x180048ead  lea     ecx, [r8+1]; nCount
0x180048eb1  call    cs:__imp_WaitForMultipleObjectsEx
0x180048eb7  mov     esi, eax
0x180048eb9  test    r15b, r15b
0x180048ebc  jz      short loc_180048E6D
0x180048ebe  test    esi, esi
0x180048ec0  jz      short loc_180048EDD
0x180048ec2  call    cs:__imp_GetLastError
0x180048ec8  test    eax, eax
0x180048eca  jle     short loc_180048ED4
0x180048ecc  movzx   eax, ax
0x180048ecf  or      eax, 80070000h
0x180048ed4  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180048edb  jmp     short loc_180048F02
0x180048edd  lea     rdx, [rsp+118h+Reply]; Reply
0x180048ee2  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180048ee7  call    cs:__imp_RpcAsyncCompleteCall
0x180048eed  test    eax, eax
0x180048eef  jz      short loc_180048F21
0x180048ef1  jle     short loc_180048EFB
0x180048ef3  movzx   eax, ax
0x180048ef6  or      eax, 80070000h
0x180048efb  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180048f02  mov     r8d, 222h; unsigned int
0x180048f08  mov     [rsp+118h+Reply], eax
0x180048f0c  mov     [rsp+118h+bAlertable], eax
0x180048f10  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180048f17  mov     ecx, 2; unsigned __int8
0x180048f1c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180048f21  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x180048f29  test    rcx, rcx
0x180048f2c  jz      short loc_180048F34
0x180048f2e  call    cs:__imp_CloseHandle
0x180048f34  test    r15b, r15b
0x180048f37  jz      short loc_180048F78
0x180048f39  mov     [rsp+118h+Reply], 800705B4h
0x180048f41  lea     rdx, [rsp+118h+var_CC]
0x180048f46  lea     rcx, aWlidcimportide; "WLIDCImportIdentity"
0x180048f4d  call    ??$RPCCallTimedOut@AEAY0BE@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BE@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[20],ulong &>(char const (&)[20],ulong &)
0x180048f52  mov     eax, [rsp+118h+Reply]
0x180048f56  mov     [rsp+118h+bAlertable], eax
0x180048f5a  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180048f61  mov     r8d, 222h; unsigned int
0x180048f67  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180048f6e  mov     ecx, 2; unsigned __int8
0x180048f73  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180048f78  test    r14b, r14b
0x180048f7b  jz      short loc_180048FA8
0x180048f7d  mov     eax, 800704C7h
0x180048f82  mov     [rsp+118h+Reply], eax
0x180048f86  mov     [rsp+118h+bAlertable], eax
0x180048f8a  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180048f91  mov     r8d, 222h; unsigned int
0x180048f97  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180048f9e  mov     ecx, 2; unsigned __int8
0x180048fa3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180048fa8  cmp     [rsp+118h+Reply], 800706B5h
0x180048fb0  jz      short loc_180048FBC
0x180048fb2  cmp     [rsp+118h+Reply], 800706BAh
0x180048fba  jnz     short loc_180048FC1
0x180048fbc  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180048fc1  lea     rcx, [rsp+118h+var_C8]; this
0x180048fc6  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x180048fcb  mov     eax, [rsp+118h+Reply]
0x180048fcf  mov     rcx, [rsp+118h+var_38]
0x180048fd7  xor     rcx, rsp; StackCookie
0x180048fda  call    __security_check_cookie
0x180048fdf  add     rsp, 0F0h
0x180048fe6  pop     r15
0x180048fe8  pop     r14
0x180048fea  pop     r13
0x180048fec  pop     r12
0x180048fee  pop     rsi
0x180048fef  retn
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
