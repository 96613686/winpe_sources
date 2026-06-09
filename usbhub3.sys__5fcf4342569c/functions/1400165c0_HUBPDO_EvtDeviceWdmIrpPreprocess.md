# HUBPDO_EvtDeviceWdmIrpPreprocess

- ea: `0x1400165c0`
- end: `0x1400178b3`
- name: `HUBPDO_EvtDeviceWdmIrpPreprocess`
- size: `4851`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140001f94`
- `0x1400024b8`
- `0x1400067ac`
- `0x1400083b4`
- `0x14000a53c`
- `0x14000f304`
- `0x14001444c`
- `0x1400165c0`
- `0x1400185e8`
- `0x140019d98`
- `0x14001b15c`
- `0x14001c150`
- `0x14001c570`
- `0x14001d788`
- `0x140026d98`
- `0x140026ef0`
- `0x14002f788`
- `0x140033530`
- `0x1400336a8`
- `0x14003f5b4`
- `0x140045530`
- `0x140045570`
- `0x140045640`
- `0x140082cc4`
- `0x1400834b0`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400166d4`
- `ntoskrnl!IofCallDriver` at `0x1400166d4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140016a42`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140016b4d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140016a42`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140016b4d`
- `ntoskrnl!KeGetCurrentIrql` at `0x140016cfe`
- `ntoskrnl!KeGetCurrentIrql` at `0x140016dd8`
- `ntoskrnl!KeGetCurrentIrql` at `0x140016e71`
- `ntoskrnl!KeGetCurrentIrql` at `0x140017140`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001735e`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400173c4`
- `ntoskrnl!KeGetCurrentIrql` at `0x140016cfe`
- `ntoskrnl!KeGetCurrentIrql` at `0x140016dd8`
- `ntoskrnl!KeGetCurrentIrql` at `0x140016e71`
- `ntoskrnl!KeGetCurrentIrql` at `0x140017140`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001735e`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400173c4`
- `ntoskrnl!KeInitializeEvent` at `0x1400175b2`
- `ntoskrnl!KeInitializeEvent` at `0x14001769c`
- `ntoskrnl!KeInitializeEvent` at `0x1400175b2`
- `ntoskrnl!KeInitializeEvent` at `0x14001769c`
- `ntoskrnl!IofCompleteRequest` at `0x14001787b`
- `ntoskrnl!IofCompleteRequest` at `0x14001787b`
- `ntoskrnl!RtlCompareMemory` at `0x14001744b`
- `ntoskrnl!RtlCompareMemory` at `0x14001748a`
- `ntoskrnl!RtlCompareMemory` at `0x140017741`
- `ntoskrnl!RtlCompareMemory` at `0x14001777b`
- `ntoskrnl!RtlCompareMemory` at `0x1400177ac`
- `ntoskrnl!RtlCompareMemory` at `0x1400177dd`
- `ntoskrnl!RtlCompareMemory` at `0x140017800`
- `ntoskrnl!RtlCompareMemory` at `0x14001744b`
- `ntoskrnl!RtlCompareMemory` at `0x14001748a`
- `ntoskrnl!RtlCompareMemory` at `0x140017741`
- `ntoskrnl!RtlCompareMemory` at `0x14001777b`
- `ntoskrnl!RtlCompareMemory` at `0x1400177ac`
- `ntoskrnl!RtlCompareMemory` at `0x1400177dd`
- `ntoskrnl!RtlCompareMemory` at `0x140017800`

## pseudocode

