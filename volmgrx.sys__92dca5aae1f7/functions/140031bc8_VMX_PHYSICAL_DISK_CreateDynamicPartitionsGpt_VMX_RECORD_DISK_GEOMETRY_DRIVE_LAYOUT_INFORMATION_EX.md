# VMX_PHYSICAL_DISK::CreateDynamicPartitionsGpt(VMX_RECORD *,_DISK_GEOMETRY *,_DRIVE_LAYOUT_INFORMATION_EX *)

- ea: `0x140031bc8`
- end: `0x140032614`
- name: `?CreateDynamicPartitionsGpt@VMX_PHYSICAL_DISK@@AEAAJPEAVVMX_RECORD@@PEAU_DISK_GEOMETRY@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z`
- size: `2636`
- prototype: `__int64 __fastcall(VMX_PHYSICAL_DISK *__hidden this, struct VMX_RECORD *, struct _DISK_GEOMETRY *, struct _DRIVE_LAYOUT_INFORMATION_EX *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140044ac4`

## callees

- `0x140006c0c`
- `0x1400099d8`
- `0x14001be80`
- `0x140031bc8`
- `0x1400342bc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140031c0e`
- `ntoskrnl!ExAllocatePool2` at `0x140031c0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031fc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032012`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032221`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400323e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032545`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400325b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031fc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032012`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032221`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400323e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032545`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400325b7`
- `ntoskrnl!ExUuidCreate` at `0x140031f83`
- `ntoskrnl!ExUuidCreate` at `0x14003239e`
- `ntoskrnl!ExUuidCreate` at `0x14003252e`
- `ntoskrnl!ExUuidCreate` at `0x140031f83`
- `ntoskrnl!ExUuidCreate` at `0x14003239e`
- `ntoskrnl!ExUuidCreate` at `0x14003252e`

## pseudocode

