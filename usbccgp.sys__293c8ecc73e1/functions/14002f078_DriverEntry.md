# DriverEntry

- ea: `0x14002f078`
- end: `0x14002f260`
- name: `DriverEntry`
- size: `488`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002f010`

## callees

- `0x14000a6cc`
- `0x140014d50`
- `0x1400268fc`
- `0x14002d1b8`
- `0x14002d27c`
- `0x14002dc8c`
- `0x14002de2c`
- `0x14002f078`
- `0x14002f268`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14002f0ae`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14002f1e6`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14002f0ae`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14002f1e6`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002f1d5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002f1d5`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_Initialize` at `0x14002f20a`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_Initialize` at `0x14002f20a`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int (__fastcall *SystemRoutineAddress)(__int64, char *, __int64); // rax
  __int64 v5; // rcx
  _LIST_ENTRY *v6; // rax
  NTSTATUS result; // eax
  int v8; // edx
  struct _UNICODE_STRING SystemRoutineName; // [rsp+30h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-18h] BYREF
  char v11; // [rsp+60h] [rbp+8h] BYREF

  *(_QWORD *)&SystemRoutineName.Length = 3276848;
  DestinationString = 0;
  v11 = 0;
  SystemRoutineName.Buffer = L"NtQuerySystemInformation";
  SystemRoutineAddress = (int (__fastcall *)(__int64, char *, __int64))MmGetSystemRoutineAddress(&SystemRoutineName);
  if ( SystemRoutineAddress && SystemRoutineAddress(227, &v11, 1) >= 0 && v11 )
    ExPoolZeroingNativelySupported = 1;
  ExDefaultNonPagedPoolType = 512;
  ExDefaultMdlProtection = 0x40000000;
  DriverObject->MajorFunction[22] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))USBC_Dispatch;
  DriverObject->MajorFunction[27] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))USBC_Dispatch;
  DriverObject->MajorFunction[15] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))USBC_Dispatch;
  DriverObject->MajorFunction[23] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))USBC_Dispatch;
  DriverObject->MajorFunction[14] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))USBC_Dispatch;
  DriverObject->MajorFunction[2] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))USBC_Dispatch;
  DriverObject->MajorFunction[0] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))USBC_Dispatch;
  DriverObject->DriverUnload = (void (__fastcall *)(_DRIVER_OBJECT *))USBC_DriverUnload;
  DriverObject->DriverExtension->AddDevice = (int (__fastcall *)(_DRIVER_OBJECT *, _DEVICE_OBJECT *))USBC_AddDevice;
  RegQueryGenericCompositeUSBDeviceString();
  wil_InitializeFeatureStaging();
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (_DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_USBCCGP;
  WPP_MAIN_CB.DeviceType = 0;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (struct _IO_TIMER *)1;
  WPP_MAIN_CB.DeviceExtension = 0;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm(DriverObject, RegistryPath);
  AllocateDriverGlobalIFRLog();
  USBC_WmiDriverEntry(v5, RegistryPath);
  RtlInitUnicodeString(&DestinationString, L"KseQueryDeviceFlags");
  v6 = (_LIST_ENTRY *)MmGetSystemRoutineAddress(&DestinationString);
  g_DriverObject = (__int64)DriverObject;
  WPP_MAIN_CB.Queue.ListEntry.Flink = v6;
  result = SleepstudyHelper_Initialize(&g_SleepstudyLibraryHandle, DriverObject);
  if ( result < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 3;
      WPP_RECORDER_SF_d(g_RecorderLog, v8, 8, 14, (__int64)WPP_e84aa8ae2d9034c0d4fedfbc39bcd7a4_Traceguids, result);
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14002f078  mov     rax, rsp
0x14002f07b  mov     [rax+10h], rbx
0x14002f07f  push    rdi
0x14002f080  sub     rsp, 50h
0x14002f084  mov     qword ptr [rax-28h], 320030h
0x14002f08c  xorps   xmm0, xmm0
0x14002f08f  movups  xmmword ptr [rax-18h], xmm0
0x14002f093  mov     byte ptr [rax+8], 0
0x14002f097  mov     rbx, rcx
0x14002f09a  lea     rax, aNtquerysystemi; "NtQuerySystemInformation"
0x14002f0a1  mov     rdi, rdx
0x14002f0a4  lea     rcx, [rsp+58h+SystemRoutineName]; SystemRoutineName
0x14002f0a9  mov     [rsp+58h+SystemRoutineName.Buffer], rax
0x14002f0ae  call    cs:__imp_MmGetSystemRoutineAddress
0x14002f0b5  nop     dword ptr [rax+rax+00h]
0x14002f0ba  test    rax, rax
0x14002f0bd  jz      short loc_14002F0E7
0x14002f0bf  xor     r9d, r9d
0x14002f0c2  lea     rdx, [rsp+58h+arg_0]
0x14002f0c7  mov     ecx, 0E3h
0x14002f0cc  lea     r8d, [r9+1]
0x14002f0d0  call    _guard_dispatch_icall
0x14002f0d5  test    eax, eax
0x14002f0d7  js      short loc_14002F0E7
0x14002f0d9  cmp     [rsp+58h+arg_0], 0
0x14002f0de  jz      short loc_14002F0E7
0x14002f0e0  mov     cs:ExPoolZeroingNativelySupported, 1
0x14002f0e7  mov     cs:ExDefaultNonPagedPoolType, 200h
0x14002f0f1  lea     rax, USBC_Dispatch
0x14002f0f8  mov     cs:ExDefaultMdlProtection, 40000000h
0x14002f102  lea     rcx, USBC_AddDevice
0x14002f109  mov     [rbx+120h], rax
0x14002f110  mov     [rbx+148h], rax
0x14002f117  mov     [rbx+0E8h], rax
0x14002f11e  mov     [rbx+128h], rax
0x14002f125  mov     [rbx+0E0h], rax
0x14002f12c  mov     [rbx+80h], rax
0x14002f133  mov     [rbx+70h], rax
0x14002f137  lea     rax, USBC_DriverUnload
0x14002f13e  mov     [rbx+68h], rax
0x14002f142  mov     rax, [rbx+30h]
0x14002f146  mov     [rax+8], rcx
0x14002f14a  call    RegQueryGenericCompositeUSBDeviceString
0x14002f14f  call    wil_InitializeFeatureStaging
0x14002f154  lea     rax, WPP_ThisDir_CTLGUID_USBCCGP
0x14002f15b  mov     qword ptr cs:WPP_MAIN_CB.Type, 0
0x14002f166  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14002f16d  xor     eax, eax
0x14002f16f  mov     cs:WPP_MAIN_CB.DeviceType, eax
0x14002f175  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x14002f180  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14002f18b  mov     cs:WPP_MAIN_CB.Timer, 1
0x14002f196  mov     cs:WPP_MAIN_CB.DeviceExtension, 0
0x14002f1a1  call    WppLoadTracingSupport
0x14002f1a6  mov     rdx, rdi; __annotation("TMC:", "bc6c9364-fc67-42c5-acf7-abed3b12ecc6", "USBCCGP", "DBG_INIT", "DBG_PNP", "DBG_POWER", "DBG_URB", "DBG_IOCTL", "DBG_DEVICE_CONTROL", "DBG_IDLE", "DBG_ERROR", "DBG_IRP_LOG", "DebugFlag9", "DebugFlag10", "DebugFlag11", "DebugFlag12", "DebugFlag13", "DebugFlag14", "DebugFlag15", "DebugFlag16", "DebugFlag17", "DebugFlag18", "DebugFlag19", "DebugFlag20", "DebugFlag21", "DebugFlag22", "DebugFlag23", "DebugFlag24", "DebugFlag25", "DebugFlag26", "DebugFlag27", "DebugFlag28", "DebugFlag29", "DebugFlag30", "DebugFlag31", "PUBLIC_TMF:")
0x14002f1a9  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14002f1b4  mov     rcx, rbx
0x14002f1b7  call    WppInitKm
0x14002f1bc  call    AllocateDriverGlobalIFRLog
0x14002f1c1  mov     rdx, rdi
0x14002f1c4  call    USBC_WmiDriverEntry
0x14002f1c9  lea     rdx, aKsequerydevice; "KseQueryDeviceFlags"
0x14002f1d0  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x14002f1d5  call    cs:__imp_RtlInitUnicodeString
0x14002f1dc  nop     dword ptr [rax+rax+00h]
0x14002f1e1  lea     rcx, [rsp+58h+DestinationString]; SystemRoutineName
0x14002f1e6  call    cs:__imp_MmGetSystemRoutineAddress
0x14002f1ed  nop     dword ptr [rax+rax+00h]
0x14002f1f2  mov     rdx, rbx
0x14002f1f5  mov     cs:g_DriverObject, rbx
0x14002f1fc  lea     rcx, g_SleepstudyLibraryHandle
0x14002f203  mov     qword ptr cs:WPP_MAIN_CB.Queue, rax
0x14002f20a  call    cs:__imp_SleepstudyHelper_Initialize
0x14002f211  nop     dword ptr [rax+rax+00h]
0x14002f216  test    eax, eax
0x14002f218  jns     short loc_14002F254
0x14002f21a  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002f221  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002f228  jz      short loc_14002F252
0x14002f22a  mov     rcx, cs:g_RecorderLog
0x14002f231  mov     r9d, 0Eh
0x14002f237  mov     [rsp+58h+var_30], eax
0x14002f23b  mov     dl, 3
0x14002f23d  lea     rax, WPP_e84aa8ae2d9034c0d4fedfbc39bcd7a4_Traceguids
0x14002f244  mov     [rsp+58h+var_38], rax
0x14002f249  lea     r8d, [r9-6]
0x14002f24d  call    WPP_RECORDER_SF_d
0x14002f252  xor     eax, eax
0x14002f254  mov     rbx, [rsp+58h+arg_8]
0x14002f259  add     rsp, 50h
0x14002f25d  pop     rdi
0x14002f25e  retn
```
