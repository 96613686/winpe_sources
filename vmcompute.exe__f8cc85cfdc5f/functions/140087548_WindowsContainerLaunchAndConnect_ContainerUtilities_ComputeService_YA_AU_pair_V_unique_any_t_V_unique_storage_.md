# ?WindowsContainerLaunchAndConnect@ContainerUtilities@ComputeService@@YA?AU?$pair@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_WC_CONTAINER_NOTIFICATION@@P6AJPEAU1@@_E$1?WcReleaseContainerTerminationNotification@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@@std@@PEAXAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@4@AEBVCancellationToken@Management@2@_NP6AX0W4_WC_CONTAINER_TERMINATION_REASON@@PEAU_WC_CONTAINER_NOTIFICATION@@0@Z0@Z

- ea: `0x140087548`
- end: `0x14008774b`
- name: `?WindowsContainerLaunchAndConnect@ContainerUtilities@ComputeService@@YA?AU?$pair@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_WC_CONTAINER_NOTIFICATION@@P6AJPEAU1@@_E$1?WcReleaseContainerTerminationNotification@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@@std@@PEAXAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@4@AEBVCancellationToken@Management@2@_NP6AX0W4_WC_CONTAINER_TERMINATION_REASON@@PEAU_WC_CONTAINER_NOTIFICATION@@0@Z0@Z`
- size: `515`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140119ef8`

## callees

- `0x140017040`
- `0x1400454a4`
- `0x140046df8`
- `0x140085800`
- `0x140087524`
- `0x140087548`
- `0x140087754`
- `0x1400877b4`
- `0x140087800`
- `0x14008815c`
- `0x1400c40e0`
- `0x1400d630c`
- `0x1401332f0`
- `0x140177ddc`
- `0x140201d5c`
- `0x14021601c`
- `0x14025a28c`
- `0x14025a3dc`

## import_xrefs

- `container!WcLaunchContainer` at `0x14008760e`
- `container!WcLaunchContainer` at `0x14008760e`
- `container!WcRegisterForContainerTerminationNotification` at `0x1400875af`
- `container!WcRegisterForContainerTerminationNotification` at `0x1400875af`
- `container!WcSetRegistryFlushState` at `0x1400876af`
- `container!WcSetRegistryFlushState` at `0x1400876af`

## string_xrefs

- `0x1400875c6`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`
- `0x140087625`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`
- `0x1400876c6`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall ComputeService::ContainerUtilities::WindowsContainerLaunchAndConnect(
        _QWORD *a1,
        __int64 a2,
        _QWORD *a3,
        ComputeService::Management::CancellationToken *a4,
        char a5)
{
  __int64 v8; // rbx
  __int64 v9; // rdi
  int v10; // eax
  __int64 v11; // rax
  int v12; // eax
  _QWORD *v13; // rcx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  int v16; // eax
  __int64 v18; // [rsp+20h] [rbp-61h] BYREF
  void *v19[3]; // [rsp+28h] [rbp-59h] BYREF
  _BYTE v20[24]; // [rsp+40h] [rbp-41h] BYREF
  __int64 v21; // [rsp+58h] [rbp-29h] BYREF
  __int64 v22; // [rsp+60h] [rbp-21h] BYREF
  _QWORD v23[3]; // [rsp+68h] [rbp-19h] BYREF
  unsigned __int64 v24; // [rsp+80h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+47h]

  v19[0] = a1;
  v21 = a2;
  v22 = 0;
  v8 = 0;
  v18 = 0;
  v9 = *(_QWORD *)(*a3 + 8LL);
  _reset___unique_storage_U__resource_policy_PEAU_WC_CONTAINER_NOTIFICATION__P6AJPEAU1___E_1_WcReleaseContainerTerminationNotification__YAJ0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAAXPEAU_WC_CONTAINER_NOTIFICATION___Z(
    &v22,
    0);
  v10 = WcRegisterForContainerTerminationNotification(
          v21,
          &ComputeService::ContainerUtilities::Details::ContainerTerminationCallback,
          v9 + 72,
          &v22);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x336,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
      (const char *)(unsigned int)v10,
      v18);
  if ( !*(_BYTE *)(ComputeService::Management::ComputeSystem::GetStateAs<ComputeService::Management::BaseContainerState>(*a3)
                 + 49) )
  {
    v11 = lambda_bffcbee7f2770ed84e920f222a7c63ec_::_lambda_bffcbee7f2770ed84e920f222a7c63ec_(v19, &v21, &v22);
    wil::ScopeExit__lambda_1c6b154b8443c82d45248bfbc35d940e___(v20, v11);
    v12 = WcLaunchContainer(v21, 0);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x344,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
        (const char *)(unsigned int)v12,
        v18);
    ComputeService::ContainerUtilities::QueryContainerNamespacePath(v23, v21);
    v19[0] = 0;
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      v19,
      0);
    v13 = v23;
    if ( v24 > 7 )
      v13 = (_QWORD *)v23[0];
    ContainerGetServiceStartEvent(v13, v19);
    ComputeService::Management::CancellationToken::Wait(a4, v19[0], 0x36EE80u);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &v18,
      0);
    v14 = v23;
    if ( v24 > 7 )
      v14 = (_QWORD *)v23[0];
    ContainerGetServiceBinding(v14, &v18);
    if ( a5 )
    {
      LOBYTE(v15) = 1;
      v16 = WcSetRegistryFlushState(v21, v15);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x352,
          (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
          (const char *)(unsigned int)v16,
          v18);
    }
    v20[16] = 0;
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v19);
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v23);
    wil::details::ScopeExitFn__lambda_1c6b154b8443c82d45248bfbc35d940e___::_ScopeExitFn__lambda_1c6b154b8443c82d45248bfbc35d940e___(v20);
    v8 = v18;
  }
  *a1 = v22;
  v22 = 0;
  a1[1] = v8;
  v18 = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v18);
  __1__unique_storage_U__resource_policy_PEAU_WC_CONTAINER_NOTIFICATION__P6AJPEAU1___E_1_WcReleaseContainerTerminationNotification__YAJ0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v22);
  return a1;
}

```

