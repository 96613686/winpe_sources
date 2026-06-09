# USBVideoPinCreate

- ea: `0x1400171d0`
- end: `0x140017e46`
- name: `USBVideoPinCreate`
- size: `3190`
- prototype: `__int64 __fastcall(PKSPIN Pin)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, installer_update`

## callees

- `0x140001544`
- `0x140004bac`
- `0x1400051e4`
- `0x140009f34`
- `0x14000c318`
- `0x14000c4c0`
- `0x14000c80c`
- `0x14000c95c`
- `0x14000ca50`
- `0x140011bc0`
- `0x14001461c`
- `0x140016cd4`
- `0x14001709c`
- `0x1400171d0`
- `0x140019d34`
- `0x14001ab4c`
- `0x14001b15c`
- `0x14001d0cc`
- `0x14002511c`
- `0x140040a70`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140017abd`
- `ntoskrnl!KeInitializeEvent` at `0x140017abd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001746e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001746e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140017401`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140017401`
- `ntoskrnl!KeInitializeSpinLock` at `0x140017aa5`
- `ntoskrnl!KeInitializeSpinLock` at `0x140017aa5`
- `ks!KsPinGetConnectedFilterInterface` at `0x140017358`
- `ks!KsPinGetConnectedFilterInterface` at `0x140017358`
- `ks!KsPinRegisterPowerCallbacks` at `0x140017d0d`
- `ks!KsPinRegisterPowerCallbacks` at `0x140017d0d`
- `ks!_KsEdit` at `0x140017ae1`
- `ks!_KsEdit` at `0x140017b13`
- `ks!_KsEdit` at `0x140017ae1`
- `ks!_KsEdit` at `0x140017b13`
- `ks!KsGetDevice` at `0x140017253`
- `ks!KsGetDevice` at `0x140017253`
- `ks!KsAddItemToObjectBag` at `0x140017454`
- `ks!KsAddItemToObjectBag` at `0x140017454`
- `ks!KsPinGetParentFilter` at `0x14001721d`
- `ks!KsPinGetParentFilter` at `0x14001721d`

## pseudocode

