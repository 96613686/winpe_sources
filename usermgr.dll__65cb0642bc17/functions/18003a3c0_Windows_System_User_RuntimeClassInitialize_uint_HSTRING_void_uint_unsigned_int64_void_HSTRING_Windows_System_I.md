# Windows::System::User::RuntimeClassInitialize(uint,HSTRING__ *,void *,uint,unsigned __int64 *,void *,HSTRING__ *,Windows::System::IUser *,ulong)

- ea: `0x18003a3c0`
- end: `0x18003af2f`
- name: `?RuntimeClassInitialize@User@System@Windows@@QEAAJIPEAUHSTRING__@@PEAXIPEA_K10PEAUIUser@23@K@Z`
- size: `2927`
- prototype: `int(Windows::System::User *__hidden this, unsigned int, HSTRING, void *, unsigned int, unsigned __int64 *, void *, HSTRING, struct Windows::System::IUser *, unsigned int)`
- caller_count: `1`
- callee_count: `34`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003a270`

## callees

- `0x180001450`
- `0x1800052a8`
- `0x18000acdc`
- `0x18000ce48`
- `0x18000d354`
- `0x180010b9c`
- `0x180012890`
- `0x180014e7c`
- `0x1800181f0`
- `0x180018b60`
- `0x180019060`
- `0x180024828`
- `0x18003322c`
- `0x18003329c`
- `0x18003a3c0`
- `0x180041bb0`
- `0x180047b60`
- `0x18004a338`
- `0x18004ba28`
- `0x18004e4e8`
- `0x18004e58c`
- `0x18004fe50`
- `0x180050c38`
- `0x1800513d0`
- `0x1800624bc`
- `0x180063b80`
- `0x180063ef0`
- `0x18006f1c9`
- `0x1800b8da8`
- `0x1800dbd08`
- `0x1800dc080`
- `0x1800dc0c4`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18003ac30`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003ac30`
- `msvcrt!_ui64tow_s` at `0x18003a774`
- `msvcrt!_ui64tow_s` at `0x18003a774`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18003a98c`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18003a98c`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x18003a9fa`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x18003ac07`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x18003a9fa`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x18003ac07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a43e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a9cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003abd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ac5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a43e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a9cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003abd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ac5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a69d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a6e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a69d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a6e0`
- `ntdll!RtlAllocateHeap` at `0x18003a7b6`
- `ntdll!RtlAllocateHeap` at `0x18003a7b6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003aac0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003aac0`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18003ab75`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18003ab75`

## string_xrefs

- `0x18003ad3d`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x18003ad50`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x18003ad65`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x18003ad7a`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x18003ad8f`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x18003ada4`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x18003adb8`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x18003adcd`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x18003ade1`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x18003adf8`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x18003ae0c`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x18003ae20`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x18003ae34`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x18003ae48`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x18003ae5d`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x18003ae72`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x18003ae86`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x18003ae9a`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x18003aeab`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x18003aebf`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x18003aed3`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x18003aee8`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x18003aefa`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x18003af0b`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x18003af1c`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Windows::System::User::RuntimeClassInitialize(
        Windows::System::User *this,
        unsigned int a2,
        HSTRING a3,
        WCHAR *a4,
        unsigned int a5,
        unsigned __int64 *a6,
        WCHAR *a7,
        HSTRING string,
        WCHAR *a9,
        unsigned int a10)
{
  HSTRING v10; // rdi
  unsigned __int64 v11; // r13
  const struct _tlgProvider_t *v13; // rax
  int v14; // ebx
  int v15; // r8d
  int v16; // r9d
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  unsigned int v21; // eax
  int v22; // eax
  wil::details::in1diag3 *v23; // rcx
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, _QWORD, __int64 *); // rbx
  int v26; // eax
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, HSTRING *); // rbx
  int v29; // eax
  HSTRING v30; // rcx
  int v31; // eax
  int v32; // eax
  int v33; // eax
  PVOID Heap; // rax
  __int64 v35; // r8
  HSTRING *v36; // r15
  int v37; // eax
  __int64 v38; // rdi
  __int64 (__fastcall *v39)(__int64, _QWORD, __int64 *); // rbx
  int v40; // eax
  __int64 v41; // rdi
  __int64 (__fastcall *v42)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)); // rbx
  int v43; // eax
  int v44; // eax
  HSTRING v45; // rbx
  int v46; // eax
  int v47; // eax
  HRESULT v48; // eax
  int v49; // eax
  const unsigned __int16 *v50; // rax
  Windows::System::User *v51; // rcx
  const char *v52; // r9
  __int64 v53; // rcx
  int v54; // eax
  int v55; // eax
  int token_information; // eax
  PSID *v57; // rdi
  const char *v58; // r9
  const char *v59; // r9
  unsigned __int64 v60; // rcx
  const unsigned __int16 *v61; // rax
  Windows::System::User *v62; // rcx
  const char *v63; // r9
  const struct _tlgProvider_t *v64; // rbx
  int v65; // r8d
  int v66; // r9d
  __int64 result; // rax
  const struct _tlgProvider_t *v68; // rax
  int v69; // ebx
  wil *v70; // rcx
  int v71; // r8d
  int v72; // r9d
  int ReferencedDomainName; // [rsp+20h] [rbp-238h]
  int ReferencedDomainNamea; // [rsp+20h] [rbp-238h]
  _BYTE v75[8]; // [rsp+50h] [rbp-208h] BYREF
  HSTRING v76; // [rsp+58h] [rbp-200h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp-1F8h] BYREF
  unsigned int v78[2]; // [rsp+68h] [rbp-1F0h] BYREF
  PSID *StringRawBuffer; // [rsp+70h] [rbp-1E8h] BYREF
  DWORD cchReferencedDomainName[2]; // [rsp+78h] [rbp-1E0h] BYREF
  __int64 v81; // [rsp+80h] [rbp-1D8h] BYREF
  __int64 (__fastcall ***v82)(_QWORD, GUID *, __int64); // [rsp+88h] [rbp-1D0h] BYREF
  __int64 v83; // [rsp+90h] [rbp-1C8h] BYREF
  LPUNKNOWN ppunkMarshal; // [rsp+98h] [rbp-1C0h] BYREF
  HSTRING v85; // [rsp+A0h] [rbp-1B8h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+A8h] [rbp-1B0h] BYREF
  __int64 v87; // [rsp+B0h] [rbp-1A8h] BYREF
  HSTRING v88; // [rsp+B8h] [rbp-1A0h] BYREF
  WCHAR Name[8]; // [rsp+C0h] [rbp-198h] BYREF
  __int64 v90[4]; // [rsp+D0h] [rbp-188h] BYREF
  wchar_t Buffer[16]; // [rsp+F0h] [rbp-168h] BYREF
  WCHAR v92[128]; // [rsp+110h] [rbp-148h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  v10 = (HSTRING)a4;
  v11 = a2;
  *(_QWORD *)cchReferencedDomainName = a3;
  v85 = string;
  v88 = string;
  v13 = UserMgrUserModelTelemetry::Provider();
  v14 = (int)v13;
  if ( *(_DWORD *)v13 > 5u )
  {
    v78[0] = a10;
    StringRawBuffer = (PSID *)WindowsGetStringRawBuffer(string, 0);
    StringSid = a7;
    v76 = v10;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v14,
      (unsigned int)&unk_18012B6A0,
      v15,
      v16,
      (__int64)&v76,
      (__int64)&StringSid,
      (__int64)&StringRawBuffer,
      (__int64)v78);
  }
  ppunkMarshal = 0;
  v83 = 0;
  v82 = 0;
  v87 = 0;
  v81 = 0;
  v75[0] = 0;
  try
  {
    v17 = Windows::System::Internal::StaticsCache::GetStaticInstance<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>>(&v83);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x79,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
        (const char *)(unsigned int)v17,
        ReferencedDomainName);
    *((_DWORD *)this + 16) = _InterlockedIncrement((volatile signed __int32 *)&Windows::System::User::s_marshalId);
    *((_DWORD *)this + 17) = v11;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>::operator=(
      (char *)this + 208,
      a9);
    v18 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)this + 24, (HSTRING *)cchReferencedDomainName);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7D,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
        (const char *)(unsigned int)v18,
        ReferencedDomainName);
    v90[1] = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      (HSTRING_HEADER *)Name,
      L"Windows.Foundation.Collections.PropertySet",
      0x2Bu,
      0x2Au);
    v19 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
            v90[1],
            (_QWORD *)this + 17);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x80,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
        (const char *)(unsigned int)v19,
        ReferencedDomainName);
    if ( a9 )
    {
      *((_DWORD *)this + 37) = 2;
      StringSid = a9;
      Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&StringSid);
      v90[1] = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference((HSTRING_HEADER *)Name, L"guestHost", 0xAu, 9u);
      v20 = Windows::System::Internal::Implementation::ComUtils::IntoPropertySet<IInspectable *>(*((_QWORD *)this + 17));
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x88,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
          (const char *)(unsigned int)v20,
          ReferencedDomainName);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&StringSid);
    }
    if ( (unsigned int)(v11 - 16) > 0xFFFEF )
      v21 = (unsigned int)(v11 - 1) <= 0xE;
    else
      v21 = 2;
    v22 = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 4) + 56LL))((char *)this + 32, v21);
    v23 = retaddr;
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
        (const char *)(unsigned int)v22,
        ReferencedDomainName);
    if ( *((_DWORD *)this + 36) == 2 )
    {
      v76 = 0;
      v24 = v83;
      v25 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v83 + 96LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
      v26 = v25(v24, (unsigned int)v11, &v81);
      if ( v26 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x9A,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
          (const char *)(unsigned int)v26,
          ReferencedDomainName);
      v27 = v81;
      v28 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v81 + 64LL);
      WindowsDeleteString(v76);
      v76 = 0;
      v29 = v28(v27, &v76);
      if ( v29 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x9B,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
          (const char *)(unsigned int)v29,
          ReferencedDomainName);
      v30 = v76;
      if ( !v76 )
        *((_DWORD *)this + 36) = 1;
      WindowsDeleteString(v30);
      v10 = (HSTRING)a4;
    }
    if ( *((_DWORD *)this + 37) == 2 )
    {
      if ( !a9 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v23);
      v78[0] = 0;
      v32 = (*(__int64 (__fastcall **)(WCHAR *, unsigned int *))(*(_QWORD *)a9 + 56LL))(a9, v78);
      if ( v32 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB1,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
          (const char *)(unsigned int)v32,
          ReferencedDomainName);
      *((_DWORD *)this + 36) = v78[0];
    }
    else
    {
      v31 = *((_DWORD *)this + 36);
      if ( v31 == 2 )
      {
        *((_DWORD *)this + 37) = 1;
      }
      else if ( v31 == 1 )
      {
        *((_DWORD *)this + 37) = 0;
      }
    }
    _ui64tow_s(v11, Buffer, 0xBu, 10);
    v33 = Microsoft::WRL::Wrappers::HString::Set<513>((char *)this + 120, Buffer);
    if ( v33 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xBA,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
        (const char *)(unsigned int)v33,
        ReferencedDomainName);
    if ( a5 )
    {
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 8LL * a5);
      *((_QWORD *)this + 13) = Heap;
      if ( !Heap )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC0,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
          (const char *)0x8007000ELL,
          ReferencedDomainName);
      v35 = 0;
      do
      {
        *(_QWORD *)(*((_QWORD *)this + 13) + 8 * v35) = a6[v35];
        v35 = (unsigned int)(v35 + 1);
      }
      while ( (unsigned int)v35 < a5 );
    }
    *((_QWORD *)this + 9) = v10;
    *((_QWORD *)this + 10) = a7;
    *((_DWORD *)this + 28) = a5;
    v36 = (HSTRING *)((char *)this + 88);
    v37 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)this + 11, &v88);
    if ( v37 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCA,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
        (const char *)(unsigned int)v37,
        ReferencedDomainName);
    *((_DWORD *)this + 29) = a10;
    if ( *((_DWORD *)this + 37) != 2 && *((_DWORD *)this + 36) == 2 )
    {
      v38 = v83;
      v39 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v83 + 96LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
      v40 = v39(v38, (unsigned int)v11, &v81);
      if ( v40 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD1,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
          (const char *)(unsigned int)v40,
          ReferencedDomainName);
      v41 = v81;
      v42 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)v81 + 88LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v82);
      v43 = v42(v41, &v82);
      if ( v43 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD2,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
          (const char *)(unsigned int)v43,
          ReferencedDomainName);
      v44 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
              &v82,
              (__int64)&v87);
      if ( v44 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD3,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
          (const char *)(unsigned int)v44,
          ReferencedDomainName);
      v45 = *v36;
      v90[1] = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference((HSTRING_HEADER *)Name, L"Sid", 4u, 3u);
      v46 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
              v87,
              v90[1],
              (__int64)v45,
              (__int64)v75);
      if ( v46 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD4,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
          (const char *)(unsigned int)v46,
          ReferencedDomainName);
      v47 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v83 + 80LL))(v83, (unsigned int)v11, v82);
      if ( v47 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD5,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
          (const char *)(unsigned int)v47,
          ReferencedDomainName);
    }
    v48 = CoCreateFreeThreadedMarshaler(0, &ppunkMarshal);
    if ( v48 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDA,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
        (const char *)(unsigned int)v48,
        ReferencedDomainName);
    v49 = Microsoft::WRL::ComPtr<IUnknown>::As<IMarshal>(
            (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&ppunkMarshal,
            (__int64)this + 216);
    if ( v49 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDB,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
        (const char *)(unsigned int)v49,
        ReferencedDomainName);
    v50 = WindowsGetStringRawBuffer(*v36, 0);
    if ( Windows::System::User::AddRestoreDataOrDeleteIfNecessary(
           v51,
           *((_DWORD *)this + 29),
           v50,
           1,
           (struct _LUID *)this + 12)
      && !*((_DWORD *)this + 25)
      && !*((_DWORD *)this + 24)
      && !AllocateLocallyUniqueId((PLUID)this + 12) )
    {
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xE2,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
        v52);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl)
      && (unsigned int)LUAIsShadowAdminEnabled(v53) )
    {
      v54 = LUAIsUserUACAdminEx(*((HANDLE *)this + 9));
      if ( v54 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0xEA,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
          (const char *)(unsigned int)v54,
          ReferencedDomainNamea);
      if ( *((_DWORD *)this + 64) == 1 )
      {
        v55 = LUAGetElevatedToken(*((HANDLE *)this + 9), (PHANDLE)this + 28);
        if ( v55 < 0 )
          wil::details::in1diag3::_Throw_NtStatus(
            retaddr,
            (void *)0xEE,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
            (const char *)(unsigned int)v55,
            ReferencedDomainNamea);
        StringRawBuffer = 0;
        token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(
                              (void **)&StringRawBuffer,
                              *((_QWORD *)this + 28));
        if ( token_information < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF1,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
            (const char *)(unsigned int)token_information,
            ReferencedDomainNamea);
        StringSid = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &StringSid,
          0);
        v57 = StringRawBuffer;
        if ( !ConvertSidToStringSidW(*StringRawBuffer, &StringSid) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0xF4,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
            v58);
        *(_QWORD *)v78 = StringSid;
        Microsoft::WRL::Wrappers::HString::Set<unsigned short *>((HSTRING *)this + 29);
        *(_OWORD *)Name = 0;
        memset(v90, 0, 26);
        LODWORD(v76) = 21;
        memset_0(v92, 0, sizeof(v92));
        cchReferencedDomainName[0] = 128;
        peUse = SidTypeInvalid;
        if ( !LookupAccountSidW(0, *v57, Name, (LPDWORD)&v76, v92, cchReferencedDomainName, &peUse) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0xFD,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
            v59);
        v78[0] = 0;
        v60 = -1;
        do
          ++v60;
        while ( Name[v60] );
        if ( (int)ULongLongToUInt(v60, v78) >= 0 )
          Microsoft::WRL::Wrappers::HString::Set((Windows::System::User *)((char *)this + 248), Name, v78[0]);
        v61 = WindowsGetStringRawBuffer(*((HSTRING *)this + 29), 0);
        if ( Windows::System::User::AddRestoreDataOrDeleteIfNecessary(
               v62,
               *((_DWORD *)this + 29),
               v61,
               1,
               (struct _LUID *)this + 30)
          && !*((_DWORD *)this + 61)
          && !*((_DWORD *)this + 60)
          && !AllocateLocallyUniqueId((PLUID)this + 30) )
        {
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x106,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\user.cpp",
            v63);
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
        if ( v57 )
          operator delete(v57);
      }
    }
    v64 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v64 > 5u )
    {
      LODWORD(v76) = 0;
      cchReferencedDomainName[0] = a10;
      v85 = (HSTRING)WindowsGetStringRawBuffer(v85, 0);
      StringRawBuffer = (PSID *)a7;
      StringSid = a4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v64,
        (unsigned int)byte_18012B5AB,
        v65,
        v66,
        (__int64)&StringSid,
        (__int64)&StringRawBuffer,
        (__int64)&v85,
        (__int64)cchReferencedDomainName,
        (__int64)&v76);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v82);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v83);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
    result = 0;
  }
  catch ( ... )
  {
    v68 = UserMgrUserModelTelemetry::Provider();
    v69 = (int)v68;
    v70 = (wil *)*(unsigned int *)v68;
    if ( (unsigned int)v70 > 5 )
    {
      LODWORD(v76) = wil::ResultFromCaughtException(v70);
      cchReferencedDomainName[0] = a10;
      v85 = (HSTRING)WindowsGetStringRawBuffer(v88, 0);
      StringRawBuffer = (PSID *)a7;
      ppunkMarshal = (LPUNKNOWN)a4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v69,
        (unsigned int)&dword_18012B61C,
        v71,
        v72,
        (__int64)&ppunkMarshal,
        (__int64)&StringRawBuffer,
        (__int64)&v85,
        (__int64)cchReferencedDomainName,
        (__int64)&v76);
    }
    return (unsigned int)wil::ResultFromCaughtException(v70);
  }
  return result;
}

```

