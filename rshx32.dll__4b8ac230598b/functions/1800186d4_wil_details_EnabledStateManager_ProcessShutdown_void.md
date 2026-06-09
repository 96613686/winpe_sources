# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x1800186d4`
- end: `0x180018768`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180016a9c`
- `0x18001d7f0`

## callees

- `0x1800186d4`
- `0x18001890c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018715`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018715`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800186ff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800186ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018752`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018752`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018720`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018720`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001874a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001874a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180018741`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180018741`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180018733`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180018733`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::ProcessShutdown(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rdi
  struct _TP_TIMER *Ptr; // rsi
  DWORD LastError; // ebx

  LODWORD(this->Ptr) = 0;
  v1 = this + 1;
  Ptr = (struct _TP_TIMER *)this[2].Ptr;
  this[2].Ptr = 0;
  AcquireSRWLockExclusive(this + 1);
  wil::details::EnabledStateManager::RecordCachedUsageUnderLock(this);
  if ( v1 )
    ReleaseSRWLockExclusive(v1);
  if ( Ptr )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(Ptr, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(Ptr, 1);
    CloseThreadpoolTimer(Ptr);
    SetLastError(LastError);
  }
}

```

## disassembly

```asm
0x1800186d4  mov     [rsp+arg_0], rbx
0x1800186d9  mov     [rsp+arg_8], rsi
0x1800186de  push    rdi
0x1800186df  sub     rsp, 20h
0x1800186e3  mov     dword ptr [rcx], 0
0x1800186e9  lea     rdi, [rcx+8]
0x1800186ed  mov     rsi, [rcx+10h]
0x1800186f1  mov     rbx, rcx
0x1800186f4  mov     qword ptr [rcx+10h], 0
0x1800186fc  mov     rcx, rdi; SRWLock
0x1800186ff  call    cs:__imp_AcquireSRWLockExclusive
0x180018705  mov     rcx, rbx
0x180018708  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18001870d  test    rdi, rdi
0x180018710  jz      short loc_18001871B
0x180018712  mov     rcx, rdi; SRWLock
0x180018715  call    cs:__imp_ReleaseSRWLockExclusive
0x18001871b  test    rsi, rsi
0x18001871e  jz      short loc_180018758
0x180018720  call    cs:__imp_GetLastError
0x180018726  xor     r9d, r9d; msWindowLength
0x180018729  xor     r8d, r8d; msPeriod
0x18001872c  xor     edx, edx; pftDueTime
0x18001872e  mov     rcx, rsi; pti
0x180018731  mov     ebx, eax
0x180018733  call    cs:__imp_SetThreadpoolTimer
0x180018739  mov     edx, 1; fCancelPendingCallbacks
0x18001873e  mov     rcx, rsi; pti
0x180018741  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180018747  mov     rcx, rsi; pti
0x18001874a  call    cs:__imp_CloseThreadpoolTimer
0x180018750  mov     ecx, ebx; dwErrCode
0x180018752  call    cs:__imp_SetLastError
0x180018758  mov     rbx, [rsp+28h+arg_0]
0x18001875d  mov     rsi, [rsp+28h+arg_8]
0x180018762  add     rsp, 20h
0x180018766  pop     rdi
0x180018767  retn
```
