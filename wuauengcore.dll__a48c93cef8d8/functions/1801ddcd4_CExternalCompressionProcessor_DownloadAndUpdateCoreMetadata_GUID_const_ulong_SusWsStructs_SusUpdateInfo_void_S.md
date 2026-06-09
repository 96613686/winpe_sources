# CExternalCompressionProcessor::DownloadAndUpdateCoreMetadata(_GUID const &,ulong,SusWsStructs::SusUpdateInfo *,void *,SusWsStructs::SusGetFileLocationsResults const &,CExternalCompressionProcessorError *,COptimizedUpdatesInfo &,ulong *)

- ea: `0x1801ddcd4`
- end: `0x1801de80d`
- name: `?DownloadAndUpdateCoreMetadata@CExternalCompressionProcessor@@AEAAJAEBU_GUID@@KPEAUSusUpdateInfo@SusWsStructs@@PEAXAEBUSusGetFileLocationsResults@4@PEAVCExternalCompressionProcessorError@@AEAVCOptimizedUpdatesInfo@@PEAK@Z`
- size: `2873`
- prototype: `__int64 __fastcall(CExternalCompressionProcessor *__hidden this, const struct _GUID *, unsigned int, struct SusWsStructs::SusUpdateInfo *, void *, const struct SusWsStructs::SusGetFileLocationsResults *, struct CExternalCompressionProcessorError *, struct COptimizedUpdatesInfo *, unsigned int *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1801dc904`

## callees

- `0x18000def4`
- `0x180014964`
- `0x18010dc60`
- `0x18010e010`
- `0x18010e3f8`
- `0x18010e454`
- `0x180113ae8`
- `0x18012264c`
- `0x18012372c`
- `0x180123c38`
- `0x18012b618`
- `0x18012d944`
- `0x18012d9d4`
- `0x1801dc740`
- `0x1801dc780`
- `0x1801dd24c`
- `0x1801ddc7c`
- `0x1801ddcd4`
- `0x1801de814`
- `0x180238960`
- `0x180238984`
- `0x180239110`
- `0x180241100`
- `0x180241780`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dddf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dde0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dddf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dde0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801dddc1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801dddc1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801ddd87`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801ddd87`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x1801de7bf`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x1801de7bf`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x1801dddea`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x1801dddea`
- `OLEAUT32!__imp_SysFreeString` at `0x1801de2cf`
- `OLEAUT32!__imp_SysFreeString` at `0x1801de2cf`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1801de355`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1801de355`

## string_xrefs

