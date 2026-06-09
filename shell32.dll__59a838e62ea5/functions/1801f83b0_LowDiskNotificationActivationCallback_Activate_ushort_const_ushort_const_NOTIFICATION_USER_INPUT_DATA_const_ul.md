# LowDiskNotificationActivationCallback::Activate(ushort const *,ushort const *,NOTIFICATION_USER_INPUT_DATA const *,ulong)

- ea: `0x1801f83b0`
- end: `0x1801f8d6e`
- name: `?Activate@LowDiskNotificationActivationCallback@@UEAAJPEBG0PEBUNOTIFICATION_USER_INPUT_DATA@@K@Z`
- size: `2494`
- prototype: `int(LowDiskNotificationActivationCallback *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const struct NOTIFICATION_USER_INPUT_DATA *, unsigned int)`
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000f05c`
- `0x18003cd64`
- `0x18007fd24`
- `0x1800b2640`
- `0x1800b8f00`
- `0x1800f188c`
- `0x1801bb990`
- `0x1801f83b0`
- `0x1801f8d74`
- `0x180233280`
- `0x18025e21c`
- `0x180270e08`
- `0x180270ebc`
- `0x180270ef8`
- `0x18027130c`
- `0x1802713b4`
- `0x18027145c`
- `0x180271504`
- `0x1802715ac`
- `0x180271904`
- `0x180272768`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801f84b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801f84b0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801f8402`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801f8515`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801f854e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801f85ba`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801f87a2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801f895b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801f8a3b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801f8ac6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801f8cc5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801f8402`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801f8515`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801f854e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801f85ba`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801f87a2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801f895b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801f8a3b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801f8ac6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801f8cc5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801f88a1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801f88a1`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1801f84cb`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1801f84cb`
- `ext-ms-win-com-ole32-l1-1-1!CoAllowSetForegroundWindow` at `0x1801f88ba`
- `ext-ms-win-com-ole32-l1-1-1!CoAllowSetForegroundWindow` at `0x1801f88ba`

## string_xrefs

