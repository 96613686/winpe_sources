# WcInstanceSetup

- ea: `0x140032d80`
- end: `0x1400338a7`
- name: `WcInstanceSetup`
- size: `2855`
- prototype: `__int64 __fastcall(struct _FLT_FILTER **, int, int, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400020c4`
- `0x140002ab4`
- `0x140004198`
- `0x14000678c`
- `0x140006814`
- `0x14000696c`
- `0x140007c60`
- `0x1400080c0`
- `0x1400085e0`
- `0x14002e444`
- `0x140032d80`

## import_xrefs

- `ntoskrnl!IoGetBootLayers` at `0x140033706`
- `ntoskrnl!IoGetBootLayers` at `0x140033706`
- `ntoskrnl!IoMountBootLayer` at `0x14003375d`
- `ntoskrnl!IoMountBootLayer` at `0x14003375d`
- `ntoskrnl!RtlGUIDFromString` at `0x1400335e8`
- `ntoskrnl!RtlGUIDFromString` at `0x1400335e8`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x1400336a4`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x1400336a4`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140032f04`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140032f21`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140032f04`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140032f21`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140032f8f`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140032f8f`
- `ntoskrnl!ObfDereferenceObject` at `0x140033056`
- `ntoskrnl!ObfDereferenceObject` at `0x140033859`
- `ntoskrnl!ObfDereferenceObject` at `0x140033056`
- `ntoskrnl!ObfDereferenceObject` at `0x140033859`
- `ntoskrnl!ExInitializeResourceLite` at `0x140033332`
- `ntoskrnl!ExInitializeResourceLite` at `0x140033332`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033844`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033844`
- `ntoskrnl!ExAllocatePool2` at `0x14003337e`
- `ntoskrnl!ExAllocatePool2` at `0x14003337e`
- `FLTMGR!FltAllocateContext` at `0x14003313c`
- `FLTMGR!FltAllocateContext` at `0x140033261`
- `FLTMGR!FltAllocateContext` at `0x14003313c`
- `FLTMGR!FltAllocateContext` at `0x140033261`
- `FLTMGR!FltGetDiskDeviceObject` at `0x140032fb1`
- `FLTMGR!FltGetDiskDeviceObject` at `0x140032fb1`
- `FLTMGR!FltSetInstanceContext` at `0x1400336bf`
- `FLTMGR!FltSetInstanceContext` at `0x1400336bf`
- `FLTMGR!FltQueryVolumeInformation` at `0x14003363a`
- `FLTMGR!FltQueryVolumeInformation` at `0x14003363a`
- `FLTMGR!FltGetVolumeGuidName` at `0x140033598`
- `FLTMGR!FltGetVolumeGuidName` at `0x140033598`
- `FLTMGR!FltGetVolumeProperties` at `0x14003335b`
- `FLTMGR!FltGetVolumeProperties` at `0x140033400`
- `FLTMGR!FltGetVolumeProperties` at `0x14003335b`
- `FLTMGR!FltGetVolumeProperties` at `0x140033400`
- `FLTMGR!FltIsVolumeSnapshot` at `0x1400330b5`
- `FLTMGR!FltIsVolumeSnapshot` at `0x1400330b5`
- `FLTMGR!FltGetInstanceInformation` at `0x140032e72`
- `FLTMGR!FltGetInstanceInformation` at `0x140032e72`
- `FLTMGR!FltQueryVolumeInformationFile` at `0x14003353d`
- `FLTMGR!FltQueryVolumeInformationFile` at `0x14003353d`
- `FLTMGR!FltCreateFileEx` at `0x1400334c9`
- `FLTMGR!FltCreateFileEx` at `0x1400334c9`
- `FLTMGR!FltClose` at `0x14003386e`
- `FLTMGR!FltClose` at `0x14003386e`
- `FLTMGR!FltReleaseContext` at `0x140033799`
- `FLTMGR!FltReleaseContext` at `0x140033827`
- `FLTMGR!FltReleaseContext` at `0x140033799`
- `FLTMGR!FltReleaseContext` at `0x140033827`

## pseudocode

