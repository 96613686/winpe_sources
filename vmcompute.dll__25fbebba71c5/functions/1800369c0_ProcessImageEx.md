# ProcessImageEx

- ea: `0x1800369c0`
- end: `0x18003733a`
- name: `ProcessImageEx`
- size: `2426`
- prototype: ``
- caller_count: `5`
- callee_count: `32`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180036940`
- `0x180036970`
- `0x1800369a0`
- `0x180037340`
- `0x180037370`

## callees

- `0x180002f50`
- `0x180003c78`
- `0x180006158`
- `0x180006660`
- `0x18000d108`
- `0x180018bd4`
- `0x180022cd4`
- `0x180022d10`
- `0x18002cbb0`
- `0x18002dfb8`
- `0x18002e5c4`
- `0x18002ee18`
- `0x18002f94c`
- `0x18002fe2c`
- `0x18002ff50`
- `0x1800317ec`
- `0x18003195c`
- `0x180031acc`
- `0x180031c3c`
- `0x180031dac`
- `0x180031f1c`
- `0x18003208c`
- `0x1800321dc`
- `0x180034694`
- `0x1800369c0`
- `0x18004a688`
- `0x18005340c`
- `0x1800542e4`
- `0x18005cf28`
- `0x18005d664`
- `0x18005dab8`
- `0x18005fe7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036f01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036f01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036f20`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036f20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036f12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036ffe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003708a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036f12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036ffe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003708a`
- `VirtDisk!CreateVirtualDisk` at `0x180036d65`
- `VirtDisk!CreateVirtualDisk` at `0x180036d65`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x180036e60`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x180036e60`

## string_xrefs

