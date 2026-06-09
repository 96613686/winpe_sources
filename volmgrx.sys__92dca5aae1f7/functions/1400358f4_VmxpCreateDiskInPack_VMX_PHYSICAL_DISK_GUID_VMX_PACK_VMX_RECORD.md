# VmxpCreateDiskInPack(VMX_PHYSICAL_DISK *,_GUID *,VMX_PACK * *,VMX_RECORD * *)

- ea: `0x1400358f4`
- end: `0x140035e36`
- name: `?VmxpCreateDiskInPack@@YAJPEAVVMX_PHYSICAL_DISK@@PEAU_GUID@@PEAPEAVVMX_PACK@@PEAPEAVVMX_RECORD@@@Z`
- size: `1346`
- prototype: `__int64 __fastcall(struct VMX_PHYSICAL_DISK *, struct _GUID *, struct VMX_PACK **, struct VMX_RECORD **)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140030a04`

## callees

- `0x1400099d8`
- `0x14001b960`
- `0x14001b9a0`
- `0x14002a3f4`
- `0x14002b0c4`
- `0x14002d44c`
- `0x14002eab4`
- `0x14002eaf4`
- `0x14002fbf4`
- `0x140033278`
- `0x1400358f4`
- `0x14003acbc`
- `0x14003c244`
- `0x140044ac4`
- `0x140045798`
- `0x14004a70c`
- `0x14004a73c`
- `0x14004a88c`
- `0x14004ae60`
- `0x14004bac0`
- `0x1400532d4`
- `0x1400537c4`
- `0x1400557e4`
- `0x140055f34`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140035aa4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035c59`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035cba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035d36`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035d95`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035aa4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035c59`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035cba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035d36`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035d95`

## pseudocode

