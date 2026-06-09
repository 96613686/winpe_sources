# DriverEntry

- ea: `0x1400161ec`
- end: `0x140016919`
- name: `DriverEntry`
- size: `1837`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140016010`

## callees

- `0x140004e84`
- `0x14000666c`
- `0x140008a78`
- `0x140008d20`
- `0x140009240`
- `0x1400126f8`
- `0x140012c78`
- `0x14001348c`
- `0x140013520`
- `0x140013e18`
- `0x140013e70`
- `0x140014040`
- `0x140016078`
- `0x1400161ec`
- `0x140016920`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14001678c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001678c`
- `ntoskrnl!RtlGetVersion` at `0x1400164a3`
- `ntoskrnl!RtlGetVersion` at `0x1400164a3`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14001639a`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14001639a`
- `ntoskrnl!PcwRegister` at `0x1400166b8`
- `ntoskrnl!PcwRegister` at `0x140016711`
- `ntoskrnl!PcwRegister` at `0x1400166b8`
- `ntoskrnl!PcwRegister` at `0x140016711`
- `HAL!KeQueryPerformanceCounter` at `0x1400163b4`
- `HAL!KeQueryPerformanceCounter` at `0x1400163b4`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x1400168e6`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x1400168e6`
- `FLTMGR!FltStartFiltering` at `0x140016892`
- `FLTMGR!FltStartFiltering` at `0x140016892`
- `FLTMGR!FltCreateCommunicationPort` at `0x140016852`
- `FLTMGR!FltCreateCommunicationPort` at `0x140016852`
- `FLTMGR!FltBuildDefaultSecurityDescriptor` at `0x1400167a2`
- `FLTMGR!FltBuildDefaultSecurityDescriptor` at `0x1400167a2`
- `FLTMGR!FltRegisterFilter` at `0x140016739`
- `FLTMGR!FltRegisterFilter` at `0x140016739`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x1400163eb`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x1400163eb`
- `FLTMGR!FltInitializePushLock` at `0x140016323`
- `FLTMGR!FltInitializePushLock` at `0x140016323`

## string_xrefs

