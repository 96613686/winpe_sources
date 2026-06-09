# WLIDCEnumIdentities(unsigned __int64,ushort const *,ushort const *,ulong *,ushort * * *)

- ea: `0x18000ceb0`
- end: `0x18000d3d5`
- name: `?WLIDCEnumIdentities@@YAJ_KPEBG1PEAKPEAPEAPEAG@Z`
- size: `1317`
- prototype: `__int64 __fastcall(unsigned __int64, const unsigned __int16 *, const unsigned __int16 *, unsigned int *, unsigned __int16 ***)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000c4f0`
- `0x18000ee10`
- `0x180041690`

## callees

- `0x18000a400`
- `0x18000ceb0`
- `0x18000f870`
- `0x180010cc4`
- `0x180015be0`
- `0x18001a0d0`
- `0x180043240`
- `0x18005246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000cfe5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000cfe5`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000d0ef`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000d144`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000d0ef`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000d144`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cff8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d155`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cff8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d155`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d321`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d321`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d1c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d1c4`
- `RPCRT4!RpcBindingFree` at `0x18000d3a8`
- `RPCRT4!RpcBindingFree` at `0x18000d3a8`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18000cfa2`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18000cfa2`
- `RPCRT4!RpcAsyncCancelCall` at `0x18000d116`
- `RPCRT4!RpcAsyncCancelCall` at `0x18000d116`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18000d065`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18000d065`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000d17d`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000d17d`

## string_xrefs

- `0x18000d00a`: `RPC failed to create new event, hr = %#x`
- `0x18000d191`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCEnumIdentities(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int *a4,
        unsigned __int16 ***a5)
{
  DWORD v8; // r14d
  __int64 result; // rax
  char v10; // si
  char v11; // di
  int LastError; // eax
  const unsigned __int16 *v13; // r9
  unsigned int v14; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v16; // ebx
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  __int64 v18; // rcx
  BOOL bAlertable[2]; // [rsp+20h] [rbp-188h]
  unsigned int Reply; // [rsp+50h] [rbp-158h] BYREF
  unsigned int v21[3]; // [rsp+54h] [rbp-154h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+60h] [rbp-148h] BYREF
  unsigned __int16 ***v23; // [rsp+68h] [rbp-140h]
  __int64 v24; // [rsp+70h] [rbp-138h] BYREF
  HANDLE Handles[2]; // [rsp+78h] [rbp-130h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+88h] [rbp-120h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+A0h] [rbp-108h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+110h] [rbp-98h] BYREF
  char *v29; // [rsp+120h] [rbp-88h]
  int v30; // [rsp+128h] [rbp-80h]
  int v31; // [rsp+12Ch] [rbp-7Ch]
  const char *v32; // [rsp+130h] [rbp-78h]
  __int64 v33; // [rsp+138h] [rbp-70h]
  unsigned int *v34; // [rsp+140h] [rbp-68h]
  __int64 v35; // [rsp+148h] [rbp-60h]
  __int64 *v36; // [rsp+150h] [rbp-58h]
  __int64 v37; // [rsp+158h] [rbp-50h]

  v24 = (__int64)a4;
  v23 = a5;
  v21[0] = 0;
  v8 = g_dwLongTimeOut;
  if ( !g_dwLongTimeOut )
  {
    if ( (int)WLIDCpGetConfigDWORDValue(a1, v21) >= 0 )
    {
      v8 = 1000 * v21[0];
      g_dwLongTimeOut = 1000 * v21[0];
    }
    else
    {
      v8 = 600000;
    }
  }
  v21[0] = v8;
  Binding = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&Binding);
  Reply = result;
  if ( (int)result >= 0 )
  {
    memset(&pAsync, 0, sizeof(pAsync));
    v10 = 0;
    v11 = 0;
    *(_OWORD *)Handles = 0;
    LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v13 = L"RPC AsyncInitializeHandle failed, hr = %#x";
      v14 = 812;
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
        Ndr64AsyncClientCall(
          (MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo,
          0x19u,
          0,
          &pAsync,
          Binding,
          a1,
          a2,
          a3,
          v24,
          v23);
        LastError = Reply;
        if ( (Reply & 0x80000000) != 0 )
        {
          v13 = L"RPC call failed, hr = %#x";
          v14 = 814;
LABEL_34:
          bAlertable[0] = LastError;
          TracePrintW(
            2u,
            "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
            v14,
            v13,
            *(_QWORD *)bAlertable);
          goto LABEL_35;
        }
        v16 = WaitForMultipleObjectsEx(1u, Handles, 0, v8, 0);
        do
        {
          if ( v11 || v16 != 258 && v16 != 1 )
            break;
          RpcAsyncCancelCall(&pAsync, 1);
          if ( v16 == 258 )
            v10 = 1;
          else
            v11 = 1;
          v16 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
        }
        while ( !v10 );
        if ( v16 )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v13 = L"Encountered error while waiting on RPC call, hr = %#x";
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
            if ( v10 )
            {
              Reply = -2147023436;
              v18 = *(_QWORD *)(wil::details::static_lazy<MSAClientTraceTelemetry>::get(
                                  NotificationRoutine,
                                  _lambda_f3ddbd0a50d11f24ac1f58eb5524dee0_::_lambda_invoker_cdecl_)
                              + 8);
              if ( *(_DWORD *)v18 > 5u
                && (*(_QWORD *)(v18 + 16) & 0x400000000000LL) != 0
                && (*(_QWORD *)(v18 + 24) & 0x400000000000LL) == *(_QWORD *)(v18 + 24) )
              {
                v24 = 50331648;
                v21[0] = v8;
                v36 = &v24;
                v37 = 8;
                v34 = v21;
                v35 = 4;
                v32 = "WLIDCEnumIdentities";
                v33 = 20;
                *(_DWORD *)&EventDescriptor.Id = 184549376;
                *(_DWORD *)&EventDescriptor.Level = 5;
                EventDescriptor.Keyword = 0x400000000000LL;
                UserData.Ptr = *(_QWORD *)(v18 + 8);
                UserData.Size = *(unsigned __int16 *)UserData.Ptr;
                UserData.Reserved = 2;
                v29 = byte_180077265;
                v30 = 68;
                v31 = 1;
                LODWORD(v23) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
                EventWriteTransfer(*(_QWORD *)(v18 + 32), &EventDescriptor, 0, 0, 5u, &UserData);
              }
              bAlertable[0] = Reply;
              TracePrintW(
                2u,
                "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
                0x32Eu,
                L"RPC call timed out, hr = %#x",
                *(_QWORD *)bAlertable);
            }
            if ( v11 )
            {
              Reply = -2147023673;
              bAlertable[0] = -2147023673;
              TracePrintW(
                2u,
                "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
                0x32Eu,
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
          v13 = L"RPC Async complete call failed, hr = %#x";
        }
        v14 = 814;
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v13 = L"RPC failed to create new event, hr = %#x";
        v14 = 812;
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
0x18000ceb0  push    rbx
0x18000ceb2  push    rsi
0x18000ceb3  push    rdi
0x18000ceb4  push    r12
0x18000ceb6  push    r13
0x18000ceb8  push    r14
0x18000ceba  push    r15
0x18000cebc  sub     rsp, 170h
0x18000cec3  mov     rax, cs:__security_cookie
0x18000ceca  xor     rax, rsp
0x18000cecd  mov     [rsp+1A8h+var_48], rax
0x18000ced5  mov     [rsp+1A8h+var_138], r9
0x18000ceda  mov     r13, r8
0x18000cedd  mov     r12, rdx
0x18000cee0  mov     rbx, rcx
0x18000cee3  mov     rax, [rsp+1A8h+arg_20]
0x18000ceeb  mov     [rsp+1A8h+var_140], rax
0x18000cef0  xor     r15d, r15d
0x18000cef3  mov     [rsp+1A8h+var_154], r15d
0x18000cef8  mov     r14d, cs:?g_dwLongTimeOut@@3KA; ulong g_dwLongTimeOut
0x18000ceff  test    r14d, r14d
0x18000cf02  jnz     short loc_18000CF2A
0x18000cf04  lea     rdx, [rsp+1A8h+var_154]; unsigned int *
0x18000cf09  call    ?WLIDCpGetConfigDWORDValue@@YAJKPEAK@Z; WLIDCpGetConfigDWORDValue(ulong,ulong *)
0x18000cf0e  test    eax, eax
0x18000cf10  jns     short loc_18000CF1A
0x18000cf12  mov     r14d, 927C0h
0x18000cf18  jmp     short loc_18000CF2A
0x18000cf1a  imul    r14d, [rsp+1A8h+var_154], 3E8h
0x18000cf23  mov     cs:?g_dwLongTimeOut@@3KA, r14d; ulong g_dwLongTimeOut
0x18000cf2a  mov     [rsp+1A8h+var_154], r14d
0x18000cf2f  mov     [rsp+1A8h+Reply], r15d
0x18000cf34  mov     [rsp+1A8h+Binding], r15
0x18000cf39  lea     rcx, [rsp+1A8h+Binding]; this
0x18000cf3e  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18000cf43  mov     [rsp+1A8h+Reply], eax
0x18000cf47  test    eax, eax
0x18000cf49  js      loc_18000D3B2
0x18000cf4f  xorps   xmm0, xmm0
0x18000cf52  movups  xmmword ptr [rsp+1A8h+pAsync.Size], xmm0
0x18000cf5a  movups  xmmword ptr [rsp+1A8h+pAsync.StubInfo], xmm0
0x18000cf62  movups  xmmword ptr [rsp+1A8h+pAsync.RuntimeInfo], xmm0
0x18000cf6a  movups  xmmword ptr [rsp+1A8h+pAsync.u], xmm0
0x18000cf72  movups  xmmword ptr [rsp+1A8h+pAsync.u+10h], xmm0
0x18000cf7a  movups  xmmword ptr [rsp+1A8h+pAsync.Reserved], xmm0
0x18000cf82  movups  xmmword ptr [rsp+1A8h+pAsync.Reserved+10h], xmm0
0x18000cf8a  xor     sil, sil
0x18000cf8d  xor     dil, dil
0x18000cf90  movups  xmmword ptr [rsp+1A8h+Handles], xmm0
0x18000cf95  mov     edx, 70h ; 'p'; Size
0x18000cf9a  lea     rcx, [rsp+1A8h+pAsync]; pAsync
0x18000cfa2  call    cs:__imp_RpcAsyncInitializeHandle
0x18000cfa8  test    eax, eax
0x18000cfaa  jz      short loc_18000CFC8
0x18000cfac  jle     short loc_18000CFB6
0x18000cfae  movzx   eax, ax
0x18000cfb1  or      eax, 80070000h
0x18000cfb6  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18000cfbd  mov     r8d, 32Ch
0x18000cfc3  jmp     loc_18000D19E
0x18000cfc8  mov     [rsp+1A8h+pAsync.UserInfo], r15
0x18000cfd0  mov     [rsp+1A8h+pAsync.NotificationType], 1
0x18000cfdb  xor     r9d, r9d; lpName
0x18000cfde  xor     r8d, r8d; bInitialState
0x18000cfe1  xor     edx, edx; bManualReset
0x18000cfe3  xor     ecx, ecx; lpEventAttributes
0x18000cfe5  call    cs:__imp_CreateEventW
0x18000cfeb  mov     qword ptr [rsp+1A8h+pAsync.u], rax
0x18000cff3  test    rax, rax
0x18000cff6  jnz     short loc_18000D01C
0x18000cff8  call    cs:__imp_GetLastError
0x18000cffe  test    eax, eax
0x18000d000  jle     short loc_18000D00A
0x18000d002  movzx   eax, ax
0x18000d005  or      eax, 80070000h
0x18000d00a  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18000d011  mov     r8d, 32Ch
0x18000d017  jmp     loc_18000D19E
0x18000d01c  mov     [rsp+1A8h+Handles], rax
0x18000d021  mov     rax, [rsp+1A8h+var_140]
0x18000d026  mov     [rsp+1A8h+var_160], rax
0x18000d02b  mov     rax, [rsp+1A8h+var_138]
0x18000d030  mov     [rsp+1A8h+var_168], rax
0x18000d035  mov     [rsp+1A8h+var_170], r13
0x18000d03a  mov     [rsp+1A8h+var_178], r12
0x18000d03f  mov     [rsp+1A8h+UserData], rbx
0x18000d044  mov     rax, [rsp+1A8h+Binding]
0x18000d049  mov     qword ptr [rsp+1A8h+bAlertable], rax
0x18000d04e  lea     r9, [rsp+1A8h+pAsync]
0x18000d056  xor     r8d, r8d; pReturnValue
0x18000d059  mov     edx, 19h; nProcNum
0x18000d05e  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000d065  call    cs:__imp_Ndr64AsyncClientCall
0x18000d06b  mov     eax, [rsp+1A8h+Reply]
0x18000d06f  jmp     short loc_18000D0C4
0x18000d071  test    eax, eax
0x18000d073  jle     short loc_18000D07D
0x18000d075  movzx   eax, ax
0x18000d078  or      eax, 80070000h
0x18000d07d  mov     [rsp+1A8h+Reply], eax
0x18000d081  mov     [rsp+1A8h+bAlertable], eax
0x18000d085  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18000d08c  mov     r8d, 32Eh; unsigned int
0x18000d092  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000d099  mov     ecx, 2; unsigned __int8
0x18000d09e  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000d0a3  mov     eax, [rsp+1A8h+Reply]
0x18000d0a7  test    eax, eax
0x18000d0a9  js      short loc_18000D0B4
0x18000d0ab  mov     eax, 8000FFFFh
0x18000d0b0  mov     [rsp+1A8h+Reply], eax
0x18000d0b4  xor     r15d, r15d
0x18000d0b7  mov     r14d, [rsp+1A8h+var_154]
0x18000d0bc  movzx   esi, r15b
0x18000d0c0  movzx   edi, r15b
0x18000d0c4  test    eax, eax
0x18000d0c6  jns     short loc_18000D0DA
0x18000d0c8  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18000d0cf  mov     r8d, 32Eh
0x18000d0d5  jmp     loc_18000D1A2
0x18000d0da  mov     [rsp+1A8h+bAlertable], r15d; bAlertable
0x18000d0df  mov     r9d, r14d; dwMilliseconds
0x18000d0e2  xor     r8d, r8d; bWaitAll
0x18000d0e5  lea     rdx, [rsp+1A8h+Handles]; lpHandles
0x18000d0ea  mov     ecx, 1; nCount
0x18000d0ef  call    cs:__imp_WaitForMultipleObjectsEx
0x18000d0f5  mov     ebx, eax
0x18000d0f7  test    dil, dil
0x18000d0fa  jnz     short loc_18000D151
0x18000d0fc  cmp     ebx, 102h
0x18000d102  jz      short loc_18000D109
0x18000d104  cmp     ebx, 1
0x18000d107  jnz     short loc_18000D151
0x18000d109  mov     edx, 1; fAbort
0x18000d10e  lea     rcx, [rsp+1A8h+pAsync]; pAsync
0x18000d116  call    cs:__imp_RpcAsyncCancelCall
0x18000d11c  cmp     ebx, 102h
0x18000d122  jnz     short loc_18000D129
0x18000d124  mov     sil, 1
0x18000d127  jmp     short loc_18000D12C
0x18000d129  mov     dil, 1
0x18000d12c  mov     [rsp+1A8h+bAlertable], r15d; bAlertable
0x18000d131  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x18000d137  xor     r8d, r8d; bWaitAll
0x18000d13a  lea     rdx, [rsp+1A8h+Handles]; lpHandles
0x18000d13f  mov     ecx, 1; nCount
0x18000d144  call    cs:__imp_WaitForMultipleObjectsEx
0x18000d14a  mov     ebx, eax
0x18000d14c  test    sil, sil
0x18000d14f  jz      short loc_18000D0F7
0x18000d151  test    ebx, ebx
0x18000d153  jz      short loc_18000D170
0x18000d155  call    cs:__imp_GetLastError
0x18000d15b  test    eax, eax
0x18000d15d  jle     short loc_18000D167
0x18000d15f  movzx   eax, ax
0x18000d162  or      eax, 80070000h
0x18000d167  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18000d16e  jmp     short loc_18000D198
0x18000d170  lea     rdx, [rsp+1A8h+Reply]; Reply
0x18000d175  lea     rcx, [rsp+1A8h+pAsync]; pAsync
0x18000d17d  call    cs:__imp_RpcAsyncCompleteCall
0x18000d183  test    eax, eax
0x18000d185  jz      short loc_18000D1B7
0x18000d187  jle     short loc_18000D191
0x18000d189  movzx   eax, ax
0x18000d18c  or      eax, 80070000h
0x18000d191  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18000d198  mov     r8d, 32Eh; unsigned int
0x18000d19e  mov     [rsp+1A8h+Reply], eax
0x18000d1a2  mov     [rsp+1A8h+bAlertable], eax
0x18000d1a6  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000d1ad  mov     ecx, 2; unsigned __int8
0x18000d1b2  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000d1b7  mov     rcx, qword ptr [rsp+1A8h+pAsync.u]; hObject
0x18000d1bf  test    rcx, rcx
0x18000d1c2  jz      short loc_18000D1CA
0x18000d1c4  call    cs:__imp_CloseHandle
0x18000d1ca  test    sil, sil
0x18000d1cd  jz      loc_18000D34D
0x18000d1d3  mov     [rsp+1A8h+Reply], 800705B4h
0x18000d1db  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f3ddbd0a50d11f24ac1f58eb5524dee0_@@CA@XZ; _lambda_f3ddbd0a50d11f24ac1f58eb5524dee0_::_lambda_invoker_cdecl_(void)
0x18000d1e2  call    ?get@?$static_lazy@VMSAClientTraceTelemetry@@@details@wil@@QEAAPEAVMSAClientTraceTelemetry@@P6AXXZ@Z; wil::details::static_lazy<MSAClientTraceTelemetry>::get(void (*)(void))
0x18000d1e7  mov     rcx, [rax+8]
0x18000d1eb  mov     eax, [rcx]
0x18000d1ed  cmp     eax, 5
0x18000d1f0  jbe     loc_18000D327
0x18000d1f6  mov     rdx, [rcx+18h]
0x18000d1fa  mov     rax, [rcx+10h]
0x18000d1fe  mov     r8, 400000000000h
0x18000d208  test    r8, rax
0x18000d20b  jz      loc_18000D327
0x18000d211  mov     rax, rdx
0x18000d214  and     rax, r8
0x18000d217  cmp     rax, rdx
0x18000d21a  jnz     loc_18000D327
0x18000d220  mov     [rsp+1A8h+var_138], 3000000h
0x18000d229  mov     [rsp+1A8h+var_154], r14d
0x18000d22e  lea     rax, [rsp+1A8h+var_138]
0x18000d233  mov     [rsp+1A8h+var_58], rax
0x18000d23b  mov     [rsp+1A8h+var_50], 8
0x18000d247  lea     rax, [rsp+1A8h+var_154]
0x18000d24c  mov     [rsp+1A8h+var_68], rax
0x18000d254  mov     [rsp+1A8h+var_60], 4
0x18000d260  lea     rax, aWlidcenumident; "WLIDCEnumIdentities"
0x18000d267  mov     [rsp+1A8h+var_78], rax
0x18000d26f  mov     [rsp+1A8h+var_70], 14h
0x18000d27b  mov     dword ptr [rsp+1A8h+EventDescriptor.Id], 0B000000h
0x18000d286  movzx   eax, cs:word_18007725B
0x18000d28d  mov     dword ptr [rsp+1A8h+EventDescriptor.Level], eax
0x18000d294  mov     [rsp+1A8h+EventDescriptor.Keyword], r8
0x18000d29c  mov     rax, [rcx+8]
0x18000d2a0  mov     [rsp+1A8h+var_98.Ptr], rax
0x18000d2a8  movzx   eax, word ptr [rax]
0x18000d2ab  mov     [rsp+1A8h+var_98.Size], eax
0x18000d2b2  mov     dword ptr [rsp+1A8h+var_98.0Ch], 2
0x18000d2bd  lea     rax, byte_180077265
0x18000d2c4  mov     [rsp+1A8h+var_88], rax
0x18000d2cc  mov     [rsp+1A8h+var_80], 44h ; 'D'
0x18000d2d7  mov     [rsp+1A8h+var_7C], 1
0x18000d2e2  lea     rax, _TraceLoggingMetadataEnd
0x18000d2e9  lea     rdx, _TraceLoggingMetadata
0x18000d2f0  sub     eax, edx
0x18000d2f2  mov     dword ptr [rsp+1A8h+var_140], eax
0x18000d2f6  mov     eax, dword ptr [rsp+1A8h+var_140]
0x18000d2fa  lea     rax, [rsp+1A8h+var_98]
0x18000d302  mov     [rsp+1A8h+UserData], rax; UserData
0x18000d307  mov     [rsp+1A8h+bAlertable], 5; UserDataCount
0x18000d30f  xor     r9d, r9d; RelatedActivityId
0x18000d312  xor     r8d, r8d; ActivityId
0x18000d315  lea     rdx, [rsp+1A8h+EventDescriptor]; EventDescriptor
0x18000d31d  mov     rcx, [rcx+20h]; RegHandle
0x18000d321  call    cs:__imp_EventWriteTransfer
0x18000d327  mov     eax, [rsp+1A8h+Reply]
0x18000d32b  mov     [rsp+1A8h+bAlertable], eax
0x18000d32f  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18000d336  mov     r8d, 32Eh; unsigned int
0x18000d33c  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000d343  mov     ecx, 2; unsigned __int8
0x18000d348  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000d34d  test    dil, dil
0x18000d350  jz      short loc_18000D380
0x18000d352  mov     [rsp+1A8h+Reply], 800704C7h
0x18000d35a  mov     [rsp+1A8h+bAlertable], 800704C7h
0x18000d362  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18000d369  mov     r8d, 32Eh; unsigned int
0x18000d36f  lea     rdx, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000d376  mov     ecx, 2; unsigned __int8
0x18000d37b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000d380  mov     eax, [rsp+1A8h+Reply]
0x18000d384  cmp     eax, 800706B5h
0x18000d389  jz      short loc_18000D392
0x18000d38b  cmp     eax, 800706BAh
0x18000d390  jnz     short loc_18000D39B
0x18000d392  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18000d397  mov     eax, [rsp+1A8h+Reply]
0x18000d39b  cmp     [rsp+1A8h+Binding], 0
0x18000d3a1  jz      short loc_18000D3B2
0x18000d3a3  lea     rcx, [rsp+1A8h+Binding]; Binding
0x18000d3a8  call    cs:__imp_RpcBindingFree
0x18000d3ae  mov     eax, [rsp+1A8h+Reply]
0x18000d3b2  mov     rcx, [rsp+1A8h+var_48]
0x18000d3ba  xor     rcx, rsp; StackCookie
0x18000d3bd  call    __security_check_cookie
0x18000d3c2  add     rsp, 170h
0x18000d3c9  pop     r15
0x18000d3cb  pop     r14
0x18000d3cd  pop     r13
0x18000d3cf  pop     r12
0x18000d3d1  pop     rdi
0x18000d3d2  pop     rsi
0x18000d3d3  pop     rbx
0x18000d3d4  retn
0x1800543e0  push    rbp
0x1800543e2  sub     rsp, 50h
0x1800543e6  mov     rbp, rdx
0x1800543e9  mov     rcx, [rcx]
0x1800543ec  mov     ecx, [rcx]; unsigned int
0x1800543ee  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x1800543f3  nop
0x1800543f4  add     rsp, 50h
0x1800543f8  pop     rbp
0x1800543f9  retn
```
