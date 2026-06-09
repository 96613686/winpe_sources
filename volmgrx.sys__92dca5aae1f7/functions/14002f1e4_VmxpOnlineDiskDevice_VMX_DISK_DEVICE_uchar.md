# VmxpOnlineDiskDevice(VMX_DISK_DEVICE *,uchar)

- ea: `0x14002f1e4`
- end: `0x14002fbeb`
- name: `?VmxpOnlineDiskDevice@@YAXPEAVVMX_DISK_DEVICE@@E@Z`
- size: `2567`
- prototype: `void __fastcall(struct VMX_DISK_DEVICE *this)`
- caller_count: `3`
- callee_count: `42`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x140031390`
- `0x14003ae9c`
- `0x14003aefc`

## callees

- `0x140005f80`
- `0x140007600`
- `0x140007b08`
- `0x140008d28`
- `0x140008dc8`
- `0x140008df0`
- `0x140008eec`
- `0x140009718`
- `0x14001b78c`
- `0x14001b960`
- `0x14001b9a0`
- `0x14001ba60`
- `0x14001be80`
- `0x14002b0c4`
- `0x14002d3ec`
- `0x14002d44c`
- `0x14002d75c`
- `0x14002f1e4`
- `0x14002fbf4`
- `0x14002fcfc`
- `0x14002fe20`
- `0x140031648`
- `0x14003261c`
- `0x1400330a4`
- `0x140033750`
- `0x140033a5c`
- `0x140033c48`
- `0x1400375cc`
- `0x14003763c`
- `0x14003769c`
- `0x14003acbc`
- `0x140040690`
- `0x140040de4`
- `0x140043340`
- `0x140046c80`
- `0x140048830`
- `0x140049b04`
- `0x1400531c8`
- `0x140059528`
- `0x14005c600`
- `0x14005d40c`
- `0x14005d734`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002f366`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f44f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f366`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f44f`
- `ntoskrnl!ExUuidCreate` at `0x14002f40f`
- `ntoskrnl!ExUuidCreate` at `0x14002f40f`

## pseudocode

