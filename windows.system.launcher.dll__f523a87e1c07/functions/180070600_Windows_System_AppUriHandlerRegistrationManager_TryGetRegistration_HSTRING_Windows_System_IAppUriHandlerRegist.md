# Windows::System::AppUriHandlerRegistrationManager::TryGetRegistration(HSTRING__ *,Windows::System::IAppUriHandlerRegistration * *)

- ea: `0x180070600`
- end: `0x180070c6e`
- name: `?TryGetRegistration@AppUriHandlerRegistrationManager@System@Windows@@UEAAJPEAUHSTRING__@@PEAPEAUIAppUriHandlerRegistration@23@@Z`
- size: `1646`
- prototype: `__int64 __fastcall(Windows::System::AppUriHandlerRegistrationManager *this, HSTRING, struct Windows::System::IAppUriHandlerRegistration **)`
- caller_count: `0`
- callee_count: `32`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800047dc`
- `0x1800049bc`
- `0x18000f194`
- `0x180010c04`
- `0x1800170f0`
- `0x18001a528`
- `0x180020fe0`
- `0x180021114`
- `0x180032bf0`
- `0x180034d10`
- `0x18003c4f8`
- `0x18003d318`
- `0x18003e040`
- `0x18004a844`
- `0x18004acdc`
- `0x18006323c`
- `0x180064f44`
- `0x180070600`
- `0x180070c80`
- `0x180070cd0`
- `0x180070d74`
- `0x180070da0`
- `0x180070e58`
- `0x180076930`
- `0x18007bbe8`
- `0x18007fab4`
- `0x180087298`
- `0x18008a030`
- `0x1800c11b8`
- `0x1800c122c`
- `0x1800c4548`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180070715`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180070715`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180070811`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180070811`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180070906`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180070906`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180070b72`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180070b72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007068c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800707f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180070827`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007068c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800707f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180070827`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070725`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070bdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070725`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070bdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180070739`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180070739`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070bf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070bf0`

## string_xrefs

- `0x18007092a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`
- `0x1800706f2`: `onecoreuap\shell\windows.system.launcher\lib\windows.system.appurihandlerregistration.cpp`
- `0x18007074e`: `onecoreuap\shell\windows.system.launcher\lib\windows.system.appurihandlerregistration.cpp`
- `0x1800707d4`: `onecoreuap\shell\windows.system.launcher\lib\windows.system.appurihandlerregistration.cpp`
- `0x18007088e`: `onecoreuap\shell\windows.system.launcher\lib\windows.system.appurihandlerregistration.cpp`
- `0x1800708c9`: `onecoreuap\shell\windows.system.launcher\lib\windows.system.appurihandlerregistration.cpp`
- `0x18007094f`: `onecoreuap\shell\windows.system.launcher\lib\windows.system.appurihandlerregistration.cpp`
- `0x1800709e2`: `onecoreuap\shell\windows.system.launcher\lib\windows.system.appurihandlerregistration.cpp`
- `0x180070a65`: `onecoreuap\shell\windows.system.launcher\lib\windows.system.appurihandlerregistration.cpp`
- `0x180070a91`: `onecoreuap\shell\windows.system.launcher\lib\windows.system.appurihandlerregistration.cpp`
- `0x180070b27`: `onecoreuap\shell\windows.system.launcher\lib\windows.system.appurihandlerregistration.cpp`
- `0x180070643`: `AppUriHandlerRegistrationManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall Windows::System::AppUriHandlerRegistrationManager::TryGetRegistration(
        Windows::System::AppUriHandlerRegistrationManager *this,
        HSTRING a2,
        struct Windows::System::IAppUriHandlerRegistration **a3)
{
  struct Windows::System::IAppUriHandlerRegistration **v3; // r13
  struct Windows::System::IAppUriHandlerRegistration *v6; // rdi
  unsigned __int16 **v7; // rdx
  int CallingProcessPackageFamilyName; // eax
  HRESULT v9; // eax
  WCHAR *v10; // rbx
  __int64 v11; // r14
  __int64 (__fastcall *v12)(__int64, __int64, HSTRING, HSTRING); // rsi
  int v13; // eax
  const WCHAR *v14; // rax
  int v15; // eax
  int v16; // edi
  struct Windows::System::IAppUriHandlerRegistration **v17; // rax
  const char *v18; // r9
  int bIgnoreCase; // [rsp+20h] [rbp-308h]
  int bIgnoreCasea; // [rsp+20h] [rbp-308h]
  int v22; // [rsp+30h] [rbp-2F8h] BYREF
  PCWSTR StringRawBuffer; // [rsp+38h] [rbp-2F0h] BYREF
  HSTRING string; // [rsp+40h] [rbp-2E8h] BYREF
  __int64 v25; // [rsp+48h] [rbp-2E0h] BYREF
  int v26[2]; // [rsp+50h] [rbp-2D8h] BYREF
  LPCWCH lpString2; // [rsp+58h] [rbp-2D0h] BYREF
  PCWSTR v28; // [rsp+60h] [rbp-2C8h] BYREF
  HSTRING v29; // [rsp+68h] [rbp-2C0h] BYREF
  __int64 v30; // [rsp+70h] [rbp-2B8h] BYREF
  __int64 v31; // [rsp+78h] [rbp-2B0h] BYREF
  struct Windows::System::IAppUriHandlerRegistration *v32; // [rsp+80h] [rbp-2A8h]
  _QWORD v33[3]; // [rsp+88h] [rbp-2A0h] BYREF
  HSTRING v34; // [rsp+A0h] [rbp-288h] BYREF
  struct Windows::System::IAppUriHandlerRegistration **v35; // [rsp+A8h] [rbp-280h]
  __int64 *v36; // [rsp+B0h] [rbp-278h] BYREF
  __int64 v37; // [rsp+B8h] [rbp-270h] BYREF
  char v38; // [rsp+C0h] [rbp-268h]
  __int128 v39; // [rsp+D0h] [rbp-258h] BYREF
  __int64 v40; // [rsp+E0h] [rbp-248h]
  __int64 v41; // [rsp+E8h] [rbp-240h]
  __int128 v42; // [rsp+F0h] [rbp-238h]
  __int128 v43; // [rsp+100h] [rbp-228h]
  __int64 v44; // [rsp+110h] [rbp-218h]
  int v45; // [rsp+118h] [rbp-210h]
  _QWORD v46[42]; // [rsp+190h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+0h]

