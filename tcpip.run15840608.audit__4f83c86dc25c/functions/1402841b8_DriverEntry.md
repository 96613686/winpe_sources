# DriverEntry

- ea: `0x1402841b8`
- end: `0x14028470e`
- name: `DriverEntry`
- size: `1366`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `36`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140284150`

## callees

- `0x140153660`
- `0x140157918`
- `0x140157c88`
- `0x140157ec4`
- `0x1401580a4`
- `0x1401582b4`
- `0x1401583f0`
- `0x1401584bc`
- `0x140159d08`
- `0x140159f50`
- `0x1401b7a6c`
- `0x1401b8074`
- `0x1401b8268`
- `0x1401be118`
- `0x1401c0fd0`
- `0x1401c1580`
- `0x140252594`
- `0x140252640`
- `0x140252674`
- `0x1402526f8`
- `0x14025278c`
- `0x140252b7c`
- `0x140252d58`
- `0x140252dac`
- `0x140252eb4`
- `0x140252ff4`
- `0x140259be0`
- `0x14025a008`
- `0x14025be2c`
- `0x14025bf60`
- `0x1402841b8`
- `0x140284714`
- `0x1402848bc`
- `0x140284b70`
- `0x14028539c`
- `0x140285c14`

## import_xrefs

- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14028438a`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14028438a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140284352`
- `ntoskrnl!KeWaitForSingleObject` at `0x14028451d`
- `ntoskrnl!KeWaitForSingleObject` at `0x140284352`
- `ntoskrnl!KeWaitForSingleObject` at `0x14028451d`
- `ntoskrnl!KeInitializeEvent` at `0x140284490`
- `ntoskrnl!KeInitializeEvent` at `0x140284490`
- `ntoskrnl!IofCallDriver` at `0x1402844f6`
- `ntoskrnl!IofCallDriver` at `0x1402844f6`
- `ntoskrnl!IoCreateDevice` at `0x140284328`
- `ntoskrnl!IoCreateDevice` at `0x140284328`
- `ntoskrnl!PsGetCurrentProcess` at `0x140284202`
- `ntoskrnl!PsGetCurrentProcess` at `0x140284202`
- `ntoskrnl!RtlGetVersion` at `0x14028428c`
- `ntoskrnl!RtlGetVersion` at `0x14028428c`
- `ntoskrnl!KeReleaseMutex` at `0x140284638`
- `ntoskrnl!KeReleaseMutex` at `0x1402846fb`
- `ntoskrnl!KeReleaseMutex` at `0x140284638`
- `ntoskrnl!KeReleaseMutex` at `0x1402846fb`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140284459`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140284459`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1402844db`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1402844db`
- `ntoskrnl!IoDeleteDevice` at `0x14028464b`
- `ntoskrnl!IoDeleteDevice` at `0x14028464b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140284435`
- `ntoskrnl!RtlInitUnicodeString` at `0x140284435`
- `ntoskrnl!ObfDereferenceObject` at `0x14028455a`
- `ntoskrnl!ObfDereferenceObject` at `0x14028455a`
- `ntoskrnl!KeInitializeMutex` at `0x140284225`
- `ntoskrnl!KeInitializeMutex` at `0x140284225`
- `NETIO!NetioUnInitializeNetBufferListLibrary` at `0x140284610`
- `NETIO!NetioUnInitializeNetBufferListLibrary` at `0x140284610`
- `NETIO!NetioSetTriageBlock` at `0x14028425c`
- `NETIO!NetioSetTriageBlock` at `0x14028425c`
- `NETIO!NetioRegisterTriageDumpDataCallback` at `0x1402846e6`
- `NETIO!NetioRegisterTriageDumpDataCallback` at `0x1402846e6`
- `NETIO!NetioRegisterProcessorAddCallback` at `0x14028436f`
- `NETIO!NetioRegisterProcessorAddCallback` at `0x14028436f`
- `NETIO!NetioUnRegisterProcessorAddCallback` at `0x140284623`
- `NETIO!NetioUnRegisterProcessorAddCallback` at `0x140284623`
- `NETIO!NetioInitializeNetBufferListLibrary` at `0x14028439c`
- `NETIO!NetioInitializeNetBufferListLibrary` at `0x14028439c`
- `NETIO!RtlInvokeStartRoutines` at `0x140284404`
- `NETIO!RtlInvokeStartRoutines` at `0x140284404`
- `NETIO!RtlInvokeStopRoutines` at `0x1402845ff`
- `NETIO!RtlInvokeStopRoutines` at `0x1402845ff`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  int started; // ebx
  __int64 v6; // r8
  __int64 v7; // r9
  struct _LIST_ENTRY *CurrentProcess; // rax
  int v9; // eax
  NTSTATUS DeviceObjectPointer; // ebx
  IRP *v11; // rax
  struct _KEVENT Event; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-88h] BYREF
  _BYTE VersionInformation[284]; // [rsp+90h] [rbp-70h] BYREF

  memset(VersionInformation, 0, sizeof(VersionInformation));
  started = wil_InitializeFeatureStaging();
  if ( started < 0 )
    goto LABEL_43;
  CurrentProcess = (struct _LIST_ENTRY *)PsGetCurrentProcess(v4, v3, v6, v7);
  *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters = DriverObject;
  WPP_MAIN_CB.Queue.ListEntry.Flink = CurrentProcess;
  KeInitializeMutex(&Mutex, 0);
  LOBYTE(WPP_MAIN_CB.DeviceType) = IsSystemRunningAsVailGuest();
  *(_DWORD *)&WPP_MAIN_CB.StackSize = GetProductType();
  LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceObject) = GetPortTrackerMode();
  NetioSetTriageBlock(1, &TcpipGlobalTriageBlock);
  InitializeTelemetryAssertsKMByDriverObject(DriverObject);
  memset(&VersionInformation[4], 0, 0x118u);
  *(_DWORD *)VersionInformation = 284;
  if ( RtlGetVersion((PRTL_OSVERSIONINFOW)VersionInformation) >= 0 && VersionInformation[282] != 1 )
    TcpipIsServerSKU = 1;
  started = TcpipStartTrace();
  if ( started < 0 )
    goto LABEL_43;
  TlgRegisterAggregateProvider(&dword_1402241F8);
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_140224230);
  started = PktMonClientInitialize();
  if ( started < 0 )
  {
LABEL_42:
    TraceLoggingUnregister_EtwUnregister(&dword_140224230);
    TlgUnregisterAggregateProvider(&dword_1402241F8);
    TcpipStopTrace();
LABEL_43:
    wil_UninitializeFeatureStaging();
    return started;
  }
  started = TcpipPcwStartup();
  if ( started < 0 )
  {
LABEL_41:
    PktMonClientUninitialize();
    goto LABEL_42;
  }
  started = InitializeMemoryUsageTracking();
  if ( started < 0
    || (started = IoCreateDevice(DriverObject, 0, 0, 0x12u, 0, 0, (PDEVICE_OBJECT *)&TcpipDeviceObject), started < 0) )
  {
LABEL_40:
    TcpipPcwCleanup();
    goto LABEL_41;
  }
  KeWaitForSingleObject(&Mutex, Executive, 0, 0, 0);
  started = NetioRegisterProcessorAddCallback(qword_1402284D8, TcpipProcessorAddCallback, 0);
  if ( started < 0 )
  {
LABEL_39:
    KeReleaseMutex(&Mutex, 0);
    IoDeleteDevice((PDEVICE_OBJECT)TcpipDeviceObject);
    goto LABEL_40;
  }
  dword_1402284F0 = KeQueryActiveProcessorCountEx(0xFFFFu);
  started = NetioInitializeNetBufferListLibrary();
  if ( started < 0 )
  {
LABEL_38:
    NetioUnRegisterProcessorAddCallback(qword_1402284D8);
    goto LABEL_39;
  }
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_NETIO;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  v9 = RtlInvokeStartRoutines(&RssStartStopRoutines, 4, &RssStartedModules);
  RssPagesLocked = 0;
  started = v9;
  if ( v9 < 0 )
  {
LABEL_37:
    WppCleanupKm();
    NetioUnInitializeNetBufferListLibrary();
    goto LABEL_38;
  }
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\TcpAllocHooks");
  DeviceObjectPointer = IoGetDeviceObjectPointer(
                          &DestinationString,
                          0xC0100000,
                          (PFILE_OBJECT *)&WPP_MAIN_CB.Queue.Wcb.DeviceContext,
                          (PDEVICE_OBJECT *)&WPP_MAIN_CB.DeviceExtension);
  if ( DeviceObjectPointer >= 0 )
  {
    IoStatusBlock = 0;
    memset(&Event, 0, sizeof(Event));
    KeInitializeEvent(&Event, NotificationEvent, 0);
    v11 = IoBuildDeviceIoControlRequest(
            0x120000u,
            (PDEVICE_OBJECT)WPP_MAIN_CB.DeviceExtension,
            0,
            0,
            &WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Blink,
            8u,
            0,
            &Event,
            &IoStatusBlock);
    if ( !v11 )
    {
      DeviceObjectPointer = -1073741670;
LABEL_24:
      ObfDereferenceObject(WPP_MAIN_CB.Queue.Wcb.DeviceContext);
      WPP_MAIN_CB.Queue.Wcb.DeviceContext = 0;
      WPP_MAIN_CB.DeviceExtension = 0;
      goto LABEL_25;
    }
    DeviceObjectPointer = IofCallDriver((PDEVICE_OBJECT)WPP_MAIN_CB.DeviceExtension, v11);
    if ( DeviceObjectPointer == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      DeviceObjectPointer = IoStatusBlock.Status;
    }
    if ( DeviceObjectPointer < 0 )
    {
      WPP_MAIN_CB.Queue.ListEntry.Blink = 0;
    }
    else if ( !WPP_MAIN_CB.Queue.ListEntry.Blink )
    {
      DeviceObjectPointer = -1073741822;
    }
    if ( DeviceObjectPointer < 0 )
      goto LABEL_24;
  }
LABEL_25:
  if ( (BYTE5(WPP_MAIN_CB.Dpc.DeferredContext) & 4) != 0 )
    McTemplateK0d_EtwWriteTransfer(
      &MICROSOFT_TCPIP_PROVIDER_Context,
      TCPIP_ALLOC_HOOKS_SETUP,
      MICROSOFT_TCPIP_PROVIDER,
      (unsigned int)DeviceObjectPointer);
  started = TlStartup();
  if ( started < 0 )
    goto LABEL_36;
  started = NlStartup(DriverObject);
  if ( started < 0 )
  {
LABEL_35:
    TlCleanup();
LABEL_36:
    RtlInvokeStopRoutines(&RssStartStopRoutines, 4, &RssStartedModules);
    goto LABEL_37;
  }
  started = FlStartup();
  if ( started < 0 )
  {
LABEL_34:
    NlCleanup();
    goto LABEL_35;
  }
  started = TcpipPowerStartup();
  if ( started < 0 )
  {
LABEL_33:
    FlCleanup();
    goto LABEL_34;
  }
  started = TcpipConfigStartup();
  if ( started < 0 )
  {
    TcpipPowerCleanup();
    goto LABEL_33;
  }
  if ( (unsigned __int8)IsSystemRunningAsVailGuest() )
  {
    if ( (unsigned __int8)IsWcosLoopbackSupported() )
      IpsLbStartup();
  }
  TcpipInitializeHealthTelemetry(DriverObject);
  NetioRegisterTriageDumpDataCallback(qword_140228450, 3, TcpipPopulateTriageDumpData, &TcpipGlobalTriageBlock, "TCPIP");
  KeReleaseMutex(&Mutex, 0);
  return 0;
}

```

