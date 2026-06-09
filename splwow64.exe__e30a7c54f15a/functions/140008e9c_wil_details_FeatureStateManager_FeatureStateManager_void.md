# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x140008e9c`
- end: `0x140009088`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400157b0`

## callees

- `0x140008c0c`
- `0x140008e9c`
- `0x14000b430`
- `0x14000bd58`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140008f68`
- `KERNEL32!HeapFree` at `0x140008fb8`
- `KERNEL32!HeapFree` at `0x140008ff8`
- `KERNEL32!HeapFree` at `0x140008f68`
- `KERNEL32!HeapFree` at `0x140008fb8`
- `KERNEL32!HeapFree` at `0x140008ff8`
- `KERNEL32!SetLastError` at `0x140008eec`
- `KERNEL32!SetLastError` at `0x140008f35`
- `KERNEL32!SetLastError` at `0x140008eec`
- `KERNEL32!SetLastError` at `0x140008f35`
- `KERNEL32!GetLastError` at `0x140008eba`
- `KERNEL32!GetLastError` at `0x140008f03`
- `KERNEL32!GetLastError` at `0x140008eba`
- `KERNEL32!GetLastError` at `0x140008f03`
- `KERNEL32!DeleteCriticalSection` at `0x140008fc1`
- `KERNEL32!DeleteCriticalSection` at `0x140009002`
- `KERNEL32!DeleteCriticalSection` at `0x140008fc1`
- `KERNEL32!DeleteCriticalSection` at `0x140009002`
- `KERNEL32!GetProcessHeap` at `0x140008f5a`
- `KERNEL32!GetProcessHeap` at `0x140008faa`
- `KERNEL32!GetProcessHeap` at `0x140008fea`
- `KERNEL32!GetProcessHeap` at `0x140008f5a`
- `KERNEL32!GetProcessHeap` at `0x140008faa`
- `KERNEL32!GetProcessHeap` at `0x140008fea`
- `KERNEL32!SetThreadpoolTimer` at `0x140008ecd`
- `KERNEL32!SetThreadpoolTimer` at `0x140008f16`
- `KERNEL32!SetThreadpoolTimer` at `0x14000901c`
- `KERNEL32!SetThreadpoolTimer` at `0x14000904d`
- `KERNEL32!SetThreadpoolTimer` at `0x140008ecd`
- `KERNEL32!SetThreadpoolTimer` at `0x140008f16`
- `KERNEL32!SetThreadpoolTimer` at `0x14000901c`
- `KERNEL32!SetThreadpoolTimer` at `0x14000904d`
- `KERNEL32!CloseThreadpoolTimer` at `0x140008ee4`
- `KERNEL32!CloseThreadpoolTimer` at `0x140008f2d`
- `KERNEL32!CloseThreadpoolTimer` at `0x140009033`
- `KERNEL32!CloseThreadpoolTimer` at `0x140009064`
- `KERNEL32!CloseThreadpoolTimer` at `0x140008ee4`
- `KERNEL32!CloseThreadpoolTimer` at `0x140008f2d`
- `KERNEL32!CloseThreadpoolTimer` at `0x140009033`
- `KERNEL32!CloseThreadpoolTimer` at `0x140009064`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140008edb`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140008f24`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000902a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000905b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140008edb`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140008f24`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000902a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000905b`

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
  void *v8; // r8
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
  v8 = (void *)*((_QWORD *)this + 28);
  if ( v8 && qword_140021168 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_140021168[25], qword_140021168, v8);
  v9 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v9 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v9);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((char *)this + 144);
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
0x140008e9c  mov     [rsp+arg_0], rbx
0x140008ea1  mov     [rsp+arg_8], rsi
0x140008ea6  push    rdi
0x140008ea7  sub     rsp, 20h
0x140008eab  mov     byte ptr [rcx], 0
0x140008eae  mov     rdi, rcx
0x140008eb1  mov     rsi, [rcx+30h]
0x140008eb5  test    rsi, rsi
0x140008eb8  jz      short loc_140008EF2
0x140008eba  call    cs:__imp_GetLastError
0x140008ec0  xor     r9d, r9d; msWindowLength
0x140008ec3  xor     r8d, r8d; msPeriod
0x140008ec6  xor     edx, edx; pftDueTime
0x140008ec8  mov     rcx, rsi; pti
0x140008ecb  mov     ebx, eax
0x140008ecd  call    cs:__imp_SetThreadpoolTimer
0x140008ed3  mov     edx, 1; fCancelPendingCallbacks
0x140008ed8  mov     rcx, rsi; pti
0x140008edb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008ee1  mov     rcx, rsi; pti
0x140008ee4  call    cs:__imp_CloseThreadpoolTimer
0x140008eea  mov     ecx, ebx; dwErrCode
0x140008eec  call    cs:__imp_SetLastError
0x140008ef2  mov     qword ptr [rdi+30h], 0
0x140008efa  mov     rsi, [rdi+38h]
0x140008efe  test    rsi, rsi
0x140008f01  jz      short loc_140008F3B
0x140008f03  call    cs:__imp_GetLastError
0x140008f09  xor     r9d, r9d; msWindowLength
0x140008f0c  xor     r8d, r8d; msPeriod
0x140008f0f  xor     edx, edx; pftDueTime
0x140008f11  mov     rcx, rsi; pti
0x140008f14  mov     ebx, eax
0x140008f16  call    cs:__imp_SetThreadpoolTimer
0x140008f1c  mov     edx, 1; fCancelPendingCallbacks
0x140008f21  mov     rcx, rsi; pti
0x140008f24  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008f2a  mov     rcx, rsi; pti
0x140008f2d  call    cs:__imp_CloseThreadpoolTimer
0x140008f33  mov     ecx, ebx; dwErrCode
0x140008f35  call    cs:__imp_SetLastError
0x140008f3b  mov     qword ptr [rdi+38h], 0
0x140008f43  mov     rbx, [rdi+100h]
0x140008f4a  mov     qword ptr [rdi+100h], 0
0x140008f55  test    rbx, rbx
0x140008f58  jz      short loc_140008F6E
0x140008f5a  call    cs:__imp_GetProcessHeap
0x140008f60  mov     r8, rbx; lpMem
0x140008f63  xor     edx, edx; dwFlags
0x140008f65  mov     rcx, rax; hHeap
0x140008f68  call    cs:__imp_HeapFree
0x140008f6e  mov     r8, [rdi+0E0h]; void *
0x140008f75  test    r8, r8
0x140008f78  jz      short loc_140008F92
0x140008f7a  mov     rdx, cs:qword_140021168; SRWLock
0x140008f81  test    rdx, rdx
0x140008f84  jz      short loc_140008F92
0x140008f86  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140008f8d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAX@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,void *)
0x140008f92  lea     rbx, [rdi+98h]
0x140008f99  mov     rsi, [rbx+40h]
0x140008f9d  mov     qword ptr [rbx+40h], 0
0x140008fa5  test    rsi, rsi
0x140008fa8  jz      short loc_140008FBE
0x140008faa  call    cs:__imp_GetProcessHeap
0x140008fb0  mov     r8, rsi; lpMem
0x140008fb3  xor     edx, edx; dwFlags
0x140008fb5  mov     rcx, rax; hHeap
0x140008fb8  call    cs:__imp_HeapFree
0x140008fbe  mov     rcx, rbx; lpCriticalSection
0x140008fc1  call    cs:__imp_DeleteCriticalSection
0x140008fc7  lea     rcx, [rdi+90h]
0x140008fce  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140008fd3  mov     rsi, [rdi+88h]
0x140008fda  mov     qword ptr [rdi+88h], 0
0x140008fe5  test    rsi, rsi
0x140008fe8  jz      short loc_140008FFE
0x140008fea  call    cs:__imp_GetProcessHeap
0x140008ff0  mov     r8, rsi; lpMem
0x140008ff3  xor     edx, edx; dwFlags
0x140008ff5  mov     rcx, rax; hHeap
0x140008ff8  call    cs:__imp_HeapFree
0x140008ffe  lea     rcx, [rdi+48h]; lpCriticalSection
0x140009002  call    cs:__imp_DeleteCriticalSection
0x140009008  mov     rbx, [rdi+38h]
0x14000900c  test    rbx, rbx
0x14000900f  jz      short loc_140009039
0x140009011  xor     r9d, r9d; msWindowLength
0x140009014  xor     r8d, r8d; msPeriod
0x140009017  xor     edx, edx; pftDueTime
0x140009019  mov     rcx, rbx; pti
0x14000901c  call    cs:__imp_SetThreadpoolTimer
0x140009022  mov     edx, 1; fCancelPendingCallbacks
0x140009027  mov     rcx, rbx; pti
0x14000902a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140009030  mov     rcx, rbx; pti
0x140009033  call    cs:__imp_CloseThreadpoolTimer
0x140009039  mov     rbx, [rdi+30h]
0x14000903d  test    rbx, rbx
0x140009040  jz      short loc_14000906A
0x140009042  xor     r9d, r9d; msWindowLength
0x140009045  xor     r8d, r8d; msPeriod
0x140009048  xor     edx, edx; pftDueTime
0x14000904a  mov     rcx, rbx; pti
0x14000904d  call    cs:__imp_SetThreadpoolTimer
0x140009053  mov     edx, 1; fCancelPendingCallbacks
0x140009058  mov     rcx, rbx; pti
0x14000905b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140009061  mov     rcx, rbx; pti
0x140009064  call    cs:__imp_CloseThreadpoolTimer
0x14000906a  mov     rcx, [rdi+10h]; lpMem
0x14000906e  test    rcx, rcx
0x140009071  jz      short loc_140009078
0x140009073  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x140009078  mov     rbx, [rsp+28h+arg_0]
0x14000907d  mov     rsi, [rsp+28h+arg_8]
0x140009082  add     rsp, 20h
0x140009086  pop     rdi
0x140009087  retn
```
