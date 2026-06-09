# wil::details::_dynamic_atexit_destructor_for__g_enabledStateManager__

- ea: `0x180031360`
- end: `0x18003159a`
- name: `wil::details::_dynamic_atexit_destructor_for__g_enabledStateManager__`
- size: `570`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800037b0`
- `0x18000c434`
- `0x18000c4b4`
- `0x18000cc10`
- `0x180031360`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800313dc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003150a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800313dc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003150a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031438`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031566`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031438`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031566`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031475`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003149c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031475`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003149c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031483`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800314aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031483`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800314aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800313a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031571`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800313a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031571`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800313bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031583`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800313bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031583`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800314d9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800314d9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800314e2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800314e2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800314cb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800314cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void wil::details::_dynamic_atexit_destructor_for__g_enabledStateManager__()
{
  struct _TP_TIMER *v0; // rsi
  DWORD v1; // edi
  unsigned int v2; // r9d
  unsigned int *v3; // rdi
  __int64 v4; // rsi
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v5; // rdx
  void *v6; // rdi
  HANDLE ProcessHeap; // rax
  void *v8; // rdi
  HANDLE v9; // rax
  struct _TP_TIMER *v10; // rbx
  struct _TP_TIMER *v11; // rdi
  unsigned int v12; // r9d
  unsigned int *v13; // rbx
  __int64 v14; // rsi
  DWORD LastError; // ebx
  const char *v16; // [rsp+20h] [rbp-8h]

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    wil::details::g_enabledStateManager = 0;
    v11 = pti;
    pti = 0;
    AcquireSRWLockExclusive(&SRWLock);
    v13 = (unsigned int *)qword_180041838;
    v14 = qword_180041840;
    if ( (unsigned __int64)(qword_180041840 - qword_180041838) >= 0x10 )
    {
      while ( v13 != (unsigned int *)v14 )
      {
        wil_details_RecordCachedUsage(*v13, *((_QWORD *)v13 + 1));
        v13 += 4;
      }
      qword_180041840 = qword_180041838;
      wil::details::WilApi_RecordFeatureUsage(0, 0xFEu, 0, v12, v16);
    }
    ReleaseSRWLockExclusive(&SRWLock);
    if ( v11 )
    {
      LastError = GetLastError();
      wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v11);
      SetLastError(LastError);
    }
  }
  else
  {
    wil::details::g_enabledStateManager = 0;
    v0 = pti;
    if ( pti )
    {
      v1 = GetLastError();
      wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v0);
      SetLastError(v1);
    }
    wil::details::g_enabledStateManager = 0;
    pti = 0;
    AcquireSRWLockExclusive(&SRWLock);
    v3 = (unsigned int *)qword_180041838;
    v4 = qword_180041840;
    if ( (unsigned __int64)(qword_180041840 - qword_180041838) >= 0x10 )
    {
      while ( v3 != (unsigned int *)v4 )
      {
        wil_details_RecordCachedUsage(*v3, *((_QWORD *)v3 + 1));
        v3 += 4;
      }
      qword_180041840 = qword_180041838;
      wil::details::WilApi_RecordFeatureUsage(0, 0xFEu, 0, v2, v16);
    }
    ReleaseSRWLockExclusive(&SRWLock);
    if ( qword_180041880 )
      wil::details::WilApi_UnsubscribeFeatureStateChangeNotification(qword_180041880, v5);
    if ( qword_180041878 )
      wil::details::WilApi_UnsubscribeFeatureStateChangeNotification(qword_180041878, v5);
    v6 = lpMem;
    lpMem = 0;
    if ( v6 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v6);
    }
    v8 = qword_180041850;
    qword_180041850 = 0;
    if ( v8 )
    {
      v9 = GetProcessHeap();
      HeapFree(v9, 0, v8);
    }
    v10 = pti;
    if ( pti )
    {
      SetThreadpoolTimer(pti, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v10, 1);
      CloseThreadpoolTimer(v10);
    }
  }
}

```

## disassembly

