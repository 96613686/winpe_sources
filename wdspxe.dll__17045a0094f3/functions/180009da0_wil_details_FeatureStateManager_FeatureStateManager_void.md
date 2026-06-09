# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180009da0`
- end: `0x180009f75`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `469`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800120c0`

## callees

- `0x180009da0`
- `0x18000e7dc`
- `0x1800103e0`
- `0x180010454`
- `0x180010c80`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180009e65`
- `KERNEL32!DeleteCriticalSection` at `0x180009eba`
- `KERNEL32!DeleteCriticalSection` at `0x180009e65`
- `KERNEL32!DeleteCriticalSection` at `0x180009eba`
- `KERNEL32!GetProcessHeap` at `0x180009de9`
- `KERNEL32!GetProcessHeap` at `0x180009e42`
- `KERNEL32!GetProcessHeap` at `0x180009e96`
- `KERNEL32!GetProcessHeap` at `0x180009de9`
- `KERNEL32!GetProcessHeap` at `0x180009e42`
- `KERNEL32!GetProcessHeap` at `0x180009e96`
- `KERNEL32!HeapFree` at `0x180009dfd`
- `KERNEL32!HeapFree` at `0x180009e56`
- `KERNEL32!HeapFree` at `0x180009eaa`
- `KERNEL32!HeapFree` at `0x180009dfd`
- `KERNEL32!HeapFree` at `0x180009e56`
- `KERNEL32!HeapFree` at `0x180009eaa`
- `KERNEL32!SetThreadpoolTimer` at `0x180009edf`
- `KERNEL32!SetThreadpoolTimer` at `0x180009f1f`
- `KERNEL32!SetThreadpoolTimer` at `0x180009edf`
- `KERNEL32!SetThreadpoolTimer` at `0x180009f1f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180009ef0`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180009f30`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180009ef0`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180009f30`
- `KERNEL32!CloseThreadpoolTimer` at `0x180009eff`
- `KERNEL32!CloseThreadpoolTimer` at `0x180009f3f`
- `KERNEL32!CloseThreadpoolTimer` at `0x180009eff`
- `KERNEL32!CloseThreadpoolTimer` at `0x180009f3f`

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
0x180009da0  mov     rax, rsp
0x180009da3  mov     [rax+8], rbx
0x180009da7  mov     [rax+10h], rsi
0x180009dab  mov     [rax+18h], rdi
0x180009daf  mov     [rax+20h], r14
0x180009db3  push    r15
0x180009db5  sub     rsp, 20h
0x180009db9  mov     rbx, rcx
0x180009dbc  mov     byte ptr [rcx], 0
0x180009dbf  add     rcx, 30h ; '0'
0x180009dc3  xor     edx, edx
0x180009dc5  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180009dca  xor     edx, edx
0x180009dcc  lea     rcx, [rbx+38h]
0x180009dd0  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180009dd5  mov     rdi, [rbx+100h]
0x180009ddc  and     qword ptr [rbx+100h], 0
0x180009de4  test    rdi, rdi
0x180009de7  jz      short loc_180009E09
0x180009de9  call    cs:__imp_GetProcessHeap
0x180009df0  nop     dword ptr [rax+rax+00h]
0x180009df5  mov     r8, rdi; lpMem
0x180009df8  xor     edx, edx; dwFlags
0x180009dfa  mov     rcx, rax; hHeap
0x180009dfd  call    cs:__imp_HeapFree
0x180009e04  nop     dword ptr [rax+rax+00h]
0x180009e09  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180009e10  test    r8, r8
0x180009e13  jz      short loc_180009E2D
0x180009e15  mov     rdx, cs:SRWLock; SRWLock
0x180009e1c  test    rdx, rdx
0x180009e1f  jz      short loc_180009E2D
0x180009e21  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180009e28  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180009e2d  lea     rdi, [rbx+98h]
0x180009e34  mov     rsi, [rdi+40h]
0x180009e38  and     qword ptr [rdi+40h], 0
0x180009e3d  test    rsi, rsi
0x180009e40  jz      short loc_180009E62
0x180009e42  call    cs:__imp_GetProcessHeap
0x180009e49  nop     dword ptr [rax+rax+00h]
0x180009e4e  mov     r8, rsi; lpMem
0x180009e51  xor     edx, edx; dwFlags
0x180009e53  mov     rcx, rax; hHeap
0x180009e56  call    cs:__imp_HeapFree
0x180009e5d  nop     dword ptr [rax+rax+00h]
0x180009e62  mov     rcx, rdi; lpCriticalSection
0x180009e65  call    cs:__imp_DeleteCriticalSection
0x180009e6c  nop     dword ptr [rax+rax+00h]
0x180009e71  mov     rcx, [rbx+90h]; this
0x180009e78  test    rcx, rcx
0x180009e7b  jz      short loc_180009E82
0x180009e7d  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x180009e82  mov     rsi, [rbx+88h]
0x180009e89  and     qword ptr [rbx+88h], 0
0x180009e91  test    rsi, rsi
0x180009e94  jz      short loc_180009EB6
0x180009e96  call    cs:__imp_GetProcessHeap
0x180009e9d  nop     dword ptr [rax+rax+00h]
0x180009ea2  mov     r8, rsi; lpMem
0x180009ea5  xor     edx, edx; dwFlags
0x180009ea7  mov     rcx, rax; hHeap
0x180009eaa  call    cs:__imp_HeapFree
0x180009eb1  nop     dword ptr [rax+rax+00h]
0x180009eb6  lea     rcx, [rbx+48h]; lpCriticalSection
0x180009eba  call    cs:__imp_DeleteCriticalSection
0x180009ec1  nop     dword ptr [rax+rax+00h]
0x180009ec6  mov     rdi, [rbx+38h]
0x180009eca  mov     esi, 1
0x180009ecf  test    rdi, rdi
0x180009ed2  jz      short loc_180009F0B
0x180009ed4  xor     r9d, r9d; msWindowLength
0x180009ed7  xor     r8d, r8d; msPeriod
0x180009eda  xor     edx, edx; pftDueTime
0x180009edc  mov     rcx, rdi; pti
0x180009edf  call    cs:__imp_SetThreadpoolTimer
0x180009ee6  nop     dword ptr [rax+rax+00h]
0x180009eeb  mov     edx, esi; fCancelPendingCallbacks
0x180009eed  mov     rcx, rdi; pti
0x180009ef0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009ef7  nop     dword ptr [rax+rax+00h]
0x180009efc  mov     rcx, rdi; pti
0x180009eff  call    cs:__imp_CloseThreadpoolTimer
0x180009f06  nop     dword ptr [rax+rax+00h]
0x180009f0b  mov     rdi, [rbx+30h]
0x180009f0f  test    rdi, rdi
0x180009f12  jz      short loc_180009F4B
0x180009f14  xor     r9d, r9d; msWindowLength
0x180009f17  xor     r8d, r8d; msPeriod
0x180009f1a  xor     edx, edx; pftDueTime
0x180009f1c  mov     rcx, rdi; pti
0x180009f1f  call    cs:__imp_SetThreadpoolTimer
0x180009f26  nop     dword ptr [rax+rax+00h]
0x180009f2b  mov     edx, esi; fCancelPendingCallbacks
0x180009f2d  mov     rcx, rdi; pti
0x180009f30  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009f37  nop     dword ptr [rax+rax+00h]
0x180009f3c  mov     rcx, rdi; pti
0x180009f3f  call    cs:__imp_CloseThreadpoolTimer
0x180009f46  nop     dword ptr [rax+rax+00h]
0x180009f4b  mov     rcx, [rbx+10h]; lpMem
0x180009f4f  test    rcx, rcx
0x180009f52  jz      short loc_180009F59
0x180009f54  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180009f59  mov     rbx, [rsp+28h+arg_0]
0x180009f5e  mov     rsi, [rsp+28h+arg_8]
0x180009f63  mov     rdi, [rsp+28h+arg_10]
0x180009f68  mov     r14, [rsp+28h+arg_18]
0x180009f6d  add     rsp, 20h
0x180009f71  pop     r15
0x180009f73  retn
```