  v3 = a3;
  v34 = a2;
  v35 = a3;
  *a3 = 0;
  wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v46,
    "AppUriHandlerRegistrationManager");
  v46[0] = &LauncherClientProvider::AppUriHandlerRegistrationManager::`vftable';
  LauncherClientProvider::AppUriHandlerRegistrationManager::StartActivity((LauncherClientProvider::AppUriHandlerRegistrationManager *)v46);
  v6 = 0;
  v32 = 0;
  if ( a2 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    LauncherClientProvider::AppUriHandlerRegistrationManager::CreateRegistration<unsigned short const *>(
      v46,
      &StringRawBuffer);
    try
    {
      wil::GetActivationFactory<Windows::Internal::StateRepository::IAppUriHandlerGroupStatics>(&v31);
      GetStateRepoUserFromSystemUser(&v30, *((_QWORD *)this + 5));
      *(_QWORD *)v26 = 0;
      lpString2 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &lpString2,
        0);
      CallingProcessPackageFamilyName = UserAwareCallerIdentity::GetCallingProcessPackageFamilyName(
                                          (UserAwareCallerIdentity *)&lpString2,
                                          v7);
      if ( CallingProcessPackageFamilyName < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x170,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.appurihandlerregistration.cpp",
          (const char *)(unsigned int)CallingProcessPackageFamilyName,
          bIgnoreCase);
      string = 0;
      if ( *((_QWORD *)this + 6) )
      {
        AcquireSRWLockShared((PSRWLOCK)this + 7);
        StringRawBuffer = (PCWSTR)((char *)this + 56);
        WindowsDeleteString(string);
        string = 0;
        v9 = WindowsDuplicateString(*((HSTRING *)this + 6), &string);
        if ( v9 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x176,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.appurihandlerregistration.cpp",
            (const char *)(unsigned int)v9,
            bIgnoreCase);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&StringRawBuffer);
        v10 = (WCHAR *)lpString2;
      }
      else
      {
        v10 = (WCHAR *)lpString2;
        StringRawBuffer = lpString2;
        Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&string, &StringRawBuffer);
      }
      v11 = v31;
      v12 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING, HSTRING))(*(_QWORD *)v31 + 120LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v26);
      v13 = v12(v11, v30, string, a2);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x17E,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.appurihandlerregistration.cpp",
          (const char *)(unsigned int)v13,
          (int)v26);
      if ( *(_QWORD *)v26 )
      {
        v14 = WindowsGetStringRawBuffer(string, 0);
        if ( CompareStringOrdinal(v14, -1, v10, -1, 1) != 2 )
        {
          v28 = WindowsGetStringRawBuffer(string, 0);
          v29 = (HSTRING)v10;
          LauncherClientProvider::AppUriHandlerRegistrationManager::CreateRegistrationForPackage<unsigned short *,unsigned short const *>(
            v46,
            &v29,
            &v28);
          std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<std::vector<std::wstring> const,std::vector<std::wstring> const>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<std::vector<std::wstring> const,std::vector<std::wstring> const>>>>>>>(v33);
          GetHostIds(v33);
          if ( v33[0] == v33[1] )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x18A,
              (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.appurihandlerregistration.cpp",
              (const char *)0x80070005LL,
              bIgnoreCasea);
          StringRawBuffer = 0;
          v15 = (*(__int64 (__fastcall **)(_QWORD, PCWSTR *))(**(_QWORD **)v26 + 72LL))(
                  *(_QWORD *)v26,
                  &StringRawBuffer);
          if ( v15 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x18D,
              (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.appurihandlerregistration.cpp",
              (const char *)(unsigned int)v15,
              bIgnoreCasea);
          v25 = 0;
          v36 = &v25;
          v37 = 0;
          v38 = 1;
          v16 = SRCacheManager_Open(0, &v37);
          wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v36);
          if ( v16 >= 0 )
            v16 = 0;
          else
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA5,
              (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
              (const char *)(unsigned int)v16,
              bIgnoreCasea);
          if ( v16 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x190,
              (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.appurihandlerregistration.cpp",
              (const char *)(unsigned int)v16,
              bIgnoreCasea);
          v39 = 0;
          v40 = 0;
          v41 = 0;
          v42 = 0;
          v43 = 0;
          v44 = 0;
          v45 = 0;
          LOBYTE(v22) = 0;
          StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Get(&v25, StringRawBuffer, 16, &v39);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x196,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.appurihandlerregistration.cpp",
            (const char *)0x80070057LL,
            (int)&v22);
        }
        v29 = string;
        v28 = (PCWSTR)*((_QWORD *)this + 5);
        v17 = (struct Windows::System::IAppUriHandlerRegistration **)Microsoft::WRL::Details::Make<Windows::System::AppUriHandlerRegistration,HSTRING__ * &,Windows::System::IUser *,HSTRING__ *>(
                                                                       &StringRawBuffer,
                                                                       &v34,
                                                                       &v28,
                                                                       &v29);
        v6 = *v17;
        *v17 = 0;
        v32 = v6;
        if ( StringRawBuffer )
        {
          StringRawBuffer = 0;
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::IAppUriHandlerRegistration,Windows::System::IAppUriHandlerRegistration2>::Release();
        }
      }
      WindowsDeleteString(string);
      string = 0;
      if ( v10 )
        CoTaskMemFree(v10);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v26);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v31);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x1AC,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.appurihandlerregistration.cpp",
        v18);
      v6 = v32;
      v3 = v35;
    }
  }
  *v3 = v6;
  wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v46);
  LauncherClientProvider::AppUriHandlerRegistrationManager::~AppUriHandlerRegistrationManager((LauncherClientProvider::AppUriHandlerRegistrationManager *)v46);
  return 0;
}

```

