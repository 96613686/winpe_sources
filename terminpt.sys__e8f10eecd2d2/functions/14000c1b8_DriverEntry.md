# DriverEntry

- ea: `0x14000c1b8`
- end: `0x14000c49f`
- name: `DriverEntry`
- size: `743`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, registry_config, loader_planting, installer_update`

## callers

- `0x14000c010`

## callees

- `0x14000173c`
- `0x1400017e8`
- `0x140003500`
- `0x14000a500`
- `0x14000a708`
- `0x14000a7d0`
- `0x14000c078`
- `0x14000c1b8`

## import_xrefs

- `ntoskrnl!KeInitializeGuardedMutex` at `0x14000c28e`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x14000c28e`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14000c3f5`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14000c3f5`
- `ntoskrnl!IoCreateDevice` at `0x14000c371`
- `ntoskrnl!IoCreateDevice` at `0x14000c371`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c33c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c3dd`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c415`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c33c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c3dd`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c415`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int v4; // edx
  int v5; // r8d
  int v6; // edx
  int v7; // ebx
  int v8; // r8d
  __int64 v9; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-38h] BYREF

  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_CtlGuid;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.DeviceType = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  DestinationString = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WPP_MAIN_CB.DeviceExtension = 0;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm(DriverObject, RegistryPath);
  BYTE1(WPP_MAIN_CB.Dpc.DpcData) = 1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      v5,
      10,
      (__int64)WPP_a22c8264ce0a30878b50f65ec3447f16_Traceguids);
  memset(&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels, 0, 0xB8u);
  KeInitializeGuardedMutex((PKGUARDED_MUTEX)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink);
  WPP_MAIN_CB.Dpc.SystemArgument1 = &WPP_MAIN_CB.Dpc.DeferredContext;
  WPP_MAIN_CB.Dpc.DeferredContext = &WPP_MAIN_CB.Dpc.DeferredContext;
  DriverObject->FastIoDispatch = 0;
  DriverObject->DriverUnload = (PDRIVER_UNLOAD)TiUnload;
  DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)TiCreate;
  DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&TiClose;
  DriverObject->MajorFunction[15] = (PDRIVER_DISPATCH)PtInternalDeviceControl;
  DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)TiDeviceControl;
  DriverObject->MajorFunction[27] = (PDRIVER_DISPATCH)PtPnP;
  DriverObject->MajorFunction[22] = (PDRIVER_DISPATCH)PtPower;
  DriverObject->MajorFunction[23] = (PDRIVER_DISPATCH)PtSystemControl;
  DriverObject->DriverExtension->AddDevice = (PDRIVER_ADD_DEVICE)PtAddDevice;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\TermInptCDO");
  v7 = IoCreateDevice(
         DriverObject,
         0,
         &DestinationString,
         0x38u,
         0,
         0,
         (PDEVICE_OBJECT *)&WPP_MAIN_CB.Dpc.SystemArgument2);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sD(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      v8,
      11,
      (__int64)WPP_a22c8264ce0a30878b50f65ec3447f16_Traceguids);
  if ( v7 < 0 )
    goto LABEL_10;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      v8,
      12,
      (__int64)WPP_a22c8264ce0a30878b50f65ec3447f16_Traceguids);
  RtlInitUnicodeString((PUNICODE_STRING)&WPP_MAIN_CB.ActiveThreadCount, L"\\DosDevices\\TermInptCDO");
  v7 = IoCreateSymbolicLink((PUNICODE_STRING)&WPP_MAIN_CB.ActiveThreadCount, &DestinationString);
  if ( v7 < 0 )
  {
    RtlInitUnicodeString((PUNICODE_STRING)&WPP_MAIN_CB.ActiveThreadCount, &word_1400052E8);
LABEL_10:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        v8,
        14,
        (__int64)WPP_a22c8264ce0a30878b50f65ec3447f16_Traceguids);
    TiUnload(DriverObject);
    return v7;
  }
  v7 = PtEntry(v9, RegistryPath);
  if ( v7 < 0 )
    goto LABEL_10;
  LOBYTE(WPP_MAIN_CB.Dpc.DpcData) = 1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sD(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      v8,
      13,
      (__int64)WPP_a22c8264ce0a30878b50f65ec3447f16_Traceguids);
  return v7;
}

