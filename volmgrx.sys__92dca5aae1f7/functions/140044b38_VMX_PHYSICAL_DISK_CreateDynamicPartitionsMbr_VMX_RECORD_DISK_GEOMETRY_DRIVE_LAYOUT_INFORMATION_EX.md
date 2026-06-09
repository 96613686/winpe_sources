# VMX_PHYSICAL_DISK::CreateDynamicPartitionsMbr(VMX_RECORD *,_DISK_GEOMETRY *,_DRIVE_LAYOUT_INFORMATION_EX *)

- ea: `0x140044b38`
- end: `0x14004529d`
- name: `?CreateDynamicPartitionsMbr@VMX_PHYSICAL_DISK@@AEAAJPEAVVMX_RECORD@@PEAU_DISK_GEOMETRY@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z`
- size: `1893`
- prototype: `__int64 __fastcall(VMX_PHYSICAL_DISK *__hidden this, struct VMX_RECORD *, struct _DISK_GEOMETRY *, struct _DRIVE_LAYOUT_INFORMATION_EX *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140044ac4`

## callees

- `0x1400099d8`
- `0x14001be80`
- `0x1400342bc`
- `0x140044b38`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140044ca2`
- `ntoskrnl!ExAllocatePool2` at `0x140044ca2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045279`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045279`

## pseudocode

