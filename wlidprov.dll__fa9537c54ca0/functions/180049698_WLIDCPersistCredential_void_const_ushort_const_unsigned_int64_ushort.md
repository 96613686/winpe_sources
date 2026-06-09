# WLIDCPersistCredential(void * const,ushort const *,unsigned __int64,ushort * *)

- ea: `0x180049698`
- end: `0x1800499fa`
- name: `?WLIDCPersistCredential@@YAJQEAXPEBG_KPEAPEAG@Z`
- size: `866`
- prototype: `__int64 __fastcall(void *const, const unsigned __int16 *, unsigned __int64, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800238ec`
- `0x180041890`

## callees

- `0x18000a400`
- `0x180010c68`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180041d98`
- `0x180043240`
- `0x180049698`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180049774`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180049774`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004986f`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800498c4`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004986f`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800498c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049787`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800498d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049787`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800498d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049944`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049944`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004972d`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004972d`
- `RPCRT4!RpcAsyncCancelCall` at `0x180049899`
- `RPCRT4!RpcAsyncCancelCall` at `0x180049899`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800497e7`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800497e7`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800498fd`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800498fd`

## string_xrefs

- `0x180049799`: `RPC failed to create new event, hr = %#x`
- `0x180049911`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCPersistCredential(
        void *const a1,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 **a4)
{
  DWORD v6; // esi
  char v7; // r15
  char v8; // r14
  int LastError; // eax
  const unsigned __int16 *v10; // r9
  unsigned int v11; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  unsigned __int16 **v13; // rax
  DWORD v14; // esi
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-108h]
  unsigned int Reply; // [rsp+40h] [rbp-E8h] BYREF
  char v18; // [rsp+44h] [rbp-E4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-E0h] BYREF
  DWORD v20; // [rsp+4Ch] [rbp-DCh] BYREF
  __int64 v21; // [rsp+50h] [rbp-D8h] BYREF
  __int64 v22; // [rsp+58h] [rbp-D0h]
  const unsigned __int16 *v23; // [rsp+60h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+68h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+80h] [rbp-A8h] BYREF

  v22 = a3;
  v23 = a2;
  v21 = 0;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v6 = dwMilliseconds;
  v20 = dwMilliseconds;
  v7 = 0;
  v18 = 0;
  v8 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v11 = 840;
    goto LABEL_29;
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
    goto LABEL_5;
  }
  Handles[0] = EventW;
  v13 = (unsigned __int16 **)&v21;
  if ( a4 )
    v13 = a4;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x1Bu, 0, &pAsync, a1, v23, v22, v13);
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
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_30;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC Async complete call failed, hr = %#x";
  }
  v11 = 847;
LABEL_29:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(
    2u,
    "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
    v11,
    v10,
    *(_QWORD *)bAlertable);
