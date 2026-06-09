# QueryAssociationBroker::GetAppUriHandlerHosts(HSTRING__ *,HSTRING__ *,Windows::System::IUser *,Windows::System::Internal::Launch::AppUriHandlerHostTypeOptions,Windows::Foundation::Collections::IVector<Windows::System::AppUriHandlerHost *> * *)

- ea: `0x180065450`
- end: `0x18006607e`
- name: `?GetAppUriHandlerHosts@QueryAssociationBroker@@UEAAJPEAUHSTRING__@@0PEAUIUser@System@Windows@@W4AppUriHandlerHostTypeOptions@Launch@Internal@45@PEAPEAU?$IVector@PEAVAppUriHandlerHost@System@Windows@@@Collections@Foundation@5@@Z`
- size: `3118`
- prototype: `__int64 __fastcall(__int64, HSTRING, HSTRING, struct Windows::System::IUser *, int, __int64)`
- caller_count: `0`
- callee_count: `39`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800049bc`
- `0x1800049e8`
- `0x180004fe4`
- `0x180009a7c`
- `0x18000a790`
- `0x18000b0fc`
- `0x18000b1fc`
- `0x18000f194`
- `0x180010c04`
- `0x180014af8`
- `0x1800170f0`
- `0x18001a528`
- `0x18001d10c`
- `0x180034d10`
- `0x18003ab7c`
- `0x1800640f4`
- `0x18006465c`
- `0x180065450`
- `0x180066084`
- `0x180066628`
- `0x1800666cc`
- `0x180066864`
- `0x180066b04`
- `0x180066cfc`
- `0x180067278`
- `0x180067358`
- `0x180067484`
- `0x1800674cc`
- `0x180067840`
- `0x18006799c`
- `0x1800679c8`
- `0x180079db8`
- `0x18007c350`
- `0x18007d254`
- `0x18008a030`
- `0x1800b4470`
- `0x1800b5004`
- `0x1800b9960`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180065576`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180065576`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180065b4d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180065b4d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1800655dc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1800655dc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180065bb5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180065bb5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18006601a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18006601a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180065c8c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180065cf7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180065d67`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180065f9f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180066004`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180065c8c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180065cf7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180065d67`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180065f9f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180066004`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006548e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006549c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065642`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065b31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065e0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006548e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006549c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065642`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065b31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065e0f`

## string_xrefs

