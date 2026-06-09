# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x14000a0bc`
- end: `0x14000a150`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140008c78`
- `0x140015760`

## callees

- `0x14000a0bc`
- `0x14000a6c4`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000a13a`
- `KERNEL32!SetLastError` at `0x14000a13a`
- `KERNEL32!GetLastError` at `0x14000a108`
- `KERNEL32!GetLastError` at `0x14000a108`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000a0e7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000a0e7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000a0fd`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000a0fd`
- `KERNEL32!SetThreadpoolTimer` at `0x14000a11b`
- `KERNEL32!SetThreadpoolTimer` at `0x14000a11b`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000a132`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000a132`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000a129`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000a129`

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
0x14000a0bc  mov     [rsp+arg_0], rbx
0x14000a0c1  mov     [rsp+arg_8], rsi
0x14000a0c6  push    rdi
0x14000a0c7  sub     rsp, 20h
0x14000a0cb  mov     dword ptr [rcx], 0
0x14000a0d1  lea     rdi, [rcx+8]
0x14000a0d5  mov     rsi, [rcx+10h]
0x14000a0d9  mov     rbx, rcx
0x14000a0dc  mov     qword ptr [rcx+10h], 0
0x14000a0e4  mov     rcx, rdi; SRWLock
0x14000a0e7  call    cs:__imp_AcquireSRWLockExclusive
0x14000a0ed  mov     rcx, rbx
0x14000a0f0  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x14000a0f5  test    rdi, rdi
0x14000a0f8  jz      short loc_14000A103
0x14000a0fa  mov     rcx, rdi; SRWLock
0x14000a0fd  call    cs:__imp_ReleaseSRWLockExclusive
0x14000a103  test    rsi, rsi
0x14000a106  jz      short loc_14000A140
0x14000a108  call    cs:__imp_GetLastError
0x14000a10e  xor     r9d, r9d; msWindowLength
0x14000a111  xor     r8d, r8d; msPeriod
0x14000a114  xor     edx, edx; pftDueTime
0x14000a116  mov     rcx, rsi; pti
0x14000a119  mov     ebx, eax
0x14000a11b  call    cs:__imp_SetThreadpoolTimer
0x14000a121  mov     edx, 1; fCancelPendingCallbacks
0x14000a126  mov     rcx, rsi; pti
0x14000a129  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000a12f  mov     rcx, rsi; pti
0x14000a132  call    cs:__imp_CloseThreadpoolTimer
0x14000a138  mov     ecx, ebx; dwErrCode
0x14000a13a  call    cs:__imp_SetLastError
0x14000a140  mov     rbx, [rsp+28h+arg_0]
0x14000a145  mov     rsi, [rsp+28h+arg_8]
0x14000a14a  add     rsp, 20h
0x14000a14e  pop     rdi
0x14000a14f  retn
```
