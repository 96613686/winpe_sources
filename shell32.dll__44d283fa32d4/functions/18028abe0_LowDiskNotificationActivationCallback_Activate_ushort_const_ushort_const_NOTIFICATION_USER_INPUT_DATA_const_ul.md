# LowDiskNotificationActivationCallback::Activate(ushort const *,ushort const *,NOTIFICATION_USER_INPUT_DATA const *,ulong)

- ea: `0x18028abe0`
- end: `0x18028b585`
- name: `?Activate@LowDiskNotificationActivationCallback@@UEAAJPEBG0PEBUNOTIFICATION_USER_INPUT_DATA@@K@Z`
- size: `2469`
- prototype: `int(LowDiskNotificationActivationCallback *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const struct NOTIFICATION_USER_INPUT_DATA *, unsigned int)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000f6cc`
- `0x180038608`
- `0x18007b944`
- `0x1800c23f8`
- `0x1800f5920`
- `0x1801d0a0c`
- `0x180249490`
- `0x1802761f8`
- `0x180289a18`
- `0x180289ae4`
- `0x180289e94`
- `0x180289fd0`
- `0x18028a078`
- `0x18028a120`
- `0x18028a1c8`
- `0x18028a270`
- `0x18028a5d0`
- `0x18028a7a0`
- `0x18028abe0`
- `0x18028be4c`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18028ac32`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18028acef`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18028ad2e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18028ada0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18028af8e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18028b159`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18028b23f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18028b2d0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18028b4d5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18028ac32`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18028acef`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18028ad2e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18028ada0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18028af8e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18028b159`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18028b23f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18028b2d0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18028b4d5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18028b093`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18028b093`
- `ext-ms-win-com-ole32-l1-1-1!CoAllowSetForegroundWindow` at `0x18028b0b2`
- `ext-ms-win-com-ole32-l1-1-1!CoAllowSetForegroundWindow` at `0x18028b0b2`

## string_xrefs

