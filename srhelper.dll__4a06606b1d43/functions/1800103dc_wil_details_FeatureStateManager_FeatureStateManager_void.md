# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800103dc`
- end: `0x1800105c8`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180015ca0`

## callees

- `0x180010298`
- `0x1800103dc`
- `0x180013950`
- `0x180014420`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800103fa`
- `KERNEL32!GetLastError` at `0x180010443`
- `KERNEL32!GetLastError` at `0x1800103fa`
- `KERNEL32!GetLastError` at `0x180010443`
- `KERNEL32!DeleteCriticalSection` at `0x180010501`
- `KERNEL32!DeleteCriticalSection` at `0x180010542`
- `KERNEL32!DeleteCriticalSection` at `0x180010501`
- `KERNEL32!DeleteCriticalSection` at `0x180010542`
- `KERNEL32!SetLastError` at `0x18001042c`
- `KERNEL32!SetLastError` at `0x180010475`
- `KERNEL32!SetLastError` at `0x18001042c`
- `KERNEL32!SetLastError` at `0x180010475`
- `KERNEL32!HeapFree` at `0x1800104a8`
- `KERNEL32!HeapFree` at `0x1800104f8`
- `KERNEL32!HeapFree` at `0x180010538`
- `KERNEL32!HeapFree` at `0x1800104a8`
- `KERNEL32!HeapFree` at `0x1800104f8`
- `KERNEL32!HeapFree` at `0x180010538`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18001041b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180010464`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18001056a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18001059b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18001041b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180010464`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18001056a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18001059b`
- `KERNEL32!CloseThreadpoolTimer` at `0x180010424`
- `KERNEL32!CloseThreadpoolTimer` at `0x18001046d`
- `KERNEL32!CloseThreadpoolTimer` at `0x180010573`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800105a4`
- `KERNEL32!CloseThreadpoolTimer` at `0x180010424`
- `KERNEL32!CloseThreadpoolTimer` at `0x18001046d`
- `KERNEL32!CloseThreadpoolTimer` at `0x180010573`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800105a4`
- `KERNEL32!SetThreadpoolTimer` at `0x18001040d`
- `KERNEL32!SetThreadpoolTimer` at `0x180010456`
- `KERNEL32!SetThreadpoolTimer` at `0x18001055c`
- `KERNEL32!SetThreadpoolTimer` at `0x18001058d`
- `KERNEL32!SetThreadpoolTimer` at `0x18001040d`
- `KERNEL32!SetThreadpoolTimer` at `0x180010456`
- `KERNEL32!SetThreadpoolTimer` at `0x18001055c`
- `KERNEL32!SetThreadpoolTimer` at `0x18001058d`
- `KERNEL32!GetProcessHeap` at `0x18001049a`
- `KERNEL32!GetProcessHeap` at `0x1800104ea`
- `KERNEL32!GetProcessHeap` at `0x18001052a`
- `KERNEL32!GetProcessHeap` at `0x18001049a`
- `KERNEL32!GetProcessHeap` at `0x1800104ea`
- `KERNEL32!GetProcessHeap` at `0x18001052a`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::~FeatureStateManager(wil::details::FeatureStateManager *this)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *v4; // rsi
  DWORD v5; // ebx
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v8; // r8
  void *v9; // rsi
  HANDLE v10; // rax
  void *v11; // rsi
  HANDLE v12; // rax
  struct _TP_TIMER *v13; // rbx
  struct _TP_TIMER *v14; // rbx
  void *v15; // rcx

  *(_BYTE *)this = 0;
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v2 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 6) = 0;
  v4 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v4 )
  {
    v5 = GetLastError();
    SetThreadpoolTimer(v4, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v4, 1);
    CloseThreadpoolTimer(v4);
    SetLastError(v5);
  }
  *((_QWORD *)this + 7) = 0;
  v6 = (void *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
  v8 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)*((_QWORD *)this + 28);
  if ( v8 && qword_18001D178 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18001D178[25], qword_18001D178, v8);
  v9 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v9 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v9);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((__int64 *)this + 18);
  v11 = (void *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v11 )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v11);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v13 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v13 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 7), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v13, 1);
    CloseThreadpoolTimer(v13);
  }
  v14 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v14 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 6), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v14, 1);
    CloseThreadpoolTimer(v14);
  }
  v15 = (void *)*((_QWORD *)this + 2);
  if ( v15 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v15);
}

```

## disassembly