## disassembly

```asm
0x18003a3c0  mov     [rsp+arg_18], r9
0x18003a3c5  push    rbx
0x18003a3c6  push    rsi
0x18003a3c7  push    rdi
0x18003a3c8  push    r12
0x18003a3ca  push    r13
0x18003a3cc  push    r14
0x18003a3ce  push    r15
0x18003a3d0  sub     rsp, 220h
0x18003a3d7  mov     rax, cs:__security_cookie
0x18003a3de  xor     rax, rsp
0x18003a3e1  mov     [rsp+258h+var_48], rax
0x18003a3e9  mov     rdi, r9
0x18003a3ec  mov     r13d, edx
0x18003a3ef  mov     rsi, rcx
0x18003a3f2  mov     qword ptr [rsp+258h+var_1E0], r8
0x18003a3f7  mov     r12d, [rsp+258h+arg_20]
0x18003a3ff  mov     r14, [rsp+258h+string]
0x18003a407  mov     [rsp+258h+var_1B8], r14
0x18003a40f  mov     [rsp+258h+var_1A0], r14
0x18003a417  mov     r15, [rsp+258h+arg_40]
0x18003a41f  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x18003a424  mov     rbx, rax
0x18003a427  mov     ecx, [rax]
0x18003a429  cmp     ecx, 5
0x18003a42c  jbe     short loc_18003A492
0x18003a42e  mov     eax, [rsp+258h+arg_48]
0x18003a435  mov     [rsp+258h+var_1F0], eax
0x18003a439  xor     edx, edx; length
0x18003a43b  mov     rcx, r14; string
0x18003a43e  call    cs:__imp_WindowsGetStringRawBuffer
0x18003a444  mov     [rsp+258h+var_1E8], rax
0x18003a449  mov     rax, [rsp+258h+arg_30]
0x18003a451  mov     [rsp+258h+StringSid], rax
0x18003a456  mov     [rsp+258h+var_200], rdi
0x18003a45b  lea     rax, [rsp+258h+var_1F0]
0x18003a460  mov     [rsp+258h+var_220], rax
0x18003a465  lea     rax, [rsp+258h+var_1E8]
0x18003a46a  mov     [rsp+258h+peUse], rax
0x18003a46f  lea     rax, [rsp+258h+StringSid]
0x18003a474  mov     [rsp+258h+cchReferencedDomainName], rax
0x18003a479  lea     rax, [rsp+258h+var_200]
0x18003a47e  mov     [rsp+258h+ReferencedDomainName], rax; int
0x18003a483  lea     rdx, unk_18012B6A0
0x18003a48a  mov     rcx, rbx
0x18003a48d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18003a492  xor     r14d, r14d
0x18003a495  mov     [rsp+258h+ppunkMarshal], r14
0x18003a49d  mov     [rsp+258h+var_1C8], r14
0x18003a4a5  mov     [rsp+258h+var_1D0], r14
0x18003a4ad  mov     [rsp+258h+var_1A8], r14
0x18003a4b5  mov     [rsp+258h+var_1D8], r14
0x18003a4bd  mov     [rsp+258h+var_208], r14b
0x18003a4c2  lea     rcx, [rsp+258h+var_1C8]
0x18003a4ca  call    ??$GetStaticInstance@V?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@@StaticsCache@Internal@System@Windows@@SAJV?$ComPtrRef@V?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@K@Z; Windows::System::Internal::StaticsCache::GetStaticInstance<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>>,ulong)
0x18003a4cf  mov     rcx, [rsp+258h]; this
0x18003a4d7  test    eax, eax
0x18003a4d9  js      loc_18003AD3A
0x18003a4df  mov     eax, 1
0x18003a4e4  lock xadd cs:?s_marshalId@User@System@Windows@@0IA, eax; uint Windows::System::User::s_marshalId
0x18003a4ec  inc     eax
0x18003a4ee  mov     [rsi+40h], eax
0x18003a4f1  mov     [rsi+44h], r13d
0x18003a4f5  lea     rcx, [rsi+0D0h]
0x18003a4fc  mov     rdx, r15
0x18003a4ff  call    ??4?$ComPtr@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@WRL@Microsoft@@QEAAAEAV012@PEAU?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>::operator=(Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *)
0x18003a504  lea     rcx, [rsi+0C0h]; newString
0x18003a50b  lea     rdx, [rsp+258h+var_1E0]; HSTRING *
0x18003a510  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18003a515  mov     rcx, [rsp+258h]; this
0x18003a51d  test    eax, eax
0x18003a51f  js      loc_18003AD4D
0x18003a525  lea     rbx, [rsi+88h]
0x18003a52c  mov     qword ptr [rsp+258h+var_180], r14
0x18003a534  mov     r9d, 2Ah ; '*'; unsigned int
0x18003a53a  lea     r8d, [r9+1]; unsigned int
0x18003a53e  lea     rdx, ?RuntimeClass_Windows_Foundation_Collections_PropertySet@@3QBGB; "Windows.Foundation.Collections.Property"...
0x18003a545  lea     rcx, [rsp+258h+Name]; hstringHeader
0x18003a54d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003a552  nop
0x18003a553  mov     rdx, rbx
0x18003a556  mov     rcx, qword ptr [rsp+258h+var_180]
0x18003a55e  call    ??$ActivateInstance@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>)
0x18003a563  mov     rcx, [rsp+258h]; this
0x18003a56b  test    eax, eax
0x18003a56d  js      loc_18003AD62
0x18003a573  mov     r14d, 2
0x18003a579  test    r15, r15
0x18003a57c  jz      short loc_18003A5F0
0x18003a57e  mov     [rsi+94h], r14d
0x18003a585  mov     [rsp+258h+StringSid], r15
0x18003a58a  lea     rcx, [rsp+258h+StringSid]
0x18003a58f  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18003a594  nop
0x18003a595  mov     qword ptr [rsp+258h+var_180], 0
0x18003a5a1  lea     r9d, [r14+7]; unsigned int
0x18003a5a5  lea     r8d, [r14+8]; unsigned int
0x18003a5a9  lea     rdx, sourceString; "guestHost"
0x18003a5b0  lea     rcx, [rsp+258h+Name]; hstringHeader
0x18003a5b8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003a5bd  nop
0x18003a5be  lea     r9, [rsp+258h+var_208]
0x18003a5c3  mov     r8, r15
0x18003a5c6  mov     rdx, qword ptr [rsp+258h+var_180]
0x18003a5ce  mov     rcx, [rbx]
0x18003a5d1  call    ??$IntoPropertySet@PEAUIInspectable@@@ComUtils@Implementation@Internal@System@Windows@@SAJPEAUIPropertySet@Collections@Foundation@4@PEAUHSTRING__@@PEAUIInspectable@@PEAE@Z; Windows::System::Internal::Implementation::ComUtils::IntoPropertySet<IInspectable *>(Windows::Foundation::Collections::IPropertySet *,HSTRING__ *,IInspectable *,uchar *)
0x18003a5d6  mov     rcx, [rsp+258h]; this
0x18003a5de  test    eax, eax
0x18003a5e0  js      loc_18003AD77
0x18003a5e6  lea     rcx, [rsp+258h+StringSid]
0x18003a5eb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a5f0  lea     rcx, [rsi+20h]
0x18003a5f4  mov     rax, [rcx]
0x18003a5f7  mov     r8, [rax+38h]
0x18003a5fb  lea     eax, [r13-10h]
0x18003a5ff  cmp     eax, 0FFFEFh
0x18003a604  ja      short loc_18003A60B
0x18003a606  mov     eax, r14d
0x18003a609  jmp     short loc_18003A617
0x18003a60b  lea     edx, [r13-1]
0x18003a60f  xor     eax, eax
0x18003a611  cmp     edx, 0Eh
0x18003a614  setbe   al
0x18003a617  mov     edx, eax
0x18003a619  mov     rax, r8
0x18003a61c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a621  mov     rcx, [rsp+258h]; this
0x18003a629  test    eax, eax
0x18003a62b  js      loc_18003AD8C
0x18003a631  cmp     [rsi+90h], r14d
0x18003a638  jnz     loc_18003A6EE
0x18003a63e  mov     [rsp+258h+var_200], 0
0x18003a647  mov     rdi, [rsp+258h+var_1C8]
0x18003a64f  mov     rax, [rdi]
0x18003a652  mov     rbx, [rax+60h]
0x18003a656  lea     rcx, [rsp+258h+var_1D8]
0x18003a65e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a663  lea     r8, [rsp+258h+var_1D8]
0x18003a66b  mov     edx, r13d
0x18003a66e  mov     rcx, rdi
0x18003a671  mov     rax, rbx
0x18003a674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a679  mov     rcx, [rsp+258h]; this
0x18003a681  test    eax, eax
0x18003a683  js      loc_18003ADA1
0x18003a689  mov     rdi, [rsp+258h+var_1D8]
0x18003a691  mov     rax, [rdi]
0x18003a694  mov     rbx, [rax+40h]
0x18003a698  mov     rcx, [rsp+258h+var_200]; string
0x18003a69d  call    cs:__imp_WindowsDeleteString
0x18003a6a3  mov     [rsp+258h+var_200], 0
0x18003a6ac  lea     rdx, [rsp+258h+var_200]
0x18003a6b1  mov     rcx, rdi
0x18003a6b4  mov     rax, rbx
0x18003a6b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a6bc  mov     rcx, [rsp+258h]; this
0x18003a6c4  test    eax, eax
0x18003a6c6  js      loc_18003ADB5
0x18003a6cc  mov     rcx, [rsp+258h+var_200]; string
0x18003a6d1  test    rcx, rcx
0x18003a6d4  jnz     short loc_18003A6E0
0x18003a6d6  mov     dword ptr [rsi+90h], 1
0x18003a6e0  call    cs:__imp_WindowsDeleteString
0x18003a6e6  mov     rdi, [rsp+258h+arg_18]
0x18003a6ee  cmp     [rsi+94h], r14d
0x18003a6f5  jz      short loc_18003A71F
0x18003a6f7  mov     eax, [rsi+90h]
0x18003a6fd  cmp     eax, r14d
0x18003a700  jnz     short loc_18003A70E
0x18003a702  mov     dword ptr [rsi+94h], 1
0x18003a70c  jmp     short loc_18003A75F
0x18003a70e  cmp     eax, 1
0x18003a711  jnz     short loc_18003A75F
0x18003a713  mov     dword ptr [rsi+94h], 0
0x18003a71d  jmp     short loc_18003A75F
0x18003a71f  test    r15, r15
0x18003a722  jnz     short loc_18003A729
0x18003a724  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003a729  mov     [rsp+258h+var_1F0], 0
0x18003a731  mov     rax, [r15]
0x18003a734  lea     rdx, [rsp+258h+var_1F0]
0x18003a739  mov     rcx, r15
0x18003a73c  mov     rax, [rax+38h]
0x18003a740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a745  mov     rcx, [rsp+258h]; this
0x18003a74d  test    eax, eax
0x18003a74f  js      loc_18003ADCA
0x18003a755  mov     eax, [rsp+258h+var_1F0]
0x18003a759  mov     [rsi+90h], eax
0x18003a75f  mov     rcx, r13; Value
0x18003a762  mov     r9d, 0Ah; Radix
0x18003a768  lea     r8d, [r9+1]; BufferCount
0x18003a76c  lea     rdx, [rsp+258h+Buffer]; Buffer
0x18003a774  call    cs:__imp__ui64tow_s
0x18003a77a  lea     rcx, [rsi+78h]
0x18003a77e  lea     rdx, [rsp+258h+Buffer]
0x18003a786  call    ??$Set@$0CAB@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0CAB@G@Z; Microsoft::WRL::Wrappers::HString::Set<513>(ushort (&)[513])
0x18003a78b  mov     rcx, [rsp+258h]; this
0x18003a793  test    eax, eax
0x18003a795  js      loc_18003ADDE
0x18003a79b  test    r12d, r12d
0x18003a79e  jz      short loc_18003A7F0
0x18003a7a0  mov     r8, r12
0x18003a7a3  shl     r8, 3; Size
0x18003a7a7  mov     rcx, gs:60h
0x18003a7b0  xor     edx, edx; Flags
0x18003a7b2  mov     rcx, [rcx+30h]; HeapHandle
0x18003a7b6  call    cs:__imp_RtlAllocateHeap
0x18003a7bc  mov     [rsi+68h], rax
0x18003a7c0  mov     rcx, [rsp+258h]; this
0x18003a7c8  test    rax, rax
0x18003a7cb  jz      loc_18003ADF2
0x18003a7d1  xor     r8d, r8d
0x18003a7d4  mov     rcx, [rsi+68h]
0x18003a7d8  mov     rax, [rsp+258h+arg_28]
0x18003a7e0  mov     rax, [rax+r8*8]
0x18003a7e4  mov     [rcx+r8*8], rax
0x18003a7e8  inc     r8d
0x18003a7eb  cmp     r8d, r12d
0x18003a7ee  jb      short loc_18003A7D4
0x18003a7f0  mov     [rsi+48h], rdi
0x18003a7f4  mov     rax, [rsp+258h+arg_30]
0x18003a7fc  mov     [rsi+50h], rax
0x18003a800  mov     [rsi+70h], r12d
0x18003a804  lea     r15, [rsi+58h]
0x18003a808  lea     rdx, [rsp+258h+var_1A0]; HSTRING *
0x18003a810  mov     rcx, r15; newString
0x18003a813  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18003a818  mov     rcx, [rsp+258h]; this
0x18003a820  test    eax, eax
0x18003a822  js      loc_18003AE09
0x18003a828  mov     r12d, [rsp+258h+arg_48]
0x18003a830  mov     [rsi+74h], r12d
0x18003a834  cmp     [rsi+94h], r14d
0x18003a83b  jz      loc_18003A97F
0x18003a841  cmp     [rsi+90h], r14d
0x18003a848  jnz     loc_18003A97F
0x18003a84e  mov     rdi, [rsp+258h+var_1C8]
0x18003a856  mov     rax, [rdi]
0x18003a859  mov     rbx, [rax+60h]
0x18003a85d  lea     rcx, [rsp+258h+var_1D8]
0x18003a865  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a86a  lea     r8, [rsp+258h+var_1D8]
0x18003a872  mov     edx, r13d
0x18003a875  mov     rcx, rdi
0x18003a878  mov     rax, rbx
0x18003a87b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a880  mov     rcx, [rsp+258h]; this
0x18003a888  xor     r14d, r14d
0x18003a88b  test    eax, eax
0x18003a88d  js      loc_18003AE1D
0x18003a893  mov     rdi, [rsp+258h+var_1D8]
0x18003a89b  mov     rax, [rdi]
0x18003a89e  mov     rbx, [rax+58h]
0x18003a8a2  lea     rcx, [rsp+258h+var_1D0]
0x18003a8aa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a8af  lea     rdx, [rsp+258h+var_1D0]
0x18003a8b7  mov     rcx, rdi
0x18003a8ba  mov     rax, rbx
0x18003a8bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a8c2  mov     rcx, [rsp+258h]; this
0x18003a8ca  test    eax, eax
0x18003a8cc  js      loc_18003AE31
0x18003a8d2  lea     rdx, [rsp+258h+var_1A8]
0x18003a8da  lea     rcx, [rsp+258h+var_1D0]
0x18003a8e2  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x18003a8e7  mov     rcx, [rsp+258h]; this
0x18003a8ef  test    eax, eax
0x18003a8f1  js      loc_18003AE45
0x18003a8f7  mov     rbx, [r15]
0x18003a8fa  mov     qword ptr [rsp+258h+var_180], r14
0x18003a902  mov     r9d, 3; unsigned int
0x18003a908  lea     r8d, [r9+1]; unsigned int
0x18003a90c  lea     rdx, aSid_0; "Sid"
0x18003a913  lea     rcx, [rsp+258h+Name]; hstringHeader
0x18003a91b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003a920  nop
0x18003a921  lea     r9, [rsp+258h+var_208]
0x18003a926  mov     r8, rbx
0x18003a929  mov     rdx, qword ptr [rsp+258h+var_180]
0x18003a931  mov     rcx, [rsp+258h+var_1A8]
0x18003a939  call    ??$IntoPropertyMap@PEAUHSTRING__@@@ComUtils@Implementation@Internal@System@Windows@@SAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@4@PEAUHSTRING__@@1PEAE@Z; Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,HSTRING__ *,HSTRING__ *,uchar *)
0x18003a93e  mov     rcx, [rsp+258h]; this
0x18003a946  test    eax, eax
0x18003a948  js      loc_18003AE5A
0x18003a94e  mov     rcx, [rsp+258h+var_1C8]
0x18003a956  mov     rax, [rcx]
0x18003a959  mov     r8, [rsp+258h+var_1D0]
0x18003a961  mov     edx, r13d
0x18003a964  mov     rax, [rax+50h]
0x18003a968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a96d  mov     rcx, [rsp+258h]; this
0x18003a975  test    eax, eax
0x18003a977  js      loc_18003AE6F
0x18003a97d  jmp     short loc_18003A982
0x18003a97f  xor     r14d, r14d
0x18003a982  lea     rdx, [rsp+258h+ppunkMarshal]; ppunkMarshal
0x18003a98a  xor     ecx, ecx; punkOuter
0x18003a98c  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18003a992  mov     rcx, [rsp+258h]; this
  ... truncated ...
```
