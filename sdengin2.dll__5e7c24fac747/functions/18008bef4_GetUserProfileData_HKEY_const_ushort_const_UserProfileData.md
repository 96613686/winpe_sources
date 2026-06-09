# GetUserProfileData(HKEY__ * const,ushort const *,_UserProfileData * *)

- ea: `0x18008bef4`
- end: `0x18008cac7`
- name: `?GetUserProfileData@@YAJQEAUHKEY__@@PEBGPEAPEAU_UserProfileData@@@Z`
- size: `3027`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, struct _UserProfileData **)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18008b924`

## callees

- `0x180008240`
- `0x180009a98`
- `0x180014394`
- `0x180021904`
- `0x18006fe84`
- `0x18006ff8c`
- `0x1800709ec`
- `0x1800885bc`
- `0x18008baec`
- `0x18008bba0`
- `0x18008bef4`
- `0x18008cad0`
- `0x18008cc70`
- `0x18008cf94`
- `0x18008d0d4`
- `0x18008f5d0`
- `0x18009a0bc`
- `0x18009a378`
- `0x18009ae34`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18008c2f5`
- `KERNEL32!GetLastError` at `0x18008c470`
- `KERNEL32!GetLastError` at `0x18008c526`
- `KERNEL32!GetLastError` at `0x18008c2f5`
- `KERNEL32!GetLastError` at `0x18008c470`
- `KERNEL32!GetLastError` at `0x18008c526`
- `KERNEL32!GetFileAttributesW` at `0x18008c2cd`
- `KERNEL32!GetFileAttributesW` at `0x18008c462`
- `KERNEL32!GetFileAttributesW` at `0x18008c518`
- `KERNEL32!GetFileAttributesW` at `0x18008c2cd`
- `KERNEL32!GetFileAttributesW` at `0x18008c462`
- `KERNEL32!GetFileAttributesW` at `0x18008c518`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008c344`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008c60d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008c69b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008c99e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008c9b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008ca6d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008ca86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008c344`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008c60d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008c69b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008c99e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008c9b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008ca6d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008ca86`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008c36c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008c635`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008c6c3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008c36c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008c635`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008c6c3`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18008c5a8`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18008c9cf`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18008c5a8`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18008c9cf`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18008c5bb`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18008c5bb`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18008c19e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18008c19e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18008c1d2`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18008c1d2`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18008c13e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18008c13e`
- `ole32!CoTaskMemFree` at `0x18008c983`
- `ole32!CoTaskMemFree` at `0x18008ca12`
- `ole32!CoTaskMemFree` at `0x18008ca31`
- `ole32!CoTaskMemFree` at `0x18008c983`
- `ole32!CoTaskMemFree` at `0x18008ca12`
- `ole32!CoTaskMemFree` at `0x18008ca31`
- `ole32!CoTaskMemAlloc` at `0x18008c81f`
- `ole32!CoTaskMemAlloc` at `0x18008c81f`

## string_xrefs

- `0x18008c597`: `__SAFEDOCS_LOADED_TEMP_HIVE`
- `0x18008c9c1`: `__SAFEDOCS_LOADED_TEMP_HIVE`

## pseudocode

```c
__int64 __fastcall GetUserProfileData(HKEY hKey, const unsigned __int16 *a2, struct _UserProfileData **a3)
{
  struct _UserProfileData **v3; // r15
  LPVOID v6; // r12
  __int16 v7; // ax
  __int64 v8; // rcx
  int UserProfilePath; // ecx
  const unsigned __int16 *v10; // r13
  LSTATUS v11; // eax
  PVOID *v12; // rcx
  const WCHAR *v13; // r14
  DWORD FileAttributesW; // r15d
  __int64 v15; // rcx
  __int16 v16; // ax
  DWORD v17; // r15d
  __int64 v18; // rcx
  int KeyW; // eax
  bool v20; // sf
  _QWORD *v21; // rcx
  int v22; // edx
  const WCHAR *v23; // r9
  bool v24; // sf
  HKEY v25; // rcx
  int v26; // eax
  int v27; // r8d
  bool v28; // sf
  __int64 v29; // rdi
  LPCWSTR v30; // r14
  int v31; // eax
  int v32; // r8d
  bool v33; // sf
  _BYTE *v34; // rax
  const unsigned __int16 *v35; // rdx
  char *v36; // rcx
  unsigned int i; // edi
  __int64 v38; // rbx
  unsigned int v39; // ebx
  LPDWORD cchReferencedDomainName; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *peUse; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v43; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v44; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v45; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v46; // [rsp+50h] [rbp-B0h]
  unsigned int v47; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKeya; // [rsp+68h] [rbp-98h] BYREF
  int LastFailureAsHRESULT; // [rsp+70h] [rbp-90h] BYREF
  __int16 v50; // [rsp+74h] [rbp-8Ch]
  __int16 v51; // [rsp+76h] [rbp-8Ah]
  LPVOID pv; // [rsp+A8h] [rbp-58h] BYREF
  HKEY phkResult; // [rsp+B0h] [rbp-50h] BYREF
  enum _SID_NAME_USE v54; // [rsp+B8h] [rbp-48h] BYREF
  struct _UserProfileData **v55; // [rsp+C0h] [rbp-40h]
  PSID pSid2; // [rsp+C8h] [rbp-38h]
  int v57; // [rsp+D0h] [rbp-30h]
  unsigned __int16 *v58; // [rsp+D8h] [rbp-28h] BYREF
  LPCWSTR lpFileName; // [rsp+E0h] [rbp-20h] BYREF
  DWORD v60; // [rsp+E8h] [rbp-18h] BYREF
  DWORD cchName; // [rsp+ECh] [rbp-14h] BYREF
  DWORD cbSid; // [rsp+F0h] [rbp-10h] BYREF
  PSID Sid; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int16 *v64[2]; // [rsp+100h] [rbp+0h] BYREF
  LPCWSTR lpFile[2]; // [rsp+110h] [rbp+10h] BYREF
  LPCWSTR lpValueName[2]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 *v67[2]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE pSid[80]; // [rsp+140h] [rbp+40h] BYREF
  WCHAR Name; // [rsp+190h] [rbp+90h] BYREF
  __int128 v70; // [rsp+192h] [rbp+92h]
  __int128 v71; // [rsp+1A2h] [rbp+A2h]
  __int64 v72; // [rsp+1B2h] [rbp+B2h]
  WCHAR ReferencedDomainName; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v74[526]; // [rsp+1C2h] [rbp+C2h] BYREF

  v3 = a3;
  v55 = a3;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "GetUserProfileData", 282, 1);
  if ( v3 )
    *v3 = 0;
  lpFileName = 0;
  pSid2 = 0;
  Sid = 0;
  v72 = 0;
  v57 = 0;
  v70 = 0;
  v6 = 0;
  v54 = SidTypeInvalid;
  v71 = 0;
  Name = 0;
  ReferencedDomainName = 0;
  memset_0(v74, 0, 0x206u);
  cchName = 21;
  v60 = 260;
  hKeya = 0;
  phkResult = 0;
  lpFile[0] = (LPCWSTR)qword_1800E8530;
  lpFile[1] = 0;
  v67[0] = (unsigned __int16 *)qword_1800E8530;
  v67[1] = 0;
  lpValueName[0] = (LPCWSTR)qword_1800E8530;
  lpValueName[1] = 0;
  v64[0] = (unsigned __int16 *)qword_1800E8530;
  v64[1] = 0;
  v58 = 0;
  pv = 0;
  v47 = 0;
  memset_0(pSid, 0, 0x48u);
  cbSid = 68;
  v7 = 312;
  if ( !hKey || (v50 = 312, v7 = 313, !a2) || (v50 = 313, v7 = 314, !v3) )
  {
    LastFailureAsHRESULT = -2147024809;
    goto LABEL_5;
  }
  LastFailureAsHRESULT = 0;
  v50 = 314;
  if ( (int)GetUserSid(hKey, a2, (unsigned __int8 **)&Sid) >= 0 )
  {
    pSid2 = Sid;
    if ( !Sid )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)((_DWORD)Sid + 12),
          &WPP_500c1448b7193519884fd297f141796f_Traceguids,
          a2);
      LastFailureAsHRESULT = 1;
      v7 = 332;
      goto LABEL_118;
    }
    LookupAccountSidW(0, Sid, &Name, &cchName, &ReferencedDomainName, &v60, &v54);
    if ( v54 != SidTypeUser )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_500c1448b7193519884fd297f141796f_Traceguids, a2);
      LastFailureAsHRESULT = 1;
      v7 = 346;
      goto LABEL_118;
    }
    if ( !CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8);
      v7 = 351;
      goto LABEL_5;
    }
    LastFailureAsHRESULT = 0;
    v50 = 351;
    if ( EqualSid(pSid, pSid2) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_500c1448b7193519884fd297f141796f_Traceguids, a2);
      LastFailureAsHRESULT = 1;
      v7 = 357;
      goto LABEL_118;
    }
    LastFailureAsHRESULT = GetFriendlyNameForUser(a2, &ReferencedDomainName, &Name, (struct CBsString *)v67);
    v7 = 360;
    if ( LastFailureAsHRESULT < 0
      || (v50 = 360,
          UserProfilePath = GetUserProfilePath(hKey, a2, (unsigned __int16 **)&lpFileName),
          LastFailureAsHRESULT = UserProfilePath,
          v7 = 362,
          UserProfilePath < 0) )
    {
LABEL_5:
      v51 = v7;
      goto LABEL_119;
    }
    v50 = 362;
    if ( UserProfilePath == 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_500c1448b7193519884fd297f141796f_Traceguids, a2);
      LastFailureAsHRESULT = 1;
      v7 = 366;
      goto LABEL_118;
    }
    v10 = lpFileName;
    if ( GetFileAttributesW(lpFileName) == -1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
      {
        LODWORD(cchReferencedDomainName) = GetLastError();
        WPP_SF_SSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          (unsigned int)&WPP_500c1448b7193519884fd297f141796f_Traceguids,
          (_DWORD)a2,
          (__int64)v10,
          cchReferencedDomainName);
      }
      LastFailureAsHRESULT = 1;
      v7 = 374;
      goto LABEL_118;
    }
    if ( (unsigned __int64)hKeya - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(hKeya);
      hKeya = 0;
    }
    v11 = RegOpenKeyExW(HKEY_USERS, a2, 0, 0x20019u, &hKeya);
    if ( (unsigned int)(v11 - 2) > 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          (unsigned int)&WPP_500c1448b7193519884fd297f141796f_Traceguids,
          (_DWORD)a2,
          v11);
      goto LABEL_88;
    }
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_500c1448b7193519884fd297f141796f_Traceguids, a2);
        v12 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x10000000) != 0 )
        WPP_SF_S(v12[2], 19, &WPP_500c1448b7193519884fd297f141796f_Traceguids, v10);
    }
    LastFailureAsHRESULT = CBsString::SetPath(
                             (CBsString *)lpFile,
                             v10,
                             L"NTUSER.MAN",
                             0,
                             0,
                             0,
                             peUse,
                             v43,
                             v44,
                             v45,
                             v46);
    v7 = 398;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_5;
    v13 = lpFile[0];
    v50 = 398;
    FileAttributesW = GetFileAttributesW(lpFile[0]);
    if ( FileAttributesW == -1 && GetLastError() != 2 )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v15);
      v16 = 401;
