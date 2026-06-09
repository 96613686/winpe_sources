# WcmCommon::ThreadPoolWorkQueue::SubmitWork__NlmManager::NlmServiceStateChangeCallback_::_6_::_lambda_1___

- ea: `0x1800c8078`
- end: `0x1800c8108`
- name: `WcmCommon::ThreadPoolWorkQueue::SubmitWork__NlmManager::NlmServiceStateChangeCallback_::_6_::_lambda_1___`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800ca020`

## callees

- `0x180027630`
- `0x1800c8078`
- `0x1800c8998`
- `0x1800c8a4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c80b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c80e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c80b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c80e2`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800c80f7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800c80f7`

## pseudocode

```c
void __fastcall WcmCommon::ThreadPoolWorkQueue::SubmitWork__NlmManager::NlmServiceStateChangeCallback_::_6_::_lambda_1___(
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
      std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__NlmManager::NlmServiceStateChangeCallback_::_6_::_lambda_1___(
        a1 + 152,
        a2);
    else
      std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__NlmManager::NlmServiceStateChangeCallback_::_6_::_lambda_1___(
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
0x1800c8078  mov     [rsp+arg_8], rbx
0x1800c807d  push    rdi
0x1800c807e  sub     rsp, 30h
0x1800c8082  mov     rdi, rdx
0x1800c8085  mov     rbx, rcx
0x1800c8088  mov     [rsp+38h+lpCriticalSection], 0
0x1800c8091  lea     rdx, [rcx+8]
0x1800c8095  lea     rcx, [rsp+38h+lpCriticalSection]
0x1800c809a  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800c809f  nop
0x1800c80a0  lea     rcx, [rbx+98h]
0x1800c80a7  cmp     byte ptr [rcx+78h], 0
0x1800c80ab  jz      short loc_1800C80BF
0x1800c80ad  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x1800c80b2  test    rcx, rcx
0x1800c80b5  jz      short loc_1800C80FD
0x1800c80b7  call    cs:__imp_LeaveCriticalSection
0x1800c80bd  jmp     short loc_1800C80FD
0x1800c80bf  mov     rdx, rdi
0x1800c80c2  cmp     dword ptr [rbx], 1
0x1800c80c5  jnz     short loc_1800C80CE
0x1800c80c7  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__NlmManager__NlmServiceStateChangeCallback____6____lambda_1___
0x1800c80cc  jmp     short loc_1800C80D8
0x1800c80ce  add     rcx, 50h ; 'P'
0x1800c80d2  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__NlmManager__NlmServiceStateChangeCallback____6____lambda_1___
0x1800c80d7  nop
0x1800c80d8  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x1800c80dd  test    rcx, rcx
0x1800c80e0  jz      short loc_1800C80E8
0x1800c80e2  call    cs:__imp_LeaveCriticalSection
0x1800c80e8  lock inc qword ptr [rbx+88h]
0x1800c80f0  mov     rcx, [rbx+80h]; pwk
0x1800c80f7  call    cs:__imp_SubmitThreadpoolWork
0x1800c80fd  mov     rbx, [rsp+38h+arg_8]
0x1800c8102  add     rsp, 30h
0x1800c8106  pop     rdi
0x1800c8107  retn
```
