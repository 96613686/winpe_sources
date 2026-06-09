# SIO_RAID::Initialize(SDB_SPACE *,unsigned __int64,SIO_SPACE *,SIO_TIER *)

- ea: `0x1400229d0`
- end: `0x140023b68`
- name: `?Initialize@SIO_RAID@@UEAAJPEAVSDB_SPACE@@_KPEAVSIO_SPACE@@PEAVSIO_TIER@@@Z`
- size: `4504`
- prototype: `__int64 __fastcall(SIO_RAID *__hidden this, struct SDB_SPACE *, unsigned __int64, struct SIO_SPACE *, struct SIO_TIER *)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x14004f4c0`
- `0x140052f30`

## callees

- `0x1400058a0`
- `0x140005eb0`
- `0x140007fa0`
- `0x140009f80`
- `0x14000b3e0`
- `0x14000bb50`
- `0x14000c630`
- `0x14000e530`
- `0x14000fb70`
- `0x14001f2d0`
- `0x1400229d0`
- `0x140023cb0`
- `0x140026e00`
- `0x1400559d0`
- `0x140068000`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x14002340d`
- `ntoskrnl!IoAllocateMdl` at `0x1400236dd`
- `ntoskrnl!IoAllocateMdl` at `0x14002340d`
- `ntoskrnl!IoAllocateMdl` at `0x1400236dd`
- `ntoskrnl!ExAllocatePool2` at `0x140022b85`
- `ntoskrnl!ExAllocatePool2` at `0x14002332b`
- `ntoskrnl!ExAllocatePool2` at `0x1400239ad`
- `ntoskrnl!ExAllocatePool2` at `0x140022b85`
- `ntoskrnl!ExAllocatePool2` at `0x14002332b`
- `ntoskrnl!ExAllocatePool2` at `0x1400239ad`
- `ntoskrnl!MmAllocateMappingAddress` at `0x14002371a`
- `ntoskrnl!MmAllocateMappingAddress` at `0x14002371a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002356d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400235bd`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140023607`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140023784`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400238f4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002393e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002356d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400235bd`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140023607`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140023784`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400238f4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002393e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002353c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002358c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400235d6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140023753`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400238c3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002390d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002353c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002358c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400235d6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140023753`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400238c3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002390d`
- `ntoskrnl!RtlSetBit` at `0x14002308b`
- `ntoskrnl!RtlSetBit` at `0x14002308b`

## pseudocode

```c
__int64 __fastcall SIO_RAID::Initialize(
        SIO_RAID *this,
        SC_SPARSE **a2,
        unsigned __int64 a3,
        struct SIO_SPACE *a4,
        struct SIO_TIER *a5)
{
  bool v5; // r15
  __int64 v10; // rax
  int v11; // ebp
  unsigned int v12; // edi
  unsigned int v13; // esi
  _WORD *i; // rax
  __int16 v15; // r8
  char *v16; // rcx
  char *v17; // r9
  char *v18; // rdx
  int v19; // ecx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rax
  unsigned int v23; // eax
  _DWORD *v24; // rax
  __int64 v25; // rax
  __int64 Pool2; // rax
  __int64 v27; // r9
  char v28; // r15
  unsigned int v29; // r14d
  unsigned int v30; // ebp
  unsigned int v31; // esi
  __int64 v32; // rax
  __int64 v33; // rax
  unsigned int j; // edi
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  unsigned int v39; // eax
  _BYTE *Object; // rdi
  char *v41; // rax
  char *v42; // r15
  char *v43; // rsi
  __int64 v44; // r14
  unsigned int v45; // ebp
  __int64 v46; // rdx
  __int64 k; // rcx
  struct SDB_RECORD *SpaceById; // rax
  SDB_SPACE **v49; // rcx
  struct SDB_RECORD *Extent; // rax
  char *v51; // rax
  int v52; // edi
  _BYTE *v53; // r13
  unsigned int v54; // r12d
  char *v55; // rax
  __int64 v56; // r15
  __int64 v57; // rdx
  unsigned int v58; // eax
  __int64 v59; // rax
  __int64 v60; // rax
  __int16 v61; // ax
  unsigned int v62; // esi
  __int64 v63; // rcx
  __int64 v64; // rcx
  _WORD *v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // rax
  __int64 v68; // rdx
  __int64 v69; // rcx
  __int64 v70; // rdx
  __int64 v71; // rcx
  __int64 v72; // rcx
  __int64 v73; // rcx
  __int64 v74; // rcx
  __int64 v75; // rcx
  __int64 RecordByRecordId; // rax
  __int64 v77; // rax
  __int64 v78; // rbp
  __int64 v79; // rdi
  __int64 v80; // r9
  struct SC_DRIVE *Drive; // r14
  int v82; // r8d
  int v83; // ecx
  __int64 v84; // rcx
  int v85; // edx
  __int64 v86; // rcx
  char v87; // al
  __int64 v88; // rax
  __int64 v89; // rax
  char *v90; // rax
  __int64 v91; // r9
  __int16 v92; // r8
  __int64 v93; // rcx
  __int64 v94; // rcx
  int v95; // edx
  int v96; // ecx
  int v97; // ecx
  int v98; // ecx
  int v99; // ecx
  _QWORD *v100; // rax
  _QWORD *v101; // rcx
  char v102; // dl
  int v103; // r8d
  unsigned int m; // esi
  __int64 v105; // rax
  __int64 v106; // rax
  unsigned int v107; // r9d
  unsigned int v108; // ebp
  __int64 v109; // r8
  __int64 v110; // rcx
  __int64 v111; // r10
  __int16 *v112; // r14
  int v113; // edi
  int v114; // edx
  __int64 v115; // rcx
  __int16 v116; // ax
  __int64 v117; // rax
  __int64 v118; // rax
  _WORD *v119; // rdx
  unsigned __int64 v120; // rdi
  __int64 v121; // rax
  bool v122; // cf
  __int64 v123; // rax
  unsigned __int64 *v124; // rax
  _QWORD *v125; // rbp
  SIO_BUCKET *n; // rsi
  ULONG v127; // ebp
  char v128; // di
  _BYTE *Packet; // rax
  SIO_LOG_PACKET *v130; // rsi
  PMDL Mdl; // rax
  _DWORD *DeviceExtension; // rdi
  char v133; // di
  _BYTE *v134; // rax
  SC_PACKET *v135; // rax
  _DWORD *v136; // rdi
  char v137; // di
  _BYTE *v138; // rax
  SC_PACKET *v139; // rax
  unsigned int v140; // edi
  ULONG v141; // edx
  unsigned int v142; // edi
  ULONG v143; // edx
  unsigned int v144; // edi
  ULONG v145; // edx
  int v146; // edi
  bool v147; // r14
  char v148; // di
  _BYTE *v149; // rax
  SIO_LOG_PACKET *v150; // rax
  __int64 v151; // rdi
  PMDL v152; // rax
  PVOID MappingAddress; // rax
  unsigned int v154; // edi
  ULONG v155; // edx
  char v156; // di
  _BYTE *v157; // rax
  SC_PACKET *v158; // rax
  char v159; // di
  _BYTE *v160; // rax
  SC_PACKET *v161; // rax
  unsigned int v162; // edi
  ULONG v163; // edx
  unsigned int v164; // edi
  ULONG v165; // edx
  __int64 v166; // rcx
  __int64 v167; // rdx
  __int64 v168; // rax
  __int64 v169; // r11
  _QWORD *v170; // rcx
  _QWORD *v171; // rax
  __int64 v172; // rax
  int v173; // r8d
  __int64 v174; // rdx
  unsigned __int64 v175; // rdx
  unsigned int v176; // edx
  __int64 v177; // r11
  _DWORD *v178; // r11
  int Irp; // [rsp+20h] [rbp-68h]
  unsigned int v181; // [rsp+30h] [rbp-58h]
  ULONG Length; // [rsp+34h] [rbp-54h]
  __int64 v183; // [rsp+38h] [rbp-50h]
  char v184; // [rsp+90h] [rbp+8h]
  unsigned int v185; // [rsp+98h] [rbp+10h]
  unsigned int v186; // [rsp+A0h] [rbp+18h]
  bool v187; // [rsp+A8h] [rbp+20h]
  unsigned int v188; // [rsp+B0h] [rbp+28h]

