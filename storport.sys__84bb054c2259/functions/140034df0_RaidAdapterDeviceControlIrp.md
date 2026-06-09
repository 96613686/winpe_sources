# RaidAdapterDeviceControlIrp

- ea: `0x140034df0`
- end: `0x14003628a`
- name: `RaidAdapterDeviceControlIrp`
- size: `5274`
- prototype: ``
- caller_count: `1`
- callee_count: `66`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140034cd0`

## callees

- `0x140006f50`
- `0x140025144`
- `0x14002a0d8`
- `0x1400312c8`
- `0x140034df0`
- `0x1400378a8`
- `0x14003db68`
- `0x14003e0dc`
- `0x14003e138`
- `0x14004acac`
- `0x14004d910`
- `0x140064200`
- `0x14006d1c0`
- `0x14006d298`
- `0x14006e7a4`
- `0x140071f3c`
- `0x140072c44`
- `0x140074770`
- `0x140076138`
- `0x14007817c`
- `0x14008479c`
- `0x1400848c4`
- `0x1400869a8`
- `0x140086d68`
- `0x1400885b0`
- `0x1400889c8`
- `0x140088e00`
- `0x1400892b0`
- `0x1400897fc`
- `0x14008a124`
- `0x14008a554`
- `0x14008a930`
- `0x14008b7ac`
- `0x14008bc84`
- `0x14008bffc`
- `0x14008c660`
- `0x14008d494`
- `0x14008d8a0`
- `0x14008e96c`
- `0x14008ee48`
- `0x14008f1bc`
- `0x14008f97c`
- `0x140090088`
- `0x140090488`
- `0x14009084c`
- `0x140090cb4`
- `0x140093e14`
- `0x140098968`
- `0x1400a7bdc`
- `0x1400a80e8`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x140034e62`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140034f2e`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140035489`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140035f15`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140034e62`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140034f2e`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140035489`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140035f15`
- `ntoskrnl!IofCompleteRequest` at `0x1400351d9`
- `ntoskrnl!IofCompleteRequest` at `0x140035745`
- `ntoskrnl!IofCompleteRequest` at `0x1400351d9`
- `ntoskrnl!IofCompleteRequest` at `0x140035745`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140036254`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140036254`

## pseudocode

```c
__int64 __fastcall RaidAdapterDeviceControlIrp(__int64 a1, __int64 a2)
{
  char v2; // r12
  int v5; // r15d
  __int64 v6; // rcx
  char v7; // r14
  unsigned int v8; // r13d
  unsigned __int64 v9; // rax
  bool v10; // zf
  unsigned __int64 v11; // rcx
  __int64 v12; // rdx
  int *v13; // rax
  int v14; // ecx
  __int64 *v15; // rdx
  __int64 v16; // rdx
  unsigned int v17; // r12d
  unsigned __int8 v18; // r10
  char *v19; // r11
  char v20; // si
  _BYTE *v21; // r9
  __int64 v22; // r15
  char v23; // r13
  unsigned __int64 v24; // rdi
  __int64 v25; // r8
  int v26; // ecx
  char v27; // cl
  char v28; // di
  char v29; // r11
  char v30; // r8
  _BYTE *v31; // rax
  char *v32; // r8
  unsigned int v33; // eax
  __int64 v35; // rcx
  unsigned int inserted; // esi
  __int64 v37; // r8
  unsigned int LockingObjectMetadata; // eax
  __int64 v39; // rcx
  unsigned __int64 v40; // rcx
  unsigned __int8 *v41; // rdx
  int v42; // eax
  int *v43; // rax
  int v44; // ecx
  __int64 *v45; // rdx
  __int64 v46; // rdx
  unsigned int v47; // r13d
  unsigned __int8 v48; // r10
  char *v49; // r11
  _BYTE *v50; // r9
  __int64 v51; // r12
  unsigned __int64 v52; // r15
  __int64 v53; // r8
  int v54; // ecx
  char v55; // r12
  char v56; // cl
  char v57; // r15
  char v58; // r11
  char v59; // r8
  _BYTE *v60; // rax
  char *v61; // r8
  unsigned int v62; // eax
  __int64 v63; // rdx
  unsigned int v64; // r13d
  unsigned __int8 v65; // r11
  char *v66; // r10
  _BYTE *v67; // r9
  __int64 v68; // r12
  unsigned __int64 v69; // r15
  __int64 v70; // r8
  int v71; // ecx
  char v72; // r12
  char v73; // cl
  char v74; // r15
  char v75; // r10
  char v76; // r8
  _BYTE *v77; // rax
  char *v78; // r8
  unsigned int v79; // eax
  unsigned int v80; // eax
  char v81; // [rsp+60h] [rbp-19h]
  char v82; // [rsp+60h] [rbp-19h]
  char v83; // [rsp+61h] [rbp-18h]
  char v84; // [rsp+61h] [rbp-18h]
  _BYTE v85[2]; // [rsp+62h] [rbp-17h] BYREF
  unsigned int v86; // [rsp+64h] [rbp-15h]
  unsigned int v87; // [rsp+68h] [rbp-11h]
  __int128 v88; // [rsp+70h] [rbp-9h] BYREF
  __int128 v89; // [rsp+80h] [rbp+7h] BYREF

  v2 = 0;
  v89 = 0;
  v85[0] = 0;
  v5 = RaidAcquireAdapterRemoveLock();
  v6 = *(_QWORD *)(a2 + 184);
  v7 = 1;
  v87 = v5;
  v8 = *(_DWORD *)(v6 + 24);
  v86 = v8;
  if ( StorEtwLoggingEnabled )
  {
    IoGetActivityIdIrp(a2, &v89);
    if ( v8 == 315396 || (v9 = v8 - 315412, (unsigned int)v9 <= 0x34) && (v6 = 0x11000011000001LL, _bittest64(&v6, v9)) )
    {
      if ( (byte_140177433 & 1) != 0 )
        McTemplateK0pddd_EtwWriteTransfer(
          *(unsigned __int8 *)(*(_QWORD *)(a2 + 184) + 1LL),
          (unsigned int)EventPassThrough,
          (unsigned int)&v89,
          a2,
          **(_BYTE **)(a2 + 184),
          *(_BYTE *)(*(_QWORD *)(a2 + 184) + 1LL),
          v8);
    }
    else if ( (byte_140177432 & 2) != 0 )
    {
      McTemplateK0pddd_EtwWriteTransfer(
        *(unsigned __int8 *)(*(_QWORD *)(a2 + 184) + 1LL),
        (unsigned int)EventIOCTL,
        (unsigned int)&v89,
        a2,
        **(_BYTE **)(a2 + 184),
        *(_BYTE *)(*(_QWORD *)(a2 + 184) + 1LL),
        v8);
    }
  }
  if ( v5 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qqDD(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        WPP_17a2ccf459a039b6fd190e52d544bf1c_Traceguids,
        a1,
        a2,
        HIWORD(v8),
        (v8 >> 2) & 0xFFF);
    }
    inserted = ExtensionAdapterIoctlReplace(v6, a1, a2);
    if ( inserted != -1073741822 )
      goto LABEL_398;
    ExtensionAdapterIoctlPre(v35, a1, a2);
    if ( v8 > 0x2D5F90 )
    {
      if ( v8 > 0x2DDC10 )
      {
        if ( v8 > 0x2DDF9C )
        {
          switch ( v8 )
          {
            case 0x2DDFA0u:
              if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
                || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
              {
                LockingObjectMetadata = RaidAdapterStorageTcgEraseLockingObject(a1, (PIRP)a2);
                goto LABEL_395;
              }
              break;
            case 0x2DDFA4u:
              if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
                || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
              {
                LockingObjectMetadata = RaidAdapterStorageTcgSetLockingObject(a1, (PIRP)a2);
                goto LABEL_395;
              }
              break;
            case 0x2DDFACu:
              if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
                || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
              {
                LockingObjectMetadata = RaidAdapterStorageTcgSetLockingObjectMetadata(a1, a2);
                goto LABEL_395;
              }
              break;
            case 0x2DDFB0u:
              if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
                || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
              {
                LockingObjectMetadata = RaidAdapterStorageTcgResetState(a1, a2);
                goto LABEL_395;
              }
              break;
            case 0x32C000u:
            case 0x32C038u:
              LockingObjectMetadata = RaForwardIrp(*(_QWORD *)(a1 + 24), a2);
              goto LABEL_395;
            default:
              goto LABEL_329;
          }
        }
        else
        {
          switch ( v8 )
          {
            case 0x2DDF9Cu:
              if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
                || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
              {
                LockingObjectMetadata = RaidAdapterStorageTcgSetLockingObjectAuthKey(a1, (PIRP)a2);
                goto LABEL_395;
              }
              break;
            case 0x2DDCD8u:
              if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
                || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
              {
                LockingObjectMetadata = RaidAdapterMFNDNameSpacePageMapControl(a1, a2);
                goto LABEL_395;
              }
              break;
            case 0x2DDF84u:
              if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
                || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
              {
                LockingObjectMetadata = RaidAdapterStorageTcgActivateLocking(a1, (PIRP)a2);
                goto LABEL_395;
              }
              break;
            case 0x2DDF88u:
              if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
                || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
              {
                LockingObjectMetadata = RaidAdapterStorageTcgRevertConfig(a1, (PIRP)a2);
                goto LABEL_395;
              }
              break;
            case 0x2DDF8Cu:
              if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
                || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
              {
                LockingObjectMetadata = RaidAdapterStorageTcgSetSpAuthorityKey(a1, (PIRP)a2);
                goto LABEL_395;
              }
              break;
            case 0x2DDF94u:
              if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
                || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
              {
                LockingObjectMetadata = RaidAdapterStorageTcgAssignLockingObject(a1, (PIRP)a2);
                goto LABEL_395;
              }
              break;
            case 0x2DDF98u:
              if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
                || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
              {
                LockingObjectMetadata = RaidAdapterStorageTcgDeassignLockingObject(a1, (PIRP)a2);
                goto LABEL_395;
              }
              break;
            default:
              goto LABEL_329;
          }
        }
      }
      else if ( v8 == 3005456 )
      {
        if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
          || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
        {
          LockingObjectMetadata = RaidAdapterHwBootPartitionActivateIoctl(a1, a2);
          goto LABEL_395;
        }
      }
      else if ( v8 > 0x2DD04C )
      {
        switch ( v8 )
        {
          case 0x2DD200u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              LockingObjectMetadata = RaAdapterSetTemperatureThresholdIoctl(a1, a2);
              goto LABEL_395;
            }
            break;
          case 0x2DD3C0u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              LockingObjectMetadata = RaAdapterProtocolCommandIoctl(a1, a2);
              goto LABEL_395;
            }
            break;
          case 0x2DD684u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              LockingObjectMetadata = RaidAdapterSetBootLunIoctl(a1, a2);
              goto LABEL_395;
            }
            break;
          case 0x2DDC04u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              LockingObjectMetadata = RaidAdapterHwFirmwareDownloadIoctl(a1, a2);
              goto LABEL_395;
            }
            break;
          case 0x2DDC08u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              LockingObjectMetadata = RaidAdapterHwFirmwareActivateIoctl(a1, a2);
              goto LABEL_395;
            }
            break;
          case 0x2DDC0Cu:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              LockingObjectMetadata = RaidAdapterHwBootPartitionDownloadIoctl(a1, a2);
              goto LABEL_395;
            }
            break;
          default:
            goto LABEL_329;
        }
      }
      else
      {
        switch ( v8 )
        {
          case 0x2DD04Cu:
            LockingObjectMetadata = RaidAdapterStorageSetPciLinkBandwidthIoctl(a1, a2);
            goto LABEL_395;
          case 0x2D5FA8u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              LockingObjectMetadata = RaidAdapterStorageTcgGetLockingObjectMetadata(a1, a2);
              goto LABEL_395;
            }
            break;
          case 0x2D93F4u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              LockingObjectMetadata = RaidAdapterStorageInternalSetPropertyIoctl(a1, a2);
              goto LABEL_395;
            }
            break;
          case 0x2D93FCu:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              LockingObjectMetadata = RaidAdapterStorageSetPropertyIoctl(a1, a2);
              goto LABEL_395;
            }
            break;
          case 0x2D9CD0u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              LockingObjectMetadata = RaidAdapterReconfigureMFND(a1, a2);
              goto LABEL_395;
            }
            break;
          case 0x2D9CD4u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              LockingObjectMetadata = RaidAdapterMFNDChildPFControl(a1, a2);
              goto LABEL_395;
            }
            break;
          case 0x2D9CE2u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              LockingObjectMetadata = RaidAdapterMFNDNameSpaceWrite(a1, (PIRP)a2);
              goto LABEL_395;
            }
            break;
          case 0x2DD044u:
            LockingObjectMetadata = RaidAdapterStorageNotificationConfigureIoctl(a1, a2);
            goto LABEL_395;
          default:
            goto LABEL_329;
        }
      }
      goto LABEL_392;
    }
    if ( v8 == 2973584 )
    {
      if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
        || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
      {
        LockingObjectMetadata = RaidAdapterStorageTcgEnumerateLockingObjects(a1, a2);
        goto LABEL_395;
      }
      goto LABEL_392;
    }
    if ( v8 > 0x2D1680 )
    {
      if ( v8 > 0x2D1F80 )
      {
        switch ( v8 )
        {
          case 0x2D4C1Cu:
            LockingObjectMetadata = StorageGetSystemFeatureSupportIoctl((PIRP)a2);
            goto LABEL_395;
          case 0x2D5000u:
            LockingObjectMetadata = RaidAdapterStorageResetBusIoctl(a1, a2);
            goto LABEL_395;
          case 0x2D5014u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              LockingObjectMetadata = RaidAdapterStorageBreakReservationIoctl(a1, a2);
              goto LABEL_395;
            }
            break;
          case 0x2D5020u:
            LockingObjectMetadata = RaidAdapterStorageDeviceResetIoctl(a1, a2);
            goto LABEL_395;
          case 0x2D5048u:
            LockingObjectMetadata = RaidAdapterStorageNotificationGetInfoIoctl(a1, a2);
            goto LABEL_395;
          case 0x2D5CDDu:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              LockingObjectMetadata = RaidAdapterMFNDNameSpaceRead(a1, (PIRP)a2);
              goto LABEL_395;
            }
            break;
          default:
            goto LABEL_329;
        }
      }
      else
      {
        switch ( v8 )
        {
          case 0x2D1F80u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              LockingObjectMetadata = RaidAdapterStorageTcgQueryCapability(a1, a2);
              goto LABEL_395;
            }
            break;
          case 0x2D1C00u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              LockingObjectMetadata = RaidAdapterHwFirmwareGetInfoIoctl((_QWORD *)a1, a2);
              goto LABEL_395;
            }
            break;
          case 0x2D1C14u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              LockingObjectMetadata = RaidAdapterHwBootPartitionGetInfoIoctl(a1, a2);
              goto LABEL_395;
            }
            break;
          case 0x2D1C94u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              LockingObjectMetadata = RaidAdapterPowerCapIoctl(a1, a2);
              goto LABEL_395;
            }
            break;
          case 0x2D1C98u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              LockingObjectMetadata = RaidAdapterRpmbRequest(a1, a2);
              goto LABEL_395;
            }
            break;
          case 0x2D1CA0u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              LockingObjectMetadata = RaidAdapterDiagnosticIoctl(a1, a2);
              goto LABEL_395;
            }
            break;
          case 0x2D1CCCu:
            LockingObjectMetadata = RaidAdapterSetLedState(a1, a2);
            goto LABEL_395;
          default:
            goto LABEL_329;
        }
      }
