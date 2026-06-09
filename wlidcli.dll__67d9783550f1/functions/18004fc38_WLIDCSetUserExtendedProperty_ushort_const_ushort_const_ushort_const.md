# WLIDCSetUserExtendedProperty(ushort const *,ushort const *,ushort const *)

- ea: `0x18004fc38`
- end: `0x18004ff9c`
- name: `?WLIDCSetUserExtendedProperty@@YAJPEBG00@Z`
- size: `868`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180033910`
- `0x180034500`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180045394`
- `0x180046ce0`
- `0x18004cd04`
- `0x18004fc38`
- `0x180050c84`
- `0x180050e40`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004fe0b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004fe5d`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004fe0b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004fe5d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004fd1f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004fd1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fd32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fe6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fd32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fe6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004feda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004feda`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004fe32`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004fe32`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004fd83`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004fd83`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004fe93`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004fe93`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004fcd8`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004fcd8`

## string_xrefs

- `0x18004fd44`: `RPC failed to create new event, hr = %#x`
- `0x18004fea7`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCSetUserExtendedProperty(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
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
  const unsigned __int16 *v20; // [rsp+58h] [rbp-C0h]
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
    v11 = 764;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x15u, 0, &pAsync, v19, a1, a2, v20);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v10 = L"RPC call failed, hr = %#x";
    v11 = 766;
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
    v11 = 766;
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
      (__int64)"WLIDCSetUserExtendedProperty",
      (int *)&v18);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x2FEu,
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
      0x2FEu,
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
0x18004fc38  push    rsi
0x18004fc3a  push    r12
0x18004fc3c  push    r13
0x18004fc3e  push    r14
0x18004fc40  push    r15
0x18004fc42  sub     rsp, 0F0h
0x18004fc49  mov     rax, cs:__security_cookie
0x18004fc50  xor     rax, rsp
0x18004fc53  mov     [rsp+118h+var_38], rax
0x18004fc5b  mov     [rsp+118h+var_C0], r8
0x18004fc60  mov     r13, rdx
0x18004fc63  mov     r12, rcx
0x18004fc66  mov     [rsp+118h+dwMilliseconds], 0
0x18004fc6e  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x18004fc73  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004fc78  mov     [rsp+118h+Reply], 0
0x18004fc80  mov     [rsp+118h+var_C8], 0
0x18004fc89  lea     rcx, [rsp+118h+var_C8]; this
0x18004fc8e  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18004fc93  mov     [rsp+118h+Reply], eax
0x18004fc97  test    eax, eax
0x18004fc99  js      loc_18004FF7B
0x18004fc9f  xor     edx, edx; Val
0x18004fca1  lea     r8d, [rdx+70h]; Size
0x18004fca5  lea     rcx, [rsp+118h+pAsync]; void *
0x18004fcaa  call    memset_0
0x18004fcaf  mov     esi, [rsp+118h+dwMilliseconds]
0x18004fcb3  mov     [rsp+118h+dwMilliseconds], esi
0x18004fcb7  mov     [rsp+118h+var_CC], esi
0x18004fcbb  xor     r15b, r15b
0x18004fcbe  mov     [rsp+118h+var_D4], r15b
0x18004fcc3  xor     r14b, r14b
0x18004fcc6  xorps   xmm0, xmm0
0x18004fcc9  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x18004fcce  mov     edx, 70h ; 'p'; Size
0x18004fcd3  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004fcd8  call    cs:__imp_RpcAsyncInitializeHandle
0x18004fcde  test    eax, eax
0x18004fce0  jz      short loc_18004FCFE
0x18004fce2  jle     short loc_18004FCEC
0x18004fce4  movzx   eax, ax
0x18004fce7  or      eax, 80070000h
0x18004fcec  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004fcf3  mov     r8d, 2FCh
0x18004fcf9  jmp     loc_18004FEB4
0x18004fcfe  mov     [rsp+118h+pAsync.UserInfo], 0
0x18004fd0a  mov     [rsp+118h+pAsync.NotificationType], 1
0x18004fd15  xor     r9d, r9d; lpName
0x18004fd18  xor     r8d, r8d; bInitialState
0x18004fd1b  xor     edx, edx; bManualReset
0x18004fd1d  xor     ecx, ecx; lpEventAttributes
0x18004fd1f  call    cs:__imp_CreateEventW
0x18004fd25  mov     qword ptr [rsp+118h+pAsync.u], rax
0x18004fd2d  test    rax, rax
0x18004fd30  jnz     short loc_18004FD4D
0x18004fd32  call    cs:__imp_GetLastError
0x18004fd38  test    eax, eax
0x18004fd3a  jle     short loc_18004FD44
0x18004fd3c  movzx   eax, ax
0x18004fd3f  or      eax, 80070000h
0x18004fd44  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004fd4b  jmp     short loc_18004FCF3
0x18004fd4d  mov     [rsp+118h+Handles], rax
0x18004fd52  mov     rax, [rsp+118h+var_C0]
0x18004fd57  mov     [rsp+118h+var_E0], rax
0x18004fd5c  mov     [rsp+118h+var_E8], r13
0x18004fd61  mov     [rsp+118h+var_F0], r12
0x18004fd66  mov     rax, [rsp+118h+var_C8]
0x18004fd6b  mov     qword ptr [rsp+118h+bAlertable], rax
0x18004fd70  lea     r9, [rsp+118h+pAsync]
0x18004fd75  xor     r8d, r8d; pReturnValue
0x18004fd78  lea     edx, [r8+15h]; nProcNum
0x18004fd7c  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004fd83  call    cs:__imp_Ndr64AsyncClientCall
0x18004fd89  mov     eax, [rsp+118h+Reply]
0x18004fd8d  jmp     short loc_18004FDDE
0x18004fd8f  test    eax, eax
0x18004fd91  jle     short loc_18004FD9B
0x18004fd93  movzx   eax, ax
0x18004fd96  or      eax, 80070000h
0x18004fd9b  mov     [rsp+118h+Reply], eax
0x18004fd9f  mov     [rsp+118h+bAlertable], eax
0x18004fda3  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004fdaa  mov     r8d, 2FEh; unsigned int
0x18004fdb0  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004fdb7  mov     ecx, 2; unsigned __int8
0x18004fdbc  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004fdc1  mov     eax, [rsp+118h+Reply]
0x18004fdc5  test    eax, eax
0x18004fdc7  js      short loc_18004FDD2
0x18004fdc9  mov     eax, 8000FFFFh
0x18004fdce  mov     [rsp+118h+Reply], eax
0x18004fdd2  mov     esi, [rsp+118h+dwMilliseconds]
0x18004fdd6  mov     r15b, [rsp+118h+var_D4]
0x18004fddb  mov     r14b, r15b
0x18004fdde  test    eax, eax
0x18004fde0  jns     short loc_18004FDF4
0x18004fde2  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004fde9  mov     r8d, 2FEh
0x18004fdef  jmp     loc_18004FEB8
0x18004fdf4  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004fdfc  mov     r9d, esi; dwMilliseconds
0x18004fdff  xor     r8d, r8d; bWaitAll
0x18004fe02  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004fe07  lea     ecx, [r8+1]; nCount
0x18004fe0b  call    cs:__imp_WaitForMultipleObjectsEx
0x18004fe11  mov     esi, eax
0x18004fe13  mov     r12d, 102h
0x18004fe19  test    r14b, r14b
0x18004fe1c  jnz     short loc_18004FE6A
0x18004fe1e  cmp     esi, r12d
0x18004fe21  jz      short loc_18004FE28
0x18004fe23  cmp     esi, 1
0x18004fe26  jnz     short loc_18004FE6A
0x18004fe28  mov     edx, 1; fAbort
0x18004fe2d  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004fe32  call    cs:__imp_RpcAsyncCancelCall
0x18004fe38  cmp     esi, r12d
0x18004fe3b  jnz     short loc_18004FE42
0x18004fe3d  mov     r15b, 1
0x18004fe40  jmp     short loc_18004FE45
0x18004fe42  mov     r14b, 1
0x18004fe45  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004fe4d  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004fe51  xor     r8d, r8d; bWaitAll
0x18004fe54  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004fe59  lea     ecx, [r8+1]; nCount
0x18004fe5d  call    cs:__imp_WaitForMultipleObjectsEx
0x18004fe63  mov     esi, eax
0x18004fe65  test    r15b, r15b
0x18004fe68  jz      short loc_18004FE19
0x18004fe6a  test    esi, esi
0x18004fe6c  jz      short loc_18004FE89
0x18004fe6e  call    cs:__imp_GetLastError
0x18004fe74  test    eax, eax
0x18004fe76  jle     short loc_18004FE80
0x18004fe78  movzx   eax, ax
0x18004fe7b  or      eax, 80070000h
0x18004fe80  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004fe87  jmp     short loc_18004FEAE
0x18004fe89  lea     rdx, [rsp+118h+Reply]; Reply
0x18004fe8e  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004fe93  call    cs:__imp_RpcAsyncCompleteCall
0x18004fe99  test    eax, eax
0x18004fe9b  jz      short loc_18004FECD
0x18004fe9d  jle     short loc_18004FEA7
0x18004fe9f  movzx   eax, ax
0x18004fea2  or      eax, 80070000h
0x18004fea7  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004feae  mov     r8d, 2FEh; unsigned int
0x18004feb4  mov     [rsp+118h+Reply], eax
0x18004feb8  mov     [rsp+118h+bAlertable], eax
0x18004febc  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004fec3  mov     ecx, 2; unsigned __int8
0x18004fec8  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004fecd  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x18004fed5  test    rcx, rcx
0x18004fed8  jz      short loc_18004FEE0
0x18004feda  call    cs:__imp_CloseHandle
0x18004fee0  test    r15b, r15b
0x18004fee3  jz      short loc_18004FF24
0x18004fee5  mov     [rsp+118h+Reply], 800705B4h
0x18004feed  lea     rdx, [rsp+118h+var_CC]
0x18004fef2  lea     rcx, aWlidcsetuserex; "WLIDCSetUserExtendedProperty"
0x18004fef9  call    ??$RPCCallTimedOut@AEAY0BN@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BN@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[29],ulong &>(char const (&)[29],ulong &)
0x18004fefe  mov     eax, [rsp+118h+Reply]
0x18004ff02  mov     [rsp+118h+bAlertable], eax
0x18004ff06  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004ff0d  mov     r8d, 2FEh; unsigned int
0x18004ff13  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004ff1a  mov     ecx, 2; unsigned __int8
0x18004ff1f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004ff24  test    r14b, r14b
0x18004ff27  jz      short loc_18004FF54
0x18004ff29  mov     eax, 800704C7h
0x18004ff2e  mov     [rsp+118h+Reply], eax
0x18004ff32  mov     [rsp+118h+bAlertable], eax
0x18004ff36  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004ff3d  mov     r8d, 2FEh; unsigned int
0x18004ff43  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004ff4a  mov     ecx, 2; unsigned __int8
0x18004ff4f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004ff54  cmp     [rsp+118h+Reply], 800706B5h
0x18004ff5c  jz      short loc_18004FF68
0x18004ff5e  cmp     [rsp+118h+Reply], 800706BAh
0x18004ff66  jnz     short loc_18004FF6D
0x18004ff68  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004ff6d  lea     rcx, [rsp+118h+var_C8]; this
0x18004ff72  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18004ff77  mov     eax, [rsp+118h+Reply]
0x18004ff7b  mov     rcx, [rsp+118h+var_38]
0x18004ff83  xor     rcx, rsp; StackCookie
0x18004ff86  call    __security_check_cookie
0x18004ff8b  add     rsp, 0F0h
0x18004ff92  pop     r15
0x18004ff94  pop     r14
0x18004ff96  pop     r13
0x18004ff98  pop     r12
0x18004ff9a  pop     rsi
0x18004ff9b  retn
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
