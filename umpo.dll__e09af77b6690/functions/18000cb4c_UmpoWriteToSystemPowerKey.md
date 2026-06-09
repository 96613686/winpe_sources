# UmpoWriteToSystemPowerKey

- ea: `0x18000cb4c`
- end: `0x18000d078`
- name: `UmpoWriteToSystemPowerKey`
- size: `1324`
- prototype: `__int64 __fastcall(UUID *, UUID *, UUID *, UUID *, unsigned int, DWORD dwType, unsigned int, BYTE *, DWORD cbData)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b9b8`
- `0x180013938`
- `0x180015150`

## callees

- `0x180004e0c`
- `0x180005480`
- `0x180006570`
- `0x18000ab60`
- `0x18000b540`
- `0x18000b6cc`
- `0x18000cb4c`
- `0x18000f3dc`
- `0x180010070`
- `0x1800127cc`
- `0x1800140ac`
- `0x1800188bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x18000cf6b`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x18000cf6b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000cfc6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000cfc6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ce5b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ce5b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000cf26`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000cf26`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cf8b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cf8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cce4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cfdc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cffe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d016`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d031`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d049`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cce4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cfdc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cffe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d016`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d031`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d049`
- `RPCRT4!UuidEqual` at `0x18000cc9d`
- `RPCRT4!UuidEqual` at `0x18000cc9d`

## pseudocode

