# Shutdown(utl::unique_lock<utl::mutex> &)

- ea: `0x18009e314`
- end: `0x18009e528`
- name: `?Shutdown@@YAXAEAV?$unique_lock@Vmutex@utl@@@utl@@@Z`
- size: `532`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x18009daf0`
- `0x18009e540`
- `0x1800d9d7d`

## callees

- `0x180001008`
- `0x180033ae0`
- `0x18005ff90`
- `0x180064854`
- `0x180092ee4`
- `0x1800974b4`
- `0x18009aee0`
- `0x18009cfec`
- `0x18009d080`
- `0x18009e314`
- `0x1800a4cf4`
- `0x1800c1a08`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18009e472`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18009e472`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18009e47f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18009e47f`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x18009e3f4`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x18009e415`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x18009e3f4`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x18009e415`
- `RPCRT4!RpcEpUnregister` at `0x18009e451`
- `RPCRT4!RpcEpUnregister` at `0x18009e451`
- `RPCRT4!RpcServerInqBindings` at `0x18009e439`
- `RPCRT4!RpcServerInqBindings` at `0x18009e439`

## pseudocode

```c
void Shutdown()
{
  _DWORD *v0; // r9
  RPC_BINDING_VECTOR **v1; // rax
  RPC_BINDING_VECTOR *BindingVector; // [rsp+20h] [rbp-40h] BYREF
  int v3; // [rsp+28h] [rbp-38h] BYREF
  char v4; // [rsp+2Ch] [rbp-34h]
  _BYTE v5[16]; // [rsp+30h] [rbp-30h] BYREF
  _DWORD v6[4]; // [rsp+40h] [rbp-20h] BYREF

  if ( !byte_180111704 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids);
    }
    v3 = 0;
    v4 = 0;
    _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v3);
    if ( (unsigned int)dword_18010F008 > 5 )
    {
      if ( v4 && (v6[0] || v6[1] || v6[2] || v6[3]) )
        v0 = v6;
      else
        v0 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_18010F008,
        &unk_1800FC05B,
        v5,
        v0);
    }
    byte_180111704 = 1;
    if ( g_service )
      EventService::SignalShutdown(g_service);
    if ( byte_180111705 )
    {
      RpcServerUnregisterIfEx(&unk_1800DFBE0, 0, 1);
      byte_180111705 = 0;
    }
    if ( byte_180110118 )
    {
      RpcServerUnregisterIfEx(&unk_1800E1ED0, 0, 1);
      byte_180110118 = 0;
    }
    if ( byte_1801116B0 )
    {
      BindingVector = 0;
      v1 = (RPC_BINDING_VECTOR **)tlx::replace<tlx::handle_traits<_RPC_BINDING_VECTOR *,long (_RPC_BINDING_VECTOR *),&long MyRpcBindingVectorFree(_RPC_BINDING_VECTOR *),0>>(&BindingVector);
      if ( !RpcServerInqBindings(v1) )
        RpcEpUnregister(&unk_1800DFBE0, BindingVector, 0);
      byte_1801116B0 = 0;
      tlx::unique_any<tlx::handle_traits<_RPC_BINDING_VECTOR *,long (_RPC_BINDING_VECTOR *),&long MyRpcBindingVectorFree(_RPC_BINDING_VECTOR *),0>>::~unique_any<tlx::handle_traits<_RPC_BINDING_VECTOR *,long (_RPC_BINDING_VECTOR *),&long MyRpcBindingVectorFree(_RPC_BINDING_VECTOR *),0>>(&BindingVector);
    }
    CloseThreadpoolCleanupGroupMembers(ptpcg, 0, 0);
    CloseThreadpoolCleanupGroup(ptpcg);
    if ( g_service )
    {
      LegacyEventLogShutDown(&v3);
      EventService::GlobalShutdown();
    }
    tlx::unique_any<tlx::file_handle_traits>::reset(&hEvent, 0);
    v3 = 2;
    if ( (unsigned int)dword_18010F008 > 5 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_18010F008,
        &unk_1800FBF14,
        v5,
        0);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids);
    }
    TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>::~TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>(&v3);
  }
}

```

## disassembly

