# FirewallManager::InternalUpdateTrafficDescriptorFilters(WcmRoutePolicy::RoutingRulesForInterface const *)

- ea: `0x1800745ec`
- end: `0x18007484d`
- name: `?InternalUpdateTrafficDescriptorFilters@FirewallManager@@AEAAXPEBURoutingRulesForInterface@WcmRoutePolicy@@@Z`
- size: `609`
- prototype: `void __fastcall(FirewallManager *__hidden this, const struct WcmRoutePolicy::RoutingRulesForInterface *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002ec10`

## callees

- `0x180007ff8`
- `0x180008394`
- `0x18000dd88`
- `0x180010080`
- `0x180012410`
- `0x180019434`
- `0x180027630`
- `0x18002af10`
- `0x1800745ec`
- `0x180074854`
- `0x180074880`
- `0x180084f50`
- `0x18008534c`
- `0x1800c5724`
- `0x1800c5b14`
- `0x1800c5bb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800747aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800747e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800747aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800747e2`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800747f7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800747f7`

## string_xrefs

- `0x180074684`: `FirewallManager::UpdateTrafficDescriptorFilters`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
void __fastcall FirewallManager::InternalUpdateTrafficDescriptorFilters(
        FirewallManager *this,
        const struct WcmRoutePolicy::RoutingRulesForInterface *a2)
{
  const struct WcmRoutePolicy::RoutingRulesForInterface *v2; // r14
  FirewallManager *v3; // rdi
  _DWORD *v4; // rsi
  const char *v5; // r9
  char *v6; // rbx
  unsigned int i; // esi
  const char *v8; // r9
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-A8h] BYREF
  _DWORD *v10; // [rsp+28h] [rbp-A0h] BYREF
  std::_Ref_count_base *v11; // [rsp+30h] [rbp-98h]
  const struct WcmRoutePolicy::RoutingRulesForInterface *v12; // [rsp+38h] [rbp-90h]
  FirewallManager *v13; // [rsp+40h] [rbp-88h]
  std::_Ref_count_base *v14[2]; // [rsp+48h] [rbp-80h] BYREF
  _QWORD v15[2]; // [rsp+58h] [rbp-70h] BYREF
  _BYTE v16[24]; // [rsp+68h] [rbp-60h] BYREF
  __int64 v17; // [rsp+80h] [rbp-48h] BYREF
  __int128 v18; // [rsp+90h] [rbp-38h] BYREF
  __int64 v19; // [rsp+A0h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v2 = a2;
  v3 = this;
  v13 = this;
  v12 = a2;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 23, &WPP_d8a94f88c0853b4dcaf5d33ae778eeca_Traceguids);
  }
  try
  {
    try
    {
      *(_OWORD *)v14 = 0;
      v4 = operator new(0x20u);
      v4[2] = 1;
      v4[3] = 1;
      *(_QWORD *)v4 = &std::_Ref_count_obj2<WcmTimerTracking>::`vftable';
      WcmTimerTracking::WcmTimerTracking(
        (WcmTimerTracking *)(v4 + 4),
        "FirewallManager::UpdateTrafficDescriptorFilters");
      v10 = v4 + 4;
      v11 = (std::_Ref_count_base *)v4;
      std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::operator=(
        v14,
        &v10);
      if ( v11 )
        std::_Ref_count_base::_Decref(v11);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x1F2,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\firewallmanager\\firewallmanager.cpp",
        v5);
      v2 = v12;
      v3 = v13;
    }
    v18 = 0;
    v19 = 0;
    std::vector<FirewallManager::TrafficDescriptor>::vector<FirewallManager::TrafficDescriptor>(&v18);
    v6 = (char *)v2 + 12;
    for ( i = 0; ; ++i )
    {
      LODWORD(lpCriticalSection) = i;
      v10 = v6;
      if ( i >= *((_DWORD *)v2 + 2) )
        break;
      if ( (*(_DWORD *)v6 & 0x800) != 0 && (*(_DWORD *)v6 & 0xFFFEE7FF) == 0 )
        std::vector<FirewallManager::TrafficDescriptor>::emplace_back<_NET_LUID_LH const &,WWAN_TRAFFIC_DESCRIPTOR const &>(
          &v18,
          (const union _NET_LUID_LH *)v2,
          (const struct WWAN_TRAFFIC_DESCRIPTOR *)v6);
      v6 += *((unsigned int *)v6 + 117) + 472;
    }
    v15[0] = v3;
    v15[1] = *(_QWORD *)v2;
    std::vector<SleepStudy::Singleton::ApplicationNetworkActivity>::vector<SleepStudy::Singleton::ApplicationNetworkActivity>(
      v16,
      &v18);
    std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(
      &v17,
      v14);
    lpCriticalSection = 0;
    wil::EnterCriticalSection(&lpCriticalSection, (char *)v3 + 56);
    if ( *((_BYTE *)v3 + 320) )
    {
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
    }
    else
    {
      if ( *((_DWORD *)v3 + 12) == 1 )
        std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__FirewallManager::InternalUpdateTrafficDescriptorFilters_::_3_::_lambda_1___(
          (char *)v3 + 200,
          v15);
      else
        std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__FirewallManager::InternalUpdateTrafficDescriptorFilters_::_3_::_lambda_1___(
          (char *)v3 + 280,
          v15);
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      _InterlockedIncrement64((volatile signed __int64 *)v3 + 23);
      SubmitThreadpoolWork(*((PTP_WORK *)v3 + 22));
    }
    FirewallManager::InternalUpdateTrafficDescriptorFilters_::_3_::_lambda_1_::__lambda_1_(v15);
    std::vector<FirewallManager::TrafficDescriptor>::_Tidy(&v18);
    if ( v14[1] )
      std::_Ref_count_base::_Decref(v14[1]);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x237,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\firewallmanager\\firewallmanager.cpp",
      v8);
  }
}

