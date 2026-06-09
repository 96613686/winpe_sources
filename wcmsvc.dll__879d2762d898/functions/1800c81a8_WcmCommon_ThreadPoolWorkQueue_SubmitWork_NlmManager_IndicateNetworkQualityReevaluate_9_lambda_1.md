# WcmCommon::ThreadPoolWorkQueue::SubmitWork__NlmManager::IndicateNetworkQualityReevaluate_::_9_::_lambda_1___

- ea: `0x1800c81a8`
- end: `0x1800c8238`
- name: `WcmCommon::ThreadPoolWorkQueue::SubmitWork__NlmManager::IndicateNetworkQualityReevaluate_::_9_::_lambda_1___`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180020d18`

## callees

- `0x180027630`
- `0x1800c81a8`
- `0x1800c8c70`
- `0x1800c8d24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c81e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c8212`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c81e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c8212`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800c8227`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800c8227`

## pseudocode

```c
void __fastcall WcmCommon::ThreadPoolWorkQueue::SubmitWork__NlmManager::IndicateNetworkQualityReevaluate_::_9_::_lambda_1___(
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
      std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__NlmManager::IndicateNetworkQualityReevaluate_::_9_::_lambda_1___(
        a1 + 152,
        a2);
    else
      std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__NlmManager::IndicateNetworkQualityReevaluate_::_9_::_lambda_1___(
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
0x1800c81a8  mov     [rsp+arg_8], rbx
0x1800c81ad  push    rdi
0x1800c81ae  sub     rsp, 30h
0x1800c81b2  mov     rdi, rdx
0x1800c81b5  mov     rbx, rcx
0x1800c81b8  mov     [rsp+38h+lpCriticalSection], 0
0x1800c81c1  lea     rdx, [rcx+8]
0x1800c81c5  lea     rcx, [rsp+38h+lpCriticalSection]
0x1800c81ca  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800c81cf  nop
0x1800c81d0  lea     rcx, [rbx+98h]
0x1800c81d7  cmp     byte ptr [rcx+78h], 0
0x1800c81db  jz      short loc_1800C81EF
0x1800c81dd  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x1800c81e2  test    rcx, rcx
0x1800c81e5  jz      short loc_1800C822D
0x1800c81e7  call    cs:__imp_LeaveCriticalSection
0x1800c81ed  jmp     short loc_1800C822D
0x1800c81ef  mov     rdx, rdi
0x1800c81f2  cmp     dword ptr [rbx], 1
0x1800c81f5  jnz     short loc_1800C81FE
0x1800c81f7  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__NlmManager__IndicateNetworkQualityReevaluate____9____lambda_1___
0x1800c81fc  jmp     short loc_1800C8208
0x1800c81fe  add     rcx, 50h ; 'P'
0x1800c8202  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__NlmManager__IndicateNetworkQualityReevaluate____9____lambda_1___
0x1800c8207  nop
0x1800c8208  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x1800c820d  test    rcx, rcx
0x1800c8210  jz      short loc_1800C8218
0x1800c8212  call    cs:__imp_LeaveCriticalSection
0x1800c8218  lock inc qword ptr [rbx+88h]
0x1800c8220  mov     rcx, [rbx+80h]; pwk
0x1800c8227  call    cs:__imp_SubmitThreadpoolWork
0x1800c822d  mov     rbx, [rsp+38h+arg_8]
0x1800c8232  add     rsp, 30h
0x1800c8236  pop     rdi
0x1800c8237  retn
```
