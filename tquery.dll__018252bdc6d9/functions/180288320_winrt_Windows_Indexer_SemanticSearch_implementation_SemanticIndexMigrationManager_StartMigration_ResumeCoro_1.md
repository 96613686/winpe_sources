# winrt::Windows::Indexer::SemanticSearch::implementation::SemanticIndexMigrationManager::StartMigration$_ResumeCoro$1

- ea: `0x180288320`
- end: `0x180288890`
- name: `winrt::Windows::Indexer::SemanticSearch::implementation::SemanticIndexMigrationManager::StartMigration$_ResumeCoro$1`
- size: `1392`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `35`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180288310`
- `0x180288898`

## callees

- `0x180038f08`
- `0x180140660`
- `0x18014067c`
- `0x180142234`
- `0x180143384`
- `0x1801433a0`
- `0x180143770`
- `0x1801438e0`
- `0x18014d4a4`
- `0x18014d7c0`
- `0x18014d7e0`
- `0x18014d800`
- `0x180189260`
- `0x180189280`
- `0x18018940c`
- `0x180189474`
- `0x180190820`
- `0x1801d1a60`
- `0x18027ea1c`
- `0x180281b28`
- `0x180281d58`
- `0x1802820dc`
- `0x180282fc8`
- `0x180283824`
- `0x180283fa8`
- `0x1802841d0`
- `0x180284230`
- `0x1802876e0`
- `0x180287cf8`
- `0x180287d48`
- `0x180287dcc`
- `0x180287e24`
- `0x180288320`
- `0x1802891a4`
- `0x1802891c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1802884fc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18028851d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1802884fc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18028851d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1802883f6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180288680`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1802883f6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180288680`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1802883c7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18028843d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1802883c7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18028843d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18028841b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1802884dc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1802886c6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18028841b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1802884dc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1802886c6`

## string_xrefs

- `0x1802885d3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall winrt::Windows::Indexer::SemanticSearch::implementation::SemanticIndexMigrationManager::StartMigration__ResumeCoro_1(
        _WORD *Block)
{
  bool v3; // bl
  winrt::impl::signal_awaiter *v4; // r14
  char *v5; // r12
  HANDLE v6; // rbx
  DWORD v7; // eax
  const char *v8; // r9
  void *v9; // rdx
  char *v10; // rbx
  wil::details **v11; // rax
  wil::details **v12; // rcx
  wil::details *v13; // rdx
  wil::details *v14; // r12
  void *v15; // rdx
  _QWORD *v16; // r14
  __int64 v17; // rbx
  _QWORD *v18; // r15
  __int64 v19; // rax
  _QWORD *v20; // rbx
  __int64 v21; // rax
  int v22; // [rsp+20h] [rbp-88h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  wil::details **v24; // [rsp+C0h] [rbp+18h]
  wil::details *v25; // [rsp+C8h] [rbp+20h]

  LOWORD(v22) = Block[16];
  switch ( (__int16)v22 )
  {
    case -1:
    case 3:
      goto LABEL_42;
    case 2:
      SemanticSearchTelemetry::SemanticIndexRebuildMigration();
      if ( dword_180369940 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                       + 16LL) )
      {
        Init_thread_header(&dword_180369940);
        if ( dword_180369940 == -1 )
        {
          qword_180369948 = CreateEventW(0, 1, 1, 0);
          atexit(winrt::Windows::Indexer::SemanticSearch::implementation::SemanticIndexMigrationManager::StartMigration_::_3_::_dynamic_atexit_destructor_for__sequentialMigrationEvent__);
          Init_thread_footer(&dword_180369940);
        }
      }
      AcquireSRWLockShared(&stru_1803690A0);
      *((_QWORD *)Block + 5) = &stru_1803690A0;
      v3 = qword_180369948 != 0;
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>();
      if ( !v3 )
      {
        AcquireSRWLockExclusive(&stru_1803690A0);
        *((_QWORD *)Block + 6) = &stru_1803690A0;
        if ( !qword_180369948 )
        {
          *((_QWORD *)Block + 7) = CreateEventW(0, 1, 1, 0);
          __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
            &qword_180369948,
            Block + 28);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Block + 28);
          if ( !qword_180369948 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xA5,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\tripolipi\\semanticindexmigrationmanager.cpp",
              (const char *)0x80004005LL,
              v22);
        }
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(Block + 24);
      }
      *((_QWORD *)Block + 8) = 0;
      *((_BYTE *)Block + 72) = 1;
      v4 = (winrt::impl::signal_awaiter *)(Block + 40);
      goto LABEL_22;
    case 4:
      goto LABEL_12;
    case 5:
      winrt::impl::signal_awaiter::~signal_awaiter((winrt::impl::signal_awaiter *)(Block + 40));
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_SetEvent_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Block + 32);
      goto LABEL_42;
    case 6:
      goto LABEL_38;
    case 7:
      winrt::cancellable_awaiter<winrt::impl::signal_awaiter>::~cancellable_awaiter<winrt::impl::signal_awaiter>(Block + 100);
      _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)(Block + 84));
      winrt::com_ptr<winrt::Windows::Indexer::SemanticSearch::implementation::SemanticIndexMigrationManager>::unconditional_release_ref(Block + 76);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_SetEvent_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Block + 32);
      goto LABEL_42;
    default:
      __debugbreak();
      return;
  }
  while ( 1 )
  {
LABEL_12:
    v4 = (winrt::impl::signal_awaiter *)(Block + 40);
    winrt::impl::signal_awaiter::await_resume((winrt::impl::signal_awaiter *)(Block + 40));
    winrt::impl::signal_awaiter::~signal_awaiter((winrt::impl::signal_awaiter *)(Block + 40));
    AcquireSRWLockExclusive(&stru_1803690A0);
    v5 = (char *)(Block + 68);
    *((_QWORD *)Block + 17) = &stru_1803690A0;
    v6 = qword_180369948;
    v7 = WaitForSingleObjectEx(qword_180369948, 0, 0);
    if ( v7 != 258 )
    {
      if ( v7 || WaitForSingleObjectEx(v6, 0, 0) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xB07,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v8);
      *((_BYTE *)Block + 72) = 0;
      wil::details::ResetEvent((wil::details *)qword_180369948, v9);
      v10 = (char *)(Block + 72);
      v11 = (wil::details **)_SetEvent_scope_exit___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_SetEvent_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_XZ(
                               &qword_180369948,
                               Block + 72);
      v24 = v11;
      v12 = (wil::details **)(Block + 32);
      if ( Block + 32 != (_WORD *)v11 )
      {
        v13 = *v11;
        v25 = *v11;
        v14 = *v12;
        if ( *v12 )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)(Block + 116));
          wil::details::SetEvent(v14, v15);
          wil::last_error_context::~last_error_context((wil::last_error_context *)(Block + 116));
          v11 = v24;
          v12 = (wil::details **)(Block + 32);
          v10 = (char *)(Block + 72);
          v13 = v25;
        }
        *v12 = v13;
        *v11 = 0;
        v5 = (char *)(Block + 68);
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_SetEvent_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v10);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v5);
LABEL_22:
    if ( !*((_BYTE *)Block + 72) )
      break;
    *(_QWORD *)v4 = 0;
    *((_QWORD *)Block + 11) = 0;
    *((_QWORD *)Block + 12) = 0;
    *((_QWORD *)Block + 13) = qword_180369948;
    *((_DWORD *)Block + 28) = 0;
    *((_QWORD *)Block + 15) = 0;
    *((_DWORD *)Block + 32) = 0;
    if ( !winrt::impl::signal_awaiter::await_ready(v4) )
    {
      Block[16] = 4;
      winrt::impl::signal_awaiter::await_suspend<std::coroutine_traits<winrt::fire_and_forget,winrt::weak_ref<winrt::Windows::Indexer::SemanticSearch::implementation::SemanticIndexMigrationManager>>::promise_type>(
        v4,
        Block);
      return;
    }
  }
  v16 = Block + 76;
  winrt::weak_ref<winrt::Windows::Indexer::SemanticSearch::implementation::SemanticIndexMigrationManager>::get(
    Block + 12,
    Block + 76);
  v17 = *((_QWORD *)Block + 19);
  if ( !v17
    || !(unsigned __int8)winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticIndexOperations<winrt::Windows::Indexer::SemanticSearch::ISemanticIndexOperations>::RequiresMigration(v17 + 24) )
  {
    goto LABEL_39;
  }
  AcquireSRWLockShared((PSRWLOCK)(v17 + 40));
  *((_QWORD *)Block + 20) = v17 + 40;
  if ( *(_BYTE *)(v17 + 64) )
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>();
    winrt::com_ptr<winrt::Windows::Indexer::SemanticSearch::implementation::SemanticIndexMigrationManager>::unconditional_release_ref(Block + 76);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_SetEvent_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Block + 32);
    goto LABEL_42;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>();
  v18 = Block + 84;
  *((_QWORD *)Block + 21) = 0;
  AcquireSRWLockExclusive((PSRWLOCK)(v17 + 40));
  *((_QWORD *)Block + 22) = v17 + 40;
  if ( *(_BYTE *)(v17 + 64) )
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(Block + 88);
    _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)(Block + 84));
    winrt::com_ptr<winrt::Windows::Indexer::SemanticSearch::implementation::SemanticIndexMigrationManager>::unconditional_release_ref(Block + 76);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_SetEvent_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Block + 32);