- `0x140016211`: `\Registry\Machine\System\CurrentControlSet\Control\QoS`
- `0x14001657c`: `CapacityCompensationPercent`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS QoSControlSecurityDescriptor; // ebx
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  __int64 v5; // rdx
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  int v8; // edx
  int v9; // r8d
  int v10; // r9d
  int v12; // [rsp+40h] [rbp-C0h] BYREF
  int v13; // [rsp+44h] [rbp-BCh] BYREF
  int v14; // [rsp+48h] [rbp-B8h] BYREF
  int v15; // [rsp+4Ch] [rbp-B4h] BYREF
  int v16; // [rsp+50h] [rbp-B0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp-A8h] BYREF
  _PCW_REGISTRATION_INFORMATION Info; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v19; // [rsp+90h] [rbp-70h]
  _QWORD v20[2]; // [rsp+98h] [rbp-68h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE VersionInformation[284]; // [rsp+F0h] [rbp-10h] BYREF
  _OWORD v24[5]; // [rsp+210h] [rbp+110h] BYREF
  _OWORD v25[2]; // [rsp+260h] [rbp+160h]

  v24[0] = *(_OWORD *)L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\QoS";
  v24[2] = *(_OWORD *)L"e\\System\\CurrentControlSet\\Control\\QoS";
  v24[1] = *(_OWORD *)L"y\\Machine\\System\\CurrentControlSet\\Control\\QoS";
  v24[4] = *(_OWORD *)L"ControlSet\\Control\\QoS";
  v20[1] = v24;
  v24[3] = *(_OWORD *)L"\\CurrentControlSet\\Control\\QoS";
  v25[0] = *(_OWORD *)L"et\\Control\\QoS";
  *(_OWORD *)((char *)v25 + 14) = *(_OWORD *)L"rol\\QoS";
  v20[0] = 7209068;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(VersionInformation, 0, sizeof(VersionInformation));
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  SecurityDescriptor = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_StorQosFltTraceGuid;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  wil_InitializeFeatureStaging();
  memset(&SqosGlobals, 0, 0x180u);
  DeviceObject = (PDEVICE_OBJECT)DriverObject;
  Filter = 0;
  FltInitializePushLock(&SqosGlobals);
  qword_14000D150 = (__int64)&qword_14000D148;
  qword_14000D148 = (__int64)&qword_14000D148;
  qword_14000D170 = (__int64)&qword_14000D168;
  qword_14000D168 = (__int64)&qword_14000D168;
  qword_14000D158 = 0;
  qword_14000D160 = 0;
  byte_14000D178 = 0;
  ExInitializeLookasideListEx(&Lookaside, 0, 0, (POOL_TYPE)512, 0, 0x140u, 0x46535153u, 0);
  word_14000D2A8 = 0;
  KeQueryPerformanceCounter(&PerformanceFrequency);
  dword_14000D2A0 = 0x2000;
  byte_14000D2AA = 0;
  qword_14000D298 = 0x9896800000uLL / PerformanceFrequency.QuadPart;
  FltWorkItem = FltAllocateGenericWorkItem();
  if ( !FltWorkItem )
  {
    QoSControlSecurityDescriptor = -1073741670;
    goto LABEL_46;
  }
  ::SecurityDescriptor = 0;
  QoSControlSecurityDescriptor = SqospCreateQoSControlSecurityDescriptor(&::SecurityDescriptor);
  if ( QoSControlSecurityDescriptor >= 0 )
  {
    v12 = 83000;
    v16 = 1000;
    v15 = 10;
    v14 = 25;
    v13 = 0;
    memset(&VersionInformation[4], 0, 0x118u);
    *(_DWORD *)VersionInformation = 284;
    QoSControlSecurityDescriptor = RtlGetVersion((PRTL_OSVERSIONINFOW)VersionInformation);
    if ( QoSControlSecurityDescriptor >= 0 )
    {
      if ( VersionInformation[282] == 1 )
        byte_14000D2AB = 1;
      SqospGetParametersUINT32(
        (_DWORD)DriverObject,
        (unsigned int)L"LatencyTargetMicroseconds",
        1000,
        10000000,
        (__int64)&v12);
      SqospGetParametersUINT32(
        (_DWORD)DriverObject,
        (unsigned int)L"MinimumDeviceLatencyMicroseconds",
        1000,
        v12,
        (__int64)&v16);
      SqospGetParametersUINT32((_DWORD)DriverObject, (unsigned int)L"UnreservedCapacityPercent", 1, 50, (__int64)&v15);
      SqospGetParametersUINT32(
        (_DWORD)DriverObject,
        (unsigned int)L"CapacityCompensationPercent",
        0,
        100,
        (__int64)&v14);
      SqospGetParametersBOOLEAN(DriverObject, v7, &byte_14000D2AA);
      SqospGetParametersUINT32((_DWORD)DriverObject, (unsigned int)L"DefaultFlowBypassPolicy", 0, 2, (__int64)&v13);
      if ( v13 == 1 )
      {
        byte_14000D2AB = 1;
      }
      else if ( v13 == 2 )
      {
        byte_14000D2AB = 0;
      }
      SqospGetRegistryUINT32((unsigned int)v20, v8, v9, v10, (__int64)&dword_14000D2A0);
      dword_14000D2A0 = ((dword_14000D2A0 - 1)
                       | ((unsigned int)(dword_14000D2A0 - 1) >> 1)
                       | (((dword_14000D2A0 - 1) | ((unsigned int)(dword_14000D2A0 - 1) >> 1)) >> 2)
                       | (((dword_14000D2A0 - 1)
                         | ((unsigned int)(dword_14000D2A0 - 1) >> 1)
                         | (((dword_14000D2A0 - 1) | ((unsigned int)(dword_14000D2A0 - 1) >> 1)) >> 2)) >> 4)
                       | (((dword_14000D2A0 - 1)
                         | ((unsigned int)(dword_14000D2A0 - 1) >> 1)
                         | (((dword_14000D2A0 - 1) | ((unsigned int)(dword_14000D2A0 - 1) >> 1)) >> 2)
                         | (((dword_14000D2A0 - 1)
                           | ((unsigned int)(dword_14000D2A0 - 1) >> 1)
                           | (((dword_14000D2A0 - 1) | ((unsigned int)(dword_14000D2A0 - 1) >> 1)) >> 2)) >> 4)) >> 8)
                       | (((dword_14000D2A0 - 1)
                         | ((unsigned int)(dword_14000D2A0 - 1) >> 1)
                         | (((dword_14000D2A0 - 1) | ((unsigned int)(dword_14000D2A0 - 1) >> 1)) >> 2)
                         | (((dword_14000D2A0 - 1)
                           | ((unsigned int)(dword_14000D2A0 - 1) >> 1)
                           | (((dword_14000D2A0 - 1) | ((unsigned int)(dword_14000D2A0 - 1) >> 1)) >> 2)) >> 4)
                         | (((dword_14000D2A0 - 1)
                           | ((unsigned int)(dword_14000D2A0 - 1) >> 1)
                           | (((dword_14000D2A0 - 1) | ((unsigned int)(dword_14000D2A0 - 1) >> 1)) >> 2)
                           | (((dword_14000D2A0 - 1)
                             | ((unsigned int)(dword_14000D2A0 - 1) >> 1)
                             | (((dword_14000D2A0 - 1) | ((unsigned int)(dword_14000D2A0 - 1) >> 1)) >> 2)) >> 4)) >> 8)) >> 16))
                      + 1;
      dword_14000D2A4 = SqospLogBase2();
      qword_14000D330 = 10000000;
      qword_14000D328 = 100000;
      BalanceInitialize(PerformanceFrequency.LowPart, v12, v16, v15, v14);
      QoSControlSecurityDescriptor = SqospInitializeJobDispatcher(&Object);
      if ( QoSControlSecurityDescriptor < 0 )
        goto LABEL_46;
      *(_QWORD *)&Info.Version = 512;
      Info.Name = (PCUNICODE_STRING)L"68";
      *(_QWORD *)&Info.CounterCount = 18;
      Info.Counters = (PPCW_COUNTER_DESCRIPTOR)`SqosPcInitRegistrationInformationDeviceCounterSet'::`2'::Descriptors;
      v19 = 0;
      Info.Callback = 0;
      Info.CallbackContext = 0;
      if ( PcwRegister(&SqosPcDeviceCounterSet, &Info) >= 0 )
        LOBYTE(word_14000D2A8) = 1;
      *(_QWORD *)&Info.Version = 512;
      Info.Name = (PCUNICODE_STRING)L"24";
      *(_QWORD *)&Info.CounterCount = 10;
      Info.Counters = (PPCW_COUNTER_DESCRIPTOR)`SqosPcInitRegistrationInformationFlowCounterSet'::`2'::Descriptors;
      v19 = 0;
      Info.Callback = 0;
      Info.CallbackContext = 0;
      if ( PcwRegister(&SqosPcFlowCounterSet, &Info) >= 0 )
        HIBYTE(word_14000D2A8) = 1;
      QoSControlSecurityDescriptor = FltRegisterFilter(DriverObject, &SqosFilterRegistration, (PFLT_FILTER *)&Filter);
      if ( QoSControlSecurityDescriptor >= 0 )
      {
        RtlInitUnicodeString(&DestinationString, L"\\storqosfltport");
        QoSControlSecurityDescriptor = FltBuildDefaultSecurityDescriptor(&SecurityDescriptor, 0x1F0001u);
        if ( QoSControlSecurityDescriptor >= 0 )
        {
          ObjectAttributes.ObjectName = &DestinationString;
          ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
          ObjectAttributes.Length = 48;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.Attributes = 576;
          ObjectAttributes.SecurityQualityOfService = 0;
          QoSControlSecurityDescriptor = FltCreateCommunicationPort(
                                           (PFLT_FILTER)Filter,
                                           &ServerPort,
                                           &ObjectAttributes,
                                           0,
                                           SqosConnectNotifyCallback,
                                           SqosDisconnectNotifyCallback,
                                           SqosMessageNotifyCallback,
                                           1);
          if ( QoSControlSecurityDescriptor >= 0 )
          {
            QoSControlSecurityDescriptor = FltStartFiltering((PFLT_FILTER)Filter);
            if ( QoSControlSecurityDescriptor >= 0 )
              goto LABEL_46;
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            {
              goto LABEL_46;
            }
            v5 = 15;
          }
          else
          {
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            {
              goto LABEL_46;
            }
            v5 = 14;
          }
        }
        else
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_46;
          }
          v5 = 13;
        }
      }
      else
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_46;
        }
        v5 = 12;
      }
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_46;
      }
      v5 = 11;
    }
    AttachedDevice = v6->AttachedDevice;
    goto LABEL_45;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    v5 = 10;
