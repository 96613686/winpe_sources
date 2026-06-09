# UpdatePolicyReader::ReadGPPolicyCore(tagUpdatePolicy,tagUpdatePolicyValue_V1 *,wchar_t const *,wchar_t const *)

- ea: `0x18001bf44`
- end: `0x18001c884`
- name: `?ReadGPPolicyCore@UpdatePolicyReader@@CAJW4tagUpdatePolicy@@PEAUtagUpdatePolicyValue_V1@@PEB_W2@Z`
- size: `2368`
- prototype: `__int64 __fastcall(int, __int64, const wchar_t *, const wchar_t *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001bb5c`
- `0x18001bd30`

## callees

- `0x180014ea8`
- `0x18001bf44`
- `0x18001c88c`
- `0x18001c9bc`
- `0x18001cbac`
- `0x18001e480`
- `0x18001e52c`
- `0x18001e5f4`
- `0x18001e680`
- `0x18001e704`
- `0x18001ec08`
- `0x18002ffd0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001bfa5`
- `OLEAUT32!__imp_VariantInit` at `0x18001bfa5`
- `OLEAUT32!__imp_VariantClear` at `0x18001c855`
- `OLEAUT32!__imp_VariantClear` at `0x18001c855`

## string_xrefs

- `0x18001c157`: `AlwaysAutoRebootAtScheduledTime`
- `0x18001c13f`: `AlwaysAutoRebootAtScheduledTimeMinutes`
- `0x18001c567`: `NoAutoUpdate`
- `0x18001c283`: `DoNotConnectToWindowsUpdateInternetLocations`
- `0x18001c34d`: `DoNotConnectToWindowsUpdateInternetLocations`
- `0x18001c2bf`: `DisableWindowsUpdateAccess`
- `0x18001c83d`: `DisableWindowsUpdateAccess`
- `0x18001c021`: `ScheduledInstallDay`
- `0x18001c185`: `ScheduledInstallTime`
- `0x18001c592`: `AllowMUUpdateService`
- `0x18001c808`: `SetProxyBehaviorForUpdateDetection`
- `0x18001c527`: `ScheduledInstallEveryWeek`
- `0x18001c4f1`: `ScheduledInstallFirstWeek`
- `0x18001c4c7`: `ScheduledInstallSecondWeek`
- `0x18001c4a1`: `ScheduledInstallThirdWeek`
- `0x18001c5c5`: `ScheduledInstallFourthWeek`
- `0x18001c657`: `UseUpdateClassPolicySource`
- `0x18001c6e2`: `UseUpdateClassPolicySource`
- `0x18001c758`: `UseUpdateClassPolicySource`
- `0x18001c7ce`: `UseUpdateClassPolicySource`
- `0x18001c7ec`: `SetPolicyDrivenUpdateSourceForFeatureUpdates`
- `0x18001c782`: `SetPolicyDrivenUpdateSourceForQualityUpdates`
- `0x18001c70c`: `SetPolicyDrivenUpdateSourceForDriverUpdates`
- `0x18001c680`: `SetPolicyDrivenUpdateSourceForOtherUpdates`

## pseudocode

