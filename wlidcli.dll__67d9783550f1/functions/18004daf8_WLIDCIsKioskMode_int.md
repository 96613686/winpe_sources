# WLIDCIsKioskMode(int *)

- ea: `0x18004daf8`
- end: `0x18004de3e`
- name: `?WLIDCIsKioskMode@@YAJPEAH@Z`
- size: `838`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002706c`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180044d94`
- `0x180046ce0`
- `0x18004cd04`
- `0x18004daf8`
- `0x180050c84`
- `0x180050e40`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004dcaf`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004dd01`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004dcaf`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004dd01`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004dbd2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004dbd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dbe5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dd12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dbe5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dd12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004dd7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004dd7e`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004dcd6`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004dcd6`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004dc27`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004dc27`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004dd37`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004dd37`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004db8e`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004db8e`

## string_xrefs

- `0x18004dbf7`: `RPC failed to create new event, hr = %#x`
- `0x18004dd4b`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCIsKioskMode(int *a1, unsigned int a2)
{
  __int64 result; // rax
  DWORD v4; // esi
  char v5; // r15
  char v6; // r14
  int LastError; // eax
  const unsigned __int16 *v8; // r9
  unsigned int v9; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v11; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-E8h]
  int Reply; // [rsp+30h] [rbp-D8h] BYREF
  char v14; // [rsp+34h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+38h] [rbp-D0h] BYREF
  DWORD v16; // [rsp+3Ch] [rbp-CCh] BYREF
  __int64 v17; // [rsp+40h] [rbp-C8h] BYREF
  HANDLE Handles[3]; // [rsp+48h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+60h] [rbp-A8h] BYREF

  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  v17 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v17);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v4 = dwMilliseconds;
  v16 = dwMilliseconds;
  v5 = 0;
  v14 = 0;
  v6 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v9 = 1080;
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
    v8 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x32u, 0, &pAsync, v17, a1);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v8 = L"RPC call failed, hr = %#x";
    v9 = 1082;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v9,
      v8,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
  v11 = WaitForMultipleObjectsEx(1u, Handles, 0, v4, 0);
  do
  {
    if ( v6 || v11 != 258 && v11 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v11 == 258 )
      v5 = 1;
    else
      v6 = 1;
    v11 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v5 );
  if ( v11 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = L"Encountered error while waiting on RPC call, hr = %#x";
LABEL_29:
    v9 = 1082;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v5 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[17],unsigned long &>(
      (__int64)"WLIDCIsKioskMode",
      (int *)&v16);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x43Au,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v6 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x43Au,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v17);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x18004daf8  push    rsi
