# CVssDiffMgmt::QueryVolumesSupportedForDiffAreas(ushort *,IVssEnumMgmtObject * *)

- ea: `0x18002d1f0`
- end: `0x18002deed`
- name: `?QueryVolumesSupportedForDiffAreas@CVssDiffMgmt@@UEAAJPEAGPEAPEAUIVssEnumMgmtObject@@@Z`
- size: `3325`
- prototype: `__int64 __fastcall(CVssDiffMgmt *__hidden this, unsigned __int16 *, struct IVssEnumMgmtObject **)`
- caller_count: `0`
- callee_count: `34`
- tags: `broker_com_uri`

## callees

- `0x180001580`
- `0x180001acc`
- `0x18000212c`
- `0x1800034cc`
- `0x1800036c4`
- `0x180003888`
- `0x180007604`
- `0x180011178`
- `0x18001c404`
- `0x18001c424`
- `0x18001d424`
- `0x180025c40`
- `0x180025ea4`
- `0x1800275b4`
- `0x18002a4f8`
- `0x18002a774`
- `0x18002d1f0`
- `0x18002e79c`
- `0x180031914`
- `0x180033a8c`
- `0x180033c78`
- `0x180034a4c`
- `0x18003649c`
- `0x1800367b8`
- `0x18003b0ec`
- `0x18003d78c`
- `0x18003df28`
- `0x18003e574`
- `0x18003eafc`
- `0x18003ef54`
- `0x18003f1f4`
- `0x18003f52c`
- `0x180040cb0`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dd38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dd38`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18002dd2a`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18002dd2a`

## string_xrefs

- `0x18002d6a3`: `Error reading encryption status on volume %s (0x%08lx)`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CVssDiffMgmt::QueryVolumesSupportedForDiffAreas(
        CVssDiffMgmt *this,
        unsigned __int16 *a2,
        struct IVssEnumMgmtObject **a3)
{
  struct IVssEnumMgmtObject **v3; // rdi
  struct _HRESOURCE *PhysicalDiskResourceForVolumeName; // r14
  char v6; // al
  _QWORD *v7; // rax
  __int64 v8; // rsi
  unsigned __int16 **v9; // r8
  const unsigned __int16 *v10; // rdx
  char v11; // r12
  int v12; // ebx
  unsigned __int16 *v13; // r8
  bool v14; // r13
  char HasParentVolume; // r15
  bool v16; // bl
  unsigned __int16 *v17; // rcx
  int v18; // edx
  int v19; // eax
  char VolumeInformationFlags; // al
  unsigned __int16 **v21; // r8
  __int64 v22; // rax
  unsigned int SectorSizeForVolume; // edi
  CVssDiffMgmt *v24; // rcx
  CVssClusterAPI *v25; // rcx
  struct _HRESOURCE *v26; // rbx
  bool v27; // zf
  CVssClusterAPI *v28; // rcx
  bool CanEstablishDependency; // al
  DWORD LastError; // ebx
  unsigned int v31; // ebx
  __int64 v33; // [rsp+20h] [rbp-718h]
  __int64 v34; // [rsp+20h] [rbp-718h]
  bool v35; // [rsp+40h] [rbp-6F8h] BYREF
  char v36; // [rsp+41h] [rbp-6F7h]
  LPVOID v37; // [rsp+48h] [rbp-6F0h] BYREF
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+50h] [rbp-6E8h] BYREF
  const unsigned __int16 *v39; // [rsp+58h] [rbp-6E0h] BYREF
  const unsigned __int16 *v40; // [rsp+60h] [rbp-6D8h]
  const unsigned __int16 *v41; // [rsp+68h] [rbp-6D0h]
  int v42; // [rsp+70h] [rbp-6C8h]
  int v43; // [rsp+74h] [rbp-6C4h]
  int v44; // [rsp+78h] [rbp-6C0h]
  _BYTE v45[120]; // [rsp+80h] [rbp-6B8h] BYREF
  int v46; // [rsp+F8h] [rbp-640h]
  struct IVssEnumMgmtObject **v47; // [rsp+100h] [rbp-638h]
  union _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+108h] [rbp-630h] BYREF
  union _ULARGE_INTEGER FreeBytesAvailableToCaller; // [rsp+110h] [rbp-628h] BYREF
  unsigned __int16 *v50; // [rsp+118h] [rbp-620h]
  LPVOID v51; // [rsp+120h] [rbp-618h] BYREF
  BOOL v52; // [rsp+128h] [rbp-610h]
  unsigned int v53; // [rsp+144h] [rbp-5F4h]
  unsigned int v54; // [rsp+190h] [rbp-5A8h] BYREF
  __int64 v55; // [rsp+198h] [rbp-5A0h] BYREF
  __int64 v56; // [rsp+1A0h] [rbp-598h] BYREF
  char v57; // [rsp+1A8h] [rbp-590h]
  _com_error *v58; // [rsp+1B0h] [rbp-588h] BYREF
  const std::exception *v59; // [rsp+1B8h] [rbp-580h] BYREF
  LPCRITICAL_SECTION v60[2]; // [rsp+1C0h] [rbp-578h] BYREF
  HCLUSTER v61[2]; // [rsp+1D0h] [rbp-568h] BYREF
  _QWORD v62[4]; // [rsp+1E0h] [rbp-558h] BYREF
  unsigned __int16 v63[4]; // [rsp+200h] [rbp-538h] BYREF
  const unsigned __int16 *v64; // [rsp+208h] [rbp-530h]
  const unsigned __int16 *v65; // [rsp+210h] [rbp-528h]
  int v66; // [rsp+218h] [rbp-520h]
  int v67; // [rsp+21Ch] [rbp-51Ch]
  int v68; // [rsp+220h] [rbp-518h]
  _BYTE v69[120]; // [rsp+228h] [rbp-510h] BYREF
  int v70; // [rsp+2A0h] [rbp-498h]
  WCHAR v71[56]; // [rsp+410h] [rbp-328h] BYREF
  unsigned __int16 v72[56]; // [rsp+480h] [rbp-2B8h] BYREF
  WCHAR DirectoryName[264]; // [rsp+4F0h] [rbp-248h] BYREF

  v3 = a3;
  v47 = a3;
  v50 = a2;
  *(_QWORD *)v63 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
  v64 = L"CVssDiffMgmt::QueryVolumesSupportedForDiffAreas";
  v65 = L"SPRDIFMC";
  v66 = 624;
  v67 = 2;
  v68 = 255;
  PhysicalDiskResourceForVolumeName = 0;
  v70 = 0x1000000;
  memset_0(v69, 0, sizeof(v69));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v51, (__int64)v63, 0);
  if ( v3 )
    *v3 = 0;
  try
  {
    v6 = IsInGroup();
    *(_QWORD *)v63 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
    v64 = L"CVssDiffMgmt::QueryVolumesSupportedForDiffAreas";
    v65 = L"SPRDIFMC";
    v67 = 2;
    v68 = 255;
    v70 = 0x1000000;
    if ( !v6 )
    {
      v66 = 633;
      memset_0(v69, 0, sizeof(v69));
      CVssFunctionTracer::Throw(
        (CVssFunctionTracer *)&v51,
        (const struct CVssDebugInfo *)v63,
        -2147024891,
        L"The client process is not running under an administrator account");
    }
    v66 = 637;
    memset_0(v69, 0, sizeof(v69));
    CVssFunctionTracer::Trace(&v51, v63, L"Parameters: pwszOriginalVolumeName = %s  ppEnum = %p", a2, v3);
    if ( !v3 )
    {
      *(_QWORD *)v63 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
      v64 = L"CVssDiffMgmt::QueryVolumesSupportedForDiffAreas";
      v65 = L"SPRDIFMC";
      v66 = 643;
      v67 = 2;
      v68 = 255;
      v70 = 0x1000000;
      memset_0(v69, 0, sizeof(v69));
      CVssFunctionTracer::Throw(
        (CVssFunctionTracer *)&v51,
        (const struct CVssDebugInfo *)v63,
        -2147024809,
        L"NULL ppEnum");
    }
    v7 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = (__int64)v7;
    TotalNumberOfFreeBytes.QuadPart = (ULONGLONG)v7;
    if ( v7 )
    {
      v7[1] = 0;
      v7[2] = 0;
      *((_DWORD *)v7 + 6) = 0;
      *v7 = &VSS_MGMT_OBJECT_PROP_Array::`vftable';
    }
    else
    {
      v8 = 0;
    }
    if ( !v8 )
    {
      *(_QWORD *)v63 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
      v64 = L"CVssDiffMgmt::QueryVolumesSupportedForDiffAreas";
      v65 = L"SPRDIFMC";
      v66 = 648;
      v67 = 2;
      v68 = 255;
      v70 = 0x1000000;
      memset_0(v69, 0, sizeof(v69));
      CVssFunctionTracer::Throw(
        (CVssFunctionTracer *)&v51,
        (const struct CVssDebugInfo *)v63,
        -2147024882,
        L"Memory allocation error.");
    }
    v55 = v8;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
    CVssAutomaticLock2::CVssAutomaticLock2(
      (CVssAutomaticLock2 *)v60,
      (struct CVssCriticalSection *)CVsSoftwareProvider::m_cs);
    *(_QWORD *)v63 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
    v64 = L"CVssDiffMgmt::QueryVolumesSupportedForDiffAreas";
    v65 = L"SPRDIFMC";
    v66 = 659;
    v67 = 2;
    v68 = 255;
    v70 = 0x1000000;
    memset_0(v69, 0, sizeof(v69));
    CVssFunctionTracer::AddOperation((struct CVssFunctionTracer *)&v51, (const struct CVssDebugInfo *)v63, 427);
    CVssClusterAPI::CVssClusterAPI((CVssClusterAPI *)v61);
    v36 = 0;
    v71[0] = 0;
    if ( a2 )
    {
      v39 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
      v40 = L"CVssDiffMgmt::QueryVolumesSupportedForDiffAreas";
      v41 = L"SPRDIFMC";
      v42 = 679;
      v43 = 2;
      v44 = 255;
      v46 = 0x1000000;
      memset_0(v45, 0, sizeof(v45));
      GetVolumeNameWithCheck((const struct CVssDebugInfo *)&v39, 0x80070057, a2, v71);
      v11 = CVssClusterAPI::Initialize((CVssClusterAPI *)v61, v10);
      memset_0(v63, 0, 0x62u);
      StringCchCopyW(v63, 0x31u, v71);
      v35 = 0;
      v12 = FveDetectVolume(v63, &v35);
      v52 = v12;
      v14 = v35;
      if ( v12 < 0 )
      {
        v39 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
        v40 = L"CVssDiffMgmt::QueryVolumesSupportedForDiffAreas";
        v41 = L"SPRDIFMC";
        v42 = 698;
        v43 = 2;
        v44 = 255;
        v46 = 0x1000000;
        memset_0(v45, 0, sizeof(v45));
        LODWORD(v33) = v12;
        CVssFunctionTracer::Trace(&v51, &v39, L"Error reading encryption status on volume %s (0x%08lx)", v63, v33);
      }
      v35 = 0;
      HasParentVolume = VssVolumeHasParentVolume(v71, &v35, v13);
      if ( HasParentVolume && !v35 )
        v36 = 1;
    }
    else
    {
      v11 = 0;
      HasParentVolume = 0;
      v14 = 0;
    }
    v16 = 0;
    if ( v11 )
      PhysicalDiskResourceForVolumeName = CVssClusterAPI::GetPhysicalDiskResourceForVolumeName(v61, v71, v9);
    v56 = -1;
    v57 = 1;
    while ( 1 )
    {
      if ( v36 )
      {
        v39 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
        v40 = L"CVssDiffMgmt::QueryVolumesSupportedForDiffAreas";
        v41 = L"SPRDIFMC";
        v42 = 725;
        v43 = 2;
        v44 = 255;
        v46 = 0x1000000;
        memset_0(v45, 0, sizeof(v45));
        CVssFunctionTracer::Trace(
          &v51,
          &v39,
          L"Volume %s is nested to deeply to support snapshots; no diff area volumes are available",
          v50);
LABEL_26:
        v39 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
        v40 = L"CVssDiffMgmt::QueryVolumesSupportedForDiffAreas";
        v41 = L"SPRDIFMC";
        v42 = 874;
        v43 = 2;
        v44 = 255;
        v46 = 0x1000000;
        memset_0(v45, 0, sizeof(v45));
        v52 = VssBuildEnumInterface<CVssMgmtEnumFromArray,IVssEnumMgmtObject,VSS_MGMT_OBJECT_PROP_Array>(
                (CVssDebugInfo *)&v39,
                v8,
                (__int64)v3);
        CVssVolumeIterator::~CVssVolumeIterator((HANDLE *)&v56);
        std::wstring::_Tidy_deallocate(v62);
        CVssAutomaticLock2::~CVssAutomaticLock2(v60);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v55);
        goto LABEL_77;
      }
      if ( !CVssVolumeIterator::SelectNewVolume(
              (CVssVolumeIterator *)&v56,
              (struct CVssFunctionTracer *)&v51,
              DirectoryName) )
        goto LABEL_26;
      v39 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
      v40 = L"CVssDiffMgmt::QueryVolumesSupportedForDiffAreas";
      v41 = L"SPRDIFMC";
      v42 = 738;
      v43 = 2;
      v44 = 255;
      v46 = 0x1000000;
      memset_0(v45, 0, sizeof(v45));
      GetVolumeNameWithCheck((const struct CVssDebugInfo *)&v39, 0x80042308, DirectoryName, v72);
      if ( !v11 && !v14 && !HasParentVolume )
        goto LABEL_40;
      v17 = v71;
      do
      {
        v18 = *(unsigned __int16 *)((char *)v17 + (char *)v72 - (char *)v71);
        v19 = *v17 - v18;
        if ( v19 )
          break;
        ++v17;
      }
      while ( v18 );
      v16 = v19 == 0;
      if ( v14 && v19 )
      {
        v39 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
        v40 = L"CVssDiffMgmt::QueryVolumesSupportedForDiffAreas";
        v41 = L"SPRDIFMC";
        v42 = 750;
        v43 = 2;
        v44 = 255;
        v16 = 0;
        v46 = 0x1000000;
        memset_0(v45, 0, sizeof(v45));
        CVssFunctionTracer::Trace(
          &v51,
          &v39,
          L"Volume %s is encrypted and cannot have diff area on volume %s ",
          v71,
          v72);
      }
      else if ( HasParentVolume && v19 )
      {
        v39 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
        v40 = L"CVssDiffMgmt::QueryVolumesSupportedForDiffAreas";
        v41 = L"SPRDIFMC";
        v42 = 758;
        v43 = 2;
        v44 = 255;
        v16 = 0;
        v46 = 0x1000000;
        memset_0(v45, 0, sizeof(v45));
        CVssFunctionTracer::Trace(&v51, &v39, L"Volume %s is nested and cannot have diff area on volume %s ", v71, v72);
      }
      else
      {
LABEL_40:
        VolumeInformationFlags = CVsSoftwareProvider::GetVolumeInformationFlags(DirectoryName, 29, 0, 0, 31);
        if ( (VolumeInformationFlags & 2) == 0 )
          goto LABEL_22;
        if ( v16 || (VolumeInformationFlags & 0x20) == 0 )
        {
          v22 = -1;
          do
            ++v22;
          while ( v71[v22] );
          if ( !v22 )
            goto LABEL_51;
          SectorSizeForVolume = CVssDiffMgmt::GetSectorSizeForVolume(0, DirectoryName);
          if ( SectorSizeForVolume <= (unsigned int)CVssDiffMgmt::GetSectorSizeForVolume(v24, v71) )
          {
            v3 = v47;
LABEL_51:
            if ( v16 || !VssVolumeHasParentVolume(v72, 0, (unsigned __int16 *)v21) )
            {
              if ( !v11 || v16 )
              {
LABEL_64:
                v16 = 0;
                goto LABEL_65;
              }
              v26 = CVssClusterAPI::GetPhysicalDiskResourceForVolumeName(v61, DirectoryName, v21);
              if ( PhysicalDiskResourceForVolumeName )
              {
                if ( !v26 || CVssClusterAPI::AreResourcesEqual(v25, PhysicalDiskResourceForVolumeName, v26) )
                {
LABEL_22:
                  v16 = 0;
                }
                else
                {
                  if ( CVssClusterAPI::IsDependencyAlreadyEstablished(v61, PhysicalDiskResourceForVolumeName, v26) )
                    goto LABEL_64;
                  CanEstablishDependency = CVssClusterAPI::CanEstablishDependency(
                                             v28,
                                             PhysicalDiskResourceForVolumeName,
                                             v26);
                  v16 = 0;
                  if ( CanEstablishDependency )
                  {
LABEL_65:
                    VssGetVolumeDisplayName(DirectoryName, v63, (DWORD)v21);
                    FreeBytesAvailableToCaller.QuadPart = 0;
                    TotalNumberOfBytes.QuadPart = 0;
                    TotalNumberOfFreeBytes.QuadPart = 0;
                    if ( !GetDiskFreeSpaceExW(
                            DirectoryName,
                            &FreeBytesAvailableToCaller,
                            &TotalNumberOfBytes,
                            &TotalNumberOfFreeBytes) )
                    {
                      LastError = GetLastError();
                      v39 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
                      v40 = L"CVssDiffMgmt::QueryVolumesSupportedForDiffAreas";
                      v41 = L"SPRDIFMC";
                      v42 = 843;
                      v43 = 2;
                      v44 = 255;
                      v46 = 0x1000000;
                      memset_0(v45, 0, sizeof(v45));
                      LODWORD(v34) = LastError;
                      CVssFunctionTracer::Trace(
                        &v51,
                        &v39,
                        L"Cannot get the free space for volume (%s) - [0x%08lx]",
                        DirectoryName,
                        v34);
                      goto LABEL_22;
                    }
                    v37 = 0;
                    VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsDiffVolume(
                      (VSS_MGMT_OBJECT_PROP_Ptr *)&v37,
                      (struct CVssFunctionTracer *)&v51,
                      DirectoryName,
                      v63,
                      FreeBytesAvailableToCaller.QuadPart,
                      TotalNumberOfBytes.QuadPart);
                    if ( !(unsigned int)ATL::CSimpleArray<VSS_MGMT_OBJECT_PROP_Ptr,ATL::CSimpleArrayEqualHelper<VSS_MGMT_OBJECT_PROP_Ptr>>::Add(
                                          v8 + 8,
                                          &v37) )
                    {
                      v39 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
                      v40 = L"CVssDiffMgmt::QueryVolumesSupportedForDiffAreas";
                      v41 = L"SPRDIFMC";
                      v42 = 865;
                      v43 = 2;
                      v44 = 255;
                      v46 = 0x1000000;
                      memset_0(v45, 0, sizeof(v45));
                      CVssFunctionTracer::Throw(
                        (CVssFunctionTracer *)&v51,
                        (const struct CVssDebugInfo *)&v39,
                        -2147024882,
                        L"Cannot add element to the array");
                    }
                    v37 = 0;
                    VSS_MGMT_OBJECT_PROP_Ptr::~VSS_MGMT_OBJECT_PROP_Ptr(&v37);
                  }
                }
              }
              else
              {
                v27 = v26 == 0;
                v16 = 0;
                if ( v27 )
                  goto LABEL_65;
              }
            }
            else
            {
              v39 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
              v40 = L"CVssDiffMgmt::QueryVolumesSupportedForDiffAreas";
              v41 = L"SPRDIFMC";
              v42 = 785;
              v43 = 2;
              v44 = 255;
              v16 = 0;
              v46 = 0x1000000;
              memset_0(v45, 0, sizeof(v45));
              CVssFunctionTracer::Trace(
                &v51,
                &v39,
                L"Volume %s is nested and cannot support diff area for another volume ",
                DirectoryName);
            }
          }
          else
          {
            v39 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
            v40 = L"CVssDiffMgmt::QueryVolumesSupportedForDiffAreas";
            v41 = L"SPRDIFMC";
            v42 = 778;
            v43 = 2;
            v44 = 255;
            v16 = 0;
            v46 = 0x1000000;
            memset_0(v45, 0, sizeof(v45));
            CVssFunctionTracer::Trace(
              &v51,
              &v39,
              L"Volume %s has a sector size greater than volume %s and cannot be used for diff area",
              DirectoryName,
              v71);
            v3 = v47;
          }
        }
        else
        {
          v39 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
          v40 = L"CVssDiffMgmt::QueryVolumesSupportedForDiffAreas";
          v41 = L"SPRDIFMC";
          v42 = 770;
          v43 = 2;
          v44 = 255;
          v16 = 0;
          v46 = 0x1000000;
          memset_0(v45, 0, sizeof(v45));
          CVssFunctionTracer::Trace(
            &v51,
            &v39,
            L"Volume %s is encrypted and cannot support diff area for another volume ",
            DirectoryName);
        }
      }
    }
  }
  catch ( long v54 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v51,
      v54,
      L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx",
      L"SPRDIFMC",
      L"CVssDiffMgmt::QueryVolumesSupportedForDiffAreas",
      0x36Cu,
      v53);
  }
  catch ( _com_error *v58 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v51,
      v58,
      L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx",
      L"SPRDIFMC",
      L"CVssDiffMgmt::QueryVolumesSupportedForDiffAreas",
      0x36Cu,
      v53);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v51,
      L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx",
      L"SPRDIFMC",
      L"CVssDiffMgmt::QueryVolumesSupportedForDiffAreas",
      0x36Cu,
      v53);
  }
  catch ( const std::exception *v59 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v51,
      v59,
      L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx",
      L"SPRDIFMC",
      L"CVssDiffMgmt::QueryVolumesSupportedForDiffAreas",
      0x36Cu,
      v53);
  }
