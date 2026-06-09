# WLIDCGetUserExtendedProperty(ushort const *,ushort const *,ushort * *)

- ea: `0x18004cd60`
- end: `0x18004d0c4`
- name: `?WLIDCGetUserExtendedProperty@@YAJPEBG0PEAPEAG@Z`
- size: `868`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002f130`
- `0x180030490`
- `0x180034500`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180045394`
- `0x180046ce0`
- `0x18004cd04`
- `0x18004cd60`
- `0x180050c84`
- `0x180050e40`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004cf33`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004cf85`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004cf33`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004cf85`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004ce47`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004ce47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ce5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cf96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ce5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cf96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d002`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d002`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004cf5a`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004cf5a`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004ceab`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004ceab`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004cfbb`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004cfbb`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004ce00`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004ce00`

## string_xrefs

- `0x18004ce6c`: `RPC failed to create new event, hr = %#x`
- `0x18004cfcf`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCGetUserExtendedProperty(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
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
  unsigned __int16 **v20; // [rsp+58h] [rbp-C0h]
  HANDLE Handles[2]; // [rsp+60h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-A8h] BYREF

  v20 = a3;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
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
    v11 = 753;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x14u, 0, &pAsync, v19, a1, a2, v20);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v10 = L"RPC call failed, hr = %#x";
    v11 = 755;
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
    v11 = 755;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[29],unsigned long &>(
      (__int64)"WLIDCGetUserExtendedProperty",
      (int *)&v18);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x2F3u,
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
      0x2F3u,
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
0x18004cd60  push    rsi
0x18004cd62  push    r12
0x18004cd64  push    r13
0x18004cd66  push    r14
0x18004cd68  push    r15
0x18004cd6a  sub     rsp, 0F0h
0x18004cd71  mov     rax, cs:__security_cookie
0x18004cd78  xor     rax, rsp
0x18004cd7b  mov     [rsp+118h+var_38], rax
0x18004cd83  mov     [rsp+118h+var_C0], r8
0x18004cd88  mov     r13, rdx
0x18004cd8b  mov     r12, rcx
0x18004cd8e  mov     [rsp+118h+dwMilliseconds], 0
0x18004cd96  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x18004cd9b  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004cda0  mov     [rsp+118h+Reply], 0
0x18004cda8  mov     [rsp+118h+var_C8], 0
0x18004cdb1  lea     rcx, [rsp+118h+var_C8]; this
0x18004cdb6  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18004cdbb  mov     [rsp+118h+Reply], eax
0x18004cdbf  test    eax, eax
0x18004cdc1  js      loc_18004D0A3
0x18004cdc7  xor     edx, edx; Val
0x18004cdc9  lea     r8d, [rdx+70h]; Size
0x18004cdcd  lea     rcx, [rsp+118h+pAsync]; void *
0x18004cdd2  call    memset_0
0x18004cdd7  mov     esi, [rsp+118h+dwMilliseconds]
0x18004cddb  mov     [rsp+118h+dwMilliseconds], esi
0x18004cddf  mov     [rsp+118h+var_CC], esi
0x18004cde3  xor     r15b, r15b
0x18004cde6  mov     [rsp+118h+var_D4], r15b
0x18004cdeb  xor     r14b, r14b
0x18004cdee  xorps   xmm0, xmm0
0x18004cdf1  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x18004cdf6  mov     edx, 70h ; 'p'; Size
0x18004cdfb  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004ce00  call    cs:__imp_RpcAsyncInitializeHandle
0x18004ce06  test    eax, eax
0x18004ce08  jz      short loc_18004CE26
0x18004ce0a  jle     short loc_18004CE14
0x18004ce0c  movzx   eax, ax
0x18004ce0f  or      eax, 80070000h
0x18004ce14  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004ce1b  mov     r8d, 2F1h
0x18004ce21  jmp     loc_18004CFDC
0x18004ce26  mov     [rsp+118h+pAsync.UserInfo], 0
0x18004ce32  mov     [rsp+118h+pAsync.NotificationType], 1
0x18004ce3d  xor     r9d, r9d; lpName
0x18004ce40  xor     r8d, r8d; bInitialState
0x18004ce43  xor     edx, edx; bManualReset
0x18004ce45  xor     ecx, ecx; lpEventAttributes
0x18004ce47  call    cs:__imp_CreateEventW
0x18004ce4d  mov     qword ptr [rsp+118h+pAsync.u], rax
0x18004ce55  test    rax, rax
0x18004ce58  jnz     short loc_18004CE75
0x18004ce5a  call    cs:__imp_GetLastError
0x18004ce60  test    eax, eax
0x18004ce62  jle     short loc_18004CE6C
0x18004ce64  movzx   eax, ax
0x18004ce67  or      eax, 80070000h
0x18004ce6c  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004ce73  jmp     short loc_18004CE1B
0x18004ce75  mov     [rsp+118h+Handles], rax
0x18004ce7a  mov     rax, [rsp+118h+var_C0]
0x18004ce7f  mov     [rsp+118h+var_E0], rax
0x18004ce84  mov     [rsp+118h+var_E8], r13
0x18004ce89  mov     [rsp+118h+var_F0], r12
0x18004ce8e  mov     rax, [rsp+118h+var_C8]
0x18004ce93  mov     qword ptr [rsp+118h+bAlertable], rax
0x18004ce98  lea     r9, [rsp+118h+pAsync]
0x18004ce9d  xor     r8d, r8d; pReturnValue
0x18004cea0  lea     edx, [r8+14h]; nProcNum
0x18004cea4  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004ceab  call    cs:__imp_Ndr64AsyncClientCall
0x18004ceb1  mov     eax, [rsp+118h+Reply]
0x18004ceb5  jmp     short loc_18004CF06
0x18004ceb7  test    eax, eax
0x18004ceb9  jle     short loc_18004CEC3
0x18004cebb  movzx   eax, ax
0x18004cebe  or      eax, 80070000h
0x18004cec3  mov     [rsp+118h+Reply], eax
0x18004cec7  mov     [rsp+118h+bAlertable], eax
0x18004cecb  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004ced2  mov     r8d, 2F3h; unsigned int
0x18004ced8  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004cedf  mov     ecx, 2; unsigned __int8
0x18004cee4  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004cee9  mov     eax, [rsp+118h+Reply]
0x18004ceed  test    eax, eax
0x18004ceef  js      short loc_18004CEFA
0x18004cef1  mov     eax, 8000FFFFh
0x18004cef6  mov     [rsp+118h+Reply], eax
0x18004cefa  mov     esi, [rsp+118h+dwMilliseconds]
0x18004cefe  mov     r15b, [rsp+118h+var_D4]
0x18004cf03  mov     r14b, r15b
0x18004cf06  test    eax, eax
0x18004cf08  jns     short loc_18004CF1C
0x18004cf0a  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004cf11  mov     r8d, 2F3h
0x18004cf17  jmp     loc_18004CFE0
0x18004cf1c  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004cf24  mov     r9d, esi; dwMilliseconds
0x18004cf27  xor     r8d, r8d; bWaitAll
0x18004cf2a  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004cf2f  lea     ecx, [r8+1]; nCount
0x18004cf33  call    cs:__imp_WaitForMultipleObjectsEx
0x18004cf39  mov     esi, eax
0x18004cf3b  mov     r12d, 102h
0x18004cf41  test    r14b, r14b
0x18004cf44  jnz     short loc_18004CF92
0x18004cf46  cmp     esi, r12d
0x18004cf49  jz      short loc_18004CF50
0x18004cf4b  cmp     esi, 1
0x18004cf4e  jnz     short loc_18004CF92
0x18004cf50  mov     edx, 1; fAbort
0x18004cf55  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004cf5a  call    cs:__imp_RpcAsyncCancelCall
0x18004cf60  cmp     esi, r12d
0x18004cf63  jnz     short loc_18004CF6A
0x18004cf65  mov     r15b, 1
0x18004cf68  jmp     short loc_18004CF6D
0x18004cf6a  mov     r14b, 1
0x18004cf6d  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004cf75  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004cf79  xor     r8d, r8d; bWaitAll
0x18004cf7c  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004cf81  lea     ecx, [r8+1]; nCount
0x18004cf85  call    cs:__imp_WaitForMultipleObjectsEx
0x18004cf8b  mov     esi, eax
0x18004cf8d  test    r15b, r15b
0x18004cf90  jz      short loc_18004CF41
0x18004cf92  test    esi, esi
0x18004cf94  jz      short loc_18004CFB1
0x18004cf96  call    cs:__imp_GetLastError
0x18004cf9c  test    eax, eax
0x18004cf9e  jle     short loc_18004CFA8
0x18004cfa0  movzx   eax, ax
0x18004cfa3  or      eax, 80070000h
0x18004cfa8  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004cfaf  jmp     short loc_18004CFD6
0x18004cfb1  lea     rdx, [rsp+118h+Reply]; Reply
0x18004cfb6  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004cfbb  call    cs:__imp_RpcAsyncCompleteCall
0x18004cfc1  test    eax, eax
0x18004cfc3  jz      short loc_18004CFF5
0x18004cfc5  jle     short loc_18004CFCF
0x18004cfc7  movzx   eax, ax
0x18004cfca  or      eax, 80070000h
0x18004cfcf  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004cfd6  mov     r8d, 2F3h; unsigned int
0x18004cfdc  mov     [rsp+118h+Reply], eax
0x18004cfe0  mov     [rsp+118h+bAlertable], eax
0x18004cfe4  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004cfeb  mov     ecx, 2; unsigned __int8
0x18004cff0  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004cff5  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x18004cffd  test    rcx, rcx
0x18004d000  jz      short loc_18004D008
0x18004d002  call    cs:__imp_CloseHandle
0x18004d008  test    r15b, r15b
0x18004d00b  jz      short loc_18004D04C
0x18004d00d  mov     [rsp+118h+Reply], 800705B4h
0x18004d015  lea     rdx, [rsp+118h+var_CC]
0x18004d01a  lea     rcx, aWlidcgetuserex; "WLIDCGetUserExtendedProperty"
0x18004d021  call    ??$RPCCallTimedOut@AEAY0BN@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BN@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[29],ulong &>(char const (&)[29],ulong &)
0x18004d026  mov     eax, [rsp+118h+Reply]
0x18004d02a  mov     [rsp+118h+bAlertable], eax
0x18004d02e  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004d035  mov     r8d, 2F3h; unsigned int
0x18004d03b  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004d042  mov     ecx, 2; unsigned __int8
0x18004d047  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004d04c  test    r14b, r14b
0x18004d04f  jz      short loc_18004D07C
0x18004d051  mov     eax, 800704C7h
0x18004d056  mov     [rsp+118h+Reply], eax
0x18004d05a  mov     [rsp+118h+bAlertable], eax
0x18004d05e  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004d065  mov     r8d, 2F3h; unsigned int
0x18004d06b  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004d072  mov     ecx, 2; unsigned __int8
0x18004d077  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004d07c  cmp     [rsp+118h+Reply], 800706B5h
0x18004d084  jz      short loc_18004D090
0x18004d086  cmp     [rsp+118h+Reply], 800706BAh
0x18004d08e  jnz     short loc_18004D095
0x18004d090  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004d095  lea     rcx, [rsp+118h+var_C8]; this
0x18004d09a  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18004d09f  mov     eax, [rsp+118h+Reply]
0x18004d0a3  mov     rcx, [rsp+118h+var_38]
0x18004d0ab  xor     rcx, rsp; StackCookie
0x18004d0ae  call    __security_check_cookie
0x18004d0b3  add     rsp, 0F0h
0x18004d0ba  pop     r15
0x18004d0bc  pop     r14
0x18004d0be  pop     r13
0x18004d0c0  pop     r12
0x18004d0c2  pop     rsi
0x18004d0c3  retn
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
