# HUBFDO_EvtDeviceAdd

- ea: `0x140078bd0`
- end: `0x140079938`
- name: `HUBFDO_EvtDeviceAdd`
- size: `3432`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x140001a54`
- `0x140001f94`
- `0x140002430`
- `0x1400024b8`
- `0x14000aa4c`
- `0x14000c578`
- `0x14000dcb8`
- `0x140010290`
- `0x1400336a8`
- `0x140045530`
- `0x140045570`
- `0x140045940`
- `0x140078bd0`
- `0x1400848ec`

## import_xrefs

- `ntoskrnl!KeResetEvent` at `0x14007981f`
- `ntoskrnl!KeResetEvent` at `0x14007981f`
- `ntoskrnl!IoRegisterShutdownNotification` at `0x140078fda`
- `ntoskrnl!IoRegisterShutdownNotification` at `0x140078fda`
- `ntoskrnl!PoDirectedDripsSetDeviceFlags` at `0x14007969e`
- `ntoskrnl!PoDirectedDripsSetDeviceFlags` at `0x14007969e`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x14007912a`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x14007912a`
- `USBD!USBD_AllocateHubNumber` at `0x14007909d`
- `USBD!USBD_AllocateHubNumber` at `0x14007909d`
- `USBD!USBD_ReleaseHubNumber` at `0x1400798b7`
- `USBD!USBD_ReleaseHubNumber` at `0x1400798b7`

## pseudocode

```c
__int64 __fastcall HUBFDO_EvtDeviceAdd(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  __int64 v3; // rcx
  __int64 v4; // rdi
  __int64 v5; // r9
  __int64 v6; // rcx
  int DeviceCapabilities; // ebx
  __int64 v8; // r9
  __int64 v9; // rax
  int v10; // edx
  int v11; // r9d
  struct _DEVICE_OBJECT *v12; // rax
  NTSTATUS v13; // eax
  char v14; // bl
  __int64 v15; // rax
  int v16; // edx
  _QWORD *v17; // r14
  __int64 v18; // r9
  __int64 v19; // r9
  __int64 v20; // r9
  __int64 v21; // r9
  __int64 v22; // rax
  int v23; // edx
  int v24; // r9d
  int v25; // r8d
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rax
  int IsEnabledDeviceUsageNoInline; // eax
  unsigned __int64 v30; // rdx
  PWDF_DRIVER_GLOBALS v31; // rcx
  bool v32; // zf
  __int64 v33; // r9
  int (__fastcall *v34)(PWDF_DRIVER_GLOBALS, unsigned __int64, GUID *, __int64, int, int); // rax
  int v35; // eax
  int v36; // edx
  int v37; // eax
  int v38; // edx
  __int64 v39; // r9
  __int64 v40; // rax
  int v41; // edx
  int v43; // [rsp+20h] [rbp-E0h]
  int v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+28h] [rbp-D8h]
  char v46; // [rsp+28h] [rbp-D8h]
  int v47; // [rsp+28h] [rbp-D8h]
  __int64 v48; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v49; // [rsp+40h] [rbp-C0h] BYREF
  char v50[8]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v51; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v52; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v53; // [rsp+68h] [rbp-98h]
  __int128 v54; // [rsp+78h] [rbp-88h]
  __int64 *v55; // [rsp+88h] [rbp-78h]
  __int128 v56; // [rsp+90h] [rbp-70h] BYREF
  __int128 v57; // [rsp+A0h] [rbp-60h]
  __int128 v58; // [rsp+B0h] [rbp-50h]
  __int64 *v59; // [rsp+C0h] [rbp-40h]
  __int128 v60; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v61; // [rsp+E0h] [rbp-20h]
  __m256i v62; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v63[12]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v64[18]; // [rsp+170h] [rbp+70h] BYREF
  __int128 v65; // [rsp+200h] [rbp+100h] BYREF
  __int128 v66; // [rsp+210h] [rbp+110h]
  char pszDest[16]; // [rsp+220h] [rbp+120h] BYREF
  __int64 v68; // [rsp+230h] [rbp+130h]
  _OWORD v69[2]; // [rsp+238h] [rbp+138h] BYREF
  __int128 v70; // [rsp+258h] [rbp+158h]
  GUID v71; // [rsp+268h] [rbp+168h] BYREF
  __int64 v72; // [rsp+278h] [rbp+178h]

  v51 = a2;
  v2 = a2;
  LODWORD(v55) = 0;
  v72 = 0;
  v49 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v71 = 0;
  memset(v64, 0, 0x8Cu);
  memset(v63, 0, sizeof(v63));
  v50[0] = 0;
  memset(&v62, 0, 28);
  LODWORD(v59) = 0;
  v68 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  memset(v69, 0, sizeof(v69));
  v70 = 0;
  v60 = 0;
  v61 = 0;
  v65 = 0;
  v66 = 0;
  *(_OWORD *)pszDest = 0;
  if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 2) != 0 )
  {
    McTemplateK0_EtwWriteTransfer(v3, USBHUB3_ETW_EVENT_HUB_ADD_DEVICE_START, 0);
    v2 = v51;
  }
  v55 = off_14006B270;
  *(_QWORD *)&v52 = 56;
  *((_QWORD *)&v52 + 1) = HUBFDO_EvtDeviceCleanupCallback;
  *((_QWORD *)&v53 + 1) = 0x100000001LL;
  *(_QWORD *)&v53 = HUBFDO_EvtDeviceDestroyCallback;
  v4 = 0;
  v54 = 0;
  memset(v64, 0, sizeof(v64));
  v64[1] = HUBFDO_EvtDeviceD0Entry;
  LODWORD(v64[0]) = 144;
  v64[3] = HUBFDO_EvtDeviceD0Exit;
  v64[5] = HUBFDO_EvtDevicePrepareHardware;
  v64[6] = HUBFDO_EvtDeviceReleaseHardware;
  v64[12] = HUBFDO_EvtDeviceSurpriseRemoval;
  v64[15] = HUBFDO_EvtDeviceUsageNotification;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *))(WdfFunctions_01015 + 440))(WdfDriverGlobals, v2, v64);
  LOBYTE(v5) = 16;
  DeviceCapabilities = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, void *, __int64, _QWORD, _DWORD))(WdfFunctions_01015 + 584))(
                         WdfDriverGlobals,
                         v51,
                         &HUBFDO_EvtDeviceShutdownPreprocess,
                         v5,
                         0,
                         0);
  if ( DeviceCapabilities < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_58;
    v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
           WdfDriverGlobals,
           WdfDriverGlobals->Driver,
           off_14006B2C0);
    v11 = 12;
    goto LABEL_6;
  }
  v50[0] = 7;
  LOBYTE(v8) = 27;
  DeviceCapabilities = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 (__fastcall *)(), __int64, char *, int))(WdfFunctions_01015 + 584))(
                         WdfDriverGlobals,
                         v51,
                         TUNNEL_EvtIrpPreprocessQueryDevRelations,
                         v8,
                         v50,
                         1);
  if ( DeviceCapabilities < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
             WdfDriverGlobals,
             WdfDriverGlobals->Driver,
             off_14006B2C0);
      v11 = 13;
