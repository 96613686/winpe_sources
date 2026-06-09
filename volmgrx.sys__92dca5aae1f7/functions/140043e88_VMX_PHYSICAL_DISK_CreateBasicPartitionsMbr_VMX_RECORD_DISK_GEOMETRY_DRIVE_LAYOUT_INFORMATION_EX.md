# VMX_PHYSICAL_DISK::CreateBasicPartitionsMbr(VMX_RECORD *,_DISK_GEOMETRY *,_DRIVE_LAYOUT_INFORMATION_EX *)

- ea: `0x140043e88`
- end: `0x140044abb`
- name: `?CreateBasicPartitionsMbr@VMX_PHYSICAL_DISK@@AEAAJPEAVVMX_RECORD@@PEAU_DISK_GEOMETRY@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z`
- size: `3123`
- prototype: `__int64 __fastcall(VMX_PHYSICAL_DISK *__hidden this, struct VMX_RECORD *, struct _DISK_GEOMETRY *, struct _DRIVE_LAYOUT_INFORMATION_EX *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140043754`

## callees

- `0x1400099d8`
- `0x14001be80`
- `0x1400342bc`
- `0x140040580`
- `0x1400436c0`
- `0x140043e88`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140044228`
- `ntoskrnl!ExAllocatePool2` at `0x140044228`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044a22`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044a50`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044a22`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044a50`

## pseudocode

```c
__int64 __fastcall VMX_PHYSICAL_DISK::CreateBasicPartitionsMbr(
        VMX_PHYSICAL_DISK *this,
        struct VMX_RECORD *a2,
        struct _DISK_GEOMETRY *a3,
        struct _DRIVE_LAYOUT_INFORMATION_EX *a4)
{
  int v5; // ebx
  unsigned __int64 BytesPerSector; // rsi
  int v7; // r14d
  __int64 v8; // r11
  __int64 v9; // rax
  DWORD PartitionCount; // r9d
  __int64 v11; // rdx
  __int64 v12; // r10
  LARGE_INTEGER v13; // r10
  unsigned __int64 v14; // rsi
  __int64 v15; // rdx
  unsigned int PartitionType; // r8d
  LARGE_INTEGER StartingOffset; // r8
  __int64 v18; // rcx
  unsigned __int64 v19; // r14
  unsigned __int64 v20; // r12
  int v21; // r15d
  _QWORD *v22; // r13
  __int64 v23; // rcx
  VMX_VOLUME_INFO *v24; // rcx
  __int64 v25; // r8
  DWORD v26; // r10d
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // rsi
  unsigned int v29; // eax
  int v30; // r9d
  LARGE_INTEGER v31; // r9
  unsigned int v32; // ebx
  VMX_NOTIFICATION_QUEUE *v33; // rcx
  __int64 v34; // rdx
  VMX_NOTIFICATION_QUEUE *v36; // rcx
  __int64 v37; // rdx
  int v38; // r13d
  unsigned int v39; // eax
  __int64 v40; // r14
  __int64 Pool2; // rax
  _DWORD *v42; // rbx
  __int128 v43; // xmm1
  __int128 v44; // xmm0
  __int64 v45; // r10
  __int64 v46; // r8
  int v47; // r11d
  __int64 v48; // rdx
  unsigned int v49; // ecx
  __int128 v50; // xmm1
  __int64 v51; // rcx
  __int128 v52; // xmm0
  GUID PartitionId; // xmm1
  __int128 v54; // xmm0
  __int128 v55; // xmm1
  __int128 v56; // xmm0
  __int128 v57; // xmm1
  __int128 v58; // xmm0
  VMX_NOTIFICATION_QUEUE *v59; // rcx
  __int64 v60; // rdx
  unsigned __int64 v61; // r8
  unsigned __int64 v62; // rdx
  __int64 v63; // rcx
  _QWORD *v64; // rsi
  unsigned __int64 v65; // r11
  __int64 v66; // r12
  unsigned __int64 v67; // r9
  BOOLEAN BootIndicator; // r13
  __int64 i; // r8
  __int64 v70; // rdx
  unsigned int v71; // eax
  int v72; // ecx
  LARGE_INTEGER v73; // rcx
  __int64 v74; // r9
  __int64 v75; // rdx
  __int64 v76; // r8
  char v77; // cl
  LARGE_INTEGER v78; // r12
  __int64 j; // r8
  unsigned int v80; // ecx
  int v81; // r9d
  __int128 v82; // xmm1
  __int64 v83; // rcx
  __int128 v84; // xmm0
  GUID v85; // xmm1
  __int128 v86; // xmm0
  __int128 v87; // xmm1
  __int128 v88; // xmm0
  __int128 v89; // xmm1
  __int128 v90; // xmm0
  __int64 v91; // r9
  unsigned __int64 v92; // rsi
  unsigned __int64 k; // r11
  unsigned int v94; // ecx
  __int64 v95; // r8
  __int64 v96; // rcx
  __int128 v97; // xmm1
  __int128 v98; // xmm0
  __int128 v99; // xmm1
  __int128 v100; // xmm0
  __int128 v101; // xmm1
  __int128 v102; // xmm0
  __int128 v103; // xmm1
  __int128 v104; // xmm0
  unsigned __int64 v105; // r12
  __int64 v106; // rcx
  __int64 v107; // rcx
  char v108; // di
  __int64 v109; // rcx
  _QWORD *v110; // r8
  unsigned __int64 v111; // rdx
  __int64 v112; // r9
  __int64 v113; // rcx
  __int64 v114; // rsi
  __int64 v115; // rcx
  __int64 v116; // rcx
  char v117; // al
  __int64 v118; // rcx
  int v119; // edi
  unsigned __int64 v120; // [rsp+20h] [rbp-49h]
  unsigned __int64 v121; // [rsp+28h] [rbp-41h]
  __int128 v122; // [rsp+30h] [rbp-39h] BYREF
  __int64 v123; // [rsp+40h] [rbp-29h]
  DWORD SectorsPerTrack; // [rsp+48h] [rbp-21h]
  unsigned __int64 v125; // [rsp+50h] [rbp-19h]
  LARGE_INTEGER v126; // [rsp+58h] [rbp-11h]
  __int64 v127; // [rsp+60h] [rbp-9h]
  __int128 v128; // [rsp+68h] [rbp-1h] BYREF
  __int64 v129; // [rsp+78h] [rbp+Fh]
  __int64 v130; // [rsp+80h] [rbp+17h]
  unsigned __int64 v132; // [rsp+D8h] [rbp+6Fh] BYREF
  DWORD TracksPerCylinder; // [rsp+E0h] [rbp+77h]

