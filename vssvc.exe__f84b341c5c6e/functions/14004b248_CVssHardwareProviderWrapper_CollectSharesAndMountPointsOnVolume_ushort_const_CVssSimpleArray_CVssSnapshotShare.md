# CVssHardwareProviderWrapper::CollectSharesAndMountPointsOnVolume(ushort const *,CVssSimpleArray<CVssSnapshotShareInfo> &,_SHARE_INFO_502 * &,ushort * &)

- ea: `0x14004b248`
- end: `0x14004ba14`
- name: `?CollectSharesAndMountPointsOnVolume@CVssHardwareProviderWrapper@@AEAAXPEBGAEAV?$CVssSimpleArray@UCVssSnapshotShareInfo@@@@AEAPEAU_SHARE_INFO_502@@AEAPEAG@Z`
- size: `1996`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, reparse_path`

## callers

- `0x140063f60`

## callees

- `0x14000e640`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013b00`
- `0x140025b00`
- `0x14003a8f0`
- `0x14003ade4`
- `0x14003d54c`
- `0x14003eedc`
- `0x14003fc04`
- `0x140049ec4`
- `0x14004b248`
- `0x140091560`
- `0x1400921dc`
- `0x1400921e8`
- `0x1400b21e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004b941`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004b941`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b41f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b430`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b523`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b629`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b7a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b83a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b8c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b41f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b430`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b523`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b629`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b7a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b83a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b8c4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14004b4ca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14004b4ca`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x14004b798`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x14004b798`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14004b61b`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14004b830`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14004b8ba`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14004b61b`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14004b830`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14004b8ba`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x14004b419`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x14004b50b`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x14004b419`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x14004b50b`
- `srvcli!NetShareEnum` at `0x14004b6ec`
- `srvcli!NetShareEnum` at `0x14004b6ec`

## string_xrefs