LABEL_6:
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(v9 + 64),
        v10,
        2,
        v11,
        (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids,
        DeviceCapabilities);
      goto LABEL_58;
    }
    goto LABEL_58;
  }
  *((_QWORD *)&v60 + 1) = HUBFDO_EvtDeviceArmWakeFromS0;
  *(_QWORD *)&v60 = 64;
  *(_QWORD *)&v61 = HUBFDO_EvtDeviceDisarmWakeFromS0;
  v62.m256i_i64[0] = (__int64)HUBFDO_EvtDeviceArmWakeFromSx;
  v62.m256i_i64[1] = (__int64)HUBFDO_EvtDeviceDisarmWakeFromSx;
  *((_QWORD *)&v61 + 1) = 0;
  *(_OWORD *)&v62.m256i_u64[2] = 0;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *))(WdfFunctions_01015 + 448))(
    WdfDriverGlobals,
    v51,
    &v60);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 3440))(WdfDriverGlobals, v51, 2);
  DeviceCapabilities = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64 *, __int128 *, unsigned __int64 *))(WdfFunctions_01015 + 600))(
                         WdfDriverGlobals,
                         &v51,
                         &v52,
                         &v49);
  if ( DeviceCapabilities >= 0 )
  {
    v12 = (struct _DEVICE_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64))(WdfFunctions_01015 + 248))(
                                     WdfDriverGlobals,
                                     v49);
    v13 = IoRegisterShutdownNotification(v12);
    v14 = v13;
    if ( v13 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v15 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
              WdfDriverGlobals,
              WdfDriverGlobals->Driver,
              off_14006B2C0);
      LOBYTE(v16) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(v15 + 64),
        v16,
        2,
        15,
        (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids,
        v14);
    }
    v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, __int64 *))(WdfFunctions_01015 + 1616))(
           WdfDriverGlobals,
           v49,
           off_14006B270);
    *(_QWORD *)(v4 + 16) = v49;
    *(_QWORD *)(v4 + 24) = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64))(WdfFunctions_01015 + 264))(
                             WdfDriverGlobals,
                             v49);
    *(_QWORD *)v4 = g_Usbhub3_Triage_Info;
    *(_DWORD *)(v4 + 96) = USBD_AllocateHubNumber();
    *(_QWORD *)&v65 = 56;
    HIDWORD(v66) = 16;
    pszDest[0] = 0;
    v68 = 0x200000002LL;
    *(_QWORD *)&v66 = v4;
    BYTE8(v66) = 1;
    *((_QWORD *)&v65 + 1) = 0x20000000400LL;
    RtlStringCchPrintfA(pszDest, 0x10u, "hub%d", *(_DWORD *)(v4 + 96));
    v17 = (_QWORD *)(v4 + 2536);
    if ( (int)imp_WppRecorderLogCreate(WPP_GLOBAL_Control, &v65, v4 + 2536) < 0 )
      *v17 = *(_QWORD *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015
                                                                                                  + 1616))(
                           WdfDriverGlobals,
                           WdfDriverGlobals->Driver,
                           off_14006B2C0)
                       + 64);
    LOBYTE(v18) = 1;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, __int64, __int64))(WdfFunctions_01015 + 392))(
      WdfDriverGlobals,
      v49,
      1,
      v18);
    LOBYTE(v19) = 1;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, __int64, __int64))(WdfFunctions_01015 + 392))(
      WdfDriverGlobals,
      v49,
      2,
      v19);
    LOBYTE(v20) = 1;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, __int64, __int64))(WdfFunctions_01015 + 392))(
      WdfDriverGlobals,
      v49,
      3,
      v20);
    LOBYTE(v21) = 1;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, __int64, __int64))(WdfFunctions_01015 + 392))(
      WdfDriverGlobals,
      v49,
      4,
      v21);
    DeviceCapabilities = HUBFDO_GetDeviceCapabilities(v49, v4 + 712, *v17);
    if ( DeviceCapabilities < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_58;
      v22 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
              WdfDriverGlobals,
              WdfDriverGlobals->Driver,
              off_14006B2C0);
      v24 = 16;
      v46 = DeviceCapabilities;
      v25 = 2;
      v26 = *(_QWORD *)(v22 + 64);
      goto LABEL_21;
    }
    *((_QWORD *)&v70 + 1) = -1;
    LODWORD(v69[0]) = 48;
    *(__m128i *)((char *)v69 + 4) = _mm_load_si128((const __m128i *)&_xmm);
    *(_QWORD *)((char *)&v69[1] + 4) = 0x200000002LL;
    *(_QWORD *)&v70 = 0x200000002LL;
    HIDWORD(v69[1]) = 1;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, _OWORD *))(WdfFunctions_01015 + 664))(
      WdfDriverGlobals,
      v49,
      v69);
    *(_QWORD *)(v4 + 344) = v4;
    LOWORD(v45) = 1013;
    LOWORD(v43) = 144;
    v27 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, GUID *, __int64, int, int, _QWORD))(WdfFunctions_01015 + 1048))(
            WdfDriverGlobals,
            v49,
            &GUID_HUB_PARENT_INTERFACE,
            v4 + 208,
            v43,
            v45,
            0);
    DeviceCapabilities = v27;
    if ( v27 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_58;
      v24 = 17;
LABEL_25:
      v46 = v27;
LABEL_26:
      v26 = *v17;
      v25 = 3;
LABEL_21:
      LOBYTE(v23) = 2;
      WPP_RECORDER_SF_d(v26, v23, v25, v24, (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids, v46);
      goto LABEL_58;
    }
    if ( !*(_BYTE *)(v4 + 240) )
    {
      v28 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64))(WdfFunctions_01015 + 336))(
              WdfDriverGlobals,
              v49);
      *(_QWORD *)(v4 + 2464) = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1424))(
                                 WdfDriverGlobals,
                                 v28);
      *(_QWORD *)(v4 + 32) = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64))(WdfFunctions_01015 + 336))(
                               WdfDriverGlobals,
                               v49);
      *(_DWORD *)(v4 + 92) = 500;
    }
    *(_QWORD *)(v4 + 384) = *(_QWORD *)(v4 + 248);
    *(_QWORD *)(v4 + 400) = HUBHTX_ClearTTBuffer;
    *(_QWORD *)(v4 + 544) = HUBPDO_NoPingResponse;
    *(_QWORD *)(v4 + 392) = v4;
    IsEnabledDeviceUsageNoInline = Feature_EUSB2__private_IsEnabledDeviceUsageNoInline();
    v30 = v49;
    v31 = WdfDriverGlobals;
    v32 = IsEnabledDeviceUsageNoInline == 0;
    v33 = v4 + 352;
    v34 = *(int (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, GUID *, __int64, int, int))(WdfFunctions_01015
                                                                                                 + 1048);
    if ( !v32 )
    {
      LOWORD(v47) = 3000;
      LOWORD(v44) = 264;
      if ( ((int (__fastcall *)(PWDF_DRIVER_GLOBALS, unsigned __int64, GUID *, __int64, int, int, _QWORD))v34)(
             WdfDriverGlobals,
             v49,
             &GUID_HUB_CONTROLLERSTACK_INTERFACE,
             v33,
             v44,
             v47,
             0) >= 0 )
        goto LABEL_37;
      v33 = v4 + 352;
      v30 = v49;
      v31 = WdfDriverGlobals;
      v34 = *(int (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, GUID *, __int64, int, int))(WdfFunctions_01015 + 1048);
    }
    LOWORD(v47) = 2000;
    LOWORD(v44) = 264;
    if ( v34(v31, v30, &GUID_HUB_CONTROLLERSTACK_INTERFACE, v33, v44, v47) < 0 )
    {
      LOWORD(v47) = 1000;
      LOWORD(v44) = 264;
      DeviceCapabilities = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, GUID *, __int64, int, int, _QWORD))(WdfFunctions_01015 + 1048))(
                             WdfDriverGlobals,
                             v49,
                             &GUID_HUB_CONTROLLERSTACK_INTERFACE,
                             v4 + 352,
                             v44,
                             v47,
                             0);
      if ( DeviceCapabilities < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_58;
        v24 = 18;
        goto LABEL_36;
      }
    }