  v5 = 0;
  *((_QWORD *)this + 4) = a5;
  *((_QWORD *)this + 1) = a4;
  *((_QWORD *)this + 2) = a3;
  v183 = *((_QWORD *)a4 + 22);
  v10 = *((_QWORD *)a4 + 47);
  v187 = 0;
  if ( v10 )
  {
    v5 = *(_QWORD *)(v10 + 16) != 0;
    v187 = v5;
  }
  v11 = 0;
  v12 = 0;
  v13 = 0;
  for ( i = SC_SPARSE::GetObject(a2[29], a3 / (unsigned __int64)a2[34]); i; i = *(_WORD **)(*(_QWORD *)v18 + 80LL) )
  {
    v15 = i[15] & 1;
    if ( v15 )
    {
      v16 = (char *)(i + 20);
      v17 = (char *)(i + 20);
      v18 = (char *)(i + 16);
    }
    else
    {
      v16 = (char *)(i + 16);
      v18 = (char *)(i + 16);
      v17 = (char *)(i + 20);
    }
    v19 = *(_DWORD *)(*(_QWORD *)v16 + 64LL);
    if ( v19 != v11 )
    {
      v11 = v19;
      v13 = 0;
    }
    if ( v12 <= ++v13 )
      v12 = v13;
    if ( v15 )
      v18 = v17;
  }
  *((_BYTE *)this + 43) = v12;
  if ( (unsigned __int8)v12 > 1u )
  {
    *((_DWORD *)a4 + 11) |= 4u;
    LOBYTE(v12) = *((_BYTE *)this + 43);
  }
  v20 = *((_QWORD *)this + 4);
  v21 = v20 + 88;
  if ( v20 )
    v22 = v20 + 88;
  else
    v22 = *((_QWORD *)this + 1) + 80LL;
  if ( *(_DWORD *)(v22 + 16) <= 1u )
  {
    v23 = 0x1000000;
    if ( v5 )
      v23 = 0x40000;
  }
  else if ( v20 )
  {
    v23 = *(_DWORD *)(v20 + 108);
  }
  else
  {
    v23 = *(_DWORD *)(*((_QWORD *)this + 1) + 100LL);
  }
  Length = v23;
  _BitScanReverse(&v23, v23);
  *((_BYTE *)this + 42) = v23;
  if ( v20 )
    v24 = (_DWORD *)(v20 + 88);
  else
    v24 = (_DWORD *)(*((_QWORD *)this + 1) + 80LL);
  if ( *v24 == 1 )
    *((_WORD *)this + 20) |= 0x20u;
  if ( (unsigned __int8)v12 > 1u )
    *((_WORD *)this + 20) |= 2u;
  if ( !v20 )
    v21 = *((_QWORD *)this + 1) + 80LL;
  v25 = 32LL * *(_DWORD *)(v21 + 16) * (unsigned int)(unsigned __int8)v12;
  if ( !is_mul_ok(*(_DWORD *)(v21 + 16) * (unsigned int)(unsigned __int8)v12, 0x20u) )
    v25 = -1;
  Pool2 = ExAllocatePool2(64, v25, 1816752211);
  *((_QWORD *)this + 6) = Pool2;
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v184 = 0;
  v186 = 0;
  v31 = 0;
  v185 = 0;
  while ( 1 )
  {
    v32 = *((_QWORD *)this + 4);
    v33 = v32 ? v32 + 88 : *((_QWORD *)this + 1) + 80LL;
    if ( v31 >= *(_DWORD *)(v33 + 16) )
      break;
    for ( j = 0;
          j < *((unsigned __int8 *)this + 43);
          *(_DWORD *)(32LL * (v31 + *(_DWORD *)(v38 + 16) * v39) + *((_QWORD *)this + 6) + 20) = -1 )
    {
      LOBYTE(v27) = 7;
      LOBYTE(Irp) = 0;
      SIO_RAID::SetColumnActiveState(this, v31, j, v27, Irp);
      v35 = *((_QWORD *)this + 4);
      if ( v35 )
        v36 = v35 + 88;
      else
        v36 = *((_QWORD *)this + 1) + 80LL;
      *(_DWORD *)(32LL * (v31 + *(_DWORD *)(v36 + 16) * j) + *((_QWORD *)this + 6) + 16) = -1;
      v37 = *((_QWORD *)this + 4);
      if ( v37 )
        v38 = v37 + 88;
      else
        v38 = *((_QWORD *)this + 1) + 80LL;
      v39 = j++;
    }
    ++v31;
  }
  Object = SC_SPARSE::GetObject(a2[29], a3 / (unsigned __int64)a2[34]);
  if ( Object )
  {
    do
    {
      if ( (Object[30] & 1) != 0 )
      {
        v41 = Object + 40;
        v42 = Object + 40;
        v43 = Object + 32;
      }
      else
      {
        v41 = Object + 32;
        v43 = Object + 32;
        v42 = Object + 40;
      }
      v44 = *(_QWORD *)v41;
      v45 = *(_DWORD *)(*(_QWORD *)v41 + 72LL);
      if ( v45 != -1 )
      {
        v46 = *((_QWORD *)this + 1);
        for ( k = v46; *(_QWORD *)(k + 280); k = *(_QWORD *)(k + 280) )
          ;
        SpaceById = SDB_POOL_CONFIG::FindSpaceById(*(SDB_POOL_CONFIG **)(k + 144), (struct _GUID *)(v46 + 24));
        v49 = (SDB_SPACE **)((char *)SpaceById + 40);
        if ( (*((_BYTE *)SpaceById + 30) & 1) == 0 )
          v49 = (SDB_SPACE **)((char *)SpaceById + 32);
        Extent = SDB_SPACE::FindExtent(*v49, *((_QWORD *)this + 2), *(_DWORD *)(v44 + 64), v45);
        if ( (*((_BYTE *)Extent + 30) & 1) != 0 )
          v51 = (char *)Extent + 40;
        else
          v51 = (char *)Extent + 32;
        *(_WORD *)(*(_QWORD *)v51 + 78LL) |= 2u;
      }
      if ( (Object[30] & 1) != 0 )
        v43 = v42;
      Object = *(_BYTE **)(*(_QWORD *)v43 + 80LL);
    }
    while ( Object );
    v30 = 0;
    v29 = 0;
    v28 = 0;
  }
  v52 = -1;
  v181 = -1;
  v53 = SC_SPARSE::GetObject(a2[29], a3 / (unsigned __int64)a2[34]);
  v54 = -1;
  if ( v53 )
  {
    while ( 1 )
    {
      v55 = v53 + 40;
      if ( (v53[30] & 1) == 0 )
        v55 = v53 + 32;
      v56 = *(_QWORD *)v55;
      v57 = *((_QWORD *)this + 1);
      v58 = *(_DWORD *)(*(_QWORD *)v55 + 64LL);
      if ( v58 != v52 )
      {
        v29 = 0;
        v181 = v58;
        v52 = v58;
        v186 = 0;
        v59 = *((_QWORD *)this + 4);
        if ( v59 )
          v60 = v59 + 88;
        else
          v60 = v57 + 80;
        v30 = *(_DWORD *)(v60 + 8);
        v185 = v30;
      }
      v61 = *(_WORD *)(v56 + 78);
      if ( (v61 & 2) != 0 )
      {
        v62 = v30;
        *(_WORD *)(v56 + 78) = v61 & 0xFFFD;
        v63 = *((_QWORD *)this + 4);
        v185 = v30 + 1;
        if ( v63 )
          v64 = v63 + 88;
        else
          v64 = *((_QWORD *)this + 1) + 80LL;
        v65 = (_WORD *)(*((_QWORD *)this + 6) + 32LL * (v52 + *(_DWORD *)(v64 + 16) * v30));
        *v65 |= 4u;
        v57 = *((_QWORD *)this + 1);
      }
      else
      {
        v62 = v29;
        v186 = v29 + 1;
      }
      v66 = *((_QWORD *)this + 4);
      v67 = v57 + 80;
      v68 = v66 + 88;
      if ( !v66 )
        v68 = v67;
      *(_DWORD *)(32LL * (v52 + *(_DWORD *)(v68 + 16) * v62) + *((_QWORD *)this + 6) + 16) = *(_DWORD *)(v56 + 68);
      v69 = *((_QWORD *)this + 4);
      v70 = *(unsigned int *)(v56 + 72);
      if ( v69 )
        v71 = v69 + 88;
      else
        v71 = *((_QWORD *)this + 1) + 80LL;
      *(_DWORD *)(32LL * (v52 + *(_DWORD *)(v71 + 16) * v62) + *((_QWORD *)this + 6) + 20) = v70;
      if ( (*(_BYTE *)(v56 + 76) & 2) != 0 )
      {
        v72 = *((_QWORD *)this + 4);
        if ( v72 )
          v73 = v72 + 88;
        else
          v73 = *((_QWORD *)this + 1) + 80LL;
        v70 = *((_QWORD *)this + 6) + 32LL * (v52 + *(_DWORD *)(v73 + 16) * v62);
        *(_WORD *)v70 |= 0x10u;
      }
      if ( (*(_BYTE *)(v56 + 76) & 8) != 0 )
      {
        v74 = *((_QWORD *)this + 4);
        if ( v74 )
          v75 = v74 + 88;
        else
          v75 = *((_QWORD *)this + 1) + 80LL;
        v70 = *((_QWORD *)this + 6) + 32LL * (v52 + *(_DWORD *)(v75 + 16) * v62);
        *(_WORD *)v70 |= 0x20u;
      }
      LOBYTE(v70) = 2;
      RecordByRecordId = SDB_POOL_CONFIG::FindRecordByRecordId(
                           *(_QWORD *)(*(_QWORD *)(v56 + 16) + 16LL),
                           v70,
                           *(unsigned int *)(v56 + 60));
      if ( (*(_BYTE *)(RecordByRecordId + 30) & 1) != 0 )
        v77 = RecordByRecordId + 40;
      else
        v77 = RecordByRecordId + 32;
      v78 = *(_QWORD *)v77;
      v79 = *(_QWORD *)(*(_QWORD *)v77 + 16LL);
      Drive = SIO_SPACE::GetDrive(*((SIO_SPACE **)this + 1), *(_DWORD *)(v79 + 24));
      if ( *(_DWORD *)(v78 + 68) == 5 && *(_DWORD *)(v56 + 72) == -1 )
      {
        ++*(_QWORD *)(v183 + 368);
        v79 = *(_QWORD *)(v78 + 16);
      }
      v82 = 0;
      if ( *(_DWORD *)(v78 + 108) != 1 )
        break;
LABEL_112:
      if ( v54 >= v82 + 1 )
      {
LABEL_113:
        v83 = 0;
        v188 = 0;
        if ( *(_DWORD *)(v78 + 108) != 1 )
        {
          if ( *(_DWORD *)(v78 + 108) != 2 )
          {
            if ( *(_DWORD *)(v78 + 108) == 3 )
              goto LABEL_119;
            if ( *(_DWORD *)(v78 + 108) != 4 )
            {
              if ( *(_DWORD *)(v78 + 108) == 5 )
              {
                v83 = 1;
LABEL_119:
                ++v83;
                goto LABEL_120;
              }
LABEL_123:
              v54 = v188;
              goto LABEL_124;
            }
LABEL_120:
            ++v83;
          }
          ++v83;
        }
        v188 = v83 + 1;
        goto LABEL_123;
      }
LABEL_124:
      v84 = *((_QWORD *)this + 4);
      v85 = *(_DWORD *)(v79 + 24);
      if ( v84 )
        v86 = v84 + 88;
      else
        v86 = *((_QWORD *)this + 1) + 80LL;
      v52 = v181;
      *(_DWORD *)(32LL * (v181 + *(_DWORD *)(v86 + 16) * v62) + *((_QWORD *)this + 6) + 4) = v85;
      if ( (*(_BYTE *)(v56 + 76) & 1) != 0 )
      {
        LOBYTE(v80) = 3;
        v87 = 7;
      }
      else if ( Drive )
      {
        LOBYTE(v80) = 1;
        v87 = 0;
      }
      else
      {
        LOBYTE(v80) = 2;
        v87 = 1;
      }
      LOBYTE(Irp) = v87;
      SIO_RAID::SetColumnActiveState(this, v181, v62, v80, Irp);
      v88 = *((_QWORD *)this + 4);
      if ( v88 )
        v89 = v88 + 88;
      else
        v89 = *((_QWORD *)this + 1) + 80LL;
      *(_QWORD *)(32LL * (v181 + *(_DWORD *)(v89 + 16) * v62) + *((_QWORD *)this + 6) + 8) = *(_QWORD *)(v56 + 48);
      if ( Drive )
      {
        RtlSetBit((PRTL_BITMAP)(*((_QWORD *)this + 1) + 256LL), *(_DWORD *)(*(_QWORD *)(v78 + 16) + 24LL));
        v28 = v184;
        if ( *((_BYTE *)Drive + 403) )
          v28 = 1;
        v184 = v28;
      }
      else
      {
        v28 = v184;
      }
      v90 = v53 + 40;
      if ( (v53[30] & 1) == 0 )
        v90 = v53 + 32;
      v30 = v185;
      v29 = v186;
      v53 = *(_BYTE **)(*(_QWORD *)v90 + 80LL);
      if ( !v53 )
      {
        if ( v28 )
          *((_WORD *)this + 20) |= 0x200u;
        goto LABEL_145;
      }
    }
    if ( *(_DWORD *)(v78 + 108) == 2 )
    {
LABEL_111:
      ++v82;
      goto LABEL_112;
    }
    if ( *(_DWORD *)(v78 + 108) != 3 )
    {
      if ( *(_DWORD *)(v78 + 108) == 4 )
      {
LABEL_110:
        ++v82;
        goto LABEL_111;
      }
      if ( *(_DWORD *)(v78 + 108) != 5 )
        goto LABEL_113;
      v82 = 1;
    }
    ++v82;
    goto LABEL_110;
  }
LABEL_145:
  v91 = *((_QWORD *)this + 1);
  v92 = *((_WORD *)this + 20);
  v93 = *(_QWORD *)(v91 + 376);
  if ( !v93 )
    goto LABEL_160;
  v94 = *(_QWORD *)(v93 + 16);
  if ( !v94 || (v92 & 1) != 0 )
    goto LABEL_160;
  v95 = 0;
  v96 = *(_DWORD *)(v94 + 64) - 1;
  if ( v96 )
  {
    v97 = v96 - 1;
    if ( !v97 )
    {
LABEL_156:
      ++v95;
      goto LABEL_157;
    }
    v98 = v97 - 1;
    if ( v98 )
    {
      v99 = v98 - 1;
      if ( !v99 )
      {
LABEL_155:
        ++v95;
        goto LABEL_156;
      }
      if ( v99 != 1 )
      {
LABEL_159:
        *((_WORD *)this + 20) = v92 | 8;
        goto LABEL_160;
      }
      v95 = 1;
    }
    ++v95;
    goto LABEL_155;
  }
LABEL_157:
  if ( v54 >= v95 + 1 || v28 )
    goto LABEL_159;
LABEL_160:
  v100 = *(_QWORD **)(v91 + 296);
  if ( v100 == (_QWORD *)(v91 + 296) )
  {
    v101 = 0;
    v102 = 0;
  }
  else
  {
    while ( 1 )
    {
      v101 = v100 - 39;
      if ( *((_BYTE *)v100 - 272) == 11 )
        break;
      v100 = (_QWORD *)*v100;
      if ( v100 == (_QWORD *)(v91 + 296) )
        goto LABEL_181;
    }
    v102 = 1;
  }
  if ( !v102 )
    v101 = 0;
  if ( v101 && !v28 )
  {
    v103 = 0;
    switch ( *((_DWORD *)v101 + 16) )
    {
      case 1:
        goto LABEL_179;
      case 2:
LABEL_178:
        ++v103;
LABEL_179:
        if ( v54 < v103 + 1 )
          *((_WORD *)this + 20) |= 0x100u;
        break;
      case 3:
        goto LABEL_176;
      case 4:
LABEL_177:
        ++v103;
        goto LABEL_178;
      case 5:
        v103 = 1;
LABEL_176:
        ++v103;
        goto LABEL_177;
    }
  }
LABEL_181:
  for ( m = 0; ; ++m )
  {
    v105 = *((_QWORD *)this + 4);
    v106 = v105 ? v105 + 88 : *((_QWORD *)this + 1) + 80LL;
    if ( m >= *(_DWORD *)(v106 + 16) )
      break;
    LOBYTE(v107) = *((_BYTE *)this + 43);
    if ( (_BYTE)v107 )
    {
      v108 = 0;
      do
      {
        v109 = *((_QWORD *)this + 4);
        if ( v109 )
          v110 = v109 + 88;
        else
          v110 = *((_QWORD *)this + 1) + 80LL;
        v111 = *((_QWORD *)this + 6);
        v112 = (__int16 *)(v111 + 32LL * (m + *(_DWORD *)(v110 + 16) * v108));
        v113 = *((_DWORD *)v112 + 5);
        if ( v113 != -1 )
        {
          v114 = 0;
          if ( (_BYTE)v107 )
          {
            while ( 1 )
            {
              v115 = v109 ? v109 + 88 : *((_QWORD *)this + 1) + 80LL;
              if ( *(_DWORD *)(32LL * (m + *(_DWORD *)(v115 + 16) * v114) + v111 + 16) == v113 )
                break;
              if ( ++v114 >= (unsigned int)(unsigned __int8)v107 )
                goto LABEL_198;
            }
          }
          else
          {
LABEL_198:
            v114 = -1;
          }
          v116 = *v112;
          *((_DWORD *)v112 + 5) = v114;
          if ( (v116 & 0x10) != 0 )
          {
            v117 = *((_QWORD *)this + 4);
            if ( v117 )
              v118 = v117 + 88;
            else
              v118 = *((_QWORD *)this + 1) + 80LL;
            v119 = (_WORD *)(*((_QWORD *)this + 6) + 32LL * (m + *((_DWORD *)v112 + 5) * *(_DWORD *)(v118 + 16)));
            *v119 |= 0x10u;
          }
        }
        v107 = *((unsigned __int8 *)this + 43);
        ++v108;
      }
      while ( v108 < v107 );
    }
  }
  if ( (*((_BYTE *)this + 40) & 2) != 0 )
  {
    v120 = *((unsigned int *)WPP_MAIN_CB.DeviceExtension + 151);
    v121 = 24 * v120;
    if ( !is_mul_ok(v120, 0x18u) )
      v121 = -1;
    v122 = __CFADD__(v121, 8);
    v123 = v121 + 8;
    if ( v122 )
      v123 = -1;
    v124 = (unsigned __int64 *)ExAllocatePool2(64, v123, 1682534483);
    if ( !v124 )
    {
      *((_QWORD *)this + 7) = 0;
      return (unsigned int)-1073741670;
    }
    *v124 = v120;
    v125 = v124 + 1;
    for ( n = (SIO_BUCKET *)(v124 + 1); v120; --v120 )
    {
      SIO_BUCKET::SIO_BUCKET(n);
      n = (SIO_BUCKET *)((char *)n + 24);
    }
    *((_QWORD *)this + 7) = v125;
    if ( !v125 )
      return (unsigned int)-1073741670;
  }
  v127 = *((_DWORD *)WPP_MAIN_CB.DeviceExtension + 113);
  if ( Length < v127 )
    v127 = Length;
  if ( v127 && !*(_QWORD *)(*((_QWORD *)this + 1) + 560LL) )
  {
    if ( *((_BYTE *)WPP_MAIN_CB.DeviceExtension + 435) )
    {
      v128 = -1;
    }
    else
    {
      v140 = *((_DWORD *)WPP_MAIN_CB.DeviceExtension + 84);
      v141 = KeGetCurrentProcessorNumberEx(0) % v140;
      v128 = v141;
      if ( (_BYTE)v141 != 0xFF )
      {
        Packet = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 43)
                                                                          + ((unsigned __int64)(unsigned __int8)v141 << 7)));
        goto LABEL_222;
      }
    }
    Packet = SP_CONTROL::AllocatePacket((POOL_TYPE)512, 0x118u, 0x4B507053u);
