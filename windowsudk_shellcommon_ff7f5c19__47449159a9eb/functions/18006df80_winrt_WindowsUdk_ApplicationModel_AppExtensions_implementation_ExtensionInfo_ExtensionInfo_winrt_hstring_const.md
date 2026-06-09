# winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::ExtensionInfo(winrt::hstring const &,SRAppExtensionData const &)

- ea: `0x18006df80`
- end: `0x18006ea7d`
- name: `??0ExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@QEAA@AEBUhstring@5@AEBUSRAppExtensionData@@@Z`
- size: `2813`
- prototype: `__int64 __fastcall(winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo *__hidden this, const struct winrt::hstring *, const struct SRAppExtensionData *)`
- caller_count: `1`
- callee_count: `46`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006def0`

## callees

- `0x18000b428`
- `0x18000c314`
- `0x18000c55c`
- `0x180011e64`
- `0x180013490`
- `0x180021c00`
- `0x180024e14`
- `0x180025064`
- `0x180025c4c`
- `0x180026480`
- `0x180026760`
- `0x18002677c`
- `0x18002a054`
- `0x180035814`
- `0x1800375a4`
- `0x1800377b0`
- `0x180037bc4`
- `0x1800469e8`
- `0x180053f7c`
- `0x18005b8a0`
- `0x18005edb0`
- `0x18006df80`
- `0x180072740`
- `0x180074b70`
- `0x1800795e4`
- `0x1800d971c`
- `0x1800d97d0`
- `0x1800da8ec`
- `0x1800dab80`
- `0x180108890`
- `0x18010e284`
- `0x18015cb00`
- `0x18015cfa0`
- `0x18015d850`
- `0x18015d868`
- `0x1802a036c`
- `0x1802b2314`
- `0x1802b2b70`
- `0x1802b3bcc`
- `0x1802b6de8`
- `0x1802b7258`
- `0x1802ba578`
- `0x1802ba5b4`
- `0x1802ba5f0`
- `0x1802ba62c`
- `0x1804a2010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006e98c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006e98c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18006ea15`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18006ea15`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x18006e2e2`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x18006e2e2`

## string_xrefs

- `0x18006ea6b`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\ExtensionCache_impl.h`
- `0x18006e9d0`: `%s\AppxManifest.xml`
- `0x18006e9f8`: `%s\AppxBlockMap.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo *__fastcall winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::ExtensionInfo(
        winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo *this,
        const struct winrt::hstring *a2,
        const struct SRAppExtensionData *a3)
{
  char **v5; // r14
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  bool v11; // zf
  int v12; // ebx
  int v13; // eax
  int v14; // ebx
  int v15; // ebx
  int v16; // ebx
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // r8
  std::filesystem::path *v22; // rax
  char *v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // r8
  char *v28; // rdx
  unsigned int EffectivePackageStatusForUser; // eax
  int v30; // r8d
  unsigned int v31; // edx
  unsigned int v32; // eax
  int v33; // edx
  unsigned int v34; // edx
  unsigned int v35; // edx
  unsigned int v36; // edx
  unsigned int v37; // edx
  unsigned int v38; // edx
  unsigned int v39; // edx
  unsigned int v40; // edx
  unsigned int v41; // edx
  _QWORD *v42; // rax
  int v43; // ebx
  int v44; // ebx
  int v45; // ebx
  int v46; // ebx
  int v47; // ebx
  int v48; // ebx
  int v49; // ebx
  int v50; // ebx
  int v51; // ebx
  int v52; // ebx
  int v53; // ebx
  int v54; // ebx
  _QWORD *v55; // rax
  int v56; // eax
  winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo *v57; // rax
  const struct std::nothrow_t *v58; // rdx
  void **v59; // rbx
  void *v60; // rcx
  char IsEnabled; // al
  struct IInspectableVtbl *v62; // rbx
  __int64 v63; // rax
  int v64; // ecx
  __int64 v65; // rax
  int v66; // eax
  void (__fastcall ***v67)(_QWORD, __int64 *, void **); // rcx
  void *v68; // rbx
  struct IInspectableVtbl *lpVtbl; // rcx
  struct IInspectable *v70; // rbx
  struct IInspectable *v71; // rsi
  const WCHAR *v72; // rcx
  char v73; // al
  const WCHAR *v74; // rcx
  int v75; // eax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  __int64 v78; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v79[2]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v80[32]; // [rsp+48h] [rbp-B8h] BYREF
  void *v81[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v82; // [rsp+78h] [rbp-88h] BYREF
  IInspectable v83; // [rsp+80h] [rbp-80h] BYREF
  int v84; // [rsp+88h] [rbp-78h] BYREF
  struct IInspectable *v85; // [rsp+90h] [rbp-70h] BYREF
  int v86; // [rsp+98h] [rbp-68h]
  _BYTE v87[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v88[32]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR pszPath[264]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+248h]

  v79[1] = this;
  *(_QWORD *)this = 0;
  std::wstring::wstring((char *)this + 8, a2);
  std::wstring::wstring((char *)this + 40);
  std::wstring::wstring((char *)this + 72);
  std::wstring::wstring((char *)this + 104);
  std::wstring::wstring((char *)this + 136);
  v5 = (char **)((char *)this + 168);
  std::wstring::wstring((char *)this + 168);
  std::wstring::wstring((char *)this + 200);
  std::wstring::wstring((char *)this + 232);
  std::wstring::wstring((char *)this + 264);
  std::wstring::wstring((char *)this + 296);
  std::wstring::wstring((char *)this + 328);
  *((_QWORD *)this + 45) = 0;
  *((_DWORD *)this + 92) = 0;
  *(_QWORD *)((char *)this + 372) = 0;
  *(_QWORD *)((char *)this + 380) = 0;
  *((_BYTE *)this + 396) = 0;
  *((_BYTE *)this + 404) = 0;
  *((_QWORD *)this + 51) = 0;
  *((_QWORD *)this + 52) = 0;
  *((_QWORD *)this + 53) = 0;
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>((char *)this + 432);
  *((_DWORD *)this + 112) = 0;
  *((_QWORD *)this + 57) = 0;
  *((_QWORD *)this + 58) = 0;
  *((_QWORD *)this + 59) = 0;
  *((_QWORD *)this + 60) = 0;
  *((_QWORD *)this + 61) = 0;
  *((_QWORD *)this + 62) = 0;
  *((_QWORD *)this + 63) = 0;
  *((_DWORD *)this + 129) = 1;
  *((_DWORD *)this + 130) = 256;
  *((_WORD *)this + 262) = 0;
  *((_QWORD *)this + 66) = 0;
  v6 = *(_QWORD *)a3;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(v6 + 2 * v7) );
  std::wstring::_Assign<wchar_t>((char *)this + 40, v6, v7);
  *((_QWORD *)this + 45) = *((_QWORD *)a3 + 6);
  v8 = *((_DWORD *)a3 + 14);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_61119654>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_61119654>::GetImpl'::`2'::impl) )
  {
    v9 = v8 - 2;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        v12 = v10 - 2;
        v11 = v12 == 0;
        goto LABEL_7;
      }
