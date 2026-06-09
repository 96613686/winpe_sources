# Windows::System::Internal::UserManagerStatics::ConvertSponsoredUserToOnline(uint,Windows::System::IUser *,bool,long *)

- ea: `0x18008de44`
- end: `0x18008e8ab`
- name: `?ConvertSponsoredUserToOnline@UserManagerStatics@Internal@System@Windows@@AEAAJIPEAUIUser@34@_NPEAJ@Z`
- size: `2663`
- prototype: `__int64 __usercall@<rax>(Windows::System::Internal::UserManagerStatics *__hidden this@<rcx>, unsigned int@<edx>, struct Windows::System::IUser *@<r8>, bool@<r9b>, int *)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18008e8b4`

## callees

- `0x180006130`
- `0x180007920`
- `0x1800088e8`
- `0x18000ce48`
- `0x18000ed00`
- `0x180015540`
- `0x1800181f0`
- `0x180024828`
- `0x18002799c`
- `0x1800332e8`
- `0x18004b3d0`
- `0x18004ba28`
- `0x180050c38`
- `0x1800513d0`
- `0x180060524`
- `0x1800624bc`
- `0x18008de44`
- `0x180092d74`
- `0x180092dd4`
- `0x180094884`
- `0x1800bff28`
- `0x1800c0008`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e1c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e293`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e2a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e846`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e1c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e293`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e2a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e846`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e088`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e0bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e15d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e3f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e407`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e415`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e088`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e0bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e15d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e3f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e407`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e415`

## string_xrefs

