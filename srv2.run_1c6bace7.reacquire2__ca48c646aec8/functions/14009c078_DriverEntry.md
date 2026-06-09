# DriverEntry

- ea: `0x14009c078`
- end: `0x14009c437`
- name: `DriverEntry`
- size: `959`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x14009c010`

## callees

- `0x14002019c`
- `0x1400224b8`
- `0x140023584`
- `0x1400235c4`
- `0x14005d6ec`
- `0x14005da48`
- `0x14005f8a4`
- `0x14005f928`
- `0x14005f9bc`
- `0x14005fdac`
- `0x140072a44`
- `0x140072b84`
- `0x14009c078`
- `0x14009c440`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14009c179`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009c326`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009c179`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009c326`
- `ntoskrnl!ExDeleteResourceLite` at `0x14009c3df`
- `ntoskrnl!ExDeleteResourceLite` at `0x14009c3df`
- `ntoskrnl!ExInitializeResourceLite` at `0x14009c30f`
- `ntoskrnl!ExInitializeResourceLite` at `0x14009c30f`
- `ntoskrnl!IoGetCurrentProcess` at `0x14009c29c`
- `ntoskrnl!IoGetCurrentProcess` at `0x14009c29c`
- `ntoskrnl!IoCreateDevice` at `0x14009c1d2`
- `ntoskrnl!IoCreateDevice` at `0x14009c1d2`
- `ntoskrnl!IoCreateNotificationEvent` at `0x14009c33a`
- `ntoskrnl!IoCreateNotificationEvent` at `0x14009c33a`
- `ntoskrnl!ObfReferenceObject` at `0x14009c35c`
- `ntoskrnl!ObfReferenceObject` at `0x14009c35c`
- `ntoskrnl!ZwClose` at `0x14009c36c`
- `ntoskrnl!ZwClose` at `0x14009c36c`
- `ntoskrnl!ObfDereferenceObject` at `0x14009c3c5`
- `ntoskrnl!ObfDereferenceObject` at `0x14009c3c5`
- `ntoskrnl!IoDeleteDevice` at `0x14009c3f2`
- `ntoskrnl!IoDeleteDevice` at `0x14009c3f2`
- `ntoskrnl!KeInitializeSpinLock` at `0x14009c18c`
- `ntoskrnl!KeInitializeSpinLock` at `0x14009c18c`
- `srvnet!SrvLibApplySrvDeviceAcl` at `0x14009c241`
- `srvnet!SrvLibApplySrvDeviceAcl` at `0x14009c241`
- `srvnet!SrvNetIsDriverLoaded` at `0x14009c12a`
- `srvnet!SrvNetIsDriverLoaded` at `0x14009c12a`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS v3; // edi
  NTSTATUS v4; // eax
  struct _KPROCESS *CurrentProcess; // rax
  PKEVENT v6; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING EventName; // [rsp+50h] [rbp-10h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+A0h] [rbp+40h] BYREF
  void *EventHandle; // [rsp+A8h] [rbp+48h] BYREF

  DeviceObject = 0;
  DestinationString = 0;
  EventHandle = 0;
  EventName = 0;
  McGenEventRegister_EtwRegister(DriverObject, RegistryPath);
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_Srv2Log;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  TlgRegisterAggregateProvider();
  wil_InitializeFeatureStaging();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_5bb5acbc86b838dd4009309de35c075e_Traceguids);
  }
  if ( !(unsigned __int8)SrvNetIsDriverLoaded() )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_5bb5acbc86b838dd4009309de35c075e_Traceguids);
    }
    v3 = -1073741204;
    goto LABEL_32;
  }
  RtlInitUnicodeString(&DestinationString, L"\\Device\\Srv2");
  KeInitializeSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.SystemArgument2);
  *(_QWORD *)&WPP_MAIN_CB.ActiveThreadCount = &WPP_MAIN_CB.Dpc.DpcData;
  WPP_MAIN_CB.Dpc.DpcData = &WPP_MAIN_CB.Dpc.DpcData;
  v4 = IoCreateDevice(DriverObject, 0, &DestinationString, 0x14u, 0x100u, 0, &DeviceObject);
  v3 = v4;
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        23,
        WPP_5bb5acbc86b838dd4009309de35c075e_Traceguids,
        (unsigned int)v4);
    }
    goto LABEL_32;
  }
  v3 = SrvLibApplySrvDeviceAcl(DeviceObject, 2032127, 1179808, 1180063, 2032127, 1179808);
  if ( v3 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        24,
        WPP_5bb5acbc86b838dd4009309de35c075e_Traceguids,
        (unsigned int)v3);
    }
LABEL_31:
    IoDeleteDevice((PDEVICE_OBJECT)Srv2DeviceObject);
    Srv2DeviceObject = 0;
    Srv2ServerProcess = 0;
LABEL_32:
    wil_UninitializeFeatureStaging();
    TlgUnregisterAggregateProvider();
    WppCleanupKm();
    McGenEventUnregister_EtwUnregister();
    return v3;
  }
  Srv2DeviceObject = DeviceObject;
  CurrentProcess = IoGetCurrentProcess();
  Srv2DriverState = 0;
  Srv2ServerProcess = CurrentProcess;
  memset64(DriverObject->MajorFunction, (unsigned __int64)&Srv2DefaultDispatch, 0x1Cu);
  DriverObject->MajorFunction[18] = (PDRIVER_DISPATCH)&Srv2Cleanup;
  DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&Srv2Close;
  DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)&Srv2Create;
  DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)&Srv2DeviceControl;
  DriverObject->DriverUnload = (PDRIVER_UNLOAD)DriverUnload;
  ExInitializeResourceLite((PERESOURCE)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead);
  RtlInitUnicodeString(&EventName, L"\\KernelObjects\\HighNonPagedPoolCondition");
  v6 = IoCreateNotificationEvent(&EventName, &EventHandle);
  Srv2HighNonPagedPoolConditionEvent = v6;
  if ( !v6 )
  {
    v3 = -1073741670;
LABEL_28:
    Srv2UnregisterPerfCounterProvider();
    if ( Srv2HighNonPagedPoolConditionEvent )
    {
      ObfDereferenceObject(Srv2HighNonPagedPoolConditionEvent);
      Srv2HighNonPagedPoolConditionEvent = 0;
    }
    ExDeleteResourceLite((PERESOURCE)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead);
    goto LABEL_31;
  }
  ObfReferenceObject(v6);
  ZwClose(EventHandle);
  v3 = Srv2RegisterPerfCounterProvider();
  if ( v3 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        25,
        WPP_5bb5acbc86b838dd4009309de35c075e_Traceguids,
        (unsigned int)v3);
    }
    goto LABEL_28;
  }
  return v3;
}

```

