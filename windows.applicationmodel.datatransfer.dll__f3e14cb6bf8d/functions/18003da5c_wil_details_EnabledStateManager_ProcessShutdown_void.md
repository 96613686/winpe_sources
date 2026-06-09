# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18003da5c`
- end: `0x18003daf0`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800179e0`
- `0x180080140`

## callees

- `0x18003da5c`
- `0x180043f40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003da9d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003da9d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003da87`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003da87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003dada`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003dada`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003daa8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003daa8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003dad2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003dad2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003dac9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003dac9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003dabb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003dabb`

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
0x18003da5c  mov     [rsp+arg_0], rbx
0x18003da61  mov     [rsp+arg_8], rsi
0x18003da66  push    rdi
0x18003da67  sub     rsp, 20h
0x18003da6b  mov     dword ptr [rcx], 0
0x18003da71  lea     rdi, [rcx+8]
0x18003da75  mov     rsi, [rcx+10h]
0x18003da79  mov     rbx, rcx
0x18003da7c  mov     qword ptr [rcx+10h], 0
0x18003da84  mov     rcx, rdi; SRWLock
0x18003da87  call    cs:__imp_AcquireSRWLockExclusive
0x18003da8d  mov     rcx, rbx
0x18003da90  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18003da95  test    rdi, rdi
0x18003da98  jz      short loc_18003DAA3
0x18003da9a  mov     rcx, rdi; SRWLock
0x18003da9d  call    cs:__imp_ReleaseSRWLockExclusive
0x18003daa3  test    rsi, rsi
0x18003daa6  jz      short loc_18003DAE0
0x18003daa8  call    cs:__imp_GetLastError
0x18003daae  xor     r9d, r9d; msWindowLength
0x18003dab1  xor     r8d, r8d; msPeriod
0x18003dab4  xor     edx, edx; pftDueTime
0x18003dab6  mov     rcx, rsi; pti
0x18003dab9  mov     ebx, eax
0x18003dabb  call    cs:__imp_SetThreadpoolTimer
0x18003dac1  mov     edx, 1; fCancelPendingCallbacks
0x18003dac6  mov     rcx, rsi; pti
0x18003dac9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003dacf  mov     rcx, rsi; pti
0x18003dad2  call    cs:__imp_CloseThreadpoolTimer
0x18003dad8  mov     ecx, ebx; dwErrCode
0x18003dada  call    cs:__imp_SetLastError
0x18003dae0  mov     rbx, [rsp+28h+arg_0]
0x18003dae5  mov     rsi, [rsp+28h+arg_8]
0x18003daea  add     rsp, 20h
0x18003daee  pop     rdi
0x18003daef  retn
```
