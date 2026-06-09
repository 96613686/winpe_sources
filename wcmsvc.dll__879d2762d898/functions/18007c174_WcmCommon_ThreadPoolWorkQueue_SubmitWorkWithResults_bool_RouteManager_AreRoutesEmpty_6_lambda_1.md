# WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_bool__RouteManager::AreRoutesEmpty_::_6_::_lambda_1___

- ea: `0x18007c174`
- end: `0x18007c2f1`
- name: `WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_bool__RouteManager::AreRoutesEmpty_::_6_::_lambda_1___`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800beb84`

## callees

- `0x180007ff8`
- `0x180008394`
- `0x180010080`
- `0x180010560`
- `0x18001d53c`
- `0x180027630`
- `0x18006de30`
- `0x18007c174`
- `0x18007c2f8`
- `0x18008534c`
- `0x180098260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c1dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c2ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c1dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c2ad`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18007c2c2`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18007c2c2`

## pseudocode

```c
_QWORD *__fastcall WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_bool__RouteManager::AreRoutesEmpty_::_6_::_lambda_1___(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  std::_Ref_count_base *v6; // rdi
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-49h] BYREF
  std::_Ref_count_base *v9; // [rsp+28h] [rbp-41h] BYREF
  std::_Ref_count_base *v10; // [rsp+30h] [rbp-39h]
  __int128 v11; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v12[112]; // [rsp+50h] [rbp-19h] BYREF

  v11 = 0;
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
    v6 = (std::_Ref_count_base *)operator new(0x78u);
    v9 = v6;
    *(_OWORD *)v6 = 0;
    *((_DWORD *)v6 + 2) = 1;
    *((_DWORD *)v6 + 3) = 1;
    *(_QWORD *)v6 = &std::_Ref_count_obj2<WcmCommon::ThreadPoolWaitableResult<bool>>::`vftable';
    WcmCommon::ThreadPoolWaitableResult_bool_::ThreadPoolWaitableResult_bool___RouteManager::AreRoutesEmpty_::_6_::_lambda_1___(
      (char *)v6 + 16,
      a3);
    v9 = (std::_Ref_count_base *)((char *)v6 + 16);
    v10 = v6;
    std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::operator=(
      &v11,
      &v9);
    if ( v10 )
      std::_Ref_count_base::_Decref(v10);
    if ( *(_DWORD *)a1 == 1 )
    {
      std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(
        &v9,
        &v11);
      std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::push_back(a1 + 192, &v9);
      if ( v10 )
        std::_Ref_count_base::_Decref(v10);
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
    *(_OWORD *)a2 = v11;
  }
  return a2;
}

```

## disassembly

