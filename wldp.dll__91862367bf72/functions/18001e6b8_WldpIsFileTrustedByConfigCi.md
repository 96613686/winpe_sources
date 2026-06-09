# WldpIsFileTrustedByConfigCi

- ea: `0x18001e6b8`
- end: `0x18001f030`
- name: `WldpIsFileTrustedByConfigCi`
- size: `2424`
- prototype: `__int64 __fastcall(unsigned __int64, __int64, __int64, __int64, _QWORD *, unsigned int *, _OWORD *, _BYTE *)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, loader_planting`

## callers

- `0x180015118`
- `0x18001e1d4`

## callees

- `0x180018918`
- `0x180018950`
- `0x18001898c`
- `0x18001e6b8`
- `0x18001f038`
- `0x18001f0b4`
- `0x18001f3fc`
- `0x18001f414`
- `0x18001f8c4`
- `0x180021ec0`
- `0x180022a10`
- `0x18002b90c`
- `0x18002c09c`
- `0x18002c0e4`
- `0x18002c9d4`
- `0x18002d870`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e938`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e94e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ea6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ea85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eb7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eb93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ecdf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ecf5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ee5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ee79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001efc4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001efde`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e938`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e94e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ea6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ea85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eb7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eb93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ecdf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ecf5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ee5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ee79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001efc4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001efde`
- `WINTRUST!WTConfigCiFreePrivateData` at `0x18001e7ac`
- `WINTRUST!WTConfigCiFreePrivateData` at `0x18001e970`
- `WINTRUST!WTConfigCiFreePrivateData` at `0x18001eaa2`
- `WINTRUST!WTConfigCiFreePrivateData` at `0x18001ebb0`
- `WINTRUST!WTConfigCiFreePrivateData` at `0x18001ed12`
- `WINTRUST!WTConfigCiFreePrivateData` at `0x18001ee96`
- `WINTRUST!WTConfigCiFreePrivateData` at `0x18001effb`
- `WINTRUST!WTConfigCiFreePrivateData` at `0x18001e7ac`
- `WINTRUST!WTConfigCiFreePrivateData` at `0x18001e970`
- `WINTRUST!WTConfigCiFreePrivateData` at `0x18001eaa2`
- `WINTRUST!WTConfigCiFreePrivateData` at `0x18001ebb0`
- `WINTRUST!WTConfigCiFreePrivateData` at `0x18001ed12`
- `WINTRUST!WTConfigCiFreePrivateData` at `0x18001ee96`
- `WINTRUST!WTConfigCiFreePrivateData` at `0x18001effb`

## string_xrefs