- `0x14004b295`: `CVssHardwareProviderWrapper::CollectSharesAndMountPointsOnVolume`
- `0x14004b445`: `CVssHardwareProviderWrapper::CollectSharesAndMountPointsOnVolume`
- `0x14004b53f`: `CVssHardwareProviderWrapper::CollectSharesAndMountPointsOnVolume`
- `0x14004b645`: `CVssHardwareProviderWrapper::CollectSharesAndMountPointsOnVolume`
- `0x14004b703`: `CVssHardwareProviderWrapper::CollectSharesAndMountPointsOnVolume`
- `0x14004b7be`: `CVssHardwareProviderWrapper::CollectSharesAndMountPointsOnVolume`
- `0x14004b856`: `CVssHardwareProviderWrapper::CollectSharesAndMountPointsOnVolume`
- `0x14004b8e0`: `CVssHardwareProviderWrapper::CollectSharesAndMountPointsOnVolume`
- `0x14004b28a`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x14004b534`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x14004b63a`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x14004b6f8`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x14004b7b3`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x14004b84b`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x14004b8d5`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x14004b499`: `GetVolumePathNamesForVolumeName(%s) failed with 0x%08lx`
- `0x14004b58a`: `GetVolumePathNamesForVolumeName(%s) failed with 0x%08lx`
- `0x14004b691`: `GetVolumeNameForVolumeMountPoint(%s)`
- `0x14004b802`: `GetVolumePathName(%s) failed with 0x%08lx`
- `0x14004b89d`: `GetVolumeNameForVolumeMountPoint(%s) fails with 0x%08lx`
- `0x14004b927`: `GetVolumeNameForVolumeMountPoint(%s) fail with 0x%08lx`
- `0x14004b371`: `StringCchCopy fails to copy volume name`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CVssHardwareProviderWrapper::CollectSharesAndMountPointsOnVolume(
        __int64 a1,
        const unsigned __int16 *a2,
        __int64 a3,
        LPBYTE *a4,
        WCHAR **a5)
{
  int v7; // r15d
  __int64 v8; // rax
  signed int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rbx
  WCHAR *v12; // rax
  WCHAR *v13; // rbx
  signed int LastError; // eax
  unsigned int v15; // ebx
  signed int v16; // eax
  unsigned int v17; // ebx
  DWORD v18; // ebx
  LPBYTE v19; // r12
  BYTE *v20; // r14
  signed int v21; // eax
  unsigned int v22; // ebx
  WCHAR *v23; // r9
  const wchar_t *v24; // r8
  signed int v25; // eax
  signed int v26; // eax
  int v27; // eax
  LPBYTE v28; // rax
  LPDWORD entriesread; // [rsp+20h] [rbp-E0h]
  DWORD cchReturnLength[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v31; // [rsp+50h] [rbp-B0h] BYREF
  __int64 pExceptionObject; // [rsp+58h] [rbp-A8h] BYREF
  void **v33; // [rsp+60h] [rbp-A0h] BYREF
  LPBYTE bufptr; // [rsp+68h] [rbp-98h] BYREF
  void **v35; // [rsp+70h] [rbp-90h] BYREF
  WCHAR *v36; // [rsp+78h] [rbp-88h]
  DWORD totalentries[4]; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v38; // [rsp+90h] [rbp-70h] BYREF
  int v39; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v40; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v41[4]; // [rsp+108h] [rbp+8h] BYREF
  const unsigned __int16 *v42; // [rsp+110h] [rbp+10h]
  int v43; // [rsp+118h] [rbp+18h]
  int v44; // [rsp+11Ch] [rbp+1Ch]
  int v45; // [rsp+120h] [rbp+20h]
  _BYTE v46[120]; // [rsp+128h] [rbp+28h] BYREF
  int v47; // [rsp+1A0h] [rbp+A0h]
  WCHAR szVolumeName[264]; // [rsp+310h] [rbp+210h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+520h] [rbp+420h] BYREF
  WCHAR szVolumeMountPoint[264]; // [rsp+730h] [rbp+630h] BYREF
  WCHAR v51[264]; // [rsp+940h] [rbp+840h] BYREF
  WCHAR v52[264]; // [rsp+B50h] [rbp+A50h] BYREF

  pExceptionObject = a3;
  v40 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
  *(_QWORD *)v41 = L"CVssHardwareProviderWrapper::CollectSharesAndMountPointsOnVolume";
  v42 = L"CORHDELC";
  v43 = 1002;
  v44 = 1;
  v45 = 255;
  v7 = 0;
  v47 = 0x1000000;
  memset_0(v46, 0, sizeof(v46));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v38, (__int64)&v40, 0);
  cchReturnLength[0] = 0;
  memset_0(szVolumeName, 0, 0x208u);
  v36 = 0;
  v35 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
  v39 = StringCchCopyW(szVolumeName, 0x104u, a2);
  v40 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
  *(_QWORD *)v41 = L"CVssHardwareProviderWrapper::CollectSharesAndMountPointsOnVolume";
  v42 = L"CORHDELC";
  v43 = 1013;
  v44 = 1;
  v45 = 255;
  v47 = 0x1000000;
  memset_0(v46, 0, sizeof(v46));
  CVssFunctionTracer::CheckForErrorInternal(&v38, &v40, L"StringCchCopy fails to copy volume name");
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  if ( a2[v8 - 1] != 92 )
  {
    v39 = StringCchCatW(szVolumeName, 0x104u, L"\\");
    v40 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
    *(_QWORD *)v41 = L"CVssHardwareProviderWrapper::CollectSharesAndMountPointsOnVolume";
    v42 = L"CORHDELC";
    v43 = 1020;
    v44 = 1;
    v45 = 255;
    v47 = 0x1000000;
    memset_0(v46, 0, sizeof(v46));
    CVssFunctionTracer::CheckForErrorInternal(&v38, &v40, L"StringCchCat fails to concat backslash");
  }
  GetVolumePathNamesForVolumeNameW(szVolumeName, 0, 0, cchReturnLength);
  if ( GetLastError() == 234 )
  {
    v11 = cchReturnLength[0];
    CVssAutoGenericValue_Storage<unsigned short *,0,void * (*)(void *),&void * LocalFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close(&v35);
    v12 = (WCHAR *)LocalAlloc(0, 2 * v11 + 2);
    v13 = v12;
    v36 = v12;
    if ( !v12 )
    {
      LODWORD(pExceptionObject) = -2147024882;
      throw (long *)&pExceptionObject;
    }
    if ( GetVolumePathNamesForVolumeNameW(szVolumeName, v12, cchReturnLength[0], cchReturnLength) )
    {
      v36 = 0;
    }
    else
    {
      LastError = GetLastError();
      v15 = LastError;
      if ( LastError > 0 )
        v15 = (unsigned __int16)LastError | 0x80070000;
      v40 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      *(_QWORD *)v41 = L"CVssHardwareProviderWrapper::CollectSharesAndMountPointsOnVolume";
      v42 = L"CORHDELC";
      v43 = 1041;
      v44 = 6;
      v45 = 255;
      v47 = 0x1000000;
      memset_0(v46, 0, sizeof(v46));
      CVssFunctionTracer::Trace(
        &v38,
        &v40,
        L"GetVolumePathNamesForVolumeName(%s) failed with 0x%08lx",
        szVolumeName,
        v15);
      CVssAutoGenericValue_Storage<unsigned short *,0,void * (*)(void *),&void * LocalFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close(&v35);
      v13 = 0;
    }
    *a5 = v13;
    v31 = 0;
    totalentries[0] = 0;
    memset_0(szVolumePathName, 0, 0x208u);
    memset_0(szVolumeMountPoint, 0, 0x208u);
    memset_0(v52, 0, 0x208u);
    memset_0(v51, 0, 0x208u);
    if ( !GetVolumeNameForVolumeMountPointW(szVolumeName, v51, 0x104u) )
    {
      v16 = GetLastError();
      v17 = v16;
      if ( v16 > 0 )
        v17 = (unsigned __int16)v16 | 0x80070000;
      v40 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      *(_QWORD *)v41 = L"CVssHardwareProviderWrapper::CollectSharesAndMountPointsOnVolume";
      v42 = L"CORHDELC";
      v43 = 1063;
      v44 = 6;
      v45 = 255;
      v47 = 0x1000000;
      memset_0(v46, 0, sizeof(v46));
      CVssFunctionTracer::TranslateGenericError(&v38, &v40, v17, L"GetVolumeNameForVolumeMountPoint(%s)", szVolumeName);
    }
    bufptr = 0;
    v33 = &CVssAuto<unsigned char *,CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>>::`vftable';
    CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>::Close(&v33);
    v18 = NetShareEnum(0, 0x1F6u, &bufptr, 0xFFFFFFFF, &v31, totalentries, 0);
    if ( v18 )
    {
      v40 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      *(_QWORD *)v41 = L"CVssHardwareProviderWrapper::CollectSharesAndMountPointsOnVolume";
      v42 = L"CORHDELC";
      v43 = 1080;
      v44 = 6;
      v45 = 255;
      v47 = 0x1000000;
      memset_0(v46, 0, sizeof(v46));
      CVssFunctionTracer::Trace(&v38, &v40, L"NetShareEnum failed with %d", v18);
LABEL_41:
      v28 = bufptr;
      bufptr = 0;
      *a4 = v28;
      CVssAuto<unsigned char *,CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>>::~CVssAuto<unsigned char *,CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>>(&v33);
      goto LABEL_42;
    }
    v19 = bufptr;
    if ( !v31 )
      goto LABEL_41;
    while ( 1 )
    {
      v20 = &v19[72 * v7];
      if ( !*((_DWORD *)v20 + 2) )
      {
        if ( GetVolumePathNameW(*((LPCWSTR *)v20 + 5), szVolumePathName, 0x104u) )
        {
          if ( GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeMountPoint, 0x104u) )
          {
            if ( GetVolumeNameForVolumeMountPointW(szVolumeMountPoint, v52, 0x104u) )
            {
              if ( !(unsigned int)_o__wcsicmp(v52, v51) )
              {
                v40 = (const unsigned __int16 *)&v19[72 * v7];
                v27 = StringCchCopyW(v41, 0x104u, szVolumePathName);
                if ( v27 < 0 )
                {
                  LODWORD(pExceptionObject) = v27;
                  throw (long *)&pExceptionObject;
                }
                if ( !(unsigned int)ATL::CSimpleArray<CVssSnapshotShareInfo,ATL::CSimpleArrayEqualHelper<CVssSnapshotShareInfo>>::Add(
                                      pExceptionObject,
                                      &v40) )
                {
                  LODWORD(pExceptionObject) = -2147024882;
                  throw (long *)&pExceptionObject;
                }
              }
              goto LABEL_40;
            }
            v26 = GetLastError();
            v22 = v26;
            if ( v26 > 0 )
              v22 = (unsigned __int16)v26 | 0x80070000;
            v40 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
            *(_QWORD *)v41 = L"CVssHardwareProviderWrapper::CollectSharesAndMountPointsOnVolume";
            v42 = L"CORHDELC";
            v43 = 1107;
            v44 = 6;
            v45 = 255;
            v47 = 0x1000000;
            memset_0(v46, 0, sizeof(v46));
            v23 = szVolumeMountPoint;
            v24 = L"GetVolumeNameForVolumeMountPoint(%s) fail with 0x%08lx";
          }
          else
          {
            v25 = GetLastError();
            v22 = v25;
            if ( v25 > 0 )
              v22 = (unsigned __int16)v25 | 0x80070000;
            v40 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
            *(_QWORD *)v41 = L"CVssHardwareProviderWrapper::CollectSharesAndMountPointsOnVolume";
            v42 = L"CORHDELC";
            v43 = 1103;
            v44 = 6;
            v45 = 255;
            v47 = 0x1000000;
            memset_0(v46, 0, sizeof(v46));
            v23 = szVolumePathName;
            v24 = L"GetVolumeNameForVolumeMountPoint(%s) fails with 0x%08lx";
          }
        }
        else
        {
          v21 = GetLastError();
          v22 = v21;
          if ( v21 > 0 )
            v22 = (unsigned __int16)v21 | 0x80070000;
          v40 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
          *(_QWORD *)v41 = L"CVssHardwareProviderWrapper::CollectSharesAndMountPointsOnVolume";
          v42 = L"CORHDELC";
          v43 = 1091;
          v44 = 6;
          v45 = 255;
          v47 = 0x1000000;
          memset_0(v46, 0, sizeof(v46));
          v23 = (WCHAR *)*((_QWORD *)v20 + 5);
          v24 = L"GetVolumePathName(%s) failed with 0x%08lx";
        }
        LODWORD(entriesread) = v22;
        CVssFunctionTracer::Trace(&v38, &v40, v24, v23, entriesread);
      }
