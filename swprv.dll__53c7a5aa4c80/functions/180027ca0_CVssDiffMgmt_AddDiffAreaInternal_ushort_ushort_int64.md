# CVssDiffMgmt::AddDiffAreaInternal(ushort *,ushort *,__int64)

- ea: `0x180027ca0`
- end: `0x1800287c8`
- name: `?AddDiffAreaInternal@CVssDiffMgmt@@EEAAJPEAG0_J@Z`
- size: `2856`
- prototype: `__int64 __fastcall(CVssDiffMgmt *__hidden this, unsigned __int16 *, unsigned __int16 *, __int64)`
- caller_count: `0`
- callee_count: `30`
- tags: `reparse_path, installer_update, broker_com_uri`

## callees

- `0x180001580`
- `0x18000212c`
- `0x1800034cc`
- `0x180003888`
- `0x18001d7f0`
- `0x18001d8dc`
- `0x18001d988`
- `0x18001dc3c`
- `0x18001dd84`
- `0x18001e6f8`
- `0x18001ea00`
- `0x180027ca0`
- `0x18002a280`
- `0x18002a4f8`
- `0x18002a774`
- `0x18002e79c`
- `0x180033a8c`
- `0x180033c78`
- `0x180034278`
- `0x180034a4c`
- `0x180035f44`
- `0x18003609c`
- `0x18003649c`
- `0x1800367b8`
- `0x180039394`
- `0x18003df28`
- `0x18003e054`
- `0x18003f1f4`
- `0x18003ff6c`
- `0x180040cb0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800282b3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800283ac`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800282b3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800283ac`

## string_xrefs

- `0x180028129`: `Association already exists`
- `0x1800286dc`: `cluster.RemoveDependency(%s, %s)`

## pseudocode

```c
__int64 __fastcall CVssDiffMgmt::AddDiffAreaInternal(
        CVssDiffMgmt *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        __int64 a4)
{
  __int64 MinDiffAreaOnVolume; // rax
  CVssDiffMgmt *v5; // rcx
  CVssDiffMgmt *v6; // rcx
  unsigned int SectorSizeForVolume; // eax
  unsigned __int16 *v8; // r8
  int v9; // r9d
  unsigned __int16 *v10; // r8
  int v11; // r9d
  bool v12; // dl
  const unsigned __int16 *v13; // rdx
  unsigned int v14; // ebx
  __int64 v16; // [rsp+28h] [rbp-400h]
  bool v17[16]; // [rsp+40h] [rbp-3E8h] BYREF
  const unsigned __int16 *v18; // [rsp+50h] [rbp-3D8h] BYREF
  const unsigned __int16 *v19; // [rsp+58h] [rbp-3D0h]
  const unsigned __int16 *v20; // [rsp+60h] [rbp-3C8h]
  int v21; // [rsp+68h] [rbp-3C0h]
  int v22; // [rsp+6Ch] [rbp-3BCh]
  int v23; // [rsp+70h] [rbp-3B8h]
  _BYTE v24[120]; // [rsp+78h] [rbp-3B0h] BYREF
  int v25; // [rsp+F0h] [rbp-338h]
  unsigned __int16 *v26; // [rsp+F8h] [rbp-330h]
  unsigned __int16 *v27; // [rsp+100h] [rbp-328h]
  unsigned int AssociationFlags; // [rsp+108h] [rbp-320h]
  unsigned __int16 *v29; // [rsp+110h] [rbp-318h]
  __int64 v30; // [rsp+118h] [rbp-310h]
  unsigned __int16 *v31; // [rsp+120h] [rbp-308h]
  LPVOID v32; // [rsp+130h] [rbp-2F8h] BYREF
  int v33; // [rsp+138h] [rbp-2F0h]
  unsigned int v34; // [rsp+154h] [rbp-2D4h]
  unsigned int v35; // [rsp+1A0h] [rbp-288h] BYREF
  unsigned int v36; // [rsp+1A4h] [rbp-284h] BYREF
  _com_error *v37; // [rsp+1A8h] [rbp-280h] BYREF
  const std::exception *v38; // [rsp+1B0h] [rbp-278h] BYREF
  _com_error *v39; // [rsp+1B8h] [rbp-270h] BYREF
  const std::exception *v40; // [rsp+1C0h] [rbp-268h] BYREF
  LPCRITICAL_SECTION v41[3]; // [rsp+1C8h] [rbp-260h] BYREF
  struct _RTL_CRITICAL_SECTION v42[4]; // [rsp+1E0h] [rbp-248h] BYREF
  HCLUSTER v43[2]; // [rsp+290h] [rbp-198h] BYREF
  _QWORD v44[4]; // [rsp+2A0h] [rbp-188h] BYREF
  _QWORD v45[3]; // [rsp+2C0h] [rbp-168h] BYREF
  int v46; // [rsp+2D8h] [rbp-150h]
  int v47; // [rsp+2DCh] [rbp-14Ch]
  int v48; // [rsp+2E0h] [rbp-148h]
  _DWORD v49[34]; // [rsp+2E8h] [rbp-140h] BYREF
  WCHAR szVolumeMountPoint[56]; // [rsp+370h] [rbp-B8h] BYREF

  v30 = a4;
  v27 = a3;
  v26 = a2;
  v31 = a2;
  v29 = a3;
  v45[0] = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
  v45[1] = L"CVssDiffMgmt::AddDiffAreaInternal";
  v45[2] = L"SPRDIFMC";
  v46 = 222;
  v47 = 2;
  v48 = 255;
  v49[30] = 0x1000000;
  memset_0(v49, 0, 0x78u);
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v32, (__int64)v45, 0);
  v18 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
  v19 = L"CVssDiffMgmt::AddDiffAreaInternal";
  v20 = L"SPRDIFMC";
  v21 = 227;
  v22 = 2;
  v23 = 255;
  v25 = 0x1000000;
  memset_0(v24, 0, sizeof(v24));
  CVssFunctionTracer::Trace(
    &v32,
    &v18,
    L"Parameters: \n  pwszVolumeName = %s\n  pwszDiffAreaVolumeName = %s\n  llMaximumDiffSpace = %I64d\n",
    v26,
    v27,
    v30);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    if ( !v26 )
    {
      v18 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
      v19 = L"CVssDiffMgmt::AddDiffAreaInternal";
      v20 = L"SPRDIFMC";
      v21 = 237;
      v22 = 2;
      v23 = 255;
      v25 = 0x1000000;
      memset_0(v24, 0, sizeof(v24));
      CVssFunctionTracer::Throw(
        (CVssFunctionTracer *)&v32,
        (const struct CVssDebugInfo *)&v18,
        -2147024809,
        L"NULL pwszVolumeName");
    }
    if ( !v27 )
    {
      v18 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
      v19 = L"CVssDiffMgmt::AddDiffAreaInternal";
      v20 = L"SPRDIFMC";
      v21 = 239;
      v22 = 2;
      v23 = 255;
      v25 = 0x1000000;
      memset_0(v24, 0, sizeof(v24));
      CVssFunctionTracer::Throw(
        (CVssFunctionTracer *)&v32,
        (const struct CVssDebugInfo *)&v18,
        -2147024809,
        L"NULL pwszDiffAreaVolumeName");
    }
    if ( v30 <= -2 || !v30 )
    {
      v18 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
      v19 = L"CVssDiffMgmt::AddDiffAreaInternal";
      v20 = L"SPRDIFMC";
      v21 = 242;
      v22 = 2;
      v23 = 255;
      v25 = 0x1000000;
      memset_0(v24, 0, sizeof(v24));
      CVssFunctionTracer::Throw(
        (CVssFunctionTracer *)&v32,
        (const struct CVssDebugInfo *)&v18,
        -2147024809,
        L"Invalid llMaximumDiffSpace");
    }
    if ( v30 != -1 )
    {
      MinDiffAreaOnVolume = CVssMachineInformation::GetMinDiffAreaOnVolume(v27);
      if ( v30 < MinDiffAreaOnVolume )
      {
        v18 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
        v19 = L"CVssDiffMgmt::AddDiffAreaInternal";
        v20 = L"SPRDIFMC";
        v21 = 246;
        v22 = 2;
        v23 = 255;
        v25 = 0x1000000;
        memset_0(v24, 0, sizeof(v24));
        CVssFunctionTracer::Throw(
          (CVssFunctionTracer *)&v32,
          (const struct CVssDebugInfo *)&v18,
          -2147212513,
          L"Not enough storage for the initial diff area allocation");
      }
    }
    v18 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
    v19 = L"CVssDiffMgmt::AddDiffAreaInternal";
    v20 = L"SPRDIFMC";
    v21 = 251;
    v22 = 2;
    v23 = 255;
    v25 = 0x1000000;
    memset_0(v24, 0, sizeof(v24));
    GetVolumeNameWithCheck((const struct CVssDebugInfo *)&v18, 2147942487u, v26, (WCHAR *)v45);
    v18 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
    v19 = L"CVssDiffMgmt::AddDiffAreaInternal";
    v20 = L"SPRDIFMC";
    v21 = 256;
    v22 = 2;
    v23 = 255;
    v25 = 0x1000000;
    memset_0(v24, 0, sizeof(v24));
    GetVolumeNameWithCheck((const struct CVssDebugInfo *)&v18, 2147942487u, v27, szVolumeMountPoint);
    AssociationFlags = CVssDiffMgmt::GetAssociationFlags((unsigned __int16 *)v45, szVolumeMountPoint);
    v18 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
    v19 = L"CVssDiffMgmt::AddDiffAreaInternal";
    v20 = L"SPRDIFMC";
    v21 = 262;
    v22 = 2;
    v23 = 255;
    v25 = 0x1000000;
    memset_0(v24, 0, sizeof(v24));
    LODWORD(v16) = AssociationFlags;
    CVssFunctionTracer::Trace(
      &v32,
      &v18,
      L"An association is proposed: %s - %s with flags 0x%08lx",
      v26,
      szVolumeMountPoint,
      v16);
    if ( (AssociationFlags & 4) != 0 )
    {
      v18 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
      v19 = L"CVssDiffMgmt::AddDiffAreaInternal";
      v20 = L"SPRDIFMC";
      v21 = 265;
      v22 = 2;
      v23 = 255;
      v25 = 0x1000000;
      memset_0(v24, 0, sizeof(v24));
      CVssFunctionTracer::Throw(
        (CVssFunctionTracer *)&v32,
        (const struct CVssDebugInfo *)&v18,
        -2147212532,
        L"Unsupported volume(s)");
    }
    if ( (AssociationFlags & 2) != 0 )
    {
      v18 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
      v19 = L"CVssDiffMgmt::AddDiffAreaInternal";
      v20 = L"SPRDIFMC";
      v21 = 267;
      v22 = 2;
      v23 = 255;
      v25 = 0x1000000;
      memset_0(v24, 0, sizeof(v24));
      CVssFunctionTracer::Throw(
        (CVssFunctionTracer *)&v32,
        (const struct CVssDebugInfo *)&v18,
        -2147212531,
        L"Association already exists");
    }
    if ( (AssociationFlags & 1) != 0 )
    {
      v18 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
      v19 = L"CVssDiffMgmt::AddDiffAreaInternal";
      v20 = L"SPRDIFMC";
      v21 = 269;
      v22 = 2;
      v23 = 255;
      v25 = 0x1000000;
      memset_0(v24, 0, sizeof(v24));
      CVssFunctionTracer::Throw(
        (CVssFunctionTracer *)&v32,
        (const struct CVssDebugInfo *)&v18,
        -2147212514,
        L"Original volume has snapshots on it");
    }
    if ( (AssociationFlags & 8) != 0 )
    {
      v18 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
      v19 = L"CVssDiffMgmt::AddDiffAreaInternal";
      v20 = L"SPRDIFMC";
      v21 = 271;
      v22 = 2;
      v23 = 255;
      v25 = 0x1000000;
      memset_0(v24, 0, sizeof(v24));
      CVssFunctionTracer::Throw(
        (CVssFunctionTracer *)&v32,
        (const struct CVssDebugInfo *)&v18,
        -2147212532,
        L"Encryted volume requires diff area on the same volume");
    }
    AssociationFlags = CVssDiffMgmt::GetSectorSizeForVolume(v5, szVolumeMountPoint);
    SectorSizeForVolume = CVssDiffMgmt::GetSectorSizeForVolume(v6, (unsigned __int16 *)v45);
    if ( AssociationFlags > SectorSizeForVolume )
    {
      v18 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
      v19 = L"CVssDiffMgmt::AddDiffAreaInternal";
      v20 = L"SPRDIFMC";
      v21 = 275;
      v22 = 2;
      v23 = 255;
      v25 = 0x1000000;
      memset_0(v24, 0, sizeof(v24));
      CVssFunctionTracer::Throw(
        (CVssFunctionTracer *)&v32,
        (const struct CVssDebugInfo *)&v18,
        -2147212532,
        L"Sector size of diff area volume must be <= sector size of original.");
    }
    v17[0] = 0;
    if ( VssVolumeHasParentVolume((const unsigned __int16 *)v45, v17, v8, v9) )
    {
      if ( (unsigned int)_o__wcsicmp(v45, szVolumeMountPoint) )
      {
        v18 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
        v19 = L"CVssDiffMgmt::AddDiffAreaInternal";
        v20 = L"SPRDIFMC";
        v21 = 284;
        v22 = 2;
        v23 = 255;
        v25 = 0x1000000;
        memset_0(v24, 0, sizeof(v24));
        CVssFunctionTracer::Throw(
          (CVssFunctionTracer *)&v32,
          (const struct CVssDebugInfo *)&v18,
          -2147212532,
          L"Nested volume requires diff area on the same volume");
      }
      if ( !v17[0] )
      {
        v18 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
        v19 = L"CVssDiffMgmt::AddDiffAreaInternal";
        v20 = L"SPRDIFMC";
        v21 = 289;
        v22 = 2;
        v23 = 255;
        v25 = 0x1000000;
        memset_0(v24, 0, sizeof(v24));
        CVssFunctionTracer::Throw(
          (CVssFunctionTracer *)&v32,
          (const struct CVssDebugInfo *)&v18,
          -2147212500,
          L"Volume %s is too deeply nested",
          v45);
      }
    }
    if ( VssVolumeHasParentVolume(szVolumeMountPoint, v17, v10, v11)
      && (unsigned int)_o__wcsicmp(v45, szVolumeMountPoint) )
    {
      v18 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
      v19 = L"CVssDiffMgmt::AddDiffAreaInternal";
      v20 = L"SPRDIFMC";
      v21 = 297;
      v22 = 2;
      v23 = 255;
      v25 = 0x1000000;
      memset_0(v24, 0, sizeof(v24));
      CVssFunctionTracer::Throw(
        (CVssFunctionTracer *)&v32,
        (const struct CVssDebugInfo *)&v18,
        -2147212500,
        L"Volume %s is too deeply nested",
        szVolumeMountPoint);
    }
    CVssAutomaticLock2::CVssAutomaticLock2(
      (CVssAutomaticLock2 *)v41,
      (struct CVssCriticalSection *)CVsSoftwareProvider::m_cs);
    v18 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
    v19 = L"CVssDiffMgmt::AddDiffAreaInternal";
    v20 = L"SPRDIFMC";
    v21 = 303;
    v22 = 2;
    v23 = 255;
    v25 = 0x1000000;
    memset_0(v24, 0, sizeof(v24));
    CVssFunctionTracer::AddOperation((struct CVssFunctionTracer *)&v32, (const struct CVssDebugInfo *)&v18, 425);
    v18 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
    v19 = L"CVssDiffMgmt::AddDiffAreaInternal";
    v20 = L"SPRDIFMC";
    v21 = 304;
    v22 = 2;
    v23 = 255;
    v25 = 0x1000000;
    memset_0(v24, 0, sizeof(v24));
    CVssFunctionTracer::AddContext((__int64)&v32, (const struct CVssDebugInfo *)&v18);
    v18 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
    v19 = L"CVssDiffMgmt::AddDiffAreaInternal";
    v20 = L"SPRDIFMC";
    v21 = 305;
    v22 = 2;
    v23 = 255;
    v25 = 0x1000000;
    memset_0(v24, 0, sizeof(v24));
    CVssFunctionTracer::AddContext((__int64)&v32, (const struct CVssDebugInfo *)&v18);
    v17[0] = 0;
    CVssDiffArea::CVssDiffArea((CVssDiffArea *)v42, v12);
    ((void (__stdcall *)(CVssDiffArea *, const unsigned __int16 *, bool))CVssDiffArea::InitializeForVolume)(
      (CVssDiffArea *)v42,
      (const unsigned __int16 *)v45,
      0);
    CVssDiffArea::Clear((CVssDiffArea *)v42);
    CVssDiffArea::AddVolume((CVssDiffArea *)v42, szVolumeMountPoint);
    CVssDiffArea::ChangeDiffAreaMaximumSize((CVssDiffArea *)v42, v30, 0);
    CVssDiffArea::SetExplicit((CVssDiffArea *)v42, 1);
    CVssClusterAPI::CVssClusterAPI((CVssClusterAPI *)v43);
    if ( __eh34_try(0, 1) )
    {
      __eh34_scope_strut(1);
      if ( CVssClusterAPI::Initialize((CVssClusterAPI *)v43, v13) )
        v17[0] = CVssClusterAPI::AddDependency((CVssClusterAPI *)v43, (const unsigned __int16 *)v45, szVolumeMountPoint);
    }
    if ( __eh34_catch(1) )
    {
      if ( __eh34_catch_type(1, &long `RTTI Type Descriptor', (long *)&v35) )
      {
        CVssFunctionTracer::HandleHresultException(
          (CVssFunctionTracer *)&v32,
          v35,
          L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx",
          L"SPRDIFMC",
          L"CVssDiffMgmt::AddDiffAreaInternal",
          0x144u,
          v34);
        v26 = v31;
        v27 = v29;
        __eh34_try_continuation(1, &long `RTTI Type Descriptor', &loc_1800285EC);
        goto LABEL_32;
      }
      if ( __eh34_catch_type(1, &_com_error `RTTI Type Descriptor', &v37) )
        CVssFunctionTracer::HandleComException(
          (CVssFunctionTracer *)&v32,
          v37,
          L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx",
          L"SPRDIFMC",
          L"CVssDiffMgmt::AddDiffAreaInternal",
          0x144u,
          v34);
      if ( __eh34_catch_type(1, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        CVssFunctionTracer::HandleStdBadAllocException(
          (CVssFunctionTracer *)&v32,
          L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx",
          L"SPRDIFMC",
          L"CVssDiffMgmt::AddDiffAreaInternal",
          0x144u,
          v34);
        v26 = v31;
        v27 = v29;
        __eh34_try_continuation(1, &std::bad_alloc `RTTI Type Descriptor', &loc_180028600);
        goto LABEL_32;
      }
      if ( __eh34_catch_type(1, &std::exception `RTTI Type Descriptor', &v38) )
        CVssFunctionTracer::HandleStdGenericException(
          (CVssFunctionTracer *)&v32,
          v38,
          L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx",
          L"SPRDIFMC",
          L"CVssDiffMgmt::AddDiffAreaInternal",
          0x144u,
          v34);
    }
LABEL_32:
    if ( v33 < 0 )
    {
      CVssDiffArea::Clear((CVssDiffArea *)v42);
      if ( v17[0] && !CVssClusterAPI::RemoveDependency(v43, (const unsigned __int16 *)v45, szVolumeMountPoint) )
      {
        v18 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
        v19 = L"CVssDiffMgmt::AddDiffAreaInternal";
        v20 = L"SPRDIFMC";
        v21 = 335;
        v22 = 2;
        v23 = 255;
        v25 = 0x1000000;
        memset_0(v24, 0, sizeof(v24));
        CVssFunctionTracer::LogGenericWarning(&v32, &v18, L"cluster.RemoveDependency(%s, %s)", v26, v27);
      }
      CVssFunctionTracer::ReThrow((CVssFunctionTracer *)&v32);
    }
    std::wstring::_Tidy_deallocate(v44);
    CVssDiffArea::~CVssDiffArea(v42);
    CVssAutomaticLock2::~CVssAutomaticLock2(v41);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &long `RTTI Type Descriptor', (long *)&v36) )
    {
      CVssFunctionTracer::HandleHresultException(
        (CVssFunctionTracer *)&v32,
        v36,
        L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx",
        L"SPRDIFMC",
        L"CVssDiffMgmt::AddDiffAreaInternal",
        0x157u,
        v34);
      __eh34_try_continuation(0, &long `RTTI Type Descriptor', &loc_180028789);
      goto LABEL_39;
    }
    if ( __eh34_catch_type(0, &_com_error `RTTI Type Descriptor', &v39) )
      CVssFunctionTracer::HandleComException(
        (CVssFunctionTracer *)&v32,
        v39,
        L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx",
        L"SPRDIFMC",
        L"CVssDiffMgmt::AddDiffAreaInternal",
        0x157u,
        v34);
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      CVssFunctionTracer::HandleStdBadAllocException(
        (CVssFunctionTracer *)&v32,
        L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx",
        L"SPRDIFMC",
        L"CVssDiffMgmt::AddDiffAreaInternal",
        0x157u,
        v34);
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18002878D);
      goto LABEL_39;
    }
    if ( __eh34_catch_type(0, &std::exception `RTTI Type Descriptor', &v40) )
      CVssFunctionTracer::HandleStdGenericException(
        (CVssFunctionTracer *)&v32,
        v40,
        L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx",
        L"SPRDIFMC",
        L"CVssDiffMgmt::AddDiffAreaInternal",
        0x157u,
        v34);
  }
LABEL_39:
  v14 = v33;
  CVssFunctionTracer::~CVssFunctionTracer(&v32);
  return v14;
}

```

## disassembly

```asm
0x180027ca0  mov     r11, rsp
0x180027ca3  push    rbx
0x180027ca4  push    rsi
0x180027ca5  push    rdi
0x180027ca6  push    r12
0x180027ca8  push    r13
0x180027caa  push    r14
0x180027cac  push    r15
0x180027cae  sub     rsp, 3F0h
0x180027cb5  mov     rax, cs:__security_cookie
0x180027cbc  xor     rax, rsp
0x180027cbf  mov     [rsp+428h+var_48], rax
0x180027cc7  mov     [rsp+428h+var_310], r9
0x180027ccf  mov     rax, r8
0x180027cd2  mov     [rsp+428h+var_328], rax
0x180027cda  mov     [rsp+428h+var_330], rdx
0x180027ce2  mov     [rsp+428h+var_308], rdx
0x180027cea  mov     [rsp+428h+var_318], rax
0x180027cf2  lea     rsi, aBaseStorVssMod_2; "base\\stor\\vss\\modules\\softprv\\src"...
0x180027cf9  mov     [r11-168h], rsi
0x180027d00  lea     r14, aCvssdiffmgmtAd_0; "CVssDiffMgmt::AddDiffAreaInternal"
0x180027d07  mov     [r11-160h], r14
0x180027d0e  lea     r15, aSprdifmc; "SPRDIFMC"
0x180027d15  mov     [r11-158h], r15
0x180027d1c  mov     [rsp+428h+var_150], 0DEh
0x180027d27  mov     edi, 2
0x180027d2c  mov     [rsp+428h+var_14C], edi
0x180027d33  mov     r12d, 0FFh
0x180027d39  mov     [r11-148h], r12d
0x180027d40  xor     ebx, ebx
0x180027d42  mov     [rsp+428h+var_C8], 1000000h
0x180027d4d  lea     r13d, [rdi+76h]
0x180027d51  mov     r8d, r13d; Size
0x180027d54  xor     edx, edx; Val
0x180027d56  lea     rcx, [r11-140h]; void *
0x180027d5d  call    memset_0
0x180027d62  xor     r8d, r8d
0x180027d65  lea     rdx, [rsp+428h+var_168]
0x180027d6d  lea     rcx, [rsp+428h+var_2F8]
0x180027d75  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x180027d7a  nop
0x180027d7b  mov     [rsp+428h+var_3D8], rsi
0x180027d80  mov     [rsp+428h+var_3D0], r14
0x180027d85  mov     [rsp+428h+var_3C8], r15
0x180027d8a  mov     [rsp+428h+var_3C0], 0E3h
0x180027d92  mov     [rsp+428h+var_3BC], edi
0x180027d96  mov     [rsp+428h+var_3B8], r12d
0x180027d9b  mov     [rsp+428h+var_338], 1000000h
0x180027da6  mov     r8d, r13d; Size
0x180027da9  xor     edx, edx; Val
0x180027dab  lea     rcx, [rsp+428h+var_3B0]; void *
0x180027db0  call    memset_0
0x180027db5  mov     rcx, [rsp+428h+var_310]
0x180027dbd  mov     [rsp+428h+var_400], rcx
0x180027dc2  mov     r8, [rsp+428h+var_328]
0x180027dca  mov     [rsp+428h+var_408], r8
0x180027dcf  mov     r9, [rsp+428h+var_330]
0x180027dd7  lea     r8, aParametersPwsz_5; "Parameters: \n  pwszVolumeName = %s\n  "...
0x180027dde  lea     rdx, [rsp+428h+var_3D8]
0x180027de3  lea     rcx, [rsp+428h+var_2F8]
0x180027deb  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180027df0  cmp     [rsp+428h+var_330], rbx
0x180027df8  jnz     short loc_180027E53
0x180027dfa  mov     [rsp+428h+var_3D8], rsi
0x180027dff  mov     [rsp+428h+var_3D0], r14
0x180027e04  mov     [rsp+428h+var_3C8], r15
0x180027e09  mov     [rsp+428h+var_3C0], 0EDh
0x180027e11  mov     [rsp+428h+var_3BC], edi
0x180027e15  mov     [rsp+428h+var_3B8], r12d
0x180027e1a  mov     [rsp+428h+var_338], 1000000h
0x180027e25  mov     r8d, r13d; Size
0x180027e28  xor     edx, edx; Val
0x180027e2a  lea     rcx, [rsp+428h+var_3B0]; void *
0x180027e2f  call    memset_0
0x180027e34  lea     r9, aNullPwszvolume; "NULL pwszVolumeName"
0x180027e3b  mov     r8d, 80070057h
0x180027e41  lea     rdx, [rsp+428h+var_3D8]
0x180027e46  lea     rcx, [rsp+428h+var_2F8]
0x180027e4e  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180027e53  mov     rax, [rsp+428h+var_328]
0x180027e5b  test    rax, rax
0x180027e5e  jnz     short loc_180027EB9
0x180027e60  mov     [rsp+428h+var_3D8], rsi
0x180027e65  mov     [rsp+428h+var_3D0], r14
0x180027e6a  mov     [rsp+428h+var_3C8], r15
0x180027e6f  mov     [rsp+428h+var_3C0], 0EFh
0x180027e77  mov     [rsp+428h+var_3BC], edi
0x180027e7b  mov     [rsp+428h+var_3B8], r12d
0x180027e80  mov     [rsp+428h+var_338], 1000000h
0x180027e8b  mov     r8, r13; Size
0x180027e8e  xor     edx, edx; Val
0x180027e90  lea     rcx, [rsp+428h+var_3B0]; void *
0x180027e95  call    memset_0
0x180027e9a  lea     r9, aNullPwszdiffar; "NULL pwszDiffAreaVolumeName"
0x180027ea1  mov     r8d, 80070057h
0x180027ea7  lea     rdx, [rsp+428h+var_3D8]
0x180027eac  lea     rcx, [rsp+428h+var_2F8]
0x180027eb4  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180027eb9  mov     rcx, [rsp+428h+var_310]
0x180027ec1  cmp     rcx, 0FFFFFFFFFFFFFFFEh
0x180027ec5  jle     loc_18002872F
0x180027ecb  test    rcx, rcx
0x180027ece  jz      loc_18002872F
0x180027ed4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180027ed8  jz      short loc_180027F45
0x180027eda  mov     rcx, rax; unsigned __int16 *
0x180027edd  call    ?GetMinDiffAreaOnVolume@CVssMachineInformation@@SA_JPEBG@Z; CVssMachineInformation::GetMinDiffAreaOnVolume(ushort const *)
0x180027ee2  cmp     [rsp+428h+var_310], rax
0x180027eea  jge     short loc_180027F45
0x180027eec  mov     [rsp+428h+var_3D8], rsi
0x180027ef1  mov     [rsp+428h+var_3D0], r14
0x180027ef6  mov     [rsp+428h+var_3C8], r15
0x180027efb  mov     [rsp+428h+var_3C0], 0F6h
0x180027f03  mov     [rsp+428h+var_3BC], edi
0x180027f07  mov     [rsp+428h+var_3B8], r12d
0x180027f0c  mov     [rsp+428h+var_338], 1000000h
0x180027f17  mov     r8, r13; Size
0x180027f1a  xor     edx, edx; Val
0x180027f1c  lea     rcx, [rsp+428h+var_3B0]; void *
0x180027f21  call    memset_0
0x180027f26  lea     r9, aNotEnoughStora; "Not enough storage for the initial diff"...
0x180027f2d  mov     r8d, 8004231Fh
0x180027f33  lea     rdx, [rsp+428h+var_3D8]
0x180027f38  lea     rcx, [rsp+428h+var_2F8]
0x180027f40  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180027f45  mov     [rsp+428h+var_3D8], rsi
0x180027f4a  mov     [rsp+428h+var_3D0], r14
0x180027f4f  mov     [rsp+428h+var_3C8], r15
0x180027f54  mov     [rsp+428h+var_3C0], 0FBh
0x180027f5c  mov     [rsp+428h+var_3BC], edi
0x180027f60  mov     [rsp+428h+var_3B8], r12d
0x180027f65  mov     [rsp+428h+var_338], 1000000h
0x180027f70  mov     r8, r13; Size
0x180027f73  xor     edx, edx; Val
0x180027f75  lea     rcx, [rsp+428h+var_3B0]; void *
0x180027f7a  call    memset_0
0x180027f7f  lea     r9, [rsp+428h+var_168]
0x180027f87  mov     r8, [rsp+428h+var_330]
0x180027f8f  mov     edx, 80070057h
0x180027f94  lea     rcx, [rsp+428h+var_3D8]
0x180027f99  call    ?GetVolumeNameWithCheck@@YAXUCVssDebugInfo@@JPEBGPEAGK@Z; GetVolumeNameWithCheck(CVssDebugInfo,long,ushort const *,ushort *,ulong)
0x180027f9e  mov     [rsp+428h+var_3D8], rsi
0x180027fa3  mov     [rsp+428h+var_3D0], r14
0x180027fa8  mov     [rsp+428h+var_3C8], r15
0x180027fad  mov     [rsp+428h+var_3C0], 100h
0x180027fb5  mov     [rsp+428h+var_3BC], edi
0x180027fb9  mov     [rsp+428h+var_3B8], r12d
0x180027fbe  mov     [rsp+428h+var_338], 1000000h
0x180027fc9  mov     r8, r13; Size
0x180027fcc  xor     edx, edx; Val
0x180027fce  lea     rcx, [rsp+428h+var_3B0]; void *
0x180027fd3  call    memset_0
0x180027fd8  lea     r9, [rsp+428h+szVolumeMountPoint]
0x180027fe0  mov     r8, [rsp+428h+var_328]
0x180027fe8  mov     edx, 80070057h
0x180027fed  lea     rcx, [rsp+428h+var_3D8]
0x180027ff2  call    ?GetVolumeNameWithCheck@@YAXUCVssDebugInfo@@JPEBGPEAGK@Z; GetVolumeNameWithCheck(CVssDebugInfo,long,ushort const *,ushort *,ulong)
0x180027ff7  lea     rdx, [rsp+428h+szVolumeMountPoint]; unsigned __int16 *
0x180027fff  lea     rcx, [rsp+428h+var_168]; unsigned __int16 *
0x180028007  call    ?GetAssociationFlags@CVssDiffMgmt@@SAJPEAG0@Z; CVssDiffMgmt::GetAssociationFlags(ushort *,ushort *)
0x18002800c  mov     [rsp+428h+var_320], eax
0x180028013  mov     [rsp+428h+var_3D8], rsi
0x180028018  mov     [rsp+428h+var_3D0], r14
0x18002801d  mov     [rsp+428h+var_3C8], r15
0x180028022  mov     [rsp+428h+var_3C0], 106h
0x18002802a  mov     [rsp+428h+var_3BC], edi
0x18002802e  mov     [rsp+428h+var_3B8], r12d
0x180028033  mov     [rsp+428h+var_338], 1000000h
0x18002803e  mov     r8, r13; Size
0x180028041  xor     edx, edx; Val
0x180028043  lea     rcx, [rsp+428h+var_3B0]; void *
0x180028048  call    memset_0
0x18002804d  mov     eax, [rsp+428h+var_320]
0x180028054  mov     dword ptr [rsp+428h+var_400], eax
0x180028058  lea     rax, [rsp+428h+szVolumeMountPoint]
0x180028060  mov     [rsp+428h+var_408], rax
0x180028065  mov     r9, [rsp+428h+var_330]
0x18002806d  lea     r8, aAnAssociationI_1; "An association is proposed: %s - %s wit"...
0x180028074  lea     rdx, [rsp+428h+var_3D8]
0x180028079  lea     rcx, [rsp+428h+var_2F8]
0x180028081  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180028086  mov     eax, [rsp+428h+var_320]
0x18002808d  test    al, 4
0x18002808f  jz      short loc_1800280EA
0x180028091  mov     [rsp+428h+var_3D8], rsi
0x180028096  mov     [rsp+428h+var_3D0], r14
0x18002809b  mov     [rsp+428h+var_3C8], r15
0x1800280a0  mov     [rsp+428h+var_3C0], 109h
0x1800280a8  mov     [rsp+428h+var_3BC], edi
0x1800280ac  mov     [rsp+428h+var_3B8], r12d
0x1800280b1  mov     [rsp+428h+var_338], 1000000h
0x1800280bc  mov     r8, r13; Size
0x1800280bf  xor     edx, edx; Val
0x1800280c1  lea     rcx, [rsp+428h+var_3B0]; void *
0x1800280c6  call    memset_0
0x1800280cb  lea     r9, aUnsupportedVol; "Unsupported volume(s)"
0x1800280d2  mov     r8d, 8004230Ch
0x1800280d8  lea     rdx, [rsp+428h+var_3D8]
0x1800280dd  lea     rcx, [rsp+428h+var_2F8]
0x1800280e5  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x1800280ea  test    dil, al
0x1800280ed  jz      short loc_180028148
0x1800280ef  mov     [rsp+428h+var_3D8], rsi
0x1800280f4  mov     [rsp+428h+var_3D0], r14
0x1800280f9  mov     [rsp+428h+var_3C8], r15
0x1800280fe  mov     [rsp+428h+var_3C0], 10Bh
0x180028106  mov     [rsp+428h+var_3BC], edi
0x18002810a  mov     [rsp+428h+var_3B8], r12d
0x18002810f  mov     [rsp+428h+var_338], 1000000h
0x18002811a  mov     r8, r13; Size
0x18002811d  xor     edx, edx; Val
0x18002811f  lea     rcx, [rsp+428h+var_3B0]; void *
0x180028124  call    memset_0
0x180028129  lea     r9, aAssociationAlr; "Association already exists"
0x180028130  mov     r8d, 8004230Dh
0x180028136  lea     rdx, [rsp+428h+var_3D8]
0x18002813b  lea     rcx, [rsp+428h+var_2F8]
0x180028143  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180028148  test    al, 1
0x18002814a  jz      short loc_1800281A5
0x18002814c  mov     [rsp+428h+var_3D8], rsi
0x180028151  mov     [rsp+428h+var_3D0], r14
0x180028156  mov     [rsp+428h+var_3C8], r15
0x18002815b  mov     [rsp+428h+var_3C0], 10Dh
0x180028163  mov     [rsp+428h+var_3BC], edi
0x180028167  mov     [rsp+428h+var_3B8], r12d
0x18002816c  mov     [rsp+428h+var_338], 1000000h
0x180028177  mov     r8, r13; Size
0x18002817a  xor     edx, edx; Val
0x18002817c  lea     rcx, [rsp+428h+var_3B0]; void *
0x180028181  call    memset_0
0x180028186  lea     r9, aOriginalVolume; "Original volume has snapshots on it"
0x18002818d  mov     r8d, 8004231Eh
0x180028193  lea     rdx, [rsp+428h+var_3D8]
0x180028198  lea     rcx, [rsp+428h+var_2F8]
0x1800281a0  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x1800281a5  test    al, 8
0x1800281a7  jz      short loc_180028202
0x1800281a9  mov     [rsp+428h+var_3D8], rsi
0x1800281ae  mov     [rsp+428h+var_3D0], r14
0x1800281b3  mov     [rsp+428h+var_3C8], r15
0x1800281b8  mov     [rsp+428h+var_3C0], 10Fh
0x1800281c0  mov     [rsp+428h+var_3BC], edi
0x1800281c4  mov     [rsp+428h+var_3B8], r12d
0x1800281c9  mov     [rsp+428h+var_338], 1000000h
0x1800281d4  mov     r8, r13; Size
0x1800281d7  xor     edx, edx; Val
0x1800281d9  lea     rcx, [rsp+428h+var_3B0]; void *
0x1800281de  call    memset_0
0x1800281e3  lea     r9, aEncrytedVolume; "Encryted volume requires diff area on t"...
0x1800281ea  mov     r8d, 8004230Ch
0x1800281f0  lea     rdx, [rsp+428h+var_3D8]
0x1800281f5  lea     rcx, [rsp+428h+var_2F8]
0x1800281fd  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180028202  lea     rdx, [rsp+428h+szVolumeMountPoint]; unsigned __int16 *
0x18002820a  call    ?GetSectorSizeForVolume@CVssDiffMgmt@@AEAAKPEAG@Z; CVssDiffMgmt::GetSectorSizeForVolume(ushort *)
0x18002820f  mov     [rsp+428h+var_320], eax
0x180028216  lea     rdx, [rsp+428h+var_168]; unsigned __int16 *
0x18002821e  call    ?GetSectorSizeForVolume@CVssDiffMgmt@@AEAAKPEAG@Z; CVssDiffMgmt::GetSectorSizeForVolume(ushort *)
0x180028223  cmp     [rsp+428h+var_320], eax
0x18002822a  jbe     short loc_180028285
0x18002822c  mov     [rsp+428h+var_3D8], rsi
0x180028231  mov     [rsp+428h+var_3D0], r14
0x180028236  mov     [rsp+428h+var_3C8], r15
0x18002823b  mov     [rsp+428h+var_3C0], 113h
0x180028243  mov     [rsp+428h+var_3BC], edi
0x180028247  mov     [rsp+428h+var_3B8], r12d
0x18002824c  mov     [rsp+428h+var_338], 1000000h
0x180028257  mov     r8, r13; Size
0x18002825a  xor     edx, edx; Val
0x18002825c  lea     rcx, [rsp+428h+var_3B0]; void *
0x180028261  call    memset_0
0x180028266  lea     r9, aSectorSizeOfDi; "Sector size of diff area volume must be"...
0x18002826d  mov     r8d, 8004230Ch
0x180028273  lea     rdx, [rsp+428h+var_3D8]
0x180028278  lea     rcx, [rsp+428h+var_2F8]
0x180028280  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180028285  mov     [rsp+428h+var_3E8], bl
0x180028289  lea     rdx, [rsp+428h+var_3E8]; bool *
0x18002828e  lea     rcx, [rsp+428h+var_168]; unsigned __int16 *
0x180028296  call    ?VssVolumeHasParentVolume@@YA_NPEBGPEA_NPEAGH@Z; VssVolumeHasParentVolume(ushort const *,bool *,ushort *,int)
0x18002829b  test    al, al
0x18002829d  jz      loc_180028382
0x1800282a3  lea     rdx, [rsp+428h+szVolumeMountPoint]
0x1800282ab  lea     rcx, [rsp+428h+var_168]
0x1800282b3  call    cs:__imp__o__wcsicmp
0x1800282b9  test    eax, eax
0x1800282bb  jz      short loc_180028316
0x1800282bd  mov     [rsp+428h+var_3D8], rsi
0x1800282c2  mov     [rsp+428h+var_3D0], r14
0x1800282c7  mov     [rsp+428h+var_3C8], r15
0x1800282cc  mov     [rsp+428h+var_3C0], 11Ch
0x1800282d4  mov     [rsp+428h+var_3BC], edi
0x1800282d8  mov     [rsp+428h+var_3B8], r12d
0x1800282dd  mov     [rsp+428h+var_338], 1000000h
0x1800282e8  mov     r8, r13; Size
0x1800282eb  xor     edx, edx; Val
0x1800282ed  lea     rcx, [rsp+428h+var_3B0]; void *
0x1800282f2  call    memset_0
0x1800282f7  lea     r9, aNestedVolumeRe; "Nested volume requires diff area on the"...
  ... truncated ...
```
