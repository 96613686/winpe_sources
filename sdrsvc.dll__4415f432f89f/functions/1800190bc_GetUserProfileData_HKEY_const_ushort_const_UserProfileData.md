# GetUserProfileData(HKEY__ * const,ushort const *,_UserProfileData * *)

- ea: `0x1800190bc`
- end: `0x180019c9a`
- name: `?GetUserProfileData@@YAJQEAUHKEY__@@PEBGPEAPEAU_UserProfileData@@@Z`
- size: `3038`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, struct _UserProfileData **)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180018a50`

## callees

- `0x180014f70`
- `0x18001507c`
- `0x18001586c`
- `0x180015974`
- `0x180015f34`
- `0x180018c18`
- `0x180018d38`
- `0x1800190bc`
- `0x180019ca0`
- `0x180019e58`
- `0x18001a18c`
- `0x18001a2cc`
- `0x18001a388`
- `0x18001b4c0`
- `0x18001c58c`
- `0x18001fc5c`
- `0x18001fcc0`
- `0x180020488`
- `0x18002170a`
- `0x180021740`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800194d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019636`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800196df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800194d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019636`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800196df`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18001976b`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180019b82`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18001976b`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180019b82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019511`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800197d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001985e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019b51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019b6a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019c40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019c59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019511`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800197d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001985e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019b51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019b6a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019c40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019c59`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019539`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800197f8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019886`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019539`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800197f8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019886`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18001977e`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18001977e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001936b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001936b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001939e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001939e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800194a9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180019628`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800196d1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800194a9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180019628`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800196d1`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18001930e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18001930e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800199d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800199d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019b2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019b36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019bb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019bd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019be5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019c04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019b2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019b36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019bb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019bd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019be5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019c04`

## string_xrefs

- `0x18001975a`: `__SAFEDOCS_LOADED_TEMP_HIVE`
- `0x180019b74`: `__SAFEDOCS_LOADED_TEMP_HIVE`

## pseudocode

```c
__int64 __fastcall GetUserProfileData(HKEY hKey, const unsigned __int16 *a2, struct _UserProfileData **a3)
{
  struct _UserProfileData **v3; // r15
  LPVOID v6; // r13
  unsigned __int16 *v7; // r12
  PSID v8; // rdi
  __int16 v9; // ax
  __int16 v10; // ax
  __int64 v11; // rcx
  int UserProfilePath; // ecx
  char LastError; // al
  int v14; // edx
  int v15; // r8d
  LSTATUS v16; // eax
  const unsigned __int16 *v17; // r9
  _QWORD *v18; // rcx
  const WCHAR *v19; // r14
  const unsigned __int16 *v20; // r9
  DWORD FileAttributesW; // r15d
  __int64 v22; // rcx
  DWORD v23; // r15d
  __int64 v24; // rcx
  int KeyW; // eax
  bool v26; // sf
  _QWORD *v27; // rcx
  int v28; // edx
  const WCHAR *v29; // r9
  bool v30; // sf
  HKEY v31; // rcx
  int v32; // eax
  int v33; // r8d
  bool v34; // sf
  const unsigned __int16 *v35; // r9
  __int64 v36; // rdi
  LPCWSTR v37; // r14
  int v38; // eax
  int v39; // r8d
  const unsigned __int16 *v40; // r9
  bool v41; // sf
  _BYTE *v42; // rax
  const unsigned __int16 *v43; // rdx
  unsigned __int16 *v44; // rax
  char *v45; // rcx
  unsigned int i; // ebx
  __int64 v47; // rdi
  LPVOID *v48; // rsi
  LPVOID *v49; // rdi
  unsigned int v50; // ebx
  const unsigned __int16 *ReferencedDomainName; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *cchReferencedDomainName; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *peUse; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v55; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v56; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v57; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v58; // [rsp+50h] [rbp-B0h]
  PSID Sid; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v60; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKeya; // [rsp+70h] [rbp-90h] BYREF
  int LastFailureAsHRESULT; // [rsp+78h] [rbp-88h] BYREF
  __int16 v63; // [rsp+7Ch] [rbp-84h]
  __int16 v64; // [rsp+7Eh] [rbp-82h]
  HKEY phkResult; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp-48h] BYREF
  enum _SID_NAME_USE v67; // [rsp+C0h] [rbp-40h] BYREF
  struct _UserProfileData **v68; // [rsp+C8h] [rbp-38h]
  int v69; // [rsp+D0h] [rbp-30h]
  LPCWSTR lpFileName; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int16 *v71; // [rsp+E0h] [rbp-20h] BYREF
  DWORD v72; // [rsp+E8h] [rbp-18h] BYREF
  DWORD cchName; // [rsp+ECh] [rbp-14h] BYREF
  DWORD cbSid; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 *v75[2]; // [rsp+F8h] [rbp-8h] BYREF
  LPCWSTR lpFile[2]; // [rsp+108h] [rbp+8h] BYREF
  LPCWSTR lpValueName[2]; // [rsp+118h] [rbp+18h] BYREF
  unsigned __int16 *v78[3]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE pSid[80]; // [rsp+140h] [rbp+40h] BYREF
  WCHAR Name; // [rsp+190h] [rbp+90h] BYREF
  __int128 v81; // [rsp+192h] [rbp+92h]
  __int128 v82; // [rsp+1A2h] [rbp+A2h]
  __int64 v83; // [rsp+1B2h] [rbp+B2h]
  WCHAR v84; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v85[526]; // [rsp+1C2h] [rbp+C2h] BYREF

  v3 = a3;
  v68 = a3;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "GetUserProfileData", 282, 1);
  if ( v3 )
    *v3 = 0;
  lpFileName = 0;
  Sid = 0;
  v83 = 0;
  v69 = 0;
  v67 = SidTypeInvalid;
  v81 = 0;
  v6 = 0;
  v7 = 0;
  v82 = 0;
  v8 = 0;
  Name = 0;
  v84 = 0;
  memset_0(v85, 0, 0x206u);
  cchName = 21;
  v72 = 260;
  hKeya = 0;
  phkResult = 0;
  lpFile[0] = (LPCWSTR)qword_180028260;
  lpFile[1] = 0;
  v78[0] = (unsigned __int16 *)qword_180028260;
  v78[1] = 0;
  lpValueName[0] = (LPCWSTR)qword_180028260;
  lpValueName[1] = 0;
  v75[0] = (unsigned __int16 *)qword_180028260;
  v75[1] = 0;
  v71 = 0;
  pv = 0;
  v60 = 0;
  memset_0(pSid, 0, 0x48u);
  cbSid = 68;
  v9 = 312;
  if ( !hKey || (v63 = 312, v9 = 313, !a2) || (v63 = 313, v9 = 314, !v3) )
  {
    LastFailureAsHRESULT = -2147024809;
    goto LABEL_125;
  }
  LastFailureAsHRESULT = 0;
  v63 = 314;
  if ( (int)GetUserSid(hKey, a2, (unsigned __int8 **)&Sid) < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_500c1448b7193519884fd297f141796f_Traceguids, a2);
    }
    v8 = Sid;
    v63 = 326;
    LastFailureAsHRESULT = 1;
    goto LABEL_126;
  }
  v8 = Sid;
  if ( !Sid )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_500c1448b7193519884fd297f141796f_Traceguids, a2);
      v8 = Sid;
    }
    v10 = 332;
