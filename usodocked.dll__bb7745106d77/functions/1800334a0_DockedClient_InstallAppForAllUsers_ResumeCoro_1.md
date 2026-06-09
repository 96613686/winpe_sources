# DockedClient::InstallAppForAllUsers$_ResumeCoro$1

- ea: `0x1800334a0`
- end: `0x180033b70`
- name: `DockedClient::InstallAppForAllUsers$_ResumeCoro$1`
- size: `1744`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180033b78`

## callees

- `0x180007660`
- `0x180007dc0`
- `0x1800209fc`
- `0x1800285d0`
- `0x180028704`
- `0x180028c48`
- `0x18002c82c`
- `0x18002d2cc`
- `0x180031f7c`
- `0x1800334a0`
- `0x180036834`
- `0x18003738c`
- `0x1800375ec`
- `0x18003a7b4`
- `0x18003b958`
- `0x18003bf74`
- `0x180071010`

## import_xrefs

- `msvcp_win!_Thrd_yield` at `0x18003368f`
- `msvcp_win!_Thrd_yield` at `0x18003373a`
- `msvcp_win!_Thrd_yield` at `0x18003387e`
- `msvcp_win!_Thrd_yield` at `0x180033939`
- `msvcp_win!_Thrd_yield` at `0x18003368f`
- `msvcp_win!_Thrd_yield` at `0x18003373a`
- `msvcp_win!_Thrd_yield` at `0x18003387e`
- `msvcp_win!_Thrd_yield` at `0x180033939`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800335b1`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800337e1`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800335b1`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800337e1`

## string_xrefs

- `0x1800337b3`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedclient.cpp`
- `0x18003398a`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall DockedClient::InstallAppForAllUsers__ResumeCoro_1(__int64 a1, __int64 a2, __int64 a3)
{
  __int16 *v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 v11; // rax
  volatile __int64 *v12; // rbx
  __int64 *v13; // rax
  __int64 v14; // rdx
  volatile __int64 *v15; // rbx
  const char *v16; // r9
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rax
  volatile __int64 *v21; // rbx
  volatile __int64 **v22; // r12
  __int64 *v23; // rbx
  __int64 *v24; // r14
  __int64 v25; // rax
  volatile __int64 *v26; // rbx
  const char *v27; // r9
  __int64 *v28; // r12
  __int64 v29; // rbx
  __int64 v30; // rcx
  __int64 v31; // r15
  volatile signed __int32 *v32; // rbx
  int v33; // [rsp+20h] [rbp-148h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v5 = &_ImageBase;
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 3:
      goto LABEL_80;
    case 2:
      LOBYTE(a3) = 3;
      LOBYTE(v5) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_TFLHydrate>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_TFLHydrate>::GetImpl'::`2'::impl,
        v5,
        a3);
      *(_QWORD *)(a1 + 16) = 0;
      *(_DWORD *)(a1 + 24) = 0;
      *(_QWORD *)(a1 + 272) = &qword_180095C18;
      _InterlockedAdd64(&qword_180095C18, 1u);
      if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::StagePackageOptions,winrt::Windows::Foundation::IActivationFactory> )
      {
        _lambda_f53e1bd8d161f883aae135691cd6bc0e_::operator()(
          v6,
          a1 + 32,
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::StagePackageOptions,winrt::Windows::Foundation::IActivationFactory>);
        _InterlockedDecrement64(&qword_180095C18);
      }
      else
      {
        _InterlockedDecrement64(&qword_180095C18);
        *(_QWORD *)(a1 + 280) = _lambda_f53e1bd8d161f883aae135691cd6bc0e_::_lambda_invoker_cdecl_;
        winrt::impl::factory_cache_entry<winrt::Windows::Management::Deployment::StagePackageOptions,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Management::Deployment::StagePackageOptions (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
          v6,
          a1 + 32);
      }
      v7 = *(unsigned int *)(a1 + 416);
      if ( (_DWORD)v7 )
      {
        v9 = *(_QWORD *)(a1 + 408);
        if ( *(_WORD *)(v9 + 2 * v7) )
          abort();
        v8 = a1 + 56;
        *(_DWORD *)(a1 + 56) = 1;
        *(_DWORD *)(a1 + 60) = v7;
        *(_QWORD *)(a1 + 72) = v9;
      }
      else
      {
        v8 = 0;
      }
      *(_QWORD *)(a1 + 48) = v8;
      v10 = a1 + 288;
      *(_QWORD *)(a1 + 288) = a1 + 48;
      *(_QWORD *)(a1 + 296) = &qword_180095C78;
      _InterlockedAdd64(&qword_180095C78, 1u);
      if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory> )
      {
        _lambda_0a61d549bec6c444b35123f4c9509ca7_::operator()(
          v10,
          a1 + 40,
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>);
        _InterlockedDecrement64(&qword_180095C78);
      }
      else
      {
        _InterlockedDecrement64(&qword_180095C78);
        winrt::impl::factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>::call<_lambda_0a61d549bec6c444b35123f4c9509ca7_ &>(
          v10,
          a1 + 40,
          a1 + 288);
      }
      *(_QWORD *)(a1 + 368) = a1 + 16;
      v11 = winrt::impl::consume_Windows_Management_Deployment_IPackageManager9<winrt::Windows::Management::Deployment::PackageManager>::StagePackageByUriAsync(
              a1 + 400,
              a1 + 80,
              a1 + 40,
              a1 + 32);
      *(_QWORD *)(a1 + 88) = 0;
      *(_QWORD *)(a1 + 96) = v11;
      *(_QWORD *)(a1 + 104) = 0;
      *(_BYTE *)(a1 + 112) = 1;
      *(_WORD *)(a1 + 8) = 4;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Management::Deployment::DeploymentResult,winrt::Windows::Management::Deployment::DeploymentProgress>,1>::await_suspend<std::experimental::coroutine_traits<Concurrency::task<DockedClient::AppInstallResult>,DockedClient *,winrt::Windows::Management::Deployment::PackageManager,std::basic_string_view<unsigned short>,std::basic_string_view<unsigned short>>::promise_type>(
                              a1 + 88,
                              a1) )
        return;
      goto LABEL_26;
    case 4:
LABEL_26:
      v13 = (__int64 *)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Management::Deployment::DeploymentResult,winrt::Windows::Management::Deployment::DeploymentProgress>,1>::await_resume(
                         a1 + 88,
                         a1 + 120);
      if ( (__int64 *)(a1 + 16) != v13 )
      {
        v14 = *v13;
        *v13 = 0;
        *(_QWORD *)(a1 + 16) = v14;
      }
      if ( *(_QWORD *)(a1 + 120) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 120);
      v15 = *(volatile __int64 **)(a1 + 88);
      if ( v15 )
      {
        while ( _InterlockedExchange64(v15, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 80) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 80);
      if ( *(_QWORD *)(a1 + 40) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 40);
      if ( *(_QWORD *)(a1 + 32) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 32);
      v16 = (const char *)*(unsigned int *)winrt::impl::consume_Windows_Management_Deployment_IDeploymentResult<winrt::Windows::Management::Deployment::IDeploymentResult>::ExtendedErrorCode(
                                             a1 + 16,
                                             a1 + 128);
      *(_DWORD *)(a1 + 24) = (_DWORD)v16;
      if ( (int)v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x175,
          (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedclient.cpp",
          v16,
          v33);
      v17 = *(unsigned int *)(a1 + 432);
      if ( (_DWORD)v17 )
      {
        v19 = *(_QWORD *)(a1 + 424);
        if ( *(_WORD *)(v19 + 2 * v17) )
          abort();
        v18 = a1 + 144;
        *(_DWORD *)(a1 + 144) = 1;
        *(_DWORD *)(a1 + 148) = v17;
        *(_QWORD *)(a1 + 160) = v19;
      }
      else
      {
        v18 = 0;
      }
      *(_QWORD *)(a1 + 136) = v18;
      v20 = winrt::impl::consume_Windows_Management_Deployment_IPackageManager6<winrt::Windows::Management::Deployment::PackageManager>::ProvisionPackageForAllUsersAsync(
              *(_QWORD *)(a1 + 368) + 384LL,
              a1 + 168);
      *(_QWORD *)(a1 + 176) = 0;
      *(_QWORD *)(a1 + 184) = v20;
      *(_QWORD *)(a1 + 192) = 0;
      *(_BYTE *)(a1 + 200) = 1;
      *(_WORD *)(a1 + 8) = 6;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Management::Deployment::DeploymentResult,winrt::Windows::Management::Deployment::DeploymentProgress>,1>::await_suspend<std::experimental::coroutine_traits<Concurrency::task<DockedClient::AppInstallResult>,DockedClient *,winrt::Windows::Management::Deployment::PackageManager,std::basic_string_view<unsigned short>,std::basic_string_view<unsigned short>>::promise_type>(
                              a1 + 176,
                              a1) )
        return;
      goto LABEL_58;
    case 5:
      v12 = *(volatile __int64 **)(a1 + 88);
      if ( v12 )
      {
        while ( _InterlockedExchange64(v12, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 80) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 80);
      if ( *(_QWORD *)(a1 + 40) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 40);
      if ( *(_QWORD *)(a1 + 32) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 32);
      goto LABEL_80;
    case 6:
LABEL_58:
      v22 = (volatile __int64 **)(a1 + 176);
      v23 = (__int64 *)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Management::Deployment::DeploymentResult,winrt::Windows::Management::Deployment::DeploymentProgress>,1>::await_resume(
                         a1 + 176,
                         a1 + 208);
      v24 = (__int64 *)(a1 + 16);
      if ( (__int64 *)(a1 + 16) != v23 )
      {
        if ( *v24 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 16);
        v25 = *v23;
        *v23 = 0;
        *v24 = v25;
      }
      if ( *(_QWORD *)(a1 + 208) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 208);
      v26 = *v22;
      if ( *v22 )
      {
        while ( _InterlockedExchange64(v26, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 168) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 168);
      v27 = (const char *)*(unsigned int *)winrt::impl::consume_Windows_Management_Deployment_IDeploymentResult<winrt::Windows::Management::Deployment::IDeploymentResult>::ExtendedErrorCode(
                                             a1 + 16,
                                             a1 + 216);
      *(_DWORD *)(a1 + 24) = (_DWORD)v27;
      if ( (int)v27 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x179,
          (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedclient.cpp",
          v27,
          v33);
      *(_QWORD *)(a1 + 248) = 0;
      v28 = (__int64 *)(a1 + 256);
      v29 = *v24;
      *(_QWORD *)(a1 + 256) = *v24;
      if ( v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
      *(_DWORD *)(a1 + 264) = 0;
      *(_DWORD *)(a1 + 268) = 256;
      v30 = a1 + 328;
      *(_DWORD *)(a1 + 328) = *(_DWORD *)(a1 + 248);
      v31 = *v28;
      *(_QWORD *)(a1 + 336) = *v28;
      if ( v31 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
        v30 = a1 + 328;
      }
      *(_DWORD *)(a1 + 344) = *(_DWORD *)(a1 + 264);
      *(_BYTE *)(a1 + 348) = *(_BYTE *)(a1 + 268);
      *(_BYTE *)(a1 + 349) = *(_BYTE *)(a1 + 269);
      Concurrency::task_completion_event<DockedClient::AppInstallResult>::set(a1 - 16, v30);
      if ( v31 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 256);
      if ( v29 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 16);
      goto LABEL_80;
    case 7:
      v21 = *(volatile __int64 **)(a1 + 176);
      if ( v21 )
      {
        while ( _InterlockedExchange64(v21, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 168) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 168);
      if ( *(_QWORD *)(a1 + 16) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 16);
LABEL_80:
      v32 = *(volatile signed __int32 **)(a1 - 8);
      if ( v32 )
      {
        if ( _InterlockedExchangeAdd(v32 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
          if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
        }
      }
      if ( *(_QWORD *)(a1 + 400) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 400);
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 16));
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x1800334a0  mov     r11, rsp
0x1800334a3  mov     [r11+10h], rbx
0x1800334a7  mov     [r11+18h], rsi
0x1800334ab  mov     [r11+8], rcx
0x1800334af  push    rdi
0x1800334b0  push    r12
0x1800334b2  push    r13
0x1800334b4  push    r14
0x1800334b6  push    r15
0x1800334b8  sub     rsp, 140h
0x1800334bf  mov     rax, cs:__security_cookie
0x1800334c6  xor     rax, rsp
0x1800334c9  mov     [rsp+168h+var_38], rax
0x1800334d1  mov     rsi, rcx
0x1800334d4  mov     r13, rcx
0x1800334d7  mov     [rsp+168h+var_108], rcx
0x1800334dc  movzx   eax, word ptr [rsi+8]
0x1800334e0  mov     [rsp+168h+var_128], ax
0x1800334e5  mov     r12d, 1
0x1800334eb  add     ax, r12w
0x1800334ef  cmp     ax, 8; switch 9 cases
0x1800334f3  ja      def_18003350E; jumptable 000000018003350E default case, cases 1,2
0x1800334f9  movsx   rax, ax
0x1800334fd  lea     rdx, __ImageBase
0x180033504  mov     ecx, ds:(jpt_18003350E - 180000000h)[rdx+rax*4]
0x18003350b  add     rcx, rdx
0x18003350e  jmp     rcx; switch jump
0x180033510  xor     edi, edi; jumptable 000000018003350E case 4
0x180033512  jmp     loc_180033AB4
0x180033517  xor     edi, edi; jumptable 000000018003350E case 3
0x180033519  mov     r8b, 3
0x18003351c  mov     dl, r12b
0x18003351f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TFLHydrate@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TFLHydrate@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TFLHydrate> `wil::Feature<__WilFeatureTraits_Feature_TFLHydrate>::GetImpl(void)'::`2'::impl
0x180033526  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_TFLHydrate@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TFLHydrate>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003352b  lea     r15, [rsi+10h]
0x18003352f  mov     [r15], rdi
0x180033532  mov     [rsi+18h], edi
0x180033535  lea     rax, qword_180095C18
0x18003353c  mov     [rsi+110h], rax
0x180033543  lock add cs:qword_180095C18, r12
0x18003354b  lea     r14, [rsi+20h]
0x18003354f  cmp     cs:??$factory_cache_entry_v@UStagePackageOptions@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UStagePackageOptions@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, rdi; factory_cache_entry<winrt::Windows::Management::Deployment::StagePackageOptions,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Management::Deployment::StagePackageOptions,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::StagePackageOptions,winrt::Windows::Foundation::IActivationFactory>
0x180033556  jz      short loc_180033572
0x180033558  lea     r8, ??$factory_cache_entry_v@UStagePackageOptions@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UStagePackageOptions@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Management::Deployment::StagePackageOptions,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Management::Deployment::StagePackageOptions,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::StagePackageOptions,winrt::Windows::Foundation::IActivationFactory>
0x18003355f  mov     rdx, r14
0x180033562  call    ??R_lambda_f53e1bd8d161f883aae135691cd6bc0e_@@QEBA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_f53e1bd8d161f883aae135691cd6bc0e_::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x180033567  nop
0x180033568  lock dec cs:qword_180095C18
0x180033570  jmp     short loc_180033594
0x180033572  lock dec cs:qword_180095C18
0x18003357a  lea     r8, [rsi+118h]
0x180033581  lea     rax, ?_lambda_invoker_cdecl_@_lambda_f53e1bd8d161f883aae135691cd6bc0e_@@CA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_f53e1bd8d161f883aae135691cd6bc0e_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x180033588  mov     [r8], rax
0x18003358b  mov     rdx, r14
0x18003358e  call    ??$call@P6A?AUStagePackageOptions@Deployment@Management@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UStagePackageOptions@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUStagePackageOptions@Deployment@Management@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z
0x180033593  nop
0x180033594  mov     ecx, [rsi+1A0h]
0x18003359a  test    ecx, ecx
0x18003359c  jnz     short loc_1800335A3
0x18003359e  mov     rdx, rdi
0x1800335a1  jmp     short loc_1800335C6
0x1800335a3  mov     r8, [rsi+198h]
0x1800335aa  cmp     [r8+rcx*2], di
0x1800335af  jz      short loc_1800335B8
0x1800335b1  call    cs:__imp_abort
0x1800335b8  lea     rdx, [rsi+38h]
0x1800335bc  mov     [rdx], r12d
0x1800335bf  mov     [rsi+3Ch], ecx
0x1800335c2  mov     [rsi+48h], r8
0x1800335c6  mov     rcx, r13
0x1800335c9  mov     eax, 30h ; '0'
0x1800335ce  add     rax, rcx
0x1800335d1  mov     [rax], rdx
0x1800335d4  lea     rcx, [rsi+120h]
0x1800335db  mov     [rcx], rax
0x1800335de  lea     rax, qword_180095C78
0x1800335e5  mov     [rsi+128h], rax
0x1800335ec  lock add cs:qword_180095C78, r12
0x1800335f4  lea     rbx, [rsi+28h]
0x1800335f8  cmp     cs:??$factory_cache_entry_v@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@3U?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@12@A, rdi; factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>::winrt::factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>
0x1800335ff  jz      short loc_18003361B
0x180033601  lea     r8, ??$factory_cache_entry_v@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@3U?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@12@A; factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>::winrt::factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>
0x180033608  mov     rdx, rbx
0x18003360b  call    ??R_lambda_0a61d549bec6c444b35123f4c9509ca7_@@QEBA@AEBUIUriRuntimeClassFactory@Foundation@Windows@winrt@@@Z; _lambda_0a61d549bec6c444b35123f4c9509ca7_::operator()(winrt::Windows::Foundation::IUriRuntimeClassFactory const &)
0x180033610  nop
0x180033611  lock dec cs:qword_180095C78
0x180033619  jmp     short loc_18003362F
0x18003361b  lock dec cs:qword_180095C78
0x180033623  mov     r8, rcx
0x180033626  mov     rdx, rbx
0x180033629  call    ??$call@AEAV_lambda_0a61d549bec6c444b35123f4c9509ca7_@@@?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@QEAA?A_PAEAV_lambda_0a61d549bec6c444b35123f4c9509ca7_@@@Z
0x18003362e  nop
0x18003362f  mov     [rsi+170h], r15
0x180033636  lea     rdx, [rsi+50h]
0x18003363a  lea     rcx, [r15+180h]
0x180033641  mov     r9, r14
0x180033644  mov     r8, rbx
0x180033647  call    ?StagePackageByUriAsync@?$consume_Windows_Management_Deployment_IPackageManager9@UPackageManager@Deployment@Management@Windows@winrt@@@impl@winrt@@QEBA@AEBUUri@Foundation@Windows@3@AEBUStagePackageOptions@Deployment@Management@63@@Z; winrt::impl::consume_Windows_Management_Deployment_IPackageManager9<winrt::Windows::Management::Deployment::PackageManager>::StagePackageByUriAsync(winrt::Windows::Foundation::Uri const &,winrt::Windows::Management::Deployment::StagePackageOptions const &)
0x18003364c  nop
0x18003364d  lea     rcx, [rsi+58h]
0x180033651  mov     [rcx], rdi
0x180033654  mov     [rsi+60h], rax
0x180033658  mov     [rsi+68h], rdi
0x18003365c  mov     [rsi+70h], r12b
0x180033660  mov     eax, 4
0x180033665  mov     [rsi+8], ax
0x180033669  mov     rdx, rsi
0x18003366c  call    ??$await_suspend@Upromise_type@?$coroutine_traits@V?$task@UAppInstallResult@DockedClient@@@Concurrency@@PEAVDockedClient@@UPackageManager@Deployment@Management@Windows@winrt@@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V9std@@@experimental@std@@@?$await_adapter@U?$IAsyncOperationWithProgress@UDeploymentResult@Deployment@Management@Windows@winrt@@UDeploymentProgress@2345@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@V?$task@UAppInstallResult@DockedClient@@@Concurrency@@PEAVDockedClient@@UPackageManager@Deployment@Management@Windows@winrt@@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V9std@@@experimental@std@@@experimental@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Management::Deployment::DeploymentResult,winrt::Windows::Management::Deployment::DeploymentProgress>,1>::await_suspend<std::experimental::coroutine_traits<Concurrency::task<DockedClient::AppInstallResult>,DockedClient *,winrt::Windows::Management::Deployment::PackageManager,std::basic_string_view<ushort>,std::basic_string_view<ushort>>::promise_type>(std::experimental::coroutine_handle<std::experimental::coroutine_traits<Concurrency::task<DockedClient::AppInstallResult>,DockedClient *,winrt::Windows::Management::Deployment::PackageManager,std::basic_string_view<ushort>,std::basic_string_view<ushort>>::promise_type>)
0x180033671  test    al, al
0x180033673  jz      short loc_1800336EC
0x180033675  jmp     loc_180033B1C
0x18003367a  mov     rbx, [rsi+58h]; jumptable 000000018003350E case 6
0x18003367e  xor     edi, edi
0x180033680  test    rbx, rbx
0x180033683  jz      short loc_1800336A0
0x180033685  mov     [rsp+168h+var_D0], rbx
0x18003368d  jmp     short loc_180033695
0x18003368f  call    cs:__imp__Thrd_yield
0x180033695  mov     rax, rdi
0x180033698  xchg    rax, [rbx]
0x18003369b  cmp     rax, r12
0x18003369e  jz      short loc_18003368F
0x1800336a0  lea     rcx, [rsi+50h]
0x1800336a4  mov     rax, [rcx]
0x1800336a7  mov     [rsp+168h+var_100], rax
0x1800336ac  test    rax, rax
0x1800336af  jz      short loc_1800336B7
0x1800336b1  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800336b6  nop
0x1800336b7  lea     rcx, [rsi+28h]
0x1800336bb  mov     rax, [rcx]
0x1800336be  mov     [rsp+168h+var_F8], rax
0x1800336c3  test    rax, rax
0x1800336c6  jz      short loc_1800336CE
0x1800336c8  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800336cd  nop
0x1800336ce  lea     rcx, [rsi+20h]
0x1800336d2  mov     rax, [rcx]
0x1800336d5  mov     [rsp+168h+var_F0], rax
0x1800336da  test    rax, rax
0x1800336dd  jz      short loc_1800336E5
0x1800336df  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800336e4  nop
0x1800336e5  jmp     loc_180033AB4
0x1800336ea  xor     edi, edi; jumptable 000000018003350E case 5
0x1800336ec  lea     rbx, [rsi+78h]
0x1800336f0  mov     rdx, rbx
0x1800336f3  lea     rcx, [rsi+58h]
0x1800336f7  call    ?await_resume@?$await_adapter@U?$IAsyncOperationWithProgress@UDeploymentResult@Deployment@Management@Windows@winrt@@UDeploymentProgress@2345@@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Management::Deployment::DeploymentResult,winrt::Windows::Management::Deployment::DeploymentProgress>,1>::await_resume(void)
0x1800336fc  lea     r14, [rsi+10h]
0x180033700  cmp     r14, rax
0x180033703  jz      short loc_18003370E
0x180033705  mov     rdx, [rax]
0x180033708  mov     [rax], rdi
0x18003370b  mov     [r14], rdx
0x18003370e  mov     rax, [rbx]
0x180033711  mov     [rsp+168h+var_E0], rax
0x180033719  test    rax, rax
0x18003371c  jz      short loc_180033727
0x18003371e  mov     rcx, rbx
0x180033721  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180033726  nop
0x180033727  mov     rbx, [rsi+58h]
0x18003372b  test    rbx, rbx
0x18003372e  jz      short loc_18003374B
0x180033730  mov     [rsp+168h+var_D0], rbx
0x180033738  jmp     short loc_180033740
0x18003373a  call    cs:__imp__Thrd_yield
0x180033740  mov     rax, rdi
0x180033743  xchg    rax, [rbx]
0x180033746  cmp     rax, r12
0x180033749  jz      short loc_18003373A
0x18003374b  lea     rcx, [rsi+50h]
0x18003374f  mov     rax, [rcx]
0x180033752  mov     [rsp+168h+var_100], rax
0x180033757  test    rax, rax
0x18003375a  jz      short loc_180033762
0x18003375c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180033761  nop
0x180033762  mov     rax, [rsi+28h]
0x180033766  mov     [rsp+168h+var_F8], rax
0x18003376b  test    rax, rax
0x18003376e  jz      short loc_18003377A
0x180033770  lea     rcx, [rsi+28h]
0x180033774  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180033779  nop
0x18003377a  lea     rcx, [rsi+20h]
0x18003377e  mov     rax, [rcx]
0x180033781  mov     [rsp+168h+var_F0], rax
0x180033786  test    rax, rax
0x180033789  jz      short loc_180033790
0x18003378b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180033790  lea     rdx, [rsi+80h]
0x180033797  mov     rcx, r14
0x18003379a  call    ?ExtendedErrorCode@?$consume_Windows_Management_Deployment_IDeploymentResult@UIDeploymentResult@Deployment@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Management_Deployment_IDeploymentResult<winrt::Windows::Management::Deployment::IDeploymentResult>::ExtendedErrorCode(void)
0x18003379f  mov     r9d, [rax]; char *
0x1800337a2  mov     [rsi+18h], r9d
0x1800337a6  mov     rcx, [rsp+168h]; this
0x1800337ae  test    r9d, r9d
0x1800337b1  jns     short loc_1800337C4
0x1800337b3  lea     r8, aOnecoreEnduser_23; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800337ba  mov     edx, 175h; void *
0x1800337bf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800337c4  mov     ecx, [rsi+1B0h]
0x1800337ca  test    ecx, ecx
0x1800337cc  jnz     short loc_1800337D3
0x1800337ce  mov     rdx, rdi
0x1800337d1  jmp     short loc_1800337FF
0x1800337d3  mov     r8, [rsi+1A8h]
0x1800337da  cmp     [r8+rcx*2], di
0x1800337df  jz      short loc_1800337E8
0x1800337e1  call    cs:__imp_abort
0x1800337e8  lea     rdx, [rsi+90h]
0x1800337ef  mov     [rdx], r12d
0x1800337f2  mov     [rsi+94h], ecx
0x1800337f8  mov     [rsi+0A0h], r8
0x1800337ff  mov     rcx, r13
0x180033802  mov     eax, 88h
0x180033807  lea     r8, [rax+rcx]
0x18003380b  mov     [r8], rdx
0x18003380e  mov     rcx, [rsi+170h]
0x180033815  lea     rdx, [rsi+0A8h]
0x18003381c  add     rcx, 180h
0x180033823  call    ?ProvisionPackageForAllUsersAsync@?$consume_Windows_Management_Deployment_IPackageManager6@UPackageManager@Deployment@Management@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Management_Deployment_IPackageManager6<winrt::Windows::Management::Deployment::PackageManager>::ProvisionPackageForAllUsersAsync(winrt::param::hstring const &)
0x180033828  nop
0x180033829  lea     rcx, [rsi+0B0h]
0x180033830  mov     [rcx], rdi
0x180033833  mov     [rsi+0B8h], rax
0x18003383a  mov     qword ptr [rsi+0C0h], 0
0x180033845  mov     [rsi+0C8h], r12b
0x18003384c  mov     eax, 6
0x180033851  mov     [rsi+8], ax
0x180033855  mov     rdx, rsi
0x180033858  call    ??$await_suspend@Upromise_type@?$coroutine_traits@V?$task@UAppInstallResult@DockedClient@@@Concurrency@@PEAVDockedClient@@UPackageManager@Deployment@Management@Windows@winrt@@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V9std@@@experimental@std@@@?$await_adapter@U?$IAsyncOperationWithProgress@UDeploymentResult@Deployment@Management@Windows@winrt@@UDeploymentProgress@2345@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@V?$task@UAppInstallResult@DockedClient@@@Concurrency@@PEAVDockedClient@@UPackageManager@Deployment@Management@Windows@winrt@@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V9std@@@experimental@std@@@experimental@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Management::Deployment::DeploymentResult,winrt::Windows::Management::Deployment::DeploymentProgress>,1>::await_suspend<std::experimental::coroutine_traits<Concurrency::task<DockedClient::AppInstallResult>,DockedClient *,winrt::Windows::Management::Deployment::PackageManager,std::basic_string_view<ushort>,std::basic_string_view<ushort>>::promise_type>(std::experimental::coroutine_handle<std::experimental::coroutine_traits<Concurrency::task<DockedClient::AppInstallResult>,DockedClient *,winrt::Windows::Management::Deployment::PackageManager,std::basic_string_view<ushort>,std::basic_string_view<ushort>>::promise_type>)
0x18003385d  test    al, al
0x18003385f  jz      short loc_1800338CA
0x180033861  jmp     loc_180033B1C
0x180033866  mov     rbx, [rsi+0B0h]; jumptable 000000018003350E case 8
0x18003386d  xor     edi, edi
0x18003386f  test    rbx, rbx
0x180033872  jz      short loc_18003388F
0x180033874  mov     [rsp+168h+var_B0], rbx
0x18003387c  jmp     short loc_180033884
0x18003387e  call    cs:__imp__Thrd_yield
0x180033884  mov     rax, rdi
0x180033887  xchg    rax, [rbx]
0x18003388a  cmp     rax, r12
0x18003388d  jz      short loc_18003387E
0x18003388f  lea     rcx, [rsi+0A8h]
0x180033896  mov     rax, [rcx]
0x180033899  mov     [rsp+168h+var_E8], rax
0x1800338a1  test    rax, rax
0x1800338a4  jz      short loc_1800338AC
0x1800338a6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800338ab  nop
0x1800338ac  lea     rcx, [rsi+10h]
0x1800338b0  mov     rax, [rcx]
0x1800338b3  mov     [rsp+168h+var_138], rax
0x1800338b8  test    rax, rax
0x1800338bb  jz      short loc_1800338C3
0x1800338bd  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800338c2  nop
0x1800338c3  jmp     loc_180033AB4
0x1800338c8  xor     edi, edi; jumptable 000000018003350E case 7
0x1800338ca  lea     r15, [rsi+0D0h]
0x1800338d1  lea     r12, [rsi+0B0h]
0x1800338d8  mov     rdx, r15
0x1800338db  mov     rcx, r12
0x1800338de  call    ?await_resume@?$await_adapter@U?$IAsyncOperationWithProgress@UDeploymentResult@Deployment@Management@Windows@winrt@@UDeploymentProgress@2345@@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Management::Deployment::DeploymentResult,winrt::Windows::Management::Deployment::DeploymentProgress>,1>::await_resume(void)
0x1800338e3  mov     rbx, rax
0x1800338e6  lea     r14, [rsi+10h]
0x1800338ea  cmp     r14, rax
0x1800338ed  jz      short loc_18003390D
0x1800338ef  mov     rcx, [r14]
0x1800338f2  mov     [rsp+168h+var_138], rcx
0x1800338f7  test    rcx, rcx
0x1800338fa  jz      short loc_180033904
0x1800338fc  mov     rcx, r14
0x1800338ff  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180033904  mov     rax, [rbx]
0x180033907  mov     [rbx], rdi
0x18003390a  mov     [r14], rax
0x18003390d  mov     rax, [r15]
0x180033910  mov     [rsp+168h+var_D8], rax
0x180033918  test    rax, rax
0x18003391b  jz      short loc_180033926
0x18003391d  mov     rcx, r15
0x180033920  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180033925  nop
0x180033926  mov     rbx, [r12]
0x18003392a  test    rbx, rbx
0x18003392d  jz      short loc_18003394B
0x18003392f  mov     [rsp+168h+var_B0], rbx
0x180033937  jmp     short loc_18003393F
0x180033939  call    cs:__imp__Thrd_yield
0x18003393f  mov     rax, rdi
0x180033942  xchg    rax, [rbx]
0x180033945  cmp     rax, 1
0x180033949  jz      short loc_180033939
0x18003394b  lea     rcx, [rsi+0A8h]
  ... truncated ...
```
