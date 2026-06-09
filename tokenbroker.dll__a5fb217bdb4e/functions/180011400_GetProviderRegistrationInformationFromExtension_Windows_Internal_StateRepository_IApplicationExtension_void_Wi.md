# _GetProviderRegistrationInformationFromExtension(Windows::Internal::StateRepository::IApplicationExtension *,void *,Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation * *)

- ea: `0x180011400`
- end: `0x180011f8c`
- name: `?_GetProviderRegistrationInformationFromExtension@@YAJPEAUIApplicationExtension@StateRepository@Internal@Windows@@PEAXPEAPEAUIWamProviderRegistrationInformation@Web@Authentication@Security@34@@Z`
- size: `2956`
- prototype: `__int64 __fastcall(struct Windows::Internal::StateRepository::IApplicationExtension *, void *, struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation **)`
- caller_count: `4`
- callee_count: `23`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180012080`
- `0x180020268`
- `0x1800228e0`
- `0x18009e750`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x180011400`
- `0x180013990`
- `0x180013d60`
- `0x1800175c0`
- `0x180019be8`
- `0x180019f0c`
- `0x18002ea84`
- `0x180030f90`
- `0x1800348cc`
- `0x180041a50`
- `0x1800439d0`
- `0x180045660`
- `0x18004be18`
- `0x18004e850`
- `0x180050240`
- `0x180051e9c`
- `0x180065764`
- `0x18008e690`
- `0x18009942c`
- `0x18009e550`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011814`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011814`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011e84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011e84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800117fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800117fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180011757`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180011757`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011526`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800115dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800116bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011931`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800119c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011a12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011a2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011a74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011abc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011b0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011d93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011da3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011db3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011dd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011dfa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011e0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011e30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011e41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011ea9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011ecd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011ef1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011f01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011f27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011f38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011526`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800115dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800116bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011931`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800119c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011a12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011a2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011a74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011abc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011b0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011d93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011da3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011db3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011dd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011dfa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011e0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011e30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011e41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011ea9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011ecd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011ef1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011f01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011f27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011f38`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180011835`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800118f6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180011835`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800118f6`
- `ext-ms-win-kernel32-package-l1-1-0!PackageFamilyNameFromFullName` at `0x18001176b`
- `ext-ms-win-kernel32-package-l1-1-0!PackageFamilyNameFromFullName` at `0x18001176b`

## string_xrefs

