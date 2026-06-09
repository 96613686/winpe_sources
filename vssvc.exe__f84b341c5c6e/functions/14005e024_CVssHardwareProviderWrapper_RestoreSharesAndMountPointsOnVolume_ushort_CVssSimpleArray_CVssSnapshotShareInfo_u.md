# CVssHardwareProviderWrapper::RestoreSharesAndMountPointsOnVolume(ushort *,CVssSimpleArray<CVssSnapshotShareInfo> &,ushort *)

- ea: `0x14005e024`
- end: `0x14005eaf2`
- name: `?RestoreSharesAndMountPointsOnVolume@CVssHardwareProviderWrapper@@AEAAXPEAGAEAV?$CVssSimpleArray@UCVssSnapshotShareInfo@@@@0@Z`
- size: `2766`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x140063f60`

## callees

- `0x140006020`
- `0x14000e640`
- `0x140010170`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013b00`
- `0x140015e38`
- `0x140025b00`
- `0x1400326c0`
- `0x1400330fc`
- `0x14003a8f0`
- `0x14003ade4`
- `0x14003fc04`
- `0x140049ec4`
- `0x14005e024`
- `0x14005eaf8`
- `0x140091560`
- `0x1400921dc`
- `0x1400921e8`
- `0x1400b20a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005e276`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005e287`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005e2a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005e3ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005e3c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005e481`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005e5e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005e638`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005e276`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005e287`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005e2a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005e3ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005e3c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005e481`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005e5e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005e638`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14005e356`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14005e356`
- `api-ms-win-core-file-l1-1-0!DeleteVolumeMountPointW` at `0x14005e473`
- `api-ms-win-core-file-l1-1-0!DeleteVolumeMountPointW` at `0x14005e473`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x14005e270`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x14005e3a0`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x14005e270`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x14005e3a0`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetVolumeMountPointW` at `0x14005e54e`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetVolumeMountPointW` at `0x14005e54e`
- `srvcli!NetShareDel` at `0x14005e846`
- `srvcli!NetShareDel` at `0x14005e846`
- `srvcli!NetShareAdd` at `0x14005e8e8`
- `srvcli!NetShareAdd` at `0x14005e8e8`

## string_xrefs

- `0x14005e065`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x14005e71c`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x14005e31d`: `GetVolumePathNamesForVolumeName(%s) fails with 0x%08lx`
- `0x14005e43d`: `GetVolumePathNamesForVolumeName(%s) fails with 0x%08lx`
- `0x14005e6b4`: `SetVolumeMountPoint(%s, %s) fails with 0x%08lx`
- `0x14005e4ee`: `Fail to delete mount point %s for volume %s, winerror %d`
- `0x14005e071`: `CVssHardwareProviderWrapper::RestoreSharesAndMountPointsOnVolume`
- `0x14005e715`: `CVssHardwareProviderWrapper::RestoreSharesAndMountPointsOnVolume`
- `0x14005e17e`: `StringCchCopy copy input volume name`
- `0x14005e78b`: `Fail to restore all mount points for %s. [0%08lx]. Continuing.`
- `0x14005ea10`: `NetShareAdd(%s, %s) failed with %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CVssHardwareProviderWrapper::RestoreSharesAndMountPointsOnVolume(
        __int64 a1,
        const unsigned __int16 *a2,
        __int64 a3,
        const WCHAR *a4)
{
  __int64 v5; // rax
  signed int LastError; // eax
  signed int v7; // eax
  __int64 v8; // rbx
  WCHAR *v9; // rax
  const WCHAR *v10; // r14
  signed int v11; // eax
  unsigned int v12; // ebx
  signed int v13; // eax
  unsigned int v14; // r14d
  __int64 v15; // rax
  DWORD v16; // ebx
  __int64 v17; // rax
  WCHAR *v18; // rbx
  __int64 v19; // rax
  struct CVssDebugInfo *v20; // rax
  struct CVssDebugInfo *v21; // rbx
  __int64 v22; // rax
  signed int v23; // eax
  unsigned int v24; // ebx
  __int64 v25; // rax
  WCHAR *v26; // rbx
  bool v27; // zf
  WCHAR *v28; // r14
  int v29; // ebx
  unsigned int v30; // eax
  LPWSTR **v31; // rbx
  __int64 v32; // rdx
  WCHAR *v33; // r9
  unsigned int v34; // r14d
  DWORD v35; // r14d
  WCHAR *v36; // r14
  struct CVssDebugInfo *v37; // rax
  __int64 v38; // rax
  __int64 v39; // [rsp+20h] [rbp-758h]
  __int64 v40; // [rsp+20h] [rbp-758h]
  __int64 v41; // [rsp+28h] [rbp-750h]
  unsigned int v42; // [rsp+40h] [rbp-738h]
  unsigned int v43; // [rsp+40h] [rbp-738h]
  LPCWSTR lpszVolumeMountPoint; // [rsp+48h] [rbp-730h]
  DWORD cchReturnLength; // [rsp+50h] [rbp-728h] BYREF
  LPCWSTR v46; // [rsp+58h] [rbp-720h]
  const WCHAR *v47; // [rsp+60h] [rbp-718h]
  BOOL v48; // [rsp+68h] [rbp-710h]
  const unsigned __int16 *v49; // [rsp+70h] [rbp-708h] BYREF
  const unsigned __int16 *v50; // [rsp+78h] [rbp-700h]
  const unsigned __int16 *v51; // [rsp+80h] [rbp-6F8h]
  int v52; // [rsp+88h] [rbp-6F0h]
  int v53; // [rsp+8Ch] [rbp-6ECh]
  int v54; // [rsp+90h] [rbp-6E8h]
  _BYTE v55[120]; // [rsp+98h] [rbp-6E0h] BYREF
  int v56; // [rsp+110h] [rbp-668h]
  int pExceptionObject; // [rsp+118h] [rbp-660h] BYREF
  __int64 v58; // [rsp+120h] [rbp-658h]
  void **v59; // [rsp+128h] [rbp-650h] BYREF
  WCHAR *v60; // [rsp+130h] [rbp-648h]
  LPVOID v61; // [rsp+140h] [rbp-638h] BYREF
  int v62; // [rsp+148h] [rbp-630h]
  unsigned int v63; // [rsp+164h] [rbp-614h]
  int v64; // [rsp+1B0h] [rbp-5C8h] BYREF
  const std::exception *v65; // [rsp+1B8h] [rbp-5C0h] BYREF
  _com_error *v66; // [rsp+1C0h] [rbp-5B8h] BYREF
  _BYTE v67[168]; // [rsp+1C8h] [rbp-5B0h] BYREF
  _BYTE v68[176]; // [rsp+270h] [rbp-508h] BYREF
  WCHAR szVolumeName[264]; // [rsp+320h] [rbp-458h] BYREF
  unsigned __int16 v70[264]; // [rsp+530h] [rbp-248h] BYREF

  lpszVolumeMountPoint = a4;
  v58 = a3;
  v47 = a4;
  v49 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
  v50 = L"CVssHardwareProviderWrapper::RestoreSharesAndMountPointsOnVolume";
  v51 = L"CORHDELC";
  v52 = 1436;
  v53 = 1;
  v54 = 255;
  v56 = 0x1000000;
  memset_0(v55, 0, sizeof(v55));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v61, (__int64)&v49, 0);
  cchReturnLength = 0;
  memset_0(szVolumeName, 0, 0x208u);
  v60 = 0;
  v59 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
  v62 = StringCchCopyW(szVolumeName, 0x104u, a2);
  v49 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
  v50 = L"CVssHardwareProviderWrapper::RestoreSharesAndMountPointsOnVolume";
  v51 = L"CORHDELC";
  v52 = 1449;
  v53 = 1;
  v54 = 255;
  v56 = 0x1000000;
  memset_0(v55, 0, sizeof(v55));
  CVssFunctionTracer::CheckForErrorInternal(&v61, &v49, L"StringCchCopy copy input volume name");
  v5 = -1;
  do
    ++v5;
  while ( szVolumeName[v5] );
  if ( *(_WORD *)&v68[2 * (unsigned __int16)v5 + 174] != 92 )
  {
    v62 = StringCchCatW(szVolumeName, 0x104u, L"\\");
    v49 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
    v50 = L"CVssHardwareProviderWrapper::RestoreSharesAndMountPointsOnVolume";
    v51 = L"CORHDELC";
    v52 = 1458;
    v53 = 1;
    v54 = 255;
    v56 = 0x1000000;
    memset_0(v55, 0, sizeof(v55));
    CVssFunctionTracer::CheckForErrorInternal(&v61, &v49, L"StringCchCat fails to concat backslash");
  }
  v48 = lpszVolumeMountPoint == 0;
  try
  {
    if ( lpszVolumeMountPoint )
    {
      GetVolumePathNamesForVolumeNameW(szVolumeName, 0, 0, &cchReturnLength);
      if ( GetLastError() != 234 )
      {
        LastError = GetLastError();
        v42 = LastError;
        if ( LastError > 0 )
          v42 = (unsigned __int16)LastError | 0x80070000;
        v7 = GetLastError();
        LODWORD(v46) = v7;
        if ( v7 > 0 )
          LODWORD(v46) = (unsigned __int16)v7 | 0x80070000;
        v49 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
        v50 = L"CVssHardwareProviderWrapper::RestoreSharesAndMountPointsOnVolume";
        v51 = L"CORHDELC";
        v52 = 1479;
        v53 = 1;
        v54 = 255;
        v56 = 0x1000000;
        memset_0(v55, 0, sizeof(v55));
        CVssFunctionTracer::Throw(
          &v61,
          &v49,
          (unsigned int)v46,
          L"GetVolumePathNamesForVolumeName(%s) fails with 0x%08lx",
          szVolumeName,
          v42);
      }
      v8 = cchReturnLength;
      CVssAutoGenericValue_Storage<unsigned short *,0,void * (*)(void *),&void * LocalFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close(&v59);
      v9 = (WCHAR *)LocalAlloc(0, 2 * v8 + 2);
      v10 = v9;
      v60 = v9;
      if ( !v9 )
      {
        pExceptionObject = -2147024882;
        throw (long *)&pExceptionObject;
      }
      if ( !GetVolumePathNamesForVolumeNameW(szVolumeName, v9, cchReturnLength, &cchReturnLength) )
      {
        v11 = GetLastError();
        v12 = v11;
        if ( v11 > 0 )
          v12 = (unsigned __int16)v11 | 0x80070000;
        v13 = GetLastError();
        v14 = v13;
        if ( v13 > 0 )
          v14 = (unsigned __int16)v13 | 0x80070000;
        v49 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
        v50 = L"CVssHardwareProviderWrapper::RestoreSharesAndMountPointsOnVolume";
        v51 = L"CORHDELC";
        v52 = 1487;
        v53 = 1;
        v54 = 255;
        v56 = 0x1000000;
        memset_0(v55, 0, sizeof(v55));
        CVssFunctionTracer::Throw(
          &v61,
          &v49,
          v14,
          L"GetVolumePathNamesForVolumeName(%s) fails with 0x%08lx",
          szVolumeName,
          v12);
      }
      do
      {
        v15 = -1;
        do
          ++v15;
        while ( v10[v15] );
        if ( !v15 )
          break;
        if ( !DeleteVolumeMountPointW(v10) )
        {
          v16 = GetLastError();
          v49 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
          v50 = L"CVssHardwareProviderWrapper::RestoreSharesAndMountPointsOnVolume";
          v51 = L"CORHDELC";
          v52 = 1499;
          v53 = 1;
          v54 = 255;
          v56 = 0x1000000;
          memset_0(v55, 0, sizeof(v55));
          LODWORD(v41) = v16;
          CVssFunctionTracer::Trace(
            &v61,
            &v49,
            L"Fail to delete mount point %s for volume %s, winerror %d",
            v10,
            szVolumeName,
            v41);
        }
        v17 = -1;
        do
          ++v17;
        while ( v10[v17] );
        v10 += v17 + 1;
      }
      while ( v10 );
      v18 = (WCHAR *)lpszVolumeMountPoint;
      v46 = lpszVolumeMountPoint;
      do
      {
        v19 = -1;
        do
          ++v19;
        while ( v18[v19] );
        if ( !v19 )
          break;
        if ( !SetVolumeMountPointW(v18, szVolumeName) )
        {
          v49 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
          v50 = L"CVssHardwareProviderWrapper::RestoreSharesAndMountPointsOnVolume";
          v51 = L"CORHDELC";
          v52 = 1515;
          v53 = 6;
          v54 = 255;
          v56 = 0x1000000;
          memset_0(v55, 0, sizeof(v55));
          v20 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v49, (CVssDebugInfo *)v68, v18);
          v21 = CVssDebugInfo::operator<<(v20, (CVssDebugInfo *)v67, szVolumeName);
          GetLastError();
          v22 = CVssDebugInfo::operator<<(v21, (CVssDebugInfo *)v70);
          CVssFunctionTracer::LogError(&v61, 12353, v22, 1);
          CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v67);
          CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v68);
          CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v49);
          v23 = GetLastError();
          v24 = v23;
          if ( v23 > 0 )
            v24 = (unsigned __int16)v23 | 0x80070000;
          v49 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
          v50 = L"CVssHardwareProviderWrapper::RestoreSharesAndMountPointsOnVolume";
          v51 = L"CORHDELC";
          v52 = 1517;
          v53 = 6;
          v54 = 255;
          v56 = 0x1000000;
          memset_0(v55, 0, sizeof(v55));
          LODWORD(v41) = v24;
          v18 = (WCHAR *)v46;
          CVssFunctionTracer::Trace(
            &v61,
            &v49,
            L"SetVolumeMountPoint(%s, %s) fails with 0x%08lx",
            v46,
            szVolumeName,
            v41);
          v48 = 1;
        }
        v25 = -1;
        do
          ++v25;
        while ( v18[v25] );
        v26 = &v18[v25];
        v27 = v26 + 1 == 0;
        v18 = v26 + 1;
        v46 = v18;
      }
      while ( !v27 );
    }
  }
  catch ( long v64 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v61,
      v64,
      L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx",
      L"CORHDELC",
      L"CVssHardwareProviderWrapper::RestoreSharesAndMountPointsOnVolume",
      0x5F7u,
      v63);
    v28 = (WCHAR *)v47;
    lpszVolumeMountPoint = v47;
    goto LABEL_42;
  }
  catch ( _com_error *v66 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v61,
      v66,
      L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx",
      L"CORHDELC",
      L"CVssHardwareProviderWrapper::RestoreSharesAndMountPointsOnVolume",
      0x5F7u,
      v63);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v61,
      L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx",
      L"CORHDELC",
      L"CVssHardwareProviderWrapper::RestoreSharesAndMountPointsOnVolume",
      0x5F7u,
      v63);
    v28 = (WCHAR *)v47;
    lpszVolumeMountPoint = v47;
    goto LABEL_42;
  }
  catch ( const std::exception *v65 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v61,
      v65,
      L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx",
      L"CORHDELC",
      L"CVssHardwareProviderWrapper::RestoreSharesAndMountPointsOnVolume",
      0x5F7u,
      v63);
  }
  v28 = (WCHAR *)lpszVolumeMountPoint;