LABEL_222:
    if ( !Packet )
      return (unsigned int)-1073741670;
    Packet[171] = v128;
    *((_WORD *)Packet + 86) = 0;
    v130 = SIO_LOG_PACKET::SIO_LOG_PACKET((SIO_LOG_PACKET *)Packet);
    if ( !v130 )
      return (unsigned int)-1073741670;
    Mdl = IoAllocateMdl((PVOID)0xFFF, v127, 0, 0, 0);
    *((_QWORD *)v130 + 15) = Mdl;
    if ( !Mdl )
      goto LABEL_254;
    DeviceExtension = WPP_MAIN_CB.DeviceExtension;
    *((_DWORD *)v130 + 28) = 2;
    *((_WORD *)v130 + 58) = -1;
    *(_BYTE *)(*((_QWORD *)this + 1) + 604LL) = 1;
    *(_QWORD *)(*((_QWORD *)this + 1) + 560LL) = v130;
    *(_DWORD *)(*((_QWORD *)this + 1) + 600LL) = v127;
    if ( *((_BYTE *)DeviceExtension + 435) )
    {
      v133 = -1;
    }
    else
    {
      v142 = DeviceExtension[84];
      v143 = KeGetCurrentProcessorNumberEx(0) % v142;
      v133 = v143;
      if ( (_BYTE)v143 != 0xFF )
      {
        v134 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 43)
                                                                        + ((unsigned __int64)(unsigned __int8)v143 << 7)));
        goto LABEL_228;
      }
    }
    v134 = SP_CONTROL::AllocatePacket((POOL_TYPE)512, 0xF8u, 0x4B507053u);
