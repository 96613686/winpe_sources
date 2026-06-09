# HyperVGuestLoader::IsolatedVm::FileFormat::Details::UnmarshalPlatform(uint,gsl::span<gsl::byte const,-1>,std::set<uint,std::less<uint>,std::allocator<uint>> &,std::map<uint,uint,std::less<uint>,std::allocator<std::pair<uint const,uint>>> &,std::optional<std::set<uint,std::less<uint>,std::allocator<uint>>> &)

- ea: `0x1400999d0`
- end: `0x140099f71`
- name: `?UnmarshalPlatform@Details@FileFormat@IsolatedVm@HyperVGuestLoader@@YA?AV?$optional@V?$variant@U_IGVM_VHS_SUPPORTED_PLATFORM@@UPageData@FileFormat@IsolatedVm@HyperVGuestLoader@@UVbsVpContext@345@U_IGVM_VHS_CVM_POLICY@@USnpVpContext@345@U_IGVM_VHS_TD_INFO@@UParameterArea@345@UVpCountParameter@345@UMmioRangesParameter@345@USratParameter@345@UMadtParameter@345@USlitParameter@345@UPpttParameter@345@UMemoryMapParameter@345@UCommandLineParameter@345@U_IGVM_VHS_PARAMETER_INSERT@@U_IGVM_VHS_REQUIRED_MEMORY@@U_IGVM_VHS_ERROR_RANGE@@U_IGVM_VHS_SNP_ID_BLOCK@@U_IGVM_VHS_VBS_MEASUREMENT@@URelocatableRegion@345@UPageTableRelocationRegion@345@UDeviceTreeParameter@345@URmeVpContext@345@@std@@@std@@IV?$span@$$CBW4byte@gsl@@$0?0@gsl@@AEAV?$set@IU?$less@I@std@@V?$allocator@I@2@@6@AEAV?$map@IIU?$less@I@std@@V?$allocator@U?$pair@$$CBII@std@@@2@@6@AEAV?$optional@V?$set@IU?$less@I@std@@V?$allocator@I@2@@std@@@6@@Z`
- size: `1441`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400bec40`

## callees

- `0x140024cd8`
- `0x140078628`
- `0x14007a6cc`
- `0x1400999d0`
- `0x1401b1394`
- `0x1401b2368`
- `0x1401b242c`
- `0x1401b2ba4`
- `0x1401b3110`
- `0x1401b3778`
- `0x1401b49bc`
- `0x1402a28f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x140099f64`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x140099f64`

## string_xrefs

