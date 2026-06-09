# DriverEntry

- ea: `0x14005d078`
- end: `0x14005d349`
- name: `DriverEntry`
- size: `721`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x14005d010`

## callees

- `0x14001c080`
- `0x140038dd8`
- `0x140038e6c`
- `0x14003d288`
- `0x14005d078`
- `0x14005d4f4`
- `0x14005da18`

## import_xrefs

- `ntoskrnl!IoCreateDevice` at `0x14005d0f4`
- `ntoskrnl!IoCreateDevice` at `0x14005d140`
- `ntoskrnl!IoCreateDevice` at `0x14005d0f4`
- `ntoskrnl!IoCreateDevice` at `0x14005d140`
- `ntoskrnl!IoDeleteDevice` at `0x14005d2ce`
- `ntoskrnl!IoDeleteDevice` at `0x14005d2e3`
- `ntoskrnl!IoDeleteDevice` at `0x14005d2ce`
- `ntoskrnl!IoDeleteDevice` at `0x14005d2e3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005d0c9`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005d115`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005d0c9`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005d115`
- `ntoskrnl!FsRtlRegisterFileSystemFilterCallbacks` at `0x14005d1fd`
- `ntoskrnl!FsRtlRegisterFileSystemFilterCallbacks` at `0x14005d1fd`
- `ntoskrnl!IoRegisterFileSystem` at `0x14005d2a5`
- `ntoskrnl!IoRegisterFileSystem` at `0x14005d2b5`
- `ntoskrnl!IoRegisterFileSystem` at `0x14005d2a5`
- `ntoskrnl!IoRegisterFileSystem` at `0x14005d2b5`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14005d31a`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14005d31a`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14005d2fb`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14005d2fb`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int v3; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-49h] BYREF
  _FS_FILTER_CALLBACKS Callbacks; // [rsp+50h] [rbp-39h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+100h] [rbp+77h] BYREF
  PDEVICE_OBJECT v8; // [rsp+108h] [rbp+7Fh] BYREF

  DeviceObject = 0;
  v8 = 0;
  DestinationString = 0;
  memset(&Callbacks, 0, sizeof(Callbacks));
  v3 = wil_InitializeFeatureStaging();
  if ( v3 < 0 )
    goto LABEL_6;
  RtlInitUnicodeString(&DestinationString, L"\\UdfsCdRom");
  v3 = IoCreateDevice(DriverObject, 0, &DestinationString, 3u, 0, 0, &DeviceObject);
  if ( v3 < 0 )
    goto LABEL_6;
  RtlInitUnicodeString(&DestinationString, L"\\UdfsDisk");
  v3 = IoCreateDevice(DriverObject, 0, &DestinationString, 8u, 0, 0, &v8);
  if ( v3 < 0 )
    goto LABEL_6;
  DriverObject->MajorFunction[27] = (PDRIVER_DISPATCH)UdfFsdDispatch;
  DriverObject->MajorFunction[18] = (PDRIVER_DISPATCH)UdfFsdDispatch;
  DriverObject->MajorFunction[17] = (PDRIVER_DISPATCH)UdfFsdDispatch;
  DriverObject->MajorFunction[16] = (PDRIVER_DISPATCH)UdfFsdDispatch;
  DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)UdfFsdDispatch;
  DriverObject->MajorFunction[13] = (PDRIVER_DISPATCH)UdfFsdDispatch;
  DriverObject->MajorFunction[12] = (PDRIVER_DISPATCH)UdfFsdDispatch;
  DriverObject->MajorFunction[11] = (PDRIVER_DISPATCH)UdfFsdDispatch;
  DriverObject->MajorFunction[10] = (PDRIVER_DISPATCH)UdfFsdDispatch;
  DriverObject->MajorFunction[9] = (PDRIVER_DISPATCH)UdfFsdDispatch;
  DriverObject->MajorFunction[6] = (PDRIVER_DISPATCH)UdfFsdDispatch;
  DriverObject->MajorFunction[5] = (PDRIVER_DISPATCH)UdfFsdDispatch;
  DriverObject->MajorFunction[4] = (PDRIVER_DISPATCH)UdfFsdDispatch;
  DriverObject->MajorFunction[3] = (PDRIVER_DISPATCH)UdfFsdDispatch;
  DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)UdfFsdDispatch;
  DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)UdfFsdDispatch;
  DriverObject->FastIoDispatch = (PFAST_IO_DISPATCH)&WPP_MAIN_CB.DeviceExtension;
  memset(&Callbacks, 0, sizeof(Callbacks));
  Callbacks.SizeOfFsFilterCallbacks = 120;
  Callbacks.PreAcquireForSectionSynchronization = (PFS_FILTER_CALLBACK)UdfFilterCallbackAcquireForCreateSection;
  v3 = FsRtlRegisterFileSystemFilterCallbacks(DriverObject, &Callbacks);
  if ( v3 < 0 )
  {
LABEL_6:
    if ( DeviceObject )
      IoDeleteDevice(DeviceObject);
    if ( v8 )
      IoDeleteDevice(v8);
    if ( g_wil_details_featureChangeNotification )
    {
      RtlUnregisterFeatureConfigurationChangeNotification();
      g_wil_details_featureChangeNotification = 0;
    }
    if ( g_wil_details_featureUsageProvider )
    {
      RtlUnregisterFeatureUsageProvider();
      g_wil_details_featureUsageProvider = 0;
    }
    g_wil_details_isFeatureStagingInitialized = 0;
    return v3;
  }
  else
  {
    UdfInitializeGlobalData(DriverObject, DeviceObject, v8);
    *(_QWORD *)&WPP_MAIN_CB.Type = 0;
    WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_Udfs;
    WPP_MAIN_CB.NextDevice = 0;
    WPP_MAIN_CB.CurrentIrp = 0;
    WPP_MAIN_CB.Timer = (PIO_TIMER)1;
    WppLoadTracingSupport();
    WPP_MAIN_CB.CurrentIrp = 0;
    WppInitKm();
    memset(&WPP_MAIN_CB.Reserved, 0, 0x68u);
    *((_QWORD *)&WPP_MAIN_CB.Reserved + 1) = MEMORY[0xFFFFF78000000014];
    qword_140025A90 = MEMORY[0xFFFFF78000000320];
    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation();
    IoRegisterFileSystem(DeviceObject);
    IoRegisterFileSystem(v8);
    return 0;
  }
}

