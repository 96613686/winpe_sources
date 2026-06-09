# Windows::System::Internal::UserManagerStatics::PerformAuthorizationCheck(void *,uint,HSTRING__ *,HSTRING__ *,Windows::System::Internal::SignInResult *,Windows::Foundation::Collections::IPropertySet * *)

- ea: `0x180096a9c`
- end: `0x1800976e4`
- name: `?PerformAuthorizationCheck@UserManagerStatics@Internal@System@Windows@@AEAAJPEAXIPEAUHSTRING__@@1PEAVSignInResult@234@PEAPEAUIPropertySet@Collections@Foundation@4@@Z`
- size: `3144`
- prototype: `int(Windows::System::Internal::UserManagerStatics *__hidden this, void *, unsigned int, HSTRING, HSTRING, struct Windows::System::Internal::SignInResult *, struct Windows::Foundation::Collections::IPropertySet **)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18009ac9c`

## callees

- `0x1800088e8`
- `0x18000ce48`
- `0x18000ed00`
- `0x180015540`
- `0x1800181f0`
- `0x180024828`
- `0x18004b3d0`
- `0x18004ba28`
- `0x180050c38`
- `0x1800513d0`
- `0x180060524`
- `0x18008504c`
- `0x180094e90`
- `0x180096a9c`
- `0x1800c0008`
- `0x1800c0fe8`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `msvcrt!wcsstr` at `0x180096d12`
- `msvcrt!wcsstr` at `0x180096d2b`
- `msvcrt!wcsstr` at `0x180096d12`
- `msvcrt!wcsstr` at `0x180096d2b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180096f23`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180096f23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180096cf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180096cff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180096cf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180096cff`

## string_xrefs

- `0x180096bd3`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180096c2a`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180096cb3`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180096d6a`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180096de5`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180096e3e`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180096eb7`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180097129`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800971c8`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180097260`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180097304`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800973ae`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009744e`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800974e9`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180097581`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180097601`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800974ac`: `Privileges`
- `0x180096f45`: `onecore\ds\security\umstartup\usermgr\lib\signinresult.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall Windows::System::Internal::UserManagerStatics::PerformAuthorizationCheck(
        Windows::System::Internal::UserManagerStatics *this,
        void *a2,
        unsigned int a3,
        HSTRING a4,
        HSTRING string,
        struct Windows::System::Internal::SignInResult *a6,
        struct Windows::Foundation::Collections::IPropertySet **a7)
{
  int v11; // eax
  int v12; // ebx
  int v13; // eax
  int v14; // eax
  const wchar_t *StringRawBuffer; // rsi
  const unsigned __int16 *v16; // rdi
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  signed int v21; // eax
  bool v22; // sf
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, const wchar_t *, const WCHAR **, const WCHAR **); // rbx
  PVOID Reserved1; // rbx
  int v26; // eax
  PVOID v27; // rbx
  int v28; // eax
  PVOID v29; // rbx
  int v30; // eax
  PVOID v31; // rbx
  int v32; // eax
  PVOID v33; // rbx
  int v34; // eax
  PVOID v35; // rbx
  int v36; // eax
  PVOID v37; // rbx
  int v38; // eax
  PVOID v39; // rbx
  int v40; // eax
  int v42; // [rsp+20h] [rbp-E0h]
  _BYTE v43[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v44; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v45; // [rsp+68h] [rbp-98h] BYREF
  __int64 v46; // [rsp+70h] [rbp-90h] BYREF
  int v47; // [rsp+78h] [rbp-88h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v48; // [rsp+80h] [rbp-80h] BYREF
  const WCHAR *v49; // [rsp+88h] [rbp-78h] BYREF
  __int64 v50; // [rsp+90h] [rbp-70h] BYREF
  __int64 (__fastcall ***v51)(_QWORD, GUID *, __int64); // [rsp+98h] [rbp-68h] BYREF
  const WCHAR *v52; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v53; // [rsp+A8h] [rbp-58h]
  __int64 v54; // [rsp+B0h] [rbp-50h]
  const WCHAR *v55; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v56; // [rsp+C0h] [rbp-40h]
  __int64 v57; // [rsp+C8h] [rbp-38h]
  const WCHAR *v58; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v59; // [rsp+D8h] [rbp-28h]
  __int64 v60; // [rsp+E0h] [rbp-20h]
  const WCHAR *v61; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v62; // [rsp+F0h] [rbp-10h]
  __int64 v63; // [rsp+F8h] [rbp-8h]
  const WCHAR *v64; // [rsp+100h] [rbp+0h] BYREF
  __int64 v65; // [rsp+108h] [rbp+8h]
  __int64 v66; // [rsp+110h] [rbp+10h]
  int v67[2]; // [rsp+118h] [rbp+18h] BYREF
  __int64 v68; // [rsp+120h] [rbp+20h]
  __int64 v69; // [rsp+128h] [rbp+28h]
  const WCHAR *v70; // [rsp+130h] [rbp+30h] BYREF
  __int64 v71; // [rsp+138h] [rbp+38h]
  __int64 v72; // [rsp+140h] [rbp+40h]
  const WCHAR *v73; // [rsp+148h] [rbp+48h] BYREF
  __int64 v74; // [rsp+150h] [rbp+50h]
  __int64 v75; // [rsp+158h] [rbp+58h]
  struct Windows::Foundation::Collections::IPropertySet **v76; // [rsp+160h] [rbp+60h]
  int *v77; // [rsp+168h] [rbp+68h]
  __int64 *v78; // [rsp+170h] [rbp+70h]
  char v79; // [rsp+178h] [rbp+78h]
  _BYTE v80[64]; // [rsp+180h] [rbp+80h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v82; // [rsp+1D8h] [rbp+D8h]
  HSTRING_HEADER v83; // [rsp+1E0h] [rbp+E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]

  v76 = a7;
  v51 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))a6;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v51);
  v50 = 0;
  v45 = 0;
  v48 = 0;
  v46 = 0;
  v44 = 0;
  v43[0] = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  v70 = 0;
  v71 = 0;
  v72 = 0;
  *(_QWORD *)v67 = 0;
  v68 = 0;
  v69 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v77 = &v44;
  v78 = &v45;
  v79 = 1;
  v82 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Foundation.Collections.PropertySet",
    0x2Bu,
    0x2Au);
  v11 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
          v82,
          &v48);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1015,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v11,
      v42);
    if ( v44 && v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 168LL))(v45);
    goto LABEL_103;
  }
  v13 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
          (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v48,
          (__int64)&v46);
  v12 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1017,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v13,
      v42);
    if ( v44 && v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 168LL))(v45);
    goto LABEL_103;
  }
  if ( !(*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 69) + 8LL))((char *)this + 552) )
  {
LABEL_96:
    if ( v44 && v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 168LL))(v45);
    v12 = 0;
    goto LABEL_103;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
  v14 = Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Localize(
          (char *)this + 552,
          &GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5,
          &v45);
  v12 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x101B,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v14,
      v42);
    if ( v44 && v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 168LL))(v45);
    goto LABEL_103;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v16 = WindowsGetStringRawBuffer(a4, 0);
  if ( wcsstr(StringRawBuffer, L"@") && !wcsstr(StringRawBuffer, L"\\") )
  {
    v47 = 0;
    v17 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v45 + 384LL))(
            v45,
            StringRawBuffer,
            &v47);
    v12 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1022,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v17,
        v42);
      if ( v44 && v45 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 168LL))(v45);
      goto LABEL_103;
    }
    if ( (v47 & 1) != 0 )
    {
      Windows::System::Internal::LogSignOutUserReason(a3, 0, "PerformAuthorization - clear MSA signin");
      v18 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)v45 + 80LL))(
              v45,
              StringRawBuffer,
              0);
      v12 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1026,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v18,
          v42);
        if ( v44 && v45 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 168LL))(v45);
        goto LABEL_103;
      }
    }
    v19 = Microsoft::WRL::ComPtr<Windows::System::Internal::SignInResult>::As<IUserAuthenticationCallback>(
            &v51,
            (__int64)&v50);
    v12 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1029,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v19,
        v42);
      if ( v44 && v45 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 168LL))(v45);
      goto LABEL_103;
    }
    Windows::System::Internal::Implementation::AutoUserContext::AutoUserContext(
      (Windows::System::Internal::Implementation::AutoUserContext *)v80,
      a2,
      v16);
    v20 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v45 + 152LL))(v45, v50, &v44);
    v12 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1032,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v20,
        v42);
      Windows::System::Internal::Implementation::AutoUserContext::Revoke((Windows::System::Internal::Implementation::AutoUserContext *)v80);
      if ( v44 && v45 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 168LL))(v45);
      goto LABEL_103;
    }
    v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v45 + 24LL))(v45, StringRawBuffer);
    if ( v12 < 0 )
    {
      v21 = WaitForSingleObject(*((HANDLE *)a6 + 17), 0x2710u);
      v22 = v21 < 0;
      if ( v21 )
      {
        if ( v21 > 0 )
        {
          v21 = (unsigned __int16)v21 | 0x80070000;
          v22 = v21 < 0;
        }
        if ( v22 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x162,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\signinresult.cpp",
            (const char *)(unsigned int)v21,
            v42);
      }
      Windows::System::Internal::Implementation::AutoUserContext::Revoke((Windows::System::Internal::Implementation::AutoUserContext *)v80);
      if ( v44 && v45 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 168LL))(v45);
      goto LABEL_103;
    }
    v23 = v45;
    v24 = *(__int64 (__fastcall **)(__int64, const wchar_t *, const WCHAR **, const WCHAR **))(*(_QWORD *)v45 + 608LL);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v52);
    v53 = -1;
    v54 = -1;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v55);
    v56 = -1;
    v57 = -1;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v58);
    v59 = -1;
    v60 = -1;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v61);
    v62 = -1;
    v63 = -1;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v64);
    v65 = -1;
    v66 = -1;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v67);
    v68 = -1;
    v69 = -1;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v70);
    v71 = -1;
    v72 = -1;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v73);
    v74 = -1;
    v75 = -1;
    v12 = v24(v23, StringRawBuffer, &v73, &v70);
    if ( v12 < 0 )
    {
      Windows::System::Internal::SignInResult::WaitForUserAuthenticationFailure(a6);
      Windows::System::Internal::Implementation::AutoUserContext::Revoke((Windows::System::Internal::Implementation::AutoUserContext *)v80);
      if ( v44 && v45 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 168LL))(v45);
      goto LABEL_103;
    }
    Windows::System::Internal::Implementation::AutoUserContext::Revoke((Windows::System::Internal::Implementation::AutoUserContext *)v80);
    Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v83, &v73)[1].Reserved.Reserved1;
    v82 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"UserData", 9u, 8u);
    v26 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
            v46,
            v82,
            (__int64)Reserved1,
            (__int64)v43);
    v12 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1043,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v26,
        (int)v67);
      if ( v44 && v45 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 168LL))(v45);
      goto LABEL_103;
    }
    v27 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v83, &v70)[1].Reserved.Reserved1;
    v82 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"XboxUserId", 0xBu, 0xAu);
    v28 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
            v46,
            v82,
            (__int64)v27,
            (__int64)v43);
    v12 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1044,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v28,
        (int)v67);
      if ( v44 && v45 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 168LL))(v45);
      goto LABEL_103;
    }
    v29 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v83, (const WCHAR **)v67)[1].Reserved.Reserved1;
    v82 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Gamertag", 9u, 8u);
    v30 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
            v46,
            v82,
            (__int64)v29,
            (__int64)v43);
    v12 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1045,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v30,
        (int)v67);
      if ( v44 && v45 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 168LL))(v45);
      goto LABEL_103;
    }
    v49 = v64;
    v31 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v83, &v49)[1].Reserved.Reserved1;
    v82 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ModernGamertag", 0xFu, 0xEu);
    v32 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
            v46,
            v82,
            (__int64)v31,
            (__int64)v43);
    v12 = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1046,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v32,
        (int)v67);
      if ( v44 && v45 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 168LL))(v45);
      goto LABEL_103;
    }
    v49 = v61;
    v33 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v83, &v49)[1].Reserved.Reserved1;
    v82 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ModernGamertagSuffix", 0x15u, 0x14u);
    v34 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
            v46,
            v82,
            (__int64)v33,
            (__int64)v43);
    v12 = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1047,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v34,
        (int)v67);
      if ( v44 && v45 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 168LL))(v45);
      goto LABEL_103;
    }
    v49 = v58;
    v35 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v83, &v49)[1].Reserved.Reserved1;
    v82 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"UniqueModernGamertag", 0x15u, 0x14u);
    v36 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
            v46,
            v82,
            (__int64)v35,
            (__int64)v43);
    v12 = v36;
    if ( v36 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1048,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v36,
        (int)v67);
      if ( v44 && v45 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 168LL))(v45);
      goto LABEL_103;
    }
    v37 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v83, &v55)[1].Reserved.Reserved1;
    v82 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Privileges", 0xBu, 0xAu);
    v38 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
            v46,
            v82,
            (__int64)v37,
            (__int64)v43);
    v12 = v38;
    if ( v38 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1049,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v38,
        (int)v67);
      if ( v44 && v45 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 168LL))(v45);
      goto LABEL_103;
    }
    v39 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v83, &v52)[1].Reserved.Reserved1;
    v82 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"AgeGroup", 9u, 8u);
    v40 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
            v46,
            v82,
            (__int64)v39,
            (__int64)v43);
    v12 = v40;
    if ( v40 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x104A,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v40,
        (int)v67);
      if ( v44 && v45 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 168LL))(v45);
      goto LABEL_103;
    }
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v48);
    *v76 = v48;
    goto LABEL_96;
  }
  v12 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x101F,
    (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
    (const char *)0x80070057LL,
    v42);
  if ( v44 && v45 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 168LL))(v45);
