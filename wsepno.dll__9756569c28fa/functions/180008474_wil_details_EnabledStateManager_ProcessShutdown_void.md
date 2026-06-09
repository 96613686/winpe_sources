# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x180008474`
- end: `0x180008508`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004e08`
- `0x18000e6a0`

## callees

- `0x180008474`
- `0x180009018`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800084f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800084f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084c0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000849f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000849f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800084b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800084b5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800084ea`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800084ea`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800084e1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800084e1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800084d3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800084d3`

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
0x180008474  mov     [rsp+arg_0], rbx
0x180008479  mov     [rsp+arg_8], rsi
0x18000847e  push    rdi
0x18000847f  sub     rsp, 20h
0x180008483  mov     dword ptr [rcx], 0
0x180008489  lea     rdi, [rcx+8]
0x18000848d  mov     rsi, [rcx+10h]
0x180008491  mov     rbx, rcx
0x180008494  mov     qword ptr [rcx+10h], 0
0x18000849c  mov     rcx, rdi; SRWLock
0x18000849f  call    cs:__imp_AcquireSRWLockExclusive
0x1800084a5  mov     rcx, rbx
0x1800084a8  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x1800084ad  test    rdi, rdi
0x1800084b0  jz      short loc_1800084BB
0x1800084b2  mov     rcx, rdi; SRWLock
0x1800084b5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800084bb  test    rsi, rsi
0x1800084be  jz      short loc_1800084F8
0x1800084c0  call    cs:__imp_GetLastError
0x1800084c6  xor     r9d, r9d; msWindowLength
0x1800084c9  xor     r8d, r8d; msPeriod
0x1800084cc  xor     edx, edx; pftDueTime
0x1800084ce  mov     rcx, rsi; pti
0x1800084d1  mov     ebx, eax
0x1800084d3  call    cs:__imp_SetThreadpoolTimer
0x1800084d9  mov     edx, 1; fCancelPendingCallbacks
0x1800084de  mov     rcx, rsi; pti
0x1800084e1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800084e7  mov     rcx, rsi; pti
0x1800084ea  call    cs:__imp_CloseThreadpoolTimer
0x1800084f0  mov     ecx, ebx; dwErrCode
0x1800084f2  call    cs:__imp_SetLastError
0x1800084f8  mov     rbx, [rsp+28h+arg_0]
0x1800084fd  mov     rsi, [rsp+28h+arg_8]
0x180008502  add     rsp, 20h
0x180008506  pop     rdi
0x180008507  retn
```
