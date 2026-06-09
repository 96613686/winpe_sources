# WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_std::tuple_long_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void_(__cdecl_)(void__)_noexcept_&RoutePolicyOnDemand::CloseRequest_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_________RoutePolicyOnDemand::OpenRequestInternal_::_3_::_lambda_1___

- ea: `0x1800a1d64`
- end: `0x1800a1ebc`
- name: `WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_std::tuple_long_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void_(__cdecl_)(void__)_noexcept_&RoutePolicyOnDemand::CloseRequest_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_________RoutePolicyOnDemand::OpenRequestInternal_::_3_::_lambda_1___`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800638c4`

## callees

- `0x180008394`
- `0x180010080`
- `0x180010560`
- `0x18001d53c`
- `0x180027630`
- `0x18006de30`
- `0x18008534c`
- `0x180098260`
- `0x1800a1b94`
- `0x1800a1d64`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a1dcc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a1e80`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a1dcc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a1e80`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800a1e95`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800a1e95`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_std::tuple_long_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__RoutePolicyOnDemand::CloseRequest_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_________RoutePolicyOnDemand::OpenRequestInternal_::_3_::_lambda_1___(
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
    WcmCommon::ThreadPoolWaitableResult_std::tuple_long_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__RoutePolicyOnDemand::CloseRequest_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_________::ThreadPoolWaitableResult_std::tuple_long_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__RoutePolicyOnDemand::CloseRequest_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t___________RoutePolicyOnDemand::OpenRequestInternal_::_3_::_lambda_1___(
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
0x1800a1d64  mov     [rsp-8+arg_18], rbx
0x1800a1d69  push    rbp
0x1800a1d6a  push    rsi
0x1800a1d6b  push    rdi
0x1800a1d6c  push    r14
0x1800a1d6e  push    r15
0x1800a1d70  lea     rbp, [rsp-37h]
0x1800a1d75  sub     rsp, 0A0h
0x1800a1d7c  mov     r15, r8
0x1800a1d7f  mov     rbx, rdx
0x1800a1d82  mov     rdi, rcx
0x1800a1d85  mov     [rbp+57h+lpCriticalSection], rdx
0x1800a1d89  xorps   xmm1, xmm1
0x1800a1d8c  movdqu  [rbp+57h+var_98], xmm1
0x1800a1d91  mov     [rbp+57h+lpCriticalSection], 0
0x1800a1d99  lea     rdx, [rcx+8]
0x1800a1d9d  lea     rcx, [rbp+57h+lpCriticalSection]
0x1800a1da1  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800a1da6  nop
0x1800a1da7  cmp     byte ptr [rdi+110h], 0
0x1800a1dae  jz      short loc_1800A1DD7
0x1800a1db0  mov     qword ptr [rbx], 0
0x1800a1db7  mov     qword ptr [rbx+8], 0
0x1800a1dbf  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x1800a1dc3  test    rcx, rcx
0x1800a1dc6  jz      loc_1800A1EA2
0x1800a1dcc  call    cs:__imp_LeaveCriticalSection
0x1800a1dd2  jmp     loc_1800A1EA2
0x1800a1dd7  mov     ecx, 80h; Size
0x1800a1ddc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a1de1  mov     rsi, rax
0x1800a1de4  mov     [rbp+57h+var_80], rax
0x1800a1de8  xorps   xmm0, xmm0
0x1800a1deb  movups  xmmword ptr [rax], xmm0
0x1800a1dee  mov     dword ptr [rax+8], 1
0x1800a1df5  mov     dword ptr [rax+0Ch], 1
0x1800a1dfc  lea     rax, ??_7?$_Ref_count_obj2@V?$ThreadPoolWaitableResult@V?$tuple@JV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseRequest@RoutePolicyOnDemand@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@WcmCommon@@@std@@6B@
0x1800a1e03  mov     [rsi], rax
0x1800a1e06  lea     r14, [rsi+10h]
0x1800a1e0a  mov     rdx, r15
0x1800a1e0d  mov     rcx, r14
0x1800a1e10  call    WcmCommon__ThreadPoolWaitableResult_std__tuple_long_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__RoutePolicyOnDemand__CloseRequest_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t___________ThreadPoolWaitableResult_std__tuple_long_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__RoutePolicyOnDemand__CloseRequest_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t___________RoutePolicyOnDemand__OpenRequestInternal____3____lambda_1___
0x1800a1e15  nop
0x1800a1e16  mov     qword ptr [rbp+57h+var_98], r14
0x1800a1e1a  mov     qword ptr [rbp+57h+var_98+8], rsi
0x1800a1e1e  lea     rdx, [rbp+57h+var_98]
0x1800a1e22  cmp     dword ptr [rdi], 1
0x1800a1e25  jnz     short loc_1800A1E52
0x1800a1e27  lea     rcx, [rbp+57h+var_80]
0x1800a1e2b  call    ??$?0V?$ThreadPoolWaitableResult@V?$tuple@JV?$unique_ptr@U_WCM_ONDEMAND_STATE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?WcmFree@@YAX0@Z@wil@@@std@@@std@@@WcmCommon@@$0A@@?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@QEAA@AEBV?$shared_ptr@V?$ThreadPoolWaitableResult@V?$tuple@JV?$unique_ptr@U_WCM_ONDEMAND_STATE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?WcmFree@@YAX0@Z@wil@@@std@@@std@@@WcmCommon@@@1@@Z; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<std::tuple<long,std::unique_ptr<_WCM_ONDEMAND_STATE_INFO,wil::function_deleter<void (*)(void *),&WcmFree(void *)>>>>> const &)
0x1800a1e30  nop
0x1800a1e31  lea     rdx, [rbp+57h+var_80]
0x1800a1e35  lea     rcx, [rdi+0C0h]
0x1800a1e3c  call    ?push_back@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@QEAAX$$QEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@Z; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::push_back(std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult> &&)
0x1800a1e41  nop
0x1800a1e42  mov     rcx, [rbp+57h+var_78]; this
0x1800a1e46  test    rcx, rcx
0x1800a1e49  jz      short loc_1800A1E77
0x1800a1e4b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a1e50  jmp     short loc_1800A1E77
0x1800a1e52  lea     rcx, [rbp+57h+var_70]
0x1800a1e56  call    ??$?0AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@std@@$0A@$0A@@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@1@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<bool>> &)
0x1800a1e5b  nop
0x1800a1e5c  lea     rdx, [rbp+57h+var_70]
0x1800a1e60  lea     rcx, [rdi+0E8h]
0x1800a1e67  call    ??$_Emplace_back_internal@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@AEAAX$$QEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Emplace_back_internal<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &&)
0x1800a1e6c  nop
0x1800a1e6d  lea     rcx, [rbp+57h+var_70]
0x1800a1e71  call    ??1?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@XZ; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(void)
0x1800a1e76  nop
0x1800a1e77  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x1800a1e7b  test    rcx, rcx
0x1800a1e7e  jz      short loc_1800A1E86
0x1800a1e80  call    cs:__imp_LeaveCriticalSection
0x1800a1e86  lock inc qword ptr [rdi+88h]
0x1800a1e8e  mov     rcx, [rdi+80h]; pwk
0x1800a1e95  call    cs:__imp_SubmitThreadpoolWork
0x1800a1e9b  mov     [rbx], r14
0x1800a1e9e  mov     [rbx+8], rsi
0x1800a1ea2  mov     rax, rbx
0x1800a1ea5  mov     rbx, [rsp+0C0h+arg_18]
0x1800a1ead  add     rsp, 0A0h
0x1800a1eb4  pop     r15
0x1800a1eb6  pop     r14
0x1800a1eb8  pop     rdi
0x1800a1eb9  pop     rsi
0x1800a1eba  pop     rbp
0x1800a1ebb  retn
```