```c
void __fastcall VmxpOnlineDiskDevice(struct VMX_DISK_DEVICE *this)
{
  struct VMX_PHYSICAL_DISK *PhysicalDiskByDevice; // rax
  struct VMX_PHYSICAL_DISK *v3; // r14
  char v4; // r13
  struct VMX_PACK *v5; // rdx
  struct _DRIVE_LAYOUT_INFORMATION_EX *v6; // rbx
  char v7; // r15
  unsigned int i; // edx
  unsigned int v9; // esi
  unsigned int v10; // r12d
  VMX_GLOBAL_DATA *v11; // rax
  VMX_GLOBAL_DATA *v12; // rbx
  UUID *v13; // rcx
  __int64 v14; // rsi
  __int64 v15; // r15
  unsigned int v16; // edx
  unsigned __int8 v17; // di
  PVOID v18; // rcx
  struct VMX_PHYSICAL_DISK *v19; // rcx
  struct VMX_PHYSICAL_DISK **v20; // rax
  struct VMX_PHYSICAL_DISK *v21; // rcx
  VMX_GLOBAL_DATA *v22; // rcx
  char *v23; // rax
  VMX_GLOBAL_DATA **v24; // rdx
  struct _GUID *v25; // rax
  struct VMX_PACK *PackById; // rax
  struct VMX_PACK *v27; // rdi
  __int64 v28; // rcx
  struct VMX_PACK **v29; // rax
  _QWORD *v30; // rcx
  struct VMX_PACK **v31; // rsi
  unsigned int v32; // edx
  unsigned int v33; // edx
  VMX_CONFIG *v34; // rcx
  struct VMX_PACK *v35; // rax
  unsigned int v36; // edx
  VMX_GLOBAL_DATA *v37; // rcx
  struct VMX_PACK **v38; // rdx
  struct VMX_PACK *j; // rcx
  __int64 v40; // rax
  __int64 v41; // rax
  struct VMX_RECORD *v42; // r15
  VMX_CONFIG *DiskById; // rax
  char v44; // si
  struct VMX_LOG_COPY *v45; // rsi
  struct VMX_LOG_COPY *v46; // r12
  _BYTE *v47; // rax
  VMX_GLOBAL_DATA *v48; // r12
  char *v49; // rax
  char *v50; // rsi
  __int64 v51; // rax
  struct VMX_RECORD *v52; // rax
  VMX_PACK *v53; // r12
  VMX_PACK *v54; // rcx
  VMX_PACK **v55; // rax
  unsigned int v56; // edx
  VMX_CONFIG *v57; // r12
  int v58; // eax
  VMX_PHYSICAL_DISK *v59; // rcx
  struct VMX_RECORD *v60; // rax
  struct VMX_RECORD *v61; // r12
  VMX_PACK *v62; // rcx
  VMX_GLOBAL_DATA *v63; // rsi
  __int64 v64; // r15
  struct VMX_PHYSICAL_DISK *v65; // rcx
  struct VMX_PHYSICAL_DISK **v66; // rax
  unsigned __int8 v67; // [rsp+30h] [rbp-49h] BYREF
  unsigned __int8 v68; // [rsp+31h] [rbp-48h] BYREF
  unsigned __int8 v69; // [rsp+32h] [rbp-47h] BYREF
  unsigned __int8 v70[5]; // [rsp+33h] [rbp-46h] BYREF
  PVOID P; // [rsp+38h] [rbp-41h] BYREF
  struct _GUID *v72; // [rsp+40h] [rbp-39h] BYREF
  VMX_CONFIG *DiskByPhysicalDisk; // [rsp+48h] [rbp-31h]
  VMX_GLOBAL_DATA *v74; // [rsp+50h] [rbp-29h]
  __int64 v75; // [rsp+58h] [rbp-21h]
  struct _BOOTDISK_INFORMATION_LITE *v76; // [rsp+60h] [rbp-19h] BYREF
  PVOID v77; // [rsp+68h] [rbp-11h] BYREF
  VMX_PACK *v78; // [rsp+70h] [rbp-9h] BYREF
  __int128 v79; // [rsp+78h] [rbp-1h] BYREF

  v74 = Global;
  v78 = 0;
  v67 = 0;
  v68 = 0;
  v70[0] = 0;
  v79 = 0;
  P = 0;
  v77 = 0;
  v76 = 0;
  v69 = 1;
  if ( (int)VMX_DISK_DEVICE::GetDiskAttributes(this, &v79) < 0 || (BYTE8(v79) & 1) != 0 )
    return;
  *((_BYTE *)this + 54) = 1;
  v72 = 0;
  PhysicalDiskByDevice = VmxpFindPhysicalDiskByDevice(this);
  v3 = PhysicalDiskByDevice;
  if ( PhysicalDiskByDevice )
  {
    v4 = 1;
    DiskByPhysicalDisk = VmxpFindDiskByPhysicalDisk(PhysicalDiskByDevice, (struct VMX_PACK **)&v72);
  }
  else
  {
    DiskByPhysicalDisk = 0;
    v4 = 0;
  }
  if ( _InterlockedExchange((volatile __int32 *)this + 11, 0) )
    VmxpSendRecordedFailureNotification(this);
  if ( (int)VMX_DISK_DEVICE::GetDriveLayoutEx(this, (struct _DRIVE_LAYOUT_INFORMATION_EX **)&P) < 0 )
    goto LABEL_33;
  v6 = (struct _DRIVE_LAYOUT_INFORMATION_EX *)P;
  v7 = 0;
  if ( *(_DWORD *)P )
  {
    if ( *(_DWORD *)P == 1 )
    {
      v9 = 0;
      v10 = *((_DWORD *)P + 1);
      while ( v9 < v10 )
      {
        if ( !memcmp(&v6->PartitionEntry[v9].Mbr, &PARTITION_LDM_DATA_GUID, 0x10u) )
        {
          v7 = 1;
          break;
        }
        ++v9;
      }
    }
  }
  else
  {
    for ( i = 0; i < *((_DWORD *)P + 1); ++i )
    {
      if ( *((_BYTE *)P + 144 * i + 80) == 66 )
      {
        v7 = 1;
        break;
      }
    }
  }
  (*((void (__fastcall **)(_QWORD, struct _BOOTDISK_INFORMATION_LITE **))v74 + 20))(*((_QWORD *)v74 + 1), &v76);
  VmxpCheckCurrentBootSystemCritical(v6, v76, &v67, v70, &v68);
  ExFreePoolWithTag(v6, 0);
  if ( !v7 )
    goto LABEL_33;
  if ( (int)VMX_DISK_DEVICE::IsSupported(this, &v69) < 0 )
    goto LABEL_33;
  v11 = (VMX_GLOBAL_DATA *)VMX_ALLOCATED_OBJECT::operator new(0x80u, 0x102u, 0x64506D56u);
  v12 = v11;
  if ( !v11 )
    goto LABEL_33;
  memset(v11, 0, 0x80u);
  v13 = (UUID *)((char *)v12 + 44);
  *((_BYTE *)v12 + 121) = v67;
  *((_BYTE *)v12 + 122) = v70[0];
  *((_BYTE *)v12 + 123) = v68;
  if ( v3 )
  {
    *v13 = *(UUID *)((char *)v3 + 44);
LABEL_26:
    *((_QWORD *)v12 + 2) = this;
    VMX_PHYSICAL_DISK::ReadMetadata(v12);
    v14 = *((_QWORD *)v12 + 11);
    v15 = *((_QWORD *)v12 + 13);
    v75 = v14;
    if ( !v14 )
      goto LABEL_39;
    if ( v3 && *((_QWORD *)v3 + 11) )
    {
      if ( !*((_BYTE *)v3 + 120) )
        goto LABEL_39;
      goto LABEL_38;
    }
    if ( (int)VMX_DISK_DEVICE::GetSnapshotInfo(this, (struct _DISK_SNAPSHOT_INFO **)&v77) >= 0 )
    {
      v18 = v77;
      if ( *((_DWORD *)v77 + 1) == 2 )
        *((_BYTE *)v12 + 120) = 1;
      ExFreePoolWithTag(v18, 0);
      if ( !VmxpFindPhysicalDiskById((struct _GUID *)(v14 + 40)) )
      {
LABEL_39:
        if ( v4 )
        {
          v19 = *(struct VMX_PHYSICAL_DISK **)v3;
          if ( *(struct VMX_PHYSICAL_DISK **)(*(_QWORD *)v3 + 8LL) != v3 )
            goto LABEL_153;
          v20 = (struct VMX_PHYSICAL_DISK **)*((_QWORD *)v3 + 1);
          if ( *v20 != v3 )
            goto LABEL_153;
          *v20 = v19;
          *((_QWORD *)v19 + 1) = v20;
          v21 = *v20;
          if ( *((struct VMX_PHYSICAL_DISK ***)*v20 + 1) != v20 )
            goto LABEL_153;
          *(_QWORD *)v12 = v21;
          *((_QWORD *)v12 + 1) = v20;
          *((_QWORD *)v21 + 1) = v12;
          *v20 = v12;
        }
        else
        {
          v22 = Global;
          v23 = (char *)Global + 184;
          v24 = (VMX_GLOBAL_DATA **)*((_QWORD *)Global + 24);
          if ( *v24 != (VMX_GLOBAL_DATA *)((char *)Global + 184) )
            goto LABEL_153;
          *((_QWORD *)v12 + 1) = v24;
          *(_QWORD *)v12 = v23;
          *v24 = v12;
          *((_QWORD *)v23 + 1) = v12;
          VMX_NOTIFICATION_QUEUE::AddInvalidDiskNotification(*((_QWORD *)v22 + 36), 1, v12);
        }
        v67 = 0;
        v17 = 0;
        if ( v14 && !*((_BYTE *)v12 + 120) && v69 && *((_BYTE *)Global + 273) )
        {
          if ( v4
            && (!v72
             || memcmp(
                  (const void *)(v14 + 72),
                  (const void *)(*(_QWORD *)(*(_QWORD *)&v72[1].Data1 + 8LL) + 8LL),
                  0x10u)) )
          {
            VmxpOfflinePhysicalDisk(v3);
            v4 = 0;
          }
          v25 = (struct _GUID *)(v14 + 72);
          v69 = 0;
          v72 = (struct _GUID *)(v14 + 72);
          while ( 1 )
          {
            PackById = VmxpFindPackById(v25);
            P = PackById;
            v27 = PackById;
            v68 = 0;
            if ( !v15 || !*(_BYTE *)(v15 + 16) || *(_BYTE *)(v15 + 18) || *(_BYTE *)(v15 + 17) )
              goto LABEL_97;
            if ( PackById )
            {
              v28 = *(_QWORD *)(*((_QWORD *)PackById + 2) + 8LL);
              v29 = (struct VMX_PACK **)(v15 + 32);
              if ( *(_WORD *)(v15 + 20) != 3 )
                v29 = (struct VMX_PACK **)(v15 + 24);
              v5 = *v29;
              v30 = (_QWORD *)(*(_WORD *)(v28 + 72) == 3 ? v28 + 64 : v28 + 56);
              if ( (unsigned __int64)v5 <= *v30 )
                goto LABEL_97;
            }
            v31 = (struct VMX_PACK **)VMX_ALLOCATED_OBJECT::operator new(0x38u, 0x102u, 0x6F436D56u);
            if ( !v31 )
            {
              v31 = 0;
              goto LABEL_96;
            }
            *v31 = 0;
            v31[1] = 0;
            v31[4] = 0;
            v31[5] = 0;
            v31[3] = (struct VMX_PACK *)(v31 + 2);
            v31[2] = (struct VMX_PACK *)(v31 + 2);
            v31[6] = (struct VMX_PACK *)1;
            *(_BYTE *)(v15 + 19) = 0;
            if ( (int)VMX_CONFIG::Read((VMX_CONFIG *)v31, (struct VMX_CONFIG_COPY *)v15) < 0 )
            {
              VMX_CONFIG::`scalar deleting destructor'((VMX_CONFIG *)v31, v32);
              v31 = 0;
              goto LABEL_96;
            }
            v74 = v12;
            if ( (int)VMX_CONFIG::SanityCheck((VMX_CONFIG *)v31, v12) < 0 )
            {
              *(_WORD *)(v15 + 18) = 1;
              VMX_CONFIG::`scalar deleting destructor'((VMX_CONFIG *)v31, (unsigned int)v5);
              v31 = 0;
            }
            if ( !v31 )
              goto LABEL_96;
            if ( v4 )
            {
              VmxpOfflinePhysicalDisk(v3);
              v4 = 0;
              v27 = VmxpFindPackById(v72);
              P = v27;
            }
            if ( !v27 )
            {
              v35 = (struct VMX_PACK *)VMX_ALLOCATED_OBJECT::operator new(0x40u, 0x102u, 0x61506D56u);
              v27 = v35;
              if ( v35 )
              {
                memset(v35, 0, 0x40u);
                *((_QWORD *)v27 + 2) = v31;
                v37 = Global;
                *v31 = v27;
                P = v27;
                v38 = (struct VMX_PACK **)*((_QWORD *)v37 + 26);
                if ( *v38 == (VMX_GLOBAL_DATA *)((char *)v37 + 200) )
                {
                  *((_QWORD *)v27 + 1) = v38;
                  *(_QWORD *)v27 = (char *)v37 + 200;
                  *v38 = v27;
                  *((_QWORD *)v37 + 26) = v27;
                  VMX_NOTIFICATION_QUEUE::AddTaskNotification(
                    *((_QWORD *)v37 + 36),
                    1,
                    *(_QWORD *)(*((_QWORD *)v27 + 2) + 32LL),
                    0);
                  v12 = v74;
                  v68 = 1;
                  goto LABEL_85;
                }
LABEL_153:
                __fastfail(3u);
              }
              VMX_CONFIG::`scalar deleting destructor'((VMX_CONFIG *)v31, v36);
              goto LABEL_143;
            }
            if ( !*((_BYTE *)v27 + 56) )
              goto LABEL_79;
            if ( *((_BYTE *)v27 + 57) || v69 )
              break;
            VmxpRecoverPackConfigOnline(v27, (struct VMX_PACK **)&P);
            v25 = v72;
            v69 = 1;
          }
          VMX_PACK::Offline(v27);