- `0x18008dfe9`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18008e768`: `Privileges`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall Windows::System::Internal::UserManagerStatics::ConvertSponsoredUserToOnline(
        Windows::System::Internal::UserManagerStatics *this,
        unsigned int a2,
        struct Windows::System::IUser *a3,
        char a4,
        int *a5)
{
  char *v9; // rsi
  __int64 v10; // rcx
  int v11; // r8d
  int v12; // r9d
  int SponsoringUser; // eax
  unsigned int v14; // ebx
  __int64 v15; // rdx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, _QWORD, __int64 *); // rbx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rbx
  Windows::System::Internal::UserManagerStatics *v20; // rcx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, HSTRING *); // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 v24; // rsi
  __int64 (__fastcall *v25)(__int64, _QWORD, PCWSTR, PCWSTR); // rdi
  PCWSTR v26; // rbx
  PCWSTR v27; // rax
  int v28; // eax
  PVOID Reserved1; // rbx
  PVOID v31; // rbx
  PVOID v32; // rbx
  PVOID v33; // rbx
  PVOID v34; // rbx
  PVOID v35; // rbx
  PVOID v36; // rbx
  PVOID v37; // rbx
  __int64 v38; // rsi
  __int64 (__fastcall *v39)(__int64, PCWSTR, __int64); // rdi
  __int64 v40; // rbx
  PCWSTR v41; // rax
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *UserStaticsInternal; // rax
  __int64 *v43; // [rsp+20h] [rbp-E0h]
  _BYTE v44[4]; // [rsp+70h] [rbp-90h] BYREF
  int v45; // [rsp+74h] [rbp-8Ch] BYREF
  _BYTE v46[8]; // [rsp+78h] [rbp-88h] BYREF
  int v47[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v48; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v49; // [rsp+90h] [rbp-70h] BYREF
  __int64 v50; // [rsp+98h] [rbp-68h] BYREF
  HSTRING v51; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v52; // [rsp+A8h] [rbp-58h] BYREF
  HSTRING string; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING v54; // [rsp+B8h] [rbp-48h] BYREF
  __int64 (__fastcall ***v55)(_QWORD, GUID *, __int64); // [rsp+C0h] [rbp-40h] BYREF
  __int64 v56; // [rsp+C8h] [rbp-38h] BYREF
  __int64 (__fastcall ***v57)(_QWORD, GUID *, __int64 *); // [rsp+D0h] [rbp-30h] BYREF
  void *v58; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v59; // [rsp+E0h] [rbp-20h] BYREF
  struct Windows::System::IUser *v60; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v61; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v62; // [rsp+F8h] [rbp-8h]
  __int64 v63; // [rsp+100h] [rbp+0h]
  __int64 v64; // [rsp+108h] [rbp+8h] BYREF
  __int64 v65; // [rsp+110h] [rbp+10h]
  __int64 v66; // [rsp+118h] [rbp+18h]
  __int64 v67; // [rsp+120h] [rbp+20h] BYREF
  __int64 v68; // [rsp+128h] [rbp+28h]
  __int64 v69; // [rsp+130h] [rbp+30h]
  __int64 v70; // [rsp+138h] [rbp+38h] BYREF
  __int64 v71; // [rsp+140h] [rbp+40h]
  __int64 v72; // [rsp+148h] [rbp+48h]
  __int64 v73; // [rsp+150h] [rbp+50h] BYREF
  __int64 v74; // [rsp+158h] [rbp+58h]
  __int64 v75; // [rsp+160h] [rbp+60h]
  __int64 v76; // [rsp+168h] [rbp+68h] BYREF
  __int64 v77; // [rsp+170h] [rbp+70h]
  __int64 v78; // [rsp+178h] [rbp+78h]
  __int64 v79; // [rsp+180h] [rbp+80h] BYREF
  __int64 v80; // [rsp+188h] [rbp+88h]
  __int64 v81; // [rsp+190h] [rbp+90h]
  __int64 v82; // [rsp+198h] [rbp+98h] BYREF
  __int64 v83; // [rsp+1A0h] [rbp+A0h]
  __int64 v84; // [rsp+1A8h] [rbp+A8h]
  int **v85; // [rsp+1B0h] [rbp+B0h]
  int *v86; // [rsp+1B8h] [rbp+B8h]
  char v87; // [rsp+1C0h] [rbp+C0h]
  _BYTE v88[64]; // [rsp+1D0h] [rbp+D0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+210h] [rbp+110h] BYREF
  __int64 v90; // [rsp+228h] [rbp+128h]
  HSTRING_HEADER v91; // [rsp+230h] [rbp+130h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v9 = (char *)this + 552;
  if ( !(*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 69) + 8LL))((char *)this + 552) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v10);
  v45 = 0;
  v54 = 0;
  v49 = 0;
  v51 = 0;
  string = 0;
  v82 = 0;
  v83 = 0;
  v84 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  v70 = 0;
  v71 = 0;
  v72 = 0;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v60 = 0;
  v57 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))a3;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v57);
  v56 = 0;
  v52 = 0;
  v50 = 0;
  v55 = 0;
  v48 = 0;
  v44[0] = 0;
  v58 = 0;
  v59 = 0;
  v85 = &a5;
  v86 = &v45;
  v87 = 1;
  if ( (unsigned int)dword_180146228 > 4 )
  {
    v47[0] = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180146228,
      (unsigned int)&unk_180126428,
      v11,
      v12,
      (__int64)v47);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
  SponsoringUser = Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Localize(
                     v9,
                     &GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5,
                     &v50);
  v14 = SponsoringUser;
  if ( SponsoringUser < 0 )
  {
    v15 = 2595;
    goto LABEL_9;
  }
  SponsoringUser = Windows::System::Internal::UserManagerStatics::GetSponsoringUser(this, &v49, &v60);
  v14 = SponsoringUser;
  if ( SponsoringUser < 0 )
  {
    v15 = 2598;
    goto LABEL_9;
  }
  SponsoringUser = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 67) + 120LL))(
                     *((_QWORD *)this + 67),
                     v49);
  v14 = SponsoringUser;
  if ( SponsoringUser < 0 )
  {
    v15 = 2600;
    goto LABEL_9;
  }
  v16 = *((_QWORD *)this + 67);
  v17 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v16 + 96LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
  SponsoringUser = v17(v16, v49, &v52);
  v14 = SponsoringUser;
  if ( SponsoringUser < 0 )
  {
    v15 = 2601;
    goto LABEL_9;
  }
  v18 = v52;
  v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v52 + 64LL);
  WindowsDeleteString(string);
  string = 0;
  SponsoringUser = v19(v18, &string);
  v14 = SponsoringUser;
  if ( SponsoringUser < 0 )
  {
    v15 = 2602;
    goto LABEL_9;
  }
  WindowsDeleteString(v51);
  v51 = 0;
  SponsoringUser = Windows::System::Internal::UserManagerStatics::GetSponsoredUserName(v20, a2, &v51);
  v14 = SponsoringUser;
  if ( SponsoringUser < 0 )
  {
    v15 = 2604;
    goto LABEL_9;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
  SponsoringUser = Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Localize(
                     v9,
                     &GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5,
                     &v50);
  v14 = SponsoringUser;
  if ( SponsoringUser < 0 )
  {
    v15 = 2605;
    goto LABEL_9;
  }
  SponsoringUser = Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
                     &v57,
                     &v56);
  v14 = SponsoringUser;
  if ( SponsoringUser < 0 )
  {
    v15 = 2607;
    goto LABEL_9;
  }
  SponsoringUser = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v56 + 80LL))(v56, &v58);
  v14 = SponsoringUser;
  if ( SponsoringUser < 0 )
  {
    v15 = 2608;
    goto LABEL_9;
  }
  v21 = v52;
  v22 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v52 + 56LL);
  WindowsDeleteString(v54);
  v54 = 0;
  SponsoringUser = v22(v21, &v54);
  v14 = SponsoringUser;
  if ( SponsoringUser < 0 )
  {
    v15 = 2609;
    goto LABEL_9;
  }
  v46[0] = 0;
  SponsoringUser = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v52 + 80LL))(v52, v46);
  v14 = SponsoringUser;
  if ( SponsoringUser < 0 )
  {
    v15 = 2612;
    goto LABEL_9;
  }
  if ( v46[0] )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(v54, 0);
    Windows::System::Internal::Implementation::AutoUserContext::AutoUserContext(
      (Windows::System::Internal::Implementation::AutoUserContext *)v88,
      v58,
      StringRawBuffer);
    v24 = v50;
    v25 = *(__int64 (__fastcall **)(__int64, _QWORD, PCWSTR, PCWSTR))(*(_QWORD *)v50 + 616LL);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v61);
    v62 = -1;
    v63 = -1;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v64);
    v65 = -1;
    v66 = -1;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v67);
    v68 = -1;
    v69 = -1;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v70);
    v71 = -1;
    v72 = -1;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v73);
    v74 = -1;
    v75 = -1;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v76);
    v77 = -1;
    v78 = -1;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v79);
    v80 = -1;
    v81 = -1;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v82);
    v83 = -1;
    v84 = -1;
    v26 = WindowsGetStringRawBuffer(string, 0);
    v27 = WindowsGetStringRawBuffer(v51, 0);
    v43 = &v82;
    v28 = v25(v24, a2, v27, v26);
    v45 = v28;
    if ( v28 < 0 )
    {
      if ( a4 && (unsigned __int8)Windows::System::Internal::IsConnectivityError((unsigned int)v28) )
        Windows::System::Internal::Implementation::UserOnlineConversionTracker::WaitForConnectivityError(
          (LPCRITICAL_SECTION)((char *)this + 384),
          a2);
      Windows::System::Internal::Implementation::AutoUserContext::Revoke((Windows::System::Internal::Implementation::AutoUserContext *)v88);
      goto LABEL_35;
    }
    Windows::System::Internal::Implementation::AutoUserContext::Revoke((Windows::System::Internal::Implementation::AutoUserContext *)v88);
    v90 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Foundation.Collections.PropertySet",
      0x2Bu,
      0x2Au);
    SponsoringUser = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
                       v90,
                       &v55);
    v14 = SponsoringUser;
    if ( SponsoringUser < 0 )
    {
      v15 = 2642;
      goto LABEL_9;
    }
    SponsoringUser = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
                       &v55,
                       (__int64)&v48);
    v14 = SponsoringUser;
    if ( SponsoringUser < 0 )
    {
      v15 = 2644;
      goto LABEL_9;
    }
    *(_QWORD *)v47 = v82;
    Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v91, (const WCHAR **)v47)[1].Reserved.Reserved1;
    v90 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"UserData", 9u, 8u);
    SponsoringUser = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
                       v48,
                       v90,
                       (__int64)Reserved1,
                       (__int64)v44);
    v14 = SponsoringUser;
    if ( SponsoringUser < 0 )
    {
      v15 = 2646;
      goto LABEL_9;
    }
    *(_QWORD *)v47 = v79;
    v31 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v91, (const WCHAR **)v47)[1].Reserved.Reserved1;
    v90 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"XboxUserId", 0xBu, 0xAu);
    SponsoringUser = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
                       v48,
                       v90,
                       (__int64)v31,
                       (__int64)v44);
    v14 = SponsoringUser;
    if ( SponsoringUser < 0 )
    {
      v15 = 2647;
      goto LABEL_9;
    }
    *(_QWORD *)v47 = v76;
    v32 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v91, (const WCHAR **)v47)[1].Reserved.Reserved1;
    v90 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Gamertag", 9u, 8u);
    SponsoringUser = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
                       v48,
                       v90,
                       (__int64)v32,
                       (__int64)v44);
    v14 = SponsoringUser;
    if ( SponsoringUser < 0 )
    {
      v15 = 2648;
      goto LABEL_9;
    }
    *(_QWORD *)v47 = v73;
    v33 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v91, (const WCHAR **)v47)[1].Reserved.Reserved1;
    v90 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ModernGamertag", 0xFu, 0xEu);
    SponsoringUser = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
                       v48,
                       v90,
                       (__int64)v33,
                       (__int64)v44);
    v14 = SponsoringUser;
    if ( SponsoringUser < 0 )
    {
      v15 = 2649;
      goto LABEL_9;
    }
    *(_QWORD *)v47 = v70;
    v34 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v91, (const WCHAR **)v47)[1].Reserved.Reserved1;
    v90 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ModernGamertagSuffix", 0x15u, 0x14u);
    SponsoringUser = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
                       v48,
                       v90,
                       (__int64)v34,
                       (__int64)v44);
    v14 = SponsoringUser;
    if ( SponsoringUser < 0 )
    {
      v15 = 2650;
      goto LABEL_9;
    }
    *(_QWORD *)v47 = v67;
    v35 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v91, (const WCHAR **)v47)[1].Reserved.Reserved1;
    v90 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"UniqueModernGamertag", 0x15u, 0x14u);
    SponsoringUser = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
                       v48,
                       v90,
                       (__int64)v35,
                       (__int64)v44);
    v14 = SponsoringUser;
    if ( SponsoringUser < 0 )
    {
      v15 = 2651;
      goto LABEL_9;
    }
    *(_QWORD *)v47 = v64;
    v36 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v91, (const WCHAR **)v47)[1].Reserved.Reserved1;
    v90 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Privileges", 0xBu, 0xAu);
    SponsoringUser = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
                       v48,
                       v90,
                       (__int64)v36,
                       (__int64)v44);
    v14 = SponsoringUser;
    if ( SponsoringUser < 0 )
    {
      v15 = 2652;
      goto LABEL_9;
    }
    *(_QWORD *)v47 = v61;
    v37 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v91, (const WCHAR **)v47)[1].Reserved.Reserved1;
    v90 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"AgeGroup", 9u, 8u);
    SponsoringUser = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
                       v48,
                       v90,
                       (__int64)v37,
                       (__int64)v44);
    v14 = SponsoringUser;
    if ( SponsoringUser < 0 )
    {
      v15 = 2653;
      goto LABEL_9;
    }
    SponsoringUser = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v56 + 88LL))(v56, &v59);
    v14 = SponsoringUser;
    if ( SponsoringUser < 0 )
    {
      v15 = 2655;
      goto LABEL_9;
    }
    v38 = v50;
    v39 = *(__int64 (__fastcall **)(__int64, PCWSTR, __int64))(*(_QWORD *)v50 + 432LL);
    v40 = v59;
    v41 = WindowsGetStringRawBuffer(v51, 0);
    SponsoringUser = v39(v38, v41, v40);
    v14 = SponsoringUser;
    if ( SponsoringUser < 0 )
    {
      v15 = 2656;
      goto LABEL_9;
    }
    UserStaticsInternal = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(this);
    SponsoringUser = (*(__int64 (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, struct Windows::System::IUser *, __int64, __int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*(_QWORD *)UserStaticsInternal + 120LL))(
                       UserStaticsInternal,
                       a3,
                       2,
                       v55);
    v14 = SponsoringUser;
    if ( SponsoringUser < 0 )
    {
      v15 = 2658;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)SponsoringUser,
        (int)v43);
      if ( a5 )
        *a5 = v45;
      goto LABEL_38;
    }
  }
LABEL_35:
  if ( a5 )
    *a5 = v45;
  v14 = 0;
LABEL_38:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v57);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v60);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v61);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v64);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v67);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v70);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v73);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v76);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v79);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v82);
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v51);
  v51 = 0;
  WindowsDeleteString(v54);
  return v14;
}

```

