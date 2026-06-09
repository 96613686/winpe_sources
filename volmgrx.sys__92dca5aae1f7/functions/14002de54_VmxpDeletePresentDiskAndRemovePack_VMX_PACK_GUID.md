# VmxpDeletePresentDiskAndRemovePack(VMX_PACK *,_GUID *)

- ea: `0x14002de54`
- end: `0x14002e229`
- name: `?VmxpDeletePresentDiskAndRemovePack@@YAJPEAVVMX_PACK@@PEAU_GUID@@@Z`
- size: `981`
- prototype: `__int64 __fastcall(struct VMX_PACK *this, struct _GUID *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003677c`

## callees

- `0x140008dc8`
- `0x140008df0`
- `0x1400099d8`
- `0x14001b960`
- `0x14001b9a0`
- `0x14002a3f4`
- `0x14002d3ec`
- `0x14002de54`
- `0x14002eab4`
- `0x14002fbf4`
- `0x1400315e8`
- `0x140033854`
- `0x140043754`
- `0x140044ac4`
- `0x14004a70c`
- `0x14004bac0`
- `0x140055f34`
- `0x14005c600`
- `0x14005d734`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002dfcb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e109`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e1af`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002dfcb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e109`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e1af`

## pseudocode

```c
__int64 __fastcall VmxpDeletePresentDiskAndRemovePack(struct VMX_PACK *this, struct _GUID *a2)
{
  VMX_CONFIG *v3; // rcx
  struct VMX_RECORD *DiskById; // rax
  struct VMX_RECORD *v5; // r14
  VMX_GLOBAL_DATA *v7; // rbp
  VMX_PHYSICAL_DISK *v8; // rbx
  VMX_DISK_DEVICE *v9; // r15
  int DriveGeometry; // esi
  VMX_NOTIFICATION_QUEUE *v11; // r10
  __int64 v12; // rdx
  __int64 v13; // rcx
  VMX_NOTIFICATION_QUEUE *v14; // rcx
  struct VMX_PACK *v15; // rcx
  struct VMX_PACK **v16; // rax
  unsigned int v17; // edx
  VMX_PHYSICAL_DISK *v18; // rcx
  VMX_PHYSICAL_DISK **v19; // rax
  unsigned int v20; // edx
  struct _DRIVE_LAYOUT_INFORMATION_EX *v21; // rdi
  PVOID P; // [rsp+20h] [rbp-58h] BYREF
  _DISK_GEOMETRY v23; // [rsp+28h] [rbp-50h] BYREF

  v3 = (VMX_CONFIG *)*((_QWORD *)this + 2);
  memset(&v23, 0, sizeof(v23));
  P = 0;
  DiskById = VMX_CONFIG::FindDiskById(v3, a2);
  v5 = DiskById;
  if ( !DiskById )
  {
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 3), 130, WPP_2f8af752156e3401cd435973c831895d_Traceguids, 3224895496LL);
    }
    return 3224895496LL;
  }
  v7 = Global;
  v8 = *(VMX_PHYSICAL_DISK **)(*((_QWORD *)DiskById + (*((_WORD *)DiskById + 32) & 1) + 5) + 128LL);
  v9 = (VMX_DISK_DEVICE *)*((_QWORD *)v8 + 2);
  DriveGeometry = VMX_DISK_DEVICE::GetDriveGeometry(v9, &v23);
  if ( DriveGeometry < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return (unsigned int)DriveGeometry;
    }
    v12 = 131;
    goto LABEL_12;
  }
  DriveGeometry = VMX_DISK_DEVICE::GetDriveLayoutEx(v9, (struct _DRIVE_LAYOUT_INFORMATION_EX **)&P);
  if ( DriveGeometry < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return (unsigned int)DriveGeometry;
    }
    v12 = 132;
LABEL_12:
    v13 = *((_QWORD *)v11 + 3);
LABEL_47:
    WPP_SF_d(v13, v12, WPP_2f8af752156e3401cd435973c831895d_Traceguids, (unsigned int)DriveGeometry);
    return (unsigned int)DriveGeometry;
  }
  (*((void (__fastcall **)(_QWORD, _QWORD))v7 + 18))(*((_QWORD *)v7 + 1), *((_QWORD *)v9 + 2));
  DriveGeometry = VMX_PHYSICAL_DISK::CreateBasicPartitions(v8, v5, &v23, (struct _DRIVE_LAYOUT_INFORMATION_EX *)P);
  ExFreePoolWithTag(P, 0);
  if ( DriveGeometry < 0 )
  {
    (*((void (__fastcall **)(_QWORD, _QWORD))v7 + 18))(*((_QWORD *)v7 + 1), 0);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return (unsigned int)DriveGeometry;
    }
    v12 = 133;
    goto LABEL_46;
  }
  DriveGeometry = VMX_DISK_DEVICE::GetDriveLayoutEx(v9, (struct _DRIVE_LAYOUT_INFORMATION_EX **)&P);
  if ( DriveGeometry < 0 )
  {
    VmxpRemovePhysicalDisk(v8);
    (*((void (__fastcall **)(_QWORD, _QWORD))v7 + 18))(*((_QWORD *)v7 + 1), 0);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return (unsigned int)DriveGeometry;
    }
    v12 = 134;
    goto LABEL_46;
  }
  DriveGeometry = VMX_PACK::BeginTransaction(this);
  if ( DriveGeometry < 0 )
    goto LABEL_40;
  DriveGeometry = VMX_PACK::RemoveVolumesTransaction(this, v5);
  if ( DriveGeometry < 0 )
  {
    VMX_PACK::AbortTransaction(this);
    goto LABEL_40;
  }
  DriveGeometry = VMX_PACK::CommitTransaction((struct VMX_CONFIG **)this, 1, 0);
  if ( DriveGeometry < 0 )
  {
LABEL_40:
    v21 = (struct _DRIVE_LAYOUT_INFORMATION_EX *)P;
    if ( (int)VMX_PHYSICAL_DISK::CreateDynamicPartitions(v8, v5, &v23, (struct _DRIVE_LAYOUT_INFORMATION_EX *)P) < 0 )
    {
      VMX_PHYSICAL_DISK::DeletePrivateRegion(v8, v21);
      VmxpRemovePhysicalDisk(v8);
    }
    ExFreePoolWithTag(v21, 0);
    (*((void (__fastcall **)(_QWORD, _QWORD))v7 + 18))(*((_QWORD *)v7 + 1), 0);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return (unsigned int)DriveGeometry;
    }
    v12 = 135;
LABEL_46:
    v13 = *((_QWORD *)v14 + 3);
    goto LABEL_47;
  }
  v15 = *(struct VMX_PACK **)this;
  if ( *(struct VMX_PACK **)(*(_QWORD *)this + 8LL) != this )
    goto LABEL_38;
  v16 = (struct VMX_PACK **)*((_QWORD *)this + 1);
  if ( *v16 != this )
    goto LABEL_38;
  *v16 = v15;
  *((_QWORD *)v15 + 1) = v16;
  VmxpSendPackDepartNotifications(this);
  VMX_PACK::`scalar deleting destructor'(this, v17);
  VMX_PHYSICAL_DISK::DeletePrivateRegion(v8, (struct _DRIVE_LAYOUT_INFORMATION_EX *)P);
  ExFreePoolWithTag(P, 0);
  (*((void (__fastcall **)(_QWORD, _QWORD))v7 + 18))(*((_QWORD *)v7 + 1), 0);
  v18 = *(VMX_PHYSICAL_DISK **)v8;
  if ( *(VMX_PHYSICAL_DISK **)(*(_QWORD *)v8 + 8LL) != v8
    || (v19 = (VMX_PHYSICAL_DISK **)*((_QWORD *)v8 + 1), *v19 != v8) )
  {
LABEL_38:
    __fastfail(3u);
  }
  *v19 = v18;
  *((_QWORD *)v18 + 1) = v19;
  VMX_NOTIFICATION_QUEUE::AddInvalidDiskNotification(*((_QWORD *)Global + 36), 2, v8);
  if ( v8 )
    VMX_PHYSICAL_DISK::`scalar deleting destructor'(v8, v20);
  return 0;
}

```

