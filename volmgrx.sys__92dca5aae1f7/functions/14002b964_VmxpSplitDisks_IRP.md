# VmxpSplitDisks(_IRP *)

- ea: `0x14002b964`
- end: `0x14002c3d6`
- name: `?VmxpSplitDisks@@YAJPEAU_IRP@@@Z`
- size: `2674`
- prototype: `__int64 __fastcall(struct _IRP *)`
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14005c9a0`

## callees

- `0x140005f80`
- `0x140008d00`
- `0x140008dc8`
- `0x1400097c0`
- `0x1400099d8`
- `0x14001b9a0`
- `0x14001be80`
- `0x14002a3f4`
- `0x14002acb8`
- `0x14002b0c4`
- `0x14002b964`
- `0x14002d3ec`
- `0x1400314e8`
- `0x14003acbc`
- `0x14003c244`
- `0x14003d81c`
- `0x140041970`
- `0x14004a70c`
- `0x14004bac0`
- `0x14004e3ac`
- `0x14004e950`
- `0x140050bf0`
- `0x14005137c`
- `0x1400531c8`
- `0x140054b2c`
- `0x1400561fc`
- `0x140057448`
- `0x14005757c`
- `0x14005abb4`
- `0x14005d734`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002bcfe`
- `ntoskrnl!ExAllocatePool2` at `0x14002bcfe`
- `ntoskrnl!ExUuidCreate` at `0x14002bbd1`
- `ntoskrnl!ExUuidCreate` at `0x14002bbd1`

## pseudocode

