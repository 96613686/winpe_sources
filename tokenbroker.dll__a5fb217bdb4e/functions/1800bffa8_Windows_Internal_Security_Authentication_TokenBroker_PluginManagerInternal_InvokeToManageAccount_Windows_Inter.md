# Windows::Internal::Security::Authentication::TokenBroker::PluginManagerInternal::InvokeToManageAccount(Windows::Internal::Security::Authentication::Web::CallerContext *,Windows::Security::Credentials::IWebAccount *,uint,bool,Windows::Storage::Streams::IRandomAccessStream *,HSTRING__ *,IWaitForUIActivationOperation * *)

- ea: `0x1800bffa8`
- end: `0x1800c08f4`
- name: `?InvokeToManageAccount@PluginManagerInternal@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAVCallerContext@Web@3456@PEAUIWebAccount@Credentials@46@I_NPEAUIRandomAccessStream@Streams@Storage@6@PEAUHSTRING__@@PEAPEAUIWaitForUIActivationOperation@@@Z`
- size: `2380`
- prototype: `__int64 __fastcall(struct Windows::Internal::Security::Authentication::Web::CallerContext *, struct Windows::Security::Credentials::IWebAccount *, unsigned int, bool, struct Windows::Storage::Streams::IRandomAccessStream *, HSTRING, struct IWaitForUIActivationOperation **)`
- caller_count: `3`
- callee_count: `22`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800ba774`
- `0x1800ba868`
- `0x1800e2a1c`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x180010a70`
- `0x180040980`
- `0x1800412e0`
- `0x18004c014`
- `0x180081df0`
- `0x180083a54`
- `0x18008e690`
- `0x18008fccc`
- `0x18009b954`
- `0x1800a2cb4`
- `0x1800a2d04`
- `0x1800a2df4`
- `0x1800a2e44`
- `0x1800a3e98`
- `0x1800a3edc`
- `0x1800b3c18`
- `0x1800b7318`
- `0x1800bffa8`
- `0x1800e3f2c`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c007a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c007a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c010d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0122`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c018d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c055c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0583`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0594`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0878`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c089f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c08b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c010d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0122`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c018d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c055c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0583`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0594`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0878`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c089f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c08b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800c0060`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800c0060`
- `ext-ms-win-webtokenrequest-win32-l1-1-0!InvokePluginAsWin32` at `0x1800c04cd`
- `ext-ms-win-webtokenrequest-win32-l1-1-0!InvokePluginAsWin32` at `0x1800c04cd`

## string_xrefs

