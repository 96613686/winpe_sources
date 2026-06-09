# WLIDCEnumerateUserAssociatedDevices(void * const,ulong,ushort *,ulong *,__MIDL_liveidsvc_0003 * *)

- ea: `0x18000e500`
- end: `0x18000e856`
- name: `?WLIDCEnumerateUserAssociatedDevices@@YAJQEAXKPEAGPEAKPEAPEAU__MIDL_liveidsvc_0003@@@Z`
- size: `854`
- prototype: `__int64 __fastcall(void *const, unsigned int, unsigned __int16 *, unsigned int *, struct __MIDL_liveidsvc_0003 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180007b00`
- `0x18000a3e8`

## callees

- `0x1800027f0`
- `0x1800033b4`
- `0x18000c590`
- `0x18000dc00`
- `0x18000e500`
- `0x18000e85c`
- `0x18000f4cc`
- `0x18000fe90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000e6d2`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000e727`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000e6d2`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000e727`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e5db`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e5db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e5ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e738`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e5ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e738`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e7a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e7a7`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000e760`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000e760`
- `RPCRT4!RpcAsyncCancelCall` at `0x18000e6fc`
- `RPCRT4!RpcAsyncCancelCall` at `0x18000e6fc`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18000e64a`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18000e64a`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18000e594`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18000e594`

## string_xrefs

- `0x18000e600`: `RPC failed to create new event, hr = %#x`
- `0x18000e774`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCEnumerateUserAssociatedDevices(
        void *const a1,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned int *a4,
        struct __MIDL_liveidsvc_0003 **a5)
{
  DWORD v7; // esi
  char v8; // r15
  char v9; // r14
  int LastError; // eax
  const unsigned __int16 *v11; // r9
  unsigned int v12; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v14; // esi
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-108h]
  unsigned int Reply; // [rsp+50h] [rbp-D8h] BYREF
  char v19; // [rsp+54h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+58h] [rbp-D0h] BYREF
  DWORD v21; // [rsp+5Ch] [rbp-CCh] BYREF
  struct __MIDL_liveidsvc_0003 **v22; // [rsp+60h] [rbp-C8h]
  unsigned int *v23; // [rsp+68h] [rbp-C0h]
  HANDLE Handles[2]; // [rsp+70h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+80h] [rbp-A8h] BYREF

  v23 = a4;
  v22 = a5;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v7 = dwMilliseconds;
  v21 = dwMilliseconds;
  v8 = 0;
  v19 = 0;
  v9 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v11 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v12 = 938;
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
    v11 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_5;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x26u, 0, &pAsync, a1, 0, a3, v23, v22);
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
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_28;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v11 = L"RPC Async complete call failed, hr = %#x";
  }
  v12 = 940;
LABEL_27:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(
    2u,
    "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
    v12,
    v11,
    *(_QWORD *)bAlertable);
