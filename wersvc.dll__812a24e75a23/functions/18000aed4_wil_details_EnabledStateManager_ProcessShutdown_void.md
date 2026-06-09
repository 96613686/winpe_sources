# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000aed4`
- end: `0x18000af68`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800087d4`
- `0x180035180`

## callees

- `0x18000aed4`
- `0x18000b4e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af20`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000af52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000af52`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000aeff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000aeff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000af15`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000af15`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000af41`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000af41`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000af4a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000af4a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000af33`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000af33`

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
0x18000aed4  mov     [rsp+arg_0], rbx
0x18000aed9  mov     [rsp+arg_8], rsi
0x18000aede  push    rdi
0x18000aedf  sub     rsp, 20h
0x18000aee3  mov     dword ptr [rcx], 0
0x18000aee9  lea     rdi, [rcx+8]
0x18000aeed  mov     rsi, [rcx+10h]
0x18000aef1  mov     rbx, rcx
0x18000aef4  mov     qword ptr [rcx+10h], 0
0x18000aefc  mov     rcx, rdi; SRWLock
0x18000aeff  call    cs:__imp_AcquireSRWLockExclusive
0x18000af05  mov     rcx, rbx
0x18000af08  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18000af0d  test    rdi, rdi
0x18000af10  jz      short loc_18000AF1B
0x18000af12  mov     rcx, rdi; SRWLock
0x18000af15  call    cs:__imp_ReleaseSRWLockExclusive
0x18000af1b  test    rsi, rsi
0x18000af1e  jz      short loc_18000AF58
0x18000af20  call    cs:__imp_GetLastError
0x18000af26  xor     r9d, r9d; msWindowLength
0x18000af29  xor     r8d, r8d; msPeriod
0x18000af2c  xor     edx, edx; pftDueTime
0x18000af2e  mov     rcx, rsi; pti
0x18000af31  mov     ebx, eax
0x18000af33  call    cs:__imp_SetThreadpoolTimer
0x18000af39  mov     edx, 1; fCancelPendingCallbacks
0x18000af3e  mov     rcx, rsi; pti
0x18000af41  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000af47  mov     rcx, rsi; pti
0x18000af4a  call    cs:__imp_CloseThreadpoolTimer
0x18000af50  mov     ecx, ebx; dwErrCode
0x18000af52  call    cs:__imp_SetLastError
0x18000af58  mov     rbx, [rsp+28h+arg_0]
0x18000af5d  mov     rsi, [rsp+28h+arg_8]
0x18000af62  add     rsp, 20h
0x18000af66  pop     rdi
0x18000af67  retn
```
