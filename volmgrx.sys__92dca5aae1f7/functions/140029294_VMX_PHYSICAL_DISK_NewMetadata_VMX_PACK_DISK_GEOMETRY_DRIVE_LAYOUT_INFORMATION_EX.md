# VMX_PHYSICAL_DISK::NewMetadata(VMX_PACK *,_DISK_GEOMETRY *,_DRIVE_LAYOUT_INFORMATION_EX * *)

- ea: `0x140029294`
- end: `0x14002a3ee`
- name: `?NewMetadata@VMX_PHYSICAL_DISK@@AEAAJPEAVVMX_PACK@@PEAU_DISK_GEOMETRY@@PEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z`
- size: `4442`
- prototype: `__int64 __fastcall(VMX_PHYSICAL_DISK *__hidden this, struct VMX_PACK *, struct _DISK_GEOMETRY *, struct _DRIVE_LAYOUT_INFORMATION_EX **)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x140045798`

## callees

- `0x140005f80`
- `0x1400097c0`
- `0x1400099d8`
- `0x14001b960`
- `0x14001be80`
- `0x140029294`
- `0x140033854`
- `0x140033958`
- `0x140033c48`
- `0x1400452a4`
- `0x140045c98`
- `0x140045ce0`
- `0x140047924`
- `0x140048fa0`
- `0x14005c600`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140029ec1`
- `ntoskrnl!ExAllocatePool2` at `0x140029f41`
- `ntoskrnl!ExAllocatePool2` at `0x140029ec1`
- `ntoskrnl!ExAllocatePool2` at `0x140029f41`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400295ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002967a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400296d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029799`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400297e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002999d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029a9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029b08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029b6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029bc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029c6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029e6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029ee5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029f65`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a04a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a0d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a1d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a220`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a27f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a2d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a307`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a35f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400295ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002967a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400296d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029799`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400297e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002999d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029a9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029b08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029b6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029bc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029c6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029e6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029ee5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029f65`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a04a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a0d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a1d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a220`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a27f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a2d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a307`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a35f`
- `ntoskrnl!ExUuidCreate` at `0x140029c53`
- `ntoskrnl!ExUuidCreate` at `0x140029c53`

## pseudocode