## disassembly

```asm
0x14002de54  mov     [rsp+arg_10], rbx
0x14002de59  push    rbp
0x14002de5a  push    rsi
0x14002de5b  push    rdi
0x14002de5c  push    r14
0x14002de5e  push    r15
0x14002de60  sub     rsp, 50h
0x14002de64  mov     rax, cs:__security_cookie
0x14002de6b  xor     rax, rsp
0x14002de6e  mov     [rsp+78h+var_38], rax
0x14002de73  xor     eax, eax
0x14002de75  mov     rdi, rcx
0x14002de78  mov     rcx, [rcx+10h]; this
0x14002de7c  xorps   xmm0, xmm0
0x14002de7f  movups  xmmword ptr [rsp+78h+var_50.Cylinders], xmm0
0x14002de84  mov     qword ptr [rsp+78h+var_50.SectorsPerTrack], rax
0x14002de89  mov     [rsp+78h+P], rax
0x14002de8e  call    ?FindDiskById@VMX_CONFIG@@QEAAPEAVVMX_RECORD@@PEAU_GUID@@@Z; VMX_CONFIG::FindDiskById(_GUID *)
0x14002de93  mov     r14, rax
0x14002de96  test    rax, rax
0x14002de99  jnz     short loc_14002DEE2
0x14002de9b  mov     r10, cs:WPP_GLOBAL_Control
0x14002dea2  lea     rax, WPP_GLOBAL_Control
0x14002dea9  mov     ebx, 0C0380008h
0x14002deae  cmp     r10, rax
0x14002deb1  jz      short loc_14002DEDB
0x14002deb3  mov     ecx, [r10+2Ch]
0x14002deb7  test    cl, 2
0x14002deba  jz      short loc_14002DEDB
0x14002debc  cmp     byte ptr [r10+29h], 2
0x14002dec1  jb      short loc_14002DEDB
0x14002dec3  mov     rcx, [r10+18h]
0x14002dec7  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x14002dece  mov     edx, 82h
0x14002ded3  mov     r9d, ebx
0x14002ded6  call    WPP_SF_d
0x14002dedb  mov     eax, ebx
0x14002dedd  jmp     loc_14002E207
0x14002dee2  movzx   eax, word ptr [rax+40h]
0x14002dee6  lea     rdx, [rsp+78h+var_50]; PVOID
0x14002deeb  mov     rbp, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14002def2  and     eax, 1
0x14002def5  mov     rax, [r14+rax*8+28h]
0x14002defa  mov     rbx, [rax+80h]
0x14002df01  mov     r15, [rbx+10h]
0x14002df05  mov     rcx, r15; this
0x14002df08  call    ?GetDriveGeometry@VMX_DISK_DEVICE@@QEAAJPEAU_DISK_GEOMETRY@@@Z; VMX_DISK_DEVICE::GetDriveGeometry(_DISK_GEOMETRY *)
0x14002df0d  mov     esi, eax
0x14002df0f  test    eax, eax
0x14002df11  jns     short loc_14002DF50
0x14002df13  mov     r10, cs:WPP_GLOBAL_Control
0x14002df1a  lea     rax, WPP_GLOBAL_Control
0x14002df21  cmp     r10, rax
0x14002df24  jz      loc_14002E205
0x14002df2a  mov     ecx, [r10+2Ch]
0x14002df2e  test    cl, 2
0x14002df31  jz      loc_14002E205
0x14002df37  cmp     byte ptr [r10+29h], 2
0x14002df3c  jb      loc_14002E205
0x14002df42  mov     edx, 83h
0x14002df47  mov     rcx, [r10+18h]
0x14002df4b  jmp     loc_14002E1F6
0x14002df50  lea     rdx, [rsp+78h+P]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x14002df55  mov     rcx, r15; this
0x14002df58  call    ?GetDriveLayoutEx@VMX_DISK_DEVICE@@QEAAJPEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_DISK_DEVICE::GetDriveLayoutEx(_DRIVE_LAYOUT_INFORMATION_EX * *)
0x14002df5d  mov     esi, eax
0x14002df5f  test    eax, eax
0x14002df61  jns     short loc_14002DF99
0x14002df63  mov     r10, cs:WPP_GLOBAL_Control
0x14002df6a  lea     rax, WPP_GLOBAL_Control
0x14002df71  cmp     r10, rax
0x14002df74  jz      loc_14002E205
0x14002df7a  mov     ecx, [r10+2Ch]
0x14002df7e  test    cl, 2
0x14002df81  jz      loc_14002E205
0x14002df87  cmp     byte ptr [r10+29h], 2
0x14002df8c  jb      loc_14002E205
0x14002df92  mov     edx, 84h
0x14002df97  jmp     short loc_14002DF47
0x14002df99  mov     rax, [rbp+90h]
0x14002dfa0  mov     rdx, [r15+10h]
0x14002dfa4  mov     rcx, [rbp+8]
0x14002dfa8  call    _guard_dispatch_icall
0x14002dfad  mov     r9, [rsp+78h+P]; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x14002dfb2  lea     r8, [rsp+78h+var_50]; struct _DISK_GEOMETRY *
0x14002dfb7  mov     rdx, r14; struct VMX_RECORD *
0x14002dfba  mov     rcx, rbx; this
0x14002dfbd  call    ?CreateBasicPartitions@VMX_PHYSICAL_DISK@@QEAAJPEAVVMX_RECORD@@PEAU_DISK_GEOMETRY@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_PHYSICAL_DISK::CreateBasicPartitions(VMX_RECORD *,_DISK_GEOMETRY *,_DRIVE_LAYOUT_INFORMATION_EX *)
0x14002dfc2  mov     rcx, [rsp+78h+P]; P
0x14002dfc7  xor     edx, edx; Tag
0x14002dfc9  mov     esi, eax
0x14002dfcb  call    cs:__imp_ExFreePoolWithTag
0x14002dfd2  nop     dword ptr [rax+rax+00h]
0x14002dfd7  test    esi, esi
0x14002dfd9  jns     short loc_14002E023
0x14002dfdb  mov     rax, [rbp+90h]
0x14002dfe2  xor     edx, edx
0x14002dfe4  mov     rcx, [rbp+8]
0x14002dfe8  call    _guard_dispatch_icall
0x14002dfed  mov     rcx, cs:WPP_GLOBAL_Control
0x14002dff4  lea     rax, WPP_GLOBAL_Control
0x14002dffb  cmp     rcx, rax
0x14002dffe  jz      loc_14002E205
0x14002e004  mov     eax, [rcx+2Ch]
0x14002e007  test    al, 2
0x14002e009  jz      loc_14002E205
0x14002e00f  cmp     byte ptr [rcx+29h], 2
0x14002e013  jb      loc_14002E205
0x14002e019  mov     edx, 85h
0x14002e01e  jmp     loc_14002E1F2
0x14002e023  lea     rdx, [rsp+78h+P]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x14002e028  mov     rcx, r15; this
0x14002e02b  call    ?GetDriveLayoutEx@VMX_DISK_DEVICE@@QEAAJPEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_DISK_DEVICE::GetDriveLayoutEx(_DRIVE_LAYOUT_INFORMATION_EX * *)
0x14002e030  mov     esi, eax
0x14002e032  test    eax, eax
0x14002e034  jns     short loc_14002E086
0x14002e036  mov     rcx, rbx; this
0x14002e039  call    ?VmxpRemovePhysicalDisk@@YAXPEAVVMX_PHYSICAL_DISK@@@Z; VmxpRemovePhysicalDisk(VMX_PHYSICAL_DISK *)
0x14002e03e  mov     rax, [rbp+90h]
0x14002e045  xor     edx, edx
0x14002e047  mov     rcx, [rbp+8]
0x14002e04b  call    _guard_dispatch_icall
0x14002e050  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e057  lea     rax, WPP_GLOBAL_Control
0x14002e05e  cmp     rcx, rax
0x14002e061  jz      loc_14002E205
0x14002e067  mov     eax, [rcx+2Ch]
0x14002e06a  test    al, 2
0x14002e06c  jz      loc_14002E205
0x14002e072  cmp     byte ptr [rcx+29h], 2
0x14002e076  jb      loc_14002E205
0x14002e07c  mov     edx, 86h
0x14002e081  jmp     loc_14002E1F2
0x14002e086  mov     rcx, rdi; this
0x14002e089  call    ?BeginTransaction@VMX_PACK@@QEAAJXZ; VMX_PACK::BeginTransaction(void)
0x14002e08e  mov     esi, eax
0x14002e090  test    eax, eax
0x14002e092  js      loc_14002E17B
0x14002e098  mov     rdx, r14; struct VMX_RECORD *
0x14002e09b  mov     rcx, rdi; this
0x14002e09e  call    ?RemoveVolumesTransaction@VMX_PACK@@QEAAJPEAVVMX_RECORD@@@Z; VMX_PACK::RemoveVolumesTransaction(VMX_RECORD *)
0x14002e0a3  mov     esi, eax
0x14002e0a5  mov     rcx, rdi; this
0x14002e0a8  test    eax, eax
0x14002e0aa  js      loc_14002E176
0x14002e0b0  xor     r8d, r8d; unsigned __int8
0x14002e0b3  mov     dl, 1; unsigned __int8
0x14002e0b5  call    ?CommitTransaction@VMX_PACK@@QEAAJEE@Z; VMX_PACK::CommitTransaction(uchar,uchar)
0x14002e0ba  mov     esi, eax
0x14002e0bc  test    eax, eax
0x14002e0be  js      loc_14002E17B
0x14002e0c4  mov     rcx, [rdi]
0x14002e0c7  cmp     [rcx+8], rdi
0x14002e0cb  jnz     loc_14002E16F
0x14002e0d1  mov     rax, [rdi+8]
0x14002e0d5  cmp     [rax], rdi
0x14002e0d8  jnz     loc_14002E16F
0x14002e0de  mov     [rax], rcx
0x14002e0e1  mov     [rcx+8], rax
0x14002e0e5  mov     rcx, rdi; struct VMX_PACK *
0x14002e0e8  call    ?VmxpSendPackDepartNotifications@@YAXPEAVVMX_PACK@@@Z; VmxpSendPackDepartNotifications(VMX_PACK *)
0x14002e0ed  mov     rcx, rdi; this
0x14002e0f0  call    ??_GVMX_PACK@@QEAAPEAXI@Z; VMX_PACK::`scalar deleting destructor'(uint)
0x14002e0f5  mov     rdx, [rsp+78h+P]; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x14002e0fa  mov     rcx, rbx; this
0x14002e0fd  call    ?DeletePrivateRegion@VMX_PHYSICAL_DISK@@QEAAXPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_PHYSICAL_DISK::DeletePrivateRegion(_DRIVE_LAYOUT_INFORMATION_EX *)
0x14002e102  mov     rcx, [rsp+78h+P]; P
0x14002e107  xor     edx, edx; Tag
0x14002e109  call    cs:__imp_ExFreePoolWithTag
0x14002e110  nop     dword ptr [rax+rax+00h]
0x14002e115  mov     rax, [rbp+90h]
0x14002e11c  xor     edx, edx
0x14002e11e  mov     rcx, [rbp+8]
0x14002e122  call    _guard_dispatch_icall
0x14002e127  mov     rcx, [rbx]
0x14002e12a  cmp     [rcx+8], rbx
0x14002e12e  jnz     short loc_14002E16F
0x14002e130  mov     rax, [rbx+8]
0x14002e134  cmp     [rax], rbx
0x14002e137  jnz     short loc_14002E16F
0x14002e139  mov     [rax], rcx
0x14002e13c  mov     r8, rbx
0x14002e13f  mov     [rcx+8], rax
0x14002e143  mov     edx, 2
0x14002e148  mov     rcx, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14002e14f  mov     rcx, [rcx+120h]
0x14002e156  call    ?AddInvalidDiskNotification@VMX_NOTIFICATION_QUEUE@@QEAAXW4_VM_NOTIFICATION_EVENT@@PEAVVMX_PHYSICAL_DISK@@@Z; VMX_NOTIFICATION_QUEUE::AddInvalidDiskNotification(_VM_NOTIFICATION_EVENT,VMX_PHYSICAL_DISK *)
0x14002e15b  test    rbx, rbx
0x14002e15e  jz      short loc_14002E168
0x14002e160  mov     rcx, rbx; this
0x14002e163  call    ??_GVMX_PHYSICAL_DISK@@QEAAPEAXI@Z; VMX_PHYSICAL_DISK::`scalar deleting destructor'(uint)
0x14002e168  xor     eax, eax
0x14002e16a  jmp     loc_14002E207
0x14002e16f  mov     ecx, 3
0x14002e174  int     29h; Win8: RtlFailFast(ecx)
0x14002e176  call    ?AbortTransaction@VMX_PACK@@QEAAXXZ; VMX_PACK::AbortTransaction(void)
0x14002e17b  mov     rdi, [rsp+78h+P]
0x14002e180  lea     r8, [rsp+78h+var_50]; struct _DISK_GEOMETRY *
0x14002e185  mov     r9, rdi; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x14002e188  mov     rdx, r14; struct VMX_RECORD *
0x14002e18b  mov     rcx, rbx; this
0x14002e18e  call    ?CreateDynamicPartitions@VMX_PHYSICAL_DISK@@QEAAJPEAVVMX_RECORD@@PEAU_DISK_GEOMETRY@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_PHYSICAL_DISK::CreateDynamicPartitions(VMX_RECORD *,_DISK_GEOMETRY *,_DRIVE_LAYOUT_INFORMATION_EX *)
0x14002e193  test    eax, eax
0x14002e195  jns     short loc_14002E1AA
0x14002e197  mov     rdx, rdi; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x14002e19a  mov     rcx, rbx; this
0x14002e19d  call    ?DeletePrivateRegion@VMX_PHYSICAL_DISK@@QEAAXPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_PHYSICAL_DISK::DeletePrivateRegion(_DRIVE_LAYOUT_INFORMATION_EX *)
0x14002e1a2  mov     rcx, rbx; this
0x14002e1a5  call    ?VmxpRemovePhysicalDisk@@YAXPEAVVMX_PHYSICAL_DISK@@@Z; VmxpRemovePhysicalDisk(VMX_PHYSICAL_DISK *)
0x14002e1aa  xor     edx, edx; Tag
0x14002e1ac  mov     rcx, rdi; P
0x14002e1af  call    cs:__imp_ExFreePoolWithTag
0x14002e1b6  nop     dword ptr [rax+rax+00h]
0x14002e1bb  mov     rax, [rbp+90h]
0x14002e1c2  xor     edx, edx
0x14002e1c4  mov     rcx, [rbp+8]
0x14002e1c8  call    _guard_dispatch_icall
0x14002e1cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e1d4  lea     rax, WPP_GLOBAL_Control
0x14002e1db  cmp     rcx, rax
0x14002e1de  jz      short loc_14002E205
0x14002e1e0  mov     eax, [rcx+2Ch]
0x14002e1e3  test    al, 2
0x14002e1e5  jz      short loc_14002E205
0x14002e1e7  cmp     byte ptr [rcx+29h], 2
0x14002e1eb  jb      short loc_14002E205
0x14002e1ed  mov     edx, 87h
0x14002e1f2  mov     rcx, [rcx+18h]
0x14002e1f6  mov     r9d, esi
0x14002e1f9  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x14002e200  call    WPP_SF_d
0x14002e205  mov     eax, esi
0x14002e207  mov     rcx, [rsp+78h+var_38]
0x14002e20c  xor     rcx, rsp; StackCookie
0x14002e20f  call    __security_check_cookie
0x14002e214  mov     rbx, [rsp+78h+arg_10]
0x14002e21c  add     rsp, 50h
0x14002e220  pop     r15
0x14002e222  pop     r14
0x14002e224  pop     rdi
0x14002e225  pop     rsi
0x14002e226  pop     rbp
0x14002e227  retn
```