  v5 = 0;
  BytesPerSector = a3->BytesPerSector;
  v121 = BytesPerSector;
  v7 = 32801;
  v8 = *((_QWORD *)a2 + (*((_WORD *)a2 + 32) & 1) + 5);
  SectorsPerTrack = a3->SectorsPerTrack;
  TracksPerCylinder = a3->TracksPerCylinder;
  v9 = *((_QWORD *)this + 11);
  PartitionCount = a4->PartitionCount;
  v127 = v8;
  LODWORD(v132) = 0;
  v11 = *(_QWORD *)(v9 + 136);
  v12 = *(_QWORD *)(v9 + 144);
  v129 = 0;
  v13.QuadPart = BytesPerSector * (v11 + v12);
  v14 = v11 * BytesPerSector;
  v128 = 0;
  v126 = v13;
  v15 = 0;
  v120 = v14;
  do
  {
    if ( (unsigned int)v15 >= PartitionCount )
      break;
    PartitionType = a4->PartitionEntry[v15].Mbr.PartitionType;
    if ( ((unsigned __int8)PartitionType > 0xFu || !_bittest(&v7, PartitionType)) && (_BYTE)PartitionType != 66 )
    {
      StartingOffset = a4->PartitionEntry[v15].StartingOffset;
      if ( StartingOffset.QuadPart >= (unsigned __int64)v13.QuadPart
        || StartingOffset.QuadPart + a4->PartitionEntry[v15].PartitionLength.QuadPart <= v14 )
      {
        ++v5;
      }
    }
    v15 = (unsigned int)(v15 + 1);
  }
  while ( (unsigned int)v15 < 4 );
  v18 = *(_QWORD *)(v8 + 120);
  v122 = 0;
  v19 = 0;
  v20 = v14;
  LODWORD(v132) = v5;
  v21 = 0;
  v123 = 0;
  while ( v18 )
  {
    v22 = *(_QWORD **)(v18 + 8LL * (*(_WORD *)(v18 + 64) & 1) + 40);
    v23 = *(_QWORD *)(v22[21] + 8LL * (*(_WORD *)(v22[21] + 64LL) & 1) + 40);
    if ( *(_BYTE *)(v23 + 87) != 2 || *(_DWORD *)(v23 + 92) != 1 )
    {
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v37 = 92;
LABEL_45:
        WPP_SF_d(*((_QWORD *)v36 + 3), v37, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids, 3224895493LL);
      }
      return 3224895493LL;
    }
    v24 = *(VMX_VOLUME_INFO **)(*(_QWORD *)(v23 + 136) + 8LL * (*(_WORD *)(*(_QWORD *)(v23 + 136) + 64LL) & 1) + 40);
    if ( *((_DWORD *)v24 + 40) != 1 )
    {
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v37 = 93;
        goto LABEL_45;
      }
      return 3224895493LL;
    }
    VMX_VOLUME_INFO::QueryGptAttributes(v24);
    v25 = 0;
    v26 = a4->PartitionCount;
    v27 = v14 + (v22[10] << 9);
    v28 = v27 + (v22[12] << 9);
    if ( v26 )
    {
      while ( 1 )
      {
        v29 = a4->PartitionEntry[v25].Mbr.PartitionType;
        if ( (unsigned __int8)v29 > 0xFu || (v30 = 32801, !_bittest(&v30, v29)) )
        {
          v31 = a4->PartitionEntry[v25].StartingOffset;
          if ( v31.QuadPart == v27 && v31.QuadPart + a4->PartitionEntry[v25].PartitionLength.QuadPart == v28 )
            break;
        }
        v25 = (unsigned int)(v25 + 1);
        if ( (unsigned int)v25 >= v26 )
          goto LABEL_21;
      }
    }
    else
    {
LABEL_21:
      if ( (unsigned int)v25 >= v26 )
      {
        if ( v27 >= v20 + v121 )
          goto LABEL_24;
        goto LABEL_29;
      }
    }
    if ( (unsigned int)v25 >= 4 )
    {
      BYTE4(v123) = 1;
LABEL_24:
      *((_QWORD *)&v122 + 1) = v28;
      if ( !v21 )
        v19 = v20;
      LODWORD(v123) = ++v21;
      *(_QWORD *)&v122 = v19;
      goto LABEL_27;
    }
LABEL_29:
    *((_QWORD *)&v122 + 1) = v27;
    LODWORD(v132) = v5 + 1;
    v32 = VMX_MBR_CONTAINER::CompareCopyContainer(
            (VMX_MBR_CONTAINER *)&v128,
            (struct VMX_MBR_CONTAINER *)&v122,
            (unsigned int *)&v132);
    if ( (v32 & 0x80000000) != 0 )
    {
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v34 = 94;
        goto LABEL_35;
      }
      return v32;
    }
    v5 = v132;
    v21 = 0;
    v19 = 0;
    v122 = 0;
    v123 = 0;
