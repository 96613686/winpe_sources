# CUpdatePolicyReader::ReadUpdatePolicyName(tagUpdatePolicy,wchar_t * *)

- ea: `0x18000cb70`
- end: `0x18000ce3e`
- name: `?ReadUpdatePolicyName@CUpdatePolicyReader@@UEAAJW4tagUpdatePolicy@@PEAPEA_W@Z`
- size: `718`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000ca74`
- `0x18000cb70`

## string_xrefs

- `0x18000cd36`: `PauseQualityUpdatesStartTime`
- `0x18000ce2d`: `PauseFeatureUpdatesStartTime`
- `0x18000cda2`: `PauseQualityUpdatesEndTime`
- `0x18000ce24`: `PauseFeatureUpdatesEndTime`
- `0x18000cbd9`: `AlwaysAutoRebootAtScheduledTimeMinutes`
- `0x18000ce1b`: `DisableWindowsUpdateAccess`
- `0x18000cc2d`: `RequireUpdateApproval`
- `0x18000ccc2`: `AllowResumeUpdateAfterDevicePoweredOn`
- `0x18000cc21`: `AllowAutoUpdate`
- `0x18000ccb6`: `DisableAllUnmanagedUpdateServicesWhenWsus`
- `0x18000ccaa`: `AllowUpdateService`
- `0x18000cc39`: `ScheduledInstallDay`
- `0x18000ccda`: `ScheduledInstallTime`
- `0x18000cc9e`: `AllowNonMicrosoftSignedUpdate`
- `0x18000cc15`: `IgnoreMOUpdateDownloadLimit`
- `0x18000cd96`: `AllowMUUpdateService`
- `0x18000cd8a`: `UpdateServiceUrlAlternate`
- `0x18000ce12`: `SetProxyBehaviorForUpdateDetection`
- `0x18000ce09`: `DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection`
- `0x18000cd72`: `ScheduledInstallEveryWeek`
- `0x18000cd66`: `ScheduledInstallFirstWeek`
- `0x18000cd5a`: `ScheduledInstallSecondWeek`
- `0x18000cd4e`: `ScheduledInstallThirdWeek`
- `0x18000cd42`: `ScheduledInstallFourthWeek`
- `0x18000ce00`: `SetPolicyDrivenUpdateSourceForFeatureUpdates`
- `0x18000cdf7`: `SetPolicyDrivenUpdateSourceForQualityUpdates`
- `0x18000cdee`: `SetPolicyDrivenUpdateSourceForDriverUpdates`
- `0x18000cde5`: `SetPolicyDrivenUpdateSourceForOtherUpdates`

## pseudocode

```c
__int64 __fastcall CUpdatePolicyReader::ReadUpdatePolicyName(CUpdatePolicyReader *a1, int a2, wchar_t **a3)
{
  int v3; // edx
  int v4; // edx
  int v5; // edx
  const wchar_t *v6; // rdx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  int v14; // edx
  int v15; // edx
  int v16; // edx
  int v17; // edx
  int v18; // edx
  int v19; // edx
  int v20; // edx
  int v21; // edx
  int v22; // edx
  int v23; // edx
  int v24; // edx
  int v25; // edx
  int v26; // edx
  int v27; // edx
  int v28; // edx
  int v29; // edx
  int v30; // edx
  int v31; // edx
  int v32; // edx
  int v33; // edx

  if ( a2 > 24 )
  {
    if ( a2 > 34 )
    {
      v26 = a2 - 35;
      if ( !v26 )
      {
        v6 = L"PauseFeatureUpdatesStartTime";
        return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
      }
      v27 = v26 - 1;
      if ( !v27 )
      {
        v6 = L"PauseFeatureUpdatesEndTime";
        return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
      }
      v28 = v27 - 1;
      if ( !v28 )
      {
        v6 = L"DisableWindowsUpdateAccess";
        return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
      }
      v29 = v28 - 1;
      if ( !v29 )
      {
        v6 = L"SetProxyBehaviorForUpdateDetection";
        return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
      }
      v30 = v29 - 1;
      if ( !v30 )
      {
        v6 = L"DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection";
        return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
      }
      v31 = v30 - 1;
      if ( !v31 )
      {
        v6 = L"SetPolicyDrivenUpdateSourceForFeatureUpdates";
        return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
      }
      v32 = v31 - 1;
      if ( !v32 )
      {
        v6 = L"SetPolicyDrivenUpdateSourceForQualityUpdates";
        return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
      }
      v33 = v32 - 1;
      if ( !v33 )
      {
        v6 = L"SetPolicyDrivenUpdateSourceForDriverUpdates";
        return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
      }
      if ( v33 == 1 )
      {
        v6 = L"SetPolicyDrivenUpdateSourceForOtherUpdates";
        return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
      }
    }
    else
    {
      if ( a2 == 34 )
      {
        v6 = L"PauseQualityUpdatesEndTime";
        return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
      }
      v18 = a2 - 25;
      if ( !v18 )
      {
        v6 = L"AllowMUUpdateService";
        return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
      }
      v19 = v18 - 1;
      if ( !v19 )
      {
        v6 = L"UpdateServiceUrlAlternate";
        return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
      }
      v20 = v19 - 1;
      if ( !v20 )
      {
        v6 = L"FillEmptyContentUrls";
        return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
      }
      v21 = v20 - 1;
      if ( !v21 )
      {
        v6 = L"ScheduledInstallEveryWeek";
        return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
      }
      v22 = v21 - 1;
      if ( !v22 )
      {
        v6 = L"ScheduledInstallFirstWeek";
        return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
      }
      v23 = v22 - 1;
      if ( !v23 )
      {
        v6 = L"ScheduledInstallSecondWeek";
        return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
      }
      v24 = v23 - 1;
      if ( !v24 )
      {
        v6 = L"ScheduledInstallThirdWeek";
        return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
      }
      v25 = v24 - 1;
      if ( !v25 )
      {
        v6 = L"ScheduledInstallFourthWeek";
        return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
      }
      if ( v25 == 1 )
      {
        v6 = L"PauseQualityUpdatesStartTime";
        return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
      }
    }
    return 2147942487LL;
  }
  if ( a2 == 24 )
  {
    v6 = L"ActiveHoursEnd";
    return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
  }
  if ( a2 > 10 )
  {
    v10 = a2 - 11;
    if ( !v10 )
    {
      v6 = L"ScheduledInstallTime";
      return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
    }
    v11 = v10 - 1;
    if ( !v11 )
    {
      v6 = L"WUServer";
      return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
    }
    v12 = v11 - 1;
    if ( !v12 )
    {
      v6 = L"AllowResumeUpdateAfterDevicePoweredOn";
      return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
    }
    v13 = v12 - 1;
    if ( !v13 )
    {
      v6 = L"DisableAllUnmanagedUpdateServicesWhenWsus";
      return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
    }
    v14 = v13 - 1;
    if ( !v14 )
    {
      v6 = L"AllowUpdateService";
      return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
    }
    v15 = v14 - 1;
    if ( !v15 )
    {
      v6 = L"AllowNonMicrosoftSignedUpdate";
      return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
    }
    v16 = v15 - 2;
    if ( !v16 )
    {
      v6 = L"FlightEnabled";
      return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
    }
    v17 = v16 - 4;
    if ( !v17 )
    {
      v6 = L"SetActiveHours";
      return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
    }
    if ( v17 == 1 )
    {
      v6 = L"ActiveHoursStart";
      return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
    }
    return 2147942487LL;
  }
  if ( a2 == 10 )
  {
    v6 = L"ScheduledInstallDay";
    return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
  }
  if ( a2 > 5 )
  {
    v7 = a2 - 6;
    if ( !v7 )
    {
      v6 = L"RequireUpdateApproval";
      return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
    }
    v8 = v7 - 1;
    if ( !v8 )
    {
      v6 = L"AllowAutoUpdate";
      return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
    }
    v9 = v8 - 1;
    if ( !v9 )
    {
      v6 = L"IgnoreMOUpdateDownloadLimit";
      return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
    }
    if ( v9 == 1 )
    {
      v6 = L"IgnoreMOAppDownloadLimit";
      return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
    }
    return 2147942487LL;
  }
  if ( a2 == 5 )
  {
    v6 = L"TargetGroup";
    return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
  }
  if ( !a2 )
    goto LABEL_14;
  v3 = a2 - 1;
  if ( !v3 )
  {
    v6 = L"AlwaysAutoRebootAtScheduledTimeMinutes";
    return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
  }
  v4 = v3 - 1;
  if ( !v4 )
  {
LABEL_14:
    v6 = L"NoAutoRebootWithLoggedOnUsers";
    return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v6 = L"AUOptions";
    return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
  }
  if ( v5 != 1 )
    return 2147942487LL;
  v6 = L"DetectionFrequency";
  return CUpdatePolicyReader::CopyPolicyString(a1, v6, a3);
}