- `0x1801f85f4`: `Windows.Foundation.Uri`
- `0x1801f8aff`: `Windows.Foundation.Uri`
- `0x1801f8509`: `command:DeleteWinOld_No`
- `0x1801f83f6`: `command:DeleteWinOld_Yes`
- `0x1801f85ae`: `command:LaunchStoragePolicies`
- `0x1801f8542`: `command:StoragePolicies_ReminderToast`
- `0x1801f8cb9`: `command:Backup_Dismiss`
- `0x1801f8aba`: `command:Backup_Enable`
- `0x1801f894f`: `command:CloudAgeOut_Enable`
- `0x1801f8a2f`: `command:CloudAgeOut_Dismiss`
- `0x1801f8796`: `command:LaunchSystemStorage`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall LowDiskNotificationActivationCallback::Activate(
        LowDiskNotificationActivationCallback *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct NOTIFICATION_USER_INPUT_DATA *a4)
{
  __int64 *v5; // rax
  __int64 v6; // rbx
  DWORD CurrentThreadId; // eax
  const unsigned __int16 *v8; // r8
  const unsigned __int16 *v9; // rdx
  HRESULT v10; // ebx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64, LPVOID *); // rbx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, LPVOID, __int64 *); // rbx
  char v15; // si
  int v17; // eax
  LPVOID v18; // rdi
  __int64 (__fastcall *v19)(LPVOID, __int64, __int64 *); // rbx
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, __int64, __int64 *); // rbx
  char v22; // si
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+50h] [rbp-B0h]
  HSTRING_HEADER v27; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+70h] [rbp-90h]
  HSTRING_HEADER v29; // [rsp+78h] [rbp-88h] BYREF
  __int64 v30; // [rsp+90h] [rbp-70h]
  _QWORD v31[42]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v32; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned int v33; // [rsp+1F4h] [rbp+F4h] BYREF
  LPVOID ppv; // [rsp+1F8h] [rbp+F8h] BYREF
  __int64 v35; // [rsp+200h] [rbp+100h] BYREF
  __int64 v36; // [rsp+208h] [rbp+108h] BYREF
  __int64 v37; // [rsp+210h] [rbp+110h] BYREF
  __int64 v38; // [rsp+218h] [rbp+118h] BYREF
  _OWORD v39[21]; // [rsp+220h] [rbp+120h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+398h] [rbp+298h]

  v32 = 0;
  if ( CompareStringOrdinal(a3, -1, L"command:DeleteWinOld_Yes", -1, 0) == 2 )
  {
    v33 = 0;
    v32 = 0;
    v24 = 0;
    Shell32LoggingTelemetry::StorageToastClicks<unsigned long,int,int>(&v24, &v32, &v33);
    wil::ActivityBase<Shell32Logging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Shell32Logging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v39);
    *(_QWORD *)&v39[0] = &Shell32LoggingTelemetry::WinOldLowStorageCleanup::`vftable';
    Shell32LoggingTelemetry::WinOldLowStorageCleanup::StartActivity(
      (Shell32LoggingTelemetry::WinOldLowStorageCleanup *)v39,
      a3);
    wil::ActivityBase<Shell32Logging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Shell32Logging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
      v31,
      v39);
    v31[0] = &Shell32LoggingTelemetry::WinOldLowStorageCleanup::`vftable';
    v5 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_68629a2cfc93c9567073a2a3da4bf69e_>,_lambda_68629a2cfc93c9567073a2a3da4bf69e_>(
                      &v38,
                      v31);
    v6 = *v5;
    *v5 = 0;
    if ( v38 )
    {
      v38 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::Release();
    }
    CurrentThreadId = GetCurrentThreadId();
    SHTaskPoolQueueTask(3, 0, CurrentThreadId);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    Shell32LoggingTelemetry::WinOldLowStorageCleanup::~WinOldLowStorageCleanup((Shell32LoggingTelemetry::WinOldLowStorageCleanup *)v31);
    Shell32LoggingTelemetry::WinOldLowStorageCleanup::~WinOldLowStorageCleanup((Shell32LoggingTelemetry::WinOldLowStorageCleanup *)v39);
    return 0;
  }
  if ( CompareStringOrdinal(a3, -1, L"command:DeleteWinOld_No", -1, 0) == 2 )
  {
    v8 = L"NumWinOldLowStorageNotify";
    v9 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\DiskSpaceChecking";
LABEL_46:
    SHRegSetDWORD(HKEY_CURRENT_USER, v9, v8, 3u);
    return 0;
  }
  if ( CompareStringOrdinal(a3, -1, L"command:StoragePolicies_ReminderToast", -1, 0) == 2 )
  {
    v32 = SHRegSetDWORD(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\StoragePolicy",
            L"OptOutButtonClicked",
            1u);
    v33 = 1;
    v24 = 1;
    Shell32LoggingTelemetry::StorageToastClicks<unsigned long,long &,int>(&v24, &v32, &v33);
    return 0;
  }
  if ( CompareStringOrdinal(a3, -1, L"command:LaunchStoragePolicies", -1, 0) == 2 )
  {
    v36 = 0;
    v37 = 0;
    ppv = 0;
    v35 = 0;
    v26 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Foundation.Uri", 0x17u, 0x16u);
    v10 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
            v26,
            &v37);
    v24 = v10;
    if ( v10 < 0 )
      goto LABEL_17;
    v11 = v37;
    v12 = *(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v37 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    v28 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v27, L"ms-settings:storagepolicies", 0x1Cu, 0x1Bu);
    v32 = 3;
    v10 = v12(v11, v28, &ppv);
    v24 = v10;
    if ( v10 < 0 )
      goto LABEL_17;
    v30 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v29, L"Windows.System.Launcher", 0x18u, 0x17u);
    v32 = 7;
    v10 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics>>(
            v30,
            &v36);
    v24 = v10;
    if ( v10 < 0
      || (v13 = v36,
          v14 = *(__int64 (__fastcall **)(__int64, LPVOID, __int64 *))(*(_QWORD *)v36 + 64LL),
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35),
          v10 = v14(v13, ppv, &v35),
          v24 = v10,
          v10 < 0) )
    {
LABEL_17:
      v15 = 0;
    }
    else
    {
      v15 = 1;
    }
    if ( v15 )
    {
      v24 = 0;
      v10 = 0;
    }
    v33 = 0;
    v32 = 2;
    Shell32LoggingTelemetry::StorageToastClicks<unsigned long,long &,int>(&v32, &v24, &v33);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
    goto LABEL_21;
  }
  if ( CompareStringOrdinal(a3, -1, L"command:LaunchSystemStorage", -1, 0) == 2 )
  {
    ppv = 0;
    v39[0] = *(_OWORD *)L"page=SettingsPageStorageSenseStorageOverview&target=SystemSettings_StorageSense_SystemDrive&invoke=true";
    v39[1] = *(_OWORD *)L"tingsPageStorageSenseStorageOverview&target=SystemSettings_StorageSense_SystemDrive&invoke=true";
    v39[2] = *(_OWORD *)L"eStorageSenseStorageOverview&target=SystemSettings_StorageSense_SystemDrive&invoke=true";
    v39[3] = *(_OWORD *)L"SenseStorageOverview&target=SystemSettings_StorageSense_SystemDrive&invoke=true";
    v39[4] = *(_OWORD *)L"rageOverview&target=SystemSettings_StorageSense_SystemDrive&invoke=true";
    v39[5] = *(_OWORD *)L"view&target=SystemSettings_StorageSense_SystemDrive&invoke=true";
    v39[6] = *(_OWORD *)L"get=SystemSettings_StorageSense_SystemDrive&invoke=true";
    v39[7] = *(_OWORD *)L"emSettings_StorageSense_SystemDrive&invoke=true";
    v39[8] = *(_OWORD *)L"gs_StorageSense_SystemDrive&invoke=true";
    v39[9] = *(_OWORD *)L"geSense_SystemDrive&invoke=true";
    v39[10] = *(_OWORD *)L"SystemDrive&invoke=true";
    v39[11] = *(_OWORD *)L"ive&invoke=true";
    v39[12] = *(_OWORD *)L"ke=true";
    v33 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    v10 = CoCreateInstance(&CLSID_ApplicationActivationManager, 0, 4u, &GUID_2e941141_7f97_4756_ba1d_9decde894a3d, &ppv);
    v24 = v10;
    if ( v10 >= 0 )
    {
      v10 = CoAllowSetForegroundWindow((IUnknown *)ppv, 0);
      v24 = v10;
      if ( v10 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(LPVOID, const WCHAR *, _OWORD *, _QWORD, unsigned int *))(*(_QWORD *)ppv + 24LL))(
                ppv,
                L"windows.immersivecontrolpanel_cw5n1h2txyewy!microsoft.windows.immersivecontrolpanel",
                v39,
                0,
                &v33);
        v24 = v10;
        if ( v10 >= 0 )
        {
          v24 = 0;
          v10 = 0;
        }
      }
    }
    v32 = 0;
    LODWORD(v35) = 3;
    Shell32LoggingTelemetry::StorageToastClicks<unsigned long,long &,int>(&v35, &v24, &v32);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
