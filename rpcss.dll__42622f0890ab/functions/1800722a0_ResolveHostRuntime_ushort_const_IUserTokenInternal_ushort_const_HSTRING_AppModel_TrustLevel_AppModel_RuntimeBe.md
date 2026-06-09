# ResolveHostRuntime(ushort const *,IUserTokenInternal *,ushort const *,HSTRING__ * *,AppModel::TrustLevel *,AppModel::RuntimeBehavior *)

- ea: `0x1800722a0`
- end: `0x1800728ce`
- name: `?ResolveHostRuntime@@YAJPEBGPEAUIUserTokenInternal@@0PEAPEAUHSTRING__@@PEAW4TrustLevel@AppModel@@PEAW4RuntimeBehavior@4@@Z`
- size: `1582`
- prototype: `int(const unsigned __int16 *, struct IUserTokenInternal *, const unsigned __int16 *, HSTRING *, enum TrustLevel *, enum AppModel::RuntimeBehavior *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007658c`

## callees

- `0x180005c40`
- `0x180020ed0`
- `0x18002ba28`
- `0x18002effc`
- `0x18002f8cc`
- `0x180041540`
- `0x180043850`
- `0x1800722a0`
- `0x1800728d4`
- `0x18007cc4c`
- `0x180093414`
- `0x180093538`
- `0x1800a2f9c`
- `0x1800adb60`
- `0x1800ccd24`
- `0x1800ccddc`
- `0x1800cd338`
- `0x1800cd418`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072330`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072330`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180072539`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800725e4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007263e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800726c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007275d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180072820`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180072539`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800725e4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007263e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800726c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007275d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180072820`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1800723ac`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1800723ac`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180072401`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180072772`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180072872`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800728a8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180072401`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180072772`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180072872`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800728a8`

## string_xrefs

- `0x180072305`: `onecore\com\combase\catalog\services.cxx`
- `0x18007236f`: `onecore\com\combase\catalog\services.cxx`
- `0x1800723de`: `onecore\com\combase\catalog\services.cxx`
- `0x1800725af`: `onecore\com\combase\catalog\services.cxx`
- `0x180072604`: `onecore\com\combase\catalog\services.cxx`
- `0x180072683`: `onecore\com\combase\catalog\services.cxx`
- `0x180072790`: `onecore\com\combase\catalog\services.cxx`
- `0x1800727c3`: `onecore\com\combase\catalog\services.cxx`
- `0x1800727f9`: `onecore\com\combase\catalog\services.cxx`
- `0x18007282c`: `onecore\com\combase\catalog\services.cxx`
- `0x18007284b`: `onecore\com\combase\catalog\services.cxx`
- `0x180072880`: `onecore\com\combase\catalog\services.cxx`
- `0x1800723c6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`
- `0x180072597`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`
- `0x1800727e1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`

## pseudocode