LABEL_392:
      inserted = RaInsertDFxQueue(*(_QWORD *)(a1 + 8), a2);
      if ( !inserted )
        inserted = 259;
      goto LABEL_396;
    }
    if ( v8 == 2954880 )
    {
      if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
        || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
      {
        LockingObjectMetadata = RaidAdapterQueryBootLunsIoctl(a1, a2);
        goto LABEL_395;
      }
      goto LABEL_392;
    }
    if ( v8 <= 0x4D038 )
    {
      switch ( v8 )
      {
        case 0x4D038u:
          if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
            || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
          {
            return RaidAdapterMiniportProcessServiceRequest(a1, a2);
          }
          goto LABEL_392;
        case 0x4100Cu:
          LockingObjectMetadata = RaidAdapterScsiGetInquiryDataIoctl(a1, a2);
          goto LABEL_395;
        case 0x41010u:
          LockingObjectMetadata = RaidAdapterScsiGetCapabilitiesIoctl(a1, a2);
          goto LABEL_395;
        case 0x41018u:
          LockingObjectMetadata = RaidAdapterScsiGetAddressIoctl(a1, a2);
          goto LABEL_395;
        case 0x4101Cu:
          LockingObjectMetadata = RaidAdapterScsiRescanBusIoctl(a1, a2);
          goto LABEL_395;
      }
      if ( v8 != 315396 )
      {
        if ( v8 != 315400 )
        {
          if ( v8 == 315412 )
          {
LABEL_93:
            LOBYTE(v37) = 1;
LABEL_94:
            LockingObjectMetadata = RaidAdapterPassThrough(a1, a2, v37);
LABEL_395:
            inserted = LockingObjectMetadata;
LABEL_396:
            v80 = ExtensionAdapterIoctlPost(v39, a1, a2);
            v2 = v85[0];
            if ( v80 != -1073741822 )
              inserted = v80;
LABEL_398:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_qqDD(
                WPP_GLOBAL_Control->AttachedDevice,
                11,
                WPP_17a2ccf459a039b6fd190e52d544bf1c_Traceguids,
                a1,
                a2,
                v8,
                inserted);
            }
            if ( !v2 )
              ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 320));
            return inserted;
          }