- `0x180036cd9`: `GraphDriver_ProcessImage_CreateVhd`
- `0x180036da1`: `GraphDriver_ProcessImage_MountVhd`
- `0x1800370b3`: `GraphDriver_ProcessImage_CreateDiff`
- `0x18003714b`: `GraphDriver_ProcessImage_GrantAccess`
- `0x180036bcb`: `SystemTemplate.vhdx`
- `0x1800372d6`: `onecore\vm\compute\dll\legacy\src\graphdriver.cpp`
- `0x1800372eb`: `onecore\vm\compute\dll\legacy\src\graphdriver.cpp`
- `0x180037300`: `onecore\vm\compute\dll\legacy\src\graphdriver.cpp`
- `0x180037327`: `onecore\vm\compute\dll\legacy\src\graphdriver.cpp`
- `0x180036b9d`: `SystemTemplateBase.vhdx`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall ProcessImageEx(PCWSTR pszPathIn, char *a2, int a3, char a4, PCWSTR pszPathIna)
{
  ULONG v7; // edi
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  void **Handle; // rax
  const WCHAR *v13; // rdx
  DWORD v14; // eax
  DWORD VirtualDiskPhysicalPath; // eax
  const unsigned __int16 *v16; // rdx
  const WCHAR *v17; // rcx
  HANDLE v18; // rdi
  DWORD LastError; // ebx
  const struct Schema::Options::OsLayerOptions *v20; // r9
  const WCHAR *v21; // rdx
  const WCHAR *v22; // rcx
  unsigned int v23; // r9d
  PCWSTR *v24; // rcx
  unsigned int v25; // r9d
  PCWSTR *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // r8
  const char *v29; // r9
  __int64 result; // rax
  const char *v31; // r9
  const char *v32; // r9
  unsigned int v33; // eax
  int v34; // edx
  int Flags; // [rsp+20h] [rbp-AD8h]
  unsigned int Flagsa; // [rsp+20h] [rbp-AD8h]
  const char *ProviderSpecificFlags; // [rsp+28h] [rbp-AD0h]
  _OWORD Src[2]; // [rsp+50h] [rbp-AA8h] BYREF
  ULONG DiskPathSizeInBytes; // [rsp+70h] [rbp-A88h] BYREF
  HANDLE VirtualDiskHandle; // [rsp+78h] [rbp-A80h] BYREF
  HANDLE hObject; // [rsp+80h] [rbp-A78h] BYREF
  PCWSTR Path[2]; // [rsp+88h] [rbp-A70h] BYREF
  __m128i si128; // [rsp+98h] [rbp-A60h]
  PCWSTR v44[2]; // [rsp+A8h] [rbp-A50h] BYREF
  __m128i v45; // [rsp+B8h] [rbp-A40h]
  __int64 v46; // [rsp+C8h] [rbp-A30h] BYREF
  __int128 v47; // [rsp+D0h] [rbp-A28h] BYREF
  __int64 v48; // [rsp+E0h] [rbp-A18h]
  __int128 v49; // [rsp+E8h] [rbp-A10h]
  struct _VIRTUAL_STORAGE_TYPE VirtualStorageType; // [rsp+F8h] [rbp-A00h] BYREF
  void **v51; // [rsp+110h] [rbp-9E8h] BYREF
  int v52; // [rsp+118h] [rbp-9E0h] BYREF
  char v53; // [rsp+11Ch] [rbp-9DCh]
  int v54; // [rsp+140h] [rbp-9B8h] BYREF
  const char *v55; // [rsp+148h] [rbp-9B0h]
  __int64 v56; // [rsp+150h] [rbp-9A8h]
  char v57; // [rsp+158h] [rbp-9A0h]
  int v58; // [rsp+160h] [rbp-998h]
  _BYTE v59[152]; // [rsp+168h] [rbp-990h] BYREF
  __int128 v60; // [rsp+200h] [rbp-8F8h]
  int v61; // [rsp+210h] [rbp-8E8h]
  __int64 v62; // [rsp+218h] [rbp-8E0h]
  int *v63; // [rsp+220h] [rbp-8D8h]
  __int64 v64; // [rsp+228h] [rbp-8D0h]
  __int64 v65; // [rsp+230h] [rbp-8C8h]
  void ***v66; // [rsp+238h] [rbp-8C0h]
  __int64 v67; // [rsp+240h] [rbp-8B8h]
  int v68; // [rsp+248h] [rbp-8B0h]
  int *v69; // [rsp+250h] [rbp-8A8h]
  char v70; // [rsp+258h] [rbp-8A0h]
  PCWSTR v71[8]; // [rsp+260h] [rbp-898h] BYREF
  _QWORD v72[42]; // [rsp+2A0h] [rbp-858h] BYREF
  _QWORD v73[42]; // [rsp+3F0h] [rbp-708h] BYREF
  struct _CREATE_VIRTUAL_DISK_PARAMETERS Parameters; // [rsp+540h] [rbp-5B8h] BYREF
  _QWORD v75[42]; // [rsp+600h] [rbp-4F8h] BYREF
  _QWORD v76[42]; // [rsp+750h] [rbp-3A8h] BYREF
  WCHAR DiskPath[264]; // [rsp+8A0h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+AF8h] [rbp+0h]

  v7 = (unsigned int)a2;
  memset_0(&v51, 0, 0x150u);
  DiskPathSizeInBytes = v7;
  v52 = 0;
  v53 = 0;
  v57 = 0;
  v54 = 0;
  v55 = "GraphDriver_ProcessImage";
  v56 = 0;
  v58 = 0;
  v60 = 0;
  memset_0(v59, 0, sizeof(v59));
  v61 = 1;
  v62 = 0;
  v63 = &v52;
  v64 = 0;
  v65 = 0;
  v66 = &v51;
  v67 = 0;
  v68 = 0;
  v69 = &v54;
  v70 = 0;
  v51 = &ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage::`vftable';
  try
  {
    ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage::StartActivity<unsigned int>(
      (__int64)&v51,
      (int *)&DiskPathSizeInBytes);
    v46 = 0;
    v47 = 0;
    v48 = 0;
    v49 = 0;
    *(_OWORD *)Path = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(Path[0]) = 0;
    *(_OWORD *)v44 = 0;
    v45 = si128;
    LOWORD(v44[0]) = 0;
    if ( !pszPathIna || !*pszPathIna )
    {
      v32 = (const char *)(unsigned int)wil::verify_hresult<long>(2147942487LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5CF,
        (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\graphdriver.cpp",
        v32,
        Flags);
    }
    if ( v7 )
    {
      if ( v7 != 1 && v7 - 2 > 1 )
      {
        v31 = (const char *)(unsigned int)wil::verify_hresult<long>(2147942487LL);
        LODWORD(ProviderSpecificFlags) = v7;
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x5E3,
          (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\graphdriver.cpp",
          v31,
          (int)"Unrecognized ImageType: %x",
          ProviderSpecificFlags);
      }
      LODWORD(v46) = 1;
      v9 = Vml::CombineFilePath(Src, pszPathIna, L"SystemTemplateBase.vhdx");
      std::wstring::operator=(Path, v9);
      std::wstring::~wstring(Src);
      v10 = Vml::CombineFilePath(Src, pszPathIna, L"SystemTemplate.vhdx");
    }
    else
    {
      LODWORD(v46) = 0;
      v11 = Vml::CombineFilePath(Src, pszPathIna, L"blank-base.vhdx");
      std::wstring::operator=(Path, v11);
      std::wstring::~wstring(Src);
      v10 = Vml::CombineFilePath(Src, pszPathIna, L"blank.vhdx");
    }
    std::wstring::operator=(v44, v10);
    std::wstring::~wstring(Src);
    BYTE4(v46) = a4 & 1;
    HIBYTE(v46) = (a4 & 2) != 0;
    BYTE6(v46) = v7 == 2;
    *(_QWORD *)&Parameters.Version = 2;
    memset_0(&Parameters.Version1, 0, 0xB0u);
    Parameters.Version1.MaximumSize = (unsigned __int64)(unsigned int)(a3 << 20) << 10;
    Parameters.Version1.BlockSizeInBytes = 0x100000;
    memset(&VirtualStorageType, 0, sizeof(VirtualStorageType));
    VirtualDiskHandle = (HANDLE)-1LL;
    memset_0(v73, 0, sizeof(v73));
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(
      v73,
      "GraphDriver_ProcessImage_CreateVhd");
    v73[0] = &ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_CreateVhd::`vftable';
    ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_CreateVhd::StartActivity(
      (ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_CreateVhd *)v73,
      (const struct ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage *)&v51);
    Handle = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&VirtualDiskHandle);
    v13 = (const WCHAR *)Path;
    if ( si128.m128i_i64[1] > 7uLL )
      v13 = Path[0];
    v14 = CreateVirtualDisk(
            &VirtualStorageType,
            v13,
            VIRTUAL_DISK_ACCESS_NONE,
            0,
            CREATE_VIRTUAL_DISK_FLAG_NONE,
            0,
            &Parameters,
            0,
            Handle);
    if ( v14 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x5FE,
        (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\graphdriver.cpp",
        (const char *)v14,
        Flagsa);
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v73);
    memset_0(v72, 0, sizeof(v72));
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(
      v72,
      "GraphDriver_ProcessImage_MountVhd");
    v72[0] = &ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_MountVhd::`vftable';
    ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_MountVhd::StartActivity(
      (ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_MountVhd *)v72,
      (const struct ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage *)&v51);
    MountVhd(
      VirtualDiskHandle,
      ATTACH_VIRTUAL_DISK_FLAG_BYPASS_DEFAULT_ENCRYPTION_POLICY|ATTACH_VIRTUAL_DISK_FLAG_NO_DRIVE_LETTER,
      4u);
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v72);
    memset_0(v76, 0, sizeof(v76));
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(
      v76,
      "GraphDriver_ProcessImage_SetupSandbox");
    v76[0] = &ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_SetupSandbox::`vftable';
    ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_SetupSandbox::StartActivity(
      (ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_SetupSandbox *)v76,
      (const struct ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage *)&v51);
    DiskPathSizeInBytes = 520;
    VirtualDiskPhysicalPath = GetVirtualDiskPhysicalPath(VirtualDiskHandle, &DiskPathSizeInBytes, DiskPath);
    if ( VirtualDiskPhysicalPath )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x609,
        (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\graphdriver.cpp",
        (const char *)VirtualDiskPhysicalPath,
        Flagsa);
    hObject = 0;
    OpenDisk(&hObject, DiskPath);
    Src[0] = GUID_00000000_0000_0000_0000_000000000000;
    FormatDisk(v71, hObject, L"NTFS", Src);
    if ( !(_DWORD)v46 )
    {
      v17 = (const WCHAR *)v71;
      if ( v71[3] > (PCWSTR)7 )
        v17 = v71[0];
      OsImageUtilities::Helpers::CreateSandboxStateDirectory(v17, v16);
      v18 = VirtualDiskHandle;
      if ( (char *)VirtualDiskHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        LastError = GetLastError();
        CloseHandle(v18);
        SetLastError(LastError);
      }
      VirtualDiskHandle = (HANDLE)-1LL;
    }
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v76);
    memset_0(v75, 0, sizeof(v75));
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(
      v75,
      "GraphDriver_ProcessImage_ProcessOsLayer");
    v75[0] = &ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_ProcessOsLayer::`vftable';
    ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_ProcessOsLayer::StartActivity(
      (ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_ProcessOsLayer *)v75,
      (const struct ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage *)&v51);
    OsImageUtilities::ProcessOsLayer(pszPathIn, (PCWSTR)v71, (const struct PartitionInfo *)&v46, v20);
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v75);
    v75[0] = &ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_ProcessOsLayer::`vftable';
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v75);
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(v75);
    std::wstring::~wstring(v71);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    v76[0] = &ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_SetupSandbox::`vftable';
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v76);
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(v76);
    v72[0] = &ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_MountVhd::`vftable';
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v72);
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(v72);
    v73[0] = &ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_CreateVhd::`vftable';
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v73);
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(v73);
    if ( (char *)VirtualDiskHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(VirtualDiskHandle);
    if ( (a4 & 4) == 0 )
    {
      memset_0(v72, 0, sizeof(v72));
      wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(
        v72,
        "GraphDriver_ProcessImage_CreateDiff");
      v72[0] = &ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_CreateDiff::`vftable';
      ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_CreateDiff::StartActivity(
        (ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_CreateDiff *)v72,
        (const struct ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage *)&v51);
      v21 = (const WCHAR *)Path;
      if ( si128.m128i_i64[1] > 7uLL )
        v21 = Path[0];
      v22 = (const WCHAR *)v44;
      if ( v45.m128i_i64[1] > 7uLL )
        v22 = v44[0];
      CreateDiffVhd(v22, v21, 1u);
      wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v72);
      memset_0(v73, 0, sizeof(v73));
      wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(
        v73,
        "GraphDriver_ProcessImage_GrantAccess");
      v73[0] = &ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_GrantAccess::`vftable';
      ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_GrantAccess::StartActivity(
        (ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_GrantAccess *)v73,
        (const struct ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage *)&v51);
      v24 = Path;
      if ( si128.m128i_i64[1] > 7uLL )
        v24 = (PCWSTR *)Path[0];
      VmFileUtilities::GrantVmGroupAccess((VmFileUtilities *)v24, 0, 169, v23);
      v26 = v44;
      if ( v45.m128i_i64[1] > 7uLL )
        v26 = (PCWSTR *)v44[0];
      VmFileUtilities::GrantVmGroupAccess((VmFileUtilities *)v26, 0, 169, v25);
      wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v73);
      v73[0] = &ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_GrantAccess::`vftable';
      wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v73);
      wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(v73);
      v72[0] = &ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_CreateDiff::`vftable';
      wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v72);
      wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(v72);
    }
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,1,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v51);
    std::wstring::~wstring(v44);
    std::wstring::~wstring(Path);
    std::vector<Schema::Common::Resources::Layer>::_Tidy(&v47, v27, v28);
    v51 = &ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage::`vftable';
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,1,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v51);
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(&v51);
    result = 0;
  }
  catch ( ... )
  {
    v33 = wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0x62A,
            (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\graphdriver.cpp",
            v29);
    return (unsigned int)ClientError::ToV1Result((ClientError *)v33, v34);
  }
  return result;
}

