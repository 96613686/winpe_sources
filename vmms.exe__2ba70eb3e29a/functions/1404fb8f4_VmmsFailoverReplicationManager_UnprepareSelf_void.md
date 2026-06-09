# VmmsFailoverReplicationManager::UnprepareSelf(void)

- ea: `0x1404fb8f4`
- end: `0x1404fbbcf`
- name: `?UnprepareSelf@VmmsFailoverReplicationManager@@EEAAXXZ`
- size: `731`
- prototype: `void __fastcall(VmmsFailoverReplicationManager *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1404fb8e0`

## callees

- `0x14000131c`
- `0x14001a024`
- `0x14008108c`
- `0x1400b2bdc`
- `0x140144194`
- `0x140497314`
- `0x1404baac0`
- `0x1404fb88c`
- `0x1404fb8f4`
- `0x140504a40`
- `0x1405c681c`
- `0x140660618`
- `0x1408aa010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1404fb950`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1404fb993`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1404fb9db`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1404fba23`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1404fba6b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1404fbab3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1404fb950`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1404fb993`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1404fb9db`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1404fba23`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1404fba6b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1404fbab3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1404fb93d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1404fb984`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1404fb9c8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1404fba10`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1404fba58`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1404fbaa0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1404fb93d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1404fb984`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1404fb9c8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1404fba10`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1404fba58`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1404fbaa0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1404fb928`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1404fb973`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1404fb9b3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1404fb9fb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1404fba43`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1404fba8b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1404fb928`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1404fb973`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1404fb9b3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1404fb9fb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1404fba43`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1404fba8b`

## pseudocode

