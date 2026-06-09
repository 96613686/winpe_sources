# RemotePushSubscription::~RemotePushSubscription(void)

- ea: `0x1800154dc`
- end: `0x180015603`
- name: `??1RemotePushSubscription@@UEAA@XZ`
- size: `295`
- prototype: `void __fastcall(RemotePushSubscription *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800154a0`

## callees

- `0x180007010`
- `0x180007aa0`
- `0x18000a420`
- `0x1800154dc`
- `0x180015730`
- `0x180015768`
- `0x1800157bc`
- `0x18001585c`
- `0x180015880`
- `0x1800158b8`
- `0x180038d98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800155d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800155d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800155ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800155ea`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800155e1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800155e1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800155f8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800155f8`

## pseudocode

```c
void __fastcall RemotePushSubscription::~RemotePushSubscription(RemotePushSubscription *this)
{
  PTP_WAIT *v2; // rsi
  void *v3; // rdx

  *(_QWORD *)this = &RemotePushSubscription::`vftable';
  if ( !*((_BYTE *)this + 344) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v2 = (PTP_WAIT *)((char *)this + 64);
  if ( *((_QWORD *)this + 8) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)this + 28);
    SetThreadpoolWait(*v2, 0, 0);
    ReleaseSRWLockExclusive((PSRWLOCK)this + 28);
    WaitForThreadpoolWaitCallbacks(*v2, 1);
  }
  DestroyRpcQueryChannelInfo(*((_DWORD *)this + 84), *((struct tag_EvtRpcQueryChannelInfo **)this + 26));
  v3 = (void *)*((_QWORD *)this + 30);
  if ( v3 )
    Session::RemoveControllableObject(*((Session **)this + 6), v3);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>((char *)this + 288);
  RemotePushSubscription::BatchResultSet::Clear((RemotePushSubscription *)((char *)this + 248));
  tlx::unique_any<tlx::handle_traits<void *,void (void *),&void MyEvtRpcFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void (void *),&void MyEvtRpcFree(void *),0>>((char *)this + 240);
  tlx::unique_any<tlx::handle_traits<void *,void (void *),&void MyEvtRpcFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void (void *),&void MyEvtRpcFree(void *),0>>((char *)this + 232);
  wmi::AutoRef<Object>::Release((char *)this + 216);
  EvtHandleRef::~EvtHandleRef((RemotePushSubscription *)((char *)this + 200));
  wmi::AutoRef<Object>::Release((char *)this + 192);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((char *)this + 72);
  tlx::unique_any<tlx::handle_traits<_TP_WAIT *,void (_TP_WAIT *),&private: static void RemotePullSubscription::WaitAndCloseThreadpoolWait(_TP_WAIT *),0>>::~unique_any<tlx::handle_traits<_TP_WAIT *,void (_TP_WAIT *),&private: static void RemotePullSubscription::WaitAndCloseThreadpoolWait(_TP_WAIT *),0>>((char *)this + 64);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((char *)this + 56);
  wmi::AutoRef<Object>::Release((char *)this + 48);
  *(_QWORD *)this = &wmi::RefBase::`vftable';
}

