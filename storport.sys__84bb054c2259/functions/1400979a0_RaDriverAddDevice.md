# RaDriverAddDevice

- ea: `0x1400979a0`
- end: `0x140097eff`
- name: `RaDriverAddDevice`
- size: `1375`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT DeviceObject)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140046b20`
- `0x140047a18`
- `0x140047f20`
- `0x140051204`
- `0x140067bc0`
- `0x140091870`
- `0x140093dc0`
- `0x1400978c4`
- `0x1400979a0`
- `0x14009c38c`
- `0x1400baa40`
- `0x1400f327c`
- `0x1400f33e0`
- `0x14018704c`
- `0x140187594`
- `0x14018f540`
- `0x14019e95c`
- `0x1401bdbe8`
- `0x1401c0368`

## import_xrefs

- `ntoskrnl!IoDetachDevice` at `0x140097e12`
- `ntoskrnl!IoDetachDevice` at `0x140097e12`
- `ntoskrnl!RtlInitUnicodeString` at `0x140097b4e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140097b65`
- `ntoskrnl!RtlInitUnicodeString` at `0x140097be7`
- `ntoskrnl!RtlInitUnicodeString` at `0x140097bfe`
- `ntoskrnl!RtlInitUnicodeString` at `0x140097c59`
- `ntoskrnl!RtlInitUnicodeString` at `0x140097c70`
- `ntoskrnl!RtlInitUnicodeString` at `0x140097b4e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140097b65`
- `ntoskrnl!RtlInitUnicodeString` at `0x140097be7`
- `ntoskrnl!RtlInitUnicodeString` at `0x140097bfe`
- `ntoskrnl!RtlInitUnicodeString` at `0x140097c59`
- `ntoskrnl!RtlInitUnicodeString` at `0x140097c70`
- `ntoskrnl!IoDeleteDevice` at `0x140097d77`
- `ntoskrnl!IoDeleteDevice` at `0x140097d77`
- `ntoskrnl!ExFreePoolWithTag` at `0x140097ed5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140097ed5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140097e52`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140097e52`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140097a5e`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140097a5e`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x140097da5`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x140097da5`
- `ntoskrnl!IoCreateDevice` at `0x140097d08`
- `ntoskrnl!IoCreateDevice` at `0x140097d08`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140097e9e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140097e9e`

## pseudocode

```c
__int64 __fastcall RaDriverAddDevice(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT DeviceObject)
{
  _QWORD *v4; // r14
  char *DeviceExtension; // r15
  unsigned int v6; // esi
  __int64 v7; // rbx
  unsigned int BusInterface; // eax
  __int64 v9; // rdx
  __int64 DriverInitData; // rdi
  __int64 v11; // rdx
  int v12; // r12d
  bool v13; // bl
  ULONG v14; // edx
  NTSTATUS NvmeAdapter; // edi
  __int64 v16; // r8
  PDEVICE_OBJECT v17; // rax
  struct _DEVICE_OBJECT *v18; // rsi
  __int64 v19; // r13
  int v20; // eax
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  _QWORD *v23; // rax
  _QWORD *v24; // rax
  struct _DEVICE_OBJECT *DeviceCharacteristics; // [rsp+20h] [rbp-79h]
  PDEVICE_OBJECT SourceDevice; // [rsp+40h] [rbp-59h] BYREF
  int v28; // [rsp+48h] [rbp-51h] BYREF
  __int64 v29; // [rsp+50h] [rbp-49h] BYREF
  int v30; // [rsp+58h] [rbp-41h] BYREF
  int v31; // [rsp+5Ch] [rbp-3Dh] BYREF
  int v32; // [rsp+60h] [rbp-39h] BYREF
  BOOL v33; // [rsp+64h] [rbp-35h] BYREF
  struct _UNICODE_STRING DeviceName; // [rsp+68h] [rbp-31h] BYREF
  struct _UNICODE_STRING v35; // [rsp+78h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-11h] BYREF
  int v37[2]; // [rsp+98h] [rbp-1h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+A0h] [rbp+7h] BYREF
  char v40; // [rsp+110h] [rbp+77h]
  int KeyHandle; // [rsp+118h] [rbp+7Fh] BYREF

  LODWORD(v29) = 0;
  v30 = 0;
  SourceDevice = 0;
  v4 = 0;
  v28 = 0;
  DeviceExtension = 0;
  v31 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v32 = 0;
  DeviceName = 0;
  v33 = 0;
  DestinationString = 0;
  v40 = 0;
  v35 = 0;
  v6 = 2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(
      WPP_GLOBAL_Control->AttachedDevice,
      11,
      WPP_61bd6e0e791f31e2ffa75bd9431aea96_Traceguids,
      DriverObject,
      DeviceObject);
  }
  DeviceName = 0;
  *(_QWORD *)v37 = IoGetDriverObjectExtension(DriverObject, DriverEntry);
  v7 = *(_QWORD *)v37;
  RaidCreateDeviceName(DeviceObject, &DeviceName, &v28);
  BusInterface = RaGetBusInterface(DeviceObject);
  v9 = 0;
  if ( BusInterface != -1 )
    v9 = BusInterface;
  DriverInitData = RaFindDriverInitData(v7, v9);
  LOBYTE(KeyHandle) = PortReadStorageBusType(v7 + 40, 0, &v29);
  if ( (unsigned __int8)StorIsChildAdapterPdo(DeviceObject)
    && (LOBYTE(v11) = 1, (unsigned __int8)PortReadStorageBusType(v7 + 40, v11, &v30) == 1) )
  {
    v12 = v30;
  }
  else
  {
    v12 = v29;
    if ( !(_BYTE)KeyHandle )
      v12 = 127;
  }
  if ( v12 == 20 )
  {
    v13 = 1;
    goto LABEL_30;
  }
  v13 = 0;
  if ( v12 == 17 )
  {
    if ( DisableNativeNVMeStack )
      goto LABEL_36;
    if ( DriverInitData && (*(_DWORD *)(DriverInitData + 184) & 0x40000000) != 0 )
    {
      if ( g_OSisClient )
        v13 = (unsigned int)Feature_NativeNVMeStackEnableForClientOS__private_IsEnabledDeviceUsageNoInline() != 0;
      else
        v13 = 1;
    }
    RtlInitUnicodeString(&DestinationString, L"StorPort");
    RtlInitUnicodeString(&v35, L"EnableNVMeInterface");
    v29 = (__int64)&v31;
    KeyHandle = 4;
    if ( (int)PortRegistryReadDeviceKey(
                (int)DeviceObject,
                (int)&DestinationString,
                (int)&v35,
                4,
                (__int64)&v29,
                &KeyHandle) < 0 )
    {
      if ( !v13 )
        goto LABEL_30;
    }
    else
    {
      if ( !v31 )
      {
LABEL_27:
        v13 = 0;
        goto LABEL_30;
      }
      v13 = 1;
    }
    if ( !DriverInitData || (*(_DWORD *)(DriverInitData + 184) & 0x40000000) != 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"StorPort");
      RtlInitUnicodeString(&v35, L"DMArSupport");
      v29 = (__int64)&v32;
      KeyHandle = 4;
      if ( (int)PortRegistryReadDeviceKey(
                  (int)DeviceObject,
                  (int)&DestinationString,
                  (int)&v35,
                  4,
                  (__int64)&v29,
                  &KeyHandle) >= 0 )
      {
        v33 = v32 != 0;
        RtlInitUnicodeString(&DestinationString, L"DMA Management");
        RtlInitUnicodeString(&v35, L"RemappingSupported");
        PortRegistryWriteDeviceKey(
          (_DWORD)DeviceObject,
          (unsigned int)&DestinationString,
          (unsigned int)&v35,
          4,
          (__int64)&v33,
          4);
      }
      goto LABEL_30;
    }
    goto LABEL_27;
  }
