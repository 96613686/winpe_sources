# Windows::System::UserStatics::RemoveUserAndFireUserRemoved(uint,uint)

- ea: `0x18007d860`
- end: `0x18007e01e`
- name: `?RemoveUserAndFireUserRemoved@UserStatics@System@Windows@@UEAAJII@Z`
- size: `1982`
- prototype: `__int64 __fastcall(Windows::System::UserStatics *__hidden this, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `29`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006130`
- `0x180007920`
- `0x18000acdc`
- `0x18000ce48`
- `0x18000f5c0`
- `0x180012890`
- `0x1800179c0`
- `0x180025cd4`
- `0x18002618c`
- `0x180033850`
- `0x180037e98`
- `0x180037ee4`
- `0x18003991c`
- `0x18003d02c`
- `0x18003daf4`
- `0x18003f404`
- `0x18003f980`
- `0x18003fcac`
- `0x18004a338`
- `0x18006179c`
- `0x180062748`
- `0x1800691fc`
- `0x180074aa0`
- `0x18007d860`
- `0x1800804f8`
- `0x1800810c0`
- `0x180081254`
- `0x1800b763c`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007d8e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007db78`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007dbf1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007d8e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007db78`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007dbf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007df0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007df0b`

## string_xrefs

- `0x18007da28`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x18007df53`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x18007df67`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x18007df7b`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x18007df90`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x18007dfa4`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x18007dfb9`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x18007dfce`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x18007dfe2`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x18007dff7`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x18007e00b`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall Windows::System::UserStatics::RemoveUserAndFireUserRemoved(
        Windows::System::UserStatics *this,
        unsigned int a2,
        unsigned int a3)
{
  const struct _tlgProvider_t *v6; // rax
  int v7; // r9d
  int v8; // r8d
  __int64 v9; // rbx
  int v10; // eax
  int v11; // eax
  __int64 v12; // rbx
  int v13; // eax
  __int64 v14; // rbx
  struct IUnknown *v15; // rdi
  __int64 v16; // rbx
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // r8
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 (__fastcall ****v23)(); // r11
  int v24; // eax
  __int64 *v25; // r9
  __int64 v26; // rax
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rcx
  __int64 k; // rcx
  __int64 v31; // rax
  int v32; // eax
  const struct _tlgProvider_t *v33; // rax
  int v34; // r8d
  int v35; // r9d
  __int64 result; // rax
  __int64 v37; // rcx
  __int64 j; // rax
  struct IUnknown **v39; // r12
  int v40; // eax
  int v41; // eax
  __int64 v42; // rcx
  __int64 i; // rax
  const struct _tlgProvider_t *v44; // rax
  int v45; // ebx
  wil *v46; // rcx
  int v47; // r8d
  int v48; // r9d
  int v49; // [rsp+20h] [rbp-B8h]
  __int64 v50; // [rsp+40h] [rbp-98h] BYREF
  __int64 v51[2]; // [rsp+48h] [rbp-90h] BYREF
  __int64 v52; // [rsp+58h] [rbp-80h] BYREF
  struct IUnknown *v53; // [rsp+60h] [rbp-78h] BYREF
  __int64 (__fastcall **v54)(); // [rsp+68h] [rbp-70h] BYREF
  __int64 v55; // [rsp+70h] [rbp-68h]
  __int64 (__fastcall ***v56)(); // [rsp+80h] [rbp-58h]
  char *v57; // [rsp+88h] [rbp-50h] BYREF
  _QWORD v58[9]; // [rsp+90h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]
  __int64 (__fastcall ***v60)(); // [rsp+E0h] [rbp+8h] BYREF
  unsigned int v61; // [rsp+E8h] [rbp+10h] BYREF
  unsigned int v62; // [rsp+F0h] [rbp+18h] BYREF
  __int64 *v63; // [rsp+F8h] [rbp+20h] BYREF

  v62 = a3;
  v61 = a2;
  v6 = UserMgrUserModelTelemetry::Provider();
  v8 = *(_DWORD *)v6;
  if ( *(_DWORD *)v6 > 5u )
  {
    LODWORD(v60) = a3;
    LODWORD(v63) = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v6,
      (unsigned int)&byte_180123217,
      v8,
      v7,
      (__int64)&v63,
      (__int64)&v60);
  }
  v53 = 0;
  v58[0] = 0;
  v52 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v57 = (char *)this + 72;
  v63 = (__int64 *)__PAIR64__(a3, a2);
  std::_Tree<std::_Tmap_traits<std::pair<unsigned int,unsigned long>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<unsigned int,unsigned long>>,std::allocator<std::pair<std::pair<unsigned int,unsigned long> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::find(
    (char *)this + 112,
    v51,
    &v63);
  try
  {
    v9 = v51[0];
    if ( v51[0] == *((_QWORD *)this + 14) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4C4,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)0x80070490LL,
        v49);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::operator=(&v53, v51[0] + 40);
    v10 = Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
            (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))&v53,
            &v52);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4C9,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)(unsigned int)v10,
        v49);
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v52 + 56LL))(v52, 0);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4CA,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)(unsigned int)v11,
        v49);
    std::_Tree<std::_Tmap_traits<std::pair<unsigned int,unsigned long>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<unsigned int,unsigned long>>,std::allocator<std::pair<std::pair<unsigned int,unsigned long> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::erase(
      (char *)this + 112,
      &v63,
      v9);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
    {
      v63 = (__int64 *)__PAIR64__(a3, a2);
      std::_Tree<std::_Tmap_traits<std::pair<unsigned int,unsigned long>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<unsigned int,unsigned long>>,std::allocator<std::pair<std::pair<unsigned int,unsigned long> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::find(
        (char *)this + 408,
        v51,
        &v63);
      v12 = v51[0];
      if ( v51[0] != *((_QWORD *)this + 51) )
      {
        v63 = 0;
        if ( (int)Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
                    (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v51[0] + 40),
                    (__int64 *)&v63) >= 0 )
        {
          v13 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v63 + 56))(v63, 0);
          if ( v13 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x4D6,
              (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
              (const char *)(unsigned int)v13,
              v49);
        }
        std::_Tree<std::_Tmap_traits<std::pair<unsigned int,unsigned long>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<unsigned int,unsigned long>>,std::allocator<std::pair<std::pair<unsigned int,unsigned long> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::erase(
          (char *)this + 408,
          v51,
          v12);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v63);
      }
    }
    v14 = **((_QWORD **)this + 18);
    v15 = v53;
    while ( v14 != *((_QWORD *)this + 18) )
    {
      LODWORD(v63) = 0;
      v51[0] = 0;
      v39 = (struct IUnknown **)(v14 + 40);
      v40 = Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
              (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v14 + 40),
              v51);
      if ( v40 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4E0,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
          (const char *)(unsigned int)v40,
          v49);
      v41 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v51[0] + 48LL))(v51[0], &v63);
      if ( v41 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4E2,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
          (const char *)(unsigned int)v41,
          v49);
      if ( *v39 == v15
        || Windows::System::Internal::Implementation::ComUtils::IsEqualObject(*v39, v15)
        || (_DWORD)v63 == a2 )
      {
        WindowsDeleteString(*(HSTRING *)(v14 + 32));
        v14 = *(_QWORD *)std::_Tree<std::_Tmap_traits<HSTRING__ *,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<HSTRING__ *>,std::allocator<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::erase(
                           (char *)this + 144,
                           &v54,
                           v14);
      }
      else if ( !*(_BYTE *)(v14 + 25) )
      {
        v42 = *(_QWORD *)(v14 + 16);
        if ( *(_BYTE *)(v42 + 25) )
        {
          for ( i = *(_QWORD *)(v14 + 8); !*(_BYTE *)(i + 25) && v14 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
            v14 = i;
        }
        else
        {
          i = std::_Tree_val<std::_Tree_simple_types<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>>::_Min(v42);
        }
        v14 = i;
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v51);
    }
    v16 = **((_QWORD **)this + 20);
    while ( v16 != *((_QWORD *)this + 20) )
    {
      v63 = 0;
      if ( (int)Microsoft::WRL::WeakRef::As<Windows::System::IUser>((_QWORD *)(v16 + 40), &v63) >= 0 || v63 )
      {
        if ( !*(_BYTE *)(v16 + 25) )
        {
          v37 = *(_QWORD *)(v16 + 16);
          if ( *(_BYTE *)(v37 + 25) )
          {
            for ( j = *(_QWORD *)(v16 + 8); !*(_BYTE *)(j + 25) && v16 == *(_QWORD *)(j + 16); j = *(_QWORD *)(j + 8) )
              v16 = j;
          }
          else
          {
            j = std::_Tree_val<std::_Tree_simple_types<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>>::_Min(v37);
          }
          v16 = j;
        }
      }
      else
      {
        v16 = *(_QWORD *)std::_Tree<std::_Tmap_traits<unsigned __int64,Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInArbiter>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInArbiter>>>,0>>::erase(
                           (char *)this + 160,
                           v51,
                           v16);
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v63);
    }
    v50 = 0;
    LODWORD(v60) = 0;
    v17 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)()))(*(_QWORD *)v52 + 64LL))(v52, &v60);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x505,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)(unsigned int)v17,
        v49);
    v63 = &v50;
    v18 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v63);
    v19 = Microsoft::WRL::AsWeak<Windows::System::IUser>(v15, v18);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x506,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)(unsigned int)v19,
        v49);
    v20 = std::pair<unsigned int const,Microsoft::WRL::WeakRef>::pair<unsigned int const,Microsoft::WRL::WeakRef>(
            &v54,
            &v60,
            &v50);
    std::_Tree<std::_Tmap_traits<unsigned int,Microsoft::WRL::WeakRef,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,Microsoft::WRL::WeakRef>>,0>>::insert(
      (char *)this + 160,
      v51,
      v20);
    v21 = v55;
    if ( v55 )
    {
      v55 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 352);
    v22 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v57);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
    v63 = (__int64 *)((char *)this + 176);
    std::_Tree<std::_Tmap_traits<unsigned int,unsigned long,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,unsigned long>>,0>>::find(
      (char *)this + 216,
      &v60,
      &v62);
    if ( v60 != *v23 && *((_DWORD *)v60 + 8) == a2 )
    {
      v24 = (*(__int64 (__fastcall **)(Windows::System::UserStatics *, _QWORD))(*(_QWORD *)this + 88LL))(this, a3);
      if ( v24 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x515,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
          (const char *)(unsigned int)v24,
          v49);
    }
    Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v63);
    EnterCriticalSection((LPCRITICAL_SECTION)this + 6);
    v60 = (__int64 (__fastcall ***)())((char *)this + 240);
    v25 = (__int64 *)*((_QWORD *)this + 35);
    v26 = *v25;
    while ( (__int64 *)v26 != v25 )
    {
      if ( *(_DWORD *)(v26 + 64) == a2 )
      {
        std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::_Eqrange(
          (char *)this + 280,
          &v54);
        std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::erase(
          (char *)this + 280,
          &v63,
          v54,
          v55);
        std::_Tree<std::_Tmap_traits<unsigned int,std::pair<wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebAccountMonitor2,wil::err_exception_policy>,EventRegistrationToken>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::pair<wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebAccountMonitor2,wil::err_exception_policy>,EventRegistrationToken>>>,0>>::erase(
          (char *)this + 296,
          &v61);
        break;
      }
      if ( !*(_BYTE *)(v26 + 25) )
      {
        v29 = *(_QWORD *)(v26 + 16);
        if ( *(_BYTE *)(v29 + 25) )
        {
          for ( k = *(_QWORD *)(v26 + 8); !*(_BYTE *)(k + 25) && v26 == *(_QWORD *)(k + 16); k = *(_QWORD *)(k + 8) )
            v26 = k;
          v26 = k;
        }
        else
        {
          v26 = std::_Tree_val<std::_Tree_simple_types<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>>::_Min(v29);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v60);
    v27 = *((_QWORD *)this - 7);
    v60 = &v54;
    v54 = off_1800EEB48;
    v56 = &v54;
    v28 = (*(__int64 (__fastcall **)(char *, char *, struct IUnknown *, __int64 (__fastcall ***)()))(v27 + 64))(
            (char *)this - 56,
            (char *)this + 384,
            v15,
            &v54);
    if ( v28 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x52A,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)(unsigned int)v28,
        v49);
    v31 = *((_QWORD *)this - 7);
    v60 = &v54;
    v54 = off_1800EEB80;
    v56 = &v54;
    v32 = (*(__int64 (__fastcall **)(char *, char *, struct IUnknown *, __int64 (__fastcall ***)()))(v31 + 64))(
            (char *)this - 56,
            (char *)this + 360,
            v15,
            &v54);
    if ( v32 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x52E,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)(unsigned int)v32,
        v49);
    v33 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v33 > 5u )
    {
      LODWORD(v60) = 0;
      LODWORD(v63) = a3;
      LODWORD(v50) = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v33,
        (unsigned int)byte_1801231C3,
        v34,
        v35,
        (__int64)&v50,
        (__int64)&v63,
        (__int64)&v60);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v52);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v58);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v53);
    result = 0;
  }
  catch ( ... )
  {
    v44 = UserMgrUserModelTelemetry::Provider();
    v45 = (int)v44;
    v46 = (wil *)*(unsigned int *)v44;
    if ( (unsigned int)v46 > 5 )
    {
      LODWORD(v60) = wil::ResultFromCaughtException(v46);
      LODWORD(v63) = v62;
      LODWORD(v50) = v61;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v45,
        (unsigned int)&dword_18012315C,
        v47,
        v48,
        (__int64)&v50,
        (__int64)&v63,
        (__int64)&v60);
    }
    LODWORD(v60) = wil::ResultFromCaughtException(v46);
    return (unsigned int)v60;
  }
  return result;
}

```

