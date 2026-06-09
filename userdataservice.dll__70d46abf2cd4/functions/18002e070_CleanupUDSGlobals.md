# CleanupUDSGlobals

- ea: `0x18002e070`
- end: `0x18002e350`
- name: `CleanupUDSGlobals`
- size: `736`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002db90`

## callees

- `0x18002e070`
- `0x18002e358`
- `0x18002e3e4`
- `0x18002e48c`
- `0x18002e5d4`
- `0x18002e6e8`
- `0x18002e778`
- `0x18002e800`
- `0x18002e898`
- `0x18002e990`
- `0x18002eaa4`
- `0x18002eb3c`
- `0x18002ec28`
- `0x18002ed20`
- `0x18006dde8`
- `0x18006dfc8`
- `0x18006f010`
- `0x180072be0`
- `0x180072ccc`
- `0x18007add8`
- `0x18007b5e0`
- `0x18007bf2c`
- `0x18007e7d0`
- `0x18007ea08`
- `0x18009d518`
- `0x1800aa370`
- `0x1800ae6b4`
- `0x1800aff4c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002e164`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002e27c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002e2af`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002e2e2`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002e164`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002e27c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002e2af`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002e2e2`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002e099`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002e0cc`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002e0ff`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002e135`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002e1c9`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002e1ff`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002e235`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002e099`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002e0cc`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002e0ff`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002e135`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002e1c9`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002e1ff`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002e235`

## pseudocode

```c
void CleanupUDSGlobals()
{
  AppointmentNotificationManager *v0; // rbx
  ContactNotificationManager *v1; // rbx
  EmailNotificationManager *v2; // rbx
  CallHistoryNotificationManager *v3; // rbx
  UdmMaintenanceAdviseSink *v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  WINBOOL fPending; // [rsp+40h] [rbp+20h] BYREF
  LPVOID Context; // [rsp+48h] [rbp+28h] BYREF
  LPINIT_ONCE lpInitOnce; // [rsp+50h] [rbp+30h] BYREF

  fPending = 0;
  Context = 0;
  InitOnceBeginInitialize(&stru_18015E1E8, 0, &fPending, &Context);
  v0 = (AppointmentNotificationManager *)Context;
  if ( !Context )
  {
    v0 = (AppointmentNotificationManager *)qword_18015E1F0;
    AppointmentNotificationManager::AppointmentNotificationManager((AppointmentNotificationManager *)qword_18015E1F0);
    lpInitOnce = 0;
    InitOnceComplete(&stru_18015E1E8, 0, qword_18015E1F0);
    tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&lpInitOnce);
  }
  AppointmentNotificationManager::Unadvise(v0);
  fPending = 0;
  Context = 0;
  InitOnceBeginInitialize(&stru_18015E0C0, 0, &fPending, &Context);
  v1 = (ContactNotificationManager *)Context;
  if ( !Context )
  {
    v1 = (ContactNotificationManager *)qword_18015E0C8;
    ContactNotificationManager::ContactNotificationManager((ContactNotificationManager *)qword_18015E0C8);
    lpInitOnce = 0;
    InitOnceComplete(&stru_18015E0C0, 0, qword_18015E0C8);
    tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&lpInitOnce);
  }
  ContactNotificationManager::Unadvise(v1);
  fPending = 0;
  Context = 0;
  InitOnceBeginInitialize(&stru_18015D9A8, 0, &fPending, &Context);
  v2 = (EmailNotificationManager *)Context;
  if ( !Context )
  {
    v2 = (EmailNotificationManager *)qword_18015D9B0;
    EmailNotificationManager::EmailNotificationManager((EmailNotificationManager *)qword_18015D9B0);
    lpInitOnce = 0;
    InitOnceComplete(&stru_18015D9A8, 0, qword_18015D9B0);
    tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&lpInitOnce);
  }
  EmailNotificationManager::Unadvise(v2);
  fPending = 0;
  Context = 0;
  InitOnceBeginInitialize(&stru_18015E890, 0, &fPending, &Context);
  v3 = (CallHistoryNotificationManager *)Context;
  if ( !Context )
  {
    lpInitOnce = &stru_18015E890;
    v3 = (CallHistoryNotificationManager *)tlx::_LazyImpl<CallHistoryNotificationManager,tlx::lazy_construct<CallHistoryNotificationManager>,tlx::static_lazy<CallHistoryNotificationManager,0,tlx::lazy_construct<CallHistoryNotificationManager>>>::_Initializer::_Construct(&lpInitOnce);
    if ( lpInitOnce )
      InitOnceComplete(lpInitOnce, 4u, 0);
  }
  CallHistoryNotificationManager::Unadvise(v3);
  AppointmentStoreEventSink::Shutdown();
  ChatEventSink::Shutdown();
  ChatStoreChangedEventSink::Shutdown();
  ContactAggregateEventSink::Shutdown();
  ContactEventSink::Shutdown();
  EmailMailboxEventSink::Shutdown();
  RcsServiceStatusChangedEventSink::Shutdown();
  RcsTransportChangedEventSink::Shutdown();
  ComposingStatusChangedEventSink::Shutdown();
  RcsEndUserMessageEventSink::Shutdown();
  UserDataAccountStoreEventSink::Shutdown();
  SyncManagerEventSink::Shutdown();
  fPending = 0;
  Context = 0;
  InitOnceBeginInitialize(&stru_18015E3C8, 0, &fPending, &Context);
  v4 = (UdmMaintenanceAdviseSink *)Context;
  if ( !Context )
  {
    lpInitOnce = &stru_18015E3C8;
    v4 = (UdmMaintenanceAdviseSink *)tlx::_LazyImpl<UdmMaintenanceAdviseSink,tlx::lazy_construct<UdmMaintenanceAdviseSink>,tlx::static_lazy<UdmMaintenanceAdviseSink,0,tlx::lazy_construct<UdmMaintenanceAdviseSink>>>::_Initializer::_Construct(&lpInitOnce);
    tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&lpInitOnce);
  }
  UdmMaintenanceAdviseSink::Uninitialize(v4);
  fPending = 0;
  Context = 0;
  InitOnceBeginInitialize(&stru_18015E850, 0, &fPending, &Context);
  v5 = (struct _RTL_CRITICAL_SECTION *)Context;
  if ( !Context )
  {
    lpInitOnce = &stru_18015E850;
    v5 = (struct _RTL_CRITICAL_SECTION *)tlx::_LazyImpl<ImportContactsManager,tlx::lazy_construct<ImportContactsManager>,tlx::static_lazy<ImportContactsManager,0,tlx::lazy_construct<ImportContactsManager>>>::_Initializer::_Construct(&lpInitOnce);
    tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&lpInitOnce);
  }
  ImportContactsManager::Shutdown(v5);
  fPending = 0;
  Context = 0;
  InitOnceBeginInitialize(&stru_18015E520, 0, &fPending, &Context);
  v6 = (struct _RTL_CRITICAL_SECTION *)Context;
  if ( !Context )
  {
    lpInitOnce = &stru_18015E520;
    v6 = (struct _RTL_CRITICAL_SECTION *)tlx::_LazyImpl<DataCleanupManager,tlx::lazy_construct<DataCleanupManager>,tlx::static_lazy<DataCleanupManager,0,tlx::lazy_construct<DataCleanupManager>>>::_Initializer::_Construct(&lpInitOnce);
    tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&lpInitOnce);
  }
  DataCleanupManager::Shutdown(v6);
}

```

