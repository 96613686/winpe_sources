# WorkThreadManager::s_CheckFloodListProgress(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x180037600`
- end: `0x18003777b`
- name: `?s_CheckFloodListProgress@WorkThreadManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `379`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task`

## callees

- `0x18000a6a0`
- `0x18000d6bc`
- `0x18000e7f0`
- `0x18000f7d4`
- `0x18000f808`
- `0x180037600`
- `0x180037784`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003761f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003761f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800376c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800376c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800376b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800376b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800376c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800376c8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800376ab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800376ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WorkThreadManager::s_CheckFloodListProgress(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_TIMER Timer)
{
  WorkThreadManager::TaskData *v3; // rdi
  unsigned int v4; // ecx
  DWORD LastError; // ebx
  unsigned int v6; // edx
  __int64 v7; // rax
  __int64 v8; // rax
  unsigned int v9; // edx
  WorkThreadManager::TaskData *v10; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-10h] BYREF
  __int64 v12; // [rsp+28h] [rbp-8h]
  WorkThreadManager::TaskData *v13; // [rsp+58h] [rbp+28h] BYREF

  v3 = 0;
  v13 = 0;
  AcquireSRWLockExclusive(&WorkThreadManager::s_rwLock);
  if ( WorkThreadManager::s_taskFloodingList == (_UNKNOWN *)&WorkThreadManager::s_taskFloodingList )
  {
    WorkThreadManager::s_floodCheckPeriod = 25;
    WorkThreadManager::s_anyThreadMadeProgress = 0;
LABEL_3:
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      &WorkThreadManager::s_floodListTimer,
      0);
    goto LABEL_10;
  }
  if ( WorkThreadManager::s_anyThreadMadeProgress )
  {
    v4 = WorkThreadManager::s_floodCheckPeriod;
    WorkThreadManager::s_anyThreadMadeProgress = 0;
  }
  else
  {
    v8 = WorkThreadManager::TaskList::PopFront(&WorkThreadManager::s_taskFloodingList, &pftDueTime);
    wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>::operator=(
      &v13,
      v8);
    v10 = (WorkThreadManager::TaskData *)pftDueTime;
    pftDueTime = 0;
    if ( v10 )
      WorkThreadManager::TaskData::`scalar deleting destructor'(v10, v9);
    if ( WorkThreadManager::s_taskFloodingList == (_UNKNOWN *)&WorkThreadManager::s_taskFloodingList )
    {
      v4 = WorkThreadManager::s_floodCheckPeriod;
    }
    else
    {
      v4 = 2000;
      if ( WorkThreadManager::s_floodCheckPeriod + 25 > 0x7D0 )
        v4 = WorkThreadManager::s_floodCheckPeriod + 25;
      WorkThreadManager::s_floodCheckPeriod = v4;
    }
    v3 = v13;
  }
  if ( !v4 )
    goto LABEL_3;
  pftDueTime = (struct _FILETIME)(-10000LL * v4);
  SetThreadpoolTimer(WorkThreadManager::s_floodListTimer, &pftDueTime, 0, 0);
LABEL_10:
  LastError = GetLastError();
  ReleaseSRWLockExclusive(&WorkThreadManager::s_rwLock);
  SetLastError(LastError);
  v12 = 0;
  if ( v3 )
  {
    *((_DWORD *)v3 + 1) |= 0x10u;
    v7 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
           &pftDueTime,
           &v13);
    WorkThreadManager::s_AttachAndRecoverTask(v7);
    v3 = v13;
  }
  if ( v3 )
    WorkThreadManager::TaskData::`scalar deleting destructor'(v3, v6);
}

