# DriverEntry

- ea: `0x14005b3c8`
- end: `0x14005bbb2`
- name: `DriverEntry`
- size: `2026`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14005b360`

## callees

- `0x140008360`
- `0x14000fc18`
- `0x14001389c`
- `0x140013a44`
- `0x140014a00`
- `0x140015790`
- `0x140015850`
- `0x14001efcc`
- `0x140020a94`
- `0x14002a840`
- `0x140041218`
- `0x1400416ac`
- `0x140041740`
- `0x140041770`
- `0x140041d24`
- `0x1400556b0`
- `0x140056010`
- `0x1400564f0`
- `0x140056be0`
- `0x140056e3c`
- `0x140057028`
- `0x14005b008`
- `0x14005b0a0`
- `0x14005b190`
- `0x14005b220`
- `0x14005b3c8`
- `0x14005bbb8`

## import_xrefs

- `ntoskrnl!ZwPowerInformation` at `0x14005ba6a`
- `ntoskrnl!ZwPowerInformation` at `0x14005ba6a`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005b83a`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005b83a`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14005b477`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14005b477`
- `ntoskrnl!KeInitializeSpinLock` at `0x14005b715`
- `ntoskrnl!KeInitializeSpinLock` at `0x14005b8ed`
- `ntoskrnl!KeInitializeSpinLock` at `0x14005b915`
- `ntoskrnl!KeInitializeSpinLock` at `0x14005b715`
- `ntoskrnl!KeInitializeSpinLock` at `0x14005b8ed`
- `ntoskrnl!KeInitializeSpinLock` at `0x14005b915`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005b619`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005b619`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x14005b491`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x14005b491`
- `ntoskrnl!ExInitializeResourceLite` at `0x14005b728`
- `ntoskrnl!ExInitializeResourceLite` at `0x14005b742`
- `ntoskrnl!ExInitializeResourceLite` at `0x14005b759`
- `ntoskrnl!ExInitializeResourceLite` at `0x14005b773`
- `ntoskrnl!ExInitializeResourceLite` at `0x14005b78d`
- `ntoskrnl!ExInitializeResourceLite` at `0x14005b7a7`
- `ntoskrnl!ExInitializeResourceLite` at `0x14005b728`
- `ntoskrnl!ExInitializeResourceLite` at `0x14005b742`
- `ntoskrnl!ExInitializeResourceLite` at `0x14005b759`
- `ntoskrnl!ExInitializeResourceLite` at `0x14005b773`
- `ntoskrnl!ExInitializeResourceLite` at `0x14005b78d`
- `ntoskrnl!ExInitializeResourceLite` at `0x14005b7a7`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14005b528`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14005b528`
- `ntoskrnl!KeInitializeEvent` at `0x14005b7d9`
- `ntoskrnl!KeInitializeEvent` at `0x14005b7d9`
- `ntoskrnl!IoCreateDevice` at `0x14005b651`
- `ntoskrnl!IoCreateDevice` at `0x14005b651`
- `TDI!TdiIsIPTransportSupported` at `0x14005b4ca`
- `TDI!TdiIsIPTransportSupported` at `0x14005b4ca`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  char v3; // al
  unsigned __int8 IsIPTransportSupported; // al
  __int64 v5; // r8
  PDEVICE_OBJECT v6; // rcx
  __int64 Timer_high; // rdx
  int v8; // eax
  NTSTATUS Parameters; // edi
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  PERESOURCE v13; // rdi
  PERESOURCE v14; // rcx
  PERESOURCE v15; // rcx
  PVOID *p_Reserved2; // rax
  PERESOURCE v17; // rdi
  NTSTATUS v18; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-38h] BYREF
  char OutputBuffer; // [rsp+90h] [rbp+18h] BYREF
  int v22; // [rsp+98h] [rbp+20h]

  DestinationString = 0;
  v22 = 0;
  McGenEventRegister_EtwRegister(DriverObject, RegistryPath);
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_SrvNetLog;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_4c791a4f213531f920775678ddb20f34_Traceguids);
  }
  wil_InitializeFeatureStaging();
  ExInitializeRundownProtection(&SrvNetRdmaRundownProtector);
  SrvNetRdmaRundownSrwLock = 0;
  KeInitializeGuardedMutex(&SrvNetRdmaRundownMutex);
  if ( (int)SrvLibQueryLicensingDWord(L"SMBServer-AllowRdmaUsage") < 0 || (v3 = 1, !v22) )
    v3 = 0;
  SrvNetIsSMBDirectSupported = v3;
  IsIPTransportSupported = TdiIsIPTransportSupported();
  SrvNetUseTdiNotifications = IsIPTransportSupported;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (Timer_high & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_l(WPP_GLOBAL_Control->AttachedDevice, Timer_high, v5, IsIPTransportSupported);
  }
  if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x80000) != 0 )
    McTemplateK0t_EtwWriteTransfer(v6, SRVNET_EVENT_TDI_MODE_ENABLED, 0, (unsigned __int8)SrvNetUseTdiNotifications);
  SrvNetNumberOfActiveProcessorsAtServerStart = KeQueryActiveProcessorCountEx(0xFFFFu);
  v8 = SrvLibInitializeSecurityDescriptors();
  Parameters = v8;
  if ( v8 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_82;
    }
    v11 = 12;
    v12 = (unsigned int)v8;
LABEL_81:
    WPP_SF_d(v10->AttachedDevice, v11, WPP_4c791a4f213531f920775678ddb20f34_Traceguids, v12);
LABEL_82:
    DriverUnload();
    return Parameters;
  }
  SrvNetInitProgress |= 1u;
  Parameters = SrvAdminInitialize(DriverObject);
  if ( Parameters < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_82;
    }
    v11 = 13;
    goto LABEL_80;
  }
  SrvNetInitProgress |= 2u;
  Parameters = SmbCryptoInitialize();
  if ( Parameters < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_82;
    }
    v11 = 14;
    goto LABEL_80;
  }
  SrvNetInitProgress |= 4u;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\SrvNet");
  Parameters = IoCreateDevice(
                 DriverObject,
                 0x478u,
                 &DestinationString,
                 0x14u,
                 0x100u,
                 0,
                 (PDEVICE_OBJECT *)&SrvNetDeviceObject);
  if ( Parameters < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_82;
    }
    v11 = 15;
    goto LABEL_80;
  }
  SrvNetInitProgress |= 8u;
  Parameters = SrvLibApplyDeviceAcl((__int64)SrvNetDeviceObject, 0x1F01FFu, 0, 0x1F01FFu, 0x1F01FFu, 0);
  if ( Parameters < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_82;
    }
    v11 = 16;
    goto LABEL_80;
  }
  SrvNetDeviceExtension = (PERESOURCE)*((_QWORD *)SrvNetDeviceObject + 8);
  v13 = SrvNetDeviceExtension;
  memset(SrvNetDeviceExtension, 0, 0x478u);
  KeInitializeSpinLock((PKSPIN_LOCK)&v13[1]);
  ExInitializeResourceLite(SrvNetDeviceExtension);
  ExInitializeResourceLite((PERESOURCE)((char *)SrvNetDeviceExtension + 288));
  ExInitializeResourceLite((PERESOURCE)((char *)SrvNetDeviceExtension + 120));
  ExInitializeResourceLite((PERESOURCE)((char *)SrvNetDeviceExtension + 528));
  ExInitializeResourceLite((PERESOURCE)((char *)SrvNetDeviceExtension + 840));
  ExInitializeResourceLite((PERESOURCE)((char *)SrvNetDeviceExtension + 944));
  v14 = SrvNetDeviceExtension;
  *(_DWORD *)&SrvNetDeviceExtension[2].ActiveCount = 1;
  v14[2].SharedWaiters = 0;
  LODWORD(v14[2].ExclusiveWaiters) = 0;
  KeInitializeEvent((PRKEVENT)&v14[2].OwnerEntry, SynchronizationEvent, 0);
  v15 = SrvNetDeviceExtension;
  p_Reserved2 = &SrvNetDeviceExtension[3].Reserved2;
  SrvNetDeviceExtension[3].CreatorBackTraceIndex = (ULONG_PTR)&SrvNetDeviceExtension[3].Reserved2;
  *p_Reserved2 = p_Reserved2;
  v15[4].SystemResourcesList.Flink = (struct _LIST_ENTRY *)&v15[3].SpinLock;
  v15[3].SpinLock = (KSPIN_LOCK)&v15[3].SpinLock;
  v15[4].OwnerTable = (POWNER_ENTRY)&v15[4].SystemResourcesList.Blink;
  v15[4].SystemResourcesList.Blink = (struct _LIST_ENTRY *)&v15[4].SystemResourcesList.Blink;
  v15[10].OwnerTable = (POWNER_ENTRY)&v15[10].SystemResourcesList.Blink;
  v15[10].SystemResourcesList.Blink = (struct _LIST_ENTRY *)&v15[10].SystemResourcesList.Blink;
  SrvNetInitializeListenerRuleList(&v15[10].ActiveCount);
  v17 = SrvNetDeviceExtension;
  LODWORD(SrvNetDeviceExtension[1].SystemResourcesList.Blink) = 0;
  *(_QWORD *)&v17[4].ActiveCount = IoGetCurrentProcess();
  SrvNetInitProgress |= 0x10u;
  Parameters = SrvNetLoadParameters();
  if ( Parameters < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_82;
    }
    v11 = 17;
    goto LABEL_80;
  }
  Parameters = SrvNetWskProviderInitialize();
  if ( Parameters < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_82;
    }
    v11 = 18;
    goto LABEL_80;
  }
  SrvNetInitProgress |= 0xE0u;
  WPP_MAIN_CB.Queue.ListEntry.Blink = &WPP_MAIN_CB.Queue.ListEntry;
  WPP_MAIN_CB.Queue.ListEntry.Flink = &WPP_MAIN_CB.Queue.ListEntry;
  KeInitializeSpinLock(&SrvNetConnectionClosingListLock);
  *(_QWORD *)&WPP_MAIN_CB.DeviceType = &WPP_MAIN_CB.DeviceExtension;
  WPP_MAIN_CB.DeviceExtension = &WPP_MAIN_CB.DeviceExtension;
  KeInitializeSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
  SrvXsInitialize();
  SrvGrovelerInitialize();
  byte_140036679 |= 1u;
  Parameters = SrvIdSegInitialize();
  if ( Parameters < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_82;
    }
    v11 = 21;
    goto LABEL_80;
  }
  byte_140036679 |= 2u;
  Parameters = SrvNetCreateBufferLookasides();
  if ( Parameters < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_82;
    }
    v11 = 22;
    goto LABEL_80;
  }
  byte_140036679 |= 4u;
  Parameters = SrvNetAllocateStatisticsQueues();
  if ( Parameters < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_82;
    }
    v11 = 23;
    goto LABEL_80;
  }
  byte_140036679 |= 8u;
  *(_QWORD *)&SrvNetStatistics = MEMORY[0xFFFFF78000000014];
  Parameters = SrvNetInitializeScavenger();
  if ( Parameters < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_82;
    }
    v11 = 24;
    goto LABEL_80;
  }
  byte_140036679 |= 0x10u;
  OutputBuffer = 0;
  v18 = ZwPowerInformation((POWER_INFORMATION_LEVEL)66, 0, 0, &OutputBuffer, 1u);
  if ( v18 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        25,
        WPP_4c791a4f213531f920775678ddb20f34_Traceguids,
        (unsigned int)v18);
    }
  }
  else
  {
    SrvNetIsAoAc = OutputBuffer;
  }
  Parameters = SmbCompressionInitialize();
  if ( Parameters < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_82;
    }
    v11 = 26;
LABEL_80:
    v12 = (unsigned int)Parameters;
    goto LABEL_81;
  }
  byte_140036679 |= 0x20u;
  memset64(DriverObject->MajorFunction, (unsigned __int64)SrvNetDefaultDispatch, 0x1Cu);
  DriverObject->MajorFunction[18] = (PDRIVER_DISPATCH)SrvNetCleanup;
  DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)SrvNetClose;
  DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)&SrvNetCreate;
  DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)SrvNetDeviceControl;
  DriverObject->DriverUnload = (PDRIVER_UNLOAD)DriverUnload;
  memset(&SrvNetFastIo, 0, 0xE0u);
  SrvNetFastIo = 224;
  qword_140040200 = (__int64)SrvNetFastIoDeviceControl;
  DriverObject->FastIoDispatch = (PFAST_IO_DISPATCH)&SrvNetFastIo;
  SrvNetIsLoadedAsDriver = 1;
  SrvNetLogComponentCapabilities();
  return 0;
}

```