```

## disassembly

```asm
0x18000cb70  sub     rsp, 28h
0x18000cb74  cmp     edx, 18h
0x18000cb77  jg      loc_18000CCF2
0x18000cb7d  jz      loc_18000CCE6
0x18000cb83  cmp     edx, 0Ah
0x18000cb86  jg      loc_18000CC45
0x18000cb8c  jz      loc_18000CC39
0x18000cb92  cmp     edx, 5
0x18000cb95  jg      short loc_18000CBF1
0x18000cb97  jz      short loc_18000CBE5
0x18000cb99  test    edx, edx
0x18000cb9b  jz      short loc_18000CBCD
0x18000cb9d  sub     edx, 1
0x18000cba0  jz      short loc_18000CBD9
0x18000cba2  sub     edx, 1
0x18000cba5  jz      short loc_18000CBCD
0x18000cba7  sub     edx, 1
0x18000cbaa  jz      short loc_18000CBC1
0x18000cbac  cmp     edx, 1
0x18000cbaf  jnz     loc_18000CDDB
0x18000cbb5  lea     rdx, aDetectionfrequ_0; "DetectionFrequency"
0x18000cbbc  jmp     loc_18000CE34
0x18000cbc1  lea     rdx, aAuoptions; "AUOptions"
0x18000cbc8  jmp     loc_18000CE34
0x18000cbcd  lea     rdx, aNoautorebootwi; "NoAutoRebootWithLoggedOnUsers"
0x18000cbd4  jmp     loc_18000CE34
0x18000cbd9  lea     rdx, aAlwaysautorebo_0; "AlwaysAutoRebootAtScheduledTimeMinutes"
0x18000cbe0  jmp     loc_18000CE34
0x18000cbe5  lea     rdx, aTargetgroup; "TargetGroup"
0x18000cbec  jmp     loc_18000CE34
0x18000cbf1  sub     edx, 6
0x18000cbf4  jz      short loc_18000CC2D
0x18000cbf6  sub     edx, 1
0x18000cbf9  jz      short loc_18000CC21
0x18000cbfb  sub     edx, 1
0x18000cbfe  jz      short loc_18000CC15
0x18000cc00  cmp     edx, 1
0x18000cc03  jnz     loc_18000CDDB
0x18000cc09  lea     rdx, aIgnoremoappdow; "IgnoreMOAppDownloadLimit"
0x18000cc10  jmp     loc_18000CE34
0x18000cc15  lea     rdx, aIgnoremoupdate; "IgnoreMOUpdateDownloadLimit"
0x18000cc1c  jmp     loc_18000CE34
0x18000cc21  lea     rdx, aAllowautoupdat; "AllowAutoUpdate"
0x18000cc28  jmp     loc_18000CE34
0x18000cc2d  lea     rdx, aRequireupdatea; "RequireUpdateApproval"
0x18000cc34  jmp     loc_18000CE34
0x18000cc39  lea     rdx, aScheduledinsta_5; "ScheduledInstallDay"
0x18000cc40  jmp     loc_18000CE34
0x18000cc45  sub     edx, 0Bh
0x18000cc48  jz      loc_18000CCDA
0x18000cc4e  sub     edx, 1
0x18000cc51  jz      short loc_18000CCCE
0x18000cc53  sub     edx, 1
0x18000cc56  jz      short loc_18000CCC2
0x18000cc58  sub     edx, 1
0x18000cc5b  jz      short loc_18000CCB6
0x18000cc5d  sub     edx, 1
0x18000cc60  jz      short loc_18000CCAA
0x18000cc62  sub     edx, 1
0x18000cc65  jz      short loc_18000CC9E
0x18000cc67  sub     edx, 2
0x18000cc6a  jz      short loc_18000CC92
0x18000cc6c  sub     edx, 4
0x18000cc6f  jz      short loc_18000CC86
0x18000cc71  cmp     edx, 1
0x18000cc74  jnz     loc_18000CDDB
0x18000cc7a  lea     rdx, aActivehourssta; "ActiveHoursStart"
0x18000cc81  jmp     loc_18000CE34
0x18000cc86  lea     rdx, aSetactivehours_0; "SetActiveHours"
0x18000cc8d  jmp     loc_18000CE34
0x18000cc92  lea     rdx, aFlightenabled; "FlightEnabled"
0x18000cc99  jmp     loc_18000CE34
0x18000cc9e  lea     rdx, aAllownonmicros; "AllowNonMicrosoftSignedUpdate"
0x18000cca5  jmp     loc_18000CE34
0x18000ccaa  lea     rdx, aAllowupdateser; "AllowUpdateService"
0x18000ccb1  jmp     loc_18000CE34
0x18000ccb6  lea     rdx, aDisableallunma; "DisableAllUnmanagedUpdateServicesWhenWs"...
0x18000ccbd  jmp     loc_18000CE34
0x18000ccc2  lea     rdx, aAllowresumeupd; "AllowResumeUpdateAfterDevicePoweredOn"
0x18000ccc9  jmp     loc_18000CE34
0x18000ccce  lea     rdx, aWuserver; "WUServer"
0x18000ccd5  jmp     loc_18000CE34
0x18000ccda  lea     rdx, aScheduledinsta_2; "ScheduledInstallTime"
0x18000cce1  jmp     loc_18000CE34
0x18000cce6  lea     rdx, aActivehoursend; "ActiveHoursEnd"
0x18000cced  jmp     loc_18000CE34
0x18000ccf2  cmp     edx, 22h ; '"'
0x18000ccf5  jg      loc_18000CDAE
0x18000ccfb  jz      loc_18000CDA2
0x18000cd01  sub     edx, 19h
0x18000cd04  jz      loc_18000CD96
0x18000cd0a  sub     edx, 1
0x18000cd0d  jz      short loc_18000CD8A
0x18000cd0f  sub     edx, 1
0x18000cd12  jz      short loc_18000CD7E
0x18000cd14  sub     edx, 1
0x18000cd17  jz      short loc_18000CD72
0x18000cd19  sub     edx, 1
0x18000cd1c  jz      short loc_18000CD66
0x18000cd1e  sub     edx, 1
0x18000cd21  jz      short loc_18000CD5A
0x18000cd23  sub     edx, 1
0x18000cd26  jz      short loc_18000CD4E
0x18000cd28  sub     edx, 1
0x18000cd2b  jz      short loc_18000CD42
0x18000cd2d  cmp     edx, 1
0x18000cd30  jnz     loc_18000CDDB
0x18000cd36  lea     rdx, aPausequalityup_1; "PauseQualityUpdatesStartTime"
0x18000cd3d  jmp     loc_18000CE34
0x18000cd42  lea     rdx, aScheduledinsta; "ScheduledInstallFourthWeek"
0x18000cd49  jmp     loc_18000CE34
0x18000cd4e  lea     rdx, aScheduledinsta_3; "ScheduledInstallThirdWeek"
0x18000cd55  jmp     loc_18000CE34
0x18000cd5a  lea     rdx, aScheduledinsta_1; "ScheduledInstallSecondWeek"
0x18000cd61  jmp     loc_18000CE34
0x18000cd66  lea     rdx, aScheduledinsta_0; "ScheduledInstallFirstWeek"
0x18000cd6d  jmp     loc_18000CE34
0x18000cd72  lea     rdx, aScheduledinsta_4; "ScheduledInstallEveryWeek"
0x18000cd79  jmp     loc_18000CE34
0x18000cd7e  lea     rdx, aFillemptyconte; "FillEmptyContentUrls"
0x18000cd85  jmp     loc_18000CE34
0x18000cd8a  lea     rdx, aUpdateserviceu; "UpdateServiceUrlAlternate"
0x18000cd91  jmp     loc_18000CE34
0x18000cd96  lea     rdx, aAllowmuupdates; "AllowMUUpdateService"
0x18000cd9d  jmp     loc_18000CE34
0x18000cda2  lea     rdx, aPausequalityup_0; "PauseQualityUpdatesEndTime"
0x18000cda9  jmp     loc_18000CE34
0x18000cdae  sub     edx, 23h ; '#'
0x18000cdb1  jz      short loc_18000CE2D
0x18000cdb3  sub     edx, 1
0x18000cdb6  jz      short loc_18000CE24
0x18000cdb8  sub     edx, 1
0x18000cdbb  jz      short loc_18000CE1B
0x18000cdbd  sub     edx, 1
0x18000cdc0  jz      short loc_18000CE12
0x18000cdc2  sub     edx, 1
0x18000cdc5  jz      short loc_18000CE09
0x18000cdc7  sub     edx, 1
0x18000cdca  jz      short loc_18000CE00
0x18000cdcc  sub     edx, 1
0x18000cdcf  jz      short loc_18000CDF7
0x18000cdd1  sub     edx, 1
0x18000cdd4  jz      short loc_18000CDEE
0x18000cdd6  cmp     edx, 1
0x18000cdd9  jz      short loc_18000CDE5
0x18000cddb  mov     eax, 80070057h
0x18000cde0  add     rsp, 28h
0x18000cde4  retn
0x18000cde5  lea     rdx, aSetpolicydrive; "SetPolicyDrivenUpdateSourceForOtherUpda"...
0x18000cdec  jmp     short loc_18000CE34
0x18000cdee  lea     rdx, aSetpolicydrive_0; "SetPolicyDrivenUpdateSourceForDriverUpd"...
0x18000cdf5  jmp     short loc_18000CE34
0x18000cdf7  lea     rdx, aSetpolicydrive_2; "SetPolicyDrivenUpdateSourceForQualityUp"...
0x18000cdfe  jmp     short loc_18000CE34
0x18000ce00  lea     rdx, aSetpolicydrive_1; "SetPolicyDrivenUpdateSourceForFeatureUp"...
0x18000ce07  jmp     short loc_18000CE34
0x18000ce09  lea     rdx, aDonotenforceen; "DoNotEnforceEnterpriseTLSCertPinningFor"...
0x18000ce10  jmp     short loc_18000CE34
0x18000ce12  lea     rdx, aSetproxybehavi; "SetProxyBehaviorForUpdateDetection"
0x18000ce19  jmp     short loc_18000CE34
0x18000ce1b  lea     rdx, aDisablewindows; "DisableWindowsUpdateAccess"
0x18000ce22  jmp     short loc_18000CE34
0x18000ce24  lea     rdx, aPausefeatureup; "PauseFeatureUpdatesEndTime"
0x18000ce2b  jmp     short loc_18000CE34
0x18000ce2d  lea     rdx, aPausefeatureup_0; "PauseFeatureUpdatesStartTime"
0x18000ce34  call    ?CopyPolicyString@CUpdatePolicyReader@@AEAAJPEB_WPEAPEA_W@Z; CUpdatePolicyReader::CopyPolicyString(wchar_t const *,wchar_t * *)
0x18000ce39  add     rsp, 28h
0x18000ce3d  retn
```
