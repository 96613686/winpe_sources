# CreateStaticFunctionPDOs

- ea: `0x140023938`
- end: `0x140024186`
- name: `CreateStaticFunctionPDOs`
- size: `2126`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140028f7c`

## callees

- `0x14000a6cc`
- `0x14000b4bc`
- `0x14000c2bc`
- `0x14000d9b4`
- `0x14000f664`
- `0x140011f4c`
- `0x140013630`
- `0x140013858`
- `0x140015100`
- `0x140023694`
- `0x140023938`
- `0x14002610c`
- `0x140028440`
- `0x14002990c`
- `0x14002a1cc`
- `0x14002c7d0`

## import_xrefs

- `ntoskrnl!IoCreateDevice` at `0x140023af7`
- `ntoskrnl!IoCreateDevice` at `0x140023af7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400240cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400240cc`
- `ntoskrnl!KeInitializeEvent` at `0x140023c0a`
- `ntoskrnl!KeInitializeEvent` at `0x140023c35`
- `ntoskrnl!KeInitializeEvent` at `0x140023d1f`
- `ntoskrnl!KeInitializeEvent` at `0x140023c0a`
- `ntoskrnl!KeInitializeEvent` at `0x140023c35`
- `ntoskrnl!KeInitializeEvent` at `0x140023d1f`
- `ntoskrnl!ExAllocatePool2` at `0x140023a12`
- `ntoskrnl!ExAllocatePool2` at `0x140023a12`
- `ntoskrnl!IoDeleteDevice` at `0x1400240ab`
- `ntoskrnl!IoDeleteDevice` at `0x1400240ab`
- `ntoskrnl!KeInitializeSpinLock` at `0x140023b9d`
- `ntoskrnl!KeInitializeSpinLock` at `0x140023c1d`
- `ntoskrnl!KeInitializeSpinLock` at `0x140023c48`
- `ntoskrnl!KeInitializeSpinLock` at `0x140023b9d`
- `ntoskrnl!KeInitializeSpinLock` at `0x140023c1d`
- `ntoskrnl!KeInitializeSpinLock` at `0x140023c48`
- `ntoskrnl!IoCsqInitialize` at `0x140023cad`
- `ntoskrnl!IoCsqInitialize` at `0x140023d07`
- `ntoskrnl!IoCsqInitialize` at `0x140023cad`
- `ntoskrnl!IoCsqInitialize` at `0x140023d07`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140023dd8`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140023e42`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140023dd8`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140023e42`

## pseudocode

```c
__int64 __fastcall CreateStaticFunctionPDOs(__int64 a1)
{
  __int64 v1; // rbp
  unsigned int v3; // ebx
  unsigned int v4; // eax
  __int64 v5; // rdx
  unsigned int v6; // esi
  unsigned int v7; // eax
  __int64 Pool2; // rax
  __int64 v9; // rdx
  NTSTATUS ResourcesForFunctionSuspend; // ebp
  unsigned int v11; // r12d
  unsigned int v12; // r14d
  __int64 v13; // r13
  int v14; // edx
  char *DeviceExtension; // rbx
  char *v16; // rsi
  int v17; // eax
  int v18; // ecx
  unsigned __int8 *v19; // rbx
  __int64 v20; // rcx
  PUSB_INTERFACE_DESCRIPTOR v21; // rax
  PUSB_INTERFACE_DESCRIPTOR v22; // r14
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v24; // r8
  __int64 v25; // rcx
  unsigned __int8 bAlternateSetting; // al
  char v27; // cl
  __int64 v28; // rax
  char v29; // al
  __int64 v30; // rbx
  unsigned int i; // ebx
  struct _DEVICE_OBJECT *v32; // rsi
  char Exclusive; // [rsp+28h] [rbp-50h]
  PDEVICE_OBJECT *DeviceObject; // [rsp+30h] [rbp-48h]
  PDEVICE_OBJECT *DeviceObjecta; // [rsp+30h] [rbp-48h]
  int v37; // [rsp+80h] [rbp+8h]
  PDEVICE_OBJECT v38; // [rsp+88h] [rbp+10h] BYREF
  char *v39; // [rsp+90h] [rbp+18h]

  v1 = *(_QWORD *)(a1 + 56);
  v3 = 0;
  LOBYTE(v4) = *(_BYTE *)(v1 + 4);
  if ( (_BYTE)v4 )
  {
    do
    {
      v5 = *(_QWORD *)(*(_QWORD *)(a1 + 88) + 16LL * v3);
      if ( *(_BYTE *)(v5 + 5) == 13 )
      {
        v6 = *(unsigned __int8 *)(v5 + 2);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          Exclusive = *(_BYTE *)(v5 + 2);
          LOBYTE(v5) = 4;
          WPP_RECORDER_SF_d(
            *(_QWORD *)(a1 + 1368),
            v5,
            1,
            10,
            (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids,
            Exclusive);
        }
        InitCSInfo(a1, v6);
      }
      v4 = *(unsigned __int8 *)(v1 + 4);
      ++v3;
    }
    while ( v3 < v4 );
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_dd(
      *(_QWORD *)(a1 + 1368),
      4,
      1,
      11,
      (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids,
      v4,
      *(_DWORD *)(a1 + 116));
  v7 = InvokePdoEnableCallbacks(a1);
  *(_DWORD *)(a1 + 120) = v7;
  Pool2 = ExAllocatePool2(64, 8LL * v7 + 16, 1130525525);
  *(_QWORD *)(a1 + 128) = Pool2;
  if ( !Pool2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_d(*(_QWORD *)(a1 + 1368), v9, 8, 12, (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids, 0);
    }
    LODWORD(DeviceObject) = 0;
    ResourcesForFunctionSuspend = -1073741670;
    RecordStartFailData(a1, -1073741670, 0, -1610612731, 1129530929, 0, (size_t)DeviceObject);
    *(_QWORD *)(a1 + 128) = 0;
LABEL_56:
    if ( *(_QWORD *)(a1 + 128) )
    {
      for ( i = 0; i < *(_DWORD *)(a1 + 120); ++i )
      {
        v32 = *(struct _DEVICE_OBJECT **)(*(_QWORD *)(a1 + 128) + 8LL * i + 8);
        if ( v32 )
        {
          FreeResourcesForFunctionSuspend(v32->DeviceExtension);
          IoDeleteDevice(v32);
        }
      }
      ExFreePoolWithTag(*(PVOID *)(a1 + 128), 0x43627355u);
      *(_QWORD *)(a1 + 128) = 0;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1 + 1368),
        v9,
        8,
        17,
        (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids,
        ResourcesForFunctionSuspend);
    }
    return (unsigned int)ResourcesForFunctionSuspend;
  }
  ResourcesForFunctionSuspend = 0;
  v11 = 0;
  v12 = 0;
  v37 = 0;
  if ( !*(_DWORD *)(a1 + 116) )
    goto LABEL_53;
  while ( 1 )
  {
    v38 = 0;
    v13 = *(_QWORD *)(a1 + 1136) + 88LL * v12;
    if ( (*(_DWORD *)(v13 + 80) & 0x10) == 0 )
      break;
LABEL_52:
    v37 = ++v12;
    if ( v12 >= *(_DWORD *)(a1 + 116) )
      goto LABEL_53;
  }
  if ( v11 >= *(_DWORD *)(a1 + 120) )
  {
    ResourcesForFunctionSuspend = -1073741668;
    goto LABEL_56;
  }
  ResourcesForFunctionSuspend = IoCreateDevice(*(PDRIVER_OBJECT *)(a1 + 16), 0x570u, 0, 0x22u, 0x80u, 0, &v38);
  if ( ResourcesForFunctionSuspend >= 0 && v38 )
  {
    DeviceExtension = (char *)v38->DeviceExtension;
    v39 = DeviceExtension;
    memset(DeviceExtension + 5, 0, 0x56Bu);
    strcpy(DeviceExtension, "UsbC");
    v16 = DeviceExtension + 8;
    v38->Flags |= 0x2000u;
    *((_DWORD *)DeviceExtension + 2) = 1131373648;
    *((_DWORD *)DeviceExtension + 3) = v12;
    *((_QWORD *)DeviceExtension + 29) = v38;
    *((_QWORD *)DeviceExtension + 37) = 0;
    DeviceExtension[126] = 0;
    *((_DWORD *)DeviceExtension + 76) = 0;
    *((_QWORD *)DeviceExtension + 30) = a1;
    *((_QWORD *)DeviceExtension + 31) = v13;
    *((_DWORD *)DeviceExtension + 6) = 1;
    KeInitializeSpinLock((PKSPIN_LOCK)DeviceExtension + 53);
    *((_DWORD *)DeviceExtension + 76) |= 8u;
    *((_QWORD *)DeviceExtension + 54) = 0;
    DeviceExtension[309] = *(_BYTE *)(a1 + 1362) == 0;
    *((_QWORD *)DeviceExtension + 50) = *(_QWORD *)(a1 + 1368);
    *((_QWORD *)DeviceExtension + 43) = 0;
    *((_QWORD *)DeviceExtension + 46) = 0;
    *((_QWORD *)DeviceExtension + 45) = DeviceExtension + 352;
    *((_QWORD *)DeviceExtension + 44) = DeviceExtension + 352;
    *((_DWORD *)DeviceExtension + 79) = 1;
    KeInitializeEvent((PRKEVENT)(DeviceExtension + 320), NotificationEvent, 0);
    KeInitializeSpinLock((PKSPIN_LOCK)DeviceExtension + 36);
    KeInitializeEvent((PRKEVENT)(DeviceExtension + 440), SynchronizationEvent, 1u);
    KeInitializeSpinLock((PKSPIN_LOCK)DeviceExtension + 58);
    *((_QWORD *)DeviceExtension + 60) = DeviceExtension + 472;
    *((_QWORD *)DeviceExtension + 59) = DeviceExtension + 472;
    *((_QWORD *)DeviceExtension + 14) = DeviceExtension + 104;
    *((_QWORD *)DeviceExtension + 13) = DeviceExtension + 104;
    IoCsqInitialize(
      (PIO_CSQ)(DeviceExtension + 40),
      WaitWakeInsertIrp,
      WaitWakeRemoveIrp,
      PdoIdlePeekNextIrp,
      WaitWakeAcquireLock,
      WaitWakeReleaseLock,
      WaitWakeCancelComplete);
    *((_QWORD *)DeviceExtension + 25) = DeviceExtension + 192;
    *((_QWORD *)DeviceExtension + 24) = DeviceExtension + 192;
    IoCsqInitialize(
      (PIO_CSQ)DeviceExtension + 2,
      PdoIdleInsertIrp,
      PdoIdleRemoveIrp,
      PdoIdlePeekNextIrp,
      PdoIdleAcquireLock,
      PdoIdleReleaseLock,
      PdoIdleCancelComplete);
    KeInitializeEvent((PRKEVENT)(DeviceExtension + 208), NotificationEvent, 1u);
    v17 = *(unsigned __int8 *)(v13 + 5);
    *((_DWORD *)DeviceExtension + 4) = v17;
    v18 = *(unsigned __int8 *)(v13 + 6);
    *((_DWORD *)DeviceExtension + 5) = v18;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_dd(
        *(_QWORD *)(a1 + 1368),
        4,
        1,
        14,
        (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids,
        v18,
        v17);
    *(_OWORD *)(DeviceExtension + 264) = *(_OWORD *)(a1 + 96);
    *((_WORD *)DeviceExtension + 140) = *(_WORD *)(a1 + 112);
    v19 = ***(unsigned __int8 ****)(v13 + 8);
    v20 = *((_QWORD *)v16 + 29);
    if ( *(_WORD *)(v20 + 98) > 0x200u && (*(_DWORD *)(v20 + 1224) & 0x20) == 0 )
    {
      v21 = USBD_ParseConfigurationDescriptorEx(
              *(PUSB_CONFIGURATION_DESCRIPTOR *)(v20 + 48),
              ***(PVOID ***)(v13 + 8),
              v19[2],
              -1,
              8,
              6,
              98);
      if ( v21 )
      {
        if ( !*(_BYTE *)(*((_QWORD *)v16 + 29) + 1363LL) )
        {
          v16[303] = 1;
          v16[305] = v21->bAlternateSetting;
        }
      }
    }
    if ( v19[5] != 0xFF )
      goto LABEL_36;
    v22 = USBD_ParseConfigurationDescriptorEx(
            *(PUSB_CONFIGURATION_DESCRIPTOR *)(*((_QWORD *)v16 + 29) + 48LL),
            v19,
            v19[2],
            -1,
            7,
            1,
            4);
    if ( !v22 )
    {
LABEL_35:
      v12 = v37;
LABEL_36:
      if ( (unsigned int)Feature_WinUsb_Print__private_IsEnabledDeviceUsageNoInline()
        && v19[5] == 7
        && (unsigned int)CheckOptInWinUsbPrint(
                           *(unsigned __int16 *)(*((_QWORD *)v16 + 29) + 104LL),
                           *(unsigned __int16 *)(*((_QWORD *)v16 + 29) + 106LL)) )
      {
        v16[408] = 1;
      }
      v27 = *(_BYTE *)(***(_QWORD ***)(v13 + 8) + 8LL);
      if ( v27 )
        v16[271] = v27;
      v28 = *(_QWORD *)(v13 + 16);
      if ( v28 )
      {
        v29 = *(_BYTE *)(v28 + 7);
        if ( v29 )
          v16[271] = v29;
      }
      *(_QWORD *)(*(_QWORD *)(a1 + 128) + 8LL * v11 + 8) = v38;
      v9 = 88LL * v12;
      *(_QWORD *)(v9 + *(_QWORD *)(a1 + 1136) + 72) = v38;
      v38->StackSize = *(_BYTE *)(*(_QWORD *)(a1 + 32) + 76LL) + 1;
      if ( *(_BYTE *)(a1 + 1361) )
        SetFunctionHandleData(a1, v16, *(_QWORD *)(*(_QWORD *)(a1 + 1352) + 8LL * v12));
      if ( *(_BYTE *)(a1 + 1362) )
      {
        ResourcesForFunctionSuspend = AllocateResourcesForFunctionSuspend(a1, v16);
        if ( ResourcesForFunctionSuspend < 0 )
          goto LABEL_56;
        v30 = *((_QWORD *)v16 + 48);
        *(_BYTE *)(v30 + 57) = IsFunctionRemoteWakeCapable(a1, v16);
      }
      ++v11;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = 4;
        WPP_RECORDER_SF_qD(
          *(_QWORD *)(a1 + 1368),
          v9,
          1,
          15,
          (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids,
          (char)v38,
          v11);
      }
      goto LABEL_52;
    }
    IsEnabledDeviceUsageNoInline = Feature_WinUsb_Print__private_IsEnabledDeviceUsageNoInline();
    v25 = *((_QWORD *)v39 + 30);
    if ( IsEnabledDeviceUsageNoInline )
    {
      if ( (unsigned int)CheckOptInWinUsbPrint(*(unsigned __int16 *)(v25 + 104), *(unsigned __int16 *)(v25 + 106)) )
      {
        bAlternateSetting = v22->bAlternateSetting;
        v16[408] = 1;
LABEL_34:
        v16[305] = bAlternateSetting;
        goto LABEL_35;
      }
      v25 = *((_QWORD *)v16 + 29);
    }
    v16[303] = 1;
    LOBYTE(v24) = v19[2];
    if ( !(unsigned int)CheckIppUsbAltIndex(*(unsigned __int16 *)(v25 + 104), *(unsigned __int16 *)(v25 + 106), v24)
      && !(unsigned int)IsProtectedPrintEnabled() )
    {
      goto LABEL_35;
    }
    v16[304] = 1;
    bAlternateSetting = v22->bAlternateSetting;
    goto LABEL_34;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v14) = 2;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(a1 + 1368),
      v14,
      8,
      13,
      (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids,
      ResourcesForFunctionSuspend);
  }
  LODWORD(DeviceObjecta) = 0;
  RecordStartFailData(a1, ResourcesForFunctionSuspend, 0, -1610612731, 1129530930, 0, (size_t)DeviceObjecta);
LABEL_53:
  if ( ResourcesForFunctionSuspend < 0 )
    goto LABEL_56;
  **(_DWORD **)(a1 + 128) = *(_DWORD *)(a1 + 120);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = 4;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(a1 + 1368),
      v9,
      1,
      16,
      (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids,
      *(_DWORD *)(a1 + 120));
  }
  return (unsigned int)ResourcesForFunctionSuspend;
}

