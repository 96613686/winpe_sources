# DriverEntry

- ea: `0x140018078`
- end: `0x14001828f`
- name: `DriverEntry`
- size: `535`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x140018010`

## callees

- `0x140004934`
- `0x140014a44`
- `0x140014d70`
- `0x140014fe8`
- `0x140018078`
- `0x140018298`
- `0x1400184b0`

## import_xrefs

- `ntoskrnl!IoRegisterDriverReinitialization` at `0x14001823f`
- `ntoskrnl!IoRegisterDriverReinitialization` at `0x14001823f`
- `ntoskrnl!IoInvalidateDeviceState` at `0x140018250`
- `ntoskrnl!IoInvalidateDeviceState` at `0x140018250`
- `ntoskrnl!IoReportDetectedDevice` at `0x140018169`
- `ntoskrnl!IoReportDetectedDevice` at `0x140018169`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x140018207`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x140018207`
- `ntoskrnl!IoRegisterBootDriverReinitialization` at `0x140018226`
- `ntoskrnl!IoRegisterBootDriverReinitialization` at `0x140018226`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1400181ac`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1400181ac`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS GlobalSettings; // ebx
  PDEVICE_OBJECT PhysicalDeviceObject; // [rsp+50h] [rbp+8h] BYREF

  PhysicalDeviceObject = 0;
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation();
  McGenEventRegister_EtwRegister();
  DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)VmCreate;
  DriverObject->MajorFunction[3] = (PDRIVER_DISPATCH)VmReadWrite;
  DriverObject->MajorFunction[4] = (PDRIVER_DISPATCH)VmReadWrite;
  DriverObject->MajorFunction[9] = (PDRIVER_DISPATCH)VmFlushBuffers;
  DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)VmDeviceControl;
  DriverObject->MajorFunction[15] = (PDRIVER_DISPATCH)VmInternalDeviceControl;
  DriverObject->MajorFunction[16] = (PDRIVER_DISPATCH)VmShutdown;
  DriverObject->MajorFunction[18] = (PDRIVER_DISPATCH)VmCleanup;
  DriverObject->MajorFunction[22] = (PDRIVER_DISPATCH)VmPower;
  DriverObject->MajorFunction[23] = (PDRIVER_DISPATCH)VmWmi;
  DriverObject->MajorFunction[27] = (PDRIVER_DISPATCH)VmPnp;
  DriverObject->DriverUnload = (PDRIVER_UNLOAD)VmUnload;
  GlobalSettings = IoReportDetectedDevice(
                     DriverObject,
                     InterfaceTypeUndefined,
                     0xFFFFFFFF,
                     0xFFFFFFFF,
                     0,
                     0,
                     1u,
                     &PhysicalDeviceObject);
  if ( GlobalSettings < 0
    || (GlobalSettings = VmAddDevice(DriverObject, PhysicalDeviceObject), GlobalSettings < 0)
    || (GlobalSettings = RtlDuplicateUnicodeString(1u, RegistryPath, (PUNICODE_STRING)VmRootExtension + 18),
        GlobalSettings < 0)
    || (GlobalSettings = VmpQueryGlobalSettings(), GlobalSettings < 0)
    || (GlobalSettings = IoRegisterPlugPlayNotification(
                           EventCategoryDeviceInterfaceChange,
                           0,
                           &GUID_DEVINTERFACE_HIDDEN_VOLUME,
                           DriverObject,
                           VmVolumeDeviceNotification,
                           0,
                           (PVOID *)VmRootExtension + 47),
        GlobalSettings < 0) )
  {
    if ( VmRootExtension )
      VmpRemoveDevice(*(PDEVICE_OBJECT *)VmRootExtension, 1);
    VmUnload(DriverObject);
  }
  else
  {
    IoRegisterBootDriverReinitialization(DriverObject, VmBootDriverReinitialization, 0);
    IoRegisterDriverReinitialization(DriverObject, VmDriverReinitialization, 0);
    IoInvalidateDeviceState(PhysicalDeviceObject);
  }
  return GlobalSettings;
}

```

## disassembly

