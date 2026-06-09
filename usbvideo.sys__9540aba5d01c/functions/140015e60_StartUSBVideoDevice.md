# StartUSBVideoDevice

- ea: `0x140015e60`
- end: `0x1400166a3`
- name: `StartUSBVideoDevice`
- size: `2115`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1400104f0`
- `0x14001df50`

## callees

- `0x140005308`
- `0x140009b9c`
- `0x140010e64`
- `0x1400151a0`
- `0x140015e60`
- `0x1400170d8`
- `0x14001ab4c`
- `0x14001b15c`
- `0x14001f224`
- `0x14001f460`
- `0x140020704`
- `0x140020a94`
- `0x140021784`
- `0x140021814`
- `0x14002f2e0`
- `0x14002f3e8`
- `0x140040b40`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140016428`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140016428`
- `ntoskrnl!KeInitializeSemaphore` at `0x140016377`
- `ntoskrnl!KeInitializeSemaphore` at `0x140016377`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400163c9`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400163c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015f72`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015f83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016086`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016166`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001635e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016497`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400164a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400164be`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016633`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001664d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015f72`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015f83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016086`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016166`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001635e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016497`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400164a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400164be`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016633`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001664d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140015ece`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140015f09`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140015fc2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001609d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140016300`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400165a2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140015ece`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140015f09`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140015fc2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001609d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140016300`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400165a2`
- `ks!KsAddItemToObjectBag` at `0x140015fa5`
- `ks!KsAddItemToObjectBag` at `0x14001614a`
- `ks!KsAddItemToObjectBag` at `0x140016343`
- `ks!KsAddItemToObjectBag` at `0x1400165fa`
- `ks!KsAddItemToObjectBag` at `0x140015fa5`
- `ks!KsAddItemToObjectBag` at `0x14001614a`
- `ks!KsAddItemToObjectBag` at `0x140016343`
- `ks!KsAddItemToObjectBag` at `0x1400165fa`
- `USBD!USBD_CreateConfigurationRequestEx` at `0x1400164eb`
- `USBD!USBD_CreateConfigurationRequestEx` at `0x1400164eb`

## string_xrefs

- `0x140016067`: `The total size of Configuration Descriptor is too short`
- `0x14001647e`: `Invalid Configuration Descriptor size`

## pseudocode

```c
__int64 __fastcall StartUSBVideoDevice(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rdi
  _DWORD *v5; // rax
  _DWORD *v6; // rbx
  unsigned __int16 *v7; // r13
  NTSTATUS v8; // ebp
  __int64 result; // rax
  struct _USB_CONFIGURATION_DESCRIPTOR *v10; // rbp
  int v11; // r15d
  const wchar_t *v12; // r8
  size_t wTotalLength; // r15
  struct _USB_CONFIGURATION_DESCRIPTOR *v14; // rax
  USHORT v15; // ax
  NTSTATUS v16; // eax
  void *v17; // rcx
  NTSTATUS v18; // eax
  NTSTATUS v19; // ebx
  __int64 v20; // rdx
  int v21; // ecx
  __int64 v22; // r8
  int v23; // r9d
  int v24; // r15d
  int v25; // ecx
  _OWORD *v26; // rax
  NTSTATUS v27; // eax
  struct _KSEMAPHORE *v28; // rcx
  ULONG v29; // edx
  __int64 v30; // rcx
  __int64 v31; // r8
  int v32; // eax
  PURB ConfigurationRequest; // rax
  PURB v34; // rbp
  int v35; // r13d
  PVOID PoolWithTag; // rax
  PVOID v37; // rbx
  void *v38; // rdx
  void *v39; // rcx
  __int128 v40; // [rsp+40h] [rbp-58h] BYREF
  _DWORD *v41; // [rsp+50h] [rbp-48h]
  USHORT Size; // [rsp+A0h] [rbp+8h]
  unsigned int Sizea; // [rsp+A0h] [rbp+8h]
  SIZE_T Sizeb; // [rsp+A0h] [rbp+8h]
  int Src; // [rsp+A8h] [rbp+10h]
  unsigned __int16 *Srca; // [rsp+A8h] [rbp+10h]

  v4 = *(_QWORD *)(a1 + 16);
  if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) != 0 )
    McTemplateK0p_EtwWriteTransfer(a1, USBVideo_StartUSBVideoDevice_Start, a3, 0);
  if ( *(_QWORD *)(v4 + 40) )
  {
    v19 = 0;
    if ( *(_QWORD *)(v4 + 672) )
      goto LABEL_59;
    ConfigurationRequest = USBD_CreateConfigurationRequestEx(
                             *(PUSB_CONFIGURATION_DESCRIPTOR *)(v4 + 32),
                             *(PUSBD_INTERFACE_LIST_ENTRY *)(v4 + 664));
    v34 = ConfigurationRequest;
    if ( ConfigurationRequest )
    {
      v19 = SubmitUrbToUsbdSynch(a1, ConfigurationRequest);
      if ( v19 < 0 || v34->UrbHeader.Status < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v4);
        if ( v19 >= 0 )
          v19 = -1073741823;
LABEL_101:
        v29 = 0;
        v28 = (struct _KSEMAPHORE *)v34;
        goto LABEL_56;
      }
      v35 = 0;
      *(_QWORD *)(v4 + 672) = v34->UrbSelectConfiguration.ConfigurationHandle;
      while ( v35 < *(unsigned __int8 *)(*(_QWORD *)(v4 + 32) + 4LL) )
      {
        Srca = *(unsigned __int16 **)(*(_QWORD *)(v4 + 664) + 16LL * v35 + 8);
        Sizeb = *Srca;
        PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1536, Sizeb, 0x56425355u);
        v37 = PoolWithTag;
        if ( !ExPoolZeroingNativelySupported && PoolWithTag )
          memset(PoolWithTag, 0, Sizeb);
        *(_QWORD *)(*(_QWORD *)(v4 + 664) + 16LL * v35 + 8) = v37;
        v38 = *(void **)(*(_QWORD *)(v4 + 664) + 16LL * v35 + 8);
        if ( !v38 )
        {
          v19 = -1073741670;
          goto LABEL_101;
        }
        v19 = KsAddItemToObjectBag(*(KSOBJECT_BAG *)(a1 + 8), v38, FreeMem);
        v39 = *(void **)(*(_QWORD *)(v4 + 664) + 16LL * v35 + 8);
        if ( v19 < 0 )
        {
          ExFreePoolWithTag(v39, 0x56425355u);
          goto LABEL_101;
        }
        memmove(v39, Srca, *Srca);
        ++v35;
      }
      ExFreePoolWithTag(v34, 0);
