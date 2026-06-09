# VmxpPrepareForDeleteDynamicPartitionsGpt(_DISK_GEOMETRY *,_DRIVE_LAYOUT_INFORMATION_EX *,_DRIVE_LAYOUT_INFORMATION_EX * *)

- ea: `0x140047134`
- end: `0x14004735f`
- name: `?VmxpPrepareForDeleteDynamicPartitionsGpt@@YAJPEAU_DISK_GEOMETRY@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAPEAU2@@Z`
- size: `555`
- prototype: `__int64 __fastcall(struct _DISK_GEOMETRY *, struct _DRIVE_LAYOUT_INFORMATION_EX *, struct _DRIVE_LAYOUT_INFORMATION_EX **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140034c20`
- `0x1400458e8`

## callees

- `0x14001be80`
- `0x140047134`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140047168`
- `ntoskrnl!ExAllocatePool2` at `0x140047168`

## pseudocode

```c
__int64 __fastcall VmxpPrepareForDeleteDynamicPartitionsGpt(
        struct _DISK_GEOMETRY *a1,
        struct _DRIVE_LAYOUT_INFORMATION_EX *a2,
        struct _DRIVE_LAYOUT_INFORMATION_EX **a3)
{
  __int64 PartitionCount; // rax
  __int64 Pool2; // rax
  struct _DRIVE_LAYOUT_INFORMATION_EX *v7; // rbx
  __int64 result; // rax
  __int64 v9; // r14
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  unsigned int v12; // r11d
  __int64 i; // rsi
  __int64 v14; // rax
  __int64 j; // r10
  unsigned int v16; // ecx
  __int64 v17; // r8
  __int64 v18; // rcx
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  GUID PartitionId; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int64 v28; // rcx
  __int128 v29; // xmm0
  GUID v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0

  PartitionCount = a2->PartitionCount;
  *a3 = 0;
  Pool2 = ExAllocatePool2(258, 144 * PartitionCount + 48, 1632398678);
  v7 = (struct _DRIVE_LAYOUT_INFORMATION_EX *)Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  v9 = a2->PartitionCount;
  v10 = *(_OWORD *)a2->Gpt.DiskId.Data4;
  *(_OWORD *)Pool2 = *(_OWORD *)&a2->PartitionStyle;
  v11 = *(_OWORD *)&a2->Gpt.UsableLength.LowPart;
  *(_OWORD *)(Pool2 + 16) = v10;
  *(_OWORD *)(Pool2 + 32) = v11;
  *(_DWORD *)(Pool2 + 4) = 0;
  memset((void *)(Pool2 + 48), 0, 144 * v9);
  v12 = 0;
  for ( i = 0; (unsigned int)i < (unsigned int)v9; i = (unsigned int)(i + 1) )
  {
    v14 = *(_QWORD *)&a2->PartitionEntry[i].Mbr - *(_QWORD *)&PARTITION_LDM_DATA_GUID.Data1;
    if ( !v14 )
      v14 = *(_QWORD *)a2->PartitionEntry[i].Gpt.PartitionType.Data4 - *(_QWORD *)PARTITION_LDM_DATA_GUID.Data4;
    if ( v14 )
    {
      for ( j = 0; (unsigned int)j < v12; j = (unsigned int)(j + 1) )
      {
        if ( a2->PartitionEntry[i].StartingOffset.QuadPart < (unsigned __int64)v7->PartitionEntry[j].StartingOffset.QuadPart )
          break;
      }
      v16 = v12;
      if ( v12 > (unsigned int)j )
      {
        do
        {
          v17 = v16 - 1;
          v18 = v16;
          v19 = *(_OWORD *)&v7->PartitionEntry[v17].PartitionLength.LowPart;
          *(_OWORD *)&v7->PartitionEntry[v18].PartitionStyle = *(_OWORD *)&v7->PartitionEntry[v17].PartitionStyle;
          v20 = *(_OWORD *)&v7->PartitionEntry[v17].Mbr.PartitionType;
          *(_OWORD *)&v7->PartitionEntry[v18].PartitionLength.LowPart = v19;
          PartitionId = v7->PartitionEntry[v17].Gpt.PartitionId;
          *(_OWORD *)&v7->PartitionEntry[v18].Mbr.PartitionType = v20;
          v22 = *(_OWORD *)&v7->PartitionEntry[v17].Gpt.Attributes;
          v7->PartitionEntry[v18].Gpt.PartitionId = PartitionId;
          v23 = *(_OWORD *)&v7->PartitionEntry[v17].Gpt.Name[4];
          *(_OWORD *)&v7->PartitionEntry[v18].Gpt.Attributes = v22;
          v24 = *(_OWORD *)&v7->PartitionEntry[v17].Gpt.Name[12];
          *(_OWORD *)&v7->PartitionEntry[v18].Gpt.Name[4] = v23;
          v25 = *(_OWORD *)&v7->PartitionEntry[v17].Gpt.Name[20];
          *(_OWORD *)&v7->PartitionEntry[v18].Gpt.Name[12] = v24;
          v26 = *(_OWORD *)&v7->PartitionEntry[v17].Gpt.Name[28];
          *(_OWORD *)&v7->PartitionEntry[v18].Gpt.Name[20] = v25;
          *(_OWORD *)&v7->PartitionEntry[v18].Gpt.Name[28] = v26;
          v16 = v17;
        }
        while ( (unsigned int)v17 > (unsigned int)j );
      }
      ++v12;
      v27 = *(_OWORD *)&a2->PartitionEntry[i].PartitionLength.LowPart;
      v28 = j;
      *(_OWORD *)&v7->PartitionEntry[v28].PartitionStyle = *(_OWORD *)&a2->PartitionEntry[i].PartitionStyle;
      v29 = *(_OWORD *)&a2->PartitionEntry[i].Mbr.PartitionType;
      *(_OWORD *)&v7->PartitionEntry[v28].PartitionLength.LowPart = v27;
      v30 = a2->PartitionEntry[i].Gpt.PartitionId;
      *(_OWORD *)&v7->PartitionEntry[v28].Mbr.PartitionType = v29;
      v31 = *(_OWORD *)&a2->PartitionEntry[i].Gpt.Attributes;
      v7->PartitionEntry[v28].Gpt.PartitionId = v30;
      v32 = *(_OWORD *)&a2->PartitionEntry[i].Gpt.Name[4];
      *(_OWORD *)&v7->PartitionEntry[v28].Gpt.Attributes = v31;
      v33 = *(_OWORD *)&a2->PartitionEntry[i].Gpt.Name[12];
      *(_OWORD *)&v7->PartitionEntry[v28].Gpt.Name[4] = v32;
      v34 = *(_OWORD *)&a2->PartitionEntry[i].Gpt.Name[20];
      *(_OWORD *)&v7->PartitionEntry[v28].Gpt.Name[12] = v33;
      v35 = *(_OWORD *)&a2->PartitionEntry[i].Gpt.Name[28];
      *(_OWORD *)&v7->PartitionEntry[v28].Gpt.Name[20] = v34;
      *(_OWORD *)&v7->PartitionEntry[v28].Gpt.Name[28] = v35;
      v7->PartitionEntry[v28].RewritePartition = 1;
    }
  }
  v7->PartitionCount = v12;
  result = 0;
  *a3 = v7;
  return result;
}