- `0x1800658c9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18006596f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180065506`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x18006553e`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x18006559f`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180065624`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x18006566e`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x18006569f`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800656e8`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x18006579a`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800657ea`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x18006586b`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800658ed`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800659d2`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180065a28`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180065a8a`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180065aed`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180065b13`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180065b8a`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180065bfd`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180065c40`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180065cbe`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180065d34`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180065de6`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180065ebc`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180065f15`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180065f53`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180065fd0`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180065600`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`
- `0x1800654a5`: `GetAppUriHandlerHosts`
- `0x180065567`: `AppUriHandlers`

## pseudocode

```c
__int64 __fastcall QueryAssociationBroker::GetAppUriHandlerHosts(
        __int64 a1,
        HSTRING a2,
        HSTRING a3,
        struct Windows::System::IUser *a4,
        int a5,
        __int64 a6)
{
  const unsigned __int16 *StringRawBuffer; // rdi
  const unsigned __int16 *v11; // rbx
  __int64 v12; // rcx
  int v13; // eax
  int SystemApplicationDataKey; // eax
  int v15; // eax
  bool v16; // dl
  int v17; // ebx
  const unsigned __int16 *v18; // rax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  const unsigned __int16 *v24; // r9
  int v25; // eax
  int v26; // ebx
  int v27; // eax
  int v28; // ebx
  __int64 v29; // rdx
  int v30; // eax
  int v31; // eax
  __int64 v32; // r8
  int v33; // eax
  const WCHAR *v34; // rbx
  const WCHAR *v35; // rax
  int v36; // eax
  LPCWCH v37; // rcx
  int v38; // eax
  int v39; // eax
  __int64 v40; // rcx
  int v41; // eax
  __int64 v42; // rcx
  int v43; // eax
  __int64 v44; // rcx
  int v45; // eax
  const unsigned __int16 *v46; // rax
  int v47; // eax
  int v48; // eax
  int v49; // eax
  __int64 v50; // rcx
  int v51; // eax
  __int64 v52; // rcx
  __int64 v53; // rcx
  int phkResult; // [rsp+20h] [rbp-3C8h]
  PHKEY phkResulta; // [rsp+20h] [rbp-3C8h]
  char v57; // [rsp+30h] [rbp-3B8h] BYREF
  char v58; // [rsp+31h] [rbp-3B7h] BYREF
  char v59; // [rsp+32h] [rbp-3B6h] BYREF
  _BYTE v60[5]; // [rsp+33h] [rbp-3B5h] BYREF
  __int64 v61; // [rsp+38h] [rbp-3B0h] BYREF
  void *v62; // [rsp+40h] [rbp-3A8h] BYREF
  __int64 StateRepoUserFromSystemUser; // [rsp+48h] [rbp-3A0h] BYREF
  __int64 v64; // [rsp+50h] [rbp-398h] BYREF
  __int64 v65; // [rsp+58h] [rbp-390h] BYREF
  int v66; // [rsp+60h] [rbp-388h]
  __int64 v67; // [rsp+68h] [rbp-380h]
  HKEY v68; // [rsp+70h] [rbp-378h] BYREF
  __int64 v69; // [rsp+78h] [rbp-370h] BYREF
  int v70; // [rsp+80h] [rbp-368h]
  __int64 v71; // [rsp+88h] [rbp-360h]
  __int64 v72; // [rsp+90h] [rbp-358h] BYREF
  HKEY hKey; // [rsp+98h] [rbp-350h] BYREF
  LPCWCH lpString2[2]; // [rsp+A0h] [rbp-348h] BYREF
  __int128 v75; // [rsp+B0h] [rbp-338h]
  __int64 v76; // [rsp+C0h] [rbp-328h]
  __int64 v77; // [rsp+C8h] [rbp-320h] BYREF
  int v78; // [rsp+D0h] [rbp-318h]
  __int64 v79; // [rsp+D8h] [rbp-310h]
  __int64 v80; // [rsp+E0h] [rbp-308h] BYREF
  __int64 v81; // [rsp+E8h] [rbp-300h] BYREF
  int v82; // [rsp+F0h] [rbp-2F8h]
  __int64 v83; // [rsp+F8h] [rbp-2F0h]
  _OWORD v84[2]; // [rsp+100h] [rbp-2E8h] BYREF
  __int128 v85; // [rsp+120h] [rbp-2C8h]
  __int64 v86[2]; // [rsp+130h] [rbp-2B8h] BYREF
  __int64 v87; // [rsp+140h] [rbp-2A8h]
  __int64 v88; // [rsp+148h] [rbp-2A0h]
  __int64 v89; // [rsp+150h] [rbp-298h]
  __int64 v90; // [rsp+158h] [rbp-290h]
  __int64 v91; // [rsp+160h] [rbp-288h]
  __int64 v92; // [rsp+168h] [rbp-280h]
  __int128 v93; // [rsp+170h] [rbp-278h]
  int v94; // [rsp+180h] [rbp-268h]
  __int64 v95; // [rsp+188h] [rbp-260h]
  __int64 v96; // [rsp+190h] [rbp-258h]
  __int64 v97[2]; // [rsp+1A0h] [rbp-248h] BYREF
  __int64 v98; // [rsp+1B0h] [rbp-238h]
  __int64 v99; // [rsp+1B8h] [rbp-230h]
  __int128 v100; // [rsp+1C0h] [rbp-228h]
  __int128 v101; // [rsp+1D0h] [rbp-218h]
  __int64 v102; // [rsp+1E0h] [rbp-208h]
  int v103; // [rsp+1E8h] [rbp-200h]
  __int64 v104[2]; // [rsp+1F0h] [rbp-1F8h] BYREF
  __int64 v105; // [rsp+200h] [rbp-1E8h]
  __int64 v106; // [rsp+208h] [rbp-1E0h]
  __int128 v107; // [rsp+210h] [rbp-1D8h]
  __int128 v108; // [rsp+220h] [rbp-1C8h]
  __int128 v109; // [rsp+230h] [rbp-1B8h]
  __int128 v110; // [rsp+240h] [rbp-1A8h]
  _QWORD v111[42]; // [rsp+250h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3E8h] [rbp+0h]

  StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
  v11 = WindowsGetStringRawBuffer(a2, 0);
  wil::ActivityBase<LauncherServiceProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherServiceProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v111);
  v111[0] = &LauncherServiceProvider::GetAppUriHandlerHosts::`vftable';
  LauncherServiceProvider::GetAppUriHandlerHosts::StartActivity(
    (LauncherServiceProvider::GetAppUriHandlerHosts *)v111,
    v11,
    StringRawBuffer);
  v64 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
  v13 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::System::AppUriHandlerHost,Windows::Foundation::Collections::Internal::AgileVector<Windows::System::AppUriHandlerHost *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::AppUriHandlerHost *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::AppUriHandlerHost *>,0>>(
          v12,
          &v64);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4EC,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v13,
      phkResult);
  hKey = 0;
  SystemApplicationDataKey = GetSystemApplicationDataKey(a2, &hKey);
  if ( SystemApplicationDataKey < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4F0,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)SystemApplicationDataKey,
      phkResult);
  v68 = 0;
  v15 = RegOpenKeyExW(hKey, L"AppUriHandlers", 0, 0x20019u, &v68);
  v16 = (v15 & 0xFFFFFFFD) == 0;
  if ( v15 > 0 )
    v15 = (unsigned __int16)v15 | 0x80070000;
  if ( !v16 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4FA,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v15,
      (int)phkResulta);
  v61 = 0;
  lpString2[0] = (LPCWCH)&v61;
  lpString2[1] = 0;
  LOBYTE(v75) = 1;
  v17 = SRCacheManager_Open(0, &lpString2[1]);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(lpString2);
  if ( v17 >= 0 )
    v17 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      (const char *)(unsigned int)v17,
      (int)phkResulta);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4FD,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v17,
      (int)phkResulta);
  v72 = 0;
  v18 = WindowsGetStringRawBuffer(a2, 0);
  v19 = StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(
          (struct StateRepository::Cache::Manager_NoThrow *)&v61,
          v18,
          &v72);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x500,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v19,
      (int)phkResulta);
  if ( !v72 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x501,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)0x80070057LL,
      (int)phkResulta);
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v20 = StateRepository::Cache::Entity::Package_NoThrow::FindByPackageFamily(
          (struct StateRepository::Cache::Manager_NoThrow *)&v61,
          v72,
          (struct StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *)&v77);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x504,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v20,
      (int)phkResulta);
  if ( !a5 || (a5 & 1) != 0 )
  {
    *(_OWORD *)v86 = 0;
    v87 = 0;
    v88 = 0;
    v89 = 0;
    v90 = 0;
    v91 = 0;
    v92 = 0;
    v93 = 0;
    v94 = 0;
    v95 = 0;
    v96 = 0;
    v57 = 0;
    v21 = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(&v77, 0, v86, &v57);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x50C,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v21,
        (int)phkResulta);
LABEL_24:
    if ( v57 )
    {
      v65 = 0;
      v66 = 0;
      v67 = 0;
      v22 = StateRepository::Cache::Entity::Application_NoThrow::FindByPackage(
              (struct StateRepository::Cache::Manager_NoThrow *)&v61,
              v86[0],
              (struct StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow *)&v65);
      if ( v22 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x511,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
          (const char *)(unsigned int)v22,
          (int)phkResulta);
      *(_OWORD *)v104 = 0;
      v105 = 0;
      v106 = 0;
      v107 = 0;
      v108 = 0;
      v109 = 0;
      v110 = 0;
      v60[0] = 0;
      v23 = StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::Get(&v65, 0, v104, v60);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x516,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
          (const char *)(unsigned int)v23,
          (int)phkResulta);
      while ( 1 )
      {
        if ( !v60[0] )
        {
          ++v78;
          v43 = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(&v77, 0, v86, &v57);
          if ( v43 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x547,
              (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
              (const char *)(unsigned int)v43,
              (int)phkResulta);
          StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v104);
          v44 = v65;
          v65 = 0;
          if ( v44 )
            SRCacheContext_Close();
          goto LABEL_24;
        }
        v81 = 0;
        v82 = 0;
        v83 = 0;
        v25 = StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplicationAndCategory(
                (StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow *)&v81,
                (struct StateRepository::Cache::Manager_NoThrow *)&v61,
                v104[0],
                v24);
        v26 = v25;
        if ( v25 >= 0 )
          v26 = 0;
        else
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3B9,
            (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
            (const char *)(unsigned int)v25,
            (int)phkResulta);
        if ( v26 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x51B,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
            (const char *)(unsigned int)v26,
            (int)phkResulta);
        *(_OWORD *)v97 = 0;
        v98 = 0;
        v99 = 0;
        v100 = 0;
        v101 = 0;
        v102 = 0;
        v103 = 0;
        v58 = 0;
        if ( v81 )
        {
          v62 = 0;
          v27 = StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(
                  (StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow *)&v81,
                  (__int64 *)&v62);
          v28 = v27;
          if ( v27 < 0 )
          {
            v29 = 684;
LABEL_38:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v29,
              (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
              (const char *)(unsigned int)v27,
              (int)phkResulta);
            goto LABEL_43;
          }
          if ( v62 )
          {
            phkResulta = (PHKEY)&v58;
            v27 = StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Get(v83, v62, 0, v97);
            v28 = v27;
            if ( v27 < 0 )
            {
              v29 = 689;
              goto LABEL_38;
            }
          }
        }
        v28 = 0;
LABEL_43:
        if ( v28 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x520,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
            (const char *)(unsigned int)v28,
            (int)phkResulta);
        if ( v58 )
        {
          v69 = 0;
          v70 = 0;
          v71 = 0;
          v30 = StateRepository::Cache::Entity::AppUriHandler_NoThrow::FindByExtension(
                  (struct StateRepository::Cache::Manager_NoThrow *)&v61,
                  v97[0],
                  (struct StateRepository::Cache::Entity::AppUriHandlerIndexIterator_NoThrow *)&v69);
          if ( v30 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x526,
              (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
              (const char *)(unsigned int)v30,
              (int)phkResulta);
          memset(v84, 0, sizeof(v84));
          v85 = 0;
          v59 = 0;
          v31 = StateRepository::Cache::Entity::AppUriHandlerIndexIterator_NoThrow::Get(&v69, 19, v84, &v59);
          if ( v31 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x52B,
              (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
              (const char *)(unsigned int)v31,
              (int)phkResulta);
          while ( v59 )
          {
            *(_OWORD *)lpString2 = 0;
            *(_QWORD *)&v75 = 0;
            v33 = StateRepository::Cache::Entity::AppUriHandlerGroup_NoThrow::Get(
                    &v61,
                    *((_QWORD *)&v85 + 1),
                    v32,
                    lpString2);
            if ( v33 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x531,
                (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
                (const char *)(unsigned int)v33,
                (int)&v58);
            if ( !v58 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x532,
                (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
                (const char *)0x8000FFFFLL,
                (int)&v58);
            v34 = lpString2[1];
            v35 = WindowsGetStringRawBuffer(a3, 0);
            if ( CompareStringOrdinal(v35, -1, v34, -1, 1) == 2 )
            {
              CreateAppUriHandlerHost(&StateRepoUserFromSystemUser, v68, *((_QWORD *)&v84[0] + 1));
              v38 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v64 + 104LL))(
                      v64,
                      StateRepoUserFromSystemUser);
              if ( v38 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x53E,
                  (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
                  (const char *)(unsigned int)v38,
                  (int)phkResulta);
              ++v70;
              v39 = StateRepository::Cache::Entity::AppUriHandlerIndexIterator_NoThrow::Get(&v69, 19, v84, &v59);
              if ( v39 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x540,
                  (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
                  (const char *)(unsigned int)v39,
                  (int)phkResulta);
              if ( StateRepoUserFromSystemUser )
              {
                StateRepoUserFromSystemUser = 0;
                Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::IAppUriHandlerHost,Windows::System::IAppUriHandlerHost2,Microsoft::WRL::FtmBase>::Release();
              }
            }
            else
            {
              ++v70;
              v36 = StateRepository::Cache::Entity::AppUriHandlerIndexIterator_NoThrow::Get(&v69, 19, v84, &v59);
              if ( v36 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x537,
                  (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
                  (const char *)(unsigned int)v36,
                  (int)phkResulta);
            }
            v37 = lpString2[1];
            lpString2[1] = 0;
            if ( v37 )
              SRCache_Free();
          }
          StateRepository::Cache::Entity::AppUriHandler_NoThrow::~AppUriHandler_NoThrow((StateRepository::Cache::Entity::AppUriHandler_NoThrow *)v84);
          v40 = v69;
          v69 = 0;
          if ( v40 )
            SRCacheContext_Close();
        }
        ++v66;
        v41 = StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::Get(&v65, 0, v104, v60);
        if ( v41 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x544,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
            (const char *)(unsigned int)v41,
            (int)phkResulta);
        StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)v97);
        v42 = v81;
        v81 = 0;
        if ( v42 )
          SRCacheContext_Close();
      }
    }
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v86);
    if ( !a5 )
      goto LABEL_78;
  }
  if ( (a5 & 2) != 0 )
  {
LABEL_78:
    StateRepoUserFromSystemUser = 0;
    if ( a4 )
    {
      StateRepoUserFromSystemUser = GetStateRepoUserFromSystemUser(
                                      (struct StateRepository::Cache::Manager_NoThrow *)&v61,
                                      a4);
    }
    else
    {
      wil::GetImpersonationTokenForClientOfObject(
        &v62,
        a1 & ((unsigned __int128)-(__int128)(unsigned __int64)(a1 - 40) >> 64));
      v45 = StateRepository::Cache::Entity::User_NoThrow::GetByToken(
              (struct StateRepository::Cache::Manager_NoThrow *)&v61,
              v62,
              &StateRepoUserFromSystemUser);
      if ( v45 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x55A,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
          (const char *)(unsigned int)v45,
          (int)phkResulta);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v62);
    }
    v80 = 0;
    v46 = WindowsGetStringRawBuffer(a3, 0);
    StateRepository::Cache::Entity::DynamicAppUriHandlerGroup_NoThrow::GetByUserAndPackageFamilyAndName(
      (struct StateRepository::Cache::Manager_NoThrow *)&v61,
      StateRepoUserFromSystemUser,
      v72,
      v46,
      &v80);
    if ( v80 )
    {
      v65 = 0;
      v66 = 0;
      v67 = 0;
      StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::FindByDynamicAppUriHandlerGroup(
        (struct StateRepository::Cache::Manager_NoThrow *)&v61,
        v80,
        (struct StateRepository::Cache::Entity::DynamicAppUriHandlerIndexIterator_NoThrow *)&v65);
      *(_OWORD *)lpString2 = 0;
      v75 = 0;
      v76 = 0;
      v57 = 0;
      v47 = StateRepository::Cache::Entity::DynamicAppUriHandlerIndexIterator_NoThrow::Get(&v65, 6, lpString2, &v57);
      if ( v47 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x569,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
          (const char *)(unsigned int)v47,
          (int)phkResulta);
      while ( v57 )
      {
        CreateAppUriHandlerHost(&v62, v68, v75);
        v48 = (*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)v64 + 104LL))(v64, v62);
        if ( v48 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x56F,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
            (const char *)(unsigned int)v48,
            (int)phkResulta);
        ++v66;
        v49 = StateRepository::Cache::Entity::DynamicAppUriHandlerIndexIterator_NoThrow::Get(&v65, 6, lpString2, &v57);
        if ( v49 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x571,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
            (const char *)(unsigned int)v49,
            (int)phkResulta);
        if ( v62 )
        {
          v62 = 0;
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::IAppUriHandlerHost,Windows::System::IAppUriHandlerHost2,Microsoft::WRL::FtmBase>::Release();
        }
      }
      StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::~DynamicAppUriHandler_NoThrow((StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow *)lpString2);
      v50 = v65;
      v65 = 0;
      if ( v50 )
        SRCacheContext_Close();
    }
  }
  v51 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64))v64)(v64, &GUID_4a226614_2197_526a_a9ff_03025d18e322, a6);
  if ( v51 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x576,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v51,
      (int)phkResulta);
  wil::ActivityBase<LauncherServiceProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v111);
  v52 = v77;
  v77 = 0;
  if ( v52 )
    SRCacheContext_Close();
  v53 = v61;
  v61 = 0;
  if ( v53 )
    SRCacheManager_Close();
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v68);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
  LauncherServiceProvider::GetAppUriHandlerHosts::~GetAppUriHandlerHosts((LauncherServiceProvider::GetAppUriHandlerHosts *)v111);
  return 0;
}

```

