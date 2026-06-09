# HUBPDO_CreatePdoInternal

- ea: `0x14007f118`
- end: `0x14008040d`
- name: `HUBPDO_CreatePdoInternal`
- size: `4853`
- prototype: `__int64 __fastcall(_QWORD *, char)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14007f054`
- `0x140080414`

## callees

- `0x140001f94`
- `0x1400024b8`
- `0x140014580`
- `0x140019f58`
- `0x14001a07c`
- `0x14001c674`
- `0x14001d874`
- `0x14003f5b4`
- `0x140045530`
- `0x140045570`
- `0x140045940`
- `0x14007ea48`
- `0x14007f118`
- `0x14008283c`
- `0x14008a274`
- `0x14008d9e0`
- `0x14008e0e0`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x14007ffe1`
- `ntoskrnl!KeInitializeSpinLock` at `0x14007ffe1`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x14007f904`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x14007f904`
- `ntoskrnl!KeInitializeEvent` at `0x14007ffa7`
- `ntoskrnl!KeInitializeEvent` at `0x14007ffa7`

## pseudocode

```c
__int64 __fastcall HUBPDO_CreatePdoInternal(_QWORD *a1, char a2)
{
  char v4; // r12
  char v5; // r13
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rcx
  char v9; // r14
  int v10; // edi
  __int64 v11; // r9
  int v12; // eax
  int v13; // edx
  __int64 v14; // r9
  int v15; // r9d
  __int64 v16; // r9
  __int64 v17; // r9
  int v18; // r15d
  int v19; // eax
  int v20; // edx
  __int64 v21; // rax
  int v22; // eax
  int v23; // edx
  int PdoName; // eax
  int v25; // r9d
  __int64 v26; // r15
  int v27; // edi
  char v28; // cl
  int v29; // eax
  int v30; // edx
  int v31; // r9d
  __int64 v32; // r9
  __int64 v33; // r9
  __int64 v34; // r9
  __int64 v35; // r9
  int v36; // eax
  int v37; // edx
  int v38; // edx
  __int64 v39; // rax
  __int64 v40; // r9
  bool v41; // zf
  int v42; // edx
  int v43; // r8d
  __int64 v44; // rcx
  BOOL v45; // eax
  __int64 v46; // rcx
  BOOL v47; // eax
  __int64 v48; // rax
  int v49; // eax
  int v50; // edx
  struct _KEVENT *v51; // rax
  int v52; // eax
  int v53; // edx
  __int64 v54; // r8
  __int64 v55; // rax
  __int64 v56; // rdx
  __int64 v57; // rax
  unsigned int v58; // edi
  __int64 v59; // rax
  __int64 v61; // [rsp+28h] [rbp-D8h]
  __int64 v63; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v64; // [rsp+98h] [rbp-68h] BYREF
  _OWORD v65[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v66; // [rsp+C0h] [rbp-40h]
  __int64 *v67; // [rsp+D0h] [rbp-30h]
  __int64 v68; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v69[48]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v70; // [rsp+110h] [rbp+10h] BYREF
  __int64 v71; // [rsp+120h] [rbp+20h]
  __int128 v72; // [rsp+128h] [rbp+28h] BYREF
  __int128 v73; // [rsp+138h] [rbp+38h]
  __int64 (__fastcall *v74)(__int64, wchar_t **); // [rsp+148h] [rbp+48h]
  __int64 v75; // [rsp+150h] [rbp+50h] BYREF
  __int128 v76; // [rsp+160h] [rbp+60h] BYREF
  __int128 v77; // [rsp+170h] [rbp+70h]
  __m256i v78; // [rsp+180h] [rbp+80h] BYREF
  _QWORD v79[18]; // [rsp+1A0h] [rbp+A0h] BYREF
  _QWORD v80[12]; // [rsp+230h] [rbp+130h] BYREF
  _QWORD v81[18]; // [rsp+290h] [rbp+190h] BYREF
  _QWORD v82[10]; // [rsp+320h] [rbp+220h] BYREF
  __int128 v83; // [rsp+370h] [rbp+270h] BYREF
  __int128 v84; // [rsp+380h] [rbp+280h]
  __int128 v85; // [rsp+390h] [rbp+290h]
  int v86; // [rsp+3A0h] [rbp+2A0h]
  int v87; // [rsp+3A4h] [rbp+2A4h]
  int v88; // [rsp+3A8h] [rbp+2A8h]
  int v89; // [rsp+3ACh] [rbp+2ACh]
  int v90; // [rsp+3B0h] [rbp+2B0h]
  int v91; // [rsp+3B4h] [rbp+2B4h]
  _DWORD v92[2]; // [rsp+3B8h] [rbp+2B8h] BYREF
  char v93; // [rsp+3C0h] [rbp+2C0h]

  memset(v79, 0, 0x8Cu);
  memset(&v78, 0, 28);
  LODWORD(v67) = 0;
  v76 = 0;
  v77 = 0;
  memset(v65, 0, sizeof(v65));
  v66 = 0;
  memset(v80, 0, sizeof(v80));
  v75 = 0;
  v63 = 0;
  v83 = 0;
  v84 = 0;
  v85 = 0;
  memset(v82, 0, sizeof(v82));
  memset(v81, 0, sizeof(v81));
  v4 = 0;
  v74 = 0;
  LODWORD(v71) = 0;
  v5 = 0;
  v68 = 0;
  v64 = 0;
  v6 = a1[1];
  v72 = 0;
  v73 = 0;
  memset(v69, 0, 44);
  v70 = 0;
  _InterlockedAnd((volatile signed __int32 *)(v6 + 1336), 0xFFFFFF7F);
  if ( a2 )
  {
    _InterlockedOr((volatile signed __int32 *)a1 + 411, 2u);
    if ( (*(_DWORD *)(*a1 + 40LL) & 0x40000) != 0 && (a1[205] & 0x20) != 0 )
      HUBREG_SetVidPidRevForPort(a1);
  }
  else
  {
    _InterlockedAnd((volatile signed __int32 *)a1 + 411, 0xFFFFFFFD);
    if ( (*(_DWORD *)(*a1 + 40LL) & 0x40000) == 0 || (a1[205] & 0x20) == 0 )
    {
      if ( (unsigned int)Feature_UH3WET__private_IsEnabledDeviceUsageNoInline() )
        WMI_FireNotification((__int64 *)a1[1], 0);
      else
        WMI_FireNotificationOld(*a1, *(_WORD *)(a1[1] + 200LL), 0);
    }
  }
  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, *a1);
  v63 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1680))(WdfDriverGlobals, v7);
  if ( !v63 )
  {
    v9 = 0;
    v10 = -1073741670;
    goto LABEL_93;
  }
  v9 = 1;
  memset(v79, 0, sizeof(v79));
  v79[1] = HUBPDO_EvtDeviceD0Entry;
  v79[3] = HUBPDO_EvtDeviceD0Exit;
  v79[5] = HUBPDO_EvtDevicePrepareHardware;
  v79[6] = HUBPDO_EvtDeviceReleaseHardware;
  v79[12] = HUBPDO_EvtDeviceSurpriseRemoval;
  v79[9] = HUBPDO_EvtDeviceSelfManagedIoInit;
  v79[11] = HUBPDO_EvtDeviceSelfManagedIoInit;
  v79[10] = HUBPDO_EvtDeviceSelfManagedIoSuspend;
  v79[17] = HUBPDO_EvtDeviceUsageNotificationEx;
  v79[14] = HUBPDO_EvtDeviceQueryStop;
  v79[13] = HUBPDO_EvtDeviceQueryRemove;
  LODWORD(v79[0]) = 144;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *))(WdfFunctions_01015 + 440))(
    WdfDriverGlobals,
    v63,
    v79);
  v78.m256i_i64[1] = (__int64)HUBPDO_EvtDeviceEnableWakeAtBus;
  v78.m256i_i64[2] = (__int64)HUBPDO_EvtDeviceDisableWakeAtBus;
  v78.m256i_i64[3] = (__int64)HUBPDO_EvtDeviceReportedMissing;
  *(_QWORD *)&v77 = HUBPDO_EvtDeviceResourceRequirementsQuery;
  v76 = 0x40u;
  *((_QWORD *)&v77 + 1) = 0;
  v78.m256i_i64[0] = 0;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *))(WdfFunctions_01015 + 1688))(
    WdfDriverGlobals,
    v63,
    &v76);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 528))(WdfDriverGlobals, v63, 34);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 496))(WdfDriverGlobals, v63, 0);
  LOBYTE(v11) = 15;
  v12 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 (__fastcall *)(__int64, IRP *), __int64, _QWORD, _DWORD))(WdfFunctions_01015 + 584))(
          WdfDriverGlobals,
          v63,
          HUBPDO_EvtDeviceWdmIrpPreprocess,
          v11,
          0,
          0);
  v10 = v12;
  if ( v12 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_93;
    v15 = 120;
    goto LABEL_15;
  }
  LOBYTE(v14) = 14;
  v12 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 (__fastcall *)(__int64, IRP *), __int64, _QWORD, _DWORD))(WdfFunctions_01015 + 584))(
          WdfDriverGlobals,
          v63,
          HUBPDO_EvtDeviceWdmIrpPreprocess,
          v14,
          0,
          0);
  v10 = v12;
  if ( v12 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_93;
    v15 = 121;
    goto LABEL_15;
  }
  v92[0] = 419564552;
  LOBYTE(v16) = 27;
  v92[1] = 336271104;
  v93 = 19;
  v12 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 (__fastcall *)(__int64, IRP *), __int64, _DWORD *, int))(WdfFunctions_01015 + 584))(
          WdfDriverGlobals,
          v63,
          HUBPDO_EvtDeviceWdmIrpPnPPowerPreprocess,
          v16,
          v92,
          9);
  v10 = v12;
  if ( v12 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_93;
    v15 = 122;
    goto LABEL_15;
  }
  LOBYTE(v92[0]) = 2;
  LOBYTE(v17) = 22;
  v12 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 (__fastcall *)(__int64, IRP *), __int64, _DWORD *, int))(WdfFunctions_01015 + 584))(
          WdfDriverGlobals,
          v63,
          HUBPDO_EvtDeviceWdmIrpPnPPowerPreprocess,
          v17,
          v92,
          1);
  v10 = v12;
  if ( v12 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_93;
    v15 = 123;
    goto LABEL_15;
  }
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 3136))(WdfDriverGlobals, v63);
  v68 = 0x100000008LL;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 3224))(
    WdfDriverGlobals,
    v63,
    &v68);
  v12 = HUBPDO_AssignPDOIds((__int64)a1, v63);
  v10 = v12;
  if ( v12 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_93;
    v15 = 124;
LABEL_15:
    LODWORD(v61) = v12;
    LOBYTE(v13) = 2;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(a1[1] + 1432LL),
      v13,
      2,
      v15,
      (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
      v61);
    v9 = 1;
    goto LABEL_93;
  }
  v18 = 0;
  if ( (*((_DWORD *)a1 + 411) & 2) == 0 )
  {
    v19 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, GUID *))(WdfFunctions_01015 + 1744))(
            WdfDriverGlobals,
            v63,
            &GUID_DEVCLASS_UNKNOWN);
    if ( v19 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v61) = v19;
      LOBYTE(v20) = 3;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1[1] + 1432LL),
        v20,
        2,
        125,
        (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
        v61);
    }
  }
  v67 = off_14006B1D0;
  *(_QWORD *)&v65[0] = 56;
  *((_QWORD *)&v65[0] + 1) = HUBPDO_EvtDeviceCleanup;
  *(_QWORD *)&v65[1] = 0;
  v66 = 0;
  *((_QWORD *)&v65[1] + 1) = 0x100000001LL;
  v21 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD *))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, a1);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const char *, __int64, const char *))(WdfFunctions_01015 + 1640))(
    WdfDriverGlobals,
    v21,
    "DSM PDO Tag",
    8742,
    "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubpdo.c");
  v5 = 1;
  while ( 1 )
  {
    PdoName = HUBPDO_MakePdoName((__int64)a1, v63);
    v10 = PdoName;
    if ( PdoName < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_44;
      v25 = 126;
      LODWORD(v61) = PdoName;
LABEL_43:
      LOBYTE(v23) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1[1] + 1432LL),
        v23,
        2,
        v25,
        (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
        v61);
      goto LABEL_44;
    }
    v22 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const UNICODE_STRING *))(WdfFunctions_01015 + 544))(
            WdfDriverGlobals,
            v63,
            &SDDL_DEVOBJ_SYS_ALL_ADM_RWX_WORLD_RW_RES_R);
    v10 = v22;
    if ( v22 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_44;
      v25 = 127;
LABEL_42:
      LODWORD(v61) = v22;
      goto LABEL_43;
    }
    v22 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64 *, _OWORD *, unsigned __int64 *))(WdfFunctions_01015
                                                                                                  + 600))(
            WdfDriverGlobals,
            &v63,
            v65,
            &v64);
    v10 = v22;
    if ( v22 >= 0 )
      break;
    if ( v22 != -1073741771 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v25 = 128;
        goto LABEL_42;
      }
