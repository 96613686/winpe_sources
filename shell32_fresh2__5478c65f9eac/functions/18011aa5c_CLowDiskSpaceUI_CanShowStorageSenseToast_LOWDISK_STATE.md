# CLowDiskSpaceUI::_CanShowStorageSenseToast(LOWDISK_STATE)

- ea: `0x18011aa5c`
- end: `0x18011b3f4`
- name: `?_CanShowStorageSenseToast@CLowDiskSpaceUI@@AEAAHW4LOWDISK_STATE@@@Z`
- size: `2456`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18011b658`

## callees

- `0x18000f6cc`
- `0x18003a3e0`
- `0x180043ac0`
- `0x1800c23f8`
- `0x1800f5920`
- `0x18011aa5c`
- `0x18011b3fc`
- `0x18011b520`
- `0x180173758`
- `0x1801e1c58`
- `0x1801ed0f0`
- `0x180221a80`
- `0x18022d44c`
- `0x180249490`
- `0x18024a53c`
- `0x180289870`
- `0x18028e538`
- `0x18028e604`
- `0x18028e7c8`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18011ac0d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18011ac0d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18011ab6e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18011aed9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18011af5d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18011ab6e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18011aed9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18011af5d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18011b2a8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18011b2a8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18011ab25`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18011ab25`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18011affa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18011affa`
- `ext-ms-win-storage-sense-l1-2-0!GetStoragePolicySettings` at `0x18011ac7e`
- `ext-ms-win-storage-sense-l1-2-0!GetStoragePolicySettings` at `0x18011adbe`
- `ext-ms-win-storage-sense-l1-2-0!GetStoragePolicySettings` at `0x18011ae7b`
- `ext-ms-win-storage-sense-l1-2-0!GetStoragePolicySettings` at `0x18011b141`
- `ext-ms-win-storage-sense-l1-2-0!GetStoragePolicySettings` at `0x18011ac7e`
- `ext-ms-win-storage-sense-l1-2-0!GetStoragePolicySettings` at `0x18011adbe`
- `ext-ms-win-storage-sense-l1-2-0!GetStoragePolicySettings` at `0x18011ae7b`
- `ext-ms-win-storage-sense-l1-2-0!GetStoragePolicySettings` at `0x18011b141`
- `cldapi!CfGetSyncRootInfoByPath` at `0x18011b17b`
- `cldapi!CfGetSyncRootInfoByPath` at `0x18011b17b`

## string_xrefs