LABEL_45:
    WPP_SF_d(
      AttachedDevice,
      v5,
      WPP_97d16c38264433ff5e04fa48b3a3652b_Traceguids,
      (unsigned int)QoSControlSecurityDescriptor);
  }
LABEL_46:
  if ( SecurityDescriptor )
    FltFreeSecurityDescriptor(SecurityDescriptor);
  if ( QoSControlSecurityDescriptor < 0 )
    SqosFilterUnloadInternal();
  return QoSControlSecurityDescriptor;
}

```

## disassembly

```asm
0x1400161ec  push    rbp
0x1400161ee  push    rbx
0x1400161ef  push    rsi
0x1400161f0  push    rdi
0x1400161f1  lea     rbp, [rsp-198h]
0x1400161f9  sub     rsp, 298h
0x140016200  mov     rax, cs:__security_cookie
0x140016207  xor     rax, rsp
0x14001620a  mov     [rbp+1B0h+var_30], rax
0x140016211  movaps  xmm0, xmmword ptr cs:aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x140016218  lea     rax, [rbp+1B0h+var_A0]
0x14001621f  movaps  xmm1, xmmword ptr cs:aRegistryMachin+10h; "y\\Machine\\System\\CurrentControlSet\\"...
0x140016226  mov     rdi, rcx
0x140016229  movaps  [rbp+1B0h+var_A0], xmm0
0x140016230  lea     rcx, [rbp+1B0h+VersionInformation]; void *
0x140016234  movaps  xmm0, xmmword ptr cs:aRegistryMachin+20h; "e\\System\\CurrentControlSet\\Control\\"...
0x14001623b  xor     edx, edx; Val
0x14001623d  movaps  [rbp+1B0h+var_80], xmm0
0x140016244  mov     r8d, 11Ch; Size
0x14001624a  movaps  xmm0, xmmword ptr cs:aRegistryMachin+40h; "ControlSet\\Control\\QoS"
0x140016251  movaps  [rbp+1B0h+var_90], xmm1
0x140016258  movaps  xmm1, xmmword ptr cs:aRegistryMachin+30h; "\\CurrentControlSet\\Control\\QoS"
0x14001625f  movaps  [rbp+1B0h+var_60], xmm0
0x140016266  movups  xmm0, xmmword ptr cs:aRegistryMachin+5Eh; "rol\\QoS"
0x14001626d  mov     [rbp+1B0h+var_210], rax
0x140016271  xor     eax, eax
0x140016273  movaps  [rbp+1B0h+var_70], xmm1
0x14001627a  movaps  xmm1, xmmword ptr cs:aRegistryMachin+50h; "et\\Control\\QoS"
0x140016281  movaps  xmmword ptr [rbp+1B0h+var_50], xmm1
0x140016288  movups  xmmword ptr [rbp+1B0h+var_50+0Eh], xmm0
0x14001628f  mov     [rbp+1B0h+var_218], 6E006Ch
0x140016297  xorps   xmm0, xmm0
0x14001629a  movups  xmmword ptr [rbp+1B0h+ObjectAttributes.ObjectName], xmm0
0x14001629e  movups  xmmword ptr [rbp+1B0h+ObjectAttributes+1Ch], xmm0
0x1400162a2  movups  xmmword ptr [rbp+1B0h+DestinationString.Length], xmm0
0x1400162a6  movups  xmmword ptr [rbp+1B0h+ObjectAttributes.Length], xmm0
0x1400162aa  call    memset
0x1400162af  xor     esi, esi
0x1400162b1  mov     cs:WPP_MAIN_CB.Timer, 1
0x1400162bc  lea     rax, WPP_ThisDir_CTLGUID_StorQosFltTraceGuid
0x1400162c3  mov     [rsp+2B0h+SecurityDescriptor], rsi
0x1400162c8  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x1400162cf  mov     qword ptr cs:WPP_MAIN_CB.Type, rsi
0x1400162d6  mov     cs:WPP_MAIN_CB.NextDevice, rsi
0x1400162dd  mov     cs:WPP_MAIN_CB.CurrentIrp, rsi
0x1400162e4  call    WppLoadTracingSupport
0x1400162e9  mov     cs:WPP_MAIN_CB.CurrentIrp, rsi
0x1400162f0  call    WppInitKm
0x1400162f5  call    wil_InitializeFeatureStaging
0x1400162fa  xor     edx, edx; Val
0x1400162fc  lea     rcx, SqosGlobals; void *
0x140016303  mov     r8d, 180h; Size
0x140016309  call    memset
0x14001630e  lea     rcx, SqosGlobals; PushLock
0x140016315  mov     cs:DeviceObject, rdi
0x14001631c  mov     cs:Filter, rsi
0x140016323  call    cs:__imp_FltInitializePushLock
0x14001632a  nop     dword ptr [rax+rax+00h]
0x14001632f  lea     rax, qword_14000D148
0x140016336  mov     [rsp+2B0h+Depth], si; Depth
0x14001633b  mov     cs:qword_14000D150, rax
0x140016342  lea     rcx, Lookaside; Lookaside
0x140016349  mov     cs:qword_14000D148, rax
0x140016350  mov     r9d, 200h; PoolType
0x140016356  lea     rax, qword_14000D168
0x14001635d  mov     [rsp+2B0h+Tag], 46535153h; Tag
0x140016365  mov     [rsp+2B0h+Size], 140h; Size
0x14001636e  xor     r8d, r8d; Free
0x140016371  xor     edx, edx; Allocate
0x140016373  mov     cs:qword_14000D170, rax
0x14001637a  mov     cs:qword_14000D168, rax
0x140016381  mov     cs:qword_14000D158, rsi
0x140016388  mov     cs:qword_14000D160, rsi
0x14001638f  mov     cs:byte_14000D178, sil
0x140016396  mov     [rsp+2B0h+Flags], esi; Flags
0x14001639a  call    cs:__imp_ExInitializeLookasideListEx
0x1400163a1  nop     dword ptr [rax+rax+00h]
0x1400163a6  lea     rcx, PerformanceFrequency; PerformanceFrequency
0x1400163ad  mov     cs:word_14000D2A8, si
0x1400163b4  call    cs:__imp_KeQueryPerformanceCounter
0x1400163bb  nop     dword ptr [rax+rax+00h]
0x1400163c0  xor     edx, edx
0x1400163c2  mov     cs:dword_14000D2A0, 2000h
0x1400163cc  mov     rax, 9896800000h
0x1400163d6  mov     cs:byte_14000D2AA, sil
0x1400163dd  div     qword ptr cs:PerformanceFrequency
0x1400163e4  mov     cs:qword_14000D298, rax
0x1400163eb  call    cs:__imp_FltAllocateGenericWorkItem
0x1400163f2  nop     dword ptr [rax+rax+00h]
0x1400163f7  mov     cs:FltWorkItem, rax
0x1400163fe  test    rax, rax
0x140016401  jnz     short loc_14001640D
0x140016403  mov     ebx, 0C000009Ah
0x140016408  jmp     loc_1400168DC
0x14001640d  lea     rcx, SecurityDescriptor
0x140016414  mov     cs:SecurityDescriptor, rsi
0x14001641b  call    SqospCreateQoSControlSecurityDescriptor
0x140016420  mov     ebx, eax
0x140016422  test    eax, eax
0x140016424  jns     short loc_140016463
0x140016426  mov     r10, cs:WPP_GLOBAL_Control
0x14001642d  lea     rax, WPP_GLOBAL_Control
0x140016434  cmp     r10, rax
0x140016437  jz      loc_1400168DC
0x14001643d  mov     ecx, [r10+2Ch]
0x140016441  test    cl, 1
0x140016444  jz      loc_1400168DC
0x14001644a  cmp     byte ptr [r10+29h], 2
0x14001644f  jb      loc_1400168DC
0x140016455  mov     rcx, [r10+18h]
0x140016459  mov     edx, 0Ah
0x14001645e  jmp     loc_1400168CD
0x140016463  xor     edx, edx; Val
0x140016465  mov     [rsp+2B0h+var_270], 14438h
0x14001646d  mov     r8d, 118h; Size
0x140016473  mov     [rsp+2B0h+var_260], 3E8h
0x14001647b  lea     rcx, [rbp+1B0h+VersionInformation.dwMajorVersion]; void *
0x14001647f  mov     [rsp+2B0h+var_264], 0Ah
0x140016487  mov     [rsp+2B0h+var_268], 19h
0x14001648f  mov     [rsp+2B0h+var_26C], esi
0x140016493  call    memset
0x140016498  lea     rcx, [rbp+1B0h+VersionInformation]; lpVersionInformation
0x14001649c  mov     [rbp+1B0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1400164a3  call    cs:__imp_RtlGetVersion
0x1400164aa  nop     dword ptr [rax+rax+00h]
0x1400164af  mov     ebx, eax
0x1400164b1  test    eax, eax
0x1400164b3  jns     short loc_1400164EB
0x1400164b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400164bc  lea     rax, WPP_GLOBAL_Control
0x1400164c3  cmp     rcx, rax
0x1400164c6  jz      loc_1400168DC
0x1400164cc  mov     eax, [rcx+2Ch]
0x1400164cf  test    al, 1
0x1400164d1  jz      loc_1400168DC
0x1400164d7  cmp     byte ptr [rcx+29h], 2
0x1400164db  jb      loc_1400168DC
0x1400164e1  mov     edx, 0Bh
0x1400164e6  jmp     loc_1400168C9
0x1400164eb  cmp     [rbp+1B0h+var_A6], 1
0x1400164f2  jnz     short loc_1400164FB
0x1400164f4  mov     cs:byte_14000D2AB, 1
0x1400164fb  lea     rax, [rsp+2B0h+var_270]
0x140016500  mov     ebx, 989680h
0x140016505  mov     r9d, ebx
0x140016508  mov     qword ptr [rsp+2B0h+Flags], rax
0x14001650d  mov     r8d, 3E8h
0x140016513  lea     rdx, aLatencytargetm; "LatencyTargetMicroseconds"
0x14001651a  mov     rcx, rdi
0x14001651d  call    SqospGetParametersUINT32
0x140016522  mov     r9d, [rsp+2B0h+var_270]
0x140016527  lea     rax, [rsp+2B0h+var_260]
0x14001652c  mov     r8d, 3E8h
0x140016532  mov     qword ptr [rsp+2B0h+Flags], rax
0x140016537  lea     rdx, aMinimumdevicel; "MinimumDeviceLatencyMicroseconds"
0x14001653e  mov     rcx, rdi
0x140016541  call    SqospGetParametersUINT32
0x140016546  mov     r9d, 32h ; '2'
0x14001654c  lea     rax, [rsp+2B0h+var_264]
0x140016551  lea     rdx, aUnreservedcapa; "UnreservedCapacityPercent"
0x140016558  mov     qword ptr [rsp+2B0h+Flags], rax
0x14001655d  mov     rcx, rdi
0x140016560  lea     r8d, [r9-31h]
0x140016564  call    SqospGetParametersUINT32
0x140016569  lea     rax, [rsp+2B0h+var_268]
0x14001656e  mov     r9d, 64h ; 'd'
0x140016574  xor     r8d, r8d
0x140016577  mov     qword ptr [rsp+2B0h+Flags], rax
0x14001657c  lea     rdx, aCapacitycompen; "CapacityCompensationPercent"
0x140016583  mov     rcx, rdi
0x140016586  call    SqospGetParametersUINT32
0x14001658b  lea     r8, byte_14000D2AA
0x140016592  mov     rcx, rdi
0x140016595  call    SqospGetParametersBOOLEAN
0x14001659a  lea     rax, [rsp+2B0h+var_26C]
0x14001659f  mov     r9d, 2
0x1400165a5  xor     r8d, r8d
0x1400165a8  mov     qword ptr [rsp+2B0h+Flags], rax
0x1400165ad  lea     rdx, aDefaultflowbyp; "DefaultFlowBypassPolicy"
0x1400165b4  mov     rcx, rdi
0x1400165b7  call    SqospGetParametersUINT32
0x1400165bc  mov     eax, [rsp+2B0h+var_26C]
0x1400165c0  sub     eax, 1
0x1400165c3  jz      short loc_1400165D3
0x1400165c5  cmp     eax, 1
0x1400165c8  jnz     short loc_1400165DA
0x1400165ca  mov     cs:byte_14000D2AB, sil
0x1400165d1  jmp     short loc_1400165DA
0x1400165d3  mov     cs:byte_14000D2AB, 1
0x1400165da  lea     rax, dword_14000D2A0
0x1400165e1  lea     rcx, [rbp+1B0h+var_218]
0x1400165e5  mov     qword ptr [rsp+2B0h+Flags], rax
0x1400165ea  call    SqospGetRegistryUINT32
0x1400165ef  mov     eax, cs:dword_14000D2A0
0x1400165f5  dec     eax
0x1400165f7  mov     ecx, eax
0x1400165f9  shr     ecx, 1
0x1400165fb  or      ecx, eax
0x1400165fd  mov     eax, ecx
0x1400165ff  shr     eax, 2
0x140016602  or      eax, ecx
0x140016604  mov     ecx, eax
0x140016606  shr     ecx, 4
0x140016609  or      ecx, eax
0x14001660b  mov     eax, ecx
0x14001660d  shr     eax, 8
0x140016610  or      eax, ecx
0x140016612  mov     ecx, eax
0x140016614  shr     ecx, 10h
0x140016617  or      ecx, eax
0x140016619  inc     ecx
0x14001661b  mov     cs:dword_14000D2A0, ecx
0x140016621  call    SqospLogBase2
0x140016626  mov     r9d, [rsp+2B0h+var_264]
0x14001662b  mov     r8d, [rsp+2B0h+var_260]
0x140016630  mov     edx, [rsp+2B0h+var_270]
0x140016634  mov     rcx, qword ptr cs:PerformanceFrequency
0x14001663b  mov     cs:dword_14000D2A4, eax
0x140016641  mov     eax, [rsp+2B0h+var_268]
0x140016645  mov     [rsp+2B0h+Flags], eax
0x140016649  mov     cs:qword_14000D330, rbx
0x140016650  mov     cs:qword_14000D328, 186A0h
0x14001665b  call    BalanceInitialize
0x140016660  lea     rcx, Object; Object
0x140016667  call    SqospInitializeJobDispatcher
0x14001666c  mov     ebx, eax
0x14001666e  test    eax, eax
0x140016670  js      loc_1400168DC
0x140016676  lea     rax, ?Name@?1??SqosPcInitRegistrationInformationDeviceCounterSet@@9@9; "68"
0x14001667d  mov     qword ptr [rsp+2B0h+Info.Version], 200h
0x140016686  mov     [rsp+2B0h+Info.Name], rax
0x14001668b  lea     rdx, [rsp+2B0h+Info]; Info
0x140016690  lea     rax, ?Descriptors@?1??SqosPcInitRegistrationInformationDeviceCounterSet@@9@9; `SqosPcInitRegistrationInformationDeviceCounterSet'::`2'::Descriptors
0x140016697  mov     qword ptr [rsp+2B0h+Info.CounterCount], 12h
0x1400166a0  lea     rcx, SqosPcDeviceCounterSet; Registration
0x1400166a7  mov     [rsp+2B0h+Info.Counters], rax
0x1400166ac  mov     [rbp+1B0h+var_220], rsi
0x1400166b0  mov     [rbp+1B0h+Info.Callback], rsi
0x1400166b4  mov     [rbp+1B0h+Info.CallbackContext], rsi
0x1400166b8  call    cs:__imp_PcwRegister
0x1400166bf  nop     dword ptr [rax+rax+00h]
0x1400166c4  test    eax, eax
0x1400166c6  js      short loc_1400166CF
0x1400166c8  mov     byte ptr cs:word_14000D2A8, 1
0x1400166cf  lea     rax, ?Name@?1??SqosPcInitRegistrationInformationFlowCounterSet@@9@9; "24"
0x1400166d6  mov     qword ptr [rsp+2B0h+Info.Version], 200h
0x1400166df  mov     [rsp+2B0h+Info.Name], rax
0x1400166e4  lea     rdx, [rsp+2B0h+Info]; Info
0x1400166e9  lea     rax, ?Descriptors@?1??SqosPcInitRegistrationInformationFlowCounterSet@@9@9; `SqosPcInitRegistrationInformationFlowCounterSet'::`2'::Descriptors
0x1400166f0  mov     qword ptr [rsp+2B0h+Info.CounterCount], 0Ah
0x1400166f9  lea     rcx, SqosPcFlowCounterSet; Registration
0x140016700  mov     [rsp+2B0h+Info.Counters], rax
0x140016705  mov     [rbp+1B0h+var_220], rsi
0x140016709  mov     [rbp+1B0h+Info.Callback], rsi
0x14001670d  mov     [rbp+1B0h+Info.CallbackContext], rsi
0x140016711  call    cs:__imp_PcwRegister
0x140016718  nop     dword ptr [rax+rax+00h]
0x14001671d  test    eax, eax
0x14001671f  js      short loc_140016728
0x140016721  mov     byte ptr cs:word_14000D2A8+1, 1
0x140016728  lea     r8, Filter; RetFilter
0x14001672f  mov     rcx, rdi; Driver
0x140016732  lea     rdx, SqosFilterRegistration; Registration
0x140016739  call    cs:__imp_FltRegisterFilter
0x140016740  nop     dword ptr [rax+rax+00h]
0x140016745  mov     ebx, eax
0x140016747  test    eax, eax
0x140016749  jns     short loc_140016781
0x14001674b  mov     rcx, cs:WPP_GLOBAL_Control
0x140016752  lea     rax, WPP_GLOBAL_Control
0x140016759  cmp     rcx, rax
0x14001675c  jz      loc_1400168DC
0x140016762  mov     eax, [rcx+2Ch]
0x140016765  test    al, 1
0x140016767  jz      loc_1400168DC
0x14001676d  cmp     byte ptr [rcx+29h], 2
0x140016771  jb      loc_1400168DC
0x140016777  mov     edx, 0Ch
0x14001677c  jmp     loc_1400168C9
0x140016781  lea     rdx, aStorqosfltport; "\\storqosfltport"
0x140016788  lea     rcx, [rbp+1B0h+DestinationString]; DestinationString
0x14001678c  call    cs:__imp_RtlInitUnicodeString
0x140016793  nop     dword ptr [rax+rax+00h]
0x140016798  mov     edx, 1F0001h; DesiredAccess
0x14001679d  lea     rcx, [rsp+2B0h+SecurityDescriptor]; SecurityDescriptor
0x1400167a2  call    cs:__imp_FltBuildDefaultSecurityDescriptor
0x1400167a9  nop     dword ptr [rax+rax+00h]
0x1400167ae  mov     ebx, eax
0x1400167b0  test    eax, eax
0x1400167b2  jns     short loc_1400167EA
0x1400167b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400167bb  lea     rax, WPP_GLOBAL_Control
0x1400167c2  cmp     rcx, rax
0x1400167c5  jz      loc_1400168DC
0x1400167cb  mov     eax, [rcx+2Ch]
0x1400167ce  test    al, 1
0x1400167d0  jz      loc_1400168DC
0x1400167d6  cmp     byte ptr [rcx+29h], 2
0x1400167da  jb      loc_1400168DC
0x1400167e0  mov     edx, 0Dh
  ... truncated ...
```
