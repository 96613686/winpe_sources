# VmxpDeletePresentDiskFromPack(VMX_PACK *,_GUID *)

- ea: `0x14002eb3c`
- end: `0x14002f1dd`
- name: `?VmxpDeletePresentDiskFromPack@@YAJPEAVVMX_PACK@@PEAU_GUID@@@Z`
- size: `1697`
- prototype: `__int64 __fastcall(struct VMX_PACK *this, struct _GUID *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003677c`

## callees

- `0x140008df0`
- `0x1400099d8`
- `0x14001b960`
- `0x14001b9a0`
- `0x14002a3f4`
- `0x14002eab4`
- `0x14002eaf4`
- `0x14002eb3c`
- `0x14002fbf4`
- `0x1400315e8`
- `0x140033854`
- `0x14003acbc`
- `0x140043754`
- `0x140044ac4`
- `0x14004a70c`
- `0x14004ae60`
- `0x14004bac0`
- `0x1400557e4`
- `0x140055984`
- `0x140055f34`
- `0x1400561fc`
- `0x14005c600`
- `0x14005d734`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002ec5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ed3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ee11`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ee90`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f03b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ec5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ed3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ee11`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ee90`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f03b`

## pseudocode

```c
__int64 __fastcall VmxpDeletePresentDiskFromPack(struct VMX_PACK *this, struct _GUID *a2)
{
  VMX_GLOBAL_DATA *v2; // r15
  struct _GUID *v3; // rsi
  struct VMX_PACK *v4; // rbx
  int v5; // edi
  struct VMX_RECORD *DiskById; // r14
  __int64 v7; // r12
  VMX_PHYSICAL_DISK *v8; // rdi
  VMX_DISK_DEVICE *v9; // r13
  int DriveGeometry; // esi
  VMX_PHYSICAL_DISK *v11; // rcx
  VMX_PHYSICAL_DISK **v12; // rax
  unsigned int v13; // edx
  struct _DRIVE_LAYOUT_INFORMATION_EX *v15; // r12
  VMX_NOTIFICATION_QUEUE *v16; // rcx
  __int64 v17; // rdx
  struct _DRIVE_LAYOUT_INFORMATION_EX *v18; // r12
  VMX_NOTIFICATION_QUEUE *v19; // rcx
  unsigned int v20; // ebx
  __int64 v21; // rdx
  VMX_NOTIFICATION_QUEUE *v22; // rcx
  __int64 v23; // rdx
  PVOID P; // [rsp+20h] [rbp-40h] BYREF
  struct VMX_PACK *v25; // [rsp+28h] [rbp-38h] BYREF
  struct _GUID *v26; // [rsp+30h] [rbp-30h]
  struct _DISK_GEOMETRY v27; // [rsp+38h] [rbp-28h] BYREF

  v2 = Global;
  memset(&v27, 0, sizeof(v27));
  P = 0;
  v3 = a2;
  v26 = a2;
  v4 = this;
  v25 = this;
  VMX_PACK::RemoveOutOfSyncVoters(this);
  while ( 1 )
  {
    while ( 1 )
    {
      v5 = VMX_PACK::BeginTransaction(v4);
      if ( v5 >= 0 )
      {
        v5 = VMX_PACK::CommitTransaction((struct VMX_CONFIG **)v4, 0, 1);
        if ( v5 >= 0 )
          break;
      }
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          136,
          WPP_2f8af752156e3401cd435973c831895d_Traceguids,
          (unsigned int)v5);
      }
      if ( v5 != -1070071728 && v5 != -1070071804 || VmxpRecoverPackConfigOnline(v4, &v25) < 0 )
        return (unsigned int)v5;
      v4 = v25;
    }
    DiskById = VMX_CONFIG::FindDiskById(*((VMX_CONFIG **)v4 + 2), v3);
    v7 = *((_QWORD *)DiskById + (*((_WORD *)DiskById + 32) & 1) + 5);
    v8 = *(VMX_PHYSICAL_DISK **)(v7 + 128);
    if ( !v8 )
    {
      v19 = WPP_GLOBAL_Control;
      v20 = -1070071791;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v21 = 137;
LABEL_94:
        WPP_SF_d(*((_QWORD *)v19 + 3), v21, WPP_2f8af752156e3401cd435973c831895d_Traceguids, v20);
      }
      return v20;
    }
    if ( *((_DWORD *)v4 + 10) == 1 && (*(_DWORD *)(v7 + 96) & 0x20) == 0 )
    {
      v19 = WPP_GLOBAL_Control;
      v20 = -1070071798;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v21 = 138;
        goto LABEL_94;
      }
      return v20;
    }
    v9 = (VMX_DISK_DEVICE *)*((_QWORD *)v8 + 2);
    DriveGeometry = VMX_DISK_DEVICE::GetDriveGeometry(v9, &v27);
    if ( DriveGeometry < 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return (unsigned int)DriveGeometry;
      }
      v23 = 139;