- `0x18028ade0`: `Windows.Foundation.Uri`
- `0x18028b30f`: `Windows.Foundation.Uri`
- `0x18028ace3`: `command:DeleteWinOld_No`
- `0x18028ac26`: `command:DeleteWinOld_Yes`
- `0x18028b233`: `command:CloudAgeOut_Dismiss`
- `0x18028b14d`: `command:CloudAgeOut_Enable`
- `0x18028ad94`: `command:LaunchStoragePolicies`
- `0x18028ad22`: `command:StoragePolicies_ReminderToast`
- `0x18028b2c4`: `command:Backup_Enable`
- `0x18028b4c9`: `command:Backup_Dismiss`
- `0x18028af82`: `command:LaunchSystemStorage`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall LowDiskNotificationActivationCallback::Activate(
        LowDiskNotificationActivationCallback *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct NOTIFICATION_USER_INPUT_DATA *a4)
{
  __int64 v5; // rcx
  const unsigned __int16 *v6; // r8
  const unsigned __int16 *v7; // rdx
  HRESULT v8; // ebx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64, LPVOID *); // rbx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, LPVOID, __int64 *); // rbx
  char v13; // si
  int v15; // eax
  LPVOID v16; // rdi
  __int64 (__fastcall *v17)(LPVOID, __int64, __int64 *); // rbx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64, __int64 *); // rbx
  char v20; // si
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h]
  HSTRING_HEADER v25; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v26; // [rsp+70h] [rbp-90h]
  HSTRING_HEADER v27; // [rsp+78h] [rbp-88h] BYREF
  __int64 v28; // [rsp+90h] [rbp-70h]
  _QWORD v29[42]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v30; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned int v31; // [rsp+1F4h] [rbp+F4h] BYREF
  LPVOID ppv; // [rsp+1F8h] [rbp+F8h] BYREF
  __int64 v33; // [rsp+200h] [rbp+100h] BYREF
  __int64 v34; // [rsp+208h] [rbp+108h] BYREF
  __int64 v35; // [rsp+210h] [rbp+110h] BYREF
  __int64 v36; // [rsp+218h] [rbp+118h] BYREF
  _OWORD v37[21]; // [rsp+220h] [rbp+120h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+398h] [rbp+298h]

  v30 = 0;
  if ( CompareStringOrdinal(a3, -1, L"command:DeleteWinOld_Yes", -1, 0) != 2 )
  {
    if ( CompareStringOrdinal(a3, -1, L"command:DeleteWinOld_No", -1, 0) == 2 )
    {
      v6 = L"NumWinOldLowStorageNotify";
      v7 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\DiskSpaceChecking";
      goto LABEL_42;
    }
    if ( CompareStringOrdinal(a3, -1, L"command:StoragePolicies_ReminderToast", -1, 0) == 2 )
    {
      v30 = SHRegSetDWORD(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\StoragePolicy",
              L"OptOutButtonClicked",
              1u);
      v31 = 1;
      v22 = 1;
      Shell32LoggingTelemetry::StorageToastClicks<unsigned long,long &,int>(&v22, &v30, &v31);
      return 0;
    }
    if ( CompareStringOrdinal(a3, -1, L"command:LaunchStoragePolicies", -1, 0) == 2 )
    {
      v34 = 0;
      v35 = 0;
      ppv = 0;
      v33 = 0;
      v24 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Foundation.Uri",
        0x17u,
        0x16u);
      v8 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
             v24,
             &v35);
      v22 = v8;
      if ( v8 < 0 )
        goto LABEL_13;
      v9 = v35;
      v10 = *(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v35 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      v26 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v25, L"ms-settings:storagepolicies", 0x1Cu, 0x1Bu);
      v30 = 3;
      v8 = v10(v9, v26, &ppv);
      v22 = v8;
      if ( v8 < 0 )
        goto LABEL_13;
      v28 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v27, L"Windows.System.Launcher", 0x18u, 0x17u);
      v30 = 7;
      v8 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics>>(
             v28,
             &v34);
      v22 = v8;
      if ( v8 < 0
        || (v11 = v34,
            v12 = *(__int64 (__fastcall **)(__int64, LPVOID, __int64 *))(*(_QWORD *)v34 + 64LL),
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33),
            v8 = v12(v11, ppv, &v33),
            v22 = v8,
            v8 < 0) )
      {
LABEL_13:
        v13 = 0;
      }
      else
      {
        v13 = 1;
      }
      if ( v13 )
      {
        v22 = 0;
        v8 = 0;
      }
      v31 = 0;
      v30 = 2;
      Shell32LoggingTelemetry::StorageToastClicks<unsigned long,long &,int>(&v30, &v22, &v31);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    }
    else
    {
      if ( CompareStringOrdinal(a3, -1, L"command:LaunchSystemStorage", -1, 0) != 2 )
      {
        if ( CompareStringOrdinal(a3, -1, L"command:CloudAgeOut_Enable", -1, 0) == 2 )
        {
          v30 = 0;
          SHRegGetDWORD(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\StoragePolicy",
            L"CloudConsentToastCount",
            &v30);
          LODWORD(v33) = 0;
          v31 = 4;
          Shell32LoggingTelemetry::StorageToastClicks<unsigned long,int,unsigned long &>(&v31, &v33, &v30);
          SHRegSetDWORD(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\StoragePolicy",
            L"CloudConsentToastCount",
            3u);
          SHRegSetDWORD(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\StoragePolicy",
            L"CloudfilePolicyConsent",
            1u);
          v15 = Windows::Internal::ComTaskPool::QueueTask<_lambda_801389270c9f3bb6703e5b95cfa6771c_>();
          v8 = v15;
          if ( v15 >= 0 )
            return 0;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x8A7,
            (unsigned int)"shell\\shell32\\lowdisk.cpp",
            (const char *)(unsigned int)v15,
            bIgnoreCase);
        }
        else
        {
          if ( CompareStringOrdinal(a3, -1, L"command:CloudAgeOut_Dismiss", -1, 0) == 2 )
          {
            v30 = 0;
            SHRegGetDWORD(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\StoragePolicy",
              L"CloudConsentToastCount",
              &v30);
            LODWORD(v33) = 1223;
            v31 = 4;
            Shell32LoggingTelemetry::StorageToastClicks<unsigned long,long,unsigned long &>(&v31, &v33, &v30);
            v6 = L"CloudConsentToastCount";
            v7 = L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\StoragePolicy";
            goto LABEL_42;
          }
          if ( CompareStringOrdinal(a3, -1, L"command:Backup_Enable", -1, 0) != 2 )
          {
            if ( CompareStringOrdinal(a3, -1, L"command:Backup_Dismiss", -1, 0) != 2 )
              return 0;
            v31 = 0;
            SHRegGetDWORD(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\BackupReminder",
              L"BackupReminderToastCount",
              &v31);
            LODWORD(v33) = 1223;
            v30 = 5;
            Shell32LoggingTelemetry::StorageToastClicks<unsigned long,long,unsigned long &>(&v30, &v33, &v31);
            v6 = L"BackupReminderToastCount";
            v7 = L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\BackupReminder";
LABEL_42:
            SHRegSetDWORD(HKEY_CURRENT_USER, v7, v6, 3u);
            return 0;
          }
          v36 = 0;
          ppv = 0;
          v34 = 0;
          v35 = 0;
          v28 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v27, L"Windows.Foundation.Uri", 0x17u, 0x16u);
          v8 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
                 v28,
                 &ppv);
          v22 = v8;
          if ( v8 < 0 )
            goto LABEL_36;
          v16 = ppv;
          v17 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 48LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
          v26 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v25, L"ms-settings:backup", 0x13u, 0x12u);
          v30 = 24;
          v8 = v17(v16, v26, &v34);
          v22 = v8;
          if ( v8 < 0 )
            goto LABEL_36;
          v24 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(
            &hstringHeader,
            L"Windows.System.Launcher",
            0x18u,
            0x17u);
          v30 = 56;
          v8 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics>>(
                 v24,
                 &v36);
          v22 = v8;
          if ( v8 < 0
            || (v18 = v36,
                v19 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v36 + 64LL),
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35),
                v8 = v19(v18, v34, &v35),
                v22 = v8,
                v8 < 0) )
          {
LABEL_36:
            v20 = 0;
          }
          else
          {
            v20 = 1;
          }
          if ( v20 )
          {
            v22 = 0;
            v8 = 0;
          }
          v31 = 0;
          SHRegGetDWORD(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\BackupReminder",
            L"BackupReminderToastCount",
            &v31);
          LODWORD(v33) = 5;
          Shell32LoggingTelemetry::StorageToastClicks<unsigned long,long &,unsigned long &>(&v33, &v22, &v31);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
        }
        return (unsigned int)v8;
      }
      ppv = 0;
      v37[0] = *(_OWORD *)L"page=SettingsPageStorageSenseStorageOverview&target=SystemSettings_StorageSense_SystemDrive&invoke=true";
      v37[1] = *(_OWORD *)L"tingsPageStorageSenseStorageOverview&target=SystemSettings_StorageSense_SystemDrive&invoke=true";
      v37[2] = *(_OWORD *)L"eStorageSenseStorageOverview&target=SystemSettings_StorageSense_SystemDrive&invoke=true";
      v37[3] = *(_OWORD *)L"SenseStorageOverview&target=SystemSettings_StorageSense_SystemDrive&invoke=true";
      v37[4] = *(_OWORD *)L"rageOverview&target=SystemSettings_StorageSense_SystemDrive&invoke=true";
      v37[5] = *(_OWORD *)L"view&target=SystemSettings_StorageSense_SystemDrive&invoke=true";
      v37[6] = *(_OWORD *)L"get=SystemSettings_StorageSense_SystemDrive&invoke=true";
      v37[7] = *(_OWORD *)L"emSettings_StorageSense_SystemDrive&invoke=true";
      v37[8] = *(_OWORD *)L"gs_StorageSense_SystemDrive&invoke=true";
      v37[9] = *(_OWORD *)L"geSense_SystemDrive&invoke=true";
      v37[10] = *(_OWORD *)L"SystemDrive&invoke=true";
      v37[11] = *(_OWORD *)L"ive&invoke=true";
      v37[12] = *(_OWORD *)L"ke=true";
      v31 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      v8 = CoCreateInstance(
             &CLSID_ApplicationActivationManager,
             0,
             4u,
             &GUID_2e941141_7f97_4756_ba1d_9decde894a3d,
             &ppv);
      v22 = v8;
      if ( v8 >= 0 )
      {
        v8 = CoAllowSetForegroundWindow((IUnknown *)ppv, 0);
        v22 = v8;
        if ( v8 >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(LPVOID, const WCHAR *, _OWORD *, _QWORD, unsigned int *))(*(_QWORD *)ppv + 24LL))(
                 ppv,
                 L"windows.immersivecontrolpanel_cw5n1h2txyewy!microsoft.windows.immersivecontrolpanel",
                 v37,
                 0,
                 &v31);
          v22 = v8;
          if ( v8 >= 0 )
          {
            v22 = 0;
            v8 = 0;
          }
        }
      }
      v30 = 0;
      LODWORD(v33) = 3;
      Shell32LoggingTelemetry::StorageToastClicks<unsigned long,long &,int>(&v33, &v22, &v30);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    }
    if ( v8 < 0 )
      return 0;
    return (unsigned int)v8;
  }
  v31 = 0;
  v30 = 0;
  v22 = 0;
  Shell32LoggingTelemetry::StorageToastClicks<unsigned long,int,int>(&v22, &v30, &v31);
  wil::ActivityBase<Shell32Logging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Shell32Logging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v37);
  *(_QWORD *)&v37[0] = &Shell32LoggingTelemetry::WinOldLowStorageCleanup::`vftable';
  Shell32LoggingTelemetry::WinOldLowStorageCleanup::StartActivity(
    (Shell32LoggingTelemetry::WinOldLowStorageCleanup *)v37,
    a3);
  wil::ActivityBase<Shell32Logging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Shell32Logging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v29,
    v37);
  v29[0] = &Shell32LoggingTelemetry::WinOldLowStorageCleanup::`vftable';
  Windows::Internal::ComTaskPool::QueueTask<_lambda_68629a2cfc93c9567073a2a3da4bf69e_>(v5, v29);
  Shell32LoggingTelemetry::WinOldLowStorageCleanup::~WinOldLowStorageCleanup((Shell32LoggingTelemetry::WinOldLowStorageCleanup *)v29);
  Shell32LoggingTelemetry::WinOldLowStorageCleanup::~WinOldLowStorageCleanup((Shell32LoggingTelemetry::WinOldLowStorageCleanup *)v37);
  return 0;
}

