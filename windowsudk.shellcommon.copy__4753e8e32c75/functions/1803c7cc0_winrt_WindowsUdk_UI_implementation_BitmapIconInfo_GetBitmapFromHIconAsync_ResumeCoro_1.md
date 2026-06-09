# winrt::WindowsUdk::UI::implementation::BitmapIconInfo::GetBitmapFromHIconAsync$_ResumeCoro$1

- ea: `0x1803c7cc0`
- end: `0x1803c81c4`
- name: `winrt::WindowsUdk::UI::implementation::BitmapIconInfo::GetBitmapFromHIconAsync$_ResumeCoro$1`
- size: `1284`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1803c81cc`

## callees

- `0x18000b428`
- `0x180011f98`
- `0x18002a030`
- `0x18002e634`
- `0x180073410`
- `0x180081e44`
- `0x1800a0278`
- `0x1800d6d38`
- `0x1800dca48`
- `0x1800dff00`
- `0x1800e488c`
- `0x1800eba80`
- `0x1800f4704`
- `0x1800f4760`
- `0x18015cfa0`
- `0x18015d898`
- `0x1802bf744`
- `0x1802ef400`
- `0x18032bcac`
- `0x18032f360`
- `0x1803c785c`
- `0x1803c7894`
- `0x1803c7cc0`
- `0x1804a2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1803c7d46`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1803c7d46`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOverStream` at `0x1803c7ea2`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOverStream` at `0x1803c7ea2`

## string_xrefs

