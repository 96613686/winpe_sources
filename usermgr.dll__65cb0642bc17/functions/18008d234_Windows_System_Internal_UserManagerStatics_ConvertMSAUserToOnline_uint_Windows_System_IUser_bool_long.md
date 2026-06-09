# Windows::System::Internal::UserManagerStatics::ConvertMSAUserToOnline(uint,Windows::System::IUser *,bool,long *)

- ea: `0x18008d234`
- end: `0x18008de3d`
- name: `?ConvertMSAUserToOnline@UserManagerStatics@Internal@System@Windows@@AEAAJIPEAUIUser@34@_NPEAJ@Z`
- size: `3081`
- prototype: `__int64 __usercall@<rax>(Windows::System::Internal::UserManagerStatics *__hidden this@<rcx>, unsigned int@<edx>, struct Windows::System::IUser *@<r8>, bool@<r9b>, int *)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

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
- `0x180051268`
- `0x1800513d0`
- `0x180060524`
- `0x1800624bc`
- `0x1800755e8`
- `0x18008d234`
- `0x180094884`
- `0x180094e90`
- `0x1800a3e0c`
- `0x1800bff28`
- `0x1800c0008`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008d486`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008d741`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008d811`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008d486`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008d741`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008d811`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d451`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d4df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d690`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d69e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d451`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d4df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d690`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d69e`

## string_xrefs