LABEL_329:
          v10 = StorEtwLoggingEnabled == 0;
          inserted = -1073741637;
          *(_DWORD *)(a2 + 48) = -1073741637;
          *(_BYTE *)(a2 + 141) = -84;
          if ( v10 )
            goto LABEL_184;
          v88 = 0;
          IoGetActivityIdIrp(a2, &v88);
          v41 = *(unsigned __int8 **)(a2 + 184);
          if ( *v41 != 14 )
          {
            v42 = *v41 - 15;
            if ( *v41 == 15 )
            {
              if ( byte_140177431 < 0 )
              {
                v63 = *((_QWORD *)v41 + 1);
                if ( *(_BYTE *)(v63 + 2) == 40 )
                {
                  if ( *(_DWORD *)(v63 + 20) )
                    goto LABEL_184;
                  v64 = *(_DWORD *)(v63 + 56);
                  if ( !v64 )
                    goto LABEL_184;
                  v65 = 0;
                  v66 = 0;
                  v82 = 0;
                  v67 = 0;
                  v84 = 0;
                  v68 = 0;
                  do
                  {
                    v40 = *(unsigned int *)(v63 + 4 * v68 + 120);
                    if ( (unsigned int)v40 >= 0x80 )
                    {
                      v69 = *(unsigned int *)(v63 + 16);
                      if ( (unsigned int)v40 < (unsigned int)v69 )
                      {
                        v70 = (unsigned int)v40;
                        v71 = *(_DWORD *)(v40 + v63) - 64;
                        if ( v71 )
                        {
                          LODWORD(v40) = v71 - 1;
                          if ( (_DWORD)v40 )
                          {
                            if ( (_DWORD)v40 == 1 )
                            {
                              LODWORD(v40) = v70 + 40;
                              if ( v70 + 40 <= v69 )
                              {
                                if ( *(_DWORD *)(v70 + v63 + 12) )
                                  v66 = (char *)(v70 + v63 + 32);
                                v67 = *(_BYTE **)(v70 + v63 + 24);
LABEL_346:
                                v72 = *(_BYTE *)(v70 + v63 + 8);
                                v65 = *(_BYTE *)(v70 + v63 + 9);
                                goto LABEL_355;
                              }
                            }
                          }
                          else
                          {
                            LODWORD(v40) = v70 + 56;
                            if ( v70 + 56 <= v69 )
                            {
                              v84 = 1;
                              if ( *(_BYTE *)(v70 + v63 + 10) )
                                v66 = (char *)(v70 + v63 + 24);
                              v67 = *(_BYTE **)(v70 + v63 + 16);
                              v65 = *(_BYTE *)(v70 + v63 + 9);
                              v82 = *(_BYTE *)(v70 + v63 + 8);
                            }
                          }
                        }
                        else
                        {
                          LODWORD(v40) = v70 + 40;
                          if ( v70 + 40 <= v69 )
                          {
                            if ( *(_BYTE *)(v70 + v63 + 10) )
                              v66 = (char *)(v70 + v63 + 24);
                            v67 = *(_BYTE **)(v70 + v63 + 16);
                            goto LABEL_346;
                          }
                        }
                        if ( v84 )
                          break;
                      }
                    }
                    v68 = (unsigned int)(v68 + 1);
                  }
                  while ( (unsigned int)v68 < v64 );
                  v72 = v82;
LABEL_355:
                  if ( !v66 )
                    goto LABEL_184;
                  v73 = *v66;
                }
                else
                {
                  v73 = *(_BYTE *)(v63 + 72);
                  v67 = *(_BYTE **)(v63 + 32);
                  v65 = *(_BYTE *)(v63 + 11);
                  v72 = *(_BYTE *)(v63 + 4);
                  if ( *(_BYTE *)(v63 + 2) )
                    goto LABEL_184;
                }
                LOBYTE(v40) = v73 - 8;
                if ( (v40 & 0x5D) == 0 )
                {
                  v74 = *(_BYTE *)(v63 + 3);
                  if ( v74 == 1 || !v67 || !v65 )
                    goto LABEL_378;
                  LOBYTE(v63) = 0;
                  v75 = 0;
                  v76 = 0;
                  v40 = (unsigned __int64)&v67[v65];
                  v77 = v67 + 8;
                  if ( (unsigned __int8)((*v67 & 0x7F) - 114) <= 1u )
                  {
                    if ( (unsigned __int64)v77 <= v40 )
                    {
                      v75 = v67[2];
                      LOBYTE(v63) = v67[1] & 0xF;
                      v76 = v67[3];
                      goto LABEL_377;
                    }
                  }
                  else if ( (unsigned __int64)v77 <= v40 )
                  {
                    v78 = v67 + 13;
                    LOBYTE(v63) = v67[2] & 0xF;
                    v79 = v65;
                    if ( (unsigned int)(unsigned __int8)v67[7] + 8 <= v65 )
                      v79 = (unsigned __int8)v67[7] + 8;
                    v40 = (unsigned __int64)&v67[v79];
                    if ( (unsigned __int64)v78 <= v40 )
                      v75 = v67[12];
                    if ( (unsigned __int64)(v67 + 14) > v40 )
                      v76 = 0;
                    else
                      v76 = *v78;
LABEL_377:
                    if ( v7 )
                    {
LABEL_379:
                      McTemplateK0pduuuuup_EtwWriteTransfer(
                        v40,
                        v63,
                        (unsigned int)&v88,
                        a2,
                        *(_DWORD *)(a2 + 48),
                        v74,
                        v72,
                        v63,
                        v75,
                        v76,
                        a2);
                      goto LABEL_184;
                    }
LABEL_378:
                    LOBYTE(v63) = 0;
                    v75 = 0;
                    v76 = 0;
                    goto LABEL_379;
                  }
                  v7 = 0;
                  goto LABEL_377;
                }
              }
LABEL_184:
              IofCompleteRequest((PIRP)a2, 0);
              v8 = v86;
              goto LABEL_396;
            }
            goto LABEL_122;
          }