```c
__int64 __fastcall ResolveHostRuntime(
        const unsigned __int16 *a1,
        struct IUserTokenInternal *a2,
        unsigned __int16 *a3,
        HSTRING *a4,
        enum TrustLevel *a5,
        enum AppModel::RuntimeBehavior *a6)
{
  int FilteredStaticPackageGraphPackagesForMainPackage; // eax
  unsigned int v11; // ebx
  int FilteredPackagesForMainPackage; // eax
  int v13; // ebx
  int v14; // edi
  __int64 v15; // rcx
  char *v16; // rdi
  char *v17; // r14
  const unsigned __int16 *v18; // rdx
  int v19; // eax
  const unsigned __int16 *v20; // r9
  int v21; // esi
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 *v27; // rcx
  int v28; // eax
  __int64 v29; // rdx
  __int64 *v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 *v33; // rcx
  __int64 v34; // rcx
  int PackagedFileAbsolutePath; // eax
  __int64 v36; // rdx
  __int64 *v37; // rcx
  enum TrustLevel v38; // ecx
  __int64 v39; // rdx
  __int64 *v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // rdx
  __int64 *v44; // rcx
  unsigned int v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
  int v48; // [rsp+20h] [rbp-E0h]
  int v49; // [rsp+20h] [rbp-E0h]
  bool v50[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v51; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v52[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v53; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v54; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v55; // [rsp+58h] [rbp-A8h]
  HSTRING v56; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID lpMem; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v58; // [rsp+70h] [rbp-90h] BYREF
  __int64 v59; // [rsp+78h] [rbp-88h] BYREF
  __int64 v60[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v61; // [rsp+90h] [rbp-70h]
  __int64 v62; // [rsp+98h] [rbp-68h]
  __int128 v63; // [rsp+A0h] [rbp-60h]
  __int128 v64; // [rsp+B0h] [rbp-50h]
  __int128 v65; // [rsp+C0h] [rbp-40h] BYREF
  int v66; // [rsp+D0h] [rbp-30h]
  __int64 v67; // [rsp+D8h] [rbp-28h]
  unsigned __int16 *v68[2]; // [rsp+E0h] [rbp-20h]
  __int128 v69; // [rsp+F0h] [rbp-10h]
  __int64 v70; // [rsp+100h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  lpMem = 0;
  v58 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
  {
    FilteredStaticPackageGraphPackagesForMainPackage = GetFilteredStaticPackageGraphPackagesForMainPackage(
                                                         a2,
                                                         a3,
                                                         0x200000u);
    v11 = FilteredStaticPackageGraphPackagesForMainPackage;
    if ( FilteredStaticPackageGraphPackagesForMainPackage < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC0B,
        (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
        (const char *)(unsigned int)FilteredStaticPackageGraphPackagesForMainPackage,
        v46);
      return v11;
    }
  }
  else
  {
    wil::unique_any_array_ptr<PACKAGE_INFO,PrivMemDeleter,wil::empty_deleter,unsigned __int64>::reset(&lpMem);
    FilteredPackagesForMainPackage = GetFilteredPackagesForMainPackage(
                                       a2,
                                       a3,
                                       0x200000u,
                                       &v58,
                                       (struct PACKAGE_INFO **)&lpMem);
    v11 = FilteredPackagesForMainPackage;
    if ( FilteredPackagesForMainPackage < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC10,
        (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
        (const char *)(unsigned int)FilteredPackagesForMainPackage,
        v46);
      goto LABEL_73;
    }
  }
  v51 = 0;
  v13 = 1;
  v53 = &v51;
  LOBYTE(v55) = 1;
  v54 = 0;
  v14 = SRCacheManager_Open(0, &v54);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v53);
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      (const char *)(unsigned int)v14,
      v46);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC14,
      (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
      (const char *)(unsigned int)v14,
      v47);
    v15 = v51;
    v51 = 0;
    goto LABEL_8;
  }
  v16 = (char *)lpMem;
  v17 = (char *)lpMem + 80 * v58;
  while ( 1 )
  {
    if ( v16 == v17 )
    {
      v11 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xC66,
              (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
              (const char *)0x490,
              v46);
LABEL_70:
      v34 = v51;
      v51 = 0;
LABEL_71:
      if ( v34 )
        SRCacheManager_Close();
      goto LABEL_73;
    }
    v18 = (const unsigned __int16 *)*((_QWORD *)v16 + 2);
    v59 = 0;
    v19 = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
            (struct StateRepository::Cache::Manager_NoThrow *)&v51,
            v18,
            &v59);
    v21 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC1A,
        (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
        (const char *)(unsigned int)v19,
        v46);
      goto LABEL_65;
    }
    if ( !v59 )
    {
      v11 = -2147023728;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC1B,
        (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
        (const char *)0x80070490LL,
        v46);
      goto LABEL_70;
    }
    v53 = 0;
    LODWORD(v54) = 0;
    v55 = 0;
    v21 = StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow::OpenByPackageAndCategory(
            (StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow *)&v53,
            (struct StateRepository::Cache::Manager_NoThrow *)&v51,
            v59,
            v20);
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x391,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
        (const char *)(unsigned int)v21,
        v46);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC20,
        (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
        (const char *)(unsigned int)v21,
        v49);
LABEL_61:
      v44 = v53;
      v53 = 0;
      if ( v44 )
        SRCacheContext_Close(v44, v43);
LABEL_65:
      v31 = v51;
      v51 = 0;
LABEL_66:
      if ( v31 )
        SRCacheManager_Close();
      v11 = v21;
      goto LABEL_73;
    }
    v61 = 0;
    *(_OWORD *)v60 = 0;
    v63 = 0;
    v64 = 0;
    v62 = 0;
    v52[0] = 0;
    v21 = StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow::Get(&v53, v22, v60, v52);
    if ( v21 < 0 )
    {
      v25 = 3108;
LABEL_59:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
        (const char *)(unsigned int)v21,
        v46);
      StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow((StateRepository::Cache::Entity::PackageExtension_NoThrow *)v60);
      goto LABEL_61;
    }
LABEL_17:
    if ( v52[0] )
      break;
    StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow((StateRepository::Cache::Entity::PackageExtension_NoThrow *)v60);
    v27 = v53;
    v53 = 0;
    if ( v27 )
      SRCacheContext_Close(v27, v26);
    v16 += 80;
  }
  v50[0] = 0;
  v21 = StateRepository::Cache::Entity::HostRuntime_NoThrow::ExistsByHostIdAndPackageExtension(
          (struct StateRepository::Cache::Manager_NoThrow *)&v51,
          a1,
          v60[0],
          v50);
  if ( v21 < 0 )
  {
    v25 = 3114;
    goto LABEL_59;
  }
  if ( !v50[0] )
  {
    LODWORD(v54) = v54 + 1;
    v21 = StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow::Get(&v53, v23, v60, v52);
    if ( v21 < 0 )
    {
      v25 = 3170;
      goto LABEL_59;
    }
    goto LABEL_17;
  }
  v50[0] = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  *(_OWORD *)v68 = 0;
  v69 = 0;
  v70 = 0;
  v28 = StateRepository::Cache::Entity::Activation_NoThrow::Get(&v51, v63, v24, &v65);
  v21 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32F,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
      (const char *)(unsigned int)v28,
      (int)v50);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC30,
      (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
      (const char *)(unsigned int)v21,
      v48);
    StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow((StateRepository::Cache::Entity::Activation_NoThrow *)&v65);
    StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow((StateRepository::Cache::Entity::PackageExtension_NoThrow *)v60);
    v30 = v53;
    v53 = 0;
    if ( v30 )
      SRCacheContext_Close(v30, v29);
    v31 = v51;
    v51 = 0;
    goto LABEL_66;
  }
  if ( !v50[0] )
  {
    v11 = -2147023728;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC31,
      (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
      (const char *)0x80070490LL,
      (int)v50);
LABEL_31:
    StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow((StateRepository::Cache::Entity::Activation_NoThrow *)&v65);
    StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow((StateRepository::Cache::Entity::PackageExtension_NoThrow *)v60);
    v33 = v53;
    v53 = 0;
    if ( v33 )
      SRCacheContext_Close(v33, v32);
    v34 = v51;
    v51 = 0;
    goto LABEL_71;
  }
  v56 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    &v56,
    0);
  PackagedFileAbsolutePath = GetPackagedFileAbsolutePath(a2, *((const char **)v16 + 2), v68[0], &v56);
  v14 = PackagedFileAbsolutePath;
  if ( PackagedFileAbsolutePath >= 0 )
  {
    if ( (v66 & 0x80u) == 0 )
    {
      if ( (v66 & 4) == 0 )
      {
        v42 = 3138;
        goto LABEL_56;
      }
      v38 = PartialTrust;
    }
    else
    {
      v38 = BaseTrust;
    }
    if ( (v66 & 0x100) != 0 )
    {
      v13 = 0;
LABEL_49:
      *a4 = v56;
      v56 = 0;
      *a5 = v38;
      *(_DWORD *)a6 = v13;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v56);
      StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow((StateRepository::Cache::Entity::Activation_NoThrow *)&v65);
      StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow((StateRepository::Cache::Entity::PackageExtension_NoThrow *)v60);
      v40 = v53;
      v53 = 0;
      if ( v40 )
        SRCacheContext_Close(v40, v39);
      v41 = v51;
      v51 = 0;
      if ( v41 )
        SRCacheManager_Close();
      v11 = 0;
      goto LABEL_73;
    }
    if ( (v66 & 0x10) != 0 )
      goto LABEL_49;
    if ( (v66 & 0x20) != 0 )
    {
      v13 = 2;
      goto LABEL_49;
    }
    if ( (v66 & 0x200) != 0 )
    {
      v13 = 3;
      goto LABEL_49;
    }
    v42 = 3160;
LABEL_56:
    v11 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v42,
      (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
      (const char *)0x8000FFFFLL,
      (int)v50);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v56);
    goto LABEL_31;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC35,
    (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
    (const char *)(unsigned int)PackagedFileAbsolutePath,
    (int)v50);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v56);
  StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow((StateRepository::Cache::Entity::Activation_NoThrow *)&v65);
  StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow((StateRepository::Cache::Entity::PackageExtension_NoThrow *)v60);
  v37 = v53;
  v53 = 0;
  if ( v37 )
    SRCacheContext_Close(v37, v36);
  v15 = v51;
  v51 = 0;
LABEL_8:
  if ( v15 )
    SRCacheManager_Close();
  v11 = v14;
LABEL_73:
  wil::unique_any_array_ptr<PACKAGE_INFO,PrivMemDeleter,wil::empty_deleter,unsigned __int64>::reset(&lpMem);
  return v11;
}

```