LABEL_40:
      if ( ++v7 >= v31 )
        goto LABEL_41;
    }
  }
  v9 = GetLastError();
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  v40 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
  *(_QWORD *)v41 = L"CVssHardwareProviderWrapper::CollectSharesAndMountPointsOnVolume";
  v42 = L"CORHDELC";
  v43 = 1028;
  v44 = 6;
  v45 = 255;
  v47 = 0x1000000;
  memset_0(v46, 0, sizeof(v46));
  CVssFunctionTracer::Trace(&v38, &v40, L"GetVolumePathNamesForVolumeName(%s) failed with 0x%08lx", szVolumeName, v10);
LABEL_42:
  CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(&v35);
  CVssFunctionTracer::~CVssFunctionTracer(&v38);
}

```

## disassembly

```asm
0x14004b248  mov     [rsp-8+arg_0], rbx
0x14004b24d  push    rbp
0x14004b24e  push    rsi
0x14004b24f  push    rdi
0x14004b250  push    r12
0x14004b252  push    r13
0x14004b254  push    r14
0x14004b256  push    r15
0x14004b258  lea     rbp, [rsp-0C70h]
0x14004b260  sub     rsp, 0D70h
0x14004b267  mov     rax, cs:__security_cookie
0x14004b26e  xor     rax, rsp
0x14004b271  mov     [rbp+0CA0h+var_40], rax
0x14004b278  mov     r13, r9
0x14004b27b  mov     [rsp+0DA0h+pExceptionObject], r8
0x14004b280  mov     rbx, rdx
0x14004b283  mov     r14, [rbp+0CA0h+arg_20]
0x14004b28a  lea     rsi, aBaseStorVssMod_22; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x14004b291  mov     [rbp+0CA0h+var_CA0], rsi
0x14004b295  lea     rdi, aCvsshardwarepr_168; "CVssHardwareProviderWrapper::CollectSha"...
0x14004b29c  mov     qword ptr [rbp+0CA0h+var_C98], rdi
0x14004b2a0  lea     rax, aCorhdelc; "CORHDELC"
0x14004b2a7  mov     [rbp+0CA0h+var_C90], rax
0x14004b2ab  mov     [rbp+0CA0h+var_C88], 3EAh
0x14004b2b2  mov     r12d, 1
0x14004b2b8  mov     [rbp+0CA0h+var_C84], r12d
0x14004b2bc  mov     [rbp+0CA0h+var_C80], 0FFh
0x14004b2c3  xor     r15d, r15d
0x14004b2c6  mov     [rbp+0CA0h+var_C00], 1000000h
0x14004b2d0  xor     edx, edx; Val
0x14004b2d2  lea     r8d, [r12+77h]; Size
0x14004b2d7  lea     rcx, [rbp+0CA0h+var_C78]; void *
0x14004b2db  call    memset_0
0x14004b2e0  xor     r8d, r8d
0x14004b2e3  lea     rdx, [rbp+0CA0h+var_CA0]
0x14004b2e7  lea     rcx, [rbp+0CA0h+var_D10]
0x14004b2eb  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x14004b2f0  nop
0x14004b2f1  mov     [rsp+0DA0h+cchReturnLength], r15d
0x14004b2f6  xor     edx, edx; Val
0x14004b2f8  mov     r8d, 208h; Size
0x14004b2fe  lea     rcx, [rbp+0CA0h+szVolumeName]; void *
0x14004b305  call    memset_0
0x14004b30a  mov     [rsp+0DA0h+var_D28], r15
0x14004b30f  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x14004b316  mov     [rsp+0DA0h+var_D30], rax
0x14004b31b  mov     r8, rbx; unsigned __int16 *
0x14004b31e  mov     edx, 104h; unsigned __int64
0x14004b323  lea     rcx, [rbp+0CA0h+szVolumeName]; unsigned __int16 *
0x14004b32a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14004b32f  mov     [rbp+0CA0h+var_D08], eax
0x14004b332  mov     [rbp+0CA0h+var_CA0], rsi
0x14004b336  mov     qword ptr [rbp+0CA0h+var_C98], rdi
0x14004b33a  lea     rax, aCorhdelc; "CORHDELC"
0x14004b341  mov     [rbp+0CA0h+var_C90], rax
0x14004b345  mov     [rbp+0CA0h+var_C88], 3F5h
0x14004b34c  mov     [rbp+0CA0h+var_C84], r12d
0x14004b350  mov     [rbp+0CA0h+var_C80], 0FFh
0x14004b357  mov     [rbp+0CA0h+var_C00], 1000000h
0x14004b361  xor     edx, edx; Val
0x14004b363  lea     r8d, [r12+77h]; Size
0x14004b368  lea     rcx, [rbp+0CA0h+var_C78]; void *
0x14004b36c  call    memset_0
0x14004b371  lea     r8, aStringcchcopyF_4; "StringCchCopy fails to copy volume name"
0x14004b378  lea     rdx, [rbp+0CA0h+var_CA0]
0x14004b37c  lea     rcx, [rbp+0CA0h+var_D10]
0x14004b380  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x14004b385  or      rax, 0FFFFFFFFFFFFFFFFh
0x14004b389  inc     rax
0x14004b38c  cmp     [rbx+rax*2], r15w
0x14004b391  jnz     short loc_14004B389
0x14004b393  cmp     word ptr [rbx+rax*2-2], 5Ch ; '\'
0x14004b399  jz      short loc_14004B408
0x14004b39b  lea     r8, pszSrc; "\\"
0x14004b3a2  mov     edx, 104h; unsigned __int64
0x14004b3a7  lea     rcx, [rbp+0CA0h+szVolumeName]; unsigned __int16 *
0x14004b3ae  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14004b3b3  mov     [rbp+0CA0h+var_D08], eax
0x14004b3b6  mov     [rbp+0CA0h+var_CA0], rsi
0x14004b3ba  mov     qword ptr [rbp+0CA0h+var_C98], rdi
0x14004b3be  lea     rax, aCorhdelc; "CORHDELC"
0x14004b3c5  mov     [rbp+0CA0h+var_C90], rax
0x14004b3c9  mov     [rbp+0CA0h+var_C88], 3FCh
0x14004b3d0  mov     [rbp+0CA0h+var_C84], r12d
0x14004b3d4  mov     [rbp+0CA0h+var_C80], 0FFh
0x14004b3db  mov     [rbp+0CA0h+var_C00], 1000000h
0x14004b3e5  xor     edx, edx; Val
0x14004b3e7  lea     r8d, [rdx+78h]; Size
0x14004b3eb  lea     rcx, [rbp+0CA0h+var_C78]; void *
0x14004b3ef  call    memset_0
0x14004b3f4  lea     r8, aStringcchcatFa_1; "StringCchCat fails to concat backslash"
0x14004b3fb  lea     rdx, [rbp+0CA0h+var_CA0]
0x14004b3ff  lea     rcx, [rbp+0CA0h+var_D10]
0x14004b403  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x14004b408  lea     r9, [rsp+0DA0h+cchReturnLength]; lpcchReturnLength
0x14004b40d  xor     r8d, r8d; cchBufferLength
0x14004b410  xor     edx, edx; lpszVolumePathNames
0x14004b412  lea     rcx, [rbp+0CA0h+szVolumeName]; lpszVolumeName
0x14004b419  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x14004b41f  call    cs:__imp_GetLastError
0x14004b425  cmp     eax, 0EAh
0x14004b42a  jz      loc_14004B4B2
0x14004b430  call    cs:__imp_GetLastError
0x14004b436  mov     ebx, eax
0x14004b438  test    eax, eax
0x14004b43a  jle     short loc_14004B44C
0x14004b43c  movzx   ebx, ax
0x14004b43f  or      ebx, 80070000h
0x14004b445  lea     rdi, aCvsshardwarepr_168; "CVssHardwareProviderWrapper::CollectSha"...
0x14004b44c  mov     [rbp+0CA0h+var_CA0], rsi
0x14004b450  mov     qword ptr [rbp+0CA0h+var_C98], rdi
0x14004b454  lea     rax, aCorhdelc; "CORHDELC"
0x14004b45b  mov     [rbp+0CA0h+var_C90], rax
0x14004b45f  mov     [rbp+0CA0h+var_C88], 404h
0x14004b466  mov     esi, 6
0x14004b46b  mov     [rbp+0CA0h+var_C84], esi
0x14004b46e  mov     [rbp+0CA0h+var_C80], 0FFh
0x14004b475  mov     [rbp+0CA0h+var_C00], 1000000h
0x14004b47f  xor     edx, edx; Val
0x14004b481  lea     r8d, [rsi+72h]; Size
0x14004b485  lea     rcx, [rbp+0CA0h+var_C78]; void *
0x14004b489  call    memset_0
0x14004b48e  mov     dword ptr [rsp+0DA0h+entriesread], ebx
0x14004b492  lea     r9, [rbp+0CA0h+szVolumeName]
0x14004b499  lea     r8, aGetvolumepathn_0; "GetVolumePathNamesForVolumeName(%s) fai"...
0x14004b4a0  lea     rdx, [rbp+0CA0h+var_CA0]
0x14004b4a4  lea     rcx, [rbp+0CA0h+var_D10]
0x14004b4a8  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14004b4ad  jmp     loc_14004B9A6
0x14004b4b2  mov     ebx, [rsp+0DA0h+cchReturnLength]
0x14004b4b6  lea     rcx, [rsp+0DA0h+var_D30]
0x14004b4bb  call    ?Close@?$CVssAutoGenericValue_Storage@PEAG$0A@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZP6AAEAPEAGAEAPEAG@Z$1?Identity@?$DTyper@PEAG@@SAAEAPEAG1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<ushort *,0,void * (*)(void *),&LocalFree(void *),ushort * & (*)(ushort * &),&DTyper<ushort *>::Identity(ushort * &)>::Close(void)
0x14004b4c0  lea     rdx, ds:2[rbx*2]; uBytes
0x14004b4c8  xor     ecx, ecx; uFlags
0x14004b4ca  call    cs:__imp_LocalAlloc
0x14004b4d0  mov     rbx, rax
0x14004b4d3  mov     [rsp+0DA0h+var_D28], rax
0x14004b4d8  test    rax, rax
0x14004b4db  jnz     short loc_14004B4F7
0x14004b4dd  mov     dword ptr [rsp+0DA0h+pExceptionObject], 8007000Eh
0x14004b4e5  lea     rdx, _TI1J; pThrowInfo
0x14004b4ec  lea     rcx, [rsp+0DA0h+pExceptionObject]; pExceptionObject
0x14004b4f1  call    _CxxThrowException_0
0x14004b4f7  lea     r9, [rsp+0DA0h+cchReturnLength]; lpcchReturnLength
0x14004b4fc  mov     r8d, [rsp+0DA0h+cchReturnLength]; cchBufferLength
0x14004b501  mov     rdx, rax; lpszVolumePathNames
0x14004b504  lea     rcx, [rbp+0CA0h+szVolumeName]; lpszVolumeName
0x14004b50b  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x14004b511  mov     edi, 80070000h
0x14004b516  mov     esi, 6
0x14004b51b  test    eax, eax
0x14004b51d  jnz     loc_14004B5AD
0x14004b523  call    cs:__imp_GetLastError
0x14004b529  mov     ebx, eax
0x14004b52b  test    eax, eax
0x14004b52d  jle     short loc_14004B534
0x14004b52f  movzx   ebx, ax
0x14004b532  or      ebx, edi
0x14004b534  lea     rax, aBaseStorVssMod_22; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x14004b53b  mov     [rbp+0CA0h+var_CA0], rax
0x14004b53f  lea     rax, aCvsshardwarepr_168; "CVssHardwareProviderWrapper::CollectSha"...
0x14004b546  mov     qword ptr [rbp+0CA0h+var_C98], rax
0x14004b54a  lea     rax, aCorhdelc; "CORHDELC"
0x14004b551  mov     [rbp+0CA0h+var_C90], rax
0x14004b555  mov     [rbp+0CA0h+var_C88], 411h
0x14004b55c  mov     [rbp+0CA0h+var_C84], esi
0x14004b55f  mov     [rbp+0CA0h+var_C80], 0FFh
0x14004b566  mov     [rbp+0CA0h+var_C00], 1000000h
0x14004b570  xor     edx, edx; Val
0x14004b572  lea     r8d, [rdx+78h]; Size
0x14004b576  lea     rcx, [rbp+0CA0h+var_C78]; void *
0x14004b57a  call    memset_0
0x14004b57f  mov     dword ptr [rsp+0DA0h+entriesread], ebx
0x14004b583  lea     r9, [rbp+0CA0h+szVolumeName]
0x14004b58a  lea     r8, aGetvolumepathn_0; "GetVolumePathNamesForVolumeName(%s) fai"...
0x14004b591  lea     rdx, [rbp+0CA0h+var_CA0]
0x14004b595  lea     rcx, [rbp+0CA0h+var_D10]
0x14004b599  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14004b59e  lea     rcx, [rsp+0DA0h+var_D30]
0x14004b5a3  call    ?Close@?$CVssAutoGenericValue_Storage@PEAG$0A@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZP6AAEAPEAGAEAPEAG@Z$1?Identity@?$DTyper@PEAG@@SAAEAPEAG1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<ushort *,0,void * (*)(void *),&LocalFree(void *),ushort * & (*)(ushort * &),&DTyper<ushort *>::Identity(ushort * &)>::Close(void)
0x14004b5a8  mov     rbx, r15
0x14004b5ab  jmp     short loc_14004B5B2
0x14004b5ad  mov     [rsp+0DA0h+var_D28], r15
0x14004b5b2  mov     [r14], rbx
0x14004b5b5  mov     [rsp+0DA0h+var_D50], r15d
0x14004b5ba  mov     [rbp+0CA0h+var_D20], r15d
0x14004b5be  mov     ebx, 208h
0x14004b5c3  mov     r8d, ebx; Size
0x14004b5c6  xor     edx, edx; Val
0x14004b5c8  lea     rcx, [rbp+0CA0h+szVolumePathName]; void *
0x14004b5cf  call    memset_0
0x14004b5d4  mov     r8d, ebx; Size
0x14004b5d7  xor     edx, edx; Val
0x14004b5d9  lea     rcx, [rbp+0CA0h+szVolumeMountPoint]; void *
0x14004b5e0  call    memset_0
0x14004b5e5  mov     r8d, ebx; Size
0x14004b5e8  xor     edx, edx; Val
0x14004b5ea  lea     rcx, [rbp+0CA0h+var_250]; void *
0x14004b5f1  call    memset_0
0x14004b5f6  mov     r8d, ebx; Size
0x14004b5f9  xor     edx, edx; Val
0x14004b5fb  lea     rcx, [rbp+0CA0h+var_460]; void *
0x14004b602  call    memset_0
0x14004b607  mov     r8d, 104h; cchBufferLength
0x14004b60d  lea     rdx, [rbp+0CA0h+var_460]; lpszVolumeName
0x14004b614  lea     rcx, [rbp+0CA0h+szVolumeName]; lpszVolumeMountPoint
0x14004b61b  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x14004b621  test    eax, eax
0x14004b623  jnz     loc_14004B6A9
0x14004b629  call    cs:__imp_GetLastError
0x14004b62f  mov     ebx, eax
0x14004b631  test    eax, eax
0x14004b633  jle     short loc_14004B63A
0x14004b635  movzx   ebx, ax
0x14004b638  or      ebx, edi
0x14004b63a  lea     rax, aBaseStorVssMod_22; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x14004b641  mov     [rbp+0CA0h+var_CA0], rax
0x14004b645  lea     rax, aCvsshardwarepr_168; "CVssHardwareProviderWrapper::CollectSha"...
0x14004b64c  mov     qword ptr [rbp+0CA0h+var_C98], rax
0x14004b650  lea     rax, aCorhdelc; "CORHDELC"
0x14004b657  mov     [rbp+0CA0h+var_C90], rax
0x14004b65b  mov     [rbp+0CA0h+var_C88], 427h
0x14004b662  mov     [rbp+0CA0h+var_C84], esi
0x14004b665  mov     [rbp+0CA0h+var_C80], 0FFh
0x14004b66c  mov     [rbp+0CA0h+var_C00], 1000000h
0x14004b676  xor     edx, edx; Val
0x14004b678  lea     r8d, [rdx+78h]; Size
0x14004b67c  lea     rcx, [rbp+0CA0h+var_C78]; void *
0x14004b680  call    memset_0
0x14004b685  lea     rax, [rbp+0CA0h+szVolumeName]
0x14004b68c  mov     [rsp+0DA0h+entriesread], rax
0x14004b691  lea     r9, aGetvolumenamef_4; "GetVolumeNameForVolumeMountPoint(%s)"
0x14004b698  mov     r8d, ebx
0x14004b69b  lea     rdx, [rbp+0CA0h+var_CA0]
0x14004b69f  lea     rcx, [rbp+0CA0h+var_D10]
0x14004b6a3  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14004b6a9  mov     [rsp+0DA0h+bufptr], r15
0x14004b6ae  lea     rax, ??_7?$CVssAuto@PEAEV?$CVssAutoGenericValue_Storage@PEAE$0A@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZP6AAEAPEAEAEAPEAE@Z$1?Identity@?$DTyper@PEAE@@SAAEAPEAE1@Z@@@@6B@; const CVssAuto<uchar *,CVssAutoGenericValue_Storage<uchar *,0,ulong (*)(void *),&NetApiBufferFree(void *),uchar * & (*)(uchar * &),&DTyper<uchar *>::Identity(uchar * &)>>::`vftable'
0x14004b6b5  mov     [rsp+0DA0h+var_D40], rax
0x14004b6ba  lea     rcx, [rsp+0DA0h+var_D40]
0x14004b6bf  call    ?Close@?$CVssAutoGenericValue_Storage@PEAE$0A@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZP6AAEAPEAEAEAPEAE@Z$1?Identity@?$DTyper@PEAE@@SAAEAPEAE1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<uchar *,0,ulong (*)(void *),&NetApiBufferFree(void *),uchar * & (*)(uchar * &),&DTyper<uchar *>::Identity(uchar * &)>::Close(void)
0x14004b6c4  mov     [rsp+0DA0h+resume_handle], r15; resume_handle
0x14004b6c9  lea     rax, [rbp+0CA0h+var_D20]
0x14004b6cd  mov     [rsp+0DA0h+totalentries], rax; totalentries
0x14004b6d2  lea     rax, [rsp+0DA0h+var_D50]
0x14004b6d7  mov     [rsp+0DA0h+entriesread], rax; entriesread
0x14004b6dc  or      r9d, 0FFFFFFFFh; prefmaxlen
0x14004b6e0  lea     r8, [rsp+0DA0h+bufptr]; bufptr
0x14004b6e5  mov     edx, 1F6h; level
0x14004b6ea  xor     ecx, ecx; servername
0x14004b6ec  call    cs:__imp_NetShareEnum
0x14004b6f2  mov     ebx, eax
0x14004b6f4  test    eax, eax
0x14004b6f6  jz      short loc_14004B75F
0x14004b6f8  lea     rax, aBaseStorVssMod_22; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x14004b6ff  mov     [rbp+0CA0h+var_CA0], rax
0x14004b703  lea     rax, aCvsshardwarepr_168; "CVssHardwareProviderWrapper::CollectSha"...
0x14004b70a  mov     qword ptr [rbp+0CA0h+var_C98], rax
0x14004b70e  lea     rax, aCorhdelc; "CORHDELC"
0x14004b715  mov     [rbp+0CA0h+var_C90], rax
0x14004b719  mov     [rbp+0CA0h+var_C88], 438h
0x14004b720  mov     [rbp+0CA0h+var_C84], esi
0x14004b723  mov     [rbp+0CA0h+var_C80], 0FFh
0x14004b72a  mov     [rbp+0CA0h+var_C00], 1000000h
0x14004b734  xor     edx, edx; Val
0x14004b736  lea     r8d, [rdx+78h]; Size
0x14004b73a  lea     rcx, [rbp+0CA0h+var_C78]; void *
0x14004b73e  call    memset_0
0x14004b743  mov     r9d, ebx
0x14004b746  lea     r8, aNetshareenumFa; "NetShareEnum failed with %d"
0x14004b74d  lea     rdx, [rbp+0CA0h+var_CA0]
0x14004b751  lea     rcx, [rbp+0CA0h+var_D10]
0x14004b755  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14004b75a  jmp     loc_14004B98D
0x14004b75f  mov     r12, [rsp+0DA0h+bufptr]
0x14004b764  cmp     [rsp+0DA0h+var_D50], 0
0x14004b769  jbe     loc_14004B98A
0x14004b76f  mov     eax, r15d
0x14004b772  lea     rcx, [rax+rax*8]
0x14004b776  lea     r14, [r12+rcx*8]
0x14004b77a  cmp     dword ptr [r14+8], 0
0x14004b77f  jnz     loc_14004B97C
0x14004b785  mov     ebx, 104h
0x14004b78a  mov     r8d, ebx; cchBufferLength
0x14004b78d  lea     rdx, [rbp+0CA0h+szVolumePathName]; lpszVolumePathName
0x14004b794  mov     rcx, [r14+28h]; lpszFileName
0x14004b798  call    cs:__imp_GetVolumePathNameW
0x14004b79e  test    eax, eax
0x14004b7a0  jnz     short loc_14004B81F
0x14004b7a2  call    cs:__imp_GetLastError
0x14004b7a8  mov     ebx, eax
0x14004b7aa  test    eax, eax
0x14004b7ac  jle     short loc_14004B7B3
0x14004b7ae  movzx   ebx, ax
0x14004b7b1  or      ebx, edi
0x14004b7b3  lea     rax, aBaseStorVssMod_22; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x14004b7ba  mov     [rbp+0CA0h+var_CA0], rax
0x14004b7be  lea     rax, aCvsshardwarepr_168; "CVssHardwareProviderWrapper::CollectSha"...
0x14004b7c5  mov     qword ptr [rbp+0CA0h+var_C98], rax
0x14004b7c9  lea     rax, aCorhdelc; "CORHDELC"
  ... truncated ...
```