```c
__int64 __fastcall VMX_PHYSICAL_DISK::NewMetadata(
        VMX_PHYSICAL_DISK *this,
        struct VMX_PACK *a2,
        struct _DISK_GEOMETRY *a3,
        struct _DRIVE_LAYOUT_INFORMATION_EX **a4)
{
  __int64 v4; // rax
  VMX_DISK_DEVICE *v6; // rcx
  unsigned int DriveGeometry; // edi
  VMX_NOTIFICATION_QUEUE *v9; // r10
  __int64 v10; // rdx
  unsigned __int64 v11; // r15
  VMX_DISK_DEVICE *v12; // r8
  DWORD SectorsPerTrack; // ebx
  struct _DRIVE_LAYOUT_INFORMATION_EX *v15; // rdi
  __int64 v16; // r9
  LARGE_INTEGER StartingUsableOffset; // r15
  LARGE_INTEGER v18; // rbx
  unsigned int v19; // r12d
  unsigned __int64 v20; // r14
  unsigned __int64 v21; // rdx
  __int64 m; // r10
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  unsigned __int64 v28; // rcx
  LARGE_INTEGER v29; // r8
  LARGE_INTEGER v30; // r11
  __int64 n; // r10
  __int64 v32; // rax
  LARGE_INTEGER v33; // r8
  LARGE_INTEGER v34; // rcx
  VMX_NOTIFICATION_QUEUE *v35; // r10
  __int64 v36; // rdx
  int MetadataPartition; // r14d
  VMX_NOTIFICATION_QUEUE *v38; // r10
  __int64 v39; // rdx
  __int64 v40; // r13
  unsigned __int64 v41; // r13
  unsigned __int64 v42; // rcx
  _WORD *v43; // rax
  _WORD *v44; // r12
  VMX_NOTIFICATION_QUEUE *v45; // r10
  __int64 v46; // rdx
  unsigned int v47; // r12d
  unsigned int PartitionCount; // r14d
  unsigned __int64 v49; // r11
  __int64 v50; // r9
  __int64 v51; // rcx
  __int64 v52; // rbx
  char v53; // al
  unsigned __int8 v54; // al
  __int64 i; // r8
  __int64 v56; // rcx
  __int64 v57; // rdx
  unsigned __int64 v58; // rdx
  void *v59; // r10
  __int64 v60; // rdx
  unsigned __int64 QuadPart; // r8
  unsigned int PartitionType; // ecx
  int v63; // ebx
  __int64 v64; // rbx
  LARGE_INTEGER StartingOffset; // rcx
  void *v66; // r9
  unsigned __int64 v67; // rbx
  unsigned __int64 v68; // r11
  __int64 j; // r9
  unsigned __int64 v70; // rdx
  __int64 v71; // rax
  unsigned __int64 v72; // r10
  VMX_NOTIFICATION_QUEUE *v73; // r10
  __int64 v74; // rdx
  unsigned __int64 v75; // r12
  unsigned __int64 v76; // rax
  __int64 v77; // rcx
  unsigned __int64 v78; // rdx
  unsigned int v79; // ebx
  __int64 v80; // r8
  unsigned __int64 v81; // r8
  unsigned __int64 v82; // rax
  __int64 v83; // rcx
  __int64 v84; // rax
  _QWORD *v85; // rax
  _QWORD *v86; // rdx
  _QWORD *v87; // rdx
  _BYTE *v88; // rax
  _BYTE *v89; // r14
  __int64 v90; // rcx
  struct VMX_TOC_ENTRY *v91; // rdx
  int inserted; // r15d
  __int64 v93; // rax
  __int64 k; // rcx
  _BYTE *v95; // rax
  _BYTE *v96; // r15
  struct VMX_TOC_ENTRY *v97; // rdx
  VMX_LOG_COPY *v98; // rax
  unsigned __int8 v99[8]; // [rsp+20h] [rbp-59h] BYREF
  unsigned __int64 v100; // [rsp+28h] [rbp-51h]
  unsigned int v101; // [rsp+30h] [rbp-49h]
  PVOID P; // [rsp+38h] [rbp-41h] BYREF
  unsigned __int64 v103; // [rsp+40h] [rbp-39h]
  unsigned __int64 v104; // [rsp+48h] [rbp-31h]
  __int64 v105; // [rsp+50h] [rbp-29h]
  unsigned __int64 v106; // [rsp+58h] [rbp-21h] BYREF
  struct _DRIVE_LAYOUT_INFORMATION_EX **v107; // [rsp+60h] [rbp-19h]
  _OWORD v108[2]; // [rsp+68h] [rbp-11h] BYREF

  v4 = *((_QWORD *)a2 + 2);
  v6 = (VMX_DISK_DEVICE *)*((_QWORD *)this + 2);
  v106 = 0;
  v107 = a4;
  v105 = *(_QWORD *)(v4 + 8);
  P = 0;
  v99[0] = 0;
  DriveGeometry = VMX_DISK_DEVICE::GetDriveGeometry(v6, a3);
  if ( (DriveGeometry & 0x80000000) != 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return DriveGeometry;
    }
    v10 = 31;
LABEL_23:
    WPP_SF_d(*((_QWORD *)v9 + 3), v10, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids, DriveGeometry);
    return DriveGeometry;
  }
  v11 = *(unsigned int *)(*((_QWORD *)this + 2) + 36LL);
  v101 = v11;
  if ( a3->BytesPerSector != (_DWORD)v11 )
  {
    v9 = WPP_GLOBAL_Control;
    DriveGeometry = -1073741823;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return DriveGeometry;
    }
    v10 = 32;
    goto LABEL_23;
  }
  if ( !VmxpSupportedBytesPerSector(v11) )
  {
    v9 = WPP_GLOBAL_Control;
    DriveGeometry = -1070071787;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return DriveGeometry;
    }
    v10 = 33;
    goto LABEL_23;
  }
  DriveGeometry = VMX_DISK_DEVICE::IsSupported(v12, v99);
  if ( (DriveGeometry & 0x80000000) != 0 )
  {
LABEL_19:
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return DriveGeometry;
    }
    v10 = 34;
    goto LABEL_23;
  }
  if ( !v99[0] )
  {
    DriveGeometry = -1073741637;
    goto LABEL_19;
  }
  DriveGeometry = VMX_DISK_DEVICE::GetLengthInfo(*((VMX_DISK_DEVICE **)this + 2), &v106);
  if ( (DriveGeometry & 0x80000000) != 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return DriveGeometry;
    }
    v10 = 35;
    goto LABEL_23;
  }
  SectorsPerTrack = a3->SectorsPerTrack;
  v103 = v11;
  v104 = v106 / v11;
  LODWORD(v100) = SectorsPerTrack;
  while ( 2 )
  {
    DriveGeometry = VMX_DISK_DEVICE::GetDriveLayoutEx(
                      *((VMX_DISK_DEVICE **)this + 2),
                      (struct _DRIVE_LAYOUT_INFORMATION_EX **)&P);
    if ( (DriveGeometry & 0x80000000) != 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return DriveGeometry;
      }
      v10 = 36;
      goto LABEL_23;
    }
    v15 = (struct _DRIVE_LAYOUT_INFORMATION_EX *)P;
    *((_DWORD *)this + 6) = *(_DWORD *)P;
    if ( !v15->PartitionStyle )
    {
      v47 = 0;
      *((_DWORD *)this + 7) = v15->Mbr.Signature;
      PartitionCount = v15->PartitionCount;
      v49 = 0;
      memset(v108, 0, sizeof(v108));
      v50 = 0;
      v51 = 0x100000201LL;
      do
      {
        if ( (unsigned int)v50 >= PartitionCount )
          break;
        v52 = (__int64)&v15->PartitionEntry[v50];
        v53 = *(_BYTE *)(v52 + 32);
        if ( v53 != -96 && v53 != -124 && v53 != 39 && v53 != 18 )
        {
          v54 = v53 + 34;
          if ( v54 > 0x20u || !_bittest64(&v51, v54) )
            continue;
        }
        for ( i = 0; (unsigned int)i < v47; i = (unsigned int)(i + 1) )
        {
          if ( *(_QWORD *)(*((_QWORD *)v108 + i) + 8LL) > *(_QWORD *)(v52 + 8) )
            break;
        }
        v56 = v47;
        if ( v47 > (unsigned int)i )
        {
          do
          {
            v57 = (unsigned int)(v56 - 1);
            *((_QWORD *)v108 + v56) = *((_QWORD *)v108 + v57);
            v56 = v57;
          }
          while ( (unsigned int)v57 > (unsigned int)i );
        }
        ++v47;
        v58 = v15->PartitionEntry[v50].StartingOffset.QuadPart + v15->PartitionEntry[v50].PartitionLength.QuadPart;
        v51 = 0x100000201LL;
        *((_QWORD *)v108 + i) = v52;
        if ( v58 > v49 )
          v49 = v58;
        v50 = (unsigned int)(v50 + 1);
      }
      while ( (unsigned int)v50 < 4 );
      v59 = 0;
      P = 0;
      v41 = v104 * v103;
      v60 = 0;
      QuadPart = v104 * v103;
      while ( (unsigned int)v60 < PartitionCount )
      {
        PartitionType = v15->PartitionEntry[v60].Mbr.PartitionType;
        if ( (unsigned __int8)PartitionType > 0xFu || (v63 = 32801, !_bittest(&v63, PartitionType)) )
        {
          if ( (_BYTE)PartitionType != 0xA0
            && (_BYTE)PartitionType != 0x84
            && (_BYTE)PartitionType != 39
            && (_BYTE)PartitionType != 18
            && ((unsigned __int8)(PartitionType + 34) > 0x20u
             || (v64 = 0x100000201LL, !_bittest64(&v64, PartitionType + 34)))
            || (unsigned int)v60 >= 4 )
          {
            if ( (_BYTE)PartitionType == 66 )
            {
              ExFreePoolWithTag(v15, 0);
              v38 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
              {
                v39 = 37;
LABEL_133:
                WPP_SF_d(*((_QWORD *)v38 + 3), v39, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids, 3224895495LL);
              }
              return 3224895495LL;
            }
            StartingOffset = v15->PartitionEntry[v60].StartingOffset;
            v66 = (void *)(StartingOffset.QuadPart + v15->PartitionEntry[v60].PartitionLength.QuadPart);
            if ( StartingOffset.QuadPart >= QuadPart )
              StartingOffset.QuadPart = QuadPart;
            QuadPart = StartingOffset.QuadPart;
            if ( v66 > v59 )
            {
              v59 = v66;
              P = v66;
            }
          }
        }
        v60 = (unsigned int)(v60 + 1);
      }
      if ( v41 <= 0x100000 || v41 < v49 + 0x100000 || v41 < (unsigned __int64)v59 + 0x100000 )
      {
        ExFreePoolWithTag(v15, 0);
        v45 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
        {
          return 3224895507LL;
        }
        v46 = 38;
LABEL_255:
        WPP_SF_d(*((_QWORD *)v45 + 3), v46, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids, 3224895507LL);
        return 3224895507LL;
      }
      v67 = v41 - 0x100000;
      v68 = v103 * (unsigned int)v100;
      StartingUsableOffset.QuadPart = 0;
      v100 = v41 - 0x100000;
      v20 = 0;
      for ( j = 0; ; j = (unsigned int)(j + 1) )
      {
        if ( (unsigned int)j > v47 )
          goto LABEL_153;
        if ( (_DWORD)j )
        {
          v71 = *((_QWORD *)v108 + (unsigned int)(j - 1));
          v70 = *(_QWORD *)(v71 + 8) + *(_QWORD *)(v71 + 16);
        }
        else
        {
          v70 = v68;
          if ( v68 >= QuadPart )
            v70 = QuadPart;
        }
        if ( (_DWORD)j == v47 )
          v72 = v41 - 0x100000;
        else
          v72 = *(_QWORD *)(*((_QWORD *)v108 + j) + 8LL);
        if ( QuadPart >= v67 )
        {
          if ( v72 - v70 >= v20 - StartingUsableOffset.QuadPart )
          {
            StartingUsableOffset.QuadPart = v70;
            v20 = v72;
          }
        }
        else if ( QuadPart < v72 )
        {
          if ( QuadPart < v70 || (unsigned __int64)P > v72 )
          {
            ExFreePoolWithTag(v15, 0);
            v35 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
            {
              v36 = 39;
LABEL_165:
              WPP_SF_d(*((_QWORD *)v35 + 3), v36, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids, 3224895500LL);
            }
            return 3224895500LL;
          }
          StartingUsableOffset.QuadPart = v70;
          v20 = v72;
LABEL_153:
          if ( StartingUsableOffset.QuadPart == v20 )
          {
            ExFreePoolWithTag(v15, 0);
            v45 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
            {
              v46 = 40;
              goto LABEL_255;
            }
            return 3224895507LL;
          }
          if ( v20 < v67 )
          {
            ExFreePoolWithTag(v15, 0);
            v45 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
            {
              return 3224895507LL;
            }
            v46 = 41;
            goto LABEL_255;
          }
LABEL_86:
          v42 = v103;
          *((_QWORD *)this + 8) = (v41 - v103) / v103;
          *((_QWORD *)this + 9) = (v41 - 98304) / v42;
          *((_QWORD *)this + 10) = v15->PartitionStyle == 0 ? 6 : 0;
          v43 = (_WORD *)VMX_ALLOCATED_OBJECT::operator new(312, 258, 1749314902);
          v44 = v43;
          if ( v43 )
            memset(v43, 0, 0x138u);
          else
            v44 = 0;
          *((_QWORD *)this + 11) = v44;
          if ( v44 )
          {
            *v44 = 2;
            v75 = v100;
            *(_WORD *)(*((_QWORD *)this + 11) + 2LL) = 12;
            v76 = v75 / v103;
            v77 = *((_QWORD *)this + 11);
            v78 = *((_QWORD *)this + 8) - v75 / v103;
            v104 = v75 / v103;
            *(_QWORD *)(v77 + 24) = v78;
            *(_QWORD *)(*((_QWORD *)this + 11) + 32LL) = *((_QWORD *)this + 9) - v76;
            LODWORD(v100) = ExUuidCreate((UUID *)(*((_QWORD *)this + 11) + 40LL));
            if ( (v100 & 0x80000000) != 0LL )
            {
              ExFreePoolWithTag(v15, 0);
              if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0 )
              {
                return (unsigned int)v100;
              }
              else
              {
                v79 = v100;
                if ( *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 3),
                    48,
                    WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids,
                    (unsigned int)v100);
              }
              return v79;
            }
            v80 = v105;
            *(_OWORD *)(*((_QWORD *)this + 11) + 56LL) = HOSTID_DEFAULT_GUID;
            *(_OWORD *)(*((_QWORD *)this + 11) + 72LL) = *(_OWORD *)(v80 + 8);
            RtlStringCbCopyA((NTSTRSAFE_PSTR)(*((_QWORD *)this + 11) + 88LL), 0x20u, (NTSTRSAFE_PCSTR)(v80 + 24));
            v81 = v101;
            v82 = StartingUsableOffset.QuadPart / (unsigned __int64)v101;
            *(_DWORD *)(*((_QWORD *)this + 11) + 120LL) = v101;
            *(_DWORD *)(*((_QWORD *)this + 11) + 124LL) = 0;
            *(_QWORD *)(*((_QWORD *)this + 11) + 136LL) = v82;
            *(_QWORD *)(*((_QWORD *)this + 11) + 144LL) = (v20 - StartingUsableOffset.QuadPart) / v81;
            *(_QWORD *)(*((_QWORD *)this + 11) + 152LL) = v104;
            *(_QWORD *)(*((_QWORD *)this + 11) + 160LL) = (v41 - v75) / v81;
            *(_QWORD *)(*((_QWORD *)this + 11) + 168LL) = 0x400 / (unsigned int)v81;
            *(_QWORD *)(*((_QWORD *)this + 11) + 176LL) = 0xFFA00 / (unsigned int)v81;
            v83 = *((_QWORD *)this + 11);
            v84 = *(_QWORD *)(v83 + 176);
            if ( v84 == *(_QWORD *)(v83 + 24) )
              *(_QWORD *)(v83 + 176) = v84 - 1;
            *(_DWORD *)(*((_QWORD *)this + 11) + 184LL) = 1;
            *(_DWORD *)(*((_QWORD *)this + 11) + 188LL) = 1;
            *(_QWORD *)(*((_QWORD *)this + 11) + 192LL) = ((int)v81 + 758271) / (unsigned int)v81;
            *(_QWORD *)(*((_QWORD *)this + 11) + 200LL) = ((int)v81 + 114687) / (unsigned int)v81;
            *(_DWORD *)(*((_QWORD *)this + 11) + 208LL) = *((_DWORD *)Global + 62);
            v85 = (_QWORD *)VMX_ALLOCATED_OBJECT::operator new(72, 258, 1666477398);
            if ( v85 )
            {
              *v85 = 0;
              v85[1] = 0;
              v85[2] = 0;
              v85[4] = v85 + 3;
              v85[3] = v85 + 3;
              v85[6] = v85 + 5;
              v85[5] = v85 + 5;
              v85[8] = v85 + 7;
              v85[7] = v85 + 7;
            }
            else
            {
              v85 = 0;
            }
            *((_QWORD *)this + 12) = v85;
            if ( v85 )
            {
              *(_DWORD *)v85 = 1;
              *(_QWORD *)(*((_QWORD *)this + 12) + 8LL) = ExAllocatePool2(258, 8, 538996054);
              v86 = *(_QWORD **)(*((_QWORD *)this + 12) + 8LL);
              if ( v86 )
              {
                *v86 = *(_QWORD *)(*((_QWORD *)this + 11) + 168LL);
                *(_QWORD *)(*((_QWORD *)this + 12) + 16LL) = ExAllocatePool2(258, 8, 538996054);
                v87 = *(_QWORD **)(*((_QWORD *)this + 12) + 16LL);
                if ( v87 )
                {
                  *v87 = *(_QWORD *)(*((_QWORD *)this + 11) + 176LL);
                  v88 = (_BYTE *)VMX_ALLOCATED_OBJECT::operator new(64, 258, 1700031830);
                  v89 = v88;
                  if ( v88 )
                  {
                    memset(v88, 0, 0x40u);
                    v89[32] = 1;
                    *((_WORD *)v89 + 17) = 0;
                    v90 = 0x2200 / v101;
                    *((_QWORD *)v89 + 5) = v90;
                    if ( v90 == *(_QWORD *)(*((_QWORD *)this + 11) + 168LL) )
                      *((_QWORD *)v89 + 5) = v90 + 1;
                    *((_QWORD *)v89 + 6) = *(_QWORD *)(*((_QWORD *)this + 11) + 192LL);
                    *((_WORD *)v89 + 28) = 1;
                    *((_DWORD *)v89 + 15) = 0;
                    VMX_TOC::InsertEntry(*((VMX_TOC **)this + 12), (struct VMX_TOC_ENTRY *)v89);
                    inserted = VMX_TOC::InsertEntryInCopy(*((VMX_TOC **)this + 12), v91);
                    if ( inserted < 0 )
                    {
                      ExFreePoolWithTag(v15, 0);
                      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
                      {
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 3),
                          53,
                          WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids,
                          (unsigned int)inserted);
                      }
                      return (unsigned int)inserted;
                    }
                    v93 = VMX_ALLOCATED_OBJECT::operator new(40, 258, 1665363286);
                    if ( v93 )
                    {
                      *(_OWORD *)v93 = 0;
                      *(_OWORD *)(v93 + 16) = 0;
                      *(_QWORD *)(v93 + 32) = 0;
                    }
                    else
                    {
                      v93 = 0;
                    }
                    *((_QWORD *)this + 13) = v93;
                    if ( v93 )
                    {
                      *(_QWORD *)v93 = this;
                      *(_QWORD *)(*((_QWORD *)this + 13) + 8LL) = *(_QWORD *)(*((_QWORD *)this + 12) + 40LL);
                      for ( k = 0; k != 4; ++k )
                        *(_BYTE *)(k + *((_QWORD *)this + 13) + 16) = 0;
                      *(_WORD *)(*((_QWORD *)this + 13) + 20LL) = 6;
                      *(_QWORD *)(*((_QWORD *)this + 13) + 24LL) = 0;
                      *(_QWORD *)(*((_QWORD *)this + 13) + 32LL) = 0;
                      v95 = (_BYTE *)VMX_ALLOCATED_OBJECT::operator new(64, 258, 1700031830);
                      v96 = v95;
                      if ( v95 )
                      {
                        memset(v95, 0, 0x40u);
                        v96[32] = 2;
                        *((_WORD *)v96 + 17) = 0;
                        *((_QWORD *)v96 + 5) = *((_QWORD *)v89 + 5) + *((_QWORD *)v89 + 6);
                        *((_QWORD *)v96 + 6) = *(_QWORD *)(*((_QWORD *)this + 11) + 200LL);
                        *((_WORD *)v96 + 28) = 1;
                        *((_DWORD *)v96 + 15) = 0;
                        VMX_TOC::InsertEntry(*((VMX_TOC **)this + 12), (struct VMX_TOC_ENTRY *)v96);
                        MetadataPartition = VMX_TOC::InsertEntryInCopy(*((VMX_TOC **)this + 12), v97);
                        if ( MetadataPartition < 0 )
                        {
                          ExFreePoolWithTag(v15, 0);
                          return (unsigned int)MetadataPartition;
                        }
                        v98 = (VMX_LOG_COPY *)VMX_ALLOCATED_OBJECT::operator new(48, 66, 1665953110);
                        if ( v98 )
                        {
                          *(_OWORD *)v98 = 0;
                          *((_OWORD *)v98 + 1) = 0;
                          *((_OWORD *)v98 + 2) = 0;
                        }
                        else
                        {
                          v98 = 0;
                        }
                        *((_QWORD *)this + 14) = v98;
                        if ( v98 )
                        {
                          if ( (int)VMX_LOG_COPY::Initialize(
                                      v98,
                                      this,
                                      *(struct VMX_COPY **)(*((_QWORD *)this + 12) + 56LL)) >= 0 )
                          {
                            *v107 = v15;
                            return 0;
                          }
                          ExFreePoolWithTag(v15, 0);
                          v73 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                            || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
                            || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
                          {
                            return 3221225626LL;
                          }
                          v74 = 57;
                        }
                        else
                        {
                          ExFreePoolWithTag(v15, 0);
                          v73 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                            || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
                            || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
                          {
                            return 3221225626LL;
                          }
                          v74 = 56;
                        }
                      }
                      else
                      {
                        ExFreePoolWithTag(v15, 0);
                        v73 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
                          || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
                        {
                          return 3221225626LL;
                        }
                        v74 = 55;
                      }
                    }
                    else
                    {
                      ExFreePoolWithTag(v15, 0);
                      v73 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
                        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
                      {
                        return 3221225626LL;
                      }
                      v74 = 54;
                    }
                  }
                  else
                  {
                    ExFreePoolWithTag(v15, 0);
                    v73 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
                    {
                      return 3221225626LL;
                    }
                    v74 = 52;
                  }
                }
                else
                {
                  ExFreePoolWithTag(v15, 0);
                  v73 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
                  {
                    return 3221225626LL;
                  }
                  v74 = 51;
                }
              }
              else
              {
                ExFreePoolWithTag(v15, 0);
                v73 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
                {
                  return 3221225626LL;
                }
                v74 = 50;
              }
            }
            else
            {
              ExFreePoolWithTag(v15, 0);
              v73 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
              {
                return 3221225626LL;
              }
              v74 = 49;
            }
LABEL_249:
            WPP_SF_d(*((_QWORD *)v73 + 3), v74, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids, 3221225626LL);
          }
          else
          {
            ExFreePoolWithTag(v15, 0);
            v73 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
            {
              v74 = 47;
              goto LABEL_249;
            }
          }
          return 3221225626LL;
        }
      }
    }
    if ( v15->PartitionStyle != 1 )
    {
      ExFreePoolWithTag(v15, 0);
      v9 = WPP_GLOBAL_Control;
      DriveGeometry = -1070071754;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return DriveGeometry;
      }
      v10 = 46;
      goto LABEL_23;
    }
    v16 = 0;
    *(_OWORD *)((char *)this + 28) = *(_OWORD *)&v15->Mbr.Signature;
    StartingUsableOffset = v15->Gpt.StartingUsableOffset;
    v18 = StartingUsableOffset;
    v19 = v15->PartitionCount;
    v20 = StartingUsableOffset.QuadPart + v15->Gpt.UsableLength.QuadPart;
    v21 = v20;
    for ( m = 0; (unsigned int)m < v19; m = (unsigned int)(m + 1) )
    {
      v23 = m;
      v24 = (__int64)&v15->PartitionEntry[m];
      v25 = *(_QWORD *)&v15->PartitionEntry[m].Mbr - *(_QWORD *)&PARTITION_LDM_METADATA_GUID.Data1;
      if ( !v25 )
        v25 = *(_QWORD *)v15->PartitionEntry[v23].Gpt.PartitionType.Data4 - *(_QWORD *)PARTITION_LDM_METADATA_GUID.Data4;
      if ( v25 )
      {
        v26 = *(_QWORD *)&v15->PartitionEntry[v23].Mbr - *(_QWORD *)&PARTITION_LDM_DATA_GUID.Data1;
        if ( !v26 )
          v26 = *(_QWORD *)v15->PartitionEntry[v23].Gpt.PartitionType.Data4 - *(_QWORD *)PARTITION_LDM_DATA_GUID.Data4;
        if ( !v26 )
        {
          ExFreePoolWithTag(v15, 0);
          v38 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
          {
            v39 = 42;
            goto LABEL_133;
          }
          return 3224895495LL;
        }
        v27 = *(_QWORD *)&v15->PartitionEntry[v23].Mbr - *(_QWORD *)&PARTITION_BASIC_DATA_GUID.Data1;
        if ( !v27 )
          v27 = *(_QWORD *)v15->PartitionEntry[v23].Gpt.PartitionType.Data4 - *(_QWORD *)PARTITION_BASIC_DATA_GUID.Data4;
        if ( !v27 )
        {
          v28 = *(_QWORD *)(v24 + 8);
          v29.QuadPart = v28 + *(_QWORD *)(v24 + 16);
          if ( v28 >= v21 )
            v28 = v21;
          v21 = v28;
          if ( v29.QuadPart > (unsigned __int64)v18.QuadPart )
            v18 = v29;
        }
      }
      else
      {
        if ( v16 )
          v24 = v16;
        v16 = v24;
      }
    }
    v30.QuadPart = v21;
    if ( v18.QuadPart >= v21 )
      v30 = v18;
    for ( n = 0; (unsigned int)n < v19; n = (unsigned int)(n + 1) )
    {
      v32 = *(_QWORD *)&v15->PartitionEntry[n].Mbr - *(_QWORD *)&PARTITION_BASIC_DATA_GUID.Data1;
      if ( !v32 )
        v32 = *(_QWORD *)v15->PartitionEntry[n].Gpt.PartitionType.Data4 - *(_QWORD *)PARTITION_BASIC_DATA_GUID.Data4;
      if ( v32 )
      {
        v33 = v15->PartitionEntry[n].StartingOffset;
        v34.QuadPart = v33.QuadPart + v15->PartitionEntry[n].PartitionLength.QuadPart;
        if ( v33.QuadPart >= (unsigned __int64)v30.QuadPart )
        {
          if ( v34.QuadPart > v21 )
            goto LABEL_70;
        }
        else if ( v34.QuadPart > v21 )
        {
          ExFreePoolWithTag(v15, 0);
          v35 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
          {
            v36 = 43;
            goto LABEL_165;
          }
          return 3224895500LL;
        }
        if ( v34.QuadPart > (unsigned __int64)StartingUsableOffset.QuadPart )
          StartingUsableOffset.QuadPart = v33.QuadPart + v15->PartitionEntry[n].PartitionLength.QuadPart;
        if ( v33.QuadPart >= (unsigned __int64)v30.QuadPart )
        {
LABEL_70:
          if ( v33.QuadPart < v20 )
            v20 = v15->PartitionEntry[n].StartingOffset.QuadPart;
          continue;
        }
      }
    }
    if ( StartingUsableOffset.QuadPart == v20 )
    {
      ExFreePoolWithTag(v15, 0);
      v45 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v46 = 44;
        goto LABEL_255;
      }
      return 3224895507LL;
    }
    if ( v16 )
    {
      v40 = *(_QWORD *)(v16 + 16);
      v100 = *(_QWORD *)(v16 + 8);
      v41 = v100 + v40;
      goto LABEL_86;
    }
    MetadataPartition = VMX_PHYSICAL_DISK::CreateMetadataPartition(this, v15);
    ExFreePoolWithTag(v15, 0);
    if ( MetadataPartition >= 0 )
      continue;
    break;
  }
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      45,
      WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids,
      (unsigned int)MetadataPartition);
  }
  return (unsigned int)MetadataPartition;
}

```