- `0x1801ddd79`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x1801de05c`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x1801ddf90`: `C:\__w\1\s\src\Client\Engine\ExternalCab\ExternalCompressionProcessorError.cpp`
- `0x1801de72b`: `C:\__w\1\s\src\Client\Engine\ExternalCab\ExternalCompressionProcessorError.cpp`
- `0x1801ddeda`: `C:\__w\1\s\src\Client\Engine\ExternalCab\ExternalCompressionProcessor.cpp`
- `0x1801de481`: `C:\__w\1\s\src\Client\Engine\ExternalCab\ExternalCompressionProcessor.cpp`
- `0x1801de4d1`: `C:\__w\1\s\src\Client\Engine\ExternalCab\ExternalCompressionProcessor.cpp`
- `0x1801de4f8`: `C:\__w\1\s\src\Client\Engine\ExternalCab\ExternalCompressionProcessor.cpp`
- `0x1801de54c`: `C:\__w\1\s\src\Client\Engine\ExternalCab\ExternalCompressionProcessor.cpp`
- `0x1801de5ab`: `C:\__w\1\s\src\Client\Engine\ExternalCab\ExternalCompressionProcessor.cpp`
- `0x1801de5c5`: `C:\__w\1\s\src\Client\Engine\ExternalCab\ExternalCompressionProcessor.cpp`
- `0x1801de66e`: `C:\__w\1\s\src\Client\Engine\ExternalCab\ExternalCompressionProcessor.cpp`
- `0x1801ddd95`: `ECPFailOptimizedUpdateDownloadAtIndex`
- `0x1801de49f`: `ECP: Update core metadata failed due to invalid file encoding`
- `0x1801de253`: `Successfully decompressed file. Compressed file size = %d, decompressed file size = %d`
- `0x1801de579`: `ECP: failed to get list of decompressed files`
- `0x1801de789`: `ECP: This roundtrip contained some optimized updates which failed. New Update count = %lu, Old Count = %lu`
- `0x1801de509`: `ECP: Failed to update optimized core metadata`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CExternalCompressionProcessor::DownloadAndUpdateCoreMetadata(
        CExternalCompressionProcessor *this,
        const struct _GUID *a2,
        unsigned int a3,
        struct SusWsStructs::SusUpdateInfo *a4,
        void *a5,
        const struct SusWsStructs::SusGetFileLocationsResults *a6,
        struct CExternalCompressionProcessorError *a7,
        struct COptimizedUpdatesInfo *a8,
        unsigned int *a9)
{
  const struct SusWsStructs::SusGetFileLocationsResults *v10; // r12
  struct COptimizedUpdatesInfo *v11; // r13
  signed int v12; // esi
  unsigned int v13; // ebx
  int v14; // r15d
  signed int LastError; // eax
  unsigned __int64 v16; // rcx
  signed int v17; // eax
  __int64 v18; // rax
  COutputMemoryFile *v19; // rdi
  unsigned int v20; // r14d
  char *v21; // rcx
  __int64 v22; // rax
  const void *v23; // r13
  __int64 v24; // rsi
  __int64 v25; // r15
  size_t v26; // r12
  const void **v27; // rbx
  struct CExternalCompressionProcessorError *v28; // r14
  HKEY v29; // rbx
  CExternalCompressionCabDownloadInfo *v30; // rax
  CExternalCompressionCabDownloadInfo *v31; // rdi
  int v32; // eax
  int v33; // ebx
  HKEY v34; // rbx
  int v35; // r14d
  char *v36; // r13
  __int64 v37; // rcx
  __int64 v38; // rax
  const WCHAR *v39; // rbx
  unsigned int v40; // r12d
  const unsigned __int8 *v41; // r15
  __int64 v42; // rax
  __int64 v43; // rdx
  CExternalCompressionProcessor *v44; // rcx
  void *v45; // rbx
  int v46; // r9d
  int v47; // eax
  void *v48; // rbx
  int v49; // eax
  __int64 v50; // rdx
  __int64 v51; // r12
  BSTR *v52; // r15
  _BYTE *v53; // rbx
  unsigned int v54; // r14d
  int v55; // eax
  unsigned int v56; // esi
  UINT v57; // r14d
  BSTR v58; // rax
  void *v59; // rbx
  __int64 v60; // rdx
  void *v61; // rbx
  unsigned int *v62; // rdi
  unsigned int v63; // ebx
  HKEY v64; // rbx
  void **phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  int phkResultc; // [rsp+20h] [rbp-E0h]
  int *v70; // [rsp+30h] [rbp-D0h]
  unsigned __int8 **v71; // [rsp+38h] [rbp-C8h]
  int v72; // [rsp+50h] [rbp-B0h]
  int v73; // [rsp+50h] [rbp-B0h]
  unsigned int v74; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v75; // [rsp+58h] [rbp-A8h] BYREF
  int v76; // [rsp+5Ch] [rbp-A4h] BYREF
  int v77; // [rsp+60h] [rbp-A0h]
  const struct SusWsStructs::SusGetFileLocationsResults *v78; // [rsp+68h] [rbp-98h]
  unsigned int v79; // [rsp+70h] [rbp-90h]
  COutputMemoryFile *v80; // [rsp+78h] [rbp-88h] BYREF
  struct COptimizedUpdatesInfo *v81; // [rsp+80h] [rbp-80h]
  void *v82; // [rsp+88h] [rbp-78h]
  __int64 v83; // [rsp+90h] [rbp-70h]
  __int64 v84; // [rsp+98h] [rbp-68h]
  struct SusWsStructs::SusUpdateInfo *v85; // [rsp+A0h] [rbp-60h]
  const struct _GUID *v86; // [rsp+A8h] [rbp-58h]
  CExternalCompressionProcessor *v87; // [rsp+B0h] [rbp-50h]
  struct CExternalCompressionProcessorError *v88; // [rsp+B8h] [rbp-48h]
  unsigned int *v89; // [rsp+C0h] [rbp-40h]
  HKEY hKey; // [rsp+C8h] [rbp-38h] BYREF
  void *v91; // [rsp+D0h] [rbp-30h] BYREF
  void *lpMem[2]; // [rsp+D8h] [rbp-28h] BYREF
  DWORD dwDataLen[2]; // [rsp+E8h] [rbp-18h]
  unsigned int v94; // [rsp+F0h] [rbp-10h] BYREF
  HCRYPTPROV phProv; // [rsp+F8h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v85 = a4;
  v79 = a3;
  v86 = a2;
  v87 = this;
  v82 = a5;
  v10 = a6;
  v78 = a6;
  v88 = a7;
  v11 = a8;
  v81 = a8;
  v89 = a9;
  v12 = 0;
  v94 = 0;
  v13 = *((_DWORD *)a8 + 3);
  hKey = 0;
  v14 = 0;
  v72 = 0;
  if ( (unsigned int)AreTestKeysAllowed(1)
    && !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
          0,
          0x20019u,
          &hKey) )
  {
    if ( !RegQueryDwordValue(hKey, L"ECPFailOptimizedUpdateDownloadAtIndex", &v94) )
    {
      v14 = 1;
      v72 = 1;
      if ( v94 >= v13 )
        v94 = v13 - 1;
    }
    RegCloseKey(hKey);
  }
  hKey = 0;
  phProv = 0;
  if ( !CryptAcquireContextW(&phProv, 0, 0, 0x18u, 0xF0000040) )
  {
    LastError = GetLastError();
    v16 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v16 = (unsigned int)LastError;
    if ( (v16 & 0x80000000) == 0LL )
    {
      v12 = -2147467259;
    }
    else
    {
      v17 = GetLastError();
      v12 = (unsigned __int16)v17 | 0x80070000;
      if ( v17 <= 0 )
        v12 = v17;
    }
    goto LABEL_79;
  }
  *a9 = a3;
  v18 = 0;
  v77 = 0;
  if ( !*((_DWORD *)a8 + 3) )
    goto LABEL_109;
