# _anonymous_namespace_::TryCreateSecondaryTileIconAsync$_ResumeCoro$1

- ea: `0x1804667c0`
- end: `0x180466d3c`
- name: `_anonymous_namespace_::TryCreateSecondaryTileIconAsync$_ResumeCoro$1`
- size: `1404`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180466d44`

## callees

- `0x18000b428`
- `0x18000b444`
- `0x180026860`
- `0x1800356e0`
- `0x1800483f4`
- `0x180071388`
- `0x180074bec`
- `0x180077910`
- `0x1800a14f8`
- `0x1800d97d0`
- `0x1800e3a88`
- `0x1800f88a0`
- `0x1801343c8`
- `0x180137f7c`
- `0x1801592dc`
- `0x180159738`
- `0x1801597c8`
- `0x18015cb00`
- `0x18015cfa0`
- `0x180287674`
- `0x18028b43c`
- `0x1803b4dc4`
- `0x18046340c`
- `0x180463a50`
- `0x180463e74`
- `0x1804667c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180466b65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180466b65`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180466afe`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180466afe`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180466b56`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180466b56`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnExpandEnvStringsW` at `0x1804669ca`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnExpandEnvStringsW` at `0x1804669ca`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectory` at `0x180466a66`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectory` at `0x180466a66`

## string_xrefs

- `0x180466aa2`: `shellcommon\undockeddevkit\libs\windowsudkinternal.ui.startscreen\tileidinternal.cpp`
- `0x180466b8d`: `shellcommon\undockeddevkit\libs\windowsudkinternal.ui.startscreen\tileidinternal.cpp`
- `0x180466c4c`: `shellcommon\undockeddevkit\libs\windowsudkinternal.ui.startscreen\tileidinternal.cpp`

## pseudocode

```c
void __fastcall anonymous_namespace_::TryCreateSecondaryTileIconAsync__ResumeCoro_1(__int64 a1)
{
  __int64 v2; // r12
  __int64 v3; // rcx
  _QWORD *v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // rax
  const WCHAR **v7; // r13
  const WCHAR *v8; // rcx
  __int64 v9; // r8
  std::filesystem::path *v10; // rax
  struct std::filesystem::path *v11; // rax
  int v12; // eax
  unsigned int v13; // ebx
  const WCHAR *v14; // rcx
  HANDLE FileW; // rbx
  const char *v16; // r9
  DWORD v17; // r15d
  const void *v18; // rax
  signed int v19; // r15d
  signed int LastError; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-148h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-148h]
  int v23; // [rsp+48h] [rbp-120h]
  int v24; // [rsp+58h] [rbp-110h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v2 = a1 + 8;
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
    case 5:
      goto LABEL_34;
    case 2:
      *(_BYTE *)(a1 + 12) = 0;
      winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::WindowsUdk::AI::MachineLearning::WisePredictor>,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::WindowsUdk::AI::MachineLearning::WisePredictor>,void>::await_transform<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::PredictionUnit::Predictor>>(
        a1 - 112,
        a1 + 12);
      *(_WORD *)v2 = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(v3, a1);
      break;
    case 4:
      tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>>((struct wil::details::IFailureCallback *)(a1 + 16));
      v4 = (_QWORD *)(a1 + 72);
      tip2::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(
        a1 + 80,
        a1 + 72);
      std::wstring::_Assign<wchar_t>(*(_QWORD *)(a1 + 80) + 272LL, *(_QWORD *)(v2 + 848), *(_QWORD *)(v2 + 856));
      tip2::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::~test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(a1 + 80);
      tip2::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(
        a1 + 88,
        a1 + 72);
      std::wstring::_Assign<wchar_t>(*(_QWORD *)(a1 + 88) + 304LL, *(_QWORD *)(a1 + 888), *(_QWORD *)(a1 + 896));
      tip2::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::~test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(a1 + 88);
      winrt::param::hstring::hstring(a1 + 96, a1 + 872);
      winrt::Windows::Security::Cryptography::CryptographicBuffer::DecodeFromBase64String((const struct winrt::param::hstring *)(a1 + 128));
      *(_OWORD *)(a1 + 136) = *(_OWORD *)(*(_QWORD *)(a1 + 72) + 152LL);
      v5 = *(_QWORD *)(a1 + 888);
      v6 = -1;
      do
        ++v6;
      while ( *(_WORD *)(v5 + 2 * v6) );
      *(_OWORD *)(a1 + 832) = *(_OWORD *)(v2 + 848);
      *(_QWORD *)(a1 + 816) = v5;
      *(_QWORD *)(a1 + 824) = v6;
      v7 = (const WCHAR **)(a1 + 152);
      anonymous_namespace_::GetPathFromMSAppDataUriForAumid(a1 + 152);
      if ( *(_QWORD *)(a1 + 168) )
      {
        if ( *(_QWORD *)(a1 + 176) <= 7u )
          v8 = (const WCHAR *)(a1 + 152);
        else
          v8 = *v7;
        PathUnExpandEnvStringsW(v8, (LPWSTR)(a1 + 192), 0x104u);
        tip2::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(
          a1 + 720,
          a1 + 72);
        v9 = -1;
        do
          ++v9;
        while ( *(_WORD *)(a1 + 192 + 2 * v9) );
        std::wstring::_Assign<wchar_t>(*(_QWORD *)(a1 + 720) + 336LL, a1 + 192, v9);
        tip2::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::~test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(a1 + 720);
        tip2::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(
          a1 + 728,
          a1 + 72);
        *(_BYTE *)(*(_QWORD *)(a1 + 728) + 369LL) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::~test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(a1 + 728);
        v10 = (std::filesystem::path *)std::filesystem::path::path(a1 + 736, a1 + 152);
        v11 = std::filesystem::path::remove_filename(v10);
        if ( *((_QWORD *)v11 + 3) > 7u )
          v11 = *(struct std::filesystem::path **)v11;
        v12 = SHCreateDirectory(0, (PCWSTR)v11);
        v13 = v12;
        if ( v12 > 0 )
          v13 = (unsigned __int16)v12 | 0x80070000;
        std::filesystem::path::~path((std::filesystem::path *)(a1 + 736));
        if ( !v13 || v13 == -2147024713 || v13 == -2147024816 )
        {
          if ( *(_QWORD *)(a1 + 176) <= 7u )
            v14 = (const WCHAR *)(a1 + 152);
          else
            v14 = *v7;
          FileW = CreateFileW(v14, 0x40000000u, 0, 0, 2u, 0x80u, 0);
          *(_QWORD *)(a1 + 768) = FileW;
          if ( FileW == (HANDLE)-1LL )
          {
            wil::details::in1diag3::_Log_GetLastError(
              retaddr,
              (void *)0xAF,
              (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudkinternal.ui.startscreen\\tileidinternal.cpp",
              v16);
          }
          else
          {
            *(_DWORD *)(a1 + 776) = 0;
            v17 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Internal::Text::Core::CoreTextKeyFilter>,winrt::Windows::UI::Internal::Text::Core::CoreTextKeyFilter>::Size(a1 + 128);
            v18 = (const void *)winrt::impl::consume_Windows_Storage_Streams_IBuffer<winrt::Windows::Storage::Streams::IBuffer>::data(a1 + 128);
            if ( WriteFile(FileW, v18, v17, (LPDWORD)(a1 + 776), 0) )
            {
              v19 = 0;
            }
            else
            {
              LastError = GetLastError();
              v19 = LastError;
              if ( LastError > 0 )
                v19 = (unsigned __int16)LastError | 0x80070000;
            }
            if ( v19 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0xA4,
                (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudkinternal.ui.startscreen\\tileidinternal.cpp",
                (const char *)(unsigned int)v19,
                dwCreationDispositiona);
            v23 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Internal::Text::Core::CoreTextKeyFilter>,winrt::Windows::UI::Internal::Text::Core::CoreTextKeyFilter>::Size(a1 + 128);
            tip2::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(
              a1 + 784,
              a1 + 72);
            *(_DWORD *)(*(_QWORD *)(a1 + 784) + 372LL) = v23;
            tip2::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::~test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(a1 + 784);
            v24 = *(_DWORD *)(a1 + 776);
            tip2::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(
              a1 + 792,
              a1 + 72);
            *(_DWORD *)(*(_QWORD *)(a1 + 792) + 376LL) = v24;
            tip2::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::~test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(a1 + 792);
            v4 = (_QWORD *)(a1 + 72);
            if ( v19 >= 0 )
            {
              tip2::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(
                a1 + 800,
                a1 + 72);
              *(_BYTE *)(*(_QWORD *)(a1 + 800) + 369LL) = 0;
              tip2::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::~test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(a1 + 800);
            }
          }
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(a1 + 768);
        }
        else
        {
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0xB4,
            (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudkinternal.ui.startscreen\\tileidinternal.cpp",
            (const char *)v13,
            dwCreationDisposition);
        }
      }
      std::filesystem::path::~path((std::filesystem::path *)(a1 + 152));
      tip2::details::shared_data<1,0,0>::complete_without_lock(*v4 + 8LL);
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)(a1 + 128));
      tip2::test_watcher<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::~test_watcher<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(a1 + 16);
      *(_QWORD *)(a1 + 808) = a1 - 112;
      *(_WORD *)v2 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::WindowsUdk::UI::MenuItem>>,winrt::Windows::Storage::IStorageItem,winrt::Windows::System::User,winrt::WindowsUdk::UI::MenuItemGetOptions>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::WindowsUdk::UI::MenuItem>>,void>::final_suspend_awaiter::await_suspend() )
      {
LABEL_34:
        winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,winrt::WindowsUdk::UI::Input::Text::implementation::InputMethodConversionIndicator *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,void>::~promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,winrt::WindowsUdk::UI::Input::Text::implementation::InputMethodConversionIndicator *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,void>(a1 - 112);
        if ( *(_WORD *)(a1 + 10) )
          operator delete((void *)(a1 - 112), (const struct std::nothrow_t *)0x400);
      }
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x1804667c0  mov     r11, rsp
0x1804667c3  mov     [r11+10h], rbx
0x1804667c7  mov     [r11+18h], rsi
0x1804667cb  mov     [r11+8], rcx
0x1804667cf  push    rdi
0x1804667d0  push    r12
0x1804667d2  push    r13
0x1804667d4  push    r14
0x1804667d6  push    r15
0x1804667d8  sub     rsp, 140h
0x1804667df  mov     rax, cs:__security_cookie
0x1804667e6  xor     rax, rsp
0x1804667e9  mov     [rsp+168h+var_30], rax
0x1804667f1  mov     rsi, rcx
0x1804667f4  mov     [rsp+168h+var_118], rcx
0x1804667f9  lea     r12, [rsi+8]
0x1804667fd  mov     [rsp+168h+var_108], r12
0x180466802  movzx   eax, word ptr [r12]
0x180466807  mov     [rsp+168h+var_128], ax
0x18046680c  inc     ax; switch 7 cases
0x18046680f  cmp     ax, 6
0x180466813  ja      def_18046682E; jumptable 000000018046682E default case, case 0
0x180466819  movsx   rax, ax
0x18046681d  lea     rdx, __ImageBase
0x180466824  mov     ecx, ds:(jpt_18046682E - 180000000h)[rdx+rax*4]
0x18046682b  add     rcx, rdx
0x18046682e  jmp     rcx; switch jump
0x180466830  xor     r14d, r14d; jumptable 000000018046682E case 3
0x180466833  jmp     loc_180466CD1
0x180466838  lea     rdx, [rsi+0Ch]; jumptable 000000018046682E case 2
0x18046683c  xor     r14d, r14d
0x18046683f  mov     [rdx], r14b
0x180466842  lea     rcx, [rsi-70h]
0x180466846  call    ??$await_transform@U?$IAsyncOperation@UPredictor@PredictionUnit@Internal@Windows@winrt@@@Foundation@Windows@winrt@@@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UWisePredictor@MachineLearning@AI@WindowsUdk@winrt@@@Foundation@Windows@winrt@@Uhstring@4@U54@@experimental@std@@U?$IAsyncOperation@UWisePredictor@MachineLearning@AI@WindowsUdk@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEAA$$QEAU?$IAsyncOperation@UPredictor@PredictionUnit@Internal@Windows@winrt@@@Foundation@Windows@2@$$QEAU3452@@Z; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::WindowsUdk::AI::MachineLearning::WisePredictor>,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::WindowsUdk::AI::MachineLearning::WisePredictor>,void>::await_transform<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::PredictionUnit::Predictor>>(winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::PredictionUnit::Predictor> &&)
0x18046684b  lea     eax, [r14+4]
0x18046684f  mov     [r12], ax
0x180466854  mov     rdx, rsi
0x180466857  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@experimental@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::experimental::coroutine_handle<void>)
0x18046685c  jmp     loc_180466CF2
0x180466861  xor     r14d, r14d; jumptable 000000018046682E case 5
0x180466864  jmp     loc_180466CD1
0x180466869  lea     rcx, [rsi+10h]; jumptable 000000018046682E case 4
0x18046686d  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_SecondaryTileLogoCreationTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x180466872  nop
0x180466873  lea     rdi, [rsi+48h]
0x180466877  lea     rbx, [rsi+50h]
0x18046687b  mov     rdx, rdi
0x18046687e  mov     rcx, rbx
0x180466881  call    ??0?$test_data_control@V?$merged_data@U_tip_SecondaryTileLogoCreationTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_SecondaryTileLogoCreationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>,wil::err_returncode_policy> const &)
0x180466886  nop
0x180466887  mov     rcx, [rbx]
0x18046688a  mov     [rsp+168h+var_100], rcx
0x18046688f  add     rcx, 110h
0x180466896  mov     r8, [r12+358h]
0x18046689e  mov     rdx, [r12+350h]
0x1804668a6  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1804668ab  nop
0x1804668ac  mov     rcx, rbx
0x1804668af  call    ??1?$test_data_control@V?$merged_data@U_tip_SecondaryTileLogoCreationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::~test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(void)
0x1804668b4  lea     rbx, [rsi+58h]
0x1804668b8  mov     rdx, rdi
0x1804668bb  mov     rcx, rbx
0x1804668be  call    ??0?$test_data_control@V?$merged_data@U_tip_SecondaryTileLogoCreationTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_SecondaryTileLogoCreationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>,wil::err_returncode_policy> const &)
0x1804668c3  nop
0x1804668c4  mov     rcx, [rbx]
0x1804668c7  mov     [rsp+168h+var_F8], rcx
0x1804668cc  add     rcx, 130h
0x1804668d3  mov     r8, [rsi+380h]
0x1804668da  mov     rdx, [rsi+378h]
0x1804668e1  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1804668e6  nop
0x1804668e7  mov     rcx, rbx
0x1804668ea  call    ??1?$test_data_control@V?$merged_data@U_tip_SecondaryTileLogoCreationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::~test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(void)
0x1804668ef  lea     rdx, [rsi+368h]
0x1804668f6  lea     rcx, [rsi+60h]
0x1804668fa  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::param::hstring::hstring(std::wstring_view const &)
0x1804668ff  lea     rcx, [rsi+80h]; struct winrt::param::hstring *
0x180466906  lea     rdx, [rsi+60h]
0x18046690a  call    ?DecodeFromBase64String@CryptographicBuffer@Cryptography@Security@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Security::Cryptography::CryptographicBuffer::DecodeFromBase64String(winrt::param::hstring const &)
0x18046690f  nop
0x180466910  mov     rax, [rdi]
0x180466913  mov     [rsp+168h+var_90], rax
0x18046691b  lea     r9, [rsi+88h]
0x180466922  movups  xmm0, xmmword ptr [rax+98h]
0x180466929  movdqu  xmmword ptr [r9], xmm0
0x18046692e  mov     rcx, [rsi+378h]
0x180466935  or      rax, 0FFFFFFFFFFFFFFFFh
0x180466939  xor     r14d, r14d
0x18046693c  inc     rax
0x18046693f  cmp     [rcx+rax*2], r14w
0x180466944  jnz     short loc_18046693C
0x180466946  lea     r8, [rsi+340h]
0x18046694d  movups  xmm0, xmmword ptr [r12+350h]
0x180466956  movdqu  xmmword ptr [r8], xmm0
0x18046695b  lea     rdx, [rsi+330h]
0x180466962  mov     [rdx], rcx
0x180466965  mov     [rsi+338h], rax
0x18046696c  lea     r13, [rsi+98h]
0x180466973  mov     rcx, r13
0x180466976  call    _anonymous_namespace___GetPathFromMSAppDataUriForAumid
0x18046697b  nop
0x18046697c  mov     rax, [rsi+0A8h]
0x180466983  mov     [rsp+168h+var_78], rax
0x18046698b  test    rax, rax
0x18046698e  jz      loc_180466C6B
0x180466994  mov     rax, [rsi+0B0h]
0x18046699b  mov     [rsp+168h+var_70], rax
0x1804669a3  cmp     rax, 7
0x1804669a7  jbe     short loc_1804669B7
0x1804669a9  mov     rcx, [r13+0]
0x1804669ad  mov     [rsp+168h+var_88], rcx
0x1804669b5  jmp     short loc_1804669BA
0x1804669b7  mov     rcx, r13; pszPath
0x1804669ba  lea     rbx, [rsi+0C0h]
0x1804669c1  mov     r8d, 104h; cchBuf
0x1804669c7  mov     rdx, rbx; pszBuf
0x1804669ca  call    cs:__imp_PathUnExpandEnvStringsW
0x1804669d0  lea     r15, [rsi+2D0h]
0x1804669d7  mov     rdx, rdi
0x1804669da  mov     rcx, r15
0x1804669dd  call    ??0?$test_data_control@V?$merged_data@U_tip_SecondaryTileLogoCreationTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_SecondaryTileLogoCreationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>,wil::err_returncode_policy> const &)
0x1804669e2  nop
0x1804669e3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1804669e7  inc     r8
0x1804669ea  cmp     [rbx+r8*2], r14w
0x1804669ef  jnz     short loc_1804669E7
0x1804669f1  mov     rcx, [r15]
0x1804669f4  mov     [rsp+168h+var_F0], rcx
0x1804669f9  add     rcx, 150h
0x180466a00  mov     rdx, rbx
0x180466a03  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180466a08  nop
0x180466a09  mov     rcx, r15
0x180466a0c  call    ??1?$test_data_control@V?$merged_data@U_tip_SecondaryTileLogoCreationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::~test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(void)
0x180466a11  lea     rbx, [rsi+2D8h]
0x180466a18  mov     rdx, rdi
0x180466a1b  mov     rcx, rbx
0x180466a1e  call    ??0?$test_data_control@V?$merged_data@U_tip_SecondaryTileLogoCreationTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_SecondaryTileLogoCreationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>,wil::err_returncode_policy> const &)
0x180466a23  mov     rax, [rbx]
0x180466a26  mov     [rsp+168h+var_E8], rax
0x180466a2e  mov     byte ptr [rax+171h], 1
0x180466a35  mov     rcx, rbx
0x180466a38  call    ??1?$test_data_control@V?$merged_data@U_tip_SecondaryTileLogoCreationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::~test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(void)
0x180466a3d  lea     r15, [rsi+2E0h]
0x180466a44  mov     rdx, r13
0x180466a47  mov     rcx, r15
0x180466a4a  call    ??$?0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0A@@path@filesystem@std@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@W4format@012@@Z; std::filesystem::path::path(std::wstring const &,std::filesystem::path::format)
0x180466a4f  mov     rcx, rax; this
0x180466a52  call    ?remove_filename@path@filesystem@std@@QEAAAEAV123@XZ; std::filesystem::path::remove_filename(void)
0x180466a57  cmp     qword ptr [rax+18h], 7
0x180466a5c  jbe     short loc_180466A61
0x180466a5e  mov     rax, [rax]
0x180466a61  mov     rdx, rax; pszPath
0x180466a64  xor     ecx, ecx; hwnd
0x180466a66  call    cs:__imp_SHCreateDirectory
0x180466a6c  mov     ebx, eax
0x180466a6e  test    eax, eax
0x180466a70  jle     short loc_180466A7B
0x180466a72  movzx   ebx, ax
0x180466a75  or      ebx, 80070000h
0x180466a7b  mov     rcx, r15; this
0x180466a7e  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x180466a83  test    ebx, ebx
0x180466a85  jz      short loc_180466AB8
0x180466a87  cmp     ebx, 800700B7h
0x180466a8d  jz      short loc_180466AB8
0x180466a8f  cmp     ebx, 80070050h
0x180466a95  jz      short loc_180466AB8
0x180466a97  mov     rcx, [rsp+168h]; this
0x180466a9f  mov     r9d, ebx; char *
0x180466aa2  lea     r8, aShellcommonUnd_69; "shellcommon\\undockeddevkit\\libs\\wind"...
0x180466aa9  mov     edx, 0B4h; void *
0x180466aae  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180466ab3  jmp     loc_180466C6B
0x180466ab8  mov     rax, [rsi+0B0h]
0x180466abf  mov     [rsp+168h+var_70], rax
0x180466ac7  cmp     rax, 7
0x180466acb  jbe     short loc_180466ADB
0x180466acd  mov     rcx, [r13+0]
0x180466ad1  mov     [rsp+168h+var_88], rcx
0x180466ad9  jmp     short loc_180466ADE
0x180466adb  mov     rcx, r13; lpFileName
0x180466ade  mov     [rsp+168h+hTemplateFile], r14; hTemplateFile
0x180466ae3  mov     [rsp+168h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180466aeb  mov     [rsp+168h+dwCreationDisposition], 2; dwCreationDisposition
0x180466af3  xor     r9d, r9d; lpSecurityAttributes
0x180466af6  xor     r8d, r8d; dwShareMode
0x180466af9  mov     edx, 40000000h; dwDesiredAccess
0x180466afe  call    cs:__imp_CreateFileW
0x180466b04  mov     rbx, rax
0x180466b07  mov     [rsi+300h], rax
0x180466b0e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180466b12  jz      loc_180466C44
0x180466b18  lea     rdi, [rsi+308h]
0x180466b1f  mov     [rdi], r14d
0x180466b22  lea     rcx, [rsi+80h]
0x180466b29  call    ?Size@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@UCoreTextKeyFilter@Core@Text@Internal@UI@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UCoreTextKeyFilter@Core@Text@Internal@UI@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Internal::Text::Core::CoreTextKeyFilter>,winrt::Windows::UI::Internal::Text::Core::CoreTextKeyFilter>::Size(void)
0x180466b2e  mov     r15d, eax
0x180466b31  lea     rcx, [rsi+80h]
0x180466b38  call    ?data@?$consume_Windows_Storage_Streams_IBuffer@UIBuffer@Streams@Storage@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Storage_Streams_IBuffer<winrt::Windows::Storage::Streams::IBuffer>::data(void)
0x180466b3d  mov     [rsp+168h+var_E0], rbx
0x180466b45  mov     qword ptr [rsp+168h+dwCreationDisposition], r14; int
0x180466b4a  mov     r9, rdi; lpNumberOfBytesWritten
0x180466b4d  mov     r8d, r15d; nNumberOfBytesToWrite
0x180466b50  mov     rdx, rax; lpBuffer
0x180466b53  mov     rcx, rbx; hFile
0x180466b56  call    cs:__imp_WriteFile
0x180466b5c  test    eax, eax
0x180466b5e  jz      short loc_180466B65
0x180466b60  mov     r15d, r14d
0x180466b63  jmp     short loc_180466B7D
0x180466b65  call    cs:__imp_GetLastError
0x180466b6b  mov     r15d, eax
0x180466b6e  test    eax, eax
0x180466b70  jle     short loc_180466B7D
0x180466b72  movzx   r15d, ax
0x180466b76  or      r15d, 80070000h
0x180466b7d  mov     rcx, [rsp+168h]; this
0x180466b85  test    r15d, r15d
0x180466b88  jns     short loc_180466B9E
0x180466b8a  mov     r9d, r15d; char *
0x180466b8d  lea     r8, aShellcommonUnd_69; "shellcommon\\undockeddevkit\\libs\\wind"...
0x180466b94  mov     edx, 0A4h; void *
0x180466b99  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180466b9e  lea     rcx, [rsi+80h]
0x180466ba5  call    ?Size@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@UCoreTextKeyFilter@Core@Text@Internal@UI@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UCoreTextKeyFilter@Core@Text@Internal@UI@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Internal::Text::Core::CoreTextKeyFilter>,winrt::Windows::UI::Internal::Text::Core::CoreTextKeyFilter>::Size(void)
0x180466baa  mov     dword ptr [rsp+168h+var_120], eax
0x180466bae  lea     rbx, [rsi+310h]
0x180466bb5  lea     rdx, [rsi+48h]
0x180466bb9  mov     rcx, rbx
0x180466bbc  call    ??0?$test_data_control@V?$merged_data@U_tip_SecondaryTileLogoCreationTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_SecondaryTileLogoCreationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>,wil::err_returncode_policy> const &)
0x180466bc1  mov     rcx, [rbx]
0x180466bc4  mov     [rsp+168h+var_D8], rcx
0x180466bcc  mov     eax, dword ptr [rsp+168h+var_120]
0x180466bd0  mov     [rcx+174h], eax
0x180466bd6  mov     rcx, rbx
0x180466bd9  call    ??1?$test_data_control@V?$merged_data@U_tip_SecondaryTileLogoCreationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::~test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(void)
0x180466bde  mov     edi, [rdi]
0x180466be0  mov     [rsp+168h+var_110], edi
0x180466be4  lea     rbx, [rsi+318h]
0x180466beb  lea     rdx, [rsi+48h]
0x180466bef  mov     rcx, rbx
0x180466bf2  call    ??0?$test_data_control@V?$merged_data@U_tip_SecondaryTileLogoCreationTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_SecondaryTileLogoCreationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>,wil::err_returncode_policy> const &)
0x180466bf7  mov     rax, [rbx]
0x180466bfa  mov     [rsp+168h+var_120], rax
0x180466bff  mov     [rax+178h], edi
0x180466c05  mov     rcx, rbx
0x180466c08  call    ??1?$test_data_control@V?$merged_data@U_tip_SecondaryTileLogoCreationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::~test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(void)
0x180466c0d  lea     rdi, [rsi+48h]
0x180466c11  test    r15d, r15d
0x180466c14  js      short loc_180466C5E
0x180466c16  lea     rbx, [rsi+320h]
0x180466c1d  mov     rdx, rdi
0x180466c20  mov     rcx, rbx
0x180466c23  call    ??0?$test_data_control@V?$merged_data@U_tip_SecondaryTileLogoCreationTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_SecondaryTileLogoCreationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>,wil::err_returncode_policy> const &)
0x180466c28  mov     rax, [rbx]
0x180466c2b  mov     [rsp+168h+var_D0], rax
0x180466c33  mov     [rax+171h], r14b
0x180466c3a  mov     rcx, rbx
0x180466c3d  call    ??1?$test_data_control@V?$merged_data@U_tip_SecondaryTileLogoCreationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::~test_data_control<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(void)
0x180466c42  jmp     short loc_180466C5E
0x180466c44  mov     rcx, [rsp+168h]; this
0x180466c4c  lea     r8, aShellcommonUnd_69; "shellcommon\\undockeddevkit\\libs\\wind"...
0x180466c53  mov     edx, 0AFh; void *
0x180466c58  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180466c5d  nop
0x180466c5e  lea     rcx, [rsi+300h]
0x180466c65  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180466c6a  nop
0x180466c6b  mov     rcx, r13; this
0x180466c6e  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x180466c73  mov     rcx, [rdi]
0x180466c76  mov     [rsp+168h+var_90], rcx
0x180466c7e  add     rcx, 8
0x180466c82  call    ?complete_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::complete_without_lock(void)
0x180466c87  nop
0x180466c88  lea     rcx, [rsi+80h]; this
0x180466c8f  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x180466c94  nop
0x180466c95  lea     rcx, [rsi+10h]
0x180466c99  call    ??1?$test_watcher@V?$merged_data@U_tip_SecondaryTileLogoCreationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>::~test_watcher<tip2::details::merged_data<_tip_SecondaryTileLogoCreationTest,_tip_SecondaryTileLogoCreationTest>>(void)
0x180466c9e  nop
0x180466c9f  jmp     short loc_180466CAE
0x180466ca1  xor     r14d, r14d
0x180466ca4  mov     r12, [rsp+168h+var_108]
0x180466ca9  mov     rsi, [rsp+168h+var_118]
0x180466cae  lea     rcx, [rsi+328h]
0x180466cb5  lea     rax, [rsi-70h]
0x180466cb9  mov     [rcx], rax
0x180466cbc  xor     eax, eax
0x180466cbe  mov     [r12], ax
0x180466cc3  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@U?$IVectorView@UMenuItem@UI@WindowsUdk@winrt@@@Collections@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@UIStorageItem@Storage@34@UUser@System@34@UMenuItemGetOptions@UI@WindowsUdk@4@@experimental@std@@U?$IAsyncOperation@U?$IVectorView@UMenuItem@UI@WindowsUdk@winrt@@@Collections@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@experimental@std@@@Z; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::WindowsUdk::UI::MenuItem>>,winrt::Windows::Storage::IStorageItem,winrt::Windows::System::User,winrt::WindowsUdk::UI::MenuItemGetOptions>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::WindowsUdk::UI::MenuItem>>,void>::final_suspend_awaiter::await_suspend(std::experimental::coroutine_handle<void>)
0x180466cc8  test    al, al
0x180466cca  jz      short loc_180466CD1
0x180466ccc  jmp     short loc_180466CF2
0x180466cce  xor     r14d, r14d; jumptable 000000018046682E cases -1,1
0x180466cd1  lea     rcx, [rsi-70h]
0x180466cd5  call    ??1?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@USoftwareBitmap@Imaging@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUInputMethodConversionIndicator@implementation@Text@Input@UI@WindowsUdk@4@@experimental@std@@U?$IAsyncOperation@USoftwareBitmap@Imaging@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@UEAA@XZ; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,winrt::WindowsUdk::UI::Input::Text::implementation::InputMethodConversionIndicator *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,void>::~promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,winrt::WindowsUdk::UI::Input::Text::implementation::InputMethodConversionIndicator *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,void>(void)
0x180466cda  cmp     [rsi+0Ah], r14w
0x180466cdf  jz      short loc_180466CF2
  ... truncated ...
```