- `0x18008d3e3`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18008d5bf`: `Skipping authentication refresh since last attempt failed`
- `0x18008dcfc`: `Privileges`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
__int64 __fastcall Windows::System::Internal::UserManagerStatics::ConvertMSAUserToOnline(
        Windows::System::Internal::UserManagerStatics *this,
        unsigned int a2,
        struct Windows::System::IUser *a3,
        char a4,
        int *a5)
{
  char *v9; // rbx
  __int64 v10; // rcx
  int v11; // r8d
  int v12; // r9d
  int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // rdx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, _QWORD, struct Windows::System::Internal::IUserProfile **); // rbx
  struct Windows::System::Internal::IUserProfile *v18; // rdi
  __int64 (__fastcall *v19)(struct Windows::System::Internal::IUserProfile *, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // r15
  struct Windows::System::Internal::IUserProfile *v21; // rdi
  __int64 (__fastcall *v22)(struct Windows::System::Internal::IUserProfile *, HSTRING *); // rbx
  struct Windows::System::Internal::IUserProfile *v23; // rdi
  __int64 (__fastcall *v24)(struct Windows::System::Internal::IUserProfile *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)); // rbx
  __int64 v25; // rcx
  const unsigned __int16 *v27; // rax
  int v28; // eax
  __int64 v29; // rcx
  unsigned int v30; // r9d
  const unsigned __int16 *v31; // rax
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, PCWSTR, __int64 *, __int64 *); // rbx
  int v34; // eax
  __int64 v35; // rcx
  unsigned int v36; // r9d
  PVOID Reserved1; // rbx
  PVOID v38; // rbx
  PVOID v39; // rbx
  PVOID v40; // rbx
  PVOID v41; // rbx
  PVOID v42; // rbx
  PVOID v43; // rbx
  PVOID v44; // rbx
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *UserStaticsInternal; // rax
  __int64 *v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v48[4]; // [rsp+64h] [rbp-9Ch] BYREF
  int v49[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v50; // [rsp+70h] [rbp-90h] BYREF
  __int64 v51; // [rsp+78h] [rbp-88h] BYREF
  struct Windows::System::Internal::IUserProfile *v52; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v53; // [rsp+88h] [rbp-78h] BYREF
  int v54; // [rsp+90h] [rbp-70h] BYREF
  int v55; // [rsp+94h] [rbp-6Ch] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v56; // [rsp+98h] [rbp-68h] BYREF
  HSTRING string; // [rsp+A0h] [rbp-60h] BYREF
  __int64 (__fastcall ***v58)(_QWORD, GUID *, __int64); // [rsp+A8h] [rbp-58h] BYREF
  __int64 v59; // [rsp+B0h] [rbp-50h] BYREF
  void *v60; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v61; // [rsp+C0h] [rbp-40h] BYREF
  __int64 (__fastcall ***v62)(_QWORD, GUID *, __int64 *); // [rsp+C8h] [rbp-38h] BYREF
  __int64 v63; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v64; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v65; // [rsp+E0h] [rbp-20h]
  __int64 v66; // [rsp+E8h] [rbp-18h]
  __int64 v67; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v68; // [rsp+F8h] [rbp-8h]
  __int64 v69; // [rsp+100h] [rbp+0h]
  __int64 v70; // [rsp+108h] [rbp+8h] BYREF
  __int64 v71; // [rsp+110h] [rbp+10h]
  __int64 v72; // [rsp+118h] [rbp+18h]
  __int64 v73; // [rsp+120h] [rbp+20h] BYREF
  __int64 v74; // [rsp+128h] [rbp+28h]
  __int64 v75; // [rsp+130h] [rbp+30h]
  __int64 v76; // [rsp+138h] [rbp+38h] BYREF
  __int64 v77; // [rsp+140h] [rbp+40h]
  __int64 v78; // [rsp+148h] [rbp+48h]
  __int64 v79; // [rsp+150h] [rbp+50h] BYREF
  __int64 v80; // [rsp+158h] [rbp+58h]
  __int64 v81; // [rsp+160h] [rbp+60h]
  __int64 v82; // [rsp+168h] [rbp+68h] BYREF
  __int64 v83; // [rsp+170h] [rbp+70h]
  __int64 v84; // [rsp+178h] [rbp+78h]
  __int64 v85; // [rsp+180h] [rbp+80h] BYREF
  __int64 v86; // [rsp+188h] [rbp+88h]
  __int64 v87; // [rsp+190h] [rbp+90h]
  int **v88; // [rsp+198h] [rbp+98h]
  int *v89; // [rsp+1A0h] [rbp+A0h]
  char v90; // [rsp+1A8h] [rbp+A8h]
  _BYTE v91[64]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v92[64]; // [rsp+1F0h] [rbp+F0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+230h] [rbp+130h] BYREF
  __int64 v94; // [rsp+248h] [rbp+148h]
  HSTRING_HEADER v95; // [rsp+250h] [rbp+150h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v9 = (char *)this + 552;
  if ( !(*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 69) + 8LL))((char *)this + 552) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v10);
  v47 = 0;
  string = 0;
  v53 = 0;
  v85 = 0;
  v86 = 0;
  v87 = 0;
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
  v62 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))a3;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v62);
  v59 = 0;
  v52 = 0;
  v51 = 0;
  v56 = 0;
  v50 = 0;
  v58 = 0;
  v61 = 0;
  v60 = 0;
  v54 = 0;
  v63 = 0;
  v48[0] = 0;
  v88 = &a5;
  v89 = &v47;
  v90 = 1;
  if ( (unsigned int)dword_180146228 > 4 )
  {
    v49[0] = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180146228,
      (unsigned int)&dword_18012645C,
      v11,
      v12,
      (__int64)v49);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
  v13 = Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Localize(
          v9,
          &GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5,
          &v51);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 2462;
    goto LABEL_9;
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 67) + 120LL))(*((_QWORD *)this + 67), a2);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 2464;
    goto LABEL_9;
  }
  v16 = *((_QWORD *)this + 67);
  v17 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::System::Internal::IUserProfile **))(*(_QWORD *)v16 + 96LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
  v13 = v17(v16, a2, &v52);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 2465;
    goto LABEL_9;
  }
  v18 = v52;
  v19 = *(__int64 (__fastcall **)(struct Windows::System::Internal::IUserProfile *, HSTRING *))(*(_QWORD *)v52 + 64LL);
  WindowsDeleteString(string);
  string = 0;
  v13 = v19(v18, &string);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 2466;
    goto LABEL_9;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v13 = Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
          &v62,
          &v59);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 2469;
    goto LABEL_9;
  }
  v13 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v59 + 80LL))(v59, &v60);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 2470;
    goto LABEL_9;
  }
  v21 = v52;
  v22 = *(__int64 (__fastcall **)(struct Windows::System::Internal::IUserProfile *, HSTRING *))(*(_QWORD *)v52 + 56LL);
  WindowsDeleteString(v53);
  v53 = 0;
  v13 = v22(v21, &v53);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 2471;
    goto LABEL_9;
  }
  v23 = v52;
  v24 = *(__int64 (__fastcall **)(struct Windows::System::Internal::IUserProfile *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)v52 + 88LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
  v13 = v24(v23, &v58);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 2473;
    goto LABEL_9;
  }
  v13 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
          &v58,
          (__int64)&v61);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 2475;
    goto LABEL_9;
  }
  v94 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"lastSigninResult", 0x11u, 0x10u);
  v13 = Windows::System::Internal::Implementation::ComUtils::FromPropertyMap<unsigned long>(v61, v94, (__int64)&v54);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 2476;
    goto LABEL_9;
  }
  if ( v54 < 0 )
  {
    if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 2) != 0 )
      McTemplateU0zd_EventWriteTransfer(
        v25,
        LogWarning,
        L"Skipping authentication refresh since last attempt failed",
        (unsigned int)v54);
    goto LABEL_30;
  }
  v55 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, PCWSTR, int *))(*(_QWORD *)v51 + 384LL))(v51, StringRawBuffer, &v55);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 2493;
    goto LABEL_9;
  }
  if ( (v55 & 1) != 0 )
  {
    Windows::System::Internal::LogSignOutUserReason(a2, 0, "ConvertMSAUserToOnline - clear MSA signin");
    v13 = (*(__int64 (__fastcall **)(__int64, PCWSTR, _QWORD))(*(_QWORD *)v51 + 80LL))(v51, StringRawBuffer, 0);
    v14 = v13;
    if ( v13 < 0 )
    {
      v15 = 2497;
      goto LABEL_9;
    }
  }
  v27 = WindowsGetStringRawBuffer(v53, 0);
  Windows::System::Internal::Implementation::AutoUserContext::AutoUserContext(
    (Windows::System::Internal::Implementation::AutoUserContext *)v91,
    v60,
    v27);
  v28 = (*(__int64 (__fastcall **)(__int64, PCWSTR))(*(_QWORD *)v51 + 24LL))(v51, StringRawBuffer);
  v30 = v28;
  v47 = v28;
  if ( v28 < 0 )
  {
    if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 2) != 0 )
    {
      McTemplateU0zd_EventWriteTransfer(v29, LogWarning, L"MicrosoftAccount authentication failed", (unsigned int)v28);
      v30 = v47;
    }
    if ( a4 && (unsigned __int8)Windows::System::Internal::IsConnectivityError(v30) )
    {
      Windows::System::Internal::Implementation::UserOnlineConversionTracker::WaitForConnectivityError(
        (LPCRITICAL_SECTION)((char *)this + 384),
        a2);
      v30 = v47;
    }
    Windows::System::Internal::LogSignOutUserReason(
      a2,
      v30,
      "ConvertMSAUserToOnline - AuthenticateMicrosoftAccount failed");
    (*(void (__fastcall **)(__int64, PCWSTR, _QWORD))(*(_QWORD *)v51 + 80LL))(v51, StringRawBuffer, 0);
    Windows::System::Internal::Implementation::AutoUserContext::Revoke((Windows::System::Internal::Implementation::AutoUserContext *)v91);
    goto LABEL_30;
  }
  Windows::System::Internal::Implementation::AutoUserContext::Revoke((Windows::System::Internal::Implementation::AutoUserContext *)v91);
  v31 = WindowsGetStringRawBuffer(v53, 0);
  Windows::System::Internal::Implementation::AutoUserContext::AutoUserContext(
    (Windows::System::Internal::Implementation::AutoUserContext *)v92,
    v60,
    v31);
  v32 = v51;
  v33 = *(__int64 (__fastcall **)(__int64, PCWSTR, __int64 *, __int64 *))(*(_QWORD *)v51 + 608LL);
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
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v85);
  v86 = -1;
  v87 = -1;
  v46 = &v79;
  v34 = v33(v32, StringRawBuffer, &v85, &v82);
  v36 = v34;
  v47 = v34;
  if ( v34 < 0 )
  {
    if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 2) != 0 )
    {
      McTemplateU0zd_EventWriteTransfer(v35, LogWarning, L"Xbox Live authentication failed", (unsigned int)v34);
      v36 = v47;
    }
    if ( a4 && (unsigned __int8)Windows::System::Internal::IsConnectivityError(v36) )
    {
      Windows::System::Internal::Implementation::UserOnlineConversionTracker::WaitForConnectivityError(
        (LPCRITICAL_SECTION)((char *)this + 384),
        a2);
      v36 = v47;
    }
    Windows::System::Internal::LogSignOutUserReason(a2, v36, "ConvertMSAUserToOnline - AuthenticateUserEx failed");
    (*(void (__fastcall **)(__int64, PCWSTR, _QWORD))(*(_QWORD *)v51 + 80LL))(v51, StringRawBuffer, 0);
    Windows::System::Internal::Implementation::AutoUserContext::Revoke((Windows::System::Internal::Implementation::AutoUserContext *)v92);
    goto LABEL_30;
  }
  Windows::System::Internal::Implementation::AutoUserContext::Revoke((Windows::System::Internal::Implementation::AutoUserContext *)v92);
  v94 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Foundation.Collections.PropertySet",
    0x2Bu,
    0x2Au);
  v13 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
          v94,
          &v56);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 2534;
    goto LABEL_9;
  }
  v13 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
          (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v56,
          (__int64)&v50);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 2536;
    goto LABEL_9;
  }
  *(_QWORD *)v49 = v85;
  Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v95, (const WCHAR **)v49)[1].Reserved.Reserved1;
  v94 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"UserData", 9u, 8u);
  v13 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
          v50,
          v94,
          (__int64)Reserved1,
          (__int64)v48);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 2538;
    goto LABEL_9;
  }
  *(_QWORD *)v49 = v82;
  v38 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v95, (const WCHAR **)v49)[1].Reserved.Reserved1;
  v94 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"XboxUserId", 0xBu, 0xAu);
  v13 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
          v50,
          v94,
          (__int64)v38,
          (__int64)v48);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 2539;
    goto LABEL_9;
  }
  *(_QWORD *)v49 = v79;
  v39 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v95, (const WCHAR **)v49)[1].Reserved.Reserved1;
  v94 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Gamertag", 9u, 8u);
  v13 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
          v50,
          v94,
          (__int64)v39,
          (__int64)v48);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 2540;
    goto LABEL_9;
  }
  *(_QWORD *)v49 = v76;
  v40 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v95, (const WCHAR **)v49)[1].Reserved.Reserved1;
  v94 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ModernGamertag", 0xFu, 0xEu);
  v13 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
          v50,
          v94,
          (__int64)v40,
          (__int64)v48);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 2541;
    goto LABEL_9;
  }
  *(_QWORD *)v49 = v73;
  v41 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v95, (const WCHAR **)v49)[1].Reserved.Reserved1;
  v94 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ModernGamertagSuffix", 0x15u, 0x14u);
  v13 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
          v50,
          v94,
          (__int64)v41,
          (__int64)v48);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 2542;
    goto LABEL_9;
  }
  *(_QWORD *)v49 = v70;
  v42 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v95, (const WCHAR **)v49)[1].Reserved.Reserved1;
  v94 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"UniqueModernGamertag", 0x15u, 0x14u);
  v13 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
          v50,
          v94,
          (__int64)v42,
          (__int64)v48);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 2543;
    goto LABEL_9;
  }
  *(_QWORD *)v49 = v67;
  v43 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v95, (const WCHAR **)v49)[1].Reserved.Reserved1;
  v94 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Privileges", 0xBu, 0xAu);
  v13 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
          v50,
          v94,
          (__int64)v43,
          (__int64)v48);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 2544;
    goto LABEL_9;
  }
  *(_QWORD *)v49 = v64;
  v44 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v95, (const WCHAR **)v49)[1].Reserved.Reserved1;
  v94 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"AgeGroup", 9u, 8u);
  v13 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
          v50,
          v94,
          (__int64)v44,
          (__int64)v48);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 2545;
    goto LABEL_9;
  }
  Windows::System::Internal::UserManagerStatics::UpdateOfflineProfileFromAuthZ(this, v52, v56);
  v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v59 + 88LL))(v59, &v63);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 2550;
    goto LABEL_9;
  }
  v13 = (*(__int64 (__fastcall **)(__int64, PCWSTR, __int64))(*(_QWORD *)v51 + 432LL))(v51, StringRawBuffer, v63);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 2551;
    goto LABEL_9;
  }
  UserStaticsInternal = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(this);
  v13 = (*(__int64 (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, struct Windows::System::IUser *, __int64, struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)UserStaticsInternal + 120LL))(
          UserStaticsInternal,
          a3,
          2,
          v56);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = 2553;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v13,
      (int)v46);
    if ( a5 )
      *a5 = v47;
    goto LABEL_33;
  }
LABEL_30:
  if ( a5 )
    *a5 = v47;
  v14 = 0;
LABEL_33:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v56);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v59);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v62);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v64);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v67);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v70);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v73);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v76);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v79);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v82);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v85);
  WindowsDeleteString(v53);
  v53 = 0;
  WindowsDeleteString(string);
  return v14;
}

```