LABEL_17:
    LastFailureAsHRESULT = 1;
    v63 = v10;
    goto LABEL_126;
  }
  LookupAccountSidW(0, Sid, &Name, &cchName, &v84, &v72, &v67);
  if ( v67 != SidTypeUser )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_500c1448b7193519884fd297f141796f_Traceguids, a2);
      v8 = Sid;
    }
    v10 = 346;
    goto LABEL_17;
  }
  if ( !CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v11);
    v9 = 351;
    goto LABEL_125;
  }
  LastFailureAsHRESULT = 0;
  v63 = 351;
  if ( EqualSid(pSid, v8) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_500c1448b7193519884fd297f141796f_Traceguids, a2);
      v8 = Sid;
    }
    v10 = 357;
    goto LABEL_17;
  }
  LastFailureAsHRESULT = GetFriendlyNameForUser(a2, &v84, &Name, (struct CBsString *)v78);
  v9 = 360;
  if ( LastFailureAsHRESULT < 0 )
  {
LABEL_125:
    v64 = v9;
    goto LABEL_126;
  }
  v63 = 360;
  UserProfilePath = GetUserProfilePath(hKey, a2, (unsigned __int16 **)&lpFileName);
  LastFailureAsHRESULT = UserProfilePath;
  v9 = 362;
  if ( UserProfilePath < 0 )
  {
    v7 = (unsigned __int16 *)lpFileName;
    goto LABEL_125;
  }
  v63 = 362;
  if ( UserProfilePath == 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_500c1448b7193519884fd297f141796f_Traceguids, a2);
      v8 = Sid;
    }
    v7 = (unsigned __int16 *)lpFileName;
    v63 = 366;
    LastFailureAsHRESULT = 1;
    goto LABEL_126;
  }
  v7 = (unsigned __int16 *)lpFileName;
  if ( GetFileAttributesW(lpFileName) == -1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v15, (_DWORD)a2, (__int64)v7, LastError);
      }
      v8 = Sid;
    }
    v10 = 374;
    goto LABEL_17;
  }
  if ( (unsigned __int64)hKeya - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKeya);
    hKeya = 0;
  }
  v16 = RegOpenKeyExW(HKEY_USERS, a2, 0, 0x20019u, &hKeya);
  if ( (unsigned int)(v16 - 2) > 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)&WPP_500c1448b7193519884fd297f141796f_Traceguids,
        (_DWORD)a2,
        v16);
    }