- `0x18001e87e`: `onecore\base\ngscb\wldp\dll\filetrust.cpp`
- `0x18001ec25`: `onecore\base\ngscb\wldp\dll\filetrust.cpp`
- `0x18001eeba`: `onecore\base\ngscb\wldp\dll\filetrust.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WldpIsFileTrustedByConfigCi(
        unsigned __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        unsigned int *a6,
        _OWORD *a7,
        _BYTE *a8)
{
  int v10; // ebx
  int v11; // r8d
  int IsEmbedSignatureTrusted; // ebx
  HLOCAL v13; // rcx
  HLOCAL v14; // rcx
  const char *v15; // r9
  __int64 result; // rax
  int v17; // r8d
  HLOCAL v18; // rcx
  HLOCAL v19; // rcx
  unsigned int v20; // esi
  HLOCAL v21; // rcx
  HLOCAL v22; // rcx
  int IsCatalogSignatureTrusted; // eax
  unsigned int v24; // ebx
  HLOCAL v25; // rcx
  HLOCAL v26; // rcx
  unsigned __int128 v27; // kr10_16
  unsigned int v28; // edi
  HLOCAL v29; // rcx
  HLOCAL v30; // rcx
  HLOCAL v31; // rcx
  HLOCAL v32; // rcx
  int v33; // [rsp+20h] [rbp-228h]
  int v34; // [rsp+20h] [rbp-228h]
  int v35; // [rsp+50h] [rbp-1F8h] BYREF
  unsigned __int128 v36; // [rsp+58h] [rbp-1F0h] BYREF
  __int64 v37; // [rsp+68h] [rbp-1E0h]
  HLOCAL hMem; // [rsp+70h] [rbp-1D8h]
  HLOCAL v39; // [rsp+78h] [rbp-1D0h]
  __int128 v40; // [rsp+80h] [rbp-1C8h] BYREF
  __int64 v41; // [rsp+90h] [rbp-1B8h]
  unsigned int v42; // [rsp+98h] [rbp-1B0h] BYREF
  __int64 v43; // [rsp+A0h] [rbp-1A8h] BYREF
  unsigned int v44; // [rsp+A8h] [rbp-1A0h] BYREF
  int v45; // [rsp+ACh] [rbp-19Ch]
  __int64 v46; // [rsp+B0h] [rbp-198h] BYREF
  unsigned __int64 v47; // [rsp+B8h] [rbp-190h]
  __int64 v48; // [rsp+C0h] [rbp-188h]
  __int128 v49; // [rsp+C8h] [rbp-180h] BYREF
  __int64 v50; // [rsp+D8h] [rbp-170h]
  __int64 v51; // [rsp+E0h] [rbp-168h]
  __int128 v52; // [rsp+E8h] [rbp-160h] BYREF
  __int64 *v53; // [rsp+F8h] [rbp-150h] BYREF
  __int64 v54; // [rsp+100h] [rbp-148h] BYREF
  char v55; // [rsp+108h] [rbp-140h]
  _DWORD v56[60]; // [rsp+110h] [rbp-138h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  v50 = a3;
  v48 = a2;
  v10 = a1;
  v47 = a1;
  v45 = 0;
  try
  {
    v46 = 0;
    v44 = 0;
    v49 = 0;
    v42 = 0;
    v52 = 0;
    LOBYTE(v35) = 0;
    memset_0(v56, 0, 0xE8u);
    v56[0] = 232;
    v43 = 0;
    v39 = 0;
    hMem = 0;
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(&v40);
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(&v36);
    WTConfigCiFreePrivateData(v56);
    memset_0(v56, 0, 0xE8u);
    v56[0] = 232;
    v53 = &v43;
    v54 = 0;
    v55 = 1;
    v45 = 1;
    LOBYTE(v11) = 1;
    IsEmbedSignatureTrusted = WldpIsEmbedSignatureTrusted(
                                v10,
                                v48,
                                v11,
                                (unsigned int)&v44,
                                (__int64)&v35,
                                (__int64)&v49,
                                (__int64)&v54,
                                (__int64)v56);
    v45 = 0;
    wil::details::out_param_t_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_______::_out_param_t_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_______(&v53);
    if ( IsEmbedSignatureTrusted < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B4,
        (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\filetrust.cpp",
        (const char *)(unsigned int)IsEmbedSignatureTrusted,
        v33);
      if ( (_QWORD)v36 )
      {
        std::_Destroy_range_std::allocator_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_________(
          v36,
          *((_QWORD *)&v36 + 1));
        std::_Deallocate<16>(v36, (v37 - v36) & 0xFFFFFFFFFFFFFFF8uLL);
        v36 = 0;
        v37 = 0;
      }
      if ( (_QWORD)v40 )
      {
        std::_Destroy_range_std::allocator_wil::unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE______WTConfigCiFreePrivateData_void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_____noexcept__NewProviderData_____(
          v40,
          *((_QWORD *)&v40 + 1));
        std::_Deallocate<16>(v40, 8 * ((v41 - (__int64)v40) >> 3));
        v40 = 0;
        v41 = 0;
      }
      v13 = hMem;
      hMem = 0;
      if ( v13 )
        LocalFree(v13);
      v14 = v39;
      v39 = 0;
      if ( v14 )
        LocalFree(v14);
      if ( v43 )
        WldpFreeStateData();
      WTConfigCiFreePrivateData(v56);
      return (unsigned int)IsEmbedSignatureTrusted;
    }
    std::vector_wil::unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE______WTConfigCiFreePrivateData_void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_____noexcept__NewProviderData__std::allocator_wil::unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE______WTConfigCiFreePrivateData_void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_____noexcept__NewProviderData_____::emplace_back_wil::unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE______WTConfigCiFreePrivateData_void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_____noexcept__NewProviderData___(
      a4,
      v56);
    std::vector_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t______std::allocator_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_________::emplace_back_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_______(
      a3,
      &v43);
    if ( (_BYTE)v35 )
    {
      *a7 = v49;
      *a6 = v44;
      *a5 = 0;
      *a8 = 1;
      if ( (_QWORD)v36 )
      {
        std::_Destroy_range_std::allocator_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_________(
          v36,
          *((_QWORD *)&v36 + 1));
        std::_Deallocate<16>(v36, (v37 - v36) & 0xFFFFFFFFFFFFFFF8uLL);
        v36 = 0;
        v37 = 0;
      }
      if ( (_QWORD)v40 )
      {
        std::_Destroy_range_std::allocator_wil::unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE______WTConfigCiFreePrivateData_void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_____noexcept__NewProviderData_____(
          v40,
          *((_QWORD *)&v40 + 1));
        std::_Deallocate<16>(v40, 8 * ((v41 - (__int64)v40) >> 3));
        v40 = 0;
        v41 = 0;
      }
      v18 = hMem;
      hMem = 0;
      if ( v18 )
        LocalFree(v18);
      v19 = v39;
      v39 = 0;
      if ( v19 )
        LocalFree(v19);
LABEL_73:
      wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_____::_unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_____(&v43);
      WTConfigCiFreePrivateData(v56);
      return 0;
    }
    v20 = v44;
    if ( v44 == 1 )
    {
      *a7 = v49;
      *a6 = 1;
      *a5 = 0;
      *a8 = 1;
      if ( (_QWORD)v36 )
      {
        std::_Destroy_range_std::allocator_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_________(
          v36,
          *((_QWORD *)&v36 + 1));
        std::_Deallocate<16>(v36, (v37 - v36) & 0xFFFFFFFFFFFFFFF8uLL);
        v36 = 0;
        v37 = 0;
      }
      if ( (_QWORD)v40 )
      {
        std::_Destroy_range_std::allocator_wil::unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE______WTConfigCiFreePrivateData_void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_____noexcept__NewProviderData_____(
          v40,
          *((_QWORD *)&v40 + 1));
        std::_Deallocate<16>(v40, 8 * ((v41 - (__int64)v40) >> 3));
        v40 = 0;
        v41 = 0;
      }
      v21 = hMem;
      hMem = 0;
      if ( v21 )
        LocalFree(v21);
      v22 = v39;
      v39 = 0;
      if ( v22 )
        LocalFree(v22);
      goto LABEL_73;
    }
    LOBYTE(v17) = 1;
    IsCatalogSignatureTrusted = WldpIsCatalogSignatureTrusted(
                                  v47,
                                  v48,
                                  v17,
                                  (unsigned int)&v36,
                                  a4,
                                  (__int64)&v46,
                                  (__int64)&v42,
                                  (__int64)&v35,
                                  (__int64)&v52);
    v24 = IsCatalogSignatureTrusted;
    if ( IsCatalogSignatureTrusted >= 0 )
    {
      v27 = v36;
      v47 = *((_QWORD *)&v36 + 1);
      if ( *((_QWORD *)&v36 + 1) == (_QWORD)v36 )
      {
        v28 = v20;
        v42 = v20;
        LOBYTE(v35) = 0;
      }
      else
      {
        v28 = v42;
      }
      v51 = v36;
      while ( (_QWORD)v27 != *((_QWORD *)&v27 + 1) )
      {
        std::vector_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t______std::allocator_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_________::emplace_back_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_______(
          v50,
          v27);
        v51 = v27 + 8;
        v27 = __PAIR128__(v47, (__int64)v27 + 8);
      }
      if ( v28 == 1 )
      {
        *a7 = v52;
        *a6 = 1;
        *a5 = v46 + 1;
        *a8 = 0;
        if ( (_QWORD)v36 )
        {
          std::_Destroy_range_std::allocator_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_________(
            v36,
            *((_QWORD *)&v36 + 1));
          std::_Deallocate<16>(v36, (v37 - v36) & 0xFFFFFFFFFFFFFFF8uLL);
          v36 = 0;
          v37 = 0;
        }
        if ( (_QWORD)v40 )
        {
          std::_Destroy_range_std::allocator_wil::unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE______WTConfigCiFreePrivateData_void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_____noexcept__NewProviderData_____(
            v40,
            *((_QWORD *)&v40 + 1));
          std::_Deallocate<16>(v40, 8 * ((v41 - (__int64)v40) >> 3));
          v40 = 0;
          v41 = 0;
        }
        v29 = hMem;
        hMem = 0;
        if ( v29 )
          LocalFree(v29);
        v30 = v39;
        v39 = 0;
        if ( v30 )
          LocalFree(v30);
      }
      else
      {
        if ( v28 != v20 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x3F5,
            (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\filetrust.cpp",
            (const char *)0x8000FFFFLL,
            v34);
        if ( v20 > v28 )
        {
          *a7 = v52;
          *a5 = v46 + 1;
          *a6 = v28;
          *a8 = 0;
        }
        else
        {
          *a7 = v49;
          *a5 = 0;
          *a6 = v20;
          *a8 = 1;
        }
        if ( (_QWORD)v36 )
        {
          std::_Destroy_range_std::allocator_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_________(
            v36,
            *((_QWORD *)&v36 + 1));
          std::_Deallocate<16>(v36, (v37 - v36) & 0xFFFFFFFFFFFFFFF8uLL);
          v36 = 0;
          v37 = 0;
        }
        if ( (_QWORD)v40 )
        {
          std::_Destroy_range_std::allocator_wil::unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE______WTConfigCiFreePrivateData_void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_____noexcept__NewProviderData_____(
            v40,
            *((_QWORD *)&v40 + 1));
          std::_Deallocate<16>(v40, 8 * ((v41 - (__int64)v40) >> 3));
          v40 = 0;
          v41 = 0;
        }
        v31 = hMem;
        hMem = 0;
        if ( v31 )
          LocalFree(v31);
        v32 = v39;
        v39 = 0;
        if ( v32 )
          LocalFree(v32);
      }
      goto LABEL_73;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D6,
      (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\filetrust.cpp",
      (const char *)(unsigned int)IsCatalogSignatureTrusted,
      v34);
    if ( (_QWORD)v36 )
    {
      std::_Destroy_range_std::allocator_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_________(
        v36,
        *((_QWORD *)&v36 + 1));
      std::_Deallocate<16>(v36, (v37 - v36) & 0xFFFFFFFFFFFFFFF8uLL);
      v36 = 0;
      v37 = 0;
    }
    if ( (_QWORD)v40 )
    {
      std::_Destroy_range_std::allocator_wil::unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE______WTConfigCiFreePrivateData_void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_____noexcept__NewProviderData_____(
        v40,
        *((_QWORD *)&v40 + 1));
      std::_Deallocate<16>(v40, 8 * ((v41 - (__int64)v40) >> 3));
      v40 = 0;
      v41 = 0;
    }
    v25 = hMem;
    hMem = 0;
    if ( v25 )
      LocalFree(v25);
    v26 = v39;
    v39 = 0;
    if ( v26 )
      LocalFree(v26);
    wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_____::_unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_____(&v43);
    WTConfigCiFreePrivateData(v56);
    result = v24;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x409,
                           (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\filetrust.cpp",
                           v15);
  }
  return result;
}

```