```c
__int64 __fastcall USBVideoPinCreate(PKSPIN Pin)
{
  PKSFILTER ParentFilter; // rax
  _QWORD *Context; // r13
  __int64 v4; // rsi
  PKSDEVICE Device; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  unsigned int v9; // eax
  unsigned int v10; // r8d
  char *v11; // rdi
  int v12; // ebx
  NTSTATUS v13; // ebx
  bool v14; // zf
  char *PoolWithTag; // rax
  __int64 DispatcherFromFormat; // rax
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  unsigned __int16 v19; // ax
  PUSB_INTERFACE_DESCRIPTOR FirstVideoStreamingAltSetting; // rax
  PUSB_INTERFACE_DESCRIPTOR v21; // r13
  int VideoEndpointAddress; // eax
  PDEVICE_OBJECT v23; // rcx
  __int64 v24; // rdx
  __int64 UsbDataRangeForPin; // rax
  __int64 v26; // r13
  PKSDATAFORMAT ConnectionFormat; // rcx
  LONGLONG v28; // rax
  _DWORD *v29; // rdx
  LONGLONG v30; // rax
  LONGLONG v31; // rax
  LONGLONG v32; // rax
  LONGLONG v33; // rax
  LONGLONG v34; // rax
  __int64 v35; // rax
  __int64 v36; // rcx
  int v37; // eax
  unsigned int v38; // ebx
  int v39; // r8d
  bool v40; // cc
  bool v41; // cc
  __int64 OptimalAltSetting; // rax
  char v43; // al
  const KSPIN_DESCRIPTOR_EX *Descriptor; // rax
  KSALLOCATOR_FRAMING_EX *AllocatorFraming; // rbx
  int v46; // ecx
  int v47; // r9d
  __int64 v48; // r9
  ULONG v49; // eax
  unsigned int v50; // edx
  unsigned __int64 v51; // rcx
  int v52; // eax
  _QWORD *v53; // [rsp+50h] [rbp-19h]
  int v54[2]; // [rsp+58h] [rbp-11h]
  __int128 v55; // [rsp+70h] [rbp+7h] BYREF
  int v56; // [rsp+80h] [rbp+17h]
  int v57; // [rsp+84h] [rbp+1Bh]
  __int64 v58; // [rsp+88h] [rbp+1Fh]
  PUSB_INTERFACE_DESCRIPTOR v59; // [rsp+D0h] [rbp+67h] BYREF
  int v60; // [rsp+E0h] [rbp+77h] BYREF
  PVOID Interface; // [rsp+E8h] [rbp+7Fh] BYREF

  Interface = 0;
  v60 = 0;
  if ( Pin
    && (ParentFilter = KsPinGetParentFilter(Pin)) != 0
    && (Context = ParentFilter->Context, (v53 = Context) != 0)
    && (v4 = *Context) != 0 )
  {
    Device = KsGetDevice(ParentFilter);
    *(_QWORD *)v54 = Device;
    if ( !Device )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids, v4);
      return 3221225473LL;
    }
    if ( Device->DevicePowerState != PowerDeviceD0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids, v4);
      return 3221225635LL;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids, v4, Pin->Id);
    v7 = *(_QWORD *)(v4 + 744);
    v8 = 136LL * Pin->Id;
    v9 = *(_DWORD *)(v8 + v7 + 4);
    v10 = *(_DWORD *)(v8 + v7);
    if ( v9 < v10 )
    {
      *(_DWORD *)(v8 + v7 + 4) = v9 + 1;
      v11 = 0;
      if ( KsPinGetConnectedFilterInterface(Pin, &IID_IKsControl, &Interface) >= 0 )
      {
        v58 = 0;
        v55 = KSPROPSETID_DevInstPropertySet;
        LODWORD(v59) = 0;
        v56 = 0;
        v57 = 1;
        v12 = (*(__int64 (__fastcall **)(PVOID, __int128 *, __int64, __int128 *, int, PUSB_INTERFACE_DESCRIPTOR *))(*(_QWORD *)Interface + 24LL))(
                Interface,
                &v55,
                32,
                &v55,
                32,
                &v59);
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)Interface + 16LL))(Interface);
        if ( v12 >= 0 && (_DWORD)v58 == *(_DWORD *)(v4 + 724) )
          goto LABEL_22;
      }
      v14 = Pin->DataFlow == KSPIN_DATAFLOW_OUT ? *(_DWORD *)(v4 + 740) == 0 : *(_DWORD *)(v4 + 736) == 0;
      if ( !v14 )
        goto LABEL_22;
      PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1536, 0x220u, 0x56425355u);
      v11 = PoolWithTag;
      if ( !ExPoolZeroingNativelySupported && PoolWithTag )
        memset(PoolWithTag, 0, 0x220u);
      Pin->Context = v11;
      if ( !v11 )
      {
LABEL_22:
        v13 = -1073741670;
LABEL_184:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_qqD(
            WPP_GLOBAL_Control->AttachedDevice,
            61,
            WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids,
            v4,
            v11,
            v13);
        goto LABEL_187;
      }
      memset(v11, 0, 0x220u);
      v13 = KsAddItemToObjectBag(Pin->Bag, v11, FreeMem);
      if ( v13 < 0 )
      {
        ExFreePoolWithTag(v11, 0x56425355u);
        goto LABEL_184;
      }
      DispatcherFromFormat = FindDispatcherFromFormat(*Context, Pin->ConnectionFormat, Pin->Id);
      *((_QWORD *)v11 + 49) = DispatcherFromFormat;
      if ( !DispatcherFromFormat )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          goto LABEL_38;
        v18 = 45;
LABEL_37:
        WPP_SF_qq(v17->AttachedDevice, v18, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids, v4, v11);
LABEL_38:
        v13 = -1073741823;
        goto LABEL_184;
      }
      *((_DWORD *)v11 + 100) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)DispatcherFromFormat + 32LL))(DispatcherFromFormat);
      v19 = *(_WORD *)(v4 + 364);
      if ( v19 >= 0x110u )
        *((_DWORD *)v11 + 45) = v19 < 0x150u ? 34 : 48;
      else
        *((_DWORD *)v11 + 45) = 26;
      *(_QWORD *)v11 = v4;
      *((_QWORD *)v11 + 1) = Context[1];
      *((_QWORD *)v11 + 19) = 0;
      FirstVideoStreamingAltSetting = GetFirstVideoStreamingAltSetting(
                                        *(struct _USB_CONFIGURATION_DESCRIPTOR **)(v4 + 32),
                                        Pin->Id);
      v59 = FirstVideoStreamingAltSetting;
      v21 = FirstVideoStreamingAltSetting;
      if ( !FirstVideoStreamingAltSetting )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          goto LABEL_38;
        v18 = 46;
        goto LABEL_37;
      }
      v11[177] = FirstVideoStreamingAltSetting->bInterfaceNumber;
      VideoEndpointAddress = GetVideoEndpointAddress(
                               *(struct _USB_CONFIGURATION_DESCRIPTOR **)(v4 + 32),
                               &FirstVideoStreamingAltSetting->bLength,
                               (UCHAR *)v11 + 376);
      v13 = VideoEndpointAddress;
      if ( VideoEndpointAddress < 0 )
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            goto LABEL_184;
          v24 = 47;
LABEL_50:
          WPP_SF_qqD(
            v23->AttachedDevice,
            v24,
            WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids,
            v4,
            v11,
            VideoEndpointAddress);
          goto LABEL_184;
        }
        goto LABEL_187;
      }
      *((_DWORD *)v11 + 95) = (unsigned __int8)IsBulkVideoEndpoint(*(PVOID *)(v4 + 32), v21);
      v11[377] = 0;
      UsbDataRangeForPin = GetUsbDataRangeForPin(v53, Pin);
      v26 = UsbDataRangeForPin;
      if ( !UsbDataRangeForPin )
      {
        v13 = -1073741808;
        goto LABEL_184;
      }
      *((_QWORD *)v11 + 2) = UsbDataRangeForPin;
      ConnectionFormat = Pin->ConnectionFormat;
      v28 = *(&ConnectionFormat->Alignment + 4) - *(_QWORD *)&KSDATAFORMAT_SUBTYPE_DVSD.Data1;
      if ( !v28 )
        v28 = *(&ConnectionFormat->Alignment + 5) - *(_QWORD *)KSDATAFORMAT_SUBTYPE_DVSD.Data4;
      v29 = (_DWORD *)(v26 + 52);
      if ( v28 || *v29 != 333667 )
      {
        v30 = *(&ConnectionFormat->Alignment + 4) - *(_QWORD *)&KSDATAFORMAT_SUBTYPE_DVSD.Data1;
        if ( !v30 )
          v30 = *(&ConnectionFormat->Alignment + 5) - *(_QWORD *)KSDATAFORMAT_SUBTYPE_DVSD.Data4;
        if ( v30 || *v29 != 400000 )
        {
          v31 = *(&ConnectionFormat->Alignment + 4) - *(_QWORD *)&KSDATAFORMAT_SUBTYPE_DVSL.Data1;
          if ( !v31 )
            v31 = *(&ConnectionFormat->Alignment + 5) - *(_QWORD *)KSDATAFORMAT_SUBTYPE_DVSL.Data4;
          if ( v31 || *v29 != 333667 )
          {
            v32 = *(&ConnectionFormat->Alignment + 4) - *(_QWORD *)&KSDATAFORMAT_SUBTYPE_DVSL.Data1;
            if ( !v32 )
              v32 = *(&ConnectionFormat->Alignment + 5) - *(_QWORD *)KSDATAFORMAT_SUBTYPE_DVSL.Data4;
            if ( v32 || *v29 != 400000 )
            {
              v33 = *(&ConnectionFormat->Alignment + 4) - *(_QWORD *)&KSDATAFORMAT_SUBTYPE_DVHD.Data1;
              if ( !v33 )
                v33 = *(&ConnectionFormat->Alignment + 5) - *(_QWORD *)KSDATAFORMAT_SUBTYPE_DVHD.Data4;
              if ( v33 || *v29 != 333667 )
              {
                v34 = *(&ConnectionFormat->Alignment + 4) - *(_QWORD *)&KSDATAFORMAT_SUBTYPE_DVHD.Data1;
                if ( !v34 )
                  v34 = *(&ConnectionFormat->Alignment + 5) - *(_QWORD *)KSDATAFORMAT_SUBTYPE_DVHD.Data4;
                if ( v34 || *v29 != 400000 )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                  {
                    WPP_SF_qq(
                      WPP_GLOBAL_Control->AttachedDevice,
                      48,
                      WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids,
                      v4,
                      v11);
                  }
                }
                else
                {
                  *(_DWORD *)(v4 + 8) = 5044;
                }
              }
              else
              {
                *(_DWORD *)(v4 + 8) = 5043;
              }
            }
            else
            {
              *(_DWORD *)(v4 + 8) = 5041;
            }
          }
          else
          {
            *(_DWORD *)(v4 + 8) = 5039;
          }
        }
        else
        {
          *(_DWORD *)(v4 + 8) = 5040;
        }
      }
      else
      {
        *(_DWORD *)(v4 + 8) = 5038;
      }
      v11[387] = 0;
      v35 = *(_QWORD *)(v26 + 144) - 0x424866292017BE05LL;
      if ( *(_QWORD *)(v26 + 144) == 0x424866292017BE05LL )
        v35 = *(_QWORD *)(v26 + 152) + 0x636443B8E5811256LL;
      if ( v35 )
      {
        v11[386] = 0;
      }
      else
      {
        v11[386] = 1;
        v36 = *(_QWORD *)(v26 + 128) - *(_QWORD *)&MEDIASUBTYPE_H264.Data1;
        if ( !v36 )
          v36 = *(_QWORD *)(v26 + 136) - *(_QWORD *)MEDIASUBTYPE_H264.Data4;
        if ( v36 )
        {
          v11[387] = 1;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids, v4, v11);
        }
      }
      v14 = *(_QWORD *)(v53[9] + 8LL * Pin->Id) == 2;
      *((_QWORD *)v11 + 53) = *(_QWORD *)v54;
      v11[440] = v14;
      *((_QWORD *)v11 + 54) = v53;
      VideoEndpointAddress = NegotiateVideoStreamParameters(v54[0]);
      v13 = VideoEndpointAddress;
      if ( VideoEndpointAddress < 0 )
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            goto LABEL_184;
          v24 = 50;
          goto LABEL_50;
        }
LABEL_187:
        --*(_DWORD *)(136LL * Pin->Id + *(_QWORD *)(v4 + 744) + 4);
        return (unsigned int)v13;
      }
      if ( *(_WORD *)(v4 + 364) >= 0x110u )
      {
        if ( !*(_BYTE *)(v26 + 81) && (v11[214] & 2) != 0 )
          *((_DWORD *)v11 + 102) |= 4u;
        if ( *(_BYTE *)(v26 + 80) )
          *((_DWORD *)v11 + 102) |= 2u;
      }
      if ( *((_DWORD *)v11 + 95) )
      {
        **((_QWORD **)v11 + 2) = v59;
        v37 = *(_DWORD *)(v11 + 206);
        *((_DWORD *)v11 + 7) = 0;
        *((_DWORD *)v11 + 8) = v37;
        if ( !v37 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_qqD(
              WPP_GLOBAL_Control->AttachedDevice,
              51,
              WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids,
              v4,
              v11,
              0);
          goto LABEL_38;
        }
      }
      else
      {
        v38 = *(_DWORD *)(v11 + 206);
        LODWORD(v59) = v38;
        if ( (unsigned int)Feature_EUSB2__private_IsEnabledDeviceUsageNoInline() )
        {
          if ( !v38
            || (*(_BYTE *)(*(_QWORD *)v11 + 3LL)
              ? (v40 = v38 <= 0xC000)
              : !*(_BYTE *)(v4 + 5)
              ? (v40 = v38 <= 0xC00)
              : (v40 = v38 <= 0x1800),
                !v40 || *(_BYTE *)(*(_QWORD *)v11 + 4LL) && v38 > 0x18000) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
              WPP_SF_qqLddd(
                WPP_GLOBAL_Control->AttachedDevice,
                *(unsigned __int8 *)(*(_QWORD *)v11 + 5LL),
                *(unsigned __int8 *)(*(_QWORD *)v11 + 4LL),
                v4,
                v11,
                v38,
                *(unsigned __int8 *)(*(_QWORD *)v11 + 3LL),
                *(unsigned __int8 *)(*(_QWORD *)v11 + 4LL),
                *(unsigned __int8 *)(*(_QWORD *)v11 + 5LL));
          }
        }
        else if ( !v38
               || (*(_BYTE *)(*(_QWORD *)v11 + 3LL) ? (v41 = v38 <= 0xC000) : (v41 = v38 <= 0xC00),
                   !v41 || *(_BYTE *)(*(_QWORD *)v11 + 4LL) && v38 > 0x18000) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
            WPP_SF_qqD(
              WPP_GLOBAL_Control->AttachedDevice,
              53,
              WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids,
              v4,
              v11,
              v38);
        }
        LOBYTE(v39) = v11[376];
        OptimalAltSetting = FindOptimalAltSetting(v4, Pin->Id, v39, (unsigned int)&v59, (__int64)&v60);
        if ( !OptimalAltSetting )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
            goto LABEL_38;
          v18 = 54;
          goto LABEL_37;
        }
        *(_DWORD *)(v11 + 206) = (_DWORD)v59;
        **((_QWORD **)v11 + 2) = OptimalAltSetting;
        *((_DWORD *)v11 + 7) = v60;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_qqD(
          WPP_GLOBAL_Control->AttachedDevice,
          55,
          WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids,
          v4,
          v11,
          *((unsigned __int16 *)v11 + 100));
      v43 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)(v4 + 680) + 64LL))(*(_QWORD *)(*(_QWORD *)(v4 + 680) + 8LL));
      v11[385] = v43;
      *((_DWORD *)v11 + 15) = v43 != 0 ? 8000 : 1000;
      *((_DWORD *)v11 + 16) = v43 != 0 ? 8 : 1;
      KeInitializeSpinLock((PKSPIN_LOCK)v11 + 15);
      KeInitializeEvent((PRKEVENT)(v11 + 128), NotificationEvent, 0);
      v13 = _KsEdit(Pin->Bag, (PVOID *)Pin, 0x88u, 0x88u, 0x56425355u);
      if ( v13 < 0
        || (v13 = _KsEdit(Pin->Bag, (PVOID *)&Pin->Descriptor->AllocatorFraming, 0x70u, 0x70u, 0x56425355u), v13 < 0) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_qqD(
              WPP_GLOBAL_Control->AttachedDevice,
              56,
              WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids,
              v4,
              v11,
              v13);
          goto LABEL_184;
        }
        goto LABEL_187;
      }
      Descriptor = Pin->Descriptor;
      Pin->StreamHeaderSize = 128;
      AllocatorFraming = (KSALLOCATOR_FRAMING_EX *)Descriptor->AllocatorFraming;
      AllocatorFraming->FramingItem[0].Frames = 10;
      v46 = *((_DWORD *)v11 + 100);
      if ( (v46 & 0x20) != 0 || (*((_DWORD *)v11 + 102) & 0x20) != 0 )
      {
        v48 = *(unsigned int *)(v11 + 202);
        if ( !(_DWORD)v48 )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            goto LABEL_38;
          v18 = 57;
          goto LABEL_37;
        }
      }
      else
      {
        if ( *((_DWORD *)v11 + 95) || Pin->DataFlow != KSPIN_DATAFLOW_OUT )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            goto LABEL_38;
          v18 = 58;
          goto LABEL_37;
        }
        if ( v11[385] )
          v47 = 96 * *(_DWORD *)(v11 + 206);
        else
          v47 = 12 * *(_DWORD *)(v11 + 206);
        v48 = (v47 & 0xFFFFF000) + 4096;
      }
      *((_DWORD *)v11 + 10) = v48;
      if ( (v46 & 8) != 0 )
      {
        v48 = *(unsigned int *)(*((_QWORD *)v11 + 2) + 60LL);
        *((_DWORD *)v11 + 10) = v48;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_dd(
          WPP_GLOBAL_Control->AttachedDevice,
          59,
          WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids,
          v48,
          AllocatorFraming->FramingItem[0].Frames);
      AllocatorFraming->CountItems = 1;
      v49 = *((_DWORD *)v11 + 10);
      AllocatorFraming->FramingItem[0].Flags |= 0x4000u;
      AllocatorFraming->FramingItem[0].FramingRange.Range.MaxFrameSize = v49;
      AllocatorFraming->FramingItem[0].FramingRange.Range.MinFrameSize = v49;
      AllocatorFraming->FramingItem[0].PhysicalRange.MaxFrameSize = v49;
      AllocatorFraming->FramingItem[0].PhysicalRange.MinFrameSize = v49;
      AllocatorFraming->FramingItem[0].FramingRange.Range.Stepping = 0;
      AllocatorFraming->FramingItem[0].PhysicalRange.Stepping = 0;
      v50 = *(_DWORD *)(*((_QWORD *)v11 + 2) + 72LL);
      if ( !v50 )
        v50 = *(_DWORD *)(v4 + 720);
      v51 = v50 * (unsigned __int64)*((unsigned int *)v11 + 47);
      *((_DWORD *)v11 + 11) = v50;
      v52 = 1;
      if ( (unsigned int)(v51 / 0x989680) > 1 )
        v52 = v51 / 0x989680;
      *((_DWORD *)v11 + 12) = v52;
      if ( Pin->DataFlow == KSPIN_DATAFLOW_OUT )
      {
        *((_DWORD *)v11 + 6) = 0;
        v13 = CaptureStreamInitEx(Pin);
        if ( v13 >= 0 )
        {
          ++*(_DWORD *)(v4 + 736);
          goto LABEL_173;
        }
      }
      else
      {
        *((_DWORD *)v11 + 6) = 1;
        v13 = FrameRenderStreamInit(Pin);
        if ( v13 >= 0 )
        {
          ++*(_DWORD *)(v4 + 740);
LABEL_173:
          *(_QWORD *)(v53[8] + 8LL * Pin->Id) = v11;
          if ( *((_DWORD *)v53 + 15) == -1 )
            *((_DWORD *)v53 + 15) = Pin->Id;
        }
      }
      v40 = *((_DWORD *)v11 + 6) <= 1u;
      *((_QWORD *)v11 + 52) = Pin;
      if ( v40 )
        KsPinRegisterPowerCallbacks(Pin, USBVideoPinGoToStandby, USBVideoPinReturnFromStandby);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids, v4, v11);
      return (unsigned int)v13;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids, v4, v9, v10);
    return 3221225626LL;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x1400171d0  mov     [rsp-8+arg_8], rbx
0x1400171d5  push    rbp
0x1400171d6  push    rsi
0x1400171d7  push    rdi
0x1400171d8  push    r12
0x1400171da  push    r13
0x1400171dc  push    r14
0x1400171de  push    r15
0x1400171e0  lea     rbp, [rsp-27h]
0x1400171e5  sub     rsp, 90h
0x1400171ec  xor     ebx, ebx
0x1400171ee  mov     dword ptr [rbp+57h+var_60], 2017BE05h
0x1400171f5  mov     [rbp+57h+Interface], rbx
0x1400171f9  mov     r15, rcx
0x1400171fc  mov     [rbp+57h+arg_10], ebx
0x1400171ff  mov     dword ptr [rbp+57h+var_60+4], 42486629h
0x140017206  mov     dword ptr [rbp+57h+var_60+8], 1A7EEDAAh
0x14001720d  mov     dword ptr [rbp+57h+var_60+0Ch], 9C9BBC47h
0x140017214  test    rcx, rcx
0x140017217  jz      loc_140017DF7
0x14001721d  call    cs:__imp_KsPinGetParentFilter
0x140017224  nop     dword ptr [rax+rax+00h]
0x140017229  test    rax, rax
0x14001722c  jz      loc_140017DF7
0x140017232  mov     r13, [rax+10h]
0x140017236  mov     [rbp+57h+var_70], r13
0x14001723a  test    r13, r13
0x14001723d  jz      loc_140017DF7
0x140017243  mov     rsi, [r13+0]
0x140017247  test    rsi, rsi
0x14001724a  jz      loc_140017DF7
0x140017250  mov     rcx, rax; Object
0x140017253  call    cs:__imp_KsGetDevice
0x14001725a  nop     dword ptr [rax+rax+00h]
0x14001725f  mov     qword ptr [rbp+57h+var_68], rax
0x140017263  test    rax, rax
0x140017266  jnz     short loc_1400172A1
0x140017268  mov     rcx, cs:WPP_GLOBAL_Control
0x14001726f  lea     r14, WPP_GLOBAL_Control
0x140017276  cmp     rcx, r14
0x140017279  jz      short loc_140017297
0x14001727b  cmp     byte ptr [rcx+29h], 2
0x14001727f  jb      short loc_140017297
0x140017281  mov     rcx, [rcx+18h]
0x140017285  lea     edx, [rbx+29h]
0x140017288  mov     r9, rsi
0x14001728b  lea     r8, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids
0x140017292  call    WPP_SF_q
0x140017297  mov     eax, 0C0000001h
0x14001729c  jmp     loc_140017E2A
0x1400172a1  cmp     dword ptr [rax+38h], 1
0x1400172a5  jz      short loc_1400172E2
0x1400172a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400172ae  lea     r14, WPP_GLOBAL_Control
0x1400172b5  cmp     rcx, r14
0x1400172b8  jz      short loc_1400172D8
0x1400172ba  cmp     byte ptr [rcx+29h], 2
0x1400172be  jb      short loc_1400172D8
0x1400172c0  mov     rcx, [rcx+18h]
0x1400172c4  lea     r8, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids
0x1400172cb  mov     edx, 2Ah ; '*'
0x1400172d0  mov     r9, rsi
0x1400172d3  call    WPP_SF_q
0x1400172d8  mov     eax, 0C00000A3h
0x1400172dd  jmp     loc_140017E2A
0x1400172e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400172e9  lea     r14, WPP_GLOBAL_Control
0x1400172f0  lea     r12, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids
0x1400172f7  cmp     rcx, r14
0x1400172fa  jz      short loc_14001731E
0x1400172fc  cmp     byte ptr [rcx+29h], 4
0x140017300  jb      short loc_14001731E
0x140017302  mov     eax, [r15+18h]
0x140017306  mov     edx, 2Bh ; '+'
0x14001730b  mov     rcx, [rcx+18h]
0x14001730f  mov     r9, rsi
0x140017312  mov     r8, r12
0x140017315  mov     [rsp+0C0h+Tag], eax
0x140017319  call    WPP_SF_qD
0x14001731e  mov     eax, [r15+18h]
0x140017322  mov     rdx, [rsi+2E8h]
0x140017329  imul    rcx, rax, 88h
0x140017330  mov     eax, [rcx+rdx+4]
0x140017334  mov     r8d, [rcx+rdx]
0x140017338  cmp     eax, r8d
0x14001733b  jnb     loc_140017DC1
0x140017341  inc     eax
0x140017343  lea     r8, [rbp+57h+Interface]; Interface
0x140017347  mov     [rcx+rdx+4], eax
0x14001734b  mov     rdi, rbx
0x14001734e  lea     rdx, IID_IKsControl; InterfaceId
0x140017355  mov     rcx, r15; Pin
0x140017358  call    cs:__imp_KsPinGetConnectedFilterInterface
0x14001735f  nop     dword ptr [rax+rax+00h]
0x140017364  mov     r8d, 20h ; ' '
0x14001736a  test    eax, eax
0x14001736c  js      short loc_1400173DE
0x14001736e  movups  xmm0, cs:KSPROPSETID_DevInstPropertySet
0x140017375  mov     rcx, [rbp+57h+Interface]
0x140017379  lea     rdx, [rbp+57h+arg_0]
0x14001737d  mov     [rbp+57h+var_38], rbx
0x140017381  lea     r9, [rbp+57h+var_50]
0x140017385  movdqu  [rbp+57h+var_50], xmm0
0x14001738a  mov     dword ptr [rbp+57h+arg_0], ebx
0x14001738d  mov     [rbp+57h+var_40], ebx
0x140017390  mov     [rbp+57h+var_3C], 1
0x140017397  mov     rax, [rcx]
0x14001739a  mov     [rsp+0C0h+var_98], rdx
0x14001739f  lea     rdx, [rbp+57h+var_50]
0x1400173a3  mov     [rsp+0C0h+Tag], r8d
0x1400173a8  mov     rax, [rax+18h]
0x1400173ac  call    _guard_dispatch_icall
0x1400173b1  mov     rcx, [rbp+57h+Interface]
0x1400173b5  mov     ebx, eax
0x1400173b7  mov     rdx, [rcx]
0x1400173ba  mov     rax, [rdx+10h]
0x1400173be  call    _guard_dispatch_icall
0x1400173c3  test    ebx, ebx
0x1400173c5  js      short loc_1400173DC
0x1400173c7  mov     eax, [rsi+2D4h]
0x1400173cd  cmp     dword ptr [rbp+57h+var_38], eax
0x1400173d0  jnz     short loc_1400173DC
0x1400173d2  mov     ebx, 0C000009Ah
0x1400173d7  jmp     loc_140017D7A
0x1400173dc  xor     ebx, ebx
0x1400173de  cmp     dword ptr [r15+74h], 2
0x1400173e3  jnz     loc_14001747F
0x1400173e9  cmp     [rsi+2E4h], ebx
0x1400173ef  ja      short loc_1400173D2
0x1400173f1  mov     edx, 220h; NumberOfBytes
0x1400173f6  mov     ecx, 600h; PoolType
0x1400173fb  mov     r8d, 56425355h; Tag
0x140017401  call    cs:__imp_ExAllocatePoolWithTag
0x140017408  nop     dword ptr [rax+rax+00h]
0x14001740d  cmp     cs:ExPoolZeroingNativelySupported, bl
0x140017413  mov     rdi, rax
0x140017416  jnz     short loc_14001742D
0x140017418  test    rax, rax
0x14001741b  jz      short loc_14001742D
0x14001741d  xor     edx, edx; Val
0x14001741f  mov     r8d, 220h; Size
0x140017425  mov     rcx, rax; void *
0x140017428  call    memset
0x14001742d  mov     [r15+10h], rdi
0x140017431  test    rdi, rdi
0x140017434  jz      short loc_1400173D2
0x140017436  xor     edx, edx; Val
0x140017438  mov     r8d, 220h; Size
0x14001743e  mov     rcx, rdi; void *
0x140017441  call    memset
0x140017446  mov     rcx, [r15+8]; ObjectBag
0x14001744a  lea     r8, FreeMem; Free
0x140017451  mov     rdx, rdi; Item
0x140017454  call    cs:__imp_KsAddItemToObjectBag
0x14001745b  nop     dword ptr [rax+rax+00h]
0x140017460  mov     ebx, eax
0x140017462  test    eax, eax
0x140017464  jns     short loc_14001748A
0x140017466  mov     edx, 56425355h; Tag
0x14001746b  mov     rcx, rdi; P
0x14001746e  call    cs:__imp_ExFreePoolWithTag
0x140017475  nop     dword ptr [rax+rax+00h]
0x14001747a  jmp     loc_140017D7A
0x14001747f  cmp     [rsi+2E0h], ebx
0x140017485  jmp     loc_1400173EF
0x14001748a  mov     r8d, [r15+18h]
0x14001748e  mov     rdx, [r15+60h]
0x140017492  mov     rcx, [r13+0]
0x140017496  call    FindDispatcherFromFormat
0x14001749b  mov     [rdi+188h], rax
0x1400174a2  mov     rcx, rax
0x1400174a5  test    rax, rax
0x1400174a8  jnz     short loc_1400174DD
0x1400174aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400174b1  cmp     rcx, r14
0x1400174b4  jz      short loc_1400174D3
0x1400174b6  cmp     byte ptr [rcx+29h], 2
0x1400174ba  jb      short loc_1400174D3
0x1400174bc  lea     edx, [rax+2Dh]
0x1400174bf  mov     rcx, [rcx+18h]
0x1400174c3  mov     r9, rsi
0x1400174c6  mov     r8, r12
0x1400174c9  mov     qword ptr [rsp+0C0h+Tag], rdi
0x1400174ce  call    WPP_SF_qq
0x1400174d3  mov     ebx, 0C0000001h
0x1400174d8  jmp     loc_140017D7A
0x1400174dd  mov     rax, [rax]
0x1400174e0  mov     rax, [rax+20h]
0x1400174e4  call    _guard_dispatch_icall
0x1400174e9  mov     [rdi+190h], eax
0x1400174ef  mov     ecx, 110h
0x1400174f4  movzx   eax, word ptr [rsi+16Ch]
0x1400174fb  cmp     ax, cx
0x1400174fe  jnb     short loc_14001750C
0x140017500  mov     dword ptr [rdi+0B4h], 1Ah
0x14001750a  jmp     short loc_140017522
0x14001750c  mov     ecx, 150h
0x140017511  cmp     ax, cx
0x140017514  sbb     eax, eax
0x140017516  and     eax, 0FFFFFFF2h
0x140017519  add     eax, 30h ; '0'
0x14001751c  mov     [rdi+0B4h], eax
0x140017522  mov     [rdi], rsi
0x140017525  mov     rax, [r13+8]
0x140017529  mov     [rdi+8], rax
0x14001752d  mov     qword ptr [rdi+98h], 0
0x140017538  mov     edx, [r15+18h]
0x14001753c  mov     rcx, [rsi+20h]; DescriptorBuffer
0x140017540  call    GetFirstVideoStreamingAltSetting
0x140017545  mov     [rbp+57h+arg_0], rax
0x140017549  mov     r13, rax
0x14001754c  test    rax, rax
0x14001754f  jnz     short loc_140017573
0x140017551  mov     rcx, cs:WPP_GLOBAL_Control
0x140017558  cmp     rcx, r14
0x14001755b  jz      loc_1400174D3
0x140017561  cmp     byte ptr [rcx+29h], 2
0x140017565  jb      loc_1400174D3
0x14001756b  lea     edx, [rax+2Eh]
0x14001756e  jmp     loc_1400174BF
0x140017573  mov     al, [rax+2]
0x140017576  lea     r8, [rdi+178h]
0x14001757d  mov     [rdi+0B1h], al
0x140017583  mov     rdx, r13
0x140017586  mov     rcx, [rsi+20h]; StartPosition
0x14001758a  call    GetVideoEndpointAddress
0x14001758f  mov     ebx, eax
0x140017591  test    eax, eax
0x140017593  jns     short loc_1400175BD
0x140017595  mov     rcx, cs:WPP_GLOBAL_Control
0x14001759c  cmp     rcx, r14
0x14001759f  jz      loc_140017DA9
0x1400175a5  cmp     byte ptr [rcx+29h], 2
0x1400175a9  jb      loc_140017D7A
0x1400175af  mov     edx, 2Fh ; '/'
0x1400175b4  mov     dword ptr [rsp+0C0h+var_98], eax
0x1400175b8  jmp     loc_140017D66
0x1400175bd  mov     rcx, [rsi+20h]; DescriptorBuffer
0x1400175c1  mov     rdx, r13; StartPosition
0x1400175c4  call    IsBulkVideoEndpoint
0x1400175c9  mov     rbx, [rbp+57h+var_70]
0x1400175cd  mov     rdx, r15
0x1400175d0  movzx   eax, al
0x1400175d3  mov     rcx, rbx
0x1400175d6  mov     [rdi+17Ch], eax
0x1400175dc  mov     byte ptr [rdi+179h], 0
0x1400175e3  call    GetUsbDataRangeForPin
0x1400175e8  mov     r13, rax
0x1400175eb  test    rax, rax
0x1400175ee  jnz     short loc_1400175FA
0x1400175f0  mov     ebx, 0C0000010h
0x1400175f5  jmp     loc_140017D7A
0x1400175fa  mov     [rdi+10h], r13
0x1400175fe  mov     rcx, [r15+60h]
0x140017602  mov     r9, qword ptr cs:KSDATAFORMAT_SUBTYPE_DVSD.Data1
0x140017609  mov     r8, qword ptr cs:KSDATAFORMAT_SUBTYPE_DVSD.Data4
0x140017610  mov     rax, [rcx+20h]
0x140017614  sub     rax, r9
0x140017617  jnz     short loc_140017620
0x140017619  mov     rax, [rcx+28h]
0x14001761d  sub     rax, r8
0x140017620  lea     rdx, [r13+34h]
0x140017624  mov     r11d, 51763h
0x14001762a  test    rax, rax
0x14001762d  jnz     short loc_140017640
0x14001762f  cmp     [rdx], r11d
0x140017632  jnz     short loc_140017640
0x140017634  mov     dword ptr [rsi+8], 13AEh
0x14001763b  jmp     loc_140017742
0x140017640  mov     rax, [rcx+20h]
0x140017644  sub     rax, r9
0x140017647  jnz     short loc_140017650
0x140017649  mov     rax, [rcx+28h]
0x14001764d  sub     rax, r8
0x140017650  mov     r10d, 61A80h
0x140017656  test    rax, rax
0x140017659  jnz     short loc_14001766C
0x14001765b  cmp     [rdx], r10d
0x14001765e  jnz     short loc_14001766C
0x140017660  mov     dword ptr [rsi+8], 13B0h
0x140017667  jmp     loc_140017742
0x14001766c  mov     rax, [rcx+20h]
0x140017670  mov     r9, qword ptr cs:KSDATAFORMAT_SUBTYPE_DVSL.Data1
0x140017677  mov     r8, qword ptr cs:KSDATAFORMAT_SUBTYPE_DVSL.Data4
0x14001767e  sub     rax, r9
0x140017681  jnz     short loc_14001768A
0x140017683  mov     rax, [rcx+28h]
0x140017687  sub     rax, r8
0x14001768a  test    rax, rax
0x14001768d  jnz     short loc_1400176A0
0x14001768f  cmp     [rdx], r11d
0x140017692  jnz     short loc_1400176A0
0x140017694  mov     dword ptr [rsi+8], 13AFh
0x14001769b  jmp     loc_140017742
0x1400176a0  mov     rax, [rcx+20h]
0x1400176a4  sub     rax, r9
0x1400176a7  jnz     short loc_1400176B0
0x1400176a9  mov     rax, [rcx+28h]
0x1400176ad  sub     rax, r8
0x1400176b0  test    rax, rax
  ... truncated ...
```