- `0x1800c0020`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800c00dc`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800c016e`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800c01e9`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800c02e2`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800c0331`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800c036f`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800c03e7`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800c0429`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800c0469`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800c04e2`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800c05eb`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800c05b8`: `Windows.Internal.PlatformExtensions.TokenBrokerExperience`
- `0x1800c06e7`: `Windows.Internal.PlatformExtensions.TokenBrokerExperience`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::PluginManagerInternal::InvokeToManageAccount(
        struct Windows::Internal::Security::Authentication::Web::CallerContext *a1,
        struct Windows::Security::Credentials::IWebAccount *a2,
        int a3,
        char a4,
        struct Windows::Storage::Streams::IRandomAccessStream *a5,
        HSTRING a6,
        struct IWaitForUIActivationOperation **a7)
{
  __int64 v8; // r15
  struct IWaitForUIActivationOperation **v11; // r12
  char v12; // si
  __int64 (__fastcall *v13)(struct Windows::Security::Credentials::IWebAccount *, struct Windows::Security::Credentials::IWebAccountProvider **); // rbx
  int v14; // eax
  unsigned int ExtensionForProvider; // ebx
  int v16; // r9d
  PCWSTR StringRawBuffer; // rax
  int v18; // eax
  __int64 v19; // rdx
  struct Windows::Internal::String *v20; // r8
  int AumId; // eax
  __int64 WindowSizeForWebAccountProviderOperation; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rcx
  int v28; // eax
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, __int64 *); // rbx
  int v33; // eax
  int v34; // eax
  int v35; // eax
  HSTRING v36; // rbx
  int v37; // edi
  __int64 v38; // rdx
  int v39; // eax
  __int64 v40; // rdx
  __int64 v41; // r9
  __int64 *v42; // rdi
  __int64 v43; // rax
  bool v44; // zf
  __int64 v45; // rsi
  __int64 (__fastcall *v46)(__int64 *, HSTRING *, HSTRING, __int64); // r14
  __int64 (__fastcall *v47)(__int64 *, HSTRING *, HSTRING, __int64); // r14
  __int64 *v48; // rdi
  __int64 v49; // rax
  __int64 v50; // rsi
  __int64 (__fastcall *v51)(__int64 *, HSTRING *, HSTRING, __int64); // r14
  __int64 (__fastcall *v52)(__int64 *, HSTRING *, HSTRING, __int64); // r14
  struct IWaitForUIActivationOperation *v53; // rax
  int v55; // [rsp+28h] [rbp-E0h]
  __int64 v56; // [rsp+48h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+50h] [rbp-B8h] BYREF
  int v58[2]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v59; // [rsp+60h] [rbp-A8h] BYREF
  struct Windows::Security::Credentials::IWebAccount *v60; // [rsp+68h] [rbp-A0h] BYREF
  HSTRING v61; // [rsp+70h] [rbp-98h] BYREF
  __int64 v62; // [rsp+78h] [rbp-90h] BYREF
  __int64 *v63; // [rsp+80h] [rbp-88h] BYREF
  HSTRING v64; // [rsp+88h] [rbp-80h] BYREF
  __int64 v65; // [rsp+90h] [rbp-78h] BYREF
  __int64 v66; // [rsp+98h] [rbp-70h] BYREF
  __int64 v67; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v68; // [rsp+A8h] [rbp-60h] BYREF
  struct IWaitForUIActivationOperation *v69; // [rsp+B0h] [rbp-58h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v70; // [rsp+B8h] [rbp-50h] BYREF
  int v71; // [rsp+C0h] [rbp-48h] BYREF
  _QWORD v72[3]; // [rsp+C8h] [rbp-40h] BYREF
  struct Windows::Security::Credentials::IWebAccount *v73; // [rsp+E0h] [rbp-28h] BYREF
  _QWORD v74[2]; // [rsp+E8h] [rbp-20h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+F8h] [rbp-10h] BYREF
  HSTRING *v76; // [rsp+110h] [rbp+8h]
  wil::details::in1diag3 *retaddr; // [rsp+180h] [rbp+78h]

  v8 = a3;
  v11 = a7;
  v12 = 0;
  v70 = 0;
  v13 = *(__int64 (__fastcall **)(struct Windows::Security::Credentials::IWebAccount *, struct Windows::Security::Credentials::IWebAccountProvider **))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
  v14 = v13(a2, &v70);
  ExtensionForProvider = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64E,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v14,
      v55);
    goto LABEL_94;
  }
  string = 0;
  (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *, HSTRING *))(*(_QWORD *)v70 + 48LL))(
    v70,
    &string);
  if ( (unsigned int)dword_180175000 > 5 )
  {
    if ( WindowsIsStringEmpty(string) )
      StringRawBuffer = L"null";
    else
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    *(_QWORD *)v58 = StringRawBuffer;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (unsigned int)&dword_180175000,
      (unsigned int)byte_18014EA5B,
      0,
      v16,
      (__int64)v58);
  }
  v61 = 0;
  v60 = a2;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v60);
  v59 = 0;
  v18 = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(
          &v60,
          &v59);
  ExtensionForProvider = v18;
  if ( v18 < 0 )
  {
    v19 = 1631;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v18,
      v55);
LABEL_11:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
    if ( v61 )
      WindowsDeleteString(v61);
    if ( string )
      WindowsDeleteString(string);
    goto LABEL_94;
  }
  v18 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v59 + 48LL))(v59, &v61);
  ExtensionForProvider = v18;
  if ( v18 < 0 )
  {
    v19 = 1632;
    goto LABEL_10;
  }
  v64 = 0;
  AumId = Windows::Internal::Security::Authentication::Web::GetAumId(
            v70,
            (struct Windows::Security::Credentials::IWebAccountProvider *)&v64,
            v20);
  ExtensionForProvider = AumId;
  if ( AumId < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x664,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)AumId,
      v55);
    goto LABEL_19;
  }
  v62 = 0;
  v58[0] = (int)v70;
  LOBYTE(v58[1]) = 0;
  *(_WORD *)((char *)&v58[1] + 1) = *(_WORD *)((char *)&v70 + 5);
  HIBYTE(v58[1]) = HIBYTE(v70);
  ExtensionForProvider = Windows::Internal::Security::Authentication::TokenBroker::SystemExtension::FindExtensionForProvider(
                           (__int64 (__fastcall ***)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *))v70,
                           (__int64)&v62,
                           *(__int64 *)v58);
  if ( (int)(ExtensionForProvider + 0x80000000) >= 0 && ExtensionForProvider != -2147024894 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66B,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)ExtensionForProvider,
      v55);
LABEL_24:
    std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension>::~unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension>(&v62);