```c
__int64 __fastcall UpdatePolicyReader::ReadGPPolicyCore(int a1, __int64 a2, const wchar_t *a3, const wchar_t *a4)
{
  int GPPolicyStateOnly; // esi
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  const wchar_t *v14; // rdx
  unsigned int v15; // r9d
  unsigned int v16; // r8d
  int GPDWordPolicyValueWithPolicyState; // eax
  const wchar_t *v18; // r9
  const wchar_t *v19; // rcx
  const wchar_t *v20; // rdx
  const wchar_t *v21; // r9
  int v22; // eax
  const wchar_t *v23; // rdx
  const wchar_t *v24; // r8
  const wchar_t *v25; // rcx
  int GPAuOptions; // eax
  const wchar_t *v27; // rdx
  const wchar_t *v28; // rcx
  int v29; // ebx
  int v30; // ebx
  int v31; // ebx
  int v32; // ebx
  int v33; // ebx
  int v34; // ebx
  bool v35; // zf
  int v36; // ebx
  int v37; // ebx
  int v38; // ebx
  int v39; // ebx
  int v40; // ebx
  int v41; // ebx
  int v42; // ebx
  int v43; // ebx
  int v44; // ebx
  int v45; // ebx
  int v46; // ebx
  int v47; // ebx
  const wchar_t *v48; // rdx
  unsigned int v50; // [rsp+20h] [rbp-60h]
  unsigned int v51; // [rsp+20h] [rbp-60h]
  struct tagUpdatePolicyValue_V1 *v52; // [rsp+28h] [rbp-58h]
  unsigned int v53; // [rsp+28h] [rbp-58h]
  unsigned int v54; // [rsp+30h] [rbp-50h]
  struct tagUpdatePolicyValue_V1 *v55; // [rsp+38h] [rbp-48h]
  int v56; // [rsp+40h] [rbp-40h] BYREF
  int v57; // [rsp+44h] [rbp-3Ch] BYREF
  _BYTE v58[40]; // [rsp+48h] [rbp-38h] BYREF

  *(_DWORD *)a2 = a1;
  v56 = 0;
  GPPolicyStateOnly = 0;
  v57 = 0;
  memset(v58, 0, sizeof(v58));
  VariantInit((VARIANTARG *)&v58[16]);
  *(_QWORD *)&v58[4] = 0;
  *(_DWORD *)v58 = 0;
  if ( a1 <= 24 )
  {
    if ( a1 == 24 )
    {
      v55 = (struct tagUpdatePolicyValue_V1 *)a2;
      v21 = L"ActiveHoursEnd";
      v54 = 23;
      v53 = 0;
      v51 = 17;
LABEL_43:
      v24 = a3;
      v23 = L"SetActiveHours";
      v25 = a3;
      goto LABEL_24;
    }
    if ( a1 <= 11 )
    {
      if ( a1 == 11 )
      {
        if ( (unsigned int)UpdatePolicyReader::GetGPAuOptions(a4) == 4 )
        {
          v52 = (struct tagUpdatePolicyValue_V1 *)a2;
          v16 = 3;
          v50 = 24;
          v14 = L"ScheduledInstallTime";
          v15 = 0;
          goto LABEL_15;
        }
        goto LABEL_147;
      }
      if ( !a1 )
        goto LABEL_147;
      v9 = a1 - 1;
      if ( !v9 )
      {
        if ( (unsigned int)UpdatePolicyReader::GetGPAuOptions(a4) - 4 > 1 )
          goto LABEL_147;
        v55 = (struct tagUpdatePolicyValue_V1 *)a2;
        v21 = L"AlwaysAutoRebootAtScheduledTimeMinutes";
        v22 = 15;
        v54 = 180;
        v53 = 15;
        v23 = L"AlwaysAutoRebootAtScheduledTime";
LABEL_23:
        v24 = a4;
        v51 = v22;
        v25 = a4;
LABEL_24:
        GPDWordPolicyValueWithPolicyState = UpdatePolicyReader::ReadGPDWordPolicyValueWithPolicyState(
                                              v25,
                                              v23,
                                              v24,
                                              v21,
                                              v51,
                                              v53,
                                              v54,
                                              v55);
        goto LABEL_146;
      }
      v10 = v9 - 1;
      if ( v10 )
      {
        v11 = v10 - 1;
        if ( v11 )
        {
          v12 = v11 - 1;
          if ( v12 )
          {
            v13 = v12 - 1;
            if ( v13 )
            {
              if ( v13 == 5 && (unsigned int)UpdatePolicyReader::GetGPAuOptions(a4) == 4 )
              {
                v52 = (struct tagUpdatePolicyValue_V1 *)a2;
                v14 = L"ScheduledInstallDay";
                v50 = 7;
LABEL_14:
                v15 = 0;
                v16 = 0;
LABEL_15:
                GPDWordPolicyValueWithPolicyState = UpdatePolicyReader::ReadGPDWordPolicyValueWithoutPolicyState(
                                                      a4,
                                                      v14,
                                                      v16,
                                                      v15,
                                                      v50,
                                                      v52);
                goto LABEL_146;
              }
              goto LABEL_147;
            }
            GPPolicyStateOnly = UpdatePolicyReader::ReadGPPolicyStateHelper(
                                  a4,
                                  L"UseWUServer",
                                  (enum tagUpdatePolicyStatus *)&v56,
                                  &v57);
            if ( GPPolicyStateOnly < 0 || v56 != 1 || !v57 )
              goto LABEL_147;
            v18 = L"TargetGroup";
            v19 = a3;
            v20 = L"TargetGroupEnabled";
            goto LABEL_21;
          }
          v55 = (struct tagUpdatePolicyValue_V1 *)a2;
          v21 = L"DetectionFrequency";
          v22 = 22;
          v23 = L"DetectionFrequencyEnabled";
          v54 = 22;
          v53 = 1;
          goto LABEL_23;
        }
        GPAuOptions = UpdatePolicyReader::GetGPAuOptions(a4);
        if ( !GPAuOptions )
          goto LABEL_147;
        *(_DWORD *)(a2 + 24) = GPAuOptions;
        goto LABEL_27;
      }
      if ( (unsigned int)UpdatePolicyReader::GetGPAuOptions(a4) - 4 > 1 )
        goto LABEL_147;
      v27 = L"NoAutoRebootWithLoggedOnUsers";
      v28 = a4;
LABEL_145:
      GPDWordPolicyValueWithPolicyState = UpdatePolicyReader::ReadGPPolicyStateOnly(
                                            v28,
                                            v27,
                                            (struct tagUpdatePolicyValue_V1 *)a2);
      goto LABEL_146;
    }
    v29 = a1 - 12;
    if ( !v29 )
    {
      v18 = L"WUServer";
      v19 = a4;
      v20 = L"UseWUServer";
LABEL_21:
      GPDWordPolicyValueWithPolicyState = UpdatePolicyReader::ReadGPStringPolicyValueWithPolicyState(
                                            v19,
                                            v20,
                                            a3,
                                            v18,
                                            (struct tagUpdatePolicyValue_V1 *)a2);
      goto LABEL_146;
    }
    v30 = v29 - 1;
    if ( v30 )
    {
      v31 = v30 - 1;
      if ( v31 )
      {
        v32 = v31 - 1;
        if ( !v32 )
        {
          GPPolicyStateOnly = UpdatePolicyReader::ReadGPPolicyStateHelper(
                                a4,
                                L"UseWUServer",
                                (enum tagUpdatePolicyStatus *)&v56,
                                &v57);
          if ( GPPolicyStateOnly >= 0 && v56 == 1 )
          {
            if ( v57 )
            {
              GPPolicyStateOnly = UpdatePolicyReader::ReadGPPolicyStateOnly(
                                    a3,
                                    L"DoNotConnectToWindowsUpdateInternetLocations",
                                    (struct tagUpdatePolicyValue_V1 *)a2);
              if ( GPPolicyStateOnly >= 0 )
              {
                if ( *(_DWORD *)(a2 + 4) != 1
                  || (v35 = *(_DWORD *)(a2 + 24) == 1, *(_DWORD *)(a2 + 24) = *(_DWORD *)(a2 + 24) != 1, !v35) )
                {
                  GPPolicyStateOnly = UpdatePolicyReader::ReadGPPolicyStateOnly(
                                        a3,
                                        L"DisableWindowsUpdateAccess",
                                        (struct tagUpdatePolicyValue_V1 *)v58);
                  if ( GPPolicyStateOnly >= 0 && *(_DWORD *)&v58[4] == 1 )
                  {
                    *(_DWORD *)(a2 + 24) = *(_DWORD *)&v58[24] != 1;
                    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes>::GetImpl'::`2'::impl) )
                      *(_WORD *)(a2 + 16) = 3;
                    *(_DWORD *)(a2 + 8) = *(_DWORD *)&v58[8];
                    *(_DWORD *)(a2 + 4) = 1;
                  }
                }
              }
            }
          }
          goto LABEL_147;
        }
        v33 = v32 - 1;
        if ( v33 )
        {
          v34 = v33 - 6;
          if ( v34 )
          {
            if ( v34 != 1 )
              goto LABEL_147;
            v55 = (struct tagUpdatePolicyValue_V1 *)a2;
            v21 = L"ActiveHoursStart";
            v54 = 23;
            v53 = 0;
            v51 = 8;
            goto LABEL_43;
          }
          v27 = L"SetActiveHours";
        }
        else
        {
          GPPolicyStateOnly = UpdatePolicyReader::ReadGPPolicyStateHelper(
                                a4,
                                L"UseWUServer",
                                (enum tagUpdatePolicyStatus *)&v56,
                                &v57);
          if ( GPPolicyStateOnly < 0 || v56 != 1 || !v57 )
            goto LABEL_147;
          v27 = L"AcceptTrustedPublisherCerts";
        }
      }
      else
      {
        GPPolicyStateOnly = UpdatePolicyReader::ReadGPPolicyStateHelper(
                              a4,
                              L"UseWUServer",
                              (enum tagUpdatePolicyStatus *)&v56,
                              &v57);
        if ( GPPolicyStateOnly < 0 || v56 != 1 || !v57 )
          goto LABEL_147;
        v27 = L"DoNotConnectToWindowsUpdateInternetLocations";
      }