LABEL_12:
      v13 = 3;
      goto LABEL_18;
    }
LABEL_17:
    v13 = 4;
    goto LABEL_18;
  }
  v14 = v8 - 2;
  if ( !v14 )
    goto LABEL_17;
  v15 = v14 - 1;
  if ( !v15 )
    goto LABEL_12;
  v16 = v15 - 1;
  if ( !v16 )
    goto LABEL_11;
  v12 = v16 - 1;
  v11 = v12 == 0;
LABEL_7:
  if ( v11 )
  {
LABEL_11:
    v13 = 1;
    goto LABEL_18;
  }
  if ( v12 == 1 )
    v13 = 2;
  else
    v13 = 0;
LABEL_18:
  *((_DWORD *)this + 94) = v13;
  v17 = *((_QWORD *)a3 + 4);
  *((_QWORD *)this + 46) = v17;
  v18 = *((_QWORD *)a3 + 3);
  v19 = -1;
  do
    ++v19;
  while ( *(_WORD *)(v18 + 2 * v19) );
  std::wstring::_Assign<wchar_t>((char *)this + 168, v18, v19);
  v20 = *((_QWORD *)a3 + 5);
  v21 = -1;
  do
    ++v21;
  while ( *(_WORD *)(v20 + 2 * v21) );
  std::wstring::_Assign<wchar_t>((char *)this + 264, v20, v21);
  v22 = (std::filesystem::path *)std::wstring::wstring(&v85, (char *)this + 168);
  *((_DWORD *)this + 95) = GetPackageType(v22);
  if ( *((_QWORD *)this + 24) <= 7u )
    v23 = (char *)this + 168;
  else
    v23 = *v5;
  PackageFamilyNameAndPublisherIdFromPackageFullName(v87, v23);
  std::wstring::operator=((char *)this + 136, v87);
  std::wstring::operator=((char *)this + 104, v88);
  v24 = *((_QWORD *)a3 + 1);
  if ( v24 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *(_WORD *)(v24 + 2 * v25) );
    std::wstring::_Assign<wchar_t>((char *)this + 296, v24, v25);
  }
  v26 = *((_QWORD *)a3 + 2);
  if ( v26 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *(_WORD *)(v26 + 2 * v27) );
    std::wstring::_Assign<wchar_t>((char *)this + 328, v26, v27);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_61119654>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_61119654>::GetImpl'::`2'::impl) )
  {
    if ( winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::g_unsignedPackagePresent
      || *((_DWORD *)this + 94) )
    {
      goto LABEL_40;
    }
  }
  else if ( winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::g_unsignedPackagePresent
         || *((_DWORD *)this + 94) != 1 )
  {
    goto LABEL_40;
  }
  winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::g_unsignedPackagePresent = 1;