LABEL_19:
    if ( v64 )
      WindowsDeleteString(v64);
    goto LABEL_11;
  }
  if ( v62 )
  {
    WindowSizeForWebAccountProviderOperation = Windows::Internal::Security::Authentication::TokenBroker::SystemExtension::GetWindowSizeForWebAccountProviderOperation(
                                                 v62,
                                                 v74,
                                                 3);
    v72[1] = *(_QWORD *)WindowSizeForWebAccountProviderOperation;
    v12 = *(_BYTE *)(WindowSizeForWebAccountProviderOperation + 8);
  }
  *(_QWORD *)v58 = 0;
  v56 = 0;
  v71 = 3;
  if ( a4 )
  {
    v72[0] = a2;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
    hstringHeader.Reserved.Reserved1 = &v71;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = v72;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = &a5;
    v76 = &a6;
    v25 = Windows::Internal::ComTaskPool::_MakeAndInitializeOnSTAThread<Windows::Security::Authentication::Web::Provider::CWebAccountProviderActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,_lambda_6aba97d38aa6af56caca1a89944c6f86_>(
            v24,
            v23,
            &v56,
            &hstringHeader);
  }
  else
  {
    v74[0] = 0;
    v73 = a2;
    v72[0] = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
    hstringHeader.Reserved.Reserved1 = &v71;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = v72;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = &v73;
    v76 = (HSTRING *)v74;
    v25 = Windows::Internal::ComTaskPool::_MakeAndInitializeOnSTAThread<Windows::Security::Authentication::Web::Provider::CWebAccountProviderActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,_lambda_f570e3bbb038c7d48dd55e7fafb2e1c1_>(
            v27,
            v26,
            &v56,
            &hstringHeader);
  }
  ExtensionForProvider = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x68C,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v25,
      v55);
LABEL_32:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v58);
    goto LABEL_24;
  }
  v65 = 0;
  v28 = Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::IActivatedEventArgs>::As<Windows::ApplicationModel::Activation::IWebAccountProviderActivatedEventArgs>(
          &v56,
          &v65);
  ExtensionForProvider = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x68F,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v28,
      v55);
LABEL_35:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
    goto LABEL_32;
  }
  v67 = 0;
  v29 = Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::IActivatedEventArgs>::As<Windows::ApplicationModel::Activation::IActivatedEventArgsInternal>(
          &v56,
          &v67);
  ExtensionForProvider = v29;
  if ( v29 < 0 )
  {
    v30 = 1682;
LABEL_38:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v30,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v29,
      v55);
LABEL_39:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
    goto LABEL_35;
  }
  v29 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v67 + 56LL))(v67, *((_QWORD *)a1 + 1));
  ExtensionForProvider = v29;
  if ( v29 < 0 )
  {
    v30 = 1683;
    goto LABEL_38;
  }
  v68 = 0;
  v31 = v65;
  v32 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v65 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
  v33 = v32(v31, &v68);
  ExtensionForProvider = v33;
  if ( v33 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x696,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v33,
      v55);
LABEL_44:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
    goto LABEL_39;
  }
  v69 = 0;
  v34 = Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Provider::IWebAccountProviderOperation>::As<IWaitForUIActivationOperation>(
          &v68,
          &v69);
  ExtensionForProvider = v34;
  if ( v34 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x699,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v34,
      v55);
LABEL_47:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
    goto LABEL_44;
  }
  v66 = 0;
  v35 = Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::IActivatedEventArgs>::As<IInspectable>(&v56, &v66);
  ExtensionForProvider = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x69D,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v35,
      v55);
LABEL_50:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
    goto LABEL_47;
  }
  v63 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WAMPluginWin32Activation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WAMPluginWin32Activation>::GetImpl'::`2'::impl) )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
    v76 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.PlatformExtensions.TokenBrokerExperience",
      0x3Au,
      0x39u);
    v39 = Windows::Internal::PlatformExtensions::TryActivateContractExtension<Windows::Internal::PlatformExtensions::ITokenBrokerExperienceContract>(
            v76,
            &v63,
            (unsigned int)v8);
    ExtensionForProvider = v39;
    if ( v39 < 0 )
    {
      v40 = 1738;
      goto LABEL_64;
    }
    v48 = v63;
    if ( v63 )
    {
      v49 = *v63;
      v36 = v64;
      v76 = 0;
      v44 = v12 == 0;
      v50 = v66;
      if ( v44 )
      {
        v52 = *(__int64 (__fastcall **)(__int64 *, HSTRING *, HSTRING, __int64))(v49 + 48);
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.WebAccountProvider",
          0x1Bu,
          0x1Au);
        v55 = v8;
        v37 = v52(v48, v76, v36, v50);
        if ( v37 < 0 )
        {
          v38 = 1756;
          goto LABEL_55;
        }
      }
      else
      {
        v51 = *(__int64 (__fastcall **)(__int64 *, HSTRING *, HSTRING, __int64))(v49 + 56);
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.WebAccountProvider",
          0x1Bu,
          0x1Au);
        v55 = v8;
        v37 = v51(v48, v76, v36, v50);
        if ( v37 < 0 )
        {
          v38 = 1748;
          goto LABEL_55;
        }
      }
      goto LABEL_83;
    }
    v40 = 1739;