LABEL_88:
      WPP_SF_d(*((_QWORD *)v22 + 3), v23, WPP_2f8af752156e3401cd435973c831895d_Traceguids, (unsigned int)DriveGeometry);
      return (unsigned int)DriveGeometry;
    }
    DriveGeometry = VMX_DISK_DEVICE::GetDriveLayoutEx(v9, (struct _DRIVE_LAYOUT_INFORMATION_EX **)&P);
    if ( DriveGeometry < 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return (unsigned int)DriveGeometry;
      }
      v23 = 140;
      goto LABEL_88;
    }
    (*((void (__fastcall **)(_QWORD, _QWORD))v2 + 18))(*((_QWORD *)v2 + 1), *((_QWORD *)v9 + 2));
    DriveGeometry = VMX_PHYSICAL_DISK::CreateBasicPartitions(
                      v8,
                      DiskById,
                      &v27,
                      (struct _DRIVE_LAYOUT_INFORMATION_EX *)P);
    ExFreePoolWithTag(P, 0);
    if ( DriveGeometry < 0 )
    {
      (*((void (__fastcall **)(_QWORD, _QWORD))v2 + 18))(*((_QWORD *)v2 + 1), 0);
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return (unsigned int)DriveGeometry;
      }
      v23 = 141;
      goto LABEL_88;
    }
    DriveGeometry = VMX_DISK_DEVICE::GetDriveLayoutEx(v9, (struct _DRIVE_LAYOUT_INFORMATION_EX **)&P);
    if ( DriveGeometry < 0 )
    {
      VmxpRemovePhysicalDisk(v8);
      (*((void (__fastcall **)(_QWORD, _QWORD))v2 + 18))(*((_QWORD *)v2 + 1), 0);
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return (unsigned int)DriveGeometry;
      }
      v23 = 142;
      goto LABEL_88;
    }
    if ( (*(_DWORD *)(v7 + 96) & 0x20) != 0 )
      goto LABEL_15;
    DriveGeometry = VMX_PACK::BeginTransaction(v4);
    if ( DriveGeometry >= 0 )
      break;
LABEL_23:
    v15 = (struct _DRIVE_LAYOUT_INFORMATION_EX *)P;
    if ( (int)VMX_PHYSICAL_DISK::CreateDynamicPartitions(v8, DiskById, &v27, (struct _DRIVE_LAYOUT_INFORMATION_EX *)P) < 0 )
    {
      if ( *((_BYTE *)v4 + 56) && (int)VMX_PACK::BeginTransaction(v4) >= 0 )
      {
        if ( VMX_PACK::RemoveVolumesTransaction(v4, DiskById) < 0 )
          VMX_PACK::AbortTransaction(v4);
        else
          VMX_PACK::CommitTransaction((struct VMX_CONFIG **)v4, 1, 0);
      }
      VMX_PHYSICAL_DISK::DeletePrivateRegion(v8, v15);
      VmxpRemovePhysicalDisk(v8);
    }
    ExFreePoolWithTag(v15, 0);
    (*((void (__fastcall **)(_QWORD, _QWORD))v2 + 18))(*((_QWORD *)v2 + 1), 0);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v17 = 143;
LABEL_45:
      WPP_SF_d(*((_QWORD *)v16 + 3), v17, WPP_2f8af752156e3401cd435973c831895d_Traceguids, (unsigned int)DriveGeometry);
    }
LABEL_46:
    if ( DriveGeometry != -1070071728 && DriveGeometry != -1070071804 || VmxpRecoverPackConfigOnline(v4, &v25) < 0 )
      return (unsigned int)DriveGeometry;
    v4 = v25;
    v3 = v26;
  }
  DriveGeometry = VMX_PACK::RemoveVoterTransaction(v4, DiskById);
  if ( DriveGeometry < 0 )
  {
    VMX_PACK::AbortTransaction(v4);
    goto LABEL_23;
  }
  DriveGeometry = VMX_PACK::CommitTransaction((struct VMX_CONFIG **)v4, 0, 1);
  if ( DriveGeometry < 0 )
    goto LABEL_23;