- `0x180011487`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`
- `0x1800114fb`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`
- `0x1800115b1`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`
- `0x180011643`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`
- `0x180011695`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`
- `0x1800116e2`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`
- `0x180011721`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`
- `0x180011d47`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`
- `0x180011b1e`: `Windows.Foundation.Uri`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
__int64 __fastcall _GetProviderRegistrationInformationFromExtension(
        struct Windows::Internal::StateRepository::IApplicationExtension *a1,
        void *a2,
        struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation **a3)
{
  int WebAccountProviderElementAttributes; // eax
  signed int v6; // edi
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, HSTRING_HEADER *); // rbx
  _QWORD *v9; // rax
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, HSTRING_HEADER *); // rbx
  _QWORD *v15; // rax
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  int v18; // eax
  __int64 (__fastcall *v19)(struct Windows::Internal::StateRepository::IApplicationExtension *, __int64 *); // rbx
  int v20; // eax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64 *); // rbx
  int v23; // eax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, HSTRING *); // rbx
  int v26; // eax
  unsigned __int64 v27; // r9
  __int64 v28; // rdx
  int v29; // eax
  const WCHAR *StringRawBuffer; // rax
  LONG v31; // eax
  int v32; // eax
  HSTRING v33; // rcx
  HSTRING v34; // rbx
  int ActivationFactory; // eax
  __int64 v36; // rdi
  __int64 (__fastcall *v37)(__int64, __int64, __int64 *); // rbx
  int v38; // eax
  __int64 v39; // rbx
  int v40; // eax
  __int64 v41; // rdi
  __int64 (__fastcall *v42)(__int64, __int64, __int64 *); // rbx
  int v43; // eax
  __int64 v44; // rdi
  __int64 (__fastcall *v45)(__int64, HSTRING *); // rbx
  int v46; // eax
  __int64 v47; // rdx
  __int64 v48; // rdi
  __int64 (__fastcall *v49)(__int64, HSTRING *); // rbx
  __int64 v50; // rdi
  __int64 (__fastcall *v51)(__int64, HSTRING *); // rbx
  int v52; // eax
  int v53; // eax
  _QWORD *v54; // rax
  int v55; // eax
  int v56; // eax
  __int64 v57; // rdx
  int ManagedUrls; // eax
  int v59; // r9d
  __int64 v60; // rdi
  int (__fastcall *v61)(__int64, HSTRING, __int64 *); // rbx
  __int64 v62; // rdi
  __int64 (__fastcall *v63)(__int64, __int64 *); // rbx
  int v64; // eax
  __int64 v65; // rbx
  HSTRING v66; // rdi
  HSTRING v67; // rsi
  HSTRING v68; // r14
  HSTRING v69; // r15
  int v70; // r12d
  int v71; // r13d
  HSTRING v72; // rbx
  int v73; // eax
  struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *v75; // rax
  signed int LastError; // eax
  unsigned int v77; // ebx
  int v78; // [rsp+20h] [rbp-E0h]
  int v79; // [rsp+20h] [rbp-E0h]
  __int64 v80; // [rsp+48h] [rbp-B8h]
  int v81; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING string; // [rsp+68h] [rbp-98h] BYREF
  __int64 v83; // [rsp+70h] [rbp-90h] BYREF
  HSTRING v84; // [rsp+78h] [rbp-88h] BYREF
  __int64 v85; // [rsp+80h] [rbp-80h] BYREF
  char v86; // [rsp+88h] [rbp-78h]
  HSTRING v87; // [rsp+90h] [rbp-70h] BYREF
  __int64 v88; // [rsp+98h] [rbp-68h] BYREF
  HSTRING v89; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v90; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v91; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING v92; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING v93; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v94; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v95; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING v96; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v97; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v98; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v99; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v100; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING v101; // [rsp+100h] [rbp+0h] BYREF
  struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *v102; // [rsp+108h] [rbp+8h] BYREF
  __int64 v103; // [rsp+110h] [rbp+10h] BYREF
  HSTRING v104; // [rsp+118h] [rbp+18h] BYREF
  int v105; // [rsp+120h] [rbp+20h]
  UINT32 packageFamilyNameLength; // [rsp+128h] [rbp+28h] BYREF
  int *v107; // [rsp+130h] [rbp+30h] BYREF
  char v108; // [rsp+138h] [rbp+38h]
  struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation **v109; // [rsp+140h] [rbp+40h]
  HSTRING v110; // [rsp+148h] [rbp+48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+150h] [rbp+50h] BYREF
  HSTRING v112[5]; // [rsp+168h] [rbp+68h] BYREF
  WCHAR packageFamilyName[264]; // [rsp+190h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3E8h] [rbp+2E8h]

  v109 = a3;
  v81 = 0;
  v104 = 0;
  v105 = 0;
  v107 = &v81;
  v108 = 1;
  *a3 = 0;
  v100 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v100);
  WebAccountProviderElementAttributes = _GetWebAccountProviderElementAttributes(a1, &v100);
  v6 = WebAccountProviderElementAttributes;
  v81 = WebAccountProviderElementAttributes;
  if ( WebAccountProviderElementAttributes < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22E,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
      (const char *)(unsigned int)WebAccountProviderElementAttributes,
      v78);
LABEL_100:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v100);
    v108 = 0;
    lambda_ff3c5b7b9b1498b348a39200f0507ed4_::operator()(&v107);
    RoVariant::~RoVariant((RoVariant *)&v104);
    return (unsigned int)v6;
  }
  string = 0;
  v7 = v100;
  v8 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING_HEADER *))(*(_QWORD *)v100 + 48LL);
  v110 = (HSTRING)&v104;
  hstringHeader.Reserved.Reserved1 = 0;
  v9 = (_QWORD *)Windows::Internal::StringReference::StringReference(v112, L"@Url");
  v6 = v8(v7, *v9, &hstringHeader);
  v81 = v6;
  RoVariant::Attach((RoVariant *)v110, (struct IInspectable *)hstringHeader.Reserved.Reserved1);
  if ( v6 < 0 )
  {
    v10 = (unsigned int)v6;
    v11 = 563;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
      (const char *)v10,
      v78);
