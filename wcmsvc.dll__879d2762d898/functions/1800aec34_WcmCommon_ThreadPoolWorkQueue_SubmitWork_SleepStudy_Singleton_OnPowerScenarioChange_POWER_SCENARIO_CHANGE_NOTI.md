# WcmCommon::ThreadPoolWorkQueue::SubmitWork<``SleepStudy::Singleton::OnPowerScenarioChange(_POWER_SCENARIO_CHANGE_NOTIFICATION_DATA const &)'::`24'::_lambda_1_::operator()(void)'::`6'::_lambda_1_>(``SleepStudy::Singleton::OnPowerScenarioChange(_POWER_SCENARIO_CHANGE_NOTIFICATION_DATA const &)'::`24'::_lambda_1_::operator()(void)'::`6'::_lambda_1_ &&)

- ea: `0x1800aec34`
- end: `0x1800aecc4`
- name: `??$SubmitWork@V_lambda_1_@?5???R1?BI@??OnPowerScenarioChange@Singleton@SleepStudy@@AEAAXAEBU_POWER_SCENARIO_CHANGE_NOTIFICATION_DATA@@@Z@QEBA@XZ@@ThreadPoolWorkQueue@WcmCommon@@QEAAX$$QEAV_lambda_1_@?5???R2?BI@??OnPowerScenarioChange@Singleton@SleepStudy@@AEAAXAEBU_POWER_SCENARIO_CHANGE_NOTIFICATION_DATA@@@Z@QEBA@XZ@@Z`
- size: `144`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18004ca10`

## callees

- `0x180027630`
- `0x1800aec34`
- `0x1800affb0`
- `0x1800b004c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800aec73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800aec9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800aec73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800aec9e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800aecb3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800aecb3`

## pseudocode

```c
void __fastcall XZ::QEBA::Z::SubmitWork<``SleepStudy::Singleton::OnPowerScenarioChange'::`24'::_lambda_1_::operator()'::`6'::_lambda_1_,AXAEBU_POWER_SCENARIO_CHANGE_NOTIFICATION_DATA &>(
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
      ___emplace_back_V_lambda_1___5___R1_BI___OnPowerScenarioChange_Singleton_SleepStudy__AEAAXAEBU_POWER_SCENARIO_CHANGE_NOTIFICATION_DATA___Z_QEBA_XZ____deque_V__function___A6AXXZ_std__V__allocator_V__function___A6AXXZ_std___2__std__QEAAAEAV__function___A6AXXZ_1___QEAV_lambda_1___5___R3_BI___OnPowerScenarioChange_Singleton_SleepStudy__AEAAXAEBU_POWER_SCENARIO_CHANGE_NOTIFICATION_DATA___Z_QEBA_XZ__Z(
        a1 + 152,
        a2);
    else
      ___emplace_back_V_lambda_1___5___R1_BI___OnPowerScenarioChange_Singleton_SleepStudy__AEAAXAEBU_POWER_SCENARIO_CHANGE_NOTIFICATION_DATA___Z_QEBA_XZ____deque_V__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__std__V__allocator_V__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__std___2__std__QEAAAEAV__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__1___QEAV_lambda_1___5___R3_BI___OnPowerScenarioChange_Singleton_SleepStudy__AEAAXAEBU_POWER_SCENARIO_CHANGE_NOTIFICATION_DATA___Z_QEBA_XZ__Z(
        (_QWORD *)(a1 + 232),
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
0x1800aec34  mov     [rsp+arg_10], rbx
0x1800aec39  push    rdi
0x1800aec3a  sub     rsp, 30h
0x1800aec3e  mov     rdi, rdx
0x1800aec41  mov     rbx, rcx
0x1800aec44  mov     [rsp+38h+lpCriticalSection], 0
0x1800aec4d  lea     rdx, [rcx+8]
0x1800aec51  lea     rcx, [rsp+38h+lpCriticalSection]
0x1800aec56  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800aec5b  nop
0x1800aec5c  lea     rcx, [rbx+98h]
0x1800aec63  cmp     byte ptr [rcx+78h], 0
0x1800aec67  jz      short loc_1800AEC7B
0x1800aec69  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x1800aec6e  test    rcx, rcx
0x1800aec71  jz      short loc_1800AECB9
0x1800aec73  call    cs:__imp_LeaveCriticalSection
0x1800aec79  jmp     short loc_1800AECB9
0x1800aec7b  mov     rdx, rdi
0x1800aec7e  cmp     dword ptr [rbx], 1
0x1800aec81  jnz     short loc_1800AEC8A
0x1800aec83  call    ??$emplace_back@V_lambda_1_@?5???R1?BI@??OnPowerScenarioChange@Singleton@SleepStudy@@AEAAXAEBU_POWER_SCENARIO_CHANGE_NOTIFICATION_DATA@@@Z@QEBA@XZ@@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAAAEAV?$function@$$A6AXXZ@1@$$QEAV_lambda_1_@?5???R3?BI@??OnPowerScenarioChange@Singleton@SleepStudy@@AEAAXAEBU_POWER_SCENARIO_CHANGE_NOTIFICATION_DATA@@@Z@QEBA@XZ@@Z; std::deque<std::function<void (void)>>::emplace_back<``SleepStudy::Singleton::OnPowerScenarioChange(_POWER_SCENARIO_CHANGE_NOTIFICATION_DATA const &)'::`24'::_lambda_1_::operator()(void)'::`6'::_lambda_1_>(``SleepStudy::Singleton::OnPowerScenarioChange(_POWER_SCENARIO_CHANGE_NOTIFICATION_DATA const &)'::`24'::_lambda_1_::operator()(void)'::`6'::_lambda_1_ &&)
0x1800aec88  jmp     short loc_1800AEC94
0x1800aec8a  add     rcx, 50h ; 'P'
0x1800aec8e  call    ??$emplace_back@V_lambda_1_@?5???R1?BI@??OnPowerScenarioChange@Singleton@SleepStudy@@AEAAXAEBU_POWER_SCENARIO_CHANGE_NOTIFICATION_DATA@@@Z@QEBA@XZ@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@QEAAAEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@$$QEAV_lambda_1_@?5???R3?BI@??OnPowerScenarioChange@Singleton@SleepStudy@@AEAAXAEBU_POWER_SCENARIO_CHANGE_NOTIFICATION_DATA@@@Z@QEBA@XZ@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::emplace_back<``SleepStudy::Singleton::OnPowerScenarioChange(_POWER_SCENARIO_CHANGE_NOTIFICATION_DATA const &)'::`24'::_lambda_1_::operator()(void)'::`6'::_lambda_1_>(``SleepStudy::Singleton::OnPowerScenarioChange(_POWER_SCENARIO_CHANGE_NOTIFICATION_DATA const &)'::`24'::_lambda_1_::operator()(void)'::`6'::_lambda_1_ &&)
0x1800aec93  nop
0x1800aec94  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x1800aec99  test    rcx, rcx
0x1800aec9c  jz      short loc_1800AECA4
0x1800aec9e  call    cs:__imp_LeaveCriticalSection
0x1800aeca4  lock inc qword ptr [rbx+88h]
0x1800aecac  mov     rcx, [rbx+80h]; pwk
0x1800aecb3  call    cs:__imp_SubmitThreadpoolWork
0x1800aecb9  mov     rbx, [rsp+38h+arg_10]
0x1800aecbe  add     rsp, 30h
0x1800aecc2  pop     rdi
0x1800aecc3  retn
```
