# USBVideoAddDevice

- ea: `0x1400156a0`
- end: `0x140015e56`
- name: `USBVideoAddDevice`
- size: `1974`
- prototype: `__int64 __fastcall(PKSDEVICE Device)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140004bac`
- `0x140005308`
- `0x14000e964`
- `0x14000efa4`
- `0x140013470`
- `0x1400156a0`
- `0x14001709c`
- `0x14001ab4c`
- `0x14001acf0`
- `0x14001b15c`
- `0x14001b59c`
- `0x14001b644`
- `0x14001d20c`
- `0x14001d860`
- `0x14001e468`
- `0x14003be34`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!IoCsqInitialize` at `0x140015b14`
- `ntoskrnl!IoCsqInitialize` at `0x140015b71`
- `ntoskrnl!IoCsqInitialize` at `0x140015be4`
- `ntoskrnl!IoCsqInitialize` at `0x140015b14`
- `ntoskrnl!IoCsqInitialize` at `0x140015b71`
- `ntoskrnl!IoCsqInitialize` at `0x140015be4`
- `ntoskrnl!KeInitializeSemaphore` at `0x140015a6e`
- `ntoskrnl!KeInitializeSemaphore` at `0x140015a86`
- `ntoskrnl!KeInitializeSemaphore` at `0x140015a6e`
- `ntoskrnl!KeInitializeSemaphore` at `0x140015a86`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x140015ac8`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x140015ac8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015795`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015d28`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015795`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015d28`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140015702`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140015c98`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140015702`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140015c98`
- `ntoskrnl!KeInitializeSpinLock` at `0x140015a51`
- `ntoskrnl!KeInitializeSpinLock` at `0x140015b8a`
- `ntoskrnl!KeInitializeSpinLock` at `0x140015a51`
- `ntoskrnl!KeInitializeSpinLock` at `0x140015b8a`
- `ntoskrnl!KeInitializeMutex` at `0x140015c3a`
- `ntoskrnl!KeInitializeMutex` at `0x140015c3a`
- `ntoskrnl!IoSizeofWorkItem` at `0x140015c7d`
- `ntoskrnl!IoSizeofWorkItem` at `0x140015c7d`
- `ks!KsReleaseDevice` at `0x14001577b`
- `ks!KsReleaseDevice` at `0x14001577b`
- `ks!KsAcquireDevice` at `0x14001574f`
- `ks!KsAcquireDevice` at `0x14001574f`
- `ks!KsAddItemToObjectBag` at `0x14001576a`
- `ks!KsAddItemToObjectBag` at `0x140015ce4`
- `ks!KsAddItemToObjectBag` at `0x14001576a`
- `ks!KsAddItemToObjectBag` at `0x140015ce4`

## pseudocode

