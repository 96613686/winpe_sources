# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180003694`
- end: `0x180003869`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `469`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000dc70`

## callees

- `0x180003694`
- `0x1800097c8`
- `0x18000b2c8`
- `0x18000b33c`
- `0x18000ba50`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800036f1`
- `KERNEL32!HeapFree` at `0x18000374a`
- `KERNEL32!HeapFree` at `0x18000379e`
- `KERNEL32!HeapFree` at `0x1800036f1`
- `KERNEL32!HeapFree` at `0x18000374a`
- `KERNEL32!HeapFree` at `0x18000379e`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800037e4`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003824`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800037e4`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003824`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800037f3`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003833`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800037f3`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003833`
- `KERNEL32!SetThreadpoolTimer` at `0x1800037d3`
- `KERNEL32!SetThreadpoolTimer` at `0x180003813`
- `KERNEL32!SetThreadpoolTimer` at `0x1800037d3`
- `KERNEL32!SetThreadpoolTimer` at `0x180003813`
- `KERNEL32!DeleteCriticalSection` at `0x180003759`
- `KERNEL32!DeleteCriticalSection` at `0x1800037ae`
- `KERNEL32!DeleteCriticalSection` at `0x180003759`
- `KERNEL32!DeleteCriticalSection` at `0x1800037ae`
- `KERNEL32!GetProcessHeap` at `0x1800036dd`
- `KERNEL32!GetProcessHeap` at `0x180003736`
- `KERNEL32!GetProcessHeap` at `0x18000378a`
- `KERNEL32!GetProcessHeap` at `0x1800036dd`
- `KERNEL32!GetProcessHeap` at `0x180003736`
- `KERNEL32!GetProcessHeap` at `0x18000378a`

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
  if ( v4 && SRWLock )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&SRWLock[25], SRWLock, v4);
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
0x180003694  mov     rax, rsp
0x180003697  mov     [rax+8], rbx
0x18000369b  mov     [rax+10h], rsi
0x18000369f  mov     [rax+18h], rdi
0x1800036a3  mov     [rax+20h], r14
0x1800036a7  push    r15
0x1800036a9  sub     rsp, 20h
0x1800036ad  mov     rbx, rcx
0x1800036b0  mov     byte ptr [rcx], 0
0x1800036b3  add     rcx, 30h ; '0'
0x1800036b7  xor     edx, edx
0x1800036b9  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800036be  xor     edx, edx
0x1800036c0  lea     rcx, [rbx+38h]
0x1800036c4  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800036c9  mov     rdi, [rbx+100h]
0x1800036d0  and     qword ptr [rbx+100h], 0
0x1800036d8  test    rdi, rdi
0x1800036db  jz      short loc_1800036FD
0x1800036dd  call    cs:__imp_GetProcessHeap
0x1800036e4  nop     dword ptr [rax+rax+00h]
0x1800036e9  mov     r8, rdi; lpMem
0x1800036ec  xor     edx, edx; dwFlags
0x1800036ee  mov     rcx, rax; hHeap
0x1800036f1  call    cs:__imp_HeapFree
0x1800036f8  nop     dword ptr [rax+rax+00h]
0x1800036fd  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180003704  test    r8, r8
0x180003707  jz      short loc_180003721
0x180003709  mov     rdx, cs:SRWLock; SRWLock
0x180003710  test    rdx, rdx
0x180003713  jz      short loc_180003721
0x180003715  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000371c  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180003721  lea     rdi, [rbx+98h]
0x180003728  mov     rsi, [rdi+40h]
0x18000372c  and     qword ptr [rdi+40h], 0
0x180003731  test    rsi, rsi
0x180003734  jz      short loc_180003756
0x180003736  call    cs:__imp_GetProcessHeap
0x18000373d  nop     dword ptr [rax+rax+00h]
0x180003742  mov     r8, rsi; lpMem
0x180003745  xor     edx, edx; dwFlags
0x180003747  mov     rcx, rax; hHeap
0x18000374a  call    cs:__imp_HeapFree
0x180003751  nop     dword ptr [rax+rax+00h]
0x180003756  mov     rcx, rdi; lpCriticalSection
0x180003759  call    cs:__imp_DeleteCriticalSection
0x180003760  nop     dword ptr [rax+rax+00h]
0x180003765  mov     rcx, [rbx+90h]; this
0x18000376c  test    rcx, rcx
0x18000376f  jz      short loc_180003776
0x180003771  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x180003776  mov     rsi, [rbx+88h]
0x18000377d  and     qword ptr [rbx+88h], 0
0x180003785  test    rsi, rsi
0x180003788  jz      short loc_1800037AA
0x18000378a  call    cs:__imp_GetProcessHeap
0x180003791  nop     dword ptr [rax+rax+00h]
0x180003796  mov     r8, rsi; lpMem
0x180003799  xor     edx, edx; dwFlags
0x18000379b  mov     rcx, rax; hHeap
0x18000379e  call    cs:__imp_HeapFree
0x1800037a5  nop     dword ptr [rax+rax+00h]
0x1800037aa  lea     rcx, [rbx+48h]; lpCriticalSection
0x1800037ae  call    cs:__imp_DeleteCriticalSection
0x1800037b5  nop     dword ptr [rax+rax+00h]
0x1800037ba  mov     rdi, [rbx+38h]
0x1800037be  mov     esi, 1
0x1800037c3  test    rdi, rdi
0x1800037c6  jz      short loc_1800037FF
0x1800037c8  xor     r9d, r9d; msWindowLength
0x1800037cb  xor     r8d, r8d; msPeriod
0x1800037ce  xor     edx, edx; pftDueTime
0x1800037d0  mov     rcx, rdi; pti
0x1800037d3  call    cs:__imp_SetThreadpoolTimer
0x1800037da  nop     dword ptr [rax+rax+00h]
0x1800037df  mov     edx, esi; fCancelPendingCallbacks
0x1800037e1  mov     rcx, rdi; pti
0x1800037e4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800037eb  nop     dword ptr [rax+rax+00h]
0x1800037f0  mov     rcx, rdi; pti
0x1800037f3  call    cs:__imp_CloseThreadpoolTimer
0x1800037fa  nop     dword ptr [rax+rax+00h]
0x1800037ff  mov     rdi, [rbx+30h]
0x180003803  test    rdi, rdi
0x180003806  jz      short loc_18000383F
0x180003808  xor     r9d, r9d; msWindowLength
0x18000380b  xor     r8d, r8d; msPeriod
0x18000380e  xor     edx, edx; pftDueTime
0x180003810  mov     rcx, rdi; pti
0x180003813  call    cs:__imp_SetThreadpoolTimer
0x18000381a  nop     dword ptr [rax+rax+00h]
0x18000381f  mov     edx, esi; fCancelPendingCallbacks
0x180003821  mov     rcx, rdi; pti
0x180003824  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000382b  nop     dword ptr [rax+rax+00h]
0x180003830  mov     rcx, rdi; pti
0x180003833  call    cs:__imp_CloseThreadpoolTimer
0x18000383a  nop     dword ptr [rax+rax+00h]
0x18000383f  mov     rcx, [rbx+10h]; lpMem
0x180003843  test    rcx, rcx
0x180003846  jz      short loc_18000384D
0x180003848  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18000384d  mov     rbx, [rsp+28h+arg_0]
0x180003852  mov     rsi, [rsp+28h+arg_8]
0x180003857  mov     rdi, [rsp+28h+arg_10]
0x18000385c  mov     r14, [rsp+28h+arg_18]
0x180003861  add     rsp, 20h
0x180003865  pop     r15
0x180003867  retn
```