LABEL_40:
  v84 = 0;
  if ( *((_QWORD *)this + 24) <= 7u )
    v28 = (char *)this + 168;
  else
    v28 = *v5;
  EffectivePackageStatusForUser = GetEffectivePackageStatusForUser(0, v28, &v84);
  if ( EffectivePackageStatusForUser )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x26D,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\ExtensionCache_impl.h",
      (const char *)EffectivePackageStatusForUser,
      bIgnoreCase);
  v30 = v84;
  if ( (v84 & 0x80u) == 0 )
    *((_DWORD *)this + 96) &= ~1u;
  else
    *((_DWORD *)this + 96) |= 1u;
  v31 = *((_DWORD *)this + 96) | 0x100;
  if ( (v30 & 0x10) == 0 )
    v31 = *((_DWORD *)this + 96) & 0xFFFFFEFF;
  v32 = v31 & 0xFFFFFFFD;
  v33 = v31 | 2;
  if ( (v30 & 0x40) == 0 )
    v33 = v32;
  *((_DWORD *)this + 96) = v33;
  if ( (v30 & 0x20) != 0 )
    v34 = v33 | 4;
  else
    v34 = v33 & 0xFFFFFFFB;
  *((_DWORD *)this + 96) = v34;
  if ( (v30 & 8) != 0 )
    v35 = v34 | 8;
  else
    v35 = v34 & 0xFFFFFFF7;
  *((_DWORD *)this + 96) = v35;
  if ( (v30 & 1) != 0 )
    v36 = v35 | 0x10;
  else
    v36 = v35 & 0xFFFFFFEF;
  *((_DWORD *)this + 96) = v36;
  if ( (v30 & 0x4000302) != 0 )
    v37 = v36 | 0x20;
  else
    v37 = v36 & 0xFFFFFFDF;
  *((_DWORD *)this + 96) = v37;
  if ( (v30 & 0x4000307) != 0 )
    v38 = v37 | 0x40;
  else
    v38 = v37 & 0xFFFFFFBF;
  *((_DWORD *)this + 96) = v38;
  if ( (v30 & 0x98) != 0 )
    v39 = v38 | 0x80;
  else
    v39 = v38 & 0xFFFFFF7F;
  *((_DWORD *)this + 96) = v39;
  if ( (v30 & 0x81020) != 0 )
    v40 = v39 | 0x200;
  else
    v40 = v39 & 0xFFFFFDFF;
  *((_DWORD *)this + 96) = v40;
  if ( (v30 & 4) != 0 )
    v41 = v40 | 0x400;
  else
    v41 = v40 & 0xFFFFFBFF;
  *((_DWORD *)this + 96) = v41;
  v78 = 0;
  v42 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::operator->(
                    &v78,
                    v81);
  std::wstring::operator=(*v42 + 272LL, (char *)this + 168);
  tip2::test_data_control<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::~test_data_control<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>(v81);
  v43 = *((_DWORD *)this + 96);
  *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::operator->(
                           &v78,
                           v81)
            + 304LL) = v43;
  tip2::test_data_control<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::~test_data_control<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>(v81);
  v44 = *((_DWORD *)this + 96) & 1;
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::operator->(
                          &v78,
                          v81)
           + 308LL) = v44;
  tip2::test_data_control<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::~test_data_control<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>(v81);
  v45 = *((_DWORD *)this + 96);
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::operator->(
                          &v78,
                          v81)
           + 309LL) = (v45 & 0x100) != 0;
  tip2::test_data_control<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::~test_data_control<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>(v81);
  v46 = *((_DWORD *)this + 96);
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::operator->(
                          &v78,
                          v81)
           + 310LL) = (v46 & 2) != 0;
  tip2::test_data_control<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::~test_data_control<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>(v81);
  v47 = *((_DWORD *)this + 96);
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::operator->(
                          &v78,
                          v81)
           + 311LL) = (v47 & 4) != 0;
  tip2::test_data_control<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::~test_data_control<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>(v81);
  v48 = *((_DWORD *)this + 96);
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::operator->(
                          &v78,
                          v81)
           + 312LL) = (v48 & 8) != 0;
  tip2::test_data_control<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::~test_data_control<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>(v81);
  v49 = *((_DWORD *)this + 96);
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::operator->(
                          &v78,
                          v81)
           + 313LL) = (v49 & 0x10) != 0;
  tip2::test_data_control<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::~test_data_control<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>(v81);
  v50 = *((_DWORD *)this + 96);
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::operator->(
                          &v78,
                          v81)
           + 314LL) = (v50 & 0x20) != 0;
  tip2::test_data_control<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::~test_data_control<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>(v81);
  v51 = *((_DWORD *)this + 96);
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::operator->(
                          &v78,
                          v81)
           + 315LL) = (v51 & 0x40) != 0;
  tip2::test_data_control<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::~test_data_control<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>(v81);
  v52 = *((_DWORD *)this + 96);
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::operator->(
                          &v78,
                          v81)
           + 316LL) = (v52 & 0x80) != 0;
  tip2::test_data_control<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::~test_data_control<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>(v81);
  v53 = *((_DWORD *)this + 96);
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::operator->(
                          &v78,
                          v81)
           + 317LL) = (v53 & 0x200) != 0;
  tip2::test_data_control<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::~test_data_control<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>(v81);
  v54 = *((_DWORD *)this + 96);
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::operator->(
                          &v78,
                          v81)
           + 318LL) = (v54 & 0x400) != 0;
  tip2::test_data_control<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::~test_data_control<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>(v81);
  if ( v78 && (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started(v78 + 8) )
    wil::com_ptr_t<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>,wil::err_returncode_policy>::reset(&v78);
  v55 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::ensure_data(&v78);
  tip2::details::shared_data<0,0,0>::start(*v55 + 8LL, &v85);
  if ( v78 )
    tip2::details::shared_data<0,0,0>::complete_without_lock(v78 + 8);
  v56 = *((_DWORD *)a3 + 15);
  *((_DWORD *)this + 112) = v56;
  if ( v56 )
  {
    v57 = (winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo *)std::make_unique<unsigned char [0],0>(
                                                                                                 v81,
                                                                                                 *((unsigned int *)a3
                                                                                                 + 15));
    v59 = (void **)((char *)this + 456);
    if ( (winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo *)((char *)this + 456) != v57 )
    {
      v58 = *(const struct std::nothrow_t **)v57;
      *(_QWORD *)v57 = 0;
      v60 = *v59;
      *v59 = v58;
      if ( v60 )
        operator delete(v60, v58);
    }
    if ( v81[0] )
      operator delete(v81[0], v58);
    memcpy_0(*v59, *((const void **)a3 + 8), *((unsigned int *)a3 + 15));
    winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::GetExtensionProperties(this, v79);
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_60689272>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60689272>::GetImpl'::`2'::impl);
    v62 = (struct IInspectableVtbl *)v79[0];
    v83.lpVtbl = (struct IInspectableVtbl *)v79[0];
    if ( IsEnabled )
    {
      winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ModalDialog>::add_ref(&v83);
      v63 = winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::LookupVelocityId(
              v81,
              &v83);
      if ( *(_BYTE *)(v63 + 4) )
      {
        v64 = *(_DWORD *)v63;
        if ( !*((_BYTE *)this + 404) )
          *((_BYTE *)this + 404) = 1;
        *((_DWORD *)this + 100) = v64;
      }
      else
      {
        *((_BYTE *)this + 404) = 0;
      }
    }
    else
    {
      winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ModalDialog>::add_ref(&v83);
      v65 = winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::LookupVelocityProperties(
              v81,
              &v83);
      if ( *(_BYTE *)(v65 + 8) )
      {
        *((_DWORD *)this + 97) = *(_DWORD *)v65;
        v66 = *(_DWORD *)(v65 + 4);
        if ( !*((_BYTE *)this + 396) )
          *((_BYTE *)this + 396) = 1;
        *((_DWORD *)this + 98) = v66;
      }
      else
      {
        *((_BYTE *)this + 396) = 0;
      }
    }
    v83.lpVtbl = v62;
    winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ModalDialog>::add_ref(&v83);
    *((_BYTE *)this + 521) = winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::LookupMdmPolicyProperties(&v83);
    winrt::param::hstring::hstring((winrt::param::hstring *)&v85, L"ApiContracts");
    v67 = *(void (__fastcall ****)(_QWORD, __int64 *, void **))winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::TryLookup(
                                                                 v79,
                                                                 &v82,
                                                                 &v85);
    v81[0] = 0;
    if ( v67 )
    {
      (**v67)(v67, &winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IPropertySet>, v81);
      v68 = v81[0];
    }
    else
    {
      v68 = 0;
    }
    if ( v82 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v82);
    if ( v68 )
    {
      winrt::param::hstring::hstring((winrt::param::hstring *)v80, L"ApiContract");
      winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::TryLookup(
        v81,
        &v83,
        v80);
      lpVtbl = v83.lpVtbl;
      if ( v83.lpVtbl )
      {
        v82 = 0;
        (*(void (__fastcall **)(struct IInspectableVtbl *, __int64 *, __int64 *))v83.lpVtbl->QueryInterface)(
          v83.lpVtbl,
          &winrt::impl::guid_v<winrt::Windows::Foundation::IPropertyValue>,
          &v82);
        if ( v82
          && (unsigned int)winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::Type(&v82) == 1037 )
        {
          v85 = 0;
          v86 = 0;
          winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetInspectableArray(
            &v82,
            &v85);
          v70 = v85;
          v71 = &v85[v86];
          while ( v70 != v71 )
            winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::AddContract(this, v70++);
          winrt::com_array<winrt::Windows::Foundation::IInspectable>::clear(&v85);
        }
        else
        {
          winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::AddContract(this, &v83);
        }
        winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v82);
        lpVtbl = v83.lpVtbl;
      }
      if ( lpVtbl )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v83);
    }
    winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)v81);
    winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)v79);
  }
  winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::LoadPackageMetadata(this);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59821427>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59821427>::GetImpl'::`2'::impl) )
  {
    v72 = (const WCHAR *)((char *)this + 168);
    if ( *((_QWORD *)this + 24) > 7u )
      v72 = *(const WCHAR **)v72;
    v73 = winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::DetermineIfIsUndockedFlightingPackage(v72)
        & 1;
    *((_BYTE *)this + 523) = v73;
    *((_BYTE *)this + 522) = v73;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_52940282>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_52940282>::GetImpl'::`2'::impl) )
  {
    v74 = (const WCHAR *)((char *)this + 136);
    if ( *((_QWORD *)this + 20) > 7u )
      v74 = *(const WCHAR **)v74;
    if ( CompareStringOrdinal(v74, -1, L"MicrosoftWindows.Client.CoPilot_cw5n1h2txyewy", -1, 1) == 2 )
      *((_BYTE *)this + 522) = 1;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58937533>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58937533>::GetImpl'::`2'::impl) )
  {
    memset_0(pszPath, 0, 0x208u);
    if ( *((_DWORD *)this + 94) > 1u )
    {
      v75 = StringCchPrintfW(pszPath, 0x104u, L"%s\\AppxBlockMap.xml");
      goto LABEL_129;
    }
  }
  else
  {
    memset_0(pszPath, 0, 0x208u);
  }
  v75 = StringCchPrintfW(pszPath, 0x104u, L"%s\\AppxManifest.xml");