```c
__int64 __fastcall VmxpSplitDisks(struct _IRP *a1)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  struct _GUID *MasterIrp; // r13
  VMX_NOTIFICATION_QUEUE *v3; // rcx
  NTSTATUS v4; // esi
  __int64 v5; // rdx
  unsigned __int64 Options; // rax
  int v7; // eax
  __int64 v8; // r9
  VMX_PACK *v9; // rbp
  struct VMX_RECORD **v10; // r12
  struct VMX_RECORD *v11; // rbx
  char *v12; // r14
  unsigned int v13; // edx
  unsigned int i; // ecx
  unsigned int v15; // edx
  __int64 Data1; // rax
  __int64 Pool2; // rax
  unsigned int v18; // edx
  VMX_NOTIFICATION_QUEUE *v19; // rcx
  __int64 v20; // rdx
  unsigned int v21; // ebx
  unsigned int v22; // edx
  __int64 v23; // r9
  __int64 v24; // rcx
  struct VMX_RECORD *DiskById; // rax
  unsigned int v26; // edx
  __int64 v27; // rdi
  unsigned int v28; // edx
  __int64 v29; // rcx
  __int64 v30; // rdx
  unsigned int v31; // edx
  struct VMX_RECORD **v32; // r12
  struct VMX_RECORD *j; // rsi
  __int64 v34; // rdx
  int v35; // r15d
  __int64 v36; // r12
  VMX_CONFIG **v37; // rax
  unsigned int v38; // edx
  VMX_CONFIG **v39; // r15
  unsigned int v40; // edx
  unsigned int v41; // edx
  VMX_CONFIG *v42; // rax
  VMX_GLOBAL_DATA **v43; // rcx
  VMX_CONFIG *v44; // rax
  __int64 v45; // rcx
  VMX_CONFIG *v46; // rax
  VMX_CONFIG *v47; // rcx
  void **v48; // rax
  unsigned int v49; // edx
  VMX_PACK *v50; // rax
  VMX_PACK **v51; // rcx
  unsigned int v52; // edx
  unsigned int v53; // edx
  int v54; // esi
  unsigned int v56; // edx
  VMX_PACK *v57; // rcx
  VMX_CONFIG *v58; // rax
  void **v59; // rcx
  unsigned int v60; // edx
  char v62; // [rsp+78h] [rbp+10h] BYREF
  VMX_PACK *v63; // [rsp+80h] [rbp+18h] BYREF
  struct _GUID *v64; // [rsp+88h] [rbp+20h]

  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  MasterIrp = (struct _GUID *)a1->AssociatedIrp.MasterIrp;
  v63 = 0;
  VMX_TASK_WRAPPER::VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)&v62, 0);
  if ( !*((_BYTE *)Global + 273) )
  {
    v3 = WPP_GLOBAL_Control;
    v4 = -1070071783;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v5 = 313;
      goto LABEL_149;
    }
    goto LABEL_151;
  }
  Options = CurrentStackLocation->Parameters.Create.Options;
  v4 = -1073741811;
  if ( (unsigned int)Options < 0x64 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v5 = 314;
      goto LABEL_149;
    }
    goto LABEL_151;
  }
  if ( Options < 16 * (unsigned __int64)MasterIrp[5].Data1 + 84 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v5 = 315;
      goto LABEL_149;
    }
    goto LABEL_151;
  }
  if ( CurrentStackLocation->Parameters.Read.Length < 0x10 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v5 = 316;
      goto LABEL_149;
    }
    goto LABEL_151;
  }
  v7 = VmxpValidatePackIdInput(MasterIrp, &v63);
  v4 = v7;
  if ( v7 < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_151;
    }
    v5 = 317;
    v8 = (unsigned int)v7;
    goto LABEL_150;
  }
  if ( !MasterIrp[5].Data1 )
  {
    v3 = WPP_GLOBAL_Control;
    v4 = -1070071718;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v5 = 318;
      goto LABEL_149;
    }
    goto LABEL_151;
  }
  v9 = v63;
  v10 = (struct VMX_RECORD **)*((_QWORD *)v63 + 2);
  v11 = v10[1];
  v12 = (char *)VMX_ALLOCATED_OBJECT::operator new(0xB8u, 0x102u, 0x78546D56u);
  if ( !v12 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v20 = 319;
LABEL_161:
      WPP_SF_d(*((_QWORD *)v19 + 3), v20, WPP_2f8af752156e3401cd435973c831895d_Traceguids, 3221225626LL);
    }
LABEL_162:
    VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)&v62);
    return 3221225626LL;
  }
  *(_OWORD *)v12 = 0;
  *((_OWORD *)v12 + 1) = 0;
  *((_OWORD *)v12 + 2) = 0;
  *((_QWORD *)v12 + 6) = 0;
  *((_WORD *)v12 + 24) = 1;
  *((_DWORD *)v12 + 40) = 0;
  *((_QWORD *)v12 + 21) = 0;
  *((_WORD *)v12 + 88) = 0;
  *((_QWORD *)v12 + 7) = v9;
  *((_OWORD *)v12 + 4) = *(_OWORD *)((char *)v11 + 8);
  RtlStringCbCopyA(v12 + 80, 0x20u, (NTSTRSAFE_PCSTR)v11 + 24);
  v64 = (struct _GUID *)(v12 + 112);
  v4 = ExUuidCreate((UUID *)v12 + 7);
  if ( v4 < 0 )
  {
    VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v12, v13);
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v5 = 320;
      goto LABEL_149;
    }
    goto LABEL_151;
  }
  for ( i = 0; i < 0x20; ++i )
  {
    v13 = *((__int16 *)&MasterIrp[1].Data1 + i);
    if ( (char)*((_WORD *)&MasterIrp[1].Data1 + i) != *((_WORD *)&MasterIrp[1].Data1 + i) )
    {
      VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v12, v13);
      v3 = WPP_GLOBAL_Control;
      v4 = -1070071758;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v5 = 321;
        goto LABEL_149;
      }
      goto LABEL_151;
    }
    v12[i + 128] = v13;
    if ( !(_BYTE)v13 )
      break;
  }
  v4 = VMX_RECORD_INFO::SanityCheckMandatoryName(v12 + 128, v13);
  if ( v4 < 0 )
  {
    VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v12, v15);
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v5 = 322;
      goto LABEL_149;
    }
    goto LABEL_151;
  }
  Data1 = MasterIrp[5].Data1;
  *((_DWORD *)v12 + 40) = Data1;
  Pool2 = ExAllocatePool2(258, 48 * Data1, 538996054);
  *((_QWORD *)v12 + 21) = Pool2;
  if ( !Pool2 )
  {
    VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v12, v18);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v20 = 323;
      goto LABEL_161;
    }
    goto LABEL_162;
  }
  v21 = 0;
LABEL_57:
  if ( v21 >= MasterIrp[5].Data1 )
  {
    if ( !VMX_PACK::IsDiskSetSelfContained(v9, (struct VMX_CHANGE_IDENTITY_TRANSACTION *)v12) )
    {
      VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v12, v31);
      v3 = WPP_GLOBAL_Control;
      v4 = -1070071786;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        goto LABEL_151;
      }
      v5 = 327;
      goto LABEL_149;
    }
    v32 = v10 + 2;
    for ( j = *v32; ; j = *(struct VMX_RECORD **)j )
    {
      if ( j == (struct VMX_RECORD *)v32 )
        goto LABEL_99;
      if ( *((_WORD *)j + 16) == 4 )
      {
        v34 = *((_QWORD *)j + (*((_WORD *)j + 32) & 1LL) + 5);
        if ( (*(_DWORD *)(v34 + 96) & 0x20) == 0 )
        {
          if ( VMX_CHANGE_IDENTITY_TRANSACTION::FindDiskByOldDiskId(
                 (VMX_CHANGE_IDENTITY_TRANSACTION *)v12,
                 (struct _GUID *)(v34 + 72)) )
          {
            if ( *((_DWORD *)v9 + 10) == 1 )
              goto LABEL_99;
            v35 = VMX_PACK::BeginTransaction(v9);
            if ( v35 < 0 )
              goto LABEL_95;
            v35 = VMX_PACK::RemoveVoterTransaction(v9, j);
            if ( v35 < 0 )
            {
              VMX_PACK::AbortTransaction(v9);
LABEL_95:
              if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 3),
                  328,
                  WPP_2f8af752156e3401cd435973c831895d_Traceguids,
                  (unsigned int)v35);
              }
LABEL_99:
              v36 = 64;
              v37 = (VMX_CONFIG **)VMX_ALLOCATED_OBJECT::operator new(0x40u, 0x102u, 0x61506D56u);
              v39 = v37;
              if ( v37 )
              {
                memset(v37, 0, 0x40u);
                v4 = VMX_PACK::CopyPack((VMX_PACK *)v39, v9);
                if ( v4 < 0 )
                {
                  VMX_PACK::`scalar deleting destructor'((VMX_PACK *)v39, v40);
                  VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'(
                    (VMX_CHANGE_IDENTITY_TRANSACTION *)v12,
                    v41);
                  v3 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
                  {
                    goto LABEL_151;
                  }
                  v5 = 330;
                  goto LABEL_149;
                }
                *(struct _GUID *)v39[3] = *v64;
                v42 = (VMX_GLOBAL_DATA *)((char *)Global + 200);
                v43 = (VMX_GLOBAL_DATA **)*((_QWORD *)Global + 26);
                if ( *v43 != (VMX_GLOBAL_DATA *)((char *)Global + 200) )
                  goto LABEL_152;
                *v39 = v42;
                v39[1] = (VMX_CONFIG *)v43;
                *v43 = (VMX_GLOBAL_DATA *)v39;
                *((_QWORD *)v42 + 1) = v39;
                v44 = v39[2];
                v39[6] = (VMX_CONFIG *)v12;
                v45 = *((_QWORD *)v44 + 1);
                if ( *(_WORD *)(v45 + 72) != 3 )
                  v36 = 56;
                *(_QWORD *)v12 = *(_QWORD *)(v36 + v45) + 1LL;
                v46 = v39[6];
                *(_OWORD *)((char *)v46 + 8) = *(_OWORD *)(v45 + 144);
                *(_OWORD *)((char *)v46 + 20) = *(_OWORD *)(v45 + 156);
                v4 = VMX_PACK::SplitDisksTargetTransaction((VMX_PACK *)v39);
                if ( v4 < 0 )
                {
                  VMX_CONFIG::AbortRecords(v39[2]);
                  v39[6] = 0;
                }
                else
                {
                  v4 = VMX_PACK::CommitChangeIdentityTransaction((VMX_PACK *)v39);
                  if ( v4 >= 0 )
                  {
                    if ( *((_BYTE *)v39 + 56) )
                      VMX_PACK::Offline((VMX_PACK *)v39);
                    if ( !*((_DWORD *)v39 + 9) )
                    {
                      v47 = *v39;
                      if ( *((VMX_CONFIG ***)*v39 + 1) == v39 )
                      {
                        v48 = (void **)v39[1];
                        if ( *v48 == v39 )
                        {
                          *v48 = v47;
                          *((_QWORD *)v47 + 1) = v48;
                          VmxpSendPackDepartNotifications((struct VMX_PACK *)v39);
                          VMX_PACK::`scalar deleting destructor'((VMX_PACK *)v39, v49);
                          v39 = 0;
                          goto LABEL_116;
                        }
                      }
LABEL_152:
                      __fastfail(3u);
                    }
LABEL_116:
                    VMX_PACK::SplitDisksSourceCleanup(v9, (struct VMX_CHANGE_IDENTITY_TRANSACTION *)v12);
                    if ( *((_DWORD *)v9 + 9) )
                    {
                      while ( 1 )
                      {
                        v54 = VMX_PACK::BeginTransaction(v9);
                        if ( v54 >= 0 )
                        {
                          v54 = VMX_PACK::SplitDisksSourceTransaction(v9, (struct VMX_CHANGE_IDENTITY_TRANSACTION *)v12);
                          if ( v54 < 0 )
                          {
                            VMX_PACK::AbortTransaction(v9);
                          }
                          else
                          {
                            v54 = VMX_PACK::CommitTransaction(v9, 0, 1u);
                            if ( v54 >= 0 )
                              break;
                          }
                        }
                        if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
                          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
                        {
                          WPP_SF_d(
                            *((_QWORD *)WPP_GLOBAL_Control + 3),
                            332,
                            WPP_2f8af752156e3401cd435973c831895d_Traceguids,
                            (unsigned int)v54);
                        }
                        if ( v54 != -1070071728 && v54 != -1070071804 || (int)VmxpRecoverPackConfigOnline(v9, &v63) < 0 )
                          break;
                        v9 = v63;
                      }
                    }
                    else
                    {
                      v50 = *(VMX_PACK **)v9;
                      if ( *(VMX_PACK **)(*(_QWORD *)v9 + 8LL) != v9 )
                        goto LABEL_152;
                      v51 = (VMX_PACK **)*((_QWORD *)v9 + 1);
                      if ( *v51 != v9 )
                        goto LABEL_152;
                      *v51 = v50;
                      *((_QWORD *)v50 + 1) = v51;
                      VmxpSendPackDepartNotifications(v9);
                      VMX_PACK::`scalar deleting destructor'(v9, v52);
                    }
                    if ( v39 )
                    {
                      *MasterIrp = *v64;
                      a1->IoStatus.Information = 16;
                      VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'(
                        (VMX_CHANGE_IDENTITY_TRANSACTION *)v12,
                        v53);
                      VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)&v62);
                      return 0;
                    }
                    VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'(
                      (VMX_CHANGE_IDENTITY_TRANSACTION *)v12,
                      v53);
                    v3 = WPP_GLOBAL_Control;
                    v4 = -1070071767;
                    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
                    {
                      goto LABEL_151;
                    }
                    v5 = 333;