```c
__int64 __fastcall WcInstanceSetup(struct _FLT_FILTER **a1, int a2, int a3, unsigned int a4)
{
  int v6; // eax
  struct _FLT_INSTANCE *v7; // rcx
  unsigned __int16 v8; // r12
  __int64 v9; // rdx
  __int64 v10; // rcx
  NTSTATUS InstanceInformation; // ebx
  __int64 v12; // r8
  char v13; // bl
  int v14; // edx
  NTSTATUS v15; // eax
  int v16; // r9d
  ULONG Flags; // ebx
  int v18; // eax
  NTSTATUS IsVolumeSnapshot; // eax
  int v20; // r8d
  int v21; // edx
  struct _FLT_FILTER *v22; // rcx
  NTSTATUS v23; // eax
  int v24; // edx
  char *v25; // rcx
  NTSTATUS v26; // eax
  int v27; // ecx
  struct _FLT_VOLUME_PROPERTIES *Pool2; // rax
  NTSTATUS VolumeProperties; // eax
  struct _FLT_INSTANCE *v30; // rdx
  NTSTATUS v31; // eax
  int v32; // r9d
  int v33; // r8d
  NTSTATUS v34; // eax
  struct _FLT_VOLUME *v35; // rcx
  NTSTATUS v36; // eax
  NTSTATUS v37; // eax
  NTSTATUS v38; // eax
  NTSTATUS v39; // eax
  int BootLayers; // eax
  struct _DEVICE_OBJECT *NextDevice; // rax
  int BytesReturned; // [rsp+20h] [rbp-E0h]
  int BytesReturneda; // [rsp+20h] [rbp-E0h]
  int ObjectAttributes; // [rsp+28h] [rbp-D8h]
  char IoStatusBlock; // [rsp+30h] [rbp-D0h]
  char IoStatusBlocka; // [rsp+30h] [rbp-D0h]
  char AllocationSize; // [rsp+38h] [rbp-C8h]
  char AllocationSizea; // [rsp+38h] [rbp-C8h]
  bool v50; // [rsp+80h] [rbp-80h]
  __int16 v51; // [rsp+84h] [rbp-7Ch]
  unsigned __int8 IsSnapshotVolume; // [rsp+88h] [rbp-78h] BYREF
  BOOLEAN v53; // [rsp+89h] [rbp-77h]
  PFLT_CONTEXT ReturnedContext; // [rsp+90h] [rbp-70h] BYREF
  BOOLEAN v55; // [rsp+98h] [rbp-68h]
  ULONG LengthReturned; // [rsp+9Ch] [rbp-64h] BYREF
  int v57; // [rsp+A0h] [rbp-60h]
  int v58; // [rsp+A4h] [rbp-5Ch]
  PVOID P; // [rsp+A8h] [rbp-58h]
  PDEVICE_OBJECT DiskDeviceObject; // [rsp+B0h] [rbp-50h] BYREF
  struct _UNICODE_STRING VolumeGuidName; // [rsp+B8h] [rbp-48h] BYREF
  ULONG v62; // [rsp+C8h] [rbp-38h] BYREF
  PFILE_OBJECT FileObject; // [rsp+D0h] [rbp-30h] BYREF
  UNICODE_STRING String1; // [rsp+D8h] [rbp-28h] BYREF
  __int128 *v65; // [rsp+E8h] [rbp-18h]
  void *FileHandle; // [rsp+F0h] [rbp-10h] BYREF
  struct _OBJECT_ATTRIBUTES v67; // [rsp+F8h] [rbp-8h] BYREF
  struct _IO_STATUS_BLOCK Iosb; // [rsp+128h] [rbp+28h] BYREF
  __int128 FsInformation; // [rsp+138h] [rbp+38h] BYREF
  __int64 v70; // [rsp+148h] [rbp+48h]
  __int128 v71; // [rsp+150h] [rbp+50h] BYREF
  __int128 v72; // [rsp+160h] [rbp+60h] BYREF
  _OWORD v73[2]; // [rsp+170h] [rbp+70h]
  char v74; // [rsp+190h] [rbp+90h] BYREF
  _BYTE Buffer[4]; // [rsp+200h] [rbp+100h] BYREF
  USHORT v76; // [rsp+204h] [rbp+104h]
  unsigned __int16 v77; // [rsp+206h] [rbp+106h]

  v58 = a3;
  v57 = a2;
  ReturnedContext = 0;
  IsSnapshotVolume = 0;
  v70 = 0;
  LengthReturned = 0;
  FileObject = 0;
  FileHandle = 0;
  v62 = 0;
  FsInformation = 0;
  memset(&v67, 0, 44);
  Iosb = 0;
  v72 = *(_OWORD *)L"Name Not Available";
  v73[0] = *(_OWORD *)L" Available";
  *(_QWORD *)((char *)v73 + 14) = *(_QWORD *)L"ble";
  VolumeGuidName = 0;
  v71 = 0;
  String1 = 0;
  if ( a4 > 0x1C )
    return (unsigned int)-1071906801;
  v6 = 268443716;
  if ( !_bittest(&v6, a4) )
    return (unsigned int)-1071906801;
  v7 = a1[3];
  v65 = &v72;
  v8 = 19;
  P = 0;
  v51 = 19;
  InstanceInformation = FltGetInstanceInformation(v7, InstanceBasicInformation, Buffer, 0x210u, &v62);
  if ( InstanceInformation < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_sDlLDd(wil_details_featureDescriptors_a->DeviceExtension, v9, v12, 21, BytesReturned);
    }
    goto LABEL_15;
  }
  String1.Length = v76;
  String1.MaximumLength = v76;
  v50 = 0;
  String1.Buffer = (PWSTR)&Buffer[v77];
  v53 = RtlEqualUnicodeString(&String1, &SourceString, 0);
  v13 = v57;
  v55 = RtlEqualUnicodeString(&String1, &stru_14000A630, 0);
  if ( (v57 & 1) != 0 )
  {
    if ( a4 == 2 )
    {
      if ( memcmp(&Guid, NULL_GUID, 0x10u) && !RtlCompareUnicodeString(&String1, &DestinationString, 0) )
      {
        DiskDeviceObject = 0;
        v15 = FltGetDiskDeviceObject(a1[2], &DiskDeviceObject);
        InstanceInformation = v15;
        if ( v15 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
LABEL_14:
            v8 = 19;
LABEL_15:
            if ( InstanceInformation != -1071906801 && ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 1) != 0 )
              McTemplateK0dhzr1_EtwWriteTransfer(v10, v9, v12, InstanceInformation, v8, (__int64)v65);
            goto LABEL_107;
          }
          AllocationSize = v15;
          v16 = 22;
          IoStatusBlock = -2;
LABEL_13:
          LOBYTE(v9) = 2;
          WPP_RECORDER_SF_sDd(
            wil_details_featureDescriptors_a->DeviceExtension,
            v9,
            4,
            v16,
            (__int64)WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\wcifs\\wcifs.c",
            IoStatusBlock,
            AllocationSize);
          goto LABEL_14;
        }
        Flags = DiskDeviceObject->Flags;
        ObfDereferenceObject(DiskDeviceObject);
        v50 = (Flags & 0x100) != 0;
        if ( (Flags & 0x100) != 0 )
          goto LABEL_25;
        v13 = v57;
      }
      if ( v53 && (unsigned __int8)WcShouldAutoAttach(a1[3], a1[2]) )
      {
LABEL_25:
        IsVolumeSnapshot = FltIsVolumeSnapshot(a1[2], &IsSnapshotVolume);
        v21 = 0;
        if ( IsVolumeSnapshot >= 0 )
        {
          if ( IsSnapshotVolume )
          {
            InstanceInformation = -1071906801;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
              && LOWORD(wil_details_featureDescriptors_a->DeviceType) )
            {
              LOBYTE(v21) = 5;
              WPP_RECORDER_SF_sDlLD(WcVerboseRecorder, v21, v20, 25, BytesReturned, ObjectAttributes, 67, v58, a4, v57);
            }
            goto LABEL_107;
          }
        }
        else if ( IsVolumeSnapshot != -1071906791 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v21) = 3;
          WPP_RECORDER_SF_sDlLDd(wil_details_featureDescriptors_a->DeviceExtension, v21, v20, 24, BytesReturned);
        }
        v22 = a1[1];
        if ( byte_14000E680 )
        {
          v23 = FltAllocateContext(v22, 2u, 0x13Cu, (POOL_TYPE)512, &ReturnedContext);
          v9 = 0;
          InstanceInformation = v23;
          if ( v23 < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_14;
            AllocationSize = v23;
            v16 = 26;
            IoStatusBlock = 87;
            goto LABEL_13;
          }
          memset(ReturnedContext, 0, 0x130u);
          v25 = (char *)ReturnedContext + 304;
          *((_QWORD *)ReturnedContext + 4) = (char *)ReturnedContext + 304;
          *(_QWORD *)v25 = 0;
          *((_DWORD *)v25 + 2) = 0;
        }
        else
        {
          v26 = FltAllocateContext(v22, 2u, 0x130u, (POOL_TYPE)512, &ReturnedContext);
          v9 = 0;
          InstanceInformation = v26;
          if ( v26 < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_14;
            AllocationSize = v26;
            v16 = 27;
            IoStatusBlock = 107;
            goto LABEL_13;
          }
          memset(ReturnedContext, 0, 0x130u);
        }
        *(_QWORD *)ReturnedContext = a1[3];
        *((_DWORD *)ReturnedContext + 2) = a4;
        if ( v53 )
        {
          *((_DWORD *)ReturnedContext + 4) = dword_14000E250;
        }
        else if ( v55 )
        {
          v27 = -1;
          if ( !HIBYTE(qword_14000E6A2) )
            v27 = dword_14000E254;
          *((_DWORD *)ReturnedContext + 4) = v27;
        }
        else
        {
          *((_DWORD *)ReturnedContext + 4) = -1;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v24) = 3;
            WPP_RECORDER_SF_sD(
              wil_details_featureDescriptors_a->DeviceExtension,
              v24,
              4,
              28,
              (__int64)WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\wcifs\\wcifs.c",
              133);
          }
        }
        ExInitializeResourceLite((PERESOURCE)((char *)ReturnedContext + 72));
        if ( a4 != 2 && a4 != 28 )
          goto LABEL_82;
        InstanceInformation = FltGetVolumeProperties(a1[2], 0, 0, &LengthReturned);
        if ( InstanceInformation == -1073741789 )
        {
          Pool2 = (struct _FLT_VOLUME_PROPERTIES *)ExAllocatePool2(256, LengthReturned, 1667842903);
          P = Pool2;
          if ( !Pool2 )
          {
            InstanceInformation = -1073741670;
            goto LABEL_61;
          }
        }
        else
        {
          v10 = 0;
          P = 0;
          Pool2 = 0;
          if ( InstanceInformation < 0 )
          {
LABEL_61:
            P = 0;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v9) = 2;
              WPP_RECORDER_SF_sDd(
                wil_details_featureDescriptors_a->DeviceExtension,
                v9,
                4,
                29,
                (__int64)WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids,
                (__int64)"onecore\\base\\fs\\wci\\wcifs\\wcifs.c",
                161,
                InstanceInformation);
            }
            goto LABEL_14;
          }
        }
        VolumeProperties = FltGetVolumeProperties(a1[2], Pool2, LengthReturned, &LengthReturned);
        v9 = 0;
        InstanceInformation = VolumeProperties;
        if ( VolumeProperties < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_14;
          AllocationSize = VolumeProperties;
          v16 = 30;
          IoStatusBlock = -84;
          goto LABEL_13;
        }
        v65 = (__int128 *)*((_QWORD *)P + 8);
        v51 = *((_WORD *)P + 28) >> 1;
        v67.RootDirectory = 0;
        v30 = a1[3];
        v67.ObjectName = (PUNICODE_STRING)((char *)P + 56);
        v67.Length = 48;
        v67.Attributes = 576;
        *(_OWORD *)&v67.SecurityDescriptor = 0;
        v31 = FltCreateFileEx(Globals, v30, &FileHandle, &FileObject, 0x180u, &v67, &Iosb, 0, 0, 7u, 1u, 0x20u, 0, 0, 0);
        v9 = 0;
        InstanceInformation = v31;
        if ( v31 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
LABEL_72:
            v8 = v51;
            goto LABEL_15;
          }
          AllocationSizea = v31;
          v32 = 31;
          IoStatusBlocka = -48;
          goto LABEL_70;
        }
        v34 = FltQueryVolumeInformationFile(a1[3], FileObject, &FsInformation, 0x18u, FileFsSizeInformation, 0);
        InstanceInformation = v34;
        if ( v34 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_72;
          AllocationSizea = v34;
          v32 = 32;
          IoStatusBlocka = -35;
          goto LABEL_70;
        }
        *((_DWORD *)ReturnedContext + 3) = HIDWORD(v70) * v70;
        v35 = a1[2];
        VolumeGuidName.Buffer = (PWSTR)&v74;
        *(_DWORD *)&VolumeGuidName.Length = 6422528;
        v36 = FltGetVolumeGuidName(v35, &VolumeGuidName, &LengthReturned);
        InstanceInformation = v36;
        if ( v36 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_72;
          AllocationSizea = v36;
          v32 = 33;
          IoStatusBlocka = -21;
          goto LABEL_70;
        }
        VolumeGuidName.Buffer += 10;
        VolumeGuidName.Length -= 20;
        v37 = RtlGUIDFromString(&VolumeGuidName, (GUID *)((char *)ReturnedContext + 40));
        InstanceInformation = v37;
        if ( v37 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_72;
          AllocationSizea = v37;
          v32 = 34;
          IoStatusBlocka = -10;
        }
        else
        {
LABEL_82:
          v38 = FltQueryVolumeInformation(a1[3], &Iosb, &v71, 0x10u, FileFsAttributeInformation);
          *((_BYTE *)ReturnedContext + 296) = ((int)(v38 + 0x80000000) < 0 || v38 == -2147483643) && (v71 & 0x200) != 0;
          *((_DWORD *)ReturnedContext + 16) = 0;
          RtlInitializeGenericTableAvl(
            (PRTL_AVL_TABLE)((char *)ReturnedContext + 176),
            (PRTL_AVL_COMPARE_ROUTINE)WcCompareUnionTableEntry,
            WcAllocateUnionTableEntry,
            (PRTL_AVL_FREE_ROUTINE)WcFreeUnionTableEntry,
            0);
          v39 = FltSetInstanceContext(a1[3], FLT_SET_CONTEXT_KEEP_IF_EXISTS, ReturnedContext, 0);
          v9 = 0;
          InstanceInformation = v39;
          if ( v39 >= 0 )
          {
            if ( !v50 )
              goto LABEL_103;
            DiskDeviceObject = 0;
            BootLayers = IoGetBootLayers(&DiskDeviceObject);
            v9 = 0;
            InstanceInformation = BootLayers;
            if ( BootLayers < 0 )
            {
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                goto LABEL_72;
              AllocationSizea = BootLayers;
              v32 = 36;
              IoStatusBlocka = 36;
              v33 = 1;
              goto LABEL_71;
            }
            if ( *(_DWORD *)&DiskDeviceObject->Type == 3 && LODWORD(DiskDeviceObject->AttachedDevice) == 1 )
            {
              NextDevice = DiskDeviceObject->NextDevice;
              if ( **(_DWORD **)&NextDevice->Type == 4 )
                IoMountBootLayer(*(_QWORD *)&NextDevice->Type, 0, 0);
            }
            if ( a4 == 2 )
            {
              InstanceInformation = WcSetupVsmbBootUnionContext(ReturnedContext, 0);
              v9 = 0;
            }
            else
            {
              InstanceInformation = WcSetupVsmbBootUnionContext(Context, ReturnedContext);
              FltReleaseContext(Context);
              v9 = 0;
              Context = 0;
            }
            if ( InstanceInformation >= 0 )
            {
LABEL_103:
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v9) = 4;
                WPP_RECORDER_SF_sDlLD(
                  wil_details_featureDescriptors_a->DeviceExtension,
                  v9,
                  v12,
                  38,
                  BytesReturneda,
                  ObjectAttributes,
                  83,
                  v58,
                  a4,
                  v57);
              }
              InstanceInformation = 0;
              goto LABEL_107;
            }
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_72;
            AllocationSizea = InstanceInformation;
            v32 = 37;
            IoStatusBlocka = 75;
          }
          else
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_72;
            AllocationSizea = v39;
            v32 = 35;
            IoStatusBlocka = 27;
          }
        }
LABEL_70:
        v33 = 4;
LABEL_71:
        LOBYTE(v9) = 2;
        WPP_RECORDER_SF_sDd(
          wil_details_featureDescriptors_a->DeviceExtension,
          v9,
          v33,
          v32,
          (__int64)WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\wcifs.c",
          IoStatusBlocka,
          AllocationSizea);
        goto LABEL_72;
      }
    }
    else
    {
      v50 = 0;
      if ( a4 == 6 )
      {
        v50 = 0;
        if ( Context )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v14) = 4;
            WPP_RECORDER_SF_sD(
              wil_details_featureDescriptors_a->DeviceExtension,
              v14,
              4,
              23,
              (__int64)WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\wcifs\\wcifs.c",
              28);
          }
          v50 = 1;
          goto LABEL_25;
        }
      }
    }
  }
  if ( (v13 & 2) != 0 && a4 <= 0x1C )
  {
    v18 = 268443716;
    if ( _bittest(&v18, a4) )
      goto LABEL_25;
  }
  InstanceInformation = -1071906801;
LABEL_107:
  if ( ReturnedContext )
    FltReleaseContext(ReturnedContext);
  if ( P )
    ExFreePoolWithTag(P, 0x63694357u);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( FileHandle )
    FltClose(FileHandle);
  return (unsigned int)InstanceInformation;
}

```

