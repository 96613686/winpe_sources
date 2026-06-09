# WLIDCPersistCredential(void * const,ushort const *,unsigned __int64,ushort * *)

- ea: `0x18004de44`
- end: `0x18004e18f`
- name: `?WLIDCPersistCredential@@YAJQEAXPEBG_KPEAPEAG@Z`
- size: `843`
- prototype: `__int64 __fastcall(void *const, const unsigned __int16 *, unsigned __int64, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180032600`
- `0x18003c770`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x1800450dc`
- `0x180046ce0`
- `0x18004cd04`
- `0x18004de44`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004e001`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004e053`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004e001`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004e053`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004df16`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004df16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004df29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e064`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004df29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e064`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e0d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e0d0`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004e028`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004e028`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004df79`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004df79`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004e089`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004e089`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004decf`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004decf`

## string_xrefs

- `0x18004df3b`: `RPC failed to create new event, hr = %#x`
- `0x18004e09d`: `RPC Async complete call failed, hr = %#x`

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
  DWORD v13; // esi
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-E8h]
  unsigned int Reply; // [rsp+40h] [rbp-C8h] BYREF
  char v17; // [rsp+44h] [rbp-C4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-C0h] BYREF
  DWORD v19; // [rsp+4Ch] [rbp-BCh] BYREF
  __int64 v20; // [rsp+50h] [rbp-B8h] BYREF
  HANDLE Handles[3]; // [rsp+58h] [rbp-B0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-98h] BYREF

  v20 = 0;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v6 = dwMilliseconds;
  v19 = dwMilliseconds;
  v7 = 0;
  v17 = 0;
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
    v10 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_5;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x1Bu, 0, &pAsync, a1, a2, 0, &v20);
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
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_28;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC Async complete call failed, hr = %#x";
  }
  v11 = 847;
LABEL_27:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(
    2u,
    "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
    v11,
    v10,
    *(_QWORD *)bAlertable);