```

## disassembly

```asm
0x180037600  mov     [rsp-8+arg_0], rbx
0x180037605  mov     [rsp-8+arg_8], rdi
0x18003760a  push    rbp
0x18003760b  mov     rbp, rsp
0x18003760e  sub     rsp, 30h
0x180037612  xor     edi, edi
0x180037614  mov     [rbp+arg_18], rdi
0x180037618  lea     rcx, ?s_rwLock@WorkThreadManager@@0Vsrwlock@wil@@A; SRWLock
0x18003761f  call    cs:__imp_AcquireSRWLockExclusive
0x180037625  nop
0x180037626  lea     rbx, ?s_taskFloodingList@WorkThreadManager@@0VTaskList@1@A; WorkThreadManager::TaskList WorkThreadManager::s_taskFloodingList
0x18003762d  cmp     cs:?s_taskFloodingList@WorkThreadManager@@0VTaskList@1@A, rbx; WorkThreadManager::TaskList WorkThreadManager::s_taskFloodingList
0x180037634  jnz     loc_1800376F0
0x18003763a  mov     cs:?s_floodCheckPeriod@WorkThreadManager@@0KA, 19h; ulong WorkThreadManager::s_floodCheckPeriod
0x180037644  mov     cs:?s_anyThreadMadeProgress@WorkThreadManager@@0_NA, dil; bool WorkThreadManager::s_anyThreadMadeProgress
0x18003764b  xor     edx, edx
0x18003764d  lea     rcx, ?s_floodListTimer@WorkThreadManager@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> WorkThreadManager::s_floodListTimer
0x180037654  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180037659  jmp     short loc_1800376B1
0x18003765b  mov     eax, cs:?s_floodCheckPeriod@WorkThreadManager@@0KA; ulong WorkThreadManager::s_floodCheckPeriod
0x180037661  add     eax, 19h
0x180037664  mov     ecx, 7D0h
0x180037669  cmp     eax, ecx
0x18003766b  cmova   ecx, eax
0x18003766e  mov     cs:?s_floodCheckPeriod@WorkThreadManager@@0KA, ecx; ulong WorkThreadManager::s_floodCheckPeriod
0x180037674  mov     rdi, [rbp+arg_18]
0x180037678  test    ecx, ecx
0x18003767a  jz      short loc_18003764B
0x18003767c  mov     eax, ecx
0x18003767e  imul    rax, 0FFFFFFFFFFFFD8F0h
0x180037685  mov     rcx, rax
0x180037688  shr     rcx, 20h
0x18003768c  mov     [rbp+pftDueTime.dwHighDateTime], ecx
0x18003768f  mov     [rbp+pftDueTime.dwLowDateTime], eax
0x180037692  mov     rax, qword ptr [rbp+pftDueTime.dwLowDateTime]
0x180037696  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], rax
0x18003769a  xor     r9d, r9d; msWindowLength
0x18003769d  xor     r8d, r8d; msPeriod
0x1800376a0  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x1800376a4  mov     rcx, cs:?s_floodListTimer@WorkThreadManager@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; pti
0x1800376ab  call    cs:__imp_SetThreadpoolTimer
0x1800376b1  call    cs:__imp_GetLastError
0x1800376b7  mov     ebx, eax
0x1800376b9  lea     rcx, ?s_rwLock@WorkThreadManager@@0Vsrwlock@wil@@A; SRWLock
0x1800376c0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800376c6  mov     ecx, ebx; dwErrCode
0x1800376c8  call    cs:__imp_SetLastError
0x1800376ce  mov     [rbp+var_8], 0
0x1800376d6  test    rdi, rdi
0x1800376d9  jnz     short loc_180037715
0x1800376db  test    rdi, rdi
0x1800376de  jnz     short loc_18003770B
0x1800376e0  mov     rbx, [rsp+30h+arg_0]
0x1800376e5  mov     rdi, [rsp+30h+arg_8]
0x1800376ea  add     rsp, 30h
0x1800376ee  pop     rbp
0x1800376ef  retn
0x1800376f0  cmp     cs:?s_anyThreadMadeProgress@WorkThreadManager@@0_NA, 0; bool WorkThreadManager::s_anyThreadMadeProgress
0x1800376f7  jz      short loc_180037734
0x1800376f9  mov     ecx, cs:?s_floodCheckPeriod@WorkThreadManager@@0KA; ulong WorkThreadManager::s_floodCheckPeriod
0x1800376ff  mov     cs:?s_anyThreadMadeProgress@WorkThreadManager@@0_NA, 0; bool WorkThreadManager::s_anyThreadMadeProgress
0x180037706  jmp     loc_180037678
0x18003770b  mov     rcx, rdi; this
0x18003770e  call    ??_GTaskData@WorkThreadManager@@QEAAPEAXI@Z; WorkThreadManager::TaskData::`scalar deleting destructor'(uint)
0x180037713  jmp     short loc_1800376E0
0x180037715  or      dword ptr [rdi+4], 10h
0x180037719  lea     rdx, [rbp+arg_18]
0x18003771d  lea     rcx, [rbp+pftDueTime]
0x180037721  call    ??0?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x180037726  mov     rcx, rax
0x180037729  call    ?s_AttachAndRecoverTask@WorkThreadManager@@CAXV?$unique_ptr@UTaskData@WorkThreadManager@@U?$default_delete@UTaskData@WorkThreadManager@@@wistd@@@wistd@@@Z; WorkThreadManager::s_AttachAndRecoverTask(wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>)
0x18003772e  mov     rdi, [rbp+arg_18]
0x180037732  jmp     short loc_1800376DB
0x180037734  lea     rdx, [rbp+pftDueTime]
0x180037738  mov     rcx, rbx
0x18003773b  call    ?PopFront@TaskList@WorkThreadManager@@QEAA?AV?$unique_ptr@UTaskData@WorkThreadManager@@U?$default_delete@UTaskData@WorkThreadManager@@@wistd@@@wistd@@XZ; WorkThreadManager::TaskList::PopFront(void)
0x180037740  mov     rdx, rax
0x180037743  lea     rcx, [rbp+arg_18]
0x180037747  call    ??4?$unique_ptr@UTaskData@WorkThreadManager@@U?$default_delete@UTaskData@WorkThreadManager@@@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>::operator=(wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>> &&)
0x18003774c  mov     rcx, qword ptr [rbp+pftDueTime.dwLowDateTime]; this
0x180037750  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], 0
0x180037758  test    rcx, rcx
0x18003775b  jz      short loc_180037762
0x18003775d  call    ??_GTaskData@WorkThreadManager@@QEAAPEAXI@Z; WorkThreadManager::TaskData::`scalar deleting destructor'(uint)
0x180037762  cmp     cs:?s_taskFloodingList@WorkThreadManager@@0VTaskList@1@A, rbx; WorkThreadManager::TaskList WorkThreadManager::s_taskFloodingList
0x180037769  jnz     loc_18003765B
0x18003776f  mov     ecx, cs:?s_floodCheckPeriod@WorkThreadManager@@0KA; ulong WorkThreadManager::s_floodCheckPeriod
0x180037775  jmp     loc_180037674
```