LABEL_21:
    if ( v10 < 0 )
      return 0;
    return (unsigned int)v10;
  }
  if ( CompareStringOrdinal(a3, -1, L"command:CloudAgeOut_Enable", -1, 0) == 2 )
  {
    v32 = 0;
    SHRegGetDWORD(
      HKEY_CURRENT_USER,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\StoragePolicy",
      L"CloudConsentToastCount",
      &v32);
    LODWORD(v35) = 0;
    v33 = 4;
    Shell32LoggingTelemetry::StorageToastClicks<unsigned long,int,unsigned long &>(&v33, &v35, &v32);
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
    v17 = Windows::Internal::ComTaskPool::QueueTask<_lambda_801389270c9f3bb6703e5b95cfa6771c_>();
    v10 = v17;
    if ( v17 >= 0 )
      return 0;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8A7,
      (unsigned int)"shell\\shell32\\lowdisk.cpp",
      (const char *)(unsigned int)v17,
      bIgnoreCase);
    return (unsigned int)v10;
  }
  if ( CompareStringOrdinal(a3, -1, L"command:CloudAgeOut_Dismiss", -1, 0) == 2 )
  {
    v32 = 0;
    SHRegGetDWORD(
      HKEY_CURRENT_USER,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\StoragePolicy",
      L"CloudConsentToastCount",
      &v32);
    LODWORD(v35) = 1223;
    v33 = 4;
    Shell32LoggingTelemetry::StorageToastClicks<unsigned long,long,unsigned long &>(&v33, &v35, &v32);
    v8 = L"CloudConsentToastCount";
    v9 = L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\StoragePolicy";
    goto LABEL_46;
  }
  if ( CompareStringOrdinal(a3, -1, L"command:Backup_Enable", -1, 0) == 2 )
  {
    v38 = 0;
    ppv = 0;
    v36 = 0;
    v37 = 0;
    v30 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v29, L"Windows.Foundation.Uri", 0x17u, 0x16u);
    v10 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
            v30,
            &ppv);
    v24 = v10;
    if ( v10 < 0 )
      goto LABEL_40;
    v18 = ppv;
    v19 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
    v28 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v27, L"ms-settings:backup", 0x13u, 0x12u);
    v32 = 24;
    v10 = v19(v18, v28, &v36);
    v24 = v10;
    if ( v10 < 0 )
      goto LABEL_40;
    v26 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.System.Launcher",
      0x18u,
      0x17u);
    v32 = 56;
    v10 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics>>(
            v26,
            &v38);
    v24 = v10;
    if ( v10 < 0
      || (v20 = v38,
          v21 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v38 + 64LL),
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37),
          v10 = v21(v20, v36, &v37),
          v24 = v10,
          v10 < 0) )
    {
LABEL_40:
      v22 = 0;
    }
    else
    {
      v22 = 1;
    }
    if ( v22 )
    {
      v24 = 0;
      v10 = 0;
    }
    v33 = 0;
    SHRegGetDWORD(
      HKEY_CURRENT_USER,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\BackupReminder",
      L"BackupReminderToastCount",
      &v33);
    LODWORD(v35) = 5;
    Shell32LoggingTelemetry::StorageToastClicks<unsigned long,long &,unsigned long &>(&v35, &v24, &v33);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
    return (unsigned int)v10;
  }
  if ( CompareStringOrdinal(a3, -1, L"command:Backup_Dismiss", -1, 0) == 2 )
  {
    v33 = 0;
    SHRegGetDWORD(
      HKEY_CURRENT_USER,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\BackupReminder",
      L"BackupReminderToastCount",
      &v33);
    LODWORD(v35) = 1223;
    v32 = 5;
    Shell32LoggingTelemetry::StorageToastClicks<unsigned long,long,unsigned long &>(&v32, &v35, &v33);
    v8 = L"BackupReminderToastCount";
    v9 = L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\BackupReminder";
    goto LABEL_46;
  }
  return 0;
}