LABEL_44:
      v9 = v5;
      goto LABEL_93;
    }
    ++v18;
  }
  v26 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, __int64 *))(WdfFunctions_01015 + 1616))(
          WdfDriverGlobals,
          v64,
          off_14006B1D0);
  IoInitializeRemoveLockEx((PIO_REMOVE_LOCK)(v26 + 424), 0x55535257u, 0, 0, 0x20u);
  memset((void *)(v26 + 456), 0, 0x50u);
  *(_BYTE *)(v26 + 536) = 0;
  v27 = *((_DWORD *)a1 + 410);
  if ( (v27 & 2) != 0 )
  {
    memset(v81, 0, sizeof(v81));
    LODWORD(v81[0]) = 66388112;
    v81[2] = HUBFDO_GetPortStatusForDebuggingComplete;
    v81[3] = HUBFDO_GetPortStatusForDebuggingComplete;
    v28 = *(_BYTE *)(*a1 + 240LL);
    LODWORD(v81[6]) = *((_DWORD *)a1 + 43);
    v81[5] = a1[3];
    *(_QWORD *)&v69[8] = v81;
    LOBYTE(v81[4]) = v28 + 1;
    *(_QWORD *)&v69[24] = 0;
    *(_QWORD *)&v69[16] = &GUID_HUB_PARENT_INTERFACE;
    *(_QWORD *)&v69[32] = HUBPDO_EvtDeviceProcessQueryInterfaceRequest;
    *(_QWORD *)&v69[40] = 1;
    BYTE5(v81[6]) = (v27 & 0x1000) != 0;
    v81[17] = 0;
    *(_QWORD *)v69 = 48;
    v29 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, _BYTE *))(WdfFunctions_01015 + 1824))(
            WdfDriverGlobals,
            v64,
            v69);
    v10 = v29;
    if ( v29 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v31 = 129;
        goto LABEL_49;
      }
      goto LABEL_50;
    }
  }
  *(_QWORD *)&v73 = HUBFDO_GetPortStatusForDebuggingComplete;
  *((_QWORD *)&v73 + 1) = HUBFDO_GetPortStatusForDebuggingComplete;
  v74 = HUBPDO_GetLocationString;
  *(_QWORD *)&v69[8] = &v72;
  *(_QWORD *)&v69[16] = &GUID_PNP_LOCATION_INTERFACE;
  *(_QWORD *)&v72 = 65576;
  *((_QWORD *)&v72 + 1) = a1;
  *(_QWORD *)v69 = 48;
  memset(&v69[24], 0, 24);
  v29 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, _BYTE *))(WdfFunctions_01015 + 1824))(
          WdfDriverGlobals,
          v64,
          v69);
  v10 = v29;
  if ( v29 >= 0 )
  {
    LOBYTE(v32) = 1;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, __int64, __int64))(WdfFunctions_01015 + 392))(
      WdfDriverGlobals,
      v64,
      1,
      v32);
    LOBYTE(v33) = 1;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, __int64, __int64))(WdfFunctions_01015 + 392))(
      WdfDriverGlobals,
      v64,
      2,
      v33);
    LOBYTE(v34) = 1;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, __int64, __int64))(WdfFunctions_01015 + 392))(
      WdfDriverGlobals,
      v64,
      3,
      v34);
    LOBYTE(v35) = 1;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, __int64, __int64))(WdfFunctions_01015 + 392))(
      WdfDriverGlobals,
      v64,
      4,
      v35);
    *(_QWORD *)(v26 + 24) = a1;
    *(_QWORD *)(v26 + 16) = *a1;
    *(_WORD *)(v26 + 48) = *(_WORD *)(a1[1] + 200LL);
    *(_DWORD *)(v26 + 384) = 5;
    *(_DWORD *)(v26 + 388) = -1;
    if ( a2 )
      *(_QWORD *)(v26 + 8) = *(_QWORD *)(*a1 + 2464LL);
    else
      *(_BYTE *)v26 = 1;
    a1[2] = v26;
    memset(v80, 0, sizeof(v80));
    v80[6] = HUBPDO_EvtIoInternalDeviceControl;
    LODWORD(v80[0]) = 96;
    v80[5] = HUBPDO_EvtIoDeviceControl;
    BYTE5(v80[1]) = 1;
    *(_QWORD *)((char *)v80 + 4) = 1;
    v36 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, _QWORD *, _QWORD))(WdfFunctions_01015 + 1216))(
            WdfDriverGlobals,
            v64,
            v80,
            0);
    v10 = v36;
    if ( v36 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v61) = v36;
        LOBYTE(v37) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(a1[1] + 1432LL),
          v37,
          2,
          131,
          (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
          v61);
      }
      v4 = 1;
      v5 = 0;
      goto LABEL_44;
    }
    v38 = *((_DWORD *)a1 + 410);
    *((_QWORD *)&v85 + 1) = -1;
    *(_QWORD *)&v83 = 0x200000030LL;
    DWORD1(v84) = ((unsigned __int8)v38 >> 6) & 1;
    v39 = a1[1];
    HIDWORD(v83) = ((unsigned __int8)~(_BYTE)v38 >> 5) & 1;
    DWORD2(v83) = 2;
    LODWORD(v84) = 2;
    *((_QWORD *)&v84 + 1) = 2;
    *(_QWORD *)&v85 = 0x200000002LL;
    DWORD2(v85) = *(unsigned __int16 *)(v39 + 200);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, __int128 *))(WdfFunctions_01015 + 664))(
      WdfDriverGlobals,
      v64,
      &v83);
    v40 = *a1;
    *(_QWORD *)((char *)v82 + 4) = 0x200000002LL;
    v41 = (a1[205] & 0x102) == 0;
    v42 = 2;
    *(__m128i *)((char *)&v82[3] + 4) = _mm_load_si128((const __m128i *)&_xmm);
    v82[8] = -1;
    v4 = 1;
    v82[9] = 0x5FFFFFFFFLL;
    *(_QWORD *)((char *)&v82[1] + 4) = 0x200000002LL;
    *(_QWORD *)((char *)&v82[2] + 4) = 0x200000002LL;
    v5 = 0;
    LODWORD(v82[0]) = 80;
    *(_OWORD *)&v82[5] = *(_OWORD *)((char *)&v82[3] + 4);
    v82[7] = 0x700000005LL;
    v43 = *(_DWORD *)(v40 + 756);
    HIDWORD(v82[7]) = v43;
    LODWORD(v82[4]) = 1;
    v82[8] = 0;
    LODWORD(v82[9]) = 0;
    if ( v41 )
    {
      LODWORD(v82[7]) = 1;
      *(_QWORD *)((char *)&v82[1] + 4) = 1;
      *(_QWORD *)((char *)&v82[2] + 4) = 0;
      *(_QWORD *)((char *)v82 + 4) = 0;
      while ( 1 )
      {
        v44 = (unsigned int)v42;
        v45 = v42++ > v43;
        *((_DWORD *)&v82[3] + v44 + 1) = v45 + 3;
        if ( v42 > 6 )
          break;
        v43 = HIDWORD(v82[7]);
      }
    }
    else
    {
      LODWORD(v82[7]) = 3;
      *(_QWORD *)((char *)&v82[1] + 4) = 0x100000001LL;
      *(_QWORD *)((char *)&v82[2] + 4) = 1;
      *(_QWORD *)((char *)v82 + 4) = 0x100000001LL;
      while ( 1 )
      {
        v46 = (unsigned int)v42;
        v47 = v42++ > v43;
        *((_DWORD *)&v82[3] + v46 + 1) = v47 + 3;
        if ( v42 > 6 )
          break;
        v43 = HIDWORD(v82[7]);
      }
      if ( (a1[183] & 0x800) != 0 )
      {
        v67 = off_14006B128;
        v66 = v64;
        *(_OWORD *)((char *)v65 + 4) = 0;
        *(_QWORD *)((char *)&v65[1] + 4) = 0x100000000LL;
        LODWORD(v65[0]) = 56;
        HIDWORD(v65[1]) = 1;
        v48 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 336))(
                WdfDriverGlobals,
                *(_QWORD *)(v40 + 16));
        v49 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _OWORD *, __int64, __int64))(WdfFunctions_01015 + 1976))(
                WdfDriverGlobals,
                v65,
                v48,
                v26 + 264);
        v10 = v49;
        if ( v49 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LODWORD(v61) = v49;
            LOBYTE(v50) = 2;
            WPP_RECORDER_SF_d(
              *(_QWORD *)(a1[1] + 1432LL),
              v50,
              2,
              132,
              (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
              v61);
          }
          *(_QWORD *)(v26 + 264) = 0;
          goto LABEL_44;
        }
        v51 = (struct _KEVENT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01015
                                                                                                  + 1616))(
                                  WdfDriverGlobals,
                                  *(_QWORD *)(v26 + 264),
                                  off_14006B128);
        KeInitializeEvent(v51 + 1, NotificationEvent, 0);
      }
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, _QWORD *))(WdfFunctions_01015 + 672))(
      WdfDriverGlobals,
      v64,
      v82);
    KeInitializeSpinLock((PKSPIN_LOCK)(v26 + 208));
    *(_DWORD *)(v26 + 216) = 6000;
    *(_QWORD *)(v26 + 224) = ISMStateTable;
    *(_DWORD *)(v26 + 232) = 6000;
    v67 = off_14006B100;
    v66 = v64;
    *((_QWORD *)&v65[1] + 1) = 0x100000001LL;
    v71 = 1;
    *((_QWORD *)&v70 + 1) = HUBIDLE_EvtIdleWorkItem;
    memset((char *)v65 + 4, 0, 20);
    LODWORD(v65[0]) = 56;
    *(_QWORD *)&v70 = 24;
    v52 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, _OWORD *, __int64))(WdfFunctions_01015 + 3032))(
            WdfDriverGlobals,
            &v70,
            v65,
            v26 + 256);
    v10 = v52;
    if ( v52 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v61) = v52;
        LOBYTE(v53) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(a1[1] + 1432LL),
          v53,
          2,
          133,
          (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
          v61);
      }
      *(_QWORD *)(v26 + 256) = 0;
      goto LABEL_44;
    }
    HUBIDLE_AddEvent(v26 + 72, 6009, 0);
    _InterlockedOr((volatile signed __int32 *)(v26 + 32), 0x1000u);
    v22 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, unsigned __int64))(WdfFunctions_01015 + 1064))(
            WdfDriverGlobals,
            *(_QWORD *)(*a1 + 16LL),
            v64);
    v10 = v22;
    if ( v22 >= 0 )
    {
      v54 = *(_QWORD *)(v26 + 16);
      v86 = *(unsigned __int16 *)(v54 + 328);
      v55 = 0;
      do
      {
        v56 = (unsigned int)(v55 + 1);
        *(&v86 + v56) = *(unsigned __int16 *)(v54 + 2 * v55 + 330);
        v55 = v56;
      }
      while ( (unsigned int)v56 < 5 );
      v57 = *(unsigned __int8 *)(v54 + 240);
      if ( (unsigned __int8)v57 < 6u )
        *(&v86 + v57) = *(unsigned __int16 *)(v26 + 48);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qDDDdddddd(
          *(_QWORD *)(a1[1] + 1432LL),
          *((unsigned __int16 *)a1 + 1004),
          *((unsigned __int16 *)a1 + 1003),
          *((unsigned __int16 *)a1 + 1002),
          (unsigned int)&v75,
          (char)a1,
          *((_WORD *)a1 + 1002),
          *((_WORD *)a1 + 1003),
          *((_WORD *)a1 + 1004),
          v86,
          v87,
          v88,
          v89,
          v90,
          v91);
      v4 = 0;
      _InterlockedOr((volatile signed __int32 *)a1 + 557, 1u);
      _InterlockedOr((volatile signed __int32 *)a1 + 557, 2u);
      _InterlockedOr((volatile signed __int32 *)a1 + 557, 4u);
      _InterlockedOr((volatile signed __int32 *)a1 + 557, 0x10u);
      _InterlockedOr((volatile signed __int32 *)a1 + 557, 8u);
      _InterlockedOr((volatile signed __int32 *)a1 + 557, 0x20u);
      if ( (a1[205] & 2) != 0 )
        HUBPDO_RegisterForPowerSettingsForHub(v26, v56, v54, 0);
      else
        HUBPDO_RegisterForPowerSettingsForDevice(v26, v56, v54, 0);
      goto LABEL_44;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v9 = 0;
      goto LABEL_93;
    }
    v25 = 134;
    goto LABEL_42;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v31 = 130;