## disassembly

```asm
0x18002e070  mov     [rsp-18h+arg_18], rbx
0x18002e075  push    rbp
0x18002e076  push    rsi
0x18002e077  push    rdi
0x18002e078  mov     rbp, rsp
0x18002e07b  sub     rsp, 20h
0x18002e07f  xor     edi, edi
0x18002e081  lea     r9, [rbp+Context]; lpContext
0x18002e085  lea     r8, [rbp+fPending]; fPending
0x18002e089  mov     [rbp+fPending], edi
0x18002e08c  xor     edx, edx; dwFlags
0x18002e08e  mov     [rbp+Context], rdi
0x18002e092  lea     rcx, stru_18015E1E8; lpInitOnce
0x18002e099  call    cs:__imp_InitOnceBeginInitialize
0x18002e09f  mov     rbx, [rbp+Context]
0x18002e0a3  test    rbx, rbx
0x18002e0a6  jz      loc_18002E25D
0x18002e0ac  mov     rcx, rbx; this
0x18002e0af  call    ?Unadvise@AppointmentNotificationManager@@QEAAXXZ; AppointmentNotificationManager::Unadvise(void)
0x18002e0b4  lea     r9, [rbp+Context]; lpContext
0x18002e0b8  mov     [rbp+fPending], edi
0x18002e0bb  lea     r8, [rbp+fPending]; fPending
0x18002e0bf  mov     [rbp+Context], rdi
0x18002e0c3  xor     edx, edx; dwFlags
0x18002e0c5  lea     rcx, stru_18015E0C0; lpInitOnce
0x18002e0cc  call    cs:__imp_InitOnceBeginInitialize
0x18002e0d2  mov     rbx, [rbp+Context]
0x18002e0d6  test    rbx, rbx
0x18002e0d9  jz      loc_18002E290
0x18002e0df  mov     rcx, rbx; this
0x18002e0e2  call    ?Unadvise@ContactNotificationManager@@QEAAXXZ; ContactNotificationManager::Unadvise(void)
0x18002e0e7  lea     r9, [rbp+Context]; lpContext
0x18002e0eb  mov     [rbp+fPending], edi
0x18002e0ee  lea     r8, [rbp+fPending]; fPending
0x18002e0f2  mov     [rbp+Context], rdi
0x18002e0f6  xor     edx, edx; dwFlags
0x18002e0f8  lea     rcx, stru_18015D9A8; lpInitOnce
0x18002e0ff  call    cs:__imp_InitOnceBeginInitialize
0x18002e105  mov     rbx, [rbp+Context]
0x18002e109  test    rbx, rbx
0x18002e10c  jz      loc_18002E2C3
0x18002e112  mov     rcx, rbx; this
0x18002e115  call    ?Unadvise@EmailNotificationManager@@QEAAXXZ; EmailNotificationManager::Unadvise(void)
0x18002e11a  lea     rsi, stru_18015E890
0x18002e121  mov     [rbp+fPending], edi
0x18002e124  mov     rcx, rsi; lpInitOnce
0x18002e127  mov     [rbp+Context], rdi
0x18002e12b  lea     r9, [rbp+Context]; lpContext
0x18002e12f  xor     edx, edx; dwFlags
0x18002e131  lea     r8, [rbp+fPending]; fPending
0x18002e135  call    cs:__imp_InitOnceBeginInitialize
0x18002e13b  mov     rbx, [rbp+Context]
0x18002e13f  test    rbx, rbx
0x18002e142  jnz     short loc_18002E16A
0x18002e144  lea     rcx, [rbp+lpInitOnce]
0x18002e148  mov     [rbp+lpInitOnce], rsi
0x18002e14c  call    ?_Construct@_Initializer@?$_LazyImpl@VCallHistoryNotificationManager@@V?$lazy_construct@VCallHistoryNotificationManager@@@tlx@@V?$static_lazy@VCallHistoryNotificationManager@@$0A@V?$lazy_construct@VCallHistoryNotificationManager@@@tlx@@@3@@tlx@@QEAAPEAXXZ; tlx::_LazyImpl<CallHistoryNotificationManager,tlx::lazy_construct<CallHistoryNotificationManager>,tlx::static_lazy<CallHistoryNotificationManager,0,tlx::lazy_construct<CallHistoryNotificationManager>>>::_Initializer::_Construct(void)
0x18002e151  mov     rcx, [rbp+lpInitOnce]; lpInitOnce
0x18002e155  mov     rbx, rax
0x18002e158  test    rcx, rcx
0x18002e15b  jz      short loc_18002E16A
0x18002e15d  xor     r8d, r8d; lpContext
0x18002e160  lea     edx, [r8+4]; dwFlags
0x18002e164  call    cs:__imp_InitOnceComplete
0x18002e16a  mov     rcx, rbx; this
0x18002e16d  call    ?Unadvise@CallHistoryNotificationManager@@QEAAXXZ; CallHistoryNotificationManager::Unadvise(void)
0x18002e172  call    ?Shutdown@AppointmentStoreEventSink@@SAXXZ; AppointmentStoreEventSink::Shutdown(void)
0x18002e177  call    ?Shutdown@ChatEventSink@@SAXXZ; ChatEventSink::Shutdown(void)
0x18002e17c  call    ?Shutdown@ChatStoreChangedEventSink@@SAXXZ; ChatStoreChangedEventSink::Shutdown(void)
0x18002e181  call    ?Shutdown@ContactAggregateEventSink@@SAXXZ; ContactAggregateEventSink::Shutdown(void)
0x18002e186  call    ?Shutdown@ContactEventSink@@SAXXZ; ContactEventSink::Shutdown(void)
0x18002e18b  call    ?Shutdown@EmailMailboxEventSink@@SAXXZ; EmailMailboxEventSink::Shutdown(void)
0x18002e190  call    ?Shutdown@RcsServiceStatusChangedEventSink@@SAXXZ; RcsServiceStatusChangedEventSink::Shutdown(void)
0x18002e195  call    ?Shutdown@RcsTransportChangedEventSink@@SAXXZ; RcsTransportChangedEventSink::Shutdown(void)
0x18002e19a  call    ?Shutdown@ComposingStatusChangedEventSink@@SAXXZ; ComposingStatusChangedEventSink::Shutdown(void)
0x18002e19f  call    ?Shutdown@RcsEndUserMessageEventSink@@SAXXZ; RcsEndUserMessageEventSink::Shutdown(void)
0x18002e1a4  call    ?Shutdown@UserDataAccountStoreEventSink@@SAXXZ; UserDataAccountStoreEventSink::Shutdown(void)
0x18002e1a9  call    ?Shutdown@SyncManagerEventSink@@SAXXZ; SyncManagerEventSink::Shutdown(void)
0x18002e1ae  lea     rsi, stru_18015E3C8
0x18002e1b5  mov     [rbp+fPending], edi
0x18002e1b8  mov     rcx, rsi; lpInitOnce
0x18002e1bb  mov     [rbp+Context], rdi
0x18002e1bf  lea     r9, [rbp+Context]; lpContext
0x18002e1c3  xor     edx, edx; dwFlags
0x18002e1c5  lea     r8, [rbp+fPending]; fPending
0x18002e1c9  call    cs:__imp_InitOnceBeginInitialize
0x18002e1cf  mov     rbx, [rbp+Context]
0x18002e1d3  test    rbx, rbx
0x18002e1d6  jz      loc_18002E2F6
0x18002e1dc  mov     rcx, rbx; this
0x18002e1df  call    ?Uninitialize@UdmMaintenanceAdviseSink@@QEAAXXZ; UdmMaintenanceAdviseSink::Uninitialize(void)
0x18002e1e4  lea     rsi, stru_18015E850
0x18002e1eb  mov     [rbp+fPending], edi
0x18002e1ee  mov     rcx, rsi; lpInitOnce
0x18002e1f1  mov     [rbp+Context], rdi
0x18002e1f5  lea     r9, [rbp+Context]; lpContext
0x18002e1f9  xor     edx, edx; dwFlags
0x18002e1fb  lea     r8, [rbp+fPending]; fPending
0x18002e1ff  call    cs:__imp_InitOnceBeginInitialize
0x18002e205  mov     rbx, [rbp+Context]
0x18002e209  test    rbx, rbx
0x18002e20c  jz      loc_18002E314
0x18002e212  mov     rcx, rbx; lpCriticalSection
0x18002e215  call    ?Shutdown@ImportContactsManager@@QEAAXXZ; ImportContactsManager::Shutdown(void)
0x18002e21a  lea     rsi, stru_18015E520
0x18002e221  mov     [rbp+fPending], edi
0x18002e224  mov     rcx, rsi; lpInitOnce
0x18002e227  mov     [rbp+Context], rdi
0x18002e22b  lea     r9, [rbp+Context]; lpContext
0x18002e22f  xor     edx, edx; dwFlags
0x18002e231  lea     r8, [rbp+fPending]; fPending
0x18002e235  call    cs:__imp_InitOnceBeginInitialize
0x18002e23b  mov     rbx, [rbp+Context]
0x18002e23f  test    rbx, rbx
0x18002e242  jz      loc_18002E332
0x18002e248  mov     rcx, rbx; lpCriticalSection
0x18002e24b  call    ?Shutdown@DataCleanupManager@@QEAAXXZ; DataCleanupManager::Shutdown(void)
0x18002e250  mov     rbx, [rsp+20h+arg_18]
0x18002e255  add     rsp, 20h
0x18002e259  pop     rdi
0x18002e25a  pop     rsi
0x18002e25b  pop     rbp
0x18002e25c  retn
0x18002e25d  lea     rbx, qword_18015E1F0
0x18002e264  mov     rcx, rbx; this
0x18002e267  call    ??0AppointmentNotificationManager@@QEAA@XZ; AppointmentNotificationManager::AppointmentNotificationManager(void)
0x18002e26c  mov     r8, rbx; lpContext
0x18002e26f  mov     [rbp+lpInitOnce], rdi
0x18002e273  xor     edx, edx; dwFlags
0x18002e275  lea     rcx, stru_18015E1E8; lpInitOnce
0x18002e27c  call    cs:__imp_InitOnceComplete
0x18002e282  lea     rcx, [rbp+lpInitOnce]
0x18002e286  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x18002e28b  jmp     loc_18002E0AC
0x18002e290  lea     rbx, qword_18015E0C8
0x18002e297  mov     rcx, rbx; this
0x18002e29a  call    ??0ContactNotificationManager@@QEAA@XZ; ContactNotificationManager::ContactNotificationManager(void)
0x18002e29f  mov     r8, rbx; lpContext
0x18002e2a2  mov     [rbp+lpInitOnce], rdi
0x18002e2a6  xor     edx, edx; dwFlags
0x18002e2a8  lea     rcx, stru_18015E0C0; lpInitOnce
0x18002e2af  call    cs:__imp_InitOnceComplete
0x18002e2b5  lea     rcx, [rbp+lpInitOnce]
0x18002e2b9  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x18002e2be  jmp     loc_18002E0DF
0x18002e2c3  lea     rbx, qword_18015D9B0
0x18002e2ca  mov     rcx, rbx; this
0x18002e2cd  call    ??0EmailNotificationManager@@QEAA@XZ; EmailNotificationManager::EmailNotificationManager(void)
0x18002e2d2  mov     r8, rbx; lpContext
0x18002e2d5  mov     [rbp+lpInitOnce], rdi
0x18002e2d9  xor     edx, edx; dwFlags
0x18002e2db  lea     rcx, stru_18015D9A8; lpInitOnce
0x18002e2e2  call    cs:__imp_InitOnceComplete
0x18002e2e8  lea     rcx, [rbp+lpInitOnce]
0x18002e2ec  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x18002e2f1  jmp     loc_18002E112
0x18002e2f6  lea     rcx, [rbp+lpInitOnce]
0x18002e2fa  mov     [rbp+lpInitOnce], rsi
0x18002e2fe  call    ?_Construct@_Initializer@?$_LazyImpl@VUdmMaintenanceAdviseSink@@V?$lazy_construct@VUdmMaintenanceAdviseSink@@@tlx@@V?$static_lazy@VUdmMaintenanceAdviseSink@@$0A@V?$lazy_construct@VUdmMaintenanceAdviseSink@@@tlx@@@3@@tlx@@QEAAPEAXXZ; tlx::_LazyImpl<UdmMaintenanceAdviseSink,tlx::lazy_construct<UdmMaintenanceAdviseSink>,tlx::static_lazy<UdmMaintenanceAdviseSink,0,tlx::lazy_construct<UdmMaintenanceAdviseSink>>>::_Initializer::_Construct(void)
0x18002e303  lea     rcx, [rbp+lpInitOnce]
0x18002e307  mov     rbx, rax
0x18002e30a  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x18002e30f  jmp     loc_18002E1DC
0x18002e314  lea     rcx, [rbp+lpInitOnce]
0x18002e318  mov     [rbp+lpInitOnce], rsi
0x18002e31c  call    ?_Construct@_Initializer@?$_LazyImpl@VImportContactsManager@@V?$lazy_construct@VImportContactsManager@@@tlx@@V?$static_lazy@VImportContactsManager@@$0A@V?$lazy_construct@VImportContactsManager@@@tlx@@@3@@tlx@@QEAAPEAXXZ; tlx::_LazyImpl<ImportContactsManager,tlx::lazy_construct<ImportContactsManager>,tlx::static_lazy<ImportContactsManager,0,tlx::lazy_construct<ImportContactsManager>>>::_Initializer::_Construct(void)
0x18002e321  lea     rcx, [rbp+lpInitOnce]
0x18002e325  mov     rbx, rax
0x18002e328  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x18002e32d  jmp     loc_18002E212
0x18002e332  lea     rcx, [rbp+lpInitOnce]
0x18002e336  mov     [rbp+lpInitOnce], rsi
0x18002e33a  call    ?_Construct@_Initializer@?$_LazyImpl@VDataCleanupManager@@V?$lazy_construct@VDataCleanupManager@@@tlx@@V?$static_lazy@VDataCleanupManager@@$0A@V?$lazy_construct@VDataCleanupManager@@@tlx@@@3@@tlx@@QEAAPEAXXZ; tlx::_LazyImpl<DataCleanupManager,tlx::lazy_construct<DataCleanupManager>,tlx::static_lazy<DataCleanupManager,0,tlx::lazy_construct<DataCleanupManager>>>::_Initializer::_Construct(void)
0x18002e33f  lea     rcx, [rbp+lpInitOnce]
0x18002e343  mov     rbx, rax
0x18002e346  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x18002e34b  jmp     loc_18002E248
```
