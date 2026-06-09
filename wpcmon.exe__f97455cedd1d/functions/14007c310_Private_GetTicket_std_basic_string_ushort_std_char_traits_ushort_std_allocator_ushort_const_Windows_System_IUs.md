# Private::GetTicket(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Windows::System::IUser *,Optional<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> const &)

- ea: `0x14007c310`
- end: `0x14007d2d0`
- name: `?GetTicket@Private@@YA?AUUserTicketResult@MicrosoftAccount@wpc@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIUser@System@Windows@@AEBV?$Optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@@@Z`
- size: `4032`
- prototype: ``
- caller_count: `3`
- callee_count: `23`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14007a830`
- `0x14007b98c`
- `0x14007d880`

## callees

- `0x140005530`
- `0x140006338`
- `0x140009858`
- `0x14000b744`
- `0x14000ccac`
- `0x14001f654`
- `0x14001f6b4`
- `0x140031ba0`
- `0x140060f58`
- `0x1400615c0`
- `0x140067360`
- `0x140079a50`
- `0x140079ac8`
- `0x140079db8`
- `0x14007a2e0`
- `0x14007a574`
- `0x14007ac60`
- `0x14007ad14`
- `0x14007b090`
- `0x14007c310`
- `0x14007eb34`
- `0x14007ed0c`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14007cae8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14007cae8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14007ca29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14007ca29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14007c3f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14007c475`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14007c4af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14007c541`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14007c3f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14007c475`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14007c4af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14007c541`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14007c431`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14007c58b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14007c431`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14007c58b`

## string_xrefs

