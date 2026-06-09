# VMX_PHYSICAL_DISK::CreateBasicPartitionsGpt(VMX_RECORD *,_DISK_GEOMETRY *,_DRIVE_LAYOUT_INFORMATION_EX *)

- ea: `0x1400437c8`
- end: `0x140043e81`
- name: `?CreateBasicPartitionsGpt@VMX_PHYSICAL_DISK@@AEAAJPEAVVMX_RECORD@@PEAU_DISK_GEOMETRY@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z`
- size: `1721`
- prototype: `__int64 __fastcall(VMX_DISK_DEVICE **this, struct VMX_RECORD *, struct _DISK_GEOMETRY *, struct _DRIVE_LAYOUT_INFORMATION_EX *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140043754`

## callees

- `0x140006c0c`
- `0x1400099d8`
- `0x14001be80`
- `0x1400342bc`
- `0x140040580`
- `0x1400437c8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14004380f`
- `ntoskrnl!ExAllocatePool2` at `0x14004380f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043b4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043b96`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043bdd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043db6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043e20`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043b4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043b96`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043bdd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043db6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043e20`

## pseudocode

```c
__int64 __fastcall VMX_PHYSICAL_DISK::CreateBasicPartitionsGpt(
        VMX_DISK_DEVICE **this,
        struct VMX_RECORD *a2,
        struct _DISK_GEOMETRY *a3,
        struct _DRIVE_LAYOUT_INFORMATION_EX *a4)
{
  __int64 BytesPerSector; // rbx
  __int64 v6; // r13
  __int64 Pool2; // rax
  _DWORD *v8; // rdi
  VMX_NOTIFICATION_QUEUE *v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  VMX_PHYSICAL_DISK *v14; // r8
  __int64 v15; // r12
  DWORD PartitionCount; // r14d
  __int64 v17; // rbp
  __int64 v18; // r11
  VMX_DISK_DEVICE *v19; // rax
  unsigned __int64 v20; // rbx
  LARGE_INTEGER StartingOffset; // rdx
  __int64 i; // r10
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
  __int64 j; // rcx
  _QWORD *v44; // r13
  __int64 v45; // rcx
  __int64 v46; // rbx
  __int64 v47; // rdx
  wchar_t *v48; // rcx
  __int64 v49; // rax
  __int64 v50; // r11
  unsigned __int64 GptAttributes; // rax
  VMX_NOTIFICATION_QUEUE *v52; // rcx
  __int64 v53; // rdx
  DWORD v54; // r13d
  LARGE_INTEGER v55; // rbx
  __int64 v56; // r11
  unsigned int v57; // r12d
  LARGE_INTEGER v58; // rdx
  unsigned int k; // r10d
  unsigned int v60; // ecx
  __int64 v61; // r8
  __int64 v62; // rcx
  __int128 v63; // xmm1
  __int128 v64; // xmm0
  __int128 v65; // xmm1
  __int128 v66; // xmm0
  __int128 v67; // xmm1
  __int128 v68; // xmm0
  __int128 v69; // xmm1
  __int128 v70; // xmm0
  __int128 v71; // xmm1
  __int64 v72; // rcx
  __int128 v73; // xmm0
  GUID v74; // xmm1
  __int128 v75; // xmm0
  __int128 v76; // xmm1
  __int128 v77; // xmm0
  __int128 v78; // xmm1
  __int128 v79; // xmm0
  __int64 v82; // [rsp+68h] [rbp+10h]
  __int64 v83; // [rsp+70h] [rbp+18h]

