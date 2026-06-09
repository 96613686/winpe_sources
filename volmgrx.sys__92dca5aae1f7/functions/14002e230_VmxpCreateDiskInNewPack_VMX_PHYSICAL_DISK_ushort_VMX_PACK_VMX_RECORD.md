# VmxpCreateDiskInNewPack(VMX_PHYSICAL_DISK *,ushort *,VMX_PACK * *,VMX_RECORD * *)

- ea: `0x14002e230`
- end: `0x14002eaad`
- name: `?VmxpCreateDiskInNewPack@@YAJPEAVVMX_PHYSICAL_DISK@@PEAGPEAPEAVVMX_PACK@@PEAPEAVVMX_RECORD@@@Z`
- size: `2173`
- prototype: `__int64 __fastcall(struct VMX_PHYSICAL_DISK *, unsigned __int16 *, struct VMX_PACK **, struct VMX_RECORD **)`
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140030a04`

## callees

- `0x140005f80`
- `0x140008dc8`
- `0x140008eec`
- `0x140009670`
- `0x140009718`
- `0x1400099d8`
- `0x14001b960`
- `0x14001b9a0`
- `0x14001be80`
- `0x14002a3f4`
- `0x14002b0c4`
- `0x14002d3ec`
- `0x14002d44c`
- `0x14002e230`
- `0x14002eab4`
- `0x14002eaf4`
- `0x14002fbf4`
- `0x1400316d4`
- `0x140033278`
- `0x140044ac4`
- `0x140045798`
- `0x14004a70c`
- `0x14004a73c`
- `0x14004a88c`
- `0x14004ae60`
- `0x14004bac0`
- `0x1400532d4`
- `0x1400537c4`
- `0x140055f34`
- `0x14005d40c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002e47e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e536`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e5f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e807`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e8ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e902`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e9c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e47e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e536`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e5f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e807`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e8ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e902`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e9c4`

## pseudocode

```c
__int64 __fastcall VmxpCreateDiskInNewPack(
        struct VMX_PHYSICAL_DISK *a1,
        unsigned __int16 *a2,
        struct VMX_PACK **a3,
        struct VMX_RECORD **a4)
{
  VMX_GLOBAL_DATA *v4; // rsi
  unsigned int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r15
  VMX_PACK *v12; // rax
  VMX_PACK *v13; // rbx
  unsigned int v14; // edx
  int v15; // r14d
  __int64 v16; // rcx
  __int64 v17; // rdx
  VMX_GLOBAL_DATA *v19; // rcx
  char *v20; // rax
  VMX_GLOBAL_DATA **v21; // r8
  _QWORD *v22; // rcx
  void **v23; // rdx
  unsigned int v24; // edx
  VMX_NOTIFICATION_QUEUE *v25; // rcx
  _QWORD *v26; // rcx
  void **v27; // rax
  unsigned int v28; // edx
  _QWORD *v29; // rcx
  void **v30; // rax
  unsigned int v31; // edx
  _QWORD *v32; // rcx
  void **v33; // rax
  unsigned int v34; // edx
  int v35; // r15d
  struct VMX_RECORD *v36; // r14
  int v37; // eax
  struct _DRIVE_LAYOUT_INFORMATION_EX *v38; // r12
  __int64 v39; // rax
  VMX_GLOBAL_DATA *v40; // rcx
  VMX_PACK *v41; // rcx
  _QWORD *v42; // rcx
  void **v43; // rax
  unsigned int v44; // edx
  VMX_NOTIFICATION_QUEUE *v45; // rcx
  __int64 v46; // rdx
  struct VMX_RECORD **v47; // rax
  _QWORD *v48; // rcx
  void **v49; // rax
  unsigned int v50; // edx
  _QWORD *v51; // rcx
  void **v52; // rax
  unsigned int v53; // edx
  PVOID P; // [rsp+30h] [rbp-48h] BYREF
  struct VMX_RECORD *v55; // [rsp+38h] [rbp-40h] BYREF
  struct VMX_RECORD **v56; // [rsp+40h] [rbp-38h]
  struct _DISK_GEOMETRY v57; // [rsp+48h] [rbp-30h] BYREF