LABEL_16:
  lpMem[0] = (void *)&CSafeBuffer<unsigned char>::`vftable';
  lpMem[1] = 0;
  *(_QWORD *)dwDataLen = 0;
  v19 = 0;
  v80 = 0;
  v20 = 0;
  if ( v14 && v94 == (_DWORD)v18 )
  {
    v12 = -2145844844;
    LODWORD(v70) = v18;
    WUTrace(0, 0, 8, 5, 0, L"ECP: Test key forces download for the external cab #%lu to fail", v70);
LABEL_77:
    WUTrace(
      0,
      0,
      8,
      5,
      v12,
      L"ECP: Failed to download cab file from %ws",
      *(_QWORD *)(88LL * v20 + *(_QWORD *)v10 + 16));
    goto LABEL_78;
  }
  v83 = v18;
  v21 = (char *)(16 * v18);
  v91 = v21;
  v22 = *((_QWORD *)v11 + 2);
  v23 = *(const void **)&v21[v22 + 8];
  v24 = 0;
  if ( *((int *)v10 + 2) <= 0 )
  {
LABEL_22:
    v12 = -2145107915;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5DC,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\ExternalCab\\ExternalCompressionProcessor.cpp",
      (const char *)0x80244035LL,
      (int)phkResult);
    WUTrace(0, 0, 8, 5, -2145107915, L"ECP: Failed to find matching file location");
LABEL_23:
    lpMem[0] = (void *)&CSafeBuffer<unsigned char>::`vftable';
    SusFree(lpMem[1]);
    goto LABEL_24;
  }
  v25 = *((int *)v10 + 2);
  v26 = *(unsigned int *)&v21[v22];
  v27 = (const void **)(*(_QWORD *)v78 + 8LL);
  while ( memcmp(v23, *v27, v26) )
  {
    ++v20;
    ++v24;
    v27 += 11;
    if ( v24 >= v25 )
      goto LABEL_22;
  }
  v34 = hKey;
  if ( hKey )
  {
    CExternalCompressionCabDownloadInfo::~CExternalCompressionCabDownloadInfo((CExternalCompressionCabDownloadInfo *)hKey);
    operator delete(v34, (const struct std::nothrow_t *)0x18);
    hKey = 0;
  }
  v84 = 88LL * v20;
  v10 = v78;
  phkResult = lpMem;
  v12 = CExternalCompressionProcessor::DownloadCabFile(v87, v86, *(_QWORD *)(*(_QWORD *)v78 + v84 + 16), v82);
  if ( v12 < 0 )
    goto LABEL_77;
  v35 = 0;
  v36 = (char *)v91;
  while ( 1 )
  {
    if ( v35 == 1
      && (unsigned int)AreTestKeysAllowed(1)
      && (unsigned int)RegQueryDwordValueWithDefaultAndRangeCheck(
                         v37,
                         L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
                         L"AllowSHA1ContentHash",
                         0,
                         0,
                         -1) )
    {
      WUTrace(0, 0, 32, 4, 0, L" Using Test Override: %ws", L"AllowSHA1ContentHash");
LABEL_52:
      v45 = v82;
      if ( !CExternalCompressionProcessor::ShouldContinue(v44, v82) )
      {
        v12 = -2145124341;
        lpMem[0] = (void *)&CSafeBuffer<unsigned char>::`vftable';
        SusFree(lpMem[1]);
        goto LABEL_109;
      }
      v91 = 0;
      v47 = DecompressCabFile((unsigned int)lpMem, 0, 0, v46, (__int64)v45, (__int64)&v91);
      v12 = v47;
      if ( v47 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1ED,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\ExternalCab\\ExternalCompressionProcessor.cpp",
          (const char *)(unsigned int)v47,
          phkResulta);
        v59 = v91;
        if ( v91 )
        {
          CSusListIterator<COutputMemoryFile>::~CSusListIterator<COutputMemoryFile>(v91);
          operator delete(v59, (const struct std::nothrow_t *)0x28);
        }
        goto LABEL_91;
      }
      v48 = v91;
      if ( !v91 )
      {
        WUTrace(0, 0, 8, 5, 0, L"ECP: failed to get list of decompressed files");
        v12 = -2145107916;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x200,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\ExternalCab\\ExternalCompressionProcessor.cpp",
          (const char *)0x80244034LL,
          phkResultc);
        goto LABEL_91;
      }
      *((_QWORD *)v91 + 4) = *((_QWORD *)v91 + 1);
      v49 = CSusListIterator<LockLocation>::Remove(v48, &v80);
      v12 = v49;
      if ( v49 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1FA,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\ExternalCab\\ExternalCompressionProcessor.cpp",
          (const char *)(unsigned int)v49,
          phkResulta);
        CSusListIterator<COutputMemoryFile>::~CSusListIterator<COutputMemoryFile>(v48);
        operator delete(v48, (const struct std::nothrow_t *)0x28);
        v19 = v80;
LABEL_91:
        WUTrace(
          0,
          0,
          8,
          5,
          v12,
          L"ECP: Failed to expand cab file downloaded from %ws",
          *(_QWORD *)(*(_QWORD *)v78 + v84 + 16));
        if ( !v19 )
          goto LABEL_78;
LABEL_86:
        COutputMemoryFile::~COutputMemoryFile(v19);
        operator delete(v19, (const struct std::nothrow_t *)0x120);
        goto LABEL_78;
      }
      v19 = v80;
      WUTrace(0, 0, 8, 5, 0, L"Successfully decompressed file. Compressed file size = %d, decompressed file size = %d");
      CSusListIterator<COutputMemoryFile>::~CSusListIterator<COutputMemoryFile>(v48);
      operator delete(v48, (const struct std::nothrow_t *)0x28);
      v50 = *((_QWORD *)v19 + 2);
      v11 = v81;
      v51 = v83;
      v52 = (BSTR *)((char *)v85 + 272 * *(unsigned int *)(*((_QWORD *)v81 + 3) + 4 * v83));
      v53 = *(_BYTE **)(v50 + 8);
      v54 = *(_DWORD *)(v50 + 20);
      *(_QWORD *)(v50 + 8) = 0;
      *(_QWORD *)(v50 + 16) = 0;
      if ( !v53 )
      {
        v12 = -2145107918;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x21E,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\ExternalCab\\ExternalCompressionProcessor.cpp",
          (const char *)0x80244032LL,
          (int)phkResult);
        goto LABEL_85;
      }
      SysFreeString(v52[28]);
      if ( v54 <= 2 )
        goto LABEL_83;
      if ( *(_WORD *)v53 == 0xFEFF )
      {
        v55 = 2;
      }
      else
      {
        if ( *(_WORD *)v53 != 0xFFFE )
        {
          if ( *v53 == 0xEF && v53[1] == 0xBB && v53[2] == 0xBF || v54 <= 4 )
          {
LABEL_83:
            WUTrace(0, 0, 8, 5, 0, L"ECP: Update core metadata failed due to invalid file encoding");
            v12 = -2145107919;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x235,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\ExternalCab\\ExternalCompressionProcessor.cpp",
              (const char *)0x80244031LL,
              phkResultb);
            SusFree(v53);
LABEL_85:
            WUTrace(0, 0, 8, 5, v12, L"ECP: Failed to update optimized core metadata");
            goto LABEL_86;
          }
          if ( *(_DWORD *)v53 == -131072 )
          {
            v55 = 4;
          }
          else
          {
            if ( *(_DWORD *)v53 != 65279 )
              goto LABEL_83;
            v55 = 5;
          }
          v56 = 4;
          goto LABEL_72;
        }
        v55 = 3;
      }
      v56 = 2;
LABEL_72:
      if ( v55 != 2 )
        goto LABEL_83;
      v57 = v54 - v56;
      v58 = SysAllocStringByteLen(0, v57);
      v52[28] = v58;
      if ( !v58 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x246,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\ExternalCab\\ExternalCompressionProcessor.cpp",
          (const char *)0x8007000ELL,
          (int)phkResult);
        SusFree(v53);
        v12 = -2147024882;
        goto LABEL_85;
      }
      memmove(v58, &v53[v56], v57);
      SusFree(v53);
      v12 = 0;
      *(_DWORD *)(*((_QWORD *)v11 + 4) + 4 * v51) = 1;
      COutputMemoryFile::~COutputMemoryFile(v19);
      operator delete(v19, (const struct std::nothrow_t *)0x120);
      lpMem[0] = (void *)&CSafeBuffer<unsigned char>::`vftable';
      SusFree(lpMem[1]);
      v18 = (unsigned int)(v77 + 1);
      v77 = v18;
      if ( (unsigned int)v18 >= *((_DWORD *)v11 + 3) )
        goto LABEL_109;
      v10 = v78;
      v14 = v72;
      goto LABEL_16;
    }
    v38 = *((_QWORD *)v81 + 5);
    v39 = *(const WCHAR **)(v38 + 24 * v83 + 16);
    v40 = *(_DWORD *)(v38 + 24 * v83);
    v41 = *(const unsigned __int8 **)(v38 + 24 * v83 + 8);
    v42 = *((_QWORD *)v81 + 2);
    if ( v35 == 1 )
    {
      if ( !v41 || !v39 )
      {
        v43 = 231;
LABEL_98:
        v12 = -2145099773;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v43,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\DigestSelector.cpp",
          (const char *)0x80246003LL,
          (int)phkResult);
        goto LABEL_23;
      }
    }
    else
    {
      if ( !*(_QWORD *)&v36[v42 + 8] )
      {
        v43 = 244;
        goto LABEL_98;
      }
      v40 = *(_DWORD *)&v36[v42];
      v41 = *(const unsigned __int8 **)&v36[v42 + 8];
      v39 = L"SHA1";
    }
    if ( v35 == 1 )
    {
      v74 = 0;
      v75 = 0;
      v12 = SelectAlgId(L"SHA1", &v74);
      if ( v12 < 0 )
        goto LABEL_78;
      v12 = SelectAlgId(v39, &v75);
      if ( v12 < 0 )
        goto LABEL_78;
      LODWORD(v91) = 0;
      v76 = 0;
      if ( (int)HashAlgFamilyFromAlgId(v74, (enum HashingAlgorithmFamily *)&v91) < 0
        || (int)HashAlgFamilyFromAlgId(v75, (enum HashingAlgorithmFamily *)&v76) < 0
        || (_DWORD)v91 == v76 )
      {
        v12 = -2145099774;
        goto LABEL_23;
      }
    }
    LODWORD(v91) = 0;
    v12 = ValidateMemoryFile((BYTE *)lpMem[1], dwDataLen[1], phProv, v39, v41, v40, (int *)&v91, 0, 0);
    if ( v12 < 0 )
      break;
    if ( !(_DWORD)v91 )
    {
      v12 = -2146889721;
      v60 = 464;
      goto LABEL_96;
    }
    if ( ++v35 >= 2 )
      goto LABEL_52;
  }
  v60 = 462;
