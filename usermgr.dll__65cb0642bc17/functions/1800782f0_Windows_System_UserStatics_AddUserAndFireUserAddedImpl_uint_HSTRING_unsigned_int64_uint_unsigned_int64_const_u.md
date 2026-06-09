# Windows::System::UserStatics::AddUserAndFireUserAddedImpl(uint,HSTRING__ *,unsigned __int64,uint,unsigned __int64 * const,unsigned __int64,HSTRING__ *,Windows::System::IUser *,uint,Windows::System::UserAuthenticationStatus,Windows::Foundation::Collections::IPropertySet *,bool,Windows::System::IUser * *)

- ea: `0x1800782f0`
- end: `0x180078e0b`
- name: `?AddUserAndFireUserAddedImpl@UserStatics@System@Windows@@EEAAJIPEAUHSTRING__@@_KIQEA_K10PEAUIUser@23@IW4UserAuthenticationStatus@23@PEAUIPropertySet@Collections@Foundation@3@_NPEAPEAU523@@Z`
- size: `2843`
- prototype: `int __high(unsigned int, HSTRING, unsigned __int64, unsigned int, unsigned __int64 *const, unsigned __int64, HSTRING, struct Windows::System::IUser *, unsigned int, enum Windows::System::UserAuthenticationStatus, struct Windows::Foundation::Collections::IPropertySet *, bool, struct Windows::System::IUser **)`
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001524`
- `0x180006130`
- `0x1800062e4`
- `0x180007920`
- `0x18000acdc`
- `0x18000ce48`
- `0x18000eec0`
- `0x180012890`
- `0x1800179c0`
- `0x180024828`
- `0x180028c0c`
- `0x180039664`
- `0x18003991c`
- `0x18003a270`
- `0x18004a338`
- `0x18004e58c`
- `0x180053018`
- `0x180053304`
- `0x18006dfbc`
- `0x1800782f0`
- `0x1800dc080`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180078421`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180078421`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18007897d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18007897d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800789b1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800789b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180078347`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180078b8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180078347`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180078b8a`
- `ext-ms-win-security-efswrt-l1-1-3!CdplProtectKnownUserFolders` at `0x18007899b`
- `ext-ms-win-security-efswrt-l1-1-3!CdplProtectKnownUserFolders` at `0x18007899b`

## string_xrefs