LABEL_98:
    if ( string )
      WindowsDeleteString(string);
    goto LABEL_100;
  }
  v110 = v104;
  LODWORD(hstringHeader.Reserved.Reserved1) = v105;
  WindowsDeleteString(string);
  string = 0;
  v12 = RoVariant::Accessor::GetString((RoVariant::Accessor *)&v110, &string);
  v6 = v12;
  v81 = v12;
  if ( v12 < 0 )
  {
    v10 = (unsigned int)v12;
    v11 = 564;
    goto LABEL_5;
  }
  v84 = 0;
  v13 = v100;
  v14 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING_HEADER *))(*(_QWORD *)v100 + 48LL);
  v110 = (HSTRING)&v104;
  hstringHeader.Reserved.Reserved1 = 0;
  v15 = (_QWORD *)Windows::Internal::StringReference::StringReference(v112, L"@BackgroundEntryPoint");
  v6 = v14(v13, *v15, &hstringHeader);
  v81 = v6;
  RoVariant::Attach((RoVariant *)v110, (struct IInspectable *)hstringHeader.Reserved.Reserved1);
  if ( v6 < 0 )
  {
    v16 = (unsigned int)v6;
    v17 = 569;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
      (const char *)v16,
      v78);
    goto LABEL_96;
  }
  v110 = v104;
  LODWORD(hstringHeader.Reserved.Reserved1) = v105;
  WindowsDeleteString(v84);
  v84 = 0;
  v18 = RoVariant::Accessor::GetString((RoVariant::Accessor *)&v110, &v84);
  v6 = v18;
  v81 = v18;
  if ( v18 < 0 )
  {
    v16 = (unsigned int)v18;
    v17 = 570;
    goto LABEL_10;
  }
  v83 = 0;
  v19 = *(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IApplicationExtension *, __int64 *))(*(_QWORD *)a1 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
  v20 = v19(a1, &v83);
  v6 = v20;
  v81 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23D,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
      (const char *)(unsigned int)v20,
      v78);
LABEL_95:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
LABEL_96:
    if ( v84 )
      WindowsDeleteString(v84);
    goto LABEL_98;
  }
  v85 = 0;
  v21 = v83;
  v22 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v83 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
  v23 = v22(v21, &v85);
  v6 = v23;
  v81 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23F,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
      (const char *)(unsigned int)v23,
      v78);
LABEL_94:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    goto LABEL_95;
  }
  v87 = 0;
  v24 = v85;
  v25 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v85 + 112LL);
  WindowsDeleteString(0);
  v87 = 0;
  v26 = v25(v24, &v87);
  v6 = v26;
  v81 = v26;
  if ( v26 < 0 )
  {
    v27 = (unsigned int)v26;
    v28 = 579;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
      (const char *)v27,
      v78);
    goto LABEL_92;
  }
  LODWORD(v101) = 0;
  v29 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v85 + 1168LL))(v85, &v101);
  if ( v29 >= 0 )
  {
    v86 = (_DWORD)v101 == 2;
  }
  else
  {
    v86 = 0;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x248,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
      (const char *)(unsigned int)v29,
      v78);
  }
  packageFamilyNameLength = 260;
  StringRawBuffer = WindowsGetStringRawBuffer(v87, 0);
  v31 = PackageFamilyNameFromFullName(StringRawBuffer, &packageFamilyNameLength, packageFamilyName);
  v6 = v31;
  if ( v31 > 0 )
    v6 = (unsigned __int16)v31 | 0x80070000;
  v81 = v6;
  if ( v6 < 0 )
  {
    v27 = (unsigned int)v6;
    v28 = 595;
    goto LABEL_19;
  }
  v92 = 0;
  v32 = Windows::Internal::String::_InitializeHelper((Windows::Internal::String *)&v92, packageFamilyName);
  v6 = v32;
  v81 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x256,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
      (const char *)(unsigned int)v32,
      v78);
    goto LABEL_29;
  }
  v88 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Internal.StateRepository.ApplicationResourceResolver",
         0x3Cu,
         &hstringHeader,
         &v110) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v34 = v110;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v88);
  ActivationFactory = RoGetActivationFactory(v34, &GUID_84463b2a_c88e_4597_b41f_17d3bf6486e9, &v88);
  v6 = ActivationFactory;
  v81 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25C,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v78);
LABEL_35:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v88);
LABEL_29:
    v33 = v92;
    if ( !v92 )
      goto LABEL_92;
    goto LABEL_91;
  }
  v90 = 0;
  v36 = v88;
  v37 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v88 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v90);
  v38 = v37(v36, v83, &v90);
  v6 = v38;
  v81 = v38;
  if ( v38 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25E,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
      (const char *)(unsigned int)v38,
      v78);
LABEL_38:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v90);
    goto LABEL_35;
  }
  v89 = 0;
  v91 = 0;
  v39 = *(_QWORD *)Windows::Internal::StringReference::StringReference(
                     v112,
                     L"Windows.Internal.StateRepository.PackageResourceResolver");
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
  v40 = RoGetActivationFactory(v39, &GUID_cb4720b3_052a_4478_b348_29a7cf0d828e, &v91);
  v6 = v40;
  v81 = v40;
  if ( v40 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x265,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
      (const char *)(unsigned int)v40,
      v78);
    goto LABEL_41;
  }
  v94 = 0;
  v41 = v91;
  v42 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v91 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v94);
  v43 = v42(v41, v85, &v94);
  v6 = v43;
  v81 = v43;
  if ( v43 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x267,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
      (const char *)(unsigned int)v43,
      v78);
