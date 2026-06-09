# DriverEntry

- ea: `0x14005f078`
- end: `0x14005f4b9`
- name: `DriverEntry`
- size: `1089`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14005f010`

## callees

- `0x140008d78`
- `0x1400090c4`
- `0x1400091b0`
- `0x1400092b8`
- `0x1400093c0`
- `0x1400094ac`
- `0x14001be80`
- `0x14003cc8c`
- `0x14003ce6c`
- `0x14003cf00`
- `0x14003d2dc`
- `0x14005d644`
- `0x14005f078`
- `0x14005f4c0`
- `0x14005f62c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14005f475`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f475`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005f3ef`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005f3ef`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14005f40d`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14005f40d`
- `ntoskrnl!ExAllocatePool2` at `0x14005f128`
- `ntoskrnl!ExAllocatePool2` at `0x14005f1b4`
- `ntoskrnl!ExAllocatePool2` at `0x14005f1e9`
- `ntoskrnl!ExAllocatePool2` at `0x14005f24a`
- `ntoskrnl!ExAllocatePool2` at `0x14005f128`
- `ntoskrnl!ExAllocatePool2` at `0x14005f1b4`
- `ntoskrnl!ExAllocatePool2` at `0x14005f1e9`
- `ntoskrnl!ExAllocatePool2` at `0x14005f24a`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  _DRIVER_OBJECT **Pool2; // rax
  _DRIVER_OBJECT **v4; // rbx
  __int64 v5; // rax
  _QWORD *v6; // rax
  _QWORD *v7; // rdx
  __int64 v8; // rax
  unsigned int v9; // edx
  int DeviceObjectPointer; // ebx
  unsigned int v11; // edx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD InputBuffer[32]; // [rsp+50h] [rbp-B0h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+160h] [rbp+60h] BYREF
  PFILE_OBJECT FileObject; // [rsp+170h] [rbp+70h] BYREF

  memset(InputBuffer, 0, 0xF8u);
  FileObject = 0;
  DestinationString = 0;
  DeviceObject = 0;
  DriverObject->DriverUnload = 0;
  wil_InitializeFeatureStaging();
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_VolMgr;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  Pool2 = (_DRIVER_OBJECT **)ExAllocatePool2(66, 312, 538996054);
  v4 = Pool2;
  if ( !Pool2 )
  {
    Global = 0;
    wil_UninitializeFeatureStaging();
    return -1073741670;
  }
  memset(Pool2, 0, 0x138u);
  Global = (VMX_GLOBAL_DATA *)v4;
  v4[22] = (_DRIVER_OBJECT *)(v4 + 21);
  v4[21] = (_DRIVER_OBJECT *)(v4 + 21);
  v4[24] = (_DRIVER_OBJECT *)(v4 + 23);
  v4[23] = (_DRIVER_OBJECT *)(v4 + 23);
  v4[26] = (_DRIVER_OBJECT *)(v4 + 25);
  v4[25] = (_DRIVER_OBJECT *)(v4 + 25);
  *v4 = DriverObject;
  VmxpCheckSystemLicense();
  VmxpReadTestMode();
  VmxpReadPrimaryPackId();
  VmxpReadPendingPrimaryPackId();
  VmxpPauseOnlineInternal(0);
  VmxpReadOnlineSplitBrainVolumes();
  v5 = ExAllocatePool2(66, 0x8000, 1967287638);
  *((_QWORD *)Global + 32) = v5;
  if ( !v5 )
    goto LABEL_8;
  v6 = (_QWORD *)ExAllocatePool2(258, 56, 538996054);
  v7 = v6;
  if ( v6 )
  {
    *v6 = 1;
    v6[4] = v6 + 3;
    v6[3] = v6 + 3;
    v6[6] = v6 + 5;
    v6[5] = v6 + 5;
    v6[2] = v6 + 1;
    v6[1] = v6 + 1;
  }
  else
  {
    v7 = 0;
  }
  *((_QWORD *)Global + 36) = v7;
  if ( !v7 || (v8 = ExAllocatePool2(258, 0x4000, 1649569110), (*((_QWORD *)Global + 33) = v8) == 0) )
  {
LABEL_8:
    wil_UninitializeFeatureStaging();
    if ( Global )
      VMX_GLOBAL_DATA::`scalar deleting destructor'(Global, v9);
    return -1073741670;
  }
  InputBuffer[0] = VmxWholeDiskArrivedImmediate;
  InputBuffer[1] = VmxWholeDiskArrivedDelayed;
  InputBuffer[2] = VmxPartitionArrivedImmediate;
  InputBuffer[3] = VmxPartitionArrivedDelayed;
  InputBuffer[4] = VmxPartitionRemovedImmediate;
  InputBuffer[5] = VmxPartitionRemovedDelayed;
  InputBuffer[6] = VmxWholeDiskRemovedImmediate;
  InputBuffer[7] = VmxWholeDiskRemovedDelayed;
  InputBuffer[8] = VmxBootDriverReinitialization;
  InputBuffer[9] = VmxDriverReinitialization;
  InputBuffer[10] = VmxShutdown;
  InputBuffer[11] = VmxSetPowerState;
  InputBuffer[12] = VmxVolMgrDeviceControl;
  InputBuffer[13] = VmxVolumeDeviceControl;
  InputBuffer[14] = VmxReadWrite;
  InputBuffer[15] = VmxQueryVolumeId;
  InputBuffer[16] = VmxQueryStackSize;
  InputBuffer[17] = VmxQueryAlignmentRequirement;
  InputBuffer[18] = VmxQuerySystemBootFlags;
  InputBuffer[19] = VmxQueryGptAttributes;
  InputBuffer[20] = VmxQueryPowerRelations;
  InputBuffer[21] = VmxQueryNumaNode;
  InputBuffer[22] = VmxSetGptAttributes;
  InputBuffer[23] = VmxCreateLegacyNameLinks;
  InputBuffer[24] = VmxDeleteLegacyNameLinks;
  InputBuffer[25] = VmxResidingOnDisk;
  InputBuffer[26] = VmxDependsOnPartition;
  InputBuffer[27] = VmxBroadcastIrp;
  InputBuffer[28] = VmxShutdownVolume;
  InputBuffer[29] = VmxCommitDeviceCallback;
  InputBuffer[30] = VmxSetSplitIoNotifyRoutines;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\VolMgrControl");
  DeviceObjectPointer = IoGetDeviceObjectPointer(&DestinationString, 0x80u, &FileObject, &DeviceObject);
  if ( DeviceObjectPointer < 0
    || (DeviceObjectPointer = VmxpSendDeviceControl(
                                DeviceObject,
                                0x760640u,
                                InputBuffer,
                                0xF8u,
                                (char *)Global + 8,
                                0xA0u,
                                1u),
        ObfDereferenceObject(FileObject),
        DeviceObjectPointer < 0) )
  {
    wil_UninitializeFeatureStaging();
    if ( Global )
      VMX_GLOBAL_DATA::`scalar deleting destructor'(Global, v11);
    return DeviceObjectPointer;
  }
  else
  {
    VmxpSetSoftBoot();
    return 0;
  }
}