LABEL_77:
  v31 = v52;
  CVssFunctionTracer::~CVssFunctionTracer(&v51);
  return v31;
}

```

## disassembly

```asm
0x18002d1f0  mov     r11, rsp
0x18002d1f3  mov     [r11+8], rbx
0x18002d1f7  mov     [r11+20h], rsi
0x18002d1fb  push    rdi
0x18002d1fc  push    r12
0x18002d1fe  push    r13
0x18002d200  push    r14
0x18002d202  push    r15
0x18002d204  sub     rsp, 710h
0x18002d20b  mov     rax, cs:__security_cookie
0x18002d212  xor     rax, rsp
0x18002d215  mov     [rsp+738h+var_38], rax
0x18002d21d  mov     rdi, r8
0x18002d220  mov     [rsp+738h+var_638], r8
0x18002d228  mov     rbx, rdx
0x18002d22b  mov     [rsp+738h+var_620], rdx
0x18002d233  lea     r12, aBaseStorVssMod_2; "base\\stor\\vss\\modules\\softprv\\src"...
0x18002d23a  mov     [r11-538h], r12
0x18002d241  lea     r13, aCvssdiffmgmtQu_3; "CVssDiffMgmt::QueryVolumesSupportedForD"...
0x18002d248  mov     [r11-530h], r13
0x18002d24f  lea     rsi, aSprdifmc; "SPRDIFMC"
0x18002d256  mov     [r11-528h], rsi
0x18002d25d  mov     [rsp+738h+var_520], 270h
0x18002d268  mov     r15d, 2
0x18002d26e  mov     [r11-51Ch], r15d
0x18002d275  mov     [rsp+738h+var_518], 0FFh
0x18002d280  xor     r14d, r14d
0x18002d283  mov     [rsp+738h+var_498], 1000000h
0x18002d28e  xor     edx, edx; Val
0x18002d290  lea     r8d, [r15+76h]; Size
0x18002d294  lea     rcx, [r11-510h]; void *
0x18002d29b  call    memset_0
0x18002d2a0  xor     r8d, r8d
0x18002d2a3  lea     rdx, [rsp+738h+var_538]
0x18002d2ab  lea     rcx, [rsp+738h+var_618]
0x18002d2b3  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18002d2b8  nop
0x18002d2b9  test    rdi, rdi
0x18002d2bc  jz      short loc_18002D2C1
0x18002d2be  mov     [rdi], r14
0x18002d2c1  call    ?IsInGroup@@YA_NK_N@Z; IsInGroup(ulong,bool)
0x18002d2c6  mov     qword ptr [rsp+738h+var_538], r12
0x18002d2ce  mov     [rsp+738h+var_530], r13
0x18002d2d6  mov     [rsp+738h+var_528], rsi
0x18002d2de  mov     [rsp+738h+var_51C], r15d
0x18002d2e6  mov     [rsp+738h+var_518], 0FFh
0x18002d2f1  mov     [rsp+738h+var_498], 1000000h
0x18002d2fc  xor     edx, edx; Val
0x18002d2fe  lea     r8d, [rdx+78h]; Size
0x18002d302  lea     rcx, [rsp+738h+var_510]; void *
0x18002d30a  test    al, al
0x18002d30c  jnz     short loc_18002D340
0x18002d30e  mov     [rsp+738h+var_520], 279h
0x18002d319  call    memset_0
0x18002d31e  lea     r9, aTheClientProce_0; "The client process is not running under"...
0x18002d325  mov     r8d, 80070005h
0x18002d32b  lea     rdx, [rsp+738h+var_538]
0x18002d333  lea     rcx, [rsp+738h+var_618]
0x18002d33b  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18002d340  mov     [rsp+738h+var_520], 27Dh
0x18002d34b  call    memset_0
0x18002d350  mov     [rsp+738h+var_718], rdi
0x18002d355  mov     r9, rbx
0x18002d358  lea     r8, aParametersPwsz_7; "Parameters: pwszOriginalVolumeName = %s"...
0x18002d35f  lea     rdx, [rsp+738h+var_538]
0x18002d367  lea     rcx, [rsp+738h+var_618]
0x18002d36f  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18002d374  test    rdi, rdi
0x18002d377  jnz     short loc_18002D3EF
0x18002d379  mov     qword ptr [rsp+738h+var_538], r12
0x18002d381  mov     [rsp+738h+var_530], r13
0x18002d389  mov     [rsp+738h+var_528], rsi
0x18002d391  mov     [rsp+738h+var_520], 283h
0x18002d39c  mov     [rsp+738h+var_51C], r15d
0x18002d3a4  mov     [rsp+738h+var_518], 0FFh
0x18002d3af  mov     [rsp+738h+var_498], 1000000h
0x18002d3ba  xor     edx, edx; Val
0x18002d3bc  lea     r8d, [rdi+78h]; Size
0x18002d3c0  lea     rcx, [rsp+738h+var_510]; void *
0x18002d3c8  call    memset_0
0x18002d3cd  lea     r9, aNullPpenum; "NULL ppEnum"
0x18002d3d4  mov     r8d, 80070057h
0x18002d3da  lea     rdx, [rsp+738h+var_538]
0x18002d3e2  lea     rcx, [rsp+738h+var_618]
0x18002d3ea  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18002d3ef  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002d3f6  mov     ecx, 20h ; ' '; unsigned __int64
0x18002d3fb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002d400  mov     rsi, rax
0x18002d403  mov     qword ptr [rsp+738h+TotalNumberOfFreeBytes], rax
0x18002d408  test    rax, rax
0x18002d40b  jz      short loc_18002D425
0x18002d40d  mov     [rax+8], r14
0x18002d411  mov     [rax+10h], r14
0x18002d415  mov     [rax+18h], r14d
0x18002d419  lea     rax, ??_7VSS_MGMT_OBJECT_PROP_Array@@6B@; const VSS_MGMT_OBJECT_PROP_Array::`vftable'
0x18002d420  mov     [rsi], rax
0x18002d423  jmp     short loc_18002D428
0x18002d425  mov     rsi, r14
0x18002d428  test    rsi, rsi
0x18002d42b  jnz     short loc_18002D4AB
0x18002d42d  mov     qword ptr [rsp+738h+var_538], r12
0x18002d435  mov     [rsp+738h+var_530], r13
0x18002d43d  lea     rax, aSprdifmc; "SPRDIFMC"
0x18002d444  mov     [rsp+738h+var_528], rax
0x18002d44c  mov     [rsp+738h+var_520], 288h
0x18002d457  mov     [rsp+738h+var_51C], r15d
0x18002d45f  mov     [rsp+738h+var_518], 0FFh
0x18002d46a  mov     [rsp+738h+var_498], 1000000h
0x18002d475  xor     edx, edx; Val
0x18002d477  lea     r8d, [rsi+78h]; Size
0x18002d47b  lea     rcx, [rsp+738h+var_510]; void *
0x18002d483  call    memset_0
0x18002d488  lea     r9, aMemoryAllocati_0; "Memory allocation error."
0x18002d48f  mov     r8d, 8007000Eh
0x18002d495  lea     rdx, [rsp+738h+var_538]
0x18002d49d  lea     rcx, [rsp+738h+var_618]
0x18002d4a5  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18002d4ab  mov     [rsp+738h+var_5A0], rsi
0x18002d4b3  mov     rax, [rsi]
0x18002d4b6  mov     rcx, rsi
0x18002d4b9  mov     rax, [rax+8]
0x18002d4bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d4c2  nop
0x18002d4c3  lea     rdx, ?m_cs@CVsSoftwareProvider@@0VCVssCriticalSection@@A; struct CVssCriticalSection *
0x18002d4ca  lea     rcx, [rsp+738h+var_578]; this
0x18002d4d2  call    ??0CVssAutomaticLock2@@QEAA@AEAVCVssCriticalSection@@@Z; CVssAutomaticLock2::CVssAutomaticLock2(CVssCriticalSection &)
0x18002d4d7  nop
0x18002d4d8  mov     qword ptr [rsp+738h+var_538], r12
0x18002d4e0  mov     [rsp+738h+var_530], r13
0x18002d4e8  lea     rax, aSprdifmc; "SPRDIFMC"
0x18002d4ef  mov     [rsp+738h+var_528], rax
0x18002d4f7  mov     [rsp+738h+var_520], 293h
0x18002d502  mov     [rsp+738h+var_51C], r15d
0x18002d50a  mov     [rsp+738h+var_518], 0FFh
0x18002d515  mov     [rsp+738h+var_498], 1000000h
0x18002d520  xor     edx, edx; Val
0x18002d522  lea     r8d, [rdx+78h]; Size
0x18002d526  lea     rcx, [rsp+738h+var_510]; void *
0x18002d52e  call    memset_0
0x18002d533  mov     r8d, 1ABh
0x18002d539  lea     rdx, [rsp+738h+var_538]
0x18002d541  lea     rcx, [rsp+738h+var_618]
0x18002d549  call    ?AddOperation@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IZZ; CVssFunctionTracer::AddOperation(CVssDebugInfo,uint,...)
0x18002d54e  lea     rcx, [rsp+738h+var_568]; this
0x18002d556  call    ??0CVssClusterAPI@@QEAA@XZ; CVssClusterAPI::CVssClusterAPI(void)
0x18002d55b  nop
0x18002d55c  mov     [rsp+738h+var_6F7], r14b
0x18002d561  mov     [rsp+738h+var_328], r14w
0x18002d56a  test    rbx, rbx
0x18002d56d  jz      loc_18002D6E8
0x18002d573  mov     [rsp+738h+var_6E0], r12
0x18002d578  mov     [rsp+738h+var_6D8], r13
0x18002d57d  lea     rax, aSprdifmc; "SPRDIFMC"
0x18002d584  mov     [rsp+738h+var_6D0], rax
0x18002d589  mov     [rsp+738h+var_6C8], 2A7h
0x18002d591  mov     [rsp+738h+var_6C4], r15d
0x18002d596  mov     [rsp+738h+var_6C0], 0FFh
0x18002d59e  mov     [rsp+738h+var_640], 1000000h
0x18002d5a9  xor     edx, edx; Val
0x18002d5ab  lea     r8d, [rdx+78h]; Size
0x18002d5af  lea     rcx, [rsp+738h+var_6B8]; void *
0x18002d5b7  call    memset_0
0x18002d5bc  lea     r9, [rsp+738h+var_328]
0x18002d5c4  mov     r8, rbx
0x18002d5c7  mov     edx, 80070057h
0x18002d5cc  lea     rcx, [rsp+738h+var_6E0]
0x18002d5d1  call    ?GetVolumeNameWithCheck@@YAXUCVssDebugInfo@@JPEBGPEAGK@Z; GetVolumeNameWithCheck(CVssDebugInfo,long,ushort const *,ushort *,ulong)
0x18002d5d6  lea     rcx, [rsp+738h+var_568]; this
0x18002d5de  call    ?Initialize@CVssClusterAPI@@QEAA_NPEBG@Z; CVssClusterAPI::Initialize(ushort const *)
0x18002d5e3  mov     r12b, al
0x18002d5e6  xor     edx, edx; Val
0x18002d5e8  lea     r8d, [rdx+62h]; Size
0x18002d5ec  lea     rcx, [rsp+738h+var_538]; void *
0x18002d5f4  call    memset_0
0x18002d5f9  lea     r8, [rsp+738h+var_328]; unsigned __int16 *
0x18002d601  mov     edx, 31h ; '1'; unsigned __int64
0x18002d606  lea     rcx, [rsp+738h+var_538]; unsigned __int16 *
0x18002d60e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002d613  mov     [rsp+738h+var_6F8], r14b
0x18002d618  lea     rdx, [rsp+738h+var_6F8]
0x18002d61d  lea     rcx, [rsp+738h+var_538]
0x18002d625  call    FveDetectVolume
0x18002d62a  mov     ebx, eax
0x18002d62c  mov     [rsp+738h+var_610], eax
0x18002d633  cmp     [rsp+738h+var_6F8], r14b
0x18002d638  setnz   r13b
0x18002d63c  test    eax, eax
0x18002d63e  jns     short loc_18002D6BC
0x18002d640  lea     rax, aBaseStorVssMod_2; "base\\stor\\vss\\modules\\softprv\\src"...
0x18002d647  mov     [rsp+738h+var_6E0], rax
0x18002d64c  lea     rax, aCvssdiffmgmtQu_3; "CVssDiffMgmt::QueryVolumesSupportedForD"...
0x18002d653  mov     [rsp+738h+var_6D8], rax
0x18002d658  lea     rax, aSprdifmc; "SPRDIFMC"
0x18002d65f  mov     [rsp+738h+var_6D0], rax
0x18002d664  mov     [rsp+738h+var_6C8], 2BAh
0x18002d66c  mov     [rsp+738h+var_6C4], r15d
0x18002d671  mov     [rsp+738h+var_6C0], 0FFh
0x18002d679  mov     [rsp+738h+var_640], 1000000h
0x18002d684  xor     edx, edx; Val
0x18002d686  lea     r8d, [rdx+78h]; Size
0x18002d68a  lea     rcx, [rsp+738h+var_6B8]; void *
0x18002d692  call    memset_0
0x18002d697  mov     dword ptr [rsp+738h+var_718], ebx
0x18002d69b  lea     r9, [rsp+738h+var_538]
0x18002d6a3  lea     r8, aErrorReadingEn_0; "Error reading encryption status on volu"...
0x18002d6aa  lea     rdx, [rsp+738h+var_6E0]
0x18002d6af  lea     rcx, [rsp+738h+var_618]
0x18002d6b7  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18002d6bc  mov     [rsp+738h+var_6F8], r14b
0x18002d6c1  lea     rdx, [rsp+738h+var_6F8]; bool *
0x18002d6c6  lea     rcx, [rsp+738h+var_328]; unsigned __int16 *
0x18002d6ce  call    ?VssVolumeHasParentVolume@@YA_NPEBGPEA_NPEAGH@Z; VssVolumeHasParentVolume(ushort const *,bool *,ushort *,int)
0x18002d6d3  mov     r15b, al
0x18002d6d6  test    al, al
0x18002d6d8  jz      short loc_18002D6F1
0x18002d6da  cmp     [rsp+738h+var_6F8], r14b
0x18002d6df  jnz     short loc_18002D6F1
0x18002d6e1  mov     [rsp+738h+var_6F7], 1
0x18002d6e6  jmp     short loc_18002D6F1
0x18002d6e8  mov     r12b, r14b
0x18002d6eb  mov     r15b, r14b
0x18002d6ee  mov     r13b, r14b
0x18002d6f1  xor     ebx, ebx
0x18002d6f3  test    r12b, r12b
0x18002d6f6  jz      short loc_18002D710
0x18002d6f8  lea     rdx, [rsp+738h+var_328]; unsigned __int16 *
0x18002d700  lea     rcx, [rsp+738h+var_568]; this
0x18002d708  call    ?GetPhysicalDiskResourceForVolumeName@CVssClusterAPI@@QEAAPEAU_HRESOURCE@@PEBGPEAPEAG@Z; CVssClusterAPI::GetPhysicalDiskResourceForVolumeName(ushort const *,ushort * *)
0x18002d70d  mov     r14, rax
0x18002d710  mov     [rsp+738h+var_598], 0FFFFFFFFFFFFFFFFh
0x18002d71c  mov     [rsp+738h+var_590], 1
0x18002d724  jmp     short loc_18002D728
0x18002d726  xor     ebx, ebx
0x18002d728  cmp     [rsp+738h+var_6F7], bl
0x18002d72c  jz      short loc_18002D7AB
0x18002d72e  lea     rax, aBaseStorVssMod_2; "base\\stor\\vss\\modules\\softprv\\src"...
0x18002d735  mov     [rsp+738h+var_6E0], rax
0x18002d73a  lea     rax, aCvssdiffmgmtQu_3; "CVssDiffMgmt::QueryVolumesSupportedForD"...
0x18002d741  mov     [rsp+738h+var_6D8], rax
0x18002d746  lea     rax, aSprdifmc; "SPRDIFMC"
0x18002d74d  mov     [rsp+738h+var_6D0], rax
0x18002d752  mov     [rsp+738h+var_6C8], 2D5h
0x18002d75a  mov     [rsp+738h+var_6C4], 2
0x18002d762  mov     [rsp+738h+var_6C0], 0FFh
0x18002d76a  mov     [rsp+738h+var_640], 1000000h
0x18002d775  xor     edx, edx; Val
0x18002d777  lea     r8d, [rdx+78h]; Size
0x18002d77b  lea     rcx, [rsp+738h+var_6B8]; void *
0x18002d783  call    memset_0
0x18002d788  mov     r9, [rsp+738h+var_620]
0x18002d790  lea     r8, aVolumeSIsNeste; "Volume %s is nested to deeply to suppor"...
0x18002d797  lea     rdx, [rsp+738h+var_6E0]
0x18002d79c  lea     rcx, [rsp+738h+var_618]
0x18002d7a4  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18002d7a9  jmp     short loc_18002D7D0
0x18002d7ab  lea     r8, [rsp+738h+DirectoryName]; unsigned __int16 *
0x18002d7b3  lea     rdx, [rsp+738h+var_618]; struct CVssFunctionTracer *
0x18002d7bb  lea     rcx, [rsp+738h+var_598]; this
0x18002d7c3  call    ?SelectNewVolume@CVssVolumeIterator@@QEAA_NAEAVCVssFunctionTracer@@PEAGH@Z; CVssVolumeIterator::SelectNewVolume(CVssFunctionTracer &,ushort *,int)
0x18002d7c8  test    al, al
0x18002d7ca  jnz     loc_18002D87E
0x18002d7d0  lea     rax, aBaseStorVssMod_2; "base\\stor\\vss\\modules\\softprv\\src"...
0x18002d7d7  mov     [rsp+738h+var_6E0], rax
0x18002d7dc  lea     rax, aCvssdiffmgmtQu_3; "CVssDiffMgmt::QueryVolumesSupportedForD"...
0x18002d7e3  mov     [rsp+738h+var_6D8], rax
0x18002d7e8  lea     rax, aSprdifmc; "SPRDIFMC"
0x18002d7ef  mov     [rsp+738h+var_6D0], rax
0x18002d7f4  mov     [rsp+738h+var_6C8], 36Ah
0x18002d7fc  mov     [rsp+738h+var_6C4], 2
0x18002d804  mov     [rsp+738h+var_6C0], 0FFh
0x18002d80c  mov     [rsp+738h+var_640], 1000000h
0x18002d817  xor     edx, edx; Val
0x18002d819  lea     r8d, [rdx+78h]; Size
0x18002d81d  lea     rcx, [rsp+738h+var_6B8]; void *
0x18002d825  call    memset_0
0x18002d82a  mov     r8, rdi
0x18002d82d  mov     rdx, rsi
0x18002d830  lea     rcx, [rsp+738h+var_6E0]; this
0x18002d835  call    ??$VssBuildEnumInterface@VCVssMgmtEnumFromArray@@UIVssEnumMgmtObject@@VVSS_MGMT_OBJECT_PROP_Array@@@@YAJUCVssDebugInfo@@PEAVVSS_MGMT_OBJECT_PROP_Array@@PEAPEAUIVssEnumMgmtObject@@@Z; VssBuildEnumInterface<CVssMgmtEnumFromArray,IVssEnumMgmtObject,VSS_MGMT_OBJECT_PROP_Array>(CVssDebugInfo,VSS_MGMT_OBJECT_PROP_Array *,IVssEnumMgmtObject * *)
0x18002d83a  mov     [rsp+738h+var_610], eax
0x18002d841  lea     rcx, [rsp+738h+var_598]; this
0x18002d849  call    ??1CVssVolumeIterator@@QEAA@XZ; CVssVolumeIterator::~CVssVolumeIterator(void)
0x18002d84e  nop
0x18002d84f  lea     rcx, [rsp+738h+var_558]
0x18002d857  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d85c  nop
0x18002d85d  lea     rcx, [rsp+738h+var_578]; this
0x18002d865  call    ??1CVssAutomaticLock2@@QEAA@XZ; CVssAutomaticLock2::~CVssAutomaticLock2(void)
0x18002d86a  nop
0x18002d86b  lea     rcx, [rsp+738h+var_5A0]
0x18002d873  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002d878  nop
0x18002d879  jmp     loc_18002DEAA
0x18002d87e  lea     rax, aBaseStorVssMod_2; "base\\stor\\vss\\modules\\softprv\\src"...
0x18002d885  mov     [rsp+738h+var_6E0], rax
0x18002d88a  lea     rax, aCvssdiffmgmtQu_3; "CVssDiffMgmt::QueryVolumesSupportedForD"...
0x18002d891  mov     [rsp+738h+var_6D8], rax
0x18002d896  lea     rax, aSprdifmc; "SPRDIFMC"
0x18002d89d  mov     [rsp+738h+var_6D0], rax
  ... truncated ...
```
