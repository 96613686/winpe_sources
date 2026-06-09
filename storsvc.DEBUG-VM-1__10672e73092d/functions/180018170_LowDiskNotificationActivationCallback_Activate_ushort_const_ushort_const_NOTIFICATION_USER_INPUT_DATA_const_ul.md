# LowDiskNotificationActivationCallback::Activate(ushort const *,ushort const *,NOTIFICATION_USER_INPUT_DATA const *,ulong)

- ea: `0x180018170`
- end: `0x180018867`
- name: `?Activate@LowDiskNotificationActivationCallback@@UEAAJPEBG0PEBUNOTIFICATION_USER_INPUT_DATA@@K@Z`
- size: `1783`
- prototype: `int(LowDiskNotificationActivationCallback *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const struct NOTIFICATION_USER_INPUT_DATA *, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000d030`
- `0x180012734`
- `0x180014a00`
- `0x180017500`
- `0x18001780c`
- `0x18001784c`
- `0x180017b84`
- `0x180017c3c`
- `0x180018170`
- `0x180018c0c`
- `0x180018cc0`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800181bb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800181e4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180018216`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001824c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800183fb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180018536`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800185de`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180018633`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800187fe`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800181bb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800181e4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180018216`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001824c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800183fb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180018536`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800185de`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180018633`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800187fe`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800184ce`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800184ce`
- `ext-ms-win-com-ole32-l1-1-1!CoAllowSetForegroundWindow` at `0x1800184df`
- `ext-ms-win-com-ole32-l1-1-1!CoAllowSetForegroundWindow` at `0x1800184df`

## string_xrefs

