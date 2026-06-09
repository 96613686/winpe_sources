# UpdatePolicyReader::GetUpdatePolicyName(tagUpdatePolicy,wchar_t const * *)

- ea: `0x18001b740`
- end: `0x18001ba18`
- name: `?GetUpdatePolicyName@UpdatePolicyReader@@SAJW4tagUpdatePolicy@@PEAPEB_W@Z`
- size: `728`
- prototype: `__int64 __fastcall(int, const wchar_t **)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18001b740`

## string_xrefs

- `0x18001b915`: `PauseQualityUpdatesStartTime`
- `0x18001ba0a`: `PauseFeatureUpdatesStartTime`
- `0x18001b981`: `PauseQualityUpdatesEndTime`
- `0x18001ba01`: `PauseFeatureUpdatesEndTime`
- `0x18001b7b8`: `AlwaysAutoRebootAtScheduledTimeMinutes`
- `0x18001b9f8`: `DisableWindowsUpdateAccess`
- `0x18001b80c`: `RequireUpdateApproval`
- `0x18001b8a1`: `AllowResumeUpdateAfterDevicePoweredOn`
- `0x18001b800`: `AllowAutoUpdate`
- `0x18001b895`: `DisableAllUnmanagedUpdateServicesWhenWsus`
- `0x18001b889`: `AllowUpdateService`
- `0x18001b818`: `ScheduledInstallDay`
- `0x18001b8b9`: `ScheduledInstallTime`
- `0x18001b87d`: `AllowNonMicrosoftSignedUpdate`
- `0x18001b7f4`: `IgnoreMOUpdateDownloadLimit`
- `0x18001b975`: `AllowMUUpdateService`
- `0x18001b969`: `UpdateServiceUrlAlternate`
- `0x18001b9ef`: `SetProxyBehaviorForUpdateDetection`
- `0x18001b9e6`: `DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection`
- `0x18001b951`: `ScheduledInstallEveryWeek`
- `0x18001b945`: `ScheduledInstallFirstWeek`
- `0x18001b939`: `ScheduledInstallSecondWeek`
- `0x18001b92d`: `ScheduledInstallThirdWeek`
- `0x18001b921`: `ScheduledInstallFourthWeek`
- `0x18001b9dd`: `SetPolicyDrivenUpdateSourceForFeatureUpdates`
- `0x18001b9d4`: `SetPolicyDrivenUpdateSourceForQualityUpdates`
- `0x18001b9cb`: `SetPolicyDrivenUpdateSourceForDriverUpdates`
- `0x18001b9c2`: `SetPolicyDrivenUpdateSourceForOtherUpdates`

## pseudocode