## disassembly

```asm
0x140032d80  push    rbp
0x140032d82  push    rbx
0x140032d83  push    rsi
0x140032d84  push    rdi
0x140032d85  push    r12
0x140032d87  push    r13
0x140032d89  push    r14
0x140032d8b  push    r15
0x140032d8d  lea     rbp, [rsp-328h]
0x140032d95  sub     rsp, 428h
0x140032d9c  mov     rax, cs:__security_cookie
0x140032da3  xor     rax, rsp
0x140032da6  mov     [rbp+360h+var_50], rax
0x140032dad  movups  xmm1, xmmword ptr cs:aNameNotAvailab; "Name Not Available"
0x140032db4  mov     [rbp+360h+var_3BC], r8d
0x140032db8  xor     edi, edi
0x140032dba  xorps   xmm0, xmm0
0x140032dbd  mov     [rbp+360h+var_3C0], edx
0x140032dc0  movups  xmmword ptr [rbp+360h+var_368.ObjectName], xmm0
0x140032dc4  xor     eax, eax
0x140032dc6  mov     r14d, r9d
0x140032dc9  mov     [rbp+360h+ReturnedContext], rdi
0x140032dcd  mov     r15d, r8d
0x140032dd0  mov     [rbp+360h+IsSnapshotVolume], dil
0x140032dd4  mov     esi, edx
0x140032dd6  mov     [rbp+360h+var_318], rax
0x140032dda  mov     r13, rcx
0x140032ddd  mov     [rbp+360h+LengthReturned], edi
0x140032de0  mov     [rbp+360h+FileObject], rdi
0x140032de4  mov     [rbp+360h+FileHandle], rdi
0x140032de8  mov     [rbp+360h+var_398], edi
0x140032deb  movups  xmmword ptr [rbp+360h+var_368+1Ch], xmm0
0x140032def  movups  [rbp+360h+FsInformation], xmm0
0x140032df3  movups  xmmword ptr [rbp+360h+var_368.Length], xmm0
0x140032df7  movups  xmmword ptr [rbp+360h+Iosb], xmm0
0x140032dfb  movups  xmm0, xmmword ptr cs:aNameNotAvailab+10h; " Available"
0x140032e02  movups  [rbp+360h+var_300], xmm1
0x140032e06  movsd   xmm1, qword ptr cs:aNameNotAvailab+1Eh; "ble"
0x140032e0e  movups  xmmword ptr [rbp+360h+var_2F0], xmm0
0x140032e12  movsd   qword ptr [rbp+360h+var_2F0+0Eh], xmm1
0x140032e17  xorps   xmm0, xmm0
0x140032e1a  xorps   xmm1, xmm1
0x140032e1d  movups  xmmword ptr [rbp+360h+VolumeGuidName.Length], xmm1
0x140032e21  movups  [rbp+360h+var_310], xmm0
0x140032e25  movups  xmmword ptr [rbp+360h+String1.Length], xmm0
0x140032e29  cmp     r9d, 1Ch
0x140032e2d  ja      loc_14003387C
0x140032e33  mov     eax, 10002044h
0x140032e38  bt      eax, r9d
0x140032e3c  jnb     loc_14003387C
0x140032e42  mov     rcx, [rcx+18h]; Instance
0x140032e46  lea     rax, [rbp+360h+var_300]
0x140032e4a  mov     [rbp+360h+var_378], rax
0x140032e4e  lea     r12d, [rdi+13h]
0x140032e52  lea     rax, [rbp+360h+var_398]
0x140032e56  mov     [rbp+360h+P], rdi
0x140032e5a  mov     r9d, 210h; BufferSize
0x140032e60  mov     [rsp+460h+BytesReturned], rax; BytesReturned
0x140032e65  lea     r8, [rbp+360h+Buffer]; Buffer
0x140032e6c  mov     [rbp+360h+var_3DC], r12d
0x140032e70  xor     edx, edx; InformationClass
0x140032e72  call    cs:__imp_FltGetInstanceInformation
0x140032e79  nop     dword ptr [rax+rax+00h]
0x140032e7e  mov     ebx, eax
0x140032e80  test    eax, eax
0x140032e82  jns     short loc_140032ECE
0x140032e84  lea     rdi, WPP_RECORDER_INITIALIZED
0x140032e8b  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140032e92  jz      loc_14003301A
0x140032e98  mov     rcx, cs:wil_details_featureDescriptors_a
0x140032e9f  lea     r9d, [r12+2]
0x140032ea4  mov     [rsp+460h+CreateDisposition], eax
0x140032ea8  mov     dl, 2
0x140032eaa  mov     [rsp+460h+ShareAccess], esi
0x140032eae  mov     [rsp+460h+FileAttributes], r14d
0x140032eb3  mov     rcx, [rcx+40h]
0x140032eb7  mov     dword ptr [rsp+460h+AllocationSize], r15d
0x140032ebc  mov     dword ptr [rsp+460h+IoStatusBlock], 2D0h
0x140032ec4  call    WPP_RECORDER_SF_sDlLDd
0x140032ec9  jmp     loc_14003301A
0x140032ece  mov     rax, [rbp+360h+var_25C]
0x140032ed5  lea     rcx, [rbp+360h+Buffer]
0x140032edc  mov     [rbp+360h+String1.Length], ax
0x140032ee0  lea     rdx, SourceString; String2
0x140032ee7  mov     [rbp+360h+String1.MaximumLength], ax
0x140032eeb  xor     r8d, r8d; CaseInSensitive
0x140032eee  movzx   eax, word ptr [rbp+360h+var_25C+2]
0x140032ef5  add     rcx, rax
0x140032ef8  mov     [rbp+360h+var_3E0], dil
0x140032efc  mov     [rbp+360h+String1.Buffer], rcx
0x140032f00  lea     rcx, [rbp+360h+String1]; String1
0x140032f04  call    cs:__imp_RtlEqualUnicodeString
0x140032f0b  nop     dword ptr [rax+rax+00h]
0x140032f10  xor     r8d, r8d; CaseInSensitive
0x140032f13  lea     rdx, stru_14000A630; String2
0x140032f1a  lea     rcx, [rbp+360h+String1]; String1
0x140032f1e  mov     [rbp+360h+var_3D7], al
0x140032f21  call    cs:__imp_RtlEqualUnicodeString
0x140032f28  nop     dword ptr [rax+rax+00h]
0x140032f2d  mov     ebx, [rbp+360h+var_3C0]
0x140032f30  lea     rdi, WPP_RECORDER_INITIALIZED
0x140032f37  mov     [rbp+360h+var_3C8], al
0x140032f3a  lea     r15, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\wcifs\\wcifs.c"
0x140032f41  lea     r12, WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids
0x140032f48  mov     esi, 4
0x140032f4d  test    bl, 1
0x140032f50  jz      loc_14003308B
0x140032f56  cmp     r14d, 2
0x140032f5a  jnz     loc_140033176
0x140032f60  lea     r8d, [rsi+0Ch]; Size
0x140032f64  lea     rdx, NULL_GUID; Buf2
0x140032f6b  lea     rcx, Guid; Buf1
0x140032f72  call    memcmp
0x140032f77  xor     ecx, ecx
0x140032f79  test    eax, eax
0x140032f7b  jz      loc_140033075
0x140032f81  xor     r8d, r8d; CaseInSensitive
0x140032f84  lea     rdx, DestinationString; String2
0x140032f8b  lea     rcx, [rbp+360h+String1]; String1
0x140032f8f  call    cs:__imp_RtlCompareUnicodeString
0x140032f96  nop     dword ptr [rax+rax+00h]
0x140032f9b  xor     ecx, ecx
0x140032f9d  test    eax, eax
0x140032f9f  jnz     loc_140033075
0x140032fa5  mov     [rbp+360h+DiskDeviceObject], rcx
0x140032fa9  lea     rdx, [rbp+360h+DiskDeviceObject]; DiskDeviceObject
0x140032fad  mov     rcx, [r13+10h]; Volume
0x140032fb1  call    cs:__imp_FltGetDiskDeviceObject
0x140032fb8  nop     dword ptr [rax+rax+00h]
0x140032fbd  mov     ebx, eax
0x140032fbf  test    eax, eax
0x140032fc1  jns     loc_14003304F
0x140032fc7  lea     rdi, WPP_RECORDER_INITIALIZED
0x140032fce  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140032fd5  jz      short loc_140033014
0x140032fd7  mov     dword ptr [rsp+460h+AllocationSize], eax
0x140032fdb  lea     r9d, [rsi+12h]
0x140032fdf  mov     dword ptr [rsp+460h+IoStatusBlock], 2FEh
0x140032fe7  lea     r15, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\wcifs\\wcifs.c"
0x140032fee  lea     r12, WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids
0x140032ff5  mov     rcx, cs:wil_details_featureDescriptors_a
0x140032ffc  mov     r8d, esi
0x140032fff  mov     [rsp+460h+ObjectAttributes], r15
0x140033004  mov     dl, 2
0x140033006  mov     [rsp+460h+BytesReturned], r12
0x14003300b  mov     rcx, [rcx+40h]
0x14003300f  call    WPP_RECORDER_SF_sDd
0x140033014  mov     r12d, 13h
0x14003301a  cmp     ebx, 0C01C000Fh
0x140033020  jz      loc_14003381E
0x140033026  test    byte ptr cs:WPP_MAIN_CB.Queue, 1
0x14003302d  jz      loc_14003381E
0x140033033  mov     rax, [rbp+360h+var_378]
0x140033037  mov     r9d, ebx
0x14003303a  mov     [rsp+460h+ObjectAttributes], rax
0x14003303f  mov     word ptr [rsp+460h+BytesReturned], r12w
0x140033045  call    McTemplateK0dhzr1_EtwWriteTransfer
0x14003304a  jmp     loc_14003381E
0x14003304f  mov     rcx, [rbp+360h+DiskDeviceObject]; Object
0x140033053  mov     ebx, [rcx+30h]
0x140033056  call    cs:__imp_ObfDereferenceObject
0x14003305d  nop     dword ptr [rax+rax+00h]
0x140033062  xor     ecx, ecx
0x140033064  bt      ebx, 8
0x140033068  setb    [rbp+360h+var_3E0]
0x14003306c  bt      ebx, 8
0x140033070  jb      short loc_1400330AD
0x140033072  mov     ebx, [rbp+360h+var_3C0]
0x140033075  cmp     [rbp+360h+var_3D7], cl
0x140033078  jz      short loc_14003308B
0x14003307a  mov     rdx, [r13+10h]; Volume
0x14003307e  mov     rcx, [r13+18h]; InitiatingInstance
0x140033082  call    WcShouldAutoAttach
0x140033087  test    al, al
0x140033089  jnz     short loc_1400330AD
0x14003308b  test    bl, 2
0x14003308e  jz      loc_140033819
0x140033094  cmp     r14d, 1Ch
0x140033098  ja      loc_140033819
0x14003309e  mov     eax, 10002044h
0x1400330a3  bt      eax, r14d
0x1400330a7  jnb     loc_140033819
0x1400330ad  mov     rcx, [r13+10h]; FltObject
0x1400330b1  lea     rdx, [rbp+360h+IsSnapshotVolume]; IsSnapshotVolume
0x1400330b5  call    cs:__imp_FltIsVolumeSnapshot
0x1400330bc  nop     dword ptr [rax+rax+00h]
0x1400330c1  xor     edx, edx
0x1400330c3  test    eax, eax
0x1400330c5  jns     loc_1400331D3
0x1400330cb  cmp     eax, 0C01C0019h
0x1400330d0  jz      short loc_140033112
0x1400330d2  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400330d9  jz      short loc_140033112
0x1400330db  mov     rcx, cs:wil_details_featureDescriptors_a
0x1400330e2  lea     r9d, [rdx+18h]
0x1400330e6  mov     [rsp+460h+CreateDisposition], eax
0x1400330ea  mov     dl, 3
0x1400330ec  mov     eax, [rbp+360h+var_3C0]
0x1400330ef  mov     [rsp+460h+ShareAccess], eax
0x1400330f3  mov     eax, [rbp+360h+var_3BC]
0x1400330f6  mov     rcx, [rcx+40h]
0x1400330fa  mov     [rsp+460h+FileAttributes], r14d
0x1400330ff  mov     dword ptr [rsp+460h+AllocationSize], eax
0x140033103  mov     dword ptr [rsp+460h+IoStatusBlock], 337h
0x14003310b  call    WPP_RECORDER_SF_sDlLDd
0x140033110  xor     edx, edx
0x140033112  cmp     cs:byte_14000E680, dl
0x140033118  lea     rax, [rbp+360h+ReturnedContext]
0x14003311c  mov     rcx, [r13+8]; Filter
0x140033120  mov     r9d, 200h; PoolType
0x140033126  mov     [rsp+460h+BytesReturned], rax; ReturnedContext
0x14003312b  mov     edx, 2; ContextType
0x140033130  jz      loc_14003325B
0x140033136  mov     r8d, 13Ch; ContextSize
0x14003313c  call    cs:__imp_FltAllocateContext
0x140033143  nop     dword ptr [rax+rax+00h]
0x140033148  xor     edx, edx; Val
0x14003314a  mov     ebx, eax
0x14003314c  test    eax, eax
0x14003314e  jns     loc_140033233
0x140033154  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003315b  jz      loc_140033014
0x140033161  mov     dword ptr [rsp+460h+AllocationSize], eax
0x140033165  lea     r9d, [rdx+1Ah]
0x140033169  mov     dword ptr [rsp+460h+IoStatusBlock], 357h
0x140033171  jmp     loc_140032FF5
0x140033176  xor     eax, eax
0x140033178  mov     [rbp+360h+var_3E0], al
0x14003317b  cmp     r14d, 6
0x14003317f  jnz     loc_14003308B
0x140033185  cmp     cs:Context, rax
0x14003318c  mov     [rbp+360h+var_3E0], al
0x14003318f  jz      loc_14003308B
0x140033195  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003319c  jz      short loc_1400331CA
0x14003319e  mov     rcx, cs:wil_details_featureDescriptors_a
0x1400331a5  lea     r9d, [rax+17h]
0x1400331a9  mov     dword ptr [rsp+460h+IoStatusBlock], 31Ch
0x1400331b1  mov     r8d, esi
0x1400331b4  mov     [rsp+460h+ObjectAttributes], r15
0x1400331b9  mov     dl, sil
0x1400331bc  mov     [rsp+460h+BytesReturned], r12
0x1400331c1  mov     rcx, [rcx+40h]
0x1400331c5  call    WPP_RECORDER_SF_sD
0x1400331ca  mov     [rbp+360h+var_3E0], 1
0x1400331ce  jmp     loc_1400330AD
0x1400331d3  cmp     [rbp+360h+IsSnapshotVolume], dl
0x1400331d6  jz      loc_140033112
0x1400331dc  mov     ebx, 0C01C000Fh
0x1400331e1  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400331e8  jz      loc_14003381E
0x1400331ee  mov     rax, cs:wil_details_featureDescriptors_a
0x1400331f5  cmp     [rax+48h], dx
0x1400331f9  jz      loc_14003381E
0x1400331ff  mov     eax, [rbp+360h+var_3C0]
0x140033202  mov     r9d, 19h
0x140033208  mov     rcx, cs:_WcVerboseRecorder
0x14003320f  mov     dl, 5
0x140033211  mov     [rsp+460h+ShareAccess], eax
0x140033215  mov     eax, [rbp+360h+var_3BC]
0x140033218  mov     [rsp+460h+FileAttributes], r14d
0x14003321d  mov     dword ptr [rsp+460h+AllocationSize], eax
0x140033221  mov     dword ptr [rsp+460h+IoStatusBlock], 343h
0x140033229  call    WPP_RECORDER_SF_sDlLD
0x14003322e  jmp     loc_14003381E
0x140033233  mov     rcx, [rbp+360h+ReturnedContext]; void *
0x140033237  mov     r8d, 130h; Size
0x14003323d  call    memset
0x140033242  mov     rax, [rbp+360h+ReturnedContext]
0x140033246  lea     rcx, [rax+130h]
0x14003324d  mov     [rax+20h], rcx
0x140033251  xor     eax, eax
0x140033253  mov     [rcx], rax
0x140033256  mov     [rcx+8], eax
0x140033259  jmp     short loc_1400332A6
0x14003325b  mov     r8d, 130h; ContextSize
0x140033261  call    cs:__imp_FltAllocateContext
0x140033268  nop     dword ptr [rax+rax+00h]
0x14003326d  xor     edx, edx; Val
0x14003326f  mov     ebx, eax
0x140033271  test    eax, eax
0x140033273  jns     short loc_140033297
0x140033275  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003327c  jz      loc_140033014
0x140033282  mov     dword ptr [rsp+460h+AllocationSize], eax
0x140033286  lea     r9d, [rdx+1Bh]
0x14003328a  mov     dword ptr [rsp+460h+IoStatusBlock], 36Bh
0x140033292  jmp     loc_140032FF5
0x140033297  mov     rcx, [rbp+360h+ReturnedContext]; void *
0x14003329b  mov     r8d, 130h; Size
0x1400332a1  call    memset
0x1400332a6  mov     rax, [rbp+360h+ReturnedContext]
0x1400332aa  xor     ebx, ebx
0x1400332ac  mov     rcx, [r13+18h]
0x1400332b0  mov     [rax], rcx
0x1400332b3  mov     rax, [rbp+360h+ReturnedContext]
0x1400332b7  mov     [rax+8], r14d
0x1400332bb  cmp     [rbp+360h+var_3D7], bl
0x1400332be  jz      short loc_1400332CF
0x1400332c0  mov     rcx, [rbp+360h+ReturnedContext]
  ... truncated ...
```