## disassembly

```asm
0x18008de44  mov     [rsp-8+arg_10], rbx
0x18008de49  push    rbp
0x18008de4a  push    rsi
0x18008de4b  push    rdi
0x18008de4c  push    r12
0x18008de4e  push    r13
0x18008de50  push    r14
0x18008de52  push    r15
0x18008de54  lea     rbp, [rsp-160h]
0x18008de5c  sub     rsp, 260h
0x18008de63  mov     rax, cs:__security_cookie
0x18008de6a  xor     rax, rsp
0x18008de6d  mov     [rbp+190h+var_40], rax
0x18008de74  mov     r13b, r9b
0x18008de77  mov     r12, r8
0x18008de7a  mov     r15d, edx
0x18008de7d  mov     r14, rcx
0x18008de80  lea     rsi, [rcx+228h]
0x18008de87  mov     rax, [rsi]
0x18008de8a  mov     rcx, rsi
0x18008de8d  mov     rax, [rax+8]
0x18008de91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008de96  xor     edi, edi
0x18008de98  test    al, al
0x18008de9a  jnz     short loc_18008DEA1
0x18008de9c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008dea1  mov     [rsp+290h+var_21C], edi
0x18008dea5  mov     [rbp+190h+var_1D8], rdi
0x18008dea9  mov     [rbp+190h+var_200], edi
0x18008deac  mov     [rbp+190h+var_1F0], rdi
0x18008deb0  mov     [rbp+190h+string], rdi
0x18008deb4  mov     [rbp+190h+var_F8], rdi
0x18008debb  mov     [rbp+190h+var_F0], rdi
0x18008dec2  mov     [rbp+190h+var_E8], rdi
0x18008dec9  mov     [rbp+190h+var_110], rdi
0x18008ded0  mov     [rbp+190h+var_108], rdi
0x18008ded7  mov     [rbp+190h+var_100], rdi
0x18008dede  mov     [rbp+190h+var_128], rdi
0x18008dee2  mov     [rbp+190h+var_120], rdi
0x18008dee6  mov     [rbp+190h+var_118], rdi
0x18008deea  mov     [rbp+190h+var_140], rdi
0x18008deee  mov     [rbp+190h+var_138], rdi
0x18008def2  mov     [rbp+190h+var_130], rdi
0x18008def6  mov     [rbp+190h+var_158], rdi
0x18008defa  mov     [rbp+190h+var_150], rdi
0x18008defe  mov     [rbp+190h+var_148], rdi
0x18008df02  mov     [rbp+190h+var_170], rdi
0x18008df06  mov     [rbp+190h+var_168], rdi
0x18008df0a  mov     [rbp+190h+var_160], rdi
0x18008df0e  mov     [rbp+190h+var_188], rdi
0x18008df12  mov     [rbp+190h+var_180], rdi
0x18008df16  mov     [rbp+190h+var_178], rdi
0x18008df1a  mov     [rbp+190h+var_1A0], rdi
0x18008df1e  mov     [rbp+190h+var_198], rdi
0x18008df22  mov     [rbp+190h+var_190], rdi
0x18008df26  mov     [rbp+190h+var_1A8], rdi
0x18008df2a  mov     [rbp+190h+var_1C0], r12
0x18008df2e  lea     rcx, [rbp+190h+var_1C0]
0x18008df32  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18008df37  nop
0x18008df38  mov     [rbp+190h+var_1C8], rdi
0x18008df3c  mov     [rbp+190h+var_1E8], rdi
0x18008df40  mov     [rbp+190h+var_1F8], rdi
0x18008df44  mov     [rbp+190h+var_1D0], rdi
0x18008df48  mov     [rbp+190h+var_208], rdi
0x18008df4c  mov     [rsp+290h+var_220], dil
0x18008df51  mov     [rbp+190h+var_1B8], rdi
0x18008df55  mov     [rbp+190h+var_1B0], rdi
0x18008df59  lea     rax, [rbp+190h+arg_20]
0x18008df60  mov     [rbp+190h+var_E0], rax
0x18008df67  lea     rax, [rsp+290h+var_21C]
0x18008df6c  mov     [rbp+190h+var_D8], rax
0x18008df73  mov     [rbp+190h+var_D0], 1
0x18008df7a  mov     eax, cs:dword_180146228
0x18008df80  cmp     eax, 4
0x18008df83  jbe     short loc_18008DFA5
0x18008df85  mov     [rbp+190h+var_210], r15d
0x18008df89  lea     rax, [rbp+190h+var_210]
0x18008df8d  mov     qword ptr [rsp+290h+var_270], rax; int
0x18008df92  lea     rdx, unk_180126428
0x18008df99  lea     rcx, dword_180146228
0x18008dfa0  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18008dfa5  lea     rcx, [rbp+190h+var_1F8]
0x18008dfa9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008dfae  lea     r8, [rbp+190h+var_1F8]
0x18008dfb2  lea     rdx, _GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5
0x18008dfb9  mov     rcx, rsi
0x18008dfbc  call    ?Localize@?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@IEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Localize(_GUID const &,void * *)
0x18008dfc1  mov     ebx, eax
0x18008dfc3  test    eax, eax
0x18008dfc5  jns     short loc_18008DFCE
0x18008dfc7  mov     edx, 0A23h
0x18008dfcc  jmp     short loc_18008DFE9
0x18008dfce  lea     r8, [rbp+190h+var_1A8]; struct Windows::System::IUser **
0x18008dfd2  lea     rdx, [rbp+190h+var_200]; unsigned int *
0x18008dfd6  mov     rcx, r14; this
0x18008dfd9  call    ?GetSponsoringUser@UserManagerStatics@Internal@System@Windows@@AEAAJPEAIPEAPEAUIUser@34@@Z; Windows::System::Internal::UserManagerStatics::GetSponsoringUser(uint *,Windows::System::IUser * *)
0x18008dfde  mov     ebx, eax
0x18008dfe0  test    eax, eax
0x18008dfe2  jns     short loc_18008E01B
0x18008dfe4  mov     edx, 0A26h; void *
0x18008dfe9  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x18008dff0  mov     r9d, eax; char *
0x18008dff3  mov     rcx, [rbp+198h]; this
0x18008dffa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008dfff  nop
0x18008e000  mov     rcx, [rbp+190h+arg_20]
0x18008e007  test    rcx, rcx
0x18008e00a  jz      loc_18008E359
0x18008e010  mov     eax, [rsp+290h+var_21C]
0x18008e014  mov     [rcx], eax
0x18008e016  jmp     loc_18008E359
0x18008e01b  mov     rcx, [r14+218h]
0x18008e022  mov     rax, [rcx]
0x18008e025  mov     edx, [rbp+190h+var_200]
0x18008e028  mov     rax, [rax+78h]
0x18008e02c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e031  mov     ebx, eax
0x18008e033  test    eax, eax
0x18008e035  jns     short loc_18008E03E
0x18008e037  mov     edx, 0A28h
0x18008e03c  jmp     short loc_18008DFE9
0x18008e03e  mov     rdi, [r14+218h]
0x18008e045  mov     rax, [rdi]
0x18008e048  mov     rbx, [rax+60h]
0x18008e04c  lea     rcx, [rbp+190h+var_1E8]
0x18008e050  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008e055  lea     r8, [rbp+190h+var_1E8]
0x18008e059  mov     edx, [rbp+190h+var_200]
0x18008e05c  mov     rcx, rdi
0x18008e05f  mov     rax, rbx
0x18008e062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e067  mov     ebx, eax
0x18008e069  xor     edi, edi
0x18008e06b  test    eax, eax
0x18008e06d  jns     short loc_18008E079
0x18008e06f  mov     edx, 0A29h
0x18008e074  jmp     loc_18008DFE9
0x18008e079  mov     rdi, [rbp+190h+var_1E8]
0x18008e07d  mov     rax, [rdi]
0x18008e080  mov     rbx, [rax+40h]
0x18008e084  mov     rcx, [rbp+190h+string]; string
0x18008e088  call    cs:__imp_WindowsDeleteString
0x18008e08e  mov     [rbp+190h+string], 0
0x18008e096  lea     rdx, [rbp+190h+string]
0x18008e09a  mov     rcx, rdi
0x18008e09d  mov     rax, rbx
0x18008e0a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e0a5  mov     ebx, eax
0x18008e0a7  xor     edi, edi
0x18008e0a9  test    eax, eax
0x18008e0ab  jns     short loc_18008E0B7
0x18008e0ad  mov     edx, 0A2Ah
0x18008e0b2  jmp     loc_18008DFE9
0x18008e0b7  mov     rcx, [rbp+190h+var_1F0]; string
0x18008e0bb  call    cs:__imp_WindowsDeleteString
0x18008e0c1  mov     [rbp+190h+var_1F0], rdi
0x18008e0c5  lea     r8, [rbp+190h+var_1F0]; HSTRING *
0x18008e0c9  mov     edx, r15d; unsigned int
0x18008e0cc  call    ?GetSponsoredUserName@UserManagerStatics@Internal@System@Windows@@AEAAJIPEAPEAUHSTRING__@@@Z; Windows::System::Internal::UserManagerStatics::GetSponsoredUserName(uint,HSTRING__ * *)
0x18008e0d1  mov     ebx, eax
0x18008e0d3  test    eax, eax
0x18008e0d5  jns     short loc_18008E0E1
0x18008e0d7  mov     edx, 0A2Ch
0x18008e0dc  jmp     loc_18008DFE9
0x18008e0e1  lea     rcx, [rbp+190h+var_1F8]
0x18008e0e5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008e0ea  lea     r8, [rbp+190h+var_1F8]
0x18008e0ee  lea     rdx, _GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5
0x18008e0f5  mov     rcx, rsi
0x18008e0f8  call    ?Localize@?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@IEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Localize(_GUID const &,void * *)
0x18008e0fd  mov     ebx, eax
0x18008e0ff  test    eax, eax
0x18008e101  jns     short loc_18008E10D
0x18008e103  mov     edx, 0A2Dh
0x18008e108  jmp     loc_18008DFE9
0x18008e10d  lea     rdx, [rbp+190h+var_1C8]
0x18008e111  lea     rcx, [rbp+190h+var_1C0]
0x18008e115  call    ??$As@UIUserInternal@Implementation@Internal@System@Windows@@@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserInternal>>)
0x18008e11a  mov     ebx, eax
0x18008e11c  test    eax, eax
0x18008e11e  jns     short loc_18008E12A
0x18008e120  mov     edx, 0A2Fh
0x18008e125  jmp     loc_18008DFE9
0x18008e12a  mov     rcx, [rbp+190h+var_1C8]
0x18008e12e  mov     rax, [rcx]
0x18008e131  lea     rdx, [rbp+190h+var_1B8]
0x18008e135  mov     rax, [rax+50h]
0x18008e139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e13e  mov     ebx, eax
0x18008e140  test    eax, eax
0x18008e142  jns     short loc_18008E14E
0x18008e144  mov     edx, 0A30h
0x18008e149  jmp     loc_18008DFE9
0x18008e14e  mov     rdi, [rbp+190h+var_1E8]
0x18008e152  mov     rax, [rdi]
0x18008e155  mov     rbx, [rax+38h]
0x18008e159  mov     rcx, [rbp+190h+var_1D8]; string
0x18008e15d  call    cs:__imp_WindowsDeleteString
0x18008e163  mov     [rbp+190h+var_1D8], 0
0x18008e16b  lea     rdx, [rbp+190h+var_1D8]
0x18008e16f  mov     rcx, rdi
0x18008e172  mov     rax, rbx
0x18008e175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e17a  mov     ebx, eax
0x18008e17c  xor     edi, edi
0x18008e17e  test    eax, eax
0x18008e180  jns     short loc_18008E18C
0x18008e182  mov     edx, 0A31h
0x18008e187  jmp     loc_18008DFE9
0x18008e18c  mov     [rsp+290h+var_218], dil
0x18008e191  mov     rcx, [rbp+190h+var_1E8]
0x18008e195  mov     rax, [rcx]
0x18008e198  lea     rdx, [rsp+290h+var_218]
0x18008e19d  mov     rax, [rax+50h]
0x18008e1a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e1a6  mov     ebx, eax
0x18008e1a8  test    eax, eax
0x18008e1aa  jns     short loc_18008E1B6
0x18008e1ac  mov     edx, 0A34h
0x18008e1b1  jmp     loc_18008DFE9
0x18008e1b6  cmp     [rsp+290h+var_218], dil
0x18008e1bb  jz      loc_18008E345
0x18008e1c1  xor     edx, edx; length
0x18008e1c3  mov     rcx, [rbp+190h+var_1D8]; string
0x18008e1c7  call    cs:__imp_WindowsGetStringRawBuffer
0x18008e1cd  mov     r8, rax; unsigned __int16 *
0x18008e1d0  mov     rdx, [rbp+190h+var_1B8]; void *
0x18008e1d4  lea     rcx, [rbp+190h+var_C0]; this
0x18008e1db  call    ??0AutoUserContext@Implementation@Internal@System@Windows@@QEAA@PEAXPEBG@Z; Windows::System::Internal::Implementation::AutoUserContext::AutoUserContext(void *,ushort const *)
0x18008e1e0  nop
0x18008e1e1  mov     rsi, [rbp+190h+var_1F8]
0x18008e1e5  mov     rax, [rsi]
0x18008e1e8  mov     rdi, [rax+268h]
0x18008e1ef  lea     rcx, [rbp+190h+var_1A0]
0x18008e1f3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18008e1f8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18008e1fc  mov     [rbp+190h+var_198], rbx
0x18008e200  mov     [rbp+190h+var_190], rbx
0x18008e204  lea     rcx, [rbp+190h+var_188]
0x18008e208  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18008e20d  mov     [rbp+190h+var_180], rbx
0x18008e211  mov     [rbp+190h+var_178], rbx
0x18008e215  lea     rcx, [rbp+190h+var_170]
0x18008e219  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18008e21e  mov     [rbp+190h+var_168], rbx
0x18008e222  mov     [rbp+190h+var_160], rbx
0x18008e226  lea     rcx, [rbp+190h+var_158]
0x18008e22a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18008e22f  mov     [rbp+190h+var_150], rbx
0x18008e233  mov     [rbp+190h+var_148], rbx
0x18008e237  lea     rcx, [rbp+190h+var_140]
0x18008e23b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18008e240  mov     [rbp+190h+var_138], rbx
0x18008e244  mov     [rbp+190h+var_130], rbx
0x18008e248  lea     rcx, [rbp+190h+var_128]
0x18008e24c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18008e251  mov     [rbp+190h+var_120], rbx
0x18008e255  mov     [rbp+190h+var_118], rbx
0x18008e259  lea     rcx, [rbp+190h+var_110]
0x18008e260  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18008e265  mov     [rbp+190h+var_108], rbx
0x18008e26c  mov     [rbp+190h+var_100], rbx
0x18008e273  lea     rcx, [rbp+190h+var_F8]
0x18008e27a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18008e27f  mov     [rbp+190h+var_F0], rbx
0x18008e286  mov     [rbp+190h+var_E8], rbx
0x18008e28d  xor     edx, edx; length
0x18008e28f  mov     rcx, [rbp+190h+string]; string
0x18008e293  call    cs:__imp_WindowsGetStringRawBuffer
0x18008e299  mov     rbx, rax
0x18008e29c  xor     edx, edx; length
0x18008e29e  mov     rcx, [rbp+190h+var_1F0]; string
0x18008e2a2  call    cs:__imp_WindowsGetStringRawBuffer
0x18008e2a8  lea     rcx, [rbp+190h+var_1A0]
0x18008e2ac  mov     [rsp+290h+var_238], rcx
0x18008e2b1  lea     rcx, [rbp+190h+var_188]
0x18008e2b5  mov     [rsp+290h+var_240], rcx
0x18008e2ba  lea     rcx, [rbp+190h+var_170]
0x18008e2be  mov     [rsp+290h+var_248], rcx
0x18008e2c3  lea     rcx, [rbp+190h+var_158]
0x18008e2c7  mov     [rsp+290h+var_250], rcx
0x18008e2cc  lea     rcx, [rbp+190h+var_140]
0x18008e2d0  mov     [rsp+290h+var_258], rcx
0x18008e2d5  lea     rcx, [rbp+190h+var_128]
0x18008e2d9  mov     [rsp+290h+var_260], rcx
0x18008e2de  lea     rcx, [rbp+190h+var_110]
0x18008e2e5  mov     [rsp+290h+var_268], rcx
0x18008e2ea  lea     rcx, [rbp+190h+var_F8]
0x18008e2f1  mov     qword ptr [rsp+290h+var_270], rcx
0x18008e2f6  mov     r9, rbx
0x18008e2f9  mov     r8, rax
0x18008e2fc  mov     edx, r15d
0x18008e2ff  mov     rcx, rsi
0x18008e302  mov     rax, rdi
0x18008e305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e30a  mov     [rsp+290h+var_21C], eax
0x18008e30e  xor     edi, edi
0x18008e310  test    eax, eax
0x18008e312  jns     loc_18008E447
  ... truncated ...
```