```c
__int64 __fastcall USBVideoAddDevice(PKSDEVICE Device)
{
  PVOID PoolWithTag; // rax
  void *v3; // rbx
  __int64 result; // rax
  NTSTATUS v5; // edi
  _BYTE *Context; // rbx
  int v7; // eax
  unsigned int *v8; // r14
  char v9; // al
  ULONG v10; // r8d
  ULONG v11; // r9d
  unsigned int v12; // ecx
  USBD_HANDLE *v13; // rdi
  ULONG v14; // r8d
  UCHAR *v15; // r9
  ULONG v16; // r8d
  UCHAR *v17; // r9
  ULONG v18; // r8d
  UCHAR *v19; // r9
  struct _DEVICE_OBJECT *v20; // rcx
  int SecureInterface; // eax
  const char *v22; // rdx
  int v23; // eax
  __int64 v24; // rax
  ULONG v25; // ebp
  PVOID v26; // rax
  __int64 v27; // r8
  void *v28; // rdi
  PDEVICE_OBJECT PhysicalDeviceObject; // rcx
  int DeviceRegValueDword; // eax
  PDEVICE_OBJECT v31; // rcx
  __int64 v32; // rdx
  PDEVICE_OBJECT v33; // rcx
  ULONG *USBDHandle; // [rsp+20h] [rbp-68h]
  ULONG *USBDHandlea; // [rsp+20h] [rbp-68h]
  ULONG *USBDHandleb; // [rsp+20h] [rbp-68h]
  int v37; // [rsp+90h] [rbp+8h] BYREF

  v37 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids);
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1536, 0x600u, 0x56425355u);
  v3 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported && PoolWithTag )
    memset(PoolWithTag, 0, 0x600u);
  Device->Context = v3;
  if ( !v3 )
    return 3221225626LL;
  memset(v3, 0, 0x600u);
  KsAcquireDevice(Device);
  v5 = KsAddItemToObjectBag(Device->Bag, Device->Context, FreeMem);
  KsReleaseDevice(Device);
  Context = Device->Context;
  if ( v5 < 0 )
  {
    ExFreePoolWithTag(Context, 0x56425355u);
    Device->Context = 0;
    return (unsigned int)v5;
  }
  *((_QWORD *)Context + 3) = Device;
  *((_QWORD *)Context + 2) = Device->NextDeviceObject;
  v7 = dword_14004C700 + 1;
  *Context = 1;
  dword_14004C700 = v7;
  *((_DWORD *)Context + 181) = v7;
  *((_DWORD *)Context + 2) = 5086;
  *((_QWORD *)Context + 29) = -20000000;
  Context[800] = -1;
  USBVideoGetDeviceFlags(Context);
  v8 = (unsigned int *)(Context + 1512);
  v9 = ~(unsigned __int8)*((_DWORD *)Context + 382);
  *((_DWORD *)Context + 377) = 0;
  *((_DWORD *)Context + 378) = v9 & 1;
  GetDeviceRegValueDword(Device->PhysicalDeviceObject, 1, L"InterruptResetLimit", Context + 1512);
  *((_DWORD *)Context + 379) = (Context[1528] & 2) == 0 ? 3 : 0;
  GetDeviceRegValueDword(Device->PhysicalDeviceObject, 1, L"InterruptReissueLimit", Context + 1516);
  v12 = *((_DWORD *)Context + 379);
  if ( v12 )
  {
    if ( v12 <= *v8 )
      v12 = *v8;
    *((_DWORD *)Context + 379) = v12;
  }
  *((_DWORD *)Context + 380) = 0;
  v13 = (USBD_HANDLE *)(Context + 872);
  if ( USBD_CreateHandle(
         Device->FunctionalDeviceObject,
         Device->NextDeviceObject,
         v10,
         v11,
         (USBD_HANDLE *)Context + 109) >= 0 )
  {
    if ( USBD_QueryUsbCapability(
           *v13,
           &GUID_USB_CAPABILITY_DEVICE_CONNECTION_SUPER_SPEED_COMPATIBLE,
           v14,
           v15,
           USBDHandle) >= 0 )
    {
      Context[3] = 1;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids, Context);
    }
    if ( USBD_QueryUsbCapability(*v13, &GUID_USB_CAPABILITY_SSP_ISOCH_PIPE_FLAGS, v16, v17, USBDHandlea) >= 0 )
    {
      Context[4] = 1;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids, Context);
    }
    if ( (unsigned int)Feature_EUSB2__private_IsEnabledDeviceUsageNoInline() )
    {
      if ( USBD_QueryUsbCapability(
             *v13,
             &GUID_USB_CAPABILITY_CONTROLLER_EUSB2_DOUBLE_ISOCH_COMPATIBLE,
             v18,
             v19,
             USBDHandleb) >= 0 )
      {
        Context[5] = 1;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids, Context);
      }
    }
    if ( USBD_QueryUsbCapability(*v13, &GUID_USB_CAPABILITY_SECURE_TRANSFERS, v18, v19, USBDHandleb) >= 0 )
    {
      v20 = (struct _DEVICE_OBJECT *)*((_QWORD *)Context + 2);
      *((_DWORD *)Context + 216) = 1;
      SecureInterface = RetrieveSecureInterface(v20);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v22 = "IS";
        if ( SecureInterface < 0 )
          v22 = "IS NOT";
        WPP_SF_qs(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v22,
          (unsigned int)"IS NOT",
          (_DWORD)Context,
          (__int64)v22);
      }
    }
  }
  result = CreateDeviceUtilityObject(*((struct _KSDEVICE **)Context + 3));
  if ( (int)result >= 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids, Context);
    if ( (int)GetDeviceRegValueDword(Device->PhysicalDeviceObject, 2, L"UvcFlags", &v37) >= 0 )
    {
      v23 = v37;
      *((_DWORD *)Context + 179) = v37;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids, Context, v23);
    }
    *((_DWORD *)Context + 179) |= 2u;
    KeInitializeSpinLock((PKSPIN_LOCK)Context + 52);
    KeInitializeSemaphore((PRKSEMAPHORE)Context + 19, 0, 0x7FFFFFFF);
    KeInitializeSemaphore((PRKSEMAPHORE)(Context + 808), 0, 0x7FFFFFFF);
    *((_QWORD *)Context + 73) = Context + 576;
    *((_QWORD *)Context + 72) = Context + 576;
    *((_QWORD *)Context + 75) = Context + 592;
    *((_QWORD *)Context + 74) = Context + 592;
    IoInitializeRemoveLockEx((PIO_REMOVE_LOCK)Context + 24, 0x56627355u, 0, 0, 0x20u);
    v5 = IoCsqInitialize(
           (PIO_CSQ)Context + 8,
           CsInsertIrp,
           FilterCreateQueue_RemoveIrp,
           CsPeekNextIrpStatusInterruptQ,
           CsAcquireLock,
           CsReleaseLock,
           CsCompleteCanceledIrp);
    if ( v5 >= 0 )
    {
      *((_QWORD *)Context + 63) = Context + 496;
      *((_QWORD *)Context + 62) = Context + 496;
      v5 = IoCsqInitialize(
             (PIO_CSQ)(Context + 432),
             CsInsertIrp,
             FilterCreateQueue_RemoveIrp,
             CsPeekNextIrpStatusInterruptQ,
             CsAcquireLockStatusInterruptQ,
             CsReleaseLockStatusInterruptQ,
             CsCompleteCanceledIrp);
      if ( v5 >= 0 )
      {
        KeInitializeSpinLock((PKSPIN_LOCK)Context + 40);
        *((_QWORD *)Context + 42) = Context + 328;
        *((_QWORD *)Context + 41) = Context + 328;
        v5 = IoCsqInitialize(
               (PIO_CSQ)Context + 4,
               FilterCreateQueue_InsertIrp,
               FilterCreateQueue_RemoveIrp,
               FilterCreateQueue_PeekNextIrp,
               FilterCreateQueue_Lock,
               FilterCreateQueue_Unlock,
               FilterCreateQueue_CompleteCanceledIrp);
      }
    }
    *((_QWORD *)Context + 43) = 0;
    v24 = 0;
    *((_QWORD *)Context + 110) = 0;
    do
    {
      *(_QWORD *)&Context[8 * v24 + 1088] = 0;
      *(_QWORD *)&Context[8 * v24 + 952] = 0;
      *(_DWORD *)&Context[4 * v24++ + 1276] = 1;
    }
    while ( v24 != 17 );
    *((_DWORD *)Context + 336) = 1;
    KeInitializeMutex((PRKMUTEX)Context + 16, 0);
    CreateTelemetrySessionId((UUID *)(Context + 1348));
    PopulateHardwareId(Device);
    if ( !(unsigned int)Feature_Servicing_UvcPerfIrpCache__private_IsEnabledNoReportingNoInline() || v5 < 0 )
      return (unsigned int)v5;
    Context[353] = 0;
    v25 = IoSizeofWorkItem();
    v26 = ExAllocatePoolWithTag((POOL_TYPE)1536, v25, 0x56425355u);
    v28 = v26;
    if ( !ExPoolZeroingNativelySupported && v26 )
      memset(v26, 0, v25);
    *((_QWORD *)Context + 31) = v28;
    if ( !v28 )
    {
      v5 = -1073741670;
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids, Context);
      if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 4) != 0 )
        McTemplateK0p_EtwWriteTransfer(v33, USBVideo_PowerIrp_AllocationFailure, v27, 0);
      return (unsigned int)v5;
    }
    v5 = KsAddItemToObjectBag(*(KSOBJECT_BAG *)(*((_QWORD *)Context + 3) + 8LL), v28, FreeMem);
    if ( v5 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids, Context);
      ExFreePoolWithTag(*((PVOID *)Context + 31), 0x56425355u);
      *((_QWORD *)Context + 31) = 0;
      return (unsigned int)v5;
    }
    PhysicalDeviceObject = Device->PhysicalDeviceObject;
    v37 = 0;
    DeviceRegValueDword = GetDeviceRegValueDword(PhysicalDeviceObject, 1, L"PowerlineFrequency", &v37);
    v5 = DeviceRegValueDword;
    if ( DeviceRegValueDword < 0 )
    {
      if ( DeviceRegValueDword == -1073741772 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids, Context);
        Context[352] = -2;
        return 0;
      }
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
        return (unsigned int)v5;
      v32 = 27;
    }
    else
    {
      DeviceRegValueDword = v37;
      Context[352] = v37;
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        return (unsigned int)v5;
      v32 = 25;
    }
    WPP_SF_qD(v31->AttachedDevice, v32, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids, Context, DeviceRegValueDword);
    return (unsigned int)v5;
  }
  return result;
}

```

