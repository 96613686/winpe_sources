# CTSparseBlock<ulong,CASFV1MetadataObject::METADATA_REC,20,0>::RemoveValue(ulong)

- ea: `0x180020030`
- end: `0x1800201c0`
- name: `?RemoveValue@?$CTSparseBlock@KUMETADATA_REC@CASFV1MetadataObject@@$0BE@$0A@@@QEAAJK@Z`
- size: `400`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001fcf0`

## callees

- `0x180020030`
- `0x180025b2c`
- `0x18002a07c`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,CASFV1MetadataObject::METADATA_REC,20,0>::RemoveValue(
        __int64 a1,
        unsigned int a2)
{
  __int64 i; // rbx
  __int64 v5; // rax
  int v6; // r12d
  int v7; // edx
  int v8; // r14d
  unsigned int v9; // edx
  int v10; // r15d
  unsigned int v11; // esi
  __int128 v12; // xmm1
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r10
  char j; // r11
  unsigned __int8 v17; // si
  _OWORD v19[5]; // [rsp+20h] [rbp-58h] BYREF

  for ( i = a1; i; i = *(_QWORD *)(i + 568) )
  {
    if ( a2 < *(_DWORD *)(i + 8) + 20 )
      break;
  }
  v5 = *(_QWORD *)(a1 + 576);
  v6 = 0;
  if ( v5 )
  {
    v7 = *(_DWORD *)(a1 + 584);
    if ( a2 < v7 + *(_DWORD *)(v5 + 8) )
    {
      if ( v7 )
        *(_DWORD *)(a1 + 584) = v7 - 1;
      else
        v6 = 1;
    }
  }
  v8 = 0;
  while ( i )
  {
    v9 = *(_DWORD *)(i + 8);
    if ( a2 < v9 )
    {
      v10 = 0;
      v11 = 0;
      if ( (*(_BYTE *)(i + 42)
          & (unsigned __int8)CTSparseBlock<unsigned long,CASFV1MetadataObject::METADATA_REC,20,0>::s_bSingleBitMasks) != 0 )
      {
        v12 = *(_OWORD *)(i + 55);
        v19[0] = *(_OWORD *)(i + 45);
        *(_OWORD *)((char *)v19 + 10) = v12;
        v8 = CTSparseBlock<unsigned long,CASFV1MetadataObject::METADATA_REC,20,0>::SetValue(a1, v9 - 1, v19);
        if ( v8 < 0 )
          return (unsigned int)v8;
      }
    }
    else
    {
      v10 = 1;
      v11 = a2 - v9;
    }
    memmove_0((void *)(i + 26LL * v11 + 45), (const void *)(i + 26LL * (v11 + 1) + 45), 26LL * (19 - v11));
    v13 = v11 >> 3;
    v14 = v13;
    v15 = v13 + i;
    for ( j = *(_BYTE *)(v13 + i + 42); (unsigned int)v14 < 3; v14 = (unsigned int)(v14 + 1) )
    {
      *(_BYTE *)(v14 + i + 42) *= 2;
      if ( (unsigned int)v14 < 2 && *(char *)((unsigned int)(v14 + 1) + i + 42) < 0 )
        *(_BYTE *)(v14 + i + 42) |= 1u;
    }
    if ( v10 )
    {
      v17 = v11 & 7;
      if ( v17 )
      {
        *(_BYTE *)(v15 + 42) &= *((_BYTE *)&qword_1800320F8 - v17);
        *(_BYTE *)(v15 + 42) |= j
                              & *((_BYTE *)CTSparseBlock<unsigned long,CASFV1MetadataObject::METADATA_REC,20,0>::s_bLeftBitMasks
                                + v17);
      }
    }
    if ( v6 && *(_QWORD *)(i + 568) == *(_QWORD *)(a1 + 576) )
    {
      *(_QWORD *)(a1 + 576) = i;
      *(_DWORD *)(a1 + 584) = 19;
    }
    i = *(_QWORD *)(i + 568);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180020030  push    rbx
0x180020032  push    rbp
0x180020033  push    rsi
0x180020034  push    rdi
0x180020035  push    r12
0x180020037  push    r14
0x180020039  push    r15
0x18002003b  sub     rsp, 40h
0x18002003f  mov     ebp, edx
0x180020041  mov     rdi, rcx
0x180020044  mov     rbx, rcx
0x180020047  test    rcx, rcx
0x18002004a  jz      short loc_180020062
0x18002004c  mov     eax, [rbx+8]
0x18002004f  add     eax, 14h
0x180020052  cmp     ebp, eax
0x180020054  jb      short loc_180020062
0x180020056  mov     rbx, [rbx+238h]
0x18002005d  test    rbx, rbx
0x180020060  jnz     short loc_18002004C
0x180020062  mov     rax, [rcx+240h]
0x180020069  xor     r12d, r12d
0x18002006c  test    rax, rax
0x18002006f  jz      short loc_180020093
0x180020071  mov     edx, [rcx+248h]
0x180020077  mov     ecx, [rax+8]
0x18002007a  add     ecx, edx
0x18002007c  cmp     ebp, ecx
0x18002007e  jnb     short loc_180020093
0x180020080  test    edx, edx
0x180020082  jnz     short loc_18002008A
0x180020084  lea     r12d, [rdx+1]
0x180020088  jmp     short loc_180020093
0x18002008a  lea     eax, [rdx-1]
0x18002008d  mov     [rdi+248h], eax
0x180020093  xor     r14d, r14d
0x180020096  jmp     loc_1800201A5
0x18002009b  mov     edx, [rbx+8]
0x18002009e  cmp     ebp, edx
0x1800200a0  jb      short loc_1800200AE
0x1800200a2  mov     esi, ebp
0x1800200a4  mov     r15d, 1
0x1800200aa  sub     esi, edx
0x1800200ac  jmp     short loc_1800200EA
0x1800200ae  mov     al, [rbx+2Ah]
0x1800200b1  xor     r15d, r15d
0x1800200b4  xor     esi, esi
0x1800200b6  test    cs:?s_bSingleBitMasks@?$CTSparseBlock@KUMETADATA_REC@CASFV1MetadataObject@@$0BE@$0A@@@0PAEA, al; uchar near * CTSparseBlock<ulong,CASFV1MetadataObject::METADATA_REC,20,0>::s_bSingleBitMasks
0x1800200bc  jz      short loc_1800200EA
0x1800200be  movups  xmm0, xmmword ptr [rbx+2Dh]
0x1800200c2  dec     edx
0x1800200c4  lea     r8, [rsp+78h+var_58]
0x1800200c9  movups  xmm1, xmmword ptr [rbx+37h]
0x1800200cd  mov     rcx, rdi
0x1800200d0  movaps  [rsp+78h+var_58], xmm0
0x1800200d5  movups  [rsp+78h+var_58+0Ah], xmm1
0x1800200da  call    ?SetValue@?$CTSparseBlock@KUMETADATA_REC@CASFV1MetadataObject@@$0BE@$0A@@@QEAAJKUMETADATA_REC@CASFV1MetadataObject@@@Z; CTSparseBlock<ulong,CASFV1MetadataObject::METADATA_REC,20,0>::SetValue(ulong,CASFV1MetadataObject::METADATA_REC)
0x1800200df  mov     r14d, eax
0x1800200e2  test    eax, eax
0x1800200e4  js      loc_1800201AE
0x1800200ea  mov     eax, 13h
0x1800200ef  lea     ecx, [rsi+1]
0x1800200f2  imul    rdx, rcx, 1Ah
0x1800200f6  sub     eax, esi
0x1800200f8  imul    r8, rax, 1Ah; Size
0x1800200fc  mov     eax, esi
0x1800200fe  add     rdx, 2Dh ; '-'
0x180020102  imul    rcx, rax, 1Ah
0x180020106  add     rdx, rbx; Src
0x180020109  add     rcx, 2Dh ; '-'
0x18002010d  add     rcx, rbx; void *
0x180020110  call    memmove_0
0x180020115  mov     eax, esi
0x180020117  shr     eax, 3
0x18002011a  mov     edx, eax
0x18002011c  lea     r10, [rax+rbx]
0x180020120  mov     r11b, [r10+2Ah]
0x180020124  cmp     eax, 3
0x180020127  jnb     short loc_180020148
0x180020129  shl     byte ptr [rdx+rbx+2Ah], 1
0x18002012d  cmp     edx, 2
0x180020130  jnb     short loc_180020141
0x180020132  lea     eax, [rdx+1]
0x180020135  cmp     byte ptr [rax+rbx+2Ah], 0
0x18002013a  jge     short loc_180020141
0x18002013c  or      byte ptr [rdx+rbx+2Ah], 1
0x180020141  inc     edx
0x180020143  cmp     edx, 3
0x180020146  jb      short loc_180020129
0x180020148  test    r15d, r15d
0x18002014b  jz      short loc_180020178
0x18002014d  and     sil, 7
0x180020151  jbe     short loc_180020178
0x180020153  movzx   ecx, sil
0x180020157  lea     rax, qword_1800320F8
0x18002015e  sub     rax, rcx
0x180020161  mov     al, [rax]
0x180020163  and     [r10+2Ah], al
0x180020167  lea     rax, ?s_bLeftBitMasks@?$CTSparseBlock@KUMETADATA_REC@CASFV1MetadataObject@@$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,CASFV1MetadataObject::METADATA_REC,20,0>::s_bLeftBitMasks
0x18002016e  mov     al, [rcx+rax]
0x180020171  and     al, r11b
0x180020174  or      [r10+2Ah], al
0x180020178  test    r12d, r12d
0x18002017b  jz      short loc_18002019E
0x18002017d  mov     rax, [rdi+240h]
0x180020184  cmp     [rbx+238h], rax
0x18002018b  jnz     short loc_18002019E
0x18002018d  mov     [rdi+240h], rbx
0x180020194  mov     dword ptr [rdi+248h], 13h
0x18002019e  mov     rbx, [rbx+238h]
0x1800201a5  test    rbx, rbx
0x1800201a8  jnz     loc_18002009B
0x1800201ae  mov     eax, r14d
0x1800201b1  add     rsp, 40h
0x1800201b5  pop     r15
0x1800201b7  pop     r14
0x1800201b9  pop     r12
0x1800201bb  pop     rdi
0x1800201bc  pop     rsi
0x1800201bd  pop     rbp
0x1800201be  pop     rbx
0x1800201bf  retn
```