- `0x18011ae52`: `ConfigStorageSenseCloudContentDehydrationThreshold`
- `0x18011ab59`: `InstallTime`
- `0x18011ab04`: `%c:\Windows.old`
- `0x18011abcd`: `LastInstallTimeLowStorageNotify`
- `0x18011accc`: `LastInstallTimeLowStorageNotify`
- `0x18011aec1`: `LastInstallTimeLowStorageNotify`
- `0x18011b36e`: `LastInstallTimeLowStorageNotify`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CLowDiskSpaceUI::_CanShowStorageSenseToast(__int64 a1, int a2)
{
  unsigned int v4; // esi
  CLowDiskSpaceUI *v5; // rcx
  CLowDiskSpaceUI *v6; // rcx
  CLowDiskSpaceUI *v7; // rcx
  const unsigned __int16 *v8; // r8
  CLowDiskSpaceUI *v10; // rcx
  CLowDiskSpaceUI *v11; // rcx
  LSTATUS ValueW; // eax
  CLowDiskSpaceUI *v13; // rcx
  bool v14; // sf
  LSTATUS v15; // eax
  bool v16; // sf
  struct _FILETIME v17; // rdi
  int (__fastcall *v18)(struct _FILETIME, int *); // rbx
  unsigned int v19; // eax
  unsigned int i; // r14d
  __int64 v21; // rdi
  int (__fastcall *v22)(__int64, _QWORD, GUID *, struct _FILETIME *); // rbx
  struct _FILETIME v23; // rdi
  int (__fastcall *v24)(struct _FILETIME, __int64 *); // rbx
  LPVOID v25; // rdi
  int (__fastcall *v26)(LPVOID, __int64, _QWORD, __int64 *); // rbx
  CLowDiskSpaceUI *v27; // rcx
  CLowDiskSpaceUI *v28; // rcx
  HKEY v29; // rcx
  CLowDiskSpaceUI *v30; // rcx
  CLowDiskSpaceUI *v31; // rcx
  CLowDiskSpaceUI *v32; // rcx
  CLowDiskSpaceUI *v33; // rcx
  DWORD v34; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v35; // [rsp+44h] [rbp-BCh] BYREF
  DWORD v36; // [rsp+48h] [rbp-B8h] BYREF
  int v37; // [rsp+4Ch] [rbp-B4h] BYREF
  FILETIME FileTime2; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME v39; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v40; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v41; // [rsp+64h] [rbp-9Ch] BYREF
  int v42[2]; // [rsp+68h] [rbp-98h] BYREF
  struct _FILETIME v43; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v44; // [rsp+78h] [rbp-88h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v46; // [rsp+88h] [rbp-78h] BYREF
  int pvData; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int v48; // [rsp+90h] [rbp-70h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+98h] [rbp-68h] BYREF
  DWORD pcbData; // [rsp+A0h] [rbp-60h] BYREF
  FILETIME FileTime1; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v52; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v53; // [rsp+B8h] [rbp-48h]
  __int64 v54; // [rsp+C0h] [rbp-40h]
  __int64 v55; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v56; // [rsp+D0h] [rbp-30h]
  __int64 v57; // [rsp+D8h] [rbp-28h]
  WCHAR pszPath[264]; // [rsp+E0h] [rbp-20h] BYREF

  FileTime1 = 0;
  FileTime2 = 0;
  pcbData = 8;
  v44 = 0;
  v41 = 0;
  v40 = 0;
  v46 = 0;
  pvData = 0;
  v48 = 0;
  v35 = 0;
  if ( a2 == 6 )
  {
    LUAIsUserUACAdmin(&v35);
    if ( !v35 )
      return 0;
    memset_0(pszPath, 0, 0x208u);
    if ( !*(_DWORD *)(a1 + 40)
      || (int)StringCchPrintfW(pszPath, 0x104u, L"%c:\\Windows.old", *(unsigned __int16 *)(a1 + 12)) < 0
      || !PathFileExistsW(pszPath) )
    {
      return 0;
    }
    v4 = a2 - 5;
    goto LABEL_7;
  }
  v4 = 1;
  switch ( a2 )
  {
    case 5:
      v35 = 0;
      if ( (int)CLowDiskSpaceUI::_GetIsMDMConfigured((CLowDiskSpaceUI *)a1, L"AllowStorageSenseGlobal", (int *)&v35) >= 0
        && v35 )
      {
        return 0;
      }
      v34 = 0;
      if ( (int)GetStoragePolicySettings(0, 0, &v34) >= 0 && v34 == 1 )
        return 0;
      if ( (int)SHRegGetDWORD(
                  HKEY_CURRENT_USER,
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\StoragePolicy",
                  L"StoragePoliciesNotified",
                  &v40) >= 0
        && v40 == 1
        || (int)SHRegGetFILETIME(
                  HKEY_CURRENT_USER,
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\DiskSpaceChecking",
                  L"LastInstallTimeLowStorageNotify",
                  &FileTime2) >= 0
        && CLowDiskSpaceUI::_DurationFromNow(v7, &FileTime2) < 0xC92A69C000LL )
      {
        return 0;
      }
      v8 = L"OptinToastFired";
      goto LABEL_26;
    case 12:
      v34 = 0;
      if ( (int)CLowDiskSpaceUI::_GetIsMDMConfigured((CLowDiskSpaceUI *)a1, L"AllowStorageSenseGlobal", (int *)&v34) >= 0
        && v34 )
      {
        return 0;
      }
      v39 = 0;
      if ( CLowDiskSpaceUI::_GetOOBETime(v10, &v39) >= 0
        && CLowDiskSpaceUI::_DurationFromNow(v11, &v39) < 0xC92A69C000LL )
      {
        return 0;
      }
      v35 = 0;
      if ( (int)GetStoragePolicySettings(0, 0, &v35) < 0
        || !v35
        || (int)SHRegGetDWORD(
                  HKEY_CURRENT_USER,
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\StoragePolicy",
                  L"StoragePoliciesNotified",
                  &v40) >= 0
        && v40 == 1 )
      {
        return 0;
      }
      if ( (int)SHRegGetDWORD(
                  HKEY_CURRENT_USER,
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\StoragePolicy",
                  L"StoragePoliciesChanged",
                  &v46) >= 0
        && v46 == 1 )
      {
        return 0;
      }
      v8 = L"FirstLaunchToastFired";
LABEL_26:
      if ( (int)SHRegGetDWORD(
                  HKEY_CURRENT_USER,
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\StoragePolicy",
                  v8,
                  &v41) < 0
        || !v41 )
      {
        return v4;
      }
      return 0;
    case 8:
      v34 = 0;
      if ( (int)CLowDiskSpaceUI::_GetIsMDMConfigured(
                  (CLowDiskSpaceUI *)a1,
                  L"ConfigStorageSenseCloudContentDehydrationThreshold",
                  (int *)&v34) >= 0
        && v34 )
      {
        return 0;
      }
      v37 = 0;
      if ( (int)GetStoragePolicySettings(0, 0, &v37) < 0 || !v37 )
        return 0;
      v34 = 8;
      ValueW = RegGetValueW(
                 HKEY_CURRENT_USER,
                 L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\DiskSpaceChecking",
                 L"LastInstallTimeLowStorageNotify",
                 8u,
                 0,
                 &FileTime2,
                 &v34);
      v14 = ValueW < 0;
      if ( ValueW > 0 )
        v14 = 1;
      if ( v14 || v34 != 8 )
      {
        FileTime2 = 0;
      }
      else if ( CLowDiskSpaceUI::_DurationFromNow(v13, &FileTime2) < 0xC92A69C000LL )
      {
        return 0;
      }
      v36 = 4;
      v15 = RegGetValueW(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\StoragePolicy",
              L"CloudfilePolicyConsent",
              0x10u,
              0,
              &pvData,
              &v36);
      v16 = v15 < 0;
      if ( v15 > 0 )
        v16 = 1;
      if ( (v16 || !pvData)
        && ((int)SHRegGetDWORD(
                   HKEY_CURRENT_USER,
                   L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\StoragePolicy",
                   L"CloudConsentToastCount",
                   &v48) < 0
         || v48 < 3) )
      {
        ppv = 0;
        v39 = 0;
        *(_QWORD *)v42 = 0;
        v43 = 0;
        v52 = 0;
        v53 = 0;
        v54 = 0;
        v55 = 0;
        v56 = 0;
        v57 = 0;
        v35 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
        if ( CoCreateInstance(&CLSID_SyncRootManager, 0, 1u, &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64, &ppv) >= 0
          && (int)Microsoft::WRL::ComPtr<ISyncRootManager>::As<ISyncRootManagerPriv>(&ppv, &v39) >= 0 )
        {
          v17 = v39;
          v18 = *(int (__fastcall **)(struct _FILETIME, int *))(**(_QWORD **)&v39 + 24LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v42);
          if ( ((__int64 (__fastcall *)(_QWORD, _QWORD))v18)(v17, v42) >= 0
            && (*(int (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)v42 + 24LL))(*(_QWORD *)v42, &v35) >= 0 )
          {
            v19 = v35;
            if ( v35 )
            {
              for ( i = 0; i < v19; ++i )
              {
                v21 = *(_QWORD *)v42;
                v22 = *(int (__fastcall **)(__int64, _QWORD, GUID *, struct _FILETIME *))(**(_QWORD **)v42 + 32LL);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
                if ( v22(v21, i, &GUID_ca01c124_2769_4576_bf12_8a54ee671a86, &v43) >= 0 )
                {
                  v23 = v43;
                  v24 = *(int (__fastcall **)(struct _FILETIME, __int64 *))(**(_QWORD **)&v43 + 24LL);
                  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v52);
                  v53 = -1;
                  v54 = -1;
                  if ( ((__int64 (__fastcall *)(_QWORD, _QWORD))v24)(v23, &v52) >= 0 )
                  {
                    v25 = ppv;
                    v26 = *(int (__fastcall **)(LPVOID, __int64, _QWORD, __int64 *))(*(_QWORD *)ppv + 136LL);
                    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v55);
                    v56 = -1;
                    v57 = -1;
                    if ( v26(v25, v52, 0, &v55) >= 0 )
                    {
                      v34 = 0;
                      if ( (int)GetStoragePolicySettings(1, v52, &v34) >= 0 && v34 )
                      {
                        v4 = 0;
LABEL_74:
                        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v55);
                        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v52);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v42);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
                        return v4;
                      }
                      SystemTimeAsFileTime = 0;
                      v36 = 0;
                      if ( (int)CfGetSyncRootInfoByPath(v55, 0, &SystemTimeAsFileTime, 8, &v36) >= 0 )
                        goto LABEL_74;
                    }
                  }
                }
                v19 = v35;
              }
            }
          }
        }
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v55);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v52);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v42);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      }
      return 0;
    case 9:
      v35 = 0;
      if ( (int)SHRegGetDWORD(
                  HKEY_LOCAL_MACHINE,
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\BackupReminder",
                  L"TestBackupReminderToast",
                  &v35) >= 0
        && v35
        && ((unsigned int)CLowDiskSpaceUI::IsBackupReminderEnabled(v27) || v35 == 2) )
      {
        v39 = 0;
        if ( (int)SHRegGetFILETIME(
                    HKEY_CURRENT_USER,
                    L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\BackupReminder",
                    L"FirstProfileSeenTime",
                    &v39) >= 0 )
        {
          if ( CLowDiskSpaceUI::_DurationFromNow(v28, &v39) >= 0x8F0D1800 )
          {
            v37 = 0;
            v34 = 0;
            v42[0] = 0;
            if ( ((int)CLowDiskSpaceUI::_GetIsFHConfigured((CLowDiskSpaceUI *)0x8F0D1800LL, &v37) < 0 || !v37)
              && ((int)CLowDiskSpaceUI::_GetIsWin7BackupConfigured(v30, (int *)&v34) < 0 || !v34)
              && ((int)CLowDiskSpaceUI::_GetIsKFMEnrolled(v31, v42) < 0 || !v42[0]) )
            {
              v36 = 0;
              if ( (int)SHRegGetDWORD(
                          HKEY_CURRENT_USER,
                          L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\BackupReminder",
                          L"BackupReminderToastCount",
                          &v36) < 0
                || v36 < 3 )
              {
                if ( (int)SHRegGetFILETIME(
                            HKEY_CURRENT_USER,
                            L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\DiskSpaceChecking",
                            L"LastInstallTimeLowStorageNotify",
                            &FileTime2) >= 0 )
                  CLowDiskSpaceUI::_DurationFromNow(v32, &FileTime2);
                v43 = 0;
                if ( (int)SHRegGetFILETIME(
                            HKEY_CURRENT_USER,
                            L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\BackupReminder",
                            L"LastTimeBackupReminderNotify",
                            &v43) < 0
                  || CLowDiskSpaceUI::_DurationFromNow(v33, &v43) >= 0x47868C00 )
                {
                  return v4;
                }
              }
            }
          }
        }
        else
        {
          SystemTimeAsFileTime = 0;
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          SHRegSetFILETIME(
            v29,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\BackupReminder",
            L"FirstProfileSeenTime",
            &SystemTimeAsFileTime);
        }
      }
      return 0;
  }
