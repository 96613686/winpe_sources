# CWcnIdentity::InitializeToSelf(void)

- ea: `0x18000b850`
- end: `0x18000c4c3`
- name: `?InitializeToSelf@CWcnIdentity@@QEAAJXZ`
- size: `3187`
- prototype: `__int64 __fastcall(CWcnIdentity *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180003dec`

## callees

- `0x180004f2c`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000a558`
- `0x18000a5ac`
- `0x18000a6d4`
- `0x18000b850`
- `0x18000c4cc`
- `0x180016118`
- `0x180016d20`
- `0x18001a57c`
- `0x18001b548`
- `0x18001b82c`
- `0x18001bbd8`
- `0x18001cdd0`
- `0x180053004`
- `0x180056144`
- `0x180056df2`
- `0x180056e30`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18000be48`
- `msvcrt!swprintf_s` at `0x18000be48`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b97c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b97c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c444`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c444`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b903`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b903`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bad3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bad3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd82`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000bab7`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000bab7`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18000bd59`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18000bd59`

## pseudocode

```c
__int64 __fastcall CWcnIdentity::InitializeToSelf(CWcnIdentity *this)
{
  const char *Indent; // rax
  __int64 v3; // r10
  RTL_SRWLOCK *v4; // rsi
  const char *v5; // rax
  __int64 v6; // r10
  LSTATUS ValueW; // eax
  unsigned int v8; // ebx
  signed int v9; // ebx
  _BYTE *v10; // r10
  int v11; // eax
  unsigned int v12; // eax
  __int64 v13; // r10
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v16; // rcx
  const char *v17; // rax
  __int64 v18; // r10
  unsigned int v19; // eax
  char v20; // r10
  int v21; // eax
  unsigned int v22; // eax
  __int64 v23; // r10
  CWcnAttributeDatabase *v24; // rdi
  int appended; // eax
  _QWORD *v26; // rcx
  unsigned int v27; // ebx
  unsigned int v28; // eax
  char v29; // r10
  int v30; // ebx
  bool v31; // al
  unsigned int v32; // r8d
  CWcnIdentity *v33; // rcx
  enum tagWCN_VALUE_TYPE_RF_BANDS RfBands; // eax
  unsigned int v35; // eax
  __int64 v36; // r10
  LPDWORD pdwType; // [rsp+20h] [rbp-E0h]
  PVOID pvData; // [rsp+28h] [rbp-D8h]
  bool v40; // [rsp+40h] [rbp-C0h] BYREF
  bool v41; // [rsp+41h] [rbp-BFh] BYREF
  unsigned __int8 v42[8]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD nSize; // [rsp+54h] [rbp-ACh] BYREF
  _BYTE v45[32]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v46[24]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v47[48]; // [rsp+90h] [rbp-70h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Buffer[16]; // [rsp+1E0h] [rbp+E0h] BYREF
  OLECHAR sz[40]; // [rsp+200h] [rbp+100h] BYREF
  wchar_t v51[32]; // [rsp+250h] [rbp+150h] BYREF

  CWcnAttribute::CWcnAttribute((CWcnAttribute *)v46);
  memset_0(&VersionInformation, 0, sizeof(VersionInformation));
  v40 = 1;
  v41 = 1;
  *(_QWORD *)v42 = 0;
  CSbSafeBuffer::CSbSafeBuffer((CSbSafeBuffer *)v45);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v3 + 16), 20, WPP_e632221d673033b22bf624a0da3869d5_Traceguids, Indent);
  }
  v4 = (RTL_SRWLOCK *)((char *)this + 32);
  AcquireSRWLockExclusive((PSRWLOCK)this + 4);
  pcbData = 76;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v5 = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 10, WPP_e632221d673033b22bf624a0da3869d5_Traceguids, v5);
  }
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Cryptography", L"MachineGuid", 2u, 0, sz, &pcbData);
  if ( ValueW )
  {
    if ( ValueW > 0 )
      v8 = (unsigned __int16)ValueW | 0x80070000;
    else
      v8 = ValueW;
    v9 = v8 | 0x80000000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_23;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_e632221d673033b22bf624a0da3869d5_Traceguids,
        (unsigned int)ValueW,
        v9);
LABEL_18:
      v10 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    sz[37] = 0;
    v11 = WcnGuidFromString(sz, (LPIID)this + 1);
    v9 = v11;
    if ( v11 >= 0 )
      goto LABEL_18;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_198;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_e632221d673033b22bf624a0da3869d5_Traceguids,
        (unsigned int)v11);
      goto LABEL_18;
    }
  }
  if ( v10 != (_BYTE *)&WPP_GLOBAL_Control )
  {
    if ( v9 >= 0 && v10[25] < 6u )
      goto LABEL_28;
    v12 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v13 + 16), 13, (unsigned int)WPP_e632221d673033b22bf624a0da3869d5_Traceguids, v12, v9);
    v10 = WPP_GLOBAL_Control;
  }
