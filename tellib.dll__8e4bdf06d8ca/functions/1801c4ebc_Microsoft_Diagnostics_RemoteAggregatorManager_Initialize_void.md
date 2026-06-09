# Microsoft::Diagnostics::RemoteAggregatorManager::Initialize(void)

- ea: `0x1801c4ebc`
- end: `0x1801c5102`
- name: `?Initialize@RemoteAggregatorManager@Diagnostics@Microsoft@@QEAAXXZ`
- size: `582`
- prototype: `void __fastcall(Microsoft::Diagnostics::RemoteAggregatorManager *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801817c4`

## callees

- `0x18001d160`
- `0x180026ef4`
- `0x180027be0`
- `0x18009d380`
- `0x1800a1e24`
- `0x1800b84fc`
- `0x1800eded4`
- `0x180105ae4`
- `0x18012de40`
- `0x1801760ac`
- `0x1801c4b9c`
- `0x1801c4ebc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1801c50f5`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1801c50f5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1801c507b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1801c507b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1801c4fea`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1801c502f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1801c4fea`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1801c502f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801c4f02`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801c4f2c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801c4f02`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801c4f2c`

## string_xrefs

- `0x1801c5003`: `onecore\base\telemetry\utc\service\engine\remoteaggregatormanager.cpp`
- `0x1801c5048`: `onecore\base\telemetry\utc\service\engine\remoteaggregatormanager.cpp`
- `0x1801c50a0`: `onecore\base\telemetry\utc\service\engine\remoteaggregatormanager.cpp`
- `0x1801c4f25`: `MissionControlAggregator.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::Diagnostics::RemoteAggregatorManager::Initialize(
        Microsoft::Diagnostics::RemoteAggregatorManager *this)
{
  WCHAR *i; // rbx
  char *v3; // rcx
  bool v4; // si
  PTP_TIMER ThreadpoolTimer; // rax
  const char *v6; // r9
  PTP_TIMER v7; // rax
  const char *v8; // r9
  PTP_WAIT ThreadpoolWait; // rax
  const char *v10; // r9
  __int128 v11; // [rsp+30h] [rbp-58h] BYREF
  __int128 v12; // [rsp+40h] [rbp-48h] BYREF
  _BYTE v13[16]; // [rsp+50h] [rbp-38h] BYREF
  __int64 v14; // [rsp+60h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  for ( i = &Microsoft::Diagnostics::k_inboxAggregatorModulePaths;
        i != (WCHAR *)&`Microsoft::Diagnostics::better_enums::_data_ConfigurationType::_name_array'::`2'::value;
        i += 16 )
  {
    if ( *((_QWORD *)i + 3) <= 7u )
      v3 = (char *)i;
    else
      v3 = *(char **)i;
    if ( GetFileAttributesW((LPCWSTR)v3) != -1 )
    {
      v4 = 1;
      goto LABEL_10;
    }
  }
  v4 = GetFileAttributesW(L"MissionControlAggregator.dll") != -1;
LABEL_10:
  std::wstring::wstring(v13);
  v11 = *(_OWORD *)&off_18035FE58;
  v12 = *(_OWORD *)&off_18035FE98;
  Microsoft::Diagnostics::Utils::Registry::GetString(-2147483646, &v12, &v11, v13);
  if ( !v4 && !v14 )
    *((_BYTE *)this + 1912) = 1;
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v13);
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (_DWORD)this + 1144,
    1,
    0,
    0,
    0);
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (_DWORD)this + 1152,
    1,
    0,
    0,
    0);
  ThreadpoolTimer = CreateThreadpoolTimer(
                      Microsoft::Diagnostics::Utils::Os::MethodToTpTimerCallbackAdapter<Microsoft::Diagnostics::RemoteAggregatorManager,{public: void Microsoft::Diagnostics::RemoteAggregatorManager::FlushAsync(void),0}>,
                      this,
                      0);
  if ( !ThreadpoolTimer )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x4E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\remoteaggregatormanager.cpp",
      v6);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    (char *)this + 1688,
    ThreadpoolTimer);
  v7 = CreateThreadpoolTimer(
         Microsoft::Diagnostics::Utils::Os::MethodToTpTimerCallbackAdapter<Microsoft::Diagnostics::RemoteAggregatorManager,{public: void Microsoft::Diagnostics::RemoteAggregatorManager::GetChildProcessToReadyStateAsync(void),0}>,
         this,
         0);
  if ( !v7 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\remoteaggregatormanager.cpp",
      v8);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    (char *)this + 1592,
    v7);
  ThreadpoolWait = CreateThreadpoolWait(
                     Microsoft::Diagnostics::RemoteAggregatorManager::Initialize_::_2_::_lambda_1_::_lambda_invoker_cdecl_,
                     this,
                     0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    (char *)this + 1248,
    ThreadpoolWait);
  if ( !*((_QWORD *)this + 156) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x5B,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\remoteaggregatormanager.cpp",
      v10);
  Microsoft::Diagnostics::RemoteAggregatorManager::DeserializeControlGroupsFromRegistry(this);
  if ( (int)Microsoft::Diagnostics::UtcWrapperBase::Initialize((Microsoft::Diagnostics::RemoteAggregatorManager *)((char *)this + 1496)) < 0 )
  {
    _o_terminate();
    __debugbreak();
    JUMPOUT(0x1801C5102LL);
  }
  Microsoft::Diagnostics::RemoteAggregatorManager::ArmStartTimer(this);
}

