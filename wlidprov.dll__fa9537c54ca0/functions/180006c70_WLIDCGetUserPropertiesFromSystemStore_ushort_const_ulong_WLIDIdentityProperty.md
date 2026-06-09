# WLIDCGetUserPropertiesFromSystemStore(ushort const *,ulong *,_WLIDIdentityProperty * *)

- ea: `0x180006c70`
- end: `0x180007166`
- name: `?WLIDCGetUserPropertiesFromSystemStore@@YAJPEBGPEAKPEAPEAU_WLIDIdentityProperty@@@Z`
- size: `1270`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *, struct _WLIDIdentityProperty **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180007170`
- `0x180041850`

## callees

- `0x180006c70`
- `0x18000a400`
- `0x18000f870`
- `0x180010cc4`
- `0x180015be0`
- `0x18001a0d0`
- `0x180043240`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006d93`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006d93`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180006e89`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180006ede`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180006e89`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180006ede`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006da6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006eef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006da6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006eef`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800070b2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800070b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f5e`
- `RPCRT4!RpcBindingFree` at `0x180007139`
- `RPCRT4!RpcBindingFree` at `0x180007139`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180006d50`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180006d50`
- `RPCRT4!RpcAsyncCancelCall` at `0x180006eb0`
- `RPCRT4!RpcAsyncCancelCall` at `0x180006eb0`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180006dff`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180006dff`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180006f17`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180006f17`

## string_xrefs

- `0x180006db8`: `RPC failed to create new event, hr = %#x`
- `0x180006f2b`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCGetUserPropertiesFromSystemStore(
        const unsigned __int16 *a1,
        unsigned int *a2,
        struct _WLIDIdentityProperty **a3)
{
  DWORD v6; // r14d
  __int64 result; // rax
  char v8; // si
  char v9; // di
  int LastError; // eax
  const unsigned __int16 *v11; // r9
  unsigned int v12; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v14; // ebx
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  __int64 v16; // rcx
  BOOL bAlertable[2]; // [rsp+20h] [rbp-178h]
  unsigned int Reply; // [rsp+40h] [rbp-158h] BYREF
  unsigned int v19[3]; // [rsp+44h] [rbp-154h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+50h] [rbp-148h] BYREF
  unsigned int v21; // [rsp+58h] [rbp-140h]
  __int64 v22; // [rsp+60h] [rbp-138h] BYREF
  HANDLE Handles[2]; // [rsp+68h] [rbp-130h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+78h] [rbp-120h] BYREF
  _RPC_ASYNC_STATE pAsync; // [rsp+90h] [rbp-108h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+100h] [rbp-98h] BYREF
  char *v27; // [rsp+110h] [rbp-88h]
  int v28; // [rsp+118h] [rbp-80h]
  int v29; // [rsp+11Ch] [rbp-7Ch]
  const char *v30; // [rsp+120h] [rbp-78h]
  __int64 v31; // [rsp+128h] [rbp-70h]
  unsigned int *v32; // [rsp+130h] [rbp-68h]
  __int64 v33; // [rsp+138h] [rbp-60h]
  __int64 *v34; // [rsp+140h] [rbp-58h]
  __int64 v35; // [rsp+148h] [rbp-50h]