```

## disassembly

```asm
0x14005f078  mov     [rsp-8+arg_8], rbx
0x14005f07d  mov     [rsp-8+arg_18], rdi
0x14005f082  push    rbp
0x14005f083  lea     rbp, [rsp-50h]
0x14005f088  sub     rsp, 150h
0x14005f08f  mov     rdi, rcx
0x14005f092  xor     edx, edx; Val
0x14005f094  lea     rcx, [rsp+150h+InputBuffer]; void *
0x14005f099  mov     r8d, 0F8h; Size
0x14005f09f  call    memset
0x14005f0a4  xorps   xmm0, xmm0
0x14005f0a7  mov     [rbp+50h+FileObject], 0
0x14005f0af  movups  xmmword ptr [rsp+150h+DestinationString.Length], xmm0
0x14005f0b4  mov     [rbp+50h+DeviceObject], 0
0x14005f0bc  mov     qword ptr [rdi+68h], 0
0x14005f0c4  call    wil_InitializeFeatureStaging
0x14005f0c9  lea     rax, WPP_ThisDir_CTLGUID_VolMgr
0x14005f0d0  mov     qword ptr cs:WPP_MAIN_CB.Type, 0
0x14005f0db  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14005f0e2  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x14005f0ed  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14005f0f8  mov     cs:WPP_MAIN_CB.Timer, 1
0x14005f103  call    WppLoadTracingSupport
0x14005f108  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14005f113  call    WppInitKm
0x14005f118  mov     edx, 138h
0x14005f11d  mov     ecx, 42h ; 'B'
0x14005f122  mov     r8d, 20206D56h
0x14005f128  call    cs:__imp_ExAllocatePool2
0x14005f12f  nop     dword ptr [rax+rax+00h]
0x14005f134  mov     rbx, rax
0x14005f137  test    rax, rax
0x14005f13a  jz      loc_14005F48E
0x14005f140  xor     edx, edx; Val
0x14005f142  mov     r8d, 138h; Size
0x14005f148  mov     rcx, rax; void *
0x14005f14b  call    memset
0x14005f150  lea     rcx, [rbx+0A8h]
0x14005f157  mov     cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA, rbx; VMX_GLOBAL_DATA * Global
0x14005f15e  mov     [rcx+8], rcx
0x14005f162  lea     rdx, [rbx+0C8h]
0x14005f169  mov     [rcx], rcx
0x14005f16c  lea     rcx, [rbx+0B8h]
0x14005f173  mov     [rcx+8], rcx
0x14005f177  mov     [rcx], rcx
0x14005f17a  mov     [rdx+8], rdx
0x14005f17e  mov     [rdx], rdx
0x14005f181  mov     [rbx], rdi
0x14005f184  call    VmxpCheckSystemLicense
0x14005f189  call    ?VmxpReadTestMode@@YAJXZ; VmxpReadTestMode(void)
0x14005f18e  call    ?VmxpReadPrimaryPackId@@YAJXZ; VmxpReadPrimaryPackId(void)
0x14005f193  call    ?VmxpReadPendingPrimaryPackId@@YAJXZ; VmxpReadPendingPrimaryPackId(void)
0x14005f198  xor     ecx, ecx
0x14005f19a  call    VmxpPauseOnlineInternal
0x14005f19f  call    ?VmxpReadOnlineSplitBrainVolumes@@YAJXZ; VmxpReadOnlineSplitBrainVolumes(void)
0x14005f1a4  mov     edx, 8000h
0x14005f1a9  mov     ecx, 42h ; 'B'
0x14005f1ae  mov     r8d, 75426D56h
0x14005f1b4  call    cs:__imp_ExAllocatePool2
0x14005f1bb  nop     dword ptr [rax+rax+00h]
0x14005f1c0  mov     rcx, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14005f1c7  mov     [rcx+100h], rax
0x14005f1ce  test    rax, rax
0x14005f1d1  jz      loc_14005F269
0x14005f1d7  mov     ebx, 102h
0x14005f1dc  mov     edx, 38h ; '8'
0x14005f1e1  mov     ecx, ebx
0x14005f1e3  mov     r8d, 20206D56h
0x14005f1e9  call    cs:__imp_ExAllocatePool2
0x14005f1f0  nop     dword ptr [rax+rax+00h]
0x14005f1f5  mov     rdx, rax
0x14005f1f8  test    rax, rax
0x14005f1fb  jz      short loc_14005F227
0x14005f1fd  lea     rcx, [rax+18h]
0x14005f201  mov     qword ptr [rax], 1
0x14005f208  mov     [rcx+8], rcx
0x14005f20c  mov     [rcx], rcx
0x14005f20f  lea     rcx, [rax+28h]
0x14005f213  mov     [rcx+8], rcx
0x14005f217  mov     [rcx], rcx
0x14005f21a  lea     rcx, [rax+8]
0x14005f21e  mov     [rcx+8], rcx
0x14005f222  mov     [rcx], rcx
0x14005f225  jmp     short loc_14005F229
0x14005f227  xor     edx, edx
0x14005f229  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14005f230  mov     [rax+120h], rdx
0x14005f237  test    rdx, rdx
0x14005f23a  jz      short loc_14005F269
0x14005f23c  mov     edx, 4000h
0x14005f241  mov     r8d, 62526D56h
0x14005f247  mov     rcx, rbx
0x14005f24a  call    cs:__imp_ExAllocatePool2
0x14005f251  nop     dword ptr [rax+rax+00h]
0x14005f256  mov     rcx, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14005f25d  mov     [rcx+108h], rax
0x14005f264  test    rax, rax
0x14005f267  jnz     short loc_14005F288
0x14005f269  call    wil_UninitializeFeatureStaging
0x14005f26e  mov     rcx, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; this
0x14005f275  test    rcx, rcx
0x14005f278  jz      loc_14005F49E
0x14005f27e  call    ??_GVMX_GLOBAL_DATA@@QEAAPEAXI@Z; VMX_GLOBAL_DATA::`scalar deleting destructor'(uint)
0x14005f283  jmp     loc_14005F49E
0x14005f288  lea     rax, ?VmxWholeDiskArrivedImmediate@@YAJPEAU_DEVICE_OBJECT@@PEAE@Z; VmxWholeDiskArrivedImmediate(_DEVICE_OBJECT *,uchar *)
0x14005f28f  mov     [rsp+150h+InputBuffer], rax
0x14005f294  lea     rdx, aDeviceVolmgrco; "\\Device\\VolMgrControl"
0x14005f29b  lea     rax, ?VmxWholeDiskArrivedDelayed@@YAJPEAU_DEVICE_OBJECT@@@Z; VmxWholeDiskArrivedDelayed(_DEVICE_OBJECT *)
0x14005f2a2  mov     [rsp+150h+var_F8], rax
0x14005f2a7  lea     rcx, [rsp+150h+DestinationString]; DestinationString
0x14005f2ac  lea     rax, ?VmxPartitionArrivedImmediate@@YAJPEAU_DEVICE_OBJECT@@0PEAU_PARTITION_INFORMATION_EX@@PEAE@Z; VmxPartitionArrivedImmediate(_DEVICE_OBJECT *,_DEVICE_OBJECT *,_PARTITION_INFORMATION_EX *,uchar *)
0x14005f2b3  mov     [rsp+150h+var_F0], rax
0x14005f2b8  lea     rax, ?VmxPartitionArrivedDelayed@@YAJPEAU_DEVICE_OBJECT@@0@Z; VmxPartitionArrivedDelayed(_DEVICE_OBJECT *,_DEVICE_OBJECT *)
0x14005f2bf  mov     [rsp+150h+var_E8], rax
0x14005f2c4  lea     rax, ?VmxPartitionRemovedImmediate@@YAJPEAU_DEVICE_OBJECT@@0PEAU_PARTITION_INFORMATION_EX@@PEAE@Z; VmxPartitionRemovedImmediate(_DEVICE_OBJECT *,_DEVICE_OBJECT *,_PARTITION_INFORMATION_EX *,uchar *)
0x14005f2cb  mov     [rsp+150h+var_E0], rax
0x14005f2d0  lea     rax, ?VmxPartitionRemovedDelayed@@YAJPEAU_DEVICE_OBJECT@@0@Z; VmxPartitionRemovedDelayed(_DEVICE_OBJECT *,_DEVICE_OBJECT *)
0x14005f2d7  mov     [rsp+150h+var_D8], rax
0x14005f2dc  lea     rax, ?VmxWholeDiskRemovedImmediate@@YAJPEAU_DEVICE_OBJECT@@PEAE@Z; VmxWholeDiskRemovedImmediate(_DEVICE_OBJECT *,uchar *)
0x14005f2e3  mov     [rbp+50h+var_D0], rax
0x14005f2e7  lea     rax, ?VmxWholeDiskRemovedDelayed@@YAJPEAU_DEVICE_OBJECT@@@Z; VmxWholeDiskRemovedDelayed(_DEVICE_OBJECT *)
0x14005f2ee  mov     [rbp+50h+var_C8], rax
0x14005f2f2  lea     rax, ?VmxBootDriverReinitialization@@YAXXZ; VmxBootDriverReinitialization(void)
0x14005f2f9  mov     [rbp+50h+var_C0], rax
0x14005f2fd  lea     rax, ?VmxDriverReinitialization@@YAXXZ; VmxDriverReinitialization(void)
0x14005f304  mov     [rbp+50h+var_B8], rax
0x14005f308  lea     rax, ?VmxShutdown@@YAXXZ; VmxShutdown(void)
0x14005f30f  mov     [rbp+50h+var_B0], rax
0x14005f313  lea     rax, ?VmxSetPowerState@@YAXPEAU_DEVICE_OBJECT@@0W4_DEVICE_POWER_STATE@@@Z; VmxSetPowerState(_DEVICE_OBJECT *,_DEVICE_OBJECT *,_DEVICE_POWER_STATE)
0x14005f31a  mov     [rbp+50h+var_A8], rax
0x14005f31e  lea     rax, ?VmxVolMgrDeviceControl@@YAJPEAU_IRP@@@Z; VmxVolMgrDeviceControl(_IRP *)
0x14005f325  mov     [rbp+50h+var_A0], rax
0x14005f329  lea     rax, ?VmxVolumeDeviceControl@@YAJPEAXPEAU_IRP@@@Z; VmxVolumeDeviceControl(void *,_IRP *)
0x14005f330  mov     [rbp+50h+var_98], rax
0x14005f334  lea     rax, VmxReadWrite
0x14005f33b  mov     [rbp+50h+var_90], rax
0x14005f33f  lea     rax, ?VmxQueryVolumeId@@YAXPEAXPEAU_GUID@@@Z; VmxQueryVolumeId(void *,_GUID *)
0x14005f346  mov     [rbp+50h+var_88], rax
0x14005f34a  lea     rax, ?VmxQueryStackSize@@YAEPEAX@Z; VmxQueryStackSize(void *)
0x14005f351  mov     [rbp+50h+var_80], rax
0x14005f355  lea     rax, ?VmxQueryAlignmentRequirement@@YAKPEAX@Z; VmxQueryAlignmentRequirement(void *)
0x14005f35c  mov     [rbp+50h+var_78], rax
0x14005f360  lea     rax, ?VmxQuerySystemBootFlags@@YAXPEAXPEAE11@Z; VmxQuerySystemBootFlags(void *,uchar *,uchar *,uchar *)
0x14005f367  mov     [rbp+50h+var_70], rax
0x14005f36b  lea     rax, ?VmxQueryGptAttributes@@YA_KPEAX@Z; VmxQueryGptAttributes(void *)
0x14005f372  mov     [rbp+50h+var_68], rax
0x14005f376  lea     rax, ?VmxQueryPowerRelations@@YAJPEAXPEAPEAU_DEVICE_RELATIONS@@@Z; VmxQueryPowerRelations(void *,_DEVICE_RELATIONS * *)
0x14005f37d  mov     [rbp+50h+var_60], rax
0x14005f381  lea     rax, ?VmxQueryNumaNode@@YAJPEAXPEAK@Z; VmxQueryNumaNode(void *,ulong *)
0x14005f388  mov     [rbp+50h+var_58], rax
0x14005f38c  lea     rax, ?VmxSetGptAttributes@@YAJPEAX_KE@Z; VmxSetGptAttributes(void *,unsigned __int64,uchar)
0x14005f393  mov     [rbp+50h+var_50], rax
0x14005f397  lea     rax, ?VmxCreateLegacyNameLinks@@YAXPEAXPEAG@Z; VmxCreateLegacyNameLinks(void *,ushort *)
0x14005f39e  mov     [rbp+50h+var_48], rax
0x14005f3a2  lea     rax, ?VmxDeleteLegacyNameLinks@@YAXPEAX@Z; VmxDeleteLegacyNameLinks(void *)
0x14005f3a9  mov     [rbp+50h+var_40], rax
0x14005f3ad  lea     rax, ?VmxResidingOnDisk@@YAEPEAXPEAU_DEVICE_OBJECT@@PEAE@Z; VmxResidingOnDisk(void *,_DEVICE_OBJECT *,uchar *)
0x14005f3b4  mov     [rbp+50h+var_38], rax
0x14005f3b8  lea     rax, ?VmxDependsOnPartition@@YAEPEAXPEAU_DEVICE_OBJECT@@1@Z; VmxDependsOnPartition(void *,_DEVICE_OBJECT *,_DEVICE_OBJECT *)
0x14005f3bf  mov     [rbp+50h+var_30], rax
0x14005f3c3  lea     rax, ?VmxBroadcastIrp@@YAXPEAXPEAU_IRP@@P6AX0J@Z0E@Z; VmxBroadcastIrp(void *,_IRP *,void (*)(void *,long),void *,uchar)
0x14005f3ca  mov     [rbp+50h+var_28], rax
0x14005f3ce  lea     rax, ?VmxShutdownVolume@@YAXPEAX@Z; VmxShutdownVolume(void *)
0x14005f3d5  mov     [rbp+50h+var_20], rax
0x14005f3d9  lea     rax, ?VmxCommitDeviceCallback@@YAXPEAX0E@Z; VmxCommitDeviceCallback(void *,void *,uchar)
0x14005f3e0  mov     [rbp+50h+var_18], rax
0x14005f3e4  lea     rax, ?VmxSetSplitIoNotifyRoutines@@YAXPEAXPEAU_WMI_SPLITIO_NOTIFY_ROUTINES@@@Z; VmxSetSplitIoNotifyRoutines(void *,_WMI_SPLITIO_NOTIFY_ROUTINES *)
0x14005f3eb  mov     [rbp+50h+var_10], rax
0x14005f3ef  call    cs:__imp_RtlInitUnicodeString
0x14005f3f6  nop     dword ptr [rax+rax+00h]
0x14005f3fb  lea     r9, [rbp+50h+DeviceObject]; DeviceObject
0x14005f3ff  mov     edx, 80h; DesiredAccess
0x14005f404  lea     r8, [rbp+50h+FileObject]; FileObject
0x14005f408  lea     rcx, [rsp+150h+DestinationString]; ObjectName
0x14005f40d  call    cs:__imp_IoGetDeviceObjectPointer
0x14005f414  nop     dword ptr [rax+rax+00h]
0x14005f419  mov     ebx, eax
0x14005f41b  test    eax, eax
0x14005f41d  jns     short loc_14005F439
0x14005f41f  call    wil_UninitializeFeatureStaging
0x14005f424  mov     rcx, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; this
0x14005f42b  test    rcx, rcx
0x14005f42e  jz      short loc_14005F435
0x14005f430  call    ??_GVMX_GLOBAL_DATA@@QEAAPEAXI@Z; VMX_GLOBAL_DATA::`scalar deleting destructor'(uint)
0x14005f435  mov     eax, ebx
0x14005f437  jmp     short loc_14005F4A3
0x14005f439  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14005f440  lea     r8, [rsp+150h+InputBuffer]; InputBuffer
0x14005f445  mov     rcx, [rbp+50h+DeviceObject]; DeviceObject
0x14005f449  add     rax, 8
0x14005f44d  mov     [rsp+150h+var_120], 1; BOOLEAN
0x14005f452  mov     r9d, 0F8h; InputBufferLength
0x14005f458  mov     [rsp+150h+var_128], 0A0h; ULONG
0x14005f460  mov     edx, 760640h; IoControlCode
0x14005f465  mov     [rsp+150h+var_130], rax; PVOID
0x14005f46a  call    ?VmxpSendDeviceControl@@YAJPEAU_DEVICE_OBJECT@@KPEAXK1KE@Z; VmxpSendDeviceControl(_DEVICE_OBJECT *,ulong,void *,ulong,void *,ulong,uchar)
0x14005f46f  mov     rcx, [rbp+50h+FileObject]; Object
0x14005f473  mov     ebx, eax
0x14005f475  call    cs:__imp_ObfDereferenceObject
0x14005f47c  nop     dword ptr [rax+rax+00h]
0x14005f481  test    ebx, ebx
0x14005f483  js      short loc_14005F41F
0x14005f485  call    ?VmxpSetSoftBoot@@YAJXZ; VmxpSetSoftBoot(void)
0x14005f48a  xor     eax, eax
0x14005f48c  jmp     short loc_14005F4A3
0x14005f48e  mov     cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA, 0; VMX_GLOBAL_DATA * Global
0x14005f499  call    wil_UninitializeFeatureStaging
0x14005f49e  mov     eax, 0C000009Ah
0x14005f4a3  lea     r11, [rsp+150h+var_s0]
0x14005f4ab  mov     rbx, [r11+18h]
0x14005f4af  mov     rdi, [r11+28h]
0x14005f4b3  mov     rsp, r11
0x14005f4b6  pop     rbp
0x14005f4b7  retn
```