```

## disassembly

```asm
0x1801f83b0  mov     [rsp-8+arg_0], rbx
0x1801f83b5  mov     [rsp-8+arg_8], rsi
0x1801f83ba  push    rbp
0x1801f83bb  push    rdi
0x1801f83bc  push    r14
0x1801f83be  lea     rbp, [rsp-280h]
0x1801f83c6  sub     rsp, 380h
0x1801f83cd  mov     rax, cs:__security_cookie
0x1801f83d4  xor     rax, rsp
0x1801f83d7  mov     [rbp+290h+var_20], rax
0x1801f83de  mov     rbx, r8
0x1801f83e1  xor     r14d, r14d
0x1801f83e4  mov     [rbp+290h+var_1A0], r14d
0x1801f83eb  mov     [rsp+390h+bIgnoreCase], r14d; bIgnoreCase
0x1801f83f0  or      edi, 0FFFFFFFFh
0x1801f83f3  mov     r9d, edi; cchCount2
0x1801f83f6  lea     r8, aCommandDeletew_0; "command:DeleteWinOld_Yes"
0x1801f83fd  mov     edx, edi; cchCount1
0x1801f83ff  mov     rcx, rbx; lpString1
0x1801f8402  call    cs:__imp_CompareStringOrdinal
0x1801f8408  cmp     eax, 2
0x1801f840b  jnz     loc_1801F8501
0x1801f8411  mov     [rbp+290h+var_19C], r14d
0x1801f8418  mov     [rbp+290h+var_1A0], r14d
0x1801f841f  mov     [rsp+390h+var_360], r14d
0x1801f8424  lea     r8, [rbp+290h+var_19C]
0x1801f842b  lea     rdx, [rbp+290h+var_1A0]
0x1801f8432  lea     rcx, [rsp+390h+var_360]
0x1801f8437  call    ??$StorageToastClicks@KHH@Shell32LoggingTelemetry@@SAX$$QEAK$$QEAH1@Z; Shell32LoggingTelemetry::StorageToastClicks<ulong,int,int>(ulong &&,int &&,int &&)
0x1801f843c  nop
0x1801f843d  lea     rdx, aWinoldlowstora; "WinOldLowStorageCleanup"
0x1801f8444  lea     rcx, [rbp+290h+var_170]; struct wil::details::IFailureCallback *
0x1801f844b  call    ??0?$ActivityBase@VShell32Logging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Shell32Logging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Shell32Logging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1801f8450  lea     rdi, ??_7WinOldLowStorageCleanup@Shell32LoggingTelemetry@@6B@; const Shell32LoggingTelemetry::WinOldLowStorageCleanup::`vftable'
0x1801f8457  mov     qword ptr [rbp+290h+var_170], rdi
0x1801f845e  mov     rdx, rbx; unsigned __int16 *
0x1801f8461  lea     rcx, [rbp+290h+var_170]; this
0x1801f8468  call    ?StartActivity@WinOldLowStorageCleanup@Shell32LoggingTelemetry@@QEAAXPEBG@Z; Shell32LoggingTelemetry::WinOldLowStorageCleanup::StartActivity(ushort const *)
0x1801f846d  nop
0x1801f846e  lea     rdx, [rbp+290h+var_170]
0x1801f8475  lea     rcx, [rbp+290h+var_2F0]
0x1801f8479  call    ??0?$ActivityBase@VShell32Logging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<Shell32Logging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Shell32Logging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<Shell32Logging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x1801f847e  mov     [rbp+290h+var_2F0], rdi
0x1801f8482  lea     rdx, [rbp+290h+var_2F0]
0x1801f8486  lea     rcx, [rbp+290h+var_178]
0x1801f848d  call    ??$Make@V?$CTaskWrapper@V_lambda_68629a2cfc93c9567073a2a3da4bf69e_@@@ComTaskPool@Internal@Windows@@V_lambda_68629a2cfc93c9567073a2a3da4bf69e_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_68629a2cfc93c9567073a2a3da4bf69e_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_68629a2cfc93c9567073a2a3da4bf69e_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_68629a2cfc93c9567073a2a3da4bf69e_>,_lambda_68629a2cfc93c9567073a2a3da4bf69e_>(_lambda_68629a2cfc93c9567073a2a3da4bf69e_ &&)
0x1801f8492  mov     rbx, [rax]
0x1801f8495  mov     [rax], r14
0x1801f8498  mov     rcx, [rbp+290h+var_178]
0x1801f849f  test    rcx, rcx
0x1801f84a2  jz      short loc_1801F84B0
0x1801f84a4  mov     [rbp+290h+var_178], r14
0x1801f84ab  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UICreateObject@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::Release(void)
0x1801f84b0  call    cs:__imp_GetCurrentThreadId
0x1801f84b6  mov     [rsp+390h+var_368], r14
0x1801f84bb  mov     qword ptr [rsp+390h+bIgnoreCase], rbx
0x1801f84c0  xor     r9d, r9d
0x1801f84c3  mov     r8d, eax
0x1801f84c6  xor     edx, edx
0x1801f84c8  lea     ecx, [rdx+3]
0x1801f84cb  call    cs:__imp_SHTaskPoolQueueTask
0x1801f84d1  nop
0x1801f84d2  test    rbx, rbx
0x1801f84d5  jz      short loc_1801F84E7
0x1801f84d7  mov     rax, [rbx]
0x1801f84da  mov     rcx, rbx
0x1801f84dd  mov     rax, [rax+10h]
0x1801f84e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f84e6  nop
0x1801f84e7  lea     rcx, [rbp+290h+var_2F0]; this
0x1801f84eb  call    ??1WinOldLowStorageCleanup@Shell32LoggingTelemetry@@QEAA@XZ; Shell32LoggingTelemetry::WinOldLowStorageCleanup::~WinOldLowStorageCleanup(void)
0x1801f84f0  lea     rcx, [rbp+290h+var_170]; this
0x1801f84f7  call    ??1WinOldLowStorageCleanup@Shell32LoggingTelemetry@@QEAA@XZ; Shell32LoggingTelemetry::WinOldLowStorageCleanup::~WinOldLowStorageCleanup(void)
0x1801f84fc  jmp     loc_1801F8D45
0x1801f8501  mov     [rsp+390h+bIgnoreCase], r14d; bIgnoreCase
0x1801f8506  mov     r9d, edi; cchCount2
0x1801f8509  lea     r8, aCommandDeletew; "command:DeleteWinOld_No"
0x1801f8510  mov     edx, edi; cchCount1
0x1801f8512  mov     rcx, rbx; lpString1
0x1801f8515  call    cs:__imp_CompareStringOrdinal
0x1801f851b  cmp     eax, 2
0x1801f851e  jnz     short loc_1801F853A
0x1801f8520  lea     r8, aNumwinoldlowst; "NumWinOldLowStorageNotify"
0x1801f8527  lea     rdx, aSoftwareMicros_173; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801f852e  mov     rcx, 0FFFFFFFF80000001h
0x1801f8535  jmp     loc_1801F8D3A
0x1801f853a  mov     [rsp+390h+bIgnoreCase], r14d; bIgnoreCase
0x1801f853f  mov     r9d, edi; cchCount2
0x1801f8542  lea     r8, aCommandStorage_0; "command:StoragePolicies_ReminderToast"
0x1801f8549  mov     edx, edi; cchCount1
0x1801f854b  mov     rcx, rbx; lpString1
0x1801f854e  call    cs:__imp_CompareStringOrdinal
0x1801f8554  cmp     eax, 2
0x1801f8557  jnz     short loc_1801F85A6
0x1801f8559  lea     esi, [rax-1]
0x1801f855c  mov     r9d, esi; unsigned int
0x1801f855f  lea     r8, aOptoutbuttoncl; "OptOutButtonClicked"
0x1801f8566  lea     rdx, aSoftwareMicros_80; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801f856d  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1801f8574  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1801f8579  mov     [rbp+290h+var_1A0], eax
0x1801f857f  mov     [rbp+290h+var_19C], esi
0x1801f8585  mov     [rsp+390h+var_360], esi
0x1801f8589  lea     r8, [rbp+290h+var_19C]
0x1801f8590  lea     rdx, [rbp+290h+var_1A0]
0x1801f8597  lea     rcx, [rsp+390h+var_360]
0x1801f859c  call    ??$StorageToastClicks@KAEAJH@Shell32LoggingTelemetry@@SAX$$QEAKAEAJ$$QEAH@Z; Shell32LoggingTelemetry::StorageToastClicks<ulong,long &,int>(ulong &&,long &,int &&)
0x1801f85a1  jmp     loc_1801F8D45
0x1801f85a6  mov     [rsp+390h+bIgnoreCase], r14d; bIgnoreCase
0x1801f85ab  mov     r9d, edi; cchCount2
0x1801f85ae  lea     r8, aCommandLaunchs_0; "command:LaunchStoragePolicies"
0x1801f85b5  mov     edx, edi; cchCount1
0x1801f85b7  mov     rcx, rbx; lpString1
0x1801f85ba  call    cs:__imp_CompareStringOrdinal
0x1801f85c0  cmp     eax, 2
0x1801f85c3  jnz     loc_1801F878E
0x1801f85c9  mov     [rbp+290h+var_188], r14
0x1801f85d0  mov     [rbp+290h+var_180], r14
0x1801f85d7  mov     [rbp+290h+ppv], r14
0x1801f85de  mov     [rbp+290h+var_190], r14
0x1801f85e5  mov     [rsp+390h+var_340], r14
0x1801f85ea  lea     esi, [rax+15h]
0x1801f85ed  lea     r9d, [rax+14h]; unsigned int
0x1801f85f1  mov     r8d, esi; unsigned int
0x1801f85f4  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x1801f85fb  lea     rcx, [rsp+390h+hstringHeader]; hstringHeader
0x1801f8600  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801f8605  nop
0x1801f8606  lea     rdx, [rbp+290h+var_180]
0x1801f860d  mov     rcx, [rsp+390h+var_340]
0x1801f8612  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x1801f8617  mov     ebx, eax
0x1801f8619  mov     [rsp+390h+var_360], eax
0x1801f861d  test    eax, eax
0x1801f861f  js      loc_1801F8712
0x1801f8625  mov     rdi, [rbp+290h+var_180]
0x1801f862c  mov     rax, [rdi]
0x1801f862f  mov     rbx, [rax+30h]
0x1801f8633  lea     rcx, [rbp+290h+ppv]
0x1801f863a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801f863f  mov     [rsp+390h+var_320], r14
0x1801f8644  lea     r9d, [rsi+4]; unsigned int
0x1801f8648  lea     r8d, [rsi+5]; unsigned int
0x1801f864c  lea     rdx, aMsSettingsStor; "ms-settings:storagepolicies"
0x1801f8653  lea     rcx, [rsp+390h+var_338]; hstringHeader
0x1801f8658  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801f865d  nop
0x1801f865e  mov     [rbp+290h+var_1A0], 3
0x1801f8668  lea     r8, [rbp+290h+ppv]
0x1801f866f  mov     rdx, [rsp+390h+var_320]
0x1801f8674  mov     rcx, rdi
0x1801f8677  mov     rax, rbx
0x1801f867a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f867f  mov     ebx, eax
0x1801f8681  mov     [rsp+390h+var_360], eax
0x1801f8685  test    eax, eax
0x1801f8687  js      loc_1801F8712
0x1801f868d  mov     [rbp+290h+var_300], r14
0x1801f8691  mov     r9d, esi; unsigned int
0x1801f8694  lea     r8d, [rsi+1]; unsigned int
0x1801f8698  lea     rdx, ?RuntimeClass_Windows_System_Launcher@@3QBGB; "Windows.System.Launcher"
0x1801f869f  lea     rcx, [rsp+390h+var_318]; hstringHeader
0x1801f86a4  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801f86a9  nop
0x1801f86aa  mov     [rbp+290h+var_1A0], 7
0x1801f86b4  lea     rdx, [rbp+290h+var_188]
0x1801f86bb  mov     rcx, [rbp+290h+var_300]
0x1801f86bf  call    ??$GetActivationFactory@V?$ComPtr@UILauncherStatics@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UILauncherStatics@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics>>)
0x1801f86c4  mov     ebx, eax
0x1801f86c6  mov     [rsp+390h+var_360], eax
0x1801f86ca  test    eax, eax
0x1801f86cc  js      short loc_1801F8712
0x1801f86ce  mov     rdi, [rbp+290h+var_188]
0x1801f86d5  mov     rax, [rdi]
0x1801f86d8  mov     rbx, [rax+40h]
0x1801f86dc  lea     rcx, [rbp+290h+var_190]
0x1801f86e3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801f86e8  lea     r8, [rbp+290h+var_190]
0x1801f86ef  mov     rdx, [rbp+290h+ppv]
0x1801f86f6  mov     rcx, rdi
0x1801f86f9  mov     rax, rbx
0x1801f86fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f8701  mov     ebx, eax
0x1801f8703  mov     [rsp+390h+var_360], eax
0x1801f8707  test    eax, eax
0x1801f8709  js      short loc_1801F8712
0x1801f870b  mov     esi, 1
0x1801f8710  jmp     short loc_1801F8715
0x1801f8712  mov     sil, r14b
0x1801f8715  test    sil, sil
0x1801f8718  jz      short loc_1801F8722
0x1801f871a  mov     [rsp+390h+var_360], r14d
0x1801f871f  mov     ebx, r14d
0x1801f8722  mov     [rbp+290h+var_19C], r14d
0x1801f8729  mov     [rbp+290h+var_1A0], 2
0x1801f8733  lea     r8, [rbp+290h+var_19C]
0x1801f873a  lea     rdx, [rsp+390h+var_360]
0x1801f873f  lea     rcx, [rbp+290h+var_1A0]
0x1801f8746  call    ??$StorageToastClicks@KAEAJH@Shell32LoggingTelemetry@@SAX$$QEAKAEAJ$$QEAH@Z; Shell32LoggingTelemetry::StorageToastClicks<ulong,long &,int>(ulong &&,long &,int &&)
0x1801f874b  nop
0x1801f874c  lea     rcx, [rbp+290h+var_190]
0x1801f8753  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801f8758  nop
0x1801f8759  lea     rcx, [rbp+290h+ppv]
0x1801f8760  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801f8765  nop
0x1801f8766  lea     rcx, [rbp+290h+var_180]
0x1801f876d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801f8772  nop
0x1801f8773  lea     rcx, [rbp+290h+var_188]
0x1801f877a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801f877f  test    ebx, ebx
0x1801f8781  js      loc_1801F8D45
0x1801f8787  mov     eax, ebx
0x1801f8789  jmp     loc_1801F8D47
0x1801f878e  mov     [rsp+390h+bIgnoreCase], r14d; bIgnoreCase
0x1801f8793  mov     r9d, edi; cchCount2
0x1801f8796  lea     r8, aCommandLaunchs; "command:LaunchSystemStorage"
0x1801f879d  mov     edx, edi; cchCount1
0x1801f879f  mov     rcx, rbx; lpString1
0x1801f87a2  call    cs:__imp_CompareStringOrdinal
0x1801f87a8  cmp     eax, 2
0x1801f87ab  jnz     loc_1801F8947
0x1801f87b1  mov     [rbp+290h+ppv], r14
0x1801f87b8  movaps  xmm0, xmmword ptr cs:aPageSettingspa_0; "page=SettingsPageStorageSenseStorageOve"...
0x1801f87bf  movups  [rbp+290h+var_170], xmm0
0x1801f87c6  movaps  xmm1, xmmword ptr cs:aPageSettingspa_0+10h; "tingsPageStorageSenseStorageOverview&ta"...
0x1801f87cd  movups  [rbp+290h+var_160], xmm1
0x1801f87d4  movaps  xmm0, xmmword ptr cs:aPageSettingspa_0+20h; "eStorageSenseStorageOverview&target=Sys"...
0x1801f87db  movups  [rbp+290h+var_150], xmm0
0x1801f87e2  movaps  xmm1, xmmword ptr cs:aPageSettingspa_0+30h; "SenseStorageOverview&target=SystemSetti"...
0x1801f87e9  movups  [rbp+290h+var_140], xmm1
0x1801f87f0  movaps  xmm0, xmmword ptr cs:aPageSettingspa_0+40h; "rageOverview&target=SystemSettings_Stor"...
0x1801f87f7  movups  [rbp+290h+var_130], xmm0
0x1801f87fe  movaps  xmm1, xmmword ptr cs:aPageSettingspa_0+50h; "view&target=SystemSettings_StorageSense"...
0x1801f8805  movups  [rbp+290h+var_120], xmm1
0x1801f880c  movaps  xmm0, xmmword ptr cs:aPageSettingspa_0+60h; "get=SystemSettings_StorageSense_SystemD"...
0x1801f8813  movups  [rbp+290h+var_110], xmm0
0x1801f881a  movaps  xmm1, xmmword ptr cs:aPageSettingspa_0+70h; "emSettings_StorageSense_SystemDrive&inv"...
0x1801f8821  movups  [rbp+290h+var_100], xmm1
0x1801f8828  movaps  xmm0, xmmword ptr cs:aPageSettingspa_0+80h; "gs_StorageSense_SystemDrive&invoke=true"
0x1801f882f  movups  [rbp+290h+var_F0], xmm0
0x1801f8836  movaps  xmm1, xmmword ptr cs:aPageSettingspa_0+90h; "geSense_SystemDrive&invoke=true"
0x1801f883d  movups  [rbp+290h+var_E0], xmm1
0x1801f8844  movaps  xmm0, xmmword ptr cs:aPageSettingspa_0+0A0h; "SystemDrive&invoke=true"
0x1801f884b  movups  [rbp+290h+var_D0], xmm0
0x1801f8852  movaps  xmm1, xmmword ptr cs:aPageSettingspa_0+0B0h; "ive&invoke=true"
0x1801f8859  movups  [rbp+290h+var_C0], xmm1
0x1801f8860  movaps  xmm0, xmmword ptr cs:aPageSettingspa_0+0C0h; "ke=true"
0x1801f8867  movups  [rbp+290h+var_B0], xmm0
0x1801f886e  mov     [rbp+290h+var_19C], r14d
0x1801f8875  lea     rcx, [rbp+290h+ppv]
0x1801f887c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801f8881  lea     rax, [rbp+290h+ppv]
0x1801f8888  mov     qword ptr [rsp+390h+bIgnoreCase], rax; ppv
0x1801f888d  lea     r9, _GUID_2e941141_7f97_4756_ba1d_9decde894a3d; riid
0x1801f8894  xor     edx, edx; pUnkOuter
0x1801f8896  lea     r8d, [rdx+4]; dwClsContext
0x1801f889a  lea     rcx, CLSID_ApplicationActivationManager; rclsid
0x1801f88a1  call    cs:__imp_CoCreateInstance
0x1801f88a7  mov     ebx, eax
0x1801f88a9  mov     [rsp+390h+var_360], eax
0x1801f88ad  test    eax, eax
0x1801f88af  js      short loc_1801F890C
0x1801f88b1  xor     edx, edx; lpvReserved
0x1801f88b3  mov     rcx, [rbp+290h+ppv]; pUnk
0x1801f88ba  call    cs:__imp_CoAllowSetForegroundWindow
0x1801f88c0  mov     ebx, eax
0x1801f88c2  mov     [rsp+390h+var_360], eax
0x1801f88c6  test    eax, eax
0x1801f88c8  js      short loc_1801F890C
0x1801f88ca  mov     rcx, [rbp+290h+ppv]
0x1801f88d1  mov     rax, [rcx]
0x1801f88d4  lea     rdx, [rbp+290h+var_19C]
0x1801f88db  mov     qword ptr [rsp+390h+bIgnoreCase], rdx
0x1801f88e0  xor     r9d, r9d
0x1801f88e3  lea     r8, [rbp+290h+var_170]
0x1801f88ea  lea     rdx, aWindowsImmersi; "windows.immersivecontrolpanel_cw5n1h2tx"...
0x1801f88f1  mov     rax, [rax+18h]
0x1801f88f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f88fa  mov     ebx, eax
0x1801f88fc  mov     [rsp+390h+var_360], eax
0x1801f8900  test    eax, eax
0x1801f8902  js      short loc_1801F890C
0x1801f8904  mov     [rsp+390h+var_360], r14d
0x1801f8909  mov     ebx, r14d
0x1801f890c  mov     [rbp+290h+var_1A0], r14d
0x1801f8913  mov     dword ptr [rbp+290h+var_190], 3
0x1801f891d  lea     r8, [rbp+290h+var_1A0]
0x1801f8924  lea     rdx, [rsp+390h+var_360]
0x1801f8929  lea     rcx, [rbp+290h+var_190]
0x1801f8930  call    ??$StorageToastClicks@KAEAJH@Shell32LoggingTelemetry@@SAX$$QEAKAEAJ$$QEAH@Z; Shell32LoggingTelemetry::StorageToastClicks<ulong,long &,int>(ulong &&,long &,int &&)
0x1801f8935  nop
0x1801f8936  lea     rcx, [rbp+290h+ppv]
0x1801f893d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801f8942  jmp     loc_1801F877F
0x1801f8947  mov     [rsp+390h+bIgnoreCase], r14d; int
0x1801f894c  mov     r9d, edi; cchCount2
0x1801f894f  lea     r8, aCommandCloudag_0; "command:CloudAgeOut_Enable"
0x1801f8956  mov     edx, edi; cchCount1
  ... truncated ...
```