LABEL_79:
          VmxpSendConfigNotifications(*((_QWORD *)v27 + 2), 2);
          v34 = (VMX_CONFIG *)*((_QWORD *)v27 + 2);
          if ( v34 )
            VMX_CONFIG::`scalar deleting destructor'(v34, v33);
          *((_QWORD *)v27 + 2) = v31;
          *v31 = v27;
LABEL_85:
          VmxpSendConfigNotifications(v31, 1);
          v5 = (struct VMX_PACK *)(v31 + 2);
          for ( j = v31[2]; j != v5; j = *(struct VMX_PACK **)j )
          {
            if ( *((_WORD *)j + 16) == 4 )
            {
              v40 = *(_QWORD *)(*((_QWORD *)j + (*((_WORD *)j + 32) & 1) + 5) + 128LL);
              if ( v40 )
              {
                v41 = *(_QWORD *)(v40 + 104);
                if ( v41 )
                {
                  if ( v41 != v15 )
                    *(_BYTE *)(v41 + 19) = 0;
                }
              }
            }
          }
LABEL_96:
          v42 = 0;
          if ( !v31 )
          {
LABEL_97:
            if ( !v27 )
              goto LABEL_143;
            DiskById = VMX_CONFIG::FindDiskById(*((VMX_CONFIG **)v27 + 2), (struct _GUID *)(v75 + 40));
            v42 = DiskById;
            if ( !DiskById )
              goto LABEL_143;
            v44 = 0;
            if ( v4 )
            {
              if ( DiskById == DiskByPhysicalDisk )
              {
                if ( *((_BYTE *)v27 + 56) )
                {
                  v45 = (struct VMX_LOG_COPY *)*((_QWORD *)v3 + 14);
                  v46 = (struct VMX_LOG_COPY *)*((_QWORD *)v12 + 14);
                  VMX_LOG::Acquire(*((VMX_LOG **)v27 + 3));
                  if ( v46 )
                    VMX_LOG::AddLogCopy(*((VMX_LOG **)v27 + 3), v46);
                  if ( v45 )
                    VMX_LOG::RemoveLogCopy(*((VMX_LOG **)v27 + 3), v45);
                  VMX_LOG::Release(*((VMX_LOG **)v27 + 3));
                  v44 = 1;
                }
              }
              else
              {
                VmxpOfflinePhysicalDisk(v3);
              }
              v4 = 0;
            }
            v47 = (char *)v42 + 48;
            if ( (*((_BYTE *)v42 + 64) & 1) == 0 )
              v47 = (char *)v42 + 40;
            *(_QWORD *)(*(_QWORD *)v47 + 128LL) = v12;
            if ( !v44 )
            {
              VMX_NOTIFICATION_QUEUE::AddInvalidDiskNotification(*((_QWORD *)Global + 36), 2, v12);
              VMX_NOTIFICATION_QUEUE::AddTaskNotification(*((_QWORD *)Global + 36), 3, v42, 0);
            }
          }
          if ( v68 )
          {
            v48 = Global;
            DiskByPhysicalDisk = (VMX_CONFIG *)*((_QWORD *)v27 + 2);
            v49 = (char *)Global + 184;
            v50 = (char *)*((_QWORD *)Global + 23);
            while ( v50 != v49 )
            {
              v51 = *((_QWORD *)v50 + 11);
              v75 = v51;
              if ( v51
                && memcmp((const void *)(v51 + 244), &GUID_NULL, 0x10u)
                && !memcmp((const void *)(v75 + 260), (const void *)(*((_QWORD *)DiskByPhysicalDisk + 1) + 8LL), 0x10u) )
              {
                v52 = VmxpFindDiskByPhysicalDisk((struct VMX_PHYSICAL_DISK *)v50, &v78);
                if ( v52 )
                {
                  *(_QWORD *)(*((_QWORD *)v52 + (*((_WORD *)v52 + 32) & 1) + 5) + 128LL) = 0;
                  VMX_NOTIFICATION_QUEUE::AddTaskNotification(*((_QWORD *)v48 + 36), 3, v52, 0);
                  VMX_NOTIFICATION_QUEUE::AddInvalidDiskNotification(*((_QWORD *)Global + 36), 1, v50);
                  v53 = v78;
                  VMX_PACK::UpdateCounters(v78);
                  if ( !*((_DWORD *)v53 + 9) )
                  {
                    v54 = *(VMX_PACK **)v53;
                    if ( *(VMX_PACK **)(*(_QWORD *)v53 + 8LL) != v53 )
                      goto LABEL_153;
                    v55 = (VMX_PACK **)*((_QWORD *)v53 + 1);
                    if ( *v55 != v53 )
                      goto LABEL_153;
                    *v55 = v54;
                    *((_QWORD *)v54 + 1) = v55;
                    VmxpSendPackDepartNotifications(v53);
                    VMX_PACK::`scalar deleting destructor'(v53, v56);
                  }
                }
                v57 = DiskByPhysicalDisk;
                v58 = VMX_RAW_CONFIG::MarkStale(
                        *((VMX_RAW_CONFIG **)DiskByPhysicalDisk + 1),
                        *((struct VMX_CONFIG_COPY **)v50 + 13));
                v59 = (VMX_PHYSICAL_DISK *)v50;
                if ( v58 < 0 )
                  goto LABEL_126;
                if ( (int)VMX_PHYSICAL_DISK::ChangeIdentityPhase2((VMX_PHYSICAL_DISK *)v50) < 0 )
                {
                  v59 = (VMX_PHYSICAL_DISK *)v50;
LABEL_126:
                  VMX_PHYSICAL_DISK::InvalidateMetadata(v59);
                  goto LABEL_131;
                }
                v60 = VMX_CONFIG::FindDiskById(v57, (struct _GUID *)(*((_QWORD *)v50 + 11) + 40LL));
                v61 = v60;
                if ( v60 )
                {
                  *(_QWORD *)(*((_QWORD *)v60 + (*((_WORD *)v60 + 32) & 1) + 5) + 128LL) = v50;
                  VMX_NOTIFICATION_QUEUE::AddInvalidDiskNotification(*((_QWORD *)Global + 36), 2, v50);
                  VMX_NOTIFICATION_QUEUE::AddTaskNotification(*((_QWORD *)Global + 36), 3, v61, 0);
                }
              }