- `0x140099b24`: `onecore\vm\common\guestloader\lib\isolatedvmloaderformat.cpp`
- `0x140099b48`: `onecore\vm\common\guestloader\lib\isolatedvmloaderformat.cpp`
- `0x140099b6c`: `onecore\vm\common\guestloader\lib\isolatedvmloaderformat.cpp`
- `0x140099b90`: `onecore\vm\common\guestloader\lib\isolatedvmloaderformat.cpp`
- `0x140099c6d`: `onecore\vm\common\guestloader\lib\isolatedvmloaderformat.cpp`
- `0x140099c91`: `onecore\vm\common\guestloader\lib\isolatedvmloaderformat.cpp`
- `0x140099cbd`: `onecore\vm\common\guestloader\lib\isolatedvmloaderformat.cpp`
- `0x140099ce7`: `onecore\vm\common\guestloader\lib\isolatedvmloaderformat.cpp`
- `0x140099d11`: `onecore\vm\common\guestloader\lib\isolatedvmloaderformat.cpp`
- `0x140099e76`: `onecore\vm\common\guestloader\lib\isolatedvmloaderformat.cpp`
- `0x140099eb0`: `onecore\vm\common\guestloader\lib\isolatedvmloaderformat.cpp`
- `0x140099f52`: `onecore\vm\common\guestloader\lib\isolatedvmloaderformat.cpp`

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
    JUMPOUT(0x140099F71LL);
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
0x1400999d0  mov     [rsp-8+arg_8], rbx
0x1400999d5  push    rbp
0x1400999d6  push    rsi
0x1400999d7  push    rdi
0x1400999d8  push    r12
0x1400999da  push    r13
0x1400999dc  push    r14
0x1400999de  push    r15
0x1400999e0  lea     rbp, [rsp-0FA0h]
0x1400999e8  mov     eax, 10A0h
0x1400999ed  call    _alloca_probe
0x1400999f2  sub     rsp, rax
0x1400999f5  mov     r15, r9
0x1400999f8  mov     rbx, rcx
0x1400999fb  mov     qword ptr [rsp+10D0h+var_10B0], rcx; int
0x140099a00  mov     rsi, [rbp+0FD0h+arg_20]
0x140099a07  mov     r14, [rbp+0FD0h+arg_28]
0x140099a0e  xor     r12d, r12d
0x140099a11  mov     [rsp+10D0h+var_1060], r12d
0x140099a16  mov     [rcx+1020h], r12b
0x140099a1d  lea     r13d, [r12+1]
0x140099a22  mov     [rsp+10D0h+var_1060], r13d
0x140099a27  sub     edx, r13d
0x140099a2a  jz      loc_140099E0B
0x140099a30  sub     edx, 100h
0x140099a36  jz      loc_140099DA0
0x140099a3c  sub     edx, r13d
0x140099a3f  jz      loc_140099BD9
0x140099a45  sub     edx, r13d
0x140099a48  jz      short loc_140099AB1
0x140099a4a  cmp     edx, 0FCh
0x140099a50  jnz     loc_140099F26
0x140099a56  mov     rax, [r8]
0x140099a59  mov     rdi, [r8+8]
0x140099a5d  mov     qword ptr [rsp+10D0h+var_10A0], rax
0x140099a62  mov     qword ptr [rsp+10D0h+var_10A0+8], rdi
0x140099a67  lea     rcx, [rsp+10D0h+var_10A0]
0x140099a6c  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140099a71  cmp     rax, 10h
0x140099a75  jb      loc_140099F64
0x140099a7b  lea     rcx, [rsp+10D0h+var_10A0]
0x140099a80  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140099a85  mov     r8, r14
0x140099a88  mov     rdx, rsi
0x140099a8b  mov     ecx, [rdi]
0x140099a8d  call    ?PopulateSupportedPlatforms@Details@FileFormat@IsolatedVm@HyperVGuestLoader@@YAXIAEBV?$map@IIU?$less@I@std@@V?$allocator@U?$pair@$$CBII@std@@@2@@std@@AEAV?$optional@V?$set@IU?$less@I@std@@V?$allocator@I@2@@std@@@6@@Z; HyperVGuestLoader::IsolatedVm::FileFormat::Details::PopulateSupportedPlatforms(uint,std::map<uint,uint> const &,std::optional<std::set<uint>> &)
0x140099a92  mov     rdx, rdi
0x140099a95  lea     rcx, [rsp+10D0h+var_1058]
0x140099a9a  call    ??$?0AEBU_IGVM_VHS_TD_INFO@@$0A@@?$optional@V?$variant@U_IGVM_VHS_SUPPORTED_PLATFORM@@UPageData@FileFormat@IsolatedVm@HyperVGuestLoader@@UVbsVpContext@345@U_IGVM_VHS_CVM_POLICY@@USnpVpContext@345@U_IGVM_VHS_TD_INFO@@UParameterArea@345@UVpCountParameter@345@UMmioRangesParameter@345@USratParameter@345@UMadtParameter@345@USlitParameter@345@UPpttParameter@345@UMemoryMapParameter@345@UCommandLineParameter@345@U_IGVM_VHS_PARAMETER_INSERT@@U_IGVM_VHS_REQUIRED_MEMORY@@U_IGVM_VHS_ERROR_RANGE@@U_IGVM_VHS_SNP_ID_BLOCK@@U_IGVM_VHS_VBS_MEASUREMENT@@URelocatableRegion@345@UPageTableRelocationRegion@345@UDeviceTreeParameter@345@URmeVpContext@345@@std@@@std@@QEAA@AEBU_IGVM_VHS_TD_INFO@@@Z; std::optional<std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>>::optional<std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>>(_IGVM_VHS_TD_INFO const &)
0x140099a9f  lea     rdx, [rsp+10D0h+var_1058]
0x140099aa4  mov     rcx, rbx
0x140099aa7  call    ??$_Assign_from@U?$_Optional_construct_base@V?$variant@U_IGVM_VHS_SUPPORTED_PLATFORM@@UPageData@FileFormat@IsolatedVm@HyperVGuestLoader@@UVbsVpContext@345@U_IGVM_VHS_CVM_POLICY@@USnpVpContext@345@U_IGVM_VHS_TD_INFO@@UParameterArea@345@UVpCountParameter@345@UMmioRangesParameter@345@USratParameter@345@UMadtParameter@345@USlitParameter@345@UPpttParameter@345@UMemoryMapParameter@345@UCommandLineParameter@345@U_IGVM_VHS_PARAMETER_INSERT@@U_IGVM_VHS_REQUIRED_MEMORY@@U_IGVM_VHS_ERROR_RANGE@@U_IGVM_VHS_SNP_ID_BLOCK@@U_IGVM_VHS_VBS_MEASUREMENT@@URelocatableRegion@345@UPageTableRelocationRegion@345@UDeviceTreeParameter@345@URmeVpContext@345@@std@@@std@@@?$_Optional_construct_base@V?$variant@U_IGVM_VHS_SUPPORTED_PLATFORM@@UPageData@FileFormat@IsolatedVm@HyperVGuestLoader@@UVbsVpContext@345@U_IGVM_VHS_CVM_POLICY@@USnpVpContext@345@U_IGVM_VHS_TD_INFO@@UParameterArea@345@UVpCountParameter@345@UMmioRangesParameter@345@USratParameter@345@UMadtParameter@345@USlitParameter@345@UPpttParameter@345@UMemoryMapParameter@345@UCommandLineParameter@345@U_IGVM_VHS_PARAMETER_INSERT@@U_IGVM_VHS_REQUIRED_MEMORY@@U_IGVM_VHS_ERROR_RANGE@@U_IGVM_VHS_SNP_ID_BLOCK@@U_IGVM_VHS_VBS_MEASUREMENT@@URelocatableRegion@345@UPageTableRelocationRegion@345@UDeviceTreeParameter@345@URmeVpContext@345@@std@@@std@@QEAAX$$QEAU01@@Z; std::_Optional_construct_base<std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>>::_Assign_from<std::_Optional_construct_base<std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>>>(std::_Optional_construct_base<std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>> &&)
0x140099aac  jmp     loc_140099F1C
0x140099ab1  mov     rax, [r8]
0x140099ab4  mov     rdi, [r8+8]
0x140099ab8  mov     qword ptr [rsp+10D0h+var_10A0], rax
0x140099abd  mov     qword ptr [rsp+10D0h+var_10A0+8], rdi
0x140099ac2  lea     rcx, [rsp+10D0h+var_10A0]
0x140099ac7  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140099acc  cmp     rax, 20h ; ' '
0x140099ad0  jb      loc_140099F64
0x140099ad6  lea     rcx, [rsp+10D0h+var_10A0]
0x140099adb  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140099ae0  mov     r8, r14
0x140099ae3  mov     rdx, rsi
0x140099ae6  mov     ecx, [rdi]
0x140099ae8  call    ?PopulateSupportedPlatforms@Details@FileFormat@IsolatedVm@HyperVGuestLoader@@YAXIAEBV?$map@IIU?$less@I@std@@V?$allocator@U?$pair@$$CBII@std@@@2@@std@@AEAV?$optional@V?$set@IU?$less@I@std@@V?$allocator@I@2@@std@@@6@@Z; HyperVGuestLoader::IsolatedVm::FileFormat::Details::PopulateSupportedPlatforms(uint,std::map<uint,uint> const &,std::optional<std::set<uint>> &)
0x140099aed  xorps   xmm0, xmm0
0x140099af0  movups  [rsp+10D0h+var_10A0], xmm0
0x140099af5  mov     r9d, [rdi]
0x140099af8  mov     r8, [rdi+8]
0x140099afc  mov     rcx, [rdi+10h]
0x140099b00  mov     rdx, [rdi+18h]
0x140099b04  movzx   r10d, word ptr [rdi+4]
0x140099b09  mov     r11b, [rdi+6]
0x140099b0d  mov     eax, 0FFFh
0x140099b12  test    rax, r8
0x140099b15  jz      short loc_140099B36
0x140099b17  mov     rcx, [rbp+0FD8h]; this
0x140099b1e  mov     r9d, 80070057h; char *
0x140099b24  lea     r8, aOnecoreVmCommo_59; "onecore\\vm\\common\\guestloader\\lib\\"...
0x140099b2b  mov     edx, 2DBh; void *
0x140099b30  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140099b36  test    rax, rcx
0x140099b39  jz      short loc_140099B5A
0x140099b3b  mov     rcx, [rbp+0FD8h]; this
0x140099b42  mov     r9d, 80070057h; char *
0x140099b48  lea     r8, aOnecoreVmCommo_59; "onecore\\vm\\common\\guestloader\\lib\\"...
0x140099b4f  mov     edx, 2E0h; void *
0x140099b54  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140099b5a  test    rax, rdx
0x140099b5d  jz      short loc_140099B7E
0x140099b5f  mov     rcx, [rbp+0FD8h]; this
0x140099b66  mov     r9d, 80070057h; char *
0x140099b6c  lea     r8, aOnecoreVmCommo_59; "onecore\\vm\\common\\guestloader\\lib\\"...
0x140099b73  mov     edx, 2E5h; void *
0x140099b78  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140099b7e  cmp     rdx, rcx
0x140099b81  jbe     short loc_140099BA2
0x140099b83  mov     rcx, [rbp+0FD8h]; this
0x140099b8a  mov     r9d, 80070057h; char *
0x140099b90  lea     r8, aOnecoreVmCommo_59; "onecore\\vm\\common\\guestloader\\lib\\"...
0x140099b97  mov     edx, 2EAh; void *
0x140099b9c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140099ba2  mov     dword ptr [rsp+10D0h+var_1058], r9d
0x140099ba7  mov     word ptr [rsp+10D0h+var_1058+4], r10w
0x140099bad  mov     byte ptr [rsp+10D0h+var_1058+6], r11b
0x140099bb2  mov     al, byte ptr [rsp+10D0h+var_10A0+7]
0x140099bb6  mov     byte ptr [rsp+10D0h+var_1058+7], al
0x140099bba  mov     qword ptr [rbp+0FD0h+var_1058+8], r8
0x140099bbe  mov     [rbp+0FD0h+var_1048], rcx
0x140099bc2  mov     [rbp+0FD0h+var_1040], rdx
0x140099bc6  mov     [rbp+0FD0h+var_40], 15h
0x140099bcd  mov     [rbp+0FD0h+var_38], r13b
0x140099bd4  jmp     loc_140099A9F
0x140099bd9  mov     rax, [r8]
0x140099bdc  mov     rdi, [r8+8]
0x140099be0  mov     qword ptr [rsp+10D0h+var_10A0], rax
0x140099be5  mov     qword ptr [rsp+10D0h+var_10A0+8], rdi
0x140099bea  lea     rcx, [rsp+10D0h+var_10A0]
0x140099bef  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140099bf4  cmp     rax, 30h ; '0'
0x140099bf8  jb      loc_140099F64
0x140099bfe  lea     rcx, [rsp+10D0h+var_10A0]
0x140099c03  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140099c08  mov     r8, r14
0x140099c0b  mov     rdx, rsi
0x140099c0e  mov     ecx, [rdi]
0x140099c10  call    ?PopulateSupportedPlatforms@Details@FileFormat@IsolatedVm@HyperVGuestLoader@@YAXIAEBV?$map@IIU?$less@I@std@@V?$allocator@U?$pair@$$CBII@std@@@2@@std@@AEAV?$optional@V?$set@IU?$less@I@std@@V?$allocator@I@2@@std@@@6@@Z; HyperVGuestLoader::IsolatedVm::FileFormat::Details::PopulateSupportedPlatforms(uint,std::map<uint,uint> const &,std::optional<std::set<uint>> &)
0x140099c15  xorps   xmm0, xmm0
0x140099c18  movups  [rsp+10D0h+var_10A0], xmm0
0x140099c1d  mov     r12d, [rdi]
0x140099c20  movzx   r13d, word ptr [rdi+4]
0x140099c25  mov     r8b, [rdi+7]
0x140099c29  mov     r14b, r8b
0x140099c2c  and     r14b, 1
0x140099c30  mov     sil, r8b
0x140099c33  shr     sil, 1
0x140099c36  and     sil, 1
0x140099c3a  shr     r8b, 2
0x140099c3e  and     r8b, 1
0x140099c42  mov     rcx, [rdi+8]
0x140099c46  mov     r11, [rdi+10h]
0x140099c4a  mov     r15, [rdi+18h]
0x140099c4e  mov     r10, [rdi+20h]
0x140099c52  mov     r9, [rdi+28h]
0x140099c56  mov     eax, 0FFFh
0x140099c5b  test    rax, r15
0x140099c5e  jz      short loc_140099C7F
0x140099c60  mov     rcx, [rbp+0FD8h]; this
0x140099c67  mov     r9d, 80070057h; char *
0x140099c6d  lea     r8, aOnecoreVmCommo_59; "onecore\\vm\\common\\guestloader\\lib\\"...
0x140099c74  mov     edx, 2B3h; void *
0x140099c79  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140099c7f  test    rax, rcx
0x140099c82  jz      short loc_140099CA3
0x140099c84  mov     rcx, [rbp+0FD8h]; this
0x140099c8b  mov     r9d, 80070057h; char *
0x140099c91  lea     r8, aOnecoreVmCommo_59; "onecore\\vm\\common\\guestloader\\lib\\"...
0x140099c98  mov     edx, 2B8h; void *
0x140099c9d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140099ca3  xor     edx, edx
0x140099ca5  mov     rax, r11
0x140099ca8  div     rcx
0x140099cab  test    rdx, rdx
0x140099cae  jz      short loc_140099CCF
0x140099cb0  mov     rcx, [rbp+0FD8h]; this
0x140099cb7  mov     r9d, 80070057h; char *
0x140099cbd  lea     r8, aOnecoreVmCommo_59; "onecore\\vm\\common\\guestloader\\lib\\"...
0x140099cc4  mov     edx, 2BDh; void *
0x140099cc9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140099ccf  mov     rax, r10
0x140099cd2  div     rcx
0x140099cd5  test    rdx, rdx
0x140099cd8  jz      short loc_140099CF9
0x140099cda  mov     rcx, [rbp+0FD8h]; this
0x140099ce1  mov     r9d, 80070057h; char *
0x140099ce7  lea     r8, aOnecoreVmCommo_59; "onecore\\vm\\common\\guestloader\\lib\\"...
0x140099cee  mov     edx, 2C2h; void *
0x140099cf3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140099cf9  mov     rax, r9
0x140099cfc  div     rcx
0x140099cff  test    rdx, rdx
0x140099d02  jz      short loc_140099D23
0x140099d04  mov     rcx, [rbp+0FD8h]; this
0x140099d0b  mov     r9d, 80070057h; char *
0x140099d11  lea     r8, aOnecoreVmCommo_59; "onecore\\vm\\common\\guestloader\\lib\\"...
0x140099d18  mov     edx, 2C7h; void *
0x140099d1d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140099d23  mov     dword ptr [rsp+10D0h+var_1058], r12d
0x140099d28  mov     word ptr [rsp+10D0h+var_1058+4], r13w
0x140099d2e  mov     al, [rdi+6]
0x140099d31  mov     byte ptr [rsp+10D0h+var_1058+6], al
0x140099d35  mov     byte ptr [rsp+10D0h+var_1058+7], r14b
0x140099d3a  mov     byte ptr [rbp+0FD0h+var_1058+8], sil
0x140099d3e  mov     byte ptr [rbp+0FD0h+var_1058+9], r8b
0x140099d42  mov     eax, dword ptr [rsp+10D0h+var_10A0+0Ah]
0x140099d46  mov     dword ptr [rbp+0FD0h+var_1058+0Ah], eax
0x140099d49  movzx   eax, word ptr [rsp+10D0h+var_10A0+0Eh]
0x140099d4e  mov     word ptr [rbp+0FD0h+var_1058+0Eh], ax
0x140099d52  mov     [rbp+0FD0h+var_1048], rcx
0x140099d56  mov     [rbp+0FD0h+var_1040], r11
0x140099d5a  mov     [rbp+0FD0h+var_1038], r15
0x140099d5e  mov     [rbp+0FD0h+var_1030], r10
0x140099d62  mov     [rbp+0FD0h+var_1028], r9
0x140099d66  mov     [rbp+0FD0h+var_40], 14h
0x140099d6d  mov     [rbp+0FD0h+var_38], 1
0x140099d74  cmp     byte ptr [rbx+1020h], 0
0x140099d7b  jz      short loc_140099D87
0x140099d7d  mov     ecx, 15h
0x140099d82  jmp     loc_140099EF2
0x140099d87  lea     rdx, [rsp+10D0h+var_1058]
0x140099d8c  mov     rcx, rbx
0x140099d8f  call    ??$_Construct_in_place@V?$variant@U_IGVM_VHS_SUPPORTED_PLATFORM@@UPageData@FileFormat@IsolatedVm@HyperVGuestLoader@@UVbsVpContext@345@U_IGVM_VHS_CVM_POLICY@@USnpVpContext@345@U_IGVM_VHS_TD_INFO@@UParameterArea@345@UVpCountParameter@345@UMmioRangesParameter@345@USratParameter@345@UMadtParameter@345@USlitParameter@345@UPpttParameter@345@UMemoryMapParameter@345@UCommandLineParameter@345@U_IGVM_VHS_PARAMETER_INSERT@@U_IGVM_VHS_REQUIRED_MEMORY@@U_IGVM_VHS_ERROR_RANGE@@U_IGVM_VHS_SNP_ID_BLOCK@@U_IGVM_VHS_VBS_MEASUREMENT@@URelocatableRegion@345@UPageTableRelocationRegion@345@UDeviceTreeParameter@345@URmeVpContext@345@@std@@V12@@std@@YAXAEAV?$variant@U_IGVM_VHS_SUPPORTED_PLATFORM@@UPageData@FileFormat@IsolatedVm@HyperVGuestLoader@@UVbsVpContext@345@U_IGVM_VHS_CVM_POLICY@@USnpVpContext@345@U_IGVM_VHS_TD_INFO@@UParameterArea@345@UVpCountParameter@345@UMmioRangesParameter@345@USratParameter@345@UMadtParameter@345@USlitParameter@345@UPpttParameter@345@UMemoryMapParameter@345@UCommandLineParameter@345@U_IGVM_VHS_PARAMETER_INSERT@@U_IGVM_VHS_REQUIRED_MEMORY@@U_IGVM_VHS_ERROR_RANGE@@U_IGVM_VHS_SNP_ID_BLOCK@@U_IGVM_VHS_VBS_MEASUREMENT@@URelocatableRegion@345@UPageTableRelocationRegion@345@UDeviceTreeParameter@345@URmeVpContext@345@@0@$$QEAV10@@Z; std::_Construct_in_place<std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>,std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>>(std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext> &,std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext> &&)
0x140099d94  mov     byte ptr [rbx+1020h], 1
0x140099d9b  jmp     loc_140099F1C
0x140099da0  mov     rax, [r8]
0x140099da3  mov     rdi, [r8+8]
0x140099da7  mov     qword ptr [rsp+10D0h+var_10A0], rax
0x140099dac  mov     qword ptr [rsp+10D0h+var_10A0+8], rdi
0x140099db1  lea     rcx, [rsp+10D0h+var_10A0]
0x140099db6  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140099dbb  cmp     rax, 10h
0x140099dbf  jb      loc_140099F64
0x140099dc5  lea     rcx, [rsp+10D0h+var_10A0]
0x140099dca  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140099dcf  mov     r8, r14
0x140099dd2  mov     rdx, rsi
0x140099dd5  mov     ecx, [rdi+8]
0x140099dd8  call    ?PopulateSupportedPlatforms@Details@FileFormat@IsolatedVm@HyperVGuestLoader@@YAXIAEBV?$map@IIU?$less@I@std@@V?$allocator@U?$pair@$$CBII@std@@@2@@std@@AEAV?$optional@V?$set@IU?$less@I@std@@V?$allocator@I@2@@std@@@6@@Z; HyperVGuestLoader::IsolatedVm::FileFormat::Details::PopulateSupportedPlatforms(uint,std::map<uint,uint> const &,std::optional<std::set<uint>> &)
0x140099ddd  movups  xmm0, xmmword ptr [rdi]
0x140099de0  movdqu  [rsp+10D0h+var_1058], xmm0
0x140099de6  mov     [rbp+0FD0h+var_40], 3
0x140099ded  mov     [rbp+0FD0h+var_38], r13b
0x140099df4  cmp     [rbx+1020h], r12b
0x140099dfb  jz      loc_140099F08
0x140099e01  mov     ecx, 4
0x140099e06  jmp     loc_140099EF2
0x140099e0b  mov     rax, [r8]
0x140099e0e  mov     rdi, [r8+8]
0x140099e12  mov     qword ptr [rsp+10D0h+var_10A0], rax
0x140099e17  mov     qword ptr [rsp+10D0h+var_10A0+8], rdi
0x140099e1c  lea     rcx, [rsp+10D0h+var_10A0]
0x140099e21  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140099e26  cmp     rax, 10h
0x140099e2a  jb      loc_140099F64
0x140099e30  lea     rcx, [rsp+10D0h+var_10A0]
0x140099e35  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140099e3a  cmp     [rdi], r12d
0x140099e3d  jz      loc_140099F45
0x140099e43  mov     edx, [rdi]
0x140099e45  lea     rax, [rdx-1]
0x140099e49  test    rdx, rax
0x140099e4c  jnz     loc_140099F45
0x140099e52  mov     r8, rdi
0x140099e55  lea     rdx, [rsp+10D0h+var_10A0]
0x140099e5a  mov     rcx, r15
0x140099e5d  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@I@std@@@std@@@std@@_N@1@AEBI@Z; std::_Tree<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>::insert<0,0>(uint const &)
0x140099e62  cmp     byte ptr [rsp+10D0h+var_10A0+8], r12b
0x140099e67  jnz     short loc_140099E88
0x140099e69  mov     rcx, [rbp+0FD8h]; this
0x140099e70  mov     r9d, 80070057h; char *
0x140099e76  lea     r8, aOnecoreVmCommo_59; "onecore\\vm\\common\\guestloader\\lib\\"...
0x140099e7d  mov     edx, 28Ah; void *
0x140099e82  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140099e88  lea     r8, [rdi+5]
0x140099e8c  mov     r9, rdi
0x140099e8f  lea     rdx, [rsp+10D0h+var_10A0]
0x140099e94  mov     rcx, rsi
0x140099e97  call    ??$_Emplace@AEBEAEBI@?$_Tree@V?$_Tmap_traits@IIU?$less@I@std@@V?$allocator@U?$pair@$$CBII@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBII@std@@PEAX@std@@_N@1@AEBEAEBI@Z; std::_Tree<std::_Tmap_traits<uint,uint,std::less<uint>,std::allocator<std::pair<uint const,uint>>,0>>::_Emplace<uchar const &,uint const &>(uchar const &,uint const &)
0x140099e9c  cmp     byte ptr [rsp+10D0h+var_10A0+8], r12b
0x140099ea1  jnz     short loc_140099EC2
0x140099ea3  mov     rcx, [rbp+0FD8h]; this
0x140099eaa  mov     r9d, 80070057h; char *
0x140099eb0  lea     r8, aOnecoreVmCommo_59; "onecore\\vm\\common\\guestloader\\lib\\"...
0x140099eb7  mov     edx, 291h; void *
0x140099ebc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140099ec2  mov     r8, r14
0x140099ec5  mov     rdx, rsi
0x140099ec8  mov     ecx, [rdi]
0x140099eca  call    ?PopulateSupportedPlatforms@Details@FileFormat@IsolatedVm@HyperVGuestLoader@@YAXIAEBV?$map@IIU?$less@I@std@@V?$allocator@U?$pair@$$CBII@std@@@2@@std@@AEAV?$optional@V?$set@IU?$less@I@std@@V?$allocator@I@2@@std@@@6@@Z; HyperVGuestLoader::IsolatedVm::FileFormat::Details::PopulateSupportedPlatforms(uint,std::map<uint,uint> const &,std::optional<std::set<uint>> &)
0x140099ecf  movups  xmm0, xmmword ptr [rdi]
0x140099ed2  movdqu  [rsp+10D0h+var_1058], xmm0
0x140099ed8  mov     [rbp+0FD0h+var_40], r12b
0x140099edf  mov     [rbp+0FD0h+var_38], r13b
0x140099ee6  cmp     [rbx+1020h], r12b
0x140099eed  jz      short loc_140099F08
0x140099eef  mov     rcx, r13
0x140099ef2  mov     qword ptr [rsp+10D0h+var_10B0], rbx
0x140099ef7  lea     r8, [rsp+10D0h+var_1058]
0x140099efc  lea     rdx, [rsp+10D0h+var_10B0]
0x140099f01  call    ??$_Visit@U?$_Variant_assign_visitor@U_IGVM_VHS_SUPPORTED_PLATFORM@@UPageData@FileFormat@IsolatedVm@HyperVGuestLoader@@UVbsVpContext@345@U_IGVM_VHS_CVM_POLICY@@USnpVpContext@345@U_IGVM_VHS_TD_INFO@@UParameterArea@345@UVpCountParameter@345@UMmioRangesParameter@345@USratParameter@345@UMadtParameter@345@USlitParameter@345@UPpttParameter@345@UMemoryMapParameter@345@UCommandLineParameter@345@U_IGVM_VHS_PARAMETER_INSERT@@U_IGVM_VHS_REQUIRED_MEMORY@@U_IGVM_VHS_ERROR_RANGE@@U_IGVM_VHS_SNP_ID_BLOCK@@U_IGVM_VHS_VBS_MEASUREMENT@@URelocatableRegion@345@UPageTableRelocationRegion@345@UDeviceTreeParameter@345@URmeVpContext@345@@std@@V?$_Variant_storage_@$0A@U_IGVM_VHS_SUPPORTED_PLATFORM@@UPageData@FileFormat@IsolatedVm@HyperVGuestLoader@@UVbsVpContext@345@U_IGVM_VHS_CVM_POLICY@@USnpVpContext@345@U_IGVM_VHS_TD_INFO@@UParameterArea@345@UVpCountParameter@345@UMmioRangesParameter@345@USratParameter@345@UMadtParameter@345@USlitParameter@345@UPpttParameter@345@UMemoryMapParameter@345@UCommandLineParameter@345@U_IGVM_VHS_PARAMETER_INSERT@@U_IGVM_VHS_REQUIRED_MEMORY@@U_IGVM_VHS_ERROR_RANGE@@U_IGVM_VHS_SNP_ID_BLOCK@@U_IGVM_VHS_VBS_MEASUREMENT@@URelocatableRegion@345@UPageTableRelocationRegion@345@UDeviceTreeParameter@345@URmeVpContext@345@@2@@?$_Variant_raw_visit1@$02@std@@SAX_K$$QEAU?$_Variant_assign_visitor@U_IGVM_VHS_SUPPORTED_PLATFORM@@UPageData@FileFormat@IsolatedVm@HyperVGuestLoader@@UVbsVpContext@345@U_IGVM_VHS_CVM_POLICY@@USnpVpContext@345@U_IGVM_VHS_TD_INFO@@UParameterArea@345@UVpCountParameter@345@UMmioRangesParameter@345@USratParameter@345@UMadtParameter@345@USlitParameter@345@UPpttParameter@345@UMemoryMapParameter@345@UCommandLineParameter@345@U_IGVM_VHS_PARAMETER_INSERT@@U_IGVM_VHS_REQUIRED_MEMORY@@U_IGVM_VHS_ERROR_RANGE@@U_IGVM_VHS_SNP_ID_BLOCK@@U_IGVM_VHS_VBS_MEASUREMENT@@URelocatableRegion@345@UPageTableRelocationRegion@345@UDeviceTreeParameter@345@URmeVpContext@345@@1@$$QEAV?$_Variant_storage_@$0A@U_IGVM_VHS_SUPPORTED_PLATFORM@@UPageData@FileFormat@IsolatedVm@HyperVGuestLoader@@UVbsVpContext@345@U_IGVM_VHS_CVM_POLICY@@USnpVpContext@345@U_IGVM_VHS_TD_INFO@@UParameterArea@345@UVpCountParameter@345@UMmioRangesParameter@345@USratParameter@345@UMadtParameter@345@USlitParameter@345@UPpttParameter@345@UMemoryMapParameter@345@UCommandLineParameter@345@U_IGVM_VHS_PARAMETER_INSERT@@U_IGVM_VHS_REQUIRED_MEMORY@@U_IGVM_VHS_ERROR_RANGE@@U_IGVM_VHS_SNP_ID_BLOCK@@U_IGVM_VHS_VBS_MEASUREMENT@@URelocatableRegion@345@UPageTableRelocationRegion@345@UDeviceTreeParameter@345@URmeVpContext@345@@1@@Z
0x140099f06  jmp     short loc_140099F1C
0x140099f08  lea     rdx, [rsp+10D0h+var_1058]
0x140099f0d  mov     rcx, rbx
0x140099f10  call    ??$_Construct_in_place@V?$variant@U_IGVM_VHS_SUPPORTED_PLATFORM@@UPageData@FileFormat@IsolatedVm@HyperVGuestLoader@@UVbsVpContext@345@U_IGVM_VHS_CVM_POLICY@@USnpVpContext@345@U_IGVM_VHS_TD_INFO@@UParameterArea@345@UVpCountParameter@345@UMmioRangesParameter@345@USratParameter@345@UMadtParameter@345@USlitParameter@345@UPpttParameter@345@UMemoryMapParameter@345@UCommandLineParameter@345@U_IGVM_VHS_PARAMETER_INSERT@@U_IGVM_VHS_REQUIRED_MEMORY@@U_IGVM_VHS_ERROR_RANGE@@U_IGVM_VHS_SNP_ID_BLOCK@@U_IGVM_VHS_VBS_MEASUREMENT@@URelocatableRegion@345@UPageTableRelocationRegion@345@UDeviceTreeParameter@345@URmeVpContext@345@@std@@V12@@std@@YAXAEAV?$variant@U_IGVM_VHS_SUPPORTED_PLATFORM@@UPageData@FileFormat@IsolatedVm@HyperVGuestLoader@@UVbsVpContext@345@U_IGVM_VHS_CVM_POLICY@@USnpVpContext@345@U_IGVM_VHS_TD_INFO@@UParameterArea@345@UVpCountParameter@345@UMmioRangesParameter@345@USratParameter@345@UMadtParameter@345@USlitParameter@345@UPpttParameter@345@UMemoryMapParameter@345@UCommandLineParameter@345@U_IGVM_VHS_PARAMETER_INSERT@@U_IGVM_VHS_REQUIRED_MEMORY@@U_IGVM_VHS_ERROR_RANGE@@U_IGVM_VHS_SNP_ID_BLOCK@@U_IGVM_VHS_VBS_MEASUREMENT@@URelocatableRegion@345@UPageTableRelocationRegion@345@UDeviceTreeParameter@345@URmeVpContext@345@@0@$$QEAV10@@Z; std::_Construct_in_place<std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>,std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>>(std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext> &,std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext> &&)
0x140099f15  mov     [rbx+1020h], r13b
0x140099f1c  lea     rcx, [rsp+10D0h+var_1058]
0x140099f21  call    ??1?$_Optional_destruct_base@V?$variant@U_IGVM_VHS_SUPPORTED_PLATFORM@@UPageData@FileFormat@IsolatedVm@HyperVGuestLoader@@UVbsVpContext@345@U_IGVM_VHS_CVM_POLICY@@USnpVpContext@345@U_IGVM_VHS_TD_INFO@@UParameterArea@345@UVpCountParameter@345@UMmioRangesParameter@345@USratParameter@345@UMadtParameter@345@USlitParameter@345@UPpttParameter@345@UMemoryMapParameter@345@UCommandLineParameter@345@U_IGVM_VHS_PARAMETER_INSERT@@U_IGVM_VHS_REQUIRED_MEMORY@@U_IGVM_VHS_ERROR_RANGE@@U_IGVM_VHS_SNP_ID_BLOCK@@U_IGVM_VHS_VBS_MEASUREMENT@@URelocatableRegion@345@UPageTableRelocationRegion@345@UDeviceTreeParameter@345@URmeVpContext@345@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>,0>::~_Optional_destruct_base<std::variant<_IGVM_VHS_SUPPORTED_PLATFORM,HyperVGuestLoader::IsolatedVm::FileFormat::PageData,HyperVGuestLoader::IsolatedVm::FileFormat::VbsVpContext,_IGVM_VHS_CVM_POLICY,HyperVGuestLoader::IsolatedVm::FileFormat::SnpVpContext,_IGVM_VHS_TD_INFO,HyperVGuestLoader::IsolatedVm::FileFormat::ParameterArea,HyperVGuestLoader::IsolatedVm::FileFormat::VpCountParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MmioRangesParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SratParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MadtParameter,HyperVGuestLoader::IsolatedVm::FileFormat::SlitParameter,HyperVGuestLoader::IsolatedVm::FileFormat::PpttParameter,HyperVGuestLoader::IsolatedVm::FileFormat::MemoryMapParameter,HyperVGuestLoader::IsolatedVm::FileFormat::CommandLineParameter,_IGVM_VHS_PARAMETER_INSERT,_IGVM_VHS_REQUIRED_MEMORY,_IGVM_VHS_ERROR_RANGE,_IGVM_VHS_SNP_ID_BLOCK,_IGVM_VHS_VBS_MEASUREMENT,HyperVGuestLoader::IsolatedVm::FileFormat::RelocatableRegion,HyperVGuestLoader::IsolatedVm::FileFormat::PageTableRelocationRegion,HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter,HyperVGuestLoader::IsolatedVm::FileFormat::RmeVpContext>,0>(void)
0x140099f26  mov     rax, rbx
  ... truncated ...
```
