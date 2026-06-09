# DriverEntry

- ea: `0x140019078`
- end: `0x140019737`
- name: `DriverEntry`
- size: `1727`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140019010`

## callees

- `0x14000ca14`
- `0x14000cd98`
- `0x14000ce4c`
- `0x14000d8b4`
- `0x14000d8ec`
- `0x14000d91c`
- `0x14000e0b4`
- `0x14000f500`
- `0x140017008`
- `0x14001732c`
- `0x140017474`
- `0x140019078`

## import_xrefs

- `ntoskrnl!IoUnregisterPlugPlayNotificationEx` at `0x140019691`
- `ntoskrnl!IoUnregisterPlugPlayNotificationEx` at `0x140019691`
- `ntoskrnl!ZwClose` at `0x140019659`
- `ntoskrnl!ZwClose` at `0x140019671`
- `ntoskrnl!ZwClose` at `0x140019706`
- `ntoskrnl!ZwClose` at `0x140019659`
- `ntoskrnl!ZwClose` at `0x140019671`
- `ntoskrnl!ZwClose` at `0x140019706`
- `ntoskrnl!ZwCreateKey` at `0x140019514`
- `ntoskrnl!ZwCreateKey` at `0x1400195d4`
- `ntoskrnl!ZwCreateKey` at `0x140019514`
- `ntoskrnl!ZwCreateKey` at `0x1400195d4`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x14001944d`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x14001944d`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x140019426`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x140019426`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400192d2`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400192d2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140019162`
- `ntoskrnl!RtlInitUnicodeString` at `0x140019179`
- `ntoskrnl!RtlInitUnicodeString` at `0x140019190`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400194b6`
- `ntoskrnl!RtlInitUnicodeString` at `0x140019576`
- `ntoskrnl!RtlInitUnicodeString` at `0x140019162`
- `ntoskrnl!RtlInitUnicodeString` at `0x140019179`
- `ntoskrnl!RtlInitUnicodeString` at `0x140019190`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400194b6`
- `ntoskrnl!RtlInitUnicodeString` at `0x140019576`
- `NDIS!NdisFDeregisterFilterDriver` at `0x1400196ba`
- `NDIS!NdisFDeregisterFilterDriver` at `0x1400196ba`
- `NDIS!NdisFRegisterFilterDriver` at `0x14001935b`
- `NDIS!NdisFRegisterFilterDriver` at `0x14001935b`

## string_xrefs

- `0x140019613`: `NULL != gVWiFihServiceKey`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  char v3; // r14
  struct _UNICODE_STRING v4; // xmm1
  struct _UNICODE_STRING v5; // xmm0
  NTSTATUS v6; // ebx
  char v7; // di
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  struct _UNICODE_STRING v11; // [rsp+40h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING v13; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING v14; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-60h] BYREF
  _NDIS_FILTER_DRIVER_CHARACTERISTICS FilterDriverCharacteristics; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE Handle; // [rsp+1D0h] [rbp+D0h] BYREF
  void *KeyHandle; // [rsp+1E0h] [rbp+E0h] BYREF

  memset(&FilterDriverCharacteristics, 0, sizeof(FilterDriverCharacteristics));
  DestinationString = 0;
  Handle = 0;
  v3 = 0;
  v14 = 0;
  KeyHandle = 0;
  v13 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v11 = 0;
  McGenEventRegister_EtwRegister();
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_FilterCtlGuid;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  RtlInitUnicodeString(&DestinationString, L"vwififlt");
  RtlInitUnicodeString(&v13, L"Virtual WiFi Filter Driver");
  RtlInitUnicodeString(&v14, L"{5cbf81bf-5055-47cd-9055-a76b2b4e3698}");
  v4 = v14;
  *(_QWORD *)&WPP_MAIN_CB.DeviceType = DriverObject;
  FilterDriverCharacteristics.AttachHandler = (FILTER_ATTACH_HANDLER)FilterAttach;
  *(_OWORD *)&FilterDriverCharacteristics.SetOptionsHandler = 0;
  FilterDriverCharacteristics.DetachHandler = (FILTER_DETACH_HANDLER)FilterDetach;
  *(_QWORD *)&FilterDriverCharacteristics.Flags = 2;
  FilterDriverCharacteristics.RestartHandler = (FILTER_RESTART_HANDLER)FilterRestart;
  FilterDriverCharacteristics.Header = (NDIS_OBJECT_HEADER)14680715;
  FilterDriverCharacteristics.PauseHandler = (FILTER_PAUSE_HANDLER)FilterPause;
  FilterDriverCharacteristics.OidRequestHandler = (FILTER_OID_REQUEST_HANDLER)FilterOidRequest;
  FilterDriverCharacteristics.OidRequestCompleteHandler = (FILTER_OID_REQUEST_COMPLETE_HANDLER)FilterOidRequestComplete;
  *(_DWORD *)&FilterDriverCharacteristics.MajorNdisVersion = 78342;
  FilterDriverCharacteristics.CancelOidRequestHandler = (FILTER_CANCEL_OID_REQUEST_HANDLER)&FilterCancelOidRequest;
  FilterDriverCharacteristics.DirectOidRequestHandler = (FILTER_DIRECT_OID_REQUEST_HANDLER)FilterDirectOidRequest;
  FilterDriverCharacteristics.DirectOidRequestCompleteHandler = (FILTER_DIRECT_OID_REQUEST_COMPLETE_HANDLER)FilterDirectOidRequestComplete;
  FilterDriverCharacteristics.CancelDirectOidRequestHandler = (FILTER_CANCEL_DIRECT_OID_REQUEST_HANDLER)&FilterCancelDirectOidRequest;
  FilterDriverCharacteristics.SendNetBufferListsHandler = (FILTER_SEND_NET_BUFFER_LISTS_HANDLER)FilterSendNetBufferLists;
  FilterDriverCharacteristics.ReturnNetBufferListsHandler = (FILTER_RETURN_NET_BUFFER_LISTS_HANDLER)&FilterReturnNetBufferLists;
  FilterDriverCharacteristics.SendNetBufferListsCompleteHandler = (FILTER_SEND_NET_BUFFER_LISTS_COMPLETE_HANDLER)&FilterSendNetBufferListsComplete;
  FilterDriverCharacteristics.ReceiveNetBufferListsHandler = (FILTER_RECEIVE_NET_BUFFER_LISTS_HANDLER)&FilterReceiveNetBufferLists;
  FilterDriverCharacteristics.DevicePnPEventNotifyHandler = (FILTER_DEVICE_PNP_EVENT_NOTIFY_HANDLER)&FilterDevicePnPEventNotify;
  FilterDriverCharacteristics.NetPnPEventHandler = (FILTER_NET_PNP_EVENT_HANDLER)&FilterNetPnPEvent;
  FilterDriverCharacteristics.StatusHandler = (FILTER_STATUS_HANDLER)FilterStatus;
  FilterDriverCharacteristics.FriendlyName = v13;
  FilterDriverCharacteristics.CancelSendNetBufferListsHandler = (FILTER_CANCEL_SEND_HANDLER)FilterCancelSendNetBufferLists;
  v5 = DestinationString;
  DriverObject->DriverUnload = (PDRIVER_UNLOAD)FilterUnload;
  WPP_MAIN_CB.DeviceExtension = 0;
  FilterDriverCharacteristics.UniqueName = v4;
  FilterDriverCharacteristics.ServiceName = v5;
  memset(&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels, 0, 0x60u);
  KeInitializeSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink);
  WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters = 1075;
  WPP_MAIN_CB.Queue.Wcb.DeviceContext = "DriverEntry";
  WPP_MAIN_CB.Queue.Wcb.WaitQueueEntry.SortKey = 1801678668;
  *(_QWORD *)&WPP_MAIN_CB.Dpc.TargetInfoAsUlong = &WPP_MAIN_CB.DeviceQueue.1;
  WPP_MAIN_CB.DeviceQueue.1 = (struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C)&WPP_MAIN_CB.DeviceQueue.1;
  WPP_MAIN_CB.Dpc.ProcessorHistory = (KAFFINITY)&WPP_MAIN_CB.Dpc.DpcListEntry;
  WPP_MAIN_CB.Dpc.DpcListEntry.Next = &WPP_MAIN_CB.Dpc.DpcListEntry;
  WPP_MAIN_CB.Dpc.DeferredContext = &WPP_MAIN_CB.Dpc.DeferredRoutine;
  WPP_MAIN_CB.Dpc.DeferredRoutine = (PKDEFERRED_ROUTINE)&WPP_MAIN_CB.Dpc.DeferredRoutine;
  g_fModuleInitialized = 1;
  v6 = NdisFRegisterFilterDriver(
         DriverObject,
         *(NDIS_HANDLE *)&WPP_MAIN_CB.DeviceType,
         &FilterDriverCharacteristics,
         &WPP_MAIN_CB.DeviceExtension);
  if ( v6 )
  {
    v7 = 0;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_36;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_33;
    v9 = 82;
    goto LABEL_8;
  }
  v7 = 1;
  if ( !_InterlockedExchangeAdd(&lDeviceRegistered, 1u) )
  {
    v6 = FilterRegisterDevice();
    if ( v6 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_36;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_33;
      v9 = 83;
      goto LABEL_8;
    }
  }
  v3 = 1;
  IoRegisterPlugPlayNotification(
    EventCategoryDeviceInterfaceChange,
    1u,
    &GUID_DEVINTERFACE_BUSENUM_VWIFI,
    *(PDRIVER_OBJECT *)&WPP_MAIN_CB.DeviceType,
    FilterBusDriverReadyCallbackRoutine,
    *(PVOID *)&WPP_MAIN_CB.DeviceType,
    &PnPNotificationHandle);
  v6 = IoOpenDriverRegistryKey(DriverObject, 1, 131103, 0, &Handle);
  if ( v6 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_36;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_33;
    v9 = 84;
    goto LABEL_8;
  }
  if ( !Handle )
    TraceAssert("NULL != hkRootSvc", "onecoreuap\\net\\vwifi\\filter\\filter.c", 1128);
  RtlInitUnicodeString(&v11, L"Parameters");
  ObjectAttributes.RootDirectory = Handle;
  ObjectAttributes.ObjectName = &v11;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = ZwCreateKey(&KeyHandle, 0x2001Fu, &ObjectAttributes, 0, 0, 0, 0);
  if ( v6 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_36;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_33;
    v9 = 85;
    goto LABEL_8;
  }
  if ( !KeyHandle )
    TraceAssert("NULL != hkParams", "onecoreuap\\net\\vwifi\\filter\\filter.c", 1149);
  RtlInitUnicodeString(&v11, L"VWifiSettings");
  ObjectAttributes.RootDirectory = KeyHandle;
  ObjectAttributes.ObjectName = &v11;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = ZwCreateKey(&::Handle, 0x2001Fu, &ObjectAttributes, 0, 0, 0, 0);
  if ( !v6 )
  {
    if ( !::Handle )
      TraceAssert("NULL != gVWiFihServiceKey", "onecoreuap\\net\\vwifi\\filter\\filter.c", 1170);
    goto LABEL_33;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_36;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v9 = 86;
LABEL_8:
    WPP_SF_d(v8->AttachedDevice, v9, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  }
LABEL_33:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 87, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
LABEL_36:
  if ( Handle )
    ZwClose(Handle);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( v6 )
  {
    if ( PnPNotificationHandle )
    {
      IoUnregisterPlugPlayNotificationEx(PnPNotificationHandle);
      PnPNotificationHandle = 0;
    }
    if ( v3 )
      FilterDeregisterDevice();
    if ( v7 )
      NdisFDeregisterFilterDriver(WPP_MAIN_CB.DeviceExtension);
    memset(&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels, 0, 0x60u);
    LODWORD(WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink) = 1205;
    *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type = "DriverEntry";
    WppCleanupKm();
    McGenEventUnregister_EtwUnregister();
    if ( ::Handle )
    {
      ZwClose(::Handle);
      ::Handle = 0;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x140019078  mov     [rsp-8+arg_8], rbx
0x14001907d  push    rbp
0x14001907e  push    rsi
0x14001907f  push    rdi
0x140019080  push    r12
0x140019082  push    r13
0x140019084  push    r14
0x140019086  push    r15
0x140019088  lea     rbp, [rsp-90h]
0x140019090  sub     rsp, 190h
0x140019097  mov     rsi, rcx
0x14001909a  xor     edx, edx; Val
0x14001909c  lea     rcx, [rbp+0C0h+FilterDriverCharacteristics]; void *
0x1400190a0  mov     r8d, 0E0h; Size
0x1400190a6  call    memset
0x1400190ab  xorps   xmm1, xmm1
0x1400190ae  xorps   xmm0, xmm0
0x1400190b1  xor     r15d, r15d
0x1400190b4  movups  xmmword ptr [rbp+0C0h+DestinationString.Length], xmm0
0x1400190b8  mov     [rbp+0C0h+Handle], r15
0x1400190bf  mov     r14b, r15b
0x1400190c2  movups  xmmword ptr [rbp+0C0h+var_130.Length], xmm1
0x1400190c6  mov     [rbp+0C0h+KeyHandle], r15
0x1400190cd  movups  xmmword ptr [rbp+0C0h+var_140.Length], xmm0
0x1400190d1  movups  xmmword ptr [rsp+1C0h+ObjectAttributes.Length], xmm1
0x1400190d6  movups  xmmword ptr [rsp+1C0h+ObjectAttributes.ObjectName], xmm1
0x1400190db  movups  xmmword ptr [rsp+1C0h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400190e0  movups  xmmword ptr [rsp+1C0h+var_180.Length], xmm0
0x1400190e5  call    McGenEventRegister_EtwRegister
0x1400190ea  lea     rax, WPP_ThisDir_CTLGUID_FilterCtlGuid
0x1400190f1  mov     qword ptr cs:WPP_MAIN_CB.Type, r15
0x1400190f8  lea     r12d, [r15+1]
0x1400190fc  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x140019103  mov     cs:WPP_MAIN_CB.NextDevice, r15
0x14001910a  mov     cs:WPP_MAIN_CB.CurrentIrp, r15
0x140019111  mov     cs:WPP_MAIN_CB.Timer, r12
0x140019118  call    WppLoadTracingSupport
0x14001911d  mov     cs:WPP_MAIN_CB.CurrentIrp, r15
0x140019124  call    WppInitKm
0x140019129  mov     rcx, cs:WPP_GLOBAL_Control
0x140019130  lea     r13, WPP_GLOBAL_Control
0x140019137  cmp     rcx, r13
0x14001913a  jz      short loc_140019157
0x14001913c  mov     eax, [rcx+2Ch]
0x14001913f  test    al, 20h
0x140019141  jz      short loc_140019157
0x140019143  mov     rcx, [rcx+18h]
0x140019147  lea     edx, [r15+51h]
0x14001914b  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140019152  call    WPP_SF_
0x140019157  lea     rdx, aVwififlt; "vwififlt"
0x14001915e  lea     rcx, [rbp+0C0h+DestinationString]; DestinationString
0x140019162  call    cs:__imp_RtlInitUnicodeString
0x140019169  nop     dword ptr [rax+rax+00h]
0x14001916e  lea     rdx, aVirtualWifiFil; "Virtual WiFi Filter Driver"
0x140019175  lea     rcx, [rbp+0C0h+var_140]; DestinationString
0x140019179  call    cs:__imp_RtlInitUnicodeString
0x140019180  nop     dword ptr [rax+rax+00h]
0x140019185  lea     rdx, a5cbf81bf505547; "{5cbf81bf-5055-47cd-9055-a76b2b4e3698}"
0x14001918c  lea     rcx, [rbp+0C0h+var_130]; DestinationString
0x140019190  call    cs:__imp_RtlInitUnicodeString
0x140019197  nop     dword ptr [rax+rax+00h]
0x14001919c  movups  xmm1, xmmword ptr [rbp+0C0h+var_130.Length]
0x1400191a0  mov     qword ptr cs:WPP_MAIN_CB.DeviceType, rsi
0x1400191a7  lea     rax, FilterAttach
0x1400191ae  mov     [rbp+0C0h+FilterDriverCharacteristics.AttachHandler], rax
0x1400191b2  xorps   xmm0, xmm0
0x1400191b5  lea     rax, FilterDetach
0x1400191bc  movaps  xmmword ptr [rbp+0C0h+FilterDriverCharacteristics.SetOptionsHandler], xmm0
0x1400191c0  movups  xmm0, xmmword ptr [rbp+0C0h+var_140.Length]
0x1400191c4  mov     [rbp+0C0h+FilterDriverCharacteristics.DetachHandler], rax
0x1400191c8  lea     rcx, WPP_MAIN_CB.Queue+10h; void *
0x1400191cf  lea     rax, FilterRestart
0x1400191d6  mov     qword ptr [rbp+0C0h+FilterDriverCharacteristics.Flags], 2
0x1400191de  mov     [rbp+0C0h+FilterDriverCharacteristics.RestartHandler], rax
0x1400191e2  xor     edx, edx; Val
0x1400191e4  lea     rax, FilterPause
0x1400191eb  mov     dword ptr [rbp+0C0h+FilterDriverCharacteristics.Header.Type], 0E0028Bh
0x1400191f2  mov     [rbp+0C0h+FilterDriverCharacteristics.PauseHandler], rax
0x1400191f6  lea     rax, FilterOidRequest
0x1400191fd  mov     [rbp+0C0h+FilterDriverCharacteristics.OidRequestHandler], rax
0x140019201  lea     rax, FilterOidRequestComplete
0x140019208  mov     [rbp+0C0h+FilterDriverCharacteristics.OidRequestCompleteHandler], rax
0x14001920c  lea     r8d, [rdx+60h]; Size
0x140019210  lea     rax, FilterCancelOidRequest
0x140019217  mov     dword ptr [rbp+0C0h+FilterDriverCharacteristics.MajorNdisVersion], 13206h
0x14001921e  mov     [rbp+0C0h+FilterDriverCharacteristics.CancelOidRequestHandler], rax
0x140019222  lea     rax, FilterDirectOidRequest
0x140019229  mov     [rbp+0C0h+FilterDriverCharacteristics.DirectOidRequestHandler], rax
0x14001922d  lea     rax, FilterDirectOidRequestComplete
0x140019234  mov     [rbp+0C0h+FilterDriverCharacteristics.DirectOidRequestCompleteHandler], rax
0x14001923b  lea     rax, FilterCancelDirectOidRequest
0x140019242  mov     [rbp+0C0h+FilterDriverCharacteristics.CancelDirectOidRequestHandler], rax
0x140019249  lea     rax, FilterSendNetBufferLists
0x140019250  mov     [rbp+0C0h+FilterDriverCharacteristics.SendNetBufferListsHandler], rax
0x140019254  lea     rax, FilterReturnNetBufferLists
0x14001925b  mov     [rbp+0C0h+FilterDriverCharacteristics.ReturnNetBufferListsHandler], rax
0x14001925f  lea     rax, FilterSendNetBufferListsComplete
0x140019266  mov     [rbp+0C0h+FilterDriverCharacteristics.SendNetBufferListsCompleteHandler], rax
0x14001926a  lea     rax, FilterReceiveNetBufferLists
0x140019271  mov     [rbp+0C0h+FilterDriverCharacteristics.ReceiveNetBufferListsHandler], rax
0x140019275  lea     rax, FilterDevicePnPEventNotify
0x14001927c  mov     [rbp+0C0h+FilterDriverCharacteristics.DevicePnPEventNotifyHandler], rax
0x140019280  lea     rax, FilterNetPnPEvent
0x140019287  mov     [rbp+0C0h+FilterDriverCharacteristics.NetPnPEventHandler], rax
0x14001928b  lea     rax, FilterStatus
0x140019292  mov     [rbp+0C0h+FilterDriverCharacteristics.StatusHandler], rax
0x140019296  lea     rax, FilterCancelSendNetBufferLists
0x14001929d  movdqu  xmmword ptr [rbp+0C0h+FilterDriverCharacteristics.FriendlyName.Length], xmm0
0x1400192a2  mov     [rbp+0C0h+FilterDriverCharacteristics.CancelSendNetBufferListsHandler], rax
0x1400192a6  lea     rax, FilterUnload
0x1400192ad  movups  xmm0, xmmword ptr [rbp+0C0h+DestinationString.Length]
0x1400192b1  mov     [rsi+68h], rax
0x1400192b5  mov     cs:WPP_MAIN_CB.DeviceExtension, r15
0x1400192bc  movdqu  xmmword ptr [rbp+0C0h+FilterDriverCharacteristics.UniqueName.Length], xmm1
0x1400192c1  movdqu  xmmword ptr [rbp+0C0h+FilterDriverCharacteristics.ServiceName.Length], xmm0
0x1400192c6  call    memset
0x1400192cb  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink; SpinLock
0x1400192d2  call    cs:__imp_KeInitializeSpinLock
0x1400192d9  nop     dword ptr [rax+rax+00h]
0x1400192de  lea     rax, aDriverentry; "DriverEntry"
0x1400192e5  mov     dword ptr cs:WPP_MAIN_CB.Queue+28h, 433h
0x1400192ef  mov     qword ptr cs:WPP_MAIN_CB.Queue+20h, rax
0x1400192f6  lea     r9, WPP_MAIN_CB.DeviceExtension; NdisFilterDriverHandle
0x1400192fd  lea     rax, WPP_MAIN_CB.DeviceQueue.20h
0x140019304  mov     dword ptr cs:WPP_MAIN_CB.Queue+10h, 6B636F4Ch
0x14001930e  mov     qword ptr cs:WPP_MAIN_CB.Dpc, rax
0x140019315  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h, rax
0x14001931c  lea     rax, WPP_MAIN_CB.Dpc.DpcListEntry
0x140019323  mov     cs:WPP_MAIN_CB.Dpc.ProcessorHistory, rax
0x14001932a  mov     cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next, rax
0x140019331  lea     rax, WPP_MAIN_CB.Dpc.DeferredRoutine
0x140019338  mov     cs:WPP_MAIN_CB.Dpc.DeferredContext, rax
0x14001933f  mov     cs:WPP_MAIN_CB.Dpc.DeferredRoutine, rax
0x140019346  mov     cs:g_fModuleInitialized, r12b
0x14001934d  mov     rdx, qword ptr cs:WPP_MAIN_CB.DeviceType; FilterDriverContext
0x140019354  lea     r8, [rbp+0C0h+FilterDriverCharacteristics]; FilterDriverCharacteristics
0x140019358  mov     rcx, rsi; DriverObject
0x14001935b  call    cs:__imp_NdisFRegisterFilterDriver
0x140019362  nop     dword ptr [rax+rax+00h]
0x140019367  mov     ebx, eax
0x140019369  test    eax, eax
0x14001936b  jz      short loc_1400193A9
0x14001936d  mov     dil, r15b
0x140019370  mov     rcx, cs:WPP_GLOBAL_Control
0x140019377  cmp     rcx, r13
0x14001937a  jz      loc_14001964D
0x140019380  mov     edx, [rcx+2Ch]
0x140019383  test    r12b, dl
0x140019386  jz      loc_140019622
0x14001938c  mov     edx, 52h ; 'R'
0x140019391  mov     r9d, eax
0x140019394  mov     rcx, [rcx+18h]
0x140019398  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14001939f  call    WPP_SF_d
0x1400193a4  jmp     loc_140019622
0x1400193a9  mov     dil, r12b
0x1400193ac  mov     eax, r12d
0x1400193af  lock xadd cs:lDeviceRegistered, eax
0x1400193b7  add     eax, r12d
0x1400193ba  cmp     eax, r12d
0x1400193bd  jnz     short loc_1400193F0
0x1400193bf  call    FilterRegisterDevice
0x1400193c4  mov     ebx, eax
0x1400193c6  test    eax, eax
0x1400193c8  jz      short loc_1400193F0
0x1400193ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400193d1  cmp     rcx, r13
0x1400193d4  jz      loc_14001964D
0x1400193da  mov     eax, [rcx+2Ch]
0x1400193dd  test    r12b, al
0x1400193e0  jz      loc_140019622
0x1400193e6  mov     edx, 53h ; 'S'
0x1400193eb  mov     r9d, ebx
0x1400193ee  jmp     short loc_140019394
0x1400193f0  mov     r9, qword ptr cs:WPP_MAIN_CB.DeviceType; DriverObject
0x1400193f7  lea     rax, PnPNotificationHandle
0x1400193fe  mov     [rsp+1C0h+NotificationEntry], rax; NotificationEntry
0x140019403  lea     r8, GUID_DEVINTERFACE_BUSENUM_VWIFI; EventCategoryData
0x14001940a  lea     rax, FilterBusDriverReadyCallbackRoutine
0x140019411  mov     [rsp+1C0h+Context], r9; Context
0x140019416  mov     edx, r12d; EventCategoryFlags
0x140019419  mov     [rsp+1C0h+CallbackRoutine], rax; CallbackRoutine
0x14001941e  mov     ecx, 2; EventCategory
0x140019423  mov     r14b, r12b
0x140019426  call    cs:__imp_IoRegisterPlugPlayNotification
0x14001942d  nop     dword ptr [rax+rax+00h]
0x140019432  lea     rax, [rbp+0C0h+Handle]
0x140019439  xor     r9d, r9d
0x14001943c  mov     r8d, 2001Fh
0x140019442  mov     [rsp+1C0h+CallbackRoutine], rax
0x140019447  mov     edx, r12d
0x14001944a  mov     rcx, rsi
0x14001944d  call    cs:__imp_IoOpenDriverRegistryKey
0x140019454  nop     dword ptr [rax+rax+00h]
0x140019459  mov     ebx, eax
0x14001945b  test    eax, eax
0x14001945d  jz      short loc_140019485
0x14001945f  mov     rcx, cs:WPP_GLOBAL_Control
0x140019466  cmp     rcx, r13
0x140019469  jz      loc_14001964D
0x14001946f  mov     eax, [rcx+2Ch]
0x140019472  test    r12b, al
0x140019475  jz      loc_140019622
0x14001947b  mov     edx, 54h ; 'T'
0x140019480  jmp     loc_1400193EB
0x140019485  lea     rsi, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x14001948c  cmp     [rbp+0C0h+Handle], r15
0x140019493  jnz     short loc_1400194AA
0x140019495  mov     r8d, 468h
0x14001949b  lea     rcx, aNullHkrootsvc; "NULL != hkRootSvc"
0x1400194a2  mov     rdx, rsi
0x1400194a5  call    TraceAssert
0x1400194aa  lea     rdx, aParameters; "Parameters"
0x1400194b1  lea     rcx, [rsp+1C0h+var_180]; DestinationString
0x1400194b6  call    cs:__imp_RtlInitUnicodeString
0x1400194bd  nop     dword ptr [rax+rax+00h]
0x1400194c2  mov     rax, [rbp+0C0h+Handle]
0x1400194c9  lea     r8, [rsp+1C0h+ObjectAttributes]; ObjectAttributes
0x1400194ce  mov     [rsp+1C0h+ObjectAttributes.RootDirectory], rax
0x1400194d3  lea     rcx, [rbp+0C0h+KeyHandle]; KeyHandle
0x1400194da  lea     rax, [rsp+1C0h+var_180]
0x1400194df  mov     [rsp+1C0h+NotificationEntry], r15; Disposition
0x1400194e4  xorps   xmm0, xmm0
0x1400194e7  mov     dword ptr [rsp+1C0h+Context], r15d; CreateOptions
0x1400194ec  xor     r9d, r9d; TitleIndex
0x1400194ef  mov     [rsp+1C0h+ObjectAttributes.ObjectName], rax
0x1400194f4  mov     edx, 2001Fh; DesiredAccess
0x1400194f9  mov     [rsp+1C0h+ObjectAttributes.Length], 30h ; '0'
0x140019501  mov     [rsp+1C0h+ObjectAttributes.Attributes], 240h
0x140019509  movdqu  xmmword ptr [rsp+1C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001950f  mov     [rsp+1C0h+CallbackRoutine], r15; Class
0x140019514  call    cs:__imp_ZwCreateKey
0x14001951b  nop     dword ptr [rax+rax+00h]
0x140019520  mov     ebx, eax
0x140019522  test    eax, eax
0x140019524  jz      short loc_14001954C
0x140019526  mov     rcx, cs:WPP_GLOBAL_Control
0x14001952d  cmp     rcx, r13
0x140019530  jz      loc_14001964D
0x140019536  mov     eax, [rcx+2Ch]
0x140019539  test    r12b, al
0x14001953c  jz      loc_140019622
0x140019542  mov     edx, 55h ; 'U'
0x140019547  jmp     loc_1400193EB
0x14001954c  cmp     [rbp+0C0h+KeyHandle], r15
0x140019553  jnz     short loc_14001956A
0x140019555  mov     r8d, 47Dh
0x14001955b  lea     rcx, aNullHkparams; "NULL != hkParams"
0x140019562  mov     rdx, rsi
0x140019565  call    TraceAssert
0x14001956a  lea     rdx, aVwifisettings; "VWifiSettings"
0x140019571  lea     rcx, [rsp+1C0h+var_180]; DestinationString
0x140019576  call    cs:__imp_RtlInitUnicodeString
0x14001957d  nop     dword ptr [rax+rax+00h]
0x140019582  mov     rax, [rbp+0C0h+KeyHandle]
0x140019589  lea     r8, [rsp+1C0h+ObjectAttributes]; ObjectAttributes
0x14001958e  mov     [rsp+1C0h+ObjectAttributes.RootDirectory], rax
0x140019593  lea     rcx, Handle; KeyHandle
0x14001959a  lea     rax, [rsp+1C0h+var_180]
0x14001959f  mov     [rsp+1C0h+NotificationEntry], r15; Disposition
0x1400195a4  xorps   xmm0, xmm0
0x1400195a7  mov     dword ptr [rsp+1C0h+Context], r15d; CreateOptions
0x1400195ac  xor     r9d, r9d; TitleIndex
0x1400195af  mov     [rsp+1C0h+ObjectAttributes.ObjectName], rax
0x1400195b4  mov     edx, 2001Fh; DesiredAccess
0x1400195b9  mov     [rsp+1C0h+ObjectAttributes.Length], 30h ; '0'
0x1400195c1  mov     [rsp+1C0h+ObjectAttributes.Attributes], 240h
0x1400195c9  movdqu  xmmword ptr [rsp+1C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400195cf  mov     [rsp+1C0h+CallbackRoutine], r15; Class
0x1400195d4  call    cs:__imp_ZwCreateKey
0x1400195db  nop     dword ptr [rax+rax+00h]
0x1400195e0  mov     ebx, eax
0x1400195e2  test    eax, eax
0x1400195e4  jz      short loc_140019604
0x1400195e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400195ed  cmp     rcx, r13
0x1400195f0  jz      short loc_14001964D
0x1400195f2  mov     eax, [rcx+2Ch]
0x1400195f5  test    r12b, al
0x1400195f8  jz      short loc_140019622
0x1400195fa  mov     edx, 56h ; 'V'
0x1400195ff  jmp     loc_1400193EB
0x140019604  cmp     cs:Handle, r15
0x14001960b  jnz     short loc_140019622
0x14001960d  mov     r8d, 492h
0x140019613  lea     rcx, aNullGvwifihser; "NULL != gVWiFihServiceKey"
0x14001961a  mov     rdx, rsi
0x14001961d  call    TraceAssert
0x140019622  mov     rcx, cs:WPP_GLOBAL_Control
0x140019629  cmp     rcx, r13
0x14001962c  jz      short loc_14001964D
0x14001962e  mov     eax, [rcx+2Ch]
0x140019631  test    al, 20h
0x140019633  jz      short loc_14001964D
0x140019635  mov     rcx, [rcx+18h]
0x140019639  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140019640  mov     edx, 57h ; 'W'
0x140019645  mov     r9d, ebx
0x140019648  call    WPP_SF_d
  ... truncated ...
```