LABEL_131:
              v48 = Global;
              v50 = *(char **)v50;
              v49 = (char *)Global + 184;
            }
          }
          VMX_PACK::UpdateCounters(v27);
          v63 = Global;
          if ( *((_DWORD *)Global + 70) )
          {
            *((_BYTE *)v12 + 124) = 1;
            goto LABEL_143;
          }
          if ( *((_BYTE *)v27 + 56) )
          {
            VMX_PACK::OnlineDisk(v62, v42);
            goto LABEL_143;
          }
          v64 = *(_QWORD *)(*((_QWORD *)v27 + 2) + 8LL);
          if ( !memcmp((const void *)(v64 + 8), (char *)Global + 232, 0x10u) )
          {
            if ( (int)VmxpWritePrimaryPackId((struct _GUID *)((char *)v63 + 232)) < 0 )
              goto LABEL_143;
          }
          else if ( memcmp((const void *)(v64 + 8), (char *)v63 + 216, 0x10u) )
          {
            goto LABEL_143;
          }
          if ( memcmp((char *)Global + 232, &GUID_NULL, 0x10u) )
            VmxpDeletePendingPrimaryPackId();
          VmxpOnlinePack(v27, (struct VMX_PACK **)&P);
LABEL_143:
          v17 = v67;
        }
        goto LABEL_144;
      }