```c
__int64 __fastcall UpdatePolicyReader::GetUpdatePolicyName(int a1, const wchar_t **a2)
{
  unsigned int v2; // r8d
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  const wchar_t *v6; // rax
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx

  v2 = 0;
  if ( a2 )
  {
    if ( a1 > 24 )
    {
      if ( a1 > 34 )
      {
        v26 = a1 - 35;
        if ( !v26 )
        {
          v6 = L"PauseFeatureUpdatesStartTime";
          goto LABEL_87;
        }
        v27 = v26 - 1;
        if ( !v27 )
        {
          v6 = L"PauseFeatureUpdatesEndTime";
          goto LABEL_87;
        }
        v28 = v27 - 1;
        if ( !v28 )
        {
          v6 = L"DisableWindowsUpdateAccess";
          goto LABEL_87;
        }
        v29 = v28 - 1;
        if ( !v29 )
        {
          v6 = L"SetProxyBehaviorForUpdateDetection";
          goto LABEL_87;
        }
        v30 = v29 - 1;
        if ( !v30 )
        {
          v6 = L"DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection";
          goto LABEL_87;
        }
        v31 = v30 - 1;
        if ( !v31 )
        {
          v6 = L"SetPolicyDrivenUpdateSourceForFeatureUpdates";
          goto LABEL_87;
        }
        v32 = v31 - 1;
        if ( !v32 )
        {
          v6 = L"SetPolicyDrivenUpdateSourceForQualityUpdates";
          goto LABEL_87;
        }
        v33 = v32 - 1;
        if ( !v33 )
        {
          v6 = L"SetPolicyDrivenUpdateSourceForDriverUpdates";
          goto LABEL_87;
        }
        if ( v33 == 1 )
        {
          v6 = L"SetPolicyDrivenUpdateSourceForOtherUpdates";
          goto LABEL_87;
        }
      }
      else
      {
        if ( a1 == 34 )
        {
          v6 = L"PauseQualityUpdatesEndTime";
          goto LABEL_87;
        }
        v18 = a1 - 25;
        if ( !v18 )
        {
          v6 = L"AllowMUUpdateService";
          goto LABEL_87;
        }
        v19 = v18 - 1;
        if ( !v19 )
        {
          v6 = L"UpdateServiceUrlAlternate";
          goto LABEL_87;
        }
        v20 = v19 - 1;
        if ( !v20 )
        {
          v6 = L"FillEmptyContentUrls";
          goto LABEL_87;
        }
        v21 = v20 - 1;
        if ( !v21 )
        {
          v6 = L"ScheduledInstallEveryWeek";
          goto LABEL_87;
        }
        v22 = v21 - 1;
        if ( !v22 )
        {
          v6 = L"ScheduledInstallFirstWeek";
          goto LABEL_87;
        }
        v23 = v22 - 1;
        if ( !v23 )
        {
          v6 = L"ScheduledInstallSecondWeek";
          goto LABEL_87;
        }
        v24 = v23 - 1;
        if ( !v24 )
        {
          v6 = L"ScheduledInstallThirdWeek";
          goto LABEL_87;
        }
        v25 = v24 - 1;
        if ( !v25 )
        {
          v6 = L"ScheduledInstallFourthWeek";
          goto LABEL_87;
        }
        if ( v25 == 1 )
        {
          v6 = L"PauseQualityUpdatesStartTime";
          goto LABEL_87;
        }
      }
    }
    else
    {
      if ( a1 == 24 )
      {
        v6 = L"ActiveHoursEnd";
        goto LABEL_87;
      }
      if ( a1 > 10 )
      {
        v10 = a1 - 11;
        if ( !v10 )
        {
          v6 = L"ScheduledInstallTime";
          goto LABEL_87;
        }
        v11 = v10 - 1;
        if ( !v11 )
        {
          v6 = L"WUServer";
          goto LABEL_87;
        }
        v12 = v11 - 1;
        if ( !v12 )
        {
          v6 = L"AllowResumeUpdateAfterDevicePoweredOn";
          goto LABEL_87;
        }
        v13 = v12 - 1;
        if ( !v13 )
        {
          v6 = L"DisableAllUnmanagedUpdateServicesWhenWsus";
          goto LABEL_87;
        }
        v14 = v13 - 1;
        if ( !v14 )
        {
          v6 = L"AllowUpdateService";
          goto LABEL_87;
        }
        v15 = v14 - 1;
        if ( !v15 )
        {
          v6 = L"AllowNonMicrosoftSignedUpdate";
          goto LABEL_87;
        }
        v16 = v15 - 2;
        if ( !v16 )
        {
          v6 = L"FlightEnabled";
          goto LABEL_87;
        }
        v17 = v16 - 4;
        if ( !v17 )
        {
          v6 = L"SetActiveHours";
          goto LABEL_87;
        }
        if ( v17 == 1 )
        {
          v6 = L"ActiveHoursStart";
          goto LABEL_87;
        }
      }
      else
      {
        if ( a1 == 10 )
        {
          v6 = L"ScheduledInstallDay";
          goto LABEL_87;
        }
        if ( a1 > 5 )
        {
          v7 = a1 - 6;
          if ( !v7 )
          {
            v6 = L"RequireUpdateApproval";
            goto LABEL_87;
          }
          v8 = v7 - 1;
          if ( !v8 )
          {
            v6 = L"AllowAutoUpdate";
            goto LABEL_87;
          }
          v9 = v8 - 1;
          if ( !v9 )
          {
            v6 = L"IgnoreMOUpdateDownloadLimit";
            goto LABEL_87;
          }
          if ( v9 == 1 )
          {
            v6 = L"IgnoreMOAppDownloadLimit";
            goto LABEL_87;
          }
        }
        else
        {
          if ( a1 == 5 )
          {
            v6 = L"TargetGroup";
            goto LABEL_87;
          }
          if ( !a1 )
            goto LABEL_16;
          v3 = a1 - 1;
          if ( !v3 )
          {
            v6 = L"AlwaysAutoRebootAtScheduledTimeMinutes";
            goto LABEL_87;
          }
          v4 = v3 - 1;
          if ( !v4 )
          {
LABEL_16:
            v6 = L"NoAutoRebootWithLoggedOnUsers";
            goto LABEL_87;
          }
          v5 = v4 - 1;
          if ( !v5 )
          {
            v6 = L"AUOptions";
            goto LABEL_87;
          }
          if ( v5 == 1 )
          {
            v6 = L"DetectionFrequency";
LABEL_87:
            *a2 = v6;
            return v2;
          }
        }
      }
    }
    return (unsigned int)-2147024809;
  }
  return (unsigned int)-2147467261;
}

```

