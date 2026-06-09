# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180005040`
- end: `0x18000522e`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000e6f0`

## callees

- `0x180004ce4`
- `0x180005040`
- `0x180009f00`
- `0x18000adb4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000510c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000515c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000519c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000510c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000515c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000519c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800050fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000514e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000518e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800050fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000514e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000518e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005090`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800050d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005090`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800050d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000505e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000505e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050a7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005165`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800051a6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005165`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800051a6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005088`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800050d1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800051d7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005208`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005088`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800050d1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800051d7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005208`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000507f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800050c8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800051ce`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800051ff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000507f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800050c8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800051ce`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800051ff`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005071`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800050ba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800051c0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800051f1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005071`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800050ba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800051c0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800051f1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  if ( v8 && qword_180015078 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180015078[25], qword_180015078, v8);
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
0x180005040  mov     [rsp+arg_0], rbx
0x180005045  mov     [rsp+arg_8], rsi
0x18000504a  push    rdi
0x18000504b  sub     rsp, 20h
0x18000504f  mov     rdi, rcx
0x180005052  mov     byte ptr [rcx], 0
0x180005055  mov     rsi, [rcx+30h]
0x180005059  test    rsi, rsi
0x18000505c  jz      short loc_180005096
0x18000505e  call    cs:__imp_GetLastError
0x180005064  mov     ebx, eax
0x180005066  xor     r9d, r9d; msWindowLength
0x180005069  xor     r8d, r8d; msPeriod
0x18000506c  xor     edx, edx; pftDueTime
0x18000506e  mov     rcx, rsi; pti
0x180005071  call    cs:__imp_SetThreadpoolTimer
0x180005077  mov     edx, 1; fCancelPendingCallbacks
0x18000507c  mov     rcx, rsi; pti
0x18000507f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005085  mov     rcx, rsi; pti
0x180005088  call    cs:__imp_CloseThreadpoolTimer
0x18000508e  mov     ecx, ebx; dwErrCode
0x180005090  call    cs:__imp_SetLastError
0x180005096  mov     qword ptr [rdi+30h], 0
0x18000509e  mov     rsi, [rdi+38h]
0x1800050a2  test    rsi, rsi
0x1800050a5  jz      short loc_1800050DF
0x1800050a7  call    cs:__imp_GetLastError
0x1800050ad  mov     ebx, eax
0x1800050af  xor     r9d, r9d; msWindowLength
0x1800050b2  xor     r8d, r8d; msPeriod
0x1800050b5  xor     edx, edx; pftDueTime
0x1800050b7  mov     rcx, rsi; pti
0x1800050ba  call    cs:__imp_SetThreadpoolTimer
0x1800050c0  mov     edx, 1; fCancelPendingCallbacks
0x1800050c5  mov     rcx, rsi; pti
0x1800050c8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800050ce  mov     rcx, rsi; pti
0x1800050d1  call    cs:__imp_CloseThreadpoolTimer
0x1800050d7  mov     ecx, ebx; dwErrCode
0x1800050d9  call    cs:__imp_SetLastError
0x1800050df  mov     qword ptr [rdi+38h], 0
0x1800050e7  mov     rbx, [rdi+100h]
0x1800050ee  mov     qword ptr [rdi+100h], 0
0x1800050f9  test    rbx, rbx
0x1800050fc  jz      short loc_180005112
0x1800050fe  call    cs:__imp_GetProcessHeap
0x180005104  mov     rcx, rax; hHeap
0x180005107  mov     r8, rbx; lpMem
0x18000510a  xor     edx, edx; dwFlags
0x18000510c  call    cs:__imp_HeapFree
0x180005112  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180005119  test    r8, r8
0x18000511c  jz      short loc_180005136
0x18000511e  mov     rdx, cs:qword_180015078; SRWLock
0x180005125  test    rdx, rdx
0x180005128  jz      short loc_180005136
0x18000512a  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180005131  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180005136  lea     rbx, [rdi+98h]
0x18000513d  mov     rsi, [rbx+40h]
0x180005141  mov     qword ptr [rbx+40h], 0
0x180005149  test    rsi, rsi
0x18000514c  jz      short loc_180005162
0x18000514e  call    cs:__imp_GetProcessHeap
0x180005154  mov     rcx, rax; hHeap
0x180005157  mov     r8, rsi; lpMem
0x18000515a  xor     edx, edx; dwFlags
0x18000515c  call    cs:__imp_HeapFree
0x180005162  mov     rcx, rbx; lpCriticalSection
0x180005165  call    cs:__imp_DeleteCriticalSection
0x18000516b  lea     rcx, [rdi+90h]
0x180005172  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180005177  mov     rsi, [rdi+88h]
0x18000517e  mov     qword ptr [rdi+88h], 0
0x180005189  test    rsi, rsi
0x18000518c  jz      short loc_1800051A2
0x18000518e  call    cs:__imp_GetProcessHeap
0x180005194  mov     rcx, rax; hHeap
0x180005197  mov     r8, rsi; lpMem
0x18000519a  xor     edx, edx; dwFlags
0x18000519c  call    cs:__imp_HeapFree
0x1800051a2  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800051a6  call    cs:__imp_DeleteCriticalSection
0x1800051ac  mov     rbx, [rdi+38h]
0x1800051b0  test    rbx, rbx
0x1800051b3  jz      short loc_1800051DD
0x1800051b5  xor     r9d, r9d; msWindowLength
0x1800051b8  xor     r8d, r8d; msPeriod
0x1800051bb  xor     edx, edx; pftDueTime
0x1800051bd  mov     rcx, rbx; pti
0x1800051c0  call    cs:__imp_SetThreadpoolTimer
0x1800051c6  mov     edx, 1; fCancelPendingCallbacks
0x1800051cb  mov     rcx, rbx; pti
0x1800051ce  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800051d4  mov     rcx, rbx; pti
0x1800051d7  call    cs:__imp_CloseThreadpoolTimer
0x1800051dd  mov     rbx, [rdi+30h]
0x1800051e1  test    rbx, rbx
0x1800051e4  jz      short loc_18000520F
0x1800051e6  xor     r9d, r9d; msWindowLength
0x1800051e9  xor     r8d, r8d; msPeriod
0x1800051ec  xor     edx, edx; pftDueTime
0x1800051ee  mov     rcx, rbx; pti
0x1800051f1  call    cs:__imp_SetThreadpoolTimer
0x1800051f7  mov     edx, 1; fCancelPendingCallbacks
0x1800051fc  mov     rcx, rbx; pti
0x1800051ff  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005205  mov     rcx, rbx; pti
0x180005208  call    cs:__imp_CloseThreadpoolTimer
0x18000520e  nop
0x18000520f  mov     rcx, [rdi+10h]; lpMem
0x180005213  test    rcx, rcx
0x180005216  jz      short loc_18000521E
0x180005218  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18000521d  nop
0x18000521e  mov     rbx, [rsp+28h+arg_0]
0x180005223  mov     rsi, [rsp+28h+arg_8]
0x180005228  add     rsp, 20h
0x18000522c  pop     rdi
0x18000522d  retn
```