```

## disassembly

```asm
0x1800369c0  push    rbx
0x1800369c2  push    rsi
0x1800369c3  push    rdi
0x1800369c4  push    r12
0x1800369c6  push    r13
0x1800369c8  push    r14
0x1800369ca  push    r15
0x1800369cc  sub     rsp, 0AC0h
0x1800369d3  mov     rax, cs:__security_cookie
0x1800369da  xor     rax, rsp
0x1800369dd  mov     [rsp+0AF8h+var_48], rax
0x1800369e5  mov     esi, r9d
0x1800369e8  mov     r14d, r8d
0x1800369eb  mov     edi, edx
0x1800369ed  mov     r15, rcx
0x1800369f0  mov     rbx, [rsp+0AF8h+pszPathIn]
0x1800369f8  mov     r13d, 150h
0x1800369fe  mov     r8d, r13d; Size
0x180036a01  xor     edx, edx; Val
0x180036a03  lea     rcx, [rsp+0AF8h+var_9E8]; void *
0x180036a0b  call    memset_0
0x180036a10  mov     [rsp+0AF8h+DiskPathSizeInBytes], edi
0x180036a14  xor     r12d, r12d
0x180036a17  mov     [rsp+0AF8h+var_9E0], r12d
0x180036a1f  mov     [rsp+0AF8h+var_9DC], r12b
0x180036a27  mov     [rsp+0AF8h+var_9A0], r12b
0x180036a2f  mov     [rsp+0AF8h+var_9B8], r12d
0x180036a37  lea     rax, aGraphdriverPro_1; "GraphDriver_ProcessImage"
0x180036a3e  mov     [rsp+0AF8h+var_9B0], rax
0x180036a46  mov     [rsp+0AF8h+var_9A8], r12
0x180036a4e  mov     [rsp+0AF8h+var_998], r12d
0x180036a56  xorps   xmm0, xmm0
0x180036a59  movdqa  [rsp+0AF8h+var_8F8], xmm0
0x180036a62  xor     edx, edx; Val
0x180036a64  mov     r8d, 98h; Size
0x180036a6a  lea     rcx, [rsp+0AF8h+var_990]; void *
0x180036a72  call    memset_0
0x180036a77  mov     [rsp+0AF8h+var_8E8], 1
0x180036a82  xor     eax, eax
0x180036a84  mov     [rsp+0AF8h+var_8E0], rax
0x180036a8c  lea     rax, [rsp+0AF8h+var_9E0]
0x180036a94  mov     [rsp+0AF8h+var_8D8], rax
0x180036a9c  mov     [rsp+0AF8h+var_8D0], r12
0x180036aa4  mov     [rsp+0AF8h+var_8C8], r12
0x180036aac  lea     rax, [rsp+0AF8h+var_9E8]
0x180036ab4  mov     [rsp+0AF8h+var_8C0], rax
0x180036abc  mov     [rsp+0AF8h+var_8B8], r12
0x180036ac4  mov     [rsp+0AF8h+var_8B0], r12d
0x180036acc  lea     rax, [rsp+0AF8h+var_9B8]
0x180036ad4  mov     [rsp+0AF8h+var_8A8], rax
0x180036adc  mov     [rsp+0AF8h+var_8A0], r12b
0x180036ae4  lea     rax, ??_7GraphDriver_ProcessImage@TraceProvider@Diagnostics@ComputeLegacy@@6B@; const ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage::`vftable'
0x180036aeb  mov     [rsp+0AF8h+var_9E8], rax
0x180036af3  lea     rdx, [rsp+0AF8h+DiskPathSizeInBytes]
0x180036af8  lea     rcx, [rsp+0AF8h+var_9E8]
0x180036b00  call    ??$StartActivity@I@GraphDriver_ProcessImage@TraceProvider@Diagnostics@ComputeLegacy@@QEAAX$$QEAI@Z; ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage::StartActivity<uint>(uint &&)
0x180036b05  nop
0x180036b06  mov     [rsp+0AF8h+var_A30], r12
0x180036b0e  xorps   xmm0, xmm0
0x180036b11  movdqu  [rsp+0AF8h+var_A28], xmm0
0x180036b1a  mov     [rsp+0AF8h+var_A18], r12
0x180036b22  movups  [rsp+0AF8h+var_A10], xmm0
0x180036b2a  movups  xmmword ptr [rsp+0AF8h+Path], xmm0
0x180036b32  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180036b3a  movdqu  [rsp+0AF8h+var_A60], xmm1
0x180036b43  mov     word ptr [rsp+0AF8h+Path], r12w
0x180036b4c  movups  xmmword ptr [rsp+0AF8h+var_A50], xmm0
0x180036b54  movdqu  [rsp+0AF8h+var_A40], xmm1
0x180036b5d  mov     word ptr [rsp+0AF8h+var_A50], r12w
0x180036b66  test    rbx, rbx
0x180036b69  jz      loc_180037312
0x180036b6f  cmp     [rbx], r12w
0x180036b73  jz      loc_180037312
0x180036b79  mov     ecx, edi
0x180036b7b  test    edi, edi
0x180036b7d  jz      short loc_180036BE1
0x180036b7f  sub     ecx, 1
0x180036b82  jz      short loc_180036B92
0x180036b84  sub     ecx, 1
0x180036b87  jz      short loc_180036B92
0x180036b89  cmp     ecx, 1
0x180036b8c  jnz     loc_1800372B1
0x180036b92  mov     dword ptr [rsp+0AF8h+var_A30], 1
0x180036b9d  lea     r8, aSystemtemplate_0; "SystemTemplateBase.vhdx"
0x180036ba4  mov     rdx, rbx; pszPathIn
0x180036ba7  lea     rcx, [rsp+0AF8h+Src]; Src
0x180036bac  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x180036bb1  mov     rdx, rax
0x180036bb4  lea     rcx, [rsp+0AF8h+Path]
0x180036bbc  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180036bc1  lea     rcx, [rsp+0AF8h+Src]
0x180036bc6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180036bcb  lea     r8, aSystemtemplate; "SystemTemplate.vhdx"
0x180036bd2  mov     rdx, rbx; pszPathIn
0x180036bd5  lea     rcx, [rsp+0AF8h+Src]; Src
0x180036bda  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x180036bdf  jmp     short loc_180036C2B
0x180036be1  mov     dword ptr [rsp+0AF8h+var_A30], r12d
0x180036be9  lea     r8, aBlankBaseVhdx; "blank-base.vhdx"
0x180036bf0  mov     rdx, rbx; pszPathIn
0x180036bf3  lea     rcx, [rsp+0AF8h+Src]; Src
0x180036bf8  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x180036bfd  mov     rdx, rax
0x180036c00  lea     rcx, [rsp+0AF8h+Path]
0x180036c08  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180036c0d  lea     rcx, [rsp+0AF8h+Src]
0x180036c12  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180036c17  lea     r8, aBlankVhdx; "blank.vhdx"
0x180036c1e  mov     rdx, rbx; pszPathIn
0x180036c21  lea     rcx, [rsp+0AF8h+Src]; Src
0x180036c26  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x180036c2b  mov     rdx, rax
0x180036c2e  lea     rcx, [rsp+0AF8h+var_A50]
0x180036c36  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180036c3b  lea     rcx, [rsp+0AF8h+Src]
0x180036c40  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180036c45  mov     al, sil
0x180036c48  and     al, 1
0x180036c4a  mov     byte ptr [rsp+0AF8h+var_A30+4], al
0x180036c51  mov     al, sil
0x180036c54  shr     al, 1
0x180036c56  and     al, 1
0x180036c58  mov     byte ptr [rsp+0AF8h+var_A30+7], al
0x180036c5f  cmp     edi, 2
0x180036c62  setz    byte ptr [rsp+0AF8h+var_A30+6]
0x180036c6a  mov     qword ptr [rsp+0AF8h+var_5B8.Version], 2
0x180036c76  xor     edx, edx; Val
0x180036c78  mov     r8d, 0B0h; Size
0x180036c7e  lea     rcx, [rsp+0AF8h+var_5B8.8]; void *
0x180036c86  call    memset_0
0x180036c8b  shl     r14d, 14h
0x180036c8f  mov     eax, r14d
0x180036c92  shl     rax, 0Ah
0x180036c96  mov     qword ptr [rsp+0AF8h+var_5B8.8+10h], rax
0x180036c9e  mov     dword ptr [rsp+0AF8h+var_5B8.8+18h], 100000h
0x180036ca9  xorps   xmm0, xmm0
0x180036cac  xor     eax, eax
0x180036cae  movups  xmmword ptr [rsp+0AF8h+VirtualStorageType.DeviceId], xmm0
0x180036cb6  mov     dword ptr [rsp+0AF8h+VirtualStorageType.VendorId.Data4+4], eax
0x180036cbd  mov     [rsp+0AF8h+VirtualDiskHandle], 0FFFFFFFFFFFFFFFFh
0x180036cc6  mov     r8, r13; Size
0x180036cc9  xor     edx, edx; Val
0x180036ccb  lea     rcx, [rsp+0AF8h+var_708]; void *
0x180036cd3  call    memset_0
0x180036cd8  nop
0x180036cd9  lea     rdx, aGraphdriverPro_4; "GraphDriver_ProcessImage_CreateVhd"
0x180036ce0  lea     rcx, [rsp+0AF8h+var_708]
0x180036ce8  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180036ced  lea     rax, ??_7GraphDriver_ProcessImage_CreateVhd@TraceProvider@Diagnostics@ComputeLegacy@@6B@; const ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_CreateVhd::`vftable'
0x180036cf4  mov     [rsp+0AF8h+var_708], rax
0x180036cfc  lea     rdx, [rsp+0AF8h+var_9E8]; struct ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage *
0x180036d04  lea     rcx, [rsp+0AF8h+var_708]; this
0x180036d0c  call    ?StartActivity@GraphDriver_ProcessImage_CreateVhd@TraceProvider@Diagnostics@ComputeLegacy@@QEAAXAEBVGraphDriver_ProcessImage@234@@Z; ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_CreateVhd::StartActivity(ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage const &)
0x180036d11  nop
0x180036d12  lea     rcx, [rsp+0AF8h+VirtualDiskHandle]
0x180036d17  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x180036d1c  lea     rdx, [rsp+0AF8h+Path]
0x180036d24  cmp     qword ptr [rsp+0AF8h+var_A60+8], 7
0x180036d2d  cmova   rdx, [rsp+0AF8h+Path]; Path
0x180036d36  mov     [rsp+0AF8h+Handle], rax; Handle
0x180036d3b  mov     [rsp+0AF8h+Overlapped], r12; Overlapped
0x180036d40  lea     rax, [rsp+0AF8h+var_5B8]
0x180036d48  mov     [rsp+0AF8h+Parameters], rax; Parameters
0x180036d4d  mov     dword ptr [rsp+0AF8h+ProviderSpecificFlags], r12d; ProviderSpecificFlags
0x180036d52  mov     [rsp+0AF8h+Flags], r12d; unsigned int
0x180036d57  xor     r9d, r9d; SecurityDescriptor
0x180036d5a  xor     r8d, r8d; VirtualDiskAccessMask
0x180036d5d  lea     rcx, [rsp+0AF8h+VirtualStorageType]; VirtualStorageType
0x180036d65  call    cs:__imp_CreateVirtualDisk
0x180036d6c  nop     dword ptr [rax+rax+00h]
0x180036d71  mov     rcx, [rsp+0AF8h]; this
0x180036d79  test    eax, eax
0x180036d7b  jnz     loc_1800372E8
0x180036d81  lea     rcx, [rsp+0AF8h+var_708]
0x180036d89  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180036d8e  mov     r8, r13; Size
0x180036d91  xor     edx, edx; Val
0x180036d93  lea     rcx, [rsp+0AF8h+var_858]; void *
0x180036d9b  call    memset_0
0x180036da0  nop
0x180036da1  lea     rdx, aGraphdriverPro_2; "GraphDriver_ProcessImage_MountVhd"
0x180036da8  lea     rcx, [rsp+0AF8h+var_858]
0x180036db0  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180036db5  lea     r14, ??_7GraphDriver_ProcessImage_MountVhd@TraceProvider@Diagnostics@ComputeLegacy@@6B@; const ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_MountVhd::`vftable'
0x180036dbc  mov     [rsp+0AF8h+var_858], r14
0x180036dc4  lea     rdx, [rsp+0AF8h+var_9E8]; struct ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage *
0x180036dcc  lea     rcx, [rsp+0AF8h+var_858]; this
0x180036dd4  call    ?StartActivity@GraphDriver_ProcessImage_MountVhd@TraceProvider@Diagnostics@ComputeLegacy@@QEAAXAEBVGraphDriver_ProcessImage@234@@Z; ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_MountVhd::StartActivity(ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage const &)
0x180036dd9  nop
0x180036dda  mov     edx, 22h ; '"'; enum _ATTACH_VIRTUAL_DISK_FLAG
0x180036ddf  lea     r8d, [rdx-1Eh]; unsigned __int16
0x180036de3  mov     rcx, [rsp+0AF8h+VirtualDiskHandle]; void *
0x180036de8  call    ?MountVhd@@YAXPEAXW4_ATTACH_VIRTUAL_DISK_FLAG@@G@Z; MountVhd(void *,_ATTACH_VIRTUAL_DISK_FLAG,ushort)
0x180036ded  lea     rcx, [rsp+0AF8h+var_858]
0x180036df5  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180036dfa  mov     r8, r13; Size
0x180036dfd  xor     edx, edx; Val
0x180036dff  lea     rcx, [rsp+0AF8h+var_3A8]; void *
0x180036e07  call    memset_0
0x180036e0c  nop
0x180036e0d  lea     rdx, aGraphdriverPro_0; "GraphDriver_ProcessImage_SetupSandbox"
0x180036e14  lea     rcx, [rsp+0AF8h+var_3A8]
0x180036e1c  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180036e21  lea     rdi, ??_7GraphDriver_ProcessImage_SetupSandbox@TraceProvider@Diagnostics@ComputeLegacy@@6B@; const ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_SetupSandbox::`vftable'
0x180036e28  mov     [rsp+0AF8h+var_3A8], rdi
0x180036e30  lea     rdx, [rsp+0AF8h+var_9E8]; struct ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage *
0x180036e38  lea     rcx, [rsp+0AF8h+var_3A8]; this
0x180036e40  call    ?StartActivity@GraphDriver_ProcessImage_SetupSandbox@TraceProvider@Diagnostics@ComputeLegacy@@QEAAXAEBVGraphDriver_ProcessImage@234@@Z; ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_SetupSandbox::StartActivity(ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage const &)
0x180036e45  nop
0x180036e46  mov     [rsp+0AF8h+DiskPathSizeInBytes], 208h
0x180036e4e  lea     r8, [rsp+0AF8h+DiskPath]; DiskPath
0x180036e56  lea     rdx, [rsp+0AF8h+DiskPathSizeInBytes]; DiskPathSizeInBytes
0x180036e5b  mov     rcx, [rsp+0AF8h+VirtualDiskHandle]; VirtualDiskHandle
0x180036e60  call    cs:__imp_GetVirtualDiskPhysicalPath
0x180036e67  nop     dword ptr [rax+rax+00h]
0x180036e6c  mov     rcx, [rsp+0AF8h]; this
0x180036e74  test    eax, eax
0x180036e76  jnz     loc_1800372FD
0x180036e7c  mov     [rsp+0AF8h+hObject], r12
0x180036e84  lea     rdx, [rsp+0AF8h+DiskPath]
0x180036e8c  lea     rcx, [rsp+0AF8h+hObject]
0x180036e94  call    ?OpenDisk@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBGK@Z; OpenDisk(ushort const *,ulong)
0x180036e99  nop
0x180036e9a  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180036ea1  movdqu  [rsp+0AF8h+Src], xmm0
0x180036ea7  lea     r9, [rsp+0AF8h+Src]
0x180036eac  lea     r8, aNtfs; "NTFS"
0x180036eb3  mov     rdx, [rsp+0AF8h+hObject]
0x180036ebb  lea     rcx, [rsp+0AF8h+var_898]
0x180036ec3  call    ?FormatDisk@@YA?AUPartitionInfo@@PEAXPEBGU_GUID@@@Z; FormatDisk(void *,ushort const *,_GUID)
0x180036ec8  nop
0x180036ec9  cmp     dword ptr [rsp+0AF8h+var_A30], r12d
0x180036ed1  jnz     short loc_180036F3C
0x180036ed3  lea     rcx, [rsp+0AF8h+var_898]
0x180036edb  cmp     [rsp+0AF8h+var_880], 7
0x180036ee4  cmova   rcx, [rsp+0AF8h+var_898]; pszPathIn
0x180036eed  call    ?CreateSandboxStateDirectory@Helpers@OsImageUtilities@@YAXPEBG@Z; OsImageUtilities::Helpers::CreateSandboxStateDirectory(ushort const *)
0x180036ef2  mov     rdi, [rsp+0AF8h+VirtualDiskHandle]
0x180036ef7  lea     rax, [rdi-1]
0x180036efb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180036eff  ja      short loc_180036F2C
0x180036f01  call    cs:__imp_GetLastError
0x180036f08  nop     dword ptr [rax+rax+00h]
0x180036f0d  mov     ebx, eax
0x180036f0f  mov     rcx, rdi; hObject
0x180036f12  call    cs:__imp_CloseHandle
0x180036f19  nop     dword ptr [rax+rax+00h]
0x180036f1e  mov     ecx, ebx; dwErrCode
0x180036f20  call    cs:__imp_SetLastError
0x180036f27  nop     dword ptr [rax+rax+00h]
0x180036f2c  mov     [rsp+0AF8h+VirtualDiskHandle], 0FFFFFFFFFFFFFFFFh
0x180036f35  lea     rdi, ??_7GraphDriver_ProcessImage_SetupSandbox@TraceProvider@Diagnostics@ComputeLegacy@@6B@; const ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_SetupSandbox::`vftable'
0x180036f3c  lea     rcx, [rsp+0AF8h+var_3A8]
0x180036f44  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180036f49  mov     r8, r13; Size
0x180036f4c  xor     edx, edx; Val
0x180036f4e  lea     rcx, [rsp+0AF8h+var_4F8]; void *
0x180036f56  call    memset_0
0x180036f5b  nop
0x180036f5c  lea     rdx, aGraphdriverPro_5; "GraphDriver_ProcessImage_ProcessOsLayer"
0x180036f63  lea     rcx, [rsp+0AF8h+var_4F8]
0x180036f6b  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180036f70  lea     rbx, ??_7GraphDriver_ProcessImage_ProcessOsLayer@TraceProvider@Diagnostics@ComputeLegacy@@6B@; const ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_ProcessOsLayer::`vftable'
0x180036f77  mov     [rsp+0AF8h+var_4F8], rbx
0x180036f7f  lea     rdx, [rsp+0AF8h+var_9E8]; struct ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage *
0x180036f87  lea     rcx, [rsp+0AF8h+var_4F8]; this
0x180036f8f  call    ?StartActivity@GraphDriver_ProcessImage_ProcessOsLayer@TraceProvider@Diagnostics@ComputeLegacy@@QEAAXAEBVGraphDriver_ProcessImage@234@@Z; ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_ProcessOsLayer::StartActivity(ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage const &)
0x180036f94  nop
0x180036f95  lea     r8, [rsp+0AF8h+var_A30]; struct PartitionInfo *
0x180036f9d  lea     rdx, [rsp+0AF8h+var_898]; PCWSTR
0x180036fa5  mov     rcx, r15; pszPathIn
0x180036fa8  call    ?ProcessOsLayer@OsImageUtilities@@YAXPEBGAEBUPartitionInfo@@AEBUOsLayerOptions@Options@Schema@@@Z; OsImageUtilities::ProcessOsLayer(ushort const *,PartitionInfo const &,Schema::Options::OsLayerOptions const &)
0x180036fad  lea     rcx, [rsp+0AF8h+var_4F8]
0x180036fb5  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180036fba  nop
0x180036fbb  mov     [rsp+0AF8h+var_4F8], rbx
0x180036fc3  lea     rcx, [rsp+0AF8h+var_4F8]
0x180036fcb  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180036fd0  lea     rcx, [rsp+0AF8h+var_4F8]
0x180036fd8  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180036fdd  nop
0x180036fde  lea     rcx, [rsp+0AF8h+var_898]
0x180036fe6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180036feb  nop
0x180036fec  mov     rcx, [rsp+0AF8h+hObject]; hObject
0x180036ff4  lea     rax, [rcx-1]
0x180036ff8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180036ffc  ja      short loc_18003700B
0x180036ffe  call    cs:__imp_CloseHandle
0x180037005  nop     dword ptr [rax+rax+00h]
0x18003700a  nop
0x18003700b  mov     [rsp+0AF8h+var_3A8], rdi
0x180037013  lea     rcx, [rsp+0AF8h+var_3A8]
0x18003701b  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180037020  lea     rcx, [rsp+0AF8h+var_3A8]
0x180037028  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18003702d  nop
0x18003702e  mov     [rsp+0AF8h+var_858], r14
0x180037036  lea     rcx, [rsp+0AF8h+var_858]
0x18003703e  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
  ... truncated ...
```