```c
__int64 __fastcall HUBPDO_EvtDeviceWdmIrpPreprocess(__int64 a1, IRP *a2)
{
  __int64 v3; // rbx
  __int64 v4; // rax
  int v5; // edx
  _IO_STACK_LOCATION *CurrentStackLocation; // r14
  __int64 v7; // rdi
  unsigned int LowPart; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  bool v16; // zf
  _IRP *MasterIrp; // rdx
  unsigned int Status; // ebx
  int v21; // r14d
  char v22; // dl
  unsigned int v23; // esi
  _IO_SECURITY_CONTEXT *v24; // r14
  __int64 v25; // rdx
  bool v26; // zf
  __int64 v27; // rcx
  __int64 v28; // rcx
  int v29; // r9d
  int v30; // edx
  __int64 v31; // rcx
  __int64 v32; // r8
  _IO_SECURITY_CONTEXT *SecurityContext; // r15
  __int64 v34; // rcx
  _ACCESS_STATE *v35; // rax
  _SECURITY_QUALITY_OF_SERVICE *v36; // rcx
  PVOID v37; // r10
  __int64 v38; // rdx
  unsigned __int16 *v39; // rdx
  unsigned int *v40; // rsi
  unsigned int v41; // ebx
  _SECURITY_QUALITY_OF_SERVICE *SecurityQos; // rcx
  PVOID v43; // rcx
  unsigned int AccessState_high; // eax
  unsigned int v45; // ebx
  int v46; // eax
  __int64 v47; // rcx
  unsigned int v48; // eax
  unsigned int v49; // eax
  unsigned int v50; // eax
  unsigned int v51; // eax
  unsigned int v52; // eax
  unsigned int v53; // eax
  unsigned int DeviceBusInfo; // eax
  int v55; // r9d
  __int64 v56; // rdx
  _IO_SECURITY_CONTEXT *v57; // rax
  _NAMED_PIPE_CREATE_PARAMETERS *Parameters; // rax
  unsigned int v59; // eax
  unsigned int v60; // eax
  unsigned int v61; // eax
  unsigned int v62; // eax
  unsigned int v63; // eax
  unsigned int v64; // eax
  _IO_SECURITY_CONTEXT *v65; // rcx
  __int64 v66; // rax
  __int16 v67; // dx
  __int64 v68; // r8
  unsigned int v69; // eax
  unsigned int v70; // eax
  unsigned int v71; // eax
  unsigned int v72; // eax
  unsigned int v73; // eax
  unsigned int v74; // eax
  _IO_SECURITY_CONTEXT *v75; // rax
  __int64 v76; // rcx
  _IO_SECURITY_CONTEXT *v77; // r8
  __int64 v78; // rax
  __int64 v79; // rdx
  __int64 v80; // rcx
  char v81; // cl
  __int64 v82; // rcx
  char v83; // cl
  unsigned int v84; // eax
  unsigned int v85; // eax
  unsigned int v86; // eax
  unsigned int v87; // eax
  unsigned int v88; // eax
  unsigned int v89; // eax
  int v90; // edx
  int v91; // r9d
  _IO_SECURITY_CONTEXT *v92; // rax
  int v93; // eax
  int v94; // r14d
  int v95; // r14d
  int v96; // r14d
  int v97; // r14d
  _IO_STACK_LOCATION *v98; // rax
  __int64 v99; // rax
  _IO_STACK_LOCATION *v100; // rax
  _IO_STACK_LOCATION *v101; // rax
  int v102; // eax
  int v103; // edx
  int v104; // r9d
  _IO_STACK_LOCATION *v105; // rax
  _IO_STACK_LOCATION *v106; // rax
  __int64 v107; // rax
  int v108; // ecx
  unsigned int v109; // [rsp+30h] [rbp-50h]
  _IO_STACK_LOCATION *v110; // [rsp+38h] [rbp-48h]
  struct _KEVENT Event; // [rsp+40h] [rbp-40h] BYREF
  __int128 v112; // [rsp+58h] [rbp-28h] BYREF
  __int128 Source1; // [rsp+68h] [rbp-18h] BYREF

  v3 = a1;
  *(_QWORD *)&v112 = a1;
  memset(&Event, 0, sizeof(Event));
  Source1 = 0;
  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006B1D0);
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v110 = CurrentStackLocation;
  v7 = v4;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  v109 = LowPart;
  if ( CurrentStackLocation->MajorFunction == 14 )
  {
    v9 = LowPart - 2229348;
    if ( v9 )
    {
      v10 = v9 - 4;
      if ( !v10 )
      {
        if ( CurrentStackLocation->Parameters.Read.Length != 36 )
        {
LABEL_20:
          Status = -1073741811;
          v21 = 2;
          goto LABEL_247;
        }
        v16 = CurrentStackLocation->Parameters.Create.Options == 36;
LABEL_12:
        if ( v16 )
        {
          MasterIrp = a2->AssociatedIrp.MasterIrp;
          if ( MasterIrp )
          {
            *(_QWORD *)(&MasterIrp->Size + 1) = *(_QWORD *)(*(_QWORD *)(v7 + 24) + 24LL);
            goto LABEL_15;
          }
        }
        goto LABEL_20;
      }
      v11 = v10 - 4;
      if ( v11 )
      {
        v12 = v11 - 4;
        if ( v12 )
        {
          v13 = v12 - 4;
          if ( !v13 )
            goto LABEL_15;
          v14 = v13 - 4;
          if ( !v14 )
            goto LABEL_15;
          v15 = v14 - 4;
          if ( !v15 )
            goto LABEL_15;
          if ( v15 != 4 )
            goto LABEL_261;
          if ( CurrentStackLocation->Parameters.Read.Length != 24 )
            goto LABEL_20;
          v16 = CurrentStackLocation->Parameters.Create.Options == 24;
          goto LABEL_12;
        }
      }
    }
    goto LABEL_108;
  }
  v22 = 0;
  switch ( LowPart )
  {
    case 0x220003u:
      LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
      if ( (unsigned __int16)(*(_WORD *)(CurrentStackLocation->Parameters.WMI.ProviderId + 2) - 53) <= 1u )
LABEL_23:
        v22 = 1;
      break;
    case 0x490007u:
    case 0x49104Bu:
      v22 = 1;
      break;
    case 0x220FB3u:
      LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
      if ( (*(_DWORD *)(v7 + 32) & 0x20) == 0 )
        break;
      goto LABEL_23;
    case 0x220463u:
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v5) = 4;
        WPP_RECORDER_SF_q(
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 24) + 8LL) + 1432LL),
          v5,
          5,
          57,
          (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
          (char)a2);
      }
      *(_DWORD *)(*(_QWORD *)(v7 + 24) + 1640LL) |= 0x80000u;
      goto LABEL_40;
  }
  if ( *(_BYTE *)v7 && !v22 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 3;
      WPP_RECORDER_SF_q(
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 24) + 8LL) + 1432LL),
        v5,
        5,
        58,
        (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
        (char)a2);
    }
    v23 = v109;
    Status = -1073741810;
    if ( v109 == 2228227 )
      *(_DWORD *)(CurrentStackLocation->Parameters.WMI.ProviderId + 4) = -2147482880;
LABEL_58:
    if ( (*(_DWORD *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015
                                                                                               + 1616))(
                        WdfDriverGlobals,
                        WdfDriverGlobals->Driver,
                        off_14006B2C0)
                    + 4)
        & 0x1000) != 0 )
    {
      v112 = 0;
      if ( g_IoGetActivityIdIrp )
        g_IoGetActivityIdIrp(a2, &v112, v32);
      if ( (byte_14006ED41 & 4) != 0 )
        McTemplateK0pq_EtwWriteTransfer(
          v31,
          USBHUB3_ETW_EVENT_DEVICE_INTERNAL_IOCTL_START,
          &v112,
          *(_QWORD *)(*(_QWORD *)(v7 + 24) + 24LL),
          v23);
      if ( v23 != 2228227 )
      {
        if ( v23 == 4788299 )
        {
          if ( (byte_14006ED41 & 4) == 0 )
            goto LABEL_279;
          McTemplateK0pjq_EtwWriteTransfer(
            v31,
            v30,
            (unsigned int)&v112,
            *(_QWORD *)(*(_QWORD *)(v7 + 24) + 24LL),
            (__int64)&Source1,
            Status);
        }
LABEL_277:
        if ( (byte_14006ED41 & 4) != 0 )
          McTemplateK0pqq_EtwWriteTransfer(
            v31,
            (unsigned int)USBHUB3_ETW_EVENT_DEVICE_INTERNAL_IOCTL_COMPLETE,
            (unsigned int)&v112,
            *(_QWORD *)(*(_QWORD *)(v7 + 24) + 24LL),
            v23,
            Status);
        goto LABEL_279;
      }
      SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
      if ( (byte_14006ED41 & 4) != 0 )
      {
        McTemplateK0pq_EtwWriteTransfer(
          v31,
          USBHUB3_ETW_EVENT_DEVICE_URB_START,
          &v112,
          *(_QWORD *)(*(_QWORD *)(v7 + 24) + 24LL),
          WORD1(SecurityContext->SecurityQos));
        if ( (byte_14006ED41 & 4) != 0 )
        {
          McTemplateK0pqq_EtwWriteTransfer(
            WORD1(SecurityContext->SecurityQos),
            (unsigned int)USBHUB3_ETW_EVENT_DEVICE_URB_COMPLETE,
            (unsigned int)&v112,
            *(_QWORD *)(*(_QWORD *)(v7 + 24) + 24LL),
            WORD1(SecurityContext->SecurityQos),
            HIDWORD(SecurityContext->SecurityQos));
          goto LABEL_277;
        }
      }
    }
LABEL_279:
    a2->IoStatus.Status = Status;
    goto LABEL_280;
  }
  if ( LowPart == 2228227 )
  {
    v24 = CurrentStackLocation->Parameters.Create.SecurityContext;
    LODWORD(v25) = WORD1(v24->SecurityQos);
    if ( (unsigned __int16)(v25 - 9) <= 1u || (unsigned __int16)(v25 - 57) <= 1u )
      goto LABEL_115;
    if ( (unsigned int)v25 > 0x2A )
    {
      if ( (_DWORD)v25 != 48 && (_DWORD)v25 != 49 )
      {
        if ( (_DWORD)v25 == 53 || (_DWORD)v25 == 54 )
        {
          v24->AccessState = *(_ACCESS_STATE **)(*(_QWORD *)(v7 + 24) + 24LL);
          goto LABEL_261;
        }
        v26 = (_DWORD)v25 == 59;
LABEL_114:
        if ( !v26 )
          goto LABEL_115;
      }
    }
    else
    {
      if ( (_DWORD)v25 == 42 )
      {
        v25 = *(_QWORD *)(v7 + 24);
        if ( WORD2(v24[5].AccessState) != 7 )
        {
          if ( (unsigned __int16)(*(_WORD *)(v25 + 1998) - 256) > 0xFFu && (*(_DWORD *)(v25 + 1640) & 0x80u) == 0
            || (*(_DWORD *)(v25 + 1652) & 2) != 0 )
          {
            BYTE1(v24[5].AccessState) = *(_BYTE *)(v25 + 2060);
            v24->AccessState = *(_ACCESS_STATE **)(*(_QWORD *)(v7 + 24) + 24LL);
LABEL_108:
            Status = 0;
            v21 = 1;
            goto LABEL_247;
          }
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_55;
          v28 = *(_QWORD *)(v25 + 8);
          v29 = 59;
          LOBYTE(v25) = 3;
          goto LABEL_54;
        }
        if ( (*(_DWORD *)(v25 + 2472) & 2) == 0 )
          goto LABEL_55;
        SecurityQos = v24[2].SecurityQos;
        if ( SecurityQos )
          v43 = (*(&SecurityQos->EffectiveOnly + 1) & 5) != 0
              ? *(PVOID *)&SecurityQos[2].Length
              : MmMapLockedPagesSpecifyCache((PMDL)SecurityQos, 0, MmCached, 0, 0, 0x40000010u);
        else
          v43 = *(PVOID *)&v24[1].DesiredAccess;
        if ( !v43 )
          goto LABEL_55;
        AccessState_high = *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(v7 + 24) + 2496LL) + 8LL);
        if ( AccessState_high >= HIDWORD(v24[1].AccessState) )
          AccessState_high = HIDWORD(v24[1].AccessState);
        v45 = AccessState_high;
        memmove(v43, *(const void **)(*(_QWORD *)(v7 + 24) + 2496LL), AccessState_high);
        HIDWORD(v24[1].AccessState) = v45;
        goto LABEL_90;
      }
      if ( WORD1(v24->SecurityQos) && (_DWORD)v25 != 1 )
      {
        if ( (_DWORD)v25 != 11 )
        {
          if ( (_DWORD)v25 != 19 )
          {
            v26 = (_DWORD)v25 == 30;
            goto LABEL_114;
          }
          v27 = *(_QWORD *)(v7 + 24);
          if ( (*(_DWORD *)(v27 + 1640) & 0x80000) != 0 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
LABEL_55:
              Status = -1073741637;
LABEL_56:
              CurrentStackLocation = v110;
              goto LABEL_57;
            }
            v28 = *(_QWORD *)(v27 + 8);
            v29 = 60;
            LOBYTE(v25) = 4;
LABEL_54:
            WPP_RECORDER_SF_(
              *(_QWORD *)(v28 + 1432),
              v25,
              5,
              v29,
              (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids);
            goto LABEL_55;
          }
LABEL_115:
          v24->AccessState = *(_ACCESS_STATE **)(*(_QWORD *)(v7 + 24) + 24LL);
          goto LABEL_15;
        }
        v34 = *(_QWORD *)(v7 + 24);
        if ( *(_WORD *)(v34 + 1998) <= 0x200u )
        {
          v35 = *(_ACCESS_STATE **)(v34 + 24);
LABEL_69:
          v24->AccessState = v35;
          goto LABEL_15;
        }
        Status = HUBPDO_ValidateURB(v7, v24, 4788299);
        if ( (Status & 0x80000000) != 0 )
          goto LABEL_56;
        v36 = v24[2].SecurityQos;
        if ( v36 )
        {
          if ( (*(&v36->EffectiveOnly + 1) & 5) != 0 )
            v37 = *(PVOID *)&v36[2].Length;
          else
            v37 = MmMapLockedPagesSpecifyCache((PMDL)v36, 0, MmCached, 0, 0, 0x40000010u);
        }
        else
        {
          v37 = *(PVOID *)&v24[1].DesiredAccess;
        }
        if ( !v37 )
        {
          Status = -1073741811;
          HIDWORD(v24->SecurityQos) = -2147482880;
          goto LABEL_56;
        }
        if ( BYTE3(v24[5].AccessState) == 1 )
        {
          v40 = (unsigned int *)&v24[1].AccessState + 1;
          v39 = (unsigned __int16 *)(*(_QWORD *)(v7 + 24) + 1996LL);
          v41 = 18;
          if ( HIDWORD(v24[1].AccessState) <= 0x12 )
            v41 = HIDWORD(v24[1].AccessState);
        }
        else
        {
          if ( BYTE3(v24[5].AccessState) != 2 )
            goto LABEL_115;
          v38 = *(_QWORD *)(v7 + 24);
          if ( BYTE2(v24[5].AccessState) )
          {
            v35 = *(_ACCESS_STATE **)(v38 + 24);
            goto LABEL_69;
          }
          v39 = *(unsigned __int16 **)(v38 + 2024);
          v40 = (unsigned int *)&v24[1].AccessState + 1;
          v41 = v39[1];
          if ( v41 >= HIDWORD(v24[1].AccessState) )
            v41 = HIDWORD(v24[1].AccessState);
        }
        LODWORD(v24[1].AccessState) |= 1u;
        if ( ((__int64)v24[1].AccessState & 8) != 0 )
          WORD1(v24->SecurityQos) = 8;
        memmove(v37, v39, v41);
        *v40 = v41;
LABEL_90:
        Status = 0;
        goto LABEL_56;
      }
    }
    v46 = HUBPDO_ValidateURB(v7, v24, 4788299);
    Status = v46;
    if ( v46 < 0 )
      goto LABEL_56;
    if ( v46 != 128 )
    {
      v21 = (*(_DWORD *)(*(_QWORD *)(v7 + 24) + 1640LL) & 2) != 0 ? 5 : 3;
      goto LABEL_247;
    }
    goto LABEL_90;
  }
  if ( LowPart <= 0x22043F )
  {
    if ( LowPart == 2229311 )
    {
      v65 = CurrentStackLocation->Parameters.Create.SecurityContext;
      if ( !v65 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v5) = 3;
          WPP_RECORDER_SF_(
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 24) + 8LL) + 1432LL),
            v5,
            5,
            11,
            (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids);
        }
        Status = -1073741811;
        goto LABEL_57;
      }
      v66 = *(_QWORD *)(v7 + 16);
      *(_OWORD *)&v65->SecurityQos = *(_OWORD *)(v66 + 312);
      *(_OWORD *)&v65->DesiredAccess = *(_OWORD *)(v66 + 328);
      v67 = *(_WORD *)(v7 + 48);
      v68 = *(unsigned __int8 *)(*(_QWORD *)(v7 + 16) + 240LL);
      if ( (_BYTE)v68 )
        *((_WORD *)&v65->DesiredAccess + v68) = v67;
      else
        LOWORD(v65->DesiredAccess) = v67;
      goto LABEL_40;
    }
    v47 = 2228263;
    if ( LowPart > 0x220027 )
    {
      v59 = LowPart - 2228267;
      if ( !v59 )
      {
        DeviceBusInfo = HUBPDO_RecordFailure(v7, a2, 4788299);
        goto LABEL_132;
      }
      v60 = v59 - 1013;
      if ( !v60 )
      {
        DeviceBusInfo = HUBUCX_GetDeviceBusInfo(
                          *(_QWORD *)(v7 + 16),
                          *(_QWORD *)(*(_QWORD *)(v7 + 24) + 24LL),
                          CurrentStackLocation->Parameters.WMI.ProviderId);
        goto LABEL_132;
      }
      v61 = v60 - 4;
      if ( !v61 )
      {
        DeviceBusInfo = HUBUCX_GetControllerName(
                          *(_QWORD *)(v7 + 16),
                          CurrentStackLocation->Parameters.WMI.ProviderId,
                          CurrentStackLocation->Parameters.Create.Options);
        goto LABEL_132;
      }
      v62 = v61 - 8;
      if ( v62 )
      {
        v63 = v62 - 7;
        if ( !v63 )
        {
          Status = CurrentStackLocation->Parameters.WMI.ProviderId == 0 ? 0xC000000D : 0;
          goto LABEL_57;
        }
        v64 = v63 - 4;
        if ( v64 )
        {
          if ( v64 != 4 )
          {
LABEL_229:
            Status = a2->IoStatus.Status;
            goto LABEL_57;
          }
        }
      }
    }
    else
    {
      if ( LowPart == 2228263 )
      {
        Parameters = CurrentStackLocation->Parameters.CreatePipe.Parameters;
        if ( Parameters && *(_QWORD *)&Parameters->NamedPipeType )
        {
          v112 = 0;
          if ( g_IoGetActivityIdIrp )
            g_IoGetActivityIdIrp(a2, &v112, 4788299);
          if ( (byte_14006ED41 & 4) != 0 )
            McTemplateK0p_EtwWriteTransfer(
              v47,
              USBHUB3_ETW_EVENT_DEVICE_SUBMIT_IDLE_NOTIFICATION_START,
              &v112,
              *(_QWORD *)(*(_QWORD *)(v7 + 24) + 24LL));
          return (unsigned int)HUBIDLE_AddEvent(v7 + 72, 6003, a2);
        }
        Status = -1073741224;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_57;
        v21 = 2;
        LOBYTE(v5) = 3;
        WPP_RECORDER_SF_(
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 24) + 8LL) + 1432LL),
          v5,
          5,
          69,
          (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids);
        goto LABEL_247;
      }
      v48 = LowPart - 2228231;
      if ( !v48 )
      {
        if ( (*(_DWORD *)(v7 + 32) & 1) != 0 )
        {
          if ( !KeGetCurrentIrql() )
            goto LABEL_261;
          Status = -1073741811;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_57;
          v55 = 64;
        }
        else
        {
          Status = -1073741101;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_57;
          v55 = 63;
        }
        goto LABEL_136;
      }
      v49 = v48 - 8;
      if ( v49 )
      {
        v50 = v49 - 4;
        if ( !v50 )
        {
          if ( KeGetCurrentIrql() )
          {
            Status = -1073741811;
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_57;
            v55 = 61;
          }
          else
          {
            v57 = CurrentStackLocation->Parameters.Create.SecurityContext;
            if ( v57 )
            {
              LODWORD(v57->SecurityQos) = 0;
              CurrentStackLocation->Parameters.QueryDirectory.FileName = (_UNICODE_STRING *)v7;
LABEL_255:
              v100 = a2->Tail.Overlay.CurrentStackLocation;
              *(_OWORD *)&v100[-1].MajorFunction = *(_OWORD *)&v100->MajorFunction;
              *(_OWORD *)&v100[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v100->Parameters.NotifyDirectoryEx.CompletionFilter;
              *(_OWORD *)(&v100[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v100->Parameters.SetQuota + 6);
              v100[-1].FileObject = v100->FileObject;
              v100[-1].Control = 0;
              KeInitializeEvent(&Event, NotificationEvent, 0);
              v101 = a2->Tail.Overlay.CurrentStackLocation;
              v101[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))&HUBPDO_SyncCompletionRoutine;
              v101[-1].Context = &Event;
              v101[-1].Control = -32;
              v102 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, IRP *, _QWORD, int))(WdfFunctions_01015
                                                                                                 + 3216))(
                       WdfDriverGlobals,
                       v3,
                       a2,
                       *(_QWORD *)(*(_QWORD *)(v7 + 16) + 2416LL),
                       2);
              if ( v102 >= 0 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                goto LABEL_259;
              v104 = 72;
              LOBYTE(v103) = 2;
LABEL_258:
              WPP_RECORDER_SF_d(
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 24) + 8LL) + 1432LL),
                v103,
                5,
                v104,
                (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
                v102);
LABEL_259:
              HUBMISC_WaitForSignal(&Event);
              Status = a2->IoStatus.Status;
LABEL_280:
              IofCompleteRequest(a2, 0);
              return Status;
            }
            Status = -1073741811;
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_57;
            v55 = 62;
          }
          LOBYTE(v5) = 2;
          goto LABEL_137;
        }
        v51 = v50 - 4;
        if ( v51 )
        {
          v52 = v51 - 4;
          if ( v52 )
          {
            v53 = v52 - 4;
            if ( v53 )
            {
              if ( v53 == 1 )
              {
                DeviceBusInfo = HUBPDO_GetHubName(v7, a2, 4788299);
LABEL_132:
                Status = DeviceBusInfo;
                goto LABEL_57;
              }
              goto LABEL_229;
            }
            if ( KeGetCurrentIrql() )
            {
              Status = -1073741811;
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                goto LABEL_57;
              v55 = 67;
              goto LABEL_136;
            }
            Status = 0;
            if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v7 + 4), 1, 0) )
            {
              v56 = *(_QWORD *)(v7 + 24);
              if ( (*(_DWORD *)(v56 + 2444) & 0x400) != 0 )
                HUBMISC_VerifierDbgBreak("DeviceHwVerifierClientInitiatedCyclePort", v56 + 512);
              EventWriteUSBHUB3_ETW_EVENT_CLIENT_INITIATED_RECOVERY_ACTION_Wrapper(*(_QWORD *)(v7 + 24), 2228255, 0);
              HUBSM_AddEvent(*(_QWORD *)(v7 + 24) + 512LL, 4011);
              goto LABEL_57;
            }
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v55 = 68;
LABEL_136:
              LOBYTE(v5) = 3;
LABEL_137:
              WPP_RECORDER_SF_(
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 24) + 8LL) + 1432LL),
                v5,
                5,
                v55,
                (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids);
            }
LABEL_57:
            v23 = v109;
            goto LABEL_58;
          }
        }
LABEL_40:
        Status = 0;
        goto LABEL_57;
      }
    }
    goto LABEL_174;
  }
  if ( LowPart <= 0x491043 )
  {
    if ( LowPart == 4788291 )
    {
      v77 = CurrentStackLocation->Parameters.Create.SecurityContext;
      v77->SecurityQos = *(_SECURITY_QUALITY_OF_SERVICE **)(*(_QWORD *)(v7 + 16) + 2464LL);
      v78 = *(_QWORD *)(v7 + 24);
      *(_OWORD *)&v77->AccessState = *(_OWORD *)(v78 + 1996);
      LOWORD(v77[1].SecurityQos) = *(_WORD *)(v78 + 2012);
      WORD1(v77[1].SecurityQos) = *(_WORD *)(*(_QWORD *)(v7 + 24) + 2200LL);
      WORD2(v77[1].SecurityQos) = *(_WORD *)(*(_QWORD *)(v7 + 24) + 2202LL);
      v77[2].AccessState = *(_ACCESS_STATE **)(*(_QWORD *)(v7 + 24) + 2576LL);
      v77[2].DesiredAccess = *(_DWORD *)(*(_QWORD *)(v7 + 24) + 2584LL);
      BYTE2(v77[1].DesiredAccess) = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v7 + 24) + 8LL) + 202LL);
      HIWORD(v77[1].AccessState) = *(_WORD *)(*(_QWORD *)(v7 + 24) + 2210LL);
      LOWORD(v77[1].DesiredAccess) = *(_WORD *)(*(_QWORD *)(v7 + 24) + 2212LL);
      v79 = *(_QWORD *)(v7 + 16);
      LOWORD(v77[1].FullCreateOptions) = *(_WORD *)(*(_QWORD *)(v7 + 24) + 2590LL)
                                       + *(_WORD *)(v79 + 1204)
                                       + *(_WORD *)(v79 + 2508);
      v80 = *(_QWORD *)(v7 + 24);
      if ( (*(_DWORD *)(v80 + 2224) & 1) != 0 )
      {
        HIWORD(v77[1].SecurityQos) = *(unsigned __int8 *)(v80 + 2205);
        v81 = *(_BYTE *)(*(_QWORD *)(v7 + 16) + 240LL);
      }
      else
      {
        HIWORD(v77[1].SecurityQos) = *(_WORD *)(v79 + 2494);
        v81 = *(_BYTE *)(v79 + 2496);
      }
      LOBYTE(v77[1].AccessState) = v81;
      v82 = *(_QWORD *)(v7 + 24);
      if ( (*(_DWORD *)(v82 + 2224) & 2) != 0 )
      {
        WORD1(v77[1].AccessState) = *(_WORD *)(v82 + 2208);
        v83 = *(_BYTE *)(*(_QWORD *)(v7 + 16) + 240LL);
      }
      else
      {
        WORD1(v77[1].AccessState) = *(_WORD *)(v79 + 2498);
        v83 = *(_BYTE *)(v79 + 2500);
      }
      BYTE4(v77[1].AccessState) = v83;
      if ( (*(_DWORD *)(v79 + 2512) & 1) != 0 )
        LODWORD(v77[2].SecurityQos) |= 1u;
      if ( (*(_DWORD *)(v79 + 2512) & 4) != 0 )
        LODWORD(v77[2].SecurityQos) |= 4u;
      if ( (*(_DWORD *)(*(_QWORD *)(v7 + 24) + 1640LL) & 0x2000) != 0 )
        LODWORD(v77[2].SecurityQos) |= 2u;
      if ( (((unsigned __int8)*(_DWORD *)(v79 + 2512) | *(_BYTE *)(*(_QWORD *)(v7 + 16) + 44LL)) & 8) != 0 )
        LODWORD(v77[2].SecurityQos) |= 8u;
      goto LABEL_40;
    }
    v69 = LowPart - 2229315;
    if ( !v69 )
    {
LABEL_174:
      Status = -1073741637;
      goto LABEL_57;
    }
    v70 = v69 - 12;
    if ( !v70 )
    {
      DeviceBusInfo = HUBPDO_ReturnDeviceConfigInfo(v7, a2, 4788299);
      goto LABEL_132;
    }
    v71 = v70 - 2916;
    if ( !v71 )
    {
      if ( (*(_DWORD *)(v7 + 32) & 1) != 0 )
      {
        if ( KeGetCurrentIrql() <= 2u )
        {
LABEL_253:
          v98 = a2->Tail.Overlay.CurrentStackLocation;
          *(_OWORD *)&v98[-1].MajorFunction = *(_OWORD *)&v98->MajorFunction;
          *(_OWORD *)&v98[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v98->Parameters.NotifyDirectoryEx.CompletionFilter;
          *(_OWORD *)(&v98[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v98->Parameters.SetQuota + 6);
          v98[-1].FileObject = v98->FileObject;
          v98[-1].Control = 0;
          v99 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 736))(
                  WdfDriverGlobals,
                  v3);
          return (unsigned int)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, IRP *, __int64, int))(WdfFunctions_01015 + 3216))(
                                 WdfDriverGlobals,
                                 v3,
                                 a2,
                                 v99,
                                 2);
        }
        Status = -1073741811;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_57;
        v55 = 66;
      }
      else
      {
        Status = -1073741101;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_57;
        v55 = 65;
      }
      goto LABEL_136;
    }
    v72 = v71 - 8;
    if ( !v72 )
    {
      v76 = *(_QWORD *)(v7 + 24);
      if ( (*(_DWORD *)(v76 + 1652) & 0x1000000) == 0 )
      {
        Status = -1073741275;
        goto LABEL_57;
      }
      DeviceBusInfo = HUBMISC_GenerateControllerSuffix(v76, CurrentStackLocation->Parameters.WMI.ProviderId, 4788299);
      goto LABEL_132;
    }
    v73 = v72 - 2551880;
    if ( !v73 )
    {
      v75 = CurrentStackLocation->Parameters.Create.SecurityContext;
      CurrentStackLocation->Parameters.QueryDirectory.FileName = *(_UNICODE_STRING **)(*(_QWORD *)(v7 + 24) + 24LL);
      if ( (v75->DesiredAccess & 1) != 0 )
        _InterlockedOr((volatile signed __int32 *)(v7 + 32), 0x10u);
      goto LABEL_15;
    }
    v74 = v73 - 4;
    if ( v74 && v74 != 4 )
      goto LABEL_229;
LABEL_195:
    CurrentStackLocation->Parameters.QueryDirectory.FileName = *(_UNICODE_STRING **)(*(_QWORD *)(v7 + 24) + 24LL);
    goto LABEL_15;
  }
  v84 = LowPart - 4788299;
  if ( !v84 )
  {
    v92 = CurrentStackLocation->Parameters.Create.SecurityContext;
    Source1 = *(_OWORD *)&v92->DesiredAccess;
    HIDWORD(v92[1].AccessState) = 0;
    if ( RtlCompareMemory(&Source1, &GUID_USB_CAPABILITY_FUNCTION_SUSPEND, 0x10u) == 16 )
    {
      v93 = -((*(_DWORD *)(*(_QWORD *)(v7 + 24) + 1464LL) & 0x10000) != 0);
    }
    else
    {
      if ( RtlCompareMemory(&Source1, &GUID_USB_CAPABILITY_STATIC_STREAMS, 0x10u) == 16 )
      {
        Status = (*(_DWORD *)(*(_QWORD *)(v7 + 24) + 1464LL) & 0x10000) != 0 ? 0xC00000BB : 0;
        v21 = ((*(_DWORD *)(*(_QWORD *)(v7 + 24) + 1464LL) & 0x10000) != 0) + 1;
LABEL_247:
        v94 = v21 - 1;
        if ( !v94 )
          goto LABEL_15;
        v95 = v94 - 1;
        if ( v95 )
        {
          v96 = v95 - 1;
          if ( v96 )
          {
            v97 = v96 - 1;
            if ( v97 )
            {
              if ( v97 != 1 )
                return Status;
              v3 = v112;
              goto LABEL_253;
            }
            v3 = v112;
            goto LABEL_255;
          }
          v3 = v112;
LABEL_261:
          v105 = a2->Tail.Overlay.CurrentStackLocation;
          *(_OWORD *)&v105[-1].MajorFunction = *(_OWORD *)&v105->MajorFunction;
          *(_OWORD *)&v105[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v105->Parameters.NotifyDirectoryEx.CompletionFilter;
          *(_OWORD *)(&v105[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v105->Parameters.SetQuota + 6);
          v105[-1].FileObject = v105->FileObject;
          v105[-1].Control = 0;
          KeInitializeEvent(&Event, NotificationEvent, 0);
          v106 = a2->Tail.Overlay.CurrentStackLocation;
          v106[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))&HUBPDO_SyncCompletionRoutine;
          v106[-1].Context = &Event;
          v106[-1].Control = -32;
          v107 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 736))(
                   WdfDriverGlobals,
                   v3);
          v102 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, IRP *, __int64, int))(WdfFunctions_01015 + 3216))(
                   WdfDriverGlobals,
                   v3,
                   a2,
                   v107,
                   2);
          if ( v102 >= 0 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_259;
          v104 = 73;
          LOBYTE(v103) = 3;
          goto LABEL_258;
        }
        goto LABEL_56;
      }
      if ( RtlCompareMemory(&Source1, &GUID_USB_CAPABILITY_DEVICE_CONNECTION_SUPER_SPEED_COMPATIBLE, 0x10u) == 16 )
      {
        v108 = *(_DWORD *)(*(_QWORD *)(v7 + 24) + 1464LL) & 0x800;
      }
      else if ( RtlCompareMemory(&Source1, &GUID_USB_CAPABILITY_DEVICE_CONNECTION_HIGH_SPEED_COMPATIBLE, 0x10u) == 16 )
      {
        v108 = *(_DWORD *)(*(_QWORD *)(v7 + 24) + 1464LL) & 0x900;
      }
      else
      {
        if ( RtlCompareMemory(&Source1, &GUID_USB_CAPABILITY_DEVICE_CONNECTION_FULL_SPEED_COMPATIBLE, 0x10u) != 16 )
        {
          if ( RtlCompareMemory(&Source1, &GUID_USB_CAPABILITY_DEVICE_CONNECTION_LOW_SPEED_COMPATIBLE, 0x10u) != 16
            && RtlCompareMemory(&Source1, &GUID_USB_CAPABILITY_SSP_ISOCH_PIPE_FLAGS, 0x10u) != 16 )
          {
            goto LABEL_15;
          }
          goto LABEL_40;
        }
        v108 = *(_DWORD *)(*(_QWORD *)(v7 + 24) + 1464LL) & 0xB00;
      }
      v93 = -(v108 == 0);
    }
    Status = v93 & 0xC00000BB;
    goto LABEL_57;
  }
  v85 = v84 - 4;
  if ( !v85 )
    goto LABEL_195;
  v86 = v85 - 949;
  if ( !v86 )
  {
    a2->AssociatedIrp.MasterIrp->AssociatedIrp.MasterIrp = *(_IRP **)(*(_QWORD *)(v7 + 24) + 24LL);
    goto LABEL_15;
  }
  v87 = v86 - 4;
  if ( v87 )
  {
    v88 = v87 - 7;
    if ( !v88 )
    {
      *(_QWORD *)(CurrentStackLocation->Parameters.WMI.ProviderId + 8) = *(_QWORD *)(*(_QWORD *)(v7 + 24) + 24LL);
      goto LABEL_15;
    }
    v89 = v88 - 1016;
    if ( v89 )
    {
      if ( v89 != 4 )
        goto LABEL_229;
      if ( !KeGetCurrentIrql() )
      {
        DeviceBusInfo = HUBPDO_UnregisterPortPLDRCapability(*(_QWORD *)(v7 + 24));
        goto LABEL_132;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v91 = 71;
LABEL_233:
        LOBYTE(v90) = 3;
        WPP_RECORDER_SF_(
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 24) + 8LL) + 1432LL),
          v90,
          5,
          v91,
          (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids);
      }
    }
    else
    {
      if ( !KeGetCurrentIrql() )
      {
        DeviceBusInfo = HUBPDO_RegisterPortPLDRCapability(*(_QWORD *)(v7 + 24));
        goto LABEL_132;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v91 = 70;
        goto LABEL_233;
      }
    }
    Status = -1073741808;
    goto LABEL_57;
  }
LABEL_15:
  ++a2->CurrentLocation;
  ++a2->Tail.Overlay.CurrentStackLocation;
  return (unsigned int)IofCallDriver(*(PDEVICE_OBJECT *)(v7 + 8), a2);
}

```