  BytesPerSector = a3->BytesPerSector;
  v6 = *((_QWORD *)a2 + (*((_WORD *)a2 + 32) & 1) + 5);
  Pool2 = ExAllocatePool2(258, 144LL * a4->Gpt.MaxPartitionCount + 48, 1632398678);
  v8 = (_DWORD *)Pool2;
  if ( Pool2 )
  {
    v12 = *(_OWORD *)a4->Gpt.DiskId.Data4;
    *(_OWORD *)Pool2 = *(_OWORD *)&a4->PartitionStyle;
    v13 = *(_OWORD *)&a4->Gpt.UsableLength.LowPart;
    *(_OWORD *)(Pool2 + 16) = v12;
    *(_OWORD *)(Pool2 + 32) = v13;
    *(_DWORD *)(Pool2 + 4) = 0;
    memset((void *)(Pool2 + 48), 0, 144LL * a4->Gpt.MaxPartitionCount);
    v14 = (VMX_PHYSICAL_DISK *)this;
    v15 = BytesPerSector;
    PartitionCount = a4->PartitionCount;
    v17 = 0;
    v18 = 0;
    v19 = this[11];
    v20 = *((_QWORD *)v19 + 17) * BytesPerSector;
    v82 = *((_QWORD *)v19 + 17);
    v83 = *((_QWORD *)v19 + 18);
    if ( PartitionCount )
    {
      do
      {
        StartingOffset = a4->PartitionEntry[v18].StartingOffset;
        if ( StartingOffset.QuadPart + a4->PartitionEntry[v18].PartitionLength.QuadPart <= v20 )
        {
          for ( i = 0; (unsigned int)i < (unsigned int)v17; i = (unsigned int)(i + 1) )
          {
            if ( StartingOffset.QuadPart < *(_QWORD *)&v8[36 * i + 14] )
              break;
          }
          v23 = v17;
          if ( (unsigned int)v17 > (unsigned int)i )
          {
            do
            {
              v24 = v23 - 1;
              v25 = 18LL * v23;
              v26 = *(_OWORD *)&v8[36 * v24 + 16];
              *(_OWORD *)&v8[2 * v25 + 12] = *(_OWORD *)&v8[36 * v24 + 12];
              v27 = *(_OWORD *)&v8[36 * v24 + 20];
              *(_OWORD *)&v8[2 * v25 + 16] = v26;
              v28 = *(_OWORD *)&v8[36 * v24 + 24];
              *(_OWORD *)&v8[2 * v25 + 20] = v27;
              v29 = *(_OWORD *)&v8[36 * v24 + 28];
              *(_OWORD *)&v8[2 * v25 + 24] = v28;
              v30 = *(_OWORD *)&v8[36 * v24 + 32];
              *(_OWORD *)&v8[2 * v25 + 28] = v29;
              v31 = *(_OWORD *)&v8[36 * v24 + 36];
              *(_OWORD *)&v8[2 * v25 + 32] = v30;
              v32 = *(_OWORD *)&v8[36 * v24 + 40];
              *(_OWORD *)&v8[2 * v25 + 36] = v31;
              v33 = *(_OWORD *)&v8[36 * v24 + 44];
              *(_OWORD *)&v8[2 * v25 + 40] = v32;
              *(_OWORD *)&v8[2 * v25 + 44] = v33;
              v23 = v24;
            }
            while ( (unsigned int)v24 > (unsigned int)i );
          }
          v17 = (unsigned int)(v17 + 1);
          v34 = *(_OWORD *)&a4->PartitionEntry[v18].PartitionLength.LowPart;
          v35 = 18 * i;
          *(_OWORD *)&v8[2 * v35 + 12] = *(_OWORD *)&a4->PartitionEntry[v18].PartitionStyle;
          v36 = *(_OWORD *)&a4->PartitionEntry[v18].Mbr.PartitionType;
          *(_OWORD *)&v8[2 * v35 + 16] = v34;
          PartitionId = a4->PartitionEntry[v18].Gpt.PartitionId;
          *(_OWORD *)&v8[2 * v35 + 20] = v36;
          v38 = *(_OWORD *)&a4->PartitionEntry[v18].Gpt.Attributes;
          *(GUID *)&v8[2 * v35 + 24] = PartitionId;
          v39 = *(_OWORD *)&a4->PartitionEntry[v18].Gpt.Name[4];
          *(_OWORD *)&v8[2 * v35 + 28] = v38;
          v40 = *(_OWORD *)&a4->PartitionEntry[v18].Gpt.Name[12];
          *(_OWORD *)&v8[2 * v35 + 32] = v39;
          v41 = *(_OWORD *)&a4->PartitionEntry[v18].Gpt.Name[20];
          *(_OWORD *)&v8[2 * v35 + 36] = v40;
          v42 = *(_OWORD *)&a4->PartitionEntry[v18].Gpt.Name[28];
          *(_OWORD *)&v8[2 * v35 + 40] = v41;
          *(_OWORD *)&v8[2 * v35 + 44] = v42;
          LOBYTE(v8[2 * v35 + 19]) = 1;
        }
        v18 = (unsigned int)(v18 + 1);
      }
      while ( (unsigned int)v18 < PartitionCount );
      v14 = (VMX_PHYSICAL_DISK *)this;
    }
    for ( j = *(_QWORD *)(v6 + 120); ; j = v44[20] )
    {
      if ( !j )
      {
        v54 = a4->PartitionCount;
        v55.QuadPart = v15 * (v82 + v83);
        v56 = 0;
        v57 = v17;
        while ( (unsigned int)v56 < v54 )
        {
          v58 = a4->PartitionEntry[v56].StartingOffset;
          if ( v58.QuadPart >= (unsigned __int64)v55.QuadPart )
          {
            if ( (unsigned int)v17 >= a4->Gpt.MaxPartitionCount )
            {
              ExFreePoolWithTag(v8, 0);
              v52 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
              {
                v53 = 112;
                goto LABEL_50;
              }
              return 3224895504LL;
            }
            for ( k = v57; k < (unsigned int)v17; ++k )
            {
              if ( v58.QuadPart < *(_QWORD *)&v8[36 * k + 14] )
                break;
            }
            v60 = v17;
            if ( (unsigned int)v17 > k )
            {
              do
              {
                v61 = v60 - 1;
                v62 = 18LL * v60;
                v63 = *(_OWORD *)&v8[36 * v61 + 16];
                *(_OWORD *)&v8[2 * v62 + 12] = *(_OWORD *)&v8[36 * v61 + 12];
                v64 = *(_OWORD *)&v8[36 * v61 + 20];
                *(_OWORD *)&v8[2 * v62 + 16] = v63;
                v65 = *(_OWORD *)&v8[36 * v61 + 24];
                *(_OWORD *)&v8[2 * v62 + 20] = v64;
                v66 = *(_OWORD *)&v8[36 * v61 + 28];
                *(_OWORD *)&v8[2 * v62 + 24] = v65;
                v67 = *(_OWORD *)&v8[36 * v61 + 32];
                *(_OWORD *)&v8[2 * v62 + 28] = v66;
                v68 = *(_OWORD *)&v8[36 * v61 + 36];
                *(_OWORD *)&v8[2 * v62 + 32] = v67;
                v69 = *(_OWORD *)&v8[36 * v61 + 40];
                *(_OWORD *)&v8[2 * v62 + 36] = v68;
                v70 = *(_OWORD *)&v8[36 * v61 + 44];
                *(_OWORD *)&v8[2 * v62 + 40] = v69;
                *(_OWORD *)&v8[2 * v62 + 44] = v70;
                v60 = v61;
              }
              while ( (unsigned int)v61 > k );
            }
            LODWORD(v17) = v17 + 1;
            v71 = *(_OWORD *)&a4->PartitionEntry[v56].PartitionLength.LowPart;
            v72 = 18LL * k;
            *(_OWORD *)&v8[2 * v72 + 12] = *(_OWORD *)&a4->PartitionEntry[v56].PartitionStyle;
            v73 = *(_OWORD *)&a4->PartitionEntry[v56].Mbr.PartitionType;
            *(_OWORD *)&v8[2 * v72 + 16] = v71;
            v74 = a4->PartitionEntry[v56].Gpt.PartitionId;
            *(_OWORD *)&v8[2 * v72 + 20] = v73;
            v75 = *(_OWORD *)&a4->PartitionEntry[v56].Gpt.Attributes;
            *(GUID *)&v8[2 * v72 + 24] = v74;
            v76 = *(_OWORD *)&a4->PartitionEntry[v56].Gpt.Name[4];
            *(_OWORD *)&v8[2 * v72 + 28] = v75;
            v77 = *(_OWORD *)&a4->PartitionEntry[v56].Gpt.Name[12];
            *(_OWORD *)&v8[2 * v72 + 32] = v76;
            v78 = *(_OWORD *)&a4->PartitionEntry[v56].Gpt.Name[20];
            *(_OWORD *)&v8[2 * v72 + 36] = v77;
            v79 = *(_OWORD *)&a4->PartitionEntry[v56].Gpt.Name[28];
            *(_OWORD *)&v8[2 * v72 + 40] = v78;
            *(_OWORD *)&v8[2 * v72 + 44] = v79;
            LOBYTE(v8[2 * v72 + 19]) = 1;
          }
          v56 = (unsigned int)(v56 + 1);
        }
        v8[1] = v17;
        v10 = VMX_DISK_DEVICE::SetDriveLayoutExSynchronous(this[2], v8);
        ExFreePoolWithTag(v8, 0);
        if ( (v10 & 0x80000000) != 0 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
          {
            v11 = 113;
            goto LABEL_57;
          }
        }
        return v10;
      }
      v10 = -1070071803;
      v44 = *(_QWORD **)(j + 8LL * (*(_WORD *)(j + 64) & 1) + 40);
      v45 = *(_QWORD *)(v44[21] + 8LL * (*(_WORD *)(v44[21] + 64LL) & 1) + 40);
      if ( *(_BYTE *)(v45 + 87) != 2 || *(_DWORD *)(v45 + 92) != 1 )
        break;
      if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v45 + 136) + 8LL * (*(_WORD *)(*(_QWORD *)(v45 + 136) + 64LL) & 1) + 40)
                     + 160LL) != 1 )
      {
        ExFreePoolWithTag(v8, 0);
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
        {
          v11 = 110;
          goto LABEL_57;
        }
        return v10;
      }
      if ( (unsigned int)v17 >= a4->Gpt.MaxPartitionCount )
      {
        ExFreePoolWithTag(v8, 0);
        v52 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
        {
          v53 = 111;
LABEL_50:
          WPP_SF_d(*((_QWORD *)v52 + 3), v53, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids, 3224895504LL);
        }
        return 3224895504LL;
      }
      v46 = 36 * v17;
      v47 = *(_QWORD *)(*((_QWORD *)v14 + 11) + 136LL) * v15;
      v48 = (wchar_t *)&v8[36 * v17 + 30];
      v49 = v44[10] << 9;
      v17 = (unsigned int)(v17 + 1);
      *(_QWORD *)&v8[v46 + 16] = v44[12] << 9;
      *(_QWORD *)&v8[v46 + 14] = v49 + v47;
      v8[v46 + 12] = 1;
      LOBYTE(v8[v46 + 19]) = 1;
      *(GUID *)&v8[v46 + 20] = PARTITION_BASIC_DATA_GUID;
      RtlStringCbCopyW(v48, 0x48u, L"Basic data partition");
      *(_OWORD *)&v8[v46 + 24] = *(_OWORD *)(v50 + 232);
      GptAttributes = VMX_VOLUME_INFO::QueryGptAttributes((VMX_VOLUME_INFO *)v50);
      v14 = (VMX_PHYSICAL_DISK *)this;
      *(_QWORD *)&v8[v46 + 28] = GptAttributes;
    }
    ExFreePoolWithTag(v8, 0);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v11 = 109;
      goto LABEL_57;
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    v10 = -1073741670;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v11 = 108;
LABEL_57:
      WPP_SF_d(*((_QWORD *)v9 + 3), v11, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids, v10);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x1400437c8  mov     [rsp+arg_18], rbx