## disassembly

```asm
0x180070600  push    rbx
0x180070602  push    rsi
0x180070603  push    rdi
0x180070604  push    r12
0x180070606  push    r13
0x180070608  push    r14
0x18007060a  push    r15
0x18007060c  sub     rsp, 2F0h
0x180070613  mov     rax, cs:__security_cookie
0x18007061a  xor     rax, rsp
0x18007061d  mov     [rsp+328h+var_48], rax
0x180070625  mov     r13, r8
0x180070628  mov     r12, rdx
0x18007062b  mov     r15, rcx
0x18007062e  mov     [rsp+328h+var_288], rdx
0x180070636  mov     [rsp+328h+var_280], r8
0x18007063e  xor     esi, esi
0x180070640  mov     [r8], rsi
0x180070643  lea     rdx, aAppurihandlerr; "AppUriHandlerRegistrationManager"
0x18007064a  lea     rcx, [rsp+328h+var_198]
0x180070652  call    ??0?$ActivityBase@VLauncherClientProvider@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180070657  lea     rax, ??_7AppUriHandlerRegistrationManager@LauncherClientProvider@@6B@; const LauncherClientProvider::AppUriHandlerRegistrationManager::`vftable'
0x18007065e  mov     [rsp+328h+var_198], rax
0x180070666  lea     rcx, [rsp+328h+var_198]; this
0x18007066e  call    ?StartActivity@AppUriHandlerRegistrationManager@LauncherClientProvider@@QEAAXXZ; LauncherClientProvider::AppUriHandlerRegistrationManager::StartActivity(void)
0x180070673  nop
0x180070674  mov     edi, esi
0x180070676  mov     [rsp+328h+var_2A8], rsi
0x18007067e  test    r12, r12
0x180070681  jz      loc_180070C2A
0x180070687  xor     edx, edx; length
0x180070689  mov     rcx, r12; string
0x18007068c  call    cs:__imp_WindowsGetStringRawBuffer
0x180070692  mov     [rsp+328h+var_2F0], rax
0x180070697  lea     rdx, [rsp+328h+var_2F0]
0x18007069c  lea     rcx, [rsp+328h+var_198]
0x1800706a4  call    ??$CreateRegistration@PEBG@AppUriHandlerRegistrationManager@LauncherClientProvider@@QEAAX$$QEAPEBG@Z; LauncherClientProvider::AppUriHandlerRegistrationManager::CreateRegistration<ushort const *>(ushort const * &&)
0x1800706a9  lea     rcx, [rsp+328h+var_2B0]
0x1800706ae  call    ??$GetActivationFactory@UIAppUriHandlerGroupStatics@StateRepository@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIAppUriHandlerGroupStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::StateRepository::IAppUriHandlerGroupStatics>(ushort const *)
0x1800706b3  nop
0x1800706b4  mov     rdx, [r15+28h]
0x1800706b8  lea     rcx, [rsp+328h+var_2B8]
0x1800706bd  call    ?GetStateRepoUserFromSystemUser@@YA?AV?$ComPtr@UIUser@StateRepository@Internal@Windows@@@WRL@Microsoft@@PEAUIUser@System@Windows@@@Z; GetStateRepoUserFromSystemUser(Windows::System::IUser *)
0x1800706c2  nop
0x1800706c3  mov     qword ptr [rsp+328h+var_2D8], rsi
0x1800706c8  mov     [rsp+328h+lpString2], rsi
0x1800706cd  xor     edx, edx
0x1800706cf  lea     rcx, [rsp+328h+lpString2]
0x1800706d4  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800706d9  lea     rcx, [rsp+328h+lpString2]; this
0x1800706de  call    ?GetCallingProcessPackageFamilyName@UserAwareCallerIdentity@@YAJPEAPEAG@Z; UserAwareCallerIdentity::GetCallingProcessPackageFamilyName(ushort * *)
0x1800706e3  mov     rcx, [rsp+328h]; this
0x1800706eb  test    eax, eax
0x1800706ed  jns     short loc_180070703
0x1800706ef  mov     r9d, eax; char *
0x1800706f2  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.system.launc"...
0x1800706f9  mov     edx, 170h; void *
0x1800706fe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180070703  mov     [rsp+328h+string], rsi
0x180070708  cmp     [r15+30h], rsi
0x18007070c  jz      short loc_180070771
0x18007070e  lea     rbx, [r15+38h]
0x180070712  mov     rcx, rbx; SRWLock
0x180070715  call    cs:__imp_AcquireSRWLockShared
0x18007071b  mov     [rsp+328h+var_2F0], rbx
0x180070720  mov     rcx, [rsp+328h+string]; string
0x180070725  call    cs:__imp_WindowsDeleteString
0x18007072b  mov     [rsp+328h+string], rsi
0x180070730  lea     rdx, [rsp+328h+string]; newString
0x180070735  mov     rcx, [r15+30h]; string
0x180070739  call    cs:__imp_WindowsDuplicateString
0x18007073f  mov     rcx, [rsp+328h]; this
0x180070747  test    eax, eax
0x180070749  jns     short loc_180070760
0x18007074b  mov     r9d, eax; char *
0x18007074e  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.system.launc"...
0x180070755  mov     edx, 176h; void *
0x18007075a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180070760  lea     rcx, [rsp+328h+var_2F0]
0x180070765  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18007076a  mov     rbx, [rsp+328h+lpString2]
0x18007076f  jmp     short loc_18007078A
0x180070771  mov     rbx, [rsp+328h+lpString2]
0x180070776  mov     [rsp+328h+var_2F0], rbx
0x18007077b  lea     rdx, [rsp+328h+var_2F0]
0x180070780  lea     rcx, [rsp+328h+string]
0x180070785  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18007078a  mov     r14, [rsp+328h+var_2B0]
0x18007078f  mov     rax, [r14]
0x180070792  mov     rsi, [rax+78h]
0x180070796  lea     rcx, [rsp+328h+var_2D8]
0x18007079b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800707a0  lea     rax, [rsp+328h+var_2D8]
0x1800707a5  mov     qword ptr [rsp+328h+bIgnoreCase], rax; int
0x1800707aa  mov     r9, r12
0x1800707ad  mov     r8, [rsp+328h+string]
0x1800707b2  mov     rdx, [rsp+328h+var_2B8]
0x1800707b7  mov     rcx, r14
0x1800707ba  mov     rax, rsi
0x1800707bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800707c2  mov     rcx, [rsp+328h]; this
0x1800707ca  xor     r14d, r14d
0x1800707cd  test    eax, eax
0x1800707cf  jns     short loc_1800707E5
0x1800707d1  mov     r9d, eax; char *
0x1800707d4  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.system.launc"...
0x1800707db  mov     edx, 17Eh; void *
0x1800707e0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800707e5  cmp     qword ptr [rsp+328h+var_2D8], r14
0x1800707ea  jz      loc_180070BD8
0x1800707f0  xor     edx, edx; length
0x1800707f2  mov     rcx, [rsp+328h+string]; string
0x1800707f7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800707fd  mov     [rsp+328h+bIgnoreCase], 1; int
0x180070805  or      edx, 0FFFFFFFFh; cchCount1
0x180070808  mov     r9d, edx; cchCount2
0x18007080b  mov     r8, rbx; lpString2
0x18007080e  mov     rcx, rax; lpString1
0x180070811  call    cs:__imp_CompareStringOrdinal
0x180070817  cmp     eax, 2
0x18007081a  jz      loc_180070B86
0x180070820  xor     edx, edx; length
0x180070822  mov     rcx, [rsp+328h+string]; string
0x180070827  call    cs:__imp_WindowsGetStringRawBuffer
0x18007082d  mov     [rsp+328h+var_2C8], rax
0x180070832  mov     [rsp+328h+var_2C0], rbx
0x180070837  lea     r8, [rsp+328h+var_2C8]
0x18007083c  lea     rdx, [rsp+328h+var_2C0]
0x180070841  lea     rcx, [rsp+328h+var_198]
0x180070849  call    ??$CreateRegistrationForPackage@PEAGPEBG@AppUriHandlerRegistrationManager@LauncherClientProvider@@QEAAX$$QEAPEAG$$QEAPEBG@Z; LauncherClientProvider::AppUriHandlerRegistrationManager::CreateRegistrationForPackage<ushort *,ushort const *>(ushort * &&,ushort const * &&)
0x18007084e  lea     rcx, [rsp+328h+var_2A0]
0x180070856  call    ??$?0AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@$$CBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@$$CBV12@@2@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@$$CBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@$$CBV12@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@$$CBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@$$CBV12@@2@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<std::vector<std::wstring> const,std::vector<std::wstring> const>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<std::vector<std::wstring> const,std::vector<std::wstring> const>>>>>>>(std::allocator<std::pair<std::wstring const,std::pair<std::vector<std::wstring> const,std::vector<std::wstring> const>>> const &)
0x18007085b  nop
0x18007085c  lea     rcx, [rsp+328h+var_2A0]
0x180070864  call    ?GetHostIds@@YAXAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; GetHostIds(std::vector<std::wstring> &)
0x180070869  mov     rax, [rsp+328h+var_298]
0x180070871  cmp     [rsp+328h+var_2A0], rax
0x180070879  setz    al
0x18007087c  mov     rcx, [rsp+328h]; this
0x180070884  test    al, al
0x180070886  jz      short loc_18007089F
0x180070888  mov     r9d, 80070005h; char *
0x18007088e  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.system.launc"...
0x180070895  mov     edx, 18Ah; void *
0x18007089a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007089f  mov     [rsp+328h+var_2F0], r14
0x1800708a4  mov     rcx, qword ptr [rsp+328h+var_2D8]
0x1800708a9  mov     rax, [rcx]
0x1800708ac  lea     rdx, [rsp+328h+var_2F0]
0x1800708b1  mov     rax, [rax+48h]
0x1800708b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800708ba  mov     rcx, [rsp+328h]; this
0x1800708c2  test    eax, eax
0x1800708c4  jns     short loc_1800708DA
0x1800708c6  mov     r9d, eax; char *
0x1800708c9  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.system.launc"...
0x1800708d0  mov     edx, 18Dh; void *
0x1800708d5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800708da  mov     [rsp+328h+var_2E0], r14
0x1800708df  lea     rax, [rsp+328h+var_2E0]
0x1800708e4  mov     [rsp+328h+var_278], rax
0x1800708ec  mov     [rsp+328h+var_270], r14
0x1800708f4  mov     [rsp+328h+var_268], 1
0x1800708fc  lea     rdx, [rsp+328h+var_270]
0x180070904  xor     ecx, ecx
0x180070906  call    cs:__imp_SRCacheManager_Open
0x18007090c  mov     edi, eax
0x18007090e  lea     rcx, [rsp+328h+var_278]
0x180070916  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x18007091b  test    edi, edi
0x18007091d  jns     short loc_18007093D
0x18007091f  mov     rcx, [rsp+328h]; this
0x180070927  mov     r9d, edi; char *
0x18007092a  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x180070931  mov     edx, 0A5h; void *
0x180070936  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007093b  jmp     short loc_180070940
0x18007093d  mov     edi, r14d
0x180070940  mov     rcx, [rsp+328h]; this
0x180070948  test    edi, edi
0x18007094a  jns     short loc_180070960
0x18007094c  mov     r9d, edi; char *
0x18007094f  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.system.launc"...
0x180070956  mov     edx, 190h; void *
0x18007095b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180070960  xorps   xmm0, xmm0
0x180070963  movdqa  [rsp+328h+var_258], xmm0
0x18007096c  mov     [rsp+328h+var_248], r14
0x180070974  mov     [rsp+328h+var_240], r14
0x18007097c  movdqa  [rsp+328h+var_238], xmm0
0x180070985  xorps   xmm1, xmm1
0x180070988  movdqa  [rsp+328h+var_228], xmm1
0x180070991  mov     [rsp+328h+var_218], r14
0x180070999  mov     [rsp+328h+var_210], r14d
0x1800709a1  mov     byte ptr [rsp+328h+var_2F8], r14b
0x1800709a6  lea     rax, [rsp+328h+var_2F8]
0x1800709ab  mov     qword ptr [rsp+328h+bIgnoreCase], rax; int
0x1800709b0  lea     r9, [rsp+328h+var_258]
0x1800709b8  mov     r8d, 10h
0x1800709be  mov     rdx, [rsp+328h+var_2F0]
0x1800709c3  lea     rcx, [rsp+328h+var_2E0]
0x1800709c8  call    ?Get@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x1800709cd  mov     rcx, [rsp+328h]; this
0x1800709d5  cmp     byte ptr [rsp+328h+var_2F8], r14b
0x1800709da  jnz     short loc_1800709F3
0x1800709dc  mov     r9d, 80070057h; char *
0x1800709e2  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.system.launc"...
0x1800709e9  mov     edx, 196h; void *
0x1800709ee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800709f3  xorps   xmm0, xmm0
0x1800709f6  movdqa  [rsp+328h+var_208], xmm0
0x1800709ff  mov     [rsp+328h+var_1F8], r14d
0x180070a07  mov     [rsp+328h+var_1F0], r14
0x180070a0f  movdqa  [rsp+328h+var_1E8], xmm0
0x180070a18  xorps   xmm1, xmm1
0x180070a1b  movdqa  [rsp+328h+var_1D8], xmm1
0x180070a24  mov     [rsp+328h+var_1C8], r14
0x180070a2c  lea     rax, [rsp+328h+var_2F8]
0x180070a31  mov     qword ptr [rsp+328h+bIgnoreCase], rax; int
0x180070a36  lea     r9, [rsp+328h+var_208]
0x180070a3e  mov     rdx, qword ptr [rsp+328h+var_238]
0x180070a46  lea     rcx, [rsp+328h+var_2E0]
0x180070a4b  call    ?Get@Activation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Activation_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Activation_NoThrow::CacheFlags,StateRepository::Cache::Entity::Activation_NoThrow &,bool &)
0x180070a50  mov     rcx, [rsp+328h]; this
0x180070a58  cmp     byte ptr [rsp+328h+var_2F8], r14b
0x180070a5d  jnz     short loc_180070A76
0x180070a5f  mov     r9d, 80070057h; char *
0x180070a65  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.system.launc"...
0x180070a6c  mov     edx, 19Ah; void *
0x180070a71  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180070a76  mov     rdx, [rsp+328h+var_1F0]
0x180070a7e  mov     rcx, [rsp+328h]; this
0x180070a86  test    rdx, rdx
0x180070a89  jnz     short loc_180070AA2
0x180070a8b  mov     r9d, 80070005h; char *
0x180070a91  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.system.launc"...
0x180070a98  mov     edx, 19Fh; void *
0x180070a9d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180070aa2  lea     rcx, [rsp+328h+var_1B8]
0x180070aaa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180070aaf  nop
0x180070ab0  mov     rsi, [rsp+328h+var_298]
0x180070ab8  mov     rdi, [rsp+328h+var_2A0]
0x180070ac0  cmp     rdi, rsi
0x180070ac3  jz      short loc_180070B19
0x180070ac5  lea     r8, [rsp+328h+var_1B8]
0x180070acd  cmp     [rsp+328h+var_1A0], 7
0x180070ad6  cmova   r8, [rsp+328h+var_1B8]
0x180070adf  cmp     qword ptr [rdi+18h], 7
0x180070ae4  jbe     short loc_180070AEB
0x180070ae6  mov     rcx, [rdi]
0x180070ae9  jmp     short loc_180070AEE
0x180070aeb  mov     rcx, rdi
0x180070aee  mov     r9, [rsp+328h+var_1A8]
0x180070af6  mov     rdx, [rdi+10h]
0x180070afa  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180070aff  test    al, al
0x180070b01  jnz     short loc_180070B0C
0x180070b03  add     rdi, 20h ; ' '
0x180070b07  cmp     rdi, rsi
0x180070b0a  jnz     short loc_180070AC5
0x180070b0c  mov     rsi, [rsp+328h+var_298]
0x180070b14  cmp     rdi, rsi
0x180070b17  jnz     short loc_180070B39
0x180070b19  mov     rcx, [rsp+328h]; this
0x180070b21  mov     r9d, 80070005h; char *
0x180070b27  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.system.launc"...
0x180070b2e  mov     edx, 1A6h; void *
0x180070b33  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180070b39  lea     rcx, [rsp+328h+var_1B8]
0x180070b41  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180070b46  nop
0x180070b47  lea     rcx, [rsp+328h+var_208]; this
0x180070b4f  call    ??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)
0x180070b54  nop
0x180070b55  lea     rcx, [rsp+328h+var_258]; this
0x180070b5d  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x180070b62  nop
0x180070b63  mov     rcx, [rsp+328h+var_2E0]
0x180070b68  mov     [rsp+328h+var_2E0], r14
0x180070b6d  test    rcx, rcx
0x180070b70  jz      short loc_180070B79
0x180070b72  call    cs:__imp_SRCacheManager_Close
0x180070b78  nop
0x180070b79  lea     rcx, [rsp+328h+var_2A0]
0x180070b81  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180070b86  mov     rax, [rsp+328h+string]
0x180070b8b  mov     [rsp+328h+var_2C0], rax
0x180070b90  mov     rax, [r15+28h]
0x180070b94  mov     [rsp+328h+var_2C8], rax
0x180070b99  lea     r9, [rsp+328h+var_2C0]
0x180070b9e  lea     r8, [rsp+328h+var_2C8]
0x180070ba3  lea     rdx, [rsp+328h+var_288]
0x180070bab  lea     rcx, [rsp+328h+var_2F0]
0x180070bb0  call    ??$Make@VAppUriHandlerRegistration@System@Windows@@AEAPEAUHSTRING__@@PEAUIUser@23@PEAU4@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VAppUriHandlerRegistration@System@Windows@@@12@AEAPEAUHSTRING__@@$$QEAPEAUIUser@System@Windows@@$$QEAPEAU4@@Z; Microsoft::WRL::Details::Make<Windows::System::AppUriHandlerRegistration,HSTRING__ * &,Windows::System::IUser *,HSTRING__ *>(HSTRING__ * &,Windows::System::IUser * &&,HSTRING__ * &&)
0x180070bb5  mov     rdi, [rax]
0x180070bb8  mov     [rax], r14
0x180070bbb  mov     [rsp+328h+var_2A8], rdi
0x180070bc3  mov     rcx, [rsp+328h+var_2F0]
0x180070bc8  test    rcx, rcx
  ... truncated ...
```