LABEL_23:
  if ( v9 < 0 )
  {
    if ( v10 != (_BYTE *)&WPP_GLOBAL_Control && v10[25] >= 2u )
    {
      v14 = 21;
LABEL_27:
      v15 = (unsigned int)v9;
      v16 = *((_QWORD *)v10 + 2);
LABEL_197:
      WPP_SF_d(v16, v14, WPP_e632221d673033b22bf624a0da3869d5_Traceguids, v15);
      goto LABEL_198;
    }
    goto LABEL_198;
  }
LABEL_28:
  nSize = 16;
  if ( v10 != (_BYTE *)&WPP_GLOBAL_Control && v10[25] >= 6u )
  {
    v17 = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v18 + 16), 14, WPP_e632221d673033b22bf624a0da3869d5_Traceguids, v17);
  }
  if ( !GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      GetLastError();
      v19 = (unsigned int)GetIndent(0);
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        (unsigned int)WPP_e632221d673033b22bf624a0da3869d5_Traceguids,
        v19,
        v20);
    }
    Buffer[0] = 0;
  }
  v21 = CWcnAttribute::SetValueFromString((CWcnAttribute *)v46, WCN_TYPE_DEVICE_NAME, Buffer);
  v9 = v21;
  if ( v21 >= 0 )
    goto LABEL_40;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_198;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      WPP_e632221d673033b22bf624a0da3869d5_Traceguids,
      (unsigned int)v21);
