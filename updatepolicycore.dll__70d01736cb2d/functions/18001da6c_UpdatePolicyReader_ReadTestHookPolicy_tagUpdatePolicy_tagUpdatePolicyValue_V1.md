# UpdatePolicyReader::ReadTestHookPolicy(tagUpdatePolicy,tagUpdatePolicyValue_V1 *)

- ea: `0x18001da6c`
- end: `0x18001df8b`
- name: `?ReadTestHookPolicy@UpdatePolicyReader@@CAJW4tagUpdatePolicy@@PEAUtagUpdatePolicyValue_V1@@@Z`
- size: `1311`
- prototype: `__int64 __fastcall(int, unsigned __int64, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001a320`

## callees

- `0x1800188fc`
- `0x18001da6c`
- `0x18001df94`
- `0x18001e074`
- `0x18002ffd0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001df0a`
- `OLEAUT32!__imp_VariantInit` at `0x18001df0a`
- `OLEAUT32!__imp_VariantClear` at `0x18001df5f`
- `OLEAUT32!__imp_VariantClear` at `0x18001df5f`
- `OLEAUT32!__imp_VariantCopy` at `0x18001df46`
- `OLEAUT32!__imp_VariantCopy` at `0x18001df46`

## string_xrefs

- `0x18001dd9b`: `PauseQualityUpdatesStartTime`
- `0x18001deff`: `PauseFeatureUpdatesStartTime`
- `0x18001de12`: `PauseQualityUpdatesEndTime`
- `0x18001def6`: `PauseFeatureUpdatesEndTime`
- `0x18001db13`: `AlwaysAutoRebootAtScheduledTimeMinutes`
- `0x18001deeb`: `DisableWindowsUpdateAccess`
- `0x18001dbcf`: `RequireUpdateApproval`
- `0x18001dcbc`: `AllowResumeUpdateAfterDevicePoweredOn`
- `0x18001dbc3`: `AllowAutoUpdate`
- `0x18001dcb0`: `DisableAllUnmanagedUpdateServicesWhenWsus`
- `0x18001dca4`: `AllowUpdateService`
- `0x18001dbdb`: `ScheduledInstallDay`
- `0x18001dcd4`: `ScheduledInstallTime`
- `0x18001dc98`: `AllowNonMicrosoftSignedUpdate`
- `0x18001dbb7`: `IgnoreMOUpdateDownloadLimit`
- `0x18001de06`: `AllowMUUpdateService`
- `0x18001ddef`: `UpdateServiceUrlAlternate`
- `0x18001dee2`: `SetProxyBehaviorForUpdateDetection`
- `0x18001ded9`: `DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection`
- `0x18001ddd7`: `ScheduledInstallEveryWeek`
- `0x18001ddcb`: `ScheduledInstallFirstWeek`
- `0x18001ddbf`: `ScheduledInstallSecondWeek`
- `0x18001ddb3`: `ScheduledInstallThirdWeek`
- `0x18001dda7`: `ScheduledInstallFourthWeek`
- `0x18001deb9`: `SetPolicyDrivenUpdateSourceForFeatureUpdates`
- `0x18001deb0`: `SetPolicyDrivenUpdateSourceForQualityUpdates`
- `0x18001dea7`: `SetPolicyDrivenUpdateSourceForDriverUpdates`
- `0x18001de9e`: `SetPolicyDrivenUpdateSourceForOtherUpdates`

## pseudocode

