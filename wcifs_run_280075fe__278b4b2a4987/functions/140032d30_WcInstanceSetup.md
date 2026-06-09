# WcInstanceSetup

- ea: `0x140032d30`
- end: `0x140033857`
- name: `WcInstanceSetup`
- size: `2855`
- prototype: ``
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
- `0x14002e3f4`
- `0x140032d30`

## import_xrefs

- `ntoskrnl!IoGetBootLayers` at `0x1400336b6`
- `ntoskrnl!IoGetBootLayers` at `0x1400336b6`
- `ntoskrnl!IoMountBootLayer` at `0x14003370d`
- `ntoskrnl!IoMountBootLayer` at `0x14003370d`
- `ntoskrnl!RtlGUIDFromString` at `0x140033598`
- `ntoskrnl!RtlGUIDFromString` at `0x140033598`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140033654`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140033654`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140032eb4`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140032ed1`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140032eb4`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140032ed1`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140032f3f`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140032f3f`
- `ntoskrnl!ObfDereferenceObject` at `0x140033006`
- `ntoskrnl!ObfDereferenceObject` at `0x140033809`
- `ntoskrnl!ObfDereferenceObject` at `0x140033006`
- `ntoskrnl!ObfDereferenceObject` at `0x140033809`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400332e2`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400332e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400337f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400337f4`
- `ntoskrnl!ExAllocatePool2` at `0x14003332e`
- `ntoskrnl!ExAllocatePool2` at `0x14003332e`
- `FLTMGR!FltAllocateContext` at `0x1400330ec`
- `FLTMGR!FltAllocateContext` at `0x140033211`
- `FLTMGR!FltAllocateContext` at `0x1400330ec`
- `FLTMGR!FltAllocateContext` at `0x140033211`
- `FLTMGR!FltGetDiskDeviceObject` at `0x140032f61`
- `FLTMGR!FltGetDiskDeviceObject` at `0x140032f61`
- `FLTMGR!FltSetInstanceContext` at `0x14003366f`
- `FLTMGR!FltSetInstanceContext` at `0x14003366f`
- `FLTMGR!FltQueryVolumeInformation` at `0x1400335ea`
- `FLTMGR!FltQueryVolumeInformation` at `0x1400335ea`
- `FLTMGR!FltGetVolumeGuidName` at `0x140033548`
- `FLTMGR!FltGetVolumeGuidName` at `0x140033548`
- `FLTMGR!FltGetVolumeProperties` at `0x14003330b`
- `FLTMGR!FltGetVolumeProperties` at `0x1400333b0`
- `FLTMGR!FltGetVolumeProperties` at `0x14003330b`
- `FLTMGR!FltGetVolumeProperties` at `0x1400333b0`
- `FLTMGR!FltIsVolumeSnapshot` at `0x140033065`
- `FLTMGR!FltIsVolumeSnapshot` at `0x140033065`
- `FLTMGR!FltGetInstanceInformation` at `0x140032e22`
- `FLTMGR!FltGetInstanceInformation` at `0x140032e22`
- `FLTMGR!FltQueryVolumeInformationFile` at `0x1400334ed`
- `FLTMGR!FltQueryVolumeInformationFile` at `0x1400334ed`
- `FLTMGR!FltCreateFileEx` at `0x140033479`
- `FLTMGR!FltCreateFileEx` at `0x140033479`
- `FLTMGR!FltClose` at `0x14003381e`
- `FLTMGR!FltClose` at `0x14003381e`
- `FLTMGR!FltReleaseContext` at `0x140033749`
- `FLTMGR!FltReleaseContext` at `0x1400337d7`
- `FLTMGR!FltReleaseContext` at `0x140033749`
- `FLTMGR!FltReleaseContext` at `0x1400337d7`

## pseudocode

