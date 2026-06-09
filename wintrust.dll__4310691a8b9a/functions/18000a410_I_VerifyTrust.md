# I_VerifyTrust

- ea: `0x18000a410`
- end: `0x18000b498`
- name: `I_VerifyTrust`
- size: `4232`
- prototype: `__int64 __fastcall(HWND, struct _GUID *, HKEY, void *, DWORD *, _DWORD *)`
- caller_count: `7`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800020fc`
- `0x18000a2a4`
- `0x18000a380`
- `0x18000b6a8`
- `0x18000bae0`
- `0x18000c12c`
- `0x180025750`

## callees

- `0x180008fc0`
- `0x180009420`
- `0x18000a410`
- `0x18000e2a0`
- `0x18000f050`
- `0x180013f60`
- `0x180014490`
- `0x18001d650`
- `0x18001e810`
- `0x18002e590`
- `0x18002e5d0`
- `0x18002e5dc`
- `0x18003813c`
- `0x180039540`
- `0x18004de52`
- `0x18004de6a`
- `0x18004deb0`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a99e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a99e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18000a7ee`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18000a7ee`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000a893`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000a8a8`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000a893`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000a8a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ab89`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b282`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b3be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b466`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ab89`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b282`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b3be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b466`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a7cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b450`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a7cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b450`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a7a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a7a6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x18000a63a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x18000a63a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000a5ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000a6cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000a5ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000a6cb`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x18000a6a8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x18000a6a8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000aca5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000aca5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ac54`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ac54`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a728`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a748`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a960`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a972`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ac6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000acb3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000acbe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a728`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a748`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a960`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a972`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ac6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000acb3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000acbe`
- `CRYPTSP!CryptAcquireContextA` at `0x18000ab49`
- `CRYPTSP!CryptAcquireContextA` at `0x18000ab49`
- `CRYPT32!I_CryptReadTrustedPublisherDWORDValueFromRegistry` at `0x18000ad98`
- `CRYPT32!I_CryptReadTrustedPublisherDWORDValueFromRegistry` at `0x18000ad98`
- `CRYPT32!I_CertDiagControl` at `0x18000ade9`
- `CRYPT32!I_CertDiagControl` at `0x18000b1c1`
- `CRYPT32!I_CertDiagControl` at `0x18000ade9`
- `CRYPT32!I_CertDiagControl` at `0x18000b1c1`
- `CRYPT32!I_CryptRemoveLruEntry` at `0x18000a8bb`
- `CRYPT32!I_CryptRemoveLruEntry` at `0x18000a8bb`
- `CRYPT32!I_CryptReleaseLruEntry` at `0x18000a8c5`
- `CRYPT32!I_CryptReleaseLruEntry` at `0x18000b443`
- `CRYPT32!I_CryptReleaseLruEntry` at `0x18000a8c5`
- `CRYPT32!I_CryptReleaseLruEntry` at `0x18000b443`
- `CRYPT32!I_CryptFindLruEntryData` at `0x18000a85f`
- `CRYPT32!I_CryptFindLruEntryData` at `0x18000a85f`
- `CRYPT32!I_CryptInsertLruEntry` at `0x18000b3dd`
- `CRYPT32!I_CryptInsertLruEntry` at `0x18000b3dd`
- `CRYPT32!I_CryptCreateLruEntry` at `0x18000af31`
- `CRYPT32!I_CryptCreateLruEntry` at `0x18000af31`
- `CRYPT32!I_CryptFlushLruCache` at `0x18000a7c0`
- `CRYPT32!I_CryptFlushLruCache` at `0x18000a7c0`
- `CRYPT32!CertOIDToAlgId` at `0x18000b245`
- `CRYPT32!CertOIDToAlgId` at `0x18000b245`
- `USER32!GetDesktopWindow` at `0x18000ab1f`
- `USER32!GetDesktopWindow` at `0x18000ab1f`

## string_xrefs

- `0x18000ac4d`: `Software\Microsoft\Internet Explorer\Security`
- `0x18000a5d3`: `System\CurrentControlSet\Services\WinTrust\TrustProviders`

## pseudocode