LABEL_129:
  if ( v75 >= 0 && !PathFileExistsW(pszPath) )
    *((_BYTE *)this + 522) = 1;
  wil::com_ptr_t<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>,wil::err_returncode_policy>(&v78);
  std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(v87);
  return this;
}

```

## disassembly

```asm
0x18006df80  mov     [rsp-8+arg_18], rbx
0x18006df85  push    rbp
0x18006df86  push    rsi
0x18006df87  push    rdi
0x18006df88  push    r12
0x18006df8a  push    r13
0x18006df8c  push    r14
0x18006df8e  push    r15
0x18006df90  lea     rbp, [rsp-210h]
0x18006df98  sub     rsp, 310h
0x18006df9f  mov     rax, cs:__security_cookie
0x18006dfa6  xor     rax, rsp
0x18006dfa9  mov     [rbp+240h+var_40], rax
0x18006dfb0  mov     rsi, r8
0x18006dfb3  mov     rdi, rcx
0x18006dfb6  mov     [rsp+340h+var_300], rcx
0x18006dfbb  xor     eax, eax
0x18006dfbd  mov     [rcx], rax
0x18006dfc0  add     rcx, 8
0x18006dfc4  call    ??$?0Uhstring@winrt@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBUhstring@winrt@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(winrt::hstring const &,std::allocator<wchar_t> const &)
0x18006dfc9  nop
0x18006dfca  lea     rcx, [rdi+28h]
0x18006dfce  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18006dfd3  nop
0x18006dfd4  lea     rcx, [rdi+48h]
0x18006dfd8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18006dfdd  nop
0x18006dfde  lea     rcx, [rdi+68h]
0x18006dfe2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18006dfe7  nop
0x18006dfe8  lea     rcx, [rdi+88h]
0x18006dfef  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18006dff4  nop
0x18006dff5  lea     r14, [rdi+0A8h]
0x18006dffc  mov     rcx, r14
0x18006dfff  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18006e004  nop
0x18006e005  lea     rcx, [rdi+0C8h]
0x18006e00c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18006e011  nop
0x18006e012  lea     rcx, [rdi+0E8h]
0x18006e019  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18006e01e  nop
0x18006e01f  lea     r12, [rdi+108h]
0x18006e026  mov     rcx, r12
0x18006e029  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18006e02e  nop
0x18006e02f  lea     rcx, [rdi+128h]
0x18006e036  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18006e03b  nop
0x18006e03c  lea     rcx, [rdi+148h]
0x18006e043  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18006e048  nop
0x18006e049  xor     r15d, r15d
0x18006e04c  mov     [rdi+168h], r15
0x18006e053  mov     [rdi+170h], r15d
0x18006e05a  mov     [rdi+174h], r15
0x18006e061  mov     [rdi+17Ch], r15
0x18006e068  mov     [rdi+18Ch], r15b
0x18006e06f  mov     [rdi+194h], r15b
0x18006e076  mov     [rdi+198h], r15
0x18006e07d  mov     [rdi+1A0h], r15
0x18006e084  mov     [rdi+1A8h], r15
0x18006e08b  lea     rcx, [rdi+1B0h]
0x18006e092  call    ??0?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@AEBU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(std::less<std::wstring> const &)
0x18006e097  nop
0x18006e098  mov     [rdi+1C0h], r15d
0x18006e09f  mov     [rdi+1C8h], r15
0x18006e0a6  mov     [rdi+1D0h], r15
0x18006e0ad  mov     [rdi+1D8h], r15
0x18006e0b4  mov     [rdi+1E0h], r15
0x18006e0bb  mov     [rdi+1E8h], r15
0x18006e0c2  mov     [rdi+1F0h], r15
0x18006e0c9  mov     [rdi+1F8h], r15
0x18006e0d0  mov     dword ptr [rdi+204h], 1
0x18006e0da  mov     dword ptr [rdi+208h], 100h
0x18006e0e4  mov     [rdi+20Ch], r15w
0x18006e0ec  mov     [rdi+210h], r15
0x18006e0f3  mov     rdx, [rsi]
0x18006e0f6  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006e0fa  inc     r8
0x18006e0fd  cmp     [rdx+r8*2], r15w
0x18006e102  jnz     short loc_18006E0FA
0x18006e104  lea     rcx, [rdi+28h]
0x18006e108  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18006e10d  mov     ecx, [rsi+34h]
0x18006e110  shl     rcx, 20h
0x18006e114  mov     eax, [rsi+30h]
0x18006e117  or      rcx, rax
0x18006e11a  mov     [rdi+168h], rcx
0x18006e121  mov     ebx, [rsi+38h]
0x18006e124  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_61119654@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_61119654@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61119654> `wil::Feature<__WilFeatureTraits_Feature_61119654>::GetImpl(void)'::`2'::impl
0x18006e12b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_61119654@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61119654>::__private_IsEnabled(void)
0x18006e130  mov     ecx, 4
0x18006e135  lea     r15d, [rcx-2]
0x18006e139  test    al, al
0x18006e13b  jz      short loc_18006E16A
0x18006e13d  sub     ebx, r15d
0x18006e140  jz      short loc_18006E17E
0x18006e142  sub     ebx, 1
0x18006e145  jz      short loc_18006E163
0x18006e147  sub     ebx, r15d
0x18006e14a  jz      short loc_18006E15C
0x18006e14c  cmp     ebx, 1
0x18006e14f  jz      short loc_18006E157
0x18006e151  xor     ebx, ebx
0x18006e153  mov     eax, ebx
0x18006e155  jmp     short loc_18006E182
0x18006e157  mov     eax, r15d
0x18006e15a  jmp     short loc_18006E180
0x18006e15c  mov     eax, 1
0x18006e161  jmp     short loc_18006E180
0x18006e163  mov     eax, 3
0x18006e168  jmp     short loc_18006E180
0x18006e16a  sub     ebx, r15d
0x18006e16d  jz      short loc_18006E17E
0x18006e16f  sub     ebx, 1
0x18006e172  jz      short loc_18006E163
0x18006e174  sub     ebx, 1
0x18006e177  jz      short loc_18006E15C
0x18006e179  sub     ebx, 1
0x18006e17c  jmp     short loc_18006E14A
0x18006e17e  mov     eax, ecx
0x18006e180  xor     ebx, ebx
0x18006e182  mov     [rdi+178h], eax
0x18006e188  mov     rax, [rsi+20h]
0x18006e18c  mov     rcx, rax
0x18006e18f  shr     rcx, 30h
0x18006e193  mov     [rdi+176h], cx
0x18006e19a  mov     rcx, rax
0x18006e19d  shr     rcx, 20h
0x18006e1a1  mov     [rdi+174h], cx
0x18006e1a8  mov     rcx, rax
0x18006e1ab  shr     rcx, 10h
0x18006e1af  mov     [rdi+172h], cx
0x18006e1b6  mov     [rdi+170h], ax
0x18006e1bd  mov     rdx, [rsi+18h]
0x18006e1c1  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006e1c5  inc     r8
0x18006e1c8  cmp     [rdx+r8*2], bx
0x18006e1cd  jnz     short loc_18006E1C5
0x18006e1cf  mov     rcx, r14
0x18006e1d2  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18006e1d7  mov     rdx, [rsi+28h]
0x18006e1db  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006e1df  inc     r8
0x18006e1e2  cmp     [rdx+r8*2], bx
0x18006e1e7  jnz     short loc_18006E1DF
0x18006e1e9  mov     rcx, r12
0x18006e1ec  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18006e1f1  mov     rdx, r14
0x18006e1f4  lea     rcx, [rbp+240h+var_2B0]
0x18006e1f8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006e1fd  mov     rcx, rax; this
0x18006e200  call    ?GetPackageType@@YA?AW4PackageType@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; GetPackageType(std::wstring)
0x18006e205  mov     [rdi+17Ch], eax
0x18006e20b  cmp     qword ptr [r14+18h], 7
0x18006e210  jbe     short loc_18006E217
0x18006e212  mov     rdx, [r14]
0x18006e215  jmp     short loc_18006E21A
0x18006e217  mov     rdx, r14
0x18006e21a  lea     rcx, [rbp+240h+var_290]
0x18006e21e  call    ?PackageFamilyNameAndPublisherIdFromPackageFullName@@YA?AU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEB_W@Z; PackageFamilyNameAndPublisherIdFromPackageFullName(wchar_t const *)
0x18006e223  nop
0x18006e224  lea     rdx, [rbp+240h+var_290]
0x18006e228  lea     rcx, [rdi+88h]
0x18006e22f  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18006e234  lea     rdx, [rbp+240h+var_270]
0x18006e238  lea     rcx, [rdi+68h]
0x18006e23c  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18006e241  mov     rdx, [rsi+8]
0x18006e245  xor     r12d, r12d
0x18006e248  or      r13, 0FFFFFFFFFFFFFFFFh
0x18006e24c  test    rdx, rdx
0x18006e24f  jz      short loc_18006E26A
0x18006e251  mov     r8, r13
0x18006e254  inc     r8
0x18006e257  cmp     [rdx+r8*2], r12w
0x18006e25c  jnz     short loc_18006E254
0x18006e25e  lea     rcx, [rdi+128h]
0x18006e265  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18006e26a  mov     rdx, [rsi+10h]
0x18006e26e  test    rdx, rdx
0x18006e271  jz      short loc_18006E28C
0x18006e273  mov     r8, r13
0x18006e276  inc     r8
0x18006e279  cmp     [rdx+r8*2], r12w
0x18006e27e  jnz     short loc_18006E276
0x18006e280  lea     rcx, [rdi+148h]
0x18006e287  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18006e28c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_61119654@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_61119654@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61119654> `wil::Feature<__WilFeatureTraits_Feature_61119654>::GetImpl(void)'::`2'::impl
0x18006e293  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_61119654@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61119654>::__private_IsEnabled(void)
0x18006e298  test    al, al
0x18006e29a  jz      short loc_18006E2B0
0x18006e29c  cmp     cs:?g_unsignedPackagePresent@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@3_NA, r12b; bool winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::g_unsignedPackagePresent
0x18006e2a3  jnz     short loc_18006E2C9
0x18006e2a5  cmp     [rdi+178h], r12d
0x18006e2ac  jz      short loc_18006E2C2
0x18006e2ae  jmp     short loc_18006E2C9
0x18006e2b0  cmp     cs:?g_unsignedPackagePresent@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@3_NA, r12b; bool winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::g_unsignedPackagePresent
0x18006e2b7  jnz     short loc_18006E2C9
0x18006e2b9  cmp     dword ptr [rdi+178h], 1
0x18006e2c0  jnz     short loc_18006E2C9
0x18006e2c2  mov     cs:?g_unsignedPackagePresent@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@3_NA, 1; bool winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::g_unsignedPackagePresent
0x18006e2c9  mov     [rbp+240h+var_2B8], r12d
0x18006e2cd  cmp     qword ptr [r14+18h], 7
0x18006e2d2  jbe     short loc_18006E2D9
0x18006e2d4  mov     rdx, [r14]
0x18006e2d7  jmp     short loc_18006E2DC
0x18006e2d9  mov     rdx, r14
0x18006e2dc  lea     r8, [rbp+240h+var_2B8]
0x18006e2e0  xor     ecx, ecx
0x18006e2e2  call    cs:__imp_GetEffectivePackageStatusForUser
0x18006e2e8  mov     rcx, [rbp+248h]; this
0x18006e2ef  test    eax, eax
0x18006e2f1  jnz     loc_18006EA68
0x18006e2f7  mov     r8d, [rbp+240h+var_2B8]
0x18006e2fb  test    r8b, r8b
0x18006e2fe  jns     short loc_18006E309
0x18006e300  or      dword ptr [rdi+180h], 1
0x18006e307  jmp     short loc_18006E310
0x18006e309  and     dword ptr [rdi+180h], 0FFFFFFFEh
0x18006e310  mov     edx, [rdi+180h]
0x18006e316  mov     eax, edx
0x18006e318  btr     eax, 8
0x18006e31c  bts     edx, 8
0x18006e320  test    r8b, 10h
0x18006e324  cmovz   edx, eax
0x18006e327  mov     eax, edx
0x18006e329  and     eax, 0FFFFFFFDh
0x18006e32c  or      edx, r15d
0x18006e32f  test    r8b, 40h
0x18006e333  cmovz   edx, eax
0x18006e336  mov     [rdi+180h], edx
0x18006e33c  test    r8b, 20h
0x18006e340  jz      short loc_18006E347
0x18006e342  or      edx, 4
0x18006e345  jmp     short loc_18006E34A
0x18006e347  and     edx, 0FFFFFFFBh
0x18006e34a  mov     [rdi+180h], edx
0x18006e350  test    r8b, 8
0x18006e354  jz      short loc_18006E35B
0x18006e356  or      edx, 8
0x18006e359  jmp     short loc_18006E35E
0x18006e35b  and     edx, 0FFFFFFF7h
0x18006e35e  mov     [rdi+180h], edx
0x18006e364  test    r8b, 1
0x18006e368  jz      short loc_18006E36F
0x18006e36a  or      edx, 10h
0x18006e36d  jmp     short loc_18006E372
0x18006e36f  and     edx, 0FFFFFFEFh
0x18006e372  mov     [rdi+180h], edx
0x18006e378  test    r8d, 4000302h
0x18006e37f  jz      short loc_18006E386
0x18006e381  or      edx, 20h
0x18006e384  jmp     short loc_18006E389
0x18006e386  and     edx, 0FFFFFFDFh
0x18006e389  mov     [rdi+180h], edx
0x18006e38f  test    r8d, 4000307h
0x18006e396  jz      short loc_18006E39D
0x18006e398  or      edx, 40h
0x18006e39b  jmp     short loc_18006E3A0
0x18006e39d  and     edx, 0FFFFFFBFh
0x18006e3a0  mov     [rdi+180h], edx
0x18006e3a6  test    r8b, 98h
0x18006e3aa  jz      short loc_18006E3B2
0x18006e3ac  bts     edx, 7
0x18006e3b0  jmp     short loc_18006E3B6
0x18006e3b2  btr     edx, 7
0x18006e3b6  mov     [rdi+180h], edx
0x18006e3bc  test    r8d, 81020h
0x18006e3c3  jz      short loc_18006E3CB
0x18006e3c5  bts     edx, 9
0x18006e3c9  jmp     short loc_18006E3CF
0x18006e3cb  btr     edx, 9
0x18006e3cf  mov     [rdi+180h], edx
0x18006e3d5  test    r8b, 4
0x18006e3d9  jz      short loc_18006E3E1
0x18006e3db  bts     edx, 0Ah
0x18006e3df  jmp     short loc_18006E3E5
0x18006e3e1  btr     edx, 0Ah
0x18006e3e5  mov     [rdi+180h], edx
0x18006e3eb  mov     [rsp+340h+var_310], r12
0x18006e3f0  lea     rdx, [rsp+340h+var_2D8]
0x18006e3f5  lea     rcx, [rsp+340h+var_310]
0x18006e3fa  call    ??C?$tip_test@V?$merged_data@U_tip_ExtensionCachePackageStateTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ExtensionCachePackageStateTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::operator->(void)
0x18006e3ff  nop
0x18006e400  mov     rcx, [rax]
0x18006e403  add     rcx, 110h
0x18006e40a  mov     rdx, r14
0x18006e40d  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18006e412  nop
0x18006e413  lea     rcx, [rsp+340h+var_2D8]
0x18006e418  call    ??1?$test_data_control@V?$merged_data@U_tip_ExtensionCachePackageStateTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::~test_data_control<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>(void)
0x18006e41d  mov     ebx, [rdi+180h]
0x18006e423  lea     rdx, [rsp+340h+var_2D8]
0x18006e428  lea     rcx, [rsp+340h+var_310]
0x18006e42d  call    ??C?$tip_test@V?$merged_data@U_tip_ExtensionCachePackageStateTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ExtensionCachePackageStateTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ExtensionCachePackageStateTest,_tip_ExtensionCachePackageStateTest>>::operator->(void)
0x18006e432  mov     rcx, [rax]
0x18006e435  mov     [rcx+130h], ebx
  ... truncated ...
```