```c
__int64 __fastcall UmpoWriteToSystemPowerKey(
        UUID *a1,
        UUID *a2,
        UUID *a3,
        UUID *a4,
        unsigned int a5,
        DWORD dwType,
        unsigned int a7,
        BYTE *a8,
        DWORD cbData)
{
  unsigned int IsValidPerformanceSubgroup; // ebx
  int v13; // eax
  HKEY v14; // rsi
  int v15; // eax
  const WCHAR *v16; // rax
  LSTATUS v17; // eax
  UUID *v18; // r14
  char v19; // si
  unsigned int v20; // eax
  char v21; // bl
  const WCHAR *v22; // rax
  HKEY v23; // rbx
  const WCHAR *v24; // rax
  char v26; // [rsp+50h] [rbp-81h] BYREF
  char v27; // [rsp+51h] [rbp-80h]
  HKEY hKey; // [rsp+58h] [rbp-79h] BYREF
  HKEY v29; // [rsp+60h] [rbp-71h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-69h] BYREF
  HKEY v31; // [rsp+70h] [rbp-61h] BYREF
  RPC_STATUS Status; // [rsp+78h] [rbp-59h] BYREF
  DWORD v33; // [rsp+7Ch] [rbp-55h] BYREF
  BYTE *lpData; // [rsp+80h] [rbp-51h]
  HKEY v35; // [rsp+88h] [rbp-49h] BYREF
  UUID *Uuid2; // [rsp+90h] [rbp-41h]
  __int128 Buf2; // [rsp+98h] [rbp-39h] BYREF
  WCHAR SubKey[12]; // [rsp+A8h] [rbp-29h] BYREF

  Uuid2 = a1;
  lpData = a8;
  v27 = 0;
  v29 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v35 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v26 = 0;
  Buf2 = 0;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  Status = 0;
  v33 = 16;
  v31 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  if ( UmpoFullPowerPlanSupportDisabled )
    return 50;
  if ( cbData && a8 && (!a1 || a4) && (!a3 || a4 && a1) && (a5 - 9 > 2 || cbData == 4 && dwType == 4) )
  {
    if ( a5 > 0xD || (v13 = 12396, !_bittest(&v13, a5)) || dwType == 2 )
    {
      v14 = UmpoSystemPowerRootKey;
      if ( (((unsigned __int64)UmpoSystemPowerRootKey + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        v14 = UmpoSystemPowerRootKey;
      }
      if ( a5 == 4 && (unsigned __int8)UmpoInternalIsSettingRangeDefined(a2) )
        goto LABEL_20;
      IsValidPerformanceSubgroup = 0;
      if ( a2 && !UuidEqual(a2, (UUID *)&NO_SUBGROUP_GUID, &Status) )
      {
        IsValidPerformanceSubgroup = UmpoInternalOpenGUIDSubKey(v14, a2, &v31, 0x20006u, 0, 0);
        if ( IsValidPerformanceSubgroup )
          goto LABEL_70;
        v14 = v31;
      }
      if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        RegCloseKey(hKey);
        hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
      }
      if ( a4 )
      {
        IsValidPerformanceSubgroup = UmpoInternalOpenGUIDSubKey(v14, a4, &hKey, 0x2000Eu, 0, 0);
        if ( IsValidPerformanceSubgroup )
          goto LABEL_70;
        v14 = hKey;
      }
      if ( a5 <= 0xF && (v15 = 48652, _bittest(&v15, a5)) )
      {
        v16 = (const WCHAR *)UmpoInternalDataAccessorToString(a5);
        if ( !v16 )
        {
LABEL_20:
          IsValidPerformanceSubgroup = 87;
LABEL_70:
          if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            RegCloseKey(phkResult);
            phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
          }
          if ( (unsigned __int64)v29 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            RegCloseKey(v29);
            v29 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
          }
          if ( (unsigned __int64)v31 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            RegCloseKey(v31);
            v31 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
          }
          if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            RegCloseKey(hKey);
            hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
          }
          if ( (unsigned __int64)v35 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
            RegCloseKey(v35);
          return IsValidPerformanceSubgroup;
        }
        v17 = RegSetValueExW(v14, v16, 0, dwType, lpData, cbData);
      }
      else if ( a5 - 4 <= 2 )
      {
        if ( (unsigned __int8)UmpoInternalIsSettingRangeDefined(a2) )
        {
          v23 = hKey;
        }
        else
        {
          _o__ultow_s(a7, SubKey, 11, 10);
          IsValidPerformanceSubgroup = RegOpenKeyExW(hKey, SubKey, 0, 0x20006u, &v35);
          if ( IsValidPerformanceSubgroup )
            goto LABEL_70;
          v23 = v35;
        }
        v24 = (const WCHAR *)UmpoInternalDataAccessorToString(a5);
        if ( !v24 )
          goto LABEL_20;
        v17 = RegSetValueExW(v23, v24, 0, dwType, lpData, cbData);
      }
      else
      {
        if ( a5 - 7 > 1 )
          goto LABEL_70;
        v18 = Uuid2;
        if ( !Uuid2 )
          goto LABEL_20;
        UmpoInternalIsOverlayPowerScheme(Uuid2, &v26);
        v19 = v26;
        if ( v26 )
        {
          IsValidPerformanceSubgroup = UmpoIsValidPerformanceSubgroup(a2);
          if ( IsValidPerformanceSubgroup )
            goto LABEL_70;
        }
        if ( a3 && !v19 )
        {
          IsValidPerformanceSubgroup = UmpoReadACValue(
                                         0,
                                         v18,
                                         (UUID *)&NO_SUBGROUP_GUID,
                                         0,
                                         (__int64)&GUID_POWERSCHEME_PERSONALITY,
                                         0,
                                         (__int64)&Buf2,
                                         &v33);
          if ( IsValidPerformanceSubgroup )
            goto LABEL_70;
          if ( memcmp_0(&GUID_TYPICAL_POWER_SAVINGS, &Buf2, 0x10u) )
            goto LABEL_20;
        }
        if ( hKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
          goto LABEL_20;
        if ( a3 )
          v20 = UmpoInternalOpenGUIDSubKey(hKey, a3, &phkResult, 0x20006u, cbData == 1, 0);
        else
          v20 = RegCreateKeyExW(hKey, L"DefaultPowerSchemeValues", 0, 0, 0, 0x20006u, 0, &phkResult, 0);
        IsValidPerformanceSubgroup = v20;
        if ( v20 )
          goto LABEL_70;
        IsValidPerformanceSubgroup = UmpoInternalOpenGUIDSubKey(phkResult, v18, &v29, 0x2001Fu, cbData == 1, 0);
        if ( IsValidPerformanceSubgroup )
          goto LABEL_70;
        IsValidPerformanceSubgroup = UmpoInternalCheckDefaultIndex(v29);
        if ( IsValidPerformanceSubgroup )
          goto LABEL_70;
        v21 = v27;
        if ( v27 || a3 || v19 )
          v22 = UmpoInternalDataAccessorToDefaultOverrideString(a5);
        else
          v22 = (const WCHAR *)UmpoInternalDataAccessorToString(a5);
        if ( !v22 )
          goto LABEL_20;
        if ( cbData == 1 )
        {
          if ( !v21 && !a3 && !v19 )
          {
            IsValidPerformanceSubgroup = 2;
            goto LABEL_70;
          }
          v17 = RegDeleteValueW(v29, v22);
        }
        else
        {
          v17 = RegSetValueExW(v29, v22, 0, dwType, lpData, cbData);
        }
      }
      IsValidPerformanceSubgroup = v17;
      goto LABEL_70;
    }
  }
  return 87;
}

```

