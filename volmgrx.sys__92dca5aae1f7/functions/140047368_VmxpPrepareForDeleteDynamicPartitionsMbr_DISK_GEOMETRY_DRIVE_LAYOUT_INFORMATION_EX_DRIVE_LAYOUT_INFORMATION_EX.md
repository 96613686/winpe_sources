# VmxpPrepareForDeleteDynamicPartitionsMbr(_DISK_GEOMETRY *,_DRIVE_LAYOUT_INFORMATION_EX *,_DRIVE_LAYOUT_INFORMATION_EX * *)

- ea: `0x140047368`
- end: `0x1400476a1`
- name: `?VmxpPrepareForDeleteDynamicPartitionsMbr@@YAJPEAU_DISK_GEOMETRY@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAPEAU2@@Z`
- size: `825`
- prototype: `__int64 __fastcall(struct _DISK_GEOMETRY *, struct _DRIVE_LAYOUT_INFORMATION_EX *, struct _DRIVE_LAYOUT_INFORMATION_EX **)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140034c20`
- `0x1400459b4`

## callees

- `0x1400099d8`
- `0x14001be80`
- `0x140047368`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400473ab`
- `ntoskrnl!ExAllocatePool2` at `0x1400473ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047655`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047655`

## pseudocode

```c
__int64 __fastcall VmxpPrepareForDeleteDynamicPartitionsMbr(
        struct _DISK_GEOMETRY *a1,
        struct _DRIVE_LAYOUT_INFORMATION_EX *a2,
        struct _DRIVE_LAYOUT_INFORMATION_EX **a3)
{
  DWORD PartitionCount; // eax
  int v5; // esi
  __int64 v7; // rsi
  __int64 Pool2; // rax
  struct _DRIVE_LAYOUT_INFORMATION_EX *v9; // rbx
  unsigned int v10; // edi
  char *v11; // rdi
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  DWORD v14; // r15d
  __int64 v15; // rdx
  char v16; // r11
  DWORD v17; // r10d
  char *v18; // r14
  unsigned int i; // r8d
  __int64 v20; // rax
  char *v21; // r9
  char v22; // al
  __int128 v23; // xmm1
  __int64 v24; // rcx
  __int128 v25; // xmm0
  GUID v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int64 v33; // rcx
  __int128 v34; // xmm0
  GUID v35; // xmm1
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  VMX_NOTIFICATION_QUEUE *v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // rcx

  PartitionCount = a2->PartitionCount;
  v5 = 4;
  *a3 = 0;
  if ( PartitionCount > 4 )
    v5 = PartitionCount;
  v7 = (v5 + 3) & 0xFFFFFFFC;
  Pool2 = ExAllocatePool2(258, (unsigned int)(144 * v7 + 48), 1632398678);
  v9 = (struct _DRIVE_LAYOUT_INFORMATION_EX *)Pool2;
  if ( !Pool2 )
  {
    v10 = -1073741670;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 3), 10, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids, 3221225626LL);
    }
    return v10;
  }
  v11 = 0;
  v12 = *(_OWORD *)a2->Gpt.DiskId.Data4;
  *(_OWORD *)Pool2 = *(_OWORD *)&a2->PartitionStyle;
  v13 = *(_OWORD *)&a2->Gpt.UsableLength.LowPart;
  *(_OWORD *)(Pool2 + 16) = v12;
  *(_OWORD *)(Pool2 + 32) = v13;
  *(_DWORD *)(Pool2 + 4) = 0;
  memset((void *)(Pool2 + 48), 0, 144 * v7);
  v14 = a2->PartitionCount;
  v15 = 0;
  v16 = 0;
  v17 = 0;
LABEL_9:
  if ( v17 >= v14 )
  {
    v10 = 0;
    while ( (unsigned int)v15 < (unsigned int)v7 && ((v15 & 3) != 0 || (unsigned int)v15 < 4) )
    {
      v43 = v15;
      v15 = (unsigned int)(v15 + 1);
      v9->PartitionEntry[v43].Mbr.PartitionType = 0;
      v9->PartitionEntry[v43].RewritePartition = 1;
    }
    v9->PartitionCount = v15;
    *a3 = v9;
    return v10;
  }
  v18 = 0;
  for ( i = 0; ; ++i )
  {
    v20 = v17 + i;
    if ( (unsigned int)v20 >= v14 || i >= 4 )
    {
      v11 = v18;
      v16 = 1;
      v17 += 4;
      goto LABEL_9;
    }
    v21 = (char *)a2 + 144 * v20;
    v22 = v21[80];
    if ( !v22 || v22 == 66 )
      continue;
    if ( v22 == 5 || v22 == 15 )
    {
      v18 = v21 + 48;
      continue;
    }
    if ( v16 )
      break;
LABEL_24:
    if ( (unsigned int)v15 >= (unsigned int)v7 )
    {
      v10 = -1070071797;
      v41 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v42 = 12;
        goto LABEL_37;
      }
      goto LABEL_38;
    }
    v32 = *((_OWORD *)v21 + 4);
    v33 = v15;
    v15 = (unsigned int)(v15 + 1);
    *(_OWORD *)&v9->PartitionEntry[v33].PartitionStyle = *((_OWORD *)v21 + 3);
    v34 = *((_OWORD *)v21 + 5);
    *(_OWORD *)&v9->PartitionEntry[v33].PartitionLength.LowPart = v32;
    v35 = (GUID)*((_OWORD *)v21 + 6);
    *(_OWORD *)&v9->PartitionEntry[v33].Mbr.PartitionType = v34;
    v36 = *((_OWORD *)v21 + 7);
    v9->PartitionEntry[v33].Gpt.PartitionId = v35;
    v37 = *((_OWORD *)v21 + 8);
    *(_OWORD *)&v9->PartitionEntry[v33].Gpt.Attributes = v36;
    v38 = *((_OWORD *)v21 + 9);
    *(_OWORD *)&v9->PartitionEntry[v33].Gpt.Name[4] = v37;
    v39 = *((_OWORD *)v21 + 10);
    *(_OWORD *)&v9->PartitionEntry[v33].Gpt.Name[12] = v38;
    v40 = *((_OWORD *)v21 + 11);
    *(_OWORD *)&v9->PartitionEntry[v33].Gpt.Name[20] = v39;
    *(_OWORD *)&v9->PartitionEntry[v33].Gpt.Name[28] = v40;
    v9->PartitionEntry[v33].RewritePartition = 1;
  }
  if ( (unsigned int)v15 < (unsigned int)v7 && v11 )
  {
    v23 = *((_OWORD *)v11 + 1);
    v24 = v15;
    *(_OWORD *)&v9->PartitionEntry[v24].PartitionStyle = *(_OWORD *)v11;
    v25 = *((_OWORD *)v11 + 2);
    *(_OWORD *)&v9->PartitionEntry[v24].PartitionLength.LowPart = v23;
    v26 = (GUID)*((_OWORD *)v11 + 3);
    *(_OWORD *)&v9->PartitionEntry[v24].Mbr.PartitionType = v25;
    v27 = *((_OWORD *)v11 + 4);
    v9->PartitionEntry[v24].Gpt.PartitionId = v26;
    v28 = *((_OWORD *)v11 + 5);
    *(_OWORD *)&v9->PartitionEntry[v24].Gpt.Attributes = v27;
    v29 = *((_OWORD *)v11 + 6);
    *(_OWORD *)&v9->PartitionEntry[v24].Gpt.Name[4] = v28;
    v30 = *((_OWORD *)v11 + 7);
    *(_OWORD *)&v9->PartitionEntry[v24].Gpt.Name[12] = v29;
    v31 = *((_OWORD *)v11 + 8);
    *(_OWORD *)&v9->PartitionEntry[v24].Gpt.Name[20] = v30;
    *(_OWORD *)&v9->PartitionEntry[v24].Gpt.Name[28] = v31;
    v9->PartitionEntry[v24].Mbr.PartitionType = 15;
    while ( 1 )
    {
      v15 = (unsigned int)(v15 + 1);
      v9->PartitionEntry[v24].RewritePartition = 1;
      if ( (v15 & 3) == 0 )
        break;
      v24 = v15;
      v9->PartitionEntry[v15].Mbr.PartitionType = 0;
    }
    v16 = 0;
    goto LABEL_24;
  }
  v10 = -1070071797;
  v41 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    v42 = 11;
LABEL_37:
    WPP_SF_d(*((_QWORD *)v41 + 3), v42, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids, 3224895499LL);
  }
LABEL_38:
  ExFreePoolWithTag(v9, 0);
  return v10;
}

```