LABEL_28:
  NotificationRoutine = pAsync.u.APC.NotificationRoutine;
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v8 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[36],unsigned long &>(NotificationRoutine, &v21);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x3ACu,
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
      0x3ACu,
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
0x18000e500  push    rsi
0x18000e502  push    r12
0x18000e504  push    r13
0x18000e506  push    r14
0x18000e508  push    r15
0x18000e50a  sub     rsp, 100h
0x18000e511  mov     rax, cs:__security_cookie
0x18000e518  xor     rax, rsp
0x18000e51b  mov     [rsp+128h+var_38], rax
0x18000e523  mov     [rsp+128h+var_C0], r9
0x18000e528  mov     r13, r8
0x18000e52b  mov     r12, rcx
0x18000e52e  mov     rax, [rsp+128h+arg_20]
0x18000e536  mov     [rsp+128h+var_C8], rax
0x18000e53b  mov     [rsp+128h+Reply], 0
0x18000e543  mov     [rsp+128h+dwMilliseconds], 0
0x18000e54b  lea     r8, [rsp+128h+dwMilliseconds]; unsigned int *
0x18000e550  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18000e555  xor     edx, edx; Val
0x18000e557  lea     r8d, [rdx+70h]; Size
0x18000e55b  lea     rcx, [rsp+128h+pAsync]; void *
0x18000e563  call    memset_0
0x18000e568  mov     esi, [rsp+128h+dwMilliseconds]
0x18000e56c  mov     [rsp+128h+dwMilliseconds], esi
0x18000e570  mov     [rsp+128h+var_CC], esi
0x18000e574  xor     r15b, r15b
0x18000e577  mov     [rsp+128h+var_D4], r15b
0x18000e57c  xor     r14b, r14b
0x18000e57f  xorps   xmm0, xmm0
0x18000e582  movups  xmmword ptr [rsp+128h+Handles], xmm0
0x18000e587  mov     edx, 70h ; 'p'; Size
0x18000e58c  lea     rcx, [rsp+128h+pAsync]; pAsync
0x18000e594  call    cs:__imp_RpcAsyncInitializeHandle
0x18000e59a  test    eax, eax
0x18000e59c  jz      short loc_18000E5BA
0x18000e59e  jle     short loc_18000E5A8
0x18000e5a0  movzx   eax, ax
0x18000e5a3  or      eax, 80070000h
0x18000e5a8  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18000e5af  mov     r8d, 3AAh
0x18000e5b5  jmp     loc_18000E781
0x18000e5ba  mov     [rsp+128h+pAsync.UserInfo], 0
0x18000e5c6  mov     [rsp+128h+pAsync.NotificationType], 1
0x18000e5d1  xor     r9d, r9d; lpName
0x18000e5d4  xor     r8d, r8d; bInitialState
0x18000e5d7  xor     edx, edx; bManualReset
0x18000e5d9  xor     ecx, ecx; lpEventAttributes
0x18000e5db  call    cs:__imp_CreateEventW
0x18000e5e1  mov     qword ptr [rsp+128h+pAsync.u], rax
0x18000e5e9  test    rax, rax
0x18000e5ec  jnz     short loc_18000E609
0x18000e5ee  call    cs:__imp_GetLastError
0x18000e5f4  test    eax, eax
0x18000e5f6  jle     short loc_18000E600
0x18000e5f8  movzx   eax, ax
0x18000e5fb  or      eax, 80070000h
0x18000e600  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18000e607  jmp     short loc_18000E5AF
0x18000e609  mov     [rsp+128h+Handles], rax
0x18000e60e  mov     rax, [rsp+128h+var_C8]
0x18000e613  mov     [rsp+128h+var_E8], rax
0x18000e618  mov     rax, [rsp+128h+var_C0]
0x18000e61d  mov     [rsp+128h+var_F0], rax
0x18000e622  mov     [rsp+128h+var_F8], r13
0x18000e627  mov     [rsp+128h+var_100], 0
0x18000e62f  mov     qword ptr [rsp+128h+bAlertable], r12
0x18000e634  lea     r9, [rsp+128h+pAsync]
0x18000e63c  xor     r8d, r8d; pReturnValue
0x18000e63f  lea     edx, [r8+26h]; nProcNum
0x18000e643  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000e64a  call    cs:__imp_Ndr64AsyncClientCall
0x18000e650  mov     eax, [rsp+128h+Reply]
0x18000e654  jmp     short loc_18000E6A5
0x18000e656  test    eax, eax
0x18000e658  jle     short loc_18000E662
0x18000e65a  movzx   eax, ax
0x18000e65d  or      eax, 80070000h
0x18000e662  mov     [rsp+128h+Reply], eax
0x18000e666  mov     [rsp+128h+bAlertable], eax
0x18000e66a  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18000e671  mov     r8d, 3ACh; unsigned int
0x18000e677  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000e67e  mov     ecx, 2; unsigned __int8
0x18000e683  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000e688  mov     eax, [rsp+128h+Reply]
0x18000e68c  test    eax, eax
0x18000e68e  js      short loc_18000E699
0x18000e690  mov     eax, 8000FFFFh
0x18000e695  mov     [rsp+128h+Reply], eax
0x18000e699  mov     esi, [rsp+128h+dwMilliseconds]
0x18000e69d  mov     r15b, [rsp+128h+var_D4]
0x18000e6a2  mov     r14b, r15b
0x18000e6a5  test    eax, eax
0x18000e6a7  jns     short loc_18000E6BB
0x18000e6a9  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18000e6b0  mov     r8d, 3ACh
0x18000e6b6  jmp     loc_18000E785
0x18000e6bb  mov     [rsp+128h+bAlertable], 0; bAlertable
0x18000e6c3  mov     r9d, esi; dwMilliseconds
0x18000e6c6  xor     r8d, r8d; bWaitAll
0x18000e6c9  lea     rdx, [rsp+128h+Handles]; lpHandles
0x18000e6ce  lea     ecx, [r8+1]; nCount
0x18000e6d2  call    cs:__imp_WaitForMultipleObjectsEx
0x18000e6d8  mov     esi, eax
0x18000e6da  mov     r12d, 102h
0x18000e6e0  test    r14b, r14b
0x18000e6e3  jnz     short loc_18000E734
0x18000e6e5  cmp     esi, r12d
0x18000e6e8  jz      short loc_18000E6EF
0x18000e6ea  cmp     esi, 1
0x18000e6ed  jnz     short loc_18000E734
0x18000e6ef  mov     edx, 1; fAbort
0x18000e6f4  lea     rcx, [rsp+128h+pAsync]; pAsync
0x18000e6fc  call    cs:__imp_RpcAsyncCancelCall
0x18000e702  cmp     esi, r12d
0x18000e705  jnz     short loc_18000E70C
0x18000e707  mov     r15b, 1
0x18000e70a  jmp     short loc_18000E70F
0x18000e70c  mov     r14b, 1
0x18000e70f  mov     [rsp+128h+bAlertable], 0; bAlertable
0x18000e717  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18000e71b  xor     r8d, r8d; bWaitAll
0x18000e71e  lea     rdx, [rsp+128h+Handles]; lpHandles
0x18000e723  lea     ecx, [r8+1]; nCount
0x18000e727  call    cs:__imp_WaitForMultipleObjectsEx
0x18000e72d  mov     esi, eax
0x18000e72f  test    r15b, r15b
0x18000e732  jz      short loc_18000E6E0
0x18000e734  test    esi, esi
0x18000e736  jz      short loc_18000E753
0x18000e738  call    cs:__imp_GetLastError
0x18000e73e  test    eax, eax
0x18000e740  jle     short loc_18000E74A
0x18000e742  movzx   eax, ax
0x18000e745  or      eax, 80070000h
0x18000e74a  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18000e751  jmp     short loc_18000E77B
0x18000e753  lea     rdx, [rsp+128h+Reply]; Reply
0x18000e758  lea     rcx, [rsp+128h+pAsync]; pAsync
0x18000e760  call    cs:__imp_RpcAsyncCompleteCall
0x18000e766  test    eax, eax
0x18000e768  jz      short loc_18000E79A
0x18000e76a  jle     short loc_18000E774
0x18000e76c  movzx   eax, ax
0x18000e76f  or      eax, 80070000h
0x18000e774  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18000e77b  mov     r8d, 3ACh; unsigned int
0x18000e781  mov     [rsp+128h+Reply], eax
0x18000e785  mov     [rsp+128h+bAlertable], eax
0x18000e789  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000e790  mov     ecx, 2; unsigned __int8
0x18000e795  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000e79a  mov     rcx, qword ptr [rsp+128h+pAsync.u]; hObject
0x18000e7a2  test    rcx, rcx
0x18000e7a5  jz      short loc_18000E7AD
0x18000e7a7  call    cs:__imp_CloseHandle
0x18000e7ad  test    r15b, r15b
0x18000e7b0  jz      short loc_18000E7EA
0x18000e7b2  mov     [rsp+128h+Reply], 800705B4h
0x18000e7ba  lea     rdx, [rsp+128h+var_CC]
0x18000e7bf  call    ??$RPCCallTimedOut@AEAY0CE@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0CE@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[36],ulong &>(char const (&)[36],ulong &)
0x18000e7c4  mov     eax, [rsp+128h+Reply]
0x18000e7c8  mov     [rsp+128h+bAlertable], eax
0x18000e7cc  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18000e7d3  mov     r8d, 3ACh; unsigned int
0x18000e7d9  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000e7e0  mov     ecx, 2; unsigned __int8
0x18000e7e5  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000e7ea  test    r14b, r14b
0x18000e7ed  jz      short loc_18000E81A
0x18000e7ef  mov     eax, 800704C7h
0x18000e7f4  mov     [rsp+128h+Reply], eax
0x18000e7f8  mov     [rsp+128h+bAlertable], eax
0x18000e7fc  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18000e803  mov     r8d, 3ACh; unsigned int
0x18000e809  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000e810  mov     ecx, 2; unsigned __int8
0x18000e815  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000e81a  mov     eax, [rsp+128h+Reply]
0x18000e81e  cmp     eax, 800706B5h
0x18000e823  jz      short loc_18000E82C
0x18000e825  cmp     eax, 800706BAh
0x18000e82a  jnz     short loc_18000E835
0x18000e82c  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18000e831  mov     eax, [rsp+128h+Reply]
0x18000e835  mov     rcx, [rsp+128h+var_38]
0x18000e83d  xor     rcx, rsp; StackCookie
0x18000e840  call    __security_check_cookie
0x18000e845  add     rsp, 100h
0x18000e84c  pop     r15
0x18000e84e  pop     r14
0x18000e850  pop     r13
0x18000e852  pop     r12
0x18000e854  pop     rsi
0x18000e855  retn
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