```

## disassembly

```asm
0x140023938  push    rbx
0x14002393a  push    rbp
0x14002393b  push    rsi
0x14002393c  push    rdi
0x14002393d  push    r12
0x14002393f  push    r13
0x140023941  push    r14
0x140023943  sub     rsp, 40h
0x140023947  mov     rbp, [rcx+38h]
0x14002394b  lea     r12, WPP_RECORDER_INITIALIZED
0x140023952  xor     esi, esi
0x140023954  lea     r14, WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids
0x14002395b  mov     rdi, rcx
0x14002395e  mov     ebx, esi
0x140023960  mov     al, [rbp+4]
0x140023963  test    al, al
0x140023965  jz      short loc_1400239BE
0x140023967  mov     rax, [rdi+58h]
0x14002396b  mov     ecx, ebx
0x14002396d  add     rcx, rcx
0x140023970  mov     rdx, [rax+rcx*8]
0x140023974  cmp     byte ptr [rdx+5], 0Dh
0x140023978  jnz     short loc_1400239B2
0x14002397a  movzx   esi, byte ptr [rdx+2]
0x14002397e  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140023985  jz      short loc_1400239A8
0x140023987  mov     rcx, [rdi+558h]
0x14002398e  mov     r9d, 0Ah
0x140023994  mov     dword ptr [rsp+78h+Exclusive], esi
0x140023998  mov     dl, 4
0x14002399a  mov     qword ptr [rsp+78h+DeviceCharacteristics], r14
0x14002399f  lea     r8d, [r9-9]
0x1400239a3  call    WPP_RECORDER_SF_d
0x1400239a8  mov     edx, esi
0x1400239aa  mov     rcx, rdi
0x1400239ad  call    InitCSInfo
0x1400239b2  movzx   eax, byte ptr [rbp+4]
0x1400239b6  inc     ebx
0x1400239b8  cmp     ebx, eax
0x1400239ba  jb      short loc_140023967
0x1400239bc  xor     esi, esi
0x1400239be  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400239c5  jz      short loc_1400239F2
0x1400239c7  movzx   ecx, al
0x1400239ca  mov     r9d, 0Bh
0x1400239d0  mov     eax, [rdi+74h]
0x1400239d3  mov     dl, 4
0x1400239d5  mov     dword ptr [rsp+78h+DeviceObject], eax
0x1400239d9  mov     dword ptr [rsp+78h+Exclusive], ecx
0x1400239dd  mov     rcx, [rdi+558h]
0x1400239e4  lea     r8d, [r9-0Ah]
0x1400239e8  mov     qword ptr [rsp+78h+DeviceCharacteristics], r14
0x1400239ed  call    WPP_RECORDER_SF_dd
0x1400239f2  mov     rcx, rdi
0x1400239f5  call    InvokePdoEnableCallbacks
0x1400239fa  mov     edx, eax
0x1400239fc  mov     ecx, 40h ; '@'
0x140023a01  mov     [rdi+78h], edx
0x140023a04  mov     r8d, 43627355h
0x140023a0a  lea     rdx, ds:10h[rdx*8]
0x140023a12  call    cs:__imp_ExAllocatePool2
0x140023a19  nop     dword ptr [rax+rax+00h]
0x140023a1e  mov     [rdi+80h], rax
0x140023a25  test    rax, rax
0x140023a28  jnz     short loc_140023A87
0x140023a2a  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140023a31  jz      short loc_140023A52
0x140023a33  mov     rcx, [rdi+558h]
0x140023a3a  lea     r9d, [rax+0Ch]
0x140023a3e  mov     dword ptr [rsp+78h+Exclusive], esi
0x140023a42  lea     r8d, [rax+8]
0x140023a46  mov     dl, 2
0x140023a48  mov     qword ptr [rsp+78h+DeviceCharacteristics], r14
0x140023a4d  call    WPP_RECORDER_SF_d
0x140023a52  mov     dword ptr [rsp+78h+DeviceObject], esi; Size
0x140023a56  mov     ebp, 0C000009Ah
0x140023a5b  mov     edx, ebp; int
0x140023a5d  mov     qword ptr [rsp+78h+Exclusive], rsi; Src
0x140023a62  mov     r9d, 0A0000005h; int
0x140023a68  mov     [rsp+78h+DeviceCharacteristics], 43534631h; int
0x140023a70  xor     r8d, r8d; int
0x140023a73  mov     rcx, rdi; int
0x140023a76  call    RecordStartFailData
0x140023a7b  mov     [rdi+80h], rsi
0x140023a82  jmp     loc_14002407C
0x140023a87  mov     ebp, esi
0x140023a89  mov     r12d, esi
0x140023a8c  mov     r14d, esi
0x140023a8f  mov     [rsp+78h+arg_0], esi
0x140023a96  cmp     [rdi+74h], esi
0x140023a99  jbe     loc_140024024
0x140023a9f  mov     eax, r14d
0x140023aa2  imul    r13, rax, 58h ; 'X'
0x140023aa6  mov     [rsp+78h+arg_8], rsi
0x140023aae  add     r13, [rdi+470h]
0x140023ab5  mov     eax, [r13+50h]
0x140023ab9  test    al, 10h
0x140023abb  jnz     loc_14002400F
0x140023ac1  cmp     r12d, [rdi+78h]
0x140023ac5  jnb     loc_14002417C
0x140023acb  mov     rcx, [rdi+10h]; DriverObject
0x140023acf  lea     rax, [rsp+78h+arg_8]
0x140023ad7  mov     [rsp+78h+DeviceObject], rax; DeviceObject
0x140023adc  mov     r9d, 22h ; '"'; DeviceType
0x140023ae2  mov     [rsp+78h+Exclusive], sil; Exclusive
0x140023ae7  xor     r8d, r8d; DeviceName
0x140023aea  mov     edx, 570h; DeviceExtensionSize
0x140023aef  mov     [rsp+78h+DeviceCharacteristics], 80h; DeviceCharacteristics
0x140023af7  call    cs:__imp_IoCreateDevice
0x140023afe  nop     dword ptr [rax+rax+00h]
0x140023b03  mov     ebp, eax
0x140023b05  test    eax, eax
0x140023b07  js      loc_14002411B
0x140023b0d  mov     rax, [rsp+78h+arg_8]
0x140023b15  test    rax, rax
0x140023b18  jz      loc_14002411B
0x140023b1e  mov     rbx, [rax+40h]
0x140023b22  xor     edx, edx; Val
0x140023b24  mov     r8d, 56Bh; Size
0x140023b2a  mov     [rsp+78h+arg_10], rbx
0x140023b32  lea     rcx, [rbx+5]; void *
0x140023b36  call    memset
0x140023b3b  mov     [rbx+4], sil
0x140023b3f  lea     rcx, [rbx+1A8h]; SpinLock
0x140023b46  mov     dword ptr [rbx], 43627355h
0x140023b4c  lea     rsi, [rbx+8]
0x140023b50  mov     rax, [rsp+78h+arg_8]
0x140023b58  bts     dword ptr [rax+30h], 0Dh
0x140023b5d  mov     dword ptr [rsi], 436F6450h
0x140023b63  mov     [rbx+0Ch], r14d
0x140023b67  mov     rax, [rsp+78h+arg_8]
0x140023b6f  mov     [rbx+0E8h], rax
0x140023b76  xor     eax, eax
0x140023b78  mov     [rbx+128h], rax
0x140023b7f  mov     [rbx+7Eh], al
0x140023b82  mov     [rbx+130h], eax
0x140023b88  mov     [rbx+0F0h], rdi
0x140023b8f  mov     [rbx+0F8h], r13
0x140023b96  mov     dword ptr [rbx+18h], 1
0x140023b9d  call    cs:__imp_KeInitializeSpinLock
0x140023ba4  nop     dword ptr [rax+rax+00h]
0x140023ba9  or      dword ptr [rbx+130h], 8
0x140023bb0  xor     ecx, ecx
0x140023bb2  mov     [rbx+1B0h], rcx
0x140023bb9  cmp     [rdi+552h], cl
0x140023bbf  setz    al
0x140023bc2  xor     r8d, r8d; State
0x140023bc5  mov     [rbx+135h], al
0x140023bcb  xor     edx, edx; Type
0x140023bcd  mov     rax, [rdi+558h]
0x140023bd4  lea     ebx, [rcx+1]
0x140023bd7  mov     [rsi+188h], rax
0x140023bde  lea     rax, [rsi+158h]
0x140023be5  mov     [rsi+150h], rcx
0x140023bec  mov     [rsi+168h], rcx
0x140023bf3  lea     rcx, [rsi+138h]; Event
0x140023bfa  mov     [rsi+160h], rax
0x140023c01  mov     [rax], rax
0x140023c04  mov     [rsi+134h], ebx
0x140023c0a  call    cs:__imp_KeInitializeEvent
0x140023c11  nop     dword ptr [rax+rax+00h]
0x140023c16  lea     rcx, [rsi+118h]; SpinLock
0x140023c1d  call    cs:__imp_KeInitializeSpinLock
0x140023c24  nop     dword ptr [rax+rax+00h]
0x140023c29  lea     rcx, [rsi+1B0h]; Event
0x140023c30  mov     r8b, bl; State
0x140023c33  mov     edx, ebx; Type
0x140023c35  call    cs:__imp_KeInitializeEvent
0x140023c3c  nop     dword ptr [rax+rax+00h]
0x140023c41  lea     rcx, [rsi+1C8h]; SpinLock
0x140023c48  call    cs:__imp_KeInitializeSpinLock
0x140023c4f  nop     dword ptr [rax+rax+00h]
0x140023c54  lea     rax, [rsi+1D0h]
0x140023c5b  mov     [rsi+1D8h], rax
0x140023c62  lea     rcx, [rsi+20h]; Csq
0x140023c66  mov     [rax], rax
0x140023c69  lea     r9, PdoIdlePeekNextIrp; CsqPeekNextIrp
0x140023c70  lea     rax, [rsi+60h]
0x140023c74  mov     [rsi+68h], rax
0x140023c78  lea     r8, WaitWakeRemoveIrp; CsqRemoveIrp
0x140023c7f  mov     [rax], rax
0x140023c82  lea     rdx, WaitWakeInsertIrp; CsqInsertIrp
0x140023c89  lea     rax, WaitWakeCancelComplete
0x140023c90  mov     [rsp+78h+DeviceObject], rax; CsqCompleteCanceledIrp
0x140023c95  lea     rax, WaitWakeReleaseLock
0x140023c9c  mov     qword ptr [rsp+78h+Exclusive], rax; CsqReleaseLock
0x140023ca1  lea     rax, WaitWakeAcquireLock
0x140023ca8  mov     qword ptr [rsp+78h+DeviceCharacteristics], rax; CsqAcquireLock
0x140023cad  call    cs:__imp_IoCsqInitialize
0x140023cb4  nop     dword ptr [rax+rax+00h]
0x140023cb9  lea     rax, [rsi+0B8h]
0x140023cc0  mov     [rsi+0C0h], rax
0x140023cc7  lea     rcx, [rsi+78h]; Csq
0x140023ccb  mov     [rax], rax
0x140023cce  lea     r9, PdoIdlePeekNextIrp; CsqPeekNextIrp
0x140023cd5  lea     rax, PdoIdleCancelComplete
0x140023cdc  mov     [rsp+78h+DeviceObject], rax; CsqCompleteCanceledIrp
0x140023ce1  lea     r8, PdoIdleRemoveIrp; CsqRemoveIrp
0x140023ce8  lea     rax, PdoIdleReleaseLock
0x140023cef  mov     qword ptr [rsp+78h+Exclusive], rax; CsqReleaseLock
0x140023cf4  lea     rdx, PdoIdleInsertIrp; CsqInsertIrp
0x140023cfb  lea     rax, PdoIdleAcquireLock
0x140023d02  mov     qword ptr [rsp+78h+DeviceCharacteristics], rax; CsqAcquireLock
0x140023d07  call    cs:__imp_IoCsqInitialize
0x140023d0e  nop     dword ptr [rax+rax+00h]
0x140023d13  lea     rcx, [rsi+0C8h]; Event
0x140023d1a  mov     r8b, bl; State
0x140023d1d  xor     edx, edx; Type
0x140023d1f  call    cs:__imp_KeInitializeEvent
0x140023d26  nop     dword ptr [rax+rax+00h]
0x140023d2b  movzx   eax, byte ptr [r13+5]
0x140023d30  mov     [rsi+8], eax
0x140023d33  movzx   ecx, byte ptr [r13+6]
0x140023d38  mov     [rsi+0Ch], ecx
0x140023d3b  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140023d42  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140023d49  jz      short loc_140023D74
0x140023d4b  mov     dword ptr [rsp+78h+DeviceObject], eax
0x140023d4f  lea     r9d, [rbx+0Dh]
0x140023d53  mov     dword ptr [rsp+78h+Exclusive], ecx
0x140023d57  lea     rax, WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids
0x140023d5e  mov     rcx, [rdi+558h]
0x140023d65  mov     r8d, ebx
0x140023d68  mov     dl, 4
0x140023d6a  mov     qword ptr [rsp+78h+DeviceCharacteristics], rax
0x140023d6f  call    WPP_RECORDER_SF_dd
0x140023d74  movups  xmm0, xmmword ptr [rdi+60h]
0x140023d78  movups  xmmword ptr [rsi+100h], xmm0
0x140023d7f  movzx   eax, word ptr [rdi+70h]
0x140023d83  mov     [rsi+110h], ax
0x140023d8a  mov     rax, [r13+8]
0x140023d8e  mov     rcx, [rax]
0x140023d91  mov     eax, 200h
0x140023d96  mov     rbx, [rcx]
0x140023d99  mov     rcx, [rsi+0E8h]
0x140023da0  cmp     [rcx+62h], ax
0x140023da4  jbe     short loc_140023E09
0x140023da6  mov     eax, [rcx+4C8h]
0x140023dac  test    al, 20h
0x140023dae  jnz     short loc_140023E09
0x140023db0  movzx   r8d, byte ptr [rbx+2]; InterfaceNumber
0x140023db5  or      r9d, 0FFFFFFFFh; AlternateSetting
0x140023db9  mov     rcx, [rcx+30h]; ConfigurationDescriptor
0x140023dbd  mov     rdx, rbx; StartPosition
0x140023dc0  mov     dword ptr [rsp+78h+DeviceObject], 62h ; 'b'; InterfaceProtocol
0x140023dc8  mov     dword ptr [rsp+78h+Exclusive], 6; InterfaceSubClass
0x140023dd0  mov     [rsp+78h+DeviceCharacteristics], 8; InterfaceClass
0x140023dd8  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x140023ddf  nop     dword ptr [rax+rax+00h]
0x140023de4  test    rax, rax
0x140023de7  jz      short loc_140023E09
0x140023de9  mov     rcx, [rsi+0E8h]
0x140023df0  cmp     byte ptr [rcx+553h], 0
0x140023df7  jnz     short loc_140023E09
0x140023df9  mov     byte ptr [rsi+12Fh], 1
0x140023e00  mov     al, [rax+3]
0x140023e03  mov     [rsi+131h], al
0x140023e09  cmp     byte ptr [rbx+5], 0FFh
0x140023e0d  jnz     loc_140023ED1
0x140023e13  mov     rcx, [rsi+0E8h]
0x140023e1a  or      r9d, 0FFFFFFFFh; AlternateSetting
0x140023e1e  movzx   r8d, byte ptr [rbx+2]; InterfaceNumber
0x140023e23  mov     rdx, rbx; StartPosition
0x140023e26  mov     dword ptr [rsp+78h+DeviceObject], 4; InterfaceProtocol
0x140023e2e  mov     dword ptr [rsp+78h+Exclusive], 1; InterfaceSubClass
0x140023e36  mov     rcx, [rcx+30h]; ConfigurationDescriptor
0x140023e3a  mov     [rsp+78h+DeviceCharacteristics], 7; InterfaceClass
0x140023e42  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x140023e49  nop     dword ptr [rax+rax+00h]
0x140023e4e  mov     r14, rax
0x140023e51  test    rax, rax
0x140023e54  jz      short loc_140023EC9
0x140023e56  call    Feature_WinUsb_Print__private_IsEnabledDeviceUsageNoInline
0x140023e5b  mov     rcx, [rsp+78h+arg_10]
0x140023e63  mov     rcx, [rcx+0F0h]
0x140023e6a  test    eax, eax
0x140023e6c  jz      short loc_140023E93
0x140023e6e  movzx   edx, word ptr [rcx+6Ah]
0x140023e72  movzx   ecx, word ptr [rcx+68h]
0x140023e76  call    CheckOptInWinUsbPrint
0x140023e7b  test    eax, eax
0x140023e7d  jz      short loc_140023E8C
0x140023e7f  mov     al, [r14+3]
0x140023e83  mov     byte ptr [rsi+198h], 1
0x140023e8a  jmp     short loc_140023EC3
0x140023e8c  mov     rcx, [rsi+0E8h]
0x140023e93  mov     byte ptr [rsi+12Fh], 1
0x140023e9a  movzx   edx, word ptr [rcx+6Ah]
0x140023e9e  movzx   ecx, word ptr [rcx+68h]
0x140023ea2  mov     r8b, [rbx+2]
0x140023ea6  call    CheckIppUsbAltIndex
0x140023eab  test    eax, eax
0x140023ead  jnz     short loc_140023EB8
0x140023eaf  call    IsProtectedPrintEnabled
0x140023eb4  test    eax, eax
0x140023eb6  jz      short loc_140023EC9
0x140023eb8  mov     byte ptr [rsi+130h], 1
0x140023ebf  mov     al, [r14+3]
0x140023ec3  mov     [rsi+131h], al
0x140023ec9  mov     r14d, [rsp+78h+arg_0]
  ... truncated ...
```