LABEL_144:
      v28 = a3;
      goto LABEL_145;
    }
    if ( (unsigned int)UpdatePolicyReader::GetGPAuOptions(a4) != 4 )
      goto LABEL_147;
    GPPolicyStateOnly = UpdatePolicyReader::ReadGPPolicyStateHelper(
                          a4,
                          L"AutomaticMaintenanceEnabled",
                          (enum tagUpdatePolicyStatus *)&v56,
                          &v57);
    if ( GPPolicyStateOnly < 0 || v56 && (v56 != 1 || v57) )
      goto LABEL_147;
    v56 = 0;
    v57 = 0;
    GPPolicyStateOnly = UpdatePolicyReader::ReadGPPolicyStateHelper(
                          a4,
                          L"RescheduleWaitTimeEnabled",
                          (enum tagUpdatePolicyStatus *)&v56,
                          &v57);
    if ( GPPolicyStateOnly < 0 || v56 != 1 )
      goto LABEL_147;
    if ( v57 )
    {
      v15 = 1;
      v52 = (struct tagUpdatePolicyValue_V1 *)a2;
      v16 = 1;
      v50 = 60;
      v14 = L"RescheduleWaitTime";
      goto LABEL_15;
    }
LABEL_73:
    *(_DWORD *)(a2 + 24) = 0;
LABEL_27:
    *(_DWORD *)(a2 + 4) = 1;
    *(_WORD *)(a2 + 16) = 3;