## disassembly

```asm
0x1402841b8  push    rbp
0x1402841ba  push    rbx
0x1402841bb  push    rsi
0x1402841bc  push    rdi
0x1402841bd  lea     rbp, [rsp-0C8h]
0x1402841c5  sub     rsp, 1C8h
0x1402841cc  mov     rax, cs:__security_cookie
0x1402841d3  xor     rax, rsp
0x1402841d6  mov     [rbp+0E0h+var_30], rax
0x1402841dd  mov     rdi, rcx
0x1402841e0  xor     edx, edx; Val
0x1402841e2  lea     rcx, [rbp+0E0h+VersionInformation]; void *
0x1402841e6  mov     r8d, 11Ch; Size
0x1402841ec  call    memset
0x1402841f1  call    wil_InitializeFeatureStaging
0x1402841f6  xor     esi, esi
0x1402841f8  mov     ebx, eax
0x1402841fa  test    eax, eax
0x1402841fc  js      loc_14028467E
0x140284202  call    cs:__imp_PsGetCurrentProcess
0x140284209  nop     dword ptr [rax+rax+00h]
0x14028420e  xor     edx, edx; Level
0x140284210  mov     qword ptr cs:WPP_MAIN_CB.Queue+28h, rdi
0x140284217  lea     rcx, Mutex; Mutex
0x14028421e  mov     qword ptr cs:WPP_MAIN_CB.Queue, rax
0x140284225  call    cs:__imp_KeInitializeMutex
0x14028422c  nop     dword ptr [rax+rax+00h]
0x140284231  call    IsSystemRunningAsVailGuest
0x140284236  mov     byte ptr cs:WPP_MAIN_CB.DeviceType, al
0x14028423c  call    GetProductType
0x140284241  mov     dword ptr cs:WPP_MAIN_CB.StackSize, eax
0x140284247  call    GetPortTrackerMode
0x14028424c  lea     rdx, TcpipGlobalTriageBlock
0x140284253  mov     dword ptr cs:WPP_MAIN_CB.Queue+30h, eax
0x140284259  lea     ecx, [rsi+1]
0x14028425c  call    cs:__imp_NetioSetTriageBlock
0x140284263  nop     dword ptr [rax+rax+00h]
0x140284268  mov     rcx, rdi
0x14028426b  call    InitializeTelemetryAssertsKMByDriverObject
0x140284270  xor     edx, edx; Val
0x140284272  lea     rcx, [rbp+0E0h+VersionInformation.dwMajorVersion]; void *
0x140284276  mov     r8d, 118h; Size
0x14028427c  call    memset
0x140284281  lea     rcx, [rbp+0E0h+VersionInformation]; lpVersionInformation
0x140284285  mov     [rbp+0E0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x14028428c  call    cs:__imp_RtlGetVersion
0x140284293  nop     dword ptr [rax+rax+00h]
0x140284298  test    eax, eax
0x14028429a  js      short loc_1402842AC
0x14028429c  cmp     [rbp+0E0h+var_36], 1
0x1402842a3  jz      short loc_1402842AC
0x1402842a5  mov     cs:TcpipIsServerSKU, 1
0x1402842ac  call    TcpipStartTrace
0x1402842b1  mov     ebx, eax
0x1402842b3  test    eax, eax
0x1402842b5  js      loc_14028467E
0x1402842bb  lea     rcx, dword_1402241F8
0x1402842c2  call    TlgRegisterAggregateProvider
0x1402842c7  xor     r8d, r8d
0x1402842ca  lea     rcx, dword_140224230; CallbackContext
0x1402842d1  xor     edx, edx
0x1402842d3  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x1402842d8  call    PktMonClientInitialize
0x1402842dd  mov     ebx, eax
0x1402842df  test    eax, eax
0x1402842e1  js      loc_140284661
0x1402842e7  call    TcpipPcwStartup
0x1402842ec  mov     ebx, eax
0x1402842ee  test    eax, eax
0x1402842f0  js      loc_14028465C
0x1402842f6  call    InitializeMemoryUsageTracking
0x1402842fb  mov     ebx, eax
0x1402842fd  test    eax, eax
0x1402842ff  js      loc_140284657
0x140284305  lea     rax, TcpipDeviceObject
0x14028430c  mov     r9d, 12h; DeviceType
0x140284312  mov     [rsp+1E0h+DeviceObject], rax; DeviceObject
0x140284317  xor     r8d, r8d; DeviceName
0x14028431a  mov     [rsp+1E0h+Exclusive], sil; Exclusive
0x14028431f  xor     edx, edx; DeviceExtensionSize
0x140284321  mov     rcx, rdi; DriverObject
0x140284324  mov     [rsp+1E0h+DeviceCharacteristics], esi; DeviceCharacteristics
0x140284328  call    cs:__imp_IoCreateDevice
0x14028432f  nop     dword ptr [rax+rax+00h]
0x140284334  mov     ebx, eax
0x140284336  test    eax, eax
0x140284338  js      loc_140284657
0x14028433e  xor     r9d, r9d; Alertable
0x140284341  mov     qword ptr [rsp+1E0h+DeviceCharacteristics], rsi; Timeout
0x140284346  xor     r8d, r8d; WaitMode
0x140284349  lea     rcx, Mutex; Object
0x140284350  xor     edx, edx; WaitReason
0x140284352  call    cs:__imp_KeWaitForSingleObject
0x140284359  nop     dword ptr [rax+rax+00h]
0x14028435e  xor     r8d, r8d
0x140284361  lea     rdx, TcpipProcessorAddCallback
0x140284368  lea     rcx, qword_1402284D8
0x14028436f  call    cs:__imp_NetioRegisterProcessorAddCallback
0x140284376  nop     dword ptr [rax+rax+00h]
0x14028437b  mov     ebx, eax
0x14028437d  test    eax, eax
0x14028437f  js      loc_14028462F
0x140284385  mov     ecx, 0FFFFh; GroupNumber
0x14028438a  call    cs:__imp_KeQueryActiveProcessorCountEx
0x140284391  nop     dword ptr [rax+rax+00h]
0x140284396  mov     cs:dword_1402284F0, eax
0x14028439c  call    cs:__imp_NetioInitializeNetBufferListLibrary
0x1402843a3  nop     dword ptr [rax+rax+00h]
0x1402843a8  mov     ebx, eax
0x1402843aa  test    eax, eax
0x1402843ac  js      loc_14028461C
0x1402843b2  lea     rax, WPP_ThisDir_CTLGUID_NETIO
0x1402843b9  mov     qword ptr cs:WPP_MAIN_CB.Type, rsi
0x1402843c0  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x1402843c7  mov     cs:WPP_MAIN_CB.NextDevice, rsi
0x1402843ce  mov     cs:WPP_MAIN_CB.CurrentIrp, rsi
0x1402843d5  mov     cs:WPP_MAIN_CB.Timer, 1
0x1402843e0  call    WppLoadTracingSupport
0x1402843e5  mov     cs:WPP_MAIN_CB.CurrentIrp, rsi
0x1402843ec  call    WppInitKm
0x1402843f1  lea     r8, RssStartedModules
0x1402843f8  mov     edx, 4
0x1402843fd  lea     rcx, RssStartStopRoutines
0x140284404  call    cs:__imp_RtlInvokeStartRoutines
0x14028440b  nop     dword ptr [rax+rax+00h]
0x140284410  mov     cs:RssPagesLocked, sil
0x140284417  mov     ebx, eax
0x140284419  test    eax, eax
0x14028441b  js      loc_14028460B
0x140284421  xorps   xmm0, xmm0
0x140284424  lea     rdx, aDeviceTcpalloc; "\\Device\\TcpAllocHooks"
0x14028442b  lea     rcx, [rsp+1E0h+DestinationString]; DestinationString
0x140284430  movups  xmmword ptr [rsp+1E0h+DestinationString.Length], xmm0
0x140284435  call    cs:__imp_RtlInitUnicodeString
0x14028443c  nop     dword ptr [rax+rax+00h]
0x140284441  lea     r9, WPP_MAIN_CB.DeviceExtension; DeviceObject
0x140284448  mov     edx, 0C0100000h; DesiredAccess
0x14028444d  lea     r8, WPP_MAIN_CB.Queue+20h; FileObject
0x140284454  lea     rcx, [rsp+1E0h+DestinationString]; ObjectName
0x140284459  call    cs:__imp_IoGetDeviceObjectPointer
0x140284460  nop     dword ptr [rax+rax+00h]
0x140284465  mov     ebx, eax
0x140284467  test    eax, eax
0x140284469  js      loc_140284574
0x14028446f  xorps   xmm0, xmm0
0x140284472  lea     rcx, [rsp+1E0h+Event]; Event
0x140284477  xorps   xmm1, xmm1
0x14028447a  xor     eax, eax
0x14028447c  xor     r8d, r8d; State
0x14028447f  mov     [rsp+1E0h+Event.Header.WaitListHead.Blink], rax
0x140284484  xor     edx, edx; Type
0x140284486  movups  xmmword ptr [rsp+1E0h+var_168], xmm0
0x14028448b  movups  xmmword ptr [rsp+1E0h+Event.Header], xmm1
0x140284490  call    cs:__imp_KeInitializeEvent
0x140284497  nop     dword ptr [rax+rax+00h]
0x14028449c  mov     rdx, cs:WPP_MAIN_CB.DeviceExtension; DeviceObject
0x1402844a3  lea     rax, [rsp+1E0h+var_168]
0x1402844a8  mov     [rsp+1E0h+IoStatusBlock], rax; IoStatusBlock
0x1402844ad  xor     r9d, r9d; InputBufferLength
0x1402844b0  lea     rax, [rsp+1E0h+Event]
0x1402844b5  xor     r8d, r8d; InputBuffer
0x1402844b8  mov     [rsp+1E0h+var_1A8], rax; Event
0x1402844bd  mov     ecx, 120000h; IoControlCode
0x1402844c2  mov     byte ptr [rsp+1E0h+DeviceObject], sil; InternalDeviceIoControl
0x1402844c7  lea     rax, WPP_MAIN_CB.Queue+8
0x1402844ce  mov     dword ptr [rsp+1E0h+Exclusive], 8; OutputBufferLength
0x1402844d6  mov     qword ptr [rsp+1E0h+DeviceCharacteristics], rax; OutputBuffer
0x1402844db  call    cs:__imp_IoBuildDeviceIoControlRequest
0x1402844e2  nop     dword ptr [rax+rax+00h]
0x1402844e7  test    rax, rax
0x1402844ea  jz      short loc_14028454E
0x1402844ec  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension; DeviceObject
0x1402844f3  mov     rdx, rax; Irp
0x1402844f6  call    cs:__imp_IofCallDriver
0x1402844fd  nop     dword ptr [rax+rax+00h]
0x140284502  mov     ebx, eax
0x140284504  cmp     eax, 103h
0x140284509  jnz     short loc_14028452D
0x14028450b  xor     r9d, r9d; Alertable
0x14028450e  mov     qword ptr [rsp+1E0h+DeviceCharacteristics], rsi; Timeout
0x140284513  xor     r8d, r8d; WaitMode
0x140284516  lea     rcx, [rsp+1E0h+Event]; Object
0x14028451b  xor     edx, edx; WaitReason
0x14028451d  call    cs:__imp_KeWaitForSingleObject
0x140284524  nop     dword ptr [rax+rax+00h]
0x140284529  mov     ebx, dword ptr [rsp+1E0h+var_168]
0x14028452d  test    ebx, ebx
0x14028452f  js      short loc_140284541
0x140284531  cmp     qword ptr cs:WPP_MAIN_CB.Queue+8, rsi
0x140284538  jnz     short loc_140284548
0x14028453a  mov     ebx, 0C0000002h
0x14028453f  jmp     short loc_140284548
0x140284541  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, rsi
0x140284548  test    ebx, ebx
0x14028454a  jns     short loc_140284574
0x14028454c  jmp     short loc_140284553
0x14028454e  mov     ebx, 0C000009Ah
0x140284553  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+20h; Object
0x14028455a  call    cs:__imp_ObfDereferenceObject
0x140284561  nop     dword ptr [rax+rax+00h]
0x140284566  mov     qword ptr cs:WPP_MAIN_CB.Queue+20h, rsi
0x14028456d  mov     cs:WPP_MAIN_CB.DeviceExtension, rsi
0x140284574  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredContext+5, 4
0x14028457b  jz      short loc_14028459A
0x14028457d  mov     r9d, ebx
0x140284580  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x140284587  lea     rdx, TCPIP_ALLOC_HOOKS_SETUP
0x14028458e  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140284595  call    McTemplateK0d_EtwWriteTransfer
0x14028459a  call    TlStartup
0x14028459f  mov     ebx, eax
0x1402845a1  test    eax, eax
0x1402845a3  js      short loc_1402845EC
0x1402845a5  mov     rcx, rdi; DriverObject
0x1402845a8  call    NlStartup
0x1402845ad  mov     ebx, eax
0x1402845af  test    eax, eax
0x1402845b1  js      short loc_1402845E7
0x1402845b3  call    FlStartup
0x1402845b8  mov     ebx, eax
0x1402845ba  test    eax, eax
0x1402845bc  js      short loc_1402845E2
0x1402845be  call    TcpipPowerStartup
0x1402845c3  mov     ebx, eax
0x1402845c5  test    eax, eax
0x1402845c7  js      short loc_1402845DD
0x1402845c9  call    TcpipConfigStartup
0x1402845ce  mov     ebx, eax
0x1402845d0  test    eax, eax
0x1402845d2  jns     loc_1402846A1
0x1402845d8  call    TcpipPowerCleanup
0x1402845dd  call    FlCleanup
0x1402845e2  call    NlCleanup
0x1402845e7  call    TlCleanup
0x1402845ec  lea     r8, RssStartedModules
0x1402845f3  mov     edx, 4
0x1402845f8  lea     rcx, RssStartStopRoutines
0x1402845ff  call    cs:__imp_RtlInvokeStopRoutines
0x140284606  nop     dword ptr [rax+rax+00h]
0x14028460b  call    WppCleanupKm
0x140284610  call    cs:__imp_NetioUnInitializeNetBufferListLibrary
0x140284617  nop     dword ptr [rax+rax+00h]
0x14028461c  lea     rcx, qword_1402284D8
0x140284623  call    cs:__imp_NetioUnRegisterProcessorAddCallback
0x14028462a  nop     dword ptr [rax+rax+00h]
0x14028462f  xor     edx, edx; Wait
0x140284631  lea     rcx, Mutex; Mutex
0x140284638  call    cs:__imp_KeReleaseMutex
0x14028463f  nop     dword ptr [rax+rax+00h]
0x140284644  mov     rcx, cs:TcpipDeviceObject; DeviceObject
0x14028464b  call    cs:__imp_IoDeleteDevice
0x140284652  nop     dword ptr [rax+rax+00h]
0x140284657  call    TcpipPcwCleanup
0x14028465c  call    PktMonClientUninitialize
0x140284661  lea     rcx, dword_140224230
0x140284668  call    TraceLoggingUnregister_EtwUnregister
0x14028466d  lea     rcx, dword_1402241F8
0x140284674  call    TlgUnregisterAggregateProvider
0x140284679  call    TcpipStopTrace
0x14028467e  call    wil_UninitializeFeatureStaging
0x140284683  mov     eax, ebx
0x140284685  mov     rcx, [rbp+0E0h+var_30]
0x14028468c  xor     rcx, rsp; StackCookie
0x14028468f  call    __security_check_cookie
0x140284694  add     rsp, 1C8h
0x14028469b  pop     rdi
0x14028469c  pop     rsi
0x14028469d  pop     rbx
0x14028469e  pop     rbp
0x14028469f  retn
0x1402846a1  call    IsSystemRunningAsVailGuest
0x1402846a6  test    al, al
0x1402846a8  jz      short loc_1402846B8
0x1402846aa  call    IsWcosLoopbackSupported
0x1402846af  test    al, al
0x1402846b1  jz      short loc_1402846B8
0x1402846b3  call    IpsLbStartup
0x1402846b8  mov     rcx, rdi
0x1402846bb  call    TcpipInitializeHealthTelemetry
0x1402846c0  lea     rax, aTcpip_0; "TCPIP"
0x1402846c7  mov     edx, 3
0x1402846cc  lea     r9, TcpipGlobalTriageBlock
0x1402846d3  mov     qword ptr [rsp+1E0h+DeviceCharacteristics], rax
0x1402846d8  lea     r8, TcpipPopulateTriageDumpData
0x1402846df  lea     rcx, qword_140228450
0x1402846e6  call    cs:__imp_NetioRegisterTriageDumpDataCallback
0x1402846ed  nop     dword ptr [rax+rax+00h]
0x1402846f2  xor     edx, edx; Wait
0x1402846f4  lea     rcx, Mutex; Mutex
0x1402846fb  call    cs:__imp_KeReleaseMutex
0x140284702  nop     dword ptr [rax+rax+00h]
0x140284707  xor     eax, eax
0x140284709  jmp     loc_140284685
```
