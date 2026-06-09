# WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_std::tuple_long_std::unique_ptr__WCM_ONDEMAND_STATE_INFO_wil::function_deleter_void_(__cdecl_)(void__)_&WcmFree_______RoutePolicyOnDemand::QueryStateInternal_::_3_::_lambda_1___

- ea: `0x1800a1ec4`
- end: `0x1800a201c`
- name: `WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_std::tuple_long_std::unique_ptr__WCM_ONDEMAND_STATE_INFO_wil::function_deleter_void_(__cdecl_)(void__)_&WcmFree_______RoutePolicyOnDemand::QueryStateInternal_::_3_::_lambda_1___`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007bda0`

## callees

- `0x180008394`
- `0x180010080`
- `0x180010560`
- `0x18001d53c`
- `0x180027630`
- `0x18006de30`
- `0x18008534c`
- `0x180098260`
- `0x1800a1c5c`
- `0x1800a1ec4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a1f2c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a1fe0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a1f2c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a1fe0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800a1ff5`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800a1ff5`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_std::tuple_long_std::unique_ptr__WCM_ONDEMAND_STATE_INFO_wil::function_deleter_void____cdecl___void_____WcmFree_______RoutePolicyOnDemand::QueryStateInternal_::_3_::_lambda_1___(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  _DWORD *v6; // rsi
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-49h] BYREF
  __int128 v9; // [rsp+28h] [rbp-41h] BYREF
  _DWORD *v10; // [rsp+40h] [rbp-29h] BYREF
  std::_Ref_count_base *v11; // [rsp+48h] [rbp-21h]
  _BYTE v12[112]; // [rsp+50h] [rbp-19h] BYREF

  v9 = 0;
  lpCriticalSection = 0;
  wil::EnterCriticalSection(&lpCriticalSection, a1 + 8);
  if ( *(_BYTE *)(a1 + 272) )
  {
    *a2 = 0;
    a2[1] = 0;
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
  }
  else
  {
    v6 = operator new(0x80u);
    v10 = v6;
    *(_OWORD *)v6 = 0;
    v6[2] = 1;
    v6[3] = 1;
    *(_QWORD *)v6 = ___7___Ref_count_obj2_V__ThreadPoolWaitableResult_V__tuple_JV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseRequest_RoutePolicyOnDemand__SAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil___std___WcmCommon___std__6B_;
    WcmCommon::ThreadPoolWaitableResult_std::tuple_long_std::unique_ptr__WCM_ONDEMAND_STATE_INFO_wil::function_deleter_void____cdecl___void_____WcmFree_______::ThreadPoolWaitableResult_std::tuple_long_std::unique_ptr__WCM_ONDEMAND_STATE_INFO_wil::function_deleter_void____cdecl___void_____WcmFree_________RoutePolicyOnDemand::QueryStateInternal_::_3_::_lambda_1___(
      v6 + 4,
      a3);
    *(_QWORD *)&v9 = v6 + 4;
    *((_QWORD *)&v9 + 1) = v6;
    if ( *(_DWORD *)a1 == 1 )
    {
      std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(
        &v10,
        &v9);
      std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::push_back(a1 + 192, &v10);
      if ( v11 )
        std::_Ref_count_base::_Decref(v11);
    }
    else
    {
      std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>();
      std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Emplace_back_internal<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(
        (_QWORD *)(a1 + 232),
        (__int64)v12);
      std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(v12);
    }
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    _InterlockedIncrement64((volatile signed __int64 *)(a1 + 136));
    SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 128));
    *a2 = v6 + 4;
    a2[1] = v6;
  }
  return a2;
}