LABEL_37:
    if ( *(_BYTE *)(v4 + 240) )
      v48 = 0;
    else
      v48 = *(_QWORD *)(v4 + 248);
    LOWORD(v47) = 3;
    LOWORD(v44) = 96;
    DeviceCapabilities = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, const GUID *, __int64, int, int, __int64))(WdfFunctions_01015 + 1048))(
                           WdfDriverGlobals,
                           v49,
                           &USB_BUS_INTERFACE_USBDI_GUID,
                           v4 + 616,
                           v44,
                           v47,
                           v48);
    if ( DeviceCapabilities >= 0 )
    {
      memset(v63, 0, sizeof(v63));
      v63[5] = HUBFDO_EvtIoDeviceControl;
      LODWORD(v63[0]) = 96;
      BYTE5(v63[1]) = 1;
      *(_QWORD *)&v57 = 0;
      *(_QWORD *)((char *)v63 + 4) = 1;
      v63[6] = HUBFDO_EvtIoInternalDeviceControlFromPDO;
      v59 = off_14006B0A8;
      v56 = 0;
      LODWORD(v56) = 56;
      v58 = 0;
      *((_QWORD *)&v57 + 1) = 0x100000002LL;
      v27 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, _QWORD *, __int128 *, __int64))(WdfFunctions_01015 + 1216))(
              WdfDriverGlobals,
              v49,
              v63,
              &v56,
              v4 + 2416);
      DeviceCapabilities = v27;
      if ( v27 >= 0 )
      {
        v71 = GUID_BUS_TYPE_USB;
        v72 = 15;
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, GUID *))(WdfFunctions_01015 + 680))(
          WdfDriverGlobals,
          v49,
          &v71);
        HSMMUX_InitializeHSMMuxContext(v4);
        DeviceCapabilities = HUBMISC_InitializeHsm(v4);
        if ( DeviceCapabilities < 0 )
          goto LABEL_58;
        v35 = PoDirectedDripsSetDeviceFlags(*(_QWORD *)(v4 + 24), 2);
        if ( v35 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v36) = 2;
          WPP_RECORDER_SF_d(*v17, v36, 3, 21, (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids, v35);
        }
        v55 = 0;
        *(_QWORD *)&v53 = 0;
        *((_QWORD *)&v53 + 1) = 0x100000001LL;
        v54 = v49;
        v52 = 0;
        LODWORD(v52) = 56;
        v27 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int64))(WdfFunctions_01015 + 104))(
                WdfDriverGlobals,
                &v52,
                v4 + 2752);
        DeviceCapabilities = v27;
        if ( v27 >= 0 )
        {
          v55 = 0;
          *(_QWORD *)&v53 = 0;
          *((_QWORD *)&v53 + 1) = 0x100000001LL;
          v54 = v49;
          v52 = 0;
          LODWORD(v52) = 56;
          v37 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int64))(WdfFunctions_01015 + 2496))(
                  WdfDriverGlobals,
                  &v52,
                  v4 + 2760);
          DeviceCapabilities = v37;
          if ( v37 >= 0 )
          {
            _InterlockedOr((volatile signed __int32 *)(v4 + 40), 0x20u);
            KeResetEvent((PRKEVENT)(v4 + 1168));
            HUBSM_AddHsmEvent(v4, 2023);
            (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, v4);
            HUBMISC_WaitForSignal((PVOID)(v4 + 1168));
            DeviceCapabilities = *(_DWORD *)(v4 + 1192);
          }
          else
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v38) = 2;
              WPP_RECORDER_SF_d(*v17, v38, 3, 23, (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids, v37);
            }
            (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1664))(
              WdfDriverGlobals,
              *(_QWORD *)(v4 + 2752));
          }
          goto LABEL_58;
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_58;
        v24 = 22;
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_58;
        v24 = 20;
      }
      goto LABEL_25;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_58;
    v24 = 19;