## disassembly

```asm
0x1400156a0  mov     rax, rsp
0x1400156a3  push    rbx
0x1400156a4  push    rbp
0x1400156a5  push    rsi
0x1400156a6  push    rdi
0x1400156a7  push    r12
0x1400156a9  push    r13
0x1400156ab  push    r14
0x1400156ad  push    r15
0x1400156af  sub     rsp, 48h
0x1400156b3  xor     r15d, r15d
0x1400156b6  mov     rsi, rcx
0x1400156b9  mov     [rax+8], r15d
0x1400156bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400156c4  lea     r12, WPP_GLOBAL_Control
0x1400156cb  lea     r13, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids
0x1400156d2  mov     bpl, 4
0x1400156d5  cmp     rcx, r12
0x1400156d8  jz      short loc_1400156F0
0x1400156da  cmp     [rcx+29h], bpl
0x1400156de  jb      short loc_1400156F0
0x1400156e0  mov     rcx, [rcx+18h]
0x1400156e4  lea     edx, [r15+10h]
0x1400156e8  mov     r8, r13
0x1400156eb  call    WPP_SF_
0x1400156f0  mov     edi, 600h
0x1400156f5  mov     r14d, 56425355h
0x1400156fb  mov     r8d, r14d; Tag
0x1400156fe  mov     edx, edi; NumberOfBytes
0x140015700  mov     ecx, edi; PoolType
0x140015702  call    cs:__imp_ExAllocatePoolWithTag
0x140015709  nop     dword ptr [rax+rax+00h]
0x14001570e  cmp     cs:ExPoolZeroingNativelySupported, r15b
0x140015715  mov     rbx, rax
0x140015718  jnz     short loc_14001572C
0x14001571a  test    rax, rax
0x14001571d  jz      short loc_14001572C
0x14001571f  mov     r8d, edi; Size
0x140015722  xor     edx, edx; Val
0x140015724  mov     rcx, rax; void *
0x140015727  call    memset
0x14001572c  mov     [rsi+10h], rbx
0x140015730  test    rbx, rbx
0x140015733  jnz     short loc_14001573F
0x140015735  mov     eax, 0C000009Ah
0x14001573a  jmp     loc_140015E44
0x14001573f  mov     r8, rdi; Size
0x140015742  xor     edx, edx; Val
0x140015744  mov     rcx, rbx; void *
0x140015747  call    memset
0x14001574c  mov     rcx, rsi; Device
0x14001574f  call    cs:__imp_KsAcquireDevice
0x140015756  nop     dword ptr [rax+rax+00h]
0x14001575b  mov     rdx, [rsi+10h]; Item
0x14001575f  lea     r8, FreeMem; Free
0x140015766  mov     rcx, [rsi+8]; ObjectBag
0x14001576a  call    cs:__imp_KsAddItemToObjectBag
0x140015771  nop     dword ptr [rax+rax+00h]
0x140015776  mov     rcx, rsi; Device
0x140015779  mov     edi, eax
0x14001577b  call    cs:__imp_KsReleaseDevice
0x140015782  nop     dword ptr [rax+rax+00h]
0x140015787  mov     rbx, [rsi+10h]
0x14001578b  mov     rcx, rbx; P
0x14001578e  test    edi, edi
0x140015790  jns     short loc_1400157AA
0x140015792  mov     edx, r14d; Tag
0x140015795  call    cs:__imp_ExFreePoolWithTag
0x14001579c  nop     dword ptr [rax+rax+00h]
0x1400157a1  mov     [rsi+10h], r15
0x1400157a5  jmp     loc_140015E42
0x1400157aa  mov     [rbx+18h], rsi
0x1400157ae  mov     rax, [rsi+28h]
0x1400157b2  mov     [rbx+10h], rax
0x1400157b6  mov     eax, cs:dword_14004C700
0x1400157bc  inc     eax
0x1400157be  mov     byte ptr [rbx], 1
0x1400157c1  mov     cs:dword_14004C700, eax
0x1400157c7  mov     [rbx+2D4h], eax
0x1400157cd  mov     dword ptr [rbx+8], 13DEh
0x1400157d4  mov     qword ptr [rbx+0E8h], 0FFFFFFFFFECED300h
0x1400157df  mov     byte ptr [rbx+320h], 0FFh
0x1400157e6  call    USBVideoGetDeviceFlags
0x1400157eb  mov     eax, [rbx+5F8h]
0x1400157f1  lea     r14, [rbx+5E8h]
0x1400157f8  not     eax
0x1400157fa  mov     [rbx+5E4h], r15d
0x140015801  and     eax, 1
0x140015804  lea     r8, aInterruptreset; "InterruptResetLimit"
0x14001580b  mov     [r14], eax
0x14001580e  mov     r9, r14
0x140015811  mov     rcx, [rsi+20h]
0x140015815  mov     edx, 1
0x14001581a  call    GetDeviceRegValueDword
0x14001581f  mov     al, [rbx+5F8h]
0x140015825  lea     rdi, [rbx+5ECh]
0x14001582c  and     al, 2
0x14001582e  lea     r8, aInterruptreiss; "InterruptReissueLimit"
0x140015835  neg     al
0x140015837  mov     r9, rdi
0x14001583a  mov     edx, 1
0x14001583f  sbb     ecx, ecx
0x140015841  not     ecx
0x140015843  and     ecx, 3
0x140015846  mov     [rdi], ecx
0x140015848  mov     rcx, [rsi+20h]
0x14001584c  call    GetDeviceRegValueDword
0x140015851  mov     ecx, [rdi]
0x140015853  test    ecx, ecx
0x140015855  jz      short loc_140015861
0x140015857  mov     eax, [r14]
0x14001585a  cmp     ecx, eax
0x14001585c  cmovbe  ecx, eax
0x14001585f  mov     [rdi], ecx
0x140015861  mov     [rbx+5F0h], r15d
0x140015868  lea     rdi, [rbx+368h]
0x14001586f  mov     rdx, [rsi+28h]; TargetDeviceObject
0x140015873  mov     rcx, [rsi+18h]; DeviceObject
0x140015877  mov     [rsp+88h+USBDHandle], rdi; ResultLength
0x14001587c  call    USBD_CreateHandle
0x140015881  test    eax, eax
0x140015883  js      loc_1400159AD
0x140015889  mov     rcx, [rdi]; USBDHandle
0x14001588c  lea     rdx, GUID_USB_CAPABILITY_DEVICE_CONNECTION_SUPER_SPEED_COMPATIBLE; CapabilityType
0x140015893  call    USBD_QueryUsbCapability
0x140015898  test    eax, eax
0x14001589a  js      short loc_1400158C6
0x14001589c  mov     byte ptr [rbx+3], 1
0x1400158a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400158a7  cmp     rcx, r12
0x1400158aa  jz      short loc_1400158C6
0x1400158ac  cmp     [rcx+29h], bpl
0x1400158b0  jb      short loc_1400158C6
0x1400158b2  mov     rcx, [rcx+18h]
0x1400158b6  mov     edx, 11h
0x1400158bb  mov     r9, rbx
0x1400158be  mov     r8, r13
0x1400158c1  call    WPP_SF_q
0x1400158c6  mov     rcx, [rdi]; USBDHandle
0x1400158c9  lea     rdx, GUID_USB_CAPABILITY_SSP_ISOCH_PIPE_FLAGS; CapabilityType
0x1400158d0  call    USBD_QueryUsbCapability
0x1400158d5  test    eax, eax
0x1400158d7  js      short loc_140015903
0x1400158d9  mov     byte ptr [rbx+4], 1
0x1400158dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400158e4  cmp     rcx, r12
0x1400158e7  jz      short loc_140015903
0x1400158e9  cmp     [rcx+29h], bpl
0x1400158ed  jb      short loc_140015903
0x1400158ef  mov     rcx, [rcx+18h]
0x1400158f3  mov     edx, 12h
0x1400158f8  mov     r9, rbx
0x1400158fb  mov     r8, r13
0x1400158fe  call    WPP_SF_q
0x140015903  call    Feature_EUSB2__private_IsEnabledDeviceUsageNoInline
0x140015908  test    eax, eax
0x14001590a  jz      short loc_140015949
0x14001590c  mov     rcx, [rdi]; USBDHandle
0x14001590f  lea     rdx, GUID_USB_CAPABILITY_CONTROLLER_EUSB2_DOUBLE_ISOCH_COMPATIBLE; CapabilityType
0x140015916  call    USBD_QueryUsbCapability
0x14001591b  test    eax, eax
0x14001591d  js      short loc_140015949
0x14001591f  mov     byte ptr [rbx+5], 1
0x140015923  mov     rcx, cs:WPP_GLOBAL_Control
0x14001592a  cmp     rcx, r12
0x14001592d  jz      short loc_140015949
0x14001592f  cmp     [rcx+29h], bpl
0x140015933  jb      short loc_140015949
0x140015935  mov     rcx, [rcx+18h]
0x140015939  mov     edx, 13h
0x14001593e  mov     r9, rbx
0x140015941  mov     r8, r13
0x140015944  call    WPP_SF_q
0x140015949  mov     rcx, [rdi]; USBDHandle
0x14001594c  lea     rdx, GUID_USB_CAPABILITY_SECURE_TRANSFERS; CapabilityType
0x140015953  call    USBD_QueryUsbCapability
0x140015958  test    eax, eax
0x14001595a  js      short loc_1400159AD
0x14001595c  mov     rcx, [rbx+10h]; DeviceObject
0x140015960  lea     rdx, [rbx+560h]
0x140015967  mov     dword ptr [rbx+360h], 1
0x140015971  call    RetrieveSecureInterface
0x140015976  mov     rcx, cs:WPP_GLOBAL_Control
0x14001597d  cmp     rcx, r12
0x140015980  jz      short loc_1400159AD
0x140015982  cmp     [rcx+29h], bpl
0x140015986  jb      short loc_1400159AD
0x140015988  mov     rcx, [rcx+18h]
0x14001598c  lea     r8, aIsNot; "IS NOT"
0x140015993  test    eax, eax
0x140015995  lea     rdx, aIs; "IS"
0x14001599c  mov     r9, rbx
0x14001599f  cmovs   rdx, r8
0x1400159a3  mov     [rsp+88h+USBDHandle], rdx
0x1400159a8  call    WPP_SF_qs
0x1400159ad  mov     rcx, [rbx+18h]; struct _KSDEVICE *
0x1400159b1  lea     r8, [rbx+2F8h]
0x1400159b8  call    CreateDeviceUtilityObject
0x1400159bd  test    eax, eax
0x1400159bf  js      loc_140015E44
0x1400159c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400159cc  cmp     rcx, r12
0x1400159cf  jz      short loc_1400159EB
0x1400159d1  cmp     [rcx+29h], bpl
0x1400159d5  jb      short loc_1400159EB
0x1400159d7  mov     rcx, [rcx+18h]
0x1400159db  mov     edx, 15h
0x1400159e0  mov     r9, rbx
0x1400159e3  mov     r8, r13
0x1400159e6  call    WPP_SF_q
0x1400159eb  mov     rcx, [rsi+20h]
0x1400159ef  lea     r9, [rsp+88h+arg_0]
0x1400159f7  lea     r8, aUvcflags_0; "UvcFlags"
0x1400159fe  mov     edx, 2
0x140015a03  call    GetDeviceRegValueDword
0x140015a08  test    eax, eax
0x140015a0a  js      short loc_140015A43
0x140015a0c  mov     eax, [rsp+88h+arg_0]
0x140015a13  mov     [rbx+2CCh], eax
0x140015a19  mov     rcx, cs:WPP_GLOBAL_Control
0x140015a20  cmp     rcx, r12
0x140015a23  jz      short loc_140015A43
0x140015a25  cmp     [rcx+29h], bpl
0x140015a29  jb      short loc_140015A43
0x140015a2b  mov     rcx, [rcx+18h]
0x140015a2f  mov     edx, 16h
0x140015a34  mov     r9, rbx
0x140015a37  mov     dword ptr [rsp+88h+USBDHandle], eax
0x140015a3b  mov     r8, r13
0x140015a3e  call    WPP_SF_qD
0x140015a43  or      dword ptr [rbx+2CCh], 2
0x140015a4a  lea     rcx, [rbx+1A0h]; SpinLock
0x140015a51  call    cs:__imp_KeInitializeSpinLock
0x140015a58  nop     dword ptr [rax+rax+00h]
0x140015a5d  mov     edi, 7FFFFFFFh
0x140015a62  lea     rcx, [rbx+260h]; Semaphore
0x140015a69  mov     r8d, edi; Limit
0x140015a6c  xor     edx, edx; Count
0x140015a6e  call    cs:__imp_KeInitializeSemaphore
0x140015a75  nop     dword ptr [rax+rax+00h]
0x140015a7a  lea     rcx, [rbx+328h]; Semaphore
0x140015a81  mov     r8d, edi; Limit
0x140015a84  xor     edx, edx; Count
0x140015a86  call    cs:__imp_KeInitializeSemaphore
0x140015a8d  nop     dword ptr [rax+rax+00h]
0x140015a92  lea     rax, [rbx+240h]
0x140015a99  mov     dword ptr [rsp+88h+USBDHandle], 20h ; ' '; RemlockSize
0x140015aa1  mov     [rax+8], rax
0x140015aa5  lea     rcx, [rbx+300h]; Lock
0x140015aac  mov     [rax], rax
0x140015aaf  xor     r9d, r9d; HighWatermark
0x140015ab2  lea     rax, [rbx+250h]
0x140015ab9  xor     r8d, r8d; MaxLockedMinutes
0x140015abc  mov     edx, 56627355h; AllocateTag
0x140015ac1  mov     [rax+8], rax
0x140015ac5  mov     [rax], rax
0x140015ac8  call    cs:__imp_IoInitializeRemoveLockEx
0x140015acf  nop     dword ptr [rax+rax+00h]
0x140015ad4  lea     rax, CsReleaseLock
0x140015adb  lea     rbp, CsCompleteCanceledIrp
0x140015ae2  mov     [rsp+88h+CsqCompleteCanceledIrp], rbp; CsqCompleteCanceledIrp
0x140015ae7  lea     rcx, [rbx+200h]; Csq
0x140015aee  mov     [rsp+88h+CsqReleaseLock], rax; CsqReleaseLock
0x140015af3  lea     r9, CsPeekNextIrpStatusInterruptQ; CsqPeekNextIrp
0x140015afa  lea     rax, CsAcquireLock
0x140015b01  lea     r8, FilterCreateQueue_RemoveIrp; CsqRemoveIrp
0x140015b08  mov     [rsp+88h+USBDHandle], rax; CsqAcquireLock
0x140015b0d  lea     rdx, CsInsertIrp; CsqInsertIrp
0x140015b14  call    cs:__imp_IoCsqInitialize
0x140015b1b  nop     dword ptr [rax+rax+00h]
0x140015b20  mov     edi, eax
0x140015b22  test    eax, eax
0x140015b24  js      loc_140015BF2
0x140015b2a  lea     rax, [rbx+1F0h]
0x140015b31  mov     [rsp+88h+CsqCompleteCanceledIrp], rbp; CsqCompleteCanceledIrp
0x140015b36  mov     [rax+8], rax
0x140015b3a  lea     rcx, [rbx+1B0h]; Csq
0x140015b41  mov     [rax], rax
0x140015b44  lea     r9, CsPeekNextIrpStatusInterruptQ; CsqPeekNextIrp
0x140015b4b  lea     rax, CsReleaseLockStatusInterruptQ
0x140015b52  mov     [rsp+88h+CsqReleaseLock], rax; CsqReleaseLock
0x140015b57  lea     r8, FilterCreateQueue_RemoveIrp; CsqRemoveIrp
0x140015b5e  lea     rax, CsAcquireLockStatusInterruptQ
0x140015b65  lea     rdx, CsInsertIrp; CsqInsertIrp
0x140015b6c  mov     [rsp+88h+USBDHandle], rax; CsqAcquireLock
0x140015b71  call    cs:__imp_IoCsqInitialize
0x140015b78  nop     dword ptr [rax+rax+00h]
0x140015b7d  mov     edi, eax
0x140015b7f  test    eax, eax
0x140015b81  js      short loc_140015BF2
0x140015b83  lea     rcx, [rbx+140h]; SpinLock
0x140015b8a  call    cs:__imp_KeInitializeSpinLock
0x140015b91  nop     dword ptr [rax+rax+00h]
0x140015b96  lea     rax, [rbx+148h]
0x140015b9d  mov     [rax+8], rax
0x140015ba1  lea     rcx, [rbx+100h]; Csq
0x140015ba8  mov     [rax], rax
0x140015bab  lea     r9, FilterCreateQueue_PeekNextIrp; CsqPeekNextIrp
0x140015bb2  lea     rax, FilterCreateQueue_CompleteCanceledIrp
0x140015bb9  mov     [rsp+88h+CsqCompleteCanceledIrp], rax; CsqCompleteCanceledIrp
  ... truncated ...
```
