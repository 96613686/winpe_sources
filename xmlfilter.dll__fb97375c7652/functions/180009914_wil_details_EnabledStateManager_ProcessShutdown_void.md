# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x180009914`
- end: `0x1800099a8`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800047b4`
- `0x180016040`

## callees

- `0x180009914`
- `0x180009f68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009992`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009992`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009960`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009960`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009955`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009955`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000993f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000993f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009973`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009973`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000998a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000998a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009981`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009981`

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
0x180009914  mov     [rsp+arg_0], rbx
0x180009919  mov     [rsp+arg_8], rsi
0x18000991e  push    rdi
0x18000991f  sub     rsp, 20h
0x180009923  mov     dword ptr [rcx], 0
0x180009929  lea     rdi, [rcx+8]
0x18000992d  mov     rsi, [rcx+10h]
0x180009931  mov     rbx, rcx
0x180009934  mov     qword ptr [rcx+10h], 0
0x18000993c  mov     rcx, rdi; SRWLock
0x18000993f  call    cs:__imp_AcquireSRWLockExclusive
0x180009945  mov     rcx, rbx
0x180009948  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18000994d  test    rdi, rdi
0x180009950  jz      short loc_18000995B
0x180009952  mov     rcx, rdi; SRWLock
0x180009955  call    cs:__imp_ReleaseSRWLockExclusive
0x18000995b  test    rsi, rsi
0x18000995e  jz      short loc_180009998
0x180009960  call    cs:__imp_GetLastError
0x180009966  xor     r9d, r9d; msWindowLength
0x180009969  xor     r8d, r8d; msPeriod
0x18000996c  xor     edx, edx; pftDueTime
0x18000996e  mov     rcx, rsi; pti
0x180009971  mov     ebx, eax
0x180009973  call    cs:__imp_SetThreadpoolTimer
0x180009979  mov     edx, 1; fCancelPendingCallbacks
0x18000997e  mov     rcx, rsi; pti
0x180009981  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009987  mov     rcx, rsi; pti
0x18000998a  call    cs:__imp_CloseThreadpoolTimer
0x180009990  mov     ecx, ebx; dwErrCode
0x180009992  call    cs:__imp_SetLastError
0x180009998  mov     rbx, [rsp+28h+arg_0]
0x18000999d  mov     rsi, [rsp+28h+arg_8]
0x1800099a2  add     rsp, 20h
0x1800099a6  pop     rdi
0x1800099a7  retn
```
