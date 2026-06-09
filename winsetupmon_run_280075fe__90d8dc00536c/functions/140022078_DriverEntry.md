# DriverEntry

- ea: `0x140022078`
- end: `0x1400226a7`
- name: `DriverEntry`
- size: `1583`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140022010`

## callees

- `0x140001404`
- `0x1400022f0`
- `0x140007800`
- `0x140007a58`
- `0x140007e14`
- `0x140007fec`
- `0x140008138`
- `0x140008740`
- `0x14000f900`
- `0x14000f9e0`
- `0x14001f130`
- `0x1400201b0`
- `0x140022078`

## import_xrefs

- `ntoskrnl!ExInitializeRundownProtection` at `0x140022157`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140022157`
- `ntoskrnl!EtwRegister` at `0x1400221a7`
- `ntoskrnl!EtwRegister` at `0x1400221a7`
- `ntoskrnl!PsSetCreateProcessNotifyRoutine` at `0x1400223ab`
- `ntoskrnl!PsSetCreateProcessNotifyRoutine` at `0x1400225f9`
- `ntoskrnl!PsSetCreateProcessNotifyRoutine` at `0x1400223ab`
- `ntoskrnl!PsSetCreateProcessNotifyRoutine` at `0x1400225f9`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400224e0`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400224e0`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140022582`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140022582`
- `ntoskrnl!IoDeleteDevice` at `0x1400225b5`
- `ntoskrnl!IoDeleteDevice` at `0x1400225b5`
- `ntoskrnl!EtwUnregister` at `0x140022675`
- `ntoskrnl!EtwUnregister` at `0x140022675`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002229f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002229f`
- `ntoskrnl!KeInitializeMutex` at `0x140022144`
- `ntoskrnl!KeInitializeMutex` at `0x140022144`
- `ntoskrnl!RtlInitUnicodeString` at `0x140022231`
- `ntoskrnl!RtlInitUnicodeString` at `0x140022231`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400220ee`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14002224e`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400220ee`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14002224e`
- `ntoskrnl!EtwSetInformation` at `0x1400221cc`
- `ntoskrnl!EtwSetInformation` at `0x1400221cc`
- `ntoskrnl!RtlFreeAnsiString` at `0x140022305`
- `ntoskrnl!RtlFreeAnsiString` at `0x140022305`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14002228b`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14002228b`
- `ntoskrnl!RtlInitAnsiString` at `0x1400222e1`
- `ntoskrnl!RtlInitAnsiString` at `0x1400222e1`
- `FLTMGR!FltUnregisterFilter` at `0x14002262c`
- `FLTMGR!FltUnregisterFilter` at `0x14002262c`
- `FLTMGR!FltCloseCommunicationPort` at `0x1400225d4`
- `FLTMGR!FltCloseCommunicationPort` at `0x1400225d4`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x140022561`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x140022561`
- `FLTMGR!FltStartFiltering` at `0x140022537`
- `FLTMGR!FltStartFiltering` at `0x140022537`
- `FLTMGR!FltCreateCommunicationPort` at `0x140022472`
- `FLTMGR!FltCreateCommunicationPort` at `0x140022472`
- `FLTMGR!FltBuildDefaultSecurityDescriptor` at `0x1400223dc`
- `FLTMGR!FltBuildDefaultSecurityDescriptor` at `0x1400223dc`
- `FLTMGR!FltRegisterFilter` at `0x140022384`
- `FLTMGR!FltRegisterFilter` at `0x140022384`

## string_xrefs

- `0x140022349`: `WinSetupMon::DriverEntry: Failed to create initialize state`
- `0x140022367`: `WinSetupMon::DriverEntry: LoadConfig failed`
- `0x1400223bd`: `WinSetupMon::DriverEntry: Failed PsSetCreateProcessNotifyRoutine (1)`
- `0x1400223ee`: `WinSetupMon::DriverEntry: Failed FltBuildDefaultSecurityDescriptor`
- `0x140022484`: `WinSetupMon::DriverEntry: Failed FltCreateCommunicationPort`
- `0x1400224b8`: `WinSetupMon::DriverEntry: Failed IoCreateDeviceSecure`
- `0x1400224f2`: `WinSetupMon::DriverEntry: Failed IoCreateSymbolicLink`
- `0x140022594`: `WinSetupMon::DriverEntry: Failed IoDeleteSymbolicLink`
- `0x14002260b`: `WinSetupMon::DriverEntry: Failed PsSetCreateProcessNotifyRoutine (2)`
- `0x1400221df`: `IoQueryFullDriverPath`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  PVOID SystemRoutineAddress; // rax
  NTSTATUS v5; // eax
  int v6; // eax
  __int64 (__fastcall *v7)(_DRIVER_OBJECT *, struct _UNICODE_STRING *); // rax
  NTSTATUS v8; // ebx
  __int64 v9; // rcx
  bool v10; // zf
  NTSTATUS started; // eax
  NTSTATUS Config; // ebx
  const char *v13; // rcx
  __int64 v14; // rdx
  NTSTATUS ProcessNotifyRoutine; // eax
  ULONG v16; // edx
  ULONG v17; // r9d
  NTSTATUS v18; // eax
  NTSTATUS v19; // eax
  REGHANDLE v20; // rcx
  ULONG ConnectNotifyCallback; // [rsp+20h] [rbp-E0h]
  BOOLEAN DisconnectNotifyCallback; // [rsp+28h] [rbp-D8h]
  const UNICODE_STRING *MessageNotifyCallback; // [rsp+30h] [rbp-D0h]
  const GUID *MaxConnections; // [rsp+38h] [rbp-C8h]
  PDEVICE_OBJECT *v26; // [rsp+40h] [rbp-C0h]
  _BYTE v27[8]; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING SystemRoutineName; // [rsp+58h] [rbp-A8h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DeviceName; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+80h] [rbp-80h] BYREF
  __int128 v32; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-60h] BYREF
  struct _STRING AnsiString; // [rsp+B0h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C0h] [rbp-40h] BYREF
  GUID v36; // [rsp+F0h] [rbp-10h] BYREF
  GUID ProviderId; // [rsp+100h] [rbp+0h] BYREF

  *(_QWORD *)&SystemRoutineName.Length = 3276848;
  SecurityDescriptor = 0;
  v27[0] = 0;
  SystemRoutineName.Buffer = L"ZwQuerySystemInformation";
  v32 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DeviceName = 0;
  SymbolicLinkName = 0;
  SystemRoutineAddress = MmGetSystemRoutineAddress(&SystemRoutineName);
  if ( SystemRoutineAddress
    && ((int (__fastcall *)(__int64, _BYTE *, __int64, _QWORD))SystemRoutineAddress)(227, v27, 1, 0) >= 0
    && v27[0] )
  {
    ExPoolZeroingNativelySupported = 1;
  }
  ExDefaultNonPagedPoolType = 512;
  ExDefaultMdlProtection = 0x40000000;
  KeInitializeMutex(&stru_1400197F8, 0);
  ExInitializeRundownProtection(&FilterRundownRef);
  ProviderId = (GUID)*((_OWORD *)EventInformation - 1);
  if ( qword_140019020 )
    __fastfail(5u);
  xmmword_140019028 = 0;
  v5 = EtwRegister(&ProviderId, tlgEnableCallback, &dword_140019000, &qword_140019020);
  if ( !v5 )
  {
    EtwSetInformation(qword_140019020, EventProviderSetTraits, EventInformation, *(unsigned __int16 *)EventInformation);
LABEL_9:
    byte_1400194D1 = 1;
    goto LABEL_10;
  }
  if ( v5 >= 0 )
    goto LABEL_9;
  TraceError("WinSetupMon::DriverEntry: Failed to register telemetry provider", (unsigned int)v5);
LABEL_10:
  *(_QWORD *)&SystemRoutineName.Length = 2883626;
  SystemRoutineName.Buffer = L"IoQueryFullDriverPath";
  AnsiString = 0;
  DestinationString = 0;
  if ( _InterlockedExchangeAdd(&g_AssertsOperational, 0) )
  {
    v6 = 0;
  }
  else
  {
    RtlInitUnicodeString(&DestinationString, 0);
    v7 = (__int64 (__fastcall *)(_DRIVER_OBJECT *, struct _UNICODE_STRING *))qword_14001D010;
    if ( !qword_14001D010 )
    {
      v7 = (__int64 (__fastcall *)(_DRIVER_OBJECT *, struct _UNICODE_STRING *))MmGetSystemRoutineAddress(&SystemRoutineName);
      qword_14001D010 = (__int64)v7;
      if ( !v7 )
        goto LABEL_27;
    }
    v6 = v7(DriverObject, &DestinationString);
    v8 = v6;
    if ( v6 >= 0 )
    {
      v8 = RtlUnicodeStringToAnsiString(&AnsiString, &DestinationString, 1u);
      ExFreePoolWithTag(DestinationString.Buffer, 0);
      if ( v8 >= 0 )
      {
        v9 = (unsigned int)AnsiString.Length - 1;
        if ( AnsiString.Length != 1 )
        {
          while ( AnsiString.Buffer[v9] != 92 )
          {
            v10 = (_DWORD)v9 == 1;
            v9 = (unsigned int)(v9 - 1);
            if ( v10 )
              goto LABEL_24;
          }
          if ( (_DWORD)v9 != AnsiString.Length )
          {
            ProviderId = 0;
            RtlInitAnsiString((PANSI_STRING)&ProviderId, &AnsiString.Buffer[(unsigned int)(v9 + 1)]);
            v36 = ProviderId;
            v8 = InitializeTelemetryAssertsKMWorkerInternal(&v36);
          }
        }
LABEL_24:
        RtlFreeAnsiString(&AnsiString);
      }
      v6 = v8;
    }
    if ( v8 == -1073741702 )
LABEL_27:
      v6 = InitializeTelemetryAssertsKM(RegistryPath);
  }
  if ( v6 >= 0 )
    byte_1400194D0 = 1;
  else
    TraceError("WinSetupMon::DriverEntry: Failed to initialize telemetry asserts", (unsigned int)v6);
  started = InitializeState();
  Config = started;
  if ( started < 0 )
  {
    v13 = "WinSetupMon::DriverEntry: Failed to create initialize state";
LABEL_50:
    v14 = (unsigned int)started;
    goto LABEL_51;
  }
  Config = LoadConfig();
  if ( Config >= 0 )
  {
    started = FltRegisterFilter(DriverObject, &Registration, (PFLT_FILTER *)&FilterHandle);
    Config = started;
    if ( started >= 0 )
    {
      ProcessNotifyRoutine = PsSetCreateProcessNotifyRoutine(WinSetupMonCreateProcessNotificationCallback, 0);
      if ( ProcessNotifyRoutine >= 0 )
        byte_1400194C0 = 1;
      else
        TraceError(
          "WinSetupMon::DriverEntry: Failed PsSetCreateProcessNotifyRoutine (1)",
          (unsigned int)ProcessNotifyRoutine);
      started = FltBuildDefaultSecurityDescriptor(&SecurityDescriptor, 0x1F0001u);
      Config = started;
      if ( started >= 0 )
      {
        *((_QWORD *)&v32 + 1) = L"\\WinSetupMonPort";
        ObjectAttributes.ObjectName = (PUNICODE_STRING)&v32;
        ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
        *(_QWORD *)&v32 = 2228256;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 576;
        ObjectAttributes.SecurityQualityOfService = 0;
        started = FltCreateCommunicationPort(
                    (PFLT_FILTER)FilterHandle,
                    &FilterPort,
                    &ObjectAttributes,
                    0,
                    WinSetupMonPortConnect,
                    WinSetupMonPortDisconnect,
                    WinSetupMonMessage,
                    1);
        Config = started;
        if ( started >= 0 )
        {
          *(_QWORD *)&DeviceName.Length = 2621478;
          DeviceName.Buffer = L"\\Device\\WinSetupMon";
          started = WdmlibIoCreateDeviceSecure(
                      DriverObject,
                      v16,
                      &DeviceName,
                      v17,
                      ConnectNotifyCallback,
                      DisconnectNotifyCallback,
                      MessageNotifyCallback,
                      MaxConnections,
                      v26);
          Config = started;
          if ( started >= 0 )
          {
            *(_QWORD *)&SymbolicLinkName.Length = 3145774;
            SymbolicLinkName.Buffer = L"\\DosDevices\\WinSetupMon";
            started = IoCreateSymbolicLink(&SymbolicLinkName, &DeviceName);
            Config = started;
            if ( started >= 0 )
            {
              byte_1400194C1 = 1;
              DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&WinSetupMonCreateClose;
              DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)&WinSetupMonCreateClose;
              DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)&WinSetupMonDeviceControl;
              DriverObject->MajorFunction[15] = (PDRIVER_DISPATCH)&WinSetupMonDeviceControl;
              ::DriverObject = DriverObject;
              started = FltStartFiltering((PFLT_FILTER)FilterHandle);
              Config = started;
              if ( started >= 0 )
                goto LABEL_52;
              v13 = "WinSetupMon::DriverEntry: Failed FltStartFiltering";
            }
            else
            {
              v13 = "WinSetupMon::DriverEntry: Failed IoCreateSymbolicLink";
            }
          }
          else
          {
            v13 = "WinSetupMon::DriverEntry: Failed IoCreateDeviceSecure";
          }
        }
        else
        {
          v13 = "WinSetupMon::DriverEntry: Failed FltCreateCommunicationPort";
        }
      }
      else
      {
        v13 = "WinSetupMon::DriverEntry: Failed FltBuildDefaultSecurityDescriptor";
      }
    }
    else
    {
      v13 = "WinSetupMon::DriverEntry: Failed FltRegisterFilter";
    }
    goto LABEL_50;
  }
  MicrosoftTelemetryAssertTriggeredNoArgsKM();
  v14 = (unsigned int)Config;
  v13 = "WinSetupMon::DriverEntry: LoadConfig failed";
LABEL_51:
  TraceError(v13, v14);
LABEL_52:
  if ( SecurityDescriptor )
    FltFreeSecurityDescriptor(SecurityDescriptor);
  if ( Config < 0 )
  {
    if ( byte_1400194C1 )
    {
      v18 = IoDeleteSymbolicLink(&SymbolicLinkName);
      if ( v18 >= 0 )
        byte_1400194C1 = 0;
      else
        TraceError("WinSetupMon::DriverEntry: Failed IoDeleteSymbolicLink", (unsigned int)v18);
    }
    if ( DeviceObject )
    {
      IoDeleteDevice(DeviceObject);
      DeviceObject = 0;
    }
    if ( FilterPort )
    {
      FltCloseCommunicationPort(FilterPort);
      FilterPort = 0;
    }
    if ( byte_1400194C0 )
    {
      v19 = PsSetCreateProcessNotifyRoutine(WinSetupMonCreateProcessNotificationCallback, 1u);
      if ( v19 >= 0 )
        byte_1400194C0 = 0;
      else
        TraceError("WinSetupMon::DriverEntry: Failed PsSetCreateProcessNotifyRoutine (2)", (unsigned int)v19);
    }
    if ( FilterHandle )
    {
      FltUnregisterFilter((PFLT_FILTER)FilterHandle);
      FilterHandle = 0;
    }
    UnloadConfig();
    ClearState();
    if ( byte_1400194D0 )
      UninitializeTelemetryAssertsKM();
    if ( byte_1400194D1 )
    {
      v20 = qword_140019020;
      dword_140019000 = 0;
      qword_140019020 = 0;
      EtwUnregister(v20);
    }
  }
  return Config;
}

```