LABEL_40:
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 != (_BYTE *)&WPP_GLOBAL_Control )
  {
    if ( v9 >= 0 && v10[25] < 6u )
    {
LABEL_49:
      v24 = (CWcnIdentity *)((char *)this + 40);
      appended = CWcnAttributeDatabase::AppendAttribute(v24, (const struct CWcnAttribute *)v46);
      v9 = appended;
      if ( appended >= 0 )
      {
        appended = CWcnAttribute::SetValueFromString((CWcnAttribute *)v46, WCN_TYPE_MANUFACTURER, L"Microsoft");
        v9 = appended;
        if ( appended >= 0 )
        {
          appended = CWcnAttributeDatabase::AppendAttribute(v24, (const struct CWcnAttribute *)v46);
          v9 = appended;
          if ( appended >= 0 )
          {
            appended = CWcnAttribute::SetValueFromString((CWcnAttribute *)v46, WCN_TYPE_MODEL_NAME, L"Windows");
            v9 = appended;
            if ( appended >= 0 )
            {
              appended = CWcnAttributeDatabase::AppendAttribute(v24, (const struct CWcnAttribute *)v46);
              v9 = appended;
              if ( appended >= 0 )
              {
                appended = CWcnAttribute::SetValueFromString((CWcnAttribute *)v46, WCN_TYPE_SERIAL_NUMBER, L"0");
                v9 = appended;
                if ( appended >= 0 )
                {
                  appended = CWcnAttributeDatabase::AppendAttribute(v24, (const struct CWcnAttribute *)v46);
                  v9 = appended;
                  if ( appended >= 0 )
                  {
                    VersionInformation.dwOSVersionInfoSize = 276;
                    if ( GetVersionExW(&VersionInformation) )
                    {
                      v27 = VersionInformation.dwMinorVersion + (VersionInformation.dwMajorVersion << 16);
                    }
                    else
                    {
                      v27 = 0;
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                      {
                        GetLastError();
                        v28 = (unsigned int)GetIndent(0);
                        WPP_SF_sd(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          30,
                          (unsigned int)WPP_e632221d673033b22bf624a0da3869d5_Traceguids,
                          v28,
                          v29);
                      }
                    }
                    appended = CWcnAttribute::SetValueFromInteger((CWcnAttribute *)v46, WCN_TYPE_OS_VERSION, v27);
                    v9 = appended;
                    if ( appended >= 0 )
                    {
                      appended = CWcnAttributeDatabase::AppendAttribute(v24, (const struct CWcnAttribute *)v46);
                      v9 = appended;
                      if ( appended >= 0 )
                      {
                        LODWORD(pvData) = VersionInformation.dwBuildNumber;
                        LODWORD(pdwType) = VersionInformation.dwMinorVersion;
                        swprintf_s(v51, 0x20u, L"%u.%u.%u", VersionInformation.dwMajorVersion, pdwType, pvData);
                        appended = CWcnAttribute::SetValueFromString((CWcnAttribute *)v46, WCN_TYPE_MODEL_NUMBER, v51);
                        v9 = appended;
                        if ( appended >= 0 )
                        {
                          appended = CWcnAttributeDatabase::AppendAttribute(v24, (const struct CWcnAttribute *)v46);
                          v9 = appended;
                          if ( appended >= 0 )
                          {
                            *(_WORD *)v42 = 256;
                            *(_DWORD *)&v42[2] = 82989056;
                            *(_WORD *)&v42[6] = 256;
                            appended = CSbSafeBuffer::CopyFromBuffer((CSbSafeBuffer *)v45, v42, 8u);
                            v9 = appended;
                            if ( appended >= 0 )
                            {
                              appended = CWcnAttribute::SetValueFromBlob(
                                           (CWcnAttribute *)v46,
                                           WCN_TYPE_PRIMARY_DEVICE_TYPE,
                                           (const struct CSbSafeBuffer *)v45);
                              v9 = appended;
                              if ( appended >= 0 )
                              {
                                appended = CWcnAttributeDatabase::AppendAttribute(
                                             v24,
                                             (const struct CWcnAttribute *)v46);
                                v9 = appended;
                                if ( appended >= 0 )
                                {
                                  appended = CWcnAttribute::SetValueFromInteger(
                                               (CWcnAttribute *)v46,
                                               WCN_TYPE_AUTHENTICATION_TYPE_FLAGS,
                                               0x33u);
                                  v9 = appended;
                                  if ( appended >= 0 )
                                  {
                                    appended = CWcnAttributeDatabase::AppendAttribute(
                                                 v24,
                                                 (const struct CWcnAttribute *)v46);
                                    v9 = appended;
                                    if ( appended >= 0 )
                                    {
                                      appended = CWcnAttribute::SetValueFromInteger(
                                                   (CWcnAttribute *)v46,
                                                   WCN_TYPE_ENCRYPTION_TYPE_FLAGS,
                                                   0xDu);
                                      v9 = appended;
                                      if ( appended >= 0 )
                                      {
                                        appended = CWcnAttributeDatabase::AppendAttribute(
                                                     v24,
                                                     (const struct CWcnAttribute *)v46);
                                        v9 = appended;
                                        if ( appended >= 0 )
                                        {
                                          appended = CWcnAttribute::SetValueFromInteger(
                                                       (CWcnAttribute *)v46,
                                                       WCN_TYPE_CONNECTION_TYPE_FLAGS,
                                                       3u);
                                          v9 = appended;
                                          if ( appended >= 0 )
                                          {
                                            appended = CWcnAttributeDatabase::AppendAttribute(
                                                         v24,
                                                         (const struct CWcnAttribute *)v46);
                                            v9 = appended;
                                            if ( appended >= 0 )
                                            {
                                              v30 = 17292;
                                              GetConfigMethodSetting(&v40, &v41);
                                              if ( v40 )
                                                v30 = 25484;
                                              if ( v41 )
                                                v30 |= 0x480u;
                                              v31 = IsNfcSupported();
                                              v32 = v30 | 0x70;
                                              if ( !v31 )
                                                v32 = v30;
                                              appended = CWcnAttribute::SetValueFromInteger(
                                                           (CWcnAttribute *)v46,
                                                           WCN_TYPE_CONFIG_METHODS,
                                                           v32);
                                              v9 = appended;
                                              if ( appended >= 0 )
                                              {
                                                appended = CWcnAttributeDatabase::AppendAttribute(
                                                             v24,
                                                             (const struct CWcnAttribute *)v46);
                                                v9 = appended;
                                                if ( appended >= 0 )
                                                {
                                                  appended = CWcnAttribute::SetValueFromInteger(
                                                               (CWcnAttribute *)v46,
                                                               WCN_TYPE_DEVICE_PASSWORD_ID,
                                                               0);
                                                  v9 = appended;
                                                  if ( appended >= 0 )
                                                  {
                                                    appended = CWcnAttributeDatabase::AppendAttribute(
                                                                 v24,
                                                                 (const struct CWcnAttribute *)v46);
                                                    v9 = appended;
                                                    if ( appended >= 0 )
                                                    {
                                                      appended = CWcnAttribute::SetValueFromInteger(
                                                                   (CWcnAttribute *)v46,
                                                                   WCN_TYPE_WI_FI_PROTECTED_SETUP_STATE,
                                                                   2u);
                                                      v9 = appended;
                                                      if ( appended >= 0 )
                                                      {
                                                        appended = CWcnAttributeDatabase::AppendAttribute(
                                                                     v24,
                                                                     (const struct CWcnAttribute *)v46);
                                                        v9 = appended;
                                                        if ( appended >= 0 )
                                                        {
                                                          RfBands = CWcnIdentity::LoadRfBands(v33);
                                                          appended = CWcnAttribute::SetValueFromInteger(
                                                                       (CWcnAttribute *)v46,
                                                                       WCN_TYPE_RF_BANDS,
                                                                       RfBands);
                                                          v9 = appended;
                                                          if ( appended >= 0 )
                                                          {
                                                            appended = CWcnAttributeDatabase::AppendAttribute(
                                                                         v24,
                                                                         (const struct CWcnAttribute *)v46);
                                                            v9 = appended;
                                                            if ( appended >= 0 )
                                                            {
                                                              appended = CWcnAttribute::SetValueFromInteger(
                                                                           (CWcnAttribute *)v46,
                                                                           WCN_TYPE_ASSOCIATION_STATE,
                                                                           1u);
                                                              v9 = appended;
                                                              if ( appended >= 0 )
                                                              {
                                                                appended = CWcnAttributeDatabase::AppendAttribute(
                                                                             v24,
                                                                             (const struct CWcnAttribute *)v46);
                                                                v9 = appended;
                                                                if ( appended >= 0 )
                                                                {
                                                                  appended = CWcnAttribute::SetValueFromInteger(
                                                                               (CWcnAttribute *)v46,
                                                                               WCN_TYPE_RESPONSE_TYPE,
                                                                               3u);
                                                                  v9 = appended;
                                                                  if ( appended >= 0 )
                                                                  {
                                                                    appended = CWcnAttributeDatabase::AppendAttribute(
                                                                                 v24,
                                                                                 (const struct CWcnAttribute *)v46);
                                                                    v9 = appended;
                                                                    if ( appended >= 0 )
                                                                    {
                                                                      appended = CWcnAttribute::SetValueFromInteger(
                                                                                   (CWcnAttribute *)v46,
                                                                                   WCN_TYPE_REQUEST_TYPE,
                                                                                   2u);
                                                                      v9 = appended;
                                                                      if ( appended >= 0 )
                                                                      {
                                                                        appended = CWcnAttributeDatabase::AppendAttribute(
                                                                                     v24,
                                                                                     (const struct CWcnAttribute *)v46);
                                                                        v9 = appended;
                                                                        if ( appended >= 0 )
                                                                          goto LABEL_198;
                                                                        v26 = WPP_GLOBAL_Control;
                                                                        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                                                          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                                                        {
                                                                          goto LABEL_198;
                                                                        }
                                                                        v14 = 57;
                                                                      }
                                                                      else
                                                                      {
                                                                        v26 = WPP_GLOBAL_Control;
                                                                        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                                                          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                                                        {
                                                                          goto LABEL_198;
                                                                        }
                                                                        v14 = 56;
                                                                      }
                                                                    }
                                                                    else
                                                                    {
                                                                      v26 = WPP_GLOBAL_Control;
                                                                      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                                                        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                                                      {
                                                                        goto LABEL_198;
                                                                      }
                                                                      v14 = 55;
                                                                    }
                                                                  }
                                                                  else
                                                                  {
                                                                    v26 = WPP_GLOBAL_Control;
                                                                    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                                                      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                                                    {
                                                                      goto LABEL_198;
                                                                    }
                                                                    v14 = 54;
                                                                  }
                                                                }
                                                                else
                                                                {
                                                                  v26 = WPP_GLOBAL_Control;
                                                                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                                                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                                                  {
                                                                    goto LABEL_198;
                                                                  }
                                                                  v14 = 53;
                                                                }
                                                              }
                                                              else
                                                              {
                                                                v26 = WPP_GLOBAL_Control;
                                                                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                                                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                                                {
                                                                  goto LABEL_198;
                                                                }
                                                                v14 = 52;
                                                              }
                                                            }
                                                            else
                                                            {
                                                              v26 = WPP_GLOBAL_Control;
                                                              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                                                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                                              {
                                                                goto LABEL_198;
                                                              }
                                                              v14 = 51;
                                                            }
                                                          }
                                                          else
                                                          {
                                                            v26 = WPP_GLOBAL_Control;
                                                            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                                              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                                            {
                                                              goto LABEL_198;
                                                            }
                                                            v14 = 50;
                                                          }
                                                        }
                                                        else
                                                        {
                                                          v26 = WPP_GLOBAL_Control;
                                                          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                                            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                                          {
                                                            goto LABEL_198;
                                                          }
                                                          v14 = 49;
                                                        }
                                                      }
                                                      else
                                                      {
                                                        v26 = WPP_GLOBAL_Control;
                                                        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                                          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                                        {
                                                          goto LABEL_198;
                                                        }
                                                        v14 = 48;
                                                      }
                                                    }
                                                    else
                                                    {
                                                      v26 = WPP_GLOBAL_Control;
                                                      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                                        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                                      {
                                                        goto LABEL_198;
                                                      }
                                                      v14 = 47;
                                                    }
                                                  }
                                                  else
                                                  {
                                                    v26 = WPP_GLOBAL_Control;
                                                    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                                      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                                    {
                                                      goto LABEL_198;
                                                    }
                                                    v14 = 46;
                                                  }
                                                }
                                                else
                                                {
                                                  v26 = WPP_GLOBAL_Control;
                                                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                                  {
                                                    goto LABEL_198;
                                                  }
                                                  v14 = 45;
                                                }
                                              }
                                              else
                                              {
                                                v26 = WPP_GLOBAL_Control;
                                                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                                {
                                                  goto LABEL_198;
                                                }
                                                v14 = 44;
                                              }
                                            }
                                            else
                                            {
                                              v26 = WPP_GLOBAL_Control;
                                              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                              {
                                                goto LABEL_198;
                                              }
                                              v14 = 43;
                                            }
                                          }
                                          else
                                          {
                                            v26 = WPP_GLOBAL_Control;
                                            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                            {
                                              goto LABEL_198;
                                            }
                                            v14 = 42;
                                          }
                                        }
                                        else
                                        {
                                          v26 = WPP_GLOBAL_Control;
                                          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                          {
                                            goto LABEL_198;
                                          }
                                          v14 = 41;
                                        }
                                      }
                                      else
                                      {
                                        v26 = WPP_GLOBAL_Control;
                                        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                        {
                                          goto LABEL_198;
                                        }
                                        v14 = 40;
                                      }
                                    }
                                    else
                                    {
                                      v26 = WPP_GLOBAL_Control;
                                      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                      {
                                        goto LABEL_198;
                                      }
                                      v14 = 39;
                                    }
                                  }
                                  else
                                  {
                                    v26 = WPP_GLOBAL_Control;
                                    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                    {
                                      goto LABEL_198;
                                    }
                                    v14 = 38;
                                  }
                                }
                                else
                                {
                                  v26 = WPP_GLOBAL_Control;
                                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                  {
                                    goto LABEL_198;
                                  }
                                  v14 = 37;
                                }
                              }
                              else
                              {
                                v26 = WPP_GLOBAL_Control;
                                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                {
                                  goto LABEL_198;
                                }
                                v14 = 36;
                              }
                            }
                            else
                            {
                              v26 = WPP_GLOBAL_Control;
                              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                              {
                                goto LABEL_198;
                              }
                              v14 = 35;
                            }
                          }
                          else
                          {
                            v26 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                            {
                              goto LABEL_198;
                            }
                            v14 = 34;
                          }
                        }
                        else
                        {
                          v26 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                          {
                            goto LABEL_198;
                          }
                          v14 = 33;
                        }
                      }
                      else
                      {
                        v26 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                        {
                          goto LABEL_198;
                        }
                        v14 = 32;
                      }
                    }
                    else
                    {
                      v26 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                      {
                        goto LABEL_198;
                      }
                      v14 = 31;
                    }
                  }
                  else
                  {
                    v26 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                    {
                      goto LABEL_198;
                    }
                    v14 = 29;
                  }
                }
                else
                {
                  v26 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                    goto LABEL_198;
                  v14 = 28;
                }
              }
              else
              {
                v26 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  goto LABEL_198;
                v14 = 27;
              }
            }
            else
            {
              v26 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                goto LABEL_198;
              v14 = 26;
            }
          }
          else
          {
            v26 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              goto LABEL_198;
            v14 = 25;
          }
        }
        else
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_198;
          v14 = 24;
        }
      }
      else
      {
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_198;
        v14 = 23;
      }
      v16 = v26[2];
      v15 = (unsigned int)appended;
      goto LABEL_197;
    }
    v22 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v23 + 16), 18, (unsigned int)WPP_e632221d673033b22bf624a0da3869d5_Traceguids, v22, v9);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v9 >= 0 )
    goto LABEL_49;
  if ( v10 != (_BYTE *)&WPP_GLOBAL_Control && v10[25] >= 2u )
  {
    v14 = 22;
    goto LABEL_27;
  }