LABEL_94:
    v31 = hKeya;
    if ( hKeya )
    {
      if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        RegCloseKey(phkResult);
        v31 = hKeya;
        phkResult = 0;
      }
      v32 = RegOpenKeyExW(
              v31,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Shell Folders",
              0,
              0x20019u,
              &phkResult);
      v34 = v32 < 0;
      if ( v32 > 0 )
      {
        v32 = (unsigned __int16)v32 | 0x80070000;
        v34 = v32 < 0;
      }
      if ( v34
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
      {
        WPP_SF_SSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          v33,
          (_DWORD)a2,
          (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Shell Folders",
          v32);
      }
    }
    LastFailureAsHRESULT = CBsString::Set((CBsString *)lpValueName, &FOLDERID_Libraries);
    v9 = 453;
    if ( LastFailureAsHRESULT >= 0 )
    {
      v36 = 64;
      v63 = 453;
      if ( phkResult )
      {
        v37 = lpValueName[0];
        v38 = ReadStringFromRegistry(phkResult, lpValueName[0], &v71, 0);
        if ( v38 >= 0 )
        {
LABEL_112:
          LastFailureAsHRESULT = GetUserShellPaths(a2, v7, phkResult, &v60, (struct SHELL_FOLDER_PATH **)&pv);
          v41 = LastFailureAsHRESULT < 0;
          v9 = 470;
          goto LABEL_113;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_SSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, v39, (_DWORD)a2, (__int64)v37, v38);
        LastFailureAsHRESULT = CBsString::SetPath(
                                 (CBsString *)v75,
                                 v7,
                                 L"AppData\\Roaming\\Microsoft\\Windows\\Libraries",
                                 v40,
                                 ReferencedDomainName,
                                 cchReferencedDomainName,
                                 peUse,
                                 v55,
                                 v56,
                                 v57,
                                 v58);
        v9 = 466;
        if ( LastFailureAsHRESULT >= 0 )
        {
          v63 = 466;
          LastFailureAsHRESULT = SdSafeDuplicateStr(&v71, v75[0]);
          v9 = 467;
          if ( LastFailureAsHRESULT >= 0 )
          {
            v63 = 467;
            goto LABEL_112;
          }
        }
      }
      else
      {
        LastFailureAsHRESULT = CBsString::SetPath(
                                 (CBsString *)v75,
                                 v7,
                                 L"AppData\\Roaming\\Microsoft\\Windows\\Libraries",
                                 v35,
                                 ReferencedDomainName,
                                 cchReferencedDomainName,
                                 peUse,
                                 v55,
                                 v56,
                                 v57,
                                 v58);
        v9 = 474;
        if ( LastFailureAsHRESULT >= 0 )
        {
          v63 = 474;
          LastFailureAsHRESULT = SdSafeDuplicateStr(&v71, v75[0]);
          v9 = 475;
          if ( LastFailureAsHRESULT >= 0 )
          {
            v63 = 475;
            LastFailureAsHRESULT = GetUserShellPaths(a2, v7, 0, &v60, (struct SHELL_FOLDER_PATH **)&pv);
            v41 = LastFailureAsHRESULT < 0;
            v9 = 476;
LABEL_113:
            if ( !v41 )
            {
              v63 = v9;
              v6 = CoTaskMemAlloc(0x40u);
              v9 = 485;
              if ( v6 )
              {
                v63 = 485;
                v42 = v6;
                LastFailureAsHRESULT = 0;
                do
                {
                  *v42++ = 0;
                  --v36;
                }
                while ( v36 );
                *(_QWORD *)v6 = Sid;
                v8 = 0;
                *((_DWORD *)v6 + 2) = v67 == SidTypeUser;
                LastFailureAsHRESULT = SdSafeDuplicateStr((unsigned __int16 **)v6 + 2, a2);
                v9 = 493;
                if ( LastFailureAsHRESULT >= 0 )
                {
                  v43 = v78[0];
                  v63 = 493;
                  v44 = v71;
                  *((_QWORD *)v6 + 3) = v7;
                  v7 = 0;
                  *((_QWORD *)v6 + 5) = v44;
                  *((_QWORD *)v6 + 6) = pv;
                  pv = 0;
                  *((_DWORD *)v6 + 14) = v60;
                  v60 = 0;
                  LastFailureAsHRESULT = SdSafeDuplicateStr((unsigned __int16 **)v6 + 4, v43);
                  v9 = 507;
                  if ( LastFailureAsHRESULT >= 0 )
                  {
                    *v3 = (struct _UserProfileData *)v6;
                    v6 = 0;
                    v63 = 507;
                    goto LABEL_126;
                  }
                }
                goto LABEL_125;
              }
              LastFailureAsHRESULT = -2147024882;
            }
          }
        }
      }
    }
