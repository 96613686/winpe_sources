# WLIDCNDeleteContext(void * *)

- ea: `0x180014db0`
- end: `0x180015232`
- name: `?WLIDCNDeleteContext@@YAJPEAPEAX@Z`
- size: `1154`
- prototype: `__int64 __fastcall(void **ContextHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800027e0`

## callees

- `0x18000a400`
- `0x180014db0`
- `0x180015be0`
- `0x18001a0d0`
- `0x180043240`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014e78`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014e78`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180014f5a`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180014fac`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180014f5a`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180014fac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014fbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014fbd`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001517d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001517d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015029`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015029`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180014e35`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180014e35`
- `RPCRT4!RpcSsDestroyClientContext` at `0x1800151fe`
- `RPCRT4!RpcSsDestroyClientContext` at `0x1800151fe`
- `RPCRT4!RpcAsyncCancelCall` at `0x180014f7e`
- `RPCRT4!RpcAsyncCancelCall` at `0x180014f7e`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180014ecd`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180014ecd`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180014fe2`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180014fe2`

## string_xrefs

- `0x180014e9d`: `RPC failed to create new event, hr = %#x`
- `0x180014ff6`: `RPC Async complete call failed, hr = %#x`
- `0x1800150c8`: `WLIDCNDeleteContext`

## pseudocode