```c
__int64 __fastcall I_VerifyTrust(HWND a1, struct _GUID *a2, HKEY a3, void *a4, DWORD *a5, _DWORD *a6)
{
  int v9; // r14d
  HKEY v10; // rdx
  HKEY v11; // rax
  DWORD v12; // r13d
  HKEY v13; // rdi
  void *v14; // r14
  DWORD v15; // edi
  struct _LOADED_PROVIDER_V1 *Provider; // rax
  struct _LOADED_PROVIDER_V1 *v17; // rsi
  __int64 v18; // rax
  unsigned int v19; // edx
  unsigned int v20; // r8d
  __int64 v21; // r9
  unsigned int v22; // r14d
  void *v23; // r15
  int v24; // esi
  __int64 v26; // rdx
  __int64 v27; // rax
  __int64 LruEntryData; // rax
  __int64 v29; // r13
  bool v30; // cc
  int v31; // ecx
  void *v32; // rcx
  unsigned int v33; // eax
  HMODULE v34; // rcx
  void *v35; // rcx
  __int64 v36; // rax
  _QWORD *v37; // rdx
  char *v38; // rcx
  int v39; // eax
  __int16 *v40; // rcx
  __int16 v41; // ax
  HWND DesktopWindow; // rbx
  _OWORD *v43; // rbx
  _OWORD *v44; // rax
  DWORD v45; // ebx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int16 v48; // ax
  __int64 i; // rcx
  PFN_PROVIDER_INIT_CALL pfnInitialize; // rax
  unsigned int v51; // eax
  _QWORD *v52; // rdi
  __int64 v53; // rcx
  _DWORD *v54; // rax
  int v55; // edx
  _QWORD *v56; // rax
  __int64 v57; // rdx
  __int64 v58; // rcx
  int v60; // esi
  _DWORD *v61; // rax
  _OWORD *v62; // rax
  int v63; // edi
  HKEY v64; // r15
  PFN_PROVIDER_OBJTRUST_CALL pfnObjectTrust; // rax
  PFN_PROVIDER_SIGTRUST_CALL pfnSignatureTrust; // rax
  PFN_PROVIDER_CERTTRUST_CALL pfnCertificateTrust; // rax
  PFN_PROVIDER_FINALPOLICY_CALL pfnFinalPolicy; // rax
  PFN_PROVIDER_TESTFINALPOLICY_CALL pfnTestFinalPolicy; // rax
  int j; // ebx
  PFN_PROVIDER_CLEANUP_CALL pfnCleanupPolicy; // rax
  int v72; // ebx
  __int64 v73; // rbx
  __int64 v74; // rax
  DWORD v75; // eax
  void *v76; // rcx
  DWORD *v77; // rdi
  void *v78; // rax
  _OWORD *v79; // rax
  __int64 v80; // rcx
  void *v81; // rcx
  int v82; // [rsp+60h] [rbp-A0h]
  DWORD cbMaxSubKeyLen; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-98h] BYREF
  HKEY v85; // [rsp+70h] [rbp-90h] BYREF
  __int64 v86; // [rsp+78h] [rbp-88h]
  unsigned int v87; // [rsp+80h] [rbp-80h]
  int v88; // [rsp+84h] [rbp-7Ch]
  HKEY phkResult; // [rsp+88h] [rbp-78h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-70h] BYREF
  _OWORD *v91; // [rsp+98h] [rbp-68h]
  DWORD cchName; // [rsp+A0h] [rbp-60h] BYREF
  HKEY v93; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v94; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v95; // [rsp+B8h] [rbp-48h]
  _QWORD *v96; // [rsp+C0h] [rbp-40h]
  __int128 v97; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v98; // [rsp+E0h] [rbp-20h]
  HCRYPTPROV phProv[2]; // [rsp+F0h] [rbp-10h] BYREF
  DWORD pdwPolicyFlags[4]; // [rsp+100h] [rbp+0h] BYREF
  CRYPT_PROVIDER_FUNCTIONS *pPfns[2]; // [rsp+110h] [rbp+10h]
  __int128 v102; // [rsp+120h] [rbp+20h]
  __int128 v103; // [rsp+130h] [rbp+30h]
  __int128 v104; // [rsp+140h] [rbp+40h]
  __int128 v105; // [rsp+150h] [rbp+50h]
  __int128 v106; // [rsp+160h] [rbp+60h]
  __int128 v107; // [rsp+170h] [rbp+70h]
  __int128 v108; // [rsp+180h] [rbp+80h]
  __int128 v109; // [rsp+190h] [rbp+90h]
  __int128 v110; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v111; // [rsp+1B0h] [rbp+B0h]
  __int128 v112; // [rsp+1C0h] [rbp+C0h] BYREF
  DWORD *v113; // [rsp+1D0h] [rbp+D0h]
  void *v114; // [rsp+1D8h] [rbp+D8h]
  __int128 v115; // [rsp+1E0h] [rbp+E0h] BYREF
  __int128 v116; // [rsp+1F0h] [rbp+F0h] BYREF
  __int128 v117; // [rsp+200h] [rbp+100h]
  __int128 v118; // [rsp+210h] [rbp+110h] BYREF
  __int128 v119; // [rsp+220h] [rbp+120h]
  __int128 v120; // [rsp+230h] [rbp+130h]
  __int128 v121; // [rsp+240h] [rbp+140h]
  __int128 v122; // [rsp+250h] [rbp+150h]
  __int64 v123; // [rsp+260h] [rbp+160h]
  __int128 FileInformation; // [rsp+270h] [rbp+170h] BYREF
  FILETIME FileTime1[2]; // [rsp+280h] [rbp+180h] BYREF
  int v126; // [rsp+290h] [rbp+190h]
  _WORD Data[64]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v113 = a5;
  *(_QWORD *)&v112 = a6;
  v114 = a4;
  memset_0(&v97, 0, 0xF0u);
  v9 = 0;
  v96 = 0;
  v10 = 0;
  phkResult = 0;
  v126 = 0;
  v123 = 0;
  FileInformation = 0;
  *(_OWORD *)&FileTime1[0].dwLowDateTime = 0;
  v118 = 0;
  v119 = 0;
  v120 = 0;
  v121 = 0;
  v122 = 0;
  v116 = 0;
  v117 = 0;
  if ( a5 )
  {
    cbMaxSubKeyLen = *a5;
    *a5 = 0;
  }
  else
  {
    cbMaxSubKeyLen = 0;
  }
  if ( a6 )
    *a6 = 0;
  v11 = *(HKEY *)&a2->Data1;
  v94 = 0x11CF8DA264B9D180LL;
  v95 = 0xEB85A400AA003687uLL;
  v85 = (HKEY)0x11CFE005C6B2E8D0LL;
  v86 = 0x43BFD74FC00034A1LL;
  if ( v11 == (HKEY)0x11CF8DA264B9D180LL && *(_QWORD *)a2->Data4 == v95
    || *(HKEY *)&a2->Data1 == v85 && *(_QWORD *)a2->Data4 == v86 )
  {
    v82 = 0;
    v9 = 1;
    cchName = 1;
    goto LABEL_11;
  }
  if ( *((_DWORD *)a3 + 8) != 2 || *(_DWORD *)a3 <= 0x38u || (unsigned int)(*((_DWORD *)a3 + 12) - 3) > 1 )
  {
    v82 = 0;
    goto LABEL_50;
  }
  EnterCriticalSection(&g_CatalogCache);
  if ( *((_DWORD *)a3 + 12) == 4 )
  {
    I_CryptFlushLruCache(qword_180069DC0, 0, 0);
    LeaveCriticalSection(&g_CatalogCache);
    return 0;
  }
  v82 = 1;
  if ( !GetFileAttributesExW(*(LPCWSTR *)(*((_QWORD *)a3 + 5) + 8LL), GetFileExInfoStandard, &FileInformation) )
  {
    FileInformation = 0;
    v126 = 0;
    *(_OWORD *)&FileTime1[0].dwLowDateTime = 0;
  }
  v26 = *((_QWORD *)a3 + 5);
  v115 = 0;
  v94 = 0;
  v27 = -1;
  do
    ++v27;
  while ( *(_WORD *)(*(_QWORD *)(v26 + 8) + 2 * v27) );
  LODWORD(v115) = 2 * v27;
  *((_QWORD *)&v115 + 1) = *(_QWORD *)(v26 + 8);
  LruEntryData = I_CryptFindLruEntryData(qword_180069DC0, &v115, &v94);
  v96 = (_QWORD *)LruEntryData;
  v29 = LruEntryData;
  if ( LruEntryData
    && (v126 != *(_DWORD *)(LruEntryData + 48)
     || FileTime1[1].dwHighDateTime != *(_DWORD *)(LruEntryData + 44)
     || CompareFileTime((const FILETIME *)&FileTime1[0].dwHighDateTime, (const FILETIME *)(LruEntryData + 36))
     || CompareFileTime((const FILETIME *)((char *)&FileInformation + 4), (const FILETIME *)(v29 + 20))) )
  {
    I_CryptRemoveLruEntry(*(_QWORD *)(v29 + 8), 0, 0);
    I_CryptReleaseLruEntry(*(_QWORD *)(v29 + 8));
    *((_DWORD *)a3 + 12) = 1;
    v96 = 0;
  }
  else
  {
    *((_DWORD *)a3 + 12) = 1;
    if ( v29 )
    {
      v10 = 0;
      *((_QWORD *)a3 + 7) = *(_QWORD *)v29;
      *(_QWORD *)(*(_QWORD *)v29 + 8LL) = a3;
      goto LABEL_50;
    }
  }
  *((_QWORD *)a3 + 7) = 0;
  v10 = 0;
LABEL_50:
  v30 = *(_DWORD *)a3 <= 0x38u;
  cchName = 0;
  if ( !v30 )
  {
    v31 = *((_DWORD *)a3 + 12);
    if ( (unsigned int)(v31 - 1) <= 1 )
    {
      v10 = (HKEY)*((_QWORD *)a3 + 7);
      phkResult = v10;
      if ( v31 == 2 )
      {
        if ( v10 )
        {
          I_CleanupProviderData(v10);
          v32 = (void *)*((_QWORD *)a3 + 7);
          if ( v32 )
          {
            operator delete(v32);
            *((_QWORD *)a3 + 7) = 0;
          }
        }
        return 0;
      }
    }
  }
LABEL_11:
  v12 = 0;
  v91 = 0;
  if ( !(unsigned int)I_WVTSetupProviderData(&v97, v10) )
  {
    I_CleanupProviderData(&v97);
    v24 = v82;
    v22 = -2146869247;
    v23 = 0;
    goto LABEL_124;
  }
  v13 = a3;
  v93 = a3;
  phProv[0] = (HCRYPTPROV)a2;
  if ( phkResult )
  {
    DWORD2(v109) |= 0x80000000;
    v22 = -2146762751;
    goto LABEL_117;
  }
  if ( WintrustLoadFunctionPointers(a2, pPfns[0]) )
  {
    if ( v9 )
    {
      v85 = (HKEY)0x11CFE005C6B2E8D0LL;
      v123 = 0;
      v86 = 0x43BFD74FC00034A1LL;
      *((_QWORD *)&v120 + 1) = &v116;
      *(_QWORD *)&v120 = 1;
      v118 = 0;
      LODWORD(v118) = 88;
      v116 = 0;
      LODWORD(v116) = 32;
      v119 = 0;
      v121 = 0;
      v122 = 0;
      v117 = 0;
      if ( a3 )
      {
        v36 = *(_QWORD *)a3;
        v37 = (_QWORD *)*((_QWORD *)a3 + 2);
        DWORD2(v119) = 1;
        *((_QWORD *)&v118 + 1) = v36;
        *(_QWORD *)&v117 = *v37;
        v38 = (char *)v85 - *(_QWORD *)&a2->Data1;
        if ( v85 == *(HKEY *)&a2->Data1 )
          v38 = (char *)(v86 - *(_QWORD *)a2->Data4);
        v39 = 1;
        if ( !v38 )
          v39 = 3;
        if ( a1 == HWND_MESSAGE|0x2LL )
          v39 = 2;
        DWORD2(v119) = v39;
        v40 = (__int16 *)v37[1];
        v41 = *v40;
        if ( *v40 )
        {
          do
          {
            if ( v41 == 124 )
              break;
            v41 = *++v40;
          }
          while ( *v40 );
          if ( *v40 )
            *v40 = 0;
        }
        *((_QWORD *)&v116 + 1) = *(_QWORD *)(*((_QWORD *)a3 + 2) + 8LL);
      }
      a3 = (HKEY)&v118;
      DesktopWindow = a1;
      v13 = (HKEY)&v118;
    }
    else
    {
      DesktopWindow = a1;
      if ( !a3 )
      {
LABEL_80:
        if ( (((unsigned __int64)a1 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 && *((_DWORD *)a3 + 6) != 2 )
          DesktopWindow = GetDesktopWindow();
        if ( !phProv[1]
          && !CryptAcquireContextA(
                &phProv[1],
                0,
                "Microsoft Enhanced RSA and AES Cryptographic Provider",
                0x18u,
                0xF0000000) )
        {
          goto LABEL_88;
        }
        *((_QWORD *)&v98 + 1) = DesktopWindow;
        v43 = (_OWORD *)v102;
        DWORD2(v103) = 65537;
        *((_QWORD *)&v97 + 1) = a3;
        pdwPolicyFlags[0] = 0;
        if ( !(_QWORD)v102 )
        {
          v44 = operator new[](0x98u);
          v43 = v44;
          if ( !v44 )
          {
            SetLastError(0x8007000E);
            *(_QWORD *)&v102 = 0;
LABEL_88:
            pdwPolicyFlags[0] = GetLastError();
            I_CleanupProviderData(&v97);
            v24 = v82;
            v22 = 8;
            v23 = 0;
            goto LABEL_124;
          }
          *(_QWORD *)&v102 = v44;
          LODWORD(pPfns[1]) = 38;
        }
        *v43 = 0;
        v22 = -2146762751;
        v43[1] = 0;
        v43[2] = 0;
        v43[3] = 0;
        v43[4] = 0;
        v43[5] = 0;
        v43[6] = 0;
        v43[7] = 0;
        v43[8] = 0;
        *((_QWORD *)v43 + 18) = 0;
        WintrustGetRegPolicyFlags(&pdwPolicyFlags[2]);
        pdwPolicyFlags[2] &= 0xFFFFFF5F;
        v93 = 0;
        cSubKeys = 0;
        LODWORD(hKey) = 128;
        pdwPolicyFlags[1] = 2;
        v85 = 0;
        v45 = RegOpenHKCUEx(&v85);
        if ( !v45 )
        {
          v45 = RegOpenKeyExW(v85, L"Software\\Microsoft\\Internet Explorer\\Security", 0, 0x20019u, &v93);
          if ( v85 )
          {
            if ( v85 != HKEY_CURRENT_USER )
              RegCloseKey(v85);
          }
        }
        if ( !v45 )
        {
          if ( RegQueryValueExW(v93, L"Safety Warning Level", 0, &cSubKeys, (LPBYTE)Data, (LPDWORD)&hKey) )
          {
            RegCloseKey(v93);
          }
          else
          {
            RegCloseKey(v93);
            if ( cSubKeys == 1 )
            {
              v46 = -1;
              do
              {
                if ( Data[v46 + 1] != aFailinform[v46 + 1] )
                  break;
                v46 += 2;
                if ( v46 == 11 )
                {
                  pdwPolicyFlags[1] = 2;
                  goto LABEL_112;
                }
              }
              while ( Data[v46] == aFailinform[v46] );
              v47 = 0;
              while ( 1 )
              {
                v48 = Data[v47++];
                if ( v48 != aQuery[v47 - 1] )
                  break;
                if ( v47 == 6 )
                {
                  pdwPolicyFlags[1] = 1;
                  goto LABEL_112;
                }
              }
              for ( i = 0; i != 14; i += 2 )
              {
                if ( Data[i] != aSucceedsilent[i] || Data[i + 1] != aSucceedsilent[i + 1] )
                  goto LABEL_112;
              }
              pdwPolicyFlags[1] = 0;
            }
          }
        }
LABEL_112:
        I_CryptReadTrustedPublisherDWORDValueFromRegistry(L"AuthenticodeFlags", (char *)&v110 + 8);
        if ( !a3 || *(_DWORD *)a3 <= 0x18u )
          *(_DWORD *)(v102 + 120) = 87;
        DWORD2(v109) |= 0x80000000;
        v93 = v13;
LABEL_117:
        v85 = 0;
        I_CertDiagControl(15, 0, &v85);
        pfnInitialize = pPfns[0]->pfnInitialize;
        if ( pfnInitialize )
        {
          v51 = ((__int64 (__fastcall *)(__int128 *))pfnInitialize)(&v97);
          v22 = v51;
          if ( v51 )
          {
            v12 = pdwPolicyFlags[0];
            HIDWORD(v109) = pdwPolicyFlags[0];
            if ( !pdwPolicyFlags[0] )
              v12 = v51;
            I_CleanupProviderData(&v97);
            goto LABEL_122;
          }
          if ( *(_DWORD *)a3 > 0x50u )
          {
            v61 = (_DWORD *)*((_QWORD *)a3 + 10);
            if ( v61 && *v61 < 0x20u )
            {
              v12 = -2147024809;
LABEL_122:
              v24 = v82;
LABEL_123:
              v23 = v91;
              goto LABEL_124;
            }
            *((_QWORD *)&v111 + 1) = *((_QWORD *)a3 + 10);
          }
          if ( !*((_QWORD *)&v111 + 1) )
          {
            v62 = (_OWORD *)WVTNew(0x20u);
            v91 = v62;
            v23 = v62;
            if ( !v62 )
            {
              v24 = v82;
              v12 = 14;
              goto LABEL_124;
            }
            *((_QWORD *)&v111 + 1) = v62;
            *v62 = 0;
            v62[1] = 0;
            **((_DWORD **)&v111 + 1) = 32;
          }
        }
        v63 = 0;
        v64 = v85;
        do
        {
          pfnObjectTrust = pPfns[0]->pfnObjectTrust;
          if ( pfnObjectTrust )
          {
            v63 |= 1u;
            ((void (__fastcall *)(__int128 *))pfnObjectTrust)(&v97);
          }
          if ( *(_DWORD *)(v111 + 28) && *(_DWORD *)(v111 + 24) )
            goto LABEL_170;
          if ( *(_DWORD *)(v111 + 24) )
            I_CleanupSignatureData(&v97);
          pfnSignatureTrust = pPfns[0]->pfnSignatureTrust;
          if ( pfnSignatureTrust )
          {
            v63 |= 2u;
            ((void (__fastcall *)(__int128 *))pfnSignatureTrust)(&v97);
          }
          pfnCertificateTrust = pPfns[0]->pfnCertificateTrust;
          if ( pfnCertificateTrust )
          {
            v63 |= 4u;
            ((void (__fastcall *)(__int128 *))pfnCertificateTrust)(&v97);
          }
          pfnFinalPolicy = pPfns[0]->pfnFinalPolicy;
          if ( pfnFinalPolicy )
            v22 = ((__int64 (__fastcall *)(__int128 *))pfnFinalPolicy)(&v97);
          pfnTestFinalPolicy = pPfns[0]->pfnTestFinalPolicy;
          if ( pfnTestFinalPolicy )
            ((void (__fastcall *)(__int128 *))pfnTestFinalPolicy)(&v97);
          v12 = HIDWORD(v109);
          if ( !HIDWORD(v109) )
            v12 = v22;
          for ( j = 0; j < SDWORD2(v104); ++j )
            LogSignatureTelemetry_(&v97, (unsigned int)j);
          if ( !v12 )
          {
LABEL_170:
            *(_DWORD *)(v111 + 24) = 1;
            ++*(_DWORD *)(v111 + 48);
            if ( !v12 )
              break;
          }
          else
          {
            if ( (*(_DWORD *)(*((_QWORD *)&v111 + 1) + 8LL) & 5) != 1
              && (*(_DWORD *)(*((_QWORD *)&v111 + 1) + 8LL) & 0x40000000) != 0 )
            {
              *(_DWORD *)(v111 + 28) = 1;
            }
            *(_DWORD *)(v111 + 24) = 1;
            ++*(_DWORD *)(v111 + 48);
          }
        }
        while ( !*(_DWORD *)(v111 + 28)
             && *(_DWORD *)(v111 + 40)
             && *((_QWORD *)&v97 + 1)
             && *(_DWORD *)(*((_QWORD *)&v97 + 1) + 32LL) == 1 );
        pfnCleanupPolicy = pPfns[0]->pfnCleanupPolicy;
        if ( pfnCleanupPolicy )
          ((void (__fastcall *)(__int128 *))pfnCleanupPolicy)(&v97);
        if ( *((_QWORD *)&v111 + 1) && *(_QWORD *)(*((_QWORD *)&v111 + 1) + 24LL) && *(_DWORD *)(v111 + 44) != v63 )
        {
          v12 = -2146893783;
          v22 = -2146893783;
        }
        v24 = v82;
        if ( v64 )
        {
          v72 = *((_DWORD *)a3 + 12);
          if ( v82 == 1 )
            *((_DWORD *)a3 + 12) = 3;
          v85 = v64;
          v86 = (__int64)&v97;
          v87 = v22;
          v88 = 0;
          I_CertDiagControl(16, &v85, 0);
          if ( v82 == 1 )
            *((_DWORD *)a3 + 12) = v72;
        }
        if ( v113 )
        {
          if ( v22 != -2146762496 )
          {
            v73 = v107;
            if ( (_QWORD)v107 )
            {
              v74 = *(_QWORD *)(v107 + 56);
              if ( v74 )
              {
                v75 = *(_DWORD *)(v74 + 48);
                if ( v75 )
                {
                  v76 = v114;
                  *v113 = v75;
                  if ( v76 )
                  {
                    if ( cbMaxSubKeyLen < v75 )
                    {
                      if ( !v22 )
                        v22 = 234;
                    }
                    else
                    {
                      memcpy_0(v76, *(const void **)(*(_QWORD *)(v73 + 56) + 56LL), v75);
                    }
                  }
                  v77 = (DWORD *)v112;
                  if ( (_QWORD)v112 )
                    *v77 = CertOIDToAlgId(*(LPCSTR *)(*(_QWORD *)(v73 + 56) + 24LL));
                }
              }
            }
          }
        }
        if ( !phkResult )
        {
          if ( *(_DWORD *)a3 <= 0x38u || *((_DWORD *)a3 + 12) != 1 )
          {
            I_CleanupProviderData(&v97);
            goto LABEL_205;
          }
          v78 = operator new[](0xF0u);
          if ( !v78 )
          {
            SetLastError(0x8007000E);
            *((_QWORD *)v93 + 7) = 0;
            I_CleanupProviderData(&v97);
            v22 = 8;
LABEL_205:
            if ( cchName && v22 )
            {
              if ( a3 && *(_DWORD *)a3 > 0x18u )
              {
                v22 = -2146762485;
                if ( *((_DWORD *)a3 + 6) != 3 )
                  v22 = -2146762748;
              }
              else
              {
                v22 = -2146762748;
              }
            }
            goto LABEL_123;
          }
          *((_QWORD *)a3 + 7) = v78;
        }
        I_CleanupProviderNonStateData(&v97);
        v79 = (_OWORD *)*((_QWORD *)a3 + 7);
        *v79 = v97;
        v79[1] = v98;
        v79[2] = *(_OWORD *)phProv;
        v79[3] = *(_OWORD *)pdwPolicyFlags;
        v79[4] = *(_OWORD *)pPfns;
        v79[5] = v102;
        v79[6] = v103;
        v79[7] = v104;
        v79[8] = v105;
        v79[9] = v106;
        v79[10] = v107;
        v79[11] = v108;
        v79[12] = v109;
        v79[13] = v110;
        v79[14] = v111;
        goto LABEL_205;
      }
    }
    if ( *(_DWORD *)a3 > 0x48u )
      DWORD2(v109) = *((unsigned __int16 *)a3 + 36);
    goto LABEL_80;
  }
  hKey = 0;
  phkResult = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  if ( RegOpenKeyExA(
         HKEY_LOCAL_MACHINE,
         "System\\CurrentControlSet\\Services\\WinTrust\\TrustProviders",
         0,
         0x80000000,
         &hKey) )
  {
LABEL_29:
    v22 = -2146762751;
    goto LABEL_30;
  }
  if ( RegQueryInfoKeyA(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0)
    || (cbMaxSubKeyLen += 2, (v14 = operator new[](cbMaxSubKeyLen + 1)) == 0) )
  {
LABEL_28:
    RegCloseKey(hKey);
    goto LABEL_29;
  }
  v15 = 0;
  if ( !cSubKeys )
  {
LABEL_27:
    operator delete(v14);
    goto LABEL_28;
  }
  while ( 1 )
  {
    cchName = cbMaxSubKeyLen;
    if ( RegEnumKeyExA(hKey, v15, (LPSTR)v14, &cchName, 0, 0, 0, 0)
      || RegOpenKeyExA(hKey, (LPCSTR)v14, 0, 0x82000000, &phkResult) )
    {
      goto LABEL_26;
    }
    Provider = Version1_RegLoadProvider(phkResult, (LPCCH)v14, a2);
    v17 = Provider;
    if ( Provider )
    {
      v18 = *((_QWORD *)Provider + 5);
      v19 = 0;
      v20 = *(_DWORD *)(v18 + 16);
      v21 = *(_QWORD *)(v18 + 24);
      if ( v20 )
        break;
    }
LABEL_25:
    RegCloseKey(phkResult);
LABEL_26:
    if ( ++v15 >= cSubKeys )
      goto LABEL_27;
  }
  while ( *(_QWORD *)&a2->Data1 != *(_QWORD *)(v21 + 16LL * v19)
       || *(_QWORD *)a2->Data4 != *(_QWORD *)(v21 + 16LL * v19 + 8) )
  {
    if ( ++v19 >= v20 )
      goto LABEL_25;
  }
  RegCloseKey(phkResult);
  operator delete(v14);
  RegCloseKey(hKey);
  v33 = (*(__int64 (__fastcall **)(HWND, struct _GUID *, HKEY))(*(_QWORD *)(*((_QWORD *)v17 + 5) + 8LL) + 8LL))(
          a1,
          a2,
          a3);
  v34 = (HMODULE)*((_QWORD *)v17 + 2);
  v22 = v33;
  if ( v34 )
    FreeLibrary(v34);
  v35 = (void *)*((_QWORD *)v17 + 3);
  if ( v35 )
    operator delete(v35);
  operator delete(v17);
LABEL_30:
  I_CleanupProviderData(&v97);
  DWORD2(v109) |= 0x80000000;
  v23 = 0;
  v24 = v82;
LABEL_124:
  if ( v24 != 1 )
    goto LABEL_226;
  v52 = v96;
  if ( v96 )
  {
LABEL_224:
    *(_QWORD *)(*v52 + 8LL) = 0;
    *((_DWORD *)a3 + 12) = 3;
    *((_QWORD *)a3 + 7) = 0;
    I_CryptReleaseLruEntry(v52[1]);
    goto LABEL_225;
  }
  v53 = *((_QWORD *)a3 + 7);
  v112 = 0;
  if ( !v53 )
    goto LABEL_220;
  v54 = *(_DWORD **)(v53 + 80);
  if ( v54[31] != (_DWORD)v96 )
    goto LABEL_220;
  v55 = v54[32];
  if ( v55 )
  {
    if ( v55 != -2146869232 )
      goto LABEL_220;
  }
  if ( v54[33] || !*(_QWORD *)(v53 + 112) )
    goto LABEL_220;
  v56 = operator new(0x38u);
  v52 = v56;
  if ( !v56 )
  {
    SetLastError(0x8007000E);
    v60 = 0;
LABEL_216:
    operator delete(v52);
    v52 = v96;
    goto LABEL_217;
  }
  *v56 = *((_QWORD *)a3 + 7);
  v57 = -1;
  v56[1] = 0;
  *((_OWORD *)v56 + 1) = FileInformation;
  *((_OWORD *)v56 + 2) = *(_OWORD *)&FileTime1[0].dwLowDateTime;
  *((_DWORD *)v56 + 12) = v126;
  v58 = *((_QWORD *)a3 + 5);
  while ( *(_WORD *)(*(_QWORD *)(v58 + 8) + 2 * v57++ + 2) != 0 )
    ;
  LODWORD(v112) = 2 * v57;
  *((_QWORD *)&v112 + 1) = *(_QWORD *)(v58 + 8);
  v60 = I_CryptCreateLruEntry(qword_180069DC0, &v112, v56);
  if ( v60 != 1 )
    goto LABEL_216;
LABEL_217:
  if ( v60 == 1 )
    I_CryptInsertLruEntry(v52[1], 0);
  if ( v52 )
    goto LABEL_224;
LABEL_220:
  v80 = *((_QWORD *)a3 + 7);
  if ( v80 )
  {
    I_CleanupProviderData(v80);
    v81 = (void *)*((_QWORD *)a3 + 7);
    if ( v81 )
    {
      operator delete(v81);
      *((_QWORD *)a3 + 7) = 0;
    }
  }
  *((_DWORD *)a3 + 12) = 3;
  *((_QWORD *)a3 + 7) = 0;
LABEL_225:
  LeaveCriticalSection(&g_CatalogCache);
LABEL_226:
  if ( v23 )
    operator delete(v23);
  SetLastError(v12);
  return v22;
}

```