```c
__int64 __fastcall UpdatePolicyReader::ReadTestHookPolicy(
        int a1,
        unsigned __int64 a2,
        unsigned int a3,
        unsigned int a4)
{
  wchar_t *v4; // rsi
  unsigned int PolicyValue; // edi
  const wchar_t *v6; // rbx
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
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  unsigned int v30; // edx
  __int64 v32; // [rsp+38h] [rbp-48h] BYREF
  VARIANTARG pvargSrc; // [rsp+40h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-28h] BYREF

  v4 = (wchar_t *)a2;
  PolicyValue = 0;
  if ( !a2 )
    return (unsigned int)-2147467261;
  *(_DWORD *)a2 = a1;
  if ( a1 > 24 )
  {
    if ( a1 > 34 )
    {
      switch ( a1 )
      {
        case '#':
          v6 = L"PauseFeatureUpdatesStartTime";
          goto LABEL_118;
        case '$':
          v6 = L"PauseFeatureUpdatesEndTime";
          goto LABEL_118;
        case '%':
          v6 = L"DisableWindowsUpdateAccess";
          goto LABEL_115;
        case '&':
          v6 = L"SetProxyBehaviorForUpdateDetection";
          goto LABEL_115;
        case '\'':
          v6 = L"DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection";
          goto LABEL_115;
        case '(':
          v6 = L"SetPolicyDrivenUpdateSourceForFeatureUpdates";
          break;
        case ')':
          v6 = L"SetPolicyDrivenUpdateSourceForQualityUpdates";
          break;
        case '*':
          v6 = L"SetPolicyDrivenUpdateSourceForDriverUpdates";
          break;
        case '+':
          v6 = L"SetPolicyDrivenUpdateSourceForOtherUpdates";
          break;
        default:
          v6 = 0;
          v23 = a1 - 35;
          if ( !v23 )
            goto LABEL_118;
          v24 = v23 - 1;
          if ( !v24 )
            goto LABEL_118;
          v25 = v24 - 1;
          if ( !v25 )
            goto LABEL_115;
          v26 = v25 - 1;
          if ( !v26 )
            goto LABEL_115;
          v27 = v26 - 1;
          if ( !v27 )
            goto LABEL_115;
          v28 = v27 - 1;
          if ( v28 )
          {
            v29 = v28 - 1;
            if ( v29 )
            {
              if ( (unsigned int)(v29 - 1) >= 2 )
                return PolicyValue;
            }
          }
          break;
      }
    }
    else
    {
      if ( a1 == 34 )
      {
        v6 = L"PauseQualityUpdatesEndTime";
        goto LABEL_118;
      }
      if ( a1 == 25 )
      {
        v6 = L"AllowMUUpdateService";
        goto LABEL_115;
      }
      a2 = (unsigned int)(a1 - 26);
      if ( a1 == 26 )
      {
        v6 = L"UpdateServiceUrlAlternate";
        return (unsigned int)UpdatePolicyReader::ReadTestHookPolicy(
                               v6,
                               (const wchar_t *)a2,
                               (struct tagUpdatePolicyValue_V1 *)v4);
      }
      if ( a1 == 27 )
      {
        v6 = L"FillEmptyContentUrls";
        goto LABEL_115;
      }
      if ( a1 != 28 )
      {
        switch ( a1 )
        {
          case 29:
            v6 = L"ScheduledInstallFirstWeek";
            break;
          case 30:
            v6 = L"ScheduledInstallSecondWeek";
            break;
          case 31:
            v6 = L"ScheduledInstallThirdWeek";
            break;
          case 32:
            v6 = L"ScheduledInstallFourthWeek";
            break;
          default:
            v6 = L"PauseQualityUpdatesStartTime";
            goto LABEL_118;
        }
        goto LABEL_115;
      }
      v6 = L"ScheduledInstallEveryWeek";
    }
    goto LABEL_109;
  }
  if ( a1 == 24 )
  {
    v6 = L"ActiveHoursEnd";
    goto LABEL_118;
  }
  if ( a1 <= 10 )
  {
    if ( a1 == 10 )
    {
      v6 = L"ScheduledInstallDay";
      goto LABEL_118;
    }
    if ( a1 > 5 )
    {
      switch ( a1 )
      {
        case 6:
          v6 = L"RequireUpdateApproval";
          break;
        case 7:
          v6 = L"AllowAutoUpdate";
          goto LABEL_118;
        case 8:
          v6 = L"IgnoreMOUpdateDownloadLimit";
          break;
        default:
          v6 = L"IgnoreMOAppDownloadLimit";
          break;
      }
    }
    else
    {
      switch ( a1 )
      {
        case 5:
          v6 = L"TargetGroup";
          return (unsigned int)UpdatePolicyReader::ReadTestHookPolicy(
                                 v6,
                                 (const wchar_t *)a2,
                                 (struct tagUpdatePolicyValue_V1 *)v4);
        case 0:
          return PolicyValue;
        case 1:
          v6 = L"AlwaysAutoRebootAtScheduledTimeMinutes";
          goto LABEL_118;
      }
      if ( a1 != 2 )
      {
        a2 = (unsigned int)(a1 - 3);
        if ( a1 == 3 )
        {
          v6 = L"AUOptions";
          goto LABEL_118;
        }
        if ( a1 == 4 )
        {
          v6 = L"DetectionFrequency";
          goto LABEL_118;
        }
        v6 = 0;
        v7 = a1 - 1;
        if ( !v7 )
          goto LABEL_118;
        v8 = v7 - 1;
        if ( !v8 )
          goto LABEL_115;
        v9 = v8 - 1;
        if ( !v9 )
          goto LABEL_118;
        v10 = v9 - 1;
        if ( !v10 )
          goto LABEL_118;
        v11 = v10 - 1;
        if ( v11 )
        {
          v12 = v11 - 1;
          if ( v12 )
          {
            v13 = v12 - 1;
            if ( !v13 )
              goto LABEL_118;
            if ( (unsigned int)(v13 - 1) >= 2 )
              return PolicyValue;
          }
          goto LABEL_115;
        }
        return (unsigned int)UpdatePolicyReader::ReadTestHookPolicy(
                               v6,
                               (const wchar_t *)a2,
                               (struct tagUpdatePolicyValue_V1 *)v4);
      }
      v6 = L"NoAutoRebootWithLoggedOnUsers";
    }
LABEL_115:
    v30 = 0;
    return (unsigned int)UpdatePolicyReader::ReadTestHookPolicy(v6, v30, a3, a4, (struct tagUpdatePolicyValue_V1 *)v4);
  }
  if ( a1 == 11 )
  {
    v6 = L"ScheduledInstallTime";
    goto LABEL_118;
  }
  a2 = (unsigned int)(a1 - 12);
  switch ( a1 )
  {
    case 12:
      v6 = L"WUServer";
      return (unsigned int)UpdatePolicyReader::ReadTestHookPolicy(
                             v6,
                             (const wchar_t *)a2,
                             (struct tagUpdatePolicyValue_V1 *)v4);
    case 13:
      v6 = L"AllowResumeUpdateAfterDevicePoweredOn";
      goto LABEL_109;
    case 14:
      v6 = L"DisableAllUnmanagedUpdateServicesWhenWsus";
      goto LABEL_115;
    case 15:
      v6 = L"AllowUpdateService";
      goto LABEL_109;
    case 16:
      v6 = L"AllowNonMicrosoftSignedUpdate";
      goto LABEL_115;
    case 18:
      v6 = L"FlightEnabled";
      goto LABEL_115;
  }
  a2 = (unsigned int)(a1 - 22);
  if ( a1 == 22 )
  {
    v6 = L"SetActiveHours";
    goto LABEL_115;
  }
  if ( a1 == 23 )
  {
    v6 = L"ActiveHoursStart";
    goto LABEL_118;
  }
  v6 = 0;
  v14 = a1 - 11;
  if ( v14 )
  {
    v15 = v14 - 1;
    if ( !v15 )
      return (unsigned int)UpdatePolicyReader::ReadTestHookPolicy(
                             v6,
                             (const wchar_t *)a2,
                             (struct tagUpdatePolicyValue_V1 *)v4);
    v16 = v15 - 1;
    if ( v16 )
    {
      v17 = v16 - 1;
      if ( !v17 )
        goto LABEL_115;
      v18 = v17 - 1;
      if ( v18 )
      {
        v19 = v18 - 1;
        if ( v19 )
        {
          v20 = v19 - 2;
          if ( v20 )
          {
            v21 = v20 - 4;
            if ( v21 )
            {
              if ( v21 != 1 )
                return PolicyValue;
              goto LABEL_118;
            }
          }
        }
        goto LABEL_115;
      }
    }
LABEL_109:
    v30 = 1;
    return (unsigned int)UpdatePolicyReader::ReadTestHookPolicy(v6, v30, a3, a4, (struct tagUpdatePolicyValue_V1 *)v4);
  }
LABEL_118:
  VariantInit(&pvarg);
  v32 = 0;
  pvargSrc = pvarg;
  PolicyValue = TestHookPolicyReader::GetPolicyValue(v6, 3u, (struct tagTestHookPolicyValue_V1 *)&v32);
  if ( (PolicyValue & 0x80000000) == 0 )
  {
    PolicyValue = VariantCopy((VARIANTARG *)(v4 + 8), &pvargSrc);
    *((_DWORD *)v4 + 1) = v32;
    *((_DWORD *)v4 + 2) = 6;
  }
  VariantClear(&pvarg);
  return PolicyValue;
}

```