```c
void __fastcall VmmsFailoverReplicationManager::UnprepareSelf(VmmsFailoverReplicationManager *this)
{
  char *v1; // rbx
  struct _TP_TIMER *v3; // rcx
  PTP_TIMER *v4; // r14
  struct _TP_TIMER *v5; // rcx
  struct _TP_TIMER *v6; // rcx
  struct _TP_TIMER *v7; // rcx
  struct _TP_TIMER *v8; // rcx
  struct _TP_TIMER *v9; // rcx
  int (*v10)(void *, struct IVmmsVirtualMachine *, struct AvhdReferenceTree *); // rcx
  ComVmmsFailoverReplicationManager *v11; // rcx
  VmmsMigrationManager *v12; // rdi
  RTL_SRWLOCK *v13; // rax
  RTL_SRWLOCK *v14; // rax
  VmmsMigrationManager *v15[5]; // [rsp+20h] [rbp-28h] BYREF

  v1 = (char *)this - 856;
  v3 = (struct _TP_TIMER *)*((_QWORD *)this - 106);
  if ( v3 )
  {
    SetThreadpoolTimer(v3, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this - 106), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this - 106));
  }
  v4 = (PTP_TIMER *)((char *)this - 840);
  v5 = (struct _TP_TIMER *)*((_QWORD *)this - 105);
  if ( v5 )
  {
    SetThreadpoolTimer(v5, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*v4, 1);
    CloseThreadpoolTimer(*v4);
  }
  v6 = (struct _TP_TIMER *)*((_QWORD *)this - 104);
  if ( v6 )
  {
    SetThreadpoolTimer(v6, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this - 104), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this - 104));
  }
  v7 = (struct _TP_TIMER *)*((_QWORD *)this - 102);
  if ( v7 )
  {
    SetThreadpoolTimer(v7, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this - 102), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this - 102));
  }
  v8 = (struct _TP_TIMER *)*((_QWORD *)this - 101);
  if ( v8 )
  {
    SetThreadpoolTimer(v8, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this - 101), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this - 101));
  }
  v9 = (struct _TP_TIMER *)*((_QWORD *)this - 103);
  if ( v9 )
  {
    SetThreadpoolTimer(v9, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this - 103), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this - 103));
  }
  v10 = (int (*)(void *, struct IVmmsVirtualMachine *, struct AvhdReferenceTree *))*((_QWORD *)this - 91);
  if ( v10 )
    (*(void (__fastcall **)(int (*)(void *, struct IVmmsVirtualMachine *, struct AvhdReferenceTree *), _QWORD))(*(_QWORD *)v10 + 48LL))(
      v10,
      *((unsigned int *)this - 180));
  AvhdReferenceTree::UnregisterFilter(v10, v1);
  if ( *((_QWORD *)this - 98) )
  {
    v15[0] = 0;
    if ( (unsigned __int8)Vml::VmSingletonObject<VmmsMigrationManager,VmmsMigrationManager>::TryOpenShared(v15) )
      VmmsMigrationManager::UnsubscribeEvents(v15[0], *((struct IVmmsMigrationManagerEvents **)this - 98));
    Vml::VmReferencePtr<VmmsFailoverReplicationManager::FrManagerMigrationEvents,Vml::VmUserReferenceTraits>::Reset(
      (char *)this - 784,
      0);
    Vml::VmReferencePtr<IVmmsPlannedVirtualMachine,Vml::VmUserReferenceTraits>::~VmReferencePtr<IVmmsPlannedVirtualMachine,Vml::VmUserReferenceTraits>(v15);
  }
  v11 = (ComVmmsFailoverReplicationManager *)*((_QWORD *)this - 99);
  if ( v11 )
  {
    ComVmmsFailoverReplicationManager::Teardown(v11);
    Vml::VmComPtr<ComFailoverReplicationBrokerManager>::Reset((char *)this - 792);
  }
  v15[0] = 0;
  if ( (unsigned __int8)Vml::VmSingletonObject<VmmsVirtualMachineManager,IVmmsVirtualMachineManager>::TryOpenShared(v15) )
  {
    v12 = v15[0];
    v13 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(VmmsMigrationManager *))(*(_QWORD *)v15[0] + 408LL))(v15[0]);
    Vml::VmAsyncEventBase::RemoveDelegate(v13 + 10, (VmmsFailoverReplicationManager *)((char *)this - 264));
    v14 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(VmmsMigrationManager *))(*(_QWORD *)v12 + 416LL))(v12);
    Vml::VmAsyncEventBase::RemoveDelegate(v14 + 10, (VmmsFailoverReplicationManager *)((char *)this - 136));
  }
  TraceLoggingUnregister_EventUnregister(&dword_140C6E218);
  Vml::VmSingletonObject<VmmsFailoverReplicationManager,VmmsFailoverReplicationManager>::UnprepareSelf((char *)this - 840);
  Vml::VmReferencePtr<IVmmsPlannedVirtualMachine,Vml::VmUserReferenceTraits>::~VmReferencePtr<IVmmsPlannedVirtualMachine,Vml::VmUserReferenceTraits>(v15);
}

```

## disassembly