## disassembly

```asm
0x18007d860  mov     [rsp+arg_10], r8d
0x18007d865  mov     [rsp+arg_8], edx
0x18007d869  push    rbx
0x18007d86a  push    rsi
0x18007d86b  push    rdi
0x18007d86c  push    r12
0x18007d86e  push    r13
0x18007d870  push    r14
0x18007d872  push    r15
0x18007d874  sub     rsp, 0A0h
0x18007d87b  mov     r13d, r8d
0x18007d87e  mov     r15d, edx
0x18007d881  mov     rsi, rcx
0x18007d884  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x18007d889  mov     r8d, [rax]
0x18007d88c  cmp     r8d, 5
0x18007d890  jbe     short loc_18007D8CB
0x18007d892  mov     dword ptr [rsp+0D8h+arg_0], r13d
0x18007d89a  mov     dword ptr [rsp+0D8h+arg_18], r15d
0x18007d8a2  lea     rcx, [rsp+0D8h+arg_0]
0x18007d8aa  mov     [rsp+0D8h+var_B0], rcx
0x18007d8af  lea     rcx, [rsp+0D8h+arg_18]
0x18007d8b7  mov     qword ptr [rsp+0D8h+var_B8], rcx; int
0x18007d8bc  lea     rdx, byte_180123217
0x18007d8c3  mov     rcx, rax
0x18007d8c6  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18007d8cb  xor     r12d, r12d
0x18007d8ce  mov     [rsp+0D8h+var_78], r12
0x18007d8d3  mov     [rsp+0D8h+var_48], r12
0x18007d8db  mov     [rsp+0D8h+var_80], r12
0x18007d8e0  lea     rbx, [rsi+48h]
0x18007d8e4  mov     rcx, rbx; lpCriticalSection
0x18007d8e7  call    cs:__imp_EnterCriticalSection
0x18007d8ed  mov     [rsp+0D8h+var_50], rbx
0x18007d8f5  lea     rdi, [rsi+70h]
0x18007d8f9  mov     dword ptr [rsp+0D8h+arg_18], r15d
0x18007d901  mov     dword ptr [rsp+0D8h+arg_18+4], r13d
0x18007d909  lea     r8, [rsp+0D8h+arg_18]
0x18007d911  lea     rdx, [rsp+0D8h+var_90]
0x18007d916  mov     rcx, rdi
0x18007d919  call    ?find@?$_Tree@V?$_Tmap_traits@U?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@U?$less@U?$pair@IK@std@@@2@V?$allocator@U?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@std@@@std@@@2@AEBU?$pair@IK@2@@Z; std::_Tree<std::_Tmap_traits<std::pair<uint,ulong>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<uint,ulong>>,std::allocator<std::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::find(std::pair<uint,ulong> const &)
0x18007d91e  mov     rbx, [rsp+0D8h+var_90]
0x18007d923  cmp     rbx, [rdi]
0x18007d926  setz    al
0x18007d929  mov     rcx, [rsp+0D8h]; this
0x18007d931  test    al, al
0x18007d933  jnz     loc_18007DF4D
0x18007d939  lea     rdx, [rbx+28h]
0x18007d93d  lea     rcx, [rsp+0D8h+var_78]
0x18007d942  call    ??4?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::System::IUser>::operator=(Microsoft::WRL::ComPtr<Windows::System::IUser> const &)
0x18007d947  lea     rdx, [rsp+0D8h+var_80]
0x18007d94c  lea     rcx, [rsp+0D8h+var_78]
0x18007d951  call    ??$As@UIUserInternal@Implementation@Internal@System@Windows@@@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserInternal>>)
0x18007d956  mov     rcx, [rsp+0D8h]; this
0x18007d95e  test    eax, eax
0x18007d960  js      loc_18007DF64
0x18007d966  mov     rcx, [rsp+0D8h+var_80]
0x18007d96b  mov     rax, [rcx]
0x18007d96e  xor     edx, edx
0x18007d970  mov     rax, [rax+38h]
0x18007d974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d979  mov     rcx, [rsp+0D8h]; this
0x18007d981  test    eax, eax
0x18007d983  js      loc_18007DF78
0x18007d989  mov     r8, rbx
0x18007d98c  lea     rdx, [rsp+0D8h+arg_18]
0x18007d994  mov     rcx, rdi
0x18007d997  call    ?erase@?$_Tree@V?$_Tmap_traits@U?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@U?$less@U?$pair@IK@std@@@2@V?$allocator@U?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<std::pair<uint,ulong>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<uint,ulong>>,std::allocator<std::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>>>)
0x18007d99c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x18007d9a3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x18007d9a8  test    al, al
0x18007d9aa  jz      loc_18007DA57
0x18007d9b0  lea     rdi, [rsi+198h]
0x18007d9b7  mov     dword ptr [rsp+0D8h+arg_18], r15d
0x18007d9bf  mov     dword ptr [rsp+0D8h+arg_18+4], r13d
0x18007d9c7  lea     r8, [rsp+0D8h+arg_18]
0x18007d9cf  lea     rdx, [rsp+0D8h+var_90]
0x18007d9d4  mov     rcx, rdi
0x18007d9d7  call    ?find@?$_Tree@V?$_Tmap_traits@U?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@U?$less@U?$pair@IK@std@@@2@V?$allocator@U?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@std@@@std@@@2@AEBU?$pair@IK@2@@Z; std::_Tree<std::_Tmap_traits<std::pair<uint,ulong>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<uint,ulong>>,std::allocator<std::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::find(std::pair<uint,ulong> const &)
0x18007d9dc  mov     rbx, [rsp+0D8h+var_90]
0x18007d9e1  cmp     rbx, [rdi]
0x18007d9e4  jz      short loc_18007DA57
0x18007d9e6  mov     [rsp+0D8h+arg_18], r12
0x18007d9ee  lea     rcx, [rbx+28h]
0x18007d9f2  lea     rdx, [rsp+0D8h+arg_18]
0x18007d9fa  call    ??$As@UIUserInternal@Implementation@Internal@System@Windows@@@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserInternal>>)
0x18007d9ff  test    eax, eax
0x18007da01  js      short loc_18007DA39
0x18007da03  mov     rcx, [rsp+0D8h+arg_18]
0x18007da0b  mov     rax, [rcx]
0x18007da0e  xor     edx, edx
0x18007da10  mov     rax, [rax+38h]
0x18007da14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007da19  mov     rcx, [rsp+0D8h]; this
0x18007da21  test    eax, eax
0x18007da23  jns     short loc_18007DA39
0x18007da25  mov     r9d, eax; char *
0x18007da28  lea     r8, aOnecoreDsSecur_68; "onecore\\ds\\security\\umstartup\\userm"...
0x18007da2f  mov     edx, 4D6h; void *
0x18007da34  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007da39  mov     r8, rbx
0x18007da3c  lea     rdx, [rsp+0D8h+var_90]
0x18007da41  mov     rcx, rdi
0x18007da44  call    ?erase@?$_Tree@V?$_Tmap_traits@U?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@U?$less@U?$pair@IK@std@@@2@V?$allocator@U?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<std::pair<uint,ulong>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<uint,ulong>>,std::allocator<std::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>>>)
0x18007da49  nop
0x18007da4a  lea     rcx, [rsp+0D8h+arg_18]
0x18007da52  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18007da57  lea     r14, [rsi+90h]
0x18007da5e  mov     rbx, [r14]
0x18007da61  mov     rbx, [rbx]
0x18007da64  mov     rdi, [rsp+0D8h+var_78]
0x18007da69  cmp     rbx, [r14]
0x18007da6c  jnz     loc_18007DE55
0x18007da72  lea     r14, [rsi+0A0h]
0x18007da79  mov     rbx, [r14]
0x18007da7c  mov     rbx, [rbx]
0x18007da7f  cmp     rbx, [r14]
0x18007da82  jnz     loc_18007DDD4
0x18007da88  mov     [rsp+0D8h+var_98], r12
0x18007da8d  mov     dword ptr [rsp+0D8h+arg_0], r12d
0x18007da95  mov     rcx, [rsp+0D8h+var_80]
0x18007da9a  mov     rax, [rcx]
0x18007da9d  lea     rdx, [rsp+0D8h+arg_0]
0x18007daa5  mov     rax, [rax+40h]
0x18007daa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007daae  mov     rcx, [rsp+0D8h]; this
0x18007dab6  test    eax, eax
0x18007dab8  js      loc_18007DF8D
0x18007dabe  lea     rax, [rsp+0D8h+var_98]
0x18007dac3  mov     [rsp+0D8h+arg_18], rax
0x18007dacb  lea     rcx, [rsp+0D8h+arg_18]
0x18007dad3  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18007dad8  mov     rdx, rax
0x18007dadb  mov     rcx, rdi
0x18007dade  call    ??$AsWeak@UIUser@System@Windows@@@WRL@Microsoft@@YAJPEAUIUser@System@Windows@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<Windows::System::IUser>(Windows::System::IUser *,Microsoft::WRL::WeakRef *)
0x18007dae3  mov     rcx, [rsp+0D8h]; this
0x18007daeb  test    eax, eax
0x18007daed  js      loc_18007DFA1
0x18007daf3  lea     r8, [rsp+0D8h+var_98]
0x18007daf8  lea     rdx, [rsp+0D8h+arg_0]
0x18007db00  lea     rcx, [rsp+0D8h+var_70]
0x18007db05  call    ??$?0AEAIAEAVWeakRef@WRL@Microsoft@@@?$pair@$$CBIVWeakRef@WRL@Microsoft@@@std@@QEAA@AEAIAEAVWeakRef@WRL@Microsoft@@PEAPEAX@Z; std::pair<uint const,Microsoft::WRL::WeakRef>::pair<uint const,Microsoft::WRL::WeakRef>(uint &,Microsoft::WRL::WeakRef &,void * *)
0x18007db0a  nop
0x18007db0b  mov     r8, rax
0x18007db0e  lea     rdx, [rsp+0D8h+var_90]
0x18007db13  mov     rcx, r14
0x18007db16  call    ?insert@?$_Tree@V?$_Tmap_traits@IVWeakRef@WRL@Microsoft@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIVWeakRef@WRL@Microsoft@@@std@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIVWeakRef@WRL@Microsoft@@@std@@@std@@@std@@@std@@_N@2@$$QEAU?$pair@$$CBIVWeakRef@WRL@Microsoft@@@2@@Z; std::_Tree<std::_Tmap_traits<uint,Microsoft::WRL::WeakRef,std::less<uint>,std::allocator<std::pair<uint const,Microsoft::WRL::WeakRef>>,0>>::insert(std::pair<uint const,Microsoft::WRL::WeakRef> &&)
0x18007db1b  nop
0x18007db1c  mov     rcx, [rsp+0D8h+var_68]
0x18007db21  test    rcx, rcx
0x18007db24  jz      short loc_18007DB38
0x18007db26  mov     [rsp+0D8h+var_68], r12
0x18007db2b  mov     rax, [rcx]
0x18007db2e  mov     rax, [rax+10h]
0x18007db32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007db37  nop
0x18007db38  lea     rcx, [rsi+160h]
0x18007db3f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007db44  nop
0x18007db45  mov     rcx, [rsp+0D8h+var_98]
0x18007db4a  test    rcx, rcx
0x18007db4d  jz      short loc_18007DB61
0x18007db4f  mov     [rsp+0D8h+var_98], r12
0x18007db54  mov     rax, [rcx]
0x18007db57  mov     rax, [rax+10h]
0x18007db5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007db60  nop
0x18007db61  lea     rcx, [rsp+0D8h+var_50]; this
0x18007db69  call    ??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)
0x18007db6e  lea     rbx, [rsi+0B0h]
0x18007db75  mov     rcx, rbx; lpCriticalSection
0x18007db78  call    cs:__imp_EnterCriticalSection
0x18007db7e  mov     [rsp+0D8h+arg_18], rbx
0x18007db86  lea     r11, [rsi+0D8h]
0x18007db8d  lea     r8, [rsp+0D8h+arg_10]
0x18007db95  lea     rdx, [rsp+0D8h+arg_0]
0x18007db9d  mov     rcx, r11
0x18007dba0  call    ?find@?$_Tree@V?$_Tmap_traits@IKU?$less@I@std@@V?$allocator@U?$pair@$$CBIK@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIK@std@@@std@@@std@@@2@AEBI@Z; std::_Tree<std::_Tmap_traits<uint,ulong,std::less<uint>,std::allocator<std::pair<uint const,ulong>>,0>>::find(uint const &)
0x18007dba5  mov     rdx, [rsp+0D8h+arg_0]
0x18007dbad  cmp     rdx, [r11]
0x18007dbb0  jz      short loc_18007DBDA
0x18007dbb2  cmp     [rdx+20h], r15d
0x18007dbb6  jnz     short loc_18007DBDA
0x18007dbb8  mov     rax, [rsi]
0x18007dbbb  mov     edx, r13d
0x18007dbbe  mov     rcx, rsi
0x18007dbc1  mov     rax, [rax+58h]
0x18007dbc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dbca  mov     rcx, [rsp+0D8h]; this
0x18007dbd2  test    eax, eax
0x18007dbd4  js      loc_18007DFB6
0x18007dbda  lea     rcx, [rsp+0D8h+arg_18]; this
0x18007dbe2  call    ??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)
0x18007dbe7  lea     rbx, [rsi+0F0h]
0x18007dbee  mov     rcx, rbx; lpCriticalSection
0x18007dbf1  call    cs:__imp_EnterCriticalSection
0x18007dbf7  mov     [rsp+0D8h+arg_0], rbx
0x18007dbff  lea     rbx, [rsi+118h]
0x18007dc06  mov     r9, [rbx]
0x18007dc09  mov     rax, [r9]
0x18007dc0c  cmp     rax, r9
0x18007dc0f  jz      short loc_18007DC5B
0x18007dc11  lea     r8, [rax+20h]
0x18007dc15  cmp     [r8+20h], r15d
0x18007dc19  jnz     loc_18007DCC2
0x18007dc1f  lea     rdx, [rsp+0D8h+var_70]
0x18007dc24  mov     rcx, rbx
0x18007dc27  call    ?_Eqrange@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@std@@@std@@@std@@@std@@V12@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,uint>>,0>>::_Eqrange(std::wstring const &)
0x18007dc2c  mov     r9, [rsp+0D8h+var_68]
0x18007dc31  mov     r8, [rsp+0D8h+var_70]
0x18007dc36  lea     rdx, [rsp+0D8h+arg_18]
0x18007dc3e  mov     rcx, rbx
0x18007dc41  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@std@@@std@@@std@@@2@0@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,uint>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,uint>>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,uint>>>>)
0x18007dc46  lea     rcx, [rsi+128h]
0x18007dc4d  lea     rdx, [rsp+0D8h+arg_8]
0x18007dc55  call    ?erase@?$_Tree@V?$_Tmap_traits@IU?$pair@V?$com_ptr_t@UIWebAccountMonitor2@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@UEventRegistrationToken@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIU?$pair@V?$com_ptr_t@UIWebAccountMonitor2@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@UEventRegistrationToken@@@std@@@std@@@2@$0A@@std@@@std@@QEAA_KAEBI@Z; std::_Tree<std::_Tmap_traits<uint,std::pair<wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebAccountMonitor2,wil::err_exception_policy>,EventRegistrationToken>,std::less<uint>,std::allocator<std::pair<uint const,std::pair<wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebAccountMonitor2,wil::err_exception_policy>,EventRegistrationToken>>>,0>>::erase(uint const &)
0x18007dc5a  nop
0x18007dc5b  lea     rcx, [rsp+0D8h+arg_0]
0x18007dc63  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18007dc68  lea     rbx, [rsi-38h]
0x18007dc6c  mov     rax, [rbx]
0x18007dc6f  lea     rcx, [rsp+0D8h+var_70]
0x18007dc74  mov     [rsp+0D8h+arg_0], rcx
0x18007dc7c  lea     rcx, off_1800EEB48
0x18007dc83  mov     [rsp+0D8h+var_70], rcx
0x18007dc88  lea     rcx, [rsp+0D8h+var_70]
0x18007dc8d  mov     [rsp+0D8h+var_58], rcx
0x18007dc95  lea     rdx, [rsi+180h]
0x18007dc9c  lea     r9, [rsp+0D8h+var_70]
0x18007dca1  mov     r8, rdi
0x18007dca4  mov     rcx, rbx
0x18007dca7  mov     rax, [rax+40h]
0x18007dcab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dcb0  mov     rcx, [rsp+0D8h]; this
0x18007dcb8  test    eax, eax
0x18007dcba  js      loc_18007DFCB
0x18007dcc0  jmp     short loc_18007DD01
0x18007dcc2  cmp     [rax+19h], r12b
0x18007dcc6  jnz     loc_18007DC0C
0x18007dccc  mov     rcx, [rax+10h]
0x18007dcd0  cmp     [rcx+19h], r12b
0x18007dcd4  jnz     short loc_18007DCE0
0x18007dcd6  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUHSTRING__@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@QEAUHSTRING__@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>>::_Min(std::_Tree_node<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>,void *> *)
0x18007dcdb  jmp     loc_18007DC0C
0x18007dce0  mov     rcx, [rax+8]
0x18007dce4  jmp     short loc_18007DCF3
0x18007dce6  cmp     rax, [rcx+10h]
0x18007dcea  jnz     short loc_18007DCF9
0x18007dcec  mov     rax, rcx
0x18007dcef  mov     rcx, [rcx+8]
0x18007dcf3  cmp     [rcx+19h], r12b
0x18007dcf7  jz      short loc_18007DCE6
0x18007dcf9  mov     rax, rcx
0x18007dcfc  jmp     loc_18007DC0C
0x18007dd01  mov     rax, [rbx]
0x18007dd04  lea     rcx, [rsp+0D8h+var_70]
0x18007dd09  mov     [rsp+0D8h+arg_0], rcx
0x18007dd11  lea     rcx, off_1800EEB80
0x18007dd18  mov     [rsp+0D8h+var_70], rcx
0x18007dd1d  lea     rcx, [rsp+0D8h+var_70]
0x18007dd22  mov     [rsp+0D8h+var_58], rcx
0x18007dd2a  lea     rdx, [rsi+168h]
0x18007dd31  lea     r9, [rsp+0D8h+var_70]
0x18007dd36  mov     r8, rdi
0x18007dd39  mov     rcx, rbx
0x18007dd3c  mov     rax, [rax+40h]
0x18007dd40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dd45  mov     rcx, [rsp+0D8h]; this
0x18007dd4d  test    eax, eax
0x18007dd4f  js      loc_18007DFDF
0x18007dd55  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x18007dd5a  mov     ecx, [rax]
0x18007dd5c  cmp     ecx, 5
0x18007dd5f  jbe     short loc_18007DDAA
0x18007dd61  mov     dword ptr [rsp+0D8h+arg_0], r12d
0x18007dd69  mov     dword ptr [rsp+0D8h+arg_18], r13d
0x18007dd71  mov     dword ptr [rsp+0D8h+var_98], r15d
0x18007dd76  lea     rcx, [rsp+0D8h+arg_0]
0x18007dd7e  mov     [rsp+0D8h+var_A8], rcx
0x18007dd83  lea     rcx, [rsp+0D8h+arg_18]
0x18007dd8b  mov     [rsp+0D8h+var_B0], rcx
0x18007dd90  lea     rcx, [rsp+0D8h+var_98]
0x18007dd95  mov     qword ptr [rsp+0D8h+var_B8], rcx
0x18007dd9a  lea     rdx, byte_1801231C3
0x18007dda1  mov     rcx, rax
0x18007dda4  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18007dda9  nop
0x18007ddaa  lea     rcx, [rsp+0D8h+var_80]
0x18007ddaf  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18007ddb4  nop
0x18007ddb5  lea     rcx, [rsp+0D8h+var_48]
0x18007ddbd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18007ddc2  nop
0x18007ddc3  lea     rcx, [rsp+0D8h+var_78]
0x18007ddc8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18007ddcd  xor     eax, eax
0x18007ddcf  jmp     loc_18007DF3A
0x18007ddd4  mov     [rsp+0D8h+arg_18], r12
0x18007dddc  lea     rcx, [rbx+28h]
0x18007dde0  lea     rdx, [rsp+0D8h+arg_18]
  ... truncated ...
```
