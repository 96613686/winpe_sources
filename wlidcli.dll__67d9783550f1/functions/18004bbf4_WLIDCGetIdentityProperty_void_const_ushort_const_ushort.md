# WLIDCGetIdentityProperty(void * const,ushort const *,ushort * *)

- ea: `0x18004bbf4`
- end: `0x18004bf23`
- name: `?WLIDCGetIdentityProperty@@YAJQEAXPEBGPEAPEAG@Z`
- size: `815`
- prototype: `__int64 __fastcall(void *const, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001f980`
- `0x18002f8e0`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180045168`
- `0x180046ce0`
- `0x18004bbf4`
- `0x18004cd04`
- `0x1800530e4`
- `0x180059b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004bd9e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004bdf0`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004bd9e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18004bdf0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004bcbc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004bcbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bccf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004be01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bccf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004be01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004be6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004be6d`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004bdc5`
- `RPCRT4!RpcAsyncCancelCall` at `0x18004bdc5`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004bd16`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004bd16`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004be26`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004be26`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004bc75`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18004bc75`

## string_xrefs

- `0x18004bce1`: `RPC failed to create new event, hr = %#x`
- `0x18004be3a`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCGetIdentityProperty(void *const a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  DWORD v5; // esi
  char v6; // r15
  char v7; // r14
  int LastError; // eax
  const unsigned __int16 *v9; // r9
  unsigned int v10; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v12; // esi
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-F8h]
  unsigned int Reply; // [rsp+40h] [rbp-D8h] BYREF
  char v16; // [rsp+44h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-D0h] BYREF
  DWORD v18; // [rsp+4Ch] [rbp-CCh] BYREF
  unsigned __int16 **v19; // [rsp+50h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+58h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-A8h] BYREF

  v19 = a3;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v5 = dwMilliseconds;
  v18 = dwMilliseconds;
  v6 = 0;
  v16 = 0;
  v7 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v10 = 786;
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
    v9 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_5;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x16u, 0, &pAsync, a1, a2, v19);
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
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_28;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = L"RPC Async complete call failed, hr = %#x";
  }
  v10 = 788;
