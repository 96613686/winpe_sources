# WLIDCNCreateContext(ulong,ushort * *,void * *)

- ea: `0x180048ff8`
- end: `0x18004933a`
- name: `?WLIDCNCreateContext@@YAJKPEAPEAGPEAPEAX@Z`
- size: `834`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 **, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800027e0`

## callees

- `0x18000a400`
- `0x18000f870`
- `0x180011588`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180041bf4`
- `0x180043240`
- `0x180048ff8`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800490c6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800490c6`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800491a9`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800491fb`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800491a9`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800491fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800490d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004920c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800490d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004920c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049278`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049278`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004907f`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004907f`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800491d0`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800491d0`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180049122`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180049122`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180049231`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180049231`

## string_xrefs

- `0x1800490eb`: `RPC failed to create new event, hr = %#x`
- `0x180049245`: `RPC Async complete call failed, hr = %#x`
- `0x180049290`: `WLIDCNCreateContext`

## pseudocode

```c
__int64 __fastcall WLIDCNCreateContext(int a1, unsigned __int16 **a2, void **a3)
{
  __int64 result; // rax
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
  int v17; // [rsp+48h] [rbp-D0h] BYREF
  __int64 v18; // [rsp+50h] [rbp-C8h] BYREF
  HANDLE Handles[3]; // [rsp+58h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-A8h] BYREF

  v18 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v18);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v17 = 600000;
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
    v11 = 1161;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvcnotify_ProxyInfo, 0, 0, &pAsync, v18, a1, a2, a3);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v10 = L"RPC call failed, hr = %#x";
    v11 = 1163;
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
  v13 = WaitForMultipleObjectsEx(1u, Handles, 0, 0x927C0u, 0);
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
    v11 = 1163;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[20],unsigned long &>("WLIDCNCreateContext", &v17);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x48Bu,
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
      0x48Bu,
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
0x180048ff8  push    rsi
0x180048ffa  push    r12
0x180048ffc  push    r13
0x180048ffe  push    r14
0x180049000  push    r15
0x180049002  sub     rsp, 0F0h
0x180049009  mov     rax, cs:__security_cookie
0x180049010  xor     rax, rsp
0x180049013  mov     [rsp+118h+var_38], rax
0x18004901b  mov     r13, r8
0x18004901e  mov     r12, rdx
0x180049021  mov     esi, ecx
0x180049023  mov     [rsp+118h+Reply], 0
0x18004902b  mov     [rsp+118h+var_C8], 0
0x180049034  lea     rcx, [rsp+118h+var_C8]; this
0x180049039  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18004903e  mov     [rsp+118h+Reply], eax
0x180049042  test    eax, eax
0x180049044  js      loc_180049319
0x18004904a  xor     edx, edx; Val
0x18004904c  lea     r8d, [rdx+70h]; Size
0x180049050  lea     rcx, [rsp+118h+pAsync]; void *
0x180049055  call    memset_0
0x18004905a  mov     [rsp+118h+var_D0], 927C0h
0x180049062  xor     r15b, r15b
0x180049065  mov     [rsp+118h+var_D4], r15b
0x18004906a  xor     r14b, r14b
0x18004906d  xorps   xmm0, xmm0
0x180049070  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x180049075  mov     edx, 70h ; 'p'; Size
0x18004907a  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004907f  call    cs:__imp_RpcAsyncInitializeHandle
0x180049085  test    eax, eax
0x180049087  jz      short loc_1800490A5
0x180049089  jle     short loc_180049093
0x18004908b  movzx   eax, ax
0x18004908e  or      eax, 80070000h
0x180049093  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004909a  mov     r8d, 489h
0x1800490a0  jmp     loc_180049252
0x1800490a5  mov     [rsp+118h+pAsync.UserInfo], 0
0x1800490b1  mov     [rsp+118h+pAsync.NotificationType], 1
0x1800490bc  xor     r9d, r9d; lpName
0x1800490bf  xor     r8d, r8d; bInitialState
0x1800490c2  xor     edx, edx; bManualReset
0x1800490c4  xor     ecx, ecx; lpEventAttributes
0x1800490c6  call    cs:__imp_CreateEventW
0x1800490cc  mov     qword ptr [rsp+118h+pAsync.u], rax
0x1800490d4  test    rax, rax
0x1800490d7  jnz     short loc_1800490F4
0x1800490d9  call    cs:__imp_GetLastError
0x1800490df  test    eax, eax
0x1800490e1  jle     short loc_1800490EB
0x1800490e3  movzx   eax, ax
0x1800490e6  or      eax, 80070000h
0x1800490eb  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x1800490f2  jmp     short loc_18004909A
0x1800490f4  mov     [rsp+118h+Handles], rax
0x1800490f9  mov     [rsp+118h+var_E0], r13
0x1800490fe  mov     [rsp+118h+var_E8], r12
0x180049103  mov     [rsp+118h+var_F0], esi
0x180049107  mov     rax, [rsp+118h+var_C8]
0x18004910c  mov     qword ptr [rsp+118h+bAlertable], rax
0x180049111  lea     r9, [rsp+118h+pAsync]
0x180049116  xor     r8d, r8d; pReturnValue
0x180049119  xor     edx, edx; nProcNum
0x18004911b  lea     rcx, ?liveidsvcnotify_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180049122  call    cs:__imp_Ndr64AsyncClientCall
0x180049128  mov     eax, [rsp+118h+Reply]
0x18004912c  jmp     short loc_180049179
0x18004912e  test    eax, eax
0x180049130  jle     short loc_18004913A
0x180049132  movzx   eax, ax
0x180049135  or      eax, 80070000h
0x18004913a  mov     [rsp+118h+Reply], eax
0x18004913e  mov     [rsp+118h+bAlertable], eax
0x180049142  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180049149  mov     r8d, 48Bh; unsigned int
0x18004914f  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180049156  mov     ecx, 2; unsigned __int8
0x18004915b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180049160  mov     eax, [rsp+118h+Reply]
0x180049164  test    eax, eax
0x180049166  js      short loc_180049171
0x180049168  mov     eax, 8000FFFFh
0x18004916d  mov     [rsp+118h+Reply], eax
0x180049171  mov     r15b, [rsp+118h+var_D4]
0x180049176  mov     r14b, r15b
0x180049179  test    eax, eax
0x18004917b  jns     short loc_18004918F
0x18004917d  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180049184  mov     r8d, 48Bh
0x18004918a  jmp     loc_180049256
0x18004918f  mov     [rsp+118h+bAlertable], 0; bAlertable
0x180049197  mov     r9d, 927C0h; dwMilliseconds
0x18004919d  xor     r8d, r8d; bWaitAll
0x1800491a0  lea     rdx, [rsp+118h+Handles]; lpHandles
0x1800491a5  lea     ecx, [r8+1]; nCount
0x1800491a9  call    cs:__imp_WaitForMultipleObjectsEx
0x1800491af  mov     esi, eax
0x1800491b1  mov     r12d, 102h
0x1800491b7  test    r14b, r14b
0x1800491ba  jnz     short loc_180049208
0x1800491bc  cmp     esi, r12d
0x1800491bf  jz      short loc_1800491C6
0x1800491c1  cmp     esi, 1
0x1800491c4  jnz     short loc_180049208
0x1800491c6  mov     edx, 1; fAbort
0x1800491cb  lea     rcx, [rsp+118h+pAsync]; pAsync
0x1800491d0  call    cs:__imp_RpcAsyncCancelCall
0x1800491d6  cmp     esi, r12d
0x1800491d9  jnz     short loc_1800491E0
0x1800491db  mov     r15b, 1
0x1800491de  jmp     short loc_1800491E3
0x1800491e0  mov     r14b, 1
0x1800491e3  mov     [rsp+118h+bAlertable], 0; bAlertable
0x1800491eb  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800491ef  xor     r8d, r8d; bWaitAll
0x1800491f2  lea     rdx, [rsp+118h+Handles]; lpHandles
0x1800491f7  lea     ecx, [r8+1]; nCount
0x1800491fb  call    cs:__imp_WaitForMultipleObjectsEx
0x180049201  mov     esi, eax
0x180049203  test    r15b, r15b
0x180049206  jz      short loc_1800491B7
0x180049208  test    esi, esi
0x18004920a  jz      short loc_180049227
0x18004920c  call    cs:__imp_GetLastError
0x180049212  test    eax, eax
0x180049214  jle     short loc_18004921E
0x180049216  movzx   eax, ax
0x180049219  or      eax, 80070000h
0x18004921e  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180049225  jmp     short loc_18004924C
0x180049227  lea     rdx, [rsp+118h+Reply]; Reply
0x18004922c  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180049231  call    cs:__imp_RpcAsyncCompleteCall
0x180049237  test    eax, eax
0x180049239  jz      short loc_18004926B
0x18004923b  jle     short loc_180049245
0x18004923d  movzx   eax, ax
0x180049240  or      eax, 80070000h
0x180049245  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004924c  mov     r8d, 48Bh; unsigned int
0x180049252  mov     [rsp+118h+Reply], eax
0x180049256  mov     [rsp+118h+bAlertable], eax
0x18004925a  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180049261  mov     ecx, 2; unsigned __int8
0x180049266  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004926b  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x180049273  test    rcx, rcx
0x180049276  jz      short loc_18004927E
0x180049278  call    cs:__imp_CloseHandle
0x18004927e  test    r15b, r15b
0x180049281  jz      short loc_1800492C2
0x180049283  mov     [rsp+118h+Reply], 800705B4h
0x18004928b  lea     rdx, [rsp+118h+var_D0]
0x180049290  lea     rcx, aWlidcncreateco; "WLIDCNCreateContext"
0x180049297  call    ??$RPCCallTimedOut@AEAY0BE@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BE@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[20],ulong &>(char const (&)[20],ulong &)
0x18004929c  mov     eax, [rsp+118h+Reply]
0x1800492a0  mov     [rsp+118h+bAlertable], eax
0x1800492a4  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x1800492ab  mov     r8d, 48Bh; unsigned int
0x1800492b1  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800492b8  mov     ecx, 2; unsigned __int8
0x1800492bd  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800492c2  test    r14b, r14b
0x1800492c5  jz      short loc_1800492F2
0x1800492c7  mov     eax, 800704C7h
0x1800492cc  mov     [rsp+118h+Reply], eax
0x1800492d0  mov     [rsp+118h+bAlertable], eax
0x1800492d4  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x1800492db  mov     r8d, 48Bh; unsigned int
0x1800492e1  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800492e8  mov     ecx, 2; unsigned __int8
0x1800492ed  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800492f2  cmp     [rsp+118h+Reply], 800706B5h
0x1800492fa  jz      short loc_180049306
0x1800492fc  cmp     [rsp+118h+Reply], 800706BAh
0x180049304  jnz     short loc_18004930B
0x180049306  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004930b  lea     rcx, [rsp+118h+var_C8]; this
0x180049310  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x180049315  mov     eax, [rsp+118h+Reply]
0x180049319  mov     rcx, [rsp+118h+var_38]
0x180049321  xor     rcx, rsp; StackCookie
0x180049324  call    __security_check_cookie
0x180049329  add     rsp, 0F0h
0x180049330  pop     r15
0x180049332  pop     r14
0x180049334  pop     r13
0x180049336  pop     r12
0x180049338  pop     rsi
0x180049339  retn
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