LABEL_96:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v60,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\ExternalCab\\ExternalCompressionProcessor.cpp",
    (const char *)(unsigned int)v12,
    (int)phkResult);
  HIDWORD(v71) = HIDWORD(v39);
  v70 = *(int **)(*(_QWORD *)v78 + v84 + 16);
  WUTrace(0, 0, 8, 5, v12, L"ECP: Failed to validate cab file digest downloaded from %ws, algorithm: %ws");
LABEL_78:
  lpMem[0] = (void *)&CSafeBuffer<unsigned char>::`vftable';
  SusFree(lpMem[1]);
LABEL_79:
  if ( v12 == -2147467260 )
  {
    v12 = -2145124341;
    goto LABEL_109;
  }
  if ( v12 && v12 != -2145124341 )
  {
LABEL_24:
    v28 = v88;
    *(_DWORD *)v88 = v12;
    v29 = hKey;
    if ( hKey )
    {
      v30 = (CExternalCompressionCabDownloadInfo *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
      v31 = v30;
      if ( v30 )
      {
        *(_QWORD *)v30 = 0;
        *((_DWORD *)v30 + 2) = 0;
        *((_QWORD *)v30 + 2) = 0;
        v32 = CExternalCompressionCabDownloadInfo::Initialize(
                v30,
                *(const wchar_t **)v29,
                *((_DWORD *)v29 + 2),
                *((const wchar_t **)v29 + 2));
        v73 = v32;
        if ( v32 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x6D,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\ExternalCab\\ExternalCompressionProcessorError.cpp",
            (const char *)(unsigned int)v32,
            (int)phkResult);
          CExternalCompressionCabDownloadInfo::~CExternalCompressionCabDownloadInfo(v31);
          operator delete(v31, (const struct std::nothrow_t *)0x18);
          v33 = v73;
          goto LABEL_106;
        }
        v61 = (void *)*((_QWORD *)v28 + 1);
        if ( v61 )
        {
          CExternalCompressionCabDownloadInfo::~CExternalCompressionCabDownloadInfo(*((CExternalCompressionCabDownloadInfo **)v28
                                                                                    + 1));
          operator delete(v61, (const struct std::nothrow_t *)0x18);
        }
        *((_QWORD *)v28 + 1) = v31;
      }
      else
      {
        v33 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x69,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\ExternalCab\\ExternalCompressionProcessorError.cpp",
          (const char *)0x8007000ELL,
          (int)phkResult);
LABEL_106:
        WUTrace(0, 0, 8, 5, v33, L"ECP: failed to assign cab download info for error reporting");
      }
    }
    v62 = v89;
    v63 = v79;
    v12 = CExternalCompressionProcessor::RearrangeUpdates((CExternalCompressionProcessor *)v16, v79, v85, v81, v89);
    if ( v12 >= 0 )
    {
      LODWORD(v71) = v63;
      LODWORD(v70) = *v62;
      WUTrace(
        0,
        0,
        8,
        5,
        0,
        L"ECP: This roundtrip contained some optimized updates which failed. New Update count = %lu, Old Count = %lu",
        v70,
        v71);
      v12 = -2145107921;
    }
  }
LABEL_109:
  if ( phProv )
  {
    CryptReleaseContext(phProv, 0);
    phProv = 0;
  }
  v64 = hKey;
  if ( hKey )
  {
    CExternalCompressionCabDownloadInfo::~CExternalCompressionCabDownloadInfo((CExternalCompressionCabDownloadInfo *)hKey);
    operator delete(v64, (const struct std::nothrow_t *)0x18);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1801ddcd4  push    rbp
0x1801ddcd6  push    rbx
0x1801ddcd7  push    rsi
0x1801ddcd8  push    rdi
0x1801ddcd9  push    r12
0x1801ddcdb  push    r13
0x1801ddcdd  push    r14
0x1801ddcdf  push    r15
0x1801ddce1  lea     rbp, [rsp-18h]
0x1801ddce6  sub     rsp, 118h
0x1801ddced  mov     rax, cs:__security_cookie
0x1801ddcf4  xor     rax, rsp
0x1801ddcf7  mov     [rbp+50h+var_50], rax
0x1801ddcfb  mov     [rbp+50h+var_B0], r9
0x1801ddcff  mov     edi, r8d
0x1801ddd02  mov     [rsp+150h+var_E0], r8d
0x1801ddd07  mov     [rbp+50h+var_A8], rdx
0x1801ddd0b  mov     [rbp+50h+var_A0], rcx
0x1801ddd0f  mov     rax, [rbp+50h+arg_20]
0x1801ddd16  mov     [rbp+50h+var_C8], rax
0x1801ddd1a  mov     r12, [rbp+50h+arg_28]
0x1801ddd21  mov     [rsp+150h+var_E8], r12
0x1801ddd26  mov     rax, [rbp+50h+arg_30]
0x1801ddd2d  mov     [rbp+50h+var_98], rax
0x1801ddd31  mov     r13, [rbp+50h+arg_38]
0x1801ddd38  mov     [rbp+50h+var_D0], r13
0x1801ddd3c  mov     r14, [rbp+50h+arg_40]
0x1801ddd43  mov     [rbp+50h+var_90], r14
0x1801ddd47  xor     esi, esi
0x1801ddd49  mov     [rbp+50h+var_60], esi
0x1801ddd4c  mov     ebx, [r13+0Ch]
0x1801ddd50  mov     [rbp+50h+hKey], rsi
0x1801ddd54  xor     r15d, r15d
0x1801ddd57  mov     [rsp+150h+var_100], r15d
0x1801ddd5c  mov     cl, 1; bool
0x1801ddd5e  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x1801ddd63  test    eax, eax
0x1801ddd65  jz      short loc_1801DDDC7
0x1801ddd67  lea     rax, [rbp+50h+hKey]
0x1801ddd6b  mov     [rsp+150h+phkResult], rax; phkResult
0x1801ddd70  mov     r9d, 20019h; samDesired
0x1801ddd76  xor     r8d, r8d; ulOptions
0x1801ddd79  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801ddd80  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801ddd87  call    cs:__imp_RegOpenKeyExW
0x1801ddd8d  test    eax, eax
0x1801ddd8f  jnz     short loc_1801DDDC7
0x1801ddd91  lea     r8, [rbp+50h+var_60]; unsigned int *
0x1801ddd95  lea     rdx, aEcpfailoptimiz; "ECPFailOptimizedUpdateDownloadAtIndex"
0x1801ddd9c  mov     rcx, [rbp+50h+hKey]; HKEY
0x1801ddda0  call    ?RegQueryDwordValue@@YAJPEAUHKEY__@@PEB_WPEAK@Z; RegQueryDwordValue(HKEY__ *,wchar_t const *,ulong *)
0x1801ddda5  test    eax, eax
0x1801ddda7  jnz     short loc_1801DDDBD
0x1801ddda9  lea     r15d, [rsi+1]
0x1801dddad  mov     [rsp+150h+var_100], r15d
0x1801dddb2  cmp     [rbp+50h+var_60], ebx
0x1801dddb5  jb      short loc_1801DDDBD
0x1801dddb7  lea     eax, [rbx-1]
0x1801dddba  mov     [rbp+50h+var_60], eax
0x1801dddbd  mov     rcx, [rbp+50h+hKey]; hKey
0x1801dddc1  call    cs:__imp_RegCloseKey
0x1801dddc7  mov     [rbp+50h+hKey], rsi
0x1801dddcb  mov     [rbp+50h+phProv], 0
0x1801dddd3  mov     dword ptr [rsp+150h+phkResult], 0F0000040h; int
0x1801ddddb  mov     r9d, 18h; dwProvType
0x1801ddde1  xor     r8d, r8d; szProvider
0x1801ddde4  xor     edx, edx; szContainer
0x1801ddde6  lea     rcx, [rbp+50h+phProv]; phProv
0x1801dddea  call    cs:__imp_CryptAcquireContextW
0x1801dddf0  test    eax, eax
0x1801dddf2  jnz     short loc_1801DDE2C
0x1801dddf4  call    cs:__imp_GetLastError
0x1801dddfa  movzx   ecx, ax
0x1801dddfd  mov     ebx, 80070000h
0x1801dde02  or      ecx, ebx
0x1801dde04  test    eax, eax
0x1801dde06  cmovle  ecx, eax
0x1801dde09  test    ecx, ecx
0x1801dde0b  jns     short loc_1801DDE22
0x1801dde0d  call    cs:__imp_GetLastError
0x1801dde13  movzx   esi, ax
0x1801dde16  or      esi, ebx
0x1801dde18  test    eax, eax
0x1801dde1a  cmovle  esi, eax
0x1801dde1d  jmp     loc_1801DE454
0x1801dde22  mov     esi, 80004005h
0x1801dde27  jmp     loc_1801DE454
0x1801dde2c  mov     [r14], edi
0x1801dde2f  xor     eax, eax
0x1801dde31  mov     [rsp+150h+var_F0], eax
0x1801dde35  cmp     [r13+0Ch], eax
0x1801dde39  jbe     loc_1801DE7B4
0x1801dde3f  lea     rdx, ??_7?$CSafeBuffer@E@@6B@; const CSafeBuffer<uchar>::`vftable'
0x1801dde46  xorps   xmm0, xmm0
0x1801dde49  xor     ecx, ecx
0x1801dde4b  movups  xmmword ptr [rbp+50h+lpMem], xmm0
0x1801dde4f  mov     [rbp+50h+lpMem], rdx
0x1801dde53  mov     [rbp+50h+lpMem+8], rcx
0x1801dde57  mov     qword ptr [rbp+50h+dwDataLen], rcx
0x1801dde5b  mov     edi, ecx
0x1801dde5d  mov     [rsp+150h+var_D8], rcx
0x1801dde62  mov     r14d, ecx
0x1801dde65  test    r15d, r15d
0x1801dde68  jz      short loc_1801DDE73
0x1801dde6a  cmp     [rbp+50h+var_60], eax
0x1801dde6d  jz      loc_1801DE3DE
0x1801dde73  mov     [rbp+50h+var_C0], rax
0x1801dde77  mov     rcx, rax
0x1801dde7a  shl     rcx, 4
0x1801dde7e  mov     [rbp+50h+var_80], rcx
0x1801dde82  mov     rax, [r13+10h]
0x1801dde86  mov     r13, [rcx+rax+8]
0x1801dde8b  xor     esi, esi
0x1801dde8d  cmp     [r12+8], esi
0x1801dde92  jle     short loc_1801DDECE
0x1801dde94  movsxd  r15, dword ptr [r12+8]
0x1801dde99  mov     r12d, [rcx+rax]
0x1801dde9d  mov     rcx, [rsp+150h+var_E8]
0x1801ddea2  mov     rbx, [rcx]
0x1801ddea5  add     rbx, 8
0x1801ddea9  mov     r8, r12; Size
0x1801ddeac  mov     rdx, [rbx]; Buf2
0x1801ddeaf  mov     rcx, r13; Buf1
0x1801ddeb2  call    memcmp
0x1801ddeb7  test    eax, eax
0x1801ddeb9  jz      loc_1801DDFBA
0x1801ddebf  inc     r14d
0x1801ddec2  inc     rsi
0x1801ddec5  add     rbx, 58h ; 'X'
0x1801ddec9  cmp     rsi, r15
0x1801ddecc  jl      short loc_1801DDEA9
0x1801ddece  mov     rcx, [rbp+58h]; this
0x1801dded2  mov     esi, 80244035h
0x1801dded7  mov     r9d, esi; char *
0x1801ddeda  lea     r8, aCW1SSrcClientE_98; "C:\\__w\\1\\s\\src\\Client\\Engine\\Ext"...
0x1801ddee1  mov     edx, 5DCh; void *
0x1801ddee6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ddeeb  lea     rax, aEcpFailedToFin; "ECP: Failed to find matching file locat"...
0x1801ddef2  mov     qword ptr [rsp+150h+var_128], rax
0x1801ddef7  mov     dword ptr [rsp+150h+phkResult], esi; int
0x1801ddefb  xor     edx, edx
0x1801ddefd  xor     ecx, ecx
0x1801ddeff  lea     r9d, [rdx+5]
0x1801ddf03  lea     r8d, [rdx+8]
0x1801ddf07  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801ddf0c  nop
0x1801ddf0d  lea     rax, ??_7?$CSafeBuffer@E@@6B@; const CSafeBuffer<uchar>::`vftable'
0x1801ddf14  mov     [rbp+50h+lpMem], rax
0x1801ddf18  mov     rcx, [rbp+50h+lpMem+8]; lpMem
0x1801ddf1c  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1801ddf21  mov     r14, [rbp+50h+var_98]
0x1801ddf25  mov     [r14], esi
0x1801ddf28  mov     rbx, [rbp+50h+hKey]
0x1801ddf2c  test    rbx, rbx
0x1801ddf2f  jz      loc_1801DE75D
0x1801ddf35  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801ddf3c  mov     esi, 18h
0x1801ddf41  mov     ecx, esi; unsigned __int64
0x1801ddf43  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1801ddf48  mov     rdi, rax
0x1801ddf4b  test    rax, rax
0x1801ddf4e  jz      loc_1801DE71F
0x1801ddf54  mov     qword ptr [rax], 0
0x1801ddf5b  mov     dword ptr [rax+8], 0
0x1801ddf62  mov     qword ptr [rax+10h], 0
0x1801ddf6a  mov     r9, [rbx+10h]; wchar_t *
0x1801ddf6e  mov     r8d, [rbx+8]; unsigned int
0x1801ddf72  mov     rdx, [rbx]; wchar_t *
0x1801ddf75  mov     rcx, rax; this
0x1801ddf78  call    ?Initialize@CExternalCompressionCabDownloadInfo@@QEAAJPEB_WK0@Z; CExternalCompressionCabDownloadInfo::Initialize(wchar_t const *,ulong,wchar_t const *)
0x1801ddf7d  mov     [rsp+150h+var_100], eax
0x1801ddf81  test    eax, eax
0x1801ddf83  jns     loc_1801DE6FD
0x1801ddf89  mov     rcx, [rbp+58h]; this
0x1801ddf8d  mov     r9d, eax; char *
0x1801ddf90  lea     r8, aCW1SSrcClientE_62; "C:\\__w\\1\\s\\src\\Client\\Engine\\Ext"...
0x1801ddf97  lea     edx, [rsi+55h]; void *
0x1801ddf9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ddf9f  mov     rcx, rdi; this
0x1801ddfa2  call    ??1CExternalCompressionCabDownloadInfo@@QEAA@XZ; CExternalCompressionCabDownloadInfo::~CExternalCompressionCabDownloadInfo(void)
0x1801ddfa7  mov     edx, esi; struct std::nothrow_t *
0x1801ddfa9  mov     rcx, rdi; void *
0x1801ddfac  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801ddfb1  mov     ebx, [rsp+150h+var_100]
0x1801ddfb5  jmp     loc_1801DE73C
0x1801ddfba  mov     rbx, [rbp+50h+hKey]
0x1801ddfbe  test    rbx, rbx
0x1801ddfc1  jz      short loc_1801DDFE0
0x1801ddfc3  mov     rcx, rbx; this
0x1801ddfc6  call    ??1CExternalCompressionCabDownloadInfo@@QEAA@XZ; CExternalCompressionCabDownloadInfo::~CExternalCompressionCabDownloadInfo(void)
0x1801ddfcb  mov     edx, 18h; struct std::nothrow_t *
0x1801ddfd0  mov     rcx, rbx; void *
0x1801ddfd3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801ddfd8  mov     [rbp+50h+hKey], 0
0x1801ddfe0  mov     eax, r14d
0x1801ddfe3  imul    r15, rax, 58h ; 'X'
0x1801ddfe7  mov     [rbp+50h+var_B8], r15
0x1801ddfeb  mov     r12, [rsp+150h+var_E8]
0x1801ddff0  mov     r8, [r12]
0x1801ddff4  lea     rax, [rbp+50h+hKey]
0x1801ddff8  mov     qword ptr [rsp+150h+var_128], rax
0x1801ddffd  lea     rax, [rbp+50h+lpMem]
0x1801de001  mov     [rsp+150h+phkResult], rax
0x1801de006  mov     r9, [rbp+50h+var_C8]
0x1801de00a  mov     r8, [r8+r15+10h]
0x1801de00f  mov     rdx, [rbp+50h+var_A8]
0x1801de013  mov     rcx, [rbp+50h+var_A0]
0x1801de017  call    ?DownloadCabFile@CExternalCompressionProcessor@@AEAAJAEBU_GUID@@PEB_WPEAXAEAV?$CSafeBuffer@E@@PEAPEAVCExternalCompressionCabDownloadInfo@@@Z; CExternalCompressionProcessor::DownloadCabFile(_GUID const &,wchar_t const *,void *,CSafeBuffer<uchar> &,CExternalCompressionCabDownloadInfo * *)
0x1801de01c  mov     esi, eax
0x1801de01e  test    eax, eax
0x1801de020  js      loc_1801DE409
0x1801de026  xor     r14d, r14d
0x1801de029  mov     r13, [rbp+50h+var_80]
0x1801de02d  cmp     r14d, 1
0x1801de031  jnz     short loc_1801DE070
0x1801de033  mov     cl, r14b; bool
0x1801de036  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x1801de03b  test    eax, eax
0x1801de03d  jz      short loc_1801DE070
0x1801de03f  mov     [rsp+150h+var_128], 0FFFFFFFFh
0x1801de047  mov     dword ptr [rsp+150h+phkResult], 0; int
0x1801de04f  xor     r9d, r9d
0x1801de052  lea     rbx, ?c_szAllowSHA1ContentHashTestKeyName@@3QB_WB; "AllowSHA1ContentHash"
0x1801de059  mov     r8, rbx
0x1801de05c  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801de063  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x1801de068  test    eax, eax
0x1801de06a  jnz     loc_1801DE1A3
0x1801de070  mov     rax, [rbp+50h+var_C0]
0x1801de074  lea     rcx, [rax+rax*2]
0x1801de078  mov     rdx, [rbp+50h+var_D0]
0x1801de07c  mov     rax, [rdx+28h]
0x1801de080  mov     rbx, [rax+rcx*8+10h]
0x1801de085  mov     r12d, [rax+rcx*8]
0x1801de089  mov     r15, [rax+rcx*8+8]
0x1801de08e  mov     rax, [rdx+10h]
0x1801de092  mov     rcx, [rax+r13+8]
0x1801de097  cmp     r14d, 1
0x1801de09b  jnz     short loc_1801DE0B3
0x1801de09d  xor     esi, esi
0x1801de09f  test    r15, r15
0x1801de0a2  jz      short loc_1801DE0A9
0x1801de0a4  test    rbx, rbx
0x1801de0a7  jnz     short loc_1801DE0CC
0x1801de0a9  mov     edx, 0E7h
0x1801de0ae  jmp     loc_1801DE6C6
0x1801de0b3  test    rcx, rcx
0x1801de0b6  jz      loc_1801DE6C1
0x1801de0bc  mov     r12d, [rax+r13]
0x1801de0c0  mov     r15, rcx
0x1801de0c3  lea     rbx, ?c_szSha1HashAlgorithm@@3QB_WB; "SHA1"
0x1801de0ca  xor     esi, esi
0x1801de0cc  cmp     r14d, 1
0x1801de0d0  jnz     short loc_1801DE14D
0x1801de0d2  mov     [rsp+150h+var_FC], esi
0x1801de0d6  mov     [rsp+150h+var_F8], esi
0x1801de0da  lea     rdx, [rsp+150h+var_FC]; unsigned int *
0x1801de0df  lea     rcx, ?c_szSha1HashAlgorithm@@3QB_WB; "SHA1"
0x1801de0e6  call    ?SelectAlgId@@YAJPEB_WPEAI@Z; SelectAlgId(wchar_t const *,uint *)
0x1801de0eb  mov     esi, eax
0x1801de0ed  test    eax, eax
0x1801de0ef  js      loc_1801DE440
0x1801de0f5  lea     rdx, [rsp+150h+var_F8]; unsigned int *
0x1801de0fa  mov     rcx, rbx; lpString2
0x1801de0fd  call    ?SelectAlgId@@YAJPEB_WPEAI@Z; SelectAlgId(wchar_t const *,uint *)
0x1801de102  mov     esi, eax
0x1801de104  test    eax, eax
0x1801de106  js      loc_1801DE440
0x1801de10c  xor     esi, esi
0x1801de10e  mov     dword ptr [rbp+50h+var_80], esi
0x1801de111  mov     [rsp+150h+var_F4], esi
0x1801de115  lea     rdx, [rbp+50h+var_80]; enum HashingAlgorithmFamily *
0x1801de119  mov     ecx, [rsp+150h+var_FC]; unsigned int
0x1801de11d  call    ?HashAlgFamilyFromAlgId@@YAJIAEAW4HashingAlgorithmFamily@@@Z; HashAlgFamilyFromAlgId(uint,HashingAlgorithmFamily &)
0x1801de122  test    eax, eax
0x1801de124  js      loc_1801DE46A
0x1801de12a  lea     rdx, [rsp+150h+var_F4]; enum HashingAlgorithmFamily *
0x1801de12f  mov     ecx, [rsp+150h+var_F8]; unsigned int
0x1801de133  call    ?HashAlgFamilyFromAlgId@@YAJIAEAW4HashingAlgorithmFamily@@@Z; HashAlgFamilyFromAlgId(uint,HashingAlgorithmFamily &)
0x1801de138  test    eax, eax
0x1801de13a  js      loc_1801DE46A
0x1801de140  mov     eax, [rsp+150h+var_F4]
0x1801de144  cmp     dword ptr [rbp+50h+var_80], eax
0x1801de147  jz      loc_1801DE46A
0x1801de14d  mov     dword ptr [rbp+50h+var_80], esi
0x1801de150  mov     [rsp+150h+var_110], rsi; unsigned int *
0x1801de155  mov     [rsp+150h+var_118], rsi; unsigned __int8 **
0x1801de15a  lea     rax, [rbp+50h+var_80]
0x1801de15e  mov     [rsp+150h+var_120], rax; int *
0x1801de163  mov     [rsp+150h+var_128], r12d; unsigned int
0x1801de168  mov     [rsp+150h+phkResult], r15; int
0x1801de16d  mov     r9, rbx; lpString2
0x1801de170  mov     r8, [rbp+50h+phProv]; hProv
0x1801de174  mov     edx, [rbp+50h+dwDataLen+4]; dwDataLen
0x1801de177  mov     rcx, [rbp+50h+lpMem+8]; pbData
0x1801de17b  call    ?ValidateMemoryFile@@YAJPEBEI_KPEB_W0KPEAHPEAPEAEPEAK@Z; ValidateMemoryFile(uchar const *,uint,unsigned __int64,wchar_t const *,uchar const *,ulong,int *,uchar * *,ulong *)
0x1801de180  mov     esi, eax
0x1801de182  test    eax, eax
0x1801de184  js      loc_1801DE666
0x1801de18a  cmp     dword ptr [rbp+50h+var_80], 0
  ... truncated ...
```