LABEL_27:
    v18 = v22[20];
    v20 = v28;
    v14 = v120;
  }
  *((LARGE_INTEGER *)&v122 + 1) = v126;
  v32 = VMX_MBR_CONTAINER::CompareCopyContainer(
          (VMX_MBR_CONTAINER *)&v128,
          (struct VMX_MBR_CONTAINER *)&v122,
          (unsigned int *)&v132);
  if ( (v32 & 0x80000000) != 0 )
  {
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return v32;
    }
    v34 = 95;
    goto LABEL_35;
  }
  v38 = v129;
  v39 = v132;
  v130 = v129;
  if ( (_DWORD)v129 )
    v39 = v132 + 1;
  if ( v39 > 4 )
  {
    v33 = WPP_GLOBAL_Control;
    v32 = -1070071792;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return v32;
    }
    v34 = 96;
    goto LABEL_35;
  }
  v40 = (unsigned int)(4 * v129 + 4);
  Pool2 = ExAllocatePool2(258, 144 * v40 + 48, 1632398678);
  v42 = (_DWORD *)Pool2;
  if ( !Pool2 )
  {
    v33 = WPP_GLOBAL_Control;
    v32 = -1073741670;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return v32;
    }
    v34 = 97;
LABEL_35:
    WPP_SF_d(*((_QWORD *)v33 + 3), v34, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids, v32);
    return v32;
  }
  v43 = *(_OWORD *)a4->Gpt.DiskId.Data4;
  *(_OWORD *)Pool2 = *(_OWORD *)&a4->PartitionStyle;
  v44 = *(_OWORD *)&a4->Gpt.UsableLength.LowPart;
  *(_OWORD *)(Pool2 + 16) = v43;
  *(_OWORD *)(Pool2 + 32) = v44;
  *(_DWORD *)(Pool2 + 4) = 0;
  memset((void *)(Pool2 + 48), 0, 144 * v40);
  v45 = 0;
  v46 = 0;
  v47 = 32801;
  while ( (unsigned int)v46 < 4 && (unsigned int)v46 < a4->PartitionCount )
  {
    v48 = v46;
    v49 = a4->PartitionEntry[v46].Mbr.PartitionType;
    if ( ((unsigned __int8)v49 > 0xFu || !_bittest(&v47, v49))
      && (_BYTE)v49 != 66
      && a4->PartitionEntry[v48].StartingOffset.QuadPart + a4->PartitionEntry[v48].PartitionLength.QuadPart <= v120 )
    {
      if ( (unsigned int)v45 >= (unsigned int)v40 )
      {
        v59 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
        {
          goto LABEL_168;
        }
        v60 = 98;
        goto LABEL_167;
      }
      v50 = *(_OWORD *)&a4->PartitionEntry[v48].PartitionLength.LowPart;
      v51 = 18 * v45;
      v45 = (unsigned int)(v45 + 1);
      *(_OWORD *)&v42[2 * v51 + 12] = *(_OWORD *)&a4->PartitionEntry[v48].PartitionStyle;
      v52 = *(_OWORD *)&a4->PartitionEntry[v48].Mbr.PartitionType;
      *(_OWORD *)&v42[2 * v51 + 16] = v50;
      PartitionId = a4->PartitionEntry[v48].Gpt.PartitionId;
      *(_OWORD *)&v42[2 * v51 + 20] = v52;
      v54 = *(_OWORD *)&a4->PartitionEntry[v48].Gpt.Attributes;
      *(GUID *)&v42[2 * v51 + 24] = PartitionId;
      v55 = *(_OWORD *)&a4->PartitionEntry[v48].Gpt.Name[4];
      *(_OWORD *)&v42[2 * v51 + 28] = v54;
      v56 = *(_OWORD *)&a4->PartitionEntry[v48].Gpt.Name[12];
      *(_OWORD *)&v42[2 * v51 + 32] = v55;
      v57 = *(_OWORD *)&a4->PartitionEntry[v48].Gpt.Name[20];
      *(_OWORD *)&v42[2 * v51 + 36] = v56;
      v58 = *(_OWORD *)&a4->PartitionEntry[v48].Gpt.Name[28];
      *(_OWORD *)&v42[2 * v51 + 40] = v57;
      *(_OWORD *)&v42[2 * v51 + 44] = v58;
      LOBYTE(v42[2 * v51 + 19]) = 1;
    }
    v46 = (unsigned int)(v46 + 1);
  }
  v61 = *((_QWORD *)&v128 + 1);
  v125 = *((_QWORD *)&v128 + 1);
  v62 = v128;
  v63 = *(_QWORD *)(v127 + 120);
  v132 = v128;
  while ( v63 )
  {
    v64 = *(_QWORD **)(v63 + 8LL * (*(_WORD *)(v63 + 64) & 1) + 40);
    v65 = v120 + (v64[10] << 9);
    v66 = v64[12] << 9;
    v67 = v66 + v65;
    if ( !v38 || v65 >= v61 || v67 <= v62 )
    {
      BootIndicator = 0;
      for ( i = 0; (unsigned int)i < 4 && (unsigned int)i < a4->PartitionCount; i = (unsigned int)(i + 1) )
      {
        v70 = i;
        v71 = a4->PartitionEntry[i].Mbr.PartitionType;
        if ( (unsigned __int8)v71 <= 0xFu )
        {
          v72 = 32801;
          if ( _bittest(&v72, v71) )
            continue;
        }
        v73 = a4->PartitionEntry[v70].StartingOffset;
        if ( v73.QuadPart == v65 && a4->PartitionEntry[v70].PartitionLength.QuadPart + v73.QuadPart == v67 )
        {
          BootIndicator = a4->PartitionEntry[v70].Mbr.BootIndicator;
          break;
        }
      }
      if ( (unsigned int)v45 >= (unsigned int)v40 )
      {
        v59 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
        {
          goto LABEL_168;
        }
        v60 = 99;
        goto LABEL_167;
      }
      v74 = 18 * v45;
      v45 = (unsigned int)(v45 + 1);
      v75 = *(_QWORD *)(*(_QWORD *)(v64[21] + 8LL * (*(_WORD *)(v64[21] + 64LL) & 1) + 40) + 136LL);
      v76 = *(_QWORD *)(v75 + 8LL * (*(_WORD *)(v75 + 64) & 1) + 40);
      v62 = v132;
      v42[2 * v74 + 12] = 0;
      *(_QWORD *)&v42[2 * v74 + 14] = v65;
      *(_QWORD *)&v42[2 * v74 + 16] = v66;
      LOBYTE(v42[2 * v74 + 19]) = 1;
      v77 = *(_BYTE *)(v76 + 200);
      v61 = v125;
      BYTE1(v42[2 * v74 + 20]) = BootIndicator;
      v38 = v130;
      v42[2 * v74 + 21] = v65 / v121;
      LOBYTE(v42[2 * v74 + 20]) = v77;
    }
    v63 = v64[20];
  }
  v78 = v126;
  for ( j = 0; (unsigned int)j < 4 && (unsigned int)j < a4->PartitionCount; j = (unsigned int)(j + 1) )
  {
    v80 = a4->PartitionEntry[j].Mbr.PartitionType;
    if ( (unsigned __int8)v80 <= 0xFu )
    {
      v81 = 32801;
      if ( _bittest(&v81, v80) )
        continue;
    }
    if ( (_BYTE)v80 != 66 && a4->PartitionEntry[j].StartingOffset.QuadPart >= (unsigned __int64)v78.QuadPart )
    {
      if ( (unsigned int)v45 >= (unsigned int)v40 )
      {
        v59 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
        {
          goto LABEL_168;
        }
        v60 = 100;
        goto LABEL_167;
      }
      v82 = *(_OWORD *)&a4->PartitionEntry[j].PartitionLength.LowPart;
      v83 = 18 * v45;
      v45 = (unsigned int)(v45 + 1);
      *(_OWORD *)&v42[2 * v83 + 12] = *(_OWORD *)&a4->PartitionEntry[j].PartitionStyle;
      v84 = *(_OWORD *)&a4->PartitionEntry[j].Mbr.PartitionType;
      *(_OWORD *)&v42[2 * v83 + 16] = v82;
      v85 = a4->PartitionEntry[j].Gpt.PartitionId;
      *(_OWORD *)&v42[2 * v83 + 20] = v84;
      v86 = *(_OWORD *)&a4->PartitionEntry[j].Gpt.Attributes;
      *(GUID *)&v42[2 * v83 + 24] = v85;
      v87 = *(_OWORD *)&a4->PartitionEntry[j].Gpt.Name[4];
      *(_OWORD *)&v42[2 * v83 + 28] = v86;
      v88 = *(_OWORD *)&a4->PartitionEntry[j].Gpt.Name[12];
      *(_OWORD *)&v42[2 * v83 + 32] = v87;
      v89 = *(_OWORD *)&a4->PartitionEntry[j].Gpt.Name[20];
      *(_OWORD *)&v42[2 * v83 + 36] = v88;
      v90 = *(_OWORD *)&a4->PartitionEntry[j].Gpt.Name[28];
      *(_OWORD *)&v42[2 * v83 + 40] = v89;
      *(_OWORD *)&v42[2 * v83 + 44] = v90;
      LOBYTE(v42[2 * v83 + 19]) = 1;
    }
  }
  if ( !v38 )
  {
    v92 = v132;
    v105 = v125;
    goto LABEL_126;
  }
  if ( (unsigned int)v45 >= (unsigned int)v40 )
  {
    v59 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_168;
    }
    v60 = 101;
    goto LABEL_167;
  }
  v91 = 0;
  v92 = v132;
  for ( k = v121 * SectorsPerTrack * (unsigned __int64)TracksPerCylinder;
        (unsigned int)v91 < (unsigned int)v45;
        v91 = (unsigned int)(v91 + 1) )
  {
    if ( *(_QWORD *)&v42[36 * v91 + 14] > v132 )
      break;
  }
  v94 = v45;
  if ( (unsigned int)v45 > (unsigned int)v91 )
  {
    do
    {
      v95 = v94 - 1;
      v96 = 18LL * v94;
      v97 = *(_OWORD *)&v42[36 * v95 + 16];
      *(_OWORD *)&v42[2 * v96 + 12] = *(_OWORD *)&v42[36 * v95 + 12];
      v98 = *(_OWORD *)&v42[36 * v95 + 20];
      *(_OWORD *)&v42[2 * v96 + 16] = v97;
      v99 = *(_OWORD *)&v42[36 * v95 + 24];
      *(_OWORD *)&v42[2 * v96 + 20] = v98;
      v100 = *(_OWORD *)&v42[36 * v95 + 28];
      *(_OWORD *)&v42[2 * v96 + 24] = v99;
      v101 = *(_OWORD *)&v42[36 * v95 + 32];
      *(_OWORD *)&v42[2 * v96 + 28] = v100;
      v102 = *(_OWORD *)&v42[36 * v95 + 36];
      *(_OWORD *)&v42[2 * v96 + 32] = v101;
      v103 = *(_OWORD *)&v42[36 * v95 + 40];
      *(_OWORD *)&v42[2 * v96 + 36] = v102;
      v104 = *(_OWORD *)&v42[36 * v95 + 44];
      *(_OWORD *)&v42[2 * v96 + 40] = v103;
      *(_OWORD *)&v42[2 * v96 + 44] = v104;
      v94 = v95;
    }
    while ( (unsigned int)v95 > (unsigned int)v91 );
  }
  v105 = v125;
  v106 = 18 * v91;
  v45 = (unsigned int)(v45 + 1);
  *(_QWORD *)&v42[2 * v106 + 16] = v125 - v92;
  v42[2 * v106 + 12] = 0;
  *(_QWORD *)&v42[2 * v106 + 14] = v92;
  LOBYTE(v42[2 * v106 + 19]) = 1;
  LOBYTE(v42[2 * v106 + 20]) = k << 10 < v105 ? 15 : 5;
  BYTE1(v42[2 * v106 + 20]) = 0;
  v42[2 * v106 + 21] = 0;
