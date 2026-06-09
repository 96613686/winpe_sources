# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000725c`
- end: `0x1800072f0`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000499c`
- `0x180032730`

## callees

- `0x18000725c`
- `0x1800076f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000729d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000729d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007287`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007287`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800072a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800072a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800072da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800072da`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800072d2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800072d2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800072bb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800072bb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800072c9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800072c9`

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
0x18000725c  mov     [rsp+arg_0], rbx
0x180007261  mov     [rsp+arg_8], rsi
0x180007266  push    rdi
0x180007267  sub     rsp, 20h
0x18000726b  mov     dword ptr [rcx], 0
0x180007271  lea     rdi, [rcx+8]
0x180007275  mov     rsi, [rcx+10h]
0x180007279  mov     rbx, rcx
0x18000727c  mov     qword ptr [rcx+10h], 0
0x180007284  mov     rcx, rdi; SRWLock
0x180007287  call    cs:__imp_AcquireSRWLockExclusive
0x18000728d  mov     rcx, rbx
0x180007290  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180007295  test    rdi, rdi
0x180007298  jz      short loc_1800072A3
0x18000729a  mov     rcx, rdi; SRWLock
0x18000729d  call    cs:__imp_ReleaseSRWLockExclusive
0x1800072a3  test    rsi, rsi
0x1800072a6  jz      short loc_1800072E0
0x1800072a8  call    cs:__imp_GetLastError
0x1800072ae  xor     r9d, r9d; msWindowLength
0x1800072b1  xor     r8d, r8d; msPeriod
0x1800072b4  xor     edx, edx; pftDueTime
0x1800072b6  mov     rcx, rsi; pti
0x1800072b9  mov     ebx, eax
0x1800072bb  call    cs:__imp_SetThreadpoolTimer
0x1800072c1  mov     edx, 1; fCancelPendingCallbacks
0x1800072c6  mov     rcx, rsi; pti
0x1800072c9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800072cf  mov     rcx, rsi; pti
0x1800072d2  call    cs:__imp_CloseThreadpoolTimer
0x1800072d8  mov     ecx, ebx; dwErrCode
0x1800072da  call    cs:__imp_SetLastError
0x1800072e0  mov     rbx, [rsp+28h+arg_0]
0x1800072e5  mov     rsi, [rsp+28h+arg_8]
0x1800072ea  add     rsp, 20h
0x1800072ee  pop     rdi
0x1800072ef  retn
```