```asm
0x180031360  mov     [rsp+arg_0], rbx
0x180031365  mov     [rsp+arg_8], rsi
0x18003136a  push    rdi; char *
0x18003136b  sub     rsp, 20h
0x18003136f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180031376  jnz     loc_1800314ED
0x18003137c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180031383  test    rax, rax
0x180031386  jz      short loc_180031395
0x180031388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003138d  test    al, al
0x18003138f  jnz     loc_1800314ED
0x180031395  xor     ebx, ebx
0x180031397  mov     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, ebx; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18003139d  mov     rsi, cs:pti
0x1800313a4  test    rsi, rsi
0x1800313a7  jz      short loc_1800313C1
0x1800313a9  call    cs:__imp_GetLastError
0x1800313af  mov     edi, eax
0x1800313b1  mov     rcx, rsi; pti
0x1800313b4  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1800313b9  mov     ecx, edi; dwErrCode
0x1800313bb  call    cs:__imp_SetLastError
0x1800313c1  mov     cs:pti, rbx
0x1800313c8  mov     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, ebx; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800313ce  mov     cs:pti, rbx
0x1800313d5  lea     rcx, SRWLock; SRWLock
0x1800313dc  call    cs:__imp_AcquireSRWLockExclusive
0x1800313e2  nop
0x1800313e3  mov     rdi, cs:qword_180041838
0x1800313ea  mov     rsi, cs:qword_180041840
0x1800313f1  mov     rax, rsi
0x1800313f4  sub     rax, rdi
0x1800313f7  cmp     rax, 10h
0x1800313fb  jb      short loc_180031431
0x1800313fd  cmp     rdi, rsi
0x180031400  jz      short loc_180031413
0x180031402  mov     rdx, [rdi+8]
0x180031406  mov     ecx, [rdi]
0x180031408  call    wil_details_RecordCachedUsage
0x18003140d  add     rdi, 10h
0x180031411  jmp     short loc_1800313FD
0x180031413  mov     rax, cs:qword_180041838
0x18003141a  mov     cs:qword_180041840, rax
0x180031421  xor     r8d, r8d; unsigned int
0x180031424  mov     edx, 0FEh; unsigned int
0x180031429  xor     ecx, ecx; this
0x18003142b  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180031430  nop
0x180031431  lea     rcx, SRWLock; SRWLock
0x180031438  call    cs:__imp_ReleaseSRWLockExclusive
0x18003143e  mov     rcx, cs:qword_180041880; this
0x180031445  test    rcx, rcx
0x180031448  jz      short loc_180031450
0x18003144a  call    ?WilApi_UnsubscribeFeatureStateChangeNotification@details@wil@@YAXPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details::WilApi_UnsubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18003144f  nop
0x180031450  mov     rcx, cs:qword_180041878; this
0x180031457  test    rcx, rcx
0x18003145a  jz      short loc_180031462
0x18003145c  call    ?WilApi_UnsubscribeFeatureStateChangeNotification@details@wil@@YAXPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details::WilApi_UnsubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180031461  nop
0x180031462  mov     rdi, cs:lpMem
0x180031469  mov     cs:lpMem, rbx
0x180031470  test    rdi, rdi
0x180031473  jz      short loc_180031489
0x180031475  call    cs:__imp_GetProcessHeap
0x18003147b  mov     rcx, rax; hHeap
0x18003147e  mov     r8, rdi; lpMem
0x180031481  xor     edx, edx; dwFlags
0x180031483  call    cs:__imp_HeapFree
0x180031489  mov     rdi, cs:qword_180041850
0x180031490  mov     cs:qword_180041850, rbx
0x180031497  test    rdi, rdi
0x18003149a  jz      short loc_1800314B0
0x18003149c  call    cs:__imp_GetProcessHeap
0x1800314a2  mov     rcx, rax; hHeap
0x1800314a5  mov     r8, rdi; lpMem
0x1800314a8  xor     edx, edx; dwFlags
0x1800314aa  call    cs:__imp_HeapFree
0x1800314b0  mov     rbx, cs:pti
0x1800314b7  test    rbx, rbx
0x1800314ba  jz      loc_18003158A
0x1800314c0  xor     r9d, r9d; msWindowLength
0x1800314c3  xor     r8d, r8d; msPeriod
0x1800314c6  xor     edx, edx; pftDueTime
0x1800314c8  mov     rcx, rbx; pti
0x1800314cb  call    cs:__imp_SetThreadpoolTimer
0x1800314d1  mov     edx, 1; fCancelPendingCallbacks
0x1800314d6  mov     rcx, rbx; pti
0x1800314d9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800314df  mov     rcx, rbx; pti
0x1800314e2  call    cs:__imp_CloseThreadpoolTimer
0x1800314e8  jmp     loc_18003158A
0x1800314ed  xor     ebx, ebx
0x1800314ef  mov     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, ebx; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800314f5  mov     rdi, cs:pti
0x1800314fc  mov     cs:pti, rbx
0x180031503  lea     rcx, SRWLock; SRWLock
0x18003150a  call    cs:__imp_AcquireSRWLockExclusive
0x180031510  nop
0x180031511  mov     rbx, cs:qword_180041838
0x180031518  mov     rsi, cs:qword_180041840
0x18003151f  mov     rax, rsi
0x180031522  sub     rax, rbx
0x180031525  cmp     rax, 10h
0x180031529  jb      short loc_18003155F
0x18003152b  cmp     rbx, rsi
0x18003152e  jz      short loc_180031541
0x180031530  mov     rdx, [rbx+8]
0x180031534  mov     ecx, [rbx]
0x180031536  call    wil_details_RecordCachedUsage
0x18003153b  add     rbx, 10h
0x18003153f  jmp     short loc_18003152B
0x180031541  mov     rax, cs:qword_180041838
0x180031548  mov     cs:qword_180041840, rax
0x18003154f  xor     r8d, r8d; unsigned int
0x180031552  mov     edx, 0FEh; unsigned int
0x180031557  xor     ecx, ecx; this
0x180031559  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18003155e  nop
0x18003155f  lea     rcx, SRWLock; SRWLock
0x180031566  call    cs:__imp_ReleaseSRWLockExclusive
0x18003156c  test    rdi, rdi
0x18003156f  jz      short loc_18003158A
0x180031571  call    cs:__imp_GetLastError
0x180031577  mov     ebx, eax
0x180031579  mov     rcx, rdi; pti
0x18003157c  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180031581  mov     ecx, ebx; dwErrCode
0x180031583  call    cs:__imp_SetLastError
0x180031589  nop
0x18003158a  mov     rbx, [rsp+28h+arg_0]
0x18003158f  mov     rsi, [rsp+28h+arg_8]
0x180031594  add     rsp, 20h
0x180031598  pop     rdi
0x180031599  retn
```
