# WLIDCEnumDevices(ushort const *,unsigned __int64,ulong *,__MIDL_liveidsvc_0002 * *)

- ea: `0x180048b44`
- end: `0x180048ec6`
- name: `?WLIDCEnumDevices@@YAJPEBG_KPEAKPEAPEAU__MIDL_liveidsvc_0002@@@Z`
- size: `898`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64, unsigned int *, struct __MIDL_liveidsvc_0002 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002b000`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180044d94`
- `0x180046ce0`
- `0x180048b44`
- `0x18004cd04`
- `0x180050c84`
- `0x180050e40`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180048d2f`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180048d84`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180048d2f`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180048d84`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180048c36`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180048c36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048c49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048d95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048c49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048d95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048e04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048e04`
- `RPCRT4!RpcAsyncCancelCall` at `0x180048d59`
- `RPCRT4!RpcAsyncCancelCall` at `0x180048d59`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180048ca7`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180048ca7`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180048dbd`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180048dbd`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180048bef`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180048bef`

## string_xrefs

- `0x180048c5b`: `RPC failed to create new event, hr = %#x`
- `0x180048dd1`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCEnumDevices(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned int *a3,
        struct __MIDL_liveidsvc_0002 **a4)
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
  struct __MIDL_liveidsvc_0002 **v21; // [rsp+68h] [rbp-D0h]
  unsigned int *v22; // [rsp+70h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+78h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+90h] [rbp-A8h] BYREF

  v21 = a4;
  v22 = a3;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
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
    v12 = 898;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x23u, 0, &pAsync, v20, a1, a2, v22, v21);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v11 = L"RPC call failed, hr = %#x";
    v12 = 900;
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
    v12 = 900;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[17],unsigned long &>(
      (__int64)"WLIDCEnumDevices",
      (int *)&v19);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x384u,
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
      0x384u,
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
0x180048b44  push    rsi
0x180048b46  push    r12
0x180048b48  push    r13
0x180048b4a  push    r14
0x180048b4c  push    r15
0x180048b4e  sub     rsp, 110h
0x180048b55  mov     rax, cs:__security_cookie
0x180048b5c  xor     rax, rsp
0x180048b5f  mov     [rsp+138h+var_38], rax
0x180048b67  mov     [rsp+138h+var_D0], r9
0x180048b6c  mov     [rsp+138h+var_C8], r8
0x180048b71  mov     r13, rdx
0x180048b74  mov     r12, rcx
0x180048b77  mov     [rsp+138h+dwMilliseconds], 0
0x180048b7f  lea     r8, [rsp+138h+dwMilliseconds]; unsigned int *
0x180048b84  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180048b89  mov     [rsp+138h+Reply], 0
0x180048b91  mov     [rsp+138h+var_D8], 0
0x180048b9a  lea     rcx, [rsp+138h+var_D8]; this
0x180048b9f  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x180048ba4  mov     [rsp+138h+Reply], eax
0x180048ba8  test    eax, eax
0x180048baa  js      loc_180048EA5
0x180048bb0  xor     edx, edx; Val
0x180048bb2  lea     r8d, [rdx+70h]; Size
0x180048bb6  lea     rcx, [rsp+138h+pAsync]; void *
0x180048bbe  call    memset_0
0x180048bc3  mov     esi, [rsp+138h+dwMilliseconds]
0x180048bc7  mov     [rsp+138h+dwMilliseconds], esi
0x180048bcb  mov     [rsp+138h+var_DC], esi
0x180048bcf  xor     r15b, r15b
0x180048bd2  mov     [rsp+138h+var_E4], r15b
0x180048bd7  xor     r14b, r14b
0x180048bda  xorps   xmm0, xmm0
0x180048bdd  movups  xmmword ptr [rsp+138h+Handles], xmm0
0x180048be2  mov     edx, 70h ; 'p'; Size
0x180048be7  lea     rcx, [rsp+138h+pAsync]; pAsync
0x180048bef  call    cs:__imp_RpcAsyncInitializeHandle
0x180048bf5  test    eax, eax
0x180048bf7  jz      short loc_180048C15
0x180048bf9  jle     short loc_180048C03
0x180048bfb  movzx   eax, ax
0x180048bfe  or      eax, 80070000h
0x180048c03  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180048c0a  mov     r8d, 382h
0x180048c10  jmp     loc_180048DDE
0x180048c15  mov     [rsp+138h+pAsync.UserInfo], 0
0x180048c21  mov     [rsp+138h+pAsync.NotificationType], 1
0x180048c2c  xor     r9d, r9d; lpName
0x180048c2f  xor     r8d, r8d; bInitialState
0x180048c32  xor     edx, edx; bManualReset
0x180048c34  xor     ecx, ecx; lpEventAttributes
0x180048c36  call    cs:__imp_CreateEventW
0x180048c3c  mov     qword ptr [rsp+138h+pAsync.u], rax
0x180048c44  test    rax, rax
0x180048c47  jnz     short loc_180048C64
0x180048c49  call    cs:__imp_GetLastError
0x180048c4f  test    eax, eax
0x180048c51  jle     short loc_180048C5B
0x180048c53  movzx   eax, ax
0x180048c56  or      eax, 80070000h
0x180048c5b  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180048c62  jmp     short loc_180048C0A
0x180048c64  mov     [rsp+138h+Handles], rax
0x180048c69  mov     rax, [rsp+138h+var_D0]
0x180048c6e  mov     [rsp+138h+var_F8], rax
0x180048c73  mov     rax, [rsp+138h+var_C8]
0x180048c78  mov     [rsp+138h+var_100], rax
0x180048c7d  mov     [rsp+138h+var_108], r13
0x180048c82  mov     [rsp+138h+var_110], r12
0x180048c87  mov     rax, [rsp+138h+var_D8]
0x180048c8c  mov     qword ptr [rsp+138h+bAlertable], rax
0x180048c91  lea     r9, [rsp+138h+pAsync]
0x180048c99  xor     r8d, r8d; pReturnValue
0x180048c9c  lea     edx, [r8+23h]; nProcNum
0x180048ca0  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180048ca7  call    cs:__imp_Ndr64AsyncClientCall
0x180048cad  mov     eax, [rsp+138h+Reply]
0x180048cb1  jmp     short loc_180048D02
0x180048cb3  test    eax, eax
0x180048cb5  jle     short loc_180048CBF
0x180048cb7  movzx   eax, ax
0x180048cba  or      eax, 80070000h
0x180048cbf  mov     [rsp+138h+Reply], eax
0x180048cc3  mov     [rsp+138h+bAlertable], eax
0x180048cc7  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180048cce  mov     r8d, 384h; unsigned int
0x180048cd4  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180048cdb  mov     ecx, 2; unsigned __int8
0x180048ce0  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180048ce5  mov     eax, [rsp+138h+Reply]
0x180048ce9  test    eax, eax
0x180048ceb  js      short loc_180048CF6
0x180048ced  mov     eax, 8000FFFFh
0x180048cf2  mov     [rsp+138h+Reply], eax
0x180048cf6  mov     esi, [rsp+138h+dwMilliseconds]
0x180048cfa  mov     r15b, [rsp+138h+var_E4]
0x180048cff  mov     r14b, r15b
0x180048d02  test    eax, eax
0x180048d04  jns     short loc_180048D18
0x180048d06  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180048d0d  mov     r8d, 384h
0x180048d13  jmp     loc_180048DE2
0x180048d18  mov     [rsp+138h+bAlertable], 0; bAlertable
0x180048d20  mov     r9d, esi; dwMilliseconds
0x180048d23  xor     r8d, r8d; bWaitAll
0x180048d26  lea     rdx, [rsp+138h+Handles]; lpHandles
0x180048d2b  lea     ecx, [r8+1]; nCount
0x180048d2f  call    cs:__imp_WaitForMultipleObjectsEx
0x180048d35  mov     esi, eax
0x180048d37  mov     r12d, 102h
0x180048d3d  test    r14b, r14b
0x180048d40  jnz     short loc_180048D91
0x180048d42  cmp     esi, r12d
0x180048d45  jz      short loc_180048D4C
0x180048d47  cmp     esi, 1
0x180048d4a  jnz     short loc_180048D91
0x180048d4c  mov     edx, 1; fAbort
0x180048d51  lea     rcx, [rsp+138h+pAsync]; pAsync
0x180048d59  call    cs:__imp_RpcAsyncCancelCall
0x180048d5f  cmp     esi, r12d
0x180048d62  jnz     short loc_180048D69
0x180048d64  mov     r15b, 1
0x180048d67  jmp     short loc_180048D6C
0x180048d69  mov     r14b, 1
0x180048d6c  mov     [rsp+138h+bAlertable], 0; bAlertable
0x180048d74  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180048d78  xor     r8d, r8d; bWaitAll
0x180048d7b  lea     rdx, [rsp+138h+Handles]; lpHandles
0x180048d80  lea     ecx, [r8+1]; nCount
0x180048d84  call    cs:__imp_WaitForMultipleObjectsEx
0x180048d8a  mov     esi, eax
0x180048d8c  test    r15b, r15b
0x180048d8f  jz      short loc_180048D3D
0x180048d91  test    esi, esi
0x180048d93  jz      short loc_180048DB0
0x180048d95  call    cs:__imp_GetLastError
0x180048d9b  test    eax, eax
0x180048d9d  jle     short loc_180048DA7
0x180048d9f  movzx   eax, ax
0x180048da2  or      eax, 80070000h
0x180048da7  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180048dae  jmp     short loc_180048DD8
0x180048db0  lea     rdx, [rsp+138h+Reply]; Reply
0x180048db5  lea     rcx, [rsp+138h+pAsync]; pAsync
0x180048dbd  call    cs:__imp_RpcAsyncCompleteCall
0x180048dc3  test    eax, eax
0x180048dc5  jz      short loc_180048DF7
0x180048dc7  jle     short loc_180048DD1
0x180048dc9  movzx   eax, ax
0x180048dcc  or      eax, 80070000h
0x180048dd1  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180048dd8  mov     r8d, 384h; unsigned int
0x180048dde  mov     [rsp+138h+Reply], eax
0x180048de2  mov     [rsp+138h+bAlertable], eax
0x180048de6  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180048ded  mov     ecx, 2; unsigned __int8
0x180048df2  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180048df7  mov     rcx, qword ptr [rsp+138h+pAsync.u]; hObject
0x180048dff  test    rcx, rcx
0x180048e02  jz      short loc_180048E0A
0x180048e04  call    cs:__imp_CloseHandle
0x180048e0a  test    r15b, r15b
0x180048e0d  jz      short loc_180048E4E
0x180048e0f  mov     [rsp+138h+Reply], 800705B4h
0x180048e17  lea     rdx, [rsp+138h+var_DC]
0x180048e1c  lea     rcx, aWlidcenumdevic; "WLIDCEnumDevices"
0x180048e23  call    ??$RPCCallTimedOut@AEAY0BB@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BB@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[17],ulong &>(char const (&)[17],ulong &)
0x180048e28  mov     eax, [rsp+138h+Reply]
0x180048e2c  mov     [rsp+138h+bAlertable], eax
0x180048e30  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180048e37  mov     r8d, 384h; unsigned int
0x180048e3d  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180048e44  mov     ecx, 2; unsigned __int8
0x180048e49  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180048e4e  test    r14b, r14b
0x180048e51  jz      short loc_180048E7E
0x180048e53  mov     eax, 800704C7h
0x180048e58  mov     [rsp+138h+Reply], eax
0x180048e5c  mov     [rsp+138h+bAlertable], eax
0x180048e60  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180048e67  mov     r8d, 384h; unsigned int
0x180048e6d  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180048e74  mov     ecx, 2; unsigned __int8
0x180048e79  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180048e7e  cmp     [rsp+138h+Reply], 800706B5h
0x180048e86  jz      short loc_180048E92
0x180048e88  cmp     [rsp+138h+Reply], 800706BAh
0x180048e90  jnz     short loc_180048E97
0x180048e92  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180048e97  lea     rcx, [rsp+138h+var_D8]; this
0x180048e9c  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x180048ea1  mov     eax, [rsp+138h+Reply]
0x180048ea5  mov     rcx, [rsp+138h+var_38]
0x180048ead  xor     rcx, rsp; StackCookie
0x180048eb0  call    __security_check_cookie
0x180048eb5  add     rsp, 110h
0x180048ebc  pop     r15
0x180048ebe  pop     r14
0x180048ec0  pop     r13
0x180048ec2  pop     r12
0x180048ec4  pop     rsi
0x180048ec5  retn
0x1800619d4  push    rbp
0x1800619d6  sub     rsp, 50h
0x1800619da  mov     rbp, rdx
0x1800619dd  mov     rcx, [rcx]
0x1800619e0  mov     ecx, [rcx]; unsigned int
0x1800619e2  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x1800619e7  nop
0x1800619e8  add     rsp, 50h
0x1800619ec  pop     rbp
0x1800619ed  retn
```
