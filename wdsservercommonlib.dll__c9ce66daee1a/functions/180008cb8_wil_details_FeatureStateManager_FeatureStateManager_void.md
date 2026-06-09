# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180008cb8`
- end: `0x180008e8d`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `469`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18002f860`

## callees

- `0x180008cb8`
- `0x18000c54c`
- `0x18000d518`
- `0x18000d58c`
- `0x18000dc88`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180008d7d`
- `KERNEL32!DeleteCriticalSection` at `0x180008dd2`
- `KERNEL32!DeleteCriticalSection` at `0x180008d7d`
- `KERNEL32!DeleteCriticalSection` at `0x180008dd2`
- `KERNEL32!GetProcessHeap` at `0x180008d01`
- `KERNEL32!GetProcessHeap` at `0x180008d5a`
- `KERNEL32!GetProcessHeap` at `0x180008dae`
- `KERNEL32!GetProcessHeap` at `0x180008d01`
- `KERNEL32!GetProcessHeap` at `0x180008d5a`
- `KERNEL32!GetProcessHeap` at `0x180008dae`
- `KERNEL32!HeapFree` at `0x180008d15`
- `KERNEL32!HeapFree` at `0x180008d6e`
- `KERNEL32!HeapFree` at `0x180008dc2`
- `KERNEL32!HeapFree` at `0x180008d15`
- `KERNEL32!HeapFree` at `0x180008d6e`
- `KERNEL32!HeapFree` at `0x180008dc2`
- `KERNEL32!SetThreadpoolTimer` at `0x180008df7`
- `KERNEL32!SetThreadpoolTimer` at `0x180008e37`
- `KERNEL32!SetThreadpoolTimer` at `0x180008df7`
- `KERNEL32!SetThreadpoolTimer` at `0x180008e37`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180008e08`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180008e48`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180008e08`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180008e48`
- `KERNEL32!CloseThreadpoolTimer` at `0x180008e17`
- `KERNEL32!CloseThreadpoolTimer` at `0x180008e57`
- `KERNEL32!CloseThreadpoolTimer` at `0x180008e17`
- `KERNEL32!CloseThreadpoolTimer` at `0x180008e57`

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
  if ( v4 && qword_1800493B0 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800493B0[25], qword_1800493B0, v4);
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
0x180008cb8  mov     rax, rsp
0x180008cbb  mov     [rax+8], rbx
0x180008cbf  mov     [rax+10h], rsi
0x180008cc3  mov     [rax+18h], rdi
0x180008cc7  mov     [rax+20h], r14
0x180008ccb  push    r15
0x180008ccd  sub     rsp, 20h
0x180008cd1  mov     rbx, rcx
0x180008cd4  mov     byte ptr [rcx], 0
0x180008cd7  add     rcx, 30h ; '0'
0x180008cdb  xor     edx, edx
0x180008cdd  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180008ce2  xor     edx, edx
0x180008ce4  lea     rcx, [rbx+38h]
0x180008ce8  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180008ced  mov     rdi, [rbx+100h]
0x180008cf4  and     qword ptr [rbx+100h], 0
0x180008cfc  test    rdi, rdi
0x180008cff  jz      short loc_180008D21
0x180008d01  call    cs:__imp_GetProcessHeap
0x180008d08  nop     dword ptr [rax+rax+00h]
0x180008d0d  mov     r8, rdi; lpMem
0x180008d10  xor     edx, edx; dwFlags
0x180008d12  mov     rcx, rax; hHeap
0x180008d15  call    cs:__imp_HeapFree
0x180008d1c  nop     dword ptr [rax+rax+00h]
0x180008d21  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180008d28  test    r8, r8
0x180008d2b  jz      short loc_180008D45
0x180008d2d  mov     rdx, cs:qword_1800493B0; SRWLock
0x180008d34  test    rdx, rdx
0x180008d37  jz      short loc_180008D45
0x180008d39  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180008d40  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180008d45  lea     rdi, [rbx+98h]
0x180008d4c  mov     rsi, [rdi+40h]
0x180008d50  and     qword ptr [rdi+40h], 0
0x180008d55  test    rsi, rsi
0x180008d58  jz      short loc_180008D7A
0x180008d5a  call    cs:__imp_GetProcessHeap
0x180008d61  nop     dword ptr [rax+rax+00h]
0x180008d66  mov     r8, rsi; lpMem
0x180008d69  xor     edx, edx; dwFlags
0x180008d6b  mov     rcx, rax; hHeap
0x180008d6e  call    cs:__imp_HeapFree
0x180008d75  nop     dword ptr [rax+rax+00h]
0x180008d7a  mov     rcx, rdi; lpCriticalSection
0x180008d7d  call    cs:__imp_DeleteCriticalSection
0x180008d84  nop     dword ptr [rax+rax+00h]
0x180008d89  mov     rcx, [rbx+90h]; this
0x180008d90  test    rcx, rcx
0x180008d93  jz      short loc_180008D9A
0x180008d95  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x180008d9a  mov     rsi, [rbx+88h]
0x180008da1  and     qword ptr [rbx+88h], 0
0x180008da9  test    rsi, rsi
0x180008dac  jz      short loc_180008DCE
0x180008dae  call    cs:__imp_GetProcessHeap
0x180008db5  nop     dword ptr [rax+rax+00h]
0x180008dba  mov     r8, rsi; lpMem
0x180008dbd  xor     edx, edx; dwFlags
0x180008dbf  mov     rcx, rax; hHeap
0x180008dc2  call    cs:__imp_HeapFree
0x180008dc9  nop     dword ptr [rax+rax+00h]
0x180008dce  lea     rcx, [rbx+48h]; lpCriticalSection
0x180008dd2  call    cs:__imp_DeleteCriticalSection
0x180008dd9  nop     dword ptr [rax+rax+00h]
0x180008dde  mov     rdi, [rbx+38h]
0x180008de2  mov     esi, 1
0x180008de7  test    rdi, rdi
0x180008dea  jz      short loc_180008E23
0x180008dec  xor     r9d, r9d; msWindowLength
0x180008def  xor     r8d, r8d; msPeriod
0x180008df2  xor     edx, edx; pftDueTime
0x180008df4  mov     rcx, rdi; pti
0x180008df7  call    cs:__imp_SetThreadpoolTimer
0x180008dfe  nop     dword ptr [rax+rax+00h]
0x180008e03  mov     edx, esi; fCancelPendingCallbacks
0x180008e05  mov     rcx, rdi; pti
0x180008e08  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008e0f  nop     dword ptr [rax+rax+00h]
0x180008e14  mov     rcx, rdi; pti
0x180008e17  call    cs:__imp_CloseThreadpoolTimer
0x180008e1e  nop     dword ptr [rax+rax+00h]
0x180008e23  mov     rdi, [rbx+30h]
0x180008e27  test    rdi, rdi
0x180008e2a  jz      short loc_180008E63
0x180008e2c  xor     r9d, r9d; msWindowLength
0x180008e2f  xor     r8d, r8d; msPeriod
0x180008e32  xor     edx, edx; pftDueTime
0x180008e34  mov     rcx, rdi; pti
0x180008e37  call    cs:__imp_SetThreadpoolTimer
0x180008e3e  nop     dword ptr [rax+rax+00h]
0x180008e43  mov     edx, esi; fCancelPendingCallbacks
0x180008e45  mov     rcx, rdi; pti
0x180008e48  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008e4f  nop     dword ptr [rax+rax+00h]
0x180008e54  mov     rcx, rdi; pti
0x180008e57  call    cs:__imp_CloseThreadpoolTimer
0x180008e5e  nop     dword ptr [rax+rax+00h]
0x180008e63  mov     rcx, [rbx+10h]; lpMem
0x180008e67  test    rcx, rcx
0x180008e6a  jz      short loc_180008E71
0x180008e6c  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180008e71  mov     rbx, [rsp+28h+arg_0]
0x180008e76  mov     rsi, [rsp+28h+arg_8]
0x180008e7b  mov     rdi, [rsp+28h+arg_10]
0x180008e80  mov     r14, [rsp+28h+arg_18]
0x180008e85  add     rsp, 20h
0x180008e89  pop     r15
0x180008e8b  retn
```