## disassembly

```asm
0x18001da6c  mov     [rsp-18h+arg_0], rbx
0x18001da71  mov     [rsp-18h+arg_10], rsi
0x18001da76  push    rbp
0x18001da77  push    rdi
0x18001da78  push    r14
0x18001da7a  mov     rbp, rsp
0x18001da7d  sub     rsp, 80h
0x18001da84  mov     rax, cs:__security_cookie
0x18001da8b  xor     rax, rsp
0x18001da8e  mov     [rbp+var_10], rax
0x18001da92  mov     rsi, rdx
0x18001da95  xor     r14d, r14d
0x18001da98  mov     edi, r14d
0x18001da9b  test    rdx, rdx
0x18001da9e  jnz     short loc_18001DAAA
0x18001daa0  mov     edi, 80004003h
0x18001daa5  jmp     loc_18001DF65
0x18001daaa  mov     [rdx], ecx
0x18001daac  cmp     ecx, 18h
0x18001daaf  jg      loc_18001DCEC
0x18001dab5  jz      loc_18001DCE0
0x18001dabb  cmp     ecx, 0Ah
0x18001dabe  jg      loc_18001DBE7
0x18001dac4  jz      loc_18001DBDB
0x18001daca  cmp     ecx, 5
0x18001dacd  jg      short loc_18001DB2B
0x18001dacf  jz      short loc_18001DB1F
0x18001dad1  mov     edx, ecx
0x18001dad3  test    ecx, ecx
0x18001dad5  jz      loc_18001DF65
0x18001dadb  sub     edx, 1
0x18001dade  jz      short loc_18001DB13
0x18001dae0  sub     edx, 1
0x18001dae3  jz      short loc_18001DB07
0x18001dae5  sub     edx, 1
0x18001dae8  jz      short loc_18001DAFB
0x18001daea  cmp     edx, 1
0x18001daed  jnz     short loc_18001DB49
0x18001daef  lea     rbx, aDetectionfrequ_0; "DetectionFrequency"
0x18001daf6  jmp     loc_18001DF06
0x18001dafb  lea     rbx, aAuoptions; "AUOptions"
0x18001db02  jmp     loc_18001DF06
0x18001db07  lea     rbx, aNoautorebootwi; "NoAutoRebootWithLoggedOnUsers"
0x18001db0e  jmp     loc_18001DEF2
0x18001db13  lea     rbx, aAlwaysautorebo_0; "AlwaysAutoRebootAtScheduledTimeMinutes"
0x18001db1a  jmp     loc_18001DF06
0x18001db1f  lea     rbx, aTargetgroup; "TargetGroup"
0x18001db26  jmp     loc_18001DDF6
0x18001db2b  mov     edx, ecx
0x18001db2d  sub     edx, 6
0x18001db30  jz      loc_18001DBCF
0x18001db36  sub     edx, 1
0x18001db39  jz      loc_18001DBC3
0x18001db3f  sub     edx, 1
0x18001db42  jz      short loc_18001DBB7
0x18001db44  cmp     edx, 1
0x18001db47  jz      short loc_18001DBAB
0x18001db49  mov     rbx, r14
0x18001db4c  cmp     ecx, 0Ah
0x18001db4f  jz      loc_18001DF06
0x18001db55  sub     ecx, 1
0x18001db58  jz      loc_18001DF06
0x18001db5e  sub     ecx, 1
0x18001db61  jz      loc_18001DEF2
0x18001db67  sub     ecx, 1
0x18001db6a  jz      loc_18001DF06
0x18001db70  sub     ecx, 1
0x18001db73  jz      loc_18001DF06
0x18001db79  sub     ecx, 1
0x18001db7c  jz      loc_18001DDF6
0x18001db82  sub     ecx, 1
0x18001db85  jz      loc_18001DEF2
0x18001db8b  sub     ecx, 1
0x18001db8e  jz      loc_18001DF06
0x18001db94  sub     ecx, 1
0x18001db97  jz      loc_18001DEF2
0x18001db9d  cmp     ecx, 1
0x18001dba0  jz      loc_18001DEF2
0x18001dba6  jmp     loc_18001DF65
0x18001dbab  lea     rbx, aIgnoremoappdow; "IgnoreMOAppDownloadLimit"
0x18001dbb2  jmp     loc_18001DEF2
0x18001dbb7  lea     rbx, aIgnoremoupdate; "IgnoreMOUpdateDownloadLimit"
0x18001dbbe  jmp     loc_18001DEF2
0x18001dbc3  lea     rbx, aAllowautoupdat; "AllowAutoUpdate"
0x18001dbca  jmp     loc_18001DF06
0x18001dbcf  lea     rbx, aRequireupdatea; "RequireUpdateApproval"
0x18001dbd6  jmp     loc_18001DEF2
0x18001dbdb  lea     rbx, aScheduledinsta_5; "ScheduledInstallDay"
0x18001dbe2  jmp     loc_18001DF06
0x18001dbe7  mov     edx, ecx
0x18001dbe9  sub     edx, 0Bh
0x18001dbec  jz      loc_18001DCD4
0x18001dbf2  sub     edx, 1
0x18001dbf5  jz      loc_18001DCC8
0x18001dbfb  sub     edx, 1
0x18001dbfe  jz      loc_18001DCBC
0x18001dc04  sub     edx, 1
0x18001dc07  jz      loc_18001DCB0
0x18001dc0d  sub     edx, 1
0x18001dc10  jz      loc_18001DCA4
0x18001dc16  sub     edx, 1
0x18001dc19  jz      short loc_18001DC98
0x18001dc1b  sub     edx, 2
0x18001dc1e  jz      short loc_18001DC8C
0x18001dc20  sub     edx, 4
0x18001dc23  jz      short loc_18001DC80
0x18001dc25  cmp     edx, 1
0x18001dc28  jz      short loc_18001DC74
0x18001dc2a  mov     rbx, r14
0x18001dc2d  sub     ecx, 0Bh
0x18001dc30  jz      loc_18001DF06
0x18001dc36  sub     ecx, 1
0x18001dc39  jz      loc_18001DDF6
0x18001dc3f  sub     ecx, 1
0x18001dc42  jz      loc_18001DEC0
0x18001dc48  sub     ecx, 1
0x18001dc4b  jz      loc_18001DEF2
0x18001dc51  sub     ecx, 1
0x18001dc54  jz      loc_18001DEC0
0x18001dc5a  sub     ecx, 1
0x18001dc5d  jz      loc_18001DEF2
0x18001dc63  sub     ecx, 2
0x18001dc66  jz      loc_18001DEF2
0x18001dc6c  sub     ecx, 4
0x18001dc6f  jmp     loc_18001DD87
0x18001dc74  lea     rbx, aActivehourssta; "ActiveHoursStart"
0x18001dc7b  jmp     loc_18001DF06
0x18001dc80  lea     rbx, aSetactivehours_0; "SetActiveHours"
0x18001dc87  jmp     loc_18001DEF2
0x18001dc8c  lea     rbx, aFlightenabled; "FlightEnabled"
0x18001dc93  jmp     loc_18001DEF2
0x18001dc98  lea     rbx, aAllownonmicros; "AllowNonMicrosoftSignedUpdate"
0x18001dc9f  jmp     loc_18001DEF2
0x18001dca4  lea     rbx, aAllowupdateser; "AllowUpdateService"
0x18001dcab  jmp     loc_18001DEC0
0x18001dcb0  lea     rbx, aDisableallunma; "DisableAllUnmanagedUpdateServicesWhenWs"...
0x18001dcb7  jmp     loc_18001DEF2
0x18001dcbc  lea     rbx, aAllowresumeupd; "AllowResumeUpdateAfterDevicePoweredOn"
0x18001dcc3  jmp     loc_18001DEC0
0x18001dcc8  lea     rbx, aWuserver; "WUServer"
0x18001dccf  jmp     loc_18001DDF6
0x18001dcd4  lea     rbx, aScheduledinsta_2; "ScheduledInstallTime"
0x18001dcdb  jmp     loc_18001DF06
0x18001dce0  lea     rbx, aActivehoursend; "ActiveHoursEnd"
0x18001dce7  jmp     loc_18001DF06
0x18001dcec  cmp     ecx, 22h ; '"'
0x18001dcef  jg      loc_18001DE1E
0x18001dcf5  jz      loc_18001DE12
0x18001dcfb  mov     edx, ecx
0x18001dcfd  sub     edx, 19h
0x18001dd00  jz      loc_18001DE06
0x18001dd06  sub     edx, 1; wchar_t *
0x18001dd09  jz      loc_18001DDEF
0x18001dd0f  sub     edx, 1
0x18001dd12  jz      loc_18001DDE3
0x18001dd18  sub     edx, 1
0x18001dd1b  jz      loc_18001DDD7
0x18001dd21  sub     edx, 1
0x18001dd24  jz      loc_18001DDCB
0x18001dd2a  sub     edx, 1
0x18001dd2d  jz      loc_18001DDBF
0x18001dd33  sub     edx, 1
0x18001dd36  jz      short loc_18001DDB3
0x18001dd38  sub     edx, 1
0x18001dd3b  jz      short loc_18001DDA7
0x18001dd3d  cmp     edx, 1
0x18001dd40  jz      short loc_18001DD9B
0x18001dd42  mov     rbx, r14
0x18001dd45  sub     ecx, 19h
0x18001dd48  jz      loc_18001DEF2
0x18001dd4e  sub     ecx, 1
0x18001dd51  jz      loc_18001DDF6
0x18001dd57  sub     ecx, 1
0x18001dd5a  jz      loc_18001DEF2
0x18001dd60  sub     ecx, 1
0x18001dd63  jz      loc_18001DEC0
0x18001dd69  sub     ecx, 1
0x18001dd6c  jz      loc_18001DEF2
0x18001dd72  sub     ecx, 1
0x18001dd75  jz      loc_18001DEF2
0x18001dd7b  sub     ecx, 1
0x18001dd7e  jz      loc_18001DEF2
0x18001dd84  sub     ecx, 1
0x18001dd87  jz      loc_18001DEF2
0x18001dd8d  cmp     ecx, 1
0x18001dd90  jz      loc_18001DF06
0x18001dd96  jmp     loc_18001DF65
0x18001dd9b  lea     rbx, aPausequalityup_1; "PauseQualityUpdatesStartTime"
0x18001dda2  jmp     loc_18001DF06
0x18001dda7  lea     rbx, aScheduledinsta; "ScheduledInstallFourthWeek"
0x18001ddae  jmp     loc_18001DEF2
0x18001ddb3  lea     rbx, aScheduledinsta_3; "ScheduledInstallThirdWeek"
0x18001ddba  jmp     loc_18001DEF2
0x18001ddbf  lea     rbx, aScheduledinsta_1; "ScheduledInstallSecondWeek"
0x18001ddc6  jmp     loc_18001DEF2
0x18001ddcb  lea     rbx, aScheduledinsta_0; "ScheduledInstallFirstWeek"
0x18001ddd2  jmp     loc_18001DEF2
0x18001ddd7  lea     rbx, aScheduledinsta_4; "ScheduledInstallEveryWeek"
0x18001ddde  jmp     loc_18001DEC0
0x18001dde3  lea     rbx, aFillemptyconte; "FillEmptyContentUrls"
0x18001ddea  jmp     loc_18001DEF2
0x18001ddef  lea     rbx, aUpdateserviceu; "UpdateServiceUrlAlternate"
0x18001ddf6  mov     r8, rsi; struct tagUpdatePolicyValue_V1 *
0x18001ddf9  mov     rcx, rbx; wchar_t *
0x18001ddfc  call    ?ReadTestHookPolicy@UpdatePolicyReader@@CAJPEB_W0PEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadTestHookPolicy(wchar_t const *,wchar_t const *,tagUpdatePolicyValue_V1 *)
0x18001de01  jmp     loc_18001DED2
0x18001de06  lea     rbx, aAllowmuupdates; "AllowMUUpdateService"
0x18001de0d  jmp     loc_18001DEF2
0x18001de12  lea     rbx, aPausequalityup_0; "PauseQualityUpdatesEndTime"
0x18001de19  jmp     loc_18001DF06
0x18001de1e  mov     edx, ecx
0x18001de20  sub     edx, 23h ; '#'
0x18001de23  jz      loc_18001DEFF
0x18001de29  sub     edx, 1
0x18001de2c  jz      loc_18001DEF6
0x18001de32  sub     edx, 1
0x18001de35  jz      loc_18001DEEB
0x18001de3b  sub     edx, 1
0x18001de3e  jz      loc_18001DEE2
0x18001de44  sub     edx, 1
0x18001de47  jz      loc_18001DED9
0x18001de4d  sub     edx, 1
0x18001de50  jz      short loc_18001DEB9
0x18001de52  sub     edx, 1
0x18001de55  jz      short loc_18001DEB0
0x18001de57  sub     edx, 1
0x18001de5a  jz      short loc_18001DEA7
0x18001de5c  cmp     edx, 1
0x18001de5f  jz      short loc_18001DE9E
0x18001de61  mov     rbx, r14
0x18001de64  sub     ecx, 23h ; '#'
0x18001de67  jz      loc_18001DF06
0x18001de6d  sub     ecx, 1
0x18001de70  jz      loc_18001DF06
0x18001de76  sub     ecx, 1
0x18001de79  jz      short loc_18001DEF2
0x18001de7b  sub     ecx, 1
0x18001de7e  jz      short loc_18001DEF2
0x18001de80  sub     ecx, 1
0x18001de83  jz      short loc_18001DEF2
0x18001de85  sub     ecx, 1
0x18001de88  jz      short loc_18001DEC0
0x18001de8a  sub     ecx, 1
0x18001de8d  jz      short loc_18001DEC0
0x18001de8f  sub     ecx, 1
0x18001de92  jz      short loc_18001DEC0
0x18001de94  cmp     ecx, 1
0x18001de97  jz      short loc_18001DEC0
0x18001de99  jmp     loc_18001DF65
0x18001de9e  lea     rbx, aSetpolicydrive; "SetPolicyDrivenUpdateSourceForOtherUpda"...
0x18001dea5  jmp     short loc_18001DEC0
0x18001dea7  lea     rbx, aSetpolicydrive_0; "SetPolicyDrivenUpdateSourceForDriverUpd"...
0x18001deae  jmp     short loc_18001DEC0
0x18001deb0  lea     rbx, aSetpolicydrive_2; "SetPolicyDrivenUpdateSourceForQualityUp"...
0x18001deb7  jmp     short loc_18001DEC0
0x18001deb9  lea     rbx, aSetpolicydrive_1; "SetPolicyDrivenUpdateSourceForFeatureUp"...
0x18001dec0  mov     edx, 1; unsigned int
0x18001dec5  mov     [rsp+80h+var_60], rsi; struct tagUpdatePolicyValue_V1 *
0x18001deca  mov     rcx, rbx; wchar_t *
0x18001decd  call    ?ReadTestHookPolicy@UpdatePolicyReader@@CAJPEB_WKKKPEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadTestHookPolicy(wchar_t const *,ulong,ulong,ulong,tagUpdatePolicyValue_V1 *)
0x18001ded2  mov     edi, eax
0x18001ded4  jmp     loc_18001DF65
0x18001ded9  lea     rbx, aDonotenforceen; "DoNotEnforceEnterpriseTLSCertPinningFor"...
0x18001dee0  jmp     short loc_18001DEF2
0x18001dee2  lea     rbx, aSetproxybehavi; "SetProxyBehaviorForUpdateDetection"
0x18001dee9  jmp     short loc_18001DEF2
0x18001deeb  lea     rbx, aDisablewindows; "DisableWindowsUpdateAccess"
0x18001def2  xor     edx, edx
0x18001def4  jmp     short loc_18001DEC5
0x18001def6  lea     rbx, aPausefeatureup; "PauseFeatureUpdatesEndTime"
0x18001defd  jmp     short loc_18001DF06
0x18001deff  lea     rbx, aPausefeatureup_0; "PauseFeatureUpdatesStartTime"
0x18001df06  lea     rcx, [rbp+pvarg]; pvarg
0x18001df0a  call    cs:__imp_VariantInit
0x18001df10  nop
0x18001df11  mov     [rbp+var_48], r14
0x18001df15  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18001df19  movups  xmmword ptr [rbp+pvargSrc], xmm0
0x18001df1d  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18001df22  movsd   qword ptr [rbp+pvargSrc+10h], xmm1
0x18001df27  mov     edx, 3; unsigned __int16
0x18001df2c  lea     r8, [rbp+var_48]; struct tagTestHookPolicyValue_V1 *
0x18001df30  mov     rcx, rbx; wchar_t *
0x18001df33  call    ?GetPolicyValue@TestHookPolicyReader@@SAJPEB_WGPEAUtagTestHookPolicyValue_V1@@@Z; TestHookPolicyReader::GetPolicyValue(wchar_t const *,ushort,tagTestHookPolicyValue_V1 *)
0x18001df38  mov     edi, eax
0x18001df3a  test    eax, eax
0x18001df3c  js      short loc_18001DF5B
0x18001df3e  lea     rcx, [rsi+10h]; pvargDest
0x18001df42  lea     rdx, [rbp+pvargSrc]; pvargSrc
0x18001df46  call    cs:__imp_VariantCopy
0x18001df4c  mov     edi, eax
0x18001df4e  mov     eax, dword ptr [rbp+var_48]
0x18001df51  mov     [rsi+4], eax
0x18001df54  mov     dword ptr [rsi+8], 6
0x18001df5b  lea     rcx, [rbp+pvarg]; pvarg
0x18001df5f  call    cs:__imp_VariantClear
0x18001df65  mov     eax, edi
0x18001df67  mov     rcx, [rbp+var_10]
0x18001df6b  xor     rcx, rsp; StackCookie
0x18001df6e  call    __security_check_cookie
  ... truncated ...
```
