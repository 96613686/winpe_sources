# WLIDCRegisterUserIdkey(ushort const *,ushort const *,ushort const *,int,unsigned __int64)

- ea: `0x180049a00`
- end: `0x180049d8d`
- name: `?WLIDCRegisterUserIdkey@@YAJPEBG00H_K@Z`
- size: `909`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800418b0`

## callees

- `0x18000a400`
- `0x18000f870`
- `0x180010c68`
- `0x180011588`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180041d98`
- `0x180043240`
- `0x180049a00`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180049af2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180049af2`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180049bf6`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180049c4b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180049bf6`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180049c4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049b05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049c5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049b05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049c5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049ccb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049ccb`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180049aab`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180049aab`
- `RPCRT4!RpcAsyncCancelCall` at `0x180049c20`
- `RPCRT4!RpcAsyncCancelCall` at `0x180049c20`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180049b6e`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180049b6e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180049c84`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180049c84`

## string_xrefs

- `0x180049b17`: `RPC failed to create new event, hr = %#x`
- `0x180049c98`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCRegisterUserIdkey(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned __int64 a5)
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
  int v20; // [rsp+5Ch] [rbp-DCh]
  DWORD v21; // [rsp+60h] [rbp-D8h] BYREF
  __int64 v22; // [rsp+68h] [rbp-D0h] BYREF
  const unsigned __int16 *v23; // [rsp+70h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+78h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+90h] [rbp-A8h] BYREF

  v20 = a4;
  v23 = a3;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  v22 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v22);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v8 = dwMilliseconds;
  v21 = dwMilliseconds;
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
    v13 = 1377;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x42u, 0, &pAsync, v22, a1, a2, v23, v20, a5);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v12 = L"RPC call failed, hr = %#x";
    v13 = 1386;
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
    v13 = 1386;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[23],unsigned long &>("WLIDCRegisterUserIdkey", &v21);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x56Au,
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
      0x56Au,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v22);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x180049a00  push    rsi