## disassembly

```asm
0x140022078  mov     [rsp-8+arg_10], rbx
0x14002207d  push    rbp
0x14002207e  push    rsi
0x14002207f  push    rdi
0x140022080  push    r12
0x140022082  push    r14
0x140022084  lea     rbp, [rsp-20h]
0x140022089  sub     rsp, 120h
0x140022090  mov     rax, cs:__security_cookie
0x140022097  xor     rax, rsp
0x14002209a  mov     [rbp+40h+var_30], rax
0x14002209e  xorps   xmm1, xmm1
0x1400220a1  mov     qword ptr [rsp+140h+SystemRoutineName.Length], 320030h
0x1400220aa  xor     r14d, r14d
0x1400220ad  lea     rax, aZwquerysystemi; "ZwQuerySystemInformation"
0x1400220b4  xorps   xmm0, xmm0
0x1400220b7  mov     [rsp+140h+SecurityDescriptor], r14
0x1400220bc  mov     rdi, rcx
0x1400220bf  mov     [rsp+140h+var_F0], r14b
0x1400220c4  lea     rcx, [rsp+140h+SystemRoutineName]; SystemRoutineName
0x1400220c9  mov     [rsp+140h+SystemRoutineName.Buffer], rax
0x1400220ce  lea     r12d, [r14+30h]
0x1400220d2  mov     rsi, rdx
0x1400220d5  movups  [rbp+40h+var_B0], xmm0
0x1400220d9  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm1
0x1400220dd  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm1
0x1400220e1  movups  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400220e5  movups  xmmword ptr [rsp+140h+DeviceName.Length], xmm0
0x1400220ea  movups  xmmword ptr [rbp+40h+SymbolicLinkName.Length], xmm1
0x1400220ee  call    cs:__imp_MmGetSystemRoutineAddress
0x1400220f5  nop     dword ptr [rax+rax+00h]
0x1400220fa  test    rax, rax
0x1400220fd  jz      short loc_140022127
0x1400220ff  xor     r9d, r9d
0x140022102  lea     r8d, [r14+1]
0x140022106  lea     rdx, [rsp+140h+var_F0]
0x14002210b  mov     ecx, 0E3h
0x140022110  call    _guard_dispatch_icall
0x140022115  test    eax, eax
0x140022117  js      short loc_140022127
0x140022119  cmp     [rsp+140h+var_F0], r14b
0x14002211e  jz      short loc_140022127
0x140022120  mov     cs:ExPoolZeroingNativelySupported, 1
0x140022127  xor     edx, edx; Level
0x140022129  mov     cs:ExDefaultNonPagedPoolType, 200h
0x140022133  lea     rcx, stru_1400197F8; Mutex
0x14002213a  mov     cs:ExDefaultMdlProtection, 40000000h
0x140022144  call    cs:__imp_KeInitializeMutex
0x14002214b  nop     dword ptr [rax+rax+00h]
0x140022150  lea     rcx, ?FilterRundownRef@@3U_EX_RUNDOWN_REF@@A; RunRef
0x140022157  call    cs:__imp_ExInitializeRundownProtection
0x14002215e  nop     dword ptr [rax+rax+00h]
0x140022163  cmp     cs:qword_140019020, r14
0x14002216a  mov     rax, cs:EventInformation
0x140022171  movups  xmm0, xmmword ptr [rax-10h]
0x140022175  movdqu  xmmword ptr [rbp+40h+ProviderId.Data1], xmm0
0x14002217a  jz      short loc_140022183
0x14002217c  mov     ecx, 5
0x140022181  int     29h; Win8: RtlFailFast(ecx)
0x140022183  xorps   xmm0, xmm0
0x140022186  lea     r9, qword_140019020; RegHandle
0x14002218d  lea     r8, dword_140019000; CallbackContext
0x140022194  lea     rdx, _tlgEnableCallback; EnableCallback
0x14002219b  lea     rcx, [rbp+40h+ProviderId]; ProviderId
0x14002219f  movdqu  cs:xmmword_140019028, xmm0
0x1400221a7  call    cs:__imp_EtwRegister
0x1400221ae  nop     dword ptr [rax+rax+00h]
0x1400221b3  test    eax, eax
0x1400221b5  jnz     short loc_140022219
0x1400221b7  mov     r8, cs:EventInformation; EventInformation
0x1400221be  lea     edx, [rax+2]; InformationClass
0x1400221c1  mov     rcx, cs:qword_140019020; RegHandle
0x1400221c8  movzx   r9d, word ptr [r8]; InformationLength
0x1400221cc  call    cs:__imp_EtwSetInformation
0x1400221d3  nop     dword ptr [rax+rax+00h]
0x1400221d8  mov     cs:byte_1400194D1, 1
0x1400221df  lea     rax, aIoqueryfulldri; "IoQueryFullDriverPath"
0x1400221e6  mov     qword ptr [rsp+140h+SystemRoutineName.Length], 2C002Ah
0x1400221ef  xorps   xmm0, xmm0
0x1400221f2  mov     [rsp+140h+SystemRoutineName.Buffer], rax
0x1400221f7  xorps   xmm1, xmm1
0x1400221fa  mov     eax, r14d
0x1400221fd  movups  xmmword ptr [rbp+40h+AnsiString.Length], xmm0
0x140022201  movups  xmmword ptr [rbp+40h+DestinationString.Length], xmm1
0x140022205  lock xadd cs:g_AssertsOperational, eax
0x14002220d  test    eax, eax
0x14002220f  jz      short loc_14002222B
0x140022211  mov     eax, r14d
0x140022214  jmp     loc_140022323
0x140022219  jns     short loc_1400221D8
0x14002221b  mov     edx, eax
0x14002221d  lea     rcx, aWinsetupmonDri_6; "WinSetupMon::DriverEntry: Failed to reg"...
0x140022224  call    TraceError
0x140022229  jmp     short loc_1400221DF
0x14002222b  xor     edx, edx; SourceString
0x14002222d  lea     rcx, [rbp+40h+DestinationString]; DestinationString
0x140022231  call    cs:__imp_RtlInitUnicodeString
0x140022238  nop     dword ptr [rax+rax+00h]
0x14002223d  mov     rax, cs:qword_14001D010
0x140022244  test    rax, rax
0x140022247  jnz     short loc_14002226A
0x140022249  lea     rcx, [rsp+140h+SystemRoutineName]; SystemRoutineName
0x14002224e  call    cs:__imp_MmGetSystemRoutineAddress
0x140022255  nop     dword ptr [rax+rax+00h]
0x14002225a  mov     cs:qword_14001D010, rax
0x140022261  test    rax, rax
0x140022264  jz      loc_14002231B
0x14002226a  lea     rdx, [rbp+40h+DestinationString]
0x14002226e  mov     rcx, rdi
0x140022271  call    _guard_dispatch_icall
0x140022276  mov     ebx, eax
0x140022278  test    eax, eax
0x14002227a  js      loc_140022313
0x140022280  mov     r8b, 1; AllocateDestinationString
0x140022283  lea     rdx, [rbp+40h+DestinationString]; SourceString
0x140022287  lea     rcx, [rbp+40h+AnsiString]; DestinationString
0x14002228b  call    cs:__imp_RtlUnicodeStringToAnsiString
0x140022292  nop     dword ptr [rax+rax+00h]
0x140022297  mov     rcx, [rbp+40h+DestinationString.Buffer]; P
0x14002229b  xor     edx, edx; Tag
0x14002229d  mov     ebx, eax
0x14002229f  call    cs:__imp_ExFreePoolWithTag
0x1400222a6  nop     dword ptr [rax+rax+00h]
0x1400222ab  test    ebx, ebx
0x1400222ad  js      short loc_140022311
0x1400222af  movzx   edx, [rbp+40h+AnsiString.Length]
0x1400222b3  lea     ecx, [rdx-1]
0x1400222b6  test    ecx, ecx
0x1400222b8  jz      short loc_140022301
0x1400222ba  mov     r8, [rbp+40h+AnsiString.Buffer]
0x1400222be  cmp     byte ptr [rcx+r8], 5Ch ; '\'
0x1400222c3  jz      short loc_1400222CC
0x1400222c5  add     ecx, 0FFFFFFFFh
0x1400222c8  jnz     short loc_1400222BE
0x1400222ca  jmp     short loc_140022301
0x1400222cc  cmp     ecx, edx
0x1400222ce  jz      short loc_140022301
0x1400222d0  lea     edx, [rcx+1]
0x1400222d3  xorps   xmm0, xmm0
0x1400222d6  add     rdx, r8; SourceString
0x1400222d9  lea     rcx, [rbp+40h+ProviderId]; DestinationString
0x1400222dd  movups  xmmword ptr [rbp+40h+ProviderId.Data1], xmm0
0x1400222e1  call    cs:__imp_RtlInitAnsiString
0x1400222e8  nop     dword ptr [rax+rax+00h]
0x1400222ed  movaps  xmm0, xmmword ptr [rbp+40h+ProviderId.Data1]
0x1400222f1  lea     rcx, [rbp+40h+var_50]
0x1400222f5  movdqa  [rbp+40h+var_50], xmm0
0x1400222fa  call    InitializeTelemetryAssertsKMWorkerInternal
0x1400222ff  mov     ebx, eax
0x140022301  lea     rcx, [rbp+40h+AnsiString]; AnsiString
0x140022305  call    cs:__imp_RtlFreeAnsiString
0x14002230c  nop     dword ptr [rax+rax+00h]
0x140022311  mov     eax, ebx
0x140022313  cmp     ebx, 0C000007Ah
0x140022319  jnz     short loc_140022323
0x14002231b  mov     rcx, rsi
0x14002231e  call    InitializeTelemetryAssertsKM
0x140022323  test    eax, eax
0x140022325  jns     short loc_140022337
0x140022327  mov     edx, eax
0x140022329  lea     rcx, aWinsetupmonDri_9; "WinSetupMon::DriverEntry: Failed to ini"...
0x140022330  call    TraceError
0x140022335  jmp     short loc_14002233E
0x140022337  mov     cs:byte_1400194D0, 1
0x14002233e  call    ?InitializeState@@YAJXZ; InitializeState(void)
0x140022343  mov     ebx, eax
0x140022345  test    eax, eax
0x140022347  jns     short loc_140022355
0x140022349  lea     rcx, aWinsetupmonDri_10; "WinSetupMon::DriverEntry: Failed to cre"...
0x140022350  jmp     loc_140022550
0x140022355  call    ?LoadConfig@@YAJXZ; LoadConfig(void)
0x14002235a  mov     ebx, eax
0x14002235c  test    eax, eax
0x14002235e  jns     short loc_140022373
0x140022360  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140022365  mov     edx, ebx
0x140022367  lea     rcx, aWinsetupmonDri_5; "WinSetupMon::DriverEntry: LoadConfig fa"...
0x14002236e  jmp     loc_140022552
0x140022373  lea     r8, ?FilterHandle@@3PEAU_FLT_FILTER@@EA; RetFilter
0x14002237a  mov     rcx, rdi; Driver
0x14002237d  lea     rdx, Registration; Registration
0x140022384  call    cs:__imp_FltRegisterFilter
0x14002238b  nop     dword ptr [rax+rax+00h]
0x140022390  mov     ebx, eax
0x140022392  test    eax, eax
0x140022394  jns     short loc_1400223A2
0x140022396  lea     rcx, aWinsetupmonDri_2; "WinSetupMon::DriverEntry: Failed FltReg"...
0x14002239d  jmp     loc_140022550
0x1400223a2  xor     edx, edx; Remove
0x1400223a4  lea     rcx, WinSetupMonCreateProcessNotificationCallback; NotifyRoutine
0x1400223ab  call    cs:__imp_PsSetCreateProcessNotifyRoutine
0x1400223b2  nop     dword ptr [rax+rax+00h]
0x1400223b7  test    eax, eax
0x1400223b9  jns     short loc_1400223CB
0x1400223bb  mov     edx, eax
0x1400223bd  lea     rcx, aWinsetupmonDri; "WinSetupMon::DriverEntry: Failed PsSetC"...
0x1400223c4  call    TraceError
0x1400223c9  jmp     short loc_1400223D2
0x1400223cb  mov     cs:byte_1400194C0, 1
0x1400223d2  mov     edx, 1F0001h; DesiredAccess
0x1400223d7  lea     rcx, [rsp+140h+SecurityDescriptor]; SecurityDescriptor
0x1400223dc  call    cs:__imp_FltBuildDefaultSecurityDescriptor
0x1400223e3  nop     dword ptr [rax+rax+00h]
0x1400223e8  mov     ebx, eax
0x1400223ea  test    eax, eax
0x1400223ec  jns     short loc_1400223FA
0x1400223ee  lea     rcx, aWinsetupmonDri_7; "WinSetupMon::DriverEntry: Failed FltBui"...
0x1400223f5  jmp     loc_140022550
0x1400223fa  mov     rcx, cs:?FilterHandle@@3PEAU_FLT_FILTER@@EA; Filter
0x140022401  lea     rax, aWinsetupmonpor; "\\WinSetupMonPort"
0x140022408  mov     qword ptr [rbp+40h+var_B0+8], rax
0x14002240c  lea     r8, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x140022410  mov     dword ptr [rsp+140h+MaxConnections], 1; DeviceClassGuid
0x140022418  lea     rax, [rbp+40h+var_B0]
0x14002241c  mov     [rbp+40h+ObjectAttributes.ObjectName], rax
0x140022420  lea     rdx, ?FilterPort@@3PEAU_FLT_PORT@@EA; ServerPort
0x140022427  mov     rax, [rsp+140h+SecurityDescriptor]
0x14002242c  xor     r9d, r9d; ServerPortCookie
0x14002242f  mov     [rbp+40h+ObjectAttributes.SecurityDescriptor], rax
0x140022433  lea     rax, WinSetupMonMessage
0x14002243a  mov     [rsp+140h+MessageNotifyCallback], rax; DefaultSDDLString
0x14002243f  lea     rax, WinSetupMonPortDisconnect
0x140022446  mov     [rsp+140h+DisconnectNotifyCallback], rax; Exclusive
0x14002244b  lea     rax, WinSetupMonPortConnect
0x140022452  mov     [rsp+140h+ConnectNotifyCallback], rax; DeviceCharacteristics
0x140022457  mov     qword ptr [rbp+40h+var_B0], 220020h
0x14002245f  mov     [rbp+40h+ObjectAttributes.Length], r12d
0x140022463  mov     [rbp+40h+ObjectAttributes.RootDirectory], r14
0x140022467  mov     [rbp+40h+ObjectAttributes.Attributes], 240h
0x14002246e  mov     [rbp+40h+ObjectAttributes.SecurityQualityOfService], r14
0x140022472  call    cs:__imp_FltCreateCommunicationPort
0x140022479  nop     dword ptr [rax+rax+00h]
0x14002247e  mov     ebx, eax
0x140022480  test    eax, eax
0x140022482  jns     short loc_140022490
0x140022484  lea     rcx, aWinsetupmonDri_3; "WinSetupMon::DriverEntry: Failed FltCre"...
0x14002248b  jmp     loc_140022550
0x140022490  lea     rax, aDeviceWinsetup; "\\Device\\WinSetupMon"
0x140022497  mov     qword ptr [rsp+140h+DeviceName.Length], 280026h
0x1400224a0  lea     r8, [rsp+140h+DeviceName]; DeviceName
0x1400224a5  mov     [rsp+140h+DeviceName.Buffer], rax
0x1400224aa  mov     rcx, rdi; DriverObject
0x1400224ad  call    WdmlibIoCreateDeviceSecure
0x1400224b2  mov     ebx, eax
0x1400224b4  test    eax, eax
0x1400224b6  jns     short loc_1400224C4
0x1400224b8  lea     rcx, aWinsetupmonDri_8; "WinSetupMon::DriverEntry: Failed IoCrea"...
0x1400224bf  jmp     loc_140022550
0x1400224c4  lea     rax, aDosdevicesWins; "\\DosDevices\\WinSetupMon"
0x1400224cb  mov     qword ptr [rbp+40h+SymbolicLinkName.Length], 30002Eh
0x1400224d3  lea     rdx, [rsp+140h+DeviceName]; DeviceName
0x1400224d8  mov     [rbp+40h+SymbolicLinkName.Buffer], rax
0x1400224dc  lea     rcx, [rbp+40h+SymbolicLinkName]; SymbolicLinkName
0x1400224e0  call    cs:__imp_IoCreateSymbolicLink
0x1400224e7  nop     dword ptr [rax+rax+00h]
0x1400224ec  mov     ebx, eax
0x1400224ee  test    eax, eax
0x1400224f0  jns     short loc_1400224FB
0x1400224f2  lea     rcx, aWinsetupmonDri_0; "WinSetupMon::DriverEntry: Failed IoCrea"...
0x1400224f9  jmp     short loc_140022550
0x1400224fb  lea     rax, WinSetupMonCreateClose
0x140022502  mov     cs:byte_1400194C1, 1
0x140022509  mov     [rdi+80h], rax
0x140022510  mov     [rdi+70h], rax
0x140022514  lea     rax, WinSetupMonDeviceControl
0x14002251b  mov     [rdi+0E0h], rax
0x140022522  mov     [rdi+0E8h], rax
0x140022529  mov     rcx, cs:?FilterHandle@@3PEAU_FLT_FILTER@@EA; Filter
0x140022530  mov     cs:DriverObject, rdi
0x140022537  call    cs:__imp_FltStartFiltering
0x14002253e  nop     dword ptr [rax+rax+00h]
0x140022543  mov     ebx, eax
0x140022545  test    eax, eax
0x140022547  jns     short loc_140022557
0x140022549  lea     rcx, aWinsetupmonDri_1; "WinSetupMon::DriverEntry: Failed FltSta"...
0x140022550  mov     edx, eax
0x140022552  call    TraceError
0x140022557  mov     rcx, [rsp+140h+SecurityDescriptor]; SecurityDescriptor
0x14002255c  test    rcx, rcx
0x14002255f  jz      short loc_14002256D
0x140022561  call    cs:__imp_FltFreeSecurityDescriptor
0x140022568  nop     dword ptr [rax+rax+00h]
0x14002256d  test    ebx, ebx
0x14002256f  jns     loc_140022681
0x140022575  cmp     cs:byte_1400194C1, r14b
0x14002257c  jz      short loc_1400225A9
0x14002257e  lea     rcx, [rbp+40h+SymbolicLinkName]; SymbolicLinkName
0x140022582  call    cs:__imp_IoDeleteSymbolicLink
0x140022589  nop     dword ptr [rax+rax+00h]
0x14002258e  test    eax, eax
0x140022590  jns     short loc_1400225A2
0x140022592  mov     edx, eax
0x140022594  lea     rcx, aWinsetupmonDri_4; "WinSetupMon::DriverEntry: Failed IoDele"...
0x14002259b  call    TraceError
0x1400225a0  jmp     short loc_1400225A9
0x1400225a2  mov     cs:byte_1400194C1, r14b
0x1400225a9  mov     rcx, cs:DeviceObject; DeviceObject
0x1400225b0  test    rcx, rcx
0x1400225b3  jz      short loc_1400225C8
0x1400225b5  call    cs:__imp_IoDeleteDevice
  ... truncated ...
```