```asm
0x18009e314  mov     [rsp-8+arg_0], rbx
0x18009e319  mov     [rsp-8+arg_8], rsi
0x18009e31e  push    rbp
0x18009e31f  mov     rbp, rsp
0x18009e322  sub     rsp, 60h
0x18009e326  mov     rax, cs:__security_cookie
0x18009e32d  xor     rax, rsp
0x18009e330  mov     [rbp+var_10], rax
0x18009e334  xor     ebx, ebx
0x18009e336  cmp     cs:byte_180111704, bl
0x18009e33c  jnz     loc_18009E50C
0x18009e342  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e349  lea     rsi, WPP_GLOBAL_Control
0x18009e350  cmp     rcx, rsi
0x18009e353  jz      short loc_18009E374
0x18009e355  test    byte ptr [rcx+1Ch], 8
0x18009e359  jz      short loc_18009E374
0x18009e35b  cmp     byte ptr [rcx+19h], 4
0x18009e35f  jb      short loc_18009E374
0x18009e361  mov     rcx, [rcx+10h]
0x18009e365  lea     edx, [rbx+3Dh]
0x18009e368  lea     r8, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids
0x18009e36f  call    WPP_SF_
0x18009e374  lea     rcx, [rbp+var_38]
0x18009e378  mov     [rbp+var_38], ebx
0x18009e37b  mov     [rbp+var_34], bl
0x18009e37e  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hEventLogRpcActivityProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x18009e383  mov     eax, cs:dword_18010F008
0x18009e389  cmp     eax, 5
0x18009e38c  jbe     short loc_18009E3C7
0x18009e38e  cmp     [rbp+var_34], bl
0x18009e391  jz      short loc_18009E3AD
0x18009e393  cmp     [rbp+var_20], ebx
0x18009e396  jnz     short loc_18009E3A7
0x18009e398  cmp     [rbp+var_1C], ebx
0x18009e39b  jnz     short loc_18009E3A7
0x18009e39d  cmp     [rbp+var_18], ebx
0x18009e3a0  jnz     short loc_18009E3A7
0x18009e3a2  cmp     [rbp+var_14], ebx
0x18009e3a5  jz      short loc_18009E3AD
0x18009e3a7  lea     r9, [rbp+var_20]
0x18009e3ab  jmp     short loc_18009E3B0
0x18009e3ad  mov     r9, rbx
0x18009e3b0  lea     r8, [rbp+var_30]
0x18009e3b4  lea     rdx, unk_1800FC05B
0x18009e3bb  lea     rcx, dword_18010F008
0x18009e3c2  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18009e3c7  mov     rcx, cs:?g_service@@3PEAVEventService@@EA; SRWLock
0x18009e3ce  mov     cs:byte_180111704, 1
0x18009e3d5  test    rcx, rcx
0x18009e3d8  jz      short loc_18009E3DF
0x18009e3da  call    ?SignalShutdown@EventService@@QEAAXXZ; EventService::SignalShutdown(void)
0x18009e3df  cmp     cs:byte_180111705, bl
0x18009e3e5  jz      short loc_18009E400
0x18009e3e7  xor     edx, edx; MgrTypeUuid
0x18009e3e9  lea     rcx, unk_1800DFBE0; IfSpec
0x18009e3f0  lea     r8d, [rdx+1]; RundownContextHandles
0x18009e3f4  call    cs:__imp_RpcServerUnregisterIfEx
0x18009e3fa  mov     cs:byte_180111705, bl
0x18009e400  cmp     cs:byte_180110118, bl
0x18009e406  jz      short loc_18009E421
0x18009e408  xor     edx, edx; MgrTypeUuid
0x18009e40a  lea     rcx, unk_1800E1ED0; IfSpec
0x18009e411  lea     r8d, [rdx+1]; RundownContextHandles
0x18009e415  call    cs:__imp_RpcServerUnregisterIfEx
0x18009e41b  mov     cs:byte_180110118, bl
0x18009e421  cmp     cs:byte_1801116B0, bl
0x18009e427  jz      short loc_18009E466
0x18009e429  lea     rcx, [rbp+BindingVector]
0x18009e42d  mov     [rbp+BindingVector], rbx
0x18009e431  call    ??$replace@U?$handle_traits@PEAU_RPC_BINDING_VECTOR@@$$A6AJPEAU1@@Z$1?MyRpcBindingVectorFree@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAU_RPC_BINDING_VECTOR@@AEAV?$unique_any@U?$handle_traits@PEAU_RPC_BINDING_VECTOR@@$$A6AJPEAU1@@Z$1?MyRpcBindingVectorFree@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<_RPC_BINDING_VECTOR *,long (_RPC_BINDING_VECTOR *),&MyRpcBindingVectorFree(_RPC_BINDING_VECTOR *),0>>(tlx::unique_any<tlx::handle_traits<_RPC_BINDING_VECTOR *,long (_RPC_BINDING_VECTOR *),&MyRpcBindingVectorFree(_RPC_BINDING_VECTOR *),0>> &)
0x18009e436  mov     rcx, rax; BindingVector
0x18009e439  call    cs:__imp_RpcServerInqBindings
0x18009e43f  test    eax, eax
0x18009e441  jnz     short loc_18009E457
0x18009e443  mov     rdx, [rbp+BindingVector]; BindingVector
0x18009e447  lea     rcx, unk_1800DFBE0; IfSpec
0x18009e44e  xor     r8d, r8d; UuidVector
0x18009e451  call    cs:__imp_RpcEpUnregister
0x18009e457  lea     rcx, [rbp+BindingVector]
0x18009e45b  mov     cs:byte_1801116B0, bl
0x18009e461  call    ??1?$unique_any@U?$handle_traits@PEAU_RPC_BINDING_VECTOR@@$$A6AJPEAU1@@Z$1?MyRpcBindingVectorFree@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<_RPC_BINDING_VECTOR *,long (_RPC_BINDING_VECTOR *),&MyRpcBindingVectorFree(_RPC_BINDING_VECTOR *),0>>::~unique_any<tlx::handle_traits<_RPC_BINDING_VECTOR *,long (_RPC_BINDING_VECTOR *),&MyRpcBindingVectorFree(_RPC_BINDING_VECTOR *),0>>(void)
0x18009e466  mov     rcx, cs:ptpcg; ptpcg
0x18009e46d  xor     r8d, r8d; pvCleanupContext
0x18009e470  xor     edx, edx; fCancelPendingCallbacks
0x18009e472  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18009e478  mov     rcx, cs:ptpcg; ptpcg
0x18009e47f  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18009e485  cmp     cs:?g_service@@3PEAVEventService@@EA, rbx; EventService * g_service
0x18009e48c  jz      short loc_18009E49C
0x18009e48e  lea     rcx, [rbp+var_38]
0x18009e492  call    ?LegacyEventLogShutDown@@YAXAEAV?$TraceLoggingActivity@$1?g_hEventLogRpcActivityProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@@Z; LegacyEventLogShutDown(TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider> &)
0x18009e497  call    ?GlobalShutdown@EventService@@SAXXZ; EventService::GlobalShutdown(void)
0x18009e49c  xor     edx, edx
0x18009e49e  lea     rcx, hEvent
0x18009e4a5  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18009e4aa  mov     eax, cs:dword_18010F008
0x18009e4b0  mov     [rbp+var_38], 2
0x18009e4b7  cmp     eax, 5
0x18009e4ba  jbe     short loc_18009E4D6
0x18009e4bc  xor     r9d, r9d
0x18009e4bf  lea     r8, [rbp+var_30]
0x18009e4c3  lea     rdx, unk_1800FBF14
0x18009e4ca  lea     rcx, dword_18010F008
0x18009e4d1  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18009e4d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e4dd  cmp     rcx, rsi
0x18009e4e0  jz      short loc_18009E503
0x18009e4e2  test    byte ptr [rcx+1Ch], 8
0x18009e4e6  jz      short loc_18009E503
0x18009e4e8  cmp     byte ptr [rcx+19h], 4
0x18009e4ec  jb      short loc_18009E503
0x18009e4ee  mov     rcx, [rcx+10h]
0x18009e4f2  lea     r8, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids
0x18009e4f9  mov     edx, 3Eh ; '>'
0x18009e4fe  call    WPP_SF_
0x18009e503  lea     rcx, [rbp+var_38]
0x18009e507  call    ??1?$TraceLoggingActivity@$1?g_hEventLogRpcActivityProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@QEAA@XZ; TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>::~TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>(void)
0x18009e50c  mov     rcx, [rbp+var_10]
0x18009e510  xor     rcx, rsp; StackCookie
0x18009e513  call    __security_check_cookie
0x18009e518  mov     rbx, [rsp+60h+arg_0]
0x18009e51d  mov     rsi, [rsp+60h+arg_8]
0x18009e522  add     rsp, 60h
0x18009e526  pop     rbp
0x18009e527  retn
```