LABEL_42:
  v29 = v62;
  if ( v62 < 0 )
  {
    v49 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
    v50 = L"CVssHardwareProviderWrapper::RestoreSharesAndMountPointsOnVolume";
    v51 = L"CORHDELC";
    v52 = 1531;
    v53 = 1;
    v54 = 255;
    v56 = 0x1000000;
    memset_0(v55, 0, sizeof(v55));
    LODWORD(v39) = v29;
    CVssFunctionTracer::Trace(
      &v61,
      &v49,
      L"Fail to restore all mount points for %s. [0%08lx]. Continuing.",
      szVolumeName,
      v39);
    v62 = 0;
  }
  v30 = 0;
  while ( 1 )
  {
    v43 = v30;
    if ( (signed int)v30 >= *(_DWORD *)(v58 + 8) )
      break;
    v31 = (LPWSTR **)ATL::CSimpleArray<CVssSnapshotShareInfo,ATL::CSimpleArrayEqualHelper<CVssSnapshotShareInfo>>::operator[](
                       v58,
                       v30);
    memset_0(v70, 0, 0x208u);
    v32 = -1;
    do
      ++v32;
    while ( *((_WORD *)v31 + v32 + 4) );
    v33 = szVolumeName;
    if ( !v48 )
      v33 = v28;
    v62 = StringCchPrintfW(v70, 0x104u, L"%s%s", v33, &(*v31)[5][v32]);
    v34 = v62;
    if ( v62 < 0 )
    {
      v49 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      v50 = L"CVssHardwareProviderWrapper::RestoreSharesAndMountPointsOnVolume";
      v51 = L"CORHDELC";
      v52 = 1555;
      v53 = 1;
      v54 = 255;
      v56 = 0x1000000;
      memset_0(v55, 0, sizeof(v55));
      CVssFunctionTracer::TranslateGenericError(&v61, &v49, v34, L"StringCchPrintfW()");
    }
    v35 = NetShareDel(0, **v31, 0);
    if ( v35 )
    {
      v49 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      v50 = L"CVssHardwareProviderWrapper::RestoreSharesAndMountPointsOnVolume";
      v51 = L"CORHDELC";
      v52 = 1559;
      v53 = 6;
      v54 = 255;
      v56 = 0x1000000;
      memset_0(v55, 0, sizeof(v55));
      LODWORD(v40) = v35;
      CVssFunctionTracer::Trace(&v61, &v49, L"NetShareDel(%s) failed with %d", **v31, v40);
    }
    v36 = (*v31)[5];
    (*v31)[5] = v70;
    LODWORD(v46) = NetShareAdd(0, 0x1F6u, (LPBYTE)*v31, 0);
    if ( (_DWORD)v46 )
    {
      v49 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      v50 = L"CVssHardwareProviderWrapper::RestoreSharesAndMountPointsOnVolume";
      v51 = L"CORHDELC";
      v52 = 1567;
      v53 = 6;
      v54 = 255;
      v56 = 0x1000000;
      memset_0(v55, 0, sizeof(v55));
      v37 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v49, (CVssDebugInfo *)v67, v70);
      v38 = CVssDebugInfo::operator<<(v37, (CVssDebugInfo *)v68);
      CVssFunctionTracer::LogError(&v61, 12354, v38, 1);
      CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v67);
      CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v49);
      v49 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      v50 = L"CVssHardwareProviderWrapper::RestoreSharesAndMountPointsOnVolume";
      v51 = L"CORHDELC";
      v52 = 1568;
      v53 = 6;
      v54 = 255;
      v56 = 0x1000000;
      memset_0(v55, 0, sizeof(v55));
      LODWORD(v41) = (_DWORD)v46;
      CVssFunctionTracer::Trace(&v61, &v49, L"NetShareAdd(%s, %s) failed with %d", **v31, v36, v41);
    }
    (*v31)[5] = v36;
    v30 = v43 + 1;
    v28 = (WCHAR *)lpszVolumeMountPoint;
  }
  CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(&v59);
  CVssFunctionTracer::~CVssFunctionTracer(&v61);
}

