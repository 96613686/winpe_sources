# WLIDCGetDeviceDAToken(ushort * *)

- ea: `0x18004670c`
- end: `0x180046a52`
- name: `?WLIDCGetDeviceDAToken@@YAJPEAPEAG@Z`
- size: `838`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180035690`
- `0x180041710`

## callees

- `0x18000a400`
- `0x18000f870`
- `0x180010c68`
- `0x180011588`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180041d0c`
- `0x180043240`
- `0x18004670c`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800467e6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800467e6`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800468c3`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180046915`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800468c3`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180046915`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800467f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046926`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800467f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046926`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046992`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046992`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800467a2`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800467a2`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800468ea`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800468ea`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004683b`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004683b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004694b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004694b`

## string_xrefs

- `0x18004680b`: `RPC failed to create new event, hr = %#x`
- `0x18004695f`: `RPC Async complete call failed, hr = %#x`
- `0x1800469aa`: `WLIDCGetDeviceDAToken`

## pseudocode

```c
__int64 __fastcall WLIDCGetDeviceDAToken(unsigned __int16 **a1, unsigned int a2)
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
    v9 = 1353;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x40u, 0, &pAsync, v17, a1);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v8 = L"RPC call failed, hr = %#x";
    v9 = 1355;
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
    v9 = 1355;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[22],unsigned long &>("WLIDCGetDeviceDAToken", &v16);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x54Bu,
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
      0x54Bu,
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
0x18004670c  push    rsi
0x18004670e  push    r12
0x180046710  push    r14
0x180046712  push    r15
0x180046714  sub     rsp, 0E8h
0x18004671b  mov     rax, cs:__security_cookie
0x180046722  xor     rax, rsp
0x180046725  mov     [rsp+108h+var_38], rax
0x18004672d  mov     r12, rcx
0x180046730  mov     [rsp+108h+dwMilliseconds], 0
0x180046738  lea     r8, [rsp+108h+dwMilliseconds]; unsigned int *
0x18004673d  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180046742  mov     [rsp+108h+Reply], 0
0x18004674a  mov     [rsp+108h+var_C8], 0
0x180046753  lea     rcx, [rsp+108h+var_C8]; this
0x180046758  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18004675d  mov     [rsp+108h+Reply], eax
0x180046761  test    eax, eax
0x180046763  js      loc_180046A33
0x180046769  xor     edx, edx; Val
0x18004676b  lea     r8d, [rdx+70h]; Size
0x18004676f  lea     rcx, [rsp+108h+pAsync]; void *
0x180046774  call    memset_0
0x180046779  mov     esi, [rsp+108h+dwMilliseconds]
0x18004677d  mov     [rsp+108h+dwMilliseconds], esi
0x180046781  mov     [rsp+108h+var_CC], esi
0x180046785  xor     r15b, r15b
0x180046788  mov     [rsp+108h+var_D4], r15b
0x18004678d  xor     r14b, r14b
0x180046790  xorps   xmm0, xmm0
0x180046793  movups  xmmword ptr [rsp+108h+Handles], xmm0
0x180046798  mov     edx, 70h ; 'p'; Size
0x18004679d  lea     rcx, [rsp+108h+pAsync]; pAsync
0x1800467a2  call    cs:__imp_RpcAsyncInitializeHandle
0x1800467a8  test    eax, eax
0x1800467aa  jz      short loc_1800467C8
0x1800467ac  jle     short loc_1800467B6
0x1800467ae  movzx   eax, ax
0x1800467b1  or      eax, 80070000h
0x1800467b6  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x1800467bd  mov     r8d, 549h
0x1800467c3  jmp     loc_18004696C
0x1800467c8  mov     [rsp+108h+pAsync.UserInfo], 0
0x1800467d1  mov     [rsp+108h+pAsync.NotificationType], 1
0x1800467dc  xor     r9d, r9d; lpName
0x1800467df  xor     r8d, r8d; bInitialState
0x1800467e2  xor     edx, edx; bManualReset
0x1800467e4  xor     ecx, ecx; lpEventAttributes
0x1800467e6  call    cs:__imp_CreateEventW
0x1800467ec  mov     qword ptr [rsp+108h+pAsync.u], rax
0x1800467f4  test    rax, rax
0x1800467f7  jnz     short loc_180046814
0x1800467f9  call    cs:__imp_GetLastError
0x1800467ff  test    eax, eax
0x180046801  jle     short loc_18004680B
0x180046803  movzx   eax, ax
0x180046806  or      eax, 80070000h
0x18004680b  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180046812  jmp     short loc_1800467BD
0x180046814  mov     [rsp+108h+Handles], rax
0x180046819  mov     [rsp+108h+var_E0], r12
0x18004681e  mov     rax, [rsp+108h+var_C8]
0x180046823  mov     qword ptr [rsp+108h+bAlertable], rax
0x180046828  lea     r9, [rsp+108h+pAsync]
0x18004682d  xor     r8d, r8d; pReturnValue
0x180046830  lea     edx, [r8+40h]; nProcNum
0x180046834  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004683b  call    cs:__imp_Ndr64AsyncClientCall
0x180046841  mov     eax, [rsp+108h+Reply]
0x180046845  jmp     short loc_180046896
0x180046847  test    eax, eax
0x180046849  jle     short loc_180046853
0x18004684b  movzx   eax, ax
0x18004684e  or      eax, 80070000h
0x180046853  mov     [rsp+108h+Reply], eax
0x180046857  mov     [rsp+108h+bAlertable], eax
0x18004685b  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180046862  mov     r8d, 54Bh; unsigned int
0x180046868  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004686f  mov     ecx, 2; unsigned __int8
0x180046874  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180046879  mov     eax, [rsp+108h+Reply]
0x18004687d  test    eax, eax
0x18004687f  js      short loc_18004688A
0x180046881  mov     eax, 8000FFFFh
0x180046886  mov     [rsp+108h+Reply], eax
0x18004688a  mov     esi, [rsp+108h+dwMilliseconds]
0x18004688e  mov     r15b, [rsp+108h+var_D4]
0x180046893  mov     r14b, r15b
0x180046896  test    eax, eax
0x180046898  jns     short loc_1800468AC
0x18004689a  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x1800468a1  mov     r8d, 54Bh
0x1800468a7  jmp     loc_180046970
0x1800468ac  mov     [rsp+108h+bAlertable], 0; bAlertable
0x1800468b4  mov     r9d, esi; dwMilliseconds
0x1800468b7  xor     r8d, r8d; bWaitAll
0x1800468ba  lea     rdx, [rsp+108h+Handles]; lpHandles
0x1800468bf  lea     ecx, [r8+1]; nCount
0x1800468c3  call    cs:__imp_WaitForMultipleObjectsEx
0x1800468c9  mov     esi, eax
0x1800468cb  mov     r12d, 102h
0x1800468d1  test    r14b, r14b
0x1800468d4  jnz     short loc_180046922
0x1800468d6  cmp     esi, r12d
0x1800468d9  jz      short loc_1800468E0
0x1800468db  cmp     esi, 1
0x1800468de  jnz     short loc_180046922
0x1800468e0  mov     edx, 1; fAbort
0x1800468e5  lea     rcx, [rsp+108h+pAsync]; pAsync
0x1800468ea  call    cs:__imp_RpcAsyncCancelCall
0x1800468f0  cmp     esi, r12d
0x1800468f3  jnz     short loc_1800468FA
0x1800468f5  mov     r15b, 1
0x1800468f8  jmp     short loc_1800468FD
0x1800468fa  mov     r14b, 1
0x1800468fd  mov     [rsp+108h+bAlertable], 0; bAlertable
0x180046905  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180046909  xor     r8d, r8d; bWaitAll
0x18004690c  lea     rdx, [rsp+108h+Handles]; lpHandles
0x180046911  lea     ecx, [r8+1]; nCount
0x180046915  call    cs:__imp_WaitForMultipleObjectsEx
0x18004691b  mov     esi, eax
0x18004691d  test    r15b, r15b
0x180046920  jz      short loc_1800468D1
0x180046922  test    esi, esi
0x180046924  jz      short loc_180046941
0x180046926  call    cs:__imp_GetLastError
0x18004692c  test    eax, eax
0x18004692e  jle     short loc_180046938
0x180046930  movzx   eax, ax
0x180046933  or      eax, 80070000h
0x180046938  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004693f  jmp     short loc_180046966
0x180046941  lea     rdx, [rsp+108h+Reply]; Reply
0x180046946  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18004694b  call    cs:__imp_RpcAsyncCompleteCall
0x180046951  test    eax, eax
0x180046953  jz      short loc_180046985
0x180046955  jle     short loc_18004695F
0x180046957  movzx   eax, ax
0x18004695a  or      eax, 80070000h
0x18004695f  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180046966  mov     r8d, 54Bh; unsigned int
0x18004696c  mov     [rsp+108h+Reply], eax
0x180046970  mov     [rsp+108h+bAlertable], eax
0x180046974  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004697b  mov     ecx, 2; unsigned __int8
0x180046980  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180046985  mov     rcx, qword ptr [rsp+108h+pAsync.u]; hObject
0x18004698d  test    rcx, rcx
0x180046990  jz      short loc_180046998
0x180046992  call    cs:__imp_CloseHandle
0x180046998  test    r15b, r15b
0x18004699b  jz      short loc_1800469DC
0x18004699d  mov     [rsp+108h+Reply], 800705B4h
0x1800469a5  lea     rdx, [rsp+108h+var_CC]
0x1800469aa  lea     rcx, aWlidcgetdevice; "WLIDCGetDeviceDAToken"
0x1800469b1  call    ??$RPCCallTimedOut@AEAY0BG@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BG@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[22],ulong &>(char const (&)[22],ulong &)
0x1800469b6  mov     eax, [rsp+108h+Reply]
0x1800469ba  mov     [rsp+108h+bAlertable], eax
0x1800469be  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x1800469c5  mov     r8d, 54Bh; unsigned int
0x1800469cb  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800469d2  mov     ecx, 2; unsigned __int8
0x1800469d7  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800469dc  test    r14b, r14b
0x1800469df  jz      short loc_180046A0C
0x1800469e1  mov     eax, 800704C7h
0x1800469e6  mov     [rsp+108h+Reply], eax
0x1800469ea  mov     [rsp+108h+bAlertable], eax
0x1800469ee  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x1800469f5  mov     r8d, 54Bh; unsigned int
0x1800469fb  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180046a02  mov     ecx, 2; unsigned __int8
0x180046a07  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180046a0c  cmp     [rsp+108h+Reply], 800706B5h
0x180046a14  jz      short loc_180046A20
0x180046a16  cmp     [rsp+108h+Reply], 800706BAh
0x180046a1e  jnz     short loc_180046A25
0x180046a20  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180046a25  lea     rcx, [rsp+108h+var_C8]; this
0x180046a2a  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x180046a2f  mov     eax, [rsp+108h+Reply]
0x180046a33  mov     rcx, [rsp+108h+var_38]
0x180046a3b  xor     rcx, rsp; StackCookie
0x180046a3e  call    __security_check_cookie
0x180046a43  add     rsp, 0E8h
0x180046a4a  pop     r15
0x180046a4c  pop     r14
0x180046a4e  pop     r12
0x180046a50  pop     rsi
0x180046a51  retn
0x180057041  push    rbp
0x180057043  sub     rsp, 30h
0x180057047  mov     rbp, rdx
0x18005704a  mov     rcx, [rcx]
0x18005704d  mov     ecx, [rcx]; unsigned int
0x18005704f  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x180057054  nop
0x180057055  add     rsp, 30h
0x180057059  pop     rbp
0x18005705a  retn
```