LABEL_58:
      v51 = v16;
      goto LABEL_119;
    }
    LastFailureAsHRESULT = 0;
    v50 = 401;
    if ( FileAttributesW == -1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_500c1448b7193519884fd297f141796f_Traceguids, v13);
      LastFailureAsHRESULT = CBsString::SetPath(
                               (CBsString *)lpFile,
                               v10,
                               L"NTUSER.DAT",
                               0,
                               0,
                               0,
                               peUse,
                               v43,
                               v44,
                               v45,
                               v46);
      v7 = 405;
      if ( LastFailureAsHRESULT < 0 )
        goto LABEL_5;
      v13 = lpFile[0];
      v50 = 405;
      v17 = GetFileAttributesW(lpFile[0]);
      if ( v17 == -1 && GetLastError() != 2 )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v18);
        v16 = 408;
        goto LABEL_58;
      }
      LastFailureAsHRESULT = 0;
      v50 = 408;
      if ( v17 == -1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_500c1448b7193519884fd297f141796f_Traceguids, v13);
        LastFailureAsHRESULT = 1;
        v7 = 412;
        goto LABEL_118;
      }
    }
    RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"__SAFEDOCS_LOADED_TEMP_HIVE");
    KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, L"__SAFEDOCS_LOADED_TEMP_HIVE", v13);
    v20 = KeyW < 0;
    if ( KeyW > 0 )
    {
      KeyW = (unsigned __int16)KeyW | 0x80070000;
      v20 = KeyW < 0;
    }
    if ( v20 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) == 0 )
        goto LABEL_87;
      v22 = 22;
      LODWORD(v23) = (_DWORD)a2;
    }
    else
    {
      v57 = 1;
      if ( (unsigned __int64)hKeya - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        RegCloseKey(hKeya);
        hKeya = 0;
      }
      KeyW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"__SAFEDOCS_LOADED_TEMP_HIVE", 0, 0x20019u, &hKeya);
      v24 = KeyW < 0;
      if ( KeyW > 0 )
      {
        KeyW = (unsigned __int16)KeyW | 0x80070000;
        v24 = KeyW < 0;
      }
      if ( !v24 )
        goto LABEL_87;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) == 0 )
        goto LABEL_87;
      v22 = 23;
      v23 = L"__SAFEDOCS_LOADED_TEMP_HIVE";
    }
    WPP_SF_Sd(v21[2], v22, (unsigned int)&WPP_500c1448b7193519884fd297f141796f_Traceguids, (_DWORD)v23, KeyW);
