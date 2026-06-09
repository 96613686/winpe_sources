# UpdatePolicyReader::IsPolicyEnabledInSkuMdmAllowList(tagUpdatePolicy)

- ea: `0x18001a5ac`
- end: `0x18001b737`
- name: `?IsPolicyEnabledInSkuMdmAllowList@UpdatePolicyReader@@CAHW4tagUpdatePolicy@@@Z`
- size: `4491`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001a320`

## callees

- `0x18000e7e4`
- `0x18000fcc4`
- `0x180010260`
- `0x18001a5ac`
- `0x18001ed68`
- `0x180025e5c`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001a61e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001a61e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001a5f6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001a5f6`

## string_xrefs

- `0x18001b51a`: `PauseQualityUpdatesStartTime`
- `0x18001b5f2`: `PauseFeatureUpdatesStartTime`
- `0x18001b586`: `PauseQualityUpdatesEndTime`
- `0x18001b65e`: `PauseFeatureUpdatesEndTime`
- `0x18001a639`: `AlwaysAutoRebootAtScheduledTimeMinutes`
- `0x18001a860`: `DisableWindowsUpdateAccess`
- `0x18001a8cd`: `RequireUpdateApproval`
- `0x18001abc4`: `AllowResumeUpdateAfterDevicePoweredOn`
- `0x18001a93a`: `AllowAutoUpdate`
- `0x18001ac30`: `DisableAllUnmanagedUpdateServicesWhenWsus`
- `0x18001ac9e`: `AllowUpdateService`
- `0x18001aa7e`: `ScheduledInstallDay`
- `0x18001aaeb`: `ScheduledInstallTime`
- `0x18001ab57`: `UpdateServiceUrl`
- `0x18001ad0b`: `AllowNonMicrosoftSignedUpdate`
- `0x18001a9a7`: `IgnoreMOUpdateDownloadLimit`
- `0x18001af28`: `AllowMUUpdateService`
- `0x18001af95`: `UpdateServiceUrlAlternate`
- `0x18001b06e`: `SetProxyBehaviorForUpdateDetection`
- `0x18001b0db`: `DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection`
- `0x18001b2fb`: `ScheduledInstallEveryWeek`
- `0x18001b366`: `ScheduledInstallFirstWeek`
- `0x18001b3d6`: `ScheduledInstallSecondWeek`
- `0x18001b442`: `ScheduledInstallThirdWeek`
- `0x18001b4ae`: `ScheduledInstallFourthWeek`
- `0x18001b14b`: `SetPolicyDrivenUpdateSourceForFeatureUpdates`
- `0x18001b1b7`: `SetPolicyDrivenUpdateSourceForQualityUpdates`
- `0x18001b227`: `SetPolicyDrivenUpdateSourceForDriverUpdates`
- `0x18001b292`: `SetPolicyDrivenUpdateSourceForOtherUpdates`
- `0x18001a617`: `Populating UpdatePolicy AllowList`

## pseudocode