0x1400437cd  mov     [rsp+arg_0], rcx
0x1400437d2  push    rbp
0x1400437d3  push    rsi
0x1400437d4  push    rdi
0x1400437d5  push    r12
0x1400437d7  push    r13
0x1400437d9  push    r14
0x1400437db  push    r15
0x1400437dd  sub     rsp, 20h
0x1400437e1  movzx   eax, word ptr [rdx+40h]
0x1400437e5  mov     ecx, 102h
0x1400437ea  mov     ebx, [r8+14h]
0x1400437ee  and     eax, 1
0x1400437f1  mov     r8d, 614C6D56h
0x1400437f7  mov     rsi, r9
0x1400437fa  mov     r13, [rdx+rax*8+28h]
0x1400437ff  mov     eax, [r9+28h]
0x140043803  lea     rdx, [rax+rax*8]
0x140043807  shl     rdx, 4
0x14004380b  add     rdx, 30h ; '0'
0x14004380f  call    cs:__imp_ExAllocatePool2
0x140043816  nop     dword ptr [rax+rax+00h]
0x14004381b  mov     rdi, rax
0x14004381e  test    rax, rax
0x140043821  jnz     short loc_14004385F
0x140043823  mov     rcx, cs:WPP_GLOBAL_Control
0x14004382a  lea     rax, WPP_GLOBAL_Control
0x140043831  mov     ebx, 0C000009Ah
0x140043836  cmp     rcx, rax
0x140043839  jz      loc_140043E69
0x14004383f  mov     eax, [rcx+2Ch]
0x140043842  test    al, 10h
0x140043844  jz      loc_140043E69
0x14004384a  mov     r14b, 2
0x14004384d  cmp     [rcx+29h], r14b
0x140043851  jb      loc_140043E69
0x140043857  lea     edx, [rdi+6Ch]
0x14004385a  jmp     loc_140043E56
0x14004385f  movups  xmm0, xmmword ptr [rsi]
0x140043862  xor     edx, edx; Val
0x140043864  lea     rcx, [rdi+30h]; void *
0x140043868  movups  xmm1, xmmword ptr [rsi+10h]
0x14004386c  movups  xmmword ptr [rax], xmm0
0x14004386f  movups  xmm0, xmmword ptr [rsi+20h]
0x140043873  movups  xmmword ptr [rax+10h], xmm1
0x140043877  movups  xmmword ptr [rax+20h], xmm0
0x14004387b  mov     dword ptr [rax+4], 0
0x140043882  mov     eax, [rsi+28h]
0x140043885  lea     r8, [rax+rax*8]
0x140043889  shl     r8, 4; Size
0x14004388d  call    memset
0x140043892  mov     r8, [rsp+58h+arg_0]
0x140043897  mov     r12, rbx
0x14004389a  mov     r14d, [rsi+4]
0x14004389e  xor     ebp, ebp
0x1400438a0  xor     r11d, r11d
0x1400438a3  mov     rax, [r8+58h]
0x1400438a7  mov     rdx, [rax+88h]
0x1400438ae  imul    rbx, rdx
0x1400438b2  mov     [rsp+58h+arg_8], rdx
0x1400438b7  mov     rdx, [rax+90h]
0x1400438be  mov     [rsp+58h+arg_10], rdx
0x1400438c3  test    r14d, r14d
0x1400438c6  jz      loc_140043A3D
0x1400438cc  lea     r9, [r11+r11*8]
0x1400438d0  add     r9, r9
0x1400438d3  mov     rdx, [rsi+r9*8+38h]
0x1400438d8  mov     rcx, [rsi+r9*8+40h]
0x1400438dd  add     rcx, rdx
0x1400438e0  cmp     rcx, rbx
0x1400438e3  ja      loc_140043A2C
0x1400438e9  xor     r10d, r10d
0x1400438ec  test    ebp, ebp
0x1400438ee  jz      short loc_140043906
0x1400438f0  lea     rcx, [r10+r10*8]
0x1400438f4  add     rcx, rcx
0x1400438f7  cmp     rdx, [rdi+rcx*8+38h]
0x1400438fc  jb      short loc_140043906
0x1400438fe  inc     r10d
0x140043901  cmp     r10d, ebp
0x140043904  jb      short loc_1400438F0
0x140043906  mov     ecx, ebp
0x140043908  cmp     ebp, r10d
0x14004390b  jbe     loc_1400439A3
0x140043911  lea     r8d, [rcx-1]
0x140043915  mov     eax, ecx
0x140043917  lea     rdx, [r8+r8*8]
0x14004391b  add     rdx, rdx
0x14004391e  lea     rcx, [rax+rax*8]
0x140043922  add     rcx, rcx
0x140043925  movups  xmm0, xmmword ptr [rdi+rdx*8+30h]
0x14004392a  movups  xmm1, xmmword ptr [rdi+rdx*8+40h]
0x14004392f  movups  xmmword ptr [rdi+rcx*8+30h], xmm0
0x140043934  movups  xmm0, xmmword ptr [rdi+rdx*8+50h]
0x140043939  movups  xmmword ptr [rdi+rcx*8+40h], xmm1
0x14004393e  movups  xmm1, xmmword ptr [rdi+rdx*8+60h]
0x140043943  movups  xmmword ptr [rdi+rcx*8+50h], xmm0
0x140043948  movups  xmm0, xmmword ptr [rdi+rdx*8+70h]
0x14004394d  movups  xmmword ptr [rdi+rcx*8+60h], xmm1
0x140043952  movups  xmm1, xmmword ptr [rdi+rdx*8+80h]
0x14004395a  movups  xmmword ptr [rdi+rcx*8+70h], xmm0
0x14004395f  movups  xmm0, xmmword ptr [rdi+rdx*8+90h]
0x140043967  movups  xmmword ptr [rdi+rcx*8+80h], xmm1
0x14004396f  movups  xmm1, xmmword ptr [rdi+rdx*8+0A0h]
0x140043977  movups  xmmword ptr [rdi+rcx*8+90h], xmm0
0x14004397f  movups  xmm0, xmmword ptr [rdi+rdx*8+0B0h]
0x140043987  movups  xmmword ptr [rdi+rcx*8+0A0h], xmm1
0x14004398f  movups  xmmword ptr [rdi+rcx*8+0B0h], xmm0
0x140043997  mov     ecx, r8d
0x14004399a  cmp     r8d, r10d
0x14004399d  ja      loc_140043911
0x1400439a3  movups  xmm0, xmmword ptr [rsi+r9*8+30h]
0x1400439a9  inc     ebp
0x1400439ab  lea     rcx, [r10+r10*8]
0x1400439af  movups  xmm1, xmmword ptr [rsi+r9*8+40h]
0x1400439b5  add     rcx, rcx
0x1400439b8  movups  xmmword ptr [rdi+rcx*8+30h], xmm0
0x1400439bd  movups  xmm0, xmmword ptr [rsi+r9*8+50h]
0x1400439c3  movups  xmmword ptr [rdi+rcx*8+40h], xmm1
0x1400439c8  movups  xmm1, xmmword ptr [rsi+r9*8+60h]
0x1400439ce  movups  xmmword ptr [rdi+rcx*8+50h], xmm0
0x1400439d3  movups  xmm0, xmmword ptr [rsi+r9*8+70h]
0x1400439d9  movups  xmmword ptr [rdi+rcx*8+60h], xmm1
0x1400439de  movups  xmm1, xmmword ptr [rsi+r9*8+80h]
0x1400439e7  movups  xmmword ptr [rdi+rcx*8+70h], xmm0
0x1400439ec  movups  xmm0, xmmword ptr [rsi+r9*8+90h]
0x1400439f5  movups  xmmword ptr [rdi+rcx*8+80h], xmm1
0x1400439fd  movups  xmm1, xmmword ptr [rsi+r9*8+0A0h]
0x140043a06  movups  xmmword ptr [rdi+rcx*8+90h], xmm0
0x140043a0e  movups  xmm0, xmmword ptr [rsi+r9*8+0B0h]
0x140043a17  movups  xmmword ptr [rdi+rcx*8+0A0h], xmm1
0x140043a1f  movups  xmmword ptr [rdi+rcx*8+0B0h], xmm0
0x140043a27  mov     byte ptr [rdi+rcx*8+4Ch], 1
0x140043a2c  inc     r11d
0x140043a2f  cmp     r11d, r14d
0x140043a32  jb      loc_1400438CC
0x140043a38  mov     r8, [rsp+58h+arg_0]
0x140043a3d  mov     rcx, [r13+78h]
0x140043a41  mov     r14b, 2
0x140043a44  test    rcx, rcx
0x140043a47  jz      loc_140043C20
0x140043a4d  movzx   eax, word ptr [rcx+40h]
0x140043a51  mov     ebx, 0C0380005h
0x140043a56  and     eax, 1
0x140043a59  mov     r13, [rcx+rax*8+28h]
0x140043a5e  mov     rcx, [r13+0A8h]
0x140043a65  movzx   eax, word ptr [rcx+40h]
0x140043a69  and     eax, 1
0x140043a6c  mov     rcx, [rcx+rax*8+28h]
0x140043a71  cmp     [rcx+57h], r14b
0x140043a75  jnz     loc_140043BD8
0x140043a7b  cmp     dword ptr [rcx+5Ch], 1
0x140043a7f  jnz     loc_140043BD8
0x140043a85  mov     rcx, [rcx+88h]
0x140043a8c  movzx   eax, word ptr [rcx+40h]
0x140043a90  and     eax, 1
0x140043a93  mov     r11, [rcx+rax*8+28h]
0x140043a98  cmp     dword ptr [r11+0A0h], 1
0x140043aa0  jnz     loc_140043B91
0x140043aa6  cmp     ebp, [rsi+28h]
0x140043aa9  jnb     loc_140043B4A
0x140043aaf  mov     rax, [r8+58h]
0x140043ab3  lea     rbx, ds:0[rbp*8]
0x140043abb  mov     r8, [r13+60h]
0x140043abf  lea     rcx, [rdi+78h]
0x140043ac3  movups  xmm0, xmmword ptr cs:PARTITION_BASIC_DATA_GUID.Data1
0x140043aca  shl     r8, 9
0x140043ace  add     rbx, rbp
0x140043ad1  shl     rbx, 4
0x140043ad5  mov     rdx, r12
0x140043ad8  imul    rdx, [rax+88h]
0x140043ae0  mov     rax, [r13+50h]
0x140043ae4  add     rcx, rbx; pszDest
0x140043ae7  shl     rax, 9
0x140043aeb  inc     ebp
0x140043aed  add     rdx, rax
0x140043af0  mov     [rbx+rdi+40h], r8
0x140043af5  mov     [rbx+rdi+38h], rdx
0x140043afa  lea     r8, aBasicDataParti; "Basic data partition"
0x140043b01  mov     edx, 48h ; 'H'; cbDest
0x140043b06  mov     dword ptr [rbx+rdi+30h], 1
0x140043b0e  mov     byte ptr [rbx+rdi+4Ch], 1
0x140043b13  movdqu  xmmword ptr [rbx+rdi+50h], xmm0
0x140043b19  call    RtlStringCbCopyW
0x140043b1e  movups  xmm0, xmmword ptr [r11+0E8h]
0x140043b26  mov     rcx, r11; this
0x140043b29  movdqu  xmmword ptr [rbx+rdi+60h], xmm0
0x140043b2f  call    ?QueryGptAttributes@VMX_VOLUME_INFO@@QEAA_KXZ; VMX_VOLUME_INFO::QueryGptAttributes(void)
0x140043b34  mov     r8, [rsp+58h+arg_0]
0x140043b39  mov     [rbx+rdi+70h], rax
0x140043b3e  mov     rcx, [r13+0A0h]
0x140043b45  jmp     loc_140043A44
0x140043b4a  xor     edx, edx; Tag
0x140043b4c  mov     rcx, rdi; P
0x140043b4f  call    cs:__imp_ExFreePoolWithTag
0x140043b56  nop     dword ptr [rax+rax+00h]
0x140043b5b  mov     rcx, cs:WPP_GLOBAL_Control
0x140043b62  lea     rax, WPP_GLOBAL_Control
0x140043b69  cmp     rcx, rax
0x140043b6c  jz      loc_140043DFE
0x140043b72  mov     eax, [rcx+2Ch]
0x140043b75  test    al, 10h
0x140043b77  jz      loc_140043DFE
0x140043b7d  cmp     [rcx+29h], r14b
0x140043b81  jb      loc_140043DFE
0x140043b87  mov     edx, 6Fh ; 'o'
0x140043b8c  jmp     loc_140043DE8
0x140043b91  xor     edx, edx; Tag
0x140043b93  mov     rcx, rdi; P
0x140043b96  call    cs:__imp_ExFreePoolWithTag
0x140043b9d  nop     dword ptr [rax+rax+00h]
0x140043ba2  mov     rcx, cs:WPP_GLOBAL_Control
0x140043ba9  lea     rax, WPP_GLOBAL_Control
0x140043bb0  cmp     rcx, rax
0x140043bb3  jz      loc_140043E69
0x140043bb9  mov     eax, [rcx+2Ch]
0x140043bbc  test    al, 10h
0x140043bbe  jz      loc_140043E69
0x140043bc4  cmp     [rcx+29h], r14b
0x140043bc8  jb      loc_140043E69
0x140043bce  mov     edx, 6Eh ; 'n'
0x140043bd3  jmp     loc_140043E56
0x140043bd8  xor     edx, edx; Tag
0x140043bda  mov     rcx, rdi; P
0x140043bdd  call    cs:__imp_ExFreePoolWithTag
0x140043be4  nop     dword ptr [rax+rax+00h]
0x140043be9  mov     rcx, cs:WPP_GLOBAL_Control
0x140043bf0  lea     rax, WPP_GLOBAL_Control
0x140043bf7  cmp     rcx, rax
0x140043bfa  jz      loc_140043E69
0x140043c00  mov     edx, [rcx+2Ch]
0x140043c03  test    dl, 10h
0x140043c06  jz      loc_140043E69
0x140043c0c  cmp     [rcx+29h], r14b
0x140043c10  jb      loc_140043E69
0x140043c16  mov     edx, 6Dh ; 'm'
0x140043c1b  jmp     loc_140043E56
0x140043c20  mov     rbx, [rsp+58h+arg_10]
0x140043c25  add     rbx, [rsp+58h+arg_8]
0x140043c2a  mov     r13d, [rsi+4]
0x140043c2e  imul    rbx, r12
0x140043c32  xor     r11d, r11d
0x140043c35  mov     r12d, ebp
0x140043c38  cmp     r11d, r13d
0x140043c3b  jnb     loc_140043E05
0x140043c41  lea     r9, [r11+r11*8]
0x140043c45  add     r9, r9
0x140043c48  mov     rdx, [rsi+r9*8+38h]
0x140043c4d  cmp     rdx, rbx
0x140043c50  jb      loc_140043DA9
0x140043c56  cmp     ebp, [rsi+28h]
0x140043c59  jnb     loc_140043DB1
0x140043c5f  mov     r10d, r12d
0x140043c62  cmp     r12d, ebp
0x140043c65  jnb     short loc_140043C80
0x140043c67  mov     eax, r10d
0x140043c6a  lea     rcx, [rax+rax*8]
0x140043c6e  add     rcx, rcx
0x140043c71  cmp     rdx, [rdi+rcx*8+38h]
0x140043c76  jb      short loc_140043C80
0x140043c78  inc     r10d
0x140043c7b  cmp     r10d, ebp
0x140043c7e  jb      short loc_140043C67
0x140043c80  mov     ecx, ebp
0x140043c82  cmp     ebp, r10d
0x140043c85  jbe     loc_140043D1D
0x140043c8b  lea     r8d, [rcx-1]
0x140043c8f  mov     eax, ecx
0x140043c91  lea     rdx, [r8+r8*8]
0x140043c95  add     rdx, rdx
0x140043c98  lea     rcx, [rax+rax*8]
0x140043c9c  add     rcx, rcx
0x140043c9f  movups  xmm0, xmmword ptr [rdi+rdx*8+30h]
0x140043ca4  movups  xmm1, xmmword ptr [rdi+rdx*8+40h]
0x140043ca9  movups  xmmword ptr [rdi+rcx*8+30h], xmm0
0x140043cae  movups  xmm0, xmmword ptr [rdi+rdx*8+50h]
0x140043cb3  movups  xmmword ptr [rdi+rcx*8+40h], xmm1
0x140043cb8  movups  xmm1, xmmword ptr [rdi+rdx*8+60h]
0x140043cbd  movups  xmmword ptr [rdi+rcx*8+50h], xmm0
0x140043cc2  movups  xmm0, xmmword ptr [rdi+rdx*8+70h]
0x140043cc7  movups  xmmword ptr [rdi+rcx*8+60h], xmm1
0x140043ccc  movups  xmm1, xmmword ptr [rdi+rdx*8+80h]
0x140043cd4  movups  xmmword ptr [rdi+rcx*8+70h], xmm0
0x140043cd9  movups  xmm0, xmmword ptr [rdi+rdx*8+90h]
0x140043ce1  movups  xmmword ptr [rdi+rcx*8+80h], xmm1
0x140043ce9  movups  xmm1, xmmword ptr [rdi+rdx*8+0A0h]
0x140043cf1  movups  xmmword ptr [rdi+rcx*8+90h], xmm0
0x140043cf9  movups  xmm0, xmmword ptr [rdi+rdx*8+0B0h]
0x140043d01  movups  xmmword ptr [rdi+rcx*8+0A0h], xmm1
0x140043d09  movups  xmmword ptr [rdi+rcx*8+0B0h], xmm0
0x140043d11  mov     ecx, r8d
0x140043d14  cmp     r8d, r10d
0x140043d17  ja      loc_140043C8B
0x140043d1d  movups  xmm0, xmmword ptr [rsi+r9*8+30h]
0x140043d23  mov     eax, r10d
0x140043d26  inc     ebp
0x140043d28  movups  xmm1, xmmword ptr [rsi+r9*8+40h]
0x140043d2e  lea     rcx, [rax+rax*8]
0x140043d32  add     rcx, rcx
  ... truncated ...
```