LABEL_36:
    v46 = DeviceCapabilities;
    goto LABEL_26;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
           WdfDriverGlobals,
           WdfDriverGlobals->Driver,
           off_14006B2C0);
    v11 = 14;
    goto LABEL_6;
  }
LABEL_58:
  if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 2) != 0 )
  {
    if ( v4 )
      v39 = *(_QWORD *)(v4 + 248);
    else
      v39 = 0;
    McTemplateK0pq_EtwWriteTransfer(v6, USBHUB3_ETW_EVENT_HUB_ADD_DEVICE_COMPLETE, 0, v39, DeviceCapabilities);
  }
  if ( DeviceCapabilities < 0 )
  {
    if ( v4 && *(_DWORD *)(v4 + 96) )
    {
      USBD_ReleaseHubNumber();
      *(_DWORD *)(v4 + 96) = 0;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v40 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
              WdfDriverGlobals,
              WdfDriverGlobals->Driver,
              off_14006B2C0);
      LOBYTE(v41) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(v40 + 64),
        v41,
        3,
        24,
        (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids,
        DeviceCapabilities);
    }
  }
  return (unsigned int)DeviceCapabilities;
}

```

## disassembly

```asm
0x140078bd0  push    rbp
0x140078bd2  push    rbx
0x140078bd3  push    rsi
0x140078bd4  push    rdi
0x140078bd5  push    r12
0x140078bd7  push    r13
0x140078bd9  push    r14
0x140078bdb  push    r15
0x140078bdd  lea     rbp, [rsp-198h]
0x140078be5  sub     rsp, 298h
0x140078bec  mov     rax, cs:__security_cookie
0x140078bf3  xor     rax, rsp
0x140078bf6  mov     [rbp+1D0h+var_50], rax
0x140078bfd  xorps   xmm0, xmm0
0x140078c00  mov     [rsp+2D0h+var_280], rdx
0x140078c05  xor     eax, eax
0x140078c07  lea     rcx, [rbp+1D0h+var_160]; void *
0x140078c0b  mov     rbx, rdx
0x140078c0e  mov     dword ptr [rbp+1D0h+var_248], eax
0x140078c11  xor     r13d, r13d
0x140078c14  mov     [rbp+1D0h+var_58], rax
0x140078c1b  xor     edx, edx; Val
0x140078c1d  mov     [rsp+2D0h+var_290], r13
0x140078c22  mov     r8d, 8Ch; Size
0x140078c28  mov     [rbp+1D0h+var_15C], eax
0x140078c2b  movups  [rsp+2D0h+var_278], xmm0
0x140078c30  movups  [rsp+2D0h+var_268], xmm0
0x140078c35  movups  [rsp+2D0h+var_258], xmm0
0x140078c3a  movups  [rbp+1D0h+var_68], xmm0
0x140078c41  call    memset
0x140078c46  xor     edx, edx; Val
0x140078c48  lea     r8d, [r13+60h]; Size
0x140078c4c  lea     rcx, [rbp+1D0h+var_1C0]; void *
0x140078c50  call    memset
0x140078c55  xorps   xmm0, xmm0
0x140078c58  mov     [rsp+2D0h+var_288], r13b
0x140078c5d  xor     eax, eax
0x140078c5f  lea     r12d, [r13+2]
0x140078c63  test    cs:Microsoft_Windows_USB_USBHUB3EnableBits, r12b
0x140078c6a  movups  [rbp+1D0h+var_1E0], xmm0
0x140078c6e  mov     dword ptr [rbp+1D0h+var_210], eax
0x140078c71  movups  [rbp+1D0h+var_1E0+0Ch], xmm0
0x140078c75  mov     [rbp+1D0h+var_A0], rax
0x140078c7c  movups  [rbp+1D0h+var_240], xmm0
0x140078c80  movups  [rbp+1D0h+var_230], xmm0
0x140078c84  movups  [rbp+1D0h+var_220], xmm0
0x140078c88  movups  [rbp+1D0h+var_98], xmm0
0x140078c8f  movups  [rbp+1D0h+var_88], xmm0
0x140078c96  movups  [rbp+1D0h+var_78], xmm0
0x140078c9d  movups  [rbp+1D0h+var_200], xmm0
0x140078ca1  movups  [rbp+1D0h+var_1F0], xmm0
0x140078ca5  movups  [rbp+1D0h+var_D0], xmm0
0x140078cac  movups  [rbp+1D0h+var_C0], xmm0
0x140078cb3  movups  xmmword ptr [rbp+1D0h+pszDest], xmm0
0x140078cba  jz      short loc_140078CD0
0x140078cbc  xor     r8d, r8d
0x140078cbf  lea     rdx, USBHUB3_ETW_EVENT_HUB_ADD_DEVICE_START
0x140078cc6  call    McTemplateK0_EtwWriteTransfer
0x140078ccb  mov     rbx, [rsp+2D0h+var_280]
0x140078cd0  mov     rax, cs:off_14006B270
0x140078cd7  lea     rcx, [rbp+1D0h+var_160]; void *
0x140078cdb  mov     [rbp+1D0h+var_248], rax
0x140078cdf  xorps   xmm0, xmm0
0x140078ce2  lea     rax, HUBFDO_EvtDeviceCleanupCallback
0x140078ce9  mov     qword ptr [rsp+2D0h+var_278], 38h ; '8'
0x140078cf2  mov     qword ptr [rsp+2D0h+var_278+8], rax
0x140078cf7  mov     esi, 1
0x140078cfc  lea     rax, HUBFDO_EvtDeviceDestroyCallback
0x140078d03  mov     dword ptr [rsp+2D0h+var_268+8], esi
0x140078d07  mov     r14d, 90h
0x140078d0d  mov     qword ptr [rsp+2D0h+var_268], rax
0x140078d12  mov     r8d, r14d; Size
0x140078d15  mov     dword ptr [rsp+2D0h+var_268+0Ch], esi
0x140078d19  xor     edx, edx; Val
0x140078d1b  mov     rdi, r13
0x140078d1e  movdqu  [rsp+2D0h+var_258], xmm0
0x140078d24  call    memset
0x140078d29  mov     rcx, cs:WdfDriverGlobals
0x140078d30  lea     rax, HUBFDO_EvtDeviceD0Entry
0x140078d37  mov     [rbp+1D0h+var_158], rax
0x140078d3b  lea     r8, [rbp+1D0h+var_160]
0x140078d3f  lea     rax, HUBFDO_EvtDeviceD0Exit
0x140078d46  mov     [rbp+1D0h+var_160], r14d
0x140078d4a  mov     [rbp+1D0h+var_148], rax
0x140078d51  mov     rdx, rbx
0x140078d54  lea     rax, HUBFDO_EvtDevicePrepareHardware
0x140078d5b  mov     [rbp+1D0h+var_138], rax
0x140078d62  lea     rax, HUBFDO_EvtDeviceReleaseHardware
0x140078d69  mov     [rbp+1D0h+var_130], rax
0x140078d70  lea     rax, HUBFDO_EvtDeviceSurpriseRemoval
0x140078d77  mov     [rbp+1D0h+var_100], rax
0x140078d7e  lea     rax, HUBFDO_EvtDeviceUsageNotification
0x140078d85  mov     [rbp+1D0h+var_E8], rax
0x140078d8c  mov     rax, cs:WdfFunctions_01015
0x140078d93  mov     rax, [rax+1B8h]
0x140078d9a  call    _guard_dispatch_icall
0x140078d9f  mov     rax, cs:WdfFunctions_01015
0x140078da6  lea     r8, HUBFDO_EvtDeviceShutdownPreprocess
0x140078dad  mov     rdx, [rsp+2D0h+var_280]
0x140078db2  mov     r9b, 10h
0x140078db5  mov     rcx, cs:WdfDriverGlobals
0x140078dbc  mov     dword ptr [rsp+2D0h+var_2A8], r13d
0x140078dc1  mov     rax, [rax+248h]
0x140078dc8  mov     [rsp+2D0h+var_2B0], r13
0x140078dcd  call    _guard_dispatch_icall
0x140078dd2  lea     r14d, [rsi+2]
0x140078dd6  mov     ebx, eax
0x140078dd8  lea     r15, WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids
0x140078ddf  test    eax, eax
0x140078de1  jns     short loc_140078E3C
0x140078de3  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140078dea  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140078df1  jz      loc_14007987A
0x140078df7  mov     rax, cs:WdfFunctions_01015
0x140078dfe  mov     rcx, cs:WdfDriverGlobals
0x140078e05  mov     r8, cs:off_14006B2C0
0x140078e0c  mov     rax, [rax+650h]
0x140078e13  mov     rdx, [rcx]
0x140078e16  call    _guard_dispatch_icall
0x140078e1b  lea     r9d, [r14+9]
0x140078e1f  mov     rcx, [rax+40h]
0x140078e23  mov     r8d, r12d
0x140078e26  mov     dword ptr [rsp+2D0h+var_2A8], ebx
0x140078e2a  mov     dl, r12b
0x140078e2d  mov     [rsp+2D0h+var_2B0], r15
0x140078e32  call    WPP_RECORDER_SF_d
0x140078e37  jmp     loc_14007987A
0x140078e3c  mov     rax, cs:WdfFunctions_01015
0x140078e43  lea     rcx, [rsp+2D0h+var_288]
0x140078e48  mov     rdx, [rsp+2D0h+var_280]
0x140078e4d  lea     r8, TUNNEL_EvtIrpPreprocessQueryDevRelations
0x140078e54  mov     [rsp+2D0h+var_288], 7
0x140078e59  mov     r9b, 1Bh
0x140078e5c  mov     dword ptr [rsp+2D0h+var_2A8], esi
0x140078e60  mov     rax, [rax+248h]
0x140078e67  mov     [rsp+2D0h+var_2B0], rcx
0x140078e6c  mov     rcx, cs:WdfDriverGlobals
0x140078e73  call    _guard_dispatch_icall
0x140078e78  mov     ebx, eax
0x140078e7a  test    eax, eax
0x140078e7c  jns     short loc_140078EC1
0x140078e7e  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140078e85  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140078e8c  jz      loc_14007987A
0x140078e92  mov     rax, cs:WdfFunctions_01015
0x140078e99  mov     rcx, cs:WdfDriverGlobals
0x140078ea0  mov     r8, cs:off_14006B2C0
0x140078ea7  mov     rax, [rax+650h]
0x140078eae  mov     rdx, [rcx]
0x140078eb1  call    _guard_dispatch_icall
0x140078eb6  mov     r9d, 0Dh
0x140078ebc  jmp     loc_140078E1F
0x140078ec1  mov     rdx, [rsp+2D0h+var_280]
0x140078ec6  lea     rax, HUBFDO_EvtDeviceArmWakeFromS0
0x140078ecd  mov     rcx, cs:WdfDriverGlobals
0x140078ed4  lea     r8, [rbp+1D0h+var_200]
0x140078ed8  mov     qword ptr [rbp+1D0h+var_200+8], rax
0x140078edc  xorps   xmm0, xmm0
0x140078edf  lea     rax, HUBFDO_EvtDeviceDisarmWakeFromS0
0x140078ee6  mov     qword ptr [rbp+1D0h+var_200], 40h ; '@'
0x140078eee  mov     qword ptr [rbp+1D0h+var_1F0], rax
0x140078ef2  lea     rax, HUBFDO_EvtDeviceArmWakeFromSx
0x140078ef9  mov     qword ptr [rbp+1D0h+var_1E0], rax
0x140078efd  lea     rax, HUBFDO_EvtDeviceDisarmWakeFromSx
0x140078f04  mov     qword ptr [rbp+1D0h+var_1E0+8], rax
0x140078f08  mov     rax, cs:WdfFunctions_01015
0x140078f0f  mov     qword ptr [rbp+1D0h+var_1F0+8], r13
0x140078f13  movdqa  [rbp+1D0h+var_1D0], xmm0
0x140078f18  mov     rax, [rax+1C0h]
0x140078f1f  call    _guard_dispatch_icall
0x140078f24  mov     rax, cs:WdfFunctions_01015
0x140078f2b  mov     r8d, r12d
0x140078f2e  mov     rdx, [rsp+2D0h+var_280]
0x140078f33  mov     rcx, cs:WdfDriverGlobals
0x140078f3a  mov     rax, [rax+0D70h]
0x140078f41  call    _guard_dispatch_icall
0x140078f46  mov     rax, cs:WdfFunctions_01015
0x140078f4d  lea     r9, [rsp+2D0h+var_290]
0x140078f52  mov     rcx, cs:WdfDriverGlobals
0x140078f59  lea     r8, [rsp+2D0h+var_278]
0x140078f5e  lea     rdx, [rsp+2D0h+var_280]
0x140078f63  mov     rax, [rax+258h]
0x140078f6a  call    _guard_dispatch_icall
0x140078f6f  mov     ebx, eax
0x140078f71  test    eax, eax
0x140078f73  jns     short loc_140078FB8
0x140078f75  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140078f7c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140078f83  jz      loc_14007987A
0x140078f89  mov     rax, cs:WdfFunctions_01015
0x140078f90  mov     rcx, cs:WdfDriverGlobals
0x140078f97  mov     r8, cs:off_14006B2C0
0x140078f9e  mov     rax, [rax+650h]
0x140078fa5  mov     rdx, [rcx]
0x140078fa8  call    _guard_dispatch_icall
0x140078fad  mov     r9d, 0Eh
0x140078fb3  jmp     loc_140078E1F
0x140078fb8  mov     rax, cs:WdfFunctions_01015
0x140078fbf  mov     rdx, [rsp+2D0h+var_290]
0x140078fc4  mov     rcx, cs:WdfDriverGlobals
0x140078fcb  mov     rax, [rax+0F8h]
0x140078fd2  call    _guard_dispatch_icall
0x140078fd7  mov     rcx, rax; DeviceObject
0x140078fda  call    cs:__imp_IoRegisterShutdownNotification
0x140078fe1  nop     dword ptr [rax+rax+00h]
0x140078fe6  lea     rsi, WPP_RECORDER_INITIALIZED
0x140078fed  mov     ebx, eax
0x140078fef  test    eax, eax
0x140078ff1  jns     short loc_14007903E
0x140078ff3  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140078ffa  jz      short loc_14007903E
0x140078ffc  mov     rax, cs:WdfFunctions_01015
0x140079003  mov     rcx, cs:WdfDriverGlobals
0x14007900a  mov     r8, cs:off_14006B2C0
0x140079011  mov     rax, [rax+650h]
0x140079018  mov     rdx, [rcx]
0x14007901b  call    _guard_dispatch_icall
0x140079020  mov     r9d, 0Fh
0x140079026  mov     dword ptr [rsp+2D0h+var_2A8], ebx
0x14007902a  mov     r8d, r12d
0x14007902d  mov     [rsp+2D0h+var_2B0], r15
0x140079032  mov     dl, r12b
0x140079035  mov     rcx, [rax+40h]
0x140079039  call    WPP_RECORDER_SF_d
0x14007903e  mov     rax, cs:WdfFunctions_01015
0x140079045  mov     r8, cs:off_14006B270
0x14007904c  mov     rdx, [rsp+2D0h+var_290]
0x140079051  mov     rcx, cs:WdfDriverGlobals
0x140079058  mov     rax, [rax+650h]
0x14007905f  call    _guard_dispatch_icall
0x140079064  mov     rcx, [rsp+2D0h+var_290]
0x140079069  mov     rdi, rax
0x14007906c  mov     [rax+10h], rcx
0x140079070  mov     rcx, cs:WdfFunctions_01015
0x140079077  mov     rdx, [rsp+2D0h+var_290]
0x14007907c  mov     rax, [rcx+108h]
0x140079083  mov     rcx, cs:WdfDriverGlobals
0x14007908a  call    _guard_dispatch_icall
0x14007908f  mov     [rdi+18h], rax
0x140079093  lea     rax, g_Usbhub3_Triage_Info
0x14007909a  mov     [rdi], rax
0x14007909d  call    cs:__imp_USBD_AllocateHubNumber
0x1400790a4  nop     dword ptr [rax+rax+00h]
0x1400790a9  mov     [rdi+60h], eax
0x1400790ac  lea     r8, aHubD; "hub%d"
0x1400790b3  mov     eax, 10h
0x1400790b8  mov     qword ptr [rbp+1D0h+var_D0], 38h ; '8'
0x1400790c3  mov     dword ptr [rbp+1D0h+var_C0+0Ch], eax
0x1400790c9  lea     rcx, [rbp+1D0h+pszDest]; pszDest
0x1400790d0  mov     [rbp+1D0h+pszDest], r13b
0x1400790d7  mov     edx, eax; cchDest
0x1400790d9  mov     dword ptr [rbp+1D0h+var_A0], r12d
0x1400790e0  mov     dword ptr [rbp+1D0h+var_A0+4], r12d
0x1400790e7  mov     qword ptr [rbp+1D0h+var_C0], rdi
0x1400790ee  mov     byte ptr [rbp+1D0h+var_C0+8], 1
0x1400790f5  mov     dword ptr [rbp+1D0h+var_D0+8], 400h
0x1400790ff  mov     dword ptr [rbp+1D0h+var_D0+0Ch], 200h
0x140079109  mov     r9d, [rdi+60h]
0x14007910d  call    RtlStringCchPrintfA
0x140079112  mov     rcx, cs:WPP_GLOBAL_Control
0x140079119  lea     r14, [rdi+9E8h]
0x140079120  mov     r8, r14
0x140079123  lea     rdx, [rbp+1D0h+var_D0]
0x14007912a  call    cs:__imp_imp_WppRecorderLogCreate
0x140079131  nop     dword ptr [rax+rax+00h]
0x140079136  test    eax, eax
0x140079138  jns     short loc_140079165
0x14007913a  mov     rax, cs:WdfFunctions_01015
0x140079141  mov     rcx, cs:WdfDriverGlobals
0x140079148  mov     r8, cs:off_14006B2C0
0x14007914f  mov     rax, [rax+650h]
0x140079156  mov     rdx, [rcx]
0x140079159  call    _guard_dispatch_icall
0x14007915e  mov     rcx, [rax+40h]
0x140079162  mov     [r14], rcx
0x140079165  mov     rax, cs:WdfFunctions_01015
0x14007916c  mov     r9b, 1
0x14007916f  mov     rdx, [rsp+2D0h+var_290]
0x140079174  mov     r8d, 1
0x14007917a  mov     rcx, cs:WdfDriverGlobals
0x140079181  mov     rax, [rax+188h]
0x140079188  call    _guard_dispatch_icall
0x14007918d  mov     rax, cs:WdfFunctions_01015
0x140079194  mov     r9b, 1
0x140079197  mov     rdx, [rsp+2D0h+var_290]
0x14007919c  mov     r8d, r12d
0x14007919f  mov     rcx, cs:WdfDriverGlobals
0x1400791a6  mov     rax, [rax+188h]
0x1400791ad  call    _guard_dispatch_icall
0x1400791b2  mov     rax, cs:WdfFunctions_01015
0x1400791b9  mov     r9b, 1
0x1400791bc  mov     rdx, [rsp+2D0h+var_290]
0x1400791c1  mov     r8d, 3
0x1400791c7  mov     rcx, cs:WdfDriverGlobals
0x1400791ce  mov     rax, [rax+188h]
0x1400791d5  call    _guard_dispatch_icall
0x1400791da  mov     rax, cs:WdfFunctions_01015
0x1400791e1  mov     r9b, 1
0x1400791e4  mov     rdx, [rsp+2D0h+var_290]
0x1400791e9  mov     r8d, 4
  ... truncated ...
```