LABEL_181:
          if ( (byte_140177432 & 8) == 0 )
            goto LABEL_184;
          v45 = EventNonReadWriteRequestComplete;
          goto LABEL_183;
        }
        if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
          || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
        {
          LockingObjectMetadata = RaidAdapterScsiMiniportIoctlWithAddress(a1, a2, 0, 0, 0, 2);
          goto LABEL_395;
        }
        goto LABEL_392;
      }
LABEL_186:
      v37 = 0;
      goto LABEL_94;
    }
    if ( v8 == 315460 )
      goto LABEL_186;
    if ( v8 == 315464 )
      goto LABEL_93;
    if ( v8 != 2237444 )
    {
      switch ( v8 )
      {
        case 0x2D11D4u:
          LockingObjectMetadata = RaidAdapterStorageGetInternalDataIoctl(a1, a2);
          goto LABEL_395;
        case 0x2D13F8u:
          if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
            || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
          {
            LockingObjectMetadata = RaidAdapterStorageInternalQueryPropertyIoctl(a1, a2, v85);
            goto LABEL_395;
          }
          break;
        case 0x2D1400u:
          if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
            || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
          {
            LockingObjectMetadata = RaidAdapterStorageQueryPropertyIoctl(a1, a2);
            goto LABEL_395;
          }
          break;
        default:
          goto LABEL_329;
      }
      goto LABEL_392;
    }
    if ( *(_QWORD *)(a1 + 6296) )
    {
      LockingObjectMetadata = RaidAdapterNvmeVirtualizationIgnoredNamespacesIoctl(a1, a2);
      goto LABEL_395;
    }
    v10 = StorEtwLoggingEnabled == 0;
    inserted = -1073741637;
    *(_DWORD *)(a2 + 48) = -1073741637;
    *(_BYTE *)(a2 + 141) = -84;
    if ( v10 )
      goto LABEL_184;
    v88 = 0;
    IoGetActivityIdIrp(a2, &v88);
    v41 = *(unsigned __int8 **)(a2 + 184);
    if ( *v41 == 14 )
      goto LABEL_181;
    v42 = *v41 - 15;
    if ( *v41 != 15 )
    {
LABEL_122:
      if ( v42 != 12 )
        goto LABEL_184;
      if ( v41[1] == 7 && !*((_DWORD *)v41 + 2) )
      {
        if ( (byte_140177432 & 0x40) != 0 )
        {
          v43 = *(int **)(a2 + 56);
          if ( v43 )
            v44 = *v43;
          else
            v44 = 0;
          McTemplateK0pqd_EtwWriteTransfer(v44, (_DWORD)v41, (unsigned int)&v88, a2, v44, *(_DWORD *)(a2 + 48));
        }
        goto LABEL_184;
      }
      if ( (byte_140177432 & 0x20) == 0 )
        goto LABEL_184;
      v45 = EventPnpRequestComplete;
LABEL_183:
      McTemplateK0pd_EtwWriteTransfer(v40, v45, &v88, a2, *(_DWORD *)(a2 + 48));
      goto LABEL_184;
    }
    if ( byte_140177431 >= 0 )
      goto LABEL_184;
    v46 = *((_QWORD *)v41 + 1);
    if ( *(_BYTE *)(v46 + 2) == 40 )
    {
      if ( *(_DWORD *)(v46 + 20) )
        goto LABEL_184;
      v47 = *(_DWORD *)(v46 + 56);
      if ( !v47 )
        goto LABEL_184;
      v48 = 0;
      v49 = 0;
      v81 = 0;
      v50 = 0;
      v83 = 0;
      v51 = 0;
      do
      {
        v40 = *(unsigned int *)(v46 + 4 * v51 + 120);
        if ( (unsigned int)v40 >= 0x80 )
        {
          v52 = *(unsigned int *)(v46 + 16);
          if ( (unsigned int)v40 < (unsigned int)v52 )
          {
            v53 = (unsigned int)v40;
            v54 = *(_DWORD *)(v40 + v46) - 64;
            if ( v54 )
            {
              LODWORD(v40) = v54 - 1;
              if ( (_DWORD)v40 )
              {
                if ( (_DWORD)v40 == 1 )
                {
                  LODWORD(v40) = v53 + 40;
                  if ( v53 + 40 <= v52 )
                  {
                    if ( *(_DWORD *)(v53 + v46 + 12) )
                      v49 = (char *)(v53 + v46 + 32);
                    v50 = *(_BYTE **)(v53 + v46 + 24);
LABEL_146:
                    v55 = *(_BYTE *)(v53 + v46 + 8);
                    v48 = *(_BYTE *)(v53 + v46 + 9);
                    goto LABEL_155;
                  }
                }
              }
              else
              {
                LODWORD(v40) = v53 + 56;
                if ( v53 + 56 <= v52 )
                {
                  v83 = 1;
                  if ( *(_BYTE *)(v53 + v46 + 10) )
                    v49 = (char *)(v53 + v46 + 24);
                  v50 = *(_BYTE **)(v53 + v46 + 16);
                  v48 = *(_BYTE *)(v53 + v46 + 9);
                  v81 = *(_BYTE *)(v53 + v46 + 8);
                }
              }
            }
            else
            {
              LODWORD(v40) = v53 + 40;
              if ( v53 + 40 <= v52 )
              {
                if ( *(_BYTE *)(v53 + v46 + 10) )
                  v49 = (char *)(v53 + v46 + 24);
                v50 = *(_BYTE **)(v53 + v46 + 16);
                goto LABEL_146;
              }
            }
            if ( v83 )
              break;
          }
        }
        v51 = (unsigned int)(v51 + 1);
      }
      while ( (unsigned int)v51 < v47 );
      v55 = v81;
LABEL_155:
      if ( !v49 )
        goto LABEL_184;
      v56 = *v49;
    }
    else
    {
      v56 = *(_BYTE *)(v46 + 72);
      v50 = *(_BYTE **)(v46 + 32);
      v48 = *(_BYTE *)(v46 + 11);
      v55 = *(_BYTE *)(v46 + 4);
      if ( *(_BYTE *)(v46 + 2) )
        goto LABEL_184;
    }
    LOBYTE(v40) = v56 - 8;
    if ( (v40 & 0x5D) != 0 )
      goto LABEL_184;
    v57 = *(_BYTE *)(v46 + 3);
    if ( v57 == 1 || !v50 || !v48 )
      goto LABEL_178;
    LOBYTE(v46) = 0;
    v58 = 0;
    v59 = 0;
    v40 = (unsigned __int64)&v50[v48];
    v60 = v50 + 8;
    if ( (unsigned __int8)((*v50 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v60 <= v40 )
      {
        v58 = v50[2];
        LOBYTE(v46) = v50[1] & 0xF;
        v59 = v50[3];
        goto LABEL_177;
      }
    }
    else if ( (unsigned __int64)v60 <= v40 )
    {
      v61 = v50 + 13;
      LOBYTE(v46) = v50[2] & 0xF;
      v62 = v48;
      if ( (unsigned int)(unsigned __int8)v50[7] + 8 <= v48 )
        v62 = (unsigned __int8)v50[7] + 8;
      v40 = (unsigned __int64)&v50[v62];
      if ( (unsigned __int64)v61 <= v40 )
        v58 = v50[12];
      if ( (unsigned __int64)(v50 + 14) > v40 )
        v59 = 0;
      else
        v59 = *v61;
LABEL_177:
      if ( v7 )
      {
LABEL_179:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v40,
          v46,
          (unsigned int)&v88,
          a2,
          *(_DWORD *)(a2 + 48),
          v57,
          v55,
          v46,
          v58,
          v59,
          a2);
        goto LABEL_184;
      }
LABEL_178:
      LOBYTE(v46) = 0;
      v58 = 0;
      v59 = 0;
      goto LABEL_179;
    }
    v7 = 0;
    goto LABEL_177;
  }
  v10 = StorEtwLoggingEnabled == 0;
  *(_QWORD *)(a2 + 56) = 0;
  *(_BYTE *)(a2 + 141) = -84;
  *(_DWORD *)(a2 + 48) = v5;
  if ( v10 )
    goto LABEL_74;
  v88 = 0;
  IoGetActivityIdIrp(a2, &v88);
  v12 = *(_QWORD *)(a2 + 184);
  if ( *(_BYTE *)v12 == 14 )
  {
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_74;
    v15 = EventNonReadWriteRequestComplete;
    goto LABEL_73;
  }
  if ( *(_BYTE *)v12 != 15 )
  {
    if ( *(_BYTE *)v12 != 27 )
      goto LABEL_74;
    if ( *(_BYTE *)(v12 + 1) == 7 && !*(_DWORD *)(v12 + 8) )
    {
      if ( (byte_140177432 & 0x40) != 0 )
      {
        v13 = *(int **)(a2 + 56);
        if ( v13 )
          v14 = *v13;
        else
          v14 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v14, v12, (unsigned int)&v88, a2, v14, *(_DWORD *)(a2 + 48));
      }
      goto LABEL_74;
    }
    if ( (byte_140177432 & 0x20) == 0 )
      goto LABEL_74;
    v15 = EventPnpRequestComplete;
