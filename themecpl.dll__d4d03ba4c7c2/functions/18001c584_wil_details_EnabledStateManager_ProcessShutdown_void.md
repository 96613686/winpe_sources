# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18001c584`
- end: `0x18001c633`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `175`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180011200`
- `0x1800564f0`

## callees

- `0x18001c584`
- `0x18001cb4c`
- `0x18001f0ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c5af`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c5af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c5cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c5cb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001c60c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001c60c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c5f8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c5f8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001c61b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001c61b`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::ProcessShutdown(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rdi
  struct _TP_TIMER *Ptr; // rax
  struct _TP_TIMER *v4; // rbx
  PTP_TIMER pti; // [rsp+30h] [rbp+8h] BYREF

  LODWORD(this->Ptr) = 0;
  v1 = this + 1;
  Ptr = (struct _TP_TIMER *)this[2].Ptr;
  this[2].Ptr = 0;
  pti = Ptr;
  AcquireSRWLockExclusive(this + 1);
  wil::details::EnabledStateManager::RecordCachedUsageUnderLock(this);
  if ( v1 )
    ReleaseSRWLockExclusive(v1);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    &pti,
    0);
  v4 = pti;
  if ( pti )
  {
    SetThreadpoolTimer(pti, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v4, 1);
    CloseThreadpoolTimer(v4);
  }
}

```

## disassembly

```asm
0x18001c584  mov     [rsp+arg_8], rbx
0x18001c589  push    rdi
0x18001c58a  sub     rsp, 20h
0x18001c58e  mov     dword ptr [rcx], 0
0x18001c594  lea     rdi, [rcx+8]
0x18001c598  mov     rax, [rcx+10h]
0x18001c59c  mov     rbx, rcx
0x18001c59f  mov     qword ptr [rcx+10h], 0
0x18001c5a7  mov     rcx, rdi; SRWLock
0x18001c5aa  mov     [rsp+28h+pti], rax
0x18001c5af  call    cs:__imp_AcquireSRWLockExclusive
0x18001c5b6  nop     dword ptr [rax+rax+00h]
0x18001c5bb  mov     rcx, rbx
0x18001c5be  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18001c5c3  test    rdi, rdi
0x18001c5c6  jz      short loc_18001C5D7
0x18001c5c8  mov     rcx, rdi; SRWLock
0x18001c5cb  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c5d2  nop     dword ptr [rax+rax+00h]
0x18001c5d7  xor     edx, edx
0x18001c5d9  lea     rcx, [rsp+28h+pti]
0x18001c5de  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001c5e3  mov     rbx, [rsp+28h+pti]
0x18001c5e8  test    rbx, rbx
0x18001c5eb  jz      short loc_18001C627
0x18001c5ed  xor     r9d, r9d; msWindowLength
0x18001c5f0  xor     r8d, r8d; msPeriod
0x18001c5f3  xor     edx, edx; pftDueTime
0x18001c5f5  mov     rcx, rbx; pti
0x18001c5f8  call    cs:__imp_SetThreadpoolTimer
0x18001c5ff  nop     dword ptr [rax+rax+00h]
0x18001c604  mov     edx, 1; fCancelPendingCallbacks
0x18001c609  mov     rcx, rbx; pti
0x18001c60c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001c613  nop     dword ptr [rax+rax+00h]
0x18001c618  mov     rcx, rbx; pti
0x18001c61b  call    cs:__imp_CloseThreadpoolTimer
0x18001c622  nop     dword ptr [rax+rax+00h]
0x18001c627  mov     rbx, [rsp+28h+arg_8]
0x18001c62c  add     rsp, 20h
0x18001c630  pop     rdi
0x18001c631  retn
```