LABEL_60:
    v8 = Sid;
    goto LABEL_125;
  }
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_500c1448b7193519884fd297f141796f_Traceguids, a2);
      v18 = WPP_GLOBAL_Control;
    }
    if ( v18 != &WPP_GLOBAL_Control && (*((_DWORD *)v18 + 7) & 0x10000000) != 0 )
      WPP_SF_S(v18[2], 19, &WPP_500c1448b7193519884fd297f141796f_Traceguids, v7);
  }
  LastFailureAsHRESULT = CBsString::SetPath(
                           (CBsString *)lpFile,
                           v7,
                           L"NTUSER.MAN",
                           v17,
                           ReferencedDomainName,
                           cchReferencedDomainName,
                           peUse,
                           v55,
                           v56,
                           v57,
                           v58);
  v9 = 398;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_60;
  v19 = lpFile[0];
  v63 = 398;
  FileAttributesW = GetFileAttributesW(lpFile[0]);
  if ( FileAttributesW == -1 && GetLastError() != 2 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v22);
    v9 = 401;
LABEL_64:
    v8 = Sid;
    goto LABEL_125;
  }
  LastFailureAsHRESULT = 0;
  v63 = 401;
  if ( FileAttributesW != -1 )
    goto LABEL_78;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_500c1448b7193519884fd297f141796f_Traceguids, v19);
  LastFailureAsHRESULT = CBsString::SetPath(
                           (CBsString *)lpFile,
                           v7,
                           L"NTUSER.DAT",
                           v20,
                           ReferencedDomainName,
                           cchReferencedDomainName,
                           peUse,
                           v55,
                           v56,
                           v57,
                           v58);
  v9 = 405;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_60;
  v19 = lpFile[0];
  v63 = 405;
  v23 = GetFileAttributesW(lpFile[0]);
  if ( v23 == -1 && GetLastError() != 2 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v24);
    v9 = 408;
    goto LABEL_64;
  }
  LastFailureAsHRESULT = 0;
  v63 = 408;
  if ( v23 != -1 )
  {
LABEL_78:
    RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"__SAFEDOCS_LOADED_TEMP_HIVE");
    KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, L"__SAFEDOCS_LOADED_TEMP_HIVE", v19);
    v26 = KeyW < 0;
    if ( KeyW > 0 )
    {
      KeyW = (unsigned __int16)KeyW | 0x80070000;
      v26 = KeyW < 0;
    }
    if ( v26 )
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) == 0 )
      {
        goto LABEL_93;
      }
      v28 = 22;
      LODWORD(v29) = (_DWORD)a2;
    }
    else
    {
      v69 = 1;
      if ( (unsigned __int64)hKeya - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        RegCloseKey(hKeya);
        hKeya = 0;
      }
      KeyW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"__SAFEDOCS_LOADED_TEMP_HIVE", 0, 0x20019u, &hKeya);
      v30 = KeyW < 0;
      if ( KeyW > 0 )
      {
        KeyW = (unsigned __int16)KeyW | 0x80070000;
        v30 = KeyW < 0;
      }
      if ( !v30 )
        goto LABEL_93;
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) == 0 )
      {
        goto LABEL_93;
      }
      v28 = 23;
      v29 = L"__SAFEDOCS_LOADED_TEMP_HIVE";
    }
    WPP_SF_Sd(v27[2], v28, (unsigned int)&WPP_500c1448b7193519884fd297f141796f_Traceguids, (_DWORD)v29, KeyW);
LABEL_93:
    v3 = v68;
    goto LABEL_94;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_500c1448b7193519884fd297f141796f_Traceguids, v19);
  v8 = Sid;
  v63 = 412;
  LastFailureAsHRESULT = 1;
