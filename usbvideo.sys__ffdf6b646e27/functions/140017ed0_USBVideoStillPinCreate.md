# USBVideoStillPinCreate

- ea: `0x140017ed0`
- end: `0x140018764`
- name: `USBVideoStillPinCreate`
- size: `2196`
- prototype: `__int64 __fastcall(PVOID *PointerToPointerToItem)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, installer_update`

## callees

- `0x140001544`
- `0x140004bac`
- `0x14000c318`
- `0x14000c4c0`
- `0x14000c80c`
- `0x14000c95c`
- `0x14000ca50`
- `0x140016cd4`
- `0x14001709c`
- `0x140017ed0`
- `0x140019d34`
- `0x14001ab4c`
- `0x14001b15c`
- `0x14001b2f4`
- `0x14001d0cc`
- `0x140023934`
- `0x140039d80`
- `0x140040a70`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140018530`
- `ntoskrnl!KeInitializeEvent` at `0x140018530`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001818f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001818f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140018121`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140018121`
- `ntoskrnl!KeInitializeSpinLock` at `0x140018518`
- `ntoskrnl!KeInitializeSpinLock` at `0x140018518`
- `ks!KsPinGetConnectedFilterInterface` at `0x140017fb6`
- `ks!KsPinGetConnectedFilterInterface` at `0x140017fb6`
- `ks!_KsEdit` at `0x140018555`
- `ks!_KsEdit` at `0x140018589`
- `ks!_KsEdit` at `0x140018555`
- `ks!_KsEdit` at `0x140018589`
- `ks!KsGetDevice` at `0x140018320`
- `ks!KsGetDevice` at `0x14001832f`
- `ks!KsGetDevice` at `0x140018320`
- `ks!KsGetDevice` at `0x14001832f`
- `ks!KsAddItemToObjectBag` at `0x140018175`
- `ks!KsAddItemToObjectBag` at `0x140018175`
- `ks!KsPinGetParentFilter` at `0x140017f05`
- `ks!KsPinGetParentFilter` at `0x140017f05`

## pseudocode

```c
__int64 __fastcall USBVideoStillPinCreate(struct _KSPIN *PointerToPointerToItem)
{
  PKSFILTER ParentFilter; // rax
  PKSFILTER v3; // r13
  _QWORD *Context; // rbx
  __int64 v5; // rsi
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // r8d
  __int64 v10; // rdi
  int v11; // ebx
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  NTSTATUS v14; // ebx
  __int64 VideoStreamingInputHeader; // rax
  char *PoolWithTag; // rax
  char *v17; // rdi
  __int64 DispatcherFromFormat; // rax
  PDEVICE_OBJECT v19; // rcx
  __int64 v20; // rdx
  PUSB_INTERFACE_DESCRIPTOR FirstVideoStreamingAltSetting; // rax
  int VideoEndpointAddress; // eax
  PDEVICE_OBJECT v23; // rcx
  __int64 v24; // rdx
  char v25; // al
  int v26; // eax
  __int64 UsbDataRangeForPin; // rax
  PKSDEVICE Device; // rax
  __int64 result; // rax
  int v30; // eax
  unsigned int v31; // ebx
  int v32; // r8d
  bool v33; // cc
  PDEVICE_OBJECT v34; // rcx
  __int64 v35; // rdx
  bool v36; // cc
  __int64 OptimalAltSetting; // rax
  KSALLOCATOR_FRAMING_EX *AllocatorFraming; // rdx
  int v39; // eax
  ULONG v40; // eax
  int v41; // ecx
  char v42; // al
  _QWORD *v43; // [rsp+40h] [rbp-40h]
  PVOID Interface; // [rsp+48h] [rbp-38h] BYREF
  __int64 v45; // [rsp+50h] [rbp-30h]
  __int128 v46; // [rsp+58h] [rbp-28h] BYREF
  int v47; // [rsp+68h] [rbp-18h]
  int v48; // [rsp+6Ch] [rbp-14h]
  __int64 v49; // [rsp+70h] [rbp-10h]
  unsigned int v50; // [rsp+C0h] [rbp+40h]
  PVOID StartPosition; // [rsp+D0h] [rbp+50h] BYREF
  int v52; // [rsp+D8h] [rbp+58h] BYREF

  v52 = 0;
  Interface = 0;
  if ( !PointerToPointerToItem
    || (ParentFilter = KsPinGetParentFilter(PointerToPointerToItem), (v3 = ParentFilter) == 0)
    || (Context = ParentFilter->Context, (v43 = Context) == 0)
    || (v5 = *Context) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids);
    return 3221225485LL;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      63,
      WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids,
      *Context,
      PointerToPointerToItem->Id);
  v6 = *(_QWORD *)(v5 + 744);
  v7 = 136LL * PointerToPointerToItem->Id;
  v8 = *(_DWORD *)(v7 + v6 + 4);
  v9 = *(_DWORD *)(v7 + v6);
  if ( v8 >= v9 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 64, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids, v5, v8, v9);
    return 3221225626LL;
  }
  v10 = *(unsigned int *)(v7 + v6 + 8);
  v50 = *(_DWORD *)(v7 + v6 + 8);
  *(_DWORD *)(v7 + v6 + 4) = v8 + 1;
  if ( KsPinGetConnectedFilterInterface(PointerToPointerToItem, &IID_IKsControl, &Interface) >= 0 )
  {
    v48 = 1;
    v46 = KSPROPSETID_DevInstPropertySet;
    v49 = 0;
    LODWORD(StartPosition) = 0;
    v47 = 0;
    v11 = (*(__int64 (__fastcall **)(PVOID, __int128 *, __int64, __int128 *, int, PVOID *))(*(_QWORD *)Interface + 24LL))(
            Interface,
            &v46,
            32,
            &v46,
            32,
            &StartPosition);
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)Interface + 16LL))(Interface);
    if ( v11 >= 0 && (_DWORD)v49 == *(_DWORD *)(v5 + 724) )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_16;
      v13 = 65;