LABEL_59:
      if ( IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v4 + 768), StartUSBVideoDevice, File, 1u, 0x20u) >= 0 )
      {
        v32 = InitializeIrpThreadAndQueue(a1, v4);
        v19 = v32;
        if ( v32 < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v4, v32);
        }
        IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v4 + 768), StartUSBVideoDevice, 0x20u);
      }
      if ( v19 >= 0 )
        *(_BYTE *)(v4 + 1) = 0;
      if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) != 0 )
        McTemplateK0p_EtwWriteTransfer(v30, USBVideo_StartUSBVideoDevice_Stop, v31, 0);
      return (unsigned int)v19;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v4);
    return 3221225626LL;
  }
  v41 = 0;
  v40 = 0;
  v5 = ExAllocatePoolWithTag((POOL_TYPE)1536, 0x88u, 0x56425355u);
  v6 = v5;
  if ( !v5 )
    return 3221225626LL;
  if ( !ExPoolZeroingNativelySupported )
    memset(v5, 0, 0x88u);
  v7 = (unsigned __int16 *)ExAllocatePoolWithTag((POOL_TYPE)1536, 0x12u, 0x56425355u);
  if ( !v7 )
    goto LABEL_76;
  if ( !ExPoolZeroingNativelySupported )
  {
    *(_OWORD *)v7 = 0;
    v7[8] = 0;
  }
  *v6 = 721032;
  v6[9] = 18;
  *((_QWORD *)v6 + 6) = 0;
  *((_QWORD *)v6 + 5) = v7;
  *(_DWORD *)((char *)v6 + 130) = 256;
  *((_QWORD *)v6 + 7) = 0;
  v8 = SubmitUrbToUsbdSynch(a1, v6);
  if ( v8 < 0 || (v8 = KsAddItemToObjectBag(*(KSOBJECT_BAG *)(a1 + 8), v7, FreeMem), v8 < 0) )
  {
    ExFreePoolWithTag(v7, 0x56425355u);
    ExFreePoolWithTag(v6, 0x56425355u);
    return (unsigned int)v8;
  }
  v10 = (struct _USB_CONFIGURATION_DESCRIPTOR *)ExAllocatePoolWithTag((POOL_TYPE)1536, 9u, 0x56425355u);
  if ( !v10 )
    goto LABEL_76;
  if ( !ExPoolZeroingNativelySupported )
  {
    *(_QWORD *)&v10->bLength = 0;
    v10->MaxPower = 0;
  }
  if ( (unsigned int)Feature_Servicing_Telemetry_Uvc_Invalid_Descriptor__private_IsEnabledNoReportingNoInline() )
  {
    *(_QWORD *)&v40 = v4;
    *((_QWORD *)&v40 + 1) = v7;
    v41 = v6;
  }
  *(_QWORD *)&v10->bLength = 0;
  v10->MaxPower = 0;
  *v6 = 721032;
  v6[9] = 9;
  *((_QWORD *)v6 + 6) = 0;
  *((_QWORD *)v6 + 5) = v10;
  *(_DWORD *)((char *)v6 + 130) = 512;
  *((_QWORD *)v6 + 7) = 0;
  v11 = SubmitUrbToUsbdSynch(a1, v6);
  if ( v11 < 0 )
    goto LABEL_74;
  if ( v10->wTotalLength < 9u )
  {
    v11 = -1073741668;
    if ( (unsigned int)Feature_Servicing_Telemetry_Uvc_Invalid_Descriptor__private_IsEnabledNoReportingNoInline() )
    {
      v12 = L"The total size of Configuration Descriptor is too short";
LABEL_73:
      ReportInvalidConfigurationTelemetry(&v40, 3221225628LL, v12);
      goto LABEL_74;
    }
    goto LABEL_74;
  }
  wTotalLength = v10->wTotalLength;
  Size = v10->wTotalLength;
  ExFreePoolWithTag(v10, 0x56425355u);
  v14 = (struct _USB_CONFIGURATION_DESCRIPTOR *)ExAllocatePoolWithTag(
                                                  (POOL_TYPE)1536,
                                                  (unsigned int)wTotalLength,
                                                  0x56425355u);
  v10 = v14;
  if ( !ExPoolZeroingNativelySupported )
  {
    if ( v14 )
    {
      memset(v14, 0, (unsigned int)wTotalLength);
      goto LABEL_26;
    }
LABEL_76:
    ExFreePoolWithTag(v6, 0x56425355u);
    return 3221225626LL;
  }
  if ( !v14 )
    goto LABEL_76;
