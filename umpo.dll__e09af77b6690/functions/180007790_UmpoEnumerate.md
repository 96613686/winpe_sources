# UmpoEnumerate

- ea: `0x180007790`
- end: `0x180007edf`
- name: `UmpoEnumerate`
- size: `1871`
- prototype: `__int64 __fastcall(UUID *Uuid2, UUID *, int, unsigned int, UUID *, _DWORD *, char)`
- caller_count: `9`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800027d4`
- `0x180007440`
- `0x180007650`
- `0x180008044`
- `0x180008510`
- `0x18000b7b0`
- `0x180011190`
- `0x180012fa8`
- `0x180013f20`

## callees

- `0x180003270`
- `0x1800035c0`
- `0x180003cb0`
- `0x180005480`
- `0x1800066b0`
- `0x180007790`
- `0x180007f70`
- `0x18000f3dc`
- `0x180010070`
- `0x1800188bc`
- `0x180019010`

## import_xrefs

- `ntdll!RtlGUIDFromString` at `0x180007aed`
- `ntdll!RtlGUIDFromString` at `0x180007aed`
- `ntdll!RtlInitUnicodeString` at `0x180007adf`
- `ntdll!RtlInitUnicodeString` at `0x180007adf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007a1e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007cf1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007a1e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007cf1`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180007ab2`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180007ab2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007d6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007e67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007d6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007e67`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180007a3a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180007d0e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180007a3a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180007d0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800079f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007cc4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800079f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007cc4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007a0a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007cdd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007d7d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007e75`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007a0a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007cdd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007d7d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007e75`
- `RPCRT4!UuidFromStringW` at `0x180007acf`
- `RPCRT4!UuidFromStringW` at `0x180007acf`
- `RPCRT4!UuidEqual` at `0x1800078da`
- `RPCRT4!UuidEqual` at `0x1800079a1`
- `RPCRT4!UuidEqual` at `0x1800078da`
- `RPCRT4!UuidEqual` at `0x1800079a1`

## pseudocode

```c
__int64 __fastcall UmpoEnumerate(UUID *Uuid2, UUID *a2, int a3, unsigned int a4, UUID *a5, _DWORD *a6, char a7)
{
  __int64 v7; // r13
  HKEY v12; // rbx
  unsigned int v13; // esi
  HKEY v14; // rdi
  unsigned int Value; // ebx
  HKEY v16; // r13
  unsigned int v17; // ebx
  DWORD v18; // r12d
  NTSTATUS v19; // eax
  __int64 v20; // rcx
  GUID *v21; // rdx
  char v22; // al
  unsigned int v23; // ecx
  char IsSinglePowerSetting; // al
  unsigned int v25; // ecx
  __int64 v26; // rcx
  GUID *v27; // rdx
  unsigned int v28; // eax
  HKEY v29; // rdi
  int KeyValueGuid; // ebx
  unsigned int v31; // ebx
  bool v32; // cf
  char v33; // [rsp+40h] [rbp-C0h]
  char v34; // [rsp+41h] [rbp-BFh]
  RPC_STATUS Status; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v37; // [rsp+4Ch] [rbp-B4h]
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v39; // [rsp+58h] [rbp-A8h]
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v41; // [rsp+68h] [rbp-98h]
  struct _FILETIME ftLastWriteTime; // [rsp+70h] [rbp-90h] BYREF
  _DWORD *v43; // [rsp+78h] [rbp-88h]
  UUID *v44; // [rsp+80h] [rbp-80h]
  _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  UUID Uuid; // [rsp+98h] [rbp-68h] BYREF
  WCHAR Name[8]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v48; // [rsp+C0h] [rbp-40h]
  __int128 v49; // [rsp+D0h] [rbp-30h]
  __int128 v50; // [rsp+E0h] [rbp-20h]
  __int128 v51; // [rsp+F0h] [rbp-10h]
  __int128 v52; // [rsp+100h] [rbp+0h]
  __int128 v53; // [rsp+110h] [rbp+10h]
  __int128 v54; // [rsp+120h] [rbp+20h]

  v37 = a4;
  v7 = -1;
  v44 = a5;
  v43 = a6;
  cchName = 0;
  ftLastWriteTime = 0;
  v41 = -1;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  Status = 0;
  DestinationString = 0;
  *(_OWORD *)Name = 0;
  Uuid = GUID_NULL;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  if ( a3 == 16 )
    goto LABEL_6;
  if ( !a7 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( a3 != 25 )
  {
LABEL_6:
    if ( a3 != 26 && a2 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( !a6 )
    return 87;
  v39 = *a6;
  v33 = 0;
  if ( a3 == 16 || a3 == 26 )
  {
    if ( UmpoUserPowerTlsSlot == -1 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( UmpoUserPowerLockThread == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    Value = (unsigned int)TlsGetValue(UmpoUserPowerTlsSlot);
    if ( !Value )
      AcquireSRWLockShared(&UmpoUserPowerLock);
    if ( UmpoUserPowerLockThread )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    TlsSetValue(UmpoUserPowerTlsSlot, (LPVOID)(Value + 1));
    if ( (unsigned __int64)UmpoUserPowerRootKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v41 = (__int64)UmpoUserPowerRootKey;
      v16 = UmpoUserPowerRootKey;
      if ( UmpoUserPowerRootKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      v14 = v16;
      goto LABEL_43;
    }
    v7 = 0;
    if ( (((unsigned __int64)UmpoUserPowerRootKey + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    ReleaseUserPowerLock();
LABEL_124:
    v13 = 87;
    goto LABEL_125;
  }
  if ( (unsigned int)(a3 - 17) <= 1 )
  {
    v14 = UmpoSystemPowerRootKey;
    if ( UmpoSystemPowerRootKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( a3 == 18 && Uuid2 && !UuidEqual(Uuid2, (UUID *)&NO_SUBGROUP_GUID, &Status) )
    {
      v13 = UmpoInternalOpenGUIDSubKey(v14, Uuid2, &phkResult, 0x20019u, 1, (__int64)&UmpoPowerSubGroupCache);
      if ( v13 )
        goto LABEL_125;
      v14 = phkResult;
    }
    goto LABEL_43;
  }
  if ( a3 != 25 )
    goto LABEL_124;
  if ( !a2 || !Uuid2 )
  {
    v14 = UmpoPpmProfileEventsRootKey;
    if ( UmpoPpmProfileEventsRootKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      v13 = 6;
      goto LABEL_125;
    }
    v33 = 1;
    goto LABEL_43;
  }
  v12 = UmpoSystemPowerRootKey;
  if ( !UuidEqual(Uuid2, (UUID *)&NO_SUBGROUP_GUID, &Status) )
  {
    v13 = UmpoInternalOpenGUIDSubKey(v12, Uuid2, &phkResult, 0x20019u, 1, (__int64)&UmpoPowerSubGroupCache);
    if ( v13 )
      goto LABEL_125;
    v12 = phkResult;
  }
  v13 = UmpoInternalOpenGUIDSubKey(v12, a2, &hKey, 0x20019u, 1, (__int64)&UmpoPowerSettingCache);
  if ( !v13 )
  {
    v14 = hKey;
LABEL_43:
    v17 = 0;
    v34 = 0;
    v18 = 0;
    while ( 1 )
    {
      cchName = 64;
      v13 = RegEnumKeyExW(v14, v18, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
      if ( v13 )
      {
        v28 = v37;
LABEL_85:
        v7 = v41;
        if ( a3 == 16 && v13 == 259 && v17 == v28 )
        {
          if ( !qword_1800246A8 || (v29 = 0, (KeyValueGuid = qword_1800246A8(&Uuid)) != 0) )
          {
            if ( UmpoUserPowerTlsSlot == -1 )
              MicrosoftTelemetryAssertTriggeredNoArgs();
            if ( UmpoUserPowerLockThread == GetCurrentThreadId() )
              MicrosoftTelemetryAssertTriggeredNoArgs();
            v31 = (unsigned int)TlsGetValue(UmpoUserPowerTlsSlot);
            if ( !v31 )
              AcquireSRWLockShared(&UmpoUserPowerLock);
            if ( UmpoUserPowerLockThread )
              MicrosoftTelemetryAssertTriggeredNoArgs();
            TlsSetValue(UmpoUserPowerTlsSlot, (LPVOID)(v31 + 1));
            if ( (unsigned __int64)UmpoUserPowerRootKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
            {
              v29 = 0;
              if ( (((unsigned __int64)UmpoUserPowerRootKey + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
                MicrosoftTelemetryAssertTriggeredNoArgs();
              ReleaseUserPowerLock();
              KeyValueGuid = 87;
            }
            else
            {
              v29 = UmpoUserPowerRootKey;
              KeyValueGuid = UmpoInternalGetKeyValueGuid(UmpoUserPowerRootKey, L"ActivePowerScheme", &Uuid);
            }
          }
          if ( UmpoUserPowerRootKey == v29 )
          {
            if ( !(unsigned int)TlsGetValue(UmpoUserPowerTlsSlot) || UmpoUserPowerLockThread )
              MicrosoftTelemetryAssertTriggeredNoArgs();
            ReleaseUserPowerLock();
          }
          else if ( (unsigned __int64)v29 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            RegCloseKey(v29);
          }
          if ( !KeyValueGuid )
          {
            if ( !UmpoFullPowerPlanSupportDisabled || !memcmp_0(&GUID_TYPICAL_POWER_SAVINGS, &Uuid, 0x10u) )
            {
              if ( !memcmp_0(&GUID_POWER_SCHEME_ULTIMATE_PERFORMANCE, &Uuid, 0x10u) )
              {
                v13 = 0;
                if ( !v34 )
                  v13 = 259;
              }
              else if ( !a7 && !(unsigned __int8)UmpoInternalIsSchemeVisible(&Uuid) )
              {
                v13 = 0;
              }
            }
            else
            {
              v13 = 0;
            }
          }
        }
        break;
      }
      if ( v33 )
      {
        RtlInitUnicodeString(&DestinationString, Name);
        v19 = RtlGUIDFromString(&DestinationString, &Uuid);
      }
      else
      {
        v19 = UuidFromStringW(Name, &Uuid);
      }
      v13 = v19;
      if ( !v19 )
      {
        if ( a3 != 16 )
        {
          if ( a3 == 17 )
          {
            IsSinglePowerSetting = UmpoInternalIsSinglePowerSetting(Uuid2);
            v25 = v17 + 1;
            if ( IsSinglePowerSetting )
              v25 = v17;
            v17 = v25;
            goto LABEL_82;
          }
          if ( a3 == 18 )
          {
            v22 = UmpoInternalIsSinglePowerSetting(Uuid2);
            v23 = v17 + 1;
            if ( !v22 )
              v23 = v17;
            v17 = v23;
            goto LABEL_82;
          }
          if ( a3 != 25 )
          {
            if ( a3 != 26 || UmpoFullPowerPlanSupportDisabled )
              goto LABEL_82;
            v20 = 0;
            while ( 1 )
            {
              v21 = UmpoOverlaySchemeGuids[v20];
              if ( *(_QWORD *)&Uuid.Data1 == *(_QWORD *)&v21->Data1 && *(_QWORD *)Uuid.Data4 == *(_QWORD *)v21->Data4 )
                break;
              v20 = (unsigned int)(v20 + 1);
              if ( (unsigned int)v20 >= 3 )
                goto LABEL_82;
            }
            if ( (unsigned __int8)UmpoInternalIsSinglePowerSetting(Uuid2) )
              MicrosoftTelemetryAssertTriggeredNoArgs();
          }
          goto LABEL_81;
        }
        if ( !(unsigned __int8)UmpoInternalIsSinglePowerSetting(Uuid2) )
        {
          if ( !UmpoFullPowerPlanSupportDisabled )
          {
            v26 = 0;
            while ( 1 )
            {
              v27 = UmpoOverlaySchemeGuids[v26];
              if ( *(_QWORD *)&Uuid.Data1 == *(_QWORD *)&v27->Data1 && *(_QWORD *)Uuid.Data4 == *(_QWORD *)v27->Data4 )
                goto LABEL_82;
              v26 = (unsigned int)(v26 + 1);
              if ( (unsigned int)v26 >= 3 )
                goto LABEL_76;
            }
          }
          if ( !memcmp_0(&GUID_TYPICAL_POWER_SAVINGS, &Uuid, 0x10u) )
            goto LABEL_81;
LABEL_76:
          if ( memcmp_0(&GUID_POWER_SCHEME_ULTIMATE_PERFORMANCE, &Uuid, 0x10u) )
          {
            if ( !a7 && !(unsigned __int8)UmpoInternalIsSchemeVisible(&Uuid) )
              goto LABEL_82;
LABEL_81:
            ++v17;
            goto LABEL_82;
          }
          if ( UmpoUltimatePerfSchemeAllowed )
            goto LABEL_81;
          v34 = 1;
        }
      }
LABEL_82:
      v28 = v37;
      ++v18;
      if ( v17 > v37 )
        goto LABEL_85;
    }
  }
LABEL_125:
  UmpoInternalRegCloseKey(&UmpoPowerSettingCache, hKey);
  UmpoInternalRegCloseKey(&UmpoPowerSubGroupCache, phkResult);
  if ( UmpoUserPowerRootKey == (HKEY)v7 )
  {
    if ( !(unsigned int)TlsGetValue(UmpoUserPowerTlsSlot) || UmpoUserPowerLockThread )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    ReleaseUserPowerLock();
  }
  else if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey((HKEY)v7);
  }
  if ( !v13 )
  {
    v32 = v39 < 0x10;
    *v43 = 16;
    if ( v32 || !v44 )
      return 234;
    else
      *v44 = Uuid;
  }
  return v13;
}

```

## disassembly

```asm
0x180007790  push    rbp
0x180007792  push    rbx
0x180007793  push    rsi
0x180007794  push    rdi
0x180007795  push    r13
0x180007797  push    r14
0x180007799  push    r15
0x18000779b  lea     rbp, [rsp-40h]
0x1800077a0  sub     rsp, 140h
0x1800077a7  mov     rax, cs:__security_cookie
0x1800077ae  xor     rax, rsp
0x1800077b1  mov     [rbp+70h+var_40], rax
0x1800077b5  mov     rax, [rbp+70h+arg_20]
0x1800077bc  xorps   xmm1, xmm1
0x1800077bf  mov     rbx, [rbp+70h+arg_28]
0x1800077c6  xor     esi, esi
0x1800077c8  mov     [rsp+170h+var_124], r9d
0x1800077cd  mov     r13, 0FFFFFFFFFFFFFFFFh
0x1800077d4  mov     [rbp+70h+var_F0], rax
0x1800077d8  xorps   xmm0, xmm0
0x1800077db  mov     [rsp+170h+var_F8], rbx
0x1800077e0  mov     r14d, r8d
0x1800077e3  mov     [rsp+170h+cchName], esi
0x1800077e7  mov     rdi, rdx
0x1800077ea  mov     qword ptr [rsp+170h+ftLastWriteTime.dwLowDateTime], rsi
0x1800077ef  mov     r15, rcx
0x1800077f2  mov     [rsp+170h+var_108], r13
0x1800077f7  mov     [rsp+170h+hKey], r13
0x1800077fc  mov     [rsp+170h+phkResult], r13
0x180007801  mov     [rsp+170h+Status], esi
0x180007805  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x180007809  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180007810  movups  xmmword ptr [rbp+70h+Name], xmm1
0x180007814  movups  xmmword ptr [rbp+70h+Uuid.Data1], xmm0
0x180007818  movups  [rbp+70h+var_B0], xmm1
0x18000781c  movups  [rbp+70h+var_A0], xmm1
0x180007820  movups  [rbp+70h+var_90], xmm1
0x180007824  movups  [rbp+70h+var_80], xmm1
0x180007828  movups  [rbp+70h+var_70], xmm1
0x18000782c  movups  [rbp+70h+var_60], xmm1
0x180007830  movups  [rbp+70h+var_50], xmm1
0x180007834  cmp     r8d, 10h
0x180007838  jz      short loc_18000784E
0x18000783a  cmp     [rbp+70h+arg_30], sil
0x180007841  jnz     short loc_180007848
0x180007843  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007848  cmp     r14d, 19h
0x18000784c  jz      short loc_18000785E
0x18000784e  cmp     r14d, 1Ah
0x180007852  jz      short loc_18000785E
0x180007854  test    rdi, rdi
0x180007857  jz      short loc_18000785E
0x180007859  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000785e  test    rbx, rbx
0x180007861  jnz     short loc_18000786D
0x180007863  mov     eax, 57h ; 'W'
0x180007868  jmp     loc_180007EC1
0x18000786d  mov     eax, [rbx]
0x18000786f  mov     [rsp+170h+arg_10], r12
0x180007877  lea     r12, UmpoPowerSubGroupCache
0x18000787e  mov     [rsp+170h+var_118], eax
0x180007882  mov     [rsp+170h+var_130], sil
0x180007887  cmp     r14d, 10h
0x18000788b  jz      loc_1800079E3
0x180007891  cmp     r14d, 1Ah
0x180007895  jz      loc_1800079E3
0x18000789b  lea     eax, [r14-11h]
0x18000789f  cmp     eax, 1
0x1800078a2  jbe     loc_18000796E
0x1800078a8  cmp     r14d, 19h
0x1800078ac  jnz     loc_180007E22
0x1800078b2  test    rdi, rdi
0x1800078b5  jz      loc_18000794E
0x1800078bb  test    r15, r15
0x1800078be  jz      loc_18000794E
0x1800078c4  mov     rbx, cs:UmpoSystemPowerRootKey
0x1800078cb  lea     r8, [rsp+170h+Status]; Status
0x1800078d0  lea     rdx, NO_SUBGROUP_GUID; Uuid2
0x1800078d7  mov     rcx, r15; Uuid1
0x1800078da  call    cs:__imp_UuidEqual
0x1800078e0  test    eax, eax
0x1800078e2  jnz     short loc_180007913
0x1800078e4  mov     [rsp+170h+lpClass], r12; __int64
0x1800078e9  lea     r8, [rsp+170h+phkResult]; phkResult
0x1800078ee  mov     r9d, 20019h; samDesired
0x1800078f4  mov     byte ptr [rsp+170h+lpReserved], 1; char
0x1800078f9  mov     rdx, r15; Uuid2
0x1800078fc  mov     rcx, rbx; hKey
0x1800078ff  call    UmpoInternalOpenGUIDSubKey
0x180007904  mov     esi, eax
0x180007906  test    eax, eax
0x180007908  jnz     loc_180007E27
0x18000790e  mov     rbx, [rsp+170h+phkResult]
0x180007913  lea     rax, UmpoPowerSettingCache
0x18000791a  mov     r9d, 20019h; samDesired
0x180007920  mov     [rsp+170h+lpClass], rax; __int64
0x180007925  lea     r8, [rsp+170h+hKey]; phkResult
0x18000792a  mov     rdx, rdi; Uuid2
0x18000792d  mov     byte ptr [rsp+170h+lpReserved], 1; char
0x180007932  mov     rcx, rbx; hKey
0x180007935  call    UmpoInternalOpenGUIDSubKey
0x18000793a  mov     esi, eax
0x18000793c  test    eax, eax
0x18000793e  jnz     loc_180007E27
0x180007944  mov     rdi, [rsp+170h+hKey]
0x180007949  jmp     loc_180007A6B
0x18000794e  mov     rdi, cs:UmpoPpmProfileEventsRootKey
0x180007955  cmp     rdi, r13
0x180007958  jnz     short loc_180007964
0x18000795a  mov     esi, 6
0x18000795f  jmp     loc_180007E27
0x180007964  mov     [rsp+170h+var_130], 1
0x180007969  jmp     loc_180007A6B
0x18000796e  mov     rdi, cs:UmpoSystemPowerRootKey
0x180007975  cmp     rdi, r13
0x180007978  jnz     short loc_18000797F
0x18000797a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000797f  cmp     r14d, 12h
0x180007983  jnz     loc_180007A6B
0x180007989  test    r15, r15
0x18000798c  jz      loc_180007A6B
0x180007992  lea     r8, [rsp+170h+Status]; Status
0x180007997  mov     rcx, r15; Uuid1
0x18000799a  lea     rdx, NO_SUBGROUP_GUID; Uuid2
0x1800079a1  call    cs:__imp_UuidEqual
0x1800079a7  test    eax, eax
0x1800079a9  jnz     loc_180007A6B
0x1800079af  mov     [rsp+170h+lpClass], r12; __int64
0x1800079b4  lea     r8, [rsp+170h+phkResult]; phkResult
0x1800079b9  mov     r9d, 20019h; samDesired
0x1800079bf  mov     byte ptr [rsp+170h+lpReserved], 1; char
0x1800079c4  mov     rdx, r15; Uuid2
0x1800079c7  mov     rcx, rdi; hKey
0x1800079ca  call    UmpoInternalOpenGUIDSubKey
0x1800079cf  mov     esi, eax
0x1800079d1  test    eax, eax
0x1800079d3  jnz     loc_180007E27
0x1800079d9  mov     rdi, [rsp+170h+phkResult]
0x1800079de  jmp     loc_180007A6B
0x1800079e3  cmp     cs:UmpoUserPowerTlsSlot, 0FFFFFFFFh
0x1800079ea  jnz     short loc_1800079F1
0x1800079ec  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800079f1  call    cs:__imp_GetCurrentThreadId
0x1800079f7  cmp     cs:UmpoUserPowerLockThread, eax
0x1800079fd  jnz     short loc_180007A04
0x1800079ff  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007a04  mov     ecx, cs:UmpoUserPowerTlsSlot; dwTlsIndex
0x180007a0a  call    cs:__imp_TlsGetValue
0x180007a10  mov     rbx, rax
0x180007a13  test    eax, eax
0x180007a15  jnz     short loc_180007A24
0x180007a17  lea     rcx, UmpoUserPowerLock; SRWLock
0x180007a1e  call    cs:__imp_AcquireSRWLockShared
0x180007a24  cmp     cs:UmpoUserPowerLockThread, esi
0x180007a2a  jz      short loc_180007A31
0x180007a2c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007a31  mov     ecx, cs:UmpoUserPowerTlsSlot; dwTlsIndex
0x180007a37  lea     edx, [rbx+1]; lpTlsValue
0x180007a3a  call    cs:__imp_TlsSetValue
0x180007a40  mov     rcx, cs:UmpoUserPowerRootKey
0x180007a47  lea     rax, [rcx-1]
0x180007a4b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007a4f  ja      loc_180007E09
0x180007a55  mov     [rsp+170h+var_108], rcx
0x180007a5a  mov     r13, rcx
0x180007a5d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180007a61  jnz     short loc_180007A68
0x180007a63  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007a68  mov     rdi, r13
0x180007a6b  movzx   r13d, [rsp+170h+var_130]
0x180007a71  xor     ecx, ecx
0x180007a73  xor     al, al
0x180007a75  mov     ebx, ecx
0x180007a77  mov     [rsp+170h+var_12F], al
0x180007a7b  mov     r12d, ecx
0x180007a7e  jmp     short loc_180007A82
0x180007a80  xor     ecx, ecx
0x180007a82  lea     rax, [rsp+170h+ftLastWriteTime]
0x180007a87  mov     [rsp+170h+cchName], 40h ; '@'
0x180007a8f  mov     [rsp+170h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180007a94  lea     r9, [rsp+170h+cchName]; lpcchName
0x180007a99  mov     [rsp+170h+lpcchClass], rcx; lpcchClass
0x180007a9e  lea     r8, [rbp+70h+Name]; lpName
0x180007aa2  mov     [rsp+170h+lpClass], rcx; lpClass
0x180007aa7  mov     edx, r12d; dwIndex
0x180007aaa  mov     [rsp+170h+lpReserved], rcx; lpReserved
0x180007aaf  mov     rcx, rdi; hKey
0x180007ab2  call    cs:__imp_RegEnumKeyExW
0x180007ab8  mov     esi, eax
0x180007aba  test    eax, eax
0x180007abc  jnz     loc_180007C6B
0x180007ac2  test    r13b, r13b
0x180007ac5  jnz     short loc_180007AD7
0x180007ac7  lea     rdx, [rbp+70h+Uuid]; Uuid
0x180007acb  lea     rcx, [rbp+70h+Name]; StringUuid
0x180007acf  call    cs:__imp_UuidFromStringW
0x180007ad5  jmp     short loc_180007AF3
0x180007ad7  lea     rdx, [rbp+70h+Name]; SourceString
0x180007adb  lea     rcx, [rbp+70h+DestinationString]; DestinationString
0x180007adf  call    cs:__imp_RtlInitUnicodeString
0x180007ae5  lea     rdx, [rbp+70h+Uuid]; Guid
0x180007ae9  lea     rcx, [rbp+70h+DestinationString]; GuidString
0x180007aed  call    cs:__imp_RtlGUIDFromString
0x180007af3  mov     esi, eax
0x180007af5  test    eax, eax
0x180007af7  jnz     loc_180007C5A
0x180007afd  mov     ecx, r14d
0x180007b00  sub     ecx, 10h
0x180007b03  jz      loc_180007BB6
0x180007b09  sub     ecx, 1
0x180007b0c  jz      loc_180007B9B
0x180007b12  sub     ecx, 1
0x180007b15  jz      short loc_180007B80
0x180007b17  sub     ecx, 7
0x180007b1a  jz      loc_180007C58
0x180007b20  cmp     ecx, 1
0x180007b23  jnz     loc_180007C5A
0x180007b29  cmp     cs:UmpoFullPowerPlanSupportDisabled, 0
0x180007b30  jnz     loc_180007C5A
0x180007b36  mov     r8, qword ptr [rbp+70h+Uuid.Data4]
0x180007b3a  xor     ecx, ecx
0x180007b3c  mov     r9, qword ptr [rbp+70h+Uuid.Data1]
0x180007b40  lea     rdx, UmpoOverlaySchemeGuids
0x180007b47  mov     rdx, [rdx+rcx*8]
0x180007b4b  cmp     r9, [rdx]
0x180007b4e  jnz     short loc_180007B56
0x180007b50  cmp     r8, [rdx+8]
0x180007b54  jz      short loc_180007B62
0x180007b56  inc     ecx
0x180007b58  cmp     ecx, 3
0x180007b5b  jb      short loc_180007B40
0x180007b5d  jmp     loc_180007C5A
0x180007b62  lea     rdx, [rbp+70h+Uuid]
0x180007b66  mov     rcx, r15
0x180007b69  call    UmpoInternalIsSinglePowerSetting
0x180007b6e  test    al, al
0x180007b70  jz      loc_180007C58
0x180007b76  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007b7b  jmp     loc_180007C58
0x180007b80  lea     rdx, [rbp+70h+Uuid]
0x180007b84  mov     rcx, r15
0x180007b87  call    UmpoInternalIsSinglePowerSetting
0x180007b8c  lea     ecx, [rbx+1]
0x180007b8f  test    al, al
0x180007b91  cmovz   ecx, ebx
0x180007b94  mov     ebx, ecx
0x180007b96  jmp     loc_180007C5A
0x180007b9b  lea     rdx, [rbp+70h+Uuid]
0x180007b9f  mov     rcx, r15
0x180007ba2  call    UmpoInternalIsSinglePowerSetting
0x180007ba7  lea     ecx, [rbx+1]
0x180007baa  test    al, al
0x180007bac  cmovnz  ecx, ebx
0x180007baf  mov     ebx, ecx
0x180007bb1  jmp     loc_180007C5A
0x180007bb6  lea     rdx, [rbp+70h+Uuid]
0x180007bba  mov     rcx, r15
0x180007bbd  call    UmpoInternalIsSinglePowerSetting
0x180007bc2  test    al, al
0x180007bc4  jnz     loc_180007C5A
0x180007bca  cmp     cs:UmpoFullPowerPlanSupportDisabled, al
0x180007bd0  jnz     short loc_180007BFF
0x180007bd2  mov     r8, qword ptr [rbp+70h+Uuid.Data4]
0x180007bd6  xor     ecx, ecx
0x180007bd8  mov     r9, qword ptr [rbp+70h+Uuid.Data1]
0x180007bdc  nop     dword ptr [rax+00h]
0x180007be0  lea     rdx, UmpoOverlaySchemeGuids
0x180007be7  mov     rdx, [rdx+rcx*8]
0x180007beb  cmp     r9, [rdx]
0x180007bee  jnz     short loc_180007BF6
0x180007bf0  cmp     r8, [rdx+8]
0x180007bf4  jz      short loc_180007C5A
0x180007bf6  inc     ecx
0x180007bf8  cmp     ecx, 3
0x180007bfb  jb      short loc_180007BE0
0x180007bfd  jmp     short loc_180007C19
0x180007bff  mov     r8d, 10h; Size
0x180007c05  lea     rdx, [rbp+70h+Uuid]; Buf2
0x180007c09  lea     rcx, GUID_TYPICAL_POWER_SAVINGS; Buf1
0x180007c10  call    memcmp_0
0x180007c15  test    eax, eax
0x180007c17  jz      short loc_180007C58
0x180007c19  mov     r8d, 10h; Size
0x180007c1f  lea     rdx, [rbp+70h+Uuid]; Buf2
0x180007c23  lea     rcx, GUID_POWER_SCHEME_ULTIMATE_PERFORMANCE; Buf1
0x180007c2a  call    memcmp_0
0x180007c2f  test    eax, eax
0x180007c31  jnz     short loc_180007C42
0x180007c33  cmp     cs:UmpoUltimatePerfSchemeAllowed, al
0x180007c39  jnz     short loc_180007C58
0x180007c3b  mov     [rsp+170h+var_12F], 1
0x180007c40  jmp     short loc_180007C5A
0x180007c42  cmp     [rbp+70h+arg_30], 0
0x180007c49  jnz     short loc_180007C58
0x180007c4b  lea     rcx, [rbp+70h+Uuid]
0x180007c4f  call    UmpoInternalIsSchemeVisible
0x180007c54  test    al, al
0x180007c56  jz      short loc_180007C5A
0x180007c58  inc     ebx
0x180007c5a  mov     eax, [rsp+170h+var_124]
  ... truncated ...
```
