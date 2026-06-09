# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180006884`
- end: `0x180006a48`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `452`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180081690`

## callees

- `0x180006884`
- `0x18000bc8c`
- `0x18000d42c`
- `0x18000d4a0`
- `0x18000eb30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006942`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000699a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006942`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000699a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000691f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006976`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000691f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006976`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800068d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006933`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000698a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800068d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006933`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000698a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800069df`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006a1f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800069df`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006a1f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800069bf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800069ff`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800069bf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800069ff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800069d0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006a10`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800069d0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006a10`

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
  if ( v4 && qword_1800B3C90 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800B3C90[25], qword_1800B3C90, v4);
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
0x180006884  push    rbx
0x180006886  push    rsi
0x180006887  push    rdi
0x180006888  push    r14
0x18000688a  push    r15
0x18000688c  sub     rsp, 20h
0x180006890  mov     rbx, rcx
0x180006893  mov     byte ptr [rcx], 0
0x180006896  xor     edx, edx
0x180006898  add     rcx, 30h ; '0'
0x18000689c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800068a1  xor     edx, edx
0x1800068a3  lea     rcx, [rbx+38h]
0x1800068a7  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800068ac  mov     rdi, [rbx+100h]
0x1800068b3  mov     qword ptr [rbx+100h], 0
0x1800068be  test    rdi, rdi
0x1800068c1  jz      short loc_1800068E3
0x1800068c3  call    cs:__imp_GetProcessHeap
0x1800068ca  nop     dword ptr [rax+rax+00h]
0x1800068cf  mov     rcx, rax; hHeap
0x1800068d2  mov     r8, rdi; lpMem
0x1800068d5  xor     edx, edx; dwFlags
0x1800068d7  call    cs:__imp_HeapFree
0x1800068de  nop     dword ptr [rax+rax+00h]
0x1800068e3  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800068ea  test    r8, r8
0x1800068ed  jz      short loc_180006907
0x1800068ef  mov     rdx, cs:qword_1800B3C90; SRWLock
0x1800068f6  test    rdx, rdx
0x1800068f9  jz      short loc_180006907
0x1800068fb  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180006902  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180006907  lea     rdi, [rbx+98h]
0x18000690e  mov     rsi, [rdi+40h]
0x180006912  mov     qword ptr [rdi+40h], 0
0x18000691a  test    rsi, rsi
0x18000691d  jz      short loc_18000693F
0x18000691f  call    cs:__imp_GetProcessHeap
0x180006926  nop     dword ptr [rax+rax+00h]
0x18000692b  mov     rcx, rax; hHeap
0x18000692e  mov     r8, rsi; lpMem
0x180006931  xor     edx, edx; dwFlags
0x180006933  call    cs:__imp_HeapFree
0x18000693a  nop     dword ptr [rax+rax+00h]
0x18000693f  mov     rcx, rdi; lpCriticalSection
0x180006942  call    cs:__imp_DeleteCriticalSection
0x180006949  nop     dword ptr [rax+rax+00h]
0x18000694e  mov     rcx, [rbx+90h]; this
0x180006955  test    rcx, rcx
0x180006958  jz      short loc_18000695F
0x18000695a  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x18000695f  mov     rsi, [rbx+88h]
0x180006966  mov     qword ptr [rbx+88h], 0
0x180006971  test    rsi, rsi
0x180006974  jz      short loc_180006996
0x180006976  call    cs:__imp_GetProcessHeap
0x18000697d  nop     dword ptr [rax+rax+00h]
0x180006982  mov     rcx, rax; hHeap
0x180006985  mov     r8, rsi; lpMem
0x180006988  xor     edx, edx; dwFlags
0x18000698a  call    cs:__imp_HeapFree
0x180006991  nop     dword ptr [rax+rax+00h]
0x180006996  lea     rcx, [rbx+48h]; lpCriticalSection
0x18000699a  call    cs:__imp_DeleteCriticalSection
0x1800069a1  nop     dword ptr [rax+rax+00h]
0x1800069a6  mov     rdi, [rbx+38h]
0x1800069aa  mov     esi, 1
0x1800069af  test    rdi, rdi
0x1800069b2  jz      short loc_1800069EB
0x1800069b4  xor     r9d, r9d; msWindowLength
0x1800069b7  xor     r8d, r8d; msPeriod
0x1800069ba  xor     edx, edx; pftDueTime
0x1800069bc  mov     rcx, rdi; pti
0x1800069bf  call    cs:__imp_SetThreadpoolTimer
0x1800069c6  nop     dword ptr [rax+rax+00h]
0x1800069cb  mov     edx, esi; fCancelPendingCallbacks
0x1800069cd  mov     rcx, rdi; pti
0x1800069d0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800069d7  nop     dword ptr [rax+rax+00h]
0x1800069dc  mov     rcx, rdi; pti
0x1800069df  call    cs:__imp_CloseThreadpoolTimer
0x1800069e6  nop     dword ptr [rax+rax+00h]
0x1800069eb  mov     rdi, [rbx+30h]
0x1800069ef  test    rdi, rdi
0x1800069f2  jz      short loc_180006A2C
0x1800069f4  xor     r9d, r9d; msWindowLength
0x1800069f7  xor     r8d, r8d; msPeriod
0x1800069fa  xor     edx, edx; pftDueTime
0x1800069fc  mov     rcx, rdi; pti
0x1800069ff  call    cs:__imp_SetThreadpoolTimer
0x180006a06  nop     dword ptr [rax+rax+00h]
0x180006a0b  mov     edx, esi; fCancelPendingCallbacks
0x180006a0d  mov     rcx, rdi; pti
0x180006a10  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006a17  nop     dword ptr [rax+rax+00h]
0x180006a1c  mov     rcx, rdi; pti
0x180006a1f  call    cs:__imp_CloseThreadpoolTimer
0x180006a26  nop     dword ptr [rax+rax+00h]
0x180006a2b  nop
0x180006a2c  mov     rcx, [rbx+10h]; lpMem
0x180006a30  test    rcx, rcx
0x180006a33  jz      short loc_180006A3B
0x180006a35  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180006a3a  nop
0x180006a3b  add     rsp, 20h
0x180006a3f  pop     r15
0x180006a41  pop     r14
0x180006a43  pop     rdi
0x180006a44  pop     rsi
0x180006a45  pop     rbx
0x180006a46  retn
```
