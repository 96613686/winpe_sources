# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000746c`
- end: `0x180007641`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `469`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001c650`

## callees

- `0x18000746c`
- `0x18000c620`
- `0x18000e1fc`
- `0x18000e270`
- `0x18000edd0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180007531`
- `KERNEL32!DeleteCriticalSection` at `0x180007586`
- `KERNEL32!DeleteCriticalSection` at `0x180007531`
- `KERNEL32!DeleteCriticalSection` at `0x180007586`
- `KERNEL32!GetProcessHeap` at `0x1800074b5`
- `KERNEL32!GetProcessHeap` at `0x18000750e`
- `KERNEL32!GetProcessHeap` at `0x180007562`
- `KERNEL32!GetProcessHeap` at `0x1800074b5`
- `KERNEL32!GetProcessHeap` at `0x18000750e`
- `KERNEL32!GetProcessHeap` at `0x180007562`
- `KERNEL32!HeapFree` at `0x1800074c9`
- `KERNEL32!HeapFree` at `0x180007522`
- `KERNEL32!HeapFree` at `0x180007576`
- `KERNEL32!HeapFree` at `0x1800074c9`
- `KERNEL32!HeapFree` at `0x180007522`
- `KERNEL32!HeapFree` at `0x180007576`
- `KERNEL32!SetThreadpoolTimer` at `0x1800075ab`
- `KERNEL32!SetThreadpoolTimer` at `0x1800075eb`
- `KERNEL32!SetThreadpoolTimer` at `0x1800075ab`
- `KERNEL32!SetThreadpoolTimer` at `0x1800075eb`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800075bc`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800075fc`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800075bc`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800075fc`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800075cb`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000760b`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800075cb`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000760b`

## pseudocode

```c
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
  if ( v4 && qword_180028070 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180028070[25], qword_180028070, v4);
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
0x18000746c  mov     rax, rsp
0x18000746f  mov     [rax+8], rbx
0x180007473  mov     [rax+10h], rsi
0x180007477  mov     [rax+18h], rdi
0x18000747b  mov     [rax+20h], r14
0x18000747f  push    r15
0x180007481  sub     rsp, 20h
0x180007485  mov     rbx, rcx
0x180007488  mov     byte ptr [rcx], 0
0x18000748b  add     rcx, 30h ; '0'
0x18000748f  xor     edx, edx
0x180007491  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180007496  xor     edx, edx
0x180007498  lea     rcx, [rbx+38h]
0x18000749c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800074a1  mov     rdi, [rbx+100h]
0x1800074a8  and     qword ptr [rbx+100h], 0
0x1800074b0  test    rdi, rdi
0x1800074b3  jz      short loc_1800074D5
0x1800074b5  call    cs:__imp_GetProcessHeap
0x1800074bc  nop     dword ptr [rax+rax+00h]
0x1800074c1  mov     r8, rdi; lpMem
0x1800074c4  xor     edx, edx; dwFlags
0x1800074c6  mov     rcx, rax; hHeap
0x1800074c9  call    cs:__imp_HeapFree
0x1800074d0  nop     dword ptr [rax+rax+00h]
0x1800074d5  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800074dc  test    r8, r8
0x1800074df  jz      short loc_1800074F9
0x1800074e1  mov     rdx, cs:qword_180028070; SRWLock
0x1800074e8  test    rdx, rdx
0x1800074eb  jz      short loc_1800074F9
0x1800074ed  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800074f4  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800074f9  lea     rdi, [rbx+98h]
0x180007500  mov     rsi, [rdi+40h]
0x180007504  and     qword ptr [rdi+40h], 0
0x180007509  test    rsi, rsi
0x18000750c  jz      short loc_18000752E
0x18000750e  call    cs:__imp_GetProcessHeap
0x180007515  nop     dword ptr [rax+rax+00h]
0x18000751a  mov     r8, rsi; lpMem
0x18000751d  xor     edx, edx; dwFlags
0x18000751f  mov     rcx, rax; hHeap
0x180007522  call    cs:__imp_HeapFree
0x180007529  nop     dword ptr [rax+rax+00h]
0x18000752e  mov     rcx, rdi; lpCriticalSection
0x180007531  call    cs:__imp_DeleteCriticalSection
0x180007538  nop     dword ptr [rax+rax+00h]
0x18000753d  mov     rcx, [rbx+90h]; this
0x180007544  test    rcx, rcx
0x180007547  jz      short loc_18000754E
0x180007549  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x18000754e  mov     rsi, [rbx+88h]
0x180007555  and     qword ptr [rbx+88h], 0
0x18000755d  test    rsi, rsi
0x180007560  jz      short loc_180007582
0x180007562  call    cs:__imp_GetProcessHeap
0x180007569  nop     dword ptr [rax+rax+00h]
0x18000756e  mov     r8, rsi; lpMem
0x180007571  xor     edx, edx; dwFlags
0x180007573  mov     rcx, rax; hHeap
0x180007576  call    cs:__imp_HeapFree
0x18000757d  nop     dword ptr [rax+rax+00h]
0x180007582  lea     rcx, [rbx+48h]; lpCriticalSection
0x180007586  call    cs:__imp_DeleteCriticalSection
0x18000758d  nop     dword ptr [rax+rax+00h]
0x180007592  mov     rdi, [rbx+38h]
0x180007596  mov     esi, 1
0x18000759b  test    rdi, rdi
0x18000759e  jz      short loc_1800075D7
0x1800075a0  xor     r9d, r9d; msWindowLength
0x1800075a3  xor     r8d, r8d; msPeriod
0x1800075a6  xor     edx, edx; pftDueTime
0x1800075a8  mov     rcx, rdi; pti
0x1800075ab  call    cs:__imp_SetThreadpoolTimer
0x1800075b2  nop     dword ptr [rax+rax+00h]
0x1800075b7  mov     edx, esi; fCancelPendingCallbacks
0x1800075b9  mov     rcx, rdi; pti
0x1800075bc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800075c3  nop     dword ptr [rax+rax+00h]
0x1800075c8  mov     rcx, rdi; pti
0x1800075cb  call    cs:__imp_CloseThreadpoolTimer
0x1800075d2  nop     dword ptr [rax+rax+00h]
0x1800075d7  mov     rdi, [rbx+30h]
0x1800075db  test    rdi, rdi
0x1800075de  jz      short loc_180007617
0x1800075e0  xor     r9d, r9d; msWindowLength
0x1800075e3  xor     r8d, r8d; msPeriod
0x1800075e6  xor     edx, edx; pftDueTime
0x1800075e8  mov     rcx, rdi; pti
0x1800075eb  call    cs:__imp_SetThreadpoolTimer
0x1800075f2  nop     dword ptr [rax+rax+00h]
0x1800075f7  mov     edx, esi; fCancelPendingCallbacks
0x1800075f9  mov     rcx, rdi; pti
0x1800075fc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007603  nop     dword ptr [rax+rax+00h]
0x180007608  mov     rcx, rdi; pti
0x18000760b  call    cs:__imp_CloseThreadpoolTimer
0x180007612  nop     dword ptr [rax+rax+00h]
0x180007617  mov     rcx, [rbx+10h]; lpMem
0x18000761b  test    rcx, rcx
0x18000761e  jz      short loc_180007625
0x180007620  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180007625  mov     rbx, [rsp+28h+arg_0]
0x18000762a  mov     rsi, [rsp+28h+arg_8]
0x18000762f  mov     rdi, [rsp+28h+arg_10]
0x180007634  mov     r14, [rsp+28h+arg_18]
0x180007639  add     rsp, 20h
0x18000763d  pop     r15
0x18000763f  retn
```