```c
__int64 __fastcall UpdatePolicyReader::IsPolicyEnabledInSkuMdmAllowList(int a1)
{
  unsigned __int8 v2; // bl
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rax
  __int64 v43; // rbx
  _BYTE v45[12]; // [rsp+28h] [rbp-29h] BYREF
  int v46; // [rsp+34h] [rbp-1Dh]
  __int128 v47; // [rsp+40h] [rbp-11h] BYREF
  __int128 v48; // [rsp+50h] [rbp-1h]
  char v49; // [rsp+60h] [rbp+Fh]
  int v50; // [rsp+61h] [rbp+10h]
  __int16 v51; // [rsp+65h] [rbp+14h]
  char v52; // [rsp+67h] [rbp+16h]
  int v53; // [rsp+68h] [rbp+17h] BYREF
  _QWORD v54[4]; // [rsp+70h] [rbp+1Fh] BYREF
  char v55; // [rsp+90h] [rbp+3Fh]

  v2 = 1;
  if ( !(_BYTE)word_18004EF80 )
  {
    if ( _InterlockedCompareExchange(&dword_18004EDEC, 1, 0) != 1 )
      goto LABEL_7;
    while ( _InterlockedCompareExchange(&dword_18004EDEC, 1, 0) == 1 )
      Sleep(0x64u);
    if ( !(_BYTE)word_18004EF80 )
    {
LABEL_7:
      OutputDebugStringW(L"Populating UpdatePolicy AllowList");
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"AlwaysAutoRebootAtScheduledTimeMinutes", 0x26u);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 1;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v3,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"NoAutoRebootWithLoggedOnUsers", 0x1Du);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 2;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v4,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"AUOptions", 9u);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 3;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v5,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"DetectionFrequency", 0x12u);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 4;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v6,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"TargetGroup", 0xBu);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 5;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v7,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"DisableWindowsUpdateAccess", 0x1Au);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 37;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v8,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"RequireUpdateApproval", 0x15u);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 6;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v9,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"AllowAutoUpdate", 0xFu);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 7;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v10,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"IgnoreMOUpdateDownloadLimit", 0x1Bu);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 8;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v11,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"IgnoreMOAppDownloadLimit", 0x18u);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 9;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v12,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"ScheduledInstallDay", 0x13u);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 10;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v13,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"ScheduledInstallTime", 0x14u);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 11;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v14,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"UpdateServiceUrl", 0x10u);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 12;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v15,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"AllowResumeUpdateAfterDevicePoweredOn", 0x25u);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 13;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v16,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"DisableAllUnmanagedUpdateServicesWhenWsus", 0x29u);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 14;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v17,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"AllowUpdateService", 0x12u);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 15;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v18,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"AllowNonMicrosoftSignedUpdate", 0x1Du);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 16;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v19,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"FlightEnabled", 0xDu);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 18;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v20,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"SetActiveHours", 0xEu);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 22;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v21,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"ActiveHoursStart", 0x10u);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 23;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v22,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"ActiveHoursEnd", 0xEu);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 24;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v23,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"AllowMUUpdateService", 0x14u);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 25;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v24,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"UpdateServiceUrlAlternate", 0x19u);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 26;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v25,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"FillEmptyContentUrls", 0x14u);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 27;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v26,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"SetProxyBehaviorForUpdateDetection", 0x22u);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 38;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v27,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        &v47,
        L"DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection",
        0x36u);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 39;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v28,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"SetPolicyDrivenUpdateSourceForFeatureUpdates", 0x2Cu);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 40;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v29,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"SetPolicyDrivenUpdateSourceForQualityUpdates", 0x2Cu);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 41;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v30,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"SetPolicyDrivenUpdateSourceForDriverUpdates", 0x2Bu);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 42;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v31,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"SetPolicyDrivenUpdateSourceForOtherUpdates", 0x2Au);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 43;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v32,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"ScheduledInstallEveryWeek", 0x19u);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 28;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v33,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"ScheduledInstallFirstWeek", 0x19u);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 29;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v34,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"ScheduledInstallSecondWeek", 0x1Au);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 30;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v35,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"ScheduledInstallThirdWeek", 0x19u);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 31;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v36,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"ScheduledInstallFourthWeek", 0x1Au);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 32;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v37,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"PauseQualityUpdatesStartTime", 0x1Cu);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 33;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v38,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"PauseQualityUpdatesEndTime", 0x1Au);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 34;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v39,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"PauseFeatureUpdatesStartTime", 0x1Cu);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 35;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v40,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"PauseFeatureUpdatesEndTime", 0x1Au);
      v49 = 1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 36;
      std::wstring::wstring((__int64)v54, (__int64)&v47);
      v55 = v49;
      std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(
        v41,
        (__int64)v45,
        (__int64)&v53);
      std::wstring::~wstring(v54);
      std::wstring::~wstring(&v47);
      PolicyAllowList<enum tagUpdatePolicy>::Populate();
    }
    _InterlockedExchange(&dword_18004EDEC, 0);
  }
  if ( !HIBYTE(word_18004EF80) )
  {
    v42 = *(_QWORD *)(qword_18004EF88 + 8);
    v46 = 0;
    v43 = qword_18004EF88;
    while ( !*(_BYTE *)(v42 + 25) )
    {
      if ( *(_DWORD *)(v42 + 32) >= a1 )
        v43 = v42;
      else
        v42 += 16;
      v42 = *(_QWORD *)v42;
    }
    if ( *(_BYTE *)(v43 + 25) || a1 < *(_DWORD *)(v43 + 32) )
      v43 = qword_18004EF88;
    if ( qword_18004EF88 == v43 )
      return 0;
    else
      return *(unsigned __int8 *)(v43 + 72);
  }
  return v2;
}

```

