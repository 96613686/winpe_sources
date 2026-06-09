# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1400088ac`
- end: `0x140008a98`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140010b10`

## callees

- `0x140008768`
- `0x1400088ac`
- `0x14000bd70`
- `0x14000c840`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1400089d1`
- `KERNEL32!DeleteCriticalSection` at `0x140008a12`
- `KERNEL32!DeleteCriticalSection` at `0x1400089d1`
- `KERNEL32!DeleteCriticalSection` at `0x140008a12`
- `KERNEL32!GetLastError` at `0x1400088ca`
- `KERNEL32!GetLastError` at `0x140008913`
- `KERNEL32!GetLastError` at `0x1400088ca`
- `KERNEL32!GetLastError` at `0x140008913`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400088eb`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140008934`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140008a3a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140008a6b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400088eb`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140008934`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140008a3a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140008a6b`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400088f4`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000893d`
- `KERNEL32!CloseThreadpoolTimer` at `0x140008a43`
- `KERNEL32!CloseThreadpoolTimer` at `0x140008a74`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400088f4`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000893d`
- `KERNEL32!CloseThreadpoolTimer` at `0x140008a43`
- `KERNEL32!CloseThreadpoolTimer` at `0x140008a74`
- `KERNEL32!SetThreadpoolTimer` at `0x1400088dd`
- `KERNEL32!SetThreadpoolTimer` at `0x140008926`
- `KERNEL32!SetThreadpoolTimer` at `0x140008a2c`
- `KERNEL32!SetThreadpoolTimer` at `0x140008a5d`
- `KERNEL32!SetThreadpoolTimer` at `0x1400088dd`
- `KERNEL32!SetThreadpoolTimer` at `0x140008926`
- `KERNEL32!SetThreadpoolTimer` at `0x140008a2c`
- `KERNEL32!SetThreadpoolTimer` at `0x140008a5d`
- `KERNEL32!HeapFree` at `0x140008978`
- `KERNEL32!HeapFree` at `0x1400089c8`
- `KERNEL32!HeapFree` at `0x140008a08`
- `KERNEL32!HeapFree` at `0x140008978`
- `KERNEL32!HeapFree` at `0x1400089c8`
- `KERNEL32!HeapFree` at `0x140008a08`
- `KERNEL32!GetProcessHeap` at `0x14000896a`
- `KERNEL32!GetProcessHeap` at `0x1400089ba`
- `KERNEL32!GetProcessHeap` at `0x1400089fa`
- `KERNEL32!GetProcessHeap` at `0x14000896a`
- `KERNEL32!GetProcessHeap` at `0x1400089ba`
- `KERNEL32!GetProcessHeap` at `0x1400089fa`
- `KERNEL32!SetLastError` at `0x1400088fc`
- `KERNEL32!SetLastError` at `0x140008945`
- `KERNEL32!SetLastError` at `0x1400088fc`
- `KERNEL32!SetLastError` at `0x140008945`

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
  if ( v8 && qword_140016028 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_140016028[25], qword_140016028, v8);
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
0x1400088ac  mov     [rsp+arg_0], rbx
0x1400088b1  mov     [rsp+arg_8], rsi
0x1400088b6  push    rdi
0x1400088b7  sub     rsp, 20h
0x1400088bb  mov     byte ptr [rcx], 0
0x1400088be  mov     rdi, rcx
0x1400088c1  mov     rsi, [rcx+30h]
0x1400088c5  test    rsi, rsi
0x1400088c8  jz      short loc_140008902
0x1400088ca  call    cs:__imp_GetLastError
0x1400088d0  xor     r9d, r9d; msWindowLength
0x1400088d3  xor     r8d, r8d; msPeriod
0x1400088d6  xor     edx, edx; pftDueTime
0x1400088d8  mov     rcx, rsi; pti
0x1400088db  mov     ebx, eax
0x1400088dd  call    cs:__imp_SetThreadpoolTimer
0x1400088e3  mov     edx, 1; fCancelPendingCallbacks
0x1400088e8  mov     rcx, rsi; pti
0x1400088eb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400088f1  mov     rcx, rsi; pti
0x1400088f4  call    cs:__imp_CloseThreadpoolTimer
0x1400088fa  mov     ecx, ebx; dwErrCode
0x1400088fc  call    cs:__imp_SetLastError
0x140008902  mov     qword ptr [rdi+30h], 0
0x14000890a  mov     rsi, [rdi+38h]
0x14000890e  test    rsi, rsi
0x140008911  jz      short loc_14000894B
0x140008913  call    cs:__imp_GetLastError
0x140008919  xor     r9d, r9d; msWindowLength
0x14000891c  xor     r8d, r8d; msPeriod
0x14000891f  xor     edx, edx; pftDueTime
0x140008921  mov     rcx, rsi; pti
0x140008924  mov     ebx, eax
0x140008926  call    cs:__imp_SetThreadpoolTimer
0x14000892c  mov     edx, 1; fCancelPendingCallbacks
0x140008931  mov     rcx, rsi; pti
0x140008934  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000893a  mov     rcx, rsi; pti
0x14000893d  call    cs:__imp_CloseThreadpoolTimer
0x140008943  mov     ecx, ebx; dwErrCode
0x140008945  call    cs:__imp_SetLastError
0x14000894b  mov     qword ptr [rdi+38h], 0
0x140008953  mov     rbx, [rdi+100h]
0x14000895a  mov     qword ptr [rdi+100h], 0
0x140008965  test    rbx, rbx
0x140008968  jz      short loc_14000897E
0x14000896a  call    cs:__imp_GetProcessHeap
0x140008970  mov     r8, rbx; lpMem
0x140008973  xor     edx, edx; dwFlags
0x140008975  mov     rcx, rax; hHeap
0x140008978  call    cs:__imp_HeapFree
0x14000897e  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x140008985  test    r8, r8
0x140008988  jz      short loc_1400089A2
0x14000898a  mov     rdx, cs:qword_140016028; SRWLock
0x140008991  test    rdx, rdx
0x140008994  jz      short loc_1400089A2
0x140008996  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x14000899d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1400089a2  lea     rbx, [rdi+98h]
0x1400089a9  mov     rsi, [rbx+40h]
0x1400089ad  mov     qword ptr [rbx+40h], 0
0x1400089b5  test    rsi, rsi
0x1400089b8  jz      short loc_1400089CE
0x1400089ba  call    cs:__imp_GetProcessHeap
0x1400089c0  mov     r8, rsi; lpMem
0x1400089c3  xor     edx, edx; dwFlags
0x1400089c5  mov     rcx, rax; hHeap
0x1400089c8  call    cs:__imp_HeapFree
0x1400089ce  mov     rcx, rbx; lpCriticalSection
0x1400089d1  call    cs:__imp_DeleteCriticalSection
0x1400089d7  lea     rcx, [rdi+90h]
0x1400089de  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400089e3  mov     rsi, [rdi+88h]
0x1400089ea  mov     qword ptr [rdi+88h], 0
0x1400089f5  test    rsi, rsi
0x1400089f8  jz      short loc_140008A0E
0x1400089fa  call    cs:__imp_GetProcessHeap
0x140008a00  mov     r8, rsi; lpMem
0x140008a03  xor     edx, edx; dwFlags
0x140008a05  mov     rcx, rax; hHeap
0x140008a08  call    cs:__imp_HeapFree
0x140008a0e  lea     rcx, [rdi+48h]; lpCriticalSection
0x140008a12  call    cs:__imp_DeleteCriticalSection
0x140008a18  mov     rbx, [rdi+38h]
0x140008a1c  test    rbx, rbx
0x140008a1f  jz      short loc_140008A49
0x140008a21  xor     r9d, r9d; msWindowLength
0x140008a24  xor     r8d, r8d; msPeriod
0x140008a27  xor     edx, edx; pftDueTime
0x140008a29  mov     rcx, rbx; pti
0x140008a2c  call    cs:__imp_SetThreadpoolTimer
0x140008a32  mov     edx, 1; fCancelPendingCallbacks
0x140008a37  mov     rcx, rbx; pti
0x140008a3a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008a40  mov     rcx, rbx; pti
0x140008a43  call    cs:__imp_CloseThreadpoolTimer
0x140008a49  mov     rbx, [rdi+30h]
0x140008a4d  test    rbx, rbx
0x140008a50  jz      short loc_140008A7A
0x140008a52  xor     r9d, r9d; msWindowLength
0x140008a55  xor     r8d, r8d; msPeriod
0x140008a58  xor     edx, edx; pftDueTime
0x140008a5a  mov     rcx, rbx; pti
0x140008a5d  call    cs:__imp_SetThreadpoolTimer
0x140008a63  mov     edx, 1; fCancelPendingCallbacks
0x140008a68  mov     rcx, rbx; pti
0x140008a6b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008a71  mov     rcx, rbx; pti
0x140008a74  call    cs:__imp_CloseThreadpoolTimer
0x140008a7a  mov     rcx, [rdi+10h]; lpMem
0x140008a7e  test    rcx, rcx
0x140008a81  jz      short loc_140008A88
0x140008a83  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x140008a88  mov     rbx, [rsp+28h+arg_0]
0x140008a8d  mov     rsi, [rsp+28h+arg_8]
0x140008a92  add     rsp, 20h
0x140008a96  pop     rdi
0x140008a97  retn
```