LABEL_30:
  if ( !DisableNativeNVMeStack && DriverInitData && (*(_DWORD *)(DriverInitData + 184) & 0x40000) != 0 )
  {
    v13 = 1;
    v40 = 1;
LABEL_35:
    v14 = 1504;
    goto LABEL_37;
  }
  if ( v13 )
    goto LABEL_35;
LABEL_36:
  v14 = 48 * g_RaidLogListSize + 6464;
LABEL_37:
  NvmeAdapter = IoCreateDevice(DriverObject, v14, &DeviceName, 4u, 0x100u, 0, &SourceDevice);
  if ( NvmeAdapter < 0 )
    goto LABEL_56;
  if ( v13 )
  {
    LOBYTE(v16) = v40;
    DeviceExtension = (char *)SourceDevice->DeviceExtension;
    NvmeAdapter = CreateNvmeAdapter(DeviceExtension, SourceDevice, v16);
    if ( NvmeAdapter < 0 )
    {
      v6 = 3;
      goto LABEL_57;
    }
  }
  else
  {
    v4 = SourceDevice->DeviceExtension;
    NvmeAdapter = RaidCreateAdapter(v4);
    if ( NvmeAdapter < 0 )
    {
      v6 = 4;
      goto LABEL_43;
    }
  }
  v17 = IoAttachDeviceToDeviceStack(SourceDevice, DeviceObject);
  v18 = v17;
  if ( !v17 )
  {
    NvmeAdapter = -1073741823;
    v6 = 5;
    goto LABEL_56;
  }
  DeviceCharacteristics = DeviceObject;
  v19 = *(_QWORD *)v37;
  if ( v13 )
    v20 = InitializeNvmeAdapter(
            (int)DeviceExtension,
            (int)SourceDevice,
            v37[0],
            (int)v17,
            DeviceCharacteristics,
            (__int64)&DeviceName,
            v28,
            v12);
  else
    v20 = RaidInitializeAdapter(v4, DeviceCharacteristics, (__int64)&DeviceName, v28, v12);
  DeviceName.Buffer = 0;
  NvmeAdapter = v20;
  if ( v20 < 0 )
  {
    IoDetachDevice(v18);
    v6 = 6;
LABEL_56:
    if ( v13 )
    {
LABEL_57:
      if ( DeviceExtension )
        DeleteNvmeAdapter((__int64)DeviceExtension);
LABEL_45:
      if ( SourceDevice )
        IoDeleteDevice(SourceDevice);
      if ( !BootCompleted )
        StorpLogBootError(v6, (unsigned int)NvmeAdapter);
      goto LABEL_68;
    }
LABEL_43:
    if ( v4 )
      RaidDeleteAdapter(v4);
    goto LABEL_45;
  }
  StorGetNvmeVirtualizationSupport(SourceDevice);
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v19 + 80), &LockHandle);
  v21 = (_QWORD *)(v19 + 56);
  v22 = *(_QWORD *)(v19 + 56);
  v23 = *(_QWORD **)(v22 + 8);
  if ( !v13 )
  {
    if ( v23 == v21 )
    {
      v24 = v4 + 8;
      goto LABEL_65;
    }
LABEL_63:
    __fastfail(3u);
  }
  if ( v23 != v21 )
    goto LABEL_63;
  v24 = DeviceExtension + 64;