LABEL_126:
  while ( (unsigned int)v45 < 4 )
  {
    if ( (unsigned int)v45 >= (unsigned int)v40 )
    {
      v59 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        goto LABEL_168;
      }
      v60 = 102;
LABEL_167:
      WPP_SF_d(*((_QWORD *)v59 + 3), v60, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids, 3221225473LL);
      goto LABEL_168;
    }
    v107 = 18 * v45;
    v45 = (unsigned int)(v45 + 1);
    LOBYTE(v42[2 * v107 + 20]) = 0;
    LOBYTE(v42[2 * v107 + 19]) = 1;
  }
  if ( !v38 )
  {
LABEL_169:
    v42[1] = v45;
    v119 = VMX_DISK_DEVICE::SetDriveLayoutExSynchronous(*((VMX_DISK_DEVICE **)this + 2), v42);
    ExFreePoolWithTag(v42, 0);
    if ( v119 >= 0 )
      return 0;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        107,
        WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids,
        (unsigned int)v119);
    }
    return (unsigned int)v119;
  }
  v108 = 1;
  v109 = *(_QWORD *)(v127 + 120);
  while ( 2 )
  {
    if ( !v109 )
    {
      while ( (v45 & 3) != 0 )
      {
        if ( (unsigned int)v45 >= (unsigned int)v40 )
        {
          v59 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
          {
            v60 = 106;
            goto LABEL_167;
          }
          goto LABEL_168;
        }
        v118 = 18 * v45;
        v45 = (unsigned int)(v45 + 1);
        LOBYTE(v42[2 * v118 + 20]) = 0;
        LOBYTE(v42[2 * v118 + 19]) = 1;
      }
      goto LABEL_169;
    }
    v110 = *(_QWORD **)(v109 + 8LL * (*(_WORD *)(v109 + 64) & 1) + 40);
    v111 = v120 + (v110[10] << 9);
    if ( v111 < v92 || (v112 = v110[12] << 9, v112 + v111 > v105) )
    {
LABEL_147:
      v109 = v110[20];
      continue;
    }
    break;
  }
  v113 = *(_QWORD *)(*(_QWORD *)(v110[21] + 8LL * (*(_WORD *)(v110[21] + 64LL) & 1) + 40) + 136LL);
  v114 = *(_QWORD *)(v113 + 8LL * (*(_WORD *)(v113 + 64) & 1) + 40);
  if ( v108 )
  {
    v108 = 0;
  }
  else
  {
    if ( (unsigned int)v45 >= (unsigned int)v40 )
    {
      v59 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v60 = 103;
        goto LABEL_167;
      }
      goto LABEL_168;
    }
    v115 = 18 * v45;
    v45 = (unsigned int)(v45 + 1);
    *(_QWORD *)&v42[2 * v115 + 14] = v111 - v121;
    v42[2 * v115 + 12] = 0;
    LOWORD(v42[2 * v115 + 20]) = 5;
    *(_QWORD *)&v42[2 * v115 + 16] = v112 + v121;
    v42[2 * v115 + 21] = 0;
    while ( 1 )
    {
      LOBYTE(v42[2 * v115 + 19]) = 1;
      if ( (v45 & 3) == 0 )
        break;
      if ( (unsigned int)v45 >= (unsigned int)v40 )
      {
        v59 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
        {
          v60 = 104;
          goto LABEL_167;
        }
        goto LABEL_168;
      }
      v115 = 18 * v45;
      v45 = (unsigned int)(v45 + 1);
      LOBYTE(v42[2 * v115 + 20]) = 0;
    }
  }
  if ( (unsigned int)v45 < (unsigned int)v40 )
  {
    v116 = 18 * v45;
    v45 = (unsigned int)(v45 + 1);
    v42[2 * v116 + 12] = 0;
    *(_QWORD *)&v42[2 * v116 + 14] = v111;
    *(_QWORD *)&v42[2 * v116 + 16] = v112;
    LOBYTE(v42[2 * v116 + 19]) = 1;
    v117 = *(_BYTE *)(v114 + 200);
    v92 = v132;
    LOBYTE(v42[2 * v116 + 20]) = v117;
    BYTE1(v42[2 * v116 + 20]) = 0;
    v42[2 * v116 + 21] = 1;
    goto LABEL_147;
  }
  v59 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    v60 = 105;
    goto LABEL_167;
  }
