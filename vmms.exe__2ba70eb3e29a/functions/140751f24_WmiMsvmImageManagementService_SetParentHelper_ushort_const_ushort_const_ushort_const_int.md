# WmiMsvmImageManagementService::SetParentHelper(ushort const *,ushort const *,ushort const *,int)

- ea: `0x140751f24`
- end: `0x140752808`
- name: `?SetParentHelper@WmiMsvmImageManagementService@@AEAAJPEBG00H@Z`
- size: `2276`
- prototype: `__int64 __fastcall(WmiMsvmImageManagementService *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callers

- `0x14043df28`
- `0x140752810`

## callees

- `0x14001993c`
- `0x140022640`
- `0x14004fd60`
- `0x14007a9d8`
- `0x14011d300`
- `0x140159cac`
- `0x140166d1c`
- `0x14017a4fc`
- `0x1401a73b4`
- `0x1404828e0`
- `0x140486529`
- `0x140751f24`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1407524f2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1407524f2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140752540`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14075265e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140752540`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14075265e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140752550`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140752550`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14075236c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1407525b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1407526b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140752790`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1407527a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14075236c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1407525b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1407526b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140752790`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1407527a7`
- `ntdll!RtlIsDosDeviceName_U` at `0x14075206b`
- `ntdll!RtlIsDosDeviceName_U` at `0x14075208c`
- `ntdll!RtlIsDosDeviceName_U` at `0x1407520ad`
- `ntdll!RtlIsDosDeviceName_U` at `0x14075206b`
- `ntdll!RtlIsDosDeviceName_U` at `0x14075208c`
- `ntdll!RtlIsDosDeviceName_U` at `0x1407520ad`
- `VirtDisk!GetVirtualDiskInformation` at `0x140752321`
- `VirtDisk!GetVirtualDiskInformation` at `0x1407523ea`
- `VirtDisk!GetVirtualDiskInformation` at `0x140752433`
- `VirtDisk!GetVirtualDiskInformation` at `0x1407524ad`
- `VirtDisk!GetVirtualDiskInformation` at `0x140752521`
- `VirtDisk!GetVirtualDiskInformation` at `0x140752583`
- `VirtDisk!GetVirtualDiskInformation` at `0x140752623`
- `VirtDisk!GetVirtualDiskInformation` at `0x140752321`
- `VirtDisk!GetVirtualDiskInformation` at `0x1407523ea`
- `VirtDisk!GetVirtualDiskInformation` at `0x140752433`
- `VirtDisk!GetVirtualDiskInformation` at `0x1407524ad`
- `VirtDisk!GetVirtualDiskInformation` at `0x140752521`
- `VirtDisk!GetVirtualDiskInformation` at `0x140752583`
- `VirtDisk!GetVirtualDiskInformation` at `0x140752623`
- `VirtDisk!OpenVirtualDisk` at `0x1407522e2`
- `VirtDisk!OpenVirtualDisk` at `0x1407523bd`
- `VirtDisk!OpenVirtualDisk` at `0x140752473`
- `VirtDisk!OpenVirtualDisk` at `0x1407525ef`
- `VirtDisk!OpenVirtualDisk` at `0x140752701`
- `VirtDisk!OpenVirtualDisk` at `0x1407522e2`
- `VirtDisk!OpenVirtualDisk` at `0x1407523bd`
- `VirtDisk!OpenVirtualDisk` at `0x140752473`
- `VirtDisk!OpenVirtualDisk` at `0x1407525ef`
- `VirtDisk!OpenVirtualDisk` at `0x140752701`
- `VirtDisk!SetVirtualDiskInformation` at `0x140752746`
- `VirtDisk!SetVirtualDiskInformation` at `0x140752746`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WmiMsvmImageManagementService::SetParentHelper(
        WmiMsvmImageManagementService *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  const unsigned __int16 *v7; // rbx
  const WCHAR *v8; // rcx
  const WCHAR *v9; // rcx
  const WCHAR *v10; // rcx
  const unsigned __int16 *v11; // rcx
  PCWSTR v12; // rax
  signed int v13; // ebx
  const unsigned __int16 *v14; // rcx
  const unsigned __int16 *v15; // rcx
  PCWSTR v16; // rax
  struct _EVENT_DESCRIPTOR *v17; // rcx
  PCWSTR *v18; // rax
  unsigned __int64 v19; // rdx
  PCWSTR v20; // r8
  PCWSTR v21; // rax
  unsigned int v22; // esi
  const unsigned __int16 *v23; // rcx
  const WCHAR *v24; // rdx
  signed int v25; // eax
  signed int VirtualDiskInformation; // eax
  const struct _GUID *v27; // r8
  const unsigned __int16 *v28; // r9
  bool v29; // cc
  const struct _EVENT_DESCRIPTOR *v30; // rcx
  PCWSTR *v31; // rcx
  const WCHAR *v32; // rdx
  const WCHAR *v33; // rdx
  struct _GET_VIRTUAL_DISK_INFO *p_VirtualDiskInfo; // rdi
  ULONG v35; // r14d
  PCWSTR *v36; // rdx
  PCWSTR *v37; // rcx
  struct _GET_VIRTUAL_DISK_INFO *v38; // rax
  const WCHAR *v39; // rdx
  signed int v40; // eax
  bool v41; // cc
  const struct _GUID *v42; // r8
  const unsigned __int16 *v43; // r9
  const WCHAR *v44; // rdx
  const WCHAR *v45; // rax
  __int64 v47; // [rsp+30h] [rbp-D0h] BYREF
  int v48; // [rsp+38h] [rbp-C8h] BYREF
  int v49; // [rsp+3Ch] [rbp-C4h] BYREF
  __int64 v50; // [rsp+40h] [rbp-C0h] BYREF
  int v51; // [rsp+48h] [rbp-B8h] BYREF
  ULONG VirtualDiskInfoSize; // [rsp+4Ch] [rbp-B4h] BYREF
  HANDLE VirtualDiskHandle; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-A8h] BYREF
  struct _SET_VIRTUAL_DISK_INFO v55; // [rsp+60h] [rbp-A0h] BYREF
  PCWSTR Name[2]; // [rsp+80h] [rbp-80h] BYREF
  __m128i si128; // [rsp+90h] [rbp-70h]
  PCWSTR Path[2]; // [rsp+A0h] [rbp-60h] BYREF
  __m128i v59; // [rsp+B0h] [rbp-50h]
  PCWSTR v60[2]; // [rsp+C0h] [rbp-40h] BYREF
  __m128i v61; // [rsp+D0h] [rbp-30h]
  struct _VIRTUAL_STORAGE_TYPE VirtualStorageType; // [rsp+E0h] [rbp-20h] BYREF
  struct _GET_VIRTUAL_DISK_INFO VirtualDiskInfo; // [rsp+F8h] [rbp-8h] BYREF
  PCWSTR v64[2]; // [rsp+118h] [rbp+18h] BYREF
  __m128i v65; // [rsp+128h] [rbp+28h]
  struct _OPEN_VIRTUAL_DISK_PARAMETERS Parameters; // [rsp+138h] [rbp+38h] BYREF
  struct _GET_VIRTUAL_DISK_INFO Buf1; // [rsp+168h] [rbp+68h] BYREF

  v7 = a2;
  *(_OWORD *)Name = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Name[0]) = 0;
  *(_OWORD *)Path = 0;
  v59 = si128;
  LOWORD(Path[0]) = 0;
  *(_OWORD *)v60 = 0;
  v61 = si128;
  LOWORD(v60[0]) = 0;
  *(_OWORD *)v64 = 0;
  v65 = si128;
  LOWORD(v64[0]) = 0;
  memset(&Parameters, 0, sizeof(Parameters));
  memset(&VirtualDiskInfo, 0, sizeof(VirtualDiskInfo));
  memset(&Buf1, 0, sizeof(Buf1));
  memset(&v55, 0, sizeof(v55));
  memset(&VirtualStorageType, 0, sizeof(VirtualStorageType));
  VirtualDiskHandle = (HANDLE)-1LL;
  hObject = (HANDLE)-1LL;
  v51 = 0;
  v48 = 0;
  v49 = 0;
  LODWORD(v47) = 0;
  LODWORD(v50) = 0;
  VirtualDiskInfoSize = 32;
  if ( a4 )
    a2 = a4;
  std::wstring::assign(Name, a2);
  ExpandEnvironmentVariables((LPCWSTR)Name);
  std::wstring::assign(Path, v7);
  ExpandEnvironmentVariables((LPCWSTR)Path);
  std::wstring::assign(v60, a3);
  ExpandEnvironmentVariables((LPCWSTR)v60);
  v8 = (const WCHAR *)Name;
  if ( si128.m128i_i64[1] > 7uLL )
    v8 = Name[0];
  if ( RtlIsDosDeviceName_U(v8) )
    goto LABEL_124;
  v9 = (const WCHAR *)Path;
  if ( v59.m128i_i64[1] > 7uLL )
    v9 = Path[0];
  if ( RtlIsDosDeviceName_U(v9) )
    goto LABEL_124;
  v10 = (const WCHAR *)v60;
  if ( v61.m128i_i64[1] > 7uLL )
    v10 = v60[0];
  if ( RtlIsDosDeviceName_U(v10) )
  {
LABEL_124:
    v13 = -2147024809;
LABEL_125:
    if ( VirtualDiskHandle != (HANDLE)-1LL )
      CloseHandle(VirtualDiskHandle);
    goto LABEL_127;
  }
  v11 = (const unsigned __int16 *)Path;
  if ( v59.m128i_i64[1] > 7uLL )
    v11 = Path[0];
  if ( !(unsigned int)GetVhdExtensionInfo(v11, (enum _VHD_FORMAT *)&v51, (int *)&v47, 0, 0) )
  {
    v12 = (PCWSTR)Path;
    if ( v59.m128i_i64[1] > 7uLL )
      v12 = Path[0];
LABEL_17:
    v13 = -2147024809;
    v47 = (__int64)v12;
    VmEventWriteAndReport<unsigned short const * &>(
      (struct _EVENT_DESCRIPTOR *)&MSVHDSVC_INVALID_FILE_EXTENSION,
      5u,
      (__int64)&v47);
    goto LABEL_125;
  }
  v14 = (const unsigned __int16 *)v60;
  if ( v61.m128i_i64[1] > 7uLL )
    v14 = v60[0];
  if ( !(unsigned int)GetVhdExtensionInfo(v14, (enum _VHD_FORMAT *)&v48, (int *)&v50, 0, 0) )
  {
    v12 = (PCWSTR)v60;
    if ( v61.m128i_i64[1] > 7uLL )
      v12 = v60[0];
    goto LABEL_17;
  }
  v15 = (const unsigned __int16 *)Name;
  if ( si128.m128i_i64[1] > 7uLL )
    v15 = Name[0];
  if ( !(unsigned int)GetVhdExtensionInfo(v15, (enum _VHD_FORMAT *)&v49, 0, 0, 0) )
  {
    v12 = (PCWSTR)Name;
    if ( si128.m128i_i64[1] > 7uLL )
      v12 = Name[0];
    goto LABEL_17;
  }
  if ( v51 != v48 || (_DWORD)v50 && !(_DWORD)v47 )
  {
    v16 = (PCWSTR)v60;
    if ( v61.m128i_i64[1] > 7uLL )
      v16 = v60[0];
    v17 = (struct _EVENT_DESCRIPTOR *)MSVHDSVC_INVALID_FILE_EXTENSION_MISMATCH_PARENT;
    goto LABEL_37;
  }
  if ( v51 != v49 )
  {
    v16 = (PCWSTR)Name;
    if ( si128.m128i_i64[1] > 7uLL )
      v16 = Name[0];
    v17 = (struct _EVENT_DESCRIPTOR *)&MSVHDSVC_INVALID_FILE_EXTENSION_MISMATCH_LEAF;
LABEL_37:
    v47 = (__int64)v16;
    v18 = Path;
    if ( v59.m128i_i64[1] > 7uLL )
      v18 = (PCWSTR *)Path[0];
    v50 = (__int64)v18;
    v13 = -2147024809;
    VmEventWriteAndReport<unsigned short const *,unsigned short const * &>(v17, 5u, (__int64)&v50, (__int64)&v47);
    goto LABEL_125;
  }
  v19 = si128.m128i_u64[1];
  v20 = Name[0];
  if ( v51 == 4 )
  {
    v21 = (PCWSTR)Path;
    if ( v59.m128i_i64[1] > 7uLL )
      v21 = Path[0];
  }
  else if ( v48 == 4 )
  {
    v21 = (PCWSTR)v60;
    if ( v61.m128i_i64[1] > 7uLL )
      v21 = v60[0];
  }
  else
  {
    if ( v49 != 4 )
      goto LABEL_53;
    v21 = (PCWSTR)Name;
    if ( si128.m128i_i64[1] > 7uLL )
      v21 = Name[0];
  }
  v47 = (__int64)v21;
  if ( v21 )
  {
    v13 = -2147024809;
    VmEventWriteAndReport<unsigned short const * &>(
      (struct _EVENT_DESCRIPTOR *)&MSSTOR_VHDSET_UNSUPPORTED_DIFFERENCING_DISK,
      5u,
      (__int64)&v47);
    goto LABEL_125;
  }