LABEL_49:
    LODWORD(v61) = v29;
    LOBYTE(v30) = 2;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(a1[1] + 1432LL),
      v30,
      2,
      v31,
      (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
      v61);
  }
LABEL_50:
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64))(WdfFunctions_01015 + 1664))(WdfDriverGlobals, v64);
  v5 = 0;
  v9 = 1;
  v4 = 1;
LABEL_93:
  if ( a2 )
  {
    if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 0x40) != 0 )
      McTemplateK0ppqq_EtwWriteTransfer(
        *(unsigned __int16 *)(a1[1] + 200LL),
        (unsigned int)USBHUB3_ETW_EVENT_DEVICE_ENUMERATION_COMPLETE,
        (_DWORD)a1 + 1524,
        *(_QWORD *)(*a1 + 248LL),
        a1[3],
        *(_WORD *)(a1[1] + 200LL),
        v10);
  }
  else if ( Microsoft_Windows_USB_USBHUB3EnableBits < 0 )
  {
    McTemplateK0pq_EtwWriteTransfer(
      v8,
      USBHUB3_ETW_EVENT_DEVICE_ENUMERATION_FAILED,
      (char *)a1 + 1524,
      *(_QWORD *)(*a1 + 248LL),
      v10);
  }
  if ( (*((_DWORD *)a1 + 411) & 0x40) != 0 )
  {
    *(_OWORD *)((char *)a1 + 1524) = 0;
    _InterlockedAnd((volatile signed __int32 *)a1 + 411, 0xFFFFFFBF);
  }
  v58 = (v10 >> 31) & 0xFFFFFFF4;
  if ( v9 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 432))(WdfDriverGlobals, v63);
  if ( v4 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64))(WdfFunctions_01015 + 1664))(WdfDriverGlobals, v64);
  if ( v5 )
  {
    v59 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD *))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, a1);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const char *, __int64, const char *))(WdfFunctions_01015 + 1648))(
      WdfDriverGlobals,
      v59,
      "DSM PDO Tag",
      9264,
      "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubpdo.c");
  }
  return v58 + 4077;
}

