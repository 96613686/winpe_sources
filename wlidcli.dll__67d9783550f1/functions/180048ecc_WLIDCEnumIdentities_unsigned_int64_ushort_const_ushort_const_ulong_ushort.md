# WLIDCEnumIdentities(unsigned __int64,ushort const *,ushort const *,ulong *,ushort * * *)

- ea: `0x180048ecc`
- end: `0x18004925f`
- name: `?WLIDCEnumIdentities@@YAJ_KPEBG1PEAKPEAPEAPEAG@Z`
- size: `915`
- prototype: `__int64 __fastcall(unsigned __int64, const unsigned __int16 *, const unsigned __int16 *, unsigned int *, unsigned __int16 ***)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002abc0`
- `0x180040ff8`
- `0x180041114`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180044f38`
- `0x180046ce0`
- `0x180048ecc`
- `0x18004cd04`
- `0x180050c84`
- `0x180050e40`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800490c8`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004911d`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800490c8`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004911d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180048fc6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180048fc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048fd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004912e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048fd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004912e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004919d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004919d`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800490f2`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800490f2`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180049040`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180049040`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180049156`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180049156`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180048f7f`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180048f7f`

## string_xrefs

- `0x180048feb`: `RPC failed to create new event, hr = %#x`
- `0x18004916a`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCEnumIdentities(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int *a4,
        unsigned __int16 ***a5)
{
  __int64 result; // rax
  DWORD v8; // esi
  char v9; // r15
  char v10; // r14
  int LastError; // eax
  const unsigned __int16 *v12; // r9
  unsigned int v13; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v15; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-118h]
  int Reply; // [rsp+50h] [rbp-E8h] BYREF
  char v18; // [rsp+54h] [rbp-E4h]
  DWORD dwMilliseconds; // [rsp+58h] [rbp-E0h] BYREF
  DWORD v20; // [rsp+5Ch] [rbp-DCh] BYREF
  __int64 v21; // [rsp+60h] [rbp-D8h] BYREF
  unsigned __int16 ***v22; // [rsp+68h] [rbp-D0h]
  unsigned int *v23; // [rsp+70h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+78h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+90h] [rbp-A8h] BYREF

  v23 = a4;
  v22 = a5;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue(a1, (unsigned int)a2, &dwMilliseconds);
  v21 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v21);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v8 = dwMilliseconds;
  v20 = dwMilliseconds;
  v9 = 0;
  v18 = 0;
  v10 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v12 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v13 = 812;
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
    v12 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x19u, 0, &pAsync, v21, a1, a2, 0, v23, v22);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v12 = L"RPC call failed, hr = %#x";
    v13 = 814;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v13,
      v12,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
  v15 = WaitForMultipleObjectsEx(1u, Handles, 0, v8, 0);
  do
  {
    if ( v10 || v15 != 258 && v15 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v15 == 258 )
      v9 = 1;
    else
      v10 = 1;
    v15 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v9 );
  if ( v15 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v12 = L"Encountered error while waiting on RPC call, hr = %#x";
LABEL_29:
    v13 = 814;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v12 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v9 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[20],unsigned long &>(
      (__int64)"WLIDCEnumIdentities",
      (int *)&v20);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x32Eu,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v10 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x32Eu,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v21);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x180048ecc  push    rsi