LABEL_45:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v94);
LABEL_41:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
    if ( v89 )
      WindowsDeleteString(v89);
    goto LABEL_38;
  }
  v93 = 0;
  v110 = 0;
  hstringHeader.Reserved.Reserved2[0] = 0;
  if ( (int)Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate((PHANDLE)&v110, a2) >= 0 )
  {
    v44 = v90;
    v45 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v90 + 48LL);
    WindowsDeleteString(v89);
    v89 = 0;
    v46 = v45(v44, &v89);
    v6 = v46;
    v81 = v46;
    if ( v46 < 0 )
    {
      v47 = 629;
LABEL_49:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v47,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
        (const char *)(unsigned int)v46,
        v78);
      Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&v110);
LABEL_50:
      if ( v93 )
        WindowsDeleteString(v93);
      goto LABEL_45;
    }
    v48 = v94;
    v49 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v94 + 56LL);
    WindowsDeleteString(v93);
    v93 = 0;
    v46 = v49(v48, &v93);
    v6 = v46;
    v81 = v46;
    if ( v46 < 0 )
    {
      v47 = 631;
      goto LABEL_49;
    }
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&v110);
    v96 = 0;
    v50 = v83;
    v51 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v83 + 656LL);
    WindowsDeleteString(0);
    v96 = 0;
    v52 = v51(v50, &v96);
    v6 = v52;
    v81 = v52;
    if ( v52 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x285,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
        (const char *)(unsigned int)v52,
        v78);
LABEL_56:
      if ( v96 )
        WindowsDeleteString(v96);
      goto LABEL_50;
    }
    v98 = 0;
    v53 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v83 + 232LL))(v83, &v98);
    v6 = v53;
    v81 = v53;
    if ( v53 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x289,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
        (const char *)(unsigned int)v53,
        v78);
      goto LABEL_60;
    }
    v97 = 0;
    v99 = 0;
    v54 = (_QWORD *)Windows::Internal::StringReference::StringReference(v112, L"Windows.Foundation.Uri");
    v55 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
            *v54,
            &v99);
    v6 = v55;
    v81 = v55;
    if ( v55 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x292,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
        (const char *)(unsigned int)v55,
        v78);
LABEL_64:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v99);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v97);
LABEL_60:
      if ( v98 )
        WindowsDeleteString(v98);
      goto LABEL_56;
    }
    v95 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v95);
    v56 = Windows::Internal::Security::Authentication::TokenBroker::CreateEmptyVector<Windows::Foundation::Uri *>(&v95);
    v6 = v56;
    v81 = v56;
    if ( v56 >= 0 )
    {
      ManagedUrls = _GetManagedUrls(a1, v95);
      if ( ManagedUrls >= 0 )
        goto LABEL_74;
      if ( (unsigned int)dword_180175000 > 3 )
      {
        LODWORD(v101) = ManagedUrls;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_180175000,
          (unsigned int)&word_180146856,
          0,
          v59,
          (__int64)&v101);
      }
      v56 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v95 + 120LL))(v95);
      v6 = v56;
      v81 = v56;
      if ( v56 >= 0 )
      {
LABEL_74:
        v60 = v99;
        v61 = *(int (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v99 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v97);
        if ( v61(v60, string, &v97) < 0
          || (v56 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v95 + 104LL))(v95, v97),
              v6 = v56,
              v81 = v56,
              v56 >= 0) )
        {
          v103 = 0;
          v62 = v95;
          v63 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v95 + 64LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v103);
          v64 = v63(v62, &v103);
          v6 = v64;
          v81 = v64;
          if ( v64 >= 0 )
          {
            v102 = 0;
            v65 = v103;
            v66 = v98;
            v67 = v87;
            v68 = v84;
            v69 = v96;
            v70 = (int)v93;
            v71 = (int)v89;
            v101 = string;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v102);
            v80 = v65;
            v72 = v92;
            v73 = Windows::Internal::Security::Authentication::Web::CWamProviderRegistrationInformation::MakeAndInitialize(
                    (unsigned int)&v102,
                    (_DWORD)v101,
                    v71,
                    v70,
                    (__int64)v69,
                    (__int64)v68,
                    (__int64)v92,
                    (__int64)v67,
                    (__int64)v66,
                    v80,
                    v86);
            v6 = v73;
            v81 = v73;
            if ( v73 >= 0 )
            {
              v75 = v102;
              v102 = 0;
              *v109 = v75;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x2B9,
                (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
                (const char *)(unsigned int)v73,
                v79);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v102);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v103);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v95);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v99);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v97);
            if ( v98 )
              WindowsDeleteString(v98);
            if ( v96 )
              WindowsDeleteString(v96);
            if ( v93 )
              WindowsDeleteString(v93);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v94);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
            if ( v89 )
              WindowsDeleteString(v89);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v90);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v88);
            if ( !v72 )
              goto LABEL_92;
            v33 = v72;