LABEL_228:
    if ( !v134 )
      return (unsigned int)-1073741670;
    v134[171] = v133;
    *((_WORD *)v134 + 86) = 0;
    v135 = SC_PACKET::SC_PACKET((SC_PACKET *)v134);
    if ( !v135 )
      return (unsigned int)-1073741670;
    v136 = WPP_MAIN_CB.DeviceExtension;
    *(_BYTE *)(*((_QWORD *)this + 1) + 676LL) = 1;
    *(_QWORD *)(*((_QWORD *)this + 1) + 632LL) = v135;
    if ( *((_BYTE *)v136 + 435) )
    {
      v137 = -1;
    }
    else
    {
      v144 = v136[84];
      v145 = KeGetCurrentProcessorNumberEx(0) % v144;
      v137 = v145;
      if ( (_BYTE)v145 != 0xFF )
      {
        v138 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 43)
                                                                        + ((unsigned __int64)(unsigned __int8)v145 << 7)));
LABEL_233:
        if ( !v138 )
          return (unsigned int)-1073741670;
        v138[171] = v137;
        *((_WORD *)v138 + 86) = 0;
        v139 = SC_PACKET::SC_PACKET((SC_PACKET *)v138);
        if ( !v139 )
          return (unsigned int)-1073741670;
        *(_BYTE *)(*((_QWORD *)this + 1) + 820LL) = 1;
        *(_QWORD *)(*((_QWORD *)this + 1) + 776LL) = v139;
        goto LABEL_244;
      }
    }
    v138 = SP_CONTROL::AllocatePacket((POOL_TYPE)512, 0xF8u, 0x4B507053u);
    goto LABEL_233;
  }
  v146 = 0;
  if ( !v127 )
  {
    v147 = v187;
    goto LABEL_278;
  }