```c
__int64 __fastcall VMX_PHYSICAL_DISK::CreateDynamicPartitionsMbr(
        VMX_PHYSICAL_DISK *this,
        struct VMX_RECORD *a2,
        struct _DISK_GEOMETRY *a3,
        struct _DRIVE_LAYOUT_INFORMATION_EX *a4)
{
  __int64 v4; // rax
  unsigned __int64 BytesPerSector; // r12
  unsigned int v7; // r9d
  int v10; // ebp
  __int64 v11; // r15
  __int64 v12; // r14
  unsigned __int64 v13; // r15
  LARGE_INTEGER v14; // r14
  __int64 v15; // rdx
  unsigned int PartitionType; // r8d
  LARGE_INTEGER StartingOffset; // r8
  __int64 v18; // rsi
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rax
  bool v23; // zf
  unsigned int v24; // eax
  unsigned int v25; // edi
  VMX_NOTIFICATION_QUEUE *v26; // rcx
  __int64 v27; // rdx
  __int64 Pool2; // rax
  _DWORD *v29; // rbx
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int64 v32; // r9
  __int64 i; // r8
  __int64 v34; // rdx
  unsigned int v35; // ecx
  __int128 v36; // xmm1
  __int64 v37; // rcx
  __int128 v38; // xmm0
  GUID PartitionId; // xmm1
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int128 v43; // xmm1
  __int128 v44; // xmm0
  __int64 v45; // r9
  VMX_NOTIFICATION_QUEUE *v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // rcx
  unsigned __int64 v49; // rbp
  _QWORD *v50; // rsi
  __int64 v51; // rcx
  int v52; // ecx
  unsigned __int64 v53; // r10
  bool v54; // cl
  __int64 k; // rdx
  bool v56; // r11
  unsigned int v57; // eax
  int v58; // r11d
  __int64 v59; // rcx
  __int64 v60; // r8
  __int64 j; // r8
  unsigned int v62; // ecx
  int v63; // r10d
  __int128 v64; // xmm1
  __int64 v65; // rcx
  __int128 v66; // xmm0
  GUID v67; // xmm1
  __int128 v68; // xmm0
  __int128 v69; // xmm1
  __int128 v70; // xmm0
  __int128 v71; // xmm1
  __int128 v72; // xmm0
  unsigned __int64 v73; // r11
  __int64 v74; // rdi
  __int64 v75; // r10
  unsigned __int64 v76; // rsi
  unsigned __int64 v77; // r15
  unsigned int v78; // ecx
  __int64 v79; // r8
  __int64 v80; // rcx
  __int128 v81; // xmm1
  __int128 v82; // xmm0
  __int128 v83; // xmm1
  __int128 v84; // xmm0
  __int128 v85; // xmm1
  __int128 v86; // xmm0
  __int128 v87; // xmm1
  __int128 v88; // xmm0
  __int64 v89; // rcx
  __int64 v90; // rcx
  DWORD SectorsPerTrack; // [rsp+68h] [rbp+10h]

  v4 = *((_QWORD *)this + 11);
  BytesPerSector = a3->BytesPerSector;
  v7 = 0;
  v10 = 32801;
  v11 = *(_QWORD *)(v4 + 136);
  v12 = v11 + *(_QWORD *)(v4 + 144);
  v13 = BytesPerSector * v11;
  v14.QuadPart = BytesPerSector * v12;
  v15 = 0;
  do
  {
    if ( (unsigned int)v15 >= a4->PartitionCount )
      break;
    PartitionType = a4->PartitionEntry[v15].Mbr.PartitionType;
    if ( ((unsigned __int8)PartitionType > 0xFu || !_bittest(&v10, PartitionType)) && (_BYTE)PartitionType != 66 )
    {
      StartingOffset = a4->PartitionEntry[v15].StartingOffset;
      if ( StartingOffset.QuadPart >= (unsigned __int64)v14.QuadPart
        || StartingOffset.QuadPart + a4->PartitionEntry[v15].PartitionLength.QuadPart <= v13 )
      {
        ++v7;
      }
    }
    v15 = (unsigned int)(v15 + 1);
  }
  while ( (unsigned int)v15 < 4 );
  v18 = *((_QWORD *)a2 + (*((_WORD *)a2 + 32) & 1) + 5);
  v19 = *(_QWORD *)(v18 + 120);
  while ( v19 )
  {
    v20 = *(_QWORD *)(v19 + 8LL * (*(_WORD *)(v19 + 64) & 1) + 40);
    v21 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v20 + 168) + 8LL * (*(_WORD *)(*(_QWORD *)(v20 + 168) + 64LL) & 1) + 40)
                    + 136LL);
    v22 = *(_QWORD *)(v21 + 8LL * (*(_WORD *)(v21 + 64) & 1) + 40);
    v19 = *(_QWORD *)(v20 + 160);
    v23 = (*(_DWORD *)(v22 + 156) & 0x800000) == 0;
    v24 = v7 + 1;
    if ( v23 )
      v24 = v7;
    v7 = v24;
  }
  if ( v7 > 4 )
  {
    v25 = -1070071792;
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return v25;
    }
    v27 = 79;
    goto LABEL_20;
  }
  SectorsPerTrack = a3->SectorsPerTrack;
  Pool2 = ExAllocatePool2(258, 624, 1632398678);
  v29 = (_DWORD *)Pool2;
  if ( !Pool2 )
  {
    v25 = -1073741670;
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return v25;
    }
    v27 = 80;
LABEL_20:
    WPP_SF_d(*((_QWORD *)v26 + 3), v27, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids, v25);
    return v25;
  }
  v30 = *(_OWORD *)a4->Gpt.DiskId.Data4;
  *(_OWORD *)Pool2 = *(_OWORD *)&a4->PartitionStyle;
  v31 = *(_OWORD *)&a4->Gpt.UsableLength.LowPart;
  *(_OWORD *)(Pool2 + 16) = v30;
  *(_OWORD *)(Pool2 + 32) = v31;
  *(_DWORD *)(Pool2 + 4) = 0;
  memset((void *)(Pool2 + 48), 0, 0x240u);
  v32 = 0;
  for ( i = 0; (unsigned int)i < 4 && (unsigned int)i < a4->PartitionCount; i = (unsigned int)(i + 1) )
  {
    v34 = i;
    v35 = a4->PartitionEntry[i].Mbr.PartitionType;
    if ( ((unsigned __int8)v35 > 0xFu || !_bittest(&v10, v35))
      && (_BYTE)v35 != 66
      && a4->PartitionEntry[v34].StartingOffset.QuadPart + a4->PartitionEntry[v34].PartitionLength.QuadPart <= v13 )
    {
      if ( (unsigned int)v32 >= 4 )
      {
        v45 = 3221225473LL;
        v25 = -1073741823;
        v46 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
        {
          v47 = 81;
LABEL_91:
          WPP_SF_d(*((_QWORD *)v46 + 3), v47, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids, v45);
        }
        goto LABEL_92;
      }
      v36 = *(_OWORD *)&a4->PartitionEntry[v34].PartitionLength.LowPart;
      v37 = 18 * v32;
      v32 = (unsigned int)(v32 + 1);
      *(_OWORD *)&v29[2 * v37 + 12] = *(_OWORD *)&a4->PartitionEntry[v34].PartitionStyle;
      v38 = *(_OWORD *)&a4->PartitionEntry[v34].Mbr.PartitionType;
      *(_OWORD *)&v29[2 * v37 + 16] = v36;
      PartitionId = a4->PartitionEntry[v34].Gpt.PartitionId;
      *(_OWORD *)&v29[2 * v37 + 20] = v38;
      v40 = *(_OWORD *)&a4->PartitionEntry[v34].Gpt.Attributes;
      *(GUID *)&v29[2 * v37 + 24] = PartitionId;
      v41 = *(_OWORD *)&a4->PartitionEntry[v34].Gpt.Name[4];
      *(_OWORD *)&v29[2 * v37 + 28] = v40;
      v42 = *(_OWORD *)&a4->PartitionEntry[v34].Gpt.Name[12];
      *(_OWORD *)&v29[2 * v37 + 32] = v41;
      v43 = *(_OWORD *)&a4->PartitionEntry[v34].Gpt.Name[20];
      *(_OWORD *)&v29[2 * v37 + 36] = v42;
      v44 = *(_OWORD *)&a4->PartitionEntry[v34].Gpt.Name[28];
      *(_OWORD *)&v29[2 * v37 + 40] = v43;
      *(_OWORD *)&v29[2 * v37 + 44] = v44;
      LOBYTE(v29[2 * v37 + 19]) = 1;
    }
  }
  v48 = *(_QWORD *)(v18 + 120);
  v49 = v13;
  while ( 1 )
  {
    if ( !v48 )
    {
      for ( j = 0; (unsigned int)j < 4 && (unsigned int)j < a4->PartitionCount; j = (unsigned int)(j + 1) )
      {
        v62 = a4->PartitionEntry[j].Mbr.PartitionType;
        if ( (unsigned __int8)v62 <= 0xFu )
        {
          v63 = 32801;
          if ( _bittest(&v63, v62) )
            continue;
        }
        if ( (_BYTE)v62 != 66 && a4->PartitionEntry[j].StartingOffset.QuadPart >= (unsigned __int64)v14.QuadPart )
        {
          if ( (unsigned int)v32 >= 4 )
          {
            v45 = 3221225473LL;
            v25 = -1073741823;
            v46 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
            {
              v47 = 83;
              goto LABEL_91;
            }
            goto LABEL_92;
          }
          v64 = *(_OWORD *)&a4->PartitionEntry[j].PartitionLength.LowPart;
          v65 = 18 * v32;
          v32 = (unsigned int)(v32 + 1);
          *(_OWORD *)&v29[2 * v65 + 12] = *(_OWORD *)&a4->PartitionEntry[j].PartitionStyle;
          v66 = *(_OWORD *)&a4->PartitionEntry[j].Mbr.PartitionType;
          *(_OWORD *)&v29[2 * v65 + 16] = v64;
          v67 = a4->PartitionEntry[j].Gpt.PartitionId;
          *(_OWORD *)&v29[2 * v65 + 20] = v66;
          v68 = *(_OWORD *)&a4->PartitionEntry[j].Gpt.Attributes;
          *(GUID *)&v29[2 * v65 + 24] = v67;
          v69 = *(_OWORD *)&a4->PartitionEntry[j].Gpt.Name[4];
          *(_OWORD *)&v29[2 * v65 + 28] = v68;
          v70 = *(_OWORD *)&a4->PartitionEntry[j].Gpt.Name[12];
          *(_OWORD *)&v29[2 * v65 + 32] = v69;
          v71 = *(_OWORD *)&a4->PartitionEntry[j].Gpt.Name[20];
          *(_OWORD *)&v29[2 * v65 + 36] = v70;
          v72 = *(_OWORD *)&a4->PartitionEntry[j].Gpt.Name[28];
          *(_OWORD *)&v29[2 * v65 + 40] = v71;
          *(_OWORD *)&v29[2 * v65 + 44] = v72;
          LOBYTE(v29[2 * v65 + 19]) = 1;
        }
      }
      v73 = BytesPerSector * SectorsPerTrack;
      if ( v73 > v13 )
        v73 = v13;
      v74 = 0;
      if ( (_DWORD)v32 )
      {
        while ( (unsigned int)v32 < 4 )
        {
          v75 = 18 * v74;
          v76 = *(_QWORD *)&v29[36 * v74 + 14];
          v77 = v76 + *(_QWORD *)&v29[36 * v74 + 16];
          if ( BytesPerSector + v73 <= v76 )
          {
            v78 = v32;
            if ( (unsigned int)v32 > (unsigned int)v74 )
            {
              do
              {
                v79 = v78 - 1;
                v80 = 18LL * v78;
                v81 = *(_OWORD *)&v29[36 * v79 + 16];
                *(_OWORD *)&v29[2 * v80 + 12] = *(_OWORD *)&v29[36 * v79 + 12];
                v82 = *(_OWORD *)&v29[36 * v79 + 20];
                *(_OWORD *)&v29[2 * v80 + 16] = v81;
                v83 = *(_OWORD *)&v29[36 * v79 + 24];
                *(_OWORD *)&v29[2 * v80 + 20] = v82;
                v84 = *(_OWORD *)&v29[36 * v79 + 28];
                *(_OWORD *)&v29[2 * v80 + 24] = v83;
                v85 = *(_OWORD *)&v29[36 * v79 + 32];
                *(_OWORD *)&v29[2 * v80 + 28] = v84;
                v86 = *(_OWORD *)&v29[36 * v79 + 36];
                *(_OWORD *)&v29[2 * v80 + 32] = v85;
                v87 = *(_OWORD *)&v29[36 * v79 + 40];
                *(_OWORD *)&v29[2 * v80 + 36] = v86;
                v88 = *(_OWORD *)&v29[36 * v79 + 44];
                *(_OWORD *)&v29[2 * v80 + 40] = v87;
                *(_OWORD *)&v29[2 * v80 + 44] = v88;
                v78 = v79;
              }
              while ( (unsigned int)v79 > (unsigned int)v74 );
            }
            v29[36 * v74 + 12] = 0;
            *(_QWORD *)&v29[36 * v74 + 14] = v73;
            LOBYTE(v29[36 * v74 + 19]) = 1;
            v32 = (unsigned int)(v32 + 1);
            v29[36 * v74 + 21] = v73 / BytesPerSector;
            *(_QWORD *)&v29[36 * v74 + 16] = v76 - v73;
            LODWORD(v74) = v74 + 1;
            LOWORD(v29[2 * v75 + 20]) = 66;
          }
          v74 = (unsigned int)(v74 + 1);
          v73 = v77;
          if ( (unsigned int)v74 >= (unsigned int)v32 )
            goto LABEL_81;
        }
      }
      else
      {
LABEL_81:
        if ( (unsigned int)v32 < 4 )
        {
          if ( BytesPerSector + v49 > v14.QuadPart )
            goto LABEL_84;
          v89 = 18 * v32;
          v32 = (unsigned int)(v32 + 1);
          v29[2 * v89 + 12] = 0;
          v29[2 * v89 + 21] = v49 / BytesPerSector;
          *(_QWORD *)&v29[2 * v89 + 14] = v49;
          *(_QWORD *)&v29[2 * v89 + 16] = v14.QuadPart - v49;
          LOBYTE(v29[2 * v89 + 19]) = 1;
          LOWORD(v29[2 * v89 + 20]) = 66;
          while ( (unsigned int)v32 < 4 )
          {
LABEL_84:
            v90 = 18 * v32;
            v32 = (unsigned int)(v32 + 1);
            LOBYTE(v29[2 * v90 + 20]) = 0;
            LOBYTE(v29[2 * v90 + 19]) = 1;
          }
        }
      }
      v29[1] = v32;
      v25 = VMX_DISK_DEVICE::SetDriveLayoutExSynchronous(*((VMX_DISK_DEVICE **)this + 2), v29);
      if ( (v25 & 0x80000000) != 0 )
      {
        v46 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
        {
          v47 = 84;
          v45 = v25;
          goto LABEL_91;
        }
      }
      goto LABEL_92;
    }
    v50 = *(_QWORD **)(v48 + 8LL * (*(_WORD *)(v48 + 64) & 1) + 40);
    v51 = *(_QWORD *)(*(_QWORD *)(v50[21] + 8LL * (*(_WORD *)(v50[21] + 64LL) & 1) + 40) + 136LL);
    v52 = *(_DWORD *)(*(_QWORD *)(v51 + 8LL * (*(_WORD *)(v51 + 64) & 1) + 40) + 156LL);
    if ( (v52 & 0x800000) != 0 )
      break;
LABEL_53:
    v48 = v50[20];
  }
  v53 = v13 + (v50[10] << 9);
  v54 = (v52 & 0x400000) != 0;
  for ( k = 0; ; k = (unsigned int)(k + 1) )
  {
    v56 = v54;
    if ( (unsigned int)k >= 4 || (unsigned int)k >= a4->PartitionCount )
      break;
    v57 = a4->PartitionEntry[k].Mbr.PartitionType;
    if ( (unsigned __int8)v57 <= 0xFu )
    {
      v58 = 32801;
      if ( _bittest(&v58, v57) )
        continue;
    }
    if ( a4->PartitionEntry[k].Mbr.BootIndicator )
    {
      v56 = a4->PartitionEntry[k].StartingOffset.QuadPart == v53;
      break;
    }
  }
  if ( (unsigned int)v32 < 4 )
  {
    v59 = 18 * v32;
    v60 = v50[12] << 9;
    v32 = (unsigned int)(v32 + 1);
    v29[2 * v59 + 12] = 0;
    v49 = v60 + v53;
    v29[2 * v59 + 21] = v53 / BytesPerSector;
    *(_QWORD *)&v29[2 * v59 + 14] = v53;
    *(_QWORD *)&v29[2 * v59 + 16] = v60;
    LOBYTE(v29[2 * v59 + 19]) = 1;
    LOBYTE(v29[2 * v59 + 20]) = 66;
    BYTE1(v29[2 * v59 + 20]) = v56;
    goto LABEL_53;
  }
  v45 = 3221225473LL;
  v25 = -1073741823;
  v46 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    v47 = 82;
    goto LABEL_91;
  }
LABEL_92:
  ExFreePoolWithTag(v29, 0);
  return v25;
}

```