LABEL_91:
            WindowsDeleteString(v33);
LABEL_92:
            if ( v87 )
              WindowsDeleteString(v87);
            goto LABEL_94;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2AB,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
            (const char *)(unsigned int)v64,
            v78);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v103);
          goto LABEL_68;
        }
        v57 = 679;
      }
      else
      {
        v57 = 673;
      }
    }
    else
    {
      v57 = 661;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v57,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
      (const char *)(unsigned int)v56,
      v78);
LABEL_68:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v95);
    goto LABEL_64;
  }
  LastError = GetLastError();
  v77 = LastError;
  if ( LastError > 0 )
    v77 = (unsigned __int16)LastError | 0x80070000;
  Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&v110);
  if ( v93 )
    WindowsDeleteString(v93);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v94);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
  if ( v89 )
    WindowsDeleteString(v89);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v90);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v88);
  if ( v92 )
    WindowsDeleteString(v92);
  if ( v87 )
    WindowsDeleteString(v87);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
  if ( v84 )
    WindowsDeleteString(v84);
  if ( string )
    WindowsDeleteString(string);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v100);
  v108 = 0;
  lambda_ff3c5b7b9b1498b348a39200f0507ed4_::operator()(&v107);
  RoVariant::~RoVariant((RoVariant *)&v104);
  return v77;
}