## disassembly

```asm
0x18001b740  xor     r8d, r8d
0x18001b743  test    rdx, rdx
0x18001b746  jnz     short loc_18001B753
0x18001b748  mov     r8d, 80004003h
0x18001b74e  jmp     loc_18001BA14
0x18001b753  cmp     ecx, 18h
0x18001b756  jg      loc_18001B8D1
0x18001b75c  jz      loc_18001B8C5
0x18001b762  cmp     ecx, 0Ah
0x18001b765  jg      loc_18001B824
0x18001b76b  jz      loc_18001B818
0x18001b771  cmp     ecx, 5
0x18001b774  jg      short loc_18001B7D0
0x18001b776  jz      short loc_18001B7C4
0x18001b778  test    ecx, ecx
0x18001b77a  jz      short loc_18001B7AC
0x18001b77c  sub     ecx, 1
0x18001b77f  jz      short loc_18001B7B8
0x18001b781  sub     ecx, 1
0x18001b784  jz      short loc_18001B7AC
0x18001b786  sub     ecx, 1
0x18001b789  jz      short loc_18001B7A0
0x18001b78b  cmp     ecx, 1
0x18001b78e  jnz     loc_18001B9BA
0x18001b794  lea     rax, aDetectionfrequ_0; "DetectionFrequency"
0x18001b79b  jmp     loc_18001BA11
0x18001b7a0  lea     rax, aAuoptions; "AUOptions"
0x18001b7a7  jmp     loc_18001BA11
0x18001b7ac  lea     rax, aNoautorebootwi; "NoAutoRebootWithLoggedOnUsers"
0x18001b7b3  jmp     loc_18001BA11
0x18001b7b8  lea     rax, aAlwaysautorebo_0; "AlwaysAutoRebootAtScheduledTimeMinutes"
0x18001b7bf  jmp     loc_18001BA11
0x18001b7c4  lea     rax, aTargetgroup; "TargetGroup"
0x18001b7cb  jmp     loc_18001BA11
0x18001b7d0  sub     ecx, 6
0x18001b7d3  jz      short loc_18001B80C
0x18001b7d5  sub     ecx, 1
0x18001b7d8  jz      short loc_18001B800
0x18001b7da  sub     ecx, 1
0x18001b7dd  jz      short loc_18001B7F4
0x18001b7df  cmp     ecx, 1
0x18001b7e2  jnz     loc_18001B9BA
0x18001b7e8  lea     rax, aIgnoremoappdow; "IgnoreMOAppDownloadLimit"
0x18001b7ef  jmp     loc_18001BA11
0x18001b7f4  lea     rax, aIgnoremoupdate; "IgnoreMOUpdateDownloadLimit"
0x18001b7fb  jmp     loc_18001BA11
0x18001b800  lea     rax, aAllowautoupdat; "AllowAutoUpdate"
0x18001b807  jmp     loc_18001BA11
0x18001b80c  lea     rax, aRequireupdatea; "RequireUpdateApproval"
0x18001b813  jmp     loc_18001BA11
0x18001b818  lea     rax, aScheduledinsta_5; "ScheduledInstallDay"
0x18001b81f  jmp     loc_18001BA11
0x18001b824  sub     ecx, 0Bh
0x18001b827  jz      loc_18001B8B9
0x18001b82d  sub     ecx, 1
0x18001b830  jz      short loc_18001B8AD
0x18001b832  sub     ecx, 1
0x18001b835  jz      short loc_18001B8A1
0x18001b837  sub     ecx, 1
0x18001b83a  jz      short loc_18001B895
0x18001b83c  sub     ecx, 1
0x18001b83f  jz      short loc_18001B889
0x18001b841  sub     ecx, 1
0x18001b844  jz      short loc_18001B87D
0x18001b846  sub     ecx, 2
0x18001b849  jz      short loc_18001B871
0x18001b84b  sub     ecx, 4
0x18001b84e  jz      short loc_18001B865
0x18001b850  cmp     ecx, 1
0x18001b853  jnz     loc_18001B9BA
0x18001b859  lea     rax, aActivehourssta; "ActiveHoursStart"
0x18001b860  jmp     loc_18001BA11
0x18001b865  lea     rax, aSetactivehours_0; "SetActiveHours"
0x18001b86c  jmp     loc_18001BA11
0x18001b871  lea     rax, aFlightenabled; "FlightEnabled"
0x18001b878  jmp     loc_18001BA11
0x18001b87d  lea     rax, aAllownonmicros; "AllowNonMicrosoftSignedUpdate"
0x18001b884  jmp     loc_18001BA11
0x18001b889  lea     rax, aAllowupdateser; "AllowUpdateService"
0x18001b890  jmp     loc_18001BA11
0x18001b895  lea     rax, aDisableallunma; "DisableAllUnmanagedUpdateServicesWhenWs"...
0x18001b89c  jmp     loc_18001BA11
0x18001b8a1  lea     rax, aAllowresumeupd; "AllowResumeUpdateAfterDevicePoweredOn"
0x18001b8a8  jmp     loc_18001BA11
0x18001b8ad  lea     rax, aWuserver; "WUServer"
0x18001b8b4  jmp     loc_18001BA11
0x18001b8b9  lea     rax, aScheduledinsta_2; "ScheduledInstallTime"
0x18001b8c0  jmp     loc_18001BA11
0x18001b8c5  lea     rax, aActivehoursend; "ActiveHoursEnd"
0x18001b8cc  jmp     loc_18001BA11
0x18001b8d1  cmp     ecx, 22h ; '"'
0x18001b8d4  jg      loc_18001B98D
0x18001b8da  jz      loc_18001B981
0x18001b8e0  sub     ecx, 19h
0x18001b8e3  jz      loc_18001B975
0x18001b8e9  sub     ecx, 1
0x18001b8ec  jz      short loc_18001B969
0x18001b8ee  sub     ecx, 1
0x18001b8f1  jz      short loc_18001B95D
0x18001b8f3  sub     ecx, 1
0x18001b8f6  jz      short loc_18001B951
0x18001b8f8  sub     ecx, 1
0x18001b8fb  jz      short loc_18001B945
0x18001b8fd  sub     ecx, 1
0x18001b900  jz      short loc_18001B939
0x18001b902  sub     ecx, 1
0x18001b905  jz      short loc_18001B92D
0x18001b907  sub     ecx, 1
0x18001b90a  jz      short loc_18001B921
0x18001b90c  cmp     ecx, 1
0x18001b90f  jnz     loc_18001B9BA
0x18001b915  lea     rax, aPausequalityup_1; "PauseQualityUpdatesStartTime"
0x18001b91c  jmp     loc_18001BA11
0x18001b921  lea     rax, aScheduledinsta; "ScheduledInstallFourthWeek"
0x18001b928  jmp     loc_18001BA11
0x18001b92d  lea     rax, aScheduledinsta_3; "ScheduledInstallThirdWeek"
0x18001b934  jmp     loc_18001BA11
0x18001b939  lea     rax, aScheduledinsta_1; "ScheduledInstallSecondWeek"
0x18001b940  jmp     loc_18001BA11
0x18001b945  lea     rax, aScheduledinsta_0; "ScheduledInstallFirstWeek"
0x18001b94c  jmp     loc_18001BA11
0x18001b951  lea     rax, aScheduledinsta_4; "ScheduledInstallEveryWeek"
0x18001b958  jmp     loc_18001BA11
0x18001b95d  lea     rax, aFillemptyconte; "FillEmptyContentUrls"
0x18001b964  jmp     loc_18001BA11
0x18001b969  lea     rax, aUpdateserviceu; "UpdateServiceUrlAlternate"
0x18001b970  jmp     loc_18001BA11
0x18001b975  lea     rax, aAllowmuupdates; "AllowMUUpdateService"
0x18001b97c  jmp     loc_18001BA11
0x18001b981  lea     rax, aPausequalityup_0; "PauseQualityUpdatesEndTime"
0x18001b988  jmp     loc_18001BA11
0x18001b98d  sub     ecx, 23h ; '#'
0x18001b990  jz      short loc_18001BA0A
0x18001b992  sub     ecx, 1
0x18001b995  jz      short loc_18001BA01
0x18001b997  sub     ecx, 1
0x18001b99a  jz      short loc_18001B9F8
0x18001b99c  sub     ecx, 1
0x18001b99f  jz      short loc_18001B9EF
0x18001b9a1  sub     ecx, 1
0x18001b9a4  jz      short loc_18001B9E6
0x18001b9a6  sub     ecx, 1
0x18001b9a9  jz      short loc_18001B9DD
0x18001b9ab  sub     ecx, 1
0x18001b9ae  jz      short loc_18001B9D4
0x18001b9b0  sub     ecx, 1
0x18001b9b3  jz      short loc_18001B9CB
0x18001b9b5  cmp     ecx, 1
0x18001b9b8  jz      short loc_18001B9C2
0x18001b9ba  mov     r8d, 80070057h
0x18001b9c0  jmp     short loc_18001BA14
0x18001b9c2  lea     rax, aSetpolicydrive; "SetPolicyDrivenUpdateSourceForOtherUpda"...
0x18001b9c9  jmp     short loc_18001BA11
0x18001b9cb  lea     rax, aSetpolicydrive_0; "SetPolicyDrivenUpdateSourceForDriverUpd"...
0x18001b9d2  jmp     short loc_18001BA11
0x18001b9d4  lea     rax, aSetpolicydrive_2; "SetPolicyDrivenUpdateSourceForQualityUp"...
0x18001b9db  jmp     short loc_18001BA11
0x18001b9dd  lea     rax, aSetpolicydrive_1; "SetPolicyDrivenUpdateSourceForFeatureUp"...
0x18001b9e4  jmp     short loc_18001BA11
0x18001b9e6  lea     rax, aDonotenforceen; "DoNotEnforceEnterpriseTLSCertPinningFor"...
0x18001b9ed  jmp     short loc_18001BA11
0x18001b9ef  lea     rax, aSetproxybehavi; "SetProxyBehaviorForUpdateDetection"
0x18001b9f6  jmp     short loc_18001BA11
0x18001b9f8  lea     rax, aDisablewindows; "DisableWindowsUpdateAccess"
0x18001b9ff  jmp     short loc_18001BA11
0x18001ba01  lea     rax, aPausefeatureup; "PauseFeatureUpdatesEndTime"
0x18001ba08  jmp     short loc_18001BA11
0x18001ba0a  lea     rax, aPausefeatureup_0; "PauseFeatureUpdatesStartTime"
0x18001ba11  mov     [rdx], rax
0x18001ba14  mov     eax, r8d
0x18001ba17  retn
```