LABEL_28:
    *(_DWORD *)(a2 + 8) = 1;
    goto LABEL_147;
  }
  if ( a1 > 32 )
  {
    v42 = a1 - 37;
    if ( v42 )
    {
      v43 = v42 - 1;
      if ( v43 )
      {
        v44 = v43 - 1;
        if ( !v44 )
        {
          GPDWordPolicyValueWithPolicyState = UpdatePolicyReader::ReadGPPolicy_DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection(
                                                (struct tagUpdatePolicyValue_V1 *)a2,
                                                a3,
                                                a4);
          goto LABEL_146;
        }
        v45 = v44 - 1;
        if ( v45 )
        {
          v46 = v45 - 1;
          if ( v46 )
          {
            v47 = v46 - 1;
            if ( v47 )
            {
              if ( v47 != 1 )
                goto LABEL_147;
              GPPolicyStateOnly = UpdatePolicyReader::ReadGPPolicyStateHelper(
                                    a4,
                                    L"UseWUServer",
                                    (enum tagUpdatePolicyStatus *)&v56,
                                    &v57);
              if ( GPPolicyStateOnly < 0 )
                goto LABEL_147;
              if ( v56 != 1 )
                goto LABEL_147;
              if ( !v57 )
                goto LABEL_147;
              GPPolicyStateOnly = UpdatePolicyReader::ReadGPPolicyStateHelper(
                                    a4,
                                    L"UseUpdateClassPolicySource",
                                    (enum tagUpdatePolicyStatus *)&v56,
                                    &v57);
              if ( GPPolicyStateOnly < 0 || v56 != 1 || !v57 )
                goto LABEL_147;
              v48 = L"SetPolicyDrivenUpdateSourceForOtherUpdates";
            }
            else
            {
              GPPolicyStateOnly = UpdatePolicyReader::ReadGPPolicyStateHelper(
                                    a4,
                                    L"UseWUServer",
                                    (enum tagUpdatePolicyStatus *)&v56,
                                    &v57);
              if ( GPPolicyStateOnly < 0 )
                goto LABEL_147;
              if ( v56 != 1 )
                goto LABEL_147;
              if ( !v57 )
                goto LABEL_147;
              GPPolicyStateOnly = UpdatePolicyReader::ReadGPPolicyStateHelper(
                                    a4,
                                    L"UseUpdateClassPolicySource",
                                    (enum tagUpdatePolicyStatus *)&v56,
                                    &v57);
              if ( GPPolicyStateOnly < 0 || v56 != 1 || !v57 )
                goto LABEL_147;
              v48 = L"SetPolicyDrivenUpdateSourceForDriverUpdates";
            }
          }
          else
          {
            GPPolicyStateOnly = UpdatePolicyReader::ReadGPPolicyStateHelper(
                                  a4,
                                  L"UseWUServer",
                                  (enum tagUpdatePolicyStatus *)&v56,
                                  &v57);
            if ( GPPolicyStateOnly < 0 )
              goto LABEL_147;
            if ( v56 != 1 )
              goto LABEL_147;
            if ( !v57 )
              goto LABEL_147;
            GPPolicyStateOnly = UpdatePolicyReader::ReadGPPolicyStateHelper(
                                  a4,
                                  L"UseUpdateClassPolicySource",
                                  (enum tagUpdatePolicyStatus *)&v56,
                                  &v57);
            if ( GPPolicyStateOnly < 0 || v56 != 1 || !v57 )
              goto LABEL_147;
            v48 = L"SetPolicyDrivenUpdateSourceForQualityUpdates";
          }
        }
        else
        {
          GPPolicyStateOnly = UpdatePolicyReader::ReadGPPolicyStateHelper(
                                a4,
                                L"UseWUServer",
                                (enum tagUpdatePolicyStatus *)&v56,
                                &v57);
          if ( GPPolicyStateOnly < 0 )
            goto LABEL_147;
          if ( v56 != 1 )
            goto LABEL_147;
          if ( !v57 )
            goto LABEL_147;
          GPPolicyStateOnly = UpdatePolicyReader::ReadGPPolicyStateHelper(
                                a4,
                                L"UseUpdateClassPolicySource",
                                (enum tagUpdatePolicyStatus *)&v56,
                                &v57);
          if ( GPPolicyStateOnly < 0 || v56 != 1 || !v57 )
            goto LABEL_147;
          v48 = L"SetPolicyDrivenUpdateSourceForFeatureUpdates";
        }
      }
      else
      {
        v48 = L"SetProxyBehaviorForUpdateDetection";
      }
      GPDWordPolicyValueWithPolicyState = UpdatePolicyReader::ReadGPDWordPolicyValueWithoutPolicyState(
                                            a3,
                                            v48,
                                            0,
                                            0,
                                            1u,
                                            (struct tagUpdatePolicyValue_V1 *)a2);
LABEL_146:
      GPPolicyStateOnly = GPDWordPolicyValueWithPolicyState;
      goto LABEL_147;
    }
    GPPolicyStateOnly = UpdatePolicyReader::ReadGPPolicyStateHelper(
                          a4,
                          L"UseWUServer",
                          (enum tagUpdatePolicyStatus *)&v56,
                          &v57);
    if ( GPPolicyStateOnly < 0 || v56 != 1 || !v57 )
      goto LABEL_147;
    v27 = L"DisableWindowsUpdateAccess";
    goto LABEL_144;
  }
  if ( a1 == 32 )
  {
    if ( (unsigned int)UpdatePolicyReader::GetGPAuOptions(a4) == 4 )
    {
      v52 = (struct tagUpdatePolicyValue_V1 *)a2;
      v14 = L"ScheduledInstallFourthWeek";
      v50 = 1;
      goto LABEL_14;
    }
    goto LABEL_147;
  }
  v36 = a1 - 25;
  if ( !v36 )
  {
    GPPolicyStateOnly = UpdatePolicyReader::ReadGPPolicyStateHelper(
                          a4,
                          L"NoAutoUpdate",
                          (enum tagUpdatePolicyStatus *)&v56,
                          &v57);
    if ( GPPolicyStateOnly < 0 )
      goto LABEL_147;
    if ( v56 != 1 )
    {
      *(_DWORD *)(a2 + 4) = 0;
      goto LABEL_28;
    }
    if ( !v57 )
    {
      v52 = (struct tagUpdatePolicyValue_V1 *)a2;
      v14 = L"AllowMUUpdateService";
      v50 = 1;
      goto LABEL_14;
    }
    goto LABEL_73;
  }
  v37 = v36 - 1;
  if ( !v37 )
  {
    GPDWordPolicyValueWithPolicyState = UpdatePolicyReader::ReadGPPolicy_UpdateServiceUrlAlternate(
                                          (struct tagUpdatePolicyValue_V1 *)a2,
                                          a3,
                                          a4);
    goto LABEL_146;
  }
  v38 = v37 - 1;
  if ( !v38 )
  {
    GPDWordPolicyValueWithPolicyState = UpdatePolicyReader::ReadGPPolicy_FillEmptyContentUrls(
                                          (struct tagUpdatePolicyValue_V1 *)a2,
                                          a3,
                                          a4);
    goto LABEL_146;
  }
  v39 = v38 - 1;
  if ( v39 )
  {
    v40 = v39 - 1;
    if ( v40 )
    {
      v41 = v40 - 1;
      if ( v41 )
      {
        if ( v41 == 1 && (unsigned int)UpdatePolicyReader::GetGPAuOptions(a4) == 4 )
        {
          v52 = (struct tagUpdatePolicyValue_V1 *)a2;
          v14 = L"ScheduledInstallThirdWeek";
          v50 = 1;
          goto LABEL_14;
        }
      }
      else if ( (unsigned int)UpdatePolicyReader::GetGPAuOptions(a4) == 4 )
      {
        v52 = (struct tagUpdatePolicyValue_V1 *)a2;
        v14 = L"ScheduledInstallSecondWeek";
        v50 = 1;
        goto LABEL_14;
      }
    }
    else if ( (unsigned int)UpdatePolicyReader::GetGPAuOptions(a4) == 4 )
    {
      v52 = (struct tagUpdatePolicyValue_V1 *)a2;
      v14 = L"ScheduledInstallFirstWeek";
      v50 = 1;
      goto LABEL_14;
    }
  }
  else if ( (unsigned int)UpdatePolicyReader::GetGPAuOptions(a4) == 4 )
  {
    v52 = (struct tagUpdatePolicyValue_V1 *)a2;
    v16 = 1;
    v50 = 1;
    v14 = L"ScheduledInstallEveryWeek";
    v15 = 0;
    goto LABEL_15;
  }
