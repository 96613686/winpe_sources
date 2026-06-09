# HUBDTX_ControlTransferComplete

- ea: `0x140029c90`
- end: `0x14002a86d`
- name: `HUBDTX_ControlTransferComplete`
- size: `3037`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400024b8`
- `0x1400025a4`
- `0x140006644`
- `0x140007080`
- `0x14000a53c`
- `0x140029c90`
- `0x140033530`
- `0x140045570`

## pseudocode

```c
__int64 __fastcall HUBDTX_ControlTransferComplete(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v4; // eax
  int v5; // edi
  __int64 v6; // rbx
  int v7; // esi
  unsigned __int8 *v9; // r14
  char v10; // al
  int v11; // eax
  int v12; // ecx
  int v13; // ecx
  unsigned int v14; // ebp
  __int16 v15; // ax
  char v16; // al
  bool v17; // zf
  int v18; // r9d
  char v19; // al
  char v20; // al
  char v21; // al
  __int64 v22; // rax
  char v23; // dl
  char v24; // al
  __int64 *v25; // rdx
  bool v26; // zf
  int v27; // eax
  char v28; // di
  __int64 v29; // rax
  int v30; // edx
  __int64 v32; // [rsp+50h] [rbp-68h] BYREF
  int v33; // [rsp+58h] [rbp-60h]
  __int64 v34; // [rsp+5Ch] [rbp-5Ch]
  int v35; // [rsp+64h] [rbp-54h]

  v4 = *(_DWORD *)(a4 + 316);
  v5 = *(_DWORD *)(a3 + 8);
  v6 = a4;
  v7 = *(_DWORD *)(a4 + 284);
  v9 = *(unsigned __int8 **)(a4 + 2656);
  *(_DWORD *)(a4 + 416) = 0;
  *(_DWORD *)(a4 + 264) = v4;
  v10 = *(_BYTE *)(a4 + 408);
  if ( (v10 & 0x63) == 0 && v10 < 0 && *(_BYTE *)(a4 + 409) == 26 && *(_WORD *)(a4 + 410) == 1 )
  {
    *(_DWORD *)(a4 + 2724) = v5;
    *(_DWORD *)(a4 + 2728) = v7;
    *(_OWORD *)(a4 + 1740) = 0;
    *(_OWORD *)(a4 + 1756) = 0;
  }
  if ( v5 >= 0 )
  {
    v14 = 4012;
    goto LABEL_151;
  }
  LOBYTE(a4) = 96;
  if ( *(_BYTE *)(v6 + 409) == 9 && *(_WORD *)(v6 + 410) && (*(_BYTE *)(v6 + 408) & 0x60) == 0 )
  {
    v11 = -1073733632;
    v12 = -1073741823;
  }
  else
  {
    v11 = v7;
    v12 = v5;
  }
  *(_DWORD *)(v6 + 1568) = v12;
  *(_DWORD *)(v6 + 1572) = v11;
  v13 = *(unsigned __int8 *)(v6 + 409);
  if ( (_BYTE)v13 == 48 && (*(_BYTE *)(v6 + 408) & 0x60) == 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_dD(
        *(_QWORD *)(*(_QWORD *)(v6 + 8) + 1432LL),
        2,
        5,
        10,
        (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
        v5,
        v7);
    if ( (*(_DWORD *)(v6 + 2444) & 4) != 0 )
      HUBMISC_VerifierDbgBreak("DeviceHwVerifierSetSelFailure", v6 + 512);
    *(_DWORD *)(v6 + 2440) = 1073807370;
    if ( (byte_14006ED41 & 1) != 0 )
      McTemplateK0pqqq_EtwWriteTransfer(
        v13,
        (unsigned int)USBHUB3_ETW_EVENT_SET_SEL_FAILURE,
        v6 + 1524,
        *(_QWORD *)(v6 + 24),
        0,
        v7,
        v5);
    v14 = 4008;
    if ( v7 != -1073741820 )
      v14 = 4004;
    goto LABEL_148;
  }
  v14 = 4004;
  if ( (_BYTE)v13 == 3 )
  {
    v15 = *(_WORD *)(v6 + 410);
    if ( v15 == 48 )
    {
      if ( (*(_BYTE *)(v6 + 408) & 0x60) == 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_dD(
            *(_QWORD *)(*(_QWORD *)(v6 + 8) + 1432LL),
            2,
            5,
            11,
            (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
            v5,
            v7);
        if ( (*(_DWORD *)(v6 + 2444) & 0x2000) != 0 )
          HUBMISC_VerifierDbgBreak("DeviceHwVerifierSetU1EnableFailure", v6 + 512);
        if ( (byte_14006ED41 & 1) != 0 )
          McTemplateK0pqqq_EtwWriteTransfer(
            v13,
            (unsigned int)USBHUB3_ETW_EVENT_SET_U1_ENABLE_FAILURE,
            v6 + 1524,
            *(_QWORD *)(v6 + 24),
            0,
            v7,
            v5);
        goto LABEL_148;
      }
    }
    else if ( v15 == 49 && (*(_BYTE *)(v6 + 408) & 0x60) == 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_dD(
          *(_QWORD *)(*(_QWORD *)(v6 + 8) + 1432LL),
          2,
          5,
          12,
          (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
          v5,
          v7);
      if ( (*(_DWORD *)(v6 + 2444) & 0x4000) != 0 )
        HUBMISC_VerifierDbgBreak("DeviceHwVerifierSetU2EnableFailure", v6 + 512);
      if ( (byte_14006ED41 & 1) != 0 )
        McTemplateK0pqqq_EtwWriteTransfer(
          v13,
          (unsigned int)USBHUB3_ETW_EVENT_SET_U2_ENABLE_FAILURE,
          v6 + 1524,
          *(_QWORD *)(v6 + 24),
          0,
          v7,
          v5);
      goto LABEL_148;
    }
  }
  else if ( (_BYTE)v13 == 6 && (*(_BYTE *)(v6 + 408) & 0x60) == 0 )
  {
    v16 = *(_BYTE *)(v6 + 411);
    if ( v16 == 3 )
      v17 = *(_BYTE *)(v6 + 410) == 0xEE;
    else
      v17 = v16 == 6;
    if ( !v17 && (*(_DWORD *)(v6 + 2444) & 1) != 0 )
      HUBMISC_VerifierDbgBreak("DeviceHwVerifierControlTransferFailure", v6 + 512);
    v13 = *(unsigned __int8 *)(v6 + 411) - 1;
    if ( *(_BYTE *)(v6 + 411) == 1 )
    {
      *(_DWORD *)(v6 + 2440) = 1073807360;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_dD(
          *(_QWORD *)(*(_QWORD *)(v6 + 8) + 1432LL),
          2,
          5,
          13,
          (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
          v5,
          v7);
      if ( (byte_14006ED41 & 1) != 0 )
        McTemplateK0pqqq_EtwWriteTransfer(
          v13,
          (unsigned int)USBHUB3_ETW_EVENT_DEVICE_DESCRIPTOR_FAILURE,
          v6 + 1524,
          *(_QWORD *)(v6 + 24),
          0,
          v7,
          v5);
      goto LABEL_148;
    }
    v13 = *(unsigned __int8 *)(v6 + 411) - 2;
    if ( *(_BYTE *)(v6 + 411) == 2 )
    {
      *(_DWORD *)(v6 + 2440) = 1073807367;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_dD(
          *(_QWORD *)(*(_QWORD *)(v6 + 8) + 1432LL),
          2,
          5,
          14,
          (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
          v5,
          v7);
      if ( (byte_14006ED41 & 1) != 0 )
        McTemplateK0pqqq_EtwWriteTransfer(
          v13,
          (unsigned int)USBHUB3_ETW_EVENT_CONFIG_DESCRIPTOR_FAILURE,
          v6 + 1524,
          *(_QWORD *)(v6 + 24),
          0,
          v7,
          v5);
      goto LABEL_148;
    }
    v13 = *(unsigned __int8 *)(v6 + 411) - 3;
    if ( *(_BYTE *)(v6 + 411) == 3 )
    {
      v19 = *(_BYTE *)(v6 + 2012);
      if ( v19 && v19 == *(_BYTE *)(v6 + 410) )
      {
        *(_DWORD *)(v6 + 2440) = 1073807373;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_dD(
            *(_QWORD *)(*(_QWORD *)(v6 + 8) + 1432LL),
            2,
            5,
            17,
            (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
            v5,
            v7);
        if ( (byte_14006ED41 & 1) != 0 )
          McTemplateK0pqqq_EtwWriteTransfer(
            v13,
            (unsigned int)USBHUB3_ETW_EVENT_SERIAL_NUMBER_STRING_FAILURE,
            v6 + 1524,
            *(_QWORD *)(v6 + 24),
            0,
            v7,
            v5);
      }
      else
      {
        LOBYTE(v13) = *(_BYTE *)(v6 + 410);
        if ( (_BYTE)v13 )
        {
          v20 = *(_BYTE *)(v6 + 2011);
          if ( v20 && v20 == (_BYTE)v13 )
          {
            *(_DWORD *)(v6 + 2440) = 1073807375;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_dD(
                *(_QWORD *)(*(_QWORD *)(v6 + 8) + 1432LL),
                2,
                5,
                19,
                (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
                v5,
                v7);
            if ( (byte_14006ED41 & 1) != 0 )
              McTemplateK0pqqq_EtwWriteTransfer(
                v13,
                (unsigned int)USBHUB3_ETW_EVENT_PRODUCT_ID_STRING_FAILURE,
                v6 + 1524,
                *(_QWORD *)(v6 + 24),
                0,
                v7,
                v5);
          }
          else if ( v9 )
          {
            v21 = *(_BYTE *)(*(_QWORD *)v9 + 3LL);
            if ( v21 && v21 == (_BYTE)v13 )
            {
              *(_DWORD *)(v6 + 2440) = 1073807375;
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                WPP_RECORDER_SF_dD(
                  *(_QWORD *)(*(_QWORD *)(v6 + 8) + 1432LL),
                  2,
                  5,
                  20,
                  (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
                  v5,
                  v7);
              if ( (byte_14006ED41 & 2) != 0 )
                McTemplateK0pqqq_EtwWriteTransfer(
                  v13,
                  (unsigned int)USBHUB3_ETW_EVENT_BILLBOARD_STRING_FAILURE,
                  v6 + 1524,
                  *(_QWORD *)(v6 + 24),
                  0,
                  v7,
                  v5);
            }
            else
            {
              v22 = v9[8];
              if ( (_BYTE)v22 != 0xFF )
              {
                v23 = *(_BYTE *)(*(_QWORD *)v9 + 4 * v22 + 47);
                if ( v23 )
                {
                  if ( v23 == (_BYTE)v13 )
                  {
                    *(_DWORD *)(v6 + 2440) = 1073807375;
                    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                      WPP_RECORDER_SF_dD(
                        *(_QWORD *)(*(_QWORD *)(v6 + 8) + 1432LL),
                        2,
                        5,
                        21,
                        (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
                        v5,
                        v7);
                    if ( (byte_14006ED41 & 2) != 0 )
                      McTemplateK0pqqq_EtwWriteTransfer(
                        v13,
                        (unsigned int)USBHUB3_ETW_EVENT_ALTERNATE_MODE_STRING_FAILURE,
                        v6 + 1524,
                        *(_QWORD *)(v6 + 24),
                        0,
                        v7,
                        v5);
                  }
                }
              }
            }
          }
        }
        else
        {
          *(_DWORD *)(v6 + 2440) = 1073807374;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_dD(
              *(_QWORD *)(*(_QWORD *)(v6 + 8) + 1432LL),
              2,
              5,
              18,
              (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
              v5,
              v7);
          if ( (byte_14006ED41 & 1) != 0 )
            McTemplateK0pqqq_EtwWriteTransfer(
              v13,
              (unsigned int)USBHUB3_ETW_EVENT_LANGUAGE_ID_STRING_FAILURE,
              v6 + 1524,
              *(_QWORD *)(v6 + 24),
              0,
              v7,
              v5);
        }
      }
      goto LABEL_148;
    }
    v13 = *(unsigned __int8 *)(v6 + 411) - 6;
    if ( *(_BYTE *)(v6 + 411) == 6 )
    {
      *(_DWORD *)(v6 + 2440) = 1073807372;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_dD(
          *(_QWORD *)(*(_QWORD *)(v6 + 8) + 1432LL),
          2,
          5,
          16,
          (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
          v5,
          v7);
      if ( (byte_14006ED41 & 1) != 0 )
        McTemplateK0pqqq_EtwWriteTransfer(
          v13,
          (unsigned int)USBHUB3_ETW_EVENT_DEVICE_QUALIFIER_DESCRIPTOR_FAILURE,
          v6 + 1524,
          *(_QWORD *)(v6 + 24),
          0,
          v7,
          v5);
      goto LABEL_148;
    }
    if ( *(_BYTE *)(v6 + 411) == 15 )
    {
      *(_DWORD *)(v6 + 2440) = 1073807371;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_dD(
          *(_QWORD *)(*(_QWORD *)(v6 + 8) + 1432LL),
          2,
          5,
          15,
          (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
          v5,
          v7);
      if ( (byte_14006ED41 & 1) != 0 )
        McTemplateK0pqqq_EtwWriteTransfer(
          v13,
          (unsigned int)USBHUB3_ETW_EVENT_BOS_DESCRIPTOR_FAILURE,
          v6 + 1524,
          *(_QWORD *)(v6 + 24),
          0,
          v7,
          v5);
      goto LABEL_148;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v18 = 22;
LABEL_55:
      WPP_RECORDER_SF_dD(
        *(_QWORD *)(*(_QWORD *)(v6 + 8) + 1432LL),
        2,
        5,
        v18,
        (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
        v5,
        v7);
    }
LABEL_148:
    if ( (byte_14006ED42 & 4) != 0 )
      McTemplateK0pqqq_EtwWriteTransfer(
        v13,
        (unsigned int)USBHUB3_ETW_EVENT_DEVICE_CONTROL_TRANSFER_ERROR,
        0,
        *(_QWORD *)(v6 + 24),
        0,
        v7,
        v5);
    goto LABEL_151;
  }
  v24 = *(_BYTE *)(v6 + 408) & 0x60;
  if ( v24 == 64 )
  {
    if ( (_BYTE)v13 == *(_BYTE *)(v6 + 2060) )
    {
      v13 = *(unsigned __int16 *)(v6 + 412) - 4;
      if ( *(_WORD *)(v6 + 412) == 4 )
      {
        *(_DWORD *)(v6 + 2440) = 1073807376;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_dD(
            *(_QWORD *)(*(_QWORD *)(v6 + 8) + 1432LL),
            2,
            5,
            23,
            (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
            v5,
            v7);
        if ( (byte_14006ED41 & 1) != 0 )
          McTemplateK0pqqq_EtwWriteTransfer(
            v13,
            (unsigned int)USBHUB3_ETW_EVENT_MS_EXT_CONFIG_DESCRIPTOR_FAILURE,
            v6 + 1524,
            *(_QWORD *)(v6 + 24),
            0,
            v7,
            v5);
        goto LABEL_148;
      }
      v13 = *(unsigned __int16 *)(v6 + 412) - 6;
      if ( *(_WORD *)(v6 + 412) == 6 )
      {
        *(_DWORD *)(v6 + 2440) = 1073807377;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_dD(
            *(_QWORD *)(*(_QWORD *)(v6 + 8) + 1432LL),
            2,
            5,
            24,
            (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
            v5,
            v7);
        if ( (byte_14006ED41 & 1) != 0 )
          McTemplateK0pqqq_EtwWriteTransfer(
            v13,
            (unsigned int)USBHUB3_ETW_EVENT_MS_CONTAINER_ID_DESCRIPTOR_FAILURE,
            v6 + 1524,
            *(_QWORD *)(v6 + 24),
            0,
            v7,
            v5);
        goto LABEL_148;
      }
      v13 = *(unsigned __int16 *)(v6 + 412) - 7;
      if ( *(_WORD *)(v6 + 412) == 7 )
      {
        *(_DWORD *)(v6 + 2440) = 1073807388;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_dD(
            *(_QWORD *)(*(_QWORD *)(v6 + 8) + 1432LL),
            2,
            5,
            25,
            (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
            v5,
            v7);
        if ( (byte_14006ED41 & 1) != 0 )
          McTemplateK0pqqq_EtwWriteTransfer(
            v13,
            (unsigned int)USBHUB3_ETW_EVENT_MSOS20_DESCRIPTOR_FAILURE,
            v6 + 1524,
            *(_QWORD *)(v6 + 24),
            0,
            v7,
            v5);
        goto LABEL_148;
      }
      if ( *(_WORD *)(v6 + 412) == 8 )
      {
        *(_DWORD *)(v6 + 2440) = 1073807390;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_dD(
            *(_QWORD *)(*(_QWORD *)(v6 + 8) + 1432LL),
            2,
            5,
            26,
            (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
            v5,
            v7);
        if ( (byte_14006ED41 & 2) != 0 )
          McTemplateK0pqqq_EtwWriteTransfer(
            v13,
            (unsigned int)USBHUB3_ETW_EVENT_MSOS20_SET_ALT_ENUMERATION_FAILURE,
            v6 + 1524,
            *(_QWORD *)(v6 + 24),
            0,
            v7,
            v5);
        goto LABEL_148;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v18 = 27;
        goto LABEL_55;
      }
      goto LABEL_148;
    }
  }
  else
  {
    if ( v24 )
      goto LABEL_141;
    if ( (_BYTE)v13 == 49 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_dD(
          *(_QWORD *)(*(_QWORD *)(v6 + 8) + 1432LL),
          2,
          5,
          28,
          (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
          v5,
          v7);
      if ( (*(_DWORD *)(v6 + 2444) & 8) != 0 )
        HUBMISC_VerifierDbgBreak("DeviceHwVerifierSetIsochDelayFailure", v6 + 512);
      if ( (byte_14006ED41 & 1) == 0 )
        goto LABEL_148;
      v25 = USBHUB3_ETW_EVENT_SET_ISOCH_DELAY_FAILURE;
      goto LABEL_147;
    }
    if ( (_BYTE)v13 == 1 )
    {
      v26 = *(_WORD *)(v6 + 410) == 1;
    }
    else
    {
      if ( (_BYTE)v13 != 3 || *(_WORD *)(v6 + 410) )
        goto LABEL_141;
      v26 = *(_WORD *)(v6 + 412) == 0;
    }
    if ( v26 )
      goto LABEL_148;
  }
LABEL_141:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_dDDD(
      *(_QWORD *)(*(_QWORD *)(v6 + 8) + 1432LL),
      (*(unsigned __int8 *)(v6 + 408) >> 5) & 3,
      5,
      29,
      (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
      v5,
      v7,
      (*(_BYTE *)(v6 + 408) >> 5) & 3,
      v13);
  if ( (*(_DWORD *)(v6 + 2444) & 1) != 0 )
    HUBMISC_VerifierDbgBreak("DeviceHwVerifierControlTransferFailure", v6 + 512);
  if ( (byte_14006ED42 & 4) != 0 )
  {
    v25 = USBHUB3_ETW_EVENT_DEVICE_CONTROL_TRANSFER_ERROR;
LABEL_147:
    McTemplateK0pqqq_EtwWriteTransfer(
      *(unsigned __int16 *)(*(_QWORD *)(v6 + 8) + 200LL),
      (_DWORD)v25,
      v6 + 1524,
      *(_QWORD *)(v6 + 24),
      *(_WORD *)(*(_QWORD *)(v6 + 8) + 200LL),
      v7,
      v5);
    goto LABEL_148;
  }
LABEL_151:
  v34 = 0;
  v35 = 0;
  v32 = 24;
  v33 = 0;
  v27 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *, __int64))(WdfFunctions_01015 + 1992))(
          WdfDriverGlobals,
          a1,
          &v32,
          a4);
  v28 = v27;
  if ( v27 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v29 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
            WdfDriverGlobals,
            WdfDriverGlobals->Driver,
            off_14006B2C0);
    LOBYTE(v30) = 2;
    WPP_RECORDER_SF_d(*(_QWORD *)(v29 + 64), v30, 2, 59, (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids, v28);
  }
  return HUBSM_AddEvent(v6 + 512, v14);
}

```

## disassembly

```asm
0x140029c90  push    rbx
0x140029c92  push    rbp
0x140029c93  push    rsi
0x140029c94  push    rdi
0x140029c95  push    r12
0x140029c97  push    r13
0x140029c99  push    r14
0x140029c9b  push    r15
0x140029c9d  sub     rsp, 78h
0x140029ca1  mov     eax, [r9+13Ch]
0x140029ca8  xor     r12d, r12d
0x140029cab  mov     edi, [r8+8]
0x140029caf  mov     rbx, r9
0x140029cb2  mov     esi, [r9+11Ch]
0x140029cb9  mov     r15, rcx
0x140029cbc  mov     r14, [r9+0A60h]
0x140029cc3  mov     r13w, 1
0x140029cc8  mov     [r9+1A0h], r12d
0x140029ccf  mov     [r9+108h], eax
0x140029cd6  mov     al, [r9+198h]
0x140029cdd  test    al, 63h
0x140029cdf  jnz     short loc_140029D1A
0x140029ce1  test    al, al
0x140029ce3  jns     short loc_140029D1A
0x140029ce5  cmp     byte ptr [r9+199h], 1Ah
0x140029ced  jnz     short loc_140029D1A
0x140029cef  cmp     [r9+19Ah], r13w
0x140029cf7  jnz     short loc_140029D1A
0x140029cf9  xorps   xmm0, xmm0
0x140029cfc  mov     [r9+0AA4h], edi
0x140029d03  mov     [r9+0AA8h], esi
0x140029d0a  movups  xmmword ptr [r9+6CCh], xmm0
0x140029d12  movups  xmmword ptr [r9+6DCh], xmm0
0x140029d1a  lea     r8, WPP_RECORDER_INITIALIZED
0x140029d21  test    edi, edi
0x140029d23  jns     loc_14002A7AE
0x140029d29  cmp     byte ptr [rbx+199h], 9
0x140029d30  mov     r9b, 60h ; '`'
0x140029d33  jnz     short loc_140029D54
0x140029d35  cmp     [rbx+19Ah], r12w
0x140029d3d  jz      short loc_140029D54
0x140029d3f  test    [rbx+198h], r9b
0x140029d46  jnz     short loc_140029D54
0x140029d48  mov     eax, 0C0002000h
0x140029d4d  mov     ecx, 0C0000001h
0x140029d52  jmp     short loc_140029D58
0x140029d54  mov     eax, esi
0x140029d56  mov     ecx, edi
0x140029d58  mov     [rbx+620h], ecx
0x140029d5e  mov     [rbx+624h], eax
0x140029d64  movzx   ecx, byte ptr [rbx+199h]
0x140029d6b  cmp     cl, 30h ; '0'
0x140029d6e  jnz     loc_140029E24
0x140029d74  test    [rbx+198h], r9b
0x140029d7b  jnz     loc_140029E24
0x140029d81  cmp     cs:WPP_RECORDER_INITIALIZED, r8; __annotation("TMF:",
0x140029d88  jz      short loc_140029DBA
0x140029d8a  mov     rcx, [rbx+8]
0x140029d8e  lea     rax, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x140029d95  mov     r9d, 0Ah
0x140029d9b  mov     [rsp+0B8h+var_88], esi
0x140029d9f  mov     [rsp+0B8h+var_90], edi
0x140029da3  mov     dl, 2
0x140029da5  mov     [rsp+0B8h+var_98], rax
0x140029daa  mov     rcx, [rcx+598h]
0x140029db1  lea     r8d, [r9-5]
0x140029db5  call    WPP_RECORDER_SF_dD
0x140029dba  mov     eax, [rbx+98Ch]
0x140029dc0  test    al, 4
0x140029dc2  jz      short loc_140029DD7
0x140029dc4  lea     rdx, [rbx+200h]
0x140029dcb  lea     rcx, aDevicehwverifi_12; "DeviceHwVerifierSetSelFailure"
0x140029dd2  call    HUBMISC_VerifierDbgBreak
0x140029dd7  mov     dword ptr [rbx+988h], 4001000Ah
0x140029de1  test    cs:byte_14006ED41, r13b
0x140029de8  jz      short loc_140029E0E
0x140029dea  mov     r9, [rbx+18h]
0x140029dee  lea     r8, [rbx+5F4h]
0x140029df5  mov     [rsp+0B8h+var_88], edi
0x140029df9  lea     rdx, USBHUB3_ETW_EVENT_SET_SEL_FAILURE
0x140029e00  mov     [rsp+0B8h+var_90], esi
0x140029e04  mov     dword ptr [rsp+0B8h+var_98], r12d
0x140029e09  call    McTemplateK0pqqq_EtwWriteTransfer
0x140029e0e  mov     ebp, 0FA8h
0x140029e13  cmp     esi, 0C0000004h
0x140029e19  lea     eax, [rbp-4]
0x140029e1c  cmovnz  ebp, eax
0x140029e1f  jmp     loc_14002A783
0x140029e24  mov     ebp, 0FA4h
0x140029e29  cmp     cl, 3
0x140029e2c  jnz     loc_140029F63
0x140029e32  movzx   eax, word ptr [rbx+19Ah]
0x140029e39  cmp     ax, 30h ; '0'
0x140029e3d  jnz     loc_140029ECE
0x140029e43  test    [rbx+198h], r9b
0x140029e4a  jnz     loc_14002A43C
0x140029e50  cmp     cs:WPP_RECORDER_INITIALIZED, r8; __annotation("TMF:",
0x140029e57  jz      short loc_140029E89
0x140029e59  mov     rcx, [rbx+8]
0x140029e5d  lea     rax, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x140029e64  mov     r9d, 0Bh
0x140029e6a  mov     [rsp+0B8h+var_88], esi
0x140029e6e  mov     [rsp+0B8h+var_90], edi
0x140029e72  mov     dl, 2
0x140029e74  mov     [rsp+0B8h+var_98], rax
0x140029e79  mov     rcx, [rcx+598h]
0x140029e80  lea     r8d, [r9-6]
0x140029e84  call    WPP_RECORDER_SF_dD
0x140029e89  test    dword ptr [rbx+98Ch], 2000h
0x140029e93  jz      short loc_140029EA8
0x140029e95  lea     rdx, [rbx+200h]
0x140029e9c  lea     rcx, aDevicehwverifi_2; "DeviceHwVerifierSetU1EnableFailure"
0x140029ea3  call    HUBMISC_VerifierDbgBreak
0x140029ea8  test    cs:byte_14006ED41, r13b
0x140029eaf  jz      loc_14002A783
0x140029eb5  mov     [rsp+0B8h+var_88], edi
0x140029eb9  lea     rdx, USBHUB3_ETW_EVENT_SET_U1_ENABLE_FAILURE
0x140029ec0  mov     [rsp+0B8h+var_90], esi
0x140029ec4  mov     dword ptr [rsp+0B8h+var_98], r12d
0x140029ec9  jmp     loc_14002A773
0x140029ece  cmp     ax, 31h ; '1'
0x140029ed2  jnz     loc_14002A43C
0x140029ed8  test    [rbx+198h], r9b
0x140029edf  jnz     loc_14002A43C
0x140029ee5  cmp     cs:WPP_RECORDER_INITIALIZED, r8; __annotation("TMF:",
0x140029eec  jz      short loc_140029F1E
0x140029eee  mov     rcx, [rbx+8]
0x140029ef2  lea     rax, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x140029ef9  mov     r9d, 0Ch
0x140029eff  mov     [rsp+0B8h+var_88], esi
0x140029f03  mov     [rsp+0B8h+var_90], edi
0x140029f07  mov     dl, 2
0x140029f09  mov     [rsp+0B8h+var_98], rax
0x140029f0e  mov     rcx, [rcx+598h]
0x140029f15  lea     r8d, [r9-7]
0x140029f19  call    WPP_RECORDER_SF_dD
0x140029f1e  test    dword ptr [rbx+98Ch], 4000h
0x140029f28  jz      short loc_140029F3D
0x140029f2a  lea     rdx, [rbx+200h]
0x140029f31  lea     rcx, aDevicehwverifi_9; "DeviceHwVerifierSetU2EnableFailure"
0x140029f38  call    HUBMISC_VerifierDbgBreak
0x140029f3d  test    cs:byte_14006ED41, r13b
0x140029f44  jz      loc_14002A783
0x140029f4a  mov     [rsp+0B8h+var_88], edi
0x140029f4e  lea     rdx, USBHUB3_ETW_EVENT_SET_U2_ENABLE_FAILURE
0x140029f55  mov     [rsp+0B8h+var_90], esi
0x140029f59  mov     dword ptr [rsp+0B8h+var_98], r12d
0x140029f5e  jmp     loc_14002A773
0x140029f63  cmp     cl, 6
0x140029f66  jnz     loc_14002A43C
0x140029f6c  test    [rbx+198h], r9b
0x140029f73  jnz     loc_14002A43C
0x140029f79  mov     al, [rbx+19Bh]
0x140029f7f  cmp     al, 3
0x140029f81  jnz     short loc_140029F8C
0x140029f83  cmp     byte ptr [rbx+19Ah], 0EEh
0x140029f8a  jmp     short loc_140029F8E
0x140029f8c  cmp     al, 6
0x140029f8e  jz      short loc_140029FB5
0x140029f90  mov     eax, [rbx+98Ch]
0x140029f96  test    r13b, al
0x140029f99  jz      short loc_140029FB5
0x140029f9b  lea     rdx, [rbx+200h]
0x140029fa2  lea     rcx, aDevicehwverifi_6; "DeviceHwVerifierControlTransferFailure"
0x140029fa9  call    HUBMISC_VerifierDbgBreak
0x140029fae  lea     r8, WPP_RECORDER_INITIALIZED
0x140029fb5  movzx   ecx, byte ptr [rbx+19Bh]
0x140029fbc  sub     ecx, 1
0x140029fbf  jz      loc_14002A3D3
0x140029fc5  sub     ecx, 1
0x140029fc8  jz      loc_14002A36A
0x140029fce  sub     ecx, 1
0x140029fd1  jz      loc_14002A0FB
0x140029fd7  sub     ecx, 3
0x140029fda  jz      loc_14002A092
0x140029fe0  cmp     ecx, 9
0x140029fe3  jz      short loc_14002A029
0x140029fe5  cmp     cs:WPP_RECORDER_INITIALIZED, r8; __annotation("TMF:",
0x140029fec  jz      loc_14002A783
0x140029ff2  mov     r9d, 16h
0x140029ff8  mov     rcx, [rbx+8]
0x140029ffc  lea     rax, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x14002a003  mov     [rsp+0B8h+var_88], esi
0x14002a007  mov     r8d, 5
0x14002a00d  mov     [rsp+0B8h+var_90], edi
0x14002a011  mov     dl, 2
0x14002a013  mov     [rsp+0B8h+var_98], rax
0x14002a018  mov     rcx, [rcx+598h]
0x14002a01f  call    WPP_RECORDER_SF_dD
0x14002a024  jmp     loc_14002A783
0x14002a029  mov     dword ptr [rbx+988h], 4001000Bh
0x14002a033  cmp     cs:WPP_RECORDER_INITIALIZED, r8; __annotation("TMF:",
0x14002a03a  jz      short loc_14002A06C
0x14002a03c  mov     rcx, [rbx+8]
0x14002a040  lea     rax, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x14002a047  mov     r9d, 0Fh
0x14002a04d  mov     [rsp+0B8h+var_88], esi
0x14002a051  mov     [rsp+0B8h+var_90], edi
0x14002a055  mov     dl, 2
0x14002a057  mov     [rsp+0B8h+var_98], rax
0x14002a05c  mov     rcx, [rcx+598h]
0x14002a063  lea     r8d, [r9-0Ah]
0x14002a067  call    WPP_RECORDER_SF_dD
0x14002a06c  test    cs:byte_14006ED41, r13b
0x14002a073  jz      loc_14002A783
0x14002a079  mov     [rsp+0B8h+var_88], edi
0x14002a07d  lea     rdx, USBHUB3_ETW_EVENT_BOS_DESCRIPTOR_FAILURE
0x14002a084  mov     [rsp+0B8h+var_90], esi
0x14002a088  mov     dword ptr [rsp+0B8h+var_98], r12d
0x14002a08d  jmp     loc_14002A773
0x14002a092  mov     dword ptr [rbx+988h], 4001000Ch
0x14002a09c  cmp     cs:WPP_RECORDER_INITIALIZED, r8; __annotation("TMF:",
0x14002a0a3  jz      short loc_14002A0D5
0x14002a0a5  mov     rcx, [rbx+8]
0x14002a0a9  lea     rax, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x14002a0b0  mov     r9d, 10h
0x14002a0b6  mov     [rsp+0B8h+var_88], esi
0x14002a0ba  mov     [rsp+0B8h+var_90], edi
0x14002a0be  mov     dl, 2
0x14002a0c0  mov     [rsp+0B8h+var_98], rax
0x14002a0c5  mov     rcx, [rcx+598h]
0x14002a0cc  lea     r8d, [r9-0Bh]
0x14002a0d0  call    WPP_RECORDER_SF_dD
0x14002a0d5  test    cs:byte_14006ED41, r13b
0x14002a0dc  jz      loc_14002A783
0x14002a0e2  mov     [rsp+0B8h+var_88], edi
0x14002a0e6  lea     rdx, USBHUB3_ETW_EVENT_DEVICE_QUALIFIER_DESCRIPTOR_FAILURE
0x14002a0ed  mov     [rsp+0B8h+var_90], esi
0x14002a0f1  mov     dword ptr [rsp+0B8h+var_98], r12d
0x14002a0f6  jmp     loc_14002A773
0x14002a0fb  mov     al, [rbx+7DCh]
0x14002a101  test    al, al
0x14002a103  jz      short loc_14002A176
0x14002a105  cmp     al, [rbx+19Ah]
0x14002a10b  jnz     short loc_14002A176
0x14002a10d  mov     dword ptr [rbx+988h], 4001000Dh
0x14002a117  cmp     cs:WPP_RECORDER_INITIALIZED, r8; __annotation("TMF:",
0x14002a11e  jz      short loc_14002A150
0x14002a120  mov     rcx, [rbx+8]
0x14002a124  lea     rax, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x14002a12b  mov     r9d, 11h
0x14002a131  mov     [rsp+0B8h+var_88], esi
0x14002a135  mov     [rsp+0B8h+var_90], edi
0x14002a139  mov     dl, 2
0x14002a13b  mov     [rsp+0B8h+var_98], rax
0x14002a140  mov     rcx, [rcx+598h]
0x14002a147  lea     r8d, [r9-0Ch]
0x14002a14b  call    WPP_RECORDER_SF_dD
0x14002a150  test    cs:byte_14006ED41, r13b
0x14002a157  jz      loc_14002A783
0x14002a15d  mov     [rsp+0B8h+var_88], edi
0x14002a161  lea     rdx, USBHUB3_ETW_EVENT_SERIAL_NUMBER_STRING_FAILURE
0x14002a168  mov     [rsp+0B8h+var_90], esi
0x14002a16c  mov     dword ptr [rsp+0B8h+var_98], r12d
0x14002a171  jmp     loc_14002A773
0x14002a176  mov     cl, [rbx+19Ah]
0x14002a17c  test    cl, cl
0x14002a17e  jnz     short loc_14002A1E9
0x14002a180  mov     dword ptr [rbx+988h], 4001000Eh
0x14002a18a  cmp     cs:WPP_RECORDER_INITIALIZED, r8; __annotation("TMF:",
0x14002a191  jz      short loc_14002A1C3
0x14002a193  mov     rcx, [rbx+8]
0x14002a197  lea     rax, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x14002a19e  mov     r9d, 12h
0x14002a1a4  mov     [rsp+0B8h+var_88], esi
0x14002a1a8  mov     [rsp+0B8h+var_90], edi
0x14002a1ac  mov     dl, 2
0x14002a1ae  mov     [rsp+0B8h+var_98], rax
0x14002a1b3  mov     rcx, [rcx+598h]
0x14002a1ba  lea     r8d, [r9-0Dh]
0x14002a1be  call    WPP_RECORDER_SF_dD
0x14002a1c3  test    cs:byte_14006ED41, r13b
0x14002a1ca  jz      loc_14002A783
0x14002a1d0  mov     [rsp+0B8h+var_88], edi
0x14002a1d4  lea     rdx, USBHUB3_ETW_EVENT_LANGUAGE_ID_STRING_FAILURE
0x14002a1db  mov     [rsp+0B8h+var_90], esi
0x14002a1df  mov     dword ptr [rsp+0B8h+var_98], r12d
0x14002a1e4  jmp     loc_14002A773
0x14002a1e9  mov     al, [rbx+7DBh]
0x14002a1ef  test    al, al
0x14002a1f1  jz      short loc_14002A260
0x14002a1f3  cmp     al, cl
0x14002a1f5  jnz     short loc_14002A260
0x14002a1f7  mov     dword ptr [rbx+988h], 4001000Fh
0x14002a201  cmp     cs:WPP_RECORDER_INITIALIZED, r8; __annotation("TMF:",
0x14002a208  jz      short loc_14002A23A
0x14002a20a  mov     rcx, [rbx+8]
0x14002a20e  lea     rax, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x14002a215  mov     r9d, 13h
0x14002a21b  mov     [rsp+0B8h+var_88], esi
0x14002a21f  mov     [rsp+0B8h+var_90], edi
0x14002a223  mov     dl, 2
0x14002a225  mov     [rsp+0B8h+var_98], rax
0x14002a22a  mov     rcx, [rcx+598h]
0x14002a231  lea     r8d, [r9-0Eh]
0x14002a235  call    WPP_RECORDER_SF_dD
0x14002a23a  test    cs:byte_14006ED41, r13b
0x14002a241  jz      loc_14002A783
0x14002a247  mov     [rsp+0B8h+var_88], edi
0x14002a24b  lea     rdx, USBHUB3_ETW_EVENT_PRODUCT_ID_STRING_FAILURE
  ... truncated ...
```
