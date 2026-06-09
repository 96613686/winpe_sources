# UpdatePolicyReader::ReadMDMPolicy(tagUpdatePolicy,tagUpdatePolicyValue_V1 *)

- ea: `0x18001ccf0`
- end: `0x18001d264`
- name: `?ReadMDMPolicy@UpdatePolicyReader@@CAJW4tagUpdatePolicy@@PEAUtagUpdatePolicyValue_V1@@@Z`
- size: `1396`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001a320`

## callees

- `0x18001ccf0`
- `0x18001d26c`
- `0x18001d380`
- `0x18001d534`
- `0x18001e7e4`
- `0x18001e9e8`
- `0x18002ffd0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001cd42`
- `OLEAUT32!__imp_VariantInit` at `0x18001cd42`
- `OLEAUT32!__imp_VariantClear` at `0x18001d236`
- `OLEAUT32!__imp_VariantClear` at `0x18001d236`

## string_xrefs

- `0x18001ce3c`: `AlwaysAutoRebootAtScheduledTimeMinutes`
- `0x18001cdcb`: `RequireUpdateApproval`
- `0x18001d02e`: `AllowResumeUpdateAfterDevicePoweredOn`
- `0x18001cdbc`: `AllowAutoUpdate`
- `0x18001ce01`: `AllowAutoUpdate`
- `0x18001cff5`: `AllowAutoUpdate`
- `0x18001cf6d`: `AllowUpdateService`
- `0x18001cfae`: `AllowUpdateService`
- `0x18001ce57`: `ScheduledInstallDay`
- `0x18001d057`: `ScheduledInstallTime`
- `0x18001cf17`: `UpdateServiceUrl`
- `0x18001cf47`: `UpdateServiceUrl`
- `0x18001cf80`: `UpdateServiceUrl`
- `0x18001d040`: `UpdateServiceUrl`
- `0x18001d15f`: `UpdateServiceUrl`
- `0x18001d18e`: `UpdateServiceUrl`
- `0x18001d1bb`: `UpdateServiceUrl`
- `0x18001d1e0`: `UpdateServiceUrl`
- `0x18001cf37`: `AllowNonMicrosoftSignedUpdate`
- `0x18001cdaa`: `IgnoreMOUpdateDownloadLimit`
- `0x18001d0f8`: `AllowMUUpdateService`
- `0x18001d20b`: `SetProxyBehaviorForUpdateDetection`
- `0x18001d0cf`: `ScheduledInstallEveryWeek`
- `0x18001d0bd`: `ScheduledInstallFirstWeek`
- `0x18001d0b1`: `ScheduledInstallSecondWeek`
- `0x18001d118`: `ScheduledInstallThirdWeek`
- `0x18001d214`: `ScheduledInstallFourthWeek`
- `0x18001d1f8`: `SetPolicyDrivenUpdateSourceForFeatureUpdates`
- `0x18001d1d3`: `SetPolicyDrivenUpdateSourceForQualityUpdates`
- `0x18001d1ae`: `SetPolicyDrivenUpdateSourceForDriverUpdates`
- `0x18001d17e`: `SetPolicyDrivenUpdateSourceForOtherUpdates`

## pseudocode

```c
__int64 __fastcall UpdatePolicyReader::ReadMDMPolicy(int a1, __int64 a2)
{
  int v3; // r15d
  int CspPolicy; // esi
  const wchar_t *v6; // rdx
  int v7; // ebx
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  const wchar_t *v12; // rcx
  unsigned int v13; // r9d
  unsigned int v14; // edx
  unsigned int v15; // r8d
  int v16; // ebx
  int v17; // ebx
  int v18; // ebx
  int v19; // ebx
  int v20; // ebx
  int v21; // ebx
  int MDMPolicy_DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection; // eax
  int v23; // ebx
  int v24; // ebx
  int v25; // ebx
  int v26; // ebx
  int v27; // ebx
  int v28; // ebx
  int v29; // ebx
  int v30; // ebx
  int v31; // ebx
  int v32; // ebx
  int v33; // ebx
  int v34; // ebx
  _BYTE v36[40]; // [rsp+30h] [rbp-30h] BYREF

  v3 = 0;
  CspPolicy = 0;
  memset(v36, 0, sizeof(v36));
  VariantInit((VARIANTARG *)&v36[16]);
  *(_QWORD *)&v36[4] = 0;
  *(_DWORD *)v36 = 0;
  *(_DWORD *)a2 = a1;
  if ( a1 > 23 )
  {
    if ( a1 > 31 )
    {
      v29 = a1 - 32;
      if ( !v29 )
      {
        v12 = L"ScheduledInstallFourthWeek";
        goto LABEL_91;
      }
      v30 = v29 - 6;
      if ( !v30 )
      {
        v12 = L"SetProxyBehaviorForUpdateDetection";
        goto LABEL_91;
      }
      v31 = v30 - 1;
      if ( v31 )
      {
        v32 = v31 - 1;
        if ( v32 )
        {
          v33 = v32 - 1;
          if ( v33 )
          {
            v34 = v33 - 1;
            if ( v34 )
            {
              if ( v34 == 1 )
              {
                CspPolicy = UpdatePolicyReader::ReadCspPolicy(
                              L"UpdateServiceUrl",
                              v6,
                              (struct tagUpdatePolicyValue_V1 *)v36);
                if ( CspPolicy >= 0 && *(_DWORD *)&v36[4] == 1 )
                {
                  v12 = L"SetPolicyDrivenUpdateSourceForOtherUpdates";
                  goto LABEL_91;
                }
              }
            }
            else
            {
              CspPolicy = UpdatePolicyReader::ReadCspPolicy(
                            L"UpdateServiceUrl",
                            v6,
                            (struct tagUpdatePolicyValue_V1 *)v36);
              if ( CspPolicy >= 0 && *(_DWORD *)&v36[4] == 1 )
              {
                v12 = L"SetPolicyDrivenUpdateSourceForDriverUpdates";
                goto LABEL_91;
              }
            }
          }
          else
          {
            CspPolicy = UpdatePolicyReader::ReadCspPolicy(
                          L"UpdateServiceUrl",
                          v6,
                          (struct tagUpdatePolicyValue_V1 *)v36);
            if ( CspPolicy >= 0 && *(_DWORD *)&v36[4] == 1 )
            {
              v12 = L"SetPolicyDrivenUpdateSourceForQualityUpdates";
              goto LABEL_91;
            }
          }
        }
        else
        {
          CspPolicy = UpdatePolicyReader::ReadCspPolicy(L"UpdateServiceUrl", v6, (struct tagUpdatePolicyValue_V1 *)v36);
          if ( CspPolicy >= 0 && *(_DWORD *)&v36[4] == 1 )
          {
            v12 = L"SetPolicyDrivenUpdateSourceForFeatureUpdates";
            goto LABEL_91;
          }
        }
        goto LABEL_96;
      }
      MDMPolicy_DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection = UpdatePolicyReader::ReadMDMPolicy_DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection((struct tagUpdatePolicyValue_V1 *)a2);
    }
    else
    {
      if ( a1 == 31 )
      {
        v12 = L"ScheduledInstallThirdWeek";
        goto LABEL_91;
      }
      v23 = a1 - 24;
      if ( !v23 )
      {
        v13 = 23;
        v12 = L"ActiveHoursEnd";
        v14 = 17;
        goto LABEL_93;
      }
      v24 = v23 - 1;
      if ( !v24 )
      {
        v12 = L"AllowMUUpdateService";
        goto LABEL_91;
      }
      v25 = v24 - 1;
      if ( v25 )
      {
        v26 = v25 - 1;
        if ( v26 )
        {
          v27 = v26 - 1;
          if ( v27 )
          {
            v28 = v27 - 1;
            if ( !v28 )
            {
              v12 = L"ScheduledInstallFirstWeek";
              goto LABEL_91;
            }
            if ( v28 == 1 )
            {
              v12 = L"ScheduledInstallSecondWeek";
              goto LABEL_91;
            }
            goto LABEL_96;
          }
          v13 = 1;
          v12 = L"ScheduledInstallEveryWeek";
          v14 = 1;
          goto LABEL_93;
        }
        MDMPolicy_DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection = UpdatePolicyReader::ReadMDMPolicy_FillEmptyContentUrls((struct tagUpdatePolicyValue_V1 *)a2);
      }
      else
      {
        MDMPolicy_DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection = UpdatePolicyReader::ReadMDMPolicy_UpdateServiceUrlAlternate((struct tagUpdatePolicyValue_V1 *)a2);
      }
    }
LABEL_95:
    CspPolicy = MDMPolicy_DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection;
    goto LABEL_96;
  }
  if ( a1 == 23 )
  {
    v13 = 23;
    v12 = L"ActiveHoursStart";
    v14 = 8;
    goto LABEL_93;
  }
  if ( a1 > 10 )
  {
    v16 = a1 - 11;
    if ( !v16 )
    {
      v13 = 24;
      v12 = L"ScheduledInstallTime";
      v14 = 3;
      goto LABEL_93;
    }
    v17 = v16 - 1;
    if ( v17 )
    {
      v18 = v17 - 1;
      if ( v18 )
      {
        v19 = v18 - 1;
        if ( !v19 )
        {
          CspPolicy = UpdatePolicyReader::ReadCspPolicy(L"UpdateServiceUrl", v6, (struct tagUpdatePolicyValue_V1 *)v36);
          if ( CspPolicy >= 0 && *(_DWORD *)&v36[4] == 1 )
          {
            CspPolicy = UpdatePolicyReader::ReadCspPolicy(
                          L"AllowUpdateService",
                          0,
                          0,
                          1u,
                          (struct tagUpdatePolicyValue_V1 *)a2);
            if ( CspPolicy >= 0 && *(_DWORD *)(a2 + 4) == 1 )
            {
              LOBYTE(v3) = *(_DWORD *)(a2 + 24) != 1;
              *(_DWORD *)(a2 + 24) = v3;
            }
          }
          goto LABEL_96;
        }
        v20 = v19 - 1;
        if ( v20 )
        {
          v21 = v20 - 1;
          if ( v21 )
          {
            if ( v21 == 6 )
            {
              CspPolicy = UpdatePolicyReader::ReadCspPolicy(
                            L"ActiveHoursStart",
                            8u,
                            0,
                            0x17u,
                            (struct tagUpdatePolicyValue_V1 *)v36);
              if ( CspPolicy >= 0 && *(_DWORD *)&v36[4] == 1 )
              {
                CspPolicy = UpdatePolicyReader::ReadCspPolicy(
                              L"ActiveHoursEnd",
                              0x11u,
                              0,
                              0x17u,
                              (struct tagUpdatePolicyValue_V1 *)a2);
                if ( CspPolicy >= 0 && *(_DWORD *)(a2 + 4) == 1 )
                {
                  *(_WORD *)(a2 + 16) = 3;
                  *(_DWORD *)(a2 + 24) = 1;
                }
              }
            }
          }
          else
          {
            CspPolicy = UpdatePolicyReader::ReadCspPolicy(
                          L"UpdateServiceUrl",
                          v6,
                          (struct tagUpdatePolicyValue_V1 *)v36);
            if ( CspPolicy >= 0 && *(_DWORD *)&v36[4] == 1 )
            {
              v12 = L"AllowNonMicrosoftSignedUpdate";
              goto LABEL_91;
            }
          }
          goto LABEL_96;
        }
        CspPolicy = UpdatePolicyReader::ReadCspPolicy(L"UpdateServiceUrl", v6, (struct tagUpdatePolicyValue_V1 *)v36);
        if ( CspPolicy < 0 || *(_DWORD *)&v36[4] != 1 )
          goto LABEL_96;
        v13 = 1;
        v12 = L"AllowUpdateService";
        v14 = 1;
      }
      else
      {
        CspPolicy = UpdatePolicyReader::ReadCspPolicy(
                      L"AllowAutoUpdate",
                      6u,
                      0,
                      4u,
                      (struct tagUpdatePolicyValue_V1 *)v36);
        if ( CspPolicy < 0 || *(_DWORD *)&v36[4] != 1 || (unsigned int)(*(_DWORD *)&v36[24] - 3) > 1 )
          goto LABEL_96;
        v13 = 1;
        v12 = L"AllowResumeUpdateAfterDevicePoweredOn";
        v14 = 1;
      }
LABEL_93:
      v15 = 0;
      goto LABEL_94;
    }
    MDMPolicy_DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection = UpdatePolicyReader::ReadCspPolicy(
                                                                         L"UpdateServiceUrl",
                                                                         v6,
                                                                         (struct tagUpdatePolicyValue_V1 *)a2);
    goto LABEL_95;
  }
  if ( a1 == 10 )
  {
    v13 = 7;
    v12 = L"ScheduledInstallDay";
LABEL_92:
    v14 = 0;
    goto LABEL_93;
  }
  if ( !a1 )
    goto LABEL_96;
  v7 = a1 - 1;
  if ( !v7 )
  {
    CspPolicy = UpdatePolicyReader::ReadCspPolicy(L"AllowAutoUpdate", 6u, 0, 4u, (struct tagUpdatePolicyValue_V1 *)v36);
    if ( CspPolicy < 0 || *(_DWORD *)&v36[4] != 1 || (unsigned int)(*(_DWORD *)&v36[24] - 1) > 3 )
      goto LABEL_96;
    v14 = 15;
    v12 = L"AlwaysAutoRebootAtScheduledTimeMinutes";
    v15 = 15;
    v13 = 180;
LABEL_94:
    MDMPolicy_DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection = UpdatePolicyReader::ReadCspPolicy(
                                                                         v12,
                                                                         v14,
                                                                         v15,
                                                                         v13,
                                                                         (struct tagUpdatePolicyValue_V1 *)a2);
    goto LABEL_95;
  }
  v8 = v7 - 3;
  if ( !v8 )
  {
    v14 = 22;
    v12 = L"DetectionFrequency";
    v13 = 22;
    v15 = 1;
    goto LABEL_94;
  }
  v9 = v8 - 2;
  if ( !v9 )
  {
    v12 = L"RequireUpdateApproval";
    goto LABEL_91;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    v13 = 6;
    v12 = L"AllowAutoUpdate";
    v14 = 6;
    goto LABEL_93;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    v12 = L"IgnoreMOUpdateDownloadLimit";
    goto LABEL_91;
  }
  if ( v11 == 1 )
  {
    v12 = L"IgnoreMOAppDownloadLimit";
LABEL_91:
    v13 = 1;
    goto LABEL_92;
  }
LABEL_96:
  VariantClear((VARIANTARG *)&v36[16]);
  return (unsigned int)CspPolicy;
}