LABEL_87:
    v3 = v55;
LABEL_88:
    v25 = hKeya;
    if ( hKeya )
    {
      if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        RegCloseKey(phkResult);
        v25 = hKeya;
        phkResult = 0;
      }
      v26 = RegOpenKeyExW(
              v25,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Shell Folders",
              0,
              0x20019u,
              &phkResult);
      v28 = v26 < 0;
      if ( v26 > 0 )
      {
        v26 = (unsigned __int16)v26 | 0x80070000;
        v28 = v26 < 0;
      }
      if ( v28 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
        WPP_SF_SSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          v27,
          (_DWORD)a2,
          (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Shell Folders",
          v26);
    }
    LastFailureAsHRESULT = CBsString::Set((CBsString *)lpValueName, &FOLDERID_Libraries);
    v7 = 453;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_5;
    v29 = 64;
    v50 = 453;
    if ( phkResult )
    {
      v30 = lpValueName[0];
      v31 = ReadStringFromRegistry(phkResult, lpValueName[0], &v58, 0);
      if ( v31 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_SSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, v32, (_DWORD)a2, (__int64)v30, v31);
        LastFailureAsHRESULT = CBsString::SetPath(
                                 (CBsString *)v64,
                                 v10,
                                 L"AppData\\Roaming\\Microsoft\\Windows\\Libraries",
                                 0,
                                 0,
                                 0,
                                 peUse,
                                 v43,
                                 v44,
                                 v45,
                                 v46);
        v7 = 466;
        if ( LastFailureAsHRESULT < 0 )
          goto LABEL_5;
        v50 = 466;
        LastFailureAsHRESULT = SdSafeDuplicateStr(&v58, v64[0]);
        v7 = 467;
        if ( LastFailureAsHRESULT < 0 )
          goto LABEL_5;
        v50 = 467;
      }
      LastFailureAsHRESULT = GetUserShellPaths(a2, v10, phkResult, &v47, (struct SHELL_FOLDER_PATH **)&pv);
      v33 = LastFailureAsHRESULT < 0;
      v7 = 470;
    }
    else
    {
      LastFailureAsHRESULT = CBsString::SetPath(
                               (CBsString *)v64,
                               v10,
                               L"AppData\\Roaming\\Microsoft\\Windows\\Libraries",
                               0,
                               0,
                               0,
                               peUse,
                               v43,
                               v44,
                               v45,
                               v46);
      v7 = 474;
      if ( LastFailureAsHRESULT < 0 )
        goto LABEL_5;
      v50 = 474;
      LastFailureAsHRESULT = SdSafeDuplicateStr(&v58, v64[0]);
      v7 = 475;
      if ( LastFailureAsHRESULT < 0 )
        goto LABEL_5;
      v50 = 475;
      LastFailureAsHRESULT = GetUserShellPaths(a2, v10, 0, &v47, (struct SHELL_FOLDER_PATH **)&pv);
      v33 = LastFailureAsHRESULT < 0;
      v7 = 476;
    }
    if ( !v33 )
    {
      v50 = v7;
      v6 = CoTaskMemAlloc(0x40u);
      v7 = 485;
      if ( v6 )
      {
        v50 = 485;
        v34 = v6;
        LastFailureAsHRESULT = 0;
        do
        {
          *v34++ = 0;
          --v29;
        }
        while ( v29 );
        *(_QWORD *)v6 = pSid2;
        pSid2 = 0;
        *((_DWORD *)v6 + 2) = v54 == SidTypeUser;
        LastFailureAsHRESULT = SdSafeDuplicateStr((unsigned __int16 **)v6 + 2, a2);
        v7 = 493;
        if ( LastFailureAsHRESULT >= 0 )
        {
          v35 = v67[0];
          v50 = 493;
          *((_QWORD *)v6 + 5) = v58;
          *((_QWORD *)v6 + 3) = v10;
          *((_QWORD *)v6 + 6) = pv;
          pv = 0;
          *((_DWORD *)v6 + 14) = v47;
          v47 = 0;
          lpFileName = 0;
          LastFailureAsHRESULT = SdSafeDuplicateStr((unsigned __int16 **)v6 + 4, v35);
          v7 = 507;
          if ( LastFailureAsHRESULT >= 0 )
          {
            *v3 = (struct _UserProfileData *)v6;
            v6 = 0;
LABEL_118:
            v50 = v7;
            goto LABEL_119;
          }
        }
      }
      else
      {
        LastFailureAsHRESULT = -2147024882;
      }
    }
    goto LABEL_5;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_500c1448b7193519884fd297f141796f_Traceguids, a2);
  LastFailureAsHRESULT = 1;
  v50 = 326;
  pSid2 = Sid;
