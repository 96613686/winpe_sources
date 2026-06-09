# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000a390`
- end: `0x18000a424`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800056a0`
- `0x18007c2a0`

## callees

- `0x18000a390`
- `0x18000aac4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a3bb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a3bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a3d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a3d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a3dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a3dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a40e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a40e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a3ef`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a3ef`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a3fd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a3fd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a406`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a406`

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
0x18000a390  mov     [rsp+arg_0], rbx
0x18000a395  mov     [rsp+arg_8], rsi
0x18000a39a  push    rdi
0x18000a39b  sub     rsp, 20h
0x18000a39f  mov     dword ptr [rcx], 0
0x18000a3a5  lea     rdi, [rcx+8]
0x18000a3a9  mov     rsi, [rcx+10h]
0x18000a3ad  mov     rbx, rcx
0x18000a3b0  mov     qword ptr [rcx+10h], 0
0x18000a3b8  mov     rcx, rdi; SRWLock
0x18000a3bb  call    cs:__imp_AcquireSRWLockExclusive
0x18000a3c1  mov     rcx, rbx
0x18000a3c4  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18000a3c9  test    rdi, rdi
0x18000a3cc  jz      short loc_18000A3D7
0x18000a3ce  mov     rcx, rdi; SRWLock
0x18000a3d1  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a3d7  test    rsi, rsi
0x18000a3da  jz      short loc_18000A414
0x18000a3dc  call    cs:__imp_GetLastError
0x18000a3e2  xor     r9d, r9d; msWindowLength
0x18000a3e5  xor     r8d, r8d; msPeriod
0x18000a3e8  xor     edx, edx; pftDueTime
0x18000a3ea  mov     rcx, rsi; pti
0x18000a3ed  mov     ebx, eax
0x18000a3ef  call    cs:__imp_SetThreadpoolTimer
0x18000a3f5  mov     edx, 1; fCancelPendingCallbacks
0x18000a3fa  mov     rcx, rsi; pti
0x18000a3fd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a403  mov     rcx, rsi; pti
0x18000a406  call    cs:__imp_CloseThreadpoolTimer
0x18000a40c  mov     ecx, ebx; dwErrCode
0x18000a40e  call    cs:__imp_SetLastError
0x18000a414  mov     rbx, [rsp+28h+arg_0]
0x18000a419  mov     rsi, [rsp+28h+arg_8]
0x18000a41e  add     rsp, 20h
0x18000a422  pop     rdi
0x18000a423  retn
```
