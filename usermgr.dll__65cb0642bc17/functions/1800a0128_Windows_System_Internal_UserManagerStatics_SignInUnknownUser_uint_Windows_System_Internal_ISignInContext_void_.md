# Windows::System::Internal::UserManagerStatics::SignInUnknownUser(uint,Windows::System::Internal::ISignInContext *,void *,Windows::System::Internal::ISignInResult * *)

- ea: `0x1800a0128`
- end: `0x1800a1197`
- name: `?SignInUnknownUser@UserManagerStatics@Internal@System@Windows@@AEAAJIPEAUISignInContext@234@PEAXPEAPEAUISignInResult@234@@Z`
- size: `4207`
- prototype: `__int64 __usercall@<rax>(Windows::System::Internal::UserManagerStatics *__hidden this@<rcx>, unsigned int@<edx>, struct Windows::System::Internal::ISignInContext *@<r8>, void *@<r9>, struct Windows::System::Internal::ISignInResult **)`
- caller_count: `1`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18009a4ec`

## callees

- `0x180002c18`
- `0x180007920`
- `0x18000acdc`
- `0x18000ce48`
- `0x180012890`
- `0x180014e7c`
- `0x1800181f0`
- `0x180018b60`
- `0x18002618c`
- `0x18003322c`
- `0x18003329c`
- `0x1800332e8`
- `0x18003b578`
- `0x180041fc0`
- `0x180044f08`
- `0x18004ba28`
- `0x18004bed4`
- `0x18004bf50`
- `0x18004d710`
- `0x18004da04`
- `0x18004e4e8`
- `0x18004e58c`
- `0x180050c38`
- `0x180086bcc`
- `0x18008a000`
- `0x18008c534`
- `0x180093864`
- `0x180094ff4`
- `0x1800a0128`
- `0x1800a3bf8`
- `0x1800c07d0`
- `0x1800c0ca4`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a04a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a0d38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a04a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a0d38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a03ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0545`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0558`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0584`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0753`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0c21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0c34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0c60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0dcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0de2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0e0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0eb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0ecc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0ef8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a03ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0545`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0558`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0584`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0753`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0c21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0c34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0c60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0dcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0de2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0e0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0eb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0ecc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0ef8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a01f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a01f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0aca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0ae6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0aca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0ae6`

## string_xrefs