LABEL_26:
  memset(v10, 0, wTotalLength);
  *v6 = 721032;
  *((_QWORD *)v6 + 6) = 0;
  *((_QWORD *)v6 + 7) = 0;
  v6[9] = wTotalLength;
  *((_QWORD *)v6 + 5) = v10;
  *(_DWORD *)((char *)v6 + 130) = 512;
  v11 = SubmitUrbToUsbdSynch(a1, v6);
  if ( v11 < 0 )
    goto LABEL_74;
  v15 = v10->wTotalLength;
  if ( v15 > Size || v15 < 9u )
  {
    v11 = -1073741668;
    if ( (unsigned int)Feature_Servicing_Telemetry_Uvc_Invalid_Descriptor__private_IsEnabledNoReportingNoInline() )
    {
      v12 = L"Invalid Configuration Descriptor size";
      goto LABEL_73;
    }
LABEL_74:
    v17 = v6;
    goto LABEL_75;
  }
  v16 = KsAddItemToObjectBag(*(KSOBJECT_BAG *)(a1 + 8), v10, FreeMem);
  v17 = v6;
  v11 = v16;
  if ( v16 < 0 )
  {
LABEL_75:
    ExFreePoolWithTag(v17, 0x56425355u);
    ExFreePoolWithTag(v10, 0x56425355u);
    return (unsigned int)v11;
  }
  ExFreePoolWithTag(v6, 0x56425355u);
  if ( (unsigned int)Feature_Servicing_Telemetry_Uvc_Invalid_Descriptor__private_IsEnabledNoReportingNoInline() )
    v18 = DumpAndValidateAllDescriptorsEx(v10, &v40);
  else
    v18 = DumpAndValidateAllDescriptors(v10);
  v19 = v18;
  if ( !(unsigned int)Feature_Servicing_ReportAccurateCameraError__private_IsEnabledNoReportingNoInline() )
  {
    if ( v19 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v4, v19);
      return (unsigned int)v19;
    }