## disassembly

```asm
0x18000cb4c  push    rbp
0x18000cb4e  push    rbx
0x18000cb4f  push    rsi
0x18000cb50  push    rdi
0x18000cb51  push    r12
0x18000cb53  push    r13
0x18000cb55  push    r14
0x18000cb57  push    r15
0x18000cb59  lea     rbp, [rsp-7]
0x18000cb5e  sub     rsp, 0D8h
0x18000cb65  mov     rax, cs:__security_cookie
0x18000cb6c  xor     rax, rsp
0x18000cb6f  mov     [rbp+3Fh+var_50], rax
0x18000cb73  mov     edi, [rbp+3Fh+arg_20]
0x18000cb76  mov     r12, rdx
0x18000cb79  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000cb7d  mov     [rbp+3Fh+Uuid2], rcx
0x18000cb81  cmp     cs:UmpoFullPowerPlanSupportDisabled, 0
0x18000cb88  mov     rax, rcx
0x18000cb8b  mov     rcx, [rbp+3Fh+arg_38]
0x18000cb92  xorps   xmm0, xmm0
0x18000cb95  mov     r14, r9
0x18000cb98  mov     [rbp+3Fh+lpData], rcx
0x18000cb9c  mov     r13, r8
0x18000cb9f  mov     [rbp+3Fh+var_BF], 0
0x18000cba3  mov     [rbp+3Fh+var_B0], rdx
0x18000cba7  mov     [rbp+3Fh+var_A8], rdx
0x18000cbab  mov     [rbp+3Fh+var_88], rdx
0x18000cbaf  mov     [rsp+110h+var_C0], 0
0x18000cbb4  movups  [rbp+3Fh+Buf2], xmm0
0x18000cbb8  mov     [rbp+3Fh+hKey], rdx
0x18000cbbc  mov     [rbp+3Fh+Status], 0
0x18000cbc3  mov     [rbp+3Fh+var_94], 10h
0x18000cbca  mov     [rbp+3Fh+var_A0], rdx
0x18000cbce  jz      short loc_18000CBD8
0x18000cbd0  lea     ebx, [rdx+33h]
0x18000cbd3  jmp     loc_18000D04F
0x18000cbd8  mov     r15d, [rbp+3Fh+cbData]
0x18000cbdf  test    r15d, r15d
0x18000cbe2  jz      loc_18000D053
0x18000cbe8  test    rcx, rcx
0x18000cbeb  jz      loc_18000D053
0x18000cbf1  test    rax, rax
0x18000cbf4  jz      short loc_18000CBFF
0x18000cbf6  test    r14, r14
0x18000cbf9  jz      loc_18000D053
0x18000cbff  test    r13, r13
0x18000cc02  jz      short loc_18000CC16
0x18000cc04  test    r14, r14
0x18000cc07  jz      loc_18000D053
0x18000cc0d  test    rax, rax
0x18000cc10  jz      loc_18000D053
0x18000cc16  lea     eax, [rdi-9]
0x18000cc19  cmp     eax, 2
0x18000cc1c  ja      short loc_18000CC32
0x18000cc1e  cmp     r15d, 4
0x18000cc22  jnz     loc_18000D053
0x18000cc28  cmp     [rbp+3Fh+dwType], r15d
0x18000cc2c  jnz     loc_18000D053
0x18000cc32  cmp     edi, 0Dh
0x18000cc35  ja      short loc_18000CC4B
0x18000cc37  mov     eax, 306Ch
0x18000cc3c  bt      eax, edi
0x18000cc3f  jnb     short loc_18000CC4B
0x18000cc41  cmp     [rbp+3Fh+dwType], 2
0x18000cc45  jnz     loc_18000D053
0x18000cc4b  mov     rsi, cs:UmpoSystemPowerRootKey
0x18000cc52  lea     rax, [rsi+1]
0x18000cc56  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000cc5c  jnz     short loc_18000CC6A
0x18000cc5e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000cc63  mov     rsi, cs:UmpoSystemPowerRootKey
0x18000cc6a  cmp     edi, 4
0x18000cc6d  jnz     short loc_18000CC88
0x18000cc6f  mov     rdx, r14
0x18000cc72  mov     rcx, r12
0x18000cc75  call    UmpoInternalIsSettingRangeDefined
0x18000cc7a  test    al, al
0x18000cc7c  jz      short loc_18000CC88
0x18000cc7e  mov     ebx, 57h ; 'W'
0x18000cc83  jmp     loc_18000CFCE
0x18000cc88  xor     ebx, ebx
0x18000cc8a  test    r12, r12
0x18000cc8d  jz      short loc_18000CCD3
0x18000cc8f  lea     r8, [rbp+3Fh+Status]; Status
0x18000cc93  mov     rcx, r12; Uuid1
0x18000cc96  lea     rdx, NO_SUBGROUP_GUID; Uuid2
0x18000cc9d  call    cs:__imp_UuidEqual
0x18000cca3  test    eax, eax
0x18000cca5  jnz     short loc_18000CCD3
0x18000cca7  mov     qword ptr [rsp+110h+samDesired], rbx; __int64
0x18000ccac  lea     r8, [rbp+3Fh+var_A0]; phkResult
0x18000ccb0  mov     r9d, 20006h; samDesired
0x18000ccb6  mov     byte ptr [rsp+110h+dwOptions], bl; char
0x18000ccba  mov     rdx, r12; Uuid2
0x18000ccbd  mov     rcx, rsi; hKey
0x18000ccc0  call    UmpoInternalOpenGUIDSubKey
0x18000ccc5  mov     ebx, eax
0x18000ccc7  test    eax, eax
0x18000ccc9  jnz     loc_18000CFCE
0x18000cccf  mov     rsi, [rbp+3Fh+var_A0]
0x18000ccd3  mov     rdx, [rbp+3Fh+hKey]
0x18000ccd7  lea     rcx, [rdx-1]
0x18000ccdb  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000ccdf  ja      short loc_18000CCF2
0x18000cce1  mov     rcx, rdx; hKey
0x18000cce4  call    cs:__imp_RegCloseKey
0x18000ccea  mov     [rbp+3Fh+hKey], 0FFFFFFFFFFFFFFFFh
0x18000ccf2  test    r14, r14
0x18000ccf5  jz      short loc_18000CD28
0x18000ccf7  mov     qword ptr [rsp+110h+samDesired], 0; __int64
0x18000cd00  lea     r8, [rbp+3Fh+hKey]; phkResult
0x18000cd04  mov     r9d, 2000Eh; samDesired
0x18000cd0a  mov     byte ptr [rsp+110h+dwOptions], 0; char
0x18000cd0f  mov     rdx, r14; Uuid2
0x18000cd12  mov     rcx, rsi; hKey
0x18000cd15  call    UmpoInternalOpenGUIDSubKey
0x18000cd1a  mov     ebx, eax
0x18000cd1c  test    eax, eax
0x18000cd1e  jnz     loc_18000CFCE
0x18000cd24  mov     rsi, [rbp+3Fh+hKey]
0x18000cd28  cmp     edi, 0Fh
0x18000cd2b  ja      short loc_18000CD5D
0x18000cd2d  mov     eax, 0BE0Ch
0x18000cd32  bt      eax, edi
0x18000cd35  jnb     short loc_18000CD5D
0x18000cd37  mov     ecx, edi
0x18000cd39  call    UmpoInternalDataAccessorToString
0x18000cd3e  test    rax, rax
0x18000cd41  jz      loc_18000CC7E
0x18000cd47  mov     rcx, [rbp+3Fh+lpData]
0x18000cd4b  mov     [rsp+110h+samDesired], r15d
0x18000cd50  mov     qword ptr [rsp+110h+dwOptions], rcx
0x18000cd55  mov     rcx, rsi
0x18000cd58  jmp     loc_18000CFBC
0x18000cd5d  lea     eax, [rdi-4]
0x18000cd60  cmp     eax, 2
0x18000cd63  jbe     loc_18000CF45
0x18000cd69  lea     eax, [rdi-7]
0x18000cd6c  cmp     eax, 1
0x18000cd6f  ja      loc_18000CFCE
0x18000cd75  mov     r14, [rbp+3Fh+Uuid2]
0x18000cd79  test    r14, r14
0x18000cd7c  jz      loc_18000CC7E
0x18000cd82  lea     rdx, [rsp+110h+var_C0]
0x18000cd87  mov     rcx, r14
0x18000cd8a  call    UmpoInternalIsOverlayPowerScheme
0x18000cd8f  mov     sil, [rsp+110h+var_C0]
0x18000cd94  test    sil, sil
0x18000cd97  jz      short loc_18000CDB0
0x18000cd99  mov     rcx, r12
0x18000cd9c  call    UmpoIsValidPerformanceSubgroup
0x18000cda1  xor     r12d, r12d
0x18000cda4  mov     ebx, eax
0x18000cda6  test    eax, eax
0x18000cda8  jnz     loc_18000CFCE
0x18000cdae  jmp     short loc_18000CDB3
0x18000cdb0  xor     r12d, r12d
0x18000cdb3  test    r13, r13
0x18000cdb6  jz      short loc_18000CE1A
0x18000cdb8  test    sil, sil
0x18000cdbb  jnz     short loc_18000CE1A
0x18000cdbd  lea     rax, [rbp+3Fh+var_94]
0x18000cdc1  xor     r9d, r9d
0x18000cdc4  mov     [rsp+110h+phkResult], rax
0x18000cdc9  lea     r8, NO_SUBGROUP_GUID
0x18000cdd0  lea     rax, [rbp+3Fh+Buf2]
0x18000cdd4  mov     rdx, r14
0x18000cdd7  mov     [rsp+110h+lpSecurityAttributes], rax
0x18000cddc  xor     ecx, ecx
0x18000cdde  lea     rax, GUID_POWERSCHEME_PERSONALITY
0x18000cde5  mov     qword ptr [rsp+110h+samDesired], r12
0x18000cdea  mov     qword ptr [rsp+110h+dwOptions], rax
0x18000cdef  call    UmpoReadACValue
0x18000cdf4  mov     ebx, eax
0x18000cdf6  test    eax, eax
0x18000cdf8  jnz     loc_18000CFCE
0x18000cdfe  lea     r8d, [rax+10h]; Size
0x18000ce02  lea     rdx, [rbp+3Fh+Buf2]; Buf2
0x18000ce06  lea     rcx, GUID_TYPICAL_POWER_SAVINGS; Buf1
0x18000ce0d  call    memcmp_0
0x18000ce12  test    eax, eax
0x18000ce14  jnz     loc_18000CC7E
0x18000ce1a  cmp     [rbp+3Fh+hKey], 0FFFFFFFFFFFFFFFFh
0x18000ce1f  jz      loc_18000CC7E
0x18000ce25  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18000ce29  test    r13, r13
0x18000ce2c  jnz     short loc_18000CE63
0x18000ce2e  mov     [rsp+110h+lpdwDisposition], r12; lpdwDisposition
0x18000ce33  lea     rax, [rbp+3Fh+var_A8]
0x18000ce37  mov     [rsp+110h+phkResult], rax; phkResult
0x18000ce3c  lea     rdx, aDefaultpowersc; "DefaultPowerSchemeValues"
0x18000ce43  mov     [rsp+110h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18000ce48  xor     r9d, r9d; lpClass
0x18000ce4b  mov     [rsp+110h+samDesired], 20006h; samDesired
0x18000ce53  xor     r8d, r8d; Reserved
0x18000ce56  mov     [rsp+110h+dwOptions], r12d; dwOptions
0x18000ce5b  call    cs:__imp_RegCreateKeyExW
0x18000ce61  jmp     short loc_18000CE85
0x18000ce63  cmp     r15d, 1
0x18000ce67  mov     qword ptr [rsp+110h+samDesired], r12; __int64
0x18000ce6c  mov     r9d, 20006h; samDesired
0x18000ce72  lea     r8, [rbp+3Fh+var_A8]; phkResult
0x18000ce76  setz    al
0x18000ce79  mov     rdx, r13; Uuid2
0x18000ce7c  mov     byte ptr [rsp+110h+dwOptions], al; char
0x18000ce80  call    UmpoInternalOpenGUIDSubKey
0x18000ce85  mov     ebx, eax
0x18000ce87  test    eax, eax
0x18000ce89  jnz     loc_18000CFCE
0x18000ce8f  mov     rcx, [rbp+3Fh+var_A8]; hKey
0x18000ce93  lea     r8, [rbp+3Fh+var_B0]; phkResult
0x18000ce97  cmp     r15d, 1
0x18000ce9b  mov     qword ptr [rsp+110h+samDesired], r12; __int64
0x18000cea0  mov     r9d, 2001Fh; samDesired
0x18000cea6  mov     rdx, r14; Uuid2
0x18000cea9  setz    al
0x18000ceac  mov     byte ptr [rsp+110h+dwOptions], al; char
0x18000ceb0  call    UmpoInternalOpenGUIDSubKey
0x18000ceb5  mov     ebx, eax
0x18000ceb7  test    eax, eax
0x18000ceb9  jnz     loc_18000CFCE
0x18000cebf  mov     rcx, [rbp+3Fh+var_B0]; hKey
0x18000cec3  lea     r8, [rbp+3Fh+var_BF]
0x18000cec7  mov     edx, edi
0x18000cec9  call    UmpoInternalCheckDefaultIndex
0x18000cece  mov     ebx, eax
0x18000ced0  test    eax, eax
0x18000ced2  jnz     loc_18000CFCE
0x18000ced8  mov     bl, [rbp+3Fh+var_BF]
0x18000cedb  test    bl, bl
0x18000cedd  jnz     short loc_18000CEF2
0x18000cedf  test    r13, r13
0x18000cee2  jnz     short loc_18000CEF2
0x18000cee4  test    sil, sil
0x18000cee7  jnz     short loc_18000CEF2
0x18000cee9  mov     ecx, edi
0x18000ceeb  call    UmpoInternalDataAccessorToString
0x18000cef0  jmp     short loc_18000CEF9
0x18000cef2  mov     ecx, edi
0x18000cef4  call    UmpoInternalDataAccessorToDefaultOverrideString
0x18000cef9  test    rax, rax
0x18000cefc  jz      loc_18000CC7E
0x18000cf02  cmp     r15d, 1
0x18000cf06  jnz     short loc_18000CF31
0x18000cf08  test    bl, bl
0x18000cf0a  jnz     short loc_18000CF1F
0x18000cf0c  test    r13, r13
0x18000cf0f  jnz     short loc_18000CF1F
0x18000cf11  test    sil, sil
0x18000cf14  jnz     short loc_18000CF1F
0x18000cf16  lea     ebx, [r15+1]
0x18000cf1a  jmp     loc_18000CFCE
0x18000cf1f  mov     rcx, [rbp+3Fh+var_B0]; hKey
0x18000cf23  mov     rdx, rax; lpValueName
0x18000cf26  call    cs:__imp_RegDeleteValueW
0x18000cf2c  jmp     loc_18000CFCC
0x18000cf31  mov     rcx, [rbp+3Fh+lpData]
0x18000cf35  mov     [rsp+110h+samDesired], r15d
0x18000cf3a  mov     qword ptr [rsp+110h+dwOptions], rcx
0x18000cf3f  mov     rcx, [rbp+3Fh+var_B0]
0x18000cf43  jmp     short loc_18000CFBC
0x18000cf45  mov     rdx, r14
0x18000cf48  mov     rcx, r12
0x18000cf4b  call    UmpoInternalIsSettingRangeDefined
0x18000cf50  test    al, al
0x18000cf52  jz      short loc_18000CF5A
0x18000cf54  mov     rbx, [rbp+3Fh+hKey]
0x18000cf58  jmp     short loc_18000CF9B
0x18000cf5a  mov     ecx, [rbp+3Fh+arg_30]
0x18000cf5d  lea     rdx, [rbp+3Fh+SubKey]
0x18000cf61  mov     r9d, 0Ah
0x18000cf67  lea     r8d, [r9+1]
0x18000cf6b  call    cs:__imp__o__ultow_s
0x18000cf71  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18000cf75  lea     rax, [rbp+3Fh+var_88]
0x18000cf79  mov     r9d, 20006h; samDesired
0x18000cf7f  mov     qword ptr [rsp+110h+dwOptions], rax; phkResult
0x18000cf84  xor     r8d, r8d; ulOptions
0x18000cf87  lea     rdx, [rbp+3Fh+SubKey]; lpSubKey
0x18000cf8b  call    cs:__imp_RegOpenKeyExW
0x18000cf91  mov     ebx, eax
0x18000cf93  test    eax, eax
0x18000cf95  jnz     short loc_18000CFCE
0x18000cf97  mov     rbx, [rbp+3Fh+var_88]
0x18000cf9b  mov     ecx, edi
0x18000cf9d  call    UmpoInternalDataAccessorToString
0x18000cfa2  test    rax, rax
0x18000cfa5  jz      loc_18000CC7E
0x18000cfab  mov     rcx, [rbp+3Fh+lpData]
0x18000cfaf  mov     [rsp+110h+samDesired], r15d; cbData
0x18000cfb4  mov     qword ptr [rsp+110h+dwOptions], rcx; lpData
0x18000cfb9  mov     rcx, rbx; hKey
0x18000cfbc  mov     r9d, [rbp+3Fh+dwType]; dwType
0x18000cfc0  xor     r8d, r8d; Reserved
0x18000cfc3  mov     rdx, rax; lpValueName
0x18000cfc6  call    cs:__imp_RegSetValueExW
0x18000cfcc  mov     ebx, eax
0x18000cfce  mov     rcx, [rbp+3Fh+var_A8]; hKey
0x18000cfd2  lea     rax, [rcx-1]
  ... truncated ...
```