- `0x1800a0f8c`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a0fa0`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a0fb4`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a0fc8`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a0fdc`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a0ff0`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a1004`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a1018`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a1029`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a103d`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a1051`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a1065`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a1079`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a108e`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a10a3`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a10b7`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a10cc`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a10e0`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a10f5`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a1109`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a111d`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a1132`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a1147`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a115c`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a1170`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a1184`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=28 #try_helpers=1
__int64 __fastcall Windows::System::Internal::UserManagerStatics::SignInUnknownUser(
        Windows::System::Internal::UserManagerStatics *this,
        unsigned int a2,
        struct Windows::System::Internal::ISignInContext *a3,
        void *a4,
        struct Windows::System::Internal::ISignInResult **a5)
{
  void (__fastcall *v8)(void *, __int64 *); // rbx
  void (__fastcall *v9)(void *, __int64 *); // rbx
  const struct _tlgProvider_t *v10; // rax
  int v11; // r8d
  int v12; // r9d
  __int64 (__fastcall *v13)(struct Windows::System::Internal::ISignInContext *, GUID *, __int64 *); // rbx
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  int v17; // eax
  __int64 (__fastcall *v18)(struct Windows::System::Internal::ISignInContext *, GUID *, __int64 *); // rbx
  int v19; // eax
  int v20; // eax
  int v21; // eax
  unsigned int v22; // ebx
  const unsigned __int16 *StringRawBuffer; // rax
  int v24; // eax
  int v26; // eax
  int v27; // eax
  __int64 v28; // rdi
  unsigned int (__fastcall *v29)(__int64, _QWORD, __int64 *); // rbx
  const char *v30; // r9
  int v31; // eax
  int UserBySid; // eax
  int v33; // eax
  PLSA_UNICODE_STRING v34; // rdi
  __int64 (__fastcall *v35)(PLSA_UNICODE_STRING, HSTRING *); // rbx
  int v36; // eax
  NTSTATUS v37; // eax
  int v38; // r8d
  int v39; // eax
  int v40; // eax
  __int64 (__fastcall **v41)(struct Windows::System::Internal::ISignInContext *, GUID *, __int64 *); // rax
  int v42; // eax
  int v43; // eax
  __int64 (__fastcall *v44)(char *, _QWORD, PLSA_UNICODE_STRING *); // rbx
  int v45; // eax
  PLSA_UNICODE_STRING v46; // rdi
  __int64 (__fastcall *v47)(PLSA_UNICODE_STRING, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)); // rbx
  int v48; // eax
  int v49; // eax
  HSTRING v50; // rbx
  int v51; // eax
  int v52; // eax
  HLOCAL v53; // rcx
  HLOCAL v54; // rcx
  int v55; // eax
  int v56; // eax
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *UserStaticsInternal; // rax
  int v58; // eax
  const struct _tlgProvider_t *v59; // rbx
  int v60; // r8d
  int v61; // r9d
  int v62; // [rsp+20h] [rbp-278h]
  int v63; // [rsp+20h] [rbp-278h]
  int v64; // [rsp+20h] [rbp-278h]
  int v65; // [rsp+20h] [rbp-278h]
  int v66; // [rsp+20h] [rbp-278h]
  int v67; // [rsp+20h] [rbp-278h]
  unsigned int v68; // [rsp+50h] [rbp-248h] BYREF
  char v69; // [rsp+58h] [rbp-240h] BYREF
  HSTRING v70; // [rsp+60h] [rbp-238h] BYREF
  __int64 (__fastcall ***v71)(_QWORD, GUID *, __int64); // [rsp+68h] [rbp-230h] BYREF
  _BYTE v72[8]; // [rsp+70h] [rbp-228h] BYREF
  HSTRING string; // [rsp+78h] [rbp-220h] BYREF
  int v74; // [rsp+80h] [rbp-218h] BYREF
  int v75; // [rsp+84h] [rbp-214h] BYREF
  PLSA_UNICODE_STRING SystemName; // [rsp+88h] [rbp-210h] BYREF
  int v77[2]; // [rsp+90h] [rbp-208h] BYREF
  HSTRING v78; // [rsp+98h] [rbp-200h] BYREF
  Windows::System::Internal::SignInResult *v79; // [rsp+A0h] [rbp-1F8h] BYREF
  HLOCAL v80; // [rsp+A8h] [rbp-1F0h] BYREF
  int v81[2]; // [rsp+B0h] [rbp-1E8h] BYREF
  HLOCAL hMem; // [rsp+B8h] [rbp-1E0h] BYREF
  unsigned int v83; // [rsp+C0h] [rbp-1D8h] BYREF
  __int64 v84; // [rsp+C8h] [rbp-1D0h] BYREF
  __int64 v85; // [rsp+D0h] [rbp-1C8h] BYREF
  __int64 v86; // [rsp+D8h] [rbp-1C0h] BYREF
  __int64 v87; // [rsp+E0h] [rbp-1B8h] BYREF
  __int64 v88; // [rsp+E8h] [rbp-1B0h] BYREF
  __int64 v89; // [rsp+F0h] [rbp-1A8h] BYREF
  int v90; // [rsp+F8h] [rbp-1A0h] BYREF
  int v91; // [rsp+FCh] [rbp-19Ch] BYREF
  void *v92; // [rsp+100h] [rbp-198h] BYREF
  __int64 v93; // [rsp+108h] [rbp-190h] BYREF
  __int64 v94; // [rsp+110h] [rbp-188h] BYREF
  _DWORD v95[2]; // [rsp+118h] [rbp-180h] BYREF
  void *v96; // [rsp+120h] [rbp-178h] BYREF
  PVOID PolicyHandle; // [rsp+128h] [rbp-170h] BYREF
  char v98; // [rsp+130h] [rbp-168h]
  _QWORD v99[3]; // [rsp+138h] [rbp-160h] BYREF
  _QWORD v100[8]; // [rsp+150h] [rbp-148h] BYREF
  char v101; // [rsp+190h] [rbp-108h]
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+1A0h] [rbp-F8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+1D0h] [rbp-C8h] BYREF
  __int64 v104; // [rsp+1E8h] [rbp-B0h]
  _QWORD v105[12]; // [rsp+1F0h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  v68 = a2;
  v99[1] = a3;
  v99[0] = a5;
  v89 = 0;
  v88 = 0;
  v74 = 0;
  v87 = 0;
  v94 = 0;
  v79 = 0;
  v86 = 0;
  v85 = 0;
  string = 0;
  SystemName = 0;
  v93 = 0;
  v70 = 0;
  v90 = 0;
  v91 = 0;
  v95[1] = 0;
  v78 = 0;
  v84 = 0;
  v92 = (void *)-1LL;
  v83 = 0;
  v95[0] = GetTickCount();
  v69 = 0;
  v8 = *(void (__fastcall **)(void *, __int64 *))(Windows::System::Internal::Adapters::g_AdapterCollection + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v89);
  v8(&Windows::System::Internal::Adapters::g_AdapterCollection, &v89);
  v9 = *(void (__fastcall **)(void *, __int64 *))(Windows::System::Internal::Adapters::g_AdapterCollection + 88LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v88);
  v9(&Windows::System::Internal::Adapters::g_AdapterCollection, &v88);
  *(_QWORD *)v99[0] = 0;
  v75 = 0;
  if ( a3 )
    (*(void (__fastcall **)(struct Windows::System::Internal::ISignInContext *, int *))(*(_QWORD *)a3 + 64LL))(a3, &v75);
  v10 = UserMgrUserModelTelemetry::Provider();
  if ( *(_DWORD *)v10 > 5u )
  {
    LODWORD(v80) = v75;
    v81[0] = v68;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v10,
      (unsigned int)byte_18012608B,
      v11,
      v12,
      (__int64)v81,
      (__int64)&v80);
  }
  v100[0] = &v79;
  v100[1] = &v74;
  v100[2] = v99;
  v100[3] = v95;
  v100[4] = &string;
  v100[5] = &v69;
  v100[6] = this;
  v100[7] = &v68;
  v101 = 1;
  v13 = **(__int64 (__fastcall ***)(struct Windows::System::Internal::ISignInContext *, GUID *, __int64 *))a3;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v86);
  v14 = v13(a3, &GUID_5da3f048_82e8_4c82_8bfd_c389baeda720, &v86);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF5B,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v14,
      v62);
  v15 = v86;
  v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v86 + 48LL);
  WindowsDeleteString(string);
  string = 0;
  v17 = v16(v15, &string);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF5C,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v17,
      v62);
  v18 = **(__int64 (__fastcall ***)(struct Windows::System::Internal::ISignInContext *, GUID *, __int64 *))a3;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v85);
  v19 = v18(a3, &GUID_94154ae2_729f_4ad9_9907_3d8f698e14c8, &v85);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF5F,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v19,
      v62);
  v20 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v85 + 48LL))(v85, &v83);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF60,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v20,
      v62);
  *(_QWORD *)v77 = string;
  v71 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))v70;
  v21 = Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::SignInResult,Windows::System::Internal::SignInResult,unsigned int &,HSTRING__ *,enum Windows::System::Internal::SignInCaller &,HSTRING__ *>(
          (unsigned int)&v79,
          (unsigned int)&v68,
          (unsigned int)&v71,
          (unsigned int)&v75,
          (__int64)v77);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF63,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v21,
      v63);
  v22 = v83;
  StringRawBuffer = WindowsGetStringRawBuffer(v70, 0);
  v24 = Windows::System::Internal::UserManagerStatics::LsaLogonUserWrapper(
          this,
          v68,
          a3,
          StringRawBuffer,
          v22,
          &v92,
          &v90,
          &v91);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF6D,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v24,
      v64);
  if ( v90 )
  {
    Windows::System::Internal::SignInResult::SetResultAndUserLogonStatus(v79, v90, v91);
    v101 = 0;
    lambda_0331c0bd289c122e8b9f659c97a93081_::operator()(v100);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v84);
    WindowsDeleteString(v78);
    v78 = 0;
    WindowsDeleteString(v70);
    v70 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v93);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&SystemName);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v85);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v94);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v88);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v89);
    return 0;
  }
  else
  {
    v26 = Windows::System::Internal::UserManagerStatics::CheckCancelEvent(retaddr, a4);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF74,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v26,
        v64);
    v27 = (*(__int64 (__fastcall **)(__int64, void *, __int64, _QWORD *))(*(_QWORD *)v88 + 24LL))(v88, v92, 1, v105);
    if ( v27 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0xF78,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v27,
        84);
    v28 = v89;
    v29 = *(unsigned int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v89 + 32LL);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v84,
      0);
    if ( !v29(v28, v105[0], &v84) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xF7A,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        v30);
    *(_QWORD *)v77 = v84;
    v31 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&v78);
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF7B,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v31,
        84);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&SystemName);
    UserBySid = Windows::System::Internal::UserManagerStatics::GetUserBySid(
                  this,
                  v78,
                  (struct Windows::System::Internal::IUserProfile **)&SystemName);
    if ( UserBySid < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF7D,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)UserBySid,
        84);
    if ( SystemName )
    {
      v33 = (*(__int64 (__fastcall **)(PLSA_UNICODE_STRING, unsigned int *))(*(_QWORD *)&SystemName->Length + 48LL))(
              SystemName,
              &v68);
      if ( v33 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xFB2,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v33,
          84);
      v34 = SystemName;
      v35 = *(__int64 (__fastcall **)(PLSA_UNICODE_STRING, HSTRING *))(*(_QWORD *)&SystemName->Length + 64LL);
      WindowsDeleteString(v70);
      v70 = 0;
      v36 = v35(v34, &v70);
      if ( v36 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xFB3,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v36,
          84);
    }
    else
    {
      *(_QWORD *)v77 = 0;
      memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
      v96 = v77;
      PolicyHandle = 0;
      v98 = 1;
      v37 = LsaOpenPolicy(0, &ObjectAttributes, 0x801u, &PolicyHandle);
      if ( v37 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0xF8A,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v37,
          84);
      wil::details::out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&v96);
      v80 = 0;
      hMem = 0;
      hstringHeader.Reserved.Reserved1 = &hMem;
      *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
      hstringHeader.Reserved.Reserved2[16] = 1;
      v96 = &v80;
      PolicyHandle = 0;
      v98 = 1;
      LsapLookupSids(
        v77[0],
        0x40000000,
        v38,
        (unsigned int)v105,
        (__int64)&PolicyHandle,
        (__int64)&hstringHeader.Reserved.Reserved2[8]);
      wil::details::out_param_t<wistd::unique_ptr<_LSA_REFERENCED_DOMAIN_LIST,wil::function_deleter<long (*)(void *),&long LsaFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<_LSA_REFERENCED_DOMAIN_LIST,wil::function_deleter<long (*)(void *),&long LsaFreeMemory(void *)>>>(&v96);
      wil::details::out_param_t<wistd::unique_ptr<_LSA_REFERENCED_DOMAIN_LIST,wil::function_deleter<long (*)(void *),&long LsaFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<_LSA_REFERENCED_DOMAIN_LIST,wil::function_deleter<long (*)(void *),&long LsaFreeMemory(void *)>>>(&hstringHeader);
      v39 = Microsoft::WRL::Wrappers::HString::Set(
              (Microsoft::WRL::Wrappers::HString *)&v70,
              *((const unsigned __int16 **)hMem + 2),
              *((unsigned __int16 *)hMem + 4) >> 1);
      if ( v39 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xF96,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v39,
          v65);
      v40 = (*(__int64 (__fastcall **)(_QWORD, HSTRING, unsigned int *))(**((_QWORD **)this + 67) + 144LL))(
              *((_QWORD *)this + 67),
              v70,
              &v68);
      if ( v40 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xF99,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v40,
          v65);
      if ( v68 )
      {
        v71 = 0;
        *(_QWORD *)v81 = 0;
        v72[0] = 0;
        v44 = *(__int64 (__fastcall **)(char *, _QWORD, PLSA_UNICODE_STRING *))(*((_QWORD *)this + 5) + 96LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&SystemName);
        v45 = v44((char *)this + 40, v68, &SystemName);
        if ( v45 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xFA8,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v45,
            v65);
        v46 = SystemName;
        v47 = *(__int64 (__fastcall **)(PLSA_UNICODE_STRING, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)&SystemName->Length + 88LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v71);
        v48 = v47(v46, &v71);
        if ( v48 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xFA9,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v48,
            v65);
        v49 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
                &v71,
                (__int64)v81);
        if ( v49 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xFAA,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v49,
            v65);
        v50 = v78;
        v104 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Sid", 4u, 3u);
        v51 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
                *(__int64 *)v81,
                v104,
                (__int64)v50,
                (__int64)v72);
        if ( v51 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xFAB,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v51,
            v65);
        v52 = (*(__int64 (__fastcall **)(char *, _QWORD, _QWORD))(*((_QWORD *)this + 5) + 80LL))(
                (char *)this + 40,
                v68,
                v71);
        if ( v52 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xFAC,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v52,
            v65);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v81);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v71);
      }
      else
      {
        v41 = *(__int64 (__fastcall ***)(struct Windows::System::Internal::ISignInContext *, GUID *, __int64 *))a3;
        v71 = 0;
        v42 = ((__int64 (__fastcall *)(struct Windows::System::Internal::ISignInContext *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))v41[16])(
                a3,
                &v71);
        if ( v42 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF9F,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v42,
            v65);
        v43 = (*(__int64 (__fastcall **)(char *, HSTRING, __int64 (__fastcall ***)(_QWORD, GUID *, __int64), unsigned int *))(*((_QWORD *)this + 9) + 48LL))(
                (char *)this + 72,
                v70,
                v71,
                &v68);
        if ( v43 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xFA0,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v43,
            v65);
        wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(&v71);
      }
      v53 = hMem;
      hMem = 0;
      if ( v53 )
        LocalFree(v53);
      v54 = v80;
      v80 = 0;
      if ( v54 )
        LocalFree(v54);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v77);
    }
    *(_QWORD *)v77 = string;
    v71 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))v70;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
    v55 = Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::SignInResult,Windows::System::Internal::SignInResult,unsigned int &,HSTRING__ *,enum Windows::System::Internal::SignInCaller &,HSTRING__ *>(
            (unsigned int)&v79,
            (unsigned int)&v68,
            (unsigned int)&v71,
            (unsigned int)&v75,
            (__int64)v77);
    if ( v55 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFB7,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v55,
        v66);
    Windows::System::Internal::UserManagerStatics::UpdateLastSigninResult(this, v68, 0);
    v69 = 1;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v87);
    v67 = (int)v92;
    v56 = Windows::System::Internal::UserManagerStatics::AddLoggedOnUserFromProfile(this, v68, v70, v83);
    v74 = v56;
    v92 = 0;
    if ( v56 == -2136862970 )
    {
      Windows::System::Internal::SignInResult::OverrideResultAndUserLogonStatus(v79, -2136862970);
      v74 = 0;
      v101 = 0;
      lambda_0331c0bd289c122e8b9f659c97a93081_::operator()(v100);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v84);
      WindowsDeleteString(v78);
      v78 = 0;
      WindowsDeleteString(v70);
      v70 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v93);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&SystemName);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v85);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v86);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v94);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v87);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v88);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v89);
      return 0;
    }
    else
    {
      if ( v56 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xFD2,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v56,
          v67);
      UserStaticsInternal = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(this);
      v58 = (*(__int64 (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, __int64, _QWORD))(*(_QWORD *)UserStaticsInternal + 208LL))(
              UserStaticsInternal,
              v87,
              0);
      if ( v58 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xFD5,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v58,
          v67);
      v59 = UserMgrUserModelTelemetry::Provider();
      if ( *(_DWORD *)v59 > 5u )
      {
        v81[0] = 0;
        *(_QWORD *)v77 = WindowsGetStringRawBuffer(v70, 0);
        LODWORD(v80) = v75;
        LODWORD(hMem) = v68;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          (_DWORD)v59,
          (unsigned int)byte_18012603B,
          v60,
          v61,
          (__int64)&hMem,
          (__int64)&v80,
          (__int64)v77,
          (__int64)v81);
      }
      v101 = 0;
      lambda_0331c0bd289c122e8b9f659c97a93081_::operator()(v100);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v84);
      WindowsDeleteString(v78);
      v78 = 0;
      WindowsDeleteString(v70);
      v70 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v93);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&SystemName);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v85);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v86);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v94);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v87);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v88);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v89);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x1800a0128  mov     r11, rsp
0x1800a012b  push    rbx
0x1800a012c  push    rsi
0x1800a012d  push    rdi
0x1800a012e  push    r12
0x1800a0130  push    r14
0x1800a0132  push    r15
0x1800a0134  sub     rsp, 268h
0x1800a013b  mov     rax, cs:__security_cookie
0x1800a0142  xor     rax, rsp
0x1800a0145  mov     [rsp+298h+var_48], rax
0x1800a014d  mov     r12, r9
0x1800a0150  mov     r14, r8
0x1800a0153  mov     r15, rcx
0x1800a0156  mov     [rsp+298h+var_248], edx
0x1800a015a  mov     [rsp+298h+var_158], r8
0x1800a0162  mov     rax, [rsp+298h+arg_20]
0x1800a016a  mov     [r11-160h], rax
0x1800a0171  xor     esi, esi
0x1800a0173  mov     [r11-1A8h], rsi
0x1800a017a  mov     [r11-1B0h], rsi
0x1800a0181  mov     [rsp+298h+var_218], esi
0x1800a0188  mov     [r11-1B8h], rsi
0x1800a018f  mov     [r11-188h], rsi
0x1800a0196  mov     [r11-1F8h], rsi
0x1800a019d  mov     [r11-1C0h], rsi
0x1800a01a4  mov     [r11-1C8h], rsi
0x1800a01ab  mov     [rsp+298h+string], rsi
0x1800a01b0  mov     [r11-210h], rsi
0x1800a01b7  mov     [r11-190h], rsi
0x1800a01be  mov     [rsp+298h+var_238], rsi
0x1800a01c3  mov     [rsp+298h+var_1A0], esi
0x1800a01ca  mov     [rsp+298h+var_19C], esi
0x1800a01d1  mov     [rsp+298h+var_17C], esi
0x1800a01d8  mov     [r11-200h], rsi
0x1800a01df  mov     [r11-1D0h], rsi
0x1800a01e6  mov     qword ptr [r11-198h], 0FFFFFFFFFFFFFFFFh
0x1800a01f1  mov     [rsp+298h+var_1D8], esi
0x1800a01f8  call    cs:__imp_GetTickCount
0x1800a01fe  mov     [rsp+298h+var_180], eax
0x1800a0205  mov     [rsp+298h+var_240], sil
0x1800a020a  mov     rax, cs:?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x1800a0211  mov     rbx, [rax+38h]
0x1800a0215  lea     rcx, [rsp+298h+var_1A8]
0x1800a021d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a0222  lea     rdx, [rsp+298h+var_1A8]
0x1800a022a  lea     rcx, ?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x1800a0231  mov     rax, rbx
0x1800a0234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0239  mov     rax, cs:?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x1800a0240  mov     rbx, [rax+58h]
0x1800a0244  lea     rcx, [rsp+298h+var_1B0]
0x1800a024c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a0251  lea     rdx, [rsp+298h+var_1B0]
0x1800a0259  lea     rcx, ?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x1800a0260  mov     rax, rbx
0x1800a0263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0268  mov     rax, [rsp+298h+var_160]
0x1800a0270  mov     [rax], rsi
0x1800a0273  mov     [rsp+298h+var_214], esi
0x1800a027a  test    r14, r14
0x1800a027d  jz      short loc_1800A0296
0x1800a027f  mov     rax, [r14]
0x1800a0282  lea     rdx, [rsp+298h+var_214]
0x1800a028a  mov     rcx, r14
0x1800a028d  mov     rax, [rax+40h]
0x1800a0291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0296  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x1800a029b  mov     ecx, [rax]
0x1800a029d  cmp     ecx, 5
0x1800a02a0  jbe     short loc_1800A02E4
0x1800a02a2  mov     ecx, [rsp+298h+var_214]
0x1800a02a9  mov     dword ptr [rsp+298h+var_1F0], ecx
0x1800a02b0  mov     ecx, [rsp+298h+var_248]
0x1800a02b4  mov     [rsp+298h+var_1E8], ecx
0x1800a02bb  lea     rcx, [rsp+298h+var_1F0]
0x1800a02c3  mov     [rsp+298h+var_270], rcx
0x1800a02c8  lea     rcx, [rsp+298h+var_1E8]
0x1800a02d0  mov     qword ptr [rsp+298h+var_278], rcx; int
0x1800a02d5  lea     rdx, byte_18012608B
0x1800a02dc  mov     rcx, rax
0x1800a02df  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800a02e4  lea     rax, [rsp+298h+var_1F8]
0x1800a02ec  mov     [rsp+298h+var_148], rax
0x1800a02f4  lea     rax, [rsp+298h+var_218]
0x1800a02fc  mov     [rsp+298h+var_140], rax
0x1800a0304  lea     rax, [rsp+298h+var_160]
0x1800a030c  mov     [rsp+298h+var_138], rax
0x1800a0314  lea     rax, [rsp+298h+var_180]
0x1800a031c  mov     [rsp+298h+var_130], rax
0x1800a0324  lea     rax, [rsp+298h+string]
0x1800a0329  mov     [rsp+298h+var_128], rax
0x1800a0331  lea     rax, [rsp+298h+var_240]
0x1800a0336  mov     [rsp+298h+var_120], rax
0x1800a033e  mov     [rsp+298h+var_118], r15
0x1800a0346  lea     rax, [rsp+298h+var_248]
0x1800a034b  mov     [rsp+298h+var_110], rax
0x1800a0353  mov     [rsp+298h+var_108], 1
0x1800a035b  mov     rax, [r14]
0x1800a035e  mov     rbx, [rax]
0x1800a0361  lea     rcx, [rsp+298h+var_1C0]
0x1800a0369  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a036e  lea     r8, [rsp+298h+var_1C0]
0x1800a0376  lea     rdx, _GUID_5da3f048_82e8_4c82_8bfd_c389baeda720
0x1800a037d  mov     rcx, r14
0x1800a0380  mov     rax, rbx
0x1800a0383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0388  mov     rcx, [rsp+298h]; this
0x1800a0390  test    eax, eax
0x1800a0392  js      loc_1800A0F89
0x1800a0398  mov     rdi, [rsp+298h+var_1C0]
0x1800a03a0  mov     rax, [rdi]
0x1800a03a3  mov     rbx, [rax+30h]
0x1800a03a7  mov     rcx, [rsp+298h+string]; string
0x1800a03ac  call    cs:__imp_WindowsDeleteString
0x1800a03b2  mov     [rsp+298h+string], rsi
0x1800a03b7  lea     rdx, [rsp+298h+string]
0x1800a03bc  mov     rcx, rdi
0x1800a03bf  mov     rax, rbx
0x1800a03c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a03c7  mov     rcx, [rsp+298h]; this
0x1800a03cf  test    eax, eax
0x1800a03d1  js      loc_1800A0F9D
0x1800a03d7  mov     rax, [r14]
0x1800a03da  mov     rbx, [rax]
0x1800a03dd  lea     rcx, [rsp+298h+var_1C8]
0x1800a03e5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a03ea  lea     r8, [rsp+298h+var_1C8]
0x1800a03f2  lea     rdx, _GUID_94154ae2_729f_4ad9_9907_3d8f698e14c8
0x1800a03f9  mov     rcx, r14
0x1800a03fc  mov     rax, rbx
0x1800a03ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0404  mov     rcx, [rsp+298h]; this
0x1800a040c  test    eax, eax
0x1800a040e  js      loc_1800A0FB1
0x1800a0414  mov     rcx, [rsp+298h+var_1C8]
0x1800a041c  mov     rax, [rcx]
0x1800a041f  lea     rdx, [rsp+298h+var_1D8]
0x1800a0427  mov     rax, [rax+30h]
0x1800a042b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0430  mov     rcx, [rsp+298h]; this
0x1800a0438  test    eax, eax
0x1800a043a  js      loc_1800A0FC5
0x1800a0440  mov     rax, [rsp+298h+string]
0x1800a0445  mov     qword ptr [rsp+298h+var_208], rax
0x1800a044d  mov     rax, [rsp+298h+var_238]
0x1800a0452  mov     [rsp+298h+var_230], rax
0x1800a0457  lea     rax, [rsp+298h+var_208]
0x1800a045f  mov     qword ptr [rsp+298h+var_278], rax; int
0x1800a0464  lea     r9, [rsp+298h+var_214]
0x1800a046c  lea     r8, [rsp+298h+var_230]
0x1800a0471  lea     rdx, [rsp+298h+var_248]
0x1800a0476  lea     rcx, [rsp+298h+var_1F8]
0x1800a047e  call    ??$MakeAndInitialize@VSignInResult@Internal@System@Windows@@V1234@AEAIPEAUHSTRING__@@AEAW4SignInCaller@234@PEAU5@@Details@WRL@Microsoft@@YAJPEAPEAVSignInResult@Internal@System@Windows@@AEAI$$QEAPEAUHSTRING__@@AEAW4SignInCaller@456@2@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::SignInResult,Windows::System::Internal::SignInResult,uint &,HSTRING__ *,Windows::System::Internal::SignInCaller &,HSTRING__ *>(Windows::System::Internal::SignInResult * *,uint &,HSTRING__ * &&,Windows::System::Internal::SignInCaller &,HSTRING__ * &&)
0x1800a0483  mov     rcx, [rsp+298h]; this
0x1800a048b  test    eax, eax
0x1800a048d  js      loc_1800A0FD9
0x1800a0493  mov     ebx, [rsp+298h+var_1D8]
0x1800a049a  xor     edx, edx; length
0x1800a049c  mov     rcx, [rsp+298h+var_238]; string
0x1800a04a1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a04a7  lea     rcx, [rsp+298h+var_19C]
0x1800a04af  mov     [rsp+298h+var_260], rcx; int *
0x1800a04b4  lea     rcx, [rsp+298h+var_1A0]
0x1800a04bc  mov     [rsp+298h+var_268], rcx; int *
0x1800a04c1  lea     rcx, [rsp+298h+var_198]
0x1800a04c9  mov     [rsp+298h+var_270], rcx; void **
0x1800a04ce  mov     [rsp+298h+var_278], ebx; int
0x1800a04d2  mov     r9, rax; unsigned __int16 *
0x1800a04d5  mov     r8, r14; struct Windows::System::Internal::ISignInContext *
0x1800a04d8  mov     edx, [rsp+298h+var_248]; unsigned int
0x1800a04dc  mov     rcx, r15; this
0x1800a04df  call    ?LsaLogonUserWrapper@UserManagerStatics@Internal@System@Windows@@AEAAJIPEAUISignInContext@234@PEBGIPEAPEAXPEAJ3@Z; Windows::System::Internal::UserManagerStatics::LsaLogonUserWrapper(uint,Windows::System::Internal::ISignInContext *,ushort const *,uint,void * *,long *,long *)
0x1800a04e4  mov     rcx, [rsp+298h]; this
0x1800a04ec  test    eax, eax
0x1800a04ee  js      loc_1800A0FED
0x1800a04f4  mov     edx, [rsp+298h+var_1A0]; int
0x1800a04fb  test    edx, edx
0x1800a04fd  jz      loc_1800A05F7
0x1800a0503  mov     r8d, [rsp+298h+var_19C]; int
0x1800a050b  mov     rcx, [rsp+298h+var_1F8]; this
0x1800a0513  call    ?SetResultAndUserLogonStatus@SignInResult@Internal@System@Windows@@QEAAJJJ@Z; Windows::System::Internal::SignInResult::SetResultAndUserLogonStatus(long,long)
0x1800a0518  nop
0x1800a0519  mov     [rsp+298h+var_108], sil
0x1800a0521  lea     rcx, [rsp+298h+var_148]
0x1800a0529  call    _lambda_0331c0bd289c122e8b9f659c97a93081___operator__
0x1800a052e  nop
0x1800a052f  lea     rcx, [rsp+298h+var_1D0]
0x1800a0537  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a053c  nop
0x1800a053d  mov     rcx, [rsp+298h+var_200]; string
0x1800a0545  call    cs:__imp_WindowsDeleteString
0x1800a054b  mov     [rsp+298h+var_200], rsi
0x1800a0553  mov     rcx, [rsp+298h+var_238]; string
0x1800a0558  call    cs:__imp_WindowsDeleteString
0x1800a055e  mov     [rsp+298h+var_238], rsi
0x1800a0563  lea     rcx, [rsp+298h+var_190]
0x1800a056b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a0570  nop
0x1800a0571  lea     rcx, [rsp+298h+SystemName]
0x1800a0579  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a057e  nop
0x1800a057f  mov     rcx, [rsp+298h+string]; string
0x1800a0584  call    cs:__imp_WindowsDeleteString
0x1800a058a  mov     [rsp+298h+string], rsi
0x1800a058f  lea     rcx, [rsp+298h+var_1C8]
0x1800a0597  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a059c  nop
0x1800a059d  lea     rcx, [rsp+298h+var_1C0]
0x1800a05a5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a05aa  nop
0x1800a05ab  lea     rcx, [rsp+298h+var_1F8]
0x1800a05b3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a05b8  nop
0x1800a05b9  lea     rcx, [rsp+298h+var_188]
0x1800a05c1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a05c6  nop
0x1800a05c7  lea     rcx, [rsp+298h+var_1B8]
0x1800a05cf  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a05d4  nop
0x1800a05d5  lea     rcx, [rsp+298h+var_1B0]
0x1800a05dd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a05e2  nop
0x1800a05e3  lea     rcx, [rsp+298h+var_1A8]
0x1800a05eb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a05f0  xor     eax, eax
0x1800a05f2  jmp     loc_1800A0F68
0x1800a05f7  mov     rdx, r12; void *
0x1800a05fa  call    ?CheckCancelEvent@UserManagerStatics@Internal@System@Windows@@AEAAJPEAX@Z; Windows::System::Internal::UserManagerStatics::CheckCancelEvent(void *)
0x1800a05ff  mov     rcx, [rsp+298h]; this
0x1800a0607  test    eax, eax
0x1800a0609  js      loc_1800A1001
0x1800a060f  mov     rcx, [rsp+298h+var_1B0]
0x1800a0617  mov     rax, [rcx]
0x1800a061a  lea     rdx, [rsp+298h+var_17C]
0x1800a0622  mov     [rsp+298h+var_270], rdx
0x1800a0627  mov     [rsp+298h+var_278], 54h ; 'T'; int
0x1800a062f  lea     r9, [rsp+298h+var_A8]
0x1800a0637  mov     r8d, 1
0x1800a063d  mov     rdx, [rsp+298h+var_198]
0x1800a0645  mov     rax, [rax+18h]
0x1800a0649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a064e  mov     rcx, [rsp+298h]; this
0x1800a0656  test    eax, eax
0x1800a0658  js      loc_1800A1015
0x1800a065e  mov     rdi, [rsp+298h+var_1A8]
0x1800a0666  mov     rax, [rdi]
0x1800a0669  mov     rbx, [rax+20h]
0x1800a066d  xor     edx, edx
0x1800a066f  lea     rcx, [rsp+298h+var_1D0]
0x1800a0677  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a067c  lea     r8, [rsp+298h+var_1D0]
0x1800a0684  mov     rdx, [rsp+298h+var_A8]
0x1800a068c  mov     rcx, rdi
0x1800a068f  mov     rax, rbx
0x1800a0692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0697  mov     rcx, [rsp+298h]; this
0x1800a069f  test    eax, eax
0x1800a06a1  jz      loc_1800A1029
0x1800a06a7  mov     rax, [rsp+298h+var_1D0]
0x1800a06af  mov     qword ptr [rsp+298h+var_208], rax
0x1800a06b7  lea     rdx, [rsp+298h+var_208]
0x1800a06bf  lea     rcx, [rsp+298h+var_200]; string
0x1800a06c7  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x1800a06cc  mov     rcx, [rsp+298h]; this
0x1800a06d4  test    eax, eax
0x1800a06d6  js      loc_1800A103A
0x1800a06dc  lea     rcx, [rsp+298h+SystemName]
0x1800a06e4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a06e9  lea     r8, [rsp+298h+SystemName]; struct Windows::System::Internal::IUserProfile **
0x1800a06f1  mov     rdx, [rsp+298h+var_200]; HSTRING
0x1800a06f9  mov     rcx, r15; this
0x1800a06fc  call    ?GetUserBySid@UserManagerStatics@Internal@System@Windows@@AEAAJPEAUHSTRING__@@PEAPEAUIUserProfile@234@@Z; Windows::System::Internal::UserManagerStatics::GetUserBySid(HSTRING__ *,Windows::System::Internal::IUserProfile * *)
0x1800a0701  mov     rcx, [rsp+298h]; this
0x1800a0709  test    eax, eax
0x1800a070b  js      loc_1800A104E
0x1800a0711  mov     rcx, [rsp+298h+SystemName]; SystemName
0x1800a0719  test    rcx, rcx
0x1800a071c  jz      short loc_1800A0783
0x1800a071e  mov     rax, [rcx]
0x1800a0721  lea     rdx, [rsp+298h+var_248]
0x1800a0726  mov     rax, [rax+30h]
0x1800a072a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a072f  mov     rcx, [rsp+298h]; this
0x1800a0737  test    eax, eax
0x1800a0739  js      loc_1800A1062
0x1800a073f  mov     rdi, [rsp+298h+SystemName]
0x1800a0747  mov     rax, [rdi]
0x1800a074a  mov     rbx, [rax+40h]
0x1800a074e  mov     rcx, [rsp+298h+var_238]; string
0x1800a0753  call    cs:__imp_WindowsDeleteString
0x1800a0759  mov     [rsp+298h+var_238], rsi
0x1800a075e  lea     rdx, [rsp+298h+var_238]
0x1800a0763  mov     rcx, rdi
0x1800a0766  mov     rax, rbx
0x1800a0769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a076e  mov     rcx, [rsp+298h]; this
0x1800a0776  test    eax, eax
0x1800a0778  js      loc_1800A1076
0x1800a077e  jmp     loc_1800A0AFA
  ... truncated ...
```
