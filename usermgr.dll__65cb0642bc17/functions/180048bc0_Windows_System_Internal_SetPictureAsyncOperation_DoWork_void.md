# Windows::System::Internal::SetPictureAsyncOperation::DoWork(void)

- ea: `0x180048bc0`
- end: `0x180049631`
- name: `?DoWork@SetPictureAsyncOperation@Internal@System@Windows@@UEAAJXZ`
- size: `2673`
- prototype: `__int64 __fastcall(Windows::System::Internal::SetPictureAsyncOperation *__hidden this)`
- caller_count: `0`
- callee_count: `33`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800013a4`
- `0x18000292c`
- `0x180006130`
- `0x180007920`
- `0x18000890c`
- `0x180008b10`
- `0x18000a4a0`
- `0x18000acdc`
- `0x18000ca64`
- `0x18000ce48`
- `0x18000ec28`
- `0x180012a1c`
- `0x180012e00`
- `0x180015960`
- `0x1800181f0`
- `0x180024828`
- `0x18002540c`
- `0x180025808`
- `0x18003b578`
- `0x18004254c`
- `0x180048bc0`
- `0x18004e508`
- `0x18004e58c`
- `0x180051cc0`
- `0x180060810`
- `0x1800641b8`
- `0x18006b62c`
- `0x18006f1c9`
- `0x18006f1e1`
- `0x1800ca7b0`
- `0x1800cabe8`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004908d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004908d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800492c1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180049370`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800492c1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180049370`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048e8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004927d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048e8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004927d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180048fc7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180048fc7`

## string_xrefs

