# Microsoft::Diagnostics::OsEvents::PerformAbnormalShutdownCheck(void)

- ea: `0x1802dae84`
- end: `0x1802db8b6`
- name: `?PerformAbnormalShutdownCheck@OsEvents@Diagnostics@Microsoft@@CAJXZ`
- size: `2610`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `24`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1802dade4`

## callees

- `0x18001d160`
- `0x180026ecc`
- `0x180026ef4`
- `0x1800277e8`
- `0x180027be0`
- `0x1800333b0`
- `0x180033f3c`
- `0x180046c94`
- `0x180052734`
- `0x18005b974`
- `0x1800a60e4`
- `0x1800a8e5c`
- `0x1800a9344`
- `0x1800e21c4`
- `0x18012de40`
- `0x18012de64`
- `0x18012eb08`
- `0x180167c8c`
- `0x1802da98c`
- `0x1802dab44`
- `0x1802dac2c`
- `0x1802dae84`
- `0x1802dc38c`
- `0x1802dd220`

## import_xrefs

- `ntdll!RtlCheckSystemBootStatusIntegrity` at `0x1802daec0`
- `ntdll!RtlCheckSystemBootStatusIntegrity` at `0x1802daec0`
- `ntdll!RtlCreateBootStatusDataFile` at `0x1802daed5`
- `ntdll!RtlCreateBootStatusDataFile` at `0x1802daed5`
- `ntdll!RtlRestoreSystemBootStatusDefaults` at `0x1802db111`
- `ntdll!RtlRestoreSystemBootStatusDefaults` at `0x1802db111`
- `ntdll!RtlGetSystemBootStatus` at `0x1802db22d`
- `ntdll!RtlGetSystemBootStatus` at `0x1802db22d`
- `ntdll!RtlComputeCrc32` at `0x1802db2e3`
- `ntdll!RtlComputeCrc32` at `0x1802db2e3`
- `ntdll!RtlSetSystemBootStatus` at `0x1802db307`
- `ntdll!RtlSetSystemBootStatus` at `0x1802db307`
- `ntdll!NtQuerySystemInformationEx` at `0x1802db5c8`
- `ntdll!NtQuerySystemInformationEx` at `0x1802db60c`
- `ntdll!NtQuerySystemInformationEx` at `0x1802db5c8`
- `ntdll!NtQuerySystemInformationEx` at `0x1802db60c`
- `ntdll!NtQuerySystemTime` at `0x1802db289`
- `ntdll!NtQuerySystemTime` at `0x1802db289`
- `ntdll!NtQuerySystemInformation` at `0x1802db63b`
- `ntdll!NtQuerySystemInformation` at `0x1802db63b`
- `ntdll!NtPowerInformation` at `0x1802db0e4`
- `ntdll!NtPowerInformation` at `0x1802db432`
- `ntdll!NtPowerInformation` at `0x1802db483`
- `ntdll!NtPowerInformation` at `0x1802db4c6`
- `ntdll!NtPowerInformation` at `0x1802db53e`
- `ntdll!NtPowerInformation` at `0x1802db582`
- `ntdll!NtPowerInformation` at `0x1802db7d0`
- `ntdll!NtPowerInformation` at `0x1802db0e4`
- `ntdll!NtPowerInformation` at `0x1802db432`
- `ntdll!NtPowerInformation` at `0x1802db483`
- `ntdll!NtPowerInformation` at `0x1802db4c6`
- `ntdll!NtPowerInformation` at `0x1802db53e`
- `ntdll!NtPowerInformation` at `0x1802db582`
- `ntdll!NtPowerInformation` at `0x1802db7d0`

## string_xrefs

- `0x1802daef0`: `onecore\base\telemetry\utc\service\analysis\osevents.cpp`
- `0x1802daf22`: `onecore\base\telemetry\utc\service\analysis\osevents.cpp`
- `0x1802daf6b`: `onecore\base\telemetry\utc\service\analysis\osevents.cpp`
- `0x1802db12c`: `onecore\base\telemetry\utc\service\analysis\osevents.cpp`
- `0x1802db180`: `onecore\base\telemetry\utc\service\analysis\osevents.cpp`
- `0x1802db1d0`: `onecore\base\telemetry\utc\service\analysis\osevents.cpp`
- `0x1802db248`: `onecore\base\telemetry\utc\service\analysis\osevents.cpp`
- `0x1802db2a4`: `onecore\base\telemetry\utc\service\analysis\osevents.cpp`
- `0x1802db322`: `onecore\base\telemetry\utc\service\analysis\osevents.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
int Microsoft::Diagnostics::OsEvents::PerformAbnormalShutdownCheck(void)
{
  int v0; // eax
  void *v1; // rcx
  NTSTATUS BootStatusDataFile; // eax
  int BootStatusItem; // eax
  int v5; // ebx
  char v6; // di
  void *v7; // rbx
  void *v8; // rcx
  AbnormalShutdownData *v9; // rbx
  unsigned int v10; // r15d
  NTSTATUS v11; // eax
  int v12; // eax
  void *v13; // rcx
  int v14; // ebx
  LONG v15; // edi
  int v16; // eax
  void *v17; // rcx
  int v18; // ebx
  int v19; // eax
  int v20; // ebx
  int SystemBootStatus; // eax
  int v22; // ebx
  NTSTATUS v23; // eax
  int v24; // ebx
  int v25; // eax
  int v26; // ebx
  unsigned int v27; // esi
  void *v28; // rcx
  unsigned int v29; // esi
  unsigned int v30; // edi
  void *v31; // rcx
  int v32; // ecx
  void *v33; // rcx
  char v34; // al
  void *v35; // rcx
  int OutputBufferLength; // [rsp+20h] [rbp-5D8h]
  int OutputBufferLengtha; // [rsp+20h] [rbp-5D8h]
  char OutputBuffer; // [rsp+40h] [rbp-5B8h] BYREF
  char v39[3]; // [rsp+41h] [rbp-5B7h] BYREF
  unsigned int v40; // [rsp+44h] [rbp-5B4h] BYREF
  unsigned int v41; // [rsp+48h] [rbp-5B0h] BYREF
  __int64 InputBuffer; // [rsp+50h] [rbp-5A8h] BYREF
  DWORD v43; // [rsp+58h] [rbp-5A0h] BYREF
  int v44[2]; // [rsp+60h] [rbp-598h] BYREF
  __int64 v45; // [rsp+68h] [rbp-590h]
  AbnormalShutdownData *v46; // [rsp+70h] [rbp-588h] BYREF
  unsigned int v47; // [rsp+78h] [rbp-580h] BYREF
  int v48; // [rsp+7Ch] [rbp-57Ch]
  int v49; // [rsp+80h] [rbp-578h]
  _DWORD v50[3]; // [rsp+84h] [rbp-574h] BYREF
  int v51[4]; // [rsp+90h] [rbp-568h] BYREF
  _BYTE v52[16]; // [rsp+A0h] [rbp-558h] BYREF
  _OWORD v53[4]; // [rsp+B0h] [rbp-548h] BYREF
  __int128 v54; // [rsp+F0h] [rbp-508h] BYREF
  union _LARGE_INTEGER SystemTime[2]; // [rsp+100h] [rbp-4F8h] BYREF
  _BYTE v56[1128]; // [rsp+110h] [rbp-4E8h] BYREF
  _BYTE v57[56]; // [rsp+578h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5F8h] [rbp+0h]

  v40 = 0;
  v39[0] = 1;
  v0 = RtlCheckSystemBootStatusIntegrity(v39);
  if ( v0 == -1073741772 )
  {
    BootStatusDataFile = RtlCreateBootStatusDataFile();
    if ( BootStatusDataFile < 0 )
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x30B,
               (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\osevents.cpp",
               (const char *)(unsigned int)BootStatusDataFile,
               OutputBufferLength);
    v40 = 1000;
    goto LABEL_13;
  }
  if ( v0 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x313,
             (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\osevents.cpp",
             (const char *)(unsigned int)v0,
             OutputBufferLength);
  if ( !v39[0] )
  {
    v40 = 2000;
LABEL_13:
    v6 = 1;
    goto LABEL_14;
  }
  v41 = 0;
  BootStatusItem = Microsoft::Diagnostics::OsEvents::GetBootStatusItem(v1, RtlBsdItemVersionNumber, &v41);
  v5 = BootStatusItem;
  if ( BootStatusItem < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31F,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\osevents.cpp",
      (const char *)(unsigned int)BootStatusItem,
      OutputBufferLength);
    return v5;
  }
  v6 = 0;
  if ( v41 < 0xC8 )
  {
    v40 = 3000;
    goto LABEL_13;
  }
LABEL_14:
  v7 = operator new(0x148u);
  memset_0(v7, 0, 0x148u);
  v9 = AbnormalShutdownData::AbnormalShutdownData((AbnormalShutdownData *)v7);
  v46 = v9;
  v10 = MEMORY[0x7FFE02C4];
  v41 = MEMORY[0x7FFE02C4];
  if ( !v6 )
  {
    v40 = 0;
    v27 = Microsoft::Diagnostics::OsEvents::GetBootStatusItem(v8, RtlBsdItemShutdownBootId, &v40);
    v41 = 0;
    if ( (int)Microsoft::Diagnostics::OsEvents::GetBootStatusItem(v28, RtlBsdItemReportedAbnormalShutdownBootId, &v41) >= 0 )
      v29 = v27 >> 31;
    else
      LOBYTE(v29) = 1;
    Microsoft::Diagnostics::LifetimeManager::GetAuthorizationInfo(&gs_lifetimeManager, v52, 0);
    v30 = v41 + 1;
    if ( v40 + 1 >= v41 + 1 )
      v30 = v40 + 1;
    if ( v10 > 0x10 && v30 < v10 - 16 )
      v30 = v10 - 16;
    v49 = 0;
    v48 = 0;
    v50[0] = 0;
    std::wstring::wstring(&v54);
    v47 = 0;
    InputBuffer = 0;
    if ( v30 < v10 )
    {
      LODWORD(InputBuffer) = 7;
      if ( NtPowerInformation(SystemPowerStateLogging|0x40, &InputBuffer, 8u, v9, 0x20u) < 0 )
      {
        LOBYTE(v29) = 1;
        *(_OWORD *)v9 = 0;
        *((_OWORD *)v9 + 1) = 0;
      }
      if ( !*((_QWORD *)v9 + 2) )
        LOBYTE(v29) = 1;
      InputBuffer = 42;
      if ( NtPowerInformation(SystemPowerStateLogging|0x40, &InputBuffer, 8u, (char *)v9 + 232, 0x20u) < 0 )
      {
        LOBYTE(v29) = 1;
        *(_OWORD *)((char *)v9 + 232) = 0;
        *(_OWORD *)((char *)v9 + 248) = 0;
      }
      LODWORD(InputBuffer) = 22;
      if ( NtPowerInformation(SystemPowerStateLogging|0x40, &InputBuffer, 8u, (char *)v9 + 32, 0x40u) < 0 )
      {
        LOBYTE(v29) = 1;
        memset_0(v53, 0, sizeof(v53));
        *((_OWORD *)v9 + 2) = v53[0];
        *((_OWORD *)v9 + 3) = v53[1];
        *((_OWORD *)v9 + 4) = v53[2];
        *((_OWORD *)v9 + 5) = v53[3];
      }
      LODWORD(InputBuffer) = 29;
      if ( NtPowerInformation(SystemPowerStateLogging|0x40, &InputBuffer, 8u, (char *)v9 + 184, 0x30u) < 0 )
      {
        *(_OWORD *)((char *)v9 + 184) = 0;
        *(_OWORD *)((char *)v9 + 200) = 0;
        *(_OWORD *)((char *)v9 + 216) = 0;
      }
      LODWORD(InputBuffer) = 86;
      if ( NtPowerInformation(SystemPowerStateLogging|0x40, &InputBuffer, 8u, (char *)v9 + 264, 8u) < 0 )
        *((_QWORD *)v9 + 33) = 0;
      *((_DWORD *)v9 + 44) = 7;
      if ( (int)NtQuerySystemInformationEx(72, (char *)v9 + 176, 4, (char *)v9 + 176, 8, 0) >= 0 )
      {
        v49 = *((_DWORD *)v9 + 45);
        if ( v49 )
        {
          *((_DWORD *)v9 + 44) = 8;
          if ( (int)NtQuerySystemInformationEx(72, (char *)v9 + 176, 4, (char *)v9 + 176, 8, 0) >= 0 )
            v48 = *((_DWORD *)v9 + 45);
        }
      }
      if ( NtQuerySystemInformation(SystemBootEnvironmentInformation, (char *)v9 + 144, 0x20u, 0) < 0 )
      {
        *((_OWORD *)v9 + 9) = 0;
        *((_OWORD *)v9 + 10) = 0;
      }
      *(_QWORD *)v44 = L"CrashDumpEnabled";
      v45 = 16;
      *(_QWORD *)v51 = L"System\\CurrentControlSet\\Control\\CrashControl";
      *(_QWORD *)&v51[2] = 45;
      Microsoft::Diagnostics::Utils::Registry::GetDword(-2147483646, v51, v44, v50);
      v43 = 48;
      *(_QWORD *)v51 = L"Info";
      *(_QWORD *)&v51[2] = 4;
      *(_QWORD *)v44 = L"System\\CurrentControlSet\\Control\\CrashControl\\LastCrashdump";
      v45 = 59;
      Microsoft::Diagnostics::Utils::Registry::GetBinary(v32, (int)v44, (int)v51, (_DWORD)v9 + 96, &v43);
      *(_QWORD *)v51 = L"VirtualMachineId";
      *(_QWORD *)&v51[2] = 16;
      *(_QWORD *)v44 = L"SOFTWARE\\Microsoft\\Virtual Machine\\Guest\\Parameters";
      v45 = 51;
      if ( (int)Microsoft::Diagnostics::Utils::Registry::GetString(-2147483646, v44, v51, &v54) >= 0 )
        Microsoft::Diagnostics::Utils::String::NormalizeToBracelessUppercaseGuidString(&v54);
    }
    if ( (int)Microsoft::Diagnostics::OsEvents::SetBootStatusItem(
                v31,
                RtlBsdItemReportedAbnormalShutdownBootId,
                v10 - 1) >= 0
      && (int)Microsoft::Diagnostics::OsEvents::GetBootStatusItem(v33, RtlBsdItemReportedAbnormalShutdownBootId, &v47) >= 0
      && v10 - 1 == v47 )
    {
      if ( !(_BYTE)v29 )
      {
LABEL_67:
        OutputBuffer = 0;
        LODWORD(InputBuffer) = 50;
        if ( NtPowerInformation(SystemPowerStateLogging|0x40, &InputBuffer, 8u, &OutputBuffer, 1u) >= 0 )
        {
          v34 = OutputBuffer;
        }
        else
        {
          v34 = 0;
          OutputBuffer = 0;
        }
        if ( v34 && *((_DWORD *)v9 + 27) >= v30 && *((_DWORD *)v9 + 26) )
          OutputBuffer = 0;
        *((_BYTE *)v9 + 320) = v29;
        std::wstring::operator=((char *)v9 + 288, &v54);
        *((_DWORD *)v9 + 69) = v48;
        *((_DWORD *)v9 + 68) = v49;
        *((_DWORD *)v9 + 70) = v50[0];
        *((_BYTE *)v9 + 321) = OutputBuffer;
        while ( v30 < v10 )
        {
          Microsoft::Diagnostics::OsEvents::SendABSEvent(v30, v10, v40, v9);
          Microsoft::Diagnostics::OsEvents::SetBootStatusItem(v35, RtlBsdItemReportedAbnormalShutdownBootId, v30++);
        }
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v54);
        goto LABEL_78;
      }
    }
    else
    {
      LOBYTE(v29) = 1;
    }
    if ( v10 - v30 > 1 )
      v30 = v10 - 1;
    goto LABEL_67;
  }
  *(_QWORD *)v44 = L"OsEvents_BootStatReset_0";
  v45 = 24;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
    (unsigned int)v56,
    (unsigned int)v44,
    16779264,
    0,
    1,
    0,
    0);
  *(_QWORD *)v44 = L"ResetReason";
  v45 = 11;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>((unsigned int)v56, (unsigned int)v57);
  *(_QWORD *)v44 = L"BootId";
  v45 = 6;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>((unsigned int)v56, (unsigned int)v57);
  *(_OWORD *)v51 = 0;
  Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(&v43, v51);
  Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v56);
  OutputBuffer = 0;
  InputBuffer = 62;
  v11 = NtPowerInformation(SystemPowerStateLogging|0x40, &InputBuffer, 8u, &OutputBuffer, 1u);
  if ( !OutputBuffer && v11 >= 0 )
  {
    *((_BYTE *)v9 + 322) = 1;
    Microsoft::Diagnostics::OsEvents::SendABSEvent(0, 0, 0, v9);
  }
  v12 = RtlRestoreSystemBootStatusDefaults();
  if ( v12 < 0 )
  {
    v14 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x353,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\osevents.cpp",
            (const char *)(unsigned int)v12,
            OutputBufferLengtha);
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v56);
    std::unique_ptr<AbnormalShutdownData>::~unique_ptr<AbnormalShutdownData>(&v46);
    return v14;
  }
  v15 = v41;
  v16 = Microsoft::Diagnostics::OsEvents::SetBootStatusItem(v13, RtlBsdItemBootId, v41);
  v18 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x356,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\osevents.cpp",
      (const char *)(unsigned int)v16,
      OutputBufferLengtha);
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v56);
    std::unique_ptr<AbnormalShutdownData>::~unique_ptr<AbnormalShutdownData>(&v46);
    return v18;
  }
  v19 = Microsoft::Diagnostics::OsEvents::SetBootStatusItem(v17, RtlBsdItemShutdownBootId, v15 - 1);
  v20 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x359,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\osevents.cpp",
      (const char *)(unsigned int)v19,
      OutputBufferLengtha);
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v56);
    std::unique_ptr<AbnormalShutdownData>::~unique_ptr<AbnormalShutdownData>(&v46);
    return v20;
  }
  v54 = 0;
  *(_OWORD *)&SystemTime[0].LowPart = 0;
  SystemBootStatus = RtlGetSystemBootStatus(7, &v54, 32);
  if ( SystemBootStatus < 0 )
  {
    v22 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x35D,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\osevents.cpp",
            (const char *)(unsigned int)SystemBootStatus,
            OutputBufferLengtha);
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v56);
    std::unique_ptr<AbnormalShutdownData>::~unique_ptr<AbnormalShutdownData>(&v46);
    return v22;
  }
  SystemTime[1].HighPart = v15;
  v23 = NtQuerySystemTime(SystemTime);
  if ( v23 < 0 )
  {
    v24 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x35F,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\osevents.cpp",
            (const char *)(unsigned int)v23,
            OutputBufferLengtha);
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v56);
    std::unique_ptr<AbnormalShutdownData>::~unique_ptr<AbnormalShutdownData>(&v46);
    return v24;
  }
  SystemTime[1].LowPart = RtlComputeCrc32(0, (PUCHAR)SystemTime, 8u);
  v25 = RtlSetSystemBootStatus(7, &v54, 32, 0);
  if ( v25 < 0 )
  {
    v26 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x361,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\osevents.cpp",
            (const char *)(unsigned int)v25,
            OutputBufferLengtha);
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v56);
    std::unique_ptr<AbnormalShutdownData>::~unique_ptr<AbnormalShutdownData>(&v46);
    return v26;
  }
  Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v56);