0x180048ece  push    r12
0x180048ed0  push    r13
0x180048ed2  push    r14
0x180048ed4  push    r15
0x180048ed6  sub     rsp, 110h
0x180048edd  mov     rax, cs:__security_cookie
0x180048ee4  xor     rax, rsp
0x180048ee7  mov     [rsp+138h+var_38], rax
0x180048eef  mov     [rsp+138h+var_C8], r9
0x180048ef4  mov     r13, rdx
0x180048ef7  mov     r12, rcx
0x180048efa  mov     rax, [rsp+138h+arg_20]
0x180048f02  mov     [rsp+138h+var_D0], rax
0x180048f07  mov     [rsp+138h+dwMilliseconds], 0
0x180048f0f  lea     r8, [rsp+138h+dwMilliseconds]; unsigned int *
0x180048f14  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180048f19  mov     [rsp+138h+Reply], 0
0x180048f21  mov     [rsp+138h+var_D8], 0
0x180048f2a  lea     rcx, [rsp+138h+var_D8]; this
0x180048f2f  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x180048f34  mov     [rsp+138h+Reply], eax
0x180048f38  test    eax, eax
0x180048f3a  js      loc_18004923E
0x180048f40  xor     edx, edx; Val
0x180048f42  lea     r8d, [rdx+70h]; Size
0x180048f46  lea     rcx, [rsp+138h+pAsync]; void *
0x180048f4e  call    memset_0
0x180048f53  mov     esi, [rsp+138h+dwMilliseconds]
0x180048f57  mov     [rsp+138h+dwMilliseconds], esi
0x180048f5b  mov     [rsp+138h+var_DC], esi
0x180048f5f  xor     r15b, r15b
0x180048f62  mov     [rsp+138h+var_E4], r15b
0x180048f67  xor     r14b, r14b
0x180048f6a  xorps   xmm0, xmm0
0x180048f6d  movups  xmmword ptr [rsp+138h+Handles], xmm0
0x180048f72  mov     edx, 70h ; 'p'; Size
0x180048f77  lea     rcx, [rsp+138h+pAsync]; pAsync
0x180048f7f  call    cs:__imp_RpcAsyncInitializeHandle
0x180048f85  test    eax, eax
0x180048f87  jz      short loc_180048FA5
0x180048f89  jle     short loc_180048F93
0x180048f8b  movzx   eax, ax
0x180048f8e  or      eax, 80070000h
0x180048f93  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180048f9a  mov     r8d, 32Ch
0x180048fa0  jmp     loc_180049177
0x180048fa5  mov     [rsp+138h+pAsync.UserInfo], 0
0x180048fb1  mov     [rsp+138h+pAsync.NotificationType], 1
0x180048fbc  xor     r9d, r9d; lpName
0x180048fbf  xor     r8d, r8d; bInitialState
0x180048fc2  xor     edx, edx; bManualReset
0x180048fc4  xor     ecx, ecx; lpEventAttributes
0x180048fc6  call    cs:__imp_CreateEventW
0x180048fcc  mov     qword ptr [rsp+138h+pAsync.u], rax
0x180048fd4  test    rax, rax
0x180048fd7  jnz     short loc_180048FF4
0x180048fd9  call    cs:__imp_GetLastError
0x180048fdf  test    eax, eax
0x180048fe1  jle     short loc_180048FEB
0x180048fe3  movzx   eax, ax
0x180048fe6  or      eax, 80070000h
0x180048feb  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180048ff2  jmp     short loc_180048F9A
0x180048ff4  mov     [rsp+138h+Handles], rax
0x180048ff9  mov     rax, [rsp+138h+var_D0]
0x180048ffe  mov     [rsp+138h+var_F0], rax
0x180049003  mov     rax, [rsp+138h+var_C8]
0x180049008  mov     [rsp+138h+var_F8], rax
0x18004900d  mov     [rsp+138h+var_100], 0
0x180049016  mov     [rsp+138h+var_108], r13
0x18004901b  mov     [rsp+138h+var_110], r12
0x180049020  mov     rax, [rsp+138h+var_D8]
0x180049025  mov     qword ptr [rsp+138h+bAlertable], rax
0x18004902a  lea     r9, [rsp+138h+pAsync]
0x180049032  xor     r8d, r8d; pReturnValue
0x180049035  lea     edx, [r8+19h]; nProcNum
0x180049039  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180049040  call    cs:__imp_Ndr64AsyncClientCall
0x180049046  mov     eax, [rsp+138h+Reply]
0x18004904a  jmp     short loc_18004909B
0x18004904c  test    eax, eax
0x18004904e  jle     short loc_180049058
0x180049050  movzx   eax, ax
0x180049053  or      eax, 80070000h
0x180049058  mov     [rsp+138h+Reply], eax
0x18004905c  mov     [rsp+138h+bAlertable], eax
0x180049060  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180049067  mov     r8d, 32Eh; unsigned int
0x18004906d  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180049074  mov     ecx, 2; unsigned __int8
0x180049079  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004907e  mov     eax, [rsp+138h+Reply]
0x180049082  test    eax, eax
0x180049084  js      short loc_18004908F
0x180049086  mov     eax, 8000FFFFh
0x18004908b  mov     [rsp+138h+Reply], eax
0x18004908f  mov     esi, [rsp+138h+dwMilliseconds]
0x180049093  mov     r15b, [rsp+138h+var_E4]
0x180049098  mov     r14b, r15b
0x18004909b  test    eax, eax
0x18004909d  jns     short loc_1800490B1
0x18004909f  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x1800490a6  mov     r8d, 32Eh
0x1800490ac  jmp     loc_18004917B
0x1800490b1  mov     [rsp+138h+bAlertable], 0; bAlertable
0x1800490b9  mov     r9d, esi; dwMilliseconds
0x1800490bc  xor     r8d, r8d; bWaitAll
0x1800490bf  lea     rdx, [rsp+138h+Handles]; lpHandles
0x1800490c4  lea     ecx, [r8+1]; nCount
0x1800490c8  call    cs:__imp_WaitForMultipleObjectsEx
0x1800490ce  mov     esi, eax
0x1800490d0  mov     r12d, 102h
0x1800490d6  test    r14b, r14b
0x1800490d9  jnz     short loc_18004912A
0x1800490db  cmp     esi, r12d
0x1800490de  jz      short loc_1800490E5
0x1800490e0  cmp     esi, 1
0x1800490e3  jnz     short loc_18004912A
0x1800490e5  mov     edx, 1; fAbort
0x1800490ea  lea     rcx, [rsp+138h+pAsync]; pAsync
0x1800490f2  call    cs:__imp_RpcAsyncCancelCall
0x1800490f8  cmp     esi, r12d
0x1800490fb  jnz     short loc_180049102
0x1800490fd  mov     r15b, 1
0x180049100  jmp     short loc_180049105
0x180049102  mov     r14b, 1
0x180049105  mov     [rsp+138h+bAlertable], 0; bAlertable
0x18004910d  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180049111  xor     r8d, r8d; bWaitAll
0x180049114  lea     rdx, [rsp+138h+Handles]; lpHandles
0x180049119  lea     ecx, [r8+1]; nCount
0x18004911d  call    cs:__imp_WaitForMultipleObjectsEx
0x180049123  mov     esi, eax
0x180049125  test    r15b, r15b
0x180049128  jz      short loc_1800490D6
0x18004912a  test    esi, esi
0x18004912c  jz      short loc_180049149
0x18004912e  call    cs:__imp_GetLastError
0x180049134  test    eax, eax
0x180049136  jle     short loc_180049140
0x180049138  movzx   eax, ax
0x18004913b  or      eax, 80070000h
0x180049140  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180049147  jmp     short loc_180049171
0x180049149  lea     rdx, [rsp+138h+Reply]; Reply
0x18004914e  lea     rcx, [rsp+138h+pAsync]; pAsync
0x180049156  call    cs:__imp_RpcAsyncCompleteCall
0x18004915c  test    eax, eax
0x18004915e  jz      short loc_180049190
0x180049160  jle     short loc_18004916A
0x180049162  movzx   eax, ax
0x180049165  or      eax, 80070000h
0x18004916a  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180049171  mov     r8d, 32Eh; unsigned int
0x180049177  mov     [rsp+138h+Reply], eax
0x18004917b  mov     [rsp+138h+bAlertable], eax
0x18004917f  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180049186  mov     ecx, 2; unsigned __int8
0x18004918b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180049190  mov     rcx, qword ptr [rsp+138h+pAsync.u]; hObject
0x180049198  test    rcx, rcx
0x18004919b  jz      short loc_1800491A3
0x18004919d  call    cs:__imp_CloseHandle
0x1800491a3  test    r15b, r15b
0x1800491a6  jz      short loc_1800491E7
0x1800491a8  mov     [rsp+138h+Reply], 800705B4h
0x1800491b0  lea     rdx, [rsp+138h+var_DC]
0x1800491b5  lea     rcx, aWlidcenumident; "WLIDCEnumIdentities"
0x1800491bc  call    ??$RPCCallTimedOut@AEAY0BE@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BE@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[20],ulong &>(char const (&)[20],ulong &)
0x1800491c1  mov     eax, [rsp+138h+Reply]
0x1800491c5  mov     [rsp+138h+bAlertable], eax
0x1800491c9  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x1800491d0  mov     r8d, 32Eh; unsigned int
0x1800491d6  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800491dd  mov     ecx, 2; unsigned __int8
0x1800491e2  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800491e7  test    r14b, r14b
0x1800491ea  jz      short loc_180049217
0x1800491ec  mov     eax, 800704C7h
0x1800491f1  mov     [rsp+138h+Reply], eax
0x1800491f5  mov     [rsp+138h+bAlertable], eax
0x1800491f9  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180049200  mov     r8d, 32Eh; unsigned int
0x180049206  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004920d  mov     ecx, 2; unsigned __int8
0x180049212  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180049217  cmp     [rsp+138h+Reply], 800706B5h
0x18004921f  jz      short loc_18004922B
0x180049221  cmp     [rsp+138h+Reply], 800706BAh
0x180049229  jnz     short loc_180049230
0x18004922b  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180049230  lea     rcx, [rsp+138h+var_D8]; this
0x180049235  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18004923a  mov     eax, [rsp+138h+Reply]
0x18004923e  mov     rcx, [rsp+138h+var_38]
0x180049246  xor     rcx, rsp; StackCookie
0x180049249  call    __security_check_cookie
0x18004924e  add     rsp, 110h
0x180049255  pop     r15
0x180049257  pop     r14
0x180049259  pop     r13
0x18004925b  pop     r12
0x18004925d  pop     rsi
0x18004925e  retn
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
