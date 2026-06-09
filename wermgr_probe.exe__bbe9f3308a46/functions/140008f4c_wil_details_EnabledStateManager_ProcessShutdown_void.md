# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x140008f4c`
- end: `0x140008fe0`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140004bf4`
- `0x14001cfa0`

## callees

- `0x140008f4c`
- `0x14000915c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008f98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008f98`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008fca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008fca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008f8d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008f8d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008f77`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008f77`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008fc2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008fc2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008fb9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008fb9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008fab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008fab`

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
0x140008f4c  mov     [rsp+arg_0], rbx
0x140008f51  mov     [rsp+arg_8], rsi
0x140008f56  push    rdi
0x140008f57  sub     rsp, 20h
0x140008f5b  mov     dword ptr [rcx], 0
0x140008f61  lea     rdi, [rcx+8]
0x140008f65  mov     rsi, [rcx+10h]
0x140008f69  mov     rbx, rcx
0x140008f6c  mov     qword ptr [rcx+10h], 0
0x140008f74  mov     rcx, rdi; SRWLock
0x140008f77  call    cs:__imp_AcquireSRWLockExclusive
0x140008f7d  mov     rcx, rbx
0x140008f80  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x140008f85  test    rdi, rdi
0x140008f88  jz      short loc_140008F93
0x140008f8a  mov     rcx, rdi; SRWLock
0x140008f8d  call    cs:__imp_ReleaseSRWLockExclusive
0x140008f93  test    rsi, rsi
0x140008f96  jz      short loc_140008FD0
0x140008f98  call    cs:__imp_GetLastError
0x140008f9e  xor     r9d, r9d; msWindowLength
0x140008fa1  xor     r8d, r8d; msPeriod
0x140008fa4  xor     edx, edx; pftDueTime
0x140008fa6  mov     rcx, rsi; pti
0x140008fa9  mov     ebx, eax
0x140008fab  call    cs:__imp_SetThreadpoolTimer
0x140008fb1  mov     edx, 1; fCancelPendingCallbacks
0x140008fb6  mov     rcx, rsi; pti
0x140008fb9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008fbf  mov     rcx, rsi; pti
0x140008fc2  call    cs:__imp_CloseThreadpoolTimer
0x140008fc8  mov     ecx, ebx; dwErrCode
0x140008fca  call    cs:__imp_SetLastError
0x140008fd0  mov     rbx, [rsp+28h+arg_0]
0x140008fd5  mov     rsi, [rsp+28h+arg_8]
0x140008fda  add     rsp, 20h
0x140008fde  pop     rdi
0x140008fdf  retn
```