LABEL_244:
  v146 = 0;
  v147 = v187;
  if ( *(_QWORD *)(*((_QWORD *)this + 1) + 704LL) || v187 )
    goto LABEL_259;
  if ( *((_BYTE *)WPP_MAIN_CB.DeviceExtension + 435) )
  {
    v148 = -1;
LABEL_248:
    v149 = SP_CONTROL::AllocatePacket((POOL_TYPE)512, 0x118u, 0x4B507053u);
    goto LABEL_249;
  }
  v154 = *((_DWORD *)WPP_MAIN_CB.DeviceExtension + 84);
  v155 = KeGetCurrentProcessorNumberEx(0) % v154;
  v148 = v155;
  if ( (_BYTE)v155 == 0xFF )
    goto LABEL_248;
  v149 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 43)
                                                                  + ((unsigned __int64)(unsigned __int8)v155 << 7)));
LABEL_249:
  if ( !v149 )
    return (unsigned int)-1073741670;
  v149[171] = v148;
  *((_WORD *)v149 + 86) = 0;
  v150 = SIO_LOG_PACKET::SIO_LOG_PACKET((SIO_LOG_PACKET *)v149);
  v130 = v150;
  if ( !v150 )
    return (unsigned int)-1073741670;
  v146 = SC_BUFFER::Initialize((char *)v150 + 112, 3, 0, v127);
  if ( v146 < 0 )
  {
LABEL_255:
    (**(void (__fastcall ***)(SIO_LOG_PACKET *, __int64))v130)(v130, 1);
    return (unsigned int)v146;
  }
  *(_BYTE *)(*((_QWORD *)this + 1) + 748LL) = 1;
  v151 = *((_QWORD *)this + 1);
  v152 = IoAllocateMdl((PVOID)0xFFF, v127, 0, 0, 0);
  *(_QWORD *)(v151 + 720) = v152;
  if ( !v152
    || (*(_DWORD *)(v151 + 712) = 2,
        *(_WORD *)(v151 + 716) = -1,
        (MappingAddress = MmAllocateMappingAddress((v127 + 0x1FFF) & 0xFFFFF000, 0x6C4D7053u)) == 0) )
  {
LABEL_254:
    v146 = -1073741670;
    goto LABEL_255;
  }
  v146 = 0;
  *(_QWORD *)(*((_QWORD *)this + 1) + 704LL) = v130;
  *(_QWORD *)(*((_QWORD *)this + 1) + 728LL) = MappingAddress;
  *(_DWORD *)(*((_QWORD *)this + 1) + 744LL) = v127;
LABEL_259:
  if ( *(_QWORD *)(*((_QWORD *)this + 1) + 848LL) )
    goto LABEL_266;
  if ( *((_BYTE *)WPP_MAIN_CB.DeviceExtension + 435) )
  {
    v156 = -1;
LABEL_262:
    v157 = SP_CONTROL::AllocatePacket((POOL_TYPE)512, 0xF8u, 0x4B507053u);
    goto LABEL_263;
  }
  v162 = *((_DWORD *)WPP_MAIN_CB.DeviceExtension + 84);
  v163 = KeGetCurrentProcessorNumberEx(0) % v162;
  v156 = v163;
  if ( (_BYTE)v163 == 0xFF )
    goto LABEL_262;
  v157 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 43)
                                                                  + ((unsigned __int64)(unsigned __int8)v163 << 7)));
LABEL_263:
  if ( !v157 )
    return (unsigned int)-1073741670;
  v157[171] = v156;
  *((_WORD *)v157 + 86) = 0;
  v158 = SC_PACKET::SC_PACKET((SC_PACKET *)v157);
  if ( !v158 )
    return (unsigned int)-1073741670;
  v146 = 0;
  *(_BYTE *)(*((_QWORD *)this + 1) + 892LL) = 1;
  *(_QWORD *)(*((_QWORD *)this + 1) + 848LL) = v158;
