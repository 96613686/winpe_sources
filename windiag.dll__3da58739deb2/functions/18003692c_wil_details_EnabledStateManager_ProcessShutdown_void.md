# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18003692c`
- end: `0x1800369c0`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180033d90`
- `0x18009bb80`

## callees

- `0x18003692c`
- `0x180036d78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180036957`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180036957`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003696d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003696d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800369aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800369aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036978`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036978`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180036999`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180036999`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800369a2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800369a2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003698b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003698b`

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
0x18003692c  mov     [rsp+arg_0], rbx
0x180036931  mov     [rsp+arg_8], rsi
0x180036936  push    rdi
0x180036937  sub     rsp, 20h
0x18003693b  mov     dword ptr [rcx], 0
0x180036941  lea     rdi, [rcx+8]
0x180036945  mov     rsi, [rcx+10h]
0x180036949  mov     rbx, rcx
0x18003694c  mov     qword ptr [rcx+10h], 0
0x180036954  mov     rcx, rdi; SRWLock
0x180036957  call    cs:__imp_AcquireSRWLockExclusive
0x18003695d  mov     rcx, rbx
0x180036960  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180036965  test    rdi, rdi
0x180036968  jz      short loc_180036973
0x18003696a  mov     rcx, rdi; SRWLock
0x18003696d  call    cs:__imp_ReleaseSRWLockExclusive
0x180036973  test    rsi, rsi
0x180036976  jz      short loc_1800369B0
0x180036978  call    cs:__imp_GetLastError
0x18003697e  xor     r9d, r9d; msWindowLength
0x180036981  xor     r8d, r8d; msPeriod
0x180036984  xor     edx, edx; pftDueTime
0x180036986  mov     rcx, rsi; pti
0x180036989  mov     ebx, eax
0x18003698b  call    cs:__imp_SetThreadpoolTimer
0x180036991  mov     edx, 1; fCancelPendingCallbacks
0x180036996  mov     rcx, rsi; pti
0x180036999  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003699f  mov     rcx, rsi; pti
0x1800369a2  call    cs:__imp_CloseThreadpoolTimer
0x1800369a8  mov     ecx, ebx; dwErrCode
0x1800369aa  call    cs:__imp_SetLastError
0x1800369b0  mov     rbx, [rsp+28h+arg_0]
0x1800369b5  mov     rsi, [rsp+28h+arg_8]
0x1800369ba  add     rsp, 20h
0x1800369be  pop     rdi
0x1800369bf  retn
```