```c
__int64 __fastcall VMX_PHYSICAL_DISK::CreateDynamicPartitionsGpt(
        VMX_PHYSICAL_DISK *this,
        struct VMX_RECORD *a2,
        struct _DISK_GEOMETRY *a3,
        struct _DRIVE_LAYOUT_INFORMATION_EX *a4)
{
  __int64 BytesPerSector; // rdi
  __int64 v7; // r15
  __int64 Pool2; // rax
  _DWORD *v9; // rbx
  PARTITION_INFORMATION_EX *v11; // rbp
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int64 v14; // rax
  __int64 v15; // rdx
  DWORD PartitionCount; // r11d
  __int64 v17; // r10
  unsigned __int64 v18; // r12
  __int64 v19; // rdi
  LARGE_INTEGER StartingOffset; // rdx
  __int64 v21; // rax
  __int64 i; // r9
  unsigned int v23; // ecx
  __int64 v24; // r8
  __int64 v25; // rcx
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int64 v35; // rcx
  __int128 v36; // xmm0
  GUID PartitionId; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int64 v43; // rcx
  unsigned int v44; // r13d
  _QWORD *v45; // r12
  __int64 v46; // rcx
  __int64 v47; // r11
  DWORD v48; // r8d
  __int64 v49; // rdx
  __int64 v50; // r15
  UUID *v51; // rcx
  DWORD v52; // r11d
  GUID v53; // xmm0
  NTSTATUS v54; // r12d
  VMX_NOTIFICATION_QUEUE *v55; // rcx
  __int64 v56; // rdx
  VMX_NOTIFICATION_QUEUE *v57; // rcx
  __int64 v58; // rdx
  unsigned int v59; // r15d
  DWORD v60; // ebp
  LARGE_INTEGER v61; // r10
  __int64 v62; // r11
  LARGE_INTEGER v63; // rdx
  __int64 v64; // rax
  unsigned int j; // r10d
  unsigned int v66; // ecx
  __int64 v67; // r8
  __int64 v68; // rcx
  __int128 v69; // xmm1
  __int128 v70; // xmm0
  __int128 v71; // xmm1
  __int128 v72; // xmm0
  __int128 v73; // xmm1
  __int128 v74; // xmm0
  __int128 v75; // xmm1
  __int128 v76; // xmm0
  __int64 v77; // rax
  __int128 v78; // xmm1
  __int64 v79; // rcx
  __int128 v80; // xmm0
  GUID v81; // xmm1
  __int128 v82; // xmm0
  __int128 v83; // xmm1
  __int128 v84; // xmm0
  __int128 v85; // xmm1
  __int128 v86; // xmm0
  unsigned __int64 v87; // r12
  __int64 v88; // rbp
  unsigned __int64 v89; // r9
  __int64 v90; // rax
  unsigned int v91; // ecx
  __int64 v92; // r8
  __int64 v93; // rcx
  __int128 v94; // xmm1
  __int128 v95; // xmm0
  __int128 v96; // xmm1
  __int128 v97; // xmm0
  __int128 v98; // xmm1
  __int128 v99; // xmm0
  __int128 v100; // xmm1
  __int128 v101; // xmm0
  unsigned int v102; // ecx
  __int64 v103; // r8
  __int64 v104; // rcx
  __int128 v105; // xmm1
  __int128 v106; // xmm0
  __int128 v107; // xmm1
  __int128 v108; // xmm0
  __int128 v109; // xmm1
  __int128 v110; // xmm0
  __int128 v111; // xmm1
  __int128 v112; // xmm0
  __int64 v113; // rsi
  NTSTATUS v114; // ebp
  int v115; // edi
  __int64 v116; // [rsp+20h] [rbp-58h]
  unsigned __int64 v117; // [rsp+28h] [rbp-50h]
  __int64 v119; // [rsp+88h] [rbp+10h]
  LARGE_INTEGER v120; // [rsp+88h] [rbp+10h]
  _QWORD *v121; // [rsp+90h] [rbp+18h]
  unsigned __int64 v122; // [rsp+90h] [rbp+18h]
  __int64 v123; // [rsp+98h] [rbp+20h]
  __int64 v124; // [rsp+98h] [rbp+20h]

  BytesPerSector = a3->BytesPerSector;
  v7 = *((_QWORD *)a2 + (*((_WORD *)a2 + 32) & 1) + 5);
  Pool2 = ExAllocatePool2(258, 144LL * a4->Gpt.MaxPartitionCount + 48, 1632398678);
  v9 = (_DWORD *)Pool2;
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 3), 85, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids, 3221225626LL);
    }
    return 3221225626LL;
  }
  v11 = 0;
  v12 = *(_OWORD *)a4->Gpt.DiskId.Data4;
  *(_OWORD *)Pool2 = *(_OWORD *)&a4->PartitionStyle;
  v13 = *(_OWORD *)&a4->Gpt.UsableLength.LowPart;
  *(_OWORD *)(Pool2 + 16) = v12;
  *(_OWORD *)(Pool2 + 32) = v13;
  *(_DWORD *)(Pool2 + 4) = 0;
  memset((void *)(Pool2 + 48), 0, 144LL * a4->Gpt.MaxPartitionCount);
  v14 = *((_QWORD *)this + 11);
  v15 = BytesPerSector;
  PartitionCount = a4->PartitionCount;
  v17 = 0;
  v119 = BytesPerSector;
  v123 = *(_QWORD *)(v14 + 136);
  v18 = BytesPerSector * v123;
  v19 = 0;
  v116 = *(_QWORD *)(v14 + 144);
  v117 = v18;
  if ( PartitionCount )
  {
    do
    {
      v11 = &a4->PartitionEntry[v17];
      StartingOffset = v11->StartingOffset;
      if ( StartingOffset.QuadPart + v11->PartitionLength.QuadPart <= v18 )
      {
        v21 = *(_QWORD *)&v11->Mbr - *(_QWORD *)&PARTITION_LDM_DATA_GUID.Data1;
        if ( !v21 )
          v21 = *(_QWORD *)v11->Gpt.PartitionType.Data4 - *(_QWORD *)PARTITION_LDM_DATA_GUID.Data4;
        if ( v21 )
        {
          for ( i = 0; (unsigned int)i < (unsigned int)v19; i = (unsigned int)(i + 1) )
          {
            if ( StartingOffset.QuadPart < *(_QWORD *)&v9[36 * i + 14] )
              break;
          }
          v23 = v19;
          if ( (unsigned int)v19 > (unsigned int)i )
          {
            do
            {
              v24 = v23 - 1;
              v25 = 18LL * v23;
              v26 = *(_OWORD *)&v9[36 * v24 + 16];
              *(_OWORD *)&v9[2 * v25 + 12] = *(_OWORD *)&v9[36 * v24 + 12];
              v27 = *(_OWORD *)&v9[36 * v24 + 20];
              *(_OWORD *)&v9[2 * v25 + 16] = v26;
              v28 = *(_OWORD *)&v9[36 * v24 + 24];
              *(_OWORD *)&v9[2 * v25 + 20] = v27;
              v29 = *(_OWORD *)&v9[36 * v24 + 28];
              *(_OWORD *)&v9[2 * v25 + 24] = v28;
              v30 = *(_OWORD *)&v9[36 * v24 + 32];
              *(_OWORD *)&v9[2 * v25 + 28] = v29;
              v31 = *(_OWORD *)&v9[36 * v24 + 36];
              *(_OWORD *)&v9[2 * v25 + 32] = v30;
              v32 = *(_OWORD *)&v9[36 * v24 + 40];
              *(_OWORD *)&v9[2 * v25 + 36] = v31;
              v33 = *(_OWORD *)&v9[36 * v24 + 44];
              *(_OWORD *)&v9[2 * v25 + 40] = v32;
              *(_OWORD *)&v9[2 * v25 + 44] = v33;
              v23 = v24;
            }
            while ( (unsigned int)v24 > (unsigned int)i );
          }
          v19 = (unsigned int)(v19 + 1);
          v34 = *(_OWORD *)&v11->PartitionLength.LowPart;
          v35 = 18 * i;
          *(_OWORD *)&v9[2 * v35 + 12] = *(_OWORD *)&v11->PartitionStyle;
          v36 = *(_OWORD *)&v11->Mbr.PartitionType;
          *(_OWORD *)&v9[2 * v35 + 16] = v34;
          PartitionId = v11->Gpt.PartitionId;
          *(_OWORD *)&v9[2 * v35 + 20] = v36;
          v38 = *(_OWORD *)&v11->Gpt.Attributes;
          *(GUID *)&v9[2 * v35 + 24] = PartitionId;
          v39 = *(_OWORD *)&v11->Gpt.Name[4];
          *(_OWORD *)&v9[2 * v35 + 28] = v38;
          v40 = *(_OWORD *)&v11->Gpt.Name[12];
          *(_OWORD *)&v9[2 * v35 + 32] = v39;
          v41 = *(_OWORD *)&v11->Gpt.Name[20];
          *(_OWORD *)&v9[2 * v35 + 36] = v40;
          v42 = *(_OWORD *)&v11->Gpt.Name[28];
          *(_OWORD *)&v9[2 * v35 + 40] = v41;
          *(_OWORD *)&v9[2 * v35 + 44] = v42;
          LOBYTE(v9[2 * v35 + 19]) = 1;
        }
      }
      v17 = (unsigned int)(v17 + 1);
    }
    while ( (unsigned int)v17 < PartitionCount );
    v15 = v119;
  }
  v43 = *(_QWORD *)(v7 + 120);
  v44 = v19;
  while ( v43 )
  {
    v45 = *(_QWORD **)(v43 + 8LL * (*(_WORD *)(v43 + 64) & 1) + 40);
    v121 = v45;
    v46 = *(_QWORD *)(*(_QWORD *)(v45[21] + 8LL * (*(_WORD *)(v45[21] + 64LL) & 1) + 40) + 136LL);
    if ( (*(_DWORD *)(*(_QWORD *)(v46 + 8LL * (*(_WORD *)(v46 + 64) & 1) + 40) + 156LL) & 0x800000) != 0 )
    {
      v47 = 0;
      v48 = a4->PartitionCount;
      v49 = (v45[10] << 9) + *(_QWORD *)(*((_QWORD *)this + 11) + 136LL) * v15;
      if ( v48 )
      {
        do
        {
          v11 = &a4->PartitionEntry[v47];
          if ( v11->StartingOffset.QuadPart == v49 )
            break;
          v47 = (unsigned int)(v47 + 1);
        }
        while ( (unsigned int)v47 < v48 );
      }
      if ( (unsigned int)v19 >= a4->Gpt.MaxPartitionCount )
      {
        ExFreePoolWithTag(v9, 0);
        v57 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
        {
          v58 = 86;
LABEL_60:
          WPP_SF_d(*((_QWORD *)v57 + 3), v58, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids, 3224895504LL);
        }
        return 3224895504LL;
      }
      v50 = 36 * v19;
      v19 = (unsigned int)(v19 + 1);
      *(_QWORD *)&v9[v50 + 16] = v45[12] << 9;
      *(_QWORD *)&v9[v50 + 14] = v49;
      v9[v50 + 12] = 1;
      LOBYTE(v9[v50 + 19]) = 1;
      *(GUID *)&v9[v50 + 20] = PARTITION_LDM_DATA_GUID;
      RtlStringCbCopyW((NTSTRSAFE_PWSTR)&v9[v50 + 30], 0x48u, L"LDM data partition");
      v51 = (UUID *)&v9[v50 + 24];
      if ( v52 >= a4->PartitionCount )
      {
        v54 = ExUuidCreate(v51);
        if ( v54 < 0 )
        {
          ExFreePoolWithTag(v9, 0);
          v55 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
          {
            v56 = 87;
LABEL_36:
            WPP_SF_d(*((_QWORD *)v55 + 3), v56, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids, (unsigned int)v54);
          }
          return (unsigned int)v54;
        }
        v45 = v121;
        *(_QWORD *)&v9[v50 + 28] = 0;
      }
      else
      {
        v53 = v11->Gpt.PartitionId;
        *(_QWORD *)&v9[v50 + 28] = v11->Gpt.Attributes;
        *v51 = v53;
      }
    }
    v43 = v45[20];
    v15 = v119;
  }
  v59 = v19;
  v60 = a4->PartitionCount;
  v61.QuadPart = v15 * (v123 + v116);
  v62 = 0;
  v120 = v61;
  while ( 1 )
  {
    if ( (unsigned int)v62 >= v60 )
    {
      v87 = v117;
      while ( v44 < v59 )
      {
        v88 = 36LL * v44;
        v89 = *(_QWORD *)&v9[v88 + 14];
        v90 = *(_QWORD *)&v9[v88 + 16];
        v122 = v89;
        v124 = v90;
        if ( v89 > v87 )
        {
          if ( (unsigned int)v19 >= a4->Gpt.MaxPartitionCount )
            break;
          v91 = v19;
          if ( (unsigned int)v19 > v44 )
          {
            do
            {
              v92 = v91 - 1;
              v93 = 18LL * v91;
              v94 = *(_OWORD *)&v9[36 * v92 + 16];
              *(_OWORD *)&v9[2 * v93 + 12] = *(_OWORD *)&v9[36 * v92 + 12];
              v95 = *(_OWORD *)&v9[36 * v92 + 20];
              *(_OWORD *)&v9[2 * v93 + 16] = v94;
              v96 = *(_OWORD *)&v9[36 * v92 + 24];
              *(_OWORD *)&v9[2 * v93 + 20] = v95;
              v97 = *(_OWORD *)&v9[36 * v92 + 28];
              *(_OWORD *)&v9[2 * v93 + 24] = v96;
              v98 = *(_OWORD *)&v9[36 * v92 + 32];
              *(_OWORD *)&v9[2 * v93 + 28] = v97;
              v99 = *(_OWORD *)&v9[36 * v92 + 36];
              *(_OWORD *)&v9[2 * v93 + 32] = v98;
              v100 = *(_OWORD *)&v9[36 * v92 + 40];
              *(_OWORD *)&v9[2 * v93 + 36] = v99;
              v101 = *(_OWORD *)&v9[36 * v92 + 44];
              *(_OWORD *)&v9[2 * v93 + 40] = v100;
              *(_OWORD *)&v9[2 * v93 + 44] = v101;
              v91 = v92;
            }
            while ( (unsigned int)v92 > v44 );
          }
          v9[v88 + 12] = 1;
          *(_QWORD *)&v9[v88 + 14] = v87;
          *(_QWORD *)&v9[v88 + 16] = v89 - v87;
          LOBYTE(v9[v88 + 19]) = 1;
          *(GUID *)&v9[v88 + 20] = PARTITION_LDM_DATA_GUID;
          RtlStringCbCopyW((NTSTRSAFE_PWSTR)&v9[v88 + 30], 0x48u, L"LDM data partition");
          v54 = ExUuidCreate((UUID *)&v9[v88 + 24]);
          if ( v54 < 0 )
          {
            ExFreePoolWithTag(v9, 0);
            v55 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
            {
              v56 = 89;
              goto LABEL_36;
            }
            return (unsigned int)v54;
          }
          v89 = v122;
          LODWORD(v19) = v19 + 1;
          v90 = v124;
          ++v59;
          ++v44;
          *(_QWORD *)&v9[v88 + 28] = 0;
        }
        v87 = v90 + v89;
        ++v44;
      }
      if ( v120.QuadPart > v87 && (unsigned int)v19 < a4->Gpt.MaxPartitionCount )
      {
        v102 = v19;
        if ( (unsigned int)v19 > v59 )
        {
          do
          {
            v103 = v102 - 1;
            v104 = 18LL * v102;
            v105 = *(_OWORD *)&v9[36 * v103 + 16];
            *(_OWORD *)&v9[2 * v104 + 12] = *(_OWORD *)&v9[36 * v103 + 12];
            v106 = *(_OWORD *)&v9[36 * v103 + 20];
            *(_OWORD *)&v9[2 * v104 + 16] = v105;
            v107 = *(_OWORD *)&v9[36 * v103 + 24];
            *(_OWORD *)&v9[2 * v104 + 20] = v106;
            v108 = *(_OWORD *)&v9[36 * v103 + 28];
            *(_OWORD *)&v9[2 * v104 + 24] = v107;
            v109 = *(_OWORD *)&v9[36 * v103 + 32];
            *(_OWORD *)&v9[2 * v104 + 28] = v108;
            v110 = *(_OWORD *)&v9[36 * v103 + 36];
            *(_OWORD *)&v9[2 * v104 + 32] = v109;
            v111 = *(_OWORD *)&v9[36 * v103 + 40];
            *(_OWORD *)&v9[2 * v104 + 36] = v110;
            v112 = *(_OWORD *)&v9[36 * v103 + 44];
            *(_OWORD *)&v9[2 * v104 + 40] = v111;
            *(_OWORD *)&v9[2 * v104 + 44] = v112;
            v102 = v103;
          }
          while ( (unsigned int)v103 > v59 );
        }
        v113 = 36LL * v59;
        v9[v113 + 12] = 1;
        *(_QWORD *)&v9[v113 + 14] = v87;
        *(_QWORD *)&v9[v113 + 16] = v120.QuadPart - v87;
        LOBYTE(v9[v113 + 19]) = 1;
        *(GUID *)&v9[v113 + 20] = PARTITION_LDM_DATA_GUID;
        RtlStringCbCopyW((NTSTRSAFE_PWSTR)&v9[v113 + 30], 0x48u, L"LDM data partition");
        v114 = ExUuidCreate((UUID *)&v9[v113 + 24]);
        if ( v114 < 0 )
        {
          ExFreePoolWithTag(v9, 0);
          if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              90,
              WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids,
              (unsigned int)v114);
          }
          return (unsigned int)v114;
        }
        LODWORD(v19) = v19 + 1;
        *(_QWORD *)&v9[v113 + 28] = 0;
      }
      v9[1] = v19;
      v115 = VMX_DISK_DEVICE::SetDriveLayoutExSynchronous(*((VMX_DISK_DEVICE **)this + 2), v9);
      ExFreePoolWithTag(v9, 0);
      if ( v115 < 0
        && WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          91,
          WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids,
          (unsigned int)v115);
      }
      return (unsigned int)v115;
    }
    v63 = a4->PartitionEntry[v62].StartingOffset;
    if ( v63.QuadPart >= (unsigned __int64)v61.QuadPart )
    {
      v64 = *(_QWORD *)&a4->PartitionEntry[v62].Mbr - *(_QWORD *)&PARTITION_LDM_DATA_GUID.Data1;
      if ( !v64 )
        v64 = *(_QWORD *)a4->PartitionEntry[v62].Gpt.PartitionType.Data4 - *(_QWORD *)PARTITION_LDM_DATA_GUID.Data4;
      if ( v64 )
        break;
    }
LABEL_55:
    v62 = (unsigned int)(v62 + 1);
  }
  if ( (unsigned int)v19 < a4->Gpt.MaxPartitionCount )
  {
    for ( j = v59; j < (unsigned int)v19; ++j )
    {
      if ( v63.QuadPart < *(_QWORD *)&v9[36 * j + 14] )
        break;
    }
    v66 = v19;
    if ( (unsigned int)v19 > j )
    {
      do
      {
        v67 = v66 - 1;
        v68 = 18LL * v66;
        v69 = *(_OWORD *)&v9[36 * v67 + 16];
        *(_OWORD *)&v9[2 * v68 + 12] = *(_OWORD *)&v9[36 * v67 + 12];
        v70 = *(_OWORD *)&v9[36 * v67 + 20];
        *(_OWORD *)&v9[2 * v68 + 16] = v69;
        v71 = *(_OWORD *)&v9[36 * v67 + 24];
        *(_OWORD *)&v9[2 * v68 + 20] = v70;
        v72 = *(_OWORD *)&v9[36 * v67 + 28];
        *(_OWORD *)&v9[2 * v68 + 24] = v71;
        v73 = *(_OWORD *)&v9[36 * v67 + 32];
        *(_OWORD *)&v9[2 * v68 + 28] = v72;
        v74 = *(_OWORD *)&v9[36 * v67 + 36];
        *(_OWORD *)&v9[2 * v68 + 32] = v73;
        v75 = *(_OWORD *)&v9[36 * v67 + 40];
        *(_OWORD *)&v9[2 * v68 + 36] = v74;
        v76 = *(_OWORD *)&v9[36 * v67 + 44];
        *(_OWORD *)&v9[2 * v68 + 40] = v75;
        *(_OWORD *)&v9[2 * v68 + 44] = v76;
        v66 = v67;
      }
      while ( (unsigned int)v67 > j );
    }
    v77 = j;
    LODWORD(v19) = v19 + 1;
    v78 = *(_OWORD *)&a4->PartitionEntry[v62].PartitionLength.LowPart;
    v61 = v120;
    v79 = 18 * v77;
    *(_OWORD *)&v9[2 * v79 + 12] = *(_OWORD *)&a4->PartitionEntry[v62].PartitionStyle;
    v80 = *(_OWORD *)&a4->PartitionEntry[v62].Mbr.PartitionType;
    *(_OWORD *)&v9[2 * v79 + 16] = v78;
    v81 = a4->PartitionEntry[v62].Gpt.PartitionId;
    *(_OWORD *)&v9[2 * v79 + 20] = v80;
    v82 = *(_OWORD *)&a4->PartitionEntry[v62].Gpt.Attributes;
    *(GUID *)&v9[2 * v79 + 24] = v81;
    v83 = *(_OWORD *)&a4->PartitionEntry[v62].Gpt.Name[4];
    *(_OWORD *)&v9[2 * v79 + 28] = v82;
    v84 = *(_OWORD *)&a4->PartitionEntry[v62].Gpt.Name[12];
    *(_OWORD *)&v9[2 * v79 + 32] = v83;
    v85 = *(_OWORD *)&a4->PartitionEntry[v62].Gpt.Name[20];
    *(_OWORD *)&v9[2 * v79 + 36] = v84;
    v86 = *(_OWORD *)&a4->PartitionEntry[v62].Gpt.Name[28];
    *(_OWORD *)&v9[2 * v79 + 40] = v85;
    *(_OWORD *)&v9[2 * v79 + 44] = v86;
    LOBYTE(v9[2 * v79 + 19]) = 1;
    goto LABEL_55;
  }
  ExFreePoolWithTag(v9, 0);
  v57 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    v58 = 88;
    goto LABEL_60;
  }
  return 3224895504LL;
}

```