```

## disassembly

```asm
0x18028abe0  mov     [rsp-8+arg_0], rbx
0x18028abe5  mov     [rsp-8+arg_8], rsi
0x18028abea  push    rbp
0x18028abeb  push    rdi
0x18028abec  push    r14
0x18028abee  lea     rbp, [rsp-280h]
0x18028abf6  sub     rsp, 380h
0x18028abfd  mov     rax, cs:__security_cookie
0x18028ac04  xor     rax, rsp
0x18028ac07  mov     [rbp+290h+var_20], rax
0x18028ac0e  mov     rbx, r8
0x18028ac11  xor     r14d, r14d
0x18028ac14  mov     [rbp+290h+var_1A0], r14d
0x18028ac1b  mov     [rsp+390h+bIgnoreCase], r14d; bIgnoreCase
0x18028ac20  or      edi, 0FFFFFFFFh
0x18028ac23  mov     r9d, edi; cchCount2
0x18028ac26  lea     r8, aCommandDeletew_0; "command:DeleteWinOld_Yes"
0x18028ac2d  mov     edx, edi; cchCount1
0x18028ac2f  mov     rcx, rbx; lpString1
0x18028ac32  call    cs:__imp_CompareStringOrdinal
0x18028ac39  nop     dword ptr [rax+rax+00h]
0x18028ac3e  cmp     eax, 2
0x18028ac41  jnz     loc_18028ACDB
0x18028ac47  mov     [rbp+290h+var_19C], r14d
0x18028ac4e  mov     [rbp+290h+var_1A0], r14d
0x18028ac55  mov     [rsp+390h+var_360], r14d
0x18028ac5a  lea     r8, [rbp+290h+var_19C]
0x18028ac61  lea     rdx, [rbp+290h+var_1A0]
0x18028ac68  lea     rcx, [rsp+390h+var_360]
0x18028ac6d  call    ??$StorageToastClicks@KHH@Shell32LoggingTelemetry@@SAX$$QEAK$$QEAH1@Z; Shell32LoggingTelemetry::StorageToastClicks<ulong,int,int>(ulong &&,int &&,int &&)
0x18028ac72  nop
0x18028ac73  lea     rdx, aWinoldlowstora; "WinOldLowStorageCleanup"
0x18028ac7a  lea     rcx, [rbp+290h+var_170]; struct wil::details::IFailureCallback *
0x18028ac81  call    ??0?$ActivityBase@VShell32Logging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Shell32Logging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Shell32Logging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18028ac86  lea     rdi, ??_7WinOldLowStorageCleanup@Shell32LoggingTelemetry@@6B@; const Shell32LoggingTelemetry::WinOldLowStorageCleanup::`vftable'
0x18028ac8d  mov     qword ptr [rbp+290h+var_170], rdi
0x18028ac94  mov     rdx, rbx; unsigned __int16 *
0x18028ac97  lea     rcx, [rbp+290h+var_170]; this
0x18028ac9e  call    ?StartActivity@WinOldLowStorageCleanup@Shell32LoggingTelemetry@@QEAAXPEBG@Z; Shell32LoggingTelemetry::WinOldLowStorageCleanup::StartActivity(ushort const *)
0x18028aca3  nop
0x18028aca4  lea     rdx, [rbp+290h+var_170]
0x18028acab  lea     rcx, [rbp+290h+var_2F0]
0x18028acaf  call    ??0?$ActivityBase@VShell32Logging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<Shell32Logging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Shell32Logging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<Shell32Logging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x18028acb4  mov     [rbp+290h+var_2F0], rdi
0x18028acb8  lea     rdx, [rbp+290h+var_2F0]
0x18028acbc  call    ??$QueueTask@V_lambda_68629a2cfc93c9567073a2a3da4bf69e_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@$$QEAV_lambda_68629a2cfc93c9567073a2a3da4bf69e_@@@Z; Windows::Internal::ComTaskPool::QueueTask<_lambda_68629a2cfc93c9567073a2a3da4bf69e_>(Windows::Internal::TaskApartment,_lambda_68629a2cfc93c9567073a2a3da4bf69e_ &&)
0x18028acc1  lea     rcx, [rbp+290h+var_2F0]; this
0x18028acc5  call    ??1WinOldLowStorageCleanup@Shell32LoggingTelemetry@@QEAA@XZ; Shell32LoggingTelemetry::WinOldLowStorageCleanup::~WinOldLowStorageCleanup(void)
0x18028acca  lea     rcx, [rbp+290h+var_170]; this
0x18028acd1  call    ??1WinOldLowStorageCleanup@Shell32LoggingTelemetry@@QEAA@XZ; Shell32LoggingTelemetry::WinOldLowStorageCleanup::~WinOldLowStorageCleanup(void)
0x18028acd6  jmp     loc_18028B55B
0x18028acdb  mov     [rsp+390h+bIgnoreCase], r14d; bIgnoreCase
0x18028ace0  mov     r9d, edi; cchCount2
0x18028ace3  lea     r8, aCommandDeletew; "command:DeleteWinOld_No"
0x18028acea  mov     edx, edi; cchCount1
0x18028acec  mov     rcx, rbx; lpString1
0x18028acef  call    cs:__imp_CompareStringOrdinal
0x18028acf6  nop     dword ptr [rax+rax+00h]
0x18028acfb  cmp     eax, 2
0x18028acfe  jnz     short loc_18028AD1A
0x18028ad00  lea     r8, aNumwinoldlowst; "NumWinOldLowStorageNotify"
0x18028ad07  lea     rdx, aSoftwareMicros_173; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18028ad0e  mov     rcx, 0FFFFFFFF80000001h
0x18028ad15  jmp     loc_18028B550
0x18028ad1a  mov     [rsp+390h+bIgnoreCase], r14d; bIgnoreCase
0x18028ad1f  mov     r9d, edi; cchCount2
0x18028ad22  lea     r8, aCommandStorage_0; "command:StoragePolicies_ReminderToast"
0x18028ad29  mov     edx, edi; cchCount1
0x18028ad2b  mov     rcx, rbx; lpString1
0x18028ad2e  call    cs:__imp_CompareStringOrdinal
0x18028ad35  nop     dword ptr [rax+rax+00h]
0x18028ad3a  cmp     eax, 2
0x18028ad3d  jnz     short loc_18028AD8C
0x18028ad3f  lea     esi, [rax-1]
0x18028ad42  mov     r9d, esi; unsigned int
0x18028ad45  lea     r8, aOptoutbuttoncl; "OptOutButtonClicked"
0x18028ad4c  lea     rdx, aSoftwareMicros_80; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18028ad53  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x18028ad5a  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18028ad5f  mov     [rbp+290h+var_1A0], eax
0x18028ad65  mov     [rbp+290h+var_19C], esi
0x18028ad6b  mov     [rsp+390h+var_360], esi
0x18028ad6f  lea     r8, [rbp+290h+var_19C]
0x18028ad76  lea     rdx, [rbp+290h+var_1A0]
0x18028ad7d  lea     rcx, [rsp+390h+var_360]
0x18028ad82  call    ??$StorageToastClicks@KAEAJH@Shell32LoggingTelemetry@@SAX$$QEAKAEAJ$$QEAH@Z; Shell32LoggingTelemetry::StorageToastClicks<ulong,long &,int>(ulong &&,long &,int &&)
0x18028ad87  jmp     loc_18028B55B
0x18028ad8c  mov     [rsp+390h+bIgnoreCase], r14d; bIgnoreCase
0x18028ad91  mov     r9d, edi; cchCount2
0x18028ad94  lea     r8, aCommandLaunchs_0; "command:LaunchStoragePolicies"
0x18028ad9b  mov     edx, edi; cchCount1
0x18028ad9d  mov     rcx, rbx; lpString1
0x18028ada0  call    cs:__imp_CompareStringOrdinal
0x18028ada7  nop     dword ptr [rax+rax+00h]
0x18028adac  cmp     eax, 2
0x18028adaf  jnz     loc_18028AF7A
0x18028adb5  mov     [rbp+290h+var_188], r14
0x18028adbc  mov     [rbp+290h+var_180], r14
0x18028adc3  mov     [rbp+290h+ppv], r14
0x18028adca  mov     [rbp+290h+var_190], r14
0x18028add1  mov     [rsp+390h+var_340], r14
0x18028add6  lea     esi, [rax+15h]
0x18028add9  lea     r9d, [rax+14h]; unsigned int
0x18028addd  mov     r8d, esi; unsigned int
0x18028ade0  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x18028ade7  lea     rcx, [rsp+390h+hstringHeader]; hstringHeader
0x18028adec  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18028adf1  nop
0x18028adf2  lea     rdx, [rbp+290h+var_180]
0x18028adf9  mov     rcx, [rsp+390h+var_340]
0x18028adfe  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x18028ae03  mov     ebx, eax
0x18028ae05  mov     [rsp+390h+var_360], eax
0x18028ae09  test    eax, eax
0x18028ae0b  js      loc_18028AEFE
0x18028ae11  mov     rdi, [rbp+290h+var_180]
0x18028ae18  mov     rax, [rdi]
0x18028ae1b  mov     rbx, [rax+30h]
0x18028ae1f  lea     rcx, [rbp+290h+ppv]
0x18028ae26  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18028ae2b  mov     [rsp+390h+var_320], r14
0x18028ae30  lea     r9d, [rsi+4]; unsigned int
0x18028ae34  lea     r8d, [rsi+5]; unsigned int
0x18028ae38  lea     rdx, aMsSettingsStor; "ms-settings:storagepolicies"
0x18028ae3f  lea     rcx, [rsp+390h+var_338]; hstringHeader
0x18028ae44  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18028ae49  nop
0x18028ae4a  mov     [rbp+290h+var_1A0], 3
0x18028ae54  lea     r8, [rbp+290h+ppv]
0x18028ae5b  mov     rdx, [rsp+390h+var_320]
0x18028ae60  mov     rcx, rdi
0x18028ae63  mov     rax, rbx
0x18028ae66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028ae6b  mov     ebx, eax
0x18028ae6d  mov     [rsp+390h+var_360], eax
0x18028ae71  test    eax, eax
0x18028ae73  js      loc_18028AEFE
0x18028ae79  mov     [rbp+290h+var_300], r14
0x18028ae7d  mov     r9d, esi; unsigned int
0x18028ae80  lea     r8d, [rsi+1]; unsigned int
0x18028ae84  lea     rdx, ?RuntimeClass_Windows_System_Launcher@@3QBGB; "Windows.System.Launcher"
0x18028ae8b  lea     rcx, [rsp+390h+var_318]; hstringHeader
0x18028ae90  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18028ae95  nop
0x18028ae96  mov     [rbp+290h+var_1A0], 7
0x18028aea0  lea     rdx, [rbp+290h+var_188]
0x18028aea7  mov     rcx, [rbp+290h+var_300]
0x18028aeab  call    ??$GetActivationFactory@V?$ComPtr@UILauncherStatics@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UILauncherStatics@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics>>)
0x18028aeb0  mov     ebx, eax
0x18028aeb2  mov     [rsp+390h+var_360], eax
0x18028aeb6  test    eax, eax
0x18028aeb8  js      short loc_18028AEFE
0x18028aeba  mov     rdi, [rbp+290h+var_188]
0x18028aec1  mov     rax, [rdi]
0x18028aec4  mov     rbx, [rax+40h]
0x18028aec8  lea     rcx, [rbp+290h+var_190]
0x18028aecf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18028aed4  lea     r8, [rbp+290h+var_190]
0x18028aedb  mov     rdx, [rbp+290h+ppv]
0x18028aee2  mov     rcx, rdi
0x18028aee5  mov     rax, rbx
0x18028aee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028aeed  mov     ebx, eax
0x18028aeef  mov     [rsp+390h+var_360], eax
0x18028aef3  test    eax, eax
0x18028aef5  js      short loc_18028AEFE
0x18028aef7  mov     esi, 1
0x18028aefc  jmp     short loc_18028AF01
0x18028aefe  mov     sil, r14b
0x18028af01  test    sil, sil
0x18028af04  jz      short loc_18028AF0E
0x18028af06  mov     [rsp+390h+var_360], r14d
0x18028af0b  mov     ebx, r14d
0x18028af0e  mov     [rbp+290h+var_19C], r14d
0x18028af15  mov     [rbp+290h+var_1A0], 2
0x18028af1f  lea     r8, [rbp+290h+var_19C]
0x18028af26  lea     rdx, [rsp+390h+var_360]
0x18028af2b  lea     rcx, [rbp+290h+var_1A0]
0x18028af32  call    ??$StorageToastClicks@KAEAJH@Shell32LoggingTelemetry@@SAX$$QEAKAEAJ$$QEAH@Z; Shell32LoggingTelemetry::StorageToastClicks<ulong,long &,int>(ulong &&,long &,int &&)
0x18028af37  nop
0x18028af38  lea     rcx, [rbp+290h+var_190]
0x18028af3f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18028af44  nop
0x18028af45  lea     rcx, [rbp+290h+ppv]
0x18028af4c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18028af51  nop
0x18028af52  lea     rcx, [rbp+290h+var_180]
0x18028af59  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18028af5e  nop
0x18028af5f  lea     rcx, [rbp+290h+var_188]
0x18028af66  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18028af6b  test    ebx, ebx
0x18028af6d  js      loc_18028B55B
0x18028af73  mov     eax, ebx
0x18028af75  jmp     loc_18028B55D
0x18028af7a  mov     [rsp+390h+bIgnoreCase], r14d; bIgnoreCase
0x18028af7f  mov     r9d, edi; cchCount2
0x18028af82  lea     r8, aCommandLaunchs; "command:LaunchSystemStorage"
0x18028af89  mov     edx, edi; cchCount1
0x18028af8b  mov     rcx, rbx; lpString1
0x18028af8e  call    cs:__imp_CompareStringOrdinal
0x18028af95  nop     dword ptr [rax+rax+00h]
0x18028af9a  cmp     eax, 2
0x18028af9d  jnz     loc_18028B145
0x18028afa3  mov     [rbp+290h+ppv], r14
0x18028afaa  movaps  xmm0, xmmword ptr cs:aPageSettingspa_0; "page=SettingsPageStorageSenseStorageOve"...
0x18028afb1  movups  [rbp+290h+var_170], xmm0
0x18028afb8  movaps  xmm1, xmmword ptr cs:aPageSettingspa_0+10h; "tingsPageStorageSenseStorageOverview&ta"...
0x18028afbf  movups  [rbp+290h+var_160], xmm1
0x18028afc6  movaps  xmm0, xmmword ptr cs:aPageSettingspa_0+20h; "eStorageSenseStorageOverview&target=Sys"...
0x18028afcd  movups  [rbp+290h+var_150], xmm0
0x18028afd4  movaps  xmm1, xmmword ptr cs:aPageSettingspa_0+30h; "SenseStorageOverview&target=SystemSetti"...
0x18028afdb  movups  [rbp+290h+var_140], xmm1
0x18028afe2  movaps  xmm0, xmmword ptr cs:aPageSettingspa_0+40h; "rageOverview&target=SystemSettings_Stor"...
0x18028afe9  movups  [rbp+290h+var_130], xmm0
0x18028aff0  movaps  xmm1, xmmword ptr cs:aPageSettingspa_0+50h; "view&target=SystemSettings_StorageSense"...
0x18028aff7  movups  [rbp+290h+var_120], xmm1
0x18028affe  movaps  xmm0, xmmword ptr cs:aPageSettingspa_0+60h; "get=SystemSettings_StorageSense_SystemD"...
0x18028b005  movups  [rbp+290h+var_110], xmm0
0x18028b00c  movaps  xmm1, xmmword ptr cs:aPageSettingspa_0+70h; "emSettings_StorageSense_SystemDrive&inv"...
0x18028b013  movups  [rbp+290h+var_100], xmm1
0x18028b01a  movaps  xmm0, xmmword ptr cs:aPageSettingspa_0+80h; "gs_StorageSense_SystemDrive&invoke=true"
0x18028b021  movups  [rbp+290h+var_F0], xmm0
0x18028b028  movaps  xmm1, xmmword ptr cs:aPageSettingspa_0+90h; "geSense_SystemDrive&invoke=true"
0x18028b02f  movups  [rbp+290h+var_E0], xmm1
0x18028b036  movaps  xmm0, xmmword ptr cs:aPageSettingspa_0+0A0h; "SystemDrive&invoke=true"
0x18028b03d  movups  [rbp+290h+var_D0], xmm0
0x18028b044  movaps  xmm1, xmmword ptr cs:aPageSettingspa_0+0B0h; "ive&invoke=true"
0x18028b04b  movups  [rbp+290h+var_C0], xmm1
0x18028b052  movaps  xmm0, xmmword ptr cs:aPageSettingspa_0+0C0h; "ke=true"
0x18028b059  movups  [rbp+290h+var_B0], xmm0
0x18028b060  mov     [rbp+290h+var_19C], r14d
0x18028b067  lea     rcx, [rbp+290h+ppv]
0x18028b06e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18028b073  lea     rax, [rbp+290h+ppv]
0x18028b07a  mov     qword ptr [rsp+390h+bIgnoreCase], rax; ppv
0x18028b07f  lea     r9, _GUID_2e941141_7f97_4756_ba1d_9decde894a3d; riid
0x18028b086  xor     edx, edx; pUnkOuter
0x18028b088  lea     r8d, [rdx+4]; dwClsContext
0x18028b08c  lea     rcx, CLSID_ApplicationActivationManager; rclsid
0x18028b093  call    cs:__imp_CoCreateInstance
0x18028b09a  nop     dword ptr [rax+rax+00h]
0x18028b09f  mov     ebx, eax
0x18028b0a1  mov     [rsp+390h+var_360], eax
0x18028b0a5  test    eax, eax
0x18028b0a7  js      short loc_18028B10A
0x18028b0a9  xor     edx, edx; lpvReserved
0x18028b0ab  mov     rcx, [rbp+290h+ppv]; pUnk
0x18028b0b2  call    cs:__imp_CoAllowSetForegroundWindow
0x18028b0b9  nop     dword ptr [rax+rax+00h]
0x18028b0be  mov     ebx, eax
0x18028b0c0  mov     [rsp+390h+var_360], eax
0x18028b0c4  test    eax, eax
0x18028b0c6  js      short loc_18028B10A
0x18028b0c8  mov     rcx, [rbp+290h+ppv]
0x18028b0cf  mov     rax, [rcx]
0x18028b0d2  lea     rdx, [rbp+290h+var_19C]
0x18028b0d9  mov     qword ptr [rsp+390h+bIgnoreCase], rdx
0x18028b0de  xor     r9d, r9d
0x18028b0e1  lea     r8, [rbp+290h+var_170]
0x18028b0e8  lea     rdx, aWindowsImmersi; "windows.immersivecontrolpanel_cw5n1h2tx"...
0x18028b0ef  mov     rax, [rax+18h]
0x18028b0f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028b0f8  mov     ebx, eax
0x18028b0fa  mov     [rsp+390h+var_360], eax
0x18028b0fe  test    eax, eax
0x18028b100  js      short loc_18028B10A
0x18028b102  mov     [rsp+390h+var_360], r14d
0x18028b107  mov     ebx, r14d
0x18028b10a  mov     [rbp+290h+var_1A0], r14d
0x18028b111  mov     dword ptr [rbp+290h+var_190], 3
0x18028b11b  lea     r8, [rbp+290h+var_1A0]
0x18028b122  lea     rdx, [rsp+390h+var_360]
0x18028b127  lea     rcx, [rbp+290h+var_190]
0x18028b12e  call    ??$StorageToastClicks@KAEAJH@Shell32LoggingTelemetry@@SAX$$QEAKAEAJ$$QEAH@Z; Shell32LoggingTelemetry::StorageToastClicks<ulong,long &,int>(ulong &&,long &,int &&)
0x18028b133  nop
0x18028b134  lea     rcx, [rbp+290h+ppv]
0x18028b13b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18028b140  jmp     loc_18028AF6B
0x18028b145  mov     [rsp+390h+bIgnoreCase], r14d; int
0x18028b14a  mov     r9d, edi; cchCount2
0x18028b14d  lea     r8, aCommandCloudag_0; "command:CloudAgeOut_Enable"
0x18028b154  mov     edx, edi; cchCount1
0x18028b156  mov     rcx, rbx; lpString1
0x18028b159  call    cs:__imp_CompareStringOrdinal
0x18028b160  nop     dword ptr [rax+rax+00h]
0x18028b165  cmp     eax, 2
0x18028b168  jnz     loc_18028B22B
0x18028b16e  mov     [rbp+290h+var_1A0], r14d
0x18028b175  lea     r9, [rbp+290h+var_1A0]; unsigned int *
0x18028b17c  lea     r8, aCloudconsentto; "CloudConsentToastCount"
0x18028b183  lea     rdx, aSoftwareMicros_80; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18028b18a  mov     rdi, 0FFFFFFFF80000001h
0x18028b191  mov     rcx, rdi; HKEY
0x18028b194  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18028b199  mov     dword ptr [rbp+290h+var_190], r14d
0x18028b1a0  mov     [rbp+290h+var_19C], 4
0x18028b1aa  lea     r8, [rbp+290h+var_1A0]
0x18028b1b1  lea     rdx, [rbp+290h+var_190]
0x18028b1b8  lea     rcx, [rbp+290h+var_19C]
  ... truncated ...
```