LABEL_28:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v7 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[23],unsigned long &>(
      (__int64)"WLIDCPersistCredential",
      (int *)&v19);
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
0x18004de44  mov     [rsp+arg_10], rsi
0x18004de49  mov     [rsp+arg_18], r12
0x18004de4e  push    r13
0x18004de50  push    r14
0x18004de52  push    r15
0x18004de54  sub     rsp, 0F0h
0x18004de5b  mov     rax, cs:__security_cookie
0x18004de62  xor     rax, rsp
0x18004de65  mov     [rsp+108h+var_28], rax
0x18004de6d  mov     r13, rdx
0x18004de70  mov     r12, rcx
0x18004de73  mov     [rsp+108h+var_B8], 0
0x18004de7c  mov     [rsp+108h+Reply], 0
0x18004de84  mov     [rsp+108h+dwMilliseconds], 0
0x18004de8c  lea     r8, [rsp+108h+dwMilliseconds]; unsigned int *
0x18004de91  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004de96  xor     edx, edx; Val
0x18004de98  lea     r8d, [rdx+70h]; Size
0x18004de9c  lea     rcx, [rsp+108h+pAsync]; void *
0x18004dea1  call    memset_0
0x18004dea6  mov     esi, [rsp+108h+dwMilliseconds]
0x18004deaa  mov     [rsp+108h+dwMilliseconds], esi
0x18004deae  mov     [rsp+108h+var_BC], esi
0x18004deb2  xor     r15b, r15b
0x18004deb5  mov     [rsp+108h+var_C4], r15b
0x18004deba  xor     r14b, r14b
0x18004debd  xorps   xmm0, xmm0
0x18004dec0  movups  xmmword ptr [rsp+108h+Handles], xmm0
0x18004dec5  mov     edx, 70h ; 'p'; Size
0x18004deca  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004decf  call    cs:__imp_RpcAsyncInitializeHandle
0x18004ded5  test    eax, eax
0x18004ded7  jz      short loc_18004DEF5
0x18004ded9  jle     short loc_18004DEE3
0x18004dedb  movzx   eax, ax
0x18004dede  or      eax, 80070000h
0x18004dee3  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004deea  mov     r8d, 348h
0x18004def0  jmp     loc_18004E0AA
0x18004def5  mov     [rsp+108h+pAsync.UserInfo], 0
0x18004df01  mov     [rsp+108h+pAsync.NotificationType], 1
0x18004df0c  xor     r9d, r9d; lpName
0x18004df0f  xor     r8d, r8d; bInitialState
0x18004df12  xor     edx, edx; bManualReset
0x18004df14  xor     ecx, ecx; lpEventAttributes
0x18004df16  call    cs:__imp_CreateEventW
0x18004df1c  mov     qword ptr [rsp+108h+pAsync.u], rax
0x18004df24  test    rax, rax
0x18004df27  jnz     short loc_18004DF44
0x18004df29  call    cs:__imp_GetLastError
0x18004df2f  test    eax, eax
0x18004df31  jle     short loc_18004DF3B
0x18004df33  movzx   eax, ax
0x18004df36  or      eax, 80070000h
0x18004df3b  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004df42  jmp     short loc_18004DEEA
0x18004df44  mov     [rsp+108h+Handles], rax
0x18004df49  lea     rax, [rsp+108h+var_B8]
0x18004df4e  mov     [rsp+108h+var_D0], rax
0x18004df53  mov     [rsp+108h+var_D8], 0
0x18004df5c  mov     [rsp+108h+var_E0], r13
0x18004df61  mov     qword ptr [rsp+108h+bAlertable], r12
0x18004df66  lea     r9, [rsp+108h+pAsync]
0x18004df6b  xor     r8d, r8d; pReturnValue
0x18004df6e  lea     edx, [r8+1Bh]; nProcNum
0x18004df72  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004df79  call    cs:__imp_Ndr64AsyncClientCall
0x18004df7f  mov     eax, [rsp+108h+Reply]
0x18004df83  jmp     short loc_18004DFD4
0x18004df85  test    eax, eax
0x18004df87  jle     short loc_18004DF91
0x18004df89  movzx   eax, ax
0x18004df8c  or      eax, 80070000h
0x18004df91  mov     [rsp+108h+Reply], eax
0x18004df95  mov     [rsp+108h+bAlertable], eax
0x18004df99  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004dfa0  mov     r8d, 34Fh; unsigned int
0x18004dfa6  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004dfad  mov     ecx, 2; unsigned __int8
0x18004dfb2  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004dfb7  mov     eax, [rsp+108h+Reply]
0x18004dfbb  test    eax, eax
0x18004dfbd  js      short loc_18004DFC8
0x18004dfbf  mov     eax, 8000FFFFh
0x18004dfc4  mov     [rsp+108h+Reply], eax
0x18004dfc8  mov     esi, [rsp+108h+dwMilliseconds]
0x18004dfcc  mov     r15b, [rsp+108h+var_C4]
0x18004dfd1  mov     r14b, r15b
0x18004dfd4  test    eax, eax
0x18004dfd6  jns     short loc_18004DFEA
0x18004dfd8  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004dfdf  mov     r8d, 34Fh
0x18004dfe5  jmp     loc_18004E0AE
0x18004dfea  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18004dff2  mov     r9d, esi; dwMilliseconds
0x18004dff5  xor     r8d, r8d; bWaitAll
0x18004dff8  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18004dffd  lea     ecx, [r8+1]; nCount
0x18004e001  call    cs:__imp_WaitForMultipleObjectsEx
0x18004e007  mov     esi, eax
0x18004e009  mov     r12d, 102h
0x18004e00f  test    r14b, r14b
0x18004e012  jnz     short loc_18004E060
0x18004e014  cmp     esi, r12d
0x18004e017  jz      short loc_18004E01E
0x18004e019  cmp     esi, 1
0x18004e01c  jnz     short loc_18004E060
0x18004e01e  mov     edx, 1; fAbort
0x18004e023  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004e028  call    cs:__imp_RpcAsyncCancelCall
0x18004e02e  cmp     esi, r12d
0x18004e031  jnz     short loc_18004E038
0x18004e033  mov     r15b, 1
0x18004e036  jmp     short loc_18004E03B
0x18004e038  mov     r14b, 1
0x18004e03b  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18004e043  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004e047  xor     r8d, r8d; bWaitAll
0x18004e04a  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18004e04f  lea     ecx, [r8+1]; nCount
0x18004e053  call    cs:__imp_WaitForMultipleObjectsEx
0x18004e059  mov     esi, eax
0x18004e05b  test    r15b, r15b
0x18004e05e  jz      short loc_18004E00F
0x18004e060  test    esi, esi
0x18004e062  jz      short loc_18004E07F
0x18004e064  call    cs:__imp_GetLastError
0x18004e06a  test    eax, eax
0x18004e06c  jle     short loc_18004E076
0x18004e06e  movzx   eax, ax
0x18004e071  or      eax, 80070000h
0x18004e076  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004e07d  jmp     short loc_18004E0A4
0x18004e07f  lea     rdx, [rsp+108h+Reply]; Reply
0x18004e084  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004e089  call    cs:__imp_RpcAsyncCompleteCall
0x18004e08f  test    eax, eax
0x18004e091  jz      short loc_18004E0C3
0x18004e093  jle     short loc_18004E09D
0x18004e095  movzx   eax, ax
0x18004e098  or      eax, 80070000h
0x18004e09d  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004e0a4  mov     r8d, 34Fh; unsigned int
0x18004e0aa  mov     [rsp+108h+Reply], eax
0x18004e0ae  mov     [rsp+108h+bAlertable], eax
0x18004e0b2  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004e0b9  mov     ecx, 2; unsigned __int8
0x18004e0be  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004e0c3  mov     rcx, qword ptr [rsp+108h+pAsync.u]; hObject
0x18004e0cb  test    rcx, rcx
0x18004e0ce  jz      short loc_18004E0D6
0x18004e0d0  call    cs:__imp_CloseHandle
0x18004e0d6  test    r15b, r15b
0x18004e0d9  jz      short loc_18004E11A
0x18004e0db  mov     [rsp+108h+Reply], 800705B4h
0x18004e0e3  lea     rdx, [rsp+108h+var_BC]
0x18004e0e8  lea     rcx, aWlidcpersistcr; "WLIDCPersistCredential"
0x18004e0ef  call    ??$RPCCallTimedOut@AEAY0BH@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BH@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[23],ulong &>(char const (&)[23],ulong &)
0x18004e0f4  mov     eax, [rsp+108h+Reply]
0x18004e0f8  mov     [rsp+108h+bAlertable], eax
0x18004e0fc  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004e103  mov     r8d, 34Fh; unsigned int
0x18004e109  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004e110  mov     ecx, 2; unsigned __int8
0x18004e115  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004e11a  test    r14b, r14b
0x18004e11d  jz      short loc_18004E14A
0x18004e11f  mov     eax, 800704C7h
0x18004e124  mov     [rsp+108h+Reply], eax
0x18004e128  mov     [rsp+108h+bAlertable], eax
0x18004e12c  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004e133  mov     r8d, 34Fh; unsigned int
0x18004e139  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004e140  mov     ecx, 2; unsigned __int8
0x18004e145  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004e14a  mov     eax, [rsp+108h+Reply]
0x18004e14e  cmp     eax, 800706B5h
0x18004e153  jz      short loc_18004E15C
0x18004e155  cmp     eax, 800706BAh
0x18004e15a  jnz     short loc_18004E165
0x18004e15c  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004e161  mov     eax, [rsp+108h+Reply]
0x18004e165  mov     rcx, [rsp+108h+var_28]
0x18004e16d  xor     rcx, rsp; StackCookie
0x18004e170  call    __security_check_cookie
0x18004e175  lea     r11, [rsp+108h+var_18]
0x18004e17d  mov     rsi, [r11+30h]
0x18004e181  mov     r12, [r11+38h]
0x18004e185  mov     rsp, r11
0x18004e188  pop     r15
0x18004e18a  pop     r14
0x18004e18c  pop     r13
0x18004e18e  retn
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