LABEL_266:
  if ( *(_QWORD *)(*((_QWORD *)this + 1) + 920LL) )
    goto LABEL_278;
  if ( *((_BYTE *)WPP_MAIN_CB.DeviceExtension + 435) )
  {
    v159 = -1;
LABEL_269:
    v160 = SP_CONTROL::AllocatePacket((POOL_TYPE)512, 0xF8u, 0x4B507053u);
    goto LABEL_270;
  }
  v164 = *((_DWORD *)WPP_MAIN_CB.DeviceExtension + 84);
  v165 = KeGetCurrentProcessorNumberEx(0) % v164;
  v159 = v165;
  if ( (_BYTE)v165 == 0xFF )
    goto LABEL_269;
  v160 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 43)
                                                                  + ((unsigned __int64)(unsigned __int8)v165 << 7)));
LABEL_270:
  if ( !v160 )
    return (unsigned int)-1073741670;
  v160[171] = v159;
  *((_WORD *)v160 + 86) = 0;
  v161 = SC_PACKET::SC_PACKET((SC_PACKET *)v160);
  if ( !v161 )
    return (unsigned int)-1073741670;
  v146 = 0;
  *(_BYTE *)(*((_QWORD *)this + 1) + 964LL) = 1;
  *(_QWORD *)(*((_QWORD *)this + 1) + 920LL) = v161;