## disassembly

```asm
0x18008d234  mov     [rsp-8+arg_10], rbx
0x18008d239  push    rbp
0x18008d23a  push    rsi
0x18008d23b  push    rdi
0x18008d23c  push    r12
0x18008d23e  push    r13
0x18008d240  push    r14
0x18008d242  push    r15
0x18008d244  lea     rbp, [rsp-180h]
0x18008d24c  sub     rsp, 280h
0x18008d253  mov     rax, cs:__security_cookie
0x18008d25a  xor     rax, rsp
0x18008d25d  mov     [rbp+1B0h+var_40], rax
0x18008d264  mov     r12b, r9b
0x18008d267  mov     r13, r8
0x18008d26a  mov     esi, edx
0x18008d26c  mov     r14, rcx
0x18008d26f  lea     rbx, [rcx+228h]
0x18008d276  mov     rax, [rbx]
0x18008d279  mov     rcx, rbx
0x18008d27c  mov     rax, [rax+8]
0x18008d280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d285  xor     edi, edi
0x18008d287  test    al, al
0x18008d289  jnz     short loc_18008D290
0x18008d28b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008d290  mov     [rsp+2B0h+var_250], edi
0x18008d294  mov     [rbp+1B0h+string], rdi
0x18008d298  mov     [rbp+1B0h+var_228], rdi
0x18008d29c  mov     [rbp+1B0h+var_130], rdi
0x18008d2a3  mov     [rbp+1B0h+var_128], rdi
0x18008d2aa  mov     [rbp+1B0h+var_120], rdi
0x18008d2b1  mov     [rbp+1B0h+var_148], rdi
0x18008d2b5  mov     [rbp+1B0h+var_140], rdi
0x18008d2b9  mov     [rbp+1B0h+var_138], rdi
0x18008d2bd  mov     [rbp+1B0h+var_160], rdi
0x18008d2c1  mov     [rbp+1B0h+var_158], rdi
0x18008d2c5  mov     [rbp+1B0h+var_150], rdi
0x18008d2c9  mov     [rbp+1B0h+var_178], rdi
0x18008d2cd  mov     [rbp+1B0h+var_170], rdi
0x18008d2d1  mov     [rbp+1B0h+var_168], rdi
0x18008d2d5  mov     [rbp+1B0h+var_190], rdi
0x18008d2d9  mov     [rbp+1B0h+var_188], rdi
0x18008d2dd  mov     [rbp+1B0h+var_180], rdi
0x18008d2e1  mov     [rbp+1B0h+var_1A8], rdi
0x18008d2e5  mov     [rbp+1B0h+var_1A0], rdi
0x18008d2e9  mov     [rbp+1B0h+var_198], rdi
0x18008d2ed  mov     [rbp+1B0h+var_1C0], rdi
0x18008d2f1  mov     [rbp+1B0h+var_1B8], rdi
0x18008d2f5  mov     [rbp+1B0h+var_1B0], rdi
0x18008d2f9  mov     [rbp+1B0h+var_1D8], rdi
0x18008d2fd  mov     [rbp+1B0h+var_1D0], rdi
0x18008d301  mov     [rbp+1B0h+var_1C8], rdi
0x18008d305  mov     [rbp+1B0h+var_1E8], r13
0x18008d309  lea     rcx, [rbp+1B0h+var_1E8]
0x18008d30d  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18008d312  nop
0x18008d313  mov     [rbp+1B0h+var_200], rdi
0x18008d317  mov     [rbp+1B0h+var_230], rdi
0x18008d31b  mov     [rsp+2B0h+var_238], rdi
0x18008d320  mov     [rbp+1B0h+var_218], rdi
0x18008d324  mov     [rsp+2B0h+var_240], rdi
0x18008d329  mov     [rbp+1B0h+var_208], rdi
0x18008d32d  mov     [rbp+1B0h+var_1F0], rdi
0x18008d331  mov     [rbp+1B0h+var_1F8], rdi
0x18008d335  mov     [rbp+1B0h+var_220], edi
0x18008d338  mov     [rbp+1B0h+var_1E0], rdi
0x18008d33c  mov     [rsp+2B0h+var_24C], dil
0x18008d341  lea     rax, [rbp+1B0h+arg_20]
0x18008d348  mov     [rbp+1B0h+var_118], rax
0x18008d34f  lea     rax, [rsp+2B0h+var_250]
0x18008d354  mov     [rbp+1B0h+var_110], rax
0x18008d35b  mov     [rbp+1B0h+var_108], 1
0x18008d362  mov     eax, cs:dword_180146228
0x18008d368  cmp     eax, 4
0x18008d36b  jbe     short loc_18008D38E
0x18008d36d  mov     [rsp+2B0h+var_248], esi
0x18008d371  lea     rax, [rsp+2B0h+var_248]
0x18008d376  mov     qword ptr [rsp+2B0h+var_290], rax; int
0x18008d37b  lea     rdx, dword_18012645C
0x18008d382  lea     rcx, dword_180146228
0x18008d389  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18008d38e  lea     rcx, [rsp+2B0h+var_238]
0x18008d393  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008d398  lea     r8, [rsp+2B0h+var_238]
0x18008d39d  lea     rdx, _GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5
0x18008d3a4  mov     rcx, rbx
0x18008d3a7  call    ?Localize@?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@IEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Localize(_GUID const &,void * *)
0x18008d3ac  mov     ebx, eax
0x18008d3ae  test    eax, eax
0x18008d3b0  jns     short loc_18008D3B9
0x18008d3b2  mov     edx, 99Eh
0x18008d3b7  jmp     short loc_18008D3D9
0x18008d3b9  mov     rcx, [r14+218h]
0x18008d3c0  mov     rax, [rcx]
0x18008d3c3  mov     edx, esi
0x18008d3c5  mov     rax, [rax+78h]
0x18008d3c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d3ce  mov     ebx, eax
0x18008d3d0  test    eax, eax
0x18008d3d2  jns     short loc_18008D40B
0x18008d3d4  mov     edx, 9A0h; void *
0x18008d3d9  mov     rcx, [rbp+1B8h]; this
0x18008d3e0  mov     r9d, eax; char *
0x18008d3e3  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x18008d3ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d3ef  nop
0x18008d3f0  mov     rcx, [rbp+1B0h+arg_20]
0x18008d3f7  test    rcx, rcx
0x18008d3fa  jz      loc_18008D5E7
0x18008d400  mov     eax, [rsp+2B0h+var_250]
0x18008d404  mov     [rcx], eax
0x18008d406  jmp     loc_18008D5E7
0x18008d40b  mov     rdi, [r14+218h]
0x18008d412  mov     rax, [rdi]
0x18008d415  mov     rbx, [rax+60h]
0x18008d419  lea     rcx, [rbp+1B0h+var_230]
0x18008d41d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008d422  lea     r8, [rbp+1B0h+var_230]
0x18008d426  mov     edx, esi
0x18008d428  mov     rcx, rdi
0x18008d42b  mov     rax, rbx
0x18008d42e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d433  mov     ebx, eax
0x18008d435  xor     edi, edi
0x18008d437  test    eax, eax
0x18008d439  jns     short loc_18008D442
0x18008d43b  mov     edx, 9A1h
0x18008d440  jmp     short loc_18008D3D9
0x18008d442  mov     rdi, [rbp+1B0h+var_230]
0x18008d446  mov     rax, [rdi]
0x18008d449  mov     rbx, [rax+40h]
0x18008d44d  mov     rcx, [rbp+1B0h+string]; string
0x18008d451  call    cs:__imp_WindowsDeleteString
0x18008d457  mov     [rbp+1B0h+string], 0
0x18008d45f  lea     rdx, [rbp+1B0h+string]
0x18008d463  mov     rcx, rdi
0x18008d466  mov     rax, rbx
0x18008d469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d46e  mov     ebx, eax
0x18008d470  xor     edi, edi
0x18008d472  test    eax, eax
0x18008d474  jns     short loc_18008D480
0x18008d476  mov     edx, 9A2h
0x18008d47b  jmp     loc_18008D3D9
0x18008d480  xor     edx, edx; length
0x18008d482  mov     rcx, [rbp+1B0h+string]; string
0x18008d486  call    cs:__imp_WindowsGetStringRawBuffer
0x18008d48c  mov     r15, rax
0x18008d48f  lea     rdx, [rbp+1B0h+var_200]
0x18008d493  lea     rcx, [rbp+1B0h+var_1E8]
0x18008d497  call    ??$As@UIUserInternal@Implementation@Internal@System@Windows@@@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserInternal>>)
0x18008d49c  mov     ebx, eax
0x18008d49e  test    eax, eax
0x18008d4a0  jns     short loc_18008D4AC
0x18008d4a2  mov     edx, 9A5h
0x18008d4a7  jmp     loc_18008D3D9
0x18008d4ac  mov     rcx, [rbp+1B0h+var_200]
0x18008d4b0  mov     rax, [rcx]
0x18008d4b3  lea     rdx, [rbp+1B0h+var_1F8]
0x18008d4b7  mov     rax, [rax+50h]
0x18008d4bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d4c0  mov     ebx, eax
0x18008d4c2  test    eax, eax
0x18008d4c4  jns     short loc_18008D4D0
0x18008d4c6  mov     edx, 9A6h
0x18008d4cb  jmp     loc_18008D3D9
0x18008d4d0  mov     rdi, [rbp+1B0h+var_230]
0x18008d4d4  mov     rax, [rdi]
0x18008d4d7  mov     rbx, [rax+38h]
0x18008d4db  mov     rcx, [rbp+1B0h+var_228]; string
0x18008d4df  call    cs:__imp_WindowsDeleteString
0x18008d4e5  mov     [rbp+1B0h+var_228], 0
0x18008d4ed  lea     rdx, [rbp+1B0h+var_228]
0x18008d4f1  mov     rcx, rdi
0x18008d4f4  mov     rax, rbx
0x18008d4f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d4fc  mov     ebx, eax
0x18008d4fe  xor     edi, edi
0x18008d500  test    eax, eax
0x18008d502  jns     short loc_18008D50E
0x18008d504  mov     edx, 9A7h
0x18008d509  jmp     loc_18008D3D9
0x18008d50e  mov     rdi, [rbp+1B0h+var_230]
0x18008d512  mov     rax, [rdi]
0x18008d515  mov     rbx, [rax+58h]
0x18008d519  lea     rcx, [rbp+1B0h+var_208]
0x18008d51d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008d522  lea     rdx, [rbp+1B0h+var_208]
0x18008d526  mov     rcx, rdi
0x18008d529  mov     rax, rbx
0x18008d52c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d531  mov     ebx, eax
0x18008d533  xor     edi, edi
0x18008d535  test    eax, eax
0x18008d537  jns     short loc_18008D543
0x18008d539  mov     edx, 9A9h
0x18008d53e  jmp     loc_18008D3D9
0x18008d543  lea     rdx, [rbp+1B0h+var_1F0]
0x18008d547  lea     rcx, [rbp+1B0h+var_208]
0x18008d54b  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x18008d550  mov     ebx, eax
0x18008d552  test    eax, eax
0x18008d554  jns     short loc_18008D560
0x18008d556  mov     edx, 9ABh
0x18008d55b  jmp     loc_18008D3D9
0x18008d560  mov     [rbp+1B0h+var_68], rdi
0x18008d567  mov     r9d, 10h; unsigned int
0x18008d56d  lea     r8d, [r9+1]; unsigned int
0x18008d571  lea     rdx, aLastsigninresu; "lastSigninResult"
0x18008d578  lea     rcx, [rbp+1B0h+hstringHeader]; hstringHeader
0x18008d57f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18008d584  nop
0x18008d585  lea     r8, [rbp+1B0h+var_220]
0x18008d589  mov     rdx, [rbp+1B0h+var_68]
0x18008d590  mov     rcx, [rbp+1B0h+var_1F0]
0x18008d594  call    ??$FromPropertyMap@K@ComUtils@Implementation@Internal@System@Windows@@SAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@4@PEAUHSTRING__@@PEAK@Z; Windows::System::Internal::Implementation::ComUtils::FromPropertyMap<ulong>(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,HSTRING__ *,ulong *)
0x18008d599  mov     ebx, eax
0x18008d59b  test    eax, eax
0x18008d59d  jns     short loc_18008D5A9
0x18008d59f  mov     edx, 9ACh
0x18008d5a4  jmp     loc_18008D3D9
0x18008d5a9  mov     r9d, [rbp+1B0h+var_220]
0x18008d5ad  test    r9d, r9d
0x18008d5b0  jns     loc_18008D6D0
0x18008d5b6  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 2
0x18008d5bd  jz      short loc_18008D5D3
0x18008d5bf  lea     r8, aSkippingAuthen; "Skipping authentication refresh since l"...
0x18008d5c6  lea     rdx, LogWarning
0x18008d5cd  call    McTemplateU0zd_EventWriteTransfer
0x18008d5d2  nop
0x18008d5d3  mov     rcx, [rbp+1B0h+arg_20]
0x18008d5da  test    rcx, rcx
0x18008d5dd  jz      short loc_18008D5E5
0x18008d5df  mov     eax, [rsp+2B0h+var_250]
0x18008d5e3  mov     [rcx], eax
0x18008d5e5  mov     ebx, edi
0x18008d5e7  lea     rcx, [rbp+1B0h+var_1F0]
0x18008d5eb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008d5f0  nop
0x18008d5f1  lea     rcx, [rbp+1B0h+var_208]
0x18008d5f5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008d5fa  nop
0x18008d5fb  lea     rcx, [rsp+2B0h+var_240]
0x18008d600  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008d605  nop
0x18008d606  lea     rcx, [rbp+1B0h+var_218]
0x18008d60a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008d60f  nop
0x18008d610  lea     rcx, [rsp+2B0h+var_238]
0x18008d615  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008d61a  nop
0x18008d61b  lea     rcx, [rbp+1B0h+var_230]
0x18008d61f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008d624  nop
0x18008d625  lea     rcx, [rbp+1B0h+var_200]
0x18008d629  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18008d62e  nop
0x18008d62f  lea     rcx, [rbp+1B0h+var_1E8]
0x18008d633  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18008d638  nop
0x18008d639  lea     rcx, [rbp+1B0h+var_1D8]
0x18008d63d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18008d642  nop
0x18008d643  lea     rcx, [rbp+1B0h+var_1C0]
0x18008d647  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18008d64c  nop
0x18008d64d  lea     rcx, [rbp+1B0h+var_1A8]
0x18008d651  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18008d656  nop
0x18008d657  lea     rcx, [rbp+1B0h+var_190]
0x18008d65b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18008d660  nop
0x18008d661  lea     rcx, [rbp+1B0h+var_178]
0x18008d665  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18008d66a  nop
0x18008d66b  lea     rcx, [rbp+1B0h+var_160]
0x18008d66f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18008d674  nop
0x18008d675  lea     rcx, [rbp+1B0h+var_148]
0x18008d679  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18008d67e  nop
0x18008d67f  lea     rcx, [rbp+1B0h+var_130]
0x18008d686  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18008d68b  nop
0x18008d68c  mov     rcx, [rbp+1B0h+var_228]; string
0x18008d690  call    cs:__imp_WindowsDeleteString
0x18008d696  mov     [rbp+1B0h+var_228], rdi
0x18008d69a  mov     rcx, [rbp+1B0h+string]; string
0x18008d69e  call    cs:__imp_WindowsDeleteString
0x18008d6a4  mov     eax, ebx
0x18008d6a6  mov     rcx, [rbp+1B0h+var_40]
0x18008d6ad  xor     rcx, rsp; StackCookie
0x18008d6b0  call    __security_check_cookie
0x18008d6b5  mov     rbx, [rsp+2B0h+arg_10]
0x18008d6bd  add     rsp, 280h
0x18008d6c4  pop     r15
0x18008d6c6  pop     r14
0x18008d6c8  pop     r13
0x18008d6ca  pop     r12
  ... truncated ...
```