## disassembly

```asm
0x180065450  push    rbx
0x180065452  push    rsi
0x180065453  push    rdi
0x180065454  push    r12
0x180065456  push    r13
0x180065458  push    r14
0x18006545a  push    r15
0x18006545c  sub     rsp, 3B0h
0x180065463  mov     rax, cs:__security_cookie
0x18006546a  xor     rax, rsp
0x18006546d  mov     [rsp+3E8h+var_48], rax
0x180065475  mov     r14, r9
0x180065478  mov     r12, r8
0x18006547b  mov     rsi, rdx
0x18006547e  mov     r15, rcx
0x180065481  mov     r13, [rsp+3E8h+arg_28]
0x180065489  xor     edx, edx; length
0x18006548b  mov     rcx, r8; string
0x18006548e  call    cs:__imp_WindowsGetStringRawBuffer
0x180065494  mov     rdi, rax
0x180065497  xor     edx, edx; length
0x180065499  mov     rcx, rsi; string
0x18006549c  call    cs:__imp_WindowsGetStringRawBuffer
0x1800654a2  mov     rbx, rax
0x1800654a5  lea     rdx, aGetappurihandl; "GetAppUriHandlerHosts"
0x1800654ac  lea     rcx, [rsp+3E8h+var_198]; struct wil::details::IFailureCallback *
0x1800654b4  call    ??0?$ActivityBase@VLauncherServiceProvider@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherServiceProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherServiceProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800654b9  lea     rax, ??_7GetAppUriHandlerHosts@LauncherServiceProvider@@6B@; const LauncherServiceProvider::GetAppUriHandlerHosts::`vftable'
0x1800654c0  mov     [rsp+3E8h+var_198], rax
0x1800654c8  mov     r8, rdi; unsigned __int16 *
0x1800654cb  mov     rdx, rbx; unsigned __int16 *
0x1800654ce  lea     rcx, [rsp+3E8h+var_198]; this
0x1800654d6  call    ?StartActivity@GetAppUriHandlerHosts@LauncherServiceProvider@@QEAAXPEBG0@Z; LauncherServiceProvider::GetAppUriHandlerHosts::StartActivity(ushort const *,ushort const *)
0x1800654db  nop
0x1800654dc  xor     edi, edi
0x1800654de  mov     [rsp+3E8h+var_398], rdi
0x1800654e3  lea     rcx, [rsp+3E8h+var_398]
0x1800654e8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800654ed  lea     rdx, [rsp+3E8h+var_398]
0x1800654f2  call    ??$CreateExternalObjectVector@VAppUriHandlerHost@System@Windows@@V?$AgileVector@PEAVAppUriHandlerHost@System@Windows@@U?$DefaultEqualityPredicate@PEAVAppUriHandlerHost@System@Windows@@@Internal@Collections@Foundation@3@U?$DefaultLifetimeTraits@PEAVAppUriHandlerHost@System@Windows@@@5673@$0A@@Internal@Collections@Foundation@3@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVAppUriHandlerHost@System@Windows@@U?$DefaultEqualityPredicate@PEAVAppUriHandlerHost@System@Windows@@@Internal@Collections@Foundation@3@U?$DefaultLifetimeTraits@PEAVAppUriHandlerHost@System@Windows@@@5673@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::System::AppUriHandlerHost,Windows::Foundation::Collections::Internal::AgileVector<Windows::System::AppUriHandlerHost *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::AppUriHandlerHost *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::AppUriHandlerHost *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::System::AppUriHandlerHost *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::AppUriHandlerHost *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::AppUriHandlerHost *>,0> * *)
0x1800654f7  mov     rcx, [rsp+3E8h]; this
0x1800654ff  test    eax, eax
0x180065501  jns     short loc_180065517
0x180065503  mov     r9d, eax; char *
0x180065506  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x18006550d  mov     edx, 4ECh; void *
0x180065512  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180065517  mov     [rsp+3E8h+hKey], rdi
0x18006551f  lea     rdx, [rsp+3E8h+hKey]; HKEY *
0x180065527  mov     rcx, rsi; HSTRING
0x18006552a  call    ?GetSystemApplicationDataKey@@YAJPEAUHSTRING__@@PEAPEAUHKEY__@@@Z; GetSystemApplicationDataKey(HSTRING__ *,HKEY__ * *)
0x18006552f  mov     rcx, [rsp+3E8h]; this
0x180065537  test    eax, eax
0x180065539  jns     short loc_18006554F
0x18006553b  mov     r9d, eax; char *
0x18006553e  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180065545  mov     edx, 4F0h; void *
0x18006554a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006554f  mov     [rsp+3E8h+var_378], rdi
0x180065554  lea     rax, [rsp+3E8h+var_378]
0x180065559  mov     [rsp+3E8h+phkResult], rax; int
0x18006555e  mov     r9d, 20019h; samDesired
0x180065564  xor     r8d, r8d; ulOptions
0x180065567  lea     rdx, aAppurihandlers; "AppUriHandlers"
0x18006556e  mov     rcx, [rsp+3E8h+hKey]; hKey
0x180065576  call    cs:__imp_RegOpenKeyExW
0x18006557c  test    eax, 0FFFFFFFDh
0x180065581  setz    dl
0x180065584  test    eax, eax
0x180065586  jle     short loc_180065590
0x180065588  movzx   eax, ax
0x18006558b  or      eax, 80070000h
0x180065590  mov     rcx, [rsp+3E8h]; this
0x180065598  test    dl, dl
0x18006559a  jnz     short loc_1800655B0
0x18006559c  mov     r9d, eax; char *
0x18006559f  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x1800655a6  mov     edx, 4FAh; void *
0x1800655ab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800655b0  mov     [rsp+3E8h+var_3B0], rdi
0x1800655b5  lea     rax, [rsp+3E8h+var_3B0]
0x1800655ba  mov     [rsp+3E8h+lpString2], rax
0x1800655c2  mov     [rsp+3E8h+lpString2+8], rdi
0x1800655ca  mov     byte ptr [rsp+3E8h+var_338], 1
0x1800655d2  lea     rdx, [rsp+3E8h+lpString2+8]
0x1800655da  xor     ecx, ecx
0x1800655dc  call    cs:__imp_SRCacheManager_Open
0x1800655e2  mov     ebx, eax
0x1800655e4  lea     rcx, [rsp+3E8h+lpString2]
0x1800655ec  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x1800655f1  test    ebx, ebx
0x1800655f3  jns     short loc_180065613
0x1800655f5  mov     rcx, [rsp+3E8h]; this
0x1800655fd  mov     r9d, ebx; char *
0x180065600  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x180065607  mov     edx, 0A5h; void *
0x18006560c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065611  jmp     short loc_180065615
0x180065613  mov     ebx, edi
0x180065615  mov     rcx, [rsp+3E8h]; this
0x18006561d  test    ebx, ebx
0x18006561f  jns     short loc_180065635
0x180065621  mov     r9d, ebx; char *
0x180065624  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x18006562b  mov     edx, 4FDh; void *
0x180065630  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180065635  mov     [rsp+3E8h+var_358], rdi
0x18006563d  xor     edx, edx; length
0x18006563f  mov     rcx, rsi; string
0x180065642  call    cs:__imp_WindowsGetStringRawBuffer
0x180065648  mov     rdx, rax; unsigned __int16 *
0x18006564b  lea     r8, [rsp+3E8h+var_358]; __int64 *
0x180065653  lea     rcx, [rsp+3E8h+var_3B0]; struct StateRepository::Cache::Manager_NoThrow *
0x180065658  call    ?GetByPackageFamilyName@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x18006565d  mov     rcx, [rsp+3E8h]; this
0x180065665  xor     esi, esi
0x180065667  test    eax, eax
0x180065669  jns     short loc_18006567F
0x18006566b  mov     r9d, eax; char *
0x18006566e  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180065675  mov     edx, 500h; void *
0x18006567a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006567f  mov     rdx, [rsp+3E8h+var_358]; __int64
0x180065687  test    rdx, rdx
0x18006568a  setz    al
0x18006568d  mov     rcx, [rsp+3E8h]; this
0x180065695  test    al, al
0x180065697  jz      short loc_1800656B0
0x180065699  mov     r9d, 80070057h; char *
0x18006569f  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x1800656a6  mov     edx, 501h; void *
0x1800656ab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800656b0  mov     [rsp+3E8h+var_320], rsi
0x1800656b8  mov     [rsp+3E8h+var_318], esi
0x1800656bf  mov     [rsp+3E8h+var_310], rsi
0x1800656c7  lea     r8, [rsp+3E8h+var_320]; this
0x1800656cf  lea     rcx, [rsp+3E8h+var_3B0]; struct StateRepository::Cache::Manager_NoThrow *
0x1800656d4  call    ?FindByPackageFamily@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JAEAVPackageIndexIterator_NoThrow@234@@Z; StateRepository::Cache::Entity::Package_NoThrow::FindByPackageFamily(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageIndexIterator_NoThrow &)
0x1800656d9  mov     rcx, [rsp+3E8h]; this
0x1800656e1  test    eax, eax
0x1800656e3  jns     short loc_1800656F9
0x1800656e5  mov     r9d, eax; char *
0x1800656e8  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x1800656ef  mov     edx, 504h; void *
0x1800656f4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800656f9  mov     edi, [rsp+3E8h+arg_20]
0x180065700  test    edi, edi
0x180065702  jz      short loc_18006570E
0x180065704  test    dil, 1
0x180065708  jz      loc_180065D83
0x18006570e  xorps   xmm0, xmm0
0x180065711  movdqa  xmmword ptr [rsp+3E8h+var_2B8], xmm0
0x18006571a  mov     [rsp+3E8h+var_2A8], rsi
0x180065722  mov     [rsp+3E8h+var_2A0], rsi
0x18006572a  mov     [rsp+3E8h+var_298], rsi
0x180065732  mov     [rsp+3E8h+var_290], rsi
0x18006573a  mov     [rsp+3E8h+var_288], rsi
0x180065742  mov     [rsp+3E8h+var_280], rsi
0x18006574a  movdqa  [rsp+3E8h+var_278], xmm0
0x180065753  mov     [rsp+3E8h+var_268], esi
0x18006575a  mov     [rsp+3E8h+var_260], rsi
0x180065762  mov     [rsp+3E8h+var_258], rsi
0x18006576a  mov     [rsp+3E8h+var_3B8], sil
0x18006576f  lea     r9, [rsp+3E8h+var_3B8]
0x180065774  lea     r8, [rsp+3E8h+var_2B8]
0x18006577c  xor     edx, edx
0x18006577e  lea     rcx, [rsp+3E8h+var_320]
0x180065786  call    ?Get@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Package_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x18006578b  mov     rcx, [rsp+3E8h]; this
0x180065793  test    eax, eax
0x180065795  jns     short loc_1800657AB
0x180065797  mov     r9d, eax; char *
0x18006579a  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x1800657a1  mov     edx, 50Ch; void *
0x1800657a6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800657ab  cmp     [rsp+3E8h+var_3B8], sil
0x1800657b0  jz      loc_180065D72
0x1800657b6  mov     [rsp+3E8h+var_390], rsi
0x1800657bb  mov     [rsp+3E8h+var_388], esi
0x1800657bf  mov     [rsp+3E8h+var_380], rsi
0x1800657c4  lea     r8, [rsp+3E8h+var_390]; this
0x1800657c9  mov     rdx, [rsp+3E8h+var_2B8]; __int64
0x1800657d1  lea     rcx, [rsp+3E8h+var_3B0]; struct StateRepository::Cache::Manager_NoThrow *
0x1800657d6  call    ?FindByPackage@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JAEAVApplicationIndexIterator_NoThrow@234@@Z; StateRepository::Cache::Entity::Application_NoThrow::FindByPackage(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow &)
0x1800657db  mov     rcx, [rsp+3E8h]; this
0x1800657e3  test    eax, eax
0x1800657e5  jns     short loc_1800657FB
0x1800657e7  mov     r9d, eax; char *
0x1800657ea  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x1800657f1  mov     edx, 511h; void *
0x1800657f6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800657fb  xorps   xmm0, xmm0
0x1800657fe  movdqa  xmmword ptr [rsp+3E8h+var_1F8], xmm0
0x180065807  mov     [rsp+3E8h+var_1E8], rsi
0x18006580f  mov     [rsp+3E8h+var_1E0], rsi
0x180065817  movdqa  [rsp+3E8h+var_1D8], xmm0
0x180065820  xorps   xmm1, xmm1
0x180065823  movdqa  [rsp+3E8h+var_1C8], xmm1
0x18006582c  movdqa  [rsp+3E8h+var_1B8], xmm0
0x180065835  movdqa  [rsp+3E8h+var_1A8], xmm1
0x18006583e  mov     [rsp+3E8h+var_3B7+2], sil
0x180065843  lea     r9, [rsp+3E8h+var_3B7+2]
0x180065848  lea     r8, [rsp+3E8h+var_1F8]
0x180065850  xor     edx, edx
0x180065852  lea     rcx, [rsp+3E8h+var_390]
0x180065857  call    ?Get@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Application_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x18006585c  mov     rcx, [rsp+3E8h]; this
0x180065864  test    eax, eax
0x180065866  jns     short loc_18006587C
0x180065868  mov     r9d, eax; char *
0x18006586b  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180065872  mov     edx, 516h; void *
0x180065877  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006587c  cmp     [rsp+3E8h+var_3B7+2], sil
0x180065881  jz      loc_180065D02
0x180065887  mov     [rsp+3E8h+var_300], rsi
0x18006588f  mov     [rsp+3E8h+var_2F8], esi
0x180065896  mov     [rsp+3E8h+var_2F0], rsi
0x18006589e  mov     r8, [rsp+3E8h+var_1F8]; __int64
0x1800658a6  lea     rdx, [rsp+3E8h+var_3B0]; struct StateRepository::Cache::Manager_NoThrow *
0x1800658ab  lea     rcx, [rsp+3E8h+var_300]; this
0x1800658b3  call    ?OpenByApplicationAndCategory@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_JPEBG@Z; StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplicationAndCategory(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *)
0x1800658b8  mov     ebx, eax
0x1800658ba  test    eax, eax
0x1800658bc  jns     short loc_1800658DC
0x1800658be  mov     rcx, [rsp+3E8h]; this
0x1800658c6  mov     r9d, eax; char *
0x1800658c9  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800658d0  mov     edx, 3B9h; void *
0x1800658d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800658da  jmp     short loc_1800658DE
0x1800658dc  mov     ebx, esi
0x1800658de  mov     rcx, [rsp+3E8h]; this
0x1800658e6  test    ebx, ebx
0x1800658e8  jns     short loc_1800658FE
0x1800658ea  mov     r9d, ebx; char *
0x1800658ed  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x1800658f4  mov     edx, 51Bh; void *
0x1800658f9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800658fe  xorps   xmm0, xmm0
0x180065901  movdqa  xmmword ptr [rsp+3E8h+var_248], xmm0
0x18006590a  mov     [rsp+3E8h+var_238], rsi
0x180065912  mov     [rsp+3E8h+var_230], rsi
0x18006591a  movdqa  [rsp+3E8h+var_228], xmm0
0x180065923  xorps   xmm1, xmm1
0x180065926  movdqa  [rsp+3E8h+var_218], xmm1
0x18006592f  mov     [rsp+3E8h+var_208], rsi
0x180065937  mov     [rsp+3E8h+var_200], esi
0x18006593e  mov     [rsp+3E8h+var_3B7], sil
0x180065943  cmp     [rsp+3E8h+var_300], rsi
0x18006594b  jz      short loc_1800659C1
0x18006594d  mov     [rsp+3E8h+var_3A8], rsi
0x180065952  lea     rdx, [rsp+3E8h+var_3A8]; __int64 *
0x180065957  lea     rcx, [rsp+3E8h+var_300]; this
0x18006595f  call    ?Get@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEA_J@Z; StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(__int64 &)
0x180065964  mov     ebx, eax
0x180065966  test    eax, eax
0x180065968  jns     short loc_180065988
0x18006596a  mov     edx, 2ACh; void *
0x18006596f  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x180065976  mov     r9d, eax; char *
0x180065979  mov     rcx, [rsp+3E8h]; this
0x180065981  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065986  jmp     short loc_1800659C3
0x180065988  mov     rdx, [rsp+3E8h+var_3A8]
0x18006598d  test    rdx, rdx
0x180065990  jz      short loc_1800659C1
0x180065992  lea     rax, [rsp+3E8h+var_3B7]
0x180065997  mov     [rsp+3E8h+phkResult], rax
0x18006599c  lea     r9, [rsp+3E8h+var_248]
0x1800659a4  xor     r8d, r8d
0x1800659a7  mov     rcx, [rsp+3E8h+var_2F0]
0x1800659af  call    ?Get@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x1800659b4  mov     ebx, eax
0x1800659b6  test    eax, eax
0x1800659b8  jns     short loc_1800659C1
0x1800659ba  mov     edx, 2B1h
0x1800659bf  jmp     short loc_18006596F
0x1800659c1  mov     ebx, esi
0x1800659c3  mov     rcx, [rsp+3E8h]; this
0x1800659cb  test    ebx, ebx
0x1800659cd  jns     short loc_1800659E3
0x1800659cf  mov     r9d, ebx; char *
0x1800659d2  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x1800659d9  mov     edx, 520h; void *
0x1800659de  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800659e3  cmp     [rsp+3E8h+var_3B7], sil
0x1800659e8  jz      loc_180065C92
0x1800659ee  mov     [rsp+3E8h+var_370], rsi
0x1800659f3  mov     [rsp+3E8h+var_368], esi
0x1800659fa  mov     [rsp+3E8h+var_360], rsi
0x180065a02  lea     r8, [rsp+3E8h+var_370]; this
0x180065a07  mov     rdx, [rsp+3E8h+var_248]; __int64
0x180065a0f  lea     rcx, [rsp+3E8h+var_3B0]; struct StateRepository::Cache::Manager_NoThrow *
0x180065a14  call    ?FindByExtension@AppUriHandler_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JAEAVAppUriHandlerIndexIterator_NoThrow@234@@Z; StateRepository::Cache::Entity::AppUriHandler_NoThrow::FindByExtension(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::AppUriHandlerIndexIterator_NoThrow &)
0x180065a19  mov     rcx, [rsp+3E8h]; this
0x180065a21  test    eax, eax
0x180065a23  jns     short loc_180065A39
0x180065a25  mov     r9d, eax; char *
0x180065a28  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
  ... truncated ...
```