LABEL_78:
  std::unique_ptr<AbnormalShutdownData>::~unique_ptr<AbnormalShutdownData>(&v46);
  return 0;
}

```

## disassembly

```asm
0x1802dae84  push    rbx
0x1802dae86  push    rsi
0x1802dae87  push    rdi
0x1802dae88  push    r12
0x1802dae8a  push    r13
0x1802dae8c  push    r14
0x1802dae8e  push    r15
0x1802dae90  sub     rsp, 5C0h
0x1802dae97  mov     rax, cs:__security_cookie
0x1802dae9e  xor     rax, rsp
0x1802daea1  mov     [rsp+5F8h+var_48], rax
0x1802daea9  xor     r12d, r12d
0x1802daeac  mov     [rsp+5F8h+var_5B4], r12d
0x1802daeb1  lea     esi, [r12+1]
0x1802daeb6  mov     [rsp+5F8h+var_5B7], sil
0x1802daebb  lea     rcx, [rsp+5F8h+var_5B7]
0x1802daec0  call    cs:__imp_RtlCheckSystemBootStatusIntegrity
0x1802daec7  nop     dword ptr [rax+rax+00h]
0x1802daecc  cmp     eax, 0C0000034h
0x1802daed1  jnz     short loc_1802DAF13
0x1802daed3  xor     ecx, ecx
0x1802daed5  call    cs:__imp_RtlCreateBootStatusDataFile
0x1802daedc  nop     dword ptr [rax+rax+00h]
0x1802daee1  test    eax, eax
0x1802daee3  jns     short loc_1802DAF06
0x1802daee5  mov     rcx, [rsp+5F8h]; this
0x1802daeed  mov     r9d, eax; char *
0x1802daef0  lea     r8, aOnecoreBaseTel_56; "onecore\\base\\telemetry\\utc\\service"...
0x1802daef7  mov     edx, 30Bh; void *
0x1802daefc  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1802daf01  jmp     loc_1802DB892
0x1802daf06  mov     [rsp+5F8h+var_5B4], 3E8h
0x1802daf0e  jmp     loc_1802DAF98
0x1802daf13  test    eax, eax
0x1802daf15  jns     short loc_1802DAF38
0x1802daf17  mov     rcx, [rsp+5F8h]; this
0x1802daf1f  mov     r9d, eax; char *
0x1802daf22  lea     r8, aOnecoreBaseTel_56; "onecore\\base\\telemetry\\utc\\service"...
0x1802daf29  mov     edx, 313h; void *
0x1802daf2e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1802daf33  jmp     loc_1802DB892
0x1802daf38  cmp     [rsp+5F8h+var_5B7], r12b
0x1802daf3d  jnz     short loc_1802DAF49
0x1802daf3f  mov     [rsp+5F8h+var_5B4], 7D0h
0x1802daf47  jmp     short loc_1802DAF98
0x1802daf49  mov     [rsp+5F8h+var_5B0], r12d
0x1802daf4e  lea     r8, [rsp+5F8h+var_5B0]; unsigned int *
0x1802daf53  xor     edx, edx; enum RTL_BSD_ITEM_TYPE
0x1802daf55  call    ?GetBootStatusItem@OsEvents@Diagnostics@Microsoft@@CAJPEAXW4RTL_BSD_ITEM_TYPE@@PEAK@Z; Microsoft::Diagnostics::OsEvents::GetBootStatusItem(void *,RTL_BSD_ITEM_TYPE,ulong *)
0x1802daf5a  mov     ebx, eax
0x1802daf5c  test    eax, eax
0x1802daf5e  jns     short loc_1802DAF83
0x1802daf60  mov     rcx, [rsp+5F8h]; this
0x1802daf68  mov     r9d, eax; char *
0x1802daf6b  lea     r8, aOnecoreBaseTel_56; "onecore\\base\\telemetry\\utc\\service"...
0x1802daf72  mov     edx, 31Fh; void *
0x1802daf77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802daf7c  mov     eax, ebx
0x1802daf7e  jmp     loc_1802DB892
0x1802daf83  mov     dil, r12b
0x1802daf86  cmp     [rsp+5F8h+var_5B0], 0C8h
0x1802daf8e  jnb     short loc_1802DAF9B
0x1802daf90  mov     [rsp+5F8h+var_5B4], 0BB8h
0x1802daf98  mov     dil, sil
0x1802daf9b  mov     r14d, 148h
0x1802dafa1  mov     ecx, r14d; Size
0x1802dafa4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802dafa9  mov     rbx, rax
0x1802dafac  mov     r8d, r14d; Size
0x1802dafaf  xor     edx, edx; Val
0x1802dafb1  mov     rcx, rax; void *
0x1802dafb4  call    memset_0
0x1802dafb9  mov     rcx, rbx; this
0x1802dafbc  call    ??0AbnormalShutdownData@@QEAA@XZ; AbnormalShutdownData::AbnormalShutdownData(void)
0x1802dafc1  mov     rbx, rax
0x1802dafc4  mov     [rsp+5F8h+var_588], rax
0x1802dafc9  mov     r15d, ds:7FFE02C4h
0x1802dafd1  mov     [rsp+5F8h+var_5B0], r15d
0x1802dafd6  test    dil, dil
0x1802dafd9  jz      loc_1802DB366
0x1802dafdf  lea     rax, aOseventsBootst; "OsEvents_BootStatReset_0"
0x1802dafe6  mov     qword ptr [rsp+5F8h+var_598], rax
0x1802dafeb  mov     [rsp+5F8h+var_590], 18h
0x1802daff4  mov     [rsp+5F8h+var_5C8], r12b
0x1802daff9  mov     byte ptr [rsp+5F8h+var_5D0], r12b
0x1802daffe  mov     byte ptr [rsp+5F8h+OutputBufferLength], sil
0x1802db003  mov     r9, 800000000000h
0x1802db00d  mov     r8d, 1000800h
0x1802db013  lea     rdx, [rsp+5F8h+var_598]
0x1802db018  lea     rcx, [rsp+5F8h+var_4E8]
0x1802db020  call    ??0AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@UPrivacyDataType@@_KVTriggerPersistence@12@VTriggerLatency@12@_N@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(std::wstring_view,PrivacyDataType,unsigned __int64,Microsoft::Diagnostics::TriggerPersistence,Microsoft::Diagnostics::TriggerLatency,bool)
0x1802db025  nop
0x1802db026  lea     rax, aResetreason; "ResetReason"
0x1802db02d  mov     qword ptr [rsp+5F8h+var_598], rax
0x1802db032  mov     [rsp+5F8h+var_590], 0Bh
0x1802db03b  lea     r9, [rsp+5F8h+var_5B4]
0x1802db040  lea     r8, [rsp+5F8h+var_598]
0x1802db045  lea     rdx, [rsp+5F8h+var_80]
0x1802db04d  lea     rcx, [rsp+5F8h+var_4E8]
0x1802db055  call    ??$AddField@K@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBK@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<ulong>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,ulong const &)
0x1802db05a  lea     rax, aBootid_0; "BootId"
0x1802db061  mov     qword ptr [rsp+5F8h+var_598], rax
0x1802db066  mov     [rsp+5F8h+var_590], 6
0x1802db06f  lea     r9, [rsp+5F8h+var_5B0]
0x1802db074  lea     r8, [rsp+5F8h+var_598]
0x1802db079  lea     rdx, [rsp+5F8h+var_80]
0x1802db081  lea     rcx, [rsp+5F8h+var_4E8]
0x1802db089  call    ??$AddField@K@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBK@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<ulong>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,ulong const &)
0x1802db08e  xorps   xmm0, xmm0
0x1802db091  movdqa  xmmword ptr [rsp+5F8h+var_568], xmm0
0x1802db09a  lea     rdx, [rsp+5F8h+var_568]
0x1802db0a2  lea     rcx, [rsp+5F8h+var_5A0]
0x1802db0a7  call    ??$MakeEnumSet@VPersistSyntheticOptions@Diagnostics@Microsoft@@@Enum@Utils@Diagnostics@Microsoft@@SA?AV?$bitset@$01@std@@V?$initializer_list@VPersistSyntheticOptions@Diagnostics@Microsoft@@@5@@Z; Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(std::initializer_list<Microsoft::Diagnostics::PersistSyntheticOptions>)
0x1802db0ac  mov     edx, [rax]
0x1802db0ae  lea     rcx, [rsp+5F8h+var_4E8]; this
0x1802db0b6  call    ?PersistSyntheticEvent@AsimovEventSerializer@Diagnostics@Microsoft@@SAJAEAVAsimovSyntheticEvent@23@V?$bitset@$01@std@@@Z; Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent(Microsoft::Diagnostics::AsimovSyntheticEvent &,std::bitset<2>)
0x1802db0bb  mov     [rsp+5F8h+OutputBuffer], r12b
0x1802db0c0  mov     [rsp+5F8h+InputBuffer], 3Eh ; '>'
0x1802db0c9  mov     [rsp+5F8h+OutputBufferLength], esi; int
0x1802db0cd  lea     r9, [rsp+5F8h+OutputBuffer]; OutputBuffer
0x1802db0d2  mov     r14d, 8
0x1802db0d8  mov     r8d, r14d; InputBufferLength
0x1802db0db  lea     rdx, [rsp+5F8h+InputBuffer]; InputBuffer
0x1802db0e0  lea     ecx, [r14+4Fh]; PowerInformationLevel
0x1802db0e4  call    cs:__imp_NtPowerInformation
0x1802db0eb  nop     dword ptr [rax+rax+00h]
0x1802db0f0  cmp     [rsp+5F8h+OutputBuffer], r12b
0x1802db0f5  jnz     short loc_1802DB111
0x1802db0f7  test    eax, eax
0x1802db0f9  js      short loc_1802DB111
0x1802db0fb  mov     [rbx+142h], sil
0x1802db102  mov     r9, rbx; struct AbnormalShutdownData *
0x1802db105  xor     r8d, r8d; unsigned int
0x1802db108  xor     edx, edx; unsigned int
0x1802db10a  xor     ecx, ecx; unsigned int
0x1802db10c  call    ?SendABSEvent@OsEvents@Diagnostics@Microsoft@@CAXKKKPEBUAbnormalShutdownData@@@Z; Microsoft::Diagnostics::OsEvents::SendABSEvent(ulong,ulong,ulong,AbnormalShutdownData const *)
0x1802db111  call    cs:__imp_RtlRestoreSystemBootStatusDefaults
0x1802db118  nop     dword ptr [rax+rax+00h]
0x1802db11d  test    eax, eax
0x1802db11f  jns     short loc_1802DB15E
0x1802db121  mov     rcx, [rsp+5F8h]; this
0x1802db129  mov     r9d, eax; char *
0x1802db12c  lea     r8, aOnecoreBaseTel_56; "onecore\\base\\telemetry\\utc\\service"...
0x1802db133  mov     edx, 353h; void *
0x1802db138  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1802db13d  mov     ebx, eax
0x1802db13f  lea     rcx, [rsp+5F8h+var_4E8]; this
0x1802db147  call    ??1AsimovSyntheticEvent@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent(void)
0x1802db14c  nop
0x1802db14d  lea     rcx, [rsp+5F8h+var_588]
0x1802db152  call    ??1?$unique_ptr@UAbnormalShutdownData@@U?$default_delete@UAbnormalShutdownData@@@std@@@std@@QEAA@XZ; std::unique_ptr<AbnormalShutdownData>::~unique_ptr<AbnormalShutdownData>(void)
0x1802db157  mov     eax, ebx
0x1802db159  jmp     loc_1802DB892
0x1802db15e  mov     edi, [rsp+5F8h+var_5B0]
0x1802db162  mov     r8d, edi; unsigned int
0x1802db165  mov     edx, 0Ah; enum RTL_BSD_ITEM_TYPE
0x1802db16a  call    ?SetBootStatusItem@OsEvents@Diagnostics@Microsoft@@CAJPEAXW4RTL_BSD_ITEM_TYPE@@K@Z; Microsoft::Diagnostics::OsEvents::SetBootStatusItem(void *,RTL_BSD_ITEM_TYPE,ulong)
0x1802db16f  mov     ebx, eax
0x1802db171  test    eax, eax
0x1802db173  jns     short loc_1802DB1B1
0x1802db175  mov     rcx, [rsp+5F8h]; this
0x1802db17d  mov     r9d, eax; char *
0x1802db180  lea     r8, aOnecoreBaseTel_56; "onecore\\base\\telemetry\\utc\\service"...
0x1802db187  mov     edx, 356h; void *
0x1802db18c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802db191  nop
0x1802db192  lea     rcx, [rsp+5F8h+var_4E8]; this
0x1802db19a  call    ??1AsimovSyntheticEvent@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent(void)
0x1802db19f  nop
0x1802db1a0  lea     rcx, [rsp+5F8h+var_588]
0x1802db1a5  call    ??1?$unique_ptr@UAbnormalShutdownData@@U?$default_delete@UAbnormalShutdownData@@@std@@@std@@QEAA@XZ; std::unique_ptr<AbnormalShutdownData>::~unique_ptr<AbnormalShutdownData>(void)
0x1802db1aa  mov     eax, ebx
0x1802db1ac  jmp     loc_1802DB892
0x1802db1b1  lea     r8d, [rdi-1]; unsigned int
0x1802db1b5  mov     edx, 0Bh; enum RTL_BSD_ITEM_TYPE
0x1802db1ba  call    ?SetBootStatusItem@OsEvents@Diagnostics@Microsoft@@CAJPEAXW4RTL_BSD_ITEM_TYPE@@K@Z; Microsoft::Diagnostics::OsEvents::SetBootStatusItem(void *,RTL_BSD_ITEM_TYPE,ulong)
0x1802db1bf  mov     ebx, eax
0x1802db1c1  test    eax, eax
0x1802db1c3  jns     short loc_1802DB201
0x1802db1c5  mov     rcx, [rsp+5F8h]; this
0x1802db1cd  mov     r9d, eax; char *
0x1802db1d0  lea     r8, aOnecoreBaseTel_56; "onecore\\base\\telemetry\\utc\\service"...
0x1802db1d7  mov     edx, 359h; void *
0x1802db1dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802db1e1  nop
0x1802db1e2  lea     rcx, [rsp+5F8h+var_4E8]; this
0x1802db1ea  call    ??1AsimovSyntheticEvent@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent(void)
0x1802db1ef  nop
0x1802db1f0  lea     rcx, [rsp+5F8h+var_588]
0x1802db1f5  call    ??1?$unique_ptr@UAbnormalShutdownData@@U?$default_delete@UAbnormalShutdownData@@@std@@@std@@QEAA@XZ; std::unique_ptr<AbnormalShutdownData>::~unique_ptr<AbnormalShutdownData>(void)
0x1802db1fa  mov     eax, ebx
0x1802db1fc  jmp     loc_1802DB892
0x1802db201  xorps   xmm0, xmm0
0x1802db204  movups  [rsp+5F8h+var_508], xmm0
0x1802db20c  movups  xmmword ptr [rsp+5F8h+SystemTime], xmm0
0x1802db214  xor     r9d, r9d
0x1802db217  lea     ebx, [r9+20h]
0x1802db21b  mov     r8d, ebx
0x1802db21e  lea     rdx, [rsp+5F8h+var_508]
0x1802db226  lea     r12d, [r9+7]
0x1802db22a  mov     ecx, r12d
0x1802db22d  call    cs:__imp_RtlGetSystemBootStatus
0x1802db234  nop     dword ptr [rax+rax+00h]
0x1802db239  test    eax, eax
0x1802db23b  jns     short loc_1802DB27A
0x1802db23d  mov     rcx, [rsp+5F8h]; this
0x1802db245  mov     r9d, eax; char *
0x1802db248  lea     r8, aOnecoreBaseTel_56; "onecore\\base\\telemetry\\utc\\service"...
0x1802db24f  mov     edx, 35Dh; void *
0x1802db254  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1802db259  mov     ebx, eax
0x1802db25b  lea     rcx, [rsp+5F8h+var_4E8]; this
0x1802db263  call    ??1AsimovSyntheticEvent@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent(void)
0x1802db268  nop
0x1802db269  lea     rcx, [rsp+5F8h+var_588]
0x1802db26e  call    ??1?$unique_ptr@UAbnormalShutdownData@@U?$default_delete@UAbnormalShutdownData@@@std@@@std@@QEAA@XZ; std::unique_ptr<AbnormalShutdownData>::~unique_ptr<AbnormalShutdownData>(void)
0x1802db273  mov     eax, ebx
0x1802db275  jmp     loc_1802DB892
0x1802db27a  mov     dword ptr [rsp+5F8h+SystemTime+0Ch], edi
0x1802db281  lea     rcx, [rsp+5F8h+SystemTime]; SystemTime
0x1802db289  call    cs:__imp_NtQuerySystemTime
0x1802db290  nop     dword ptr [rax+rax+00h]
0x1802db295  test    eax, eax
0x1802db297  jns     short loc_1802DB2D6
0x1802db299  mov     rcx, [rsp+5F8h]; this
0x1802db2a1  mov     r9d, eax; char *
0x1802db2a4  lea     r8, aOnecoreBaseTel_56; "onecore\\base\\telemetry\\utc\\service"...
0x1802db2ab  mov     edx, 35Fh; void *
0x1802db2b0  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1802db2b5  mov     ebx, eax
0x1802db2b7  lea     rcx, [rsp+5F8h+var_4E8]; this
0x1802db2bf  call    ??1AsimovSyntheticEvent@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent(void)
0x1802db2c4  nop
0x1802db2c5  lea     rcx, [rsp+5F8h+var_588]
0x1802db2ca  call    ??1?$unique_ptr@UAbnormalShutdownData@@U?$default_delete@UAbnormalShutdownData@@@std@@@std@@QEAA@XZ; std::unique_ptr<AbnormalShutdownData>::~unique_ptr<AbnormalShutdownData>(void)
0x1802db2cf  mov     eax, ebx
0x1802db2d1  jmp     loc_1802DB892
0x1802db2d6  mov     r8d, r14d; Length
0x1802db2d9  lea     rdx, [rsp+5F8h+SystemTime]; Buffer
0x1802db2e1  xor     ecx, ecx; InitialCrc
0x1802db2e3  call    cs:__imp_RtlComputeCrc32
0x1802db2ea  nop     dword ptr [rax+rax+00h]
0x1802db2ef  mov     dword ptr [rsp+5F8h+SystemTime+8], eax
0x1802db2f6  xor     r9d, r9d
0x1802db2f9  mov     r8d, ebx
0x1802db2fc  lea     rdx, [rsp+5F8h+var_508]
0x1802db304  mov     ecx, r12d
0x1802db307  call    cs:__imp_RtlSetSystemBootStatus
0x1802db30e  nop     dword ptr [rax+rax+00h]
0x1802db313  test    eax, eax
0x1802db315  jns     short loc_1802DB354
0x1802db317  mov     rcx, [rsp+5F8h]; this
0x1802db31f  mov     r9d, eax; char *
0x1802db322  lea     r8, aOnecoreBaseTel_56; "onecore\\base\\telemetry\\utc\\service"...
0x1802db329  mov     edx, 361h; void *
0x1802db32e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1802db333  mov     ebx, eax
0x1802db335  lea     rcx, [rsp+5F8h+var_4E8]; this
0x1802db33d  call    ??1AsimovSyntheticEvent@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent(void)
0x1802db342  nop
0x1802db343  lea     rcx, [rsp+5F8h+var_588]
0x1802db348  call    ??1?$unique_ptr@UAbnormalShutdownData@@U?$default_delete@UAbnormalShutdownData@@@std@@@std@@QEAA@XZ; std::unique_ptr<AbnormalShutdownData>::~unique_ptr<AbnormalShutdownData>(void)
0x1802db34d  mov     eax, ebx
0x1802db34f  jmp     loc_1802DB892
0x1802db354  lea     rcx, [rsp+5F8h+var_4E8]; this
0x1802db35c  call    ??1AsimovSyntheticEvent@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent(void)
0x1802db361  jmp     loc_1802DB880
0x1802db366  mov     [rsp+5F8h+var_5B4], r12d
0x1802db36b  lea     r8, [rsp+5F8h+var_5B4]; unsigned int *
0x1802db370  mov     edx, 0Bh; enum RTL_BSD_ITEM_TYPE
0x1802db375  call    ?GetBootStatusItem@OsEvents@Diagnostics@Microsoft@@CAJPEAXW4RTL_BSD_ITEM_TYPE@@PEAK@Z; Microsoft::Diagnostics::OsEvents::GetBootStatusItem(void *,RTL_BSD_ITEM_TYPE,ulong *)
0x1802db37a  mov     esi, eax
0x1802db37c  mov     [rsp+5F8h+var_5B0], r12d
0x1802db381  lea     r8, [rsp+5F8h+var_5B0]; unsigned int *
0x1802db386  mov     edx, 0Ch; enum RTL_BSD_ITEM_TYPE
0x1802db38b  call    ?GetBootStatusItem@OsEvents@Diagnostics@Microsoft@@CAJPEAXW4RTL_BSD_ITEM_TYPE@@PEAK@Z; Microsoft::Diagnostics::OsEvents::GetBootStatusItem(void *,RTL_BSD_ITEM_TYPE,ulong *)
0x1802db390  test    eax, eax
0x1802db392  jns     short loc_1802DB399
0x1802db394  mov     sil, 1
0x1802db397  jmp     short loc_1802DB39C
0x1802db399  shr     esi, 1Fh
0x1802db39c  xor     r8d, r8d
0x1802db39f  lea     rdx, [rsp+5F8h+var_558]
0x1802db3a7  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; Microsoft::Diagnostics::LifetimeManager gs_lifetimeManager
0x1802db3ae  call    ?GetAuthorizationInfo@LifetimeManager@Diagnostics@Microsoft@@QEAA?AVAuthorizationInfo@23@_N@Z; Microsoft::Diagnostics::LifetimeManager::GetAuthorizationInfo(bool)
0x1802db3b3  mov     edi, [rsp+5F8h+var_5B0]
0x1802db3b7  inc     edi
0x1802db3b9  mov     eax, [rsp+5F8h+var_5B4]
0x1802db3bd  inc     eax
0x1802db3bf  cmp     eax, edi
0x1802db3c1  cmovnb  edi, eax
0x1802db3c4  cmp     r15d, 10h
0x1802db3c8  jbe     short loc_1802DB3D3
0x1802db3ca  lea     eax, [r15-10h]
0x1802db3ce  cmp     edi, eax
0x1802db3d0  cmovb   edi, eax
0x1802db3d3  mov     [rsp+5F8h+var_578], r12d
0x1802db3db  mov     [rsp+5F8h+var_57C], r12d
0x1802db3e0  mov     [rsp+5F8h+var_574], r12d
0x1802db3e8  lea     rcx, [rsp+5F8h+var_508]; void *
  ... truncated ...
```