## disassembly

```asm
0x1400165c0  mov     [rsp-38h+arg_10], rbx
0x1400165c5  push    rbp
0x1400165c6  push    rsi
0x1400165c7  push    rdi
0x1400165c8  push    r12
0x1400165ca  push    r13
0x1400165cc  push    r14
0x1400165ce  push    r15
0x1400165d0  mov     rbp, rsp
0x1400165d3  sub     rsp, 80h
0x1400165da  mov     rax, cs:__security_cookie
0x1400165e1  xor     rax, rsp
0x1400165e4  mov     [rbp+var_8], rax
0x1400165e8  mov     r8, cs:off_14006B1D0
0x1400165ef  xor     eax, eax
0x1400165f1  mov     [rbp+Event.Header.WaitListHead.Blink], rax
0x1400165f5  xorps   xmm0, xmm0
0x1400165f8  mov     rax, cs:WdfFunctions_01015
0x1400165ff  mov     r13, rdx
0x140016602  mov     rbx, rcx
0x140016605  mov     qword ptr [rbp+var_28], rcx
0x140016609  movups  xmmword ptr [rbp+Event.Header.___u0], xmm0
0x14001660d  mov     rdx, rcx
0x140016610  mov     rcx, cs:WdfDriverGlobals
0x140016617  movups  [rbp+Source1], xmm0
0x14001661b  mov     rax, [rax+650h]
0x140016622  call    _guard_dispatch_icall
0x140016627  mov     r14, [r13+0B8h]
0x14001662e  lea     rsi, WPP_RECORDER_INITIALIZED
0x140016635  mov     r10d, 1
0x14001663b  mov     [rbp+var_48], r14
0x14001663f  mov     rdi, rax
0x140016642  lea     r15, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x140016649  mov     r8d, 49104Bh
0x14001664f  cmp     byte ptr [r14], 0Eh
0x140016653  mov     eax, [r14+18h]
0x140016657  lea     r12d, [r10+3]
0x14001665b  mov     [rbp+var_50], eax
0x14001665e  jnz     loc_140016708
0x140016664  sub     eax, 220464h
0x140016669  jz      loc_140016C05
0x14001666f  sub     eax, r12d
0x140016672  jz      short loc_1400166EA
0x140016674  sub     eax, r12d
0x140016677  jz      loc_140016C05
0x14001667d  sub     eax, r12d
0x140016680  jz      loc_140016C05
0x140016686  sub     eax, r12d
0x140016689  jz      short loc_1400166C1
0x14001668b  sub     eax, r12d
0x14001668e  jz      short loc_1400166C1
0x140016690  sub     eax, r12d
0x140016693  jz      short loc_1400166C1
0x140016695  cmp     eax, r12d
0x140016698  jnz     loc_140017667
0x14001669e  cmp     dword ptr [r14+8], 18h
0x1400166a3  jnz     short loc_1400166F8
0x1400166a5  cmp     dword ptr [r14+10h], 18h
0x1400166aa  jnz     short loc_1400166F8
0x1400166ac  mov     rdx, [r13+18h]
0x1400166b0  test    rdx, rdx
0x1400166b3  jz      short loc_1400166F8
0x1400166b5  mov     rax, [rdi+18h]
0x1400166b9  mov     rcx, [rax+18h]
0x1400166bd  mov     [rdx+4], rcx
0x1400166c1  inc     byte ptr [r13+43h]
0x1400166c5  mov     rdx, r13; Irp
0x1400166c8  add     qword ptr [r13+0B8h], 48h ; 'H'
0x1400166d0  mov     rcx, [rdi+8]; DeviceObject
0x1400166d4  call    cs:__imp_IofCallDriver
0x1400166db  nop     dword ptr [rax+rax+00h]
0x1400166e0  mov     ebx, eax
0x1400166e2  mov     eax, ebx
0x1400166e4  jmp     loc_14001788C
0x1400166ea  cmp     dword ptr [r14+8], 24h ; '$'
0x1400166ef  jnz     short loc_1400166F8
0x1400166f1  cmp     dword ptr [r14+10h], 24h ; '$'
0x1400166f6  jmp     short loc_1400166AA
0x1400166f8  mov     ebx, 0C000000Dh
0x1400166fd  mov     r14d, 2
0x140016703  jmp     loc_1400174C7
0x140016708  xor     dl, dl
0x14001670a  cmp     eax, 220003h
0x14001670f  jnz     loc_1400167A3
0x140016715  mov     rax, [r14+8]
0x140016719  movzx   ecx, word ptr [rax+2]
0x14001671d  mov     eax, [rbp+var_50]
0x140016720  sub     cx, 35h ; '5'
0x140016724  cmp     cx, r10w
0x140016728  ja      short loc_14001672D
0x14001672a  mov     dl, r10b
0x14001672d  cmp     byte ptr [rdi], 0
0x140016730  jz      loc_14001682C
0x140016736  test    dl, dl
0x140016738  jnz     loc_14001682C
0x14001673e  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140016745  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14001674c  jz      short loc_14001677F
0x14001674e  mov     rax, [rdi+18h]
0x140016752  lea     r15, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x140016759  mov     r9d, 3Ah ; ':'
0x14001675f  mov     qword ptr [rsp+80h+Priority], r13
0x140016764  mov     dl, 3
0x140016766  mov     qword ptr [rsp+80h+BugCheckOnFailure], r15
0x14001676b  mov     rcx, [rax+8]
0x14001676f  lea     r8d, [r9-35h]
0x140016773  mov     rcx, [rcx+598h]
0x14001677a  call    WPP_RECORDER_SF_q
0x14001677f  mov     esi, [rbp+var_50]
0x140016782  mov     ebx, 0C000000Eh
0x140016787  cmp     esi, 220003h
0x14001678d  jnz     loc_1400168ED
0x140016793  mov     rax, [r14+8]
0x140016797  mov     dword ptr [rax+4], 80000300h
0x14001679e  jmp     loc_1400168ED
0x1400167a3  cmp     eax, 490007h
0x1400167a8  jz      short loc_1400167C9
0x1400167aa  cmp     eax, r8d
0x1400167ad  jz      short loc_1400167C9
0x1400167af  cmp     eax, 220FB3h
0x1400167b4  jnz     short loc_1400167CC
0x1400167b6  mov     eax, [rdi+20h]
0x1400167b9  test    al, 20h
0x1400167bb  mov     eax, [rbp+var_50]
0x1400167be  jz      loc_14001672D
0x1400167c4  jmp     loc_14001672A
0x1400167c9  mov     dl, r10b
0x1400167cc  cmp     eax, 220463h
0x1400167d1  jnz     loc_14001672D
0x1400167d7  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400167de  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400167e5  jz      short loc_140016819
0x1400167e7  mov     rax, [rdi+18h]
0x1400167eb  lea     r15, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x1400167f2  mov     r9d, 39h ; '9'
0x1400167f8  mov     qword ptr [rsp+80h+Priority], r13
0x1400167fd  mov     dl, r12b
0x140016800  mov     qword ptr [rsp+80h+BugCheckOnFailure], r15
0x140016805  mov     rcx, [rax+8]
0x140016809  lea     r8d, [r9-34h]
0x14001680d  mov     rcx, [rcx+598h]
0x140016814  call    WPP_RECORDER_SF_q
0x140016819  mov     rax, [rdi+18h]
0x14001681d  bts     dword ptr [rax+668h], 13h
0x140016825  xor     ebx, ebx
0x140016827  jmp     loc_1400168EA
0x14001682c  cmp     eax, 220003h
0x140016831  jnz     loc_140016C89
0x140016837  mov     r14, [r14+8]
0x14001683b  movzx   edx, word ptr [r14+2]
0x140016840  lea     eax, [rdx-9]
0x140016843  cmp     ax, r10w
0x140016847  jbe     loc_140016C28
0x14001684d  lea     eax, [rdx-39h]
0x140016850  cmp     ax, r10w
0x140016854  jbe     loc_140016C28
0x14001685a  mov     ecx, edx
0x14001685c  cmp     edx, 2Ah ; '*'
0x14001685f  ja      loc_140016C0F
0x140016865  jz      loc_140016AFB
0x14001686b  test    edx, edx
0x14001686d  jz      loc_140016C4A
0x140016873  sub     ecx, r10d
0x140016876  jz      loc_140016C4A
0x14001687c  sub     ecx, 0Ah
0x14001687f  jz      loc_1400169DB
0x140016885  sub     ecx, 8
0x140016888  jz      short loc_140016892
0x14001688a  cmp     ecx, 0Bh
0x14001688d  jmp     loc_140016C26
0x140016892  mov     rcx, [rdi+18h]
0x140016896  test    dword ptr [rcx+668h], 80000h
0x1400168a0  jz      loc_140016C28
0x1400168a6  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400168ad  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400168b4  jz      short loc_1400168E1
0x1400168b6  mov     rcx, [rcx+8]
0x1400168ba  mov     r9d, 3Ch ; '<'
0x1400168c0  mov     dl, r12b
0x1400168c3  mov     rcx, [rcx+598h]
0x1400168ca  lea     r15, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x1400168d1  mov     r8d, 5
0x1400168d7  mov     qword ptr [rsp+80h+BugCheckOnFailure], r15
0x1400168dc  call    WPP_RECORDER_SF_
0x1400168e1  mov     ebx, 0C00000BBh
0x1400168e6  mov     r14, [rbp+var_48]
0x1400168ea  mov     esi, [rbp+var_50]
0x1400168ed  mov     rax, cs:WdfFunctions_01015
0x1400168f4  mov     rcx, cs:WdfDriverGlobals
0x1400168fb  mov     r8, cs:off_14006B2C0
0x140016902  mov     rax, [rax+650h]
0x140016909  mov     rdx, [rcx]
0x14001690c  call    _guard_dispatch_icall
0x140016911  test    dword ptr [rax+4], 1000h
0x140016918  jz      loc_140017872
0x14001691e  mov     rax, cs:g_IoGetActivityIdIrp
0x140016925  xorps   xmm0, xmm0
0x140016928  movups  [rbp+var_28], xmm0
0x14001692c  test    rax, rax
0x14001692f  jz      short loc_14001693D
0x140016931  lea     rdx, [rbp+var_28]
0x140016935  mov     rcx, r13
0x140016938  call    _guard_dispatch_icall
0x14001693d  test    cs:byte_14006ED41, r12b
0x140016944  jz      short loc_140016962
0x140016946  mov     r9, [rdi+18h]
0x14001694a  lea     r8, [rbp+var_28]
0x14001694e  lea     rdx, USBHUB3_ETW_EVENT_DEVICE_INTERNAL_IOCTL_START
0x140016955  mov     [rsp+80h+BugCheckOnFailure], esi
0x140016959  mov     r9, [r9+18h]
0x14001695d  call    McTemplateK0pq_EtwWriteTransfer
0x140016962  cmp     esi, 220003h
0x140016968  jnz     loc_14001781A
0x14001696e  test    cs:byte_14006ED41, r12b
0x140016975  mov     r15, [r14+8]
0x140016979  jz      loc_140017872
0x14001697f  mov     r9, [rdi+18h]
0x140016983  lea     r8, [rbp+var_28]
0x140016987  movzx   eax, word ptr [r15+2]
0x14001698c  lea     rdx, USBHUB3_ETW_EVENT_DEVICE_URB_START
0x140016993  mov     [rsp+80h+BugCheckOnFailure], eax
0x140016997  mov     r9, [r9+18h]
0x14001699b  call    McTemplateK0pq_EtwWriteTransfer
0x1400169a0  test    cs:byte_14006ED41, r12b
0x1400169a7  jz      loc_140017872
0x1400169ad  mov     r9, [rdi+18h]
0x1400169b1  lea     r8, [rbp+var_28]
0x1400169b5  movzx   ecx, word ptr [r15+2]
0x1400169ba  lea     rdx, USBHUB3_ETW_EVENT_DEVICE_URB_COMPLETE
0x1400169c1  mov     eax, [r15+4]
0x1400169c5  mov     [rsp+80h+Priority], eax
0x1400169c9  mov     r9, [r9+18h]
0x1400169cd  mov     [rsp+80h+BugCheckOnFailure], ecx
0x1400169d1  call    McTemplateK0pqq_EtwWriteTransfer
0x1400169d6  jmp     loc_140017849
0x1400169db  mov     rcx, [rdi+18h]
0x1400169df  mov     eax, 200h
0x1400169e4  cmp     [rcx+7CEh], ax
0x1400169eb  ja      short loc_1400169FA
0x1400169ed  mov     rax, [rcx+18h]
0x1400169f1  mov     [r14+8], rax
0x1400169f5  jmp     loc_1400166C1
0x1400169fa  mov     rdx, r14
0x1400169fd  mov     rcx, rdi
0x140016a00  call    HUBPDO_ValidateURB
0x140016a05  mov     ebx, eax
0x140016a07  test    eax, eax
0x140016a09  js      loc_1400168E6
0x140016a0f  mov     rcx, [r14+30h]; MemoryDescriptorList
0x140016a13  mov     r15d, 1
0x140016a19  test    rcx, rcx
0x140016a1c  jz      short loc_140016A53
0x140016a1e  test    byte ptr [rcx+0Ah], 5
0x140016a22  jz      short loc_140016A2A
0x140016a24  mov     r10, [rcx+18h]
0x140016a28  jmp     short loc_140016A57
0x140016a2a  mov     [rsp+80h+Priority], 40000010h; Priority
0x140016a32  xor     r9d, r9d; RequestedAddress
0x140016a35  mov     r8d, r15d; CacheType
0x140016a38  mov     [rsp+80h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140016a40  xor     edx, edx; AccessMode
0x140016a42  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140016a49  nop     dword ptr [rax+rax+00h]
0x140016a4e  mov     r10, rax
0x140016a51  jmp     short loc_140016A57
0x140016a53  mov     r10, [r14+28h]
0x140016a57  test    r10, r10
0x140016a5a  jnz     short loc_140016A6E
0x140016a5c  mov     ebx, 0C000000Dh
0x140016a61  mov     dword ptr [r14+4], 80000300h
0x140016a69  jmp     loc_1400168E6
0x140016a6e  movzx   ecx, byte ptr [r14+83h]
0x140016a76  sub     ecx, 1
0x140016a79  jz      short loc_140016AB3
0x140016a7b  cmp     ecx, 1
0x140016a7e  jnz     loc_140016C28
0x140016a84  cmp     byte ptr [r14+82h], 0
0x140016a8c  mov     rdx, [rdi+18h]
0x140016a90  jbe     short loc_140016A9B
0x140016a92  mov     rax, [rdx+18h]
0x140016a96  jmp     loc_1400169F1
0x140016a9b  mov     rdx, [rdx+7E8h]
0x140016aa2  lea     rsi, [r14+24h]
0x140016aa6  mov     eax, [rsi]
0x140016aa8  movzx   ebx, word ptr [rdx+2]
0x140016aac  cmp     ebx, eax
0x140016aae  cmovnb  ebx, eax
0x140016ab1  jmp     short loc_140016ACF
0x140016ab3  mov     rdx, [rdi+18h]
0x140016ab7  lea     rsi, [r14+24h]
0x140016abb  mov     eax, [rsi]
0x140016abd  add     rdx, 7CCh; Src
0x140016ac4  mov     ebx, 12h
0x140016ac9  cmp     eax, ebx
0x140016acb  ja      short loc_140016ACF
0x140016acd  mov     ebx, eax
0x140016acf  or      [r14+20h], r15d
0x140016ad3  mov     r9d, 8
0x140016ad9  mov     eax, [r14+20h]
0x140016add  test    r9b, al
  ... truncated ...
```