- `0x180048f95`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`
- `0x180049440`: `onecore\ds\security\umstartup\usermgr\lib\setpictureasyncoperation.cpp`
- `0x180049454`: `onecore\ds\security\umstartup\usermgr\lib\setpictureasyncoperation.cpp`
- `0x180049467`: `onecore\ds\security\umstartup\usermgr\lib\setpictureasyncoperation.cpp`
- `0x18004947b`: `onecore\ds\security\umstartup\usermgr\lib\setpictureasyncoperation.cpp`
- `0x18004948f`: `onecore\ds\security\umstartup\usermgr\lib\setpictureasyncoperation.cpp`
- `0x1800494a3`: `onecore\ds\security\umstartup\usermgr\lib\setpictureasyncoperation.cpp`
- `0x1800494b8`: `onecore\ds\security\umstartup\usermgr\lib\setpictureasyncoperation.cpp`
- `0x1800494cd`: `onecore\ds\security\umstartup\usermgr\lib\setpictureasyncoperation.cpp`
- `0x1800494e2`: `onecore\ds\security\umstartup\usermgr\lib\setpictureasyncoperation.cpp`
- `0x1800494f7`: `onecore\ds\security\umstartup\usermgr\lib\setpictureasyncoperation.cpp`
- `0x18004950c`: `onecore\ds\security\umstartup\usermgr\lib\setpictureasyncoperation.cpp`
- `0x180049521`: `onecore\ds\security\umstartup\usermgr\lib\setpictureasyncoperation.cpp`
- `0x180049532`: `onecore\ds\security\umstartup\usermgr\lib\setpictureasyncoperation.cpp`
- `0x180049547`: `onecore\ds\security\umstartup\usermgr\lib\setpictureasyncoperation.cpp`
- `0x18004955b`: `onecore\ds\security\umstartup\usermgr\lib\setpictureasyncoperation.cpp`
- `0x18004956f`: `onecore\ds\security\umstartup\usermgr\lib\setpictureasyncoperation.cpp`
- `0x180049583`: `onecore\ds\security\umstartup\usermgr\lib\setpictureasyncoperation.cpp`
- `0x180049597`: `onecore\ds\security\umstartup\usermgr\lib\setpictureasyncoperation.cpp`
- `0x1800495ac`: `onecore\ds\security\umstartup\usermgr\lib\setpictureasyncoperation.cpp`
- `0x1800495c0`: `onecore\ds\security\umstartup\usermgr\lib\setpictureasyncoperation.cpp`
- `0x1800495d1`: `onecore\ds\security\umstartup\usermgr\lib\setpictureasyncoperation.cpp`
- `0x1800495f8`: `onecore\ds\security\umstartup\usermgr\lib\setpictureasyncoperation.cpp`
- `0x18004961e`: `onecore\ds\security\umstartup\usermgr\lib\setpictureasyncoperation.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall Windows::System::Internal::SetPictureAsyncOperation::DoWork(
        Windows::System::Internal::SetPictureAsyncOperation *this)
{
  unsigned __int64 v1; // rbp
  int v3; // eax
  __int64 *v4; // rcx
  __int64 v5; // rax
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  __int64 v13; // r8
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // r8d
  int v17; // r9d
  __int64 v18; // rbx
  int v19; // eax
  __int64 v20; // rdi
  int ActivationFactory; // eax
  __int64 v22; // rsi
  __int64 (__fastcall *v23)(__int64, unsigned __int64); // rdi
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  const char *v28; // r9
  int v29; // eax
  __int64 v30; // rbx
  int updated; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  __int64 v35; // r8
  __int64 v36; // r9
  int v37; // ecx
  int v38; // ecx
  int v39; // ecx
  int v40; // ecx
  int v41; // ecx
  __int64 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  int v45; // eax
  const char *v46; // r9
  int v47; // ecx
  int v48; // r8d
  int v49; // r9d
  __int64 v50; // rcx
  __int64 v51; // rcx
  wil *v52; // rcx
  __int64 result; // rax
  __int64 v54; // rcx
  __int64 v55; // rcx
  unsigned int v56; // ebx
  unsigned int v57; // eax
  unsigned int v58; // eax
  _BYTE *v59; // rbp
  int v60; // eax
  __int64 v61; // r8
  __int64 v62; // r9
  __int64 v63; // rbx
  int v64; // ecx
  int v65; // r8d
  int v66; // r9d
  int v67; // [rsp+20h] [rbp-50h]
  int v68; // [rsp+20h] [rbp-50h]
  int v69; // [rsp+20h] [rbp-50h]
  unsigned int v70; // [rsp+20h] [rbp-50h]
  char v71; // [rsp+70h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+2C8h]

  v1 = (unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL;
  *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x88) = this;
  *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x90) = 0;
  *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = 0;
  memset_0((void *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 224), 0, 0x1A0u);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    ((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 64,
    0);
  try
  {
    GetCallerTokenFromComCall((PHANDLE)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 64));
    GetCallerInformationFromToken(
      *(HANDLE *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40),
      (struct _BASIC_CALLER_INFORMATION *)(v1 + 224),
      0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v1 + 64,
      0);
    GetCallerToken2((PHANDLE)(v1 + 64));
    *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x70) = *((_QWORD *)this + 26);
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v1 + 112);
    *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = 0;
    v3 = Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
           (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v1 + 112),
           (__int64 *)(v1 + 48));
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5E,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\setpictureasyncoperation.cpp",
        (const char *)(unsigned int)v3,
        v67);
    (*(void (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL)
                                                                   + 0x30)
                                                     + 88LL))(
      *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30),
      v1 + 144);
    Windows::System::Internal::GetDefaultSignedInAccount(
      v1 + 152,
      *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x90));
    *(_OWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0xB0) = 0;
    if ( !memcmp_0((const void *)(v1 + 160), (const void *)(v1 + 176), 0x10u) )
    {
      *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
      v4 = *(__int64 **)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30);
      v5 = *v4;
      *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
      v6 = (*(__int64 (__fastcall **)(__int64 *, unsigned __int64))(v5 + 72))(v4, v1 + 24);
      if ( v6 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x67,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\setpictureasyncoperation.cpp",
          (const char *)(unsigned int)v6,
          v67);
      wil::GetActivationFactory<Microsoft::LocalUserImageProvider::ILocalUserImageProviderStatics>((const WCHAR *)(v1 + 80));
      *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x60) = *((_QWORD *)this + 30);
      *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38) = *(_QWORD *)(((unsigned __int64)&v71
                                                                                        & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                       + 0x18);
      *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48) = *((_QWORD *)this + 27);
      ___call_and_wait_for_completion_UILocalUserImageProviderStatics_LocalUserImageProvider_Microsoft__PEAUHSTRING____PEAU4_PEAUIRandomAccessStreamReference_Streams_Storage_Windows__PEAPEAUIAsyncAction_Foundation_8___ZPEAU4_PEAU4_PEAU5678__wil__YA_A_PPEAUILocalUserImageProviderStatics_LocalUserImageProvider_Microsoft__P8123_EAAJPEAUHSTRING____1PEAUIRandomAccessStreamReference_Streams_Storage_Windows__PEAPEAUIAsyncAction_Foundation_8__Z__QEAPEAU4_5__QEAPEAU5678__Z(
        *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50),
        v7,
        (_QWORD *)(v1 + 72),
        (_QWORD *)(v1 + 56),
        (_QWORD *)(v1 + 96));
      *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
      *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = 0;
      Windows::System::Internal::StaticsCache::GetStaticInstance<Windows::System::Internal::Implementation::IUserStaticsInternal>((_QWORD *)(v1 + 32));
      v8 = *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 8);
      *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      Windows::System::Internal::StaticsCache::GetStaticInstance<Windows::System::Internal::Implementation::IUserManagerPrivate>((_QWORD *)(v1 + 8));
      *(_BYTE *)v1 = 0;
      *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x58) = 0;
      *(_DWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = 0;
      *(_DWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
      v9 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(((unsigned __int64)&v71
                                                                              & 0xFFFFFFFFFFFFFFE0uLL)
                                                                             + 0x30)
                                                               + 48LL))(
             *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30),
             v1 + 4);
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x7D,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\setpictureasyncoperation.cpp",
          (const char *)(unsigned int)v9,
          v68);
      v10 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(((unsigned __int64)&v71
                                                                               & 0xFFFFFFFFFFFFFFE0uLL)
                                                                              + 0x30)
                                                                + 96LL))(
              *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30),
              v1 + 16);
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x7E,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\setpictureasyncoperation.cpp",
          (const char *)(unsigned int)v10,
          v68);
      v69 = v1 + 88;
      v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, unsigned __int64))(**(_QWORD **)(((unsigned __int64)&v71
                                                                                               & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                              + 0x20)
                                                                                + 136LL))(
              *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20),
              *(unsigned int *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 4),
              *(unsigned int *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10),
              (unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL);
      if ( v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x80,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\setpictureasyncoperation.cpp",
          (const char *)(unsigned int)v11,
          v69);
      v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL)
                                                                    + 8)
                                                      + 80LL))(
              *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 8),
              *((_QWORD *)this + 26));
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x82,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\setpictureasyncoperation.cpp",
          (const char *)(unsigned int)v12,
          v69);
      LOBYTE(v13) = *(_BYTE *)v1;
      (*(void (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(**(_QWORD **)(((unsigned __int64)&v71
                                                                             & 0xFFFFFFFFFFFFFFE0uLL)
                                                                            + 0x20)
                                                              + 128LL))(
        *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20),
        *((_QWORD *)this + 26),
        v13,
        *((_QWORD *)this + 27));
      if ( (unsigned int)dword_180146228 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_180146228, 0x400000000000LL, v14, v15) )
      {
        *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x60) = WindowsGetStringRawBuffer(
                                                                                 *((HSTRING *)this + 27),
                                                                                 0);
        *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38) = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
          (unsigned int)&dword_180146228,
          (unsigned int)word_18012C83A,
          v16,
          v17,
          v1 + 56,
          v1 + 96);
      }
      *((_DWORD *)this + 56) = 0;
      wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(v1 + 88);
      wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(v1 + 8);
      wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(v1 + 32);
      wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(v1 + 80);
      Windows::Internal::String::~String((Windows::Internal::String *)(v1 + 24));
      goto LABEL_57;
    }
    if ( memcmp_0((const void *)(v1 + 160), qword_180116AD8, 0x10u)
      && memcmp_0((const void *)(v1 + 160), qword_180116AC8, 0x10u) )
    {
LABEL_57:
      v56 = *((_DWORD *)this + 56);
      wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(v1 + 152);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v1 + 48);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v1 + 112);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v1 + 64);
      return v56;
    }
    v18 = *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x98);
    *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x58) = v18;
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
    *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50) = 0;
    v19 = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(
            (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))(v1 + 88),
            v1 + 80);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x93,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\setpictureasyncoperation.cpp",
        (const char *)(unsigned int)v19,
        v67);
    *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = 0;
    *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0xB0) = 0;
    *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0xD8) = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      (HSTRING_HEADER *)(v1 + 192),
      L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
      0x41u,
      0x40u);
    v20 = *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0xD8);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v1 + 32);
    ActivationFactory = RoGetActivationFactory(v20, &GUID_78371994_f53b_489b_b66f_3acca8b88faa, v1 + 32);
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x98,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\setpictureasyncoperation.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v67);
    *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
    v22 = *((_QWORD *)this + 30);
    v23 = *(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v22 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v1 + 24);
    v24 = v23(v22, v1 + 24);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9B,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\setpictureasyncoperation.cpp",
        (const char *)(unsigned int)v24,
        v67);
    *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38) = 0;
    v25 = BlockOnCompletionAndGetResults<Windows::Storage::Streams::IRandomAccessStreamWithContentType *,Windows::Storage::Streams::IRandomAccessStreamWithContentType>(
            *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18),
            v1 + 56);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9E,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\setpictureasyncoperation.cpp",
        (const char *)(unsigned int)v25,
        v67);
    *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48) = 0;
    v26 = Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStreamWithContentType>::As<Windows::Storage::Streams::IRandomAccessStream>(
            (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))(v1 + 56),
            v1 + 72);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA1,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\setpictureasyncoperation.cpp",
        (const char *)(unsigned int)v26,
        v67);
    *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
    *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28) = 0;
    *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x60) = 0;
    v27 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(((unsigned __int64)&v71
                                                                             & 0xFFFFFFFFFFFFFFE0uLL)
                                                                            + 0x30)
                                                              + 80LL))(
            *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30),
            v1 + 96);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA6,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\setpictureasyncoperation.cpp",
        (const char *)(unsigned int)v27,
        v67);
    if ( !ImpersonateLoggedOnUser(*(HANDLE *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x60)) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xA7,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\setpictureasyncoperation.cpp",
        v28);
    *(_BYTE *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 1) = 1;
    v70 = *((_DWORD *)this + 58);
    v29 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**(_QWORD **)(((unsigned __int64)&v71
                                                                                    & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                   + 0x20)
                                                                     + 48LL))(
            *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20),
            v18,
            *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48),
            *((_QWORD *)this + 27));
    if ( v29 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAA,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\setpictureasyncoperation.cpp",
        (const char *)(unsigned int)v29,
        v70);
    v30 = *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 8);
    updated = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::UpdateWebAccountPictureResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::UpdateWebAccountPictureResult *>>(v30);
    if ( updated >= 0 )
      updated = (*(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v30 + 64LL))(v30, v1 + 40);
    if ( updated < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAB,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\setpictureasyncoperation.cpp",
        (const char *)(unsigned int)updated,
        v70);
    v32 = (*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL)
                                                                  + 0x28)
                                                    + 72LL))(
            *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28),
            (char *)this + 229);
    if ( v32 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAC,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\setpictureasyncoperation.cpp",
        (const char *)(unsigned int)v32,
        v70);
    v33 = (*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL)
                                                                  + 0x28)
                                                    + 64LL))(
            *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28),
            (char *)this + 228);
    if ( v33 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAD,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\setpictureasyncoperation.cpp",
        (const char *)(unsigned int)v33,
        v70);
    *(_DWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = 5;
    v34 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(((unsigned __int64)&v71
                                                                             & 0xFFFFFFFFFFFFFFE0uLL)
                                                                            + 0x28)
                                                              + 48LL))(
            *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28),
            v1 + 4);
    if ( v34 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB0,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\setpictureasyncoperation.cpp",
        (const char *)(unsigned int)v34,
        v70);
    v37 = *(_DWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 4);
    if ( !v37 )
    {
      *((_DWORD *)this + 56) = 0;
LABEL_52:
      RevertToSelf();
      v54 = *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28);
      if ( v54 )
      {
        *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28) = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
      }
      v55 = *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 8);
      if ( v55 )
      {
        *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v1 + 72);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v1 + 56);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v1 + 24);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v1 + 32);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v1 + 80);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v1 + 88);
      goto LABEL_57;
    }
    v38 = v37 - 1;
    if ( !v38 )
      goto LABEL_80;
    v39 = v38 - 1;
    if ( !v39 )
    {
      v57 = wil::verify_hresult<long>(3489661500LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC2,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\setpictureasyncoperation.cpp",
        (const char *)v57,
        v70);
    }
    v40 = v39 - 1;
    if ( !v40 )
    {
LABEL_80:
      v58 = wil::verify_hresult<long>(2156265484LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC5,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\setpictureasyncoperation.cpp",
        (const char *)v58,
        v70);
    }
    v41 = v40 - 1;
    if ( v41 )
    {
      if ( v41 == 1 )
      {
        *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x68) = 0;
        *(_DWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
        v42 = *(__int64 **)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28);
        v43 = *v42;
        *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x68) = 0;
        v44 = (*(__int64 (__fastcall **)(__int64 *, unsigned __int64))(v43 + 56))(v42, v1 + 104);
        if ( v44 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xC9,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\setpictureasyncoperation.cpp",
            (const char *)(unsigned int)v44,
            v70);
        v45 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(((unsigned __int64)&v71
                                                                                 & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                + 0x68)
                                                                  + 48LL))(
                *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x68),
                v1 + 16);
        if ( v45 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xCA,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\setpictureasyncoperation.cpp",
            (const char *)(unsigned int)v45,
            v70);
        v46 = (const char *)*(unsigned int *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10);
        if ( (_DWORD)v46 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0xCB,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\setpictureasyncoperation.cpp",
            v46,
            v70);
        wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(v1 + 104);
      }
      goto LABEL_52;
    }
    *((_DWORD *)this + 56) = -2147023673;
    if ( (unsigned int)dword_180146228 > 5
      && (unsigned __int8)tlgKeywordOn(&dword_180146228, 0x400000000000LL, v35, v36) )
    {
      *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x78) = WindowsGetStringRawBuffer(
                                                                               *((HSTRING *)this + 27),
                                                                               0);
      *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80) = 0x1000000;
      *(_BYTE *)v1 = 1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        v47,
        (unsigned int)byte_18012C7DB,
        v48,
        v49,
        (unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL,
        v1 + 128,
        v1 + 120);
    }
    RevertToSelf();
    v50 = *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28);
    if ( v50 )
    {
      *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    }
    v51 = *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 8);
    if ( v51 )
    {
      *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v1 + 72);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v1 + 56);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v1 + 24);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v1 + 32);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v1 + 80);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v1 + 88);
    wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(v1 + 152);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v1 + 48);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v1 + 112);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v1 + 64);
    result = 0;
  }
  catch ( ... )
  {
    v59 = (_BYTE *)((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL);
    v60 = wil::ResultFromCaughtException(v52);
    v63 = *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x88);
    *(_DWORD *)(v63 + 224) = v60;
    if ( (unsigned int)dword_180146228 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180146228, 0x400000000000LL, v61, v62) )
      {
        *(_DWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = *(_DWORD *)(v63 + 224);
        *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x88) = WindowsGetStringRawBuffer(
                                                                                 *(HSTRING *)(v63 + 216),
                                                                                 0);
        *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80) = "Request Execution";
        *(_QWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 0x78) = 0x1000000;
        *v59 = 1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v64,
          (unsigned int)&word_18012C76E,
          v65,
          v66,
          (unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL,
          (__int64)(v59 + 120),
          (__int64)(v59 + 128),
          (__int64)(v59 + 136),
          (__int64)(v59 + 4));
      }
    }
    *(_DWORD *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = *(_DWORD *)(v63 + 224);
    return *(unsigned int *)(((unsigned __int64)&v71 & 0xFFFFFFFFFFFFFFE0uLL) + 4);
  }
  return result;
}