LABEL_38:
      *((_BYTE *)v12 + 120) = 1;
      goto LABEL_39;
    }
    goto LABEL_32;
  }
  if ( ExUuidCreate(v13) >= 0 )
    goto LABEL_26;
LABEL_32:
  VMX_PHYSICAL_DISK::`scalar deleting destructor'(v12, v16);
LABEL_33:
  v17 = v4;
LABEL_144:
  if ( v4 )
    VmxpOfflinePhysicalDisk(v3);
  if ( v17 )
  {
    v65 = *(struct VMX_PHYSICAL_DISK **)v3;
    if ( *(struct VMX_PHYSICAL_DISK **)(*(_QWORD *)v3 + 8LL) != v3 )
      goto LABEL_153;
    v66 = (struct VMX_PHYSICAL_DISK **)*((_QWORD *)v3 + 1);
    if ( *v66 != v3 )
      goto LABEL_153;
    *v66 = v65;
    *((_QWORD *)v65 + 1) = v66;
    VMX_NOTIFICATION_QUEUE::AddInvalidDiskNotification(*((_QWORD *)Global + 36), 2, v3);
  }
  if ( v3 )
    VMX_PHYSICAL_DISK::`scalar deleting destructor'(v3, (unsigned int)v5);
}

```

## disassembly

```asm
0x14002f1e4  push    rbp
0x14002f1e6  push    rbx
0x14002f1e7  push    rsi
0x14002f1e8  push    rdi
0x14002f1e9  push    r12
0x14002f1eb  push    r13
0x14002f1ed  push    r14
0x14002f1ef  push    r15
0x14002f1f1  lea     rbp, [rsp-1Fh]
0x14002f1f6  sub     rsp, 98h
0x14002f1fd  mov     rax, cs:__security_cookie
0x14002f204  xor     rax, rsp
0x14002f207  mov     [rbp+57h+var_48], rax
0x14002f20b  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14002f212  lea     rdx, [rbp+57h+var_58]; PVOID
0x14002f216  xor     r12d, r12d
0x14002f219  mov     [rbp+57h+var_80], rax
0x14002f21d  xorps   xmm0, xmm0
0x14002f220  mov     [rbp+57h+var_60], r12
0x14002f224  mov     [rbp+57h+var_A0], r12b
0x14002f228  mov     rdi, rcx
0x14002f22b  mov     [rbp+57h+var_9F], r12b
0x14002f22f  mov     [rbp+57h+var_9D], r12b
0x14002f233  movups  [rbp+57h+var_58], xmm0
0x14002f237  mov     [rbp+57h+P], r12
0x14002f23b  mov     [rbp+57h+var_68], r12
0x14002f23f  mov     [rbp+57h+var_70], r12
0x14002f243  mov     [rbp+57h+var_9E], 1
0x14002f247  call    ?GetDiskAttributes@VMX_DISK_DEVICE@@QEAAJPEAU_GET_DISK_ATTRIBUTES@@@Z; VMX_DISK_DEVICE::GetDiskAttributes(_GET_DISK_ATTRIBUTES *)
0x14002f24c  test    eax, eax
0x14002f24e  js      loc_14002FBC3
0x14002f254  test    byte ptr [rbp+57h+var_58+8], 1
0x14002f258  jnz     loc_14002FBC3
0x14002f25e  mov     rcx, rdi; struct VMX_DISK_DEVICE *
0x14002f261  mov     byte ptr [rdi+36h], 1
0x14002f265  mov     [rbp+57h+var_90], r12
0x14002f269  call    ?VmxpFindPhysicalDiskByDevice@@YAPEAVVMX_PHYSICAL_DISK@@PEAVVMX_DISK_DEVICE@@@Z; VmxpFindPhysicalDiskByDevice(VMX_DISK_DEVICE *)
0x14002f26e  mov     r14, rax
0x14002f271  test    rax, rax
0x14002f274  jz      short loc_14002F28B
0x14002f276  lea     rdx, [rbp+57h+var_90]; struct VMX_PACK **
0x14002f27a  mov     rcx, rax; struct VMX_PHYSICAL_DISK *
0x14002f27d  mov     r13b, 1
0x14002f280  call    ?VmxpFindDiskByPhysicalDisk@@YAPEAVVMX_RECORD@@PEAVVMX_PHYSICAL_DISK@@PEAPEAVVMX_PACK@@@Z; VmxpFindDiskByPhysicalDisk(VMX_PHYSICAL_DISK *,VMX_PACK * *)
0x14002f285  mov     [rbp+57h+var_88], rax
0x14002f289  jmp     short loc_14002F292
0x14002f28b  mov     [rbp+57h+var_88], r12
0x14002f28f  mov     r13b, r12b
0x14002f292  mov     eax, r12d
0x14002f295  xchg    eax, [rdi+2Ch]
0x14002f298  test    eax, eax
0x14002f29a  jz      short loc_14002F2A4
0x14002f29c  mov     rcx, rdi; struct VMX_DISK_DEVICE *
0x14002f29f  call    ?VmxpSendRecordedFailureNotification@@YAXPEAVVMX_DISK_DEVICE@@@Z; VmxpSendRecordedFailureNotification(VMX_DISK_DEVICE *)
0x14002f2a4  lea     rdx, [rbp+57h+P]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x14002f2a8  mov     rcx, rdi; this
0x14002f2ab  call    ?GetDriveLayoutEx@VMX_DISK_DEVICE@@QEAAJPEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_DISK_DEVICE::GetDriveLayoutEx(_DRIVE_LAYOUT_INFORMATION_EX * *)
0x14002f2b0  test    eax, eax
0x14002f2b2  js      loc_14002F427
0x14002f2b8  mov     rbx, [rbp+57h+P]
0x14002f2bc  mov     r15b, r12b
0x14002f2bf  mov     eax, [rbx]
0x14002f2c1  test    eax, eax
0x14002f2c3  jnz     short loc_14002F2EA
0x14002f2c5  mov     r8d, [rbx+4]
0x14002f2c9  mov     edx, r12d
0x14002f2cc  cmp     edx, r8d
0x14002f2cf  jnb     short loc_14002F32C
0x14002f2d1  mov     eax, edx
0x14002f2d3  lea     rcx, [rax+rax*8]
0x14002f2d7  add     rcx, rcx
0x14002f2da  cmp     byte ptr [rbx+rcx*8+50h], 42h ; 'B'
0x14002f2df  jz      short loc_14002F2E5
0x14002f2e1  inc     edx
0x14002f2e3  jmp     short loc_14002F2CC
0x14002f2e5  mov     r15b, 1
0x14002f2e8  jmp     short loc_14002F32C
0x14002f2ea  cmp     eax, 1
0x14002f2ed  jnz     short loc_14002F32C
0x14002f2ef  mov     esi, r12d
0x14002f2f2  mov     r12d, [rbx+4]
0x14002f2f6  cmp     esi, r12d
0x14002f2f9  jnb     short loc_14002F329
0x14002f2fb  mov     eax, esi
0x14002f2fd  lea     rdx, PARTITION_LDM_DATA_GUID; Buf2
0x14002f304  mov     r8d, 10h; Size
0x14002f30a  lea     rcx, [rax+rax*8]
0x14002f30e  shl     rcx, 4
0x14002f312  add     rcx, 50h ; 'P'
0x14002f316  add     rcx, rbx; Buf1
0x14002f319  call    memcmp
0x14002f31e  test    eax, eax
0x14002f320  jz      short loc_14002F326
0x14002f322  inc     esi
0x14002f324  jmp     short loc_14002F2F6
0x14002f326  mov     r15b, 1
0x14002f329  xor     r12d, r12d
0x14002f32c  mov     rcx, [rbp+57h+var_80]
0x14002f330  lea     rdx, [rbp+57h+var_70]
0x14002f334  mov     rax, [rcx+0A0h]
0x14002f33b  mov     rcx, [rcx+8]
0x14002f33f  call    _guard_dispatch_icall
0x14002f344  mov     rdx, [rbp+57h+var_70]; struct _BOOTDISK_INFORMATION_LITE *
0x14002f348  lea     rax, [rbp+57h+var_9F]
0x14002f34c  lea     r9, [rbp+57h+var_9D]; unsigned __int8 *
0x14002f350  mov     [rsp+0D0h+var_B0], rax; unsigned __int8 *
0x14002f355  lea     r8, [rbp+57h+var_A0]; unsigned __int8 *
0x14002f359  mov     rcx, rbx; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x14002f35c  call    ?VmxpCheckCurrentBootSystemCritical@@YAXPEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAU_BOOTDISK_INFORMATION_LITE@@PEAE22@Z; VmxpCheckCurrentBootSystemCritical(_DRIVE_LAYOUT_INFORMATION_EX *,_BOOTDISK_INFORMATION_LITE *,uchar *,uchar *,uchar *)
0x14002f361  mov     rcx, rbx; P
0x14002f364  xor     edx, edx; Tag
0x14002f366  call    cs:__imp_ExFreePoolWithTag
0x14002f36d  nop     dword ptr [rax+rax+00h]
0x14002f372  test    r15b, r15b
0x14002f375  jz      loc_14002F427
0x14002f37b  lea     rdx, [rbp+57h+var_9E]; unsigned __int8 *
0x14002f37f  mov     rcx, rdi; this
0x14002f382  call    ?IsSupported@VMX_DISK_DEVICE@@QEAAJPEAE@Z; VMX_DISK_DEVICE::IsSupported(uchar *)
0x14002f387  test    eax, eax
0x14002f389  js      loc_14002F427
0x14002f38f  mov     esi, 80h
0x14002f394  mov     edx, 102h; unsigned __int64
0x14002f399  mov     ecx, esi; unsigned __int64
0x14002f39b  mov     r8d, 64506D56h; unsigned int
0x14002f3a1  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x14002f3a6  mov     rbx, rax
0x14002f3a9  test    rax, rax
0x14002f3ac  jz      short loc_14002F427
0x14002f3ae  mov     r8d, esi; Size
0x14002f3b1  xor     edx, edx; Val
0x14002f3b3  mov     rcx, rax; void *
0x14002f3b6  call    memset
0x14002f3bb  mov     al, [rbp+57h+var_A0]
0x14002f3be  lea     rcx, [rbx+2Ch]; Uuid
0x14002f3c2  mov     [rbx+79h], al
0x14002f3c5  mov     al, [rbp+57h+var_9D]
0x14002f3c8  mov     [rbx+7Ah], al
0x14002f3cb  mov     al, [rbp+57h+var_9F]
0x14002f3ce  mov     [rbx+7Bh], al
0x14002f3d1  test    r14, r14
0x14002f3d4  jz      short loc_14002F40F
0x14002f3d6  movups  xmm0, xmmword ptr [r14+2Ch]
0x14002f3db  movdqu  xmmword ptr [rcx], xmm0
0x14002f3df  mov     rcx, rbx; this
0x14002f3e2  mov     [rbx+10h], rdi
0x14002f3e6  call    ?ReadMetadata@VMX_PHYSICAL_DISK@@QEAAXXZ; VMX_PHYSICAL_DISK::ReadMetadata(void)
0x14002f3eb  mov     rsi, [rbx+58h]
0x14002f3ef  mov     r15, [rbx+68h]
0x14002f3f3  mov     [rbp+57h+var_78], rsi
0x14002f3f7  test    rsi, rsi
0x14002f3fa  jz      short loc_14002F46D
0x14002f3fc  test    r14, r14
0x14002f3ff  jz      short loc_14002F42F
0x14002f401  cmp     [r14+58h], r12
0x14002f405  jz      short loc_14002F42F
0x14002f407  cmp     [r14+78h], r12b
0x14002f40b  jnz     short loc_14002F469
0x14002f40d  jmp     short loc_14002F46D
0x14002f40f  call    cs:__imp_ExUuidCreate
0x14002f416  nop     dword ptr [rax+rax+00h]
0x14002f41b  test    eax, eax
0x14002f41d  jns     short loc_14002F3DF
0x14002f41f  mov     rcx, rbx; this
0x14002f422  call    ??_GVMX_PHYSICAL_DISK@@QEAAPEAXI@Z; VMX_PHYSICAL_DISK::`scalar deleting destructor'(uint)
0x14002f427  mov     dil, r13b
0x14002f42a  jmp     loc_14002FB70
0x14002f42f  lea     rdx, [rbp+57h+var_68]; struct _DISK_SNAPSHOT_INFO **
0x14002f433  mov     rcx, rdi; this
0x14002f436  call    ?GetSnapshotInfo@VMX_DISK_DEVICE@@QEAAJPEAPEAU_DISK_SNAPSHOT_INFO@@@Z; VMX_DISK_DEVICE::GetSnapshotInfo(_DISK_SNAPSHOT_INFO * *)
0x14002f43b  test    eax, eax
0x14002f43d  js      short loc_14002F41F
0x14002f43f  mov     rcx, [rbp+57h+var_68]; P
0x14002f443  cmp     dword ptr [rcx+4], 2
0x14002f447  jnz     short loc_14002F44D
0x14002f449  mov     byte ptr [rbx+78h], 1
0x14002f44d  xor     edx, edx; Tag
0x14002f44f  call    cs:__imp_ExFreePoolWithTag
0x14002f456  nop     dword ptr [rax+rax+00h]
0x14002f45b  lea     rcx, [rsi+28h]; struct _GUID *
0x14002f45f  call    ?VmxpFindPhysicalDiskById@@YAPEAVVMX_PHYSICAL_DISK@@PEAU_GUID@@@Z; VmxpFindPhysicalDiskById(_GUID *)
0x14002f464  test    rax, rax
0x14002f467  jz      short loc_14002F46D
0x14002f469  mov     byte ptr [rbx+78h], 1
0x14002f46d  test    r13b, r13b
0x14002f470  jz      short loc_14002F4B0
0x14002f472  mov     rcx, [r14]
0x14002f475  cmp     [rcx+8], r14
0x14002f479  jnz     loc_14002FBE4
0x14002f47f  mov     rax, [r14+8]
0x14002f483  cmp     [rax], r14
0x14002f486  jnz     loc_14002FBE4
0x14002f48c  mov     [rax], rcx
0x14002f48f  mov     [rcx+8], rax
0x14002f493  mov     rcx, [rax]
0x14002f496  cmp     [rcx+8], rax
0x14002f49a  jnz     loc_14002FBE4
0x14002f4a0  mov     [rbx], rcx
0x14002f4a3  mov     [rbx+8], rax
0x14002f4a7  mov     [rcx+8], rbx
0x14002f4ab  mov     [rax], rbx
0x14002f4ae  jmp     short loc_14002F4ED
0x14002f4b0  mov     rcx, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14002f4b7  lea     rax, [rcx+0B8h]
0x14002f4be  mov     rdx, [rax+8]
0x14002f4c2  cmp     [rdx], rax
0x14002f4c5  jnz     loc_14002FBE4
0x14002f4cb  mov     [rbx+8], rdx
0x14002f4cf  mov     r8, rbx
0x14002f4d2  mov     [rbx], rax
0x14002f4d5  mov     [rdx], rbx
0x14002f4d8  mov     edx, 1
0x14002f4dd  mov     [rax+8], rbx
0x14002f4e1  mov     rcx, [rcx+120h]
0x14002f4e8  call    ?AddInvalidDiskNotification@VMX_NOTIFICATION_QUEUE@@QEAAXW4_VM_NOTIFICATION_EVENT@@PEAVVMX_PHYSICAL_DISK@@@Z; VMX_NOTIFICATION_QUEUE::AddInvalidDiskNotification(_VM_NOTIFICATION_EVENT,VMX_PHYSICAL_DISK *)
0x14002f4ed  mov     [rbp+57h+var_A0], r12b
0x14002f4f1  mov     dil, r12b
0x14002f4f4  test    rsi, rsi
0x14002f4f7  jz      loc_14002FB70
0x14002f4fd  cmp     [rbx+78h], r12b
0x14002f501  jnz     loc_14002FB70
0x14002f507  cmp     [rbp+57h+var_9E], r12b
0x14002f50b  jz      loc_14002FB70
0x14002f511  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14002f518  cmp     [rax+111h], r12b
0x14002f51f  jz      loc_14002FB70
0x14002f525  test    r13b, r13b
0x14002f528  jz      short loc_14002F55D
0x14002f52a  mov     rax, [rbp+57h+var_90]
0x14002f52e  test    rax, rax
0x14002f531  jz      short loc_14002F552
0x14002f533  mov     rax, [rax+10h]
0x14002f537  lea     rcx, [rsi+48h]; Buf1
0x14002f53b  mov     r8d, 10h; Size
0x14002f541  mov     rdx, [rax+8]
0x14002f545  add     rdx, 8; Buf2
0x14002f549  call    memcmp
0x14002f54e  test    eax, eax
0x14002f550  jz      short loc_14002F55D
0x14002f552  mov     rcx, r14; this
0x14002f555  call    ?VmxpOfflinePhysicalDisk@@YAXPEAVVMX_PHYSICAL_DISK@@@Z; VmxpOfflinePhysicalDisk(VMX_PHYSICAL_DISK *)
0x14002f55a  mov     r13b, r12b
0x14002f55d  lea     rax, [rsi+48h]
0x14002f561  mov     [rbp+57h+var_9E], r12b
0x14002f565  mov     [rbp+57h+var_90], rax
0x14002f569  mov     rcx, rax; struct _GUID *
0x14002f56c  call    ?VmxpFindPackById@@YAPEAVVMX_PACK@@PEAU_GUID@@@Z; VmxpFindPackById(_GUID *)
0x14002f571  mov     [rbp+57h+P], rax
0x14002f575  mov     rdi, rax
0x14002f578  mov     [rbp+57h+var_9F], r12b
0x14002f57c  test    r15, r15
0x14002f57f  jz      loc_14002F7F6
0x14002f585  cmp     [r15+10h], r12b
0x14002f589  jz      loc_14002F7F6
0x14002f58f  cmp     [r15+12h], r12b
0x14002f593  jnz     loc_14002F7F6
0x14002f599  cmp     [r15+11h], r12b
0x14002f59d  jnz     loc_14002F7F6
0x14002f5a3  test    rax, rax
0x14002f5a6  jz      short loc_14002F5E2
0x14002f5a8  mov     rax, [rax+10h]
0x14002f5ac  mov     r8d, 3
0x14002f5b2  mov     rcx, [rax+8]
0x14002f5b6  lea     rax, [r15+20h]
0x14002f5ba  cmp     [r15+14h], r8w
0x14002f5bf  jz      short loc_14002F5C5
0x14002f5c1  lea     rax, [r15+18h]
0x14002f5c5  mov     rdx, [rax]
0x14002f5c8  cmp     [rcx+48h], r8w
0x14002f5cd  jnz     short loc_14002F5D5
0x14002f5cf  add     rcx, 40h ; '@'
0x14002f5d3  jmp     short loc_14002F5D9
0x14002f5d5  add     rcx, 38h ; '8'
0x14002f5d9  cmp     rdx, [rcx]
0x14002f5dc  jbe     loc_14002F7F6
0x14002f5e2  mov     edx, 102h; unsigned __int64
0x14002f5e7  mov     ecx, 38h ; '8'; unsigned __int64
0x14002f5ec  mov     r8d, 6F436D56h; unsigned int
0x14002f5f2  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x14002f5f7  mov     rsi, rax
0x14002f5fa  test    rax, rax
0x14002f5fd  jz      loc_14002F834
0x14002f603  xor     eax, eax
0x14002f605  lea     rcx, [rsi+10h]
0x14002f609  mov     [rsi], rax
0x14002f60c  mov     rdx, r15; struct VMX_CONFIG_COPY *
0x14002f60f  mov     [rsi+8], rax
0x14002f613  mov     r12, rbx
0x14002f616  mov     [rsi+20h], rax
0x14002f61a  mov     [rsi+28h], rax
0x14002f61e  mov     [rsi+18h], rcx
0x14002f622  mov     [rcx], rcx
0x14002f625  mov     rcx, rsi; this
0x14002f628  mov     qword ptr [rsi+30h], 1
0x14002f630  mov     [r15+13h], al
0x14002f634  call    ?Read@VMX_CONFIG@@QEAAJPEAVVMX_CONFIG_COPY@@@Z; VMX_CONFIG::Read(VMX_CONFIG_COPY *)
0x14002f639  mov     rcx, rsi; this
0x14002f63c  test    eax, eax
0x14002f63e  js      loc_14002F7E0
0x14002f644  mov     rdx, rbx; struct VMX_PHYSICAL_DISK *
0x14002f647  mov     [rbp+57h+var_80], rbx
  ... truncated ...
```