LABEL_50:
    *(_WORD *)(v4 + 364) = GetSpecVersion(v10);
    v26 = ExAllocatePoolWithTag((POOL_TYPE)1536, 0x20u, 0x56425355u);
    if ( !ExPoolZeroingNativelySupported && v26 )
    {
      *v26 = 0;
      v26[1] = 0;
    }
    *(_QWORD *)(v4 + 424) = v26;
    if ( v26 )
    {
      v27 = KsAddItemToObjectBag(*(KSOBJECT_BAG *)(a1 + 8), v26, FreeMem);
      v28 = *(struct _KSEMAPHORE **)(v4 + 424);
      v19 = v27;
      if ( v27 < 0 )
      {
        v29 = 1447187285;
LABEL_56:
        ExFreePoolWithTag(v28, v29);
        return (unsigned int)v19;
      }
      KeInitializeSemaphore(v28, 1, 1);
      result = SelectDeviceConfiguration(a1, v10);
      v19 = result;
      if ( (int)result < 0 )
        return result;
      *(_QWORD *)(v4 + 40) = v7;
      *(_QWORD *)(v4 + 32) = v10;
      *(_BYTE *)v4 = 0;
      goto LABEL_59;
    }
    return 3221225626LL;
  }
  v22 = v7[5];
  v23 = v7[6];
  v24 = v7[4];
  Sizea = v7[5];
  Src = v23;
  if ( v19 >= 0 )
  {
    v25 = (int)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qddd(
        WPP_GLOBAL_Control->AttachedDevice,
        36,
        WPP_b11e537a527d30190cd6733beb5dc248_Traceguids,
        v4,
        v24,
        v22,
        v23);
      LODWORD(v22) = Sizea;
      v23 = Src;
    }
    if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) != 0 )
      McTemplateK0pqqq_EtwWriteTransfer(v25, (unsigned int)USBVideo_ValidConfiguration, v22, v23, v24, v22, v23);
    goto LABEL_50;
  }
  if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 8) != 0 )
  {
    McTemplateK0pqqq_EtwWriteTransfer(v21, (unsigned int)USBVideo_InvalidConfiguration, v22, v23, v24, v22, v23);
    v22 = Sizea;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_qDddd(WPP_GLOBAL_Control->AttachedDevice, v20, v22, v4);
  return 3223257088LL;
}