```

## disassembly

```asm
0x180048bc0  push    rbp
0x180048bc2  push    rbx
0x180048bc3  push    rsi
0x180048bc4  push    rdi
0x180048bc5  push    r14
0x180048bc7  push    r15
0x180048bc9  sub     rsp, 308h
0x180048bd0  lea     rbp, [rsp+70h]
0x180048bd5  and     rbp, 0FFFFFFFFFFFFFFE0h
0x180048bd9  mov     rax, cs:__security_cookie
0x180048be0  xor     rax, rsp
0x180048be3  mov     [rbp+2C0h+var_40], rax
0x180048bea  mov     r14, rcx
0x180048bed  mov     [rbp+2C0h+var_238], rcx
0x180048bf4  xor     r15d, r15d
0x180048bf7  mov     [rbp+2C0h+var_230], r15
0x180048bfe  mov     [rbp+2C0h+TokenHandle], r15
0x180048c02  xor     edx, edx; Val
0x180048c04  mov     r8d, 1A0h; Size
0x180048c0a  lea     rcx, [rbp+2C0h+var_1E0]; void *
0x180048c11  call    memset_0
0x180048c16  xor     edx, edx
0x180048c18  lea     rcx, [rbp+2C0h+TokenHandle]
0x180048c1c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180048c21  lea     rcx, [rbp+2C0h+TokenHandle]; phNewToken
0x180048c25  call    ?GetCallerTokenFromComCall@@YAJPEAPEAX@Z; GetCallerTokenFromComCall(void * *)
0x180048c2a  xor     r8d, r8d; struct _EXTENDED_CALLER_INFORMATION *
0x180048c2d  lea     rdx, [rbp+2C0h+var_1E0]; struct _BASIC_CALLER_INFORMATION *
0x180048c34  mov     rcx, [rbp+2C0h+TokenHandle]; ClientToken
0x180048c38  call    ?GetCallerInformationFromToken@@YAJPEAXPEAU_BASIC_CALLER_INFORMATION@@PEAU_EXTENDED_CALLER_INFORMATION@@@Z; GetCallerInformationFromToken(void *,_BASIC_CALLER_INFORMATION *,_EXTENDED_CALLER_INFORMATION *)
0x180048c3d  xor     edx, edx
0x180048c3f  lea     rcx, [rbp+2C0h+TokenHandle]
0x180048c43  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180048c48  lea     rcx, [rbp+2C0h+TokenHandle]; TokenHandle
0x180048c4c  call    ?GetCallerToken2@@YAJPEAPEAX@Z; GetCallerToken2(void * *)
0x180048c51  mov     rax, [r14+0D0h]
0x180048c58  mov     [rbp+2C0h+var_250], rax
0x180048c5c  lea     rcx, [rbp+2C0h+var_250]
0x180048c60  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180048c65  nop
0x180048c66  mov     [rbp+2C0h+var_290], r15
0x180048c6a  lea     rdx, [rbp+2C0h+var_290]
0x180048c6e  lea     rcx, [rbp+2C0h+var_250]
0x180048c72  call    ??$As@UIUserInternal@Implementation@Internal@System@Windows@@@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserInternal>>)
0x180048c77  mov     rcx, [rsp+338h]; this
0x180048c7f  test    eax, eax
0x180048c81  js      loc_18004943D
0x180048c87  mov     rcx, [rbp+2C0h+var_290]
0x180048c8b  mov     rax, [rcx]
0x180048c8e  lea     rdx, [rbp+2C0h+var_230]
0x180048c95  mov     rax, [rax+58h]
0x180048c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048c9e  mov     rdx, [rbp+2C0h+var_230]
0x180048ca5  lea     rcx, [rbp+2C0h+var_228]
0x180048cac  call    ?GetDefaultSignedInAccount@Internal@System@Windows@@YA?AU?$pair@V?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@U_GUID@@@std@@_K@Z; Windows::System::Internal::GetDefaultSignedInAccount(unsigned __int64)
0x180048cb1  nop
0x180048cb2  xorps   xmm0, xmm0
0x180048cb5  movups  [rbp+2C0h+Buf2], xmm0
0x180048cbc  mov     ebx, 10h
0x180048cc1  mov     r8d, ebx; Size
0x180048cc4  lea     rdx, [rbp+2C0h+Buf2]; Buf2
0x180048ccb  lea     rcx, [rbp+2C0h+Buf1]; Buf1
0x180048cd2  call    memcmp_0
0x180048cd7  test    eax, eax
0x180048cd9  jnz     loc_180048F00
0x180048cdf  mov     [rbp+2C0h+var_2A8], r15
0x180048ce3  mov     rcx, [rbp+2C0h+var_290]
0x180048ce7  mov     rax, [rcx]
0x180048cea  mov     [rbp+2C0h+var_2A8], r15
0x180048cee  lea     rdx, [rbp+2C0h+var_2A8]
0x180048cf2  mov     rax, [rax+48h]
0x180048cf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048cfb  mov     rcx, [rsp+338h]; this
0x180048d03  test    eax, eax
0x180048d05  js      loc_180049451
0x180048d0b  lea     rcx, [rbp+2C0h+var_270]
0x180048d0f  call    ??$GetActivationFactory@UILocalUserImageProviderStatics@LocalUserImageProvider@Microsoft@@@wil@@YA?AV?$com_ptr_t@UILocalUserImageProviderStatics@LocalUserImageProvider@Microsoft@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Microsoft::LocalUserImageProvider::ILocalUserImageProviderStatics>(ushort const *)
0x180048d14  nop
0x180048d15  mov     rax, [r14+0F0h]
0x180048d1c  mov     [rbp+2C0h+hToken], rax
0x180048d20  mov     rax, [rbp+2C0h+var_2A8]
0x180048d24  mov     [rbp+2C0h+var_288], rax
0x180048d28  mov     rax, [r14+0D8h]
0x180048d2f  mov     [rbp+2C0h+var_278], rax
0x180048d33  lea     rax, [rbp+2C0h+hToken]
0x180048d37  mov     qword ptr [rsp+330h+var_310], rax; int
0x180048d3c  lea     r9, [rbp+2C0h+var_288]
0x180048d40  lea     r8, [rbp+2C0h+var_278]
0x180048d44  mov     rcx, [rbp+2C0h+var_270]
0x180048d48  call    ??$call_and_wait_for_completion@UILocalUserImageProviderStatics@LocalUserImageProvider@Microsoft@@PEAUHSTRING__@@PEAU4@PEAUIRandomAccessStreamReference@Streams@Storage@Windows@@PEAPEAUIAsyncAction@Foundation@8@$$ZPEAU4@PEAU4@PEAU5678@@wil@@YA?A_PPEAUILocalUserImageProviderStatics@LocalUserImageProvider@Microsoft@@P8123@EAAJPEAUHSTRING__@@1PEAUIRandomAccessStreamReference@Streams@Storage@Windows@@PEAPEAUIAsyncAction@Foundation@8@@Z$$QEAPEAU4@5$$QEAPEAU5678@@Z
0x180048d4d  nop
0x180048d4e  mov     [rbp+2C0h+var_2B8], r15
0x180048d52  mov     [rbp+2C0h+var_2A0], r15
0x180048d56  lea     rcx, [rbp+2C0h+var_2A0]
0x180048d5a  call    ??$GetStaticInstance@UIUserStaticsInternal@Implementation@Internal@System@Windows@@@StaticsCache@Internal@System@Windows@@SAJPEAPEAUIUserStaticsInternal@Implementation@123@K@Z; Windows::System::Internal::StaticsCache::GetStaticInstance<Windows::System::Internal::Implementation::IUserStaticsInternal>(Windows::System::Internal::Implementation::IUserStaticsInternal * *,ulong)
0x180048d5f  nop
0x180048d60  mov     rcx, [rbp+2C0h+var_2B8]
0x180048d64  mov     [rbp+2C0h+var_2B8], r15
0x180048d68  test    rcx, rcx
0x180048d6b  jz      short loc_180048D7A
0x180048d6d  mov     rax, [rcx]
0x180048d70  mov     rax, [rax+10h]
0x180048d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048d79  nop
0x180048d7a  lea     rcx, [rbp+2C0h+var_2B8]
0x180048d7e  call    ??$GetStaticInstance@UIUserManagerPrivate@Implementation@Internal@System@Windows@@@StaticsCache@Internal@System@Windows@@SAJPEAPEAUIUserManagerPrivate@Implementation@123@K@Z; Windows::System::Internal::StaticsCache::GetStaticInstance<Windows::System::Internal::Implementation::IUserManagerPrivate>(Windows::System::Internal::Implementation::IUserManagerPrivate * *,ulong)
0x180048d83  mov     [rbp+2C0h+var_2C0], r15b
0x180048d87  mov     qword ptr [rbp+2C0h+var_268], r15
0x180048d8b  mov     [rbp+2C0h+var_2BC], r15d
0x180048d8f  mov     dword ptr [rbp+2C0h+var_2B0], r15d
0x180048d93  mov     rcx, [rbp+2C0h+var_290]
0x180048d97  mov     rax, [rcx]
0x180048d9a  lea     rdx, [rbp+2C0h+var_2BC]
0x180048d9e  mov     rax, [rax+30h]
0x180048da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048da7  mov     rcx, [rsp+338h]; this
0x180048daf  test    eax, eax
0x180048db1  js      loc_180049464
0x180048db7  mov     rcx, [rbp+2C0h+var_290]
0x180048dbb  mov     rax, [rcx]
0x180048dbe  lea     rdx, [rbp+2C0h+var_2B0]
0x180048dc2  mov     rax, [rax+60h]
0x180048dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048dcb  mov     rcx, [rsp+338h]; this
0x180048dd3  test    eax, eax
0x180048dd5  js      loc_180049478
0x180048ddb  mov     rcx, [rbp+2C0h+var_2A0]
0x180048ddf  mov     rax, [rcx]
0x180048de2  lea     rdx, [rbp+2C0h+var_268]
0x180048de6  mov     qword ptr [rsp+330h+var_310], rdx; int
0x180048deb  lea     r9, [rbp+2C0h+var_2C0]
0x180048def  mov     r8d, dword ptr [rbp+2C0h+var_2B0]
0x180048df3  mov     edx, [rbp+2C0h+var_2BC]
0x180048df6  mov     rax, [rax+88h]
0x180048dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e02  mov     rcx, [rsp+338h]; this
0x180048e0a  test    eax, eax
0x180048e0c  js      loc_18004948C
0x180048e12  mov     rcx, [rbp+2C0h+var_2B8]
0x180048e16  mov     rax, [rcx]
0x180048e19  mov     rdx, [r14+0D0h]
0x180048e20  mov     rax, [rax+50h]
0x180048e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e29  mov     rcx, [rsp+338h]; this
0x180048e31  test    eax, eax
0x180048e33  js      loc_1800494A0
0x180048e39  mov     rcx, [rbp+2C0h+var_2A0]
0x180048e3d  mov     rax, [rcx]
0x180048e40  mov     r9, [r14+0D8h]
0x180048e47  mov     r8b, [rbp+2C0h+var_2C0]
0x180048e4b  mov     rdx, [r14+0D0h]
0x180048e52  mov     rax, [rax+80h]
0x180048e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e5e  mov     eax, cs:dword_180146228
0x180048e64  cmp     eax, 5
0x180048e67  jbe     short loc_180048EC3
0x180048e69  mov     rdx, 400000000000h
0x180048e73  lea     rcx, dword_180146228
0x180048e7a  call    _tlgKeywordOn
0x180048e7f  test    al, al
0x180048e81  jz      short loc_180048EC3
0x180048e83  xor     edx, edx; length
0x180048e85  mov     rcx, [r14+0D8h]; string
0x180048e8c  call    cs:__imp_WindowsGetStringRawBuffer
0x180048e92  mov     [rbp+2C0h+hToken], rax
0x180048e96  mov     [rbp+2C0h+var_288], 1000000h
0x180048e9e  lea     rax, [rbp+2C0h+hToken]
0x180048ea2  mov     [rsp+330h+var_308], rax
0x180048ea7  lea     rax, [rbp+2C0h+var_288]
0x180048eab  mov     qword ptr [rsp+330h+var_310], rax
0x180048eb0  lea     rdx, word_18012C83A
0x180048eb7  lea     rcx, dword_180146228
0x180048ebe  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x180048ec3  mov     [r14+0E0h], r15d
0x180048eca  lea     rcx, [rbp+2C0h+var_268]
0x180048ece  call    ??1?$com_ptr_t@VSetAutologonForUserAsyncOperation@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(void)
0x180048ed3  nop
0x180048ed4  lea     rcx, [rbp+2C0h+var_2B8]
0x180048ed8  call    ??1?$com_ptr_t@VSetAutologonForUserAsyncOperation@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(void)
0x180048edd  nop
0x180048ede  lea     rcx, [rbp+2C0h+var_2A0]
0x180048ee2  call    ??1?$com_ptr_t@VSetAutologonForUserAsyncOperation@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(void)
0x180048ee7  nop
0x180048ee8  lea     rcx, [rbp+2C0h+var_270]
0x180048eec  call    ??1?$com_ptr_t@VSetAutologonForUserAsyncOperation@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(void)
0x180048ef1  nop
0x180048ef2  lea     rcx, [rbp+2C0h+var_2A8]; this
0x180048ef6  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180048efb  jmp     loc_1800493E6
0x180048f00  mov     r8, rbx; Size
0x180048f03  lea     rdx, qword_180116AD8; Buf2
0x180048f0a  lea     rcx, [rbp+2C0h+Buf1]; Buf1
0x180048f11  call    memcmp_0
0x180048f16  test    eax, eax
0x180048f18  jz      short loc_180048F38
0x180048f1a  mov     r8, rbx; Size
0x180048f1d  lea     rdx, qword_180116AC8; Buf2
0x180048f24  lea     rcx, [rbp+2C0h+Buf1]; Buf1
0x180048f2b  call    memcmp_0
0x180048f30  test    eax, eax
0x180048f32  jnz     loc_1800493E6
0x180048f38  mov     rbx, [rbp+2C0h+var_228]
0x180048f3f  mov     qword ptr [rbp+2C0h+var_268], rbx
0x180048f43  test    rbx, rbx
0x180048f46  jz      short loc_180048F58
0x180048f48  mov     rax, [rbx]
0x180048f4b  mov     rcx, rbx
0x180048f4e  mov     rax, [rax+8]
0x180048f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048f57  nop
0x180048f58  mov     [rbp+2C0h+var_270], r15
0x180048f5c  lea     rdx, [rbp+2C0h+var_270]
0x180048f60  lea     rcx, [rbp+2C0h+var_268]
0x180048f64  call    ??$As@UIWebAccount2@Credentials@Security@Windows@@@?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccount2@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount2>>)
0x180048f69  mov     rcx, [rsp+338h]; this
0x180048f71  test    eax, eax
0x180048f73  js      loc_1800494B5
0x180048f79  mov     [rbp+2C0h+var_2A0], r15
0x180048f7d  mov     qword ptr [rbp+2C0h+Buf2], r15
0x180048f84  mov     [rbp+2C0h+var_1E8], r15
0x180048f8b  mov     r9d, 40h ; '@'; unsigned int
0x180048f91  lea     r8d, [r9+1]; unsigned int
0x180048f95  lea     rdx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x180048f9c  lea     rcx, [rbp+2C0h+hstringHeader]; hstringHeader
0x180048fa3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180048fa8  nop
0x180048fa9  mov     rdi, [rbp+2C0h+var_1E8]
0x180048fb0  lea     rcx, [rbp+2C0h+var_2A0]
0x180048fb4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048fb9  lea     r8, [rbp+2C0h+var_2A0]
0x180048fbd  lea     rdx, _GUID_78371994_f53b_489b_b66f_3acca8b88faa
0x180048fc4  mov     rcx, rdi
0x180048fc7  call    cs:__imp_RoGetActivationFactory
0x180048fcd  mov     rcx, [rsp+338h]; this
0x180048fd5  test    eax, eax
0x180048fd7  js      loc_1800494CA
0x180048fdd  mov     [rbp+2C0h+var_2A8], r15
0x180048fe1  mov     rsi, [r14+0F0h]
0x180048fe8  mov     rax, [rsi]
0x180048feb  mov     rdi, [rax+30h]
0x180048fef  lea     rcx, [rbp+2C0h+var_2A8]
0x180048ff3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048ff8  lea     rdx, [rbp+2C0h+var_2A8]
0x180048ffc  mov     rcx, rsi
0x180048fff  mov     rax, rdi
0x180049002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049007  mov     rcx, [rsp+338h]; this
0x18004900f  test    eax, eax
0x180049011  js      loc_1800494DF
0x180049017  mov     [rbp+2C0h+var_288], r15
0x18004901b  lea     rdx, [rbp+2C0h+var_288]
0x18004901f  mov     rcx, [rbp+2C0h+var_2A8]
0x180049023  call    ??$BlockOnCompletionAndGetResults@PEAUIRandomAccessStreamWithContentType@Streams@Storage@Windows@@U1234@@@YAJPEAU?$IAsyncOperation@PEAUIRandomAccessStreamWithContentType@Streams@Storage@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIRandomAccessStreamWithContentType@Streams@Storage@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Storage::Streams::IRandomAccessStreamWithContentType *,Windows::Storage::Streams::IRandomAccessStreamWithContentType>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStreamWithContentType *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStreamWithContentType>>,tagCOWAIT_FLAGS,void *)
0x180049028  mov     rcx, [rsp+338h]; this
0x180049030  test    eax, eax
0x180049032  js      loc_1800494F4
0x180049038  mov     [rbp+2C0h+var_278], r15
0x18004903c  lea     rdx, [rbp+2C0h+var_278]
0x180049040  lea     rcx, [rbp+2C0h+var_288]
0x180049044  call    ??$As@UIRandomAccessStream@Streams@Storage@Windows@@@?$ComPtr@UIRandomAccessStreamWithContentType@Streams@Storage@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIRandomAccessStream@Streams@Storage@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStreamWithContentType>::As<Windows::Storage::Streams::IRandomAccessStream>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStream>>)
0x180049049  mov     rcx, [rsp+338h]; this
0x180049051  test    eax, eax
0x180049053  js      loc_180049509
0x180049059  mov     [rbp+2C0h+var_2B8], r15
0x18004905d  mov     [rbp+2C0h+var_298], r15
0x180049061  mov     [rbp+2C0h+hToken], r15
0x180049065  mov     rcx, [rbp+2C0h+var_290]
0x180049069  mov     rax, [rcx]
0x18004906c  lea     rdx, [rbp+2C0h+hToken]
0x180049070  mov     rax, [rax+50h]
0x180049074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049079  mov     rcx, [rsp+338h]; this
0x180049081  test    eax, eax
0x180049083  js      loc_18004951E
0x180049089  mov     rcx, [rbp+2C0h+hToken]; hToken
0x18004908d  call    cs:__imp_ImpersonateLoggedOnUser
0x180049093  mov     rcx, [rsp+338h]; this
0x18004909b  test    eax, eax
0x18004909d  jz      loc_180049532
0x1800490a3  mov     [rbp+2C0h+var_2BF], 1
0x1800490a7  mov     rcx, [rbp+2C0h+var_2A0]
0x1800490ab  mov     rax, [rcx]
0x1800490ae  lea     rdx, [rbp+2C0h+var_2B8]
0x1800490b2  mov     [rsp+330h+var_308], rdx
0x1800490b7  mov     edx, [r14+0E8h]
0x1800490be  mov     [rsp+330h+var_310], edx; int
0x1800490c2  mov     r9, [r14+0D8h]
0x1800490c9  mov     r8, [rbp+2C0h+var_278]
0x1800490cd  mov     rdx, rbx
0x1800490d0  mov     rax, [rax+30h]
0x1800490d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800490d9  mov     rcx, [rsp+338h]; this
0x1800490e1  test    eax, eax
0x1800490e3  js      loc_180049544
0x1800490e9  mov     rbx, [rbp+2C0h+var_2B8]
0x1800490ed  mov     rcx, rbx
0x1800490f0  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUpdateWebAccountPictureResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUpdateWebAccountPictureResult@Web@Authentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUpdateWebAccountPictureResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::UpdateWebAccountPictureResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::UpdateWebAccountPictureResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::UpdateWebAccountPictureResult *> *,tagCOWAIT_FLAGS,void *)
0x1800490f5  test    eax, eax
0x1800490f7  js      short loc_18004910C
0x1800490f9  mov     rax, [rbx]
  ... truncated ...
```