LABEL_77:
    ExtensionForProvider = -2147467263;
    v41 = 2147500033LL;
    goto LABEL_65;
  }
  if ( (unsigned __int8)IsInvokePluginAsWin32Present() )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
    v36 = v64;
    v37 = InvokePluginAsWin32(v64, v66, v8, &v63);
    if ( v37 < 0 )
    {
      v38 = 1704;
LABEL_55:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v38,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
        (const char *)(unsigned int)v37,
        v55);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v58);
      std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension>::~unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension>(&v62);
      if ( v36 )
        WindowsDeleteString(v36);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
      if ( v61 )
        WindowsDeleteString(v61);
      if ( string )
        WindowsDeleteString(string);
      ExtensionForProvider = v37;
      goto LABEL_94;
    }
    goto LABEL_83;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
  v76 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.PlatformExtensions.TokenBrokerExperience",
    0x3Au,
    0x39u);
  v39 = Windows::Internal::PlatformExtensions::TryActivateContractExtension<Windows::Internal::PlatformExtensions::ITokenBrokerExperienceContract>(
          v76,
          &v63,
          (unsigned int)v8);
  ExtensionForProvider = v39;
  if ( v39 < 0 )
  {
    v40 = 1711;
LABEL_64:
    v41 = (unsigned int)v39;
LABEL_65:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v40,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)v41,
      v55);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
    goto LABEL_50;
  }
  v42 = v63;
  if ( !v63 )
  {
    v40 = 1712;
    goto LABEL_77;
  }
  v43 = *v63;
  v36 = v64;
  v76 = 0;
  v44 = v12 == 0;
  v45 = v66;
  if ( v44 )
  {
    v47 = *(__int64 (__fastcall **)(__int64 *, HSTRING *, HSTRING, __int64))(v43 + 48);
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.WebAccountProvider",
      0x1Bu,
      0x1Au);
    v55 = v8;
    v37 = v47(v42, v76, v36, v45);
    if ( v37 < 0 )
    {
      v38 = 1729;
      goto LABEL_55;
    }
  }
  else
  {
    v46 = *(__int64 (__fastcall **)(__int64 *, HSTRING *, HSTRING, __int64))(v43 + 56);
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.WebAccountProvider",
      0x1Bu,
      0x1Au);
    v55 = v8;
    v37 = v46(v42, v76, v36, v45);
    if ( v37 < 0 )
    {
      v38 = 1721;
      goto LABEL_55;
    }
  }
LABEL_83:
  if ( v11 )
  {
    v53 = v69;
    v69 = 0;
    *v11 = v53;
  }
  v37 = (*(__int64 (__fastcall **)(__int64 *))(*v63 + 64))(v63);
  if ( v37 < 0 )
  {
    v38 = 1767;
    goto LABEL_55;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v58);
  std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension>::~unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension>(&v62);
  if ( v36 )
    WindowsDeleteString(v36);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
  if ( v61 )
    WindowsDeleteString(v61);
  if ( string )
    WindowsDeleteString(string);
  ExtensionForProvider = 0;
LABEL_94:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
  return ExtensionForProvider;
}