  v4 = Global;
  *a3 = 0;
  v56 = a4;
  *(_QWORD *)&v57.SectorsPerTrack = 0;
  v55 = 0;
  P = 0;
  *a4 = 0;
  *(_OWORD *)&v57.Cylinders.LowPart = 0;
  if ( VmxpFindPackById((struct _GUID *)((char *)v4 + 216)) )
  {
    v8 = -1070071726;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return v8;
    }
    v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v10 = 107;
LABEL_94:
    WPP_SF_d(v9, v10, WPP_2f8af752156e3401cd435973c831895d_Traceguids, v8);
    return v8;
  }
  v11 = *((_QWORD *)a1 + 2);
  v12 = (VMX_PACK *)VMX_ALLOCATED_OBJECT::operator new(64, 258, 1632660822);
  v13 = v12;
  if ( !v12 )
  {
    v8 = -1073741670;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return v8;
    }
    v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v10 = 108;
    goto LABEL_94;
  }
  memset(v12, 0, 0x40u);
  v15 = VMX_PACK::NewPack(v13, a2);
  if ( v15 < 0 )
  {
    VMX_PACK::`scalar deleting destructor'(v13, v14);
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return (unsigned int)v15;
    }
    v16 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v17 = 109;
LABEL_12:
    WPP_SF_d(v16, v17, WPP_2f8af752156e3401cd435973c831895d_Traceguids, (unsigned int)v15);
    return (unsigned int)v15;
  }
  v19 = Global;
  v20 = (char *)Global + 200;
  v21 = (VMX_GLOBAL_DATA **)*((_QWORD *)Global + 26);
  if ( *v21 != (VMX_GLOBAL_DATA *)((char *)Global + 200) )
    goto LABEL_89;
  *(_QWORD *)v13 = v20;
  *((_QWORD *)v13 + 1) = v21;
  *v21 = v13;
  *((_QWORD *)v20 + 1) = v13;
  VMX_NOTIFICATION_QUEUE::AddTaskNotification(*((_QWORD *)v19 + 36), 1, *(_QWORD *)(*((_QWORD *)v13 + 2) + 32LL), 0);
  (*((void (__fastcall **)(_QWORD, _QWORD))v4 + 18))(*((_QWORD *)v4 + 1), *(_QWORD *)(v11 + 16));
  v15 = VMX_PHYSICAL_DISK::CreatePrivateRegion(a1, v13, &v57, (struct _DRIVE_LAYOUT_INFORMATION_EX **)&P);
  if ( v15 < 0 )
  {
    v22 = *(_QWORD **)v13;
    if ( *(VMX_PACK **)(*(_QWORD *)v13 + 8LL) == v13 )
    {
      v23 = (void **)*((_QWORD *)v13 + 1);
      if ( *v23 == v13 )
      {
        *v23 = v22;
        v22[1] = v23;
        VmxpSendPackDepartNotifications(v13);
        VMX_PACK::`scalar deleting destructor'(v13, v24);
        (*((void (__fastcall **)(_QWORD, _QWORD))v4 + 18))(*((_QWORD *)v4 + 1), 0);
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
        {
          return (unsigned int)v15;
        }
        v17 = 110;
        goto LABEL_22;
      }
    }
LABEL_89:
    __fastfail(3u);
  }
  v15 = VMX_PACK::OnlineConfigCopy((VMX_CONFIG **)v13, a1);
  if ( v15 < 0 )
  {
    VMX_PHYSICAL_DISK::DeletePrivateRegion(a1, (struct _DRIVE_LAYOUT_INFORMATION_EX *)P);
    ExFreePoolWithTag(P, 0);
    v26 = *(_QWORD **)v13;
    if ( *(VMX_PACK **)(*(_QWORD *)v13 + 8LL) != v13 )
      goto LABEL_89;
    v27 = (void **)*((_QWORD *)v13 + 1);
    if ( *v27 != v13 )
      goto LABEL_89;
    *v27 = v26;
    v26[1] = v27;
    VmxpSendPackDepartNotifications(v13);
    VMX_PACK::`scalar deleting destructor'(v13, v28);
    (*((void (__fastcall **)(_QWORD, _QWORD))v4 + 18))(*((_QWORD *)v4 + 1), 0);
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return (unsigned int)v15;
    }
    v17 = 111;
    goto LABEL_22;
  }
  v15 = VMX_PACK::OnlineLogCopy((VMX_LOG **)v13, a1);
  if ( v15 < 0 )
  {
    VMX_PACK::OfflineLogCopy(v13, a1);
    VMX_PHYSICAL_DISK::DeletePrivateRegion(a1, (struct _DRIVE_LAYOUT_INFORMATION_EX *)P);
    ExFreePoolWithTag(P, 0);
    v29 = *(_QWORD **)v13;
    if ( *(VMX_PACK **)(*(_QWORD *)v13 + 8LL) != v13 )
      goto LABEL_89;
    v30 = (void **)*((_QWORD *)v13 + 1);
    if ( *v30 != v13 )
      goto LABEL_89;
    *v30 = v29;
    v29[1] = v30;
    VmxpSendPackDepartNotifications(v13);
    VMX_PACK::`scalar deleting destructor'(v13, v31);
    (*((void (__fastcall **)(_QWORD, _QWORD))v4 + 18))(*((_QWORD *)v4 + 1), 0);
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return (unsigned int)v15;
    }
    v17 = 112;