## disassembly

```asm
0x140047368  push    rbx
0x14004736a  push    rbp
0x14004736b  push    rsi
0x14004736c  push    rdi
0x14004736d  push    r12
0x14004736f  push    r14
0x140047371  push    r15
0x140047373  sub     rsp, 20h
0x140047377  mov     eax, [rdx+4]
0x14004737a  mov     rbp, rdx
0x14004737d  mov     esi, 4
0x140047382  mov     qword ptr [r8], 0
0x140047389  cmp     eax, esi
0x14004738b  mov     r12, r8
0x14004738e  mov     ecx, 102h
0x140047393  mov     r8d, 614C6D56h
0x140047399  cmova   esi, eax
0x14004739c  add     esi, 3
0x14004739f  and     esi, 0FFFFFFFCh
0x1400473a2  lea     edx, [rsi+rsi*8]
0x1400473a5  shl     edx, 4
0x1400473a8  add     edx, 30h ; '0'
0x1400473ab  call    cs:__imp_ExAllocatePool2
0x1400473b2  nop     dword ptr [rax+rax+00h]
0x1400473b7  mov     rbx, rax
0x1400473ba  test    rax, rax
0x1400473bd  jnz     short loc_14004740B
0x1400473bf  mov     edi, 0C000009Ah
0x1400473c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400473cb  lea     rax, WPP_GLOBAL_Control
0x1400473d2  cmp     rcx, rax
0x1400473d5  jz      loc_14004768F
0x1400473db  mov     eax, [rcx+2Ch]
0x1400473de  test    al, 10h
0x1400473e0  jz      loc_14004768F
0x1400473e6  cmp     byte ptr [rcx+29h], 2
0x1400473ea  jb      loc_14004768F
0x1400473f0  mov     rcx, [rcx+18h]
0x1400473f4  lea     edx, [rbx+0Ah]
0x1400473f7  mov     r9d, edi
0x1400473fa  lea     r8, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids
0x140047401  call    WPP_SF_d
0x140047406  jmp     loc_14004768F
0x14004740b  movups  xmm0, xmmword ptr [rbp+0]
0x14004740f  lea     r8, [rsi+rsi*8]
0x140047413  xor     edi, edi
0x140047415  movups  xmm1, xmmword ptr [rbp+10h]
0x140047419  shl     r8, 4; Size
0x14004741d  lea     rcx, [rax+30h]; void *
0x140047421  movups  xmmword ptr [rax], xmm0
0x140047424  xor     edx, edx; Val
0x140047426  movups  xmm0, xmmword ptr [rbp+20h]
0x14004742a  movups  xmmword ptr [rax+10h], xmm1
0x14004742e  movups  xmmword ptr [rax+20h], xmm0
0x140047432  mov     [rax+4], edi
0x140047435  call    memset
0x14004743a  mov     r15d, [rbp+4]
0x14004743e  xor     edx, edx
0x140047440  xor     r11b, r11b
0x140047443  xor     r10d, r10d
0x140047446  cmp     r10d, r15d
0x140047449  jnb     loc_140047663
0x14004744f  xor     r14d, r14d
0x140047452  xor     r8d, r8d
0x140047455  lea     eax, [r10+r8]
0x140047459  cmp     eax, r15d
0x14004745c  jnb     loc_1400475D3
0x140047462  cmp     r8d, 4
0x140047466  jnb     loc_1400475D3
0x14004746c  lea     r9, [rax+rax*8]
0x140047470  shl     r9, 4
0x140047474  add     r9, rbp
0x140047477  mov     al, [r9+50h]
0x14004747b  test    al, al
0x14004747d  jz      loc_1400475CB
0x140047483  cmp     al, 42h ; 'B'
0x140047485  jz      loc_1400475CB
0x14004748b  cmp     al, 5
0x14004748d  jz      loc_1400475C7
0x140047493  cmp     al, 0Fh
0x140047495  jz      loc_1400475C7
0x14004749b  test    r11b, r11b
0x14004749e  jz      loc_14004753D
0x1400474a4  cmp     edx, esi
0x1400474a6  jnb     loc_1400475E2
0x1400474ac  test    rdi, rdi
0x1400474af  jz      loc_1400475E2
0x1400474b5  movups  xmm0, xmmword ptr [rdi]
0x1400474b8  lea     rcx, [rdx+rdx*8]
0x1400474bc  movups  xmm1, xmmword ptr [rdi+10h]
0x1400474c0  add     rcx, rcx
0x1400474c3  movups  xmmword ptr [rbx+rcx*8+30h], xmm0
0x1400474c8  movups  xmm0, xmmword ptr [rdi+20h]
0x1400474cc  movups  xmmword ptr [rbx+rcx*8+40h], xmm1
0x1400474d1  movups  xmm1, xmmword ptr [rdi+30h]
0x1400474d5  movups  xmmword ptr [rbx+rcx*8+50h], xmm0
0x1400474da  movups  xmm0, xmmword ptr [rdi+40h]
0x1400474de  movups  xmmword ptr [rbx+rcx*8+60h], xmm1
0x1400474e3  movups  xmm1, xmmword ptr [rdi+50h]
0x1400474e7  movups  xmmword ptr [rbx+rcx*8+70h], xmm0
0x1400474ec  movups  xmm0, xmmword ptr [rdi+60h]
0x1400474f0  movups  xmmword ptr [rbx+rcx*8+80h], xmm1
0x1400474f8  movups  xmm1, xmmword ptr [rdi+70h]
0x1400474fc  movups  xmmword ptr [rbx+rcx*8+90h], xmm0
0x140047504  movups  xmm0, xmmword ptr [rdi+80h]
0x14004750b  movups  xmmword ptr [rbx+rcx*8+0A0h], xmm1
0x140047513  movups  xmmword ptr [rbx+rcx*8+0B0h], xmm0
0x14004751b  mov     byte ptr [rbx+rcx*8+50h], 0Fh
0x140047520  jmp     short loc_14004752E
0x140047522  lea     rcx, [rdx+rdx*8]
0x140047526  add     rcx, rcx
0x140047529  mov     byte ptr [rbx+rcx*8+50h], 0
0x14004752e  inc     edx
0x140047530  mov     byte ptr [rbx+rcx*8+4Ch], 1
0x140047535  test    dl, 3
0x140047538  jnz     short loc_140047522
0x14004753a  xor     r11b, r11b
0x14004753d  cmp     edx, esi
0x14004753f  jnb     loc_140047612
0x140047545  movups  xmm0, xmmword ptr [r9+30h]
0x14004754a  lea     rcx, [rdx+rdx*8]
0x14004754e  movups  xmm1, xmmword ptr [r9+40h]
0x140047553  add     rcx, rcx
0x140047556  inc     edx
0x140047558  movups  xmmword ptr [rbx+rcx*8+30h], xmm0
0x14004755d  movups  xmm0, xmmword ptr [r9+50h]
0x140047562  movups  xmmword ptr [rbx+rcx*8+40h], xmm1
0x140047567  movups  xmm1, xmmword ptr [r9+60h]
0x14004756c  movups  xmmword ptr [rbx+rcx*8+50h], xmm0
0x140047571  movups  xmm0, xmmword ptr [r9+70h]
0x140047576  movups  xmmword ptr [rbx+rcx*8+60h], xmm1
0x14004757b  movups  xmm1, xmmword ptr [r9+80h]
0x140047583  movups  xmmword ptr [rbx+rcx*8+70h], xmm0
0x140047588  movups  xmm0, xmmword ptr [r9+90h]
0x140047590  movups  xmmword ptr [rbx+rcx*8+80h], xmm1
0x140047598  movups  xmm1, xmmword ptr [r9+0A0h]
0x1400475a0  movups  xmmword ptr [rbx+rcx*8+90h], xmm0
0x1400475a8  movups  xmm0, xmmword ptr [r9+0B0h]
0x1400475b0  movups  xmmword ptr [rbx+rcx*8+0A0h], xmm1
0x1400475b8  movups  xmmword ptr [rbx+rcx*8+0B0h], xmm0
0x1400475c0  mov     byte ptr [rbx+rcx*8+4Ch], 1
0x1400475c5  jmp     short loc_1400475CB
0x1400475c7  lea     r14, [r9+30h]
0x1400475cb  inc     r8d
0x1400475ce  jmp     loc_140047455
0x1400475d3  mov     rdi, r14
0x1400475d6  mov     r11b, 1
0x1400475d9  add     r10d, 4
0x1400475dd  jmp     loc_140047446
0x1400475e2  mov     r9d, 0C038000Bh
0x1400475e8  mov     edi, r9d
0x1400475eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400475f2  lea     rax, WPP_GLOBAL_Control
0x1400475f9  cmp     rcx, rax
0x1400475fc  jz      short loc_140047650
0x1400475fe  mov     eax, [rcx+2Ch]
0x140047601  test    al, 10h
0x140047603  jz      short loc_140047650
0x140047605  cmp     byte ptr [rcx+29h], 2
0x140047609  jb      short loc_140047650
0x14004760b  mov     edx, 0Bh
0x140047610  jmp     short loc_140047640
0x140047612  mov     r9d, 0C038000Bh
0x140047618  mov     edi, r9d
0x14004761b  mov     rcx, cs:WPP_GLOBAL_Control
0x140047622  lea     rax, WPP_GLOBAL_Control
0x140047629  cmp     rcx, rax
0x14004762c  jz      short loc_140047650
0x14004762e  mov     eax, [rcx+2Ch]
0x140047631  test    al, 10h
0x140047633  jz      short loc_140047650
0x140047635  cmp     byte ptr [rcx+29h], 2
0x140047639  jb      short loc_140047650
0x14004763b  mov     edx, 0Ch
0x140047640  mov     rcx, [rcx+18h]
0x140047644  lea     r8, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids
0x14004764b  call    WPP_SF_d
0x140047650  xor     edx, edx; Tag
0x140047652  mov     rcx, rbx; P
0x140047655  call    cs:__imp_ExFreePoolWithTag
0x14004765c  nop     dword ptr [rax+rax+00h]
0x140047661  jmp     short loc_14004768F
0x140047663  xor     edi, edi
0x140047665  jmp     short loc_140047684
0x140047667  test    dl, 3
0x14004766a  jnz     short loc_140047671
0x14004766c  cmp     edx, 4
0x14004766f  jnb     short loc_140047688
0x140047671  lea     rcx, [rdx+rdx*8]
0x140047675  add     rcx, rcx
0x140047678  inc     edx
0x14004767a  mov     [rbx+rcx*8+50h], dil
0x14004767f  mov     byte ptr [rbx+rcx*8+4Ch], 1
0x140047684  cmp     edx, esi
0x140047686  jb      short loc_140047667
0x140047688  mov     [rbx+4], edx
0x14004768b  mov     [r12], rbx
0x14004768f  mov     eax, edi
0x140047691  add     rsp, 20h
0x140047695  pop     r15
0x140047697  pop     r14
0x140047699  pop     r12
0x14004769b  pop     rdi
0x14004769c  pop     rsi
0x14004769d  pop     rbp
0x14004769e  pop     rbx
0x14004769f  retn
```