0x18004dafa  push    r12
0x18004dafc  push    r14
0x18004dafe  push    r15
0x18004db00  sub     rsp, 0E8h
0x18004db07  mov     rax, cs:__security_cookie
0x18004db0e  xor     rax, rsp
0x18004db11  mov     [rsp+108h+var_38], rax
0x18004db19  mov     r12, rcx
0x18004db1c  mov     [rsp+108h+dwMilliseconds], 0
0x18004db24  lea     r8, [rsp+108h+dwMilliseconds]; unsigned int *
0x18004db29  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004db2e  mov     [rsp+108h+Reply], 0
0x18004db36  mov     [rsp+108h+var_C8], 0
0x18004db3f  lea     rcx, [rsp+108h+var_C8]; this
0x18004db44  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18004db49  mov     [rsp+108h+Reply], eax
0x18004db4d  test    eax, eax
0x18004db4f  js      loc_18004DE1F
0x18004db55  xor     edx, edx; Val
0x18004db57  lea     r8d, [rdx+70h]; Size
0x18004db5b  lea     rcx, [rsp+108h+pAsync]; void *
0x18004db60  call    memset_0
0x18004db65  mov     esi, [rsp+108h+dwMilliseconds]
0x18004db69  mov     [rsp+108h+dwMilliseconds], esi
0x18004db6d  mov     [rsp+108h+var_CC], esi
0x18004db71  xor     r15b, r15b
0x18004db74  mov     [rsp+108h+var_D4], r15b
0x18004db79  xor     r14b, r14b
0x18004db7c  xorps   xmm0, xmm0
0x18004db7f  movups  xmmword ptr [rsp+108h+Handles], xmm0
0x18004db84  mov     edx, 70h ; 'p'; Size
0x18004db89  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004db8e  call    cs:__imp_RpcAsyncInitializeHandle
0x18004db94  test    eax, eax
0x18004db96  jz      short loc_18004DBB4
0x18004db98  jle     short loc_18004DBA2
0x18004db9a  movzx   eax, ax
0x18004db9d  or      eax, 80070000h
0x18004dba2  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004dba9  mov     r8d, 438h
0x18004dbaf  jmp     loc_18004DD58
0x18004dbb4  mov     [rsp+108h+pAsync.UserInfo], 0
0x18004dbbd  mov     [rsp+108h+pAsync.NotificationType], 1
0x18004dbc8  xor     r9d, r9d; lpName
0x18004dbcb  xor     r8d, r8d; bInitialState
0x18004dbce  xor     edx, edx; bManualReset
0x18004dbd0  xor     ecx, ecx; lpEventAttributes
0x18004dbd2  call    cs:__imp_CreateEventW
0x18004dbd8  mov     qword ptr [rsp+108h+pAsync.u], rax
0x18004dbe0  test    rax, rax
0x18004dbe3  jnz     short loc_18004DC00
0x18004dbe5  call    cs:__imp_GetLastError
0x18004dbeb  test    eax, eax
0x18004dbed  jle     short loc_18004DBF7
0x18004dbef  movzx   eax, ax
0x18004dbf2  or      eax, 80070000h
0x18004dbf7  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004dbfe  jmp     short loc_18004DBA9
0x18004dc00  mov     [rsp+108h+Handles], rax
0x18004dc05  mov     [rsp+108h+var_E0], r12
0x18004dc0a  mov     rax, [rsp+108h+var_C8]
0x18004dc0f  mov     qword ptr [rsp+108h+bAlertable], rax
0x18004dc14  lea     r9, [rsp+108h+pAsync]
0x18004dc19  xor     r8d, r8d; pReturnValue
0x18004dc1c  lea     edx, [r8+32h]; nProcNum
0x18004dc20  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004dc27  call    cs:__imp_Ndr64AsyncClientCall
0x18004dc2d  mov     eax, [rsp+108h+Reply]
0x18004dc31  jmp     short loc_18004DC82
0x18004dc33  test    eax, eax
0x18004dc35  jle     short loc_18004DC3F
0x18004dc37  movzx   eax, ax
0x18004dc3a  or      eax, 80070000h
0x18004dc3f  mov     [rsp+108h+Reply], eax
0x18004dc43  mov     [rsp+108h+bAlertable], eax
0x18004dc47  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004dc4e  mov     r8d, 43Ah; unsigned int
0x18004dc54  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004dc5b  mov     ecx, 2; unsigned __int8
0x18004dc60  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004dc65  mov     eax, [rsp+108h+Reply]
0x18004dc69  test    eax, eax
0x18004dc6b  js      short loc_18004DC76
0x18004dc6d  mov     eax, 8000FFFFh
0x18004dc72  mov     [rsp+108h+Reply], eax
0x18004dc76  mov     esi, [rsp+108h+dwMilliseconds]
0x18004dc7a  mov     r15b, [rsp+108h+var_D4]
0x18004dc7f  mov     r14b, r15b
0x18004dc82  test    eax, eax
0x18004dc84  jns     short loc_18004DC98
0x18004dc86  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004dc8d  mov     r8d, 43Ah
0x18004dc93  jmp     loc_18004DD5C
0x18004dc98  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18004dca0  mov     r9d, esi; dwMilliseconds
0x18004dca3  xor     r8d, r8d; bWaitAll
0x18004dca6  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18004dcab  lea     ecx, [r8+1]; nCount
0x18004dcaf  call    cs:__imp_WaitForMultipleObjectsEx
0x18004dcb5  mov     esi, eax
0x18004dcb7  mov     r12d, 102h
0x18004dcbd  test    r14b, r14b
0x18004dcc0  jnz     short loc_18004DD0E
0x18004dcc2  cmp     esi, r12d
0x18004dcc5  jz      short loc_18004DCCC
0x18004dcc7  cmp     esi, 1
0x18004dcca  jnz     short loc_18004DD0E
0x18004dccc  mov     edx, 1; fAbort
0x18004dcd1  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004dcd6  call    cs:__imp_RpcAsyncCancelCall
0x18004dcdc  cmp     esi, r12d
0x18004dcdf  jnz     short loc_18004DCE6
0x18004dce1  mov     r15b, 1
0x18004dce4  jmp     short loc_18004DCE9
0x18004dce6  mov     r14b, 1
0x18004dce9  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18004dcf1  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004dcf5  xor     r8d, r8d; bWaitAll
0x18004dcf8  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18004dcfd  lea     ecx, [r8+1]; nCount
0x18004dd01  call    cs:__imp_WaitForMultipleObjectsEx
0x18004dd07  mov     esi, eax
0x18004dd09  test    r15b, r15b
0x18004dd0c  jz      short loc_18004DCBD
0x18004dd0e  test    esi, esi
0x18004dd10  jz      short loc_18004DD2D
0x18004dd12  call    cs:__imp_GetLastError
0x18004dd18  test    eax, eax
0x18004dd1a  jle     short loc_18004DD24
0x18004dd1c  movzx   eax, ax
0x18004dd1f  or      eax, 80070000h
0x18004dd24  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004dd2b  jmp     short loc_18004DD52
0x18004dd2d  lea     rdx, [rsp+108h+Reply]; Reply
0x18004dd32  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004dd37  call    cs:__imp_RpcAsyncCompleteCall
0x18004dd3d  test    eax, eax
0x18004dd3f  jz      short loc_18004DD71
0x18004dd41  jle     short loc_18004DD4B
0x18004dd43  movzx   eax, ax
0x18004dd46  or      eax, 80070000h
0x18004dd4b  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004dd52  mov     r8d, 43Ah; unsigned int
0x18004dd58  mov     [rsp+108h+Reply], eax
0x18004dd5c  mov     [rsp+108h+bAlertable], eax
0x18004dd60  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004dd67  mov     ecx, 2; unsigned __int8
0x18004dd6c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004dd71  mov     rcx, qword ptr [rsp+108h+pAsync.u]; hObject
0x18004dd79  test    rcx, rcx
0x18004dd7c  jz      short loc_18004DD84
0x18004dd7e  call    cs:__imp_CloseHandle
0x18004dd84  test    r15b, r15b
0x18004dd87  jz      short loc_18004DDC8
0x18004dd89  mov     [rsp+108h+Reply], 800705B4h
0x18004dd91  lea     rdx, [rsp+108h+var_CC]
0x18004dd96  lea     rcx, aWlidciskioskmo; "WLIDCIsKioskMode"
0x18004dd9d  call    ??$RPCCallTimedOut@AEAY0BB@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BB@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[17],ulong &>(char const (&)[17],ulong &)
0x18004dda2  mov     eax, [rsp+108h+Reply]
0x18004dda6  mov     [rsp+108h+bAlertable], eax
0x18004ddaa  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004ddb1  mov     r8d, 43Ah; unsigned int
0x18004ddb7  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004ddbe  mov     ecx, 2; unsigned __int8
0x18004ddc3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004ddc8  test    r14b, r14b
0x18004ddcb  jz      short loc_18004DDF8
0x18004ddcd  mov     eax, 800704C7h
0x18004ddd2  mov     [rsp+108h+Reply], eax
0x18004ddd6  mov     [rsp+108h+bAlertable], eax
0x18004ddda  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004dde1  mov     r8d, 43Ah; unsigned int
0x18004dde7  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004ddee  mov     ecx, 2; unsigned __int8
0x18004ddf3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004ddf8  cmp     [rsp+108h+Reply], 800706B5h
0x18004de00  jz      short loc_18004DE0C
0x18004de02  cmp     [rsp+108h+Reply], 800706BAh
0x18004de0a  jnz     short loc_18004DE11
0x18004de0c  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004de11  lea     rcx, [rsp+108h+var_C8]; this
0x18004de16  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18004de1b  mov     eax, [rsp+108h+Reply]
0x18004de1f  mov     rcx, [rsp+108h+var_38]
0x18004de27  xor     rcx, rsp; StackCookie
0x18004de2a  call    __security_check_cookie
0x18004de2f  add     rsp, 0E8h
0x18004de36  pop     r15
0x18004de38  pop     r14
0x18004de3a  pop     r12
0x18004de3c  pop     rsi
0x18004de3d  retn
0x1800619f5  push    rbp
0x1800619f7  sub     rsp, 30h
0x1800619fb  mov     rbp, rdx
0x1800619fe  mov     rcx, [rcx]
0x180061a01  mov     ecx, [rcx]; unsigned int
0x180061a03  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x180061a08  nop
0x180061a09  add     rsp, 30h
0x180061a0d  pop     rbp
0x180061a0e  retn
```
