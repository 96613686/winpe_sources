# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x14000506c`
- end: `0x140005258`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140014bc0`

## callees

- `0x140004ddc`
- `0x14000506c`
- `0x14000a0ac`
- `0x14000bbe0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140005138`
- `KERNEL32!HeapFree` at `0x140005188`
- `KERNEL32!HeapFree` at `0x1400051c8`
- `KERNEL32!HeapFree` at `0x140005138`
- `KERNEL32!HeapFree` at `0x140005188`
- `KERNEL32!HeapFree` at `0x1400051c8`
- `KERNEL32!SetThreadpoolTimer` at `0x14000509d`
- `KERNEL32!SetThreadpoolTimer` at `0x1400050e6`
- `KERNEL32!SetThreadpoolTimer` at `0x1400051ec`
- `KERNEL32!SetThreadpoolTimer` at `0x14000521d`
- `KERNEL32!SetThreadpoolTimer` at `0x14000509d`
- `KERNEL32!SetThreadpoolTimer` at `0x1400050e6`
- `KERNEL32!SetThreadpoolTimer` at `0x1400051ec`
- `KERNEL32!SetThreadpoolTimer` at `0x14000521d`
- `KERNEL32!DeleteCriticalSection` at `0x140005191`
- `KERNEL32!DeleteCriticalSection` at `0x1400051d2`
- `KERNEL32!DeleteCriticalSection` at `0x140005191`
- `KERNEL32!DeleteCriticalSection` at `0x1400051d2`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400050ab`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400050f4`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400051fa`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000522b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400050ab`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400050f4`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400051fa`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000522b`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400050b4`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400050fd`
- `KERNEL32!CloseThreadpoolTimer` at `0x140005203`
- `KERNEL32!CloseThreadpoolTimer` at `0x140005234`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400050b4`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400050fd`
- `KERNEL32!CloseThreadpoolTimer` at `0x140005203`
- `KERNEL32!CloseThreadpoolTimer` at `0x140005234`
- `KERNEL32!GetLastError` at `0x14000508a`
- `KERNEL32!GetLastError` at `0x1400050d3`
- `KERNEL32!GetLastError` at `0x14000508a`
- `KERNEL32!GetLastError` at `0x1400050d3`
- `KERNEL32!SetLastError` at `0x1400050bc`
- `KERNEL32!SetLastError` at `0x140005105`
- `KERNEL32!SetLastError` at `0x1400050bc`
- `KERNEL32!SetLastError` at `0x140005105`
- `KERNEL32!GetProcessHeap` at `0x14000512a`
- `KERNEL32!GetProcessHeap` at `0x14000517a`
- `KERNEL32!GetProcessHeap` at `0x1400051ba`
- `KERNEL32!GetProcessHeap` at `0x14000512a`
- `KERNEL32!GetProcessHeap` at `0x14000517a`
- `KERNEL32!GetProcessHeap` at `0x1400051ba`

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
  if ( v8 && qword_140020028 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_140020028[25], qword_140020028, v8);
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
0x14000506c  mov     [rsp+arg_0], rbx
0x140005071  mov     [rsp+arg_8], rsi
0x140005076  push    rdi
0x140005077  sub     rsp, 20h
0x14000507b  mov     byte ptr [rcx], 0
0x14000507e  mov     rdi, rcx
0x140005081  mov     rsi, [rcx+30h]
0x140005085  test    rsi, rsi
0x140005088  jz      short loc_1400050C2
0x14000508a  call    cs:__imp_GetLastError
0x140005090  xor     r9d, r9d; msWindowLength
0x140005093  xor     r8d, r8d; msPeriod
0x140005096  xor     edx, edx; pftDueTime
0x140005098  mov     rcx, rsi; pti
0x14000509b  mov     ebx, eax
0x14000509d  call    cs:__imp_SetThreadpoolTimer
0x1400050a3  mov     edx, 1; fCancelPendingCallbacks
0x1400050a8  mov     rcx, rsi; pti
0x1400050ab  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400050b1  mov     rcx, rsi; pti
0x1400050b4  call    cs:__imp_CloseThreadpoolTimer
0x1400050ba  mov     ecx, ebx; dwErrCode
0x1400050bc  call    cs:__imp_SetLastError
0x1400050c2  mov     qword ptr [rdi+30h], 0
0x1400050ca  mov     rsi, [rdi+38h]
0x1400050ce  test    rsi, rsi
0x1400050d1  jz      short loc_14000510B
0x1400050d3  call    cs:__imp_GetLastError
0x1400050d9  xor     r9d, r9d; msWindowLength
0x1400050dc  xor     r8d, r8d; msPeriod
0x1400050df  xor     edx, edx; pftDueTime
0x1400050e1  mov     rcx, rsi; pti
0x1400050e4  mov     ebx, eax
0x1400050e6  call    cs:__imp_SetThreadpoolTimer
0x1400050ec  mov     edx, 1; fCancelPendingCallbacks
0x1400050f1  mov     rcx, rsi; pti
0x1400050f4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400050fa  mov     rcx, rsi; pti
0x1400050fd  call    cs:__imp_CloseThreadpoolTimer
0x140005103  mov     ecx, ebx; dwErrCode
0x140005105  call    cs:__imp_SetLastError
0x14000510b  mov     qword ptr [rdi+38h], 0
0x140005113  mov     rbx, [rdi+100h]
0x14000511a  mov     qword ptr [rdi+100h], 0
0x140005125  test    rbx, rbx
0x140005128  jz      short loc_14000513E
0x14000512a  call    cs:__imp_GetProcessHeap
0x140005130  mov     r8, rbx; lpMem
0x140005133  xor     edx, edx; dwFlags
0x140005135  mov     rcx, rax; hHeap
0x140005138  call    cs:__imp_HeapFree
0x14000513e  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x140005145  test    r8, r8
0x140005148  jz      short loc_140005162
0x14000514a  mov     rdx, cs:qword_140020028; SRWLock
0x140005151  test    rdx, rdx
0x140005154  jz      short loc_140005162
0x140005156  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x14000515d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x140005162  lea     rbx, [rdi+98h]
0x140005169  mov     rsi, [rbx+40h]
0x14000516d  mov     qword ptr [rbx+40h], 0
0x140005175  test    rsi, rsi
0x140005178  jz      short loc_14000518E
0x14000517a  call    cs:__imp_GetProcessHeap
0x140005180  mov     r8, rsi; lpMem
0x140005183  xor     edx, edx; dwFlags
0x140005185  mov     rcx, rax; hHeap
0x140005188  call    cs:__imp_HeapFree
0x14000518e  mov     rcx, rbx; lpCriticalSection
0x140005191  call    cs:__imp_DeleteCriticalSection
0x140005197  lea     rcx, [rdi+90h]
0x14000519e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400051a3  mov     rsi, [rdi+88h]
0x1400051aa  mov     qword ptr [rdi+88h], 0
0x1400051b5  test    rsi, rsi
0x1400051b8  jz      short loc_1400051CE
0x1400051ba  call    cs:__imp_GetProcessHeap
0x1400051c0  mov     r8, rsi; lpMem
0x1400051c3  xor     edx, edx; dwFlags
0x1400051c5  mov     rcx, rax; hHeap
0x1400051c8  call    cs:__imp_HeapFree
0x1400051ce  lea     rcx, [rdi+48h]; lpCriticalSection
0x1400051d2  call    cs:__imp_DeleteCriticalSection
0x1400051d8  mov     rbx, [rdi+38h]
0x1400051dc  test    rbx, rbx
0x1400051df  jz      short loc_140005209
0x1400051e1  xor     r9d, r9d; msWindowLength
0x1400051e4  xor     r8d, r8d; msPeriod
0x1400051e7  xor     edx, edx; pftDueTime
0x1400051e9  mov     rcx, rbx; pti
0x1400051ec  call    cs:__imp_SetThreadpoolTimer
0x1400051f2  mov     edx, 1; fCancelPendingCallbacks
0x1400051f7  mov     rcx, rbx; pti
0x1400051fa  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005200  mov     rcx, rbx; pti
0x140005203  call    cs:__imp_CloseThreadpoolTimer
0x140005209  mov     rbx, [rdi+30h]
0x14000520d  test    rbx, rbx
0x140005210  jz      short loc_14000523A
0x140005212  xor     r9d, r9d; msWindowLength
0x140005215  xor     r8d, r8d; msPeriod
0x140005218  xor     edx, edx; pftDueTime
0x14000521a  mov     rcx, rbx; pti
0x14000521d  call    cs:__imp_SetThreadpoolTimer
0x140005223  mov     edx, 1; fCancelPendingCallbacks
0x140005228  mov     rcx, rbx; pti
0x14000522b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005231  mov     rcx, rbx; pti
0x140005234  call    cs:__imp_CloseThreadpoolTimer
0x14000523a  mov     rcx, [rdi+10h]; lpMem
0x14000523e  test    rcx, rcx
0x140005241  jz      short loc_140005248
0x140005243  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x140005248  mov     rbx, [rsp+28h+arg_0]
0x14000524d  mov     rsi, [rsp+28h+arg_8]
0x140005252  add     rsp, 20h
0x140005256  pop     rdi
0x140005257  retn
```