```

## disassembly

```asm
0x18001ccf0  mov     [rsp-18h+arg_0], rbx
0x18001ccf5  mov     [rsp-18h+arg_10], rsi
0x18001ccfa  mov     [rsp-18h+arg_18], rdi
0x18001ccff  push    rbp
0x18001cd00  push    r14
0x18001cd02  push    r15
0x18001cd04  mov     rbp, rsp
0x18001cd07  sub     rsp, 60h
0x18001cd0b  mov     rax, cs:__security_cookie
0x18001cd12  xor     rax, rsp
0x18001cd15  mov     [rbp+var_8], rax
0x18001cd19  xor     eax, eax
0x18001cd1b  lea     rdi, [rbp+var_30]
0x18001cd1f  mov     ebx, ecx
0x18001cd21  mov     qword ptr [rbp+pvarg+10h], rax
0x18001cd25  xorps   xmm0, xmm0
0x18001cd28  xor     r15d, r15d
0x18001cd2b  movups  [rbp+var_30], xmm0
0x18001cd2f  lea     ecx, [rax+28h]
0x18001cd32  mov     r14, rdx
0x18001cd35  movups  xmmword ptr [rbp+pvarg], xmm0
0x18001cd39  mov     esi, r15d
0x18001cd3c  rep stosb
0x18001cd3e  lea     rcx, [rbp+pvarg]; pvarg
0x18001cd42  call    cs:__imp_VariantInit
0x18001cd48  lea     edi, [r15+17h]
0x18001cd4c  mov     qword ptr [rbp+var_30+4], r15
0x18001cd50  mov     dword ptr [rbp+var_30], r15d
0x18001cd54  mov     [r14], ebx
0x18001cd57  cmp     ebx, edi
0x18001cd59  jg      loc_18001D07B
0x18001cd5f  jz      loc_18001D067
0x18001cd65  cmp     ebx, 0Ah
0x18001cd68  jg      loc_18001CE63
0x18001cd6e  jz      loc_18001CE51
0x18001cd74  test    ebx, ebx
0x18001cd76  jz      loc_18001D232
0x18001cd7c  sub     ebx, 1
0x18001cd7f  jz      short loc_18001CDEF
0x18001cd81  sub     ebx, 3
0x18001cd84  jz      short loc_18001CDD7
0x18001cd86  sub     ebx, 2
0x18001cd89  jz      short loc_18001CDCB
0x18001cd8b  sub     ebx, 1
0x18001cd8e  jz      short loc_18001CDB6
0x18001cd90  sub     ebx, 1
0x18001cd93  jz      short loc_18001CDAA
0x18001cd95  cmp     ebx, 1
0x18001cd98  jnz     loc_18001D232
0x18001cd9e  lea     rcx, aIgnoremoappdow; "IgnoreMOAppDownloadLimit"
0x18001cda5  jmp     loc_18001D21B
0x18001cdaa  lea     rcx, aIgnoremoupdate; "IgnoreMOUpdateDownloadLimit"
0x18001cdb1  jmp     loc_18001D21B
0x18001cdb6  mov     r9d, 6
0x18001cdbc  lea     rcx, aAllowautoupdat; "AllowAutoUpdate"
0x18001cdc3  mov     edx, r9d
0x18001cdc6  jmp     loc_18001D223
0x18001cdcb  lea     rcx, aRequireupdatea; "RequireUpdateApproval"
0x18001cdd2  jmp     loc_18001D21B
0x18001cdd7  mov     edx, 16h
0x18001cddc  lea     rcx, aDetectionfrequ_0; "DetectionFrequency"
0x18001cde3  mov     r9d, edx
0x18001cde6  lea     r8d, [rdx-15h]
0x18001cdea  jmp     loc_18001D226
0x18001cdef  mov     r9d, 4; unsigned int
0x18001cdf5  lea     rax, [rbp+var_30]
0x18001cdf9  xor     r8d, r8d; unsigned int
0x18001cdfc  mov     [rsp+60h+var_40], rax; struct tagUpdatePolicyValue_V1 *
0x18001ce01  lea     rcx, aAllowautoupdat; "AllowAutoUpdate"
0x18001ce08  lea     edx, [r9+2]; unsigned int
0x18001ce0c  call    ?ReadCspPolicy@UpdatePolicyReader@@CAJPEB_WKKKPEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadCspPolicy(wchar_t const *,ulong,ulong,ulong,tagUpdatePolicyValue_V1 *)
0x18001ce11  mov     esi, eax
0x18001ce13  test    eax, eax
0x18001ce15  js      loc_18001D232
0x18001ce1b  cmp     dword ptr [rbp+var_30+4], 1
0x18001ce1f  jnz     loc_18001D232
0x18001ce25  mov     eax, dword ptr [rbp+pvarg+8]
0x18001ce28  mov     edx, 3
0x18001ce2d  dec     eax
0x18001ce2f  cmp     eax, edx
0x18001ce31  ja      loc_18001D232
0x18001ce37  mov     edx, 0Fh
0x18001ce3c  lea     rcx, aAlwaysautorebo_0; "AlwaysAutoRebootAtScheduledTimeMinutes"
0x18001ce43  mov     r8d, edx
0x18001ce46  mov     r9d, 0B4h
0x18001ce4c  jmp     loc_18001D226
0x18001ce51  mov     r9d, 7
0x18001ce57  lea     rcx, aScheduledinsta_5; "ScheduledInstallDay"
0x18001ce5e  jmp     loc_18001D221
0x18001ce63  sub     ebx, 0Bh
0x18001ce66  jz      loc_18001D051
0x18001ce6c  sub     ebx, 1
0x18001ce6f  jz      loc_18001D03D
0x18001ce75  sub     ebx, 1
0x18001ce78  jz      loc_18001CFE3
0x18001ce7e  sub     ebx, 1
0x18001ce81  jz      loc_18001CF7C
0x18001ce87  sub     ebx, 1
0x18001ce8a  jz      loc_18001CF43
0x18001ce90  sub     ebx, 1
0x18001ce93  jz      short loc_18001CF13
0x18001ce95  cmp     ebx, 6
0x18001ce98  jnz     loc_18001D232
0x18001ce9e  lea     rax, [rbp+var_30]
0x18001cea2  mov     r9d, edi; unsigned int
0x18001cea5  xor     r8d, r8d; unsigned int
0x18001cea8  mov     [rsp+60h+var_40], rax; struct tagUpdatePolicyValue_V1 *
0x18001cead  lea     edx, [rbx+2]; unsigned int
0x18001ceb0  lea     rcx, aActivehourssta; "ActiveHoursStart"
0x18001ceb7  call    ?ReadCspPolicy@UpdatePolicyReader@@CAJPEB_WKKKPEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadCspPolicy(wchar_t const *,ulong,ulong,ulong,tagUpdatePolicyValue_V1 *)
0x18001cebc  mov     esi, eax
0x18001cebe  test    eax, eax
0x18001cec0  js      loc_18001D232
0x18001cec6  cmp     dword ptr [rbp+var_30+4], 1
0x18001ceca  jnz     loc_18001D232
0x18001ced0  mov     r9d, edi; unsigned int
0x18001ced3  mov     [rsp+60h+var_40], r14; struct tagUpdatePolicyValue_V1 *
0x18001ced8  xor     r8d, r8d; unsigned int
0x18001cedb  lea     edx, [rbx+0Bh]; unsigned int
0x18001cede  lea     rcx, aActivehoursend; "ActiveHoursEnd"
0x18001cee5  call    ?ReadCspPolicy@UpdatePolicyReader@@CAJPEB_WKKKPEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadCspPolicy(wchar_t const *,ulong,ulong,ulong,tagUpdatePolicyValue_V1 *)
0x18001ceea  mov     esi, eax
0x18001ceec  test    eax, eax
0x18001ceee  js      loc_18001D232
0x18001cef4  cmp     dword ptr [r14+4], 1
0x18001cef9  jnz     loc_18001D232
0x18001ceff  mov     word ptr [r14+10h], 3
0x18001cf06  mov     dword ptr [r14+18h], 1
0x18001cf0e  jmp     loc_18001D232
0x18001cf13  lea     r8, [rbp+var_30]; struct tagUpdatePolicyValue_V1 *
0x18001cf17  lea     rcx, aUpdateserviceu_0; "UpdateServiceUrl"
0x18001cf1e  call    ?ReadCspPolicy@UpdatePolicyReader@@CAJPEB_W0PEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadCspPolicy(wchar_t const *,wchar_t const *,tagUpdatePolicyValue_V1 *)
0x18001cf23  mov     esi, eax
0x18001cf25  test    eax, eax
0x18001cf27  js      loc_18001D232
0x18001cf2d  cmp     dword ptr [rbp+var_30+4], 1
0x18001cf31  jnz     loc_18001D232
0x18001cf37  lea     rcx, aAllownonmicros; "AllowNonMicrosoftSignedUpdate"
0x18001cf3e  jmp     loc_18001D21B
0x18001cf43  lea     r8, [rbp+var_30]; struct tagUpdatePolicyValue_V1 *
0x18001cf47  lea     rcx, aUpdateserviceu_0; "UpdateServiceUrl"
0x18001cf4e  call    ?ReadCspPolicy@UpdatePolicyReader@@CAJPEB_W0PEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadCspPolicy(wchar_t const *,wchar_t const *,tagUpdatePolicyValue_V1 *)
0x18001cf53  mov     esi, eax
0x18001cf55  test    eax, eax
0x18001cf57  js      loc_18001D232
0x18001cf5d  cmp     dword ptr [rbp+var_30+4], 1
0x18001cf61  jnz     loc_18001D232
0x18001cf67  mov     r9d, 1
0x18001cf6d  lea     rcx, aAllowupdateser; "AllowUpdateService"
0x18001cf74  mov     edx, r9d
0x18001cf77  jmp     loc_18001D223
0x18001cf7c  lea     r8, [rbp+var_30]; struct tagUpdatePolicyValue_V1 *
0x18001cf80  lea     rcx, aUpdateserviceu_0; "UpdateServiceUrl"
0x18001cf87  call    ?ReadCspPolicy@UpdatePolicyReader@@CAJPEB_W0PEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadCspPolicy(wchar_t const *,wchar_t const *,tagUpdatePolicyValue_V1 *)
0x18001cf8c  mov     esi, eax
0x18001cf8e  test    eax, eax
0x18001cf90  js      loc_18001D232
0x18001cf96  cmp     dword ptr [rbp+var_30+4], 1
0x18001cf9a  jnz     loc_18001D232
0x18001cfa0  mov     r9d, 1; unsigned int
0x18001cfa6  mov     [rsp+60h+var_40], r14; struct tagUpdatePolicyValue_V1 *
0x18001cfab  xor     r8d, r8d; unsigned int
0x18001cfae  lea     rcx, aAllowupdateser; "AllowUpdateService"
0x18001cfb5  xor     edx, edx; unsigned int
0x18001cfb7  call    ?ReadCspPolicy@UpdatePolicyReader@@CAJPEB_WKKKPEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadCspPolicy(wchar_t const *,ulong,ulong,ulong,tagUpdatePolicyValue_V1 *)
0x18001cfbc  mov     esi, eax
0x18001cfbe  test    eax, eax
0x18001cfc0  js      loc_18001D232
0x18001cfc6  cmp     dword ptr [r14+4], 1
0x18001cfcb  jnz     loc_18001D232
0x18001cfd1  cmp     dword ptr [r14+18h], 1
0x18001cfd6  setnz   r15b
0x18001cfda  mov     [r14+18h], r15d
0x18001cfde  jmp     loc_18001D232
0x18001cfe3  mov     r9d, 4; unsigned int
0x18001cfe9  lea     rax, [rbp+var_30]
0x18001cfed  xor     r8d, r8d; unsigned int
0x18001cff0  mov     [rsp+60h+var_40], rax; struct tagUpdatePolicyValue_V1 *
0x18001cff5  lea     rcx, aAllowautoupdat; "AllowAutoUpdate"
0x18001cffc  lea     edx, [r9+2]; unsigned int
0x18001d000  call    ?ReadCspPolicy@UpdatePolicyReader@@CAJPEB_WKKKPEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadCspPolicy(wchar_t const *,ulong,ulong,ulong,tagUpdatePolicyValue_V1 *)
0x18001d005  mov     esi, eax
0x18001d007  test    eax, eax
0x18001d009  js      loc_18001D232
0x18001d00f  cmp     dword ptr [rbp+var_30+4], 1
0x18001d013  jnz     loc_18001D232
0x18001d019  mov     eax, dword ptr [rbp+pvarg+8]
0x18001d01c  add     eax, 0FFFFFFFDh
0x18001d01f  cmp     eax, 1
0x18001d022  ja      loc_18001D232
0x18001d028  mov     r9d, 1
0x18001d02e  lea     rcx, aAllowresumeupd; "AllowResumeUpdateAfterDevicePoweredOn"
0x18001d035  mov     edx, r9d
0x18001d038  jmp     loc_18001D223
0x18001d03d  mov     r8, r14; struct tagUpdatePolicyValue_V1 *
0x18001d040  lea     rcx, aUpdateserviceu_0; "UpdateServiceUrl"
0x18001d047  call    ?ReadCspPolicy@UpdatePolicyReader@@CAJPEB_W0PEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadCspPolicy(wchar_t const *,wchar_t const *,tagUpdatePolicyValue_V1 *)
0x18001d04c  jmp     loc_18001D230
0x18001d051  mov     r9d, 18h
0x18001d057  lea     rcx, aScheduledinsta_2; "ScheduledInstallTime"
0x18001d05e  lea     edx, [r9-15h]
0x18001d062  jmp     loc_18001D223
0x18001d067  mov     r9d, edi
0x18001d06a  lea     rcx, aActivehourssta; "ActiveHoursStart"
0x18001d071  mov     edx, 8
0x18001d076  jmp     loc_18001D223
0x18001d07b  cmp     ebx, 1Fh
0x18001d07e  jg      loc_18001D124
0x18001d084  jz      loc_18001D118
0x18001d08a  sub     ebx, 18h
0x18001d08d  jz      short loc_18001D104
0x18001d08f  sub     ebx, 1
0x18001d092  jz      short loc_18001D0F8
0x18001d094  sub     ebx, 1
0x18001d097  jz      short loc_18001D0EB
0x18001d099  sub     ebx, 1
0x18001d09c  jz      short loc_18001D0DE
0x18001d09e  sub     ebx, 1
0x18001d0a1  jz      short loc_18001D0C9
0x18001d0a3  sub     ebx, 1
0x18001d0a6  jz      short loc_18001D0BD
0x18001d0a8  cmp     ebx, 1
0x18001d0ab  jnz     loc_18001D232
0x18001d0b1  lea     rcx, aScheduledinsta_1; "ScheduledInstallSecondWeek"
0x18001d0b8  jmp     loc_18001D21B
0x18001d0bd  lea     rcx, aScheduledinsta_0; "ScheduledInstallFirstWeek"
0x18001d0c4  jmp     loc_18001D21B
0x18001d0c9  mov     r9d, 1
0x18001d0cf  lea     rcx, aScheduledinsta_4; "ScheduledInstallEveryWeek"
0x18001d0d6  mov     edx, r9d
0x18001d0d9  jmp     loc_18001D223
0x18001d0de  mov     rcx, r14; struct tagUpdatePolicyValue_V1 *
0x18001d0e1  call    ?ReadMDMPolicy_FillEmptyContentUrls@UpdatePolicyReader@@CAJPEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadMDMPolicy_FillEmptyContentUrls(tagUpdatePolicyValue_V1 *)
0x18001d0e6  jmp     loc_18001D230
0x18001d0eb  mov     rcx, r14; struct tagUpdatePolicyValue_V1 *
0x18001d0ee  call    ?ReadMDMPolicy_UpdateServiceUrlAlternate@UpdatePolicyReader@@CAJPEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadMDMPolicy_UpdateServiceUrlAlternate(tagUpdatePolicyValue_V1 *)
0x18001d0f3  jmp     loc_18001D230
0x18001d0f8  lea     rcx, aAllowmuupdates; "AllowMUUpdateService"
0x18001d0ff  jmp     loc_18001D21B
0x18001d104  mov     r9d, edi
0x18001d107  lea     rcx, aActivehoursend; "ActiveHoursEnd"
0x18001d10e  mov     edx, 11h
0x18001d113  jmp     loc_18001D223
0x18001d118  lea     rcx, aScheduledinsta_3; "ScheduledInstallThirdWeek"
0x18001d11f  jmp     loc_18001D21B
0x18001d124  sub     ebx, 20h ; ' '
0x18001d127  jz      loc_18001D214
0x18001d12d  sub     ebx, 6
0x18001d130  jz      loc_18001D20B
0x18001d136  sub     ebx, 1
0x18001d139  jz      loc_18001D201
0x18001d13f  sub     ebx, 1
0x18001d142  jz      loc_18001D1DC
0x18001d148  sub     ebx, 1
0x18001d14b  jz      short loc_18001D1B7
0x18001d14d  sub     ebx, 1
0x18001d150  jz      short loc_18001D18A
0x18001d152  cmp     ebx, 1
0x18001d155  jnz     loc_18001D232
0x18001d15b  lea     r8, [rbp+var_30]; struct tagUpdatePolicyValue_V1 *
0x18001d15f  lea     rcx, aUpdateserviceu_0; "UpdateServiceUrl"
0x18001d166  call    ?ReadCspPolicy@UpdatePolicyReader@@CAJPEB_W0PEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadCspPolicy(wchar_t const *,wchar_t const *,tagUpdatePolicyValue_V1 *)
0x18001d16b  mov     esi, eax
0x18001d16d  test    eax, eax
0x18001d16f  js      loc_18001D232
0x18001d175  cmp     dword ptr [rbp+var_30+4], ebx
0x18001d178  jnz     loc_18001D232
0x18001d17e  lea     rcx, aSetpolicydrive; "SetPolicyDrivenUpdateSourceForOtherUpda"...
0x18001d185  jmp     loc_18001D21B
0x18001d18a  lea     r8, [rbp+var_30]; struct tagUpdatePolicyValue_V1 *
0x18001d18e  lea     rcx, aUpdateserviceu_0; "UpdateServiceUrl"
0x18001d195  call    ?ReadCspPolicy@UpdatePolicyReader@@CAJPEB_W0PEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadCspPolicy(wchar_t const *,wchar_t const *,tagUpdatePolicyValue_V1 *)
0x18001d19a  mov     esi, eax
0x18001d19c  test    eax, eax
0x18001d19e  js      loc_18001D232
0x18001d1a4  cmp     dword ptr [rbp+var_30+4], 1
0x18001d1a8  jnz     loc_18001D232
0x18001d1ae  lea     rcx, aSetpolicydrive_0; "SetPolicyDrivenUpdateSourceForDriverUpd"...
0x18001d1b5  jmp     short loc_18001D21B
0x18001d1b7  lea     r8, [rbp+var_30]; struct tagUpdatePolicyValue_V1 *
0x18001d1bb  lea     rcx, aUpdateserviceu_0; "UpdateServiceUrl"
0x18001d1c2  call    ?ReadCspPolicy@UpdatePolicyReader@@CAJPEB_W0PEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadCspPolicy(wchar_t const *,wchar_t const *,tagUpdatePolicyValue_V1 *)
0x18001d1c7  mov     esi, eax
0x18001d1c9  test    eax, eax
0x18001d1cb  js      short loc_18001D232
0x18001d1cd  cmp     dword ptr [rbp+var_30+4], 1
0x18001d1d1  jnz     short loc_18001D232
0x18001d1d3  lea     rcx, aSetpolicydrive_2; "SetPolicyDrivenUpdateSourceForQualityUp"...
0x18001d1da  jmp     short loc_18001D21B
0x18001d1dc  lea     r8, [rbp+var_30]; struct tagUpdatePolicyValue_V1 *
0x18001d1e0  lea     rcx, aUpdateserviceu_0; "UpdateServiceUrl"
0x18001d1e7  call    ?ReadCspPolicy@UpdatePolicyReader@@CAJPEB_W0PEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadCspPolicy(wchar_t const *,wchar_t const *,tagUpdatePolicyValue_V1 *)
0x18001d1ec  mov     esi, eax
0x18001d1ee  test    eax, eax
0x18001d1f0  js      short loc_18001D232
0x18001d1f2  cmp     dword ptr [rbp+var_30+4], 1
0x18001d1f6  jnz     short loc_18001D232
0x18001d1f8  lea     rcx, aSetpolicydrive_1; "SetPolicyDrivenUpdateSourceForFeatureUp"...
0x18001d1ff  jmp     short loc_18001D21B
0x18001d201  mov     rcx, r14; struct tagUpdatePolicyValue_V1 *
  ... truncated ...
```
