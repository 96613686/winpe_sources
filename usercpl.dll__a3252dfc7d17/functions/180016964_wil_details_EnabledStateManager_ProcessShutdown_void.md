# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x180016964`
- end: `0x1800169f8`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800133e0`
- `0x1800777f0`

## callees

- `0x180016964`
- `0x180016da8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800169a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800169a5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001698f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001698f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800169b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800169b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800169e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800169e2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800169d1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800169d1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800169c3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800169c3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800169da`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800169da`

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
0x180016964  mov     [rsp+arg_0], rbx
0x180016969  mov     [rsp+arg_8], rsi
0x18001696e  push    rdi
0x18001696f  sub     rsp, 20h
0x180016973  mov     dword ptr [rcx], 0
0x180016979  lea     rdi, [rcx+8]
0x18001697d  mov     rsi, [rcx+10h]
0x180016981  mov     rbx, rcx
0x180016984  mov     qword ptr [rcx+10h], 0
0x18001698c  mov     rcx, rdi; SRWLock
0x18001698f  call    cs:__imp_AcquireSRWLockExclusive
0x180016995  mov     rcx, rbx
0x180016998  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18001699d  test    rdi, rdi
0x1800169a0  jz      short loc_1800169AB
0x1800169a2  mov     rcx, rdi; SRWLock
0x1800169a5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800169ab  test    rsi, rsi
0x1800169ae  jz      short loc_1800169E8
0x1800169b0  call    cs:__imp_GetLastError
0x1800169b6  xor     r9d, r9d; msWindowLength
0x1800169b9  xor     r8d, r8d; msPeriod
0x1800169bc  xor     edx, edx; pftDueTime
0x1800169be  mov     rcx, rsi; pti
0x1800169c1  mov     ebx, eax
0x1800169c3  call    cs:__imp_SetThreadpoolTimer
0x1800169c9  mov     edx, 1; fCancelPendingCallbacks
0x1800169ce  mov     rcx, rsi; pti
0x1800169d1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800169d7  mov     rcx, rsi; pti
0x1800169da  call    cs:__imp_CloseThreadpoolTimer
0x1800169e0  mov     ecx, ebx; dwErrCode
0x1800169e2  call    cs:__imp_SetLastError
0x1800169e8  mov     rbx, [rsp+28h+arg_0]
0x1800169ed  mov     rsi, [rsp+28h+arg_8]
0x1800169f2  add     rsp, 20h
0x1800169f6  pop     rdi
0x1800169f7  retn
```