LABEL_22:
    v16 = *((_QWORD *)v25 + 3);
    goto LABEL_12;
  }
  v15 = VmxpWritePendingPrimaryPackId((struct _GUID *)(*(_QWORD *)(*((_QWORD *)v13 + 2) + 8LL) + 8LL));
  if ( v15 < 0 )
  {
    VMX_PACK::OfflineLogCopy(v13, a1);
    VMX_PHYSICAL_DISK::DeletePrivateRegion(a1, (struct _DRIVE_LAYOUT_INFORMATION_EX *)P);
    ExFreePoolWithTag(P, 0);
    v32 = *(_QWORD **)v13;
    if ( *(VMX_PACK **)(*(_QWORD *)v13 + 8LL) == v13 )
    {
      v33 = (void **)*((_QWORD *)v13 + 1);
      if ( *v33 == v13 )
      {
        *v33 = v32;
        v32[1] = v33;
        VmxpSendPackDepartNotifications(v13);
        VMX_PACK::`scalar deleting destructor'(v13, v34);
        if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            113,
            WPP_2f8af752156e3401cd435973c831895d_Traceguids,
            (unsigned int)v15);
        }
        (*((void (__fastcall **)(_QWORD, _QWORD))v4 + 18))(*((_QWORD *)v4 + 1), 0);
        return (unsigned int)v15;
      }
    }
    goto LABEL_89;
  }
  v35 = VMX_PACK::BeginTransaction(v13);
  if ( v35 < 0 )
    goto LABEL_81;
  v35 = VMX_PACK::AddDiskTransaction(v13, a1, &v55);
  if ( v35 < 0 || (v36 = v55, v35 = VMX_PACK::AddVoterTransaction((struct VMX_TRANSACTION **)v13, v55), v35 < 0) )
  {
    VMX_PACK::AbortTransaction(v13);
LABEL_81:
    VmxpDeletePendingPrimaryPackId();
    VMX_PACK::OfflineLogCopy(v13, a1);
    VMX_PHYSICAL_DISK::DeletePrivateRegion(a1, (struct _DRIVE_LAYOUT_INFORMATION_EX *)P);
    ExFreePoolWithTag(P, 0);
    v51 = *(_QWORD **)v13;
    if ( *(VMX_PACK **)(*(_QWORD *)v13 + 8LL) != v13 )
      goto LABEL_89;
    v52 = (void **)*((_QWORD *)v13 + 1);
    if ( *v52 != v13 )
      goto LABEL_89;
    *v52 = v51;
    v51[1] = v52;
    VmxpSendPackDepartNotifications(v13);
    VMX_PACK::`scalar deleting destructor'(v13, v53);
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        114,
        WPP_2f8af752156e3401cd435973c831895d_Traceguids,
        (unsigned int)v35);
    }
    (*((void (__fastcall **)(_QWORD, _QWORD))v4 + 18))(*((_QWORD *)v4 + 1), 0);
    return (unsigned int)v35;
  }
  v35 = VMX_PACK::CommitTransaction((struct VMX_CONFIG **)v13, 0, 1);
  if ( v35 < 0 )
    goto LABEL_81;
  v37 = VMX_PACK::BeginTransaction(v13);
  v38 = (struct _DRIVE_LAYOUT_INFORMATION_EX *)P;
  v35 = v37;
  if ( v37 < 0 )
    goto LABEL_73;
  v35 = VMX_PACK::AddVolumesTransaction(v13, a1, &v57, (struct _DRIVE_LAYOUT_INFORMATION_EX *)P, v36);
  if ( v35 < 0 )
  {
    VMX_PACK::AbortTransaction(v13);
    goto LABEL_73;
  }
  v35 = VMX_PACK::CommitTransaction((struct VMX_CONFIG **)v13, 0, 1);
  if ( v35 < 0 )
  {
LABEL_73:
    VmxpDeletePendingPrimaryPackId();
    VMX_PACK::OfflineLogCopy(v13, a1);
    VMX_PHYSICAL_DISK::DeletePrivateRegion(a1, v38);
    ExFreePoolWithTag(v38, 0);
    v48 = *(_QWORD **)v13;
    if ( *(VMX_PACK **)(*(_QWORD *)v13 + 8LL) != v13 )
      goto LABEL_89;
    v49 = (void **)*((_QWORD *)v13 + 1);
    if ( *v49 != v13 )
      goto LABEL_89;
    *v49 = v48;
    v48[1] = v49;
    VmxpSendPackDepartNotifications(v13);
    VMX_PACK::`scalar deleting destructor'(v13, v50);
    (*((void (__fastcall **)(_QWORD, _QWORD))v4 + 18))(*((_QWORD *)v4 + 1), 0);
    v45 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v46 = 115;
      goto LABEL_79;
    }
    return (unsigned int)v35;
  }
  v35 = VMX_PHYSICAL_DISK::CreateDynamicPartitions(a1, v36, &v57, v38);
  if ( v35 < 0 )
  {
    VmxpDeletePendingPrimaryPackId();
    VMX_PACK::OfflineLogCopy(v13, a1);
    if ( (int)VMX_PACK::BeginTransaction(v13) >= 0 )
    {
      if ( VMX_PACK::RemoveVolumesTransaction(v13, v36) < 0 )
      {
        VMX_PACK::AbortTransaction(v13);
      }
      else if ( (int)VMX_PACK::CommitTransaction((struct VMX_CONFIG **)v13, 1, 0) >= 0 )
      {
        VMX_PHYSICAL_DISK::DeletePrivateRegion(a1, v38);
        goto LABEL_63;
      }
    }
    if ( (*((_BYTE *)v36 + 64) & 1) != 0 )
      v39 = *((_QWORD *)v36 + 6);
    else
      v39 = *((_QWORD *)v36 + 5);
    v40 = Global;
    *(_QWORD *)(v39 + 128) = 0;
    VMX_NOTIFICATION_QUEUE::AddTaskNotification(*((_QWORD *)v40 + 36), 3, (__int64)v36, 0);
    VMX_NOTIFICATION_QUEUE::AddInvalidDiskNotification(*((_QWORD *)Global + 36), 1, a1);
    VMX_PACK::UpdateCounters(v13);
    if ( *((_BYTE *)v13 + 56) )
      VMX_PACK::OfflineDiskVolumes(v41, v36);
LABEL_63:
    ExFreePoolWithTag(v38, 0);
    v42 = *(_QWORD **)v13;
    if ( *(VMX_PACK **)(*(_QWORD *)v13 + 8LL) != v13 )
      goto LABEL_89;
    v43 = (void **)*((_QWORD *)v13 + 1);
    if ( *v43 != v13 )
      goto LABEL_89;
    *v43 = v42;
    v42[1] = v43;
    VmxpSendPackDepartNotifications(v13);
    VMX_PACK::`scalar deleting destructor'(v13, v44);
    (*((void (__fastcall **)(_QWORD, _QWORD))v4 + 18))(*((_QWORD *)v4 + 1), 0);
    v45 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v46 = 116;
LABEL_79:
      WPP_SF_d(*((_QWORD *)v45 + 3), v46, WPP_2f8af752156e3401cd435973c831895d_Traceguids, (unsigned int)v35);
      return (unsigned int)v35;
    }
    return (unsigned int)v35;
  }
  if ( VmxpWritePrimaryPackId((struct _GUID *)((char *)Global + 232)) >= 0 )
    VmxpDeletePendingPrimaryPackId();
  ExFreePoolWithTag(v38, 0);
  (*((void (__fastcall **)(_QWORD, _QWORD))v4 + 18))(*((_QWORD *)v4 + 1), 0);
  v47 = v56;
  *a3 = v13;
  *v47 = v36;
  return 0;
}

