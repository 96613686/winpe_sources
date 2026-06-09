# GetReservedSize(ushort *,ulong,unsigned __int64 &)

- ea: `0x18001a7c4`
- end: `0x18001ad79`
- name: `?GetReservedSize@@YAJPEAGKAEA_K@Z`
- size: `1461`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, reparse_path, installer_update`

## callers

- `0x180025420`
- `0x18002c080`

## callees

- `0x18000d030`
- `0x18000d450`
- `0x18000ddb0`
- `0x180012ce0`
- `0x1800199f0`
- `0x180019c44`
- `0x18001a2ac`
- `0x18001a7c4`
- `0x18001bef8`
- `0x18007318c`
- `0x18007342c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18001a904`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18001a904`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a979`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a9a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a9b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a9a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a9b0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001aa85`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001aa85`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18001a96f`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18001a96f`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18001a91c`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18001a91c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001aa3f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001aada`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001aa3f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001aada`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18001a8b4`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18001a8b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetReservedSize(unsigned __int16 *a1, int a2, unsigned __int64 *a3)
{
  __int64 v6; // r12
  __int64 FileW; // r13
  unsigned int v8; // r14d
  signed int i; // ebx
  union _LARGE_INTEGER *v10; // r8
  signed int DiskLayoutInternal; // ebx
  signed int LastError; // eax
  __int64 v14; // rax
  unsigned __int64 v15; // rcx
  HANDLE v16; // rax
  unsigned int *v17; // r8
  struct _DISK_GEOMETRY_EX *v18; // rdi
  __int64 v19; // rsi
  int v20; // eax
  unsigned __int64 v21; // rcx
  __int64 v22; // rdx
  bool v23; // zf
  LONGLONG v24; // rax
  LONGLONG v25; // rax
  LONGLONG v26; // rax
  LONGLONG v27; // rax
  LONGLONG v28; // rax
  LONGLONG v29; // rax
  LONGLONG v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  LONGLONG v35; // rax
  LONGLONG v36; // rax
  __int64 v37; // rax
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  struct _DISK_GEOMETRY_EX *v39; // [rsp+48h] [rbp-B8h] BYREF
  union _LARGE_INTEGER v40; // [rsp+50h] [rbp-B0h] BYREF
  _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v42; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v43; // [rsp+70h] [rbp-90h]
  _BYTE v44[16]; // [rsp+78h] [rbp-88h] BYREF
  _OWORD OutBuffer[2]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR RootPathName[4]; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR szVolumeName[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR VolumeNameBuffer[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  WCHAR szVolumeMountPoint[264]; // [rsp+4D0h] [rbp+3D0h] BYREF
  WCHAR FileName[264]; // [rsp+6E0h] [rbp+5E0h] BYREF

  v6 = -1;
  v43 = -1;
  FileW = -1;
  memset(OutBuffer, 0, sizeof(OutBuffer));
  v8 = 0;
  v39 = 0;
  v42 = 0;
  std::_Tree<std::_Tmap_traits<enum _STORAGE_RESERVE_ID,unsigned __int64,std::less<enum _STORAGE_RESERVE_ID>,std::allocator<std::pair<enum _STORAGE_RESERVE_ID const,unsigned __int64>>,0>>::_Alloc_sentinel_and_proxy(&v42);
  *a3 = 0;
  if ( a2 )
  {
    wcscpy(RootPathName, L"A:\\");
    memset_0(VolumeNameBuffer, 0, 0x208u);
    TotalNumberOfBytes.QuadPart = 0;
    v40.QuadPart = 0;
    for ( i = 0; i < 26; ++i )
    {
      if ( _bittest(&a2, i) )
      {
        RootPathName[0] = i + 65;
        if ( GetVolumeInformationW(RootPathName, VolumeNameBuffer, 0x104u, 0, 0, 0, 0, 0) )
        {
          if ( (int)GetDiskNumberAndExtent(RootPathName, 0, v10, &v40) >= 0 )
          {
            *(_DWORD *)(*(_QWORD *)std::map<__int64,int>::_Try_emplace<__int64 const &,>(&v42, v44, &v40) + 40LL) = 1;
            if ( (unsigned int)_o__wcsnicmp(VolumeNameBuffer, L"DATA", 260) )
            {
              if ( GetDiskFreeSpaceExW(RootPathName, 0, &TotalNumberOfBytes, 0) )
                *a3 += TotalNumberOfBytes.QuadPart;
            }
          }
        }
      }
    }
    v6 = v43;
  }
  DiskLayoutInternal = StringCchPrintfW(szVolumeMountPoint, 0x104u, L"%ws\\", a1);
  if ( DiskLayoutInternal >= 0 )
  {
    if ( !GetVolumeNameForVolumeMountPointW(szVolumeMountPoint, szVolumeName, 0x104u) )
      goto LABEL_13;
    v14 = -1;
    do
      ++v14;
    while ( szVolumeName[v14] );
    v15 = 2 * v14 - 2;
    if ( v15 >= 0x208 )
      _report_rangecheckfailure();
    *(WCHAR *)((char *)szVolumeName + v15) = 0;
    FileW = (__int64)CreateFileW(szVolumeName, 0x80000000, 3u, 0, 3u, 0x80u, 0);
    if ( FileW == -1 )
      goto LABEL_13;
    BytesReturned = 0;
    if ( !DeviceIoControl((HANDLE)FileW, 0x560000u, 0, 0, OutBuffer, 0x20u, &BytesReturned, 0) )
      goto LABEL_13;
    DiskLayoutInternal = StringCchPrintfW(FileName, 0x104u, L"\\\\.\\PhysicalDrive%u", DWORD2(OutBuffer[0]));
    if ( DiskLayoutInternal < 0 )
      goto LABEL_15;
    v16 = CreateFileW(FileName, 0x80000000, 3u, 0, 3u, 0x80u, 0);
    v6 = (__int64)v16;
    if ( v16 == (HANDLE)-1LL )
    {
LABEL_13:
      LastError = GetLastError();
      DiskLayoutInternal = LastError;
      if ( LastError > 0 )
        DiskLayoutInternal = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      DiskLayoutInternal = GetDiskLayoutInternal(v16, (struct _DRIVE_LAYOUT_INFORMATION_EX **)&v39, v17);
      if ( DiskLayoutInternal >= 0 )
      {
        v18 = v39;
        if ( v39->Geometry.Cylinders.HighPart )
        {
          do
          {
            v19 = 144LL * v8;
            if ( !*(LONGLONG *)((char *)&v18[1].DiskSize.QuadPart + v19)
              || *(_DWORD *)(*(_QWORD *)std::map<__int64,int>::_Try_emplace<__int64 const &,>(
                                          &v42,
                                          v44,
                                          (char *)&v18[1].Geometry.SectorsPerTrack + v19)
                           + 40LL) == 1 )
            {
              goto LABEL_80;
            }
            v20 = *(MEDIA_TYPE *)((char *)&v18[1].Geometry.MediaType + v19);
            if ( v20 )
            {
              if ( v20 != 1 )
                goto LABEL_80;
              v24 = *(LONGLONG *)((char *)&v18[2].Geometry.Cylinders.QuadPart + v19)
                  - *(_QWORD *)&PARTITION_BSP_GUID.Data1;
              if ( !v24 )
                v24 = *(_QWORD *)((char *)&v18[2].Geometry.MediaType + v19) - *(_QWORD *)PARTITION_BSP_GUID.Data4;
              if ( v24 )
              {
                v25 = *(LONGLONG *)((char *)&v18[2].Geometry.Cylinders.QuadPart + v19)
                    - *(_QWORD *)&PARTITION_DPP_GUID.Data1;
                if ( !v25 )
                  v25 = *(_QWORD *)((char *)&v18[2].Geometry.MediaType + v19) - *(_QWORD *)PARTITION_DPP_GUID.Data4;
                if ( v25 )
                {
                  v26 = *(LONGLONG *)((char *)&v18[2].Geometry.Cylinders.QuadPart + v19)
                      - *(_QWORD *)&PARTITION_BASIC_DATA_GUID.Data1;
                  if ( !v26 )
                    v26 = *(_QWORD *)((char *)&v18[2].Geometry.MediaType + v19)
                        - *(_QWORD *)PARTITION_BASIC_DATA_GUID.Data4;
                  if ( v26 )
                  {
                    v27 = *(LONGLONG *)((char *)&v18[2].Geometry.Cylinders.QuadPart + v19)
                        - *(_QWORD *)&PARTITION_MAIN_OS_GUID.Data1;
                    if ( !v27 )
                      v27 = *(_QWORD *)((char *)&v18[2].Geometry.MediaType + v19)
                          - *(_QWORD *)PARTITION_MAIN_OS_GUID.Data4;
                    if ( v27 )
                    {
                      v28 = *(LONGLONG *)((char *)&v18[2].Geometry.Cylinders.QuadPart + v19)
                          - *(_QWORD *)&PARTITION_MSFT_RECOVERY_GUID.Data1;
                      if ( !v28 )
                        v28 = *(_QWORD *)((char *)&v18[2].Geometry.MediaType + v19)
                            - *(_QWORD *)PARTITION_MSFT_RECOVERY_GUID.Data4;
                      if ( v28 )
                      {
                        v29 = *(LONGLONG *)((char *)&v18[2].Geometry.Cylinders.QuadPart + v19)
                            - *(_QWORD *)&PARTITION_OS_DATA_GUID.Data1;
                        if ( !v29 )
                          v29 = *(_QWORD *)((char *)&v18[2].Geometry.MediaType + v19)
                              - *(_QWORD *)PARTITION_OS_DATA_GUID.Data4;
                        if ( v29 )
                        {
                          v30 = *(LONGLONG *)((char *)&v18[2].Geometry.Cylinders.QuadPart + v19)
                              - *(_QWORD *)&PARTITION_PRE_INSTALLED_GUID.Data1;
                          if ( !v30 )
                            v30 = *(_QWORD *)((char *)&v18[2].Geometry.MediaType + v19)
                                - *(_QWORD *)PARTITION_PRE_INSTALLED_GUID.Data4;
                          if ( v30 )
                          {
                            v31 = *(LONGLONG *)((char *)&v18[2].Geometry.Cylinders.QuadPart + v19)
                                - PARTITION_SERVICING_FILES_GUID;
                            if ( !v31 )
                              v31 = *(_QWORD *)((char *)&v18[2].Geometry.MediaType + v19) - 0x6A00C0A9EA8D4CAELL;
                            if ( v31 )
                            {
                              v32 = *(LONGLONG *)((char *)&v18[2].Geometry.Cylinders.QuadPart + v19)
                                  - PARTITION_SERVICING_METADATA_GUID;
                              if ( !v32 )
                                v32 = *(_QWORD *)((char *)&v18[2].Geometry.MediaType + v19) + 0x31D62D50C28FB145LL;
                              if ( v32 )
                              {
                                v33 = *(LONGLONG *)((char *)&v18[2].Geometry.Cylinders.QuadPart + v19)
                                    - PARTITION_SERVICING_RESERVE_GUID;
                                if ( !v33 )
                                  v33 = *(_QWORD *)((char *)&v18[2].Geometry.MediaType + v19) - 0x146D13FEB6FF19A3LL;
                                if ( v33 )
                                {
                                  v34 = *(LONGLONG *)((char *)&v18[2].Geometry.Cylinders.QuadPart + v19)
                                      - PARTITION_SERVICING_STAGING_ROOT_GUID;
                                  if ( !v34 )
                                    v34 = *(_QWORD *)((char *)&v18[2].Geometry.MediaType + v19) + 0x2046FB4244130C56LL;
                                  if ( v34 )
                                  {
                                    v35 = *(LONGLONG *)((char *)&v18[2].Geometry.Cylinders.QuadPart + v19)
                                        - *(_QWORD *)&PARTITION_WINDOWS_SYSTEM_GUID.Data1;
                                    if ( !v35 )
                                      v35 = *(_QWORD *)((char *)&v18[2].Geometry.MediaType + v19)
                                          - *(_QWORD *)PARTITION_WINDOWS_SYSTEM_GUID.Data4;
                                    if ( v35 )
                                    {
                                      v36 = *(LONGLONG *)((char *)&v18[2].Geometry.Cylinders.QuadPart + v19)
                                          - *(_QWORD *)&PARTITION_LDM_DATA_GUID.Data1;
                                      if ( !v36 )
                                        v36 = *(_QWORD *)((char *)&v18[2].Geometry.MediaType + v19)
                                            - *(_QWORD *)PARTITION_LDM_DATA_GUID.Data4;
                                      if ( v36 )
                                        goto LABEL_79;
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
              v37 = *(_QWORD *)&v18[2].Data[v19];
              if ( v37 < 0 )
              {
LABEL_79:
                *a3 += *(LONGLONG *)((char *)&v18[1].DiskSize.QuadPart + v19);
                goto LABEL_80;
              }
              v23 = (v37 & 0x7000000000000000LL) == 0;
            }
            else
            {
              v21 = *((unsigned __int8 *)&v18[2].Geometry.Cylinders.LowPart + v19);
              if ( (_BYTE)v21 == 66 )
                goto LABEL_80;
              if ( (unsigned __int8)v21 <= 0x2Du )
              {
                v22 = 0x3F800000D8F2LL;
                if ( _bittest64(&v22, v21) )
                  goto LABEL_80;
              }
              v23 = (_BYTE)v21 == 0xEF;
            }
            if ( !v23 )
              goto LABEL_79;
LABEL_80:
            ++v8;
          }
          while ( v8 < v18->Geometry.Cylinders.HighPart );
        }
      }
    }
  }
LABEL_15:
  SafeFreeDiskGeometry(&v39);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  if ( v6 != -1 )
    CloseHandle((HANDLE)v6);
  std::_Tree<std::_Tmap_traits<int,DiskInfo *,std::less<int>,std::allocator<std::pair<int const,DiskInfo *>>,0>>::~_Tree<std::_Tmap_traits<int,DiskInfo *,std::less<int>,std::allocator<std::pair<int const,DiskInfo *>>,0>>(&v42);
  return (unsigned int)DiskLayoutInternal;
}

```