LABEL_27:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(2u, "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp", v10, v9, *(_QWORD *)bAlertable);
LABEL_28:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v6 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[25],unsigned long &>(
      (__int64)"WLIDCGetIdentityProperty",
      (int *)&v18);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x314u,
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
      0x314u,
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
0x18004bbf4  push    rsi
0x18004bbf6  push    r12
0x18004bbf8  push    r13
0x18004bbfa  push    r14
0x18004bbfc  push    r15
0x18004bbfe  sub     rsp, 0F0h
0x18004bc05  mov     rax, cs:__security_cookie
0x18004bc0c  xor     rax, rsp
0x18004bc0f  mov     [rsp+118h+var_38], rax
0x18004bc17  mov     [rsp+118h+var_C8], r8
0x18004bc1c  mov     r13, rdx
0x18004bc1f  mov     r12, rcx
0x18004bc22  mov     [rsp+118h+Reply], 0
0x18004bc2a  mov     [rsp+118h+dwMilliseconds], 0
0x18004bc32  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x18004bc37  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18004bc3c  xor     edx, edx; Val
0x18004bc3e  lea     r8d, [rdx+70h]; Size
0x18004bc42  lea     rcx, [rsp+118h+pAsync]; void *
0x18004bc47  call    memset_0
0x18004bc4c  mov     esi, [rsp+118h+dwMilliseconds]
0x18004bc50  mov     [rsp+118h+dwMilliseconds], esi
0x18004bc54  mov     [rsp+118h+var_CC], esi
0x18004bc58  xor     r15b, r15b
0x18004bc5b  mov     [rsp+118h+var_D4], r15b
0x18004bc60  xor     r14b, r14b
0x18004bc63  xorps   xmm0, xmm0
0x18004bc66  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x18004bc6b  mov     edx, 70h ; 'p'; Size
0x18004bc70  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004bc75  call    cs:__imp_RpcAsyncInitializeHandle
0x18004bc7b  test    eax, eax
0x18004bc7d  jz      short loc_18004BC9B
0x18004bc7f  jle     short loc_18004BC89
0x18004bc81  movzx   eax, ax
0x18004bc84  or      eax, 80070000h
0x18004bc89  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18004bc90  mov     r8d, 312h
0x18004bc96  jmp     loc_18004BE47
0x18004bc9b  mov     [rsp+118h+pAsync.UserInfo], 0
0x18004bca7  mov     [rsp+118h+pAsync.NotificationType], 1
0x18004bcb2  xor     r9d, r9d; lpName
0x18004bcb5  xor     r8d, r8d; bInitialState
0x18004bcb8  xor     edx, edx; bManualReset
0x18004bcba  xor     ecx, ecx; lpEventAttributes
0x18004bcbc  call    cs:__imp_CreateEventW
0x18004bcc2  mov     qword ptr [rsp+118h+pAsync.u], rax
0x18004bcca  test    rax, rax
0x18004bccd  jnz     short loc_18004BCEA
0x18004bccf  call    cs:__imp_GetLastError
0x18004bcd5  test    eax, eax
0x18004bcd7  jle     short loc_18004BCE1
0x18004bcd9  movzx   eax, ax
0x18004bcdc  or      eax, 80070000h
0x18004bce1  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18004bce8  jmp     short loc_18004BC90
0x18004bcea  mov     [rsp+118h+Handles], rax
0x18004bcef  mov     rax, [rsp+118h+var_C8]
0x18004bcf4  mov     [rsp+118h+var_E8], rax
0x18004bcf9  mov     [rsp+118h+var_F0], r13
0x18004bcfe  mov     qword ptr [rsp+118h+bAlertable], r12
0x18004bd03  lea     r9, [rsp+118h+pAsync]
0x18004bd08  xor     r8d, r8d; pReturnValue
0x18004bd0b  lea     edx, [r8+16h]; nProcNum
0x18004bd0f  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004bd16  call    cs:__imp_Ndr64AsyncClientCall
0x18004bd1c  mov     eax, [rsp+118h+Reply]
0x18004bd20  jmp     short loc_18004BD71
0x18004bd22  test    eax, eax
0x18004bd24  jle     short loc_18004BD2E
0x18004bd26  movzx   eax, ax
0x18004bd29  or      eax, 80070000h
0x18004bd2e  mov     [rsp+118h+Reply], eax
0x18004bd32  mov     [rsp+118h+bAlertable], eax
0x18004bd36  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18004bd3d  mov     r8d, 314h; unsigned int
0x18004bd43  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004bd4a  mov     ecx, 2; unsigned __int8
0x18004bd4f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004bd54  mov     eax, [rsp+118h+Reply]
0x18004bd58  test    eax, eax
0x18004bd5a  js      short loc_18004BD65
0x18004bd5c  mov     eax, 8000FFFFh
0x18004bd61  mov     [rsp+118h+Reply], eax
0x18004bd65  mov     esi, [rsp+118h+dwMilliseconds]
0x18004bd69  mov     r15b, [rsp+118h+var_D4]
0x18004bd6e  mov     r14b, r15b
0x18004bd71  test    eax, eax
0x18004bd73  jns     short loc_18004BD87
0x18004bd75  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18004bd7c  mov     r8d, 314h
0x18004bd82  jmp     loc_18004BE4B
0x18004bd87  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004bd8f  mov     r9d, esi; dwMilliseconds
0x18004bd92  xor     r8d, r8d; bWaitAll
0x18004bd95  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004bd9a  lea     ecx, [r8+1]; nCount
0x18004bd9e  call    cs:__imp_WaitForMultipleObjectsEx
0x18004bda4  mov     esi, eax
0x18004bda6  mov     r12d, 102h
0x18004bdac  test    r14b, r14b
0x18004bdaf  jnz     short loc_18004BDFD
0x18004bdb1  cmp     esi, r12d
0x18004bdb4  jz      short loc_18004BDBB
0x18004bdb6  cmp     esi, 1
0x18004bdb9  jnz     short loc_18004BDFD
0x18004bdbb  mov     edx, 1; fAbort
0x18004bdc0  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004bdc5  call    cs:__imp_RpcAsyncCancelCall
0x18004bdcb  cmp     esi, r12d
0x18004bdce  jnz     short loc_18004BDD5
0x18004bdd0  mov     r15b, 1
0x18004bdd3  jmp     short loc_18004BDD8
0x18004bdd5  mov     r14b, 1
0x18004bdd8  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18004bde0  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004bde4  xor     r8d, r8d; bWaitAll
0x18004bde7  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18004bdec  lea     ecx, [r8+1]; nCount
0x18004bdf0  call    cs:__imp_WaitForMultipleObjectsEx
0x18004bdf6  mov     esi, eax
0x18004bdf8  test    r15b, r15b
0x18004bdfb  jz      short loc_18004BDAC
0x18004bdfd  test    esi, esi
0x18004bdff  jz      short loc_18004BE1C
0x18004be01  call    cs:__imp_GetLastError
0x18004be07  test    eax, eax
0x18004be09  jle     short loc_18004BE13
0x18004be0b  movzx   eax, ax
0x18004be0e  or      eax, 80070000h
0x18004be13  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18004be1a  jmp     short loc_18004BE41
0x18004be1c  lea     rdx, [rsp+118h+Reply]; Reply
0x18004be21  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18004be26  call    cs:__imp_RpcAsyncCompleteCall
0x18004be2c  test    eax, eax
0x18004be2e  jz      short loc_18004BE60
0x18004be30  jle     short loc_18004BE3A
0x18004be32  movzx   eax, ax
0x18004be35  or      eax, 80070000h
0x18004be3a  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18004be41  mov     r8d, 314h; unsigned int
0x18004be47  mov     [rsp+118h+Reply], eax
0x18004be4b  mov     [rsp+118h+bAlertable], eax
0x18004be4f  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004be56  mov     ecx, 2; unsigned __int8
0x18004be5b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004be60  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x18004be68  test    rcx, rcx
0x18004be6b  jz      short loc_18004BE73
0x18004be6d  call    cs:__imp_CloseHandle
0x18004be73  test    r15b, r15b
0x18004be76  jz      short loc_18004BEB7
0x18004be78  mov     [rsp+118h+Reply], 800705B4h
0x18004be80  lea     rdx, [rsp+118h+var_CC]
0x18004be85  lea     rcx, aWlidcgetidenti; "WLIDCGetIdentityProperty"
0x18004be8c  call    ??$RPCCallTimedOut@AEAY0BJ@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BJ@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[25],ulong &>(char const (&)[25],ulong &)
0x18004be91  mov     eax, [rsp+118h+Reply]
0x18004be95  mov     [rsp+118h+bAlertable], eax
0x18004be99  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18004bea0  mov     r8d, 314h; unsigned int
0x18004bea6  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004bead  mov     ecx, 2; unsigned __int8
0x18004beb2  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004beb7  test    r14b, r14b
0x18004beba  jz      short loc_18004BEE7
0x18004bebc  mov     eax, 800704C7h
0x18004bec1  mov     [rsp+118h+Reply], eax
0x18004bec5  mov     [rsp+118h+bAlertable], eax
0x18004bec9  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18004bed0  mov     r8d, 314h; unsigned int
0x18004bed6  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004bedd  mov     ecx, 2; unsigned __int8
0x18004bee2  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004bee7  mov     eax, [rsp+118h+Reply]
0x18004beeb  cmp     eax, 800706B5h
0x18004bef0  jz      short loc_18004BEF9
0x18004bef2  cmp     eax, 800706BAh
0x18004bef7  jnz     short loc_18004BF02
0x18004bef9  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18004befe  mov     eax, [rsp+118h+Reply]
0x18004bf02  mov     rcx, [rsp+118h+var_38]
0x18004bf0a  xor     rcx, rsp; StackCookie
0x18004bf0d  call    __security_check_cookie
0x18004bf12  add     rsp, 0F0h
0x18004bf19  pop     r15
0x18004bf1b  pop     r14
0x18004bf1d  pop     r13
0x18004bf1f  pop     r12
0x18004bf21  pop     rsi
0x18004bf22  retn
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