- `0x14007c4a8`: `https://login.microsoft.com`
- `0x14007c3e9`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`
- `0x14007c53a`: `Windows.Security.Authentication.Web.Core.WebTokenRequest`

## pseudocode

```c
// Hidden C++ exception states: #wind=42
wpc::MicrosoftAccount::UserTicketResult *__fastcall Private::GetTicket(
        wpc::MicrosoftAccount::UserTicketResult *a1,
        WCHAR *a2,
        __int64 a3,
        __int64 a4)
{
  WCHAR *v4; // rdi
  __int64 v6; // rcx
  WCHAR *v7; // r9
  HRESULT v8; // eax
  int v9; // edx
  unsigned int v10; // r8d
  int ActivationFactory; // eax
  int v12; // esi
  _QWORD *v13; // rsi
  __int64 v14; // r13
  HRESULT v15; // eax
  int v16; // edx
  unsigned int v17; // r8d
  HSTRING v18; // r15
  HRESULT v19; // eax
  int v20; // edx
  unsigned int v21; // r8d
  int v22; // esi
  HRESULT v23; // eax
  int v24; // edx
  unsigned int v25; // r8d
  HSTRING v26; // rsi
  __int64 v27; // rcx
  int v28; // esi
  unsigned int v29; // r8d
  __int64 v30; // rsi
  __int64 (__fastcall *v31)(__int64, __int64, PVOID, PVOID, _DWORD, __int64 *); // r12
  unsigned int v32; // r8d
  PVOID Reserved1; // r15
  HSTRING_HEADER *v34; // rax
  int v35; // edi
  unsigned int v36; // r8d
  const WCHAR *v37; // rcx
  _QWORD *v38; // rdi
  __int64 (__fastcall *v39)(_QWORD *, __int64, PVOID, WCHAR **); // rsi
  HSTRING_HEADER *v40; // rax
  HRESULT v41; // edx
  int v42; // edi
  __int64 v43; // r8
  WCHAR *v44; // rsi
  int v45; // edi
  _QWORD *v46; // rdi
  __int64 (__fastcall *v47)(_QWORD *, __int64, __int64, int (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rsi
  int (__fastcall ***v48)(_QWORD, GUID *, __int64 *); // rcx
  HRESULT v49; // edx
  int v50; // edi
  __int64 v51; // r8
  __int64 v52; // rcx
  WCHAR *v53; // rcx
  int (__fastcall ***v54)(_QWORD, GUID *, __int64 *); // rsi
  int v55; // edi
  int v56; // edi
  int v57; // edi
  unsigned int v58; // r8d
  WCHAR *v59; // rcx
  int v60; // eax
  HRESULT v61; // edx
  __int64 v62; // r8
  int v63; // edi
  int v64; // eax
  int v65; // edi
  __int64 v66; // r8
  int v67; // eax
  int v68; // edi
  int v69; // eax
  int v70; // edi
  int v71; // eax
  int v72; // edi
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v74; // rcx
  __int128 *v75; // r9
  __int64 v76; // rcx
  __int64 v77; // rcx
  __int64 v78; // rcx
  int (__fastcall ***v79)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v80; // rcx
  __int64 v81; // rcx
  __int64 v82; // rcx
  __int64 v83; // rcx
  _QWORD *v84; // rcx
  wpc::MicrosoftAccount::UserTicketResult *result; // rax
  __int64 v86; // r8
  __int64 v87; // r8
  int v88; // eax
  __int64 v89; // r8
  unsigned int v90; // ebx
  wpc::MicrosoftAccount::UserTicketResult *v91; // rcx
  unsigned int v92; // [rsp+40h] [rbp-618h] BYREF
  WCHAR *v93; // [rsp+48h] [rbp-610h] BYREF
  __int64 v94; // [rsp+50h] [rbp-608h] BYREF
  _QWORD *v95; // [rsp+58h] [rbp-600h] BYREF
  __int64 v96; // [rsp+60h] [rbp-5F8h] BYREF
  int (__fastcall ***v97)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp-5F0h] BYREF
  __int64 v98; // [rsp+70h] [rbp-5E8h] BYREF
  __int64 v99; // [rsp+78h] [rbp-5E0h] BYREF
  __int64 v100; // [rsp+80h] [rbp-5D8h] BYREF
  __int64 v101; // [rsp+88h] [rbp-5D0h] BYREF
  __int64 v102; // [rsp+90h] [rbp-5C8h] BYREF
  __int64 v103; // [rsp+98h] [rbp-5C0h] BYREF
  wpc::MicrosoftAccount::UserTicketResult *v104; // [rsp+A0h] [rbp-5B8h]
  HSTRING v105; // [rsp+B0h] [rbp-5A8h] BYREF
  const WCHAR *v106; // [rsp+B8h] [rbp-5A0h] BYREF
  const wpc::MicrosoftAccount::UserTicketResult *v107; // [rsp+C8h] [rbp-590h] BYREF
  _BYTE v108[40]; // [rsp+D0h] [rbp-588h] BYREF
  _BYTE v109[40]; // [rsp+F8h] [rbp-560h] BYREF
  _BYTE v110[40]; // [rsp+120h] [rbp-538h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+148h] [rbp-510h] BYREF
  _BYTE v112[40]; // [rsp+170h] [rbp-4E8h] BYREF
  _BYTE v113[40]; // [rsp+198h] [rbp-4C0h] BYREF
  _BYTE v114[40]; // [rsp+1C0h] [rbp-498h] BYREF
  _BYTE v115[40]; // [rsp+1E8h] [rbp-470h] BYREF
  _BYTE v116[40]; // [rsp+210h] [rbp-448h] BYREF
  _BYTE v117[40]; // [rsp+238h] [rbp-420h] BYREF
  _BYTE v118[40]; // [rsp+260h] [rbp-3F8h] BYREF
  _BYTE v119[40]; // [rsp+288h] [rbp-3D0h] BYREF
  _BYTE v120[40]; // [rsp+2B0h] [rbp-3A8h] BYREF
  _BYTE v121[40]; // [rsp+2D8h] [rbp-380h] BYREF
  _BYTE v122[40]; // [rsp+300h] [rbp-358h] BYREF
  HSTRING_HEADER v123; // [rsp+328h] [rbp-330h] BYREF
  HSTRING v124; // [rsp+340h] [rbp-318h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+348h] [rbp-310h] BYREF
  HSTRING string; // [rsp+360h] [rbp-2F8h] BYREF
  __int128 v127; // [rsp+368h] [rbp-2F0h] BYREF
  __int128 v128; // [rsp+378h] [rbp-2E0h]
  _BYTE v129[80]; // [rsp+390h] [rbp-2C8h] BYREF
  _BYTE v130[80]; // [rsp+3E0h] [rbp-278h] BYREF
  _BYTE v131[80]; // [rsp+430h] [rbp-228h] BYREF
  _BYTE v132[80]; // [rsp+480h] [rbp-1D8h] BYREF
  _BYTE v133[80]; // [rsp+4D0h] [rbp-188h] BYREF
  _BYTE v134[80]; // [rsp+520h] [rbp-138h] BYREF
  _BYTE v135[80]; // [rsp+570h] [rbp-E8h] BYREF
  _BYTE v136[80]; // [rsp+5C0h] [rbp-98h] BYREF

  v94 = a4;
  v4 = a2;
  v104 = a1;
  v6 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    {
      if ( *((_QWORD *)a2 + 3) <= 7u )
        v7 = a2;
      else
        v7 = *(WCHAR **)a2;
      WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_d559cce52a1433e229f26c816596a62e_Traceguids, v7);
      v6 = WPP_GLOBAL_Control;
    }
    if ( (_UNKNOWN *)v6 != &WPP_GLOBAL_Control && (*(_BYTE *)(v6 + 28) & 4) != 0 )
      WPP_SF_S(
        *(_QWORD *)(v6 + 16),
        13,
        WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
        L"{f1273a19-b987-46a7-8564-c35a5e715902}");
  }
  v95 = 0;
  string = 0;
  v8 = WindowsCreateStringReference(
         L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
         0x45u,
         &hstringHeader,
         &string);
  try
  {
    if ( v8 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v8, v9, v10);
      __debugbreak();
    }
    ActivationFactory = RoGetActivationFactory(string, &GUID_6aca7c92_a581_4479_9c10_752eff44fd34, &v95);
    v12 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          14,
          WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
          (unsigned int)ActivationFactory);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v12);
      throw (ErrorCodeException *)pExceptionObject;
    }
    v103 = 0;
    v13 = v95;
    v14 = *v95;
    string = 0;
    v15 = WindowsCreateStringReference(L"consumers", 9u, &hstringHeader, &string);
    if ( v15 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v15, v16, v17);
    }
    else
    {
      v18 = string;
      v124 = 0;
      v19 = WindowsCreateStringReference(L"https://login.microsoft.com", 0x1Bu, &v123, &v124);
      if ( v19 >= 0 )
      {
        LODWORD(v13) = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, HSTRING, __int64 *))(v14 + 96))(
                         v13,
                         v124,
                         v18,
                         &v103);
        LODWORD(v14) = 0;
        if ( (int)v13 >= 0 )
        {
          v98 = 0;
          v22 = BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccountProvider *,Windows::Security::Credentials::IWebAccountProvider>(
                  v103,
                  &v98);
          if ( v22 < 0 || !v98 )
          {
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
            {
              WPP_SF_D(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                18,
                WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                (unsigned int)v22);
            }
            v88 = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>::operator int Microsoft::WRL::Details::BoolStruct::*(&v98);
            v89 = 2147500035LL;
            if ( v88 != -1 )
              v89 = (unsigned int)v22;
            wpc::MicrosoftAccount::UserTicketResult::UserTicketResult(v136, 5, v89, 0);
            throw (wpc::MicrosoftAccount::UserTicketResult *)v136;
          }
          v100 = 0;
          v124 = 0;
          v23 = WindowsCreateStringReference(
                  L"Windows.Security.Authentication.Web.Core.WebTokenRequest",
                  0x38u,
                  &v123,
                  &v124);
          if ( v23 < 0 )
          {
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v23, v24, v25);
            __debugbreak();
          }
          v26 = v124;
          v27 = v100;
          if ( v100 )
          {
            v100 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
          }
          v28 = RoGetActivationFactory(v26, &GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9, &v100);
          if ( v28 < 0 )
          {
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                19,
                WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                (unsigned int)v28);
            }
            ErrorCodeException::ErrorCodeException((ErrorCodeException *)v113, v28);
            throw (ErrorCodeException *)v113;
          }
          v99 = 0;
          v30 = v100;
          v31 = *(__int64 (__fastcall **)(__int64, __int64, PVOID, PVOID, _DWORD, __int64 *))(*(_QWORD *)v100 + 56LL);
          Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                        &v123,
                        (const WCHAR **)off_1400B0B00,
                        v29)[1].Reserved.Reserved1;
          if ( *((_QWORD *)v4 + 3) > 7u )
            v4 = *(WCHAR **)v4;
          v93 = v4;
          v34 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)&v93, v32);
          v35 = v31(v30, v98, v34[1].Reserved.Reserved1, Reserved1, 0, &v99);
          if ( v35 < 0 )
          {
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                20,
                WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                (unsigned int)v35);
            }
            ErrorCodeException::ErrorCodeException((ErrorCodeException *)v114, v35);
            throw (ErrorCodeException *)v114;
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_49666091>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_49666091>::GetImpl'::`2'::impl) )
            Private::AddSsoPropertyToWebRequest(&v99);
          v97 = 0;
          v37 = *(const WCHAR **)(v94 + 40);
          if ( v37 )
          {
            v93 = 0;
            v38 = v95;
            v39 = *(__int64 (__fastcall **)(_QWORD *, __int64, PVOID, WCHAR **))(*v95 + 80LL);
            if ( *((_QWORD *)v37 + 3) > 7u )
              v37 = *(const WCHAR **)v37;
            v106 = v37;
            v40 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v123, &v106, v36);
            v42 = v39(v38, v98, v40[1].Reserved.Reserved1, &v93);
            if ( v42 < 0 )
            {
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
              {
                WPP_SF_d(
                  *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                  21,
                  WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                  (unsigned int)v42);
              }
              ErrorCodeException::ErrorCodeException((ErrorCodeException *)v115, v42);
              throw (ErrorCodeException *)v115;
            }
            v94 = 0;
            v44 = v93;
            v45 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(
                    (int (__fastcall ***)(_QWORD, GUID *, __int64 *))v93,
                    v41,
                    v43);
            if ( v45 < 0
              || (v45 = (*(__int64 (__fastcall **)(WCHAR *, __int64 *))(*(_QWORD *)v44 + 64LL))(v44, &v94), v45 < 0) )
            {
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
              {
                WPP_SF_d(
                  *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                  22,
                  WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                  (unsigned int)v45);
              }
              ErrorCodeException::ErrorCodeException((ErrorCodeException *)v117, v45);
              throw (ErrorCodeException *)v117;
            }
            v46 = v95;
            v47 = *(__int64 (__fastcall **)(_QWORD *, __int64, __int64, int (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*v95 + 56LL);
            v48 = v97;
            if ( v97 )
            {
              v97 = 0;
              ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v48)[2])(v48);
            }
            v50 = v47(v46, v99, v94, &v97);
            if ( v50 < 0 )
            {
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
              {
                WPP_SF_d(
                  *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                  23,
                  WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                  (unsigned int)v50);
              }
              ErrorCodeException::ErrorCodeException((ErrorCodeException *)v116, v50);
              throw (ErrorCodeException *)v116;
            }
            v52 = v94;
            if ( v94 )
            {
              v94 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
            }
            v53 = v93;
            if ( v93 )
            {
              v93 = 0;
              (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)v53 + 16LL))(v53);
            }
          }
          else
          {
            v57 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD))(*v95 + 48LL))(v95, v99, &v97);
            if ( v57 < 0 )
            {
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
              {
                WPP_SF_d(
                  *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                  24,
                  WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                  (unsigned int)v57);
              }
              ErrorCodeException::ErrorCodeException((ErrorCodeException *)v118, v57);
              throw (ErrorCodeException *)v118;
            }
          }
          v96 = 0;
          v54 = v97;
          v55 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(
                  v97,
                  v49,
                  v51);
          if ( v55 < 0
            || (v55 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*v54)[8])(
                        v54,
                        &v96),
                v55 < 0) )
          {
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                25,
                WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                (unsigned int)v55);
            }
            ErrorCodeException::ErrorCodeException((ErrorCodeException *)v110, v55);
            throw (ErrorCodeException *)v110;
          }
          v92 = 0;
          v56 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v96 + 56LL))(v96, &v92);
          if ( v56 < 0 )
          {
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                26,
                WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                (unsigned int)v56);
            }
            ErrorCodeException::ErrorCodeException((ErrorCodeException *)v119, v56);
            throw (ErrorCodeException *)v119;
          }
          v58 = v92;
          if ( (unsigned __int64)(int)v92 >= 6 )
          {
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
            {
              goto LABEL_54;
            }
            WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 28, WPP_d559cce52a1433e229f26c816596a62e_Traceguids, v92);
          }
          else
          {
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
            {
              goto LABEL_54;
            }
            WPP_SF_dS(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              27,
              (unsigned int)WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
              v92,
              (__int64)(&Private::StatusString)[v92]);
          }
          v58 = v92;