LABEL_15:
  DriveGeometry = VMX_PACK::BeginTransaction(v4);
  if ( DriveGeometry < 0 )
    goto LABEL_35;
  DriveGeometry = VMX_PACK::RemoveVolumesTransaction(v4, DiskById);
  if ( DriveGeometry < 0 || (DriveGeometry = VMX_PACK::RemoveDiskTransaction(v4, DiskById), DriveGeometry < 0) )
  {
    VMX_PACK::AbortTransaction(v4);
LABEL_35:
    v18 = (struct _DRIVE_LAYOUT_INFORMATION_EX *)P;
    if ( (int)VMX_PHYSICAL_DISK::CreateDynamicPartitions(v8, DiskById, &v27, (struct _DRIVE_LAYOUT_INFORMATION_EX *)P) < 0 )
    {
      if ( *((_BYTE *)v4 + 56) && (int)VMX_PACK::BeginTransaction(v4) >= 0 )
      {
        if ( VMX_PACK::RemoveVolumesTransaction(v4, DiskById) < 0 )
          VMX_PACK::AbortTransaction(v4);
        else
          VMX_PACK::CommitTransaction((struct VMX_CONFIG **)v4, 1, 0);
      }
      VMX_PHYSICAL_DISK::DeletePrivateRegion(v8, v18);
      VmxpRemovePhysicalDisk(v8);
      ExFreePoolWithTag(v18, 0);
      (*((void (__fastcall **)(_QWORD, _QWORD))v2 + 18))(*((_QWORD *)v2 + 1), 0);
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v23 = 144;
        goto LABEL_88;
      }
      return (unsigned int)DriveGeometry;
    }
    ExFreePoolWithTag(v18, 0);
    (*((void (__fastcall **)(_QWORD, _QWORD))v2 + 18))(*((_QWORD *)v2 + 1), 0);
    if ( *((_BYTE *)v4 + 56) && (int)VMX_PACK::BeginTransaction(v4) >= 0 )
    {
      if ( (int)VMX_PACK::AddVoterTransaction((struct VMX_TRANSACTION **)v4, DiskById) < 0 )
        VMX_PACK::AbortTransaction(v4);
      else
        VMX_PACK::CommitTransaction((struct VMX_CONFIG **)v4, 0, 1);
    }
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v17 = 145;
      goto LABEL_45;
    }
    goto LABEL_46;
  }
  DriveGeometry = VMX_PACK::CommitTransaction((struct VMX_CONFIG **)v4, 0, 1);
  if ( DriveGeometry < 0 )
    goto LABEL_35;
  VMX_PACK::OfflineLogCopy(v4, v8);
  VMX_PHYSICAL_DISK::DeletePrivateRegion(v8, (struct _DRIVE_LAYOUT_INFORMATION_EX *)P);
  ExFreePoolWithTag(P, 0);
  (*((void (__fastcall **)(_QWORD, _QWORD))v2 + 18))(*((_QWORD *)v2 + 1), 0);
  v11 = *(VMX_PHYSICAL_DISK **)v8;
  if ( *(VMX_PHYSICAL_DISK **)(*(_QWORD *)v8 + 8LL) != v8
    || (v12 = (VMX_PHYSICAL_DISK **)*((_QWORD *)v8 + 1), *v12 != v8) )
  {
    __fastfail(3u);
  }
  *v12 = v11;
  *((_QWORD *)v11 + 1) = v12;
  VMX_NOTIFICATION_QUEUE::AddInvalidDiskNotification(*((_QWORD *)Global + 36), 2, v8);
  VMX_PHYSICAL_DISK::`scalar deleting destructor'(v8, v13);
  return 0;
}

```

## disassembly

