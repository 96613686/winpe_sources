# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180011434`
- end: `0x1800115f8`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `452`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180056540`

## callees

- `0x180011434`
- `0x18001d8f8`
- `0x18001e998`
- `0x18001ea0c`
- `0x18001f0ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800114f2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001154a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800114f2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001154a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011487`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800114e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001153a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011487`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800114e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001153a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011473`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800114cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011526`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011473`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800114cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011526`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011580`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800115c0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011580`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800115c0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001156f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800115af`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001156f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800115af`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001158f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800115cf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001158f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800115cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::FeatureStateManager::~FeatureStateManager(wil::details::FeatureStateManager *this)
{
  void *v2; // rdi
  HANDLE ProcessHeap; // rax
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v4; // r8
  void *v5; // rsi
  HANDLE v6; // rax
  void *v7; // rdx
  wil::details *v8; // rcx
  void *v9; // rsi
  HANDLE v10; // rax
  struct _TP_TIMER *v11; // rdi
  struct _TP_TIMER *v12; // rdi
  void *v13; // rcx

  *(_BYTE *)this = 0;
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    (char *)this + 48,
    0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    (char *)this + 56,
    0);
  v2 = (void *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  v4 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)*((_QWORD *)this + 28);
  if ( v4 && qword_18006F530 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18006F530[25], qword_18006F530, v4);
  v5 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v5 )
  {
    v6 = GetProcessHeap();
    HeapFree(v6, 0, v5);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  v8 = (wil::details *)*((_QWORD *)this + 18);
  if ( v8 )
    wil::details::UnregisterWilFeatureConfigurationChange(v8, v7);
  v9 = (void *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v9 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v9);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v11 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v11 )
  {
    SetThreadpoolTimer(v11, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v11, 1);
    CloseThreadpoolTimer(v11);
  }
  v12 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v12 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 6), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v12, 1);
    CloseThreadpoolTimer(v12);
  }
  v13 = (void *)*((_QWORD *)this + 2);
  if ( v13 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v13);
}