- `0x1803c7df0`: `OneCore\Internal\Sdk\Inc\wil\opensource\wil\result_macros.h`
- `0x1803c7d5b`: `shellcommon\undockeddevkit\libs\windowsudk.ui\bitmapiconinfo.cpp`
- `0x1803c7da7`: `shellcommon\undockeddevkit\libs\windowsudk.ui\bitmapiconinfo.cpp`
- `0x1803c7e17`: `shellcommon\undockeddevkit\libs\windowsudk.ui\bitmapiconinfo.cpp`
- `0x1803c7e6d`: `shellcommon\undockeddevkit\libs\windowsudk.ui\bitmapiconinfo.cpp`
- `0x1803c7eb7`: `shellcommon\undockeddevkit\libs\windowsudk.ui\bitmapiconinfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void __fastcall winrt::WindowsUdk::UI::implementation::BitmapIconInfo::GetBitmapFromHIconAsync__ResumeCoro_1(
        __int64 a1)
{
  _WORD *v2; // rsi
  _QWORD *v3; // r14
  HRESULT Instance; // eax
  int v5; // eax
  int v6; // eax
  int StreamOfWICBitmapSourceWithOptions; // eax
  struct IUnknown *v8; // rdx
  void **v9; // rax
  int RandomAccessStreamOverStream; // eax
  __int64 Async; // rax
  const struct winrt::impl::slim_source_location *v12; // rax
  enum AsyncStatus v13; // edx
  __int64 SoftwareBitmapAsync; // rax
  const struct winrt::impl::slim_source_location *v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // r14
  int ppv; // [rsp+20h] [rbp-108h]
  _BYTE pExceptionObject[24]; // [rsp+68h] [rbp-C0h] BYREF
  _BYTE v21[168]; // [rsp+80h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v2 = (_WORD *)(a1 + 8);
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_25;
    case 2:
      v3 = (_QWORD *)(a1 + 16);
      *(_QWORD *)(a1 + 16) = 0;
      Instance = CoCreateInstance(
                   &CLSID_WICImagingFactory2,
                   0,
                   1u,
                   &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
                   (LPVOID *)(a1 + 16));
      if ( Instance < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8B,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.ui\\bitmapiconinfo.cpp",
          (const char *)(unsigned int)Instance,
          ppv);
      *(_QWORD *)(a1 + 24) = 0;
      v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(*(_QWORD *)*v3 + 176LL))(
             *v3,
             *(_QWORD *)(a1 + 304),
             a1 + 24);
      if ( v5 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8E,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.ui\\bitmapiconinfo.cpp",
          (const char *)(unsigned int)v5,
          ppv);
      *(_QWORD *)(a1 + 32) = 0;
      v6 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64))(a1 + 24))(
             *(_QWORD *)(a1 + 24),
             &GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94,
             a1 + 32);
      if ( v6 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"OneCore\\Internal\\Sdk\\Inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v6,
          ppv);
      if ( !*(_QWORD *)(a1 + 32) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x92,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.ui\\bitmapiconinfo.cpp",
          (const char *)0x8000FFFFLL,
          ppv);
      *(_QWORD *)(a1 + 40) = 0;
      *(GUID *)(a1 + 192) = GUID_WICPixelFormat32bppBGRA;
      StreamOfWICBitmapSourceWithOptions = GetStreamOfWICBitmapSourceWithOptions();
      if ( StreamOfWICBitmapSourceWithOptions < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x95,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.ui\\bitmapiconinfo.cpp",
          (const char *)(unsigned int)StreamOfWICBitmapSourceWithOptions,
          ppv);
      *(_QWORD *)(a1 + 48) = 0;
      v9 = winrt::put_abi((winrt *)(a1 + 48), v8);
      RandomAccessStreamOverStream = CreateRandomAccessStreamOverStream(
                                       *(_QWORD *)(a1 + 40),
                                       0,
                                       winrt::impl::guid_v<winrt::Windows::Storage::Streams::IRandomAccessStream>,
                                       v9);
      if ( RandomAccessStreamOverStream < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x99,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.ui\\bitmapiconinfo.cpp",
          (const char *)(unsigned int)RandomAccessStreamOverStream,
          ppv);
      *(_QWORD *)(a1 + 176) = a1 - 112;
      Async = winrt::Windows::Graphics::Imaging::BitmapDecoder::CreateAsync((const struct winrt::Windows::Storage::Streams::IRandomAccessStream *)(a1 + 56));
      if ( *(_DWORD *)(a1 - 112 + 96) == 2 )
      {
        v12 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 208);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)pExceptionObject, v12);
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *(_QWORD *)(a1 + 64) = 0;
      *(_QWORD *)(a1 + 72) = Async;
      *(_QWORD *)(a1 + 80) = 0;
      *(_BYTE *)(a1 + 88) = 1;
      *v2 = 4;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::BitmapDecoder>,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,winrt::WindowsUdk::UI::implementation::BitmapIconInfo *,HICON__ *>::promise_type>(
                              a1 + 64,
                              a1) )
        return;
      goto LABEL_19;
    case 4:
LABEL_19:
      *(_DWORD *)(a1 + 232) = 0;
      *(_QWORD *)(a1 + 240) = 0;
      *(_QWORD *)(a1 + 248) = 0;
      winrt::check_hresult(a1 + 256, *(unsigned int *)(a1 + 84), a1 + 232);
      winrt::impl::check_status_canceled((winrt::impl *)*(unsigned int *)(a1 + 80), v13);
      winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::WindowsUdk::Services::Iris::IrisCreativeResults>,winrt::WindowsUdk::Services::Iris::IrisCreativeResults>::GetResults(
        *(_QWORD *)(a1 + 72),
        a1 + 96);
      winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,1>>(a1 + 64);
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)(a1 + 56));
      SoftwareBitmapAsync = winrt::impl::consume_Windows_Graphics_Imaging_IBitmapFrameWithSoftwareBitmap<winrt::Windows::Graphics::Imaging::BitmapDecoder>::GetSoftwareBitmapAsync(
                              a1 + 96,
                              a1 + 112);
      if ( *(_DWORD *)(a1 - 16) == 2 )
      {
        v15 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 264);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)v21, v15);
        throw (winrt::hresult_canceled *)v21;
      }
      v16 = winrt::Windows::Foundation::operator co_await<winrt::hstring>(a1 + 120, SoftwareBitmapAsync);
      *(_QWORD *)(a1 + 104) = v16;
      *v2 = 6;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,winrt::WindowsUdk::UI::implementation::BitmapIconInfo *,HICON__ *>::promise_type>(
                              v16,
                              a1) )
        return;
      goto LABEL_24;
    case 5:
      winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,1>>(a1 + 64);
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)(a1 + 56));
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)(a1 + 48));
      wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(a1 + 40);
      wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(a1 + 32);
      wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(a1 + 24);
      wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(a1 + 16);
      goto LABEL_25;
    case 6:
LABEL_24:
      v17 = winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::WindowsInternal::Shell::UnifiedTile::LogoLoading::LogoInfo,winrt::Windows::Storage::Streams::IRandomAccessStream>>,1>::await_resume(
              *(_QWORD *)(a1 + 104),
              a1 + 152);
      v18 = *(_QWORD *)(a1 + 176);
      winrt::Windows::Foundation::IUnknown::operator=(v18 + 104, v17);
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)(a1 + 152));
      winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,1>>(a1 + 120);
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)(a1 + 112));
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)(a1 + 96));
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)(a1 + 48));
      wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(a1 + 40);
      wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(a1 + 32);
      wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(a1 + 24);
      wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(a1 + 16);
      *(_QWORD *)(a1 + 160) = v18;
      *v2 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::WindowsUdk::UI::Shell::implementation::MessageReceiver *,enum winrt::WindowsUdk::UI::Shell::MessageReceiverThreadingModel,winrt::Windows::Foundation::Collections::ValueSet const &>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>::final_suspend_awaiter::await_suspend() )
        goto LABEL_25;
      return;
    case 7:
      winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,1>>(a1 + 120);
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)(a1 + 112));
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)(a1 + 96));
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)(a1 + 48));
      wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(a1 + 40);
      wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(a1 + 32);
      wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(a1 + 24);
      wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(a1 + 16);
LABEL_25:
      std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,winrt::WindowsUdk::UI::implementation::BitmapIconInfo *,HICON__ *>::promise_type::~promise_type(a1 - 112);
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 112), (const struct std::nothrow_t *)0x1B0);
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x1803c7cc0  mov     [rsp+arg_0], rcx
0x1803c7cc5  push    rbx
0x1803c7cc6  push    rsi
0x1803c7cc7  push    rdi
0x1803c7cc8  push    r12
0x1803c7cca  push    r13
0x1803c7ccc  push    r14
0x1803c7cce  push    r15
0x1803c7cd0  sub     rsp, 0F0h
0x1803c7cd7  mov     rbx, [rsp+128h+arg_0]
0x1803c7cdf  lea     rsi, [rbx+8]
0x1803c7ce3  mov     [rsp+128h+arg_10], rsi
0x1803c7ceb  movzx   eax, word ptr [rsi]
0x1803c7cee  mov     [rsp+128h+var_F8], ax
0x1803c7cf3  mov     r13d, 1
0x1803c7cf9  add     ax, r13w
0x1803c7cfd  cmp     ax, 8; switch 9 cases
0x1803c7d01  ja      def_1803C7D1C; jumptable 00000001803C7D1C default case, case 1
0x1803c7d07  movsx   rax, ax
0x1803c7d0b  lea     rdx, __ImageBase
0x1803c7d12  mov     ecx, ds:(jpt_1803C7D1C - 180000000h)[rdx+rax*4]
0x1803c7d19  add     rcx, rdx
0x1803c7d1c  jmp     rcx; switch jump
0x1803c7d1e  xor     edi, edi; jumptable 00000001803C7D1C case 4
0x1803c7d20  jmp     loc_1803C816B
0x1803c7d25  xor     edi, edi; jumptable 00000001803C7D1C case 3
0x1803c7d27  lea     r14, [rbx+10h]
0x1803c7d2b  mov     [r14], rdi
0x1803c7d2e  mov     [rsp+128h+ppv], r14; int
0x1803c7d33  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x1803c7d3a  mov     r8d, r13d; dwClsContext
0x1803c7d3d  xor     edx, edx; pUnkOuter
0x1803c7d3f  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x1803c7d46  call    cs:__imp_CoCreateInstance
0x1803c7d4c  mov     rcx, [rsp+128h]; this
0x1803c7d54  test    eax, eax
0x1803c7d56  jns     short loc_1803C7D6C
0x1803c7d58  mov     r9d, eax; char *
0x1803c7d5b  lea     r8, aShellcommonUnd_127; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1803c7d62  mov     edx, 8Bh; void *
0x1803c7d67  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1803c7d6c  lea     r12, [rbx+18h]
0x1803c7d70  mov     [r12], rdi
0x1803c7d74  mov     rcx, [r14]
0x1803c7d77  mov     [rsp+128h+arg_8], rcx
0x1803c7d7f  mov     rax, [rcx]
0x1803c7d82  mov     r8, r12
0x1803c7d85  mov     rdx, [r14+120h]
0x1803c7d8c  mov     rax, [rax+0B0h]
0x1803c7d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803c7d98  mov     rcx, [rsp+128h]; this
0x1803c7da0  test    eax, eax
0x1803c7da2  jns     short loc_1803C7DB9
0x1803c7da4  mov     r9d, eax; char *
0x1803c7da7  lea     r8, aShellcommonUnd_127; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1803c7dae  mov     edx, 8Eh; void *
0x1803c7db3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1803c7db9  lea     r15, [rbx+20h]
0x1803c7dbd  mov     [r15], rdi
0x1803c7dc0  mov     rcx, [r12]
0x1803c7dc4  mov     [rsp+128h+arg_18], rcx
0x1803c7dcc  mov     rax, [rcx]
0x1803c7dcf  mov     r8, r15
0x1803c7dd2  lea     rdx, _GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94
0x1803c7dd9  mov     rax, [rax]
0x1803c7ddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803c7de1  mov     rcx, [rsp+128h]; this
0x1803c7de9  test    eax, eax
0x1803c7deb  jns     short loc_1803C7E01
0x1803c7ded  mov     r9d, eax; char *
0x1803c7df0  lea     r8, aOnecoreInterna_18; "OneCore\\Internal\\Sdk\\Inc\\wil\\opens"...
0x1803c7df7  mov     edx, 1CBEh; void *
0x1803c7dfc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1803c7e01  mov     rcx, [rsp+128h]; this
0x1803c7e09  mov     rdx, [r15]
0x1803c7e0c  test    rdx, rdx
0x1803c7e0f  jnz     short loc_1803C7E29
0x1803c7e11  mov     r9d, 8000FFFFh; char *
0x1803c7e17  lea     r8, aShellcommonUnd_127; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1803c7e1e  mov     edx, 92h; void *
0x1803c7e23  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1803c7e29  lea     r12, [rbx+28h]
0x1803c7e2d  mov     [r12], rdi
0x1803c7e31  mov     [rsp+128h+var_F0], rdx
0x1803c7e36  mov     rcx, [r14]
0x1803c7e39  mov     [rsp+128h+arg_8], rcx
0x1803c7e41  lea     r9, [rbx+0C0h]
0x1803c7e48  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat32bppBGRA.Data1
0x1803c7e4f  movdqu  xmmword ptr [r9], xmm0
0x1803c7e54  mov     [rsp+128h+var_100], r12
0x1803c7e59  call    ?GetStreamOfWICBitmapSourceWithOptions@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@AEBU_GUID@@U3@W4EncodingOptions@@PEAPEAUIStream@@@Z; GetStreamOfWICBitmapSourceWithOptions(IWICImagingFactory *,IWICBitmapSource *,_GUID const &,_GUID,EncodingOptions,IStream * *)
0x1803c7e5e  mov     rcx, [rsp+128h]; this
0x1803c7e66  test    eax, eax
0x1803c7e68  jns     short loc_1803C7E7E
0x1803c7e6a  mov     r9d, eax; char *
0x1803c7e6d  lea     r8, aShellcommonUnd_127; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1803c7e74  mov     edx, 95h; void *
0x1803c7e79  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1803c7e7e  lea     r15, [rbx+30h]
0x1803c7e82  mov     [r15], rdi
0x1803c7e85  mov     rcx, r15; this
0x1803c7e88  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x1803c7e8d  mov     rcx, [r12]
0x1803c7e91  mov     [rsp+128h+var_E8], rcx
0x1803c7e96  mov     r9, rax
0x1803c7e99  lea     r8, ??$guid_v@UIRandomAccessStream@Streams@Storage@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Storage::Streams::IRandomAccessStream>
0x1803c7ea0  xor     edx, edx
0x1803c7ea2  call    cs:__imp_CreateRandomAccessStreamOverStream
0x1803c7ea8  mov     rcx, [rsp+128h]; this
0x1803c7eb0  test    eax, eax
0x1803c7eb2  jns     short loc_1803C7EC8
0x1803c7eb4  mov     r9d, eax; char *
0x1803c7eb7  lea     r8, aShellcommonUnd_127; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1803c7ebe  mov     edx, 99h; void *
0x1803c7ec3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1803c7ec8  lea     r14, [rbx-70h]
0x1803c7ecc  mov     [rbx+0B0h], r14
0x1803c7ed3  lea     rcx, [rbx+38h]; struct winrt::Windows::Storage::Streams::IRandomAccessStream *
0x1803c7ed7  mov     rdx, r15
0x1803c7eda  call    ?CreateAsync@BitmapDecoder@Imaging@Graphics@Windows@winrt@@SA@AEBUIRandomAccessStream@Streams@Storage@45@@Z; winrt::Windows::Graphics::Imaging::BitmapDecoder::CreateAsync(winrt::Windows::Storage::Streams::IRandomAccessStream const &)
0x1803c7edf  nop
0x1803c7ee0  mov     ecx, [r14+60h]
0x1803c7ee4  nop
0x1803c7ee5  cmp     ecx, 2
0x1803c7ee8  jnz     short loc_1803C7F14
0x1803c7eea  lea     rcx, [rbx+0D0h]
0x1803c7ef1  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1803c7ef6  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1803c7ef9  lea     rcx, [rsp+128h+pExceptionObject]; this
0x1803c7efe  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x1803c7f03  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x1803c7f0a  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x1803c7f0f  call    _CxxThrowException_0
0x1803c7f14  lea     rcx, [rbx+40h]
0x1803c7f18  mov     [rcx], rdi
0x1803c7f1b  mov     [rbx+48h], rax
0x1803c7f1f  mov     [rbx+50h], rdi
0x1803c7f23  mov     [rbx+58h], r13b
0x1803c7f27  mov     eax, 4
0x1803c7f2c  mov     [rsi], ax
0x1803c7f2f  mov     rdx, rbx
0x1803c7f32  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@USoftwareBitmap@Imaging@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUBitmapIconInfo@implementation@UI@WindowsUdk@4@PEAUHICON__@@@experimental@std@@@?$await_adapter@U?$IAsyncOperation@UBitmapDecoder@Imaging@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@USoftwareBitmap@Imaging@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUBitmapIconInfo@implementation@UI@WindowsUdk@4@PEAUHICON__@@@experimental@std@@@experimental@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::BitmapDecoder>,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,winrt::WindowsUdk::UI::implementation::BitmapIconInfo *,HICON__ *>::promise_type>(std::experimental::coroutine_handle<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,winrt::WindowsUdk::UI::implementation::BitmapIconInfo *,HICON__ *>::promise_type>)
0x1803c7f37  test    al, al
0x1803c7f39  jz      short loc_1803C7F8F
0x1803c7f3b  jmp     loc_1803C818B
0x1803c7f40  lea     rcx, [rbx+40h]; jumptable 00000001803C7D1C case 6
0x1803c7f44  call    ??1?$cancellable_awaiter@U?$await_adapter@U?$IAsyncOperation@I@Foundation@Windows@winrt@@$00@impl@winrt@@@winrt@@QEAA@XZ; winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<uint>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<uint>,1>>(void)
0x1803c7f49  nop
0x1803c7f4a  lea     rcx, [rbx+38h]; this
0x1803c7f4e  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1803c7f53  nop
0x1803c7f54  lea     rcx, [rbx+30h]; this
0x1803c7f58  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1803c7f5d  nop
0x1803c7f5e  lea     rcx, [rbx+28h]
0x1803c7f62  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x1803c7f67  nop
0x1803c7f68  lea     rcx, [rbx+20h]
0x1803c7f6c  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x1803c7f71  nop
0x1803c7f72  lea     rcx, [rbx+18h]
0x1803c7f76  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x1803c7f7b  nop
0x1803c7f7c  lea     rcx, [rbx+10h]
0x1803c7f80  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x1803c7f85  nop
0x1803c7f86  xor     edi, edi
0x1803c7f88  jmp     loc_1803C816B
0x1803c7f8d  xor     edi, edi; jumptable 00000001803C7D1C case 5
0x1803c7f8f  lea     r8, [rbx+0E8h]
0x1803c7f96  mov     [r8], edi
0x1803c7f99  mov     [rbx+0F0h], rdi
0x1803c7fa0  mov     [rbx+0F8h], rdi
0x1803c7fa7  mov     edx, [rbx+54h]
0x1803c7faa  mov     [rsp+128h+var_CC], edx
0x1803c7fae  lea     rcx, [rbx+100h]
0x1803c7fb5  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1803c7fba  mov     ecx, [rbx+50h]; this
0x1803c7fbd  mov     [rsp+128h+var_D0], ecx
0x1803c7fc1  call    ?check_status_canceled@impl@winrt@@YAXW4AsyncStatus@Foundation@Windows@2@@Z; winrt::impl::check_status_canceled(winrt::Windows::Foundation::AsyncStatus)
0x1803c7fc6  mov     rcx, [rbx+48h]
0x1803c7fca  mov     [rsp+128h+var_D8], rcx
0x1803c7fcf  lea     rdx, [rbx+60h]
0x1803c7fd3  call    ?GetResults@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UIrisCreativeResults@Iris@Services@WindowsUdk@winrt@@@Foundation@Windows@winrt@@UIrisCreativeResults@Iris@Services@WindowsUdk@4@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::WindowsUdk::Services::Iris::IrisCreativeResults>,winrt::WindowsUdk::Services::Iris::IrisCreativeResults>::GetResults(void)
0x1803c7fd8  nop
0x1803c7fd9  lea     rcx, [rbx+40h]
0x1803c7fdd  call    ??1?$cancellable_awaiter@U?$await_adapter@U?$IAsyncOperation@I@Foundation@Windows@winrt@@$00@impl@winrt@@@winrt@@QEAA@XZ; winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<uint>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<uint>,1>>(void)
0x1803c7fe2  nop
0x1803c7fe3  lea     rcx, [rbx+38h]; this
0x1803c7fe7  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1803c7fec  lea     rdx, [rbx+70h]
0x1803c7ff0  lea     rcx, [rbx+60h]
0x1803c7ff4  call    ?GetSoftwareBitmapAsync@?$consume_Windows_Graphics_Imaging_IBitmapFrameWithSoftwareBitmap@UBitmapDecoder@Imaging@Graphics@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Graphics_Imaging_IBitmapFrameWithSoftwareBitmap<winrt::Windows::Graphics::Imaging::BitmapDecoder>::GetSoftwareBitmapAsync(void)
0x1803c7ff9  nop
0x1803c7ffa  mov     ecx, [rbx-10h]
0x1803c7ffd  nop
0x1803c7ffe  cmp     ecx, 2
0x1803c8001  jnz     short loc_1803C8033
0x1803c8003  lea     rcx, [rbx+108h]
0x1803c800a  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1803c800f  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1803c8012  lea     rcx, [rsp+128h+var_A8]; this
0x1803c801a  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x1803c801f  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x1803c8026  lea     rcx, [rsp+128h+var_A8]; pExceptionObject
0x1803c802e  call    _CxxThrowException_0
0x1803c8033  lea     rcx, [rbx+78h]
0x1803c8037  mov     rdx, rax
0x1803c803a  call    ??$?__LUhstring@winrt@@@Foundation@Windows@winrt@@YA?AU?$await_adapter@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@$00@impl@2@AEBU?$IAsyncOperation@Uhstring@winrt@@@012@@Z; winrt::Windows::Foundation::operator co_await<winrt::hstring>(winrt::Windows::Foundation::IAsyncOperation<winrt::hstring> const &)
0x1803c803f  mov     [rbx+68h], rax
0x1803c8043  mov     ecx, 6
0x1803c8048  mov     [rsi], cx
0x1803c804b  mov     rdx, rbx
0x1803c804e  mov     rcx, rax
0x1803c8051  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@USoftwareBitmap@Imaging@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUBitmapIconInfo@implementation@UI@WindowsUdk@4@PEAUHICON__@@@experimental@std@@@?$await_adapter@U?$IAsyncOperation@USoftwareBitmap@Imaging@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@USoftwareBitmap@Imaging@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUBitmapIconInfo@implementation@UI@WindowsUdk@4@PEAUHICON__@@@experimental@std@@@experimental@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,winrt::WindowsUdk::UI::implementation::BitmapIconInfo *,HICON__ *>::promise_type>(std::experimental::coroutine_handle<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,winrt::WindowsUdk::UI::implementation::BitmapIconInfo *,HICON__ *>::promise_type>)
0x1803c8056  test    al, al
0x1803c8058  jz      short loc_1803C80B8
0x1803c805a  jmp     loc_1803C818B
0x1803c805f  lea     rcx, [rbx+78h]; jumptable 00000001803C7D1C case 8
0x1803c8063  call    ??1?$cancellable_awaiter@U?$await_adapter@U?$IAsyncOperation@I@Foundation@Windows@winrt@@$00@impl@winrt@@@winrt@@QEAA@XZ; winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<uint>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<uint>,1>>(void)
0x1803c8068  nop
0x1803c8069  lea     rcx, [rbx+70h]; this
0x1803c806d  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1803c8072  nop
0x1803c8073  lea     rcx, [rbx+60h]; this
0x1803c8077  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1803c807c  nop
0x1803c807d  lea     rcx, [rbx+30h]; this
0x1803c8081  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1803c8086  nop
0x1803c8087  lea     rcx, [rbx+28h]
0x1803c808b  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x1803c8090  nop
0x1803c8091  lea     rcx, [rbx+20h]
0x1803c8095  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x1803c809a  nop
0x1803c809b  lea     rcx, [rbx+18h]
0x1803c809f  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x1803c80a4  nop
0x1803c80a5  lea     rcx, [rbx+10h]
0x1803c80a9  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x1803c80ae  nop
0x1803c80af  xor     edi, edi
0x1803c80b1  jmp     loc_1803C816B
0x1803c80b6  xor     edi, edi; jumptable 00000001803C7D1C case 7
0x1803c80b8  lea     r15, [rbx+98h]
0x1803c80bf  mov     rdx, r15
0x1803c80c2  mov     rcx, [rbx+68h]
0x1803c80c6  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@U?$IKeyValuePair@ULogoInfo@LogoLoading@UnifiedTile@Shell@WindowsInternal@winrt@@UIRandomAccessStream@Streams@Storage@Windows@6@@Collections@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::WindowsInternal::Shell::UnifiedTile::LogoLoading::LogoInfo,winrt::Windows::Storage::Streams::IRandomAccessStream>>,1>::await_resume(void)
0x1803c80cb  mov     r14, [rbx+0B0h]
0x1803c80d2  lea     rcx, [r14+68h]
0x1803c80d6  mov     rdx, rax
0x1803c80d9  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x1803c80de  mov     rcx, r15; this
0x1803c80e1  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1803c80e6  nop
0x1803c80e7  lea     rcx, [rbx+78h]
0x1803c80eb  call    ??1?$cancellable_awaiter@U?$await_adapter@U?$IAsyncOperation@I@Foundation@Windows@winrt@@$00@impl@winrt@@@winrt@@QEAA@XZ; winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<uint>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<uint>,1>>(void)
0x1803c80f0  nop
0x1803c80f1  lea     rcx, [rbx+70h]; this
0x1803c80f5  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1803c80fa  nop
0x1803c80fb  lea     rcx, [rbx+60h]; this
0x1803c80ff  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1803c8104  nop
0x1803c8105  lea     rcx, [rbx+30h]; this
0x1803c8109  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1803c810e  nop
0x1803c810f  lea     rcx, [rbx+28h]
0x1803c8113  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x1803c8118  nop
0x1803c8119  lea     rcx, [rbx+20h]
0x1803c811d  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x1803c8122  nop
0x1803c8123  lea     rcx, [rbx+18h]
0x1803c8127  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x1803c812c  nop
0x1803c812d  lea     rcx, [rbx+10h]
0x1803c8131  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x1803c8136  nop
0x1803c8137  jmp     short loc_1803C814F
0x1803c8139  mov     rbx, [rsp+128h+arg_0]
0x1803c8141  lea     r14, [rbx-70h]
0x1803c8145  xor     edi, edi
0x1803c8147  mov     rsi, [rsp+128h+arg_10]
0x1803c814f  lea     rcx, [rbx+0A0h]
0x1803c8156  mov     [rcx], r14
0x1803c8159  xor     eax, eax
0x1803c815b  mov     [rsi], ax
0x1803c815e  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@PEAUMessageReceiver@implementation@Shell@UI@WindowsUdk@4@W4MessageReceiverThreadingModel@7894@AEBUValueSet@Collections@234@@experimental@std@@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@experimental@std@@@Z; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::WindowsUdk::UI::Shell::implementation::MessageReceiver *,winrt::WindowsUdk::UI::Shell::MessageReceiverThreadingModel,winrt::Windows::Foundation::Collections::ValueSet const &>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>::final_suspend_awaiter::await_suspend(std::experimental::coroutine_handle<void>)
0x1803c8163  test    al, al
0x1803c8165  jz      short loc_1803C816B
0x1803c8167  jmp     short loc_1803C818B
0x1803c8169  xor     edi, edi; jumptable 00000001803C7D1C cases 0,2
0x1803c816b  lea     rcx, [rbx-70h]
0x1803c816f  call    ??1promise_type@?$coroutine_traits@U?$IAsyncOperation@USoftwareBitmap@Imaging@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUBitmapIconInfo@implementation@UI@WindowsUdk@4@PEAUHICON__@@@experimental@std@@UEAA@XZ; std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Imaging::SoftwareBitmap>,winrt::WindowsUdk::UI::implementation::BitmapIconInfo *,HICON__ *>::promise_type::~promise_type(void)
0x1803c8174  cmp     [rbx+0Ah], di
0x1803c8178  jz      short loc_1803C818B
0x1803c817a  mov     edx, 1B0h; struct std::nothrow_t *
0x1803c817f  lea     rcx, [rbx-70h]; void *
  ... truncated ...
```