LABEL_42:
    winrt::Windows::Indexer::SemanticSearch::implementation::SemanticIndexMigrationManager::StartMigration_::_32_::_parameters_::__parameters_(Block + 12);
    if ( Block[17] )
      operator delete(Block);
    return;
  }
  v19 = winrt::Windows::Indexer::SemanticSearch::implementation::SemanticIndexMigrationManager::PerformMigrationAsync(
          v17,
          Block + 92);
  v20 = (_QWORD *)(v17 + 32);
  winrt::Windows::Foundation::IUnknown::operator=(v20, v19);
  if ( v18 != v20 )
  {
    if ( *v18 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(Block + 84);
    *v18 = *v20;
    winrt::Windows::Foundation::IUnknown::add_ref((winrt::Windows::Foundation::IUnknown *)(Block + 84));
  }
  _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)(Block + 92));
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(Block + 88);
  v21 = winrt::Windows::Foundation::operator co_await(Block + 100, Block + 84);
  *((_QWORD *)Block + 24) = v21;
  Block[16] = 6;
  if ( !(unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_suspend<std::coroutine_traits<winrt::fire_and_forget,inverted::SemanticDatabaseBuilder &,winrt::Windows::Indexer::SemanticSearch::ISemanticIndexOperations,enum winrt::Windows::Indexer::SemanticSearch::ModelKind>::promise_type>(
                           v21,
                           Block) )
  {
LABEL_38:
    winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_resume(*((_QWORD *)Block + 24));
    winrt::cancellable_awaiter<winrt::impl::signal_awaiter>::~cancellable_awaiter<winrt::impl::signal_awaiter>(Block + 100);
    _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)(Block + 84));
    v16 = Block + 76;
