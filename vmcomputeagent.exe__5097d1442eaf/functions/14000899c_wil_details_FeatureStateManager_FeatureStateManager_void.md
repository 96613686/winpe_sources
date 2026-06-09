# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x14000899c`
- end: `0x140008b77`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `475`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400fd6b0`

## callees

- `0x140008894`
- `0x14000899c`
- `0x14000c914`
- `0x14000e090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140008aae`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140008aef`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140008aae`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140008aef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008a5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008a97`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008ad7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008a5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008a97`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008ad7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008a68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008aa5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008ae5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008a68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008aa5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008ae5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400089ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008a35`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400089ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008a35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400089ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008a03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400089ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008a03`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400089cd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008a16`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008b09`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008b3a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400089cd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008a16`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008b09`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008b3a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400089e4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008a2d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008b20`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008b51`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400089e4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008a2d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008b20`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008b51`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400089db`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008a24`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008b17`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008b48`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400089db`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008a24`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008b17`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008b48`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::FeatureStateManager::~FeatureStateManager(
        wil::details::FeatureStateManager *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *a2)
{
  struct _TP_TIMER *v3; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *v5; // rsi
  DWORD v6; // ebx
  void *v7; // rbx
  HANDLE ProcessHeap; // rax
  wil::details *v9; // rcx
  void *v10; // rsi
  HANDLE v11; // rax
  void *v12; // rsi
  HANDLE v13; // rax
  struct _TP_TIMER *v14; // rbx
  struct _TP_TIMER *v15; // rbx
  void *v16; // rcx

  *(_BYTE *)this = 0;
  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v3 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v3, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v3, 1);
    CloseThreadpoolTimer(v3);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 6) = 0;
  v5 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v5 )
  {
    v6 = GetLastError();
    SetThreadpoolTimer(v5, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v5, 1);
    CloseThreadpoolTimer(v5);
    SetLastError(v6);
  }
  *((_QWORD *)this + 7) = 0;
  v7 = (void *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  if ( v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
  }
  v9 = (wil::details *)*((_QWORD *)this + 28);
  if ( v9 )
    wil::details::UnsubscribeProcessWideUsageFlush(v9, a2);
  v10 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v10 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v10);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((char *)this + 144);
  v12 = (void *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v12 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v12);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v14 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v14 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 7), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v14, 1);
    CloseThreadpoolTimer(v14);
  }
  v15 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v15 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 6), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v15, 1);
    CloseThreadpoolTimer(v15);
  }
  v16 = (void *)*((_QWORD *)this + 2);
  if ( v16 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v16);
}

```

## disassembly