  v19[0] = 0;
  v6 = g_dwLongTimeOut;
  if ( !g_dwLongTimeOut )
  {
    if ( (int)WLIDCpGetConfigDWORDValue((unsigned int)a1, v19) >= 0 )
    {
      v6 = 1000 * v19[0];
      g_dwLongTimeOut = 1000 * v19[0];
    }
    else
    {
      v6 = 600000;
    }
  }
  v19[0] = v6;
  Binding = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&Binding);
  Reply = result;
  if ( (int)result >= 0 )
  {
    memset(&pAsync, 0, sizeof(pAsync));
    v8 = 0;
    v9 = 0;
    *(_OWORD *)Handles = 0;
    LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v11 = L"RPC AsyncInitializeHandle failed, hr = %#x";
      v12 = 1102;
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
        Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x37u, 0, &pAsync, Binding, a1, a2, a3);
        LastError = Reply;
        if ( (Reply & 0x80000000) != 0 )
        {
          v11 = L"RPC call failed, hr = %#x";
          v12 = 1104;
LABEL_34:
          bAlertable[0] = LastError;
          TracePrintW(
            2u,
            "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
            v12,
            v11,
            *(_QWORD *)bAlertable);
          goto LABEL_35;
        }
        v14 = WaitForMultipleObjectsEx(1u, Handles, 0, v6, 0);
        do
        {
          if ( v9 || v14 != 258 && v14 != 1 )
            break;
          RpcAsyncCancelCall(&pAsync, 1);
          if ( v14 == 258 )
            v8 = 1;
          else
            v9 = 1;
          v14 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
        }
        while ( !v8 );
        if ( v14 )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v11 = L"Encountered error while waiting on RPC call, hr = %#x";
        }
        else
        {
          LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
          if ( !LastError )
          {
LABEL_35:
            NotificationRoutine = pAsync.u.APC.NotificationRoutine;
            if ( pAsync.u.APC.NotificationRoutine )
              CloseHandle(pAsync.u.APC.NotificationRoutine);
            if ( v8 )
            {
              Reply = -2147023436;
              v16 = *(_QWORD *)(wil::details::static_lazy<MSAClientTraceTelemetry>::get(
                                  NotificationRoutine,
                                  _lambda_f3ddbd0a50d11f24ac1f58eb5524dee0_::_lambda_invoker_cdecl_)
                              + 8);
              if ( *(_DWORD *)v16 > 5u
                && (*(_QWORD *)(v16 + 16) & 0x400000000000LL) != 0
                && (*(_QWORD *)(v16 + 24) & 0x400000000000LL) == *(_QWORD *)(v16 + 24) )
              {
                v22 = 50331648;
                v19[0] = v6;
                v34 = &v22;
                v35 = 8;
                v32 = v19;
                v33 = 4;
                v30 = "WLIDCGetUserPropertiesFromSystemStore";
                v31 = 38;
                *(_DWORD *)&EventDescriptor.Id = 184549376;
                *(_DWORD *)&EventDescriptor.Level = 5;
                EventDescriptor.Keyword = 0x400000000000LL;
                UserData.Ptr = *(_QWORD *)(v16 + 8);
                UserData.Size = *(unsigned __int16 *)UserData.Ptr;
                UserData.Reserved = 2;
                v27 = byte_1800776F3;
                v28 = 68;
                v29 = 1;
                v21 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
                EventWriteTransfer(*(_QWORD *)(v16 + 32), &EventDescriptor, 0, 0, 5u, &UserData);
              }
              bAlertable[0] = Reply;
              TracePrintW(
                2u,
                "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
                0x450u,
                L"RPC call timed out, hr = %#x",
                *(_QWORD *)bAlertable);
            }
            if ( v9 )
            {
              Reply = -2147023673;
              bAlertable[0] = -2147023673;
              TracePrintW(
                2u,
                "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
                0x450u,
                L"RPC call was cancelled, hr = %#x",
                *(_QWORD *)bAlertable);
            }
            result = Reply;
            if ( Reply == -2147023179 || Reply == -2147023174 )
            {
              TraceServiceStatus();
              result = Reply;
            }
            if ( Binding )
            {
              RpcBindingFree(&Binding);
              return Reply;
            }
            return result;
          }
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v11 = L"RPC Async complete call failed, hr = %#x";
        }
        v12 = 1104;
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v11 = L"RPC failed to create new event, hr = %#x";
        v12 = 1102;
      }
    }
    Reply = LastError;
    goto LABEL_34;
  }
  return result;
}