```

## disassembly

```asm
0x14002e230  push    rbp
0x14002e232  push    rbx
0x14002e233  push    rsi
0x14002e234  push    rdi
0x14002e235  push    r12
0x14002e237  push    r13
0x14002e239  push    r14
0x14002e23b  push    r15
0x14002e23d  mov     rbp, rsp
0x14002e240  sub     rsp, 78h
0x14002e244  mov     rax, cs:__security_cookie
0x14002e24b  xor     rax, rsp
0x14002e24e  mov     [rbp+var_18], rax
0x14002e252  mov     rsi, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14002e259  xor     r12d, r12d
0x14002e25c  mov     rdi, rcx
0x14002e25f  mov     [r8], r12
0x14002e262  xor     ecx, ecx
0x14002e264  mov     [rbp+var_38], r9
0x14002e268  mov     qword ptr [rbp+var_30.SectorsPerTrack], rcx
0x14002e26c  xorps   xmm0, xmm0
0x14002e26f  lea     rcx, [rsi+0D8h]; struct _GUID *
0x14002e276  mov     [rbp+var_40], r12
0x14002e27a  mov     r13, r8
0x14002e27d  mov     [rbp+P], r12
0x14002e281  mov     r14, rdx
0x14002e284  mov     [r9], r12
0x14002e287  movups  xmmword ptr [rbp+var_30.Cylinders], xmm0
0x14002e28b  call    ?VmxpFindPackById@@YAPEAVVMX_PACK@@PEAU_GUID@@@Z; VmxpFindPackById(_GUID *)
0x14002e290  test    rax, rax
0x14002e293  jz      short loc_14002E2D7
0x14002e295  mov     r10, cs:WPP_GLOBAL_Control
0x14002e29c  lea     rax, WPP_GLOBAL_Control
0x14002e2a3  mov     ebx, 0C0380052h
0x14002e2a8  cmp     r10, rax
0x14002e2ab  jz      loc_14002EA8D
0x14002e2b1  mov     ecx, [r10+2Ch]
0x14002e2b5  test    cl, 2
0x14002e2b8  jz      loc_14002EA8D
0x14002e2be  cmp     byte ptr [r10+29h], 2
0x14002e2c3  jb      loc_14002EA8D
0x14002e2c9  mov     rcx, [r10+18h]
0x14002e2cd  lea     edx, [r12+6Bh]
0x14002e2d2  jmp     loc_14002EA7E
0x14002e2d7  mov     r15, [rdi+10h]
0x14002e2db  mov     edx, 102h; unsigned __int64
0x14002e2e0  mov     ecx, 40h ; '@'; unsigned __int64
0x14002e2e5  mov     r8d, 61506D56h; unsigned int
0x14002e2eb  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x14002e2f0  mov     rbx, rax
0x14002e2f3  test    rax, rax
0x14002e2f6  jz      loc_14002EA4F
0x14002e2fc  xor     edx, edx; Val
0x14002e2fe  mov     rcx, rax; void *
0x14002e301  lea     r8d, [rdx+40h]; Size
0x14002e305  call    memset
0x14002e30a  mov     rdx, r14; unsigned __int16 *
0x14002e30d  mov     rcx, rbx; this
0x14002e310  call    ?NewPack@VMX_PACK@@QEAAJPEAG@Z; VMX_PACK::NewPack(ushort *)
0x14002e315  mov     r14d, eax
0x14002e318  test    eax, eax
0x14002e31a  jns     short loc_14002E367
0x14002e31c  mov     rcx, rbx; this
0x14002e31f  call    ??_GVMX_PACK@@QEAAPEAXI@Z; VMX_PACK::`scalar deleting destructor'(uint)
0x14002e324  mov     r10, cs:WPP_GLOBAL_Control
0x14002e32b  lea     rax, WPP_GLOBAL_Control
0x14002e332  cmp     r10, rax
0x14002e335  jz      short loc_14002E35F
0x14002e337  mov     ecx, [r10+2Ch]
0x14002e33b  test    cl, 2
0x14002e33e  jz      short loc_14002E35F
0x14002e340  cmp     byte ptr [r10+29h], 2
0x14002e345  jb      short loc_14002E35F
0x14002e347  mov     rcx, [r10+18h]
0x14002e34b  mov     edx, 6Dh ; 'm'
0x14002e350  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x14002e357  mov     r9d, r14d
0x14002e35a  call    WPP_SF_d
0x14002e35f  mov     eax, r14d
0x14002e362  jmp     loc_14002EA8F
0x14002e367  mov     rcx, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14002e36e  lea     rax, [rcx+0C8h]
0x14002e375  mov     r8, [rax+8]
0x14002e379  cmp     [r8], rax
0x14002e37c  jnz     loc_14002EA48
0x14002e382  mov     [rbx], rax
0x14002e385  xor     r9d, r9d
0x14002e388  mov     [rbx+8], r8
0x14002e38c  mov     [r8], rbx
0x14002e38f  mov     [rax+8], rbx
0x14002e393  mov     r8, [rbx+10h]
0x14002e397  lea     edx, [r9+1]
0x14002e39b  mov     rcx, [rcx+120h]
0x14002e3a2  mov     r8, [r8+20h]
0x14002e3a6  call    ?AddTaskNotification@VMX_NOTIFICATION_QUEUE@@QEAAXW4_VM_NOTIFICATION_EVENT@@PEAVVMX_RECORD@@PEAU_GUID@@@Z; VMX_NOTIFICATION_QUEUE::AddTaskNotification(_VM_NOTIFICATION_EVENT,VMX_RECORD *,_GUID *)
0x14002e3ab  mov     rax, [rsi+90h]
0x14002e3b2  mov     rdx, [r15+10h]
0x14002e3b6  mov     rcx, [rsi+8]
0x14002e3ba  call    _guard_dispatch_icall
0x14002e3bf  lea     r9, [rbp+P]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x14002e3c3  mov     rdx, rbx; struct VMX_PACK *
0x14002e3c6  lea     r8, [rbp+var_30]; struct _DISK_GEOMETRY *
0x14002e3ca  mov     rcx, rdi; this
0x14002e3cd  call    ?CreatePrivateRegion@VMX_PHYSICAL_DISK@@QEAAJPEAVVMX_PACK@@PEAU_DISK_GEOMETRY@@PEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_PHYSICAL_DISK::CreatePrivateRegion(VMX_PACK *,_DISK_GEOMETRY *,_DRIVE_LAYOUT_INFORMATION_EX * *)
0x14002e3d2  mov     r14d, eax
0x14002e3d5  test    eax, eax
0x14002e3d7  jns     short loc_14002E456
0x14002e3d9  mov     rcx, [rbx]
0x14002e3dc  cmp     [rcx+8], rbx
0x14002e3e0  jnz     loc_14002EA48
0x14002e3e6  mov     rdx, [rbx+8]
0x14002e3ea  cmp     [rdx], rbx
0x14002e3ed  jnz     loc_14002EA48
0x14002e3f3  mov     [rdx], rcx
0x14002e3f6  mov     [rcx+8], rdx
0x14002e3fa  mov     rcx, rbx; struct VMX_PACK *
0x14002e3fd  call    ?VmxpSendPackDepartNotifications@@YAXPEAVVMX_PACK@@@Z; VmxpSendPackDepartNotifications(VMX_PACK *)
0x14002e402  mov     rcx, rbx; this
0x14002e405  call    ??_GVMX_PACK@@QEAAPEAXI@Z; VMX_PACK::`scalar deleting destructor'(uint)
0x14002e40a  mov     rax, [rsi+90h]
0x14002e411  xor     edx, edx
0x14002e413  mov     rcx, [rsi+8]
0x14002e417  call    _guard_dispatch_icall
0x14002e41c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e423  lea     rax, WPP_GLOBAL_Control
0x14002e42a  cmp     rcx, rax
0x14002e42d  jz      loc_14002E35F
0x14002e433  mov     eax, [rcx+2Ch]
0x14002e436  test    al, 2
0x14002e438  jz      loc_14002E35F
0x14002e43e  cmp     byte ptr [rcx+29h], 2
0x14002e442  jb      loc_14002E35F
0x14002e448  mov     edx, 6Eh ; 'n'
0x14002e44d  mov     rcx, [rcx+18h]
0x14002e451  jmp     loc_14002E350
0x14002e456  mov     rdx, rdi; struct VMX_PHYSICAL_DISK *
0x14002e459  mov     rcx, rbx; this
0x14002e45c  call    ?OnlineConfigCopy@VMX_PACK@@QEAAJPEAVVMX_PHYSICAL_DISK@@@Z; VMX_PACK::OnlineConfigCopy(VMX_PHYSICAL_DISK *)
0x14002e461  mov     r14d, eax
0x14002e464  test    eax, eax
0x14002e466  jns     loc_14002E503
0x14002e46c  mov     rdx, [rbp+P]; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x14002e470  mov     rcx, rdi; this
0x14002e473  call    ?DeletePrivateRegion@VMX_PHYSICAL_DISK@@QEAAXPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_PHYSICAL_DISK::DeletePrivateRegion(_DRIVE_LAYOUT_INFORMATION_EX *)
0x14002e478  mov     rcx, [rbp+P]; P
0x14002e47c  xor     edx, edx; Tag
0x14002e47e  call    cs:__imp_ExFreePoolWithTag
0x14002e485  nop     dword ptr [rax+rax+00h]
0x14002e48a  mov     rcx, [rbx]
0x14002e48d  cmp     [rcx+8], rbx
0x14002e491  jnz     loc_14002EA48
0x14002e497  mov     rax, [rbx+8]
0x14002e49b  cmp     [rax], rbx
0x14002e49e  jnz     loc_14002EA48
0x14002e4a4  mov     [rax], rcx
0x14002e4a7  mov     [rcx+8], rax
0x14002e4ab  mov     rcx, rbx; struct VMX_PACK *
0x14002e4ae  call    ?VmxpSendPackDepartNotifications@@YAXPEAVVMX_PACK@@@Z; VmxpSendPackDepartNotifications(VMX_PACK *)
0x14002e4b3  mov     rcx, rbx; this
0x14002e4b6  call    ??_GVMX_PACK@@QEAAPEAXI@Z; VMX_PACK::`scalar deleting destructor'(uint)
0x14002e4bb  mov     rax, [rsi+90h]
0x14002e4c2  xor     edx, edx
0x14002e4c4  mov     rcx, [rsi+8]
0x14002e4c8  call    _guard_dispatch_icall
0x14002e4cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e4d4  lea     rax, WPP_GLOBAL_Control
0x14002e4db  cmp     rcx, rax
0x14002e4de  jz      loc_14002E35F
0x14002e4e4  mov     eax, [rcx+2Ch]
0x14002e4e7  test    al, 2
0x14002e4e9  jz      loc_14002E35F
0x14002e4ef  cmp     byte ptr [rcx+29h], 2
0x14002e4f3  jb      loc_14002E35F
0x14002e4f9  mov     edx, 6Fh ; 'o'
0x14002e4fe  jmp     loc_14002E44D
0x14002e503  mov     rdx, rdi; struct VMX_PHYSICAL_DISK *
0x14002e506  mov     rcx, rbx; this
0x14002e509  call    ?OnlineLogCopy@VMX_PACK@@QEAAJPEAVVMX_PHYSICAL_DISK@@@Z; VMX_PACK::OnlineLogCopy(VMX_PHYSICAL_DISK *)
0x14002e50e  mov     r14d, eax
0x14002e511  test    eax, eax
0x14002e513  jns     loc_14002E5BB
0x14002e519  mov     rdx, rdi; struct VMX_PHYSICAL_DISK *
0x14002e51c  mov     rcx, rbx; this
0x14002e51f  call    ?OfflineLogCopy@VMX_PACK@@QEAAXPEAVVMX_PHYSICAL_DISK@@@Z; VMX_PACK::OfflineLogCopy(VMX_PHYSICAL_DISK *)
0x14002e524  mov     rdx, [rbp+P]; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x14002e528  mov     rcx, rdi; this
0x14002e52b  call    ?DeletePrivateRegion@VMX_PHYSICAL_DISK@@QEAAXPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_PHYSICAL_DISK::DeletePrivateRegion(_DRIVE_LAYOUT_INFORMATION_EX *)
0x14002e530  mov     rcx, [rbp+P]; P
0x14002e534  xor     edx, edx; Tag
0x14002e536  call    cs:__imp_ExFreePoolWithTag
0x14002e53d  nop     dword ptr [rax+rax+00h]
0x14002e542  mov     rcx, [rbx]
0x14002e545  cmp     [rcx+8], rbx
0x14002e549  jnz     loc_14002EA48
0x14002e54f  mov     rax, [rbx+8]
0x14002e553  cmp     [rax], rbx
0x14002e556  jnz     loc_14002EA48
0x14002e55c  mov     [rax], rcx
0x14002e55f  mov     [rcx+8], rax
0x14002e563  mov     rcx, rbx; struct VMX_PACK *
0x14002e566  call    ?VmxpSendPackDepartNotifications@@YAXPEAVVMX_PACK@@@Z; VmxpSendPackDepartNotifications(VMX_PACK *)
0x14002e56b  mov     rcx, rbx; this
0x14002e56e  call    ??_GVMX_PACK@@QEAAPEAXI@Z; VMX_PACK::`scalar deleting destructor'(uint)
0x14002e573  mov     rax, [rsi+90h]
0x14002e57a  xor     edx, edx
0x14002e57c  mov     rcx, [rsi+8]
0x14002e580  call    _guard_dispatch_icall
0x14002e585  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e58c  lea     rax, WPP_GLOBAL_Control
0x14002e593  cmp     rcx, rax
0x14002e596  jz      loc_14002E35F
0x14002e59c  mov     eax, [rcx+2Ch]
0x14002e59f  test    al, 2
0x14002e5a1  jz      loc_14002E35F
0x14002e5a7  cmp     byte ptr [rcx+29h], 2
0x14002e5ab  jb      loc_14002E35F
0x14002e5b1  mov     edx, 70h ; 'p'
0x14002e5b6  jmp     loc_14002E44D
0x14002e5bb  mov     rax, [rbx+10h]
0x14002e5bf  mov     rcx, [rax+8]
0x14002e5c3  add     rcx, 8; struct _GUID *
0x14002e5c7  call    ?VmxpWritePendingPrimaryPackId@@YAJPEAU_GUID@@@Z; VmxpWritePendingPrimaryPackId(_GUID *)
0x14002e5cc  mov     r14d, eax
0x14002e5cf  mov     rcx, rbx; this
0x14002e5d2  test    eax, eax
0x14002e5d4  jns     loc_14002E680
0x14002e5da  mov     rdx, rdi; struct VMX_PHYSICAL_DISK *
0x14002e5dd  call    ?OfflineLogCopy@VMX_PACK@@QEAAXPEAVVMX_PHYSICAL_DISK@@@Z; VMX_PACK::OfflineLogCopy(VMX_PHYSICAL_DISK *)
0x14002e5e2  mov     rdx, [rbp+P]; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x14002e5e6  mov     rcx, rdi; this
0x14002e5e9  call    ?DeletePrivateRegion@VMX_PHYSICAL_DISK@@QEAAXPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_PHYSICAL_DISK::DeletePrivateRegion(_DRIVE_LAYOUT_INFORMATION_EX *)
0x14002e5ee  mov     rcx, [rbp+P]; P
0x14002e5f2  xor     edx, edx; Tag
0x14002e5f4  call    cs:__imp_ExFreePoolWithTag
0x14002e5fb  nop     dword ptr [rax+rax+00h]
0x14002e600  mov     rcx, [rbx]
0x14002e603  cmp     [rcx+8], rbx
0x14002e607  jnz     loc_14002EA48
0x14002e60d  mov     rax, [rbx+8]
0x14002e611  cmp     [rax], rbx
0x14002e614  jnz     loc_14002EA48
0x14002e61a  mov     [rax], rcx
0x14002e61d  mov     [rcx+8], rax
0x14002e621  mov     rcx, rbx; struct VMX_PACK *
0x14002e624  call    ?VmxpSendPackDepartNotifications@@YAXPEAVVMX_PACK@@@Z; VmxpSendPackDepartNotifications(VMX_PACK *)
0x14002e629  mov     rcx, rbx; this
0x14002e62c  call    ??_GVMX_PACK@@QEAAPEAXI@Z; VMX_PACK::`scalar deleting destructor'(uint)
0x14002e631  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e638  lea     rax, WPP_GLOBAL_Control
0x14002e63f  cmp     rcx, rax
0x14002e642  jz      short loc_14002E669
0x14002e644  mov     eax, [rcx+2Ch]
0x14002e647  test    al, 2
0x14002e649  jz      short loc_14002E669
0x14002e64b  cmp     byte ptr [rcx+29h], 2
0x14002e64f  jb      short loc_14002E669
0x14002e651  mov     rcx, [rcx+18h]
0x14002e655  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x14002e65c  mov     edx, 71h ; 'q'
0x14002e661  mov     r9d, r14d
0x14002e664  call    WPP_SF_d
0x14002e669  mov     rax, [rsi+90h]
0x14002e670  xor     edx, edx
0x14002e672  mov     rcx, [rsi+8]
0x14002e676  call    _guard_dispatch_icall
0x14002e67b  jmp     loc_14002E35F
0x14002e680  call    ?BeginTransaction@VMX_PACK@@QEAAJXZ; VMX_PACK::BeginTransaction(void)
0x14002e685  mov     r15d, eax
0x14002e688  test    eax, eax
0x14002e68a  js      loc_14002E9A2
0x14002e690  lea     r8, [rbp+var_40]; struct VMX_RECORD **
0x14002e694  mov     rdx, rdi; struct VMX_PHYSICAL_DISK *
0x14002e697  mov     rcx, rbx; this
0x14002e69a  call    ?AddDiskTransaction@VMX_PACK@@QEAAJPEAVVMX_PHYSICAL_DISK@@PEAPEAVVMX_RECORD@@@Z; VMX_PACK::AddDiskTransaction(VMX_PHYSICAL_DISK *,VMX_RECORD * *)
0x14002e69f  mov     r15d, eax
0x14002e6a2  test    eax, eax
0x14002e6a4  js      loc_14002E99A
0x14002e6aa  mov     r14, [rbp+var_40]
0x14002e6ae  mov     rcx, rbx; this
0x14002e6b1  mov     rdx, r14; struct VMX_RECORD *
0x14002e6b4  call    ?AddVoterTransaction@VMX_PACK@@QEAAJPEAVVMX_RECORD@@@Z; VMX_PACK::AddVoterTransaction(VMX_RECORD *)
0x14002e6b9  mov     r15d, eax
0x14002e6bc  test    eax, eax
0x14002e6be  js      loc_14002E99A
0x14002e6c4  mov     r8b, 1; unsigned __int8
0x14002e6c7  xor     edx, edx; unsigned __int8
0x14002e6c9  mov     rcx, rbx; this
0x14002e6cc  call    ?CommitTransaction@VMX_PACK@@QEAAJEE@Z; VMX_PACK::CommitTransaction(uchar,uchar)
0x14002e6d1  mov     r15d, eax
0x14002e6d4  test    eax, eax
0x14002e6d6  js      loc_14002E9A2
0x14002e6dc  mov     rcx, rbx; this
0x14002e6df  call    ?BeginTransaction@VMX_PACK@@QEAAJXZ; VMX_PACK::BeginTransaction(void)
0x14002e6e4  mov     r12, [rbp+P]
0x14002e6e8  mov     r15d, eax
0x14002e6eb  test    eax, eax
0x14002e6ed  js      loc_14002E8E2
0x14002e6f3  mov     r9, r12; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x14002e6f6  mov     [rsp+78h+var_58], r14; struct VMX_RECORD *
0x14002e6fb  lea     r8, [rbp+var_30]; struct _DISK_GEOMETRY *
  ... truncated ...
```