LABEL_54:
          if ( v58 )
          {
            LODWORD(v94) = 0;
            v93 = 0;
            if ( (*(int (__fastcall **)(__int64, WCHAR **))(*(_QWORD *)v96 + 64LL))(v96, &v93) >= 0 )
              (*(void (__fastcall **)(WCHAR *, __int64 *))(*(_QWORD *)v93 + 48LL))(v93, &v94);
            v59 = v93;
            if ( v93 )
            {
              v93 = 0;
              (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)v59 + 16LL))(v59);
            }
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
            {
              WPP_SF_dd(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                29,
                WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                v92,
                v94);
            }
            if ( v92 != 1 )
            {
              if ( v92 == 3 )
              {
                v93 = 0;
                v60 = (*(__int64 (__fastcall **)(__int64, WCHAR **))(*(_QWORD *)v96 + 72LL))(v96, &v93);
                v63 = v60;
                if ( v60 >= 0 )
                {
                  v64 = WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(
                          (int (__fastcall ***)(_QWORD, GUID *, __int64 *))v93,
                          v61,
                          v62);
                  v65 = v64;
                  if ( v64 >= 0 )
                  {
                    v66 = (unsigned int)v94;
                    if ( (_DWORD)v94 != 1317 )
                    {
                      if ( (_DWORD)v94 != -2147023579 )
                      {
                        if ( (_DWORD)v94 != 1231 )
                        {
                          if ( (_DWORD)v94 == -2147023665 )
                          {
                            wpc::MicrosoftAccount::UserTicketResult::UserTicketResult(v132, 3, 2147943631LL, v92);
                            throw (wpc::MicrosoftAccount::UserTicketResult *)v132;
                          }
                          if ( (int)v94 > 0 )
                            v66 = (unsigned __int16)v94 | 0x80070000;
                          wpc::MicrosoftAccount::UserTicketResult::UserTicketResult(v133, 4, v66, v92);
                          throw (wpc::MicrosoftAccount::UserTicketResult *)v133;
                        }
                        wpc::MicrosoftAccount::UserTicketResult::UserTicketResult(v131, 3, 2147943631LL, v92);
                        throw (wpc::MicrosoftAccount::UserTicketResult *)v131;
                      }
                      wpc::MicrosoftAccount::UserTicketResult::UserTicketResult(v130, 1, 2147943717LL, v92);
                      throw (wpc::MicrosoftAccount::UserTicketResult *)v130;
                    }
                    wpc::MicrosoftAccount::UserTicketResult::UserTicketResult(v129, 1, 2147943717LL, v92);
                    throw (wpc::MicrosoftAccount::UserTicketResult *)v129;
                  }
                  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                  {
                    WPP_SF_d(
                      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                      31,
                      WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                      (unsigned int)v64);
                  }
                  ErrorCodeException::ErrorCodeException((ErrorCodeException *)v121, v65);
                  throw (ErrorCodeException *)v121;
                }
                if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                {
                  WPP_SF_d(
                    *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                    30,
                    WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                    (unsigned int)v60);
                }
                ErrorCodeException::ErrorCodeException((ErrorCodeException *)v120, v63);
                throw (ErrorCodeException *)v120;
              }
              v86 = (unsigned int)v94;
              if ( (int)v94 > 0 )
                v86 = (unsigned __int16)v94 | 0x80070000;
              wpc::MicrosoftAccount::UserTicketResult::UserTicketResult(v134, 3, v86, v92);
              throw (wpc::MicrosoftAccount::UserTicketResult *)v134;
            }
            v87 = (unsigned int)v94;
            if ( (int)v94 > 0 )
              v87 = (unsigned __int16)v94 | 0x80070000;
            wpc::MicrosoftAccount::UserTicketResult::UserTicketResult(v135, 2, v87, 1);
            throw (wpc::MicrosoftAccount::UserTicketResult *)v135;
          }
          v102 = 0;
          v67 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v96 + 48LL))(v96, &v102);
          v68 = v67;
          if ( v67 < 0 )
          {
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                32,
                WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                (unsigned int)v67);
            }
            ErrorCodeException::ErrorCodeException((ErrorCodeException *)v122, v68);
            throw (ErrorCodeException *)v122;
          }
          v101 = 0;
          v69 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v102 + 48LL))(v102, 0, &v101);
          v70 = v69;
          if ( v69 < 0 )
          {
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                33,
                WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                (unsigned int)v69);
            }
            ErrorCodeException::ErrorCodeException((ErrorCodeException *)v108, v70);
            throw (ErrorCodeException *)v108;
          }
          v105 = 0;
          v71 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v101 + 48LL))(v101, &v105);
          v72 = v71;
          if ( v71 < 0 )
          {
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                34,
                WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
                (unsigned int)v71);
            }
            ErrorCodeException::ErrorCodeException((ErrorCodeException *)v109, v72);
            throw (ErrorCodeException *)v109;
          }
          StringRawBuffer = WindowsGetStringRawBuffer(v105, 0);
          v127 = 0;
          v128 = 0;
          v74 = -1;
          do
            ++v74;
          while ( StringRawBuffer[v74] );
          std::wstring::_Construct<1,unsigned short const *>((char **)&v127, StringRawBuffer, v74);
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
          {
            v75 = &v127;
            if ( *((_QWORD *)&v128 + 1) > 7u )
              v75 = (__int128 *)v127;
            WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 35, WPP_d559cce52a1433e229f26c816596a62e_Traceguids, v75);
          }
          v106 = (const WCHAR *)a1;
          *((_QWORD *)a1 + 2) = 0;
          *((_QWORD *)a1 + 8) = 0;
          std::wstring::wstring((__int64)a1 + 32, (__int64)&v127);
          *((_QWORD *)a1 + 8) = (char *)a1 + 32;
          std::wstring::~wstring((char **)&v127);
          if ( v105 )
            WindowsDeleteString(v105);
          v76 = v101;
          if ( v101 )
          {
            v101 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
          }
          v77 = v102;
          if ( v102 )
          {
            v102 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
          }
          v78 = v96;
          if ( v96 )
          {
            v96 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
          }
          v79 = v97;
          if ( v97 )
          {
            v97 = 0;
            ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v79)[2])(v79);
          }
          v80 = v99;
          if ( v99 )
          {
            v99 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
          }
          v81 = v100;
          if ( v100 )
          {
            v100 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
          }
          v82 = v98;
          if ( v98 )
          {
            v98 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
          }
          v83 = v103;
          if ( v103 )
          {
            v103 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
          }
          v84 = v95;
          if ( v95 )
          {
            v95 = 0;
            (*(void (__fastcall **)(_QWORD *, _QWORD))(*v84 + 16LL))(v84, *v84);
          }
          return a1;
        }