```

## disassembly

```asm
0x140047134  push    rbx
0x140047136  push    rbp
0x140047137  push    rsi
0x140047138  push    rdi
0x140047139  push    r14
0x14004713b  push    r15
0x14004713d  sub     rsp, 28h
0x140047141  mov     eax, [rdx+4]
0x140047144  mov     rdi, rdx
0x140047147  mov     r15, r8
0x14004714a  mov     qword ptr [r8], 0
0x140047151  mov     ecx, 102h
0x140047156  mov     r8d, 614C6D56h
0x14004715c  lea     rdx, [rax+rax*8]
0x140047160  shl     rdx, 4
0x140047164  add     rdx, 30h ; '0'
0x140047168  call    cs:__imp_ExAllocatePool2
0x14004716f  nop     dword ptr [rax+rax+00h]
0x140047174  mov     rbx, rax
0x140047177  test    rax, rax
0x14004717a  jnz     short loc_140047186
0x14004717c  mov     eax, 0C000009Ah
0x140047181  jmp     loc_140047351
0x140047186  movups  xmm0, xmmword ptr [rdi]
0x140047189  mov     r14d, [rdi+4]
0x14004718d  xor     edx, edx; Val
0x14004718f  movups  xmm1, xmmword ptr [rdi+10h]
0x140047193  lea     rcx, [rax+30h]; void *
0x140047197  movups  xmmword ptr [rax], xmm0
0x14004719a  lea     r8, [r14+r14*8]
0x14004719e  movups  xmm0, xmmword ptr [rdi+20h]
0x1400471a2  shl     r8, 4; Size
0x1400471a6  movups  xmmword ptr [rax+10h], xmm1
0x1400471aa  movups  xmmword ptr [rax+20h], xmm0
0x1400471ae  mov     dword ptr [rax+4], 0
0x1400471b5  call    memset
0x1400471ba  xor     r11d, r11d
0x1400471bd  xor     esi, esi
0x1400471bf  test    r14d, r14d
0x1400471c2  jz      loc_140047348
0x1400471c8  lea     r9, [rsi+rsi*8]
0x1400471cc  add     r9, r9
0x1400471cf  mov     rax, [rdi+r9*8+50h]
0x1400471d4  sub     rax, qword ptr cs:PARTITION_LDM_DATA_GUID.Data1
0x1400471db  jnz     short loc_1400471E9
0x1400471dd  mov     rax, [rdi+r9*8+58h]
0x1400471e2  sub     rax, qword ptr cs:PARTITION_LDM_DATA_GUID.Data4
0x1400471e9  test    rax, rax
0x1400471ec  jz      loc_14004733D
0x1400471f2  mov     rdx, [rdi+r9*8+38h]
0x1400471f7  xor     r10d, r10d
0x1400471fa  test    r11d, r11d
0x1400471fd  jz      short loc_140047215
0x1400471ff  lea     rcx, [r10+r10*8]
0x140047203  add     rcx, rcx
0x140047206  cmp     rdx, [rbx+rcx*8+38h]
0x14004720b  jb      short loc_140047215
0x14004720d  inc     r10d
0x140047210  cmp     r10d, r11d
0x140047213  jb      short loc_1400471FF
0x140047215  mov     ecx, r11d
0x140047218  cmp     r11d, r10d
0x14004721b  jbe     loc_1400472B3
0x140047221  lea     r8d, [rcx-1]
0x140047225  mov     eax, ecx
0x140047227  lea     rdx, [r8+r8*8]
0x14004722b  add     rdx, rdx
0x14004722e  lea     rcx, [rax+rax*8]
0x140047232  add     rcx, rcx
0x140047235  movups  xmm0, xmmword ptr [rbx+rdx*8+30h]
0x14004723a  movups  xmm1, xmmword ptr [rbx+rdx*8+40h]
0x14004723f  movups  xmmword ptr [rbx+rcx*8+30h], xmm0
0x140047244  movups  xmm0, xmmword ptr [rbx+rdx*8+50h]
0x140047249  movups  xmmword ptr [rbx+rcx*8+40h], xmm1
0x14004724e  movups  xmm1, xmmword ptr [rbx+rdx*8+60h]
0x140047253  movups  xmmword ptr [rbx+rcx*8+50h], xmm0
0x140047258  movups  xmm0, xmmword ptr [rbx+rdx*8+70h]
0x14004725d  movups  xmmword ptr [rbx+rcx*8+60h], xmm1
0x140047262  movups  xmm1, xmmword ptr [rbx+rdx*8+80h]
0x14004726a  movups  xmmword ptr [rbx+rcx*8+70h], xmm0
0x14004726f  movups  xmm0, xmmword ptr [rbx+rdx*8+90h]
0x140047277  movups  xmmword ptr [rbx+rcx*8+80h], xmm1
0x14004727f  movups  xmm1, xmmword ptr [rbx+rdx*8+0A0h]
0x140047287  movups  xmmword ptr [rbx+rcx*8+90h], xmm0
0x14004728f  movups  xmm0, xmmword ptr [rbx+rdx*8+0B0h]
0x140047297  movups  xmmword ptr [rbx+rcx*8+0A0h], xmm1
0x14004729f  movups  xmmword ptr [rbx+rcx*8+0B0h], xmm0
0x1400472a7  mov     ecx, r8d
0x1400472aa  cmp     r8d, r10d
0x1400472ad  ja      loc_140047221
0x1400472b3  movups  xmm0, xmmword ptr [rdi+r9*8+30h]
0x1400472b9  inc     r11d
0x1400472bc  lea     rcx, [r10+r10*8]
0x1400472c0  movups  xmm1, xmmword ptr [rdi+r9*8+40h]
0x1400472c6  add     rcx, rcx
0x1400472c9  movups  xmmword ptr [rbx+rcx*8+30h], xmm0
0x1400472ce  movups  xmm0, xmmword ptr [rdi+r9*8+50h]
0x1400472d4  movups  xmmword ptr [rbx+rcx*8+40h], xmm1
0x1400472d9  movups  xmm1, xmmword ptr [rdi+r9*8+60h]
0x1400472df  movups  xmmword ptr [rbx+rcx*8+50h], xmm0
0x1400472e4  movups  xmm0, xmmword ptr [rdi+r9*8+70h]
0x1400472ea  movups  xmmword ptr [rbx+rcx*8+60h], xmm1
0x1400472ef  movups  xmm1, xmmword ptr [rdi+r9*8+80h]
0x1400472f8  movups  xmmword ptr [rbx+rcx*8+70h], xmm0
0x1400472fd  movups  xmm0, xmmword ptr [rdi+r9*8+90h]
0x140047306  movups  xmmword ptr [rbx+rcx*8+80h], xmm1
0x14004730e  movups  xmm1, xmmword ptr [rdi+r9*8+0A0h]
0x140047317  movups  xmmword ptr [rbx+rcx*8+90h], xmm0
0x14004731f  movups  xmm0, xmmword ptr [rdi+r9*8+0B0h]
0x140047328  movups  xmmword ptr [rbx+rcx*8+0A0h], xmm1
0x140047330  movups  xmmword ptr [rbx+rcx*8+0B0h], xmm0
0x140047338  mov     byte ptr [rbx+rcx*8+4Ch], 1
0x14004733d  inc     esi
0x14004733f  cmp     esi, r14d
0x140047342  jb      loc_1400471C8
0x140047348  mov     [rbx+4], r11d
0x14004734c  xor     eax, eax
0x14004734e  mov     [r15], rbx
0x140047351  add     rsp, 28h
0x140047355  pop     r15
0x140047357  pop     r14
0x140047359  pop     rdi
0x14004735a  pop     rsi
0x14004735b  pop     rbp
0x14004735c  pop     rbx
0x14004735d  retn
```