```c
__int64 __fastcall WcInstanceSetup(struct _FLT_FILTER **a1, int a2, int a3, unsigned int a4)
{
  int v6; // eax
  struct _FLT_INSTANCE *v7; // rcx
  __int16 v8; // r12
  int v9; // edx
  int v10; // ecx
  NTSTATUS InstanceInformation; // ebx
  int v12; // r8d
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
      WPP_RECORDER_SF_sDlLDd(WPP_GLOBAL_Control->DeviceExtension, v9, v12, 21, BytesReturned);
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
            WPP_GLOBAL_Control->DeviceExtension,
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
              && LOWORD(WPP_GLOBAL_Control->DeviceType) )
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
          WPP_RECORDER_SF_sDlLDd(WPP_GLOBAL_Control->DeviceExtension, v21, v20, 24, BytesReturned);
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
              WPP_GLOBAL_Control->DeviceExtension,
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
                WPP_GLOBAL_Control->DeviceExtension,
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
            WcCompareUnionTableEntry,
            WcAllocateUnionTableEntry,
            WcFreeUnionTableEntry,
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
                  WPP_GLOBAL_Control->DeviceExtension,
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
          WPP_GLOBAL_Control->DeviceExtension,
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
              WPP_GLOBAL_Control->DeviceExtension,
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
0x140032d30  push    rbp
0x140032d32  push    rbx
0x140032d33  push    rsi
0x140032d34  push    rdi
0x140032d35  push    r12
0x140032d37  push    r13
0x140032d39  push    r14
0x140032d3b  push    r15
0x140032d3d  lea     rbp, [rsp-328h]
0x140032d45  sub     rsp, 428h
0x140032d4c  mov     rax, cs:__security_cookie
0x140032d53  xor     rax, rsp
0x140032d56  mov     [rbp+360h+var_50], rax
0x140032d5d  movups  xmm1, xmmword ptr cs:aNameNotAvailab; "Name Not Available"
0x140032d64  mov     [rbp+360h+var_3BC], r8d
0x140032d68  xor     edi, edi
0x140032d6a  xorps   xmm0, xmm0
0x140032d6d  mov     [rbp+360h+var_3C0], edx
0x140032d70  movups  xmmword ptr [rbp+360h+var_368.ObjectName], xmm0
0x140032d74  xor     eax, eax
0x140032d76  mov     r14d, r9d
0x140032d79  mov     [rbp+360h+ReturnedContext], rdi
0x140032d7d  mov     r15d, r8d
0x140032d80  mov     [rbp+360h+IsSnapshotVolume], dil
0x140032d84  mov     esi, edx
0x140032d86  mov     [rbp+360h+var_318], rax
0x140032d8a  mov     r13, rcx
0x140032d8d  mov     [rbp+360h+LengthReturned], edi
0x140032d90  mov     [rbp+360h+FileObject], rdi
0x140032d94  mov     [rbp+360h+FileHandle], rdi
0x140032d98  mov     [rbp+360h+var_398], edi
0x140032d9b  movups  xmmword ptr [rbp+360h+var_368+1Ch], xmm0
0x140032d9f  movups  [rbp+360h+FsInformation], xmm0
0x140032da3  movups  xmmword ptr [rbp+360h+var_368.Length], xmm0
0x140032da7  movups  xmmword ptr [rbp+360h+Iosb], xmm0
0x140032dab  movups  xmm0, xmmword ptr cs:aNameNotAvailab+10h; " Available"
0x140032db2  movups  [rbp+360h+var_300], xmm1
0x140032db6  movsd   xmm1, qword ptr cs:aNameNotAvailab+1Eh; "ble"
0x140032dbe  movups  xmmword ptr [rbp+360h+var_2F0], xmm0
0x140032dc2  movsd   qword ptr [rbp+360h+var_2F0+0Eh], xmm1
0x140032dc7  xorps   xmm0, xmm0
0x140032dca  xorps   xmm1, xmm1
0x140032dcd  movups  xmmword ptr [rbp+360h+VolumeGuidName.Length], xmm1
0x140032dd1  movups  [rbp+360h+var_310], xmm0
0x140032dd5  movups  xmmword ptr [rbp+360h+String1.Length], xmm0
0x140032dd9  cmp     r9d, 1Ch
0x140032ddd  ja      loc_14003382C
0x140032de3  mov     eax, 10002044h
0x140032de8  bt      eax, r9d
0x140032dec  jnb     loc_14003382C
0x140032df2  mov     rcx, [rcx+18h]; Instance
0x140032df6  lea     rax, [rbp+360h+var_300]
0x140032dfa  mov     [rbp+360h+var_378], rax
0x140032dfe  lea     r12d, [rdi+13h]
0x140032e02  lea     rax, [rbp+360h+var_398]
0x140032e06  mov     [rbp+360h+P], rdi
0x140032e0a  mov     r9d, 210h; BufferSize
0x140032e10  mov     [rsp+460h+BytesReturned], rax; BytesReturned
0x140032e15  lea     r8, [rbp+360h+Buffer]; Buffer
0x140032e1c  mov     [rbp+360h+var_3DC], r12d
0x140032e20  xor     edx, edx; InformationClass
0x140032e22  call    cs:__imp_FltGetInstanceInformation
0x140032e29  nop     dword ptr [rax+rax+00h]
0x140032e2e  mov     ebx, eax
0x140032e30  test    eax, eax
0x140032e32  jns     short loc_140032E7E
0x140032e34  lea     rdi, WPP_RECORDER_INITIALIZED
0x140032e3b  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140032e42  jz      loc_140032FCA
0x140032e48  mov     rcx, cs:WPP_GLOBAL_Control
0x140032e4f  lea     r9d, [r12+2]
0x140032e54  mov     [rsp+460h+CreateDisposition], eax
0x140032e58  mov     dl, 2
0x140032e5a  mov     [rsp+460h+ShareAccess], esi
0x140032e5e  mov     [rsp+460h+FileAttributes], r14d
0x140032e63  mov     rcx, [rcx+40h]
0x140032e67  mov     dword ptr [rsp+460h+AllocationSize], r15d
0x140032e6c  mov     dword ptr [rsp+460h+IoStatusBlock], 2D0h
0x140032e74  call    WPP_RECORDER_SF_sDlLDd
0x140032e79  jmp     loc_140032FCA
0x140032e7e  mov     rax, [rbp+360h+var_25C]
0x140032e85  lea     rcx, [rbp+360h+Buffer]
0x140032e8c  mov     [rbp+360h+String1.Length], ax
0x140032e90  lea     rdx, SourceString; String2
0x140032e97  mov     [rbp+360h+String1.MaximumLength], ax
0x140032e9b  xor     r8d, r8d; CaseInSensitive
0x140032e9e  movzx   eax, word ptr [rbp+360h+var_25C+2]
0x140032ea5  add     rcx, rax
0x140032ea8  mov     [rbp+360h+var_3E0], dil
0x140032eac  mov     [rbp+360h+String1.Buffer], rcx
0x140032eb0  lea     rcx, [rbp+360h+String1]; String1
0x140032eb4  call    cs:__imp_RtlEqualUnicodeString
0x140032ebb  nop     dword ptr [rax+rax+00h]
0x140032ec0  xor     r8d, r8d; CaseInSensitive
0x140032ec3  lea     rdx, stru_14000A630; String2
0x140032eca  lea     rcx, [rbp+360h+String1]; String1
0x140032ece  mov     [rbp+360h+var_3D7], al
0x140032ed1  call    cs:__imp_RtlEqualUnicodeString
0x140032ed8  nop     dword ptr [rax+rax+00h]
0x140032edd  mov     ebx, [rbp+360h+var_3C0]
0x140032ee0  lea     rdi, WPP_RECORDER_INITIALIZED
0x140032ee7  mov     [rbp+360h+var_3C8], al
0x140032eea  lea     r15, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\wcifs\\wcifs.c"
0x140032ef1  lea     r12, WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids
0x140032ef8  mov     esi, 4
0x140032efd  test    bl, 1
0x140032f00  jz      loc_14003303B
0x140032f06  cmp     r14d, 2
0x140032f0a  jnz     loc_140033126
0x140032f10  lea     r8d, [rsi+0Ch]; Size
0x140032f14  lea     rdx, NULL_GUID; Buf2
0x140032f1b  lea     rcx, Guid; Buf1
0x140032f22  call    memcmp
0x140032f27  xor     ecx, ecx
0x140032f29  test    eax, eax
0x140032f2b  jz      loc_140033025
0x140032f31  xor     r8d, r8d; CaseInSensitive
0x140032f34  lea     rdx, DestinationString; String2
0x140032f3b  lea     rcx, [rbp+360h+String1]; String1
0x140032f3f  call    cs:__imp_RtlCompareUnicodeString
0x140032f46  nop     dword ptr [rax+rax+00h]
0x140032f4b  xor     ecx, ecx
0x140032f4d  test    eax, eax
0x140032f4f  jnz     loc_140033025
0x140032f55  mov     [rbp+360h+DiskDeviceObject], rcx
0x140032f59  lea     rdx, [rbp+360h+DiskDeviceObject]; DiskDeviceObject
0x140032f5d  mov     rcx, [r13+10h]; Volume
0x140032f61  call    cs:__imp_FltGetDiskDeviceObject
0x140032f68  nop     dword ptr [rax+rax+00h]
0x140032f6d  mov     ebx, eax
0x140032f6f  test    eax, eax
0x140032f71  jns     loc_140032FFF
0x140032f77  lea     rdi, WPP_RECORDER_INITIALIZED
0x140032f7e  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140032f85  jz      short loc_140032FC4
0x140032f87  mov     dword ptr [rsp+460h+AllocationSize], eax
0x140032f8b  lea     r9d, [rsi+12h]
0x140032f8f  mov     dword ptr [rsp+460h+IoStatusBlock], 2FEh
0x140032f97  lea     r15, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\wcifs\\wcifs.c"
0x140032f9e  lea     r12, WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids
0x140032fa5  mov     rcx, cs:WPP_GLOBAL_Control
0x140032fac  mov     r8d, esi
0x140032faf  mov     [rsp+460h+ObjectAttributes], r15
0x140032fb4  mov     dl, 2
0x140032fb6  mov     [rsp+460h+BytesReturned], r12
0x140032fbb  mov     rcx, [rcx+40h]
0x140032fbf  call    WPP_RECORDER_SF_sDd
0x140032fc4  mov     r12d, 13h
0x140032fca  cmp     ebx, 0C01C000Fh
0x140032fd0  jz      loc_1400337CE
0x140032fd6  test    byte ptr cs:WPP_MAIN_CB.Queue, 1
0x140032fdd  jz      loc_1400337CE
0x140032fe3  mov     rax, [rbp+360h+var_378]
0x140032fe7  mov     r9d, ebx
0x140032fea  mov     [rsp+460h+ObjectAttributes], rax
0x140032fef  mov     word ptr [rsp+460h+BytesReturned], r12w
0x140032ff5  call    McTemplateK0dhzr1_EtwWriteTransfer
0x140032ffa  jmp     loc_1400337CE
0x140032fff  mov     rcx, [rbp+360h+DiskDeviceObject]; Object
0x140033003  mov     ebx, [rcx+30h]
0x140033006  call    cs:__imp_ObfDereferenceObject
0x14003300d  nop     dword ptr [rax+rax+00h]
0x140033012  xor     ecx, ecx
0x140033014  bt      ebx, 8
0x140033018  setb    [rbp+360h+var_3E0]
0x14003301c  bt      ebx, 8
0x140033020  jb      short loc_14003305D
0x140033022  mov     ebx, [rbp+360h+var_3C0]
0x140033025  cmp     [rbp+360h+var_3D7], cl
0x140033028  jz      short loc_14003303B
0x14003302a  mov     rdx, [r13+10h]; Volume
0x14003302e  mov     rcx, [r13+18h]; InitiatingInstance
0x140033032  call    WcShouldAutoAttach
0x140033037  test    al, al
0x140033039  jnz     short loc_14003305D
0x14003303b  test    bl, 2
0x14003303e  jz      loc_1400337C9
0x140033044  cmp     r14d, 1Ch
0x140033048  ja      loc_1400337C9
0x14003304e  mov     eax, 10002044h
0x140033053  bt      eax, r14d
0x140033057  jnb     loc_1400337C9
0x14003305d  mov     rcx, [r13+10h]; FltObject
0x140033061  lea     rdx, [rbp+360h+IsSnapshotVolume]; IsSnapshotVolume
0x140033065  call    cs:__imp_FltIsVolumeSnapshot
0x14003306c  nop     dword ptr [rax+rax+00h]
0x140033071  xor     edx, edx
0x140033073  test    eax, eax
0x140033075  jns     loc_140033183
0x14003307b  cmp     eax, 0C01C0019h
0x140033080  jz      short loc_1400330C2
0x140033082  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140033089  jz      short loc_1400330C2
0x14003308b  mov     rcx, cs:WPP_GLOBAL_Control
0x140033092  lea     r9d, [rdx+18h]
0x140033096  mov     [rsp+460h+CreateDisposition], eax
0x14003309a  mov     dl, 3
0x14003309c  mov     eax, [rbp+360h+var_3C0]
0x14003309f  mov     [rsp+460h+ShareAccess], eax
0x1400330a3  mov     eax, [rbp+360h+var_3BC]
0x1400330a6  mov     rcx, [rcx+40h]
0x1400330aa  mov     [rsp+460h+FileAttributes], r14d
0x1400330af  mov     dword ptr [rsp+460h+AllocationSize], eax
0x1400330b3  mov     dword ptr [rsp+460h+IoStatusBlock], 337h
0x1400330bb  call    WPP_RECORDER_SF_sDlLDd
0x1400330c0  xor     edx, edx
0x1400330c2  cmp     cs:byte_14000E680, dl
0x1400330c8  lea     rax, [rbp+360h+ReturnedContext]
0x1400330cc  mov     rcx, [r13+8]; Filter
0x1400330d0  mov     r9d, 200h; PoolType
0x1400330d6  mov     [rsp+460h+BytesReturned], rax; ReturnedContext
0x1400330db  mov     edx, 2; ContextType
0x1400330e0  jz      loc_14003320B
0x1400330e6  mov     r8d, 13Ch; ContextSize
0x1400330ec  call    cs:__imp_FltAllocateContext
0x1400330f3  nop     dword ptr [rax+rax+00h]
0x1400330f8  xor     edx, edx; Val
0x1400330fa  mov     ebx, eax
0x1400330fc  test    eax, eax
0x1400330fe  jns     loc_1400331E3
0x140033104  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003310b  jz      loc_140032FC4
0x140033111  mov     dword ptr [rsp+460h+AllocationSize], eax
0x140033115  lea     r9d, [rdx+1Ah]
0x140033119  mov     dword ptr [rsp+460h+IoStatusBlock], 357h
0x140033121  jmp     loc_140032FA5
0x140033126  xor     eax, eax
0x140033128  mov     [rbp+360h+var_3E0], al
0x14003312b  cmp     r14d, 6
0x14003312f  jnz     loc_14003303B
0x140033135  cmp     cs:Context, rax
0x14003313c  mov     [rbp+360h+var_3E0], al
0x14003313f  jz      loc_14003303B
0x140033145  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003314c  jz      short loc_14003317A
0x14003314e  mov     rcx, cs:WPP_GLOBAL_Control
0x140033155  lea     r9d, [rax+17h]
0x140033159  mov     dword ptr [rsp+460h+IoStatusBlock], 31Ch
0x140033161  mov     r8d, esi
0x140033164  mov     [rsp+460h+ObjectAttributes], r15
0x140033169  mov     dl, sil
0x14003316c  mov     [rsp+460h+BytesReturned], r12
0x140033171  mov     rcx, [rcx+40h]
0x140033175  call    WPP_RECORDER_SF_sD
0x14003317a  mov     [rbp+360h+var_3E0], 1
0x14003317e  jmp     loc_14003305D
0x140033183  cmp     [rbp+360h+IsSnapshotVolume], dl
0x140033186  jz      loc_1400330C2
0x14003318c  mov     ebx, 0C01C000Fh
0x140033191  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140033198  jz      loc_1400337CE
0x14003319e  mov     rax, cs:WPP_GLOBAL_Control
0x1400331a5  cmp     [rax+48h], dx
0x1400331a9  jz      loc_1400337CE
0x1400331af  mov     eax, [rbp+360h+var_3C0]
0x1400331b2  mov     r9d, 19h
0x1400331b8  mov     rcx, cs:_WcVerboseRecorder
0x1400331bf  mov     dl, 5
0x1400331c1  mov     [rsp+460h+ShareAccess], eax
0x1400331c5  mov     eax, [rbp+360h+var_3BC]
0x1400331c8  mov     [rsp+460h+FileAttributes], r14d
0x1400331cd  mov     dword ptr [rsp+460h+AllocationSize], eax
0x1400331d1  mov     dword ptr [rsp+460h+IoStatusBlock], 343h
0x1400331d9  call    WPP_RECORDER_SF_sDlLD
0x1400331de  jmp     loc_1400337CE
0x1400331e3  mov     rcx, [rbp+360h+ReturnedContext]; void *
0x1400331e7  mov     r8d, 130h; Size
0x1400331ed  call    memset
0x1400331f2  mov     rax, [rbp+360h+ReturnedContext]
0x1400331f6  lea     rcx, [rax+130h]
0x1400331fd  mov     [rax+20h], rcx
0x140033201  xor     eax, eax
0x140033203  mov     [rcx], rax
0x140033206  mov     [rcx+8], eax
0x140033209  jmp     short loc_140033256
0x14003320b  mov     r8d, 130h; ContextSize
0x140033211  call    cs:__imp_FltAllocateContext
0x140033218  nop     dword ptr [rax+rax+00h]
0x14003321d  xor     edx, edx; Val
0x14003321f  mov     ebx, eax
0x140033221  test    eax, eax
0x140033223  jns     short loc_140033247
0x140033225  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003322c  jz      loc_140032FC4
0x140033232  mov     dword ptr [rsp+460h+AllocationSize], eax
0x140033236  lea     r9d, [rdx+1Bh]
0x14003323a  mov     dword ptr [rsp+460h+IoStatusBlock], 36Bh
0x140033242  jmp     loc_140032FA5
0x140033247  mov     rcx, [rbp+360h+ReturnedContext]; void *
0x14003324b  mov     r8d, 130h; Size
0x140033251  call    memset
0x140033256  mov     rax, [rbp+360h+ReturnedContext]
0x14003325a  xor     ebx, ebx
0x14003325c  mov     rcx, [r13+18h]
0x140033260  mov     [rax], rcx
0x140033263  mov     rax, [rbp+360h+ReturnedContext]
0x140033267  mov     [rax+8], r14d
0x14003326b  cmp     [rbp+360h+var_3D7], bl
0x14003326e  jz      short loc_14003327F
0x140033270  mov     rcx, [rbp+360h+ReturnedContext]
  ... truncated ...
```