```

## disassembly

```asm
0x1800bffa8  mov     rax, rsp
0x1800bffab  mov     [rax+20h], rbx
0x1800bffaf  push    rbp
0x1800bffb0  push    rsi
0x1800bffb1  push    rdi
0x1800bffb2  push    r12
0x1800bffb4  push    r13
0x1800bffb6  push    r14
0x1800bffb8  push    r15
0x1800bffba  lea     rbp, [rax-78h]
0x1800bffbe  sub     rsp, 140h
0x1800bffc5  movaps  xmmword ptr [rax-48h], xmm6
0x1800bffc9  movaps  xmmword ptr [rax-58h], xmm7
0x1800bffcd  mov     rax, cs:__security_cookie
0x1800bffd4  xor     rax, rsp
0x1800bffd7  mov     [rbp+70h+var_60], rax
0x1800bffdb  mov     r14b, r9b
0x1800bffde  movsxd  r15, r8d
0x1800bffe1  mov     rdi, rdx
0x1800bffe4  mov     r13, rcx
0x1800bffe7  mov     r12, [rbp+70h+arg_30]
0x1800bffee  xor     esi, esi
0x1800bfff0  mov     [rbp+70h+var_C0], rsi
0x1800bfff4  mov     rax, [rdx]
0x1800bfff7  mov     rbx, [rax+30h]
0x1800bfffb  lea     rcx, [rbp+70h+var_C0]
0x1800bffff  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c0004  lea     rdx, [rbp+70h+var_C0]
0x1800c0008  mov     rcx, rdi
0x1800c000b  mov     rax, rbx
0x1800c000e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0013  mov     ebx, eax
0x1800c0015  test    eax, eax
0x1800c0017  jns     short loc_1800C0036
0x1800c0019  mov     rcx, [rbp+78h]; this
0x1800c001d  mov     r9d, eax; char *
0x1800c0020  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800c0027  mov     edx, 64Eh; void *
0x1800c002c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0031  jmp     loc_1800C08B8
0x1800c0036  mov     [rsp+170h+string], rsi
0x1800c003b  mov     rcx, [rbp+70h+var_C0]
0x1800c003f  mov     rax, [rcx]
0x1800c0042  lea     rdx, [rsp+170h+string]
0x1800c0047  mov     rax, [rax+30h]
0x1800c004b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0050  mov     eax, cs:dword_180175000
0x1800c0056  cmp     eax, 5
0x1800c0059  jbe     short loc_1800C00A5
0x1800c005b  mov     rcx, [rsp+170h+string]; string
0x1800c0060  call    cs:__imp_WindowsIsStringEmpty
0x1800c0066  test    eax, eax
0x1800c0068  jz      short loc_1800C0073
0x1800c006a  lea     rax, aNull; "null"
0x1800c0071  jmp     short loc_1800C0080
0x1800c0073  xor     edx, edx; length
0x1800c0075  mov     rcx, [rsp+170h+string]; string
0x1800c007a  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c0080  mov     qword ptr [rsp+170h+var_120], rax
0x1800c0085  lea     rax, [rsp+170h+var_120]
0x1800c008a  mov     qword ptr [rsp+170h+var_150], rax; int
0x1800c008f  xor     r8d, r8d
0x1800c0092  lea     rdx, byte_18014EA5B
0x1800c0099  lea     rcx, dword_180175000
0x1800c00a0  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800c00a5  mov     [rsp+170h+var_108], rsi
0x1800c00aa  mov     [rsp+170h+var_110], rdi
0x1800c00af  lea     rcx, [rsp+170h+var_110]
0x1800c00b4  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800c00b9  nop
0x1800c00ba  mov     [rsp+170h+var_118], rsi
0x1800c00bf  lea     rdx, [rsp+170h+var_118]
0x1800c00c4  lea     rcx, [rsp+170h+var_110]
0x1800c00c9  call    ??$As@UIWebAccount2@Credentials@Security@Windows@@@?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccount2@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount2>>)
0x1800c00ce  mov     ebx, eax
0x1800c00d0  test    eax, eax
0x1800c00d2  jns     short loc_1800C012D
0x1800c00d4  mov     edx, 65Fh; void *
0x1800c00d9  mov     r9d, eax; char *
0x1800c00dc  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800c00e3  mov     rcx, [rbp+78h]; this
0x1800c00e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c00ec  nop
0x1800c00ed  lea     rcx, [rsp+170h+var_118]
0x1800c00f2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c00f7  nop
0x1800c00f8  lea     rcx, [rsp+170h+var_110]
0x1800c00fd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c0102  nop
0x1800c0103  mov     rcx, [rsp+170h+var_108]; string
0x1800c0108  test    rcx, rcx
0x1800c010b  jz      short loc_1800C0114
0x1800c010d  call    cs:__imp_WindowsDeleteString
0x1800c0113  nop
0x1800c0114  mov     rcx, [rsp+170h+string]; string
0x1800c0119  test    rcx, rcx
0x1800c011c  jz      loc_1800C08B8
0x1800c0122  call    cs:__imp_WindowsDeleteString
0x1800c0128  jmp     loc_1800C08B8
0x1800c012d  mov     rcx, [rsp+170h+var_118]
0x1800c0132  mov     rax, [rcx]
0x1800c0135  lea     rdx, [rsp+170h+var_108]
0x1800c013a  mov     rax, [rax+30h]
0x1800c013e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0143  mov     ebx, eax
0x1800c0145  test    eax, eax
0x1800c0147  jns     short loc_1800C0150
0x1800c0149  mov     edx, 660h
0x1800c014e  jmp     short loc_1800C00D9
0x1800c0150  mov     [rbp+70h+var_F0], rsi
0x1800c0154  lea     rdx, [rbp+70h+var_F0]; struct Windows::Security::Credentials::IWebAccountProvider *
0x1800c0158  mov     rcx, [rbp+70h+var_C0]; this
0x1800c015c  call    ?GetAumId@Web@Authentication@Security@Internal@Windows@@YAJPEAUIWebAccountProvider@Credentials@35@AEAVString@45@@Z; Windows::Internal::Security::Authentication::Web::GetAumId(Windows::Security::Credentials::IWebAccountProvider *,Windows::Internal::String &)
0x1800c0161  mov     ebx, eax
0x1800c0163  test    eax, eax
0x1800c0165  jns     short loc_1800C0198
0x1800c0167  mov     rcx, [rbp+78h]; this
0x1800c016b  mov     r9d, eax; char *
0x1800c016e  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800c0175  mov     edx, 664h; void *
0x1800c017a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c017f  nop
0x1800c0180  mov     rcx, [rbp+70h+var_F0]; string
0x1800c0184  test    rcx, rcx
0x1800c0187  jz      loc_1800C00ED
0x1800c018d  call    cs:__imp_WindowsDeleteString
0x1800c0193  jmp     loc_1800C00ED
0x1800c0198  mov     [rsp+170h+var_100], rsi
0x1800c019d  mov     eax, dword ptr [rbp+70h+var_C0]
0x1800c01a0  mov     [rsp+170h+var_120], eax
0x1800c01a4  mov     byte ptr [rsp+170h+var_120+4], sil
0x1800c01a9  movzx   eax, word ptr [rbp+70h+var_C0+5]
0x1800c01ad  mov     word ptr [rsp+170h+var_120+5], ax
0x1800c01b2  mov     al, byte ptr [rbp+70h+var_C0+7]
0x1800c01b5  mov     byte ptr [rsp+170h+var_120+7], al
0x1800c01b9  mov     r8, qword ptr [rsp+170h+var_120]
0x1800c01be  lea     rdx, [rsp+170h+var_100]
0x1800c01c3  mov     rcx, [rbp+70h+var_C0]; struct Windows::Security::Credentials::IWebAccountProvider *
0x1800c01c7  call    ?FindExtensionForProvider@SystemExtension@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAUIWebAccountProvider@Credentials@46@AEAV?$unique_ptr@VSystemExtension@TokenBroker@Authentication@Security@Internal@Windows@@U?$default_delete@VSystemExtension@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@std@@V?$optional@W4ExtensionType@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@Z; Windows::Internal::Security::Authentication::TokenBroker::SystemExtension::FindExtensionForProvider(Windows::Security::Credentials::IWebAccountProvider *,std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension> &,std::optional<Windows::Internal::Security::Authentication::TokenBroker::ExtensionType>)
0x1800c01cc  mov     ebx, eax
0x1800c01ce  mov     eax, 80000000h
0x1800c01d3  lea     ecx, [rbx+rax]
0x1800c01d6  test    eax, ecx
0x1800c01d8  jnz     short loc_1800C020A
0x1800c01da  cmp     ebx, 80070002h
0x1800c01e0  jz      short loc_1800C020A
0x1800c01e2  mov     rcx, [rbp+78h]; this
0x1800c01e6  mov     r9d, ebx; char *
0x1800c01e9  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800c01f0  mov     edx, 66Bh; void *
0x1800c01f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c01fa  nop
0x1800c01fb  lea     rcx, [rsp+170h+var_100]
0x1800c0200  call    ??1?$unique_ptr@VSystemExtension@TokenBroker@Authentication@Security@Internal@Windows@@U?$default_delete@VSystemExtension@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension>::~unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension>(void)
0x1800c0205  jmp     loc_1800C0180
0x1800c020a  mov     ebx, 3
0x1800c020f  mov     rcx, [rsp+170h+var_100]
0x1800c0214  test    rcx, rcx
0x1800c0217  jz      short loc_1800C0230
0x1800c0219  mov     r8d, ebx
0x1800c021c  lea     rdx, [rbp+70h+var_90]
0x1800c0220  call    ?GetWindowSizeForWebAccountProviderOperation@SystemExtension@TokenBroker@Authentication@Security@Internal@Windows@@QEAA?AV?$optional@USize@Foundation@Windows@@@std@@W4WebAccountProviderOperationKind@Provider@Web@346@@Z; Windows::Internal::Security::Authentication::TokenBroker::SystemExtension::GetWindowSizeForWebAccountProviderOperation(Windows::Security::Authentication::Web::Provider::WebAccountProviderOperationKind)
0x1800c0225  mov     rcx, [rax]
0x1800c0228  mov     [rbp+70h+var_A8], rcx
0x1800c022c  mov     sil, [rax+8]
0x1800c0230  mov     qword ptr [rsp+170h+var_120], 0
0x1800c0239  mov     [rsp+170h+var_130], 0
0x1800c0242  mov     [rbp+70h+var_B8], ebx
0x1800c0245  lea     rcx, [rsp+170h+var_130]
0x1800c024a  test    r14b, r14b
0x1800c024d  jz      short loc_1800C028E
0x1800c024f  mov     [rbp+70h+var_B0], rdi
0x1800c0253  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c0258  lea     rax, [rbp+70h+var_B8]
0x1800c025c  mov     qword ptr [rbp+70h+hstringHeader.Reserved], rax
0x1800c0260  lea     rax, [rbp+70h+var_B0]
0x1800c0264  mov     qword ptr [rbp+70h+hstringHeader.Reserved+8], rax
0x1800c0268  lea     rax, [rbp+70h+arg_20]
0x1800c026f  mov     qword ptr [rbp+70h+hstringHeader.Reserved+10h], rax
0x1800c0273  lea     rax, [rbp+70h+arg_28]
0x1800c027a  mov     [rbp+70h+var_68], rax
0x1800c027e  lea     r9, [rbp+70h+hstringHeader]
0x1800c0282  lea     r8, [rsp+170h+var_130]
0x1800c0287  call    ??$_MakeAndInitializeOnSTAThread@VCWebAccountProviderActivatedEventArgs@Provider@Web@Authentication@Security@Windows@@UIActivatedEventArgs@Activation@ApplicationModel@6@V_lambda_6aba97d38aa6af56caca1a89944c6f86_@@@ComTaskPool@Internal@Windows@@CAJW4TaskOptions@12@KPEAPEAUIActivatedEventArgs@Activation@ApplicationModel@2@AEBV_lambda_6aba97d38aa6af56caca1a89944c6f86_@@@Z; Windows::Internal::ComTaskPool::_MakeAndInitializeOnSTAThread<Windows::Security::Authentication::Web::Provider::CWebAccountProviderActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,_lambda_6aba97d38aa6af56caca1a89944c6f86_>(Windows::Internal::TaskOptions,ulong,Windows::ApplicationModel::Activation::IActivatedEventArgs * *,_lambda_6aba97d38aa6af56caca1a89944c6f86_ const &)
0x1800c028c  jmp     short loc_1800C02D5
0x1800c028e  mov     [rbp+70h+var_90], 0
0x1800c0296  mov     [rbp+70h+var_98], rdi
0x1800c029a  mov     [rbp+70h+var_B0], 0
0x1800c02a2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c02a7  lea     rax, [rbp+70h+var_B8]
0x1800c02ab  mov     qword ptr [rbp+70h+hstringHeader.Reserved], rax
0x1800c02af  lea     rax, [rbp+70h+var_B0]
0x1800c02b3  mov     qword ptr [rbp+70h+hstringHeader.Reserved+8], rax
0x1800c02b7  lea     rax, [rbp+70h+var_98]
0x1800c02bb  mov     qword ptr [rbp+70h+hstringHeader.Reserved+10h], rax
0x1800c02bf  lea     rax, [rbp+70h+var_90]
0x1800c02c3  mov     [rbp+70h+var_68], rax
0x1800c02c7  lea     r9, [rbp+70h+hstringHeader]
0x1800c02cb  lea     r8, [rsp+170h+var_130]
0x1800c02d0  call    ??$_MakeAndInitializeOnSTAThread@VCWebAccountProviderActivatedEventArgs@Provider@Web@Authentication@Security@Windows@@UIActivatedEventArgs@Activation@ApplicationModel@6@V_lambda_f570e3bbb038c7d48dd55e7fafb2e1c1_@@@ComTaskPool@Internal@Windows@@CAJW4TaskOptions@12@KPEAPEAUIActivatedEventArgs@Activation@ApplicationModel@2@AEBV_lambda_f570e3bbb038c7d48dd55e7fafb2e1c1_@@@Z; Windows::Internal::ComTaskPool::_MakeAndInitializeOnSTAThread<Windows::Security::Authentication::Web::Provider::CWebAccountProviderActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,_lambda_f570e3bbb038c7d48dd55e7fafb2e1c1_>(Windows::Internal::TaskOptions,ulong,Windows::ApplicationModel::Activation::IActivatedEventArgs * *,_lambda_f570e3bbb038c7d48dd55e7fafb2e1c1_ const &)
0x1800c02d5  mov     ebx, eax
0x1800c02d7  test    eax, eax
0x1800c02d9  jns     short loc_1800C030E
0x1800c02db  mov     rcx, [rbp+78h]; this
0x1800c02df  mov     r9d, eax; char *
0x1800c02e2  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800c02e9  mov     edx, 68Ch; void *
0x1800c02ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c02f3  nop
0x1800c02f4  lea     rcx, [rsp+170h+var_130]
0x1800c02f9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c02fe  nop
0x1800c02ff  lea     rcx, [rsp+170h+var_120]
0x1800c0304  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c0309  jmp     loc_1800C01FB
0x1800c030e  mov     [rbp+70h+var_E8], 0
0x1800c0316  lea     rdx, [rbp+70h+var_E8]
0x1800c031a  lea     rcx, [rsp+170h+var_130]
0x1800c031f  call    ??$As@UIWebAccountProviderActivatedEventArgs@Activation@ApplicationModel@Windows@@@?$ComPtr@UIActivatedEventArgs@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccountProviderActivatedEventArgs@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::IActivatedEventArgs>::As<Windows::ApplicationModel::Activation::IWebAccountProviderActivatedEventArgs>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::IWebAccountProviderActivatedEventArgs>>)
0x1800c0324  mov     ebx, eax
0x1800c0326  test    eax, eax
0x1800c0328  jns     short loc_1800C034E
0x1800c032a  mov     rcx, [rbp+78h]; this
0x1800c032e  mov     r9d, eax; char *
0x1800c0331  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800c0338  mov     edx, 68Fh; void *
0x1800c033d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0342  nop
0x1800c0343  lea     rcx, [rbp+70h+var_E8]
0x1800c0347  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c034c  jmp     short loc_1800C02F4
0x1800c034e  mov     [rbp+70h+var_D8], 0
0x1800c0356  lea     rdx, [rbp+70h+var_D8]
0x1800c035a  lea     rcx, [rsp+170h+var_130]
0x1800c035f  call    ??$As@UIActivatedEventArgsInternal@Activation@ApplicationModel@Windows@@@?$ComPtr@UIActivatedEventArgs@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIActivatedEventArgsInternal@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::IActivatedEventArgs>::As<Windows::ApplicationModel::Activation::IActivatedEventArgsInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::IActivatedEventArgsInternal>>)
0x1800c0364  mov     ebx, eax
0x1800c0366  test    eax, eax
0x1800c0368  jns     short loc_1800C038E
0x1800c036a  mov     edx, 692h; void *
0x1800c036f  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800c0376  mov     r9d, eax; char *
0x1800c0379  mov     rcx, [rbp+78h]; this
0x1800c037d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0382  nop
0x1800c0383  lea     rcx, [rbp+70h+var_D8]
0x1800c0387  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c038c  jmp     short loc_1800C0343
0x1800c038e  mov     rcx, [rbp+70h+var_D8]
0x1800c0392  mov     rax, [rcx]
0x1800c0395  mov     rdx, [r13+8]
0x1800c0399  mov     rax, [rax+38h]
0x1800c039d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c03a2  mov     ebx, eax
0x1800c03a4  test    eax, eax
0x1800c03a6  jns     short loc_1800C03AF
0x1800c03a8  mov     edx, 693h
0x1800c03ad  jmp     short loc_1800C036F
0x1800c03af  mov     [rbp+70h+var_D0], 0
0x1800c03b7  mov     rdi, [rbp+70h+var_E8]
0x1800c03bb  mov     rax, [rdi]
0x1800c03be  mov     rbx, [rax+30h]
0x1800c03c2  lea     rcx, [rbp+70h+var_D0]
0x1800c03c6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c03cb  lea     rdx, [rbp+70h+var_D0]
0x1800c03cf  mov     rcx, rdi
0x1800c03d2  mov     rax, rbx
0x1800c03d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c03da  mov     ebx, eax
0x1800c03dc  test    eax, eax
0x1800c03de  jns     short loc_1800C0407
0x1800c03e0  mov     rcx, [rbp+78h]; this
0x1800c03e4  mov     r9d, eax; char *
0x1800c03e7  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800c03ee  mov     edx, 696h; void *
0x1800c03f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c03f8  nop
0x1800c03f9  lea     rcx, [rbp+70h+var_D0]
0x1800c03fd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c0402  jmp     loc_1800C0383
0x1800c0407  mov     [rbp+70h+var_C8], 0
0x1800c040f  lea     rdx, [rbp+70h+var_C8]
0x1800c0413  lea     rcx, [rbp+70h+var_D0]
0x1800c0417  call    ??$As@UIWaitForUIActivationOperation@@@?$ComPtr@UIWebAccountProviderOperation@Provider@Web@Authentication@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWaitForUIActivationOperation@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Provider::IWebAccountProviderOperation>::As<IWaitForUIActivationOperation>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IWaitForUIActivationOperation>>)
0x1800c041c  mov     ebx, eax
0x1800c041e  test    eax, eax
0x1800c0420  jns     short loc_1800C0446
0x1800c0422  mov     rcx, [rbp+78h]; this
0x1800c0426  mov     r9d, eax; char *
0x1800c0429  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800c0430  mov     edx, 699h; void *
0x1800c0435  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c043a  nop
0x1800c043b  lea     rcx, [rbp+70h+var_C8]
0x1800c043f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c0444  jmp     short loc_1800C03F9
0x1800c0446  mov     [rbp+70h+var_E0], 0
0x1800c044e  lea     rdx, [rbp+70h+var_E0]
0x1800c0452  lea     rcx, [rsp+170h+var_130]
0x1800c0457  call    ??$As@UIInspectable@@@?$ComPtr@UIActivatedEventArgs@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIInspectable@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::IActivatedEventArgs>::As<IInspectable>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IInspectable>>)
0x1800c045c  mov     ebx, eax
  ... truncated ...
```
