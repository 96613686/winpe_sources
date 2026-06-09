# WLIDCGetUsersFromSsoGroup(unsigned __int64,ulong,ulong *,ushort * * *)

- ea: `0x18004d0cc`
- end: `0x18004d44e`
- name: `?WLIDCGetUsersFromSsoGroup@@YAJ_KKPEAKPEAPEAPEAG@Z`
- size: `898`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned int, unsigned int *, unsigned __int16 ***)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002d580`
- `0x180035640`
- `0x180036480`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x1800451f4`
- `0x180046ce0`
- `0x18004cd04`
- `0x18004d0cc`
- `0x180050c84`
- `0x180050e40`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004d2b7`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004d30c`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004d2b7`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004d30c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004d1be`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004d1be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d1d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d31d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d1d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d31d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d38c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d38c`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004d2e1`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004d2e1`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004d22f`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004d22f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004d345`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004d345`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004d177`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004d177`

## string_xrefs

- `0x18004d1e3`: `RPC failed to create new event, hr = %#x`
- `0x18004d359`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCGetUsersFromSsoGroup(__int64 a1, unsigned int a2, unsigned int *a3, unsigned __int16 ***a4)
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
  unsigned __int16 ***v21; // [rsp+68h] [rbp-D0h]
  unsigned int *v22; // [rsp+70h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+78h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+90h] [rbp-A8h] BYREF

  v21 = a4;
  v22 = a3;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue(a1, a2, &dwMilliseconds);
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
    v12 = 985;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x2Au, 0, &pAsync, v20, a1, a2, v22, v21);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v11 = L"RPC call failed, hr = %#x";
    v12 = 987;
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
    v12 = 987;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[26],unsigned long &>(
      (__int64)"WLIDCGetUsersFromSsoGroup",
      (int *)&v19);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x3DBu,
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
      0x3DBu,
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
0x18004d0cc  push    rsi
0x18004d0ce  push    r12
0x18004d0d0  push    r13
0x18004d0d2  push    r14
0x18004d0d4  push    r15
0x18004d0d6  sub     rsp, 110h
0x18004d0dd  mov     rax, cs:__security_cookie
0x18004d0e4  xor     rax, rsp
0x18004d0e7  mov     [rsp+138h+var_38], rax
0x18004d0ef  mov     [rsp+138h+var_D0], r9
0x18004d0f4  mov     [rsp+138h+var_C8], r8
0x18004d0f9  mov     r13d, edx
0x18004d0fc  mov     r12, rcx
0x18004d0ff  mov     [rsp+138h+dwMilliseconds], 0
0x18004d107  lea     r8, [rsp+138h+dwMilliseconds]; unsigned int *
0x18004d10c  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004d111  mov     [rsp+138h+Reply], 0
0x18004d119  mov     [rsp+138h+var_D8], 0
0x18004d122  lea     rcx, [rsp+138h+var_D8]; this
0x18004d127  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18004d12c  mov     [rsp+138h+Reply], eax
0x18004d130  test    eax, eax
0x18004d132  js      loc_18004D42D
0x18004d138  xor     edx, edx; Val
0x18004d13a  lea     r8d, [rdx+70h]; Size
0x18004d13e  lea     rcx, [rsp+138h+pAsync]; void *
0x18004d146  call    memset_0
0x18004d14b  mov     esi, [rsp+138h+dwMilliseconds]
0x18004d14f  mov     [rsp+138h+dwMilliseconds], esi
0x18004d153  mov     [rsp+138h+var_DC], esi
0x18004d157  xor     r15b, r15b
0x18004d15a  mov     [rsp+138h+var_E4], r15b
0x18004d15f  xor     r14b, r14b
0x18004d162  xorps   xmm0, xmm0
0x18004d165  movups  xmmword ptr [rsp+138h+Handles], xmm0
0x18004d16a  mov     edx, 70h ; 'p'; Size
0x18004d16f  lea     rcx, [rsp+138h+pAsync]; pAsync
0x18004d177  call    cs:__imp_RpcAsyncInitializeHandle
0x18004d17d  test    eax, eax
0x18004d17f  jz      short loc_18004D19D
0x18004d181  jle     short loc_18004D18B
0x18004d183  movzx   eax, ax
0x18004d186  or      eax, 80070000h
0x18004d18b  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004d192  mov     r8d, 3D9h
0x18004d198  jmp     loc_18004D366
0x18004d19d  mov     [rsp+138h+pAsync.UserInfo], 0
0x18004d1a9  mov     [rsp+138h+pAsync.NotificationType], 1
0x18004d1b4  xor     r9d, r9d; lpName
0x18004d1b7  xor     r8d, r8d; bInitialState
0x18004d1ba  xor     edx, edx; bManualReset
0x18004d1bc  xor     ecx, ecx; lpEventAttributes
0x18004d1be  call    cs:__imp_CreateEventW
0x18004d1c4  mov     qword ptr [rsp+138h+pAsync.u], rax
0x18004d1cc  test    rax, rax
0x18004d1cf  jnz     short loc_18004D1EC
0x18004d1d1  call    cs:__imp_GetLastError
0x18004d1d7  test    eax, eax
0x18004d1d9  jle     short loc_18004D1E3
0x18004d1db  movzx   eax, ax
0x18004d1de  or      eax, 80070000h
0x18004d1e3  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004d1ea  jmp     short loc_18004D192
0x18004d1ec  mov     [rsp+138h+Handles], rax
0x18004d1f1  mov     rax, [rsp+138h+var_D0]
0x18004d1f6  mov     [rsp+138h+var_F8], rax
0x18004d1fb  mov     rax, [rsp+138h+var_C8]
0x18004d200  mov     [rsp+138h+var_100], rax
0x18004d205  mov     [rsp+138h+var_108], r13d
0x18004d20a  mov     [rsp+138h+var_110], r12
0x18004d20f  mov     rax, [rsp+138h+var_D8]
0x18004d214  mov     qword ptr [rsp+138h+bAlertable], rax
0x18004d219  lea     r9, [rsp+138h+pAsync]
0x18004d221  xor     r8d, r8d; pReturnValue
0x18004d224  lea     edx, [r8+2Ah]; nProcNum
0x18004d228  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004d22f  call    cs:__imp_Ndr64AsyncClientCall
0x18004d235  mov     eax, [rsp+138h+Reply]
0x18004d239  jmp     short loc_18004D28A
0x18004d23b  test    eax, eax
0x18004d23d  jle     short loc_18004D247
0x18004d23f  movzx   eax, ax
0x18004d242  or      eax, 80070000h
0x18004d247  mov     [rsp+138h+Reply], eax
0x18004d24b  mov     [rsp+138h+bAlertable], eax
0x18004d24f  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004d256  mov     r8d, 3DBh; unsigned int
0x18004d25c  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004d263  mov     ecx, 2; unsigned __int8
0x18004d268  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004d26d  mov     eax, [rsp+138h+Reply]
0x18004d271  test    eax, eax
0x18004d273  js      short loc_18004D27E
0x18004d275  mov     eax, 8000FFFFh
0x18004d27a  mov     [rsp+138h+Reply], eax
0x18004d27e  mov     esi, [rsp+138h+dwMilliseconds]
0x18004d282  mov     r15b, [rsp+138h+var_E4]
0x18004d287  mov     r14b, r15b
0x18004d28a  test    eax, eax
0x18004d28c  jns     short loc_18004D2A0
0x18004d28e  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004d295  mov     r8d, 3DBh
0x18004d29b  jmp     loc_18004D36A
0x18004d2a0  mov     [rsp+138h+bAlertable], 0; bAlertable
0x18004d2a8  mov     r9d, esi; dwMilliseconds
0x18004d2ab  xor     r8d, r8d; bWaitAll
0x18004d2ae  lea     rdx, [rsp+138h+Handles]; lpHandles
0x18004d2b3  lea     ecx, [r8+1]; nCount
0x18004d2b7  call    cs:__imp_WaitForMultipleObjectsEx
0x18004d2bd  mov     esi, eax
0x18004d2bf  mov     r12d, 102h
0x18004d2c5  test    r14b, r14b
0x18004d2c8  jnz     short loc_18004D319
0x18004d2ca  cmp     esi, r12d
0x18004d2cd  jz      short loc_18004D2D4
0x18004d2cf  cmp     esi, 1
0x18004d2d2  jnz     short loc_18004D319
0x18004d2d4  mov     edx, 1; fAbort
0x18004d2d9  lea     rcx, [rsp+138h+pAsync]; pAsync
0x18004d2e1  call    cs:__imp_RpcAsyncCancelCall
0x18004d2e7  cmp     esi, r12d
0x18004d2ea  jnz     short loc_18004D2F1
0x18004d2ec  mov     r15b, 1
0x18004d2ef  jmp     short loc_18004D2F4
0x18004d2f1  mov     r14b, 1
0x18004d2f4  mov     [rsp+138h+bAlertable], 0; bAlertable
0x18004d2fc  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004d300  xor     r8d, r8d; bWaitAll
0x18004d303  lea     rdx, [rsp+138h+Handles]; lpHandles
0x18004d308  lea     ecx, [r8+1]; nCount
0x18004d30c  call    cs:__imp_WaitForMultipleObjectsEx
0x18004d312  mov     esi, eax
0x18004d314  test    r15b, r15b
0x18004d317  jz      short loc_18004D2C5
0x18004d319  test    esi, esi
0x18004d31b  jz      short loc_18004D338
0x18004d31d  call    cs:__imp_GetLastError
0x18004d323  test    eax, eax
0x18004d325  jle     short loc_18004D32F
0x18004d327  movzx   eax, ax
0x18004d32a  or      eax, 80070000h
0x18004d32f  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004d336  jmp     short loc_18004D360
0x18004d338  lea     rdx, [rsp+138h+Reply]; Reply
0x18004d33d  lea     rcx, [rsp+138h+pAsync]; pAsync
0x18004d345  call    cs:__imp_RpcAsyncCompleteCall
0x18004d34b  test    eax, eax
0x18004d34d  jz      short loc_18004D37F
0x18004d34f  jle     short loc_18004D359
0x18004d351  movzx   eax, ax
0x18004d354  or      eax, 80070000h
0x18004d359  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004d360  mov     r8d, 3DBh; unsigned int
0x18004d366  mov     [rsp+138h+Reply], eax
0x18004d36a  mov     [rsp+138h+bAlertable], eax
0x18004d36e  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004d375  mov     ecx, 2; unsigned __int8
0x18004d37a  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004d37f  mov     rcx, qword ptr [rsp+138h+pAsync.u]; hObject
0x18004d387  test    rcx, rcx
0x18004d38a  jz      short loc_18004D392
0x18004d38c  call    cs:__imp_CloseHandle
0x18004d392  test    r15b, r15b
0x18004d395  jz      short loc_18004D3D6
0x18004d397  mov     [rsp+138h+Reply], 800705B4h
0x18004d39f  lea     rdx, [rsp+138h+var_DC]
0x18004d3a4  lea     rcx, aWlidcgetusersf; "WLIDCGetUsersFromSsoGroup"
0x18004d3ab  call    ??$RPCCallTimedOut@AEAY0BK@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BK@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[26],ulong &>(char const (&)[26],ulong &)
0x18004d3b0  mov     eax, [rsp+138h+Reply]
0x18004d3b4  mov     [rsp+138h+bAlertable], eax
0x18004d3b8  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004d3bf  mov     r8d, 3DBh; unsigned int
0x18004d3c5  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004d3cc  mov     ecx, 2; unsigned __int8
0x18004d3d1  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004d3d6  test    r14b, r14b
0x18004d3d9  jz      short loc_18004D406
0x18004d3db  mov     eax, 800704C7h
0x18004d3e0  mov     [rsp+138h+Reply], eax
0x18004d3e4  mov     [rsp+138h+bAlertable], eax
0x18004d3e8  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004d3ef  mov     r8d, 3DBh; unsigned int
0x18004d3f5  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004d3fc  mov     ecx, 2; unsigned __int8
0x18004d401  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004d406  cmp     [rsp+138h+Reply], 800706B5h
0x18004d40e  jz      short loc_18004D41A
0x18004d410  cmp     [rsp+138h+Reply], 800706BAh
0x18004d418  jnz     short loc_18004D41F
0x18004d41a  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004d41f  lea     rcx, [rsp+138h+var_D8]; this
0x18004d424  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18004d429  mov     eax, [rsp+138h+Reply]
0x18004d42d  mov     rcx, [rsp+138h+var_38]
0x18004d435  xor     rcx, rsp; StackCookie
0x18004d438  call    __security_check_cookie
0x18004d43d  add     rsp, 110h
0x18004d444  pop     r15
0x18004d446  pop     r14
0x18004d448  pop     r13
0x18004d44a  pop     r12
0x18004d44c  pop     rsi
0x18004d44d  retn
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
