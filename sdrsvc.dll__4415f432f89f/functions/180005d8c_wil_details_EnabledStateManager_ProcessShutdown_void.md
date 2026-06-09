# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x180005d8c`
- end: `0x180005e20`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003468`
- `0x180021be0`

## callees

- `0x180005d8c`
- `0x1800061b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005db7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005db7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005dcd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005dcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005dd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005dd8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005e0a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005e0a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005e02`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005e02`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005deb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005deb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005df9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005df9`

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
0x180005d8c  mov     [rsp+arg_0], rbx
0x180005d91  mov     [rsp+arg_8], rsi
0x180005d96  push    rdi
0x180005d97  sub     rsp, 20h
0x180005d9b  mov     dword ptr [rcx], 0
0x180005da1  lea     rdi, [rcx+8]
0x180005da5  mov     rsi, [rcx+10h]
0x180005da9  mov     rbx, rcx
0x180005dac  mov     qword ptr [rcx+10h], 0
0x180005db4  mov     rcx, rdi; SRWLock
0x180005db7  call    cs:__imp_AcquireSRWLockExclusive
0x180005dbd  mov     rcx, rbx
0x180005dc0  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180005dc5  test    rdi, rdi
0x180005dc8  jz      short loc_180005DD3
0x180005dca  mov     rcx, rdi; SRWLock
0x180005dcd  call    cs:__imp_ReleaseSRWLockExclusive
0x180005dd3  test    rsi, rsi
0x180005dd6  jz      short loc_180005E10
0x180005dd8  call    cs:__imp_GetLastError
0x180005dde  xor     r9d, r9d; msWindowLength
0x180005de1  xor     r8d, r8d; msPeriod
0x180005de4  xor     edx, edx; pftDueTime
0x180005de6  mov     rcx, rsi; pti
0x180005de9  mov     ebx, eax
0x180005deb  call    cs:__imp_SetThreadpoolTimer
0x180005df1  mov     edx, 1; fCancelPendingCallbacks
0x180005df6  mov     rcx, rsi; pti
0x180005df9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005dff  mov     rcx, rsi; pti
0x180005e02  call    cs:__imp_CloseThreadpoolTimer
0x180005e08  mov     ecx, ebx; dwErrCode
0x180005e0a  call    cs:__imp_SetLastError
0x180005e10  mov     rbx, [rsp+28h+arg_0]
0x180005e15  mov     rsi, [rsp+28h+arg_8]
0x180005e1a  add     rsp, 20h
0x180005e1e  pop     rdi
0x180005e1f  retn
```