LABEL_7:
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion",
         L"InstallTime",
         0x40u,
         0,
         &FileTime1,
         &pcbData) < 0
    || CLowDiskSpaceUI::_DurationFromNow(v5, &FileTime1) < 0x10C388D000LL )
  {
    return 0;
  }
  if ( (int)SHRegGetDWORD(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\DiskSpaceChecking",
              L"NumWinOldLowStorageNotify",
              &v44) >= 0 )
  {
    if ( (int)SHRegGetFILETIME(
                HKEY_CURRENT_USER,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\DiskSpaceChecking",
                L"LastInstallTimeLowStorageNotify",
                &FileTime2) < 0 )
      goto LABEL_13;
    if ( CLowDiskSpaceUI::_DurationFromNow(v6, &FileTime2) >= 0xC92A69C000LL )
    {
      if ( CompareFileTime(&FileTime1, &FileTime2) <= 0 )
      {
LABEL_13:
        if ( a2 != 7 && v44 >= 3 )
          return 0;
        return v4;
      }
      goto LABEL_98;
    }
    return 0;
  }
LABEL_98:
  v44 = 0;
  SHRegSetDWORD(
    HKEY_CURRENT_USER,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\DiskSpaceChecking",
    L"NumWinOldLowStorageNotify",
    0);
  return v4;
}