```

## disassembly

```asm
0x1800a1ec4  mov     [rsp-8+arg_10], rbx
0x1800a1ec9  push    rbp
0x1800a1eca  push    rsi
0x1800a1ecb  push    rdi
0x1800a1ecc  push    r14
0x1800a1ece  push    r15
0x1800a1ed0  lea     rbp, [rsp-37h]
0x1800a1ed5  sub     rsp, 0A0h
0x1800a1edc  mov     r15, r8
0x1800a1edf  mov     rbx, rdx
0x1800a1ee2  mov     rdi, rcx
0x1800a1ee5  mov     [rbp+57h+lpCriticalSection], rdx
0x1800a1ee9  xorps   xmm1, xmm1
0x1800a1eec  movdqu  [rbp+57h+var_98], xmm1
0x1800a1ef1  mov     [rbp+57h+lpCriticalSection], 0
0x1800a1ef9  lea     rdx, [rcx+8]
0x1800a1efd  lea     rcx, [rbp+57h+lpCriticalSection]
0x1800a1f01  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800a1f06  nop
0x1800a1f07  cmp     byte ptr [rdi+110h], 0
0x1800a1f0e  jz      short loc_1800A1F37
0x1800a1f10  mov     qword ptr [rbx], 0
0x1800a1f17  mov     qword ptr [rbx+8], 0
0x1800a1f1f  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x1800a1f23  test    rcx, rcx
0x1800a1f26  jz      loc_1800A2002
0x1800a1f2c  call    cs:__imp_LeaveCriticalSection
0x1800a1f32  jmp     loc_1800A2002
0x1800a1f37  mov     ecx, 80h; Size
0x1800a1f3c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a1f41  mov     rsi, rax
0x1800a1f44  mov     [rbp+57h+var_80], rax
0x1800a1f48  xorps   xmm0, xmm0
0x1800a1f4b  movups  xmmword ptr [rax], xmm0
0x1800a1f4e  mov     dword ptr [rax+8], 1
0x1800a1f55  mov     dword ptr [rax+0Ch], 1
0x1800a1f5c  lea     rax, ??_7?$_Ref_count_obj2@V?$ThreadPoolWaitableResult@V?$tuple@JV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseRequest@RoutePolicyOnDemand@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@WcmCommon@@@std@@6B@
0x1800a1f63  mov     [rsi], rax
0x1800a1f66  lea     r14, [rsi+10h]
0x1800a1f6a  mov     rdx, r15
0x1800a1f6d  mov     rcx, r14
0x1800a1f70  call    WcmCommon__ThreadPoolWaitableResult_std__tuple_long_std__unique_ptr__WCM_ONDEMAND_STATE_INFO_wil__function_deleter_void____cdecl___void_____WcmFree_________ThreadPoolWaitableResult_std__tuple_long_std__unique_ptr__WCM_ONDEMAND_STATE_INFO_wil__function_deleter_void____cdecl___void_____WcmFree_________RoutePolicyOnDemand__QueryStateInternal____3____lambda_1___
0x1800a1f75  nop
0x1800a1f76  mov     qword ptr [rbp+57h+var_98], r14
0x1800a1f7a  mov     qword ptr [rbp+57h+var_98+8], rsi
0x1800a1f7e  lea     rdx, [rbp+57h+var_98]
0x1800a1f82  cmp     dword ptr [rdi], 1
0x1800a1f85  jnz     short loc_1800A1FB2
0x1800a1f87  lea     rcx, [rbp+57h+var_80]
0x1800a1f8b  call    ??$?0V?$ThreadPoolWaitableResult@V?$tuple@JV?$unique_ptr@U_WCM_ONDEMAND_STATE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?WcmFree@@YAX0@Z@wil@@@std@@@std@@@WcmCommon@@$0A@@?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@QEAA@AEBV?$shared_ptr@V?$ThreadPoolWaitableResult@V?$tuple@JV?$unique_ptr@U_WCM_ONDEMAND_STATE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?WcmFree@@YAX0@Z@wil@@@std@@@std@@@WcmCommon@@@1@@Z; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<std::tuple<long,std::unique_ptr<_WCM_ONDEMAND_STATE_INFO,wil::function_deleter<void (*)(void *),&WcmFree(void *)>>>>> const &)
0x1800a1f90  nop
0x1800a1f91  lea     rdx, [rbp+57h+var_80]
0x1800a1f95  lea     rcx, [rdi+0C0h]
0x1800a1f9c  call    ?push_back@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@QEAAX$$QEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@Z; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::push_back(std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult> &&)
0x1800a1fa1  nop
0x1800a1fa2  mov     rcx, [rbp+57h+var_78]; this
0x1800a1fa6  test    rcx, rcx
0x1800a1fa9  jz      short loc_1800A1FD7
0x1800a1fab  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a1fb0  jmp     short loc_1800A1FD7
0x1800a1fb2  lea     rcx, [rbp+57h+var_70]
0x1800a1fb6  call    ??$?0AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@std@@$0A@$0A@@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@1@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<bool>> &)
0x1800a1fbb  nop
0x1800a1fbc  lea     rdx, [rbp+57h+var_70]
0x1800a1fc0  lea     rcx, [rdi+0E8h]
0x1800a1fc7  call    ??$_Emplace_back_internal@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@AEAAX$$QEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Emplace_back_internal<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &&)
0x1800a1fcc  nop
0x1800a1fcd  lea     rcx, [rbp+57h+var_70]
0x1800a1fd1  call    ??1?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@XZ; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(void)
0x1800a1fd6  nop
0x1800a1fd7  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x1800a1fdb  test    rcx, rcx
0x1800a1fde  jz      short loc_1800A1FE6
0x1800a1fe0  call    cs:__imp_LeaveCriticalSection
0x1800a1fe6  lock inc qword ptr [rdi+88h]
0x1800a1fee  mov     rcx, [rdi+80h]; pwk
0x1800a1ff5  call    cs:__imp_SubmitThreadpoolWork
0x1800a1ffb  mov     [rbx], r14
0x1800a1ffe  mov     [rbx+8], rsi
0x1800a2002  mov     rax, rbx
0x1800a2005  mov     rbx, [rsp+0C0h+arg_10]
0x1800a200d  add     rsp, 0A0h
0x1800a2014  pop     r15
0x1800a2016  pop     r14
0x1800a2018  pop     rdi
0x1800a2019  pop     rsi
0x1800a201a  pop     rbp
0x1800a201b  retn
```