## disassembly

```asm
0x140087548  push    rbp
0x14008754a  push    rbx
0x14008754b  push    rsi
0x14008754c  push    rdi
0x14008754d  push    r14
0x14008754f  push    r15
0x140087551  lea     rbp, [rsp-17h]
0x140087556  sub     rsp, 98h
0x14008755d  mov     rax, cs:__security_cookie
0x140087564  xor     rax, rsp
0x140087567  mov     [rbp+3Fh+var_38], rax
0x14008756b  mov     r15, r9
0x14008756e  mov     r14, r8
0x140087571  mov     rsi, rcx
0x140087574  mov     [rbp+3Fh+var_98], rcx
0x140087578  mov     [rbp+3Fh+var_68], rdx
0x14008757c  mov     [rbp+3Fh+var_60], 0
0x140087584  xor     ebx, ebx
0x140087586  mov     [rbp+3Fh+var_A0], rbx
0x14008758a  mov     rax, [r8]
0x14008758d  mov     rdi, [rax+8]
0x140087591  xor     edx, edx
0x140087593  lea     rcx, [rbp+3Fh+var_60]
0x140087597  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_WC_CONTAINER_NOTIFICATION@@P6AJPEAU1@@_E$1?WcReleaseContainerTerminationNotification@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_WC_CONTAINER_NOTIFICATION@@@Z
0x14008759c  lea     r8, [rdi+48h]
0x1400875a0  lea     r9, [rbp+3Fh+var_60]
0x1400875a4  lea     rdx, ?ContainerTerminationCallback@Details@ContainerUtilities@ComputeService@@YAXPEAXW4_WC_CONTAINER_TERMINATION_REASON@@PEAU_WC_CONTAINER_NOTIFICATION@@0@Z; ComputeService::ContainerUtilities::Details::ContainerTerminationCallback(void *,_WC_CONTAINER_TERMINATION_REASON,_WC_CONTAINER_NOTIFICATION *,void *)
0x1400875ab  mov     rcx, [rbp+3Fh+var_68]
0x1400875af  call    cs:__imp_WcRegisterForContainerTerminationNotification
0x1400875b6  nop     dword ptr [rax+rax+00h]
0x1400875bb  mov     rcx, [rbp+47h]; this
0x1400875bf  test    eax, eax
0x1400875c1  jns     short loc_1400875D8
0x1400875c3  mov     r9d, eax; char *
0x1400875c6  lea     r8, aOnecoreVmCompu_146; "onecore\\vm\\compute\\management\\share"...
0x1400875cd  mov     edx, 336h; void *
0x1400875d2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400875d8  mov     rcx, [r14]
0x1400875db  call    ??$GetStateAs@UBaseContainerState@Management@ComputeService@@@ComputeSystem@Management@ComputeService@@QEAAPEAUBaseContainerState@12@XZ; ComputeService::Management::ComputeSystem::GetStateAs<ComputeService::Management::BaseContainerState>(void)
0x1400875e0  cmp     byte ptr [rax+31h], 0
0x1400875e4  jnz     loc_1400876FD
0x1400875ea  lea     r8, [rbp+3Fh+var_60]
0x1400875ee  lea     rdx, [rbp+3Fh+var_68]
0x1400875f2  lea     rcx, [rbp+3Fh+var_98]
0x1400875f6  call    _lambda_bffcbee7f2770ed84e920f222a7c63ec____lambda_bffcbee7f2770ed84e920f222a7c63ec_
0x1400875fb  mov     rdx, rax
0x1400875fe  lea     rcx, [rbp+3Fh+var_80]
0x140087602  call    wil__ScopeExit__lambda_1c6b154b8443c82d45248bfbc35d940e___
0x140087607  nop
0x140087608  xor     edx, edx
0x14008760a  mov     rcx, [rbp+3Fh+var_68]
0x14008760e  call    cs:__imp_WcLaunchContainer
0x140087615  nop     dword ptr [rax+rax+00h]
0x14008761a  mov     rcx, [rbp+47h]; this
0x14008761e  test    eax, eax
0x140087620  jns     short loc_140087637
0x140087622  mov     r9d, eax; char *
0x140087625  lea     r8, aOnecoreVmCompu_146; "onecore\\vm\\compute\\management\\share"...
0x14008762c  mov     edx, 344h; void *
0x140087631  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140087637  mov     rdx, [rbp+3Fh+var_68]
0x14008763b  lea     rcx, [rbp+3Fh+var_58]
0x14008763f  call    ?QueryContainerNamespacePath@ContainerUtilities@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; ComputeService::ContainerUtilities::QueryContainerNamespacePath(void *)
0x140087644  nop
0x140087645  mov     [rbp+3Fh+var_98], 0
0x14008764d  xor     edx, edx
0x14008764f  lea     rcx, [rbp+3Fh+var_98]
0x140087653  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140087658  lea     rcx, [rbp+3Fh+var_58]
0x14008765c  cmp     [rbp+3Fh+var_40], 7
0x140087661  cmova   rcx, [rbp+3Fh+var_58]
0x140087666  lea     rdx, [rbp+3Fh+var_98]
0x14008766a  call    ContainerGetServiceStartEvent
0x14008766f  mov     r8d, 36EE80h; unsigned int
0x140087675  mov     rdx, [rbp+3Fh+var_98]; void *
0x140087679  mov     rcx, r15; this
0x14008767c  call    ?Wait@CancellationToken@Management@ComputeService@@QEBAXPEAXK@Z; ComputeService::Management::CancellationToken::Wait(void *,ulong)
0x140087681  xor     edx, edx
0x140087683  lea     rcx, [rbp+3Fh+var_A0]
0x140087687  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x14008768c  lea     rcx, [rbp+3Fh+var_58]
0x140087690  cmp     [rbp+3Fh+var_40], 7
0x140087695  cmova   rcx, [rbp+3Fh+var_58]
0x14008769a  lea     rdx, [rbp+3Fh+var_A0]
0x14008769e  call    ContainerGetServiceBinding
0x1400876a3  cmp     [rbp+3Fh+arg_20], 0
0x1400876a7  jz      short loc_1400876D8
0x1400876a9  mov     dl, 1
0x1400876ab  mov     rcx, [rbp+3Fh+var_68]
0x1400876af  call    cs:__imp_WcSetRegistryFlushState
0x1400876b6  nop     dword ptr [rax+rax+00h]
0x1400876bb  mov     rcx, [rbp+47h]; this
0x1400876bf  test    eax, eax
0x1400876c1  jns     short loc_1400876D8
0x1400876c3  mov     r9d, eax; char *
0x1400876c6  lea     r8, aOnecoreVmCompu_146; "onecore\\vm\\compute\\management\\share"...
0x1400876cd  mov     edx, 352h; void *
0x1400876d2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400876d8  mov     [rbp+3Fh+var_70], 0
0x1400876dc  lea     rcx, [rbp+3Fh+var_98]
0x1400876e0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400876e5  nop
0x1400876e6  lea     rcx, [rbp+3Fh+var_58]; this
0x1400876ea  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400876ef  nop
0x1400876f0  lea     rcx, [rbp+3Fh+var_80]
0x1400876f4  call    wil__details__ScopeExitFn__lambda_1c6b154b8443c82d45248bfbc35d940e______ScopeExitFn__lambda_1c6b154b8443c82d45248bfbc35d940e___
0x1400876f9  mov     rbx, [rbp+3Fh+var_A0]
0x1400876fd  mov     rcx, [rbp+3Fh+var_60]
0x140087701  mov     [rsi], rcx
0x140087704  mov     [rbp+3Fh+var_60], 0
0x14008770c  mov     [rsi+8], rbx
0x140087710  mov     [rbp+3Fh+var_A0], 0
0x140087718  lea     rcx, [rbp+3Fh+var_A0]
0x14008771c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140087721  nop
0x140087722  lea     rcx, [rbp+3Fh+var_60]
0x140087726  call    ??1?$unique_storage@U?$resource_policy@PEAU_WC_CONTAINER_NOTIFICATION@@P6AJPEAU1@@_E$1?WcReleaseContainerTerminationNotification@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14008772b  mov     rax, rsi
0x14008772e  mov     rcx, [rbp+3Fh+var_38]
0x140087732  xor     rcx, rsp; StackCookie
0x140087735  call    __security_check_cookie
0x14008773a  add     rsp, 98h
0x140087741  pop     r15
0x140087743  pop     r14
0x140087745  pop     rdi
0x140087746  pop     rsi
0x140087747  pop     rbx
0x140087748  pop     rbp
0x140087749  retn
```