LABEL_149:
                    v8 = (unsigned int)v4;
LABEL_150:
                    WPP_SF_d(*((_QWORD *)v3 + 3), v5, WPP_2f8af752156e3401cd435973c831895d_Traceguids, v8);
                    goto LABEL_151;
                  }
                }
                VMX_PACK::UpdateCounters(v9);
                if ( *((_BYTE *)v9 + 57) && !VMX_PACK::QuorumInSync(v57) )
                  *((_BYTE *)v9 + 57) = 0;
                v58 = *v39;
                if ( *((VMX_CONFIG ***)*v39 + 1) != v39 )
                  goto LABEL_152;
                v59 = (void **)v39[1];
                if ( *v59 != v39 )
                  goto LABEL_152;
                *v59 = v58;
                *((_QWORD *)v58 + 1) = v59;
                VMX_PACK::`scalar deleting destructor'((VMX_PACK *)v39, v56);
                VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'(
                  (VMX_CHANGE_IDENTITY_TRANSACTION *)v12,
                  v60);
                v3 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
                {
                  goto LABEL_151;
                }
                v5 = 331;
                goto LABEL_149;
              }
              VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v12, v38);
              v19 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
              {
                v20 = 329;
                goto LABEL_161;
              }
              goto LABEL_162;
            }
            v35 = VMX_PACK::CommitTransaction(v9, 0, 1u);
            if ( v35 < 0 )
              goto LABEL_95;
          }
        }
      }
    }
  }
  v22 = 0;
  v23 = v21;
  while ( 1 )
  {
    if ( v22 >= v21 )
    {
      DiskById = VMX_CONFIG::FindDiskById((VMX_CONFIG *)v10, (struct _GUID *)&MasterIrp[v23 + 5].Data2);
      if ( !DiskById )
      {
        VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v12, v26);
        v3 = WPP_GLOBAL_Control;
        v4 = -1070071800;
        if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
        {
          goto LABEL_151;
        }
        v5 = 325;
        goto LABEL_149;
      }
      v27 = *((_QWORD *)DiskById + (*((_WORD *)DiskById + 32) & 1) + 5);
      v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 88LL))(v27);
      if ( v4 < 0 )
      {
        VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v12, v28);
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
        {
          goto LABEL_151;
        }
        v5 = 326;
        goto LABEL_149;
      }
      v29 = *((_QWORD *)v12 + 21);
      v30 = 6LL * v21;
      *(_OWORD *)(v29 + 8 * v30) = *(_OWORD *)(v27 + 72);
      *(_OWORD *)(v29 + 8 * v30 + 16) = *(_OWORD *)(v27 + 72);
      *(_QWORD *)(v29 + 8 * v30 + 32) = *(_QWORD *)(v27 + 128);
      *(_BYTE *)(v29 + 8 * v30 + 40) = 0;
      ++v21;
      goto LABEL_57;
    }
    v24 = *(_QWORD *)&MasterIrp[v22 + 5].Data2 - *(_QWORD *)&MasterIrp[v23 + 5].Data2;
    if ( !v24 )
      v24 = *(_QWORD *)&MasterIrp[v22 + 5].Data4[4] - *(_QWORD *)&MasterIrp[v23 + 5].Data4[4];
    if ( !v24 )
      break;
    ++v22;
  }
  VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v12, v22);
  v3 = WPP_GLOBAL_Control;
  v4 = -1070071802;
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    v5 = 324;
    goto LABEL_149;
  }
LABEL_151:
  VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)&v62);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14002b964  mov     rax, rsp
0x14002b967  mov     [rax+8], rcx
0x14002b96b  push    rbx
0x14002b96c  push    rbp
0x14002b96d  push    rsi
0x14002b96e  push    rdi
0x14002b96f  push    r12
0x14002b971  push    r13
0x14002b973  push    r14
0x14002b975  push    r15
0x14002b977  sub     rsp, 28h
0x14002b97b  mov     rbx, [rcx+0B8h]
0x14002b982  xor     edi, edi
0x14002b984  mov     r13, [rcx+18h]
0x14002b988  xor     edx, edx; unsigned __int8
0x14002b98a  lea     rcx, [rax+10h]; this
0x14002b98e  mov     [rax+18h], rdi
0x14002b992  call    ??0VMX_TASK_WRAPPER@@QEAA@E@Z; VMX_TASK_WRAPPER::VMX_TASK_WRAPPER(uchar)
0x14002b997  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14002b99e  cmp     [rax+111h], dil
0x14002b9a5  jnz     short loc_14002B9E3
0x14002b9a7  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b9ae  lea     rdi, WPP_GLOBAL_Control
0x14002b9b5  mov     esi, 0C0380019h
0x14002b9ba  cmp     rcx, rdi
0x14002b9bd  jz      loc_14002C33D
0x14002b9c3  mov     eax, [rcx+2Ch]
0x14002b9c6  mov     bl, 2
0x14002b9c8  test    bl, al
0x14002b9ca  jz      loc_14002C33D
0x14002b9d0  cmp     [rcx+29h], bl
0x14002b9d3  jb      loc_14002C33D
0x14002b9d9  mov     edx, 139h
0x14002b9de  jmp     loc_14002C32A
0x14002b9e3  mov     eax, [rbx+10h]
0x14002b9e6  mov     esi, 0C000000Dh
0x14002b9eb  cmp     eax, 64h ; 'd'
0x14002b9ee  jnb     short loc_14002BA27
0x14002b9f0  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b9f7  lea     rdi, WPP_GLOBAL_Control
0x14002b9fe  cmp     rcx, rdi
0x14002ba01  jz      loc_14002C33D
0x14002ba07  mov     eax, [rcx+2Ch]
0x14002ba0a  mov     bl, 2
0x14002ba0c  test    bl, al
0x14002ba0e  jz      loc_14002C33D
0x14002ba14  cmp     [rcx+29h], bl
0x14002ba17  jb      loc_14002C33D
0x14002ba1d  mov     edx, 13Ah
0x14002ba22  jmp     loc_14002C32A
0x14002ba27  mov     ecx, [r13+50h]
0x14002ba2b  shl     rcx, 4
0x14002ba2f  add     rcx, 54h ; 'T'
0x14002ba33  cmp     rax, rcx
0x14002ba36  jnb     short loc_14002BA6F
0x14002ba38  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ba3f  lea     rdi, WPP_GLOBAL_Control
0x14002ba46  cmp     rcx, rdi
0x14002ba49  jz      loc_14002C33D
0x14002ba4f  mov     eax, [rcx+2Ch]
0x14002ba52  mov     bl, 2
0x14002ba54  test    bl, al
0x14002ba56  jz      loc_14002C33D
0x14002ba5c  cmp     [rcx+29h], bl
0x14002ba5f  jb      loc_14002C33D
0x14002ba65  mov     edx, 13Bh
0x14002ba6a  jmp     loc_14002C32A
0x14002ba6f  cmp     dword ptr [rbx+8], 10h
0x14002ba73  jnb     short loc_14002BAAC
0x14002ba75  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ba7c  lea     rdi, WPP_GLOBAL_Control
0x14002ba83  cmp     rcx, rdi
0x14002ba86  jz      loc_14002C33D
0x14002ba8c  mov     eax, [rcx+2Ch]
0x14002ba8f  mov     bl, 2
0x14002ba91  test    bl, al
0x14002ba93  jz      loc_14002C33D
0x14002ba99  cmp     [rcx+29h], bl
0x14002ba9c  jb      loc_14002C33D
0x14002baa2  mov     edx, 13Ch
0x14002baa7  jmp     loc_14002C32A
0x14002baac  lea     rdx, [rsp+68h+arg_10]; struct VMX_PACK **
0x14002bab4  mov     rcx, r13; struct _GUID *
0x14002bab7  call    ?VmxpValidatePackIdInput@@YAJPEAU_GUID@@PEAPEAVVMX_PACK@@@Z; VmxpValidatePackIdInput(_GUID *,VMX_PACK * *)
0x14002babc  mov     esi, eax
0x14002babe  test    eax, eax
0x14002bac0  jns     short loc_14002BAFC
0x14002bac2  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bac9  lea     rdi, WPP_GLOBAL_Control
0x14002bad0  cmp     rcx, rdi
0x14002bad3  jz      loc_14002C33D
0x14002bad9  mov     edx, [rcx+2Ch]
0x14002badc  mov     bl, 2
0x14002bade  test    bl, dl
0x14002bae0  jz      loc_14002C33D
0x14002bae6  cmp     [rcx+29h], bl
0x14002bae9  jb      loc_14002C33D
0x14002baef  mov     edx, 13Dh
0x14002baf4  mov     r9d, eax
0x14002baf7  jmp     loc_14002C32D
0x14002bafc  cmp     [r13+50h], edi
0x14002bb00  jnz     short loc_14002BB3E
0x14002bb02  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bb09  lea     rdi, WPP_GLOBAL_Control
0x14002bb10  mov     esi, 0C038005Ah
0x14002bb15  cmp     rcx, rdi
0x14002bb18  jz      loc_14002C33D
0x14002bb1e  mov     eax, [rcx+2Ch]
0x14002bb21  mov     bl, 2
0x14002bb23  test    bl, al
0x14002bb25  jz      loc_14002C33D
0x14002bb2b  cmp     [rcx+29h], bl
0x14002bb2e  jb      loc_14002C33D
0x14002bb34  mov     edx, 13Eh
0x14002bb39  jmp     loc_14002C32A
0x14002bb3e  mov     rbp, [rsp+68h+arg_10]
0x14002bb46  mov     edx, 102h; unsigned __int64
0x14002bb4b  mov     r8d, 78546D56h; unsigned int
0x14002bb51  mov     r12, [rbp+10h]
0x14002bb55  lea     ecx, [rdx-4Ah]; unsigned __int64
0x14002bb58  mov     rbx, [r12+8]
0x14002bb5d  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x14002bb62  mov     r14, rax
0x14002bb65  test    rax, rax
0x14002bb68  jz      loc_14002C379
0x14002bb6e  xor     eax, eax
0x14002bb70  lea     r8, [rbx+18h]; pszSrc
0x14002bb74  xorps   xmm0, xmm0
0x14002bb77  lea     rcx, [r14+50h]; pszDest
0x14002bb7b  movups  xmmword ptr [r14], xmm0
0x14002bb7f  movups  xmmword ptr [r14+10h], xmm0
0x14002bb84  lea     r15d, [rax+1]
0x14002bb88  movups  xmmword ptr [r14+20h], xmm0
0x14002bb8d  mov     [r14+30h], rax
0x14002bb91  lea     edx, [rax+20h]; cbDest
0x14002bb94  mov     [r14+30h], r15w
0x14002bb99  mov     [r14+0A0h], edi
0x14002bba0  mov     [r14+0A8h], rdi
0x14002bba7  mov     [r14+0B0h], di
0x14002bbaf  mov     [r14+38h], rbp
0x14002bbb3  movups  xmm0, xmmword ptr [rbx+8]
0x14002bbb7  movdqu  xmmword ptr [r14+40h], xmm0
0x14002bbbd  call    RtlStringCbCopyA
0x14002bbc2  lea     rax, [r14+70h]
0x14002bbc6  mov     rcx, rax; Uuid
0x14002bbc9  mov     [rsp+68h+arg_18], rax
0x14002bbd1  call    cs:__imp_ExUuidCreate
0x14002bbd8  nop     dword ptr [rax+rax+00h]
0x14002bbdd  mov     esi, eax
0x14002bbdf  test    eax, eax
0x14002bbe1  jns     short loc_14002BC22
0x14002bbe3  mov     rcx, r14; this
0x14002bbe6  call    ??_GVMX_CHANGE_IDENTITY_TRANSACTION@@QEAAPEAXI@Z; VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'(uint)
0x14002bbeb  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bbf2  lea     rdi, WPP_GLOBAL_Control
0x14002bbf9  cmp     rcx, rdi
0x14002bbfc  jz      loc_14002C33D
0x14002bc02  mov     eax, [rcx+2Ch]
0x14002bc05  mov     bl, 2
0x14002bc07  test    bl, al
0x14002bc09  jz      loc_14002C33D
0x14002bc0f  cmp     [rcx+29h], bl
0x14002bc12  jb      loc_14002C33D
0x14002bc18  mov     edx, 140h
0x14002bc1d  jmp     loc_14002C32A
0x14002bc22  mov     ecx, edi
0x14002bc24  cmp     ecx, 20h ; ' '
0x14002bc27  jnb     short loc_14002BC8F
0x14002bc29  mov     r8d, ecx
0x14002bc2c  movsx   edx, word ptr [r13+r8*2+10h]; unsigned int
0x14002bc32  movsx   eax, dl
0x14002bc35  cmp     ax, dx
0x14002bc38  jnz     short loc_14002BC4B
0x14002bc3a  mov     [r14+r8+80h], dl
0x14002bc42  test    dl, dl
0x14002bc44  jz      short loc_14002BC8F
0x14002bc46  add     ecx, r15d
0x14002bc49  jmp     short loc_14002BC24
0x14002bc4b  mov     rcx, r14; this
0x14002bc4e  call    ??_GVMX_CHANGE_IDENTITY_TRANSACTION@@QEAAPEAXI@Z; VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'(uint)
0x14002bc53  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bc5a  lea     rdi, WPP_GLOBAL_Control
0x14002bc61  mov     esi, 0C0380032h
0x14002bc66  cmp     rcx, rdi
0x14002bc69  jz      loc_14002C33D
0x14002bc6f  mov     eax, [rcx+2Ch]
0x14002bc72  mov     bl, 2
0x14002bc74  test    bl, al
0x14002bc76  jz      loc_14002C33D
0x14002bc7c  cmp     [rcx+29h], bl
0x14002bc7f  jb      loc_14002C33D
0x14002bc85  mov     edx, 141h
0x14002bc8a  jmp     loc_14002C32A
0x14002bc8f  lea     rcx, [r14+80h]; char *
0x14002bc96  call    ?SanityCheckMandatoryName@VMX_RECORD_INFO@@SAJPEADK@Z; VMX_RECORD_INFO::SanityCheckMandatoryName(char *,ulong)
0x14002bc9b  mov     esi, eax
0x14002bc9d  test    eax, eax
0x14002bc9f  jns     short loc_14002BCE0
0x14002bca1  mov     rcx, r14; this
0x14002bca4  call    ??_GVMX_CHANGE_IDENTITY_TRANSACTION@@QEAAPEAXI@Z; VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'(uint)
0x14002bca9  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bcb0  lea     rdi, WPP_GLOBAL_Control
0x14002bcb7  cmp     rcx, rdi
0x14002bcba  jz      loc_14002C33D
0x14002bcc0  mov     eax, [rcx+2Ch]
0x14002bcc3  mov     bl, 2
0x14002bcc5  test    bl, al
0x14002bcc7  jz      loc_14002C33D
0x14002bccd  cmp     [rcx+29h], bl
0x14002bcd0  jb      loc_14002C33D
0x14002bcd6  mov     edx, 142h
0x14002bcdb  jmp     loc_14002C32A
0x14002bce0  mov     eax, [r13+50h]
0x14002bce4  mov     ecx, 102h
0x14002bce9  mov     r8d, 20206D56h
0x14002bcef  mov     [r14+0A0h], eax
0x14002bcf6  lea     rdx, [rax+rax*2]
0x14002bcfa  shl     rdx, 4
0x14002bcfe  call    cs:__imp_ExAllocatePool2
0x14002bd05  nop     dword ptr [rax+rax+00h]
0x14002bd0a  mov     [r14+0A8h], rax
0x14002bd11  test    rax, rax
0x14002bd14  jnz     short loc_14002BD55
0x14002bd16  mov     rcx, r14; this
0x14002bd19  call    ??_GVMX_CHANGE_IDENTITY_TRANSACTION@@QEAAPEAXI@Z; VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'(uint)
0x14002bd1e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bd25  lea     rdi, WPP_GLOBAL_Control
0x14002bd2c  cmp     rcx, rdi
0x14002bd2f  jz      loc_14002C3B5
0x14002bd35  mov     eax, [rcx+2Ch]
0x14002bd38  mov     bl, 2
0x14002bd3a  test    bl, al
0x14002bd3c  jz      loc_14002C3B5
0x14002bd42  cmp     [rcx+29h], bl
0x14002bd45  jb      loc_14002C3B5
0x14002bd4b  mov     edx, 143h
0x14002bd50  jmp     loc_14002C39F
0x14002bd55  mov     ebx, edi
0x14002bd57  cmp     ebx, [r13+50h]
0x14002bd5b  jnb     loc_14002BEDE
0x14002bd61  mov     r9d, ebx
0x14002bd64  mov     edx, edi; unsigned int
0x14002bd66  shl     r9, 4
0x14002bd6a  mov     r15d, ebx
0x14002bd6d  cmp     edx, ebx
0x14002bd6f  jnb     short loc_14002BD9A
0x14002bd71  mov     r8d, edx
0x14002bd74  add     r8, r8
0x14002bd77  mov     rcx, [r13+r8*8+54h]
0x14002bd7c  sub     rcx, [r9+r13+54h]
0x14002bd81  jnz     short loc_14002BD8D
0x14002bd83  mov     rcx, [r13+r8*8+5Ch]
0x14002bd88  sub     rcx, [r9+r13+5Ch]
0x14002bd8d  test    rcx, rcx
0x14002bd90  jz      loc_14002BE17
0x14002bd96  inc     edx
0x14002bd98  jmp     short loc_14002BD6D
0x14002bd9a  lea     rdx, [r13+54h]
0x14002bd9e  mov     rcx, r12; this
0x14002bda1  add     rdx, r9; struct _GUID *
0x14002bda4  call    ?FindDiskById@VMX_CONFIG@@QEAAPEAVVMX_RECORD@@PEAU_GUID@@@Z; VMX_CONFIG::FindDiskById(_GUID *)
0x14002bda9  test    rax, rax
0x14002bdac  jz      loc_14002BE9A
0x14002bdb2  movzx   ecx, word ptr [rax+40h]
0x14002bdb6  and     ecx, 1
0x14002bdb9  mov     rdi, [rax+rcx*8+28h]
0x14002bdbe  mov     rcx, rdi
0x14002bdc1  mov     rax, [rdi]
0x14002bdc4  mov     rax, [rax+58h]
0x14002bdc8  call    _guard_dispatch_icall
0x14002bdcd  mov     esi, eax
0x14002bdcf  test    eax, eax
0x14002bdd1  js      loc_14002BE5B
0x14002bdd7  movups  xmm0, xmmword ptr [rdi+48h]
0x14002bddb  mov     rcx, [r14+0A8h]
0x14002bde2  lea     rdx, [r15+r15*2]
0x14002bde6  add     rdx, rdx
0x14002bde9  movdqu  xmmword ptr [rcx+rdx*8], xmm0
0x14002bdee  movups  xmm1, xmmword ptr [rdi+48h]
0x14002bdf2  movdqu  xmmword ptr [rcx+rdx*8+10h], xmm1
0x14002bdf8  mov     rax, [rdi+80h]
0x14002bdff  xor     edi, edi
0x14002be01  mov     [rcx+rdx*8+20h], rax
0x14002be06  mov     [rcx+rdx*8+28h], dil
0x14002be0b  lea     r15d, [rdi+1]
0x14002be0f  add     ebx, r15d
0x14002be12  jmp     loc_14002BD57
0x14002be17  mov     rcx, r14; this
0x14002be1a  call    ??_GVMX_CHANGE_IDENTITY_TRANSACTION@@QEAAPEAXI@Z; VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'(uint)
0x14002be1f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002be26  lea     rdi, WPP_GLOBAL_Control
0x14002be2d  mov     esi, 0C0380006h
0x14002be32  cmp     rcx, rdi
0x14002be35  jz      loc_14002C33D
0x14002be3b  mov     eax, [rcx+2Ch]
0x14002be3e  mov     bl, 2
0x14002be40  test    bl, al
0x14002be42  jz      loc_14002C33D
0x14002be48  cmp     [rcx+29h], bl
0x14002be4b  jb      loc_14002C33D
  ... truncated ...
```