LABEL_168:
  ExFreePoolWithTag(v42, 0);
  return 3221225473LL;
}

```

## disassembly

```asm
0x140043e88  mov     [rsp-8+arg_18], rbx
0x140043e8d  mov     [rsp-8+arg_0], rcx
0x140043e92  push    rbp
0x140043e93  push    rsi
0x140043e94  push    rdi
0x140043e95  push    r12
0x140043e97  push    r13
0x140043e99  push    r14
0x140043e9b  push    r15
0x140043e9d  lea     rbp, [rsp-27h]
0x140043ea2  sub     rsp, 90h
0x140043ea9  movzx   eax, word ptr [rdx+40h]
0x140043ead  mov     rdi, r9
0x140043eb0  and     eax, 1
0x140043eb3  mov     r9, rcx
0x140043eb6  mov     ecx, [r8+14h]
0x140043eba  xor     ebx, ebx
0x140043ebc  mov     esi, ecx
0x140043ebe  mov     [rbp+57h+var_98], rcx
0x140043ec2  xorps   xmm0, xmm0
0x140043ec5  mov     r14d, 8021h
0x140043ecb  mov     r11, [rdx+rax*8+28h]
0x140043ed0  mov     eax, [r8+10h]
0x140043ed4  mov     [rbp+57h+var_78], eax
0x140043ed7  mov     eax, [r8+0Ch]
0x140043edb  mov     [rbp+57h+arg_10], eax
0x140043ede  mov     rax, [r9+58h]
0x140043ee2  mov     r9d, [rdi+4]
0x140043ee6  mov     [rbp+57h+var_60], r11
0x140043eea  mov     dword ptr [rbp+57h+arg_8], ebx
0x140043eed  mov     rdx, [rax+88h]
0x140043ef4  mov     r10, [rax+90h]
0x140043efb  xor     eax, eax
0x140043efd  add     r10, rdx
0x140043f00  mov     [rbp+57h+var_48], rax
0x140043f04  imul    r10, rcx
0x140043f08  imul    rsi, rdx
0x140043f0c  movups  [rbp+57h+var_58], xmm0
0x140043f10  mov     [rbp+57h+var_68], r10
0x140043f14  xor     edx, edx
0x140043f16  mov     [rbp+57h+var_A0], rsi
0x140043f1a  cmp     edx, r9d
0x140043f1d  jnb     short loc_140043F5E
0x140043f1f  lea     rcx, [rdx+rdx*8]
0x140043f23  add     rcx, rcx
0x140043f26  movzx   r8d, byte ptr [rdi+rcx*8+50h]
0x140043f2c  cmp     r8b, 0Fh
0x140043f30  ja      short loc_140043F38
0x140043f32  bt      r14d, r8d
0x140043f36  jb      short loc_140043F57
0x140043f38  cmp     r8b, 42h ; 'B'
0x140043f3c  jz      short loc_140043F57
0x140043f3e  mov     r8, [rdi+rcx*8+38h]
0x140043f43  cmp     r8, r10
0x140043f46  jnb     short loc_140043F55
0x140043f48  mov     rcx, [rdi+rcx*8+40h]
0x140043f4d  add     rcx, r8
0x140043f50  cmp     rcx, rsi
0x140043f53  ja      short loc_140043F57
0x140043f55  inc     ebx
0x140043f57  inc     edx
0x140043f59  cmp     edx, 4
0x140043f5c  jb      short loc_140043F1A
0x140043f5e  mov     rcx, [r11+78h]
0x140043f62  xorps   xmm0, xmm0
0x140043f65  movups  [rbp+57h+var_90], xmm0
0x140043f69  mov     r14, qword ptr [rbp+57h+var_90]
0x140043f6d  mov     r12, rsi
0x140043f70  mov     dword ptr [rbp+57h+arg_8], ebx
0x140043f73  mov     r15d, eax
0x140043f76  mov     [rbp+57h+var_80], rax
0x140043f7a  test    rcx, rcx
0x140043f7d  jz      loc_140044160
0x140043f83  movzx   eax, word ptr [rcx+40h]
0x140043f87  and     eax, 1
0x140043f8a  mov     r13, [rcx+rax*8+28h]
0x140043f8f  mov     rcx, [r13+0A8h]
0x140043f96  movzx   eax, word ptr [rcx+40h]
0x140043f9a  and     eax, 1
0x140043f9d  mov     rcx, [rcx+rax*8+28h]
0x140043fa2  cmp     byte ptr [rcx+57h], 2
0x140043fa6  jnz     loc_14004411A
0x140043fac  cmp     dword ptr [rcx+5Ch], 1
0x140043fb0  jnz     loc_14004411A
0x140043fb6  mov     rcx, [rcx+88h]
0x140043fbd  movzx   eax, word ptr [rcx+40h]
0x140043fc1  and     eax, 1
0x140043fc4  mov     rcx, [rcx+rax*8+28h]; this
0x140043fc9  cmp     dword ptr [rcx+0A0h], 1
0x140043fd0  jnz     loc_1400440F3
0x140043fd6  call    ?QueryGptAttributes@VMX_VOLUME_INFO@@QEAA_KXZ; VMX_VOLUME_INFO::QueryGptAttributes(void)
0x140043fdb  mov     rdx, [r13+50h]
0x140043fdf  xor     r8d, r8d
0x140043fe2  mov     r10d, [rdi+4]
0x140043fe6  shl     rdx, 9
0x140043fea  add     rdx, rsi
0x140043fed  mov     rsi, [r13+60h]
0x140043ff1  shl     rsi, 9
0x140043ff5  add     rsi, rdx
0x140043ff8  test    r10d, r10d
0x140043ffb  jz      short loc_140044038
0x140043ffd  lea     rcx, [r8+r8*8]
0x140044001  add     rcx, rcx
0x140044004  movzx   eax, byte ptr [rdi+rcx*8+50h]
0x140044009  cmp     al, 0Fh
0x14004400b  ja      short loc_140044019
0x14004400d  mov     r9d, 8021h
0x140044013  bt      r9d, eax
0x140044017  jb      short loc_140044030
0x140044019  mov     r9, [rdi+rcx*8+38h]
0x14004401e  cmp     r9, rdx
0x140044021  jnz     short loc_140044030
0x140044023  mov     rcx, [rdi+rcx*8+40h]
0x140044028  add     rcx, r9
0x14004402b  cmp     rcx, rsi
0x14004402e  jz      short loc_14004403D
0x140044030  inc     r8d
0x140044033  cmp     r8d, r10d
0x140044036  jb      short loc_140043FFD
0x140044038  cmp     r8d, r10d
0x14004403b  jnb     short loc_140044070
0x14004403d  cmp     r8d, 4
0x140044041  jb      short loc_14004407C
0x140044043  mov     byte ptr [rbp+57h+var_80+4], 1
0x140044047  test    r15d, r15d
0x14004404a  mov     qword ptr [rbp+57h+var_90+8], rsi
0x14004404e  cmovz   r14, r12
0x140044052  inc     r15d
0x140044055  mov     dword ptr [rbp+57h+var_80], r15d
0x140044059  mov     qword ptr [rbp+57h+var_90], r14
0x14004405d  mov     rcx, [r13+0A0h]
0x140044064  mov     r12, rsi
0x140044067  mov     rsi, [rbp+57h+var_A0]
0x14004406b  jmp     loc_140043F7A
0x140044070  mov     rax, [rbp+57h+var_98]
0x140044074  add     rax, r12
0x140044077  cmp     rdx, rax
0x14004407a  jnb     short loc_140044047
0x14004407c  mov     qword ptr [rbp+57h+var_90+8], rdx
0x140044080  lea     r8, [rbp+57h+arg_8]; unsigned int *
0x140044084  inc     ebx
0x140044086  lea     rdx, [rbp+57h+var_90]; struct VMX_MBR_CONTAINER *
0x14004408a  lea     rcx, [rbp+57h+var_58]; this
0x14004408e  mov     dword ptr [rbp+57h+arg_8], ebx
0x140044091  call    ?CompareCopyContainer@VMX_MBR_CONTAINER@@QEAAJPEAV1@PEAK@Z; VMX_MBR_CONTAINER::CompareCopyContainer(VMX_MBR_CONTAINER *,ulong *)
0x140044096  mov     ebx, eax
0x140044098  test    eax, eax
0x14004409a  js      short loc_1400440B4
0x14004409c  mov     ebx, dword ptr [rbp+57h+arg_8]
0x14004409f  xorps   xmm0, xmm0
0x1400440a2  xor     r15d, r15d
0x1400440a5  movq    r14, xmm0
0x1400440aa  movups  [rbp+57h+var_90], xmm0
0x1400440ae  mov     [rbp+57h+var_80], r15
0x1400440b2  jmp     short loc_14004405D
0x1400440b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400440bb  lea     rax, WPP_GLOBAL_Control
0x1400440c2  cmp     rcx, rax
0x1400440c5  jz      short loc_1400440EC
0x1400440c7  mov     eax, [rcx+2Ch]
0x1400440ca  test    al, 10h
0x1400440cc  jz      short loc_1400440EC
0x1400440ce  cmp     byte ptr [rcx+29h], 2
0x1400440d2  jb      short loc_1400440EC
0x1400440d4  mov     edx, 5Eh ; '^'
0x1400440d9  mov     rcx, [rcx+18h]
0x1400440dd  lea     r8, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids
0x1400440e4  mov     r9d, ebx
0x1400440e7  call    WPP_SF_d
0x1400440ec  mov     eax, ebx
0x1400440ee  jmp     loc_140044A9F
0x1400440f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400440fa  lea     rax, WPP_GLOBAL_Control
0x140044101  cmp     rcx, rax
0x140044104  jz      short loc_140044156
0x140044106  mov     eax, [rcx+2Ch]
0x140044109  test    al, 10h
0x14004410b  jz      short loc_140044156
0x14004410d  cmp     byte ptr [rcx+29h], 2
0x140044111  jb      short loc_140044156
0x140044113  mov     edx, 5Dh ; ']'
0x140044118  jmp     short loc_140044140
0x14004411a  mov     rcx, cs:WPP_GLOBAL_Control
0x140044121  lea     rax, WPP_GLOBAL_Control
0x140044128  cmp     rcx, rax
0x14004412b  jz      short loc_140044156
0x14004412d  mov     edx, [rcx+2Ch]
0x140044130  test    dl, 10h
0x140044133  jz      short loc_140044156
0x140044135  cmp     byte ptr [rcx+29h], 2
0x140044139  jb      short loc_140044156
0x14004413b  mov     edx, 5Ch ; '\'
0x140044140  mov     rcx, [rcx+18h]
0x140044144  lea     r8, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids
0x14004414b  mov     r9d, 0C0380005h
0x140044151  call    WPP_SF_d
0x140044156  mov     eax, 0C0380005h
0x14004415b  jmp     loc_140044A9F
0x140044160  mov     r12, [rbp+57h+var_68]
0x140044164  lea     r8, [rbp+57h+arg_8]; unsigned int *
0x140044168  lea     rdx, [rbp+57h+var_90]; struct VMX_MBR_CONTAINER *
0x14004416c  mov     qword ptr [rbp+57h+var_90+8], r12
0x140044170  lea     rcx, [rbp+57h+var_58]; this
0x140044174  call    ?CompareCopyContainer@VMX_MBR_CONTAINER@@QEAAJPEAV1@PEAK@Z; VMX_MBR_CONTAINER::CompareCopyContainer(VMX_MBR_CONTAINER *,ulong *)
0x140044179  mov     ebx, eax
0x14004417b  test    eax, eax
0x14004417d  jns     short loc_1400441B6
0x14004417f  mov     rcx, cs:WPP_GLOBAL_Control
0x140044186  lea     rax, WPP_GLOBAL_Control
0x14004418d  cmp     rcx, rax
0x140044190  jz      loc_1400440EC
0x140044196  mov     edx, [rcx+2Ch]
0x140044199  test    dl, 10h
0x14004419c  jz      loc_1400440EC
0x1400441a2  cmp     byte ptr [rcx+29h], 2
0x1400441a6  jb      loc_1400440EC
0x1400441ac  mov     edx, 5Fh ; '_'
0x1400441b1  jmp     loc_1400440D9
0x1400441b6  mov     r13, [rbp+57h+var_48]
0x1400441ba  mov     eax, dword ptr [rbp+57h+arg_8]
0x1400441bd  mov     [rbp+57h+var_40], r13
0x1400441c1  test    r13d, r13d
0x1400441c4  jz      short loc_1400441C8
0x1400441c6  inc     eax
0x1400441c8  cmp     eax, 4
0x1400441cb  jbe     short loc_140044209
0x1400441cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400441d4  lea     rax, WPP_GLOBAL_Control
0x1400441db  mov     ebx, 0C0380010h
0x1400441e0  cmp     rcx, rax
0x1400441e3  jz      loc_1400440EC
0x1400441e9  mov     edx, [rcx+2Ch]
0x1400441ec  test    dl, 10h
0x1400441ef  jz      loc_1400440EC
0x1400441f5  cmp     byte ptr [rcx+29h], 2
0x1400441f9  jb      loc_1400440EC
0x1400441ff  mov     edx, 60h ; '`'
0x140044204  jmp     loc_1400440D9
0x140044209  lea     r14d, ds:4[r13*4]
0x140044211  mov     ecx, 102h
0x140044216  lea     rsi, [r14+r14*8]
0x14004421a  mov     r8d, 614C6D56h
0x140044220  shl     rsi, 4
0x140044224  lea     rdx, [rsi+30h]
0x140044228  call    cs:__imp_ExAllocatePool2
0x14004422f  nop     dword ptr [rax+rax+00h]
0x140044234  mov     rbx, rax
0x140044237  test    rax, rax
0x14004423a  jnz     short loc_140044278
0x14004423c  mov     rcx, cs:WPP_GLOBAL_Control
0x140044243  lea     rax, WPP_GLOBAL_Control
0x14004424a  mov     ebx, 0C000009Ah
0x14004424f  cmp     rcx, rax
0x140044252  jz      loc_1400440EC
0x140044258  mov     edx, [rcx+2Ch]
0x14004425b  test    dl, 10h
0x14004425e  jz      loc_1400440EC
0x140044264  cmp     byte ptr [rcx+29h], 2
0x140044268  jb      loc_1400440EC
0x14004426e  mov     edx, 61h ; 'a'
0x140044273  jmp     loc_1400440D9
0x140044278  movups  xmm0, xmmword ptr [rdi]
0x14004427b  mov     r8, rsi; Size
0x14004427e  xor     edx, edx; Val
0x140044280  movups  xmm1, xmmword ptr [rdi+10h]
0x140044284  lea     rcx, [rax+30h]; void *
0x140044288  movups  xmmword ptr [rax], xmm0
0x14004428b  movups  xmm0, xmmword ptr [rdi+20h]
0x14004428f  movups  xmmword ptr [rax+10h], xmm1
0x140044293  movups  xmmword ptr [rax+20h], xmm0
0x140044297  mov     dword ptr [rax+4], 0
0x14004429e  call    memset
0x1400442a3  mov     r9, [rbp+57h+var_A0]
0x1400442a7  xor     r10d, r10d
0x1400442aa  xor     r8d, r8d
0x1400442ad  mov     r11d, 8021h
0x1400442b3  cmp     r8d, 4
0x1400442b7  jnb     loc_1400443C7
0x1400442bd  cmp     r8d, [rdi+4]
0x1400442c1  jnb     loc_1400443C7
0x1400442c7  lea     rdx, [r8+r8*8]
0x1400442cb  shl     rdx, 4
0x1400442cf  movzx   ecx, byte ptr [rdx+rdi+50h]
0x1400442d4  cmp     cl, 0Fh
0x1400442d7  ja      short loc_1400442E3
0x1400442d9  bt      r11d, ecx
0x1400442dd  jb      loc_140044389
0x1400442e3  cmp     cl, 42h ; 'B'
0x1400442e6  jz      loc_140044389
0x1400442ec  mov     rax, [rdx+rdi+40h]
0x1400442f1  add     rax, [rdx+rdi+38h]
0x1400442f6  cmp     rax, r9
0x1400442f9  ja      loc_140044389
0x1400442ff  cmp     r10d, r14d
0x140044302  jnb     loc_140044391
0x140044308  movups  xmm0, xmmword ptr [rdx+rdi+30h]
0x14004430d  lea     rcx, [r10+r10*8]
0x140044311  movups  xmm1, xmmword ptr [rdx+rdi+40h]
0x140044316  add     rcx, rcx
0x140044319  inc     r10d
  ... truncated ...
```