LABEL_126:
  if ( v7 )
    CoTaskMemFree(v7);
  CoTaskMemFree(v8);
  if ( v69 )
  {
    if ( (unsigned __int64)hKeya - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(hKeya);
      hKeya = 0;
    }
    if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(phkResult);
      phkResult = 0;
    }
    RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"__SAFEDOCS_LOADED_TEMP_HIVE");
  }
  v45 = (char *)pv;
  if ( pv )
  {
    for ( i = 0; i < v60; ++i )
    {
      v47 = 16LL * i;
      v48 = (LPVOID *)&v45[v47];
      if ( &v45[v47] && *v48 )
      {
        CoTaskMemFree(*v48);
        *v48 = 0;
        v45 = (char *)pv;
      }
      v49 = (LPVOID *)&v45[v47 + 8];
      if ( v49 && *v49 )
      {
        CoTaskMemFree(*v49);
        *v49 = 0;
        v45 = (char *)pv;
      }
    }
    CoTaskMemFree(v45);
    pv = 0;
    v60 = 0;
  }
  if ( v6 )
  {
    FreeUserProfileData((struct _UserProfileData *)v6);
    CoTaskMemFree(v6);
  }
  v50 = LastFailureAsHRESULT;
  CBsString::_Release((LPVOID *)v75);
  CBsString::_Release((LPVOID *)lpValueName);
  CBsString::_Release((LPVOID *)v78);
  CBsString::_Release((LPVOID *)lpFile);
  if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( (unsigned __int64)hKeya - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKeya);
    hKeya = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v50;
}