```

## disassembly

```asm
0x180006c70  push    rbx
0x180006c72  push    rsi
0x180006c73  push    rdi
0x180006c74  push    r12
0x180006c76  push    r13
0x180006c78  push    r14
0x180006c7a  push    r15
0x180006c7c  sub     rsp, 160h
0x180006c83  mov     rax, cs:__security_cookie
0x180006c8a  xor     rax, rsp
0x180006c8d  mov     [rsp+198h+var_48], rax
0x180006c95  mov     r13, r8
0x180006c98  mov     r12, rdx
0x180006c9b  mov     rbx, rcx
0x180006c9e  xor     r15d, r15d
0x180006ca1  mov     [rsp+198h+var_154], r15d
0x180006ca6  mov     r14d, cs:?g_dwLongTimeOut@@3KA; ulong g_dwLongTimeOut
0x180006cad  test    r14d, r14d
0x180006cb0  jnz     short loc_180006CD8
0x180006cb2  lea     rdx, [rsp+198h+var_154]; unsigned int *
0x180006cb7  call    ?WLIDCpGetConfigDWORDValue@@YAJKPEAK@Z; WLIDCpGetConfigDWORDValue(ulong,ulong *)
0x180006cbc  test    eax, eax
0x180006cbe  jns     short loc_180006CC8
0x180006cc0  mov     r14d, 927C0h
0x180006cc6  jmp     short loc_180006CD8
0x180006cc8  imul    r14d, [rsp+198h+var_154], 3E8h
0x180006cd1  mov     cs:?g_dwLongTimeOut@@3KA, r14d; ulong g_dwLongTimeOut
0x180006cd8  mov     [rsp+198h+var_154], r14d
0x180006cdd  mov     [rsp+198h+Reply], r15d
0x180006ce2  mov     [rsp+198h+Binding], r15
0x180006ce7  lea     rcx, [rsp+198h+Binding]; this
0x180006cec  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x180006cf1  mov     [rsp+198h+Reply], eax
0x180006cf5  test    eax, eax
0x180006cf7  js      loc_180007143
0x180006cfd  xorps   xmm0, xmm0
0x180006d00  movups  xmmword ptr [rsp+198h+pAsync.Size], xmm0
0x180006d08  movups  xmmword ptr [rsp+198h+pAsync.StubInfo], xmm0
0x180006d10  movups  xmmword ptr [rsp+198h+pAsync.RuntimeInfo], xmm0
0x180006d18  movups  xmmword ptr [rsp+198h+pAsync.u], xmm0
0x180006d20  movups  xmmword ptr [rsp+198h+pAsync.u+10h], xmm0
0x180006d28  movups  xmmword ptr [rsp+198h+pAsync.Reserved], xmm0
0x180006d30  movups  xmmword ptr [rsp+198h+pAsync.Reserved+10h], xmm0
0x180006d38  xor     sil, sil
0x180006d3b  xor     dil, dil
0x180006d3e  movups  xmmword ptr [rsp+198h+Handles], xmm0
0x180006d43  mov     edx, 70h ; 'p'; Size
0x180006d48  lea     rcx, [rsp+198h+pAsync]; pAsync
0x180006d50  call    cs:__imp_RpcAsyncInitializeHandle
0x180006d56  test    eax, eax
0x180006d58  jz      short loc_180006D76
0x180006d5a  jle     short loc_180006D64
0x180006d5c  movzx   eax, ax
0x180006d5f  or      eax, 80070000h
0x180006d64  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180006d6b  mov     r8d, 44Eh
0x180006d71  jmp     loc_180006F38
0x180006d76  mov     [rsp+198h+pAsync.UserInfo], r15
0x180006d7e  mov     [rsp+198h+pAsync.NotificationType], 1
0x180006d89  xor     r9d, r9d; lpName
0x180006d8c  xor     r8d, r8d; bInitialState
0x180006d8f  xor     edx, edx; bManualReset
0x180006d91  xor     ecx, ecx; lpEventAttributes
0x180006d93  call    cs:__imp_CreateEventW
0x180006d99  mov     qword ptr [rsp+198h+pAsync.u], rax
0x180006da1  test    rax, rax
0x180006da4  jnz     short loc_180006DCA
0x180006da6  call    cs:__imp_GetLastError
0x180006dac  test    eax, eax
0x180006dae  jle     short loc_180006DB8
0x180006db0  movzx   eax, ax
0x180006db3  or      eax, 80070000h
0x180006db8  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180006dbf  mov     r8d, 44Eh
0x180006dc5  jmp     loc_180006F38
0x180006dca  mov     [rsp+198h+Handles], rax
0x180006dcf  mov     [rsp+198h+var_160], r13
0x180006dd4  mov     [rsp+198h+var_168], r12
0x180006dd9  mov     [rsp+198h+UserData], rbx
0x180006dde  mov     rax, [rsp+198h+Binding]
0x180006de3  mov     qword ptr [rsp+198h+bAlertable], rax
0x180006de8  lea     r9, [rsp+198h+pAsync]
0x180006df0  xor     r8d, r8d; pReturnValue
0x180006df3  mov     edx, 37h ; '7'; nProcNum
0x180006df8  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180006dff  call    cs:__imp_Ndr64AsyncClientCall
0x180006e05  mov     eax, [rsp+198h+Reply]
0x180006e09  jmp     short loc_180006E5E
0x180006e0b  test    eax, eax
0x180006e0d  jle     short loc_180006E17
0x180006e0f  movzx   eax, ax
0x180006e12  or      eax, 80070000h
0x180006e17  mov     [rsp+198h+Reply], eax
0x180006e1b  mov     [rsp+198h+bAlertable], eax
0x180006e1f  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180006e26  mov     r8d, 450h; unsigned int
0x180006e2c  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180006e33  mov     ecx, 2; unsigned __int8
0x180006e38  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180006e3d  mov     eax, [rsp+198h+Reply]
0x180006e41  test    eax, eax
0x180006e43  js      short loc_180006E4E
0x180006e45  mov     eax, 8000FFFFh
0x180006e4a  mov     [rsp+198h+Reply], eax
0x180006e4e  xor     r15d, r15d
0x180006e51  mov     r14d, [rsp+198h+var_154]
0x180006e56  movzx   esi, r15b
0x180006e5a  movzx   edi, r15b
0x180006e5e  test    eax, eax
0x180006e60  jns     short loc_180006E74
0x180006e62  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180006e69  mov     r8d, 450h
0x180006e6f  jmp     loc_180006F3C
0x180006e74  mov     [rsp+198h+bAlertable], r15d; bAlertable
0x180006e79  mov     r9d, r14d; dwMilliseconds
0x180006e7c  xor     r8d, r8d; bWaitAll
0x180006e7f  lea     rdx, [rsp+198h+Handles]; lpHandles
0x180006e84  mov     ecx, 1; nCount
0x180006e89  call    cs:__imp_WaitForMultipleObjectsEx
0x180006e8f  mov     ebx, eax
0x180006e91  test    dil, dil
0x180006e94  jnz     short loc_180006EEB
0x180006e96  cmp     ebx, 102h
0x180006e9c  jz      short loc_180006EA3
0x180006e9e  cmp     ebx, 1
0x180006ea1  jnz     short loc_180006EEB
0x180006ea3  mov     edx, 1; fAbort
0x180006ea8  lea     rcx, [rsp+198h+pAsync]; pAsync
0x180006eb0  call    cs:__imp_RpcAsyncCancelCall
0x180006eb6  cmp     ebx, 102h
0x180006ebc  jnz     short loc_180006EC3
0x180006ebe  mov     sil, 1
0x180006ec1  jmp     short loc_180006EC6
0x180006ec3  mov     dil, 1
0x180006ec6  mov     [rsp+198h+bAlertable], r15d; bAlertable
0x180006ecb  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x180006ed1  xor     r8d, r8d; bWaitAll
0x180006ed4  lea     rdx, [rsp+198h+Handles]; lpHandles
0x180006ed9  mov     ecx, 1; nCount
0x180006ede  call    cs:__imp_WaitForMultipleObjectsEx
0x180006ee4  mov     ebx, eax
0x180006ee6  test    sil, sil
0x180006ee9  jz      short loc_180006E91
0x180006eeb  test    ebx, ebx
0x180006eed  jz      short loc_180006F0A
0x180006eef  call    cs:__imp_GetLastError
0x180006ef5  test    eax, eax
0x180006ef7  jle     short loc_180006F01
0x180006ef9  movzx   eax, ax
0x180006efc  or      eax, 80070000h
0x180006f01  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180006f08  jmp     short loc_180006F32
0x180006f0a  lea     rdx, [rsp+198h+Reply]; Reply
0x180006f0f  lea     rcx, [rsp+198h+pAsync]; pAsync
0x180006f17  call    cs:__imp_RpcAsyncCompleteCall
0x180006f1d  test    eax, eax
0x180006f1f  jz      short loc_180006F51
0x180006f21  jle     short loc_180006F2B
0x180006f23  movzx   eax, ax
0x180006f26  or      eax, 80070000h
0x180006f2b  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180006f32  mov     r8d, 450h; unsigned int
0x180006f38  mov     [rsp+198h+Reply], eax
0x180006f3c  mov     [rsp+198h+bAlertable], eax
0x180006f40  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180006f47  mov     ecx, 2; unsigned __int8
0x180006f4c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180006f51  mov     rcx, qword ptr [rsp+198h+pAsync.u]; hObject
0x180006f59  test    rcx, rcx
0x180006f5c  jz      short loc_180006F64
0x180006f5e  call    cs:__imp_CloseHandle
0x180006f64  test    sil, sil
0x180006f67  jz      loc_1800070DE
0x180006f6d  mov     [rsp+198h+Reply], 800705B4h
0x180006f75  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f3ddbd0a50d11f24ac1f58eb5524dee0_@@CA@XZ; _lambda_f3ddbd0a50d11f24ac1f58eb5524dee0_::_lambda_invoker_cdecl_(void)
0x180006f7c  call    ?get@?$static_lazy@VMSAClientTraceTelemetry@@@details@wil@@QEAAPEAVMSAClientTraceTelemetry@@P6AXXZ@Z; wil::details::static_lazy<MSAClientTraceTelemetry>::get(void (*)(void))
0x180006f81  mov     rcx, [rax+8]
0x180006f85  mov     eax, [rcx]
0x180006f87  cmp     eax, 5
0x180006f8a  jbe     loc_1800070B8
0x180006f90  mov     rdx, [rcx+18h]
0x180006f94  mov     rax, [rcx+10h]
0x180006f98  mov     r8, 400000000000h
0x180006fa2  test    r8, rax
0x180006fa5  jz      loc_1800070B8
0x180006fab  mov     rax, rdx
0x180006fae  and     rax, r8
0x180006fb1  cmp     rax, rdx
0x180006fb4  jnz     loc_1800070B8
0x180006fba  mov     [rsp+198h+var_138], 3000000h
0x180006fc3  mov     [rsp+198h+var_154], r14d
0x180006fc8  lea     rax, [rsp+198h+var_138]
0x180006fcd  mov     [rsp+198h+var_58], rax
0x180006fd5  mov     [rsp+198h+var_50], 8
0x180006fe1  lea     rax, [rsp+198h+var_154]
0x180006fe6  mov     [rsp+198h+var_68], rax
0x180006fee  mov     [rsp+198h+var_60], 4
0x180006ffa  lea     rax, aWlidcgetuserpr_0; "WLIDCGetUserPropertiesFromSystemStore"
0x180007001  mov     [rsp+198h+var_78], rax
0x180007009  mov     [rsp+198h+var_70], 26h ; '&'
0x180007015  mov     dword ptr [rsp+198h+EventDescriptor.Id], 0B000000h
0x18000701d  movzx   eax, cs:word_1800776E9
0x180007024  mov     dword ptr [rsp+198h+EventDescriptor.Level], eax
0x180007028  mov     [rsp+198h+EventDescriptor.Keyword], r8
0x180007030  mov     rax, [rcx+8]
0x180007034  mov     [rsp+198h+var_98.Ptr], rax
0x18000703c  movzx   eax, word ptr [rax]
0x18000703f  mov     [rsp+198h+var_98.Size], eax
0x180007046  mov     dword ptr [rsp+198h+var_98.0Ch], 2
0x180007051  lea     rax, byte_1800776F3
0x180007058  mov     [rsp+198h+var_88], rax
0x180007060  mov     [rsp+198h+var_80], 44h ; 'D'
0x18000706b  mov     [rsp+198h+var_7C], 1
0x180007076  lea     rax, _TraceLoggingMetadataEnd
0x18000707d  lea     rdx, _TraceLoggingMetadata
0x180007084  sub     eax, edx
0x180007086  mov     [rsp+198h+var_140], eax
0x18000708a  mov     eax, [rsp+198h+var_140]
0x18000708e  lea     rax, [rsp+198h+var_98]
0x180007096  mov     [rsp+198h+UserData], rax; UserData
0x18000709b  mov     [rsp+198h+bAlertable], 5; UserDataCount
0x1800070a3  xor     r9d, r9d; RelatedActivityId
0x1800070a6  xor     r8d, r8d; ActivityId
0x1800070a9  lea     rdx, [rsp+198h+EventDescriptor]; EventDescriptor
0x1800070ae  mov     rcx, [rcx+20h]; RegHandle
0x1800070b2  call    cs:__imp_EventWriteTransfer
0x1800070b8  mov     eax, [rsp+198h+Reply]
0x1800070bc  mov     [rsp+198h+bAlertable], eax
0x1800070c0  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x1800070c7  mov     r8d, 450h; unsigned int
0x1800070cd  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800070d4  mov     ecx, 2; unsigned __int8
0x1800070d9  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800070de  test    dil, dil
0x1800070e1  jz      short loc_180007111
0x1800070e3  mov     [rsp+198h+Reply], 800704C7h
0x1800070eb  mov     [rsp+198h+bAlertable], 800704C7h
0x1800070f3  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x1800070fa  mov     r8d, 450h; unsigned int
0x180007100  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180007107  mov     ecx, 2; unsigned __int8
0x18000710c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180007111  mov     eax, [rsp+198h+Reply]
0x180007115  cmp     eax, 800706B5h
0x18000711a  jz      short loc_180007123
0x18000711c  cmp     eax, 800706BAh
0x180007121  jnz     short loc_18000712C
0x180007123  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180007128  mov     eax, [rsp+198h+Reply]
0x18000712c  cmp     [rsp+198h+Binding], 0
0x180007132  jz      short loc_180007143
0x180007134  lea     rcx, [rsp+198h+Binding]; Binding
0x180007139  call    cs:__imp_RpcBindingFree
0x18000713f  mov     eax, [rsp+198h+Reply]
0x180007143  mov     rcx, [rsp+198h+var_48]
0x18000714b  xor     rcx, rsp; StackCookie
0x18000714e  call    __security_check_cookie
0x180007153  add     rsp, 160h
0x18000715a  pop     r15
0x18000715c  pop     r14
0x18000715e  pop     r13
0x180007160  pop     r12
0x180007162  pop     rdi
0x180007163  pop     rsi
0x180007164  pop     rbx
0x180007165  retn
0x180053e40  push    rbp
0x180053e42  sub     rsp, 40h
0x180053e46  mov     rbp, rdx
0x180053e49  mov     rcx, [rcx]
0x180053e4c  mov     ecx, [rcx]; unsigned int
0x180053e4e  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x180053e53  nop
0x180053e54  add     rsp, 40h
0x180053e58  pop     rbp
0x180053e59  retn
```