LABEL_103:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v52);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v55);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v58);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v61);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v64);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v67);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v70);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v73);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180096a9c  mov     [rsp-8+arg_8], rbx
0x180096aa1  push    rbp
0x180096aa2  push    rsi
0x180096aa3  push    rdi
0x180096aa4  push    r12
0x180096aa6  push    r13
0x180096aa8  push    r14
0x180096aaa  push    r15
0x180096aac  lea     rbp, [rsp-110h]
0x180096ab4  sub     rsp, 210h
0x180096abb  mov     rax, cs:__security_cookie
0x180096ac2  xor     rax, rsp
0x180096ac5  mov     [rbp+140h+var_40], rax
0x180096acc  mov     r15, r9
0x180096acf  mov     r12d, r8d
0x180096ad2  mov     r13, rdx
0x180096ad5  mov     rdi, rcx
0x180096ad8  mov     rsi, [rbp+140h+string]
0x180096adf  mov     rax, [rbp+140h+arg_30]
0x180096ae6  mov     [rbp+140h+var_E0], rax
0x180096aea  mov     r14, [rbp+140h+arg_28]
0x180096af1  mov     [rbp+140h+var_1A8], r14
0x180096af5  lea     rcx, [rbp+140h+var_1A8]
0x180096af9  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180096afe  nop
0x180096aff  xor     ecx, ecx
0x180096b01  mov     [rbp+140h+var_1B0], rcx
0x180096b05  mov     [rsp+240h+var_1D8], rcx
0x180096b0a  mov     [rbp+140h+var_1C0], rcx
0x180096b0e  mov     [rsp+240h+var_1D0], rcx
0x180096b13  mov     [rsp+240h+var_1DC], ecx
0x180096b17  mov     [rsp+240h+var_1E0], cl
0x180096b1b  mov     [rbp+140h+var_F8], rcx
0x180096b1f  mov     [rbp+140h+var_F0], rcx
0x180096b23  mov     [rbp+140h+var_E8], rcx
0x180096b27  mov     [rbp+140h+var_110], rcx
0x180096b2b  mov     [rbp+140h+var_108], rcx
0x180096b2f  mov     [rbp+140h+var_100], rcx
0x180096b33  mov     qword ptr [rbp+140h+var_128], rcx
0x180096b37  mov     [rbp+140h+var_120], rcx
0x180096b3b  mov     [rbp+140h+var_118], rcx
0x180096b3f  mov     [rbp+140h+var_140], rcx
0x180096b43  mov     [rbp+140h+var_138], rcx
0x180096b47  mov     [rbp+140h+var_130], rcx
0x180096b4b  mov     [rbp+140h+var_158], rcx
0x180096b4f  mov     [rbp+140h+var_150], rcx
0x180096b53  mov     [rbp+140h+var_148], rcx
0x180096b57  mov     [rbp+140h+var_170], rcx
0x180096b5b  mov     [rbp+140h+var_168], rcx
0x180096b5f  mov     [rbp+140h+var_160], rcx
0x180096b63  mov     [rbp+140h+var_188], rcx
0x180096b67  mov     [rbp+140h+var_180], rcx
0x180096b6b  mov     [rbp+140h+var_178], rcx
0x180096b6f  mov     [rbp+140h+var_1A0], rcx
0x180096b73  mov     [rbp+140h+var_198], rcx
0x180096b77  mov     [rbp+140h+var_190], rcx
0x180096b7b  lea     rax, [rsp+240h+var_1DC]
0x180096b80  mov     [rbp+140h+var_D8], rax
0x180096b84  lea     rax, [rsp+240h+var_1D8]
0x180096b89  mov     [rbp+140h+var_D0], rax
0x180096b8d  mov     [rbp+140h+var_C8], 1
0x180096b91  mov     [rbp+140h+var_68], rcx
0x180096b98  lea     r9d, [rcx+2Ah]; unsigned int
0x180096b9c  lea     r8d, [rcx+2Bh]; unsigned int
0x180096ba0  lea     rdx, ?RuntimeClass_Windows_Foundation_Collections_PropertySet@@3QBGB; "Windows.Foundation.Collections.Property"...
0x180096ba7  lea     rcx, [rbp+140h+hstringHeader]; hstringHeader
0x180096bae  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180096bb3  lea     rdx, [rbp+140h+var_1C0]
0x180096bb7  mov     rcx, [rbp+140h+var_68]
0x180096bbe  call    ??$ActivateInstance@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>)
0x180096bc3  mov     ebx, eax
0x180096bc5  test    eax, eax
0x180096bc7  jns     short loc_180096C0C
0x180096bc9  mov     rcx, [rbp+148h]; this
0x180096bd0  mov     r9d, eax; char *
0x180096bd3  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180096bda  mov     edx, 1015h; void *
0x180096bdf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180096be4  nop
0x180096be5  mov     edx, [rsp+240h+var_1DC]
0x180096be9  test    edx, edx
0x180096beb  jz      short loc_180096C07
0x180096bed  mov     rcx, [rsp+240h+var_1D8]
0x180096bf2  test    rcx, rcx
0x180096bf5  jz      short loc_180096C07
0x180096bf7  mov     rax, [rcx]
0x180096bfa  mov     rax, [rax+0A8h]
0x180096c01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096c06  nop
0x180096c07  jmp     loc_180097635
0x180096c0c  lea     rdx, [rsp+240h+var_1D0]
0x180096c11  lea     rcx, [rbp+140h+var_1C0]
0x180096c15  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x180096c1a  mov     ebx, eax
0x180096c1c  test    eax, eax
0x180096c1e  jns     short loc_180096C63
0x180096c20  mov     rcx, [rbp+148h]; this
0x180096c27  mov     r9d, eax; char *
0x180096c2a  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180096c31  mov     edx, 1017h; void *
0x180096c36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180096c3b  nop
0x180096c3c  mov     edx, [rsp+240h+var_1DC]
0x180096c40  test    edx, edx
0x180096c42  jz      short loc_180096C5E
0x180096c44  mov     rcx, [rsp+240h+var_1D8]
0x180096c49  test    rcx, rcx
0x180096c4c  jz      short loc_180096C5E
0x180096c4e  mov     rax, [rcx]
0x180096c51  mov     rax, [rax+0A8h]
0x180096c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096c5d  nop
0x180096c5e  jmp     loc_180097635
0x180096c63  lea     rbx, [rdi+228h]
0x180096c6a  mov     rax, [rbx]
0x180096c6d  mov     rcx, rbx
0x180096c70  mov     rax, [rax+8]
0x180096c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096c79  test    al, al
0x180096c7b  jnz     short loc_180096C85
0x180096c7d  xor     r12d, r12d
0x180096c80  jmp     loc_1800975CB
0x180096c85  lea     rcx, [rsp+240h+var_1D8]
0x180096c8a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180096c8f  lea     r8, [rsp+240h+var_1D8]
0x180096c94  lea     rdx, _GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5
0x180096c9b  mov     rcx, rbx
0x180096c9e  call    ?Localize@?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@IEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Localize(_GUID const &,void * *)
0x180096ca3  mov     ebx, eax
0x180096ca5  test    eax, eax
0x180096ca7  jns     short loc_180096CEC
0x180096ca9  mov     rcx, [rbp+148h]; this
0x180096cb0  mov     r9d, eax; char *
0x180096cb3  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180096cba  mov     edx, 101Bh; void *
0x180096cbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180096cc4  nop
0x180096cc5  mov     edx, [rsp+240h+var_1DC]
0x180096cc9  test    edx, edx
0x180096ccb  jz      short loc_180096CE7
0x180096ccd  mov     rcx, [rsp+240h+var_1D8]
0x180096cd2  test    rcx, rcx
0x180096cd5  jz      short loc_180096CE7
0x180096cd7  mov     rax, [rcx]
0x180096cda  mov     rax, [rax+0A8h]
0x180096ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096ce6  nop
0x180096ce7  jmp     loc_180097635
0x180096cec  xor     edx, edx; length
0x180096cee  mov     rcx, rsi; string
0x180096cf1  call    cs:__imp_WindowsGetStringRawBuffer
0x180096cf7  mov     rsi, rax
0x180096cfa  xor     edx, edx; length
0x180096cfc  mov     rcx, r15; string
0x180096cff  call    cs:__imp_WindowsGetStringRawBuffer
0x180096d05  mov     rdi, rax
0x180096d08  lea     rdx, asc_1801118C4; "@"
0x180096d0f  mov     rcx, rsi; Str
0x180096d12  call    cs:__imp_wcsstr
0x180096d18  test    rax, rax
0x180096d1b  jz      loc_1800975F2
0x180096d21  lea     rdx, SubStr; "\\"
0x180096d28  mov     rcx, rsi; Str
0x180096d2b  call    cs:__imp_wcsstr
0x180096d31  test    rax, rax
0x180096d34  jnz     loc_1800975F2
0x180096d3a  mov     [rsp+240h+var_1C8], eax
0x180096d3e  mov     rcx, [rsp+240h+var_1D8]
0x180096d43  mov     rax, [rcx]
0x180096d46  lea     r8, [rsp+240h+var_1C8]
0x180096d4b  mov     rdx, rsi
0x180096d4e  mov     rax, [rax+180h]
0x180096d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096d5a  mov     ebx, eax
0x180096d5c  test    eax, eax
0x180096d5e  jns     short loc_180096DA3
0x180096d60  mov     rcx, [rbp+148h]; this
0x180096d67  mov     r9d, eax; char *
0x180096d6a  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180096d71  mov     edx, 1022h; void *
0x180096d76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180096d7b  nop
0x180096d7c  mov     edx, [rsp+240h+var_1DC]
0x180096d80  test    edx, edx
0x180096d82  jz      short loc_180096D9E
0x180096d84  mov     rcx, [rsp+240h+var_1D8]
0x180096d89  test    rcx, rcx
0x180096d8c  jz      short loc_180096D9E
0x180096d8e  mov     rax, [rcx]
0x180096d91  mov     rax, [rax+0A8h]
0x180096d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096d9d  nop
0x180096d9e  jmp     loc_180097635
0x180096da3  test    byte ptr [rsp+240h+var_1C8], 1
0x180096da8  jz      short loc_180096E1E
0x180096daa  lea     r8, aPerformauthori; "PerformAuthorization - clear MSA signin"
0x180096db1  xor     edx, edx
0x180096db3  mov     ecx, r12d
0x180096db6  call    Windows__System__Internal__LogSignOutUserReason
0x180096dbb  mov     rcx, [rsp+240h+var_1D8]
0x180096dc0  mov     rax, [rcx]
0x180096dc3  xor     r8d, r8d
0x180096dc6  mov     rdx, rsi
0x180096dc9  mov     rax, [rax+50h]
0x180096dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096dd2  mov     ebx, eax
0x180096dd4  xor     r12d, r12d
0x180096dd7  test    eax, eax
0x180096dd9  jns     short loc_180096E21
0x180096ddb  mov     rcx, [rbp+148h]; this
0x180096de2  mov     r9d, eax; char *
0x180096de5  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180096dec  mov     edx, 1026h; void *
0x180096df1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180096df6  nop
0x180096df7  mov     edx, [rsp+240h+var_1DC]
0x180096dfb  test    edx, edx
0x180096dfd  jz      short loc_180096E19
0x180096dff  mov     rcx, [rsp+240h+var_1D8]
0x180096e04  test    rcx, rcx
0x180096e07  jz      short loc_180096E19
0x180096e09  mov     rax, [rcx]
0x180096e0c  mov     rax, [rax+0A8h]
0x180096e13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096e18  nop
0x180096e19  jmp     loc_180097635
0x180096e1e  xor     r12d, r12d
0x180096e21  lea     rdx, [rbp+140h+var_1B0]
0x180096e25  lea     rcx, [rbp+140h+var_1A8]
0x180096e29  call    ??$As@UIUserAuthenticationCallback@@@?$ComPtr@VSignInResult@Internal@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserAuthenticationCallback@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::SignInResult>::As<IUserAuthenticationCallback>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IUserAuthenticationCallback>>)
0x180096e2e  mov     ebx, eax
0x180096e30  test    eax, eax
0x180096e32  jns     short loc_180096E77
0x180096e34  mov     rcx, [rbp+148h]; this
0x180096e3b  mov     r9d, eax; char *
0x180096e3e  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180096e45  mov     edx, 1029h; void *
0x180096e4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180096e4f  nop
0x180096e50  mov     edx, [rsp+240h+var_1DC]
0x180096e54  test    edx, edx
0x180096e56  jz      short loc_180096E72
0x180096e58  mov     rcx, [rsp+240h+var_1D8]
0x180096e5d  test    rcx, rcx
0x180096e60  jz      short loc_180096E72
0x180096e62  mov     rax, [rcx]
0x180096e65  mov     rax, [rax+0A8h]
0x180096e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096e71  nop
0x180096e72  jmp     loc_180097635
0x180096e77  mov     r8, rdi; unsigned __int16 *
0x180096e7a  mov     rdx, r13; void *
0x180096e7d  lea     rcx, [rbp+140h+var_C0]; this
0x180096e84  call    ??0AutoUserContext@Implementation@Internal@System@Windows@@QEAA@PEAXPEBG@Z; Windows::System::Internal::Implementation::AutoUserContext::AutoUserContext(void *,ushort const *)
0x180096e89  nop
0x180096e8a  mov     rcx, [rsp+240h+var_1D8]
0x180096e8f  mov     rax, [rcx]
0x180096e92  lea     r8, [rsp+240h+var_1DC]
0x180096e97  mov     rdx, [rbp+140h+var_1B0]
0x180096e9b  mov     rax, [rax+98h]
0x180096ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096ea7  mov     ebx, eax
0x180096ea9  test    eax, eax
0x180096eab  jns     short loc_180096EFD
0x180096ead  mov     rcx, [rbp+148h]; this
0x180096eb4  mov     r9d, eax; char *
0x180096eb7  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180096ebe  mov     edx, 1032h; void *
0x180096ec3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180096ec8  nop
0x180096ec9  lea     rcx, [rbp+140h+var_C0]; this
0x180096ed0  call    ?Revoke@AutoUserContext@Implementation@Internal@System@Windows@@QEAAXXZ; Windows::System::Internal::Implementation::AutoUserContext::Revoke(void)
0x180096ed5  nop
0x180096ed6  mov     edx, [rsp+240h+var_1DC]
0x180096eda  test    edx, edx
0x180096edc  jz      short loc_180096EF8
0x180096ede  mov     rcx, [rsp+240h+var_1D8]
0x180096ee3  test    rcx, rcx
0x180096ee6  jz      short loc_180096EF8
0x180096ee8  mov     rax, [rcx]
0x180096eeb  mov     rax, [rax+0A8h]
0x180096ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096ef7  nop
0x180096ef8  jmp     loc_180097635
0x180096efd  mov     rcx, [rsp+240h+var_1D8]
0x180096f02  mov     rax, [rcx]
0x180096f05  mov     rdx, rsi
0x180096f08  mov     rax, [rax+18h]
0x180096f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096f11  mov     ebx, eax
0x180096f13  test    eax, eax
0x180096f15  jns     short loc_180096F8B
0x180096f17  mov     edx, 2710h; dwMilliseconds
0x180096f1c  mov     rcx, [r14+88h]; hHandle
0x180096f23  call    cs:__imp_WaitForSingleObject
0x180096f29  test    eax, eax
0x180096f2b  jz      short loc_180096F57
0x180096f2d  jle     short loc_180096F39
0x180096f2f  movzx   eax, ax
0x180096f32  or      eax, 80070000h
  ... truncated ...
```
