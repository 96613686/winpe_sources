# CLowDiskSpaceUI::_CanShowStorageSenseToast(LOWDISK_STATE)

- ea: `0x18010cfe8`
- end: `0x18010d937`
- name: `?_CanShowStorageSenseToast@CLowDiskSpaceUI@@AEAAHW4LOWDISK_STATE@@@Z`
- size: `2383`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18010db68`

## callees

- `0x18000f05c`
- `0x18003eab0`
- `0x180047d00`
- `0x1800b8f00`
- `0x1800f188c`
- `0x18010cfe8`
- `0x18010d940`
- `0x18010da58`
- `0x180162c08`
- `0x1801cb6bc`
- `0x1801d5e7c`
- `0x18020a894`
- `0x180216304`
- `0x180233280`
- `0x1802342fc`
- `0x180270c60`
- `0x180274d88`
- `0x180274e4c`
- `0x180275008`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18010d18d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18010d18d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18010d0f4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18010d440`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18010d4be`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18010d0f4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18010d440`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18010d4be`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18010d7f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18010d7f1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18010d0b1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18010d0b1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18010d555`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18010d555`
- `ext-ms-win-storage-sense-l1-2-0!GetStoragePolicySettings` at `0x18010d1f8`
- `ext-ms-win-storage-sense-l1-2-0!GetStoragePolicySettings` at `0x18010d331`
- `ext-ms-win-storage-sense-l1-2-0!GetStoragePolicySettings` at `0x18010d3e8`
- `ext-ms-win-storage-sense-l1-2-0!GetStoragePolicySettings` at `0x18010d696`
- `ext-ms-win-storage-sense-l1-2-0!GetStoragePolicySettings` at `0x18010d1f8`
- `ext-ms-win-storage-sense-l1-2-0!GetStoragePolicySettings` at `0x18010d331`
- `ext-ms-win-storage-sense-l1-2-0!GetStoragePolicySettings` at `0x18010d3e8`
- `ext-ms-win-storage-sense-l1-2-0!GetStoragePolicySettings` at `0x18010d696`
- `cldapi!CfGetSyncRootInfoByPath` at `0x18010d6ca`
- `cldapi!CfGetSyncRootInfoByPath` at `0x18010d6ca`

## string_xrefs

- `0x18010d3bf`: `ConfigStorageSenseCloudContentDehydrationThreshold`
- `0x18010d0df`: `InstallTime`
- `0x18010d090`: `%c:\Windows.old`
- `0x18010d14d`: `LastInstallTimeLowStorageNotify`
- `0x18010d240`: `LastInstallTimeLowStorageNotify`
- `0x18010d428`: `LastInstallTimeLowStorageNotify`
- `0x18010d8b1`: `LastInstallTimeLowStorageNotify`

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
0x18010cfe8  mov     [rsp-8+arg_8], rbx
0x18010cfed  mov     [rsp-8+arg_10], rsi
0x18010cff2  push    rbp
0x18010cff3  push    rdi
0x18010cff4  push    r13
0x18010cff6  push    r14
0x18010cff8  push    r15
0x18010cffa  lea     rbp, [rsp-200h]
0x18010d002  sub     rsp, 300h
0x18010d009  mov     rax, cs:__security_cookie
0x18010d010  xor     rax, rsp
0x18010d013  mov     [rbp+220h+var_30], rax
0x18010d01a  mov     edi, edx
0x18010d01c  mov     rbx, rcx
0x18010d01f  xor     r15d, r15d
0x18010d022  mov     qword ptr [rbp+220h+FileTime1.dwLowDateTime], r15
0x18010d026  mov     qword ptr [rsp+320h+FileTime2.dwLowDateTime], r15
0x18010d02b  mov     [rbp+220h+var_280], 8
0x18010d032  mov     [rsp+320h+var_2A8], r15d
0x18010d037  mov     [rsp+320h+var_2BC], r15d
0x18010d03c  mov     [rsp+320h+var_2C0], r15d
0x18010d041  mov     [rbp+220h+var_298], r15d
0x18010d045  mov     [rbp+220h+var_294], r15d
0x18010d049  mov     [rbp+220h+var_290], r15d
0x18010d04d  mov     [rsp+320h+var_2DC], r15d
0x18010d052  cmp     edx, 6
0x18010d055  jnz     loc_18010D1B7
0x18010d05b  lea     rcx, [rsp+320h+var_2DC]
0x18010d060  call    LUAIsUserUACAdmin
0x18010d065  cmp     [rsp+320h+var_2DC], r15d
0x18010d06a  jz      loc_18010D29C
0x18010d070  xor     edx, edx; Val
0x18010d072  mov     r8d, 208h; Size
0x18010d078  lea     rcx, [rbp+220h+pszPath]; void *
0x18010d07c  call    memset_0
0x18010d081  cmp     [rbx+28h], r15d
0x18010d085  jz      loc_18010D29C
0x18010d08b  movzx   r9d, word ptr [rbx+0Ch]
0x18010d090  lea     r8, aCWindowsOld; "%c:\\Windows.old"
0x18010d097  mov     edx, 104h; unsigned __int64
0x18010d09c  lea     rcx, [rbp+220h+pszPath]; unsigned __int16 *
0x18010d0a0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18010d0a5  test    eax, eax
0x18010d0a7  js      loc_18010D29C
0x18010d0ad  lea     rcx, [rbp+220h+pszPath]; pszPath
0x18010d0b1  call    cs:__imp_PathFileExistsW
0x18010d0b7  test    eax, eax
0x18010d0b9  jz      loc_18010D29C
0x18010d0bf  lea     esi, [rdi-5]
0x18010d0c2  lea     rax, [rbp+220h+var_280]
0x18010d0c6  mov     [rsp+320h+pcbData], rax; pcbData
0x18010d0cb  lea     rax, [rbp+220h+FileTime1]
0x18010d0cf  mov     [rsp+320h+pvData], rax; pvData
0x18010d0d4  mov     [rsp+320h+pdwType], r15; pdwType
0x18010d0d9  mov     r9d, 40h ; '@'; dwFlags
0x18010d0df  lea     r8, aInstalltime; "InstallTime"
0x18010d0e6  lea     rdx, aSoftwareMicros_167; "Software\\Microsoft\\Windows NT\\Curren"...
0x18010d0ed  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18010d0f4  call    cs:__imp_RegGetValueW
0x18010d0fa  test    eax, eax
0x18010d0fc  js      loc_18010D29C
0x18010d102  lea     rdx, [rbp+220h+FileTime1]; struct _FILETIME *
0x18010d106  call    ?_DurationFromNow@CLowDiskSpaceUI@@AEAA_KAEBU_FILETIME@@@Z; CLowDiskSpaceUI::_DurationFromNow(_FILETIME const &)
0x18010d10b  mov     rcx, 10C388D000h
0x18010d115  cmp     rax, rcx
0x18010d118  jb      loc_18010D29C
0x18010d11e  lea     r9, [rsp+320h+var_2A8]; unsigned int *
0x18010d123  lea     r8, aNumwinoldlowst; "NumWinOldLowStorageNotify"
0x18010d12a  lea     rdx, aSoftwareMicros_173; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18010d131  mov     rbx, 0FFFFFFFF80000001h
0x18010d138  mov     rcx, rbx; HKEY
0x18010d13b  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18010d140  test    eax, eax
0x18010d142  js      loc_18010D914
0x18010d148  lea     r9, [rsp+320h+FileTime2]; struct _FILETIME *
0x18010d14d  lea     r8, aLastinstalltim; "LastInstallTimeLowStorageNotify"
0x18010d154  lea     rdx, aSoftwareMicros_173; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18010d15b  mov     rcx, rbx; HKEY
0x18010d15e  call    ?SHRegGetFILETIME@@YAJPEAUHKEY__@@PEBG1PEAU_FILETIME@@@Z; SHRegGetFILETIME(HKEY__ *,ushort const *,ushort const *,_FILETIME *)
0x18010d163  test    eax, eax
0x18010d165  js      short loc_18010D19B
0x18010d167  lea     rdx, [rsp+320h+FileTime2]; struct _FILETIME *
0x18010d16c  call    ?_DurationFromNow@CLowDiskSpaceUI@@AEAA_KAEBU_FILETIME@@@Z; CLowDiskSpaceUI::_DurationFromNow(_FILETIME const &)
0x18010d171  mov     rcx, 0C92A69C000h
0x18010d17b  cmp     rax, rcx
0x18010d17e  jb      loc_18010D29C
0x18010d184  lea     rdx, [rsp+320h+FileTime2]; lpFileTime2
0x18010d189  lea     rcx, [rbp+220h+FileTime1]; lpFileTime1
0x18010d18d  call    cs:__imp_CompareFileTime
0x18010d193  test    eax, eax
0x18010d195  jg      loc_18010D914
0x18010d19b  cmp     edi, 7
0x18010d19e  jz      loc_18010D721
0x18010d1a4  cmp     [rsp+320h+var_2A8], 3
0x18010d1a9  jb      loc_18010D721
0x18010d1af  mov     esi, r15d
0x18010d1b2  jmp     loc_18010D721
0x18010d1b7  mov     esi, 1
0x18010d1bc  cmp     edi, 5
0x18010d1bf  jnz     loc_18010D2C9
0x18010d1c5  mov     [rsp+320h+var_2DC], r15d
0x18010d1ca  lea     r8, [rsp+320h+var_2DC]; int *
0x18010d1cf  lea     rdx, aAllowstoragese; "AllowStorageSenseGlobal"
0x18010d1d6  call    ?_GetIsMDMConfigured@CLowDiskSpaceUI@@AEAAJPEBGPEAH@Z; CLowDiskSpaceUI::_GetIsMDMConfigured(ushort const *,int *)
0x18010d1db  test    eax, eax
0x18010d1dd  js      short loc_18010D1EA
0x18010d1df  cmp     [rsp+320h+var_2DC], r15d
0x18010d1e4  jnz     loc_18010D29C
0x18010d1ea  mov     [rsp+320h+var_2E0], r15d
0x18010d1ef  lea     r8, [rsp+320h+var_2E0]
0x18010d1f4  xor     edx, edx
0x18010d1f6  xor     ecx, ecx
0x18010d1f8  call    cs:__imp_GetStoragePolicySettings
0x18010d1fe  test    eax, eax
0x18010d200  js      short loc_18010D20C
0x18010d202  cmp     [rsp+320h+var_2E0], esi
0x18010d206  jz      loc_18010D29C
0x18010d20c  lea     r9, [rsp+320h+var_2C0]; unsigned int *
0x18010d211  lea     r8, aStoragepolicie_0; "StoragePoliciesNotified"
0x18010d218  lea     rdi, aSoftwareMicros_80; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18010d21f  mov     rdx, rdi; unsigned __int16 *
0x18010d222  mov     rbx, 0FFFFFFFF80000001h
0x18010d229  mov     rcx, rbx; HKEY
0x18010d22c  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18010d231  test    eax, eax
0x18010d233  js      short loc_18010D23B
0x18010d235  cmp     [rsp+320h+var_2C0], esi
0x18010d239  jz      short loc_18010D29C
0x18010d23b  lea     r9, [rsp+320h+FileTime2]; struct _FILETIME *
0x18010d240  lea     r8, aLastinstalltim; "LastInstallTimeLowStorageNotify"
0x18010d247  lea     rdx, aSoftwareMicros_173; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18010d24e  mov     rcx, rbx; HKEY
0x18010d251  call    ?SHRegGetFILETIME@@YAJPEAUHKEY__@@PEBG1PEAU_FILETIME@@@Z; SHRegGetFILETIME(HKEY__ *,ushort const *,ushort const *,_FILETIME *)
0x18010d256  test    eax, eax
0x18010d258  js      short loc_18010D273
0x18010d25a  lea     rdx, [rsp+320h+FileTime2]; struct _FILETIME *
0x18010d25f  call    ?_DurationFromNow@CLowDiskSpaceUI@@AEAA_KAEBU_FILETIME@@@Z; CLowDiskSpaceUI::_DurationFromNow(_FILETIME const &)
0x18010d264  mov     rcx, 0C92A69C000h
0x18010d26e  cmp     rax, rcx
0x18010d271  jb      short loc_18010D29C
0x18010d273  lea     r8, aOptintoastfire; "OptinToastFired"
0x18010d27a  lea     r9, [rsp+320h+var_2BC]; unsigned int *
0x18010d27f  mov     rdx, rdi; unsigned __int16 *
0x18010d282  mov     rcx, rbx; HKEY
0x18010d285  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18010d28a  test    eax, eax
0x18010d28c  js      loc_18010D721
0x18010d292  cmp     [rsp+320h+var_2BC], esi
0x18010d296  jb      loc_18010D721
0x18010d29c  xor     eax, eax
0x18010d29e  mov     rcx, [rbp+220h+var_30]
0x18010d2a5  xor     rcx, rsp; StackCookie
0x18010d2a8  call    __security_check_cookie
0x18010d2ad  lea     r11, [rsp+320h+var_20]
0x18010d2b5  mov     rbx, [r11+38h]
0x18010d2b9  mov     rsi, [r11+40h]
0x18010d2bd  mov     rsp, r11
0x18010d2c0  pop     r15
0x18010d2c2  pop     r14
0x18010d2c4  pop     r13
0x18010d2c6  pop     rdi
0x18010d2c7  pop     rbp
0x18010d2c8  retn
0x18010d2c9  cmp     edi, 0Ch
0x18010d2cc  jnz     loc_18010D3AC
0x18010d2d2  mov     [rsp+320h+var_2E0], r15d
0x18010d2d7  lea     r8, [rsp+320h+var_2E0]; int *
0x18010d2dc  lea     rdx, aAllowstoragese; "AllowStorageSenseGlobal"
0x18010d2e3  call    ?_GetIsMDMConfigured@CLowDiskSpaceUI@@AEAAJPEBGPEAH@Z; CLowDiskSpaceUI::_GetIsMDMConfigured(ushort const *,int *)
0x18010d2e8  test    eax, eax
0x18010d2ea  js      short loc_18010D2F3
0x18010d2ec  cmp     [rsp+320h+var_2E0], r15d
0x18010d2f1  jnz     short loc_18010D29C
0x18010d2f3  mov     qword ptr [rsp+320h+var_2C8.dwLowDateTime], r15
0x18010d2f8  lea     rdx, [rsp+320h+var_2C8]; struct _FILETIME *
0x18010d2fd  call    ?_GetOOBETime@CLowDiskSpaceUI@@AEAAJPEAU_FILETIME@@@Z; CLowDiskSpaceUI::_GetOOBETime(_FILETIME *)
0x18010d302  test    eax, eax
0x18010d304  js      short loc_18010D323
0x18010d306  lea     rdx, [rsp+320h+var_2C8]; struct _FILETIME *
0x18010d30b  call    ?_DurationFromNow@CLowDiskSpaceUI@@AEAA_KAEBU_FILETIME@@@Z; CLowDiskSpaceUI::_DurationFromNow(_FILETIME const &)
0x18010d310  mov     rcx, 0C92A69C000h
0x18010d31a  cmp     rax, rcx
0x18010d31d  jb      loc_18010D29C
0x18010d323  mov     [rsp+320h+var_2DC], r15d
0x18010d328  lea     r8, [rsp+320h+var_2DC]
0x18010d32d  xor     edx, edx
0x18010d32f  xor     ecx, ecx
0x18010d331  call    cs:__imp_GetStoragePolicySettings
0x18010d337  test    eax, eax
0x18010d339  js      loc_18010D29C
0x18010d33f  cmp     [rsp+320h+var_2DC], r15d
0x18010d344  jz      loc_18010D29C
0x18010d34a  lea     r9, [rsp+320h+var_2C0]; unsigned int *
0x18010d34f  lea     r8, aStoragepolicie_0; "StoragePoliciesNotified"
0x18010d356  lea     rdi, aSoftwareMicros_80; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18010d35d  mov     rdx, rdi; unsigned __int16 *
0x18010d360  mov     rbx, 0FFFFFFFF80000001h
0x18010d367  mov     rcx, rbx; HKEY
0x18010d36a  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18010d36f  test    eax, eax
0x18010d371  js      short loc_18010D37D
0x18010d373  cmp     [rsp+320h+var_2C0], esi
0x18010d377  jz      loc_18010D29C
0x18010d37d  lea     r9, [rbp+220h+var_298]; unsigned int *
0x18010d381  lea     r8, aStoragepolicie; "StoragePoliciesChanged"
0x18010d388  mov     rdx, rdi; unsigned __int16 *
0x18010d38b  mov     rcx, rbx; HKEY
0x18010d38e  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18010d393  test    eax, eax
0x18010d395  js      short loc_18010D3A0
0x18010d397  cmp     [rbp+220h+var_298], esi
0x18010d39a  jz      loc_18010D29C
0x18010d3a0  lea     r8, aFirstlaunchtoa; "FirstLaunchToastFired"
0x18010d3a7  jmp     loc_18010D27A
0x18010d3ac  cmp     edi, 8
0x18010d3af  jnz     loc_18010D76B
0x18010d3b5  mov     [rsp+320h+var_2E0], r15d
0x18010d3ba  lea     r8, [rsp+320h+var_2E0]; int *
0x18010d3bf  lea     rdx, aConfigstorages; "ConfigStorageSenseCloudContentDehydrati"...
0x18010d3c6  call    ?_GetIsMDMConfigured@CLowDiskSpaceUI@@AEAAJPEBGPEAH@Z; CLowDiskSpaceUI::_GetIsMDMConfigured(ushort const *,int *)
0x18010d3cb  test    eax, eax
0x18010d3cd  js      short loc_18010D3DA
0x18010d3cf  cmp     [rsp+320h+var_2E0], r15d
0x18010d3d4  jnz     loc_18010D29C
0x18010d3da  mov     [rsp+320h+var_2D4], r15d
0x18010d3df  lea     r8, [rsp+320h+var_2D4]
0x18010d3e4  xor     edx, edx
0x18010d3e6  xor     ecx, ecx
0x18010d3e8  call    cs:__imp_GetStoragePolicySettings
0x18010d3ee  test    eax, eax
0x18010d3f0  js      loc_18010D29C
0x18010d3f6  cmp     [rsp+320h+var_2D4], r15d
0x18010d3fb  jz      loc_18010D29C
0x18010d401  mov     [rsp+320h+var_2E0], 8
0x18010d409  lea     rax, [rsp+320h+var_2E0]
0x18010d40e  mov     [rsp+320h+pcbData], rax; pcbData
0x18010d413  lea     rax, [rsp+320h+FileTime2]
0x18010d418  mov     [rsp+320h+pvData], rax; pvData
0x18010d41d  mov     [rsp+320h+pdwType], r15; pdwType
0x18010d422  mov     r9d, 8; dwFlags
0x18010d428  lea     r8, aLastinstalltim; "LastInstallTimeLowStorageNotify"
0x18010d42f  lea     rdx, aSoftwareMicros_173; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18010d436  mov     rbx, 0FFFFFFFF80000001h
0x18010d43d  mov     rcx, rbx; hkey
0x18010d440  call    cs:__imp_RegGetValueW
0x18010d446  mov     r14d, 80070000h
0x18010d44c  test    eax, eax
0x18010d44e  jle     short loc_18010D458
0x18010d450  movzx   eax, ax
0x18010d453  or      eax, r14d
0x18010d456  test    eax, eax
0x18010d458  js      short loc_18010D47F
0x18010d45a  cmp     [rsp+320h+var_2E0], 8
0x18010d45f  jnz     short loc_18010D47F
0x18010d461  lea     rdx, [rsp+320h+FileTime2]; struct _FILETIME *
0x18010d466  call    ?_DurationFromNow@CLowDiskSpaceUI@@AEAA_KAEBU_FILETIME@@@Z; CLowDiskSpaceUI::_DurationFromNow(_FILETIME const &)
0x18010d46b  mov     rcx, 0C92A69C000h
0x18010d475  cmp     rax, rcx
0x18010d478  jnb     short loc_18010D484
0x18010d47a  jmp     loc_18010D29C
0x18010d47f  mov     qword ptr [rsp+320h+FileTime2.dwLowDateTime], r15
0x18010d484  mov     [rsp+320h+var_2D8], 4
0x18010d48c  lea     rax, [rsp+320h+var_2D8]
0x18010d491  mov     [rsp+320h+pcbData], rax; pcbData
0x18010d496  lea     rax, [rbp+220h+var_294]
0x18010d49a  mov     [rsp+320h+pvData], rax; pvData
0x18010d49f  mov     [rsp+320h+pdwType], r15; pdwType
0x18010d4a4  mov     r9d, 10h; dwFlags
0x18010d4aa  lea     r8, aCloudfilepolic; "CloudfilePolicyConsent"
0x18010d4b1  lea     rdi, aSoftwareMicros_80; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18010d4b8  mov     rdx, rdi; lpSubKey
0x18010d4bb  mov     rcx, rbx; hkey
0x18010d4be  call    cs:__imp_RegGetValueW
0x18010d4c4  test    eax, eax
0x18010d4c6  jle     short loc_18010D4D0
0x18010d4c8  movzx   eax, ax
0x18010d4cb  or      eax, r14d
0x18010d4ce  test    eax, eax
0x18010d4d0  js      short loc_18010D4DC
0x18010d4d2  cmp     [rbp+220h+var_294], r15d
0x18010d4d6  jnz     loc_18010D29C
0x18010d4dc  lea     r9, [rbp+220h+var_290]; unsigned int *
0x18010d4e0  lea     r8, aCloudconsentto; "CloudConsentToastCount"
0x18010d4e7  mov     rdx, rdi; unsigned __int16 *
0x18010d4ea  mov     rcx, rbx; HKEY
0x18010d4ed  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18010d4f2  test    eax, eax
0x18010d4f4  js      short loc_18010D500
0x18010d4f6  cmp     [rbp+220h+var_290], 3
0x18010d4fa  jnb     loc_18010D29C
0x18010d500  mov     [rbp+220h+ppv], r15
0x18010d504  mov     qword ptr [rsp+320h+var_2C8.dwLowDateTime], r15
0x18010d509  mov     qword ptr [rsp+320h+var_2B8], r15
0x18010d50e  mov     qword ptr [rsp+320h+var_2B0.dwLowDateTime], r15
0x18010d513  mov     [rbp+220h+var_270], r15
0x18010d517  mov     [rbp+220h+var_268], r15
0x18010d51b  mov     [rbp+220h+var_260], r15
0x18010d51f  mov     [rbp+220h+var_258], r15
0x18010d523  mov     [rbp+220h+var_250], r15
0x18010d527  mov     [rbp+220h+var_248], r15
  ... truncated ...
```
