# HUBFDO_EvtDevicePrepareHardware

- ea: `0x140079940`
- end: `0x14007a4d9`
- name: `HUBFDO_EvtDevicePrepareHardware`
- size: `2969`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `25`
- tags: `reparse_path, installer_update, broker_com_uri`

## callees

- `0x140001a98`
- `0x140001f94`
- `0x140001ffc`
- `0x140002078`
- `0x140002108`
- `0x140002384`
- `0x1400024b8`
- `0x1400067ac`
- `0x1400073cc`
- `0x1400083b4`
- `0x14000aa4c`
- `0x1400336a8`
- `0x140045570`
- `0x140045640`
- `0x14007881c`
- `0x140079940`
- `0x14007de8c`
- `0x14007e678`
- `0x14007e8fc`
- `0x140083e7c`
- `0x140089c94`
- `0x140089f3c`
- `0x14008c9fc`
- `0x14008e798`
- `0x14008f0a4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14007a3a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a3a6`
- `ntoskrnl!KeResetEvent` at `0x140079b03`
- `ntoskrnl!KeResetEvent` at `0x140079b03`
- `ntoskrnl!ExAllocatePool2` at `0x140079bdf`
- `ntoskrnl!ExAllocatePool2` at `0x14007a34a`
- `ntoskrnl!ExAllocatePool2` at `0x140079bdf`
- `ntoskrnl!ExAllocatePool2` at `0x14007a34a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140079a3e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140079b73`
- `ntoskrnl!RtlInitUnicodeString` at `0x140079a3e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140079b73`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140079c43`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140079c43`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140079a58`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140079a58`

## pseudocode