- `0x18001827b`: `Windows.Foundation.Uri`
- `0x180018663`: `Windows.Foundation.Uri`
- `0x1800181af`: `command:DeleteWinOld_Yes`
- `0x1800181d8`: `command:DeleteWinOld_No`
- `0x18001820a`: `command:StoragePolicies_ReminderToast`
- `0x180018240`: `command:LaunchStoragePolicies`
- `0x18001852a`: `command:CloudAgeOut_Enable`
- `0x1800185d2`: `command:CloudAgeOut_Dismiss`
- `0x1800187f2`: `command:Backup_Dismiss`
- `0x180018627`: `command:Backup_Enable`
- `0x1800185b4`: `onecore\drivers\storage\storsvc\service\dsktoplowdisk.cpp`
- `0x1800183ef`: `command:LaunchSystemStorage`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall LowDiskNotificationActivationCallback::Activate(
        LowDiskNotificationActivationCallback *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct NOTIFICATION_USER_INPUT_DATA *a4)
{
  HKEY v5; // rcx
  const unsigned __int16 *v6; // r8
  const unsigned __int16 *v7; // rdx
  unsigned int v8; // r9d
  char v9; // si
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64, LPVOID *); // rbx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, LPVOID, unsigned int *); // rbx
  char v15; // cl
  int v16; // ebx
  HKEY v18; // rcx
  HKEY v19; // rcx
  int v20; // eax
  char v21; // si
  int v22; // eax
  LPVOID v23; // rdi
  __int64 (__fastcall *v24)(LPVOID, __int64, __int64 *); // rbx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, __int64, __int64 *); // rbx
  char v27; // r14
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  LPVOID ppv; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v30[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v33; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING_HEADER v34; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+78h] [rbp-88h]
  HSTRING_HEADER v36; // [rsp+80h] [rbp-80h] BYREF
  __int64 v37; // [rsp+98h] [rbp-68h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v39; // [rsp+B8h] [rbp-48h]
  _OWORD v40[13]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  if ( CompareStringOrdinal(a3, -1, L"command:DeleteWinOld_Yes", -1, 0) != 2 )
  {
    if ( CompareStringOrdinal(a3, -1, L"command:DeleteWinOld_No", -1, 0) == 2 )
    {
      v6 = L"NumWinOldLowStorageNotify";
      v7 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\DiskSpaceChecking";
LABEL_52:
      v8 = 3;
      goto LABEL_53;
    }
    if ( CompareStringOrdinal(a3, -1, L"command:StoragePolicies_ReminderToast", -1, 0) == 2 )
    {
      v8 = 1;
      v6 = L"OptOutButtonClicked";
LABEL_7:
      v7 = L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\StoragePolicy";
LABEL_53:
      SHRegSetDWORD(v5, v7, v6, v8);
      return 0;
    }
    if ( CompareStringOrdinal(a3, -1, L"command:LaunchStoragePolicies", -1, 0) == 2 )
    {
      v31 = 0;
      v32 = 0;
      ppv = 0;
      *(_QWORD *)v30 = 0;
      v39 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Foundation.Uri",
        0x17u,
        0x16u);
      v9 = 1;
      v10 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
              v39,
              &v32);
      if ( v10 < 0 )
        goto LABEL_13;
      v11 = v32;
      v12 = *(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v32 + 48LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
      v37 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v36, L"ms-settings:storagepolicies", 0x1Cu, 0x1Bu);
      v9 = 3;
      v10 = v12(v11, v37, &ppv);
      if ( v10 < 0 )
        goto LABEL_13;
      v35 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v34, L"Windows.System.Launcher", 0x18u, 0x17u);
      v9 = 7;
      v10 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics>>(
              v35,
              &v31);
      if ( v10 < 0
        || (v13 = v31,
            v14 = *(__int64 (__fastcall **)(__int64, LPVOID, unsigned int *))(*(_QWORD *)v31 + 64LL),
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v30),
            v10 = v14(v13, ppv, v30),
            v15 = 1,
            v10 < 0) )
      {
LABEL_13:
        v15 = 0;
      }
      if ( (v9 & 4) != 0 )
      {
        v9 &= ~4u;
        v35 = 0;
      }
      if ( (v9 & 2) != 0 )
      {
        v9 &= ~2u;
        v37 = 0;
      }
      if ( (v9 & 1) != 0 )
        v39 = 0;
      v16 = 0;
      if ( !v15 )
        v16 = v10;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v30);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
      if ( v16 < 0 )
        return 0;
    }
    else
    {
      if ( CompareStringOrdinal(a3, -1, L"command:LaunchSystemStorage", -1, 0) == 2 )
      {
        ppv = 0;
        v40[0] = *(_OWORD *)L"page=SettingsPageStorageSenseStorageOverview&target=SystemSettings_StorageSense_SystemDrive&invoke=true";
        v40[1] = *(_OWORD *)L"tingsPageStorageSenseStorageOverview&target=SystemSettings_StorageSense_SystemDrive&invoke=true";
        v40[2] = *(_OWORD *)L"eStorageSenseStorageOverview&target=SystemSettings_StorageSense_SystemDrive&invoke=true";
        v40[3] = *(_OWORD *)L"SenseStorageOverview&target=SystemSettings_StorageSense_SystemDrive&invoke=true";
        v40[4] = *(_OWORD *)L"rageOverview&target=SystemSettings_StorageSense_SystemDrive&invoke=true";
        v40[5] = *(_OWORD *)L"view&target=SystemSettings_StorageSense_SystemDrive&invoke=true";
        v40[6] = *(_OWORD *)L"get=SystemSettings_StorageSense_SystemDrive&invoke=true";
        v40[7] = *(_OWORD *)L"emSettings_StorageSense_SystemDrive&invoke=true";
        v40[8] = *(_OWORD *)L"gs_StorageSense_SystemDrive&invoke=true";
        v40[9] = *(_OWORD *)L"geSense_SystemDrive&invoke=true";
        v40[10] = *(_OWORD *)L"SystemDrive&invoke=true";
        v40[11] = *(_OWORD *)L"ive&invoke=true";
        v40[12] = *(_OWORD *)L"ke=true";
        v30[0] = 0;
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
        if ( CoCreateInstance(
               &CLSID_ApplicationActivationManager,
               0,
               4u,
               &GUID_2e941141_7f97_4756_ba1d_9decde894a3d,
               &ppv) >= 0
          && CoAllowSetForegroundWindow((IUnknown *)ppv, 0) >= 0 )
        {
          (*(void (__fastcall **)(LPVOID, const wchar_t *, _OWORD *, _QWORD, unsigned int *))(*(_QWORD *)ppv + 24LL))(
            ppv,
            L"windows.immersivecontrolpanel_cw5n1h2txyewy!microsoft.windows.immersivecontrolpanel",
            v40,
            0,
            v30);
        }
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
        return 0;
      }
      if ( CompareStringOrdinal(a3, -1, L"command:CloudAgeOut_Enable", -1, 0) == 2 )
      {
        v30[0] = 0;
        SHRegGetDWORD(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\StoragePolicy",
          L"CloudConsentToastCount",
          v30);
        SHRegSetDWORD(
          v18,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\StoragePolicy",
          L"CloudConsentToastCount",
          3u);
        SHRegSetDWORD(
          v19,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\StoragePolicy",
          L"CloudfilePolicyConsent",
          1u);
        v20 = Windows::Internal::ComTaskPool::QueueTask<_lambda_7dc4ac9b600921e8e3fa6fc24b24baf0_>();
        v16 = v20;
        if ( v20 >= 0 )
          return 0;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x790,
          (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\dsktoplowdisk.cpp",
          (const char *)(unsigned int)v20,
          bIgnoreCase);
      }
      else
      {
        if ( CompareStringOrdinal(a3, -1, L"command:CloudAgeOut_Dismiss", -1, 0) == 2 )
        {
          v30[0] = 0;
          SHRegGetDWORD(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\StoragePolicy",
            L"CloudConsentToastCount",
            v30);
          v8 = 3;
          v6 = L"CloudConsentToastCount";
          goto LABEL_7;
        }
        if ( CompareStringOrdinal(a3, -1, L"command:Backup_Enable", -1, 0) != 2 )
        {
          if ( CompareStringOrdinal(a3, -1, L"command:Backup_Dismiss", -1, 0) != 2 )
            return 0;
          v30[0] = 0;
          SHRegGetDWORD(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\BackupReminder",
            L"BackupReminderToastCount",
            v30);
          v6 = L"BackupReminderToastCount";
          v7 = L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\BackupReminder";
          goto LABEL_52;
        }
        v33 = 0;
        ppv = 0;
        v31 = 0;
        v32 = 0;
        v35 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v34, L"Windows.Foundation.Uri", 0x17u, 0x16u);
        v21 = 8;
        v22 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
                v35,
                &ppv);
        if ( v22 < 0 )
          goto LABEL_40;
        v23 = ppv;
        v24 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 48LL);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
        v37 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v36, L"ms-settings:backup", 0x13u, 0x12u);
        v21 = 24;
        v22 = v24(v23, v37, &v31);
        if ( v22 < 0 )
          goto LABEL_40;
        v39 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.System.Launcher",
          0x18u,
          0x17u);
        v21 = 56;
        v22 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics>>(
                v39,
                &v33);
        if ( v22 < 0
          || (v25 = v33,
              v26 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v33 + 64LL),
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32),
              v22 = v26(v25, v31, &v32),
              v22 < 0) )
        {
LABEL_40:
          v27 = 0;
        }
        else
        {
          v27 = 1;
        }
        if ( (v21 & 0x20) != 0 )
        {
          v21 &= ~0x20u;
          v39 = 0;
        }
        if ( (v21 & 0x10) != 0 )
        {
          v21 &= ~0x10u;
          v37 = 0;
        }
        if ( (v21 & 8) != 0 )
          v35 = 0;
        v16 = 0;
        if ( !v27 )
          v16 = v22;
        v30[0] = 0;
        SHRegGetDWORD(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\BackupReminder",
          L"BackupReminderToastCount",
          v30);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
      }
    }
    return (unsigned int)v16;
  }
  Windows::Internal::ComTaskPool::QueueTask<_lambda_62052a4312895de2745c1598789222b9_>();
  return 0;
}