LABEL_73:
    McTemplateK0pd_EtwWriteTransfer(v11, v15, &v88, a2, *(_DWORD *)(a2 + 48));
    goto LABEL_74;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_74;
  v16 = *(_QWORD *)(v12 + 8);
  if ( *(_BYTE *)(v16 + 2) == 40 )
  {
    if ( *(_DWORD *)(v16 + 20) )
      goto LABEL_74;
    v17 = *(_DWORD *)(v16 + 56);
    if ( !v17 )
      goto LABEL_74;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v23 = 0;
    while ( 1 )
    {
      v11 = *(unsigned int *)(v16 + 4 * v22 + 120);
      if ( (unsigned int)v11 >= 0x80 )
      {
        v24 = *(unsigned int *)(v16 + 16);
        if ( (unsigned int)v11 < (unsigned int)v24 )
        {
          v25 = (unsigned int)v11;
          v26 = *(_DWORD *)(v11 + v16) - 64;
          if ( v26 )
          {
            LODWORD(v11) = v26 - 1;
            if ( (_DWORD)v11 )
            {
              if ( (_DWORD)v11 == 1 )
              {
                LODWORD(v11) = v25 + 40;
                if ( v25 + 40 <= v24 )
                {
                  if ( *(_DWORD *)(v25 + v16 + 12) )
                    v19 = (char *)(v25 + v16 + 32);
                  v21 = *(_BYTE **)(v25 + v16 + 24);
                  goto LABEL_48;
                }
              }
            }
            else
            {
              LODWORD(v11) = v25 + 56;
              if ( v25 + 56 <= v24 )
              {
                v23 = 1;
                if ( *(_BYTE *)(v25 + v16 + 10) )
                  v19 = (char *)(v25 + v16 + 24);
                v20 = *(_BYTE *)(v25 + v16 + 8);
                v21 = *(_BYTE **)(v25 + v16 + 16);
                v18 = *(_BYTE *)(v25 + v16 + 9);
              }
            }
          }
          else
          {
            LODWORD(v11) = v25 + 40;
            if ( v25 + 40 <= v24 )
            {
              if ( *(_BYTE *)(v25 + v16 + 10) )
                v19 = (char *)(v25 + v16 + 24);
              v21 = *(_BYTE **)(v25 + v16 + 16);
LABEL_48:
              v18 = *(_BYTE *)(v25 + v16 + 9);
              v20 = *(_BYTE *)(v25 + v16 + 8);
LABEL_49:
              if ( v19 )
              {
                v27 = *v19;
                goto LABEL_52;
              }
              goto LABEL_74;
            }
          }
          if ( v23 )
            goto LABEL_49;
        }
      }
      v22 = (unsigned int)(v22 + 1);
      if ( (unsigned int)v22 >= v17 )
        goto LABEL_49;
    }
  }
  v27 = *(_BYTE *)(v16 + 72);
  v21 = *(_BYTE **)(v16 + 32);
  v18 = *(_BYTE *)(v16 + 11);
  v20 = *(_BYTE *)(v16 + 4);
  if ( *(_BYTE *)(v16 + 2) )
    goto LABEL_74;