LABEL_53:
  VirtualStorageType.VendorId = VIRTUAL_STORAGE_TYPE_VENDOR_MICROSOFT;
  Parameters.Version = OPEN_VIRTUAL_DISK_VERSION_2;
  v22 = 1;
  Parameters.Version1.RWDepth = 1;
  if ( a4 )
  {
    v23 = (const unsigned __int16 *)Path;
    if ( v59.m128i_i64[1] > 7uLL )
      v23 = Path[0];
    VirtualStorageType.DeviceId = GetVhdDeviceIDFromExtension(v23);
    v24 = (const WCHAR *)Path;
    if ( v59.m128i_i64[1] > 7uLL )
      v24 = Path[0];
    v25 = OpenVirtualDisk(
            &VirtualStorageType,
            v24,
            VIRTUAL_DISK_ACCESS_NONE,
            OPEN_VIRTUAL_DISK_FLAG_NO_PARENTS,
            &Parameters,
            &VirtualDiskHandle);
    v13 = v25;
    if ( VirtualDiskHandle == (HANDLE)-1LL )
      goto LABEL_59;
    VirtualDiskInfo.Version = GET_VIRTUAL_DISK_INFO_PROVIDER_SUBTYPE;
    VirtualDiskInformation = GetVirtualDiskInformation(VirtualDiskHandle, &VirtualDiskInfoSize, &VirtualDiskInfo, 0);
    v13 = VirtualDiskInformation;
    v29 = VirtualDiskInformation <= 0;
    if ( VirtualDiskInformation )
    {
LABEL_62:
      if ( !v29 )
        v13 = (unsigned __int16)VirtualDiskInformation | 0x80070000;
      goto LABEL_125;
    }
    if ( VirtualDiskInfo.Identifier.Data1 != 4 )
    {
      v30 = &MSVHDSVC_SET_PARENT_CHILD_NOT_DIFFERENCING_FAILURE;
LABEL_66:
      v13 = -2147024809;
      VmEventWriteAndReport(v30, 5u, v27, v28);
      goto LABEL_125;
    }
    CloseHandle(VirtualDiskHandle);
    v19 = si128.m128i_u64[1];
    v20 = Name[0];
  }
  v31 = Name;
  if ( v19 > 7 )
    v31 = (PCWSTR *)v20;
  VirtualStorageType.DeviceId = GetVhdDeviceIDFromExtension((const unsigned __int16 *)v31);
  v32 = (const WCHAR *)Name;
  if ( si128.m128i_i64[1] > 7uLL )
    v32 = Name[0];
  v25 = OpenVirtualDisk(
          &VirtualStorageType,
          v32,
          VIRTUAL_DISK_ACCESS_NONE,
          OPEN_VIRTUAL_DISK_FLAG_NO_PARENTS,
          &Parameters,
          &VirtualDiskHandle);
  v13 = v25;
  if ( VirtualDiskHandle != (HANDLE)-1LL )
  {
    VirtualDiskInfo.Version = GET_VIRTUAL_DISK_INFO_PROVIDER_SUBTYPE;
    VirtualDiskInformation = GetVirtualDiskInformation(VirtualDiskHandle, &VirtualDiskInfoSize, &VirtualDiskInfo, 0);
    v13 = VirtualDiskInformation;
    v29 = VirtualDiskInformation <= 0;
    if ( VirtualDiskInformation )
      goto LABEL_62;
    if ( VirtualDiskInfo.Identifier.Data1 == 4 )
    {
      VirtualDiskInfo.Version = GET_VIRTUAL_DISK_INFO_PARENT_IDENTIFIER;
      VirtualDiskInformation = GetVirtualDiskInformation(VirtualDiskHandle, &VirtualDiskInfoSize, &VirtualDiskInfo, 0);
      v13 = VirtualDiskInformation;
      v29 = VirtualDiskInformation <= 0;
      if ( !VirtualDiskInformation )
      {
        v33 = (const WCHAR *)v60;
        if ( v61.m128i_i64[1] > 7uLL )
          v33 = v60[0];
        VirtualDiskInformation = OpenVirtualDisk(
                                   &VirtualStorageType,
                                   v33,
                                   VIRTUAL_DISK_ACCESS_NONE,
                                   OPEN_VIRTUAL_DISK_FLAG_NO_PARENTS,
                                   &Parameters,
                                   &hObject);
        v13 = VirtualDiskInformation;
        if ( hObject == (HANDLE)-1LL )
        {
          v29 = VirtualDiskInformation <= 0;
        }
        else
        {
          VirtualDiskInfoSize = 32;
          Buf1.Version = GET_VIRTUAL_DISK_INFO_IDENTIFIER;
          VirtualDiskInformation = GetVirtualDiskInformation(hObject, &VirtualDiskInfoSize, &Buf1, 0);
          v13 = VirtualDiskInformation;
          v29 = VirtualDiskInformation <= 0;
          if ( !VirtualDiskInformation )
          {
            p_VirtualDiskInfo = &VirtualDiskInfo;
            v35 = 32;
            std::wstring::operator=(v64, Name);
            while ( 1 )
            {
              v36 = Path;
              if ( v59.m128i_i64[1] > 7uLL )
                v36 = (PCWSTR *)Path[0];
              v37 = v64;
              if ( v65.m128i_i64[1] > 7uLL )
                v37 = (PCWSTR *)v64[0];
              if ( !(unsigned int)_o__wcsicmp(v37, v36) )
              {
                if ( !a5 && memcmp_0(&Buf1.Size, &VirtualDiskInfo.Size, 0x10u) )
                {
                  v13 = -1069940722;
                  VmEventWriteAndReport(&MSVHDSVC_SET_PARENT_ID_MISMATCH_FAILURE, 5u, v42, v43);
                  goto LABEL_105;
                }
                CloseHandle(VirtualDiskHandle);
                VirtualDiskHandle = (HANDLE)-1LL;
                Parameters.Version1.RWDepth = 0;
                v44 = (const WCHAR *)Name;
                if ( si128.m128i_i64[1] > 7uLL )
                  v44 = Name[0];
                v40 = OpenVirtualDisk(
                        &VirtualStorageType,
                        v44,
                        VIRTUAL_DISK_ACCESS_NONE,
                        (OPEN_VIRTUAL_DISK_FLAG)(a4 == 0),
                        &Parameters,
                        &VirtualDiskHandle);
                v13 = v40;
                if ( VirtualDiskHandle == (HANDLE)-1LL )
                {
LABEL_107:
                  v41 = v40 <= 0;
LABEL_102:
                  if ( v41 )
                    goto LABEL_105;
                }
                else
                {
                  v13 = 0;
                  v55.Version = SET_VIRTUAL_DISK_INFO_PARENT_PATH_WITH_DEPTH;
                  v55.UniqueIdentifier.Data1 = v22;
                  v45 = (const WCHAR *)v60;
                  if ( v61.m128i_i64[1] > 7uLL )
                    v45 = v60[0];
                  v55.ParentPathWithDepthInfo.ParentFilePath = v45;
                  v40 = SetVirtualDiskInformation(VirtualDiskHandle, &v55);
                  if ( !v40 )
                    goto LABEL_105;
                  if ( v40 <= 0 )
                  {
                    v13 = v40;
                    goto LABEL_105;
                  }
                }
                v13 = (unsigned __int16)v40;
LABEL_104:
                v13 |= 0x80070000;
                goto LABEL_105;
              }
              p_VirtualDiskInfo->Version = GET_VIRTUAL_DISK_INFO_PARENT_LOCATION;
              VirtualDiskInfoSize = v35;
              v13 = GetVirtualDiskInformation(VirtualDiskHandle, &VirtualDiskInfoSize, p_VirtualDiskInfo, 0);
              if ( v13 == 122 )
              {
                if ( p_VirtualDiskInfo != &VirtualDiskInfo )
                  free(p_VirtualDiskInfo);
                v38 = (struct _GET_VIRTUAL_DISK_INFO *)malloc(VirtualDiskInfoSize);
                p_VirtualDiskInfo = v38;
                if ( !v38 )
                {
                  v13 = -2147024882;
                  goto LABEL_105;
                }
                v35 = VirtualDiskInfoSize;
                v38->Version = GET_VIRTUAL_DISK_INFO_PARENT_LOCATION;
                v13 = GetVirtualDiskInformation(VirtualDiskHandle, &VirtualDiskInfoSize, v38, 0);
              }
              if ( v13 )
                break;
              std::wstring::assign(v64, &p_VirtualDiskInfo->ParentIdentifier.Data2);
              ExpandEnvironmentVariables((LPCWSTR)v64);
              CloseHandle(VirtualDiskHandle);
              v39 = (const WCHAR *)v64;
              if ( v65.m128i_i64[1] > 7uLL )
                v39 = v64[0];
              v40 = OpenVirtualDisk(
                      &VirtualStorageType,
                      v39,
                      VIRTUAL_DISK_ACCESS_NONE,
                      OPEN_VIRTUAL_DISK_FLAG_NO_PARENTS,
                      &Parameters,
                      &VirtualDiskHandle);
              v13 = v40;
              if ( VirtualDiskHandle == (HANDLE)-1LL )
                goto LABEL_107;
              VirtualDiskInfo.Version = GET_VIRTUAL_DISK_INFO_PARENT_IDENTIFIER;
              VirtualDiskInfoSize = 32;
              v40 = GetVirtualDiskInformation(VirtualDiskHandle, &VirtualDiskInfoSize, &VirtualDiskInfo, 0);
              v13 = v40;
              v41 = v40 <= 0;
              if ( v40 )
                goto LABEL_102;
              ++v22;
            }
            if ( v13 > 0 )
            {
              v13 = (unsigned __int16)v13;
              goto LABEL_104;
            }
LABEL_105:
            if ( p_VirtualDiskInfo != &VirtualDiskInfo )
              free(p_VirtualDiskInfo);
            goto LABEL_125;
          }
        }
      }
      goto LABEL_62;
    }
    v30 = &MSVHDSVC_SET_PARENT_CHILD_NOT_DIFFERENCING_FAILURE;
    if ( a4 )
      v30 = (const struct _EVENT_DESCRIPTOR *)MSVHDSVC_SET_PARENT_LEAF_NOT_DIFFERENCING_FAILURE;
    goto LABEL_66;
  }