LABEL_15:
      WPP_SF_q(v12->AttachedDevice, v13, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids, v5);
LABEL_16:
      v14 = -1073741670;
LABEL_116:
      --*(_DWORD *)(136LL * PointerToPointerToItem->Id + *(_QWORD *)(v5 + 744) + 4);
      return (unsigned int)v14;
    }
    Context = v43;
  }
  if ( *(_DWORD *)(v5 + 740) )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_16;
    v13 = 66;
    goto LABEL_15;
  }
  VideoStreamingInputHeader = GetVideoStreamingInputHeader((unsigned int)v10, *(_QWORD *)(v5 + 32));
  v45 = VideoStreamingInputHeader;
  if ( !VideoStreamingInputHeader )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 67, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids, v5);
    goto LABEL_26;
  }
  if ( *(_BYTE *)(VideoStreamingInputHeader + 9) == 2 && !*(_QWORD *)(Context[8] + 8 * v10) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 68, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids, v5);
    v14 = -1073741811;
    goto LABEL_116;
  }
  PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1536, 0x220u, 0x56425355u);
  v17 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported && PoolWithTag )
    memset(PoolWithTag, 0, 0x220u);
  PointerToPointerToItem->Context = v17;
  if ( !v17 )
    goto LABEL_16;
  memset(v17, 0, 0x220u);
  v14 = KsAddItemToObjectBag(PointerToPointerToItem->Bag, v17, FreeMem);
  if ( v14 < 0 )
  {
    ExFreePoolWithTag(v17, 0x56425355u);
    goto LABEL_116;
  }
  DispatcherFromFormat = FindDispatcherFromFormat(
                           *v43,
                           PointerToPointerToItem->ConnectionFormat,
                           PointerToPointerToItem->Id);
  *((_QWORD *)v17 + 49) = DispatcherFromFormat;
  if ( !DispatcherFromFormat )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      goto LABEL_26;
    v20 = 69;