LABEL_52:
  LOBYTE(v11) = v27 - 8;
  if ( (v11 & 0x5D) == 0 )
  {
    v28 = *(_BYTE *)(v16 + 3);
    if ( v28 == 1 || !v21 || !v18 )
      goto LABEL_69;
    LOBYTE(v16) = 0;
    v29 = 0;
    v30 = 0;
    v11 = (unsigned __int64)&v21[v18];
    v31 = v21 + 8;
    if ( (unsigned __int8)((*v21 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v31 <= v11 )
      {
        v29 = v21[2];
        LOBYTE(v16) = v21[1] & 0xF;
        v30 = v21[3];
        goto LABEL_68;
      }
    }
    else if ( (unsigned __int64)v31 <= v11 )
    {
      v32 = v21 + 13;
      LOBYTE(v16) = v21[2] & 0xF;
      v33 = v18;
      if ( (unsigned int)(unsigned __int8)v21[7] + 8 <= v18 )
        v33 = (unsigned __int8)v21[7] + 8;
      v11 = (unsigned __int64)&v21[v33];
      if ( (unsigned __int64)v32 <= v11 )
        v29 = v21[12];
      if ( (unsigned __int64)(v21 + 14) > v11 )
        v30 = 0;
      else
        v30 = *v32;
LABEL_68:
      if ( v7 )
      {
LABEL_70:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v11,
          v16,
          (unsigned int)&v88,
          a2,
          *(_DWORD *)(a2 + 48),
          v28,
          v20,
          v16,
          v29,
          v30,
          a2);
        goto LABEL_74;
      }
LABEL_69:
      LOBYTE(v16) = 0;
      v29 = 0;
      v30 = 0;
      goto LABEL_70;
    }
    v7 = 0;
    goto LABEL_68;
  }
LABEL_74:
  IofCompleteRequest((PIRP)a2, 0);
  return v87;
}