LABEL_147:
  VariantClear((VARIANTARG *)&v58[16]);
  return (unsigned int)GPPolicyStateOnly;
}

```

## disassembly

```asm
0x18001bf44  mov     [rsp-38h+arg_0], rbx
0x18001bf49  push    rbp
0x18001bf4a  push    rsi
0x18001bf4b  push    rdi
0x18001bf4c  push    r12
0x18001bf4e  push    r13
0x18001bf50  push    r14
0x18001bf52  push    r15
0x18001bf54  mov     rbp, rsp
0x18001bf57  sub     rsp, 80h
0x18001bf5e  mov     rax, cs:__security_cookie
0x18001bf65  xor     rax, rsp
0x18001bf68  mov     [rbp+var_10], rax
0x18001bf6c  xor     eax, eax
0x18001bf6e  mov     [rdx], ecx
0x18001bf70  mov     ebx, ecx
0x18001bf72  mov     qword ptr [rbp+pvarg+10h], rax
0x18001bf76  xorps   xmm0, xmm0
0x18001bf79  lea     rdi, [rbp+var_38]
0x18001bf7d  xor     r13d, r13d
0x18001bf80  mov     r15, r9
0x18001bf83  lea     ecx, [rax+28h]
0x18001bf86  mov     [rbp+var_40], r13d
0x18001bf8a  movups  [rbp+var_38], xmm0
0x18001bf8e  mov     r12, r8
0x18001bf91  mov     r14, rdx
0x18001bf94  movups  xmmword ptr [rbp+pvarg], xmm0
0x18001bf98  mov     esi, r13d
0x18001bf9b  mov     [rbp+var_3C], r13d
0x18001bf9f  rep stosb
0x18001bfa1  lea     rcx, [rbp+pvarg]; pvarg
0x18001bfa5  call    cs:__imp_VariantInit
0x18001bfab  mov     qword ptr [rbp+var_38+4], r13
0x18001bfaf  mov     dword ptr [rbp+var_38], r13d
0x18001bfb3  cmp     ebx, 18h
0x18001bfb6  jg      loc_18001C445
0x18001bfbc  jz      loc_18001C41F
0x18001bfc2  cmp     ebx, 0Bh
0x18001bfc5  jg      loc_18001C194
0x18001bfcb  jz      loc_18001C163
0x18001bfd1  test    ebx, ebx
0x18001bfd3  jz      loc_18001C851
0x18001bfd9  sub     ebx, 1
0x18001bfdc  jz      loc_18001C126
0x18001bfe2  sub     ebx, 1
0x18001bfe5  jz      loc_18001C103
0x18001bfeb  sub     ebx, 1
0x18001bfee  jz      loc_18001C0D3
0x18001bff4  sub     ebx, 1
0x18001bff7  jz      loc_18001C09B
0x18001bffd  sub     ebx, 1
0x18001c000  jz      short loc_18001C043
0x18001c002  cmp     ebx, 5
0x18001c005  jnz     loc_18001C851
0x18001c00b  mov     rcx, r15; wchar_t *
0x18001c00e  call    ?GetGPAuOptions@UpdatePolicyReader@@CAKPEB_W@Z; UpdatePolicyReader::GetGPAuOptions(wchar_t const *)
0x18001c013  cmp     eax, 4
0x18001c016  jnz     loc_18001C851
0x18001c01c  mov     [rsp+80h+var_58], r14; struct tagUpdatePolicyValue_V1 *
0x18001c021  lea     rdx, aScheduledinsta_5; "ScheduledInstallDay"
0x18001c028  mov     dword ptr [rsp+80h+var_60], 7; unsigned int
0x18001c030  xor     r9d, r9d; unsigned int
0x18001c033  xor     r8d, r8d; unsigned int
0x18001c036  mov     rcx, r15; wchar_t *
0x18001c039  call    ?ReadGPDWordPolicyValueWithoutPolicyState@UpdatePolicyReader@@CAJPEB_W0KKKPEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadGPDWordPolicyValueWithoutPolicyState(wchar_t const *,wchar_t const *,ulong,ulong,ulong,tagUpdatePolicyValue_V1 *)
0x18001c03e  jmp     loc_18001C84F
0x18001c043  lea     r9, [rbp+var_3C]; int *
0x18001c047  mov     rcx, r15; lpSubKey
0x18001c04a  lea     r8, [rbp+var_40]; enum tagUpdatePolicyStatus *
0x18001c04e  lea     rdx, aUsewuserver; "UseWUServer"
0x18001c055  call    ?ReadGPPolicyStateHelper@UpdatePolicyReader@@CAJPEB_W0PEAW4tagUpdatePolicyStatus@@PEAH@Z; UpdatePolicyReader::ReadGPPolicyStateHelper(wchar_t const *,wchar_t const *,tagUpdatePolicyStatus *,int *)
0x18001c05a  mov     esi, eax
0x18001c05c  test    eax, eax
0x18001c05e  js      loc_18001C851
0x18001c064  cmp     [rbp+var_40], 1
0x18001c068  jnz     loc_18001C851
0x18001c06e  cmp     [rbp+var_3C], r13d
0x18001c072  jz      loc_18001C851
0x18001c078  lea     r9, aTargetgroup; "TargetGroup"
0x18001c07f  mov     rcx, r12; wchar_t *
0x18001c082  lea     rdx, aTargetgroupena; "TargetGroupEnabled"
0x18001c089  mov     r8, r12; wchar_t *
0x18001c08c  mov     [rsp+80h+var_60], r14; struct tagUpdatePolicyValue_V1 *
0x18001c091  call    ?ReadGPStringPolicyValueWithPolicyState@UpdatePolicyReader@@CAJPEB_W000PEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadGPStringPolicyValueWithPolicyState(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,tagUpdatePolicyValue_V1 *)
0x18001c096  jmp     loc_18001C84F
0x18001c09b  mov     [rsp+80h+var_48], r14; struct tagUpdatePolicyValue_V1 *
0x18001c0a0  lea     r9, aDetectionfrequ_0; "DetectionFrequency"
0x18001c0a7  mov     eax, 16h
0x18001c0ac  lea     rdx, aDetectionfrequ; "DetectionFrequencyEnabled"
0x18001c0b3  mov     [rsp+80h+var_50], eax; unsigned int
0x18001c0b7  mov     dword ptr [rsp+80h+var_58], 1; unsigned int
0x18001c0bf  mov     r8, r15; wchar_t *
0x18001c0c2  mov     dword ptr [rsp+80h+var_60], eax; unsigned int
0x18001c0c6  mov     rcx, r15; wchar_t *
0x18001c0c9  call    ?ReadGPDWordPolicyValueWithPolicyState@UpdatePolicyReader@@CAJPEB_W000KKKPEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadGPDWordPolicyValueWithPolicyState(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,tagUpdatePolicyValue_V1 *)
0x18001c0ce  jmp     loc_18001C84F
0x18001c0d3  mov     rcx, r15; wchar_t *
0x18001c0d6  call    ?GetGPAuOptions@UpdatePolicyReader@@CAKPEB_W@Z; UpdatePolicyReader::GetGPAuOptions(wchar_t const *)
0x18001c0db  test    eax, eax
0x18001c0dd  jz      loc_18001C851
0x18001c0e3  mov     [r14+18h], eax
0x18001c0e7  mov     dword ptr [r14+4], 1
0x18001c0ef  mov     word ptr [r14+10h], 3
0x18001c0f6  mov     dword ptr [r14+8], 1
0x18001c0fe  jmp     loc_18001C851
0x18001c103  mov     rcx, r15; wchar_t *
0x18001c106  call    ?GetGPAuOptions@UpdatePolicyReader@@CAKPEB_W@Z; UpdatePolicyReader::GetGPAuOptions(wchar_t const *)
0x18001c10b  add     eax, 0FFFFFFFCh
0x18001c10e  cmp     eax, 1
0x18001c111  ja      loc_18001C851
0x18001c117  lea     rdx, aNoautorebootwi; "NoAutoRebootWithLoggedOnUsers"
0x18001c11e  mov     rcx, r15
0x18001c121  jmp     loc_18001C847
0x18001c126  mov     rcx, r15; wchar_t *
0x18001c129  call    ?GetGPAuOptions@UpdatePolicyReader@@CAKPEB_W@Z; UpdatePolicyReader::GetGPAuOptions(wchar_t const *)
0x18001c12e  add     eax, 0FFFFFFFCh
0x18001c131  cmp     eax, 1
0x18001c134  ja      loc_18001C851
0x18001c13a  mov     [rsp+80h+var_48], r14
0x18001c13f  lea     r9, aAlwaysautorebo_0; "AlwaysAutoRebootAtScheduledTimeMinutes"
0x18001c146  mov     eax, 0Fh
0x18001c14b  mov     [rsp+80h+var_50], 0B4h
0x18001c153  mov     dword ptr [rsp+80h+var_58], eax
0x18001c157  lea     rdx, aAlwaysautorebo; "AlwaysAutoRebootAtScheduledTime"
0x18001c15e  jmp     loc_18001C0BF
0x18001c163  mov     rcx, r15; wchar_t *
0x18001c166  call    ?GetGPAuOptions@UpdatePolicyReader@@CAKPEB_W@Z; UpdatePolicyReader::GetGPAuOptions(wchar_t const *)
0x18001c16b  cmp     eax, 4
0x18001c16e  jnz     loc_18001C851
0x18001c174  mov     [rsp+80h+var_58], r14
0x18001c179  lea     r8d, [rax-1]
0x18001c17d  mov     dword ptr [rsp+80h+var_60], 18h
0x18001c185  lea     rdx, aScheduledinsta_2; "ScheduledInstallTime"
0x18001c18c  xor     r9d, r9d
0x18001c18f  jmp     loc_18001C036
0x18001c194  sub     ebx, 0Ch
0x18001c197  jz      loc_18001C409
0x18001c19d  sub     ebx, 1
0x18001c1a0  jz      loc_18001C359
0x18001c1a6  sub     ebx, 1
0x18001c1a9  jz      loc_18001C318
0x18001c1af  sub     ebx, 1
0x18001c1b2  jz      loc_18001C24B
0x18001c1b8  sub     ebx, 1
0x18001c1bb  jz      short loc_18001C20A
0x18001c1bd  sub     ebx, 6
0x18001c1c0  jz      short loc_18001C1FE
0x18001c1c2  cmp     ebx, 1
0x18001c1c5  jnz     loc_18001C851
0x18001c1cb  mov     [rsp+80h+var_48], r14
0x18001c1d0  lea     r9, aActivehourssta; "ActiveHoursStart"
0x18001c1d7  mov     [rsp+80h+var_50], 17h
0x18001c1df  mov     dword ptr [rsp+80h+var_58], r13d
0x18001c1e4  mov     dword ptr [rsp+80h+var_60], 8
0x18001c1ec  mov     r8, r12
0x18001c1ef  lea     rdx, aSetactivehours_0; "SetActiveHours"
0x18001c1f6  mov     rcx, r12
0x18001c1f9  jmp     loc_18001C0C9
0x18001c1fe  lea     rdx, aSetactivehours_0; "SetActiveHours"
0x18001c205  jmp     loc_18001C844
0x18001c20a  lea     r9, [rbp+var_3C]; int *
0x18001c20e  mov     rcx, r15; lpSubKey
0x18001c211  lea     r8, [rbp+var_40]; enum tagUpdatePolicyStatus *
0x18001c215  lea     rdx, aUsewuserver; "UseWUServer"
0x18001c21c  call    ?ReadGPPolicyStateHelper@UpdatePolicyReader@@CAJPEB_W0PEAW4tagUpdatePolicyStatus@@PEAH@Z; UpdatePolicyReader::ReadGPPolicyStateHelper(wchar_t const *,wchar_t const *,tagUpdatePolicyStatus *,int *)
0x18001c221  mov     esi, eax
0x18001c223  test    eax, eax
0x18001c225  js      loc_18001C851
0x18001c22b  cmp     [rbp+var_40], 1
0x18001c22f  jnz     loc_18001C851
0x18001c235  cmp     [rbp+var_3C], r13d
0x18001c239  jz      loc_18001C851
0x18001c23f  lea     rdx, aAccepttrustedp; "AcceptTrustedPublisherCerts"
0x18001c246  jmp     loc_18001C844
0x18001c24b  lea     r9, [rbp+var_3C]; int *
0x18001c24f  mov     rcx, r15; lpSubKey
0x18001c252  lea     r8, [rbp+var_40]; enum tagUpdatePolicyStatus *
0x18001c256  lea     rdx, aUsewuserver; "UseWUServer"
0x18001c25d  call    ?ReadGPPolicyStateHelper@UpdatePolicyReader@@CAJPEB_W0PEAW4tagUpdatePolicyStatus@@PEAH@Z; UpdatePolicyReader::ReadGPPolicyStateHelper(wchar_t const *,wchar_t const *,tagUpdatePolicyStatus *,int *)
0x18001c262  mov     esi, eax
0x18001c264  test    eax, eax
0x18001c266  js      loc_18001C851
0x18001c26c  cmp     [rbp+var_40], 1
0x18001c270  jnz     loc_18001C851
0x18001c276  cmp     [rbp+var_3C], r13d
0x18001c27a  jz      loc_18001C851
0x18001c280  mov     r8, r14; struct tagUpdatePolicyValue_V1 *
0x18001c283  lea     rdx, aDonotconnectto; "DoNotConnectToWindowsUpdateInternetLoca"...
0x18001c28a  mov     rcx, r12; wchar_t *
0x18001c28d  call    ?ReadGPPolicyStateOnly@UpdatePolicyReader@@CAJPEB_W0PEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadGPPolicyStateOnly(wchar_t const *,wchar_t const *,tagUpdatePolicyValue_V1 *)
0x18001c292  mov     esi, eax
0x18001c294  test    eax, eax
0x18001c296  js      loc_18001C851
0x18001c29c  cmp     dword ptr [r14+4], 1
0x18001c2a1  jnz     short loc_18001C2B8
0x18001c2a3  cmp     dword ptr [r14+18h], 1
0x18001c2a8  mov     eax, r13d
0x18001c2ab  setnz   al
0x18001c2ae  mov     [r14+18h], eax
0x18001c2b2  jz      loc_18001C851
0x18001c2b8  lea     r8, [rbp+var_38]; struct tagUpdatePolicyValue_V1 *
0x18001c2bc  mov     rcx, r12; wchar_t *
0x18001c2bf  lea     rdx, aDisablewindows; "DisableWindowsUpdateAccess"
0x18001c2c6  call    ?ReadGPPolicyStateOnly@UpdatePolicyReader@@CAJPEB_W0PEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadGPPolicyStateOnly(wchar_t const *,wchar_t const *,tagUpdatePolicyValue_V1 *)
0x18001c2cb  mov     esi, eax
0x18001c2cd  test    eax, eax
0x18001c2cf  js      loc_18001C851
0x18001c2d5  cmp     dword ptr [rbp+var_38+4], 1
0x18001c2d9  jnz     loc_18001C851
0x18001c2df  cmp     dword ptr [rbp+pvarg+8], 1
0x18001c2e3  mov     eax, r13d
0x18001c2e6  setnz   al
0x18001c2e9  mov     [r14+18h], eax
0x18001c2ed  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes> `wil::Feature<__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes>::GetImpl(void)'::`2'::impl
0x18001c2f4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes>::__private_IsEnabled(void)
0x18001c2f9  test    al, al
0x18001c2fb  jz      short loc_18001C304
0x18001c2fd  mov     word ptr [r14+10h], 3
0x18001c304  mov     eax, dword ptr [rbp+var_38+8]
0x18001c307  mov     [r14+8], eax
0x18001c30b  mov     dword ptr [r14+4], 1
0x18001c313  jmp     loc_18001C851
0x18001c318  lea     r9, [rbp+var_3C]; int *
0x18001c31c  mov     rcx, r15; lpSubKey
0x18001c31f  lea     r8, [rbp+var_40]; enum tagUpdatePolicyStatus *
0x18001c323  lea     rdx, aUsewuserver; "UseWUServer"
0x18001c32a  call    ?ReadGPPolicyStateHelper@UpdatePolicyReader@@CAJPEB_W0PEAW4tagUpdatePolicyStatus@@PEAH@Z; UpdatePolicyReader::ReadGPPolicyStateHelper(wchar_t const *,wchar_t const *,tagUpdatePolicyStatus *,int *)
0x18001c32f  mov     esi, eax
0x18001c331  test    eax, eax
0x18001c333  js      loc_18001C851
0x18001c339  cmp     [rbp+var_40], 1
0x18001c33d  jnz     loc_18001C851
0x18001c343  cmp     [rbp+var_3C], r13d
0x18001c347  jz      loc_18001C851
0x18001c34d  lea     rdx, aDonotconnectto; "DoNotConnectToWindowsUpdateInternetLoca"...
0x18001c354  jmp     loc_18001C844
0x18001c359  mov     rcx, r15; wchar_t *
0x18001c35c  call    ?GetGPAuOptions@UpdatePolicyReader@@CAKPEB_W@Z; UpdatePolicyReader::GetGPAuOptions(wchar_t const *)
0x18001c361  cmp     eax, 4
0x18001c364  jnz     loc_18001C851
0x18001c36a  lea     r9, [rbp+var_3C]; int *
0x18001c36e  mov     rcx, r15; lpSubKey
0x18001c371  lea     r8, [rbp+var_40]; enum tagUpdatePolicyStatus *
0x18001c375  lea     rdx, aAutomaticmaint; "AutomaticMaintenanceEnabled"
0x18001c37c  call    ?ReadGPPolicyStateHelper@UpdatePolicyReader@@CAJPEB_W0PEAW4tagUpdatePolicyStatus@@PEAH@Z; UpdatePolicyReader::ReadGPPolicyStateHelper(wchar_t const *,wchar_t const *,tagUpdatePolicyStatus *,int *)
0x18001c381  mov     esi, eax
0x18001c383  test    eax, eax
0x18001c385  js      loc_18001C851
0x18001c38b  mov     eax, [rbp+var_40]
0x18001c38e  test    eax, eax
0x18001c390  jz      short loc_18001C3A5
0x18001c392  cmp     eax, 1
0x18001c395  jnz     loc_18001C851
0x18001c39b  cmp     [rbp+var_3C], r13d
0x18001c39f  jnz     loc_18001C851
0x18001c3a5  lea     r9, [rbp+var_3C]; int *
0x18001c3a9  mov     [rbp+var_40], r13d
0x18001c3ad  lea     r8, [rbp+var_40]; enum tagUpdatePolicyStatus *
0x18001c3b1  mov     [rbp+var_3C], r13d
0x18001c3b5  lea     rdx, aReschedulewait; "RescheduleWaitTimeEnabled"
0x18001c3bc  mov     rcx, r15; lpSubKey
0x18001c3bf  call    ?ReadGPPolicyStateHelper@UpdatePolicyReader@@CAJPEB_W0PEAW4tagUpdatePolicyStatus@@PEAH@Z; UpdatePolicyReader::ReadGPPolicyStateHelper(wchar_t const *,wchar_t const *,tagUpdatePolicyStatus *,int *)
0x18001c3c4  mov     esi, eax
0x18001c3c6  test    eax, eax
0x18001c3c8  js      loc_18001C851
0x18001c3ce  cmp     [rbp+var_40], 1
0x18001c3d2  jnz     loc_18001C851
0x18001c3d8  cmp     [rbp+var_3C], r13d
0x18001c3dc  jz      short loc_18001C400
0x18001c3de  mov     r9d, 1
0x18001c3e4  mov     [rsp+80h+var_58], r14
0x18001c3e9  mov     r8d, r9d
0x18001c3ec  mov     dword ptr [rsp+80h+var_60], 3Ch ; '<'
0x18001c3f4  lea     rdx, aReschedulewait_0; "RescheduleWaitTime"
0x18001c3fb  jmp     loc_18001C036
0x18001c400  mov     [r14+18h], r13d
0x18001c404  jmp     loc_18001C0E7
0x18001c409  lea     r9, aWuserver; "WUServer"
0x18001c410  mov     rcx, r15
0x18001c413  lea     rdx, aUsewuserver; "UseWUServer"
0x18001c41a  jmp     loc_18001C089
0x18001c41f  mov     [rsp+80h+var_48], r14
0x18001c424  lea     r9, aActivehoursend; "ActiveHoursEnd"
0x18001c42b  mov     [rsp+80h+var_50], 17h
0x18001c433  mov     dword ptr [rsp+80h+var_58], r13d
0x18001c438  mov     dword ptr [rsp+80h+var_60], 11h
0x18001c440  jmp     loc_18001C1EC
0x18001c445  cmp     ebx, 20h ; ' '
0x18001c448  jg      loc_18001C5D9
0x18001c44e  jz      loc_18001C5AF
0x18001c454  sub     ebx, 19h
0x18001c457  jz      loc_18001C55C
0x18001c45d  sub     ebx, 1
0x18001c460  jz      loc_18001C549
0x18001c466  sub     ebx, 1
0x18001c469  jz      loc_18001C536
0x18001c46f  sub     ebx, 1
0x18001c472  jz      loc_18001C505
0x18001c478  sub     ebx, 1
0x18001c47b  jz      short loc_18001C4DB
  ... truncated ...
```
