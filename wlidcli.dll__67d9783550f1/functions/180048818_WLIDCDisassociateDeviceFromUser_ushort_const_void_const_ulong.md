# WLIDCDisassociateDeviceFromUser(ushort const *,void * const,ulong)

- ea: `0x180048818`
- end: `0x180048b3e`
- name: `?WLIDCDisassociateDeviceFromUser@@YAJPEBGQEAXK@Z`
- size: `806`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void *const, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180035d30`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180045530`
- `0x180046ce0`
- `0x180048818`
- `0x18004cd04`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800489c0`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180048a12`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800489c0`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180048a12`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800488e0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800488e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800488f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048a23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800488f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048a23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048a8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048a8f`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800489e7`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800489e7`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180048938`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180048938`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180048a48`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180048a48`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180048899`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180048899`

## string_xrefs

- `0x180048905`: `RPC failed to create new event, hr = %#x`
- `0x180048a5c`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCDisassociateDeviceFromUser(const unsigned __int16 *a1, void *const a2, int a3)
{
  DWORD v5; // esi
  char v6; // r15
  char v7; // r14
  int LastError; // eax
  const unsigned __int16 *v9; // r9
  unsigned int v10; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v12; // esi
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-F8h]
  unsigned int Reply; // [rsp+40h] [rbp-D8h] BYREF
  char v17; // [rsp+44h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-D0h] BYREF
  int v19; // [rsp+4Ch] [rbp-CCh]
  DWORD v20; // [rsp+50h] [rbp-C8h] BYREF
  HANDLE Handles[3]; // [rsp+58h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-A8h] BYREF

  v19 = a3;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v5 = dwMilliseconds;
  v20 = dwMilliseconds;
  v6 = 0;
  v17 = 0;
  v7 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v10 = 925;
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
    v9 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_5;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x25u, 0, &pAsync, a1, a2, v19);
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
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_28;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = L"RPC Async complete call failed, hr = %#x";
  }
  v10 = 927;