LABEL_43:
    WPP_SF_qq(v19->AttachedDevice, v20, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids, v5, v17);
LABEL_26:
    v14 = -1073741823;
    goto LABEL_116;
  }
  *((_DWORD *)v17 + 100) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)DispatcherFromFormat + 32LL))(DispatcherFromFormat);
  *(_QWORD *)v17 = v5;
  *((_QWORD *)v17 + 1) = v43[1];
  *((_QWORD *)v17 + 19) = 0;
  FirstVideoStreamingAltSetting = GetFirstVideoStreamingAltSetting(
                                    *(struct _USB_CONFIGURATION_DESCRIPTOR **)(v5 + 32),
                                    v50);
  StartPosition = FirstVideoStreamingAltSetting;
  if ( !FirstVideoStreamingAltSetting )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_26;
    v20 = 70;
    goto LABEL_43;
  }
  v17[177] = FirstVideoStreamingAltSetting->bInterfaceNumber;
  VideoEndpointAddress = GetVideoEndpointAddress(
                           *(struct _USB_CONFIGURATION_DESCRIPTOR **)(v5 + 32),
                           &FirstVideoStreamingAltSetting->bLength,
                           (UCHAR *)v17 + 376);
  v14 = VideoEndpointAddress;
  if ( VideoEndpointAddress < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_116;
    v24 = 71;
    goto LABEL_52;
  }
  v25 = *(_BYTE *)(v45 + 9);
  v17[377] = v25;
  if ( v25 == 3 )
    v26 = 1;
  else
    v26 = (unsigned __int8)IsBulkVideoEndpoint(*(PVOID *)(v5 + 32), StartPosition);
  *((_DWORD *)v17 + 95) = v26;
  UsbDataRangeForPin = GetUsbDataRangeForPin(v43, PointerToPointerToItem);
  if ( !UsbDataRangeForPin )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 72, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids, v5, v17);
    v14 = -1073741808;
    goto LABEL_116;
  }
  *((_QWORD *)v17 + 2) = UsbDataRangeForPin;
  KsGetDevice(v3);
  Device = KsGetDevice(v3);
  *((_QWORD *)v17 + 53) = Device;
  if ( !Device )
    return 3221225473LL;
  VideoEndpointAddress = NegotiateStillStreamParameters((int)Device);
  v14 = VideoEndpointAddress;
  if ( VideoEndpointAddress < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_116;
    v24 = 73;
LABEL_52:
    WPP_SF_qqD(v23->AttachedDevice, v24, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids, v5, v17, VideoEndpointAddress);
    goto LABEL_116;
  }
  if ( !*((_DWORD *)v17 + 95) )
  {
    v31 = *(_DWORD *)(v17 + 191);
    LODWORD(StartPosition) = v31;
    if ( (unsigned int)Feature_EUSB2__private_IsEnabledDeviceUsageNoInline() )
    {
      if ( v31 )
      {
        if ( *(_BYTE *)(*(_QWORD *)v17 + 3LL) )
          v33 = v31 <= 0xC000;
        else
          v33 = *(_BYTE *)(v5 + 5) ? v31 <= 0x1800 : v31 <= 0xC00;
        if ( v33 && (!*(_BYTE *)(*(_QWORD *)v17 + 4LL) || v31 <= 0x18000) )
          goto LABEL_96;
      }
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
        goto LABEL_96;
      v35 = 75;
    }
    else
    {
      if ( v31 )
      {
        v36 = *(_BYTE *)(*(_QWORD *)v17 + 3LL) ? v31 <= 0xC000 : v31 <= 0xC00;
        if ( v36 && (!*(_BYTE *)(*(_QWORD *)v17 + 4LL) || v31 <= 0x18000) )
          goto LABEL_96;
      }
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
        goto LABEL_96;
      v35 = 76;
    }
    WPP_SF_qqD(v34->AttachedDevice, v35, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids, v5, v17, v31);
LABEL_96:
    LOBYTE(v32) = v17[376];
    OptimalAltSetting = FindOptimalAltSetting(v5, v50, v32, (unsigned int)&StartPosition, (__int64)&v52);
    if ( !OptimalAltSetting )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
        goto LABEL_26;
      v20 = 77;
      goto LABEL_43;
    }
    *(_DWORD *)(v17 + 191) = (_DWORD)StartPosition;
    **((_QWORD **)v17 + 2) = OptimalAltSetting;
    *((_DWORD *)v17 + 7) = v52;
    goto LABEL_101;
  }
  **((_QWORD **)v17 + 2) = StartPosition;
  v30 = *(_DWORD *)(v17 + 191);
  *((_DWORD *)v17 + 7) = 0;
  *((_DWORD *)v17 + 8) = v30;
  if ( !v30 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 74, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids, v5, v17, 0);
    goto LABEL_26;
  }