```

## disassembly

```asm
0x1800745ec  mov     [rsp+arg_10], rbx
0x1800745f1  push    rsi
0x1800745f2  push    rdi
0x1800745f3  push    r14
0x1800745f5  sub     rsp, 0B0h
0x1800745fc  mov     rax, cs:__security_cookie
0x180074603  xor     rax, rsp
0x180074606  mov     [rsp+0C8h+var_20], rax
0x18007460e  mov     r14, rdx
0x180074611  mov     rdi, rcx
0x180074614  mov     [rsp+0C8h+var_88], rcx
0x180074619  mov     [rsp+0C8h+var_90], rdx
0x18007461e  lea     rax, WPP_GLOBAL_Control
0x180074625  mov     rcx, cs:WPP_GLOBAL_Control
0x18007462c  cmp     rcx, rax
0x18007462f  jz      short loc_180074652
0x180074631  cmp     byte ptr [rcx+19h], 4
0x180074635  jb      short loc_180074652
0x180074637  test    byte ptr [rcx+1Ch], 1
0x18007463b  jz      short loc_180074652
0x18007463d  mov     edx, 17h
0x180074642  lea     r8, WPP_d8a94f88c0853b4dcaf5d33ae778eeca_Traceguids
0x180074649  mov     rcx, [rcx+10h]
0x18007464d  call    WPP_SF_
0x180074652  xorps   xmm1, xmm1
0x180074655  movdqu  xmmword ptr [rsp+0C8h+var_80], xmm1
0x18007465b  mov     ecx, 20h ; ' '; Size
0x180074660  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180074665  mov     rsi, rax
0x180074668  mov     dword ptr [rax+8], 1
0x18007466f  mov     dword ptr [rax+0Ch], 1
0x180074676  lea     rax, ??_7?$_Ref_count_obj2@VWcmTimerTracking@@@std@@6B@; const std::_Ref_count_obj2<WcmTimerTracking>::`vftable'
0x18007467d  mov     [rsi], rax
0x180074680  lea     rbx, [rsi+10h]
0x180074684  lea     rdx, aFirewallmanage_5; "FirewallManager::UpdateTrafficDescripto"...
0x18007468b  mov     rcx, rbx; this
0x18007468e  call    ??0WcmTimerTracking@@QEAA@PEBD@Z; WcmTimerTracking::WcmTimerTracking(char const *)
0x180074693  mov     [rsp+0C8h+var_A0], rbx
0x180074698  mov     [rsp+0C8h+var_98], rsi
0x18007469d  lea     rdx, [rsp+0C8h+var_A0]
0x1800746a2  lea     rcx, [rsp+0C8h+var_80]
0x1800746a7  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>> &&)
0x1800746ac  mov     rcx, [rsp+0C8h+var_98]; this
0x1800746b1  test    rcx, rcx
0x1800746b4  jz      short loc_1800746BC
0x1800746b6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800746bb  nop
0x1800746bc  jmp     short loc_1800746C8
0x1800746be  mov     r14, [rsp+0C8h+var_90]
0x1800746c3  mov     rdi, [rsp+0C8h+var_88]
0x1800746c8  xorps   xmm0, xmm0
0x1800746cb  xor     eax, eax
0x1800746cd  movups  [rsp+0C8h+var_38], xmm0
0x1800746d5  mov     [rsp+0C8h+var_28], rax
0x1800746dd  lea     rcx, [rsp+0C8h+var_38]
0x1800746e5  call    ??0?$vector@UTrafficDescriptor@FirewallManager@@V?$allocator@UTrafficDescriptor@FirewallManager@@@std@@@std@@QEAA@XZ; std::vector<FirewallManager::TrafficDescriptor>::vector<FirewallManager::TrafficDescriptor>(void)
0x1800746ea  nop
0x1800746eb  lea     rbx, [r14+0Ch]
0x1800746ef  xor     esi, esi
0x1800746f1  mov     dword ptr [rsp+0C8h+lpCriticalSection], esi
0x1800746f5  mov     [rsp+0C8h+var_A0], rbx
0x1800746fa  cmp     esi, [r14+8]
0x1800746fe  jnb     short loc_18007474D
0x180074700  test    dword ptr [rbx], 800h
0x180074706  jz      short loc_180074724
0x180074708  test    dword ptr [rbx], 0FFFEE7FFh
0x18007470e  jnz     short loc_180074724
0x180074710  mov     r8, rbx
0x180074713  mov     rdx, r14
0x180074716  lea     rcx, [rsp+0C8h+var_38]
0x18007471e  call    ??$emplace_back@AEBT_NET_LUID_LH@@AEBUWWAN_TRAFFIC_DESCRIPTOR@@@?$vector@UTrafficDescriptor@FirewallManager@@V?$allocator@UTrafficDescriptor@FirewallManager@@@std@@@std@@QEAAAEAUTrafficDescriptor@FirewallManager@@AEBT_NET_LUID_LH@@AEBUWWAN_TRAFFIC_DESCRIPTOR@@@Z; std::vector<FirewallManager::TrafficDescriptor>::emplace_back<_NET_LUID_LH const &,WWAN_TRAFFIC_DESCRIPTOR const &>(_NET_LUID_LH const &,WWAN_TRAFFIC_DESCRIPTOR const &)
0x180074723  nop
0x180074724  jmp     short loc_180074739
0x180074726  mov     rbx, [rsp+0C8h+var_A0]
0x18007472b  mov     esi, dword ptr [rsp+0C8h+lpCriticalSection]
0x18007472f  mov     r14, [rsp+0C8h+var_90]
0x180074734  mov     rdi, [rsp+0C8h+var_88]
0x180074739  mov     eax, [rbx+1D4h]
0x18007473f  add     rbx, 1D8h
0x180074746  add     rbx, rax
0x180074749  inc     esi
0x18007474b  jmp     short loc_1800746F1
0x18007474d  mov     [rsp+0C8h+var_70], rdi
0x180074752  mov     rax, [r14]
0x180074755  mov     [rsp+0C8h+var_68], rax
0x18007475a  lea     rdx, [rsp+0C8h+var_38]
0x180074762  lea     rcx, [rsp+0C8h+var_60]
0x180074767  call    ??0?$vector@UApplicationNetworkActivity@Singleton@SleepStudy@@V?$allocator@UApplicationNetworkActivity@Singleton@SleepStudy@@@std@@@std@@QEAA@$$QEAV01@@Z; std::vector<SleepStudy::Singleton::ApplicationNetworkActivity>::vector<SleepStudy::Singleton::ApplicationNetworkActivity>(std::vector<SleepStudy::Singleton::ApplicationNetworkActivity> &&)
0x18007476c  lea     rdx, [rsp+0C8h+var_80]
0x180074771  lea     rcx, [rsp+0C8h+var_48]
0x180074779  call    ??$?0V?$ThreadPoolWaitableResult@V?$tuple@JV?$unique_ptr@U_WCM_ONDEMAND_STATE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?WcmFree@@YAX0@Z@wil@@@std@@@std@@@WcmCommon@@$0A@@?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@QEAA@AEBV?$shared_ptr@V?$ThreadPoolWaitableResult@V?$tuple@JV?$unique_ptr@U_WCM_ONDEMAND_STATE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?WcmFree@@YAX0@Z@wil@@@std@@@std@@@WcmCommon@@@1@@Z; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<std::tuple<long,std::unique_ptr<_WCM_ONDEMAND_STATE_INFO,wil::function_deleter<void (*)(void *),&WcmFree(void *)>>>>> const &)
0x18007477e  nop
0x18007477f  mov     [rsp+0C8h+lpCriticalSection], 0
0x180074788  lea     rdx, [rdi+38h]
0x18007478c  lea     rcx, [rsp+0C8h+lpCriticalSection]
0x180074791  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180074796  nop
0x180074797  cmp     byte ptr [rdi+140h], 0
0x18007479e  jz      short loc_1800747B2
0x1800747a0  mov     rcx, [rsp+0C8h+lpCriticalSection]; lpCriticalSection
0x1800747a5  test    rcx, rcx
0x1800747a8  jz      short loc_1800747FE
0x1800747aa  call    cs:__imp_LeaveCriticalSection
0x1800747b0  jmp     short loc_1800747FE
0x1800747b2  lea     rdx, [rsp+0C8h+var_70]
0x1800747b7  cmp     dword ptr [rdi+30h], 1
0x1800747bb  jnz     short loc_1800747CB
0x1800747bd  lea     rcx, [rdi+0C8h]
0x1800747c4  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__FirewallManager__InternalUpdateTrafficDescriptorFilters____3____lambda_1___
0x1800747c9  jmp     short loc_1800747D8
0x1800747cb  lea     rcx, [rdi+118h]
0x1800747d2  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__FirewallManager__InternalUpdateTrafficDescriptorFilters____3____lambda_1___
0x1800747d7  nop
0x1800747d8  mov     rcx, [rsp+0C8h+lpCriticalSection]; lpCriticalSection
0x1800747dd  test    rcx, rcx
0x1800747e0  jz      short loc_1800747E8
0x1800747e2  call    cs:__imp_LeaveCriticalSection
0x1800747e8  lock inc qword ptr [rdi+0B8h]
0x1800747f0  mov     rcx, [rdi+0B0h]; pwk
0x1800747f7  call    cs:__imp_SubmitThreadpoolWork
0x1800747fd  nop
0x1800747fe  lea     rcx, [rsp+0C8h+var_70]
0x180074803  call    _FirewallManager__InternalUpdateTrafficDescriptorFilters____3____lambda_1_____lambda_1_
0x180074808  nop
0x180074809  lea     rcx, [rsp+0C8h+var_38]
0x180074811  call    ?_Tidy@?$vector@UTrafficDescriptor@FirewallManager@@V?$allocator@UTrafficDescriptor@FirewallManager@@@std@@@std@@AEAAXXZ; std::vector<FirewallManager::TrafficDescriptor>::_Tidy(void)
0x180074816  nop
0x180074817  mov     rcx, [rsp+0C8h+var_80+8]; this
0x18007481c  test    rcx, rcx
0x18007481f  jz      short loc_180074827
0x180074821  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180074826  nop
0x180074827  jmp     short $+2
0x180074829  mov     rcx, [rsp+0C8h+var_20]
0x180074831  xor     rcx, rsp; StackCookie
0x180074834  call    __security_check_cookie
0x180074839  mov     rbx, [rsp+0C8h+arg_10]
0x180074841  add     rsp, 0B0h
0x180074848  pop     r14
0x18007484a  pop     rdi
0x18007484b  pop     rsi
0x18007484c  retn
```