## disassembly

```asm
0x18001a7c4  mov     [rsp-8+arg_8], rbx
0x18001a7c9  push    rbp
0x18001a7ca  push    rsi
0x18001a7cb  push    rdi
0x18001a7cc  push    r12
0x18001a7ce  push    r13
0x18001a7d0  push    r14
0x18001a7d2  push    r15
0x18001a7d4  lea     rbp, [rsp-800h]
0x18001a7dc  sub     rsp, 900h
0x18001a7e3  mov     rax, cs:__security_cookie
0x18001a7ea  xor     rax, rsp
0x18001a7ed  mov     [rbp+830h+var_40], rax
0x18001a7f4  mov     r15, r8
0x18001a7f7  mov     edi, edx
0x18001a7f9  mov     rsi, rcx
0x18001a7fc  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a800  mov     r12, rax
0x18001a803  mov     [rsp+930h+var_8C0], rax
0x18001a808  mov     r13, rax
0x18001a80b  xorps   xmm0, xmm0
0x18001a80e  movups  [rbp+830h+OutBuffer], xmm0
0x18001a812  movups  [rbp+830h+var_898], xmm0
0x18001a816  xor     r14d, r14d
0x18001a819  mov     [rsp+930h+var_8E8], r14
0x18001a81e  movdqu  [rsp+930h+var_8D0], xmm0
0x18001a824  lea     rcx, [rsp+930h+var_8D0]
0x18001a829  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@W4_STORAGE_RESERVE_ID@@_KU?$less@W4_STORAGE_RESERVE_ID@@@std@@V?$allocator@U?$pair@$$CBW4_STORAGE_RESERVE_ID@@_K@std@@@3@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<_STORAGE_RESERVE_ID,unsigned __int64,std::less<_STORAGE_RESERVE_ID>,std::allocator<std::pair<_STORAGE_RESERVE_ID const,unsigned __int64>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18001a82e  nop
0x18001a82f  mov     [r15], r14
0x18001a832  test    edi, edi
0x18001a834  jz      loc_18001A93E
0x18001a83a  lea     eax, [r13+42h]
0x18001a83e  mov     [rbp+830h+RootPathName], ax
0x18001a842  mov     eax, dword ptr cs:aA+2; ":\\"
0x18001a848  mov     [rbp+830h+var_886], eax
0x18001a84b  movzx   eax, word ptr cs:aA+6; ""
0x18001a852  mov     [rbp+830h+var_882], ax
0x18001a856  xor     edx, edx; Val
0x18001a858  mov     r8d, 208h; Size
0x18001a85e  lea     rcx, [rbp+830h+VolumeNameBuffer]; void *
0x18001a865  call    memset_0
0x18001a86a  mov     qword ptr [rsp+930h+TotalNumberOfBytes], r14
0x18001a86f  mov     qword ptr [rsp+930h+var_8E0], r14
0x18001a874  mov     ebx, r14d
0x18001a877  lea     r12d, [r13+42h]
0x18001a87b  bt      edi, ebx
0x18001a87e  jnb     loc_18001A92E
0x18001a884  lea     eax, [r12+rbx]
0x18001a888  mov     [rbp+830h+RootPathName], ax
0x18001a88c  mov     [rsp+930h+nFileSystemNameSize], r14d; nFileSystemNameSize
0x18001a891  mov     [rsp+930h+lpFileSystemNameBuffer], r14; lpFileSystemNameBuffer
0x18001a896  mov     [rsp+930h+lpFileSystemFlags], r14; lpFileSystemFlags
0x18001a89b  mov     [rsp+930h+lpMaximumComponentLength], r14; lpMaximumComponentLength
0x18001a8a0  xor     r9d, r9d; lpVolumeSerialNumber
0x18001a8a3  mov     r8d, 104h; nVolumeNameSize
0x18001a8a9  lea     rdx, [rbp+830h+VolumeNameBuffer]; lpVolumeNameBuffer
0x18001a8b0  lea     rcx, [rbp+830h+RootPathName]; lpRootPathName
0x18001a8b4  call    cs:__imp_GetVolumeInformationW
0x18001a8ba  test    eax, eax
0x18001a8bc  jz      short loc_18001A92E
0x18001a8be  lea     r9, [rsp+930h+var_8E0]; union _LARGE_INTEGER *
0x18001a8c3  xor     edx, edx; unsigned int *
0x18001a8c5  lea     rcx, [rbp+830h+RootPathName]; unsigned __int16 *
0x18001a8c9  call    ?GetDiskNumberAndExtent@@YAJPEBGPEAKPEAT_LARGE_INTEGER@@2@Z; GetDiskNumberAndExtent(ushort const *,ulong *,_LARGE_INTEGER *,_LARGE_INTEGER *)
0x18001a8ce  test    eax, eax
0x18001a8d0  js      short loc_18001A92E
0x18001a8d2  lea     r8, [rsp+930h+var_8E0]
0x18001a8d7  lea     rdx, [rsp+930h+var_8B8]
0x18001a8dc  lea     rcx, [rsp+930h+var_8D0]
0x18001a8e1  call    ??$_Try_emplace@AEB_J$$V@?$map@_JHU?$less@_J@std@@V?$allocator@U?$pair@$$CB_JH@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_JH@std@@PEAX@std@@_N@1@AEB_J@Z; std::map<__int64,int>::_Try_emplace<__int64 const &,>(__int64 const &)
0x18001a8e6  mov     rcx, [rax]
0x18001a8e9  mov     dword ptr [rcx+28h], 1
0x18001a8f0  mov     r8d, 104h
0x18001a8f6  lea     rdx, aData; "DATA"
0x18001a8fd  lea     rcx, [rbp+830h+VolumeNameBuffer]
0x18001a904  call    cs:__imp__o__wcsnicmp
0x18001a90a  test    eax, eax
0x18001a90c  jz      short loc_18001A92E
0x18001a90e  xor     r9d, r9d; lpTotalNumberOfFreeBytes
0x18001a911  lea     r8, [rsp+930h+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x18001a916  xor     edx, edx; lpFreeBytesAvailableToCaller
0x18001a918  lea     rcx, [rbp+830h+RootPathName]; lpDirectoryName
0x18001a91c  call    cs:__imp_GetDiskFreeSpaceExW
0x18001a922  test    eax, eax
0x18001a924  jz      short loc_18001A92E
0x18001a926  mov     rax, qword ptr [rsp+930h+TotalNumberOfBytes]
0x18001a92b  add     [r15], rax
0x18001a92e  inc     ebx
0x18001a930  cmp     ebx, 1Ah
0x18001a933  jl      loc_18001A87B
0x18001a939  mov     r12, [rsp+930h+var_8C0]
0x18001a93e  mov     r9, rsi
0x18001a941  lea     r8, aWs; "%ws\\"
0x18001a948  mov     esi, 104h
0x18001a94d  mov     edx, esi; unsigned __int64
0x18001a94f  lea     rcx, [rbp+830h+szVolumeMountPoint]; unsigned __int16 *
0x18001a956  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a95b  mov     ebx, eax
0x18001a95d  test    eax, eax
0x18001a95f  js      short loc_18001A98E
0x18001a961  mov     r8d, esi; cchBufferLength
0x18001a964  lea     rdx, [rbp+830h+szVolumeName]; lpszVolumeName
0x18001a968  lea     rcx, [rbp+830h+szVolumeMountPoint]; lpszVolumeMountPoint
0x18001a96f  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18001a975  test    eax, eax
0x18001a977  jnz     short loc_18001A9ED
0x18001a979  call    cs:__imp_GetLastError
0x18001a97f  mov     ebx, eax
0x18001a981  test    eax, eax
0x18001a983  jle     short loc_18001A98E
0x18001a985  movzx   ebx, ax
0x18001a988  or      ebx, 80070000h
0x18001a98e  lea     rcx, [rsp+930h+var_8E8]; struct _DISK_GEOMETRY_EX **
0x18001a993  call    ?SafeFreeDiskGeometry@@YAXPEAPEAU_DISK_GEOMETRY_EX@@@Z; SafeFreeDiskGeometry(_DISK_GEOMETRY_EX * *)
0x18001a998  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x18001a99c  jz      short loc_18001A9A7
0x18001a99e  mov     rcx, r13; hObject
0x18001a9a1  call    cs:__imp_CloseHandle
0x18001a9a7  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x18001a9ab  jz      short loc_18001A9B7
0x18001a9ad  mov     rcx, r12; hObject
0x18001a9b0  call    cs:__imp_CloseHandle
0x18001a9b6  nop
0x18001a9b7  lea     rcx, [rsp+930h+var_8D0]
0x18001a9bc  call    ??1?$_Tree@V?$_Tmap_traits@HPEAVDiskInfo@@U?$less@H@std@@V?$allocator@U?$pair@$$CBHPEAVDiskInfo@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<int,DiskInfo *,std::less<int>,std::allocator<std::pair<int const,DiskInfo *>>,0>>::~_Tree<std::_Tmap_traits<int,DiskInfo *,std::less<int>,std::allocator<std::pair<int const,DiskInfo *>>,0>>(void)
0x18001a9c1  mov     eax, ebx
0x18001a9c3  mov     rcx, [rbp+830h+var_40]
0x18001a9ca  xor     rcx, rsp; StackCookie
0x18001a9cd  call    __security_check_cookie
0x18001a9d2  mov     rbx, [rsp+930h+arg_8]
0x18001a9da  add     rsp, 900h
0x18001a9e1  pop     r15
0x18001a9e3  pop     r14
0x18001a9e5  pop     r13
0x18001a9e7  pop     r12
0x18001a9e9  pop     rdi
0x18001a9ea  pop     rsi
0x18001a9eb  pop     rbp
0x18001a9ec  retn
0x18001a9ed  lea     rcx, [rbp+830h+szVolumeName]
0x18001a9f1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a9f5  inc     rax
0x18001a9f8  cmp     [rcx+rax*2], r14w
0x18001a9fd  jnz     short loc_18001A9F5
0x18001a9ff  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18001aa07  cmp     rcx, 208h
0x18001aa0e  jnb     loc_18001AD73
0x18001aa14  mov     [rbp+rcx+830h+szVolumeName], r14w
0x18001aa1a  mov     [rsp+930h+lpFileSystemNameBuffer], r14; hTemplateFile
0x18001aa1f  mov     dword ptr [rsp+930h+lpFileSystemFlags], 80h; dwFlagsAndAttributes
0x18001aa27  mov     edi, 3
0x18001aa2c  mov     dword ptr [rsp+930h+lpMaximumComponentLength], edi; dwCreationDisposition
0x18001aa30  xor     r9d, r9d; lpSecurityAttributes
0x18001aa33  mov     r8d, edi; dwShareMode
0x18001aa36  mov     edx, 80000000h; dwDesiredAccess
0x18001aa3b  lea     rcx, [rbp+830h+szVolumeName]; lpFileName
0x18001aa3f  call    cs:__imp_CreateFileW
0x18001aa45  mov     r13, rax
0x18001aa48  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001aa4c  jz      loc_18001A979
0x18001aa52  mov     [rsp+930h+BytesReturned], r14d
0x18001aa57  mov     qword ptr [rsp+930h+nFileSystemNameSize], r14; lpOverlapped
0x18001aa5c  lea     rax, [rsp+930h+BytesReturned]
0x18001aa61  mov     [rsp+930h+lpFileSystemNameBuffer], rax; lpBytesReturned
0x18001aa66  mov     dword ptr [rsp+930h+lpFileSystemFlags], 20h ; ' '; nOutBufferSize
0x18001aa6e  lea     rax, [rbp+830h+OutBuffer]
0x18001aa72  mov     [rsp+930h+lpMaximumComponentLength], rax; lpOutBuffer
0x18001aa77  xor     r9d, r9d; nInBufferSize
0x18001aa7a  xor     r8d, r8d; lpInBuffer
0x18001aa7d  mov     edx, 560000h; dwIoControlCode
0x18001aa82  mov     rcx, r13; hDevice
0x18001aa85  call    cs:__imp_DeviceIoControl
0x18001aa8b  test    eax, eax
0x18001aa8d  jz      loc_18001A979
0x18001aa93  mov     r9d, dword ptr [rbp+830h+OutBuffer+8]
0x18001aa97  lea     r8, aPhysicaldriveU; "\\\\.\\PhysicalDrive%u"
0x18001aa9e  mov     rdx, rsi; unsigned __int64
0x18001aaa1  lea     rcx, [rbp+830h+FileName]; unsigned __int16 *
0x18001aaa8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001aaad  mov     ebx, eax
0x18001aaaf  test    eax, eax
0x18001aab1  js      loc_18001A98E
0x18001aab7  mov     [rsp+930h+lpFileSystemNameBuffer], r14; hTemplateFile
0x18001aabc  mov     dword ptr [rsp+930h+lpFileSystemFlags], 80h; dwFlagsAndAttributes
0x18001aac4  mov     dword ptr [rsp+930h+lpMaximumComponentLength], edi; dwCreationDisposition
0x18001aac8  xor     r9d, r9d; lpSecurityAttributes
0x18001aacb  mov     r8d, edi; dwShareMode
0x18001aace  mov     edx, 80000000h; dwDesiredAccess
0x18001aad3  lea     rcx, [rbp+830h+FileName]; lpFileName
0x18001aada  call    cs:__imp_CreateFileW
0x18001aae0  mov     r12, rax
0x18001aae3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001aae7  jz      loc_18001A979
0x18001aaed  lea     rdx, [rsp+930h+var_8E8]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x18001aaf2  mov     rcx, rax; hDevice
0x18001aaf5  call    ?GetDiskLayoutInternal@@YAJQEAXPEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAK@Z; GetDiskLayoutInternal(void * const,_DRIVE_LAYOUT_INFORMATION_EX * *,ulong *)
0x18001aafa  mov     ebx, eax
0x18001aafc  test    eax, eax
0x18001aafe  js      loc_18001A98E
0x18001ab04  mov     rdi, [rsp+930h+var_8E8]
0x18001ab09  cmp     dword ptr [rdi+4], 0
0x18001ab0d  jbe     loc_18001A98E
0x18001ab13  mov     eax, r14d
0x18001ab16  lea     rsi, [rax+rax*8]
0x18001ab1a  shl     rsi, 4
0x18001ab1e  cmp     qword ptr [rsi+rdi+40h], 0
0x18001ab24  jz      loc_18001AD61
0x18001ab2a  lea     r8, [rdi+38h]
0x18001ab2e  add     r8, rsi
0x18001ab31  lea     rdx, [rsp+930h+var_8B8]
0x18001ab36  lea     rcx, [rsp+930h+var_8D0]
0x18001ab3b  call    ??$_Try_emplace@AEB_J$$V@?$map@_JHU?$less@_J@std@@V?$allocator@U?$pair@$$CB_JH@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_JH@std@@PEAX@std@@_N@1@AEB_J@Z; std::map<__int64,int>::_Try_emplace<__int64 const &,>(__int64 const &)
0x18001ab40  mov     rcx, [rax]
0x18001ab43  cmp     dword ptr [rcx+28h], 1
0x18001ab47  jz      loc_18001AD61
0x18001ab4d  mov     eax, [rsi+rdi+30h]
0x18001ab51  test    eax, eax
0x18001ab53  jnz     short loc_18001AB84
0x18001ab55  movzx   ecx, byte ptr [rsi+rdi+50h]
0x18001ab5a  cmp     cl, 42h ; 'B'
0x18001ab5d  jz      loc_18001AD61
0x18001ab63  cmp     cl, 2Dh ; '-'
0x18001ab66  ja      short loc_18001AB7C
0x18001ab68  mov     rdx, 3F800000D8F2h
0x18001ab72  bt      rdx, rcx
0x18001ab76  jb      loc_18001AD61
0x18001ab7c  cmp     cl, 0EFh
0x18001ab7f  jmp     loc_18001AD57
0x18001ab84  cmp     eax, 1
0x18001ab87  jnz     loc_18001AD61
0x18001ab8d  mov     rax, [rsi+rdi+50h]
0x18001ab92  sub     rax, qword ptr cs:PARTITION_BSP_GUID.Data1
0x18001ab99  jnz     short loc_18001ABA7
0x18001ab9b  mov     rax, [rsi+rdi+58h]
0x18001aba0  sub     rax, qword ptr cs:PARTITION_BSP_GUID.Data4
0x18001aba7  test    rax, rax
0x18001abaa  jz      loc_18001AD40
0x18001abb0  mov     rax, [rsi+rdi+50h]
0x18001abb5  sub     rax, qword ptr cs:PARTITION_DPP_GUID.Data1
0x18001abbc  jnz     short loc_18001ABCA
0x18001abbe  mov     rax, [rsi+rdi+58h]
0x18001abc3  sub     rax, qword ptr cs:PARTITION_DPP_GUID.Data4
0x18001abca  test    rax, rax
0x18001abcd  jz      loc_18001AD40
0x18001abd3  mov     rax, [rsi+rdi+50h]
0x18001abd8  sub     rax, qword ptr cs:PARTITION_BASIC_DATA_GUID.Data1
0x18001abdf  jnz     short loc_18001ABED
0x18001abe1  mov     rax, [rsi+rdi+58h]
0x18001abe6  sub     rax, qword ptr cs:PARTITION_BASIC_DATA_GUID.Data4
0x18001abed  test    rax, rax
0x18001abf0  jz      loc_18001AD40
0x18001abf6  mov     rax, [rsi+rdi+50h]
0x18001abfb  sub     rax, qword ptr cs:PARTITION_MAIN_OS_GUID.Data1
0x18001ac02  jnz     short loc_18001AC10
0x18001ac04  mov     rax, [rsi+rdi+58h]
0x18001ac09  sub     rax, qword ptr cs:PARTITION_MAIN_OS_GUID.Data4
0x18001ac10  test    rax, rax
0x18001ac13  jz      loc_18001AD40
0x18001ac19  mov     rax, [rsi+rdi+50h]
0x18001ac1e  sub     rax, qword ptr cs:PARTITION_MSFT_RECOVERY_GUID.Data1
0x18001ac25  jnz     short loc_18001AC33
0x18001ac27  mov     rax, [rsi+rdi+58h]
0x18001ac2c  sub     rax, qword ptr cs:PARTITION_MSFT_RECOVERY_GUID.Data4
0x18001ac33  test    rax, rax
0x18001ac36  jz      loc_18001AD40
0x18001ac3c  mov     rax, [rsi+rdi+50h]
0x18001ac41  sub     rax, qword ptr cs:PARTITION_OS_DATA_GUID.Data1
0x18001ac48  jnz     short loc_18001AC56
0x18001ac4a  mov     rax, [rsi+rdi+58h]
0x18001ac4f  sub     rax, qword ptr cs:PARTITION_OS_DATA_GUID.Data4
0x18001ac56  test    rax, rax
0x18001ac59  jz      loc_18001AD40
0x18001ac5f  mov     rax, [rsi+rdi+50h]
0x18001ac64  sub     rax, qword ptr cs:PARTITION_PRE_INSTALLED_GUID.Data1
0x18001ac6b  jnz     short loc_18001AC79
0x18001ac6d  mov     rax, [rsi+rdi+58h]
0x18001ac72  sub     rax, qword ptr cs:PARTITION_PRE_INSTALLED_GUID.Data4
0x18001ac79  test    rax, rax
0x18001ac7c  jz      loc_18001AD40
0x18001ac82  mov     rax, [rsi+rdi+50h]
0x18001ac87  sub     rax, cs:PARTITION_SERVICING_FILES_GUID
0x18001ac8e  jnz     short loc_18001AC9C
0x18001ac90  mov     rax, [rsi+rdi+58h]
0x18001ac95  sub     rax, cs:qword_180093B20
0x18001ac9c  test    rax, rax
0x18001ac9f  jz      loc_18001AD40
0x18001aca5  mov     rax, [rsi+rdi+50h]
0x18001acaa  sub     rax, cs:PARTITION_SERVICING_METADATA_GUID
0x18001acb1  jnz     short loc_18001ACBF
0x18001acb3  mov     rax, [rsi+rdi+58h]
0x18001acb8  sub     rax, cs:qword_180093AF0
0x18001acbf  test    rax, rax
0x18001acc2  jz      short loc_18001AD40
0x18001acc4  mov     rax, [rsi+rdi+50h]
0x18001acc9  sub     rax, cs:PARTITION_SERVICING_RESERVE_GUID
0x18001acd0  jnz     short loc_18001ACDE
0x18001acd2  mov     rax, [rsi+rdi+58h]
0x18001acd7  sub     rax, cs:qword_1800939C8
0x18001acde  test    rax, rax
  ... truncated ...
```
