# UmpoReadFromSystemPowerKey

- ea: `0x18000681c`
- end: `0x18000724b`
- name: `UmpoReadFromSystemPowerKey`
- size: `2607`
- prototype: `__int64 __fastcall(UUID *, UUID *Uuid1, __int64, UUID *, char, unsigned int, DWORD *, unsigned int, BYTE *, LPDWORD lpcbData, int *)`
- caller_count: `14`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004760`
- `0x1800051e0`
- `0x1800058c4`
- `0x1800059c0`
- `0x180005cb4`
- `0x1800061d0`
- `0x180006570`
- `0x1800066b0`
- `0x180007254`
- `0x180008044`
- `0x1800083d0`
- `0x18000b9b8`
- `0x180011190`
- `0x180012fa8`

## callees

- `0x180004e0c`
- `0x180005480`
- `0x1800059c0`
- `0x180006570`
- `0x18000681c`
- `0x180007f70`
- `0x18000ab60`
- `0x18000ac40`
- `0x18000ae50`
- `0x18000b4b0`
- `0x18000b688`
- `0x18000b6cc`
- `0x18000ead4`
- `0x18000f3dc`
- `0x180010070`
- `0x180012864`
- `0x1800188bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180007076`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180007076`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000702d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800070eb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007122`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007159`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800071f0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000702d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800070eb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007122`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007159`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800071f0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006ad0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006bb8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007096`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006ad0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006bb8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007096`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006c1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006d48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006d6a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006dc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006f61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006f83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000723e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006c1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006d48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006d6a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006dc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006f61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006f83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000723e`
- `RPCRT4!UuidEqual` at `0x180006997`
- `RPCRT4!UuidEqual` at `0x180006c4a`
- `RPCRT4!UuidEqual` at `0x180006997`
- `RPCRT4!UuidEqual` at `0x180006c4a`

## pseudocode

```c
__int64 __fastcall UmpoReadFromSystemPowerKey(
        UUID *a1,
        UUID *Uuid1,
        __int64 a3,
        UUID *a4,
        char a5,
        unsigned int a6,
        DWORD *a7,
        unsigned int a8,
        BYTE *a9,
        LPDWORD lpcbData,
        int *a11)
{
  HKEY v13; // r15
  __int64 v14; // rax
  unsigned int v15; // ebx
  HKEY v17; // r14
  int v18; // r12d
  int v19; // eax
  const WCHAR *v20; // rax
  LSTATUS Value; // eax
  UUID *v22; // r14
  LSTATUS v23; // eax
  int v24; // r9d
  char v25; // r15
  char v26; // al
  unsigned int v27; // eax
  LSTATUS v28; // eax
  unsigned int v29; // eax
  bool v30; // zf
  char v31; // r15
  int v32; // edi
  unsigned int v33; // eax
  char v34; // di
  __int64 v35; // rax
  const WCHAR *v36; // r14
  BYTE *v37; // r15
  unsigned int PowerSettingDefaultOverride; // eax
  char IsSettingRangeDefined; // r13
  HKEY v40; // r14
  DWORD *v41; // r13
  unsigned int v42; // ecx
  LPDWORD v43; // rcx
  const WCHAR *v44; // rax
  _BYTE v45[4]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v46; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v48; // [rsp+60h] [rbp-A0h] BYREF
  LPDWORD p_Data1; // [rsp+68h] [rbp-98h]
  __int64 v50; // [rsp+70h] [rbp-90h] BYREF
  LPBYTE lpData; // [rsp+78h] [rbp-88h]
  BYTE v52[4]; // [rsp+80h] [rbp-80h] BYREF
  BYTE Data[4]; // [rsp+84h] [rbp-7Ch] BYREF
  HKEY v54; // [rsp+88h] [rbp-78h] BYREF
  UUID *Uuid2; // [rsp+90h] [rbp-70h]
  UUID *v56; // [rsp+98h] [rbp-68h]
  LPDWORD lpType; // [rsp+A0h] [rbp-60h]
  RPC_STATUS Status; // [rsp+A8h] [rbp-58h] BYREF
  BYTE v59[4]; // [rsp+ACh] [rbp-54h] BYREF
  __int64 v60; // [rsp+B0h] [rbp-50h]
  HKEY v61; // [rsp+B8h] [rbp-48h] BYREF
  HKEY phkResult; // [rsp+C0h] [rbp-40h] BYREF
  int *v63; // [rsp+C8h] [rbp-38h]
  UUID v64; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR v65[16]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR SubKey[40]; // [rsp+100h] [rbp+0h] BYREF

  lpType = a7;
  v13 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  lpData = a9;
  v14 = (__int64)a11;
  Uuid2 = a4;
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v54 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v61 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v63 = a11;
  v60 = a3;
  v56 = Uuid1;
  p_Data1 = lpcbData;
  v45[0] = 0;
  *(_DWORD *)v52 = 0;
  *(_DWORD *)v59 = 0;
  *(_DWORD *)Data = 0;
  v64 = 0;
  Status = 0;
  v46 = 0;
  LODWORD(v50) = 0;
  if ( UmpoFullPowerPlanSupportDisabled && a1 )
  {
    if ( *(_QWORD *)&a1->Data1 != *(_QWORD *)&GUID_TYPICAL_POWER_SAVINGS.Data1
      || *(_QWORD *)a1->Data4 != *(_QWORD *)GUID_TYPICAL_POWER_SAVINGS.Data4 )
    {
      v15 = 50;
      goto LABEL_138;
    }
    v14 = (__int64)v63;
  }
  if ( !lpcbData || v14 && a6 - 7 > 1 )
    return 87;
  if ( a1 )
  {
    if ( a5
      && *(_QWORD *)&a1->Data1 == *(_QWORD *)&GUID_POWER_MODE_NONE.Data1
      && *(_QWORD *)a1->Data4 == *(_QWORD *)GUID_POWER_MODE_NONE.Data4 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      return 87;
    }
    if ( !a4 )
      return 87;
  }
  v17 = UmpoSystemPowerRootKey;
  v15 = 0;
  if ( Uuid1 )
  {
    if ( !UuidEqual(Uuid1, (UUID *)&NO_SUBGROUP_GUID, &Status) )
    {
      v15 = UmpoInternalOpenGUIDSubKey(v17, v56, &v61, 0x20019u, 1, (int *)&UmpoPowerSubGroupCache);
      if ( v15 )
        goto LABEL_138;
      v17 = v61;
    }
    v13 = v54;
  }
  if ( a4 )
  {
    v15 = UmpoInternalOpenGUIDSubKey(v17, a4, &v54, 0x20019u, 1, (int *)&UmpoPowerSettingCache);
    if ( v15 )
      goto LABEL_138;
    v13 = v54;
    v17 = v54;
  }
  v18 = 6;
  if ( a6 <= 0xF )
  {
    v19 = 48652;
    if ( _bittest(&v19, a6) )
    {
      v20 = (const WCHAR *)UmpoInternalDataAccessorToString(a6);
      if ( v20 )
      {
        Value = RegQueryValueExW(v17, v20, 0, lpType, lpData, lpcbData);
LABEL_133:
        v15 = Value;
        goto LABEL_134;
      }
LABEL_32:
      v15 = 87;
      goto LABEL_138;
    }
  }
  if ( a6 - 4 > 2 )
  {
    if ( a6 - 7 > 1 )
      goto LABEL_135;
    v48 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    if ( !a1 || v13 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      goto LABEL_32;
    if ( !v60
      || *(_QWORD *)v60 == *(_QWORD *)&GUID_POWER_POLICY_PROFILE_DEFAULT.Data1
      && *(_QWORD *)(v60 + 8) == *(_QWORD *)GUID_POWER_POLICY_PROFILE_DEFAULT.Data4 )
    {
      v28 = RegOpenKeyExW(v13, L"DefaultPowerSchemeValues", 0, 0x20019u, &hKey);
      v25 = 1;
      p_Data1 = &a1->Data1;
      v15 = v28;
      v22 = a1;
    }
    else
    {
      p_Data1 = &a1->Data1;
      v22 = a1;
      UmpoInternalConvertGuidToStringBuffer(v60, SubKey);
      v23 = RegOpenKeyExW(v13, SubKey, 0, 0x20019u, &hKey);
      v25 = 0;
      v15 = v23;
      if ( v23 == 2 )
      {
        v26 = a5;
        if ( a5 )
        {
LABEL_75:
          v32 = v60;
          if ( !UmpoIsPolicyManagerSupported )
          {
LABEL_79:
            Value = UmpoGetPowerSettingDefaultOverride(
                      (int)v22,
                      (int)v56,
                      v32,
                      (int)Uuid2,
                      a6,
                      (__int64)lpType,
                      lpData,
                      (__int64)lpcbData);
            v18 = 5;
            goto LABEL_133;
          }
          LOBYTE(v24) = v26;
          v33 = UmpoInternalCheckAdvancedSettingOverride(
                  (_DWORD)v56,
                  (_DWORD)Uuid2,
                  (_DWORD)v22,
                  v24,
                  v60,
                  a6,
                  (__int64)&v50);
          v15 = v33;
          if ( v33 )
          {
            if ( v33 != 1168 )
              MicrosoftTelemetryAssertTriggeredNoArgs();
            goto LABEL_79;
          }
          if ( lpData )
          {
            if ( *lpcbData < 4 )
              v15 = 234;
            else
              *(_DWORD *)lpData = v50;
          }
          *lpcbData = 4;
          v18 = 4;
LABEL_134:
          if ( v15 )
            goto LABEL_138;
LABEL_135:
          if ( v63 && a6 - 7 <= 1 )
            *v63 = v18;
          goto LABEL_138;
        }
        v46 = 16;
        if ( a6 == 7 )
        {
          v27 = UmpoReadACValue(
                  0,
                  a1,
                  (UUID *)&NO_SUBGROUP_GUID,
                  0,
                  (__int64)&GUID_POWERSCHEME_PERSONALITY,
                  0,
                  (__int64)&v64,
                  &v46);
        }
        else
        {
          if ( a6 != 8 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          v27 = UmpoInternalReadxCValue(
                  0,
                  a1,
                  (UUID *)&NO_SUBGROUP_GUID,
                  0,
                  (__int64)&GUID_POWERSCHEME_PERSONALITY,
                  0,
                  0,
                  (__int64)&v64,
                  &v46);
        }
        v15 = v27;
        if ( v27 )
          goto LABEL_138;
        v22 = &v64;
LABEL_74:
        v26 = a5;
        goto LABEL_75;
      }
    }
    if ( v15 )
      goto LABEL_138;
    v15 = UmpoInternalOpenGUIDSubKey(hKey, a1, &v48, 0x20019u, 1, 0);
    if ( !v15 )
      goto LABEL_60;
    if ( a5 )
    {
      if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        RegCloseKey(hKey);
        hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
      }
      if ( v15 != 2 )
        goto LABEL_138;
      goto LABEL_74;
    }
    if ( UuidEqual(&GUID_POWERSCHEME_PERSONALITY, Uuid2, &Status)
      || ((v46 = 16, a6 != 7)
        ? (v29 = UmpoInternalReadxCValue(
                   0,
                   a1,
                   (UUID *)&NO_SUBGROUP_GUID,
                   0,
                   (__int64)&GUID_POWERSCHEME_PERSONALITY,
                   0,
                   0,
                   (__int64)&v64,
                   &v46))
        : (v29 = UmpoReadACValue(
                   0,
                   a1,
                   (UUID *)&NO_SUBGROUP_GUID,
                   0,
                   (__int64)&GUID_POWERSCHEME_PERSONALITY,
                   0,
                   (__int64)&v64,
                   &v46)),
          (v15 = v29) != 0) )
    {
      v22 = (UUID *)p_Data1;
    }
    else
    {
      v22 = &v64;
      p_Data1 = (LPDWORD)&v64;
      v15 = UmpoInternalOpenGUIDSubKey(hKey, &v64, &v48, 0x20019u, 1, 0);
      if ( !v15 )
      {
LABEL_60:
        v30 = v25 == 0;
        v31 = a5;
        if ( v30 && !a5 && memcmp_0(v22, &GUID_TYPICAL_POWER_SAVINGS, 0x10u) )
        {
          v15 = 50;
          if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            RegCloseKey(hKey);
            hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
          }
          if ( (unsigned __int64)v48 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
            RegCloseKey(v48);
          goto LABEL_138;
        }
        goto LABEL_86;
      }
    }
    if ( !v25 || (v15 = UmpoInternalOpenGUIDSubKey(hKey, &GUID_TYPICAL_POWER_SAVINGS, &v48, 0x20019u, 1, 0)) != 0 )
    {
      if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        RegCloseKey(hKey);
        hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
      }
      if ( !v25 || v15 != 2 )
        goto LABEL_138;
      goto LABEL_74;
    }
    v31 = 0;
LABEL_86:
    v15 = UmpoInternalCheckDefaultOverride(v48, a6, v45);
    if ( v15 )
    {
LABEL_97:
      if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        RegCloseKey(hKey);
        hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
      }
      if ( (unsigned __int64)v48 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        RegCloseKey(v48);
      goto LABEL_134;
    }
    v34 = v45[0];
    if ( v45[0] )
    {
      v35 = (__int64)UmpoInternalDataAccessorToDefaultOverrideString(a6);
      v18 = 2;
    }
    else
    {
      v15 = UmpoInternalCheckDefaultProvisioningOrPolicyManager(
              v48,
              (__int64)v22,
              v31,
              v60,
              (__int64)&v50,
              (__int64)v45);
      if ( v15 )
      {
LABEL_109:
        v15 = 87;
        goto LABEL_97;
      }
      v34 = v45[0];
      if ( v45[0] )
      {
        if ( UmpoIsPolicyManagerSupported )
        {
          if ( lpData )
          {
            if ( *lpcbData < 4 )
              v15 = 234;
            else
              *(_DWORD *)lpData = v50;
          }
          v18 = 4;
          *lpcbData = 4;
          goto LABEL_97;
        }
        v35 = (__int64)UmpoInternalDataAccessorToDefaultProvString(a6);
        v18 = 3;
      }
      else
      {
        v35 = UmpoInternalDataAccessorToString(a6);
      }
    }
    v36 = (const WCHAR *)v35;
    if ( v35 )
    {
      v37 = lpData;
      if ( v34
        || (v46 = *lpcbData,
            PowerSettingDefaultOverride = UmpoGetPowerSettingDefaultOverride(
                                            (int)p_Data1,
                                            (int)v56,
                                            v60,
                                            (int)Uuid2,
                                            a6,
                                            (__int64)lpType,
                                            lpData,
                                            (__int64)&v46),
            (v15 = PowerSettingDefaultOverride) != 0)
        && PowerSettingDefaultOverride != 234 )
      {
        v15 = RegQueryValueExW(v48, v36, 0, lpType, v37, lpcbData);
      }
      else
      {
        v18 = 5;
        *lpcbData = v46;
      }
      goto LABEL_97;
    }
    goto LABEL_109;
  }
  IsSettingRangeDefined = UmpoInternalIsSettingRangeDefined(v56);
  if ( IsSettingRangeDefined )
  {
    v40 = v54;
  }
  else
  {
    _o__ultow_s(a8, v65, 11, 10);
    v15 = RegOpenKeyExW(v54, v65, 0, 0x20019u, &phkResult);
    if ( v15 )
      goto LABEL_138;
    v40 = phkResult;
  }
  if ( a6 != 4 || !IsSettingRangeDefined )
  {
    v44 = (const WCHAR *)UmpoInternalDataAccessorToString(a6);
    if ( v44 )
    {
      Value = RegQueryValueExW(v40, v44, 0, lpType, lpData, p_Data1);
      goto LABEL_133;
    }
    goto LABEL_32;
  }
  v41 = lpType;
  v46 = 4;
  v15 = RegQueryValueExW(v40, L"ValueMin", 0, lpType, Data, &v46);
  if ( !v15 )
  {
    v46 = 4;
    v15 = RegQueryValueExW(v40, L"ValueMax", 0, v41, v59, &v46);
    if ( !v15 )
    {
      v46 = 4;
      v15 = RegQueryValueExW(v40, L"ValueIncrement", 0, v41, v52, &v46);
      if ( !v15 )
      {
        v42 = *(_DWORD *)v52;
        if ( !*(_DWORD *)v52 )
        {
          v42 = 1;
          *(_DWORD *)v52 = 1;
        }
        if ( a8 > *(_DWORD *)v59 || a8 < *(_DWORD *)Data || (a8 - *(_DWORD *)Data) % v42 )
        {
          v43 = p_Data1;
          v15 = 13;
          goto LABEL_130;
        }
        v43 = p_Data1;
        if ( lpData )
        {
          if ( *p_Data1 < 4 )
          {
            v15 = 234;
            goto LABEL_130;
          }
          *(_DWORD *)lpData = a8;
        }
        v15 = 0;
LABEL_130:
        *v43 = 4;
        goto LABEL_134;
      }
    }
  }
LABEL_138:
  UmpoInternalRegCloseKey((__int64)&UmpoPowerSubGroupCache, v61);
  UmpoInternalRegCloseKey((__int64)&UmpoPowerSettingCache, v54);
  if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(phkResult);
  return v15;
}