```

## disassembly

```asm
0x18011aa5c  mov     [rsp-8+arg_8], rbx
0x18011aa61  mov     [rsp-8+arg_10], rsi
0x18011aa66  push    rbp
0x18011aa67  push    rdi
0x18011aa68  push    r13
0x18011aa6a  push    r14
0x18011aa6c  push    r15
0x18011aa6e  lea     rbp, [rsp-200h]
0x18011aa76  sub     rsp, 300h
0x18011aa7d  mov     rax, cs:__security_cookie
0x18011aa84  xor     rax, rsp
0x18011aa87  mov     [rbp+220h+var_30], rax
0x18011aa8e  mov     edi, edx
0x18011aa90  mov     rbx, rcx
0x18011aa93  xor     r15d, r15d
0x18011aa96  mov     qword ptr [rbp+220h+FileTime1.dwLowDateTime], r15
0x18011aa9a  mov     qword ptr [rsp+320h+FileTime2.dwLowDateTime], r15
0x18011aa9f  mov     [rbp+220h+var_280], 8
0x18011aaa6  mov     [rsp+320h+var_2A8], r15d
0x18011aaab  mov     [rsp+320h+var_2BC], r15d
0x18011aab0  mov     [rsp+320h+var_2C0], r15d
0x18011aab5  mov     [rbp+220h+var_298], r15d
0x18011aab9  mov     [rbp+220h+var_294], r15d
0x18011aabd  mov     [rbp+220h+var_290], r15d
0x18011aac1  mov     [rsp+320h+var_2DC], r15d
0x18011aac6  cmp     edx, 6
0x18011aac9  jnz     loc_18011AC3D
0x18011aacf  lea     rcx, [rsp+320h+var_2DC]
0x18011aad4  call    LUAIsUserUACAdmin
0x18011aad9  cmp     [rsp+320h+var_2DC], r15d
0x18011aade  jz      loc_18011AD28
0x18011aae4  xor     edx, edx; Val
0x18011aae6  mov     r8d, 208h; Size
0x18011aaec  lea     rcx, [rbp+220h+pszPath]; void *
0x18011aaf0  call    memset_0
0x18011aaf5  cmp     [rbx+28h], r15d
0x18011aaf9  jz      loc_18011AD28
0x18011aaff  movzx   r9d, word ptr [rbx+0Ch]
0x18011ab04  lea     r8, aCWindowsOld; "%c:\\Windows.old"
0x18011ab0b  mov     edx, 104h; unsigned __int64
0x18011ab10  lea     rcx, [rbp+220h+pszPath]; unsigned __int16 *
0x18011ab14  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18011ab19  test    eax, eax
0x18011ab1b  js      loc_18011AD28
0x18011ab21  lea     rcx, [rbp+220h+pszPath]; pszPath
0x18011ab25  call    cs:__imp_PathFileExistsW
0x18011ab2c  nop     dword ptr [rax+rax+00h]
0x18011ab31  test    eax, eax
0x18011ab33  jz      loc_18011AD28
0x18011ab39  lea     esi, [rdi-5]
0x18011ab3c  lea     rax, [rbp+220h+var_280]
0x18011ab40  mov     [rsp+320h+pcbData], rax; pcbData
0x18011ab45  lea     rax, [rbp+220h+FileTime1]
0x18011ab49  mov     [rsp+320h+pvData], rax; pvData
0x18011ab4e  mov     [rsp+320h+pdwType], r15; pdwType
0x18011ab53  mov     r9d, 40h ; '@'; dwFlags
0x18011ab59  lea     r8, aInstalltime; "InstallTime"
0x18011ab60  lea     rdx, aSoftwareMicros_167; "Software\\Microsoft\\Windows NT\\Curren"...
0x18011ab67  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18011ab6e  call    cs:__imp_RegGetValueW
0x18011ab75  nop     dword ptr [rax+rax+00h]
0x18011ab7a  test    eax, eax
0x18011ab7c  js      loc_18011AD28
0x18011ab82  lea     rdx, [rbp+220h+FileTime1]; struct _FILETIME *
0x18011ab86  call    ?_DurationFromNow@CLowDiskSpaceUI@@AEAA_KAEBU_FILETIME@@@Z; CLowDiskSpaceUI::_DurationFromNow(_FILETIME const &)
0x18011ab8b  mov     rcx, 10C388D000h
0x18011ab95  cmp     rax, rcx
0x18011ab98  jb      loc_18011AD28
0x18011ab9e  lea     r9, [rsp+320h+var_2A8]; unsigned int *
0x18011aba3  lea     r8, aNumwinoldlowst; "NumWinOldLowStorageNotify"
0x18011abaa  lea     rdx, aSoftwareMicros_173; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18011abb1  mov     rbx, 0FFFFFFFF80000001h
0x18011abb8  mov     rcx, rbx; HKEY
0x18011abbb  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18011abc0  test    eax, eax
0x18011abc2  js      loc_18011B3D1
0x18011abc8  lea     r9, [rsp+320h+FileTime2]; struct _FILETIME *
0x18011abcd  lea     r8, aLastinstalltim; "LastInstallTimeLowStorageNotify"
0x18011abd4  lea     rdx, aSoftwareMicros_173; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18011abdb  mov     rcx, rbx; HKEY
0x18011abde  call    ?SHRegGetFILETIME@@YAJPEAUHKEY__@@PEBG1PEAU_FILETIME@@@Z; SHRegGetFILETIME(HKEY__ *,ushort const *,ushort const *,_FILETIME *)
0x18011abe3  test    eax, eax
0x18011abe5  js      short loc_18011AC21
0x18011abe7  lea     rdx, [rsp+320h+FileTime2]; struct _FILETIME *
0x18011abec  call    ?_DurationFromNow@CLowDiskSpaceUI@@AEAA_KAEBU_FILETIME@@@Z; CLowDiskSpaceUI::_DurationFromNow(_FILETIME const &)
0x18011abf1  mov     rcx, 0C92A69C000h
0x18011abfb  cmp     rax, rcx
0x18011abfe  jb      loc_18011AD28
0x18011ac04  lea     rdx, [rsp+320h+FileTime2]; lpFileTime2
0x18011ac09  lea     rcx, [rbp+220h+FileTime1]; lpFileTime1
0x18011ac0d  call    cs:__imp_CompareFileTime
0x18011ac14  nop     dword ptr [rax+rax+00h]
0x18011ac19  test    eax, eax
0x18011ac1b  jg      loc_18011B3D1
0x18011ac21  cmp     edi, 7
0x18011ac24  jz      loc_18011B1D8
0x18011ac2a  cmp     [rsp+320h+var_2A8], 3
0x18011ac2f  jb      loc_18011B1D8
0x18011ac35  mov     esi, r15d
0x18011ac38  jmp     loc_18011B1D8
0x18011ac3d  mov     esi, 1
0x18011ac42  cmp     edi, 5
0x18011ac45  jnz     loc_18011AD56
0x18011ac4b  mov     [rsp+320h+var_2DC], r15d
0x18011ac50  lea     r8, [rsp+320h+var_2DC]; int *
0x18011ac55  lea     rdx, aAllowstoragese; "AllowStorageSenseGlobal"
0x18011ac5c  call    ?_GetIsMDMConfigured@CLowDiskSpaceUI@@AEAAJPEBGPEAH@Z; CLowDiskSpaceUI::_GetIsMDMConfigured(ushort const *,int *)
0x18011ac61  test    eax, eax
0x18011ac63  js      short loc_18011AC70
0x18011ac65  cmp     [rsp+320h+var_2DC], r15d
0x18011ac6a  jnz     loc_18011AD28
0x18011ac70  mov     [rsp+320h+var_2E0], r15d
0x18011ac75  lea     r8, [rsp+320h+var_2E0]
0x18011ac7a  xor     edx, edx
0x18011ac7c  xor     ecx, ecx
0x18011ac7e  call    cs:__imp_GetStoragePolicySettings
0x18011ac85  nop     dword ptr [rax+rax+00h]
0x18011ac8a  test    eax, eax
0x18011ac8c  js      short loc_18011AC98
0x18011ac8e  cmp     [rsp+320h+var_2E0], esi
0x18011ac92  jz      loc_18011AD28
0x18011ac98  lea     r9, [rsp+320h+var_2C0]; unsigned int *
0x18011ac9d  lea     r8, aStoragepolicie_0; "StoragePoliciesNotified"
0x18011aca4  lea     rdi, aSoftwareMicros_80; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18011acab  mov     rdx, rdi; unsigned __int16 *
0x18011acae  mov     rbx, 0FFFFFFFF80000001h
0x18011acb5  mov     rcx, rbx; HKEY
0x18011acb8  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18011acbd  test    eax, eax
0x18011acbf  js      short loc_18011ACC7
0x18011acc1  cmp     [rsp+320h+var_2C0], esi
0x18011acc5  jz      short loc_18011AD28
0x18011acc7  lea     r9, [rsp+320h+FileTime2]; struct _FILETIME *
0x18011accc  lea     r8, aLastinstalltim; "LastInstallTimeLowStorageNotify"
0x18011acd3  lea     rdx, aSoftwareMicros_173; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18011acda  mov     rcx, rbx; HKEY
0x18011acdd  call    ?SHRegGetFILETIME@@YAJPEAUHKEY__@@PEBG1PEAU_FILETIME@@@Z; SHRegGetFILETIME(HKEY__ *,ushort const *,ushort const *,_FILETIME *)
0x18011ace2  test    eax, eax
0x18011ace4  js      short loc_18011ACFF
0x18011ace6  lea     rdx, [rsp+320h+FileTime2]; struct _FILETIME *
0x18011aceb  call    ?_DurationFromNow@CLowDiskSpaceUI@@AEAA_KAEBU_FILETIME@@@Z; CLowDiskSpaceUI::_DurationFromNow(_FILETIME const &)
0x18011acf0  mov     rcx, 0C92A69C000h
0x18011acfa  cmp     rax, rcx
0x18011acfd  jb      short loc_18011AD28
0x18011acff  lea     r8, aOptintoastfire; "OptinToastFired"
0x18011ad06  lea     r9, [rsp+320h+var_2BC]; unsigned int *
0x18011ad0b  mov     rdx, rdi; unsigned __int16 *
0x18011ad0e  mov     rcx, rbx; HKEY
0x18011ad11  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18011ad16  test    eax, eax
0x18011ad18  js      loc_18011B1D8
0x18011ad1e  cmp     [rsp+320h+var_2BC], esi
0x18011ad22  jb      loc_18011B1D8
0x18011ad28  xor     eax, eax
0x18011ad2a  mov     rcx, [rbp+220h+var_30]
0x18011ad31  xor     rcx, rsp; StackCookie
0x18011ad34  call    __security_check_cookie
0x18011ad39  lea     r11, [rsp+320h+var_20]
0x18011ad41  mov     rbx, [r11+38h]
0x18011ad45  mov     rsi, [r11+40h]
0x18011ad49  mov     rsp, r11
0x18011ad4c  pop     r15
0x18011ad4e  pop     r14
0x18011ad50  pop     r13
0x18011ad52  pop     rdi
0x18011ad53  pop     rbp
0x18011ad54  retn
0x18011ad56  cmp     edi, 0Ch
0x18011ad59  jnz     loc_18011AE3F
0x18011ad5f  mov     [rsp+320h+var_2E0], r15d
0x18011ad64  lea     r8, [rsp+320h+var_2E0]; int *
0x18011ad69  lea     rdx, aAllowstoragese; "AllowStorageSenseGlobal"
0x18011ad70  call    ?_GetIsMDMConfigured@CLowDiskSpaceUI@@AEAAJPEBGPEAH@Z; CLowDiskSpaceUI::_GetIsMDMConfigured(ushort const *,int *)
0x18011ad75  test    eax, eax
0x18011ad77  js      short loc_18011AD80
0x18011ad79  cmp     [rsp+320h+var_2E0], r15d
0x18011ad7e  jnz     short loc_18011AD28
0x18011ad80  mov     qword ptr [rsp+320h+var_2C8.dwLowDateTime], r15
0x18011ad85  lea     rdx, [rsp+320h+var_2C8]; struct _FILETIME *
0x18011ad8a  call    ?_GetOOBETime@CLowDiskSpaceUI@@AEAAJPEAU_FILETIME@@@Z; CLowDiskSpaceUI::_GetOOBETime(_FILETIME *)
0x18011ad8f  test    eax, eax
0x18011ad91  js      short loc_18011ADB0
0x18011ad93  lea     rdx, [rsp+320h+var_2C8]; struct _FILETIME *
0x18011ad98  call    ?_DurationFromNow@CLowDiskSpaceUI@@AEAA_KAEBU_FILETIME@@@Z; CLowDiskSpaceUI::_DurationFromNow(_FILETIME const &)
0x18011ad9d  mov     rcx, 0C92A69C000h
0x18011ada7  cmp     rax, rcx
0x18011adaa  jb      loc_18011AD28
0x18011adb0  mov     [rsp+320h+var_2DC], r15d
0x18011adb5  lea     r8, [rsp+320h+var_2DC]
0x18011adba  xor     edx, edx
0x18011adbc  xor     ecx, ecx
0x18011adbe  call    cs:__imp_GetStoragePolicySettings
0x18011adc5  nop     dword ptr [rax+rax+00h]
0x18011adca  test    eax, eax
0x18011adcc  js      loc_18011AD28
0x18011add2  cmp     [rsp+320h+var_2DC], r15d
0x18011add7  jz      loc_18011AD28
0x18011addd  lea     r9, [rsp+320h+var_2C0]; unsigned int *
0x18011ade2  lea     r8, aStoragepolicie_0; "StoragePoliciesNotified"
0x18011ade9  lea     rdi, aSoftwareMicros_80; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18011adf0  mov     rdx, rdi; unsigned __int16 *
0x18011adf3  mov     rbx, 0FFFFFFFF80000001h
0x18011adfa  mov     rcx, rbx; HKEY
0x18011adfd  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18011ae02  test    eax, eax
0x18011ae04  js      short loc_18011AE10
0x18011ae06  cmp     [rsp+320h+var_2C0], esi
0x18011ae0a  jz      loc_18011AD28
0x18011ae10  lea     r9, [rbp+220h+var_298]; unsigned int *
0x18011ae14  lea     r8, aStoragepolicie; "StoragePoliciesChanged"
0x18011ae1b  mov     rdx, rdi; unsigned __int16 *
0x18011ae1e  mov     rcx, rbx; HKEY
0x18011ae21  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18011ae26  test    eax, eax
0x18011ae28  js      short loc_18011AE33
0x18011ae2a  cmp     [rbp+220h+var_298], esi
0x18011ae2d  jz      loc_18011AD28
0x18011ae33  lea     r8, aFirstlaunchtoa; "FirstLaunchToastFired"
0x18011ae3a  jmp     loc_18011AD06
0x18011ae3f  cmp     edi, 8
0x18011ae42  jnz     loc_18011B222
0x18011ae48  mov     [rsp+320h+var_2E0], r15d
0x18011ae4d  lea     r8, [rsp+320h+var_2E0]; int *
0x18011ae52  lea     rdx, aConfigstorages; "ConfigStorageSenseCloudContentDehydrati"...
0x18011ae59  call    ?_GetIsMDMConfigured@CLowDiskSpaceUI@@AEAAJPEBGPEAH@Z; CLowDiskSpaceUI::_GetIsMDMConfigured(ushort const *,int *)
0x18011ae5e  test    eax, eax
0x18011ae60  js      short loc_18011AE6D
0x18011ae62  cmp     [rsp+320h+var_2E0], r15d
0x18011ae67  jnz     loc_18011AD28
0x18011ae6d  mov     [rsp+320h+var_2D4], r15d
0x18011ae72  lea     r8, [rsp+320h+var_2D4]
0x18011ae77  xor     edx, edx
0x18011ae79  xor     ecx, ecx
0x18011ae7b  call    cs:__imp_GetStoragePolicySettings
0x18011ae82  nop     dword ptr [rax+rax+00h]
0x18011ae87  test    eax, eax
0x18011ae89  js      loc_18011AD28
0x18011ae8f  cmp     [rsp+320h+var_2D4], r15d
0x18011ae94  jz      loc_18011AD28
0x18011ae9a  mov     [rsp+320h+var_2E0], 8
0x18011aea2  lea     rax, [rsp+320h+var_2E0]
0x18011aea7  mov     [rsp+320h+pcbData], rax; pcbData
0x18011aeac  lea     rax, [rsp+320h+FileTime2]
0x18011aeb1  mov     [rsp+320h+pvData], rax; pvData
0x18011aeb6  mov     [rsp+320h+pdwType], r15; pdwType
0x18011aebb  mov     r9d, 8; dwFlags
0x18011aec1  lea     r8, aLastinstalltim; "LastInstallTimeLowStorageNotify"
0x18011aec8  lea     rdx, aSoftwareMicros_173; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18011aecf  mov     rbx, 0FFFFFFFF80000001h
0x18011aed6  mov     rcx, rbx; hkey
0x18011aed9  call    cs:__imp_RegGetValueW
0x18011aee0  nop     dword ptr [rax+rax+00h]
0x18011aee5  mov     r14d, 80070000h
0x18011aeeb  test    eax, eax
0x18011aeed  jle     short loc_18011AEF7
0x18011aeef  movzx   eax, ax
0x18011aef2  or      eax, r14d
0x18011aef5  test    eax, eax
0x18011aef7  js      short loc_18011AF1E
0x18011aef9  cmp     [rsp+320h+var_2E0], 8
0x18011aefe  jnz     short loc_18011AF1E
0x18011af00  lea     rdx, [rsp+320h+FileTime2]; struct _FILETIME *
0x18011af05  call    ?_DurationFromNow@CLowDiskSpaceUI@@AEAA_KAEBU_FILETIME@@@Z; CLowDiskSpaceUI::_DurationFromNow(_FILETIME const &)
0x18011af0a  mov     rcx, 0C92A69C000h
0x18011af14  cmp     rax, rcx
0x18011af17  jnb     short loc_18011AF23
0x18011af19  jmp     loc_18011AD28
0x18011af1e  mov     qword ptr [rsp+320h+FileTime2.dwLowDateTime], r15
0x18011af23  mov     [rsp+320h+var_2D8], 4
0x18011af2b  lea     rax, [rsp+320h+var_2D8]
0x18011af30  mov     [rsp+320h+pcbData], rax; pcbData
0x18011af35  lea     rax, [rbp+220h+var_294]
0x18011af39  mov     [rsp+320h+pvData], rax; pvData
0x18011af3e  mov     [rsp+320h+pdwType], r15; pdwType
0x18011af43  mov     r9d, 10h; dwFlags
0x18011af49  lea     r8, aCloudfilepolic; "CloudfilePolicyConsent"
0x18011af50  lea     rdi, aSoftwareMicros_80; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18011af57  mov     rdx, rdi; lpSubKey
0x18011af5a  mov     rcx, rbx; hkey
0x18011af5d  call    cs:__imp_RegGetValueW
0x18011af64  nop     dword ptr [rax+rax+00h]
0x18011af69  test    eax, eax
0x18011af6b  jle     short loc_18011AF75
0x18011af6d  movzx   eax, ax
0x18011af70  or      eax, r14d
0x18011af73  test    eax, eax
0x18011af75  js      short loc_18011AF81
0x18011af77  cmp     [rbp+220h+var_294], r15d
0x18011af7b  jnz     loc_18011AD28
0x18011af81  lea     r9, [rbp+220h+var_290]; unsigned int *
0x18011af85  lea     r8, aCloudconsentto; "CloudConsentToastCount"
0x18011af8c  mov     rdx, rdi; unsigned __int16 *
0x18011af8f  mov     rcx, rbx; HKEY
0x18011af92  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18011af97  test    eax, eax
0x18011af99  js      short loc_18011AFA5
0x18011af9b  cmp     [rbp+220h+var_290], 3
0x18011af9f  jnb     loc_18011AD28
0x18011afa5  mov     [rbp+220h+ppv], r15
0x18011afa9  mov     qword ptr [rsp+320h+var_2C8.dwLowDateTime], r15
  ... truncated ...
```