- `0x180078c75`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180078c8d`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180078ca1`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180078cb5`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180078cc9`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180078cdd`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180078cf1`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180078d05`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180078d1a`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180078d2f`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180078d43`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180078d57`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180078d6b`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180078d80`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180078d95`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180078da6`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180078dbb`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180078dd0`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180078de4`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180078df8`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 Windows::System::UserStatics::AddUserAndFireUserAddedImpl(__int64 *a1, unsigned int a2, ...)
{
  HANDLE v2; // r12
  HSTRING v3; // rdi
  __int64 *v5; // rsi
  const struct _tlgProvider_t *v6; // rax
  int v7; // ebx
  unsigned int v8; // r13d
  int v9; // r8d
  int v10; // r9d
  bool v11; // zf
  char v12; // al
  __int64 (__fastcall ***v13)(_QWORD, GUID *, __int64); // rbx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  unsigned int v17; // r14d
  int v18; // eax
  __int64 v19; // r12
  int v20; // eax
  _DWORD *v21; // rax
  __int64 v22; // rcx
  int v23; // eax
  int v24; // eax
  __int64 (__fastcall ***v25)(_QWORD, GUID *, __int64); // r15
  __int64 (__fastcall *v26)(_QWORD, GUID *, unsigned __int64 *); // rbx
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  _DWORD *v32; // rax
  int v33; // eax
  const char *v34; // r9
  int v35; // eax
  __int64 v36; // rax
  int v37; // eax
  __int64 v38; // rax
  int v39; // eax
  int v40; // eax
  char v41; // al
  unsigned int (__fastcall *v42)(__int64 *, _QWORD, __int64 (__fastcall ****)()); // rbx
  const struct _tlgProvider_t *v43; // rbx
  int v44; // r8d
  int v45; // r9d
  __int64 result; // rax
  const struct _tlgProvider_t *v47; // rax
  int v48; // ebx
  wil *v49; // rcx
  int v50; // r8d
  int v51; // r9d
  int v52; // [rsp+20h] [rbp-108h]
  int v53; // [rsp+20h] [rbp-108h]
  char v54[8]; // [rsp+60h] [rbp-C8h] BYREF
  unsigned __int64 v55; // [rsp+68h] [rbp-C0h] BYREF
  char v56[8]; // [rsp+70h] [rbp-B8h] BYREF
  int v57[2]; // [rsp+78h] [rbp-B0h] BYREF
  __int64 (__fastcall **v58)(); // [rsp+80h] [rbp-A8h] BYREF
  unsigned int v59; // [rsp+88h] [rbp-A0h] BYREF
  __int64 (__fastcall ***v60)(_QWORD, GUID *, __int64); // [rsp+90h] [rbp-98h] BYREF
  _QWORD v61[2]; // [rsp+98h] [rbp-90h] BYREF
  PCWSTR v62; // [rsp+A8h] [rbp-80h] BYREF
  void *StringRawBuffer; // [rsp+B0h] [rbp-78h] BYREF
  char v64[8]; // [rsp+B8h] [rbp-70h] BYREF
  __int64 v65; // [rsp+C0h] [rbp-68h] BYREF
  __int64 (__fastcall ***v66)(_QWORD, GUID *, __int64); // [rsp+C8h] [rbp-60h] BYREF
  __int64 (__fastcall **v67)(); // [rsp+D0h] [rbp-58h] BYREF
  char v68[16]; // [rsp+D8h] [rbp-50h] BYREF
  __int64 (__fastcall ***v69)(); // [rsp+E8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]
  unsigned int v72; // [rsp+138h] [rbp+10h] BYREF
  HSTRING string; // [rsp+140h] [rbp+18h] BYREF
  va_list stringa; // [rsp+140h] [rbp+18h]
  HANDLE hToken; // [rsp+148h] [rbp+20h]
  __int64 v76; // [rsp+150h] [rbp+28h] BYREF
  va_list va1; // [rsp+150h] [rbp+28h]
  __int64 v78; // [rsp+158h] [rbp+30h] BYREF
  va_list va2; // [rsp+158h] [rbp+30h]
  __int64 (__fastcall ***v80)(_QWORD, GUID *, __int64); // [rsp+160h] [rbp+38h]
  __int64 v81; // [rsp+168h] [rbp+40h] BYREF
  va_list va3; // [rsp+168h] [rbp+40h]
  __int64 v83; // [rsp+170h] [rbp+48h] BYREF
  va_list va4; // [rsp+170h] [rbp+48h]
  __int64 v85; // [rsp+178h] [rbp+50h] BYREF
  va_list va5; // [rsp+178h] [rbp+50h]
  __int64 v87; // [rsp+180h] [rbp+58h]
  __int64 v88; // [rsp+188h] [rbp+60h]
  __int64 v89; // [rsp+190h] [rbp+68h]
  __int64 (__fastcall ***v90)(); // [rsp+198h] [rbp+70h] BYREF
  va_list va6; // [rsp+198h] [rbp+70h]
  va_list va7; // [rsp+1A0h] [rbp+78h] BYREF

  va_start(va7, a2);
  va_start(va6, a2);
  va_start(va5, a2);
  va_start(va4, a2);
  va_start(va3, a2);
  va_start(va2, a2);
  va_start(va1, a2);
  va_start(stringa, a2);
  string = va_arg(va1, HSTRING);
  hToken = va_arg(va1, HANDLE);
  va_copy(va2, va1);
  v76 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v78 = va_arg(va3, _QWORD);
  v80 = va_arg(va3, __int64 (__fastcall ***)(_QWORD, GUID *, __int64));
  va_copy(va4, va3);
  v81 = va_arg(va4, _QWORD);
  va_copy(va5, va4);
  v83 = va_arg(va5, _QWORD);
  va_copy(va6, va5);
  v85 = va_arg(va6, _QWORD);
  v87 = va_arg(va6, _QWORD);
  v88 = va_arg(va6, _QWORD);
  v89 = va_arg(va6, _QWORD);
  va_copy(va7, va6);
  v90 = va_arg(va7, __int64 (__fastcall ***)());
  v72 = a2;
  v2 = hToken;
  v3 = string;
  v5 = a1;
  v6 = UserMgrUserModelTelemetry::Provider();
  v7 = (int)v6;
  v8 = v85;
  if ( *(_DWORD *)v6 > 5u )
  {
    v57[0] = v85;
    StringRawBuffer = (void *)WindowsGetStringRawBuffer(v3, 0);
    v66 = v80;
    LODWORD(v60) = v76;
    v61[0] = v2;
    LODWORD(v55) = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v7,
      (unsigned int)&unk_180123780,
      v9,
      v10,
      (__int64)&v55,
      (__int64)v61,
      (__int64)&v60,
      (__int64)&v66,
      (__int64)&StringRawBuffer,
      (__int64)v57);
  }
  try
  {
    if ( !v90 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x243,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)0x80004003LL,
        v52);
    *v90 = 0;
    v58 = 0;
    v65 = 0;
    v66 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 16));
    v62 = (PCWSTR)(v5 + 16);
    v55 = __PAIR64__(v8, a2);
    std::_Tree<std::_Tmap_traits<std::pair<unsigned int,unsigned long>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<unsigned int,unsigned long>>,std::allocator<std::pair<std::pair<unsigned int,unsigned long> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::find(
      v5 + 21,
      v61,
      &v55);
    if ( v61[0] != v5[21]
      || (v11 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::pair<unsigned int,unsigned long>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<unsigned int,unsigned long>>,std::allocator<std::pair<std::pair<unsigned int,unsigned long> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::find(
                             v5 + 23,
                             v61,
                             &v55) == v5[23],
          v12 = 0,
          !v11) )
    {
      v12 = 1;
    }
    if ( v12 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x26D,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)0x80A20303LL,
        v52);
    v13 = v80;
    v61[0] = v80;
    StringRawBuffer = v2;
    v14 = Microsoft::WRL::Details::MakeAndInitialize<Windows::System::User,Windows::System::User,unsigned int &,HSTRING__ * &,void *,unsigned int &,unsigned __int64 * &,void *,HSTRING__ * &,Windows::System::IUser * &,unsigned int &>(
            (unsigned int)&v66,
            (unsigned int)&v72,
            (unsigned int)stringa,
            (unsigned int)&StringRawBuffer,
            (__int64)va1,
            (__int64)va2,
            (__int64)v61,
            (__int64)va3,
            (__int64)va4,
            (__int64)va5);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x278,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)(unsigned int)v14,
        v53);
    v15 = Microsoft::WRL::ComPtr<Windows::System::User>::As<Windows::System::IUser>(&v66, (__int64)&v58);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x279,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)(unsigned int)v15,
        v53);
    v16 = Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
            (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))&v58,
            &v65);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x27A,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)(unsigned int)v16,
        v53);
    v17 = v87;
    if ( (_DWORD)v87 )
    {
      v18 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v65 + 56LL))(v65, (unsigned int)v87);
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x27D,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
          (const char *)(unsigned int)v18,
          v53);
    }
    v19 = v88;
    if ( v88 )
    {
      v54[0] = 0;
      v20 = (*(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v65 + 112LL))(v65, v88, v54);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x282,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
          (const char *)(unsigned int)v20,
          v53);
    }
    v61[0] = v58;
    v55 = __PAIR64__(v8, v72);
    v21 = std::pair<std::pair<unsigned int,unsigned long> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>::pair<std::pair<unsigned int,unsigned long> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>(
            &StringRawBuffer,
            &v55,
            v61);
    std::_Tree<std::_Tmap_traits<std::pair<unsigned int,unsigned long>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<unsigned int,unsigned long>>,std::allocator<std::pair<std::pair<unsigned int,unsigned long> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::insert(
      v5 + 21,
      &v67,
      v21);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v64);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v5 + 51);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl)
      && (unsigned int)LUAIsShadowAdminEnabled(v22) )
    {
      v54[0] = 0;
      v23 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v65 + 168LL))(v65, v54);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x29D,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
          (const char *)(unsigned int)v23,
          v53);
      if ( v54[0] )
      {
        v60 = 0;
        v61[0] = v13;
        StringRawBuffer = hToken;
        v24 = Microsoft::WRL::Details::MakeAndInitialize<Windows::System::User,Windows::System::User,unsigned int &,HSTRING__ * &,void *,unsigned int &,unsigned __int64 * &,void *,HSTRING__ * &,Windows::System::IUser * &,unsigned int &>(
                (unsigned int)&v60,
                (unsigned int)&v72,
                (unsigned int)stringa,
                (unsigned int)&StringRawBuffer,
                (__int64)va1,
                (__int64)va2,
                (__int64)v61,
                (__int64)va3,
                (__int64)va4,
                (__int64)va5);
        if ( v24 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2AC,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
            (const char *)(unsigned int)v24,
            v53);
        v55 = 0;
        v25 = v60;
        v26 = (__int64 (__fastcall *)(_QWORD, GUID *, unsigned __int64 *))**v60;
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
        v27 = v26(v25, &GUID_ebe7ab25_f6a9_4472_9fa2_e979ef15ff58, &v55);
        if ( v27 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2AF,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
            (const char *)(unsigned int)v27,
            v53);
        if ( v17 )
        {
          v28 = (*(__int64 (__fastcall **)(unsigned __int64, _QWORD))(*(_QWORD *)v55 + 56LL))(v55, v17);
          if ( v28 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x2B3,
              (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
              (const char *)(unsigned int)v28,
              v53);
        }
        if ( v19 )
        {
          v56[0] = 0;
          v29 = (*(__int64 (__fastcall **)(unsigned __int64, __int64, char *))(*(_QWORD *)v55 + 112LL))(v55, v19, v56);
          if ( v29 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x2B9,
              (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
              (const char *)(unsigned int)v29,
              v53);
        }
        v30 = (*(__int64 (__fastcall **)(unsigned __int64))(*(_QWORD *)v55 + 160LL))(v55);
        if ( v30 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2BC,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
            (const char *)(unsigned int)v30,
            v53);
        *(_QWORD *)v57 = 0;
        v31 = Microsoft::WRL::ComPtr<Windows::System::User>::As<Windows::System::IUser>(&v60, (__int64)v57);
        if ( v31 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2BF,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
            (const char *)(unsigned int)v31,
            v53);
        v61[0] = *(_QWORD *)v57;
        StringRawBuffer = (void *)__PAIR64__(v8, v72);
        v32 = std::pair<std::pair<unsigned int,unsigned long> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>::pair<std::pair<unsigned int,unsigned long> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>(
                &v67,
                &StringRawBuffer,
                v61);
        std::_Tree<std::_Tmap_traits<std::pair<unsigned int,unsigned long>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<unsigned int,unsigned long>>,std::allocator<std::pair<std::pair<unsigned int,unsigned long> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::insert(
          v5 + 58,
          v61,
          v32);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v68);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v57);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
        if ( v25 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v25)[2])(v25);
      }
    }
    Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v62);
    if ( v66 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v66)[2])(v66);
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v58);
    *v90 = v58;
    if ( (unsigned __int8)IsCdplIsSupportedPresent() )
    {
      v57[0] = 0;
      CdplIsSupportedInl(v57);
      if ( v57[0] )
      {
        v62 = 0;
        v33 = (*(__int64 (__fastcall **)(__int64, PCWSTR *))(*(_QWORD *)v65 + 80LL))(v65, &v62);
        if ( v33 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2D6,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
            (const char *)(unsigned int)v33,
            v53);
        if ( !ImpersonateLoggedOnUser(hToken) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x2D7,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
            v34);
        BYTE1(v90) = 1;
        v35 = CdplProtectKnownUserFolders(retaddr);
        if ( v35 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2E0,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
            (const char *)(unsigned int)v35,
            v53);
        RevertToSelf();
      }
    }
    v36 = *v5;
    v90 = &v67;
    v67 = off_1800F0398;
    v69 = &v67;
    v37 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, __int64 (__fastcall **)(), __int64 (__fastcall ***)()))(v36 + 64))(
            v5,
            v5 + 55,
            v58,
            &v67);
    if ( v37 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2ED,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)(unsigned int)v37,
        v53);
    v38 = *v5;
    v90 = &v67;
    v67 = off_1800F0360;
    v69 = &v67;
    v39 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, __int64 (__fastcall **)(), __int64 (__fastcall ***)()))(v38 + 64))(
            v5,
            v5 + 52,
            v58,
            &v67);
    if ( v39 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2F2,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)(unsigned int)v39,
        v53);
    v59 = 0;
    v40 = (*((__int64 (__fastcall **)(__int64 (__fastcall **)(), unsigned int *))*v58 + 7))(v58, &v59);
    if ( v40 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2F6,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)(unsigned int)v40,
        v53);
    if ( v59 )
    {
      LOBYTE(v90) = 0;
      try
      {
        v41 = Windows::System::Internal::WCOS::IsResourceAccount<Windows::System::IUser *>(v58);
        LOBYTE(v90) = v41;
      }
      catch ( ... )
      {
        v5 = a1;
        v8 = v85;
        v41 = (char)v90;
      }
      if ( !v41 )
      {
        v90 = 0;
        v42 = *(unsigned int (__fastcall **)(__int64 *, _QWORD, __int64 (__fastcall ****)()))(v5[7] + 72);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((__int64 (__fastcall ****)())va6);
        if ( v42(v5 + 7, v8, (__int64 (__fastcall ****)())va6) == -2147023728 )
          (*(void (__fastcall **)(__int64 *, _QWORD, _QWORD))(v5[7] + 80))(v5 + 7, v8, v72);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((__int64 (__fastcall ****)())va6);
      }
    }
    v43 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v43 > 5u )
    {
      LODWORD(v90) = 0;
      LODWORD(v55) = v8;
      v62 = WindowsGetStringRawBuffer(string, 0);
      v61[0] = v80;
      LODWORD(v60) = v76;
      StringRawBuffer = hToken;
      v57[0] = v72;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v43,
        (unsigned int)&unk_180123700,
        v44,
        v45,
        (__int64)v57,
        (__int64)&StringRawBuffer,
        (__int64)&v60,
        (__int64)v61,
        (__int64)&v62,
        (__int64)&v55,
        (__int64)va6);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v65);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v58);
    result = 0;
  }
  catch ( ... )
  {
    v47 = UserMgrUserModelTelemetry::Provider();
    v48 = (int)v47;
    v49 = (wil *)*(unsigned int *)v47;
    if ( (unsigned int)v49 > 5 )
    {
      LODWORD(v90) = wil::ResultFromCaughtException(v49);
      LODWORD(v55) = v85;
      v62 = WindowsGetStringRawBuffer(string, 0);
      v61[0] = v80;
      LODWORD(v60) = v76;
      StringRawBuffer = hToken;
      v59 = v72;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v48,
        (unsigned int)byte_18012366D,
        v50,
        v51,
        (__int64)&v59,
        (__int64)&StringRawBuffer,
        (__int64)&v60,
        (__int64)v61,
        (__int64)&v62,
        (__int64)&v55,
        (__int64)va6);
    }
    LODWORD(v90) = wil::ResultFromCaughtException(v49);
    return (unsigned int)v90;
  }
  return result;
}

```