```c
__int64 __fastcall VmxpCreateDiskInPack(
        struct VMX_PHYSICAL_DISK *a1,
        struct _GUID *a2,
        struct VMX_PACK **a3,
        struct VMX_RECORD **a4)
{
  unsigned int v5; // ebx
  int v6; // r11d
  __int64 v7; // rcx
  __int64 v8; // rdx
  VMX_GLOBAL_DATA *v10; // r13
  _QWORD *v11; // rcx
  VMX_PACK *v12; // rbx
  int v13; // esi
  struct VMX_RECORD *v14; // r14
  int v15; // esi
  __int64 v16; // rax
  VMX_GLOBAL_DATA *v17; // rcx
  VMX_PACK *v18; // rcx
  VMX_NOTIFICATION_QUEUE *v19; // rcx
  __int64 v20; // rdx
  PVOID P; // [rsp+30h] [rbp-29h] BYREF
  VMX_PACK *v22; // [rsp+38h] [rbp-21h] BYREF
  struct VMX_RECORD *v23; // [rsp+40h] [rbp-19h] BYREF
  _QWORD *i; // [rsp+48h] [rbp-11h]
  struct VMX_PACK **v25; // [rsp+50h] [rbp-9h]
  struct VMX_RECORD **v26; // [rsp+58h] [rbp-1h]
  struct _DISK_GEOMETRY v27; // [rsp+60h] [rbp+7h] BYREF

  v26 = a4;
  *a3 = 0;
  v25 = a3;
  v22 = 0;
  P = 0;
  v23 = 0;
  memset(&v27, 0, sizeof(v27));
  *a4 = 0;
  v5 = VmxpValidatePackIdInput(a2, &v22);
  if ( (v5 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v7 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v8 = (unsigned int)(v6 + 101);
      goto LABEL_6;
    }
    return v5;
  }
  v10 = Global;
  v11 = (_QWORD *)(*((_QWORD *)a1 + 2) + 16LL);
  for ( i = v11; ; v11 = i )
  {
    (*((void (__fastcall **)(_QWORD, _QWORD))v10 + 18))(*((_QWORD *)v10 + 1), *v11);
    v12 = v22;
    v13 = VMX_PHYSICAL_DISK::CreatePrivateRegion(a1, v22, &v27, (struct _DRIVE_LAYOUT_INFORMATION_EX **)&P);
    if ( v13 < 0 )
    {
      (*((void (__fastcall **)(_QWORD, _QWORD))v10 + 18))(*((_QWORD *)v10 + 1), 0);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return (unsigned int)v13;
      }
      v20 = 102;
      goto LABEL_67;
    }
    v13 = VMX_PACK::OnlineConfigCopy((VMX_CONFIG **)v12, a1);
    if ( v13 < 0 )
    {
      VMX_PHYSICAL_DISK::DeletePrivateRegion(a1, (struct _DRIVE_LAYOUT_INFORMATION_EX *)P);
      ExFreePoolWithTag(P, 0);
      (*((void (__fastcall **)(_QWORD, _QWORD))v10 + 18))(*((_QWORD *)v10 + 1), 0);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return (unsigned int)v13;
      }
      v20 = 103;
      goto LABEL_67;
    }
    v13 = VMX_PACK::OnlineLogCopy((VMX_LOG **)v12, a1);
    if ( v13 < 0 )
    {
      VMX_PACK::OfflineLogCopy(v12, a1);
      VMX_PHYSICAL_DISK::DeletePrivateRegion(a1, (struct _DRIVE_LAYOUT_INFORMATION_EX *)P);
      ExFreePoolWithTag(P, 0);
      (*((void (__fastcall **)(_QWORD, _QWORD))v10 + 18))(*((_QWORD *)v10 + 1), 0);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return (unsigned int)v13;
      }
      v20 = 104;
LABEL_67:
      WPP_SF_d(*((_QWORD *)v19 + 3), v20, WPP_2f8af752156e3401cd435973c831895d_Traceguids, (unsigned int)v13);
      return (unsigned int)v13;
    }
    v13 = VMX_PACK::BeginTransaction(v12);
    if ( v13 >= 0 )
      break;
LABEL_18:
    VMX_PACK::OfflineLogCopy(v12, a1);
    VMX_PHYSICAL_DISK::DeletePrivateRegion(a1, (struct _DRIVE_LAYOUT_INFORMATION_EX *)P);
    ExFreePoolWithTag(P, 0);
    (*((void (__fastcall **)(_QWORD, _QWORD))v10 + 18))(*((_QWORD *)v10 + 1), 0);
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        105,
        WPP_2f8af752156e3401cd435973c831895d_Traceguids,
        (unsigned int)v13);
    }
    if ( v13 != -1070071728 && v13 != -1070071804 || VmxpRecoverPackConfigOnline(v12, &v22) < 0 )
      return (unsigned int)v13;
  }
  v13 = VMX_PACK::AddDiskTransaction(v12, a1, &v23);
  if ( v13 < 0
    || (v14 = v23,
        v13 = VMX_PACK::AddVolumesTransaction(v12, a1, &v27, (struct _DRIVE_LAYOUT_INFORMATION_EX *)P, v23),
        v13 < 0) )
  {
    VMX_PACK::AbortTransaction(v12);
    goto LABEL_18;
  }
  v13 = VMX_PACK::CommitTransaction((struct VMX_CONFIG **)v12, 0, 1);
  if ( v13 < 0 )
    goto LABEL_18;
  LODWORD(v22) = VMX_PHYSICAL_DISK::CreateDynamicPartitions(a1, v14, &v27, (struct _DRIVE_LAYOUT_INFORMATION_EX *)P);
  if ( (int)v22 >= 0 )
  {
    ExFreePoolWithTag(P, 0);
    (*((void (__fastcall **)(_QWORD, _QWORD))v10 + 18))(*((_QWORD *)v10 + 1), 0);
    if ( (int)VMX_PACK::BeginTransaction(v12) >= 0 )
    {
      if ( (int)VMX_PACK::AddVoterTransaction((struct VMX_TRANSACTION **)v12, v14) < 0 )
        VMX_PACK::AbortTransaction(v12);
      else
        VMX_PACK::CommitTransaction((struct VMX_CONFIG **)v12, 0, 1);
    }
    *v25 = v12;
    *v26 = v14;
    return 0;
  }
  VMX_PACK::OfflineLogCopy(v12, a1);
  v15 = VMX_PACK::BeginTransaction(v12);
  if ( v15 < 0 )
  {
LABEL_33:
    if ( *((_BYTE *)v12 + 56) )
    {
      v15 = VMX_PACK::BeginTransaction(v12);
      if ( v15 >= 0 )
      {
        v15 = VMX_PACK::RemoveVolumesTransaction(v12, v14);
        if ( v15 < 0 )
          VMX_PACK::AbortTransaction(v12);
        else
          v15 = VMX_PACK::CommitTransaction((struct VMX_CONFIG **)v12, 1, 0);
      }
    }
    if ( (*((_BYTE *)v14 + 64) & 1) != 0 )
      v16 = *((_QWORD *)v14 + 6);
    else
      v16 = *((_QWORD *)v14 + 5);
    v17 = Global;
    *(_QWORD *)(v16 + 128) = 0;
    VMX_NOTIFICATION_QUEUE::AddTaskNotification(*((_QWORD *)v17 + 36), 3, (__int64)v14, 0);
    VMX_NOTIFICATION_QUEUE::AddInvalidDiskNotification(*((_QWORD *)Global + 36), 1, a1);
    VMX_PACK::UpdateCounters(v12);
    if ( *((_BYTE *)v12 + 56) )
      VMX_PACK::OfflineDiskVolumes(v18, v14);
    if ( v15 >= 0 )
      goto LABEL_44;
    goto LABEL_45;
  }
  v15 = VMX_PACK::RemoveVolumesTransaction(v12, v14);
  if ( v15 < 0 || (v15 = VMX_PACK::RemoveDiskTransaction(v12, v14), v15 < 0) )
  {
    VMX_PACK::AbortTransaction(v12);
    goto LABEL_33;
  }
  v15 = VMX_PACK::CommitTransaction((struct VMX_CONFIG **)v12, 0, 1);
  if ( v15 < 0 )
    goto LABEL_33;
LABEL_44:
  VMX_PHYSICAL_DISK::DeletePrivateRegion(a1, (struct _DRIVE_LAYOUT_INFORMATION_EX *)P);
LABEL_45:
  ExFreePoolWithTag(P, 0);
  (*((void (__fastcall **)(_QWORD, _QWORD))v10 + 18))(*((_QWORD *)v10 + 1), 0);
  if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0 )
  {
    return (unsigned int)v22;
  }
  v5 = (unsigned int)v22;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    return v5;
  v7 = *((_QWORD *)WPP_GLOBAL_Control + 3);
  v8 = 106;
LABEL_6:
  WPP_SF_d(v7, v8, WPP_2f8af752156e3401cd435973c831895d_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x1400358f4  push    rbp
0x1400358f6  push    rbx
0x1400358f7  push    rsi
0x1400358f8  push    r13
0x1400358fa  push    r14
0x1400358fc  push    r15
0x1400358fe  lea     rbp, [rsp-2Fh]
0x140035903  sub     rsp, 88h
0x14003590a  mov     rax, cs:__security_cookie
0x140035911  xor     rax, rsp
0x140035914  mov     [rbp+57h+var_38], rax
0x140035918  xor     r11d, r11d
0x14003591b  mov     [rbp+57h+var_58], r9
0x14003591f  mov     r15, rcx
0x140035922  mov     [r8], r11
0x140035925  xor     ecx, ecx
0x140035927  mov     [rbp+57h+var_60], r8
0x14003592b  mov     rax, rdx
0x14003592e  mov     qword ptr [rbp+57h+var_50.SectorsPerTrack], rcx
0x140035932  xorps   xmm0, xmm0
0x140035935  mov     [rbp+57h+var_78], r11
0x140035939  mov     rcx, rax; struct _GUID *
0x14003593c  mov     [rbp+57h+P], r11
0x140035940  lea     rdx, [rbp+57h+var_78]; struct VMX_PACK **
0x140035944  mov     [rbp+57h+var_70], r11
0x140035948  movups  xmmword ptr [rbp+57h+var_50.Cylinders], xmm0
0x14003594c  mov     [r9], r11
0x14003594f  call    ?VmxpValidatePackIdInput@@YAJPEAU_GUID@@PEAPEAVVMX_PACK@@@Z; VmxpValidatePackIdInput(_GUID *,VMX_PACK * *)
0x140035954  mov     ebx, eax
0x140035956  test    eax, eax
0x140035958  jns     short loc_14003599B
0x14003595a  mov     r10, cs:WPP_GLOBAL_Control
0x140035961  lea     rax, WPP_GLOBAL_Control
0x140035968  cmp     r10, rax
0x14003596b  jz      short loc_140035994
0x14003596d  mov     ecx, [r10+2Ch]
0x140035971  test    cl, 2
0x140035974  jz      short loc_140035994
0x140035976  cmp     byte ptr [r10+29h], 2
0x14003597b  jb      short loc_140035994
0x14003597d  mov     rcx, [r10+18h]
0x140035981  lea     edx, [r11+65h]
0x140035985  mov     r9d, ebx
0x140035988  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x14003598f  call    WPP_SF_d
0x140035994  mov     eax, ebx
0x140035996  jmp     loc_140035E18
0x14003599b  mov     rcx, [r15+10h]
0x14003599f  lea     r14, WPP_GLOBAL_Control
0x1400359a6  mov     r13, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x1400359ad  add     rcx, 10h
0x1400359b1  mov     [rbp+57h+var_68], rcx
0x1400359b5  mov     rdx, [rcx]
0x1400359b8  mov     rcx, [r13+8]
0x1400359bc  mov     rax, [r13+90h]
0x1400359c3  call    _guard_dispatch_icall
0x1400359c8  mov     rbx, [rbp+57h+var_78]
0x1400359cc  lea     r9, [rbp+57h+P]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x1400359d0  mov     rdx, rbx; struct VMX_PACK *
0x1400359d3  lea     r8, [rbp+57h+var_50]; struct _DISK_GEOMETRY *
0x1400359d7  mov     rcx, r15; this
0x1400359da  call    ?CreatePrivateRegion@VMX_PHYSICAL_DISK@@QEAAJPEAVVMX_PACK@@PEAU_DISK_GEOMETRY@@PEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_PHYSICAL_DISK::CreatePrivateRegion(VMX_PACK *,_DISK_GEOMETRY *,_DRIVE_LAYOUT_INFORMATION_EX * *)
0x1400359df  mov     esi, eax
0x1400359e1  test    eax, eax
0x1400359e3  js      loc_140035DD3
0x1400359e9  mov     rdx, r15; struct VMX_PHYSICAL_DISK *
0x1400359ec  mov     rcx, rbx; this
0x1400359ef  call    ?OnlineConfigCopy@VMX_PACK@@QEAAJPEAVVMX_PHYSICAL_DISK@@@Z; VMX_PACK::OnlineConfigCopy(VMX_PHYSICAL_DISK *)
0x1400359f4  mov     esi, eax
0x1400359f6  test    eax, eax
0x1400359f8  js      loc_140035D83
0x1400359fe  mov     rdx, r15; struct VMX_PHYSICAL_DISK *
0x140035a01  mov     rcx, rbx; this
0x140035a04  call    ?OnlineLogCopy@VMX_PACK@@QEAAJPEAVVMX_PHYSICAL_DISK@@@Z; VMX_PACK::OnlineLogCopy(VMX_PHYSICAL_DISK *)
0x140035a09  mov     esi, eax
0x140035a0b  mov     rcx, rbx; this
0x140035a0e  test    eax, eax
0x140035a10  js      loc_140035D1C
0x140035a16  call    ?BeginTransaction@VMX_PACK@@QEAAJXZ; VMX_PACK::BeginTransaction(void)
0x140035a1b  mov     esi, eax
0x140035a1d  test    eax, eax
0x140035a1f  js      short loc_140035A87
0x140035a21  lea     r8, [rbp+57h+var_70]; struct VMX_RECORD **
0x140035a25  mov     rdx, r15; struct VMX_PHYSICAL_DISK *
0x140035a28  mov     rcx, rbx; this
0x140035a2b  call    ?AddDiskTransaction@VMX_PACK@@QEAAJPEAVVMX_PHYSICAL_DISK@@PEAPEAVVMX_RECORD@@@Z; VMX_PACK::AddDiskTransaction(VMX_PHYSICAL_DISK *,VMX_RECORD * *)
0x140035a30  mov     esi, eax
0x140035a32  test    eax, eax
0x140035a34  js      short loc_140035A7F
0x140035a36  mov     r14, [rbp+57h+var_70]
0x140035a3a  lea     r8, [rbp+57h+var_50]; struct _DISK_GEOMETRY *
0x140035a3e  mov     r9, [rbp+57h+P]; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x140035a42  mov     rdx, r15; struct VMX_PHYSICAL_DISK *
0x140035a45  mov     rcx, rbx; this
0x140035a48  mov     [rsp+0B0h+var_90], r14; struct VMX_RECORD *
0x140035a4d  call    ?AddVolumesTransaction@VMX_PACK@@QEAAJPEAVVMX_PHYSICAL_DISK@@PEAU_DISK_GEOMETRY@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAVVMX_RECORD@@@Z; VMX_PACK::AddVolumesTransaction(VMX_PHYSICAL_DISK *,_DISK_GEOMETRY *,_DRIVE_LAYOUT_INFORMATION_EX *,VMX_RECORD *)
0x140035a52  mov     esi, eax
0x140035a54  test    eax, eax
0x140035a56  js      short loc_140035A78
0x140035a58  mov     r8b, 1; unsigned __int8
0x140035a5b  xor     edx, edx; unsigned __int8
0x140035a5d  mov     rcx, rbx; this
0x140035a60  call    ?CommitTransaction@VMX_PACK@@QEAAJEE@Z; VMX_PACK::CommitTransaction(uchar,uchar)
0x140035a65  mov     esi, eax
0x140035a67  test    eax, eax
0x140035a69  jns     loc_140035B24
0x140035a6f  lea     r14, WPP_GLOBAL_Control
0x140035a76  jmp     short loc_140035A87
0x140035a78  lea     r14, WPP_GLOBAL_Control
0x140035a7f  mov     rcx, rbx; this
0x140035a82  call    ?AbortTransaction@VMX_PACK@@QEAAXXZ; VMX_PACK::AbortTransaction(void)
0x140035a87  mov     rdx, r15; struct VMX_PHYSICAL_DISK *
0x140035a8a  mov     rcx, rbx; this
0x140035a8d  call    ?OfflineLogCopy@VMX_PACK@@QEAAXPEAVVMX_PHYSICAL_DISK@@@Z; VMX_PACK::OfflineLogCopy(VMX_PHYSICAL_DISK *)
0x140035a92  mov     rdx, [rbp+57h+P]; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x140035a96  mov     rcx, r15; this
0x140035a99  call    ?DeletePrivateRegion@VMX_PHYSICAL_DISK@@QEAAXPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_PHYSICAL_DISK::DeletePrivateRegion(_DRIVE_LAYOUT_INFORMATION_EX *)
0x140035a9e  mov     rcx, [rbp+57h+P]; P
0x140035aa2  xor     edx, edx; Tag
0x140035aa4  call    cs:__imp_ExFreePoolWithTag
0x140035aab  nop     dword ptr [rax+rax+00h]
0x140035ab0  mov     rax, [r13+90h]
0x140035ab7  xor     edx, edx
0x140035ab9  mov     rcx, [r13+8]
0x140035abd  call    _guard_dispatch_icall
0x140035ac2  mov     rcx, cs:WPP_GLOBAL_Control
0x140035ac9  cmp     rcx, r14
0x140035acc  jz      short loc_140035AF3
0x140035ace  mov     eax, [rcx+2Ch]
0x140035ad1  test    al, 2
0x140035ad3  jz      short loc_140035AF3
0x140035ad5  cmp     byte ptr [rcx+29h], 2
0x140035ad9  jb      short loc_140035AF3
0x140035adb  mov     rcx, [rcx+18h]
0x140035adf  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x140035ae6  mov     edx, 69h ; 'i'
0x140035aeb  mov     r9d, esi
0x140035aee  call    WPP_SF_d
0x140035af3  cmp     esi, 0C0380050h
0x140035af9  jz      short loc_140035B07
0x140035afb  cmp     esi, 0C0380004h
0x140035b01  jnz     loc_140035E16
0x140035b07  lea     rdx, [rbp+57h+var_78]; struct VMX_PACK **
0x140035b0b  mov     rcx, rbx; struct VMX_PACK *
0x140035b0e  call    ?VmxpRecoverPackConfigOnline@@YAJPEAVVMX_PACK@@PEAPEAV1@@Z; VmxpRecoverPackConfigOnline(VMX_PACK *,VMX_PACK * *)
0x140035b13  test    eax, eax
0x140035b15  js      loc_140035E16
0x140035b1b  mov     rcx, [rbp+57h+var_68]
0x140035b1f  jmp     loc_1400359B5
0x140035b24  mov     r9, [rbp+57h+P]; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x140035b28  lea     r8, [rbp+57h+var_50]; struct _DISK_GEOMETRY *
0x140035b2c  mov     rdx, r14; struct VMX_RECORD *
0x140035b2f  mov     rcx, r15; this
0x140035b32  call    ?CreateDynamicPartitions@VMX_PHYSICAL_DISK@@QEAAJPEAVVMX_RECORD@@PEAU_DISK_GEOMETRY@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_PHYSICAL_DISK::CreateDynamicPartitions(VMX_RECORD *,_DISK_GEOMETRY *,_DRIVE_LAYOUT_INFORMATION_EX *)
0x140035b37  mov     dword ptr [rbp+57h+var_78], eax
0x140035b3a  test    eax, eax
0x140035b3c  jns     loc_140035CB4
0x140035b42  mov     rdx, r15; struct VMX_PHYSICAL_DISK *
0x140035b45  mov     rcx, rbx; this
0x140035b48  call    ?OfflineLogCopy@VMX_PACK@@QEAAXPEAVVMX_PHYSICAL_DISK@@@Z; VMX_PACK::OfflineLogCopy(VMX_PHYSICAL_DISK *)
0x140035b4d  mov     rcx, rbx; this
0x140035b50  call    ?BeginTransaction@VMX_PACK@@QEAAJXZ; VMX_PACK::BeginTransaction(void)
0x140035b55  mov     esi, eax
0x140035b57  test    eax, eax
0x140035b59  js      short loc_140035B9E
0x140035b5b  mov     rdx, r14; struct VMX_RECORD *
0x140035b5e  mov     rcx, rbx; this
0x140035b61  call    ?RemoveVolumesTransaction@VMX_PACK@@QEAAJPEAVVMX_RECORD@@@Z; VMX_PACK::RemoveVolumesTransaction(VMX_RECORD *)
0x140035b66  mov     esi, eax
0x140035b68  test    eax, eax
0x140035b6a  js      short loc_140035B96
0x140035b6c  mov     rdx, r14; struct VMX_RECORD *
0x140035b6f  mov     rcx, rbx; this
0x140035b72  call    ?RemoveDiskTransaction@VMX_PACK@@QEAAJPEAVVMX_RECORD@@@Z; VMX_PACK::RemoveDiskTransaction(VMX_RECORD *)
0x140035b77  mov     esi, eax
0x140035b79  test    eax, eax
0x140035b7b  js      short loc_140035B96
0x140035b7d  mov     r8b, 1; unsigned __int8
0x140035b80  xor     edx, edx; unsigned __int8
0x140035b82  mov     rcx, rbx; this
0x140035b85  call    ?CommitTransaction@VMX_PACK@@QEAAJEE@Z; VMX_PACK::CommitTransaction(uchar,uchar)
0x140035b8a  mov     esi, eax
0x140035b8c  test    eax, eax
0x140035b8e  jns     loc_140035C47
0x140035b94  jmp     short loc_140035B9E
0x140035b96  mov     rcx, rbx; this
0x140035b99  call    ?AbortTransaction@VMX_PACK@@QEAAXXZ; VMX_PACK::AbortTransaction(void)
0x140035b9e  cmp     byte ptr [rbx+38h], 0
0x140035ba2  jz      short loc_140035BD9
0x140035ba4  mov     rcx, rbx; this
0x140035ba7  call    ?BeginTransaction@VMX_PACK@@QEAAJXZ; VMX_PACK::BeginTransaction(void)
0x140035bac  mov     esi, eax
0x140035bae  test    eax, eax
0x140035bb0  js      short loc_140035BD9
0x140035bb2  mov     rdx, r14; struct VMX_RECORD *
0x140035bb5  mov     rcx, rbx; this
0x140035bb8  call    ?RemoveVolumesTransaction@VMX_PACK@@QEAAJPEAVVMX_RECORD@@@Z; VMX_PACK::RemoveVolumesTransaction(VMX_RECORD *)
0x140035bbd  mov     esi, eax
0x140035bbf  mov     rcx, rbx; this
0x140035bc2  test    eax, eax
0x140035bc4  js      short loc_140035BD4
0x140035bc6  xor     r8d, r8d; unsigned __int8
0x140035bc9  mov     dl, 1; unsigned __int8
0x140035bcb  call    ?CommitTransaction@VMX_PACK@@QEAAJEE@Z; VMX_PACK::CommitTransaction(uchar,uchar)
0x140035bd0  mov     esi, eax
0x140035bd2  jmp     short loc_140035BD9
0x140035bd4  call    ?AbortTransaction@VMX_PACK@@QEAAXXZ; VMX_PACK::AbortTransaction(void)
0x140035bd9  test    byte ptr [r14+40h], 1
0x140035bde  jz      short loc_140035BE6
0x140035be0  mov     rax, [r14+30h]
0x140035be4  jmp     short loc_140035BEA
0x140035be6  mov     rax, [r14+28h]
0x140035bea  mov     rcx, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x140035bf1  xor     r9d, r9d
0x140035bf4  mov     qword ptr [rax+80h], 0
0x140035bff  mov     r8, r14
0x140035c02  mov     rcx, [rcx+120h]
0x140035c09  lea     edx, [r9+3]
0x140035c0d  call    ?AddTaskNotification@VMX_NOTIFICATION_QUEUE@@QEAAXW4_VM_NOTIFICATION_EVENT@@PEAVVMX_RECORD@@PEAU_GUID@@@Z; VMX_NOTIFICATION_QUEUE::AddTaskNotification(_VM_NOTIFICATION_EVENT,VMX_RECORD *,_GUID *)
0x140035c12  mov     rcx, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x140035c19  mov     r8, r15
0x140035c1c  mov     edx, 1
0x140035c21  mov     rcx, [rcx+120h]
0x140035c28  call    ?AddInvalidDiskNotification@VMX_NOTIFICATION_QUEUE@@QEAAXW4_VM_NOTIFICATION_EVENT@@PEAVVMX_PHYSICAL_DISK@@@Z; VMX_NOTIFICATION_QUEUE::AddInvalidDiskNotification(_VM_NOTIFICATION_EVENT,VMX_PHYSICAL_DISK *)
0x140035c2d  mov     rcx, rbx; this
0x140035c30  call    ?UpdateCounters@VMX_PACK@@QEAAXXZ; VMX_PACK::UpdateCounters(void)
0x140035c35  cmp     byte ptr [rbx+38h], 0
0x140035c39  jz      short loc_140035C43
0x140035c3b  mov     rdx, r14; struct VMX_RECORD *
0x140035c3e  call    ?OfflineDiskVolumes@VMX_PACK@@QEAAXPEAVVMX_RECORD@@@Z; VMX_PACK::OfflineDiskVolumes(VMX_RECORD *)
0x140035c43  test    esi, esi
0x140035c45  js      short loc_140035C53
0x140035c47  mov     rdx, [rbp+57h+P]; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x140035c4b  mov     rcx, r15; this
0x140035c4e  call    ?DeletePrivateRegion@VMX_PHYSICAL_DISK@@QEAAXPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_PHYSICAL_DISK::DeletePrivateRegion(_DRIVE_LAYOUT_INFORMATION_EX *)
0x140035c53  mov     rcx, [rbp+57h+P]; P
0x140035c57  xor     edx, edx; Tag
0x140035c59  call    cs:__imp_ExFreePoolWithTag
0x140035c60  nop     dword ptr [rax+rax+00h]
0x140035c65  mov     rax, [r13+90h]
0x140035c6c  xor     edx, edx
0x140035c6e  mov     rcx, [r13+8]
0x140035c72  call    _guard_dispatch_icall
0x140035c77  mov     rcx, cs:WPP_GLOBAL_Control
0x140035c7e  lea     rax, WPP_GLOBAL_Control
0x140035c85  cmp     rcx, rax
0x140035c88  jz      short loc_140035CAC
0x140035c8a  mov     eax, [rcx+2Ch]
0x140035c8d  test    al, 2
0x140035c8f  jz      short loc_140035CAC
0x140035c91  cmp     byte ptr [rcx+29h], 2
0x140035c95  mov     ebx, dword ptr [rbp+57h+var_78]
0x140035c98  jb      loc_140035994
0x140035c9e  mov     rcx, [rcx+18h]
0x140035ca2  mov     edx, 6Ah ; 'j'
0x140035ca7  jmp     loc_140035985
0x140035cac  mov     ebx, dword ptr [rbp+57h+var_78]
0x140035caf  jmp     loc_140035994
0x140035cb4  mov     rcx, [rbp+57h+P]; P
0x140035cb8  xor     edx, edx; Tag
0x140035cba  call    cs:__imp_ExFreePoolWithTag
0x140035cc1  nop     dword ptr [rax+rax+00h]
0x140035cc6  mov     rax, [r13+90h]
0x140035ccd  xor     edx, edx
0x140035ccf  mov     rcx, [r13+8]
0x140035cd3  call    _guard_dispatch_icall
0x140035cd8  mov     rcx, rbx; this
0x140035cdb  call    ?BeginTransaction@VMX_PACK@@QEAAJXZ; VMX_PACK::BeginTransaction(void)
0x140035ce0  test    eax, eax
0x140035ce2  js      short loc_140035D07
0x140035ce4  mov     rdx, r14; struct VMX_RECORD *
0x140035ce7  mov     rcx, rbx; this
0x140035cea  call    ?AddVoterTransaction@VMX_PACK@@QEAAJPEAVVMX_RECORD@@@Z; VMX_PACK::AddVoterTransaction(VMX_RECORD *)
0x140035cef  mov     rcx, rbx; this
0x140035cf2  test    eax, eax
0x140035cf4  js      short loc_140035D02
0x140035cf6  mov     r8b, 1; unsigned __int8
0x140035cf9  xor     edx, edx; unsigned __int8
0x140035cfb  call    ?CommitTransaction@VMX_PACK@@QEAAJEE@Z; VMX_PACK::CommitTransaction(uchar,uchar)
0x140035d00  jmp     short loc_140035D07
0x140035d02  call    ?AbortTransaction@VMX_PACK@@QEAAXXZ; VMX_PACK::AbortTransaction(void)
0x140035d07  mov     rax, [rbp+57h+var_60]
0x140035d0b  mov     [rax], rbx
0x140035d0e  mov     rax, [rbp+57h+var_58]
0x140035d12  mov     [rax], r14
0x140035d15  xor     eax, eax
0x140035d17  jmp     loc_140035E18
0x140035d1c  mov     rdx, r15; struct VMX_PHYSICAL_DISK *
0x140035d1f  call    ?OfflineLogCopy@VMX_PACK@@QEAAXPEAVVMX_PHYSICAL_DISK@@@Z; VMX_PACK::OfflineLogCopy(VMX_PHYSICAL_DISK *)
0x140035d24  mov     rdx, [rbp+57h+P]; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x140035d28  mov     rcx, r15; this
0x140035d2b  call    ?DeletePrivateRegion@VMX_PHYSICAL_DISK@@QEAAXPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_PHYSICAL_DISK::DeletePrivateRegion(_DRIVE_LAYOUT_INFORMATION_EX *)
0x140035d30  mov     rcx, [rbp+57h+P]; P
0x140035d34  xor     edx, edx; Tag
0x140035d36  call    cs:__imp_ExFreePoolWithTag
0x140035d3d  nop     dword ptr [rax+rax+00h]
0x140035d42  mov     rax, [r13+90h]
0x140035d49  xor     edx, edx
0x140035d4b  mov     rcx, [r13+8]
0x140035d4f  call    _guard_dispatch_icall
  ... truncated ...
```
