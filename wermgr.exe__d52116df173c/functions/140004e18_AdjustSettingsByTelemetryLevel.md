# AdjustSettingsByTelemetryLevel

- ea: `0x140004e18`
- end: `0x14000545b`
- name: `AdjustSettingsByTelemetryLevel`
- size: `1603`
- prototype: `LSTATUS()`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14000e49c`

## callees

- `0x140003224`
- `0x14000470c`
- `0x140004e18`
- `0x140005464`
- `0x140005cec`
- `0x140006814`
- `0x140006d34`
- `0x14000705c`
- `0x1400071d4`
- `0x140007234`
- `0x140008c40`
- `0x14000936c`
- `0x14000daa4`
- `0x140017de4`

## import_xrefs

- `DiagnosticDataSettings!TelGetWerTelemetryMode` at `0x140004f37`
- `DiagnosticDataSettings!TelGetWerTelemetryMode` at `0x140004f37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004e6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004e6f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004e5e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004e5e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140004eb8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140004fde`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400050a8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400052ab`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140004eb8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140004fde`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400050a8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400052ab`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400053c9`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000541d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400053c9`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000541d`
- `wer!WerpHasOobeCompleted` at `0x140004ec6`
- `wer!WerpHasOobeCompleted` at `0x140004ec6`

## string_xrefs

- `0x140005027`: `Failed to read the ring from flight info`
- `0x140005063`: `Incorrect ring value read from flight info`
- `0x1400052c1`: `Failed to read PreviousRing from registry`
- `0x1400052fb`: `Unsupported PreviousRing value read`

## pseudocode

```c
LSTATUS AdjustSettingsByTelemetryLevel()
{
  HKEY *v0; // rax
  LSTATUS v1; // ebx
  LSTATUS result; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx
  int CurrentRing; // ebx
  wil::details *v6; // rcx
  unsigned int v7; // r8d
  int v8; // edi
  const char *v9; // rax
  __int64 v10; // rdx
  wchar_t *v11; // rdx
  int v12; // ecx
  const wchar_t *v13; // rcx
  unsigned __int64 v14; // rax
  const wchar_t *v15; // rdx
  int ValueW; // eax
  int v17; // edx
  int DumpTypeForTelemetryModeAndRing; // esi
  int DumpTypeForTelemetryMode; // eax
  int v20; // edi
  LSTATUS v21; // eax
  LSTATUS v22; // eax
  wil::details *phkResult; // [rsp+20h] [rbp-69h]
  const char *pcbData; // [rsp+30h] [rbp-59h]
  unsigned int Data; // [rsp+40h] [rbp-49h] BYREF
  unsigned int v26; // [rsp+44h] [rbp-45h] BYREF
  int pvData; // [rsp+48h] [rbp-41h] BYREF
  int v28; // [rsp+4Ch] [rbp-3Dh] BYREF
  int v29; // [rsp+50h] [rbp-39h] BYREF
  int v30; // [rsp+54h] [rbp-35h] BYREF
  int v31; // [rsp+58h] [rbp-31h] BYREF
  __int64 v32; // [rsp+60h] [rbp-29h] BYREF
  void *v33; // [rsp+68h] [rbp-21h] BYREF
  char *v34; // [rsp+70h] [rbp-19h]
  _WORD v35[8]; // [rsp+78h] [rbp-11h] BYREF
  void *v36[2]; // [rsp+88h] [rbp-1h] BYREF
  _WORD v37[36]; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+E8h] [rbp+5Fh]
  HKEY hKey; // [rsp+F0h] [rbp+67h] BYREF
  int v40; // [rsp+F8h] [rbp+6Fh] BYREF
  DWORD v41; // [rsp+100h] [rbp+77h] BYREF
  int v42; // [rsp+108h] [rbp+7Fh] BYREF

  hKey = 0;
  v0 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\RecoveryEnvironment", 0, 0x20019u, v0);
  if ( hKey )
    RegCloseKey(hKey);
  if ( !v1 )
    return 0;
  pvData = 0;
  v41 = 4;
  RegGetValueW(
    HKEY_LOCAL_MACHINE,
    L"Software\\Microsoft\\Windows\\Windows Error Reporting",
    L"ChangeDumpTypeByTelemetryLevel",
    0x10u,
    0,
    &pvData,
    &v41);
  v28 = 0;
  result = WerpHasOobeCompleted(&v28);
  if ( result < 0 )
    return result;
  if ( !pvData || !v28 )
    return 0;
  v42 = 0;
  v29 = 0;
  v30 = 0;
  LOBYTE(hKey) = 0;
  result = GetCurrentKernelDumpType(&v42, &v29, &v30, &hKey);
  CurrentRing = result;
  if ( result < 0 )
    return result;
  if ( (_BYTE)hKey )
  {
    if ( !v29 || !v30 )
      return DisableAutoDumpSetting(v4, v3);
    return 0;
  }
  Data = TelGetWerTelemetryMode();
  v7 = *(_DWORD *)Feature_DefaultOptionalToMini__descriptor;
  if ( (*(_DWORD *)Feature_DefaultOptionalToMini__descriptor & 4) == 0 )
  {
    v32 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefaultOptionalToMini>::GetCachedFeatureEnabledState(
             v6,
             &v32);
    v7 = v32;
  }
  LODWORD(hKey) = 0;
  WORD2(hKey) = 3;
  wil::details::ReportUsageToService(
    (__int64)&qword_14002DD00,
    0x29F5803u,
    (v7 >> 10) & 1,
    (v7 >> 11) & 1,
    (__int64)&hKey,
    1u,
    3);
  v8 = -1;
  v26 = -1;
  v41 = 4;
  result = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\Windows Error Reporting",
             L"PreviousTelemetryMode",
             0x10u,
             0,
             &v26,
             &v41);
  if ( (result & 0xFFFFFFFD) == 0 )
  {
    v31 = 0;
    v40 = 0;
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::GetImpl'::`2'::impl) )
    {
      CurrentRing = GetCurrentRing(&v40);
      if ( CurrentRing < 0 )
      {
        v9 = "Failed to read the ring from flight info";
        v10 = 1898;
LABEL_20:
        LODWORD(phkResult) = CurrentRing;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)v10,
          (int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
          "AdjustSettingsByTelemetryLevel",
          phkResult,
          (__int64)v9,
          pcbData);
        return CurrentRing;
      }
      if ( (unsigned int)(v40 - 1) > 1 )
      {
        v9 = "Incorrect ring value read from flight info";
        CurrentRing = -2147024883;
        v10 = 1905;
        goto LABEL_20;
      }
    }
    else
    {
      v41 = 4;
      RegGetValueW(
        HKEY_LOCAL_MACHINE,
        L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug",
        L"SimRetailForDumpEval",
        0x10u,
        0,
        &v31,
        &v41);
    }
    if ( v26 == -1 )
    {
      if ( Data < 2 )
      {
        if ( v42 != 7 )
          goto LABEL_81;
        v11 = L"TelemetryLevelFirstRun";
        goto LABEL_32;
      }
      v4 = Data - 2;
      if ( (unsigned int)v4 > 1 )
        goto LABEL_81;
      if ( v42 == 7 )
      {
        if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::GetImpl'::`2'::impl) )
        {
          v33 = v35;
          v34 = (char *)v35;
          v35[0] = 0;
          v36[0] = v37;
          v36[1] = v37;
          v37[0] = 0;
          if ( (int)UtilGetFlightInfo((__int64)&v33, (__int64)v36) >= 0 )
          {
            v13 = (const wchar_t *)v33;
            v14 = (v34 - (_BYTE *)v33) >> 1;
            v15 = L"Retail";
            if ( v14 >= 6 )
            {
              v8 = v14 > 6;
              v14 = 6;
              goto LABEL_38;
            }
            if ( v14 )
            {
LABEL_38:
              while ( *v13 == *v15 )
              {
                ++v13;
                ++v15;
                if ( !--v14 )
                  goto LABEL_42;
              }
              v8 = *v13 < *v15 ? -1 : 1;
            }
LABEL_42:
            if ( v8 && v31 != 1 )
            {
              CurrentRing = DisableAutoDumpSetting(v13, v15);
              if ( v36[0] != v37 )
                operator delete(v36[0], (const struct std::nothrow_t *)&std::nothrow);
              if ( v33 != v35 )
                operator delete(v33, (const struct std::nothrow_t *)&std::nothrow);
              return CurrentRing;
            }
            CurrentRing = ChangeKernelDumpType(3, (int *)L"Retail");
          }
          if ( v36[0] != v37 )
            operator delete(v36[0], (const struct std::nothrow_t *)&std::nothrow);
          if ( v33 != v35 )
            operator delete(v33, (const struct std::nothrow_t *)&std::nothrow);
          goto LABEL_81;
        }
        if ( v40 == 1 )
        {
          v11 = L"Retail";
LABEL_32:
          v12 = 3;
LABEL_80:
          CurrentRing = ChangeKernelDumpType(v12, (int *)v11);
LABEL_81:
          v21 = RegSetKeyValueW(
                  HKEY_LOCAL_MACHINE,
                  L"Software\\Microsoft\\Windows\\Windows Error Reporting",
                  L"PreviousTelemetryMode",
                  4u,
                  &Data,
                  4u);
          if ( CurrentRing >= 0 && v21 )
          {
            if ( v21 > 0 )
              CurrentRing = (unsigned __int16)v21 | 0x80070000;
            else
              CurrentRing = v21;
          }
          if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::GetImpl'::`2'::impl) )
          {
            v22 = RegSetKeyValueW(
                    HKEY_LOCAL_MACHINE,
                    L"Software\\Microsoft\\Windows\\Windows Error Reporting",
                    L"PreviousRing",
                    4u,
                    &v40,
                    4u);
            if ( CurrentRing >= 0 )
            {
              if ( v22 )
              {
                if ( v22 > 0 )
                  return (unsigned __int16)v22 | 0x80070000;
                else
                  return v22;
              }
            }
          }
          return CurrentRing;
        }
      }
      else if ( v42 != 3 )
      {
        goto LABEL_81;
      }
      return DisableAutoDumpSetting(v4, v3);
    }
    LODWORD(hKey) = 0;
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::GetImpl'::`2'::impl) )
    {
      v41 = 4;
      ValueW = RegGetValueW(
                 HKEY_LOCAL_MACHINE,
                 L"Software\\Microsoft\\Windows\\Windows Error Reporting",
                 L"PreviousRing",
                 0x10u,
                 0,
                 &hKey,
                 &v41);
      if ( ValueW )
      {
        if ( ValueW > 0 )
          ValueW = (unsigned __int16)ValueW | 0x80070000;
        LODWORD(phkResult) = ValueW;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)0x7E6,
          (int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
          "AdjustSettingsByTelemetryLevel",
          phkResult,
          (__int64)"Failed to read PreviousRing from registry",
          pcbData);
        v17 = v40;
        LODWORD(hKey) = v40;
      }
      else
      {
        v17 = (int)hKey;
      }
      if ( (unsigned int)(v17 - 1) > 1 )
      {
        v9 = "Unsupported PreviousRing value read";
        CurrentRing = -2147024883;
        v10 = 2029;
        goto LABEL_20;
      }
      DumpTypeForTelemetryModeAndRing = GetDumpTypeForTelemetryModeAndRing(v26);
      DumpTypeForTelemetryMode = GetDumpTypeForTelemetryModeAndRing(Data);
    }
    else
    {
      DumpTypeForTelemetryModeAndRing = GetDumpTypeForTelemetryMode(v26);
      DumpTypeForTelemetryMode = GetDumpTypeForTelemetryMode(Data);
    }
    v20 = DumpTypeForTelemetryMode;
    if ( v42 != DumpTypeForTelemetryModeAndRing )
      return DisableAutoDumpSetting(v4, v3);
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::GetImpl'::`2'::impl) )
    {
      if ( Data == v26 && v40 == (_DWORD)hKey || v42 == v20 )
        goto LABEL_81;
      if ( v40 != (_DWORD)hKey )
      {
        v11 = L"RingAndTelemetryLevelChanged";
        if ( Data == v26 )
          v11 = L"RingChanged";
        goto LABEL_79;
      }
    }
    else if ( Data == v26 || v42 == v20 )
    {
      goto LABEL_81;
    }
    v11 = L"TelemetryLevelChanged";