```

## disassembly

```asm
0x1800190bc  mov     [rsp-8+arg_18], rbx
0x1800190c1  push    rbp
0x1800190c2  push    rsi
0x1800190c3  push    rdi
0x1800190c4  push    r12
0x1800190c6  push    r13
0x1800190c8  push    r14
0x1800190ca  push    r15
0x1800190cc  lea     rbp, [rsp-2E0h]
0x1800190d4  sub     rsp, 3E0h
0x1800190db  mov     rax, cs:__security_cookie
0x1800190e2  xor     rax, rsp
0x1800190e5  mov     [rbp+310h+var_40], rax
0x1800190ec  mov     r15, r8
0x1800190ef  mov     [rbp+310h+var_348], r8
0x1800190f3  mov     rsi, rdx
0x1800190f6  mov     rbx, rcx
0x1800190f9  mov     r8d, 11Ah; unsigned __int16
0x1800190ff  lea     rdx, aGetuserprofile; "GetUserProfileData"
0x180019106  lea     rcx, [rsp+410h+var_398]; this
0x18001910b  mov     r9d, 1; unsigned __int16
0x180019111  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180019116  xor     r14d, r14d
0x180019119  test    r15, r15
0x18001911c  jz      short loc_180019121
0x18001911e  mov     [r15], r14
0x180019121  xorps   xmm0, xmm0
0x180019124  mov     [rbp+310h+lpFileName], r14
0x180019128  xor     eax, eax
0x18001912a  mov     [rsp+410h+Sid], r14
0x18001912f  xor     edx, edx; Val
0x180019131  mov     [rbp+310h+var_25E], rax
0x180019138  mov     r8d, 206h; Size
0x18001913e  mov     [rbp+310h+var_340], r14d
0x180019142  lea     rcx, [rbp+310h+var_24E]; void *
0x180019149  mov     [rbp+310h+var_350], 7
0x180019150  movups  [rbp+310h+var_27E], xmm0
0x180019157  mov     r13, r14
0x18001915a  mov     r12, r14
0x18001915d  movups  [rbp+310h+var_26E], xmm0
0x180019164  mov     rdi, r14
0x180019167  mov     [rbp+310h+Name], r14w
0x18001916f  mov     [rbp+310h+var_250], r14w
0x180019177  call    memset_0
0x18001917c  lea     rax, qword_180028260
0x180019183  mov     [rbp+310h+cchName], 15h
0x18001918a  xor     edx, edx; Val
0x18001918c  mov     [rbp+310h+var_328], 104h
0x180019193  lea     rcx, [rbp+310h+pSid]; void *
0x180019197  mov     [rsp+410h+hKey], r14
0x18001919c  mov     [rbp+310h+phkResult], r14
0x1800191a0  mov     [rbp+310h+lpFile], rax
0x1800191a4  lea     r8d, [rdx+48h]; Size
0x1800191a8  mov     [rbp+310h+var_300], r14
0x1800191ac  mov     [rbp+310h+var_2E8], rax
0x1800191b0  mov     [rbp+310h+var_2E0], r14
0x1800191b4  mov     [rbp+310h+lpValueName], rax
0x1800191b8  mov     [rbp+310h+var_2F0], r14
0x1800191bc  mov     [rbp+310h+var_318], rax
0x1800191c0  mov     [rbp+310h+var_310], r14
0x1800191c4  mov     [rbp+310h+var_330], r14
0x1800191c8  mov     [rbp+310h+pv], r14
0x1800191cc  mov     [rsp+410h+var_3A8], r14d
0x1800191d1  call    memset_0
0x1800191d6  mov     [rbp+310h+cbSid], 44h ; 'D'
0x1800191dd  mov     eax, 138h
0x1800191e2  test    rbx, rbx
0x1800191e5  jz      loc_180019B18
0x1800191eb  mov     [rsp+410h+var_394], ax
0x1800191f0  mov     eax, 139h
0x1800191f5  test    rsi, rsi
0x1800191f8  jz      loc_180019B18
0x1800191fe  mov     [rsp+410h+var_394], ax
0x180019203  mov     eax, 13Ah
0x180019208  test    r15, r15
0x18001920b  jz      loc_180019B18
0x180019211  lea     r8, [rsp+410h+Sid]; unsigned __int8 **
0x180019216  mov     [rsp+410h+var_398], r14d
0x18001921b  mov     rdx, rsi; lpSubKey
0x18001921e  mov     [rsp+410h+var_394], ax
0x180019223  mov     rcx, rbx; hKey
0x180019226  call    ?GetUserSid@@YAJQEAUHKEY__@@PEBGPEAPEAE@Z; GetUserSid(HKEY__ * const,ushort const *,uchar * *)
0x18001922b  test    eax, eax
0x18001922d  jns     short loc_180019280
0x18001922f  mov     rcx, cs:WPP_GLOBAL_Control
0x180019236  lea     rbx, WPP_GLOBAL_Control
0x18001923d  cmp     rcx, rbx
0x180019240  jz      short loc_180019264
0x180019242  mov     edi, 10000000h
0x180019247  test    [rcx+1Ch], edi
0x18001924a  jz      short loc_180019264
0x18001924c  mov     rcx, [rcx+10h]
0x180019250  lea     r8, WPP_500c1448b7193519884fd297f141796f_Traceguids
0x180019257  mov     edx, 0Bh
0x18001925c  mov     r9, rsi
0x18001925f  call    WPP_SF_S
0x180019264  mov     rdi, [rsp+410h+Sid]
0x180019269  mov     eax, 146h
0x18001926e  mov     [rsp+410h+var_394], ax
0x180019273  mov     [rsp+410h+var_398], 1
0x18001927b  jmp     loc_180019B25
0x180019280  mov     rdi, [rsp+410h+Sid]
0x180019285  mov     [rsp+410h+Sid], rdi
0x18001928a  test    rdi, rdi
0x18001928d  jnz     short loc_1800192E0
0x18001928f  mov     rcx, cs:WPP_GLOBAL_Control
0x180019296  lea     rbx, WPP_GLOBAL_Control
0x18001929d  cmp     rcx, rbx
0x1800192a0  jz      short loc_1800192C9
0x1800192a2  mov     edi, 10000000h
0x1800192a7  test    [rcx+1Ch], edi
0x1800192aa  jz      short loc_1800192C4
0x1800192ac  mov     rcx, [rcx+10h]
0x1800192b0  lea     r8, WPP_500c1448b7193519884fd297f141796f_Traceguids
0x1800192b7  mov     edx, 0Ch
0x1800192bc  mov     r9, rsi
0x1800192bf  call    WPP_SF_S
0x1800192c4  mov     rdi, [rsp+410h+Sid]
0x1800192c9  mov     eax, 14Ch
0x1800192ce  mov     [rsp+410h+var_398], 1
0x1800192d6  mov     [rsp+410h+var_394], ax
0x1800192db  jmp     loc_180019B25
0x1800192e0  lea     rax, [rbp+310h+var_350]
0x1800192e4  mov     rdx, rdi; Sid
0x1800192e7  mov     [rsp+410h+peUse], rax; unsigned __int16 *
0x1800192ec  lea     r9, [rbp+310h+cchName]; cchName
0x1800192f0  lea     rax, [rbp+310h+var_328]
0x1800192f4  xor     ecx, ecx; lpSystemName
0x1800192f6  mov     [rsp+410h+cchReferencedDomainName], rax; unsigned __int16 *
0x1800192fb  lea     r8, [rbp+310h+Name]; Name
0x180019302  lea     rax, [rbp+310h+var_250]
0x180019309  mov     [rsp+410h+ReferencedDomainName], rax; ReferencedDomainName
0x18001930e  call    cs:__imp_LookupAccountSidW
0x180019314  cmp     [rbp+310h+var_350], 1
0x180019318  jz      short loc_18001935E
0x18001931a  mov     rcx, cs:WPP_GLOBAL_Control
0x180019321  lea     rbx, WPP_GLOBAL_Control
0x180019328  cmp     rcx, rbx
0x18001932b  jz      short loc_180019354
0x18001932d  mov     edi, 10000000h
0x180019332  test    [rcx+1Ch], edi
0x180019335  jz      short loc_18001934F
0x180019337  mov     rcx, [rcx+10h]
0x18001933b  lea     r8, WPP_500c1448b7193519884fd297f141796f_Traceguids
0x180019342  mov     edx, 0Dh
0x180019347  mov     r9, rsi
0x18001934a  call    WPP_SF_S
0x18001934f  mov     rdi, [rsp+410h+Sid]
0x180019354  mov     eax, 15Ah
0x180019359  jmp     loc_1800192CE
0x18001935e  xor     edx, edx; DomainSid
0x180019360  lea     r9, [rbp+310h+cbSid]; cbSid
0x180019364  lea     r8, [rbp+310h+pSid]; pSid
0x180019368  lea     ecx, [rdx+16h]; WellKnownSidType
0x18001936b  call    cs:__imp_CreateWellKnownSid
0x180019371  test    eax, eax
0x180019373  jnz     short loc_180019388
0x180019375  call    GetLastFailureAsHRESULT
0x18001937a  mov     [rsp+410h+var_398], eax
0x18001937e  mov     eax, 15Fh
0x180019383  jmp     loc_180019B20
0x180019388  mov     eax, 15Fh
0x18001938d  mov     [rsp+410h+var_398], r14d
0x180019392  mov     rdx, rdi; pSid2
0x180019395  mov     [rsp+410h+var_394], ax
0x18001939a  lea     rcx, [rbp+310h+pSid]; pSid1
0x18001939e  call    cs:__imp_EqualSid
0x1800193a4  test    eax, eax
0x1800193a6  jz      short loc_1800193EC
0x1800193a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800193af  lea     rbx, WPP_GLOBAL_Control
0x1800193b6  cmp     rcx, rbx
0x1800193b9  jz      short loc_1800193E2
0x1800193bb  mov     edi, 10000000h
0x1800193c0  test    [rcx+1Ch], edi
0x1800193c3  jz      short loc_1800193DD
0x1800193c5  mov     rcx, [rcx+10h]
0x1800193c9  lea     r8, WPP_500c1448b7193519884fd297f141796f_Traceguids
0x1800193d0  mov     edx, 0Eh
0x1800193d5  mov     r9, rsi
0x1800193d8  call    WPP_SF_S
0x1800193dd  mov     rdi, [rsp+410h+Sid]
0x1800193e2  mov     eax, 165h
0x1800193e7  jmp     loc_1800192CE
0x1800193ec  lea     r9, [rbp+310h+var_2E8]; struct CBsString *
0x1800193f0  mov     rcx, rsi; unsigned __int16 *
0x1800193f3  lea     r8, [rbp+310h+Name]; unsigned __int16 *
0x1800193fa  lea     rdx, [rbp+310h+var_250]; unsigned __int16 *
0x180019401  call    ?GetFriendlyNameForUser@@YAJPEBG00PEAVCBsString@@@Z; GetFriendlyNameForUser(ushort const *,ushort const *,ushort const *,CBsString *)
0x180019406  mov     [rsp+410h+var_398], eax
0x18001940a  test    eax, eax
0x18001940c  mov     eax, 168h
0x180019411  js      loc_180019B20
0x180019417  lea     r8, [rbp+310h+lpFileName]; unsigned __int16 **
0x18001941b  mov     [rsp+410h+var_394], ax
0x180019420  mov     rdx, rsi; lpSubKey
0x180019423  mov     rcx, rbx; hKey
0x180019426  call    ?GetUserProfilePath@@YAJQEAUHKEY__@@PEBGPEAPEAG@Z; GetUserProfilePath(HKEY__ * const,ushort const *,ushort * *)
0x18001942b  mov     ecx, eax
0x18001942d  mov     [rsp+410h+var_398], eax
0x180019431  test    eax, eax
0x180019433  mov     eax, 16Ah
0x180019438  jns     short loc_180019443
0x18001943a  mov     r12, [rbp+310h+lpFileName]
0x18001943e  jmp     loc_180019B20
0x180019443  mov     [rsp+410h+var_394], ax
0x180019448  cmp     ecx, 1
0x18001944b  jnz     short loc_1800194A2
0x18001944d  mov     rcx, cs:WPP_GLOBAL_Control
0x180019454  lea     rbx, WPP_GLOBAL_Control
0x18001945b  cmp     rcx, rbx
0x18001945e  jz      short loc_180019487
0x180019460  mov     edi, 10000000h
0x180019465  test    [rcx+1Ch], edi
0x180019468  jz      short loc_180019482
0x18001946a  mov     rcx, [rcx+10h]
0x18001946e  lea     r8, WPP_500c1448b7193519884fd297f141796f_Traceguids
0x180019475  mov     edx, 0Fh
0x18001947a  mov     r9, rsi
0x18001947d  call    WPP_SF_S
0x180019482  mov     rdi, [rsp+410h+Sid]
0x180019487  mov     r12, [rbp+310h+lpFileName]
0x18001948b  mov     eax, 16Eh
0x180019490  mov     [rsp+410h+var_394], ax
0x180019495  mov     [rsp+410h+var_398], 1
0x18001949d  jmp     loc_180019B25
0x1800194a2  mov     r12, [rbp+310h+lpFileName]
0x1800194a6  mov     rcx, r12; lpFileName
0x1800194a9  call    cs:__imp_GetFileAttributesW
0x1800194af  cmp     eax, 0FFFFFFFFh
0x1800194b2  jnz     short loc_180019502
0x1800194b4  mov     rax, cs:WPP_GLOBAL_Control
0x1800194bb  lea     rbx, WPP_GLOBAL_Control
0x1800194c2  cmp     rax, rbx
0x1800194c5  jz      short loc_1800194F8
0x1800194c7  mov     edi, 10000000h
0x1800194cc  test    [rax+1Ch], edi
0x1800194cf  jz      short loc_1800194F3
0x1800194d1  call    cs:__imp_GetLastError
0x1800194d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800194de  mov     r9, rsi
0x1800194e1  mov     dword ptr [rsp+410h+cchReferencedDomainName], eax
0x1800194e5  mov     [rsp+410h+ReferencedDomainName], r12
0x1800194ea  mov     rcx, [rcx+10h]
0x1800194ee  call    WPP_SF_SSD
0x1800194f3  mov     rdi, [rsp+410h+Sid]
0x1800194f8  mov     eax, 176h
0x1800194fd  jmp     loc_1800192CE
0x180019502  mov     rcx, [rsp+410h+hKey]; hKey
0x180019507  lea     rax, [rcx-1]
0x18001950b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001950f  ja      short loc_18001951C
0x180019511  call    cs:__imp_RegCloseKey
0x180019517  mov     [rsp+410h+hKey], r14
0x18001951c  lea     rax, [rsp+410h+hKey]
0x180019521  mov     r9d, 20019h; samDesired
0x180019527  xor     r8d, r8d; ulOptions
0x18001952a  mov     [rsp+410h+ReferencedDomainName], rax; unsigned __int16 *
0x18001952f  mov     rdx, rsi; lpSubKey
0x180019532  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180019539  call    cs:__imp_RegOpenKeyExW
0x18001953f  mov     edi, 10000000h
0x180019544  lea     ecx, [rax-2]
0x180019547  cmp     ecx, 1
0x18001954a  jbe     short loc_180019599
0x18001954c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019553  lea     rbx, WPP_GLOBAL_Control
0x18001955a  cmp     rcx, rbx
0x18001955d  jz      loc_18001983F
0x180019563  test    [rcx+1Ch], edi
0x180019566  jz      loc_18001983F
0x18001956c  test    eax, eax
0x18001956e  jle     short loc_180019578
0x180019570  movzx   eax, ax
0x180019573  or      eax, 80070000h
0x180019578  mov     rcx, [rcx+10h]
0x18001957c  lea     r8, WPP_500c1448b7193519884fd297f141796f_Traceguids
0x180019583  mov     edx, 12h
0x180019588  mov     dword ptr [rsp+410h+ReferencedDomainName], eax
0x18001958c  mov     r9, rsi
0x18001958f  call    WPP_SF_Sd
0x180019594  jmp     loc_18001983F
0x180019599  mov     rcx, cs:WPP_GLOBAL_Control
0x1800195a0  lea     rbx, WPP_GLOBAL_Control
0x1800195a7  cmp     rcx, rbx
0x1800195aa  jz      short loc_1800195F2
0x1800195ac  test    [rcx+1Ch], edi
0x1800195af  jz      short loc_1800195D0
0x1800195b1  mov     rcx, [rcx+10h]
0x1800195b5  lea     r8, WPP_500c1448b7193519884fd297f141796f_Traceguids
0x1800195bc  mov     edx, 11h
0x1800195c1  mov     r9, rsi
0x1800195c4  call    WPP_SF_S
0x1800195c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800195d0  cmp     rcx, rbx
0x1800195d3  jz      short loc_1800195F2
0x1800195d5  test    [rcx+1Ch], edi
0x1800195d8  jz      short loc_1800195F2
0x1800195da  mov     rcx, [rcx+10h]
0x1800195de  lea     r8, WPP_500c1448b7193519884fd297f141796f_Traceguids
  ... truncated ...
```