```

## disassembly

```asm
0x14005e024  mov     r11, rsp
0x14005e027  mov     [r11+8], rbx
0x14005e02b  push    rdi
0x14005e02c  push    r12
0x14005e02e  push    r13
0x14005e030  push    r14
0x14005e032  push    r15
0x14005e034  sub     rsp, 750h
0x14005e03b  mov     rax, cs:__security_cookie
0x14005e042  xor     rax, rsp
0x14005e045  mov     [rsp+778h+var_38], rax
0x14005e04d  mov     rax, r9
0x14005e050  mov     [rsp+778h+lpszVolumeMountPoint], rax
0x14005e055  mov     rbx, rdx
0x14005e058  mov     [rsp+778h+var_658], r8
0x14005e060  mov     [rsp+778h+var_718], rax
0x14005e065  lea     r15, aBaseStorVssMod_22; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x14005e06c  mov     [rsp+778h+var_708], r15
0x14005e071  lea     r12, aCvsshardwarepr_175; "CVssHardwareProviderWrapper::RestoreSha"...
0x14005e078  mov     [rsp+778h+var_700], r12
0x14005e07d  lea     r13, aCorhdelc; "CORHDELC"
0x14005e084  mov     [r11-6F8h], r13
0x14005e08b  mov     [rsp+778h+var_6F0], 59Ch
0x14005e096  mov     [rsp+778h+var_6EC], 1
0x14005e0a1  mov     r14d, 0FFh
0x14005e0a7  mov     [r11-6E8h], r14d
0x14005e0ae  xor     edi, edi
0x14005e0b0  mov     [rsp+778h+var_668], 1000000h
0x14005e0bb  xor     edx, edx; Val
0x14005e0bd  lea     r8d, [rdi+78h]; Size
0x14005e0c1  lea     rcx, [r11-6E0h]; void *
0x14005e0c8  call    memset_0
0x14005e0cd  xor     r8d, r8d
0x14005e0d0  lea     rdx, [rsp+778h+var_708]
0x14005e0d5  lea     rcx, [rsp+778h+var_638]
0x14005e0dd  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x14005e0e2  nop
0x14005e0e3  mov     [rsp+778h+cchReturnLength], edi
0x14005e0e7  xor     edx, edx; Val
0x14005e0e9  mov     r8d, 208h; Size
0x14005e0ef  lea     rcx, [rsp+778h+szVolumeName]; void *
0x14005e0f7  call    memset_0
0x14005e0fc  mov     [rsp+778h+var_648], rdi
0x14005e104  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x14005e10b  mov     [rsp+778h+var_650], rax
0x14005e113  mov     r8, rbx; unsigned __int16 *
0x14005e116  lea     edx, [r14+5]; unsigned __int64
0x14005e11a  lea     rcx, [rsp+778h+szVolumeName]; unsigned __int16 *
0x14005e122  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14005e127  mov     [rsp+778h+var_630], eax
0x14005e12e  mov     [rsp+778h+var_708], r15
0x14005e133  mov     [rsp+778h+var_700], r12
0x14005e138  mov     [rsp+778h+var_6F8], r13
0x14005e140  mov     [rsp+778h+var_6F0], 5A9h
0x14005e14b  mov     [rsp+778h+var_6EC], 1
0x14005e156  mov     [rsp+778h+var_6E8], r14d
0x14005e15e  mov     [rsp+778h+var_668], 1000000h
0x14005e169  lea     ebx, [rdi+78h]
0x14005e16c  mov     r8d, ebx; Size
0x14005e16f  xor     edx, edx; Val
0x14005e171  lea     rcx, [rsp+778h+var_6E0]; void *
0x14005e179  call    memset_0
0x14005e17e  lea     r8, aStringcchcopyC_0; "StringCchCopy copy input volume name"
0x14005e185  lea     rdx, [rsp+778h+var_708]
0x14005e18a  lea     rcx, [rsp+778h+var_638]
0x14005e192  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x14005e197  lea     rcx, [rsp+778h+szVolumeName]
0x14005e19f  or      rax, 0FFFFFFFFFFFFFFFFh
0x14005e1a3  inc     rax
0x14005e1a6  cmp     [rcx+rax*2], di
0x14005e1aa  jnz     short loc_14005E1A3
0x14005e1ac  movzx   eax, ax
0x14005e1af  cmp     [rsp+rax*2+778h+var_45A], 5Ch ; '\'
0x14005e1b8  jz      loc_14005E244
0x14005e1be  lea     r8, pszSrc; "\\"
0x14005e1c5  mov     edx, 104h; unsigned __int64
0x14005e1ca  lea     rcx, [rsp+778h+szVolumeName]; unsigned __int16 *
0x14005e1d2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14005e1d7  mov     [rsp+778h+var_630], eax
0x14005e1de  mov     [rsp+778h+var_708], r15
0x14005e1e3  mov     [rsp+778h+var_700], r12
0x14005e1e8  mov     [rsp+778h+var_6F8], r13
0x14005e1f0  mov     [rsp+778h+var_6F0], 5B2h
0x14005e1fb  mov     [rsp+778h+var_6EC], 1
0x14005e206  mov     [rsp+778h+var_6E8], r14d
0x14005e20e  mov     [rsp+778h+var_668], 1000000h
0x14005e219  mov     r8, rbx; Size
0x14005e21c  xor     edx, edx; Val
0x14005e21e  lea     rcx, [rsp+778h+var_6E0]; void *
0x14005e226  call    memset_0
0x14005e22b  lea     r8, aStringcchcatFa_1; "StringCchCat fails to concat backslash"
0x14005e232  lea     rdx, [rsp+778h+var_708]
0x14005e237  lea     rcx, [rsp+778h+var_638]
0x14005e23f  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x14005e244  mov     eax, edi
0x14005e246  mov     rcx, [rsp+778h+lpszVolumeMountPoint]
0x14005e24b  test    rcx, rcx
0x14005e24e  setz    al
0x14005e251  mov     [rsp+778h+var_710], eax
0x14005e255  test    rcx, rcx
0x14005e258  jz      loc_14005E6F5
0x14005e25e  lea     r9, [rsp+778h+cchReturnLength]; lpcchReturnLength
0x14005e263  xor     r8d, r8d; cchBufferLength
0x14005e266  xor     edx, edx; lpszVolumePathNames
0x14005e268  lea     rcx, [rsp+778h+szVolumeName]; lpszVolumeName
0x14005e270  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x14005e276  call    cs:__imp_GetLastError
0x14005e27c  cmp     eax, 0EAh
0x14005e281  jz      loc_14005E33B
0x14005e287  call    cs:__imp_GetLastError
0x14005e28d  mov     [rsp+778h+var_738], eax
0x14005e291  test    eax, eax
0x14005e293  jle     short loc_14005E2A1
0x14005e295  movzx   eax, ax
0x14005e298  or      eax, 80070000h
0x14005e29d  mov     [rsp+778h+var_738], eax
0x14005e2a1  call    cs:__imp_GetLastError
0x14005e2a7  mov     dword ptr [rsp+778h+var_720], eax
0x14005e2ab  test    eax, eax
0x14005e2ad  jle     short loc_14005E2BB
0x14005e2af  movzx   eax, ax
0x14005e2b2  or      eax, 80070000h
0x14005e2b7  mov     dword ptr [rsp+778h+var_720], eax
0x14005e2bb  mov     [rsp+778h+var_708], r15
0x14005e2c0  mov     [rsp+778h+var_700], r12
0x14005e2c5  mov     [rsp+778h+var_6F8], r13
0x14005e2cd  mov     [rsp+778h+var_6F0], 5C7h
0x14005e2d8  mov     [rsp+778h+var_6EC], 1
0x14005e2e3  mov     [rsp+778h+var_6E8], r14d
0x14005e2eb  mov     [rsp+778h+var_668], 1000000h
0x14005e2f6  mov     r8, rbx; Size
0x14005e2f9  xor     edx, edx; Val
0x14005e2fb  lea     rcx, [rsp+778h+var_6E0]; void *
0x14005e303  call    memset_0
0x14005e308  mov     eax, [rsp+778h+var_738]
0x14005e30c  mov     dword ptr [rsp+778h+var_750], eax
0x14005e310  lea     rax, [rsp+778h+szVolumeName]
0x14005e318  mov     [rsp+778h+var_758], rax
0x14005e31d  lea     r9, aGetvolumepathn_6; "GetVolumePathNamesForVolumeName(%s) fai"...
0x14005e324  mov     r8d, dword ptr [rsp+778h+var_720]
0x14005e329  lea     rdx, [rsp+778h+var_708]
0x14005e32e  lea     rcx, [rsp+778h+var_638]
0x14005e336  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x14005e33b  mov     ebx, [rsp+778h+cchReturnLength]
0x14005e33f  lea     rcx, [rsp+778h+var_650]
0x14005e347  call    ?Close@?$CVssAutoGenericValue_Storage@PEAG$0A@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZP6AAEAPEAGAEAPEAG@Z$1?Identity@?$DTyper@PEAG@@SAAEAPEAG1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<ushort *,0,void * (*)(void *),&LocalFree(void *),ushort * & (*)(ushort * &),&DTyper<ushort *>::Identity(ushort * &)>::Close(void)
0x14005e34c  lea     rdx, ds:2[rbx*2]; uBytes
0x14005e354  xor     ecx, ecx; uFlags
0x14005e356  call    cs:__imp_LocalAlloc
0x14005e35c  mov     r14, rax
0x14005e35f  mov     [rsp+778h+var_648], rax
0x14005e367  test    rax, rax
0x14005e36a  jnz     short loc_14005E38B
0x14005e36c  mov     [rsp+778h+pExceptionObject], 8007000Eh
0x14005e377  lea     rdx, _TI1J; pThrowInfo
0x14005e37e  lea     rcx, [rsp+778h+pExceptionObject]; pExceptionObject
0x14005e386  call    _CxxThrowException_0
0x14005e38b  lea     r9, [rsp+778h+cchReturnLength]; lpcchReturnLength
0x14005e390  mov     r8d, [rsp+778h+cchReturnLength]; cchBufferLength
0x14005e395  mov     rdx, rax; lpszVolumePathNames
0x14005e398  lea     rcx, [rsp+778h+szVolumeName]; lpszVolumeName
0x14005e3a0  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x14005e3a6  test    eax, eax
0x14005e3a8  jnz     loc_14005E459
0x14005e3ae  call    cs:__imp_GetLastError
0x14005e3b4  mov     ebx, eax
0x14005e3b6  test    eax, eax
0x14005e3b8  jle     short loc_14005E3C3
0x14005e3ba  movzx   ebx, ax
0x14005e3bd  or      ebx, 80070000h
0x14005e3c3  call    cs:__imp_GetLastError
0x14005e3c9  mov     r14d, eax
0x14005e3cc  test    eax, eax
0x14005e3ce  jle     short loc_14005E3DB
0x14005e3d0  movzx   r14d, ax
0x14005e3d4  or      r14d, 80070000h
0x14005e3db  mov     [rsp+778h+var_708], r15
0x14005e3e0  mov     [rsp+778h+var_700], r12
0x14005e3e5  mov     [rsp+778h+var_6F8], r13
0x14005e3ed  mov     [rsp+778h+var_6F0], 5CFh
0x14005e3f8  mov     [rsp+778h+var_6EC], 1
0x14005e403  mov     [rsp+778h+var_6E8], 0FFh
0x14005e40e  mov     [rsp+778h+var_668], 1000000h
0x14005e419  xor     edx, edx; Val
0x14005e41b  lea     r8d, [rdx+78h]; Size
0x14005e41f  lea     rcx, [rsp+778h+var_6E0]; void *
0x14005e427  call    memset_0
0x14005e42c  mov     dword ptr [rsp+778h+var_750], ebx
0x14005e430  lea     rax, [rsp+778h+szVolumeName]
0x14005e438  mov     [rsp+778h+var_758], rax
0x14005e43d  lea     r9, aGetvolumepathn_6; "GetVolumePathNamesForVolumeName(%s) fai"...
0x14005e444  mov     r8d, r14d
0x14005e447  lea     rdx, [rsp+778h+var_708]
0x14005e44c  lea     rcx, [rsp+778h+var_638]
0x14005e454  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x14005e459  or      rax, 0FFFFFFFFFFFFFFFFh
0x14005e45d  inc     rax
0x14005e460  cmp     [r14+rax*2], di
0x14005e465  jnz     short loc_14005E45D
0x14005e467  test    rax, rax
0x14005e46a  jz      loc_14005E523
0x14005e470  mov     rcx, r14; lpszVolumeMountPoint
0x14005e473  call    cs:__imp_DeleteVolumeMountPointW
0x14005e479  test    eax, eax
0x14005e47b  jnz     loc_14005E507
0x14005e481  call    cs:__imp_GetLastError
0x14005e487  mov     ebx, eax
0x14005e489  mov     [rsp+778h+var_708], r15
0x14005e48e  mov     [rsp+778h+var_700], r12
0x14005e493  mov     [rsp+778h+var_6F8], r13
0x14005e49b  mov     [rsp+778h+var_6F0], 5DBh
0x14005e4a6  mov     [rsp+778h+var_6EC], 1
0x14005e4b1  mov     [rsp+778h+var_6E8], 0FFh
0x14005e4bc  mov     [rsp+778h+var_668], 1000000h
0x14005e4c7  xor     edx, edx; Val
0x14005e4c9  lea     r8d, [rdx+78h]; Size
0x14005e4cd  lea     rcx, [rsp+778h+var_6E0]; void *
0x14005e4d5  call    memset_0
0x14005e4da  mov     dword ptr [rsp+778h+var_750], ebx
0x14005e4de  lea     rax, [rsp+778h+szVolumeName]
0x14005e4e6  mov     [rsp+778h+var_758], rax
0x14005e4eb  mov     r9, r14
0x14005e4ee  lea     r8, aFailToDeleteMo; "Fail to delete mount point %s for volum"...
0x14005e4f5  lea     rdx, [rsp+778h+var_708]
0x14005e4fa  lea     rcx, [rsp+778h+var_638]
0x14005e502  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14005e507  or      rax, 0FFFFFFFFFFFFFFFFh
0x14005e50b  inc     rax
0x14005e50e  cmp     [r14+rax*2], di
0x14005e513  jnz     short loc_14005E50B
0x14005e515  lea     r14, [r14+rax*2]
0x14005e519  add     r14, 2
0x14005e51d  jnz     loc_14005E459
0x14005e523  mov     rbx, [rsp+778h+lpszVolumeMountPoint]
0x14005e528  mov     [rsp+778h+var_720], rbx
0x14005e52d  or      rax, 0FFFFFFFFFFFFFFFFh
0x14005e531  inc     rax
0x14005e534  cmp     [rbx+rax*2], di
0x14005e538  jnz     short loc_14005E531
0x14005e53a  test    rax, rax
0x14005e53d  jz      loc_14005E6F5
0x14005e543  lea     rdx, [rsp+778h+szVolumeName]; lpszVolumeName
0x14005e54b  mov     rcx, rbx; lpszVolumeMountPoint
0x14005e54e  call    cs:__imp_SetVolumeMountPointW
0x14005e554  test    eax, eax
0x14005e556  jnz     loc_14005E6D5
0x14005e55c  mov     [rsp+778h+var_708], r15
0x14005e561  mov     [rsp+778h+var_700], r12
0x14005e566  mov     [rsp+778h+var_6F8], r13
0x14005e56e  mov     [rsp+778h+var_6F0], 5EBh
0x14005e579  mov     [rsp+778h+var_6EC], 6
0x14005e584  mov     r14d, 0FFh
0x14005e58a  mov     [rsp+778h+var_6E8], r14d
0x14005e592  mov     [rsp+778h+var_668], 1000000h
0x14005e59d  xor     edx, edx; Val
0x14005e59f  lea     r8d, [rax+78h]; Size
0x14005e5a3  lea     rcx, [rsp+778h+var_6E0]; void *
0x14005e5ab  call    memset_0
0x14005e5b0  mov     r8, rbx
0x14005e5b3  lea     rdx, [rsp+778h+var_508]; this
0x14005e5bb  lea     rcx, [rsp+778h+var_708]; struct CVssDebugInfo *
0x14005e5c0  call    ??6CVssDebugInfo@@QEAA?AU0@PEBG@Z; CVssDebugInfo::operator<<(ushort const *)
0x14005e5c5  lea     r8, [rsp+778h+szVolumeName]
0x14005e5cd  lea     rdx, [rsp+778h+var_5B0]; this
0x14005e5d5  mov     rcx, rax; struct CVssDebugInfo *
0x14005e5d8  call    ??6CVssDebugInfo@@QEAA?AU0@PEBG@Z; CVssDebugInfo::operator<<(ushort const *)
0x14005e5dd  mov     rbx, rax
0x14005e5e0  call    cs:__imp_GetLastError
0x14005e5e6  mov     r8d, eax
0x14005e5e9  lea     rdx, [rsp+778h+var_248]; this
0x14005e5f1  mov     rcx, rbx; struct CVssDebugInfo *
0x14005e5f4  call    ??6CVssDebugInfo@@QEAA?AU0@_J@Z; CVssDebugInfo::operator<<(__int64)
0x14005e5f9  mov     r9d, 1
0x14005e5ff  mov     r8, rax
0x14005e602  mov     edx, 3041h
0x14005e607  lea     rcx, [rsp+778h+var_638]
0x14005e60f  call    ?LogError@CVssFunctionTracer@@QEAAXKUCVssDebugInfo@@G@Z; CVssFunctionTracer::LogError(ulong,CVssDebugInfo,ushort)
0x14005e614  lea     rcx, [rsp+778h+var_5B0]; this
0x14005e61c  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14005e621  lea     rcx, [rsp+778h+var_508]; this
0x14005e629  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14005e62e  lea     rcx, [rsp+778h+var_708]; this
0x14005e633  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14005e638  call    cs:__imp_GetLastError
0x14005e63e  mov     ebx, eax
0x14005e640  test    eax, eax
0x14005e642  jle     short loc_14005E64D
0x14005e644  movzx   ebx, ax
0x14005e647  or      ebx, 80070000h
0x14005e64d  mov     [rsp+778h+var_708], r15
0x14005e652  mov     [rsp+778h+var_700], r12
0x14005e657  mov     [rsp+778h+var_6F8], r13
0x14005e65f  mov     [rsp+778h+var_6F0], 5EDh
0x14005e66a  mov     [rsp+778h+var_6EC], 6
0x14005e675  mov     [rsp+778h+var_6E8], r14d
0x14005e67d  mov     [rsp+778h+var_668], 1000000h
0x14005e688  xor     edx, edx; Val
0x14005e68a  lea     r8d, [rdx+78h]; Size
0x14005e68e  lea     rcx, [rsp+778h+var_6E0]; void *
0x14005e696  call    memset_0
  ... truncated ...
```