## disassembly

```asm
0x1800722a0  push    rbp
0x1800722a2  push    rbx
0x1800722a3  push    rsi
0x1800722a4  push    rdi
0x1800722a5  push    r12
0x1800722a7  push    r13
0x1800722a9  push    r14
0x1800722ab  push    r15
0x1800722ad  lea     rbp, [rsp-18h]
0x1800722b2  sub     rsp, 118h
0x1800722b9  xor     esi, esi
0x1800722bb  mov     r13, r9
0x1800722be  mov     [rsp+150h+lpMem], rsi
0x1800722c3  mov     rbx, r8
0x1800722c6  mov     [rsp+150h+var_E0], rsi
0x1800722cb  mov     r15, rdx
0x1800722ce  mov     r12, rcx
0x1800722d1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800722d8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800722dd  test    al, al
0x1800722df  jz      short loc_18007233B
0x1800722e1  lea     r9, [rsp+150h+lpMem]
0x1800722e6  mov     r8d, 200000h
0x1800722ec  mov     rdx, rbx
0x1800722ef  mov     rcx, r15
0x1800722f2  call    ?GetFilteredStaticPackageGraphPackagesForMainPackage@@YAJPEAUIUserTokenInternal@@PEBGIAEAV?$unique_any_array_ptr@UPACKAGE_INFO@@UPrivMemDeleter@@Uempty_deleter@wil@@_K@wil@@@Z; GetFilteredStaticPackageGraphPackagesForMainPackage(IUserTokenInternal *,ushort const *,uint,wil::unique_any_array_ptr<PACKAGE_INFO,PrivMemDeleter,wil::empty_deleter,unsigned __int64> &)
0x1800722f7  mov     ebx, eax
0x1800722f9  test    eax, eax
0x1800722fb  jns     loc_180072388
0x180072301  mov     rcx, [rbp+58h]; this
0x180072305  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18007230c  mov     r9d, eax; char *
0x18007230f  mov     edx, 0C0Bh; void *
0x180072314  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072319  mov     r8, [rsp+150h+lpMem]; lpMem
0x18007231e  test    r8, r8
0x180072321  jz      loc_1800728B8
0x180072327  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18007232e  xor     edx, edx; dwFlags
0x180072330  call    cs:__imp_HeapFree
0x180072336  jmp     loc_1800728B8
0x18007233b  lea     rcx, [rsp+150h+lpMem]
0x180072340  call    ?reset@?$unique_any_array_ptr@UPACKAGE_INFO@@UPrivMemDeleter@@Uempty_deleter@wil@@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<PACKAGE_INFO,PrivMemDeleter,wil::empty_deleter,unsigned __int64>::reset(void)
0x180072345  lea     rax, [rsp+150h+lpMem]
0x18007234a  mov     r8d, 200000h; unsigned int
0x180072350  lea     r9, [rsp+150h+var_E0]; unsigned __int64 *
0x180072355  mov     qword ptr [rsp+150h+var_130], rax; int
0x18007235a  mov     rdx, rbx; unsigned __int16 *
0x18007235d  mov     rcx, r15; struct IUserTokenInternal *
0x180072360  call    ?GetFilteredPackagesForMainPackage@@YAJPEAUIUserTokenInternal@@PEBGIPEA_KPEAPEAUPACKAGE_INFO@@@Z; GetFilteredPackagesForMainPackage(IUserTokenInternal *,ushort const *,uint,unsigned __int64 *,PACKAGE_INFO * *)
0x180072365  mov     ebx, eax
0x180072367  test    eax, eax
0x180072369  jns     short loc_180072388
0x18007236b  mov     rcx, [rbp+58h]; this
0x18007236f  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x180072376  mov     r9d, eax; char *
0x180072379  mov     edx, 0C10h; void *
0x18007237e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072383  jmp     loc_1800728AE
0x180072388  lea     rax, [rsp+150h+var_118]
0x18007238d  mov     [rsp+150h+var_118], rsi
0x180072392  mov     ebx, 1
0x180072397  mov     [rsp+150h+var_108], rax
0x18007239c  lea     rdx, [rsp+150h+var_100]
0x1800723a1  mov     byte ptr [rsp+150h+var_F8], bl
0x1800723a5  xor     ecx, ecx
0x1800723a7  mov     [rsp+150h+var_100], rsi
0x1800723ac  call    cs:__imp_SRCacheManager_Open
0x1800723b2  lea     rcx, [rsp+150h+var_108]
0x1800723b7  mov     edi, eax
0x1800723b9  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x1800723be  test    edi, edi
0x1800723c0  jns     short loc_18007240E
0x1800723c2  mov     rcx, [rbp+58h]; this
0x1800723c6  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800723cd  mov     r9d, edi; char *
0x1800723d0  mov     edx, 0A5h; void *
0x1800723d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800723da  mov     rcx, [rbp+58h]; this
0x1800723de  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x1800723e5  mov     r9d, edi; char *
0x1800723e8  mov     edx, 0C14h; void *
0x1800723ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800723f2  mov     rcx, [rsp+150h+var_118]
0x1800723f7  mov     [rsp+150h+var_118], rsi
0x1800723fc  test    rcx, rcx
0x1800723ff  jz      short loc_180072407
0x180072401  call    cs:__imp_SRCacheManager_Close
0x180072407  mov     ebx, edi
0x180072409  jmp     loc_1800728AE
0x18007240e  mov     rax, [rsp+150h+var_E0]
0x180072413  mov     rdi, [rsp+150h+lpMem]
0x180072418  lea     r14, [rax+rax*4]
0x18007241c  shl     r14, 4
0x180072420  add     r14, rdi
0x180072423  cmp     rdi, r14
0x180072426  jz      loc_18007287C
0x18007242c  mov     rdx, [rdi+10h]; unsigned __int16 *
0x180072430  lea     r8, [rsp+150h+var_D8]; __int64 *
0x180072435  lea     rcx, [rsp+150h+var_118]; struct StateRepository::Cache::Manager_NoThrow *
0x18007243a  mov     [rsp+150h+var_D8], rsi
0x18007243f  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x180072444  mov     esi, eax
0x180072446  test    eax, eax
0x180072448  js      loc_180072847
0x18007244e  mov     r8, [rsp+150h+var_D8]; __int64
0x180072453  xor     esi, esi
0x180072455  test    r8, r8
0x180072458  jz      loc_180072828
0x18007245e  lea     rdx, [rsp+150h+var_118]; struct StateRepository::Cache::Manager_NoThrow *
0x180072463  mov     [rsp+150h+var_108], rsi
0x180072468  lea     rcx, [rsp+150h+var_108]; this
0x18007246d  mov     dword ptr [rsp+150h+var_100], esi
0x180072471  mov     [rsp+150h+var_F8], rsi
0x180072476  call    ?OpenByPackageAndCategory@PackageExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_JPEBG@Z; StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow::OpenByPackageAndCategory(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *)
0x18007247b  mov     esi, eax
0x18007247d  xor     eax, eax
0x18007247f  test    esi, esi
0x180072481  js      loc_1800727DD
0x180072487  xorps   xmm0, xmm0
0x18007248a  mov     [rbp+50h+var_C0], rax
0x18007248e  xorps   xmm1, xmm1
0x180072491  movdqa  xmmword ptr [rbp+50h+var_D0], xmm0
0x180072496  lea     r9, [rsp+150h+var_110]
0x18007249b  movdqa  [rbp+50h+var_B0], xmm0
0x1800724a0  lea     r8, [rbp+50h+var_D0]
0x1800724a4  movdqa  [rbp+50h+var_A0], xmm1
0x1800724a9  lea     rcx, [rsp+150h+var_108]
0x1800724ae  mov     [rbp+50h+var_B8], rax
0x1800724b2  mov     [rsp+150h+var_110], al
0x1800724b6  call    ?Get@PackageExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@PackageExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::PackageExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExtension_NoThrow &,bool &)
0x1800724bb  mov     esi, eax
0x1800724bd  test    eax, eax
0x1800724bf  js      loc_1800727BA
0x1800724c5  xor     esi, esi
0x1800724c7  cmp     [rsp+150h+var_110], sil
0x1800724cc  jz      short loc_180072521
0x1800724ce  mov     r8, [rbp+50h+var_D0]; __int64
0x1800724d2  lea     r9, [rsp+150h+var_120]; bool *
0x1800724d7  mov     rdx, r12; unsigned __int16 *
0x1800724da  mov     [rsp+150h+var_120], sil
0x1800724df  lea     rcx, [rsp+150h+var_118]; struct StateRepository::Cache::Manager_NoThrow *
0x1800724e4  call    ?ExistsByHostIdAndPackageExtension@HostRuntime_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBG_JAEA_N@Z; StateRepository::Cache::Entity::HostRuntime_NoThrow::ExistsByHostIdAndPackageExtension(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64,bool &)
0x1800724e9  mov     esi, eax
0x1800724eb  test    eax, eax
0x1800724ed  js      loc_1800727B3
0x1800724f3  cmp     [rsp+150h+var_120], 0
0x1800724f8  jnz     short loc_180072548
0x1800724fa  add     dword ptr [rsp+150h+var_100], ebx
0x1800724fe  lea     r9, [rsp+150h+var_110]
0x180072503  lea     r8, [rbp+50h+var_D0]
0x180072507  lea     rcx, [rsp+150h+var_108]
0x18007250c  call    ?Get@PackageExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@PackageExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::PackageExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExtension_NoThrow &,bool &)
0x180072511  mov     esi, eax
0x180072513  test    eax, eax
0x180072515  jns     short loc_1800724C5
0x180072517  mov     edx, 0C62h
0x18007251c  jmp     loc_1800727BF
0x180072521  lea     rcx, [rbp+50h+var_D0]; this
0x180072525  call    ??1PackageExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(void)
0x18007252a  mov     rcx, [rsp+150h+var_108]
0x18007252f  mov     [rsp+150h+var_108], rsi
0x180072534  test    rcx, rcx
0x180072537  jz      short loc_18007253F
0x180072539  call    cs:__imp_SRCacheContext_Close
0x18007253f  add     rdi, 50h ; 'P'
0x180072543  jmp     loc_180072423
0x180072548  mov     rdx, qword ptr [rbp+50h+var_B0]
0x18007254c  lea     rax, [rsp+150h+var_120]
0x180072551  xor     r14d, r14d
0x180072554  mov     qword ptr [rsp+150h+var_130], rax; int
0x180072559  xorps   xmm0, xmm0
0x18007255c  mov     [rsp+150h+var_120], r14b
0x180072561  xorps   xmm1, xmm1
0x180072564  movdqa  [rbp+50h+var_90], xmm0
0x180072569  lea     r9, [rbp+50h+var_90]
0x18007256d  mov     [rbp+50h+var_80], r14d
0x180072571  lea     rcx, [rsp+150h+var_118]
0x180072576  mov     [rbp+50h+var_78], r14
0x18007257a  movdqa  xmmword ptr [rbp+50h+var_70], xmm0
0x18007257f  movdqa  [rbp+50h+var_60], xmm1
0x180072584  mov     [rbp+50h+var_50], r14
0x180072588  call    ?Get@Activation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Activation_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Activation_NoThrow::CacheFlags,StateRepository::Cache::Entity::Activation_NoThrow &,bool &)
0x18007258d  mov     esi, eax
0x18007258f  test    eax, eax
0x180072591  jns     short loc_1800725F9
0x180072593  mov     rcx, [rbp+58h]; this
0x180072597  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007259e  mov     r9d, eax; char *
0x1800725a1  mov     edx, 32Fh; void *
0x1800725a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800725ab  mov     rcx, [rbp+58h]; this
0x1800725af  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x1800725b6  mov     r9d, esi; char *
0x1800725b9  mov     edx, 0C30h; void *
0x1800725be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800725c3  lea     rcx, [rbp+50h+var_90]; this
0x1800725c7  call    ??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)
0x1800725cc  lea     rcx, [rbp+50h+var_D0]; this
0x1800725d0  call    ??1PackageExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(void)
0x1800725d5  mov     rcx, [rsp+150h+var_108]
0x1800725da  mov     [rsp+150h+var_108], r14
0x1800725df  test    rcx, rcx
0x1800725e2  jz      short loc_1800725EA
0x1800725e4  call    cs:__imp_SRCacheContext_Close
0x1800725ea  mov     rcx, [rsp+150h+var_118]
0x1800725ef  mov     [rsp+150h+var_118], r14
0x1800725f4  jmp     loc_18007286D
0x1800725f9  cmp     [rsp+150h+var_120], r14b
0x1800725fe  jnz     short loc_180072653
0x180072600  mov     rcx, [rbp+58h]; this
0x180072604  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18007260b  mov     ebx, 80070490h
0x180072610  mov     edx, 0C31h; void *
0x180072615  mov     r9d, ebx; char *
0x180072618  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007261d  lea     rcx, [rbp+50h+var_90]; this
0x180072621  call    ??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)
0x180072626  lea     rcx, [rbp+50h+var_D0]; this
0x18007262a  call    ??1PackageExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(void)
0x18007262f  mov     rcx, [rsp+150h+var_108]
0x180072634  mov     [rsp+150h+var_108], r14
0x180072639  test    rcx, rcx
0x18007263c  jz      short loc_180072644
0x18007263e  call    cs:__imp_SRCacheContext_Close
0x180072644  mov     rcx, [rsp+150h+var_118]
0x180072649  mov     [rsp+150h+var_118], r14
0x18007264e  jmp     loc_1800728A3
0x180072653  xor     edx, edx
0x180072655  mov     [rsp+150h+var_F0], r14
0x18007265a  lea     rcx, [rsp+150h+var_F0]
0x18007265f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180072664  mov     r8, [rbp+50h+var_70]; unsigned __int16 *
0x180072668  lea     r9, [rsp+150h+var_F0]; HSTRING *
0x18007266d  mov     rdx, [rdi+10h]; unsigned __int16 *
0x180072671  mov     rcx, r15; struct IUserTokenInternal *
0x180072674  call    ?GetPackagedFileAbsolutePath@@YAJPEAUIUserTokenInternal@@PEBG1PEAPEAUHSTRING__@@@Z; GetPackagedFileAbsolutePath(IUserTokenInternal *,ushort const *,ushort const *,HSTRING__ * *)
0x180072679  mov     edi, eax
0x18007267b  test    eax, eax
0x18007267d  jns     short loc_1800726D7
0x18007267f  mov     rcx, [rbp+58h]; this
0x180072683  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18007268a  mov     r9d, eax; char *
0x18007268d  mov     edx, 0C35h; void *
0x180072692  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072697  lea     rcx, [rsp+150h+var_F0]
0x18007269c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x1800726a1  lea     rcx, [rbp+50h+var_90]; this
0x1800726a5  call    ??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)
0x1800726aa  lea     rcx, [rbp+50h+var_D0]; this
0x1800726ae  call    ??1PackageExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(void)
0x1800726b3  mov     rcx, [rsp+150h+var_108]
0x1800726b8  mov     [rsp+150h+var_108], r14
0x1800726bd  test    rcx, rcx
0x1800726c0  jz      short loc_1800726C8
0x1800726c2  call    cs:__imp_SRCacheContext_Close
0x1800726c8  mov     rcx, [rsp+150h+var_118]
0x1800726cd  mov     [rsp+150h+var_118], r14
0x1800726d2  jmp     loc_1800723FC
0x1800726d7  mov     eax, [rbp+50h+var_80]
0x1800726da  test    al, al
0x1800726dc  jns     short loc_1800726E3
0x1800726de  mov     ecx, r14d
0x1800726e1  jmp     short loc_1800726ED
0x1800726e3  test    al, 4
0x1800726e5  jz      loc_180072787
0x1800726eb  mov     ecx, ebx
0x1800726ed  bt      eax, 8
0x1800726f1  jnb     short loc_1800726F8
0x1800726f3  mov     ebx, r14d
0x1800726f6  jmp     short loc_180072712
0x1800726f8  test    al, 10h
0x1800726fa  jnz     short loc_180072712
0x1800726fc  test    al, 20h
0x1800726fe  jz      short loc_180072707
0x180072700  mov     ebx, 2
0x180072705  jmp     short loc_180072712
0x180072707  bt      eax, 9
0x18007270b  jnb     short loc_180072780
0x18007270d  mov     ebx, 3
0x180072712  mov     rax, [rsp+150h+var_F0]
0x180072717  mov     [r13+0], rax
0x18007271b  mov     rax, [rbp+50h+arg_20]
0x180072722  mov     [rsp+150h+var_F0], r14
0x180072727  mov     [rax], ecx
0x180072729  lea     rcx, [rsp+150h+var_F0]
0x18007272e  mov     rax, [rbp+50h+arg_28]
0x180072735  mov     [rax], ebx
0x180072737  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x18007273c  lea     rcx, [rbp+50h+var_90]; this
0x180072740  call    ??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)
0x180072745  lea     rcx, [rbp+50h+var_D0]; this
0x180072749  call    ??1PackageExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(void)
0x18007274e  mov     rcx, [rsp+150h+var_108]
0x180072753  mov     [rsp+150h+var_108], r14
0x180072758  test    rcx, rcx
0x18007275b  jz      short loc_180072763
0x18007275d  call    cs:__imp_SRCacheContext_Close
0x180072763  mov     rcx, [rsp+150h+var_118]
0x180072768  mov     [rsp+150h+var_118], r14
  ... truncated ...
```