```

## disassembly

```asm
0x180011400  mov     [rsp-8+arg_18], rbx
0x180011405  push    rbp
0x180011406  push    rsi
0x180011407  push    rdi
0x180011408  push    r12
0x18001140a  push    r13
0x18001140c  push    r14
0x18001140e  push    r15
0x180011410  lea     rbp, [rsp-2B0h]
0x180011418  sub     rsp, 3B0h
0x18001141f  mov     rax, cs:__security_cookie
0x180011426  xor     rax, rsp
0x180011429  mov     [rbp+2E0h+var_40], rax
0x180011430  mov     [rbp+2E0h+var_2A0], r8
0x180011434  mov     r15, rdx
0x180011437  mov     r14, rcx
0x18001143a  xor     r12d, r12d
0x18001143d  mov     [rsp+3E0h+var_380], r12d
0x180011442  mov     [rbp+2E0h+var_2C8], r12
0x180011446  mov     [rbp+2E0h+var_2C0], r12d
0x18001144a  lea     rcx, [rsp+3E0h+var_380]
0x18001144f  mov     [rbp+2E0h+var_2B0], rcx
0x180011453  mov     [rbp+2E0h+var_2A8], 1
0x180011457  mov     [r8], r12
0x18001145a  mov     [rbp+2E0h+var_2E8], r12
0x18001145e  lea     rcx, [rbp+2E0h+var_2E8]
0x180011462  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011467  lea     rdx, [rbp+2E0h+var_2E8]
0x18001146b  mov     rcx, r14
0x18001146e  call    ?_GetWebAccountProviderElementAttributes@@YAJPEAUIApplicationExtension@StateRepository@Internal@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@4@@Z; _GetWebAccountProviderElementAttributes(Windows::Internal::StateRepository::IApplicationExtension *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)
0x180011473  mov     edi, eax
0x180011475  mov     [rsp+3E0h+var_380], eax
0x180011479  test    eax, eax
0x18001147b  jns     short loc_18001149D
0x18001147d  mov     rcx, [rbp+2E8h]; this
0x180011484  mov     r9d, eax; char *
0x180011487  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18001148e  mov     edx, 22Eh; void *
0x180011493  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011498  jmp     loc_180011E48
0x18001149d  mov     [rsp+3E0h+string], r12
0x1800114a2  mov     rdi, [rbp+2E0h+var_2E8]
0x1800114a6  mov     rax, [rdi]
0x1800114a9  mov     rbx, [rax+30h]
0x1800114ad  lea     rax, [rbp+2E0h+var_2C8]
0x1800114b1  mov     [rbp+2E0h+var_298], rax
0x1800114b5  mov     qword ptr [rbp+2E0h+hstringHeader.Reserved], r12
0x1800114b9  lea     rdx, aUrl; "@Url"
0x1800114c0  lea     rcx, [rbp+2E0h+var_278]; string
0x1800114c4  call    ??$?0$04@StringReference@Internal@Windows@@QEAA@AEAY04$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[5])
0x1800114c9  lea     r8, [rbp+2E0h+hstringHeader]
0x1800114cd  mov     rdx, [rax]
0x1800114d0  mov     rcx, rdi
0x1800114d3  mov     rax, rbx
0x1800114d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114db  mov     edi, eax
0x1800114dd  mov     [rsp+3E0h+var_380], eax
0x1800114e1  mov     rdx, qword ptr [rbp+2E0h+hstringHeader.Reserved]; struct IInspectable *
0x1800114e5  mov     rcx, [rbp+2E0h+var_298]; this
0x1800114e9  call    ?Attach@RoVariant@@QEAAXPEAUIInspectable@@@Z; RoVariant::Attach(IInspectable *)
0x1800114ee  nop
0x1800114ef  test    edi, edi
0x1800114f1  jns     short loc_180011513
0x1800114f3  mov     r9d, edi; char *
0x1800114f6  mov     edx, 233h; void *
0x1800114fb  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180011502  mov     rcx, [rbp+2E8h]; this
0x180011509  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001150e  jmp     loc_180011E37
0x180011513  mov     rax, [rbp+2E0h+var_2C8]
0x180011517  mov     [rbp+2E0h+var_298], rax
0x18001151b  mov     eax, [rbp+2E0h+var_2C0]
0x18001151e  mov     dword ptr [rbp+2E0h+hstringHeader.Reserved], eax
0x180011521  mov     rcx, [rsp+3E0h+string]; string
0x180011526  call    cs:__imp_WindowsDeleteString
0x18001152c  mov     [rsp+3E0h+string], r12
0x180011531  lea     rdx, [rsp+3E0h+string]; HSTRING *
0x180011536  lea     rcx, [rbp+2E0h+var_298]; this
0x18001153a  call    ?GetString@Accessor@RoVariant@@QEBAJPEAPEAUHSTRING__@@@Z; RoVariant::Accessor::GetString(HSTRING__ * *)
0x18001153f  mov     edi, eax
0x180011541  mov     [rsp+3E0h+var_380], eax
0x180011545  test    eax, eax
0x180011547  jns     short loc_180011553
0x180011549  mov     r9d, eax
0x18001154c  mov     edx, 234h
0x180011551  jmp     short loc_1800114FB
0x180011553  mov     [rsp+3E0h+var_368], r12
0x180011558  mov     rdi, [rbp+2E0h+var_2E8]
0x18001155c  mov     rax, [rdi]
0x18001155f  mov     rbx, [rax+30h]
0x180011563  lea     rax, [rbp+2E0h+var_2C8]
0x180011567  mov     [rbp+2E0h+var_298], rax
0x18001156b  mov     qword ptr [rbp+2E0h+hstringHeader.Reserved], r12
0x18001156f  lea     rdx, aBackgroundentr; "@BackgroundEntryPoint"
0x180011576  lea     rcx, [rbp+2E0h+var_278]; string
0x18001157a  call    ??$?0$0BG@@StringReference@Internal@Windows@@QEAA@AEAY0BG@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[22])
0x18001157f  lea     r8, [rbp+2E0h+hstringHeader]
0x180011583  mov     rdx, [rax]
0x180011586  mov     rcx, rdi
0x180011589  mov     rax, rbx
0x18001158c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011591  mov     edi, eax
0x180011593  mov     [rsp+3E0h+var_380], eax
0x180011597  mov     rdx, qword ptr [rbp+2E0h+hstringHeader.Reserved]; struct IInspectable *
0x18001159b  mov     rcx, [rbp+2E0h+var_298]; this
0x18001159f  call    ?Attach@RoVariant@@QEAAXPEAUIInspectable@@@Z; RoVariant::Attach(IInspectable *)
0x1800115a4  nop
0x1800115a5  test    edi, edi
0x1800115a7  jns     short loc_1800115C9
0x1800115a9  mov     r9d, edi; char *
0x1800115ac  mov     edx, 239h; void *
0x1800115b1  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800115b8  mov     rcx, [rbp+2E8h]; this
0x1800115bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800115c4  jmp     loc_180011E26
0x1800115c9  mov     rax, [rbp+2E0h+var_2C8]
0x1800115cd  mov     [rbp+2E0h+var_298], rax
0x1800115d1  mov     eax, [rbp+2E0h+var_2C0]
0x1800115d4  mov     dword ptr [rbp+2E0h+hstringHeader.Reserved], eax
0x1800115d7  mov     rcx, [rsp+3E0h+var_368]; string
0x1800115dc  call    cs:__imp_WindowsDeleteString
0x1800115e2  mov     [rsp+3E0h+var_368], r12
0x1800115e7  lea     rdx, [rsp+3E0h+var_368]; HSTRING *
0x1800115ec  lea     rcx, [rbp+2E0h+var_298]; this
0x1800115f0  call    ?GetString@Accessor@RoVariant@@QEBAJPEAPEAUHSTRING__@@@Z; RoVariant::Accessor::GetString(HSTRING__ * *)
0x1800115f5  mov     edi, eax
0x1800115f7  mov     [rsp+3E0h+var_380], eax
0x1800115fb  test    eax, eax
0x1800115fd  jns     short loc_180011609
0x1800115ff  mov     r9d, eax
0x180011602  mov     edx, 23Ah
0x180011607  jmp     short loc_1800115B1
0x180011609  mov     [rsp+3E0h+var_370], r12
0x18001160e  mov     rax, [r14]
0x180011611  mov     rbx, [rax+48h]
0x180011615  lea     rcx, [rsp+3E0h+var_370]
0x18001161a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001161f  lea     rdx, [rsp+3E0h+var_370]
0x180011624  mov     rcx, r14
0x180011627  mov     rax, rbx
0x18001162a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001162f  mov     edi, eax
0x180011631  mov     [rsp+3E0h+var_380], eax
0x180011635  test    eax, eax
0x180011637  jns     short loc_180011659
0x180011639  mov     rcx, [rbp+2E8h]; this
0x180011640  mov     r9d, eax; char *
0x180011643  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18001164a  mov     edx, 23Dh; void *
0x18001164f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011654  jmp     loc_180011E1B
0x180011659  mov     [rbp+2E0h+var_360], r12
0x18001165d  mov     rdi, [rsp+3E0h+var_370]
0x180011662  mov     rax, [rdi]
0x180011665  mov     rbx, [rax+48h]
0x180011669  lea     rcx, [rbp+2E0h+var_360]
0x18001166d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011672  lea     rdx, [rbp+2E0h+var_360]
0x180011676  mov     rcx, rdi
0x180011679  mov     rax, rbx
0x18001167c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011681  mov     edi, eax
0x180011683  mov     [rsp+3E0h+var_380], eax
0x180011687  test    eax, eax
0x180011689  jns     short loc_1800116AB
0x18001168b  mov     rcx, [rbp+2E8h]; this
0x180011692  mov     r9d, eax; char *
0x180011695  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18001169c  mov     edx, 23Fh; void *
0x1800116a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800116a6  jmp     loc_180011E11
0x1800116ab  mov     [rbp+2E0h+var_350], r12
0x1800116af  mov     rdi, [rbp+2E0h+var_360]
0x1800116b3  mov     rax, [rdi]
0x1800116b6  mov     rbx, [rax+70h]
0x1800116ba  xor     ecx, ecx; string
0x1800116bc  call    cs:__imp_WindowsDeleteString
0x1800116c2  mov     [rbp+2E0h+var_350], r12
0x1800116c6  lea     rdx, [rbp+2E0h+var_350]
0x1800116ca  mov     rcx, rdi
0x1800116cd  mov     rax, rbx
0x1800116d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116d5  mov     edi, eax
0x1800116d7  mov     [rsp+3E0h+var_380], eax
0x1800116db  test    eax, eax
0x1800116dd  jns     short loc_1800116FF
0x1800116df  mov     r9d, eax; char *
0x1800116e2  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800116e9  mov     edx, 243h; void *
0x1800116ee  mov     rcx, [rbp+2E8h]; this
0x1800116f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800116fa  jmp     loc_180011E01
0x1800116ff  mov     dword ptr [rbp+2E0h+var_2E0], r12d
0x180011703  mov     rcx, [rbp+2E0h+var_360]
0x180011707  mov     rax, [rcx]
0x18001170a  lea     rdx, [rbp+2E0h+var_2E0]
0x18001170e  mov     rax, [rax+490h]
0x180011715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001171a  mov     rcx, [rbp+2E8h]; this
0x180011721  lea     rsi, aOnecoreDsSecur_16; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180011728  test    eax, eax
0x18001172a  jns     short loc_180011742
0x18001172c  mov     [rbp+2E0h+var_358], r12b
0x180011730  mov     r9d, eax; char *
0x180011733  mov     r8, rsi; unsigned int
0x180011736  mov     edx, 248h; void *
0x18001173b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180011740  jmp     short loc_18001174A
0x180011742  cmp     dword ptr [rbp+2E0h+var_2E0], 2
0x180011746  setz    [rbp+2E0h+var_358]
0x18001174a  mov     [rbp+2E0h+packageFamilyNameLength], 104h
0x180011751  xor     edx, edx; length
0x180011753  mov     rcx, [rbp+2E0h+var_350]; string
0x180011757  call    cs:__imp_WindowsGetStringRawBuffer
0x18001175d  lea     r8, [rbp+2E0h+packageFamilyName]; packageFamilyName
0x180011764  lea     rdx, [rbp+2E0h+packageFamilyNameLength]; packageFamilyNameLength
0x180011768  mov     rcx, rax; packageFullName
0x18001176b  call    cs:__imp_PackageFamilyNameFromFullName
0x180011771  mov     edi, eax
0x180011773  mov     r13d, 80070000h
0x180011779  test    eax, eax
0x18001177b  jle     short loc_180011783
0x18001177d  movzx   edi, ax
0x180011780  or      edi, r13d
0x180011783  mov     [rsp+3E0h+var_380], edi
0x180011787  test    edi, edi
0x180011789  jns     short loc_18001179B
0x18001178b  mov     r9d, edi
0x18001178e  mov     r8, rsi
0x180011791  mov     edx, 253h
0x180011796  jmp     loc_1800116EE
0x18001179b  mov     [rbp+2E0h+var_328], r12
0x18001179f  lea     rdx, [rbp+2E0h+packageFamilyName]; unsigned __int16 *
0x1800117a6  lea     rcx, [rbp+2E0h+var_328]; this
0x1800117aa  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x1800117af  mov     edi, eax
0x1800117b1  mov     [rsp+3E0h+var_380], eax
0x1800117b5  test    eax, eax
0x1800117b7  jns     short loc_1800117E3
0x1800117b9  mov     rcx, [rbp+2E8h]; this
0x1800117c0  mov     r9d, eax; char *
0x1800117c3  mov     r8, rsi; unsigned int
0x1800117c6  mov     edx, 256h; void *
0x1800117cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800117d0  nop
0x1800117d1  mov     rcx, [rbp+2E0h+var_328]
0x1800117d5  test    rcx, rcx
0x1800117d8  jz      loc_180011E01
0x1800117de  jmp     loc_180011DFA
0x1800117e3  mov     [rbp+2E0h+var_348], r12
0x1800117e7  lea     r9, [rbp+2E0h+var_298]; string
0x1800117eb  lea     r8, [rbp+2E0h+hstringHeader]; hstringHeader
0x1800117ef  mov     edx, 3Ch ; '<'; length
0x1800117f4  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_ApplicationResourceResolver@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x1800117fb  call    cs:__imp_WindowsCreateStringReference
0x180011801  test    eax, eax
0x180011803  jns     short loc_18001181A
0x180011805  xor     r9d, r9d; lpArguments
0x180011808  xor     r8d, r8d; nNumberOfArguments
0x18001180b  lea     edx, [r9+1]; dwExceptionFlags
0x18001180f  mov     ecx, 0C000000Dh; dwExceptionCode
0x180011814  call    cs:__imp_RaiseException
0x18001181a  mov     rbx, [rbp+2E0h+var_298]
0x18001181e  lea     rcx, [rbp+2E0h+var_348]
0x180011822  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011827  lea     r8, [rbp+2E0h+var_348]
0x18001182b  lea     rdx, _GUID_84463b2a_c88e_4597_b41f_17d3bf6486e9
0x180011832  mov     rcx, rbx
0x180011835  call    cs:__imp_RoGetActivationFactory
0x18001183b  mov     edi, eax
0x18001183d  mov     [rsp+3E0h+var_380], eax
0x180011841  test    eax, eax
0x180011843  jns     short loc_18001186B
0x180011845  mov     rcx, [rbp+2E8h]; this
0x18001184c  mov     r9d, eax; char *
0x18001184f  mov     r8, rsi; unsigned int
0x180011852  mov     edx, 25Ch; void *
0x180011857  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001185c  nop
0x18001185d  lea     rcx, [rbp+2E0h+var_348]
0x180011861  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011866  jmp     loc_1800117D1
0x18001186b  mov     [rbp+2E0h+var_338], r12
0x18001186f  mov     rdi, [rbp+2E0h+var_348]
0x180011873  mov     rax, [rdi]
0x180011876  mov     rbx, [rax+30h]
0x18001187a  lea     rcx, [rbp+2E0h+var_338]
0x18001187e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011883  lea     r8, [rbp+2E0h+var_338]
0x180011887  mov     rdx, [rsp+3E0h+var_370]
0x18001188c  mov     rcx, rdi
0x18001188f  mov     rax, rbx
0x180011892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011897  mov     edi, eax
0x180011899  mov     [rsp+3E0h+var_380], eax
0x18001189d  test    eax, eax
0x18001189f  jns     short loc_1800118C4
0x1800118a1  mov     rcx, [rbp+2E8h]; this
0x1800118a8  mov     r9d, eax; char *
0x1800118ab  mov     r8, rsi; unsigned int
  ... truncated ...
```
