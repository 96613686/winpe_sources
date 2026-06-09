# WcmCommon::ThreadPoolWorkQueue::SubmitWork__NlmManager::NlmServiceStateChangeCallback_::_11_::_lambda_2___

- ea: `0x1800c8240`
- end: `0x1800c82d0`
- name: `WcmCommon::ThreadPoolWorkQueue::SubmitWork__NlmManager::NlmServiceStateChangeCallback_::_11_::_lambda_2___`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800ca020`

## callees

- `0x180027630`
- `0x1800c8240`
- `0x1800c8ddc`
- `0x1800c8e90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c827f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c82aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c827f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c82aa`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800c82bf`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800c82bf`

## pseudocode

```c
void __fastcall WcmCommon::ThreadPoolWorkQueue::SubmitWork__NlmManager::NlmServiceStateChangeCallback_::_11_::_lambda_2___(
        __int64 a1,
        __int64 a2)
{
  LPCRITICAL_SECTION lpCriticalSection[3]; // [rsp+20h] [rbp-18h] BYREF

  lpCriticalSection[0] = 0;
  wil::EnterCriticalSection(lpCriticalSection, a1 + 8);
  if ( *(_BYTE *)(a1 + 272) )
  {
    if ( lpCriticalSection[0] )
      LeaveCriticalSection(lpCriticalSection[0]);
  }
  else
  {
    if ( *(_DWORD *)a1 == 1 )
      std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__NlmManager::NlmServiceStateChangeCallback_::_11_::_lambda_2___(
        a1 + 152,
        a2);
    else
      std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__NlmManager::NlmServiceStateChangeCallback_::_11_::_lambda_2___(
        a1 + 232,
        a2);
    if ( lpCriticalSection[0] )
      LeaveCriticalSection(lpCriticalSection[0]);
    _InterlockedIncrement64((volatile signed __int64 *)(a1 + 136));
    SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 128));
  }
}

```

## disassembly

```asm
0x1800c8240  mov     [rsp+arg_8], rbx
0x1800c8245  push    rdi
0x1800c8246  sub     rsp, 30h
0x1800c824a  mov     rdi, rdx
0x1800c824d  mov     rbx, rcx
0x1800c8250  mov     [rsp+38h+lpCriticalSection], 0
0x1800c8259  lea     rdx, [rcx+8]
0x1800c825d  lea     rcx, [rsp+38h+lpCriticalSection]
0x1800c8262  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800c8267  nop
0x1800c8268  lea     rcx, [rbx+98h]
0x1800c826f  cmp     byte ptr [rcx+78h], 0
0x1800c8273  jz      short loc_1800C8287
0x1800c8275  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x1800c827a  test    rcx, rcx
0x1800c827d  jz      short loc_1800C82C5
0x1800c827f  call    cs:__imp_LeaveCriticalSection
0x1800c8285  jmp     short loc_1800C82C5
0x1800c8287  mov     rdx, rdi
0x1800c828a  cmp     dword ptr [rbx], 1
0x1800c828d  jnz     short loc_1800C8296
0x1800c828f  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__NlmManager__NlmServiceStateChangeCallback____11____lambda_2___
0x1800c8294  jmp     short loc_1800C82A0
0x1800c8296  add     rcx, 50h ; 'P'
0x1800c829a  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__NlmManager__NlmServiceStateChangeCallback____11____lambda_2___
0x1800c829f  nop
0x1800c82a0  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x1800c82a5  test    rcx, rcx
0x1800c82a8  jz      short loc_1800C82B0
0x1800c82aa  call    cs:__imp_LeaveCriticalSection
0x1800c82b0  lock inc qword ptr [rbx+88h]
0x1800c82b8  mov     rcx, [rbx+80h]; pwk
0x1800c82bf  call    cs:__imp_SubmitThreadpoolWork
0x1800c82c5  mov     rbx, [rsp+38h+arg_8]
0x1800c82ca  add     rsp, 30h
0x1800c82ce  pop     rdi
0x1800c82cf  retn
```