```c
__int64 __fastcall WLIDCNDeleteContext(void **ContextHandle)
{
  char v2; // si
  char v3; // di
  int LastError; // eax
  const unsigned __int16 *v5; // r9
  unsigned int v6; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v8; // ebx
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  __int64 v10; // rcx
  int v11; // eax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-138h]
  int Reply; // [rsp+30h] [rbp-128h] BYREF
  int v15; // [rsp+38h] [rbp-120h] BYREF
  void **v16; // [rsp+40h] [rbp-118h]
  __int64 v17; // [rsp+48h] [rbp-110h] BYREF
  HANDLE Handles[2]; // [rsp+50h] [rbp-108h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+60h] [rbp-F8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-E8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+E0h] [rbp-78h] BYREF
  char *v22; // [rsp+F0h] [rbp-68h]
  int v23; // [rsp+F8h] [rbp-60h]
  int v24; // [rsp+FCh] [rbp-5Ch]
  const char *v25; // [rsp+100h] [rbp-58h]
  __int64 v26; // [rsp+108h] [rbp-50h]
  int *v27; // [rsp+110h] [rbp-48h]
  __int64 v28; // [rsp+118h] [rbp-40h]
  __int64 *v29; // [rsp+120h] [rbp-38h]
  __int64 v30; // [rsp+128h] [rbp-30h]

  v16 = ContextHandle;
  Reply = 0;
  memset(&pAsync, 0, sizeof(pAsync));
  v2 = 0;
  v3 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v5 = L"RPC AsyncInitializeHandle failed, hr = %#x";
    v6 = 1171;
  }
  else
  {
    pAsync.UserInfo = 0;
    pAsync.NotificationType = RpcNotificationTypeEvent;
    EventW = (RPCNOTIFICATION_ROUTINE *)CreateEventW(0, 0, 0, 0);
    pAsync.u.APC.NotificationRoutine = EventW;
    if ( EventW )
    {
      Handles[0] = EventW;
      Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvcnotify_ProxyInfo, 1u, 0, &pAsync, ContextHandle);
      v8 = WaitForMultipleObjectsEx(1u, Handles, 0, 0x927C0u, 0);
      do
      {
        if ( v3 || v8 != 258 && v8 != 1 )
          break;
        RpcAsyncCancelCall(&pAsync, 1);
        if ( v8 == 258 )
          v2 = 1;
        else
          v3 = 1;
        v8 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
      }
      while ( !v2 );
      if ( v8 )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v5 = L"Encountered error while waiting on RPC call, hr = %#x";
      }
      else
      {
        LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
        if ( !LastError )
          goto LABEL_27;
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v5 = L"RPC Async complete call failed, hr = %#x";
      }
      v6 = 1173;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v5 = L"RPC failed to create new event, hr = %#x";
      v6 = 1171;
    }
  }
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(2u, "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp", v6, v5, *(_QWORD *)bAlertable);
LABEL_27:
  NotificationRoutine = pAsync.u.APC.NotificationRoutine;
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v2 )
  {
    Reply = -2147023436;
    v10 = *(_QWORD *)(wil::details::static_lazy<MSAClientTraceTelemetry>::get(
                        NotificationRoutine,
                        _lambda_f3ddbd0a50d11f24ac1f58eb5524dee0_::_lambda_invoker_cdecl_)
                    + 8);
    if ( *(_DWORD *)v10 > 5u
      && (*(_QWORD *)(v10 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v10 + 24) & 0x400000000000LL) == *(_QWORD *)(v10 + 24) )
    {
      v17 = 50331648;
      v15 = 600000;
      v29 = &v17;
      v30 = 8;
      v27 = &v15;
      v28 = 4;
      v25 = "WLIDCNDeleteContext";
      v26 = 20;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 5;
      EventDescriptor.Keyword = 0x400000000000LL;
      UserData.Ptr = *(_QWORD *)(v10 + 8);
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      UserData.Reserved = 2;
      v22 = byte_180077265;
      v23 = 68;
      v24 = 1;
      LODWORD(v16) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(*(_QWORD *)(v10 + 32), &EventDescriptor, 0, 0, 5u, &UserData);
    }
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x495u,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v3 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x495u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  v11 = Reply;
  if ( Reply == -2147023179 || Reply == -2147023174 )
  {
    TraceServiceStatus();
    v11 = Reply;
  }
  if ( v11 < 0 )
  {
    RpcSsDestroyClientContext(ContextHandle);
    *ContextHandle = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180014db0  mov     [rsp+arg_8], rbx
0x180014db5  mov     [rsp+arg_10], rsi
0x180014dba  push    rdi
0x180014dbb  push    r14
0x180014dbd  push    r15
0x180014dbf  sub     rsp, 140h
0x180014dc6  mov     rax, cs:__security_cookie
0x180014dcd  xor     rax, rsp
0x180014dd0  mov     [rsp+158h+var_28], rax
0x180014dd8  mov     r15, rcx
0x180014ddb  mov     [rsp+158h+var_118], rcx
0x180014de0  xor     r14d, r14d
0x180014de3  mov     [rsp+158h+Reply], r14d
0x180014de8  xorps   xmm0, xmm0
0x180014deb  movups  xmmword ptr [rsp+158h+pAsync.Size], xmm0
0x180014df0  movups  xmmword ptr [rsp+158h+pAsync.StubInfo], xmm0
0x180014df8  movups  xmmword ptr [rsp+158h+pAsync.RuntimeInfo], xmm0
0x180014e00  movups  xmmword ptr [rsp+158h+pAsync.u], xmm0
0x180014e08  movups  xmmword ptr [rsp+158h+pAsync.u+10h], xmm0
0x180014e10  movups  xmmword ptr [rsp+158h+pAsync.Reserved], xmm0
0x180014e18  movups  xmmword ptr [rsp+158h+pAsync.Reserved+10h], xmm0
0x180014e20  xor     sil, sil
0x180014e23  xor     dil, dil
0x180014e26  movups  xmmword ptr [rsp+158h+Handles], xmm0
0x180014e2b  mov     edx, 70h ; 'p'; Size
0x180014e30  lea     rcx, [rsp+158h+pAsync]; pAsync
0x180014e35  call    cs:__imp_RpcAsyncInitializeHandle
0x180014e3b  test    eax, eax
0x180014e3d  jz      short loc_180014E5B
0x180014e3f  jle     short loc_180014E49
0x180014e41  movzx   eax, ax
0x180014e44  or      eax, 80070000h
0x180014e49  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180014e50  mov     r8d, 493h
0x180014e56  jmp     loc_180015003
0x180014e5b  mov     [rsp+158h+pAsync.UserInfo], r14
0x180014e63  mov     [rsp+158h+pAsync.NotificationType], 1
0x180014e6e  xor     r9d, r9d; lpName
0x180014e71  xor     r8d, r8d; bInitialState
0x180014e74  xor     edx, edx; bManualReset
0x180014e76  xor     ecx, ecx; lpEventAttributes
0x180014e78  call    cs:__imp_CreateEventW
0x180014e7e  mov     qword ptr [rsp+158h+pAsync.u], rax
0x180014e86  test    rax, rax
0x180014e89  jnz     short loc_180014EAF
0x180014e8b  call    cs:__imp_GetLastError
0x180014e91  test    eax, eax
0x180014e93  jle     short loc_180014E9D
0x180014e95  movzx   eax, ax
0x180014e98  or      eax, 80070000h
0x180014e9d  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180014ea4  mov     r8d, 493h
0x180014eaa  jmp     loc_180015003
0x180014eaf  mov     [rsp+158h+Handles], rax
0x180014eb4  mov     qword ptr [rsp+158h+bAlertable], r15
0x180014eb9  lea     r9, [rsp+158h+pAsync]
0x180014ebe  xor     r8d, r8d; pReturnValue
0x180014ec1  mov     edx, 1; nProcNum
0x180014ec6  lea     rcx, ?liveidsvcnotify_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180014ecd  call    cs:__imp_Ndr64AsyncClientCall
0x180014ed3  mov     eax, [rsp+158h+Reply]
0x180014ed7  jmp     short loc_180014F2C
0x180014ed9  test    eax, eax
0x180014edb  jle     short loc_180014EE5
0x180014edd  movzx   eax, ax
0x180014ee0  or      eax, 80070000h
0x180014ee5  mov     [rsp+158h+Reply], eax
0x180014ee9  mov     [rsp+158h+bAlertable], eax
0x180014eed  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180014ef4  mov     r8d, 495h; unsigned int
0x180014efa  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180014f01  mov     ecx, 2; unsigned __int8
0x180014f06  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180014f0b  mov     eax, [rsp+158h+Reply]
0x180014f0f  test    eax, eax
0x180014f11  js      short loc_180014F1C
0x180014f13  mov     eax, 8000FFFFh
0x180014f18  mov     [rsp+158h+Reply], eax
0x180014f1c  xor     r14d, r14d
0x180014f1f  movzx   esi, r14b
0x180014f23  movzx   edi, r14b
0x180014f27  mov     r15, [rsp+158h+var_118]
0x180014f2c  test    eax, eax
0x180014f2e  jns     short loc_180014F42
0x180014f30  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180014f37  mov     r8d, 495h
0x180014f3d  jmp     loc_180015007
0x180014f42  mov     [rsp+158h+bAlertable], r14d; bAlertable
0x180014f47  mov     r9d, 927C0h; dwMilliseconds
0x180014f4d  xor     r8d, r8d; bWaitAll
0x180014f50  lea     rdx, [rsp+158h+Handles]; lpHandles
0x180014f55  mov     ecx, 1; nCount
0x180014f5a  call    cs:__imp_WaitForMultipleObjectsEx
0x180014f60  mov     ebx, eax
0x180014f62  test    dil, dil
0x180014f65  jnz     short loc_180014FB9
0x180014f67  cmp     ebx, 102h
0x180014f6d  jz      short loc_180014F74
0x180014f6f  cmp     ebx, 1
0x180014f72  jnz     short loc_180014FB9
0x180014f74  mov     edx, 1; fAbort
0x180014f79  lea     rcx, [rsp+158h+pAsync]; pAsync
0x180014f7e  call    cs:__imp_RpcAsyncCancelCall
0x180014f84  cmp     ebx, 102h
0x180014f8a  jnz     short loc_180014F91
0x180014f8c  mov     sil, 1
0x180014f8f  jmp     short loc_180014F94
0x180014f91  mov     dil, 1
0x180014f94  mov     [rsp+158h+bAlertable], r14d; bAlertable
0x180014f99  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x180014f9f  xor     r8d, r8d; bWaitAll
0x180014fa2  lea     rdx, [rsp+158h+Handles]; lpHandles
0x180014fa7  mov     ecx, 1; nCount
0x180014fac  call    cs:__imp_WaitForMultipleObjectsEx
0x180014fb2  mov     ebx, eax
0x180014fb4  test    sil, sil
0x180014fb7  jz      short loc_180014F62
0x180014fb9  test    ebx, ebx
0x180014fbb  jz      short loc_180014FD8
0x180014fbd  call    cs:__imp_GetLastError
0x180014fc3  test    eax, eax
0x180014fc5  jle     short loc_180014FCF
0x180014fc7  movzx   eax, ax
0x180014fca  or      eax, 80070000h
0x180014fcf  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180014fd6  jmp     short loc_180014FFD
0x180014fd8  lea     rdx, [rsp+158h+Reply]; Reply
0x180014fdd  lea     rcx, [rsp+158h+pAsync]; pAsync
0x180014fe2  call    cs:__imp_RpcAsyncCompleteCall
0x180014fe8  test    eax, eax
0x180014fea  jz      short loc_18001501C
0x180014fec  jle     short loc_180014FF6
0x180014fee  movzx   eax, ax
0x180014ff1  or      eax, 80070000h
0x180014ff6  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180014ffd  mov     r8d, 495h; unsigned int
0x180015003  mov     [rsp+158h+Reply], eax
0x180015007  mov     [rsp+158h+bAlertable], eax
0x18001500b  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180015012  mov     ecx, 2; unsigned __int8
0x180015017  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001501c  mov     rcx, qword ptr [rsp+158h+pAsync.u]; hObject
0x180015024  test    rcx, rcx
0x180015027  jz      short loc_18001502F
0x180015029  call    cs:__imp_CloseHandle
0x18001502f  test    sil, sil
0x180015032  jz      loc_1800151A9
0x180015038  mov     [rsp+158h+Reply], 800705B4h
0x180015040  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f3ddbd0a50d11f24ac1f58eb5524dee0_@@CA@XZ; _lambda_f3ddbd0a50d11f24ac1f58eb5524dee0_::_lambda_invoker_cdecl_(void)
0x180015047  call    ?get@?$static_lazy@VMSAClientTraceTelemetry@@@details@wil@@QEAAPEAVMSAClientTraceTelemetry@@P6AXXZ@Z; wil::details::static_lazy<MSAClientTraceTelemetry>::get(void (*)(void))
0x18001504c  mov     rcx, [rax+8]
0x180015050  mov     eax, [rcx]
0x180015052  cmp     eax, 5
0x180015055  jbe     loc_180015183
0x18001505b  mov     rdx, [rcx+18h]
0x18001505f  mov     rax, [rcx+10h]
0x180015063  mov     r8, 400000000000h
0x18001506d  test    r8, rax
0x180015070  jz      loc_180015183
0x180015076  mov     rax, rdx
0x180015079  and     rax, r8
0x18001507c  cmp     rax, rdx
0x18001507f  jnz     loc_180015183
0x180015085  mov     [rsp+158h+var_110], 3000000h
0x18001508e  mov     [rsp+158h+var_120], 927C0h
0x180015096  lea     rax, [rsp+158h+var_110]
0x18001509b  mov     [rsp+158h+var_38], rax
0x1800150a3  mov     [rsp+158h+var_30], 8
0x1800150af  lea     rax, [rsp+158h+var_120]
0x1800150b4  mov     [rsp+158h+var_48], rax
0x1800150bc  mov     [rsp+158h+var_40], 4
0x1800150c8  lea     rax, aWlidcndeleteco; "WLIDCNDeleteContext"
0x1800150cf  mov     [rsp+158h+var_58], rax
0x1800150d7  mov     [rsp+158h+var_50], 14h
0x1800150e3  mov     dword ptr [rsp+158h+EventDescriptor.Id], 0B000000h
0x1800150eb  movzx   eax, cs:word_18007725B
0x1800150f2  mov     dword ptr [rsp+158h+EventDescriptor.Level], eax
0x1800150f6  mov     [rsp+158h+EventDescriptor.Keyword], r8
0x1800150fb  mov     rax, [rcx+8]
0x1800150ff  mov     [rsp+158h+var_78.Ptr], rax
0x180015107  movzx   eax, word ptr [rax]
0x18001510a  mov     [rsp+158h+var_78.Size], eax
0x180015111  mov     dword ptr [rsp+158h+var_78.0Ch], 2
0x18001511c  lea     rax, byte_180077265
0x180015123  mov     [rsp+158h+var_68], rax
0x18001512b  mov     [rsp+158h+var_60], 44h ; 'D'
0x180015136  mov     [rsp+158h+var_5C], 1
0x180015141  lea     rax, _TraceLoggingMetadataEnd
0x180015148  lea     rdx, _TraceLoggingMetadata
0x18001514f  sub     eax, edx
0x180015151  mov     dword ptr [rsp+158h+var_118], eax
0x180015155  mov     eax, dword ptr [rsp+158h+var_118]
0x180015159  lea     rax, [rsp+158h+var_78]
0x180015161  mov     [rsp+158h+UserData], rax; UserData
0x180015166  mov     [rsp+158h+bAlertable], 5; UserDataCount
0x18001516e  xor     r9d, r9d; RelatedActivityId
0x180015171  xor     r8d, r8d; ActivityId
0x180015174  lea     rdx, [rsp+158h+EventDescriptor]; EventDescriptor
0x180015179  mov     rcx, [rcx+20h]; RegHandle
0x18001517d  call    cs:__imp_EventWriteTransfer
0x180015183  mov     eax, [rsp+158h+Reply]
0x180015187  mov     [rsp+158h+bAlertable], eax
0x18001518b  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180015192  mov     r8d, 495h; unsigned int
0x180015198  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001519f  mov     ecx, 2; unsigned __int8
0x1800151a4  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800151a9  test    dil, dil
0x1800151ac  jz      short loc_1800151DC
0x1800151ae  mov     [rsp+158h+Reply], 800704C7h
0x1800151b6  mov     [rsp+158h+bAlertable], 800704C7h
0x1800151be  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x1800151c5  mov     r8d, 495h; unsigned int
0x1800151cb  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800151d2  mov     ecx, 2; unsigned __int8
0x1800151d7  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800151dc  mov     eax, [rsp+158h+Reply]
0x1800151e0  cmp     eax, 800706B5h
0x1800151e5  jz      short loc_1800151EE
0x1800151e7  cmp     eax, 800706BAh
0x1800151ec  jnz     short loc_1800151F7
0x1800151ee  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x1800151f3  mov     eax, [rsp+158h+Reply]
0x1800151f7  test    eax, eax
0x1800151f9  jns     short loc_180015207
0x1800151fb  mov     rcx, r15; ContextHandle
0x1800151fe  call    cs:__imp_RpcSsDestroyClientContext
0x180015204  mov     [r15], r14
0x180015207  xor     eax, eax
0x180015209  mov     rcx, [rsp+158h+var_28]
0x180015211  xor     rcx, rsp; StackCookie
0x180015214  call    __security_check_cookie
0x180015219  lea     r11, [rsp+158h+var_18]
0x180015221  mov     rbx, [r11+28h]
0x180015225  mov     rsi, [r11+30h]
0x180015229  mov     rsp, r11
0x18001522c  pop     r15
0x18001522e  pop     r14
0x180015230  pop     rdi
0x180015231  retn
0x180057670  push    rbp
0x180057672  sub     rsp, 30h
0x180057676  mov     rbp, rdx
0x180057679  mov     rcx, [rcx]
0x18005767c  mov     ecx, [rcx]; unsigned int
0x18005767e  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x180057683  nop
0x180057684  add     rsp, 30h
0x180057688  pop     rbp
0x180057689  retn
```