## disassembly

```asm
0x140029294  push    rbp
0x140029296  push    rbx
0x140029297  push    rsi
0x140029298  push    rdi
0x140029299  push    r12
0x14002929b  push    r13
0x14002929d  push    r14
0x14002929f  push    r15
0x1400292a1  lea     rbp, [rsp-1Fh]
0x1400292a6  sub     rsp, 98h
0x1400292ad  mov     rax, cs:__security_cookie
0x1400292b4  xor     rax, rsp
0x1400292b7  mov     [rbp+57h+var_48], rax
0x1400292bb  mov     rax, [rdx+10h]
0x1400292bf  mov     rsi, rcx
0x1400292c2  mov     rcx, [rcx+10h]; this
0x1400292c6  mov     rdx, r8; PVOID
0x1400292c9  mov     [rbp+57h+var_78], 0
0x1400292d1  mov     rbx, r8
0x1400292d4  mov     [rbp+57h+var_70], r9
0x1400292d8  mov     rax, [rax+8]
0x1400292dc  mov     [rbp+57h+var_80], rax
0x1400292e0  mov     [rbp+57h+P], 0
0x1400292e8  mov     [rbp+57h+var_B0], 0
0x1400292ec  call    ?GetDriveGeometry@VMX_DISK_DEVICE@@QEAAJPEAU_DISK_GEOMETRY@@@Z; VMX_DISK_DEVICE::GetDriveGeometry(_DISK_GEOMETRY *)
0x1400292f1  mov     edi, eax
0x1400292f3  test    eax, eax
0x1400292f5  jns     short loc_140029332
0x1400292f7  mov     r10, cs:WPP_GLOBAL_Control
0x1400292fe  lea     rcx, WPP_GLOBAL_Control
0x140029305  cmp     r10, rcx
0x140029308  jz      loc_140029418
0x14002930e  mov     edx, [r10+2Ch]
0x140029312  test    dl, 10h
0x140029315  jz      loc_140029418
0x14002931b  mov     ebx, 2
0x140029320  cmp     [r10+29h], bl
0x140029324  jb      loc_140029418
0x14002932a  lea     edx, [rbx+1Dh]
0x14002932d  jmp     loc_140029405
0x140029332  mov     r8, [rsi+10h]
0x140029336  mov     r15d, [r8+24h]
0x14002933a  mov     [rbp+57h+var_A0], r15d
0x14002933e  cmp     [rbx+14h], r15d
0x140029342  jz      short loc_140029383
0x140029344  mov     r10, cs:WPP_GLOBAL_Control
0x14002934b  lea     rcx, WPP_GLOBAL_Control
0x140029352  mov     edi, 0C0000001h
0x140029357  cmp     r10, rcx
0x14002935a  jz      loc_140029418
0x140029360  mov     eax, [r10+2Ch]
0x140029364  test    al, 10h
0x140029366  jz      loc_140029418
0x14002936c  mov     ebx, 2
0x140029371  cmp     [r10+29h], bl
0x140029375  jb      loc_140029418
0x14002937b  lea     edx, [rbx+1Eh]
0x14002937e  jmp     loc_140029405
0x140029383  mov     ecx, r15d; unsigned int
0x140029386  call    ?VmxpSupportedBytesPerSector@@YAEK@Z; VmxpSupportedBytesPerSector(ulong)
0x14002938b  test    al, al
0x14002938d  jnz     short loc_1400293BF
0x14002938f  mov     r10, cs:WPP_GLOBAL_Control
0x140029396  lea     rcx, WPP_GLOBAL_Control
0x14002939d  mov     edi, 0C0380015h
0x1400293a2  cmp     r10, rcx
0x1400293a5  jz      short loc_140029418
0x1400293a7  mov     eax, [r10+2Ch]
0x1400293ab  test    al, 10h
0x1400293ad  jz      short loc_140029418
0x1400293af  mov     ebx, 2
0x1400293b4  cmp     [r10+29h], bl
0x1400293b8  jb      short loc_140029418
0x1400293ba  lea     edx, [rbx+1Fh]
0x1400293bd  jmp     short loc_140029405
0x1400293bf  lea     rdx, [rbp+57h+var_B0]; unsigned __int8 *
0x1400293c3  mov     rcx, r8; this
0x1400293c6  call    ?IsSupported@VMX_DISK_DEVICE@@QEAAJPEAE@Z; VMX_DISK_DEVICE::IsSupported(uchar *)
0x1400293cb  mov     edi, eax
0x1400293cd  test    eax, eax
0x1400293cf  js      short loc_1400293DC
0x1400293d1  cmp     [rbp+57h+var_B0], 0
0x1400293d5  jnz     short loc_14002943B
0x1400293d7  mov     edi, 0C00000BBh
0x1400293dc  mov     r10, cs:WPP_GLOBAL_Control
0x1400293e3  lea     rcx, WPP_GLOBAL_Control
0x1400293ea  cmp     r10, rcx
0x1400293ed  jz      short loc_140029418
0x1400293ef  mov     eax, [r10+2Ch]
0x1400293f3  test    al, 10h
0x1400293f5  jz      short loc_140029418
0x1400293f7  mov     ebx, 2
0x1400293fc  cmp     [r10+29h], bl
0x140029400  jb      short loc_140029418
0x140029402  lea     edx, [rbx+20h]
0x140029405  mov     rcx, [r10+18h]
0x140029409  lea     r8, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids
0x140029410  mov     r9d, edi
0x140029413  call    WPP_SF_d
0x140029418  mov     eax, edi
0x14002941a  mov     rcx, [rbp+57h+var_48]
0x14002941e  xor     rcx, rsp; StackCookie
0x140029421  call    __security_check_cookie
0x140029426  add     rsp, 98h
0x14002942d  pop     r15
0x14002942f  pop     r14
0x140029431  pop     r13
0x140029433  pop     r12
0x140029435  pop     rdi
0x140029436  pop     rsi
0x140029437  pop     rbx
0x140029438  pop     rbp
0x140029439  retn
0x14002943b  mov     rcx, [rsi+10h]; this
0x14002943f  lea     rdx, [rbp+57h+var_78]; PVOID
0x140029443  call    ?GetLengthInfo@VMX_DISK_DEVICE@@QEAAJPEAU_GET_LENGTH_INFORMATION@@@Z; VMX_DISK_DEVICE::GetLengthInfo(_GET_LENGTH_INFORMATION *)
0x140029448  mov     edi, eax
0x14002944a  test    eax, eax
0x14002944c  jns     short loc_14002947A
0x14002944e  mov     r10, cs:WPP_GLOBAL_Control
0x140029455  lea     rcx, WPP_GLOBAL_Control
0x14002945c  cmp     r10, rcx
0x14002945f  jz      short loc_140029418
0x140029461  mov     edx, [r10+2Ch]
0x140029465  test    dl, 10h
0x140029468  jz      short loc_140029418
0x14002946a  mov     ebx, 2
0x14002946f  cmp     [r10+29h], bl
0x140029473  jb      short loc_140029418
0x140029475  lea     edx, [rbx+21h]
0x140029478  jmp     short loc_140029405
0x14002947a  mov     rax, [rbp+57h+var_78]
0x14002947e  xor     edx, edx
0x140029480  mov     ebx, [rbx+10h]
0x140029483  div     r15
0x140029486  mov     [rbp+57h+var_90], r15
0x14002948a  mov     [rbp+57h+var_88], rax
0x14002948e  mov     dword ptr [rbp+57h+var_A8], ebx
0x140029491  mov     r15d, 1
0x140029497  mov     rcx, [rsi+10h]; this
0x14002949b  lea     rdx, [rbp+57h+P]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x14002949f  call    ?GetDriveLayoutEx@VMX_DISK_DEVICE@@QEAAJPEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_DISK_DEVICE::GetDriveLayoutEx(_DRIVE_LAYOUT_INFORMATION_EX * *)
0x1400294a4  mov     edi, eax
0x1400294a6  test    eax, eax
0x1400294a8  js      loc_14002A3B4
0x1400294ae  mov     rdi, [rbp+57h+P]
0x1400294b2  mov     eax, [rdi]
0x1400294b4  mov     [rsi+18h], eax
0x1400294b7  mov     eax, [rdi]
0x1400294b9  test    eax, eax
0x1400294bb  jz      loc_14002982F
0x1400294c1  cmp     eax, r15d
0x1400294c4  jnz     loc_1400297DF
0x1400294ca  movups  xmm0, xmmword ptr [rdi+8]
0x1400294ce  xor     r9d, r9d
0x1400294d1  movdqu  xmmword ptr [rsi+1Ch], xmm0
0x1400294d6  mov     r15, [rdi+18h]
0x1400294da  mov     r14, [rdi+20h]
0x1400294de  mov     rbx, r15
0x1400294e1  mov     r12d, [rdi+4]
0x1400294e5  add     r14, r15
0x1400294e8  mov     r13, qword ptr cs:PARTITION_BASIC_DATA_GUID.Data4
0x1400294ef  mov     rdx, r14
0x1400294f2  xor     r10d, r10d
0x1400294f5  cmp     r10d, r12d
0x1400294f8  jnb     loc_14002959B
0x1400294fe  lea     rcx, [r10+r10*8]
0x140029502  shl     rcx, 4
0x140029506  lea     r8, [rdi+30h]
0x14002950a  add     r8, rcx
0x14002950d  mov     rax, [rcx+rdi+50h]
0x140029512  sub     rax, qword ptr cs:PARTITION_LDM_METADATA_GUID.Data1
0x140029519  jnz     short loc_140029527
0x14002951b  mov     rax, [rcx+rdi+58h]
0x140029520  sub     rax, qword ptr cs:PARTITION_LDM_METADATA_GUID.Data4
0x140029527  test    rax, rax
0x14002952a  jnz     short loc_140029538
0x14002952c  test    r9, r9
0x14002952f  cmovnz  r8, r9
0x140029533  mov     r9, r8
0x140029536  jmp     short loc_140029593
0x140029538  mov     rax, [rcx+rdi+50h]
0x14002953d  sub     rax, qword ptr cs:PARTITION_LDM_DATA_GUID.Data1
0x140029544  jnz     short loc_140029552
0x140029546  mov     rax, [rcx+rdi+58h]
0x14002954b  sub     rax, qword ptr cs:PARTITION_LDM_DATA_GUID.Data4
0x140029552  test    rax, rax
0x140029555  jz      loc_1400296D3
0x14002955b  mov     rax, [rcx+rdi+50h]
0x140029560  sub     rax, qword ptr cs:PARTITION_BASIC_DATA_GUID.Data1
0x140029567  jnz     short loc_140029571
0x140029569  mov     rax, [rcx+rdi+58h]
0x14002956e  sub     rax, r13
0x140029571  test    rax, rax
0x140029574  jnz     short loc_140029593
0x140029576  mov     rcx, [r8+8]
0x14002957a  mov     r8, [r8+10h]
0x14002957e  add     r8, rcx
0x140029581  cmp     rcx, rdx
0x140029584  cmovnb  rcx, rdx
0x140029588  mov     rdx, rcx
0x14002958b  cmp     r8, rbx
0x14002958e  jbe     short loc_140029593
0x140029590  mov     rbx, r8
0x140029593  inc     r10d
0x140029596  jmp     loc_1400294F5
0x14002959b  cmp     rbx, rdx
0x14002959e  mov     r11, rdx
0x1400295a1  cmovnb  r11, rbx
0x1400295a5  xor     r10d, r10d
0x1400295a8  cmp     r10d, r12d
0x1400295ab  jnb     loc_140029655
0x1400295b1  lea     rcx, [r10+r10*8]
0x1400295b5  add     rcx, rcx
0x1400295b8  mov     rax, [rdi+rcx*8+50h]
0x1400295bd  sub     rax, qword ptr cs:PARTITION_BASIC_DATA_GUID.Data1
0x1400295c4  jnz     short loc_1400295CE
0x1400295c6  mov     rax, [rdi+rcx*8+58h]
0x1400295cb  sub     rax, r13
0x1400295ce  test    rax, rax
0x1400295d1  jz      short loc_14002964D
0x1400295d3  mov     r8, [rdi+rcx*8+38h]
0x1400295d8  mov     rcx, [rdi+rcx*8+40h]
0x1400295dd  add     rcx, r8
0x1400295e0  cmp     r8, r11
0x1400295e3  jnb     short loc_140029635
0x1400295e5  cmp     rcx, rdx
0x1400295e8  jbe     short loc_14002963A
0x1400295ea  xor     edx, edx; Tag
0x1400295ec  mov     rcx, rdi; P
0x1400295ef  call    cs:__imp_ExFreePoolWithTag
0x1400295f6  nop     dword ptr [rax+rax+00h]
0x1400295fb  mov     r10, cs:WPP_GLOBAL_Control
0x140029602  lea     rcx, WPP_GLOBAL_Control
0x140029609  cmp     r10, rcx
0x14002960c  jz      loc_140029B53
0x140029612  mov     eax, [r10+2Ch]
0x140029616  test    al, 10h
0x140029618  jz      loc_140029B53
0x14002961e  mov     ebx, 2
0x140029623  cmp     [r10+29h], bl
0x140029627  jb      loc_140029B53
0x14002962d  lea     edx, [rbx+29h]
0x140029630  jmp     loc_140029B3D
0x140029635  cmp     rcx, rdx
0x140029638  ja      short loc_140029646
0x14002963a  cmp     rcx, r15
0x14002963d  cmova   r15, rcx
0x140029641  cmp     r8, r11
0x140029644  jb      short loc_14002964D
0x140029646  cmp     r8, r14
0x140029649  cmovb   r14, r8
0x14002964d  inc     r10d
0x140029650  jmp     loc_1400295A8
0x140029655  cmp     r15, r14
0x140029658  jz      loc_140029794
0x14002965e  test    r9, r9
0x140029661  jnz     loc_14002971E
0x140029667  mov     rdx, rdi; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x14002966a  mov     rcx, rsi; this
0x14002966d  call    ?CreateMetadataPartition@VMX_PHYSICAL_DISK@@AEAAJPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_PHYSICAL_DISK::CreateMetadataPartition(_DRIVE_LAYOUT_INFORMATION_EX *)
0x140029672  xor     edx, edx; Tag
0x140029674  mov     rcx, rdi; P
0x140029677  mov     r14d, eax
0x14002967a  call    cs:__imp_ExFreePoolWithTag
0x140029681  nop     dword ptr [rax+rax+00h]
0x140029686  test    r14d, r14d
0x140029689  jns     loc_140029491
0x14002968f  mov     r10, cs:WPP_GLOBAL_Control
0x140029696  lea     rcx, WPP_GLOBAL_Control
0x14002969d  cmp     r10, rcx
0x1400296a0  jz      short loc_1400296CB
0x1400296a2  mov     eax, [r10+2Ch]
0x1400296a6  test    al, 10h
0x1400296a8  jz      short loc_1400296CB
0x1400296aa  mov     ebx, 2
0x1400296af  cmp     [r10+29h], bl
0x1400296b3  jb      short loc_1400296CB
0x1400296b5  mov     rcx, [r10+18h]
0x1400296b9  lea     edx, [rbx+2Bh]
0x1400296bc  mov     r9d, r14d
0x1400296bf  lea     r8, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids
0x1400296c6  call    WPP_SF_d
0x1400296cb  mov     eax, r14d
0x1400296ce  jmp     loc_14002941A
0x1400296d3  xor     edx, edx; Tag
0x1400296d5  mov     rcx, rdi; P
0x1400296d8  call    cs:__imp_ExFreePoolWithTag
0x1400296df  nop     dword ptr [rax+rax+00h]
0x1400296e4  mov     r10, cs:WPP_GLOBAL_Control
0x1400296eb  lea     rcx, WPP_GLOBAL_Control
0x1400296f2  cmp     r10, rcx
0x1400296f5  jz      loc_1400299E8
0x1400296fb  mov     eax, [r10+2Ch]
0x1400296ff  test    al, 10h
0x140029701  jz      loc_1400299E8
0x140029707  mov     ebx, 2
0x14002970c  cmp     [r10+29h], bl
0x140029710  jb      loc_1400299E8
0x140029716  lea     edx, [rbx+28h]
  ... truncated ...
```