```

## disassembly

```asm
0x1801c4ebc  mov     [rsp+arg_8], rbx
0x1801c4ec1  mov     [rsp+arg_10], rsi
0x1801c4ec6  push    rdi
0x1801c4ec7  sub     rsp, 80h
0x1801c4ece  mov     rax, cs:__security_cookie
0x1801c4ed5  xor     rax, rsp
0x1801c4ed8  mov     [rsp+88h+var_18], rax
0x1801c4edd  mov     rdi, rcx
0x1801c4ee0  lea     rbx, ?k_inboxAggregatorModulePaths@Diagnostics@Microsoft@@3PAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@A; std::wstring near * Microsoft::Diagnostics::k_inboxAggregatorModulePaths
0x1801c4ee7  lea     rax, ?value@?1??_name_array@_data_ConfigurationType@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA; char const * near * `Microsoft::Diagnostics::better_enums::_data_ConfigurationType::_name_array(void)'::`2'::value
0x1801c4eee  cmp     rbx, rax
0x1801c4ef1  jz      short loc_1801C4F23
0x1801c4ef3  cmp     qword ptr [rbx+18h], 7
0x1801c4ef8  jbe     short loc_1801C4EFF
0x1801c4efa  mov     rcx, [rbx]
0x1801c4efd  jmp     short loc_1801C4F02
0x1801c4eff  mov     rcx, rbx; lpFileName
0x1801c4f02  call    cs:__imp_GetFileAttributesW
0x1801c4f09  nop     dword ptr [rax+rax+00h]
0x1801c4f0e  cmp     eax, 0FFFFFFFFh
0x1801c4f11  jnz     short loc_1801C4F19
0x1801c4f13  add     rbx, 20h ; ' '
0x1801c4f17  jmp     short loc_1801C4EE7
0x1801c4f19  mov     ebx, 1
0x1801c4f1e  mov     sil, bl
0x1801c4f21  jmp     short loc_1801C4F46
0x1801c4f23  xor     bl, bl
0x1801c4f25  lea     rcx, FileName; "MissionControlAggregator.dll"
0x1801c4f2c  call    cs:__imp_GetFileAttributesW
0x1801c4f33  nop     dword ptr [rax+rax+00h]
0x1801c4f38  movzx   esi, bl
0x1801c4f3b  mov     ebx, 1
0x1801c4f40  cmp     eax, 0FFFFFFFFh
0x1801c4f43  cmovnz  esi, ebx
0x1801c4f46  lea     rcx, [rsp+88h+var_38]; void *
0x1801c4f4b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801c4f50  nop
0x1801c4f51  movups  xmm0, xmmword ptr cs:off_18035FE58; "TestAggregatorDll"
0x1801c4f58  movdqu  [rsp+88h+var_58], xmm0
0x1801c4f5e  movups  xmm1, xmmword ptr cs:off_18035FE98; "%DiagtrackRegistryRoot%\\TestHooks"
0x1801c4f65  movdqu  [rsp+88h+var_48], xmm1
0x1801c4f6b  lea     r9, [rsp+88h+var_38]
0x1801c4f70  lea     r8, [rsp+88h+var_58]
0x1801c4f75  lea     rdx, [rsp+88h+var_48]
0x1801c4f7a  mov     rcx, 0FFFFFFFF80000002h
0x1801c4f81  call    ?GetString@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@7@@Z; Microsoft::Diagnostics::Utils::Registry::GetString(HKEY__ *,std::wstring_view,std::wstring_view,std::wstring &)
0x1801c4f86  test    sil, sil
0x1801c4f89  jnz     short loc_1801C4F99
0x1801c4f8b  cmp     [rsp+88h+var_28], 0
0x1801c4f91  jnz     short loc_1801C4F99
0x1801c4f93  mov     [rdi+778h], bl
0x1801c4f99  lea     rcx, [rsp+88h+var_38]; this
0x1801c4f9e  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801c4fa3  lea     rcx, [rdi+478h]
0x1801c4faa  mov     [rsp+88h+var_68], 0
0x1801c4fb3  xor     r9d, r9d
0x1801c4fb6  xor     r8d, r8d
0x1801c4fb9  mov     edx, ebx
0x1801c4fbb  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1801c4fc0  lea     rcx, [rdi+480h]
0x1801c4fc7  mov     [rsp+88h+var_68], 0
0x1801c4fd0  xor     r9d, r9d
0x1801c4fd3  xor     r8d, r8d
0x1801c4fd6  mov     edx, ebx
0x1801c4fd8  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1801c4fdd  xor     r8d, r8d; pcbe
0x1801c4fe0  mov     rdx, rdi; pv
0x1801c4fe3  lea     rcx, ??$MethodToTpTimerCallbackAdapter@VRemoteAggregatorManager@Diagnostics@Microsoft@@$H?FlushAsync@123@QEAAXXZA@@Os@Utils@Diagnostics@Microsoft@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1801c4fea  call    cs:__imp_CreateThreadpoolTimer
0x1801c4ff1  nop     dword ptr [rax+rax+00h]
0x1801c4ff6  test    rax, rax
0x1801c4ff9  jnz     short loc_1801C5013
0x1801c4ffb  mov     rcx, [rsp+88h]; this
0x1801c5003  lea     r8, aOnecoreBaseTel_275; "onecore\\base\\telemetry\\utc\\service"...
0x1801c500a  lea     edx, [rax+4Eh]; void *
0x1801c500d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801c5013  lea     rcx, [rdi+698h]
0x1801c501a  mov     rdx, rax
0x1801c501d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1801c5022  xor     r8d, r8d; pcbe
0x1801c5025  mov     rdx, rdi; pv
0x1801c5028  lea     rcx, ??$MethodToTpTimerCallbackAdapter@VRemoteAggregatorManager@Diagnostics@Microsoft@@$H?GetChildProcessToReadyStateAsync@123@QEAAXXZA@@Os@Utils@Diagnostics@Microsoft@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1801c502f  call    cs:__imp_CreateThreadpoolTimer
0x1801c5036  nop     dword ptr [rax+rax+00h]
0x1801c503b  test    rax, rax
0x1801c503e  jnz     short loc_1801C5058
0x1801c5040  mov     rcx, [rsp+88h]; this
0x1801c5048  lea     r8, aOnecoreBaseTel_275; "onecore\\base\\telemetry\\utc\\service"...
0x1801c504f  lea     edx, [rax+53h]; void *
0x1801c5052  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801c5058  lea     rcx, [rdi+638h]
0x1801c505f  mov     rdx, rax
0x1801c5062  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1801c5067  lea     rbx, [rdi+4E0h]
0x1801c506e  xor     r8d, r8d; pcbe
0x1801c5071  mov     rdx, rdi; pv
0x1801c5074  lea     rcx, _Microsoft__Diagnostics__RemoteAggregatorManager__Initialize____2____lambda_1____lambda_invoker_cdecl_; pfnwa
0x1801c507b  call    cs:__imp_CreateThreadpoolWait
0x1801c5082  nop     dword ptr [rax+rax+00h]
0x1801c5087  mov     rdx, rax
0x1801c508a  mov     rcx, rbx
0x1801c508d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x1801c5092  cmp     qword ptr [rbx], 0
0x1801c5096  jnz     short loc_1801C50B2
0x1801c5098  mov     rcx, [rsp+88h]; this
0x1801c50a0  lea     r8, aOnecoreBaseTel_275; "onecore\\base\\telemetry\\utc\\service"...
0x1801c50a7  mov     edx, 5Bh ; '['; void *
0x1801c50ac  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801c50b2  mov     rcx, rdi; this
0x1801c50b5  call    ?DeserializeControlGroupsFromRegistry@RemoteAggregatorManager@Diagnostics@Microsoft@@AEAAXXZ; Microsoft::Diagnostics::RemoteAggregatorManager::DeserializeControlGroupsFromRegistry(void)
0x1801c50ba  lea     rcx, [rdi+5D8h]; this
0x1801c50c1  call    ?Initialize@UtcWrapperBase@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::UtcWrapperBase::Initialize(void)
0x1801c50c6  test    eax, eax
0x1801c50c8  js      short loc_1801C50F5
0x1801c50ca  mov     rcx, rdi; this
0x1801c50cd  call    ?ArmStartTimer@RemoteAggregatorManager@Diagnostics@Microsoft@@AEAAXXZ; Microsoft::Diagnostics::RemoteAggregatorManager::ArmStartTimer(void)
0x1801c50d2  mov     rcx, [rsp+88h+var_18]
0x1801c50d7  xor     rcx, rsp; StackCookie
0x1801c50da  call    __security_check_cookie
0x1801c50df  lea     r11, [rsp+88h+var_8]
0x1801c50e7  mov     rbx, [r11+18h]
0x1801c50eb  mov     rsi, [r11+20h]
0x1801c50ef  mov     rsp, r11
0x1801c50f2  pop     rdi
0x1801c50f3  retn
0x1801c50f5  call    cs:__imp__o_terminate
0x1801c50fc  nop     dword ptr [rax+rax+00h]
0x1801c5101  int     3; Trap to Debugger
```
