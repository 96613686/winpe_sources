# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x140014630`
- end: `0x1400146c4`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d4cc`
- `0x1400a6e00`

## callees

- `0x140014630`
- `0x140014d74`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x14001468f`
- `KERNEL32!SetThreadpoolTimer` at `0x14001468f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001465b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001465b`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400146a6`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400146a6`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140014671`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140014671`
- `KERNEL32!GetLastError` at `0x14001467c`
- `KERNEL32!GetLastError` at `0x14001467c`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14001469d`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14001469d`
- `KERNEL32!SetLastError` at `0x1400146ae`
- `KERNEL32!SetLastError` at `0x1400146ae`

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
0x140014630  mov     [rsp+arg_0], rbx
0x140014635  mov     [rsp+arg_8], rsi
0x14001463a  push    rdi
0x14001463b  sub     rsp, 20h
0x14001463f  mov     dword ptr [rcx], 0
0x140014645  lea     rdi, [rcx+8]
0x140014649  mov     rsi, [rcx+10h]
0x14001464d  mov     rbx, rcx
0x140014650  mov     qword ptr [rcx+10h], 0
0x140014658  mov     rcx, rdi; SRWLock
0x14001465b  call    cs:__imp_AcquireSRWLockExclusive
0x140014661  mov     rcx, rbx
0x140014664  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x140014669  test    rdi, rdi
0x14001466c  jz      short loc_140014677
0x14001466e  mov     rcx, rdi; SRWLock
0x140014671  call    cs:__imp_ReleaseSRWLockExclusive
0x140014677  test    rsi, rsi
0x14001467a  jz      short loc_1400146B4
0x14001467c  call    cs:__imp_GetLastError
0x140014682  xor     r9d, r9d; msWindowLength
0x140014685  xor     r8d, r8d; msPeriod
0x140014688  xor     edx, edx; pftDueTime
0x14001468a  mov     rcx, rsi; pti
0x14001468d  mov     ebx, eax
0x14001468f  call    cs:__imp_SetThreadpoolTimer
0x140014695  mov     edx, 1; fCancelPendingCallbacks
0x14001469a  mov     rcx, rsi; pti
0x14001469d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400146a3  mov     rcx, rsi; pti
0x1400146a6  call    cs:__imp_CloseThreadpoolTimer
0x1400146ac  mov     ecx, ebx; dwErrCode
0x1400146ae  call    cs:__imp_SetLastError
0x1400146b4  mov     rbx, [rsp+28h+arg_0]
0x1400146b9  mov     rsi, [rsp+28h+arg_8]
0x1400146be  add     rsp, 20h
0x1400146c2  pop     rdi
0x1400146c3  retn
```
