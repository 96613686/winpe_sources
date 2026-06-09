# TpmEvtDeviceAdd

- ea: `0x140013da0`
- end: `0x140014835`
- name: `TpmEvtDeviceAdd`
- size: `2709`
- prototype: `__int64 __fastcall(__int64, struct WDFDEVICE_INIT *)`
- caller_count: `0`
- callee_count: `19`
- tags: `reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1400078b8`
- `0x140008f6c`
- `0x140013da0`
- `0x14001483c`
- `0x140018fc8`
- `0x1400194a0`
- `0x140019c7c`
- `0x14001a88c`
- `0x14001aa78`
- `0x14001d44c`
- `0x14001d69c`
- `0x14002fda4`
- `0x140039740`
- `0x140039780`
- `0x140039b40`
- `0x140044dcc`
- `0x140045070`
- `0x140045430`
- `0x1400454a0`

## import_xrefs

- `ntoskrnl!ExIsSoftBoot` at `0x140013ea1`
- `ntoskrnl!ExIsSoftBoot` at `0x140013ea1`
- `ntoskrnl!IoQueryKsrPersistentMemorySize` at `0x140013eec`
- `ntoskrnl!IoQueryKsrPersistentMemorySize` at `0x140013eec`
- `ntoskrnl!IoAcquireKsrPersistentMemory` at `0x140013f6c`
- `ntoskrnl!IoAcquireKsrPersistentMemory` at `0x140013f6c`
- `ntoskrnl!IoGetDeviceProperty` at `0x14001469d`
- `ntoskrnl!IoGetDeviceProperty` at `0x14001469d`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400146e1`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400146e1`
- `ntoskrnl!ExAllocatePool2` at `0x14001471d`
- `ntoskrnl!ExAllocatePool2` at `0x14001471d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400146cc`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400146cc`

## string_xrefs

- `0x140014752`: `\BaseNamedObjects\SC_AutoStartComplete`

## pseudocode

```c
__int64 __fastcall TpmEvtDeviceAdd(__int64 a1, struct WDFDEVICE_INIT *a2)
{
  unsigned __int8 *v3; // rsi
  char IsSoftBoot; // r14
  __int64 v5; // rax
  int v6; // eax
  int v7; // ecx
  int v8; // r8d
  int v9; // edi
  __int64 v10; // rax
  int v11; // eax
  int v12; // ecx
  int v13; // r8d
  int v14; // edi
  struct _DRIVER_OBJECT *const v15; // rcx
  __int64 v16; // rcx
  NTSTATUS HiddenDummyDevice; // ebx
  int v18; // eax
  int v19; // ecx
  int v20; // r8d
  __int64 v22; // r9
  __int64 v23; // r9
  TpmDevice *v24; // rax
  struct TpmDevice *v25; // rdi
  struct _TPM_DEVICE_STATE *v26; // rdx
  struct _DEVICE_OBJECT *v27; // rax
  unsigned __int64 *Pool2; // rax
  unsigned __int8 v29; // r8
  unsigned __int64 *v30; // rdi
  char v31[8]; // [rsp+40h] [rbp-C0h] BYREF
  struct WDFDEVICE__ *v32; // [rsp+48h] [rbp-B8h] BYREF
  struct WDFDEVICE_INIT *v33; // [rsp+50h] [rbp-B0h] BYREF
  ULONG ResultLength; // [rsp+58h] [rbp-A8h] BYREF
  PVOID PropertyBuffer[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v36; // [rsp+70h] [rbp-90h] BYREF
  __int128 v37; // [rsp+78h] [rbp-88h] BYREF
  __int128 v38; // [rsp+88h] [rbp-78h]
  __int128 v39; // [rsp+98h] [rbp-68h]
  void *v40; // [rsp+A8h] [rbp-58h]
  struct TpmStack *v41; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v42; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v43; // [rsp+C8h] [rbp-38h]
  __int64 (__fastcall *v44)(void *, bool); // [rsp+D8h] [rbp-28h]
  __int64 v45; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v46; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v47; // [rsp+F8h] [rbp-8h]
  __int64 v48; // [rsp+108h] [rbp+8h]
  __int128 v49; // [rsp+110h] [rbp+10h] BYREF
  __int128 v50; // [rsp+120h] [rbp+20h]
  __int128 v51; // [rsp+130h] [rbp+30h]
  __int128 v52; // [rsp+140h] [rbp+40h] BYREF
  __int128 v53; // [rsp+150h] [rbp+50h]
  __int128 v54; // [rsp+160h] [rbp+60h]
  __int64 v55; // [rsp+170h] [rbp+70h]
  struct _UNICODE_STRING DestinationString; // [rsp+178h] [rbp+78h] BYREF
  _QWORD v57[12]; // [rsp+190h] [rbp+90h] BYREF
  _QWORD v58[18]; // [rsp+1F0h] [rbp+F0h] BYREF
  _OWORD v59[2]; // [rsp+280h] [rbp+180h] BYREF
  _QWORD v60[10]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int64 retaddr; // [rsp+338h] [rbp+238h]

  v33 = a2;
  v40 = 0;
  v55 = 0;
  memset(v59, 0, 28);
  v32 = 0;
  v48 = 0;
  v31[0] = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v46 = 0;
  v47 = 0;
  memset(v58, 0, sizeof(v58));
  memset(v60, 0, sizeof(v60));
  v45 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  memset(v57, 0, sizeof(v57));
  ResultLength = 0;
  v41 = 0;
  v36 = 0;
  PropertyBuffer[0] = 0;
  v44 = 0;
  v3 = 0;
  DestinationString = 0;
  v42 = 0;
  v43 = 0;
  PropertyBuffer[1] = 0;
  IsSoftBoot = ExIsSoftBoot();
  if ( !IsSoftBoot )
    goto LABEL_13;
  v5 = (*((__int64 (__fastcall **)(PKDPC, __int64))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 118))(
         WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
         a1);
  v6 = IoQueryKsrPersistentMemorySize(v5, 0, &v36);
  v9 = v6;
  if ( (TPMEnableBits & 2) != 0 )
    McTemplateK0zq_EtwWriteTransfer(
      v7,
      (unsigned int)TPM_KSR_INFORMATION,
      v8,
      (unsigned int)L"DeviceAdd: IoQueryKsrPersistentMemorySize",
      v6);
  if ( v9 < 0 || (v3 = TpmAlloc(1, v36, retaddr)) == 0 )
  {
LABEL_12:
    (*((void (__fastcall **)(PKDPC, __int64))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 118))(
      WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
      a1);
    TpmTransportType::Determine(v15);
    goto LABEL_13;
  }
  v10 = (*((__int64 (__fastcall **)(PKDPC, __int64))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 118))(
          WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
          a1);
  v11 = IoAcquireKsrPersistentMemory(v10, 0, v3, &v36);
  v14 = v11;
  if ( (TPMEnableBits & 2) != 0 )
    McTemplateK0zq_EtwWriteTransfer(
      v12,
      (unsigned int)TPM_KSR_INFORMATION,
      v13,
      (unsigned int)L"DeviceAdd: IoAcquireKsrPersistentMemory",
      v11);
  if ( v14 < 0 )
  {
    TpmFree(v3);
    v3 = 0;
    goto LABEL_12;
  }
  TpmTransportType::m_Version = *((_DWORD *)v3 + 1);
  LODWORD(WPP_MAIN_CB.DeviceExtension) = *((_DWORD *)v3 + 2);
  TpmTransportType::m_TalkingToTpmSimulator = *((_DWORD *)v3 + 3);
  if ( (TPMEnableBits & 2) != 0 )
    McTemplateK0zq_EtwWriteTransfer(
      v12,
      (unsigned int)TPM_KSR_INFORMATION,
      v13,
      (unsigned int)L"DeviceAdd: Restore TpmTransportType",
      0);
LABEL_13:
  if ( !(unsigned int)TpmTransportType::IsDeviceMatch(v33) )
  {
    HiddenDummyDevice = TpmCreateHiddenDummyDevice(v33);
    goto LABEL_55;
  }
  if ( qword_140047DB8 )
  {
    HiddenDummyDevice = -1073741438;
    goto LABEL_55;
  }
  g_fpW8TpmSubmit = (unsigned int (*)(void *, unsigned __int8 *const, unsigned int, unsigned __int8 *, unsigned int *))TpmApiPlatformW8TbsSubmit;
  g_fpGetRandom = (int (*)(unsigned __int8 *, unsigned int))TpmApiPlatformGetRandom;
  g_fpHash = (int (*)(unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *, unsigned int))TpmApiPlatformHash;
  g_fpAesCfbEncrypt = (int (*)(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *))TpmApiPlatformAesCfbEncrypt;
  g_fpAesCfbDecrypt = (int (*)(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *))TpmApiPlatformAesCfbDecrypt;
  qword_1400480B8 = (__int64)&TpmDrvTpmApiAllocCallback;
  qword_1400480B0 = (__int64)&TpmDrvTpmApiFreeCallback;
  v18 = TpmApiSetTpmCallback(v16, (unsigned int)(TpmTransportType::m_Version == 2) + 1);
  if ( v18 >= 0 )
  {
    memset(v58, 0, sizeof(v58));
    v58[1] = &TpmEvtDeviceD0Entry;
    v58[3] = &TpmEvtDeviceD0Exit;
    v58[5] = TpmEvtDevicePrepareHardware;
    v58[6] = TpmEvtDeviceReleaseHardware;
    v58[14] = TpmEvtDeviceQueryStop;
    v58[13] = TpmEvtDeviceQueryStop;
    v58[9] = TpmEvtDeviceSelfManagedIoInit;
    v58[7] = TpmEvtDeviceSelfManagedIoCleanup;
    LODWORD(v58[0]) = 144;
    (*((void (__fastcall **)(PKDPC, struct WDFDEVICE_INIT *, _QWORD *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 55))(
      WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
      v33,
      v58);
    v40 = off_140047040;
    *(_QWORD *)&v53 = 0;
    *(_QWORD *)&v37 = 56;
    v52 = 0;
    LODWORD(v52) = 56;
    *((_QWORD *)&v37 + 1) = TpmEvtDeviceContextCleanup;
    v55 = 0;
    *(_QWORD *)&v38 = 0;
    v39 = 0;
    *((_QWORD *)&v46 + 1) = TpmEvtDeviceFileCreate;
    *(_QWORD *)&v47 = TpmEvtFileClose;
    *((_QWORD *)&v38 + 1) = 0x100000002LL;
    v54 = 0;
    *((_QWORD *)&v53 + 1) = 0x400000001LL;
    LODWORD(v46) = 40;
    *((_QWORD *)&v47 + 1) = 0;
    v48 = 0x400000002LL;
    (*((void (__fastcall **)(PKDPC, struct WDFDEVICE_INIT *, __int128 *, __int128 *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp
     + 71))(
      WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
      v33,
      &v46,
      &v52);
    v31[0] = 7;
    LOBYTE(v22) = 27;
    HiddenDummyDevice = (*((__int64 (__fastcall **)(PKDPC, struct WDFDEVICE_INIT *, __int64 (__fastcall *)(), __int64, char *, int))WPP_MAIN_CB.Queue.Wcb.CurrentIrp
                         + 73))(
                          WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
                          v33,
                          TpmEvtIrpPreprocessQueryDevRelations,
                          v22,
                          v31,
                          1);
    if ( HiddenDummyDevice < 0 )
      goto LABEL_55;
    v31[0] = 2;
    LOBYTE(v23) = 22;
    HiddenDummyDevice = (*((__int64 (__fastcall **)(PKDPC, struct WDFDEVICE_INIT *, __int64 (__fastcall *)(), __int64, char *, int))WPP_MAIN_CB.Queue.Wcb.CurrentIrp
                         + 73))(
                          WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
                          v33,
                          TpmEvtIrpPreprocessSetPower,
                          v23,
                          v31,
                          1);
    if ( HiddenDummyDevice < 0 )
      goto LABEL_55;
    HiddenDummyDevice = (*((__int64 (__fastcall **)(PKDPC, struct WDFDEVICE_INIT **, __int128 *, struct WDFDEVICE__ **))WPP_MAIN_CB.Queue.Wcb.CurrentIrp
                         + 75))(
                          WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
                          &v33,
                          &v37,
                          &v32);
    if ( HiddenDummyDevice < 0 )
      goto LABEL_55;
    memset(v57, 0, sizeof(v57));
    v57[7] = TpmEvtIoStop;
    v57[0] = 0x200000060LL;
    v57[5] = &TpmEvtIoDeviceControl;
    LODWORD(v57[1]) = 2;
    BYTE5(v57[1]) = 1;
    LODWORD(v57[10]) = -1;
    HiddenDummyDevice = (*((__int64 (__fastcall **)(PKDPC, struct WDFDEVICE__ *, _QWORD *, _QWORD, __int64 *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp
                         + 152))(
                          WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
                          v32,
                          v57,
                          0,
                          &v45);
    if ( HiddenDummyDevice < 0 )
      goto LABEL_55;
    if ( (unsigned __int8)TpmIsAllowRemovalRequested() )
    {
      *(_QWORD *)&v59[0] = 0x20000001CLL;
      DWORD2(v59[0]) = 2;
      *(_QWORD *)((char *)v59 + 12) = 2;
      *(_QWORD *)((char *)&v59[1] + 4) = 0x200000002LL;
      (*((void (__fastcall **)(PKDPC, struct WDFDEVICE__ *, _OWORD *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 29))(
        WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
        v32,
        v59);
    }
    v60[7] = 0x700000005LL;
    *(__m128i *)((char *)&v60[3] + 4) = _mm_load_si128((const __m128i *)&_xmm);
    v60[0] = 0x200000050LL;
    v60[1] = 0x200000002LL;
    v60[2] = 0x200000002LL;
    LODWORD(v60[3]) = 2;
    *(_OWORD *)&v60[5] = *(_OWORD *)((char *)&v60[3] + 4);
    v60[8] = -1;
    v60[9] = 0x5FFFFFFFFLL;
    (*((void (__fastcall **)(PKDPC, struct WDFDEVICE__ *, _QWORD *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 84))(
      WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
      v32,
      v60);
    v24 = (TpmDevice *)(*((__int64 (__fastcall **)(PKDPC, struct WDFDEVICE__ *, void *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp
                        + 202))(
                         WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
                         v32,
                         off_140047040);
    v25 = v24 ? TpmDevice::TpmDevice(v24, v32) : 0LL;
    *(_QWORD *)&v38 = 0;
    v40 = off_140047018;
    v37 = 0;
    LODWORD(v37) = 56;
    v39 = 0;
    *((_QWORD *)&v38 + 1) = 0x100000001LL;
    HiddenDummyDevice = (*((__int64 (__fastcall **)(PKDPC, struct WDFDEVICE__ *, __int128 *, _QWORD))WPP_MAIN_CB.Queue.Wcb.CurrentIrp
                         + 203))(
                          WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
                          v32,
                          &v37,
                          0);
    if ( HiddenDummyDevice < 0 )
      goto LABEL_55;
    v26 = IsSoftBoot && v3 ? (struct _TPM_DEVICE_STATE *)v3 : 0LL;
    HiddenDummyDevice = TpmStack::CreateTpmStackInternal(v32, v26, v25, &v41);
    if ( HiddenDummyDevice < 0 )
      goto LABEL_55;
    v44 = 0;
    v42 = 0;
    LODWORD(v42) = 65576;
    v43 = 0;
    *((_QWORD *)&v42 + 1) = (*((__int64 (__fastcall **)(PKDPC, struct WDFDEVICE__ *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp
                             + 32))(
                              WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
                              v32);
    *(_QWORD *)&v43 = TpmTransportSpbI2CNTZDevice::CancelCurrentCommand;
    *((_QWORD *)&v43 + 1) = TpmTransportSpbI2CNTZDevice::CancelCurrentCommand;
    v44 = TpmSetMorBitState;
    *((_QWORD *)&v49 + 1) = &v42;
    *(_QWORD *)&v50 = &GUID_TPM_INTERFACE_STANDARD;
    *(_QWORD *)&v49 = 48;
    *((_QWORD *)&v50 + 1) = 0;
    v51 = 0u;
    HiddenDummyDevice = (*((__int64 (__fastcall **)(PKDPC, struct WDFDEVICE__ *, __int128 *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp
                         + 228))(
                          WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
                          v32,
                          &v49);
    if ( HiddenDummyDevice < 0 )
      goto LABEL_55;
    HiddenDummyDevice = (*((__int64 (__fastcall **)(PKDPC, struct WDFDEVICE__ *, GUID *, _QWORD))WPP_MAIN_CB.Queue.Wcb.CurrentIrp
                         + 77))(
                          WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
                          v32,
                          &GUID_DEVINTERFACE_TPM,
                          0);
    if ( HiddenDummyDevice < 0 )
      goto LABEL_55;
    LODWORD(PropertyBuffer[0]) = 34209792;
    PropertyBuffer[1] = TpmAlloc(1, 0x20Au, retaddr);
    if ( PropertyBuffer[1] )
    {
      v27 = (struct _DEVICE_OBJECT *)(*((__int64 (__fastcall **)(PKDPC, struct WDFDEVICE__ *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp
                                      + 33))(
                                       WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
                                       v32);
      HiddenDummyDevice = IoGetDeviceProperty(
                            v27,
                            DevicePropertyPhysicalDeviceObjectName,
                            WORD1(PropertyBuffer[0]),
                            PropertyBuffer[1],
                            &ResultLength);
      if ( HiddenDummyDevice < 0 )
        goto LABEL_55;
      LOWORD(PropertyBuffer[0]) = ResultLength - 2;
      RtlInitUnicodeString(&DestinationString, L"\\??\\TPM");
      HiddenDummyDevice = IoCreateSymbolicLink(&DestinationString, (PUNICODE_STRING)PropertyBuffer);
      if ( HiddenDummyDevice < 0 )
        goto LABEL_55;
      qword_140047DB8 = (__int64)v25;
      if ( !IsSoftBoot )
        TpmRegistry::CreateStandardKeys();
      Pool2 = (unsigned __int64 *)ExAllocatePool2(65, 48, 1349349460);
      v30 = Pool2;
      if ( Pool2 )
      {
        v30 = Pool2 + 2;
        *Pool2 = retaddr;
        Pool2[1] = retaddr;
      }
      if ( v30 )
      {
        *v30 = 0;
        v30[1] = 0;
        v30[2] = (unsigned __int64)L"\\BaseNamedObjects\\SC_AutoStartComplete";
        *((_DWORD *)v30 + 6) = 0;
        g_TpmTaskTrigger = (TpmTaskTrigger *)v30;
        if ( Event::Initialize((Event *)(v30 + 1), NotificationEvent, v29) >= 0 )
          Thread::Initialize((Thread *)v30, (void (*)(void *))TpmTaskTrigger::NotifyProvisioningRequired_Thread, v30);
      }
      else
      {
        g_TpmTaskTrigger = 0;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_55;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_6356bb85d3253aa80b2f75179e64f445_Traceguids);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_6356bb85d3253aa80b2f75179e64f445_Traceguids, v32);
      goto LABEL_55;
    }
    HiddenDummyDevice = -1073741670;
LABEL_55:
    if ( PropertyBuffer[1] )
      TpmFree(PropertyBuffer[1]);
    if ( v3 )
      TpmFree(v3);
    return (unsigned int)HiddenDummyDevice;
  }
  if ( (TPMEnableBits & 1) != 0 )
    McTemplateK0zq_EtwWriteTransfer(
      v19,
      (unsigned int)TPM_TPMAPI_ERROR,
      v20,
      (unsigned int)L"Setting TPM callbacks failed.",
      v18);
  return 3221225859LL;
}

```

## disassembly

```asm
0x140013da0  mov     [rsp-8+arg_10], rbx
0x140013da5  push    rbp
0x140013da6  push    rsi
0x140013da7  push    rdi
0x140013da8  push    r12
0x140013daa  push    r13
0x140013dac  push    r14
0x140013dae  push    r15
0x140013db0  lea     rbp, [rsp-200h]
0x140013db8  sub     rsp, 300h
0x140013dbf  mov     rax, cs:__security_cookie
0x140013dc6  xor     rax, rsp
0x140013dc9  mov     [rbp+230h+var_40], rax
0x140013dd0  xorps   xmm0, xmm0
0x140013dd3  mov     [rsp+330h+var_2E0], rdx
0x140013dd8  xor     eax, eax
0x140013dda  xorps   xmm1, xmm1
0x140013ddd  mov     rbx, rcx
0x140013de0  mov     [rbp+230h+var_288], rax
0x140013de4  xor     r15d, r15d
0x140013de7  mov     [rbp+230h+var_1C0], rax
0x140013deb  movups  [rbp+230h+var_B0], xmm0
0x140013df2  xor     edx, edx; Val
0x140013df4  mov     [rsp+330h+var_2E8], r15
0x140013df9  mov     r8d, 90h; Size
0x140013dff  mov     [rbp+230h+var_228], rax
0x140013e03  lea     rcx, [rbp+230h+var_140]; void *
0x140013e0a  mov     [rsp+330h+var_2F0], r15b
0x140013e0f  movups  [rbp+230h+var_B0+0Ch], xmm0
0x140013e16  movups  [rsp+330h+var_2B8], xmm0
0x140013e1b  movups  [rbp+230h+var_2A8], xmm0
0x140013e1f  movups  [rbp+230h+var_298], xmm0
0x140013e23  movups  [rbp+230h+var_1F0], xmm1
0x140013e27  movups  [rbp+230h+var_1E0], xmm1
0x140013e2b  movups  [rbp+230h+var_1D0], xmm1
0x140013e2f  movups  [rbp+230h+var_248], xmm0
0x140013e33  movups  [rbp+230h+var_238], xmm0
0x140013e37  call    memset
0x140013e3c  xor     edx, edx; Val
0x140013e3e  lea     r8d, [r15+50h]; Size
0x140013e42  lea     rcx, [rbp+230h+var_90]; void *
0x140013e49  call    memset
0x140013e4e  xorps   xmm0, xmm0
0x140013e51  mov     [rbp+230h+var_250], r15
0x140013e55  xor     edx, edx; Val
0x140013e57  lea     r8d, [r15+60h]; Size
0x140013e5b  lea     rcx, [rbp+230h+var_1A0]; void *
0x140013e62  movups  [rbp+230h+var_220], xmm0
0x140013e66  movups  [rbp+230h+var_210], xmm0
0x140013e6a  movups  [rbp+230h+var_200], xmm0
0x140013e6e  call    memset
0x140013e73  xorps   xmm0, xmm0
0x140013e76  mov     [rsp+330h+var_2D8], r15d
0x140013e7b  xorps   xmm1, xmm1
0x140013e7e  mov     [rbp+230h+var_280], r15
0x140013e82  xor     eax, eax
0x140013e84  mov     [rsp+330h+var_2C0], r15
0x140013e89  movups  xmmword ptr [rsp+330h+PropertyBuffer], xmm0
0x140013e8e  mov     [rbp+230h+var_258], rax
0x140013e92  mov     esi, r15d
0x140013e95  movups  xmmword ptr [rbp+230h+DestinationString.Length], xmm1
0x140013e99  movups  [rbp+230h+var_278], xmm0
0x140013e9d  movups  [rbp+230h+var_268], xmm0
0x140013ea1  call    cs:__imp_ExIsSoftBoot
0x140013ea8  nop     dword ptr [rax+rax+00h]
0x140013ead  mov     [rsp+330h+PropertyBuffer+8], r15
0x140013eb2  lea     r12d, [r15+2]
0x140013eb6  lea     r13d, [r15+1]
0x140013eba  mov     r14b, al
0x140013ebd  test    al, al
0x140013ebf  jz      loc_140014009
0x140013ec5  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140013ecc  mov     rdx, rbx
0x140013ecf  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140013ed6  mov     rax, [rax+3B0h]
0x140013edd  call    _guard_dispatch_icall
0x140013ee2  lea     r8, [rsp+330h+var_2C0]
0x140013ee7  xor     edx, edx
0x140013ee9  mov     rcx, rax
0x140013eec  call    cs:__imp_IoQueryKsrPersistentMemorySize
0x140013ef3  nop     dword ptr [rax+rax+00h]
0x140013ef8  test    cs:TPMEnableBits, r12b
0x140013eff  mov     edi, eax
0x140013f01  jz      short loc_140013F1A
0x140013f03  lea     r9, aDeviceaddIoque; "DeviceAdd: IoQueryKsrPersistentMemorySi"...
0x140013f0a  mov     dword ptr [rsp+330h+ResultLength], eax
0x140013f0e  lea     rdx, TPM_KSR_INFORMATION
0x140013f15  call    McTemplateK0zq_EtwWriteTransfer
0x140013f1a  test    edi, edi
0x140013f1c  js      loc_140013FE7
0x140013f22  mov     r8, [rbp+238h]; unsigned __int64
0x140013f29  mov     cl, r13b; bool
0x140013f2c  mov     rdx, [rsp+330h+var_2C0]; unsigned __int64
0x140013f31  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x140013f36  mov     rsi, rax
0x140013f39  test    rax, rax
0x140013f3c  jz      loc_140013FE7
0x140013f42  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140013f49  mov     rdx, rbx
0x140013f4c  mov     rax, [rcx+3B0h]
0x140013f53  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140013f5a  call    _guard_dispatch_icall
0x140013f5f  lea     r9, [rsp+330h+var_2C0]
0x140013f64  mov     r8, rsi
0x140013f67  xor     edx, edx
0x140013f69  mov     rcx, rax
0x140013f6c  call    cs:__imp_IoAcquireKsrPersistentMemory
0x140013f73  nop     dword ptr [rax+rax+00h]
0x140013f78  test    cs:TPMEnableBits, r12b
0x140013f7f  mov     edi, eax
0x140013f81  jz      short loc_140013F9A
0x140013f83  lea     r9, aDeviceaddIoacq; "DeviceAdd: IoAcquireKsrPersistentMemory"
0x140013f8a  mov     dword ptr [rsp+330h+ResultLength], eax
0x140013f8e  lea     rdx, TPM_KSR_INFORMATION
0x140013f95  call    McTemplateK0zq_EtwWriteTransfer
0x140013f9a  test    edi, edi
0x140013f9c  js      short loc_140013FDC
0x140013f9e  test    cs:TPMEnableBits, r12b
0x140013fa5  mov     eax, [rsi+4]
0x140013fa8  mov     cs:?m_Version@TpmTransportType@@0W4VERSION@1@A, eax; TpmTransportType::VERSION TpmTransportType::m_Version
0x140013fae  mov     eax, [rsi+8]
0x140013fb1  mov     dword ptr cs:WPP_MAIN_CB.DeviceExtension, eax
0x140013fb7  mov     eax, [rsi+0Ch]
0x140013fba  mov     cs:?m_TalkingToTpmSimulator@TpmTransportType@@0HA, eax; int TpmTransportType::m_TalkingToTpmSimulator
0x140013fc0  jz      short loc_140014009
0x140013fc2  lea     r9, aDeviceaddResto; "DeviceAdd: Restore TpmTransportType"
0x140013fc9  mov     dword ptr [rsp+330h+ResultLength], r15d
0x140013fce  lea     rdx, TPM_KSR_INFORMATION
0x140013fd5  call    McTemplateK0zq_EtwWriteTransfer
0x140013fda  jmp     short loc_140014009
0x140013fdc  mov     rcx, rsi; void *
0x140013fdf  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x140013fe4  mov     rsi, r15
0x140013fe7  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140013fee  mov     rdx, rbx
0x140013ff1  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140013ff8  mov     rax, [rax+3B0h]
0x140013fff  call    _guard_dispatch_icall
0x140014004  call    ?Determine@TpmTransportType@@SAJQEAU_DRIVER_OBJECT@@@Z; TpmTransportType::Determine(_DRIVER_OBJECT * const)
0x140014009  mov     rcx, [rsp+330h+var_2E0]; struct WDFDEVICE_INIT *
0x14001400e  call    ?IsDeviceMatch@TpmTransportType@@SAHPEAUWDFDEVICE_INIT@@@Z; TpmTransportType::IsDeviceMatch(WDFDEVICE_INIT *)
0x140014013  test    eax, eax
0x140014015  jnz     short loc_140014028
0x140014017  mov     rcx, [rsp+330h+var_2E0]
0x14001401c  call    TpmCreateHiddenDummyDevice
0x140014021  mov     ebx, eax
0x140014023  jmp     loc_1400147EC
0x140014028  cmp     cs:qword_140047DB8, r15
0x14001402f  jz      short loc_14001403B
0x140014031  mov     ebx, 0C0000182h
0x140014036  jmp     loc_1400147EC
0x14001403b  lea     rax, ?TpmApiPlatformW8TbsSubmit@@YAIPEAXQEAEIPEAEPEAI@Z; TpmApiPlatformW8TbsSubmit(void *,uchar * const,uint,uchar *,uint *)
0x140014042  mov     cs:?g_fpW8TpmSubmit@@3P6AIPEAXQEAEIPEAEPEAI@ZEA, rax; uint (*g_fpW8TpmSubmit)(void *,uchar * const,uint,uchar *,uint *)
0x140014049  lea     rax, ?TpmApiPlatformGetRandom@@YAJPEAEI@Z; TpmApiPlatformGetRandom(uchar *,uint)
0x140014050  mov     cs:?g_fpGetRandom@@3P6AJPEAEI@ZEA, rax; long (*g_fpGetRandom)(uchar *,uint)
0x140014057  lea     rax, ?TpmApiPlatformHash@@YAJPEAGPEAEI1I1IPEAIK@Z; TpmApiPlatformHash(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)
0x14001405e  mov     cs:?g_fpHash@@3P6AJPEAGPEAEI1I1IPEAIK@ZEA, rax; long (*g_fpHash)(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)
0x140014065  lea     rax, ?TpmApiPlatformAesCfbEncrypt@@YAJPEAEI0I0I0@Z; TpmApiPlatformAesCfbEncrypt(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x14001406c  mov     cs:?g_fpAesCfbEncrypt@@3P6AJPEAEI0I0I0@ZEA, rax; long (*g_fpAesCfbEncrypt)(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x140014073  lea     rax, ?TpmApiPlatformAesCfbDecrypt@@YAJPEAEI0I0I0@Z; TpmApiPlatformAesCfbDecrypt(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x14001407a  mov     cs:?g_fpAesCfbDecrypt@@3P6AJPEAEI0I0I0@ZEA, rax; long (*g_fpAesCfbDecrypt)(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x140014081  lea     rax, TpmDrvTpmApiAllocCallback
0x140014088  mov     cs:qword_1400480B8, rax
0x14001408f  lea     rax, TpmDrvTpmApiFreeCallback
0x140014096  mov     cs:qword_1400480B0, rax
0x14001409d  cmp     cs:?m_Version@TpmTransportType@@0W4VERSION@1@A, r12d; TpmTransportType::VERSION TpmTransportType::m_Version
0x1400140a4  mov     edx, r15d
0x1400140a7  setz    dl
0x1400140aa  add     edx, r13d
0x1400140ad  call    TpmApiSetTpmCallback
0x1400140b2  test    eax, eax
0x1400140b4  jns     short loc_1400140E0
0x1400140b6  test    cs:TPMEnableBits, r13b
0x1400140bd  jz      short loc_1400140D6
0x1400140bf  lea     r9, aSettingTpmCall; "Setting TPM callbacks failed."
0x1400140c6  mov     dword ptr [rsp+330h+ResultLength], eax
0x1400140ca  lea     rdx, TPM_TPMAPI_ERROR
0x1400140d1  call    McTemplateK0zq_EtwWriteTransfer
0x1400140d6  mov     eax, 0C0000183h
0x1400140db  jmp     loc_14001480A
0x1400140e0  xor     edx, edx; Val
0x1400140e2  lea     rcx, [rbp+230h+var_140]; void *
0x1400140e9  mov     r8d, 90h; Size
0x1400140ef  call    memset
0x1400140f4  mov     rdx, [rsp+330h+var_2E0]
0x1400140f9  lea     rax, TpmEvtDeviceD0Entry
0x140014100  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140014107  lea     r8, [rbp+230h+var_140]
0x14001410e  mov     [rbp+230h+var_138], rax
0x140014115  lea     rax, TpmEvtDeviceD0Exit
0x14001411c  mov     [rbp+230h+var_128], rax
0x140014123  lea     rax, TpmEvtDevicePrepareHardware
0x14001412a  mov     [rbp+230h+var_118], rax
0x140014131  lea     rax, TpmEvtDeviceReleaseHardware
0x140014138  mov     [rbp+230h+var_110], rax
0x14001413f  lea     rax, TpmEvtDeviceQueryStop
0x140014146  mov     [rbp+230h+var_D0], rax
0x14001414d  lea     rax, TpmEvtDeviceQueryStop
0x140014154  mov     [rbp+230h+var_D8], rax
0x14001415b  lea     rax, TpmEvtDeviceSelfManagedIoInit
0x140014162  mov     [rbp+230h+var_F8], rax
0x140014169  lea     rax, TpmEvtDeviceSelfManagedIoCleanup
0x140014170  mov     [rbp+230h+var_108], rax
0x140014177  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14001417e  mov     [rbp+230h+var_140], 90h
0x140014188  mov     rax, [rax+1B8h]
0x14001418f  call    _guard_dispatch_icall
0x140014194  mov     rax, cs:off_140047040
0x14001419b  lea     r9, [rbp+230h+var_1F0]
0x14001419f  mov     rdx, [rsp+330h+var_2E0]
0x1400141a4  lea     r8, [rbp+230h+var_248]
0x1400141a8  mov     [rbp+230h+var_288], rax
0x1400141ac  xorps   xmm0, xmm0
0x1400141af  movups  [rbp+230h+var_1E0], xmm0
0x1400141b3  mov     ecx, 38h ; '8'
0x1400141b8  mov     qword ptr [rsp+330h+var_2B8], 38h ; '8'
0x1400141c1  movups  [rbp+230h+var_1F0], xmm0
0x1400141c5  mov     dword ptr [rbp+230h+var_1F0], ecx
0x1400141c8  lea     rax, TpmEvtDeviceContextCleanup
0x1400141cf  mov     qword ptr [rbp+230h+var_2B8+8], rax
0x1400141d3  xor     eax, eax
0x1400141d5  mov     [rbp+230h+var_1C0], rax
0x1400141d9  mov     qword ptr [rbp+230h+var_2A8], r15
0x1400141dd  movdqu  [rbp+230h+var_298], xmm0
0x1400141e2  lea     ecx, [rax+4]
0x1400141e5  mov     dword ptr [rbp+230h+var_2A8+0Ch], r13d
0x1400141e9  mov     dword ptr [rbp+230h+var_1E0+0Ch], ecx
0x1400141ec  lea     rax, TpmEvtDeviceFileCreate
0x1400141f3  mov     qword ptr [rbp+230h+var_248+8], rax
0x1400141f7  lea     rax, TpmEvtFileClose
0x1400141fe  mov     qword ptr [rbp+230h+var_238], rax
0x140014202  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140014209  mov     dword ptr [rbp+230h+var_228+4], ecx
0x14001420c  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140014213  mov     dword ptr [rbp+230h+var_2A8+8], r12d
0x140014217  movups  [rbp+230h+var_1D0], xmm0
0x14001421b  mov     dword ptr [rbp+230h+var_1E0+8], r13d
0x14001421f  mov     dword ptr [rbp+230h+var_248], 28h ; '('
0x140014226  mov     qword ptr [rbp+230h+var_238+8], r15
0x14001422a  mov     dword ptr [rbp+230h+var_228], r12d
0x14001422e  mov     rax, [rax+238h]
0x140014235  call    _guard_dispatch_icall
0x14001423a  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140014241  lea     rcx, [rsp+330h+var_2F0]
0x140014246  mov     rdx, [rsp+330h+var_2E0]
0x14001424b  lea     r8, TpmEvtIrpPreprocessQueryDevRelations
0x140014252  mov     [rsp+330h+var_2F0], 7
0x140014257  mov     r9b, 1Bh
0x14001425a  mov     [rsp+330h+var_308], r13d
0x14001425f  mov     rax, [rax+248h]
0x140014266  mov     [rsp+330h+ResultLength], rcx
0x14001426b  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140014272  call    _guard_dispatch_icall
0x140014277  mov     ebx, eax
0x140014279  test    eax, eax
0x14001427b  js      loc_1400147EC
0x140014281  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140014288  lea     rcx, [rsp+330h+var_2F0]
0x14001428d  mov     rdx, [rsp+330h+var_2E0]
0x140014292  lea     r8, TpmEvtIrpPreprocessSetPower
0x140014299  mov     [rsp+330h+var_2F0], r12b
0x14001429e  mov     r9b, 16h
0x1400142a1  mov     [rsp+330h+var_308], r13d
0x1400142a6  mov     rax, [rax+248h]
0x1400142ad  mov     [rsp+330h+ResultLength], rcx
0x1400142b2  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x1400142b9  call    _guard_dispatch_icall
0x1400142be  mov     ebx, eax
0x1400142c0  test    eax, eax
0x1400142c2  js      loc_1400147EC
0x1400142c8  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x1400142cf  lea     r9, [rsp+330h+var_2E8]
0x1400142d4  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x1400142db  lea     r8, [rsp+330h+var_2B8]
0x1400142e0  lea     rdx, [rsp+330h+var_2E0]
0x1400142e5  mov     rax, [rax+258h]
0x1400142ec  call    _guard_dispatch_icall
0x1400142f1  mov     ebx, eax
0x1400142f3  test    eax, eax
0x1400142f5  js      loc_1400147EC
0x1400142fb  xor     edx, edx; Val
0x1400142fd  lea     rcx, [rbp+230h+var_1A0]; void *
0x140014304  lea     r8d, [rdx+60h]; Size
0x140014308  call    memset
0x14001430d  mov     rdx, [rsp+330h+var_2E8]
0x140014312  lea     rax, TpmEvtIoStop
0x140014319  mov     [rbp+230h+var_168], rax
0x140014320  lea     rcx, [rbp+230h+var_250]
0x140014324  lea     rax, TpmEvtIoDeviceControl
0x14001432b  mov     [rbp+230h+var_1A0], 60h ; '`'
0x140014335  mov     [rbp+230h+var_178], rax
0x14001433c  lea     r8, [rbp+230h+var_1A0]
0x140014343  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14001434a  or      edi, 0FFFFFFFFh
0x14001434d  mov     [rbp+230h+var_198], r12d
0x140014354  xor     r9d, r9d
0x140014357  mov     [rbp+230h+var_193], r13b
0x14001435e  mov     [rbp+230h+var_19C], r12d
0x140014365  mov     [rbp+230h+var_150], edi
0x14001436b  mov     rax, [rax+4C0h]
  ... truncated ...
```