```

## disassembly

```asm
0x180018170  push    rbp
0x180018172  push    rbx
0x180018173  push    rsi
0x180018174  push    rdi
0x180018175  push    r12
0x180018177  push    r14
0x180018179  lea     rbp, [rsp-0A8h]
0x180018181  sub     rsp, 1A8h
0x180018188  mov     rax, cs:__security_cookie
0x18001818f  xor     rax, rsp
0x180018192  mov     [rbp+0D0h+var_40], rax
0x180018199  mov     rbx, r8
0x18001819c  xor     r12d, r12d
0x18001819f  mov     [rsp+1D0h+var_1A0], r12d
0x1800181a4  mov     [rsp+1D0h+bIgnoreCase], r12d; bIgnoreCase
0x1800181a9  or      edi, 0FFFFFFFFh
0x1800181ac  mov     r9d, edi; cchCount2
0x1800181af  lea     r8, String2; "command:DeleteWinOld_Yes"
0x1800181b6  mov     edx, edi; cchCount1
0x1800181b8  mov     rcx, rbx; lpString1
0x1800181bb  call    cs:__imp_CompareStringOrdinal
0x1800181c1  cmp     eax, 2
0x1800181c4  jnz     short loc_1800181D0
0x1800181c6  call    ??$QueueTask@V_lambda_62052a4312895de2745c1598789222b9_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@$$QEAV_lambda_62052a4312895de2745c1598789222b9_@@@Z; Windows::Internal::ComTaskPool::QueueTask<_lambda_62052a4312895de2745c1598789222b9_>(Windows::Internal::TaskApartment,_lambda_62052a4312895de2745c1598789222b9_ &&)
0x1800181cb  jmp     loc_180018846
0x1800181d0  mov     [rsp+1D0h+bIgnoreCase], r12d; bIgnoreCase
0x1800181d5  mov     r9d, edi; cchCount2
0x1800181d8  lea     r8, aCommandDeletew; "command:DeleteWinOld_No"
0x1800181df  mov     edx, edi; cchCount1
0x1800181e1  mov     rcx, rbx; lpString1
0x1800181e4  call    cs:__imp_CompareStringOrdinal
0x1800181ea  cmp     eax, 2
0x1800181ed  jnz     short loc_180018202
0x1800181ef  lea     r8, aNumwinoldlowst; "NumWinOldLowStorageNotify"
0x1800181f6  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800181fd  jmp     loc_18001883B
0x180018202  mov     [rsp+1D0h+bIgnoreCase], r12d; bIgnoreCase
0x180018207  mov     r9d, edi; cchCount2
0x18001820a  lea     r8, aCommandStorage; "command:StoragePolicies_ReminderToast"
0x180018211  mov     edx, edi; cchCount1
0x180018213  mov     rcx, rbx; lpString1
0x180018216  call    cs:__imp_CompareStringOrdinal
0x18001821c  cmp     eax, 2
0x18001821f  jnz     short loc_180018238
0x180018221  lea     r9d, [rax-1]
0x180018225  lea     r8, aOptoutbuttoncl; "OptOutButtonClicked"
0x18001822c  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180018233  jmp     loc_180018841
0x180018238  mov     [rsp+1D0h+bIgnoreCase], r12d; bIgnoreCase
0x18001823d  mov     r9d, edi; cchCount2
0x180018240  lea     r8, aCommandLaunchs_0; "command:LaunchStoragePolicies"
0x180018247  mov     edx, edi; cchCount1
0x180018249  mov     rcx, rbx; lpString1
0x18001824c  call    cs:__imp_CompareStringOrdinal
0x180018252  cmp     eax, 2
0x180018255  jnz     loc_1800183E7
0x18001825b  mov     [rsp+1D0h+var_188], r12
0x180018260  mov     [rsp+1D0h+var_180], r12
0x180018265  mov     [rsp+1D0h+ppv], r12
0x18001826a  mov     qword ptr [rsp+1D0h+var_190], r12
0x18001826f  mov     [rbp+0D0h+var_118], r12
0x180018273  lea     r9d, [rax+14h]; unsigned int
0x180018277  lea     r8d, [rax+15h]; unsigned int
0x18001827b  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x180018282  lea     rcx, [rbp+0D0h+hstringHeader]; hstringHeader
0x180018286  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001828b  nop
0x18001828c  mov     r14d, 1
0x180018292  mov     esi, r14d
0x180018295  mov     [rsp+1D0h+var_1A0], r14d
0x18001829a  lea     rdx, [rsp+1D0h+var_180]
0x18001829f  mov     rcx, [rbp+0D0h+var_118]
0x1800182a3  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x1800182a8  test    eax, eax
0x1800182aa  js      loc_18001836F
0x1800182b0  mov     rdi, [rsp+1D0h+var_180]
0x1800182b5  mov     rax, [rdi]
0x1800182b8  mov     rbx, [rax+30h]
0x1800182bc  lea     rcx, [rsp+1D0h+ppv]
0x1800182c1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800182c6  mov     [rbp+0D0h+var_138], r12
0x1800182ca  lea     r9d, [r14+1Ah]; unsigned int
0x1800182ce  lea     r8d, [r14+1Bh]; unsigned int
0x1800182d2  lea     rdx, sourceString; "ms-settings:storagepolicies"
0x1800182d9  lea     rcx, [rbp+0D0h+var_150]; hstringHeader
0x1800182dd  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800182e2  nop
0x1800182e3  lea     esi, [r14+2]
0x1800182e7  mov     [rsp+1D0h+var_1A0], esi
0x1800182eb  lea     r8, [rsp+1D0h+ppv]
0x1800182f0  mov     rdx, [rbp+0D0h+var_138]
0x1800182f4  mov     rcx, rdi
0x1800182f7  mov     rax, rbx
0x1800182fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182ff  test    eax, eax
0x180018301  js      short loc_18001836F
0x180018303  mov     [rsp+1D0h+var_158], r12
0x180018308  lea     r9d, [r14+16h]; unsigned int
0x18001830c  lea     r8d, [r14+17h]; unsigned int
0x180018310  lea     rdx, ?RuntimeClass_Windows_System_Launcher@@3QBGB; "Windows.System.Launcher"
0x180018317  lea     rcx, [rsp+1D0h+var_170]; hstringHeader
0x18001831c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180018321  nop
0x180018322  lea     esi, [r14+6]
0x180018326  mov     [rsp+1D0h+var_1A0], esi
0x18001832a  lea     rdx, [rsp+1D0h+var_188]
0x18001832f  mov     rcx, [rsp+1D0h+var_158]
0x180018334  call    ??$GetActivationFactory@V?$ComPtr@UILauncherStatics@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UILauncherStatics@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics>>)
0x180018339  test    eax, eax
0x18001833b  js      short loc_18001836F
0x18001833d  mov     rdi, [rsp+1D0h+var_188]
0x180018342  mov     rax, [rdi]
0x180018345  mov     rbx, [rax+40h]
0x180018349  lea     rcx, [rsp+1D0h+var_190]
0x18001834e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180018353  lea     r8, [rsp+1D0h+var_190]
0x180018358  mov     rdx, [rsp+1D0h+ppv]
0x18001835d  mov     rcx, rdi
0x180018360  mov     rax, rbx
0x180018363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018368  test    eax, eax
0x18001836a  mov     cl, r14b
0x18001836d  jns     short loc_180018372
0x18001836f  mov     cl, r12b
0x180018372  test    sil, 4
0x180018376  jz      short loc_180018384
0x180018378  and     esi, 0FFFFFFFBh
0x18001837b  mov     [rsp+1D0h+var_1A0], esi
0x18001837f  mov     [rsp+1D0h+var_158], r12
0x180018384  test    sil, 2
0x180018388  jz      short loc_180018395
0x18001838a  and     esi, 0FFFFFFFDh
0x18001838d  mov     [rsp+1D0h+var_1A0], esi
0x180018391  mov     [rbp+0D0h+var_138], r12
0x180018395  test    r14b, sil
0x180018398  jz      short loc_1800183A5
0x18001839a  and     esi, 0FFFFFFFEh
0x18001839d  mov     [rsp+1D0h+var_1A0], esi
0x1800183a1  mov     [rbp+0D0h+var_118], r12
0x1800183a5  mov     ebx, r12d
0x1800183a8  test    cl, cl
0x1800183aa  cmovz   ebx, eax
0x1800183ad  lea     rcx, [rsp+1D0h+var_190]
0x1800183b2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800183b7  nop
0x1800183b8  lea     rcx, [rsp+1D0h+ppv]
0x1800183bd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800183c2  nop
0x1800183c3  lea     rcx, [rsp+1D0h+var_180]
0x1800183c8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800183cd  nop
0x1800183ce  lea     rcx, [rsp+1D0h+var_188]
0x1800183d3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800183d8  test    ebx, ebx
0x1800183da  js      loc_180018846
0x1800183e0  mov     eax, ebx
0x1800183e2  jmp     loc_180018848
0x1800183e7  mov     [rsp+1D0h+bIgnoreCase], r12d; bIgnoreCase
0x1800183ec  mov     r9d, edi; cchCount2
0x1800183ef  lea     r8, aCommandLaunchs; "command:LaunchSystemStorage"
0x1800183f6  mov     edx, edi; cchCount1
0x1800183f8  mov     rcx, rbx; lpString1
0x1800183fb  call    cs:__imp_CompareStringOrdinal
0x180018401  cmp     eax, 2
0x180018404  jnz     loc_180018522
0x18001840a  mov     [rsp+1D0h+ppv], r12
0x18001840f  movaps  xmm0, xmmword ptr cs:aPageSettingspa_1; "page=SettingsPageStorageSenseStorageOve"...
0x180018416  movups  [rbp+0D0h+var_110], xmm0
0x18001841a  movaps  xmm1, xmmword ptr cs:aPageSettingspa_1+10h; "tingsPageStorageSenseStorageOverview&ta"...
0x180018421  movups  [rbp+0D0h+var_100], xmm1
0x180018425  movaps  xmm0, xmmword ptr cs:aPageSettingspa_1+20h; "eStorageSenseStorageOverview&target=Sys"...
0x18001842c  movups  [rbp+0D0h+var_F0], xmm0
0x180018430  movaps  xmm1, xmmword ptr cs:aPageSettingspa_1+30h; "SenseStorageOverview&target=SystemSetti"...
0x180018437  movups  [rbp+0D0h+var_E0], xmm1
0x18001843b  movaps  xmm0, xmmword ptr cs:aPageSettingspa_1+40h; "rageOverview&target=SystemSettings_Stor"...
0x180018442  movups  [rbp+0D0h+var_D0], xmm0
0x180018446  movaps  xmm1, xmmword ptr cs:aPageSettingspa_1+50h; "view&target=SystemSettings_StorageSense"...
0x18001844d  movups  [rbp+0D0h+var_C0], xmm1
0x180018451  movaps  xmm0, xmmword ptr cs:aPageSettingspa_1+60h; "get=SystemSettings_StorageSense_SystemD"...
0x180018458  movups  [rbp+0D0h+var_B0], xmm0
0x18001845c  movaps  xmm1, xmmword ptr cs:aPageSettingspa_1+70h; "emSettings_StorageSense_SystemDrive&inv"...
0x180018463  movups  [rbp+0D0h+var_A0], xmm1
0x180018467  movaps  xmm0, xmmword ptr cs:aPageSettingspa_1+80h; "gs_StorageSense_SystemDrive&invoke=true"
0x18001846e  movups  [rbp+0D0h+var_90], xmm0
0x180018472  movaps  xmm1, xmmword ptr cs:aPageSettingspa_1+90h; "geSense_SystemDrive&invoke=true"
0x180018479  movups  [rbp+0D0h+var_80], xmm1
0x18001847d  movaps  xmm0, xmmword ptr cs:aPageSettingspa_1+0A0h; "SystemDrive&invoke=true"
0x180018484  movups  [rbp+0D0h+var_70], xmm0
0x180018488  movaps  xmm1, xmmword ptr cs:aPageSettingspa_1+0B0h; "ive&invoke=true"
0x18001848f  movups  [rbp+0D0h+var_60], xmm1
0x180018493  movaps  xmm0, xmmword ptr cs:aPageSettingspa_1+0C0h; "ke=true"
0x18001849a  movups  [rbp+0D0h+var_50], xmm0
0x1800184a1  mov     [rsp+1D0h+var_190], r12d
0x1800184a6  lea     rcx, [rsp+1D0h+ppv]
0x1800184ab  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800184b0  lea     rax, [rsp+1D0h+ppv]
0x1800184b5  mov     qword ptr [rsp+1D0h+bIgnoreCase], rax; ppv
0x1800184ba  lea     r9, _GUID_2e941141_7f97_4756_ba1d_9decde894a3d; riid
0x1800184c1  xor     edx, edx; pUnkOuter
0x1800184c3  lea     r8d, [rdx+4]; dwClsContext
0x1800184c7  lea     rcx, CLSID_ApplicationActivationManager; rclsid
0x1800184ce  call    cs:__imp_CoCreateInstance
0x1800184d4  test    eax, eax
0x1800184d6  js      short loc_180018513
0x1800184d8  xor     edx, edx; lpvReserved
0x1800184da  mov     rcx, [rsp+1D0h+ppv]; pUnk
0x1800184df  call    cs:__imp_CoAllowSetForegroundWindow
0x1800184e5  test    eax, eax
0x1800184e7  js      short loc_180018513
0x1800184e9  mov     rcx, [rsp+1D0h+ppv]
0x1800184ee  mov     rax, [rcx]
0x1800184f1  lea     rdx, [rsp+1D0h+var_190]
0x1800184f6  mov     qword ptr [rsp+1D0h+bIgnoreCase], rdx
0x1800184fb  xor     r9d, r9d
0x1800184fe  lea     r8, [rbp+0D0h+var_110]
0x180018502  lea     rdx, aWindowsImmersi; "windows.immersivecontrolpanel_cw5n1h2tx"...
0x180018509  mov     rax, [rax+18h]
0x18001850d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018512  nop
0x180018513  lea     rcx, [rsp+1D0h+ppv]
0x180018518  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001851d  jmp     loc_180018846
0x180018522  mov     [rsp+1D0h+bIgnoreCase], r12d; int
0x180018527  mov     r9d, edi; cchCount2
0x18001852a  lea     r8, aCommandCloudag_0; "command:CloudAgeOut_Enable"
0x180018531  mov     edx, edi; cchCount1
0x180018533  mov     rcx, rbx; lpString1
0x180018536  call    cs:__imp_CompareStringOrdinal
0x18001853c  cmp     eax, 2
0x18001853f  jnz     loc_1800185CA
0x180018545  mov     [rsp+1D0h+var_190], r12d
0x18001854a  lea     r9, [rsp+1D0h+var_190]; unsigned int *
0x18001854f  lea     r8, aCloudconsentto; "CloudConsentToastCount"
0x180018556  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001855d  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x180018564  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180018569  mov     r9d, 3; unsigned int
0x18001856f  lea     r8, aCloudconsentto; "CloudConsentToastCount"
0x180018576  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001857d  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180018582  mov     r9d, 1; unsigned int
0x180018588  lea     r8, aCloudfilepolic; "CloudfilePolicyConsent"
0x18001858f  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180018596  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18001859b  call    ??$QueueTask@V_lambda_7dc4ac9b600921e8e3fa6fc24b24baf0_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@$$QEAV_lambda_7dc4ac9b600921e8e3fa6fc24b24baf0_@@@Z; Windows::Internal::ComTaskPool::QueueTask<_lambda_7dc4ac9b600921e8e3fa6fc24b24baf0_>(Windows::Internal::TaskApartment,_lambda_7dc4ac9b600921e8e3fa6fc24b24baf0_ &&)
0x1800185a0  mov     ebx, eax
0x1800185a2  test    eax, eax
0x1800185a4  jns     loc_180018846
0x1800185aa  mov     rcx, [rbp+0D8h]; this
0x1800185b1  mov     r9d, eax; char *
0x1800185b4  lea     r8, aOnecoreDrivers_16; "onecore\\drivers\\storage\\storsvc\\ser"...
0x1800185bb  mov     edx, 790h; void *
0x1800185c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800185c5  jmp     loc_1800183E0
0x1800185ca  mov     [rsp+1D0h+bIgnoreCase], r12d; bIgnoreCase
0x1800185cf  mov     r9d, edi; cchCount2
0x1800185d2  lea     r8, aCommandCloudag; "command:CloudAgeOut_Dismiss"
0x1800185d9  mov     edx, edi; cchCount1
0x1800185db  mov     rcx, rbx; lpString1
0x1800185de  call    cs:__imp_CompareStringOrdinal
0x1800185e4  cmp     eax, 2
0x1800185e7  jnz     short loc_18001861F
0x1800185e9  mov     [rsp+1D0h+var_190], r12d
0x1800185ee  lea     r9, [rsp+1D0h+var_190]; unsigned int *
0x1800185f3  lea     r8, aCloudconsentto; "CloudConsentToastCount"
0x1800185fa  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180018601  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x180018608  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18001860d  mov     r9d, 3
0x180018613  lea     r8, aCloudconsentto; "CloudConsentToastCount"
0x18001861a  jmp     loc_18001822C
0x18001861f  mov     [rsp+1D0h+bIgnoreCase], r12d; bIgnoreCase
0x180018624  mov     r9d, edi; cchCount2
0x180018627  lea     r8, aCommandBackupE; "command:Backup_Enable"
0x18001862e  mov     edx, edi; cchCount1
0x180018630  mov     rcx, rbx; lpString1
0x180018633  call    cs:__imp_CompareStringOrdinal
0x180018639  cmp     eax, 2
0x18001863c  jnz     loc_1800187EA
0x180018642  mov     [rsp+1D0h+var_178], r12
0x180018647  mov     [rsp+1D0h+ppv], r12
0x18001864c  mov     [rsp+1D0h+var_188], r12
0x180018651  mov     [rsp+1D0h+var_180], r12
0x180018656  mov     [rsp+1D0h+var_158], r12
0x18001865b  lea     r9d, [rax+14h]; unsigned int
0x18001865f  lea     r8d, [rax+15h]; unsigned int
0x180018663  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x18001866a  lea     rcx, [rsp+1D0h+var_170]; hstringHeader
0x18001866f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180018674  nop
0x180018675  mov     esi, 8
0x18001867a  mov     [rsp+1D0h+var_1A0], esi
0x18001867e  lea     rdx, [rsp+1D0h+ppv]
0x180018683  mov     rcx, [rsp+1D0h+var_158]
0x180018688  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x18001868d  test    eax, eax
0x18001868f  js      loc_180018755
0x180018695  mov     rdi, [rsp+1D0h+ppv]
0x18001869a  mov     rax, [rdi]
0x18001869d  mov     rbx, [rax+30h]
  ... truncated ...
```