## disassembly

```asm
0x14005b3c8  mov     rax, rsp
0x14005b3cb  mov     [rax+8], rbx
0x14005b3cf  mov     [rax+10h], rbp
0x14005b3d3  push    rsi
0x14005b3d4  push    rdi
0x14005b3d5  push    r12
0x14005b3d7  push    r14
0x14005b3d9  push    r15
0x14005b3db  sub     rsp, 50h
0x14005b3df  xorps   xmm0, xmm0
0x14005b3e2  xor     esi, esi
0x14005b3e4  movups  xmmword ptr [rax-38h], xmm0
0x14005b3e8  mov     [rax+20h], esi
0x14005b3eb  mov     rbx, rcx
0x14005b3ee  call    McGenEventRegister_EtwRegister
0x14005b3f3  lea     rax, WPP_ThisDir_CTLGUID_SrvNetLog
0x14005b3fa  mov     qword ptr cs:WPP_MAIN_CB.Type, rsi
0x14005b401  lea     ebp, [rsi+1]
0x14005b404  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14005b40b  mov     cs:WPP_MAIN_CB.NextDevice, rsi
0x14005b412  mov     cs:WPP_MAIN_CB.CurrentIrp, rsi
0x14005b419  mov     cs:WPP_MAIN_CB.Timer, rbp
0x14005b420  call    WppLoadTracingSupport
0x14005b425  mov     cs:WPP_MAIN_CB.CurrentIrp, rsi; __annotation("TMC:", "c0183094-fdc6-493f-a3e8-697224f83f6f", "SrvNetLog", "DEBUG_TDI_PNP", "DEBUG_DISPATCH", "DEBUG_DRIVER_MAIN", "DEBUG_DRIVER_UNLOAD", "DEBUG_SRVNET", "DEBUG_SRVADMIN", "DEBUG_SRVLIB", "DEBUG_SHAREFILTER", "DEBUG_ENDPOINT", "DEBUG_TDI_CALLBACK", "DEBUG_CONNECTION", "DEBUG_SCAVENGER", "DEBUG_CLIENT", "DEBUG_NETWORK", "DEBUG_FSCTL", "DEBUG_SPOOLER", "DEBUG_WSK", "DEBUG_DISCONNECT", "DEBUG_IDSEG", "DEBUG_RDMA", "DEBUG_CRYPTO", "DEBUG_QUIC", "PUBLIC_TMF:")
0x14005b42c  call    WppInitKm
0x14005b431  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005b438  lea     r15, WPP_GLOBAL_Control
0x14005b43f  lea     r12, WPP_4c791a4f213531f920775678ddb20f34_Traceguids
0x14005b446  mov     r14b, 4
0x14005b449  cmp     rcx, r15
0x14005b44c  jz      short loc_14005B46B
0x14005b44e  mov     eax, [rcx+2Ch]
0x14005b451  test    r14b, al
0x14005b454  jz      short loc_14005B46B
0x14005b456  cmp     byte ptr [rcx+29h], 2
0x14005b45a  jb      short loc_14005B46B
0x14005b45c  mov     rcx, [rcx+18h]
0x14005b460  lea     edx, [rsi+0Ah]
0x14005b463  mov     r8, r12
0x14005b466  call    WPP_SF_
0x14005b46b  call    wil_InitializeFeatureStaging
0x14005b470  lea     rcx, SrvNetRdmaRundownProtector; RunRef
0x14005b477  call    cs:__imp_ExInitializeRundownProtection
0x14005b47e  nop     dword ptr [rax+rax+00h]
0x14005b483  lea     rcx, SrvNetRdmaRundownMutex; Mutex
0x14005b48a  mov     cs:SrvNetRdmaRundownSrwLock, rsi
0x14005b491  call    cs:__imp_KeInitializeGuardedMutex
0x14005b498  nop     dword ptr [rax+rax+00h]
0x14005b49d  lea     rdx, [rsp+78h+arg_18]
0x14005b4a5  lea     rcx, aSmbserverAllow; "SMBServer-AllowRdmaUsage"
0x14005b4ac  call    SrvLibQueryLicensingDWord
0x14005b4b1  test    eax, eax
0x14005b4b3  js      short loc_14005B4C1
0x14005b4b5  mov     al, bpl
0x14005b4b8  cmp     [rsp+78h+arg_18], esi
0x14005b4bf  jnz     short loc_14005B4C4
0x14005b4c1  mov     al, sil
0x14005b4c4  mov     cs:SrvNetIsSMBDirectSupported, al
0x14005b4ca  call    cs:__imp_TdiIsIPTransportSupported
0x14005b4d1  nop     dword ptr [rax+rax+00h]
0x14005b4d6  mov     cs:SrvNetUseTdiNotifications, al
0x14005b4dc  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005b4e3  cmp     rcx, r15
0x14005b4e6  jz      short loc_14005B503
0x14005b4e8  mov     edx, [rcx+2Ch]
0x14005b4eb  test    r14b, dl
0x14005b4ee  jz      short loc_14005B503
0x14005b4f0  cmp     byte ptr [rcx+29h], 2
0x14005b4f4  jb      short loc_14005B503
0x14005b4f6  mov     rcx, [rcx+18h]
0x14005b4fa  movzx   r9d, al
0x14005b4fe  call    WPP_SF_l
0x14005b503  test    byte ptr cs:WPP_MAIN_CB.Queue+12h, 8
0x14005b50a  jz      short loc_14005B523
0x14005b50c  movzx   r9d, cs:SrvNetUseTdiNotifications
0x14005b514  lea     rdx, SRVNET_EVENT_TDI_MODE_ENABLED
0x14005b51b  xor     r8d, r8d
0x14005b51e  call    McTemplateK0t_EtwWriteTransfer
0x14005b523  mov     ecx, 0FFFFh; GroupNumber
0x14005b528  call    cs:__imp_KeQueryActiveProcessorCountEx
0x14005b52f  nop     dword ptr [rax+rax+00h]
0x14005b534  mov     cs:SrvNetNumberOfActiveProcessorsAtServerStart, eax
0x14005b53a  call    SrvLibInitializeSecurityDescriptors
0x14005b53f  mov     edi, eax
0x14005b541  test    eax, eax
0x14005b543  jns     short loc_14005B578
0x14005b545  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005b54c  cmp     rcx, r15
0x14005b54f  jz      loc_14005BAF0
0x14005b555  mov     edx, [rcx+2Ch]
0x14005b558  test    r14b, dl
0x14005b55b  jz      loc_14005BAF0
0x14005b561  cmp     [rcx+29h], bpl
0x14005b565  jb      loc_14005BAF0
0x14005b56b  mov     edx, 0Ch
0x14005b570  mov     r9d, eax
0x14005b573  jmp     loc_14005BAE4
0x14005b578  or      cs:SrvNetInitProgress, bpl
0x14005b57f  lea     rdx, SrvNetAdminDeviceObject
0x14005b586  mov     rcx, rbx; DriverObject
0x14005b589  call    SrvAdminInitialize
0x14005b58e  mov     edi, eax
0x14005b590  test    eax, eax
0x14005b592  jns     short loc_14005B5C4
0x14005b594  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005b59b  cmp     rcx, r15
0x14005b59e  jz      loc_14005BAF0
0x14005b5a4  mov     eax, [rcx+2Ch]
0x14005b5a7  test    r14b, al
0x14005b5aa  jz      loc_14005BAF0
0x14005b5b0  cmp     [rcx+29h], bpl
0x14005b5b4  jb      loc_14005BAF0
0x14005b5ba  mov     edx, 0Dh
0x14005b5bf  jmp     loc_14005BAE1
0x14005b5c4  or      cs:SrvNetInitProgress, 2
0x14005b5cb  call    SmbCryptoInitialize
0x14005b5d0  mov     edi, eax
0x14005b5d2  test    eax, eax
0x14005b5d4  jns     short loc_14005B606
0x14005b5d6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005b5dd  cmp     rcx, r15
0x14005b5e0  jz      loc_14005BAF0
0x14005b5e6  mov     eax, [rcx+2Ch]
0x14005b5e9  test    r14b, al
0x14005b5ec  jz      loc_14005BAF0
0x14005b5f2  cmp     [rcx+29h], bpl
0x14005b5f6  jb      loc_14005BAF0
0x14005b5fc  mov     edx, 0Eh
0x14005b601  jmp     loc_14005BAE1
0x14005b606  or      cs:SrvNetInitProgress, r14b
0x14005b60d  lea     rdx, aDeviceSrvnet; "\\Device\\SrvNet"
0x14005b614  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x14005b619  call    cs:__imp_RtlInitUnicodeString
0x14005b620  nop     dword ptr [rax+rax+00h]
0x14005b625  lea     rax, SrvNetDeviceObject
0x14005b62c  mov     r9d, 14h; DeviceType
0x14005b632  mov     [rsp+78h+DeviceObject], rax; DeviceObject
0x14005b637  lea     r8, [rsp+78h+DestinationString]; DeviceName
0x14005b63c  mov     [rsp+78h+Exclusive], sil; Exclusive
0x14005b641  mov     edx, 478h; DeviceExtensionSize
0x14005b646  mov     rcx, rbx; DriverObject
0x14005b649  mov     [rsp+78h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x14005b651  call    cs:__imp_IoCreateDevice
0x14005b658  nop     dword ptr [rax+rax+00h]
0x14005b65d  mov     edi, eax
0x14005b65f  test    eax, eax
0x14005b661  jns     short loc_14005B693
0x14005b663  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005b66a  cmp     rcx, r15
0x14005b66d  jz      loc_14005BAF0
0x14005b673  mov     eax, [rcx+2Ch]
0x14005b676  test    r14b, al
0x14005b679  jz      loc_14005BAF0
0x14005b67f  cmp     [rcx+29h], bpl
0x14005b683  jb      loc_14005BAF0
0x14005b689  mov     edx, 0Fh
0x14005b68e  jmp     loc_14005BAE1
0x14005b693  mov     rcx, cs:SrvNetDeviceObject; int
0x14005b69a  mov     edx, 1F01FFh; int
0x14005b69f  or      cs:SrvNetInitProgress, 8
0x14005b6a6  mov     r9d, edx; int
0x14005b6a9  mov     dword ptr [rsp+78h+Exclusive], esi; ACCESS_MASK
0x14005b6ad  xor     r8d, r8d; int
0x14005b6b0  mov     [rsp+78h+DeviceCharacteristics], edx; ACCESS_MASK
0x14005b6b4  call    SrvLibApplyDeviceAcl
0x14005b6b9  mov     edi, eax
0x14005b6bb  test    eax, eax
0x14005b6bd  jns     short loc_14005B6EF
0x14005b6bf  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005b6c6  cmp     rcx, r15
0x14005b6c9  jz      loc_14005BAF0
0x14005b6cf  mov     eax, [rcx+2Ch]
0x14005b6d2  test    r14b, al
0x14005b6d5  jz      loc_14005BAF0
0x14005b6db  cmp     [rcx+29h], bpl
0x14005b6df  jb      loc_14005BAF0
0x14005b6e5  mov     edx, 10h
0x14005b6ea  jmp     loc_14005BAE1
0x14005b6ef  mov     rax, cs:SrvNetDeviceObject
0x14005b6f6  xor     edx, edx; Val
0x14005b6f8  mov     r8d, 478h; Size
0x14005b6fe  mov     rdi, [rax+40h]
0x14005b702  mov     rcx, rdi; void *
0x14005b705  mov     cs:SrvNetDeviceExtension, rdi
0x14005b70c  call    memset
0x14005b711  lea     rcx, [rdi+68h]; SpinLock
0x14005b715  call    cs:__imp_KeInitializeSpinLock
0x14005b71c  nop     dword ptr [rax+rax+00h]
0x14005b721  mov     rcx, cs:SrvNetDeviceExtension; Resource
0x14005b728  call    cs:__imp_ExInitializeResourceLite
0x14005b72f  nop     dword ptr [rax+rax+00h]
0x14005b734  mov     rcx, cs:SrvNetDeviceExtension
0x14005b73b  add     rcx, 120h; Resource
0x14005b742  call    cs:__imp_ExInitializeResourceLite
0x14005b749  nop     dword ptr [rax+rax+00h]
0x14005b74e  mov     rcx, cs:SrvNetDeviceExtension
0x14005b755  add     rcx, 78h ; 'x'; Resource
0x14005b759  call    cs:__imp_ExInitializeResourceLite
0x14005b760  nop     dword ptr [rax+rax+00h]
0x14005b765  mov     rcx, cs:SrvNetDeviceExtension
0x14005b76c  add     rcx, 210h; Resource
0x14005b773  call    cs:__imp_ExInitializeResourceLite
0x14005b77a  nop     dword ptr [rax+rax+00h]
0x14005b77f  mov     rcx, cs:SrvNetDeviceExtension
0x14005b786  add     rcx, 348h; Resource
0x14005b78d  call    cs:__imp_ExInitializeResourceLite
0x14005b794  nop     dword ptr [rax+rax+00h]
0x14005b799  mov     rcx, cs:SrvNetDeviceExtension
0x14005b7a0  add     rcx, 3B0h; Resource
0x14005b7a7  call    cs:__imp_ExInitializeResourceLite
0x14005b7ae  nop     dword ptr [rax+rax+00h]
0x14005b7b3  mov     rcx, cs:SrvNetDeviceExtension
0x14005b7ba  xor     r8d, r8d; State
0x14005b7bd  mov     edx, ebp; Type
0x14005b7bf  mov     [rcx+0E8h], ebp
0x14005b7c5  mov     [rcx+0F0h], rsi
0x14005b7cc  mov     [rcx+0F8h], esi
0x14005b7d2  add     rcx, 100h; Event
0x14005b7d9  call    cs:__imp_KeInitializeEvent
0x14005b7e0  nop     dword ptr [rax+rax+00h]
0x14005b7e5  mov     rcx, cs:SrvNetDeviceExtension
0x14005b7ec  lea     rax, [rcx+188h]
0x14005b7f3  mov     [rax+8], rax
0x14005b7f7  mov     [rax], rax
0x14005b7fa  lea     rax, [rcx+198h]
0x14005b801  mov     [rax+8], rax
0x14005b805  mov     [rax], rax
0x14005b808  lea     rax, [rcx+1A8h]
0x14005b80f  mov     [rax+8], rax
0x14005b813  mov     [rax], rax
0x14005b816  lea     rax, [rcx+418h]
0x14005b81d  add     rcx, 428h
0x14005b824  mov     [rax+8], rax
0x14005b828  mov     [rax], rax
0x14005b82b  call    SrvNetInitializeListenerRuleList
0x14005b830  mov     rdi, cs:SrvNetDeviceExtension
0x14005b837  mov     [rdi+70h], esi
0x14005b83a  call    cs:__imp_IoGetCurrentProcess
0x14005b841  nop     dword ptr [rax+rax+00h]
0x14005b846  mov     [rdi+1B8h], rax
0x14005b84d  or      cs:SrvNetInitProgress, 10h
0x14005b854  call    SrvNetLoadParameters
0x14005b859  mov     edi, eax
0x14005b85b  test    eax, eax
0x14005b85d  jns     short loc_14005B88F
0x14005b85f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005b866  cmp     rcx, r15
0x14005b869  jz      loc_14005BAF0
0x14005b86f  mov     eax, [rcx+2Ch]
0x14005b872  test    r14b, al
0x14005b875  jz      loc_14005BAF0
0x14005b87b  cmp     [rcx+29h], bpl
0x14005b87f  jb      loc_14005BAF0
0x14005b885  mov     edx, 11h
0x14005b88a  jmp     loc_14005BAE1
0x14005b88f  call    SrvNetWskProviderInitialize
0x14005b894  mov     edi, eax
0x14005b896  test    eax, eax
0x14005b898  jns     short loc_14005B8CA
0x14005b89a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005b8a1  cmp     rcx, r15
0x14005b8a4  jz      loc_14005BAF0
0x14005b8aa  mov     eax, [rcx+2Ch]
0x14005b8ad  test    r14b, al
0x14005b8b0  jz      loc_14005BAF0
0x14005b8b6  cmp     [rcx+29h], bpl
0x14005b8ba  jb      loc_14005BAF0
0x14005b8c0  mov     edx, 12h
0x14005b8c5  jmp     loc_14005BAE1
0x14005b8ca  or      cs:SrvNetInitProgress, 0E0h
0x14005b8d1  lea     rax, WPP_MAIN_CB.Queue
0x14005b8d8  lea     rcx, SrvNetConnectionClosingListLock; SpinLock
0x14005b8df  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, rax
0x14005b8e6  mov     qword ptr cs:WPP_MAIN_CB.Queue, rax
0x14005b8ed  call    cs:__imp_KeInitializeSpinLock
0x14005b8f4  nop     dword ptr [rax+rax+00h]
0x14005b8f9  lea     rax, WPP_MAIN_CB.DeviceExtension
0x14005b900  lea     rcx, WPP_MAIN_CB.Queue+18h; SpinLock
0x14005b907  mov     qword ptr cs:WPP_MAIN_CB.DeviceType, rax
0x14005b90e  mov     cs:WPP_MAIN_CB.DeviceExtension, rax
0x14005b915  call    cs:__imp_KeInitializeSpinLock
0x14005b91c  nop     dword ptr [rax+rax+00h]
0x14005b921  call    SrvXsInitialize
0x14005b926  call    SrvGrovelerInitialize
0x14005b92b  or      cs:byte_140036679, bpl
0x14005b932  call    SrvIdSegInitialize
0x14005b937  mov     edi, eax
0x14005b939  test    eax, eax
0x14005b93b  jns     short loc_14005B96D
0x14005b93d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005b944  cmp     rcx, r15
0x14005b947  jz      loc_14005BAF0
0x14005b94d  mov     eax, [rcx+2Ch]
0x14005b950  test    r14b, al
0x14005b953  jz      loc_14005BAF0
0x14005b959  cmp     [rcx+29h], bpl
0x14005b95d  jb      loc_14005BAF0
0x14005b963  mov     edx, 15h
0x14005b968  jmp     loc_14005BAE1
0x14005b96d  or      cs:byte_140036679, 2
  ... truncated ...
```