LABEL_101:
  *((_QWORD *)v17 + 52) = PointerToPointerToItem;
  KeInitializeSpinLock((PKSPIN_LOCK)v17 + 15);
  KeInitializeEvent((PRKEVENT)(v17 + 128), NotificationEvent, 0);
  v14 = _KsEdit(PointerToPointerToItem->Bag, (PVOID *)PointerToPointerToItem, 0x88u, 0x88u, 0x56425355u);
  if ( v14 < 0
    || (v14 = _KsEdit(
                PointerToPointerToItem->Bag,
                (PVOID *)&PointerToPointerToItem->Descriptor->AllocatorFraming,
                0x70u,
                0x70u,
                0x56425355u),
        v14 < 0) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 78, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids, v5, v17, v14);
    goto LABEL_116;
  }
  AllocatorFraming = (KSALLOCATOR_FRAMING_EX *)PointerToPointerToItem->Descriptor->AllocatorFraming;
  AllocatorFraming->FramingItem[0].Frames = 10;
  v39 = *(_DWORD *)(v17 + 187);
  if ( !v39 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_26;
    v20 = 79;
    goto LABEL_43;
  }
  *((_DWORD *)v17 + 10) = v39;
  if ( (*((_DWORD *)v17 + 100) & 0x10) != 0 )
    *((_DWORD *)v17 + 10) = *(_DWORD *)(*((_QWORD *)v17 + 2) + 60LL);
  AllocatorFraming->CountItems = 1;
  v40 = *((_DWORD *)v17 + 10);
  AllocatorFraming->FramingItem[0].Flags |= 0x4000u;
  AllocatorFraming->FramingItem[0].FramingRange.Range.MaxFrameSize = v40;
  AllocatorFraming->FramingItem[0].FramingRange.Range.MinFrameSize = v40;
  AllocatorFraming->FramingItem[0].PhysicalRange.MaxFrameSize = v40;
  AllocatorFraming->FramingItem[0].PhysicalRange.MinFrameSize = v40;
  AllocatorFraming->FramingItem[0].FramingRange.Range.Stepping = 0;
  AllocatorFraming->FramingItem[0].PhysicalRange.Stepping = 0;
  v41 = *(_DWORD *)(*((_QWORD *)v17 + 2) + 72LL);
  if ( !v41 )
    v41 = *(_DWORD *)(v5 + 720);
  *((_DWORD *)v17 + 11) = v41;
  v42 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)(v5 + 680) + 64LL))(*(_QWORD *)(*(_QWORD *)(v5 + 680) + 8LL));
  v17[385] = v42;
  *((_DWORD *)v17 + 6) = 2;
  *((_DWORD *)v17 + 15) = v42 != 0 ? 8000 : 1000;
  *((_DWORD *)v17 + 16) = v42 != 0 ? 8 : 1;
  result = StillCaptureStreamInitEx(PointerToPointerToItem);
  if ( (int)result >= 0 )
  {
    ++*(_DWORD *)(v5 + 736);
    *(_QWORD *)(v43[8] + 8LL * PointerToPointerToItem->Id) = v17;
  }
  return result;
}

