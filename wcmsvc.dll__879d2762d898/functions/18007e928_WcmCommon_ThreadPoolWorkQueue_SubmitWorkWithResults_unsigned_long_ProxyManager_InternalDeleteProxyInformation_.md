# WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_unsigned_long__ProxyManager::InternalDeleteProxyInformation_::_3_::_lambda_1___

- ea: `0x18007e928`
- end: `0x18007eaa5`
- name: `WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_unsigned_long__ProxyManager::InternalDeleteProxyInformation_::_3_::_lambda_1___`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007e1bc`

## callees

- `0x180007ff8`
- `0x180008394`
- `0x180010080`
- `0x180010560`
- `0x18001d53c`
- `0x180027630`
- `0x18006de30`
- `0x18007e928`
- `0x18007eaac`
- `0x18008534c`
- `0x180098260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007e991`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ea61`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007e991`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ea61`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18007ea76`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18007ea76`

## pseudocode

```c
_QWORD *__fastcall WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_unsigned_long__ProxyManager::InternalDeleteProxyInformation_::_3_::_lambda_1___(
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
    WcmCommon::ThreadPoolWaitableResult_unsigned_long_::ThreadPoolWaitableResult_unsigned_long___ProxyManager::InternalDeleteProxyInformation_::_3_::_lambda_1___(
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
0x18007e928  mov     [rsp-8+arg_18], rbx
0x18007e92d  push    rbp
0x18007e92e  push    rsi
0x18007e92f  push    rdi
0x18007e930  push    r14
0x18007e932  push    r15
0x18007e934  lea     rbp, [rsp-37h]
0x18007e939  sub     rsp, 0A0h
0x18007e940  mov     r15, r8
0x18007e943  mov     rsi, rdx
0x18007e946  mov     r14, rcx
0x18007e949  mov     [rbp+57h+lpCriticalSection], rdx
0x18007e94d  xorps   xmm1, xmm1
0x18007e950  movdqu  [rbp+57h+var_88], xmm1
0x18007e955  mov     [rbp+57h+lpCriticalSection], 0
0x18007e95d  lea     rdx, [rcx+8]
0x18007e961  lea     rcx, [rbp+57h+lpCriticalSection]
0x18007e965  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18007e96a  nop
0x18007e96b  cmp     byte ptr [r14+110h], 0
0x18007e973  jz      short loc_18007E99C
0x18007e975  mov     qword ptr [rsi], 0
0x18007e97c  mov     qword ptr [rsi+8], 0
0x18007e984  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x18007e988  test    rcx, rcx
0x18007e98b  jz      loc_18007EA8B
0x18007e991  call    cs:__imp_LeaveCriticalSection
0x18007e997  jmp     loc_18007EA8B
0x18007e99c  mov     ecx, 78h ; 'x'; Size
0x18007e9a1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007e9a6  mov     rdi, rax
0x18007e9a9  mov     [rbp+57h+var_98], rax
0x18007e9ad  xorps   xmm0, xmm0
0x18007e9b0  movups  xmmword ptr [rax], xmm0
0x18007e9b3  mov     dword ptr [rax+8], 1
0x18007e9ba  mov     dword ptr [rax+0Ch], 1
0x18007e9c1  lea     rax, ??_7?$_Ref_count_obj2@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@std@@6B@; const std::_Ref_count_obj2<WcmCommon::ThreadPoolWaitableResult<bool>>::`vftable'
0x18007e9c8  mov     [rdi], rax
0x18007e9cb  lea     rbx, [rdi+10h]
0x18007e9cf  mov     rdx, r15
0x18007e9d2  mov     rcx, rbx
0x18007e9d5  call    WcmCommon__ThreadPoolWaitableResult_unsigned_long___ThreadPoolWaitableResult_unsigned_long___ProxyManager__InternalDeleteProxyInformation____3____lambda_1___
0x18007e9da  nop
0x18007e9db  mov     [rbp+57h+var_98], rbx
0x18007e9df  mov     [rbp+57h+var_90], rdi
0x18007e9e3  lea     rdx, [rbp+57h+var_98]
0x18007e9e7  lea     rcx, [rbp+57h+var_88]
0x18007e9eb  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>> &&)
0x18007e9f0  mov     rcx, [rbp+57h+var_90]; this
0x18007e9f4  test    rcx, rcx
0x18007e9f7  jz      short loc_18007E9FE
0x18007e9f9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007e9fe  lea     rdx, [rbp+57h+var_88]
0x18007ea02  cmp     dword ptr [r14], 1
0x18007ea06  jnz     short loc_18007EA33
0x18007ea08  lea     rcx, [rbp+57h+var_98]
0x18007ea0c  call    ??$?0V?$ThreadPoolWaitableResult@V?$tuple@JV?$unique_ptr@U_WCM_ONDEMAND_STATE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?WcmFree@@YAX0@Z@wil@@@std@@@std@@@WcmCommon@@$0A@@?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@QEAA@AEBV?$shared_ptr@V?$ThreadPoolWaitableResult@V?$tuple@JV?$unique_ptr@U_WCM_ONDEMAND_STATE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?WcmFree@@YAX0@Z@wil@@@std@@@std@@@WcmCommon@@@1@@Z; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<std::tuple<long,std::unique_ptr<_WCM_ONDEMAND_STATE_INFO,wil::function_deleter<void (*)(void *),&WcmFree(void *)>>>>> const &)
0x18007ea11  nop
0x18007ea12  lea     rdx, [rbp+57h+var_98]
0x18007ea16  lea     rcx, [r14+0C0h]
0x18007ea1d  call    ?push_back@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@QEAAX$$QEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@Z; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::push_back(std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult> &&)
0x18007ea22  nop
0x18007ea23  mov     rcx, [rbp+57h+var_90]; this
0x18007ea27  test    rcx, rcx
0x18007ea2a  jz      short loc_18007EA58
0x18007ea2c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007ea31  jmp     short loc_18007EA58
0x18007ea33  lea     rcx, [rbp+57h+var_70]
0x18007ea37  call    ??$?0AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@std@@$0A@$0A@@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@1@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<bool>> &)
0x18007ea3c  nop
0x18007ea3d  lea     rdx, [rbp+57h+var_70]
0x18007ea41  lea     rcx, [r14+0E8h]
0x18007ea48  call    ??$_Emplace_back_internal@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@AEAAX$$QEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Emplace_back_internal<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &&)
0x18007ea4d  nop
0x18007ea4e  lea     rcx, [rbp+57h+var_70]
0x18007ea52  call    ??1?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@XZ; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(void)
0x18007ea57  nop
0x18007ea58  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x18007ea5c  test    rcx, rcx
0x18007ea5f  jz      short loc_18007EA67
0x18007ea61  call    cs:__imp_LeaveCriticalSection
0x18007ea67  lock inc qword ptr [r14+88h]
0x18007ea6f  mov     rcx, [r14+80h]; pwk
0x18007ea76  call    cs:__imp_SubmitThreadpoolWork
0x18007ea7c  mov     rax, qword ptr [rbp+57h+var_88]
0x18007ea80  mov     [rsi], rax
0x18007ea83  mov     rax, qword ptr [rbp+57h+var_88+8]
0x18007ea87  mov     [rsi+8], rax
0x18007ea8b  mov     rax, rsi
0x18007ea8e  mov     rbx, [rsp+0C0h+arg_18]
0x18007ea96  add     rsp, 0A0h
0x18007ea9d  pop     r15
0x18007ea9f  pop     r14
0x18007eaa1  pop     rdi
0x18007eaa2  pop     rsi
0x18007eaa3  pop     rbp
0x18007eaa4  retn
```