LABEL_65:
  v24[1] = v21;
  *v24 = v22;
  *(_QWORD *)(v22 + 8) = v24;
  *v21 = v24;
  ++*(_DWORD *)(v19 + 72);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( !v13 )
    RaidAdapterHack(v4);
  SourceDevice->Flags |= 0x10u;
  SourceDevice->Flags &= ~0x80u;
LABEL_68:
  if ( DeviceName.Buffer )
    ExFreePoolWithTag(DeviceName.Buffer, 0x53446152u);
  return (unsigned int)NvmeAdapter;
}

```

## disassembly

```asm
0x1400979a0  mov     [rsp-8+arg_8], rbx
0x1400979a5  mov     [rsp-8+DriverObject], rcx
0x1400979aa  push    rbp
0x1400979ab  push    rsi
0x1400979ac  push    rdi
0x1400979ad  push    r12
0x1400979af  push    r13
0x1400979b1  push    r14
0x1400979b3  push    r15
0x1400979b5  lea     rbp, [rsp-27h]
0x1400979ba  sub     rsp, 0C0h
0x1400979c1  xor     r12d, r12d
0x1400979c4  xorps   xmm0, xmm0
0x1400979c7  xor     eax, eax
0x1400979c9  mov     dword ptr [rbp+57h+var_A0], r12d
0x1400979cd  xorps   xmm1, xmm1
0x1400979d0  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x1400979d4  mov     r13, rdx
0x1400979d7  mov     [rbp+57h+var_98], r12d
0x1400979db  mov     rbx, rcx
0x1400979de  mov     [rbp+57h+SourceDevice], r12
0x1400979e2  mov     r14d, r12d
0x1400979e5  mov     [rbp+57h+var_A8], r12d
0x1400979e9  mov     r15d, r12d
0x1400979ec  mov     [rbp+57h+var_94], r12d
0x1400979f0  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x1400979f4  mov     [rbp+57h+var_90], r12d
0x1400979f8  movups  xmmword ptr [rbp+57h+DeviceName.Length], xmm0
0x1400979fc  mov     [rbp+57h+var_8C], r12d
0x140097a00  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x140097a04  mov     [rbp+57h+arg_10], r12b
0x140097a08  movups  xmmword ptr [rbp+57h+var_78.Length], xmm0
0x140097a0c  mov     rcx, cs:WPP_GLOBAL_Control
0x140097a13  lea     rax, WPP_GLOBAL_Control
0x140097a1a  lea     esi, [r12+2]
0x140097a1f  cmp     rcx, rax
0x140097a22  jz      short loc_140097A4D
0x140097a24  mov     eax, [rcx+2Ch]
0x140097a27  test    sil, al
0x140097a2a  jz      short loc_140097A4D
0x140097a2c  cmp     byte ptr [rcx+29h], 4
0x140097a30  jb      short loc_140097A4D
0x140097a32  mov     rcx, [rcx+18h]
0x140097a36  lea     edx, [rsi+9]
0x140097a39  mov     r9, rbx
0x140097a3c  mov     qword ptr [rsp+0F0h+DeviceCharacteristics], r13
0x140097a41  lea     r8, WPP_61bd6e0e791f31e2ffa75bd9431aea96_Traceguids
0x140097a48  call    WPP_SF_qq
0x140097a4d  xorps   xmm0, xmm0
0x140097a50  lea     rdx, DriverEntry; ClientIdentificationAddress
0x140097a57  mov     rcx, rbx; DriverObject
0x140097a5a  movups  xmmword ptr [rbp+57h+DeviceName.Length], xmm0
0x140097a5e  call    cs:__imp_IoGetDriverObjectExtension
0x140097a65  nop     dword ptr [rax+rax+00h]
0x140097a6a  lea     r8, [rbp+57h+var_A8]
0x140097a6e  mov     rcx, r13
0x140097a71  lea     rdx, [rbp+57h+DeviceName]
0x140097a75  mov     qword ptr [rbp+57h+var_58], rax
0x140097a79  mov     rbx, rax
0x140097a7c  call    RaidCreateDeviceName
0x140097a81  mov     rcx, r13
0x140097a84  call    RaGetBusInterface
0x140097a89  cmp     eax, 0FFFFFFFFh
0x140097a8c  mov     edx, r12d
0x140097a8f  mov     rcx, rbx
0x140097a92  cmovnz  edx, eax
0x140097a95  call    RaFindDriverInitData
0x140097a9a  lea     rcx, [rbx+28h]
0x140097a9e  xor     edx, edx
0x140097aa0  lea     r8, [rbp+57h+var_A0]
0x140097aa4  mov     rdi, rax
0x140097aa7  call    PortReadStorageBusType
0x140097aac  mov     rcx, r13; Pdo
0x140097aaf  mov     byte ptr [rbp+57h+KeyHandle], al
0x140097ab2  call    StorIsChildAdapterPdo
0x140097ab7  mov     ecx, 1
0x140097abc  test    al, al
0x140097abe  jz      short loc_140097ADE
0x140097ac0  mov     dl, cl
0x140097ac2  lea     r8, [rbp+57h+var_98]
0x140097ac6  lea     rcx, [rbx+28h]
0x140097aca  call    PortReadStorageBusType
0x140097acf  mov     ecx, 1
0x140097ad4  cmp     al, cl
0x140097ad6  jnz     short loc_140097ADE
0x140097ad8  mov     r12d, [rbp+57h+var_98]
0x140097adc  jmp     short loc_140097AEF
0x140097ade  cmp     byte ptr [rbp+57h+KeyHandle], r14b
0x140097ae2  mov     eax, 7Fh
0x140097ae7  mov     r12d, dword ptr [rbp+57h+var_A0]
0x140097aeb  cmovz   r12d, eax
0x140097aef  cmp     r12d, 14h
0x140097af3  jnz     short loc_140097AFC
0x140097af5  mov     bl, cl
0x140097af7  jmp     loc_140097CA1
0x140097afc  xor     bl, bl
0x140097afe  cmp     r12d, 11h
0x140097b02  jnz     loc_140097CA1
0x140097b08  cmp     cs:DisableNativeNVMeStack, bl
0x140097b0e  jnz     loc_140097CD2
0x140097b14  test    rdi, rdi
0x140097b17  jz      short loc_140097B43
0x140097b19  test    dword ptr [rdi+0B8h], 40000000h
0x140097b23  jz      short loc_140097B43
0x140097b25  cmp     cs:g_OSisClient, bl
0x140097b2b  jnz     short loc_140097B31
0x140097b2d  mov     bl, cl
0x140097b2f  jmp     short loc_140097B43
0x140097b31  call    Feature_NativeNVMeStackEnableForClientOS__private_IsEnabledDeviceUsageNoInline
0x140097b36  test    eax, eax
0x140097b38  movzx   ebx, bl
0x140097b3b  mov     eax, 1
0x140097b40  cmovnz  ebx, eax
0x140097b43  lea     rdx, aStorport; "StorPort"
0x140097b4a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140097b4e  call    cs:__imp_RtlInitUnicodeString
0x140097b55  nop     dword ptr [rax+rax+00h]
0x140097b5a  lea     rdx, aEnablenvmeinte; "EnableNVMeInterface"
0x140097b61  lea     rcx, [rbp+57h+var_78]; DestinationString
0x140097b65  call    cs:__imp_RtlInitUnicodeString
0x140097b6c  nop     dword ptr [rax+rax+00h]
0x140097b71  mov     ecx, 4
0x140097b76  lea     rax, [rbp+57h+var_94]
0x140097b7a  mov     [rbp+57h+var_A0], rax
0x140097b7e  lea     r8, [rbp+57h+var_78]; int
0x140097b82  lea     rax, [rbp+57h+KeyHandle]
0x140097b86  mov     [rbp+57h+KeyHandle], ecx
0x140097b89  mov     qword ptr [rsp+0F0h+Exclusive], rax; KeyHandle
0x140097b8e  lea     rdx, [rbp+57h+DestinationString]; int
0x140097b92  lea     rax, [rbp+57h+var_A0]
0x140097b96  mov     r9d, ecx; int
0x140097b99  mov     rcx, r13; int
0x140097b9c  mov     qword ptr [rsp+0F0h+DeviceCharacteristics], rax; __int64
0x140097ba1  call    PortRegistryReadDeviceKey
0x140097ba6  test    eax, eax
0x140097ba8  js      short loc_140097BB4
0x140097baa  cmp     [rbp+57h+var_94], r14d
0x140097bae  jz      short loc_140097BCD
0x140097bb0  mov     bl, 1
0x140097bb2  jmp     short loc_140097BBC
0x140097bb4  test    bl, bl
0x140097bb6  jz      loc_140097CA1
0x140097bbc  test    rdi, rdi
0x140097bbf  jz      short loc_140097BDC
0x140097bc1  test    dword ptr [rdi+0B8h], 40000000h
0x140097bcb  jnz     short loc_140097BD4
0x140097bcd  xor     bl, bl
0x140097bcf  jmp     loc_140097CA1
0x140097bd4  test    bl, bl
0x140097bd6  jz      loc_140097CA1
0x140097bdc  lea     rdx, aStorport; "StorPort"
0x140097be3  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140097be7  call    cs:__imp_RtlInitUnicodeString
0x140097bee  nop     dword ptr [rax+rax+00h]
0x140097bf3  lea     rdx, aDmarsupport; "DMArSupport"
0x140097bfa  lea     rcx, [rbp+57h+var_78]; DestinationString
0x140097bfe  call    cs:__imp_RtlInitUnicodeString
0x140097c05  nop     dword ptr [rax+rax+00h]
0x140097c0a  mov     ecx, 4
0x140097c0f  lea     rax, [rbp+57h+var_90]
0x140097c13  mov     [rbp+57h+var_A0], rax
0x140097c17  lea     r8, [rbp+57h+var_78]; int
0x140097c1b  lea     rax, [rbp+57h+KeyHandle]
0x140097c1f  mov     [rbp+57h+KeyHandle], ecx
0x140097c22  mov     qword ptr [rsp+0F0h+Exclusive], rax; KeyHandle
0x140097c27  lea     rdx, [rbp+57h+DestinationString]; int
0x140097c2b  lea     rax, [rbp+57h+var_A0]
0x140097c2f  mov     r9d, ecx; int
0x140097c32  mov     rcx, r13; int
0x140097c35  mov     qword ptr [rsp+0F0h+DeviceCharacteristics], rax; __int64
0x140097c3a  call    PortRegistryReadDeviceKey
0x140097c3f  test    eax, eax
0x140097c41  js      short loc_140097CA1
0x140097c43  xor     eax, eax
0x140097c45  lea     rdx, aDmaManagement; "DMA Management"
0x140097c4c  cmp     [rbp+57h+var_90], eax
0x140097c4f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140097c53  setnz   al
0x140097c56  mov     [rbp+57h+var_8C], eax
0x140097c59  call    cs:__imp_RtlInitUnicodeString
0x140097c60  nop     dword ptr [rax+rax+00h]
0x140097c65  lea     rdx, aRemappingsuppo; "RemappingSupported"
0x140097c6c  lea     rcx, [rbp+57h+var_78]; DestinationString
0x140097c70  call    cs:__imp_RtlInitUnicodeString
0x140097c77  nop     dword ptr [rax+rax+00h]
0x140097c7c  mov     ecx, 4
0x140097c81  lea     rax, [rbp+57h+var_8C]
0x140097c85  mov     dword ptr [rsp+0F0h+Exclusive], ecx
0x140097c89  lea     r8, [rbp+57h+var_78]
0x140097c8d  mov     r9d, ecx
0x140097c90  mov     qword ptr [rsp+0F0h+DeviceCharacteristics], rax
0x140097c95  mov     rcx, r13
0x140097c98  lea     rdx, [rbp+57h+DestinationString]
0x140097c9c  call    PortRegistryWriteDeviceKey
0x140097ca1  cmp     cs:DisableNativeNVMeStack, r14b
0x140097ca8  jnz     short loc_140097CC7
0x140097caa  test    rdi, rdi
0x140097cad  jz      short loc_140097CC7
0x140097caf  test    dword ptr [rdi+0B8h], 40000h
0x140097cb9  jz      short loc_140097CC7
0x140097cbb  mov     eax, 1
0x140097cc0  mov     bl, al
0x140097cc2  mov     [rbp+57h+arg_10], al
0x140097cc5  jmp     short loc_140097CCB
0x140097cc7  test    bl, bl
0x140097cc9  jz      short loc_140097CD2
0x140097ccb  mov     edx, 5E0h
0x140097cd0  jmp     short loc_140097CE4
0x140097cd2  mov     eax, cs:g_RaidLogListSize
0x140097cd8  lea     edx, [rax+rax*2]
0x140097cdb  shl     edx, 4
0x140097cde  add     edx, 1940h; DeviceExtensionSize
0x140097ce4  mov     rcx, [rbp+57h+DriverObject]; DriverObject
0x140097ce8  lea     rax, [rbp+57h+SourceDevice]
0x140097cec  mov     [rsp+0F0h+DeviceObject], rax; DeviceObject
0x140097cf1  lea     r8, [rbp+57h+DeviceName]; DeviceName
0x140097cf5  mov     [rsp+0F0h+Exclusive], r14b; Exclusive
0x140097cfa  mov     r9d, 4; DeviceType
0x140097d00  mov     [rsp+0F0h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x140097d08  call    cs:__imp_IoCreateDevice
0x140097d0f  nop     dword ptr [rax+rax+00h]
0x140097d14  mov     edi, eax
0x140097d16  test    eax, eax
0x140097d18  js      loc_140097E23
0x140097d1e  test    bl, bl
0x140097d20  jz      short loc_140097D46
0x140097d22  mov     rdx, [rbp+57h+SourceDevice]
0x140097d26  mov     r8b, [rbp+57h+arg_10]
0x140097d2a  mov     r15, [rdx+40h]
0x140097d2e  mov     rcx, r15
0x140097d31  call    CreateNvmeAdapter
0x140097d36  mov     edi, eax
0x140097d38  test    eax, eax
0x140097d3a  jns     short loc_140097D9E
0x140097d3c  mov     esi, 3
0x140097d41  jmp     loc_140097E2B
0x140097d46  mov     rax, [rbp+57h+SourceDevice]
0x140097d4a  mov     r14, [rax+40h]
0x140097d4e  mov     rcx, r14
0x140097d51  call    RaidCreateAdapter
0x140097d56  mov     edi, eax
0x140097d58  test    eax, eax
0x140097d5a  jns     short loc_140097D9E
0x140097d5c  mov     esi, 4
0x140097d61  test    r14, r14
0x140097d64  jz      short loc_140097D6E
0x140097d66  mov     rcx, r14
0x140097d69  call    RaidDeleteAdapter
0x140097d6e  mov     rcx, [rbp+57h+SourceDevice]; DeviceObject
0x140097d72  test    rcx, rcx
0x140097d75  jz      short loc_140097D83
0x140097d77  call    cs:__imp_IoDeleteDevice
0x140097d7e  nop     dword ptr [rax+rax+00h]
0x140097d83  cmp     cs:BootCompleted, 0
0x140097d8a  jnz     loc_140097EC7
0x140097d90  mov     edx, edi
0x140097d92  mov     ecx, esi
0x140097d94  call    StorpLogBootError
0x140097d99  jmp     loc_140097EC7
0x140097d9e  mov     rcx, [rbp+57h+SourceDevice]; SourceDevice
0x140097da2  mov     rdx, r13; TargetDevice
0x140097da5  call    cs:__imp_IoAttachDeviceToDeviceStack
0x140097dac  nop     dword ptr [rax+rax+00h]
0x140097db1  mov     rsi, rax
0x140097db4  test    rax, rax
0x140097db7  jnz     short loc_140097DC3
0x140097db9  mov     edi, 0C0000001h
0x140097dbe  lea     esi, [rax+5]
0x140097dc1  jmp     short loc_140097E23
0x140097dc3  mov     eax, [rbp+57h+var_A8]
0x140097dc6  mov     r9, rsi; int
0x140097dc9  mov     rdx, [rbp+57h+SourceDevice]; int
0x140097dcd  mov     [rsp+0F0h+var_B8], r12d; int
0x140097dd2  mov     dword ptr [rsp+0F0h+DeviceObject], eax; int
0x140097dd6  lea     rax, [rbp+57h+DeviceName]
0x140097dda  mov     qword ptr [rsp+0F0h+Exclusive], rax; __int64
0x140097ddf  mov     qword ptr [rsp+0F0h+DeviceCharacteristics], r13; DeviceObject
0x140097de4  mov     r13, qword ptr [rbp+57h+var_58]
0x140097de8  mov     r8, r13; int
0x140097deb  test    bl, bl
0x140097ded  jz      short loc_140097DF9
0x140097def  mov     rcx, r15; int
0x140097df2  call    InitializeNvmeAdapter
0x140097df7  jmp     short loc_140097E01
0x140097df9  mov     rcx, r14; Context
0x140097dfc  call    RaidInitializeAdapter
0x140097e01  mov     [rbp+57h+DeviceName.Buffer], 0
0x140097e09  mov     edi, eax
0x140097e0b  test    eax, eax
0x140097e0d  jns     short loc_140097E41
0x140097e0f  mov     rcx, rsi; TargetDevice
0x140097e12  call    cs:__imp_IoDetachDevice
0x140097e19  nop     dword ptr [rax+rax+00h]
0x140097e1e  mov     esi, 6
0x140097e23  test    bl, bl
0x140097e25  jz      loc_140097D61
0x140097e2b  test    r15, r15
0x140097e2e  jz      loc_140097D6E
0x140097e34  mov     rcx, r15
0x140097e37  call    DeleteNvmeAdapter
  ... truncated ...
```