## disassembly

```asm
0x1800782f0  mov     rax, rsp
0x1800782f3  mov     [rax+20h], r9
0x1800782f7  mov     [rax+18h], r8
0x1800782fb  mov     [rax+10h], edx
0x1800782fe  mov     [rax+8], rcx
0x180078302  push    rbx
0x180078303  push    rsi
0x180078304  push    rdi
0x180078305  push    r12
0x180078307  push    r13
0x180078309  push    r14
0x18007830b  push    r15
0x18007830d  sub     rsp, 0F0h
0x180078314  mov     r12, r9
0x180078317  mov     rdi, r8
0x18007831a  mov     r14d, edx
0x18007831d  mov     rsi, rcx
0x180078320  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x180078325  mov     rbx, rax
0x180078328  mov     r10d, [rax]
0x18007832b  cmp     r10d, 5
0x18007832f  jbe     loc_1800783D9
0x180078335  mov     r13d, dword ptr [rsp+128h+arg_48]
0x18007833d  mov     [rsp+128h+var_B0], r13d
0x180078342  xor     edx, edx; length
0x180078344  mov     rcx, rdi; string
0x180078347  call    cs:__imp_WindowsGetStringRawBuffer
0x18007834d  mov     [rsp+128h+var_78], rax
0x180078355  mov     rax, [rsp+128h+arg_30]
0x18007835d  mov     [rsp+128h+var_60], rax
0x180078365  mov     eax, dword ptr [rsp+128h+arg_20]
0x18007836c  mov     dword ptr [rsp+128h+var_98], eax
0x180078373  mov     [rsp+128h+var_90], r12
0x18007837b  mov     dword ptr [rsp+128h+var_C0], r14d
0x180078380  lea     rax, [rsp+128h+var_B0]
0x180078385  mov     [rsp+128h+var_E0], rax
0x18007838a  lea     rax, [rsp+128h+var_78]
0x180078392  mov     [rsp+128h+var_E8], rax
0x180078397  lea     rax, [rsp+128h+var_60]
0x18007839f  mov     [rsp+128h+var_F0], rax
0x1800783a4  lea     rax, [rsp+128h+var_98]
0x1800783ac  mov     [rsp+128h+var_F8], rax
0x1800783b1  lea     rax, [rsp+128h+var_90]
0x1800783b9  mov     [rsp+128h+var_100], rax
0x1800783be  lea     rax, [rsp+128h+var_C0]
0x1800783c3  mov     qword ptr [rsp+128h+var_108], rax
0x1800783c8  lea     rdx, unk_180123780
0x1800783cf  mov     rcx, rbx
0x1800783d2  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U1@U2@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@34AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800783d7  jmp     short loc_1800783E1
0x1800783d9  mov     r13d, dword ptr [rsp+128h+arg_48]
0x1800783e1  mov     rcx, [rsp+128h]; this
0x1800783e9  xor     edi, edi
0x1800783eb  mov     rax, [rsp+128h+arg_68]
0x1800783f3  test    rax, rax
0x1800783f6  jz      loc_180078C6F
0x1800783fc  mov     [rax], rdi
0x1800783ff  mov     [rsp+128h+var_A8], rdi
0x180078407  mov     [rsp+128h+var_68], rdi
0x18007840f  mov     [rsp+128h+var_60], rdi
0x180078417  lea     rbx, [rsi+80h]
0x18007841e  mov     rcx, rbx; lpCriticalSection
0x180078421  call    cs:__imp_EnterCriticalSection
0x180078427  mov     [rsp+128h+var_80], rbx
0x18007842f  mov     dword ptr [rsp+128h+var_C0], r14d
0x180078434  mov     dword ptr [rsp+128h+var_C0+4], r13d
0x180078439  lea     r15, [rsi+0A8h]
0x180078440  lea     r8, [rsp+128h+var_C0]
0x180078445  lea     rdx, [rsp+128h+var_90]
0x18007844d  mov     rcx, r15
0x180078450  call    ?find@?$_Tree@V?$_Tmap_traits@U?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@U?$less@U?$pair@IK@std@@@2@V?$allocator@U?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@std@@@std@@@2@AEBU?$pair@IK@2@@Z; std::_Tree<std::_Tmap_traits<std::pair<uint,ulong>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<uint,ulong>>,std::allocator<std::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::find(std::pair<uint,ulong> const &)
0x180078455  mov     rdx, [r15]
0x180078458  cmp     [rsp+128h+var_90], rdx
0x180078460  jnz     short loc_180078489
0x180078462  lea     rbx, [rsi+0B8h]
0x180078469  lea     r8, [rsp+128h+var_C0]
0x18007846e  lea     rdx, [rsp+128h+var_90]
0x180078476  mov     rcx, rbx
0x180078479  call    ?find@?$_Tree@V?$_Tmap_traits@U?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@U?$less@U?$pair@IK@std@@@2@V?$allocator@U?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@std@@@std@@@2@AEBU?$pair@IK@2@@Z; std::_Tree<std::_Tmap_traits<std::pair<uint,ulong>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<uint,ulong>>,std::allocator<std::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::find(std::pair<uint,ulong> const &)
0x18007847e  mov     rcx, [rbx]
0x180078481  cmp     [rax], rcx
0x180078484  mov     al, dil
0x180078487  jz      short loc_18007848B
0x180078489  mov     al, 1
0x18007848b  mov     rcx, [rsp+128h]; this
0x180078493  test    al, al
0x180078495  jnz     loc_180078C87
0x18007849b  mov     rbx, [rsp+128h+arg_30]
0x1800784a3  mov     [rsp+128h+var_90], rbx
0x1800784ab  mov     [rsp+128h+var_78], r12
0x1800784b3  lea     rax, [rsp+128h+arg_48]
0x1800784bb  mov     [rsp+128h+var_E0], rax
0x1800784c0  lea     rax, [rsp+128h+arg_40]
0x1800784c8  mov     [rsp+128h+var_E8], rax
0x1800784cd  lea     rax, [rsp+128h+arg_38]
0x1800784d5  mov     [rsp+128h+var_F0], rax
0x1800784da  lea     rax, [rsp+128h+var_90]
0x1800784e2  mov     [rsp+128h+var_F8], rax
0x1800784e7  lea     rax, [rsp+128h+arg_28]
0x1800784ef  mov     [rsp+128h+var_100], rax
0x1800784f4  lea     rax, [rsp+128h+arg_20]
0x1800784fc  mov     qword ptr [rsp+128h+var_108], rax; int
0x180078501  lea     r9, [rsp+128h+var_78]
0x180078509  lea     r8, [rsp+128h+string]
0x180078511  lea     rdx, [rsp+128h+arg_8]
0x180078519  lea     rcx, [rsp+128h+var_60]
0x180078521  call    ??$MakeAndInitialize@VUser@System@Windows@@V123@AEAIAEAPEAUHSTRING__@@PEAXAEAIAEAQEA_KPEAXAEAPEAU4@AEAPEAUIUser@23@AEAI@Details@WRL@Microsoft@@YAJPEAPEAVUser@System@Windows@@AEAIAEAPEAUHSTRING__@@$$QEAPEAX1AEAQEA_K32AEAPEAUIUser@45@1@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::System::User,Windows::System::User,uint &,HSTRING__ * &,void *,uint &,unsigned __int64 * &,void *,HSTRING__ * &,Windows::System::IUser * &,uint &>(Windows::System::User * *,uint &,HSTRING__ * &,void * &&,uint &,unsigned __int64 * &,void * &&,HSTRING__ * &,Windows::System::IUser * &,uint &)
0x180078526  mov     rcx, [rsp+128h]; this
0x18007852e  test    eax, eax
0x180078530  js      loc_180078C9E
0x180078536  lea     rdx, [rsp+128h+var_A8]
0x18007853e  lea     rcx, [rsp+128h+var_60]
0x180078546  call    ??$As@UIUser@System@Windows@@@?$ComPtr@VUser@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::User>::As<Windows::System::IUser>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::IUser>>)
0x18007854b  mov     rcx, [rsp+128h]; this
0x180078553  test    eax, eax
0x180078555  js      loc_180078CB2
0x18007855b  lea     rdx, [rsp+128h+var_68]
0x180078563  lea     rcx, [rsp+128h+var_A8]
0x18007856b  call    ??$As@UIUserInternal@Implementation@Internal@System@Windows@@@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserInternal>>)
0x180078570  mov     rcx, [rsp+128h]; this
0x180078578  test    eax, eax
0x18007857a  js      loc_180078CC6
0x180078580  mov     r14d, dword ptr [rsp+128h+arg_50]
0x180078588  test    r14d, r14d
0x18007858b  jz      short loc_1800785B4
0x18007858d  mov     rcx, [rsp+128h+var_68]
0x180078595  mov     rax, [rcx]
0x180078598  mov     edx, r14d
0x18007859b  mov     rax, [rax+38h]
0x18007859f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800785a4  mov     rcx, [rsp+128h]; this
0x1800785ac  test    eax, eax
0x1800785ae  js      loc_180078CDA
0x1800785b4  mov     r12, [rsp+128h+arg_58]
0x1800785bc  test    r12, r12
0x1800785bf  jz      short loc_1800785F2
0x1800785c1  mov     [rsp+128h+var_C8], dil
0x1800785c6  mov     rcx, [rsp+128h+var_68]
0x1800785ce  mov     rax, [rcx]
0x1800785d1  lea     r8, [rsp+128h+var_C8]
0x1800785d6  mov     rdx, r12
0x1800785d9  mov     rax, [rax+70h]
0x1800785dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800785e2  mov     rcx, [rsp+128h]; this
0x1800785ea  test    eax, eax
0x1800785ec  js      loc_180078CEE
0x1800785f2  mov     rax, [rsp+128h+var_A8]
0x1800785fa  mov     [rsp+128h+var_90], rax
0x180078602  mov     eax, [rsp+128h+arg_8]
0x180078609  mov     dword ptr [rsp+128h+var_C0], eax
0x18007860d  mov     dword ptr [rsp+128h+var_C0+4], r13d
0x180078612  lea     r8, [rsp+128h+var_90]
0x18007861a  lea     rdx, [rsp+128h+var_C0]
0x18007861f  lea     rcx, [rsp+128h+var_78]
0x180078627  call    ??$?0U?$pair@II@std@@PEAUIUser@System@Windows@@@?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@QEAA@$$QEAU?$pair@II@1@$$QEAPEAUIUser@System@Windows@@PEAPEAX@Z; std::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>(std::pair<uint,uint> &&,Windows::System::IUser * &&,void * *)
0x18007862c  nop
0x18007862d  mov     r8, rax
0x180078630  lea     rdx, [rsp+128h+var_58]
0x180078638  mov     rcx, r15
0x18007863b  call    ?insert@?$_Tree@V?$_Tmap_traits@U?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@U?$less@U?$pair@IK@std@@@2@V?$allocator@U?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@_N@2@$$QEAU?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@2@@Z; std::_Tree<std::_Tmap_traits<std::pair<uint,ulong>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<uint,ulong>>,std::allocator<std::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::insert(std::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>> &&)
0x180078640  nop
0x180078641  lea     rcx, [rsp+128h+var_70]
0x180078649  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18007864e  lea     rcx, [rsi+198h]
0x180078655  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007865a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x180078661  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x180078666  test    al, al
0x180078668  jz      loc_1800788D8
0x18007866e  call    LUAIsShadowAdminEnabled
0x180078673  test    eax, eax
0x180078675  jz      loc_1800788D8
0x18007867b  mov     [rsp+128h+var_C8], dil
0x180078680  mov     rcx, [rsp+128h+var_68]
0x180078688  mov     rax, [rcx]
0x18007868b  lea     rdx, [rsp+128h+var_C8]
0x180078690  mov     rax, [rax+0A8h]
0x180078697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007869c  mov     rcx, [rsp+128h]; this
0x1800786a4  test    eax, eax
0x1800786a6  js      loc_180078D02
0x1800786ac  cmp     [rsp+128h+var_C8], dil
0x1800786b1  jz      loc_1800788D8
0x1800786b7  mov     [rsp+128h+var_98], rdi
0x1800786bf  mov     [rsp+128h+var_90], rbx
0x1800786c7  mov     rax, [rsp+128h+hToken]
0x1800786cf  mov     [rsp+128h+var_78], rax
0x1800786d7  lea     rax, [rsp+128h+arg_48]
0x1800786df  mov     [rsp+128h+var_E0], rax
0x1800786e4  lea     rax, [rsp+128h+arg_40]
0x1800786ec  mov     [rsp+128h+var_E8], rax
0x1800786f1  lea     rax, [rsp+128h+arg_38]
0x1800786f9  mov     [rsp+128h+var_F0], rax
0x1800786fe  lea     rax, [rsp+128h+var_90]
0x180078706  mov     [rsp+128h+var_F8], rax
0x18007870b  lea     rax, [rsp+128h+arg_28]
0x180078713  mov     [rsp+128h+var_100], rax
0x180078718  lea     rax, [rsp+128h+arg_20]
0x180078720  mov     qword ptr [rsp+128h+var_108], rax; int
0x180078725  lea     r9, [rsp+128h+var_78]
0x18007872d  lea     r8, [rsp+128h+string]
0x180078735  lea     rdx, [rsp+128h+arg_8]
0x18007873d  lea     rcx, [rsp+128h+var_98]
0x180078745  call    ??$MakeAndInitialize@VUser@System@Windows@@V123@AEAIAEAPEAUHSTRING__@@PEAXAEAIAEAQEA_KPEAXAEAPEAU4@AEAPEAUIUser@23@AEAI@Details@WRL@Microsoft@@YAJPEAPEAVUser@System@Windows@@AEAIAEAPEAUHSTRING__@@$$QEAPEAX1AEAQEA_K32AEAPEAUIUser@45@1@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::System::User,Windows::System::User,uint &,HSTRING__ * &,void *,uint &,unsigned __int64 * &,void *,HSTRING__ * &,Windows::System::IUser * &,uint &>(Windows::System::User * *,uint &,HSTRING__ * &,void * &&,uint &,unsigned __int64 * &,void * &&,HSTRING__ * &,Windows::System::IUser * &,uint &)
0x18007874a  mov     rcx, [rsp+128h]; this
0x180078752  test    eax, eax
0x180078754  js      loc_180078D17
0x18007875a  mov     [rsp+128h+var_C0], rdi
0x18007875f  mov     r15, [rsp+128h+var_98]
0x180078767  mov     rax, [r15]
0x18007876a  mov     rbx, [rax]
0x18007876d  lea     rcx, [rsp+128h+var_C0]
0x180078772  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180078777  lea     r8, [rsp+128h+var_C0]
0x18007877c  lea     rdx, _GUID_ebe7ab25_f6a9_4472_9fa2_e979ef15ff58
0x180078783  mov     rcx, r15
0x180078786  mov     rax, rbx
0x180078789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007878e  nop
0x18007878f  mov     rcx, [rsp+128h]; this
0x180078797  test    eax, eax
0x180078799  js      loc_180078D2C
0x18007879f  test    r14d, r14d
0x1800787a2  jz      short loc_1800787C8
0x1800787a4  mov     rcx, [rsp+128h+var_C0]
0x1800787a9  mov     rax, [rcx]
0x1800787ac  mov     edx, r14d
0x1800787af  mov     rax, [rax+38h]
0x1800787b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800787b8  mov     rcx, [rsp+128h]; this
0x1800787c0  test    eax, eax
0x1800787c2  js      loc_180078D40
0x1800787c8  test    r12, r12
0x1800787cb  jz      short loc_1800787FB
0x1800787cd  mov     [rsp+128h+var_B8], dil
0x1800787d2  mov     rcx, [rsp+128h+var_C0]
0x1800787d7  mov     rax, [rcx]
0x1800787da  lea     r8, [rsp+128h+var_B8]
0x1800787df  mov     rdx, r12
0x1800787e2  mov     rax, [rax+70h]
0x1800787e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800787eb  mov     rcx, [rsp+128h]; this
0x1800787f3  test    eax, eax
0x1800787f5  js      loc_180078D54
0x1800787fb  mov     rcx, [rsp+128h+var_C0]
0x180078800  mov     rax, [rcx]
0x180078803  mov     rax, [rax+0A0h]
0x18007880a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007880f  mov     rcx, [rsp+128h]; this
0x180078817  test    eax, eax
0x180078819  js      loc_180078D68
0x18007881f  mov     qword ptr [rsp+128h+var_B0], rdi
0x180078824  lea     rdx, [rsp+128h+var_B0]
0x180078829  lea     rcx, [rsp+128h+var_98]
0x180078831  call    ??$As@UIUser@System@Windows@@@?$ComPtr@VUser@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::User>::As<Windows::System::IUser>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::IUser>>)
0x180078836  mov     rcx, [rsp+128h]; this
0x18007883e  test    eax, eax
0x180078840  js      loc_180078D7D
0x180078846  mov     rax, qword ptr [rsp+128h+var_B0]
0x18007884b  mov     [rsp+128h+var_90], rax
0x180078853  mov     eax, [rsp+128h+arg_8]
0x18007885a  mov     dword ptr [rsp+128h+var_78], eax
0x180078861  mov     dword ptr [rsp+128h+var_78+4], r13d
0x180078869  lea     r8, [rsp+128h+var_90]
0x180078871  lea     rdx, [rsp+128h+var_78]
0x180078879  lea     rcx, [rsp+128h+var_58]
0x180078881  call    ??$?0U?$pair@II@std@@PEAUIUser@System@Windows@@@?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@QEAA@$$QEAU?$pair@II@1@$$QEAPEAUIUser@System@Windows@@PEAPEAX@Z; std::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>(std::pair<uint,uint> &&,Windows::System::IUser * &&,void * *)
0x180078886  nop
0x180078887  lea     rcx, [rsi+1D0h]
0x18007888e  mov     r8, rax
0x180078891  lea     rdx, [rsp+128h+var_90]
0x180078899  call    ?insert@?$_Tree@V?$_Tmap_traits@U?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@U?$less@U?$pair@IK@std@@@2@V?$allocator@U?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@_N@2@$$QEAU?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@2@@Z; std::_Tree<std::_Tmap_traits<std::pair<uint,ulong>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<uint,ulong>>,std::allocator<std::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::insert(std::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>> &&)
0x18007889e  nop
0x18007889f  lea     rcx, [rsp+128h+var_50]
0x1800788a7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800788ac  nop
0x1800788ad  lea     rcx, [rsp+128h+var_B0]
0x1800788b2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800788b7  nop
0x1800788b8  lea     rcx, [rsp+128h+var_C0]
0x1800788bd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800788c2  nop
0x1800788c3  test    r15, r15
0x1800788c6  jz      short loc_1800788D8
0x1800788c8  mov     rax, [r15]
0x1800788cb  mov     rcx, r15
0x1800788ce  mov     rax, [rax+10h]
0x1800788d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800788d7  nop
0x1800788d8  lea     rcx, [rsp+128h+var_80]; this
0x1800788e0  call    ??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)
0x1800788e5  nop
0x1800788e6  mov     rcx, [rsp+128h+var_60]
0x1800788ee  test    rcx, rcx
0x1800788f1  jz      short loc_180078900
0x1800788f3  mov     rax, [rcx]
0x1800788f6  mov     rax, [rax+10h]
0x1800788fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800788ff  nop
0x180078900  lea     rcx, [rsp+128h+var_A8]
  ... truncated ...
```