```asm
0x18007c174  mov     [rsp-8+arg_10], rbx
0x18007c179  push    rbp
0x18007c17a  push    rsi
0x18007c17b  push    rdi
0x18007c17c  push    r14
0x18007c17e  push    r15
0x18007c180  lea     rbp, [rsp-37h]
0x18007c185  sub     rsp, 0A0h
0x18007c18c  mov     r15, r8
0x18007c18f  mov     rsi, rdx
0x18007c192  mov     r14, rcx
0x18007c195  mov     [rbp+57h+lpCriticalSection], rdx
0x18007c199  xorps   xmm1, xmm1
0x18007c19c  movdqu  [rbp+57h+var_88], xmm1
0x18007c1a1  mov     [rbp+57h+lpCriticalSection], 0
0x18007c1a9  lea     rdx, [rcx+8]
0x18007c1ad  lea     rcx, [rbp+57h+lpCriticalSection]
0x18007c1b1  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18007c1b6  nop
0x18007c1b7  cmp     byte ptr [r14+110h], 0
0x18007c1bf  jz      short loc_18007C1E8
0x18007c1c1  mov     qword ptr [rsi], 0
0x18007c1c8  mov     qword ptr [rsi+8], 0
0x18007c1d0  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x18007c1d4  test    rcx, rcx
0x18007c1d7  jz      loc_18007C2D7
0x18007c1dd  call    cs:__imp_LeaveCriticalSection
0x18007c1e3  jmp     loc_18007C2D7
0x18007c1e8  mov     ecx, 78h ; 'x'; Size
0x18007c1ed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007c1f2  mov     rdi, rax
0x18007c1f5  mov     [rbp+57h+var_98], rax
0x18007c1f9  xorps   xmm0, xmm0
0x18007c1fc  movups  xmmword ptr [rax], xmm0
0x18007c1ff  mov     dword ptr [rax+8], 1
0x18007c206  mov     dword ptr [rax+0Ch], 1
0x18007c20d  lea     rax, ??_7?$_Ref_count_obj2@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@std@@6B@; const std::_Ref_count_obj2<WcmCommon::ThreadPoolWaitableResult<bool>>::`vftable'
0x18007c214  mov     [rdi], rax
0x18007c217  lea     rbx, [rdi+10h]
0x18007c21b  mov     rdx, r15
0x18007c21e  mov     rcx, rbx
0x18007c221  call    WcmCommon__ThreadPoolWaitableResult_bool___ThreadPoolWaitableResult_bool___RouteManager__AreRoutesEmpty____6____lambda_1___
0x18007c226  nop
0x18007c227  mov     [rbp+57h+var_98], rbx
0x18007c22b  mov     [rbp+57h+var_90], rdi
0x18007c22f  lea     rdx, [rbp+57h+var_98]
0x18007c233  lea     rcx, [rbp+57h+var_88]
0x18007c237  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>> &&)
0x18007c23c  mov     rcx, [rbp+57h+var_90]; this
0x18007c240  test    rcx, rcx
0x18007c243  jz      short loc_18007C24A
0x18007c245  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007c24a  lea     rdx, [rbp+57h+var_88]
0x18007c24e  cmp     dword ptr [r14], 1
0x18007c252  jnz     short loc_18007C27F
0x18007c254  lea     rcx, [rbp+57h+var_98]
0x18007c258  call    ??$?0V?$ThreadPoolWaitableResult@V?$tuple@JV?$unique_ptr@U_WCM_ONDEMAND_STATE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?WcmFree@@YAX0@Z@wil@@@std@@@std@@@WcmCommon@@$0A@@?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@QEAA@AEBV?$shared_ptr@V?$ThreadPoolWaitableResult@V?$tuple@JV?$unique_ptr@U_WCM_ONDEMAND_STATE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?WcmFree@@YAX0@Z@wil@@@std@@@std@@@WcmCommon@@@1@@Z; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<std::tuple<long,std::unique_ptr<_WCM_ONDEMAND_STATE_INFO,wil::function_deleter<void (*)(void *),&WcmFree(void *)>>>>> const &)
0x18007c25d  nop
0x18007c25e  lea     rdx, [rbp+57h+var_98]
0x18007c262  lea     rcx, [r14+0C0h]
0x18007c269  call    ?push_back@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@QEAAX$$QEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@Z; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::push_back(std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult> &&)
0x18007c26e  nop
0x18007c26f  mov     rcx, [rbp+57h+var_90]; this
0x18007c273  test    rcx, rcx
0x18007c276  jz      short loc_18007C2A4
0x18007c278  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007c27d  jmp     short loc_18007C2A4
0x18007c27f  lea     rcx, [rbp+57h+var_70]
0x18007c283  call    ??$?0AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@std@@$0A@$0A@@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@1@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<bool>> &)
0x18007c288  nop
0x18007c289  lea     rdx, [rbp+57h+var_70]
0x18007c28d  lea     rcx, [r14+0E8h]
0x18007c294  call    ??$_Emplace_back_internal@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@AEAAX$$QEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Emplace_back_internal<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &&)
0x18007c299  nop
0x18007c29a  lea     rcx, [rbp+57h+var_70]
0x18007c29e  call    ??1?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@XZ; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(void)
0x18007c2a3  nop
0x18007c2a4  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x18007c2a8  test    rcx, rcx
0x18007c2ab  jz      short loc_18007C2B3
0x18007c2ad  call    cs:__imp_LeaveCriticalSection
0x18007c2b3  lock inc qword ptr [r14+88h]
0x18007c2bb  mov     rcx, [r14+80h]; pwk
0x18007c2c2  call    cs:__imp_SubmitThreadpoolWork
0x18007c2c8  mov     rax, qword ptr [rbp+57h+var_88]
0x18007c2cc  mov     [rsi], rax
0x18007c2cf  mov     rax, qword ptr [rbp+57h+var_88+8]
0x18007c2d3  mov     [rsi+8], rax
0x18007c2d7  mov     rax, rsi
0x18007c2da  mov     rbx, [rsp+0C0h+arg_10]
0x18007c2e2  add     rsp, 0A0h
0x18007c2e9  pop     r15
0x18007c2eb  pop     r14
0x18007c2ed  pop     rdi
0x18007c2ee  pop     rsi
0x18007c2ef  pop     rbp
0x18007c2f0  retn
```
