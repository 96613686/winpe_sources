# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180017c88`
- end: `0x180017e76`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180080190`

## callees

- `0x180016e58`
- `0x180017c88`
- `0x1800454e4`
- `0x1800505dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017dad`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017dee`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017dad`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017dee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017cd8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017d21`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017cd8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017d21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ca6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017cef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ca6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017cef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017d54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017da4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017de4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017d54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017da4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017de4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017d46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017d96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017dd6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017d46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017d96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017dd6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180017cd0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180017d19`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180017e1f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180017e50`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180017cd0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180017d19`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180017e1f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180017e50`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180017cc7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180017d10`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180017e16`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180017e47`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180017cc7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180017d10`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180017e16`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180017e47`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017cb9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017d02`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017e08`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017e39`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017cb9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017d02`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017e08`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017e39`

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
  if ( v8 && qword_1800AA198 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800AA198[25], qword_1800AA198, v8);
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
0x180017c88  mov     [rsp+arg_0], rbx
0x180017c8d  mov     [rsp+arg_8], rsi
0x180017c92  push    rdi
0x180017c93  sub     rsp, 20h
0x180017c97  mov     rdi, rcx
0x180017c9a  mov     byte ptr [rcx], 0
0x180017c9d  mov     rsi, [rcx+30h]
0x180017ca1  test    rsi, rsi
0x180017ca4  jz      short loc_180017CDE
0x180017ca6  call    cs:__imp_GetLastError
0x180017cac  mov     ebx, eax
0x180017cae  xor     r9d, r9d; msWindowLength
0x180017cb1  xor     r8d, r8d; msPeriod
0x180017cb4  xor     edx, edx; pftDueTime
0x180017cb6  mov     rcx, rsi; pti
0x180017cb9  call    cs:__imp_SetThreadpoolTimer
0x180017cbf  mov     edx, 1; fCancelPendingCallbacks
0x180017cc4  mov     rcx, rsi; pti
0x180017cc7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180017ccd  mov     rcx, rsi; pti
0x180017cd0  call    cs:__imp_CloseThreadpoolTimer
0x180017cd6  mov     ecx, ebx; dwErrCode
0x180017cd8  call    cs:__imp_SetLastError
0x180017cde  mov     qword ptr [rdi+30h], 0
0x180017ce6  mov     rsi, [rdi+38h]
0x180017cea  test    rsi, rsi
0x180017ced  jz      short loc_180017D27
0x180017cef  call    cs:__imp_GetLastError
0x180017cf5  mov     ebx, eax
0x180017cf7  xor     r9d, r9d; msWindowLength
0x180017cfa  xor     r8d, r8d; msPeriod
0x180017cfd  xor     edx, edx; pftDueTime
0x180017cff  mov     rcx, rsi; pti
0x180017d02  call    cs:__imp_SetThreadpoolTimer
0x180017d08  mov     edx, 1; fCancelPendingCallbacks
0x180017d0d  mov     rcx, rsi; pti
0x180017d10  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180017d16  mov     rcx, rsi; pti
0x180017d19  call    cs:__imp_CloseThreadpoolTimer
0x180017d1f  mov     ecx, ebx; dwErrCode
0x180017d21  call    cs:__imp_SetLastError
0x180017d27  mov     qword ptr [rdi+38h], 0
0x180017d2f  mov     rbx, [rdi+100h]
0x180017d36  mov     qword ptr [rdi+100h], 0
0x180017d41  test    rbx, rbx
0x180017d44  jz      short loc_180017D5A
0x180017d46  call    cs:__imp_GetProcessHeap
0x180017d4c  mov     rcx, rax; hHeap
0x180017d4f  mov     r8, rbx; lpMem
0x180017d52  xor     edx, edx; dwFlags
0x180017d54  call    cs:__imp_HeapFree
0x180017d5a  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180017d61  test    r8, r8
0x180017d64  jz      short loc_180017D7E
0x180017d66  mov     rdx, cs:qword_1800AA198; SRWLock
0x180017d6d  test    rdx, rdx
0x180017d70  jz      short loc_180017D7E
0x180017d72  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180017d79  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180017d7e  lea     rbx, [rdi+98h]
0x180017d85  mov     rsi, [rbx+40h]
0x180017d89  mov     qword ptr [rbx+40h], 0
0x180017d91  test    rsi, rsi
0x180017d94  jz      short loc_180017DAA
0x180017d96  call    cs:__imp_GetProcessHeap
0x180017d9c  mov     rcx, rax; hHeap
0x180017d9f  mov     r8, rsi; lpMem
0x180017da2  xor     edx, edx; dwFlags
0x180017da4  call    cs:__imp_HeapFree
0x180017daa  mov     rcx, rbx; lpCriticalSection
0x180017dad  call    cs:__imp_DeleteCriticalSection
0x180017db3  lea     rcx, [rdi+90h]
0x180017dba  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180017dbf  mov     rsi, [rdi+88h]
0x180017dc6  mov     qword ptr [rdi+88h], 0
0x180017dd1  test    rsi, rsi
0x180017dd4  jz      short loc_180017DEA
0x180017dd6  call    cs:__imp_GetProcessHeap
0x180017ddc  mov     rcx, rax; hHeap
0x180017ddf  mov     r8, rsi; lpMem
0x180017de2  xor     edx, edx; dwFlags
0x180017de4  call    cs:__imp_HeapFree
0x180017dea  lea     rcx, [rdi+48h]; lpCriticalSection
0x180017dee  call    cs:__imp_DeleteCriticalSection
0x180017df4  mov     rbx, [rdi+38h]
0x180017df8  test    rbx, rbx
0x180017dfb  jz      short loc_180017E25
0x180017dfd  xor     r9d, r9d; msWindowLength
0x180017e00  xor     r8d, r8d; msPeriod
0x180017e03  xor     edx, edx; pftDueTime
0x180017e05  mov     rcx, rbx; pti
0x180017e08  call    cs:__imp_SetThreadpoolTimer
0x180017e0e  mov     edx, 1; fCancelPendingCallbacks
0x180017e13  mov     rcx, rbx; pti
0x180017e16  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180017e1c  mov     rcx, rbx; pti
0x180017e1f  call    cs:__imp_CloseThreadpoolTimer
0x180017e25  mov     rbx, [rdi+30h]
0x180017e29  test    rbx, rbx
0x180017e2c  jz      short loc_180017E57
0x180017e2e  xor     r9d, r9d; msWindowLength
0x180017e31  xor     r8d, r8d; msPeriod
0x180017e34  xor     edx, edx; pftDueTime
0x180017e36  mov     rcx, rbx; pti
0x180017e39  call    cs:__imp_SetThreadpoolTimer
0x180017e3f  mov     edx, 1; fCancelPendingCallbacks
0x180017e44  mov     rcx, rbx; pti
0x180017e47  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180017e4d  mov     rcx, rbx; pti
0x180017e50  call    cs:__imp_CloseThreadpoolTimer
0x180017e56  nop
0x180017e57  mov     rcx, [rdi+10h]; lpMem
0x180017e5b  test    rcx, rcx
0x180017e5e  jz      short loc_180017E66
0x180017e60  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180017e65  nop
0x180017e66  mov     rbx, [rsp+28h+arg_0]
0x180017e6b  mov     rsi, [rsp+28h+arg_8]
0x180017e70  add     rsp, 20h
0x180017e74  pop     rdi
0x180017e75  retn
```