LABEL_39:
    if ( *v16 )
      winrt::com_ptr<winrt::Windows::Indexer::SemanticSearch::implementation::SemanticIndexMigrationManager>::unconditional_release_ref(v16);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_SetEvent_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Block + 32);
    goto LABEL_42;
  }
}

```

## disassembly

```asm
0x180288320  mov     rax, rsp
0x180288323  mov     [rax+8], rcx
0x180288327  push    rbx
0x180288328  push    rsi
0x180288329  push    rdi
0x18028832a  push    r12
0x18028832c  push    r13
0x18028832e  push    r14
0x180288330  push    r15
0x180288332  sub     rsp, 70h
0x180288336  mov     rdi, rcx
0x180288339  mov     r13, rcx
0x18028833c  mov     [rsp+0A8h+arg_8], rcx
0x180288344  movzx   eax, word ptr [rdi+20h]
0x180288348  mov     word ptr [rsp+0A8h+var_88], ax; int
0x18028834d  mov     r12d, 1
0x180288353  add     ax, r12w
0x180288357  cmp     ax, 8; switch 9 cases
0x18028835b  ja      def_180288376; jumptable 0000000180288376 default case, cases 1,2
0x180288361  movsx   rax, ax
0x180288365  lea     rdx, __ImageBase
0x18028836c  mov     ecx, ds:(jpt_180288376 - 180000000h)[rdx+rax*4]
0x180288373  add     rcx, rdx
0x180288376  jmp     rcx; switch jump
0x180288378  xor     esi, esi; jumptable 0000000180288376 case 4
0x18028837a  jmp     loc_180288835
0x18028837f  call    ?SemanticIndexRebuildMigration@SemanticSearchTelemetry@@SAXXZ; jumptable 0000000180288376 case 3
0x180288384  mov     rcx, gs:58h
0x18028838d  mov     eax, cs:_tls_index
0x180288393  mov     edx, 10h
0x180288398  mov     rax, [rcx+rax*8]
0x18028839c  mov     eax, [rdx+rax]
0x18028839f  cmp     cs:dword_180369940, eax
0x1802883a5  jle     short loc_1802883EC
0x1802883a7  lea     rcx, dword_180369940
0x1802883ae  call    _Init_thread_header
0x1802883b3  cmp     cs:dword_180369940, 0FFFFFFFFh
0x1802883ba  jnz     short loc_1802883EC
0x1802883bc  xor     r9d, r9d; lpName
0x1802883bf  mov     r8d, r12d; bInitialState
0x1802883c2  mov     edx, r12d; bManualReset
0x1802883c5  xor     ecx, ecx; lpEventAttributes
0x1802883c7  call    cs:__imp_CreateEventW
0x1802883cd  mov     cs:qword_180369948, rax
0x1802883d4  lea     rcx, _winrt__Windows__Indexer__SemanticSearch__implementation__SemanticIndexMigrationManager__StartMigration____3____dynamic_atexit_destructor_for__sequentialMigrationEvent__; void (__cdecl *)()
0x1802883db  call    atexit
0x1802883e0  lea     rcx, dword_180369940
0x1802883e7  call    _Init_thread_footer
0x1802883ec  lea     r15, stru_1803690A0
0x1802883f3  mov     rcx, r15; SRWLock
0x1802883f6  call    cs:__imp_AcquireSRWLockShared
0x1802883fc  lea     rcx, [rdi+28h]
0x180288400  mov     [rcx], r15
0x180288403  xor     esi, esi
0x180288405  cmp     cs:qword_180369948, rsi
0x18028840c  setnz   bl
0x18028840f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180288414  test    bl, bl
0x180288416  jnz     short loc_18028848F
0x180288418  mov     rcx, r15; SRWLock
0x18028841b  call    cs:__imp_AcquireSRWLockExclusive
0x180288421  mov     [rdi+30h], r15
0x180288425  cmp     cs:qword_180369948, rsi
0x18028842c  jnz     short loc_180288486
0x18028842e  lea     rbx, [rdi+38h]
0x180288432  xor     r9d, r9d; lpName
0x180288435  mov     r8d, r12d; bInitialState
0x180288438  mov     edx, r12d; bManualReset
0x18028843b  xor     ecx, ecx; lpEventAttributes
0x18028843d  call    cs:__imp_CreateEventW
0x180288443  mov     [rbx], rax
0x180288446  mov     rdx, rbx
0x180288449  lea     rcx, qword_180369948
0x180288450  call    ??4?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x180288455  mov     rcx, rbx
0x180288458  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18028845d  mov     rcx, [rsp+0A8h]; this
0x180288465  cmp     cs:qword_180369948, rsi
0x18028846c  jnz     short loc_180288486
0x18028846e  mov     r9d, 80004005h; char *
0x180288474  lea     r8, aOnecoreuapBase_273; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18028847b  mov     edx, 0A5h; void *
0x180288480  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180288486  lea     rcx, [rdi+30h]
0x18028848a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18028848f  mov     [rdi+40h], rsi
0x180288493  mov     [rdi+48h], r12b
0x180288497  lea     r14, [rdi+50h]
0x18028849b  jmp     loc_1802885ED
0x1802884a0  lea     rcx, [rdi+50h]; jumptable 0000000180288376 case 6
0x1802884a4  call    ??1signal_awaiter@impl@winrt@@QEAA@XZ; winrt::impl::signal_awaiter::~signal_awaiter(void)
0x1802884a9  nop
0x1802884aa  lea     rcx, [rdi+40h]
0x1802884ae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?SetEvent@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1802884b3  nop
0x1802884b4  xor     esi, esi
0x1802884b6  jmp     loc_180288835
0x1802884bb  lea     r15, stru_1803690A0; jumptable 0000000180288376 case 5
0x1802884c2  xor     esi, esi
0x1802884c4  lea     r14, [rdi+50h]
0x1802884c8  mov     rcx, r14; this
0x1802884cb  call    ?await_resume@signal_awaiter@impl@winrt@@QEAA_NXZ; winrt::impl::signal_awaiter::await_resume(void)
0x1802884d0  nop
0x1802884d1  mov     rcx, r14; this
0x1802884d4  call    ??1signal_awaiter@impl@winrt@@QEAA@XZ; winrt::impl::signal_awaiter::~signal_awaiter(void)
0x1802884d9  mov     rcx, r15; SRWLock
0x1802884dc  call    cs:__imp_AcquireSRWLockExclusive
0x1802884e2  lea     r12, [rdi+88h]
0x1802884e9  mov     [r12], r15
0x1802884ed  mov     rbx, cs:qword_180369948
0x1802884f4  xor     r8d, r8d; bAlertable
0x1802884f7  xor     edx, edx; dwMilliseconds
0x1802884f9  mov     rcx, rbx; hHandle
0x1802884fc  call    cs:__imp_WaitForSingleObjectEx
0x180288502  cmp     eax, 102h
0x180288507  jz      loc_1802885E5
0x18028850d  test    eax, eax
0x18028850f  jnz     loc_1802885CB
0x180288515  xor     r8d, r8d; bAlertable
0x180288518  xor     edx, edx; dwMilliseconds
0x18028851a  mov     rcx, rbx; hHandle
0x18028851d  call    cs:__imp_WaitForSingleObjectEx
0x180288523  test    eax, eax
0x180288525  jnz     loc_1802885CB
0x18028852b  mov     [rdi+48h], sil
0x18028852f  mov     rcx, cs:qword_180369948; this
0x180288536  call    ?ResetEvent@details@wil@@YAXPEAX@Z; wil::details::ResetEvent(void *)
0x18028853b  lea     rbx, [rdi+90h]
0x180288542  mov     rdx, rbx
0x180288545  lea     rcx, qword_180369948
0x18028854c  call    ?SetEvent_scope_exit@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?SetEvent@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@XZ
0x180288551  mov     [rsp+0A8h+arg_10], rax
0x180288559  lea     rcx, [rdi+40h]
0x18028855d  cmp     rcx, rax
0x180288560  jz      short loc_1802885C1
0x180288562  mov     rdx, [rax]
0x180288565  mov     [rsp+0A8h+arg_18], rdx
0x18028856d  mov     r12, [rcx]
0x180288570  mov     [rsp+0A8h+var_80], r12
0x180288575  test    r12, r12
0x180288578  jz      short loc_1802885B4
0x18028857a  lea     rbx, [rdi+0E8h]
0x180288581  mov     rcx, rbx; this
0x180288584  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180288589  mov     rcx, r12; this
0x18028858c  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x180288591  mov     rcx, rbx; this
0x180288594  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180288599  mov     rax, [rsp+0A8h+arg_10]
0x1802885a1  lea     rcx, [rdi+40h]
0x1802885a5  lea     rbx, [rdi+90h]
0x1802885ac  mov     rdx, [rsp+0A8h+arg_18]
0x1802885b4  mov     [rcx], rdx
0x1802885b7  mov     [rax], rsi
0x1802885ba  lea     r12, [rdi+88h]
0x1802885c1  mov     rcx, rbx
0x1802885c4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?SetEvent@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1802885c9  jmp     short loc_1802885E5
0x1802885cb  mov     rcx, [rsp+0A8h]; this
0x1802885d3  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1802885da  mov     edx, 0B07h; void *
0x1802885df  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1802885e5  mov     rcx, r12
0x1802885e8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1802885ed  cmp     [rdi+48h], sil
0x1802885f1  jz      short loc_180288640
0x1802885f3  mov     [r14], rsi
0x1802885f6  mov     [rdi+58h], rsi
0x1802885fa  mov     [rdi+60h], rsi
0x1802885fe  mov     rax, cs:qword_180369948
0x180288605  mov     [rdi+68h], rax
0x180288609  mov     [rdi+70h], esi
0x18028860c  mov     [rdi+78h], rsi
0x180288610  mov     [rdi+80h], esi
0x180288616  mov     rcx, r14; this
0x180288619  call    ?await_ready@signal_awaiter@impl@winrt@@QEBA_NXZ; winrt::impl::signal_awaiter::await_ready(void)
0x18028861e  test    al, al
0x180288620  jnz     loc_1802884C4
0x180288626  mov     eax, 4
0x18028862b  mov     [rdi+20h], ax
0x18028862f  mov     rdx, rdi
0x180288632  mov     rcx, r14
0x180288635  call    ??$await_suspend@Upromise_type@?$coroutine_traits@Ufire_and_forget@winrt@@U?$weak_ref@USemanticIndexMigrationManager@implementation@SemanticSearch@Indexer@Windows@winrt@@@2@@std@@@signal_awaiter@impl@winrt@@QEAAXU?$coroutine_handle@Upromise_type@?$coroutine_traits@Ufire_and_forget@winrt@@U?$weak_ref@USemanticIndexMigrationManager@implementation@SemanticSearch@Indexer@Windows@winrt@@@2@@std@@@std@@@Z; winrt::impl::signal_awaiter::await_suspend<std::coroutine_traits<winrt::fire_and_forget,winrt::weak_ref<winrt::Windows::Indexer::SemanticSearch::implementation::SemanticIndexMigrationManager>>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::fire_and_forget,winrt::weak_ref<winrt::Windows::Indexer::SemanticSearch::implementation::SemanticIndexMigrationManager>>::promise_type>)
0x18028863a  nop
0x18028863b  jmp     loc_180288859
0x180288640  lea     r14, [rdi+98h]
0x180288647  lea     rcx, [rdi+18h]
0x18028864b  mov     rdx, r14
0x18028864e  call    ?get@?$weak_ref@USemanticIndexMigrationManager@implementation@SemanticSearch@Indexer@Windows@winrt@@@winrt@@QEBA@XZ; winrt::weak_ref<winrt::Windows::Indexer::SemanticSearch::implementation::SemanticIndexMigrationManager>::get(void)
0x180288653  nop
0x180288654  mov     rbx, [r14]
0x180288657  test    rbx, rbx
0x18028865a  jz      loc_1802887FE
0x180288660  mov     [rsp+0A8h+arg_10], rbx
0x180288668  lea     rcx, [rbx+18h]
0x18028866c  call    ?RequiresMigration@?$consume_Windows_Indexer_SemanticSearch_ISemanticIndexOperations@UISemanticIndexOperations@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticIndexOperations<winrt::Windows::Indexer::SemanticSearch::ISemanticIndexOperations>::RequiresMigration(void)
0x180288671  test    al, al
0x180288673  jz      loc_1802887FE
0x180288679  lea     r12, [rbx+28h]
0x18028867d  mov     rcx, r12; SRWLock
0x180288680  call    cs:__imp_AcquireSRWLockShared
0x180288686  lea     rcx, [rdi+0A0h]
0x18028868d  mov     [rcx], r12
0x180288690  cmp     [rbx+40h], sil
0x180288694  jz      short loc_1802886B4
0x180288696  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18028869b  nop
0x18028869c  mov     rcx, r14
0x18028869f  call    ?unconditional_release_ref@?$com_ptr@USemanticIndexMigrationManager@implementation@SemanticSearch@Indexer@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Indexer::SemanticSearch::implementation::SemanticIndexMigrationManager>::unconditional_release_ref(void)
0x1802886a4  nop
0x1802886a5  lea     rcx, [rdi+40h]
0x1802886a9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?SetEvent@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1802886ae  nop
0x1802886af  jmp     loc_180288835
0x1802886b4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1802886b9  lea     r15, [rdi+0A8h]
0x1802886c0  mov     [r15], rsi
0x1802886c3  mov     rcx, r12; SRWLock
0x1802886c6  call    cs:__imp_AcquireSRWLockExclusive
0x1802886cc  lea     rax, [rdi+0B0h]
0x1802886d3  mov     [rax], r12
0x1802886d6  cmp     [rbx+40h], sil
0x1802886da  jz      short loc_180288706
0x1802886dc  mov     rcx, rax
0x1802886df  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1802886e4  nop
0x1802886e5  mov     rcx, r15; this
0x1802886e8  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x1802886ed  nop
0x1802886ee  mov     rcx, r14
0x1802886f1  call    ?unconditional_release_ref@?$com_ptr@USemanticIndexMigrationManager@implementation@SemanticSearch@Indexer@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Indexer::SemanticSearch::implementation::SemanticIndexMigrationManager>::unconditional_release_ref(void)
0x1802886f6  nop
0x1802886f7  lea     rcx, [rdi+40h]
0x1802886fb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?SetEvent@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180288700  nop
0x180288701  jmp     loc_180288835
0x180288706  lea     r14, [rdi+0B8h]
0x18028870d  mov     rdx, r14
0x180288710  mov     rcx, rbx
0x180288713  call    ?PerformMigrationAsync@SemanticIndexMigrationManager@implementation@SemanticSearch@Indexer@Windows@winrt@@AEAA?AUIAsyncAction@Foundation@56@XZ; winrt::Windows::Indexer::SemanticSearch::implementation::SemanticIndexMigrationManager::PerformMigrationAsync(void)
0x180288718  add     rbx, 20h ; ' '
0x18028871c  mov     rdx, rax
0x18028871f  mov     rcx, rbx
0x180288722  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x180288727  cmp     r15, rbx
0x18028872a  jz      short loc_180288752
0x18028872c  mov     rax, [r15]
0x18028872f  mov     [rsp+0A8h+arg_18], rax
0x180288737  test    rax, rax
0x18028873a  jz      short loc_180288744
0x18028873c  mov     rcx, r15
0x18028873f  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180288744  mov     rax, [rbx]
0x180288747  mov     [r15], rax
0x18028874a  mov     rcx, r15; this
0x18028874d  call    ?add_ref@IUnknown@Foundation@Windows@winrt@@AEBAXXZ; winrt::Windows::Foundation::IUnknown::add_ref(void)
0x180288752  mov     rcx, r14; this
0x180288755  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x18028875a  nop
0x18028875b  lea     rcx, [rdi+0B0h]
0x180288762  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180288767  lea     rcx, [rdi+0C8h]
0x18028876e  mov     rdx, r15
0x180288771  call    ??__LFoundation@Windows@winrt@@YA?AU?$await_adapter@UIAsyncAction@Foundation@Windows@winrt@@$00@impl@2@AEBUIAsyncAction@012@@Z; winrt::Windows::Foundation::operator co_await(winrt::Windows::Foundation::IAsyncAction const &)
0x180288776  mov     [rdi+0C0h], rax
0x18028877d  mov     ecx, 6
0x180288782  mov     [rdi+20h], cx
0x180288786  mov     rdx, rdi
0x180288789  mov     rcx, rax
0x18028878c  call    ??$await_suspend@Upromise_type@?$coroutine_traits@Ufire_and_forget@winrt@@AEAVSemanticDatabaseBuilder@inverted@@UISemanticIndexOperations@SemanticSearch@Indexer@Windows@2@W4ModelKind@6782@@std@@@?$await_adapter@UIAsyncAction@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@Ufire_and_forget@winrt@@AEAVSemanticDatabaseBuilder@inverted@@UISemanticIndexOperations@SemanticSearch@Indexer@Windows@2@W4ModelKind@6782@@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_suspend<std::coroutine_traits<winrt::fire_and_forget,inverted::SemanticDatabaseBuilder &,winrt::Windows::Indexer::SemanticSearch::ISemanticIndexOperations,winrt::Windows::Indexer::SemanticSearch::ModelKind>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::fire_and_forget,inverted::SemanticDatabaseBuilder &,winrt::Windows::Indexer::SemanticSearch::ISemanticIndexOperations,winrt::Windows::Indexer::SemanticSearch::ModelKind>::promise_type>)
0x180288791  test    al, al
0x180288793  jz      short loc_1802887D1
0x180288795  jmp     loc_180288859
0x18028879a  lea     rcx, [rdi+0C8h]; jumptable 0000000180288376 case 8
0x1802887a1  call    ??1?$cancellable_awaiter@Usignal_awaiter@impl@winrt@@@winrt@@QEAA@XZ; winrt::cancellable_awaiter<winrt::impl::signal_awaiter>::~cancellable_awaiter<winrt::impl::signal_awaiter>(void)
0x1802887a6  nop
0x1802887a7  lea     rcx, [rdi+0A8h]; this
0x1802887ae  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x1802887b3  nop
0x1802887b4  lea     rcx, [rdi+98h]
0x1802887bb  call    ?unconditional_release_ref@?$com_ptr@USemanticIndexMigrationManager@implementation@SemanticSearch@Indexer@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Indexer::SemanticSearch::implementation::SemanticIndexMigrationManager>::unconditional_release_ref(void)
0x1802887c0  nop
0x1802887c1  lea     rcx, [rdi+40h]
0x1802887c5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?SetEvent@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1802887ca  nop
0x1802887cb  xor     esi, esi
0x1802887cd  jmp     short loc_180288835
0x1802887cf  xor     esi, esi; jumptable 0000000180288376 case 7
0x1802887d1  mov     rcx, [rdi+0C0h]
0x1802887d8  call    ?await_resume@?$await_adapter@UIAsyncAction@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_resume(void)
0x1802887dd  nop
0x1802887de  lea     rcx, [rdi+0C8h]
0x1802887e5  call    ??1?$cancellable_awaiter@Usignal_awaiter@impl@winrt@@@winrt@@QEAA@XZ; winrt::cancellable_awaiter<winrt::impl::signal_awaiter>::~cancellable_awaiter<winrt::impl::signal_awaiter>(void)
0x1802887ea  nop
0x1802887eb  lea     rcx, [rdi+0A8h]; this
0x1802887f2  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x1802887f7  lea     r14, [rdi+98h]
0x1802887fe  mov     rax, [r14]
0x180288801  mov     [rsp+0A8h+arg_10], rax
0x180288809  test    rax, rax
  ... truncated ...
```