LABEL_27:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(2u, "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp", v10, v9, *(_QWORD *)bAlertable);
LABEL_28:
  NotificationRoutine = pAsync.u.APC.NotificationRoutine;
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v6 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[32],unsigned long &>(
      (__int64)NotificationRoutine,
      (int *)&v20);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x39Fu,
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
      0x39Fu,
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
0x180048818  push    rsi
0x18004881a  push    r12
0x18004881c  push    r13
0x18004881e  push    r14
0x180048820  push    r15
0x180048822  sub     rsp, 0F0h
0x180048829  mov     rax, cs:__security_cookie
0x180048830  xor     rax, rsp
0x180048833  mov     [rsp+118h+var_38], rax
0x18004883b  mov     [rsp+118h+var_CC], r8d
0x180048840  mov     r13, rdx
0x180048843  mov     r12, rcx
0x180048846  mov     [rsp+118h+Reply], 0
0x18004884e  mov     [rsp+118h+dwMilliseconds], 0
0x180048856  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x18004885b  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180048860  xor     edx, edx; Val
0x180048862  lea     r8d, [rdx+70h]; Size
0x180048866  lea     rcx, [rsp+118h+pAsync]; void *
0x18004886b  call    memset_0
0x180048870  mov     esi, [rsp+118h+dwMilliseconds]
0x180048874  mov     [rsp+118h+dwMilliseconds], esi
0x180048878  mov     [rsp+118h+var_C8], esi
0x18004887c  xor     r15b, r15b
0x18004887f  mov     [rsp+118h+var_D4], r15b
0x180048884  xor     r14b, r14b
0x180048887  xorps   xmm0, xmm0
0x18004888a  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x18004888f  mov     edx, 70h ; 'p'; Size
0x180048894  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180048899  call    cs:__imp_RpcAsyncInitializeHandle
0x18004889f  test    eax, eax
0x1800488a1  jz      short loc_1800488BF
0x1800488a3  jle     short loc_1800488AD
0x1800488a5  movzx   eax, ax
0x1800488a8  or      eax, 80070000h
0x1800488ad  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x1800488b4  mov     r8d, 39Dh
0x1800488ba  jmp     loc_180048A69
0x1800488bf  mov     [rsp+118h+pAsync.UserInfo], 0
0x1800488cb  mov     [rsp+118h+pAsync.NotificationType], 1
0x1800488d6  xor     r9d, r9d; lpName
0x1800488d9  xor     r8d, r8d; bInitialState
0x1800488dc  xor     edx, edx; bManualReset
0x1800488de  xor     ecx, ecx; lpEventAttributes
0x1800488e0  call    cs:__imp_CreateEventW
0x1800488e6  mov     qword ptr [rsp+118h+pAsync.u], rax
0x1800488ee  test    rax, rax
0x1800488f1  jnz     short loc_18004890E
0x1800488f3  call    cs:__imp_GetLastError
0x1800488f9  test    eax, eax
0x1800488fb  jle     short loc_180048905
0x1800488fd  movzx   eax, ax
0x180048900  or      eax, 80070000h
0x180048905  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004890c  jmp     short loc_1800488B4
0x18004890e  mov     [rsp+118h+Handles], rax
0x180048913  mov     eax, [rsp+118h+var_CC]
0x180048917  mov     [rsp+118h+var_E8], eax
0x18004891b  mov     [rsp+118h+var_F0], r13
0x180048920  mov     qword ptr [rsp+118h+bAlertable], r12
0x180048925  lea     r9, [rsp+118h+pAsync]
0x18004892a  xor     r8d, r8d; pReturnValue
0x18004892d  lea     edx, [r8+25h]; nProcNum
0x180048931  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180048938  call    cs:__imp_Ndr64AsyncClientCall
0x18004893e  mov     eax, [rsp+118h+Reply]
0x180048942  jmp     short loc_180048993
0x180048944  test    eax, eax
0x180048946  jle     short loc_180048950
0x180048948  movzx   eax, ax
0x18004894b  or      eax, 80070000h
0x180048950  mov     [rsp+118h+Reply], eax
0x180048954  mov     [rsp+118h+bAlertable], eax
0x180048958  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004895f  mov     r8d, 39Fh; unsigned int
0x180048965  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004896c  mov     ecx, 2; unsigned __int8
0x180048971  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180048976  mov     eax, [rsp+118h+Reply]
0x18004897a  test    eax, eax
0x18004897c  js      short loc_180048987
0x18004897e  mov     eax, 8000FFFFh
0x180048983  mov     [rsp+118h+Reply], eax
0x180048987  mov     esi, [rsp+118h+dwMilliseconds]
0x18004898b  mov     r15b, [rsp+118h+var_D4]
0x180048990  mov     r14b, r15b
0x180048993  test    eax, eax
0x180048995  jns     short loc_1800489A9
0x180048997  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004899e  mov     r8d, 39Fh
0x1800489a4  jmp     loc_180048A6D
0x1800489a9  mov     [rsp+118h+bAlertable], 0; bAlertable
0x1800489b1  mov     r9d, esi; dwMilliseconds
0x1800489b4  xor     r8d, r8d; bWaitAll
0x1800489b7  lea     rdx, [rsp+118h+Handles]; lpHandles
0x1800489bc  lea     ecx, [r8+1]; nCount
0x1800489c0  call    cs:__imp_WaitForMultipleObjectsEx
0x1800489c6  mov     esi, eax
0x1800489c8  mov     r12d, 102h
0x1800489ce  test    r14b, r14b
0x1800489d1  jnz     short loc_180048A1F
0x1800489d3  cmp     esi, r12d
0x1800489d6  jz      short loc_1800489DD
0x1800489d8  cmp     esi, 1
0x1800489db  jnz     short loc_180048A1F
0x1800489dd  mov     edx, 1; fAbort
0x1800489e2  lea     rcx, [rsp+118h+pAsync]; pAsync
0x1800489e7  call    cs:__imp_RpcAsyncCancelCall
0x1800489ed  cmp     esi, r12d
0x1800489f0  jnz     short loc_1800489F7
0x1800489f2  mov     r15b, 1
0x1800489f5  jmp     short loc_1800489FA
0x1800489f7  mov     r14b, 1
0x1800489fa  mov     [rsp+118h+bAlertable], 0; bAlertable
0x180048a02  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180048a06  xor     r8d, r8d; bWaitAll
0x180048a09  lea     rdx, [rsp+118h+Handles]; lpHandles
0x180048a0e  lea     ecx, [r8+1]; nCount
0x180048a12  call    cs:__imp_WaitForMultipleObjectsEx
0x180048a18  mov     esi, eax
0x180048a1a  test    r15b, r15b
0x180048a1d  jz      short loc_1800489CE
0x180048a1f  test    esi, esi
0x180048a21  jz      short loc_180048A3E
0x180048a23  call    cs:__imp_GetLastError
0x180048a29  test    eax, eax
0x180048a2b  jle     short loc_180048A35
0x180048a2d  movzx   eax, ax
0x180048a30  or      eax, 80070000h
0x180048a35  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180048a3c  jmp     short loc_180048A63
0x180048a3e  lea     rdx, [rsp+118h+Reply]; Reply
0x180048a43  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180048a48  call    cs:__imp_RpcAsyncCompleteCall
0x180048a4e  test    eax, eax
0x180048a50  jz      short loc_180048A82
0x180048a52  jle     short loc_180048A5C
0x180048a54  movzx   eax, ax
0x180048a57  or      eax, 80070000h
0x180048a5c  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180048a63  mov     r8d, 39Fh; unsigned int
0x180048a69  mov     [rsp+118h+Reply], eax
0x180048a6d  mov     [rsp+118h+bAlertable], eax
0x180048a71  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180048a78  mov     ecx, 2; unsigned __int8
0x180048a7d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180048a82  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x180048a8a  test    rcx, rcx
0x180048a8d  jz      short loc_180048A95
0x180048a8f  call    cs:__imp_CloseHandle
0x180048a95  test    r15b, r15b
0x180048a98  jz      short loc_180048AD2
0x180048a9a  mov     [rsp+118h+Reply], 800705B4h
0x180048aa2  lea     rdx, [rsp+118h+var_C8]
0x180048aa7  call    ??$RPCCallTimedOut@AEAY0CA@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0CA@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[32],ulong &>(char const (&)[32],ulong &)
0x180048aac  mov     eax, [rsp+118h+Reply]
0x180048ab0  mov     [rsp+118h+bAlertable], eax
0x180048ab4  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180048abb  mov     r8d, 39Fh; unsigned int
0x180048ac1  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180048ac8  mov     ecx, 2; unsigned __int8
0x180048acd  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180048ad2  test    r14b, r14b
0x180048ad5  jz      short loc_180048B02
0x180048ad7  mov     eax, 800704C7h
0x180048adc  mov     [rsp+118h+Reply], eax
0x180048ae0  mov     [rsp+118h+bAlertable], eax
0x180048ae4  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180048aeb  mov     r8d, 39Fh; unsigned int
0x180048af1  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180048af8  mov     ecx, 2; unsigned __int8
0x180048afd  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180048b02  mov     eax, [rsp+118h+Reply]
0x180048b06  cmp     eax, 800706B5h
0x180048b0b  jz      short loc_180048B14
0x180048b0d  cmp     eax, 800706BAh
0x180048b12  jnz     short loc_180048B1D
0x180048b14  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180048b19  mov     eax, [rsp+118h+Reply]
0x180048b1d  mov     rcx, [rsp+118h+var_38]
0x180048b25  xor     rcx, rsp; StackCookie
0x180048b28  call    __security_check_cookie
0x180048b2d  add     rsp, 0F0h
0x180048b34  pop     r15
0x180048b36  pop     r14
0x180048b38  pop     r13
0x180048b3a  pop     r12
0x180048b3c  pop     rsi
0x180048b3d  retn
0x1800619b3  push    rbp
0x1800619b5  sub     rsp, 40h
0x1800619b9  mov     rbp, rdx
0x1800619bc  mov     rcx, [rcx]
0x1800619bf  mov     ecx, [rcx]; unsigned int
0x1800619c1  call    ?WLIDpExceptionFilter@@YAHK@Z
0x1800619c6  nop
0x1800619c7  add     rsp, 40h
0x1800619cb  pop     rbp
0x1800619cc  retn
```