```asm
0x14000899c  mov     [rsp+arg_0], rbx
0x1400089a1  mov     [rsp+arg_8], rsi
0x1400089a6  push    rdi
0x1400089a7  sub     rsp, 20h
0x1400089ab  mov     rdi, rcx
0x1400089ae  mov     byte ptr [rcx], 0
0x1400089b1  mov     rsi, [rcx+30h]
0x1400089b5  test    rsi, rsi
0x1400089b8  jz      short loc_1400089F2
0x1400089ba  call    cs:__imp_GetLastError
0x1400089c0  mov     ebx, eax
0x1400089c2  xor     r9d, r9d; msWindowLength
0x1400089c5  xor     r8d, r8d; msPeriod
0x1400089c8  xor     edx, edx; pftDueTime
0x1400089ca  mov     rcx, rsi; pti
0x1400089cd  call    cs:__imp_SetThreadpoolTimer
0x1400089d3  mov     edx, 1; fCancelPendingCallbacks
0x1400089d8  mov     rcx, rsi; pti
0x1400089db  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400089e1  mov     rcx, rsi; pti
0x1400089e4  call    cs:__imp_CloseThreadpoolTimer
0x1400089ea  mov     ecx, ebx; dwErrCode
0x1400089ec  call    cs:__imp_SetLastError
0x1400089f2  mov     qword ptr [rdi+30h], 0
0x1400089fa  mov     rsi, [rdi+38h]
0x1400089fe  test    rsi, rsi
0x140008a01  jz      short loc_140008A3B
0x140008a03  call    cs:__imp_GetLastError
0x140008a09  mov     ebx, eax
0x140008a0b  xor     r9d, r9d; msWindowLength
0x140008a0e  xor     r8d, r8d; msPeriod
0x140008a11  xor     edx, edx; pftDueTime
0x140008a13  mov     rcx, rsi; pti
0x140008a16  call    cs:__imp_SetThreadpoolTimer
0x140008a1c  mov     edx, 1; fCancelPendingCallbacks
0x140008a21  mov     rcx, rsi; pti
0x140008a24  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008a2a  mov     rcx, rsi; pti
0x140008a2d  call    cs:__imp_CloseThreadpoolTimer
0x140008a33  mov     ecx, ebx; dwErrCode
0x140008a35  call    cs:__imp_SetLastError
0x140008a3b  mov     qword ptr [rdi+38h], 0
0x140008a43  mov     rbx, [rdi+100h]
0x140008a4a  mov     qword ptr [rdi+100h], 0
0x140008a55  test    rbx, rbx
0x140008a58  jz      short loc_140008A6E
0x140008a5a  call    cs:__imp_GetProcessHeap
0x140008a60  mov     rcx, rax; hHeap
0x140008a63  mov     r8, rbx; lpMem
0x140008a66  xor     edx, edx; dwFlags
0x140008a68  call    cs:__imp_HeapFree
0x140008a6e  mov     rcx, [rdi+0E0h]; this
0x140008a75  test    rcx, rcx
0x140008a78  jz      short loc_140008A7F
0x140008a7a  call    ?UnsubscribeProcessWideUsageFlush@details@wil@@YAXPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details::UnsubscribeProcessWideUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x140008a7f  lea     rbx, [rdi+98h]
0x140008a86  mov     rsi, [rbx+40h]
0x140008a8a  mov     qword ptr [rbx+40h], 0
0x140008a92  test    rsi, rsi
0x140008a95  jz      short loc_140008AAB
0x140008a97  call    cs:__imp_GetProcessHeap
0x140008a9d  mov     rcx, rax; hHeap
0x140008aa0  mov     r8, rsi; lpMem
0x140008aa3  xor     edx, edx; dwFlags
0x140008aa5  call    cs:__imp_HeapFree
0x140008aab  mov     rcx, rbx; lpCriticalSection
0x140008aae  call    cs:__imp_DeleteCriticalSection
0x140008ab4  lea     rcx, [rdi+90h]
0x140008abb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140008ac0  mov     rsi, [rdi+88h]
0x140008ac7  mov     qword ptr [rdi+88h], 0
0x140008ad2  test    rsi, rsi
0x140008ad5  jz      short loc_140008AEB
0x140008ad7  call    cs:__imp_GetProcessHeap
0x140008add  mov     rcx, rax; hHeap
0x140008ae0  mov     r8, rsi; lpMem
0x140008ae3  xor     edx, edx; dwFlags
0x140008ae5  call    cs:__imp_HeapFree
0x140008aeb  lea     rcx, [rdi+48h]; lpCriticalSection
0x140008aef  call    cs:__imp_DeleteCriticalSection
0x140008af5  mov     rbx, [rdi+38h]
0x140008af9  test    rbx, rbx
0x140008afc  jz      short loc_140008B26
0x140008afe  xor     r9d, r9d; msWindowLength
0x140008b01  xor     r8d, r8d; msPeriod
0x140008b04  xor     edx, edx; pftDueTime
0x140008b06  mov     rcx, rbx; pti
0x140008b09  call    cs:__imp_SetThreadpoolTimer
0x140008b0f  mov     edx, 1; fCancelPendingCallbacks
0x140008b14  mov     rcx, rbx; pti
0x140008b17  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008b1d  mov     rcx, rbx; pti
0x140008b20  call    cs:__imp_CloseThreadpoolTimer
0x140008b26  mov     rbx, [rdi+30h]
0x140008b2a  test    rbx, rbx
0x140008b2d  jz      short loc_140008B58
0x140008b2f  xor     r9d, r9d; msWindowLength
0x140008b32  xor     r8d, r8d; msPeriod
0x140008b35  xor     edx, edx; pftDueTime
0x140008b37  mov     rcx, rbx; pti
0x140008b3a  call    cs:__imp_SetThreadpoolTimer
0x140008b40  mov     edx, 1; fCancelPendingCallbacks
0x140008b45  mov     rcx, rbx; pti
0x140008b48  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008b4e  mov     rcx, rbx; pti
0x140008b51  call    cs:__imp_CloseThreadpoolTimer
0x140008b57  nop
0x140008b58  mov     rcx, [rdi+10h]; lpMem
0x140008b5c  test    rcx, rcx
0x140008b5f  jz      short loc_140008B67
0x140008b61  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x140008b66  nop
0x140008b67  mov     rbx, [rsp+28h+arg_0]
0x140008b6c  mov     rsi, [rsp+28h+arg_8]
0x140008b71  add     rsp, 20h
0x140008b75  pop     rdi
0x140008b76  retn
```