## disassembly

```asm
0x18001a5ac  mov     rax, rsp
0x18001a5af  mov     [rax+8], rbx
0x18001a5b3  mov     [rax+10h], rsi
0x18001a5b7  mov     [rax+18h], rdi
0x18001a5bb  push    rbp
0x18001a5bc  push    r14
0x18001a5be  push    r15
0x18001a5c0  lea     rbp, [rax-5Fh]
0x18001a5c4  sub     rsp, 90h
0x18001a5cb  mov     edi, ecx
0x18001a5cd  mov     ebx, 1
0x18001a5d2  xor     esi, esi
0x18001a5d4  cmp     byte ptr cs:word_18004EF80, sil
0x18001a5db  jnz     loc_18001B6C7
0x18001a5e1  xor     eax, eax
0x18001a5e3  lock cmpxchg cs:dword_18004EDEC, ebx
0x18001a5eb  cmp     eax, ebx
0x18001a5ed  jnz     short loc_18001A617
0x18001a5ef  jmp     short loc_18001A5FC
0x18001a5f1  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18001a5f6  call    cs:__imp_Sleep
0x18001a5fc  xor     eax, eax
0x18001a5fe  lock cmpxchg cs:dword_18004EDEC, ebx
0x18001a606  cmp     eax, ebx
0x18001a608  jz      short loc_18001A5F1
0x18001a60a  cmp     byte ptr cs:word_18004EF80, sil
0x18001a611  jnz     loc_18001B6BF
0x18001a617  lea     rcx, aPopulatingUpda; "Populating UpdatePolicy AllowList"
0x18001a61e  call    cs:__imp_OutputDebugStringW
0x18001a624  xorps   xmm0, xmm0
0x18001a627  movups  [rbp+57h+var_68], xmm0
0x18001a62b  xorps   xmm1, xmm1
0x18001a62e  movdqu  [rbp+57h+var_58], xmm1
0x18001a633  mov     r8d, 26h ; '&'
0x18001a639  lea     rdx, aAlwaysautorebo_0; "AlwaysAutoRebootAtScheduledTimeMinutes"
0x18001a640  lea     rcx, [rbp+57h+var_68]
0x18001a644  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001a649  mov     [rbp+57h+var_48], bl
0x18001a64c  xor     eax, eax
0x18001a64e  mov     [rbp+57h+var_47], eax
0x18001a651  mov     [rbp+57h+var_43], ax
0x18001a655  mov     [rbp+57h+var_41], al
0x18001a658  mov     [rbp+57h+var_40], ebx
0x18001a65b  lea     rdx, [rbp+57h+var_68]
0x18001a65f  lea     rcx, [rbp+57h+var_38]
0x18001a663  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001a668  mov     al, [rbp+57h+var_48]
0x18001a66b  mov     [rbp+57h+var_18], al
0x18001a66e  lea     r8, [rbp+57h+var_40]
0x18001a672  lea     rdx, [rbp+57h+var_80]
0x18001a676  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@W4tagUpdatePolicy@@UAllowInfo@@U?$less@W4tagUpdatePolicy@@@std@@V?$allocator@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@1@@Z; std::_Tree<std::_Tmap_traits<tagUpdatePolicy,AllowInfo,std::less<tagUpdatePolicy>,std::allocator<std::pair<tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(std::pair<tagUpdatePolicy const,AllowInfo> &&)
0x18001a67b  nop
0x18001a67c  lea     rcx, [rbp+57h+var_38]; void *
0x18001a680  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001a685  nop
0x18001a686  lea     rcx, [rbp+57h+var_68]; void *
0x18001a68a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001a68f  xorps   xmm0, xmm0
0x18001a692  movups  [rbp+57h+var_68], xmm0
0x18001a696  xorps   xmm1, xmm1
0x18001a699  movdqu  [rbp+57h+var_58], xmm1
0x18001a69e  mov     r8d, 1Dh
0x18001a6a4  lea     rdx, aNoautorebootwi; "NoAutoRebootWithLoggedOnUsers"
0x18001a6ab  lea     rcx, [rbp+57h+var_68]
0x18001a6af  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001a6b4  mov     [rbp+57h+var_48], bl
0x18001a6b7  xor     eax, eax
0x18001a6b9  mov     [rbp+57h+var_47], eax
0x18001a6bc  mov     [rbp+57h+var_43], ax
0x18001a6c0  mov     [rbp+57h+var_41], al
0x18001a6c3  mov     [rbp+57h+var_40], 2
0x18001a6ca  lea     rdx, [rbp+57h+var_68]
0x18001a6ce  lea     rcx, [rbp+57h+var_38]
0x18001a6d2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001a6d7  mov     al, [rbp+57h+var_48]
0x18001a6da  mov     [rbp+57h+var_18], al
0x18001a6dd  lea     r8, [rbp+57h+var_40]
0x18001a6e1  lea     rdx, [rbp+57h+var_80]
0x18001a6e5  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@W4tagUpdatePolicy@@UAllowInfo@@U?$less@W4tagUpdatePolicy@@@std@@V?$allocator@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@1@@Z; std::_Tree<std::_Tmap_traits<tagUpdatePolicy,AllowInfo,std::less<tagUpdatePolicy>,std::allocator<std::pair<tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(std::pair<tagUpdatePolicy const,AllowInfo> &&)
0x18001a6ea  nop
0x18001a6eb  lea     rcx, [rbp+57h+var_38]; void *
0x18001a6ef  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001a6f4  nop
0x18001a6f5  lea     rcx, [rbp+57h+var_68]; void *
0x18001a6f9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001a6fe  xorps   xmm0, xmm0
0x18001a701  movups  [rbp+57h+var_68], xmm0
0x18001a705  xorps   xmm1, xmm1
0x18001a708  movdqu  [rbp+57h+var_58], xmm1
0x18001a70d  mov     r14d, 9
0x18001a713  mov     r8d, r14d
0x18001a716  lea     rdx, aAuoptions; "AUOptions"
0x18001a71d  lea     rcx, [rbp+57h+var_68]
0x18001a721  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001a726  mov     [rbp+57h+var_48], bl
0x18001a729  xor     eax, eax
0x18001a72b  mov     [rbp+57h+var_47], eax
0x18001a72e  mov     [rbp+57h+var_43], ax
0x18001a732  mov     [rbp+57h+var_41], al
0x18001a735  mov     [rbp+57h+var_40], 3
0x18001a73c  lea     rdx, [rbp+57h+var_68]
0x18001a740  lea     rcx, [rbp+57h+var_38]
0x18001a744  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001a749  mov     al, [rbp+57h+var_48]
0x18001a74c  mov     [rbp+57h+var_18], al
0x18001a74f  lea     r8, [rbp+57h+var_40]
0x18001a753  lea     rdx, [rbp+57h+var_80]
0x18001a757  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@W4tagUpdatePolicy@@UAllowInfo@@U?$less@W4tagUpdatePolicy@@@std@@V?$allocator@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@1@@Z; std::_Tree<std::_Tmap_traits<tagUpdatePolicy,AllowInfo,std::less<tagUpdatePolicy>,std::allocator<std::pair<tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(std::pair<tagUpdatePolicy const,AllowInfo> &&)
0x18001a75c  nop
0x18001a75d  lea     rcx, [rbp+57h+var_38]; void *
0x18001a761  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001a766  nop
0x18001a767  lea     rcx, [rbp+57h+var_68]; void *
0x18001a76b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001a770  xorps   xmm0, xmm0
0x18001a773  movups  [rbp+57h+var_68], xmm0
0x18001a777  xorps   xmm1, xmm1
0x18001a77a  movdqu  [rbp+57h+var_58], xmm1
0x18001a77f  lea     r8d, [r14+9]
0x18001a783  lea     rdx, aDetectionfrequ_0; "DetectionFrequency"
0x18001a78a  lea     rcx, [rbp+57h+var_68]
0x18001a78e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001a793  mov     [rbp+57h+var_48], bl
0x18001a796  xor     eax, eax
0x18001a798  mov     [rbp+57h+var_47], eax
0x18001a79b  mov     [rbp+57h+var_43], ax
0x18001a79f  mov     [rbp+57h+var_41], al
0x18001a7a2  mov     [rbp+57h+var_40], 4
0x18001a7a9  lea     rdx, [rbp+57h+var_68]
0x18001a7ad  lea     rcx, [rbp+57h+var_38]
0x18001a7b1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001a7b6  mov     al, [rbp+57h+var_48]
0x18001a7b9  mov     [rbp+57h+var_18], al
0x18001a7bc  lea     r8, [rbp+57h+var_40]
0x18001a7c0  lea     rdx, [rbp+57h+var_80]
0x18001a7c4  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@W4tagUpdatePolicy@@UAllowInfo@@U?$less@W4tagUpdatePolicy@@@std@@V?$allocator@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@1@@Z; std::_Tree<std::_Tmap_traits<tagUpdatePolicy,AllowInfo,std::less<tagUpdatePolicy>,std::allocator<std::pair<tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(std::pair<tagUpdatePolicy const,AllowInfo> &&)
0x18001a7c9  nop
0x18001a7ca  lea     rcx, [rbp+57h+var_38]; void *
0x18001a7ce  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001a7d3  nop
0x18001a7d4  lea     rcx, [rbp+57h+var_68]; void *
0x18001a7d8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001a7dd  xorps   xmm0, xmm0
0x18001a7e0  movups  [rbp+57h+var_68], xmm0
0x18001a7e4  xorps   xmm1, xmm1
0x18001a7e7  movdqu  [rbp+57h+var_58], xmm1
0x18001a7ec  lea     esi, [r14+2]
0x18001a7f0  mov     r8d, esi
0x18001a7f3  lea     rdx, aTargetgroup; "TargetGroup"
0x18001a7fa  lea     rcx, [rbp+57h+var_68]
0x18001a7fe  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001a803  mov     [rbp+57h+var_48], bl
0x18001a806  xor     eax, eax
0x18001a808  mov     [rbp+57h+var_47], eax
0x18001a80b  mov     [rbp+57h+var_43], ax
0x18001a80f  mov     [rbp+57h+var_41], al
0x18001a812  mov     [rbp+57h+var_40], 5
0x18001a819  lea     rdx, [rbp+57h+var_68]
0x18001a81d  lea     rcx, [rbp+57h+var_38]
0x18001a821  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001a826  mov     al, [rbp+57h+var_48]
0x18001a829  mov     [rbp+57h+var_18], al
0x18001a82c  lea     r8, [rbp+57h+var_40]
0x18001a830  lea     rdx, [rbp+57h+var_80]
0x18001a834  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@W4tagUpdatePolicy@@UAllowInfo@@U?$less@W4tagUpdatePolicy@@@std@@V?$allocator@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@1@@Z; std::_Tree<std::_Tmap_traits<tagUpdatePolicy,AllowInfo,std::less<tagUpdatePolicy>,std::allocator<std::pair<tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(std::pair<tagUpdatePolicy const,AllowInfo> &&)
0x18001a839  nop
0x18001a83a  lea     rcx, [rbp+57h+var_38]; void *
0x18001a83e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001a843  nop
0x18001a844  lea     rcx, [rbp+57h+var_68]; void *
0x18001a848  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001a84d  xorps   xmm0, xmm0
0x18001a850  movups  [rbp+57h+var_68], xmm0
0x18001a854  xorps   xmm1, xmm1
0x18001a857  movdqu  [rbp+57h+var_58], xmm1
0x18001a85c  lea     r8d, [r14+11h]
0x18001a860  lea     rdx, aDisablewindows; "DisableWindowsUpdateAccess"
0x18001a867  lea     rcx, [rbp+57h+var_68]
0x18001a86b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001a870  mov     [rbp+57h+var_48], bl
0x18001a873  xor     eax, eax
0x18001a875  mov     [rbp+57h+var_47], eax
0x18001a878  mov     [rbp+57h+var_43], ax
0x18001a87c  mov     [rbp+57h+var_41], al
0x18001a87f  mov     [rbp+57h+var_40], 25h ; '%'
0x18001a886  lea     rdx, [rbp+57h+var_68]
0x18001a88a  lea     rcx, [rbp+57h+var_38]
0x18001a88e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001a893  mov     al, [rbp+57h+var_48]
0x18001a896  mov     [rbp+57h+var_18], al
0x18001a899  lea     r8, [rbp+57h+var_40]
0x18001a89d  lea     rdx, [rbp+57h+var_80]
0x18001a8a1  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@W4tagUpdatePolicy@@UAllowInfo@@U?$less@W4tagUpdatePolicy@@@std@@V?$allocator@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@1@@Z; std::_Tree<std::_Tmap_traits<tagUpdatePolicy,AllowInfo,std::less<tagUpdatePolicy>,std::allocator<std::pair<tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(std::pair<tagUpdatePolicy const,AllowInfo> &&)
0x18001a8a6  nop
0x18001a8a7  lea     rcx, [rbp+57h+var_38]; void *
0x18001a8ab  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001a8b0  nop
0x18001a8b1  lea     rcx, [rbp+57h+var_68]; void *
0x18001a8b5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001a8ba  xorps   xmm0, xmm0
0x18001a8bd  movups  [rbp+57h+var_68], xmm0
0x18001a8c1  xorps   xmm1, xmm1
0x18001a8c4  movdqu  [rbp+57h+var_58], xmm1
0x18001a8c9  lea     r8d, [r14+0Ch]
0x18001a8cd  lea     rdx, aRequireupdatea; "RequireUpdateApproval"
0x18001a8d4  lea     rcx, [rbp+57h+var_68]
0x18001a8d8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001a8dd  mov     [rbp+57h+var_48], bl
0x18001a8e0  xor     eax, eax
0x18001a8e2  mov     [rbp+57h+var_47], eax
0x18001a8e5  mov     [rbp+57h+var_43], ax
0x18001a8e9  mov     [rbp+57h+var_41], al
0x18001a8ec  mov     [rbp+57h+var_40], 6
0x18001a8f3  lea     rdx, [rbp+57h+var_68]
0x18001a8f7  lea     rcx, [rbp+57h+var_38]
0x18001a8fb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001a900  mov     al, [rbp+57h+var_48]
0x18001a903  mov     [rbp+57h+var_18], al
0x18001a906  lea     r8, [rbp+57h+var_40]
0x18001a90a  lea     rdx, [rbp+57h+var_80]
0x18001a90e  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@W4tagUpdatePolicy@@UAllowInfo@@U?$less@W4tagUpdatePolicy@@@std@@V?$allocator@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@1@@Z; std::_Tree<std::_Tmap_traits<tagUpdatePolicy,AllowInfo,std::less<tagUpdatePolicy>,std::allocator<std::pair<tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(std::pair<tagUpdatePolicy const,AllowInfo> &&)
0x18001a913  nop
0x18001a914  lea     rcx, [rbp+57h+var_38]; void *
0x18001a918  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001a91d  nop
0x18001a91e  lea     rcx, [rbp+57h+var_68]; void *
0x18001a922  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001a927  xorps   xmm0, xmm0
0x18001a92a  movups  [rbp+57h+var_68], xmm0
0x18001a92e  xorps   xmm1, xmm1
0x18001a931  movdqu  [rbp+57h+var_58], xmm1
0x18001a936  lea     r8d, [r14+6]
0x18001a93a  lea     rdx, aAllowautoupdat; "AllowAutoUpdate"
0x18001a941  lea     rcx, [rbp+57h+var_68]
0x18001a945  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001a94a  mov     [rbp+57h+var_48], bl
0x18001a94d  xor     eax, eax
0x18001a94f  mov     [rbp+57h+var_47], eax
0x18001a952  mov     [rbp+57h+var_43], ax
0x18001a956  mov     [rbp+57h+var_41], al
0x18001a959  mov     [rbp+57h+var_40], 7
0x18001a960  lea     rdx, [rbp+57h+var_68]
0x18001a964  lea     rcx, [rbp+57h+var_38]
0x18001a968  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001a96d  mov     al, [rbp+57h+var_48]
0x18001a970  mov     [rbp+57h+var_18], al
0x18001a973  lea     r8, [rbp+57h+var_40]
0x18001a977  lea     rdx, [rbp+57h+var_80]
0x18001a97b  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@W4tagUpdatePolicy@@UAllowInfo@@U?$less@W4tagUpdatePolicy@@@std@@V?$allocator@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@1@@Z; std::_Tree<std::_Tmap_traits<tagUpdatePolicy,AllowInfo,std::less<tagUpdatePolicy>,std::allocator<std::pair<tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(std::pair<tagUpdatePolicy const,AllowInfo> &&)
0x18001a980  nop
0x18001a981  lea     rcx, [rbp+57h+var_38]; void *
0x18001a985  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001a98a  nop
0x18001a98b  lea     rcx, [rbp+57h+var_68]; void *
0x18001a98f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001a994  xorps   xmm0, xmm0
0x18001a997  movups  [rbp+57h+var_68], xmm0
0x18001a99b  xorps   xmm1, xmm1
0x18001a99e  movdqu  [rbp+57h+var_58], xmm1
0x18001a9a3  lea     r8d, [r14+12h]
0x18001a9a7  lea     rdx, aIgnoremoupdate; "IgnoreMOUpdateDownloadLimit"
0x18001a9ae  lea     rcx, [rbp+57h+var_68]
0x18001a9b2  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001a9b7  mov     [rbp+57h+var_48], bl
0x18001a9ba  xor     eax, eax
0x18001a9bc  mov     [rbp+57h+var_47], eax
0x18001a9bf  mov     [rbp+57h+var_43], ax
0x18001a9c3  mov     [rbp+57h+var_41], al
0x18001a9c6  mov     [rbp+57h+var_40], 8
0x18001a9cd  lea     rdx, [rbp+57h+var_68]
0x18001a9d1  lea     rcx, [rbp+57h+var_38]
0x18001a9d5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001a9da  mov     al, [rbp+57h+var_48]
0x18001a9dd  mov     [rbp+57h+var_18], al
0x18001a9e0  lea     r8, [rbp+57h+var_40]
0x18001a9e4  lea     rdx, [rbp+57h+var_80]
0x18001a9e8  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@W4tagUpdatePolicy@@UAllowInfo@@U?$less@W4tagUpdatePolicy@@@std@@V?$allocator@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@1@@Z; std::_Tree<std::_Tmap_traits<tagUpdatePolicy,AllowInfo,std::less<tagUpdatePolicy>,std::allocator<std::pair<tagUpdatePolicy const,AllowInfo>>,0>>::insert<0,0>(std::pair<tagUpdatePolicy const,AllowInfo> &&)
0x18001a9ed  nop
0x18001a9ee  lea     rcx, [rbp+57h+var_38]; void *
0x18001a9f2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001a9f7  nop
0x18001a9f8  lea     rcx, [rbp+57h+var_68]; void *
0x18001a9fc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001aa01  xorps   xmm0, xmm0
0x18001aa04  movups  [rbp+57h+var_68], xmm0
0x18001aa08  xorps   xmm1, xmm1
0x18001aa0b  movdqu  [rbp+57h+var_58], xmm1
0x18001aa10  lea     r8d, [r14+0Fh]
0x18001aa14  lea     rdx, aIgnoremoappdow; "IgnoreMOAppDownloadLimit"
0x18001aa1b  lea     rcx, [rbp+57h+var_68]
0x18001aa1f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001aa24  mov     [rbp+57h+var_48], bl
0x18001aa27  xor     eax, eax
0x18001aa29  mov     [rbp+57h+var_47], eax
0x18001aa2c  mov     [rbp+57h+var_43], ax
0x18001aa30  mov     [rbp+57h+var_41], al
0x18001aa33  mov     [rbp+57h+var_40], r14d
0x18001aa37  lea     rdx, [rbp+57h+var_68]
0x18001aa3b  lea     rcx, [rbp+57h+var_38]
0x18001aa3f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
  ... truncated ...
```
