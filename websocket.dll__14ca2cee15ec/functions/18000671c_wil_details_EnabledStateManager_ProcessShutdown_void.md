# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000671c`
- end: `0x1800067b0`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800037c8`
- `0x18000dd90`

## callees

- `0x18000671c`
- `0x180006b40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000679a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000679a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006768`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006768`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006747`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006747`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000675d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000675d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000677b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000677b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006792`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006792`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006789`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006789`

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
0x18000671c  mov     [rsp+arg_0], rbx
0x180006721  mov     [rsp+arg_8], rsi
0x180006726  push    rdi
0x180006727  sub     rsp, 20h
0x18000672b  mov     dword ptr [rcx], 0
0x180006731  lea     rdi, [rcx+8]
0x180006735  mov     rsi, [rcx+10h]
0x180006739  mov     rbx, rcx
0x18000673c  mov     qword ptr [rcx+10h], 0
0x180006744  mov     rcx, rdi; SRWLock
0x180006747  call    cs:__imp_AcquireSRWLockExclusive
0x18000674d  mov     rcx, rbx
0x180006750  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180006755  test    rdi, rdi
0x180006758  jz      short loc_180006763
0x18000675a  mov     rcx, rdi; SRWLock
0x18000675d  call    cs:__imp_ReleaseSRWLockExclusive
0x180006763  test    rsi, rsi
0x180006766  jz      short loc_1800067A0
0x180006768  call    cs:__imp_GetLastError
0x18000676e  xor     r9d, r9d; msWindowLength
0x180006771  xor     r8d, r8d; msPeriod
0x180006774  xor     edx, edx; pftDueTime
0x180006776  mov     rcx, rsi; pti
0x180006779  mov     ebx, eax
0x18000677b  call    cs:__imp_SetThreadpoolTimer
0x180006781  mov     edx, 1; fCancelPendingCallbacks
0x180006786  mov     rcx, rsi; pti
0x180006789  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000678f  mov     rcx, rsi; pti
0x180006792  call    cs:__imp_CloseThreadpoolTimer
0x180006798  mov     ecx, ebx; dwErrCode
0x18000679a  call    cs:__imp_SetLastError
0x1800067a0  mov     rbx, [rsp+28h+arg_0]
0x1800067a5  mov     rsi, [rsp+28h+arg_8]
0x1800067aa  add     rsp, 20h
0x1800067ae  pop     rdi
0x1800067af  retn
```