```c
__int64 __fastcall HUBFDO_EvtDevicePrepareHardware(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rcx
  __int64 v4; // rdi
  int v5; // eax
  int v6; // edx
  const WCHAR *v7; // rax
  __int64 v8; // rdx
  int v9; // esi
  int v10; // edx
  __int64 Pool2; // rax
  int v12; // edx
  int v13; // edx
  int v14; // eax
  int v15; // edx
  int FirmwareUpdateDevice; // eax
  int v17; // edx
  __int64 v18; // r14
  __int64 v19; // rcx
  __int64 v20; // r15
  __int64 v21; // rax
  __int64 v22; // rbx
  int v23; // eax
  char v24; // r14
  char v25; // dl
  int v26; // eax
  int v27; // eax
  __int64 v28; // r15
  __int64 v29; // r12
  __int64 v30; // r13
  char v31; // r8
  char v32; // r9
  char v33; // r10
  char v34; // r11
  char v35; // dl
  int v36; // eax
  __int64 v37; // r15
  __int64 v38; // r12
  __int64 v39; // r13
  char v40; // r8
  char v41; // r9
  char v42; // r10
  char v43; // r11
  char v44; // dl
  __int64 v45; // rdx
  void *v46; // rax
  void *v47; // r14
  __int64 v48; // rax
  _QWORD *v49; // r8
  int v50; // edx
  __int64 v51; // rcx
  int v52; // eax
  __int64 *v54; // [rsp+28h] [rbp-118h]
  int v55; // [rsp+30h] [rbp-110h]
  char v56; // [rsp+C0h] [rbp-80h]
  char v57; // [rsp+C0h] [rbp-80h]
  char v58; // [rsp+C1h] [rbp-7Fh]
  __int16 v59; // [rsp+C4h] [rbp-7Ch]
  int v60; // [rsp+C4h] [rbp-7Ch]
  int v61; // [rsp+C8h] [rbp-78h]
  int v62; // [rsp+C8h] [rbp-78h]
  int v63; // [rsp+CCh] [rbp-74h]
  int v64; // [rsp+CCh] [rbp-74h]
  int v65; // [rsp+D0h] [rbp-70h]
  int v66; // [rsp+D0h] [rbp-70h]
  int v67; // [rsp+D4h] [rbp-6Ch]
  int v68; // [rsp+D4h] [rbp-6Ch]
  int v69; // [rsp+D8h] [rbp-68h]
  __int16 v70; // [rsp+D8h] [rbp-68h]
  int AcpiPortAttributes; // [rsp+DCh] [rbp-64h]
  __int64 v72; // [rsp+E0h] [rbp-60h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+E8h] [rbp-58h] BYREF
  UNICODE_STRING SourceString; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v75; // [rsp+108h] [rbp-38h]
  char v76; // [rsp+178h] [rbp+38h]
  char v77; // [rsp+178h] [rbp+38h]

  SourceString = 0;
  v72 = 0;
  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006B270);
  v4 = v2;
  if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 2) != 0 )
    McTemplateK0p_EtwWriteTransfer(v3, USBHUB3_ETW_EVENT_HUB_PREPARE_HARDWARE_START, 0, *(_QWORD *)(v2 + 248));
  HUBREG_QueryValuesInHubHardwareKey(v4);
  HUBREG_ReadUsb4HostNameStringFromDeviceHardwareKey((_QWORD *)v4);
  v54 = &v72;
  v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64, _QWORD))(WdfFunctions_01015 + 656))(
         WdfDriverGlobals,
         a1,
         22,
         1,
         0);
  if ( v5 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v54) = v5;
      LOBYTE(v6) = 2;
      WPP_RECORDER_SF_d(*(_QWORD *)(v4 + 2536), v6, 3, 41, (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids);
    }
  }
  else
  {
    DestinationString = 0;
    v7 = (const WCHAR *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 1552))(
                          WdfDriverGlobals,
                          v72,
                          0);
    RtlInitUnicodeString(&DestinationString, v7);
    if ( RtlEqualUnicodeString(&DestinationString, &g_SystemContainerId, 1u) )
      *(_DWORD *)(v4 + 44) |= 0x100u;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1664))(WdfDriverGlobals, v72);
  }
  if ( !*(_BYTE *)(v4 + 240) )
  {
    if ( (*(_DWORD *)(v4 + 44) & 0x100) != 0 )
      goto LABEL_15;
    goto LABEL_14;
  }
  v8 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 24) + 64LL) + 24LL);
  if ( (*(_DWORD *)(*(_QWORD *)(v8 + 8) + 204LL) & 0x800) != 0 && ((*(_DWORD *)(v8 + 2732) - 2) & 0xFFFFFFFD) == 0 )
LABEL_14:
    _InterlockedOr((volatile signed __int32 *)(v4 + 2512), 1u);
LABEL_15:
  KeResetEvent((PRKEVENT)(v4 + 1168));
  HUBSM_AddHsmEvent(v4, 2031);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, v4);
  HUBMISC_WaitForSignal((PVOID)(v4 + 1168));
  v9 = *(_DWORD *)(v4 + 1192);
  AcpiPortAttributes = v9;
  if ( v9 < 0 )
    goto LABEL_42;
  if ( (*(_DWORD *)(v4 + 40) & 0x800000) != 0 )
    HUBFDO_SetFriendlyNameForBlockedHub(v4);
  RtlInitUnicodeString(&SourceString, 0);
  HUBPARENT_GetHubSymbolicLinkName(v4);
  if ( !SourceString.Length )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_(*(_QWORD *)(v4 + 2536), v10, 3, 42, (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids);
    }
    v9 = -1073741823;
LABEL_22:
    AcpiPortAttributes = v9;
    goto LABEL_42;
  }
  Pool2 = ExAllocatePool2(64, 2LL * SourceString.Length, 1748191317);
  *(_QWORD *)(v4 + 2568) = Pool2;
  if ( !Pool2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_(*(_QWORD *)(v4 + 2536), v12, 3, 43, (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids);
    }
    v9 = -1073741670;
    goto LABEL_22;
  }
  *(_WORD *)(v4 + 2560) = 0;
  *(_WORD *)(v4 + 2562) = SourceString.Length;
  RtlCopyUnicodeString((PUNICODE_STRING)(v4 + 2560), &SourceString);
  AcpiPortAttributes = HUBACPI_GetAcpiPortAttributes(v4);
  v9 = AcpiPortAttributes;
  if ( AcpiPortAttributes >= 0 )
  {
    HUBCONNECTOR_MapHubPorts(v4);
    HUBFDO_MapDvsecUsb4Hosts((_QWORD *)v4);
    v14 = HUBFDO_AssignUsb4PortMappingProperty(v4);
    if ( v14 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v54) = v14;
      LOBYTE(v15) = 2;
      WPP_RECORDER_SF_d(*(_QWORD *)(v4 + 2536), v15, 3, 45, (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids);
    }
    WMI_RegisterHub(a1);
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(v4 + 560))(*(_QWORD *)(v4 + 248)) )
      _InterlockedOr((volatile signed __int32 *)(v4 + 776), 1u);
    if ( *(_BYTE *)(v4 + 2744) == 1 )
    {
      if ( *(_BYTE *)(v4 + 240) )
      {
        if ( *(_DWORD *)(v4 + 160) )
        {
          if ( !*(_QWORD *)(v4 + 2672) )
          {
            FirmwareUpdateDevice = FWUPDATE_CreateFirmwareUpdateDevice(v4);
            if ( FirmwareUpdateDevice < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LODWORD(v54) = FirmwareUpdateDevice;
              LOBYTE(v17) = 2;
              WPP_RECORDER_SF_d(
                *(_QWORD *)(v4 + 2536),
                v17,
                2,
                46,
                (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids);
            }
          }
        }
      }
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v13) = 2;
    WPP_RECORDER_SF_(*(_QWORD *)(v4 + 2536), v13, 3, 44, (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids);
  }
LABEL_42:
  v18 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
          WdfDriverGlobals,
          WdfDriverGlobals->Driver,
          off_14006B2C0);
  v75 = v18;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 2504))(
    WdfDriverGlobals,
    *(_QWORD *)(v18 + 32),
    0);
  if ( (*(_DWORD *)(v18 + 4) & 0x1000) != 0 && v9 >= 0 )
  {
    if ( *(_DWORD *)(v4 + 2232) == 1 )
    {
      if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 2) != 0 )
        McTemplateK0pnq_EtwWriteTransfer(
          v4 + 1196,
          (unsigned int)USBHUB3_ETW_EVENT_HUB_PREPARE_HARDWARE_USB20_HUB_INFORMATION,
          0,
          *(_QWORD *)(v4 + 248),
          71,
          v4 + 1196,
          *(_DWORD *)(v4 + 2616));
    }
    else
    {
      v19 = (unsigned int)(*(_DWORD *)(v4 + 2232) - 2);
      if ( *(_DWORD *)(v4 + 2232) == 2 )
      {
        if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 2) != 0 )
          McTemplateK0pnq_EtwWriteTransfer(
            v4 + 1196,
            (unsigned int)USBHUB3_ETW_EVENT_HUB_PREPARE_HARDWARE_USB30_HUB_INFORMATION,
            0,
            *(_QWORD *)(v4 + 248),
            12,
            v4 + 1196,
            *(_DWORD *)(v4 + 2616));
      }
      else if ( *(_DWORD *)(v4 + 2232) == 4 )
      {
        if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 2) != 0 )
          McTemplateK0pq_EtwWriteTransfer(
            v19,
            USBHUB3_ETW_EVENT_HUB_PREPARE_HARDWARE_ROOT_HUB_INFORMATION,
            0,
            *(_QWORD *)(v4 + 248),
            *(_DWORD *)(v4 + 2616));
      }
      else if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 0x20) != 0 )
      {
        McTemplateK0p_EtwWriteTransfer(
          v19,
          USBHUB3_ETW_EVENT_HUB_PREPARE_HARDWARE_UNKNOWN_HUB_TYPE,
          0,
          *(_QWORD *)(v4 + 248));
      }
    }
    v20 = v4 + 2376;
    v21 = *(_QWORD *)(v4 + 2376);
    v22 = v21 - 248;
    if ( v4 + 2376 != v21 )
    {
      while ( 1 )
      {
        v23 = *(_DWORD *)(v22 + 204);
        if ( (v23 & 2) != 0 )
        {
          v24 = 1;
          if ( (v23 & 0x1000) != 0 && (*(_DWORD *)(v4 + 44) & 0x200) != 0 )
          {
            v25 = 1;
            goto LABEL_62;
          }
        }
        else
        {
          v24 = 0;
        }
        v25 = 0;
LABEL_62:
        v26 = *(_DWORD *)(v22 + 1256);
        v58 = v25;
        if ( v26 == 3000 )
        {
          if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 2) == 0 )
            goto LABEL_91;
          v36 = *(_DWORD *)(v4 + 168);
          if ( v36 == 2 )
          {
            v37 = v4 + 186;
            v38 = v4 + 181;
            v39 = v4 + 176;
            goto LABEL_80;
          }
          v37 = 0;
          v38 = 0;
          v39 = 0;
          if ( v36 == 1 )
          {
            v70 = *(_WORD *)(v4 + 184);
            v68 = *(_DWORD *)(v4 + 180);
            v66 = *(_DWORD *)(v4 + 176);
            v64 = *(_DWORD *)(v4 + 196);
            v62 = *(_DWORD *)(v4 + 192);
            v60 = *(_DWORD *)(v4 + 188);
          }
          else
          {
LABEL_80:
            LOBYTE(v70) = 0;
            LOBYTE(v68) = -1;
            LOBYTE(v66) = -1;
            LOBYTE(v64) = 0;
            LOBYTE(v62) = 0;
            LOBYTE(v60) = 0;
          }
          if ( v25 )
          {
            v40 = (*(_DWORD *)(v22 + 1344) & 0x10) != 0;
            v41 = (*(_DWORD *)(v22 + 1344) & 4) != 0;
            v42 = (*(_DWORD *)(v22 + 1344) & 0x20) != 0;
            v43 = (*(_DWORD *)(v22 + 1344) & 8) != 0;
            v57 = 1;
            v77 = *(_BYTE *)(v22 + 1344) & 3;
          }
          else
          {
            v57 = 0;
            v40 = 0;
            v41 = 0;
            v77 = 0;
            v42 = 0;
            v43 = 0;
          }
          if ( v24 )
            v44 = *(_BYTE *)(v22 + 1341);
          else
            v44 = 0;
          McTemplateK0pquuuuuuuuxqqqqqqqsss_EtwWriteTransfer(
            *(unsigned __int16 *)(v22 + 200),
            (unsigned int)USBHUB3_ETW_EVENT_HUB_PREPARE_HARDWARE_20_PORT_V2,
            0,
            *(_QWORD *)(v4 + 248),
            *(_WORD *)(v22 + 200),
            v24,
            v44,
            v57,
            v40,
            v41,
            v42,
            v43,
            v77,
            *(_QWORD *)(v22 + 1416),
            v36,
            v60,
            v62,
            v64,
            v66,
            v68,
            v70,
            v39,
            v38,
            v37);
          goto LABEL_90;
        }
        if ( v26 != 5000 || (Microsoft_Windows_USB_USBHUB3EnableBits & 2) == 0 )
          goto LABEL_91;
        v27 = *(_DWORD *)(v4 + 168);
        if ( v27 == 2 )
        {
          v28 = v4 + 186;
          v29 = v4 + 181;
          v30 = v4 + 176;
        }
        else
        {
          v28 = 0;
          v29 = 0;
          v30 = 0;
          if ( v27 == 1 )
          {
            v59 = *(_WORD *)(v4 + 184);
            v61 = *(_DWORD *)(v4 + 180);
            v63 = *(_DWORD *)(v4 + 176);
            v65 = *(_DWORD *)(v4 + 196);
            v67 = *(_DWORD *)(v4 + 192);
            v69 = *(_DWORD *)(v4 + 188);
            goto LABEL_68;
          }
        }
        LOBYTE(v59) = 0;
        LOBYTE(v61) = -1;
        LOBYTE(v63) = -1;
        LOBYTE(v65) = 0;
        LOBYTE(v67) = 0;
        LOBYTE(v69) = 0;
LABEL_68:
        if ( v25 )
        {
          v31 = (*(_DWORD *)(v22 + 1344) & 0x10) != 0;
          v32 = (*(_DWORD *)(v22 + 1344) & 4) != 0;
          v33 = (*(_DWORD *)(v22 + 1344) & 0x20) != 0;
          v34 = (*(_DWORD *)(v22 + 1344) & 8) != 0;
          v56 = 1;
          v76 = *(_BYTE *)(v22 + 1344) & 3;
        }
        else
        {
          v56 = 0;
          v31 = 0;
          v32 = 0;
          v76 = 0;
          v33 = 0;
          v34 = 0;
        }
        if ( v24 )
          v35 = *(_BYTE *)(v22 + 1341);
        else
          v35 = 0;
        McTemplateK0pquuuuuuuuxqqqqqqqsss_EtwWriteTransfer(
          *(unsigned __int16 *)(v22 + 200),
          (unsigned int)USBHUB3_ETW_EVENT_HUB_PREPARE_HARDWARE_30_PORT_V2,
          0,
          *(_QWORD *)(v4 + 248),
          *(_WORD *)(v22 + 200),
          v24,
          v35,
          v56,
          v31,
          v32,
          v33,
          v34,
          v76,
          *(_QWORD *)(v22 + 1416),
          v27,
          v69,
          v67,
          v65,
          v63,
          v61,
          v59,
          v30,
          v29,
          v28);
LABEL_90:
        v20 = v4 + 2376;
LABEL_91:
        if ( v24 && (Microsoft_Windows_USB_USBHUB3EnableBits & 2) != 0 )
          McTemplateK0pqun_EtwWriteTransfer(
            *(unsigned __int16 *)(v22 + 200),
            (unsigned int)USBHUB3_ETW_EVENT_HUB_PREPARE_HARDWARE_ACPI_UPC_V1,
            0,
            *(_QWORD *)(v4 + 248),
            *(_WORD *)(v22 + 200),
            v58,
            v55,
            v22 + 1340);
        if ( (*(_DWORD *)(v22 + 204) & 4) != 0 && (Microsoft_Windows_USB_USBHUB3EnableBits & 2) != 0 )
          McTemplateK0pqn_EtwWriteTransfer(
            *(unsigned __int16 *)(v22 + 200),
            (unsigned int)USBHUB3_ETW_EVENT_HUB_PREPARE_HARDWARE_ACPI_PLD,
            0,
            *(_QWORD *)(v4 + 248),
            *(_WORD *)(v22 + 200),
            (_DWORD)v54,
            v22 + 1352);
        if ( (*(_DWORD *)(v22 + 204) & 0x800) != 0 )
        {
          v45 = *(_QWORD *)(v22 + 1464);
          DestinationString = 0;
          (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *))(WdfFunctions_01015 + 2472))(
            WdfDriverGlobals,
            v45,
            &DestinationString);
          v46 = (void *)ExAllocatePool2(64, DestinationString.Length + 2LL, 1681082453);
          v47 = v46;
          if ( v46 )
          {
            memmove(v46, DestinationString.Buffer, DestinationString.Length);
            if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 1) != 0 )
              McTemplateK0pqz_EtwWriteTransfer(
                *(unsigned __int16 *)(v22 + 200),
                (unsigned int)USBHUB3_ETW_EVENT_HUB_PREPARE_HARDWARE_ACPI_DSD_USB4,
                0,
                *(_QWORD *)(v4 + 248),
                *(_WORD *)(v22 + 200),
                (__int64)v47);
            ExFreePoolWithTag(v47, 0x64334855u);
          }
        }
        v48 = *(_QWORD *)(v22 + 248);
        v22 = v48 - 248;
        if ( v20 == v48 )
        {
          v9 = AcpiPortAttributes;
          v18 = v75;
          break;
        }
      }
    }
  }
  v49 = *(_QWORD **)(v18 + 24);
  if ( *v49 != v18 + 16 )
    __fastfail(3u);
  *(_QWORD *)(v4 + 2448) = v18 + 16;
  *(_QWORD *)(v4 + 2456) = v49;
  *v49 = v4 + 2448;
  *(_QWORD *)(v18 + 24) = v4 + 2448;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2512))(
    WdfDriverGlobals,
    *(_QWORD *)(v18 + 32));
  if ( v9 >= 0 )
  {
    v52 = HUBFDO_RegisterSleepstudyBlockerReasons(*(_QWORD *)(v4 + 24), v4);
    if ( v52 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v54) = v52;
      LOBYTE(v50) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(v4 + 2536),
        v50,
        2,
        47,
        (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids,
        v54);
    }
  }
  if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 2) != 0 )
    McTemplateK0pq_EtwWriteTransfer(v51, USBHUB3_ETW_EVENT_HUB_PREPARE_HARDWARE_COMPLETE, 0, *(_QWORD *)(v4 + 248), v9);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v50) = 2;
    LODWORD(v54) = *(_DWORD *)(v4 + 40);
    WPP_RECORDER_SF_d(*(_QWORD *)(v4 + 2536), v50, 3, 48, (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids, v54);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140079940  push    rbp
0x140079942  push    rbx
0x140079943  push    rsi
0x140079944  push    rdi
0x140079945  push    r12
0x140079947  push    r13
0x140079949  push    r14
0x14007994b  push    r15
0x14007994d  lea     rbp, [rsp+28h]
0x140079952  sub     rsp, 118h
0x140079959  mov     rax, cs:WdfFunctions_01015
0x140079960  xorps   xmm0, xmm0
0x140079963  mov     r8, cs:off_14006B270
0x14007996a  mov     r14, rcx
0x14007996d  movups  xmmword ptr [rbp+10h+SourceString.Length], xmm0
0x140079971  mov     rdx, rcx
0x140079974  xor     r12d, r12d
0x140079977  mov     rcx, cs:WdfDriverGlobals
0x14007997e  mov     [rbp+10h+var_70], r12
0x140079982  mov     rax, [rax+650h]
0x140079989  call    _guard_dispatch_icall
0x14007998e  test    cs:Microsoft_Windows_USB_USBHUB3EnableBits, 2
0x140079995  mov     rdi, rax
0x140079998  jz      short loc_1400799B0
0x14007999a  mov     r9, [rax+0F8h]
0x1400799a1  lea     rdx, USBHUB3_ETW_EVENT_HUB_PREPARE_HARDWARE_START
0x1400799a8  xor     r8d, r8d
0x1400799ab  call    McTemplateK0p_EtwWriteTransfer
0x1400799b0  mov     rcx, rdi
0x1400799b3  call    HUBREG_QueryValuesInHubHardwareKey
0x1400799b8  mov     rcx, rdi
0x1400799bb  call    HUBREG_ReadUsb4HostNameStringFromDeviceHardwareKey
0x1400799c0  mov     rax, cs:WdfFunctions_01015
0x1400799c7  lea     rcx, [rbp+10h+var_70]
0x1400799cb  mov     [rsp+150h+var_128], rcx
0x1400799d0  mov     r15d, 1
0x1400799d6  mov     rcx, cs:WdfDriverGlobals
0x1400799dd  mov     r9d, r15d
0x1400799e0  mov     rdx, r14
0x1400799e3  mov     [rsp+150h+var_130], r12
0x1400799e8  mov     rax, [rax+290h]
0x1400799ef  lea     r8d, [r15+15h]
0x1400799f3  call    _guard_dispatch_icall
0x1400799f8  lea     rcx, WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids
0x1400799ff  mov     ebx, 100h
0x140079a04  lea     r13, WPP_RECORDER_INITIALIZED
0x140079a0b  test    eax, eax
0x140079a0d  js      short loc_140079A8B
0x140079a0f  mov     rax, cs:WdfFunctions_01015
0x140079a16  xorps   xmm0, xmm0
0x140079a19  mov     rdx, [rbp+10h+var_70]
0x140079a1d  xor     r8d, r8d
0x140079a20  mov     rcx, cs:WdfDriverGlobals
0x140079a27  movups  xmmword ptr [rbp+10h+DestinationString.Length], xmm0
0x140079a2b  mov     rax, [rax+610h]
0x140079a32  call    _guard_dispatch_icall
0x140079a37  mov     rdx, rax; SourceString
0x140079a3a  lea     rcx, [rbp+10h+DestinationString]; DestinationString
0x140079a3e  call    cs:__imp_RtlInitUnicodeString
0x140079a45  nop     dword ptr [rax+rax+00h]
0x140079a4a  mov     r8b, r15b; CaseInSensitive
0x140079a4d  lea     rdx, g_SystemContainerId; String2
0x140079a54  lea     rcx, [rbp+10h+DestinationString]; String1
0x140079a58  call    cs:__imp_RtlEqualUnicodeString
0x140079a5f  nop     dword ptr [rax+rax+00h]
0x140079a64  test    al, al
0x140079a66  jz      short loc_140079A6B
0x140079a68  or      [rdi+2Ch], ebx
0x140079a6b  mov     rax, cs:WdfFunctions_01015
0x140079a72  mov     rdx, [rbp+10h+var_70]
0x140079a76  mov     rcx, cs:WdfDriverGlobals
0x140079a7d  mov     rax, [rax+680h]
0x140079a84  call    _guard_dispatch_icall
0x140079a89  jmp     short loc_140079AB5
0x140079a8b  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140079a92  jz      short loc_140079AB5
0x140079a94  mov     r9d, 29h ; ')'
0x140079a9a  mov     dword ptr [rsp+150h+var_128], eax
0x140079a9e  mov     [rsp+150h+var_130], rcx
0x140079aa3  mov     dl, 2
0x140079aa5  mov     rcx, [rdi+9E8h]
0x140079aac  lea     r8d, [r9-26h]
0x140079ab0  call    WPP_RECORDER_SF_d
0x140079ab5  cmp     [rdi+0F0h], r12b
0x140079abc  jz      short loc_140079AEC
0x140079abe  mov     rax, [rdi+18h]
0x140079ac2  mov     rcx, [rax+40h]
0x140079ac6  mov     rdx, [rcx+18h]
0x140079aca  mov     rax, [rdx+8]
0x140079ace  test    dword ptr [rax+0CCh], 800h
0x140079ad8  jz      short loc_140079AF9
0x140079ada  mov     eax, [rdx+0AACh]
0x140079ae0  sub     eax, 2
0x140079ae3  test    eax, 0FFFFFFFDh
0x140079ae8  jz      short loc_140079AF1
0x140079aea  jmp     short loc_140079AF9
0x140079aec  test    [rdi+2Ch], ebx
0x140079aef  jnz     short loc_140079AF9
0x140079af1  lock or [rdi+9D0h], r15d
0x140079af9  lea     rbx, [rdi+490h]
0x140079b00  mov     rcx, rbx; Event
0x140079b03  call    cs:__imp_KeResetEvent
0x140079b0a  nop     dword ptr [rax+rax+00h]
0x140079b0f  mov     edx, 7EFh
0x140079b14  mov     rcx, rdi
0x140079b17  call    HUBSM_AddHsmEvent
0x140079b1c  mov     rax, cs:WdfFunctions_01015
0x140079b23  mov     rdx, rdi
0x140079b26  mov     rcx, cs:WdfDriverGlobals
0x140079b2d  mov     rax, [rax+660h]
0x140079b34  call    _guard_dispatch_icall
0x140079b39  mov     r8, rax
0x140079b3c  lea     rdx, aHubFdoPnpcallb; "Hub FDO PnpCallback"
0x140079b43  mov     rcx, rbx; Object
0x140079b46  call    HUBMISC_WaitForSignal
0x140079b4b  mov     esi, [rdi+4A8h]
0x140079b51  mov     [rbp+10h+var_74], esi
0x140079b54  test    esi, esi
0x140079b56  js      loc_140079D6E
0x140079b5c  test    dword ptr [rdi+28h], 800000h
0x140079b63  jz      short loc_140079B6D
0x140079b65  mov     rcx, rdi
0x140079b68  call    HUBFDO_SetFriendlyNameForBlockedHub
0x140079b6d  xor     edx, edx; SourceString
0x140079b6f  lea     rcx, [rbp+10h+SourceString]; DestinationString
0x140079b73  call    cs:__imp_RtlInitUnicodeString
0x140079b7a  nop     dword ptr [rax+rax+00h]
0x140079b7f  lea     rdx, [rbp+10h+SourceString]
0x140079b83  mov     rcx, rdi
0x140079b86  call    HUBPARENT_GetHubSymbolicLinkName
0x140079b8b  movzx   eax, [rbp+10h+SourceString.Length]
0x140079b8f  test    ax, ax
0x140079b92  jnz     short loc_140079BCE
0x140079b94  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140079b9b  jz      short loc_140079BC1
0x140079b9d  mov     rcx, [rdi+9E8h]
0x140079ba4  lea     rbx, WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids
0x140079bab  mov     r9d, 2Ah ; '*'
0x140079bb1  mov     [rsp+150h+var_130], rbx
0x140079bb6  mov     dl, 2
0x140079bb8  lea     r8d, [r9-27h]
0x140079bbc  call    WPP_RECORDER_SF_
0x140079bc1  mov     esi, 0C0000001h
0x140079bc6  mov     [rbp+10h+var_74], esi
0x140079bc9  jmp     loc_140079D6E
0x140079bce  mov     rdx, rax
0x140079bd1  mov     ecx, 40h ; '@'
0x140079bd6  add     rdx, rdx
0x140079bd9  mov     r8d, 68334855h
0x140079bdf  call    cs:__imp_ExAllocatePool2
0x140079be6  nop     dword ptr [rax+rax+00h]
0x140079beb  mov     [rdi+0A08h], rax
0x140079bf2  test    rax, rax
0x140079bf5  jnz     short loc_140079C29
0x140079bf7  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140079bfe  jz      short loc_140079C22
0x140079c00  mov     rcx, [rdi+9E8h]
0x140079c07  lea     rbx, WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids
0x140079c0e  lea     r9d, [rax+2Bh]
0x140079c12  mov     [rsp+150h+var_130], rbx
0x140079c17  lea     r8d, [rax+3]
0x140079c1b  mov     dl, 2
0x140079c1d  call    WPP_RECORDER_SF_
0x140079c22  mov     esi, 0C000009Ah
0x140079c27  jmp     short loc_140079BC6
0x140079c29  lea     rcx, [rdi+0A00h]; DestinationString
0x140079c30  mov     [rcx], r12w
0x140079c34  lea     rdx, [rbp+10h+SourceString]; SourceString
0x140079c38  movzx   eax, [rbp+10h+SourceString.Length]
0x140079c3c  mov     [rdi+0A02h], ax
0x140079c43  call    cs:__imp_RtlCopyUnicodeString
0x140079c4a  nop     dword ptr [rax+rax+00h]
0x140079c4f  mov     rcx, rdi
0x140079c52  call    HUBACPI_GetAcpiPortAttributes
0x140079c57  mov     [rbp+10h+var_74], eax
0x140079c5a  mov     esi, eax
0x140079c5c  test    eax, eax
0x140079c5e  jns     short loc_140079C96
0x140079c60  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140079c67  jz      loc_140079D6E
0x140079c6d  mov     rcx, [rdi+9E8h]
0x140079c74  lea     rbx, WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids
0x140079c7b  mov     r9d, 2Ch ; ','
0x140079c81  mov     [rsp+150h+var_130], rbx
0x140079c86  mov     dl, 2
0x140079c88  lea     r8d, [r9-29h]
0x140079c8c  call    WPP_RECORDER_SF_
0x140079c91  jmp     loc_140079D6E
0x140079c96  mov     rcx, rdi
0x140079c99  call    HUBCONNECTOR_MapHubPorts
0x140079c9e  mov     rcx, rdi
0x140079ca1  call    HUBFDO_MapDvsecUsb4Hosts
0x140079ca6  mov     rcx, rdi
0x140079ca9  call    HUBFDO_AssignUsb4PortMappingProperty
0x140079cae  test    eax, eax
0x140079cb0  jns     short loc_140079CE5
0x140079cb2  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140079cb9  lea     rbx, WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids
0x140079cc0  jz      short loc_140079CEC
0x140079cc2  mov     rcx, [rdi+9E8h]
0x140079cc9  mov     r9d, 2Dh ; '-'
0x140079ccf  mov     dword ptr [rsp+150h+var_128], eax
0x140079cd3  mov     dl, 2
0x140079cd5  mov     [rsp+150h+var_130], rbx
0x140079cda  lea     r8d, [r9-2Ah]
0x140079cde  call    WPP_RECORDER_SF_d
0x140079ce3  jmp     short loc_140079CEC
0x140079ce5  lea     rbx, WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids
0x140079cec  mov     rcx, r14
0x140079cef  call    WMI_RegisterHub
0x140079cf4  mov     rax, [rdi+230h]
0x140079cfb  mov     rcx, [rdi+0F8h]
0x140079d02  call    _guard_dispatch_icall
0x140079d07  test    al, al
0x140079d09  jz      short loc_140079D13
0x140079d0b  lock or [rdi+308h], r15d
0x140079d13  cmp     [rdi+0AB8h], r15b
0x140079d1a  jnz     short loc_140079D6E
0x140079d1c  cmp     [rdi+0F0h], r12b
0x140079d23  jz      short loc_140079D6E
0x140079d25  cmp     [rdi+0A0h], r12d
0x140079d2c  jz      short loc_140079D6E
0x140079d2e  cmp     [rdi+0A70h], r12
0x140079d35  jnz     short loc_140079D6E
0x140079d37  mov     rcx, rdi
0x140079d3a  call    FWUPDATE_CreateFirmwareUpdateDevice
0x140079d3f  test    eax, eax
0x140079d41  jns     short loc_140079D6E
0x140079d43  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140079d4a  jz      short loc_140079D6E
0x140079d4c  mov     rcx, [rdi+9E8h]
0x140079d53  mov     r9d, 2Eh ; '.'
0x140079d59  mov     dword ptr [rsp+150h+var_128], eax
0x140079d5d  mov     [rsp+150h+var_130], rbx
0x140079d62  lea     r8d, [r9-2Ch]
0x140079d66  mov     dl, r8b
0x140079d69  call    WPP_RECORDER_SF_d
0x140079d6e  mov     rax, cs:WdfFunctions_01015
0x140079d75  mov     rcx, cs:WdfDriverGlobals
0x140079d7c  mov     r8, cs:off_14006B2C0
0x140079d83  mov     rax, [rax+650h]
0x140079d8a  mov     rdx, [rcx]
0x140079d8d  call    _guard_dispatch_icall
0x140079d92  mov     rcx, cs:WdfFunctions_01015
0x140079d99  mov     r14, rax
0x140079d9c  mov     [rbp+10h+var_48], rax
0x140079da0  xor     r8d, r8d
0x140079da3  mov     rax, [rcx+9C8h]
0x140079daa  mov     rcx, cs:WdfDriverGlobals
0x140079db1  mov     rdx, [r14+20h]
0x140079db5  call    _guard_dispatch_icall
0x140079dba  test    dword ptr [r14+4], 1000h
0x140079dc2  jz      loc_14007A3DC
0x140079dc8  test    esi, esi
0x140079dca  js      loc_14007A3DC
0x140079dd0  mov     ecx, [rdi+8B8h]
0x140079dd6  sub     ecx, r15d
0x140079dd9  jz      loc_140079E70
0x140079ddf  sub     ecx, r15d
0x140079de2  jz      short loc_140079E40
0x140079de4  cmp     ecx, 2
0x140079de7  jz      short loc_140079E11
0x140079de9  test    cs:Microsoft_Windows_USB_USBHUB3EnableBits, 20h
0x140079df0  jz      loc_140079EAD
0x140079df6  mov     r9, [rdi+0F8h]
0x140079dfd  lea     rdx, USBHUB3_ETW_EVENT_HUB_PREPARE_HARDWARE_UNKNOWN_HUB_TYPE
0x140079e04  xor     r8d, r8d
0x140079e07  call    McTemplateK0p_EtwWriteTransfer
0x140079e0c  jmp     loc_140079EAD
0x140079e11  test    cs:Microsoft_Windows_USB_USBHUB3EnableBits, 2
0x140079e18  jz      loc_140079EAD
0x140079e1e  mov     eax, [rdi+0A38h]
0x140079e24  lea     rdx, USBHUB3_ETW_EVENT_HUB_PREPARE_HARDWARE_ROOT_HUB_INFORMATION
0x140079e2b  mov     r9, [rdi+0F8h]
0x140079e32  xor     r8d, r8d
0x140079e35  mov     dword ptr [rsp+150h+var_130], eax
0x140079e39  call    McTemplateK0pq_EtwWriteTransfer
0x140079e3e  jmp     short loc_140079EAD
0x140079e40  test    cs:Microsoft_Windows_USB_USBHUB3EnableBits, 2
0x140079e47  jz      short loc_140079EAD
0x140079e49  mov     eax, [rdi+0A38h]
0x140079e4f  lea     rcx, [rdi+4ACh]
0x140079e56  mov     dword ptr [rsp+150h+var_120], eax
0x140079e5a  lea     rdx, USBHUB3_ETW_EVENT_HUB_PREPARE_HARDWARE_USB30_HUB_INFORMATION
0x140079e61  mov     [rsp+150h+var_128], rcx
0x140079e66  mov     dword ptr [rsp+150h+var_130], 0Ch
0x140079e6e  jmp     short loc_140079E9E
0x140079e70  test    cs:Microsoft_Windows_USB_USBHUB3EnableBits, 2
0x140079e77  jz      short loc_140079EAD
0x140079e79  mov     eax, [rdi+0A38h]
0x140079e7f  lea     rcx, [rdi+4ACh]
0x140079e86  mov     dword ptr [rsp+150h+var_120], eax
0x140079e8a  lea     rdx, USBHUB3_ETW_EVENT_HUB_PREPARE_HARDWARE_USB20_HUB_INFORMATION
0x140079e91  mov     [rsp+150h+var_128], rcx
0x140079e96  mov     dword ptr [rsp+150h+var_130], 47h ; 'G'
0x140079e9e  mov     r9, [rdi+0F8h]
0x140079ea5  xor     r8d, r8d
0x140079ea8  call    McTemplateK0pnq_EtwWriteTransfer
0x140079ead  lea     r15, [rdi+948h]
0x140079eb4  mov     rax, [r15]
  ... truncated ...
```