```asm
0x140018078  mov     [rsp+arg_8], rbx
0x14001807d  mov     [rsp+arg_10], rsi
0x140018082  push    rdi
0x140018083  sub     rsp, 40h
0x140018087  mov     rsi, rdx
0x14001808a  mov     [rsp+48h+PhysicalDeviceObject], 0
0x140018093  mov     rdi, rcx
0x140018096  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x14001809b  call    McGenEventRegister_EtwRegister
0x1400180a0  lea     rax, VmCreate
0x1400180a7  or      r8d, 0FFFFFFFFh; BusNumber
0x1400180ab  mov     [rdi+70h], rax
0x1400180af  mov     r9d, r8d; SlotNumber
0x1400180b2  lea     rax, VmReadWrite
0x1400180b9  or      edx, 0FFFFFFFFh; LegacyBusType
0x1400180bc  mov     [rdi+88h], rax
0x1400180c3  mov     rcx, rdi; DriverObject
0x1400180c6  mov     [rdi+90h], rax
0x1400180cd  lea     rax, VmFlushBuffers
0x1400180d4  mov     [rdi+0B8h], rax
0x1400180db  lea     rax, VmDeviceControl
0x1400180e2  mov     [rdi+0E0h], rax
0x1400180e9  lea     rax, VmInternalDeviceControl
0x1400180f0  mov     [rdi+0E8h], rax
0x1400180f7  lea     rax, VmShutdown
0x1400180fe  mov     [rdi+0F0h], rax
0x140018105  lea     rax, VmCleanup
0x14001810c  mov     [rdi+100h], rax
0x140018113  lea     rax, VmPower
0x14001811a  mov     [rdi+120h], rax
0x140018121  lea     rax, VmWmi
0x140018128  mov     [rdi+128h], rax
0x14001812f  lea     rax, VmPnp
0x140018136  mov     [rdi+148h], rax
0x14001813d  lea     rax, VmUnload
0x140018144  mov     [rdi+68h], rax
0x140018148  lea     rax, [rsp+48h+PhysicalDeviceObject]
0x14001814d  mov     [rsp+48h+DeviceObject], rax; DeviceObject
0x140018152  mov     [rsp+48h+ResourceAssigned], 1; ResourceAssigned
0x140018157  mov     [rsp+48h+ResourceRequirements], 0; ResourceRequirements
0x140018160  mov     [rsp+48h+ResourceList], 0; ResourceList
0x140018169  call    cs:__imp_IoReportDetectedDevice
0x140018170  nop     dword ptr [rax+rax+00h]
0x140018175  mov     ebx, eax
0x140018177  test    eax, eax
0x140018179  js      loc_14001825E
0x14001817f  mov     rdx, [rsp+48h+PhysicalDeviceObject]
0x140018184  mov     rcx, rdi
0x140018187  call    VmAddDevice
0x14001818c  mov     ebx, eax
0x14001818e  test    eax, eax
0x140018190  js      loc_14001825E
0x140018196  mov     r8, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x14001819d  mov     rdx, rsi; StringIn
0x1400181a0  add     r8, 120h; StringOut
0x1400181a7  mov     ecx, 1; Flags
0x1400181ac  call    cs:__imp_RtlDuplicateUnicodeString
0x1400181b3  nop     dword ptr [rax+rax+00h]
0x1400181b8  mov     ebx, eax
0x1400181ba  test    eax, eax
0x1400181bc  js      loc_14001825E
0x1400181c2  call    VmpQueryGlobalSettings
0x1400181c7  mov     ebx, eax
0x1400181c9  test    eax, eax
0x1400181cb  js      loc_14001825E
0x1400181d1  mov     rax, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x1400181d8  lea     r8, GUID_DEVINTERFACE_HIDDEN_VOLUME; EventCategoryData
0x1400181df  add     rax, 178h
0x1400181e5  xor     edx, edx; EventCategoryFlags
0x1400181e7  mov     qword ptr [rsp+48h+ResourceAssigned], rax; NotificationEntry
0x1400181ec  mov     r9, rdi; DriverObject
0x1400181ef  lea     rax, VmVolumeDeviceNotification
0x1400181f6  mov     [rsp+48h+ResourceRequirements], 0; Context
0x1400181ff  mov     [rsp+48h+ResourceList], rax; CallbackRoutine
0x140018204  lea     ecx, [rdx+2]; EventCategory
0x140018207  call    cs:__imp_IoRegisterPlugPlayNotification
0x14001820e  nop     dword ptr [rax+rax+00h]
0x140018213  mov     ebx, eax
0x140018215  test    eax, eax
0x140018217  js      short loc_14001825E
0x140018219  xor     r8d, r8d; Context
0x14001821c  lea     rdx, VmBootDriverReinitialization; DriverReinitializationRoutine
0x140018223  mov     rcx, rdi; DriverObject
0x140018226  call    cs:__imp_IoRegisterBootDriverReinitialization
0x14001822d  nop     dword ptr [rax+rax+00h]
0x140018232  xor     r8d, r8d; Context
0x140018235  lea     rdx, VmDriverReinitialization; DriverReinitializationRoutine
0x14001823c  mov     rcx, rdi; DriverObject
0x14001823f  call    cs:__imp_IoRegisterDriverReinitialization
0x140018246  nop     dword ptr [rax+rax+00h]
0x14001824b  mov     rcx, [rsp+48h+PhysicalDeviceObject]; PhysicalDeviceObject
0x140018250  call    cs:__imp_IoInvalidateDeviceState
0x140018257  nop     dword ptr [rax+rax+00h]
0x14001825c  jmp     short loc_14001827C
0x14001825e  mov     rcx, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x140018265  test    rcx, rcx
0x140018268  jz      short loc_140018274
0x14001826a  mov     rcx, [rcx]; DeviceObject
0x14001826d  mov     dl, 1
0x14001826f  call    VmpRemoveDevice
0x140018274  mov     rcx, rdi
0x140018277  call    VmUnload
0x14001827c  mov     rsi, [rsp+48h+arg_10]
0x140018281  mov     eax, ebx
0x140018283  mov     rbx, [rsp+48h+arg_8]
0x140018288  add     rsp, 40h
0x14001828c  pop     rdi
0x14001828d  retn
```