```

## disassembly

```asm
0x1800154dc  push    rbx
0x1800154de  push    rsi
0x1800154df  push    rdi
0x1800154e0  push    r14
0x1800154e2  sub     rsp, 28h
0x1800154e6  mov     rdi, rcx
0x1800154e9  lea     rax, ??_7RemotePushSubscription@@6B@; const RemotePushSubscription::`vftable'
0x1800154f0  mov     [rcx], rax
0x1800154f3  cmp     byte ptr [rcx+158h], 0
0x1800154fa  jz      loc_1800155BF
0x180015500  lea     rsi, [rdi+40h]
0x180015504  cmp     qword ptr [rsi], 0
0x180015508  jnz     loc_1800155C9
0x18001550e  mov     rdx, [rdi+0D0h]; struct tag_EvtRpcQueryChannelInfo *
0x180015515  mov     ecx, [rdi+150h]; unsigned int
0x18001551b  call    ?DestroyRpcQueryChannelInfo@@YAXKPEAUtag_EvtRpcQueryChannelInfo@@@Z; DestroyRpcQueryChannelInfo(ulong,tag_EvtRpcQueryChannelInfo *)
0x180015520  lea     r14, [rdi+0F0h]
0x180015527  mov     rdx, [r14]; void *
0x18001552a  test    rdx, rdx
0x18001552d  jz      short loc_180015538
0x18001552f  mov     rcx, [rdi+30h]; this
0x180015533  call    ?RemoveControllableObject@Session@@QEAA_NPEAX@Z; Session::RemoveControllableObject(void *)
0x180015538  lea     rcx, [rdi+120h]
0x18001553f  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hEventLogRpcActivityProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x180015544  lea     rcx, [rdi+0F8h]; this
0x18001554b  call    ?Clear@BatchResultSet@RemotePushSubscription@@QEAAXXZ; RemotePushSubscription::BatchResultSet::Clear(void)
0x180015550  mov     rcx, r14
0x180015553  call    ??1?$unique_any@U?$handle_traits@PEAX$$A6AXPEAX@Z$1?MyEvtRpcFree@@YAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,void (void *),&MyEvtRpcFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void (void *),&MyEvtRpcFree(void *),0>>(void)
0x180015558  lea     rcx, [rdi+0E8h]
0x18001555f  call    ??1?$unique_any@U?$handle_traits@PEAX$$A6AXPEAX@Z$1?MyEvtRpcFree@@YAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,void (void *),&MyEvtRpcFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void (void *),&MyEvtRpcFree(void *),0>>(void)
0x180015564  lea     rcx, [rdi+0D8h]; void *
0x18001556b  call    ?Release@?$AutoRef@VObject@@@wmi@@QEAAXXZ; wmi::AutoRef<Object>::Release(void)
0x180015570  lea     rcx, [rdi+0C8h]; this
0x180015577  call    ??1EvtHandleRef@@QEAA@XZ; EvtHandleRef::~EvtHandleRef(void)
0x18001557c  lea     rcx, [rdi+0C0h]; void *
0x180015583  call    ?Release@?$AutoRef@VObject@@@wmi@@QEAAXXZ; wmi::AutoRef<Object>::Release(void)
0x180015588  lea     rcx, [rdi+48h]
0x18001558c  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180015591  mov     rcx, rsi
0x180015594  call    ??1?$unique_any@U?$handle_traits@PEAU_TP_WAIT@@$$A6AXPEAU1@@Z$1?WaitAndCloseThreadpoolWait@RemotePullSubscription@@CAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<_TP_WAIT *,void (_TP_WAIT *),&RemotePullSubscription::WaitAndCloseThreadpoolWait(_TP_WAIT *),0>>::~unique_any<tlx::handle_traits<_TP_WAIT *,void (_TP_WAIT *),&RemotePullSubscription::WaitAndCloseThreadpoolWait(_TP_WAIT *),0>>(void)
0x180015599  lea     rcx, [rdi+38h]
0x18001559d  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800155a2  lea     rcx, [rdi+30h]; void *
0x1800155a6  call    ?Release@?$AutoRef@VObject@@@wmi@@QEAAXXZ; wmi::AutoRef<Object>::Release(void)
0x1800155ab  lea     rax, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x1800155b2  mov     [rdi], rax
0x1800155b5  add     rsp, 28h
0x1800155b9  pop     r14
0x1800155bb  pop     rdi
0x1800155bc  pop     rsi
0x1800155bd  pop     rbx
0x1800155be  retn
0x1800155bf  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800155c4  jmp     loc_180015500
0x1800155c9  lea     rbx, [rdi+0E0h]
0x1800155d0  mov     rcx, rbx; SRWLock
0x1800155d3  call    cs:__imp_AcquireSRWLockExclusive
0x1800155d9  xor     r8d, r8d; pftTimeout
0x1800155dc  xor     edx, edx; h
0x1800155de  mov     rcx, [rsi]; pwa
0x1800155e1  call    cs:__imp_SetThreadpoolWait
0x1800155e7  mov     rcx, rbx; SRWLock
0x1800155ea  call    cs:__imp_ReleaseSRWLockExclusive
0x1800155f0  mov     edx, 1; fCancelPendingCallbacks
0x1800155f5  mov     rcx, [rsi]; pwa
0x1800155f8  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800155fe  jmp     loc_18001550E
```