LABEL_79:
    v12 = v20;
    goto LABEL_80;
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140004e18  push    rbp
0x140004e1a  push    rbx
0x140004e1b  push    rsi
0x140004e1c  push    rdi
0x140004e1d  push    r12
0x140004e1f  push    r14
0x140004e21  push    r15
0x140004e23  lea     rbp, [rsp-27h]
0x140004e28  sub     rsp, 0B0h
0x140004e2f  xor     r15d, r15d
0x140004e32  mov     [rbp+57h+hKey], r15
0x140004e36  lea     rcx, [rbp+57h+hKey]
0x140004e3a  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140004e3f  mov     [rsp+0E0h+phkResult], rax; phkResult
0x140004e44  mov     r9d, 20019h; samDesired
0x140004e4a  xor     r8d, r8d; ulOptions
0x140004e4d  lea     rdx, SubKey; "Software\\Microsoft\\RecoveryEnvironmen"...
0x140004e54  mov     r14, 0FFFFFFFF80000002h
0x140004e5b  mov     rcx, r14; hKey
0x140004e5e  call    cs:__imp_RegOpenKeyExW
0x140004e64  mov     ebx, eax
0x140004e66  mov     rcx, [rbp+57h+hKey]; hKey
0x140004e6a  test    rcx, rcx
0x140004e6d  jz      short loc_140004E75
0x140004e6f  call    cs:__imp_RegCloseKey
0x140004e75  test    ebx, ebx
0x140004e77  jz      loc_140005447
0x140004e7d  mov     [rbp+57h+var_98], r15d
0x140004e81  mov     r12d, 4
0x140004e87  mov     [rbp+57h+arg_10], r12d
0x140004e8b  lea     rax, [rbp+57h+arg_10]
0x140004e8f  mov     [rsp+0E0h+pcbData], rax; pcbData
0x140004e94  lea     rax, [rbp+57h+var_98]
0x140004e98  mov     [rsp+0E0h+pvData], rax; pvData
0x140004e9d  mov     [rsp+0E0h+phkResult], r15; pdwType
0x140004ea2  lea     r9d, [r12+0Ch]; dwFlags
0x140004ea7  lea     r8, Value; "ChangeDumpTypeByTelemetryLevel"
0x140004eae  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\Windows E"...
0x140004eb5  mov     rcx, r14; hkey
0x140004eb8  call    cs:__imp_RegGetValueW
0x140004ebe  mov     [rbp+57h+var_94], r15d
0x140004ec2  lea     rcx, [rbp+57h+var_94]
0x140004ec6  call    cs:__imp_WerpHasOobeCompleted
0x140004ecc  test    eax, eax
0x140004ece  js      loc_140005449
0x140004ed4  cmp     [rbp+57h+var_98], r15d
0x140004ed8  jz      loc_140005447
0x140004ede  cmp     [rbp+57h+var_94], r15d
0x140004ee2  jz      loc_140005447
0x140004ee8  mov     [rbp+57h+arg_18], r15d
0x140004eec  mov     [rbp+57h+var_90], r15d
0x140004ef0  mov     [rbp+57h+var_8C], r15d
0x140004ef4  mov     byte ptr [rbp+57h+hKey], r15b
0x140004ef8  lea     r9, [rbp+57h+hKey]
0x140004efc  lea     r8, [rbp+57h+var_8C]; PVOID
0x140004f00  lea     rdx, [rbp+57h+var_90]; PVOID
0x140004f04  lea     rcx, [rbp+57h+arg_18]; pvData
0x140004f08  call    GetCurrentKernelDumpType
0x140004f0d  mov     ebx, eax
0x140004f0f  test    eax, eax
0x140004f11  js      loc_140005449
0x140004f17  cmp     byte ptr [rbp+57h+hKey], r15b
0x140004f1b  jz      short loc_140004F37
0x140004f1d  cmp     [rbp+57h+var_90], r15d
0x140004f21  jbe     short loc_140004F2D
0x140004f23  cmp     [rbp+57h+var_8C], r15d
0x140004f27  ja      loc_140005447
0x140004f2d  call    DisableAutoDumpSetting
0x140004f32  jmp     loc_140005449
0x140004f37  call    cs:__imp_TelGetWerTelemetryMode
0x140004f3d  mov     [rbp+57h+Data], eax
0x140004f40  mov     rax, cs:Feature_DefaultOptionalToMini__descriptor
0x140004f47  mov     r8d, [rax]
0x140004f4a  test    r12b, r8b
0x140004f4d  jnz     short loc_140004F62
0x140004f4f  lea     rdx, [rbp+57h+var_80]
0x140004f53  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_DefaultOptionalToMini@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefaultOptionalToMini>::GetCachedFeatureEnabledState(void)
0x140004f58  mov     rcx, [rax]
0x140004f5b  mov     [rbp+57h+var_80], rcx
0x140004f5f  mov     r8d, ecx
0x140004f62  mov     dword ptr [rbp+57h+hKey], r15d
0x140004f66  mov     word ptr [rbp+57h+hKey+4], 3
0x140004f6c  mov     r9d, r8d
0x140004f6f  shr     r9d, 0Bh
0x140004f73  mov     esi, 1
0x140004f78  and     r9d, esi
0x140004f7b  shr     r8d, 0Ah
0x140004f7f  and     r8d, esi
0x140004f82  mov     dword ptr [rsp+0E0h+pcbData], 3
0x140004f8a  mov     dword ptr [rsp+0E0h+pvData], esi
0x140004f8e  lea     rax, [rbp+57h+hKey]
0x140004f92  mov     [rsp+0E0h+phkResult], rax
0x140004f97  mov     edx, 29F5803h
0x140004f9c  lea     rcx, qword_14002DD00
0x140004fa3  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x140004fa8  or      edi, 0FFFFFFFFh
0x140004fab  mov     [rbp+57h+var_9C], edi
0x140004fae  mov     [rbp+57h+arg_10], r12d
0x140004fb2  lea     rax, [rbp+57h+arg_10]
0x140004fb6  mov     [rsp+0E0h+pcbData], rax; char *
0x140004fbb  lea     rax, [rbp+57h+var_9C]
0x140004fbf  mov     [rsp+0E0h+pvData], rax; pvData
0x140004fc4  mov     [rsp+0E0h+phkResult], r15; pdwType
0x140004fc9  lea     r9d, [rsi+0Fh]; dwFlags
0x140004fcd  lea     r8, ValueName; "PreviousTelemetryMode"
0x140004fd4  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\Windows E"...
0x140004fdb  mov     rcx, r14; hkey
0x140004fde  call    cs:__imp_RegGetValueW
0x140004fe4  test    eax, 0FFFFFFFDh
0x140004fe9  jz      short loc_140005000
0x140004feb  test    eax, eax
0x140004fed  jle     loc_140005449
0x140004ff3  movzx   eax, ax
0x140004ff6  or      eax, 80070000h
0x140004ffb  jmp     loc_140005449
0x140005000  mov     [rbp+57h+var_88], r15d
0x140005004  mov     [rbp+57h+arg_8], r15d
0x140005008  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WerMgrFixInsiderChange@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WerMgrFixInsiderChange@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerMgrFixInsiderChange> `wil::Feature<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::GetImpl(void)'::`2'::impl
0x14000500f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WerMgrFixInsiderChange@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::__private_IsEnabled(void)
0x140005014  test    al, al
0x140005016  jz      short loc_140005076
0x140005018  lea     rcx, [rbp+57h+arg_8]
0x14000501c  call    GetCurrentRing
0x140005021  mov     ebx, eax
0x140005023  test    eax, eax
0x140005025  jns     short loc_14000505A
0x140005027  lea     rax, aFailedToReadTh; "Failed to read the ring from flight inf"...
0x14000502e  mov     edx, 76Ah; void *
0x140005033  mov     [rsp+0E0h+pvData], rax; int
0x140005038  mov     rcx, [rbp+5Fh]; this
0x14000503c  mov     dword ptr [rsp+0E0h+phkResult], ebx; wil::details *
0x140005040  lea     r9, aAdjustsettings; "AdjustSettingsByTelemetryLevel"
0x140005047  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x14000504e  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140005053  mov     eax, ebx
0x140005055  jmp     loc_140005449
0x14000505a  mov     eax, [rbp+57h+arg_8]
0x14000505d  dec     eax
0x14000505f  cmp     eax, esi
0x140005061  jbe     short loc_1400050AE
0x140005063  lea     rax, aIncorrectRingV; "Incorrect ring value read from flight i"...
0x14000506a  mov     ebx, 8007000Dh
0x14000506f  mov     edx, 771h
0x140005074  jmp     short loc_140005033
0x140005076  mov     [rbp+57h+arg_10], r12d
0x14000507a  lea     rax, [rbp+57h+arg_10]
0x14000507e  mov     [rsp+0E0h+pcbData], rax; pcbData
0x140005083  lea     rax, [rbp+57h+var_88]
0x140005087  mov     [rsp+0E0h+pvData], rax; pvData
0x14000508c  mov     [rsp+0E0h+phkResult], r15; pdwType
0x140005091  mov     r9d, 10h; dwFlags
0x140005097  lea     r8, aSimretailfordu; "SimRetailForDumpEval"
0x14000509e  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\Windows E"...
0x1400050a5  mov     rcx, r14; hkey
0x1400050a8  call    cs:__imp_RegGetValueW
0x1400050ae  mov     r14d, 80070000h
0x1400050b4  cmp     [rbp+57h+var_9C], edi
0x1400050b7  jnz     loc_14000525D
0x1400050bd  mov     ecx, [rbp+57h+Data]
0x1400050c0  test    ecx, ecx
0x1400050c2  jz      loc_140005247
0x1400050c8  sub     ecx, esi
0x1400050ca  jz      loc_140005247
0x1400050d0  sub     ecx, esi
0x1400050d2  jz      short loc_1400050DC
0x1400050d4  cmp     ecx, esi
0x1400050d6  jnz     loc_1400053A3
0x1400050dc  cmp     [rbp+57h+arg_18], 7
0x1400050e0  jnz     loc_140005238
0x1400050e6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WerMgrFixInsiderChange@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WerMgrFixInsiderChange@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerMgrFixInsiderChange> `wil::Feature<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::GetImpl(void)'::`2'::impl
0x1400050ed  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WerMgrFixInsiderChange@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::__private_IsEnabled(void)
0x1400050f2  test    al, al
0x1400050f4  jz      short loc_140005110
0x1400050f6  cmp     [rbp+57h+arg_8], esi
0x1400050f9  jnz     loc_140004F2D
0x1400050ff  lea     rdx, aRetail; "Retail"
0x140005106  mov     ecx, 3
0x14000510b  jmp     loc_14000539C
0x140005110  lea     rax, [rbp+57h+var_68]
0x140005114  mov     [rbp+57h+var_78], rax
0x140005118  lea     rax, [rbp+57h+var_68]
0x14000511c  mov     [rbp+57h+var_70], rax
0x140005120  mov     [rbp+57h+var_68], r15w
0x140005125  lea     rax, [rbp+57h+var_48]
0x140005129  mov     [rbp+57h+var_58], rax
0x14000512d  lea     rax, [rbp+57h+var_48]
0x140005131  mov     [rbp+57h+var_50], rax
0x140005135  mov     [rbp+57h+var_48], r15w
0x14000513a  lea     rdx, [rbp+57h+var_58]
0x14000513e  lea     rcx, [rbp+57h+var_78]
0x140005142  call    ?UtilGetFlightInfo@@YAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@0@Z; UtilGetFlightInfo(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x140005147  test    eax, eax
0x140005149  js      loc_1400051FC
0x14000514f  mov     rax, [rbp+57h+var_70]
0x140005153  mov     rcx, [rbp+57h+var_78]
0x140005157  sub     rax, rcx
0x14000515a  sar     rax, 1
0x14000515d  lea     rdx, aRetail; "Retail"
0x140005164  cmp     rax, 6
0x140005168  jnb     short loc_140005171
0x14000516a  test    rax, rax
0x14000516d  jz      short loc_14000519D
0x14000516f  jmp     short loc_14000517D
0x140005171  mov     edi, r15d
0x140005174  setnbe  dil
0x140005178  mov     eax, 6
0x14000517d  movzx   r8d, word ptr [rcx]
0x140005181  cmp     r8w, [rdx]
0x140005185  jnz     short loc_140005196
0x140005187  add     rcx, 2
0x14000518b  add     rdx, 2
0x14000518f  sub     rax, rsi
0x140005192  jnz     short loc_14000517D
0x140005194  jmp     short loc_14000519D
0x140005196  sbb     edi, edi
0x140005198  and     edi, 0FFFFFFFEh
0x14000519b  add     edi, esi
0x14000519d  test    edi, edi
0x14000519f  jz      short loc_1400051E9
0x1400051a1  cmp     [rbp+57h+var_88], esi
0x1400051a4  jz      short loc_1400051E9
0x1400051a6  call    DisableAutoDumpSetting
0x1400051ab  mov     ebx, eax
0x1400051ad  lea     rax, [rbp+57h+var_48]
0x1400051b1  mov     rcx, [rbp+57h+var_58]; void *
0x1400051b5  cmp     rcx, rax
0x1400051b8  jz      short loc_1400051C7
0x1400051ba  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400051c1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400051c6  nop
0x1400051c7  lea     rax, [rbp+57h+var_68]
0x1400051cb  mov     rcx, [rbp+57h+var_78]; void *
0x1400051cf  cmp     rcx, rax
0x1400051d2  jz      loc_140005053
0x1400051d8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400051df  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400051e4  jmp     loc_140005053
0x1400051e9  lea     rdx, aRetail; "Retail"
0x1400051f0  mov     ecx, 3
0x1400051f5  call    ChangeKernelDumpType
0x1400051fa  mov     ebx, eax
0x1400051fc  lea     rax, [rbp+57h+var_48]
0x140005200  mov     rcx, [rbp+57h+var_58]; void *
0x140005204  cmp     rcx, rax
0x140005207  jz      short loc_140005216
0x140005209  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140005210  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140005215  nop
0x140005216  lea     rax, [rbp+57h+var_68]
0x14000521a  mov     rcx, [rbp+57h+var_78]; void *
0x14000521e  cmp     rcx, rax
0x140005221  jz      loc_1400053A3
0x140005227  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000522e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140005233  jmp     loc_1400053A3
0x140005238  cmp     [rbp+57h+arg_18], 3
0x14000523c  jnz     loc_1400053A3
0x140005242  jmp     loc_140004F2D
0x140005247  cmp     [rbp+57h+arg_18], 7
0x14000524b  jnz     loc_1400053A3
0x140005251  lea     rdx, aTelemetrylevel; "TelemetryLevelFirstRun"
0x140005258  jmp     loc_140005106
0x14000525d  mov     dword ptr [rbp+57h+hKey], r15d
0x140005261  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WerMgrFixInsiderChange@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WerMgrFixInsiderChange@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerMgrFixInsiderChange> `wil::Feature<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::GetImpl(void)'::`2'::impl
0x140005268  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WerMgrFixInsiderChange@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::__private_IsEnabled(void)
0x14000526d  test    al, al
0x14000526f  jz      loc_140005328
0x140005275  mov     [rbp+57h+arg_10], r12d
0x140005279  lea     rax, [rbp+57h+arg_10]
0x14000527d  mov     [rsp+0E0h+pcbData], rax; char *
0x140005282  lea     rax, [rbp+57h+hKey]
0x140005286  mov     [rsp+0E0h+pvData], rax; pvData
0x14000528b  mov     [rsp+0E0h+phkResult], r15; pdwType
0x140005290  mov     r9d, 10h; dwFlags
0x140005296  lea     r8, aPreviousring; "PreviousRing"
0x14000529d  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\Windows E"...
0x1400052a4  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1400052ab  call    cs:__imp_RegGetValueW
0x1400052b1  test    eax, eax
0x1400052b3  jz      short loc_1400052F1
0x1400052b5  jle     short loc_1400052BD
0x1400052b7  movzx   eax, ax
0x1400052ba  or      eax, r14d
0x1400052bd  mov     rcx, [rbp+5Fh]; this
0x1400052c1  lea     rdx, aFailedToReadPr; "Failed to read PreviousRing from regist"...
0x1400052c8  mov     [rsp+0E0h+pvData], rdx; int
0x1400052cd  mov     dword ptr [rsp+0E0h+phkResult], eax; wil::details *
0x1400052d1  lea     r9, aAdjustsettings; "AdjustSettingsByTelemetryLevel"
0x1400052d8  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x1400052df  mov     edx, 7E6h; void *
0x1400052e4  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400052e9  mov     edx, [rbp+57h+arg_8]
0x1400052ec  mov     dword ptr [rbp+57h+hKey], edx
0x1400052ef  jmp     short loc_1400052F4
0x1400052f1  mov     edx, dword ptr [rbp+57h+hKey]
0x1400052f4  lea     eax, [rdx-1]
0x1400052f7  cmp     eax, esi
0x1400052f9  jbe     short loc_140005311
0x1400052fb  lea     rax, aUnsupportedPre; "Unsupported PreviousRing value read"
0x140005302  mov     ebx, 8007000Dh
  ... truncated ...
```