```asm
0x14002eb3c  mov     [rsp-38h+arg_10], rbx
0x14002eb41  push    rbp
0x14002eb42  push    rsi
0x14002eb43  push    rdi
0x14002eb44  push    r12
0x14002eb46  push    r13
0x14002eb48  push    r14
0x14002eb4a  push    r15
0x14002eb4c  mov     rbp, rsp
0x14002eb4f  sub     rsp, 60h
0x14002eb53  mov     rax, cs:__security_cookie
0x14002eb5a  xor     rax, rsp
0x14002eb5d  mov     [rbp+var_10], rax
0x14002eb61  mov     r15, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14002eb68  xor     eax, eax
0x14002eb6a  xorps   xmm0, xmm0
0x14002eb6d  mov     qword ptr [rbp+var_28.SectorsPerTrack], rax
0x14002eb71  movups  xmmword ptr [rbp+var_28.Cylinders], xmm0
0x14002eb75  mov     [rbp+P], rax
0x14002eb79  mov     rsi, rdx
0x14002eb7c  mov     [rbp+var_30], rdx
0x14002eb80  mov     rbx, rcx
0x14002eb83  mov     [rbp+var_38], rcx
0x14002eb87  call    ?RemoveOutOfSyncVoters@VMX_PACK@@QEAAJXZ; VMX_PACK::RemoveOutOfSyncVoters(void)
0x14002eb8c  lea     r13, WPP_GLOBAL_Control
0x14002eb93  mov     rcx, rbx; this
0x14002eb96  call    ?BeginTransaction@VMX_PACK@@QEAAJXZ; VMX_PACK::BeginTransaction(void)
0x14002eb9b  mov     edi, eax
0x14002eb9d  test    eax, eax
0x14002eb9f  js      loc_14002EF50
0x14002eba5  mov     r8b, 1; unsigned __int8
0x14002eba8  xor     edx, edx; unsigned __int8
0x14002ebaa  mov     rcx, rbx; this
0x14002ebad  call    ?CommitTransaction@VMX_PACK@@QEAAJEE@Z; VMX_PACK::CommitTransaction(uchar,uchar)
0x14002ebb2  mov     edi, eax
0x14002ebb4  test    eax, eax
0x14002ebb6  js      loc_14002EF50
0x14002ebbc  mov     rcx, [rbx+10h]; this
0x14002ebc0  mov     rdx, rsi; struct _GUID *
0x14002ebc3  call    ?FindDiskById@VMX_CONFIG@@QEAAPEAVVMX_RECORD@@PEAU_GUID@@@Z; VMX_CONFIG::FindDiskById(_GUID *)
0x14002ebc8  mov     r14, rax
0x14002ebcb  movzx   ecx, word ptr [rax+40h]
0x14002ebcf  and     ecx, 1
0x14002ebd2  mov     r12, [rax+rcx*8+28h]
0x14002ebd7  mov     rdi, [r12+80h]
0x14002ebdf  test    rdi, rdi
0x14002ebe2  jz      loc_14002F17B
0x14002ebe8  cmp     dword ptr [rbx+28h], 1
0x14002ebec  jnz     short loc_14002EBFC
0x14002ebee  mov     ecx, [r12+60h]
0x14002ebf3  test    cl, 20h
0x14002ebf6  jz      loc_14002EFB2
0x14002ebfc  mov     r13, [rdi+10h]
0x14002ec00  lea     rdx, [rbp+var_28]; PVOID
0x14002ec04  mov     rcx, r13; this
0x14002ec07  call    ?GetDriveGeometry@VMX_DISK_DEVICE@@QEAAJPEAU_DISK_GEOMETRY@@@Z; VMX_DISK_DEVICE::GetDriveGeometry(_DISK_GEOMETRY *)
0x14002ec0c  mov     esi, eax
0x14002ec0e  test    eax, eax
0x14002ec10  js      loc_14002F13F
0x14002ec16  lea     rdx, [rbp+P]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x14002ec1a  mov     rcx, r13; this
0x14002ec1d  call    ?GetDriveLayoutEx@VMX_DISK_DEVICE@@QEAAJPEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_DISK_DEVICE::GetDriveLayoutEx(_DRIVE_LAYOUT_INFORMATION_EX * *)
0x14002ec22  mov     esi, eax
0x14002ec24  test    eax, eax
0x14002ec26  js      loc_14002F118
0x14002ec2c  mov     rax, [r15+90h]
0x14002ec33  mov     rdx, [r13+10h]
0x14002ec37  mov     rcx, [r15+8]
0x14002ec3b  call    _guard_dispatch_icall
0x14002ec40  mov     r9, [rbp+P]; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x14002ec44  lea     r8, [rbp+var_28]; struct _DISK_GEOMETRY *
0x14002ec48  mov     rdx, r14; struct VMX_RECORD *
0x14002ec4b  mov     rcx, rdi; this
0x14002ec4e  call    ?CreateBasicPartitions@VMX_PHYSICAL_DISK@@QEAAJPEAVVMX_RECORD@@PEAU_DISK_GEOMETRY@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_PHYSICAL_DISK::CreateBasicPartitions(VMX_RECORD *,_DISK_GEOMETRY *,_DRIVE_LAYOUT_INFORMATION_EX *)
0x14002ec53  mov     rcx, [rbp+P]; P
0x14002ec57  xor     edx, edx; Tag
0x14002ec59  mov     esi, eax
0x14002ec5b  call    cs:__imp_ExFreePoolWithTag
0x14002ec62  nop     dword ptr [rax+rax+00h]
0x14002ec67  test    esi, esi
0x14002ec69  js      loc_14002F0DF
0x14002ec6f  lea     rdx, [rbp+P]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x14002ec73  mov     rcx, r13; this
0x14002ec76  call    ?GetDriveLayoutEx@VMX_DISK_DEVICE@@QEAAJPEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_DISK_DEVICE::GetDriveLayoutEx(_DRIVE_LAYOUT_INFORMATION_EX * *)
0x14002ec7b  mov     esi, eax
0x14002ec7d  test    eax, eax
0x14002ec7f  js      loc_14002F08F
0x14002ec85  mov     eax, [r12+60h]
0x14002ec8a  test    al, 20h
0x14002ec8c  jnz     short loc_14002ECCC
0x14002ec8e  mov     rcx, rbx; this
0x14002ec91  call    ?BeginTransaction@VMX_PACK@@QEAAJXZ; VMX_PACK::BeginTransaction(void)
0x14002ec96  mov     esi, eax
0x14002ec98  test    eax, eax
0x14002ec9a  js      loc_14002EDAA
0x14002eca0  mov     rdx, r14; struct VMX_RECORD *
0x14002eca3  mov     rcx, rbx; this
0x14002eca6  call    ?RemoveVoterTransaction@VMX_PACK@@QEAAJPEAVVMX_RECORD@@@Z; VMX_PACK::RemoveVoterTransaction(VMX_RECORD *)
0x14002ecab  mov     esi, eax
0x14002ecad  mov     rcx, rbx; this
0x14002ecb0  test    eax, eax
0x14002ecb2  js      loc_14002EDA5
0x14002ecb8  mov     r8b, 1; unsigned __int8
0x14002ecbb  xor     edx, edx; unsigned __int8
0x14002ecbd  call    ?CommitTransaction@VMX_PACK@@QEAAJEE@Z; VMX_PACK::CommitTransaction(uchar,uchar)
0x14002ecc2  mov     esi, eax
0x14002ecc4  test    eax, eax
0x14002ecc6  js      loc_14002EDAA
0x14002eccc  mov     rcx, rbx; this
0x14002eccf  call    ?BeginTransaction@VMX_PACK@@QEAAJXZ; VMX_PACK::BeginTransaction(void)
0x14002ecd4  mov     esi, eax
0x14002ecd6  test    eax, eax
0x14002ecd8  js      loc_14002EE6D
0x14002ecde  mov     rdx, r14; struct VMX_RECORD *
0x14002ece1  mov     rcx, rbx; this
0x14002ece4  call    ?RemoveVolumesTransaction@VMX_PACK@@QEAAJPEAVVMX_RECORD@@@Z; VMX_PACK::RemoveVolumesTransaction(VMX_RECORD *)
0x14002ece9  mov     esi, eax
0x14002eceb  test    eax, eax
0x14002eced  js      loc_14002EE65
0x14002ecf3  mov     rdx, r14; struct VMX_RECORD *
0x14002ecf6  mov     rcx, rbx; this
0x14002ecf9  call    ?RemoveDiskTransaction@VMX_PACK@@QEAAJPEAVVMX_RECORD@@@Z; VMX_PACK::RemoveDiskTransaction(VMX_RECORD *)
0x14002ecfe  mov     esi, eax
0x14002ed00  test    eax, eax
0x14002ed02  js      loc_14002EE65
0x14002ed08  mov     r8b, 1; unsigned __int8
0x14002ed0b  xor     edx, edx; unsigned __int8
0x14002ed0d  mov     rcx, rbx; this
0x14002ed10  call    ?CommitTransaction@VMX_PACK@@QEAAJEE@Z; VMX_PACK::CommitTransaction(uchar,uchar)
0x14002ed15  mov     esi, eax
0x14002ed17  test    eax, eax
0x14002ed19  js      loc_14002EE6D
0x14002ed1f  mov     rdx, rdi; struct VMX_PHYSICAL_DISK *
0x14002ed22  mov     rcx, rbx; this
0x14002ed25  call    ?OfflineLogCopy@VMX_PACK@@QEAAXPEAVVMX_PHYSICAL_DISK@@@Z; VMX_PACK::OfflineLogCopy(VMX_PHYSICAL_DISK *)
0x14002ed2a  mov     rdx, [rbp+P]; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x14002ed2e  mov     rcx, rdi; this
0x14002ed31  call    ?DeletePrivateRegion@VMX_PHYSICAL_DISK@@QEAAXPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_PHYSICAL_DISK::DeletePrivateRegion(_DRIVE_LAYOUT_INFORMATION_EX *)
0x14002ed36  mov     rcx, [rbp+P]; P
0x14002ed3a  xor     edx, edx; Tag
0x14002ed3c  call    cs:__imp_ExFreePoolWithTag
0x14002ed43  nop     dword ptr [rax+rax+00h]
0x14002ed48  mov     rax, [r15+90h]
0x14002ed4f  xor     edx, edx
0x14002ed51  mov     rcx, [r15+8]
0x14002ed55  call    _guard_dispatch_icall
0x14002ed5a  mov     rcx, [rdi]
0x14002ed5d  cmp     [rcx+8], rdi
0x14002ed61  jnz     loc_14002EFE7
0x14002ed67  mov     rax, [rdi+8]
0x14002ed6b  cmp     [rax], rdi
0x14002ed6e  jnz     loc_14002EFE7
0x14002ed74  mov     [rax], rcx
0x14002ed77  mov     r8, rdi
0x14002ed7a  mov     [rcx+8], rax
0x14002ed7e  mov     edx, 2
0x14002ed83  mov     rcx, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14002ed8a  mov     rcx, [rcx+120h]
0x14002ed91  call    ?AddInvalidDiskNotification@VMX_NOTIFICATION_QUEUE@@QEAAXW4_VM_NOTIFICATION_EVENT@@PEAVVMX_PHYSICAL_DISK@@@Z; VMX_NOTIFICATION_QUEUE::AddInvalidDiskNotification(_VM_NOTIFICATION_EVENT,VMX_PHYSICAL_DISK *)
0x14002ed96  mov     rcx, rdi; this
0x14002ed99  call    ??_GVMX_PHYSICAL_DISK@@QEAAPEAXI@Z; VMX_PHYSICAL_DISK::`scalar deleting destructor'(uint)
0x14002ed9e  xor     eax, eax
0x14002eda0  jmp     loc_14002F1B8
0x14002eda5  call    ?AbortTransaction@VMX_PACK@@QEAAXXZ; VMX_PACK::AbortTransaction(void)
0x14002edaa  mov     r12, [rbp+P]
0x14002edae  lea     r8, [rbp+var_28]; struct _DISK_GEOMETRY *
0x14002edb2  mov     r9, r12; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x14002edb5  mov     rdx, r14; struct VMX_RECORD *
0x14002edb8  mov     rcx, rdi; this
0x14002edbb  call    ?CreateDynamicPartitions@VMX_PHYSICAL_DISK@@QEAAJPEAVVMX_RECORD@@PEAU_DISK_GEOMETRY@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_PHYSICAL_DISK::CreateDynamicPartitions(VMX_RECORD *,_DISK_GEOMETRY *,_DRIVE_LAYOUT_INFORMATION_EX *)
0x14002edc0  test    eax, eax
0x14002edc2  jns     short loc_14002EE0C
0x14002edc4  cmp     byte ptr [rbx+38h], 0
0x14002edc8  jz      short loc_14002EDF9
0x14002edca  mov     rcx, rbx; this
0x14002edcd  call    ?BeginTransaction@VMX_PACK@@QEAAJXZ; VMX_PACK::BeginTransaction(void)
0x14002edd2  test    eax, eax
0x14002edd4  js      short loc_14002EDF9
0x14002edd6  mov     rdx, r14; struct VMX_RECORD *
0x14002edd9  mov     rcx, rbx; this
0x14002eddc  call    ?RemoveVolumesTransaction@VMX_PACK@@QEAAJPEAVVMX_RECORD@@@Z; VMX_PACK::RemoveVolumesTransaction(VMX_RECORD *)
0x14002ede1  mov     rcx, rbx; this
0x14002ede4  test    eax, eax
0x14002ede6  js      short loc_14002EDF4
0x14002ede8  xor     r8d, r8d; unsigned __int8
0x14002edeb  mov     dl, 1; unsigned __int8
0x14002eded  call    ?CommitTransaction@VMX_PACK@@QEAAJEE@Z; VMX_PACK::CommitTransaction(uchar,uchar)
0x14002edf2  jmp     short loc_14002EDF9
0x14002edf4  call    ?AbortTransaction@VMX_PACK@@QEAAXXZ; VMX_PACK::AbortTransaction(void)
0x14002edf9  mov     rdx, r12; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x14002edfc  mov     rcx, rdi; this
0x14002edff  call    ?DeletePrivateRegion@VMX_PHYSICAL_DISK@@QEAAXPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_PHYSICAL_DISK::DeletePrivateRegion(_DRIVE_LAYOUT_INFORMATION_EX *)
0x14002ee04  mov     rcx, rdi; this
0x14002ee07  call    ?VmxpRemovePhysicalDisk@@YAXPEAVVMX_PHYSICAL_DISK@@@Z; VmxpRemovePhysicalDisk(VMX_PHYSICAL_DISK *)
0x14002ee0c  xor     edx, edx; Tag
0x14002ee0e  mov     rcx, r12; P
0x14002ee11  call    cs:__imp_ExFreePoolWithTag
0x14002ee18  nop     dword ptr [rax+rax+00h]
0x14002ee1d  mov     rax, [r15+90h]
0x14002ee24  xor     edx, edx
0x14002ee26  mov     rcx, [r15+8]
0x14002ee2a  call    _guard_dispatch_icall
0x14002ee2f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ee36  lea     r13, WPP_GLOBAL_Control
0x14002ee3d  cmp     rcx, r13
0x14002ee40  jz      loc_14002EF1B
0x14002ee46  mov     eax, [rcx+2Ch]
0x14002ee49  test    al, 2
0x14002ee4b  jz      loc_14002EF1B
0x14002ee51  cmp     byte ptr [rcx+29h], 2
0x14002ee55  jb      loc_14002EF1B
0x14002ee5b  mov     edx, 8Fh
0x14002ee60  jmp     loc_14002EF08
0x14002ee65  mov     rcx, rbx; this
0x14002ee68  call    ?AbortTransaction@VMX_PACK@@QEAAXXZ; VMX_PACK::AbortTransaction(void)
0x14002ee6d  mov     r12, [rbp+P]
0x14002ee71  lea     r8, [rbp+var_28]; struct _DISK_GEOMETRY *
0x14002ee75  mov     r9, r12; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x14002ee78  mov     rdx, r14; struct VMX_RECORD *
0x14002ee7b  mov     rcx, rdi; this
0x14002ee7e  call    ?CreateDynamicPartitions@VMX_PHYSICAL_DISK@@QEAAJPEAVVMX_RECORD@@PEAU_DISK_GEOMETRY@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_PHYSICAL_DISK::CreateDynamicPartitions(VMX_RECORD *,_DISK_GEOMETRY *,_DRIVE_LAYOUT_INFORMATION_EX *)
0x14002ee83  test    eax, eax
0x14002ee85  js      loc_14002EFEE
0x14002ee8b  xor     edx, edx; Tag
0x14002ee8d  mov     rcx, r12; P
0x14002ee90  call    cs:__imp_ExFreePoolWithTag
0x14002ee97  nop     dword ptr [rax+rax+00h]
0x14002ee9c  mov     rax, [r15+90h]
0x14002eea3  xor     edx, edx
0x14002eea5  mov     rcx, [r15+8]
0x14002eea9  call    _guard_dispatch_icall
0x14002eeae  cmp     byte ptr [rbx+38h], 0
0x14002eeb2  jz      short loc_14002EEE3
0x14002eeb4  mov     rcx, rbx; this
0x14002eeb7  call    ?BeginTransaction@VMX_PACK@@QEAAJXZ; VMX_PACK::BeginTransaction(void)
0x14002eebc  test    eax, eax
0x14002eebe  js      short loc_14002EEE3
0x14002eec0  mov     rdx, r14; struct VMX_RECORD *
0x14002eec3  mov     rcx, rbx; this
0x14002eec6  call    ?AddVoterTransaction@VMX_PACK@@QEAAJPEAVVMX_RECORD@@@Z; VMX_PACK::AddVoterTransaction(VMX_RECORD *)
0x14002eecb  mov     rcx, rbx; this
0x14002eece  test    eax, eax
0x14002eed0  js      short loc_14002EEDE
0x14002eed2  mov     r8b, 1; unsigned __int8
0x14002eed5  xor     edx, edx; unsigned __int8
0x14002eed7  call    ?CommitTransaction@VMX_PACK@@QEAAJEE@Z; VMX_PACK::CommitTransaction(uchar,uchar)
0x14002eedc  jmp     short loc_14002EEE3
0x14002eede  call    ?AbortTransaction@VMX_PACK@@QEAAXXZ; VMX_PACK::AbortTransaction(void)
0x14002eee3  mov     rcx, cs:WPP_GLOBAL_Control
0x14002eeea  lea     r13, WPP_GLOBAL_Control
0x14002eef1  cmp     rcx, r13
0x14002eef4  jz      short loc_14002EF1B
0x14002eef6  mov     eax, [rcx+2Ch]
0x14002eef9  test    al, 2
0x14002eefb  jz      short loc_14002EF1B
0x14002eefd  cmp     byte ptr [rcx+29h], 2
0x14002ef01  jb      short loc_14002EF1B
0x14002ef03  mov     edx, 91h
0x14002ef08  mov     rcx, [rcx+18h]
0x14002ef0c  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x14002ef13  mov     r9d, esi
0x14002ef16  call    WPP_SF_d
0x14002ef1b  cmp     esi, 0C0380050h
0x14002ef21  jz      short loc_14002EF2F
0x14002ef23  cmp     esi, 0C0380004h
0x14002ef29  jnz     loc_14002F177
0x14002ef2f  lea     rdx, [rbp+var_38]; struct VMX_PACK **
0x14002ef33  mov     rcx, rbx; struct VMX_PACK *
0x14002ef36  call    ?VmxpRecoverPackConfigOnline@@YAJPEAVVMX_PACK@@PEAPEAV1@@Z; VmxpRecoverPackConfigOnline(VMX_PACK *,VMX_PACK * *)
0x14002ef3b  test    eax, eax
0x14002ef3d  js      loc_14002F177
0x14002ef43  mov     rbx, [rbp+var_38]
0x14002ef47  mov     rsi, [rbp+var_30]
0x14002ef4b  jmp     loc_14002EB93
0x14002ef50  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ef57  cmp     rcx, r13
0x14002ef5a  jz      short loc_14002EF81
0x14002ef5c  mov     eax, [rcx+2Ch]
0x14002ef5f  test    al, 2
0x14002ef61  jz      short loc_14002EF81
0x14002ef63  cmp     byte ptr [rcx+29h], 2
0x14002ef67  jb      short loc_14002EF81
0x14002ef69  mov     rcx, [rcx+18h]
0x14002ef6d  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x14002ef74  mov     edx, 88h
0x14002ef79  mov     r9d, edi
0x14002ef7c  call    WPP_SF_d
0x14002ef81  cmp     edi, 0C0380050h
0x14002ef87  jz      short loc_14002EF95
0x14002ef89  cmp     edi, 0C0380004h
0x14002ef8f  jnz     loc_14002F1B6
0x14002ef95  lea     rdx, [rbp+var_38]; struct VMX_PACK **
0x14002ef99  mov     rcx, rbx; struct VMX_PACK *
0x14002ef9c  call    ?VmxpRecoverPackConfigOnline@@YAJPEAVVMX_PACK@@PEAPEAV1@@Z; VmxpRecoverPackConfigOnline(VMX_PACK *,VMX_PACK * *)
0x14002efa1  test    eax, eax
0x14002efa3  js      loc_14002F1B6
0x14002efa9  mov     rbx, [rbp+var_38]
0x14002efad  jmp     loc_14002EB93
0x14002efb2  mov     rcx, cs:WPP_GLOBAL_Control
0x14002efb9  mov     ebx, 0C038000Ah
  ... truncated ...
```