LABEL_59:
  if ( v25 > 0 )
    v13 = (unsigned __int16)v25 | 0x80070000;
LABEL_127:
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  std::wstring::_Tidy_deallocate(v64);
  std::wstring::_Tidy_deallocate(v60);
  std::wstring::_Tidy_deallocate(Path);
  std::wstring::_Tidy_deallocate(Name);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140751f24  mov     [rsp-8+arg_0], rbx
0x140751f29  push    rbp
0x140751f2a  push    rsi
0x140751f2b  push    rdi
0x140751f2c  push    r12
0x140751f2e  push    r13
0x140751f30  push    r14
0x140751f32  push    r15
0x140751f34  lea     rbp, [rsp-90h]
0x140751f3c  sub     rsp, 190h
0x140751f43  mov     rax, cs:__security_cookie
0x140751f4a  xor     rax, rsp
0x140751f4d  mov     [rbp+0C0h+var_38], rax
0x140751f54  mov     r15, r9
0x140751f57  mov     rdi, r8
0x140751f5a  mov     rbx, rdx
0x140751f5d  xorps   xmm0, xmm0
0x140751f60  movups  xmmword ptr [rbp+0C0h+Name], xmm0
0x140751f64  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140751f6c  movdqu  [rbp+0C0h+var_130], xmm1
0x140751f71  xor     r12d, r12d
0x140751f74  mov     word ptr [rbp+0C0h+Name], r12w
0x140751f79  movups  xmmword ptr [rbp+0C0h+Path], xmm0
0x140751f7d  movdqu  [rbp+0C0h+var_110], xmm1
0x140751f82  mov     word ptr [rbp+0C0h+Path], r12w
0x140751f87  movups  xmmword ptr [rbp+0C0h+var_100], xmm0
0x140751f8b  movdqu  [rbp+0C0h+var_F0], xmm1
0x140751f90  mov     word ptr [rbp+0C0h+var_100], r12w
0x140751f95  movups  xmmword ptr [rbp+0C0h+var_A8], xmm0
0x140751f99  movdqu  [rbp+0C0h+var_98], xmm1
0x140751f9e  mov     word ptr [rbp+0C0h+var_A8], r12w
0x140751fa3  xor     eax, eax
0x140751fa5  movups  xmmword ptr [rbp+0C0h+var_88.Version], xmm0
0x140751fa9  movups  xmmword ptr [rbp+0C0h+var_88.4+0Ch], xmm0
0x140751fad  movups  xmmword ptr [rbp+0C0h+var_88.4+18h], xmm0
0x140751fb1  movups  xmmword ptr [rbp+0C0h+VirtualDiskInfo.Version], xmm0
0x140751fb5  movups  xmmword ptr [rbp+0C0h+VirtualDiskInfo.8+8], xmm0
0x140751fb9  xorps   xmm1, xmm1
0x140751fbc  movups  xmmword ptr [rbp+0C0h+Buf1.Version], xmm1
0x140751fc0  movups  xmmword ptr [rbp+0C0h+Buf1.8+8], xmm1
0x140751fc4  movups  xmmword ptr [rsp+1C0h+var_160.Version], xmm0
0x140751fc9  movups  xmmword ptr [rsp+1C0h+var_160.8+8], xmm0
0x140751fce  movups  xmmword ptr [rbp+0C0h+VirtualStorageType.DeviceId], xmm1
0x140751fd2  mov     dword ptr [rbp+0C0h+VirtualStorageType.VendorId.Data4+4], eax
0x140751fd5  mov     [rsp+1C0h+VirtualDiskHandle], 0FFFFFFFFFFFFFFFFh
0x140751fde  mov     [rsp+1C0h+hObject], 0FFFFFFFFFFFFFFFFh
0x140751fe7  mov     [rsp+1C0h+var_178], r12d
0x140751fec  mov     [rsp+1C0h+var_188], r12d
0x140751ff1  mov     [rsp+1C0h+var_184], r12d
0x140751ff6  mov     dword ptr [rsp+1C0h+var_190], r12d
0x140751ffb  mov     dword ptr [rsp+1C0h+var_180], r12d
0x140752000  mov     [rsp+1C0h+VirtualDiskInfoSize], 20h ; ' '
0x140752008  lea     rcx, [rbp+0C0h+Name]
0x14075200c  test    r9, r9
0x14075200f  jz      short loc_140752014
0x140752011  mov     rdx, r9
0x140752014  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x140752019  lea     rdx, [rbp+0C0h+Name]
0x14075201d  lea     rcx, [rbp+0C0h+Name]; lpSrc
0x140752021  call    ?ExpandEnvironmentVariables@@YAEAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@K@Z; ExpandEnvironmentVariables(std::wstring const &,std::wstring &,ulong)
0x140752026  mov     rdx, rbx
0x140752029  lea     rcx, [rbp+0C0h+Path]
0x14075202d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x140752032  lea     rdx, [rbp+0C0h+Path]
0x140752036  lea     rcx, [rbp+0C0h+Path]; lpSrc
0x14075203a  call    ?ExpandEnvironmentVariables@@YAEAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@K@Z; ExpandEnvironmentVariables(std::wstring const &,std::wstring &,ulong)
0x14075203f  mov     rdx, rdi
0x140752042  lea     rcx, [rbp+0C0h+var_100]
0x140752046  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x14075204b  lea     rdx, [rbp+0C0h+var_100]
0x14075204f  lea     rcx, [rbp+0C0h+var_100]; lpSrc
0x140752053  call    ?ExpandEnvironmentVariables@@YAEAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@K@Z; ExpandEnvironmentVariables(std::wstring const &,std::wstring &,ulong)
0x140752058  lea     rcx, [rbp+0C0h+Name]
0x14075205c  mov     r13d, 7
0x140752062  cmp     qword ptr [rbp+0C0h+var_130+8], r13
0x140752066  cmova   rcx, [rbp+0C0h+Name]; Name
0x14075206b  call    cs:__imp_RtlIsDosDeviceName_U
0x140752072  nop     dword ptr [rax+rax+00h]
0x140752077  test    eax, eax
0x140752079  jnz     loc_140752780
0x14075207f  lea     rcx, [rbp+0C0h+Path]
0x140752083  cmp     qword ptr [rbp+0C0h+var_110+8], r13
0x140752087  cmova   rcx, [rbp+0C0h+Path]; Name
0x14075208c  call    cs:__imp_RtlIsDosDeviceName_U
0x140752093  nop     dword ptr [rax+rax+00h]
0x140752098  test    eax, eax
0x14075209a  jnz     loc_140752780
0x1407520a0  lea     rcx, [rbp+0C0h+var_100]
0x1407520a4  cmp     qword ptr [rbp+0C0h+var_F0+8], r13
0x1407520a8  cmova   rcx, [rbp+0C0h+var_100]; Name
0x1407520ad  call    cs:__imp_RtlIsDosDeviceName_U
0x1407520b4  nop     dword ptr [rax+rax+00h]
0x1407520b9  test    eax, eax
0x1407520bb  jnz     loc_140752780
0x1407520c1  lea     rcx, [rbp+0C0h+Path]
0x1407520c5  cmp     qword ptr [rbp+0C0h+var_110+8], r13
0x1407520c9  cmova   rcx, [rbp+0C0h+Path]; unsigned __int16 *
0x1407520ce  mov     [rsp+1C0h+Parameters], r12; int *
0x1407520d3  xor     r9d, r9d; unsigned int *
0x1407520d6  lea     r8, [rsp+1C0h+var_190]; int *
0x1407520db  lea     rdx, [rsp+1C0h+var_178]; enum _VHD_FORMAT *
0x1407520e0  call    ?GetVhdExtensionInfo@@YAHPEBGPEAW4_VHD_FORMAT@@PEAHPEAK2@Z; GetVhdExtensionInfo(ushort const *,_VHD_FORMAT *,int *,ulong *,int *)
0x1407520e5  test    eax, eax
0x1407520e7  jnz     short loc_140752120
0x1407520e9  lea     rax, [rbp+0C0h+Path]
0x1407520ed  cmp     qword ptr [rbp+0C0h+var_110+8], r13
0x1407520f1  cmova   rax, [rbp+0C0h+Path]
0x1407520f6  mov     ebx, 80070057h
0x1407520fb  mov     [rsp+1C0h+var_190], rax
0x140752100  lea     rax, [rsp+1C0h+var_190]
0x140752105  mov     [rsp+1C0h+Parameters], rax; __int64
0x14075210a  mov     edx, 5; unsigned int
0x14075210f  lea     rcx, MSVHDSVC_INVALID_FILE_EXTENSION; struct _EVENT_DESCRIPTOR *
0x140752116  call    ??$VmEventWriteAndReport@AEAPEBG@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@PEBGAEAPEBG@Z; VmEventWriteAndReport<ushort const * &>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const *,ushort const * &)
0x14075211b  jmp     loc_140752785
0x140752120  lea     rcx, [rbp+0C0h+var_100]
0x140752124  cmp     qword ptr [rbp+0C0h+var_F0+8], r13
0x140752128  cmova   rcx, [rbp+0C0h+var_100]; unsigned __int16 *
0x14075212d  mov     [rsp+1C0h+Parameters], r12; int *
0x140752132  xor     r9d, r9d; unsigned int *
0x140752135  lea     r8, [rsp+1C0h+var_180]; int *
0x14075213a  lea     rdx, [rsp+1C0h+var_188]; enum _VHD_FORMAT *
0x14075213f  call    ?GetVhdExtensionInfo@@YAHPEBGPEAW4_VHD_FORMAT@@PEAHPEAK2@Z; GetVhdExtensionInfo(ushort const *,_VHD_FORMAT *,int *,ulong *,int *)
0x140752144  test    eax, eax
0x140752146  jnz     short loc_140752157
0x140752148  lea     rax, [rbp+0C0h+var_100]
0x14075214c  cmp     qword ptr [rbp+0C0h+var_F0+8], r13
0x140752150  cmova   rax, [rbp+0C0h+var_100]
0x140752155  jmp     short loc_1407520F6
0x140752157  lea     rcx, [rbp+0C0h+Name]
0x14075215b  cmp     qword ptr [rbp+0C0h+var_130+8], r13
0x14075215f  cmova   rcx, [rbp+0C0h+Name]; unsigned __int16 *
0x140752164  mov     [rsp+1C0h+Parameters], r12; int *
0x140752169  xor     r9d, r9d; unsigned int *
0x14075216c  xor     r8d, r8d; int *
0x14075216f  lea     rdx, [rsp+1C0h+var_184]; enum _VHD_FORMAT *
0x140752174  call    ?GetVhdExtensionInfo@@YAHPEBGPEAW4_VHD_FORMAT@@PEAHPEAK2@Z; GetVhdExtensionInfo(ushort const *,_VHD_FORMAT *,int *,ulong *,int *)
0x140752179  test    eax, eax
0x14075217b  jnz     short loc_14075218F
0x14075217d  lea     rax, [rbp+0C0h+Name]
0x140752181  cmp     qword ptr [rbp+0C0h+var_130+8], r13
0x140752185  cmova   rax, [rbp+0C0h+Name]
0x14075218a  jmp     loc_1407520F6
0x14075218f  mov     eax, [rsp+1C0h+var_178]
0x140752193  cmp     eax, [rsp+1C0h+var_188]
0x140752197  jnz     loc_140752767
0x14075219d  cmp     dword ptr [rsp+1C0h+var_180], r12d
0x1407521a2  jz      short loc_1407521AF
0x1407521a4  cmp     dword ptr [rsp+1C0h+var_190], r12d
0x1407521a9  jz      loc_140752767
0x1407521af  cmp     eax, [rsp+1C0h+var_184]
0x1407521b3  jz      short loc_140752208
0x1407521b5  lea     rax, [rbp+0C0h+Name]
0x1407521b9  cmp     qword ptr [rbp+0C0h+var_130+8], r13
0x1407521bd  cmova   rax, [rbp+0C0h+Name]
0x1407521c2  lea     rcx, MSVHDSVC_INVALID_FILE_EXTENSION_MISMATCH_LEAF; struct _EVENT_DESCRIPTOR *
0x1407521c9  mov     [rsp+1C0h+var_190], rax
0x1407521ce  lea     rax, [rbp+0C0h+Path]
0x1407521d2  cmp     qword ptr [rbp+0C0h+var_110+8], r13
0x1407521d6  cmova   rax, [rbp+0C0h+Path]
0x1407521db  mov     [rsp+1C0h+var_180], rax
0x1407521e0  lea     rax, [rsp+1C0h+var_190]
0x1407521e5  mov     [rsp+1C0h+Handle], rax; __int64
0x1407521ea  lea     rax, [rsp+1C0h+var_180]
0x1407521ef  mov     edx, 5; unsigned int
0x1407521f4  mov     [rsp+1C0h+Parameters], rax; __int64
0x1407521f9  mov     ebx, 80070057h
0x1407521fe  call    ??$VmEventWriteAndReport@PEBGAEAPEBG@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@PEBG$$QEAPEBGAEAPEBG@Z; VmEventWriteAndReport<ushort const *,ushort const * &>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const *,ushort const * &&,ushort const * &)
0x140752203  jmp     loc_140752785
0x140752208  mov     rdx, qword ptr [rbp+0C0h+var_130+8]
0x14075220c  mov     r8, [rbp+0C0h+Name]
0x140752210  mov     edi, 4
0x140752215  cmp     eax, edi
0x140752217  jnz     short loc_140752228
0x140752219  lea     rax, [rbp+0C0h+Path]
0x14075221d  cmp     qword ptr [rbp+0C0h+var_110+8], r13
0x140752221  cmova   rax, [rbp+0C0h+Path]
0x140752226  jmp     short loc_14075224E
0x140752228  cmp     [rsp+1C0h+var_188], edi
0x14075222c  jnz     short loc_14075223D
0x14075222e  lea     rax, [rbp+0C0h+var_100]
0x140752232  cmp     qword ptr [rbp+0C0h+var_F0+8], r13
0x140752236  cmova   rax, [rbp+0C0h+var_100]
0x14075223b  jmp     short loc_14075224E
0x14075223d  cmp     [rsp+1C0h+var_184], edi
0x140752241  jnz     short loc_14075227D
0x140752243  lea     rax, [rbp+0C0h+Name]
0x140752247  cmp     rdx, r13
0x14075224a  cmova   rax, r8
0x14075224e  mov     [rsp+1C0h+var_190], rax
0x140752253  test    rax, rax
0x140752256  jz      short loc_14075227D
0x140752258  mov     ebx, 80070057h
0x14075225d  lea     rax, [rsp+1C0h+var_190]
0x140752262  mov     [rsp+1C0h+Parameters], rax; __int64
0x140752267  mov     edx, 5; unsigned int
0x14075226c  lea     rcx, MSSTOR_VHDSET_UNSUPPORTED_DIFFERENCING_DISK; struct _EVENT_DESCRIPTOR *
0x140752273  call    ??$VmEventWriteAndReport@AEAPEBG@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@PEBGAEAPEBG@Z; VmEventWriteAndReport<ushort const * &>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const *,ushort const * &)
0x140752278  jmp     loc_140752785
0x14075227d  movups  xmm0, xmmword ptr cs:VIRTUAL_STORAGE_TYPE_VENDOR_MICROSOFT.Data1
0x140752284  movdqu  xmmword ptr [rbp+0C0h+VirtualStorageType.VendorId.Data1], xmm0
0x140752289  mov     r14d, 2
0x14075228f  mov     [rbp+0C0h+var_88.Version], r14d
0x140752293  lea     esi, [r14-1]
0x140752297  mov     dword ptr [rbp+0C0h+var_88.4], esi
0x14075229a  test    r15, r15
0x14075229d  jz      loc_140752380
0x1407522a3  lea     rcx, [rbp+0C0h+Path]
0x1407522a7  cmp     qword ptr [rbp+0C0h+var_110+8], r13
0x1407522ab  cmova   rcx, [rbp+0C0h+Path]; unsigned __int16 *
0x1407522b0  call    ?GetVhdDeviceIDFromExtension@@YAKPEBG@Z; GetVhdDeviceIDFromExtension(ushort const *)
0x1407522b5  mov     [rbp+0C0h+VirtualStorageType.DeviceId], eax
0x1407522b8  lea     rdx, [rbp+0C0h+Path]
0x1407522bc  cmp     qword ptr [rbp+0C0h+var_110+8], r13
0x1407522c0  cmova   rdx, [rbp+0C0h+Path]; Path
0x1407522c5  lea     rax, [rsp+1C0h+VirtualDiskHandle]
0x1407522ca  mov     [rsp+1C0h+Handle], rax; Handle
0x1407522cf  lea     rax, [rbp+0C0h+var_88]
0x1407522d3  mov     [rsp+1C0h+Parameters], rax; Parameters
0x1407522d8  mov     r9d, esi; Flags
0x1407522db  xor     r8d, r8d; VirtualDiskAccessMask
0x1407522de  lea     rcx, [rbp+0C0h+VirtualStorageType]; VirtualStorageType
0x1407522e2  call    cs:__imp_OpenVirtualDisk
0x1407522e9  nop     dword ptr [rax+rax+00h]
0x1407522ee  mov     ebx, eax
0x1407522f0  mov     rcx, [rsp+1C0h+VirtualDiskHandle]; VirtualDiskHandle
0x1407522f5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1407522f9  jnz     short loc_140752311
0x1407522fb  test    eax, eax
0x1407522fd  jle     loc_14075279C
0x140752303  movzx   ebx, ax
0x140752306  or      ebx, 80070000h
0x14075230c  jmp     loc_14075279C
0x140752311  mov     [rbp+0C0h+VirtualDiskInfo.Version], r13d
0x140752315  xor     r9d, r9d; SizeUsed
0x140752318  lea     r8, [rbp+0C0h+VirtualDiskInfo]; VirtualDiskInfo
0x14075231c  lea     rdx, [rsp+1C0h+VirtualDiskInfoSize]; VirtualDiskInfoSize
0x140752321  call    cs:__imp_GetVirtualDiskInformation
0x140752328  nop     dword ptr [rax+rax+00h]
0x14075232d  mov     ebx, eax
0x14075232f  test    eax, eax
0x140752331  jz      short loc_140752347
0x140752333  jle     loc_140752785
0x140752339  movzx   ebx, ax
0x14075233c  or      ebx, 80070000h
0x140752342  jmp     loc_140752785
0x140752347  cmp     dword ptr [rbp+0C0h+VirtualDiskInfo.8], edi
0x14075234a  jz      short loc_140752367
0x14075234c  lea     rcx, MSVHDSVC_SET_PARENT_CHILD_NOT_DIFFERENCING_FAILURE; struct _EVENT_DESCRIPTOR *
0x140752353  mov     edx, 5; unsigned int
0x140752358  mov     ebx, 80070057h
0x14075235d  call    ?VmEventWriteAndReport@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@PEBG@Z; VmEventWriteAndReport(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const *)
0x140752362  jmp     loc_140752785
0x140752367  mov     rcx, [rsp+1C0h+VirtualDiskHandle]; hObject
0x14075236c  call    cs:__imp_CloseHandle
0x140752373  nop     dword ptr [rax+rax+00h]
0x140752378  mov     rdx, qword ptr [rbp+0C0h+var_130+8]
0x14075237c  mov     r8, [rbp+0C0h+Name]
0x140752380  lea     rcx, [rbp+0C0h+Name]
0x140752384  cmp     rdx, r13
0x140752387  cmova   rcx, r8; unsigned __int16 *
0x14075238b  call    ?GetVhdDeviceIDFromExtension@@YAKPEBG@Z; GetVhdDeviceIDFromExtension(ushort const *)
0x140752390  mov     [rbp+0C0h+VirtualStorageType.DeviceId], eax
0x140752393  lea     rdx, [rbp+0C0h+Name]
0x140752397  cmp     qword ptr [rbp+0C0h+var_130+8], r13
0x14075239b  cmova   rdx, [rbp+0C0h+Name]; Path
0x1407523a0  lea     rax, [rsp+1C0h+VirtualDiskHandle]
0x1407523a5  mov     [rsp+1C0h+Handle], rax; Handle
0x1407523aa  lea     rax, [rbp+0C0h+var_88]
0x1407523ae  mov     [rsp+1C0h+Parameters], rax; Parameters
0x1407523b3  mov     r9d, esi; Flags
0x1407523b6  xor     r8d, r8d; VirtualDiskAccessMask
0x1407523b9  lea     rcx, [rbp+0C0h+VirtualStorageType]; VirtualStorageType
0x1407523bd  call    cs:__imp_OpenVirtualDisk
0x1407523c4  nop     dword ptr [rax+rax+00h]
0x1407523c9  mov     ebx, eax
0x1407523cb  mov     rcx, [rsp+1C0h+VirtualDiskHandle]; VirtualDiskHandle
0x1407523d0  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1407523d4  jz      loc_1407522FB
0x1407523da  mov     [rbp+0C0h+VirtualDiskInfo.Version], r13d
0x1407523de  xor     r9d, r9d; SizeUsed
0x1407523e1  lea     r8, [rbp+0C0h+VirtualDiskInfo]; VirtualDiskInfo
0x1407523e5  lea     rdx, [rsp+1C0h+VirtualDiskInfoSize]; VirtualDiskInfoSize
0x1407523ea  call    cs:__imp_GetVirtualDiskInformation
0x1407523f1  nop     dword ptr [rax+rax+00h]
0x1407523f6  mov     ebx, eax
0x1407523f8  test    eax, eax
0x1407523fa  jnz     loc_140752333
0x140752400  cmp     dword ptr [rbp+0C0h+VirtualDiskInfo.8], edi
0x140752403  jz      short loc_14075241F
0x140752405  lea     rax, MSVHDSVC_SET_PARENT_LEAF_NOT_DIFFERENCING_FAILURE
0x14075240c  lea     rcx, MSVHDSVC_SET_PARENT_CHILD_NOT_DIFFERENCING_FAILURE
0x140752413  test    r15, r15
0x140752416  cmovnz  rcx, rax
0x14075241a  jmp     loc_140752353
0x14075241f  mov     [rbp+0C0h+VirtualDiskInfo.Version], edi
0x140752422  xor     r9d, r9d; SizeUsed
0x140752425  lea     r8, [rbp+0C0h+VirtualDiskInfo]; VirtualDiskInfo
0x140752429  lea     rdx, [rsp+1C0h+VirtualDiskInfoSize]; VirtualDiskInfoSize
0x14075242e  mov     rcx, [rsp+1C0h+VirtualDiskHandle]; VirtualDiskHandle
  ... truncated ...
```