## disassembly

```asm
0x18001e6b8  push    rbx
0x18001e6ba  push    rsi
0x18001e6bb  push    rdi
0x18001e6bc  push    r12
0x18001e6be  push    r13
0x18001e6c0  push    r14
0x18001e6c2  push    r15
0x18001e6c4  sub     rsp, 210h
0x18001e6cb  mov     rax, cs:__security_cookie
0x18001e6d2  xor     rax, rsp
0x18001e6d5  mov     [rsp+248h+var_48], rax
0x18001e6dd  mov     rdi, r9
0x18001e6e0  mov     rsi, r8
0x18001e6e3  mov     [rsp+248h+var_170], r8
0x18001e6eb  mov     [rsp+248h+var_188], rdx
0x18001e6f3  mov     rbx, rcx
0x18001e6f6  mov     [rsp+248h+var_190], rcx
0x18001e6fe  mov     r14, [rsp+248h+arg_20]
0x18001e706  mov     r15, [rsp+248h+arg_28]
0x18001e70e  mov     r12, [rsp+248h+arg_30]
0x18001e716  mov     r13, [rsp+248h+arg_38]
0x18001e71e  xor     eax, eax
0x18001e720  mov     [rsp+248h+var_19C], eax
0x18001e727  mov     [rsp+248h+var_198], rax
0x18001e72f  mov     [rsp+248h+var_1A0], eax
0x18001e736  xorps   xmm0, xmm0
0x18001e739  movups  [rsp+248h+var_180], xmm0
0x18001e741  mov     [rsp+248h+var_1B0], eax
0x18001e748  xorps   xmm1, xmm1
0x18001e74b  movups  [rsp+248h+var_160], xmm1
0x18001e753  mov     byte ptr [rsp+248h+var_1F8], al
0x18001e757  xor     edx, edx; Val
0x18001e759  mov     r8d, 0E8h; Size
0x18001e75f  lea     rcx, [rsp+248h+var_138]; void *
0x18001e767  call    memset_0
0x18001e76c  mov     [rsp+248h+var_138], 0E8h
0x18001e777  xor     eax, eax
0x18001e779  mov     [rsp+248h+var_1A8], rax
0x18001e781  mov     [rsp+248h+var_1D0], rax
0x18001e786  mov     [rsp+248h+hMem], rax
0x18001e78b  lea     rcx, [rsp+248h+var_1C8]
0x18001e793  call    ??$?0AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(std::allocator<std::wstring> const &)
0x18001e798  nop
0x18001e799  lea     rcx, [rsp+248h+var_1F0]
0x18001e79e  call    ??$?0AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(std::allocator<std::wstring> const &)
0x18001e7a3  nop
0x18001e7a4  lea     rcx, [rsp+248h+var_138]
0x18001e7ac  call    cs:__imp_WTConfigCiFreePrivateData
0x18001e7b2  xor     edx, edx; Val
0x18001e7b4  mov     r8d, 0E8h; Size
0x18001e7ba  lea     rcx, [rsp+248h+var_138]; void *
0x18001e7c2  call    memset_0
0x18001e7c7  mov     [rsp+248h+var_138], 0E8h
0x18001e7d2  lea     rax, [rsp+248h+var_1A8]
0x18001e7da  mov     [rsp+248h+var_150], rax
0x18001e7e2  mov     [rsp+248h+var_148], 0
0x18001e7ee  mov     [rsp+248h+var_140], 1
0x18001e7f6  mov     [rsp+248h+var_19C], 1
0x18001e801  lea     rax, [rsp+248h+var_138]
0x18001e809  mov     [rsp+248h+var_210], rax
0x18001e80e  lea     rax, [rsp+248h+var_148]
0x18001e816  mov     [rsp+248h+var_218], rax
0x18001e81b  lea     rax, [rsp+248h+var_180]
0x18001e823  mov     [rsp+248h+var_220], rax
0x18001e828  lea     rax, [rsp+248h+var_1F8]
0x18001e82d  mov     qword ptr [rsp+248h+var_228], rax; int
0x18001e832  lea     r9, [rsp+248h+var_1A0]
0x18001e83a  mov     r8b, 1
0x18001e83d  mov     rdx, [rsp+248h+var_188]
0x18001e845  mov     rcx, rbx
0x18001e848  call    WldpIsEmbedSignatureTrusted
0x18001e84d  mov     ebx, eax
0x18001e84f  mov     ecx, 1
0x18001e854  and     ecx, 0FFFFFFFEh
0x18001e857  mov     [rsp+248h+var_19C], ecx
0x18001e85e  lea     rcx, [rsp+248h+var_150]
0x18001e866  call    wil__details__out_param_t_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t__________out_param_t_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t_______
0x18001e86b  test    ebx, ebx
0x18001e86d  jns     loc_18001E97D
0x18001e873  mov     rcx, [rsp+248h]; this
0x18001e87b  mov     r9d, ebx; char *
0x18001e87e  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\wldp\\dll\\filetr"...
0x18001e885  mov     edx, 3B4h; void *
0x18001e88a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e88f  nop
0x18001e890  mov     rcx, qword ptr [rsp+248h+var_1F0]
0x18001e895  xor     edi, edi
0x18001e897  test    rcx, rcx
0x18001e89a  jz      short loc_18001E8CA
0x18001e89c  mov     rdx, qword ptr [rsp+248h+var_1F0+8]
0x18001e8a1  call    std___Destroy_range_std__allocator_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t_________
0x18001e8a6  mov     rcx, qword ptr [rsp+248h+var_1F0]
0x18001e8ab  mov     rdx, [rsp+248h+var_1E0]
0x18001e8b0  sub     rdx, rcx
0x18001e8b3  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001e8b7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001e8bc  xorps   xmm0, xmm0
0x18001e8bf  movdqu  [rsp+248h+var_1F0], xmm0
0x18001e8c5  mov     [rsp+248h+var_1E0], rdi
0x18001e8ca  mov     rcx, qword ptr [rsp+248h+var_1C8]
0x18001e8d2  test    rcx, rcx
0x18001e8d5  jz      short loc_18001E929
0x18001e8d7  mov     rdx, qword ptr [rsp+248h+var_1C8+8]
0x18001e8df  call    std___Destroy_range_std__allocator_wil__unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE______WTConfigCiFreePrivateData_void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_____noexcept__NewProviderData_____
0x18001e8e4  mov     rcx, qword ptr [rsp+248h+var_1C8]
0x18001e8ec  mov     rax, [rsp+248h+var_1B8]
0x18001e8f4  sub     rax, rcx
0x18001e8f7  sar     rax, 3
0x18001e8fb  mov     rdx, 34F72C234F72C235h
0x18001e905  imul    rax, rdx
0x18001e909  imul    rdx, rax, 0E8h
0x18001e910  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001e915  xorps   xmm0, xmm0
0x18001e918  movdqu  [rsp+248h+var_1C8], xmm0
0x18001e921  mov     [rsp+248h+var_1B8], rdi
0x18001e929  mov     rcx, [rsp+248h+hMem]; hMem
0x18001e92e  mov     [rsp+248h+hMem], rdi
0x18001e933  test    rcx, rcx
0x18001e936  jz      short loc_18001E93F
0x18001e938  call    cs:__imp_LocalFree
0x18001e93e  nop
0x18001e93f  mov     rcx, [rsp+248h+var_1D0]; hMem
0x18001e944  mov     [rsp+248h+var_1D0], rdi
0x18001e949  test    rcx, rcx
0x18001e94c  jz      short loc_18001E955
0x18001e94e  call    cs:__imp_LocalFree
0x18001e954  nop
0x18001e955  mov     rcx, [rsp+248h+var_1A8]
0x18001e95d  test    rcx, rcx
0x18001e960  jz      short loc_18001E968
0x18001e962  call    WldpFreeStateData
0x18001e967  nop
0x18001e968  lea     rcx, [rsp+248h+var_138]
0x18001e970  call    cs:__imp_WTConfigCiFreePrivateData
0x18001e976  mov     eax, ebx
0x18001e978  jmp     loc_18001F00C
0x18001e97d  lea     rdx, [rsp+248h+var_138]
0x18001e985  mov     rcx, rdi
0x18001e988  call    std__vector_wil__unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE______WTConfigCiFreePrivateData_void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_____noexcept__NewProviderData__std__allocator_wil__unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE______WTConfigCiFreePrivateData_void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_____noexcept__NewProviderData_______emplace_back_wil__unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE______WTConfigCiFreePrivateData_void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_____noexcept__NewProviderData___
0x18001e98d  lea     rdx, [rsp+248h+var_1A8]
0x18001e995  mov     rcx, rsi
0x18001e998  call    std__vector_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t______std__allocator_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t___________emplace_back_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t_______
0x18001e99d  xor     ebx, ebx
0x18001e99f  cmp     byte ptr [rsp+248h+var_1F8], bl
0x18001e9a3  jz      loc_18001EAAF
0x18001e9a9  movups  xmm0, [rsp+248h+var_180]
0x18001e9b1  movdqu  xmmword ptr [r12], xmm0
0x18001e9b7  mov     eax, [rsp+248h+var_1A0]
0x18001e9be  mov     [r15], eax
0x18001e9c1  mov     [r14], rbx
0x18001e9c4  mov     byte ptr [r13+0], 1
0x18001e9c9  mov     rcx, qword ptr [rsp+248h+var_1F0]
0x18001e9ce  test    rcx, rcx
0x18001e9d1  jz      short loc_18001EA01
0x18001e9d3  mov     rdx, qword ptr [rsp+248h+var_1F0+8]
0x18001e9d8  call    std___Destroy_range_std__allocator_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t_________
0x18001e9dd  mov     rcx, qword ptr [rsp+248h+var_1F0]
0x18001e9e2  mov     rdx, [rsp+248h+var_1E0]
0x18001e9e7  sub     rdx, rcx
0x18001e9ea  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001e9ee  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001e9f3  xorps   xmm0, xmm0
0x18001e9f6  movdqu  [rsp+248h+var_1F0], xmm0
0x18001e9fc  mov     [rsp+248h+var_1E0], rbx
0x18001ea01  mov     rcx, qword ptr [rsp+248h+var_1C8]
0x18001ea09  test    rcx, rcx
0x18001ea0c  jz      short loc_18001EA60
0x18001ea0e  mov     rdx, qword ptr [rsp+248h+var_1C8+8]
0x18001ea16  call    std___Destroy_range_std__allocator_wil__unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE______WTConfigCiFreePrivateData_void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_____noexcept__NewProviderData_____
0x18001ea1b  mov     rcx, qword ptr [rsp+248h+var_1C8]
0x18001ea23  mov     rax, [rsp+248h+var_1B8]
0x18001ea2b  sub     rax, rcx
0x18001ea2e  sar     rax, 3
0x18001ea32  mov     rdx, 34F72C234F72C235h
0x18001ea3c  imul    rax, rdx
0x18001ea40  imul    rdx, rax, 0E8h
0x18001ea47  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001ea4c  xorps   xmm0, xmm0
0x18001ea4f  movdqu  [rsp+248h+var_1C8], xmm0
0x18001ea58  mov     [rsp+248h+var_1B8], rbx
0x18001ea60  mov     rcx, [rsp+248h+hMem]; hMem
0x18001ea65  mov     [rsp+248h+hMem], rbx
0x18001ea6a  test    rcx, rcx
0x18001ea6d  jz      short loc_18001EA76
0x18001ea6f  call    cs:__imp_LocalFree
0x18001ea75  nop
0x18001ea76  mov     rcx, [rsp+248h+var_1D0]; hMem
0x18001ea7b  mov     [rsp+248h+var_1D0], rbx
0x18001ea80  test    rcx, rcx
0x18001ea83  jz      short loc_18001EA8C
0x18001ea85  call    cs:__imp_LocalFree
0x18001ea8b  nop
0x18001ea8c  lea     rcx, [rsp+248h+var_1A8]
0x18001ea94  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t_____
0x18001ea99  nop
0x18001ea9a  lea     rcx, [rsp+248h+var_138]
0x18001eaa2  call    cs:__imp_WTConfigCiFreePrivateData
0x18001eaa8  xor     eax, eax
0x18001eaaa  jmp     loc_18001F00C
0x18001eaaf  mov     esi, [rsp+248h+var_1A0]
0x18001eab6  cmp     esi, 1
0x18001eab9  jnz     loc_18001EBBD
0x18001eabf  movups  xmm0, [rsp+248h+var_180]
0x18001eac7  movdqu  xmmword ptr [r12], xmm0
0x18001eacd  mov     [r15], esi
0x18001ead0  mov     [r14], rbx
0x18001ead3  mov     [r13+0], sil
0x18001ead7  mov     rcx, qword ptr [rsp+248h+var_1F0]
0x18001eadc  test    rcx, rcx
0x18001eadf  jz      short loc_18001EB0F
0x18001eae1  mov     rdx, qword ptr [rsp+248h+var_1F0+8]
0x18001eae6  call    std___Destroy_range_std__allocator_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t_________
0x18001eaeb  mov     rcx, qword ptr [rsp+248h+var_1F0]
0x18001eaf0  mov     rdx, [rsp+248h+var_1E0]
0x18001eaf5  sub     rdx, rcx
0x18001eaf8  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001eafc  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001eb01  xorps   xmm0, xmm0
0x18001eb04  movdqu  [rsp+248h+var_1F0], xmm0
0x18001eb0a  mov     [rsp+248h+var_1E0], rbx
0x18001eb0f  mov     rcx, qword ptr [rsp+248h+var_1C8]
0x18001eb17  test    rcx, rcx
0x18001eb1a  jz      short loc_18001EB6E
0x18001eb1c  mov     rdx, qword ptr [rsp+248h+var_1C8+8]
0x18001eb24  call    std___Destroy_range_std__allocator_wil__unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE______WTConfigCiFreePrivateData_void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_____noexcept__NewProviderData_____
0x18001eb29  mov     rcx, qword ptr [rsp+248h+var_1C8]
0x18001eb31  mov     rax, [rsp+248h+var_1B8]
0x18001eb39  sub     rax, rcx
0x18001eb3c  sar     rax, 3
0x18001eb40  mov     rdx, 34F72C234F72C235h
0x18001eb4a  imul    rax, rdx
0x18001eb4e  imul    rdx, rax, 0E8h
0x18001eb55  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001eb5a  xorps   xmm0, xmm0
0x18001eb5d  movdqu  [rsp+248h+var_1C8], xmm0
0x18001eb66  mov     [rsp+248h+var_1B8], rbx
0x18001eb6e  mov     rcx, [rsp+248h+hMem]; hMem
0x18001eb73  mov     [rsp+248h+hMem], rbx
0x18001eb78  test    rcx, rcx
0x18001eb7b  jz      short loc_18001EB84
0x18001eb7d  call    cs:__imp_LocalFree
0x18001eb83  nop
0x18001eb84  mov     rcx, [rsp+248h+var_1D0]; hMem
0x18001eb89  mov     [rsp+248h+var_1D0], rbx
0x18001eb8e  test    rcx, rcx
0x18001eb91  jz      short loc_18001EB9A
0x18001eb93  call    cs:__imp_LocalFree
0x18001eb99  nop
0x18001eb9a  lea     rcx, [rsp+248h+var_1A8]
0x18001eba2  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t_____
0x18001eba7  nop
0x18001eba8  lea     rcx, [rsp+248h+var_138]
0x18001ebb0  call    cs:__imp_WTConfigCiFreePrivateData
0x18001ebb6  xor     eax, eax
0x18001ebb8  jmp     loc_18001F00C
0x18001ebbd  lea     rax, [rsp+248h+var_160]
0x18001ebc5  mov     [rsp+248h+var_208], rax
0x18001ebca  lea     rax, [rsp+248h+var_1F8]
0x18001ebcf  mov     [rsp+248h+var_210], rax
0x18001ebd4  lea     rax, [rsp+248h+var_1B0]
0x18001ebdc  mov     [rsp+248h+var_218], rax
0x18001ebe1  lea     rax, [rsp+248h+var_198]
0x18001ebe9  mov     [rsp+248h+var_220], rax
0x18001ebee  mov     qword ptr [rsp+248h+var_228], rdi; int
0x18001ebf3  lea     r9, [rsp+248h+var_1F0]
0x18001ebf8  mov     r8b, 1
0x18001ebfb  mov     rdx, [rsp+248h+var_188]
0x18001ec03  mov     rcx, [rsp+248h+var_190]
0x18001ec0b  call    WldpIsCatalogSignatureTrusted
0x18001ec10  mov     ebx, eax
0x18001ec12  test    eax, eax
0x18001ec14  jns     loc_18001ED1F
0x18001ec1a  mov     rcx, [rsp+248h]; this
0x18001ec22  mov     r9d, eax; char *
0x18001ec25  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\wldp\\dll\\filetr"...
0x18001ec2c  mov     edx, 3D6h; void *
0x18001ec31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ec36  nop
0x18001ec37  mov     rcx, qword ptr [rsp+248h+var_1F0]
0x18001ec3c  xor     edi, edi
0x18001ec3e  test    rcx, rcx
0x18001ec41  jz      short loc_18001EC71
0x18001ec43  mov     rdx, qword ptr [rsp+248h+var_1F0+8]
0x18001ec48  call    std___Destroy_range_std__allocator_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t_________
0x18001ec4d  mov     rcx, qword ptr [rsp+248h+var_1F0]
0x18001ec52  mov     rdx, [rsp+248h+var_1E0]
0x18001ec57  sub     rdx, rcx
0x18001ec5a  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001ec5e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001ec63  xorps   xmm0, xmm0
0x18001ec66  movdqu  [rsp+248h+var_1F0], xmm0
0x18001ec6c  mov     [rsp+248h+var_1E0], rdi
0x18001ec71  mov     rcx, qword ptr [rsp+248h+var_1C8]
0x18001ec79  test    rcx, rcx
0x18001ec7c  jz      short loc_18001ECD0
0x18001ec7e  mov     rdx, qword ptr [rsp+248h+var_1C8+8]
0x18001ec86  call    std___Destroy_range_std__allocator_wil__unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE______WTConfigCiFreePrivateData_void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_____noexcept__NewProviderData_____
0x18001ec8b  mov     rcx, qword ptr [rsp+248h+var_1C8]
0x18001ec93  mov     rax, [rsp+248h+var_1B8]
0x18001ec9b  sub     rax, rcx
  ... truncated ...
```