## disassembly

```asm
0x140031bc8  mov     [rsp+arg_0], rcx
0x140031bcd  push    rbx
0x140031bce  push    rbp
0x140031bcf  push    rsi
0x140031bd0  push    rdi
0x140031bd1  push    r12
0x140031bd3  push    r13
0x140031bd5  push    r14
0x140031bd7  push    r15
0x140031bd9  sub     rsp, 38h
0x140031bdd  movzx   eax, word ptr [rdx+40h]
0x140031be1  mov     r13, rcx
0x140031be4  mov     edi, [r8+14h]
0x140031be8  and     eax, 1
0x140031beb  mov     ecx, 102h
0x140031bf0  mov     r8d, 614C6D56h
0x140031bf6  mov     r14, r9
0x140031bf9  mov     r15, [rdx+rax*8+28h]
0x140031bfe  mov     eax, [r9+28h]
0x140031c02  lea     rdx, [rax+rax*8]
0x140031c06  shl     rdx, 4
0x140031c0a  add     rdx, 30h ; '0'
0x140031c0e  call    cs:__imp_ExAllocatePool2
0x140031c15  nop     dword ptr [rax+rax+00h]
0x140031c1a  mov     rbx, rax
0x140031c1d  test    rax, rax
0x140031c20  jnz     short loc_140031C66
0x140031c22  mov     rcx, cs:WPP_GLOBAL_Control
0x140031c29  lea     rax, WPP_GLOBAL_Control
0x140031c30  mov     ebx, 0C000009Ah
0x140031c35  cmp     rcx, rax
0x140031c38  jz      short loc_140031C5F
0x140031c3a  mov     eax, [rcx+2Ch]
0x140031c3d  test    al, 10h
0x140031c3f  jz      short loc_140031C5F
0x140031c41  cmp     byte ptr [rcx+29h], 2
0x140031c45  jb      short loc_140031C5F
0x140031c47  mov     rcx, [rcx+18h]
0x140031c4b  lea     r8, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids
0x140031c52  mov     edx, 55h ; 'U'
0x140031c57  mov     r9d, ebx
0x140031c5a  call    WPP_SF_d
0x140031c5f  mov     eax, ebx
0x140031c61  jmp     loc_140032602
0x140031c66  movups  xmm0, xmmword ptr [r14]
0x140031c6a  xor     ebp, ebp
0x140031c6c  xor     edx, edx; Val
0x140031c6e  movups  xmm1, xmmword ptr [r14+10h]
0x140031c73  lea     rcx, [rbx+30h]; void *
0x140031c77  movups  xmmword ptr [rax], xmm0
0x140031c7a  movups  xmm0, xmmword ptr [r14+20h]
0x140031c7f  movups  xmmword ptr [rax+10h], xmm1
0x140031c83  movups  xmmword ptr [rax+20h], xmm0
0x140031c87  mov     [rax+4], ebp
0x140031c8a  mov     eax, [r14+28h]
0x140031c8e  lea     r8, [rax+rax*8]
0x140031c92  shl     r8, 4; Size
0x140031c96  call    memset
0x140031c9b  mov     rax, [r13+58h]
0x140031c9f  mov     rdx, rdi
0x140031ca2  mov     r11d, [r14+4]
0x140031ca6  xor     r10d, r10d
0x140031ca9  mov     [rsp+78h+arg_8], rdx
0x140031cb1  mov     r8, [rax+88h]
0x140031cb8  mov     r12, r8
0x140031cbb  mov     [rsp+78h+arg_18], r8
0x140031cc3  mov     r8, [rax+90h]
0x140031cca  imul    r12, rdi
0x140031cce  xor     edi, edi
0x140031cd0  mov     [rsp+78h+var_58], r8
0x140031cd5  mov     [rsp+78h+var_50], r12
0x140031cda  test    r11d, r11d
0x140031cdd  jz      loc_140031E63
0x140031ce3  lea     rbp, [r10+r10*8]
0x140031ce7  shl     rbp, 4
0x140031ceb  add     rbp, 30h ; '0'
0x140031cef  add     rbp, r14
0x140031cf2  mov     rdx, [rbp+8]
0x140031cf6  mov     rcx, [rbp+10h]
0x140031cfa  add     rcx, rdx
0x140031cfd  cmp     rcx, r12
0x140031d00  ja      loc_140031E4F
0x140031d06  mov     rax, [rbp+20h]
0x140031d0a  sub     rax, qword ptr cs:PARTITION_LDM_DATA_GUID.Data1
0x140031d11  jnz     short loc_140031D1E
0x140031d13  mov     rax, [rbp+28h]
0x140031d17  sub     rax, qword ptr cs:PARTITION_LDM_DATA_GUID.Data4
0x140031d1e  test    rax, rax
0x140031d21  jz      loc_140031E4F
0x140031d27  xor     r9d, r9d
0x140031d2a  test    edi, edi
0x140031d2c  jz      short loc_140031D44
0x140031d2e  lea     rcx, [r9+r9*8]
0x140031d32  add     rcx, rcx
0x140031d35  cmp     rdx, [rbx+rcx*8+38h]
0x140031d3a  jb      short loc_140031D44
0x140031d3c  inc     r9d
0x140031d3f  cmp     r9d, edi
0x140031d42  jb      short loc_140031D2E
0x140031d44  mov     ecx, edi
0x140031d46  cmp     edi, r9d
0x140031d49  jbe     loc_140031DE1
0x140031d4f  lea     r8d, [rcx-1]
0x140031d53  mov     eax, ecx
0x140031d55  lea     rdx, [r8+r8*8]
0x140031d59  add     rdx, rdx
0x140031d5c  lea     rcx, [rax+rax*8]
0x140031d60  add     rcx, rcx
0x140031d63  movups  xmm0, xmmword ptr [rbx+rdx*8+30h]
0x140031d68  movups  xmm1, xmmword ptr [rbx+rdx*8+40h]
0x140031d6d  movups  xmmword ptr [rbx+rcx*8+30h], xmm0
0x140031d72  movups  xmm0, xmmword ptr [rbx+rdx*8+50h]
0x140031d77  movups  xmmword ptr [rbx+rcx*8+40h], xmm1
0x140031d7c  movups  xmm1, xmmword ptr [rbx+rdx*8+60h]
0x140031d81  movups  xmmword ptr [rbx+rcx*8+50h], xmm0
0x140031d86  movups  xmm0, xmmword ptr [rbx+rdx*8+70h]
0x140031d8b  movups  xmmword ptr [rbx+rcx*8+60h], xmm1
0x140031d90  movups  xmm1, xmmword ptr [rbx+rdx*8+80h]
0x140031d98  movups  xmmword ptr [rbx+rcx*8+70h], xmm0
0x140031d9d  movups  xmm0, xmmword ptr [rbx+rdx*8+90h]
0x140031da5  movups  xmmword ptr [rbx+rcx*8+80h], xmm1
0x140031dad  movups  xmm1, xmmword ptr [rbx+rdx*8+0A0h]
0x140031db5  movups  xmmword ptr [rbx+rcx*8+90h], xmm0
0x140031dbd  movups  xmm0, xmmword ptr [rbx+rdx*8+0B0h]
0x140031dc5  movups  xmmword ptr [rbx+rcx*8+0A0h], xmm1
0x140031dcd  movups  xmmword ptr [rbx+rcx*8+0B0h], xmm0
0x140031dd5  mov     ecx, r8d
0x140031dd8  cmp     r8d, r9d
0x140031ddb  ja      loc_140031D4F
0x140031de1  movups  xmm0, xmmword ptr [rbp+0]
0x140031de5  inc     edi
0x140031de7  lea     rcx, [r9+r9*8]
0x140031deb  movups  xmm1, xmmword ptr [rbp+10h]
0x140031def  add     rcx, rcx
0x140031df2  movups  xmmword ptr [rbx+rcx*8+30h], xmm0
0x140031df7  movups  xmm0, xmmword ptr [rbp+20h]
0x140031dfb  movups  xmmword ptr [rbx+rcx*8+40h], xmm1
0x140031e00  movups  xmm1, xmmword ptr [rbp+30h]
0x140031e04  movups  xmmword ptr [rbx+rcx*8+50h], xmm0
0x140031e09  movups  xmm0, xmmword ptr [rbp+40h]
0x140031e0d  movups  xmmword ptr [rbx+rcx*8+60h], xmm1
0x140031e12  movups  xmm1, xmmword ptr [rbp+50h]
0x140031e16  movups  xmmword ptr [rbx+rcx*8+70h], xmm0
0x140031e1b  movups  xmm0, xmmword ptr [rbp+60h]
0x140031e1f  movups  xmmword ptr [rbx+rcx*8+80h], xmm1
0x140031e27  movups  xmm1, xmmword ptr [rbp+70h]
0x140031e2b  movups  xmmword ptr [rbx+rcx*8+90h], xmm0
0x140031e33  movups  xmm0, xmmword ptr [rbp+80h]
0x140031e3a  movups  xmmword ptr [rbx+rcx*8+0A0h], xmm1
0x140031e42  movups  xmmword ptr [rbx+rcx*8+0B0h], xmm0
0x140031e4a  mov     byte ptr [rbx+rcx*8+4Ch], 1
0x140031e4f  inc     r10d
0x140031e52  cmp     r10d, r11d
0x140031e55  jb      loc_140031CE3
0x140031e5b  mov     rdx, [rsp+78h+arg_8]
0x140031e63  mov     rcx, [r15+78h]
0x140031e67  mov     r13d, edi
0x140031e6a  test    rcx, rcx
0x140031e6d  jz      loc_140032054
0x140031e73  movzx   eax, word ptr [rcx+40h]
0x140031e77  and     eax, 1
0x140031e7a  mov     r12, [rcx+rax*8+28h]
0x140031e7f  mov     [rsp+78h+arg_10], r12
0x140031e87  mov     rcx, [r12+0A8h]
0x140031e8f  movzx   eax, word ptr [rcx+40h]
0x140031e93  and     eax, 1
0x140031e96  mov     rax, [rcx+rax*8+28h]
0x140031e9b  mov     rcx, [rax+88h]
0x140031ea2  movzx   eax, word ptr [rcx+40h]
0x140031ea6  and     eax, 1
0x140031ea9  mov     rax, [rcx+rax*8+28h]
0x140031eae  test    dword ptr [rax+9Ch], 800000h
0x140031eb8  jz      loc_140031FA7
0x140031ebe  mov     rax, [rsp+78h+arg_0]
0x140031ec6  xor     r11d, r11d
0x140031ec9  mov     r8d, [r14+4]
0x140031ecd  mov     rax, [rax+58h]
0x140031ed1  imul    rdx, [rax+88h]
0x140031ed9  mov     rax, [r12+50h]
0x140031ede  shl     rax, 9
0x140031ee2  add     rdx, rax
0x140031ee5  test    r8d, r8d
0x140031ee8  jz      short loc_140031F07
0x140031eea  lea     rbp, [r11+r11*8]
0x140031eee  shl     rbp, 4
0x140031ef2  add     rbp, 30h ; '0'
0x140031ef6  add     rbp, r14
0x140031ef9  cmp     [rbp+8], rdx
0x140031efd  jz      short loc_140031F07
0x140031eff  inc     r11d
0x140031f02  cmp     r11d, r8d
0x140031f05  jb      short loc_140031EEA
0x140031f07  cmp     edi, [r14+28h]
0x140031f0b  jnb     loc_14003200D
0x140031f11  mov     rcx, [r12+60h]
0x140031f16  lea     r15, [rdi+rdi*8]
0x140031f1a  movups  xmm0, xmmword ptr cs:PARTITION_LDM_DATA_GUID.Data1
0x140031f21  shl     r15, 4
0x140031f25  lea     r8, aLdmDataPartiti; "LDM data partition"
0x140031f2c  shl     rcx, 9
0x140031f30  inc     edi
0x140031f32  mov     [r15+rbx+40h], rcx
0x140031f37  lea     rcx, [rbx+78h]
0x140031f3b  mov     [r15+rbx+38h], rdx
0x140031f40  add     rcx, r15; pszDest
0x140031f43  mov     edx, 48h ; 'H'; cbDest
0x140031f48  mov     dword ptr [r15+rbx+30h], 1
0x140031f51  mov     byte ptr [r15+rbx+4Ch], 1
0x140031f57  movdqu  xmmword ptr [r15+rbx+50h], xmm0
0x140031f5e  call    RtlStringCbCopyW
0x140031f63  lea     rcx, [rbx+60h]
0x140031f67  add     rcx, r15; Uuid
0x140031f6a  cmp     r11d, [r14+4]
0x140031f6e  jnb     short loc_140031F83
0x140031f70  movups  xmm0, xmmword ptr [rbp+30h]
0x140031f74  mov     rax, [rbp+40h]
0x140031f78  mov     [r15+rbx+70h], rax
0x140031f7d  movdqu  xmmword ptr [rcx], xmm0
0x140031f81  jmp     short loc_140031FA7
0x140031f83  call    cs:__imp_ExUuidCreate
0x140031f8a  nop     dword ptr [rax+rax+00h]
0x140031f8f  mov     r12d, eax
0x140031f92  test    eax, eax
0x140031f94  js      short loc_140031FBC
0x140031f96  mov     r12, [rsp+78h+arg_10]
0x140031f9e  mov     qword ptr [r15+rbx+70h], 0
0x140031fa7  mov     rcx, [r12+0A0h]
0x140031faf  mov     rdx, [rsp+78h+arg_8]
0x140031fb7  jmp     loc_140031E6A
0x140031fbc  xor     edx, edx; Tag
0x140031fbe  mov     rcx, rbx; P
0x140031fc1  call    cs:__imp_ExFreePoolWithTag
0x140031fc8  nop     dword ptr [rax+rax+00h]
0x140031fcd  mov     rcx, cs:WPP_GLOBAL_Control
0x140031fd4  lea     rax, WPP_GLOBAL_Control
0x140031fdb  cmp     rcx, rax
0x140031fde  jz      short loc_140032005
0x140031fe0  mov     eax, [rcx+2Ch]
0x140031fe3  test    al, 10h
0x140031fe5  jz      short loc_140032005
0x140031fe7  cmp     byte ptr [rcx+29h], 2
0x140031feb  jb      short loc_140032005
0x140031fed  mov     edx, 57h ; 'W'
0x140031ff2  mov     rcx, [rcx+18h]
0x140031ff6  lea     r8, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids
0x140031ffd  mov     r9d, r12d
0x140032000  call    WPP_SF_d
0x140032005  mov     eax, r12d
0x140032008  jmp     loc_140032602
0x14003200d  xor     edx, edx; Tag
0x14003200f  mov     rcx, rbx; P
0x140032012  call    cs:__imp_ExFreePoolWithTag
0x140032019  nop     dword ptr [rax+rax+00h]
0x14003201e  mov     rcx, cs:WPP_GLOBAL_Control
0x140032025  lea     rax, WPP_GLOBAL_Control
0x14003202c  cmp     rcx, rax
0x14003202f  jz      loc_140032268
0x140032035  mov     eax, [rcx+2Ch]
0x140032038  test    al, 10h
0x14003203a  jz      loc_140032268
0x140032040  cmp     byte ptr [rcx+29h], 2
0x140032044  jb      loc_140032268
0x14003204a  mov     edx, 56h ; 'V'
0x14003204f  jmp     loc_140032252
0x140032054  mov     r10, [rsp+78h+var_58]
0x140032059  mov     r15d, edi
0x14003205c  add     r10, [rsp+78h+arg_18]
0x140032064  mov     ebp, [r14+4]
0x140032068  imul    r10, rdx
0x14003206c  xor     r11d, r11d
0x14003206f  mov     [rsp+78h+arg_8], r10
0x140032077  cmp     r11d, ebp
0x14003207a  jnb     loc_140032272
0x140032080  lea     r9, [r11+r11*8]
0x140032084  add     r9, r9
0x140032087  mov     rdx, [r14+r9*8+38h]
0x14003208c  cmp     rdx, r10
0x14003208f  jb      loc_140032214
0x140032095  mov     rax, [r14+r9*8+50h]
0x14003209a  sub     rax, qword ptr cs:PARTITION_LDM_DATA_GUID.Data1
0x1400320a1  jnz     short loc_1400320AF
0x1400320a3  mov     rax, [r14+r9*8+58h]
0x1400320a8  sub     rax, qword ptr cs:PARTITION_LDM_DATA_GUID.Data4
0x1400320af  test    rax, rax
0x1400320b2  jz      loc_140032214
0x1400320b8  cmp     edi, [r14+28h]
0x1400320bc  jnb     loc_14003221C
0x1400320c2  mov     r10d, r15d
0x1400320c5  cmp     r15d, edi
0x1400320c8  jnb     short loc_1400320E3
0x1400320ca  mov     eax, r10d
0x1400320cd  lea     rcx, [rax+rax*8]
0x1400320d1  add     rcx, rcx
0x1400320d4  cmp     rdx, [rbx+rcx*8+38h]
0x1400320d9  jb      short loc_1400320E3
0x1400320db  inc     r10d
0x1400320de  cmp     r10d, edi
0x1400320e1  jb      short loc_1400320CA
0x1400320e3  mov     ecx, edi
0x1400320e5  cmp     edi, r10d
  ... truncated ...
```