## disassembly

```asm
0x18000a410  push    rbp
0x18000a412  push    rbx
0x18000a413  push    rsi
0x18000a414  push    rdi
0x18000a415  push    r12
0x18000a417  push    r14
0x18000a419  push    r15
0x18000a41b  lea     rbp, [rsp-240h]
0x18000a423  sub     rsp, 340h
0x18000a42a  mov     rax, cs:__security_cookie
0x18000a431  xor     rax, rsp
0x18000a434  mov     [rbp+270h+var_50], rax
0x18000a43b  mov     rdi, [rbp+270h+arg_20]
0x18000a442  mov     r12, r8
0x18000a445  mov     rsi, [rbp+270h+arg_28]
0x18000a44c  mov     rbx, rdx
0x18000a44f  mov     r15, rcx
0x18000a452  mov     [rbp+270h+var_1A0], rdi
0x18000a459  xor     edx, edx; Val
0x18000a45b  mov     qword ptr [rbp+270h+var_1B0], rsi
0x18000a462  mov     r8d, 0F0h; Size
0x18000a468  mov     [rbp+270h+var_198], r9
0x18000a46f  lea     rcx, [rbp+270h+var_2A0]; void *
0x18000a473  call    memset_0
0x18000a478  xorps   xmm1, xmm1
0x18000a47b  xorps   xmm0, xmm0
0x18000a47e  xor     r14d, r14d
0x18000a481  xor     eax, eax
0x18000a483  mov     [rbp+270h+var_2B0], r14
0x18000a487  mov     edx, r14d; Src
0x18000a48a  mov     [rbp+270h+var_2E8], rdx
0x18000a48e  mov     [rbp+270h+var_E0], eax
0x18000a494  mov     [rbp+270h+var_110], rax
0x18000a49b  movups  [rbp+270h+FileInformation], xmm0
0x18000a4a2  movups  xmmword ptr [rbp+270h+FileTime1.dwLowDateTime], xmm0
0x18000a4a9  movups  [rbp+270h+var_160], xmm1
0x18000a4b0  movups  [rbp+270h+var_150], xmm1
0x18000a4b7  movups  [rbp+270h+var_140], xmm1
0x18000a4be  movups  [rbp+270h+var_130], xmm1
0x18000a4c5  movups  [rbp+270h+var_120], xmm1
0x18000a4cc  movups  [rbp+270h+var_180], xmm0
0x18000a4d3  movups  [rbp+270h+var_170], xmm0
0x18000a4da  test    rdi, rdi
0x18000a4dd  jz      short loc_18000A4EA
0x18000a4df  mov     eax, [rdi]
0x18000a4e1  mov     [rsp+370h+cbMaxSubKeyLen], eax
0x18000a4e5  mov     [rdi], r14d
0x18000a4e8  jmp     short loc_18000A4EF
0x18000a4ea  mov     [rsp+370h+cbMaxSubKeyLen], r14d
0x18000a4ef  test    rsi, rsi
0x18000a4f2  jz      short loc_18000A4F7
0x18000a4f4  mov     [rsi], r14d
0x18000a4f7  mov     rax, [rbx]
0x18000a4fa  mov     dword ptr [rbp+270h+var_2C0], 64B9D180h
0x18000a501  mov     dword ptr [rbp+270h+var_2C0+4], 11CF8DA2h
0x18000a508  mov     [rsp+370h+var_38], r13
0x18000a510  mov     dword ptr [rbp+270h+var_2B8], 0AA003687h
0x18000a517  mov     dword ptr [rbp+270h+var_2B8+4], 0EB85A400h
0x18000a51e  mov     dword ptr [rsp+370h+var_300], 0C6B2E8D0h
0x18000a526  mov     dword ptr [rsp+370h+var_300+4], 11CFE005h
0x18000a52e  mov     dword ptr [rsp+370h+var_2F8], 0C00034A1h
0x18000a536  mov     dword ptr [rsp+370h+var_2F8+4], 43BFD74Fh
0x18000a53e  cmp     rax, [rbp+270h+var_2C0]
0x18000a542  jnz     short loc_18000A54E
0x18000a544  mov     rax, [rbx+8]
0x18000a548  cmp     rax, [rbp+270h+var_2B8]
0x18000a54c  jz      short loc_18000A56B
0x18000a54e  mov     rax, [rbx]
0x18000a551  cmp     rax, [rsp+370h+var_300]
0x18000a556  jnz     loc_18000A773
0x18000a55c  mov     rax, [rbx+8]
0x18000a560  cmp     rax, [rsp+370h+var_2F8]
0x18000a565  jnz     loc_18000A773
0x18000a56b  mov     esi, 1
0x18000a570  mov     [rsp+370h+var_310], r14d
0x18000a575  mov     r14d, esi
0x18000a578  mov     [rbp+270h+cchName], esi
0x18000a57b  xor     r13d, r13d
0x18000a57e  lea     rcx, [rbp+270h+var_2A0]; void *
0x18000a582  mov     [rbp+270h+var_2D8], r13
0x18000a586  call    I_WVTSetupProviderData
0x18000a58b  test    eax, eax
0x18000a58d  jz      loc_18000B39E
0x18000a593  mov     rdi, r12
0x18000a596  mov     [rbp+270h+var_2C8], r12
0x18000a59a  mov     [rbp+270h+phProv], rbx
0x18000a59e  cmp     [rbp+270h+var_2E8], r13
0x18000a5a2  jnz     loc_18000ADC5
0x18000a5a8  mov     rdx, [rbp+270h+pPfns]; pPfns
0x18000a5ac  mov     rcx, rbx; pgActionID
0x18000a5af  call    WintrustLoadFunctionPointers
0x18000a5b4  test    eax, eax
0x18000a5b6  jnz     loc_18000A9BF
0x18000a5bc  xor     esi, esi
0x18000a5be  lea     rax, [rbp+270h+hKey]
0x18000a5c2  mov     r9d, 80000000h; samDesired
0x18000a5c8  mov     [rbp+270h+hKey], rsi
0x18000a5cc  xor     r8d, r8d; ulOptions
0x18000a5cf  mov     [rbp+270h+var_2E8], rsi
0x18000a5d3  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Wi"...
0x18000a5da  mov     [rsp+370h+cSubKeys], esi
0x18000a5de  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a5e5  mov     [rsp+370h+cbMaxSubKeyLen], esi
0x18000a5e9  mov     [rsp+370h+phkResult], rax; phkResult
0x18000a5ee  call    cs:__imp_RegOpenKeyExA
0x18000a5f4  test    eax, eax
0x18000a5f6  jnz     loc_18000A74E
0x18000a5fc  mov     rcx, [rbp+270h+hKey]; hKey
0x18000a600  lea     rax, [rsp+370h+cbMaxSubKeyLen]
0x18000a605  mov     [rsp+370h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x18000a60a  xor     r9d, r9d; lpReserved
0x18000a60d  mov     [rsp+370h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x18000a612  xor     r8d, r8d; lpcchClass
0x18000a615  mov     [rsp+370h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x18000a61a  xor     edx, edx; lpClass
0x18000a61c  mov     [rsp+370h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x18000a621  mov     [rsp+370h+lpcValues], rsi; lpcValues
0x18000a626  mov     [rsp+370h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x18000a62b  mov     [rsp+370h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18000a630  lea     rax, [rsp+370h+cSubKeys]
0x18000a635  mov     [rsp+370h+phkResult], rax; lpcSubKeys
0x18000a63a  call    cs:__imp_RegQueryInfoKeyA
0x18000a640  test    eax, eax
0x18000a642  jnz     loc_18000A744
0x18000a648  mov     eax, [rsp+370h+cbMaxSubKeyLen]
0x18000a64c  add     eax, 2
0x18000a64f  mov     [rsp+370h+cbMaxSubKeyLen], eax
0x18000a653  lea     ecx, [rax+1]; unsigned __int64
0x18000a656  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000a65b  mov     r14, rax
0x18000a65e  test    rax, rax
0x18000a661  jz      loc_18000A744
0x18000a667  mov     edi, esi
0x18000a669  cmp     [rsp+370h+cSubKeys], esi
0x18000a66d  jbe     loc_18000A73C
0x18000a673  nop     dword ptr [rax+00h]
0x18000a677  nop     word ptr [rax+rax+00000000h]
0x18000a680  mov     eax, [rsp+370h+cbMaxSubKeyLen]
0x18000a684  lea     r9, [rbp+270h+cchName]; lpcchName
0x18000a688  mov     rcx, [rbp+270h+hKey]; hKey
0x18000a68c  mov     r8, r14; lpName
0x18000a68f  mov     [rsp+370h+lpcValues], rsi; lpftLastWriteTime
0x18000a694  mov     edx, edi; dwIndex
0x18000a696  mov     [rsp+370h+lpcbMaxClassLen], rsi; lpcchClass
0x18000a69b  mov     [rsp+370h+lpcbMaxSubKeyLen], rsi; lpClass
0x18000a6a0  mov     [rsp+370h+phkResult], rsi; lpReserved
0x18000a6a5  mov     [rbp+270h+cchName], eax
0x18000a6a8  call    cs:__imp_RegEnumKeyExA
0x18000a6ae  test    eax, eax
0x18000a6b0  jnz     short loc_18000A730
0x18000a6b2  mov     rcx, [rbp+270h+hKey]; hKey
0x18000a6b6  lea     rax, [rbp+270h+var_2E8]
0x18000a6ba  mov     r9d, 82000000h; samDesired
0x18000a6c0  mov     [rsp+370h+phkResult], rax; phkResult
0x18000a6c5  xor     r8d, r8d; ulOptions
0x18000a6c8  mov     rdx, r14; lpSubKey
0x18000a6cb  call    cs:__imp_RegOpenKeyExA
0x18000a6d1  test    eax, eax
0x18000a6d3  jnz     short loc_18000A730
0x18000a6d5  mov     rcx, [rbp+270h+var_2E8]; hKey
0x18000a6d9  mov     r8, rbx; struct _GUID *
0x18000a6dc  mov     rdx, r14; lpMultiByteStr
0x18000a6df  call    ?Version1_RegLoadProvider@@YAPEAU_LOADED_PROVIDER_V1@@PEAUHKEY__@@PEADPEAU_GUID@@@Z; Version1_RegLoadProvider(HKEY__ *,char *,_GUID *)
0x18000a6e4  mov     rsi, rax
0x18000a6e7  test    rax, rax
0x18000a6ea  jz      short loc_18000A724
0x18000a6ec  mov     rax, [rax+28h]
0x18000a6f0  xor     edx, edx
0x18000a6f2  mov     r8d, [rax+10h]
0x18000a6f6  mov     r9, [rax+18h]
0x18000a6fa  test    r8d, r8d
0x18000a6fd  jz      short loc_18000A724
0x18000a6ff  nop
0x18000a700  mov     rax, [rbx]
0x18000a703  mov     ecx, edx
0x18000a705  add     rcx, rcx
0x18000a708  cmp     rax, [r9+rcx*8]
0x18000a70c  jnz     short loc_18000A71D
0x18000a70e  mov     rax, [rbx+8]
0x18000a712  cmp     rax, [r9+rcx*8+8]
0x18000a717  jz      loc_18000A95C
0x18000a71d  inc     edx
0x18000a71f  cmp     edx, r8d
0x18000a722  jb      short loc_18000A700
0x18000a724  mov     rcx, [rbp+270h+var_2E8]; hKey
0x18000a728  call    cs:__imp_RegCloseKey
0x18000a72e  xor     esi, esi
0x18000a730  inc     edi
0x18000a732  cmp     edi, [rsp+370h+cSubKeys]
0x18000a736  jb      loc_18000A680
0x18000a73c  mov     rcx, r14; Block
0x18000a73f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a744  mov     rcx, [rbp+270h+hKey]; hKey
0x18000a748  call    cs:__imp_RegCloseKey
0x18000a74e  mov     r14d, 800B0001h
0x18000a754  lea     rcx, [rbp+270h+var_2A0]
0x18000a758  call    I_CleanupProviderData
0x18000a75d  or      [rbp+270h+var_1D8], 80000000h
0x18000a767  mov     r15, r13
0x18000a76a  mov     esi, [rsp+370h+var_310]
0x18000a76e  jmp     loc_18000AE37
0x18000a773  cmp     dword ptr [r12+20h], 2
0x18000a779  mov     esi, 1
0x18000a77e  jnz     loc_18000A8FE
0x18000a784  cmp     dword ptr [r12], 38h ; '8'
0x18000a789  jbe     loc_18000A8FE
0x18000a78f  mov     eax, [r12+30h]
0x18000a794  sub     eax, 3
0x18000a797  cmp     eax, esi
0x18000a799  ja      loc_18000A8FE
0x18000a79f  lea     rcx, ?g_CatalogCache@@3VCCatalogCache@@A; lpCriticalSection
0x18000a7a6  call    cs:__imp_EnterCriticalSection
0x18000a7ac  xor     edx, edx; fInfoLevelId
0x18000a7ae  cmp     dword ptr [r12+30h], 4
0x18000a7b4  jnz     short loc_18000A7DA
0x18000a7b6  mov     rcx, cs:qword_180069DC0
0x18000a7bd  xor     r8d, r8d
0x18000a7c0  call    cs:__imp_I_CryptFlushLruCache
0x18000a7c6  lea     rcx, ?g_CatalogCache@@3VCCatalogCache@@A; lpCriticalSection
0x18000a7cd  call    cs:__imp_LeaveCriticalSection
0x18000a7d3  xor     eax, eax
0x18000a7d5  jmp     loc_18000B46F
0x18000a7da  mov     rcx, [r12+28h]
0x18000a7df  lea     r8, [rbp+270h+FileInformation]; lpFileInformation
0x18000a7e6  mov     [rsp+370h+var_310], esi
0x18000a7ea  mov     rcx, [rcx+8]; lpFileName
0x18000a7ee  call    cs:__imp_GetFileAttributesExW
0x18000a7f4  test    eax, eax
0x18000a7f6  jnz     short loc_18000A811
0x18000a7f8  xorps   xmm0, xmm0
0x18000a7fb  xor     eax, eax
0x18000a7fd  movups  [rbp+270h+FileInformation], xmm0
0x18000a804  mov     [rbp+270h+var_E0], eax
0x18000a80a  movups  xmmword ptr [rbp+270h+FileTime1.dwLowDateTime], xmm0
0x18000a811  mov     rdx, [r12+28h]
0x18000a816  xorps   xmm0, xmm0
0x18000a819  movups  [rbp+270h+var_190], xmm0
0x18000a820  mov     [rbp+270h+var_2C0], r14
0x18000a824  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000a82b  mov     rcx, [rdx+8]
0x18000a82f  nop
0x18000a830  inc     rax
0x18000a833  cmp     [rcx+rax*2], r14w
0x18000a838  jnz     short loc_18000A830
0x18000a83a  mov     rcx, cs:qword_180069DC0
0x18000a841  lea     r8, [rbp+270h+var_2C0]
0x18000a845  add     eax, eax
0x18000a847  mov     dword ptr [rbp+270h+var_190], eax
0x18000a84d  mov     rax, [rdx+8]
0x18000a851  lea     rdx, [rbp+270h+var_190]
0x18000a858  mov     qword ptr [rbp+270h+var_190+8], rax
0x18000a85f  call    cs:__imp_I_CryptFindLruEntryData
0x18000a865  mov     [rbp+270h+var_2B0], rax
0x18000a869  mov     r13, rax
0x18000a86c  test    rax, rax
0x18000a86f  jz      short loc_18000A8DE
0x18000a871  mov     eax, [rax+30h]
0x18000a874  cmp     [rbp+270h+var_E0], eax
0x18000a87a  jnz     short loc_18000A8B2
0x18000a87c  mov     eax, [r13+2Ch]
0x18000a880  cmp     [rbp+270h+FileTime1.dwHighDateTime+8], eax
0x18000a886  jnz     short loc_18000A8B2
0x18000a888  lea     rdx, [r13+24h]; lpFileTime2
0x18000a88c  lea     rcx, [rbp+270h+FileTime1.dwHighDateTime]; lpFileTime1
0x18000a893  call    cs:__imp_CompareFileTime
0x18000a899  test    eax, eax
0x18000a89b  jnz     short loc_18000A8B2
0x18000a89d  lea     rdx, [r13+14h]; lpFileTime2
0x18000a8a1  lea     rcx, [rbp+270h+FileInformation+4]; lpFileTime1
0x18000a8a8  call    cs:__imp_CompareFileTime
0x18000a8ae  test    eax, eax
0x18000a8b0  jz      short loc_18000A8DE
0x18000a8b2  mov     rcx, [r13+8]
0x18000a8b6  xor     r8d, r8d
0x18000a8b9  xor     edx, edx
0x18000a8bb  call    cs:__imp_I_CryptRemoveLruEntry
0x18000a8c1  mov     rcx, [r13+8]
0x18000a8c5  call    cs:__imp_I_CryptReleaseLruEntry
0x18000a8cb  mov     [r12+30h], esi
0x18000a8d0  mov     [rbp+270h+var_2B0], r14
0x18000a8d4  mov     [r12+38h], r14
0x18000a8d9  mov     rdx, r14
0x18000a8dc  jmp     short loc_18000A903
0x18000a8de  mov     [r12+30h], esi
0x18000a8e3  test    r13, r13
0x18000a8e6  jz      short loc_18000A8D4
0x18000a8e8  mov     rax, [r13+0]
0x18000a8ec  mov     rdx, r14
0x18000a8ef  mov     [r12+38h], rax
0x18000a8f4  mov     rax, [r13+0]
0x18000a8f8  mov     [rax+8], r12
0x18000a8fc  jmp     short loc_18000A903
0x18000a8fe  mov     [rsp+370h+var_310], r14d
0x18000a903  cmp     dword ptr [r12], 38h ; '8'
0x18000a908  mov     [rbp+270h+cchName], r14d
0x18000a90c  jbe     loc_18000A57B
0x18000a912  mov     ecx, [r12+30h]
0x18000a917  lea     eax, [rcx-1]
0x18000a91a  cmp     eax, esi
0x18000a91c  ja      loc_18000A57B
  ... truncated ...
```