LABEL_109:
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            (unsigned int)(v14 + 17),
            WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
            (unsigned int)v13);
        ErrorCodeException::ErrorCodeException((ErrorCodeException *)v112, (int)v13);
        throw (ErrorCodeException *)v112;
      }
    }
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v19, v20, v21);
    goto LABEL_109;
  }
  catch ( const wpc::MicrosoftAccount::UserTicketResult *v107 )
  {
    wpc::MicrosoftAccount::UserTicketResult::UserTicketResult(v104, v107);
    return v104;
  }
  catch ( ... )
  {
    v90 = ErrorCodeFromCaughtException();
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_D(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 36, WPP_d559cce52a1433e229f26c816596a62e_Traceguids, v90);
    v91 = v104;
    *((_QWORD *)v104 + 2) = 0;
    *((_QWORD *)v91 + 8) = 0;
    *((_DWORD *)v91 + 1) = 0;
    *((_DWORD *)v91 + 2) = v90;
    *((_DWORD *)v91 + 3) = 3;
    *((_QWORD *)v91 + 2) = (char *)v91 + 4;
    return v104;
  }
  return result;
}

```

## disassembly

```asm
0x14007c310  push    rbx
0x14007c312  push    rsi
0x14007c313  push    rdi
0x14007c314  push    r12
0x14007c316  push    r13
0x14007c318  push    r14
0x14007c31a  push    r15
0x14007c31c  sub     rsp, 620h
0x14007c323  mov     rax, cs:__security_cookie
0x14007c32a  xor     rax, rsp
0x14007c32d  mov     [rsp+658h+var_48], rax
0x14007c335  mov     [rsp+658h+var_608], r9
0x14007c33a  mov     rdi, rdx
0x14007c33d  mov     r14, rcx
0x14007c340  mov     [rsp+658h+var_5B8], rcx
0x14007c348  xor     r12d, r12d
0x14007c34b  lea     r15, WPP_GLOBAL_Control
0x14007c352  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c359  cmp     rcx, r15
0x14007c35c  jz      short loc_14007C3C0
0x14007c35e  test    byte ptr [rcx+1Ch], 4
0x14007c362  jz      short loc_14007C394
0x14007c364  cmp     qword ptr [rdx+18h], 7
0x14007c369  jbe     short loc_14007C370
0x14007c36b  mov     r9, [rdx]
0x14007c36e  jmp     short loc_14007C373
0x14007c370  mov     r9, rdi
0x14007c373  mov     edx, 0Ch
0x14007c378  lea     rbx, WPP_d559cce52a1433e229f26c816596a62e_Traceguids
0x14007c37f  mov     r8, rbx
0x14007c382  mov     rcx, [rcx+10h]
0x14007c386  call    WPP_SF_S
0x14007c38b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c392  jmp     short loc_14007C39B
0x14007c394  lea     rbx, WPP_d559cce52a1433e229f26c816596a62e_Traceguids
0x14007c39b  cmp     rcx, r15
0x14007c39e  jz      short loc_14007C3C7
0x14007c3a0  test    byte ptr [rcx+1Ch], 4
0x14007c3a4  jz      short loc_14007C3C7
0x14007c3a6  mov     edx, 0Dh
0x14007c3ab  lea     r9, aF1273a19B98746; "{f1273a19-b987-46a7-8564-c35a5e715902}"
0x14007c3b2  mov     r8, rbx
0x14007c3b5  mov     rcx, [rcx+10h]
0x14007c3b9  call    WPP_SF_S
0x14007c3be  jmp     short loc_14007C3C7
0x14007c3c0  lea     rbx, WPP_d559cce52a1433e229f26c816596a62e_Traceguids
0x14007c3c7  mov     [rsp+658h+var_600], r12
0x14007c3cc  mov     [rsp+658h+string], r12
0x14007c3d4  lea     r9, [rsp+658h+string]; string
0x14007c3dc  lea     r8, [rsp+658h+hstringHeader]; hstringHeader
0x14007c3e4  mov     edx, 45h ; 'E'; length
0x14007c3e9  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x14007c3f0  call    cs:__imp_WindowsCreateStringReference
0x14007c3f6  test    eax, eax
0x14007c3f8  js      loc_14007CC33
0x14007c3fe  mov     rsi, [rsp+658h+string]
0x14007c406  mov     rcx, [rsp+658h+var_600]
0x14007c40b  test    rcx, rcx
0x14007c40e  jz      short loc_14007C422
0x14007c410  mov     [rsp+658h+var_600], r12
0x14007c415  mov     rax, [rcx]
0x14007c418  mov     rax, [rax+10h]
0x14007c41c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c421  nop
0x14007c422  lea     r8, [rsp+658h+var_600]
0x14007c427  lea     rdx, _GUID_6aca7c92_a581_4479_9c10_752eff44fd34
0x14007c42e  mov     rcx, rsi
0x14007c431  call    cs:__imp_RoGetActivationFactory
0x14007c437  mov     esi, eax
0x14007c439  test    eax, eax
0x14007c43b  js      loc_14007CC3B
0x14007c441  mov     [rsp+658h+var_5C0], r12
0x14007c449  mov     rsi, [rsp+658h+var_600]
0x14007c44e  mov     r13, [rsi]
0x14007c451  mov     [rsp+658h+string], r12
0x14007c459  lea     r9, [rsp+658h+string]; string
0x14007c461  lea     r8, [rsp+658h+hstringHeader]; hstringHeader
0x14007c469  mov     edx, 9; length
0x14007c46e  lea     rcx, aConsumers; "consumers"
0x14007c475  call    cs:__imp_WindowsCreateStringReference
0x14007c47b  test    eax, eax
0x14007c47d  js      loc_14007CC85
0x14007c483  mov     r15, [rsp+658h+string]
0x14007c48b  mov     [rsp+658h+var_318], r12
0x14007c493  lea     r9, [rsp+658h+var_318]; string
0x14007c49b  lea     r8, [rsp+658h+var_330]; hstringHeader
0x14007c4a3  mov     edx, 1Bh; length
0x14007c4a8  lea     rcx, aHttpsLoginMicr; "https://login.microsoft.com"
0x14007c4af  call    cs:__imp_WindowsCreateStringReference
0x14007c4b5  test    eax, eax
0x14007c4b7  js      loc_14007CC8D
0x14007c4bd  lea     r9, [rsp+658h+var_5C0]
0x14007c4c5  mov     r8, r15
0x14007c4c8  mov     rdx, [rsp+658h+var_318]
0x14007c4d0  mov     rcx, rsi
0x14007c4d3  mov     rax, [r13+60h]
0x14007c4d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c4dc  mov     esi, eax
0x14007c4de  xor     r13d, r13d
0x14007c4e1  test    eax, eax
0x14007c4e3  js      loc_14007CC95
0x14007c4e9  mov     [rsp+658h+var_5E8], r13
0x14007c4ee  lea     rdx, [rsp+658h+var_5E8]
0x14007c4f3  mov     rcx, [rsp+658h+var_5C0]
0x14007c4fb  call    ??$BlockOnCompletionAndGetResults@PEAVWebAccountProvider@Credentials@Security@Windows@@UIWebAccountProvider@234@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccountProvider *,Windows::Security::Credentials::IWebAccountProvider>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>>,tagCOWAIT_FLAGS,void *)
0x14007c500  mov     esi, eax
0x14007c502  test    eax, eax
0x14007c504  js      loc_14007D260
0x14007c50a  cmp     [rsp+658h+var_5E8], r13
0x14007c50f  jz      loc_14007D260
0x14007c515  mov     [rsp+658h+var_5D8], r13
0x14007c51d  mov     [rsp+658h+var_318], r13
0x14007c525  lea     r9, [rsp+658h+var_318]; string
0x14007c52d  lea     r8, [rsp+658h+var_330]; hstringHeader
0x14007c535  mov     edx, 38h ; '8'; length
0x14007c53a  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebTokenRequest@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x14007c541  call    cs:__imp_WindowsCreateStringReference
0x14007c547  test    eax, eax
0x14007c549  js      loc_14007CCE5
0x14007c54f  mov     rsi, [rsp+658h+var_318]
0x14007c557  mov     rcx, [rsp+658h+var_5D8]
0x14007c55f  test    rcx, rcx
0x14007c562  jz      short loc_14007C579
0x14007c564  mov     [rsp+658h+var_5D8], r13
0x14007c56c  mov     rax, [rcx]
0x14007c56f  mov     rax, [rax+10h]
0x14007c573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c578  nop
0x14007c579  lea     r8, [rsp+658h+var_5D8]
0x14007c581  lea     rdx, _GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9
0x14007c588  mov     rcx, rsi
0x14007c58b  call    cs:__imp_RoGetActivationFactory
0x14007c591  mov     esi, eax
0x14007c593  test    eax, eax
0x14007c595  js      loc_14007CCED
0x14007c59b  mov     [rsp+658h+var_5E0], r13
0x14007c5a0  mov     rsi, [rsp+658h+var_5D8]
0x14007c5a8  mov     rax, [rsi]
0x14007c5ab  mov     r12, [rax+38h]
0x14007c5af  lea     rdx, off_1400B0B00; "{f1273a19-b987-46a7-8564-c35a5e715902}"
0x14007c5b6  lea     rcx, [rsp+658h+var_330]
0x14007c5be  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x14007c5c3  nop
0x14007c5c4  mov     r15, [rax+18h]
0x14007c5c8  cmp     qword ptr [rdi+18h], 7
0x14007c5cd  jbe     short loc_14007C5D2
0x14007c5cf  mov     rdi, [rdi]
0x14007c5d2  mov     [rsp+658h+var_610], rdi
0x14007c5d7  lea     rdx, [rsp+658h+var_610]
0x14007c5dc  lea     rcx, [rsp+658h+hstringHeader]
0x14007c5e4  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x14007c5e9  nop
0x14007c5ea  lea     rcx, [rsp+658h+var_5E0]
0x14007c5ef  mov     [rsp+658h+var_630], rcx
0x14007c5f4  mov     dword ptr [rsp+658h+var_638], r13d
0x14007c5f9  mov     r9, r15
0x14007c5fc  mov     r8, [rax+18h]
0x14007c600  mov     rdx, [rsp+658h+var_5E8]
0x14007c605  mov     rcx, rsi
0x14007c608  mov     rax, r12
0x14007c60b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c610  mov     edi, eax
0x14007c612  test    eax, eax
0x14007c614  js      loc_14007CD3E
0x14007c61a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_49666091@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_49666091@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_49666091> `wil::Feature<__WilFeatureTraits_Feature_49666091>::GetImpl(void)'::`2'::impl
0x14007c621  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_49666091@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_49666091>::__private_IsEnabled(void)
0x14007c626  test    al, al
0x14007c628  jz      short loc_14007C634
0x14007c62a  lea     rcx, [rsp+658h+var_5E0]
0x14007c62f  call    ?AddSsoPropertyToWebRequest@Private@@YAXAEAV?$ComPtr@UIWebTokenRequest@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Z; Private::AddSsoPropertyToWebRequest(Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequest> &)
0x14007c634  mov     [rsp+658h+var_5F0], r13
0x14007c639  mov     rcx, [rsp+658h+var_608]
0x14007c63e  mov     rcx, [rcx+28h]
0x14007c642  test    rcx, rcx
0x14007c645  jz      loc_14007C7C6
0x14007c64b  mov     [rsp+658h+var_610], r13
0x14007c650  mov     rdi, [rsp+658h+var_600]
0x14007c655  mov     rax, [rdi]
0x14007c658  mov     rsi, [rax+50h]
0x14007c65c  cmp     qword ptr [rcx+18h], 7
0x14007c661  jbe     short loc_14007C666
0x14007c663  mov     rcx, [rcx]
0x14007c666  mov     [rsp+658h+var_5A0], rcx
0x14007c66e  lea     rdx, [rsp+658h+var_5A0]
0x14007c676  lea     rcx, [rsp+658h+var_330]
0x14007c67e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x14007c683  nop
0x14007c684  lea     r9, [rsp+658h+var_610]
0x14007c689  mov     r8, [rax+18h]
0x14007c68d  mov     rdx, [rsp+658h+var_5E8]
0x14007c692  mov     rcx, rdi
0x14007c695  mov     rax, rsi
0x14007c698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c69d  mov     edi, eax
0x14007c69f  test    eax, eax
0x14007c6a1  js      loc_14007CD8F
0x14007c6a7  mov     [rsp+658h+var_608], r13
0x14007c6ac  mov     rsi, [rsp+658h+var_610]
0x14007c6b1  mov     rcx, rsi
0x14007c6b4  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,tagCOWAIT_FLAGS,void *)
0x14007c6b9  mov     edi, eax
0x14007c6bb  test    eax, eax
0x14007c6bd  js      loc_14007CE82
0x14007c6c3  mov     rax, [rsi]
0x14007c6c6  lea     rdx, [rsp+658h+var_608]
0x14007c6cb  mov     rcx, rsi
0x14007c6ce  mov     rax, [rax+40h]
0x14007c6d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c6d7  mov     edi, eax
0x14007c6d9  test    eax, eax
0x14007c6db  js      loc_14007CE82
0x14007c6e1  mov     rdi, [rsp+658h+var_600]
0x14007c6e6  mov     rax, [rdi]
0x14007c6e9  mov     rsi, [rax+38h]
0x14007c6ed  mov     rcx, [rsp+658h+var_5F0]
0x14007c6f2  test    rcx, rcx
0x14007c6f5  jz      short loc_14007C709
0x14007c6f7  mov     [rsp+658h+var_5F0], r13
0x14007c6fc  mov     rax, [rcx]
0x14007c6ff  mov     rax, [rax+10h]
0x14007c703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c708  nop
0x14007c709  lea     r9, [rsp+658h+var_5F0]
0x14007c70e  mov     r8, [rsp+658h+var_608]
0x14007c713  mov     rdx, [rsp+658h+var_5E0]
0x14007c718  mov     rcx, rdi
0x14007c71b  mov     rax, rsi
0x14007c71e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c723  mov     edi, eax
0x14007c725  test    eax, eax
0x14007c727  js      loc_14007CDE0
0x14007c72d  mov     rcx, [rsp+658h+var_608]
0x14007c732  test    rcx, rcx
0x14007c735  jz      short loc_14007C749
0x14007c737  mov     [rsp+658h+var_608], r13
0x14007c73c  mov     rax, [rcx]
0x14007c73f  mov     rax, [rax+10h]
0x14007c743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c748  nop
0x14007c749  mov     rcx, [rsp+658h+var_610]
0x14007c74e  test    rcx, rcx
0x14007c751  jz      short loc_14007C765
0x14007c753  mov     [rsp+658h+var_610], r13
0x14007c758  mov     rax, [rcx]
0x14007c75b  mov     rax, [rax+10h]
0x14007c75f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c764  nop
0x14007c765  mov     [rsp+658h+var_5F8], r13
0x14007c76a  mov     rsi, [rsp+658h+var_5F0]
0x14007c76f  mov     rcx, rsi
0x14007c772  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)
0x14007c777  mov     edi, eax
0x14007c779  test    eax, eax
0x14007c77b  js      loc_14007D20F
0x14007c781  mov     rax, [rsi]
0x14007c784  lea     rdx, [rsp+658h+var_5F8]
0x14007c789  mov     rcx, rsi
0x14007c78c  mov     rax, [rax+40h]
0x14007c790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c795  mov     edi, eax
0x14007c797  test    eax, eax
0x14007c799  js      loc_14007D20F
0x14007c79f  mov     [rsp+658h+var_618], r13d
0x14007c7a4  mov     rcx, [rsp+658h+var_5F8]
0x14007c7a9  mov     rax, [rcx]
0x14007c7ac  lea     rdx, [rsp+658h+var_618]
0x14007c7b1  mov     rax, [rax+38h]
0x14007c7b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c7ba  mov     edi, eax
0x14007c7bc  test    eax, eax
0x14007c7be  js      loc_14007CE31
0x14007c7c4  jmp     short loc_14007C7F0
0x14007c7c6  mov     rcx, [rsp+658h+var_600]
0x14007c7cb  mov     rax, [rcx]
0x14007c7ce  lea     r8, [rsp+658h+var_5F0]
0x14007c7d3  mov     rdx, [rsp+658h+var_5E0]
0x14007c7d8  mov     rax, [rax+30h]
0x14007c7dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c7e1  mov     edi, eax
0x14007c7e3  test    eax, eax
0x14007c7e5  js      loc_14007CED3
0x14007c7eb  jmp     loc_14007C765
0x14007c7f0  movsxd  r8, [rsp+658h+var_618]
0x14007c7f5  cmp     r8, 6
0x14007c7f9  jnb     short loc_14007C83A
0x14007c7fb  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c802  lea     rsi, WPP_GLOBAL_Control
0x14007c809  cmp     rcx, rsi
0x14007c80c  jz      short loc_14007C86C
0x14007c80e  test    byte ptr [rcx+1Ch], 4
0x14007c812  jz      short loc_14007C86C
0x14007c814  lea     r9, ?StatusString@Private@@3PAPEBGA; ushort const * near * Private::StatusString
0x14007c81b  mov     edx, 1Bh
0x14007c820  mov     rax, [r9+r8*8]
0x14007c824  mov     [rsp+658h+var_638], rax
0x14007c829  mov     r9d, r8d
0x14007c82c  mov     r8, rbx
0x14007c82f  mov     rcx, [rcx+10h]
0x14007c833  call    WPP_SF_dS
0x14007c838  jmp     short loc_14007C867
  ... truncated ...
```
