# HyperVGuestLoader::IsolatedVm::FileFormat::Details::UnmarshalPlatform(uint,gsl::span<gsl::byte const,-1>,std::set<uint,std::less<uint>,std::allocator<uint>> &,std::map<uint,uint,std::less<uint>,std::allocator<std::pair<uint const,uint>>> &,std::optional<std::set<uint,std::less<uint>,std::allocator<uint>>> &)

- ea: `0x14006e6f0`
- end: `0x14006ec91`
- name: `?UnmarshalPlatform@Details@FileFormat@IsolatedVm@HyperVGuestLoader@@YA?AV?$optional@V?$variant@U_IGVM_VHS_SUPPORTED_PLATFORM@@UPageData@FileFormat@IsolatedVm@HyperVGuestLoader@@UVbsVpContext@345@U_IGVM_VHS_CVM_POLICY@@USnpVpContext@345@U_IGVM_VHS_TD_INFO@@UParameterArea@345@UVpCountParameter@345@UMmioRangesParameter@345@USratParameter@345@UMadtParameter@345@USlitParameter@345@UPpttParameter@345@UMemoryMapParameter@345@UCommandLineParameter@345@U_IGVM_VHS_PARAMETER_INSERT@@U_IGVM_VHS_REQUIRED_MEMORY@@U_IGVM_VHS_ERROR_RANGE@@U_IGVM_VHS_SNP_ID_BLOCK@@U_IGVM_VHS_VBS_MEASUREMENT@@URelocatableRegion@345@UPageTableRelocationRegion@345@UDeviceTreeParameter@345@URmeVpContext@345@@std@@@std@@IV?$span@$$CBW4byte@gsl@@$0?0@gsl@@AEAV?$set@IU?$less@I@std@@V?$allocator@I@2@@6@AEAV?$map@IIU?$less@I@std@@V?$allocator@U?$pair@$$CBII@std@@@2@@6@AEAV?$optional@V?$set@IU?$less@I@std@@V?$allocator@I@2@@std@@@6@@Z`
- size: `1441`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400c94b4`

## callees

- `0x140024768`
- `0x14006af58`
- `0x14006e6f0`
- `0x14006fee8`
- `0x1401c2064`
- `0x1401c3038`
- `0x1401c30fc`
- `0x1401c3874`
- `0x1401c3de0`
- `0x1401c4448`
- `0x1401c568c`
- `0x140299850`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x14006ec84`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x14006ec84`

## string_xrefs

- `0x14006e844`: `onecore\vm\common\guestloader\lib\isolatedvmloaderformat.cpp`
- `0x14006e868`: `onecore\vm\common\guestloader\lib\isolatedvmloaderformat.cpp`
- `0x14006e88c`: `onecore\vm\common\guestloader\lib\isolatedvmloaderformat.cpp`
- `0x14006e8b0`: `onecore\vm\common\guestloader\lib\isolatedvmloaderformat.cpp`
- `0x14006e98d`: `onecore\vm\common\guestloader\lib\isolatedvmloaderformat.cpp`
- `0x14006e9b1`: `onecore\vm\common\guestloader\lib\isolatedvmloaderformat.cpp`
- `0x14006e9dd`: `onecore\vm\common\guestloader\lib\isolatedvmloaderformat.cpp`
- `0x14006ea07`: `onecore\vm\common\guestloader\lib\isolatedvmloaderformat.cpp`
- `0x14006ea31`: `onecore\vm\common\guestloader\lib\isolatedvmloaderformat.cpp`
- `0x14006eb96`: `onecore\vm\common\guestloader\lib\isolatedvmloaderformat.cpp`
- `0x14006ebd0`: `onecore\vm\common\guestloader\lib\isolatedvmloaderformat.cpp`
- `0x14006ec72`: `onecore\vm\common\guestloader\lib\isolatedvmloaderformat.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HyperVGuestLoader::IsolatedVm::FileFormat::Details::UnmarshalPlatform(
        __int64 a1,
        int a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  unsigned int *v12; // rdi
  __int64 v13; // rcx
  unsigned int *v14; // rdi
  __int64 v15; // r8
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  __int16 v18; // r10
  char v19; // r11
  unsigned int *v20; // rdi
  __int16 v21; // r13
  char v22; // r14
  bool v23; // si
  bool v24; // r8
  unsigned __int64 v25; // rcx
  unsigned __int64 v26; // r11
  __int64 v27; // r15
  unsigned __int64 v28; // r10
  unsigned __int64 v29; // r9
  __int64 v30; // rcx
  __int128 *v31; // rdi
  _DWORD *v32; // rdi
  int v34[4]; // [rsp+20h] [rbp-E0h] BYREF
  _OWORD v35[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v36; // [rsp+70h] [rbp-90h]
  __int128 v37; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v38; // [rsp+88h] [rbp-78h]
  unsigned __int64 v39; // [rsp+90h] [rbp-70h]
  __int64 v40; // [rsp+98h] [rbp-68h]
  unsigned __int64 v41; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v42; // [rsp+A8h] [rbp-58h]
  char v43; // [rsp+1090h] [rbp+F90h]
  char v44; // [rsp+1098h] [rbp+F98h]
  wil::details::in1diag3 *retaddr; // [rsp+10D8h] [rbp+FD8h]

  *(_QWORD *)v34 = a1;
  *(_BYTE *)(a1 + 4128) = 0;
  v36 = 1;
  v8 = a2 - 1;
  if ( !v8 )
  {
    v32 = (_DWORD *)a3[1];
    *(_QWORD *)&v35[0] = *a3;
    *((_QWORD *)&v35[0] + 1) = v32;
    if ( (unsigned __int64)gsl::span<unsigned char,-1>::size_bytes(v35) < 0x10 )
      goto LABEL_50;
    gsl::span<unsigned char,-1>::size_bytes(v35);
    if ( !*v32 || (((unsigned int)*v32 - 1LL) & (unsigned int)*v32) != 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x282,
        (unsigned int)"onecore\\vm\\common\\guestloader\\lib\\isolatedvmloaderformat.cpp",
        (const char *)0x80070057LL,
        v34[0]);
    std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::insert<0,0>(
      a4,
      v35,
      v32);
    if ( !BYTE8(v35[0]) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x28A,
        (unsigned int)"onecore\\vm\\common\\guestloader\\lib\\isolatedvmloaderformat.cpp",
        (const char *)0x80070057LL,
        v34[0]);
    std::_Tree<std::_Tmap_traits<unsigned int,unsigned int,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,unsigned int>>,0>>::_Emplace<unsigned char const &,unsigned int const &>(
      a5,
      v35,
      (char *)v32 + 5,
      v32);
    if ( !BYTE8(v35[0]) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x291,
        (unsigned int)"onecore\\vm\\common\\guestloader\\lib\\isolatedvmloaderformat.cpp",
        (const char *)0x80070057LL,
        v34[0]);
    HyperVGuestLoader::IsolatedVm::FileFormat::Details::PopulateSupportedPlatforms((unsigned int)*v32, a5, a6);
    v37 = *(_OWORD *)v32;
    v43 = 0;
    v44 = 1;
    if ( *(_BYTE *)(a1 + 4128) )
    {
      v30 = 1;
      goto LABEL_45;
    }
    goto LABEL_46;
  }
  v9 = v8 - 256;
  if ( !v9 )
  {
    v31 = (__int128 *)a3[1];
    *(_QWORD *)&v35[0] = *a3;
    *((_QWORD *)&v35[0] + 1) = v31;
    if ( (unsigned __int64)gsl::span<unsigned char,-1>::size_bytes(v35) < 0x10 )
      goto LABEL_50;
    gsl::span<unsigned char,-1>::size_bytes(v35);
    HyperVGuestLoader::IsolatedVm::FileFormat::Details::PopulateSupportedPlatforms(*((unsigned int *)v31 + 2), a5, a6);
    v37 = *v31;
    v43 = 3;
    v44 = 1;
    if ( *(_BYTE *)(a1 + 4128) )
    {
      v30 = 4;
      goto LABEL_45;
    }
LABEL_46:
    std::_Construct_in_place<std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>,std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>>(
      a1,
      &v37);
    *(_BYTE *)(a1 + 4128) = 1;
    goto LABEL_47;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    v20 = (unsigned int *)a3[1];
    *(_QWORD *)&v35[0] = *a3;
    *((_QWORD *)&v35[0] + 1) = v20;
    if ( (unsigned __int64)gsl::span<unsigned char,-1>::size_bytes(v35) < 0x30 )
      goto LABEL_50;
    gsl::span<unsigned char,-1>::size_bytes(v35);
    HyperVGuestLoader::IsolatedVm::FileFormat::Details::PopulateSupportedPlatforms(*v20, a5, a6);
    v35[0] = 0;
    v21 = *((_WORD *)v20 + 2);
    v22 = *((_BYTE *)v20 + 7) & 1;
    v23 = (*((_BYTE *)v20 + 7) & 2) != 0;
    v24 = (*((_BYTE *)v20 + 7) & 4) != 0;
    v25 = *((_QWORD *)v20 + 1);
    v26 = *((_QWORD *)v20 + 2);
    v27 = *((_QWORD *)v20 + 3);
    v28 = *((_QWORD *)v20 + 4);
    v29 = *((_QWORD *)v20 + 5);
    if ( (v27 & 0xFFF) != 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2B3,
        (unsigned int)"onecore\\vm\\common\\guestloader\\lib\\isolatedvmloaderformat.cpp",
        (const char *)0x80070057LL,
        v34[0]);
    if ( (v25 & 0xFFF) != 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2B8,
        (unsigned int)"onecore\\vm\\common\\guestloader\\lib\\isolatedvmloaderformat.cpp",
        (const char *)0x80070057LL,
        v34[0]);
    if ( v26 % v25 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2BD,
        (unsigned int)"onecore\\vm\\common\\guestloader\\lib\\isolatedvmloaderformat.cpp",
        (const char *)0x80070057LL,
        v34[0]);
    if ( v28 % v25 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2C2,
        (unsigned int)"onecore\\vm\\common\\guestloader\\lib\\isolatedvmloaderformat.cpp",
        (const char *)0x80070057LL,
        v34[0]);
    if ( v29 % v25 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2C7,
        (unsigned int)"onecore\\vm\\common\\guestloader\\lib\\isolatedvmloaderformat.cpp",
        (const char *)0x80070057LL,
        v34[0]);
    LODWORD(v37) = *v20;
    WORD2(v37) = v21;
    BYTE6(v37) = *((_BYTE *)v20 + 6);
    BYTE7(v37) = v22;
    BYTE8(v37) = v23;
    BYTE9(v37) = v24;
    *(_DWORD *)((char *)&v37 + 10) = *(_DWORD *)((char *)v35 + 10);
    HIWORD(v37) = HIWORD(v35[0]);
    v38 = v25;
    v39 = v26;
    v40 = v27;
    v41 = v28;
    v42 = v29;
    v43 = 20;
    v44 = 1;
    if ( *(_BYTE *)(a1 + 4128) )
    {
      v30 = 21;
LABEL_45:
      *(_QWORD *)v34 = a1;
      std::_Variant_raw_visit1<3>::_Visit<std::_Variant_assign_visitor<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>,std::_Variant_storage_<0,_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>>(
        v30,
        v34,
        &v37);
      goto LABEL_47;
    }
    goto LABEL_46;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    v14 = (unsigned int *)a3[1];
    *(_QWORD *)&v35[0] = *a3;
    *((_QWORD *)&v35[0] + 1) = v14;
    if ( (unsigned __int64)gsl::span<unsigned char,-1>::size_bytes(v35) >= 0x20 )
    {
      gsl::span<unsigned char,-1>::size_bytes(v35);
      HyperVGuestLoader::IsolatedVm::FileFormat::Details::PopulateSupportedPlatforms(*v14, a5, a6);
      v35[0] = 0;
      v15 = *((_QWORD *)v14 + 1);
      v16 = *((_QWORD *)v14 + 2);
      v17 = *((_QWORD *)v14 + 3);
      v18 = *((_WORD *)v14 + 2);
      v19 = *((_BYTE *)v14 + 6);
      if ( (v15 & 0xFFF) != 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2DB,
          (unsigned int)"onecore\\vm\\common\\guestloader\\lib\\isolatedvmloaderformat.cpp",
          (const char *)0x80070057LL,
          v34[0]);
      if ( (v16 & 0xFFF) != 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2E0,
          (unsigned int)"onecore\\vm\\common\\guestloader\\lib\\isolatedvmloaderformat.cpp",
          (const char *)0x80070057LL,
          v34[0]);
      if ( (v17 & 0xFFF) != 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2E5,
          (unsigned int)"onecore\\vm\\common\\guestloader\\lib\\isolatedvmloaderformat.cpp",
          (const char *)0x80070057LL,
          v34[0]);
      if ( v17 > v16 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2EA,
          (unsigned int)"onecore\\vm\\common\\guestloader\\lib\\isolatedvmloaderformat.cpp",
          (const char *)0x80070057LL,
          v34[0]);
      LODWORD(v37) = *v14;
      WORD2(v37) = v18;
      BYTE6(v37) = v19;
      BYTE7(v37) = BYTE7(v35[0]);
      *((_QWORD *)&v37 + 1) = v15;
      v38 = v16;
      v39 = v17;
      v43 = 21;
      v44 = 1;
      goto LABEL_8;
    }
LABEL_50:
    _o_terminate(v13);
    __debugbreak();
    JUMPOUT(0x14006EC91LL);
  }
  if ( v11 == 252 )
  {
    v12 = (unsigned int *)a3[1];
    *(_QWORD *)&v35[0] = *a3;
    *((_QWORD *)&v35[0] + 1) = v12;
    if ( (unsigned __int64)gsl::span<unsigned char,-1>::size_bytes(v35) >= 0x10 )
    {
      gsl::span<unsigned char,-1>::size_bytes(v35);
      HyperVGuestLoader::IsolatedVm::FileFormat::Details::PopulateSupportedPlatforms(*v12, a5, a6);
      std::optional<std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>>::optional<std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>>(
        &v37,
        v12);
LABEL_8:
      std::_Optional_construct_base<std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>>::_Assign_from<std::_Optional_construct_base<std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>>>(
        a1,
        &v37);
LABEL_47:
      std::_Optional_destruct_base<std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>,0>::~_Optional_destruct_base<std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>,0>(&v37);
      return a1;
    }
    goto LABEL_50;
  }
  return a1;
}

```

## disassembly

```asm
0x14006e6f0  mov     [rsp-8+arg_8], rbx
0x14006e6f5  push    rbp
0x14006e6f6  push    rsi
0x14006e6f7  push    rdi
0x14006e6f8  push    r12
0x14006e6fa  push    r13
0x14006e6fc  push    r14
0x14006e6fe  push    r15
0x14006e700  lea     rbp, [rsp-0FA0h]
0x14006e708  mov     eax, 10A0h
0x14006e70d  call    _alloca_probe
0x14006e712  sub     rsp, rax
0x14006e715  mov     r15, r9
0x14006e718  mov     rbx, rcx
0x14006e71b  mov     qword ptr [rsp+10D0h+var_10B0], rcx; int
0x14006e720  mov     rsi, [rbp+0FD0h+arg_20]
0x14006e727  mov     r14, [rbp+0FD0h+arg_28]
0x14006e72e  xor     r12d, r12d
0x14006e731  mov     [rsp+10D0h+var_1060], r12d
0x14006e736  mov     [rcx+1020h], r12b
0x14006e73d  lea     r13d, [r12+1]
0x14006e742  mov     [rsp+10D0h+var_1060], r13d
0x14006e747  sub     edx, r13d
0x14006e74a  jz      loc_14006EB2B
0x14006e750  sub     edx, 100h
0x14006e756  jz      loc_14006EAC0
0x14006e75c  sub     edx, r13d
0x14006e75f  jz      loc_14006E8F9
0x14006e765  sub     edx, r13d
0x14006e768  jz      short loc_14006E7D1
0x14006e76a  cmp     edx, 0FCh
0x14006e770  jnz     loc_14006EC46
0x14006e776  mov     rax, [r8]
0x14006e779  mov     rdi, [r8+8]
0x14006e77d  mov     qword ptr [rsp+10D0h+var_10A0], rax
0x14006e782  mov     qword ptr [rsp+10D0h+var_10A0+8], rdi
0x14006e787  lea     rcx, [rsp+10D0h+var_10A0]
0x14006e78c  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x14006e791  cmp     rax, 10h
0x14006e795  jb      loc_14006EC84
0x14006e79b  lea     rcx, [rsp+10D0h+var_10A0]
0x14006e7a0  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x14006e7a5  mov     r8, r14
0x14006e7a8  mov     rdx, rsi
0x14006e7ab  mov     ecx, [rdi]
0x14006e7ad  call    ?PopulateSupportedPlatforms@Details@FileFormat@IsolatedVm@HyperVGuestLoader@@YAXIAEBV?$map@IIU?$less@I@std@@V?$allocator@U?$pair@$$CBII@std@@@2@@std@@AEAV?$optional@V?$set@IU?$less@I@std@@V?$allocator@I@2@@std@@@6@@Z; HyperVGuestLoader::IsolatedVm::FileFormat::Details::PopulateSupportedPlatforms(uint,std::map<uint,uint> const &,std::optional<std::set<uint>> &)
0x14006e7b2  mov     rdx, rdi
0x14006e7b5  lea     rcx, [rsp+10D0h+var_1058]
0x14006e7ba  call    ??$?0AEBU_IGVM_VHS_TD_INFO@@$0A@@?$optional@V?$variant@U_IGVM_VHS_SUPPORTED_PLATFORM@@UPageData@FileFormat@IsolatedVm@HyperVGuestLoader@@UVbsVpContext@345@U_IGVM_VHS_CVM_POLICY@@USnpVpContext@345@U_IGVM_VHS_TD_INFO@@UParameterArea@345@UVpCountParameter@345@UMmioRangesParameter@345@USratParameter@345@UMadtParameter@345@USlitParameter@345@UPpttParameter@345@UMemoryMapParameter@345@UCommandLineParameter@345@U_IGVM_VHS_PARAMETER_INSERT@@U_IGVM_VHS_REQUIRED_MEMORY@@U_IGVM_VHS_ERROR_RANGE@@U_IGVM_VHS_SNP_ID_BLOCK@@U_IGVM_VHS_VBS_MEASUREMENT@@URelocatableRegion@345@UPageTableRelocationRegion@345@UDeviceTreeParameter@345@URmeVpContext@345@@std@@@std@@QEAA@AEBU_IGVM_VHS_TD_INFO@@@Z; std::optional<std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>>::optional<std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>>(_IGVM_VHS_TD_INFO const &)
0x14006e7bf  lea     rdx, [rsp+10D0h+var_1058]
0x14006e7c4  mov     rcx, rbx
0x14006e7c7  call    ??$_Assign_from@U?$_Optional_construct_base@V?$variant@U_IGVM_VHS_SUPPORTED_PLATFORM@@UPageData@FileFormat@IsolatedVm@HyperVGuestLoader@@UVbsVpContext@345@U_IGVM_VHS_CVM_POLICY@@USnpVpContext@345@U_IGVM_VHS_TD_INFO@@UParameterArea@345@UVpCountParameter@345@UMmioRangesParameter@345@USratParameter@345@UMadtParameter@345@USlitParameter@345@UPpttParameter@345@UMemoryMapParameter@345@UCommandLineParameter@345@U_IGVM_VHS_PARAMETER_INSERT@@U_IGVM_VHS_REQUIRED_MEMORY@@U_IGVM_VHS_ERROR_RANGE@@U_IGVM_VHS_SNP_ID_BLOCK@@U_IGVM_VHS_VBS_MEASUREMENT@@URelocatableRegion@345@UPageTableRelocationRegion@345@UDeviceTreeParameter@345@URmeVpContext@345@@std@@@std@@@?$_Optional_construct_base@V?$variant@U_IGVM_VHS_SUPPORTED_PLATFORM@@UPageData@FileFormat@IsolatedVm@HyperVGuestLoader@@UVbsVpContext@345@U_IGVM_VHS_CVM_POLICY@@USnpVpContext@345@U_IGVM_VHS_TD_INFO@@UParameterArea@345@UVpCountParameter@345@UMmioRangesParameter@345@USratParameter@345@UMadtParameter@345@USlitParameter@345@UPpttParameter@345@UMemoryMapParameter@345@UCommandLineParameter@345@U_IGVM_VHS_PARAMETER_INSERT@@U_IGVM_VHS_REQUIRED_MEMORY@@U_IGVM_VHS_ERROR_RANGE@@U_IGVM_VHS_SNP_ID_BLOCK@@U_IGVM_VHS_VBS_MEASUREMENT@@URelocatableRegion@345@UPageTableRelocationRegion@345@UDeviceTreeParameter@345@URmeVpContext@345@@std@@@std@@QEAAX$$QEAU01@@Z; std::_Optional_construct_base<std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>>::_Assign_from<std::_Optional_construct_base<std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>>>(std::_Optional_construct_base<std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>> &&)
0x14006e7cc  jmp     loc_14006EC3C
0x14006e7d1  mov     rax, [r8]
0x14006e7d4  mov     rdi, [r8+8]
0x14006e7d8  mov     qword ptr [rsp+10D0h+var_10A0], rax
0x14006e7dd  mov     qword ptr [rsp+10D0h+var_10A0+8], rdi
0x14006e7e2  lea     rcx, [rsp+10D0h+var_10A0]
0x14006e7e7  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x14006e7ec  cmp     rax, 20h ; ' '
0x14006e7f0  jb      loc_14006EC84
0x14006e7f6  lea     rcx, [rsp+10D0h+var_10A0]
0x14006e7fb  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x14006e800  mov     r8, r14
0x14006e803  mov     rdx, rsi
0x14006e806  mov     ecx, [rdi]
0x14006e808  call    ?PopulateSupportedPlatforms@Details@FileFormat@IsolatedVm@HyperVGuestLoader@@YAXIAEBV?$map@IIU?$less@I@std@@V?$allocator@U?$pair@$$CBII@std@@@2@@std@@AEAV?$optional@V?$set@IU?$less@I@std@@V?$allocator@I@2@@std@@@6@@Z; HyperVGuestLoader::IsolatedVm::FileFormat::Details::PopulateSupportedPlatforms(uint,std::map<uint,uint> const &,std::optional<std::set<uint>> &)
0x14006e80d  xorps   xmm0, xmm0
0x14006e810  movups  [rsp+10D0h+var_10A0], xmm0
0x14006e815  mov     r9d, [rdi]
0x14006e818  mov     r8, [rdi+8]
0x14006e81c  mov     rcx, [rdi+10h]
0x14006e820  mov     rdx, [rdi+18h]
0x14006e824  movzx   r10d, word ptr [rdi+4]
0x14006e829  mov     r11b, [rdi+6]
0x14006e82d  mov     eax, 0FFFh
0x14006e832  test    rax, r8
0x14006e835  jz      short loc_14006E856
0x14006e837  mov     rcx, [rbp+0FD8h]; this
0x14006e83e  mov     r9d, 80070057h; char *
0x14006e844  lea     r8, aOnecoreVmCommo_59; "onecore\\vm\\common\\guestloader\\lib\\"...
0x14006e84b  mov     edx, 2DBh; void *
0x14006e850  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006e856  test    rax, rcx
0x14006e859  jz      short loc_14006E87A
0x14006e85b  mov     rcx, [rbp+0FD8h]; this
0x14006e862  mov     r9d, 80070057h; char *
0x14006e868  lea     r8, aOnecoreVmCommo_59; "onecore\\vm\\common\\guestloader\\lib\\"...
0x14006e86f  mov     edx, 2E0h; void *
0x14006e874  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006e87a  test    rax, rdx
0x14006e87d  jz      short loc_14006E89E
0x14006e87f  mov     rcx, [rbp+0FD8h]; this
0x14006e886  mov     r9d, 80070057h; char *
0x14006e88c  lea     r8, aOnecoreVmCommo_59; "onecore\\vm\\common\\guestloader\\lib\\"...
0x14006e893  mov     edx, 2E5h; void *
0x14006e898  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006e89e  cmp     rdx, rcx
0x14006e8a1  jbe     short loc_14006E8C2
0x14006e8a3  mov     rcx, [rbp+0FD8h]; this
0x14006e8aa  mov     r9d, 80070057h; char *
0x14006e8b0  lea     r8, aOnecoreVmCommo_59; "onecore\\vm\\common\\guestloader\\lib\\"...
0x14006e8b7  mov     edx, 2EAh; void *
0x14006e8bc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006e8c2  mov     dword ptr [rsp+10D0h+var_1058], r9d
0x14006e8c7  mov     word ptr [rsp+10D0h+var_1058+4], r10w
0x14006e8cd  mov     byte ptr [rsp+10D0h+var_1058+6], r11b
0x14006e8d2  mov     al, byte ptr [rsp+10D0h+var_10A0+7]
0x14006e8d6  mov     byte ptr [rsp+10D0h+var_1058+7], al
0x14006e8da  mov     qword ptr [rbp+0FD0h+var_1058+8], r8
0x14006e8de  mov     [rbp+0FD0h+var_1048], rcx
0x14006e8e2  mov     [rbp+0FD0h+var_1040], rdx
0x14006e8e6  mov     [rbp+0FD0h+var_40], 15h
0x14006e8ed  mov     [rbp+0FD0h+var_38], r13b
0x14006e8f4  jmp     loc_14006E7BF
0x14006e8f9  mov     rax, [r8]
0x14006e8fc  mov     rdi, [r8+8]
0x14006e900  mov     qword ptr [rsp+10D0h+var_10A0], rax
0x14006e905  mov     qword ptr [rsp+10D0h+var_10A0+8], rdi
0x14006e90a  lea     rcx, [rsp+10D0h+var_10A0]
0x14006e90f  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x14006e914  cmp     rax, 30h ; '0'
0x14006e918  jb      loc_14006EC84
0x14006e91e  lea     rcx, [rsp+10D0h+var_10A0]
0x14006e923  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x14006e928  mov     r8, r14
0x14006e92b  mov     rdx, rsi
0x14006e92e  mov     ecx, [rdi]
0x14006e930  call    ?PopulateSupportedPlatforms@Details@FileFormat@IsolatedVm@HyperVGuestLoader@@YAXIAEBV?$map@IIU?$less@I@std@@V?$allocator@U?$pair@$$CBII@std@@@2@@std@@AEAV?$optional@V?$set@IU?$less@I@std@@V?$allocator@I@2@@std@@@6@@Z; HyperVGuestLoader::IsolatedVm::FileFormat::Details::PopulateSupportedPlatforms(uint,std::map<uint,uint> const &,std::optional<std::set<uint>> &)
0x14006e935  xorps   xmm0, xmm0
0x14006e938  movups  [rsp+10D0h+var_10A0], xmm0
0x14006e93d  mov     r12d, [rdi]
0x14006e940  movzx   r13d, word ptr [rdi+4]
0x14006e945  mov     r8b, [rdi+7]
0x14006e949  mov     r14b, r8b
0x14006e94c  and     r14b, 1
0x14006e950  mov     sil, r8b
0x14006e953  shr     sil, 1
0x14006e956  and     sil, 1
0x14006e95a  shr     r8b, 2
0x14006e95e  and     r8b, 1
0x14006e962  mov     rcx, [rdi+8]
0x14006e966  mov     r11, [rdi+10h]
0x14006e96a  mov     r15, [rdi+18h]
0x14006e96e  mov     r10, [rdi+20h]
0x14006e972  mov     r9, [rdi+28h]
0x14006e976  mov     eax, 0FFFh
0x14006e97b  test    rax, r15
0x14006e97e  jz      short loc_14006E99F
0x14006e980  mov     rcx, [rbp+0FD8h]; this
0x14006e987  mov     r9d, 80070057h; char *
0x14006e98d  lea     r8, aOnecoreVmCommo_59; "onecore\\vm\\common\\guestloader\\lib\\"...
0x14006e994  mov     edx, 2B3h; void *
0x14006e999  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006e99f  test    rax, rcx
0x14006e9a2  jz      short loc_14006E9C3
0x14006e9a4  mov     rcx, [rbp+0FD8h]; this
0x14006e9ab  mov     r9d, 80070057h; char *
0x14006e9b1  lea     r8, aOnecoreVmCommo_59; "onecore\\vm\\common\\guestloader\\lib\\"...
0x14006e9b8  mov     edx, 2B8h; void *
0x14006e9bd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006e9c3  xor     edx, edx
0x14006e9c5  mov     rax, r11
0x14006e9c8  div     rcx
0x14006e9cb  test    rdx, rdx
0x14006e9ce  jz      short loc_14006E9EF
0x14006e9d0  mov     rcx, [rbp+0FD8h]; this
0x14006e9d7  mov     r9d, 80070057h; char *
0x14006e9dd  lea     r8, aOnecoreVmCommo_59; "onecore\\vm\\common\\guestloader\\lib\\"...
0x14006e9e4  mov     edx, 2BDh; void *
0x14006e9e9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006e9ef  mov     rax, r10
0x14006e9f2  div     rcx
0x14006e9f5  test    rdx, rdx
0x14006e9f8  jz      short loc_14006EA19
0x14006e9fa  mov     rcx, [rbp+0FD8h]; this
0x14006ea01  mov     r9d, 80070057h; char *
0x14006ea07  lea     r8, aOnecoreVmCommo_59; "onecore\\vm\\common\\guestloader\\lib\\"...
0x14006ea0e  mov     edx, 2C2h; void *
0x14006ea13  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006ea19  mov     rax, r9
0x14006ea1c  div     rcx
0x14006ea1f  test    rdx, rdx
0x14006ea22  jz      short loc_14006EA43
0x14006ea24  mov     rcx, [rbp+0FD8h]; this
0x14006ea2b  mov     r9d, 80070057h; char *
0x14006ea31  lea     r8, aOnecoreVmCommo_59; "onecore\\vm\\common\\guestloader\\lib\\"...
0x14006ea38  mov     edx, 2C7h; void *
0x14006ea3d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006ea43  mov     dword ptr [rsp+10D0h+var_1058], r12d
0x14006ea48  mov     word ptr [rsp+10D0h+var_1058+4], r13w
0x14006ea4e  mov     al, [rdi+6]
0x14006ea51  mov     byte ptr [rsp+10D0h+var_1058+6], al
0x14006ea55  mov     byte ptr [rsp+10D0h+var_1058+7], r14b
0x14006ea5a  mov     byte ptr [rbp+0FD0h+var_1058+8], sil
0x14006ea5e  mov     byte ptr [rbp+0FD0h+var_1058+9], r8b
0x14006ea62  mov     eax, dword ptr [rsp+10D0h+var_10A0+0Ah]
0x14006ea66  mov     dword ptr [rbp+0FD0h+var_1058+0Ah], eax
0x14006ea69  movzx   eax, word ptr [rsp+10D0h+var_10A0+0Eh]
0x14006ea6e  mov     word ptr [rbp+0FD0h+var_1058+0Eh], ax
0x14006ea72  mov     [rbp+0FD0h+var_1048], rcx
0x14006ea76  mov     [rbp+0FD0h+var_1040], r11
0x14006ea7a  mov     [rbp+0FD0h+var_1038], r15
0x14006ea7e  mov     [rbp+0FD0h+var_1030], r10
0x14006ea82  mov     [rbp+0FD0h+var_1028], r9
0x14006ea86  mov     [rbp+0FD0h+var_40], 14h
0x14006ea8d  mov     [rbp+0FD0h+var_38], 1
0x14006ea94  cmp     byte ptr [rbx+1020h], 0
0x14006ea9b  jz      short loc_14006EAA7
0x14006ea9d  mov     ecx, 15h
0x14006eaa2  jmp     loc_14006EC12
0x14006eaa7  lea     rdx, [rsp+10D0h+var_1058]
0x14006eaac  mov     rcx, rbx
0x14006eaaf  call    ??$_Construct_in_place@V?$variant@U_IGVM_VHS_SUPPORTED_PLATFORM@@UPageData@FileFormat@IsolatedVm@HyperVGuestLoader@@UVbsVpContext@345@U_IGVM_VHS_CVM_POLICY@@USnpVpContext@345@U_IGVM_VHS_TD_INFO@@UParameterArea@345@UVpCountParameter@345@UMmioRangesParameter@345@USratParameter@345@UMadtParameter@345@USlitParameter@345@UPpttParameter@345@UMemoryMapParameter@345@UCommandLineParameter@345@U_IGVM_VHS_PARAMETER_INSERT@@U_IGVM_VHS_REQUIRED_MEMORY@@U_IGVM_VHS_ERROR_RANGE@@U_IGVM_VHS_SNP_ID_BLOCK@@U_IGVM_VHS_VBS_MEASUREMENT@@URelocatableRegion@345@UPageTableRelocationRegion@345@UDeviceTreeParameter@345@URmeVpContext@345@@std@@V12@@std@@YAXAEAV?$variant@U_IGVM_VHS_SUPPORTED_PLATFORM@@UPageData@FileFormat@IsolatedVm@HyperVGuestLoader@@UVbsVpContext@345@U_IGVM_VHS_CVM_POLICY@@USnpVpContext@345@U_IGVM_VHS_TD_INFO@@UParameterArea@345@UVpCountParameter@345@UMmioRangesParameter@345@USratParameter@345@UMadtParameter@345@USlitParameter@345@UPpttParameter@345@UMemoryMapParameter@345@UCommandLineParameter@345@U_IGVM_VHS_PARAMETER_INSERT@@U_IGVM_VHS_REQUIRED_MEMORY@@U_IGVM_VHS_ERROR_RANGE@@U_IGVM_VHS_SNP_ID_BLOCK@@U_IGVM_VHS_VBS_MEASUREMENT@@URelocatableRegion@345@UPageTableRelocationRegion@345@UDeviceTreeParameter@345@URmeVpContext@345@@0@$$QEAV10@@Z; std::_Construct_in_place<std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>,std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>>(std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext> &,std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext> &&)
0x14006eab4  mov     byte ptr [rbx+1020h], 1
0x14006eabb  jmp     loc_14006EC3C
0x14006eac0  mov     rax, [r8]
0x14006eac3  mov     rdi, [r8+8]
0x14006eac7  mov     qword ptr [rsp+10D0h+var_10A0], rax
0x14006eacc  mov     qword ptr [rsp+10D0h+var_10A0+8], rdi
0x14006ead1  lea     rcx, [rsp+10D0h+var_10A0]
0x14006ead6  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x14006eadb  cmp     rax, 10h
0x14006eadf  jb      loc_14006EC84
0x14006eae5  lea     rcx, [rsp+10D0h+var_10A0]
0x14006eaea  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x14006eaef  mov     r8, r14
0x14006eaf2  mov     rdx, rsi
0x14006eaf5  mov     ecx, [rdi+8]
0x14006eaf8  call    ?PopulateSupportedPlatforms@Details@FileFormat@IsolatedVm@HyperVGuestLoader@@YAXIAEBV?$map@IIU?$less@I@std@@V?$allocator@U?$pair@$$CBII@std@@@2@@std@@AEAV?$optional@V?$set@IU?$less@I@std@@V?$allocator@I@2@@std@@@6@@Z; HyperVGuestLoader::IsolatedVm::FileFormat::Details::PopulateSupportedPlatforms(uint,std::map<uint,uint> const &,std::optional<std::set<uint>> &)
0x14006eafd  movups  xmm0, xmmword ptr [rdi]
0x14006eb00  movdqu  [rsp+10D0h+var_1058], xmm0
0x14006eb06  mov     [rbp+0FD0h+var_40], 3
0x14006eb0d  mov     [rbp+0FD0h+var_38], r13b
0x14006eb14  cmp     [rbx+1020h], r12b
0x14006eb1b  jz      loc_14006EC28
0x14006eb21  mov     ecx, 4
0x14006eb26  jmp     loc_14006EC12
0x14006eb2b  mov     rax, [r8]
0x14006eb2e  mov     rdi, [r8+8]
0x14006eb32  mov     qword ptr [rsp+10D0h+var_10A0], rax
0x14006eb37  mov     qword ptr [rsp+10D0h+var_10A0+8], rdi
0x14006eb3c  lea     rcx, [rsp+10D0h+var_10A0]
0x14006eb41  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x14006eb46  cmp     rax, 10h
0x14006eb4a  jb      loc_14006EC84
0x14006eb50  lea     rcx, [rsp+10D0h+var_10A0]
0x14006eb55  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x14006eb5a  cmp     [rdi], r12d
0x14006eb5d  jz      loc_14006EC65
0x14006eb63  mov     edx, [rdi]
0x14006eb65  lea     rax, [rdx-1]
0x14006eb69  test    rdx, rax
0x14006eb6c  jnz     loc_14006EC65
0x14006eb72  mov     r8, rdi
0x14006eb75  lea     rdx, [rsp+10D0h+var_10A0]
0x14006eb7a  mov     rcx, r15
0x14006eb7d  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@I@std@@@std@@@std@@_N@1@AEBI@Z; std::_Tree<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>::insert<0,0>(uint const &)
0x14006eb82  cmp     byte ptr [rsp+10D0h+var_10A0+8], r12b
0x14006eb87  jnz     short loc_14006EBA8
0x14006eb89  mov     rcx, [rbp+0FD8h]; this
0x14006eb90  mov     r9d, 80070057h; char *
0x14006eb96  lea     r8, aOnecoreVmCommo_59; "onecore\\vm\\common\\guestloader\\lib\\"...
0x14006eb9d  mov     edx, 28Ah; void *
0x14006eba2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006eba8  lea     r8, [rdi+5]
0x14006ebac  mov     r9, rdi
0x14006ebaf  lea     rdx, [rsp+10D0h+var_10A0]
0x14006ebb4  mov     rcx, rsi
0x14006ebb7  call    ??$_Emplace@AEBEAEBI@?$_Tree@V?$_Tmap_traits@IIU?$less@I@std@@V?$allocator@U?$pair@$$CBII@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBII@std@@PEAX@std@@_N@1@AEBEAEBI@Z; std::_Tree<std::_Tmap_traits<uint,uint,std::less<uint>,std::allocator<std::pair<uint const,uint>>,0>>::_Emplace<uchar const &,uint const &>(uchar const &,uint const &)
0x14006ebbc  cmp     byte ptr [rsp+10D0h+var_10A0+8], r12b
0x14006ebc1  jnz     short loc_14006EBE2
0x14006ebc3  mov     rcx, [rbp+0FD8h]; this
0x14006ebca  mov     r9d, 80070057h; char *
0x14006ebd0  lea     r8, aOnecoreVmCommo_59; "onecore\\vm\\common\\guestloader\\lib\\"...
0x14006ebd7  mov     edx, 291h; void *
0x14006ebdc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006ebe2  mov     r8, r14
0x14006ebe5  mov     rdx, rsi
0x14006ebe8  mov     ecx, [rdi]
0x14006ebea  call    ?PopulateSupportedPlatforms@Details@FileFormat@IsolatedVm@HyperVGuestLoader@@YAXIAEBV?$map@IIU?$less@I@std@@V?$allocator@U?$pair@$$CBII@std@@@2@@std@@AEAV?$optional@V?$set@IU?$less@I@std@@V?$allocator@I@2@@std@@@6@@Z; HyperVGuestLoader::IsolatedVm::FileFormat::Details::PopulateSupportedPlatforms(uint,std::map<uint,uint> const &,std::optional<std::set<uint>> &)
0x14006ebef  movups  xmm0, xmmword ptr [rdi]
0x14006ebf2  movdqu  [rsp+10D0h+var_1058], xmm0
0x14006ebf8  mov     [rbp+0FD0h+var_40], r12b
0x14006ebff  mov     [rbp+0FD0h+var_38], r13b
0x14006ec06  cmp     [rbx+1020h], r12b
0x14006ec0d  jz      short loc_14006EC28
0x14006ec0f  mov     rcx, r13
0x14006ec12  mov     qword ptr [rsp+10D0h+var_10B0], rbx
0x14006ec17  lea     r8, [rsp+10D0h+var_1058]
0x14006ec1c  lea     rdx, [rsp+10D0h+var_10B0]
0x14006ec21  call    ??$_Visit@U?$_Variant_assign_visitor@U_IGVM_VHS_SUPPORTED_PLATFORM@@UPageData@FileFormat@IsolatedVm@HyperVGuestLoader@@UVbsVpContext@345@U_IGVM_VHS_CVM_POLICY@@USnpVpContext@345@U_IGVM_VHS_TD_INFO@@UParameterArea@345@UVpCountParameter@345@UMmioRangesParameter@345@USratParameter@345@UMadtParameter@345@USlitParameter@345@UPpttParameter@345@UMemoryMapParameter@345@UCommandLineParameter@345@U_IGVM_VHS_PARAMETER_INSERT@@U_IGVM_VHS_REQUIRED_MEMORY@@U_IGVM_VHS_ERROR_RANGE@@U_IGVM_VHS_SNP_ID_BLOCK@@U_IGVM_VHS_VBS_MEASUREMENT@@URelocatableRegion@345@UPageTableRelocationRegion@345@UDeviceTreeParameter@345@URmeVpContext@345@@std@@V?$_Variant_storage_@$0A@U_IGVM_VHS_SUPPORTED_PLATFORM@@UPageData@FileFormat@IsolatedVm@HyperVGuestLoader@@UVbsVpContext@345@U_IGVM_VHS_CVM_POLICY@@USnpVpContext@345@U_IGVM_VHS_TD_INFO@@UParameterArea@345@UVpCountParameter@345@UMmioRangesParameter@345@USratParameter@345@UMadtParameter@345@USlitParameter@345@UPpttParameter@345@UMemoryMapParameter@345@UCommandLineParameter@345@U_IGVM_VHS_PARAMETER_INSERT@@U_IGVM_VHS_REQUIRED_MEMORY@@U_IGVM_VHS_ERROR_RANGE@@U_IGVM_VHS_SNP_ID_BLOCK@@U_IGVM_VHS_VBS_MEASUREMENT@@URelocatableRegion@345@UPageTableRelocationRegion@345@UDeviceTreeParameter@345@URmeVpContext@345@@2@@?$_Variant_raw_visit1@$02@std@@SAX_K$$QEAU?$_Variant_assign_visitor@U_IGVM_VHS_SUPPORTED_PLATFORM@@UPageData@FileFormat@IsolatedVm@HyperVGuestLoader@@UVbsVpContext@345@U_IGVM_VHS_CVM_POLICY@@USnpVpContext@345@U_IGVM_VHS_TD_INFO@@UParameterArea@345@UVpCountParameter@345@UMmioRangesParameter@345@USratParameter@345@UMadtParameter@345@USlitParameter@345@UPpttParameter@345@UMemoryMapParameter@345@UCommandLineParameter@345@U_IGVM_VHS_PARAMETER_INSERT@@U_IGVM_VHS_REQUIRED_MEMORY@@U_IGVM_VHS_ERROR_RANGE@@U_IGVM_VHS_SNP_ID_BLOCK@@U_IGVM_VHS_VBS_MEASUREMENT@@URelocatableRegion@345@UPageTableRelocationRegion@345@UDeviceTreeParameter@345@URmeVpContext@345@@1@$$QEAV?$_Variant_storage_@$0A@U_IGVM_VHS_SUPPORTED_PLATFORM@@UPageData@FileFormat@IsolatedVm@HyperVGuestLoader@@UVbsVpContext@345@U_IGVM_VHS_CVM_POLICY@@USnpVpContext@345@U_IGVM_VHS_TD_INFO@@UParameterArea@345@UVpCountParameter@345@UMmioRangesParameter@345@USratParameter@345@UMadtParameter@345@USlitParameter@345@UPpttParameter@345@UMemoryMapParameter@345@UCommandLineParameter@345@U_IGVM_VHS_PARAMETER_INSERT@@U_IGVM_VHS_REQUIRED_MEMORY@@U_IGVM_VHS_ERROR_RANGE@@U_IGVM_VHS_SNP_ID_BLOCK@@U_IGVM_VHS_VBS_MEASUREMENT@@URelocatableRegion@345@UPageTableRelocationRegion@345@UDeviceTreeParameter@345@URmeVpContext@345@@1@@Z
0x14006ec26  jmp     short loc_14006EC3C
0x14006ec28  lea     rdx, [rsp+10D0h+var_1058]
0x14006ec2d  mov     rcx, rbx
0x14006ec30  call    ??$_Construct_in_place@V?$variant@U_IGVM_VHS_SUPPORTED_PLATFORM@@UPageData@FileFormat@IsolatedVm@HyperVGuestLoader@@UVbsVpContext@345@U_IGVM_VHS_CVM_POLICY@@USnpVpContext@345@U_IGVM_VHS_TD_INFO@@UParameterArea@345@UVpCountParameter@345@UMmioRangesParameter@345@USratParameter@345@UMadtParameter@345@USlitParameter@345@UPpttParameter@345@UMemoryMapParameter@345@UCommandLineParameter@345@U_IGVM_VHS_PARAMETER_INSERT@@U_IGVM_VHS_REQUIRED_MEMORY@@U_IGVM_VHS_ERROR_RANGE@@U_IGVM_VHS_SNP_ID_BLOCK@@U_IGVM_VHS_VBS_MEASUREMENT@@URelocatableRegion@345@UPageTableRelocationRegion@345@UDeviceTreeParameter@345@URmeVpContext@345@@std@@V12@@std@@YAXAEAV?$variant@U_IGVM_VHS_SUPPORTED_PLATFORM@@UPageData@FileFormat@IsolatedVm@HyperVGuestLoader@@UVbsVpContext@345@U_IGVM_VHS_CVM_POLICY@@USnpVpContext@345@U_IGVM_VHS_TD_INFO@@UParameterArea@345@UVpCountParameter@345@UMmioRangesParameter@345@USratParameter@345@UMadtParameter@345@USlitParameter@345@UPpttParameter@345@UMemoryMapParameter@345@UCommandLineParameter@345@U_IGVM_VHS_PARAMETER_INSERT@@U_IGVM_VHS_REQUIRED_MEMORY@@U_IGVM_VHS_ERROR_RANGE@@U_IGVM_VHS_SNP_ID_BLOCK@@U_IGVM_VHS_VBS_MEASUREMENT@@URelocatableRegion@345@UPageTableRelocationRegion@345@UDeviceTreeParameter@345@URmeVpContext@345@@0@$$QEAV10@@Z; std::_Construct_in_place<std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>,std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>>(std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext> &,std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext> &&)
0x14006ec35  mov     [rbx+1020h], r13b
0x14006ec3c  lea     rcx, [rsp+10D0h+var_1058]
0x14006ec41  call    ??1?$_Optional_destruct_base@V?$variant@U_IGVM_VHS_SUPPORTED_PLATFORM@@UPageData@FileFormat@IsolatedVm@HyperVGuestLoader@@UVbsVpContext@345@U_IGVM_VHS_CVM_POLICY@@USnpVpContext@345@U_IGVM_VHS_TD_INFO@@UParameterArea@345@UVpCountParameter@345@UMmioRangesParameter@345@USratParameter@345@UMadtParameter@345@USlitParameter@345@UPpttParameter@345@UMemoryMapParameter@345@UCommandLineParameter@345@U_IGVM_VHS_PARAMETER_INSERT@@U_IGVM_VHS_REQUIRED_MEMORY@@U_IGVM_VHS_ERROR_RANGE@@U_IGVM_VHS_SNP_ID_BLOCK@@U_IGVM_VHS_VBS_MEASUREMENT@@URelocatableRegion@345@UPageTableRelocationRegion@345@UDeviceTreeParameter@345@URmeVpContext@345@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>,0>::~_Optional_destruct_base<std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>,0>(void)
0x14006ec46  mov     rax, rbx
  ... truncated ...
```