## disassembly

```asm
0x14009c078  mov     [rsp-28h+arg_0], rbx
0x14009c07d  push    rbp
0x14009c07e  push    rsi
0x14009c07f  push    rdi
0x14009c080  push    r12
0x14009c082  push    r13
0x14009c084  mov     rbp, rsp
0x14009c087  sub     rsp, 60h
0x14009c08b  xor     esi, esi
0x14009c08d  xorps   xmm0, xmm0
0x14009c090  xorps   xmm1, xmm1
0x14009c093  mov     [rbp+arg_10], rsi
0x14009c097  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14009c09b  mov     [rbp+EventHandle], rsi
0x14009c09f  mov     rbx, rcx
0x14009c0a2  movups  xmmword ptr [rbp+EventName.Length], xmm1
0x14009c0a6  call    McGenEventRegister_EtwRegister
0x14009c0ab  lea     rax, WPP_ThisDir_CTLGUID_Srv2Log
0x14009c0b2  mov     qword ptr cs:WPP_MAIN_CB.Type, rsi
0x14009c0b9  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14009c0c0  mov     cs:WPP_MAIN_CB.NextDevice, rsi
0x14009c0c7  mov     cs:WPP_MAIN_CB.CurrentIrp, rsi
0x14009c0ce  mov     cs:WPP_MAIN_CB.Timer, 1
0x14009c0d9  call    WppLoadTracingSupport
0x14009c0de  mov     cs:WPP_MAIN_CB.CurrentIrp, rsi; __annotation("TMC:", "2744F0B7-8455-44f8-9B64-5F589F9D163A", "Srv2Log", "DEBUG_SRV2", "DEBUG_DRIVER_FSCTL", "DEBUG_DRIVER_DISPATCH", "DEBUG_DRIVER_MAIN", "DEBUG_SMB2_PREAUTH_INTEGRITY", "DEBUG_SRVPROC_WORKITEM", "DEBUG_SRVPROC_PROCESSOR", "DEBUG_SRVPROC_PROVIDER", "DEBUG_SRVPROC_WORKER", "DEBUG_SRVPROC_RECEIVER", "DEBUG_SMB2_EXECUTE", "DEBUG_SMB2_VALIDATE", "DEBUG_SMB2_CONNECTION", "DEBUG_SMB2_WORKITEM", "DEBUG_SMB2_PROVIDER", "DEBUG_SMB2_NEGOTIATE", "DEBUG_SMB2_ECHO", "DEBUG_SMB2_SESSIONSETUP", "DEBUG_SMB2_LOGOFF", "DEBUG_SMB2_TREECONNECT", "DEBUG_SMB2_CREATE", "DEBUG_SMB2_CLOSE", "DEBUG_SMB2_OPLOCK", "DEBUG_SMB2_FLUSH", "DEBUG_SMB2_LOCK", "DEBUG_SMB2_QUERY_DIRECTORY", "DEBUG_SMB2_CHANGE_NOTIFY", "DEBUG_SMB2_QUERY_INFO", "DEBUG_SMB2_SET_INFO", "DEBUG_SMB2_IOCTL", "DEBUG_SMB2_LEASE", "DEBUG_CRYPTO", "PUBLIC_TMF:")
0x14009c0e5  call    WppInitKm
0x14009c0ea  call    TlgRegisterAggregateProvider
0x14009c0ef  call    wil_InitializeFeatureStaging
0x14009c0f4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14009c0fb  lea     r12, WPP_GLOBAL_Control
0x14009c102  lea     r13, WPP_5bb5acbc86b838dd4009309de35c075e_Traceguids
0x14009c109  cmp     rcx, r12
0x14009c10c  jz      short loc_14009C12A
0x14009c10e  mov     eax, [rcx+2Ch]
0x14009c111  test    al, 8
0x14009c113  jz      short loc_14009C12A
0x14009c115  cmp     byte ptr [rcx+29h], 2
0x14009c119  jb      short loc_14009C12A
0x14009c11b  mov     rcx, [rcx+18h]
0x14009c11f  lea     edx, [rsi+15h]
0x14009c122  mov     r8, r13
0x14009c125  call    WPP_SF_
0x14009c12a  call    cs:__imp_SrvNetIsDriverLoaded
0x14009c131  nop     dword ptr [rax+rax+00h]
0x14009c136  test    al, al
0x14009c138  jnz     short loc_14009C16E
0x14009c13a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14009c141  cmp     rcx, r12
0x14009c144  jz      short loc_14009C164
0x14009c146  mov     eax, [rcx+2Ch]
0x14009c149  test    al, 8
0x14009c14b  jz      short loc_14009C164
0x14009c14d  cmp     byte ptr [rcx+29h], 1
0x14009c151  jb      short loc_14009C164
0x14009c153  mov     rcx, [rcx+18h]
0x14009c157  mov     edx, 16h
0x14009c15c  mov     r8, r13
0x14009c15f  call    WPP_SF_
0x14009c164  mov     edi, 0C000026Ch
0x14009c169  jmp     loc_14009C40C
0x14009c16e  lea     rdx, aDeviceSrv2; "\\Device\\Srv2"
0x14009c175  lea     rcx, [rbp+DestinationString]; DestinationString
0x14009c179  call    cs:__imp_RtlInitUnicodeString
0x14009c180  nop     dword ptr [rax+rax+00h]
0x14009c185  lea     rcx, WPP_MAIN_CB.Dpc.SystemArgument2; SpinLock
0x14009c18c  call    cs:__imp_KeInitializeSpinLock
0x14009c193  nop     dword ptr [rax+rax+00h]
0x14009c198  lea     rax, WPP_MAIN_CB.Dpc.DpcData
0x14009c19f  mov     r9d, 14h; DeviceType
0x14009c1a5  mov     qword ptr cs:WPP_MAIN_CB.ActiveThreadCount, rax
0x14009c1ac  lea     r8, [rbp+DestinationString]; DeviceName
0x14009c1b0  mov     cs:WPP_MAIN_CB.Dpc.DpcData, rax
0x14009c1b7  xor     edx, edx; DeviceExtensionSize
0x14009c1b9  lea     rax, [rbp+arg_10]
0x14009c1bd  mov     rcx, rbx; DriverObject
0x14009c1c0  mov     [rsp+60h+DeviceObject], rax; DeviceObject
0x14009c1c5  mov     [rsp+60h+Exclusive], sil; Exclusive
0x14009c1ca  mov     [rsp+60h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x14009c1d2  call    cs:__imp_IoCreateDevice
0x14009c1d9  nop     dword ptr [rax+rax+00h]
0x14009c1de  mov     edi, eax
0x14009c1e0  test    eax, eax
0x14009c1e2  jns     short loc_14009C223
0x14009c1e4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14009c1eb  cmp     rcx, r12
0x14009c1ee  jz      loc_14009C40C
0x14009c1f4  mov     edx, [rcx+2Ch]
0x14009c1f7  test    dl, 8
0x14009c1fa  jz      loc_14009C40C
0x14009c200  cmp     byte ptr [rcx+29h], 1
0x14009c204  jb      loc_14009C40C
0x14009c20a  mov     rcx, [rcx+18h]
0x14009c20e  mov     edx, 17h
0x14009c213  mov     r9d, eax
0x14009c216  mov     r8, r13
0x14009c219  call    WPP_SF_d
0x14009c21e  jmp     loc_14009C40C
0x14009c223  mov     rcx, [rbp+arg_10]
0x14009c227  mov     r8d, 1200A0h
0x14009c22d  mov     edx, 1F01FFh
0x14009c232  mov     dword ptr [rsp+60h+Exclusive], r8d
0x14009c237  mov     r9d, 12019Fh
0x14009c23d  mov     [rsp+60h+DeviceCharacteristics], edx
0x14009c241  call    cs:__imp_SrvLibApplySrvDeviceAcl
0x14009c248  nop     dword ptr [rax+rax+00h]
0x14009c24d  mov     edi, eax
0x14009c24f  test    eax, eax
0x14009c251  jns     short loc_14009C291
0x14009c253  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14009c25a  cmp     rcx, r12
0x14009c25d  jz      loc_14009C3EB
0x14009c263  mov     eax, [rcx+2Ch]
0x14009c266  test    al, 8
0x14009c268  jz      loc_14009C3EB
0x14009c26e  cmp     byte ptr [rcx+29h], 1
0x14009c272  jb      loc_14009C3EB
0x14009c278  mov     rcx, [rcx+18h]
0x14009c27c  mov     edx, 18h
0x14009c281  mov     r9d, edi
0x14009c284  mov     r8, r13
0x14009c287  call    WPP_SF_d
0x14009c28c  jmp     loc_14009C3EB
0x14009c291  mov     rax, [rbp+arg_10]
0x14009c295  mov     cs:Srv2DeviceObject, rax
0x14009c29c  call    cs:__imp_IoGetCurrentProcess
0x14009c2a3  nop     dword ptr [rax+rax+00h]
0x14009c2a8  lea     rdi, [rbx+70h]
0x14009c2ac  mov     cs:Srv2DriverState, esi
0x14009c2b2  mov     cs:Srv2ServerProcess, rax
0x14009c2b9  mov     ecx, 1Ch
0x14009c2be  lea     rax, Srv2DefaultDispatch
0x14009c2c5  rep stosq
0x14009c2c8  lea     rax, Srv2Cleanup
0x14009c2cf  mov     [rbx+100h], rax
0x14009c2d6  lea     rcx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead; Resource
0x14009c2dd  lea     rax, Srv2Close
0x14009c2e4  mov     [rbx+80h], rax
0x14009c2eb  lea     rax, Srv2Create
0x14009c2f2  mov     [rbx+70h], rax
0x14009c2f6  lea     rax, Srv2DeviceControl
0x14009c2fd  mov     [rbx+0E0h], rax
0x14009c304  lea     rax, DriverUnload
0x14009c30b  mov     [rbx+68h], rax
0x14009c30f  call    cs:__imp_ExInitializeResourceLite
0x14009c316  nop     dword ptr [rax+rax+00h]
0x14009c31b  lea     rdx, aKernelobjectsH; "\\KernelObjects\\HighNonPagedPoolCondit"...
0x14009c322  lea     rcx, [rbp+EventName]; DestinationString
0x14009c326  call    cs:__imp_RtlInitUnicodeString
0x14009c32d  nop     dword ptr [rax+rax+00h]
0x14009c332  lea     rdx, [rbp+EventHandle]; EventHandle
0x14009c336  lea     rcx, [rbp+EventName]; EventName
0x14009c33a  call    cs:__imp_IoCreateNotificationEvent
0x14009c341  nop     dword ptr [rax+rax+00h]
0x14009c346  mov     cs:Srv2HighNonPagedPoolConditionEvent, rax
0x14009c34d  test    rax, rax
0x14009c350  jnz     short loc_14009C359
0x14009c352  mov     edi, 0C000009Ah
0x14009c357  jmp     short loc_14009C3B4
0x14009c359  mov     rcx, rax; Object
0x14009c35c  call    cs:__imp_ObfReferenceObject
0x14009c363  nop     dword ptr [rax+rax+00h]
0x14009c368  mov     rcx, [rbp+EventHandle]; Handle
0x14009c36c  call    cs:__imp_ZwClose
0x14009c373  nop     dword ptr [rax+rax+00h]
0x14009c378  call    Srv2RegisterPerfCounterProvider
0x14009c37d  mov     edi, eax
0x14009c37f  test    eax, eax
0x14009c381  jns     loc_14009C420
0x14009c387  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14009c38e  cmp     rcx, r12
0x14009c391  jz      short loc_14009C3B4
0x14009c393  mov     eax, [rcx+2Ch]
0x14009c396  test    al, 8
0x14009c398  jz      short loc_14009C3B4
0x14009c39a  cmp     byte ptr [rcx+29h], 1
0x14009c39e  jb      short loc_14009C3B4
0x14009c3a0  mov     rcx, [rcx+18h]
0x14009c3a4  mov     edx, 19h
0x14009c3a9  mov     r9d, edi
0x14009c3ac  mov     r8, r13
0x14009c3af  call    WPP_SF_d
0x14009c3b4  call    Srv2UnregisterPerfCounterProvider
0x14009c3b9  mov     rcx, cs:Srv2HighNonPagedPoolConditionEvent; Object
0x14009c3c0  test    rcx, rcx
0x14009c3c3  jz      short loc_14009C3D8
0x14009c3c5  call    cs:__imp_ObfDereferenceObject
0x14009c3cc  nop     dword ptr [rax+rax+00h]
0x14009c3d1  mov     cs:Srv2HighNonPagedPoolConditionEvent, rsi
0x14009c3d8  lea     rcx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead; Resource
0x14009c3df  call    cs:__imp_ExDeleteResourceLite
0x14009c3e6  nop     dword ptr [rax+rax+00h]
0x14009c3eb  mov     rcx, cs:Srv2DeviceObject; DeviceObject
0x14009c3f2  call    cs:__imp_IoDeleteDevice
0x14009c3f9  nop     dword ptr [rax+rax+00h]
0x14009c3fe  mov     cs:Srv2DeviceObject, rsi
0x14009c405  mov     cs:Srv2ServerProcess, rsi
0x14009c40c  call    wil_UninitializeFeatureStaging
0x14009c411  call    TlgUnregisterAggregateProvider
0x14009c416  call    WppCleanupKm
0x14009c41b  call    McGenEventUnregister_EtwUnregister
0x14009c420  mov     rbx, [rsp+60h+arg_0]
0x14009c428  mov     eax, edi
0x14009c42a  add     rsp, 60h
0x14009c42e  pop     r13
0x14009c430  pop     r12
0x14009c432  pop     rdi
0x14009c433  pop     rsi
0x14009c434  pop     rbp
0x14009c435  retn
```