LABEL_198:
  ReleaseSRWLockExclusive(v4);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v9 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v35 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v36 + 16), 58, (unsigned int)WPP_e632221d673033b22bf624a0da3869d5_Traceguids, v35, v9);
  }
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v45);
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v47);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000b850  mov     [rsp-8+arg_8], rbx
0x18000b855  mov     [rsp-8+arg_10], rsi
0x18000b85a  push    rbp
0x18000b85b  push    rdi
0x18000b85c  push    r12
0x18000b85e  push    r14
0x18000b860  push    r15
0x18000b862  lea     rbp, [rsp-1A0h]
0x18000b86a  sub     rsp, 2A0h
0x18000b871  mov     rax, cs:__security_cookie
0x18000b878  xor     rax, rsp
0x18000b87b  mov     [rbp+1C0h+var_30], rax
0x18000b882  mov     rdi, rcx
0x18000b885  lea     rcx, [rsp+2C0h+var_248]; this
0x18000b88a  call    ??0CWcnAttribute@@QEAA@XZ; CWcnAttribute::CWcnAttribute(void)
0x18000b88f  nop
0x18000b890  xor     edx, edx; Val
0x18000b892  mov     r8d, 114h; Size
0x18000b898  lea     rcx, [rbp+1C0h+VersionInformation]; void *
0x18000b89c  call    memset_0
0x18000b8a1  mov     ebx, 1
0x18000b8a6  mov     [rsp+2C0h+var_280], bl
0x18000b8aa  mov     [rsp+2C0h+var_27F], bl
0x18000b8ae  mov     qword ptr [rsp+2C0h+var_278], 0
0x18000b8b7  lea     rcx, [rsp+2C0h+var_268]; this
0x18000b8bc  call    ??0CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::CSbSafeBuffer(void)
0x18000b8c1  nop
0x18000b8c2  lea     r15, WPP_GLOBAL_Control
0x18000b8c9  lea     r12, WPP_e632221d673033b22bf624a0da3869d5_Traceguids
0x18000b8d0  mov     r10, cs:WPP_GLOBAL_Control
0x18000b8d7  cmp     r10, r15
0x18000b8da  jz      short loc_18000B8FC
0x18000b8dc  cmp     byte ptr [r10+19h], 6
0x18000b8e1  jb      short loc_18000B8FC
0x18000b8e3  mov     ecx, ebx; int
0x18000b8e5  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000b8ea  lea     edx, [rbx+13h]
0x18000b8ed  mov     r9, rax
0x18000b8f0  mov     r8, r12
0x18000b8f3  mov     rcx, [r10+10h]
0x18000b8f7  call    WPP_SF_s
0x18000b8fc  lea     rsi, [rdi+20h]
0x18000b900  mov     rcx, rsi; SRWLock
0x18000b903  call    cs:__imp_AcquireSRWLockExclusive
0x18000b909  mov     [rsp+2C0h+var_270], 4Ch ; 'L'
0x18000b911  mov     r10, cs:WPP_GLOBAL_Control
0x18000b918  cmp     r10, r15
0x18000b91b  jz      short loc_18000B93F
0x18000b91d  cmp     byte ptr [r10+19h], 6
0x18000b922  jb      short loc_18000B93F
0x18000b924  mov     ecx, ebx; int
0x18000b926  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000b92b  mov     edx, 0Ah
0x18000b930  mov     r9, rax
0x18000b933  mov     r8, r12
0x18000b936  mov     rcx, [r10+10h]
0x18000b93a  call    WPP_SF_s
0x18000b93f  lea     rax, [rsp+2C0h+var_270]
0x18000b944  mov     [rsp+2C0h+pcbData], rax; pcbData
0x18000b949  lea     rax, [rbp+1C0h+sz]
0x18000b950  mov     [rsp+2C0h+pvData], rax; pvData
0x18000b955  mov     [rsp+2C0h+pdwType], 0; pdwType
0x18000b95e  mov     r14d, 2
0x18000b964  mov     r9d, r14d; dwFlags
0x18000b967  lea     r8, Value; "MachineGuid"
0x18000b96e  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Cryptography"
0x18000b975  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000b97c  call    cs:__imp_RegGetValueW
0x18000b982  test    eax, eax
0x18000b984  jz      short loc_18000B9CB
0x18000b986  jg      short loc_18000B98C
0x18000b988  mov     ebx, eax
0x18000b98a  jmp     short loc_18000B995
0x18000b98c  movzx   ebx, ax
0x18000b98f  or      ebx, 80070000h
0x18000b995  or      ebx, 80000000h
0x18000b99b  mov     r10, cs:WPP_GLOBAL_Control
0x18000b9a2  cmp     r10, r15
0x18000b9a5  jz      loc_18000BA52
0x18000b9ab  cmp     [r10+19h], r14b
0x18000b9af  jb      short loc_18000BA1B
0x18000b9b1  mov     edx, 0Bh
0x18000b9b6  mov     dword ptr [rsp+2C0h+pdwType], ebx
0x18000b9ba  mov     r9d, eax
0x18000b9bd  mov     r8, r12
0x18000b9c0  mov     rcx, [r10+10h]
0x18000b9c4  call    WPP_SF_Dd
0x18000b9c9  jmp     short loc_18000BA14
0x18000b9cb  xor     eax, eax
0x18000b9cd  mov     [rbp+1C0h+var_76], ax
0x18000b9d4  lea     rdx, [rdi+10h]; lpiid
0x18000b9d8  lea     rcx, [rbp+1C0h+sz]; lpsz
0x18000b9df  call    ?WcnGuidFromString@@YAJPEBGPEAU_GUID@@@Z; WcnGuidFromString(ushort const *,_GUID *)
0x18000b9e4  mov     ebx, eax
0x18000b9e6  test    eax, eax
0x18000b9e8  jns     short loc_18000BA14
0x18000b9ea  mov     r10, cs:WPP_GLOBAL_Control
0x18000b9f1  cmp     r10, r15
0x18000b9f4  jz      loc_18000C441
0x18000b9fa  cmp     [r10+19h], r14b
0x18000b9fe  jb      short loc_18000BA1B
0x18000ba00  mov     edx, 0Ch
0x18000ba05  mov     r9d, eax
0x18000ba08  mov     r8, r12
0x18000ba0b  mov     rcx, [r10+10h]
0x18000ba0f  call    WPP_SF_d
0x18000ba14  mov     r10, cs:WPP_GLOBAL_Control
0x18000ba1b  cmp     r10, r15
0x18000ba1e  jz      short loc_18000BA52
0x18000ba20  test    ebx, ebx
0x18000ba22  js      short loc_18000BA2B
0x18000ba24  cmp     byte ptr [r10+19h], 6
0x18000ba29  jb      short loc_18000BA7A
0x18000ba2b  or      ecx, 0FFFFFFFFh; int
0x18000ba2e  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000ba33  mov     edx, 0Dh
0x18000ba38  mov     dword ptr [rsp+2C0h+pdwType], ebx
0x18000ba3c  mov     r9, rax
0x18000ba3f  mov     r8, r12
0x18000ba42  mov     rcx, [r10+10h]
0x18000ba46  call    WPP_SF_sd
0x18000ba4b  mov     r10, cs:WPP_GLOBAL_Control
0x18000ba52  test    ebx, ebx
0x18000ba54  jns     short loc_18000BA7A
0x18000ba56  cmp     r10, r15
0x18000ba59  jz      loc_18000C441
0x18000ba5f  cmp     [r10+19h], r14b
0x18000ba63  jb      loc_18000C441
0x18000ba69  mov     edx, 15h
0x18000ba6e  mov     r9d, ebx
0x18000ba71  mov     rcx, [r10+10h]
0x18000ba75  jmp     loc_18000C439
0x18000ba7a  mov     ebx, 10h
0x18000ba7f  mov     [rsp+2C0h+nSize], ebx
0x18000ba83  cmp     r10, r15
0x18000ba86  jz      short loc_18000BAA9
0x18000ba88  cmp     byte ptr [r10+19h], 6
0x18000ba8d  jb      short loc_18000BAA9
0x18000ba8f  lea     ecx, [rbx-0Fh]; int
0x18000ba92  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000ba97  lea     edx, [rbx-2]
0x18000ba9a  mov     r9, rax
0x18000ba9d  mov     r8, r12
0x18000baa0  mov     rcx, [r10+10h]
0x18000baa4  call    WPP_SF_s
0x18000baa9  lea     r8, [rsp+2C0h+nSize]; nSize
0x18000baae  lea     rdx, [rbp+1C0h+Buffer]; lpBuffer
0x18000bab5  xor     ecx, ecx; NameType
0x18000bab7  call    cs:__imp_GetComputerNameExW
0x18000babd  test    eax, eax
0x18000babf  jnz     short loc_18000BB09
0x18000bac1  mov     rax, cs:WPP_GLOBAL_Control
0x18000bac8  cmp     rax, r15
0x18000bacb  jz      short loc_18000BB00
0x18000bacd  cmp     byte ptr [rax+19h], 3
0x18000bad1  jb      short loc_18000BB00
0x18000bad3  call    cs:__imp_GetLastError
0x18000bad9  mov     r10d, eax
0x18000badc  xor     ecx, ecx; int
0x18000bade  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000bae3  mov     edx, ebx
0x18000bae5  mov     dword ptr [rsp+2C0h+pdwType], r10d
0x18000baea  mov     r9, rax
0x18000baed  mov     r8, r12
0x18000baf0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000baf7  mov     rcx, [rcx+10h]
0x18000bafb  call    WPP_SF_sd
0x18000bb00  xor     eax, eax
0x18000bb02  mov     [rbp+1C0h+Buffer], ax
0x18000bb09  lea     r8, [rbp+1C0h+Buffer]; unsigned __int16 *
0x18000bb10  mov     edx, 0Ch; enum tagWCN_ATTRIBUTE_TYPE
0x18000bb15  lea     rcx, [rsp+2C0h+var_248]; this
0x18000bb1a  call    ?SetValueFromString@CWcnAttribute@@QEAAJW4tagWCN_ATTRIBUTE_TYPE@@PEBG@Z; CWcnAttribute::SetValueFromString(tagWCN_ATTRIBUTE_TYPE,ushort const *)
0x18000bb1f  mov     ebx, eax
0x18000bb21  test    eax, eax
0x18000bb23  jns     short loc_18000BB4F
0x18000bb25  mov     r10, cs:WPP_GLOBAL_Control
0x18000bb2c  cmp     r10, r15
0x18000bb2f  jz      loc_18000C441
0x18000bb35  cmp     [r10+19h], r14b
0x18000bb39  jb      short loc_18000BB56
0x18000bb3b  mov     edx, 11h
0x18000bb40  mov     r9d, eax
0x18000bb43  mov     r8, r12
0x18000bb46  mov     rcx, [r10+10h]
0x18000bb4a  call    WPP_SF_d
0x18000bb4f  mov     r10, cs:WPP_GLOBAL_Control
0x18000bb56  cmp     r10, r15
0x18000bb59  jz      short loc_18000BB8D
0x18000bb5b  test    ebx, ebx
0x18000bb5d  js      short loc_18000BB66
0x18000bb5f  cmp     byte ptr [r10+19h], 6
0x18000bb64  jb      short loc_18000BBAE
0x18000bb66  or      ecx, 0FFFFFFFFh; int
0x18000bb69  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000bb6e  mov     edx, 12h
0x18000bb73  mov     dword ptr [rsp+2C0h+pdwType], ebx
0x18000bb77  mov     r9, rax
0x18000bb7a  mov     r8, r12
0x18000bb7d  mov     rcx, [r10+10h]
0x18000bb81  call    WPP_SF_sd
0x18000bb86  mov     r10, cs:WPP_GLOBAL_Control
0x18000bb8d  test    ebx, ebx
0x18000bb8f  jns     short loc_18000BBAE
0x18000bb91  cmp     r10, r15
0x18000bb94  jz      loc_18000C441
0x18000bb9a  cmp     [r10+19h], r14b
0x18000bb9e  jb      loc_18000C441
0x18000bba4  mov     edx, 16h
0x18000bba9  jmp     loc_18000BA6E
0x18000bbae  add     rdi, 28h ; '('
0x18000bbb2  lea     rdx, [rsp+2C0h+var_248]; struct CWcnAttribute *
0x18000bbb7  mov     rcx, rdi; this
0x18000bbba  call    ?AppendAttribute@CWcnAttributeDatabase@@QEAAJPEBVCWcnAttribute@@@Z; CWcnAttributeDatabase::AppendAttribute(CWcnAttribute const *)
0x18000bbbf  mov     ebx, eax
0x18000bbc1  test    eax, eax
0x18000bbc3  jns     short loc_18000BBE9
0x18000bbc5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bbcc  cmp     rcx, r15
0x18000bbcf  jz      loc_18000C441
0x18000bbd5  cmp     [rcx+19h], r14b
0x18000bbd9  jb      loc_18000C441
0x18000bbdf  mov     edx, 17h
0x18000bbe4  jmp     loc_18000C432
0x18000bbe9  lea     r8, aMicrosoft; "Microsoft"
0x18000bbf0  mov     edx, 1Ch; enum tagWCN_ATTRIBUTE_TYPE
0x18000bbf5  lea     rcx, [rsp+2C0h+var_248]; this
0x18000bbfa  call    ?SetValueFromString@CWcnAttribute@@QEAAJW4tagWCN_ATTRIBUTE_TYPE@@PEBG@Z; CWcnAttribute::SetValueFromString(tagWCN_ATTRIBUTE_TYPE,ushort const *)
0x18000bbff  mov     ebx, eax
0x18000bc01  test    eax, eax
0x18000bc03  jns     short loc_18000BC29
0x18000bc05  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc0c  cmp     rcx, r15
0x18000bc0f  jz      loc_18000C441
0x18000bc15  cmp     [rcx+19h], r14b
0x18000bc19  jb      loc_18000C441
0x18000bc1f  mov     edx, 18h
0x18000bc24  jmp     loc_18000C432
0x18000bc29  lea     rdx, [rsp+2C0h+var_248]; struct CWcnAttribute *
0x18000bc2e  mov     rcx, rdi; this
0x18000bc31  call    ?AppendAttribute@CWcnAttributeDatabase@@QEAAJPEBVCWcnAttribute@@@Z; CWcnAttributeDatabase::AppendAttribute(CWcnAttribute const *)
0x18000bc36  mov     ebx, eax
0x18000bc38  test    eax, eax
0x18000bc3a  jns     short loc_18000BC60
0x18000bc3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc43  cmp     rcx, r15
0x18000bc46  jz      loc_18000C441
0x18000bc4c  cmp     [rcx+19h], r14b
0x18000bc50  jb      loc_18000C441
0x18000bc56  mov     edx, 19h
0x18000bc5b  jmp     loc_18000C432
0x18000bc60  lea     r8, aWindows; "Windows"
0x18000bc67  mov     edx, 1Eh; enum tagWCN_ATTRIBUTE_TYPE
0x18000bc6c  lea     rcx, [rsp+2C0h+var_248]; this
0x18000bc71  call    ?SetValueFromString@CWcnAttribute@@QEAAJW4tagWCN_ATTRIBUTE_TYPE@@PEBG@Z; CWcnAttribute::SetValueFromString(tagWCN_ATTRIBUTE_TYPE,ushort const *)
0x18000bc76  mov     ebx, eax
0x18000bc78  test    eax, eax
0x18000bc7a  jns     short loc_18000BCA0
0x18000bc7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc83  cmp     rcx, r15
0x18000bc86  jz      loc_18000C441
0x18000bc8c  cmp     [rcx+19h], r14b
0x18000bc90  jb      loc_18000C441
0x18000bc96  mov     edx, 1Ah
0x18000bc9b  jmp     loc_18000C432
0x18000bca0  lea     rdx, [rsp+2C0h+var_248]; struct CWcnAttribute *
0x18000bca5  mov     rcx, rdi; this
0x18000bca8  call    ?AppendAttribute@CWcnAttributeDatabase@@QEAAJPEBVCWcnAttribute@@@Z; CWcnAttributeDatabase::AppendAttribute(CWcnAttribute const *)
0x18000bcad  mov     ebx, eax
0x18000bcaf  test    eax, eax
0x18000bcb1  jns     short loc_18000BCD7
0x18000bcb3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bcba  cmp     rcx, r15
0x18000bcbd  jz      loc_18000C441
0x18000bcc3  cmp     [rcx+19h], r14b
0x18000bcc7  jb      loc_18000C441
0x18000bccd  mov     edx, 1Bh
0x18000bcd2  jmp     loc_18000C432
0x18000bcd7  lea     r8, a0; "0"
0x18000bcde  mov     edx, 3Ah ; ':'; enum tagWCN_ATTRIBUTE_TYPE
0x18000bce3  lea     rcx, [rsp+2C0h+var_248]; this
0x18000bce8  call    ?SetValueFromString@CWcnAttribute@@QEAAJW4tagWCN_ATTRIBUTE_TYPE@@PEBG@Z; CWcnAttribute::SetValueFromString(tagWCN_ATTRIBUTE_TYPE,ushort const *)
0x18000bced  mov     ebx, eax
0x18000bcef  test    eax, eax
0x18000bcf1  jns     short loc_18000BD17
0x18000bcf3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bcfa  cmp     rcx, r15
0x18000bcfd  jz      loc_18000C441
0x18000bd03  cmp     [rcx+19h], r14b
0x18000bd07  jb      loc_18000C441
0x18000bd0d  mov     edx, 1Ch
0x18000bd12  jmp     loc_18000C432
0x18000bd17  lea     rdx, [rsp+2C0h+var_248]; struct CWcnAttribute *
0x18000bd1c  mov     rcx, rdi; this
0x18000bd1f  call    ?AppendAttribute@CWcnAttributeDatabase@@QEAAJPEBVCWcnAttribute@@@Z; CWcnAttributeDatabase::AppendAttribute(CWcnAttribute const *)
0x18000bd24  mov     ebx, eax
0x18000bd26  test    eax, eax
0x18000bd28  jns     short loc_18000BD4E
0x18000bd2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd31  cmp     rcx, r15
  ... truncated ...
```