## disassembly

```asm
0x140044b38  mov     [rsp+arg_10], rbx
0x140044b3d  mov     [rsp+arg_0], rcx
0x140044b42  push    rbp
0x140044b43  push    rsi
0x140044b44  push    rdi
0x140044b45  push    r12
0x140044b47  push    r13
0x140044b49  push    r14
0x140044b4b  push    r15
0x140044b4d  sub     rsp, 20h
0x140044b51  mov     rax, [rcx+58h]
0x140044b55  mov     rdi, r9
0x140044b58  mov     r12d, [r8+14h]
0x140044b5c  xor     r9d, r9d
0x140044b5f  mov     r11, rdx
0x140044b62  mov     rbx, r8
0x140044b65  mov     ebp, 8021h
0x140044b6a  mov     r10, [rax+88h]
0x140044b71  mov     r14, [rax+90h]
0x140044b78  mov     r15, r10
0x140044b7b  add     r14, r10
0x140044b7e  mov     r10d, [rdi+4]
0x140044b82  imul    r15, r12
0x140044b86  imul    r14, r12
0x140044b8a  xor     edx, edx
0x140044b8c  cmp     edx, r10d
0x140044b8f  jnb     short loc_140044BD1
0x140044b91  lea     rcx, [rdx+rdx*8]
0x140044b95  add     rcx, rcx
0x140044b98  movzx   r8d, byte ptr [rdi+rcx*8+50h]
0x140044b9e  cmp     r8b, 0Fh
0x140044ba2  ja      short loc_140044BAA
0x140044ba4  bt      ebp, r8d
0x140044ba8  jb      short loc_140044BCA
0x140044baa  cmp     r8b, 42h ; 'B'
0x140044bae  jz      short loc_140044BCA
0x140044bb0  mov     r8, [rdi+rcx*8+38h]
0x140044bb5  cmp     r8, r14
0x140044bb8  jnb     short loc_140044BC7
0x140044bba  mov     rcx, [rdi+rcx*8+40h]
0x140044bbf  add     rcx, r8
0x140044bc2  cmp     rcx, r15
0x140044bc5  ja      short loc_140044BCA
0x140044bc7  inc     r9d
0x140044bca  inc     edx
0x140044bcc  cmp     edx, 4
0x140044bcf  jb      short loc_140044B8C
0x140044bd1  movzx   eax, word ptr [r11+40h]
0x140044bd6  and     eax, 1
0x140044bd9  mov     rsi, [r11+rax*8+28h]
0x140044bde  mov     rcx, [rsi+78h]
0x140044be2  jmp     short loc_140044C32
0x140044be4  movzx   eax, word ptr [rcx+40h]
0x140044be8  and     eax, 1
0x140044beb  mov     rdx, [rcx+rax*8+28h]
0x140044bf0  mov     rcx, [rdx+0A8h]
0x140044bf7  movzx   eax, word ptr [rcx+40h]
0x140044bfb  and     eax, 1
0x140044bfe  mov     rax, [rcx+rax*8+28h]
0x140044c03  mov     rcx, [rax+88h]
0x140044c0a  movzx   eax, word ptr [rcx+40h]
0x140044c0e  and     eax, 1
0x140044c11  mov     rax, [rcx+rax*8+28h]
0x140044c16  mov     rcx, [rdx+0A0h]
0x140044c1d  test    dword ptr [rax+9Ch], 800000h
0x140044c27  lea     eax, [r9+1]
0x140044c2b  cmovz   eax, r9d
0x140044c2f  mov     r9d, eax
0x140044c32  test    rcx, rcx
0x140044c35  jnz     short loc_140044BE4
0x140044c37  cmp     r9d, 4
0x140044c3b  jbe     short loc_140044C8B
0x140044c3d  mov     edi, 0C0380010h
0x140044c42  mov     rcx, cs:WPP_GLOBAL_Control
0x140044c49  lea     rax, WPP_GLOBAL_Control
0x140044c50  cmp     rcx, rax
0x140044c53  jz      loc_140045285
0x140044c59  mov     eax, [rcx+2Ch]
0x140044c5c  test    al, 10h
0x140044c5e  jz      loc_140045285
0x140044c64  cmp     byte ptr [rcx+29h], 2
0x140044c68  jb      loc_140045285
0x140044c6e  mov     edx, 4Fh ; 'O'
0x140044c73  mov     rcx, [rcx+18h]
0x140044c77  lea     r8, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids
0x140044c7e  mov     r9d, edi
0x140044c81  call    WPP_SF_d
0x140044c86  jmp     loc_140045285
0x140044c8b  mov     eax, [rbx+10h]
0x140044c8e  mov     edx, 270h
0x140044c93  mov     ecx, 102h
0x140044c98  mov     [rsp+58h+arg_8], eax
0x140044c9c  mov     r8d, 614C6D56h
0x140044ca2  call    cs:__imp_ExAllocatePool2
0x140044ca9  nop     dword ptr [rax+rax+00h]
0x140044cae  mov     rbx, rax
0x140044cb1  test    rax, rax
0x140044cb4  jnz     short loc_140044CEC
0x140044cb6  mov     edi, 0C000009Ah
0x140044cbb  mov     rcx, cs:WPP_GLOBAL_Control
0x140044cc2  lea     rax, WPP_GLOBAL_Control
0x140044cc9  cmp     rcx, rax
0x140044ccc  jz      loc_140045285
0x140044cd2  mov     eax, [rcx+2Ch]
0x140044cd5  test    al, 10h
0x140044cd7  jz      loc_140045285
0x140044cdd  cmp     byte ptr [rcx+29h], 2
0x140044ce1  jb      loc_140045285
0x140044ce7  lea     edx, [rbx+50h]
0x140044cea  jmp     short loc_140044C73
0x140044cec  movups  xmm0, xmmword ptr [rdi]
0x140044cef  xor     edx, edx; Val
0x140044cf1  mov     r8d, 240h; Size
0x140044cf7  movups  xmm1, xmmword ptr [rdi+10h]
0x140044cfb  lea     rcx, [rax+30h]; void *
0x140044cff  movups  xmmword ptr [rax], xmm0
0x140044d02  movups  xmm0, xmmword ptr [rdi+20h]
0x140044d06  movups  xmmword ptr [rax+10h], xmm1
0x140044d0a  movups  xmmword ptr [rax+20h], xmm0
0x140044d0e  mov     dword ptr [rax+4], 0
0x140044d15  call    memset
0x140044d1a  xor     r9d, r9d
0x140044d1d  xor     r8d, r8d
0x140044d20  cmp     r8d, 4
0x140044d24  jnb     loc_140044E3D
0x140044d2a  cmp     r8d, [rdi+4]
0x140044d2e  jnb     loc_140044E3D
0x140044d34  lea     rdx, [r8+r8*8]
0x140044d38  shl     rdx, 4
0x140044d3c  movzx   ecx, byte ptr [rdx+rdi+50h]
0x140044d41  cmp     cl, 0Fh
0x140044d44  ja      short loc_140044D4F
0x140044d46  bt      ebp, ecx
0x140044d49  jb      loc_140044DF6
0x140044d4f  cmp     cl, 42h ; 'B'
0x140044d52  jz      loc_140044DF6
0x140044d58  mov     rax, [rdx+rdi+40h]
0x140044d5d  add     rax, [rdx+rdi+38h]
0x140044d62  cmp     rax, r15
0x140044d65  ja      loc_140044DF6
0x140044d6b  cmp     r9d, 4
0x140044d6f  jnb     loc_140044DFE
0x140044d75  movups  xmm0, xmmword ptr [rdx+rdi+30h]
0x140044d7a  lea     rcx, [r9+r9*8]
0x140044d7e  movups  xmm1, xmmword ptr [rdx+rdi+40h]
0x140044d83  add     rcx, rcx
0x140044d86  inc     r9d
0x140044d89  movups  xmmword ptr [rbx+rcx*8+30h], xmm0
0x140044d8e  movups  xmm0, xmmword ptr [rdx+rdi+50h]
0x140044d93  movups  xmmword ptr [rbx+rcx*8+40h], xmm1
0x140044d98  movups  xmm1, xmmword ptr [rdx+rdi+60h]
0x140044d9d  movups  xmmword ptr [rbx+rcx*8+50h], xmm0
0x140044da2  movups  xmm0, xmmword ptr [rdx+rdi+70h]
0x140044da7  movups  xmmword ptr [rbx+rcx*8+60h], xmm1
0x140044dac  movups  xmm1, xmmword ptr [rdx+rdi+80h]
0x140044db4  movups  xmmword ptr [rbx+rcx*8+70h], xmm0
0x140044db9  movups  xmm0, xmmword ptr [rdx+rdi+90h]
0x140044dc1  movups  xmmword ptr [rbx+rcx*8+80h], xmm1
0x140044dc9  movups  xmm1, xmmword ptr [rdx+rdi+0A0h]
0x140044dd1  movups  xmmword ptr [rbx+rcx*8+90h], xmm0
0x140044dd9  movups  xmm0, xmmword ptr [rdx+rdi+0B0h]
0x140044de1  movups  xmmword ptr [rbx+rcx*8+0A0h], xmm1
0x140044de9  movups  xmmword ptr [rbx+rcx*8+0B0h], xmm0
0x140044df1  mov     byte ptr [rbx+rcx*8+4Ch], 1
0x140044df6  inc     r8d
0x140044df9  jmp     loc_140044D20
0x140044dfe  mov     r9d, 0C0000001h
0x140044e04  mov     edi, r9d
0x140044e07  mov     rcx, cs:WPP_GLOBAL_Control
0x140044e0e  lea     rax, WPP_GLOBAL_Control
0x140044e15  cmp     rcx, rax
0x140044e18  jz      loc_140045274
0x140044e1e  mov     eax, [rcx+2Ch]
0x140044e21  test    al, 10h
0x140044e23  jz      loc_140045274
0x140044e29  cmp     byte ptr [rcx+29h], 2
0x140044e2d  jb      loc_140045274
0x140044e33  mov     edx, 51h ; 'Q'
0x140044e38  jmp     loc_140045264
0x140044e3d  mov     rcx, [rsi+78h]
0x140044e41  mov     rbp, r15
0x140044e44  test    rcx, rcx
0x140044e47  jz      loc_140044F78
0x140044e4d  movzx   eax, word ptr [rcx+40h]
0x140044e51  and     eax, 1
0x140044e54  mov     rsi, [rcx+rax*8+28h]
0x140044e59  mov     rcx, [rsi+0A8h]
0x140044e60  movzx   eax, word ptr [rcx+40h]
0x140044e64  and     eax, 1
0x140044e67  mov     rax, [rcx+rax*8+28h]
0x140044e6c  mov     rcx, [rax+88h]
0x140044e73  movzx   eax, word ptr [rcx+40h]
0x140044e77  and     eax, 1
0x140044e7a  mov     rax, [rcx+rax*8+28h]
0x140044e7f  mov     ecx, [rax+9Ch]
0x140044e85  bt      ecx, 17h
0x140044e89  jnb     loc_140044F2D
0x140044e8f  mov     r10, [rsi+50h]
0x140044e93  shl     r10, 9
0x140044e97  shr     ecx, 16h
0x140044e9a  add     r10, r15
0x140044e9d  and     cl, 1
0x140044ea0  xor     edx, edx
0x140044ea2  mov     r11b, cl
0x140044ea5  cmp     edx, 4
0x140044ea8  jnb     short loc_140044EE4
0x140044eaa  cmp     edx, [rdi+4]
0x140044ead  jnb     short loc_140044EE4
0x140044eaf  lea     r8, [rdx+rdx*8]
0x140044eb3  add     r8, r8
0x140044eb6  movzx   eax, byte ptr [rdi+r8*8+50h]
0x140044ebc  cmp     al, 0Fh
0x140044ebe  ja      short loc_140044ECC
0x140044ec0  mov     r11d, 8021h
0x140044ec6  bt      r11d, eax
0x140044eca  jb      short loc_140044ED9
0x140044ecc  cmp     byte ptr [rdi+r8*8+51h], 0
0x140044ed2  mov     rax, [rdi+r8*8+38h]
0x140044ed7  jnz     short loc_140044EDD
0x140044ed9  inc     edx
0x140044edb  jmp     short loc_140044EA2
0x140044edd  cmp     rax, r10
0x140044ee0  setz    r11b
0x140044ee4  cmp     r9d, 4
0x140044ee8  jnb     short loc_140044F39
0x140044eea  mov     r8, [rsi+60h]
0x140044eee  lea     rcx, [r9+r9*8]
0x140044ef2  add     rcx, rcx
0x140044ef5  shl     r8, 9
0x140044ef9  inc     r9d
0x140044efc  xor     edx, edx
0x140044efe  mov     rax, r10
0x140044f01  div     r12
0x140044f04  mov     dword ptr [rbx+rcx*8+30h], 0
0x140044f0c  lea     rbp, [r8+r10]
0x140044f10  mov     [rbx+rcx*8+54h], eax
0x140044f14  mov     [rbx+rcx*8+38h], r10
0x140044f19  mov     [rbx+rcx*8+40h], r8
0x140044f1e  mov     byte ptr [rbx+rcx*8+4Ch], 1
0x140044f23  mov     byte ptr [rbx+rcx*8+50h], 42h ; 'B'
0x140044f28  mov     [rbx+rcx*8+51h], r11b
0x140044f2d  mov     rcx, [rsi+0A0h]
0x140044f34  jmp     loc_140044E44
0x140044f39  mov     r9d, 0C0000001h
0x140044f3f  mov     edi, r9d
0x140044f42  mov     rcx, cs:WPP_GLOBAL_Control
0x140044f49  lea     rax, WPP_GLOBAL_Control
0x140044f50  cmp     rcx, rax
0x140044f53  jz      loc_140045274
0x140044f59  mov     eax, [rcx+2Ch]
0x140044f5c  test    al, 10h
0x140044f5e  jz      loc_140045274
0x140044f64  cmp     byte ptr [rcx+29h], 2
0x140044f68  jb      loc_140045274
0x140044f6e  mov     edx, 52h ; 'R'
0x140044f73  jmp     loc_140045264
0x140044f78  xor     r8d, r8d
0x140044f7b  cmp     r8d, 4
0x140044f7f  jnb     loc_140045096
0x140044f85  cmp     r8d, [rdi+4]
0x140044f89  jnb     loc_140045096
0x140044f8f  lea     rdx, [r8+r8*8]
0x140044f93  add     rdx, rdx
0x140044f96  movzx   ecx, byte ptr [rdi+rdx*8+50h]
0x140044f9b  cmp     cl, 0Fh
0x140044f9e  ja      short loc_140044FB0
0x140044fa0  mov     r10d, 8021h
0x140044fa6  bt      r10d, ecx
0x140044faa  jb      loc_14004504F
0x140044fb0  cmp     cl, 42h ; 'B'
0x140044fb3  jz      loc_14004504F
0x140044fb9  cmp     [rdi+rdx*8+38h], r14
0x140044fbe  jb      loc_14004504F
0x140044fc4  cmp     r9d, 4
0x140044fc8  jnb     loc_140045057
0x140044fce  movups  xmm0, xmmword ptr [rdi+rdx*8+30h]
0x140044fd3  lea     rcx, [r9+r9*8]
0x140044fd7  movups  xmm1, xmmword ptr [rdi+rdx*8+40h]
0x140044fdc  add     rcx, rcx
0x140044fdf  inc     r9d
0x140044fe2  movups  xmmword ptr [rbx+rcx*8+30h], xmm0
0x140044fe7  movups  xmm0, xmmword ptr [rdi+rdx*8+50h]
0x140044fec  movups  xmmword ptr [rbx+rcx*8+40h], xmm1
0x140044ff1  movups  xmm1, xmmword ptr [rdi+rdx*8+60h]
0x140044ff6  movups  xmmword ptr [rbx+rcx*8+50h], xmm0
0x140044ffb  movups  xmm0, xmmword ptr [rdi+rdx*8+70h]
0x140045000  movups  xmmword ptr [rbx+rcx*8+60h], xmm1
0x140045005  movups  xmm1, xmmword ptr [rdi+rdx*8+80h]
0x14004500d  movups  xmmword ptr [rbx+rcx*8+70h], xmm0
0x140045012  movups  xmm0, xmmword ptr [rdi+rdx*8+90h]
0x14004501a  movups  xmmword ptr [rbx+rcx*8+80h], xmm1
0x140045022  movups  xmm1, xmmword ptr [rdi+rdx*8+0A0h]
0x14004502a  movups  xmmword ptr [rbx+rcx*8+90h], xmm0
0x140045032  movups  xmm0, xmmword ptr [rdi+rdx*8+0B0h]
0x14004503a  movups  xmmword ptr [rbx+rcx*8+0A0h], xmm1
0x140045042  movups  xmmword ptr [rbx+rcx*8+0B0h], xmm0
0x14004504a  mov     byte ptr [rbx+rcx*8+4Ch], 1
0x14004504f  inc     r8d
0x140045052  jmp     loc_140044F7B
0x140045057  mov     r9d, 0C0000001h
  ... truncated ...
```