```

## disassembly

```asm
0x18000681c  push    rbp
0x18000681e  push    rbx
0x18000681f  push    rsi
0x180006820  push    rdi
0x180006821  push    r12
0x180006823  push    r13
0x180006825  push    r14
0x180006827  push    r15
0x180006829  lea     rbp, [rsp-68h]
0x18000682e  sub     rsp, 168h
0x180006835  mov     rax, cs:__security_cookie
0x18000683c  xor     rax, rsp
0x18000683f  mov     [rbp+0A0h+var_50], rax
0x180006843  mov     rax, [rbp+0A0h+arg_30]
0x18000684a  mov     rdi, rcx
0x18000684d  mov     r13, [rbp+0A0h+arg_48]
0x180006854  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180006858  cmp     cs:UmpoFullPowerPlanSupportDisabled, 0
0x18000685f  xorps   xmm0, xmm0
0x180006862  mov     esi, [rbp+0A0h+arg_28]
0x180006868  mov     r12, r9
0x18000686b  mov     [rbp+0A0h+lpType], rax
0x18000686f  mov     r15, rcx
0x180006872  mov     rax, [rbp+0A0h+arg_40]
0x180006879  mov     [rsp+1A0h+lpData], rax
0x18000687e  mov     rax, [rbp+0A0h+arg_50]
0x180006885  mov     [rbp+0A0h+Uuid2], r9
0x180006889  mov     r9, rdx
0x18000688c  mov     [rbp+0A0h+var_E0], rcx
0x180006890  mov     [rbp+0A0h+var_118], rcx
0x180006894  mov     [rbp+0A0h+var_E8], rcx
0x180006898  lea     rcx, UmpoPowerSettingCache
0x18000689f  mov     [rbp+0A0h+var_D8], rax
0x1800068a3  mov     [rbp+0A0h+var_F0], r8
0x1800068a7  mov     [rbp+0A0h+var_108], rdx
0x1800068ab  mov     [rsp+1A0h+var_138], r13
0x1800068b0  mov     byte ptr [rsp+1A0h+var_150], 0
0x1800068b5  mov     dword ptr [rbp+0A0h+var_120], 0
0x1800068bc  mov     dword ptr [rbp+0A0h+var_F4], 0
0x1800068c3  mov     dword ptr [rbp+0A0h+Data], 0
0x1800068ca  movups  xmmword ptr [rbp+0A0h+var_D0.Data1], xmm0
0x1800068ce  mov     [rbp+0A0h+Status], 0
0x1800068d5  mov     dword ptr [rsp+1A0h+var_150+4], 0
0x1800068dd  mov     dword ptr [rsp+1A0h+var_130], 0
0x1800068e5  jz      short loc_180006913
0x1800068e7  test    rdi, rdi
0x1800068ea  jz      short loc_180006913
0x1800068ec  mov     rax, [rdi]
0x1800068ef  cmp     rax, qword ptr cs:GUID_TYPICAL_POWER_SAVINGS.Data1
0x1800068f6  jnz     short loc_180006905
0x1800068f8  mov     rax, [rdi+8]
0x1800068fc  cmp     rax, qword ptr cs:GUID_TYPICAL_POWER_SAVINGS.Data4
0x180006903  jz      short loc_18000690F
0x180006905  mov     ebx, 32h ; '2'
0x18000690a  jmp     loc_180007210
0x18000690f  mov     rax, [rbp+0A0h+var_D8]
0x180006913  test    r13, r13
0x180006916  jz      short loc_180006951
0x180006918  test    rax, rax
0x18000691b  jz      short loc_180006925
0x18000691d  lea     eax, [rsi-7]
0x180006920  cmp     eax, 1
0x180006923  ja      short loc_180006951
0x180006925  test    rdi, rdi
0x180006928  jz      short loc_18000697B
0x18000692a  cmp     [rbp+0A0h+arg_20], 0
0x180006931  jz      short loc_180006976
0x180006933  mov     rax, [rdi]
0x180006936  cmp     rax, qword ptr cs:GUID_POWER_MODE_NONE.Data1
0x18000693d  jnz     short loc_180006976
0x18000693f  mov     rax, [rdi+8]
0x180006943  cmp     rax, qword ptr cs:GUID_POWER_MODE_NONE.Data4
0x18000694a  jnz     short loc_180006976
0x18000694c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180006951  mov     eax, 57h ; 'W'
0x180006956  mov     rcx, [rbp+0A0h+var_50]
0x18000695a  xor     rcx, rsp; StackCookie
0x18000695d  call    __security_check_cookie
0x180006962  add     rsp, 168h
0x180006969  pop     r15
0x18000696b  pop     r14
0x18000696d  pop     r13
0x18000696f  pop     r12
0x180006971  pop     rdi
0x180006972  pop     rsi
0x180006973  pop     rbx
0x180006974  pop     rbp
0x180006975  retn
0x180006976  test    r12, r12
0x180006979  jz      short loc_180006951
0x18000697b  mov     r14, cs:UmpoSystemPowerRootKey
0x180006982  xor     ebx, ebx
0x180006984  test    r9, r9
0x180006987  jz      short loc_1800069E1
0x180006989  lea     r8, [rbp+0A0h+Status]; Status
0x18000698d  mov     rcx, r9; Uuid1
0x180006990  lea     rdx, NO_SUBGROUP_GUID; Uuid2
0x180006997  call    cs:__imp_UuidEqual
0x18000699d  test    eax, eax
0x18000699f  jnz     short loc_1800069D6
0x1800069a1  mov     rdx, [rbp+0A0h+var_108]; Uuid2
0x1800069a5  lea     rax, UmpoPowerSubGroupCache
0x1800069ac  mov     [rsp+1A0h+lpcbData], rax; __int64
0x1800069b1  lea     r8, [rbp+0A0h+var_E8]; phkResult
0x1800069b5  mov     r9d, 20019h; samDesired
0x1800069bb  mov     byte ptr [rsp+1A0h+phkResult], 1; char
0x1800069c0  mov     rcx, r14; hKey
0x1800069c3  call    UmpoInternalOpenGUIDSubKey
0x1800069c8  mov     ebx, eax
0x1800069ca  test    eax, eax
0x1800069cc  jnz     loc_180007210
0x1800069d2  mov     r14, [rbp+0A0h+var_E8]
0x1800069d6  mov     r15, [rbp+0A0h+var_118]
0x1800069da  lea     rcx, UmpoPowerSettingCache
0x1800069e1  test    r12, r12
0x1800069e4  jz      short loc_180006A16
0x1800069e6  mov     [rsp+1A0h+lpcbData], rcx; __int64
0x1800069eb  lea     r8, [rbp+0A0h+var_118]; phkResult
0x1800069ef  mov     rcx, r14; hKey
0x1800069f2  mov     byte ptr [rsp+1A0h+phkResult], 1; char
0x1800069f7  mov     r9d, 20019h; samDesired
0x1800069fd  mov     rdx, r12; Uuid2
0x180006a00  call    UmpoInternalOpenGUIDSubKey
0x180006a05  mov     ebx, eax
0x180006a07  test    eax, eax
0x180006a09  jnz     loc_180007210
0x180006a0f  mov     r15, [rbp+0A0h+var_118]
0x180006a13  mov     r14, r15
0x180006a16  mov     r12d, 6
0x180006a1c  cmp     esi, 0Fh
0x180006a1f  ja      short loc_180006A41
0x180006a21  mov     eax, 0BE0Ch
0x180006a26  bt      eax, esi
0x180006a29  jnb     short loc_180006A41
0x180006a2b  mov     ecx, esi
0x180006a2d  call    UmpoInternalDataAccessorToString
0x180006a32  test    rax, rax
0x180006a35  jz      short loc_180006A6C
0x180006a37  mov     [rsp+1A0h+lpcbData], r13
0x180006a3c  jmp     loc_1800071D9
0x180006a41  lea     eax, [rsi-4]
0x180006a44  cmp     eax, 2
0x180006a47  jbe     loc_180007044
0x180006a4d  lea     eax, [rsi-7]
0x180006a50  cmp     eax, 1
0x180006a53  ja      loc_1800071FC
0x180006a59  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006a5d  mov     [rsp+1A0h+var_140], rax
0x180006a62  mov     [rsp+1A0h+hKey], rax
0x180006a67  test    rdi, rdi
0x180006a6a  jnz     short loc_180006A76
0x180006a6c  mov     ebx, 57h ; 'W'
0x180006a71  jmp     loc_180007210
0x180006a76  cmp     r15, rax
0x180006a79  jz      short loc_180006A6C
0x180006a7b  mov     rcx, [rbp+0A0h+var_F0]
0x180006a7f  test    rcx, rcx
0x180006a82  jz      loc_180006B9B
0x180006a88  mov     rax, [rcx]
0x180006a8b  cmp     rax, qword ptr cs:GUID_POWER_POLICY_PROFILE_DEFAULT.Data1
0x180006a92  jnz     short loc_180006AA5
0x180006a94  mov     rax, [rcx+8]
0x180006a98  cmp     rax, qword ptr cs:GUID_POWER_POLICY_PROFILE_DEFAULT.Data4
0x180006a9f  jz      loc_180006B9B
0x180006aa5  lea     rdx, [rbp+0A0h+SubKey]
0x180006aa9  mov     [rsp+1A0h+var_138], rdi
0x180006aae  mov     r14, rdi
0x180006ab1  call    UmpoInternalConvertGuidToStringBuffer
0x180006ab6  lea     rdx, [rsp+1A0h+hKey]
0x180006abb  mov     r9d, 20019h; samDesired
0x180006ac1  mov     [rsp+1A0h+phkResult], rdx; phkResult
0x180006ac6  xor     r8d, r8d; ulOptions
0x180006ac9  lea     rdx, [rbp+0A0h+SubKey]; lpSubKey
0x180006acd  mov     rcx, r15; hKey
0x180006ad0  call    cs:__imp_RegOpenKeyExW
0x180006ad6  xor     r15b, r15b
0x180006ad9  mov     ebx, eax
0x180006adb  cmp     eax, 2
0x180006ade  jnz     loc_180006BCB
0x180006ae4  mov     al, [rbp+0A0h+arg_20]
0x180006aea  test    al, al
0x180006aec  jnz     loc_180006DE9
0x180006af2  mov     dword ptr [rsp+1A0h+var_150+4], 10h
0x180006afa  cmp     esi, 7
0x180006afd  jnz     short loc_180006B3D
0x180006aff  lea     rax, [rsp+1A0h+var_150+4]
0x180006b04  xor     r9d, r9d
0x180006b07  mov     [rsp+1A0h+var_168], rax
0x180006b0c  lea     r14, GUID_POWERSCHEME_PERSONALITY
0x180006b13  lea     rax, [rbp+0A0h+var_D0]
0x180006b17  mov     rdx, rdi
0x180006b1a  mov     [rsp+1A0h+Destination], rax
0x180006b1f  lea     r8, NO_SUBGROUP_GUID
0x180006b26  mov     [rsp+1A0h+lpcbData], 0
0x180006b2f  xor     ecx, ecx
0x180006b31  mov     [rsp+1A0h+phkResult], r14
0x180006b36  call    UmpoReadACValue
0x180006b3b  jmp     short loc_180006B88
0x180006b3d  cmp     esi, 8
0x180006b40  jz      short loc_180006B47
0x180006b42  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180006b47  lea     rax, [rsp+1A0h+var_150+4]
0x180006b4c  xor     r9d, r9d
0x180006b4f  mov     [rsp+1A0h+var_160], rax
0x180006b54  lea     r14, GUID_POWERSCHEME_PERSONALITY
0x180006b5b  lea     rax, [rbp+0A0h+var_D0]
0x180006b5f  mov     rdx, rdi
0x180006b62  mov     [rsp+1A0h+var_168], rax
0x180006b67  lea     r8, NO_SUBGROUP_GUID
0x180006b6e  mov     [rsp+1A0h+Destination], 0
0x180006b77  xor     ecx, ecx
0x180006b79  mov     byte ptr [rsp+1A0h+lpcbData], r15b
0x180006b7e  mov     [rsp+1A0h+phkResult], r14
0x180006b83  call    UmpoInternalReadxCValue
0x180006b88  mov     ebx, eax
0x180006b8a  test    eax, eax
0x180006b8c  jnz     loc_180007210
0x180006b92  lea     r14, [rbp+0A0h+var_D0]
0x180006b96  jmp     loc_180006DE3
0x180006b9b  lea     rax, [rsp+1A0h+hKey]
0x180006ba0  mov     r9d, 20019h; samDesired
0x180006ba6  xor     r8d, r8d; ulOptions
0x180006ba9  mov     [rsp+1A0h+phkResult], rax; phkResult
0x180006bae  lea     rdx, aDefaultpowersc; "DefaultPowerSchemeValues"
0x180006bb5  mov     rcx, r15; hKey
0x180006bb8  call    cs:__imp_RegOpenKeyExW
0x180006bbe  mov     r15b, 1
0x180006bc1  mov     [rsp+1A0h+var_138], rdi
0x180006bc6  mov     ebx, eax
0x180006bc8  mov     r14, rdi
0x180006bcb  test    ebx, ebx
0x180006bcd  jnz     loc_180007210
0x180006bd3  mov     rcx, [rsp+1A0h+hKey]; hKey
0x180006bd8  lea     r8, [rsp+1A0h+var_140]; phkResult
0x180006bdd  mov     [rsp+1A0h+lpcbData], 0; __int64
0x180006be6  mov     r9d, 20019h; samDesired
0x180006bec  mov     rdx, rdi; Uuid2
0x180006bef  mov     byte ptr [rsp+1A0h+phkResult], 1; char
0x180006bf4  call    UmpoInternalOpenGUIDSubKey
0x180006bf9  mov     ebx, eax
0x180006bfb  test    eax, eax
0x180006bfd  jz      loc_180006CFE
0x180006c03  cmp     [rbp+0A0h+arg_20], 0
0x180006c0a  jz      short loc_180006C38
0x180006c0c  mov     rcx, [rsp+1A0h+hKey]; hKey
0x180006c11  lea     rax, [rcx-1]
0x180006c15  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180006c19  ja      short loc_180006C2A
0x180006c1b  call    cs:__imp_RegCloseKey
0x180006c21  mov     [rsp+1A0h+hKey], 0FFFFFFFFFFFFFFFFh
0x180006c2a  cmp     ebx, 2
0x180006c2d  jz      loc_180006DE3
0x180006c33  jmp     loc_180007210
0x180006c38  mov     rdx, [rbp+0A0h+Uuid2]; Uuid2
0x180006c3c  lea     r14, GUID_POWERSCHEME_PERSONALITY
0x180006c43  mov     rcx, r14; Uuid1
0x180006c46  lea     r8, [rbp+0A0h+Status]; Status
0x180006c4a  call    cs:__imp_UuidEqual
0x180006c50  test    eax, eax
0x180006c52  jnz     loc_180006D75
0x180006c58  xor     r9d, r9d
0x180006c5b  mov     dword ptr [rsp+1A0h+var_150+4], 10h
0x180006c63  xor     ecx, ecx
0x180006c65  lea     rax, [rsp+1A0h+var_150+4]
0x180006c6a  lea     r8, NO_SUBGROUP_GUID
0x180006c71  mov     rdx, rdi
0x180006c74  cmp     esi, 7
0x180006c77  jnz     short loc_180006C98
0x180006c79  mov     [rsp+1A0h+var_168], rax
0x180006c7e  lea     rax, [rbp+0A0h+var_D0]
0x180006c82  mov     [rsp+1A0h+Destination], rax
0x180006c87  mov     [rsp+1A0h+lpcbData], rcx
0x180006c8c  mov     [rsp+1A0h+phkResult], r14
0x180006c91  call    UmpoReadACValue
0x180006c96  jmp     short loc_180006CBE
0x180006c98  mov     [rsp+1A0h+var_160], rax
0x180006c9d  lea     rax, [rbp+0A0h+var_D0]
0x180006ca1  mov     [rsp+1A0h+var_168], rax
0x180006ca6  mov     [rsp+1A0h+Destination], 0
0x180006caf  mov     byte ptr [rsp+1A0h+lpcbData], 0
0x180006cb4  mov     [rsp+1A0h+phkResult], r14
0x180006cb9  call    UmpoInternalReadxCValue
0x180006cbe  mov     ebx, eax
0x180006cc0  test    eax, eax
0x180006cc2  jnz     loc_180006D75
0x180006cc8  mov     rcx, [rsp+1A0h+hKey]; hKey
0x180006ccd  lea     r14, [rbp+0A0h+var_D0]
0x180006cd1  mov     [rsp+1A0h+lpcbData], 0; __int64
0x180006cda  lea     r8, [rsp+1A0h+var_140]; phkResult
0x180006cdf  mov     r9d, 20019h; samDesired
0x180006ce5  mov     [rsp+1A0h+var_138], r14
0x180006cea  lea     rdx, [rbp+0A0h+var_D0]; Uuid2
0x180006cee  mov     byte ptr [rsp+1A0h+phkResult], 1; char
0x180006cf3  call    UmpoInternalOpenGUIDSubKey
0x180006cf8  mov     ebx, eax
0x180006cfa  test    eax, eax
0x180006cfc  jnz     short loc_180006D7A
0x180006cfe  test    r15b, r15b
0x180006d01  mov     r15b, [rbp+0A0h+arg_20]
0x180006d08  jnz     loc_180006E9E
  ... truncated ...
```