```

## disassembly

```asm
0x140017ed0  mov     [rsp-38h+arg_8], rbx
0x140017ed5  push    rbp
0x140017ed6  push    rsi
0x140017ed7  push    rdi
0x140017ed8  push    r12
0x140017eda  push    r13
0x140017edc  push    r14
0x140017ede  push    r15
0x140017ee0  mov     rbp, rsp
0x140017ee3  sub     rsp, 80h
0x140017eea  mov     [rbp+arg_18], 0
0x140017ef1  mov     r12, rcx
0x140017ef4  mov     [rbp+Interface], 0
0x140017efc  test    rcx, rcx
0x140017eff  jz      loc_140018715
0x140017f05  call    cs:__imp_KsPinGetParentFilter
0x140017f0c  nop     dword ptr [rax+rax+00h]
0x140017f11  mov     r13, rax
0x140017f14  test    rax, rax
0x140017f17  jz      loc_140018715
0x140017f1d  mov     rbx, [rax+10h]
0x140017f21  mov     [rbp+var_40], rbx
0x140017f25  test    rbx, rbx
0x140017f28  jz      loc_140018715
0x140017f2e  mov     rsi, [rbx]
0x140017f31  test    rsi, rsi
0x140017f34  jz      loc_140018715
0x140017f3a  mov     rcx, cs:WPP_GLOBAL_Control
0x140017f41  lea     r14, WPP_GLOBAL_Control
0x140017f48  lea     r15, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids
0x140017f4f  cmp     rcx, r14
0x140017f52  jz      short loc_140017F77
0x140017f54  cmp     byte ptr [rcx+29h], 4
0x140017f58  jb      short loc_140017F77
0x140017f5a  mov     eax, [r12+18h]
0x140017f5f  mov     edx, 3Fh ; '?'
0x140017f64  mov     rcx, [rcx+18h]
0x140017f68  mov     r9, rsi
0x140017f6b  mov     r8, r15
0x140017f6e  mov     [rsp+80h+Tag], eax
0x140017f72  call    WPP_SF_qD
0x140017f77  mov     eax, [r12+18h]
0x140017f7c  mov     rdx, [rsi+2E8h]
0x140017f83  imul    rcx, rax, 88h
0x140017f8a  mov     eax, [rcx+rdx+4]
0x140017f8e  mov     r8d, [rcx+rdx]
0x140017f92  cmp     eax, r8d
0x140017f95  jnb     loc_1400186DF
0x140017f9b  mov     edi, [rcx+rdx+8]
0x140017f9f  lea     r8, [rbp+Interface]; Interface
0x140017fa3  inc     eax
0x140017fa5  mov     [rbp+arg_0], edi
0x140017fa8  mov     [rcx+rdx+4], eax
0x140017fac  lea     rdx, IID_IKsControl; InterfaceId
0x140017fb3  mov     rcx, r12; Pin
0x140017fb6  call    cs:__imp_KsPinGetConnectedFilterInterface
0x140017fbd  nop     dword ptr [rax+rax+00h]
0x140017fc2  test    eax, eax
0x140017fc4  js      loc_14001806A
0x140017fca  movups  xmm0, cs:KSPROPSETID_DevInstPropertySet
0x140017fd1  mov     rcx, [rbp+Interface]
0x140017fd5  lea     rdx, [rbp+StartPosition]
0x140017fd9  xor     eax, eax
0x140017fdb  mov     [rbp+var_14], 1
0x140017fe2  movdqu  [rbp+var_28], xmm0
0x140017fe7  mov     [rbp+var_10], rax
0x140017feb  lea     r9, [rbp+var_28]
0x140017fef  mov     dword ptr [rbp+StartPosition], eax
0x140017ff2  mov     r8d, 20h ; ' '
0x140017ff8  mov     [rbp+var_18], eax
0x140017ffb  mov     rax, [rcx]
0x140017ffe  mov     [rsp+80h+var_58], rdx
0x140018003  lea     rdx, [rbp+var_28]
0x140018007  mov     [rsp+80h+Tag], r8d
0x14001800c  mov     rax, [rax+18h]
0x140018010  call    _guard_dispatch_icall
0x140018015  mov     rcx, [rbp+Interface]
0x140018019  mov     ebx, eax
0x14001801b  mov     rdx, [rcx]
0x14001801e  mov     rax, [rdx+10h]
0x140018022  call    _guard_dispatch_icall
0x140018027  test    ebx, ebx
0x140018029  js      short loc_140018066
0x14001802b  mov     eax, [rsi+2D4h]
0x140018031  cmp     dword ptr [rbp+var_10], eax
0x140018034  jnz     short loc_140018066
0x140018036  mov     rcx, cs:WPP_GLOBAL_Control
0x14001803d  cmp     rcx, r14
0x140018040  jz      short loc_14001805C
0x140018042  cmp     byte ptr [rcx+29h], 2
0x140018046  jb      short loc_14001805C
0x140018048  mov     edx, 41h ; 'A'
0x14001804d  mov     rcx, [rcx+18h]
0x140018051  mov     r9, rsi
0x140018054  mov     r8, r15
0x140018057  call    WPP_SF_q
0x14001805c  mov     ebx, 0C000009Ah
0x140018061  jmp     loc_1400186C4
0x140018066  mov     rbx, [rbp+var_40]
0x14001806a  cmp     dword ptr [rsi+2E4h], 0
0x140018071  jbe     short loc_14001808C
0x140018073  mov     rcx, cs:WPP_GLOBAL_Control
0x14001807a  cmp     rcx, r14
0x14001807d  jz      short loc_14001805C
0x14001807f  cmp     byte ptr [rcx+29h], 2
0x140018083  jb      short loc_14001805C
0x140018085  mov     edx, 42h ; 'B'
0x14001808a  jmp     short loc_14001804D
0x14001808c  mov     rdx, [rsi+20h]
0x140018090  mov     ecx, edi
0x140018092  call    GetVideoStreamingInputHeader
0x140018097  mov     [rbp+var_30], rax
0x14001809b  test    rax, rax
0x14001809e  jnz     short loc_1400180CE
0x1400180a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400180a7  cmp     rcx, r14
0x1400180aa  jz      short loc_1400180C4
0x1400180ac  cmp     byte ptr [rcx+29h], 2
0x1400180b0  jb      short loc_1400180C4
0x1400180b2  mov     rcx, [rcx+18h]
0x1400180b6  lea     edx, [rax+43h]
0x1400180b9  mov     r9, rsi
0x1400180bc  mov     r8, r15
0x1400180bf  call    WPP_SF_q
0x1400180c4  mov     ebx, 0C0000001h
0x1400180c9  jmp     loc_1400186C4
0x1400180ce  cmp     byte ptr [rax+9], 2
0x1400180d2  jnz     short loc_14001810F
0x1400180d4  mov     rax, [rbx+40h]
0x1400180d8  cmp     qword ptr [rax+rdi*8], 0
0x1400180dd  jnz     short loc_14001810F
0x1400180df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400180e6  cmp     rcx, r14
0x1400180e9  jz      short loc_140018105
0x1400180eb  cmp     byte ptr [rcx+29h], 2
0x1400180ef  jb      short loc_140018105
0x1400180f1  mov     rcx, [rcx+18h]
0x1400180f5  mov     edx, 44h ; 'D'
0x1400180fa  mov     r9, rsi
0x1400180fd  mov     r8, r15
0x140018100  call    WPP_SF_q
0x140018105  mov     ebx, 0C000000Dh
0x14001810a  jmp     loc_1400186C4
0x14001810f  mov     ebx, 220h
0x140018114  mov     r8d, 56425355h; Tag
0x14001811a  mov     edx, ebx; NumberOfBytes
0x14001811c  mov     ecx, 600h; PoolType
0x140018121  call    cs:__imp_ExAllocatePoolWithTag
0x140018128  nop     dword ptr [rax+rax+00h]
0x14001812d  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140018134  mov     rdi, rax
0x140018137  jnz     short loc_14001814B
0x140018139  test    rax, rax
0x14001813c  jz      short loc_14001814B
0x14001813e  mov     r8d, ebx; Size
0x140018141  xor     edx, edx; Val
0x140018143  mov     rcx, rax; void *
0x140018146  call    memset
0x14001814b  mov     [r12+10h], rdi
0x140018150  test    rdi, rdi
0x140018153  jz      loc_14001805C
0x140018159  mov     r8, rbx; Size
0x14001815c  xor     edx, edx; Val
0x14001815e  mov     rcx, rdi; void *
0x140018161  call    memset
0x140018166  mov     rcx, [r12+8]; ObjectBag
0x14001816b  lea     r8, FreeMem; Free
0x140018172  mov     rdx, rdi; Item
0x140018175  call    cs:__imp_KsAddItemToObjectBag
0x14001817c  nop     dword ptr [rax+rax+00h]
0x140018181  mov     ebx, eax
0x140018183  test    eax, eax
0x140018185  jns     short loc_1400181A0
0x140018187  mov     edx, 56425355h; Tag
0x14001818c  mov     rcx, rdi; P
0x14001818f  call    cs:__imp_ExFreePoolWithTag
0x140018196  nop     dword ptr [rax+rax+00h]
0x14001819b  jmp     loc_1400186C4
0x1400181a0  mov     rbx, [rbp+var_40]
0x1400181a4  mov     r8d, [r12+18h]
0x1400181a9  mov     rdx, [r12+60h]
0x1400181ae  mov     rcx, [rbx]
0x1400181b1  call    FindDispatcherFromFormat
0x1400181b6  mov     [rdi+188h], rax
0x1400181bd  mov     rcx, rax
0x1400181c0  test    rax, rax
0x1400181c3  jnz     short loc_1400181FB
0x1400181c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400181cc  cmp     rcx, r14
0x1400181cf  jz      loc_1400180C4
0x1400181d5  cmp     byte ptr [rcx+29h], 3
0x1400181d9  jb      loc_1400180C4
0x1400181df  lea     edx, [rax+45h]
0x1400181e2  mov     rcx, [rcx+18h]
0x1400181e6  mov     r9, rsi
0x1400181e9  mov     r8, r15
0x1400181ec  mov     qword ptr [rsp+80h+Tag], rdi
0x1400181f1  call    WPP_SF_qq
0x1400181f6  jmp     loc_1400180C4
0x1400181fb  mov     rax, [rax]
0x1400181fe  mov     rax, [rax+20h]
0x140018202  call    _guard_dispatch_icall
0x140018207  mov     edx, [rbp+arg_0]
0x14001820a  mov     [rdi+190h], eax
0x140018210  mov     [rdi], rsi
0x140018213  mov     rax, [rbx+8]
0x140018217  mov     [rdi+8], rax
0x14001821b  mov     qword ptr [rdi+98h], 0
0x140018226  mov     rcx, [rsi+20h]; DescriptorBuffer
0x14001822a  call    GetFirstVideoStreamingAltSetting
0x14001822f  mov     [rbp+StartPosition], rax
0x140018233  mov     rcx, rax
0x140018236  test    rax, rax
0x140018239  jnz     short loc_14001825A
0x14001823b  mov     rcx, cs:WPP_GLOBAL_Control
0x140018242  cmp     rcx, r14
0x140018245  jz      loc_1400180C4
0x14001824b  cmp     byte ptr [rcx+29h], 2
0x14001824f  jb      loc_1400180C4
0x140018255  lea     edx, [rax+46h]
0x140018258  jmp     short loc_1400181E2
0x14001825a  mov     al, [rax+2]
0x14001825d  lea     r8, [rdi+178h]
0x140018264  mov     [rdi+0B1h], al
0x14001826a  mov     rdx, rcx
0x14001826d  mov     rcx, [rsi+20h]; StartPosition
0x140018271  call    GetVideoEndpointAddress
0x140018276  mov     ebx, eax
0x140018278  test    eax, eax
0x14001827a  jns     short loc_1400182A4
0x14001827c  mov     rcx, cs:WPP_GLOBAL_Control
0x140018283  cmp     rcx, r14
0x140018286  jz      loc_1400186C4
0x14001828c  cmp     byte ptr [rcx+29h], 2
0x140018290  jb      loc_1400186C4
0x140018296  mov     edx, 47h ; 'G'
0x14001829b  mov     dword ptr [rsp+80h+var_58], eax
0x14001829f  jmp     loc_1400186B0
0x1400182a4  mov     rax, [rbp+var_30]
0x1400182a8  mov     al, [rax+9]
0x1400182ab  mov     [rdi+179h], al
0x1400182b1  cmp     al, 3
0x1400182b3  jnz     short loc_1400182BC
0x1400182b5  mov     eax, 1
0x1400182ba  jmp     short loc_1400182CC
0x1400182bc  mov     rdx, [rbp+StartPosition]; StartPosition
0x1400182c0  mov     rcx, [rsi+20h]; DescriptorBuffer
0x1400182c4  call    IsBulkVideoEndpoint
0x1400182c9  movzx   eax, al
0x1400182cc  mov     rcx, [rbp+var_40]
0x1400182d0  mov     rdx, r12
0x1400182d3  mov     [rdi+17Ch], eax
0x1400182d9  call    GetUsbDataRangeForPin
0x1400182de  mov     rbx, rax
0x1400182e1  test    rax, rax
0x1400182e4  jnz     short loc_140018319
0x1400182e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400182ed  cmp     rcx, r14
0x1400182f0  jz      short loc_14001830F
0x1400182f2  cmp     byte ptr [rcx+29h], 2
0x1400182f6  jb      short loc_14001830F
0x1400182f8  mov     rcx, [rcx+18h]
0x1400182fc  lea     edx, [rax+48h]
0x1400182ff  mov     r9, rsi
0x140018302  mov     qword ptr [rsp+80h+Tag], rdi
0x140018307  mov     r8, r15
0x14001830a  call    WPP_SF_qq
0x14001830f  mov     ebx, 0C0000010h
0x140018314  jmp     loc_1400186C4
0x140018319  mov     rcx, r13; Object
0x14001831c  mov     [rdi+10h], rbx
0x140018320  call    cs:__imp_KsGetDevice
0x140018327  nop     dword ptr [rax+rax+00h]
0x14001832c  mov     rcx, r13; Object
0x14001832f  call    cs:__imp_KsGetDevice
0x140018336  nop     dword ptr [rax+rax+00h]
0x14001833b  xor     r13d, r13d
0x14001833e  mov     [rdi+1A8h], rax
0x140018345  test    rax, rax
0x140018348  jnz     short loc_140018354
0x14001834a  mov     eax, 0C0000001h
0x14001834f  jmp     loc_140018748
0x140018354  mov     r9, rbx
0x140018357  mov     rdx, rdi
0x14001835a  mov     rcx, rax; int
0x14001835d  call    NegotiateStillStreamParameters
0x140018362  mov     ebx, eax
0x140018364  test    eax, eax
0x140018366  jns     short loc_14001838C
0x140018368  mov     rcx, cs:WPP_GLOBAL_Control
0x14001836f  cmp     rcx, r14
0x140018372  jz      loc_1400186C4
0x140018378  cmp     byte ptr [rcx+29h], 2
0x14001837c  jb      loc_1400186C4
0x140018382  mov     edx, 49h ; 'I'
0x140018387  jmp     loc_14001829B
0x14001838c  cmp     [rdi+17Ch], r13d
0x140018393  jz      short loc_1400183F0
0x140018395  mov     rax, [rdi+10h]
0x140018399  mov     rcx, [rbp+StartPosition]
  ... truncated ...
```