```

## disassembly

```asm
0x14005d078  mov     [rsp-8+arg_0], rbx
0x14005d07d  push    rbp
0x14005d07e  push    rsi
0x14005d07f  push    rdi
0x14005d080  lea     rbp, [rsp-47h]
0x14005d085  sub     rsp, 0D0h
0x14005d08c  xor     esi, esi
0x14005d08e  mov     rdi, rcx
0x14005d091  xorps   xmm0, xmm0
0x14005d094  mov     [rbp+57h+arg_10], rsi
0x14005d098  xor     edx, edx; Val
0x14005d09a  mov     [rbp+57h+arg_18], rsi
0x14005d09e  lea     rcx, [rbp+57h+Callbacks]; void *
0x14005d0a2  lea     r8d, [rsi+78h]; Size
0x14005d0a6  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14005d0aa  call    memset
0x14005d0af  call    wil_InitializeFeatureStaging
0x14005d0b4  mov     ebx, eax
0x14005d0b6  test    eax, eax
0x14005d0b8  js      loc_14005D2C5
0x14005d0be  lea     rdx, aUdfscdrom; "\\UdfsCdRom"
0x14005d0c5  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14005d0c9  call    cs:__imp_RtlInitUnicodeString
0x14005d0d0  nop     dword ptr [rax+rax+00h]
0x14005d0d5  lea     rax, [rbp+57h+arg_10]
0x14005d0d9  xor     edx, edx; DeviceExtensionSize
0x14005d0db  mov     [rsp+0E0h+DeviceObject], rax; DeviceObject
0x14005d0e0  lea     r9d, [rsi+3]; DeviceType
0x14005d0e4  mov     [rsp+0E0h+Exclusive], sil; Exclusive
0x14005d0e9  lea     r8, [rbp+57h+DestinationString]; DeviceName
0x14005d0ed  mov     rcx, rdi; DriverObject
0x14005d0f0  mov     [rsp+0E0h+DeviceCharacteristics], esi; DeviceCharacteristics
0x14005d0f4  call    cs:__imp_IoCreateDevice
0x14005d0fb  nop     dword ptr [rax+rax+00h]
0x14005d100  mov     ebx, eax
0x14005d102  test    eax, eax
0x14005d104  js      loc_14005D2C5
0x14005d10a  lea     rdx, aUdfsdisk; "\\UdfsDisk"
0x14005d111  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14005d115  call    cs:__imp_RtlInitUnicodeString
0x14005d11c  nop     dword ptr [rax+rax+00h]
0x14005d121  lea     rax, [rbp+57h+arg_18]
0x14005d125  xor     edx, edx; DeviceExtensionSize
0x14005d127  mov     [rsp+0E0h+DeviceObject], rax; DeviceObject
0x14005d12c  lea     r9d, [rsi+8]; DeviceType
0x14005d130  mov     [rsp+0E0h+Exclusive], sil; Exclusive
0x14005d135  lea     r8, [rbp+57h+DestinationString]; DeviceName
0x14005d139  mov     rcx, rdi; DriverObject
0x14005d13c  mov     [rsp+0E0h+DeviceCharacteristics], esi; DeviceCharacteristics
0x14005d140  call    cs:__imp_IoCreateDevice
0x14005d147  nop     dword ptr [rax+rax+00h]
0x14005d14c  mov     ebx, eax
0x14005d14e  test    eax, eax
0x14005d150  js      loc_14005D2C5
0x14005d156  lea     rax, UdfFsdDispatch
0x14005d15d  xor     edx, edx; Val
0x14005d15f  mov     [rdi+148h], rax
0x14005d166  lea     r8d, [rsi+78h]; Size
0x14005d16a  mov     [rdi+100h], rax
0x14005d171  lea     rcx, [rbp+57h+Callbacks]; void *
0x14005d175  mov     [rdi+0F8h], rax
0x14005d17c  mov     [rdi+0F0h], rax
0x14005d183  mov     [rdi+0E0h], rax
0x14005d18a  mov     [rdi+0D8h], rax
0x14005d191  mov     [rdi+0D0h], rax
0x14005d198  mov     [rdi+0C8h], rax
0x14005d19f  mov     [rdi+0C0h], rax
0x14005d1a6  mov     [rdi+0B8h], rax
0x14005d1ad  mov     [rdi+0A0h], rax
0x14005d1b4  mov     [rdi+98h], rax
0x14005d1bb  mov     [rdi+90h], rax
0x14005d1c2  mov     [rdi+88h], rax
0x14005d1c9  mov     [rdi+80h], rax
0x14005d1d0  mov     [rdi+70h], rax
0x14005d1d4  lea     rax, WPP_MAIN_CB.DeviceExtension
0x14005d1db  mov     [rdi+50h], rax
0x14005d1df  call    memset
0x14005d1e4  lea     rax, UdfFilterCallbackAcquireForCreateSection
0x14005d1eb  mov     [rbp+57h+Callbacks.SizeOfFsFilterCallbacks], 78h ; 'x'
0x14005d1f2  lea     rdx, [rbp+57h+Callbacks]; Callbacks
0x14005d1f6  mov     [rbp+57h+Callbacks.PreAcquireForSectionSynchronization], rax
0x14005d1fa  mov     rcx, rdi; FilterDriverObject
0x14005d1fd  call    cs:__imp_FsRtlRegisterFileSystemFilterCallbacks
0x14005d204  nop     dword ptr [rax+rax+00h]
0x14005d209  mov     ebx, eax
0x14005d20b  test    eax, eax
0x14005d20d  js      loc_14005D2C5
0x14005d213  mov     r8, [rbp+57h+arg_18]
0x14005d217  mov     rcx, rdi
0x14005d21a  mov     rdx, [rbp+57h+arg_10]
0x14005d21e  call    UdfInitializeGlobalData
0x14005d223  lea     rax, WPP_ThisDir_CTLGUID_Udfs
0x14005d22a  mov     qword ptr cs:WPP_MAIN_CB.Type, rsi
0x14005d231  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14005d238  mov     cs:WPP_MAIN_CB.NextDevice, rsi
0x14005d23f  mov     cs:WPP_MAIN_CB.CurrentIrp, rsi
0x14005d246  mov     cs:WPP_MAIN_CB.Timer, 1
0x14005d251  call    WppLoadTracingSupport
0x14005d256  mov     cs:WPP_MAIN_CB.CurrentIrp, rsi
0x14005d25d  call    WppInitKm
0x14005d262  xor     edx, edx; Val
0x14005d264  lea     r8d, [rsi+68h]; Size
0x14005d268  lea     rcx, WPP_MAIN_CB.Reserved; void *
0x14005d26f  call    memset
0x14005d274  mov     rax, 0FFFFF78000000014h
0x14005d27e  mov     rax, [rax]
0x14005d281  mov     qword ptr cs:WPP_MAIN_CB+148h, rax
0x14005d288  mov     rax, 0FFFFF78000000320h
0x14005d292  mov     rax, [rax]
0x14005d295  mov     cs:qword_140025A90, rax
0x14005d29c  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x14005d2a1  mov     rcx, [rbp+57h+arg_10]; DeviceObject
0x14005d2a5  call    cs:__imp_IoRegisterFileSystem
0x14005d2ac  nop     dword ptr [rax+rax+00h]
0x14005d2b1  mov     rcx, [rbp+57h+arg_18]; DeviceObject
0x14005d2b5  call    cs:__imp_IoRegisterFileSystem
0x14005d2bc  nop     dword ptr [rax+rax+00h]
0x14005d2c1  xor     eax, eax
0x14005d2c3  jmp     short loc_14005D335
0x14005d2c5  mov     rcx, [rbp+57h+arg_10]; DeviceObject
0x14005d2c9  test    rcx, rcx
0x14005d2cc  jz      short loc_14005D2DA
0x14005d2ce  call    cs:__imp_IoDeleteDevice
0x14005d2d5  nop     dword ptr [rax+rax+00h]
0x14005d2da  mov     rcx, [rbp+57h+arg_18]; DeviceObject
0x14005d2de  test    rcx, rcx
0x14005d2e1  jz      short loc_14005D2EF
0x14005d2e3  call    cs:__imp_IoDeleteDevice
0x14005d2ea  nop     dword ptr [rax+rax+00h]
0x14005d2ef  mov     rcx, cs:g_wil_details_featureChangeNotification
0x14005d2f6  test    rcx, rcx
0x14005d2f9  jz      short loc_14005D30E
0x14005d2fb  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x14005d302  nop     dword ptr [rax+rax+00h]
0x14005d307  mov     cs:g_wil_details_featureChangeNotification, rsi
0x14005d30e  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14005d315  test    rcx, rcx
0x14005d318  jz      short loc_14005D32D
0x14005d31a  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14005d321  nop     dword ptr [rax+rax+00h]
0x14005d326  mov     cs:g_wil_details_featureUsageProvider, rsi
0x14005d32d  mov     cs:g_wil_details_isFeatureStagingInitialized, esi
0x14005d333  mov     eax, ebx
0x14005d335  mov     rbx, [rsp+0E0h+arg_0]
0x14005d33d  add     rsp, 0D0h
0x14005d344  pop     rdi
0x14005d345  pop     rsi
0x14005d346  pop     rbp
0x14005d347  retn
```