LABEL_278:
  v166 = 0;
  v167 = *(_QWORD *)(*((_QWORD *)this + 1) + 152LL);
  if ( v167 )
    v166 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v167 + 392) + 104LL))(
             *(_QWORD *)(v167 + 392),
             *((_QWORD *)this + 2));
  if ( v147 && (!v166 || !*(_QWORD *)(v166 + 64)) )
  {
    v168 = ExAllocatePool2(64, 296, 1682534483);
    v169 = v168;
    if ( v168 )
    {
      *(_QWORD *)(v168 + 16) = 0;
      *(_QWORD *)(v168 + 56) = 0;
      *(_DWORD *)(v168 + 64) = 1;
      *(_DWORD *)(v168 + 68) = 64;
      *(_DWORD *)(v168 + 72) = 6;
      *(_QWORD *)(v168 + 80) = 64;
      *(_DWORD *)(v168 + 88) = 6;
      *(_QWORD *)(v168 + 32) = v168 + 24;
      *(_QWORD *)(v168 + 24) = v168 + 24;
      v170 = (_QWORD *)(v168 + 40);
      v171 = (_QWORD *)(v168 + 120);
      v170[1] = v170;
      *v170 = v170;
      *(_DWORD *)(v169 + 8) = 0;
      v171[1] = v171;
      *v171 = v171;
      *(_QWORD *)(v169 + 144) = v169 + 136;
      *(_QWORD *)(v169 + 136) = v169 + 136;
      *(_QWORD *)(v169 + 184) = v169 + 176;
      *(_QWORD *)(v169 + 176) = v169 + 176;
      *(_QWORD *)(v169 + 200) = v169 + 192;
      *(_QWORD *)(v169 + 192) = v169 + 192;
      *(_QWORD *)v169 = &SIO_LOG_TABLE::`vftable';
      *(_QWORD *)(v169 + 240) = v169 + 232;
      *(_QWORD *)(v169 + 232) = v169 + 232;
      *(_QWORD *)(v169 + 256) = v169 + 248;
      *(_QWORD *)(v169 + 248) = v169 + 248;
      *(_QWORD *)(v169 + 272) = v169 + 264;
      *(_QWORD *)(v169 + 264) = v169 + 264;
      *(_QWORD *)(v169 + 288) = v169 + 280;
      *(_QWORD *)(v169 + 280) = v169 + 280;
      v172 = *((_QWORD *)this + 4);
      *((_QWORD *)this + 8) = v169;
      if ( v172 )
      {
        v173 = *(_DWORD *)(v172 + 104);
        v174 = v172 + 56;
      }
      else
      {
        v174 = *((_QWORD *)this + 1) + 48LL;
        v173 = *(_DWORD *)(*((_QWORD *)this + 1) + 96LL);
      }
      v175 = *(_QWORD *)(v174 + 8) >> *((_BYTE *)this + 42);
      *(_DWORD *)(v169 + 8) = v173;
      v146 = SC_SPARSE::Initialize((SC_SPARSE *)(v169 + 16), v175);
      if ( v146 >= 0 )
      {
        *(_DWORD *)(v177 + 104) = 0x10000;
        *(_DWORD *)(v177 + 96) = 80;
        *(_DWORD *)(v177 + 108) = 16;
        *(_DWORD *)(v177 + 112) = 50;
        *(_DWORD *)(v177 + 100) = 800;
        v146 = SC_SLAB_ALLOCATOR::Initialize((SC_SLAB_ALLOCATOR *)(v177 + 152), v176, 16 * *(_WORD *)(v177 + 8));
        if ( v146 >= 0 )
        {
          v178[54] = 0x10000;
          v178[52] = 64;
          v178[55] = 16;
          v178[56] = 63;
          v178[53] = 1008;
          return 0;
        }
      }
      return (unsigned int)v146;
    }
    *((_QWORD *)this + 8) = 0;
    return (unsigned int)-1073741670;
  }
  return (unsigned int)v146;
}

```

## disassembly

```asm
0x1400229d0  push    rbx
0x1400229d2  push    rbp
0x1400229d3  push    rsi
0x1400229d4  push    rdi
0x1400229d5  push    r12
0x1400229d7  push    r13
0x1400229d9  push    r14
0x1400229db  push    r15
0x1400229dd  sub     rsp, 48h
0x1400229e1  mov     rax, [rsp+88h+arg_20]
0x1400229e9  xor     r15b, r15b
0x1400229ec  mov     [rcx+20h], rax
0x1400229f0  mov     rbx, rcx
0x1400229f3  mov     [rcx+8], r9
0x1400229f7  mov     r14, r9
0x1400229fa  mov     [rcx+10h], r8
0x1400229fe  mov     r12, r8
0x140022a01  mov     rax, [r9+0B0h]
0x140022a08  mov     r13, rdx
0x140022a0b  mov     [rsp+88h+var_50], rax
0x140022a10  mov     ecx, 1
0x140022a15  mov     rax, [r9+178h]
0x140022a1c  mov     [rsp+88h+arg_18], r15d
0x140022a24  mov     [rsp+88h+arg_0], 0
0x140022a2f  test    rax, rax
0x140022a32  jz      short loc_140022A49
0x140022a34  cmp     qword ptr [rax+10h], 0
0x140022a39  movzx   r15d, r15b
0x140022a3d  cmovnz  r15d, ecx
0x140022a41  mov     [rsp+88h+arg_18], r15d
0x140022a49  mov     rcx, [r13+0E8h]; this
0x140022a50  xor     edx, edx
0x140022a52  mov     rax, r12
0x140022a55  xor     ebp, ebp
0x140022a57  div     qword ptr [r13+110h]
0x140022a5e  xor     edi, edi
0x140022a60  xor     esi, esi
0x140022a62  mov     rdx, rax; unsigned __int64
0x140022a65  call    ?GetObject@SC_SPARSE@@QEAAPEAX_K@Z; SC_SPARSE::GetObject(unsigned __int64)
0x140022a6a  test    rax, rax
0x140022a6d  jz      short loc_140022ABD
0x140022a6f  nop
0x140022a70  movzx   r8d, word ptr [rax+1Eh]
0x140022a75  and     r8w, 1
0x140022a7a  jz      short loc_140022A89
0x140022a7c  lea     rcx, [rax+28h]
0x140022a80  mov     r9, rcx
0x140022a83  lea     rdx, [rax+20h]
0x140022a87  jmp     short loc_140022A94
0x140022a89  lea     rcx, [rax+20h]
0x140022a8d  mov     rdx, rcx
0x140022a90  lea     r9, [rax+28h]
0x140022a94  mov     rax, [rcx]
0x140022a97  mov     ecx, [rax+40h]
0x140022a9a  cmp     ecx, ebp
0x140022a9c  jz      short loc_140022AA2
0x140022a9e  mov     ebp, ecx
0x140022aa0  xor     esi, esi
0x140022aa2  inc     esi
0x140022aa4  cmp     edi, esi
0x140022aa6  cmovbe  edi, esi
0x140022aa9  test    r8w, r8w
0x140022aad  cmovnz  rdx, r9
0x140022ab1  mov     rax, [rdx]
0x140022ab4  mov     rax, [rax+50h]
0x140022ab8  test    rax, rax
0x140022abb  jnz     short loc_140022A70
0x140022abd  mov     [rbx+2Bh], dil
0x140022ac1  cmp     dil, 1
0x140022ac5  jbe     short loc_140022AD0
0x140022ac7  or      dword ptr [r14+2Ch], 4
0x140022acc  movzx   edi, byte ptr [rbx+2Bh]
0x140022ad0  mov     rdx, [rbx+20h]
0x140022ad4  lea     rcx, [rdx+58h]
0x140022ad8  test    rdx, rdx
0x140022adb  jz      short loc_140022AE2
0x140022add  mov     rax, rcx
0x140022ae0  jmp     short loc_140022AEA
0x140022ae2  mov     rax, [rbx+8]
0x140022ae6  add     rax, 50h ; 'P'
0x140022aea  cmp     dword ptr [rax+10h], 1
0x140022aee  jbe     short loc_140022B0A
0x140022af0  test    rdx, rdx
0x140022af3  jz      short loc_140022AFD
0x140022af5  mov     rax, rcx
0x140022af8  mov     eax, [rcx+14h]
0x140022afb  jmp     short loc_140022B1C
0x140022afd  mov     rax, [rbx+8]
0x140022b01  add     rax, 50h ; 'P'
0x140022b05  mov     eax, [rax+14h]
0x140022b08  jmp     short loc_140022B1C
0x140022b0a  test    r15b, r15b
0x140022b0d  mov     eax, 1000000h
0x140022b12  mov     r8d, 40000h
0x140022b18  cmovnz  eax, r8d
0x140022b1c  mov     [rsp+88h+Length], eax
0x140022b20  bsr     eax, eax
0x140022b23  mov     [rbx+2Ah], al
0x140022b26  test    rdx, rdx
0x140022b29  jz      short loc_140022B30
0x140022b2b  mov     rax, rcx
0x140022b2e  jmp     short loc_140022B38
0x140022b30  mov     rax, [rbx+8]
0x140022b34  add     rax, 50h ; 'P'
0x140022b38  cmp     dword ptr [rax], 1
0x140022b3b  jnz     short loc_140022B42
0x140022b3d  or      word ptr [rbx+28h], 20h
0x140022b42  cmp     dil, 1
0x140022b46  jbe     short loc_140022B4D
0x140022b48  or      word ptr [rbx+28h], 2
0x140022b4d  test    rdx, rdx
0x140022b50  jnz     short loc_140022B5A
0x140022b52  mov     rcx, [rbx+8]
0x140022b56  add     rcx, 50h ; 'P'
0x140022b5a  movzx   eax, dil
0x140022b5e  mov     r8d, 6C497053h
0x140022b64  imul    eax, [rcx+10h]
0x140022b68  mov     ecx, eax
0x140022b6a  mov     eax, 20h ; ' '
0x140022b6f  mul     rcx
0x140022b72  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140022b79  cmovb   rax, rcx
0x140022b7d  mov     ecx, 40h ; '@'
0x140022b82  mov     rdx, rax
0x140022b85  call    cs:__imp_ExAllocatePool2
0x140022b8c  nop     dword ptr [rax+rax+00h]
0x140022b91  mov     [rbx+30h], rax
0x140022b95  test    rax, rax
0x140022b98  jz      loc_140023B4F
0x140022b9e  xor     r15b, r15b
0x140022ba1  xor     r14d, r14d
0x140022ba4  xor     ebp, ebp
0x140022ba6  mov     [rsp+88h+arg_0], r15d
0x140022bae  mov     [rsp+88h+arg_10], r14d
0x140022bb6  xor     esi, esi
0x140022bb8  mov     [rsp+88h+arg_8], ebp
0x140022bbf  nop
0x140022bc0  mov     rax, [rbx+20h]
0x140022bc4  test    rax, rax
0x140022bc7  jz      short loc_140022BCF
0x140022bc9  add     rax, 58h ; 'X'
0x140022bcd  jmp     short loc_140022BD7
0x140022bcf  mov     rax, [rbx+8]
0x140022bd3  add     rax, 50h ; 'P'
0x140022bd7  cmp     esi, [rax+10h]
0x140022bda  jnb     loc_140022C76
0x140022be0  xor     edi, edi
0x140022be2  cmp     [rbx+2Bh], dil
0x140022be6  jbe     loc_140022C6F
0x140022bec  nop     dword ptr [rax+00h]
0x140022bf0  mov     r9b, 7
0x140022bf3  mov     byte ptr [rsp+88h+Irp], bpl
0x140022bf8  mov     r8d, edi
0x140022bfb  mov     edx, esi
0x140022bfd  mov     rcx, rbx
0x140022c00  call    ?SetColumnActiveState@SIO_RAID@@IEAAXKKW4_SC_COLUMN_STATE@@W4_SC_COLUMN_REASON@@@Z; SIO_RAID::SetColumnActiveState(ulong,ulong,_SC_COLUMN_STATE,_SC_COLUMN_REASON)
0x140022c05  mov     rcx, [rbx+20h]
0x140022c09  test    rcx, rcx
0x140022c0c  jz      short loc_140022C14
0x140022c0e  add     rcx, 58h ; 'X'
0x140022c12  jmp     short loc_140022C1C
0x140022c14  mov     rcx, [rbx+8]
0x140022c18  add     rcx, 50h ; 'P'
0x140022c1c  mov     eax, edi
0x140022c1e  imul    eax, [rcx+10h]
0x140022c22  lea     ecx, [rsi+rax]
0x140022c25  mov     rax, [rbx+30h]
0x140022c29  shl     rcx, 5
0x140022c2d  mov     dword ptr [rcx+rax+10h], 0FFFFFFFFh
0x140022c35  mov     rcx, [rbx+20h]
0x140022c39  test    rcx, rcx
0x140022c3c  jz      short loc_140022C44
0x140022c3e  add     rcx, 58h ; 'X'
0x140022c42  jmp     short loc_140022C4C
0x140022c44  mov     rcx, [rbx+8]
0x140022c48  add     rcx, 50h ; 'P'
0x140022c4c  mov     eax, edi
0x140022c4e  inc     edi
0x140022c50  imul    eax, [rcx+10h]
0x140022c54  lea     ecx, [rsi+rax]
0x140022c57  mov     rax, [rbx+30h]
0x140022c5b  shl     rcx, 5
0x140022c5f  mov     dword ptr [rcx+rax+14h], 0FFFFFFFFh
0x140022c67  movzx   eax, byte ptr [rbx+2Bh]
0x140022c6b  cmp     edi, eax
0x140022c6d  jb      short loc_140022BF0
0x140022c6f  inc     esi
0x140022c71  jmp     loc_140022BC0
0x140022c76  mov     rcx, [r13+0E8h]; this
0x140022c7d  xor     edx, edx
0x140022c7f  mov     rax, r12
0x140022c82  div     qword ptr [r13+110h]
0x140022c89  mov     rdx, rax; unsigned __int64
0x140022c8c  call    ?GetObject@SC_SPARSE@@QEAAPEAX_K@Z; SC_SPARSE::GetObject(unsigned __int64)
0x140022c91  mov     rdi, rax
0x140022c94  test    rax, rax
0x140022c97  jz      loc_140022D64
0x140022c9d  nop     dword ptr [rax]
0x140022ca0  test    byte ptr [rdi+1Eh], 1
0x140022ca4  jz      short loc_140022CB3
0x140022ca6  lea     rax, [rdi+28h]
0x140022caa  mov     r15, rax
0x140022cad  lea     rsi, [rdi+20h]
0x140022cb1  jmp     short loc_140022CBE
0x140022cb3  lea     rax, [rdi+20h]
0x140022cb7  mov     rsi, rax
0x140022cba  lea     r15, [rdi+28h]
0x140022cbe  mov     r14, [rax]
0x140022cc1  mov     ebp, [r14+48h]
0x140022cc5  cmp     ebp, 0FFFFFFFFh
0x140022cc8  jz      short loc_140022D3A
0x140022cca  mov     rdx, [rbx+8]
0x140022cce  mov     rcx, rdx
0x140022cd1  cmp     qword ptr [rdx+118h], 0
0x140022cd9  jz      short loc_140022CF1
0x140022cdb  nop     dword ptr [rax+rax+00h]
0x140022ce0  mov     rcx, [rcx+118h]
0x140022ce7  cmp     qword ptr [rcx+118h], 0
0x140022cef  jnz     short loc_140022CE0
0x140022cf1  mov     rcx, [rcx+90h]; this
0x140022cf8  add     rdx, 18h; struct _GUID *
0x140022cfc  call    ?FindSpaceById@SDB_POOL_CONFIG@@QEAAPEAVSDB_RECORD@@PEAU_GUID@@@Z; SDB_POOL_CONFIG::FindSpaceById(_GUID *)
0x140022d01  test    byte ptr [rax+1Eh], 1
0x140022d05  lea     rcx, [rax+28h]
0x140022d09  jnz     short loc_140022D0F
0x140022d0b  lea     rcx, [rax+20h]
0x140022d0f  mov     r8d, [r14+40h]; unsigned int
0x140022d13  mov     r9d, ebp; unsigned int
0x140022d16  mov     rdx, [rbx+10h]; unsigned __int64
0x140022d1a  mov     rcx, [rcx]; this
0x140022d1d  call    ?FindExtent@SDB_SPACE@@QEAAPEAVSDB_RECORD@@_KKK@Z; SDB_SPACE::FindExtent(unsigned __int64,ulong,ulong)
0x140022d22  test    byte ptr [rax+1Eh], 1
0x140022d26  jz      short loc_140022D2E
0x140022d28  add     rax, 28h ; '('
0x140022d2c  jmp     short loc_140022D32
0x140022d2e  add     rax, 20h ; ' '
0x140022d32  mov     rax, [rax]
0x140022d35  or      word ptr [rax+4Eh], 2
0x140022d3a  test    byte ptr [rdi+1Eh], 1
0x140022d3e  cmovnz  rsi, r15
0x140022d42  mov     rax, [rsi]
0x140022d45  mov     rdi, [rax+50h]
0x140022d49  test    rdi, rdi
0x140022d4c  jnz     loc_140022CA0
0x140022d52  mov     ebp, [rsp+88h+arg_8]
0x140022d59  mov     r14d, ebp
0x140022d5c  mov     r15d, [rsp+88h+arg_0]
0x140022d64  mov     rcx, [r13+0E8h]; this
0x140022d6b  xor     edx, edx
0x140022d6d  mov     rax, r12
0x140022d70  mov     edi, 0FFFFFFFFh
0x140022d75  div     qword ptr [r13+110h]
0x140022d7c  mov     [rsp+88h+var_58], edi
0x140022d80  mov     rdx, rax; unsigned __int64
0x140022d83  call    ?GetObject@SC_SPARSE@@QEAAPEAX_K@Z; SC_SPARSE::GetObject(unsigned __int64)
0x140022d88  mov     r13, rax
0x140022d8b  mov     esi, 100h
0x140022d90  mov     r12d, edi
0x140022d93  test    rax, rax
0x140022d96  jz      loc_140023109
0x140022d9c  mov     ecx, 0FFFDh
0x140022da1  test    byte ptr [r13+1Eh], 1
0x140022da6  lea     rax, [r13+28h]
0x140022daa  jnz     short loc_140022DB0
0x140022dac  lea     rax, [r13+20h]
0x140022db0  mov     r15, [rax]
0x140022db3  mov     rdx, [rbx+8]
0x140022db7  mov     eax, [r15+40h]
0x140022dbb  cmp     eax, edi
0x140022dbd  jz      short loc_140022DED
0x140022dbf  xor     r14d, r14d
0x140022dc2  mov     [rsp+88h+var_58], eax
0x140022dc6  mov     edi, eax
0x140022dc8  mov     [rsp+88h+arg_10], r14d
0x140022dd0  mov     rax, [rbx+20h]
0x140022dd4  test    rax, rax
0x140022dd7  jz      short loc_140022DDF
0x140022dd9  add     rax, 58h ; 'X'
0x140022ddd  jmp     short loc_140022DE3
0x140022ddf  lea     rax, [rdx+50h]
0x140022de3  mov     ebp, [rax+8]
0x140022de6  mov     [rsp+88h+arg_8], ebp
0x140022ded  movzx   eax, word ptr [r15+4Eh]
0x140022df2  test    al, 2
0x140022df4  jz      short loc_140022E40
0x140022df6  and     ax, cx
0x140022df9  mov     esi, ebp
0x140022dfb  inc     ebp
0x140022dfd  mov     [r15+4Eh], ax
0x140022e02  mov     rcx, [rbx+20h]
0x140022e06  mov     [rsp+88h+arg_8], ebp
0x140022e0d  test    rcx, rcx
0x140022e10  jz      short loc_140022E18
0x140022e12  add     rcx, 58h ; 'X'
0x140022e16  jmp     short loc_140022E20
0x140022e18  mov     rcx, [rbx+8]
0x140022e1c  add     rcx, 50h ; 'P'
0x140022e20  mov     edx, esi
0x140022e22  imul    edx, [rcx+10h]
0x140022e26  add     edx, edi
  ... truncated ...
```
