# WLIDCGetConfigString(ushort const *,ushort * *)

- ea: `0x180049fd8`
- end: `0x18004a33c`
- name: `?WLIDCGetConfigString@@YAJPEBGPEAPEAG@Z`
- size: `868`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002adb0`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180044fc4`
- `0x180046ce0`
- `0x180049fd8`
- `0x18004cd04`
- `0x180050c84`
- `0x180050e40`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004a1a2`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004a1f4`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004a1a2`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004a1f4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004a0c0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004a0c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a0d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a205`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a0d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a205`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a271`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a271`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004a1c9`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004a1c9`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004a11a`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004a11a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004a22a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004a22a`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004a079`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004a079`

## string_xrefs

- `0x18004a0e5`: `RPC failed to create new event, hr = %#x`
- `0x18004a23e`: `RPC Async complete call failed, hr = %#x`
- `0x18004a289`: `WLIDCGetConfigString`

## pseudocode

```c
__int64 __fastcall WLIDCGetConfigString(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  __int64 result; // rax
  DWORD v5; // esi
  char v6; // r15
  char v7; // r14
  int LastError; // eax
  const unsigned __int16 *v9; // r9
  unsigned int v10; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v12; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-E8h]
  int Reply; // [rsp+40h] [rbp-C8h] BYREF
  char v15; // [rsp+44h] [rbp-C4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-C0h] BYREF
  DWORD v17; // [rsp+4Ch] [rbp-BCh] BYREF
  __int64 v18; // [rsp+50h] [rbp-B8h] BYREF
  HANDLE Handles[3]; // [rsp+58h] [rbp-B0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-98h] BYREF

  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  v18 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v18);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v5 = dwMilliseconds;
  v17 = dwMilliseconds;
  v6 = 0;
  v15 = 0;
  v7 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v10 = 1226;
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
    v9 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x33u, 0, &pAsync, v18, a1, a2);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v9 = L"RPC call failed, hr = %#x";
    v10 = 1228;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v10,
      v9,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
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
LABEL_29:
    v10 = 1228;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v6 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],unsigned long &>(
      (__int64)"WLIDCGetConfigString",
      (int *)&v17);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x4CCu,
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
      0x4CCu,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v18);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x180049fd8  mov     [rsp+arg_10], rsi
0x180049fdd  mov     [rsp+arg_18], r12
0x180049fe2  push    r13
0x180049fe4  push    r14
0x180049fe6  push    r15
0x180049fe8  sub     rsp, 0F0h
0x180049fef  mov     rax, cs:__security_cookie
0x180049ff6  xor     rax, rsp
0x180049ff9  mov     [rsp+108h+var_28], rax
0x18004a001  mov     r13, rdx
0x18004a004  mov     r12, rcx
0x18004a007  mov     [rsp+108h+dwMilliseconds], 0
0x18004a00f  lea     r8, [rsp+108h+dwMilliseconds]; unsigned int *
0x18004a014  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004a019  mov     [rsp+108h+Reply], 0
0x18004a021  mov     [rsp+108h+var_B8], 0
0x18004a02a  lea     rcx, [rsp+108h+var_B8]; this
0x18004a02f  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18004a034  mov     [rsp+108h+Reply], eax
0x18004a038  test    eax, eax
0x18004a03a  js      loc_18004A312
0x18004a040  xor     edx, edx; Val
0x18004a042  lea     r8d, [rdx+70h]; Size
0x18004a046  lea     rcx, [rsp+108h+pAsync]; void *
0x18004a04b  call    memset_0
0x18004a050  mov     esi, [rsp+108h+dwMilliseconds]
0x18004a054  mov     [rsp+108h+dwMilliseconds], esi
0x18004a058  mov     [rsp+108h+var_BC], esi
0x18004a05c  xor     r15b, r15b
0x18004a05f  mov     [rsp+108h+var_C4], r15b
0x18004a064  xor     r14b, r14b
0x18004a067  xorps   xmm0, xmm0
0x18004a06a  movups  xmmword ptr [rsp+108h+Handles], xmm0
0x18004a06f  mov     edx, 70h ; 'p'; Size
0x18004a074  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004a079  call    cs:__imp_RpcAsyncInitializeHandle
0x18004a07f  test    eax, eax
0x18004a081  jz      short loc_18004A09F
0x18004a083  jle     short loc_18004A08D
0x18004a085  movzx   eax, ax
0x18004a088  or      eax, 80070000h
0x18004a08d  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004a094  mov     r8d, 4CAh
0x18004a09a  jmp     loc_18004A24B
0x18004a09f  mov     [rsp+108h+pAsync.UserInfo], 0
0x18004a0ab  mov     [rsp+108h+pAsync.NotificationType], 1
0x18004a0b6  xor     r9d, r9d; lpName
0x18004a0b9  xor     r8d, r8d; bInitialState
0x18004a0bc  xor     edx, edx; bManualReset
0x18004a0be  xor     ecx, ecx; lpEventAttributes
0x18004a0c0  call    cs:__imp_CreateEventW
0x18004a0c6  mov     qword ptr [rsp+108h+pAsync.u], rax
0x18004a0ce  test    rax, rax
0x18004a0d1  jnz     short loc_18004A0EE
0x18004a0d3  call    cs:__imp_GetLastError
0x18004a0d9  test    eax, eax
0x18004a0db  jle     short loc_18004A0E5
0x18004a0dd  movzx   eax, ax
0x18004a0e0  or      eax, 80070000h
0x18004a0e5  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004a0ec  jmp     short loc_18004A094
0x18004a0ee  mov     [rsp+108h+Handles], rax
0x18004a0f3  mov     [rsp+108h+var_D8], r13
0x18004a0f8  mov     [rsp+108h+var_E0], r12
0x18004a0fd  mov     rax, [rsp+108h+var_B8]
0x18004a102  mov     qword ptr [rsp+108h+bAlertable], rax
0x18004a107  lea     r9, [rsp+108h+pAsync]
0x18004a10c  xor     r8d, r8d; pReturnValue
0x18004a10f  lea     edx, [r8+33h]; nProcNum
0x18004a113  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004a11a  call    cs:__imp_Ndr64AsyncClientCall
0x18004a120  mov     eax, [rsp+108h+Reply]
0x18004a124  jmp     short loc_18004A175
0x18004a126  test    eax, eax
0x18004a128  jle     short loc_18004A132
0x18004a12a  movzx   eax, ax
0x18004a12d  or      eax, 80070000h
0x18004a132  mov     [rsp+108h+Reply], eax
0x18004a136  mov     [rsp+108h+bAlertable], eax
0x18004a13a  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004a141  mov     r8d, 4CCh; unsigned int
0x18004a147  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004a14e  mov     ecx, 2; unsigned __int8
0x18004a153  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004a158  mov     eax, [rsp+108h+Reply]
0x18004a15c  test    eax, eax
0x18004a15e  js      short loc_18004A169
0x18004a160  mov     eax, 8000FFFFh
0x18004a165  mov     [rsp+108h+Reply], eax
0x18004a169  mov     esi, [rsp+108h+dwMilliseconds]
0x18004a16d  mov     r15b, [rsp+108h+var_C4]
0x18004a172  mov     r14b, r15b
0x18004a175  test    eax, eax
0x18004a177  jns     short loc_18004A18B
0x18004a179  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004a180  mov     r8d, 4CCh
0x18004a186  jmp     loc_18004A24F
0x18004a18b  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18004a193  mov     r9d, esi; dwMilliseconds
0x18004a196  xor     r8d, r8d; bWaitAll
0x18004a199  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18004a19e  lea     ecx, [r8+1]; nCount
0x18004a1a2  call    cs:__imp_WaitForMultipleObjectsEx
0x18004a1a8  mov     esi, eax
0x18004a1aa  mov     r12d, 102h
0x18004a1b0  test    r14b, r14b
0x18004a1b3  jnz     short loc_18004A201
0x18004a1b5  cmp     esi, r12d
0x18004a1b8  jz      short loc_18004A1BF
0x18004a1ba  cmp     esi, 1
0x18004a1bd  jnz     short loc_18004A201
0x18004a1bf  mov     edx, 1; fAbort
0x18004a1c4  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004a1c9  call    cs:__imp_RpcAsyncCancelCall
0x18004a1cf  cmp     esi, r12d
0x18004a1d2  jnz     short loc_18004A1D9
0x18004a1d4  mov     r15b, 1
0x18004a1d7  jmp     short loc_18004A1DC
0x18004a1d9  mov     r14b, 1
0x18004a1dc  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18004a1e4  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004a1e8  xor     r8d, r8d; bWaitAll
0x18004a1eb  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18004a1f0  lea     ecx, [r8+1]; nCount
0x18004a1f4  call    cs:__imp_WaitForMultipleObjectsEx
0x18004a1fa  mov     esi, eax
0x18004a1fc  test    r15b, r15b
0x18004a1ff  jz      short loc_18004A1B0
0x18004a201  test    esi, esi
0x18004a203  jz      short loc_18004A220
0x18004a205  call    cs:__imp_GetLastError
0x18004a20b  test    eax, eax
0x18004a20d  jle     short loc_18004A217
0x18004a20f  movzx   eax, ax
0x18004a212  or      eax, 80070000h
0x18004a217  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004a21e  jmp     short loc_18004A245
0x18004a220  lea     rdx, [rsp+108h+Reply]; Reply
0x18004a225  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004a22a  call    cs:__imp_RpcAsyncCompleteCall
0x18004a230  test    eax, eax
0x18004a232  jz      short loc_18004A264
0x18004a234  jle     short loc_18004A23E
0x18004a236  movzx   eax, ax
0x18004a239  or      eax, 80070000h
0x18004a23e  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004a245  mov     r8d, 4CCh; unsigned int
0x18004a24b  mov     [rsp+108h+Reply], eax
0x18004a24f  mov     [rsp+108h+bAlertable], eax
0x18004a253  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004a25a  mov     ecx, 2; unsigned __int8
0x18004a25f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004a264  mov     rcx, qword ptr [rsp+108h+pAsync.u]; hObject
0x18004a26c  test    rcx, rcx
0x18004a26f  jz      short loc_18004A277
0x18004a271  call    cs:__imp_CloseHandle
0x18004a277  test    r15b, r15b
0x18004a27a  jz      short loc_18004A2BB
0x18004a27c  mov     [rsp+108h+Reply], 800705B4h
0x18004a284  lea     rdx, [rsp+108h+var_BC]
0x18004a289  lea     rcx, aWlidcgetconfig; "WLIDCGetConfigString"
0x18004a290  call    ??$RPCCallTimedOut@AEAY0BF@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BF@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],ulong &>(char const (&)[21],ulong &)
0x18004a295  mov     eax, [rsp+108h+Reply]
0x18004a299  mov     [rsp+108h+bAlertable], eax
0x18004a29d  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004a2a4  mov     r8d, 4CCh; unsigned int
0x18004a2aa  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004a2b1  mov     ecx, 2; unsigned __int8
0x18004a2b6  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004a2bb  test    r14b, r14b
0x18004a2be  jz      short loc_18004A2EB
0x18004a2c0  mov     eax, 800704C7h
0x18004a2c5  mov     [rsp+108h+Reply], eax
0x18004a2c9  mov     [rsp+108h+bAlertable], eax
0x18004a2cd  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004a2d4  mov     r8d, 4CCh; unsigned int
0x18004a2da  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004a2e1  mov     ecx, 2; unsigned __int8
0x18004a2e6  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004a2eb  cmp     [rsp+108h+Reply], 800706B5h
0x18004a2f3  jz      short loc_18004A2FF
0x18004a2f5  cmp     [rsp+108h+Reply], 800706BAh
0x18004a2fd  jnz     short loc_18004A304
0x18004a2ff  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004a304  lea     rcx, [rsp+108h+var_B8]; this
0x18004a309  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18004a30e  mov     eax, [rsp+108h+Reply]
0x18004a312  mov     rcx, [rsp+108h+var_28]
0x18004a31a  xor     rcx, rsp; StackCookie
0x18004a31d  call    __security_check_cookie
0x18004a322  lea     r11, [rsp+108h+var_18]
0x18004a32a  mov     rsi, [r11+30h]
0x18004a32e  mov     r12, [r11+38h]
0x18004a332  mov     rsp, r11
0x18004a335  pop     r15
0x18004a337  pop     r14
0x18004a339  pop     r13
0x18004a33b  retn
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
