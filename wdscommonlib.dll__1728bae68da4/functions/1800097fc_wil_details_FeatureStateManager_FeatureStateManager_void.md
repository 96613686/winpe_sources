# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800097fc`
- end: `0x1800099d1`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `469`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800308e0`

## callees

- `0x1800097fc`
- `0x18000d08c`
- `0x18000e058`
- `0x18000e0cc`
- `0x18000e7c8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800098c1`
- `KERNEL32!DeleteCriticalSection` at `0x180009916`
- `KERNEL32!DeleteCriticalSection` at `0x1800098c1`
- `KERNEL32!DeleteCriticalSection` at `0x180009916`
- `KERNEL32!GetProcessHeap` at `0x180009845`
- `KERNEL32!GetProcessHeap` at `0x18000989e`
- `KERNEL32!GetProcessHeap` at `0x1800098f2`
- `KERNEL32!GetProcessHeap` at `0x180009845`
- `KERNEL32!GetProcessHeap` at `0x18000989e`
- `KERNEL32!GetProcessHeap` at `0x1800098f2`
- `KERNEL32!HeapFree` at `0x180009859`
- `KERNEL32!HeapFree` at `0x1800098b2`
- `KERNEL32!HeapFree` at `0x180009906`
- `KERNEL32!HeapFree` at `0x180009859`
- `KERNEL32!HeapFree` at `0x1800098b2`
- `KERNEL32!HeapFree` at `0x180009906`
- `KERNEL32!SetThreadpoolTimer` at `0x18000993b`
- `KERNEL32!SetThreadpoolTimer` at `0x18000997b`
- `KERNEL32!SetThreadpoolTimer` at `0x18000993b`
- `KERNEL32!SetThreadpoolTimer` at `0x18000997b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000994c`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000998c`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000994c`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000998c`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000995b`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000999b`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000995b`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000999b`

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
  if ( v4 && qword_18004B3D0 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18004B3D0[25], qword_18004B3D0, v4);
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
0x1800097fc  mov     rax, rsp
0x1800097ff  mov     [rax+8], rbx
0x180009803  mov     [rax+10h], rsi
0x180009807  mov     [rax+18h], rdi
0x18000980b  mov     [rax+20h], r14
0x18000980f  push    r15
0x180009811  sub     rsp, 20h
0x180009815  mov     rbx, rcx
0x180009818  mov     byte ptr [rcx], 0
0x18000981b  add     rcx, 30h ; '0'
0x18000981f  xor     edx, edx
0x180009821  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180009826  xor     edx, edx
0x180009828  lea     rcx, [rbx+38h]
0x18000982c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180009831  mov     rdi, [rbx+100h]
0x180009838  and     qword ptr [rbx+100h], 0
0x180009840  test    rdi, rdi
0x180009843  jz      short loc_180009865
0x180009845  call    cs:__imp_GetProcessHeap
0x18000984c  nop     dword ptr [rax+rax+00h]
0x180009851  mov     r8, rdi; lpMem
0x180009854  xor     edx, edx; dwFlags
0x180009856  mov     rcx, rax; hHeap
0x180009859  call    cs:__imp_HeapFree
0x180009860  nop     dword ptr [rax+rax+00h]
0x180009865  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18000986c  test    r8, r8
0x18000986f  jz      short loc_180009889
0x180009871  mov     rdx, cs:qword_18004B3D0; SRWLock
0x180009878  test    rdx, rdx
0x18000987b  jz      short loc_180009889
0x18000987d  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180009884  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180009889  lea     rdi, [rbx+98h]
0x180009890  mov     rsi, [rdi+40h]
0x180009894  and     qword ptr [rdi+40h], 0
0x180009899  test    rsi, rsi
0x18000989c  jz      short loc_1800098BE
0x18000989e  call    cs:__imp_GetProcessHeap
0x1800098a5  nop     dword ptr [rax+rax+00h]
0x1800098aa  mov     r8, rsi; lpMem
0x1800098ad  xor     edx, edx; dwFlags
0x1800098af  mov     rcx, rax; hHeap
0x1800098b2  call    cs:__imp_HeapFree
0x1800098b9  nop     dword ptr [rax+rax+00h]
0x1800098be  mov     rcx, rdi; lpCriticalSection
0x1800098c1  call    cs:__imp_DeleteCriticalSection
0x1800098c8  nop     dword ptr [rax+rax+00h]
0x1800098cd  mov     rcx, [rbx+90h]; this
0x1800098d4  test    rcx, rcx
0x1800098d7  jz      short loc_1800098DE
0x1800098d9  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x1800098de  mov     rsi, [rbx+88h]
0x1800098e5  and     qword ptr [rbx+88h], 0
0x1800098ed  test    rsi, rsi
0x1800098f0  jz      short loc_180009912
0x1800098f2  call    cs:__imp_GetProcessHeap
0x1800098f9  nop     dword ptr [rax+rax+00h]
0x1800098fe  mov     r8, rsi; lpMem
0x180009901  xor     edx, edx; dwFlags
0x180009903  mov     rcx, rax; hHeap
0x180009906  call    cs:__imp_HeapFree
0x18000990d  nop     dword ptr [rax+rax+00h]
0x180009912  lea     rcx, [rbx+48h]; lpCriticalSection
0x180009916  call    cs:__imp_DeleteCriticalSection
0x18000991d  nop     dword ptr [rax+rax+00h]
0x180009922  mov     rdi, [rbx+38h]
0x180009926  mov     esi, 1
0x18000992b  test    rdi, rdi
0x18000992e  jz      short loc_180009967
0x180009930  xor     r9d, r9d; msWindowLength
0x180009933  xor     r8d, r8d; msPeriod
0x180009936  xor     edx, edx; pftDueTime
0x180009938  mov     rcx, rdi; pti
0x18000993b  call    cs:__imp_SetThreadpoolTimer
0x180009942  nop     dword ptr [rax+rax+00h]
0x180009947  mov     edx, esi; fCancelPendingCallbacks
0x180009949  mov     rcx, rdi; pti
0x18000994c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009953  nop     dword ptr [rax+rax+00h]
0x180009958  mov     rcx, rdi; pti
0x18000995b  call    cs:__imp_CloseThreadpoolTimer
0x180009962  nop     dword ptr [rax+rax+00h]
0x180009967  mov     rdi, [rbx+30h]
0x18000996b  test    rdi, rdi
0x18000996e  jz      short loc_1800099A7
0x180009970  xor     r9d, r9d; msWindowLength
0x180009973  xor     r8d, r8d; msPeriod
0x180009976  xor     edx, edx; pftDueTime
0x180009978  mov     rcx, rdi; pti
0x18000997b  call    cs:__imp_SetThreadpoolTimer
0x180009982  nop     dword ptr [rax+rax+00h]
0x180009987  mov     edx, esi; fCancelPendingCallbacks
0x180009989  mov     rcx, rdi; pti
0x18000998c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009993  nop     dword ptr [rax+rax+00h]
0x180009998  mov     rcx, rdi; pti
0x18000999b  call    cs:__imp_CloseThreadpoolTimer
0x1800099a2  nop     dword ptr [rax+rax+00h]
0x1800099a7  mov     rcx, [rbx+10h]; lpMem
0x1800099ab  test    rcx, rcx
0x1800099ae  jz      short loc_1800099B5
0x1800099b0  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800099b5  mov     rbx, [rsp+28h+arg_0]
0x1800099ba  mov     rsi, [rsp+28h+arg_8]
0x1800099bf  mov     rdi, [rsp+28h+arg_10]
0x1800099c4  mov     r14, [rsp+28h+arg_18]
0x1800099c9  add     rsp, 20h
0x1800099cd  pop     r15
0x1800099cf  retn
```