```

## disassembly

```asm
0x14000c1b8  push    rbx
0x14000c1ba  push    rsi
0x14000c1bb  push    rdi
0x14000c1bc  push    r14
0x14000c1be  push    r15
0x14000c1c0  sub     rsp, 50h
0x14000c1c4  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x14000c1cb  mov     qword ptr cs:WPP_MAIN_CB.Type, 0
0x14000c1d6  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14000c1dd  xorps   xmm0, xmm0
0x14000c1e0  xor     eax, eax
0x14000c1e2  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x14000c1ed  mov     cs:WPP_MAIN_CB.DeviceType, eax
0x14000c1f3  mov     rsi, rdx
0x14000c1f6  mov     rdi, rcx
0x14000c1f9  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14000c204  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x14000c209  mov     cs:WPP_MAIN_CB.Timer, 1
0x14000c214  mov     cs:WPP_MAIN_CB.DeviceExtension, 0
0x14000c21f  call    WppLoadTracingSupport
0x14000c224  mov     rdx, rsi
0x14000c227  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14000c232  mov     rcx, rdi
0x14000c235  call    WppInitKm
0x14000c23a  mov     byte ptr cs:WPP_MAIN_CB.Dpc.DpcData+1, 1
0x14000c241  lea     r15, WPP_RECORDER_INITIALIZED
0x14000c248  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000c24f  lea     r14, WPP_a22c8264ce0a30878b50f65ec3447f16_Traceguids
0x14000c256  jz      short loc_14000C273
0x14000c258  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c25f  mov     r9d, 0Ah
0x14000c265  mov     qword ptr [rsp+78h+DeviceCharacteristics], r14
0x14000c26a  mov     rcx, [rcx+40h]
0x14000c26e  call    WPP_RECORDER_SF_s
0x14000c273  xor     edx, edx; Val
0x14000c275  lea     rcx, WPP_MAIN_CB.Queue+10h; void *
0x14000c27c  mov     r8d, 0B8h; Size
0x14000c282  call    memset
0x14000c287  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink; Mutex
0x14000c28e  call    cs:__imp_KeInitializeGuardedMutex
0x14000c295  nop     dword ptr [rax+rax+00h]
0x14000c29a  lea     rax, WPP_MAIN_CB.Dpc.DeferredContext
0x14000c2a1  mov     cs:WPP_MAIN_CB.Dpc.SystemArgument1, rax
0x14000c2a8  lea     rcx, PtAddDevice
0x14000c2af  mov     cs:WPP_MAIN_CB.Dpc.DeferredContext, rax
0x14000c2b6  lea     rdx, aDeviceTerminpt; "\\Device\\TermInptCDO"
0x14000c2bd  lea     rax, TiUnload
0x14000c2c4  mov     qword ptr [rdi+50h], 0
0x14000c2cc  mov     [rdi+68h], rax
0x14000c2d0  lea     rax, TiCreate
0x14000c2d7  mov     [rdi+70h], rax
0x14000c2db  lea     rax, TiClose
0x14000c2e2  mov     [rdi+80h], rax
0x14000c2e9  lea     rax, PtInternalDeviceControl
0x14000c2f0  mov     [rdi+0E8h], rax
0x14000c2f7  lea     rax, TiDeviceControl
0x14000c2fe  mov     [rdi+0E0h], rax
0x14000c305  lea     rax, PtPnP
0x14000c30c  mov     [rdi+148h], rax
0x14000c313  lea     rax, PtPower
0x14000c31a  mov     [rdi+120h], rax
0x14000c321  lea     rax, PtSystemControl
0x14000c328  mov     [rdi+128h], rax
0x14000c32f  mov     rax, [rdi+30h]
0x14000c333  mov     [rax+8], rcx
0x14000c337  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x14000c33c  call    cs:__imp_RtlInitUnicodeString
0x14000c343  nop     dword ptr [rax+rax+00h]
0x14000c348  lea     rax, WPP_MAIN_CB.Dpc.SystemArgument2
0x14000c34f  mov     r9d, 38h ; '8'; DeviceType
0x14000c355  mov     [rsp+78h+DeviceObject], rax; DeviceObject
0x14000c35a  lea     r8, [rsp+78h+DestinationString]; DeviceName
0x14000c35f  mov     [rsp+78h+Exclusive], 0; Exclusive
0x14000c364  xor     edx, edx; DeviceExtensionSize
0x14000c366  mov     rcx, rdi; DriverObject
0x14000c369  mov     [rsp+78h+DeviceCharacteristics], 0; DeviceCharacteristics
0x14000c371  call    cs:__imp_IoCreateDevice
0x14000c378  nop     dword ptr [rax+rax+00h]
0x14000c37d  mov     ebx, eax
0x14000c37f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000c386  jz      short loc_14000C3A7
0x14000c388  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c38f  mov     r9d, 0Bh
0x14000c395  mov     dword ptr [rsp+78h+DeviceObject], eax
0x14000c399  mov     qword ptr [rsp+78h+DeviceCharacteristics], r14
0x14000c39e  mov     rcx, [rcx+40h]
0x14000c3a2  call    WPP_RECORDER_SF_sD
0x14000c3a7  test    ebx, ebx
0x14000c3a9  js      short loc_14000C421
0x14000c3ab  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000c3b2  jz      short loc_14000C3CF
0x14000c3b4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c3bb  mov     r9d, 0Ch
0x14000c3c1  mov     qword ptr [rsp+78h+DeviceCharacteristics], r14
0x14000c3c6  mov     rcx, [rcx+40h]
0x14000c3ca  call    WPP_RECORDER_SF_s
0x14000c3cf  lea     rdx, aDosdevicesTerm; "\\DosDevices\\TermInptCDO"
0x14000c3d6  lea     rcx, WPP_MAIN_CB.ActiveThreadCount; DestinationString
0x14000c3dd  call    cs:__imp_RtlInitUnicodeString
0x14000c3e4  nop     dword ptr [rax+rax+00h]
0x14000c3e9  lea     rdx, [rsp+78h+DestinationString]; DeviceName
0x14000c3ee  lea     rcx, WPP_MAIN_CB.ActiveThreadCount; SymbolicLinkName
0x14000c3f5  call    cs:__imp_IoCreateSymbolicLink
0x14000c3fc  nop     dword ptr [rax+rax+00h]
0x14000c401  mov     ebx, eax
0x14000c403  test    eax, eax
0x14000c405  jns     short loc_14000C460
0x14000c407  lea     rdx, word_1400052E8; SourceString
0x14000c40e  lea     rcx, WPP_MAIN_CB.ActiveThreadCount; DestinationString
0x14000c415  call    cs:__imp_RtlInitUnicodeString
0x14000c41c  nop     dword ptr [rax+rax+00h]
0x14000c421  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000c428  jz      short loc_14000C449
0x14000c42a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c431  mov     r9d, 0Eh
0x14000c437  mov     dword ptr [rsp+78h+DeviceObject], ebx
0x14000c43b  mov     qword ptr [rsp+78h+DeviceCharacteristics], r14
0x14000c440  mov     rcx, [rcx+40h]
0x14000c444  call    WPP_RECORDER_SF_sD
0x14000c449  mov     rcx, rdi
0x14000c44c  call    TiUnload
0x14000c451  mov     eax, ebx
0x14000c453  add     rsp, 50h
0x14000c457  pop     r15
0x14000c459  pop     r14
0x14000c45b  pop     rdi
0x14000c45c  pop     rsi
0x14000c45d  pop     rbx
0x14000c45e  retn
0x14000c460  mov     rdx, rsi
0x14000c463  call    PtEntry
0x14000c468  mov     ebx, eax
0x14000c46a  test    eax, eax
0x14000c46c  js      short loc_14000C421
0x14000c46e  mov     byte ptr cs:WPP_MAIN_CB.Dpc.DpcData, 1
0x14000c475  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000c47c  jz      short loc_14000C451
0x14000c47e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c485  mov     r9d, 0Dh
0x14000c48b  mov     dword ptr [rsp+78h+DeviceObject], eax
0x14000c48f  mov     qword ptr [rsp+78h+DeviceCharacteristics], r14
0x14000c494  mov     rcx, [rcx+40h]
0x14000c498  call    WPP_RECORDER_SF_sD
0x14000c49d  jmp     short loc_14000C451
```