```asm
0x1800103dc  mov     [rsp+arg_0], rbx
0x1800103e1  mov     [rsp+arg_8], rsi
0x1800103e6  push    rdi
0x1800103e7  sub     rsp, 20h
0x1800103eb  mov     byte ptr [rcx], 0
0x1800103ee  mov     rdi, rcx
0x1800103f1  mov     rsi, [rcx+30h]
0x1800103f5  test    rsi, rsi
0x1800103f8  jz      short loc_180010432
0x1800103fa  call    cs:__imp_GetLastError
0x180010400  xor     r9d, r9d; msWindowLength
0x180010403  xor     r8d, r8d; msPeriod
0x180010406  xor     edx, edx; pftDueTime
0x180010408  mov     rcx, rsi; pti
0x18001040b  mov     ebx, eax
0x18001040d  call    cs:__imp_SetThreadpoolTimer
0x180010413  mov     edx, 1; fCancelPendingCallbacks
0x180010418  mov     rcx, rsi; pti
0x18001041b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010421  mov     rcx, rsi; pti
0x180010424  call    cs:__imp_CloseThreadpoolTimer
0x18001042a  mov     ecx, ebx; dwErrCode
0x18001042c  call    cs:__imp_SetLastError
0x180010432  mov     qword ptr [rdi+30h], 0
0x18001043a  mov     rsi, [rdi+38h]
0x18001043e  test    rsi, rsi
0x180010441  jz      short loc_18001047B
0x180010443  call    cs:__imp_GetLastError
0x180010449  xor     r9d, r9d; msWindowLength
0x18001044c  xor     r8d, r8d; msPeriod
0x18001044f  xor     edx, edx; pftDueTime
0x180010451  mov     rcx, rsi; pti
0x180010454  mov     ebx, eax
0x180010456  call    cs:__imp_SetThreadpoolTimer
0x18001045c  mov     edx, 1; fCancelPendingCallbacks
0x180010461  mov     rcx, rsi; pti
0x180010464  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001046a  mov     rcx, rsi; pti
0x18001046d  call    cs:__imp_CloseThreadpoolTimer
0x180010473  mov     ecx, ebx; dwErrCode
0x180010475  call    cs:__imp_SetLastError
0x18001047b  mov     qword ptr [rdi+38h], 0
0x180010483  mov     rbx, [rdi+100h]
0x18001048a  mov     qword ptr [rdi+100h], 0
0x180010495  test    rbx, rbx
0x180010498  jz      short loc_1800104AE
0x18001049a  call    cs:__imp_GetProcessHeap
0x1800104a0  mov     r8, rbx; lpMem
0x1800104a3  xor     edx, edx; dwFlags
0x1800104a5  mov     rcx, rax; hHeap
0x1800104a8  call    cs:__imp_HeapFree
0x1800104ae  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800104b5  test    r8, r8
0x1800104b8  jz      short loc_1800104D2
0x1800104ba  mov     rdx, cs:qword_18001D178; SRWLock
0x1800104c1  test    rdx, rdx
0x1800104c4  jz      short loc_1800104D2
0x1800104c6  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800104cd  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800104d2  lea     rbx, [rdi+98h]
0x1800104d9  mov     rsi, [rbx+40h]
0x1800104dd  mov     qword ptr [rbx+40h], 0
0x1800104e5  test    rsi, rsi
0x1800104e8  jz      short loc_1800104FE
0x1800104ea  call    cs:__imp_GetProcessHeap
0x1800104f0  mov     r8, rsi; lpMem
0x1800104f3  xor     edx, edx; dwFlags
0x1800104f5  mov     rcx, rax; hHeap
0x1800104f8  call    cs:__imp_HeapFree
0x1800104fe  mov     rcx, rbx; lpCriticalSection
0x180010501  call    cs:__imp_DeleteCriticalSection
0x180010507  lea     rcx, [rdi+90h]
0x18001050e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180010513  mov     rsi, [rdi+88h]
0x18001051a  mov     qword ptr [rdi+88h], 0
0x180010525  test    rsi, rsi
0x180010528  jz      short loc_18001053E
0x18001052a  call    cs:__imp_GetProcessHeap
0x180010530  mov     r8, rsi; lpMem
0x180010533  xor     edx, edx; dwFlags
0x180010535  mov     rcx, rax; hHeap
0x180010538  call    cs:__imp_HeapFree
0x18001053e  lea     rcx, [rdi+48h]; lpCriticalSection
0x180010542  call    cs:__imp_DeleteCriticalSection
0x180010548  mov     rbx, [rdi+38h]
0x18001054c  test    rbx, rbx
0x18001054f  jz      short loc_180010579
0x180010551  xor     r9d, r9d; msWindowLength
0x180010554  xor     r8d, r8d; msPeriod
0x180010557  xor     edx, edx; pftDueTime
0x180010559  mov     rcx, rbx; pti
0x18001055c  call    cs:__imp_SetThreadpoolTimer
0x180010562  mov     edx, 1; fCancelPendingCallbacks
0x180010567  mov     rcx, rbx; pti
0x18001056a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010570  mov     rcx, rbx; pti
0x180010573  call    cs:__imp_CloseThreadpoolTimer
0x180010579  mov     rbx, [rdi+30h]
0x18001057d  test    rbx, rbx
0x180010580  jz      short loc_1800105AA
0x180010582  xor     r9d, r9d; msWindowLength
0x180010585  xor     r8d, r8d; msPeriod
0x180010588  xor     edx, edx; pftDueTime
0x18001058a  mov     rcx, rbx; pti
0x18001058d  call    cs:__imp_SetThreadpoolTimer
0x180010593  mov     edx, 1; fCancelPendingCallbacks
0x180010598  mov     rcx, rbx; pti
0x18001059b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800105a1  mov     rcx, rbx; pti
0x1800105a4  call    cs:__imp_CloseThreadpoolTimer
0x1800105aa  mov     rcx, [rdi+10h]; lpMem
0x1800105ae  test    rcx, rcx
0x1800105b1  jz      short loc_1800105B8
0x1800105b3  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800105b8  mov     rbx, [rsp+28h+arg_0]
0x1800105bd  mov     rsi, [rsp+28h+arg_8]
0x1800105c2  add     rsp, 20h
0x1800105c6  pop     rdi
0x1800105c7  retn
```