```

## disassembly

```asm
0x180011434  push    rbx
0x180011436  push    rsi
0x180011437  push    rdi
0x180011438  push    r14
0x18001143a  push    r15
0x18001143c  sub     rsp, 20h
0x180011440  mov     rbx, rcx
0x180011443  mov     byte ptr [rcx], 0
0x180011446  xor     edx, edx
0x180011448  add     rcx, 30h ; '0'
0x18001144c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180011451  xor     edx, edx
0x180011453  lea     rcx, [rbx+38h]
0x180011457  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001145c  mov     rdi, [rbx+100h]
0x180011463  mov     qword ptr [rbx+100h], 0
0x18001146e  test    rdi, rdi
0x180011471  jz      short loc_180011493
0x180011473  call    cs:__imp_GetProcessHeap
0x18001147a  nop     dword ptr [rax+rax+00h]
0x18001147f  mov     rcx, rax; hHeap
0x180011482  mov     r8, rdi; lpMem
0x180011485  xor     edx, edx; dwFlags
0x180011487  call    cs:__imp_HeapFree
0x18001148e  nop     dword ptr [rax+rax+00h]
0x180011493  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18001149a  test    r8, r8
0x18001149d  jz      short loc_1800114B7
0x18001149f  mov     rdx, cs:qword_18006F530; SRWLock
0x1800114a6  test    rdx, rdx
0x1800114a9  jz      short loc_1800114B7
0x1800114ab  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800114b2  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800114b7  lea     rdi, [rbx+98h]
0x1800114be  mov     rsi, [rdi+40h]
0x1800114c2  mov     qword ptr [rdi+40h], 0
0x1800114ca  test    rsi, rsi
0x1800114cd  jz      short loc_1800114EF
0x1800114cf  call    cs:__imp_GetProcessHeap
0x1800114d6  nop     dword ptr [rax+rax+00h]
0x1800114db  mov     rcx, rax; hHeap
0x1800114de  mov     r8, rsi; lpMem
0x1800114e1  xor     edx, edx; dwFlags
0x1800114e3  call    cs:__imp_HeapFree
0x1800114ea  nop     dword ptr [rax+rax+00h]
0x1800114ef  mov     rcx, rdi; lpCriticalSection
0x1800114f2  call    cs:__imp_DeleteCriticalSection
0x1800114f9  nop     dword ptr [rax+rax+00h]
0x1800114fe  mov     rcx, [rbx+90h]; this
0x180011505  test    rcx, rcx
0x180011508  jz      short loc_18001150F
0x18001150a  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x18001150f  mov     rsi, [rbx+88h]
0x180011516  mov     qword ptr [rbx+88h], 0
0x180011521  test    rsi, rsi
0x180011524  jz      short loc_180011546
0x180011526  call    cs:__imp_GetProcessHeap
0x18001152d  nop     dword ptr [rax+rax+00h]
0x180011532  mov     rcx, rax; hHeap
0x180011535  mov     r8, rsi; lpMem
0x180011538  xor     edx, edx; dwFlags
0x18001153a  call    cs:__imp_HeapFree
0x180011541  nop     dword ptr [rax+rax+00h]
0x180011546  lea     rcx, [rbx+48h]; lpCriticalSection
0x18001154a  call    cs:__imp_DeleteCriticalSection
0x180011551  nop     dword ptr [rax+rax+00h]
0x180011556  mov     rdi, [rbx+38h]
0x18001155a  mov     esi, 1
0x18001155f  test    rdi, rdi
0x180011562  jz      short loc_18001159B
0x180011564  xor     r9d, r9d; msWindowLength
0x180011567  xor     r8d, r8d; msPeriod
0x18001156a  xor     edx, edx; pftDueTime
0x18001156c  mov     rcx, rdi; pti
0x18001156f  call    cs:__imp_SetThreadpoolTimer
0x180011576  nop     dword ptr [rax+rax+00h]
0x18001157b  mov     edx, esi; fCancelPendingCallbacks
0x18001157d  mov     rcx, rdi; pti
0x180011580  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180011587  nop     dword ptr [rax+rax+00h]
0x18001158c  mov     rcx, rdi; pti
0x18001158f  call    cs:__imp_CloseThreadpoolTimer
0x180011596  nop     dword ptr [rax+rax+00h]
0x18001159b  mov     rdi, [rbx+30h]
0x18001159f  test    rdi, rdi
0x1800115a2  jz      short loc_1800115DC
0x1800115a4  xor     r9d, r9d; msWindowLength
0x1800115a7  xor     r8d, r8d; msPeriod
0x1800115aa  xor     edx, edx; pftDueTime
0x1800115ac  mov     rcx, rdi; pti
0x1800115af  call    cs:__imp_SetThreadpoolTimer
0x1800115b6  nop     dword ptr [rax+rax+00h]
0x1800115bb  mov     edx, esi; fCancelPendingCallbacks
0x1800115bd  mov     rcx, rdi; pti
0x1800115c0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800115c7  nop     dword ptr [rax+rax+00h]
0x1800115cc  mov     rcx, rdi; pti
0x1800115cf  call    cs:__imp_CloseThreadpoolTimer
0x1800115d6  nop     dword ptr [rax+rax+00h]
0x1800115db  nop
0x1800115dc  mov     rcx, [rbx+10h]; lpMem
0x1800115e0  test    rcx, rcx
0x1800115e3  jz      short loc_1800115EB
0x1800115e5  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800115ea  nop
0x1800115eb  add     rsp, 20h
0x1800115ef  pop     r15
0x1800115f1  pop     r14
0x1800115f3  pop     rdi
0x1800115f4  pop     rsi
0x1800115f5  pop     rbx
0x1800115f6  retn
```