```asm
0x1404fb8f4  mov     [rsp+arg_8], rbx
0x1404fb8f9  mov     [rsp+arg_10], rbp
0x1404fb8fe  push    rsi
0x1404fb8ff  push    rdi
0x1404fb900  push    r14
0x1404fb902  sub     rsp, 30h
0x1404fb906  lea     rbx, [rcx-358h]
0x1404fb90d  mov     rsi, rcx
0x1404fb910  mov     rcx, [rbx+8]; pti
0x1404fb914  xor     edi, edi
0x1404fb916  mov     ebp, 1
0x1404fb91b  test    rcx, rcx
0x1404fb91e  jz      short loc_1404FB95C
0x1404fb920  xor     r9d, r9d; msWindowLength
0x1404fb923  xor     r8d, r8d; msPeriod
0x1404fb926  xor     edx, edx; pftDueTime
0x1404fb928  call    cs:__imp_SetThreadpoolTimer
0x1404fb92f  nop     dword ptr [rax+rax+00h]
0x1404fb934  mov     rcx, [rsi-350h]; pti
0x1404fb93b  mov     edx, ebp; fCancelPendingCallbacks
0x1404fb93d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1404fb944  nop     dword ptr [rax+rax+00h]
0x1404fb949  mov     rcx, [rsi-350h]; pti
0x1404fb950  call    cs:__imp_CloseThreadpoolTimer
0x1404fb957  nop     dword ptr [rax+rax+00h]
0x1404fb95c  lea     r14, [rsi-348h]
0x1404fb963  mov     rcx, [r14]; pti
0x1404fb966  test    rcx, rcx
0x1404fb969  jz      short loc_1404FB99F
0x1404fb96b  xor     r9d, r9d; msWindowLength
0x1404fb96e  xor     r8d, r8d; msPeriod
0x1404fb971  xor     edx, edx; pftDueTime
0x1404fb973  call    cs:__imp_SetThreadpoolTimer
0x1404fb97a  nop     dword ptr [rax+rax+00h]
0x1404fb97f  mov     rcx, [r14]; pti
0x1404fb982  mov     edx, ebp; fCancelPendingCallbacks
0x1404fb984  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1404fb98b  nop     dword ptr [rax+rax+00h]
0x1404fb990  mov     rcx, [r14]; pti
0x1404fb993  call    cs:__imp_CloseThreadpoolTimer
0x1404fb99a  nop     dword ptr [rax+rax+00h]
0x1404fb99f  mov     rcx, [rsi-340h]; pti
0x1404fb9a6  test    rcx, rcx
0x1404fb9a9  jz      short loc_1404FB9E7
0x1404fb9ab  xor     r9d, r9d; msWindowLength
0x1404fb9ae  xor     r8d, r8d; msPeriod
0x1404fb9b1  xor     edx, edx; pftDueTime
0x1404fb9b3  call    cs:__imp_SetThreadpoolTimer
0x1404fb9ba  nop     dword ptr [rax+rax+00h]
0x1404fb9bf  mov     rcx, [rsi-340h]; pti
0x1404fb9c6  mov     edx, ebp; fCancelPendingCallbacks
0x1404fb9c8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1404fb9cf  nop     dword ptr [rax+rax+00h]
0x1404fb9d4  mov     rcx, [rsi-340h]; pti
0x1404fb9db  call    cs:__imp_CloseThreadpoolTimer
0x1404fb9e2  nop     dword ptr [rax+rax+00h]
0x1404fb9e7  mov     rcx, [rsi-330h]; pti
0x1404fb9ee  test    rcx, rcx
0x1404fb9f1  jz      short loc_1404FBA2F
0x1404fb9f3  xor     r9d, r9d; msWindowLength
0x1404fb9f6  xor     r8d, r8d; msPeriod
0x1404fb9f9  xor     edx, edx; pftDueTime
0x1404fb9fb  call    cs:__imp_SetThreadpoolTimer
0x1404fba02  nop     dword ptr [rax+rax+00h]
0x1404fba07  mov     rcx, [rsi-330h]; pti
0x1404fba0e  mov     edx, ebp; fCancelPendingCallbacks
0x1404fba10  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1404fba17  nop     dword ptr [rax+rax+00h]
0x1404fba1c  mov     rcx, [rsi-330h]; pti
0x1404fba23  call    cs:__imp_CloseThreadpoolTimer
0x1404fba2a  nop     dword ptr [rax+rax+00h]
0x1404fba2f  mov     rcx, [rsi-328h]; pti
0x1404fba36  test    rcx, rcx
0x1404fba39  jz      short loc_1404FBA77
0x1404fba3b  xor     r9d, r9d; msWindowLength
0x1404fba3e  xor     r8d, r8d; msPeriod
0x1404fba41  xor     edx, edx; pftDueTime
0x1404fba43  call    cs:__imp_SetThreadpoolTimer
0x1404fba4a  nop     dword ptr [rax+rax+00h]
0x1404fba4f  mov     rcx, [rsi-328h]; pti
0x1404fba56  mov     edx, ebp; fCancelPendingCallbacks
0x1404fba58  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1404fba5f  nop     dword ptr [rax+rax+00h]
0x1404fba64  mov     rcx, [rsi-328h]; pti
0x1404fba6b  call    cs:__imp_CloseThreadpoolTimer
0x1404fba72  nop     dword ptr [rax+rax+00h]
0x1404fba77  mov     rcx, [rsi-338h]; pti
0x1404fba7e  test    rcx, rcx
0x1404fba81  jz      short loc_1404FBABF
0x1404fba83  xor     r9d, r9d; msWindowLength
0x1404fba86  xor     r8d, r8d; msPeriod
0x1404fba89  xor     edx, edx; pftDueTime
0x1404fba8b  call    cs:__imp_SetThreadpoolTimer
0x1404fba92  nop     dword ptr [rax+rax+00h]
0x1404fba97  mov     rcx, [rsi-338h]; pti
0x1404fba9e  mov     edx, ebp; fCancelPendingCallbacks
0x1404fbaa0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1404fbaa7  nop     dword ptr [rax+rax+00h]
0x1404fbaac  mov     rcx, [rsi-338h]; pti
0x1404fbab3  call    cs:__imp_CloseThreadpoolTimer
0x1404fbaba  nop     dword ptr [rax+rax+00h]
0x1404fbabf  mov     rcx, [rsi-2D8h]
0x1404fbac6  test    rcx, rcx
0x1404fbac9  jz      short loc_1404FBADD
0x1404fbacb  mov     rax, [rcx]
0x1404fbace  mov     edx, [rsi-2D0h]
0x1404fbad4  mov     rax, [rax+30h]
0x1404fbad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1404fbadd  mov     rdx, rbx; void *
0x1404fbae0  call    ?UnregisterFilter@AvhdReferenceTree@@SAXP6AJPEAXPEAUIVmmsVirtualMachine@@AEAV1@@Z0@Z; AvhdReferenceTree::UnregisterFilter(long (*)(void *,IVmmsVirtualMachine *,AvhdReferenceTree &),void *)
0x1404fbae5  lea     rbx, [rsi-310h]
0x1404fbaec  cmp     [rbx], rdi
0x1404fbaef  jz      short loc_1404FBB25
0x1404fbaf1  lea     rcx, [rsp+48h+var_28]
0x1404fbaf6  mov     [rsp+48h+var_28], rdi
0x1404fbafb  call    ?TryOpenShared@?$VmSingletonObject@VVmmsMigrationManager@@V1@@Vml@@SA_NPEAPEAVVmmsMigrationManager@@@Z; Vml::VmSingletonObject<VmmsMigrationManager,VmmsMigrationManager>::TryOpenShared(VmmsMigrationManager * *)
0x1404fbb00  test    al, al
0x1404fbb02  jz      short loc_1404FBB11
0x1404fbb04  mov     rdx, [rbx]; struct IVmmsMigrationManagerEvents *
0x1404fbb07  mov     rcx, [rsp+48h+var_28]; this
0x1404fbb0c  call    ?UnsubscribeEvents@VmmsMigrationManager@@QEAAJPEAUIVmmsMigrationManagerEvents@@@Z; VmmsMigrationManager::UnsubscribeEvents(IVmmsMigrationManagerEvents *)
0x1404fbb11  xor     edx, edx
0x1404fbb13  mov     rcx, rbx
0x1404fbb16  call    ?Reset@?$VmReferencePtr@VFrManagerMigrationEvents@VmmsFailoverReplicationManager@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAVFrManagerMigrationEvents@VmmsFailoverReplicationManager@@@Z; Vml::VmReferencePtr<VmmsFailoverReplicationManager::FrManagerMigrationEvents,Vml::VmUserReferenceTraits>::Reset(VmmsFailoverReplicationManager::FrManagerMigrationEvents *)
0x1404fbb1b  lea     rcx, [rsp+48h+var_28]
0x1404fbb20  call    ??1?$VmReferencePtr@UIVmmsPlannedVirtualMachine@@VVmUserReferenceTraits@Vml@@@Vml@@QEAA@XZ; Vml::VmReferencePtr<IVmmsPlannedVirtualMachine,Vml::VmUserReferenceTraits>::~VmReferencePtr<IVmmsPlannedVirtualMachine,Vml::VmUserReferenceTraits>(void)
0x1404fbb25  lea     rbx, [rsi-318h]
0x1404fbb2c  mov     rcx, [rbx]; this
0x1404fbb2f  test    rcx, rcx
0x1404fbb32  jz      short loc_1404FBB41
0x1404fbb34  call    ?Teardown@ComVmmsFailoverReplicationManager@@AEAAXXZ; ComVmmsFailoverReplicationManager::Teardown(void)
0x1404fbb39  mov     rcx, rbx
0x1404fbb3c  call    ?Reset@?$VmComPtr@VComFailoverReplicationBrokerManager@@@Vml@@QEAAXPEAVComFailoverReplicationBrokerManager@@@Z; Vml::VmComPtr<ComFailoverReplicationBrokerManager>::Reset(ComFailoverReplicationBrokerManager *)
0x1404fbb41  lea     rcx, [rsp+48h+var_28]
0x1404fbb46  mov     [rsp+48h+var_28], rdi
0x1404fbb4b  call    ?TryOpenShared@?$VmSingletonObject@VVmmsVirtualMachineManager@@UIVmmsVirtualMachineManager@@@Vml@@SA_NPEAPEAUIVmmsVirtualMachineManager@@@Z; Vml::VmSingletonObject<VmmsVirtualMachineManager,IVmmsVirtualMachineManager>::TryOpenShared(IVmmsVirtualMachineManager * *)
0x1404fbb50  test    al, al
0x1404fbb52  jz      short loc_1404FBB9D
0x1404fbb54  mov     rdi, [rsp+48h+var_28]
0x1404fbb59  mov     rcx, rdi
0x1404fbb5c  mov     rax, [rdi]
0x1404fbb5f  mov     rax, [rax+198h]
0x1404fbb66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1404fbb6b  lea     rdx, [rsi-108h]; struct Vml::VmDelegate *
0x1404fbb72  lea     rcx, [rax+50h]; SRWLock
0x1404fbb76  call    ?RemoveDelegate@VmAsyncEventBase@Vml@@IEAAXPEAVVmDelegate@2@@Z; Vml::VmAsyncEventBase::RemoveDelegate(Vml::VmDelegate *)
0x1404fbb7b  mov     rax, [rdi]
0x1404fbb7e  mov     rcx, rdi
0x1404fbb81  mov     rax, [rax+1A0h]
0x1404fbb88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1404fbb8d  lea     rdx, [rsi-88h]; struct Vml::VmDelegate *
0x1404fbb94  lea     rcx, [rax+50h]; SRWLock
0x1404fbb98  call    ?RemoveDelegate@VmAsyncEventBase@Vml@@IEAAXPEAVVmDelegate@2@@Z; Vml::VmAsyncEventBase::RemoveDelegate(Vml::VmDelegate *)
0x1404fbb9d  lea     rcx, dword_140C6E218
0x1404fbba4  call    TraceLoggingUnregister_EventUnregister
0x1404fbba9  mov     rcx, r14
0x1404fbbac  call    ?UnprepareSelf@?$VmSingletonObject@VVmmsFailoverReplicationManager@@V1@@Vml@@MEAAXXZ; Vml::VmSingletonObject<VmmsFailoverReplicationManager,VmmsFailoverReplicationManager>::UnprepareSelf(void)
0x1404fbbb1  lea     rcx, [rsp+48h+var_28]
0x1404fbbb6  call    ??1?$VmReferencePtr@UIVmmsPlannedVirtualMachine@@VVmUserReferenceTraits@Vml@@@Vml@@QEAA@XZ; Vml::VmReferencePtr<IVmmsPlannedVirtualMachine,Vml::VmUserReferenceTraits>::~VmReferencePtr<IVmmsPlannedVirtualMachine,Vml::VmUserReferenceTraits>(void)
0x1404fbbbb  mov     rbx, [rsp+48h+arg_8]
0x1404fbbc0  mov     rbp, [rsp+48h+arg_10]
0x1404fbbc5  add     rsp, 30h
0x1404fbbc9  pop     r14
0x1404fbbcb  pop     rdi
0x1404fbbcc  pop     rsi
0x1404fbbcd  retn
```