0x180049a02  push    r12
0x180049a04  push    r13
0x180049a06  push    r14
0x180049a08  push    r15
0x180049a0a  sub     rsp, 110h
0x180049a11  mov     rax, cs:__security_cookie
0x180049a18  xor     rax, rsp
0x180049a1b  mov     [rsp+138h+var_38], rax
0x180049a23  mov     [rsp+138h+var_DC], r9d
0x180049a28  mov     [rsp+138h+var_C8], r8
0x180049a2d  mov     r13, rdx
0x180049a30  mov     r12, rcx
0x180049a33  mov     [rsp+138h+dwMilliseconds], 0
0x180049a3b  lea     r8, [rsp+138h+dwMilliseconds]; unsigned int *
0x180049a40  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180049a45  mov     [rsp+138h+Reply], 0
0x180049a4d  mov     [rsp+138h+var_D0], 0
0x180049a56  lea     rcx, [rsp+138h+var_D0]; this
0x180049a5b  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x180049a60  mov     [rsp+138h+Reply], eax
0x180049a64  test    eax, eax
0x180049a66  js      loc_180049D6C
0x180049a6c  xor     edx, edx; Val
0x180049a6e  lea     r8d, [rdx+70h]; Size
0x180049a72  lea     rcx, [rsp+138h+pAsync]; void *
0x180049a7a  call    memset_0
0x180049a7f  mov     esi, [rsp+138h+dwMilliseconds]
0x180049a83  mov     [rsp+138h+dwMilliseconds], esi
0x180049a87  mov     [rsp+138h+var_D8], esi
0x180049a8b  xor     r15b, r15b
0x180049a8e  mov     [rsp+138h+var_E4], r15b
0x180049a93  xor     r14b, r14b
0x180049a96  xorps   xmm0, xmm0
0x180049a99  movups  xmmword ptr [rsp+138h+Handles], xmm0
0x180049a9e  mov     edx, 70h ; 'p'; Size
0x180049aa3  lea     rcx, [rsp+138h+pAsync]; pAsync
0x180049aab  call    cs:__imp_RpcAsyncInitializeHandle
0x180049ab1  test    eax, eax
0x180049ab3  jz      short loc_180049AD1
0x180049ab5  jle     short loc_180049ABF
0x180049ab7  movzx   eax, ax
0x180049aba  or      eax, 80070000h
0x180049abf  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180049ac6  mov     r8d, 561h
0x180049acc  jmp     loc_180049CA5
0x180049ad1  mov     [rsp+138h+pAsync.UserInfo], 0
0x180049add  mov     [rsp+138h+pAsync.NotificationType], 1
0x180049ae8  xor     r9d, r9d; lpName
0x180049aeb  xor     r8d, r8d; bInitialState
0x180049aee  xor     edx, edx; bManualReset
0x180049af0  xor     ecx, ecx; lpEventAttributes
0x180049af2  call    cs:__imp_CreateEventW
0x180049af8  mov     qword ptr [rsp+138h+pAsync.u], rax
0x180049b00  test    rax, rax
0x180049b03  jnz     short loc_180049B20
0x180049b05  call    cs:__imp_GetLastError
0x180049b0b  test    eax, eax
0x180049b0d  jle     short loc_180049B17
0x180049b0f  movzx   eax, ax
0x180049b12  or      eax, 80070000h
0x180049b17  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180049b1e  jmp     short loc_180049AC6
0x180049b20  mov     [rsp+138h+Handles], rax
0x180049b25  mov     rax, [rsp+138h+arg_20]
0x180049b2d  mov     [rsp+138h+var_F0], rax
0x180049b32  mov     eax, [rsp+138h+var_DC]
0x180049b36  mov     [rsp+138h+var_F8], eax
0x180049b3a  mov     rax, [rsp+138h+var_C8]
0x180049b3f  mov     [rsp+138h+var_100], rax
0x180049b44  mov     [rsp+138h+var_108], r13
0x180049b49  mov     [rsp+138h+var_110], r12
0x180049b4e  mov     rax, [rsp+138h+var_D0]
0x180049b53  mov     qword ptr [rsp+138h+bAlertable], rax
0x180049b58  lea     r9, [rsp+138h+pAsync]
0x180049b60  xor     r8d, r8d; pReturnValue
0x180049b63  lea     edx, [r8+42h]; nProcNum
0x180049b67  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180049b6e  call    cs:__imp_Ndr64AsyncClientCall
0x180049b74  mov     eax, [rsp+138h+Reply]
0x180049b78  jmp     short loc_180049BC9
0x180049b7a  test    eax, eax
0x180049b7c  jle     short loc_180049B86
0x180049b7e  movzx   eax, ax
0x180049b81  or      eax, 80070000h
0x180049b86  mov     [rsp+138h+Reply], eax
0x180049b8a  mov     [rsp+138h+bAlertable], eax
0x180049b8e  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180049b95  mov     r8d, 56Ah; unsigned int
0x180049b9b  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180049ba2  mov     ecx, 2; unsigned __int8
0x180049ba7  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180049bac  mov     eax, [rsp+138h+Reply]
0x180049bb0  test    eax, eax
0x180049bb2  js      short loc_180049BBD
0x180049bb4  mov     eax, 8000FFFFh
0x180049bb9  mov     [rsp+138h+Reply], eax
0x180049bbd  mov     esi, [rsp+138h+dwMilliseconds]
0x180049bc1  mov     r15b, [rsp+138h+var_E4]
0x180049bc6  mov     r14b, r15b
0x180049bc9  test    eax, eax
0x180049bcb  jns     short loc_180049BDF
0x180049bcd  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180049bd4  mov     r8d, 56Ah
0x180049bda  jmp     loc_180049CA9
0x180049bdf  mov     [rsp+138h+bAlertable], 0; bAlertable
0x180049be7  mov     r9d, esi; dwMilliseconds
0x180049bea  xor     r8d, r8d; bWaitAll
0x180049bed  lea     rdx, [rsp+138h+Handles]; lpHandles
0x180049bf2  lea     ecx, [r8+1]; nCount
0x180049bf6  call    cs:__imp_WaitForMultipleObjectsEx
0x180049bfc  mov     esi, eax
0x180049bfe  mov     r12d, 102h
0x180049c04  test    r14b, r14b
0x180049c07  jnz     short loc_180049C58
0x180049c09  cmp     esi, r12d
0x180049c0c  jz      short loc_180049C13
0x180049c0e  cmp     esi, 1
0x180049c11  jnz     short loc_180049C58
0x180049c13  mov     edx, 1; fAbort
0x180049c18  lea     rcx, [rsp+138h+pAsync]; pAsync
0x180049c20  call    cs:__imp_RpcAsyncCancelCall
0x180049c26  cmp     esi, r12d
0x180049c29  jnz     short loc_180049C30
0x180049c2b  mov     r15b, 1
0x180049c2e  jmp     short loc_180049C33
0x180049c30  mov     r14b, 1
0x180049c33  mov     [rsp+138h+bAlertable], 0; bAlertable
0x180049c3b  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180049c3f  xor     r8d, r8d; bWaitAll
0x180049c42  lea     rdx, [rsp+138h+Handles]; lpHandles
0x180049c47  lea     ecx, [r8+1]; nCount
0x180049c4b  call    cs:__imp_WaitForMultipleObjectsEx
0x180049c51  mov     esi, eax
0x180049c53  test    r15b, r15b
0x180049c56  jz      short loc_180049C04
0x180049c58  test    esi, esi
0x180049c5a  jz      short loc_180049C77
0x180049c5c  call    cs:__imp_GetLastError
0x180049c62  test    eax, eax
0x180049c64  jle     short loc_180049C6E
0x180049c66  movzx   eax, ax
0x180049c69  or      eax, 80070000h
0x180049c6e  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180049c75  jmp     short loc_180049C9F
0x180049c77  lea     rdx, [rsp+138h+Reply]; Reply
0x180049c7c  lea     rcx, [rsp+138h+pAsync]; pAsync
0x180049c84  call    cs:__imp_RpcAsyncCompleteCall
0x180049c8a  test    eax, eax
0x180049c8c  jz      short loc_180049CBE
0x180049c8e  jle     short loc_180049C98
0x180049c90  movzx   eax, ax
0x180049c93  or      eax, 80070000h
0x180049c98  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180049c9f  mov     r8d, 56Ah; unsigned int
0x180049ca5  mov     [rsp+138h+Reply], eax
0x180049ca9  mov     [rsp+138h+bAlertable], eax
0x180049cad  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180049cb4  mov     ecx, 2; unsigned __int8
0x180049cb9  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180049cbe  mov     rcx, qword ptr [rsp+138h+pAsync.u]; hObject
0x180049cc6  test    rcx, rcx
0x180049cc9  jz      short loc_180049CD1
0x180049ccb  call    cs:__imp_CloseHandle
0x180049cd1  test    r15b, r15b
0x180049cd4  jz      short loc_180049D15
0x180049cd6  mov     [rsp+138h+Reply], 800705B4h
0x180049cde  lea     rdx, [rsp+138h+var_D8]
0x180049ce3  lea     rcx, aWlidcregisteru; "WLIDCRegisterUserIdkey"
0x180049cea  call    ??$RPCCallTimedOut@AEAY0BH@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BH@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[23],ulong &>(char const (&)[23],ulong &)
0x180049cef  mov     eax, [rsp+138h+Reply]
0x180049cf3  mov     [rsp+138h+bAlertable], eax
0x180049cf7  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180049cfe  mov     r8d, 56Ah; unsigned int
0x180049d04  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180049d0b  mov     ecx, 2; unsigned __int8
0x180049d10  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180049d15  test    r14b, r14b
0x180049d18  jz      short loc_180049D45
0x180049d1a  mov     eax, 800704C7h
0x180049d1f  mov     [rsp+138h+Reply], eax
0x180049d23  mov     [rsp+138h+bAlertable], eax
0x180049d27  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180049d2e  mov     r8d, 56Ah; unsigned int
0x180049d34  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180049d3b  mov     ecx, 2; unsigned __int8
0x180049d40  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180049d45  cmp     [rsp+138h+Reply], 800706B5h
0x180049d4d  jz      short loc_180049D59
0x180049d4f  cmp     [rsp+138h+Reply], 800706BAh
0x180049d57  jnz     short loc_180049D5E
0x180049d59  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180049d5e  lea     rcx, [rsp+138h+var_D0]; this
0x180049d63  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x180049d68  mov     eax, [rsp+138h+Reply]
0x180049d6c  mov     rcx, [rsp+138h+var_38]
0x180049d74  xor     rcx, rsp; StackCookie
0x180049d77  call    __security_check_cookie
0x180049d7c  add     rsp, 110h
0x180049d83  pop     r15
0x180049d85  pop     r14
0x180049d87  pop     r13
0x180049d89  pop     r12
0x180049d8b  pop     rsi
0x180049d8c  retn
0x180057620  push    rbp
0x180057622  sub     rsp, 50h
0x180057626  mov     rbp, rdx
0x180057629  mov     rcx, [rcx]
0x18005762c  mov     ecx, [rcx]; unsigned int
0x18005762e  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x180057633  nop
0x180057634  add     rsp, 50h
0x180057638  pop     rbp
0x180057639  retn
```