```

## disassembly

```asm
0x140015e60  mov     [rsp+arg_10], rbx
0x140015e65  push    rbp
0x140015e66  push    rsi
0x140015e67  push    rdi
0x140015e68  push    r12
0x140015e6a  push    r13
0x140015e6c  push    r14
0x140015e6e  push    r15
0x140015e70  sub     rsp, 60h
0x140015e74  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, 1
0x140015e7b  mov     r12, rcx
0x140015e7e  mov     rdi, [rcx+10h]
0x140015e82  jz      short loc_140015E93
0x140015e84  xor     r9d, r9d
0x140015e87  lea     rdx, USBVideo_StartUSBVideoDevice_Start
0x140015e8e  call    McTemplateK0p_EtwWriteTransfer
0x140015e93  cmp     qword ptr [rdi+28h], 0
0x140015e98  lea     r14, WPP_GLOBAL_Control
0x140015e9f  jnz     loc_1400164D1
0x140015ea5  xorps   xmm0, xmm0
0x140015ea8  xor     eax, eax
0x140015eaa  mov     esi, 56425355h
0x140015eaf  mov     [rsp+98h+var_48], rax
0x140015eb4  mov     r13d, 88h
0x140015eba  mov     r15d, 600h
0x140015ec0  mov     r8d, esi; Tag
0x140015ec3  mov     edx, r13d; NumberOfBytes
0x140015ec6  mov     ecx, r15d; PoolType
0x140015ec9  movups  [rsp+98h+var_58], xmm0
0x140015ece  call    cs:__imp_ExAllocatePoolWithTag
0x140015ed5  nop     dword ptr [rax+rax+00h]
0x140015eda  xor     ebp, ebp
0x140015edc  mov     rbx, rax
0x140015edf  test    rax, rax
0x140015ee2  jz      loc_1400164CA
0x140015ee8  cmp     cs:ExPoolZeroingNativelySupported, bpl
0x140015eef  jnz     short loc_140015EFE
0x140015ef1  mov     r8d, r13d; Size
0x140015ef4  xor     edx, edx; Val
0x140015ef6  mov     rcx, rax; void *
0x140015ef9  call    memset
0x140015efe  mov     r8d, esi; Tag
0x140015f01  mov     edx, 12h; NumberOfBytes
0x140015f06  mov     ecx, r15d; PoolType
0x140015f09  call    cs:__imp_ExAllocatePoolWithTag
0x140015f10  nop     dword ptr [rax+rax+00h]
0x140015f15  mov     r13, rax
0x140015f18  test    rax, rax
0x140015f1b  jz      loc_1400164B9
0x140015f21  cmp     cs:ExPoolZeroingNativelySupported, bpl
0x140015f28  jnz     short loc_140015F39
0x140015f2a  xorps   xmm0, xmm0
0x140015f2d  xor     eax, eax
0x140015f2f  movups  xmmword ptr [r13+0], xmm0
0x140015f34  mov     [r13+10h], ax
0x140015f39  mov     rdx, rbx
0x140015f3c  mov     dword ptr [rbx], 0B0088h
0x140015f42  mov     rcx, r12
0x140015f45  mov     dword ptr [rbx+24h], 12h
0x140015f4c  mov     [rbx+30h], rbp
0x140015f50  mov     [rbx+28h], r13
0x140015f54  mov     dword ptr [rbx+82h], 100h
0x140015f5e  mov     [rbx+38h], rbp
0x140015f62  call    SubmitUrbToUsbdSynch
0x140015f67  mov     ebp, eax
0x140015f69  test    eax, eax
0x140015f6b  jns     short loc_140015F96
0x140015f6d  mov     edx, esi; Tag
0x140015f6f  mov     rcx, r13; P
0x140015f72  call    cs:__imp_ExFreePoolWithTag
0x140015f79  nop     dword ptr [rax+rax+00h]
0x140015f7e  mov     edx, esi; Tag
0x140015f80  mov     rcx, rbx; P
0x140015f83  call    cs:__imp_ExFreePoolWithTag
0x140015f8a  nop     dword ptr [rax+rax+00h]
0x140015f8f  mov     eax, ebp
0x140015f91  jmp     loc_140016456
0x140015f96  mov     rcx, [r12+8]; ObjectBag
0x140015f9b  lea     r8, FreeMem; Free
0x140015fa2  mov     rdx, r13; Item
0x140015fa5  call    cs:__imp_KsAddItemToObjectBag
0x140015fac  nop     dword ptr [rax+rax+00h]
0x140015fb1  mov     ebp, eax
0x140015fb3  test    eax, eax
0x140015fb5  js      short loc_140015F6D
0x140015fb7  mov     r8d, esi; Tag
0x140015fba  mov     edx, 9; NumberOfBytes
0x140015fbf  mov     ecx, r15d; PoolType
0x140015fc2  call    cs:__imp_ExAllocatePoolWithTag
0x140015fc9  nop     dword ptr [rax+rax+00h]
0x140015fce  xor     r15d, r15d
0x140015fd1  mov     rbp, rax
0x140015fd4  test    rax, rax
0x140015fd7  jz      loc_1400164B9
0x140015fdd  cmp     cs:ExPoolZeroingNativelySupported, r15b
0x140015fe4  jnz     short loc_140015FEF
0x140015fe6  xor     eax, eax
0x140015fe8  mov     [rbp+0], rax
0x140015fec  mov     [rbp+8], al
0x140015fef  call    Feature_Servicing_Telemetry_Uvc_Invalid_Descriptor__private_IsEnabledNoReportingNoInline
0x140015ff4  test    eax, eax
0x140015ff6  jz      short loc_140016007
0x140015ff8  mov     qword ptr [rsp+98h+var_58], rdi
0x140015ffd  mov     qword ptr [rsp+98h+var_58+8], r13
0x140016002  mov     [rsp+98h+var_48], rbx
0x140016007  xor     eax, eax
0x140016009  mov     rdx, rbx
0x14001600c  mov     [rbp+0], rax
0x140016010  mov     rcx, r12
0x140016013  mov     [rbp+8], al
0x140016016  mov     dword ptr [rbx], 0B0088h
0x14001601c  mov     dword ptr [rbx+24h], 9
0x140016023  mov     [rbx+30h], r15
0x140016027  mov     [rbx+28h], rbp
0x14001602b  mov     dword ptr [rbx+82h], 200h
0x140016035  mov     [rbx+38h], r15
0x140016039  call    SubmitUrbToUsbdSynch
0x14001603e  mov     r15d, eax
0x140016041  test    eax, eax
0x140016043  js      loc_140016492
0x140016049  mov     eax, 9
0x14001604e  cmp     [rbp+2], ax
0x140016052  jnb     short loc_140016073
0x140016054  mov     r15d, 0C000009Ch
0x14001605a  call    Feature_Servicing_Telemetry_Uvc_Invalid_Descriptor__private_IsEnabledNoReportingNoInline
0x14001605f  test    eax, eax
0x140016061  jz      loc_140016492
0x140016067  lea     r8, aTheTotalSizeOf; "The total size of Configuration Descrip"...
0x14001606e  jmp     loc_140016485
0x140016073  movzx   r15d, word ptr [rbp+2]
0x140016078  mov     edx, esi; Tag
0x14001607a  mov     rcx, rbp; P
0x14001607d  mov     word ptr [rsp+98h+Size], r15w
0x140016086  call    cs:__imp_ExFreePoolWithTag
0x14001608d  nop     dword ptr [rax+rax+00h]
0x140016092  mov     edx, r15d; NumberOfBytes
0x140016095  mov     r8d, esi; Tag
0x140016098  mov     ecx, 600h; PoolType
0x14001609d  call    cs:__imp_ExAllocatePoolWithTag
0x1400160a4  nop     dword ptr [rax+rax+00h]
0x1400160a9  cmp     cs:ExPoolZeroingNativelySupported, 0
0x1400160b0  mov     rbp, rax
0x1400160b3  jnz     short loc_1400160CD
0x1400160b5  test    rax, rax
0x1400160b8  jz      loc_1400164B9
0x1400160be  mov     r8d, r15d; Size
0x1400160c1  xor     edx, edx; Val
0x1400160c3  mov     rcx, rax; void *
0x1400160c6  call    memset
0x1400160cb  jmp     short loc_1400160D6
0x1400160cd  test    rbp, rbp
0x1400160d0  jz      loc_1400164B9
0x1400160d6  mov     r8, r15; Size
0x1400160d9  xor     edx, edx; Val
0x1400160db  mov     rcx, rbp; void *
0x1400160de  call    memset
0x1400160e3  xor     ecx, ecx
0x1400160e5  mov     dword ptr [rbx], 0B0088h
0x1400160eb  mov     [rbx+30h], rcx
0x1400160ef  mov     rdx, rbx
0x1400160f2  mov     [rbx+38h], rcx
0x1400160f6  mov     rcx, r12
0x1400160f9  mov     [rbx+24h], r15d
0x1400160fd  mov     [rbx+28h], rbp
0x140016101  mov     dword ptr [rbx+82h], 200h
0x14001610b  call    SubmitUrbToUsbdSynch
0x140016110  mov     r15d, eax
0x140016113  test    eax, eax
0x140016115  js      loc_140016492
0x14001611b  movzx   eax, word ptr [rbp+2]
0x14001611f  cmp     ax, word ptr [rsp+98h+Size]
0x140016127  ja      loc_14001646F
0x14001612d  mov     ecx, 9
0x140016132  cmp     ax, cx
0x140016135  jb      loc_14001646F
0x14001613b  mov     rcx, [r12+8]; ObjectBag
0x140016140  lea     r8, FreeMem; Free
0x140016147  mov     rdx, rbp; Item
0x14001614a  call    cs:__imp_KsAddItemToObjectBag
0x140016151  nop     dword ptr [rax+rax+00h]
0x140016156  mov     edx, esi; Tag
0x140016158  mov     rcx, rbx; P
0x14001615b  mov     r15d, eax
0x14001615e  test    eax, eax
0x140016160  js      loc_140016497
0x140016166  call    cs:__imp_ExFreePoolWithTag
0x14001616d  nop     dword ptr [rax+rax+00h]
0x140016172  call    Feature_Servicing_Telemetry_Uvc_Invalid_Descriptor__private_IsEnabledNoReportingNoInline
0x140016177  mov     rcx, rbp
0x14001617a  test    eax, eax
0x14001617c  jnz     short loc_140016185
0x14001617e  call    DumpAndValidateAllDescriptors
0x140016183  jmp     short loc_14001618F
0x140016185  lea     rdx, [rsp+98h+var_58]
0x14001618a  call    DumpAndValidateAllDescriptorsEx
0x14001618f  mov     ebx, eax
0x140016191  call    Feature_Servicing_ReportAccurateCameraError__private_IsEnabledNoReportingNoInline
0x140016196  test    eax, eax
0x140016198  jnz     short loc_1400161E2
0x14001619a  test    ebx, ebx
0x14001619c  jns     loc_1400162E4
0x1400161a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400161a9  lea     r14, WPP_GLOBAL_Control
0x1400161b0  cmp     rcx, r14
0x1400161b3  jz      loc_140016454
0x1400161b9  cmp     byte ptr [rcx+29h], 2
0x1400161bd  jb      loc_140016454
0x1400161c3  mov     rcx, [rcx+18h]
0x1400161c7  lea     edx, [rax+25h]
0x1400161ca  mov     r9, rdi
0x1400161cd  mov     [rsp+98h+RemlockSize], ebx
0x1400161d1  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x1400161d8  call    WPP_SF_qD
0x1400161dd  jmp     loc_140016454
0x1400161e2  movzx   r8d, word ptr [r13+0Ah]
0x1400161e7  movzx   r9d, word ptr [r13+0Ch]
0x1400161ec  movzx   r15d, word ptr [r13+8]
0x1400161f1  mov     dword ptr [rsp+98h+Size], r8d
0x1400161f9  mov     dword ptr [rsp+98h+Src], r9d
0x140016201  test    ebx, ebx
0x140016203  jns     short loc_140016277
0x140016205  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, 8
0x14001620c  jz      short loc_140016239
0x14001620e  mov     [rsp+98h+var_68], r9d
0x140016213  lea     rdx, USBVideo_InvalidConfiguration
0x14001621a  mov     [rsp+98h+var_70], r8d
0x14001621f  mov     [rsp+98h+RemlockSize], r15d
0x140016224  call    McTemplateK0pqqq_EtwWriteTransfer
0x140016229  mov     r8d, dword ptr [rsp+98h+Size]
0x140016231  mov     r9d, dword ptr [rsp+98h+Src]
0x140016239  mov     rcx, cs:WPP_GLOBAL_Control
0x140016240  lea     r14, WPP_GLOBAL_Control
0x140016247  cmp     rcx, r14
0x14001624a  jz      short loc_14001626D
0x14001624c  cmp     byte ptr [rcx+29h], 2
0x140016250  jb      short loc_14001626D
0x140016252  mov     rcx, [rcx+18h]
0x140016256  mov     [rsp+98h+var_60], r9d
0x14001625b  mov     r9, rdi
0x14001625e  mov     [rsp+98h+var_68], r8d
0x140016263  mov     [rsp+98h+var_70], r15d
0x140016268  call    WPP_SF_qDddd
0x14001626d  mov     eax, 0C01F0000h
0x140016272  jmp     loc_140016456
0x140016277  mov     rcx, cs:WPP_GLOBAL_Control
0x14001627e  cmp     rcx, r14
0x140016281  jz      short loc_1400162C0
0x140016283  cmp     byte ptr [rcx+29h], 4
0x140016287  jb      short loc_1400162C0
0x140016289  mov     rcx, [rcx+18h]
0x14001628d  mov     edx, 24h ; '$'
0x140016292  mov     [rsp+98h+var_68], r9d
0x140016297  mov     r9, rdi
0x14001629a  mov     [rsp+98h+var_70], r8d
0x14001629f  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x1400162a6  mov     [rsp+98h+RemlockSize], r15d
0x1400162ab  call    WPP_SF_qddd
0x1400162b0  mov     r8d, dword ptr [rsp+98h+Size]
0x1400162b8  mov     r9d, dword ptr [rsp+98h+Src]
0x1400162c0  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, 1
0x1400162c7  jz      short loc_1400162E4
0x1400162c9  mov     [rsp+98h+var_68], r9d
0x1400162ce  lea     rdx, USBVideo_ValidConfiguration
0x1400162d5  mov     [rsp+98h+var_70], r8d
0x1400162da  mov     [rsp+98h+RemlockSize], r15d
0x1400162df  call    McTemplateK0pqqq_EtwWriteTransfer
0x1400162e4  mov     rcx, rbp; StartPosition
0x1400162e7  call    GetSpecVersion
0x1400162ec  mov     r8d, esi; Tag
0x1400162ef  mov     [rdi+16Ch], ax
0x1400162f6  mov     edx, 20h ; ' '; NumberOfBytes
0x1400162fb  mov     ecx, 600h; PoolType
0x140016300  call    cs:__imp_ExAllocatePoolWithTag
0x140016307  nop     dword ptr [rax+rax+00h]
0x14001630c  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140016313  jnz     short loc_140016324
0x140016315  test    rax, rax
0x140016318  jz      short loc_140016324
0x14001631a  xorps   xmm0, xmm0
0x14001631d  movups  xmmword ptr [rax], xmm0
0x140016320  movups  xmmword ptr [rax+10h], xmm0
0x140016324  mov     [rdi+1A8h], rax
0x14001632b  test    rax, rax
0x14001632e  jz      loc_1400164CA
0x140016334  mov     rcx, [r12+8]; ObjectBag
0x140016339  lea     r8, FreeMem; Free
0x140016340  mov     rdx, rax; Item
0x140016343  call    cs:__imp_KsAddItemToObjectBag
0x14001634a  nop     dword ptr [rax+rax+00h]
0x14001634f  mov     rcx, [rdi+1A8h]; Semaphore
0x140016356  mov     ebx, eax
0x140016358  test    eax, eax
0x14001635a  jns     short loc_14001636F
0x14001635c  mov     edx, esi; Tag
0x14001635e  call    cs:__imp_ExFreePoolWithTag
0x140016365  nop     dword ptr [rax+rax+00h]
0x14001636a  jmp     loc_140016454
0x14001636f  mov     edx, 1; Count
0x140016374  mov     r8d, edx; Limit
0x140016377  call    cs:__imp_KeInitializeSemaphore
  ... truncated ...
```
