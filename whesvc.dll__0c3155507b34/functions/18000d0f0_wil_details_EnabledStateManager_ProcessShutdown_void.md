# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000d0f0`
- end: `0x18000d184`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bfdc`
- `0x180028380`

## callees

- `0x18000d0f0`
- `0x18000d53c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d13c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d13c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d16e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d16e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d11b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d11b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d131`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d131`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d166`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d166`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d14f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d14f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d15d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d15d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
0x18000d0f0  mov     [rsp+arg_0], rbx
0x18000d0f5  mov     [rsp+arg_8], rsi
0x18000d0fa  push    rdi
0x18000d0fb  sub     rsp, 20h
0x18000d0ff  mov     dword ptr [rcx], 0
0x18000d105  lea     rdi, [rcx+8]
0x18000d109  mov     rsi, [rcx+10h]
0x18000d10d  mov     rbx, rcx
0x18000d110  mov     qword ptr [rcx+10h], 0
0x18000d118  mov     rcx, rdi; SRWLock
0x18000d11b  call    cs:__imp_AcquireSRWLockExclusive
0x18000d121  mov     rcx, rbx
0x18000d124  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18000d129  test    rdi, rdi
0x18000d12c  jz      short loc_18000D137
0x18000d12e  mov     rcx, rdi; SRWLock
0x18000d131  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d137  test    rsi, rsi
0x18000d13a  jz      short loc_18000D174
0x18000d13c  call    cs:__imp_GetLastError
0x18000d142  xor     r9d, r9d; msWindowLength
0x18000d145  xor     r8d, r8d; msPeriod
0x18000d148  xor     edx, edx; pftDueTime
0x18000d14a  mov     rcx, rsi; pti
0x18000d14d  mov     ebx, eax
0x18000d14f  call    cs:__imp_SetThreadpoolTimer
0x18000d155  mov     edx, 1; fCancelPendingCallbacks
0x18000d15a  mov     rcx, rsi; pti
0x18000d15d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d163  mov     rcx, rsi; pti
0x18000d166  call    cs:__imp_CloseThreadpoolTimer
0x18000d16c  mov     ecx, ebx; dwErrCode
0x18000d16e  call    cs:__imp_SetLastError
0x18000d174  mov     rbx, [rsp+28h+arg_0]
0x18000d179  mov     rsi, [rsp+28h+arg_8]
0x18000d17e  add     rsp, 20h
0x18000d182  pop     rdi
0x18000d183  retn
```