```

## disassembly

```asm
0x140034df0  mov     [rsp-8+arg_10], rbx
0x140034df5  push    rbp
0x140034df6  push    rsi
0x140034df7  push    rdi
0x140034df8  push    r12
0x140034dfa  push    r13
0x140034dfc  push    r14
0x140034dfe  push    r15
0x140034e00  lea     rbp, [rsp-27h]
0x140034e05  sub     rsp, 0A0h
0x140034e0c  mov     rax, cs:__security_cookie
0x140034e13  xor     rax, rsp
0x140034e16  mov     [rbp+57h+var_40], rax
0x140034e1a  xorps   xmm0, xmm0
0x140034e1d  xor     r12b, r12b
0x140034e20  movups  [rbp+57h+var_50], xmm0
0x140034e24  mov     [rbp+57h+var_6E], r12b
0x140034e28  mov     rbx, rdx
0x140034e2b  mov     rdi, rcx
0x140034e2e  call    RaidAcquireAdapterRemoveLock
0x140034e33  cmp     cs:StorEtwLoggingEnabled, r12b
0x140034e3a  mov     r15d, eax
0x140034e3d  mov     rcx, [rbx+0B8h]
0x140034e44  mov     r14d, 1
0x140034e4a  mov     [rbp+57h+var_68], eax
0x140034e4d  mov     r13d, [rcx+18h]
0x140034e51  mov     [rbp+57h+var_6C], r13d
0x140034e55  jz      loc_140034EF7
0x140034e5b  lea     rdx, [rbp+57h+var_50]
0x140034e5f  mov     rcx, rbx
0x140034e62  call    cs:__imp_IoGetActivityIdIrp
0x140034e69  nop     dword ptr [rax+rax+00h]
0x140034e6e  cmp     r13d, 4D004h
0x140034e75  jz      short loc_140034EC0
0x140034e77  lea     eax, [r13-4D014h]
0x140034e7e  cmp     eax, 34h ; '4'
0x140034e81  ja      short loc_140034E93
0x140034e83  mov     rcx, 11000011000001h
0x140034e8d  bt      rcx, rax
0x140034e91  jb      short loc_140034EC0
0x140034e93  test    cs:byte_140177432, 2
0x140034e9a  jz      short loc_140034EF7
0x140034e9c  mov     rax, [rbx+0B8h]
0x140034ea3  mov     [rsp+0D0h+var_A0], r13d
0x140034ea8  movzx   edx, byte ptr [rax]
0x140034eab  movzx   ecx, byte ptr [rax+1]
0x140034eaf  mov     [rsp+0D0h+var_A8], ecx
0x140034eb3  mov     dword ptr [rsp+0D0h+var_B0], edx
0x140034eb7  lea     rdx, EventIOCTL
0x140034ebe  jmp     short loc_140034EEB
0x140034ec0  test    cs:byte_140177433, r14b
0x140034ec7  jz      short loc_140034EF7
0x140034ec9  mov     rax, [rbx+0B8h]
0x140034ed0  mov     [rsp+0D0h+var_A0], r13d
0x140034ed5  movzx   edx, byte ptr [rax]
0x140034ed8  movzx   ecx, byte ptr [rax+1]
0x140034edc  mov     [rsp+0D0h+var_A8], ecx
0x140034ee0  mov     dword ptr [rsp+0D0h+var_B0], edx
0x140034ee4  lea     rdx, EventPassThrough
0x140034eeb  mov     r9, rbx
0x140034eee  lea     r8, [rbp+57h+var_50]
0x140034ef2  call    McTemplateK0pddd_EtwWriteTransfer
0x140034ef7  test    r15d, r15d
0x140034efa  jns     loc_1400351ED
0x140034f00  cmp     cs:StorEtwLoggingEnabled, r12b
0x140034f07  mov     qword ptr [rbx+38h], 0
0x140034f0f  mov     byte ptr [rbx+8Dh], 0ACh
0x140034f16  mov     [rbx+30h], r15d
0x140034f1a  jz      loc_1400351D4
0x140034f20  xorps   xmm0, xmm0
0x140034f23  lea     rdx, [rbp+57h+var_60]
0x140034f27  mov     rcx, rbx
0x140034f2a  movups  [rbp+57h+var_60], xmm0
0x140034f2e  call    cs:__imp_IoGetActivityIdIrp
0x140034f35  nop     dword ptr [rax+rax+00h]
0x140034f3a  mov     rdx, [rbx+0B8h]
0x140034f41  movzx   eax, byte ptr [rdx]
0x140034f44  sub     eax, 0Eh
0x140034f47  jz      loc_1400351B1
0x140034f4d  sub     eax, r14d
0x140034f50  jz      short loc_140034FB8
0x140034f52  cmp     eax, 0Ch
0x140034f55  jnz     loc_1400351D4
0x140034f5b  cmp     byte ptr [rdx+1], 7
0x140034f5f  jnz     short loc_140034F9F
0x140034f61  cmp     dword ptr [rdx+8], 0
0x140034f65  jnz     short loc_140034F9F
0x140034f67  test    cs:byte_140177432, 40h
0x140034f6e  jz      loc_1400351D4
0x140034f74  mov     rax, [rbx+38h]
0x140034f78  test    rax, rax
0x140034f7b  jz      short loc_140034F81
0x140034f7d  mov     ecx, [rax]
0x140034f7f  jmp     short loc_140034F83
0x140034f81  xor     ecx, ecx
0x140034f83  mov     eax, [rbx+30h]
0x140034f86  lea     r8, [rbp+57h+var_60]
0x140034f8a  mov     [rsp+0D0h+var_A8], eax
0x140034f8e  mov     r9, rbx
0x140034f91  mov     dword ptr [rsp+0D0h+var_B0], ecx
0x140034f95  call    McTemplateK0pqd_EtwWriteTransfer
0x140034f9a  jmp     loc_1400351D4
0x140034f9f  test    cs:byte_140177432, 20h
0x140034fa6  jz      loc_1400351D4
0x140034fac  lea     rdx, EventPnpRequestComplete
0x140034fb3  jmp     loc_1400351C1
0x140034fb8  cmp     cs:byte_140177431, r12b
0x140034fbf  jge     loc_1400351D4
0x140034fc5  mov     rdx, [rdx+8]
0x140034fc9  movzx   eax, byte ptr [rdx+2]
0x140034fcd  cmp     al, 28h ; '('
0x140034fcf  jnz     loc_1400350BA
0x140034fd5  cmp     dword ptr [rdx+14h], 0
0x140034fd9  jnz     loc_1400351D4
0x140034fdf  mov     r12d, [rdx+38h]
0x140034fe3  test    r12d, r12d
0x140034fe6  jz      loc_1400351D4
0x140034fec  xor     r10b, r10b
0x140034fef  xor     r11d, r11d
0x140034ff2  xor     sil, sil
0x140034ff5  xor     r9d, r9d
0x140034ff8  xor     r15d, r15d
0x140034ffb  xor     r13b, r13b
0x140034ffe  mov     ecx, [rdx+r15*4+78h]
0x140035003  cmp     ecx, 80h
0x140035009  jb      short loc_140035080
0x14003500b  mov     edi, [rdx+10h]
0x14003500e  cmp     ecx, edi
0x140035010  jnb     short loc_140035080
0x140035012  mov     r8d, ecx
0x140035015  mov     ecx, [rcx+rdx]
0x140035018  sub     ecx, 40h ; '@'
0x14003501b  jz      short loc_140035072
0x14003501d  sub     ecx, r14d
0x140035020  jz      short loc_140035046
0x140035022  cmp     ecx, r14d
0x140035025  jnz     short loc_14003507B
0x140035027  lea     rcx, [r8+28h]
0x14003502b  cmp     rcx, rdi
0x14003502e  ja      short loc_14003507B
0x140035030  cmp     dword ptr [r8+rdx+0Ch], 0
0x140035036  jbe     short loc_14003503F
0x140035038  lea     r11, [rdx+20h]
0x14003503c  add     r11, r8
0x14003503f  mov     r9, [r8+rdx+18h]
0x140035044  jmp     short loc_1400350A2
0x140035046  lea     rcx, [r8+38h]
0x14003504a  cmp     rcx, rdi
0x14003504d  ja      short loc_14003507B
0x14003504f  cmp     byte ptr [r8+rdx+0Ah], 0
0x140035055  mov     r13b, r14b
0x140035058  jbe     short loc_140035061
0x14003505a  lea     r11, [rdx+18h]
0x14003505e  add     r11, r8
0x140035061  mov     sil, [r8+rdx+8]
0x140035066  mov     r9, [r8+rdx+10h]
0x14003506b  mov     r10b, [r8+rdx+9]
0x140035070  jmp     short loc_14003507B
0x140035072  lea     rcx, [r8+28h]
0x140035076  cmp     rcx, rdi
0x140035079  jbe     short loc_14003508E
0x14003507b  test    r13b, r13b
0x14003507e  jnz     short loc_1400350AC
0x140035080  add     r15d, r14d
0x140035083  cmp     r15d, r12d
0x140035086  jb      loc_140034FFE
0x14003508c  jmp     short loc_1400350AC
0x14003508e  cmp     byte ptr [r8+rdx+0Ah], 0
0x140035094  jbe     short loc_14003509D
0x140035096  lea     r11, [rdx+18h]
0x14003509a  add     r11, r8
0x14003509d  mov     r9, [r8+rdx+10h]
0x1400350a2  mov     r10b, [r8+rdx+9]
0x1400350a7  mov     sil, [r8+rdx+8]
0x1400350ac  test    r11, r11
0x1400350af  jz      loc_1400351D4
0x1400350b5  mov     cl, [r11]
0x1400350b8  jmp     short loc_1400350D1
0x1400350ba  mov     cl, [rdx+48h]
0x1400350bd  mov     r9, [rdx+20h]
0x1400350c1  mov     r10b, [rdx+0Bh]
0x1400350c5  mov     sil, [rdx+4]
0x1400350c9  test    eax, eax
0x1400350cb  jnz     loc_1400351D4
0x1400350d1  sub     cl, 8
0x1400350d4  test    cl, 5Dh
0x1400350d7  jnz     loc_1400351D4
0x1400350dd  mov     dil, [rdx+3]
0x1400350e1  cmp     dil, r14b
0x1400350e4  jz      loc_140035177
0x1400350ea  test    r9, r9
0x1400350ed  jz      loc_140035177
0x1400350f3  test    r10b, r10b
0x1400350f6  jz      short loc_140035177
0x1400350f8  mov     al, [r9]
0x1400350fb  xor     dl, dl
0x1400350fd  and     al, 7Fh
0x1400350ff  movzx   ecx, r10b
0x140035103  sub     al, 72h ; 'r'
0x140035105  xor     r11b, r11b
0x140035108  xor     r8b, r8b
0x14003510b  add     rcx, r9
0x14003510e  cmp     al, r14b
0x140035111  lea     rax, [r9+8]
0x140035115  jbe     short loc_140035159
0x140035117  cmp     rax, rcx
0x14003511a  ja      short loc_14003516F
0x14003511c  movzx   ecx, byte ptr [r9+7]
0x140035121  lea     r8, [r9+0Dh]
0x140035125  mov     dl, [r9+2]
0x140035129  add     ecx, 8
0x14003512c  and     dl, 0Fh
0x14003512f  movzx   eax, r10b
0x140035133  cmp     ecx, eax
0x140035135  cmovbe  eax, ecx
0x140035138  mov     ecx, eax
0x14003513a  add     rcx, r9
0x14003513d  cmp     r8, rcx
0x140035140  ja      short loc_140035146
0x140035142  mov     r11b, [r9+0Ch]
0x140035146  lea     rax, [r9+0Eh]
0x14003514a  cmp     rax, rcx
0x14003514d  ja      short loc_140035154
0x14003514f  mov     r8b, [r8]
0x140035152  jmp     short loc_140035172
0x140035154  xor     r8b, r8b
0x140035157  jmp     short loc_140035172
0x140035159  cmp     rax, rcx
0x14003515c  ja      short loc_14003516F
0x14003515e  mov     dl, [r9+1]
0x140035162  mov     r11b, [r9+2]
0x140035166  and     dl, 0Fh
0x140035169  mov     r8b, [r9+3]
0x14003516d  jmp     short loc_140035172
0x14003516f  xor     r14b, r14b
0x140035172  test    r14b, r14b
0x140035175  jnz     short loc_14003517F
0x140035177  xor     dl, dl
0x140035179  xor     r11b, r11b
0x14003517c  xor     r8b, r8b
0x14003517f  mov     eax, [rbx+30h]
0x140035182  mov     r9, rbx
0x140035185  mov     [rsp+0D0h+var_80], rbx
0x14003518a  mov     [rsp+0D0h+var_88], r8b
0x14003518f  lea     r8, [rbp+57h+var_60]
0x140035193  mov     [rsp+0D0h+var_90], r11b
0x140035198  mov     [rsp+0D0h+var_98], dl
0x14003519c  mov     byte ptr [rsp+0D0h+var_A0], sil
0x1400351a1  mov     byte ptr [rsp+0D0h+var_A8], dil
0x1400351a6  mov     dword ptr [rsp+0D0h+var_B0], eax
0x1400351aa  call    McTemplateK0pduuuuup_EtwWriteTransfer
0x1400351af  jmp     short loc_1400351D4
0x1400351b1  test    cs:byte_140177432, 8
0x1400351b8  jz      short loc_1400351D4
0x1400351ba  lea     rdx, EventNonReadWriteRequestComplete
0x1400351c1  mov     eax, [rbx+30h]
0x1400351c4  lea     r8, [rbp+57h+var_60]
0x1400351c8  mov     r9, rbx
0x1400351cb  mov     dword ptr [rsp+0D0h+var_B0], eax
0x1400351cf  call    McTemplateK0pd_EtwWriteTransfer
0x1400351d4  xor     edx, edx; PriorityBoost
0x1400351d6  mov     rcx, rbx; Irp
0x1400351d9  call    cs:__imp_IofCompleteRequest
0x1400351e0  nop     dword ptr [rax+rax+00h]
0x1400351e5  mov     eax, [rbp+57h+var_68]
0x1400351e8  jmp     loc_140036262
0x1400351ed  mov     r10, cs:WPP_GLOBAL_Control
0x1400351f4  lea     r15, WPP_GLOBAL_Control
0x1400351fb  cmp     r10, r15
0x1400351fe  jz      short loc_140035246
0x140035200  mov     eax, [r10+2Ch]
0x140035204  test    al, 10h
0x140035206  jz      short loc_140035246
0x140035208  cmp     byte ptr [r10+29h], 4
0x14003520d  jb      short loc_140035246
0x14003520f  mov     ecx, r13d
0x140035212  lea     r8, WPP_17a2ccf459a039b6fd190e52d544bf1c_Traceguids
0x140035219  shr     ecx, 2
0x14003521c  mov     eax, r13d
0x14003521f  and     ecx, 0FFFh
0x140035225  shr     eax, 10h
0x140035228  mov     [rsp+0D0h+var_A0], ecx
0x14003522c  mov     edx, 0Ah
0x140035231  mov     rcx, [r10+18h]
0x140035235  mov     r9, rdi
0x140035238  mov     [rsp+0D0h+var_A8], eax
0x14003523c  mov     [rsp+0D0h+var_B0], rbx
0x140035241  call    WPP_SF_qqDD
0x140035246  mov     r8, rbx
0x140035249  mov     rdx, rdi
0x14003524c  call    ExtensionAdapterIoctlReplace
0x140035251  mov     esi, eax
0x140035253  cmp     eax, 0C0000002h
0x140035258  jnz     loc_140036209
0x14003525e  mov     r8, rbx
0x140035261  mov     rdx, rdi
0x140035264  call    ExtensionAdapterIoctlPre
0x140035269  mov     eax, 2D5F90h
0x14003526e  cmp     r13d, eax
0x140035271  ja      loc_140035A0A
  ... truncated ...
```
