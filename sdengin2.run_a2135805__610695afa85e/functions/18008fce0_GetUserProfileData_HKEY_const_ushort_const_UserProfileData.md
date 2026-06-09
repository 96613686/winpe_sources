# GetUserProfileData(HKEY__ * const,ushort const *,_UserProfileData * *)

- ea: `0x18008fce0`
- end: `0x180090950`
- name: `?GetUserProfileData@@YAJQEAUHKEY__@@PEBGPEAPEAU_UserProfileData@@@Z`
- size: `3184`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, struct _UserProfileData **)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18008f6dc`

## callees

- `0x1800083e4`
- `0x180009d0c`
- `0x180014c30`
- `0x180022540`
- `0x180072e08`
- `0x180072f14`
- `0x1800739f8`
- `0x18008c040`
- `0x18008f8b0`
- `0x18008f970`
- `0x18008fce0`
- `0x180090958`
- `0x180090b04`
- `0x180090e40`
- `0x180090f90`
- `0x1800935fc`
- `0x18009e750`
- `0x18009ea34`
- `0x18009f560`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800900f9`
- `KERNEL32!GetLastError` at `0x18009028c`
- `KERNEL32!GetLastError` at `0x18009034e`
- `KERNEL32!GetLastError` at `0x1800900f9`
- `KERNEL32!GetLastError` at `0x18009028c`
- `KERNEL32!GetLastError` at `0x18009034e`
- `KERNEL32!GetFileAttributesW` at `0x1800900cb`
- `KERNEL32!GetFileAttributesW` at `0x180090278`
- `KERNEL32!GetFileAttributesW` at `0x18009033a`
- `KERNEL32!GetFileAttributesW` at `0x1800900cb`
- `KERNEL32!GetFileAttributesW` at `0x180090278`
- `KERNEL32!GetFileAttributesW` at `0x18009033a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009014e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180090447`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800904e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800907fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009081b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800908e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180090908`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009014e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180090447`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800904e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800907fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009081b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800908e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180090908`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009017c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180090475`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009050f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009017c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180090475`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009050f`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800903d6`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180090839`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800903d6`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180090839`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800903ef`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800903ef`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18008ff90`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18008ff90`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18008ffca`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18008ffca`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18008ff2a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18008ff2a`
- `ole32!CoTaskMemFree` at `0x1800907db`
- `ole32!CoTaskMemFree` at `0x180090882`
- `ole32!CoTaskMemFree` at `0x1800908a7`
- `ole32!CoTaskMemFree` at `0x1800907db`
- `ole32!CoTaskMemFree` at `0x180090882`
- `ole32!CoTaskMemFree` at `0x1800908a7`
- `ole32!CoTaskMemAlloc` at `0x180090671`
- `ole32!CoTaskMemAlloc` at `0x180090671`

## string_xrefs

- `0x1800903c5`: `__SAFEDOCS_LOADED_TEMP_HIVE`
- `0x18009082b`: `__SAFEDOCS_LOADED_TEMP_HIVE`

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
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "GetUserProfileData", 0x11Au, 1u);
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
  lpFile[0] = (LPCWSTR)qword_1800EE510;
  lpFile[1] = 0;
  v67[0] = (unsigned __int16 *)qword_1800EE510;
  v67[1] = 0;
  lpValueName[0] = (LPCWSTR)qword_1800EE510;
  lpValueName[1] = 0;
  v64[0] = (unsigned __int16 *)qword_1800EE510;
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
0x18008fce0  mov     [rsp-8+arg_18], rbx
0x18008fce5  push    rbp
0x18008fce6  push    rsi
0x18008fce7  push    rdi
0x18008fce8  push    r12
0x18008fcea  push    r13
0x18008fcec  push    r14
0x18008fcee  push    r15
0x18008fcf0  lea     rbp, [rsp-2E0h]
0x18008fcf8  sub     rsp, 3E0h
0x18008fcff  mov     rax, cs:__security_cookie
0x18008fd06  xor     rax, rsp
0x18008fd09  mov     [rbp+310h+var_40], rax
0x18008fd10  mov     r15, r8
0x18008fd13  mov     [rbp+310h+var_350], r8
0x18008fd17  mov     rsi, rdx
0x18008fd1a  mov     rbx, rcx
0x18008fd1d  mov     r8d, 11Ah; unsigned __int16
0x18008fd23  lea     rdx, aGetuserprofile; "GetUserProfileData"
0x18008fd2a  lea     rcx, [rsp+410h+var_3A0]; this
0x18008fd2f  mov     r9d, 1; unsigned __int16
0x18008fd35  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18008fd3a  xor     r14d, r14d
0x18008fd3d  test    r15, r15
0x18008fd40  jz      short loc_18008FD45
0x18008fd42  mov     [r15], r14
0x18008fd45  mov     rax, r14
0x18008fd48  mov     [rbp+310h+lpFileName], r14
0x18008fd4c  xorps   xmm0, xmm0
0x18008fd4f  mov     [rbp+310h+pSid2], rax
0x18008fd53  xor     edx, edx; Val
0x18008fd55  mov     [rbp+310h+Sid], rax
0x18008fd59  mov     r8d, 206h; Size
0x18008fd5f  mov     [rbp+310h+var_25E], rax
0x18008fd66  lea     rcx, [rbp+310h+var_24E]; void *
0x18008fd6d  mov     [rbp+310h+var_340], r14d
0x18008fd71  movups  [rbp+310h+var_27E], xmm0
0x18008fd78  mov     r12, r14
0x18008fd7b  mov     [rbp+310h+var_358], 7
0x18008fd82  movups  [rbp+310h+var_26E], xmm0
0x18008fd89  mov     [rbp+310h+Name], r14w
0x18008fd91  mov     [rbp+310h+var_250], r14w
0x18008fd99  call    memset_0
0x18008fd9e  lea     rax, qword_1800EE510
0x18008fda5  mov     [rbp+310h+cchName], 15h
0x18008fdac  xor     edx, edx; Val
0x18008fdae  mov     [rbp+310h+var_328], 104h
0x18008fdb5  lea     rcx, [rbp+310h+pSid]; void *
0x18008fdb9  mov     [rsp+410h+hKey], r14
0x18008fdbe  mov     [rbp+310h+phkResult], r14
0x18008fdc2  mov     [rbp+310h+lpFile], rax
0x18008fdc6  lea     r8d, [rdx+48h]; Size
0x18008fdca  mov     [rbp+310h+var_2F8], r14
0x18008fdce  mov     [rbp+310h+var_2E0], rax
0x18008fdd2  mov     [rbp+310h+var_2D8], r14
0x18008fdd6  mov     [rbp+310h+lpValueName], rax
0x18008fdda  mov     [rbp+310h+var_2E8], r14
0x18008fdde  mov     [rbp+310h+var_310], rax
0x18008fde2  mov     [rbp+310h+var_308], r14
0x18008fde6  mov     [rbp+310h+var_338], r14
0x18008fdea  mov     [rbp+310h+pv], r14
0x18008fdee  mov     [rsp+410h+var_3B0], r14d
0x18008fdf3  call    memset_0
0x18008fdf8  mov     [rbp+310h+cbSid], 44h ; 'D'
0x18008fdff  mov     eax, 138h
0x18008fe04  test    rbx, rbx
0x18008fe07  jnz     short loc_18008FE1B
0x18008fe09  mov     [rsp+410h+var_3A0], 80070057h
0x18008fe11  mov     [rsp+410h+var_39A], ax
0x18008fe16  jmp     loc_1800907CE
0x18008fe1b  mov     [rsp+410h+var_39C], ax
0x18008fe20  mov     eax, 139h
0x18008fe25  test    rsi, rsi
0x18008fe28  jz      short loc_18008FE09
0x18008fe2a  mov     [rsp+410h+var_39C], ax
0x18008fe2f  mov     eax, 13Ah
0x18008fe34  test    r15, r15
0x18008fe37  jz      short loc_18008FE09
0x18008fe39  lea     r8, [rbp+310h+Sid]; unsigned __int8 **
0x18008fe3d  mov     [rsp+410h+var_3A0], r14d
0x18008fe42  mov     rdx, rsi; lpSubKey
0x18008fe45  mov     [rsp+410h+var_39C], ax
0x18008fe4a  mov     rcx, rbx; hKey
0x18008fe4d  call    ?GetUserSid@@YAJQEAUHKEY__@@PEBGPEAPEAE@Z; GetUserSid(HKEY__ * const,ushort const *,uchar * *)
0x18008fe52  test    eax, eax
0x18008fe54  jns     short loc_18008FEAA
0x18008fe56  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fe5d  lea     rbx, WPP_GLOBAL_Control
0x18008fe64  cmp     rcx, rbx
0x18008fe67  jz      short loc_18008FE8B
0x18008fe69  mov     edi, 10000000h
0x18008fe6e  test    [rcx+1Ch], edi
0x18008fe71  jz      short loc_18008FE8B
0x18008fe73  mov     rcx, [rcx+10h]
0x18008fe77  lea     r8, WPP_500c1448b7193519884fd297f141796f_Traceguids
0x18008fe7e  mov     edx, 0Bh
0x18008fe83  mov     r9, rsi
0x18008fe86  call    WPP_SF_S
0x18008fe8b  mov     eax, 146h
0x18008fe90  mov     [rsp+410h+var_3A0], 1
0x18008fe98  mov     [rsp+410h+var_39C], ax
0x18008fe9d  mov     rax, [rbp+310h+Sid]
0x18008fea1  mov     [rbp+310h+pSid2], rax
0x18008fea5  jmp     loc_1800907CE
0x18008feaa  mov     rax, [rbp+310h+Sid]
0x18008feae  mov     [rbp+310h+pSid2], rax
0x18008feb2  test    rax, rax
0x18008feb5  jnz     short loc_18008FEFC
0x18008feb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18008febe  lea     rbx, WPP_GLOBAL_Control
0x18008fec5  cmp     rcx, rbx
0x18008fec8  jz      short loc_18008FEEA
0x18008feca  mov     edi, 10000000h
0x18008fecf  test    [rcx+1Ch], edi
0x18008fed2  jz      short loc_18008FEEA
0x18008fed4  mov     rcx, [rcx+10h]
0x18008fed8  lea     edx, [rax+0Ch]
0x18008fedb  mov     r9, rsi
0x18008fede  lea     r8, WPP_500c1448b7193519884fd297f141796f_Traceguids
0x18008fee5  call    WPP_SF_S
0x18008feea  mov     [rsp+410h+var_3A0], 1
0x18008fef2  mov     eax, 14Ch
0x18008fef7  jmp     loc_1800907C9
0x18008fefc  lea     rcx, [rbp+310h+var_358]
0x18008ff00  mov     rdx, rax; Sid
0x18008ff03  mov     [rsp+410h+peUse], rcx; unsigned __int16 *
0x18008ff08  lea     r9, [rbp+310h+cchName]; cchName
0x18008ff0c  lea     rcx, [rbp+310h+var_328]
0x18008ff10  mov     [rsp+410h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x18008ff15  lea     r8, [rbp+310h+Name]; Name
0x18008ff1c  lea     rcx, [rbp+310h+var_250]
0x18008ff23  mov     [rsp+410h+ReferencedDomainName], rcx; ReferencedDomainName
0x18008ff28  xor     ecx, ecx; lpSystemName
0x18008ff2a  call    cs:__imp_LookupAccountSidW
0x18008ff31  nop     dword ptr [rax+rax+00h]
0x18008ff36  cmp     [rbp+310h+var_358], 1
0x18008ff3a  jz      short loc_18008FF83
0x18008ff3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ff43  lea     rbx, WPP_GLOBAL_Control
0x18008ff4a  cmp     rcx, rbx
0x18008ff4d  jz      short loc_18008FF71
0x18008ff4f  mov     edi, 10000000h
0x18008ff54  test    [rcx+1Ch], edi
0x18008ff57  jz      short loc_18008FF71
0x18008ff59  mov     rcx, [rcx+10h]
0x18008ff5d  lea     r8, WPP_500c1448b7193519884fd297f141796f_Traceguids
0x18008ff64  mov     edx, 0Dh
0x18008ff69  mov     r9, rsi
0x18008ff6c  call    WPP_SF_S
0x18008ff71  mov     [rsp+410h+var_3A0], 1
0x18008ff79  mov     eax, 15Ah
0x18008ff7e  jmp     loc_1800907C9
0x18008ff83  xor     edx, edx; DomainSid
0x18008ff85  lea     r9, [rbp+310h+cbSid]; cbSid
0x18008ff89  lea     r8, [rbp+310h+pSid]; pSid
0x18008ff8d  lea     ecx, [rdx+16h]; WellKnownSidType
0x18008ff90  call    cs:__imp_CreateWellKnownSid
0x18008ff97  nop     dword ptr [rax+rax+00h]
0x18008ff9c  test    eax, eax
0x18008ff9e  jnz     short loc_18008FFB3
0x18008ffa0  call    GetLastFailureAsHRESULT
0x18008ffa5  mov     [rsp+410h+var_3A0], eax
0x18008ffa9  mov     eax, 15Fh
0x18008ffae  jmp     loc_18008FE11
0x18008ffb3  mov     rdx, [rbp+310h+pSid2]; pSid2
0x18008ffb7  lea     rcx, [rbp+310h+pSid]; pSid1
0x18008ffbb  mov     eax, 15Fh
0x18008ffc0  mov     [rsp+410h+var_3A0], r14d
0x18008ffc5  mov     [rsp+410h+var_39C], ax
0x18008ffca  call    cs:__imp_EqualSid
0x18008ffd1  nop     dword ptr [rax+rax+00h]
0x18008ffd6  test    eax, eax
0x18008ffd8  jz      short loc_180090021
0x18008ffda  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ffe1  lea     rbx, WPP_GLOBAL_Control
0x18008ffe8  cmp     rcx, rbx
0x18008ffeb  jz      short loc_18009000F
0x18008ffed  mov     edi, 10000000h
0x18008fff2  test    [rcx+1Ch], edi
0x18008fff5  jz      short loc_18009000F
0x18008fff7  mov     rcx, [rcx+10h]
0x18008fffb  lea     r8, WPP_500c1448b7193519884fd297f141796f_Traceguids
0x180090002  mov     edx, 0Eh
0x180090007  mov     r9, rsi
0x18009000a  call    WPP_SF_S
0x18009000f  mov     [rsp+410h+var_3A0], 1
0x180090017  mov     eax, 165h
0x18009001c  jmp     loc_1800907C9
0x180090021  lea     r9, [rbp+310h+var_2E0]; struct CBsString *
0x180090025  mov     rcx, rsi; unsigned __int16 *
0x180090028  lea     r8, [rbp+310h+Name]; unsigned __int16 *
0x18009002f  lea     rdx, [rbp+310h+var_250]; unsigned __int16 *
0x180090036  call    ?GetFriendlyNameForUser@@YAJPEBG00PEAVCBsString@@@Z; GetFriendlyNameForUser(ushort const *,ushort const *,ushort const *,CBsString *)
0x18009003b  mov     [rsp+410h+var_3A0], eax
0x18009003f  test    eax, eax
0x180090041  mov     eax, 168h
0x180090046  js      loc_18008FE11
0x18009004c  lea     r8, [rbp+310h+lpFileName]; unsigned __int16 **
0x180090050  mov     [rsp+410h+var_39C], ax
0x180090055  mov     rdx, rsi; lpSubKey
0x180090058  mov     rcx, rbx; hKey
0x18009005b  call    ?GetUserProfilePath@@YAJQEAUHKEY__@@PEBGPEAPEAG@Z; GetUserProfilePath(HKEY__ * const,ushort const *,ushort * *)
0x180090060  mov     ecx, eax
0x180090062  mov     [rsp+410h+var_3A0], eax
0x180090066  test    eax, eax
0x180090068  mov     eax, 16Ah
0x18009006d  js      loc_18008FE11
0x180090073  mov     [rsp+410h+var_39C], ax
0x180090078  cmp     ecx, 1
0x18009007b  jnz     short loc_1800900C4
0x18009007d  mov     rcx, cs:WPP_GLOBAL_Control
0x180090084  lea     rbx, WPP_GLOBAL_Control
0x18009008b  cmp     rcx, rbx
0x18009008e  jz      short loc_1800900B2
0x180090090  mov     edi, 10000000h
0x180090095  test    [rcx+1Ch], edi
0x180090098  jz      short loc_1800900B2
0x18009009a  mov     rcx, [rcx+10h]
0x18009009e  lea     r8, WPP_500c1448b7193519884fd297f141796f_Traceguids
0x1800900a5  mov     edx, 0Fh
0x1800900aa  mov     r9, rsi
0x1800900ad  call    WPP_SF_S
0x1800900b2  mov     [rsp+410h+var_3A0], 1
0x1800900ba  mov     eax, 16Eh
0x1800900bf  jmp     loc_1800907C9
0x1800900c4  mov     r13, [rbp+310h+lpFileName]
0x1800900c8  mov     rcx, r13; lpFileName
0x1800900cb  call    cs:__imp_GetFileAttributesW
0x1800900d2  nop     dword ptr [rax+rax+00h]
0x1800900d7  cmp     eax, 0FFFFFFFFh
0x1800900da  jnz     short loc_18009013F
0x1800900dc  mov     rax, cs:WPP_GLOBAL_Control
0x1800900e3  lea     rbx, WPP_GLOBAL_Control
0x1800900ea  cmp     rax, rbx
0x1800900ed  jz      short loc_18009012D
0x1800900ef  mov     edi, 10000000h
0x1800900f4  test    [rax+1Ch], edi
0x1800900f7  jz      short loc_18009012D
0x1800900f9  call    cs:__imp_GetLastError
0x180090100  nop     dword ptr [rax+rax+00h]
0x180090105  mov     rcx, cs:WPP_GLOBAL_Control
0x18009010c  lea     r8, WPP_500c1448b7193519884fd297f141796f_Traceguids
0x180090113  mov     dword ptr [rsp+410h+cchReferencedDomainName], eax
0x180090117  mov     edx, 10h
0x18009011c  mov     r9, rsi
0x18009011f  mov     [rsp+410h+ReferencedDomainName], r13
0x180090124  mov     rcx, [rcx+10h]
0x180090128  call    WPP_SF_SSD
0x18009012d  mov     [rsp+410h+var_3A0], 1
0x180090135  mov     eax, 176h
0x18009013a  jmp     loc_1800907C9
0x18009013f  mov     rcx, [rsp+410h+hKey]; hKey
0x180090144  lea     rax, [rcx-1]
0x180090148  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18009014c  ja      short loc_18009015F
0x18009014e  call    cs:__imp_RegCloseKey
0x180090155  nop     dword ptr [rax+rax+00h]
0x18009015a  mov     [rsp+410h+hKey], r14
0x18009015f  lea     rax, [rsp+410h+hKey]
0x180090164  mov     r9d, 20019h; samDesired
0x18009016a  xor     r8d, r8d; ulOptions
0x18009016d  mov     [rsp+410h+ReferencedDomainName], rax; phkResult
0x180090172  mov     rdx, rsi; lpSubKey
0x180090175  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18009017c  call    cs:__imp_RegOpenKeyExW
0x180090183  nop     dword ptr [rax+rax+00h]
0x180090188  mov     edi, 10000000h
0x18009018d  lea     ecx, [rax-2]
0x180090190  cmp     ecx, 1
0x180090193  jbe     short loc_1800901E2
0x180090195  mov     rcx, cs:WPP_GLOBAL_Control
0x18009019c  lea     rbx, WPP_GLOBAL_Control
0x1800901a3  cmp     rcx, rbx
0x1800901a6  jz      loc_1800904C2
0x1800901ac  test    [rcx+1Ch], edi
0x1800901af  jz      loc_1800904C2
0x1800901b5  test    eax, eax
0x1800901b7  jle     short loc_1800901C1
0x1800901b9  movzx   eax, ax
0x1800901bc  or      eax, 80070000h
0x1800901c1  mov     rcx, [rcx+10h]
0x1800901c5  lea     r8, WPP_500c1448b7193519884fd297f141796f_Traceguids
0x1800901cc  mov     edx, 12h
0x1800901d1  mov     dword ptr [rsp+410h+ReferencedDomainName], eax
0x1800901d5  mov     r9, rsi
0x1800901d8  call    WPP_SF_Sd
0x1800901dd  jmp     loc_1800904C2
0x1800901e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800901e9  lea     rbx, WPP_GLOBAL_Control
0x1800901f0  cmp     rcx, rbx
0x1800901f3  jz      short loc_18009023B
0x1800901f5  test    [rcx+1Ch], edi
0x1800901f8  jz      short loc_180090219
0x1800901fa  mov     rcx, [rcx+10h]
0x1800901fe  lea     r8, WPP_500c1448b7193519884fd297f141796f_Traceguids
0x180090205  mov     edx, 11h
0x18009020a  mov     r9, rsi
0x18009020d  call    WPP_SF_S
0x180090212  mov     rcx, cs:WPP_GLOBAL_Control
0x180090219  cmp     rcx, rbx
  ... truncated ...
```