```

## disassembly

```asm
0x14007f118  push    rbp
0x14007f11a  push    rbx
0x14007f11b  push    rsi
0x14007f11c  push    rdi
0x14007f11d  push    r12
0x14007f11f  push    r13
0x14007f121  push    r14
0x14007f123  push    r15
0x14007f125  lea     rbp, [rsp-2D8h]
0x14007f12d  sub     rsp, 3D8h
0x14007f134  mov     rax, cs:__security_cookie
0x14007f13b  xor     rax, rsp
0x14007f13e  mov     [rbp+310h+var_48], rax
0x14007f145  mov     dil, dl
0x14007f148  mov     [rbp+310h+var_38F], dl
0x14007f14b  mov     rbx, rcx
0x14007f14e  xor     eax, eax
0x14007f150  xor     edx, edx; Val
0x14007f152  mov     [rbp+310h+var_26C], eax
0x14007f158  lea     rcx, [rbp+310h+var_270]; void *
0x14007f15f  mov     r8d, 8Ch; Size
0x14007f165  call    memset
0x14007f16a  xorps   xmm0, xmm0
0x14007f16d  lea     rcx, [rbp+310h+var_1E0]; void *
0x14007f174  xor     eax, eax
0x14007f176  xor     edx, edx; Val
0x14007f178  movups  [rbp+310h+var_290], xmm0
0x14007f17f  mov     dword ptr [rbp+310h+var_340], eax
0x14007f182  movups  [rbp+310h+var_2B0], xmm0
0x14007f186  lea     r8d, [rax+60h]; Size
0x14007f18a  movups  [rbp+310h+var_2A0], xmm0
0x14007f18e  movups  [rbp+310h+var_290+0Ch], xmm0
0x14007f195  movups  [rbp+310h+var_370], xmm0
0x14007f199  movups  [rbp+310h+var_360], xmm0
0x14007f19d  movups  [rbp+310h+var_350], xmm0
0x14007f1a1  call    memset
0x14007f1a6  xorps   xmm0, xmm0
0x14007f1a9  mov     [rbp+310h+var_2C0], 0
0x14007f1b1  xor     edx, edx; Val
0x14007f1b3  mov     [rbp+310h+var_380], 0
0x14007f1bb  lea     rcx, [rbp+310h+var_F0]; void *
0x14007f1c2  movups  [rbp+310h+var_A0], xmm0
0x14007f1c9  lea     r8d, [rdx+50h]; Size
0x14007f1cd  movups  [rbp+310h+var_90], xmm0
0x14007f1d4  movups  [rbp+310h+var_80], xmm0
0x14007f1db  call    memset
0x14007f1e0  xor     edx, edx; Val
0x14007f1e2  lea     rcx, [rbp+310h+var_180]; void *
0x14007f1e9  mov     r8d, 90h; Size
0x14007f1ef  call    memset
0x14007f1f4  xorps   xmm0, xmm0
0x14007f1f7  xor     eax, eax
0x14007f1f9  xor     r12b, r12b
0x14007f1fc  mov     [rbp+310h+var_2C8], rax
0x14007f200  movups  [rbp+310h+var_320], xmm0
0x14007f204  mov     dword ptr [rbp+310h+var_2F0], eax
0x14007f207  xor     r13b, r13b
0x14007f20a  mov     [rbp+310h+var_338], rax
0x14007f20e  mov     [rbp+310h+var_378], rax
0x14007f212  mov     rax, [rbx+8]
0x14007f216  movups  [rbp+310h+var_320+0Ch], xmm0
0x14007f21a  movups  [rbp+310h+var_2E8], xmm0
0x14007f21e  movups  [rbp+310h+var_2D8], xmm0
0x14007f222  movups  [rbp+310h+var_330], xmm0
0x14007f226  movups  [rbp+310h+var_300], xmm0
0x14007f22a  lock and dword ptr [rax+538h], 0FFFFFF7Fh
0x14007f235  mov     r15d, 2
0x14007f23b  test    dil, dil
0x14007f23e  jz      short loc_14007F268
0x14007f240  lock or [rbx+66Ch], r15d
0x14007f248  mov     rax, [rbx]
0x14007f24b  test    dword ptr [rax+28h], 40000h
0x14007f252  jz      short loc_14007F2B2
0x14007f254  mov     eax, [rbx+668h]
0x14007f25a  test    al, 20h
0x14007f25c  jz      short loc_14007F2B2
0x14007f25e  mov     rcx, rbx
0x14007f261  call    HUBREG_SetVidPidRevForPort
0x14007f266  jmp     short loc_14007F2B2
0x14007f268  lock and dword ptr [rbx+66Ch], 0FFFFFFFDh
0x14007f270  mov     rax, [rbx]
0x14007f273  test    dword ptr [rax+28h], 40000h
0x14007f27a  jz      short loc_14007F286
0x14007f27c  mov     eax, [rbx+668h]
0x14007f282  test    al, 20h
0x14007f284  jnz     short loc_14007F2B2
0x14007f286  call    Feature_UH3WET__private_IsEnabledDeviceUsageNoInline
0x14007f28b  test    eax, eax
0x14007f28d  jnz     short loc_14007F2A7
0x14007f28f  mov     rdx, [rbx+8]
0x14007f293  xor     r8d, r8d
0x14007f296  mov     rcx, [rbx]
0x14007f299  movzx   edx, word ptr [rdx+0C8h]
0x14007f2a0  call    WMI_FireNotificationOld
0x14007f2a5  jmp     short loc_14007F2B2
0x14007f2a7  mov     rcx, [rbx+8]
0x14007f2ab  xor     edx, edx
0x14007f2ad  call    WMI_FireNotification
0x14007f2b2  mov     rax, cs:WdfFunctions_01015
0x14007f2b9  mov     rdx, [rbx]
0x14007f2bc  mov     rcx, cs:WdfDriverGlobals
0x14007f2c3  mov     rax, [rax+660h]
0x14007f2ca  call    _guard_dispatch_icall
0x14007f2cf  mov     rcx, cs:WdfFunctions_01015
0x14007f2d6  mov     rdx, rax
0x14007f2d9  mov     r8, [rcx+690h]
0x14007f2e0  mov     rcx, cs:WdfDriverGlobals
0x14007f2e7  mov     rax, r8
0x14007f2ea  call    _guard_dispatch_icall
0x14007f2ef  mov     [rbp+310h+var_380], rax
0x14007f2f3  lea     rsi, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\usb\\usb3\\hub\\"...
0x14007f2fa  test    rax, rax
0x14007f2fd  jnz     short loc_14007F30C
0x14007f2ff  xor     r14b, r14b
0x14007f302  mov     edi, 0C000009Ah
0x14007f307  jmp     loc_1400802B3
0x14007f30c  mov     esi, 1
0x14007f311  lea     rcx, [rbp+310h+var_270]; void *
0x14007f318  mov     edi, 90h
0x14007f31d  mov     [rbp+310h+var_390], sil
0x14007f321  mov     r8d, edi; Size
0x14007f324  xor     edx, edx; Val
0x14007f326  mov     r14b, sil
0x14007f329  call    memset
0x14007f32e  mov     rdx, [rbp+310h+var_380]
0x14007f332  lea     rax, HUBPDO_EvtDeviceD0Entry
0x14007f339  mov     rcx, cs:WdfDriverGlobals
0x14007f340  lea     r8, [rbp+310h+var_270]
0x14007f347  mov     [rbp+310h+var_268], rax
0x14007f34e  lea     rax, HUBPDO_EvtDeviceD0Exit
0x14007f355  mov     [rbp+310h+var_258], rax
0x14007f35c  lea     rax, HUBPDO_EvtDevicePrepareHardware
0x14007f363  mov     [rbp+310h+var_248], rax
0x14007f36a  lea     rax, HUBPDO_EvtDeviceReleaseHardware
0x14007f371  mov     [rbp+310h+var_240], rax
0x14007f378  lea     rax, HUBPDO_EvtDeviceSurpriseRemoval
0x14007f37f  mov     [rbp+310h+var_210], rax
0x14007f386  lea     rax, HUBPDO_EvtDeviceSelfManagedIoInit
0x14007f38d  mov     [rbp+310h+var_228], rax
0x14007f394  lea     rax, HUBPDO_EvtDeviceSelfManagedIoInit
0x14007f39b  mov     [rbp+310h+var_218], rax
0x14007f3a2  lea     rax, HUBPDO_EvtDeviceSelfManagedIoSuspend
0x14007f3a9  mov     [rbp+310h+var_220], rax
0x14007f3b0  lea     rax, HUBPDO_EvtDeviceUsageNotificationEx
0x14007f3b7  mov     [rbp+310h+var_1E8], rax
0x14007f3be  lea     rax, HUBPDO_EvtDeviceQueryStop
0x14007f3c5  mov     [rbp+310h+var_200], rax
0x14007f3cc  lea     rax, HUBPDO_EvtDeviceQueryRemove
0x14007f3d3  mov     [rbp+310h+var_208], rax
0x14007f3da  mov     rax, cs:WdfFunctions_01015
0x14007f3e1  mov     [rbp+310h+var_270], edi
0x14007f3e7  mov     rax, [rax+1B8h]
0x14007f3ee  call    _guard_dispatch_icall
0x14007f3f3  mov     rdx, [rbp+310h+var_380]
0x14007f3f7  lea     rax, HUBPDO_EvtDeviceEnableWakeAtBus
0x14007f3fe  mov     rcx, cs:WdfDriverGlobals
0x14007f405  lea     r8, [rbp+310h+var_2B0]
0x14007f409  mov     qword ptr [rbp+310h+var_290+8], rax
0x14007f410  lea     rax, HUBPDO_EvtDeviceDisableWakeAtBus
0x14007f417  mov     [rbp+310h+var_280], rax
0x14007f41e  lea     rax, HUBPDO_EvtDeviceReportedMissing
0x14007f425  mov     [rbp+310h+var_278], rax
0x14007f42c  lea     rax, HUBPDO_EvtDeviceResourceRequirementsQuery
0x14007f433  mov     qword ptr [rbp+310h+var_2A0], rax
0x14007f437  mov     rax, cs:WdfFunctions_01015
0x14007f43e  mov     qword ptr [rbp+310h+var_2B0+4], 0
0x14007f446  mov     dword ptr [rbp+310h+var_2B0+0Ch], 0
0x14007f44d  mov     qword ptr [rbp+310h+var_2A0+8], 0
0x14007f455  mov     qword ptr [rbp+310h+var_290], 0
0x14007f460  mov     dword ptr [rbp+310h+var_2B0], 40h ; '@'
0x14007f467  mov     rax, [rax+698h]
0x14007f46e  call    _guard_dispatch_icall
0x14007f473  mov     rax, cs:WdfFunctions_01015
0x14007f47a  lea     r8d, [rsi+21h]
0x14007f47e  mov     rdx, [rbp+310h+var_380]
0x14007f482  mov     rcx, cs:WdfDriverGlobals
0x14007f489  mov     rax, [rax+210h]
0x14007f490  call    _guard_dispatch_icall
0x14007f495  mov     rax, cs:WdfFunctions_01015
0x14007f49c  xor     r8d, r8d
0x14007f49f  mov     rdx, [rbp+310h+var_380]
0x14007f4a3  mov     rcx, cs:WdfDriverGlobals
0x14007f4aa  mov     rax, [rax+1F0h]
0x14007f4b1  call    _guard_dispatch_icall
0x14007f4b6  mov     rax, cs:WdfFunctions_01015
0x14007f4bd  lea     r8, HUBPDO_EvtDeviceWdmIrpPreprocess
0x14007f4c4  mov     rdx, [rbp+310h+var_380]
0x14007f4c8  mov     r9b, 0Fh
0x14007f4cb  mov     rcx, cs:WdfDriverGlobals
0x14007f4d2  mov     dword ptr [rsp+410h+var_3E8], 0
0x14007f4da  mov     rax, [rax+248h]
0x14007f4e1  mov     qword ptr [rsp+410h+RemlockSize], 0
0x14007f4ea  call    _guard_dispatch_icall
0x14007f4ef  mov     edi, eax
0x14007f4f1  test    eax, eax
0x14007f4f3  jns     short loc_14007F53E
0x14007f4f5  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007f4fc  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14007f503  jz      loc_1400802AC
0x14007f509  mov     r9d, 78h ; 'x'
0x14007f50f  mov     rcx, [rbx+8]
0x14007f513  lea     r14, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x14007f51a  mov     dword ptr [rsp+410h+var_3E8], eax
0x14007f51e  mov     r8d, r15d
0x14007f521  mov     dl, r15b
0x14007f524  mov     qword ptr [rsp+410h+RemlockSize], r14
0x14007f529  mov     rcx, [rcx+598h]
0x14007f530  call    WPP_RECORDER_SF_d
0x14007f535  mov     r14b, [rbp+310h+var_390]
0x14007f539  jmp     loc_1400802AC
0x14007f53e  mov     rax, cs:WdfFunctions_01015
0x14007f545  lea     r8, HUBPDO_EvtDeviceWdmIrpPreprocess
0x14007f54c  mov     rdx, [rbp+310h+var_380]
0x14007f550  mov     r9b, 0Eh
0x14007f553  mov     rcx, cs:WdfDriverGlobals
0x14007f55a  mov     dword ptr [rsp+410h+var_3E8], 0
0x14007f562  mov     rax, [rax+248h]
0x14007f569  mov     qword ptr [rsp+410h+RemlockSize], 0
0x14007f572  call    _guard_dispatch_icall
0x14007f577  mov     edi, eax
0x14007f579  test    eax, eax
0x14007f57b  jns     short loc_14007F59C
0x14007f57d  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007f584  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14007f58b  jz      loc_1400802AC
0x14007f591  mov     r9d, 79h ; 'y'
0x14007f597  jmp     loc_14007F50F
0x14007f59c  mov     rax, cs:WdfFunctions_01015
0x14007f5a3  lea     rcx, [rbp+310h+var_58]
0x14007f5aa  mov     rdx, [rbp+310h+var_380]
0x14007f5ae  lea     r8, HUBPDO_EvtDeviceWdmIrpPnPPowerPreprocess
0x14007f5b5  mov     [rbp+310h+var_58], 19020C08h
0x14007f5bf  mov     r9b, 1Bh
0x14007f5c2  mov     [rbp+310h+var_54], 140B1700h
0x14007f5cc  mov     [rbp+310h+var_50], 13h
0x14007f5d3  mov     rax, [rax+248h]
0x14007f5da  mov     dword ptr [rsp+410h+var_3E8], 9
0x14007f5e2  mov     qword ptr [rsp+410h+RemlockSize], rcx
0x14007f5e7  mov     rcx, cs:WdfDriverGlobals
0x14007f5ee  call    _guard_dispatch_icall
0x14007f5f3  mov     edi, eax
0x14007f5f5  test    eax, eax
0x14007f5f7  jns     short loc_14007F618
0x14007f5f9  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007f600  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14007f607  jz      loc_1400802AC
0x14007f60d  mov     r9d, 7Ah ; 'z'
0x14007f613  jmp     loc_14007F50F
0x14007f618  mov     rax, cs:WdfFunctions_01015
0x14007f61f  lea     rcx, [rbp+310h+var_58]
0x14007f626  mov     rdx, [rbp+310h+var_380]
0x14007f62a  lea     r8, HUBPDO_EvtDeviceWdmIrpPnPPowerPreprocess
0x14007f631  mov     byte ptr [rbp+310h+var_58], r15b
0x14007f638  mov     r9b, 16h
0x14007f63b  mov     dword ptr [rsp+410h+var_3E8], esi
0x14007f63f  mov     rax, [rax+248h]
0x14007f646  mov     qword ptr [rsp+410h+RemlockSize], rcx
0x14007f64b  mov     rcx, cs:WdfDriverGlobals
0x14007f652  call    _guard_dispatch_icall
0x14007f657  mov     edi, eax
0x14007f659  test    eax, eax
0x14007f65b  jns     short loc_14007F67C
0x14007f65d  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007f664  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14007f66b  jz      loc_1400802AC
0x14007f671  mov     r9d, 7Bh ; '{'
0x14007f677  jmp     loc_14007F50F
0x14007f67c  mov     rax, cs:WdfFunctions_01015
0x14007f683  mov     rdx, [rbp+310h+var_380]
0x14007f687  mov     rcx, cs:WdfDriverGlobals
0x14007f68e  mov     rax, [rax+0C40h]
0x14007f695  call    _guard_dispatch_icall
0x14007f69a  mov     rax, cs:WdfFunctions_01015
0x14007f6a1  lea     r8, [rbp+310h+var_338]
0x14007f6a5  mov     rdx, [rbp+310h+var_380]
0x14007f6a9  mov     rcx, cs:WdfDriverGlobals
0x14007f6b0  mov     dword ptr [rbp+310h+var_338], 8
0x14007f6b7  mov     dword ptr [rbp+310h+var_338+4], esi
0x14007f6ba  mov     rax, [rax+0C98h]
0x14007f6c1  call    _guard_dispatch_icall
0x14007f6c6  mov     rdx, [rbp+310h+var_380]
0x14007f6ca  mov     rcx, rbx
0x14007f6cd  call    HUBPDO_AssignPDOIds
0x14007f6d2  mov     edi, eax
0x14007f6d4  test    eax, eax
0x14007f6d6  jns     short loc_14007F6F7
0x14007f6d8  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007f6df  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14007f6e6  jz      loc_1400802AC
0x14007f6ec  mov     r9d, 7Ch ; '|'
0x14007f6f2  jmp     loc_14007F50F
0x14007f6f7  mov     eax, [rbx+66Ch]
0x14007f6fd  lea     r14, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x14007f704  xor     r15d, r15d
0x14007f707  lea     rsi, WPP_RECORDER_INITIALIZED
0x14007f70e  test    al, 2
0x14007f710  jnz     short loc_14007F767
0x14007f712  mov     rax, cs:WdfFunctions_01015
0x14007f719  lea     r8, GUID_DEVCLASS_UNKNOWN
0x14007f720  mov     rdx, [rbp+310h+var_380]
  ... truncated ...
```