LABEL_30:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v7 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[23],unsigned long &>("WLIDCPersistCredential", &v20);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x34Fu,
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
      0x34Fu,
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
0x180049698  push    rsi
0x18004969a  push    r12
0x18004969c  push    r13
0x18004969e  push    r14
0x1800496a0  push    r15
0x1800496a2  sub     rsp, 100h
0x1800496a9  mov     rax, cs:__security_cookie
0x1800496b0  xor     rax, rsp
0x1800496b3  mov     [rsp+128h+var_38], rax
0x1800496bb  mov     r12, r9
0x1800496be  mov     [rsp+128h+var_D0], r8
0x1800496c3  mov     [rsp+128h+var_C8], rdx
0x1800496c8  mov     r13, rcx
0x1800496cb  mov     [rsp+128h+var_D8], 0
0x1800496d4  mov     [rsp+128h+Reply], 0
0x1800496dc  mov     [rsp+128h+dwMilliseconds], 0
0x1800496e4  lea     r8, [rsp+128h+dwMilliseconds]; unsigned int *
0x1800496e9  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x1800496ee  xor     edx, edx; Val
0x1800496f0  lea     r8d, [rdx+70h]; Size
0x1800496f4  lea     rcx, [rsp+128h+pAsync]; void *
0x1800496fc  call    memset_0
0x180049701  mov     esi, [rsp+128h+dwMilliseconds]
0x180049705  mov     [rsp+128h+dwMilliseconds], esi
0x180049709  mov     [rsp+128h+var_DC], esi
0x18004970d  xor     r15b, r15b
0x180049710  mov     [rsp+128h+var_E4], r15b
0x180049715  xor     r14b, r14b
0x180049718  xorps   xmm0, xmm0
0x18004971b  movups  xmmword ptr [rsp+128h+Handles], xmm0
0x180049720  mov     edx, 70h ; 'p'; Size
0x180049725  lea     rcx, [rsp+128h+pAsync]; pAsync
0x18004972d  call    cs:__imp_RpcAsyncInitializeHandle
0x180049733  test    eax, eax
0x180049735  jz      short loc_180049753
0x180049737  jle     short loc_180049741
0x180049739  movzx   eax, ax
0x18004973c  or      eax, 80070000h
0x180049741  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180049748  mov     r8d, 348h
0x18004974e  jmp     loc_18004991E
0x180049753  mov     [rsp+128h+pAsync.UserInfo], 0
0x18004975f  mov     [rsp+128h+pAsync.NotificationType], 1
0x18004976a  xor     r9d, r9d; lpName
0x18004976d  xor     r8d, r8d; bInitialState
0x180049770  xor     edx, edx; bManualReset
0x180049772  xor     ecx, ecx; lpEventAttributes
0x180049774  call    cs:__imp_CreateEventW
0x18004977a  mov     qword ptr [rsp+128h+pAsync.u], rax
0x180049782  test    rax, rax
0x180049785  jnz     short loc_1800497A2
0x180049787  call    cs:__imp_GetLastError
0x18004978d  test    eax, eax
0x18004978f  jle     short loc_180049799
0x180049791  movzx   eax, ax
0x180049794  or      eax, 80070000h
0x180049799  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x1800497a0  jmp     short loc_180049748
0x1800497a2  mov     [rsp+128h+Handles], rax
0x1800497a7  lea     rax, [rsp+128h+var_D8]
0x1800497ac  test    r12, r12
0x1800497af  cmovnz  rax, r12
0x1800497b3  mov     [rsp+128h+var_F0], rax
0x1800497b8  mov     rax, [rsp+128h+var_D0]
0x1800497bd  mov     [rsp+128h+var_F8], rax
0x1800497c2  mov     rax, [rsp+128h+var_C8]
0x1800497c7  mov     [rsp+128h+var_100], rax
0x1800497cc  mov     qword ptr [rsp+128h+bAlertable], r13
0x1800497d1  lea     r9, [rsp+128h+pAsync]
0x1800497d9  xor     r8d, r8d; pReturnValue
0x1800497dc  lea     edx, [r8+1Bh]; nProcNum
0x1800497e0  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800497e7  call    cs:__imp_Ndr64AsyncClientCall
0x1800497ed  mov     eax, [rsp+128h+Reply]
0x1800497f1  jmp     short loc_180049842
0x1800497f3  test    eax, eax
0x1800497f5  jle     short loc_1800497FF
0x1800497f7  movzx   eax, ax
0x1800497fa  or      eax, 80070000h
0x1800497ff  mov     [rsp+128h+Reply], eax
0x180049803  mov     [rsp+128h+bAlertable], eax
0x180049807  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004980e  mov     r8d, 34Fh; unsigned int
0x180049814  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004981b  mov     ecx, 2; unsigned __int8
0x180049820  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180049825  mov     eax, [rsp+128h+Reply]
0x180049829  test    eax, eax
0x18004982b  js      short loc_180049836
0x18004982d  mov     eax, 8000FFFFh
0x180049832  mov     [rsp+128h+Reply], eax
0x180049836  mov     esi, [rsp+128h+dwMilliseconds]
0x18004983a  mov     r15b, [rsp+128h+var_E4]
0x18004983f  mov     r14b, r15b
0x180049842  test    eax, eax
0x180049844  jns     short loc_180049858
0x180049846  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004984d  mov     r8d, 34Fh
0x180049853  jmp     loc_180049922
0x180049858  mov     [rsp+128h+bAlertable], 0; bAlertable
0x180049860  mov     r9d, esi; dwMilliseconds
0x180049863  xor     r8d, r8d; bWaitAll
0x180049866  lea     rdx, [rsp+128h+Handles]; lpHandles
0x18004986b  lea     ecx, [r8+1]; nCount
0x18004986f  call    cs:__imp_WaitForMultipleObjectsEx
0x180049875  mov     esi, eax
0x180049877  mov     r12d, 102h
0x18004987d  test    r14b, r14b
0x180049880  jnz     short loc_1800498D1
0x180049882  cmp     esi, r12d
0x180049885  jz      short loc_18004988C
0x180049887  cmp     esi, 1
0x18004988a  jnz     short loc_1800498D1
0x18004988c  mov     edx, 1; fAbort
0x180049891  lea     rcx, [rsp+128h+pAsync]; pAsync
0x180049899  call    cs:__imp_RpcAsyncCancelCall
0x18004989f  cmp     esi, r12d
0x1800498a2  jnz     short loc_1800498A9
0x1800498a4  mov     r15b, 1
0x1800498a7  jmp     short loc_1800498AC
0x1800498a9  mov     r14b, 1
0x1800498ac  mov     [rsp+128h+bAlertable], 0; bAlertable
0x1800498b4  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800498b8  xor     r8d, r8d; bWaitAll
0x1800498bb  lea     rdx, [rsp+128h+Handles]; lpHandles
0x1800498c0  lea     ecx, [r8+1]; nCount
0x1800498c4  call    cs:__imp_WaitForMultipleObjectsEx
0x1800498ca  mov     esi, eax
0x1800498cc  test    r15b, r15b
0x1800498cf  jz      short loc_18004987D
0x1800498d1  test    esi, esi
0x1800498d3  jz      short loc_1800498F0
0x1800498d5  call    cs:__imp_GetLastError
0x1800498db  test    eax, eax
0x1800498dd  jle     short loc_1800498E7
0x1800498df  movzx   eax, ax
0x1800498e2  or      eax, 80070000h
0x1800498e7  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x1800498ee  jmp     short loc_180049918
0x1800498f0  lea     rdx, [rsp+128h+Reply]; Reply
0x1800498f5  lea     rcx, [rsp+128h+pAsync]; pAsync
0x1800498fd  call    cs:__imp_RpcAsyncCompleteCall
0x180049903  test    eax, eax
0x180049905  jz      short loc_180049937
0x180049907  jle     short loc_180049911
0x180049909  movzx   eax, ax
0x18004990c  or      eax, 80070000h
0x180049911  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180049918  mov     r8d, 34Fh; unsigned int
0x18004991e  mov     [rsp+128h+Reply], eax
0x180049922  mov     [rsp+128h+bAlertable], eax
0x180049926  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004992d  mov     ecx, 2; unsigned __int8
0x180049932  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180049937  mov     rcx, qword ptr [rsp+128h+pAsync.u]; hObject
0x18004993f  test    rcx, rcx
0x180049942  jz      short loc_18004994A
0x180049944  call    cs:__imp_CloseHandle
0x18004994a  test    r15b, r15b
0x18004994d  jz      short loc_18004998E
0x18004994f  mov     [rsp+128h+Reply], 800705B4h
0x180049957  lea     rdx, [rsp+128h+var_DC]
0x18004995c  lea     rcx, aWlidcpersistcr_0; "WLIDCPersistCredential"
0x180049963  call    ??$RPCCallTimedOut@AEAY0BH@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BH@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[23],ulong &>(char const (&)[23],ulong &)
0x180049968  mov     eax, [rsp+128h+Reply]
0x18004996c  mov     [rsp+128h+bAlertable], eax
0x180049970  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180049977  mov     r8d, 34Fh; unsigned int
0x18004997d  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180049984  mov     ecx, 2; unsigned __int8
0x180049989  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004998e  test    r14b, r14b
0x180049991  jz      short loc_1800499BE
0x180049993  mov     eax, 800704C7h
0x180049998  mov     [rsp+128h+Reply], eax
0x18004999c  mov     [rsp+128h+bAlertable], eax
0x1800499a0  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x1800499a7  mov     r8d, 34Fh; unsigned int
0x1800499ad  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800499b4  mov     ecx, 2; unsigned __int8
0x1800499b9  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800499be  mov     eax, [rsp+128h+Reply]
0x1800499c2  cmp     eax, 800706B5h
0x1800499c7  jz      short loc_1800499D0
0x1800499c9  cmp     eax, 800706BAh
0x1800499ce  jnz     short loc_1800499D9
0x1800499d0  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x1800499d5  mov     eax, [rsp+128h+Reply]
0x1800499d9  mov     rcx, [rsp+128h+var_38]
0x1800499e1  xor     rcx, rsp; StackCookie
0x1800499e4  call    __security_check_cookie
0x1800499e9  add     rsp, 100h
0x1800499f0  pop     r15
0x1800499f2  pop     r14
0x1800499f4  pop     r13
0x1800499f6  pop     r12
0x1800499f8  pop     rsi
0x1800499f9  retn
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