LABEL_119:
  SdFreeString((unsigned __int16 **)&lpFileName);
  CoTaskMemFree(pSid2);
  if ( v57 )
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
  v36 = (char *)pv;
  if ( pv )
  {
    for ( i = 0; i < v47; ++i )
    {
      v38 = 16LL * i;
      SdFreeString((unsigned __int16 **)&v36[v38]);
      SdFreeString((unsigned __int16 **)((char *)pv + v38 + 8));
      v36 = (char *)pv;
    }
    CoTaskMemFree(v36);
    pv = 0;
    v47 = 0;
  }
  if ( v6 )
  {
    FreeUserProfileData((struct _UserProfileData *)v6);
    CoTaskMemFree(v6);
  }
  v39 = LastFailureAsHRESULT;
  CBsString::_Release((CBsString *)v64);
  CBsString::_Release((CBsString *)lpValueName);
  CBsString::_Release((CBsString *)v67);
  CBsString::_Release((CBsString *)lpFile);
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
  return v39;
}

```

## disassembly

```asm
0x18008bef4  mov     [rsp-8+arg_18], rbx
0x18008bef9  push    rbp
0x18008befa  push    rsi
0x18008befb  push    rdi
0x18008befc  push    r12
0x18008befe  push    r13
0x18008bf00  push    r14
0x18008bf02  push    r15
0x18008bf04  lea     rbp, [rsp-2E0h]
0x18008bf0c  sub     rsp, 3E0h
0x18008bf13  mov     rax, cs:__security_cookie
0x18008bf1a  xor     rax, rsp
0x18008bf1d  mov     [rbp+310h+var_40], rax
0x18008bf24  mov     r15, r8
0x18008bf27  mov     [rbp+310h+var_350], r8
0x18008bf2b  mov     rsi, rdx
0x18008bf2e  mov     rbx, rcx
0x18008bf31  mov     r8d, 11Ah; unsigned __int16
0x18008bf37  lea     rdx, aGetuserprofile; "GetUserProfileData"
0x18008bf3e  lea     rcx, [rsp+410h+var_3A0]; this
0x18008bf43  mov     r9d, 1; unsigned __int16
0x18008bf49  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18008bf4e  xor     r14d, r14d
0x18008bf51  test    r15, r15
0x18008bf54  jz      short loc_18008BF59
0x18008bf56  mov     [r15], r14
0x18008bf59  mov     rax, r14
0x18008bf5c  mov     [rbp+310h+lpFileName], r14
0x18008bf60  xorps   xmm0, xmm0
0x18008bf63  mov     [rbp+310h+pSid2], rax
0x18008bf67  xor     edx, edx; Val
0x18008bf69  mov     [rbp+310h+Sid], rax
0x18008bf6d  mov     r8d, 206h; Size
0x18008bf73  mov     [rbp+310h+var_25E], rax
0x18008bf7a  lea     rcx, [rbp+310h+var_24E]; void *
0x18008bf81  mov     [rbp+310h+var_340], r14d
0x18008bf85  movups  [rbp+310h+var_27E], xmm0
0x18008bf8c  mov     r12, r14
0x18008bf8f  mov     [rbp+310h+var_358], 7
0x18008bf96  movups  [rbp+310h+var_26E], xmm0
0x18008bf9d  mov     [rbp+310h+Name], r14w
0x18008bfa5  mov     [rbp+310h+var_250], r14w
0x18008bfad  call    memset_0
0x18008bfb2  lea     rax, qword_1800E8530
0x18008bfb9  mov     [rbp+310h+cchName], 15h
0x18008bfc0  xor     edx, edx; Val
0x18008bfc2  mov     [rbp+310h+var_328], 104h
0x18008bfc9  lea     rcx, [rbp+310h+pSid]; void *
0x18008bfcd  mov     [rsp+410h+hKey], r14
0x18008bfd2  mov     [rbp+310h+phkResult], r14
0x18008bfd6  mov     [rbp+310h+lpFile], rax
0x18008bfda  lea     r8d, [rdx+48h]; Size
0x18008bfde  mov     [rbp+310h+var_2F8], r14
0x18008bfe2  mov     [rbp+310h+var_2E0], rax
0x18008bfe6  mov     [rbp+310h+var_2D8], r14
0x18008bfea  mov     [rbp+310h+lpValueName], rax
0x18008bfee  mov     [rbp+310h+var_2E8], r14
0x18008bff2  mov     [rbp+310h+var_310], rax
0x18008bff6  mov     [rbp+310h+var_308], r14
0x18008bffa  mov     [rbp+310h+var_338], r14
0x18008bffe  mov     [rbp+310h+pv], r14
0x18008c002  mov     [rsp+410h+var_3B0], r14d
0x18008c007  call    memset_0
0x18008c00c  mov     [rbp+310h+cbSid], 44h ; 'D'
0x18008c013  mov     eax, 138h
0x18008c018  test    rbx, rbx
0x18008c01b  jnz     short loc_18008C02F
0x18008c01d  mov     [rsp+410h+var_3A0], 80070057h
0x18008c025  mov     [rsp+410h+var_39A], ax
0x18008c02a  jmp     loc_18008C976
0x18008c02f  mov     [rsp+410h+var_39C], ax
0x18008c034  mov     eax, 139h
0x18008c039  test    rsi, rsi
0x18008c03c  jz      short loc_18008C01D
0x18008c03e  mov     [rsp+410h+var_39C], ax
0x18008c043  mov     eax, 13Ah
0x18008c048  test    r15, r15
0x18008c04b  jz      short loc_18008C01D
0x18008c04d  lea     r8, [rbp+310h+Sid]; unsigned __int8 **
0x18008c051  mov     [rsp+410h+var_3A0], r14d
0x18008c056  mov     rdx, rsi; lpSubKey
0x18008c059  mov     [rsp+410h+var_39C], ax
0x18008c05e  mov     rcx, rbx; hKey
0x18008c061  call    ?GetUserSid@@YAJQEAUHKEY__@@PEBGPEAPEAE@Z; GetUserSid(HKEY__ * const,ushort const *,uchar * *)
0x18008c066  test    eax, eax
0x18008c068  jns     short loc_18008C0BE
0x18008c06a  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c071  lea     rbx, WPP_GLOBAL_Control
0x18008c078  cmp     rcx, rbx
0x18008c07b  jz      short loc_18008C09F
0x18008c07d  mov     edi, 10000000h
0x18008c082  test    [rcx+1Ch], edi
0x18008c085  jz      short loc_18008C09F
0x18008c087  mov     rcx, [rcx+10h]
0x18008c08b  lea     r8, WPP_500c1448b7193519884fd297f141796f_Traceguids
0x18008c092  mov     edx, 0Bh
0x18008c097  mov     r9, rsi
0x18008c09a  call    WPP_SF_S
0x18008c09f  mov     eax, 146h
0x18008c0a4  mov     [rsp+410h+var_3A0], 1
0x18008c0ac  mov     [rsp+410h+var_39C], ax
0x18008c0b1  mov     rax, [rbp+310h+Sid]
0x18008c0b5  mov     [rbp+310h+pSid2], rax
0x18008c0b9  jmp     loc_18008C976
0x18008c0be  mov     rax, [rbp+310h+Sid]
0x18008c0c2  mov     [rbp+310h+pSid2], rax
0x18008c0c6  test    rax, rax
0x18008c0c9  jnz     short loc_18008C110
0x18008c0cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c0d2  lea     rbx, WPP_GLOBAL_Control
0x18008c0d9  cmp     rcx, rbx
0x18008c0dc  jz      short loc_18008C0FE
0x18008c0de  mov     edi, 10000000h
0x18008c0e3  test    [rcx+1Ch], edi
0x18008c0e6  jz      short loc_18008C0FE
0x18008c0e8  mov     rcx, [rcx+10h]
0x18008c0ec  lea     edx, [rax+0Ch]
0x18008c0ef  mov     r9, rsi
0x18008c0f2  lea     r8, WPP_500c1448b7193519884fd297f141796f_Traceguids
0x18008c0f9  call    WPP_SF_S
0x18008c0fe  mov     [rsp+410h+var_3A0], 1
0x18008c106  mov     eax, 14Ch
0x18008c10b  jmp     loc_18008C971
0x18008c110  lea     rcx, [rbp+310h+var_358]
0x18008c114  mov     rdx, rax; Sid
0x18008c117  mov     [rsp+410h+peUse], rcx; unsigned __int16 *
0x18008c11c  lea     r9, [rbp+310h+cchName]; cchName
0x18008c120  lea     rcx, [rbp+310h+var_328]
0x18008c124  mov     [rsp+410h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x18008c129  lea     r8, [rbp+310h+Name]; Name
0x18008c130  lea     rcx, [rbp+310h+var_250]
0x18008c137  mov     [rsp+410h+ReferencedDomainName], rcx; ReferencedDomainName
0x18008c13c  xor     ecx, ecx; lpSystemName
0x18008c13e  call    cs:__imp_LookupAccountSidW
0x18008c144  cmp     [rbp+310h+var_358], 1
0x18008c148  jz      short loc_18008C191
0x18008c14a  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c151  lea     rbx, WPP_GLOBAL_Control
0x18008c158  cmp     rcx, rbx
0x18008c15b  jz      short loc_18008C17F
0x18008c15d  mov     edi, 10000000h
0x18008c162  test    [rcx+1Ch], edi
0x18008c165  jz      short loc_18008C17F
0x18008c167  mov     rcx, [rcx+10h]
0x18008c16b  lea     r8, WPP_500c1448b7193519884fd297f141796f_Traceguids
0x18008c172  mov     edx, 0Dh
0x18008c177  mov     r9, rsi
0x18008c17a  call    WPP_SF_S
0x18008c17f  mov     [rsp+410h+var_3A0], 1
0x18008c187  mov     eax, 15Ah
0x18008c18c  jmp     loc_18008C971
0x18008c191  xor     edx, edx; DomainSid
0x18008c193  lea     r9, [rbp+310h+cbSid]; cbSid
0x18008c197  lea     r8, [rbp+310h+pSid]; pSid
0x18008c19b  lea     ecx, [rdx+16h]; WellKnownSidType
0x18008c19e  call    cs:__imp_CreateWellKnownSid
0x18008c1a4  test    eax, eax
0x18008c1a6  jnz     short loc_18008C1BB
0x18008c1a8  call    GetLastFailureAsHRESULT
0x18008c1ad  mov     [rsp+410h+var_3A0], eax
0x18008c1b1  mov     eax, 15Fh
0x18008c1b6  jmp     loc_18008C025
0x18008c1bb  mov     rdx, [rbp+310h+pSid2]; pSid2
0x18008c1bf  lea     rcx, [rbp+310h+pSid]; pSid1
0x18008c1c3  mov     eax, 15Fh
0x18008c1c8  mov     [rsp+410h+var_3A0], r14d
0x18008c1cd  mov     [rsp+410h+var_39C], ax
0x18008c1d2  call    cs:__imp_EqualSid
0x18008c1d8  test    eax, eax
0x18008c1da  jz      short loc_18008C223
0x18008c1dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c1e3  lea     rbx, WPP_GLOBAL_Control
0x18008c1ea  cmp     rcx, rbx
0x18008c1ed  jz      short loc_18008C211
0x18008c1ef  mov     edi, 10000000h
0x18008c1f4  test    [rcx+1Ch], edi
0x18008c1f7  jz      short loc_18008C211
0x18008c1f9  mov     rcx, [rcx+10h]
0x18008c1fd  lea     r8, WPP_500c1448b7193519884fd297f141796f_Traceguids
0x18008c204  mov     edx, 0Eh
0x18008c209  mov     r9, rsi
0x18008c20c  call    WPP_SF_S
0x18008c211  mov     [rsp+410h+var_3A0], 1
0x18008c219  mov     eax, 165h
0x18008c21e  jmp     loc_18008C971
0x18008c223  lea     r9, [rbp+310h+var_2E0]; struct CBsString *
0x18008c227  mov     rcx, rsi; unsigned __int16 *
0x18008c22a  lea     r8, [rbp+310h+Name]; unsigned __int16 *
0x18008c231  lea     rdx, [rbp+310h+var_250]; unsigned __int16 *
0x18008c238  call    ?GetFriendlyNameForUser@@YAJPEBG00PEAVCBsString@@@Z; GetFriendlyNameForUser(ushort const *,ushort const *,ushort const *,CBsString *)
0x18008c23d  mov     [rsp+410h+var_3A0], eax
0x18008c241  test    eax, eax
0x18008c243  mov     eax, 168h
0x18008c248  js      loc_18008C025
0x18008c24e  lea     r8, [rbp+310h+lpFileName]; unsigned __int16 **
0x18008c252  mov     [rsp+410h+var_39C], ax
0x18008c257  mov     rdx, rsi; lpSubKey
0x18008c25a  mov     rcx, rbx; hKey
0x18008c25d  call    ?GetUserProfilePath@@YAJQEAUHKEY__@@PEBGPEAPEAG@Z; GetUserProfilePath(HKEY__ * const,ushort const *,ushort * *)
0x18008c262  mov     ecx, eax
0x18008c264  mov     [rsp+410h+var_3A0], eax
0x18008c268  test    eax, eax
0x18008c26a  mov     eax, 16Ah
0x18008c26f  js      loc_18008C025
0x18008c275  mov     [rsp+410h+var_39C], ax
0x18008c27a  cmp     ecx, 1
0x18008c27d  jnz     short loc_18008C2C6
0x18008c27f  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c286  lea     rbx, WPP_GLOBAL_Control
0x18008c28d  cmp     rcx, rbx
0x18008c290  jz      short loc_18008C2B4
0x18008c292  mov     edi, 10000000h
0x18008c297  test    [rcx+1Ch], edi
0x18008c29a  jz      short loc_18008C2B4
0x18008c29c  mov     rcx, [rcx+10h]
0x18008c2a0  lea     r8, WPP_500c1448b7193519884fd297f141796f_Traceguids
0x18008c2a7  mov     edx, 0Fh
0x18008c2ac  mov     r9, rsi
0x18008c2af  call    WPP_SF_S
0x18008c2b4  mov     [rsp+410h+var_3A0], 1
0x18008c2bc  mov     eax, 16Eh
0x18008c2c1  jmp     loc_18008C971
0x18008c2c6  mov     r13, [rbp+310h+lpFileName]
0x18008c2ca  mov     rcx, r13; lpFileName
0x18008c2cd  call    cs:__imp_GetFileAttributesW
0x18008c2d3  cmp     eax, 0FFFFFFFFh
0x18008c2d6  jnz     short loc_18008C335
0x18008c2d8  mov     rax, cs:WPP_GLOBAL_Control
0x18008c2df  lea     rbx, WPP_GLOBAL_Control
0x18008c2e6  cmp     rax, rbx
0x18008c2e9  jz      short loc_18008C323
0x18008c2eb  mov     edi, 10000000h
0x18008c2f0  test    [rax+1Ch], edi
0x18008c2f3  jz      short loc_18008C323
0x18008c2f5  call    cs:__imp_GetLastError
0x18008c2fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c302  lea     r8, WPP_500c1448b7193519884fd297f141796f_Traceguids
0x18008c309  mov     dword ptr [rsp+410h+cchReferencedDomainName], eax
0x18008c30d  mov     edx, 10h
0x18008c312  mov     r9, rsi
0x18008c315  mov     [rsp+410h+ReferencedDomainName], r13
0x18008c31a  mov     rcx, [rcx+10h]
0x18008c31e  call    WPP_SF_SSD
0x18008c323  mov     [rsp+410h+var_3A0], 1
0x18008c32b  mov     eax, 176h
0x18008c330  jmp     loc_18008C971
0x18008c335  mov     rcx, [rsp+410h+hKey]; hKey
0x18008c33a  lea     rax, [rcx-1]
0x18008c33e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008c342  ja      short loc_18008C34F
0x18008c344  call    cs:__imp_RegCloseKey
0x18008c34a  mov     [rsp+410h+hKey], r14
0x18008c34f  lea     rax, [rsp+410h+hKey]
0x18008c354  mov     r9d, 20019h; samDesired
0x18008c35a  xor     r8d, r8d; ulOptions
0x18008c35d  mov     [rsp+410h+ReferencedDomainName], rax; phkResult
0x18008c362  mov     rdx, rsi; lpSubKey
0x18008c365  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18008c36c  call    cs:__imp_RegOpenKeyExW
0x18008c372  mov     edi, 10000000h
0x18008c377  lea     ecx, [rax-2]
0x18008c37a  cmp     ecx, 1
0x18008c37d  jbe     short loc_18008C3CC
0x18008c37f  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c386  lea     rbx, WPP_GLOBAL_Control
0x18008c38d  cmp     rcx, rbx
0x18008c390  jz      loc_18008C67C
0x18008c396  test    [rcx+1Ch], edi
0x18008c399  jz      loc_18008C67C
0x18008c39f  test    eax, eax
0x18008c3a1  jle     short loc_18008C3AB
0x18008c3a3  movzx   eax, ax
0x18008c3a6  or      eax, 80070000h
0x18008c3ab  mov     rcx, [rcx+10h]
0x18008c3af  lea     r8, WPP_500c1448b7193519884fd297f141796f_Traceguids
0x18008c3b6  mov     edx, 12h
0x18008c3bb  mov     dword ptr [rsp+410h+ReferencedDomainName], eax
0x18008c3bf  mov     r9, rsi
0x18008c3c2  call    WPP_SF_Sd
0x18008c3c7  jmp     loc_18008C67C
0x18008c3cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c3d3  lea     rbx, WPP_GLOBAL_Control
0x18008c3da  cmp     rcx, rbx
0x18008c3dd  jz      short loc_18008C425
0x18008c3df  test    [rcx+1Ch], edi
0x18008c3e2  jz      short loc_18008C403
0x18008c3e4  mov     rcx, [rcx+10h]
0x18008c3e8  lea     r8, WPP_500c1448b7193519884fd297f141796f_Traceguids
0x18008c3ef  mov     edx, 11h
0x18008c3f4  mov     r9, rsi
0x18008c3f7  call    WPP_SF_S
0x18008c3fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c403  cmp     rcx, rbx
0x18008c406  jz      short loc_18008C425
0x18008c408  test    [rcx+1Ch], edi
0x18008c40b  jz      short loc_18008C425
0x18008c40d  mov     rcx, [rcx+10h]
0x18008c411  lea     r8, WPP_500c1448b7193519884fd297f141796f_Traceguids
0x18008c418  mov     edx, 13h
0x18008c41d  mov     r9, r13
  ... truncated ...
```
