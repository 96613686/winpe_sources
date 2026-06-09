# WLIDCSetAuthData(void * const,unsigned __int64,ulong,uchar *)

- ea: `0x18004ef0c`
- end: `0x18004f244`
- name: `?WLIDCSetAuthData@@YAJQEAX_KKPEAE@Z`
- size: `824`
- prototype: `__int64 __fastcall(void *const, unsigned __int64, unsigned int, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180032f20`
- `0x18003c770`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180044d94`
- `0x180046ce0`
- `0x18004cd04`
- `0x18004ef0c`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004f0bf`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004f111`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004f0bf`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004f111`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004efd4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004efd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004efe7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f122`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004efe7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f122`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f18e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f18e`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004f0e6`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004f0e6`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004f037`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004f037`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004f147`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004f147`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004ef8d`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004ef8d`

## string_xrefs

- `0x18004eff9`: `RPC failed to create new event, hr = %#x`
- `0x18004f15b`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCSetAuthData(void *const a1, unsigned int a2, int a3, unsigned __int8 *a4)
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
  BOOL bAlertable[2]; // [rsp+20h] [rbp-F8h]
  unsigned int Reply; // [rsp+40h] [rbp-D8h] BYREF
  char v17; // [rsp+44h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-D0h] BYREF
  DWORD v19; // [rsp+4Ch] [rbp-CCh] BYREF
  unsigned __int8 *v20; // [rsp+50h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+58h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-A8h] BYREF

  v20 = a4;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
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
    v11 = 610;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0xCu, 0, &pAsync, a1, 0, a3, v20);
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
  v11 = 612;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[17],unsigned long &>(
      (__int64)"WLIDCSetAuthData",
      (int *)&v19);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x264u,
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
      0x264u,
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
0x18004ef0c  push    rsi
0x18004ef0e  push    r12
0x18004ef10  push    r13
0x18004ef12  push    r14
0x18004ef14  push    r15
0x18004ef16  sub     rsp, 0F0h
0x18004ef1d  mov     rax, cs:__security_cookie
0x18004ef24  xor     rax, rsp
0x18004ef27  mov     [rsp+118h+var_38], rax
0x18004ef2f  mov     [rsp+118h+var_C8], r9
0x18004ef34  mov     r13d, r8d
0x18004ef37  mov     r12, rcx
0x18004ef3a  mov     [rsp+118h+Reply], 0
0x18004ef42  mov     [rsp+118h+dwMilliseconds], 0
0x18004ef4a  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x18004ef4f  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004ef54  xor     edx, edx; Val
0x18004ef56  lea     r8d, [rdx+70h]; Size
0x18004ef5a  lea     rcx, [rsp+118h+pAsync]; void *
0x18004ef5f  call    memset_0
0x18004ef64  mov     esi, [rsp+118h+dwMilliseconds]
0x18004ef68  mov     [rsp+118h+dwMilliseconds], esi
0x18004ef6c  mov     [rsp+118h+var_CC], esi
0x18004ef70  xor     r15b, r15b
0x18004ef73  mov     [rsp+118h+var_D4], r15b
0x18004ef78  xor     r14b, r14b
0x18004ef7b  xorps   xmm0, xmm0
0x18004ef7e  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x18004ef83  mov     edx, 70h ; 'p'; Size
0x18004ef88  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004ef8d  call    cs:__imp_RpcAsyncInitializeHandle
0x18004ef93  test    eax, eax
0x18004ef95  jz      short loc_18004EFB3
0x18004ef97  jle     short loc_18004EFA1
0x18004ef99  movzx   eax, ax
0x18004ef9c  or      eax, 80070000h
0x18004efa1  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004efa8  mov     r8d, 262h
0x18004efae  jmp     loc_18004F168
0x18004efb3  mov     [rsp+118h+pAsync.UserInfo], 0
0x18004efbf  mov     [rsp+118h+pAsync.NotificationType], 1
0x18004efca  xor     r9d, r9d; lpName
0x18004efcd  xor     r8d, r8d; bInitialState
0x18004efd0  xor     edx, edx; bManualReset
0x18004efd2  xor     ecx, ecx; lpEventAttributes
0x18004efd4  call    cs:__imp_CreateEventW
0x18004efda  mov     qword ptr [rsp+118h+pAsync.u], rax
0x18004efe2  test    rax, rax
0x18004efe5  jnz     short loc_18004F002
0x18004efe7  call    cs:__imp_GetLastError
0x18004efed  test    eax, eax
0x18004efef  jle     short loc_18004EFF9
0x18004eff1  movzx   eax, ax
0x18004eff4  or      eax, 80070000h
0x18004eff9  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004f000  jmp     short loc_18004EFA8
0x18004f002  mov     [rsp+118h+Handles], rax
0x18004f007  mov     rax, [rsp+118h+var_C8]
0x18004f00c  mov     [rsp+118h+var_E0], rax
0x18004f011  mov     [rsp+118h+var_E8], r13d
0x18004f016  mov     [rsp+118h+var_F0], 0
0x18004f01f  mov     qword ptr [rsp+118h+bAlertable], r12
0x18004f024  lea     r9, [rsp+118h+pAsync]
0x18004f029  xor     r8d, r8d; pReturnValue
0x18004f02c  lea     edx, [r8+0Ch]; nProcNum
0x18004f030  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004f037  call    cs:__imp_Ndr64AsyncClientCall
0x18004f03d  mov     eax, [rsp+118h+Reply]
0x18004f041  jmp     short loc_18004F092
0x18004f043  test    eax, eax
0x18004f045  jle     short loc_18004F04F
0x18004f047  movzx   eax, ax
0x18004f04a  or      eax, 80070000h
0x18004f04f  mov     [rsp+118h+Reply], eax
0x18004f053  mov     [rsp+118h+bAlertable], eax
0x18004f057  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004f05e  mov     r8d, 264h; unsigned int
0x18004f064  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004f06b  mov     ecx, 2; unsigned __int8
0x18004f070  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004f075  mov     eax, [rsp+118h+Reply]
0x18004f079  test    eax, eax
0x18004f07b  js      short loc_18004F086
0x18004f07d  mov     eax, 8000FFFFh
0x18004f082  mov     [rsp+118h+Reply], eax
0x18004f086  mov     esi, [rsp+118h+dwMilliseconds]
0x18004f08a  mov     r15b, [rsp+118h+var_D4]
0x18004f08f  mov     r14b, r15b
0x18004f092  test    eax, eax
0x18004f094  jns     short loc_18004F0A8
0x18004f096  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004f09d  mov     r8d, 264h
0x18004f0a3  jmp     loc_18004F16C
0x18004f0a8  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004f0b0  mov     r9d, esi; dwMilliseconds
0x18004f0b3  xor     r8d, r8d; bWaitAll
0x18004f0b6  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004f0bb  lea     ecx, [r8+1]; nCount
0x18004f0bf  call    cs:__imp_WaitForMultipleObjectsEx
0x18004f0c5  mov     esi, eax
0x18004f0c7  mov     r12d, 102h
0x18004f0cd  test    r14b, r14b
0x18004f0d0  jnz     short loc_18004F11E
0x18004f0d2  cmp     esi, r12d
0x18004f0d5  jz      short loc_18004F0DC
0x18004f0d7  cmp     esi, 1
0x18004f0da  jnz     short loc_18004F11E
0x18004f0dc  mov     edx, 1; fAbort
0x18004f0e1  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004f0e6  call    cs:__imp_RpcAsyncCancelCall
0x18004f0ec  cmp     esi, r12d
0x18004f0ef  jnz     short loc_18004F0F6
0x18004f0f1  mov     r15b, 1
0x18004f0f4  jmp     short loc_18004F0F9
0x18004f0f6  mov     r14b, 1
0x18004f0f9  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004f101  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004f105  xor     r8d, r8d; bWaitAll
0x18004f108  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004f10d  lea     ecx, [r8+1]; nCount
0x18004f111  call    cs:__imp_WaitForMultipleObjectsEx
0x18004f117  mov     esi, eax
0x18004f119  test    r15b, r15b
0x18004f11c  jz      short loc_18004F0CD
0x18004f11e  test    esi, esi
0x18004f120  jz      short loc_18004F13D
0x18004f122  call    cs:__imp_GetLastError
0x18004f128  test    eax, eax
0x18004f12a  jle     short loc_18004F134
0x18004f12c  movzx   eax, ax
0x18004f12f  or      eax, 80070000h
0x18004f134  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004f13b  jmp     short loc_18004F162
0x18004f13d  lea     rdx, [rsp+118h+Reply]; Reply
0x18004f142  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004f147  call    cs:__imp_RpcAsyncCompleteCall
0x18004f14d  test    eax, eax
0x18004f14f  jz      short loc_18004F181
0x18004f151  jle     short loc_18004F15B
0x18004f153  movzx   eax, ax
0x18004f156  or      eax, 80070000h
0x18004f15b  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004f162  mov     r8d, 264h; unsigned int
0x18004f168  mov     [rsp+118h+Reply], eax
0x18004f16c  mov     [rsp+118h+bAlertable], eax
0x18004f170  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004f177  mov     ecx, 2; unsigned __int8
0x18004f17c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004f181  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x18004f189  test    rcx, rcx
0x18004f18c  jz      short loc_18004F194
0x18004f18e  call    cs:__imp_CloseHandle
0x18004f194  test    r15b, r15b
0x18004f197  jz      short loc_18004F1D8
0x18004f199  mov     [rsp+118h+Reply], 800705B4h
0x18004f1a1  lea     rdx, [rsp+118h+var_CC]
0x18004f1a6  lea     rcx, aWlidcsetauthda; "WLIDCSetAuthData"
0x18004f1ad  call    ??$RPCCallTimedOut@AEAY0BB@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BB@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[17],ulong &>(char const (&)[17],ulong &)
0x18004f1b2  mov     eax, [rsp+118h+Reply]
0x18004f1b6  mov     [rsp+118h+bAlertable], eax
0x18004f1ba  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004f1c1  mov     r8d, 264h; unsigned int
0x18004f1c7  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004f1ce  mov     ecx, 2; unsigned __int8
0x18004f1d3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004f1d8  test    r14b, r14b
0x18004f1db  jz      short loc_18004F208
0x18004f1dd  mov     eax, 800704C7h
0x18004f1e2  mov     [rsp+118h+Reply], eax
0x18004f1e6  mov     [rsp+118h+bAlertable], eax
0x18004f1ea  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004f1f1  mov     r8d, 264h; unsigned int
0x18004f1f7  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004f1fe  mov     ecx, 2; unsigned __int8
0x18004f203  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004f208  mov     eax, [rsp+118h+Reply]
0x18004f20c  cmp     eax, 800706B5h
0x18004f211  jz      short loc_18004F21A
0x18004f213  cmp     eax, 800706BAh
0x18004f218  jnz     short loc_18004F223
0x18004f21a  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004f21f  mov     eax, [rsp+118h+Reply]
0x18004f223  mov     rcx, [rsp+118h+var_38]
0x18004f22b  xor     rcx, rsp; StackCookie
0x18004f22e  call    __security_check_cookie
0x18004f233  add     rsp, 0F0h
0x18004f23a  pop     r15
0x18004f23c  pop     r14
0x18004f23e  pop     r13
0x18004f240  pop     r12
0x18004f242  pop     rsi
0x18004f243  retn
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
